---
title: "Oceangoing Autonomous Catamaran"
categories: ["Drone", "Boat", "RC", "CAD"]
date: "2024-04-10T03:24:40Z"
draft: false
cover:
  image: "posts/auto-catamaran/Screenshot 2024-06-21 135247.png"
  alt: "catamaran cover"
  hidden: false
  hiddenInList: false
  hiddenInSingle: false
  relative: true
---

A research project in my university lab with the aim to develop highly modular, 3D printable unmanned surface vehicles (USVs) for research and cargo transport

# Overview

I originally modeled this vessel two years before its construction because I wanted to make an oceangoing RC boat that I could use to lower a camera under water to watch marine life. The project stayed as a model on my computer until the present day when I enrolled in a robotics class in uni. This class gave me the opportunity to fund the project as well as a collaboration with the lab I work at to turn this boat into a modular platform for research applications. 

# Design Considerations

The main design considerations and features specified were as follows:

1. Hulls constructed primarily using 3D printing
2. Capable of carrying over 40kg of payload
3. Able to operate in up to sea state 4
4. Remain afloat with multiple compartments flooded
5. Have hardpoints that allow a crane to lower the craft from a pier
6. Large battery for muti hour driving.
7. Accurate GPS position holding
8. Capable of deploying towed sensor packages
9. Highly maneuverable with short stopping distance

Taking these considerations into account, I settled on a catamaran hull as it provides good stability as well as a large open space between hulls to deploy equipment. Each hull would be split into independent watertight compartments joined together with bolts. Jet drives were selected because of their high thrust for their size as well as having low draft and superior ability to prevent tangling on debris. To help stabilize the craft and position hold, each hull would have lateral
thrusters to allow omnidirectional movement.

# CAD

![cad overview](image.png)

The initial design I came up with consisted of two hulls each comprising of 7 watertight compartments. Each hull has bulkheads on either end that go up to the top of the hull with no openings other than a gasket sealed wire channel and a hole for a steel keel tube that runs the length of the hull. Bulkheads are secured to each other using multiple large screws that are also gasket sealed. 

![wire channel](Screenshot2024-07-12223843.png)
![compartments](image_1.png)
To connect the hulls, the craft has four hardpoints, one fore and aft on each hull. This hardpoint also have a slot for a metal plate that connects the keel tube with a lifting eyelet.

![lift plate](Screenshot2024-07-12224236.png)
![truss mount](Screenshot2024-07-12223917.png)

As each compartment is to be 3D printed, I optimized the design to minimize post processing by making it so that there would be no overhang greater than 45 degrees other than the hull exterior. This way, no supports would be needed inside the hulls and the ones outside would be one easy to remove block. 

![crosssection](Screenshot2024-07-12225256.png)

The jet drives were difficult to measure out and I couldn't acccurately account for ABS shrinking so I had to get a bit creative. The drives would be fitted to an adapter plate then acetone welded into place.

![plate](Screenshot2024-07-12223946.png)

It was a pretty good design and in hindsight, performed it's task well given the limited timeframe to construct.

# Construction

![printing](20240501_105141.jpg)

After finalizeing the hull, It was time for construction. For two weeks, we ran a bambu P1S and my custom creality CR-10S to print all 18 pieces. Ultimately, it took a little over two weeks consuming roughly 14 kg of filament. Once a single hull was fabbed, I took it out to a pool test (without telling the HOA).

![single hull test](20240517_085217.jpg)

The displacement of the hulls were close enough to the estimates so work continued. Once both hulls were assembled and tested, ABS slurry was painted onto the exteriors of the hulls to guarantee waterproofing. Silicone was also applied to the perimeter of the jet intakes.

![acetone application](20240607_003256.jpg)
![silicone](20240607_003028.jpg)

Finally, the boat is ready to be wired.

![testing starts](20240525_225432.jpg)

# Electronics

![wiring](20240626_202123.jpg)

The boat requires a very large amount of power to drive its functions. Each jet is equipped with a 5684 1340kv motor connected to a 6S 150A esc. Each lateral thruster is connectd to a 6S 45A esc. To accomodate this load, We used two 6S 10,000mah lipos with power routing through a custom pcb designed by a friend. 

![jet esc](20240607_003104.jpg)
![pcb](Screenshot2024-07-12231917.png)

# Controls

To allow for position holding and autonomous driving, the craft is controlled via a Speedybee f405 Wing flight controller running ArduBoat firmware. To communicate with the boat, the driver uses a ELRS transmitter talking to an Radiomaster RP3 receiver. The boat also has a Holybro SIK 915mhz telemetry radio for uploading new waypoints.

# Testing

This is a test of the boat's thrust reversing capabilities.

{{<youtube T_ZY0gY3XMs>}}

This is a test of the boat's speed and turning capabilities. I only had one lateral thruster wired up at the time.

{{<youtube IFQc7KV5nmg>}}

# Hull Revision

![cad overview](image_2.png)

The construction and testing of this prototype hull taught me much about overlooked design considerations while also providing an opportunity to test more construction techniques. Here are some of the problems encountered and their solutions:

| Problem | Solution |
| --- | --- |
| The jet compartment developed a slow leak around the silicone sealant. | The motor mount was redesigned placing the entire jet assembly in a detatchable pod thus eliminating the large jet intake hole from the hull compartment. This also allows for the hot swapping of motor modules. |
| ABS shrinks as it cools and as a result, the acrylic lids have a poor fit to the hull which caused water to enter from the top | The new lid would also be 3D printed and use a diagonal gasket system and significantly more screws to compress a gasket layer and prevent water from entering |
| The boat while large for an RC boat, handles poorly in choppy water due to it heaving significantly as it crests waves | The new hull is nearly double the length of the original and features a wave piercing bow to go through the waves |
| The lift hooks are located in an awkward position and and because the hardpoint spans two compartments, limits the boat's ability to be disassembled | The new hardpoint is moved to an independent module between two compartments with the lifting eyelet located significantly higher than the top of the hull lid. |
| Being a piece of laser cut aluminum, the trusses were not rigid enough so when the hulls rode over waves, the trusses flexed by a significant amount. | The new trusses are made from 8040 aluminum extrusion secured to quarter inch aluminum sheets on the hardpoint modules. |
| Despite having large internal volume, each compartment is less than 250 mm long thus limiting the size of internally stored cargo | The new design has compartments over 700mm long. This is achieved by acetone welding three 240mm sections together. Due to each section not having a bulkhead on each side, they can be printed vertically, thus almost entirely eliminating the need for supports. |
| When using thrust reversing, the jets sprayed significant amounts of water over the hull which causes water intake into the jet compartment. | A fantail was added to the hulls to deflect the spray. In addition, the new craft is designed for the jets to be fully submerged which should also reduce spray |
| There is no way for internally stored components to be secured to the hull compartments | All new compartment sections have extensive numbers of heat insert so that custom acrylic or metal mounting panels can be installed |

{{< figure src="Screenshot_2024-06-26_203359.png" title="hull side view">}}
{{< figure src="image_4.png" title="hull cross section showing hardpoints, keel tube, and lid gasket system">}}
{{< figure src="Screenshot2024-07-12235511.png" title="new hardpoint and lift hook attach point">}}
{{< figure src="Screenshot2024-07-12235610.png" title="extensive use of heat inserts and bulkhead wire channels">}}
{{< figure src="Screenshot2024-07-12235651.png" title="motor pod mounts">}}

# Conclusion

This is still an ongoing project so there is no conclusion. However, like all projects, it taught me new skills such as ABS printing and waterproofing. I look forward to seeing if this craft gets used in the future.






