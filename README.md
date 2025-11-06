# 🏛️ Cell Museum

**Welcome to the museum!** Each "exhibit" is a fully characterized digital cell: from basic logic gates to sequential elements, designed using open-source EDA tools. This project documents my journey learning IC design from the ground up.

This is a personal collection of custom VLSI standard cells that I made using Xschem (schematic), Magic (layout), ngspice (simulation), and with netgen (complete verification). As a computer
engineering student at Case, I grew interested in CMOS IC design but felt disheartened because industry tools like Cadence Virtuoso are extremely expensive and not easily accessible to most students. Luckily, the tools I used for this project are all open source and can be easily installed using `apt-get` commands on Ubuntu Linux. Check the `download_instructions.txt` file in the repo to see how to download these open source tools!

---

## 📚 Exhibits (Cells)

### Combinational Logic
- [Inverter](./combinational/inverter/) - The Hello World
- [NAND Gate](./combinational/nand/) - The Universal Gate
- [NOR Gate](./combinational/nor/) - Dual of NAND, efficient pull-up network
- [AND Gate](./combinational/and/) - NAND followed by inversion
- [OR Gate](./combinational/or/) - NOR followed by inversion
- [XOR Gate](./combinational/xor/) - Transmission gate implementation for efficiency
- [2:1 Multiplexer](./combinational/mux2/) - Input selector

### Arithmetic
- [Full Adder](./arithmetic/full_adder/) - 1-bit addition with carry propagation

### Sequential Logic
- [D-Latch](./sequential/d_latch/) - Level-sensitive storage element
- [D Flip-Flop](./sequential/d_flipflop/) - Edge-triggered master-slave configuration
- [D Flip-Flop with Enable](./sequential/d_ff_en/) - Conditional loading register

---

## 🛠️ Tools & Technology

| Tool | Purpose |
|------|---------|
| **Xschem** | Schematic capture and SPICE netlist generation |
| **Magic VLSI** | Full-custom layout editor with integrated DRC |
| **ngspice** | Circuit simulation and timing analysis |
| **Netgen** | Layout vs. Schematic (LVS) verification |
| **PDK** | Sky130 (SkyWater 130nm open-source PDK) |

---

## 🎫 Getting Started

**Clone the museum:**
```bash
git clone https://github.com/yourusername/cell-museum.git
cd cell-museum
```

---

**Built with curiosity and caffeine ☕ at Case Western Reserve University**
