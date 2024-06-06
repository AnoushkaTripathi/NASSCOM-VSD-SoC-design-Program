




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


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/bc3a90f7-2892-465b-aab6-dee1aca0a26d)


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

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/a105d2e9-d983-4522-bfdb-dab5bbcaa5db)


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




## Day 3


# Inverter Characterization using Sky130 Model Files


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


## Introduction to LEF Files in VLSI Design
In VLSI (Very Large Scale Integration) design, LEF (Library Exchange Format) files play a crucial role in interfacing between layout tools and place-and-route (PnR) tools. Here’s what you need to know:

Purpose of LEF Files:

The entire layout information of a block (whether it’s a macro or a standard cell) is not necessary for PnR tools.
PnR tools require minimal information, including the PR boundary (bounding box) and pin positions.
LEF files provide an abstract representation of the block, exposing only the essential details needed for PnR.



| Cell LEF	 | Abstract view of the cell which holds information about PR boundary, pin positions and metal layer information.  |
|---------------|---------------|
| Technology LEF | Holds information about the metal layers, via, DRC technology used by placer and router.|

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/ac0ac635-a5dc-4531-a065-a6ec16dbab3c)


# VLSI Routing: Tracks and Routes

In VLSI design, understanding tracks and routes is essential for successful interconnect design. Let's break it down:

## Tracks

- **Definition:**
  - Tracks represent predefined horizontal and vertical paths on each metal layer.
  - They serve as guidelines for routing wires (metal traces) within a chip.

- **Purpose:**
  - Tracks help maintain uniform spacing and alignment during routing.
  - They simplify the routing process by providing fixed paths.

## Routes

- **Definition:**
  - Routes are the actual metal traces that carry signals (such as interconnects or wires).
  - These traces can be placed over the tracks, following specified routing rules.

- **Functionality:**
  - Routes connect different components (cells) within the chip.
  - They form the wiring network for data flow.

## `tracks.info` File

- The `tracks.info` file:
  - Provides information about horizontal and vertical tracks available on each metal layer.
  - Specifies pitch, spacing, and other relevant details necessary for efficient routing.
# Day 3 labs



Magic layout view to cmos inverter
To get the cell files refer  
 [vsdstdcelldesign](https://github.com/nickson-jose/vsdstdcelldesign) 

To extract the parasitics and characterize the cell design use below commands in tkcon window.

    extract all
    ext2spice cthresh 0 rthresh 0
    ext2spice

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/3071b576-84ac-420c-9ad8-9c8afac1f35f)

Modify the file according to 

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/d6f08b62-ae42-4283-abd4-23e9dbef5637)

Now the next step is to run the SPICE file in ngspice tool by using command ngspice sky130_inv.spice

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/9a095bc2-e916-4821-ba31-e48643c4ba97)



# Inverter Characterization using Sky130 Model Files

In this lab, we will characterize the inverter using ngspice and Sky130 model files. The goal is to extract key parameters from the simulation results.

## Parameters to Characterize

1. **Rise Time:**
   - The time taken for the output waveform to transition from 20% to 80% of its maximum value.
   - Using data points:
     - x0 = 6.16138e-09, y0 = 0.660007
     - x1 = 6.20366e-09, y1 = 2.64009
   - Rise time = x1 - x0 = 0.0422 ns

2. **Fall Time:**
   - The time taken for the output waveform to transition from 80% to 20% of its maximum value.
   - Using data points:
     - x0 = 8.04034e-09, y0 = 2.64003
     - x1 = 8.06818e-09, y1 = 0.659993
   - Fall time = x1 - x0 = 0.0278 ns

3. **Propagation Delay:**
   - The time taken for a 50% transition at the output (0 to 1) corresponding to a 50% transition at the input (1 to 0).
   - Using data points:
     - x0 = 2.18449e-09, y0 = 1.64994
     - x1 = 2.15e-09, y1 = 1.65011
   - Propagation delay = x1 - x0 = 0.034 ns

4. **Cell Fall Delay:**
   - The time taken for a 50% transition at the output (1 to 0) corresponding to a 50% transition at the input (0 to 1).
   - Using data points:
     - x0 = 4.05432e-09, y0 = 1.65
     - x1 = 4.05001e-09, y1 = 1.65
   - Cell fall delay = x1 - x0 = 0.0043 ns

## LEF File Creation
Now that we have successfully characterized the inverter, the next step is to create a LEF (Library Exchange Format) file.


wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz



**VLSI Layout Geometries and DRC Errors**

In this section, we explore independent example layout geometries (M3.1, M3.2, M3.5, and M3.6) and highlight the specific DRC (Design Rule Check) errors associated with each:

1. **M3.1 (Metal Width DRC):**
   - Violation: The metal trace width in M3.1 is below the specified minimum width threshold.
   - Error: Metal width does not meet design rules.

2. **M3.2 (Metal Spacing DRC):**
   - Violation: The distance between adjacent metal traces in M3.2 does not meet the required spacing.
   - Error: Metal spacing violation.

3. **M3.5 (Via Overlapping DRC):**
   - Violation: The vias in M3.5 overlap with each other.
   - Error: Via overlapping issue.

4. **M3.6 (Minimum Area DRC):**
   - Violation: The enclosed area within M3.6 does not meet the specified minimum area requirement.
   - Error: Minimum area violation.

Use the command `magic -d XR` to open the Magic tool

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/314d5337-9add-4e42-8f0c-7bd31439829b)

# Using Magic Tool: Filling an Area with Metal 3 and Creating a VIA2 Mask

In this guide, we'll demonstrate how to fill a selected area with metal 3 and create a VIA2 mask using the Magic layout tool.

## Steps:

1. **Select an Area and Fill with Metal 3:**
   - Open the Magic GUI.
   - Select the desired area on your layout.
   - Guide the pointer to the metal 3 layer.
   - Press `P` to fill the selected region with metal 3.

2. **Create the VIA2 Mask:**
   - Open the `tkcon` terminal within Magic.
   - Type the command: `cif see VIA2`.
   - The metal 3-filled area will now be associated with the VIA2 mask.


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/7068a406-8138-4245-aa7e-0b99659f74b9)

## **Lab exercise to fix Poly-9 error in Sky130 tech file**


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/4010493f-00a7-4adc-9659-931f505036ba)


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/d06ec717-0daa-426c-a74d-badb8432d20e)

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/71f3aeac-5094-4ba9-97dd-25af197fe039)


Commands to run in tkcon window

     # Loading updated tech file
       tech load sky130A.tech

     # Must re-run drc check to see updated drc errors
      drc check

     # Selecting region displaying the new errors and getting the error messages 
      drc why


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/06869006-06a0-4e9a-a81a-3a9c1e70ab49)

Incorrectly implemented difftap.2 simple rule correction


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/b33b6e9b-2bbd-489e-a345-7baa6f243850)

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/d6cd4fb0-ef01-4c4d-83e7-0d46649e778f)


Insert new commands  in sky130A.tech file to update drc

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/4e68ee9e-baf0-4653-a3ae-38e85e3f9245)
 
 Screenshot of Fixed DRC 


 ![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/e91a3f3c-42c6-4383-b51c-f5fe3bd82e74)


## DRC error as geometrical construct

N well rules 

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/2ee6e495-203d-415a-bc13-5a817b401abb)


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/19362396-33bc-4d03-88c3-783aa85dfd37)

New commands inserted in sky130A.tech file to update drc

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/5c21a6ef-6fa4-4a52-b835-f1cde0c1ee34)

Updated Tech file 

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/681097ff-f036-43dc-9851-b2809a9a64d2)

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/7d6951b0-5ae4-46fe-a02b-724e555fa700)

# Day 4 : Pre-layout timing analysis and importance of good clock tree 

# Timing Modeling Using Delay Tables and Converting Grid Info to Track Info

In this section, we'll explore timing modeling using delay tables and the process of converting grid information to track information. Let's break it down step by step:

## Timing Modeling with Delay Tables

1. **Delay Tables:**
   - Delay tables provide information about the delay (propagation time) of signals through various components (such as gates, wires, and interconnects).
   - These tables help estimate signal arrival times and ensure proper timing in the design.

2. **Usage:**
   - During the physical design process, delay tables are used to model the behavior of standard cells, macros, and other components.
   - They guide the placement and routing tools to optimize signal paths for timing closure.

## Converting Grid Info to Track Info

1. **Purpose:**
   - In physical design, we need to convert grid information (such as rows and columns) into track information.
   - Tracks represent predefined horizontal and vertical paths on each metal layer.

2. **Considerations:**
   - When designing standard cells, keep the following in mind:
     - Input and output ports should align with the intersection of vertical and horizontal tracks.
     - The standard cell's width should be an odd multiple of the track pitch, and its height should be an odd multiple of the vertical track pitch.

