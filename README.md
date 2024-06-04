




[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)



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



## Day 1


The RTL to GDSII flow is a process in VLSI design that converts an RTL
description of a digital circuit into a physical layout ready for fabrication. It
involves stages like RTL synthesis, floor planning, placement, routing, and
ultimately generating the GDSII file format, which contains the layout data.
This meticulous process ensures the final IC layout accurately reflects the
desired functionality and meets fabrication requirements


![fggdgf](https://github.com/AnoushkaTripathi/DIGITAL_VLSI_SoC_Design_and-planning_Training/assets/98522737/d256eedc-480c-4997-ad78-8e5438094956)

![designabstraction](https://github.com/AnoushkaTripathi/DIGITAL_VLSI_SoC_Design_and-planning_Training/assets/98522737/20b95cf6-161a-4b5e-95c0-0e89af44ce67)


The “Y chart” in VLSI (Very Large Scale Integration) refers to a graphical
representation that illustrates the interrelation between the design,
fabrication, and test processes in semiconductor manufacturing. It is called
the “Y chart” because of its shape, which resembles the letter “Y”

## Overview of QFN-48 Chip, Pads, Core, Die, and IPs

VSD Squadron Board: This is a VSD Board that you can see below. Here, we concentrate more on the enclosed region, which houses the "Microprocessor," which we will use the RTL to GDS flow to design from the abstract level to the fabrication level.
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/e7140942-4235-4659-8b90-a2e1911d97d5)


## Introduction to IC Design components and terminologies

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/1f4b8c57-cb88-4b6f-8780-746b22c76cb7)
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/97662e7a-1aef-4ce1-816a-46d0bac73ddc)
- Core

   A core is an area in the chip where the fundamental logic of the design is placed. It encapsulates all the combinational circuit, soft and hard IPs, and nets.

- Die

   Die is an area of chip that encapsulates the core and IO pads. Die is imprinted multiple times along the silicon area or wafer to increase the throughput.

- IO Pads

   IO pads are the pins that act as the source of communication between core and the outside world. Pad cells surround the rectangular metal patches where external bonds are made. input,output and power pad.



- IPs

    Foundary IPs are manually designed or need some human interference (or intelligence) essentially to define and create them like SRAM, ADC, DAC, PLLs.
- PDKs

    PDKs are interface between foundary and design engineers. PDKs contains set of files to model fabrication process for the design tools used to design IC like device models, DRC, LVS, Physical extraction, layers, LEF, standard cell libraries, timing libraries etc. SkyWater 130nm is the PDK used in this workshop specifically sky130_fd_sc_hd and openLANE is built around this PDK.

## Introduction to RISC-V
ISA: ISA is known as "Instruction Set Architecture".It is merely a means of interacting with the computer. Generally speaking, we use coding languages like C, Java, and others to write programs that must be performed by the system, but machines are unable to comprehend these languages. Here's when ISA enters the picture. The written codes will be translated from assembly language to binary, or machine comprehensible language, using ISA. The RISC V ISA is the most recent ISA to be published, and it serves this purpose.
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/32072838-15b1-463a-b39c-35f0ca6ec3b1)


## From Software Applications to Hardware

In real life, we typically interact with application software (apps) to communicate with hardware. But how does this process work exactly? Between the application software and the hardware, there is a layer called system software. The applications interface with the system software, which then translates them into a language the hardware can understand, namely binary language.

The system software is comprised of several layers:
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/0a1902fe-dc15-4ae8-991f-aad281c09e41)


  -  Operating System (OS): In addition to general tasks like handling input/output operations, memory allocation, and low-level system functions, the OS translates application software into corresponding code in languages such as C, C++, or Java.

   - Compiler: The compiler takes the code produced by the OS and converts it into an instruction set (e.g., .exe files). These instructions are tailored to the specific type of hardware being used.

   - Assembler: The assembler then converts these executable files into binary language, which the hardware can understand and execute to perform the desired operations.

##  OpenLane: Introduction to Components of Open-Source Digital ASIC Design

