---
title: "Build Guide"
date: 2026-04-20
draft: false
ShowToc: true
---

## Introduction

This guide walks through building a Landy Gauge from scratch. You'll need basic soldering skills and access to a 3D printer (or a printing service).

## What You'll Need

### Main Gauge
- Waveshare ESP32-S3 1.85" Round Touch or non touch LCD module
- Custom gauge PCB (KiCad files provided)
- Components as per the BOM
- 3D printed case

### Expansion Board (Optional)
- Custom expansion board PCB
- MCP23017 I/O expander
- Components as per the BOM
- 6-wire cable (recommended: 500mm max). This is actually a banbu labs AMS interconnect cable.
- 3D printed case

### Sensors
- **Compass**: LIS3MDL breakout (or on-board)
- **EGT**: K-type thermocouple + MCP9600
- **Boost**: MAP sensor (0.5V–4.5V output) + ADS1115
- **TPMS**: BLE tyre pressure sensors (4x)
- **IMU**: QMI8658 (on-board)

## Assembly Steps

### 1. PCB Assembly

*Detailed assembly instructions coming soon*

### 2. Case Printing

Print the gauge case using the provided STL files. Recommended settings:
- Material: PLA or PETG
- Layer height: 0.2mm
- Infill: 20%

### 3. Firmware Flashing

See the [Firmware](/firmware/) page for build and flash instructions.

### 4. Sensor Installation

[GaugeWire.kicad_sch](/downloads/wiring/GaugeWire.kicad_sch)

## Expansion Board Installation

### Wiring

The expansion board connects to the main gauge via I2C:
- SDA, SCL, VCC (3.3V), GND
- Maximum recommended cable length: 500mm
- I2C speed: 100kHz (for cable reliability)

### Vehicle Signal Connections

Connect vehicle signals to the expansion board inputs. All inputs are active-high, optically isolated:

| Input | Connect to |
|-------|-----------|
| IO1 | Ignition switched 12V |
| IO2 | Sidelights circuit |
| IO3 | Cooling fan low speed relay |
| IO4 | Cooling fan high speed relay |
| IO5 | Coolant level warning |
| IO6 | Dipped beam circuit |
| IO7 | Full beam circuit |
