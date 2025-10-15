# 🧠 VLSI Portfolio — Custom CMOS Design with Open-Source Tools

Welcome! This repository showcases my hands-on exploration of full-custom CMOS VLSI design using open-source tools like Magic VLSI, Xschem, ngspice, and netgen.

After completing a digital systems design course at Case Western Reserve University, I became fascinated by the chip design process—but quickly realized how scarce beginner-friendly resources were. This repo is both my **portfolio** and a **resource** for other students or engineers exploring VLSI.

My goal is to keep each subproject well-documented and approachable, balancing technical depth with clarity—for everyone from ECSE students to recruiters.

---

## 🛠️ Toolchain Overview

| Tool       | Purpose                                                                 |
|------------|-------------------------------------------------------------------------|
| **Xschem** | Schematic capture and SPICE netlist generation                          |
| **Magic**  | Full-custom layout (diffusion, poly, metal) + layout extraction         |
| **Netgen** | Layout vs. Schematic (LVS) validation                                   |
| **ngspice**| SPICE simulations (transient, DC, delay, switching behavior)            |

- All tools installed via `apt-get` on Ubuntu
- Technology: **2002a node** from OpenCircuitDesign (will migrate to **sky130A**)

---

## 📁 Projects

### 🔹 [1. CMOS Inverter](./CMOSInverter)
> The "Hello World" of VLSI

- Designed and simulated a CMOS inverter.
- Validated DRC and LVS using Magic + Netgen.
- Simulated transient behavior with ngspice.

### 🔹 [2. Combinational Logic Cells](./Logic Gates)
> Full-custom layout and SPICE simulation of basic gates

- Gates: NAND, NOR, AND, OR.
- Designed schematics in Xschem, laid out in Magic.
- Performed LVS and transient simulations.
- Measured **propagation delay** for each gate.

### 🔹 [3. Sequential Logic Cells](./MemoryCircuits)
> Sequential elements from the transistor level up

- SR latch and D flip-flop (schematic + layout).
- Create and lay out a single SRAM cell.
- Simulations to identify **setup** and **hold** times.
- Foundation for more complex memory blocks.
  
---

## 📌 Goals

- Explore digital layouts and schematics.
- Migrate from the 2002a node to the **Sky130A** PDK to potentially have chips manufactured.
- Build a reusable standard cell library and small datapath.
- Create a beginner-friendly write-up series on each block.

---

Feel free to explore each subfolder for detailed READMEs, layout screenshots, and simulation plots!