To design an open-source digital ASIC, several key components are required:
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/3ee3cd37-d8c7-4df7-9780-e53e73c79f74)

   - RTL Designs
- EDA Tools
- PDK Data

What are RTL Designs?

RTL (Register-Transfer-Level) design is a critical phase in the VLSI design flow, focused on creating electronic circuits using integrated circuits (ICs). It specifies a digital circuit by describing the flow of digital signals between hardware registers and the logical operations performed on these signals.
What are EDA Tools?

EDA (Electronic Design Automation) tools are software applications used to design and verify the functionality of integrated circuits (ICs). They ensure that the IC meets the required performance and density specifications.
What is PDK Data?

PDK (Process Design Kit) is a set of files used to model a fabrication process for EDA tools during IC design. This kit includes:

  -  Process Design Rules: DRC (Design Rule Check), LVS (Layout Versus Schematic), PEX (Parasitic Extraction)
 Device Models
Digital Standard Cell Libraries

 I/O Libraries

## Simplified RTL to GDS Flow

The simplified RTL to GDS flow begins with an RTL file and, through a series of stages, produces a GDS file, which can be sent to a foundry for fabrication. The steps in the RTL to GDS flow include:
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/dfcf7210-a2de-4613-912c-f1c034294cbe)



    Synthesis:
        The RTL file is converted into a circuit using components from the Standard Cell Library.
        Standard Cells in the library have a regular layout with the same height but different widths.
        Each cell has various models based on electrical, HDL, Spice, and layout (abstract and detailed) parameters.

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/599e076a-2457-4a68-9a08-3b633402d22e)

    Floor Planning & Power Planning:
        Floor Planning: Determines the position of components on the chip to minimize area, including the placement of I/O pins, ports, and pads.
        Power Planning: Designs the power supply network (VDD and GND) using power rings, power straps, and power pads, typically on the top metal layers for minimal resistance and delay.
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/eb783ee4-4d8f-4c51-903f-2b9604260995)

    Placement:
        Components are placed within the designated areas from the floor planning stage.
        Standard Cells required in the design are also placed within their cell boundaries.
        Placement is performed in two stages: Global Placement (where cells may overlap) and Detailed Placement (where cells are optimally placed following placement rules).

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/dc935b28-2c27-4c45-8975-43f0e967c2a7)


    CTS (Clock Tree Synthesis):
        Clock routing is performed before signal routing to address clock skew, the difference in time for the clock to reach various destinations.
        Symmetric Tree Structures (H-tree, I-tree, X-tree) are used to eliminate clock skew.

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/66062429-e200-4679-8c61-bbd253ee44fd)


    Routing:
        After clock routing, signal routing is performed using the remaining metal layers.
        Routing is divided into Global Routing (generates a routing guide based on PDK instructions) and Detailed Routing (actual routing according to the guide).
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/6aa48de1-e1b3-4752-b38a-e0b996cf4aae)


    Sign-off:
        Once routing is completed, the chip undergoes various checks during the sign-off stage:
            Physical Verification Checks: Design Rule Check (DRC) and Layout vs. Schematic (LVS). DRC verifies design rule compliance, while LVS ensures functional correctness against the gate-level netlist.
            Timing Checks: Static Timing Analysis (STA) checks the design for timing violations.

## Introduction to OpenLANE Detailed ASIC Design Flow

The image illustrates the detailed ASIC design flow in OpenLANE. The process begins with the Design RTL, which undergoes RTL synthesis using Yosys and ABC to produce an optimized gate-level netlist. This netlist is then subjected to STA (Static Timing Analysis) to check for timing violations. Following STA, Design for Test (DFT) is performed, though this step is optional and uses the FAULT tool.
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/837ca897-9005-40c0-acda-a4adb68836bf)

