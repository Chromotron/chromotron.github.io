---
title: "PEM cell assembly"
date: 2023-06-02T22:34:32+02:00
draft: false
---


As elaborated in the page on [deuterium]() a home fusion reactor almost exclusively relies on this gas as fuel. Sadly it is not easy and cheap to acquire. Luckily a fusor only uses minute amounts. Problematicly most of it gets wasted.

Deuterium can be bought in expensive metal cylinders. It is cheaper to extract it from [heavy water (D2O)](), water with deuterium instead of the usual protium. Industrially it is produced electrochemically via various processes which utilize the small but notable chamical differences between protium and deuterium. So that is the route I went for.

Heavy water prices for private buyers are high at currently above 3 € per gram for amounts ranging from 10 to 1000 grams, but still somewhat affordable in the amounts we need. Ten grams are enough to get things started. Do not buy heavy water in tiny ampules, those are usually overpriced. Luckily I was able to procure a 100 mL bottle for less than 100 €, a really good price.


Deuterium from heavy water
---


Splitting heavy water into deuterium and oxygen is possible in the very same ways as with normal water. The general goal should be pure D2 gas free of oxygen, (heavy) water or other unwanted substances.

A **chemical method** is adding [alkali metals](alkali-metals.md) such as sodium or alternatively alkaline earth metals such as calcium. They react violently, forming (heavy, dissolved) caustic soda (NaOD) as byproduct via 2·D2O + 2·Na → D2 + 2·OD^^- + 2·Na^^+ . Apart from the obvious dangers of a potential [Coulomb explosion](), a major disadvantage is the production of heavy water vapor due to the energetic nature of the reaction. Consequently, the deuterium gas needs to be dried, for example by flowing it through [silica gel]() or [molecular sieves](), which means quite a bit of heavy water is wasted. In total, while surely feasible when taking appropriate measures, this method is too much of a hazzle when better ones are available.

Similar methods exist. For example and if somehow acquired as such, deuterium chloride (DCl) dissolved in heavy water, probably better called 'heavy hydrochloric acid', can make a reasonable source. Adding metals will slowly dissolve them while producing deuterium gas. Iron results in a slow rate, aluminium or magnesium get quite rapid. The resulting gas will likely again require drying and as well as removal of acid, both of which can be achieved by flowing it over sodium/potassium hydroxide.

The electrochemical alternative is **electrolysis**, flowing electricity through heavy water. The simplest way is to stick two conductive rods into (heavy) water and apply a small voltage (~3V). At the positive end ("anode"), oxygen is released, while the negative side ("cathode") bubbles off deuterium gas. Pure water is actually a very good insulator, so adding some salt is required to increase the current to useful levels. Sodium/potassium hydroxide (NaOH, KOH) are particularly suitable for this job, but care must be taken because they would add non-heavy hydrogen atoms to the mix, which will intermingle with the deuterium. To avoid this, one uses sodium/potassium _deuteroxide_ (NaOD, KOD). Buying is an option, but splendidly this stuff is exactly what is left in solution by the previous method. In short, we just have to very carefully drop pure sodium into heavy water. Taking this small initial loss gives a never again decreasing stock of salt.

Other salts also work as long as they don't introduce any unwanted hydrogen. However one should still avoid those which produce hazardous gases at the anode unless care is taken. This includes common table salt NaCl where toxic chlorine is released.

Self-built electrolysis cells with stainless steel or carbon electrodes are the cheapest option and quite possibly also not that bad when done right. It  requires some engineering and effort to fully separate both gases while also keeping a heavy water connection between them. It should be assumed that some heavy water still evaporates, requiring drying of the deuterium gas, but at significantly lower losses than the first method.

A very interesting option and also my ultimate choice is a reversible **PEM** (**P**roton-**E**xchange **M**embrane) **fuel cell**. Most instances found on the internet such as eBay or AliExpress are non-reversible, which will quickly decay when used for electrolysis. I've tried two versions, both of which worked at first for electrolysis but at exponentially worse rates. A truly reversible one can be bought from [Horizon Educational](https://www.horizoneducational.com/pem-transparent-reversible-fuel-cell-1-unit/p1170) at ~80 € and is what I ended up using.

[BILD]



PEM cell assembly
---

At the center of a PEM cell sits the eponymous membrane, supported by a conducting mesh on each side. Regardless of the mode of operation, hydrogen interacts on the cathode, oxygen and water stay on the anodic side. This means that when used as a fuel cell and fed with both gases on the respective sides, the resulting water ends up on the same side as the oxygen (usually from air) and needs to be removed. When used for electrolysis, a reverse problem happens: the anode requires a consistent supply of water as running he cell dry can damage it and the produced oxygen needs to be removed.

My setup has a small reservoir made from a 10 mL centrifuge tube. A peristaltic pump, as to keep things clean and separate, cycles the (heavy) water around through the PEM cell and back to the reservoir. Thus the oxygen is flushed out to the top of the reservoir and can then escape through a very simple overpressure release valve originally intended for aquariums. This design was tested with demineralized water first, then a proper assembly was 3D-printed.

[BILD]


Piping and drying
---


After multiple variations, the deuterium is now fed into standard KF DN-10/16 piping. Earlier (deuterium-less) tests with water pipes and various kinds of threads all showed significant leakage. The current setup consists of, in this order towards to [reactor core](), an isolation valve, a pipe filled with 4A molecular sieves, a pressure gauge, ending in a vacuum inflow valve. The ends of the drying part have cotton whool and sintered filter centering rings to prevent particles from getting swept around.

[BILD]



Production & pressure control
---

The gauge is a basic mechanic over-pressure sensor for the 1 to 1000 mbar range and has an analogue output (1-5 V). It is helpful to know the current amount (i.e. pressure) of deuterium gas. Production control is then quite simple: if the pressure is below our chosen threshold, then power is sent to the PEM cell to produce more. A single fixed pressure also makes other adjustments more reliable and especially reproducable.

The target pressure is ultimately up to setup and personal choice. It is not known to me how well PEM cells react to pressures far outside their usual range, especially vacuum. So I decided to go with 0.9 bar: slightly below the outside to minimize leakage while still clearly within the range of the gauge and certainly fine for the PEM cell. Yet anything from 0.5 to 2.0 bar is probably fine, too.

The gauge actually also has a direct NPN output with settable threshold, which would allow for direct control without any further electronics. But I want to know the pressure anyway, just in case.

[BILD]


Inflow control
---

Only a very small amount of deuterium is required to keep the fusion process alive. Too much and the reaction is stiffled while deuterium is wasted through the ongoing outflow to the [vacuum pump system](). Even higher and problematic and dangerous arcing could occur. Too little and the reactor simply runs out of fuel. The solution for such fine tuning is two-fold: a [flow valve before the turbo pump]() to fine-tune the pumping rate, and a vacuum dosing valve adjusting and limiting the deuterium inrush.

[BILD]

Such valves are quite fine in their adjustments, typically a needle valve on a fine thread. In my experience they are only rarely available in used condition and otherwise expensive. I got mine from eBay (~160 €) after weeks of looking for one.

I 3D-printed a thick PETG handle and cover. This allows me to safely turn it even if the reactor is running, at which point it should still be grounded at entire outside, but any extra protection is not a bad idea. I put special care to ensure there are no exposed conductive surfaces on it.

[BILD]

A plan for later improvement is to connect the valve to a stepper motor. This would allow for automatic inflow control and thus higher autonomy for the [control system]().