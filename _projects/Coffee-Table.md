<script type="module">
import * as THREE from 'three';
import { OrbitControls } from 'three/addons/controls/OrbitControls.js';
import { GLTFLoader } from 'three/addons/loaders/GLTFLoader.js';

const canvas    = document.getElementById('ct-canvas');
const loading   = document.getElementById('ct-loading');
const btnRotate = document.getElementById('ct-btn-rotate');
const explodeSlider = document.getElementById('ct-explode-slider');

if (!canvas) { console.warn('ct-canvas not found'); }

const renderer = new THREE.WebGLRenderer({ canvas, antialias: true, alpha: true });
renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
renderer.shadowMap.enabled = true;
renderer.shadowMap.type = THREE.PCFSoftShadowMap;
renderer.outputColorSpace = THREE.SRGBColorSpace;
renderer.toneMapping = THREE.ACESFilmicToneMapping;
renderer.toneMappingExposure = 1.1;

const wrap = canvas.parentElement;
renderer.setSize(wrap.clientWidth, wrap.clientHeight);

const scene = new THREE.Scene();
scene.background = new THREE.Color(0xf0f5ee);
scene.fog = new THREE.Fog(0xf0f5ee, 12, 30);

const camera = new THREE.PerspectiveCamera(45, wrap.clientWidth / wrap.clientHeight, 0.01, 100);
camera.position.set(2.2, 1.4, 2.8);

const controls = new OrbitControls(camera, renderer.domElement);
controls.enableDamping = true;
controls.dampingFactor = 0.06;
controls.minDistance = 0.5;
controls.maxDistance = 12;
controls.maxPolarAngle = Math.PI / 2 + 0.15;
controls.target.set(0, 0.3, 0);
controls.update();

// Lighting
const ambient = new THREE.AmbientLight(0xfff8f0, 0.7);
scene.add(ambient);

const sun = new THREE.DirectionalLight(0xfff8ee, 1.6);
sun.position.set(3, 5, 4);
sun.castShadow = true;
sun.shadow.mapSize.set(2048, 2048);
sun.shadow.camera.near = 0.5;
sun.shadow.camera.far = 20;
sun.shadow.camera.left = -3;
sun.shadow.camera.right = 3;
sun.shadow.camera.top = 3;
sun.shadow.camera.bottom = -3;
sun.shadow.bias = -0.001;
scene.add(sun);

const fill = new THREE.DirectionalLight(0xd4e8ff, 0.5);
fill.position.set(-3, 2, -2);
scene.add(fill);

const rim = new THREE.DirectionalLight(0xfff0e0, 0.35);
rim.position.set(0, 3, -5);
scene.add(rim);

// Ground shadow plane
const groundGeo = new THREE.PlaneGeometry(20, 20);
const groundMat = new THREE.ShadowMaterial({ opacity: 0.12 });
const ground = new THREE.Mesh(groundGeo, groundMat);
ground.rotation.x = -Math.PI / 2;
ground.position.y = -0.01;
ground.receiveShadow = true;
scene.add(ground);

// Load model
const loader = new GLTFLoader();
const modelPath = "{{ '/assets/models/Table (Assembly).gltf' | relative_url }}";
let autoRotate = true;
let model = null;
let defaultCamPos = camera.position.clone();
let defaultTarget = controls.target.clone();

// --- Explode state ---
const explodeData = [];   // { mesh, direction }  — direction in the mesh's own local space
let explodeFactor = 0;    // 0 = assembled, 1 = fully exploded
const EXPLODE_DISTANCE = 0.4; // in model's native units (meters); tune to taste

