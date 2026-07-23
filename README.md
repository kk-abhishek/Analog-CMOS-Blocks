# VLSI CMOS Amplifier Design & Simulation Lab

Design, schematic capture, and SPICE-level simulation (DC / Transient / AC) of seven fundamental CMOS analog building blocks — implemented in **Electric VLSI Design System** with **LTspice/ngspice/HSPICE**, targeting a **130 nm CMOS** process.

> M.Tech VLSI Design | UVCE, Bangalore

---

## 📋 Overview

This repository documents the complete design flow — from schematic to simulation results — for the following amplifier topologies:

| # | Experiment | Type |
|---|------------|------|
| 01 | Common Source (CS) Amplifier | Single-stage, PMOS-driven |
| 02 | Common Gate (CG) Amplifier | Single-stage, resistive load |
| 03 | Common Drain (CD) Amplifier | Source follower |
| 04 | Cascode Amplifier | CS + CG stacked |
| 05 | Differential Amplifier | 5-transistor, current-mirror load |
| 06 | Current Mirror | PMOS reference/mirror pair |
| 07 | Two-Stage Op-Amp | Diff. Amp + CS gain stage |

Each blocks includes its schematic, SPICE netlist, and DC/Transient/AC simulation results.

---

## 🗂️ Repository Structure

```
vlsi-cmos-amplifier-lab/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── docs/                                
│   ├── CMOS_Amplifiers_Result.pdf   # Cover/summary figures used 
│                          
│
├── tech/
│   └── 130micron.txt                    # Process/device model file (.include)
│
├── 01_common_source_amplifier/
│   ├── schematic/                       # Electric VLSI library / exported schematic image
│   ├── spice/
│   │   ├── CS_amp.spi                   # DC + Transient netlist
│   │   └── CS_amp_ac.spi                # AC netlist
│   ├── results/
│   │   ├── dc_transfer.png
│   │   ├── transient.png
│   │   └── ac_bode.png
│   └── README.md                        # Aim, design params, equations, result (per experiment)
│
├── 02_common_gate_amplifier/
│   ├── schematic/
│   ├── spice/
│   ├── results/
│   └── README.md
│
├── 03_common_drain_amplifier/
│   ├── schematic/
│   ├── spice/
│   ├── results/
│   └── README.md
│
├── 04_cascode_amplifier/
│   ├── schematic/
│   ├── spice/
│   ├── results/
│   └── README.md
│
├── 05_differential_amplifier/
│   ├── schematic/
│   ├── spice/
│   ├── results/
│   └── README.md
│
├── 06_current_mirror/
│   ├── schematic/
│   ├── spice/
│   ├── results/
│   └── README.md
│
└── 07_two_stage_opamp/
    ├── schematic/
    ├── spice/
    ├── results/
    └── README.md
```

**Naming convention:** each experiment folder is prefixed `NN_` to preserve order, and contains its own `schematic/`, `spice/`, `results/`, and a short `README.md` (Aim → Design Parameters → Equations → Circuit → Waveforms → Result), mirroring the exam-prep sheet in `docs/`.

---

## 🛠️ Tools & Technology

| Tool | Purpose |
|---|---|
| **Electric VLSI Design System** | Schematic capture |
| **ngspice** | DC, Transient & AC simulation |
| **130 nm CMOS PDK** (`130micron.txt`) | Device models |

---

## ⚙️ How to Run a Simulation

```bash
# from any experiment's spice/ folder
ngspice <netlist>.spi
```

Each `.spi` file already includes the process file via:
```spice
.include "130micron.txt"
```
Update the path in each netlist to point to `tech/130micron.txt` relative to your local clone before running.

| Analysis | Netlist suffix | Example command inside ngspice |
|---|---|---|
| DC Sweep | `_dc` or default `.spi` | `run` → `plot v(vout)` |
| Transient | same file, `.tran` line uncommented | `run` → `plot v(vin) v(vout)` |
| AC / Bode | `_ac.spi` | `run` → `plot db(v(vout))` |

---

## 📐 Design Summary

| Experiment | Key Devices | Supply | Approx. Gain |
|---|---|---|---|
| CS Amplifier | PMOS 10µ/0.4µ, NMOS 2µ/0.4µ | ±2.5 V | ≈ 24 dB |
| CG Amplifier | NMOS 10µ/2µ, R_D = 10 kΩ | ±2.5 V | ≈ −1.2 dB (≈ unity) |
| CD Amplifier | NMOS 10µ/0.4µ + 2µ/0.4µ | ±2.5 V | ≈ 4.6 dB (≈ unity) |
| Cascode Amplifier | 2× NMOS 10µ/0.4µ, R_D = 10 kΩ | 2.5 V / 0 V | ≈ 4 dB |
| Differential Amplifier | NMOS 3µ, PMOS 15µ, tail 30 µA | ±2.5 V | ≈ −14 dB |
| Current Mirror | PMOS 10µ/0.4µ (1:1), I_ref = 100 µA | ±2.5 V | ≈ 36–40 dB |
| Two-Stage Op-Amp | Diff. Amp + CS stage | ±2.5 V | ≈ 24 dB |

*(Full derivations, equations, and expected waveforms are in `docs/VLSI_Amplifiers_Lab_Exam_Prep.pdf`.)*

---

## 📚 Reference Material

The experiments, circuit design methodology, simulation procedures, and theoretical concepts presented in this repository are based on the following reference:

- Behzad Razavi, *Design of Analog CMOS Integrated Circuits*, McGraw-Hill Education, First Edition.

---

## ✅ .gitignore (suggested)

```
*.bak
*.lock
*.tmp
*.jelib~
.DS_Store
```

---

## 📄 License

Add a license of your choice (e.g. MIT) if you intend the repo to be public and reusable. Academic/coursework repos are often kept unlicensed or under **MIT** for simplicity.

---

## 🙋 Author

**KK** — M.Tech VLSI Design, ECE Dept., UVCE, Bangalore (2025–2027)
