---
title: "Design and build"
date: "2025-02-21T03:24:40Z"
---

# In Game Reference

{{< figure src="researchimg.png" title="research images" >}}

The first step was finding reference material as well as researching the lore to determine the capabilities and functions of the cannon. This resulted in me digging up all sorts of in game images and extracting game files to see what needs to get implemented. The game is notorious for artistic inconsistencies so I was forced to compromise on certain aspects to maintain the aesthetic integrity while still making it feasible to manufacture. 

# Hardware Design

## Shell

{{< figure src="shelltitle.png" title="shell exterior" >}}

The first step is to create an accurate 1:1 exterior copy of the cannon. First, accurate exterior dimensions needed to be established. This was done by referencing the in game height description of the character, then pixel counting to determine the length of the box. From there, width and depth can be extrapolated. This was used to create a rectangle matching the exterior dimensions of the box. From there, flat images of each side of the box were applied to the surface of the box so surface details could be drawn and carved. Finally, the box was hollowed out in preparation for the interior.

{{< figure src="foldedside.png" title="folded side view" >}}
{{< figure src="foldedsideup.png" title="folded side/top view" >}}
{{< figure src="foldedfront.png" title="folded front view" >}}
{{< figure src="deployedside.png" title="deployed side view" >}}

## Frame

{{< figure src="extrusionframe.png" title="main body extrusion frame" >}}

Ihe entire cannon is over 4 ft long and must be rigid in order for the mechanisms to function properly. I selected 2020 aluminum extrusion for it's ease of access and wide parts compatibility. The main body uses 2020 extrusion segments along with 90 degree brackets. For cases where brackets would interfere with other mechanisms, low profile laser cut brackets would be used instead.

{{< figure src="extrusionside.png" title="main body extrusion frame side" >}}
{{< figure src="extrusionback.png" title="main body extrusion frame back" >}}

## Barrel

{{< figure src="barrel.png" title="barrel" >}}

The barrel is the largest moving mechanism on the cannon. It's a two stage actuation requiring the lower portion to slide forward then drop down. I implemented the slide portion with a linear actuator attached to a carriage riding on a length of extrusion on the lower barrel. The drop down is handled by another linear actuator. A parallelogram linkage ensures the lower and upper portions are always parallel. The main difficulty was the tight space constraints. I had to reserve space for the large exhaust cone and gas tube's bend radius without compromising the linkage's strength.

{{< figure src="barrelfolded.png" title="barrel folded" >}}
{{< figure src="barrelhalfextend.png" title="barrel slide forward" >}}
{{< figure src="barrelfullextend.png" title="barrel drop down" >}}
{{< figure src="barrelgastube.png" title="gas tube stow position" >}}
{{< figure src="barrelnocore.png" title="side view slice" >}}
{{< figure src="barrelfrontcross.png" title="barrel front crosssection with cavities for fasteners" >}}

## Trigger

{{< figure src="triggertitle.png" title="folding grip and slide assembly" >}}

Probably one of the most annoying mechanisms would be the grip assembly. The main issue is that not only does the grip have to extend, the entire block the grip is mounted must also be capable of sliding. The lore reason escapes me and while it looks pretty cool, implementing this was a struggle.

### Folding Grip

{{< figure src="triggerlink.png" title="trigger linkage" >}}

The grip contains two folding components: the grip, and a recoil brace behind it. I reference many real world rocket/missile launcher designs to get an acceptablly ergonomic shape. The two components are actuated via a single linear actuator connected to a load transfer plate. This plate synchronizes the grip and recoil spade's movement such that over the length of the actuator's travel, the grip rotates 90 degrees while simultaneously rotating the recoil spade 35 degrees. 

{{< figure src="triggerfolded.png" title="trigger folded" >}}
{{< figure src="triggerdeployed.png" title="trigger deployed" >}}

### Moving Trigger Block

{{< figure src="triggerassembly.png" title="trigger block assembly" >}}

However, as the entire trigger block must slide back and fourth, I had to contain the rotation mechanism such that it could be mounted to linear rails. As the entire weight of the cannon would be resting on this moving trigger block, two linear rails were used. It is also why every actuatior is doubled up and rated for 120Nm of torque.

{{< figure src="triggerblockback.png" title="trigger block back stop" >}}
{{< figure src="triggerblockfront.png" title="trigger block front stop " >}}
{{< figure src="triggerlinkage.png" title="folding assembly/double linear actuators " >}}

## Light Covers

{{< figure src="covertitle.png" title="light covers" >}}

