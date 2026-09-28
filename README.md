# DSLITE_Remastered

> A modern hardware rework of the Nintendo DS Lite.

**DSLITE_Remastered** is an experimental hardware engineering project aiming to recreate and modernize the Nintendo DS Lite while preserving compatibility with the original console, cartridges, controls and overall form factor.

The goal is not to emulate a Nintendo DS on a modern computer.

The goal is to understand the original hardware, reverse-engineer it where necessary, redesign selected parts of the electronics, and progressively build a **modernized DS Lite around the original architecture**.

---

## Project goals

DSLITE_Remastered explores several areas of console hardware modernization:

- Reverse engineering of the Nintendo DS Lite motherboard
- Recreation of schematics in KiCad
- PCB analysis and eventual PCB redesign
- Replacement of ageing or obsolete components
- USB-C charging
- Modern battery and charging circuitry
- Improved power management
- Modern replacement displays
- Experimental display scaling / image processing
- Replacement shells and mechanical parts
- 3D CAD reconstruction of the console
- Improved repairability
- Hardware documentation
- Community-friendly component libraries

The project will remain modular so individual modifications can potentially be reproduced independently.

---

## Project philosophy

The idea behind DSLITE_Remastered is simple:

**repair, understand, reproduce, improve.**

Rather than replacing the entire console with a Raspberry Pi or an emulator, this project attempts to retain as much of the original Nintendo DS architecture as possible.

Whenever possible, the project will favor:

- original hardware compatibility;
- measurable and documented modifications;
- replaceable components;
- open design files;
- commonly available parts;
- reproducible modifications;
- preservation of the original console's behaviour.

Some parts of the project will necessarily remain experimental.

---

## Planned architecture

The long-term project may include several independent hardware modules.

### Main motherboard

Reverse engineering and recreation of the Nintendo DS Lite motherboard.

Current reference board:

`USG-CPU-10`

Objectives:

- reproduce the original schematic;
- identify component functions;
- document power rails;
- document buses and signals;
- recreate footprints;
- compare component revisions;
- prepare a possible redesigned motherboard.

---

### Power system

Potential improvements:

- USB-C connector;
- USB-C charging;
- modern Li-ion / Li-Po battery support;
- improved battery protection;
- improved charging controller;
- voltage monitoring;
- replaceable battery design.

USB Power Delivery is not currently required for the console but may be investigated for future accessories or docking concepts.

---

### Displays

One of the major experimental areas of the project.

Possible directions include:

- modern IPS LCD replacements;
- custom LCD interface boards;
- OLED experimentation;
- improved brightness;
- improved viewing angles;
- replacement backlight circuitry.

The native Nintendo DS resolution remains:

**256 × 192 pixels per screen**

A future experimental display controller may investigate integer scaling or real-time upscaling to higher-resolution panels.

---

## DS Remastered display concept

A more experimental branch of the project explores the concept of a **"DS Remastered" display pipeline**.

Instead of modifying the game software, a dedicated video-processing circuit could intercept the original display signal and process it before sending it to a modern panel.

Conceptually:

```text
Nintendo DS GPU
      │
      ▼
Original display signal
      │
      ▼
Video capture / interface
      │
      ▼
FPGA / video processor
      │
      ├── Integer scaling
      ├── Filtering
      ├── Pixel reconstruction
      └── Experimental upscaling
      │
      ▼
Modern LCD / OLED panel
```

The first realistic objective would be **clean integer scaling**, not AI-based reconstruction.

More advanced processing may be investigated later.

---

## Mechanical redesign

The mechanical side of the project will be developed primarily using **Fusion 360**.

Possible work includes:

- recreation of the DS Lite shell;
- internal mounting points;
- USB-C modifications;
- display adapters;
- replacement hinge mechanisms;
- battery compartment redesign;
- custom shells;
- prototype PCBs;
- 3D printable replacement parts.

KiCad remains the primary tool for electronic design.

---

## Software used

### Electronics

- KiCad
- SPICE simulation where appropriate
- Datasheets
- Multimeter
- Logic analyser
- Oscilloscope

### Mechanical design

- Autodesk Fusion 360
- Mesh / STEP / STL tools
- 3D printing

### Development / documentation

- Git
- GitHub
- Linux
- Markdown
- Python

---

## Repository structure

The repository will progressively follow a structure similar to:

