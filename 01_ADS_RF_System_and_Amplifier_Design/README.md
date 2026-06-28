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
This project demonstrates the ability to:
•	Build a complete RF system and amplifier simulation flow in Keysight ADS
•	Analyze transmitter linearity using ACPR/ACLR and EVM
•	Evaluate receiver sensitivity using link-budget and Friis noise cascade methods
•	Analyze spurious products and intermodulation behavior
•	Extract and interpret IIP3/OIP3 from two-tone simulations
•	Select and verify transistor biasing for RF circuit simulation
•	Use S-parameters for gain, return loss, reverse isolation, and model verification
•	Evaluate noise figure, optimum source match, and stability
•	Apply Rollett stability methodology
•	Interpret Smith charts and design L-C matching networks
•	Compare RF performance before and after matching
•	Prepare traceable, technically defensible RF documentation

# Project Status:
Status: Completed
Tool: Keysight Advanced Design System
Project Type: RF / Microwave Circuit Design Portfolio
Main Focus: RF system analysis, amplifier simulation, linearity, noise, stability, and matching-network design

# Author:
Md Moklesur Rahman
RF / Wireless / System Specification Engineer
LinkedIn: linkedin.com/in/md-moklesur-rahman-65a63962
