# 01 - ADS RF System and Amplifier Design
# Project Overview: 
This project presents a complete RF and microwave circuit-design portfolio project developed using Keysight Advanced Design System (ADS). The project connects system-level RF performance analysis with transistor-level amplifier design.
The first part focuses on RF system characterization, including ACPR/ACLR, EVM, receiver link-budget analysis, spurious-response analysis, and two-tone third-order intercept point (IP3/TOI). The second part focuses on RF circuit realization, including transistor biasing, S-parameter model verification, noise figure analysis, stability evaluation, Smith-chart interpretation, and input/output matching-network design.
The purpose of this project is to demonstrate practical RF engineering capability, not only familiarity with ADS. The repository includes the technical report, ADS workspace/project files, exported result plots, and documentation explaining how the simulations were performed and interpreted.

# Main Topics Covered: 
•	ACPR / ACLR analysis
•	EVM and constellation evaluation
•	Receiver link-budget analysis
•	Spurious-response analysis
•	Two-tone IP3 / TOI extraction
•	Transistor bias-point selection
•	S-parameter model verification
•	Noise figure and optimum source match
•	Noise-circle interpretation
•	Rollett stability-factor methodology
•	Smith-chart interpretation
•	Input/output L-C matching-network design
•	Final comparison before and after matching
•	Engineering result traceability

# Project Workflow: 

The project follows a complete RF design flow:

Modulated RF Source
        ↓
ACPR / ACLR Analysis
        ↓
EVM and Constellation Evaluation
        ↓
Receiver Link-Budget Analysis
        ↓
Spurious and Intermodulation Mapping
        ↓
Two-Tone IP3 / TOI Extraction
        ↓
Transistor Bias Point Selection
        ↓
S-Parameter Model Verification
        ↓
Noise Figure and Stability Analysis
        ↓
Smith-Chart Matching
        ↓
Input / Output L-C Matching Network
        ↓
Final Technical Report and Result Interpretation

## Tools Used:

| Tool                         | Purpose                                                                                                          |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Keysight ADS                 | RF system simulation, circuit simulation, harmonic balance, S-parameters, noise analysis, and impedance matching |
| ADS Data Display             | Marker extraction, result visualization, spectrum plots, and S-parameter plots                                   |
| RF theory / hand calculation | ACPR, EVM, Friis noise cascade, IP3, stability analysis, and matching equations                                  |
| Technical documentation      | Report writing, result interpretation, traceability, and portfolio presentation                                  |

# Repository Structure:

## Repository Structure

```text
01_ADS_RF_System_and_Amplifier_Design/
│
├── README.md
│
├── docs/
│   └── RF_System_and_Amplifier_Design_ADS_Report.pdf
│
├── figures/
│   ├── acpr_evm/
│   ├── receiver_budget/
│   ├── spurious_ip3/
│   ├── bias_setup/
│   ├── s_parameters/
│   ├── noise_stability/
│   └── impedance_matching/
│
├── schematics/
│   └── screenshots/
│
├── simulation_results/
│   ├── acpr_evm/
│   ├── link_budget/
│   ├── ip3_toi/
│   ├── s_parameters/
│   ├── noise_figure/
│   └── matching/
│
└── notes/
    ├── measurement_methodology.md
    └── result_traceability.md
```
##  Key Results:

| Design Area           | Method / Metric                       | Result / Outcome                                                                       |
| --------------------- | ------------------------------------- | -------------------------------------------------------------------------------------- |
| Transmitter linearity | ACPR / ACLR using π/4-DQPSK source    | Adjacent-channel regrowth approximately 50–60 dBc below the main channel               |
| Signal quality        | EVM and constellation analysis        | Peak EVM approximately 0.011 normalized                                                |
| Receiver chain        | Cascaded RF link budget               | Approximately 76.1 dB cascaded gain and approximately 4.2 dB ADS-reported noise figure |
| Noise cross-check     | Friis cascade calculation             | Hand calculation gives approximately 3.7 dB cascaded noise figure                      |
| Interference analysis | Spurious-response mapping             | Low-order mixing products identified for receiver frequency planning                   |
| Linearity             | Two-tone IP3 / TOI analysis           | OIP3 approximately 21.8 dBm and IIP3 approximately −25.7 dBm                           |
| Bias design           | DC operating-point setup              | Bias point established before S-parameter, noise, and matching analysis                |
| Model verification    | S-parameter comparison                | Device model checked against reference S-parameter behavior                            |
| LNA analysis          | Noise figure and stability            | (NF_{\min}) approximately 1.74 dB near 1.86 GHz                                        |
| Matching              | Smith chart and L-C network synthesis | Input/output matching network synthesized                                              |

# ACPR / ACLR Analysis:

Adjacent-channel power ratio is used to quantify spectral regrowth caused by RF amplifier nonlinearity. In this project, the RF amplifier was driven using a π/4-DQPSK modulated source, and ADS channel-power measurements were used to compare the main-channel power against the adjacent-channel leakage power.
The simulated spectrum shows adjacent-channel lobes approximately 50–60 dBc below the main channel, demonstrating how nonlinear amplifier behavior creates out-of-band spectral regrowth. This analysis is important for RF transmitter design because ACPR/ACLR is directly related to regulatory spectral-mask compliance and transmitter linearity.

