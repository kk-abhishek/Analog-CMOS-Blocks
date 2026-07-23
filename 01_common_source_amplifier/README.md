# 📡 CMOS Common Source (CS) Amplifier

> **Analog VLSI Design Laboratory Experiment**
>
> Design and simulation of a CMOS Common Source (CS) Amplifier using a PMOS input transistor and an NMOS active load, followed by DC, Transient, and AC performance analysis.

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

The Common Source (CS) Amplifier is one of the fundamental CMOS amplifier configurations. In this experiment, a PMOS transistor acts as the input device while an NMOS transistor functions as the active load. The circuit is analyzed through DC, Transient, and AC simulations to evaluate its voltage gain and frequency response.

---

# Objective

Design and simulate a CMOS Common Source (CS) amplifier and analyze its:

- DC Characteristics
- Transient Response
- AC Frequency Response

---

# Circuit Configuration

| Component | Description |
|-----------|-------------|
| **M1** | PMOS Input Transistor |
| **M2** | NMOS Active Load |
| **Configuration** | Current Source Loaded Common Source Amplifier |

> **Circuit Diagram**

Place the circuit schematic inside the **`schematics/`** directory.

---

# Design Specifications

| Parameter | Value |
|-----------|-------|
| Technology | CMOS 130 nm |
| PMOS (M1) | W/L = 10 µm / 0.4 µm |
| NMOS (M2) | W/L = 2 µm / 0.4 µm |
| VDD | +2.5 V |
| VSS | -2.5 V |
| Bias Voltage | 2.5 V (DC) |

---

# Simulation Setup

### DC Analysis

| Parameter | Value |
|----------|-------|
| Input Sweep | -2.5 V → 20 V |

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
| Frequency Range | 100 Hz → 500 GHz |

---

# Mathematical Equations

### Drain Current

```math
I_D=\frac{1}{2}\mu_pC_{ox}\left(\frac{W}{L}\right)(V_{SG}-|V_{TP}|)^2(1+\lambda V_{DS})
```

### Output Resistance

```math
R_{out}=r_{o1}\parallel r_{o2}
```

### Voltage Gain

```math
A_v=-g_{m1}R_{out}
```

---

# Expected Waveforms

### DC Analysis

- DC Transfer Characteristics (Vin vs Vout)

### Transient Analysis

- Inverted amplified sinusoidal output

### AC Analysis

- Gain Plot
- Phase Plot (Bode Response)

---

# Simulation Results

- Switching region observed approximately between **0 V and 2 V** input.
- Transient response confirms an inverted amplified sinusoidal output.
- AC response exhibits a flat gain of approximately **24 dB**.
- The **−3 dB** cutoff frequency lies in the **hundreds of MHz** range.
- The simulation confirms proper Common Source amplifier operation.

---

# Performance Summary

| Analysis | Observation |
|----------|-------------|
| DC | Switching region near 0–2 V |
| Transient | Inverted amplified sine wave |
| AC Gain | ≈ 24 dB |
| Bandwidth | Hundreds of MHz |

---

# Tools Used

- Electric VLSI
- CMOS 130 nm Technology

---

# Repository Structure

```text
Common-Source-Amplifier/
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