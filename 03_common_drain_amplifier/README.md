# 📡 CMOS Common Drain (CD) / Source Follower Amplifier

> **Analog VLSI Design Laboratory Experiment**
>
> Design and simulation of a CMOS Common Drain (CD) Amplifier, also known as a Source Follower. The circuit is analyzed using DC, Transient, and AC simulations to study its voltage buffering characteristics and low output impedance.

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

The Common Drain (CD) Amplifier, commonly known as the Source Follower, provides high input impedance, low output impedance, and a voltage gain close to unity. This experiment evaluates its performance through DC, Transient, and AC analyses.

---

# Objective

Design and simulate a CMOS Common Drain (Source Follower) amplifier and analyze its:

- DC Characteristics
- Transient Response
- AC Frequency Response

---

# Circuit Configuration

| Component | Description |
|-----------|-------------|
| **M1** | NMOS Input Transistor |
| **M2** | NMOS Tail / Load Transistor |
| **Configuration** | Source Follower (Common Drain) |

> **Circuit Diagram**

Place the circuit schematic inside the **`schematics/`** directory.

---

# Design Specifications

| Parameter | Value |
|-----------|-------|
| Technology | CMOS 130 nm |
| NMOS (M1) | W/L = 10 µm / 0.4 µm |
| NMOS (M2) | W/L = 2 µm / 0.4 µm |
| VDD | +2.5 V |
| VSS | -2.5 V |
| Bias Voltage | 0.5 V (DC) |

---

# Simulation Setup

### DC Analysis

| Parameter | Value |
|----------|-------|
| Input Sweep | -5 V → 5 V |

### Transient Analysis

| Parameter | Value |
|----------|-------|
| Input Signal | Sine Wave |
| Amplitude | 0.4 V |
| Frequency | 1 kHz |

### AC Analysis

| Parameter | Value |
|----------|-------|
| Input Amplitude | 2 V |
| Frequency Range | 100 Hz → 100 GHz |

---

# Mathematical Equations

### Drain Current

```math
I_D=\frac{1}{2}\mu_nC_{ox}\left(\frac{W}{L}\right)(V_{GS}-V_{TN})^2(1+\lambda V_{DS})
```

### Output Resistance

```math
R_{out}\approx\frac{1}{g_{m1}}
```

### Voltage Gain

```math
A_v=\frac{g_{m1}}{g_{m1}+\frac{1}{r_{o1}}+\frac{1}{r_{o2}}}\approx1
```

---

# Expected Waveforms

### DC Analysis

- DC Transfer Characteristics

### Transient Analysis

- Input and output sinusoidal waveforms

### AC Analysis

- Gain Plot
- Phase Plot (Bode Response)

---

# Simulation Results

- DC transfer follows **Vout ≈ Vin − VGS**, confirming voltage follower operation.
- Transient response shows the output following the input with minimal distortion.
- AC response exhibits a nearly constant gain of approximately **4.6 dB (≈1.7 V/V)**.
- The circuit provides low output impedance and wide bandwidth, as expected from a Source Follower.

---

# Performance Summary

| Analysis | Observation |
|----------|-------------|
| DC | Output follows input |
| Transient | Buffered sinusoidal output |
| AC Gain | ≈ 4.6 dB |
| Output Impedance | Low |

---

# Tools Used

- Electric VLSI
- CMOS 130 nm Technology

---

# Repository Structure

```text
Common-Drain-Amplifier/
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