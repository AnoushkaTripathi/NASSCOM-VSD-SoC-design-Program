



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


#  IC Design components and terminologies

- Core

   A core is an area in the chip where the fundamental logic of the design is placed. It encapsulates all the combinational circuit, soft and hard IPs, and nets.

- Die

   Die is an area of chip that encapsulates the core and IO pads. Die is imprinted multiple times along the silicon area or wafer to increase the throughput.

- IO Pads

   IO pads are the pins that act as the source of communication between core and the outside world. Pad cells surround the rectangular metal patches where external bonds are made. input,output and power pad.

  

<img width="198" alt="ic_components" src="https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/509a7633-a81b-49ef-b798-482f5c6cbd02">


 
- IPs

    Foundary IPs are manually designed or need some human interference (or intelligence) essentially to define and create them like SRAM, ADC, DAC, PLLs.
- PDKs

    PDKs are interface between foundary and design engineers. PDKs contains set of files to model fabrication process for the design tools used to design IC like device models, DRC, LVS, Physical extraction, layers, LEF, standard cell libraries, timing libraries etc. SkyWater 130nm is the PDK used in this workshop specifically sky130_fd_sc_hd and openLANE is built around this PDK.







## Day 1 Labs
Understanding the openlane directory 

1.  Understanding the use of various linux commands

![Screenshot from 2024-05-27 09-04-24](https://github.com/AnoushkaTripathi/NASSCOM-VSD-SoC-design-Program/assets/98522737/03e2af36-5489-43fa-9faf-ee4f3d7fa647)


```bash
  ls --help
```

```bash
 openlane/
├── pdk/
│   ├── sky130A/
│   │   ├── libs.ref/
│   │   │   ├── stdcells/
│   │   │   │   ├── sky130_fd_sc_hd/
│   │   │   │   │   ├── lef/
│   │   │   │   │   ├── lib/
│   │   │   │   │   ├── gds/
│   │   │   │   │   ├── verilog/
│   │   │   ├── io/
│   │   ├── libs.tech/
│   │   │   ├── magic/
│   │   │   ├── openroad/
│   │   │   ├── klayout/
│   │   │   ├── drc/
│   │   │   ├── lvs/
│   │   │   ├── pex/
├── sky130B/
│   ├── libs.ref/
│   │   ├── stdcells/
│   │   ├── io/
│   ├── libs.tech/
│   │   ├── magic/
│   │   ├── openroad/
│   │   ├── klayout/
│   │   ├── drc/
│   │   ├── lvs/
│   │   ├── pex/
```

```bash
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
```


