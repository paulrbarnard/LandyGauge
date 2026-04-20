---
title: "Firmware"
date: 2026-04-20
draft: false
ShowToc: true
---

## Overview

The firmware is written in C using the **ESP-IDF v5.5.1** framework with **LVGL v8.2** for the graphics. It runs on the ESP32-S3 with PSRAM.

## Source Code

The full firmware source is available on GitHub:

- [LandyGauge on GitHub](https://github.com/YOUR_USERNAME/LandyGauge)

## Features

### Display Gauges
- **Compass** — digital heading with lubber line, bearing display, magnetometer calibration
- **Inclinometer** — pitch and roll angles from IMU
- **Artificial Horizon** — visual pitch/roll indicator
- **Boost Gauge** — turbo boost pressure from MAP sensor (ADS1115 ADC)
- **EGT** — exhaust gas temperature via K-type thermocouple (MCP9600)
- **Tyre Pressures** — BLE TPMS with 4-sensor pairing and persistent IDs
- **Clock** — RTC-backed with NTP time sync and timezone support (34 zones)
- **Cooling Status** — coolant level and fan speed indicators
- **Tilt Meter** — lateral tilt angle

### System Features
- **Night Mode** — automatic day/night switching via expansion board (headlights) or solar twilight calculation
- **Custom Images** — load personalised vehicle images from SD card
- **WiFi** — WPA2 connection for NTP time sync
- **Audio** — warning beeps via I2S amplifier
- **Touch** — capacitive touch for menu navigation
- **Settings** — persistent calibration and configuration via NVS

## Building the Firmware

### Prerequisites
- [ESP-IDF v5.5.1](https://docs.espressif.com/projects/esp-idf/en/v5.5.1/esp32s3/get-started/)
- USB-C cable to the ESP32-S3 module

### Build & Flash

```bash
# Source the ESP-IDF environment
source ~/esp/v5.5.1/esp-idf/export.sh

# Build
idf.py build

# Flash (adjust port as needed)
idf.py -p /dev/tty.usbmodem21301 flash

# Monitor serial output
idf.py -p /dev/tty.usbmodem21301 monitor
```

## Configuration

The gauge is configured through touch-screen menus. Key settings include:
- WiFi SSID and password
- Timezone selection
- Compass calibration
- Tilt/incline offset calibration
- TPMS sensor pairing
- Temperature units (°C/°F)
- Boost display units (bar/psi)
