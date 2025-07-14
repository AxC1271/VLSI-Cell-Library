# VLSI Projects Portfolio

Welcome! This repository showcases my hands-on exploration of CMOS chip design using open-source tools like Magic VLSI, Xschem, ngspice, and netgen. After taking a digital systems design course at Case Western, I became fascinated by VLSI—but quickly realized how scarce beginner-friendly resources were.

This repo is my personal initiative to bridge that gap. It’s both a portfolio of what I’ve built and a resource for fellow students or engineers curious about the chip design process. My goal is to keep each README informative and approachable—without being overly technical—for audiences ranging from ECSE students to prospective employers.


## 🔧 Toolchain Overview

All tools were installed via `apt-get` on Ubuntu. 

### 🖉 Xschem
Used for schematic capture. It helps visualize and construct transistor-level designs.

### 🧱 Magic VLSI Layout
Used to create physical layouts with n-diffusion, p-diffusion, poly, metal layers, etc. It also exports SPICE netlists for simulation.

### 📐 Netgen
Used for Layout vs. Schematic (LVS) checks to ensure that the layout matches the schematic functionally and topologically.

### 📈 ngspice
Performs SPICE-level simulations to verify circuit behavior (timing, voltage levels, etc.) before fabrication.

# Projects So Far
### [1. CMOS Inverter](./CMOSInverter)
- Designed and simulated a CMOS inverter using Magic and ngspice.
- Familiarized myself with these tools for VLSI workflow.

### [2. Logic Gates (Work in Progress)](./LogicGates)
- Draw out the transistor schematic layout of NAND, NOR, AND, OR, XOR, and XOR gates.
- Design the gates mentioned above using Magic VLSI Layout.
- Verify LVS using netgen then simulate using ngspice.
- Analyze the propagation delay of each individual gate.