3. **LEF File Extraction:**
   - To proceed further, we require the LEF (Library Exchange Format) file for the Inverter cell.
   - Extract it from the current Inverter cell to provide essential information for the place-and-route (PNR) process.

4. **Understanding Tracks:**
   - Open the `tracks.info` file to learn more about the horizontal and vertical tracks available on each metal layer.
   - This file specifies pitch, spacing, and other relevant details necessary for efficient routing.




# Day 4 Labs

 Commands to open the custom inverter layout
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/d84fc4fa-1e3c-4e42-8e1a-c55f8484730f)

    # Change directory to vsdstdcelldesign
    cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign

    # Command to open custom inverter layout in magic
    magic -T sky130A.tech sky130_inv.mag &

 Commands for tkcon window to set grid as tracks of locali layer

    # Get syntax for grid command
    help grid

    # Set grid values accordingly
    grid 0.46um 0.34um 0.23um 0.17um

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/b179114d-78e3-4262-82a9-5401d638b274)
 

Condition 1 Verified 

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/8664d63c-c5e6-4bdd-ad40-18ca5212cf2a)


Condition 2 verified

Horizontal Pitch 

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/b2bdf188-7051-491d-85f4-b5db4a1ac66c)

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/c80d9f83-1670-4832-90b7-f4a228e6f717)

Condition 3 verified

Vertical Pitch

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/e53b2ba1-bd70-43f1-82c8-7d7bab7bd130)


 **Save the finalized layout with custom name and open it.**

    # Command to save as
    save sky130_vsdinv.mag

Saved Layout 

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/f1bd0ad3-adcd-45f9-898e-b887531e0d47)


Generate lef from the layout.

Command for tkcon window to write lef

    # lef command
    lef write

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/9a19eb26-fdbb-43bb-b7ce-199410084d31)


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/4c7a07ed-f74b-46fe-8e25-60d3a1b70f08)

Edit 'config.tcl' to change lib file and add the new extra lef into the openlane flow.

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/b29da277-c636-43c1-9e09-c74be8bddbe1)


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/a6b4c67d-68b5-45b7-918f-6d2e8dba1b10)

     set ::env(LIB_SYNTH) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"

     set ::env(LIB_FASTEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib"
     set ::env(LIB_SLOWEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib" 

     set ::env(LIB_TYPICAL) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"

     set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]

**Run openlane flow synthesis with newly inserted custom inverter cell.**

run_synthesis 


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/ab528845-f395-403e-b9fa-8e8dfefd275f)

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/563b32d8-8f8f-4a1d-8d0b-b905430e963a)

Commands to view and change parameters to improve timing and run synthesis
```
# Now once again we have to prep design so as to update variables
prep -design picorv32a -tag 24-03_10-03 -overwrite

# Addiitional commands to include newly added lef to openlane flow merged.lef
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Command to display current value of variable SYNTH_STRATEGY
echo $::env(SYNTH_STRATEGY)

# Command to set new value for SYNTH_STRATEGY
set ::env(SYNTH_STRATEGY) "DELAY 3"

# Command to display current value of variable SYNTH_BUFFERING to check whether it's enabled
echo $::env(SYNTH_BUFFERING)

# Command to display current value of variable SYNTH_SIZING
echo $::env(SYNTH_SIZING)

# Command to set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

# Command to display current value of variable SYNTH_DRIVING_CELL to check whether it's the proper cell or not
echo $::env(SYNTH_DRIVING_CELL)

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis

```

After running above commands 

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/39023a0c-44ae-42f3-813d-52756bfb7ccb)


Now run Floor plan

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/ce82bab8-b074-40c1-893e-a94cc78288d2)

```
# Now we can run floorplan
run_floorplan
```

but it failed 

So, we use 

```
init_floorplan
place_io
tap_decap_or
```

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/6d6a5b21-2b06-4b7a-b513-e813d8e7e715)


```

# Now we are ready to run placement
run_placement

```

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/fd4dc6a2-f937-4fbd-8d52-67b4964a9a27)


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/b7c8cdb1-5b2a-4216-b99e-119553f2bf75)


```
# Command to view internal connectivity layers
expand
```

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/2c8de73a-0088-4ec1-b5f5-8afd2bbbcbdd)


