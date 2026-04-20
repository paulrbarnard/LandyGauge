---
title: "Hardware"
date: 2026-04-20
draft: false
ShowToc: true
---

## Main Gauge Board

The gauge is built around the **Waveshare ESP32-S3 1.85" Round LCD** module, with a custom PCB providing sensor connections and power management.

### Key Components

| Component | Purpose |
|-----------|---------|
| ESP32-S3 (N16R8) | Main processor with WiFi and BLE |
| PCF85063 | Real-time clock (battery backed) |
| QMI8658 | 6-axis IMU (accelerometer + gyroscope) |
| MAX98357A | I2S audio amplifier (warning beeps) |

### Downloads — Gauge Supply PCB

The power supply and interconnect PCB fits inside the 52mm gauge housing alongside the Waveshare module. KiCad project files and manufacturing outputs:

| File | Description |
|------|-------------|
| [GaugeSupply.kicad_sch](/downloads/pcb-gauge-supply/GaugeSupply.kicad_sch) | Schematic |
| [GaugeSupply.kicad_pcb](/downloads/pcb-gauge-supply/GaugeSupply.kicad_pcb) | PCB layout |
| [GaugeSupply.kicad_pro](/downloads/pcb-gauge-supply/GaugeSupply.kicad_pro) | KiCad project |
| [GaugeSupply.step](/downloads/pcb-gauge-supply/GaugeSupply.step) | 3D STEP model |
| [gerbers.zip](/downloads/pcb-gauge-supply/gerbers.zip) | Gerber files for manufacturing |

## Expansion Board

The optional expansion board connects to the gauge via a 6core cable supporting 4-wire I2C (500mm max, 100kHz) and the 12V vehicle supply.  

![RearView](/images/RearView.jpeg)

The Expansion Board provides the additional IO functions below

| Component | Purpose |
|-----------|---------|
| LIS3MDL | 3-axis magnetometer (compass) |
| MCP9600 | Thermocouple interface (EGT) |
| ADS1115 | 16-bit ADC (boost pressure) |
| MCP23017 | I/O expander (expansion board inputs) |

| Input | Function |
|-------|----------|
| IO0 | Spare
| IO1 | Ignition |
| IO2 | Sidelights |
| IO3 | Fan Low Speed |
| IO4 | Fan High Speed |
| IO5 | Coolant Level Low |
| IO6 | Low Beam (Dipped) |
| IO7 | Full Beam (High) |

| Output | Function |
|--------|----------|
| Out2 | Wadding enable |
| Out3 | Low Fan Enable |
| Out4 | High Fan Enable |

Other outputs are Spare

### Downloads — Expansion Board PCB

| File | Description |
|------|-------------|
| [LandyGauge.kicad_sch](/downloads/pcb-expansion-board/LandyGauge.kicad_sch) | Schematic |
| [LandyGauge.kicad_pcb](/downloads/pcb-expansion-board/LandyGauge.kicad_pcb) | PCB layout |
| [LandyGauge.kicad_pro](/downloads/pcb-expansion-board/LandyGauge.kicad_pro) | KiCad project |
| [LandyGauge.step](/downloads/pcb-expansion-board/LandyGauge.step) | 3D STEP model |
| [Gerbers_PCBWay.zip](/downloads/pcb-expansion-board/Gerbers_PCBWay.zip) | Gerber files (PCBWay) |
| [ExpansionBoard.pdf](/downloads/pcb-expansion-board/ExpansionBoard.pdf) | Schematic PDF |

## Fan Relay Board

The fan relay board provides switched outputs for cooling fan control.

### Downloads — Fan Relay PCB

| File | Description |
|------|-------------|
| [LandyFan.kicad_sch](/downloads/pcb-fan-relay/LandyFan.kicad_sch) | Schematic |
| [LandyFan.kicad_pcb](/downloads/pcb-fan-relay/LandyFan.kicad_pcb) | PCB layout |
| [LandyFan.kicad_pro](/downloads/pcb-fan-relay/LandyFan.kicad_pro) | KiCad project |
| [LandyFan.step](/downloads/pcb-fan-relay/LandyFan.step) | 3D STEP model |
| [gerbers.zip](/downloads/pcb-fan-relay/gerbers.zip) | Gerber files for manufacturing |

## Wiring

| File | Description |
|------|-------------|
| [Gauge Wiring.pdf](/downloads/wiring/Gauge%20Wiring.pdf) | Wiring schematic PDF |
| [GaugeWire.kicad_sch](/downloads/wiring/GaugeWire.kicad_sch) | Wiring schematic (KiCad) |
| [GaugeWire.kicad_pro](/downloads/wiring/GaugeWire.kicad_pro) | KiCad project |

## 3D Printed Cases

The gauge housing is a 52mm case designed to hold the Waveshare module and gauge supply PCB.  Two alternative bezels are provided to support Waveshare displays with and without touch support.  I have had good results printing with PET-G on a BambuLabs printer using the default settings and 0.4mm nozzel.  Note that the walls of the gauge are thinner than I would have liked to be able to fit the standard 52mm gauge opening in a dash.  The button Plug is to blank the connector for the buttons.  The buttons are optional on the touch version.  That part needs some flexibilty so I have printed it in TPU for AMS.  If you anticipate dismantling the gauge then printing the bezel in TPU lets you put it on and off multiple times.  Printing the bezel in PET-G makes for a one time assembly, as either the bezel or the body are likely to break on disassembly.

### Downloads — 3D Models

| File | Description |
|------|-------------|
| [52mm Gauge Housing.f3z](/downloads/3d-models/52mm%20Gauge%20Housing.f3z) | Fusion 360 source (full assembly) |
| [Case.obj](/downloads/3d-models/Case.obj) | Main case body (printable) |
| [Cover.obj](/downloads/3d-models/Cover.obj) | Rear cover (printable) |
| [Bezel - Touch.obj](/downloads/3d-models/Bezel%20-%20Touch.obj) | Front bezel for touch version (printable) |
| [Bezel - Non Touch.obj](/downloads/3d-models/Bezel%20-%20Non%20Touch.obj) | Front bezel for non-touch version (printable) |
| [Nut.obj](/downloads/3d-models/Nut.obj) | Mounting nut (printable) |
| [ButtonPlug.obj](/downloads/3d-models/ButtonPlug.obj) | Button plug (printable) |

## Bill of Materials

*Detailed BOM coming soon*
