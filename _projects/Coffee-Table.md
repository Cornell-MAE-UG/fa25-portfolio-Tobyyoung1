---
layout: project
title: Coffee Table
description: Handmade furniture — designed in Fusion 360, built in pine
image: /assets/images/Coffee-Table-Finished.jpeg
---

<style>
  @import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Mono:wght@400;500&family=Instrument+Sans:wght@400;500;600&display=swap');

  main.container {
    max-width: 100% !important;
    padding-left: 4rem !important;
    padding-right: 4rem !important;
  }

  .ct-page {
    font-family: 'Instrument Sans', sans-serif;
    max-width: 100%;
    width: 100%;
    margin: 0;
    padding: 2rem 0 4rem;
    color: #1a1a18;
    box-sizing: border-box;
  }

  .ct-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: #7a8c6e;
    margin: 0 0 0.5rem;
  }

  .ct-title {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(2rem, 5vw, 3rem);
    font-weight: 400;
    line-height: 1.1;
    color: #1a1a18;
    margin: 0 0 0.75rem;
  }

  .ct-subtitle {
    font-size: 17px;
    color: #5a6652;
    margin: 0 0 2rem;
    line-height: 1.5;
    max-width: 560px;
  }

  .ct-tag-row {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-bottom: 2rem;
  }

  .ct-tag {
    font-family: 'DM Mono', monospace;
    font-size: 10.5px;
    letter-spacing: 0.04em;
    background: #eaf1e6;
    color: #4a6741;
    border: 1px solid #c0d4b8;
    border-radius: 3px;
    padding: 3px 8px;
  }

  .ct-toc-label {
    font-family: 'DM Mono', monospace;
    font-size: 10.5px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: #9aaa8e;
    margin-bottom: 0.5rem;
  }

  .ct-accordion {
    border: 1px solid #d4dece;
    border-radius: 8px;
    overflow: hidden;
    margin-bottom: 3rem;
  }

  .ct-accordion-item {
    border-bottom: 1px solid #d4dece;
  }

  .ct-accordion-item:last-child {
    border-bottom: none;
  }

  .ct-accordion-trigger {
    width: 100%;
    background: #f7f9f5;
    border: none;
    cursor: pointer;
    display: grid;
    grid-template-columns: 2rem 1fr auto;
    align-items: center;
    gap: 0.75rem;
    padding: 1rem 1.25rem;
    text-align: left;
    transition: background 0.15s;
  }

  .ct-accordion-trigger:hover { background: #eff3ec; }
  .ct-accordion-trigger[aria-expanded="true"] { background: #eaf1e6; }

  .ct-acc-num {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: #9aaa8e;
    letter-spacing: 0.05em;
  }

  .ct-acc-title {
    font-size: 14px;
    font-weight: 600;
    color: #2a3328;
    line-height: 1.3;
  }

  .ct-acc-meta {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: #a0af94;
    letter-spacing: 0.04em;
    display: block;
    font-weight: 400;
  }

  .ct-acc-chevron {
    width: 16px;
    height: 16px;
    color: #7a8c6e;
    transition: transform 0.25s ease;
    flex-shrink: 0;
  }

  .ct-accordion-trigger[aria-expanded="true"] .ct-acc-chevron {
    transform: rotate(180deg);
  }

  .ct-accordion-panel {
    display: none;
    padding: 1.5rem 1.5rem 1.75rem;
    background: #fff;
    border-top: 1px solid #e4ede0;
  }

  .ct-accordion-panel.is-open { display: block; }

  .ct-section-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: #7a8c6e;
    margin: 0 0 0.35rem;
  }

  .ct-section-title {
    font-family: 'DM Serif Display', serif;
    font-size: 1.4rem;
    font-weight: 400;
    color: #1a1a18;
    margin: 0 0 1rem;
    line-height: 1.2;
  }

  .ct-body {
    font-size: 16px;
    line-height: 1.75;
    color: #2e3830;
  }

  .ct-body p { margin: 0 0 0.9rem; }

  .ct-body ul {
    margin: 0 0 0.9rem;
    padding-left: 1.4rem;
  }

  .ct-body li { margin-bottom: 0.35rem; }

  .ct-body strong {
    font-weight: 600;
    color: #1a1a18;
  }

  .ct-divider {
    border: none;
    border-top: 1px solid #e2ece0;
    margin: 1.5rem 0;
  }

  /* Photo grid */
  .ct-photo-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1rem;
    margin: 1rem 0 1.25rem;
  }

  .ct-photo-grid figure {
    margin: 0;
    display: flex;
    flex-direction: column;
  }

  .ct-photo-grid img {
    width: 100%;
    border-radius: 6px;
    border: 1px solid #d4dece;
    object-fit: cover;
    aspect-ratio: 4 / 3;
    display: block;
  }

  .ct-photo-grid figcaption {
    font-family: 'DM Mono', monospace;
    font-size: 10.5px;
    color: #7a8c6e;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    margin-top: 0.4rem;
  }

  .ct-photo-single img {
    width: 100%;
    border-radius: 8px;
    border: 1px solid #d4dece;
    object-fit: cover;
    max-height: 480px;
    display: block;
  }

  .ct-photo-single figcaption {
    font-family: 'DM Mono', monospace;
    font-size: 10.5px;
    color: #7a8c6e;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    margin-top: 0.5rem;
  }

  /* Spec table */
  .ct-spec-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 14px;
    margin: 0.75rem 0 1.25rem;
  }

  .ct-spec-table td {
    padding: 7px 10px;
    border-bottom: 1px solid #e4ede0;
    vertical-align: top;
  }

  .ct-spec-table tr:last-child td { border-bottom: none; }

  .ct-spec-table td:first-child {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: #7a8c6e;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    width: 38%;
  }

  .ct-spec-table td:last-child {
    color: #2a3328;
    font-weight: 500;
  }

  /* Step cards */
  .ct-step-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 0.75rem;
    margin: 1rem 0 1.25rem;
  }

  .ct-step-card {
    background: #f7f9f5;
    border: 1px solid #d4dece;
    border-radius: 6px;
    padding: 0.85rem 1rem;
  }

  .ct-step-num {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: #7a8c6e;
    letter-spacing: 0.1em;
    margin-bottom: 0.25rem;
  }

  .ct-step-name {
    font-size: 14px;
    font-weight: 600;
    color: #2a3328;
    margin-bottom: 0.3rem;
  }

  .ct-step-desc {
    font-size: 13px;
    color: #5a6a54;
    line-height: 1.5;
  }

  /* 3D Viewer */
  .ct-viewer-wrap {
    position: relative;
    width: 100%;
    height: 480px;
    border-radius: 8px;
    border: 1px solid #d4dece;
    overflow: hidden;
    background: #f0f5ee;
    margin-bottom: 1rem;
  }

  #ct-canvas {
    width: 100%;
    height: 100%;
    display: block;
  }

  .ct-viewer-loading {
    position: absolute;
    inset: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background: #f0f5ee;
    gap: 12px;
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: #7a8c6e;
    letter-spacing: 0.08em;
  }

  .ct-spinner {
    width: 28px;
    height: 28px;
    border: 2px solid #d4dece;
    border-top-color: #4a6741;
    border-radius: 50%;
    animation: ct-spin 0.8s linear infinite;
  }

  @keyframes ct-spin { to { transform: rotate(360deg); } }

  .ct-viewer-controls {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    margin-bottom: 0.5rem;
  }

  .ct-viewer-btn {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.04em;
    color: #4a6741;
    background: #f0f5ee;
    border: 1px solid #b8c9b0;
    border-radius: 4px;
    padding: 5px 12px;
    cursor: pointer;
    transition: background 0.15s, border-color 0.15s;
  }

  .ct-viewer-btn:hover {
    background: #e2ede0;
    border-color: #8aab7e;
  }

  .ct-viewer-hint {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: #9aaa8e;
    letter-spacing: 0.05em;
    margin-top: 0.25rem;
  }

  @media (max-width: 640px) {
    .ct-photo-grid { grid-template-columns: 1fr; }
    .ct-step-grid { grid-template-columns: 1fr; }
    .ct-viewer-wrap { height: 320px; }
    main.container {
      padding-left: 1.25rem !important;
      padding-right: 1.25rem !important;
    }
  }
