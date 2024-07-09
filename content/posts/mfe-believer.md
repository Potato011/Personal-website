---
title: "Long Endurance Fixed Wing Camera Platform"
date: "2024-07-05T03:24:40Z"
draft: false
cover:
  image: "posts/mfe-believer/20240523_175322.jpg"
  alt: "believer cover"
  hidden: false
  hiddenInList: false
  hiddenInSingle: false
  relative: true
---

A autonomous, long endurance, high altitude camera platform for gimballed fpv

# Overview
I planned out this aircraft to soely focus on efficiency and stable flight performance. With a 5.5Kg max takeoff weight and two 6s 10aH lipo battery, this aircraft can stay in the air for over 3 hours. Swap one of the batteries for a downward facing DSLR camera and the aircraft becomes a capable mapping platform. Control is handled vial the latest H7 processor running ardupilot firmware enabling the aircraft to navigate autonomously, accept waypoint missions, and operate a three axis
gimbal installed in the nose.

# BOM

| Airframe | [MFE Believer 1960mm UAV Fixed Wing](https://www.uavmodel.com/collections/fixed-wing/products/makeflyeasy-believer-1960mm-uav-fixed-wing) | $254 |
| --- | --- | --- |
| Motors (x2)| [T-Motor Navigator Type 700KV](https://store.tmotor.com/product/mn3110-motor-navigator-type.html) | $61.90 |
| ESC (x2) | [Hobbywing XRotor 40A ESC](https://www.hobbywingdirect.com/products/xrotor-40a-esc?variant=955949541) | $17.99 |
| Aileron/Tail Servo (x4) | [EMAX ES3054 Servo](https://emaxmodel.com/collections/digital-servo/products/emax-es3054-17g-3-5kg-0-13sec-23t-metal-gear-digital-servo-for-rc-airplane-es3154-upgrade) | $9.99 |
| Parachute Servo | [EMAX es08MA II](https://emaxmodel.com/products/emax-es08ma-ii-12g-mini-metal-gear-analog-servo-for-rc-model-robot-pwm-servo) | $7.75 |
| Propeller (CW + CCW)| [APC 12x6E](https://www.apcprop.com/product/b12x6e/) | $4.87 |
| Parachute | [6Kg Recpvery Parachute](https://www.aliexpress.us/item/2251832793756388.html?spm=a2g0o.order_list.order_list_main.5.7c141802MT3TME&gatewayAdapt=glo2usa) | $32.71 |
| Gimballed Cam | [SIYI A8 Mini 3 Axis Gimbal](https://www.aliexpress.us/item/3256805419993722.html?spm=a2g0o.order_list.order_list_main.11.16dc1802SbAQR4&gatewayAdapt=glo2usa) | $228.22 |
| FPV Cam | [Foxeer Razor Mini](https://www.amazon.com/gp/product/B0CHYGC2N9/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) | $24.58 |
| Flight Controller | [Matek H743 V3 Wing](https://www.aliexpress.us/item/3256805941771531.html?spm=a2g0o.order_list.order_list_main.57.57a71802R5Pz7Q&gatewayAdapt=glo2usa) | $101.05 |
| GPS/Compass | [Matek M10Q-5883](https://www.amazon.com/M10Q-5883-Compass-SAM-M10Q-QMC5883L-Magnetic/dp/B0BZ7VJKHV/ref=sr_1_1?crid=2TDCZQ018Q2VN&dib=eyJ2IjoiMSJ9.1YfR4_vEPm2tH7_gjvk6Qz_sF3g-rq2nUq_EODOIZj4lSPeJb7xhfVOvpE2PrzO_JXtIiLCxW0Oit-X2fzPnUguVxT_yGOhXB8SDwsR3wy8FsbMgdNOy3-UYIsTF_UXFHQCo-ZpmqEtWlWeU6DXmJg.m4nGke_FWZ9FGps3hy9zVO8MQNw_s3c9_iRBZlE-MVw&dib_tag=se&keywords=matek+m10q+gps&qid=1720247267&sprefix=matek+m10q+gps%2Caps%2C220&sr=8-1) | $40.99 |
| Reciever | [Radiomaster RP3 ELRS Reciever](https://www.amazon.com/RadioMaster-RP3-ELRS-FPV-Receiver/dp/B0BXX6H85T/ref=sr_1_1_pp?crid=26Y8I9833PQ4V&dib=eyJ2IjoiMSJ9.O_Rh3re2r7FXNEfL-MTGegxIKXfzu7XS7Wd78-236z68rdkjXLlw8LuQJj64UTsUUc5t_K46yb16t03pr6_8N8_c-5iWJRopv23md-FTURqQ97BkGcaaKtTjh0Rf3Fjx7CFY86ZMrC_K5I1gE8Sg1-L5ikYCkM6FUyi42ycKlyFEdYfHHR68hjv-8DzBu7GKIJx3smRj-I-H3m9057SZt7e5P6gUJde9cvgeCpq60jsPi7bXQ-HhfKp3s0fuDoLgnYNo6Xh78w9WQRGU8DPtVrkV3WqO_KRYkwG-Ea1Fm4w.ITyrt5pGUREfut3WkjLo_d8XptzO4Y4f0h6DHmRlH5E&dib_tag=se&keywords=radiomaster+rp3&qid=1720247323&sprefix=radiomaster+rp%2Caps%2C207&sr=8-1) | $20.99 |
| Transmitter | [Radiomaster Tx16S MKII Max - ELRS](https://www.radiomasterrc.com/products/tx16s-mark-ii-radio-controller) | $249.99 |
| VTX | [RushFPV MAX SOLO 2.5W](https://www.aliexpress.us/item/3256805022846806.html?spm=a2g0o.order_list.order_list_main.5.37be1802RZmqGY&gatewayAdapt=glo2usa) | $64.18 |
| VTX Antenna | [TBS RP-SMA Triumph](https://www.aliexpress.us/item/3256803252400674.html?spm=a2g0o.productlist.main.13.6fd04701EnOFnP&algo_pvid=d6291417-3f0d-4152-a5f1-d5b3256932e7&algo_exp_id=d6291417-3f0d-4152-a5f1-d5b3256932e7-6&pdp_npi=4%40dis%21USD%219.96%214.98%21%21%219.96%214.98%21%402103205117202476705524134e6039%2112000025793283795%21sea%21US%212304647260%21&curPageLogUid=fokkD49I81ke&utparam-url=scene%3Asearch%7Cquery_from%3A) | $4.98 |
| Battery (x2)| [Turnigy 6s 10,000mah 12C Lipo](https://hobbyking.com/en_us/turnigy-high-capacity-10000mah-6s-12c-multi-rotor-lipo-pack-w-xt90.html) | $96.99 |
|Telemetry Radio | [Holybro SIK Telemetry Radio - 915MHz 100mW](https://www.aliexpress.us/item/3256803435024117.html?spm=a2g0o.order_list.order_list_main.20.21ef18028VNOui&gatewayAdapt=glo2usa) | $59.80 |

# Airframe Construction

![Airframe Assembly](/static/mfe-believer/20240411_191819.jpg)

The airframe arrived as several large foam parts and bags of smaller plastic, acrylic, and wood parts. I followed [ArxAngel's](https://arxangelrc.blogspot.com/2017/11/believer-1960mm-professional-mapping-fpv-platform-best-designed-aerial-platform.html) construction techniques, carefully glueing the major components together, using tape to hold them in place during the drying process. After everything dried out, I conducted a stress test (me shaking it a lot) and weighed it. One of the reasons why I picked this specific airframe was its proven flight efficiency and the low weight was a reassuring sign.

![Airframe Weight](20240411_204949.jpg)

# Wiring

![Wiring 1](20240705_235445.jpg)

Wiring was tricky due to the sheer number of cable that need to be run to supply power and data to the various aircraft systems. The rolling addition of new components did not help. Wires were slotted into channels built into the airframe whenever possible and if that was not a option, taped to the side of the fuselage interior. Quick release connectores provided easy detachment of the wings but require quite a few extra solder points. All in all, it was a multi hour process.

{{< figure src="20240705_235406.jpg" title="Battery compartment wiring" >}}
{{< figure src="20240705_235411.jpg" title="Front to back view" >}}
{{< figure src="20240705_235423.jpg" title="Avionics bay" >}}
{{< figure src="20240705_235432.jpg" title="VTX bay" >}}

# Testing


![Testing 1](20240427_135815.gif)

The longest step of assembly. This was by far the most painful but educational process that led up to the first successful flight of this aircraft. The first step was to load the arduplane firmware onto the flight controller(FC) and map all the correct outputs to their corresponding control surface/motor. After that, the radio was bound and configured to talk to the FC. Following a thorough ground test to ensure all control surfaces behaved correctly both during manual control and autopilot
stabilization, the plane was ready for its first test flight ...

![Testing 2](20240506_223545.jpg)

The takeoff seemed perfect until at an altitude of roughly 10 ft, the aircraft banked sharply to the left and cartwheeled into the ground. The impact tore the nose off and caused multiple cracks along the forward half of the fuselage. Luckily, due to the nature of the crash and the extra foam padding in the battery compartment, the wings and battery were both recovered intact. Despite that, it was one of the most demoralizing experiences since this was the conclusion of multiple
unsuccessful takeoffs with this having the biggest consequence. Post crash analysis determined that the left side propeller nut was not adequately torqued down causing the left side to lose thrust thus causing the left wing to dip. With the issue in mind, the work continues


{{< figure src="20240506_231743.jpg" title="unbending the fuselage" >}}
{{< figure src="20240506_233808.jpg" title="gluing the nose" >}}
{{< figure src="20240507_125654.jpg" title="sanding excess glue" >}}
{{< figure src="20240525_165231.jpg" title="fixed(sort of)" >}}

# First Takeoof

At this point, I was at an all point low when I went to the field and after the preflight checks, I wasn't expecting too much. But then ...

![Takeoff 1](Screenshot_2024-07-04_185057.png)
![Takeoff 2](Screenshot_2024-07-04_185132.png)
![Takeoff 3](Screenshot_2024-07-04_185153.png)

My throw was a bit weak but at max throttle, the plane has a thrust to weight of over 0.5 and was able to climb out of it at the last second. The first flight was perfect with over 50 minutes of loiter time at 60 feet. The autopilot was a bit rough at first but autotuning smoothed out almost all the jitter. The sight of it flying was very uplifting.

![Takeoff 4](20240523_172957.jpg)

# Gimbal

![Gimbal 1](20240521_093453.gif)

Now that the plane proved that it could fly, it's time to install the gimbal. The plane was originally not meant to have a gimbal and to explain why there is now a gimbal we have to talk about the URC. At the time the plane was being planned out, the University Rover Challenge, the competition my robotics team competed in, changed its rules to allow drones to assist the rover. The drone challenge called for the drone to read a sign on the top of a hill. Unlike multirotors, a plane can't
hover and thus, I intend to orbit the sign with the gimbal turned sideways and zoomed in all the way. This way, I keep the efficiency of a fixed wing while being able to accomplish the mission. For the smoothest image, a brushless gimbal was selected over a servo driven pan/tilt system.

![Gimbal 2](20240525_071018.jpg)

The gimbal is installed onto a 3D printed quick release mount that allows the gimbal to be removed so the fuselage can be put into its travel box. When installed, a single self tapping screw secures the gimbal plate to the fuselage mount.

# URC

![URC 1](IMG_1717005983594.jpeg)

The plane conducted one successful flight near the competition site. Unfortunately, the harsh desert conditions caused the motors to intake airborne dust and sand which prevented a flight during the actual competition. Despite the circumstances, the footage from the desert is still excellent.

{{< figure src="Screenshot_2024-07-04_185432.png" title="takeoff" >}}
{{< figure src="Screenshot_2024-07-04_185522.png" title="looking back" >}}
{{< figure src="Screenshot_2024-07-04_185647.png" title="over the front" >}}
{{< figure src="Screenshot_2024-07-04_185714.png" title="banking right" >}}

After the competitions, the motors were replaced and a custom propeller spinner that covers the motor intakes was installed. Motor cooling is now handled by an internal fan that intakes air from the back through filters. Also, gaskets have been added to all hatches/openings to prevent dust or water from entering. These modifications should greatly increase survivability through harsh conditions on the ground and in the air.

# Conclusion

This plane was a big step forward in learning the ins and outs of ardupilot. All my previous drones were only manually controlled so this was the first project involving full end to end autopiloting. It shows how many things need to be considered to create a functional and reliable end product. While it wasn't able to complete its task at the URC, I have many plans for it in the future. 














