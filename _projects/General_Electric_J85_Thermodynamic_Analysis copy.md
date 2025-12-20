---
layout: project
title: General Electric J85 Turbojet Thermodynamic Analysis
description: Given a 150cm x 50cm design space, I was tasked with using a linear actuator to lift the maximum possible weight the highest possible height.
permalink: /General_Electric_J85_Thermodynamic_Analysis_copy/
image: /assets/images/Main_Image.jpg
---

# General Electric J85 Turbojet: Brayton Cycle Analysis

This project analyzes the thermodynamic cycle of the **General Electric J85**, a high-performance turbojet engine. The J85 is a single-spool, axial-flow engine used in the T-38 Talon and F-5 fighter aircraft. This project transitions from an ideal Brayton cycle to a real-world engine model. We account for isentropic efficiencies, pressure drops in the combustor, and variable specific heats ($c_p$) to validate the performance of the General Electric J85-GE-21.


![Pic 77]({{ "/assets/images/F5_Tiger.jpg" | relative_url }}){: class="inline-image"}
---



## 1. Ambient Conditions and Compressor Analysis

At Sea Level Static (SLS) conditions:
* **$P_1 = 101.325$ kPa**
* **$T_1 = 288.15$ K**
* **Pressure Ratio ($r_p$) = 11.3**

In a real compressor, internal friction and flow separation increase the temperature rise required to reach a specific pressure. We use an isentropic efficiency ($\eta_c$) of **0.85**.



**Ideal Exit Temperature ($T_{2s}$):**
$$T_{2s} = T_1(r_p)^{\frac{k-1}{k}} = 288.15(11.3)^{0.2857} = 576.2 \text{ K}$$

**Actual Exit Temperature ($T_{2a}$):**
The energy wasted as heat is captured by the efficiency term:
$$T_{2a} = T_1 + \frac{T_{2s} - T_1}{\eta_c} = 288.15 + \frac{576.2 - 288.15}{0.85} = 627.0 \text{ K}$$

**Specific Compressor Work ($w_c$):**
$$w_c = c_p(T_{2a} - T_1) = 1.005(627.0 - 288.15) = 340.54 \text{ kJ/kg}$$

---

![Pic 78]({{ "/assets/images/Diagram.jpg" | relative_url }}){: class="inline-image"}

## 2. Combustion Energy Balance

We model the combustor as a constant-pressure heat addition, though we account for a **3% stagnation pressure loss** ($\Delta P_{comb}$) due to fluid friction and burner geometry.

**Exit Pressure ($P_3$):**
$$P_3 = P_2(0.97) = (101.325 \cdot 11.3) \cdot 0.97 = 1110.6 \text{ kPa}$$

**Fuel-to-Air Ratio ($f$):**
Using a Turbine Inlet Temperature ($T_3$) of **1250 K** and the Lower Heating Value (LHV) of Jet-A fuel ($43,100 \text{ kJ/kg}$):
$$f = \frac{c_{pg} T_3 - c_{pa} T_{2a}}{LHV - c_{pg} T_3}$$
Using $c_{pg} = 1.15 \text{ kJ/kg}\cdot\text{K}$ for the high-temperature combustion products:
$$f = \frac{(1.15 \cdot 1250) - (1.005 \cdot 627.0)}{43100 - (1.15 \cdot 1250)} = 0.0193$$

For every 1 kg of air, the engine consumes **0.0193 kg of fuel**.

---

## 3. Turbine-Compressor Matching

The turbine extracts work from the total mass flow ($\dot{m}_a + \dot{m}_f$). This work must equal the compressor work, adjusted for mechanical efficiency ($\eta_m = 0.99$).

**Specific Turbine Work ($w_t$):**
$$w_t = \frac{w_c}{(1+f)\eta_m} = \frac{340.54}{(1.0193)(0.99)} = 337.5 \text{ kJ/kg}$$

**Actual Turbine Exit Temperature ($T_{4a}$):**
$$T_{4a} = T_3 - \frac{w_t}{c_{pg}} = 1250 - \frac{337.5}{1.15} = 956.5 \text{ K}$$

**Exit Pressure ($P_4$):**
To find the pressure at the turbine exit, we calculate the isentropic exit temperature ($T_{4s}$) using turbine efficiency ($\eta_t = 0.90$):
$$T_{4s} = T_3 - \frac{T_3 - T_{4a}}{\eta_t} = 1250 - \frac{1250 - 956.5}{0.90} = 912.8 \text{ K}$$
Now find $P_4$:
$$P_4 = P_3 \left( \frac{T_{4s}}{T_3} \right)^{\frac{k}{k-1}} = 1110.6 \left( \frac{912.8}{1250} \right)^{3.5} = 371.4 \text{ kPa}$$

---

## 4. Nozzle Expansion and Thrust

The gas expands from $P_4$ to $P_{ambient}$ ($101.325$ kPa).

**Exit Temperature ($T_5$):**
$$T_5 = T_{4a} \left( \frac{P_1}{P_4} \right)^{\frac{k-1}{k}} = 956.5 \left( \frac{101.325}{371.4} \right)^{0.248} = 688.1 \text{ K}$$
*(Note: $k$ for exhaust gas is $\approx 1.33$)*

**Exit Velocity ($V_e$):**
Assuming a nozzle efficiency of **0.97**:
$$V_e = \sqrt{2 \cdot c_{pg} \cdot \eta_n \cdot (T_{4a} - T_5)}$$
$$V_e = \sqrt{2 \cdot 1150 \cdot 0.97 \cdot (956.5 - 688.1)} = 774 \text{ m/s}$$

**Thrust Calculation:**
For the J85-GE-21 air mass flow rate of **20 kg/s**:
$$F = (\dot{m}_a + \dot{m}_f)V_e = (20 + 0.386) \cdot 774 = 15,778 \text{ N}$$
**$F \approx 3,547$ lbf**

This confirms the dry thrust specification for the J85-GE-21 of approximately 3,500 lbf.

---

## 5. Performance Change: High Altitude Effects

At an altitude of 11,000m, ambient temperature drops to 216.7 K and pressure drops to 22.6 kPa.

* **Efficiency:** Lower inlet temperatures ($T_1$) mean the compressor requires less work to reach the same pressure ratio, which can improve thermal efficiency.
* **Thrust:** Because air density is much lower at altitude, the mass flow rate ($\dot{m}$) decreases. This results in a significant drop in total thrust despite high exit velocities.