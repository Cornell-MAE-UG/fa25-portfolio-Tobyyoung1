---
layout: project
title: SLF Density Separator
description: Design and Optimization Problem — MAE2250
---

<style>
  @import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Mono:wght@400;500&family=Instrument+Sans:wght@400;500;600&display=swap');

  main.container {
    max-width: 100% !important;
    padding-left: 4rem !important;
    padding-right: 4rem !important;
  }

  .slf-page {
    font-family: 'Instrument Sans', sans-serif;
    max-width: 100%;
    width: 100%;
    margin: 0;
    padding: 2rem 0 4rem;
    color: #1a1a18;
    box-sizing: border-box;
  }

  .slf-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: #7a8c6e;
    margin: 0 0 0.5rem;
  }

  .slf-title {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(2rem, 5vw, 3rem);
    font-weight: 400;
    line-height: 1.1;
    color: #1a1a18;
    margin: 0 0 0.75rem;
  }

  .slf-subtitle {
    font-size: 17px;
    color: #5a6652;
    margin: 0 0 1.75rem;
    line-height: 1.5;
    max-width: 560px;
  }

  .slf-context-link {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-family: 'DM Mono', monospace;
    font-size: 11.5px;
    letter-spacing: 0.05em;
    color: #4a6741;
    border: 1px solid #b8c9b0;
    border-radius: 4px;
    padding: 6px 12px;
    text-decoration: none;
    margin-bottom: 2rem;
    transition: background 0.15s, border-color 0.15s;
  }

  .slf-context-link:hover {
    background: #f0f5ee;
    border-color: #8aab7e;
  }

  .slf-context-link svg {
    width: 13px;
    height: 13px;
    opacity: 0.7;
  }

  .slf-toc-label {
    font-family: 'DM Mono', monospace;
    font-size: 10.5px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: #9aaa8e;
    margin-bottom: 0.5rem;
  }

  .slf-accordion {
    border: 1px solid #d4dece;
    border-radius: 8px;
    overflow: hidden;
    margin-bottom: 3rem;
  }

  .slf-accordion-item {
    border-bottom: 1px solid #d4dece;
  }

  .slf-accordion-item:last-child {
    border-bottom: none;
  }

  .slf-accordion-trigger {
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

  .slf-accordion-trigger:hover { background: #eff3ec; }
  .slf-accordion-trigger[aria-expanded="true"] { background: #eaf1e6; }

  .slf-acc-num {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: #9aaa8e;
    letter-spacing: 0.05em;
  }

  .slf-acc-title {
    font-size: 14px;
    font-weight: 600;
    color: #2a3328;
    line-height: 1.3;
  }

  .slf-acc-meta {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: #a0af94;
    letter-spacing: 0.04em;
    display: block;
    font-weight: 400;
  }

  .slf-acc-chevron {
    width: 16px;
    height: 16px;
    color: #7a8c6e;
    transition: transform 0.25s ease;
    flex-shrink: 0;
  }

  .slf-accordion-trigger[aria-expanded="true"] .slf-acc-chevron {
    transform: rotate(180deg);
  }

  .slf-accordion-panel {
    display: none;
    padding: 1.5rem 1.5rem 1.75rem;
    background: #fff;
    border-top: 1px solid #e4ede0;
  }

  .slf-accordion-panel.is-open { display: block; }

  .slf-section-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: #7a8c6e;
    margin: 0 0 0.35rem;
  }

  .slf-section-title {
    font-family: 'DM Serif Display', serif;
    font-size: 1.4rem;
    font-weight: 400;
    color: #1a1a18;
    margin: 0 0 1rem;
    line-height: 1.2;
  }

  .slf-body {
    font-size: 16px;
    line-height: 1.75;
    color: #2e3830;
  }

  .slf-body p { margin: 0 0 0.9rem; }

  .slf-body ul, .slf-body ol {
    margin: 0 0 0.9rem;
    padding-left: 1.4rem;
  }

  .slf-body li { margin-bottom: 0.35rem; }

  .slf-body strong {
    font-weight: 600;
    color: #1a1a18;
  }

  .slf-divider {
    border: none;
    border-top: 1px solid #e2ece0;
    margin: 1.5rem 0;
  }

  .slf-step-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 0.75rem;
    margin: 1rem 0 1.25rem;
  }

  .slf-step-card {
    background: #f7f9f5;
    border: 1px solid #d4dece;
    border-radius: 6px;
    padding: 0.85rem 1rem;
  }

  .slf-step-num {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: #7a8c6e;
    letter-spacing: 0.1em;
    margin-bottom: 0.25rem;
  }

  .slf-step-name {
    font-size: 15px;
    font-weight: 600;
    color: #2a3328;
    margin-bottom: 0.3rem;
  }

  .slf-step-desc {
    font-size: 14px;
    color: #5a6a54;
    line-height: 1.5;
  }

  .slf-test-block {
    background: #f7f9f5;
    border-left: 3px solid #8aab7e;
    border-radius: 0 6px 6px 0;
    padding: 0.85rem 1.1rem;
    margin: 0.75rem 0;
  }

  .slf-test-title {
    font-size: 15px;
    font-weight: 600;
    color: #2a3328;
    margin-bottom: 0.3rem;
  }

  .slf-test-body {
    font-size: 17px;
    color: #3e4e38;
    line-height: 1.6;
  }

  .slf-test-fix {
    font-family: 'DM Mono', monospace;
    font-size: 11.5px;
    color: #4a6741;
    margin-top: 0.4rem;
  }

  .slf-quote-block {
    border-left: 3px solid #b8c9b0;
    padding: 0.6rem 1.1rem;
    margin: 1rem 0;
    font-style: italic;
    color: #4a5a44;
    font-size: 18px;
    line-height: 1.65;
  }

  .slf-quote-attr {
    font-style: normal;
    font-size: 12px;
    font-family: 'DM Mono', monospace;
    color: #7a8c6e;
    margin-top: 0.4rem;
    display: block;
  }

  .slf-score-banner {
    display: flex;
    align-items: center;
    gap: 1rem;
    background: #f0f5ee;
    border: 1px solid #c8d8c2;
    border-radius: 6px;
    padding: 0.9rem 1.25rem;
    margin-bottom: 1.5rem;
  }

  .slf-score-num {
    font-family: 'DM Serif Display', serif;
    font-size: 2rem;
    color: #4a6741;
    line-height: 1;
  }

  .slf-score-detail {
    font-size: 16px;
    color: #5a6a54;
    line-height: 1.4;
  }

  .slf-score-detail strong { color: #2a3328; }

  .slf-tag-row {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-bottom: 1rem;
  }

  .slf-tag {
    font-family: 'DM Mono', monospace;
    font-size: 10.5px;
    letter-spacing: 0.04em;
    background: #eaf1e6;
    color: #4a6741;
    border: 1px solid #c0d4b8;
    border-radius: 3px;
    padding: 3px 8px;
  }

  .slf-next-list {
    list-style: none;
    padding: 0;
    margin: 0.75rem 0;
  }

  .slf-next-list li {
    display: flex;
    gap: 0.75rem;
    align-items: flex-start;
    font-size: 18px;
    color: #2e3830;
    line-height: 1.6;
    padding: 0.5rem 0;
    border-bottom: 1px solid #e8f0e4;
  }

  .slf-next-list li:last-child { border-bottom: none; }

  .slf-next-dot {
    width: 6px;
    height: 6px;
    background: #8aab7e;
    border-radius: 50%;
    margin-top: 0.55rem;
    flex-shrink: 0;
  }

  /* ── Client Pitch Cards ── */
  .slf-pitch-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }

  .slf-pitch-card {
    background: #f7f9f5;
    border: 1px solid #d4dece;
    border-radius: 8px;
    padding: 1.25rem 1.4rem 1.4rem;
  }

  .slf-pitch-card--full { grid-column: 1 / -1; }

  .slf-pitch-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: #7a8c6e;
    margin-bottom: 0.35rem;
  }

  .slf-pitch-heading {
    font-family: 'DM Serif Display', serif;
    font-size: 1.15rem;
    font-weight: 400;
    color: #1a1a18;
    line-height: 1.25;
    margin-bottom: 0.85rem;
  }

  .slf-pitch-body {
    font-size: 14px;
    color: #2e3830;
    line-height: 1.7;
  }

  .slf-pitch-body p { margin: 0 0 0.75rem; }

  .slf-pitch-body strong {
    font-weight: 600;
    color: #1a1a18;
  }

  .slf-pitch-list {
    margin: 0;
    padding-left: 1.25rem;
  }

  .slf-pitch-list li { margin-bottom: 0.4rem; }

  .slf-pitch-stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 0.75rem;
    margin: 0.75rem 0;
  }

  .slf-pitch-stat {
    background: #fff;
    border: 1px solid #d4dece;
    border-radius: 6px;
    padding: 0.75rem 1rem;
    text-align: center;
  }

  .slf-pitch-stat-num {
    font-family: 'DM Serif Display', serif;
    font-size: 1.6rem;
    color: #4a6741;
    line-height: 1;
    margin-bottom: 0.3rem;
  }

  .slf-pitch-stat-label {
    font-size: 11.5px;
    color: #7a8c6e;
    line-height: 1.4;
  }

  /* ── Prototype media grid ── */
  .slf-media-label {
    font-family: 'DM Mono', monospace;
    font-size: 10.5px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: #7a8c6e;
    margin: 0 0 0.5rem;
  }

  .slf-media-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 1.25rem;
    margin-bottom: 0.5rem;
  }

  .slf-media-grid > div {
    display: flex;
    flex-direction: column;
  }

  .slf-media-grid img,
  .slf-media-grid video {
    width: 100%;
    flex: 1;
    border-radius: 6px;
    border: 1px solid #d4dece;
    display: block;
    /* Keep consistent height across all three */
    aspect-ratio: 4 / 3;
    object-fit: cover;
    background: #1a1a18;
  }

  .slf-media-grid video {
    background: #f0f5ee;
  }

  @media (max-width: 640px) {
    .slf-pitch-grid { grid-template-columns: 1fr; }
    .slf-pitch-stats { grid-template-columns: 1fr; }
    .slf-media-grid { grid-template-columns: 1fr; }
  }
