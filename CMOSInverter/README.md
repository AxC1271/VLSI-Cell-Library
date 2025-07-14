# CMOS Inverter

As the "Hello World" of CMOS VLSI design, this project implements a **CMOS inverter** using open-source tools. It demonstrates a full-custom flow, from schematic capture and simulation to layout and layout-vs-schematic (LVS) verification.

The goal is to explore basic CMOS behavior and get familiar with digital custom design flows using open tools — similar to those used in industry and academia.

---

### 🔧 Tools Used
| Tool        | Purpose                        |
|-------------|--------------------------------|
| Magic VLSI  | Physical layout and netlist extraction |
| ngspice     | Transient simulation of SPICE netlist |
| *(Optional)* Xschem | Schematic capture and SPICE export |
| *(Optional)* netgen | LVS comparison between layout and schematic |

> 📝 **Note:** Xschem and netgen are not strictly required for this inverter — the schematic can be described manually in SPICE, and LVS can be skipped for such a small circuit.

---

### 🧠 CMOS Inverter Theory

A CMOS inverter consists of a **PMOS pull-up** and **NMOS pull-down** transistor connected in series between VDD and GND. The gates are tied together as the input, and the drains are tied together as the output.

| Input | PMOS | NMOS | Output |
|-------|------|------|--------|
| 0     | ON   | OFF  | 1      |
| 1     | OFF  | ON   | 0      |

This complementary behavior ensures low static power and fast switching.

---

### 🧱 Layout (Magic VLSI)

<p align="center">
  <img src="./CMOSInverterLayout.png" alt="CMOS Inverter Layout" width="400"/>
</p>

- Drawn using n-diffusion, p-diffusion, poly, and metal layers.
- DRC clean.
- Extracted netlist used for LVS comparison.

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

### 🧪 Spice Models
This simulation uses BSIM3 Level-49 models for a 0.5µm process from the 2002a SCMOS node (ami05.txt). A snippet from the included model file:

```spice
.model nfet NMOS (LEVEL=49 VTH0=0.71 U0=533 ...)
.model pfet PMOS (LEVEL=49 VTH0=-0.92 U0=202 ...)
```
These models include realistic second-order effects: mobility degradation, velocity saturation, DIBL, etc.

---

### 📈 Simulation (ngspice)

<p align="center">
  <img src="./SimulationWaveForm.png" alt="CMOS Inverter Waveform" width="600"/>
</p>

The inverter demonstrates standard logic behavior:
- Low input → high output
- High input → low output

The blue waveform is the pulse input whilst the red waveform is the output, which is acting as expected.
The inverter behaves as expected — producing a clean logic inversion with minimal delay or distortion, even with modestly sized transistors.

---

### ✅ Takeaways

1. Demonstrates a full flow for designing and simulating a CMOS gate

2. Establishes foundation for scaling to larger gates (NAND, NOR, XOR)

3. Introduces critical tools used in open-source VLSI

--- 

### 🚀 Next Steps
Future ideas to build on this project:

1. 🔁 Design a ring oscillator and measure delay

2. 🔨 Create a CMOS NAND and NOR gate layout

3. 🧠 Simulate inverter chains and extract propagation delay

4. 🔎 Run LVS with netgen

5. 📐 Explore parasitic capacitance extraction and performance tuning


### Closing Notes

Feel free to reach out or fork this repo if you’re also learning custom chip design using open tools. I hope this helps other students and hobbyists dive into VLSI!



