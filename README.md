# -Arduino-Nano-Clone
Custom ATmega328P-based Nano clone — full schematic, footprint assignment, DRC-clean 29-component layout
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:314CB0,100:0d1117&height=180&section=header&text=Arduino%20Nano%20Clone&fontSize=45&fontColor=ffffff&animation=fadeIn&fontAlignY=40&desc=Custom%20PCB%20Design%20%7C%20KiCad%2010.0%20%7C%20ATmega328P&descAlignY=62&descColor=a0aec0"/>

[![KiCad](https://img.shields.io/badge/KiCad-10.0-314CB0?style=for-the-badge&logo=kicad&logoColor=white)](https://www.kicad.org/)
[![MCU](https://img.shields.io/badge/MCU-ATmega328P-00979D?style=for-the-badge&logo=arduino&logoColor=white)]()
[![Status](https://img.shields.io/badge/Status-PCB_Ready-brightgreen?style=for-the-badge)]()
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)]()

</div>

---

## 📌 Overview

A **fully custom Arduino Nano clone** designed from scratch in **KiCad 10.0** — covering the complete PCB design workflow from schematic capture to fabrication-ready Gerber files. This is not a copy-paste design; every component was manually placed, every trace routed, and every footprint assigned to match real-world physical parts.

> Built as part of my PCB design learning journey at NUST-PNEC.

---

## 🖼️ Board Preview

> *(Add your PCB layout screenshot or 3D render here)*

| Schematic | PCB Layout |
|-----------|------------|
| ![Schematic](https://github.com/arhamjaffer/-Arduino-Nano-Clone/blob/main/schematic.PNG) | ![PCB](images/pcb_layout.png) | ![3D](images/3d_render.png) |

---

## ⚙️ Specifications

| Parameter | Value |
|-----------|-------|
| **Microcontroller** | ATmega328P-AU (TQFP-32) |
| **Clock Speed** | 16 MHz (External Crystal) |
| **Operating Voltage** | 5V |
| **Input Voltage** | 7–12V (via VIN) |
| **Digital I/O Pins** | 14 (6 PWM) |
| **Analog Input Pins** | 8 |
| **Flash Memory** | 32 KB |
| **SRAM** | 2 KB |
| **EEPROM** | 1 KB |
| **USB Interface** | CH340G USB-to-Serial |
| **PCB Layers** | 2-Layer |
| **Board Dimensions** | 18mm × 45mm |
| **Total Components** | 29 |
| **EDA Tool** | KiCad 10.0 |

---

## 🗂️ Project Structure

```
Arduino-Nano-Clone/
│
├── 📁 Schematic/
│   └── nano_clone.kicad_sch       # Full schematic file
│
├── 📁 PCB/
│   └── nano_clone.kicad_pcb       # PCB layout file
│
├── 📁 Gerbers/
│   ├── nano_clone-F_Cu.gbr        # Front copper layer
│   ├── nano_clone-B_Cu.gbr        # Back copper layer
│   ├── nano_clone-F_Silkscreen.gbr
│   ├── nano_clone-B_Silkscreen.gbr
│   ├── nano_clone-F_Mask.gbr
│   ├── nano_clone-B_Mask.gbr
│   ├── nano_clone-Edge_Cuts.gbr   # Board outline
│   └── nano_clone.drl             # Drill file
│
├── 📁 BOM/
│   └── BOM.csv                    # Bill of Materials
│
├── 📁 images/
│   ├── schematic.png
│   ├── pcb_layout.png
│   └── 3d_render.png
│
└── README.md
```

---

## 🔩 Bill of Materials (Key Components)

| # | Component | Value / Part | Package | Qty |
|---|-----------|-------------|---------|-----|
| 1 | Microcontroller | ATmega328P-AU | TQFP-32 | 1 |
| 2 | USB-Serial IC | CH340G | SOP-16 | 1 |
| 3 | Crystal Oscillator | 16 MHz | HC-49S | 1 |
| 4 | Voltage Regulator | AMS1117-3.3 | SOT-223 | 1 |
| 5 | Voltage Regulator | AMS1117-5.0 | SOT-223 | 1 |
| 6 | Decoupling Capacitors | 100nF | 0402 | 8 |
| 7 | Bulk Capacitors | 10µF | 0805 | 4 |
| 8 | Crystal Load Caps | 22pF | 0402 | 2 |
| 9 | Reset Resistor | 10kΩ | 0402 | 1 |
| 10 | LED (Power) | Green | 0402 | 1 |
| 11 | LED (TX/RX/L) | Various | 0402 | 3 |
| 12 | LED Resistors | 1kΩ | 0402 | 4 |
| 13 | Reset Button | SPST Tactile | SMD | 1 |
| 14 | Mini USB Connector | Type-B Mini | SMD | 1 |
| 15 | Pin Headers | Male 15-pin | 2.54mm | 2 |

> Full BOM available in [`/BOM/BOM.csv`](BOM/BOM.csv)

---

## 🛠️ Design Workflow

```
1. Schematic Capture (KiCad Schematic Editor)
        ↓
2. Component Footprint Assignment (29 components)
        ↓
3. Netlist Export & PCB Import
        ↓
4. Board Outline Definition (18×45mm)
        ↓
5. Component Placement (DRC-guided)
        ↓
6. Trace Routing (2-layer, manual + auto)
        ↓
7. Design Rule Check (DRC) — 0 errors
        ↓
8. Gerber File Export (Fabrication-ready)
```

---

## 🏭 How to Fabricate

1. Download the [`/Gerbers/`](Gerbers/) folder
2. Zip all `.gbr` and `.drl` files
3. Upload to your preferred PCB fab:
   - [JLCPCB](https://jlcpcb.com) ← recommended, cheapest
   - [PCBWay](https://www.pcbway.com)
   - [OSH Park](https://oshpark.com)
4. Default settings work: **2 layers, 1.6mm thickness, HASL finish**

---

## 🔓 How to Open in KiCad

```bash
# Clone the repository
git clone https://github.com/arhamjaffer/arduino-nano-clone.git

# Open in KiCad 10.0
# File → Open Project → select nano_clone.kicad_pro
```

> ⚠️ Requires **KiCad 10.0** or later. Older versions may not open `.kicad_sch` files correctly.

---

## 📸 Design Highlights

- ✅ Full schematic from scratch — no templates used
- ✅ Manual footprint assignment for all 29 components
- ✅ 2-layer routing with proper ground plane
- ✅ DRC clean — zero errors, zero warnings
- ✅ Fabrication-ready Gerbers included
- ✅ Compact form factor matching original Nano dimensions

---

## 🙋 Author

**Arham Jaffer**
B.E. Electrical Engineering — NUST-PNEC, Karachi 🇵🇰
Co-Founder @ [GenXi Tech Solutions](https://www.genxitechsolutions.com/)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/arham-jaffer-7911a3308)
[![Email](https://img.shields.io/badge/Email-arhamkaimkhani1949%40gmail.com-D14836?style=flat-square&logo=gmail)](mailto:arhamkaimkhani1949@gmail.com)
[![WhatsApp](https://img.shields.io/badge/WhatsApp-Chat-25D366?style=flat-square&logo=whatsapp)](https://wa.me/923078331121)

---

## 📄 License

This project is open-source under the [MIT License](LICENSE). Feel free to use, modify, and build upon it — just give credit!

---

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,100:314CB0&height=100&section=footer"/>
</div>
