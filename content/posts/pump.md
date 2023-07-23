---
title: "Pump"
date: 2023-06-02T22:35:27+02:00
draft: true
---


A typical setup to reach decent vacuum involves two pumps in series: a initial, _roughing_ pump that brings the pressure down to 1 mbar or less, followed by a more sophisticated secondary. Most roughing pumps have one or two stages, each of which works on a relatively simple principle, usually moving gases forward by physical pushing. Meanwhile, the refined vacuum of the second stage requires rather unusual methods.

The interested hobbyist should beware that the cost of a proper pump can easily exceed 1,000 €, quite possible well above that. Used pumps can often be found on eBay at all kinds of conditions at a wide price range. It is generally hard to judge their quality without a test run, turning them into a kind of gamble. Especially turbomolecular pumps are notorious for the effects of long-term use, while diffusion pumps can be quite resilient. Most roughing pumps can be serviced by an amateur, but finding spare parts is not always easy. WHen metal parts are damaged, a repair is rarely worth the effort.

We describe some of the most common types below and then take a look at the actual setup.


Rotary vane
---

In those, an eccentric cylinder rotates within a chamber, touching at one side. The cylinder comes equipped with several extendable vanes which push against the chamber via springs. The resulting movement pushes air along the rotation while the vanes also act as a kind of valve. Typically, the vanes are made of rubber to form a basic seal against the outer wall.

For proper operation, the entire pump is placed in an oil tank. The oil not only acts as a coolant, it is most important to improve sealing to a level where reasonable vacuum can be reached.

Rotary vane pumps are relatively cheap, easy to operate, and create vacuum down to even less than 1 µbar with a second stage. They can work with many gases when equipped with a [...] and the right oil, but not to the extent some membrane pumps can; this is however of little consequence for fusor purposes. Rotary vane pumps are also not really louder than most alternatives, which still means they can be quite noisy. Due to the potential of oil mist backflow, a shut-off valve should be added and closed in advance whenever the pump is shut down. It is also advisable to add an oil mist filter to the exhaust, as quite some is produced when initially sucking on atmospheric pressure.


Membrane pumps
---

As basic principle, a piston moves a membrane up and down to repeatedly create and fill a cavity. Combined with unidirectional valves for in- and outflow, a net transport results. Often more intricate setups can be found, but ultimately the same basic principle applies.

Unlike the previous example, they work free of oil and thus without chance of backflow. They tend to be a tad more expensive for a somewhat lower pumping speed, though still affordable and fast enough for hobbyists. If needed, the chemical resistance is entirely determined by the membrane (and piping) materials, hence usually quite good. At much higher cost, even PTFE ones can be found.


Peristaltic
---

Conceptually very easy to grasp, those pumps pinch a hose and press it forward. As expected this moves whatever is contained in that section of the hose with the pinch. A typical setup consists of a rotating center of varying thickness, often with rollers to reduce friction.

Unlike the other methods listed here, a peristaltic pump has no direct contact to the interior of the hose. Therefore chemical resistance is about as good as it gets. They can also be run at slower paces and be used to control the exact amount of puped volume rather precisely, as is often done for (bio-)chemical experiments. However, the constant (un)stretching slowly damages the piping which thus needs regular replacement. The pumping rates are also significantly below the prior two types. In general, they are better suited for chemistry than vacuum applications. [We however take use of one such pump for deuterium production.]()



Turbomolecular
---

