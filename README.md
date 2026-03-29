# 01 - CMOS Inverter (TSMC 180nm)

## 📌 Project Overview
Design and DC analysis (Voltage Transfer Characteristics) of a fundamental CMOS Inverter using TSMC 180nm technology node in LTspice.

## ⚙️ Design Specifications
* **Technology Node:** 180nm
* **Power Supply (VDD):** 1.8V
* **PMOS Dimensions:** W = 1.08µm, L = 0.18µm
* **NMOS Dimensions:** W = 0.54µm, L = 0.18µm
* **Wp/Wn Ratio:** 2:1 (To compensate for lower hole mobility and center the switching threshold).

## 🖼️ Circuit Schematic
![CMOS Inverter Schematic](schematic.png)

## 📊 Simulation Results (VTC Curve)
![VTC Waveform](waveform.png)

### 💡 Key Observations
* Performed a DC Sweep from 0V to 1.8V.
* The switching threshold ($V_{th}$) is centered around **~0.9V** ($VDD/2$), validating the 2:1 sizing ratio for PMOS and NMOS.
* Achieved a sharp transition region (high gain), making it ideal for standard logic operations.
# Two-Stage CMOS Operational Amplifier (180nm Technology)

**Author:** ANKUSH RAI 
**Domain:** Analog VLSI Design  

## Project Overview
This project involves the transistor-level design and simulation of a Two-Stage CMOS Operational Amplifier using LTspice. The design is implemented using the TSMC 180nm technology node. The primary objective of this project is to understand and practically implement differential amplification, current mirroring, active loading, and negative feedback stability in a custom IC environment.

## Circuit Architecture
The Operational Amplifier is built using a modular approach, divided into four key stages:

1. **Biasing Network (Current Mirrors):** - A 10µA reference current source is mirrored using an NMOS current mirror (M1, M2, M8) to provide stable tail currents for the subsequent stages. Channel Length Modulation (CLM) effects were mitigated through optimized transistor sizing ($L=0.54µ m, W=5.4µ m$).

2. **First Stage (Differential Pair):** - Uses an NMOS differential pair (M3, M4) to accept the input voltages. It splits the 10µA tail current dynamically based on the differential input voltage.

3. **Active Load:** - A PMOS current mirror (M5, M6) acts as an active load for the differential pair. It converts the differential current into a single-ended voltage and provides high output impedance for the first stage gain.

4. **Second Stage (Common-Source Amplifier):** - A PMOS common-source amplifier (M7) loaded with an NMOS current sink (M8) provides the massive voltage gain required for the Op-Amp. 

## Design Specifications & DC Operating Point
- **Technology Node:** TSMC 180nm (`.model` Level 1 SPICE parameters)
- **Supply Voltage ($V_{DD}$):** 1.8V
- **Common Mode Input Voltage:** 0.9V
- **Tail Current:** ~10µA
- **Differential Branch Currents:** ~5µA
- **Output Stage Quiescent Current:** ~10µA

## Simulation Details
The circuit was simulated in LTspice. A `.op` (DC Operating Point) analysis was successfully conducted in a Unity Gain Buffer (Voltage Follower) configuration to establish the correct biasing points, mitigate systematic offset, and verify Kirchhoff's Current Law (KCL) across all nodes. The output node successfully tracked the 0.9V input reference.

## Tools Used
- **Schematic Capture & Simulation:** LTspice
- **Transistor Models:** TSMC 0.18µm CMOS SPICE Models