OpenLane  started as an Open Source Flow for a true Open Source Tape-out experiment.It was from e-fabless.It is a platform which supports different tools such as Yosys,OpenRoad,Magic,KLlayout and some other Open source tools.It integrates the various steps of Silicon Implementation and abstracts it. At e-fabless they have an SOC family called Strive. Strive is a family of open everything SOCs having Open PDK, Open RTL, Open EDA.

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/6265bb94-5c2a-42d8-82e8-67bd2feef055)



FAULT (for DFT) includes:

   - Scan Insertion
   - Automatic Test Pattern Generation (ATPG)
   - Test Pattern Compaction
   - Fault Coverage
   - Fault Simulation

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/607eb8bf-fe92-4e83-9757-e28598f3a93d)


After DFT, the next phase is Physical Implementation, also known as Automated Place and Route (PnR), using OpenRoad.

OpenRoad (for Physical Implementation) includes:

    Floor/Power Planning
    End Decoupling Capacitors and Tap Cells Insertion
    Placement: Global and Detailed
    Post-Placement Optimization
    Clock Tree Synthesis
    Routing: Global and Detailed

During PnR, Logic Equivalence Checking (LEC) must be performed for each design change to ensure the functionality remains unchanged after netlist modifications. An important step during physical implementation is the "Fake Antenna Diodes Insertion Script."

Dealing with Antenna Rule Violations:
When a metal wire segment is fabricated, it can act as an antenna. Reactive ion etching can cause charge accumulation on the wire, potentially damaging transistor gates during fabrication.

Solutions:

Bridging: Attaching a higher layer intermediary, which requires router awareness.
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/f4cf5f24-135e-443c-befc-cf86aed71aac)


Add antenna diode cell to leak away the charges. Antenna diodes are provided by the SCL. For this we took a preventive approach.
Add a Fake antenna didoe next to every cell input after placement.  Run the Antenna Checker(Magic) on the routed layout.If the checker reports violation on the cell input pin, replace the fake diode cell by a real one


And at the end, we perform Physical Verification. Which includes DRC(Design Rule Checking) , LVS(Layout Vs Schematic). Along with the P.V we also performs STA to check for timing violations in the design.

MAGIC is used for DRC and SPICE Extraction from Layout.

MAGIC and Netgen are used for LVS by comparing Extracted SPICE by MAGIC and Verilog Netlist.

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/0fdee7ae-caf0-428a-8136-5dd34a0938e4)






# RTL2GDS OpenLANE ASIC Flow Practical implementation

## Day 1 Labs

![Screenshot from 2024-05-27 08-56-26](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/e1e4228b-42a1-48b1-bab2-0b202e482c84)


1.  Understanding the use of various linux commands

  -  pwd : It displays the present working directory and its path.

   - cd : Using this command we can move in both ways in the directory tree.

- ls : It lists all the sub-directories and files present in the current directory.

 - mkdir : Using this command, we can create a new directory.

  -  rmdir : Using his command, we can delete an existing directory.

 -   rm : This command is used to delete the files.

  -  help : using this command we can know the working of any command.

   - clear : This command clears the terminal.



  Key Files and Directories:

    libs.ref: Houses the design libraries, including standard cells, IO cells, and other related files.
        lef: Library Exchange Format files describing the cell layouts.
        lib: Liberty files for timing and power analysis.
        gds: GDSII files containing the graphical layout of the cells.
        verilog: Verilog models of the cells.

    libs.tech: Contains technology files tailored for specific EDA tools.
        magic: Magic technology files.
        klayout: KLayout technology files and layer properties.
        ngspice: SPICE models for circuit simulation.
        openroad: Files for OpenROAD flow.
        drc: Design Rule Check files.
        lvs: Layout Versus Schematic check files.
        pex: Parasitic Extraction files.





![Screenshot from 2024-05-28 10-58-19](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/7a59a63e-171f-42d0-8ba0-f3947915923e)

To run in interactive mode (step by step mode)

    bash-4.2$ ./flow.tcl -interactive
    
    
`Package import and check`

    % package require openlane

`Prepare design`

To prepare and setup the design

    % prep -design picorv32a



![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/cb2fcb1f-989f-4f64-9713-9b8f94e23131)

