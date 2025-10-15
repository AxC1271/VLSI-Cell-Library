# 🔲 Sequential Logic — CMOS VLSI (Full Custom)

Building on the previous Combinational Logic project, this repository contains full-custom layouts and simulations of fundamental memory circuits: D Flip-Flop and SR Latch.

Each circuit has its own folder with:
- Custom layout in Magic VLSI
- Schematic in Xcircuit
- LVS checks with Netgen
- SPICE simulation using ngspice
- Parasitic-aware analysis

---

## 🛠 Tools Used

| Tool        | Purpose                                 |
|-------------|-----------------------------------------|
| Magic VLSI  | Physical layout and netlist extraction  |
| ngspice     | Transient simulation of SPICE netlists  |
| Xcircuit    | Schematic capture and SPICE export      |
| netgen      | LVS comparison between layout and schematic |

---

## 🧠 Theory: Static CMOS Logic

Memory circuits like flip-flops and latches are essential for storing state information in digital systems. They are built using combinations of logic gates and feedback loops.

Key characteristics include:
- Ability to store binary information
- Controlled by clock signals (for flip-flops)
- Static power dissipation similar to logic gates
- Robust against noise and variations

---

## 💡 Example: D Flip-Flop

### Layout (Magic VLSI)

<p align="center">
  <img src="./D-FF/DFFMagicLayout.png" width="600" />
</p>
<p align="center"><em>Magic VLSI layout (with DRC clean)</em></p>

Notice that the flip flop is composed of eight NAND gate cells that we have derived in a previous
module. Four NAND gate cells in total make a D-latch, and there is a master-slave configuration
of D-latches to create this D flip-flop.

---

## 🧪 Simulation: Spice Models

Simulation uses BSIM3 Level-49 models from the SCMOS `ami05` 0.5µm process.

```spice
.model nfet NMOS (LEVEL=49 VTH0=0.71 U0=533 ...)
.model pfet PMOS (LEVEL=49 VTH0=-0.92 U0=202 ...)
```
---

## ✅ Takeaways
- Learned how to design and simulate memory circuits
- Understand the importance of feedback in storing state

---

## 🚀 Next Steps
- Explore more complex memory elements like JK and T flip-flops
- Integrate memory circuits into larger systems like shift registers and counters
- Analyze timing characteristics and optimize for speed and power

---

## 🙌 Closing Notes
This repo is for students, researchers, and hobbyists learning VLSI using open tools. Feel free to fork, open issues, or contribute new memory circuit implementations!

