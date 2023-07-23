---
title: "Reactor Core"
date: 2023-06-02T22:34:32+02:00
draft: false
---

Deuterium injector
===

The aim of this component is to guarantee a steady controlled inflow of deuterium gas into the [reactor chamber](reactor-core.md). Only a very small amount is needed, which on one hand makes it easy to produce deuterium at a sufficient rate, but on the other hand requires special components to regulate such small flows.

Why deuterium?
---

The element most commonly associated with fusion is hydrogen. It is, after all, what the solar core expends to create helium and lots of power. Helium-3 is also sometimes mentioned as a future fuel supposedly mined from the moon to power a vast fleet of space ships. SOmeone knowledgeable in stellar physics is likely also aware that heavy stars fuse helium, carbin, and multiple other elements near the end of their lives. Lets review our options:




 When two of them merge, they almost always split back into the same constituents immediately after; in a sense, they don't stick together (more details in the final section). The heaver variants of hydrogen, named deuterium and tritium, are a much better fit. Merging any two of those usually results in helium, some neutrons, and quite a bit of energy. Similarly, the lightest stable version of helium (He-3) can be fused with similar rates, but does not produce neutrons.

- Protium (P, H-1): Normal hydrogen is by far the most common variant of this element, but is really bad for fusion. When two of them merge, they almost always split back into the same constituents immediately after without any gain; in a sense, they don't stick together. The effective rate is absurdly low, the sun only can work of this by sheer size.
- Deuterium (D, H-2): At roughly twice the mass per atom, it is surprisingly rare in the universe with initially ~0.00253% at the Big Bang, the exact ratios vary and in general decrease over time due to stars fusing it faster than protium. While different variants ("isotopes") of most elements behave all effectively identical from a chemical point of view, the extreme mass ratio (~2) between deuterium and protium causes notable differeces. This can not only be used by humans to separate them, it even happens naturally: rocky planets such as Earth tend to enrich it slowly, while losing protium to space. We ended up at ~0.015% in our water (~0.1% on Mars and a whooping 1.6% on Venus); low, but a good head start. Unlike protium, two deuterium cores fuse properly, usually into helium-3, a neutron, and energy.
- Tritium (T, H-3): The heaviest hydrogen variant that exists for longer than a blink of an eye. It is unstable and suffers radioactive beta decay into helium-3 at a half-life of 12.3 years, so after a decade, almmost half it is gone. It is used mixed with deuterium, as D+T fusion is particularly energetic, producing more than four times more energy (~17.6 MeV) per reaction than D+D (~4.0 MeV). But due to its short existence before decaying, it is almost only found as a product (intentional or not) of nuclear reactors and quite radioactive. This not only makes it very dangerous, it is also a banned substance worldwide due to nuclear treaties.
- Helium-3 (He-3): In theory an excellent nuclear fuel on its own because the fusion creates only helium-4 and protium, no neutrons at all. Neutrons, while also very useful in inducing nuclear reactions in fission reactors, are not only a type of radiation in itself, but also turn matter radioactive due to changing their isotope. It is however easier to fuse it with deuterium, which has the disadvantage of causing some neutrons when D+D happens. Its very large drawback is that helium-3 is very rare on Earth. Helium on our planet escaped into space over billions of years, that which we have at our disposal stems from alpha decays trapped underground. But the latter only produces helium-4, nothing but very rare decaying tritium ever refills helium-3.
- Helium-4 (He-4), Carbon (C), or other, heavier elements: those, especially helium-4, are viable fusion fuels in stars. But successfully fusing any of them requires even more extreme conditions, biollions isntead of dozens of millions of degrees. This is ultimately out of reach even for large scale reactors, even more so for hobbyists.

In short, only three kinds of atoms work at reasonable rates, of which two are effectively not available to us. The single one left is deuterium.



Deuterium production methods
---

Deuterium can be bought in metal cylinders, prices are very high, though. It is much cheaper to extract it from [heavy water]() (D2O), water with deuterium instead of protium. At often 3 € per gram for small quantities, prices on for private buyers are much higher than for industrial quantities, but affordable in the amounts we need. Ten grams are enough to get things started. Luckily, I was able to procure a 100 mL bottle for less than 100 €, a very good price.

Splitting heavy water into deuterium and oxygen is possible in the very same ways as with normal water. The general goal should be pure D2 gas free of oxygen, (heavy) water or other substances.

A chemical method is adding [alkali metals](alkali-metals.md) such as sodium, reacting violently and forming (heavy, dissolved) caustic soda (NaOD) as byproduct via 2·D2O + 2·Na -> D2 + 2·OD^^- + 2·Na^^+ . Apart from the obvious dangers of a [Coulomb explosion](), a major disadvantage is the production of large amount of heavy water steam and vapor due to the energetic nature of the reaction. Consequently, the deuterium gas needs to be dried, for example by flowing it through [silica gel]() or [molecular sieves](), which also wastes some heavy water. In total, while surely feasable when taking appropriate measures, this method is too much of a hazzle when better ones are available.

