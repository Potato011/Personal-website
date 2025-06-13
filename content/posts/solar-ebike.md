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
- [Hardware Plan](#hardware-plan)
  - [Electrical Enclosure Test Fit](#electrical-enclosure-test-fit)
  - [Electrical Enclosure CAD Models](#electrical-enclosure-cad-models)
  - [Electrical Enclosure Complted](#electrical-enclosure-completed)
  - [Hub Motor Modifications](#hub-motor-modifications)
  - [Suspension Fork](#suspension-fork)
- [Electrical Plan](#electrical-plan)
  - [Simplified Electrical Layout](#simplified-electrical-layout)
  - [Detailed Electrical Layout](#detailed-electrical-layout)
  - [Fault Detection](#fault-detection)
  - [Electrical Wiring](#electrical-wiring)
- [Finished Build](#finished-build)
- [Solar Panels](#solar-panels)
  - [Trailer](#trailer)
  - [Circuitry](#circuitry)
- [Testing](#testing)
  - [Regen Braking Test Method](#regen-braking-test-method)
  - [Solar Trailer Test Method](#solar-trailer-test-method)
  - [Testing Conclusion](#testing-conclusion)
- [Conclusion](#conclusion)
- [Gallery](#gallery)

# Overview
This vehicle is a continuation of my E-Cargo bike project and represents a major overhaul of the bike's electrical system in addition to hardware modifications to accomodate solar panels. With the completion of this project, the bike progresses from an minimum viable product to a robust, field tested system ready for long offgrid excursions.

![Complete Feature Diagram](bike_features.png)

# Shortcomings
{{< figure src="before.jpg" title="Bike before major overhaul" >}}
{{< figure src="beforeElectricals.jpg" title="Exposed power distribution electronics" >}}

The current bike, while containing the bare minimum equipment required to transport cargo offroad, lacks many reliability features necessary for sustaining prolonged offroad travel.

Major problems were identified in several areas:
- Mechanical
  - lack of weatherproofing on major electrical components
  - lack of quick accessibility to certain components inside frame 
  - excessive braking required to slow vehicle on long descents
  - rigid frame cause uncomfortable ride offroad

- Electrical
  - lack of modularity/upgradability for solar circuitry due to soldered Y-splitter cables
  - not all components fused
  - unclear wiring (rat's nest)
  - insufficient safety indicator lights

**Summary:** Most shortcomings relate to weatherproofing of electronics as well as cleaning up the general layout with a cleaner, more futureproof electrical layout. Additionally, braking and ride comfort are also areas that need addressing

# Initial Specifications
The following requirements were created to address these shortcomings:

- Mechanical
  - waterproof enclosures for all electrical components with quick access panels
  - regenerative braking via hub motor
  - suspension fork
  
- Electrical
  - modular node based electrical junction PCBs with spare ports
  - fuses on all power ports
  - extra ports for adaptability
  - indicator lights + control unit with cockpit dashboard

# Hardware Plan

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
{{< figure src="testFit.jpg" title="Test fit of electrical enclosure" >}}

## Electrical Enclosure Completed

{{< figure src="panels.png" title="High/Low voltage boxes" >}}
{{< figure src="vescbox.jpg" title="VESC Motor Controller Box" >}}

## Hub Motor Modifications

{{< figure src="hub1.jpg" title="Hub motor installation" >}}
![Hub Motor Install](hub_install.jpg)

**Rational:** The addition of a hub motor in addition to the middrive motor is rather radical modification only seen on a handful of ebikes anywhere. For the purposes of travelling offroad, a middrive motor is preferable due to it's ability to transmit power through the bike's chain and deraileur thus achieving higher torque for hill climbing in lower gear. A hub motor by comparison consumes far more power to achive the same performance. However, in the case of extended offroad touring, this setup offers several unique advantages.

**Emergency Backup:** While not normally an issue, a breakdown of the middrive motor would be catastrophic as it potentially leaves the rider stranded with a vehicle too heavy to pedal without assistance. Hub motors by natures are very robust, low maintanence pieces of equipment that do not interface with the rest of the bike's drivetrain. An additional motor can allow the rider to limp into the nearest service stop unaided.

**Regenerative Braking:** The far more utilized feature is definitely regenerative braking. Hub motors are able to capture rotational energy from the wheel thus slowing down the bike and converting that energy into electrical power for the battery. This feature in addition to the hydraulic brakes increase overall braking force and prolongs brake pad life when only using regen braking.

**Motor Selection:** The GMAC 10T geared hub motor was selected for its reputability along with light weight construction compared to direct drive hub motors. Geared hub motors usually do not have regen capabilities due to a clutch stopping the motor from spinning when coasting. The GMAC is unique in that it has a locked clutch that keeps the motor spinning when coasting.

![GMAC](gmac10t.jpg)

## Suspension Fork

To improve ride comfort, a suspension for was also added.
![Suspension Fork](fork.jpg)

# Electrical Plan

## Simplified Electrical Layout

![Simplified Electrical Diagram](simplified_diagram.png)

The electical components can be divided into three primary nodes, forward, middle, and rear. Each node contains its own fused power distribution board (PDB), and is responsible for distributing power from the primary high/low voltage bus bars located in the middle node to their connected components. Furthermore, each node contains its own processor to parse data sent by the central control circuit located in the middle node. This system allows for the reporting of faults as well as software modifications in the event of upgrades.

## Detailed Electrical layout

![Detailed Electrical Diagram](detailed_diagram.png)

The power pathway starts from the battery where it is sent into the high voltage bus box. This power is goes to the middrive motor controller, hub motor controller, and a 60v to 12v step down located in the low voltage buxs box. This stepped down power is sent to various 12v appliances such as the android auto dahsboard as well as the lighting relay PCB. Relays are controlled by an onboard arduino controlled by switches located in the cockpit. Data is transmitted throughout the bike via dedicated data lines carrying information from the cockpit to the forward, mid, and read nodes as well as vehicle status information back from these nodes.

## Fault Detection

In order to ensure all systems are operating as intended, the overhaul introduces fused connections, fault detection, and datalogging to the bike. This system divides the bike into several nodes each containing its own microcontroller. When a fault is detected, the microcontroller logs the issue before sending it to the central node which informs the cockpit dashboard of the fault.


![Fault Detection Circuit](circuit.png)

## Electrical Wiring

{{< figure src="wiring.jpg" title="Wiring installation" >}}
{{< figure src="testwiring.jpg" title="Test routing of waterproof bulkheads" >}}

# Finished Build

![bike build](finished.jpg)

The finished build is significantly cleaner than before with all wires hidden inside either enclosures or under cable sleeves. With these modifications, the bike should be able to operate in heavy rain and ford water up to the bottom bracket. Maintanence has also been greatly simplified easy to access side panels.

# Solar Panels

In order to provide enough power for the bike and camp equipment, 350W of solar panels were mounted to a Burley Coho single wheel trailer. These panels are lightweight and flexible thus requiring the fabrication of custom lightweight aluminum frames. As the panels are stacked on top of each other during motion, only one can be used when riding. 

## Trailer

{{< figure src="trailer.jpg" title="Solar trailer" >}}
{{< figure src="hitch.jpg" title="welded trailer hitch" >}}
{{< figure src="fullLength.jpg" title="Full Length" >}}

## Circuitry

Power from the panels are fed through an Elejoy maximum power point tracking (MPPT) solar charge controller which boosts the voltage required by the main battery. Each panel supplies power at roughly 20 volts thus with both panels in series the step up to battery voltage is minimized. This system is able to be wired in parallel with the main battery and motor due to the battery's common port battery management system (BMS).

{{< figure src="mppt.jpg" title="MPPT solar charge controller" >}}

# Testing

Testing was conducted on several trip culminating with an offroad overnight trip at Mission Trails regional park. The goal of these tests were to validate the bike's ability to increase range through regen braking and solar power. Additionally, these tests test the bike's various hardware modifications to ensure reliability under harsh conditions.

## Regen Braking Test Method

The bike with no cargo will ride down a predefined path featuring various terrain and elevation changes. In order to maintain consistency between tests, the rider will not be pedaling. Instead, the middrive throttle is used to keep the bike at a consistent speed. The same 52V 17.5ah li-ion battery is used between tests. Gear changes are allowed and are kept consistent between tests. These tests were conducted three times and results averaged.

| Test Name | Test Description | Results |
|----------|----------|----------|
| Control    | The bike is ridden through the route with only conventional disk braking. |  ~25 miles on one charge. |
| Regen   | The bike is ridden through the route with priority given to regen braking. If regen braking is not enough to come to a safe stop, disk brakes are added to the braking force.   | ~28 miles on one charge. |

## Solar Trailer Test Method

The bike with trailer and no cargo will ride down a predefined path featuring various terrain and elevation changes. In order to maintain consistency between tests, the rider will not be pedaling. Instead, the middrive throttle is used to keep the bike at a consistent speed. The same 52V 17.5ah li-ion battery is used between tests. Gear changes are allowed and are kept consistent between tests. Tests are conducted on summer days with no cloud forecast and ambient air temperature over 65 degrees fahrenheit. These tests were conducted three times and results averaged.

| Test Name | Test Description | Results |
|----------|----------|----------|
| Control   | The bike is ridden through the route with only conventional disk braking. | ~25 miles on one charge.   |
| Solar    | The bike towing the solar trailer is ridden through the route with only conventional disk braking. | ~21 miles on one charge   |

## Testing Conclusion

The bike was able to haul the trailer along with camping gear through a variety of terrain including singletrack mountain bike trails. Overall, independently testing the regen motor shows an average 12% increase in range. The solar trailer decreases range by approximately 16%. It is important to note that the trailer allows for the full recharging of a battery in approximately four hours thus achieving the overall goal of independent offgrid operation.

{{< figure src="side_view.jpg" title="Testing in downtown San Diego" >}}
{{< figure src="panels_deployed.jpg" title="Testing in downtown San Diego 2" >}}
{{< figure src="offroad1.jpg" title="Testing at Mission Trails" >}}
{{< figure src="offroad2.jpg" title="Testing at Mission Trails 2" >}}

{{<youtube lTySmGHRum0>}}

# Conclusion
Overall, I was able to achieve what I set out to do. The solar panels succeeded in decreasing my dependence on grid charging and has proven itself capable of handling the harsh offroad terrain. The bike itself has also proven itself to be a reliable vehicle with over 1000 miles logged after this upgrade. This was a great learning experience in designing a distributed system for transfering power and data throughout a vehicle. I have several future upgrades in mind but that's for next time.

# Gallery

## Wacky Cargo
{{< figure src="bikeTitan.jpg" title="carrying the fuselage of a Skywalker Titan UAV" >}}
{{< figure src="bikeTV.jpg" title="hauling 2 TVs back from university surplus store" >}}
{{< figure src="bikeBoat.jpg" title="hauling 2 3D printed catamaran USV hull" >}}

## Bikepacking Trips
{{< figure src="catalina.jpg" title="100+ mile trip on Catalina Island" >}}
{{< figure src="ferry.jpg" title="bike on ferry to catalina" >}}
{{< figure src="amtrak.jpg" title="bike on amtrak to ferry" >}}
{{< figure src="terrain.jpg" title="southern mountains of Catalina" >}}
{{< figure src="terrain2.jpg" title="steep hill climbs (1.4k ft within 3 miles)" >}}
{{< figure src="parsons.jpg" title="Parson's landing - Northernmost camp on Catalina" >}}
{{< figure src="catalinaMap.png" title="Trip route and elevation map" >}}

{{< figure src="bikepack1.jpg" title="Ascending mountain to Cleveland National Forest" >}}
{{< figure src="hill.jpg" title="Ascending mountain to Cleveland National Forest" >}}
{{< figure src="cockpit.jpg" title="bike cockpit with power meter, android auto, garmin gps, and a towel for my face" >}}
{{< figure src="route80.jpg" title="riding along historical route 80" >}}
{{< figure src="camp1.jpg" title="arrived at campsite" >}}
{{< figure src="camp.jpg" title="night in the wilderness" >}}
![Stars](stars2.jpg)
![Stars](stars3.jpg)
![Stars](stars4.jpg)
![Stars](stars5.jpg)
![Stars](stars6.jpg)
![Stars](stars7.jpg)

{{< figure src="night2.jpg" title="night in the wilderness" >}}
{{< figure src="night3.jpg" title="night in the wilderness" >}}




