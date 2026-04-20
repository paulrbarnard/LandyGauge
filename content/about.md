---
title: "About"
date: 2026-04-20
draft: false
ShowToc: false
---

## What is the Landy Gauge?

The Landy Gauge is an open-source vehicle instrument gauge built around the Waveshare ESP32-S3 1.85" round LCD module. Originally designed for Land Rover Defenders, it's adaptable to any vehicle.

It packs a surprising number of features into a compact round display:

- **Compass** — digital compass with vehicle heading and bearing
- **Inclinometer** — pitch and roll with artificial horizon display
- **Tyre Pressures** — BLE TPMS sensor monitoring for up to 4 tyres
- **Exhaust Gas Temperature** — thermocouple-based EGT monitoring
- **Boost Pressure** — MAP sensor-based turbo boost gauge
- **Clock** — RTC-backed clock with NTP sync via WiFi
- **Cooling** — coolant temperature and fan status monitoring
- **Tilt Meter** — vehicle tilt angle display

## Why Open Source?

This project started as a personal build for my own Defender. I've shared it so others can build one, modify it, and hopefully contribute improvements back.

Everything you need is here:
- **Firmware source code** — ESP-IDF based, fully documented
- **Circuit schematics** — KiCad designs for the gauge and expansion board
- **3D models** — printable cases for the gauge and expansion board
- **Build instructions** — step-by-step assembly guide

## Hardware Overview

The gauge is built around:
- **Waveshare ESP32-S3 1.85" Touch LCD** — the main display module
- **Custom PCB** — connects sensors, RTC, IMU, and I/O
- **Expansion Board** (optional) — adds vehicle signal inputs (ignition, lights, fans, coolant)

See the [Hardware](/hardware/) section for full details.

For complete usage instructions, see the [User Manual](/user-manual/).
