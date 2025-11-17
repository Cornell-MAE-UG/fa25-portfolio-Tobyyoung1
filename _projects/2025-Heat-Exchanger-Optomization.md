---
layout: project
title: Heat Exchanger Optimization
description: Heat Exchanger Analysis and Optimization
technologies: [Heat Exchanger, Fluid Pumps]
image: assets/images/Parallel-Flow-Setup.jpg
---
I assembled a bench-top plate heat-exchanger test rig from two insulated buckets (one heated, one cooled), two small circulation pumps, clear tubing, and a small brazed/plate heat-exchanger module. Each bucket acts as a reservoir and supply for one fluid stream (hot stream and cold stream). Fluid is drawn from each bucket by its respective pump and routed through the heat-exchanger. Temperature probes measured the stream temperatures entering and exiting the plate exchanger and the plate body temperature (hot and cold side temperatures on the exchanger). I ran four main tests: parallel-flow and counter-flow configurations, each at high and low pump flow rates. The experiment measures how much the hot stream cools and the cold stream warms, giving an experimental heat transfer rate and an estimate of exchanger effectiveness for each condition.

Data:
![Shaded rendering of earlier version]({{ "assets/images/Heat-exchanger-data.png" | relative_url }}){: .inline-image-r style="width: 200px"}

Parallel Flow:  
Diagram:  
![Shaded rendering of earlier version]({{ "assets/images/Parallel-Flow-Diagram.png" | relative_url }}){: .inline-image-r style="width: 200px"}

Setup:  
![Shaded rendering of earlier version]({{ "assets/images/Parallel-Flow-Setup.jpg" | relative_url }}){: .inline-image-r style="width: 200px"}

Counter Flow:  
Diagram:  
![Shaded rendering of earlier version]({{ "assets/images/Counterflow-Diagram.png" | relative_url }}){: .inline-image-r style="width: 200px"}

Setup:  
![Shaded rendering of earlier version]({{ "assets/images/Counterflow-Setup.jpg" | relative_url }}){: .inline-image-r style="width: 200px"}

Mass Balance, Energy Balance, Entropy Balance:  
![Shaded rendering of earlier version]({{ "assets/images/Mass-balance-energy-balance-entropy-balance.png" | relative_url }}){: .inline-image-r style="width: 200px"}

To make a heat exchanger more effective, based on the findings from this experiment, it is more effective to use counterflow than parallel flow. To implement this modification, the heat exchanger tubing would be reconfigured so that the hot and cold fluid streams flow in opposite directions, converting the system from parallel flow to counterflow. This adjustment increases the log mean temperature difference, improving the exchanger’s effectiveness and allowing the cold fluid to reach a higher exit temperature. As a result, the heat transfer rate is expected to rise noticeably, and the process will operate with lower entropy generation, making it more thermodynamically efficient. The performance gains can be quantified using measured inlet temperatures and calculated heat capacity rates to compare the theoretical effectiveness and heat transfer for both flow configurations.

