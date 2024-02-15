---
title: "HV-Transformer"
date: 2023-06-02T22:35:27+02:00
draft: true
---


When accelerating a given charged particle with an electric field, the total speed or energy only depends on the voltage difference between the ends. Hence why the accelerating force is often just stated in (Kilo)Volts. When considering other particles, their mass and charge also matters, but nothing else. In particular, any two identical ions will accelerate the same.


We want to accelerate deuterons (deuterium ions) towards a common center where they can collide. We do so by having a sufficiently high electric field between the reactor wall and a [gasket](). For deuterium fusion, about 30,000 V are often quoted as a good ballpark. Above 40,000 V, a lot more x-rays are produced, thus requiring special shielding, while below 20,000 V the fusion rates are close to none. Furthermore, a relatively high current of 10 mA is recommended for good rates, putting the power demand at 300 Watts or more before any losses are accounted for. As in an [ohmic]() resistor, voltage and current are coupled by the effective resistance of the setup, which therefore has to be balanced accordingly.

The central [gasket]() needs to be negatively charged relative to the chamber walls. For safety and sanity, the walls of the fusor must never be at dangerous voltages and thus have to be grounded along with all other outsides. Hence a negative direct current (DC) at -30,000 V has to be fed to the gasket.

This begs the question of how such electricity can be safely and reliably supplied.


Transformer overview
---

An electric transformer trades voltage for current, by intermittently turning it into magnetic flux. Under ideal conditions they up (or down) the voltage by the same factor as they reduce (or increase) the current. Twice the voltage at half the current, thus leaving theoretical power = voltage·current the same. Losses are almost always relevant and lead to unwanted heating. Apart from a few cases unsuitable for our cause, transformers work based on electromagnetic induction and thus require alternating current (AC). Put simply, two coils called primary and secondary are wound around a magnetically conductive core. When supplied with alternating current, the primary creates a similarly fluctuating magnetic field inside the core, which in turn induces voltage in the secondary coil. Changing electricity causes magnetism, and changing magnetism causes electricity.

In essence, each winding acts like a little voltage source, all of which are put in series. If there are m windings on the primary and n on the secondary, the voltage on the secondary is n/m times as large as that on the primary, while the current gets multiplied by the reverse fraction of m/n so that the total power stays the same, if losses are ignored.

The exact details, efficiency and side effects depend not only on voltages and power, but also the frequency. A faster rate of change in the AC means a more abrupt effect on the magnetic core, which like normal inertia resists sudden movement, yet wants to stay in motion when already so. The chosen material has a large effect on how easily it reacts on changes, which has advantages and disadvantages. In the end, the gist is that low frequency transformers are often layered iron plates, while fast frequency transformer cores are made of ferrite.

It also does not hurt to keep in mind that AC in wires creates radio noise, especially at higher frequencies. This might not only negatively influence our measurements but is simply illegal in some jurisdictions above certain levels. If possible this means that any transformer should be encased in a Faraday cage or similar.

There are two major design options: large cores connected to mains at 50 Hz (or 60 Hz in some places), or more complex switching supplies working with smaller cores at much higher frequencies. Both were tried, each coming with their own issues and design challenges. Switching devices, while easier to make and smaller, are harder to get to sufficient power / current. Sometimes a voltage multiplier is suggested in conjunction, but while they can easily increase the output voltage by a single digit factor, the resulting currents are in my experience way too small to be useful. At theoretical 30,000 V output I didn't even reach 0.1 mA in initial tests because the numbers were too small and unstable. So I went for the other option.




X-ray transformer
---

An old x-ray transformer was found on eBay at the very reasonable price of 110 €. It is on the smaller end and came without any enclosure, manual or labels. X-ray transformers need to be fully immersed in appropriate oil which acts both as isolator and coolant. Running it without oil will almost surely cause internal arcing and instant damage to the isolation and windings, rendering it worthless. Together with a proper oil and cooling containment, those transformers can weigh multiple hundreds of kilograms. Meanwhile and even with oil and additions, mine ended up at significantly less.

[BILD]

A basic x-ray transformer has six connections:

- A, B: two high voltage outputs each at the end of one of two large many-wound secondary coils.
- GND: connected to the other end of one of the aforementioned coils and to the metal parts for grounding;
- "mA": connected to the remaining end of the other large coil; in standard operation it is connected to GND via a amp-meter to track the current going into the x-ray tube;
- c, d: two connectors towards a primary coil inside the larger ones for power supply.

The one at hand however has some strange wiring, as seen on the picture, which was initially quite baffling:

