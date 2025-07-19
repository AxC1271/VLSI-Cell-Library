# 🔲 CMOS XOR Gate — Full Custom Design

This project implements a **CMOS XOR gate** using a full custom flow:  
From schematic capture in Xcircuit, layout in Magic VLSI, and simulation using ngspice (with parasitic extraction).

---

## 🧠 Logic Behavior

The XOR gate is one of the most complicated logic gates to implement, taking around 10 transistors to implement. 
Its behavior is defined by the following truth table:

| A | B | Output |
|---|---|--------|
| 0 | 0 | 0      |
| 0 | 1 | 1      |
| 1 | 0 | 1      |
| 1 | 1 | 0      |

---

## 🔧 Transistor-Level Schematic

<p align="center">
  <img src="./XOR_Schematic.png" width="800" alt="XOR Schematic"/>
</p>
<p align="center"><em>CMOS schematic captured in Xcircuit.</em></p>

---

## 🧱 Layout in Magic VLSI

<p align="center">
  <img src="./xor_layout.png" width="800" alt="XOR Layout"/>
</p>
<p align="center"><em>Full custom layout using Magic VLSI.</em></p>

---

## 🧪 Transient Simulation with ngspice

### 🔹 Input Waveforms

<p align="center">
  <img src="./XOR_Input.png" width="700" alt="Input waveform"/>
</p>

### 🔹 Output Waveform (with parasitics)

<p align="center">
  <img src="./XOR_Output.png" width="700" alt="Output waveform"/>
</p>

The output node `Z` transitions high only when `A` and `B` are different — matching XOR behavior.  
Parasitic capacitance extracted from layout (via `ext2spice`) was preserved to reflect real-world electrical effects.

---

## 📁 Files in This Project

| File                | Description                             |
|---------------------|-----------------------------------------|
| `XOR_Schematic.png` | Transistor-level schematic (Xcircuit)   |
| `xor_Layout.png`    | Magic VLSI layout                       |
| `XOR_Output.png`    | Simulated output waveform               |
| `xor_gate.spice`    | SPICE netlist with extracted parasitics |
| `README.md`         | This documentation                      |

---


