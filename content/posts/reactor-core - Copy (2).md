---
title: "Reactor Core"
date: 2023-06-02T22:34:32+02:00
draft: false
---



Reactor core
---

Most functional fusor chambers seem to be around 10 to 20 centimeters in diameter while sophisticated setups can work above and below. They should be made of stainless steel or similar material to withstand heat and vacuum, while also blocking x-rays generated during operation. In particular, aluminium (more permeable to x-rays) and glass (again x-rays; can spontaneously break due to stresses, especially with uneven heating from electron beams;  UV) are bad choices. In theory those problems can be mitigated if additional measures are carefully taken, but those materials are questionable for a proper fusor; they might be sufficient for a [demo fusor], though. Above approximately 40 kV of operating voltage, the x-ray emissions vastly increase and reach energies that can penetrate a few mm of stainless steel as in typical vacuum components. Thus any reactor invoking such voltages must be equipped with additional radiation shielding, usually distance, lead and dosimeters.



Chamber & Connections
---

For most goals a basic 3- or 4-way vacuum component with appropriate inner diameters should work. More dedicated chambers also are a viable option. Prises vary widely as explained on the [vacuum components] page, but used condition is luckily enough to get a proper fusor going.

My chamber was acquired used from eBay together with [several other interesting parts](). It was supposedly pre-owned by the German army and used to grow bead crystals. This explains the noble metal (likely silver) residues found within. Judging from the other parts and skimming over the underlying patents I think they melted small amounts of noble metals with an electron beam.

After many hours of cleaning (soapy water, demineralized water, isopropanol) and [sandblasting in my air hood](), it changed from tarnished dirty gray to a nice matte metal finish. Some metallic residue is left at one location on the inside, removal would be tedious at no obvious gain as it is unlikely to disrupt operation. At worst (or best?) silver might get activated by neutrons.

[BILDER]

As the experienced eye can guess, it is a cross with four DN-100 and two DN-40 conflat flanges (CF-100 and CF-40 for short). The central sphere is a bit below 15 cm in diameter and adds a nice bit of extra room beyond a straight cross. Two of the large flanges (bottom, left) are currently not needed and were closed off. The backwards CF-40 connection goes to the [vacuum pump & control system](), the other has a [view port] attached to it and became the front. The right is a custom flange from eBay, it has a KF-16 connector and extends into a small spherical outlet on a pipe on the inside. The top supports the high voltage feedthrough. It is actually CF-40 and thus requires an adapter. The reason why I didn't connect it directly to the cross is simple: it would mean that the high voltage rod runs in the middle of only a ~40 mm pipe, so rather close to the walls. Furthermore I need three CF-40 connections anyway, and having them sideways instead of top and bottom seemed to be the better choice.



HV-feedthrough
---

[own]



View port
---

The desire to look at the tiny star-like center entertaining life fusion is undeniable. Where else can one safely watch an ongoing nuclear reaction right before one's nose; the famous "star in a bottle"? Hence an observation window is effectively a must to quench this urge. A further justification is found in the ability to observe the grid while hot and charged, where disparities in shape, field and flow become visible.

Such a view port however causes a variety of additional design issues. As explained on the [materials]() page, glass is not exactly the best material for a fusion reactor, leaving us with the following dangers:

**Cracking**: High temperature or differentials of them can cause the glass to break. Even a small crack can let unwanted air into the chamber, but by far the largest risk is a full implosion. While likely not dangerous to the operator, the potential damage to the system is enormous:

- glass shards or even just air flow can easily cause irreparable damage and catastrophic failure in the [turbomolecular pump]();
- higher pressure can cause arcing between grid and chamber walls which can destroy the transformer and melt the ends of the arc.

Thus it is advisable to minimize the chances for this. The glass should be borosilicate which deals better with thermal abuse, but at the cost of breaking more easily under physical stress. An additional cylindrical glass pane put directly on the inside of the window can protect from uneven heating or direct damage due to electron beams. While blocking the view a bit, a protective metal grid might also be a good idea. Ultimately I bought a CF DN-40 view port (eBay, ~40€, used, no grid) as well as a protective glass plate (~20 €, cut to desired exact diameter by the seller) fitting inside the tube. The latter is not inserted yet, I plan to use a tiny bit of vacuum-compatible glue to stop it from moving around but am still looking for a better solution.


