---
layout: project
title: Linear Actuator Project
description: Given a 150cm x 50cm design space, I was tasked with using a linear actuator to lift the maximum possible weight the highest possible height.
technologies: 
permalink: /linear_actuator_project
image: /assets/images/Image.jpeg
---

##  Static Structural Analysis: Max Lift Frame Design

This analysis determines the maximum weight and maximum height achievable by the custom-designed lifting frame, based on the sketch and the selected linear actuator.


---

### 1. Component Specifications and Geometry

| Parameter | Symbol | Value (m) | Notes |
| :--- | :--- | :--- | :--- |
| **Linear Actuator Max Force** | F\_act | 12,746 N (2,865 lbf) | Tolomatic IMA 55, Max Thrust |
| **Rigid Bar Length (Load Arm)** | L\_load | 0.45 m | Length from Pivot (Pin 3) to Load |
| **Actuator Max Stroke** | Delta H\_act | 0.152 m | Max vertical lift from the actuator |
| **Pivot Height** | H\_P | 0.4664 m | Vertical distance from ground to Pin 3 |
| **Actuator X-distance from Pivot** | X\_dist | 0.20 m | Used for trigonometric calculations |

---

### 2. Maximum Bar Angle (Theta\_max)

The maximum angle is determined by the actuator's vertical rise over the fixed horizontal distance from the pivot.

#### Calculation:
Theta\_max = arctan(Actuator Lift / X\_dist)
Theta\_max = arctan(0.152 m / 0.20 m) ≈ **37.24°**

### 3. Highest Possible Height (H\_max)

The maximum vertical lift of the bar's tip from the ground.

#### Calculation:
H\_max = H\_P + L\_bar * sin(Theta\_max)
H\_max = 0.4664 m + 0.45 m * sin(37.24°) ≈ **0.7387 m**

#### Result:
* **Highest Possible Height:** **73.87 cm** (0.7387 m)

---

### 4. Weight Lifted at H\_max (Worst-Case W\_min)

This uses trigonometry to find the actual moment arms at **37.24°**.

* **Actuator Perpendicular Arm (L\_perp):** 0.20 m * cos(37.24°) ≈ **0.1594 m**
* **Load Arm (L\_load):** 0.45 m * cos(37.24°) ≈ **0.3582 m**

#### Calculation:
W\_min = (F\_act * L\_perp) / L\_load
W\_min = (12,746 N * 0.1594 m) / 0.3582 m ≈ **5,669 N**

#### Final Result Summary:
* **Weight that can be lifted at H\_max:** **5,669 N**
* **Mass that can be lifted at H\_max:** **578 kg** (5,669 N / 9.81 m/s^2)