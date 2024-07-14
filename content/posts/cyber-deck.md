---
title: "All in One Drone Control Terminal (Cyberdeck)"
date: "2023-10-06T03:24:40Z"
draft: false
cover:
  image: "posts/cyber-deck/20231014_222525.jpg"
  alt: "cyberdeck cover"
  hidden: false
  hiddenInList: false
  hiddenInSingle: false
  relative: true
---

A computer, FPV video system, SDR radio, RC transmitter, and power system enclosed in a weatherprood case

# Overview

![overview](20231014_222821.jpg)

The objective of this project was to create an all in one solution for controlling drones in the field. The main systems are a laptop, FPV monitor, secondary monitor, SDR radio, RC transitter, and power system. The secondary objective was to improve thin metal welding and battery construction. After many prototypes, all systems are working properly. In the future, I do want to slim down the electronics with a custom pcb.

# Hardware

![case](20231008_184500.jpg)

In order to weatherproof the electronics, a pelican style case with a latching lid was selected. In order to pass power and data through the case, a laser cut steel plate with wire bulkheads is secured to a hole cut into one side of the case. Another panel contains C14 and US plug socket to pass data inside and out of the case. 

![plug panel](20230616_113127.jpg)

The interior went through many iterations in order to create an ergonomic interior that can contain all of the electronics. The first iteration tried maximizing volume but left no space for switches and buttons. 

![first iter](20230616_135321.jpg)

Following that lesson, the frame was redesigned to have recesed spaces for switches and a slot for a 60% keyboard. Constructed from laser cut thin stainless steel welded together, this design allowed for precision placement of switches, ports, bulkheads, and tight fitting access panels. 

![lower cad](Screenshot2024-07-12200618.png)
![lower cad 2](Screenshot2024-07-12200647.png)
![frame](20231008_184504.jpg)
![frame 2](20231008_184520.jpg)

The upper frame is constructed in a similar fashion with 3d printed parts to hold the screens in place. This was a lot trickier as I had to make the laptop easily removeable while keeping the ports exposed. Another hard design was how to attach the top panel. I eventually settled on a hinge system similar to a casette tape door. The panel is locked in place using a door push latch. For a bith of asthetics, an RGB strip lined the outer border of the upper panel. Using sanded acrylic and
later, a light diffusing material, I get a nice looking RGB effect. 

![upper cad](Screenshot2024-07-12200539.png)
![upper frame](20231011_095029.jpg)

After both frames were constructed, a paintjob was applied. I went for a dark black with white speckles because it sort of reminded me of stars which I like.

![paint job](20231011_172050.jpg)

As the case is meant to be carried to the field, It is designed in such a way that all ports are accessible when strapped to someones back via an external frame backpack.

![backpack](20231014_224138.jpg)

# Electronics

![electronics](20231007_222240.jpg)

The main electrical system's job in the box is to power all the case's electronics such as charging the laptop, supplying dc power to test equipment, powering external screens, etc. The case could be powered either from the wall or from its built in 21700 li ion pack. If powered from the wall, the ac power goes into a 300w 12v converter. The power is then eitehr used directly or stepped to 5v for lower voltage electronics. It is also used to charge the li ion battery via a dc to dc charging
circuit. When powered from the li ion, the 3s power is sent through a 3s to 12v converter and feeds into the same 12v rail as the power supply. This system works via a three position switch that serves as the master power. A drawback is that I need to shut the cae off when switching between wall and battery. On a full charge, the case is able to power everything for over 12 hours. 

![battery](20231015_091848.jpg)

# Conclusion

This was one of the more technically challenging projects as picturing the layout of all the parts and wires in such a tight space proved especially difficult. The final product, while functional, is also not as robust as I would like. I would like to make a second iteration some time in the future that incorporates lighter weight construction, and a more integrated electrical system that isn't just off the self components. Overall, still a very fun project.

![showcase](20231015_140831.jpg)