# EVM and Constellation Analysis: 

Error-vector magnitude was used to evaluate the quality of the modulated signal. EVM compares the distorted constellation points against the ideal reference constellation and gives a direct measure of modulation accuracy.

The RMS EVM is calculated as

[
EVM_{\mathrm{RMS}}(%) =
\sqrt{
\frac{
\sum_{k=1}^{N}\left|S_{\mathrm{meas},k}-S_{\mathrm{ideal},k}\right|^2
}{
\sum_{k=1}^{N}\left|S_{\mathrm{ideal},k}\right|^2
}
}
\times 100%
]

where (S_{\mathrm{meas},k}) is the measured or distorted symbol, (S_{\mathrm{ideal},k}) is the ideal reference symbol, and (N) is the number of evaluated symbols.

The ADS result shows a peak normalized EVM of approximately 0.011, indicating a tight constellation and limited modulation distortion under the simulated operating condition.

# Receiver Link-Budget Analysis:
A cascaded receiver link-budget analysis was performed to evaluate total receiver gain, cascaded noise figure, and dynamic-range behavior. The receiver chain includes RF filtering, gain stages, mixer/down-conversion, IF filtering, and additional gain blocks.
The ADS budget analysis reports approximately 76.1 dB cascaded gain and approximately 4.2 dB cascaded noise figure. A separate hand calculation using Friis’ formula was also included to verify the noise-figure trend.
Friis’ equation is

[
F_{\mathrm{tot}} =
F_1 +
\frac{F_2-1}{G_1} +
\frac{F_3-1}{G_1G_2}

\cdots
]
where (F_i) are linear noise factors and (G_i) are linear power gains.
The hand-calculated Friis cascade gives approximately 3.7 dB noise figure, which is close to the ADS-reported value. The difference is acceptable because the hand calculation is based on schematic-read stage values and simplified assumptions. The analysis confirms the key RF principle that the first filter and first amplifier dominate the cascaded receiver noise figure.

# Spurious-Response Analysis:
Spurious-response analysis was performed to identify unwanted mixing products generated by nonlinear receiver stages and mixer operation. Mixer spurs occur at combinations of RF and LO frequencies, typically expressed as
[
f_{\mathrm{spur}} = m f_{\mathrm{RF}} \pm n f_{\mathrm{LO}}
]

where (m) and (n) are integers.
This analysis helps identify which unwanted tones may fall into the IF band and appear as false desired signals. The project demonstrates how ADS can be used for frequency planning and receiver filtering decisions before hardware implementation.

# Two-Tone IP3 / TOI Analysis:
Two-tone third-order intercept analysis was performed to evaluate receiver linearity. When two tones pass through a nonlinear RF chain, third-order intermodulation products appear at

[
2f_1 - f_2
]

and

[
2f_2 - f_1
]

These products are especially important because they appear close to the wanted tones and are difficult to remove by filtering.

The input-referred and output-referred third-order intercept points are calculated as

[
IIP3 = P_{\mathrm{in}} + \frac{\Delta P}{2}
]

[
OIP3 = IIP3 + G
]

where (\Delta P) is the power difference between the fundamental tone and the IM3 product, and (G) is the gain.
The ADS two-tone simulation gives approximately

OIP3 ≈ 21.8 dBm
IIP3 ≈ −25.7 dBm
Conversion gain ≈ 47.5 dB
The relation (OIP3 - IIP3 = G) confirms that the extracted IP3 result is self-consistent.

# Transistor Bias Setup:

The transistor-level part of the project begins with DC bias setup. Biasing is essential because it determines the operating point, small-signal gain, transconductance, noise performance, and compression behavior of the amplifier.
The operating point was selected and verified before running S-parameter, noise, stability, and matching simulations. This ensures that all subsequent RF results are based on a stable and repeatable DC condition.

# S-Parameter Model Verification:
S-parameter simulation was used to verify the RF behavior of the transistor model. The scattering parameters describe how incident and reflected waves behave at the input and output ports of an RF device.
Important S-parameters include:

S11: input reflection coefficient
S21: forward gain
S12: reverse isolation
S22: output reflection coefficient

Return loss is calculated as

[
RL = -20\log_{10}|S_{11}|
]

The ADS Smith chart and rectangular S-parameter plots were used to evaluate gain, input/output matching behavior, reverse isolation, and frequency-dependent device behavior.

# Noise Figure and Stability Analysis:

Noise figure analysis was performed to evaluate the low-noise behavior of the amplifier. The project includes NFmin extraction, noise-circle interpretation, and optimum source-match analysis.
The minimum noise figure is approximately
NFmin ≈ 1.74 dB near 1.86 GHz
Stability analysis was also performed using RF stability criteria such as Rollett stability factor and reflection-based stability interpretation. This ensures that the amplifier can be designed for stable operation across the frequency range of interest.

# Smith Chart Impedance Matching:

