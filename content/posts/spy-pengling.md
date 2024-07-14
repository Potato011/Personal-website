---
title: "Subnautica Spy Pengling"
date: "2021-01-23T03:24:40Z"
draft: false
cover:
  image: "posts/spy-pengling/20220115_222256.jpg"
  alt: "pengling cover"
  hidden: false
  hiddenInList: false
  hiddenInSingle: false
  relative: true
---

This is 1:1 functional replica of the spy pengling robot from the game Subnautica - Below Zero.

# Overview

This was my first large scale CAD assembly design. I wanted to make it as accurate as possible but also functional so I could drive it around like an RC car. Looking back, it shows hows crude my manufacturing techniques were but gave invaluable insight into how to better design robots.

## CAD Model

![cad](Spypenglingpic1.png)

# Drivetrain


{{< figure src="Screenshot2024-07-13174333.png" title="track pods each housing two brushed motors">}}

The CAD model can be divided into three primary sections which are the drivetrain, body, and head. The drivetrain contains the trackpods as well as the chassis. All drive electronics are located in the track pods with the battery and controller being located in the chassis. The body is mostly hollow except the mechanism to move the wings and a forward facing camera. 

{{< figure src="IMG_20210126_165539.jpg" title="track pod with motors installed">}}

# Head

![head](Screenshot2024-07-13174618.png)

The head is also mostly hollow but is fixed to the body through a servo so the head can rotate. The head is split into two pieces to reduce the amount of filament needed for supports.

# Body

![body](20211206_183107.jpg)

The body is split between a white exo and black endo skeleton. The endo skeleton provides the main structural supports and the exo provides the color and more detailed surface features. The body connects to the chassis via severa blult in pegs.

{{< figure src="IMG_20210210_173639.jpg" title="lower half of the body">}}
{{< figure src="IMG_20210212_154600.jpg" title="full endo skeleton">}}

# Printing

![printing](20220116_192742.jpg)

The print contained over 20 components without including track links. The entire thing was printed using my stock CR-10S. At the time of it's construction, the pandemic caused a shortage in filament so I had to resort to low rated ABS. Because of this and bad slicing settings, there were numerous print failures. Eventually, I got it done.

![full print](IMG_20210506_204538.jpg)

# Painting

![painting](20211124_154057.jpg)

To paint the model, the assembly was broken down, primed, and spraypainted. Due to the limited space available, I resorted to fashioning a paint booth out of cardboard boxes, plastic bags, and tape. The plastic bag was cut into a flat sheet with a hole cut in the middle. A latex glove was taped to the plug the hole thus allowing me to manipulate the part and paint can using one hand. To view the painting, I made a window out of packing tape (the only clear sheet I had that could be easily replaced once too much paint got on it). Smaller details were hand painted using acrylic paint and a brush.

{{< figure src="20211124_154057.jpg" title="head after being painted">}}
{{< figure src="20211206_183708.jpg" title="poor surface finish caused by globbing">}}
{{< figure src="IMG_20210506_204538.jpg" title="finished item">}}

# Testing

This is a static test of the drive system
{{<youtube D2oQXG6yKtw>}}

This is a moving test. As you can see, the tracks are removed and there is a very good reason which is explained further down in Revisions.
{{<youtube RWawQtPXd-0>}}

## Version 2

![new cad](wrapping-up-drivetrain-development-on-irl-spy-pengling-no-v0-leh3r556dtgb1.jpg)

After two years since the original model was build, I started design on a newer, more canonically accurate, and more importantly, actually functional spy pengling. The primary aim was to use better CAD experience and new manufacturing techniques to accomplish what I couldn't with the first model.

# Revisions

Here are a list of problems encountered with the first pengling and solutions:

| Problem | Solution |
| --- | --- |
| The drivetrain consisted of track over wheels which caused constant track jams when turning and the low friction between the wheels and tracks caused a significant lack of power. | The track pods are completely redesigned to use an actual sprocket system akin to those found on tanks and construction vehicles. This sprocket bites into the newly designed tracks so power is effectively transmitted into the tracks. |
| The motors were not strong enough to move the weight of the model even on flat ground | The two small dc motors in each track pod were replaced with one large geared, dc motor that can supply more than enough power to move the model. The motor drivers are also upgraded to support higher current |
| There is a lot of friction where the track rubs the against the lower part of the side skirts | The new design has the chassis fully supported using idlers that are optionally sprung using metal wires. The track geometry has also been changed from a triangle to quatrilateral which improves terrain crossing |
| The head cannot rotate 360 degrees because of the center mounted servo | The new head uses a 3d printed bearing in the head perimeter. The inside of the head has teeth so a motor can drive the head rotation while keeping the neck open for more equipment. |
| The chassis have low ground clearance and poor terrain crossing capabilities| The new trackpods are attached to the chassis using a psudo double wishbone suspension similar to those found on cars. Large RC car shock absorbers keeps the assembly relatively stiff. The tracks themselves have been modified to include more treading. |

# CAD Model

{{< figure src="wrapping-up-drivetrain-development-on-irl-spy-pengling-no-v0-skcgv456dtgb1.png" title="track pods with suspension system">}}
{{< figure src="wrapping-up-drivetrain-development-on-irl-spy-pengling-no-v0-j35pvuwfdtgb1.png" title="track pods with rollers and larger motor">}}
{{< figure src="22xx0obm4uj91.png" title="track pod upper rollers">}}
{{< figure src="tm6x8k5n4uj91.png" title="suspension travel range">}}

# Conclusion
As of now, this project is currently on hold but the design is largely finalized and I look formward to eventually finishing it. The focus of making this was to improve my CAD skills and it was pretty successful.
