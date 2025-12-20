---
layout: project
title: General Electric J85 Turbojet Thermodynamic Analysis
description: Given a 150cm x 50cm design space, I was tasked with using a linear actuator to lift the maximum possible weight the highest possible height.
permalink: /General_Electric_J85_Thermodynamic_Analysis/
image: /assets/images/Main_Image.jpg
---

# General Electric J85 Turbojet: Brayton Cycle Analysis

This project analyzes the thermodynamic cycle of the **General Electric J85**, a high-performance turbojet engine. The J85 is a single-spool, axial-flow engine used in the T-38 Talon and F-5 fighter aircraft. This analysis utilizes the Air-Standard Brayton Cycle to model the engine's performance at Sea Level Static (SLS) conditions.

![Pic 77]({{ "/assets/images/F5_Tiger.jpg" | relative_url }}){: class="inline-image"}
---


## 1. System Overview and Components

The J85 operates by converting thermal energy from fuel combustion into kinetic energy for propulsion. The engine consists of five primary stages:

* **Diffuser (Inlet):** Slows incoming air to increase static pressure.
* **Compressor:** An 8-stage axial system that increases air pressure.
* **Combustor:** Adds heat at constant pressure via fuel injection.
* **Turbine:** Extracts energy to drive the compressor.
* **Nozzle:** Accelerates exhaust gas to generate thrust.


![Pic 78]({{ "/assets/images/Diagram.jpg" | relative_url }}){: class="inline-image"}
---

## 2. Qualitative Cycle Description

The engine functions as a steady-state flow device. Unlike stationary power plants, the J85 turbine only produces enough power to drive the compressor. 

The net shaft work is zero ($\dot{W}_{net} = 0$). The "useful" output is the high velocity of the exhaust gas. Pressure energy is converted into kinetic energy in the nozzle, creating the thrust required for flight.



---

## 3. Governing Equations

These steady-flow equations define the thermodynamic state at each stage:

**Mass Balance:**
$$\dot{m}_{in} = \dot{m}_{out}$$

**Energy Balance (First Law):**
$$0 = \dot{Q}_{in} - \dot{W}_{net} + \dot{m} \left[ (h_{in} - h_{out}) + \frac{V_{in}^2 - V_{out}^2}{2} \right]$$

**Isentropic Relations:**
$$\frac{T_{exit}}{T_{inlet}} = \left( \frac{P_{exit}}{P_{inlet}} \right)^{\frac{k-1}{k}}$$

---

## 4. Thermodynamic State Point Analysis

Calculations assume $P_{ambient} = 101.3$ kPa, $T_{ambient} = 288$ K, and a compression ratio ($r_p$) of **11.5:1**.

### Stage 1 to 2: Compression
The compressor increases pressure to 1165 kPa.
* **Exit Temperature ($T_2$):** $T_2 = 288 \cdot (11.5)^{0.2857} = 580$ K
* **Work Required ($w_c$):** $1.005 \cdot (580 - 288) = 293.46$ kJ/kg

### Stage 2 to 3: Combustion
Heat is added to reach a Turbine Inlet Temperature (TIT) of 1250 K.
* **Heat Input ($q_{in}$):** $1.005 \cdot (1250 - 580) = 673.35$ kJ/kg

### Stage 3 to 4: Turbine Expansion
The turbine extracts work equal to the compressor work.
* **Exit Temperature ($T_4$):** $1250 - (293.46 / 1.005) = 958$ K
* **Exit Pressure ($P_4$):** $P_3 / (T_3/T_4)^{3.5} = 458.6$ kPa

### Stage 4 to 5: Nozzle Acceleration
Gas expands to ambient pressure to produce velocity.
* **Exit Temperature ($T_5$):** $958 \cdot (101.3 / 458.6)^{0.2857} = 622$ K
* **Exit Velocity ($V_5$):** $\sqrt{2 \cdot 1005 \cdot (958 - 622)} = 822$ m/s

---

## 5. Performance Summary

| Metric | Value |
| :--- | :--- |
| **Specific Thrust** | 822 N·s/kg |
| **Thermal Efficiency** | 50.1% |
| **Cycle Heat Input** | 673.35 kJ/kg |
| **Exhaust Velocity** | 822 m/s |

---

## 6. Performance Change: High Altitude Effects

At an altitude of 11,000m, ambient temperature drops to 216.7 K and pressure drops to 22.6 kPa.

* **Efficiency:** Lower inlet temperatures ($T_1$) mean the compressor requires less work to reach the same pressure ratio, which can improve thermal efficiency.
* **Thrust:** Because air density is much lower at altitude, the mass flow rate ($\dot{m}$) decreases. This results in a significant drop in total thrust despite high exit velocities.