
![Logo](https://www.vlsisystemdesign.com/wp-content/uploads/2016/12/vsd_logo.jpg)


# Digital VLSI SoC Design and planning Training

Welcome to the OpenLane workshop! In this workshop, we will delve into the process of designing an Application Specific Integrated Circuit (ASIC) from the Register Transfer Level (RTL) to the Graphical Data System (GDS) file using the OpenLane ASIC flow. The flow is composed of several key steps, starting with an RTL file and culminating in a GDS file.

## Lessons Learned

Understanding the RTL to GDS Flow:

1. Grasped the end-to-end process of converting a high-level hardware description to a physical ASIC layout.
Recognized the importance of each step in the flow, from synthesis to sign-off.

2. Synthesis:

Learned how RTL is converted to a gate-level netlist using standard cell libraries.
Identified the different views of cells (Liberty, HDL, SPICE, Layout).

3. Floor and Power Planning:
Understood the significance of floor planning in chip partitioning and I/O pad placement.



## DAY 1

Key Steps in the RTL to GDS Flow
Synthesis

 Converts RTL to a gate-level netlist using components from the Standard Cell Library (SCL).
Components:
Liberty view: Electrical models (delay, power).
HDL view: Behavioral models.
SPICE/CDL view: Circuit models.
Layout views: Abstract and detailed (GDS).



![Screenshot 2024-05-26 210622](https://github.com/AnoushkaTripathi/DIGITAL_VLSI_SoC_Design_and-planning_Training/assets/98522737/87695cbe-0663-4d95-b6b2-119ff617a763)
Floor and Power Planning

Floor Planning: Partitioning the chip die and placing I/O pads.
Power Planning: Establishing VDD and GND connections via rings and metal straps to minimize resistance and address electro-migration.
Placement

Global Placement: Determines optimal, but not necessarily legal, positions for cells.
Detailed Placement: Adjusts positions to ensure legality and non-overlapping placement.
Clock Distribution Network

Objective: Distribute the clock signal with minimal skew.
Structure: Typically a tree-like structure to ensure synchronized arrival of the clock signal across the chip.
Signal Routing

Process: Connects components using available metal layers.
Layers: Sky130 PDK defines 6 routing layers with specific characteristics (thickness, pitch, width).
Steps: Global routing (guides) and detailed routing (actual wiring).
Sign-off (Verification)

Design Rule Checking (DRC): Ensures the final layout adheres to design rules.
Layout vs Schematic (LVS): Confirms the layout matches the schematic.
Timing Verification: Uses static timing analysis to verify performance.
OpenLane ASIC Flow
OpenLane integrates various open-source tools to facilitate the entire ASIC design flow:

Synthesis Exploration Utility: Helps determine the best synthesis strategy based on design metrics.
Design Exploration Utility: Sweeps design configurations and generates reports to identify optimal settings.
Additional Steps
Design for Test (DFT): Optional step using tools like Fault.
Physical Design: Managed by OpenROAD, handling aspects like antenna effects and detailed placement.
Sign-off Tools
STA: OpenSTA for timing analysis.
DRC: Magic VLSI for design rule checking.
LVS: Netgen for layout vs. schematic verification.
## Screenshots

