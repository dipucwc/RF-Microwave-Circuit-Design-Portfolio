03_KiCad_Solar_Home_Power_Control_Board/README.md

# Project Overview:
This project presents the design and verification of a Solar Home Power Control Board developed using KiCad. The board integrates three major functional blocks: an ATmega328P microcontroller control core, a solar/battery power-management stage, and a mains-derived SMPS front-end with optocoupler isolation and protection circuitry.
The purpose of this project is to demonstrate end-to-end embedded hardware and power-electronics design capability, including schematic capture, component selection, closed-form circuit calculations, PCB placement and routing, 3D mechanical review, fabrication preparation, and bench-verification methodology.
This project is presented as a hardware design and validation portfolio project. It is not claimed as a certified commercial mains-powered product.

# Objective:

The main objective was to design a mixed-domain solar home control board that can manage low-voltage control, battery-backed load switching, power regulation, and isolated power-supply feedback on a single PCB.

The design demonstrates the following engineering flow:

System Requirement Definition
        ↓
Hierarchical Schematic Design in KiCad
        ↓
ATmega328P Control-Core Design
        ↓
Solar / Battery Power-Management Design
        ↓
Relay Driver and Load-Switching Design
        ↓
Mains SMPS Front-End and Isolation Review
        ↓
Closed-Form Electrical Calculations
        ↓
PCB Footprint Assignment
        ↓
PCB Placement and Routing
        ↓
Trace-Width, Creepage, Clearance, and EMC Review
        ↓
3D Mechanical Integration
        ↓
Fabrication Output Preparation
        ↓
Bench-Verification Methodology


# Repository Structure:
03_KiCad_Solar_Home_Power_Control_Board/
README.md
docs/
  Solar_Home_Power_Control_Board_KiCad_Report.pdf
figures/
  schematic/
  pcb_layout/
  routing/
  three_d_view/
  bench_measurement/
schematics/
  screenshots/
pcb/
  layout_screenshots/
  three_d_render/
fabrication/
  gerber_output/
  drill_files/
  bom/
notes/
  measurement_methodology.md
  result_traceability.md

# Key Results:

| Design Area            | Method / Metric                            | Result / Outcome                                                                                              |
| ---------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------- |
| MCU control core       | ATmega328P-based schematic design          | Crystal timebase, reset circuit, UART, relay outputs, buzzer, LEDs, and sensor input implemented              |
| Crystal oscillator     | Load-capacitance calculation               | Standard 27 pF capacitors selected for the estimated crystal load requirement                                 |
| Relay driver           | Saturated NPN transistor switch            | Base-drive margin verified for reliable relay-coil switching                                                  |
| Flyback protection     | Free-wheeling diode across relay coil      | Inductive turn-off transient clamped to protect the switching transistor                                      |
| Rectifier stage        | Full-wave bridge rectifier analysis        | AC input converted to unregulated DC bus for the power-management stage                                       |
| Reservoir capacitor    | Ripple-voltage calculation                 | 4700 µF capacitor selected for approximately 1 V peak-to-peak ripple target                                   |
| Regulated rail         | LM317 adjustable regulator                 | Output rail designed around approximately 12.5 V with adjustable voltage setting                              |
| Thermal analysis       | LM317 power-dissipation check              | Approximately 1.55 W regulator dissipation evaluated and heatsink requirement identified                      |
| Battery backup path    | Constant-voltage float-charge concept      | Reverse-blocking diode and relay logic included for backup-battery operation                                  |
| Inrush limiting        | NTC thermistor calculation                 | Mains-side capacitor charging surge bounded during power-on                                                   |
| Isolation feedback     | PC817 optocoupler feedback                 | Isolated feedback path analyzed using CTR-based design margin                                                 |
| Snubber network        | RC damping concept                         | Switching-node ringing and EMI risk addressed using snubber design logic                                      |
| PCB layout             | KiCad placement and routing                | Functional regions separated for mains/front-end, solar/battery power, and low-voltage control                |
| Trace-width sizing     | IPC-2221 current/temperature-rise estimate | High-current battery/load traces widened for current and thermal margin                                       |
| Creepage and clearance | Primary/secondary domain separation        | Mains and low-voltage areas separated with safety-aware layout practice                                       |
| 3D integration         | KiCad 3D viewer                            | Component height, placement, relay position, capacitor clearance, and connector access reviewed               |
| Bench verification     | Hantek DSO2C10 measurement methodology     | Rectified bus, ripple, regulated rail, switching node, and relay-driver behavior mapped to measurement points |
| Public portfolio scope | Safety and validation disclaimer           | Presented as a prototype/design-validation project, not as a certified commercial mains product               |


