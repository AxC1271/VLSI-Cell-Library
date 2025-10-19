# CMOS Inverter

As the "Hello World" of CMOS VLSI design, this project implements an **inverter** using open-source tools. It demonstrates a full-custom flow, from schematic capture and simulation to layout and layout-vs-schematic (LVS) verification.

The goal is to explore basic CMOS behavior and get familiar with digital custom design flows using open tools — similar to those used in industry and academia.

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
      <td>Xschem</td>
      <td>Schematic capture and SPICE export</td>
    </tr>
    <tr>
      <td>netgen</td>
      <td>LVS comparison between layout and schematic</td>
    </tr>
  </table>
</div>

---

### 🧠 CMOS Inverter Theory

A CMOS inverter consists of a **PMOS pull-up** and **NMOS pull-down** transistor connected in series between VDD and GND. The gates are tied together as the input, and the drains are tied together as the output.

<div align="center">
  <table>
    <tr>
      <th>Input</th>
      <th>PMOS</th>
      <th>NMOS</th>
      <th>Output</th>
    </tr>
    <tr>
      <td>0</td>
      <td>ON</td>
      <td>OFF</td>
      <td>1</td>
    </tr>
    <tr>
      <td>1</td>
      <td>OFF</td>
      <td>ON</td>
      <td>0</td>
    </tr>
  </table>
</div>


This complementary behavior ensures low static power and fast switching.

---

### Schematic (Xschem)
<div align="center">
  <img src="./inverter_schematic.png" alt="Inverter Schematic" width="400"/>
</div>

- Drawn using just two transistors, a PMOS and an NMOS with their drains connected.
---

### 🧱 Layout (Magic VLSI)

<div align="center">
  <img src="./inverter_layout.png" alt="Inverter Layout" width="400"/>
</div>

- Drawn using n-diffusion, p-diffusion, poly, and metal layers.
- Extracted netlist used for LVS comparison.
- DRC clean.
  
---

### 📐 SPICE Netlist

- Includes a PMOS and NMOS transistor.
- Uses .model definitions for simulation.
- Simulated using ngspice to observe inverter behavior.

This project uses a hand-written SPICE netlist based on a layout extracted from Magic, with devices sized in lambda units and simulated with realistic BSIM3 transistor models.

```spice
.include ./ami05.txt
.option scale=0.3u
.options post
.probe v(A) v(Z)

Vpower vdd 0 3.3
Vin A 0 pulse(0 3.3 100p 50p 200p 500p)

M1 Z A 0 0 nfet w=10 l=2
M2 Z A vdd vdd pfet w=20 l=2

.tran 1p 1200p
.end
```

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

<div align="center">
  <img src="./waveform.png" alt="CMOS Inverter Waveform" width="600"/>
</div>

The inverter demonstrates standard logic behavior:
- Low input → high output
- High input → low output

The blue waveform is the output while the red waveform is the input pulse, which is acting as expected.
The inverter behaves as expected — producing a clean logic inversion with minimal delay or distortion, even with modestly sized transistors.

---

### Closing Notes

Feel free to reach out or fork this repo if you’re also learning custom chip design using open tools. I hope this helps other students and hobbyists dive into VLSI!

---