Do Post-Synthesis timing analysis with OpenSTA tool.

Newly created pre_sta.conf for STA analysis in openlane directory

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/0bc39a88-65cd-4d83-abf5-4d60415658c9)

my_base.sdc



![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/0b5679e3-85f4-409c-b4da-b456e8c83258)

```
%run_synthesis
```

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/e9430c3a-8788-460e-accd-b49025af742e)


To fix this slack we use

```
# Now once again we have to prep design so as to update variables
prep -design picorv32a -tag 24-03_10-03 -overwrite

# Addiitional commands to include newly added lef to openlane flow merged.lef
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Command to display current value of variable SYNTH_STRATEGY
echo $::env(SYNTH_STRATEGY)

# Command to set new value for SYNTH_STRATEGY
set ::env(SYNTH_STRATEGY) "DELAY 3"

# Command to display current value of variable SYNTH_BUFFERING to check whether it's enabled
echo $::env(SYNTH_BUFFERING)

# Command to display current value of variable SYNTH_SIZING
echo $::env(SYNTH_SIZING)

# Command to set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

# Command to display current value of variable SYNTH_DRIVING_CELL to check whether it's the proper cell or not
echo $::env(SYNTH_DRIVING_CELL)

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis
```

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/0fd53d84-a89d-4723-a0a4-72c270b4c6db)

Finally slack is met 



**Now run Placement**

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/b821c4da-f13b-4525-a149-ea6ae8682e4e)




# Day 5 GDS II Final step

## Power Distribution Network (PDN) Generation in OpenLANE

In OpenLANE, the PDN (Power Distribution Network) is crucial for proper power delivery within the chip. Let's walk through the steps to build the PDN:

## 1. PDN Generation

- The PDN ensures that all standard cells and macros receive adequate power.
- It provides a network of power rails (VDD and VSS) across the chip.

## 2. Using `gen_pdn` Procedure

- The `gen_pdn` procedure is responsible for running the PDN generation process.
- It sets up the power grid, defines power rails, and ensures proper connectivity.

## Common Issues

1. **`LIB_SYNTH_COMPLETE`:**
   - This variable must be defined in the `config.tcl` file.
   - It is called by the `gen_pdn` procedure defined in the `or_pdn.tcl` file.

2. **`LEF_MERGED_UNPADDED`:**
   - Ensure that this variable is correctly set in the `config.tcl` file.
   - It provides essential information for PDN generation.

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/47791054-ae49-4fb6-a8e0-cfa71befca92)

##Routing

Command to perform routing
```
# Check value of 'CURRENT_DEF'
echo $::env(CURRENT_DEF)

# Check value of 'ROUTING_STRATEGY'
echo $::env(ROUTING_STRATEGY)

# Command for detailed route using TritonRoute
run_routing
```
![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/22954699-23aa-461c-9dd9-68d04917fc53)

Power Planning :

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/132c579c-3522-4bde-8c1f-cdacf9984466)


Routing :

Default switches set for routing are :

![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/37227eee-70bc-4cb8-9049-1178e9d7f210)


## VLSI Routing: Global Route and Detail Route

In VLSI design, the routing process is divided into two main stages: global route (or fast route) and detail route. Let's explore each stage:

## 1. Global Route (Fast Route)

- **Purpose:**
  - The global route focuses on quickly establishing a high-level routing solution.
  - It divides the chip into rectangular grid cells, forming a 3D routing graph.

- **Key Points:**
  - The global route creates a routing guide, which consists of boxes (representing pins of cells).
  - The output of the global route is a set of routing guides for each net.

## 2. Detail Route

- **Performed by Engine:**
  - Detail route is executed by the engine called tritonRoute.
  - It refines the routing solution obtained from the global route.

- **Using Global Route Output:**
  - Detail route utilizes the output from the global route, including the routing guides.
  - Algorithms are applied to find the best possible connectivity among all the routing points.



![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/7050b078-695e-4800-82df-6517d0a8c290)



![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/bedc2559-2ea8-43cb-9bd0-67d267ee4cd5)


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/512e44d9-66fc-4f62-abe6-3374e787f5a0)


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/1a773bfa-f827-4cfc-bff9-bd10a44900c0)


![image](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/6ebd7dc1-e06d-4c03-9427-2947c15b1a67)



## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://663d078622096c25eed3ceff--lighthearted-pasca-dc5929.netlify.app/)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/anoushkastripathi/)