Once the preparation is complete, a new directory with the current date will be generated within the “runs” folder. Inside this directory, all the necessary subdirectories for storing results, reports, and other relevant data will be created.

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/c2017d45-9c58-48ae-a670-95990cf51a81)


The preparation step involves the following actions for the picorv32a design within the openLANE flow:

**Directory Structure Setup:**

A new directory structure is created to organize the design files.
This structure includes subdirectories for different components (e.g., results, reports).

- LEF Merging:
The technology LEF (.tlef) and cell LEF (.lef) files are merged into a unified format.The technology LEF contains layer information (such as metal layers), while the cell LEF contains cell informations.
- Design Placement:
All design-related files are placed under the designs directory.
This ensures that the necessary files are organized and accessible during subsequent steps.

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/7fef32f0-2f61-4505-9f71-d4d457393105)


| `config.tcl`	 | contains the configurations used by openLANE |                      
| :-------- | :-------                                     | 
| `src`      |  contains verilog files and constraints file|




![Screenshot from 2024-05-28 10-20-40](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/498fa493-f289-4241-ae6e-58ea967f12a6)

` Synthesis `
   % run_synthesis

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/6eb7ec6b-9857-4c84-ab1e-eab611a6201c)

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/fa1c6b93-38b0-48e1-a76d-766b20e77884)


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/717ae07d-12ad-4e3a-9a0c-6a87d41228f4)

![Screenshot 2024-05-28 124638](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/c13c800c-7837-4619-a007-6cd9302a4927)


# Day 2

## Good FloorPlan Vs Bad FloorPlan and Introduction to Library Cells
Chip FloorPlanning Considerations

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/441d1181-07f7-400e-ac18-647b45307664)

Utilization Factor and Aspect Ratio
In order to find out the Utilization Factor and Aspect Ratio, first we need to know how to define height and width of core and die areas.

- Core is an area in a chip which is used to place all the logic cells and components in a chip. It is the place where logic lies in a chip.

- Die is an area that encircles the core area and used for placing I/O related components.


The height and width of core area will be decided by the netlist of the design. It will be based on the no.of components required in order to execute the logic and the height and width of the die area will be dependent on the core area height and width.

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/1b589248-1388-4bab-a098-e19fe2f4fa8e)

For example, lets consider a netlist that is having two logic gates and two flipflops each having area of 1 sq.unit. The netlist contains 4 elements and the minimum total area required for the core area will be 4 sq.units.

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/9aea0843-89ab-4fc0-8ec6-9ad6f38d406f)

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/ca37db25-2ab9-4254-a210-9520e97eb3bd)


*Utilization Factor :*  Utilization Factor is defined as "The ratio of the core area occupied by the netlist to the total core area".For a good FloorPlan, The Utilization Factor should never be '1' because when the Utilization factor becomes '1' , there will be no place for adding additional logic if needed and it will be considered as a bad FloorPlan.


`Utilization Factor = (Area occupied by netlist / Total core area)`

*Aspect Ratio :*  Aspect Ratio is defined as "The ratio of Height of the core to the width of the core". If the Aspect ratio is '1' , then the core is said to be in a square shape and other than '1' the core will be a rectangle.

`Aspect Ratio = (Height of the core / Width of the core)`

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/7997122f-8e7d-401e-a2b2-1b42e12987d1)


In this case, when calculated

- Utilization factor = (4 squnits)/(4 squnits) = 1

- Aspect Ratio = (2 units)/(2 units) = 1 //The core is in a square shape.

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/c7dceb3d-4a84-41b0-ac5f-e328d8f5f63e)

In this case, when calculated

- Utilization factor = (4 squnits)/(8 squnits) = 0.5

- Aspect Ratio = (2 units)/(4 units) = 0.5 //The core is in a rectangular shape.


# Day 2 Labs
# Steps to run floorplan using OpenLANE

