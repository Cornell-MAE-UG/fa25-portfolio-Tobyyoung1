---
layout: project
title: Pneumatic Braking System
description: Frictional Brakes on Cornell Hyperloop
image: assets/images/C-Bracket-Brakes-CAD-1.png
---

## Overview

Cornell Hyperloop's braking system consists of two complementary subsystems functioning on vastly different principles: frictional braking and magnetic braking. While both are crucial to the safe and efficient deceleration of the pod, the **frictional braking system is the primary mechanism**, while magnetic brakes provide initial deceleration at high speeds before the frictional brakes bring the pod to a complete stop.

The frictional brakes function as a contact-based braking system powered by a pneumatic assembly. A pressurized cylinder activates the system, allowing a C-bracket assembly to clamp onto the I-beam track until the pod stops. The use of an electric ball valve creates a **dead-man switch** — a fail-safe mechanism that engages braking automatically in the event of a power cut.

---

## Frictional Braking System — Full Analysis

### Design Concept

The frictional braking system applies a normal clamping force to the track I-beam via two brake pads, one above and one below the beam's flange. This sandwich-style clamping approach ensures symmetric force application, minimizing lateral bending moments on the beam and the mounting structure. The assembly is designed to be self-aligning along the track axis — accommodating minor lateral misalignment without compromising braking performance.

The core design philosophy prioritizes **fail-safe operation**: the system defaults to engaged (brakes on) when unpowered. If the pod loses electrical or pneumatic supply at any point, the return springs drive the brake pads into contact with the I-beam automatically, bringing the pod to a controlled stop.

### C-Bracket Assembly

![C-Bracket CAD — isometric view](assets/images/C-Bracket-Brakes-CAD-1.png)

The structural backbone of the frictional brake is the **C-bracket**, machined from 6061 aluminum stock (McMaster 89155K11 and 89155K113). The C-shape spans the I-beam flange, with brake pad carriers on the upper and lower arms. Key structural features include:

- **Upper plate:** Receives the pneumatic actuator load and distributes it through four guide pins into the moving brake pad carrier.
- **Lower plate (fixed):** Houses the stationary lower brake pad, bolted rigidly to the C-bracket body.
- **Guide columns:** Four precision-ground steel pins provide vertical alignment for the moving upper carrier, constraining motion to the actuation axis and preventing lateral drift under braking loads.
- **Gusset reinforcement:** Aluminum gussets (McMaster 5537T518) are epoxied and bolted at the bracket's inner corners to stiffen the structure against the bending moment induced by the clamping force couple.

The choice of aluminum over steel was deliberate: at the scale of this assembly, the weight savings (~65%) outweigh the stiffness reduction, and FEA confirmed that structural deflection under peak load remains under 7 µm.

### Dual-Actuator Configuration

![C-Bracket CAD — cross-section view showing actuator layout](assets/images/C-Bracket-Brakes-CAD-2.png)

Each brake unit uses **two pneumatic actuators** (McMaster 6453k112) mounted symmetrically on the upper plate. Operating in parallel, they together deliver the clamping force required to generate sufficient friction on the I-beam. The symmetric placement ensures the force resultant passes through the centroid of the brake pad contact area, preventing the pad carrier from tilting under load — a critical design constraint that prevents uneven pad wear and non-uniform pressure distribution.

The actuators are single-acting with spring return: compressed air drives the rod downward to engage; the integral spring retracts it when pressure is released. A return spring (Century Spring 80632CS) on the assembly provides supplemental retraction force and contributes to the fail-safe engagement behavior at the system level.

The actuators are fastened to the upper plate via dedicated actuator screws (McMaster 92949A151), and the moving carrier is connected to the actuator rods through a floating coupler that accommodates minor angular misalignment between the two actuator axes.

### Linear Guide Rail System

Precise vertical travel of the brake pad carrier is controlled by **MGN15H linear guide rails and bearing blocks** (LimoBearing). These miniature linear guides provide:

- Smooth, low-friction translation along the actuation axis
- High rigidity against off-axis moments generated during pad contact
- Consistent travel geometry, ensuring repeatable pad engagement across braking cycles

The rail blocks are mounted to the C-bracket side walls, with the rail carriages fixed to the moving upper pad carrier. The MGN15H profile was selected for its compact form factor relative to the load rating required — rated for ~800 N radial load, well above the lateral force components anticipated during braking.

### Physical Assembly

![Physical C-Bracket brake assembly](assets/images/Physical-C-Bracket-Brakes.png)

The machined and assembled C-bracket unit closely matches the CAD model. Visible in the physical assembly:

- Pneumatic actuator mounted centrally on the upper plate
- Return springs installed at the bracket's lateral faces
- Machined aluminum plates with tapped holes for guide pins and actuator screws
- Brake pad (black rubber composite, McMaster 6175K813) bonded to the lower fixed carrier

