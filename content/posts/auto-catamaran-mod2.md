---
title: "Autonomous Catamaran MOD 2"
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

# Overview
A production model of the ongoing catamaran USV project. This hull emphasizes portability and waterproofness, implementing many features from previous design along with several new design elements. This craft is designed to be the most reliable and versatile craft, being easily transportable, having large payload capacity, long mission endurance.

# Design Considerations
To be more transportable, the length has been reduced to 5 ft and the width reduced to 4 ft allowing it to fit in elevators. To simplify construction and reduce weight, the number of compartments has been reduced to 3 independently watertight compartments. In previous variants, there was a risk for water to enter through the jet drive assembly. To mitigate this, the entire drive assembly is contained in a separate compartment with no drive linkages between it and the main compartments. For
more efficiency and to conform to existing ardupilot frames, The jet drive was replaced with reversible ducted propellers on vectored mounts. These rear props can rotate in a 180 degree arc and when combine with the bow thrusters, achieves omnidirectional motion without the need for stern thrusters.

# Gallery
{{< figure src="flat.png" title="side view with flat acrylic lid" >}}
{{< figure src="bottom.png" title="bottom view" >}}
{{< figure src="side.png" title="side view" >}}
{{< figure src="rear.png" title="rear view" >}}
{{< figure src="crosssection.png" title="cross-section view" >}}
{{< figure src="lift.png" title="lift hardpoints use pvc pipes. also shows 20x20 extrusion keel tube" >}}
{{< figure src="compare.png" title="comparing past USV models" >}}
{{< figure src="comparetop.png" title="comparing past USV top view" >}}

# Construction
The hull was constructed with a large emphasis on acetone welding. many components were optimized for welding which reduced the number of bulkheads and thus the total hull weight.
{{< figure src="build3.jpg" title="hull components being laid out for welding" >}}
{{< figure src="build2.jpg" title="center hull components being welded" >}}
{{< figure src="Boat_Diagram.png" title="circuit diagram" >}}
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

# Conclusion
The craft has proved to be a highly maneuverable platform with good payload capacity. More tests will be needed but it seems promising. 