loader.load(
  modelPath,
  (gltf) => {
    model = gltf.scene;

    // Center and scale
    const box = new THREE.Box3().setFromObject(model);
    const center = box.getCenter(new THREE.Vector3());
    const size = box.getSize(new THREE.Vector3());
    const maxDim = Math.max(size.x, size.y, size.z);
    const scale = 1.8 / maxDim;

    model.scale.setScalar(scale);
    model.position.sub(center.multiplyScalar(scale));

    // Sit on ground
    const box2 = new THREE.Box3().setFromObject(model);
    model.position.y -= box2.min.y;

    // Enable shadows
    model.traverse((child) => {
      if (child.isMesh) {
        child.castShadow = true;
        child.receiveShadow = true;
        if (child.material) {
          child.material.envMapIntensity = 0.4;
        }
      }
    });

    scene.add(model);
    model.updateMatrixWorld(true);

    // Recompute the model's center in world space (post scale/position fix) — used only for the camera
    const modelBox = new THREE.Box3().setFromObject(model);
    const modelCenter = modelBox.getCenter(new THREE.Vector3());

    // --- Build explode groups ---
    // Names live on each mesh's PARENT node in this GLTF ("Tabletop" / "Leg Design 1, Segmented"),
    // not on the mesh itself — so we read child.parent.name, not child.name.
    const legMeshes = [];
    const topMeshes = [];

    model.traverse((child) => {
      if (!child.isMesh) return;
      const groupName = child.parent ? child.parent.name : '';
      if (groupName === 'Tabletop') {
        topMeshes.push(child);
      } else if (groupName && groupName.startsWith('Leg Design')) {
        legMeshes.push(child);
      }
    });

    // Stable per-mesh reference point in the mesh's own LOCAL geometry space.
    // This is unaffected by the model's continuous auto-rotation, unlike world position,
    // which is why explode directions must be computed this way rather than via getWorldPosition.
    function localCentroid(mesh) {
      if (!mesh.geometry.boundingBox) mesh.geometry.computeBoundingBox();
      const c = new THREE.Vector3();
      mesh.geometry.boundingBox.getCenter(c);
      return c;
    }

    const allMeshes = [...topMeshes, ...legMeshes];
    const overallCenter = new THREE.Vector3();
    allMeshes.forEach((m) => overallCenter.add(localCentroid(m)));
    overallCenter.divideScalar(allMeshes.length);

    // Bucket the 80 leg segments into 4 quadrants using local centroid position
    const quadrants = [[], [], [], []]; // ++, +-, -+, --  (x,z signs)
    legMeshes.forEach((mesh) => {
      const c = localCentroid(mesh);
      const dx = c.x - overallCenter.x;
      const dz = c.z - overallCenter.z;
      let idx;
      if (dx >= 0 && dz >= 0) idx = 0;
      else if (dx >= 0 && dz < 0) idx = 1;
      else if (dx < 0 && dz >= 0) idx = 2;
      else idx = 3;
      quadrants[idx].push(mesh);
    });

    function quadrantDirection(meshes) {
      if (meshes.length === 0) return new THREE.Vector3(1, 0, 0);
      const centroid = new THREE.Vector3();
      meshes.forEach((m) => centroid.add(localCentroid(m)));
      centroid.divideScalar(meshes.length);
      const dir = centroid.clone().sub(overallCenter);
      dir.y = 0; // push legs outward, horizontally
      if (dir.lengthSq() < 1e-8) return new THREE.Vector3(1, 0, 0);
      return dir.normalize();
    }

    quadrants.forEach((group) => {
      if (group.length === 0) return;
      const dir = quadrantDirection(group);
      group.forEach((mesh) => {
        explodeData.push({ mesh, direction: dir.clone() });
      });
    });

    // Tabletop lifts straight up
    topMeshes.forEach((mesh) => {
      explodeData.push({ mesh, direction: new THREE.Vector3(0, 1, 0) });
    });

    // Sanity check — should read 6 and 80
    console.log('Top meshes found:', topMeshes.length, '/ expected 6');
    console.log('Leg meshes found:', legMeshes.length, '/ expected 80');

    // Update camera target to model center
    controls.target.copy(modelCenter);
    defaultTarget = modelCenter.clone();
    camera.position.set(modelCenter.x + 2.2, modelCenter.y + 1.4, modelCenter.z + 2.8);
    defaultCamPos = camera.position.clone();
    controls.update();

    loading.style.display = 'none';
  },
  (xhr) => {
    if (xhr.total) {
      const pct = Math.round(xhr.loaded / xhr.total * 100);
      const span = loading.querySelector('span');
      if (span) span.textContent = `Loading model… ${pct}%`;
    }
  },
  (err) => {
    console.error('GLTF load error:', err);
    loading.innerHTML = '<span style="color:#a05050;font-family:DM Mono,monospace;font-size:11px;">Model failed to load</span>';
  }
);

// Sets each mesh's LOCAL position directly. Every mesh in this GLTF starts at local (0,0,0),
// so we don't need to add to an "original" position or convert through world/local space —
// which is what caused the previous bug (skewed offsets due to the model's live rotation
// at the moment the slider/wheel was used).
function applyExplode(factor) {
  explodeData.forEach(({ mesh, direction }) => {
    mesh.position.copy(direction.clone().multiplyScalar(factor * EXPLODE_DISTANCE));
  });
}

// Shift + scroll controls explode; plain scroll still zooms via OrbitControls
wrap.addEventListener('wheel', (e) => {
  if (!e.shiftKey) return;
  e.preventDefault();

  const delta = e.deltaY !== 0 ? e.deltaY : e.deltaX;
  const step = 0.0015;
  explodeFactor = THREE.MathUtils.clamp(explodeFactor + delta * step, 0, 1);

  applyExplode(explodeFactor);
  if (explodeSlider) explodeSlider.value = Math.round(explodeFactor * 100);
}, { passive: false });

// Resize
const resizeObserver = new ResizeObserver(() => {
  const w = wrap.clientWidth;
  const h = wrap.clientHeight;
  camera.aspect = w / h;
  camera.updateProjectionMatrix();
  renderer.setSize(w, h);
});
resizeObserver.observe(wrap);

// Render loop
function animate() {
  requestAnimationFrame(animate);
  if (autoRotate && model) {
    model.rotation.y += 0.004;
  }
  controls.update();
  renderer.render(scene, camera);
}
animate();

// Exposed controls
window.ctToggleRotate = function() {
  autoRotate = !autoRotate;
  if (btnRotate) btnRotate.textContent = autoRotate ? 'Pause rotation' : 'Resume rotation';
};

window.ctResetCamera = function() {
  camera.position.copy(defaultCamPos);
  controls.target.copy(defaultTarget);
  controls.update();
};

if (explodeSlider) {
  explodeSlider.addEventListener('input', (e) => {
    explodeFactor = Number(e.target.value) / 100;
    applyExplode(explodeFactor);
  });
}
</script>