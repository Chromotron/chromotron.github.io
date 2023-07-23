---
title: "HV-Transformer"
date: 2023-06-02T22:35:27+02:00
draft: true
---




Due to an interesting quirk of nature, the ultimate speed/energy which any fixed type of charged particle reaches at the center of the [gasket]() only depends on the voltage difference between the reactor walls and the gasket. For deuterium fusion, about 30,000 V are often quoted as a good ballpark. Above 40,000 V, a lot more x-rays are produced, thus requiring special shielding, while below 20,000 V the fusion rates are close to none. Furthermore, a relatively high current of 10 mA is recommended for good rates, putting the power demand at 300 Watts or more before any losses are accounted for. As in an [ohmic]() resistor, voltage and current are coupled by the effective resistance of the setup, which therefore has to be balanced accordingly.

The central [gasket]() needs to be negatively charged relative to the chamber walls. For safety and sanity, the walls of the fusor must not be at dangerous voltages and thus gets grounded along with all other outsides. Hence a negative direct current (DC) at -30,000 V has to be fed to the gasket.

This begs the question of how such electricity can be safely supplied.


Transformer overview
---

An electric transformer trades voltage for current. Under ideal conditions they up (or down) the voltage by the same factor as they reduce (or increase) the current. Losses are almost always relevant and lead to unwanted heating. Apart from rare cases unsuitable for our case, transformers work based on electromagnetic induction and thus require alternating current (AC). Put simply, two coils called primary and secondary are wound around a magnetically conductive core. When supplied with alternating current, the primary creates a similarly fluctuating magnetic field inside the core, which in turn induces voltage in the secondary coil. 

In essence, each winding acts like a little voltage source, all of which are put in series. If there are m windings on the primary and n on the secondary, the voltage on the secondary is n/m times as large as that on the primary, while the current gets multiplied by the reverse fraction of m/n so that the total power stays the same, if losses are ignored.

We want DC on the fusor, so we will have to rectify the output AC with diodes. Optionally, a capacitor can be added to filter the rectified sine wave into a flat(ter) DC.

There are two major design types available to us: large cores connected to mains at 50 Hz (or 60 Hz in some places), or more complex switching supplies working with small cores at much higher frequencies. Both were tried, each coming with their own issues and design challenges.


X-ray transformer
---

An old x-ray transformer was found on eBay at the very reasonable price of 110 €. It is on the smaller end and came without any enclosure. X-ray transformers need to be fully immersed in appropriate oil which acts both as isolator and coolant. Running it without oil will almost surely cause internal arcing and instant damage to the windings, rendering it worthless. Together with a proper oil and cooling containment, those transformers can weigh multiple hundreds of kilograms. Meanwhile and even with oil and additions, mine ended up at only 15 kg.

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

While X and Y are very likely the analogues of the high voltage outputs A and B, and GND easily matches its namesake, the remaining ones were harder to identify. At first measuring resistances by means of a multimeter was attempted. It turned out that GND was indeed connected to the metal parts of the core at no measurable resistance, as well as X by ~79 kOhm. Similarly, Y was connected to q at the same resistance, indicating that it is "mA".

A very low resistance <1 Ohm was measured between each of r, s, v and w, with their choice of color being a bit confusing. There is also a medium resistance of ??? Ohm between t and u. All other pairs are disconnected.

