# 2.4 GHz PIFA Design and Optimization in Ansys HFSS

![Antenna Design](Images/antenna_geometry.png) ## 📌 Project Overview
This repository contains the complete design, high-frequency electromagnetic simulation, and performance optimization of a Planar Inverted-F Antenna (PIFA). Developed as part of the Numesys High Frequency Electromagnetics Training Camp, the project focuses on achieving precise impedance matching and optimal radiation characteristics for 2.4 GHz ISM band applications (such as Wi-Fi and Bluetooth).

The core objective was to tune the resonant frequency exactly to 2.4 GHz with a Return Loss (S11) of $\le$ -25 dB and a directivity/gain of approximately 4 dB.

## 🛠️ Design Specifications
* **Operating Frequency:** 2.4 GHz
* **Substrate Material:** Custom dielectric with relative permittivity ($\epsilon_r$) = 2.2
* **Conductor Material:** Perfect Electric Conductor (PEC)
* **Excitation:** 50 Ohm Lumped Port
* **Analysis Type:** Driven Modal (Modal Network)
* **Boundary Conditions:** Radiation boundary via 3D vacuum bounding box

## ⚙️ Optimization Methodology
The optimization primarily focused on adjusting the electrical length of the antenna (`Length1`). 
1. **Parametric Analysis:** A broad sweep of `Length1` from 2.2 cm to 2.8 cm (with 0.05 cm steps) was conducted to observe the resonance shift.
2. **Derivative Tuning:** Analytic Derivatives were utilized for real-time slider tuning without waiting for full simulation cycles.
3. **SNOPT Algorithm:** Applied for precise, goal-oriented optimization to lock the center frequency exactly at 2.4 GHz.

## 📊 Results: Initial vs. Optimized Design

### 1. Return Loss (S11)
The optimization successfully shifted the resonant frequency and drastically improved the impedance matching.
* **Initial Design (Length = 22.14 mm):** Resonated at 2.736 GHz. S11 at 2.4 GHz was only -6.01 dB.
* **Optimized Design (Length = 24.84 mm):** Perfect resonance at 2.4 GHz. S11 improved to **-34.34 dB**.

![S11 Comparison Graph](Images/s11_comparison.png) ### 2. Radiation Pattern & Gain
The dimension optimization preserved the wide-angle, balanced radiation characteristics of the PIFA structure while slightly increasing the peak realized gain.
* **Initial Peak Gain:** 3.97 dB
* **Optimized Peak Gain:** **4.01 dB**

![3D Radiation Pattern](Images/3d_gain_optimized.png) ## 🚀 Usage & Simulation
1. Clone this repository:
   ```bash
   git clone [https://github.com/YourUsername/your-repo-name.git](https://github.com/YourUsername/your-repo-name.git)