For Floorplan to run smoothly, as a designer we should take care of some switches, that makes changes to the floorplan when changed. For example Utilization factor and aspect ratio are also part of switches. Designer should cross check these switches before initializing floorplan whether they are alligned with the project or not. Below image shows different types of switches in floorplan stage.

    % run_floorplan


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/35118e28-4c6d-4e1e-b8a8-d36d01f26078)

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/67e04602-0aaf-4704-8e23-d0f943487d3c)



![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/aff6e83c-7e78-4856-acec-a51545f8585c)

 Once the floorplan is complete, you can review the generated report to assess aspects such as die area. However, to visualize the design in a graphical user interface (GUI), you should use the MAGIC tool.


 ![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/0a9df52d-68a2-465a-937f-1d0bfdf6f6d5)


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/e38856b0-f107-464f-ae4a-81684d7fa40d)

Review Floorplan layout in magic
## Design Alignment Instructions

### Centering the Design:
1. Press `S` to select the entire design.
2. Press `V` to vertically align it to the middle of the screen.

### Zooming In on a Specific Area:
1. Left-click and drag to select the desired region.
2. Right-click to bring up the context menu.
3. Press `Z` to zoom in on the selected area.

### Getting Details of a Cell:
1. Move your cursor to the cell of interest.
2. Press `S` to select the cell.
3. In the `tkcon` window, enter the command "what"  to display cell details.


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/bb1aafc8-34f5-4705-86f6-763950dbe4e0)


## Placement in VLSI Design

Placement plays a crucial role in VLSI (Very Large Scale Integration) design. It involves determining the physical locations of standard cells or logic elements within a chip or block. Let's break it down:

1. **Global Placement:**
   - Global placement assigns general locations to movable objects (cells).
   - Some overlaps between placed objects are allowed during this stage.
   - The goal is to achieve a rough layout that satisfies area constraints.

2. **Detailed Placement:**
   - Detailed placement refines the object locations obtained from global placement.
   - It enforces non-overlapping constraints and ensures that cells are placed on legal cell sites.
   - The quality of detailed placement significantly impacts subsequent routing stages.

`magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &`

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/1642d8ce-8285-4eb9-a20f-30c230bcf22e)



## VLSI Design Documentation

### Inputs
| Item                    | Description                                                                                   |
|-------------------------|-----------------------------------------------------------------------------------------------|
| PDKs                    | Process Design Kits (PDKs) provide technology-specific information for chip design.          |
| DRC and LVS rules       | Design Rule Check (DRC) and Layout vs. Schematic (LVS) rules ensure layout compliance.        |
| SPICE models            | These models describe transistor behavior for circuit simulation.                             |
| Library & User-defined specs | Custom libraries and specifications specific to your project.                                 |

### Design Steps
1. **Circuit Design:**
   - Create the logical schematic of your circuit.
   - Define the functionality and connections of standard cells.

2. **Layout Design:**
   - Use layout tools (e.g., MAGIC) to create the physical layout.
   - Follow design rules and guidelines for placement and routing.

3. **Characterization using GUNA:**
   - Perform timing, power, and noise characterizations.
   - Validate the design against specifications.

### Outputs
- **CDL (Circuit Description Language):** A textual representation of the circuit.
- **GDSII:** The layout file in GDSII format for fabrication.
- **LEF (Library Exchange Format):** Contains information about cell sizes, pin locations, and other details.
- **Spice Extracted Netlist:** Includes parasitic information for circuit simulation.
- **Timing, Noise, and Power Libraries:** Generated during characterization.




# Day 3 labs


## CMOS Inverter Simulation with ngspice

This guide demonstrates how to create a basic CMOS inverter netlist, perform DC and transient analyses using ngspice, and understand key static and dynamic characteristics.

## Static Characteristics

1. **Switching Threshold (Vth):**
   - The voltage at which the inverter transitions from the high state (logic 1) to the low state (logic 0).
2. **Input Low Voltage (Vil):**
   - The maximum input voltage considered as logic 0.
3. **Input High Voltage (Vih):**
   - The minimum input voltage considered as logic 1.
