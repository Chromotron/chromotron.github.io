---
title: "High Voltage Feedthrough"
date: 2023-06-02T22:35:27+02:00
draft: false
---


A quite large negative voltage of about -30,000 Volts needs to be applied to the tungsten grid inside the reactor chamber to achieve fusion. Hence there is a large difference of electric potentials which in air can arc for multiple centimeters or more if humid. Such an arc effectively acts like a short circuit and would not only cut power to the fusion process, but also endangers people and causes damage all kinds of components: whatever is along or at an end of it can reach thousands of degrees (also known as arc welding), while the increased current can damage the transformer or other electric parts. The [ballast] somewhat mitigates the latter risk, yet it is hardly enough as the only precaution. An [automatic control] based on measured current is also in place, but neither solves the demand for a proper way to get all that voltage inside the fusor. In essence a very high voltage somehow has to pass through a stainless steel hull without ever connecting to it in any way.

After reading multiple sources, the [forums on fusor.net]() in particular, I decided that making my own high voltage feedthrough from scratch is likely too problematic. After all, its fail during operation can cause huge and costly damages by destroying almost every single component of the fusor in one way or another, from [delicate electronics]() and the expensive [turbomolecular pump]() to even the [steel hull]() itself. Hence a ceramically insulated professional vacuum feedthrough rated for 30,000 V was ordered online (new, ~300 €, rarely sold to private persons) and mounted on an adapter that came with the [central chamber].

I added a column of [transformer oil] contained by acrylic and rubber seals for further insulation. As an added benefit this makes it impossible for someone to accidentally or purposefully touch the contacts. It likely also increases the voltage the feed-through can handle (larger ones are very annoying to come by) because the limiting factor is usually the atmospheric side. The entire construct is capped by an acrylic plate mounted by nuts and washers on four threaded bars extending from the flange at the bottom where they replace the standard mounting screws. For stability a cable gland with strain relief was affixed with UV resin.

Over time it turned out that tightly fastened flange screws are still quite permissible for oil to seep through. In consequence a few centimeters of silicone rubber (originally bought to make molds for metal casting) was put to the bottom of the acrylic pipe to keep the oil inside. I preferred this to more permanent methods such as epoxy in case the issue persists or another arises. The feedthrough was quite difficult to get after all.


[BILDER]