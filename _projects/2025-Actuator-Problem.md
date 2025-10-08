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

