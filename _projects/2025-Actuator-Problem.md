---
layout: project
title: Actuator Height/Weight Optimization Problem
description: Design and Optimization Problem
technologies: 
image: /assets/images/Tolomatic-IMA-55-integrated-servomotor-actuator.jpg
---

For a class, we were asked to design a mechanism within a fixed 2D design space. The challenge was to use a rigid bar, three pin supports, and a linear actuator chosen from a manufacturer catalog to lift the maximum possible weight to the highest possible height. This project combined CAD modeling, actuator specification, and mechanical analysis to create a functional lifting system.

The final design used a rigid bar pinned to the ground at one end, with the actuator pinned at the other end. The actuator was free to pivot at its base, always applying force perpendicular to the bar. This setup created a lever system where the actuator force balanced the torque from the lifted weight. Careful geometric analysis showed that the minimum actuator body size and stroke constrained the bar’s range of motion, limiting the achievable angles and therefore the maximum lifting height.

![Shaded rendering of earlier version]({{ "/assets/images/PortfolioProblemDiagram.png" | relative_url }}){: .inline-image-r style="width: 200px"}

A Tolomatic IMA55 actuator with roller screw was selected from the catalog for its high peak thrust of 23,900 N, allowing the system to lift over 2,400 kg under ideal geometry. Stroke and housing dimensions were factored in to ensure the actuator fit inside the 150 cm × 50 cm box constraint. Static analysis demonstrated how the actuator force requirement depends on bar angle, and how actuator minimum/maximum length restricts the lowest and highest reachable positions.

To maximize the lift height and load capacity, I performed a moment balance about the bar’s ground pin. This allowed me to determine the maximum actuator force requirement at different bar angles. Since the actuator is pinned and always pushes along its axis, the effective lifting force depends on the geometric projection of the weight in the actuator’s direction.

The critical case occurs when the actuator is fully contracted, because the bar is at its lowest angle and the actuator must provide the greatest resisting torque. At this configuration, I solved geometrically for the component of the weight that aligned with the actuator’s line of action. Dividing the actuator’s peak thrust capacity by this projected component gave the maximum liftable weight for my design.

This project taught me how to integrate manufacturer datasheets with mechanical design, and how to balance competing constraints: maximizing lift capacity while staying within strict dimensional limits. It highlighted the importance of considering geometry, force transmission, and component limits together during early-stage mechanism design.

# Actuator Problem Portfolio Update

## **Step 1: Rigid Bar Analysis**

### **a) Problem Definition, Constraints/Objectives, Degrees of Freedom**
**Problem Definition:**  
Design a mechanism that uses an actuator to lift a load through a specified displacement. The mechanism includes a bar initially assumed to be rigid.

**Constraints:**
- Support the applied load without excessive deformation.  
- Allow the actuator to operate through its required stroke.  
- Maintain manufacturable geometry consistent with HW5.

**Objectives:**
- Achieve required output displacement.  
- Minimize actuator force.  
- Keep the mechanism lightweight and simple.

**Degrees of Freedom (DOF):**  
The mechanism has **one degree of freedom**, defined by the rotation/translation of the rigid bar driven by the actuator.

---

### **b) Static Analysis of the Rigid Bar**
Treating the bar as rigid, I performed a static analysis involving:  
- Summing forces and moments about the pivot.  
- Determining actuator force required to support the external load.  
- Using geometry to relate actuator stroke to output motion.

This analysis produced the final rigid-bar configuration used.

---

### **c) Final Rigid Mechanism Design**
![Shaded rendering of earlier version]({{ "/assets/images/PortfolioProblemDiagram.png" | relative_url }}){: .inline-image-r style="width: 200px"}

---

## **Step 2: Beam (Flexible Bar) Analysis**

### **a) Maximum Beam Deflection**
Once flexibility is considered, the bar becomes a beam subjected to two transverse forces:
1. The weight of the load  
2. The actuator’s transverse component

**Assumptions:**
- Beam is prismatic and linearly elastic.  
- Small-deflection Euler-Bernoulli beam theory applies.  
- Only transverse forces are considered.

Using the standard beam deflection formula (example for a cantilever with a tip load):

```
δ_max = (F * L^3) / (3 * E * I)
```

For this mechanism, the bar behaves as a **simply-supported beam** with a point load located between the supports. The correct maximum deflection expression is:

```
δ_max = (P * a^2 * b^2) / (3 * E * I * L)
```
Where:
- `L` = distance between pins A and B
- `a` = distance from A to the applied load
- `b = L - a`

---

### **b) Beam Design to Limit Deflection Below 2% of Length**
Requirement:
```
δ_max < 0.02 * L
```
To satisfy this, I selected a cross-section and material such that:
```
I > (F * L^3) / (3 * E * 0.02 * L)
```
I evaluated several beam profiles (e.g., rectangular aluminum tube, hollow steel section) and chose the most mass-efficient design meeting the deflection limit.

**Final Choice:**  
**Material:** 6061-T6 Aluminum rectangular tube  
**Cross‑section:** 25 mm × 50 mm outer, 2 mm wall thickness  
**Second moment of area:**  
```
I = 3.73 × 10⁻⁶ m⁴
```
**Beam mass:**  
```
~0.67 kg per meter
```
This design met the deflection requirement (δ < 0.02L) while offering the lowest mass among the evaluated options.*

---

### **c) Final Beam Design (Flexible)**
![Shaded rendering of earlier version]({{ "/assets/images/assets/images/Actuator-Portoflio-Problem-Image.jpg.png" | relative_url }}){: .inline-image-r style="width: 200px"}
---

## Beam Deflection Example (Simply-Supported Bar with Point Load)
This example matches the geometry of the mechanism used in the project: a bar pinned at A and B, with an applied point load between them.

### Geometry
- Beam span between pins A and B: `L`
- Point load applied at distance `a` from A
- Remaining distance to B: `b = L - a`
- Material modulus: `E`
- Second moment of area: `I`

### Reaction Forces
```
R_A = P * b / L
R_B = P * a / L
```

### Maximum Deflection (occurs at the load point)
```
delta_max = (P * a^2 * b^2) / (3 * E * I * L)
```
This is the appropriate formula for a simply-supported beam with a single point load.

### Deflection Curve (piecewise)
**For 0 ≤ x ≤ a:**
```
v(x) = (P * b * x / (6 * E * I * L)) * (L^2 - b^2 - x^2)
```
**For a ≤ x ≤ L:**
```
v(x) = (P * a * (L - x) / (6 * E * I * L)) * (2Lx - x^2 - a^2)
```

These formulas can be used directly for documenting your analysis or verifying numerical results.

### **End of Report**

