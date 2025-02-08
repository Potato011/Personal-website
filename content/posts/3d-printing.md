---
title: "3D Printing"
date: "2024-07-05T03:24:40Z"
draft: false
cover:
  image: "posts/3d-printing/image29.gif"
  alt: "3dprint cover"
  hidden: false
  hiddenInList: false
  hiddenInSingle: false
  relative: true
---

I've experimented a lot with 3d printing technologies and have constructed several rather unique machines.

# My First 3D Printer

My first 3D printer was a creality CR-10S purchased around 2020. Its purchased happened when I was getting familiar with cad and I got the printer in order to print the Subnautica Spy Pengling I modeled. In the years since, this printer has undergone numerous upgrades and is still in service today. It now features remote printing, dual extruders, and a more powerful main board to accomodate additional features. While it barely competes with modern 3D printers, building it taught
me a lot about troubleshooting 3D printers and the limitations of the technology. Since then, I've also branched out into other printers such as sla, multi material extruders, and large scale industrial printers. 

# Automation

![automation](20220103_120655.jpg)

One of the first mods made to the CR-10S was the addition of a raspberry pi 3 b+ loaded with octopi firmware. This allowed me to connect my printer to my local wifi and control it remotely from my laptop or phone. I wired a relay module to the pi so that I could power on various components like the printer, lights, and later, heaters/fans.

![automation 2](20230727_210521.jpg)

# Dual Extrusion

![dual extrusion](20230328_145947.jpg)

I started experimenting with dual extrusion because I wanted to upgrade my extruder and also wanted water soluable supports. My first iteration followed an existing tutorial and used E3D volcano extruders which in theory push out more material than the stock extruder. This mod required me to switch from the stock creality main board to a MKS 2.1 Gen L to accomodate the additional stepper motor needed for the second extruder. Due to this change, I was forced to learn Marlin firmware and
how to tune a printer. Ultimately, the results were less than satisfactory. While the extruder worked, the 3d printed framw was not rigid enough to create accurate layers and any lifting of the model would cause the unused nozzle to hit the print and dislodge it. After a particularly long print, I came home to this: 

![print fail](20230927_075146.jpg)

It was at this time I decided to go with a more professionally made but still unique design. The new extruder is a MakerTech Dual Extruder v2.1 and it offers the advantage of havig a metal frame and mechanism to lift the unused nozzle. Its rotating offset nozzle also had the unique advantage of covering the unused nozzle with a metal plate thus sealing it to prevent oozing. This decreased print time as the nozzled were almost guaranteed to be primed and thus, I could eliminate the need to
print a prime tower.

![makertech](20231220_144208.jpg)
![dual color](20231226_095534.jpg)

# Water Soluable Supports

![soluable](20230906_151648.jpg)

During my time in uni, I worked for the Qualcomm DroneLab with one of be responsibilities being the repairing and upgrading of the lab's 3D printing equipment. One such machine was the Zortrax M300, an industry grade dual extruder printer. Personally, it did not live up to my expectations and from what I heard from other lab personel, this printer had alwasy been a pain. However, it was the first printer that I tested water soluable supports with. The unique challenge with it was the wacky
temperature settings and different print speeds needed to prevent bad adhesion. It took some trial and error but eventually worked out.

![soluable 2](20230908_115116.jpg)
![soluable 3](20230908_115128.jpg)
![soluable 4](20230908_115040.jpg)

# Large Scale Industrial Printers

![3dp](20230729_075419.jpg)

One of the printers I maintained was a massive 3DP Workbench 300 series printer. With a 1x1x1 meter build volume and up to a 2.8mm extruder, it was capable of printing large pieces in a relatively short time. When I first started working on it, it had sat dormant for many years. To bring it back into operation, I had to upgrade the firmware and refurbish the extruder assembly. The longest process was tuning the slicer settings to prevent filament jamming. This was by far the most
frustrating process as the all metal hotend and inadequate heat brake made heat creep a big issue. Ultimately, a combination of careful heating element positioning, retraction settings, and a custom CNCed heat brake resolved the issue. The printer is now capable of printing various materials without supervision.

![3dp 2](20231001_182432.jpg)
![3dp 3](20230728_185138.jpg)
![3dp 4](20230729_075419.jpg)
![3dp 5](pelvis.jpg)

# Conclusion

3D printing is a very powerful manufacturing tool and working with them have taught me much about the troubleshooting process as well as the quirks with using this technology. It also forces me to take manufacturing into consideration when I design parts. Knowing the capabilities and limitations of various manufacturing techniques including 3d printing has paid off immensely with time and material saved.
