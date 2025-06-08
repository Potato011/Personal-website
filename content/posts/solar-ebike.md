---
title: "Solar Ebike"
categories: ["Bike", "Bikepacking", "Vehicle", "Electrical", "Arduino", "CAD"]
date: "2023-06-27T03:24:40Z"
draft: false
cover:
  image: "posts/solar-ebike/20230924_101226.jpg"
  alt: "solarbike cover"
  hidden: false
  hiddenInList: false
  hiddenInSingle: false
  relative: true
---

350 watts of light weight solar panels on a custom frame fixed to a trailer providing a significant boost to ebike range and allowing remote drone flying

## Table of Contents
- [Overview](#overview)
- [Shortcomings](#shortcomings)
- [Initial Specifications](#initial-specifications)
- [Electrical Plan](#electrical-plan)
  - [Simplified Electrical Layout](#simplified-electrical-layout)
  - [Detailed Electrical Layout](#detailed-electrical-layout)
- [Hardware Plan](#hardware-plan)
  - [Hub Motor Modifications](#hub-motor-modifications)
  - [Suspension Fork](#suspension-fork)
- [Electrical Execution](#electrical-execution)
  - [Electrical Enclosure Test Fit](#electrical-enclosure-test-fit)
  - [Electrical Enclosure CAD Models](#electrical-enclosure-cad-models)
  - [Electrical Enclosure Complted](#electrical-enclosure-completed)
  - [Electrical Wiring](#electrical-wiring)
- [Hardware Execution](#hardware-execution)
  - [Hub Motor Installation](#hub-motor-installation)
  - [Suspension Fork Installation](#suspension-fork-installation)
- [Finished Build](#finished-build)
- [Solar Panels](#solar-panels)
  - [Trailer](#trailer)
  - [Circuitry](#circuitry)
- [Testing](#testing)
- [Conclusion](#conclusion)

# Overview
This vehicle is a continuation of my E-Cargo bike project and represents a major overhaul of the bike's electrical system in addition to hardware modifications to accomodate solar panels. With the completion of this project, the bike progresses from an minimum viable product to a robust, field tested system ready for long offgrid excursions.

# Shortcomings
The current bike, while containing the bare minimum equipment required to transport cargo offroad, lacks many reliability features necessary for sustaining prolonged offroad travel.

Major problems were identified in several areas:
- Electrical
  - lack of weatherproofing on major electrical components
  - lack of quick accessibility to certain components inside frame 
  - lack of modularity/upgradability for solar circuitry due to soldered Y-splitter cables
  - not all components fused
  - unclear wiring (rat's nest)
  - insufficient safety indicator lights

- Mechanical
  - excessive braking required to slow vehicle on long descents
  - rigid frame cause uncomfortable ride offroad

**Summary:** Most shortcomings relate to weatherproofing of electronics as well as cleaning up the general layout with a cleaner, more futureproof electrical layout. Additionally, braking and ride comfort are also areas that need addressing

# Initial Specifications
The following requirements were created to address these shortcomings:
- Electrical
  - waterproof enclosures for all electrical components
  - modular node based electrical junction PCBs with spare ports
  - fuses on all power ports
  - extra ports for adaptability
  - indicator lights + control unit with cockpit dashboard

- Mechanical
  - regenerative braking via hub motor
  - suspension fork

# Electrical Plan

## Simplified Electrical Layout

![Simplified Electrical Diagram](simplified_diagram.png)

The electical components can be divided into three primary nodes, forward, middle, and rear. Each node contains its own fused power distribution board (PDB), and is responsible for distributing power from the primary high/low voltage bus bars located in the middle node to their connected components. Furthermore, each node contains its own processor to parse data sent by the central control circuit located in the middle node. This system allows for the reporting of faults as well as software modifications in the event of upgrades.

## Detailed Electrical layout

![Detailed Electrical Diagram](detailed_diagram.png)

The power pathway starts from the battery where it is sent into the high voltage bus box. This power is goes to the middrive motor controller, hub motor controller, and a 60v to 12v step down located in the low voltage buxs box. This stepped down power is sent to various 12v appliances such as the android auto dahsboard as well as the lighting relay PCB. Relays are controlled by an onboard arduino controlled by switches located in the cockpit. Data is transmitted throughout the bike via dedicated data lines carrying information from the cockpit to the forward, mid, and read nodes as well as vehicle status information back from these nodes.

# Hardware Plan

## Hub Motor Modifications

![Hub Motor Install](hub_install.jpg)

**Rational:** The addition of a hub motor in addition to the middrive motor is rather radical modification only seen on a handful of ebikes anywhere. For the purposes of travelling offroad, a middrive motor is preferable due to it's ability to transmit power through the bike's chain and deraileur thus achieving higher torque for hill climbing in lower gear. A hub motor by comparison consumes far more power to achive the same performance. However, in the case of extended offroad touring, this setup offers several unique advantages.

**Emergency Backup:** While not normally an issue, a breakdown of the middrive motor would be catastrophic as it potentially leaves the rider stranded with a vehicle too heavy to pedal without assistance. Hub motors by natures are very robust, low maintanence pieces of equipment that do not interface with the rest of the bike's drivetrain. An additional motor can allow the rider to limp into the nearest service stop unaided.

**Regenerative Braking:** The far more utilized feature is definitely regenerative braking. Hub motors are able to capture rotational energy from the wheel thus slowing down the bike and converting that energy into electrical power for the battery. This feature in addition to the hydraulic brakes increase overall braking force and prolongs brake pad life when only using regen braking.

**Motor Selection:** The GMAC 10T geared hub motor was selected for its reputability along with light weight construction compared to direct drive hub motors. Geared hub motors usually do not have regen capabilities due to a clutch stopping the motor from spinning when coasting. The GMAC is unique in that it has a locked clutch that keeps the motor spinning when coasting.

![GMAC](gmac10t.jpg)

## Suspension Fork

To improve ride comfort, a suspension for was also added.
![Suspension Fork](fork.jpg)

# Electrical Execution

## Electrical Enclosure Test Fit

{{< figure src="cardboard1.jpg" title="Cardboard test fit" >}}
{{< figure src="cardboard3.jpg" title="Cardboard High/Low voltage box" >}}
{{< figure src="cardboard4.jpg" title="High voltage box strap points" >}}

## Electrical Enclosure CAD Models

{{< figure src="cadoverview.png" title="Enclosure Overview" >}}
{{< figure src="cad3.png" title="High Voltage Bus Box" >}}
{{< figure src="cad2.png" title="Low Voltage Bus Box top view" >}}
{{< figure src="cad1.png" title="Low Voltage Bus Box bottom view" >}}
{{< figure src="cad4.png" title="VESC Motor Controller Box" >}}

## Electrical Enclosure Completed

{{< figure src="panels.png" title="High/Low voltage boxes" >}}
{{< figure src="vescbox.jpg" title="VESC Motor Controller Box" >}}

## Electrical Wiring

{{< figure src="wiring.jpg" title="Wiring installation" >}}
{{< figure src="testwiring.jpg" title="Test routing of waterproof bulkheads" >}}

# Hardware Execution

## Hub Motor Installation

{{< figure src="hub1.jpg" title="Hub motor installation" >}}

## Suspension Fork Installation

{{< figure src="fork.jpg" title="Suspension fork installation" >}}

# Finished Build

![bike build](finished.jpg)

The finished build is significantly cleaner than before with all wires hidden inside either enclosures or under cable sleeves. With these modifications, the bike should be able to operate in heavy rain and ford water up to the bottom bracket. Maintanence has also been greatly simplified easy to access side panels.

# Solar Panels

In order to provide enough power for the bike and camp equipment, 350W of solar panels were mounted to a Burley Coho single wheel trailer. These panels are lightweight and flexible thus requiring the fabrication of custom lightweight aluminum frames. As the panels are stacked on top of each other during motion, only one can be used when riding. 

## Trailer

{{< figure src="trailer.jpg" title="Solar trailer" >}}

## Circuitry

Power from the panels are fed through an Elejoy maximum power point tracking (MPPT) solar charge controller which boosts the voltage required by the main battery. Each panel supplies power at roughly 20 volts thus with both panels in series the step up to battery voltage is minimized. This system is able to be wired in parallel with the main battery and motor due to the battery's common port battery management system (BMS).

{{< figure src="mppt.jpg" title="MPPT solar charge controller" >}}

# Testing

Testing was conducted on several trip culminating with an offroad overnight trip at Mission Trails regional park. The bike was able to haul the trailer along with camping gear through a variety of terrain including singletrack mountain bike trails. A power meter onboard logged the amount of solar and regen energy collected. Overall, independently testing the regen motor shows an average 15% increase in range. The solar trailer decreases range by approximately 20% but is able to fully charge the battery from empty in approximately four hours.

{{< figure src="side_view.jpg" title="Testing in downtown San Diego" >}}
{{< figure src="panels_deployed.jpg" title="Testing in downtown San Diego 2" >}}
{{< figure src="offroad1.jpg" title="Testing at Mission Trails" >}}
{{< figure src="offroad2.jpg" title="Testing at Mission Trails 2" >}}

{{<youtube lTySmGHRum0>}}

# Conclusion
Overall, I was able to achieve what I set out to do. The solar panels succeeded in decreasing my dependence on grid charging and has proven itself capable of handling the harsh offroad terrain. The bike itself has also proven itself to be a reliable vehicle with over 1000 miles logged after this upgrade. This was a great learning experience in designing a distributed system for transfering power and data throughout a vehicle. I have several future upgrades in mind but that's for next time.

{{< figure src="catalina.jpg" title="100+ mile trip on Catalina Island" >}}