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
    height: auto;
    border-radius: 6px;
    border: 1px solid #d4dece;
    object-fit: contain;
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

  .ct-viewer-hint-top {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: #4a6741;
    letter-spacing: 0.05em;
    background: #eaf1e6;
    border: 1px solid #c0d4b8;
    border-radius: 6px;
    padding: 8px 12px;
    margin: 0 0 0.75rem;
    text-align: center;
  }

  .ct-viewer-controls-overlay {
    position: absolute;
    top: 12px;
    left: 12px;
    z-index: 5;
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .ct-viewer-controls-overlay .ct-viewer-btn {
    background: rgba(247, 249, 245, 0.9);
    backdrop-filter: blur(2px);
    box-shadow: 0 1px 4px rgba(0,0,0,0.08);
  }

  .ct-explode-overlay {
    position: absolute;
    bottom: 12px;
    left: 12px;
    right: 12px;
    z-index: 5;
    background: rgba(247, 249, 245, 0.9);
    backdrop-filter: blur(2px);
    border: 1px solid #d4dece;
    border-radius: 6px;
    padding: 8px 12px;
    box-shadow: 0 1px 4px rgba(0,0,0,0.08);
  }

  .ct-explode-overlay label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.05em;
    color: #7a8c6e;
    display: block;
    margin-bottom: 4px;
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

  <p class="ct-eyebrow">Personal Project · Summer 2026</p>
  <h1 class="ct-title">Coffee Table</h1>
  <p class="ct-subtitle">
    A handmade coffee table designed from scratch in Fusion 360 and built in pine — featuring curved tapered legs and a butcher-block-style top.
  </p>

  <div class="ct-tag-row">
    <span class="ct-tag">Fusion 360</span>
    <span class="ct-tag">Pine</span>
    <span class="ct-tag">Jigsaw</span>
    <span class="ct-tag">Circular Saw</span>
    <span class="ct-tag">Hidden Joinery</span>
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
          <span class="ct-acc-meta">Leg geometry, CAD modeling, and drawings</span>
        </span>
        <svg class="ct-acc-chevron" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.75">
          <path d="M3 6l5 5 5-5"/>
        </svg>
      </button>
      <div class="ct-accordion-panel" id="panel-design">

        <p class="ct-section-label">Concept</p>
        <h2 class="ct-section-title">Curved tapered legs, designed in Fusion 360</h2>
        <div class="ct-body">
          <p>The defining feature of the table is its leg profile — a curved inner face with an 8" radius concave sweep, tapering from a wide foot to a narrow top. Each corner leg is built from three separate pieces rather than a single blank: a fir 2×2 center post, mitered at a 5° angle from corner to corner at both the top and bottom to create a diagonal tilt, flanked by two curved pine arches attached on either side to form the finished leg.</p>
          <p>Each leg leans outward at 5° from vertical, giving the table a wide, stable stance while keeping the overall silhouette light. The geometry was fully modelled parametrically in Fusion 360, with engineering drawings generated directly from the CAD model to guide the physical build.</p>
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
          <tr><td>Top cut angle</td><td>97°</td></tr>
          <tr><td>Material</td><td>Pine (structural), butcher block top</td></tr>
        </table>

        <hr class="ct-divider">

        <p class="ct-section-label">3D Model</p>
        <h2 class="ct-section-title">Interactive assembly viewer</h2>

        <p class="ct-viewer-hint-top">Drag to orbit &nbsp;·&nbsp; Scroll to zoom &nbsp;·&nbsp; Shift+Scroll to explode &nbsp;·&nbsp; Right-drag to pan</p>

        <div class="ct-viewer-wrap">
          <canvas id="ct-canvas"></canvas>
          <div class="ct-viewer-loading" id="ct-loading">
            <div class="ct-spinner"></div>
            <span>Loading model…</span>
          </div>

          <div class="ct-viewer-controls-overlay">
            <button class="ct-viewer-btn" id="ct-btn-rotate" onclick="ctToggleRotate()">Pause rotation</button>
            <button class="ct-viewer-btn" onclick="ctResetCamera()">Reset view</button>
          </div>

          <div class="ct-explode-overlay">
            <label for="ct-explode-slider">Exploded view</label>
            <input type="range" id="ct-explode-slider" min="0" max="100" value="0" style="width:100%; accent-color:#4a6741;">
          </div>
        </div>

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
          <p>The table combines standard pine dimensional lumber with fir to balance availability, workability, and appearance. Each corner leg is assembled from three separate components: a fir center post and two curved pine arches. Rather than using visible brackets or pocket-hole joinery, the pieces are connected with concealed wood blocking fastened from the inside, creating a clean exterior while maintaining a rigid structure. The tabletop is a factory-glued pine panel manufactured in a butcher block pattern, selected for its flat, stable surface and warm grain.</p>
          <ul>
            <li><strong>Center posts:</strong> Fir dimensional lumber</li>
            <li><strong>Curved arches:</strong> Pine dimensional lumber</li>
            <li><strong>Joinery:</strong> Concealed wood blocking fastened with screws</li>
            <li><strong>Top:</strong> 48" × 24" factory-glued pine butcher block panel</li>
            <li><strong>Finish:</strong> Hand-applied wood stain</li>
          </ul>
        </div>

        <hr class="ct-divider">

        <p class="ct-section-label">Tool list</p>
        <h2 class="ct-section-title">What was used to build it</h2>
        <div class="ct-step-grid">
          <div class="ct-step-card">
            <div class="ct-step-num">CUTTING</div>
            <div class="ct-step-name">Jigsaw</div>
            <div class="ct-step-desc">Primary tool for cutting the 8R curved arch profile from 1:1 paper templates.</div>
          </div>
          <div class="ct-step-card">
            <div class="ct-step-num">CUTTING</div>
            <div class="ct-step-name">Mitre saw</div>
            <div class="ct-step-desc">Used for the 5° tapers on the fir center posts, compound top cuts, and foot miters on the curved arch pieces.</div>
          </div>
          <div class="ct-step-card">
            <div class="ct-step-num">CUTTING</div>
            <div class="ct-step-name">Circular saw + track</div>
            <div class="ct-step-desc">Straight rip cuts to prepare oversized lumber blanks before shaping.</div>
          </div>
          <div class="ct-step-card">
            <div class="ct-step-num">JOINERY</div>
            <div class="ct-step-name">Cordless drill</div>
            <div class="ct-step-desc">Used to pre-drill, countersink, and drive screws through concealed wood blocking during assembly.</div>
          </div>
          <div class="ct-step-card">
            <div class="ct-step-num">FINISHING</div>
            <div class="ct-step-name">Orbital sander</div>
            <div class="ct-step-desc">Progressive sanding from 80 → 120 → 220 grit on all surfaces. The curved profiles were shaped and refined by hand to achieve a smooth, consistent finish.</div>
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
//
// IMPORTANT: every offset stored in explodeData is expressed in MODEL-LOCAL
// space, matching baseModel (also local). This is what makes the explode
// correct at any point in the model's continuous auto-rotation — offsets
// are only ever combined with baseModel in local space, and the combined
// result is converted to world space exactly once, using the model's
// CURRENT rotation, at the end of applyExplode().
let explodeFactor = 0;
const explodeData = []; // { mesh, baseModel, phase1Offset, phase2Offset, extraOffset?, extraT0?, extraT1? } — all offsets in model-local space

const EXPLODE_TOP = 0.4;
const EXPLODE_LEG_PHASE1 = 0.22;
const EXPLODE_LEG_PHASE2 = 0.35;
const ARCH_SEPARATION = 0.18; // smaller than before — just enough to read as separate pieces
const ARCH_PHASE_T0 = 0.55; // arches only start separating once leg-splay is essentially done
const ARCH_PHASE_T1 = 1.0;
const TABLE_SCRAP_HOVER = 0.5;
const LEG_SCRAP_SLIDE = 0.32;
const SCRAP_RETRACE_DIST = 0.1; // top-leg scraps retrace part of their phase-1 outward splay during phase 2
const SCRAP_TOP_SEPARATION = 0.16; // top-leg scraps separate toward their matched arch side, mirroring the arch split
const SCRAP_CLUSTER_DIST = 0.03; // meshes closer than this (world units, post-scale) are treated as one physical scrap connector
const LEG_SCREW_FOLLOW_SCALE = 0.32;   // barely peeks out of its hole
const PHASE1_END = 0.6;   // phase 1 eases out over a wider band
const PHASE2_START = 0.4; // phase 2 eases in early, overlapping phase 1's tail
const TABLE_SCREW_PULLOUT = 0.08; // extra distance to clear the hole, along screw axis
const LEG_SCREW_PULLOUT = 0.05; // extra distance for arch-attachment screws, along screw axis

function smoothstep(edge0, edge1, x) {
  const t = THREE.MathUtils.clamp((x - edge0) / (edge1 - edge0), 0, 1);
  return t * t * (3 - 2 * t);
}

function collectMeshes(node, out) {
  if (node.isMesh) out.push(node);
  node.children.forEach((c) => collectMeshes(c, out));
}

function modelSpacePos(mesh) {
  const v = new THREE.Vector3();
  mesh.getWorldPosition(v);
  return model.worldToLocal(v);
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

    // Capture the model's rotation ONCE, synchronously, before any of the
    // classification/offset math below runs. All world-space directions
    // computed in this block get converted into local space through this
    // fixed snapshot, so the resulting local offsets are valid forever —
    // independent of how much model.rotation.y drifts afterward in animate().
    const invModelQuatAtCapture = model.quaternion.clone().invert();
    function toLocalDir(worldDir) {
      return worldDir.clone().applyQuaternion(invModelQuatAtCapture);
    }

    const modelBox = new THREE.Box3().setFromObject(model);
    const modelCenter = modelBox.getCenter(new THREE.Vector3());

    // --- Classify every mesh ---
    const allModelMeshes = [];
    collectMeshes(model, allModelMeshes);

    const topMeshes = [];
    const tableScrapMeshes = [];   // "Arch to Arch to Table Scrap"
    const legScrapMeshes = [];     // "Scrap connector"
    const legScrapGroups = [];     // meshes grouped by physical connector instance (parent node) — same pattern as rawScrewGroups
    const middleMeshes = [];
    const rightLeanMeshes = [];
    const leftLeanMeshes = [];

    const tempBox = new THREE.Box3();
    function worldCentroid(mesh) {
      tempBox.setFromObject(mesh);
      const c = new THREE.Vector3();
      tempBox.getCenter(c);
      return c;
    }

    const screwMeshes = [];
    const screwGroups = [];
    const rawScrewGroups = []; // one entry per 91420A node — later paired into real screws

    function classify(node) {
      if (!node.name) {
        node.children.forEach(classify);
        return;
      }
      if (node.name.startsWith('Tabletop')) {
        collectMeshes(node, topMeshes);
        return;
      } else if (node.name.includes('Table') && node.name.includes('Scrap')) {
        collectMeshes(node, tableScrapMeshes);
        return;
      } else if (node.name.includes('Scrap')) {
        // A single physical connector can be made of multiple submeshes.
        // Collect this node's meshes as one group (legScrapGroups) AND
        // flatten into legScrapMeshes for everywhere downstream that still
        // expects a flat list.
        const group = [];
        collectMeshes(node, group);
        legScrapMeshes.push(...group);
        legScrapGroups.push(group);
        return;
      } else if (node.name.includes('91420A')) {
        // Each 91420A node is only HALF a screw (head or shaft) — collect
        // raw here, pair them into real screws right after classify() runs.
        const group = [];
        collectMeshes(node, group);
        rawScrewGroups.push(group);
        return;
      } else if (node.name.startsWith('Middle')) {
        collectMeshes(node, middleMeshes);
        return;
      } else if (node.name.startsWith('Right')) {
        collectMeshes(node, rightLeanMeshes);
        return;
      } else if (node.name.startsWith('Left')) {
        collectMeshes(node, leftLeanMeshes);
        return;
      }
      node.children.forEach(classify);
    }
    classify(model);

    // No pairing needed — confirmed each 91420A node is already one
    // complete screw mesh (1080 nodes = 1080 screws, avg 1.00 mesh/group).
    rawScrewGroups.forEach((g) => {
      screwGroups.push(g);
      screwMeshes.push(...g);
    });

    // DIAGNOSTIC ONLY — no mutation. The previous version of this block
    // reassigned any legScrapMesh within 0.05 of a screw into that screw's
    // group, on the guess that it was a misclassified shaft. But a genuine
    // connector-block face is ALSO close to its own screw's head (that's
    // where the screw enters), so proximity alone can't distinguish
    // "this is a shaft" from "this is the block face the screw is driven
    // into" — and the console counts (32 of 64 legScrapMeshes reassigned)
    // confirm it grabbed a mix of both. Logging real names/parent
    // names/shapes here instead, so the actual rule can come from evidence.
    const legScrapNearScrew = [];
    legScrapMeshes.forEach((m) => {
      const c = worldCentroid(m);
      let nearestDist = Infinity, nearestName = '';
      screwGroups.forEach((g) => {
        g.forEach((sm) => {
          const d = c.distanceTo(worldCentroid(sm));
          if (d < nearestDist) { nearestDist = d; nearestName = sm.name; }
        });
      });
      if (nearestDist < 0.08) {
        if (!m.geometry.boundingBox) m.geometry.computeBoundingBox();
        const s = new THREE.Vector3();
        m.geometry.boundingBox.getSize(s);
        const dims = [s.x, s.y, s.z].sort((a, b) => a - b);
        legScrapNearScrew.push({
          name: m.name,
          parentName: m.parent ? m.parent.name : null,
          dist: Number(nearestDist.toFixed(4)),
          nearestScrewName: nearestName,
          bboxDims: dims.map((d) => Number(d.toFixed(4))),
          aspectRatio: Number((dims[2] / Math.max(dims[1], 1e-6)).toFixed(2)),
        });
      }
    });
    console.log('legScrapMeshes within 0.08 of a screw (candidates — inspect name/aspectRatio to tell shaft from block-face):', legScrapNearScrew);

    // Find any screw group that looks abnormal: either way too spread out
    const groups = []; // rebuild groups the same way classify() does, using window.__ctModel

    window.__ctModel.traverse((node) => {
      if (node.name && node.name.includes('91420A')) {
        const meshes = [];
        (function collect(n) { if (n.isMesh) meshes.push(n); n.children.forEach(collect); })(node);
        if (meshes.length) groups.push({ name: node.name, meshes });
      }
    });

      const stats = groups.map((g) => {
      const cs = g.meshes.map(worldCentroid);
      let maxD = 0;
      for (let i = 0; i < cs.length; i++)
        for (let j = i + 1; j < cs.length; j++)
          maxD = Math.max(maxD, cs[i].distanceTo(cs[j]));
      return { name: g.name, meshCount: g.meshes.length, spanLength: maxD };
    });

    stats.sort((a, b) => b.spanLength - a.spanLength);
    console.log('Top 10 largest-span screw groups:', stats.slice(0, 10));
    console.log('Groups with only 1 mesh:', stats.filter(s => s.meshCount === 1).length, '/ total', stats.length);

    console.log(
      'Screw groups after clustering:', screwGroups.length,
      '— avg meshes/group:', (screwMeshes.length / screwGroups.length).toFixed(2),
      '(should now be > 1.00, ideally close to 2 if every screw = head + shaft)'
    );

    const specialSet = new Set([
      ...topMeshes, ...tableScrapMeshes, ...legScrapMeshes, ...screwMeshes,
      ...middleMeshes, ...rightLeanMeshes, ...leftLeanMeshes,
    ]);
    const otherLegMeshes = allModelMeshes.filter((m) => !specialSet.has(m));

    function groupCentroid(meshes) {
      if (meshes.length === 0) return null;
      const c = new THREE.Vector3();
      meshes.forEach((m) => c.add(worldCentroid(m)));
      return c.divideScalar(meshes.length);
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

    // Tracks each individual arch instance (8 total: 4 legs × 2 arches) so
    // leg screws can look up "my arch's" splay motion and separation offset
    // directly, and so screws sharing an arch can share one pull-out axis
    // (same fix pattern as the table-screw PCA noise issue).
    const legArchGroups = []; // { meshes, legSplayPhase1, legSplayPhase2, archOffset }
    const meshToArchGroup = new Map(); // arch mesh -> its legArchGroups entry

    // Track the 2 top-of-leg scrap connectors per leg so they can ride along
    // with the whole-leg splay in phase 1, instead of waiting for phase 2
    // like the other leg-internal scraps.
    const topLegScrapMeshesSet = new Set();
    const topLegScrapSplay = new Map(); // mesh -> { phase1Offset, phase2Offset }

    // Map each leg-scrap mesh to its physical connector-instance group, so
    // "top 2 connectors per leg" selects by connector instance rather than
    // by individual submesh.
    const meshToScrapGroup = new Map();
    legScrapGroups.forEach((g) => { g.forEach((m) => meshToScrapGroup.set(m, g)); });

    // Split each leg into its 3 parts: middle post stays put as the anchor,
    // left/right arches separate away from it.
    // NOTE: dir is computed from world centroids (fine — same-instant world
    // comparison), but the resulting offset vector is converted to LOCAL
    // space via toLocalDir() before being stored, since it will be added
    // to baseModel (local) inside applyExplode().
    quadrants.forEach((group) => {
      const middleGroup = group.filter((m) => middleMeshes.includes(m));
      const rightGroup  = group.filter((m) => rightLeanMeshes.includes(m));
      const leftGroup   = group.filter((m) => leftLeanMeshes.includes(m));

      const middleC = groupCentroid(middleGroup);
      if (!middleC) return; // no middle post found for this leg, skip

      // Whole-leg splay: post + both arches slide outward together from the
      // model's overall center, confined to the X-Z plane (meshQuadrantDir
      // already has Y zeroed) — no vertical component, ever. Split across
      // phase1/phase2 so separation keeps increasing through both stages.
      const legSplayDir = meshQuadrantDir.get(group[0]) || new THREE.Vector3(1, 0, 0);
      const legSplayPhase1 = toLocalDir(legSplayDir.clone().multiplyScalar(EXPLODE_LEG_PHASE1));
      const legSplayPhase2 = toLocalDir(legSplayDir.clone().multiplyScalar(EXPLODE_LEG_PHASE2));

      // Top-of-leg scrap connectors (2 per leg, 8 total): slide out with
      // the rest of the leg during phase 1 (same whole-leg splay as the
      // middle post, X-Z plane only). During phase 2 they retrace part of
      // that outward motion and separate from each other — one heading
      // toward the right arch's side, one toward the left — mirroring how
      // the arches themselves split apart. Never any Y motion.
      //
      // Selection is done by connector INSTANCE (group), not by individual
      // submesh — a connector made of multiple submeshes now moves as one
      // rigid unit, fixing the earlier bug where only the topmost submesh
      // of each connector was selected and moved correctly.
      const legScrapMeshesInQuadrant = group.filter((m) => legScrapMeshes.includes(m));

      // Cluster leg-scrap meshes in this quadrant into physical connector
      // instances by spatial proximity (union-find on worldCentroid
      // distance), THEN classify+direction each cluster as a whole — not
      // per individual mesh. This keeps meshes belonging to the same
      // physical block moving together as one rigid unit, instead of
      // splitting apart when neighboring submeshes land on opposite sides
      // of a per-mesh arch-distance tiebreak.
      const scrapCentroids = legScrapMeshesInQuadrant.map((m) => worldCentroid(m));
      const scrapClusterParent = legScrapMeshesInQuadrant.map((_, i) => i);
      function findScrapCluster(i) {
        while (scrapClusterParent[i] !== i) {
          scrapClusterParent[i] = scrapClusterParent[scrapClusterParent[i]];
          i = scrapClusterParent[i];
        }
        return i;
      }
      for (let i = 0; i < legScrapMeshesInQuadrant.length; i++) {
        for (let j = i + 1; j < legScrapMeshesInQuadrant.length; j++) {
          if (scrapCentroids[i].distanceTo(scrapCentroids[j]) < SCRAP_CLUSTER_DIST) {
            const ri = findScrapCluster(i), rj = findScrapCluster(j);
            if (ri !== rj) scrapClusterParent[ri] = rj;
          }
        }
      }
      const scrapClusters = new Map(); // root index -> { meshes, centroids }
      legScrapMeshesInQuadrant.forEach((mesh, i) => {
        const root = findScrapCluster(i);
        if (!scrapClusters.has(root)) scrapClusters.set(root, { meshes: [], centroids: [] });
        const entry = scrapClusters.get(root);
        entry.meshes.push(mesh);
        entry.centroids.push(scrapCentroids[i]);
      });

      const rightC = rightGroup.length ? groupCentroid(rightGroup) : null;
      const leftC  = leftGroup.length ? groupCentroid(leftGroup) : null;

      scrapClusters.forEach(({ meshes, centroids }) => {
        const c = new THREE.Vector3();
        centroids.forEach((cc) => c.add(cc));
        c.divideScalar(centroids.length);

        const distRight = rightC ? c.distanceToSquared(rightC) : Infinity;
        const distLeft  = leftC ? c.distanceToSquared(leftC) : Infinity;
        if (distRight === Infinity && distLeft === Infinity) return; // no arch on this leg — leave on old fallback behavior

        // Direction from the middle post toward this CLUSTER's centroid —
        // one shared direction applied to every mesh in the cluster, so
        // the connector moves as a single rigid piece.
        const scrapDir = c.clone().sub(middleC);
        scrapDir.y = 0;
        if (scrapDir.lengthSq() < 1e-8) scrapDir.set(1, 0, 0); else scrapDir.normalize();

        const scrapPhase2 = legSplayDir.clone().multiplyScalar(-SCRAP_RETRACE_DIST)
          .add(scrapDir.clone().multiplyScalar(SCRAP_TOP_SEPARATION));

        const p1Offset = legSplayPhase1.clone();
        const p2Offset = toLocalDir(scrapPhase2);

        meshes.forEach((mesh) => {
          topLegScrapMeshesSet.add(mesh);
          topLegScrapSplay.set(mesh, { phase1Offset: p1Offset.clone(), phase2Offset: p2Offset.clone() });
          explodeData.push({ mesh, phase1Offset: p1Offset.clone(), phase2Offset: p2Offset.clone() });
        });
      });

      // Middle post: only the whole-leg splay, nothing else — no arch-style
      // offset, no Y component, so it moves straight outward on the X-Z plane.
      middleGroup.forEach((mesh) => {
        explodeData.push({ mesh, phase1Offset: legSplayPhase1.clone(), phase2Offset: legSplayPhase2.clone() });
      });

      // Arches ride along with the leg splay (phase1Offset/phase2Offset,
      // same as the middle post — no independent y-motion, no crossing
      // during the splay itself). Their OWN separation from the post is
      // deferred into extraOffset with a dedicated timing window
      // (ARCH_PHASE_T0-T1) so it only starts once the leg splay has
      // essentially finished — sequential, not simultaneous, which is
      // what stops the shorter-side arches from crossing paths mid-explode.
      if (rightGroup.length) {
        const dir = groupCentroid(rightGroup).sub(middleC);
        dir.y = 0; // flatten arch separation onto the X-Z plane
        if (dir.lengthSq() < 1e-8) dir.set(1, 0, 0); else dir.normalize();
        const archOffset = toLocalDir(dir.multiplyScalar(ARCH_SEPARATION));
        const archGroupEntry = { meshes: rightGroup, legSplayPhase1: legSplayPhase1.clone(), legSplayPhase2: legSplayPhase2.clone(), archOffset: archOffset.clone() };
        legArchGroups.push(archGroupEntry);
        rightGroup.forEach((mesh) => {
          meshToArchGroup.set(mesh, archGroupEntry);
          explodeData.push({
            mesh,
            phase1Offset: legSplayPhase1.clone(),
            phase2Offset: legSplayPhase2.clone(),
            extraOffset: archOffset.clone(),
            extraT0: ARCH_PHASE_T0,
            extraT1: ARCH_PHASE_T1,
          });
        });
      }

      if (leftGroup.length) {
        const dir = groupCentroid(leftGroup).sub(middleC);
        dir.y = 0; // flatten arch separation onto the X-Z plane
        if (dir.lengthSq() < 1e-8) dir.set(-1, 0, 0); else dir.normalize();
        const archOffset = toLocalDir(dir.multiplyScalar(ARCH_SEPARATION));
        const archGroupEntry = { meshes: leftGroup, legSplayPhase1: legSplayPhase1.clone(), legSplayPhase2: legSplayPhase2.clone(), archOffset: archOffset.clone() };
        legArchGroups.push(archGroupEntry);
        leftGroup.forEach((mesh) => {
          meshToArchGroup.set(mesh, archGroupEntry);
          explodeData.push({
            mesh,
            phase1Offset: legSplayPhase1.clone(),
            phase2Offset: legSplayPhase2.clone(),
            extraOffset: archOffset.clone(),
            extraT0: ARCH_PHASE_T0,
            extraT1: ARCH_PHASE_T1,
          });
        });
      }
    });

    function principalAxisWorld(mesh) {
      if (!mesh.geometry.boundingBox) mesh.geometry.computeBoundingBox();
      const s = new THREE.Vector3();
      mesh.geometry.boundingBox.getSize(s);
      let axis;
      if (s.x >= s.y && s.x >= s.z) axis = new THREE.Vector3(1, 0, 0);
      else if (s.y >= s.x && s.y >= s.z) axis = new THREE.Vector3(0, 1, 0);
      else axis = new THREE.Vector3(0, 0, 1);
      const worldQuat = new THREE.Quaternion();
      mesh.getWorldQuaternion(worldQuat);
      axis.applyQuaternion(worldQuat);
      return axis;
    }
    function screwAxisFromGroup(group) {
      if (group.length < 2) return principalAxisWorld(group[0]); // lone mesh fallback
      const centroids = group.map((m) => worldCentroid(m));
      let maxDistSq = -1, a = 0, b = 1;
      for (let i = 0; i < centroids.length; i++) {
        for (let j = i + 1; j < centroids.length; j++) {
          const d = centroids[i].distanceToSquared(centroids[j]);
          if (d > maxDistSq) { maxDistSq = d; a = i; b = j; }
        }
      }
      const axis = centroids[b].clone().sub(centroids[a]);
      if (axis.lengthSq() < 1e-10) return principalAxisWorld(group[0]);
      return axis.normalize();
    }

    function screwAxisFromVertices(mesh) {
      const posAttr = mesh.geometry.attributes.position;
      const n = posAttr.count;
      const v = new THREE.Vector3();
      const centroid = new THREE.Vector3();
      for (let i = 0; i < n; i++) {
        v.fromBufferAttribute(posAttr, i).applyMatrix4(mesh.matrixWorld);
        centroid.add(v);
      }
      centroid.divideScalar(n);

      let xx = 0, xy = 0, xz = 0, yy = 0, yz = 0, zz = 0;
      for (let i = 0; i < n; i++) {
        v.fromBufferAttribute(posAttr, i).applyMatrix4(mesh.matrixWorld).sub(centroid);
        xx += v.x * v.x; xy += v.x * v.y; xz += v.x * v.z;
        yy += v.y * v.y; yz += v.y * v.z; zz += v.z * v.z;
      }

      // Power iteration to find the dominant eigenvector of the covariance
      // matrix — for a thin rod shape, this IS the shaft's true long axis,
      // computed directly from real geometry, independent of node rotation.
      let axis = new THREE.Vector3(1, 1, 1).normalize();
      for (let iter = 0; iter < 25; iter++) {
        const nx = xx * axis.x + xy * axis.y + xz * axis.z;
        const ny = xy * axis.x + yy * axis.y + yz * axis.z;
        const nz = xz * axis.x + yz * axis.y + zz * axis.z;
        axis.set(nx, ny, nz);
        if (axis.lengthSq() < 1e-20) return principalAxisWorld(mesh); // degenerate fallback
        axis.normalize();
      }
      return axis;
    }

    // Combined-PCA helper: accumulates covariance from ONE mesh's world-space
    // vertices, centered on that mesh's own centroid, into a shared accumulator.
    // Centering per-mesh before combining is what lets shaft signal reinforce
    // across screws while each screw's own head asymmetry (the actual noise
    // source) washes out in the aggregate instead of steering the result.
    function centeredCovarianceFromMesh(mesh, accum) {
      const posAttr = mesh.geometry.attributes.position;
      const n = posAttr.count;
      const v = new THREE.Vector3();
      const centroid = new THREE.Vector3();
      for (let i = 0; i < n; i++) {
        v.fromBufferAttribute(posAttr, i).applyMatrix4(mesh.matrixWorld);
        centroid.add(v);
      }
      centroid.divideScalar(n);
      for (let i = 0; i < n; i++) {
        v.fromBufferAttribute(posAttr, i).applyMatrix4(mesh.matrixWorld).sub(centroid);
        accum.xx += v.x * v.x; accum.xy += v.x * v.y; accum.xz += v.x * v.z;
        accum.yy += v.y * v.y; accum.yz += v.y * v.z; accum.zz += v.z * v.z;
      }
    }

    // One shared shaft axis for ALL screws on a given connector — computed
    // from their combined, per-screw-centered vertex clouds. This is the
    // actual fix: instead of each screw voting on its own noisy axis, every
    // screw on the same connector pulls out along the identical direction.
    function computeSharedShaftAxis(groups) {
      const accum = { xx: 0, xy: 0, xz: 0, yy: 0, yz: 0, zz: 0 };
      groups.forEach((group) => {
        const shaftMesh = pickShaftMesh(group);
        centeredCovarianceFromMesh(shaftMesh, accum);
      });

      let axis = new THREE.Vector3(1, 1, 1).normalize();
      for (let iter = 0; iter < 25; iter++) {
        const nx = accum.xx * axis.x + accum.xy * axis.y + accum.xz * axis.z;
        const ny = accum.xy * axis.x + accum.yy * axis.y + accum.yz * axis.z;
        const nz = accum.xz * axis.x + accum.yz * axis.y + accum.zz * axis.z;
        axis.set(nx, ny, nz);
        if (axis.lengthSq() < 1e-20) return null; // degenerate — caller should skip
        axis.normalize();
      }
      return axis;
    }

    // Picks the most rod-like submesh in a screw group (highest long/mid
    // bounding-box aspect ratio) to derive the axis from — a head, washer,
    // or Phillips-cross shape has no reliable long axis, but the shaft does.
    function pickShaftMesh(group) {
      let best = group[0], bestRatio = -Infinity;
      group.forEach((m) => {
        if (!m.geometry.boundingBox) m.geometry.computeBoundingBox();
        const s = new THREE.Vector3();
        m.geometry.boundingBox.getSize(s);
        const dims = [s.x, s.y, s.z].sort((a, b) => a - b);
        const ratio = dims[2] / Math.max(dims[1], 1e-6);
        if (ratio > bestRatio) { bestRatio = ratio; best = m; }
      });
      return best;
    }

    // Determines whether a screw (by its world centroid) sits nearest an
    // arch mesh or a middle-post mesh — used to identify which leg screws
    // are fastening into an arch's bottom hole (as opposed to fastening a
    // scrap block into the post). Returns the SPECIFIC arch instance
    // (legArchGroups entry) it belongs to, or null if it's nearest the post.
    function nearestLegPart(centroid) {
      let bestDist = Infinity, bestMesh = null;
      const consider = (arr) => {
        arr.forEach((m) => {
          const d = centroid.distanceToSquared(worldCentroid(m));
          if (d < bestDist) { bestDist = d; bestMesh = m; }
        });
      };
      consider(rightLeanMeshes);
      consider(leftLeanMeshes);
      consider(middleMeshes);
      if (!bestMesh) return null;
      return meshToArchGroup.get(bestMesh) || null; // null = nearest the post
    }

    // Tabletop: rises in phase 1, holds in phase 2.
    // (0, EXPLODE_TOP, 0) is invariant under Y-rotation, but we still run it
    // through toLocalDir for consistency — it's a no-op here, and it means
    // this code stays correct if the model is ever rotated on other axes.
    topMeshes.forEach((mesh) => {
      explodeData.push({
        mesh,
        phase1Offset: toLocalDir(new THREE.Vector3(0, EXPLODE_TOP, 0)),
        phase2Offset: new THREE.Vector3(0, 0, 0),
      });
    });

    // Table-scrap connectors: rise straight up in phase 1, hovering between
    // the leg tops and the tabletop. Stored offsets are LOCAL from here on,
    // so anything that inherits from a scrapRef below is already local too.
    const tableScrapRefs = [];
    tableScrapMeshes.forEach((mesh) => {
      const c = worldCentroid(mesh);
      const p1Offset = toLocalDir(new THREE.Vector3(0, EXPLODE_TOP * TABLE_SCRAP_HOVER, 0));
      const p2Offset = new THREE.Vector3(0, 0, 0);
      explodeData.push({ mesh, phase1Offset: p1Offset.clone(), phase2Offset: p2Offset.clone() });
      tableScrapRefs.push({ c, phase1Offset: p1Offset, phase2Offset: p2Offset, isTableScrap: true });
    });

    // Leg-internal scrap connectors: stay put in phase 1, explode out+up in phase 2
    const legScrapRefs = [];
    legScrapMeshes.forEach((mesh) => {
      const c = worldCentroid(mesh);

      if (topLegScrapMeshesSet.has(mesh)) {
        // Already pushed to explodeData in the quadrants loop with the
        // leg-splay motion — just register it here for screw lookup.
        const splay = topLegScrapSplay.get(mesh);
        legScrapRefs.push({ c, phase1Offset: splay.phase1Offset, phase2Offset: splay.phase2Offset, isTableScrap: false });
        return;
      }

      const outDir = meshQuadrantDir.get(mesh) || new THREE.Vector3(1, 0, 0);
      const dir = outDir.clone().add(new THREE.Vector3(0, 0.8, 0)).normalize();
      const p1Offset = new THREE.Vector3(0, 0, 0);
      const p2Offset = toLocalDir(dir.multiplyScalar(LEG_SCRAP_SLIDE));
      explodeData.push({ mesh, phase1Offset: p1Offset.clone(), phase2Offset: p2Offset.clone() });
      legScrapRefs.push({ c, phase1Offset: p1Offset, phase2Offset: p2Offset, isTableScrap: false });
    });

    // Screws inherit their nearest connector's offset. Table-top screws ride
    // almost fully with the connector's rise (they should stay visually
    // seated in the wood as it lifts, not get left behind). Leg-internal
    // screws only peek partway out of their holes.
    const scrapRefs = [...tableScrapRefs, ...legScrapRefs];

    // Group screws by their nearest connector
    const screwsByConnector = new Map(); // connectorRef -> screwGroups[]
    const screwInfo = new Map();          // screwGroup -> { best, c }
    const screwArchMatch = new Map();     // screwGroup -> legArchGroups entry (or null)
    const screwsByArch = new Map();       // legArchGroups entry -> screwGroups[]

    screwGroups.forEach((group) => {
      if (group.length === 0) return;
      const c = new THREE.Vector3();
      group.forEach((m) => c.add(worldCentroid(m)));
      c.divideScalar(group.length);

      let best = null;
      let bestDist = Infinity;
      scrapRefs.forEach((ref) => {
        const d = c.distanceToSquared(ref.c);
        if (d < bestDist) { bestDist = d; best = ref; }
      });
      
      screwInfo.set(group, { best, c });
      if (best) {
        if (!screwsByConnector.has(best)) screwsByConnector.set(best, []);
        screwsByConnector.get(best).push(group);
      }

      const archMatch = nearestLegPart(c);
      screwArchMatch.set(group, archMatch);
      if (archMatch) {
        if (!screwsByArch.has(archMatch)) screwsByArch.set(archMatch, []);
        screwsByArch.get(archMatch).push(group);
      }
    });

    // One shared pull-out axis per table-scrap connector, not per screw.
    // Sign is resolved once too, from the AVERAGE screw position relative
    // to the connector — a much steadier signal than any single screw's
    // short, easily-flipped dirToScrew vector.
    const connectorAxis = new Map(); // connectorRef -> world-space unit axis
    screwsByConnector.forEach((groups, connector) => {
      if (!connector.isTableScrap) return; // leg screws don't use an explicit axis
      const axis = computeSharedShaftAxis(groups);
      if (!axis) return;

      const avgScrewCentroid = new THREE.Vector3();
      groups.forEach((group) => {
        const gc = new THREE.Vector3();
        group.forEach((m) => gc.add(worldCentroid(m)));
        gc.divideScalar(group.length);
        avgScrewCentroid.add(gc);
      });
      avgScrewCentroid.divideScalar(groups.length);

      const dirToScrews = avgScrewCentroid.clone().sub(connector.c);
      if (dirToScrews.lengthSq() > 1e-10 && axis.dot(dirToScrews) < 0) axis.negate();

      connectorAxis.set(connector, axis);
    });

    // Same shared-axis fix, applied per individual arch: every screw
    // fastened into a given arch's bottom hole pulls out along one common
    // direction instead of each voting on its own noisy per-screw PCA axis.
    const archAxis = new Map(); // legArchGroups entry -> world-space unit axis
    screwsByArch.forEach((groups, archGroupEntry) => {
      const axis = computeSharedShaftAxis(groups);
      if (!axis) return;

      const archCentroid = groupCentroid(archGroupEntry.meshes);
      const avgScrewCentroid = new THREE.Vector3();
      groups.forEach((group) => {
        const gc = new THREE.Vector3();
        group.forEach((m) => gc.add(worldCentroid(m)));
        gc.divideScalar(group.length);
        avgScrewCentroid.add(gc);
      });
      avgScrewCentroid.divideScalar(groups.length);

      const dirToScrews = avgScrewCentroid.clone().sub(archCentroid);
      if (dirToScrews.lengthSq() > 1e-10 && axis.dot(dirToScrews) < 0) axis.negate();

      archAxis.set(archGroupEntry, axis);
    });

    screwGroups.forEach((group) => {
      if (group.length === 0) return;
      const { best, c } = screwInfo.get(group) || {};

      let p1Offset, p2Offset;
      let extraOffset = null;
      let extraT0, extraT1;

      if (best && best.isTableScrap) {
        // best.phase1Offset is already local (converted when tableScrapRefs
        // were built), so it can be reused directly.
        p1Offset = best.phase1Offset.clone();
        p2Offset = new THREE.Vector3();

        // Shared axis for this connector — same direction for every screw
        // on it, computed once in the connectorAxis pass above instead of
        // per-screw. Removes the per-screw PCA noise that was causing
        // scattered, non-parallel pull-out directions.
        const axis = connectorAxis.get(best);
        if (axis) {
          extraOffset = toLocalDir(axis.clone().multiplyScalar(TABLE_SCREW_PULLOUT));
          extraT0 = PHASE1_END;
          extraT1 = Math.min(PHASE1_END + 0.25, 1.0);
        }
      } else if (best) {
        const archMatch = screwArchMatch.get(group);

        if (archMatch) {
          // Arch-attachment screw: inherit the SAME whole-leg splay motion
          // as its arch (phase1Offset/phase2Offset) — this is what makes it
          // move on the X-Z plane during phase 1 instead of sitting still
          // (previously it only inherited the scrap connector's own offset,
          // which is zero in phase 1).
          p1Offset = archMatch.legSplayPhase1.clone();
          p2Offset = archMatch.legSplayPhase2.clone();

          // Shared per-arch axis (computed once above, not per screw) plus
          // the arch's own separation offset — both timed to the same
          // ARCH_PHASE_T0-T1 window the arch itself separates in, so the
          // screw slides free exactly as its arch pulls away, in a single
          // clean direction shared by every screw on that arch.
          extraOffset = archMatch.archOffset.clone();
          const axis = archAxis.get(archMatch);
          if (axis) {
            extraOffset.add(toLocalDir(axis.clone().multiplyScalar(LEG_SCREW_PULLOUT)));
          }
          extraT0 = ARCH_PHASE_T0;
          extraT1 = ARCH_PHASE_T1;
        } else {
          // Post-attachment screw (fastens a scrap block into the middle
          // post) — unchanged, follows its connector's own offset.
          p1Offset = best.phase1Offset.clone().multiplyScalar(LEG_SCREW_FOLLOW_SCALE);
          p2Offset = best.phase2Offset.clone().multiplyScalar(LEG_SCREW_FOLLOW_SCALE);
        }
      } else {
        p1Offset = new THREE.Vector3();
        p2Offset = new THREE.Vector3();
      }

      group.forEach((mesh) => {
        const entry = { mesh, phase1Offset: p1Offset.clone(), phase2Offset: p2Offset.clone() };
        if (extraOffset) {
          entry.extraOffset = extraOffset.clone();
          entry.extraT0 = extraT0;
          entry.extraT1 = extraT1;
        }
        explodeData.push(entry);
      });
    });

    // Stamp rest position in MODEL space (not local .position). This is
    // what makes multi-submesh parts — like a screw's separate head/shaft
    // meshes — move as one rigid piece even when siblings have different
    // local rotations baked in from the export.
    explodeData.forEach((entry) => {
      entry.baseModel = modelSpacePos(entry.mesh);
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

// All offsets (phase1Offset, phase2Offset, extraOffset) are in MODEL-LOCAL
// space, matching baseModel. They're summed entirely in local space, and
// converted to world space exactly once via model.localToWorld — so this
// stays correct at any rotation angle, including while auto-rotating.
function applyExplode(factor) {
  const p1 = smoothstep(0, PHASE1_END, factor);
  const p2 = smoothstep(PHASE2_START, 1, factor);
  const targetModel = new THREE.Vector3();
  const targetWorld = new THREE.Vector3();
  const targetLocal = new THREE.Vector3();
  explodeData.forEach(({ mesh, baseModel, phase1Offset, phase2Offset, extraOffset, extraT0, extraT1 }) => {
    targetModel.copy(baseModel)
      .addScaledVector(phase1Offset, p1)
      .addScaledVector(phase2Offset, p2);
    if (extraOffset) {
      const pExtra = smoothstep(extraT0, extraT1, factor);
      targetModel.addScaledVector(extraOffset, pExtra);
    }
    targetWorld.copy(targetModel);
    model.localToWorld(targetWorld);
    targetLocal.copy(targetWorld);
    if (mesh.parent) mesh.parent.worldToLocal(targetLocal);
    mesh.position.copy(targetLocal);
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