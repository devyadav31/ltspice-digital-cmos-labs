# Transistor-Level Digital VLSI Design (180nm)

## Overview
This repository contains transistor-level schematics and simulation analyses for various digital logic architectures designed at the 180nm CMOS technology node. The project evaluates and compares different logic families based on Voltage Transfer Characteristics (VTC), propagation delay, and static power dissipation. 

All simulations were performed using **LTSpice** to validate theoretical concepts against analog circuit behavior.

## Technologies & Tools
* **EDA Tool:** LTSpice
* **Technology Node:** 180nm CMOS 
* **Simulation Types:** DC Sweep, Transient Analysis, Operating Point Analysis

## Core Logic Implementations

### 1. Standard CMOS & Pseudo-NMOS Inverters
* **CMOS:** Established the baseline performance for noise margins, symmetric rising/falling delays, and zero static power dissipation.
* **Pseudo-NMOS (`DVD_8.asc`):** Evaluated the trade-offs of ratioed logic. Analyzed the static power dissipation inherent when the pull-down network is active and the reduction in input capacitance compared to standard CMOS.

### 2. Advanced Topologies: DCVSL & TGL
* **Differential Cascode Voltage Switch Logic (DCVSL):** Designed and simulated differential logic structures to observe improvements in propagation delay and logic density at the cost of routing complexity.
* **Transmission Gate Logic (TGL):** Implemented pass-transistor logic to design efficient multiplexing and switching pathways.

## Key Performance Analyses

### Voltage Transfer Characteristics (VTC)
DC sweeps were performed to extract the switching threshold voltages ($V_{M}$) and calculate the High/Low Noise Margins ($NM_{H}$, $NM_{L}$) for the implemented logic gates.

*(Replace this line with your VTC waveform image)*
`![VTC Waveform](./waveforms/VTC_Analysis.png)`

### Propagation Delay & Transient Analysis
Transient simulations were executed to measure $t_{pHL}$ and $t_{pLH}$, allowing for the calculation of the overall propagation delay and the observation of dynamic power consumption during switching events.

*(Replace this line with your transient delay image)*
`![Transient Analysis](./waveforms/Transient_Delay.png)`

## Advanced Implementation: 8-Transistor Clocked SR Latch
**File:** `dvd_9.asc`

Engineered a clocked SR Latch to analyze dynamic logic gate behavior and state retention. 
* **Design Challenge:** Addressed charge leakage at the dynamic storage node during the evaluate phase.
* **Solution:** Successfully mitigated leakage and stabilized the logic levels by implementing bleeder transistors, ensuring reliable state retention even at lower switching frequencies.

*(Replace this line with your SR Latch waveform image)*
`![SR Latch Waveform](./waveforms/SR_Latch_Bleeder.png)`

## How to Run the Simulations
1. Clone this repository to your local machine.
2. Ensure **LTSpice** is installed.
3. Verify that the 180nm technology library text file is located in your working directory or correctly linked in the `.asc` schematic files.
4. Open any `.asc` file (e.g., `CMOS Inverter.asc`) in LTSpice and click **Run**.
