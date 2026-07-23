# 📡 CMOS Cascode Amplifier

> **Analog VLSI Design Laboratory Experiment**
>
> Design and simulation of a CMOS Cascode Amplifier by cascading a Common Source (CS) stage with a Common Gate (CG) stage. The circuit is analyzed using DC, Transient, and AC simulations to study its high output resistance and improved voltage gain.

---

## 📖 Table of Contents

- [Overview](#overview)
- [Objective](#objective)
- [Circuit Configuration](#circuit-configuration)
- [Design Specifications](#design-specifications)
- [Simulation Setup](#simulation-setup)
- [Mathematical Equations](#mathematical-equations)
- [Expected Waveforms](#expected-waveforms)
- [Simulation Results](#simulation-results)
- [Tools Used](#tools-used)
- [Repository Structure](#repository-structure)

---

# Overview

The Cascode Amplifier combines a Common Source stage with a Common Gate stage to achieve higher output resistance, improved voltage gain, and enhanced frequency performance. This experiment evaluates the amplifier through DC, Transient, and AC analyses.

---

# Objective

Design and simulate a CMOS Cascode amplifier and analyze its:

- DC Characteristics
- Transient Response
- AC Frequency Response

---

# Circuit Configuration

| Component | Description |
|-----------|-------------|
| **M1** | NMOS Common Source Transistor |
| **M2** | NMOS Cascode (Common Gate) Transistor |
| **RD** | Drain Load Resistor |
| **Configuration** | Cascode Amplifier (CS + CG) |

> **Circuit Diagram**

Place the circuit schematic inside the **`schematics/`** directory.

---

# Design Specifications

| Parameter | Value |
|-----------|-------|
| Technology | CMOS 130 nm |
| M1 (CS) | W/L = 10 µm / 0.4 µm |
| M2 (CG) | W/L = 10 µm / 0.4 µm |
| RD | 10 kΩ |
| VDD | +2.5 V |
| VSS | 0 V |
| Gate Bias (Vb) | +2.5 V (DC) |

---

# Simulation Setup

### DC Analysis

| Parameter | Value |
|----------|-------|
| Input Sweep | -5 V → 20 V |

### Transient Analysis

| Parameter | Value |
|----------|-------|
| Input Signal | Sine Wave |
| Amplitude | 5 mV |
| Frequency | 1 kHz |

### AC Analysis

| Parameter | Value |
|----------|-------|
| Input Amplitude | 2 V |
| Frequency Range | 1 Hz → 1 THz |

---

# Mathematical Equations

### Drain Current

```math
I_D=\frac{1}{2}\mu_nC_{ox}\left(\frac{W}{L}\right)(V_{GS}-V_{TN})^2(1+\lambda V_{DS})
```

### Output Resistance

```math
R_{out}=(g_{m2}r_{o2}r_{o1})\parallel R_D
```

### Voltage Gain

```math
A_v=-g_{m1}R_{out}
```

---

# Expected Waveforms

### DC Analysis

- DC Transfer Characteristics

### Transient Analysis

- Amplified sinusoidal output

### AC Analysis

- Gain Plot
- Phase Plot (Bode Response)

---

# Simulation Results

- DC transfer curve exhibits a sharp transition near **1 V**, indicating the amplifier's operating region.
- Transient response follows the input sinusoid with a nearly constant DC offset.
- AC response provides a flat gain of approximately **4 dB** before rolling off near **1 GHz**.
- The amplifier demonstrates increased output resistance due to the cascode configuration, while the resistive load limits the overall gain.

---

# Performance Summary

| Analysis | Observation |
|----------|-------------|
| DC | Sharp transition near 1 V |
| Transient | Amplified sine wave with DC offset |
| AC Gain | ≈ 4 dB |
| Bandwidth | Roll-off near 1 GHz |

---

# Tools Used

- Electric VLSI
- CMOS 130 nm Technology

---

# Repository Structure

```text
Cascode-Amplifier/
│
├── README.md
├── schematics/
└── result/
    ├── dc_analysis/
    ├── transient_analysis/
    └── ac_analysis/
```

---

# Author

**Abhishek KK**



---

## License

This project is part of the **Analog VLSI Design Laboratory** .