4. **Output Low Voltage (Vol):**
   - The voltage at which the output transitions from high to low.
5. **Output High Voltage (Voh):**
   - The voltage at which the output transitions from low to high.
6. **Noise Margins:**
   - The voltage range between Vil and Vol (low noise margin) and between Vih and Voh (high noise margin).

## Dynamic Characteristics

1. **Propagation Delays:**
   - The time taken for the output to change after a change in input.
2. **Rise Time (tr):**
   - The time taken for the output to transition from Vol to Voh.
3. **Fall Time (tf):**
   - The time taken for the output to transition from Voh to Vol.



# Design library cell using Magic Layout and ngspice characterization
## Creating Standard Cell Layout

1. **Design the Inverter Layout:**
   - Use a layout tool (such as MAGIC) to create the inverter layout.
   - Follow process-specific design rules and guidelines.
   - Place standard cells (transistors, metal layers, etc.) based on the logical schematic.

2. **Extraction Process:**
   - After layout creation, extract parasitic capacitances and resistances.
   - In the `tkcon` window, execute the command `extract all`.
   - This generates an extracted file with parasitic information (e.g., capacitances, interconnect resistance).
   - The extracted file is saved in the `vsdstdcelldesign` directory.

3. **SPICE Netlist:**
   - Use the extracted data to create a SPICE-compatible netlist (usually in `.sp` or `.cir` format).
   - Include transistor models, capacitances, and resistances.
   - Use this netlist for simulation in tools like ngspice.

Magic layout view to cmos inverter
To get the cell files refer  
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/ee73ffe3-68fa-4d11-b433-841548ff7831)
## images

![Screenshot from 2024-05-27 12-02-21](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/9c8c0753-a272-485c-a7e4-!c8739c8b9bbb)





![Screenshot from 2024-05-28 11-55-32](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/30da9be7-fd12-42ac-a5b3-09bc4cc3f2a3)

![Screenshot from 2024-05-28 11-55-37](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/93026d4a-98de-4f8f-8177-f11f92d5ca65)


![Screenshot from 2024-05-28 11-55-18](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/cdd6bea7-5ab7-47aaae6a-93e03f566d4d)
![Screenshot from 2024-05-28 11-55-28](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/bfdca5b6-2932-4bf7-982b-cfe7469f15d4)



![Screenshot from 2024-05-28 11-57-45](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/6d2b129e-5a19-489e-a39a-454cc2cbb787)
![Screenshot from 2024-05-28 12-19-46](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/37a8efd7-937c-4ecf-a6af-0af3b09aaae7)
![Screenshot from 2024-05-28 12-20-00](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/abcd5dda-307a-4366-9e33-e989094e7027)
![Screenshot from 2024-05-28 12-29-54](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/088ec513-3b9b-429e
-a06a-af1497d6baa8)
![Screenshot from 2024-05-28 12-36-02](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/7cd36088-0d0e-4af7-9e0a-942e301452ee)
![Screenshot from 2024-05-28 12-31-13](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/dd068a2a-ebde-4bcf-9d90-b31f6c28b607)
![Screenshot from 2024-05-28 12-44-35](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/b70c0548-8785-4b8e-b1cf-d82f6f69532a)

![Screenshot from 2024-05-28 13-26-29](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/074f534b-ad6c-485f-b25e-43019f6d4075)
![Screenshot from 2024-05-28 13-29-02](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/1efa9293-cbf4-41fa-9313-065fd53b8e34)
![Screenshot from 2024-05-28 13-31-39](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/844351cc-6e33-400d-ac06-f114761276d8)
![Screenshot from 2024-05-28 13-44-30](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/fd49b96b-ad7b-4ecf-a18b-db688dc89e94)

![Screenshot from 2024-05-28 14-06-47](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/39e2aa9d-e13c-4a89-a87f-46bd274f3b8b)
![Screenshot from 2024-05-28 14-35-44](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/384b2e37-8f12-4638-9a08-016a86225a05)
![Screenshot from 2024-05-28 15-05-32](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/f54f64e4-69ee-4824-a44d-c705609b6017)