The electrochemical alternative is electrolysis, flowing electricity through heavy water. The simplest way is to stick two conductive rods into (heavy) water and apply a small voltage (~3V). At the positive end ("anode"), oxygen is released, while the negative side ("cathode") bubbles off deuterium gas. Pure water is actually a very good isolator, so adding some salt is required to increase the current many-fold. Sodium/potassium hydroxide (NaOH, KOH) are particularly suitable for this job, but care must be taken because they would add non-heavy hydrogen atoms to the mix, which will intermingle with the deuterium. To avoid this, one has to use sodium/potassium _deuteroxide_ (NaOD, KOD). Buying is an option, but splendidly this stuff is exactly what is left in solution by the prior method. Hence taking small initial loss gives a never again decreasing stock.

Self-built electrolysis cells with stainless steel or carbon electrodes are the cheapest option, and quite possibly also not that bad when done right. It just requires some engineering and effort to fully separate both gases while also keeping a heavy water connection between them. It should be assumed that some heavy water still evaporates, requiring drying of the deuterium gas, but likely at significantly lower losses than the previous example.

A very interesting and also our final choice is a PEM (**P**roton-**E**xchange **M**embrane) reversible fuel cell. Most instances found on the internet such as eBay or AliExpress are non-reversible cells, which will quickly decay when used for electrolysis. At least I tried three different ones without long-term success. A truly reversible one now in use comes from [Horizon Educational](https://www.horizoneducational.com/pem-transparent-reversible-fuel-cell-1-unit/p1170) at ~80 €.

[BILD]

Lastly, further methods exist. For example and if somehow acquired as such, deuterium chloride (DCl) dissolved in heavy water, that is, heavy hydrochloric acid, can make an easy source. Adding metals will slowly dissolve most of them while producing deuterium gas. Iron results in a reasonable slow rate, aluminium or magnesium get quite rapid. This is effectively a less violent variant of the alkali method. The resulting gas will likely again require drying and potentially even removal of acid, both of which can be achieved by flowing it over sodium/potassium hydroxide.



PEM cell assembly
---

At the center of a PEM cell sits the eponymous membrane, supported by a conducting mesh. Regardless of the mode of operation, hydrogen, or in our case deuterium, interacts on the cathode's side, oxygen and water on the anode. This means that when used as a fuel cell and fed with both gases on the respective sides, the resulting water ends up on the same side as the oxygen (usually from air) and needs to be removed. When used for electrolysis, a reverse problem happens: the anode requires a consistent supply of water as running he cell dry can damage it, while the produced oxygen gets discharged.

My setup has a small reservoir made from a 10 mL centrifuge. A peristaltic pump, as to keep things clean and separate, cycles the (heavy) water around. Any oxygen can escape with the water to the reservoir's top connector, and then out of a simple overpressure release valve originally intended for aquariums.

The hydrogen/deuterium is then fed into a small steel pipe filled with 4A molecular sieves that also acts as a small buffer. To prevent particles from being swept along, the ends are equipped with a standard water pipe sieve and cotton wool.

[BILD]


Inflow control
---

Only a very small amount of deuterium is required to keep the fusion process alive. Too much and the reaction is stifled while deuterium is wasted through the ongoing outflow to the [vacuum pump system](). Too little and it simply runs out of fuel. The solution for such fine tuning is vacuum dosing valve.

[BILD]

A low pressure analog output pressure sensor was added to keep an eye on the stored amount of deuterium gas. Pressures far off from standard atmospheric ones could damage the PEM cell and also make the valve control less reliable. Hence why the feedback from the sensor controls the power to the PEM cell; due to the low rates, a simple on-off is assumed to suffice, adjusting the voltage/current to the cell is wasted effort. It was decided to turn gas production off above 1.1 bar and on below 0.9 bar but surely many other settings work.

[BILD]

As an additional measure, and because some were already lying around, a shut-off valve was added before the dosing valve. This allows thy system some basic control over the inflow, while also preventing deuterium loss if the main chamber needs to be serviced.

[BILD]



More on hydrogen fusion
---

The following is a simplified yet accurate description of how the different variants of hydrogen interact inside the sun, and thus also in a suitable reactor. To keep things simple we will continue to use to atomic names (deuterium, tritium, helium, ...) instead of the more correct names for their sole cores (deuteron, triton, helium nucleus, ...) with the exception of protons/protium.

Inside the sun, protium or rather naked protons are fused. The main mechanism for this is the formation of di-protium, two protons stuck together. This is extremely unstable and splits back into both parts within fractions of a picosecond. But there is a tiny chance for a beta+ decay to happen, turning the di-protium into deuterium by releasing a positron, which ultimately annihilates with an electron into pure energy, and a neutrino that flies off into space. On average it takes a proton billions of years until it ends up as part of deuterium. In total, this process releases only little energy compared to other nuclear reactions, but it creates a steady supply of much more reactive fuel.

Now that there is some deuterium, it can quickly fuse further. Only very rarely will it directly meet another deuterium, it is much more likely to stumble upon a proton. This forms helium-3, two of which can fuse into helium-4 and 2 protium.

[Pic from WP]

There are some further reactions that turn protium into helium by using heaver elements as a catalyst. The most famous one is the CNO cycle found in heavier stars than the sun, where nuclei of carbon, nitrogen and oxygen repeatedly absorb protons and release positrons (plus neutrinos), turning them into each other. Every four protons, minus two positrons, a helium-4 is released, colloquially known as alpha decay. Other process chains involve helium-4, which successively absorbs and emits until it effectively doubled, where it then splits again into two copies.

[Pic from WP]

