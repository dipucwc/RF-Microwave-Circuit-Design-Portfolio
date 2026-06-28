# RF-Microwave-Circuit-Design-Portfolio
# RF-Microwave-Circuit-Design-Portfolio:
This repository presents a professional RF and microwave circuit design portfolio focused on RF system analysis, RF circuit simulation, amplifier design, S-parameter verification, noise/stability analysis, impedance matching, and technical documentation.
The projects in this repository are designed to demonstrate practical engineering capability using tools such as Keysight ADS, KICad, Cadence Virtuoso, MATLAB/Python-based analysis where applicable, and RF/microwave design methodology.

# Repository Objective:
The purpose of this repository is to demonstrate end-to-end RF and microwave engineering skills, from system-level performance analysis to transistor-level circuit realization.

# The portfolio focuses on:
•	RF system design and performance analysis
•	RF/microwave amplifier simulation
•	ACPR/ACLR and EVM analysis
•	Receiver link-budget and noise-figure analysis
•	Spurious-response and intermodulation analysis
•	Two-tone IP3 / TOI evaluation
•	Transistor biasing and S-parameter verification
•	Noise circles, stability analysis, and Smith-chart interpretation
•	Input/output impedance matching
•	Technical reporting and engineering documentation


## Current Projects

## Current Projects

| No. | Project                                                           | Status      | Tool                     | Main Topics                                                                                                                                 |
| --- | ----------------------------------------------------------------- | ----------- | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| 01  | `ADS_RF_System_and_Amplifier_Design`                              | Completed   | Keysight ADS             | ACPR, EVM, receiver budget, spurious response, IP3, transistor biasing, S-parameters, noise figure, stability, matching network             |
| 02  | `Cadence_CMOS_OTA_Design`                                         | Completed   | Cadence Virtuoso         | CMOS OTA design, schematic simulation, layout, DRC/LVS, post-layout verification                                                            |
| 03  | `KiCad_Solar_Home_Power_Control_Board`                            | Completed   | KiCad                    | Solar home power-control board, schematic design, PCB layout, power-stage design, protection circuits, control interface                    |
| 04  | `ADS_LNA_Design_Noise_Matching_and_Stability`                     | In Progress | Keysight ADS / RF tools  | Low-noise amplifier design, NFmin, Gamma_opt, noise circles, gain/noise trade-off, K-factor stability, input/output matching                |
| 05  | `ADS_RF_Power_Amplifier_Linearity_and_ACPR_Optimization`          | Planned     | Keysight ADS / MATLAB    | PA linearity, gain compression, AM-AM/AM-PM, ACPR, EVM, two-tone IP3, output matching, efficiency trade-off                                 |
| 06  | `ADS_Smith_Chart_Impedance_Matching_Network_Design`               | Planned     | Keysight ADS / RF theory | Smith-chart matching, L-section networks, return loss, VSWR, reflection coefficient, bandwidth trade-off, practical L/C synthesis           |
| 07  | `RF_Filter_and_Matching_Network_Design`                           | Planned     | Keysight ADS             | RF filter design, insertion loss, return loss, group delay, impedance transformation, RF front-end filtering, matching-network optimization |
| 08  | `Cadence_RF_CMOS_LNA_or_Differential_Amplifier_Design`            | Planned     | Cadence Virtuoso         | RF CMOS amplifier design, biasing, gain, input/output matching, stability, noise figure, layout-aware verification                          |
| 09  | `ADS_Mixer_Spurious_Response_and_Receiver_Dynamic_Range_Analysis` | Planned     | Keysight ADS             | Mixer spurs, harmonic balance, IF planning, blocker analysis, intermodulation, receiver dynamic range, frequency planning                   |


# Project Structure: 
## Repository Structure

```
RF-Microwave-Circuit-Design-Portfolio/
│
├── README.md
│
├── .gitignore
│
├── 01_ADS_RF_System_and_Amplifier_Design/
│   ├── README.md
│   ├── docs/
│   │   └── RF_System_and_Amplifier_Design_ADS_Portfolio_Report.pdf
│   ├── figures/
│   │   ├── acpr_evm/
│   │   ├── receiver_budget/
│   │   ├── spurious_response/
│   │   ├── ip3_toi/
│   │   ├── biasing/
│   │   ├── s_parameters/
│   │   ├── noise_stability/
│   │   └── matching_network/
│   ├── exported_results/
│   └── notes/
│       ├── measurement_methodology.md
│       └── result_traceability.md
│
├── 02_Cadence_CMOS_OTA_Design/
│   ├── README.md
│   ├── docs/
│   ├── figures/
│   ├── schematics/
│   ├── layout/
│   ├── simulation_results/
│   └── verification/
│       ├── drc/
│       └── lvs/
│
├── 03_KiCad_Solar_Home_Power_Control_Board/
│   ├── README.md
│   ├── docs/
│   ├── schematics/
│   ├── pcb_layout/
│   ├── gerber_files/
│   ├── bom/
│   └── figures/
│
├── 04_ADS_LNA_Design_Noise_Matching_and_Stability/
│   ├── README.md
│   ├── docs/
│   ├── figures/
│   ├── exported_results/
│   └── notes/
│
├── 05_ADS_RF_Power_Amplifier_Linearity_and_ACPR_Optimization/
│   ├── README.md
│   ├── docs/
│   ├── figures/
│   ├── exported_results/
│   └── notes/
│
├── 06_ADS_Smith_Chart_Impedance_Matching_Network_Design/
│   ├── README.md
│   ├── docs/
│   ├── figures/
│   ├── exported_results/
│   └── notes/
│
├── 07_RF_Filter_and_Matching_Network_Design/
│   ├── README.md
│   ├── docs/
│   ├── figures/
│   ├── exported_results/
│   └── notes/
│
├── 08_Cadence_RF_CMOS_LNA_or_Differential_Amplifier_Design/
│   ├── README.md
│   ├── docs/
│   ├── figures/
│   ├── schematics/
│   ├── layout/
│   ├── simulation_results/
│   └── verification/
│
└── 09_ADS_Mixer_Spurious_Response_and_Receiver_Dynamic_Range_Analysis/
    ├── README.md
    ├── docs/
    ├── figures/
    ├── exported_results/
    └── notes/
```
