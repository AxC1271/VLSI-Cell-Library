# NAND Gate

The NAND gate is the universal logic gate, as any digital logic circuit can be implemented using just pure NAND gates. Within CMOS design, the NAND gate is also the simplest (along with the NOR gate). The truth table of the NAND gate goes as follows:

<div align="center">
  <table>
    <tr>
      <th>A</th>
      <th>B</th>
      <th>Output</th>
    </tr>
    <tr>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <td>0</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1</td>
      <td>0</td>
    </tr>
  </table>
</div>

---
### ⏚ Transistor Schematic (Xcircuit)

<div align="center">
  <img src="./NAND_Schematic.png" alt="NAND Gate Layout" width="400"/>
</div>
<div align="center">
  NAND Gate Schematic
  </div>
  
---

### 🧱 Layout (Magic VLSI)

<div align="center">
  <img src="./NAND_Layout.png" alt="NAND Gate Layout" width="400"/>
</div>
<div align="center">
  Magic Layout
  </div>
  
--- 

### 🧮 Simulation using ngspice 
<div align="center">
  <img src="./NAND_Input.png" alt="NAND Gate Layout" width="400"/>
</div>
<div align="center">
  Input Waveforms
</div>
<br/>

<div align="center">
  <img src="./NAND_Output.png" alt="NAND Gate Layout" width="400"/>
</div>
<div align="center">
  Output Waveform with Parasitic Capacitance
</div>
<br/>

As seen in the waveform, the output Z goes low when both A and B are high, validating the behavior of a NAND gate.

---

### 🛠️ Troubleshooting Difficulties

---