</style>

<div class="slf-page">

  <p class="slf-eyebrow">MAE2250 · Team LanternBye</p>
  <h1 class="slf-title">SLF Density Separator</h1>
  <p class="slf-subtitle">
    A sugar water–based separation system that removes Spotted Lanternfly from mechanically harvested grapes at the point of collection.
  </p>

  <a class="slf-context-link" href="#">
    <svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5">
      <path d="M3 8h10M9 4l4 4-4 4"/>
    </svg>
    MAE2250 Overall Project
  </a>

  <p class="slf-toc-label">Milestones</p>
  <div class="slf-accordion" role="list">

    <!-- Milestone 1: Client Pitch -->
    <div class="slf-accordion-item">
      <button class="slf-accordion-trigger" aria-expanded="false" aria-controls="panel-pitch" onclick="togglePanel(this, 'panel-pitch')">
        <span class="slf-acc-num">O3</span>
        <span>
          <span class="slf-acc-title">Client Pitch</span>
          <span class="slf-acc-meta">Initial concept presentation to vineyard client</span>
        </span>
        <svg class="slf-acc-chevron" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.75">
          <path d="M3 6l5 5 5-5"/>
        </svg>
      </button>
      <div class="slf-accordion-panel" id="panel-pitch" role="region">
        <div class="slf-pitch-grid">

          <div class="slf-pitch-card slf-pitch-card--full">
            <div class="slf-pitch-label">01 — Problem Overview</div>
            <div class="slf-pitch-heading">Spotted Lanternfly is degrading vineyard harvests across the U.S.</div>
            <div class="slf-pitch-body">
              <p>Over the past decade, SLF infestations have spread rapidly through major wine-producing regions, threatening both grape quality and harvest volume. During mechanical harvesting, the shaker arm dislodges grapes and SLF simultaneously — mixing an invasive pest directly into the collection stream.</p>
              <div class="slf-pitch-stats">
                <div class="slf-pitch-stat">
                  <div class="slf-pitch-stat-num">19+</div>
                  <div class="slf-pitch-stat-label">U.S. states with confirmed SLF populations (USDA APHIS, 2024)</div>
                </div>
                <div class="slf-pitch-stat">
                  <div class="slf-pitch-stat-num">$554M</div>
                  <div class="slf-pitch-stat-label">Worst-case annual economic loss estimate for Pennsylvania alone (Penn State, 2020)</div>
                </div>
                <div class="slf-pitch-stat">
                  <div class="slf-pitch-stat-num">1,400</div>
                  <div class="slf-pitch-stat-label">Vineyards at risk in New York State alone, generating $6.65B in economic activity</div>
                </div>
              </div>
            </div>
          </div>

          <div class="slf-pitch-card">
            <div class="slf-pitch-label">02 — Focused Sub-Problem</div>
            <div class="slf-pitch-heading">The harvest moment</div>
            <div class="slf-pitch-body">
              <p>We narrowed our focus to the window immediately after the mechanical shaker — before grapes reach the collection bin. This is the highest-leverage intervention point: SLF and grapes are mixed but not yet processed, and separation is still physically possible.</p>
              <ul class="slf-pitch-list">
                <li>Existing solutions focus on field-level SLF control, not harvest contamination</li>
                <li>No current in-line separation method exists for mechanical harvesters</li>
                <li>Contamination at this stage affects the entire downstream batch</li>
              </ul>
            </div>
          </div>

          <div class="slf-pitch-card">
            <div class="slf-pitch-label">03 — Proposed Solution</div>
            <div class="slf-pitch-heading">Density separation in sugar water</div>
            <div class="slf-pitch-body">
              <p>Grapes sink in sugar water; SLF float. Our system mounts directly beneath the harvester's internal shaker and exploits this density difference to automatically separate the two.</p>
              <ul class="slf-pitch-list">
                <li><strong>Separation tank</strong> — sugar water stream; grapes sink, SLF float</li>
                <li><strong>Water wheel</strong> — rotating fins skim SLF off the surface</li>
                <li><strong>Strainer tank</strong> — separates grapes from liquid</li>
                <li><strong>Recirculating pump</strong> — one batch of sugar water per run</li>
              </ul>
            </div>
          </div>

          <div class="slf-pitch-card">
            <div class="slf-pitch-label">04 — Technical Feasibility</div>
            <div class="slf-pitch-heading">Why this approach works</div>
            <div class="slf-pitch-body">
              <p>The design is grounded in a straightforward physical principle with no exotic materials or power requirements beyond a small recirculating pump.</p>
              <ul class="slf-pitch-list">
                <li><strong>Density difference</strong> — SLF and grapes have measurably different densities, enabling reliable separation in solution</li>
                <li><strong>Sugar water</strong> — chosen over plain water to match grape Brix levels, minimizing osmotic sugar loss during the brief submersion</li>
                <li><strong>Short contact time</strong> — grapes pass through quickly, limiting any quality impact</li>
                <li><strong>Self-contained</strong> — closed-loop recirculation means no ongoing water supply needed in the field</li>
              </ul>
            </div>
          </div>

          <div class="slf-pitch-card slf-pitch-card--full">
            <div class="slf-pitch-label">05 — Cost &amp; Implementation</div>
            <div class="slf-pitch-heading">Low materials cost, retrofittable design</div>
            <div class="slf-pitch-body">
              <div class="slf-pitch-stats">
                <div class="slf-pitch-stat">
                  <div class="slf-pitch-stat-num">[$ __]</div>
                  <div class="slf-pitch-stat-label">Estimated materials cost per unit</div>
                </div>
                <div class="slf-pitch-stat">
                  <div class="slf-pitch-stat-num">[__ hrs]</div>
                  <div class="slf-pitch-stat-label">Estimated installation time</div>
                </div>
                <div class="slf-pitch-stat">
                  <div class="slf-pitch-stat-num">[__]</div>
                  <div class="slf-pitch-stat-label">Harvester models compatible</div>
                </div>
              </div>
              <ul class="slf-pitch-list" style="margin-top:1rem;">
                <li>Primary materials: acrylic sheet, PVC pipe, aluminum perforated sheet, small submersible pump, sugar water</li>
                <li>Mounts beneath the existing mechanical shaker — no harvester modification required</li>
                <li>Removable when SLF infestation is low</li>
                <li>Prepped with a single batch of sugar water before entering the field</li>
              </ul>
            </div>
          </div>

        </div>
      </div>
    </div>

    <!-- Milestone 2: Functional Prototype -->
    <div class="slf-accordion-item">
      <button class="slf-accordion-trigger" aria-expanded="false" aria-controls="panel-proto" onclick="togglePanel(this, 'panel-proto')">
        <span class="slf-acc-num">O5</span>
        <span>
          <span class="slf-acc-title">Functional Prototype</span>
          <span class="slf-acc-meta">Physical build, testing, and results</span>
        </span>
        <svg class="slf-acc-chevron" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.75">
          <path d="M3 6l5 5 5-5"/>
        </svg>
      </button>
      <div class="slf-accordion-panel" id="panel-proto" role="region">
        <!-- CAD image + two demo videos, all in one equal-height row -->
        <div class="slf-media-grid">
          <div>
            <p class="slf-media-label">CAD Model</p>
            <img
              src="{{ '/assets/images/SLF_Den__Sep__CAD.png' | relative_url }}"
              alt="SLF Density Separator CAD model">
          </div>
          <div>
            <p class="slf-media-label">Demo 1</p>
            <video controls>
              <source src="{{ '/assets/images/SLF-Separator-1.mov' | relative_url }}" type="video/mp4">
              <source src="{{ '/assets/images/SLF-Separator-1.mov' | relative_url }}" type="video/quicktime">
              Your browser does not support this video format.
            </video>
          </div>
          <div>
            <p class="slf-media-label">Demo 2</p>
            <video controls>
              <source src="{{ '/assets/images/SLF-Separator-2.MOV' | relative_url }}" type="video/mp4">
              <source src="{{ '/assets/images/SLF-Separator-2.MOV' | relative_url }}" type="video/quicktime">
              Your browser does not support this video format.
            </video>
          </div>
        </div>
      </div>
    </div>

    <!-- Milestone 3: Client Report -->
    <div class="slf-accordion-item">
      <button class="slf-accordion-trigger" aria-expanded="false" aria-controls="panel-report" onclick="togglePanel(this, 'panel-report')">
        <span class="slf-acc-num">O6</span>
        <span>
          <span class="slf-acc-title">Client Report</span>
          <span class="slf-acc-meta">Proposed solution, prototype results, and next steps</span>
        </span>
        <svg class="slf-acc-chevron" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.75">
          <path d="M3 6l5 5 5-5"/>
        </svg>
      </button>
      <div class="slf-accordion-panel" id="panel-report" role="region">

        <div class="slf-score-banner">
          <div class="slf-score-num">66<span style="font-size:1rem;color:#7a8c6e;">/100</span></div>
          <div class="slf-score-detail">
            <strong>Nominated for Outstanding Problem/Solution Award</strong> — selected as 1 of 10 finalist teams out of 50<br>
            Placed <strong>6th</strong> among finalists &nbsp;·&nbsp; Score range: 44–89
          </div>
        </div>

        <div class="slf-tag-row">
          <span class="slf-tag">Fluid Dynamics</span>
          <span class="slf-tag">Density Separation</span>
          <span class="slf-tag">Laser Cutting</span>
          <span class="slf-tag">Acrylic + PVC</span>
          <span class="slf-tag">Vineyard Engineering</span>
        </div>

        <p class="slf-section-label">Context &amp; Problem</p>
        <h2 class="slf-section-title">Why SLF in the harvest bin matters</h2>
        <div class="slf-body">
          <p>Over the past decade, Spotted Lanternfly has become a significant pest for vineyards across the United States, degrading both grape quality and harvest volume. During mechanical harvesting, a shaker arm dislodges ripe grapes from vines — but it also dislodges SLF, which mix into the collection stream.</p>
          <p>Our team focused on the specific moment <strong>immediately after the shaker</strong>, before grapes reach the collection bin. A solution here is high-leverage: it's fast, uses accessible materials, and addresses the contamination at its source.</p>
          <p>Key constraints we designed around: available materials, fabrication time, cost, minimizing sugar loss from grapes while submerged, and the short window between dislodgement and collection.</p>
        </div>

        <hr class="slf-divider">

        <p class="slf-section-label">Proposed Solution</p>
        <h2 class="slf-section-title">A recirculating sugar water separation system</h2>
        <div class="slf-body">
          <p>Grapes sink in sugar water; SLF float. Our system exploits this density difference with a two-tank design that mounts directly beneath the harvester's internal shaker.</p>
        </div>

        <div class="slf-step-grid">
          <div class="slf-step-card">
            <div class="slf-step-num">STEP 01</div>
            <div class="slf-step-name">Separation tank</div>
            <div class="slf-step-desc">Grapes and SLF fall into sugar water. Grapes sink; SLF float to the surface. Tank floor is angled ~10° toward a drain opening.</div>
          </div>
          <div class="slf-step-card">
            <div class="slf-step-num">STEP 02</div>
            <div class="slf-step-name">Water wheel</div>
            <div class="slf-step-desc">A rotating fin assembly skims floating SLF off the surface and deposits them into a separate waste container.</div>
          </div>
          <div class="slf-step-card">
            <div class="slf-step-num">STEP 03</div>
            <div class="slf-step-name">Strainer tank</div>
            <div class="slf-step-desc">Grapes and sugar water fall through the drain into a second container with holes in the floor, straining grapes from the liquid.</div>
          </div>
          <div class="slf-step-card">
            <div class="slf-step-num">STEP 04</div>
            <div class="slf-step-name">Recirculation pump</div>
            <div class="slf-step-desc">Sugar water is pumped back to the separation tank. Only one batch of sugar water is needed per harvesting run.</div>
          </div>
        </div>

        <div class="slf-body">
          <p>Cleaned grapes exit the strainer tank and drop directly into the harvester's collection bins, ready for processing. Sugar water (rather than plain water) is used to match the Brix level of the grapes, minimizing osmotic sugar loss during the brief submersion.</p>
        </div>

        <hr class="slf-divider">

        <p class="slf-section-label">Prototype &amp; Testing</p>
        <h2 class="slf-section-title">What we built and what we learned</h2>
        <div class="slf-body">
          <p>The prototype water wheel was built from two laser-cut ⅛" acrylic wheels (with a 1" center bore and six fin slots), a 1" PVC pipe axle, and two aluminum fins cut from perforated sheet. These were mounted in a clear plastic bucket modified with a Dremel for axle slots and a drain opening.</p>
        </div>

        <div class="slf-test-block">
          <div class="slf-test-title">Test 1 — Full range of motion (360°)</div>
          <div class="slf-test-body">We spun the assembled water wheel by hand through a full rotation to check for grinding or interference. The wheel fouled against the tapered walls of the bucket at the bottom of the stroke.</div>
          <div class="slf-test-fix">→ Fix: Use a rectangular, untapered container for the separation tank.</div>
        </div>

        <div class="slf-test-block">
          <div class="slf-test-title">Test 2 — Assembly stability</div>
          <div class="slf-test-body">We checked the wheel + axle + fin assembly for slipping and structural integrity during rotation. Components separated under load.</div>
          <div class="slf-test-fix">→ Fix: Epoxy all joints; increases durability and resistance to environmental wear.</div>
        </div>

        <hr class="slf-divider">

        <p class="slf-section-label">Conclusion &amp; Next Steps</p>
        <h2 class="slf-section-title">Promising — not yet field-ready</h2>
        <div class="slf-body">
          <p>The prototype is structurally sound, water-retentive, and mechanically smooth. We recommend continued development before field testing. Priority next steps:</p>
        </div>
        <ul class="slf-next-list">
          <li><span class="slf-next-dot"></span><span><strong>Verify SLF floatation empirically.</strong> The density assumption is the core mechanism and needs controlled testing with live or preserved SLF.</span></li>
          <li><span class="slf-next-dot"></span><span><strong>Fine-tune sugar concentration.</strong> Match solution Brix to individual grape varietals to eliminate osmotic sugar loss risk entirely.</span></li>
          <li><span class="slf-next-dot"></span><span><strong>Harvester compatibility design.</strong> Develop mounting hardware that adapts to the range of harvesters used across client vineyards.</span></li>
          <li><span class="slf-next-dot"></span><span><strong>Splash containment.</strong> Investigate grape impact forces on the sugar water surface to prevent product loss at high throughput.</span></li>
          <li><span class="slf-next-dot"></span><span><strong>Make it removable.</strong> Design the mount so the device can be detached when SLF infestation is low.</span></li>
        </ul>

        <hr class="slf-divider">

        <p class="slf-section-label">Client Feedback</p>
        <h2 class="slf-section-title">Response from Jennifer Russo, vineyard client</h2>
        <div class="slf-quote-block">
          "I spoke with your professor and explained that I thought it was a concept that I, nor my colleagues, had thought of."
          <span class="slf-quote-attr">— Jennifer Russo</span>
        </div>
        <div class="slf-body">
          <p>Jennifer validated the concept's novelty and offered several practical refinements for future development:</p>
          <ul>
            <li><strong>Avoid water dilution</strong> — water counteracts harvest quality; she suggested drawing free-run juice from the gondola bottom as the separation medium instead.</li>
            <li><strong>MOG removal as a bonus</strong> — leaves and woody canes (Material Other than Grapes) may also float out, improving overall harvest cleanliness and returning organic matter to the vineyard floor.</li>
            <li><strong>Gondola-top mounting</strong> — fitting the device above the gondola opening at fill-height could allow real-time sorting in the field without modifying the harvester itself.</li>
            <li><strong>Removability</strong> — the device should detach easily during low-infestation seasons.</li>
          </ul>
        </div>

      </div>
    </div>

  </div><!-- end accordion -->

</div><!-- end slf-page -->

<script>
function togglePanel(btn, panelId) {
  var panel = document.getElementById(panelId);
  var isOpen = btn.getAttribute('aria-expanded') === 'true';

  document.querySelectorAll('.slf-accordion-trigger').forEach(function(b) {
    b.setAttribute('aria-expanded', 'false');
  });
  document.querySelectorAll('.slf-accordion-panel').forEach(function(p) {
    p.classList.remove('is-open');
  });

  if (!isOpen) {
    btn.setAttribute('aria-expanded', 'true');
    panel.classList.add('is-open');
  }
}
</script>