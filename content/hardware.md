---
title: "Hardware"
date: 2026-04-20
draft: false
ShowToc: true
---

## Main Gauge Board

The gauge is built around the **Waveshare ESP32-S3 1.85" Round Touch LCD** module, with a custom PCB providing sensor connections and power management.

### Key Components

| Component | Purpose |
|-----------|---------|
| ESP32-S3 (N16R8) | Main processor with WiFi and BLE |
| PCF85063 | Real-time clock (battery backed) |
| QMI8658 | 6-axis IMU (accelerometer + gyroscope) |
| LIS3MDL | 3-axis magnetometer (compass) |
| MCP9600 | Thermocouple interface (EGT) |
| ADS1115 | 16-bit ADC (boost pressure) |
| MCP23017 | I/O expander (expansion board inputs) |
| MAX98357A | I2S audio amplifier (warning beeps) |

### Circuit Schematics

The KiCad schematics and PCB layouts are available for download:

- [Main Gauge Board](#) — *coming soon*
- [Expansion Board](#) — *coming soon*

## Expansion Board

The optional expansion board connects to the gauge via a 4-wire I2C cable and provides vehicle signal inputs through a MCP23017 I/O expander:

| Input | Function |
|-------|----------|
| IO1 | Ignition |
| IO2 | Sidelights |
| IO3 | Fan Low Speed |
| IO4 | Fan High Speed |
| IO5 | Coolant Level Low |
| IO6 | Low Beam (Dipped) |
| IO7 | Full Beam (High) |

## 3D Printed Cases

Printable cases for both the gauge and expansion board are available:

- [Gauge Case](#) — *coming soon*
- [Expansion Board Case](#) — *coming soon*

## Bill of Materials

*Detailed BOM coming soon*
