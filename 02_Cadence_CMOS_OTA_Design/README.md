02_Cadence_CMOS_OTA_Design/README.md

# Project Overview:
This project presents a complete full-custom CMOS Operational Transconductance Amplifier (OTA) design using Cadence Virtuoso. The design follows an analog IC workflow from transistor-level schematic design to simulation, physical layout, DRC/LVS verification, full-circuit integration, and post-layout validation.
The OTA is implemented as a single-stage symmetrical current-mirror OTA in a 180 nm-class 2 V CMOS process. The design includes a differential input pair, PMOS current-mirror loads, NMOS output mirrors, a tail current source, and a dedicated bias-current generation network.
This project demonstrates practical analog/RF IC design capability, including schematic-level analysis, operating-point verification, large-signal transient behaviour, layout-aware design, verification sign-off, and measurement-aware silicon-validation planning.

# Objective:
The objective of this project was to design and verify a stable CMOS OTA suitable for analog and mixed-signal applications. The design goal was to realize a single-stage OTA with sufficient DC gain, unity-gain bandwidth in the tens of MHz range, stable closed-loop behaviour, and a physical layout that passes DRC/LVS verification.

# The project focuses on:
•	Transistor-level CMOS OTA design
•	Bias-current generation
•	Small-signal gain and phase analysis
•	Unity-gain bandwidth and phase-margin verification
•	DC operating-point validation
•	Slew-rate and settling-time analysis
•	Input common-mode range and output swing characterization
•	Matching-aware physical layout
•	DRC/LVS verification
•	Post-layout parasitic-aware validation
•	Measurement methodology for silicon validation

## Repository Structure

```text
Cadence_CMOS_OTA_Design/
│
├── README.md
│
├── docs/
│   └── CMOS_OTA_Design_Cadence_Virtuoso_Report.pdf
│
├── figures/
│   ├── schematic/
│   ├── ac_analysis/
│   ├── dc_operating_point/
│   ├── transient/
│   ├── common_mode_output_swing/
│   ├── layout/
│   ├── drc_lvs/
│   └── post_layout/
│
├── schematics/
│   └── screenshots/
│
├── layout/
│   └── screenshots/
│
├── simulation_results/
│   ├── ac_response/
│   ├── dc_operating_point/
│   ├── slew_settling/
│   ├── common_mode_range/
│   └── post_layout/
│
├── verification/
│   ├── drc/
│   └── lvs/
│
└── notes/
    ├── measurement_methodology.md
    └── result_traceability.md
```


# Design Flow:
Transistor-Level OTA Schematic
        ↓
Bias-Current Generation Network
        ↓
DC Operating-Point Verification
        ↓
Small-Signal AC Gain and Phase Analysis
        ↓
Unity-Gain Bandwidth and Phase-Margin Extraction
        ↓
Large-Signal Slew-Rate and Settling Verification
        ↓
Input Common-Mode Range and Output Swing Analysis
        ↓
Physical Layout with Matching-Aware Placement
        ↓
DRC and LVS Verification
        ↓
Post-Layout Simulation with Extracted Parasitics
        ↓
Measurement Methodology and Silicon-Validation Plan

# Key Results :
| Parameter              |              Result | Interpretation                                                      |
| ---------------------- | ------------------: | ------------------------------------------------------------------- |
| DC gain                |          ≈ 24.85 dB | Open-loop low-frequency gain                                        |
| Unity-gain bandwidth   |          ≈ 14.6 MHz | Frequency where the open-loop gain crosses 0 dB                     |
| Phase at unity gain    |           ≈ −106.7° | Phase value at the unity-gain frequency                             |
| Phase margin           |               ≈ 73° | Indicates stable unity-gain feedback behaviour                      |
| Slew rate              |         ≈ 15.7 V/µs | Large-signal rising-edge slope from transient response              |
| DRC                    |        0 violations | Layout satisfies design-rule checks                                 |
| LVS                    |        0 mismatches | Layout matches schematic connectivity                               |
| Post-layout validation | Meets design intent | Extracted-layout simulation confirms the expected performance trend |

# Skills Demonstrated: 
This project demonstrates practical capability in:
•	CMOS analog IC design
•	OTA architecture and current-mirror design
•	Transistor biasing and operating-point analysis
•	Small-signal gain and bandwidth analysis
•	Phase-margin and stability interpretation
•	Slew-rate and settling-time verification
•	Common-mode range and output swing characterization
•	Matching-aware physical layout
•	Dummy-device usage and layout symmetry
•	DRC/LVS verification
•	Post-layout parasitic-aware validation
•	Technical report writing and result interpretation
•	Measurement-aware analog/RF validation planning

# Project Status:
Status: Completed
Tool: Cadence Virtuoso
Project Type: Analog/RF IC Design Portfolio
Main Focus: CMOS OTA design, schematic simulation, layout, DRC/LVS, post-layout validation, and measurement methodology

# Author:
Md Moklesur Rahman
RF / Wireless / System Specification Engineer
LinkedIn:
linkedin.com/in/md-moklesur-rahman-65a63962
