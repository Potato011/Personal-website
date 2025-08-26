---
title: "Sci-Fi Cannon Prop"
categories: ["Electrical", "CAD", "Art", "Cosplay", "Video Game"]
date: "2025-02-21T03:24:40Z"
draft: false
cover:
  image: "posts/m4a1-jupiter-cannon/titlepic.png"
  alt: "M4A1 Jupiter Cannon"
  hidden: false
  hiddenInList: false
  hiddenInSingle: false
  relative: true
---

A prop from a certain game that I played. This cannon of unknown origins is wielded by the main protagonist. It resembles a large suitcase but unfolds into a particle cannon. This recreation features all moving components, light, as well as a functional propane plasma cannon hidden inside.

# Table of Contents
- [Overview](#overview)
  - [Inspiration - ANIME WARNING: Skip if not interested](#inspiration---anime-warning-optional-read---skip-to-in-game-reference-if-not-interested)
    - [Story Background](#story-background)
    - [Character](#m4a1---character-in-question)
    - [In Game Reference](#in-game-reference)
- [Hardware Design](#hardware-design)
    - [Shell](#shell)
    - [Frame](#frame)
    - [Barrel](#barrel)
    - [Trigger](#trigger)
        - [Folding Grip](#folding-grip)
        - [Moving Trigger Block](#moving-trigger-block)
    - [Light Covers](#light-covers)
        - [Triange](#triangle)
        - [Triple Covers](#triple-covers)
    - [Gas System](#gas-system)
- [Electrical Design](#electrical-design---currently-working-on)
    - [Sensors](#sensors)
    - [Control Electronics](#control-electronics)
- [Fabrication](#fabrication)
    - [Frame Fabrication](#frame-fabrication)
    - [3D Printing](#3d-printing)
    - [Metal Working](#metal-working)
    - [Actuator Instalation](#actuator-installation)
    - [PCB Fabrication](#pcb-fabrication)
    - [Final Assembly](#final-assembly)
- [Programming](#programming)
- [Testing](#testing)
- [Conclusion](#conclusion)

# Overview

I've always been a fan of sci-fi designs in media, especially games. Seeing the in-game mechanisms moving was always fascinating and while they aren't always logical, the cool factor is undeniable. This project aims to bring an in-game piece of equipment to the real world. The primary focus of this project will be:
- making complex, well organized, CAD assemblies
- robust sensor network with interlocks to allow for smooth, controlled motions
- stm32 based control system for triggering motion sequences, special effects, etc

## Inspiration - ANIME WARNING (optional read - skip to "In Game Reference" if not interested)

### Story Background

{{< figure src="2018Winter4-1.png" title="Combat in a contaminated zone" >}}

Alright I ain't gonna sugarcoat this. The game this is from is a little known gacha called GFL. Despite the anime asthetics, the story is quite dark. If you're not interested in the context and just want to know about the engineering process, skip to the next section: "In Game Reference". You've been warned.

The story takes place in an future (206x) post apocalypes alternate timeline of Earth which has been ravaged by three world wars followed by a plague of alien origin. In the aftermath of all this, the remaining governments and elites of society holed themselves into the few uncontaminated regions, isolating themselves behind massive quarantine walls. The hazards of the contaminated region saw the widespread use of Private Military Contractors (PMCs) which extensively used "Tactical Dolls" (T-Dolls), essentially sentient androids who are better suited for work in irradiated areas. They are used for jobs ranging from construction to armed security and are often directed by a human operator(you) situated in forward bases. There's way too much to get into but the story is long, involving rouge AIs, government splinter factions, cultists, and a grand conspiracy. Real dark stuff. 

Despite the bleak setting, the story focuses quite heavily on individual struggle as well as the desire to defy the fate the world has laided out for the main cast. I especially like the artwork of the setting which often portrayed with few colors and abstract brush strokes. As you can probably tell, I'm in it for the story (and the robots). 

{{< figure src="2022winter_onway.png" title="A severely contaminated zone" >}}
{{< figure src="2021white_slum.png" title="Civil unrest in Berlin" >}}
{{< figure src="19winter_biggun.png" title="Shore guns of the Paldiski submarine base located in Estonia" >}}
{{< figure src="BG-Wall.png" title="Berlin quarantine wall between green and yellow zones" >}}

### M4A1 - Character in question

{{< figure src="Pic_M4A1Mod_HD.png" title="M4A1 MOD 3 default art. The cannon in question is folded and slung behind her" >}}

The lore is that PMCs aren't allowed to use weapons newer than those used during WW3, aka thing up to and including modern weapon. Due to technological imitations, T-Dolls are only capable of proficiently operating one weapons platform, thus swapping is not possible. As a result, the PMC the player is assigned to names their T-Dolls the same as the firearm they use. Thus, the T-Doll who uses the M4A1 carbine is named "M4A1". At some point, in the story, a mentor transfers the particle cannon to her which was a memento from an earlier "sister" unit who is now missing.

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

For all linear actuators, each end of travel contains a permanent magnet endstop. when the joint approaches an endstop, a hall effect sensor located on the moving assembly will detect this endstop and raise the proper flag. As a last resort, there are also mechanical endstops but will result in the actuator stalling.

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

# Testing

# Conclusion

