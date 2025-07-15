# 🔲 CMOS NAND Gate — Full Custom Design

This project implements a **CMOS NAND gate** using a full custom flow:  
From schematic capture in Xcircuit, layout in Magic VLSI, and simulation using ngspice (with parasitic extraction).

---

## 🧠 Logic Behavior

The NAND gate is a universal logic gate — all digital systems can be built using only NANDs. Its behavior is defined by the following truth table:

| A | B | Output |
|---|---|--------|
| 0 | 0 | 1      |
| 0 | 1 | 1      |
| 1 | 0 | 1      |
| 1 | 1 | 0      |

---

## 🔧 Transistor-Level Schematic

<p align="center">
  <img src="./NAND_Schematic.png" width="400" alt="NAND Schematic"/>
</p>
<p align="center"><em>CMOS schematic captured in Xcircuit</em></p>

---

## 🧱 Layout in Magic VLSI

<p align="center">
  <img src="./NAND_Layout.png" width="400" alt="NAND Layout"/>
</p>
<p align="center"><em>Full custom layout using Magic VLSI</em></p>

---

## 🧪 Transient Simulation with ngspice

### 🔹 Input Waveforms

<p align="center">
  <img src="./NAND_Input.png" width="700" alt="Input waveform"/>
</p>

### 🔹 Output Waveform (with parasitics)

<p align="center">
  <img src="./NAND_Output.png" width="700" alt="Output waveform"/>
</p>

The output node `Z` transitions low only when both `A` and `B` are high — matching NAND behavior.  
Parasitic capacitance extracted from layout (via `ext2spice`) was preserved to reflect real-world electrical effects.

---

## ⚠️ Debugging & Engineering Insight

During testing, I originally used **fast input pulses** in the picosecond range. However, the NAND gate (with extracted layout parasitics) exhibited slower switching behavior in the nanosecond range. This mismatch caused:

- Incomplete transitions
- Residual charge buildup
- Oscillatory or jagged outputs

**Resolution:** Slowed down input waveforms to match realistic propagation delay (~10 ns), resulting in clean and stable output transitions.

---

## 📁 Files in This Project

| File               | Description                             |
|--------------------|-----------------------------------------|
| `NAND_Schematic.png` | Transistor-level schematic (Xcircuit)  |
| `NAND_Layout.png`    | Magic VLSI layout                      |
| `NAND_Output.png`    | Simulated output waveform              |
| `testbench.spice`    | SPICE netlist with extracted parasitics |
| `README.md`          | This documentation                     |

---

## ✅ Next Steps

- [ ] Implement a 2-input NOR gate
- [ ] Simulate XOR using 4 NAND gates


