# Logic Gates


Building from the previous project (CMOS Inverter), this project aims to layout the basic logic gates (NAND, NOR, AND, OR, XOR, XNOR), analyze power consumption, and analyze the propagation delay of each gate using open source tools.

---
### 🔧 Tools Used
<div align="center">
  <table>
    <tr>
      <th>Tool</th>
      <th>Purpose</th>
    </tr>
    <tr>
      <td>Magic VLSI</td>
      <td>Physical layout and netlist extraction</td>
    </tr>
    <tr>
      <td>ngspice</td>
      <td>Transient simulation of SPICE netlist</td>
    </tr>
    <tr>
      <td> Xschem</td>
      <td>Schematic capture and SPICE export</td>
    </tr>
    <tr>
      <td>netgen</td>
      <td>LVS comparison between layout and schematic</td>
    </tr>
  </table>
</div>

---

### 🧠 Static CMOS Logic 

In static CMOS logic, any function can be implemented using a PUN (pull-up network) and a PDN (pull-down network). Each network consists of PMOS and NMOS transistors respectively, and they are arranged in a way such that they complement each other. This ensures that the output of any static CMOS circuit is only ever directly connected to VDD or GND but ***NOT both*** at the same time (which also means there never exists a direct path from power to ground). This minimizes power dissipation and gives the circuit high switching speed while maintaining signal integrity.

---

### 🧱 Layout (Magic VLSI)

<div align="center">
  <img src="./NAND_Layout.png" alt="NAND Gate Layout" width="400"/>
</div>
<div align="center">
  NAND Gate Layout
  </div>
---

### 📐 SPICE Netlist

---
### 🧪 Spice Models
This simulation uses BSIM3 Level-49 models for a 0.5µm process from the 2002a SCMOS node (ami05.txt). A snippet from the included model file:

```spice
.model nfet NMOS (LEVEL=49 VTH0=0.71 U0=533 ...)
.model pfet PMOS (LEVEL=49 VTH0=-0.92 U0=202 ...)
```
These models include realistic second-order effects: mobility degradation, velocity saturation, DIBL, etc.

---

### 📈 Simulation (ngspice)

---

### ✅ Takeaways

--- 

### 🚀 Next Steps
Future ideas to build on this project:

---

### Closing Notes

Feel free to reach out or fork this repo if you’re also learning custom chip design using open tools. I hope this helps other students and hobbyists dive into VLSI!



