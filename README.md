# 16-bit Multiply-and-Accumulate (MAC) Circuit

Full custom VLSI design of a **16-bit MAC circuit** built from the transistor level up using **Cadence Virtuoso**. Every component goes through the complete IC design flow: schematic → symbol → layout → DRC → LVS → simulation.

## Tools Used
- **Cadence Virtuoso** — schematic capture, layout, simulation
- **DRC** (Design Rule Check) — layout verification
- **LVS** (Layout vs. Schematic) — netlist equivalence verification
- **Post-layout simulation** — extracted parasitics included

---

## Phase I

### Part A — D Flip-Flop (without reset)
- Full transistor-level schematic & layout
- DRC clean, LVS matched
- Functionality verified across 8 clock cycles
- **Rising delay: 60.93 ps | Falling delay: 85.14 ps** (extracted view)

### Part A — D Flip-Flop (with reset)
- Added active-low reset logic
- DRC clean, LVS matched
- **Rising delay: 56.29 ps | Falling delay: 36.64 ps**

### Part B — 16-bit Ripple Carry Adder
- Full schematic + layout
- DRC clean, LVS matched
- Schematic + post-layout simulation
- Critical path: A₀ → Cout (8 AND, 7 OR, 1 NAND, 1 EXOR, 1 NOR gates)
- **Target operating frequency: 0.83 GHz**

---

## Phase II

### Part A — Booth Encoder
- Implements Booth recoding for efficient partial product generation
- Full schematic, layout, DRC, LVS
- Schematic + post-layout simulation verified

### Part B — 16-bit 3-to-2 Compressor (Wallace Tree)
- Partial product reduction stage
- Full schematic, layout, DRC, LVS
- Schematic + post-layout simulation verified

### Part C — 16-bit 6-to-2 Compressor
- Higher-order partial product reduction
- Full schematic, layout, DRC, LVS
- Schematic + post-layout simulation verified

---

## Design Hierarchy

```
16-bit MAC
├── Phase I
│   ├── D Flip-Flop (no reset)
│   ├── D Flip-Flop (with reset)
│   └── 16-bit Adder
└── Phase II
    ├── Booth Encoder
    ├── 16-bit 3-to-2 Compressor
    └── 16-bit 6-to-2 Compressor
```

## Full Report

See [`report.pdf`](./report.pdf) for complete schematics, layouts, DRC/LVS reports, waveforms, and simulation results.

## Team
- Vejaysuriyaa Senguttuvan
- Atharva Kulkarni
- Smit Arekar
