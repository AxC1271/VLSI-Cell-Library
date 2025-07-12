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

### 📐 Schematic / SPICE Netlist

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