** Radiation**: A major danger to humans lies in the wide variety of radiation able to escape through mere glass.

- Radio waves and infrared light: The power is too low to create acute dangers, the hull of the reactor might however be too hot to touch.
- Visible light: No dangerous brightness expected and also easily noted by the observer.
- Ultraviolet light: All three types (UVA, UVB, UVC) should be expected at harmful intensities, caused by thermal emission, collisions, plasma glow, and the UV-heavy deuterium spectrum in particular. They are very damaging to various parts of the eye, easily causing irreparable damage. Even sunburn on exposed skin is possible.
- X-rays: Present in concerning amounts, mainly created by electrons impacting the grid. Depending on their energy they have a high penetration depth into steel, making shielding complicated. Their wavelength also makes them able to reflect and refract in almost random angles even on perfectly flat surfaces. Hence one has to account for stray radiation. Active monitoring and dosimeters are highly recommended.
- Neutrons: not expected at insane rates, but above safe levels. Shielding is difficult and would require a very thick (dozens of centimeters) layer of hydrogen-rich transparent material (water, acrylic) combined with an absorber (e.g. boron) with high cross-section. Keeping a minimum distance is likely the simplest and most effective protection.

In short and to repeat, UV and x-rays are the most pressing concerns, while a safety distance is strongly advised, too.

To shield against x-rays, a 10mm thick disk with 62 mm diameter made of lead glass was procured (eBay, ~40 €). It offers a lead equivalent of 2.5 mm, which significantly exceeds the x-ray absorption of the reactor hull. Both hull and lead glass were calculated to absorb enough x-rays to bring levels into safe ranges, but a dosimeter was used nonetheless. I surrounded the flange with a 5mm thick and 100mm long steel pipe which was pushed until one end touched the spherical part of the chamber to catch stray x-rays from diffuse reflections. A pipe of 70 mm inner diameter fits the 2.75 inch (69.985 mm!) outer diameter of CF DN-40 flanges very tightly. One end had however to be widened slightly with a carbide milling head to make affixing and and removal much less daunting.

I also bought two UV filter lenses for cameras (Hama [...], specialized camera shop, ~10 €/ea) with high absorption throughout the entire UV spectrum. They fit surprisingly very well on the ends of the lead glass disk while their titanium rings prevent the glasses from touching and scratching. A few small drops of superglue keep this hamburger-like assembly together. Two 3D-printed half-rings extend the diameter to 70mm on the outside.

In addition, two acrylic disks (10mm thick, 70mm diameter) tightly fitting into the pipe were ordered (eBay, ~8€/ea). They also absorb UVB and UVC to some degree, while simultaneously acting as physical support and protection for the other pieces. Their properties as neutron moderators is however too small to be of relevance. Lastly, an annular piece of highly heat resistant silicon (TrollFactory, ~30€, intended for metal castin at up to 40 °C) was cast to cover the screw heads on the view port and act as a distancer.

Altogether, those parts where stacked in the following order inside the pipe: view port - silicon ring - acrylic disk - UV filter - lead glass - UV filter - acrylic disk. Two small worm screws prevent the outer acrylic plate from moving, which fixes the other parts between it and the silicon.

This entire arrangement should, in theory, filter all harmful radiation except neutrons down to harmless levels. Only careful measurements will show if this is indeed the case, especially because good sensors for UV and x-rays are difficult to come by a budget. I currently use a sunburn index detector and a special paper strip that reacts visibly to UVA and UVC to check for the UV dosage. The x-rays are observed with a Sowjet pancake probe (...) also intended as Geiger counter for alpha radiation. Its thin window makes it more transparent for lower energy x-rays, thus increasing sensitivity. It is powered and measured by a self-assembled Geiger counter kit (...) I bought several years ago.

The ultimate and final protection lies in using a camera. It allows one to see inside from a safe distance. The previous radiation protection measures are still not irrelevant to protecte the camera and not create cone of increased radiation in direction of the view port.
As a final and ultimate protection, a camera instead of one's own eyes should be used. The above stack will then also protect the camera. A mirror is also an option.