![Screenshot from 2024-05-28 16-09-13](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/13ac49a7-0174-4344-a1c3-fb4801228d47)

![Screenshot from 2024-05-28 16-22-07](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/f4a2d2eb-770b-4a07-b807-75c7e3067f06)
![Screenshot from 2024-05-28 16-27-40](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/263f4790-9399-436b-ad2d-3ed91ac544f3)
![Screenshot from 2024-05-28 16-27-48](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/ec5283f3-1dfa-4f4c-85a2-5bfd953f6563)
![Screenshot from 2024-05-28 16-59-56](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/16f6c74d-ce13-4130-a59f-23fa4a2b2663)
![Screenshot from 2024-05-28 17-09-32](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/45e21b01-1f71-480b-8f5f-1d9cd0a87f27)
![Screenshot from 2024-05-28 17-17-59](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/2049ac06-ec79-402c-bd95-73023d1b0372)
![Screenshot from 2024-05-28 17-27-43](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/4b5bd47b-8174-4820-8a3f-a780c0d02235)
![Screenshot from 2024-05-28 17-27-48](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/7f320f36-b16c-4bc6-9e1a-7fb373e7716d)
![Screenshot from 2024-05-28 19-21-27](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/1ba8ff89-f095-4028-b9bb-838e6d25fe04)
![Screenshot from 2024-05-28 21-56-33](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/968e3983-8993-48b8-85de-c2761fb293fe)
![Screenshot from 2024-05-29 10-07-35](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/9d5ecf41-f1e7-4cac-9971-ba2baf502152)
![Screenshot from 2024-05-29 16-15-04](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/54f8f984-a98b-4232-bc88-12e6471deb2e)
![Screenshot from 2024-05-29 17-09-16](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/a9e14d2b-b6a7-485c-b46e-1695f8cab04e)
![Screenshot from 2024-05-29 19-53-35](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/83874dcb-e669-4b85-851b-c8e45f2d73c8)



![Screenshot from 2024-05-29 20-10-40](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/ceaad2a4-d1cc-4b9e-8886-70ed12337f6d)

![Screenshot from 2024-05-29 21-48-11](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/c751f16c-35c7-4cf6-af59-71fc8f896afe)

![Screenshot from 2024-05-29 22-28-19](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/3e5f8b74-ff52-48b7-8606-35b46e226858)
![Screenshot from 2024-05-30 07-44-41](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/e9d88e51-2da3-4b5b-8321-91e8f42921db)

![Screenshot from 2024-05-30 07-44-41](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/c8702f9c-bce0-4f08-a00f-83655dd77261)
![Screenshot from 2024-05-30 14-57-45](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/03b33315-ba0b-47dc-938a-9cebfbf97d95)
![Screenshot from 2024-05-31 21-09-00](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/dae73ed5-33cb-49db-a0a2-a34251da2cdc)
![Screenshot from 2024-05-31 21-42-57](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/9f3aac51-d968-4e56-911b-70bbd848d0d7)
![Screenshot from 2024-06-01 09-32-45](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/123272f2-f912-45bc-9a6c-f9d810d00544)