The two remaining mechanisms are responsible for raising several panels on the cannon revealing glowing green lights. At this point, space is a premium as gas and electrical lines still need to be routed. Thus, I had to get more creative with how to save space.

### Triangle

{{< figure src="trianglelinkage.png" title="triangle linkage" >}}

The first and simpler of the two is a triangle located towards the front of the box. This only needs to raise vertically by 15mm. The best place to mount the actuator would be between the upper extrusion frames. I designed a simple 90 degree linear joint to translate horizontal linear motion to vertical linear motion.

{{< figure src="trianglelowered.png" title="triangle lowered" >}}
{{< figure src="triangleRaised.png" title="triangle raised" >}}


### Triple Covers

{{< figure src="coversiderear.png" title="triple cover assembly" >}}

The second mechanism involves raising three panels simultaneously in the horizontal and vertical direction. In order to reduce space and construction cost, I planned to use only one actuator for the entire motion. In order to achieve two directions of movement, I attached the vertical motion assembly onto a horizontally traversing carriage. Then I designed a slot with a 90 degree bend that the vertical assembly slots into. As the linear actuator pulls the carriage along, the vertical assembly moves with it until it reaches the bend where it then begins raising.

{{< figure src="coverlowered.png" title="covers lowered" >}}
{{< figure src="coverraised.png" title="covers raised" >}}
{{< figure src="coversidetop.png" title="The entire assembly is narrow enoug to fit between the extrusion rails" >}}

### LED Diffusers

There are numerous light on the model which need to be made functional. For maximum flexibility, I will be using individually addressable led strips. The primary difficulty is that when not lit, the panel must be completely black, blending in with the surrounding black panels. This necessitates the use of a black diffuser. These are pretty rare but I was able to find a supplier. Each light window will sit flush with the body with a light strip behind it. When on, there should be a crisp, neon light and when off, there should be no trace of the light panel hidden in the larger black panel. Testing will be required.

## Gas System

{{< figure src="gastitle.png" title="gas system" >}}

In order to create a realistic firing effect, it was planned for a propane plasma cannon to be installed inside the frame. When the trigger is pulled, a solenoid opens which allows gas to vent through a tube where it collects inside the emitter located in the deployed barrel. After a delay, this gas is electroncially sparked causing a flame to travel from the gas cylinder down the length of the tube. Once this flame reaches the emitter, the increased gas volume combine with the open air creates a large bang as well as a fireball. In order to shield plastic components from heat, all surfaces in the path of the fireball are covered in either sheet metal or heat reflective tape. The gas cylinder is easily replaceable via a quick eject system.

{{< figure src="gaspipeline.png" title="gas pipeline" >}}
{{< figure src="gasrouting.png" title="gas routing" >}}
{{< figure src="gascylinderfolded.png" title="gas cylinder mounted" >}}
{{< figure src="gascylindereject.png" title="gas cylinder ejected" >}}
{{< figure src="m4firing.png" title="cannon firing animation" >}}

# Electrical Design - CURRENTLY WORKING ON

## Sensors

In order for all actuators and special effects to operate correctly and safely, numerous sensors are mounted throughout the frame to monitor the position of each actuator, temperature, voltage, current, etc. 

For all linear actuators, each end of travel contains hall effect sensor. When the joint approaches an endstop, a permanent magnet located on the moving assembly will be detected by this endstop which raises the proper flag. As a last resort, there are also mechanical endstops but will result in the actuator stalling.

The most potentially dangerous system is the gas line. In order to prevent overheating as well as accidental gas release, the solenoid and electronic trigger both have physical disconnect switches. The solenoid in particular has a separate endstop switch that checks for potential jams in the open position. There are also temperature sensors running the length of the gas tube to monitor temperature. The gas system works with the actuator sensors to prevent activating the gas system when the barrel is not fully deployed. If any safety flags are tripped, the gas system shuts down and an error flag is sent to the central control system.

## Control Electronics

One of the things I hoped to get out of this project was more STM32 pcb design experience. The PCB for this cannon needs to perform the following functions"
- actuate all actuators through proper sequence
- trigger firing sequence
- cycle light and sound effects
- detect system faults
- display information on disgnostic panel

# Fabrication

## Frame Fabrication

## 3D Printing

## Metal Working

## Actuator Installation

## PCB Fabrication

## Final Assembly

# Programming

The software's primary function is sequencing the actuation of different components in order to mirror in game motions. This includes linear actuators, lights, sound, gas sparking, etc. Additionally, it must detect faults with the system, trigger failsafes, and report them to the user. This is implemented with a combination of endstop hall effect sensors, current sensing software software timeouts.

# Testing

# Conclusion