Machining was completed in-house using the Cornell engineering machine shop. All tapped features were cut using McMaster taps sized for ½"-13 and 10-32 thread specifications (26035A183, 2522A819). Epoxy (Amazon) was used at the gusset interfaces in addition to mechanical fastening to maximize joint stiffness.

### Pneumatic Circuit

The pneumatic supply system was designed around two key constraints: maximizing braking cycles per tank, and supporting the higher outlet pressures required by the new actuator configuration.

| Parameter | Previous Regulator | Current Regulator |
|---|---|---|
| Inlet pressure | 300 psi | 6000 psi |
| Outlet pressure range | 0–125 psi | 0–400 psi |
| Braking cycles per tank | 1–2 | 180–250 |

**Circuit layout (from tank to actuators):**

1. High-pressure tank → Manual shutoff valve
2. Manual valve → ¼in female T fitting → Pressure regulator
3. Regulator → Electric ball valve (E.B.V.)
4. E.B.V. → 2-way air split → two pneumatic cylinders
5. Pressure gauge teed off downstream of regulator for real-time monitoring

The **electric ball valve** is the central fail-safe element. In its default (de-energized) state, the valve vents the actuator supply line to atmosphere, causing the springs to engage the brakes. Only an active electrical signal holds the valve open and keeps the brakes retracted — this is the dead-man switch behavior required for competition safety compliance.

Remaining procurement items: 1× ⅛in NPT brass barb, 1× ⅛" NPT extruded tee brass fitting pipe.

---

## Structural Analysis (FEA)

![ANSYS Static Structural — Total Deformation result](assets/images/Frictional-Braking-Ansys.png)

A static structural finite element analysis was performed in **ANSYS Mechanical** to validate the C-bracket assembly under peak braking loads (December 1, 2025).

### Boundary Conditions

- Fixed supports applied at the mounting interface between the C-bracket and the pod chassis frame
- Actuator load applied downward through the upper plate in the direction of brake engagement
- Reaction force applied at the lower pad surface, representing the I-beam contact reaction

### Results

| Metric | Value |
|---|---|
| Analysis type | Static Structural — Total Deformation |
| Maximum deformation | 6.65 × 10⁻⁶ m (6.65 µm) |
| Location of maximum | Mounting plate corners (cantilevered extremities) |
| Minimum deformation | 0 m (fixed mounting face) |
| Date run | December 1, 2025 |

### Interpretation

The deformation contour shows that the highest deflection occurs at the outer corners of the upper mounting plate — a predictable result, as these regions are furthest from the constrained support points and experience the largest bending moment arm. Critically, the **clamping interface and guide pin bores** (the dimensionally critical surfaces) remain in the blue-to-cyan range, indicating deflections below 1.5 µm.

This is well within acceptable tolerances for the MGN15H guide rail system (which has a running clearance of ~10–20 µm) and confirms that the structural design does not compromise braking geometry under load. The aluminum C-bracket does not require reinforcement for this load case.

---

## Assembly Status

### Completed
- Finished machining all aluminum components (C-bracket body, upper and lower carriers, guide pin bores)
- Installed pneumatic actuators and bearing screws
- Nearly completed full brake assembly

### Remaining
- Attach MGN15H linear guide rails (awaiting delivery from LimoBearing)
- Install return spring
- Connect to pneumatic circuit and conduct integrated pressure test

---

## Bill of Materials

| Item | Manufacturer | Part Number | Unit Price | Total |
|---|---|---|---|---|
| Springs | Century Spring | 80632CS | $9.68 | $38.72 |
| Braking Pads | McMaster | 6175K813 | $10.34 | $10.34 |
| Guide Rails and Bearings | LimoBearing | MGN15H | $10.35 | $41.40 |
| Gussets | McMaster | 5537T518 | $5.09 | $40.72 |
| Pneumatic Actuators | McMaster | 6453k112 | $168.09 | $336.18 |
| Plate Screws | Amazon | n/a | $14.99 | $14.99 |
| Bearing Screws | McMaster | 92467A469 | $8.65 | $8.65 |
| Actuator Screws | McMaster | 92949A151 | $5.92 | $5.92 |
| Stock for C-bracket | McMaster | 89155K11 | $18.89 | $18.89 |
| Stock for C-bracket | McMaster | 89155K113 | $10.81 | $10.81 |
| Tap ½"-13, 1-21/32" Thread Length | McMaster | 26035A183 | $7.71 | $7.71 |
| Tap 10-32, 7/8" Thread Length | McMaster | 2522A819 | $7.00 | $7.00 |
| Epoxy | Amazon | n/a | $12.87 | $12.87 |
| **Subtotal** | | | | **$554.20** |