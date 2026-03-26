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