- X, Y: two large ones seemingly leading into one of two large coils each.
- Z, W: an additional larger pair rather close to Y, leading to what seems to be a third, flat arrangement of two coils.
- GND: a yellow-green striped thinner cable which can be visually tracked to connect to the metal parts of the transformer, but also leading inside of it.
- q, r, s, t, u: thinner yellow cables leading inside the transformer.
- v, w: two more brown thinner cables otherwise visually indistinguishable from the yellow ones.

While X and Y are very likely the analogues of the high voltage outputs A and B, and GND easily matches its namesake, the remaining ones were harder to identify. At first measuring resistances by means of a multimeter was attempted. It turned out that GND was indeed connected to the metal parts of the core at no resistance, as well as X by ~79 kOhm. Similarly, Y was connected to q at the same resistance, indicating that it likely is "mA".

A very low resistance <1 Ohm was measured between each of r, s, v and w, with their choice of color being a bit confusing. There is also a medium resistance of ??? Ohm between t and u. All other pairs are disconnected.

While trying to find any datasheets or documentation, I landed on the corresponding section at [Fred's Fusor](), a website with lots of fusor engineering details that I had already visited before. It turned out that they had a very similar transformer, the main difference being a lack of two thinner wires (likely the brown ones, as seen below). They give two supposed internal wirings, the second found with help from [fusor.net]().

Based on all of the above and still not really knowing what is what, I very carefully connected some pairs of wires to mains (230 VAC, 50Hz) via a variac, with the goal of applying only a few Volts at 50 Hz. All standard high voltage precautions (one-hand-rule, not touching any potentially life wires or even any part of the transformer) were in effect as, even at such input voltages, the secondary can reach several thousands of Volts. There is also always the danger of damaging the coils by arcing if testing without immersing the transformer in oil. As a first test result and contradicting the two diagrams from Fred's Fusor, it turns out that t and u are not the primary as they induce effectively no voltage between any of X, Y, GND and q. Instead, they might lead to the second coil of the flat arrangement at the end, where Z and W connect. Applying even low voltage at any pair of r, s, v and w leads to high voltage between X and GND, as well as Y and q. In conclusion, my guess on those last four connections is correct, while the primary windings seems to be divided into three sections at r, s, v and w in some order.

For better access, short thin blank metal wires were soldered to X and Y and longer insulated cables to GND and the lowercase ones. It later turned out that this insulation hardens and brittles when immersed in oil, but this caused no notable issues. Anyone reproducing our attempt should however find ones more resistant to oil. To keep the cables distinguishable, we marked GND with black and r, s, v, w with Red, Yellow, Green and Blue cable binders. At the same time, q was combined with GND while the remaining two were isolated at the ends with shrink tubes.

The colors were assigned such that Red, Yellow, Green and Blue are probably linearly connected in that order. This order was found with a more specific measurement between all pairs of those four resulting in the following resistances:

[BILD]

It therefor stands to reason that the multimeter and its connections add ~0.2 Ohm while the four cables connect in the given order to the primary wirings, with consecutive resistances in the ballparks of:

- R-Y: 0.3 Ohm
- Y-G: 0.1 Ohm
- G-B: 0.8 Ohm

This was further confirmed by a corresponding reciprocal dependence when applying low voltage AC to them and measuring X-Y with a high voltage probe.


In theory, the current between q and GND equals that between X and Y and thus is measured in x-ray devices. But the final setup of rectifying X and Y against GND makes this all but useless, hence the merger. Instead, as described in the [article on measuring](), the current will be tracked between the GND of the transformer and the actual ground where everything else connects to.




Enclosure and oil
---

An old and cheap vacuum chamber (~80€) for drying and degassing made of stainless steel was re-purposed as an enclosure. As such it was possible to put the entire content under vacuum whenever desired.

[Bild]

With some effort, fluxed solder and hydrochloric acid, two brass connectors were soldered to its inside. They act both as mechanical anchors for the upper parts of the build as well as an internal ground connector. Grounding the enclosure is simply a matter of safety. Even if entirely disconnected from the transformer it could otherwise still accumulate quite some charge, acting as a capacitor similar to a Leyden jar with the outside world. The transformer was simply put at the bottom, which adds a second grounding connection between it and the enclosure in addition to the GND wire. All connections except the two brass ones mentioned before were either soldered, screwed together or clamped with screws in some way. This is to ensure that nothing could just come lose and thereby cause dangerous situations.

To ensure proper operation and avoid arcing, the entire transformer has to be immersed in oil According to some sources, almost any kind of dry oil from rape seed and sunflower to synthetic silicon oils should work. I cannot vouch for this, but for simple home applications away from the limits of a transformer it sounds plausible. However, the better an oil suits this specific job, the better the life expectancy.

Initially, I tried pure paraffin oil that was around from my [experiments in creating alkali metals](). A lot of brownish old residues quickly dissolved from within the coils and spread through the oil. To improve this, an oil change seemed unavoidable. As I had already ran out of paraffin oil and prices were similar, a 20 liter barrel of specialized transformer oil (Shell [...]) was ordered online (~130€ + shipping from UK). The transformer was placed in barely enough oil to cover it for the initial test and build phases. It was later again changed to counter oxidation and wetness.

The oil needs to get into every cavity around the coils, having air bubbles can be as detrimental as not having oil at all. The industry standard is to put the transformer into reasonable vacuum and only then add oil, all while not letting air in. This has the added advantage of removing most water from all parts, as it boils instantly at low pressures. AT first I tried to get around this by carefully tilting the half-filled chamber. After some success and before doing some final changes this was abandoned. Instead I added a small inlet at the top by soldering a standard female G 1/8 to 6mm hose connector into a drilled hole of appropriate size, with the thread on the outside. This can be connected to a silicone rubber pipe and a tiny valve to suck oil in directly from the barrel into the vacuum chamber.

As a note, higher vacuum is ultimately pointless and might be counterproductive. One millibar is about the same pressure as a centimeter of water or oil above. Therefor the pressure under several centimeters of oil will never get lower than a corresponding number of millibars. Thus applying vacuum below 0.1 mbar is not really improving much except directly below the surface. Furthermore, additives or even the oil itself may vaporize at high vacuum conditions, degrading the oil, in particular its ability to absorb water, which it does more than one might think.

Interestingly and despite the proper filling method there were still lots of bubbles forming. Some clearly came from within cables and other irrelevant pockets, but there was also a general bubbling from nucleation sites everywhere. It is unknown to me if it is water or air, each of which could be dissolved in the oil. The entire assembly was filled up and then left under vacuum for a week until bubbling reduced significantly. I also added two sacks of 3A zeolite molecular sieves for good measure after checking some studies on their effect on transformer oils.


Rectification
---

The transformer outputs AC at 50Hz, which should be rectified for proper fusor operation. Some sources claim this is not really necessary, which sounds plausible, but will at best only fuse atoms during the correct polarity, halving the efficiency or worse. There is generally no known advantage of AC over DC for a fusor as far as I know.

While it might be tempting to use the full difference between both ends via a standard rectifier bridge, this adds quite a few issues:

The x-ray transformer is center-tapped on the secondary and intended to be grounded there. One could theoretically leave the central GND connection floating, instead ground one of the ends and put the coils in series. But this comes with severe dangers to both humans and the coils. Most importantly, this removes the intended grounding, with all the negative consequences on safety and operation. It also doubles the voltage between the usually non-floating primary and secondary windings, quite possibly leading to arcing and break-down. The formerly grounded iron core of the transformer further heightens those chances and is at half secondary voltage in this arrangement. Normally there is only standard mains voltage between the transformer core and the primary when used as intended. It instead being at 50 times higher voltage is therefor almost guaranteed to cause catastrophic breakdown.

And worst, this all doesn't add much if anything: as the given transformer is intended for x-rays, it should be able to create 70 kV or more end to end, so half of that relative to ground. At later tests I indeed found that 230 VAC primary voltage between the Red and Blue connections results in above 30 kV on each individual secondary coil. Using any other pair would lead to even higher output, but it is unknown what is within the specifications. In short, it is simply advisable to put the coils in parallel after(!) rectification to double the potential current. The ideal circuit diagram thus looks like this:

[Diagram]

On each end, five diodes (aliexpress, ~1€ each and rated for 30 kV) soldered in series were connected, all ten together forming a half-circle for space reasons. At first glance a single 30 KV diode on each side should suffice. But not only would this put them right up to their limit, if there is capacitance towards GND they could actually see twice that. A further complication lies in small manufacturing differences between each diode. If the unavoidable leak currents of the blocking diodes are unequal, so are the voltages the diodes have to isolate by the same factor. The ideal mitigation has adequate identical resistors in parallel to each diode, chosen such that the current through each of them is larger than the maximal specified leak current of a diode. There is then a careful balance between wasting energy / current when the resistors are smaller, and chances of unequal voltage distribution when they are larger. In the end, I decided to chain at least twice as many diodes as needed and got them all from the same batch. Even if half of them fail and break down to become connectors, there would still be no unexpected short. If the worst happens, a short would only destroy the transformer without any further dangers to the outside.

Obviously the orientation of the diodes is chosen in accordance with the required negative voltage, so with their cathodes pointing towards the coils. The anodes of both diode chains are connected (called NEG in the following) and ultimately supply the cathode gasket of the fusor.

To keep track of the voltage, a divider is added inside the chamber, connecting NEG via resistors of 10^^9 Ohm and 10^^5 Ohm to GND, the smaller closer to ground. The factor between them was chosen to bring 30 kV down to 3 V, easily within typical microcontroller voltages. The divided voltage, now down in by a factor of ~10000, is fed outside to a voltmeter. Any fine-tuning of the measurement will be done digitally. The power loss through the resistor even at 100 kV is just (100,000 V)^^2 / 10^9 Ohm = 10 W and thus irrelevant. Smaller resistances might give better accuracy at the cost of higher power dissipation. The corresponding 30 µA at 30 kV are already relatively tiny but not unreasonably so. As the entire setup produces a few hundred Watts at most, total resistances below 10^^8 Ohm should definitely be avoided. 

Optionally a smoothing capacitor between NEG and GND can be added. This was so far skipped due to inherent dangers of a highly charged capacitor. Proper smoothing at 50 Hz would also require almost prohibitively large capacitances such as 100µF or ore.


Lid
---

For both safety and practicality, some kind of lid had to be added to the chamber. It should act as physical stabilization and strain relief on the cables while preventing people from touching any connections inside.

After several tries with various pieces of plastic, two variants were made. One from an old stainless steel decorative plate, the other from 1 cm thick acrylic glass, both otherwise built very similarly:

One hole each was drilled for NEG, voltage measurement and the supply cable (phase, null, GND), then all equipped with a cable gland. Just in case an overpressure valve was installed as well. A simple hole was deemed undesirable as it would allow fresh, wet air inside, adding unwanted moisture to the oil.


Voltage control
---

A standard variac (eBay, ~120€, 3 kW, 230 VAC 50 Hz primary, secondary variable from 0 to 300 VAC) is used to control the input voltage to the transformer, and thus linearly of NEG. The secondary lads to a CEE plug. It is not only rated for significantly higher voltages than mains, it also distinguishes the secondary while still having the comfort of a proper plug. To avoid blowing any more fuses (this particular variac blew them quite often when getting connected to mains, turning it into a game of chance), a simple thermistor-based inrush current limiter (Amazon, ~35 €) was added at the primary side.

A quick check of the innards showed that the output of the variac is not floating. Instead one wire is connected to one at the primary side. Ideally one would use this for null, but schuko plugs unlike CEE ones are fully symmetric by 180° and thus can not distinguish between phase and null.

[BILD]


Primary ballast
---

As seen above, the ohmic resistance at the primary side of an x-ray transformer is very low. For almost the same reason, the impedance of the relatively few windings is not high, either. This means that directly connecting it to the variac acts almost like a short, instantly exceeding limits and thus either blowing fuses or possibly causing damage. To remedy this, a ballast needs to be added. In principle, even a simple ohmic ballast such as a heater could be inserted. To waste less energy and avoid a hot room, a reactive ballast is much better. A cheap but decent choice is the primary coil of a microwave transformer, shorted and ideally also grounded at the secondary.

For safety and practicality, I put the entire inductive ballast inside a stainless steel food storage container with locking plastic lid. Two holes were drilled into opposing sides and cable glands were added to act as feed-though for cables, again ending in CEE plugs (one female, one male). Internally, the corresponding grounds were clamped to each other and the box. One phase was wired to go in and out of the primary, while the other (ideally null as forwarded through the non-floating variac above) is simply fed through.

[BILD]


Secondary ballast
---

The resistance between the fusor gasket and wall varies a lot during operation. Initially the resistance is that of centimeters of low pressure gas or vacuum, so extremely high. At higher voltages some ion flow happens, which at some point causes the resistance to suddenly become very low. To keep things in check and allow any operator (human or microcontroller) to react it is thus advisable to have an ohmic ballast on the transformer output. The exact value is hard to pin down, claims from 10^^4 to 10^^6 Ohm can be found.

I decided to use a 50 kOhm wirewound resistor on a large burnt clay pipe (aliexpress, ~30€). It was put into a plastic box filled with oil to isolate it from air and especially human stupidity. The oil is actually the yellowed transformer oil from the transformer.

[BILD]





