---
title: "Dangers and how to avoid them"
date: 2023-07-02T13:31:36+02:00
draft: true
series: "fusor"
---


WOrking with high voltages, vacuum and radiation is quite obviously dangerous. Without awareness of the potential hazards one might not only endanger oneself, but others as well. The following is a list of things to keep in mind and pay attention to. Their severity ranges from small nuisance to instantly lethal. It is intentionally kept simple to be easier to remember and look up.

**Disclaimer: This list does not and cannot cover everything!**

High voltage
---

Dangers:

- Death!
- Cardiac arrest (10 mA can be enough!)
- Severe burns
- Muscle contractions, in particular inability to let go
- Intense sunburn (arcing creates intense UV light!)
- Eye damage (from UV)


Best practices when working with dangerous electricity:

- **Never touch** any active high voltage source
- **Make triply sure that power is off** whe making any(!) changes: turn off/down, switch off, unplug; ideally also trigger/remove the fuse
- **Only use one hand**, keep the other in a pocket or otherwise away from anything that can create a second contact to minimize avoids current through the heart
- Wear **isolation** when possible, even if just a rubber glove
- If applicable, **discharge all capacitors** with a metal wire on a safe plastic stick; twice!
- Also assume that ungrounded conductors act as capacitors and are charged
- Be mindful of all conductive parts
- Do not assume that something isolates unless you have tested it in a safe environment and with x3 safety margin
- Take measures to keep other people, children and pets away from devices, switches, and anything else
- If available have another person watch you with sufficient distance; they can call emergency services when something goes wrong!
- There is nothing "so small" as to not demand all available safetly measures!


How to design with safety in mind:

- Ground everything that can be grounded; ground means a long deep metal rod into the _ground_ or similar!
- Use warning lights or sounds to inform yourself and others of running equipment; they should be wired such that they always automatically turn on when high voltage is on!
- Make parts turning on high voltages **fail open**
- Add isolation, even if just air and distance, wherever possible