![Screenshot from 2024-06-01 10-00-02](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/3f610bcb-c0d7-4b38-a64b-8cfa1f95a07e)
![Screenshot from 2024-06-01 10-11-39](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/6ed4f871-ab9d-4976-b043-011527097a76)
![Screenshot from 2024-06-01 10-13-22](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/5355353f-3929-41d1-b481-01094c6a14c2)
![Screenshot from 2024-06-01 10-31-29](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/f7c98dbc-6f08-4d4c-81bf-fb0145f8846e)
![Screenshot from 2024-06-01 10-55-53](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/c8450b9e-1582-4056-a57e-b633066839b7)
![Screenshot from 2024-06-01 11-39-35](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/03f62ddc-dd56-43f0-ab15-378f35d5c70f)
![Screenshot from 2024-06-01 11-43-39](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/3ab84f5a-93cc-45cd-9e67-c44ddf63cf08)
![Screenshot from 2024-06-01 12-00-26](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/8cf9d022-0e8d-467e-81b3-adfc9ee3b33e)
![Screenshot from 2024-06-01 12-20-30](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/b0a90c31-8965-4253-8945-0c3550819825)
![Screenshot from 2024-06-01 12-56-04](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/b100de53-4455-4984-87d2-d1b8380ca771)
![Screenshot from 2024-06-01 14-59-28](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/466adafc-f6b8-459f-8588-355433e06c0c)
![Screenshot from 2024-06-01 14-59-39](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/1308a875-21d4-4e0f-9c66-1ccece31ac91)
![Screenshot from 2024-06-01 15-01-46](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/9ff451c7-f2aa-4206-8653-2d52f652ded4)
![Screenshot from 2024-06-01 15-04-35](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/613f1a72-ac92-4bcd-aa7e-819cde146f5a)
![Screenshot from 2024-06-01 15-29-33](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/a489c4e0-db50-4233-9118-306ce76a4589)
![Screenshot from 2024-06-01 15-42-19](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/f0a17b45-8801-4035-83fa-03ccb31a9fb3)
![Screenshot from 2024-06-01 21-36-20](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/5cb3b762-d90b-4f72-99dc-d5f9acf3c8f7)
![Screenshot from 2024-06-01 22-46-39](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/68ac298e-e500-47fa-80b4-00f824894490)
![Screenshot from 2024-06-01 22-52-03](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/e843d6a9-1b74-4726-ac55-a4f1284e7fb3)
![Screenshot from 2024-06-01 22-52-19](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/c183bd8e-681a-4f90-9b5a-12e3cb2829e7)
![Screenshot from 2024-06-02 15-05-17](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/458c0d7b-c032-49a2-ace2-a7d06ae71658)
![Screenshot from 2024-06-03 08-06-08](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/6b098b24-dcde-460f-beb1-6b23e7bbcf79)
![Screenshot from 2024-06-03 12-29-38](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/be978678-6dea-403a-b932-2f0efbf95074)
![Screenshot from 2024-06-03 12-29-43](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/c56a4082-b2f2-4028-aa40-f5e012b5fb46)
![Screenshot from 2024-06-03 13-56-29](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/4f1d235d-dc4a-4147-80c4-857712a245aa)
![Screenshot from 2024-06-03 13-57-08](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/a9793469-71e5-4443-bf9e-210c7f35b802)
![Screenshot from 2024-06-03 15-06-59](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/db0352ca-b2e1-40b3-adf0-6b1c4d66d964)
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/5c07b47f-5c19-434b-a873-1ab6cbe8898c)

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/eb2ed4b2-5032-435c-89ff-2ffe8766aa8b)
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/7d32b18c-5525-40b5-a4a9-c2ea37bee739)
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/0a9296b2-d901-4cd9-a4b1-f5345bd49a2c)
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/66f08e88-2412-479f-9304-13b998b6c47f)
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/27ece5cb-99e9-4416-93b3-efad07b54434)
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/e61d9dce-44da-4a1d-84d2-a0d03477a1da)
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/2318b46f-a1ef-43c7-b3c9-80f37f95f441)
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/fea0bb21-91f0-48e1-8cfd-2cf413a8b127)

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/8de7cb89-f819-4692-b7ea-8fada6d76f2a)
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/26edb0a7-2af8-404a-bafd-b50128a58c74)
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/043932b1-8791-4c23-8393-bdb82d72c482)
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/4377e411-8fcf-4f90-b12a-bb28718fd198)

## Acknowledgements

 - [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
 - [Awesome README](https://github.com/matiassingers/awesome-readme)
 - [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)


## API Reference

#### Get all items

```http
  GET /api/items
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |

#### Get item

```http
  GET /api/items/${id}
```


#### add(num1, num2)

Takes two numbers and returns the sum.