```text
DSLITE_Remastered/
│
├── README.md
├── LICENSE
│
├── docs/
│   ├── architecture/
│   ├── reverse-engineering/
│   ├── measurements/
│   └── research/
│
├── datasheets/
│
├── schematic/
│   ├── original/
│   └── remastered/
│
├── pcb/
│   ├── original/
│   └── remastered/
│
├── libraries/
│   ├── symbols/
│   ├── footprints/
│   └── 3dmodels/
│
├── mechanical/
│   ├── shell/
│   ├── screen/
│   └── usb-c/
│
├── firmware/
│
├── tools/
│
└── references/
```

This structure may change as the project evolves.

---

## Current project status

**Status: Research / Reverse Engineering**

Current work focuses on:

- collecting DS Lite motherboard documentation;
- analysing the `USG-CPU-10` board revision;
- identifying components;
- collecting datasheets;
- reconstructing schematics;
- creating reusable KiCad symbols and footprints;
- preparing a clean Git repository structure.

No complete replacement motherboard exists yet.

---

## Roadmap

### Phase 1 — Documentation

- [ ] Photograph and document the motherboard
- [ ] Identify major ICs
- [ ] Identify passive components
- [ ] Collect datasheets
- [ ] Document test points
- [ ] Document connectors
- [ ] Map power rails

### Phase 2 — Schematic reconstruction

- [ ] Recreate `USG-CPU-10` schematics
- [ ] Verify connections
- [ ] Create missing KiCad symbols
- [ ] Create missing footprints
- [ ] Compare board revisions

### Phase 3 — PCB reconstruction

- [ ] Recreate PCB outline
- [ ] Position major components
- [ ] Reconstruct routing
- [ ] Validate dimensions
- [ ] Generate 3D PCB model

### Phase 4 — Modernization

- [ ] USB-C charging
- [ ] Modern battery circuitry
- [ ] Modern replacement displays
- [ ] Improved power circuitry
- [ ] Replacement shell design

### Phase 5 — DS Remastered experiments

- [ ] Capture original LCD signals
- [ ] Characterize timing
- [ ] Prototype FPGA display interface
- [ ] Integer-scale DS output
- [ ] Test higher-resolution panels
- [ ] Investigate image enhancement

### Phase 6 — Prototype

- [ ] Manufacture prototype PCBs
- [ ] Assemble board
- [ ] Power validation
- [ ] Boot testing
- [ ] Cartridge testing
- [ ] Touchscreen testing
- [ ] Wireless testing
- [ ] Long-term reliability testing

---

## Reverse engineering notes

All measurements and reverse-engineering information should be documented whenever possible.

Useful information includes:

```text
Component reference
Manufacturer
Part number
Package
Measured value
Connected signals
Voltage
Frequency
Datasheet
Board location
Notes
```

This repository should progressively become both a development repository and a technical reference for DS Lite hardware.

---

## KiCad libraries

One objective of the project is to create a reusable local KiCad library for DS Lite components.

Example:

```text
libraries/
├── symbols/
│   └── DSLITE_Remastered.kicad_sym
│
├── footprints/
│   └── DSLITE_Remastered.pretty/
│
└── 3dmodels/
    ├── STEP/
    └── WRL/
```

Components should preferably include:

- symbol;
- footprint;
- datasheet reference;
- manufacturer part number;
- package;
- pin description;
- 3D model when available.

---

## Contributions

Contributions are welcome.

Useful contributions include:

- board photographs;
- high-resolution scans;
- component identification;
- datasheets;
- PCB measurements;
- schematics;
- KiCad symbols;
- KiCad footprints;
- 3D models;
- electrical measurements;
- compatible replacement components;
- repair documentation.

Please document the source of technical information whenever possible.

---

## Disclaimer

DSLITE_Remastered is an independent, unofficial hardware research project.

Nintendo, Nintendo DS, Nintendo DS Lite and related trademarks are property of Nintendo and their respective owners.

This project is not affiliated with, endorsed by, or sponsored by Nintendo.

The repository is intended for:

- hardware research;
- repair;
- preservation;
- reverse engineering;
- education;
- experimentation.

No proprietary Nintendo software, firmware, ROMs or copyrighted game assets should be distributed through this repository.

---

## License

The final licensing model has not yet been selected.

Because the project may contain hardware designs, documentation and software, separate licenses may eventually be used for each category.

Possible choices include:

- CERN Open Hardware Licence for PCB and hardware designs
- GPL or MIT for software and tools
- Creative Commons for documentation

---

## Project name

**DSLITE_Remastered**

Experimental Nintendo DS Lite hardware modernization and preservation project.

```text
Original hardware.
Modern components.
Same DS.
```
