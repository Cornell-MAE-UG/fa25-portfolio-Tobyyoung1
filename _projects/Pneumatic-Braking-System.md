---
layout: project
title: Pneumatic Braking System
description: Frictional Brakes on Cornell Hyperloop
image: assets/images/C-Bracket-Brakes-CAD-1.png
---

<style>
  .container { max-width: 1000px; padding: 0 1in; }

  .pc { font-size: 0.97rem; line-height: 1.75; color: #333; }
  .pc h2 { font-size: 1.5rem; margin: 2.5rem 0 0.5rem; border-bottom: 2px solid #d0d4e0; padding-bottom: 0.3rem; }
  .pc h3 { font-size: 1.1rem; margin: 1.75rem 0 0.4rem; color: #3a3f58; }
  .pc p  { margin: 0 0 0.9rem; }
  .pc ul, .pc ol { margin: 0 0 0.9rem 1.25rem; }
  .pc li { margin-bottom: 0.3rem; }
  .pc hr { border: none; border-top: 1px solid #e2e4ec; margin: 2rem 0; }

  .stat-bar { display: flex; gap: 12px; margin: 1.25rem 0 1.75rem; flex-wrap: wrap; }
  .stat-box { flex: 1; min-width: 130px; background: #eceef5; border-radius: 8px; padding: 0.7rem 1rem; }
  .stat-box .val { font-size: 1.4rem; font-weight: 700; color: #3a3f58; line-height: 1; }
  .stat-box .lbl { font-size: 0.72rem; color: #666; margin-top: 4px; text-transform: uppercase; letter-spacing: 0.04em; }

  .img-right { float: right; width: 38%; margin: 0 0 1.2rem 1.5rem; }
  .img-left  { float: left;  width: 38%; margin: 0 1.5rem 1.2rem 0; }
  .img-full  { display: block; width: 80%; margin: 1.25rem auto; }
  .img-right img, .img-left img, .img-full img {
    width: 100%; border-radius: 8px;
    box-shadow: 0 3px 10px rgba(0,0,0,0.13);
  }
  .img-caption { font-size: 0.75rem; color: #777; text-align: center; margin-top: 5px; font-style: italic; }
  .clearfix::after { content: ''; display: table; clear: both; }

  /* Table — alternating rows use a warm tan so they contrast against the page bg */
  .pc table { width: 100%; border-collapse: collapse; margin: 1rem 0 1.25rem; font-size: 0.88rem; }
  .pc th { background: #3a3f58; color: #fff; text-align: left; padding: 8px 12px; font-weight: 600; }
  .pc td { padding: 7px 12px; border-bottom: 1px solid #ccc; background: #fff; }
  .pc tr:nth-child(even) td { background: #e8e8e8; }
  .pc tr:last-child td { border-bottom: none; font-weight: 600; background: #d0d0d0; }

  .status-grid { display: flex; gap: 1rem; margin: 0.75rem 0 1.25rem; flex-wrap: wrap; }
  .status-col { flex: 1; min-width: 200px; background: #eceef5; border-radius: 8px; padding: 0.9rem 1rem; }
  .status-col h4 { margin: 0 0 0.6rem; font-size: 0.8rem; text-transform: uppercase; letter-spacing: 0.06em; color: #3a3f58; }
  .status-col ul { margin: 0; padding-left: 1.1rem; }
  .status-col li { font-size: 0.87rem; margin-bottom: 0.3rem; }
  .done li::marker { color: #3a7d44; }
  .todo li::marker { color: #c0392b; }
</style>

<div class="pc">

<h2>Overview</h2>

<p>Cornell Hyperloop's braking system consists of two complementary subsystems: frictional braking and magnetic braking. The <strong>frictional braking system is the primary mechanism</strong> — it brings the pod to a complete stop after the magnetic brakes have handled initial deceleration at high speed.</p>

<p>A pressurized pneumatic cylinder activates a C-bracket assembly that clamps onto the I-beam track. An electric ball valve creates a <strong>dead-man switch</strong>: if the pod loses power at any point, the system defaults to brakes engaged — a competition safety requirement.</p>

<div class="stat-bar">
  <div class="stat-box"><div class="val">6000 psi</div><div class="lbl">Inlet pressure</div></div>
  <div class="stat-box"><div class="val">0–400 psi</div><div class="lbl">Outlet range</div></div>
  <div class="stat-box"><div class="val">180–250</div><div class="lbl">Brake cycles / tank</div></div>
  <div class="stat-box"><div class="val">6.65 µm</div><div class="lbl">Max FEA deformation</div></div>
  <div class="stat-box"><div class="val">$554</div><div class="lbl">BOM total</div></div>
</div>

<hr>

<h2>Frictional Braking System</h2>

<h3>Design Concept</h3>
<p>The system applies a symmetric clamping force to the I-beam flange via brake pads above and below, minimizing lateral bending on both the beam and the mount. The assembly self-aligns along the track axis to tolerate minor positional variation without compromising performance.</p>

<hr>

<h3>C-Bracket Assembly</h3>

<div class="clearfix">
  <div class="img-right">
    <img src="{{ '/assets/images/C-Bracket-Brakes-CAD-2.png' | relative_url }}" alt="C-Bracket cross-section showing actuator layout">
    <p class="img-caption">Cross-section view — dual actuator arrangement</p>
  </div>

  <p>The structural backbone is the <strong>C-bracket</strong>, machined from 6061 aluminum stock (McMaster 89155K11, 89155K113). Key features:</p>
  <ul>
    <li><strong>Upper plate</strong> — receives actuator load, distributes it through four guide pins to the moving brake carrier</li>
    <li><strong>Lower plate (fixed)</strong> — houses the stationary lower brake pad, bolted rigidly to the bracket body</li>
    <li><strong>Guide columns</strong> — four precision steel pins constrain carrier motion to the actuation axis, preventing lateral drift under load</li>
    <li><strong>Gusset reinforcement</strong> — aluminum gussets (McMaster 5537T518) epoxied and bolted at inner corners to stiffen against the clamping bending moment</li>
  </ul>
  <p>Aluminum was chosen over steel for ~65% weight savings. FEA confirmed deflection at the clamping interface stays under 1.5 µm — within MGN15H rail clearance.</p>
</div>

<hr>

<h3>Physical Assembly</h3>

<div class="clearfix">
  <div class="img-left">
    <img src="{{ '/assets/images/Physical-C-Bracket-Brakes.png' | relative_url }}" alt="Machined and assembled C-bracket brake unit">
    <p class="img-caption">Finished assembly — machined in-house at Cornell</p>
  </div>

  <p>The machined assembly closely matches the CAD model. Visible components include the centrally mounted pneumatic actuator, lateral return springs, tapped aluminum plates, and the lower rubber brake pad (McMaster 6175K813).</p>
  <p>All features were machined in the Cornell engineering shop using ½"-13 and 10-32 taps (McMaster 26035A183, 2522A819). Gusset interfaces were bonded with epoxy in addition to mechanical fastening.</p>
</div>

<hr>

<h3>Linear Guide Rail System</h3>
<p>Vertical travel of the brake pad carrier is guided by <strong>MGN15H linear rails and bearing blocks</strong> (LimoBearing), providing low-friction translation, high off-axis rigidity, and repeatable engagement geometry across hundreds of braking cycles. The MGN15H was selected for its compact footprint at ~800 N radial load rating — above the anticipated lateral force components.</p>

<hr>

<h3>Pneumatic Circuit</h3>

<div class="clearfix">
  <div class="img-right">
    <img src="{{ '/assets/images/Pneumatics-Diagram.png' | relative_url }}" alt="Physical pneumatic circuit layout with annotated components">
    <p class="img-caption">Annotated pneumatic circuit — tank, regulator, E.B.V., and cylinders</p>
  </div>

  <table>
    <thead><tr><th>Parameter</th><th>Previous Regulator</th><th>Current Regulator</th></tr></thead>
    <tbody>
      <tr><td>Inlet pressure</td><td>300 psi</td><td>6000 psi</td></tr>
      <tr><td>Outlet pressure range</td><td>0–125 psi</td><td>0–400 psi</td></tr>
      <tr><td>Braking cycles per tank</td><td>1–2</td><td>180–250</td></tr>
    </tbody>
  </table>

  <p>Circuit flow: tank → manual shutoff valve → ¼in female T → pressure regulator → electric ball valve (E.B.V.) → 2-way air split → two pneumatic cylinders, with a pressure gauge teed downstream of the regulator. The E.B.V. vents to atmosphere when de-energized, spring-engaging the brakes — the dead-man switch behavior. Remaining procurement: 1× ⅛in NPT brass barb, 1× ⅛" NPT extruded tee fitting.</p>
</div>

<hr>

<h2>Structural Analysis (FEA)</h2>

<div class="img-full">
  <img src="{{ '/assets/images/Frictional-Braking-Ansys.png' | relative_url }}" alt="ANSYS total deformation result — December 2025">
  <p class="img-caption">ANSYS Static Structural — Total Deformation (Dec 1, 2025). Max deformation 6.65 µm at mounting plate corners.</p>
</div>

<p>Static structural FEA in <strong>ANSYS Mechanical</strong> validated the C-bracket under peak braking loads. Fixed supports were applied at the chassis mounting interface; actuator load was applied downward through the upper plate; I-beam contact reaction was applied at the lower pad surface.</p>

<table>
  <thead><tr><th>Metric</th><th>Value</th></tr></thead>
  <tbody>
    <tr><td>Analysis type</td><td>Static Structural — Total Deformation</td></tr>
    <tr><td>Maximum deformation</td><td>6.65 × 10⁻⁶ m (6.65 µm) — at mounting plate corners</td></tr>
    <tr><td>Clamping interface deformation</td><td>&lt; 1.5 µm (blue-cyan range)</td></tr>
    <tr><td>MGN15H rail clearance</td><td>~10–20 µm — deformation well within tolerance</td></tr>
    <tr><td>Date run</td><td>December 1, 2025</td></tr>
  </tbody>
</table>

<p>Maximum deflection occurs at the outer corners of the upper mounting plate — the furthest points from the constrained support — as expected. The clamping interface and guide pin bores remain essentially rigid. No reinforcement is required.</p>

<hr>

<h2>Assembly Status</h2>

<div class="status-grid">
  <div class="status-col done">
    <h4>✓ Completed</h4>
    <ul>
      <li>All aluminum components machined</li>
      <li>Pneumatic actuators installed</li>
      <li>C-bracket assembly nearly complete</li>
      <li>FEA simulation validated</li>
    </ul>
  </div>
  <div class="status-col todo">
    <h4>⧖ Remaining</h4>
    <ul>
      <li>Linear guide rails — awaiting delivery</li>
      <li>Install return spring</li>
      <li>Connect to pneumatic circuit</li>
      <li>Integrated pressure test</li>
    </ul>
  </div>
</div>

<hr>

<h2>Bill of Materials</h2>

<table>
  <thead><tr><th>Item</th><th>Manufacturer</th><th>Part Number</th><th>Unit Price</th><th>Total</th></tr></thead>
  <tbody>
    <tr><td>Springs</td><td>Century Spring</td><td>80632CS</td><td>$9.68</td><td>$38.72</td></tr>
    <tr><td>Braking Pads</td><td>McMaster</td><td>6175K813</td><td>$10.34</td><td>$10.34</td></tr>
    <tr><td>Guide Rails and Bearings</td><td>LimoBearing</td><td>MGN15H</td><td>$10.35</td><td>$41.40</td></tr>
    <tr><td>Gussets</td><td>McMaster</td><td>5537T518</td><td>$5.09</td><td>$40.72</td></tr>
    <tr><td>Pneumatic Actuators</td><td>McMaster</td><td>6453k112</td><td>$168.09</td><td>$336.18</td></tr>
    <tr><td>Plate Screws</td><td>Amazon</td><td>n/a</td><td>$14.99</td><td>$14.99</td></tr>
    <tr><td>Bearing Screws</td><td>McMaster</td><td>92467A469</td><td>$8.65</td><td>$8.65</td></tr>
    <tr><td>Actuator Screws</td><td>McMaster</td><td>92949A151</td><td>$5.92</td><td>$5.92</td></tr>
    <tr><td>Stock for C-bracket</td><td>McMaster</td><td>89155K11</td><td>$18.89</td><td>$18.89</td></tr>
    <tr><td>Stock for C-bracket</td><td>McMaster</td><td>89155K113</td><td>$10.81</td><td>$10.81</td></tr>
    <tr><td>Tap ½"-13, 1-21/32"</td><td>McMaster</td><td>26035A183</td><td>$7.71</td><td>$7.71</td></tr>
    <tr><td>Tap 10-32, 7/8"</td><td>McMaster</td><td>2522A819</td><td>$7.00</td><td>$7.00</td></tr>
    <tr><td>Epoxy</td><td>Amazon</td><td>n/a</td><td>$12.87</td><td>$12.87</td></tr>
    <tr><td>Subtotal</td><td>—</td><td>—</td><td>—</td><td>$554.20</td></tr>
  </tbody>
</table>

</div>