Smith chart matching was used to synthesize input and output impedance-matching networks. The goal of matching is to transform the source and load impedances to the desired impedance seen by the transistor.
The project includes input/output L-C matching network design, including values such as

Input network:  Cin ≈ 30 pF, Lin ≈ 4 nH
Output network: Lout ≈ 16 nH, Cout ≈ 2 pF
This step demonstrates practical RF matching-network design using ADS and Smith chart methods.

# Measurement Methodology and Bench Correspondence:

Each simulated analysis in this project has a corresponding RF laboratory measurement method.
| Simulated Analysis             | Bench Instrument                                                             | Measurement Technique                                                                                  |
| ------------------------------ | ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| S-parameters / gain / matching | Vector network analyzer (VNA)                                                | (S_{11}), (S_{21}), (S_{12}), and (S_{22}) measurement after SOLT/TRL calibration                      |
| ACPR / spectrum                | Spectrum analyzer / signal analyzer                                          | Channel-power integration and ACLR/ACPR marker extraction                                              |
| EVM / constellation            | Vector signal analyzer (VSA)                                                 | Demodulated EVM, constellation, trajectory, and modulation-quality analysis                            |
| Two-tone IP3                   | Two signal generators + combiner + spectrum analyzer                         | Two-tone test and IM3 spacing extraction for IIP3/OIP3 calculation                                     |
| Noise figure / (NF_{\min})     | Noise-figure analyzer + noise source; source-pull setup for noise parameters | Y-factor noise-figure measurement and source-pull extraction of (NF_{\min}), (R_n), and (\Gamma_{opt}) |
| Bias / DC operating point      | SMU / DC source-meter                                                        | I–V sweep, (V_{CE}), (I_C), and supply-current verification                                            |

This section connects the ADS simulation results to practical RF bench validation.


# How ACPR and EVM Were Measured :
# ACPR / ACLR: 

ACPR was evaluated using a modulated RF source and channel-power measurement blocks. The wanted-channel power and adjacent-channel power were compared using integrated channel power.
The ACPR result is interpreted from:

•	Main-channel spectral power
•	Upper/lower adjacent-channel spectral regrowth
•	Channel-select filtering behavior
•	Envelope simulation output
	
# EVM :
EVM was evaluated by comparing the ideal modulated signal path against the distorted amplifier output path. The error vector is calculated as the difference between ideal and measured symbol locations.
The EVM result is interpreted from:

•Ideal constellation
•	Distorted constellation
•	Error-vector magnitude plot
•	Ideal-versus-distorted signal-path comparison

# Raw ADS Workspace and Verification: 
The raw Keysight ADS workspace, simulation datasets, schematic files, and exported result plots are provided in the accompanying project folder for technical verification.

A reviewer can open the ADS workspace to verify:
•	ACPR / EVM simulation setup
•	Receiver link-budget setup
•	Spurious-response harmonic-balance setup
•	Two-tone IP3 / TOI simulation
•	Transistor bias sweep
•	S-parameter simulation
•	Noise-circle and stability analysis
•	Input/output matching-network design
•	Exported datasets and data displays

# Final Comparison Before and After Matching:

The final matching-network section compares RF performance before and after matching using the following design indicators:

| Performance Area   | Before Matching                                                                  | After Matching                                                                               |
| ------------------ | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Input return loss  | Device input impedance is not yet transformed to the source reference impedance. | Improved through input L-C matching and stabilization network.                               |
| Output return loss | Device output impedance is not yet transformed to the load reference impedance.  | Improved through output L-C matching.                                                        |
| Gain transfer      | Limited by mismatch between device impedance and source/load impedances.         | Improved power transfer near the design frequency.                                           |
| Noise figure       | Strongly depends on source impedance relative to `Γopt`.                         | Source match selected by considering `NFmin`, `Γopt`, gain, and stability.                   |
| Stability          | Must be checked before applying the final matching network.                      | Stabilization elements included to support stable amplifier behavior.                        |
| Practical design   | Device-only behavior without complete RF implementation.                         | Realizable RF amplifier network including biasing, stabilization, and input/output matching. |


# Skills Demonstrated: 
This project demonstrates the following RF and microwave engineering skills:
•	Keysight ADS RF system simulation
•	ACPR / ACLR analysis
•	EVM and constellation interpretation
•	Receiver link-budget analysis
•	Friis noise-figure cascade calculation
•	Spurious-response analysis
•	Two-tone IP3 / TOI extraction
•	RF transistor biasing
•	S-parameter model verification
•	Smith chart interpretation
•	Noise figure and NFmin analysis
•	Stability analysis
•	Input/output impedance matching
•	L-C matching network synthesis
•	RF measurement methodology
•	VNA, spectrum analyzer, VSA, noise-figure analyzer, and SMU measurement mapping

# Project Status:
Status: Completed
Tool: Keysight Advanced Design System
Project Type: RF / Microwave Circuit Design Portfolio
Main Focus: RF system analysis, amplifier simulation, linearity, noise, stability, and matching-network design

# Author:
Md Moklesur Rahman |RF / Wireless / System Specification Engineer |LinkedIn: linkedin.com/in/md-moklesur-rahman-65a63962
