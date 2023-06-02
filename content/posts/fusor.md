---
title: "Fusor"
date: 2023-06-02T20:31:31+02:00
draft: false
---

What's a "fusor"?
===

One of the coolest physics devices within reach of an amateur at home is the Farnsworth-Hirsch fusor, a "star in a bottle". It aims to invoke ungodly forces onto the building blocks of matter to smash them together so hard, they create different elements and useful particles: the modern realization of the alchemists' dream of transmutation. Unlike larger fusion reactors such as a doughnut-shaped massive [tokamak](https://en.wikipedia.org/wiki/Tokamak) or a sleekly twisted [stellerator](https://en.wikipedia.org/wiki/Stellarator), they are usually spherical, quite small, don't cost billions of dollars, and do not aim to solve the energy crisis. Instead they strife towards very tight controlled fusion for research and potentially medical purposes.

To reach the enormous speeds and forces nuclear fusion requires, very extreme conditions are needed. Outside laboratories, fusion typically happens at the center of stars like the sun, or when they die or their dead remnants collide, and at similarly extreme conditions such as the beginning of time. Temperature, pressure and collision forces in those events are beyond the imagination of most humans, many _many_ times hotter, denser and stronger than anything most have ever witnessed. For example, the [solar core](https://en.wikipedia.org/wiki/Solar_core) has a temperature of around 15,000,000 °C (that's 27,000,000 °Freedom units) at almost seven times the density of osmium (the densest material in Earth), and all that with a pressure of over 250 billion atmospheres. Yet solar fusion is so slow as to only create the same power output as a few light bulbs per cubic meter. The massive energy production of the sun then only results due to its enormous size.

There are multiple attempts to recreate nuclear fusion on Earth, most often as an almost unlimited power source. Using [deuterium](https://en.wikipedia.org/wiki/Deuterium), [tritium](https://en.wikipedia.org/wiki/Tritium) or [helium-3](https://en.wikipedia.org/wiki/Helium-3) instead of the ordinary hydrogen of the sun is a must, as only those increase the output per volume to a reasonable range. To achieve sustainable efficient fusion reactors is an enormous engineering task humanity has yet to conquer. Consequently, the only feasible way to fuse atoms at home is in very small amounts. There is absolutely no way to achieve the energies of stars or even the smallest professional research lab oneself. For comparison, the fusion of four quadrillion deuterium atoms is about the same energy as burning a match, while a good fusor would have barely reached this number if it ran since the extinction of the dinosaurs.

The low output does not mean that the task of building a fusor is trivial. Not at all, it involves very high voltages to accelerate ionized atoms to the required speeds. But that is for nothing if they just hit some air almost immediately. Hence a high vacuum, free of pesky other things, is necessary. Also only certain rare materials actually work and need be acquired somehow, for example by [electrolysis](https://en.wikipedia.org/wiki/Electrolysis) of [heavy water](https://en.wikipedia.org/wiki/Heavy_water). Dangers for the public or neighbours are effectively non-existent, but for the researcher directly besides the running thing they are all but negligible. High voltage in particular can kill before one even notices; yet any produced radiation is so weak to be irrelevant more than a few meters away, even without shielding.

Project Prometheus
===

I've always wanted to build my own serious Fusor since I learnt about the concept many years ago, but never got around to it.

I started seriously working on a Fusor at the end of January 2023. Previously I only owned two bad vacuum pumps: a cheap single stage one from China (gets down to ~500 µbar, i.e. 2000th of atmospheric pressure) and a very worn-down Vacuubrand RD4 (~5 mbar at best, 10 times worse then the other). Despite doing fine for their intended purpose of de-gassing and drying, neither could get close to the kind of vacuum a fusor requires. The final impulse to just build my very own little sun was finding a very decently priced second RD4 in excellent condition, even recently refurbished: first test run after basic cleaning got down to 1.3µbar, hundreds of times better than the others and within the range of fusors.

Dubbed Prometheus after the ancient Greek bringer of fire and knowledge, I set out to acquire the vast knowledge & experience as well as the equipment to make my own little sun a reality. And whhile I expected a lot of work, it was even more; but not worse, as it was and is a fun endeavour.

For those interested, here's a quick list of the absurdities I had to acquire and figure out how to use properly. Links for further explanations of what kind of absurd doom machines some of those are and what I got myself into will be added as they become available:

Vacuum
---

- **Second stage vacuum pump** such as a [turbomolecular] or [diffusion] pump to create even purer vacuum, and faster.
- A serious vacuum chamber doubling as the **reactor core** able to withstand heat and radiation, while also being really tight.
- **Piping**, including **valves** and **gauges** needed to adequately control the flow.

Electricity
---

- Adjustable **high voltage supply** able to output at least 30,000 Volts at several milliamps.
- **Wiring** to keep the voltage contained and limited, including **ballasts** to deal with energy spikes.

Fuel
---

- Reliable source for small but reasonably pure amounts of **deuterium gas**.
- **Gas injector** that, when combined with the vacuum valves, keeps the amount of deuterium at desired levels.

Detectors
---

- **Neutron detector** to verify if fusion is actually happening.
- **Geiger counter** to check for radiation, just in case.

General
---

- The surprisingly vast and deep **knowledge** how all of the above actually works and how to interconnect them into **the actual fusor**.
- Ideally some (semi-)**automatic control** of the system.
- And last but definitely not least, **safety precautions**, especially for the dangerous levels of electricity, potential radiation and all kinds of mechanical hazards.