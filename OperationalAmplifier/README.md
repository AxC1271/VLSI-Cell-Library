# 🔲Memory Circuits — CMOS VLSI (Full Custom)

Moving to an analog approach, this repository contains full-custom layouts and simulations of a CMOS operational amplifier. The project folder includes: 
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

## 🧠 Theory: Analog Design



---

## 💡 Current Mirror

### Transistor-Level Schematic

<p align="center">
  <img src="./CurrentMirror/CurrentMirrorSchematic.png" width="600" />
</p>
<p align="center"><em>Basic Configuration of Current Mirror</em></p>

### Layout (Magic VLSI)

<p align="center">
  <img src="./CurrentMirror/currentmirror_layout.png" width="600" />
</p>
<p align="center"><em>Magic VLSI layout (with DRC clean)</em></p>

---

## 🧪 Simulation: Spice Models

Simulation uses BSIM3 Level-49 models from the SCMOS `ami05` 0.5µm process.

```spice
.model nfet NMOS (LEVEL=49 VTH0=0.71 U0=533 ...)
.model pfet PMOS (LEVEL=49 VTH0=-0.92 U0=202 ...)
```
---

## ✅ Takeaways
- Learned how to design and simulate a CMOS operational amplifier
- Understand the importance of gain stages and feedback in amplifiers

---

## 🚀 Next Steps
- Explore more complex op-amp configurations like fully differential and low-power designs
- Integrate op-amps into larger analog systems like filters and ADCs
- Optimize for performance metrics such as gain, bandwidth, and power consumption

---

## 🙌 Closing Notes
This repo is for students, researchers, and hobbyists learning VLSI using open tools. Feel free to fork, open issues, or contribute new amplifier designs!