To greatly improve the vacuum, a secondary pump is used. One of the most prevalent variants, a _turbomolecular pump_ is like a fan on steroids: made from a massive block of metal, wielding hundreds of little blades reminiscent of an airplane turbine, and rotating with supersonic speeds at up to 120,000 rounds per minute (that is 2000 rounds per second!). [[https://upload.wikimedia.org/wikipedia/commons/4/4c/Cut_through_turbomolecular_pump.jpg?20051129184117]]

They are a work of precision, engineered to bat gas molecules outwards, towards the primary pump. Technically speaking, they are actually compressors, they take gas and compress it into lesser vacuum. This only works if the outlet pressure is already pretty low, some require 1/1,000,000th of atmospheric pressure. Modern ones often come with an extra stage to start as high as 1/100 atmospheres. [See the corresponding Wikipedia article or other sources around the web for further details on the mechanism](https://en.wikipedia.org/wiki/Turbomolecular_pump).

The speeds are so extreme, even a single fingerprint is enough to exert up to dozens of kilograms of centrifugal force. Just like similarly fast rotating ultra-centrifuges, they can fail spectacularly; and deadly. [Here is what the aftermath of a failing centrifuge looks like](https://web.mit.edu/charliew/www/centrifuge.html): a massive piece of titanium was ripped apart and made a huge hole into a very thick steel wall (there to contain exactly such events)! If something falls into a turbomolecular pump or any interal part breaks, the damage to the blades is usually devastating and irreparable:

[https://www.lesker.com/images/faqimage-failedturbopump.jpg](Source: Kurt J. Lesker Company)

Even simple air at normal pressure can easily kill it:
(https://external-preview.redd.it/wlPHFPJpe5VR-zq-ZxmKH6FaZPPkHV5ozGtbVLYBWKw.jpg?width=432&auto=webp&v=enabled&s=78fef6f94ab7962dda4b8b2853288d9e5a4efa56) [Source: Reddit]




Diffusion
---
An alternative solution still in use but falling a little out of favor recently is an _oil diffusion pump_. They vaporize oil which then streams upwards in a jet and drags remaining gas along. Similar to turbomolecular pumps, they need an already low pressure to begin working. Their failures are usually not as impressive, but comparably expensive. They are very silent, but this is offset by the rather dirty operation. To prevent oil mist backflow, a suitable condenser cooled for example by a Peltier element should thus be added.




The pump setup
---

Many years ago a very used Vacuubrand MD-4 was bought at ~250 € for degassing, drying as well as a a few other chemical and physical applications. While enough for those purposes, it turned out to be insufficient for deeper vacuum. At best it would reach 5 mbar and even a change of most seals did not improve much. Even a cheap (~60 €) pump from China turned out to get lower by a factor of ~10, but at a significantly lower pumping speed.

[BILD]

In general, this model is known to be sturdy and to take some abuse, so another Vacuubrand MD-4 in good-looking condition was bought from an industrial re-seller. It turned out to have been refurbished as recently as 2015, according to a sticker. Indeed, it works beyond expectation, reaching down to 1.3 µbar after some warm-up time. The official ultimate vacuum at factory condition is claimed at 0.5 µbar. This nice find is what initially reignited the idea of building a fusor, now that a first stage which could reach good enough vacuum on its own was acquired. However, and also in light of a few other projects in the queue, a secondary pump was still searched for.

[BILD]

Luckily, a very affordable (375 €) little turbopump was found: a Varian Turbo-V 70LP, second-hand but supposedly unused.

[BILD]

It took some effort, but was also able to find two controllers for it, a brick and an open one:

[BILDer]

The brick version was previously unused but did not came with a cable for its very unusual plug. Some simple internal re-wiring was done to re-route the GND and to replace the plug with a cable. The other end of the cable was equipped with the standard [...] connector the V70 uses. Very cautious tests were done, where pump and controller ran without issues. At the first full run using a cold cathode gauge, an ultimate vacuum below 1 nbar was reached within minutes. This is easily enough for a fusor, but can surely be improved by longer runs and doing a bake-out in the future.

The open controller already came with a [...] connector already attached to it. It was successfully tested with a V70 of a friend.

Funnily, I never found the exact manual for either of those controllers. There are is a surprisingly large number of different versions of the V70 and its controllers out there, with different connectors and design parameters. However, several manuals were found to sufficiently match the PCBs in the controllers at hand to supply the needed informations.

