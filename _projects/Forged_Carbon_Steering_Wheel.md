---
layout: project
title: Forged Carbon Fibre Steering Wheel
description: I designed, evaluated and manufactured a forged carbon steering wheel.
permalink: /projects/Forged_Carbon_Steering_Wheel/
image: /assets/images/pic 123.png
---

# Cornell Electric Vehicles 




***

## Detailed Design (CAD Models)

According to 2025 Shell Eco Marathon rules for Urban Concept Vehicles, the steering mechanism must be operated with both hands. The steering wheel was designed to comfortably accommodate this constraint.

![Pic 11]({{ "/assets/images/cad render.png" | relative_url }}){: class="inline-image"}


## General Reflection:

The steering wheel in UC ‘25 was overall effective. **Forged carbon fiber** was used to manufacture it because of its high strength-to-weight ratio and design flexibility. Forged carbon is unique in that it liberates the designer from the fiber-orientation constraints of traditional woven carbon. Instead, it allows for complex geometries and three-dimensional shapes, with only a slight drop-off in strength. There was a **30% reduction in the steering wheel’s weight** compared to the previous year’s stock metal part. The driver reported comfortable steering throughout testing and racing.

## Manufacturing

The wheel was manufactured through a carbon forging process. After the wheel’s design was finalized, the CAD model was converted to a negative, and a mould was created in Solidworks. The mould consisted of four parts, two for the female section and two for the male section. The female and male moulds were split down the middle to ease the demoulding process. The walls of the upper and lower sections were inclined to facilitate demoulding.

![Pic 12]({{ "/assets/images/female mould.png" | relative_url }}){: class="inline-image"}

![Pic 13]({{ "/assets/images/male mould.png" | relative_url }}){: class="inline-image"}


The carbon fiber chips and epoxy resin were mixed and placed between the male and female moulds. The mould was compressed and cured at eight points around the mould to ensure equal pressure. They were tightened until no gaps were visible between any of the interfaces. In certain places, the PETG cracked under the stress of the clamps, due to the unfortunate low infill, however this was quickly fixed by spreading the force using wooden pallets in between the clamp faces and the surface of the mould.

After 24 hours, the resin had dried. The part was demoulded using a hammer and screwdriver, separating each section before pulling out the wheel. At this point, there were many imperfections, such as overhangs and occluded bolt holes. These were fixed using a die grinder, a hand drill, and sandpaper. The part was then finished with polish.

![Pic 14]({{ "/assets/images/real life.png" | relative_url }}){: class="inline-image"}

***

## Structural Validation: Finite Element Analysis (FEA)

To validate the structural integrity of the forged carbon fiber steering wheel, a **Static Stress Analysis** was conducted in Autodesk Inventor. The simulation's primary goal was to ensure the design maintained a minimum Factor of Safety (FOS) of **2.0** under extreme turning torque.

### **Analysis Setup**

| Parameter | Value | Details |
| :--- | :--- | :--- |
| **Material Model** | Forged Carbon Fiber (60/40) | Custom-defined as Isotropic with Ultimate Tensile Strength (sig_ult) of **27,850 psi** |
| **Constraint** | Fixed | Applied to the inner faces of the **five mounting holes** at the hub, simulating a rigid bolt connection. |
| **Loading** | **90 lbf** (Total) | Applied as a force couple (two opposing 45 lbf tangential loads) on the rim, simulating maximum driver steering effort. |

### **FEA Results and Conclusion**

The simulation confirmed that the design is exceptionally robust for the required load case.

![Pic 15]({{ "/assets/images/pic 123.png" | relative_url }}){: class="inline-image"}

| Parameter | Result Value | Interpretation |
| :--- | :--- | :--- |
| **Minimum FOS (FOS_min)** | **4.42** | The design is safe and over-engineered, exceeding the design target of 2.0 by a large margin. |
| **Critical Location** | Spoke-to-Hub Fillet | The highest stress concentration was correctly identified at this internal radius. |
| **Calculated Breaking Force** | **398 lbf** | The wheel is capable of withstanding over four times the simulated maximum human load before material failure (FOS = 1.0). |

The FEA results strongly validate the material and geometric design choices, demonstrating that the wheel provides a high level of structural safety and reliability.

## Assembly

A steering hub was designed and 3D printed using ABS, used to interface the steering wheel with the steering column. It featured five mounting holes to match the steering wheel, as well as a dowel hole to secure it with the steering column. The hub was attached to the wheel using 1/4”-20 bolts, and the assembled wheel was secured to the steering column using 1/4” dowels.



## Project Reflection

The forged carbon steering wheel was an improvement from the previous year’s. Significant time could have been saved in the finishing stage if proper infill is used for the moulds. For future forged carbon parts, especially those which require standby components, epoxy tooling board moulds should be considered (for ease of repeatability and precise machining).