While trying to find any datasheets or documentation, I landed on the corresponding section at [Fred's Fusor](), a website I had already used multiple times before. It turned out that they had a very similar transformer, the main difference being a lack of two thinner wires (likely the brown ones, as seen below). They give two supposed internal wirings, the second found with help from [fusor.net]().

Based on all of the above and still not really knowing what is what, I very carefully connected some pairs of wires to mains (230 VAC, 50Hz) via a variac, with the goal of applying only a few Volts at 50 Hz. All standard high voltage precautions (one-hand-rule, not touching any potentially life wires or even any part of the transformer) were used as even at such voltages, the secondary could reach several thousands of Volts. There is also always the danger of damaging the coils by arcing if testing without immersing the transformer in oil. As a first test result and contradicting the two diagrams from Fred's Fusor, it turns out that t and u are not the primary as they induce effectively no voltage between any of X, Y, GND and q. Instead, they might lead to the second coil of the flat arrangement at the end, where Z and W connect. Applying even low voltage at any pair of r, s, v and w leads to high voltage between X and GND, as well as Y and q. In conclusion, my guess on those last four connections is correct, while the the primary winding seems to be divided into three sections at r, s, v and w in some order.

A more specific measurement at all pairs of those four gives the following resistances:

[Diagramm]

It is thus safe to assume that they connect in the order [...]. This was further confirmed by a corresponding reciprocal dependence when applying low voltages to them.

For better access and later use, longer wires where soldered to GND, q, r, s, v, w.


Enclosure and oil
---

An old and cheap vacuum chamber for drying and degassing made of stainless steel was re-purposed as enclosure.

[Bild]

With some effort, solder and hydrochloric acid, two brass connectors were soldered to its inside (see the pictures below). They act both as mechanical anchors for the upper parts of the following build as well as an internal ground connector. Grounding the enclosure is simply a matter of safety. Even if entirely disconnected from the transformer it could otherwise still accumulate quite some charge, acting as a capacitor similar to a Leyden jar with the outside world. The transformer was then simply put at the bottom, which adds a second grounding connection between it and the enclosure in addition to the GND wire.

To ensure proper operation and avoid arcing, the entire transformer had to be immersed in oil According to some sources, almost any kind of dry oil from rape seed and sunflower to synthetic silicon oils should work. I cannot vouch for this, but for simple home applications it sounds plausible. However, the better an oil suits this specific job, the better the life expectancy of the core.

Initially, I tried pure paraffin oil that was around from my [experiments in creating alkali metals](). A lot of brownish old residues quickly dissolved from within the coils and spread through the oil. To improve this, an oil change seemed unavoidable. As I already ran out of paraffin oil and prices are similar, a small 20 liter barrel of specialized transformer oil (Shell [...]) was bought. The transformer given one day to drip dry of the first oil and then put back into the chamber, where then the new oil was added until it was fully immersed.

The oil needs to get into every cavity inside the coils, having air bubbles can be as detrimental as not having oil at all. The industry standard is to put the transformer into vacuum and only then dip it into the oil, all while not letting any air in. This and the following also has the added advantage of removing most water from all parts, as it boils instantly at low pressures. But this requires special equipment and is thus unfeasible for me. As a next best method and using that my enclosure is a (former) vacuum chamber, I instead put the immersed core under vacuum (~ 1-10 mbar). This expands the air bubbles by a large factor (~100), making most of them escape. To get any remaining ones to go, the setup was carefully shaken. A few times air was let in again and transformer was rotated before again applying vacuum. It seems that just normalizing pressure followed by vacuum has some effect as well, even without any shaking or rotating.

As a note, using higher vacuum is ultimately pointless and potentially counterproductive. One millibar is about the same pressure as a centimeter of water or oil above. Therefor the pressure under several centimeters of oil will never get lower than a corresponding number of millibars. Thus applying vacuum below 1 mbar is not really improving much except directly below the surface. Furthermore, additives or even the oil itself may vaporize at those conditions, degrading the oil, in particular its ability to absorb water, which it does more than one might think.

The above un-airing and drying procedure lasted for about a week. It was repeated two weeks and a month later. Especially at those later instances, some strong bubbling at corners and wire ends was observed. This is likely dissolved air and water being released at [nucleation sites]().


Rectification
---

The transformer outputs AC at 50Hz, which should be rectified for proper fusor operation. Some sources claim this is not really necessary, which sounds plausible, but will at best only fuse atoms during the correct polarity, halving or worse the efficiency.

While it might be tempting to use the full difference between both ends via a standard rectifier bridge, this adds quite a few of issues:

The x-ray transformer acts effectively as any typical transformer, but is center-tapped on the secondary and intended to be grounded there. One could theoretically leave the GND connection floating, instead grounding one of the ends, to put the coils in series and thus double the voltage. But this comes with severe dangers to both humans and the coils. Most importantly, this removes the intended grounding, with all the negative consequences on safety. It also doubles the internal voltages between the internal wiring, quite possibly leading to arcing and break-down. The formerly grounded iron core of the transformer further heightens those chances. And worst, this probably doesn't add much if anything: if one wants to get twice the voltage out of it while already exceeding the intended internal voltages by a factor of two, one could just as well ground the center tap but apply twice the voltage on the primary, whose insulation is unlikely to be the limiting factor.

Instead, we want to use the two coils in parallel:

[Diagram]

As the given transformer is intended for x-rays, it should be able to create 70 kV or more end to end (later verified to be indeed the case); so half of that relative to ground. We aim for 30-40 kV, so that is enough, and the variac could be used to slightly exceed the intended voltages if so desired. As a bonus, we now get twice the potential current, which is often the limiting factor on other fusor transformers.

On each end, six diodes (microwave, easily and cheaply to come by on the internet) were directly soldered on in series, arranged in a wide zig-zag because space is limited. As each offers a break-down voltage of 12 kV, they can theoretically deal with up to 72 kV. This ideal value is hardly reached in reality, but we only need 40 kV anyway. The anodes of both diode chains are then connected and supply the cathode of the fusor, called NEG in the following.

To safely keep track of the voltage, a divider is added inside the chamber, connecting NEG via resistors of 10^^10 Ohm and 10^^6 Ohm to GND. The middle, now down in voltage by a factor of ~10000, is fed outside to a digital voltmeter. Fine-tuning of the measurement is done at the sensor end, either by adding another resistor to ground or simply scaling appropriately in code. The power loss through the resistor even at 100 kV is just (100,000 V)^^2 / 10^10 Ohm = 1 W and thus irrelevant. Using smaller resistances might give better accuracy at the cost of higher power dissipation. As the entire setup produces a few hundred Watts at most, total resistances below 10^^8 Ohm should be avoided.

In similar manner, a smoothing capacitor between NEG and GND can be added. Due to inherent dangers of a highly charged capacitor, this part was initially left out, but intended to be added later. Three poly[..] capacitors rated as 3nF at 30 kV each were put in series to create a capacitance of 1 nF at theoretically up to 90 kV. As with the diodes, the real maximum voltage might be significantly less, even more so for capacitors.


Lid
---

For both safety and practicality, some kind of lid had to be added to the chamber. It should act as physical stabilization and strain relief on the cables while preventing people from touching any connections inside.

After several tries with various pieces of plastic, an old stainless steel decorative plate was used. One hole each was drilled for NEG, voltage measurement and the supply cable (phase, null, GND), all with a dedicated cable gland with strain relief. Just in case an overpressure valve was installed as well. A simple hole was deemed undesirable as it would allow fresh and in particular wet air to flow inside, potentially adding moisture to the oil.


Control
---

A simple variac (3 kW, 230 VAC 50 Hz primary on mains, secondary variable from 0 to 300 V) is used to control the input voltage to the transformer, and thus linearly the one of NEG. A schuko plug including a ground connection was added to th secondary side for ease of use. To avoid blowing any more fuses (this particular variac blew them quite often when getting connected to mains, turning it into a game of chance), a simple thermistor-based inrush current limiter (Amazon, ~35 €) was added at the primary side.


Ballast
---

As seen above, the ohmic resistance at the primary side of an x-ray transformer is very low. For almost the same reason, the impedance of the relatively few windings is not high, either. This means that directly connecting it to the variac acts almost like a short, instantly exceeding limits. To remedy this, a ballast needs to be added. In principle, even a simple ohmic ballast such as a heater could be used. To waste less energy and avoid a hot room, a reactive ballast is better. A cheap but decent choice is the primary coil of a microwave transformer, shorted and ideally also grounded at the secondary.

For safety and practicality, I put the entire thing inside a stainless steel food storage container with locking plastic lid. Two holes were drilled into opposing sides and cable gland with strain reliefs added to act as feed-though for cables, leading to a male and female schuko plug. Internally, the corresponding grounds were connected to each other and the box. One phase was wired to go in and out of the primary, while the other (ideally null, but not distinguished by schuko plugs) was simply fed through.

[BILD]








