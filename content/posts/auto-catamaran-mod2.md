---
title: "Autonomous Catamaran MOD 2"
categories: ["Drone", "Boat", "RC", "CAD"]
date: "2024-11-04T03:24:40Z"
draft: false
cover:
  image: "posts/auto-catamaran-mod2/dome.png"
  alt: "cat mod 2 cover"
  hidden: false
  hiddenInList: false
  hiddenInSingle: false
  relative: true
---

# Table of Contents
- [Overview](#overview)
- [Design Considerations](#design-considerations)
  - [Operational](#operational)
  - [Manufacturing](#manufacturing)
- [Conceptual Design & Studies](#conceptual-design--studies)
  - [Hull Design](#hull-design)
  - [Acetone Welding/Assembly](#acetone-weldingassembly)
  - [Seakeeping](#seakeeping)
  - [Propulsion](#propulsion)
  - [Navigation](#navigation)
  - [Electrical Layout](#electrical-layout)
- [Gallery](#gallery)
- [Construction](#construction)
- [Testing](#testing)
- [Results/Analysis](#resultsanalysis)
- [Improvements](#improvements)
- [Conclusion](#conclusion)

# Overview
A production model of the ongoing catamaran USV project. This hull emphasizes portability and waterproofness, implementing many features from previous design along with several new design elements. This craft is designed to be the most reliable and versatile craft, being easily transportable, having large payload capacity, long mission endurance.

A draft of the paper can be found here: [Exploring Low-Cost 3D Printable USVs for the purpose of Shallow Water Inspections](https://github.com/Potato011/boatpaper/blob/main/boatpaper.pdf)

This article a recounting of the process in my own words along with some tangents.

**Role:** As the project lead, I was responsible for the complete hardware design and fabrication, electrical system architecture, and autopilot implementation. I also collaborated with other team members to organize pool tests and ready the paper for publication.

# Design Considerations

In order to be easily manufacturable at low cost as well as effective during operation, requirements for the craft were split into two categories, "Manufacturing" and "Operational"

## Operational
- unobstructed view of water directly below equipment deck
- able to continue operation after hull breech
- 60 lbs cargo capacity
- capable of withstanding temporary full immersion
- capable autonomous "lawnmower" path missions
- GPS waypoint navigation accuracy within 50cm
- capable of omnidirectional movement
- transportable in standard 4x5 ft elevator
- 24hr mission endurance

## Manufacturing
- majority 3D printed components on standard 250x250mm bed
- minimize use of specialty parts/tools
- modular extrusion based deck equipment mounts
- standardized fastener/hardware usage
- parts optimized for intuitive construction

# Conceptual Design & Studies

An extensive design study was conducted in order to determine the optimal approach to achieve all design goals. As design decisions take both operational and manufacturing into account, this section will not be split but instead be divided into the major decisions.

## Hull Design
{{< figure src="domelid.png" title="side view with dome  lid" >}}
{{< figure src="flat.png" title="side view with flat acrylic lid" >}}
{{< figure src="bottom.png" title="bottom view" >}}
A catamaran hull was selected as its bridgedeck construction allows for downward facing cameras to have an unobstructed view of the water. The twin hull design also creates more compartmentalization thus increasing survivability in the event of a hull breech. Additionally, two hulls allows for smaller individual hull components without sacrificing payload capacity. This is important for increasing manufacturability on the limited print bed volumes of commercial 3D printers. 4080 extrusion was selected to serve as the bridgedeck. This increases stiffness of the hull while also providing modular mounting points for equipment Size was limited to a length of five feet and width of four feet in order to fit in elevators.

## Acetone Welding/Assembly
{{< figure src="weldjoint.jpg" title="acetone welded joint between hull segments" >}}
{{< figure src="weldsurface.jpg" title="acetone brushed skin" >}}
In order to reduce complexity, hull construction heavily relied on the use of acetone welding. Acetone welding is a technique where an ABS plastic part is brushed with acetone and pressed to another ABS part. The acetone temporarily dissolves the surface of the part causing it to fuse with the second parts. Once the acetone dries, the bond is nearly as strong as the rest of the part. This technique minimizes the need for specialized tools and hardware while only using hardware grade parts. Acetone welding is used to join major hull segments as well as acetone brushing over surfaces to fuse layer lines. To align hull segments as well as provide structural support, each hull contains a 20x20 aluminum extrusion beam running the length of the hull where the keel is usually located. For non weldable areas, metric hardware is used along with heat set inserts. To minimize galvanic corrosion, all metallic parts are stainless steel or similar metals with <0.25V.

## Seakeeping
{{< figure src="crosssection.png" title="cross-section view" >}}
To handle rough wave conditions, special care was taken to design the hull shape as well as waterproofing features. Given the craft's small size, riding over waves would create an unneccesaily violent pitching motion. Thus, an axe bow was determined to be the optimal bow shape. These bows cut through waves rather than ride over them, thus creating a smoother ride. However, this means the craft will be temporarily fully immersed which requires extensive waterproofing on all hatches and covers. This waterproofing came in the form of a dome lid secured using a series of screws compressing a layer of gasket liner. A simplified control panel consisting of waterproof switches is located at the aft of each hull under a splash resistant cover. Primary communication would be done wirelessly to reduce the number of ports exposed.

## Propulsion
{{< figure src="vector1.jpg" title="Vectored stern thrusters" >}}
{{< figure src="vectorshaft.png" title="vector shaft tube with rotary grease seal" >}}
Previous tests using jet powered boats revealed that while power dense, these systems lack the responsiveness required for accurate survey work. Their reverse buckets were incompatible with the Ardupilot firmware planned to autonomously navigate the craft. As a result, a traditional stern mounted ducted propeller was selected. However, to increase maneuverability, these thrusters would not only be reversible but also be capable of differential vectored thrust up to 50 degrees on each side. Furthermore, these stern thrusters would be aided by two bow thrusters granting the boat omnidirectional movement and rapid course adjustment in complex environments. To power this sytem, two large 48v Li-ion batteries located in each hull through a custom redundant power distribution system.

## Navigation
{{< figure src="rtk.jpg" title="Vectored stern thrusters" >}}
Ardupilot, specifically Ardurover, was selected as it is the most robust autopilot software available. This software was installed into a Matek H7 based flight controller located in the left hull. For precise maneuvering, an RTK GPS receiver was installed on the craft's bridgedeck along with a telemetry radio system for receiving correction data. This radio system is also responsible for supplying the mission coordinates from the base station.

# Electrical Layout
{{< figure src="Boat_Diagram.png" title="circuit diagram" >}}
{{< figure src="pdb.png" title="PDB prototype" >}}
{{< figure src="gland.png" title="waterproof cable gland ports" >}}
To improve survivability in the event of a hull breach, each hull is designed for independent operation should the other be compromised. Both hulls contain its own battery capable of supplying enough power to the entire craft should one battery fail. This power is routed between hulls through a custom power distribution board (PDB) that supports bidirectional power transfer and emergency cutoff should a leak be detected. The PDB also minimizes the amount of wiring required between hulls as only a few data cables need to be passed between the hull in addition to the main power cables. The autopilot is enclosed in a self contained enclosure in the left hull but should that fail, the right hull is capable of manual maneuvering via radio.

# Gallery
{{< figure src="side.png" title="side view" >}}
{{< figure src="rear.png" title="rear view" >}}
{{< figure src="lift.png" title="lift hardpoints use pvc pipes. also shows 20x20 extrusion keel tube" >}}
{{< figure src="compare.png" title="comparing past USV models" >}}
{{< figure src="comparetop.png" title="comparing past USV top view" >}}

# Construction
The hull was constructed with a large emphasis on acetone welding. many components were optimized for welding which reduced the number of bulkheads and thus the total hull weight.
{{< figure src="build3.jpg" title="hull components being laid out for welding" >}}
{{< figure src="build2.jpg" title="center hull components being welded" >}}
{{< figure src="build1.jpg" title="final assembly with electronics" >}}
{{< figure src="prepaint.jpg" title="hull prepped for painting" >}}
{{< figure src="painted.jpg" title="hull painted" >}}

# Testing
Several tests were conducted to ensure the craft's structural integrity as well as evaluate it's general performance. These started with manual controls and progressed to autonomous tests. As of now, more tuning is required in order to dial in the PID of it's differential vectored thrusters. Note, some tests occured before painting in order to evaluate if acetone alone was enough to waterproof the hull.

{{< figure src="test1_1.jpg" title="first float test" >}}
{{< figure src="test1_2.jpg" title="driving" >}}
{{< figure src="driving1.jpg" title="post painting" >}}
{{< figure src="pool1.jpg" title="driving more" >}}
{{< figure src="path1.png" title="autonomous driving data logs" >}}

Here are some videos from various tests

This is from the first test of the boat. At the time, there was no vectoring. Turning was a combination of differential thrust of the stern thruster and the bow thrusters.
{{<youtube aPDv0t_JM70>}}

This is from the second test. Vectoring is also not enabled.
{{<youtube 51xJqgGFbpM>}}

This is an autonomous path. Differential and vectoring are both enabled.
{{<youtube l47Zi1vy46s>}}

# Results/Analysis
Results are promising. The hull is capable of withstanding the stresses expected during ocean operation. The maneuvering system also performed adequately although larger thrusters are required for faster straight line traversal. Navigation, after sufficient tuning of PID, was also to achieve a satisfactory lawnmower with desired path overlap for complete camera coverage.

# Improvements
Primary goals for next iteration:
- add interlocking design into hull segments
- increase vector angle
- increase stern thruster size
- switch from screw lid to locking latch lid
- skidplates on underside of hull
- custom batteries with mount
- navigation lights
- waterproof ports for powering external equipment
- improved PDB with power logging functionality

# Conclusion
The craft has proved to be a highly maneuverable platform with good payload capacity. This products represents the cumulation of three prototypes and countless tests. I started research approximately eight months ago and in that time, I learned quite a bit about problem solving and polishing a product for production. My hopes is to take what was learned with this model and create an even more refined product sometime down the line (maybe with hydrofoils). 
