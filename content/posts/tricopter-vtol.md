---
title: "Tricopter VTOL"
categories: ["Drone", "RC", "Plane", "Copter", "Ardupilot"]
date: "2022-10-07T03:24:40Z"
draft: false
cover:
  image: "posts/tricopter-vtol/20230112_204454.jpg"
  alt: "triVTOL cover"
  hidden: false
  hiddenInList: false
  hiddenInSingle: false
  relative: true
---

A small tricopter vtol allowing for fun fixed wing FPV out of areas that lack runway space

# Overview
This project was my introduction into ardupilots and autonomous flight. Prior to this, all my models were simple RC planes which were either entirely manually controlled or had limited flight stabilization built into the receivers. It was a steep learning curve to start with a vtol but provided an excellent teaching experience.

# BOM
| Airframe | [Heewing T-1 Ranger PNP](https://www.amazon.com/gp/product/B09XKBDPXB/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) | $169.16 |
| --- | --- | --- |
| ESC (x2) | [BLHeli 35A ESC](https://www.aliexpress.us/item/3256806228712998.html?spm=a2g0o.order_list.order_list_main.5.26ff1802JbPjpp&gatewayAdapt=glo2usa) | $19.31 |
| Aileron Servo (x2) | [EMAXX es08MA II](https://emaxmodel.com/products/emax-es08ma-ii-12g-mini-metal-gear-analog-servo-for-rc-model-robot-pwm-servo) | $15.50 |
| Propeller (X2) | [HQProp Ethix 5x4x3](https://www.amazon.com/gp/product/B07XGHYKLB/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) | $16.99 |
| FPV Cam | [Runcam Racer Nano 2](https://www.amazon.com/gp/product/B0832NTZ95/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) | $25.59 |
| Flight Controller | [Matek H743 Wing V3](https://www.aliexpress.us/item/3256803206329896.html?spm=a2g0o.order_list.order_list_main.76.26ff1802JbPjpp&gatewayAdapt=glo2usa) | $107.89 |
| GPS/Compass | [Matek M10-5883](https://www.aliexpress.us/item/3256806557988306.html?spm=a2g0o.order_list.order_list_main.40.26ff1802JbPjpp&gatewayAdapt=glo2usa) | $32.47 |
| Receiver | [Radiomaster RP3 ELRS Receiver](https://www.amazon.com/gp/product/B0BGBKG635/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) | $22.99 |
| Transmitter | [Radiomaster Tx16S MKII MAX - ELRS](https://www.radiomasterrc.com/products/tx16s-mark-ii-max-radio-controller?variant=42850745188583) | $249.99 |
| VTX | [AKK X02](https://www.akktek.com/akk-x2-ultimate-us-version.html) | $24.99 |
| VTX Antenna | [TBS RP-SMA Triumph](https://www.aliexpress.us/item/3256803038729482.html?spm=a2g0o.productlist.main.13.6fd03307CVRejQ&algo_pvid=6ad86606-27b5-4bdf-a94e-3681d3a4d5f6&algo_exp_id=6ad86606-27b5-4bdf-a94e-3681d3a4d5f6-6&pdp_npi=4%40dis%21USD%213.50%213.50%21%21%213.50%213.50%21%402101ef7017279771504077103e2997%2112000024741588916%21sea%21US%212304647260%21XZ&curPageLogUid=ztyRktXwcCrC&utparam-url=scene%3Asearch%7Cquery_from%3A) | $4.98 |
| Battery (x2) | [Tattu 4s 2300mah Lipo](https://www.amazon.com/gp/product/B013I9SVD2/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) | $36.84 |

# Airframe

![Airframe Assembly](20221211_143149.jpg)

The airframe arrived as mostly assembled fuselage as I selected the pnp kit. The only major modifications I had to make were the holes in the foam cut to pass through the filght controller programming port, gps cable, and rear motor power/data cable. The kit came with landing gear but that was removed and a skid replaced it.

# Nacelle Modifications

![Nacelle Modidications](20221007_225330.jpg)

To facilitate Vertical TakeOff and Landing(VTOL), The straight nacelles were replaced by new 3D printed ones that had a servo actuated hinge that allowed the motor mount to swivel about 100 degrees up from clockwise. The motors themselves are 2207 2400KV brushless motors used for quadcopters.

# Electronics

# Testing

# Conclusion