# ATmega328P Control Core:

The control section is built around an ATmega328P microcontroller. The MCU provides sensing, timing, UART communication, relay control, and buzzer/LED status indication.

The crystal oscillator is designed using the effective load-capacitance relation:

[
C_L = \frac{C_1 C_2}{C_1 + C_2} + C_{stray}
]

For a typical crystal load capacitance of approximately 18 pF and estimated stray capacitance of approximately 4 pF, two standard 27 pF load capacitors provide a suitable practical value.

The MCU output pins drive relay coils through saturated transistor switches. The base-drive condition is checked using:

[
I_B = \frac{V_{OH} - V_{BE}}{R_B}
]

The relay driver is designed with sufficient base-current margin so that the transistor operates as a saturated switch instead of a linear amplifier. A free-wheeling diode across each relay coil protects the transistor from inductive voltage spikes during turn-off.

# Solar / Battery Power-Management Stage:

The solar/battery stage rectifies, regulates, and routes energy to the load and backup battery path. A full-wave bridge rectifier converts the AC source to unregulated DC, while a reservoir capacitor reduces ripple.

For a full-wave bridge rectifier, the approximate DC voltage and ripple are:

[
V_{DC} \approx V_{peak} - 2V_F
]

[
V_{ripple} \approx \frac{I_{load}}{2fC}
]

For a 12 V RMS secondary, the peak voltage is approximately 17 V. After the bridge diode drops, the unregulated DC rail is approximately 15.6 V. With a 4700 µF reservoir capacitor and 0.5 A load current, the ripple is approximately 1 V peak-to-peak, which matches the intended design target.


# LM317 Regulated Rail and Thermal Analysis:

The LM317 adjustable regulator sets the regulated output rail through its feedback divider:

[
V_{out} = 1.25 \left(1 + \frac{R_2}{R_1}\right) + I_{adj}R_2
]

Using a 240 Ω reference resistor and an adjustable potentiometer, the output rail can be trimmed around the intended battery-float and load-supply range.

The regulator thermal dissipation is estimated using:

[
P_{LM317} = (V_{in} - V_{out})I_{load}
]
At approximately 15.6 V input, 12.5 V output, and 0.5 A load current, the dissipation is approximately 1.55 W. This is thermally significant, so heatsinking is recommended for reliable operation.

# Battery Backup and Load Switching:

The board includes relay-based source/load switching so that the regulated supply and battery-backed path can be routed to the load. Reverse-blocking diodes are included to prevent undesired current flow between the solar, battery, regulator, and load nodes.

The battery-charging approach is described as a simple constant-voltage float-charge method suitable for a backup-battery demonstration. It is not presented as a full certified battery-management system. For lithium-ion or safety-critical battery systems, a dedicated charger IC and protection circuit would be required.

# Mains SMPS Front-End and Isolation:

The mains-derived front-end includes an NTC inrush limiter, bridge rectifier, high-voltage reservoir capacitor, optocoupler feedback, and snubber/clamp circuitry.

The NTC limits the initial charging surge into the bulk capacitor. The worst-case inrush current can be approximated by:

[
I_{inrush} = \frac{V_{peak}}{R_{NTC,cold} + R_{line}}
]

The PC817 optocoupler provides isolated feedback between the secondary-side regulation signal and the primary-side control domain. The current-transfer ratio is interpreted as:

[
I_C = \frac{CTR}{100} I_F
]

where (CTR) is expressed as a percentage.

The SMPS section is treated as a prototype-level isolated front-end design study. Practical mains hardware requires proper fusing, enclosure, creepage/clearance verification, isolation testing, and compliance testing before real deployment.


# PCB Layout and Routing:

The PCB was designed in KiCad using separated functional regions for the low-voltage MCU section, solar/battery power stage, and mains/high-voltage domain. Placement was chosen to reduce noise coupling, maintain clear power paths, and improve serviceability.

Trace widths were selected based on current level and thermal margin. The IPC-2221 trace-current relation was used as a design reference:

[
I = k \Delta T^{0.44} A^{0.725}
]

High-current battery and load traces were widened, while low-current logic traces were kept narrower. Ground and power pours were used to lower impedance, improve return paths, and improve thermal spreading.


# Creepage, Clearance, and EMC Considerations:

