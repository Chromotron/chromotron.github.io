---
title: "Reactor Core"
date: 2023-06-02T22:34:32+02:00
draft: false
---



Reactor chamber
---

Most chambers for a fusor are around 10 to 20 centimeters in diameter, sophisticated setups can also work above and below. It should be made of stainless steel or similar material to withstand heat and vacuum, while also blocking the x-rays generated during operation. In particular, aluminium (more permeable to x-rays) and glass (can spontaneously break due to stresses, especially with uneven heating) are bad choices unless additional measures are carefully taken. Above approximately 40 kV of operating voltage, the x-ray emissions vastly increase and reach energies that can penetrate steel at high rates. Thus any reactor invoking such voltages must be equipped with additional protection measures, usually distance and lead.

My chamber was acquired used from eBay together with [several other interesting parts](). It was supposedly pre-owned by the German army and used to grow bead crystals, which explains the noble metal (likely silver) residues found within. After many hours of cleaning and sandblasting in my air hood, it changed from tarnished dirty gray (some pictures at the end[???]) to a nice matte metal finish. Some residual noble metal is left at one place on the inside, but as removal is tedious is for now left in place as it is unlikely to disrupt the fusion. At worst or best it might get activated by neutrons.

[BILDER]

As the experienced eye can guess, it is a cross with four DN-100 and two DN-40 conflat flanges. The central sphere is a bit below 15 cm in diameter.



HV-feedthrough
---

A quite large negative voltage of about -30,000 Volts needs to be applied to the tungsten grid inside the reactor chamber to achieve fusion. Hence there is a large difference of electric potentials which in air can arc for multiple centimeters or more. Such an arc effectively acts like a short and would not only cut power to the fusion process, but also damage all kinds of components: whatever is along or the end of it can reach thousands of degrees as in arc welding, while the increased current can damage the transformer or other electric parts. While the [ballast] somewhat mitigates the latter risk, it is hardly enough as the only precaution. An automatic shut-down based on measured current will also be added, but neither solves the demand for a proper way to get all that voltage inside the fusor.

After reading multiple sources, the [forums]() on [fusor.net]() in particular, it was decided that making a high voltage feedthrough from scratch is likely too difficult and dangerous, as a fail during operation can cause huge and costly damages. Hence a ceramically insulated one rated for 30,000 V was ordered online at ~300 € and mounted on an adapter that came with the central chamber. A column of transformer oil contained by acrylic and rubber seals was added to other further insulation. It is capped by an acrylic plate mounted by nuts and washers on four threaded bars extending from the flange at the bottom. For stability and safety, a cable gland with strain relief, originally intended for 230 V mains, was affixed with epoxy.

[BILDer]



View port
---

There is no inherent need for a way to watch the inside of the chamber while in operation. Yet a strong desire to watch the tiny star-like center entertaining life fusion directly with ones own eyes is undeniable. Where else can one safely look at an ongoing nuclear reaction close-up? A further justification can be found in the ability to observe the grid while hot and charged, where disparities in shape, field and flow become visible. Hence a observation window is effectively a must.

A major issue lies in the wide variety of radiation emitted able to escape through mere glass:

- Radio waves and infrared light: No notable dangers, the hull of the reactor might however be hot.
- Visible light: No dangerous brightness expected and if present also notable by the observer.
- Ultraviolet light: All three types (UVA, UVB, UVC) are expected to be present at harmful intensities, caused by thermal emission, collisions and the deuterium spectrum. They are all very damaging to various parts of the eye, easily causing irreparable damage. Damage to shortly exposed skin should not be an issue. Penetration depth is low.
- X-rays: Present in concerning amounts, mainly created by electrons impacting the grid or other parts but also from other sources. Much higher penetration depth, making shielding more complex. Active monitoring and dosimeters are advisable.
- Neutrons: not expected at high rates, but above safe levels. Shielding is difficult and would require a very thick (dozens of centimeters) layer of hydrogen-rich transparent material (water is an obvious choice here). Keeping a minimum distance is most likely the easier and more effective choice.

A standard CF DN-40 flange with an embedded borosilicate glass pane was attached to a corresponding opening of the reactor chamber. To shield against x-rays, a 10mm thick disk of lead glass was procured (eBay, ~40 €). It offers a lead equivalent of 2.5 mm, which exceeds the absorption of the general reactor hull. Both hull and lead glass where calculated to absorb enough x-rays to bring levels into safe ranges, but a dosimeter was attached nonetheless. To further prevent some x-rays to escape via diffuse reflections, the looking port was surrounded by a 5mm thick and 100mm long steel pipe which was pushed over the flange until one end touched the spherical part of the chamber. A pipe of 70 mm inner diameter fits the 2.75 inch (69.985mm !) outer diameter of CF DN-40 flanges very tightly. One end was however slightly widened with a carbide milling head to make application and removal less daunting.

Two UV filter lenses for cameras (Hama [...], specialized camera shop, ~10 €/ea) with high absorption throughout the entire UV spectrum were bought. After carefully removing their inner threads from the titanium ring around them without scratching the glass, they fit tightly on the 62mm lead glass disk. The titanium ring prevents the glasses from touching. A few small drops of superglue where used to keep them from falling off the lead glass.

In addition, two acrylic disks (10mm thick, 70mm diameter) tightly fitting into the pipe were ordered (eBay, ~8€/ea). They also absorb UVB and UVC to some degree, while simultaneously acting as physical support for the other pieces. Lastly, an annular piece of highly heat resistant (up to 400°C) silicon was cast to precisely cover the screw heads on the view port. Altogether, those parts where arranged in order borosilicate - silicon ring - acrylic disk - UV filter - lead glass - UV filter - acrylic disk into the steel tube.

This entire arrangement should, in theory, filter all harmful radiation except neutrons down to harmless levels. Only careful measurements will show if this is indeed the case.

As a final and ultimate protection, a camera instead of one's own eyes should be used. The above stack will then also protect the camera. A mirror is also an option.



