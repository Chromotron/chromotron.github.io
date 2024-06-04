---
title: "Vacuum Controller"
date: 2023-06-02T22:34:32+02:00
draft: false
---


Originally this was intended as the only controller and would mount the [control panel]() directly on top. The other systems would be entirely independent and manual, especially the [high voltage control](). When development and setup progressed it became clear that a more complex system serves my intended purposes better. The decision to change for the current design happened before the connectors and container were finalized, therefor this later change did not cause much issue.


Connectors
---

The vacuum controller is built inside a gray Eurobox and features various connections:

- Schuko plug supplying power,
- Schuko receptable towards the [roughing pump](),
- Five GX12 connectors to the [vacuum gauges](), [deuterium producer]() and the [main controller](),
- Five Amphenol-Tuchel connectors for the [vacuum valves]() and the [turbomolecular pump]().


Internals
---

Measured by wiring and number of subsystems, this is probably the most complex of the controllers. It involves rails for GND, +5V, +20V (regulated) and +24V plus three more adjustable voltage outputs for the fan and the [PEM cell assembly](). Only the 24V rail is able to supply large amounts of current, the rest is quite limited. The subcomponents are:

- green main PCB
- [Arduino Nano]() (mounted on PCB)
- three ADCs (ADS1115, mounted on PCB),
- 24VDC, 500W power supply,
- Buck converter down to +5V,
- pair of 230VAC relays,
- DM320T stepper motor controller,
- Varian V70 Controller 'Brick' for the [turbomolecular pump](),
- cooling fan.

Generally all microelectronics run at 5V. The ADCs measure the voltage from the three vacuum gauges (foreline, chamber, deuterium) but require simple 1:1 voltage dividers to bring it below 5V. The corresponding gauges are supplied with L7820CV-regulated 20V for stability and protection. Only the MOSFET-operated electropneumatic vacuum valves and the stepper controller require more current at 24V.

The majority of connections control the typiical functions of each device. This among others includes a zeroing contact for the [flow valve]() as well as basic feedback regarding speed and power usage of the [turbomolecular pump]().