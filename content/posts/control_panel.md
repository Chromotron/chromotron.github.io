---
title: "Main Controller"
date: 2023-06-02T22:34:32+02:00
draft: false
---


After multiple considerations I decided to make a proper control system which tracks all measurements. A self-made control panel with dedicated buttons and displays allows the operator, me, to quickly observe and adjust critical values. But at the same time the system can react to changes quicker than a human, the latter thus only acting as a backup. As an additional feature it in principle allows remote control, in which case however one must add additional safeties including an independent fail-safe shut-off in addition to the local emergency shut-down button.

Separation into different subsystems seemed like a logical choice. The control panel should be with the operator at a distance while the rest is by necessity near the fusor.

The three independent major subsystems each have their own entries describing details and development:

- [**High Voltage**](),
- [**Vacuum**](),
- [**Neutron Counting**]().

They have little reason to exchange data directly, yet all have crucial information for the operator. Hence the obvious network topology is that of a star, each of them getting their individual connection to the central control panel.


Control Panel
---


The panel was designed and 3D-printed by me in PETG. The colored text is PLA which was carefully printed in place before creating the panel.

[BILD]


Visible in the picture are:

⦿ Four switches with an RGB LED ring:

- Foreline: activates the roughing pump on and with delay opens the valves between it and the [reactor core](),
- Chamber: controls the [turbomolecular pump](),
- Deuterium: responsible for the production of [deuterium gas from the PEM cell]().
- HV: turns the [high voltage transformer] on.

⦿ The RGB LED shows their current state. Black for off, White for ready, Green for active and all being okay, Yellow/Cyan for turning off/on, and Magenta for unexpected or problematic states that should ideally never happen. Red and Blue are used depending on the button, for excample which of voltage (red) and current (blue) currently limits the high voltage.


⦿ Eight 7-segment displays for the most important numerical data:

- Red & Blue: voltage & current, left shows actual value, right the operator-set upper limit.
- Green: pressure before (left) and after (right) the [turbomolecular pump]() and its [subsequent valves].
- Yellow: percentage by which the [flow valve] is opened as set by the operator.
- White: neutron rate per second.


⦿ Three turnable knobs:

- Red & Blue: set the upper limit for voltage & current shown on the respective right 7-segment displays.
- Green: changes the yellow openness percentage of the flow valve to adjust the pressures shown in green.


⦿ A 480x320 pixel TFT touch screen (meant for [Arduino Uno]()). It has no dedicated main usage, but its versatility allows to do show and control whatever is currently needed or was left out from becoming dedicated controls. This includes debugging output during development and controlling less important or only occasionally relevant values, for example when setting up subsystems such as purging the chamber or deuterium system from air.

⦿ The logo.


Connectivity
---

On the sides of the housing (a green Eurobox) are various connectors:

- GX12 connectors: to [neutron detector]() (5-core) and [vacuum controller]() (7-core). The 6-core was originally for high voltage control and is now obsolete.
- Fibre connector for [high voltage control](). It was changed to fibre to ensure complete galvanic isolation between the high voltage systems and the rest.
- Standard DC power connector and On/Off switch.
- Mini USB connector to upload new code to the control panel.

[BILDer]


Internals
---


[BILD]

In general, everything is kept modular and easy to exchange. After all, this is a system in development and required already many minor and major changes.

At the heart of the control panel is a [Arduino Mega](). A large majority of the pins are in use, many for the display, the rest for the panel and communication. Screws and brass distancers affix it to the main PCB and a basic shield only used for further distancing to the TFT display.

The black main PCB is a prototype board and at times uses both sides to reach the 7-segment displays and the inner pins of the Arduino Mega board. It has connectors to the other various parts as seen in the following picture:

[BILD(er)]


At the outer sides of the box are the various smaller supporting boards:

- knob-bearing green PCB,
- cheap red TTL-to-USB adapter ending in the outside Mini USB connector,
- black [DFRobot UART-to-fibre adapter](),
- [neutron counter]() on green prototype board,
- blue buck converter down to ~5V,
- protection board with TVS diode and filters merging both potential power sources (vacuum controller, external plug) via diodes.

[BILD]

The neutron counter is an [Arduino Nano]() which focuses solely on counting events from the [neutron detector]() via the respective GX12 connector. It forwards this value to the central Arduino Mega regularly. Letting the Mega itself do this task might overwhelm its ability to deal with other interrupts. Unlike the other devices, the neutron counter does not actually receive any data from any other controller, further reducing the workload.