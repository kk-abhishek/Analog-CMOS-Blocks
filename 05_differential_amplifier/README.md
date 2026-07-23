# 📡 CMOS Differential Amplifier

> **Analog VLSI Design Laboratory Experiment**
>
> Design and simulation of a 5-Transistor CMOS Differential Amplifier consisting of an NMOS differential input pair, PMOS current mirror load, and NMOS tail current source. The circuit is analyzed using DC, Transient, and AC simulations to evaluate its differential amplification characteristics.

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

The Differential Amplifier is one of the most important analog building blocks used in operational amplifiers and integrated circuits. It amplifies the voltage difference between two input signals while rejecting common-mode signals. This experiment evaluates its DC, Transient, and AC characteristics.

---

# Objective

Design and simulate a CMOS Differential Amplifier and analyze its:

- DC Characteristics
- Transient Response
- AC Frequency Response

---

# Circuit Configuration

| Component | Description |
|-----------|-------------|
| **M1, M2** | NMOS Differential Input Pair |
| **M3, M4** | PMOS Current Mirror Load |
| **M5** | NMOS Tail Current Source |
| **Configuration** | Five-Transistor Differential Amplifier |

> **Circuit Diagram**

Place the circuit schematic inside the **`schematics/`** directory.

---

# Design Specifications

| Parameter | Value |
|-----------|-------|
| Technology | CMOS 130 nm |
| NMOS Input Pair (M1, M2) | W = 3 µm |
| PMOS Mirror Load (M3, M4) | W = 15 µm |
| NMOS Tail Source (M5) | W = 4.5 µm |
| Tail Current | 30 µA |
| VDD | +2.5 V |
| VSS | -2.5 V |

---

# Simulation Setup

### DC Analysis

| Parameter | Value |
|----------|-------|
| Input | Differential DC Sweep |

### Transient Analysis

| Parameter | Value |
|----------|-------|
| V1 | 5 mV Sine Wave |
| V2 | 0 V (DC Reference) |
| Frequency | 1 kHz |

### AC Analysis

| Parameter | Value |
|----------|-------|
| Input Amplitude | 2 V |
| Frequency Range | 100 Hz → 5 GHz |

---

# Mathematical Equations

### Drain Current

```math
I_{D1}=I_{D2}=\frac{I_{TAIL}}{2}
=\frac{1}{2}\mu_nC_{ox}\left(\frac{W}{L}\right)(V_{GS}-V_{TN})^2(1+\lambda V_{DS})
```

### Output Resistance

```math
R_{out}=r_{o(\mathrm{NMOS})}\parallel r_{o(\mathrm{PMOS})}
```

### Differential Mode Gain

```math
A_{dm}=g_{m1}R_{out}
```

---

# Expected Waveforms

### DC Analysis

- Differential DC Transfer Characteristics

### Transient Analysis

- Amplified differential sinusoidal output

### AC Analysis

- Gain Plot
- Phase Plot (Bode Response)

---

# Simulation Results

- DC transfer curve exhibits the characteristic differential switching behavior near the supply rails.
- Transient response confirms proper amplification with a DC bias point of approximately **1.6 V**.
- AC response provides a low-frequency gain of approximately **−14 dB**.
- Gain begins to roll off beyond **10 MHz**, confirming the expected behavior of the differential amplifier.

---

# Performance Summary

| Analysis | Observation |
|----------|-------------|
| DC | Differential switching characteristic |
| Transient | Amplified output with 1.6 V bias |
| AC Gain | ≈ −14 dB |
| Bandwidth | Roll-off after ≈10 MHz |

---

# Tools Used

- Electric VLSI
- CMOS 130 nm Technology

---

# Repository Structure

```text
Differential-Amplifier/
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