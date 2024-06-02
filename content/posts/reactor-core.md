---
title: "Reactor Core"
date: 2023-06-02T22:34:32+02:00
draft: false
---


Most functional fusor chambers seem to be around 10 to 20 centimeters in diameter while sophisticated setups can work above and below. They should be made of stainless steel or similar material to withstand heat and vacuum, while also blocking x-rays generated during operation. In particular, aluminium (more permeable to x-rays) and glass (again x-rays; can spontaneously break due to stresses, especially with uneven heating from electron beams;  UV) are bad choices. In theory those problems can be mitigated if additional measures are carefully taken, but those materials are questionable for a proper fusor; they might be sufficient for a [demo fusor], though. Above approximately 40 kV of operating voltage, the x-ray emissions vastly increase and reach energies that can penetrate a few mm of stainless steel as in typical vacuum components. Thus any reactor invoking such voltages must be equipped with additional radiation shielding, usually distance, lead and dosimeters.



Chamber
---

For most goals a basic 3- or 4-way vacuum component with appropriate inner diameters should work. More dedicated chambers obviously are a viable option, too, just more costly. Prises vary widely as explained on the [vacuum components]() page, but used condition is luckily enough to get a proper fusor going.

My chamber was acquired used from eBay together with [several other interesting parts](). It was supposedly pre-owned by the German army and used to grow bead crystals. This explains the noble metal (likely silver) residues found within. Judging from the other parts and skimming over the underlying patents I think they melted small amounts of noble metals with an electron beam.

After many hours of cleaning (scrubbing with soapy tap water, flushing by demineralized water, wiping with isopropanol) and [sandblasting in my air hood](), it changed from tarnished dirty gray to a nice matte metal finish. Some metallic residue (silver?) is left at one location on the inside, removal would be tedious at no obvious gain as it is unlikely to disrupt operation. At worst (or best?) silver might get activated by neutrons.

[BILDER]


Connections
---

As the experienced eye can guess, it is a cross with four DN-100 and two DN-40 conflat flanges (CF-100 and CF-40 for short). The central sphere is a bit below 15 cm in diameter and adds a nice bit of extra room beyond a straight cross. Two of the large flanges (bottom, left) are currently not needed and were closed off. The backwards CF-40 connection goes to the [vacuum pumps](), the other got a [view port]() attached to it and became the front. The right is a custom flange from eBay, it has a KF-16 connector and extends into a small spherical outlet on a pipe on the inside. That's where [deuterium]() is slowly fed in. The top supports the [high voltage feedthrough]() which is actually CF-40 and thus requires an adapter. The reason why I didn't connect it directly to the cross is simple: it would mean that the high voltage rod runs in the middle of only a ~40 mm pipe, so rather close to the walls. Furthermore I need three CF-40 connections anyway, and having them sideways instead of top and bottom seemed to be the better choice.