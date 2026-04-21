---
title: "About"
date: 2026-04-20
draft: false
ShowToc: false
---

## What is the Landy Gauge?

The Landy Gauge is a 52mm standard vehicle instrument gauge.  It is an open-source project built around the Waveshare ESP32-S3 1.85" round LCD module. Originally designed for my Land Rover Defender, it's adaptable to any vehicle.

![Clock](/images/Clock.jpeg)

It packs a surprising number of features into a compact round display:

- **Compass** — digital compass with vehicle heading and bearing
- **Inclinometer** — pitch with customisable Landrover image
- **Tyre Pressures** — BLE TPMS sensor monitoring for up to 4 tyres
- **Exhaust Gas Temperature** — thermocouple-based EGT monitoring
- **Boost Pressure** — MAP sensor-based turbo boost gauge
- **Clock** — RTC-backed clock with NTP sync via WiFi
- **Cooling** — coolant temperature and fan status monitoring
- **Tilt Meter** — vehicle tilt angle display with customisable image

The project supports both the touch and non-touch versions of the Waveshare 1.85 inch display.  The expansion board is I2C connected to provide additional sensor and vehicle signal inputs.  Without the expansion board the display provides clock, TPMS, tilt and incline.  Add the expansion board for coolant temperature, EGT, Boost and some custom wadding and fan control specific to my Landrover.  The expansion board has eight 12V safe inputs and eight outputs capable of switching automotive relays.  Lots of expansion to develop your own custom functions.
The gauge has an SDCard that hosts custom voice messages and the Wavweshare display also supports voice input if your want to go that route.

## Why Open Source?

This project started as a personal build for my own Defender. I've shared it so others can build one, modify it, and hopefully contribute improvements back.

Everything you need is here:
- **Firmware source code** — ESP-IDF based, fully documented.  This was 100% vibe coded using Claude
- **Circuit schematics** — KiCad designs for the gauge and expansion board
- **3D models** — printable cases for the gauge and expansion board
- **Build instructions** — step-by-step assembly guide

## Hardware Overview

The gauge is built around:
- **Waveshare ESP32-S3 1.85" Touch or non touch LCD** — the main display module
- **Supply PCB** — connects 12V vehicle power or the expansion board to the Waveshare display.
- **Expansion Board** (optional) — adds vehicle signal inputs (ignition, lights, fans, coolant)

See the [Hardware](/hardware/) section for full details.

For complete usage instructions, see the [User Manual](/user-manual/).
