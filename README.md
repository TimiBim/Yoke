# Yoke

<img width="1754" height="1296" alt="image" src="https://github.com/user-attachments/assets/9570985a-9298-4ee2-8387-66747c297f4c" />

A sim racing steering wheel / yoke controller built around an STM32G491VE.

## Overview

Yoke is a wheel-side controller for a sim racing rig. It handles button and
encoder input, drives a color touch display, and communicates with the base
over CAN bus. Power and data arrive over a single hot-pluggable connector.

## Features

- **STM32G491VE** (LQFP100, Cortex-M4F @ 170 MHz)
- **FDCAN** link to the wheel base via TCAN332G transceiver
- **ILI9341** 320×240 SPI touch display
- **MCP23017** I²C expander for button matrix
- **Hot-plug safe** — MIC2544 current-limit controller and charge pump so the
  wheel can be connected while the rig is powered
- **Cable break detection** (*drahtbruchsicher*) — the design fails safe if the
  wheel-to-base cable is disconnected or damaged mid-session
- **ESD protection** on all external connections (ESD2CAN24DCKRQ1)
- **USB-C** for firmware flashing and debug
- 4-layer PCB with controlled-impedance CAN and USB routing

## Power Architecture

The base supplies a 5 V intermediate rail. An AP2114H-3.3 LDO generates the
local 3.3 V rail on the wheel, keeping the connector current low and avoiding
drop across the cable.

## License

- Hardware: CERN-OHL-S v2
- Firmware: MIT
