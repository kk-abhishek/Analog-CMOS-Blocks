# 📡 CMOS Common Gate (CG) Amplifier

> **Analog VLSI Design Laboratory Experiment**
>
> Design and simulation of a CMOS Common Gate (CG) Amplifier with an NMOS input transistor operating in the common-gate configuration. The circuit is analyzed using DC and AC simulations to evaluate its voltage gain and frequency response.

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

The Common Gate (CG) Amplifier is a CMOS amplifier configuration where the input is applied at the source terminal while the gate is held at a fixed bias voltage. This experiment evaluates the amplifier through DC and AC analyses to study its non-inverting gain and frequency response.

---

# Objective

Design and simulate a CMOS Common Gate (CG) amplifier and analyze its:

- DC Characteristics
- AC Frequency Response

---

# Circuit Configuration

| Component | Description |
|-----------|-------------|
| **M1** | NMOS Input Transistor |
| **RD** | Resistive Drain Load |
| **Configuration** | Common Gate Amplifier |

> **Circuit Diagram**

Place the circuit schematic inside the **`schematics/`** directory.

---

# Design Specifications

| Parameter | Value |
|-----------|-------|
| Technology | CMOS 130 nm |
| NMOS (M1) | W/L = 10 µm / 2 µm |
| Drain Resistor (RD) | 10 kΩ |
| VDD | +2.5 V |
| VSS | -2.5 V |
| Gate Bias (Vb) | +2.5 V (DC) |

---

# Simulation Setup

### DC Analysis

| Parameter | Value |
|----------|-------|
| Input Sweep | -5 V → 20 V |

### AC Analysis

| Parameter | Value |
|----------|-------|
| Input Amplitude | 1 V |
| Frequency Range | 100 Hz → 5 GHz |

---

# Mathematical Equations

### Drain Current

```math
I_D=\frac{1}{2}\mu_nC_{ox}\left(\frac{W}{L}\right)(V_{GS}-V_{TN})^2(1+\lambda V_{DS})
```

### Output Resistance

```math
R_{out}\approx R_D
```

### Voltage Gain

```math
A_v=+g_{m1}R_D
```

---

# Expected Waveforms

### DC Analysis

- DC Transfer Characteristics (Vin vs Vout)

### AC Analysis

- Gain Plot
- Phase Plot (Bode Response)

---

# Simulation Results

- DC transfer curve shows output saturation as the NMOS enters the triode region.
- AC response exhibits a near-unity gain of approximately **−1.2 dB**.
- The amplifier demonstrates non-inverting, current-buffer-like behavior.
- The simulation verifies the expected operation of the Common Gate amplifier.

---

# Performance Summary

| Analysis | Observation |
|----------|-------------|
| DC | Output saturates in triode region |
| AC Gain | ≈ −1.2 dB |
| Phase Response | Stable |
| Configuration | Non-inverting |

---

# Tools Used

- Electric VLSI
- CMOS 130 nm Technology

---

# Repository Structure

```text
Common-Gate-Amplifier/
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