---
layout: project
title: Anti-SLF
description: 
permalink: /projects/Open_Design_Project/
image: /assets/images/Screenshot 2026-04-10 221237.png

---
---
layout: project
title: "SLF Crusher: Open Design Project"
---

## Project Milestones
* [Client Pitch](#client-pitch)
* [Functional Prototype](#functional-prototype)

---

<h2 id="client-pitch">Milestone 1: Client Pitch</h2>

### Problem Statement
Current removal methods for Spotted Lanternflies (SLF)—such as shaking, suction, brushing, or high-force airflow—risk damaging grapes or interfering with harvesting machinery. There is currently no effective way to remove SLF during harvest without harming the crop.

### Impact & Vision
Because SLF feed on sap, they weaken vines and reduce fruit yield. Our goal is to eliminate SLF while preserving grapevine health. The long-term vision is a cylindrical, autonomous unit approximately the height of vineyard trellises that guides and traps insects.

### The Concept
* **Lure:** The device uses scents, sound frequencies, and sugary sap to lure SLF away from vines.
* **Mechanism:** A motion sensor activates a low-pressure vacuum to pull insects inside.
* **Execution:** A rotating blade guides them into an execution chamber where they are eliminated.
* **Advantage:** The system is designed for low maintenance and ease of installation.

### Key Risks
* **Competitive Attraction:** Natural grapevine phloem may be more appealing than artificial lures during ripening.
* **SLF Evasion:** The mechanical rotation might trigger the SLF flight response before they are captured.

---

<h2 id="functional-prototype">Milestone 2: Functional Prototype</h2>

### Purpose of the Prototype
This prototype validates the mechanical assembly of the "SLF Crusher". We specifically tested the ability of the rotating reaper wall and peg plate to guide pests into the collection chamber.

### Assembly & Components
The system uses a motor-driven D-profile shaft to rotate the internal components.

| Object Description | Material/Fabrication | Purpose |
| :--- | :--- | :--- |
| **Reaper Wall** | 3D Printed PLA | Rotating paddle/blade to guide insects |
| **Peg Plate** | 3D Printed PLA | Stationary plate with 28 pegs for convergence |
| **Rotating Floor** | 3D Printed PLA | Creates an opening for insects to fall |
| **Death Chamber** | 3D Printed PLA | Final collection container |

### Testing Results
We simulated Spotted Lanternflies using crumbled paper balls to measure success across three criteria:

* **Chamber Drop Test:** Whether paper balls reliably fall into the intended chamber.
    * **Result:** 5/5 successful drops.
* **Peg Movement Test:** Whether the pegs guide or jam the paper balls.
    * **Result:** The paper balls were crushed by the pegs rather than guided to the center.
* **Manual Spin Test:** Checking for smooth mechanical operation and friction.
    * **Result:** Faced resistance during rotation, causing the entire trap to rotate due to friction.

### Outcome & Next Iteration
To improve the design for the final submission, we will implement the following:
1. **Increased Curvature:** Redesigning the reaper wall path to guide rather than crush the flies.
2. **Larger Opening:** Increasing the diameter of the drop hole to accommodate multiple flies.
3. **Stability:** Adding weights to the bottom so the container remains stationary during rotation.
4. **Tolerances:** Adding more clearance between interlocking pegs to reduce mechanical resistance.

![Functional Prototype](/assets/images/Screenshot 2026-04-10 221237.png)