The layout separates primary and secondary domains and maintains additional clearance around mains-side circuitry. The optocoupler and transformer regions are treated as isolation-boundary components.
EMC risk is reduced by keeping high-current and high-(dV/dt) loops compact, placing the snubber close to the switching node, and using ground return paths carefully. These layout decisions reduce loop area and help control conducted and radiated emissions.

# 3D Integration and Mechanical Review :
KiCad 3D viewer was used to review the populated board before fabrication. The 3D view helps verify component height, connector access, relay placement, electrolytic capacitor clearance, heatsink position, and possible mechanical collision issues.
This step connects the electrical PCB layout to the physical hardware implementation and helps identify mechanical problems before manufacturing.

# Bench-Verification Methodology:

The prototype verification was mapped to specific measurement points and oscilloscope settings. The Hantek DSO2C10 digital storage oscilloscope was used as the reference bench instrument.

| Predicted Quantity               | Measurement Node             | Instrument / Setup                          | Verification Purpose                                                   |
| -------------------------------- | ---------------------------- | ------------------------------------------- | ---------------------------------------------------------------------- |
| Rectified bus voltage, (V_{DC})  | Reservoir capacitor output   | DSO, DC-coupled measurement                 | Confirms bridge-rectifier output and unregulated DC bus level          |
| Reservoir ripple, (V_{pp})       | Reservoir capacitor output   | DSO, AC-coupled ripple measurement          | Verifies capacitor sizing and ripple-voltage prediction                |
| Regulated output rail, (V_{out}) | LM317 output                 | DSO or digital multimeter, DC measurement   | Confirms adjustable regulator output and voltage-setpoint accuracy     |
| Switching-node waveform          | Primary drain / snubber node | DSO with 10x probe                          | Checks switching behavior, ringing, and snubber damping effect         |
| Relay-driver flyback             | Transistor collector         | DSO, single-shot capture                    | Verifies free-wheeling diode clamp and relay-coil transient protection |
| Load-switching behavior          | Relay output / load node     | DSO or digital multimeter                   | Confirms correct power routing between source, battery, and load path  |
| Battery-path voltage             | Battery terminal / load path | DSO or digital multimeter                   | Confirms backup-battery path and reverse-blocking behavior             |
| Supply-current behavior          | Input supply path            | Current probe or series current measurement | Checks current draw and validates power-budget assumptions             |

This verification plan connects the calculated design values to practical bench measurements and confirms that the circuit can be evaluated through clear, measurable hardware test points.

# Safety and Validation Scope
This project includes mains-related circuit concepts and should be treated carefully. The design is presented as an engineering portfolio and prototype validation study, not as a certified commercial mains product.
Before any real-world deployment, the design would require:
•	Proper fuse and protection design
•	Certified isolation transformer or certified AC/DC module
•	Verified creepage and clearance according to the applicable safety standard
•	Hi-pot / insulation testing
•	Thermal testing under worst-case load
•	EMI/EMC testing
•	Enclosure and touch-safety review
•	Battery chemistry-specific charge protection

# Skills Demonstrated:
This project demonstrates the following skills:
•	KiCad schematic design
•	Hierarchical hardware design
•	ATmega328P embedded control-board design
•	Relay-driver design
•	Transistor saturation analysis
•	Flyback diode protection
•	Solar/battery power-path design
•	LM317 adjustable regulator design
•	Rectifier and reservoir capacitor sizing
•	Ripple-voltage calculation
•	Thermal dissipation analysis
•	Constant-voltage float-charge concept
•	NTC inrush-limiting calculation
•	Optocoupler feedback interpretation
•	SMPS front-end design awareness
•	RC snubber concept
•	PCB placement and routing
•	IPC-2221 trace-width estimation
•	Creepage, clearance, and EMC-aware layout
•	KiCad 3D mechanical review
•	Bench-verification planning using oscilloscope measurements

# Project Status:
Status: Completed portfolio project.
The project includes schematic design, PCB layout, 3D mechanical review, fabrication-output preparation, and bench-verification methodology for a solar home power control board.
For the complete technical explanation, equations, design screenshots, PCB layout, 3D rendering, and validation discussion, please refer to the full technical report in the docs/ folder.

# Author:
Md Moklesur Rahman| LinkedIn: https://www.linkedin.com/in/md-moklesur-rahman-65a63962/|GitHub Portfolio: RF / Microwave / Wireless / Embedded Hardware / Power Electronics


