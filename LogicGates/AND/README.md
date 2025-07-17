# 🔲 CMOS AND Gate — Full Custom Design

This project implements a **CMOS AND gate** using a full custom flow:  
From schematic capture in Xcircuit, layout in Magic VLSI, and simulation using ngspice (with parasitic extraction).

---

## 🧠 Logic Behavior

The AND gate is the inverse of the NAND gate, yielding a '1' when both inputs are high. 
Its behavior is defined by the following truth table:

| A | B | Output |
|---|---|--------|
| 0 | 0 | 0      |
| 0 | 1 | 0      |
| 1 | 0 | 0      |
| 1 | 1 | 1      |

---

## 🔧 Transistor-Level Schematic

<p align="center">
  <img src="./AND_Schematic.png" width="800" alt="OR Schematic"/>
</p>
<p align="center"><em>CMOS schematic captured in Xcircuit, note that this schematic is just the NAND configuration with its output passed into an inverter.</em></p>

---

## 🧱 Layout in Magic VLSI

<p align="center">
  <img src="./and_layout.png" width="800" alt="AND Layout"/>
</p>
<p align="center"><em>Full custom layout using Magic VLSI.</em></p>

---

## 🧪 Transient Simulation with ngspice

### 🔹 Input Waveforms

<p align="center">
  <img src="./AND_Input.png" width="700" alt="Input waveform"/>
</p>

### 🔹 Output Waveform (with parasitics)

<p align="center">
  <img src="./AND_Output.png" width="700" alt="Output waveform"/>
</p>

The output node `Z` transitions high only when both `A` and `B` are both high — matching AND behavior.  
Parasitic capacitance extracted from layout (via `ext2spice`) was preserved to reflect real-world electrical effects.

---

## 📁 Files in This Project

| File                | Description                            |
|---------------------|----------------------------------------|
| `AND_Schematic.png` | Transistor-level schematic (Xcircuit)  |
| `and_Layout.png`    | Magic VLSI layout                      |
| `AND_Output.png`    | Simulated output waveform              |
| `and_gate.spice`    | SPICE netlist with extracted parasitics|
| `README.md`         | This documentation                     |

---

## ✅ Next Steps

- [ ] Implement a 2-input XOR gate
- [ ] Implement a 2-input XNOR gate