</style>

<div class="ct-page">

  <p class="ct-eyebrow">Personal Project · Summer 2025</p>
  <h1 class="ct-title">Coffee Table</h1>
  <p class="ct-subtitle">
    A handmade coffee table designed from scratch in Fusion 360 and built in pine — featuring curved tapered legs and a butcher-block-style top.
  </p>

  <div class="ct-tag-row">
    <span class="ct-tag">Fusion 360</span>
    <span class="ct-tag">Pine</span>
    <span class="ct-tag">Jigsaw</span>
    <span class="ct-tag">Circular Saw</span>
    <span class="ct-tag">Pocket Hole Joinery</span>
    <span class="ct-tag">Furniture Design</span>
    <span class="ct-tag">CAD</span>
  </div>

  <p class="ct-toc-label">Sections</p>
  <div class="ct-accordion">

    <!-- Section 1: Design -->
    <div class="ct-accordion-item">
      <button class="ct-accordion-trigger" aria-expanded="false" aria-controls="panel-design" onclick="ctToggle(this,'panel-design')">
        <span class="ct-acc-num">01</span>
        <span>
          <span class="ct-acc-title">Design</span>
          <span class="ct-acc-meta">Leg geometry, CAD modelling, and drawings</span>
        </span>
        <svg class="ct-acc-chevron" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.75">
          <path d="M3 6l5 5 5-5"/>
        </svg>
      </button>
      <div class="ct-accordion-panel" id="panel-design">

        <p class="ct-section-label">Concept</p>
        <h2 class="ct-section-title">Curved tapered legs, designed in Fusion 360</h2>
        <div class="ct-body">
          <p>The defining feature of the table is its leg profile — a curved inner face with an 8" radius concave sweep, tapering from a wide foot to a narrow top. Each leg is built from three separate pieces of fir rather than a single blank: a central 2×2 post, mitered at a 5° angle from corner to corner at both the top and bottom to create a diagonal tilt, flanked by two curved arches — one leaning in each direction — attached on either side to form the finished corner leg.</p>
          <p>Each leg leans outward at 85° from vertical, giving the table a wide, stable stance while keeping the overall silhouette light. The geometry was fully modelled parametrically in Fusion 360, with engineering drawings generated directly from the CAD model to guide the physical build.</p>
        </div>

        <hr class="ct-divider">

        <p class="ct-section-label">Dimensions</p>
        <h2 class="ct-section-title">Key specifications</h2>
        <table class="ct-spec-table">
          <tr><td>Table length</td><td>48"</td></tr>
          <tr><td>Table width</td><td>24"</td></tr>
          <tr><td>Table height</td><td>18"</td></tr>
          <tr><td>Leg height</td><td>16"</td></tr>
          <tr><td>Leg thickness</td><td>2"</td></tr>
          <tr><td>Leg top width</td><td>8.3"</td></tr>
          <tr><td>Leg foot width</td><td>10.3"</td></tr>
          <tr><td>Inner curve radius</td><td>8" (8R)</td></tr>
          <tr><td>Leg lean angle</td><td>85° (5° off vertical)</td></tr>
          <tr><td>Top cut angle</td><td>135°</td></tr>
          <tr><td>Material</td><td>Pine (structural), butcher block top</td></tr>
        </table>

        <hr class="ct-divider">

        <p class="ct-section-label">3D Model</p>
        <h2 class="ct-section-title">Interactive assembly viewer</h2>

        <div class="ct-viewer-controls">
            <button class="ct-viewer-btn" id="ct-btn-rotate" onclick="ctToggleRotate()">Pause rotation</button>
            <button class="ct-viewer-btn" onclick="ctResetCamera()">Reset view</button>
        </div>

        <div style="margin-bottom: 0.5rem;">
            <label for="ct-explode-slider" class="ct-viewer-hint" style="display:block; margin-bottom:4px;">
            Exploded view
            </label>
            <input type="range" id="ct-explode-slider" min="0" max="100" value="0" style="width:100%; accent-color:#4a6741;">
        </div>

        <div class="ct-viewer-wrap">
          <canvas id="ct-canvas"></canvas>
          <div class="ct-viewer-loading" id="ct-loading">
            <div class="ct-spinner"></div>
            <span>Loading model…</span>
          </div>
        </div>
        <p class="ct-viewer-hint">Drag to orbit &nbsp;·&nbsp; Scroll to zoom &nbsp;·&nbsp; Shift+Scroll to explode &nbsp;·&nbsp; Right-drag to pan</p>

      </div>
    </div>

    <!-- Section 2: Materials & Tools -->
    <div class="ct-accordion-item">
      <button class="ct-accordion-trigger" aria-expanded="false" aria-controls="panel-materials" onclick="ctToggle(this,'panel-materials')">
        <span class="ct-acc-num">02</span>
        <span>
          <span class="ct-acc-title">Materials &amp; Tools</span>
          <span class="ct-acc-meta">Lumber selection, hardware, and tool list</span>
        </span>
        <svg class="ct-acc-chevron" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.75">
          <path d="M3 6l5 5 5-5"/>
        </svg>
      </button>
      <div class="ct-accordion-panel" id="panel-materials">

        <p class="ct-section-label">Lumber</p>
        <h2 class="ct-section-title">Pine structure, butcher block top</h2>
        <div class="ct-body">
          <p>The legs and apron are cut from standard pine dimensional lumber — cost-effective and widely available, with enough strength for a coffee table at this scale. The tabletop is a butcher block panel, chosen for its flat, stable surface and warm grain pattern.</p>
          <ul>
            <li><strong>Legs:</strong> 2" × 12" pine boards (4 legs, each ~17" blank)</li>
            <li><strong>Apron:</strong> 1×4 pine, pocket-hole jointed to legs</li>
            <li><strong>Top:</strong> Butcher block panel, 48" × 24"</li>
            <li><strong>Finish:</strong> Wood stain, applied by hand</li>
          </ul>
        </div>

        <hr class="ct-divider">

        <p class="ct-section-label">Tool list</p>
        <h2 class="ct-section-title">What was used to build it</h2>
        <div class="ct-step-grid">
          <div class="ct-step-card">
            <div class="ct-step-num">CUTTING</div>
            <div class="ct-step-name">Jigsaw</div>
            <div class="ct-step-desc">Primary tool for the 8R concave leg curve — the only practical hand tool for this cut.</div>
          </div>
          <div class="ct-step-card">
            <div class="ct-step-num">CUTTING</div>
            <div class="ct-step-name">Mitre saw</div>
            <div class="ct-step-desc">Angled crosscuts for the 135° top and 45° foot miter on each leg.</div>
          </div>
          <div class="ct-step-card">
            <div class="ct-step-num">CUTTING</div>
            <div class="ct-step-name">Circular saw + track</div>
            <div class="ct-step-desc">Straight rip cuts along the leg blanks for the 85° tapered sides.</div>
          </div>
          <div class="ct-step-card">
            <div class="ct-step-num">JOINERY</div>
            <div class="ct-step-name">Pocket hole jig</div>
            <div class="ct-step-desc">Kreg jig for attaching apron to legs — fast, strong, and invisible from above.</div>
          </div>
          <div class="ct-step-card">
            <div class="ct-step-num">FINISHING</div>
            <div class="ct-step-name">Electric sander</div>
            <div class="ct-step-desc">80 → 120 → 220 grit progression on all faces, curves sanded with PVC pipe wrapped in sandpaper.</div>
          </div>
          <div class="ct-step-card">
            <div class="ct-step-num">DRILLING</div>
            <div class="ct-step-name">Cordless drill</div>
            <div class="ct-step-desc">Pilot holes, pocket screws, and hardware installation.</div>
          </div>
        </div>

      </div>
    </div>

    <!-- Section 3: Build Process -->
    <div class="ct-accordion-item">
      <button class="ct-accordion-trigger" aria-expanded="false" aria-controls="panel-build" onclick="ctToggle(this,'panel-build')">
        <span class="ct-acc-num">03</span>
        <span>
          <span class="ct-acc-title">Build Process</span>
          <span class="ct-acc-meta">From blank to assembled table</span>
        </span>
        <svg class="ct-acc-chevron" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.75">
          <path d="M3 6l5 5 5-5"/>
        </svg>
      </button>
      <div class="ct-accordion-panel" id="panel-build">

        <p class="ct-section-label">Cut sequence</p>
        <h2 class="ct-section-title">Six steps, in order</h2>
        <div class="ct-step-grid">
          <div class="ct-step-card">
            <div class="ct-step-num">STEP 01</div>
            <div class="ct-step-name">Rough blank</div>
            <div class="ct-step-desc">Rip pine boards to ~12" × 17" × 2" blanks, one per leg. Slightly oversized on all faces.</div>
          </div>
          <div class="ct-step-card">
            <div class="ct-step-num">STEP 02</div>
            <div class="ct-step-name">Taper the sides</div>
            <div class="ct-step-desc">Mitre saw at 5° tilt, both long edges of the central post. Gives the leg its 85° lean along a diagonal.</div>
          </div>
          <div class="ct-step-card">
            <div class="ct-step-num">STEP 03</div>
            <div class="ct-step-name">Cut the curve</div>
            <div class="ct-step-desc">Trace the 8R profile from a 1:1 paper template. Jigsaw just outside the line, sand back to it.</div>
          </div>
          <div class="ct-step-card">
            <div class="ct-step-num">STEP 04</div>
            <div class="ct-step-name">Top angle cut</div>
            <div class="ct-step-desc">Mitre saw set to two compound angles at once — roughly 7° combined with a 5° tilt — to cut the arch's top face to the correct compound shape.</div>
          </div>
          <div class="ct-step-card">
            <div class="ct-step-num">STEP 05</div>
            <div class="ct-step-name">Foot miter</div>
            <div class="ct-step-desc">Mitre saw set perpendicular to the tangent at the top of the arch, creating a flat 90° face so a second arch can connect to it seamlessly.</div>
          </div>
          <div class="ct-step-card">
            <div class="ct-step-num">STEP 06</div>
            <div class="ct-step-name">Sand and assemble</div>
            <div class="ct-step-desc">Sand all faces 80 → 220 grit. Rather than pocket holes, each arch was fastened to a scrap block, and the scrap block fastened to the post — joining the three leg pieces into one solid corner leg.</div>
          </div>
        </div>

        <hr class="ct-divider">

        <p class="ct-section-label">Process photos</p>
        <h2 class="ct-section-title">Build in progress</h2>

        <div class="ct-photo-grid">
          <figure>
            <img src="{{ '/assets/images/Coffee-Table-Leg.jpeg' | relative_url }}" alt="Single finished leg showing curved taper profile">
            <figcaption>First leg cut — front view</figcaption>
          </figure>
          <figure>
            <img src="{{ '/assets/images/Coffee-Table-Assembly.jpeg' | relative_url }}" alt="Table upside down showing leg and apron assembly">
            <figcaption>Undercarriage assembly</figcaption>
          </figure>
          <figure>
            <img src="{{ '/assets/images/Coffee-Table-Dryfit.jpeg' | relative_url }}" alt="Tabletop dry fit with leg frames positioned">
            <figcaption>Top dry-fit</figcaption>
          </figure>
        </div>

      </div>
    </div>

    <!-- Section 4: Result -->
    <div class="ct-accordion-item">
      <button class="ct-accordion-trigger" aria-expanded="false" aria-controls="panel-result" onclick="ctToggle(this,'panel-result')">
        <span class="ct-acc-num">04</span>
        <span>
          <span class="ct-acc-title">Finished Table</span>
          <span class="ct-acc-meta">Assembled, stained, and complete</span>
        </span>
        <svg class="ct-acc-chevron" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.75">
          <path d="M3 6l5 5 5-5"/>
        </svg>
      </button>
      <div class="ct-accordion-panel" id="panel-result">

        <p class="ct-section-label">Final result</p>
        <h2 class="ct-section-title">Complete and stained</h2>
        <div class="ct-body">
          <p>The completed table was sanded to 220 grit across all surfaces before stain application. The butcher block top and pine legs take the stain differently — the top shows a tighter, more uniform grain while the legs show more character variation. The overall aesthetic reads warm and handmade without looking rough.</p>
        </div>

        <div class="ct-photo-grid">
          <figure>
            <img src="{{ '/assets/images/Coffee-Table-Bare.jpeg' | relative_url }}" alt="Completed table before staining">
            <figcaption>Assembled, pre-stain</figcaption>
          </figure>
          <figure>
            <img src="{{ '/assets/images/Coffee-Table-Finished.jpeg' | relative_url }}" alt="Completed table with stain applied">
            <figcaption>Finished with stain</figcaption>
          </figure>
        </div>

      </div>
    </div>

  </div><!-- end accordion -->

</div><!-- end ct-page -->

<!-- Three.js 3D viewer -->
<script type="importmap">
{
  "imports": {
    "three": "https://cdn.jsdelivr.net/npm/three@0.165.0/build/three.module.js",
    "three/addons/": "https://cdn.jsdelivr.net/npm/three@0.165.0/examples/jsm/"
  }
}
</script>

<script type="module">
import * as THREE from 'three';
import { OrbitControls } from 'three/addons/controls/OrbitControls.js';
import { GLTFLoader } from 'three/addons/loaders/GLTFLoader.js';
import { MeshoptDecoder } from 'three/addons/libs/meshopt_decoder.module.js';

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

const groundGeo = new THREE.PlaneGeometry(20, 20);
const groundMat = new THREE.ShadowMaterial({ opacity: 0.12 });
const ground = new THREE.Mesh(groundGeo, groundMat);
ground.rotation.x = -Math.PI / 2;
ground.position.y = -0.01;
ground.receiveShadow = true;
scene.add(ground);

const loader = new GLTFLoader();
loader.setMeshoptDecoder(MeshoptDecoder);
const modelPath = "{{ '/assets/models/Table.glb' | relative_url }}";
let autoRotate = true;
let model = null;
let defaultCamPos = camera.position.clone();
let defaultTarget = controls.target.clone();

// --- Tiered explode state ---
// Phase 1 (slider 0-50%): tabletop rises; whole legs (post + 2 arches,
// moving together as rigid units) splay outward; the arch-to-arch-to-
// tabletop scrap connectors + their screws slide out of their holes.
// Phase 2 (slider 50-100%): tabletop and table-scrap connectors HOLD their
// phase-1 position; legs continue spreading further; each arch separates
// from its middle post; leg-internal scrap connectors + their screws
// explode out.
let explodeFactor = 0;
const explodeData = []; // { mesh, base, phase1Offset, phase2Offset }

const EXPLODE_TOP = 0.4;
const EXPLODE_LEG_PHASE1 = 0.22;
const EXPLODE_LEG_PHASE2 = 0.35;
const ARCH_SEPARATION = 0.35;
const TABLE_SCRAP_HOVER = 0.2;
const LEG_SCRAP_SLIDE = 0.32;
const TABLE_SCREW_FOLLOW_SCALE = 0.95; // rides almost fully with the connector's rise
const LEG_SCREW_FOLLOW_SCALE = 0.18;   // barely peeks out of its hole
const PHASE1_END = 0.6;   // phase 1 eases out over a wider band
const PHASE2_START = 0.4; // phase 2 eases in early, overlapping phase 1's tail

function smoothstep(edge0, edge1, x) {
  const t = THREE.MathUtils.clamp((x - edge0) / (edge1 - edge0), 0, 1);
  return t * t * (3 - 2 * t);
}

function collectMeshes(node, out) {
  if (node.isMesh) out.push(node);
  node.children.forEach((c) => collectMeshes(c, out));
}

loader.load(
  modelPath,
  (gltf) => {
    model = gltf.scene;

    const box = new THREE.Box3().setFromObject(model);
    const size = box.getSize(new THREE.Vector3());
    const maxDim = Math.max(size.x, size.y, size.z);
    const scale = 1.8 / maxDim;

    model.scale.setScalar(scale);
    model.position.set(0, 0, 0);

    const box2 = new THREE.Box3().setFromObject(model);
    model.position.y -= box2.min.y;

    model.traverse((child) => {
      if (child.isMesh) {
        child.castShadow = true;
        child.receiveShadow = true;
        if (child.material) child.material.envMapIntensity = 0.4;
      }
    });

    scene.add(model);
    window.__ctModel = model; // temporary debug handle — remove later
    model.updateMatrixWorld(true);

    const modelBox = new THREE.Box3().setFromObject(model);
    const modelCenter = modelBox.getCenter(new THREE.Vector3());

    // --- Classify every mesh ---
    const allModelMeshes = [];
    collectMeshes(model, allModelMeshes);

    const topMeshes = [];
    const tableScrapMeshes = [];   // "Arch to Arch to Table Scrap"
    const legScrapMeshes = [];     // "Scrap connector"
    const middleMeshes = [];
    const rightLeanMeshes = [];
    const leftLeanMeshes = [];
    const screwMeshes = [];

    model.traverse((child) => {
      if (!child.name) return;
      if (child.name.startsWith('Tabletop')) {
        collectMeshes(child, topMeshes);
      } else if (child.name.includes('Table') && child.name.includes('Scrap')) {
        collectMeshes(child, tableScrapMeshes);
      } else if (child.name.includes('Scrap')) {
        collectMeshes(child, legScrapMeshes);
      } else if (child.name.includes('91420A')) {
        collectMeshes(child, screwMeshes);
      } else if (child.name.startsWith('Middle')) {
        collectMeshes(child, middleMeshes);
      } else if (child.name.startsWith('Right')) {
        collectMeshes(child, rightLeanMeshes);
      } else if (child.name.startsWith('Left')) {
        collectMeshes(child, leftLeanMeshes);
      }
    });

    const specialSet = new Set([
      ...topMeshes, ...tableScrapMeshes, ...legScrapMeshes, ...screwMeshes,
      ...middleMeshes, ...rightLeanMeshes, ...leftLeanMeshes,
    ]);
    const otherLegMeshes = allModelMeshes.filter((m) => !specialSet.has(m));

    const tempBox = new THREE.Box3();
    function worldCentroid(mesh) {
      tempBox.setFromObject(mesh);
      const c = new THREE.Vector3();
      tempBox.getCenter(c);
      return c;
    }

    const legLikeMeshes = [
      ...legScrapMeshes, ...middleMeshes, ...rightLeanMeshes, ...leftLeanMeshes, ...otherLegMeshes,
    ];
    const overallCenter = new THREE.Vector3();
    if (legLikeMeshes.length > 0) {
      legLikeMeshes.forEach((m) => overallCenter.add(worldCentroid(m)));
      overallCenter.divideScalar(legLikeMeshes.length);
    }

    const quadrants = [[], [], [], []];
    legLikeMeshes.forEach((mesh) => {
      const c = worldCentroid(mesh);
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
      meshes.forEach((m) => centroid.add(worldCentroid(m)));
      centroid.divideScalar(meshes.length);
      const dir = centroid.clone().sub(overallCenter);
      dir.y = 0;
      if (dir.lengthSq() < 1e-8) return new THREE.Vector3(1, 0, 0);
      return dir.normalize();
    }

    const meshQuadrantDir = new Map();
    quadrants.forEach((group) => {
      const dir = quadrantDirection(group);
      group.forEach((mesh) => meshQuadrantDir.set(mesh, dir));
    });

    function principalAxis(mesh) {
      if (!mesh.geometry.boundingBox) mesh.geometry.computeBoundingBox();
      const s = new THREE.Vector3();
      mesh.geometry.boundingBox.getSize(s);
      let axis;
      if (s.x >= s.y && s.x >= s.z) axis = new THREE.Vector3(1, 0, 0);
      else if (s.y >= s.x && s.y >= s.z) axis = new THREE.Vector3(0, 1, 0);
      else axis = new THREE.Vector3(0, 0, 1);
      axis.applyQuaternion(mesh.quaternion);
      return axis;
    }

    // Tabletop: rises in phase 1, holds in phase 2
    topMeshes.forEach((mesh) => {
      explodeData.push({
        mesh,
        phase1Offset: new THREE.Vector3(0, EXPLODE_TOP, 0),
        phase2Offset: new THREE.Vector3(0, 0, 0),
      });
    });

    // Table-scrap connectors: rise straight up in phase 1, hovering between
    // the leg tops and the tabletop. Fixed direction, no per-mesh axis guessing.
    const tableScrapRefs = [];
    tableScrapMeshes.forEach((mesh) => {
      const c = worldCentroid(mesh);
      const p1Offset = new THREE.Vector3(0, EXPLODE_TOP * TABLE_SCRAP_HOVER, 0);
      const p2Offset = new THREE.Vector3(0, 0, 0);
      explodeData.push({ mesh, phase1Offset: p1Offset.clone(), phase2Offset: p2Offset.clone() });
      tableScrapRefs.push({ c, phase1Offset: p1Offset, phase2Offset: p2Offset, isTableScrap: true });
    });

    // Leg-internal scrap connectors: stay put in phase 1, explode out+up in phase 2
    const legScrapRefs = [];
    legScrapMeshes.forEach((mesh) => {
      const c = worldCentroid(mesh);
      const outDir = meshQuadrantDir.get(mesh) || new THREE.Vector3(1, 0, 0);
      const dir = outDir.clone().add(new THREE.Vector3(0, 0.8, 0)).normalize();
      const p1Offset = new THREE.Vector3(0, 0, 0);
      const p2Offset = dir.multiplyScalar(LEG_SCRAP_SLIDE);
      explodeData.push({ mesh, phase1Offset: p1Offset.clone(), phase2Offset: p2Offset.clone() });
      legScrapRefs.push({ c, phase1Offset: p1Offset, phase2Offset: p2Offset, isTableScrap: false });
    });

    // Screws inherit their nearest connector's offset. Table-top screws ride
    // almost fully with the connector's rise (they should stay visually
    // seated in the wood as it lifts, not get left behind). Leg-internal
    // screws only peek partway out of their holes.
    const scrapRefs = [...tableScrapRefs, ...legScrapRefs];

    screwMeshes.forEach((mesh) => {
      const c = worldCentroid(mesh);
      let best = null;
      let bestDist = Infinity;
      scrapRefs.forEach((ref) => {
        const d = c.distanceToSquared(ref.c);
        if (d < bestDist) { bestDist = d; best = ref; }
      });
      const scale = best && best.isTableScrap ? TABLE_SCREW_FOLLOW_SCALE : LEG_SCREW_FOLLOW_SCALE;
      const p1Offset = best ? best.phase1Offset.clone().multiplyScalar(scale) : new THREE.Vector3();
      const p2Offset = best ? best.phase2Offset.clone().multiplyScalar(scale) : new THREE.Vector3();
      explodeData.push({ mesh, phase1Offset: p1Offset, phase2Offset: p2Offset });
    });
    explodeData.forEach((entry) => {
      entry.base = entry.mesh.position.clone();
    });

    console.log('Tabletop:', topMeshes.length, '/ expected 6');
    console.log('Table-scrap connectors:', tableScrapMeshes.length, '/ expected 24');
    console.log('Leg-scrap connectors:', legScrapMeshes.length, '/ expected 64');
    console.log('Screws:', screwMeshes.length, '/ expected 1080');
    console.log('Middle post:', middleMeshes.length, '/ expected 40');
    console.log('Right lean:', rightLeanMeshes.length, '/ expected 32');
    console.log('Left lean:', leftLeanMeshes.length, '/ expected 32');
    console.log('Uncategorized leg parts:', otherLegMeshes.length, '/ expected 0');

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

function applyExplode(factor) {
  const p1 = smoothstep(0, PHASE1_END, factor);
  const p2 = smoothstep(PHASE2_START, 1, factor);
  explodeData.forEach(({ mesh, base, phase1Offset, phase2Offset }) => {
    mesh.position.copy(base)
      .addScaledVector(phase1Offset, p1)
      .addScaledVector(phase2Offset, p2);
  });
}

wrap.addEventListener('wheel', (e) => {
  if (!e.shiftKey) return;
  e.preventDefault();
  const delta = e.deltaY !== 0 ? e.deltaY : e.deltaX;
  const step = 0.0015;
  explodeFactor = THREE.MathUtils.clamp(explodeFactor + delta * step, 0, 1);
  applyExplode(explodeFactor);
  if (explodeSlider) explodeSlider.value = Math.round(explodeFactor * 100);
}, { passive: false });

const resizeObserver = new ResizeObserver(() => {
  const w = wrap.clientWidth;
  const h = wrap.clientHeight;
  camera.aspect = w / h;
  camera.updateProjectionMatrix();
  renderer.setSize(w, h);
});
resizeObserver.observe(wrap);

function animate() {
  requestAnimationFrame(animate);
  if (autoRotate && model) {
    model.rotation.y += 0.004;
  }
  controls.update();
  renderer.render(scene, camera);
}
animate();

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
<script>
function ctToggle(btn, panelId) {
  var panel = document.getElementById(panelId);
  var isOpen = btn.getAttribute('aria-expanded') === 'true';

  document.querySelectorAll('.ct-accordion-trigger').forEach(function(b) {
    b.setAttribute('aria-expanded', 'false');
  });
  document.querySelectorAll('.ct-accordion-panel').forEach(function(p) {
    p.classList.remove('is-open');
  });

  if (!isOpen) {
    btn.setAttribute('aria-expanded', 'true');
    panel.classList.add('is-open');
  }
}
</script>