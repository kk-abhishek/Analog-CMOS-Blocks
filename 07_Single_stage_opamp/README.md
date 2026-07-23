# 📡 CMOS Two-Stage Operational Amplifier

> **Analog VLSI Design Laboratory Experiment**
>
> Design and simulation of a CMOS Two-Stage Operational Amplifier consisting of a Differential Amplifier followed by a Common Source amplifier. The circuit is analyzed using DC, Transient, and AC simulations to evaluate its overall voltage gain and frequency response.

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

The Two-Stage CMOS Operational Amplifier consists of a Differential Amplifier as the first stage and a Common Source amplifier as the second stage. This configuration provides higher overall voltage gain and serves as the basic architecture for many analog integrated circuits. The amplifier is analyzed through DC, Transient, and AC simulations.

---

# Objective

Design and simulate a CMOS Two-Stage Operational Amplifier and analyze its:

- DC Characteristics
- Transient Response
- AC Frequency Response

---

# Circuit Configuration

| Component | Description |
|-----------|-------------|
| **Stage 1** | CMOS Differential Amplifier |
| **Stage 2** | Common Source Amplifier |
| **Configuration** | Two-Stage CMOS Operational Amplifier |

> **Circuit Diagram**

Place the circuit schematic inside the **`schematics/`** directory.

---

# Design Specifications

| Parameter | Value |
|-----------|-------|
| Technology | CMOS 130 nm |
| Stage 1 (NMOS Input) | W = 3 µm |
| Stage 1 (PMOS Load) | W = 15 µm |
| Tail Current | 30 µA |
| Stage 2 PMOS | W/L = 10 µm / 0.4 µm |
| Stage 2 NMOS | W/L = 2 µm / 0.4 µm |
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
| Input Signal | 2 mV Sine Wave |
| Frequency | 1 kHz |
| Reference Input | 0 V |

### AC Analysis

| Parameter | Value |
|----------|-------|
| Input Amplitude | 2 mV |
| Frequency Response | Bode Analysis |

---

# Mathematical Equations

### Stage 1 Drain Current

```math
I_{D1}=I_{D2}
=
\frac{I_{TAIL}}{2}
=
\frac{1}{2}\mu_nC_{ox}
\left(\frac{W}{L}\right)
(V_{GS}-V_{TN})^2
(1+\lambda V_{DS})
```

### Stage 2 Drain Current

```math
I_D
=
\frac{1}{2}\mu_pC_{ox}
\left(\frac{W}{L}\right)
(V_{SG}-|V_{TP}|)^2
(1+\lambda V_{DS})
```

### Output Resistance

```math
R_{out}
=
r_{o(\mathrm{NMOS})}
\parallel
r_{o(\mathrm{PMOS})}
```

### Overall Voltage Gain

```math
A_v
=
A_{v1}\times A_{v2}
=
(g_{m1}R_{out1})
(g_{m2}R_{out2})
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

- The cascaded Differential Amplifier and Common Source stage provide an overall gain of approximately **24 dB**.
- The transient response shows an amplified output with a DC bias of approximately **1.81 V**.
- The AC response remains flat over the low-frequency region before rolling off near **1 MHz**.
- The simulation confirms the correct operation of the CMOS Two-Stage Operational Amplifier.

---

# Performance Summary

| Analysis | Observation |
|----------|-------------|
| DC | Stable operating point |
| Transient | Amplified output with ≈1.81 V bias |
| AC Gain | ≈24 dB |
| Bandwidth | Roll-off near 1 MHz |

---

# Tools Used

- Electric VLSI
- CMOS 130 nm Technology

---

# Repository Structure

```text
Two-Stage-Operational-Amplifier/
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