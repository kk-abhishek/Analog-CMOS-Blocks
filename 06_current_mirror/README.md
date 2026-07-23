# 📡 CMOS Current Mirror Circuit

> **Analog VLSI Design Laboratory Experiment**
>
> Design and simulation of a CMOS PMOS Current Mirror driving an NMOS Common Source stage. The circuit is analyzed using DC, Transient, and AC simulations to verify current mirroring and amplifier performance.

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

The Current Mirror is a fundamental analog building block used to generate constant bias currents in integrated circuits. In this experiment, a PMOS current mirror supplies bias current to an NMOS Common Source amplifier. The circuit is evaluated using DC, Transient, and AC analyses.

---

# Objective

Design and simulate a CMOS PMOS Current Mirror and analyze its:

- Current Mirroring Operation
- DC Characteristics
- Transient Response
- AC Frequency Response

---

# Circuit Configuration

| Component | Description |
|-----------|-------------|
| **M1** | PMOS Mirror Output Transistor |
| **M2** | PMOS Diode-Connected Reference Transistor |
| **M3** | NMOS Common Source Output Stage |
| **Configuration** | PMOS 1:1 Current Mirror with CS Amplifier |

> **Circuit Diagram**

Place the circuit schematic inside the **`schematics/`** directory.

---

# Design Specifications

| Parameter | Value |
|-----------|-------|
| Technology | CMOS 130 nm |
| PMOS Reference (M2) | W/L = 10 µm / 0.4 µm |
| PMOS Mirror (M1) | W/L = 10 µm / 0.4 µm |
| NMOS (M3) | W/L = 2 µm / 0.4 µm |
| Mirror Ratio | 1 : 1 |
| Reference Current | 100 µA |
| VDD | +2.5 V |
| VSS | -2.5 V |

---

# Simulation Setup

### DC Analysis

| Parameter | Value |
|----------|-------|
| Input | DC Sweep |

### Transient Analysis

| Parameter | Value |
|----------|-------|
| Input Signal | Sine Wave |

### AC Analysis

| Parameter | Value |
|----------|-------|
| Input Amplitude | 2 V |
| Frequency Range | 100 Hz → 100 GHz |

---

# Mathematical Equations

### Reference Current

```math
I_{ref}=\frac{1}{2}\mu_pC_{ox}\left(\frac{W}{L}\right)_{ref}(V_{SG}-|V_{TP}|)^2(1+\lambda V_{SD,ref})
```

### Current Mirror Ratio

```math
\frac{I_{out}}{I_{ref}}
=
\frac{(W/L)_{out}}{(W/L)_{ref}}
```

### Output Current

```math
I_{out}
=
I_{ref}
\left(
\frac{(W/L)_{out}}
{(W/L)_{ref}}
\right)
\left(
\frac{1+\lambda V_{DS,out}}
{1+\lambda V_{DS,ref}}
\right)
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

- The PMOS transistors form a **1:1 current mirror**, producing an output current approximately equal to **100 µA**.
- The NMOS Common Source stage amplifies the input signal around the mirrored bias point.
- AC response exhibits a gain of approximately **36–40 dB** at low frequencies.
- Gain begins to roll off beyond **10 MHz**, confirming proper current mirror operation.

---

# Performance Summary

| Analysis | Observation |
|----------|-------------|
| Mirror Ratio | 1 : 1 |
| Output Current | ≈100 µA |
| AC Gain | ≈36–40 dB |
| Bandwidth | Roll-off after ≈10 MHz |

---

# Tools Used

- Electric VLSI
- CMOS 130 nm Technology

---

# Repository Structure

```text
Current-Mirror/
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

This project is part of the **Analog VLSI Design Laboratory**.