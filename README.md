# 2.4 GHz PIFA (Planar Inverted-F Antenna) Design & Optimization in Ansys HFSS

## 📌 Overview
[cite_start]This repository contains the design, high-frequency electromagnetic simulation, and performance optimization of a Planar Inverted-F Antenna (PIFA)[cite: 8]. [cite_start]Designed for 2.4 GHz ISM band applications (such as Wi-Fi and Bluetooth), this project was developed as part of the Numesys Training Camp - High Frequency Electromagnetics Class[cite: 1, 2].

[cite_start]The primary objective was to achieve an impedance match with a return loss (S11) of $\le$ -25 dB and a directivity/gain of approximately 4 dB at the targeted 2.4 GHz center frequency[cite: 10, 11, 12].

## 🛠️ Design Specifications & Materials
* [cite_start]**Operating Frequency:** 2.4 GHz [cite: 10]
* [cite_start]**Substrate Material:** Custom dielectric with relative permittivity $\epsilon_r = 2.2$ [cite: 18]
* [cite_start]**Conductors:** Antenna radiating arms and ground plane are modeled as Perfect Electric Conductor (PEC) [cite: 19, 22]
* [cite_start]**Excitation:** 50 Ohm Lumped Port [cite: 24]
* [cite_start]**Radiation Boundary:** A 3D vacuum bounding box to simulate free-space radiation [cite: 20, 23]

## ⚙️ Simulation Setup
* [cite_start]**Solution Type:** Driven Modal (Modal Network) [cite: 26]
* [cite_start]**Frequency Sweep:** 1.2 GHz to 3.6 GHz [cite: 27]
* [cite_start]**Sweep Type:** Interpolating Sweep with 401 linear count points to accurately capture the resonance dip [cite: 28]

## 📊 Optimization Process
The main optimization variable was the electrical length of the antenna (`Length1`). 
1. [cite_start]**Initial Design:** The starting length was set to 22.14 mm[cite: 14]. [cite_start]The initial simulation yielded a resonance at 2.736 GHz with an S11 of -13.39 dB, missing the 2.4 GHz target[cite: 34].
2. [cite_start]**Parametric Analysis:** A sweep was conducted for `Length1` from 2.2 cm to 2.8 cm with a step size of 0.05 cm to observe the shift in resonance[cite: 37].
3. [cite_start]**Derivative Tuning & SNOPT:** Analytic Derivatives and tuning sliders were used for real-time observation [cite: 42, 43][cite_start], followed by the SNOPT algorithm to precisely find the optimal length[cite: 15, 65].

## 🏆 Final Results: Initial vs. Optimized Design

### 1. Return Loss (S11) Comparison
The optimization successfully shifted the center frequency to exactly 2.4 GHz while drastically improving the impedance match.
* [cite_start]**Initial S11 (Length = 22.14 mm):** -6.01 dB at 2.4 GHz [cite: 45] [cite_start](Resonating at 2.736 GHz [cite: 34])
* [cite_start]**Optimized S11 (Length = 24.84 mm):** -34.34 dB at 2.4 GHz [cite: 46, 65]

> 🖼️ *[ÖNERİ: Buraya sunumundaki "Comparison S Parameters" (Yeşil ve Kırmızı çizgili) grafiğini ekle]*
> `![S11 Comparison](Results/s11_comparison.png)`

### 2. Radiation Pattern & Gain
[cite_start]The dimension optimization preserved the wide-angle, balanced radiation characteristics typical of a PIFA, while slightly improving the maximum gain[cite: 50, 51].
* [cite_start]**Initial Maximum Gain:** 3.97 dB [cite: 48, 51]
* [cite_start]**Optimized Maximum Gain:** 4.01 dB [cite: 49, 51, 59]

> 🖼️ *[ÖNERİ: Buraya sunumundaki "Gain Plot2" (Maksimum 4.01 olan) 3D ışıma grafiğini ekle]*
> `![3D Radiation Pattern](Results/3d_gain_optimized.png)`

## 🚀 How to Open the Project
1. Clone this repository to your local machine.
2. Open **Ansys HFSS** (Created with version 2025 R2 Student).
3. Open the `.aedt` project file.
4. Run the validation check and analyze the `Setup_Tuning` or initial setups to view the reports.

---
[cite_start]*Developed by Enver Gökay ÇAY [cite: 4]*