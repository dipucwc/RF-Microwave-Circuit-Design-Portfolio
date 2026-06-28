
# notes/result_traceability.md

# Result Traceability:

This project separates results into three categories so that the public GitHub portfolio remains technically clear and defensible.

## 1. ADS-Extracted / Simulated Results:

These are values taken directly from ADS simulation plots, budget-controller outputs, markers, and schematic-level analysis.

Examples:

* ACPR / ACLR spectral regrowth trend
* EVM and constellation result
* Receiver budget gain and noise figure
* Two-tone IP3 / TOI values
* S-parameter plots
* Noise figure and NFmin result
* Stability and matching behavior

## 2. Hand-Calculated Cross-Checks

These are values derived from RF engineering equations and used to verify the ADS results.

Examples:

* Friis cascaded noise-figure calculation
* IP3 relation between input-referred and output-referred intercept
* Return-loss calculation from S11
* Reflection-coefficient and impedance relation
* Smith chart matching interpretation

## 3. Engineering Interpretation

These are conclusions based on ADS simulation, RF theory, and standard RF measurement practice.

Examples:

* The first receiver stage dominates the cascaded noise figure.
* Two-tone IM3 products define receiver linearity and dynamic-range limits.
* ACPR shows nonlinear spectral regrowth into adjacent channels.
* EVM shows modulation-quality degradation caused by distortion, filtering, noise, and phase/amplitude error.
* Stability and matching must be verified before an amplifier can be considered practically usable.

## Important Note

This project is a simulation and RF design portfolio based on Keysight ADS. It is not presented as a fabricated hardware measurement project. The measurement-methodology section explains how the same quantities would be validated using RF bench instruments such as a VNA, spectrum analyzer, vector signal analyzer, noise-figure analyzer, signal generators, and SMU.
