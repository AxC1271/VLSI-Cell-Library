# 🏛️ The Cell Museum

A curated collection of custom VLSI standard cells, designed from transistors to layout with complete verification.

**Welcome to the museum!** Each "exhibit" is a fully characterized digital cell—from basic logic gates to sequential elements—designed using open-source EDA tools. This project documents my journey learning IC design from the ground up.

---

## 🎯 Project Goals

Learn the complete IC design flow: **schematic → simulation → layout → verification → characterization**

This isn't just about creating cells—it's about understanding the *why* behind every design decision, from transistor sizing to parasitic extraction.

---

## 📚 Exhibits (Cells)

### Combinational Logic
- [Inverter](./combinational/inverter/) - The fundamental building block
- [NAND Gate](./combinational/nand/) - Universal gate implementation
- [NOR Gate](./combinational/nor/) - Dual of NAND, efficient pull-up network
- [AND Gate](./combinational/and/) - NAND followed by inversion
- [OR Gate](./combinational/or/) - NOR followed by inversion
- [XOR Gate](./combinational/xor/) - Transmission gate implementation for efficiency
- [2:1 Multiplexer](./combinational/mux2/) - Datapath selection element

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

**Design Flow:**
```
Schematic (Xschem) → Simulation (ngspice) → Layout (Magic) → 
DRC → LVS (Netgen) → Parasitic Extraction → Post-layout Simulation
```

---

## 📊 Documentation Standard

Each cell includes comprehensive documentation:

✅ **Transistor-level schematic** - Clear, annotated diagrams  
✅ **Optimized layout** - DRC-clean with area efficiency considerations  
✅ **Pre-layout simulation** - Ideal behavior without parasitics  
✅ **Post-layout simulation** - Real-world performance with extracted R/C  
✅ **DRC verification report** - Zero violations  
✅ **LVS verification report** - Schematic-layout matching confirmed  
✅ **Timing characterization** - Measured delays, setup/hold times, power consumption  

---

## 🎓 What I Learned

Through this project, I gained hands-on experience with:

- **Parasitic effects**: Understanding how layout choices directly impact timing and power
- **Layout optimization**: Balancing area, speed, and power through careful transistor placement and routing
- **Timing characterization**: Experimental measurement of setup/hold times and propagation delays
- **Design trade-offs**: Choosing between different implementations (e.g., transmission gates vs. CMOS logic for XOR)
- **Verification methodology**: The critical importance of DRC/LVS in catching design errors early

**Key insight**: Simulation is only as good as your models. Post-layout extraction revealed significant timing differences that would have caused failures in silicon.

---

## 🔗 Related Projects

- **[RISC-V Processor](https://github.com/AxC1271/RISCV-CPU)** - My 32-bit processor uses these exact building blocks conceptually—now I understand them at the transistor level.
- **[Clock Domain Crossing Library](https://github.com/AxC1271/CDC-Guide)** - Educational resource on CDC synchronizers, validated using these sequential cells.
- **[Tiny Tapeout Submission](link)** - Applying these cells to design real silicon (chip currently in fabrication)

---

## 🎫 Getting Started

**Clone the museum:**
```bash
git clone https://github.com/yourusername/cell-museum.git
cd cell-museum
```

**Prerequisites:**
- Magic VLSI
- Xschem
- ngspice
- Netgen
- Sky130 PDK

**Self-guided tour:**
Each cell folder contains a detailed README with schematics, layouts, simulation results, and design notes. Start with the [Inverter](./combinational/inverter/) and work your way through!

---

## 📸 Contributing

Found an optimization? Have a suggestion? Feel free to open an issue or submit a pull request. This is a learning project, and I welcome feedback from the VLSI community.

---

## 📝 License

This project is open source and available for educational purposes. If you use these designs in your work, attribution is appreciated!

---

**Built with curiosity and caffeine ☕ at Case Western Reserve University**
