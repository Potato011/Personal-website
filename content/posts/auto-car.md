---
title: "1:12 Scale GPS/Compass Guided RC Car"
categories: ["Drone", "Car", "RC", "Arduino", "CAD"]
date: "2019-12-08T03:24:40Z"
draft: false
cover:
  image: "posts/auto-car/20211223_231203.jpg"
  alt: "car cover"
  hidden: false
  hiddenInList: false
  hiddenInSingle: false
  relative: true
---

A 1:12 scale rc buggy fitted with GPS/compass and proximity sensing hardware allowing for autonomous waypoint navigation. This project was constructed over covid lockdown and was my first complex robotics project. The objective of this project was to learn about microcontrollers and the design procedure constructing a robot. Its construction involved arduinos, 3D printing, and GPS tech. Because it was my first non plug-n-play project, I lacked many basic skills including soldering, hence the very strange design choices.

{{<youtube UtupRltl5_M>}}

# BOM

| Chassis | [WLToys 12428 1:12 RC Crawler](https://www.aliexpress.us/item/2251832722592199.html?spm=a2g0o.productlist.main.3.5d872a46BFu8F0&algo_pvid=868578e7-ddcb-4287-921a-4e58fde3c87a&algo_exp_id=868578e7-ddcb-4287-921a-4e58fde3c87a-1&pdp_npi=4%40dis%21USD%2184.96%2174.82%21%21%2184.96%2174.82%21%402101e9a217207775048034112e7592%2112000036183668810%21sea%21US%212304647260%21&curPageLogUid=UlzDNm7mIvzu&utparam-url=scene%3Asearch%7Cquery_from%3A) | $75.96 |
| --- | --- | ---|
| Motor kit | [Brushless conversion kit](https://www.aliexpress.us/item/3256806623177330.html?spm=a2g0o.productlist.main.13.41546e37uw3BJp&algo_pvid=ecedf76c-7e92-4d31-989b-107bc94ce787&algo_exp_id=ecedf76c-7e92-4d31-989b-107bc94ce787-6&pdp_npi=4%40dis%21USD%2164.40%2147.65%21%21%21466.02%21344.85%21%402103205217207776167574550edfa8%2112000038376513724%21sea%21US%212304647260%21&curPageLogUid=q9gwSHrKjVfH&utparam-url=scene%3Asearch%7Cquery_from%3A) | $47.65 |
| Arduino Mega | [Elegoo Mega](https://www.amazon.com/ELEGOO-ATmega2560-ATMEGA16U2-Arduino-Compliant/dp/B01H4ZDYCE/ref=sr_1_1?crid=3IKG8E4RT1SMM&dib=eyJ2IjoiMSJ9.vzlPD-gqLjM6OBy_lbEGE2JYYcjgPxrHNgW0xV6ZrCaLq9LvwLYkVAN-T9chC43274hIzbBHNcCagPnAphWecKLJfcAFocN-1yDkQg6p8MGPTJsHsXjIoJUDavVZNgwJheA4b2SI0gnJWYJ9Di8Y-goZIV_LbMCao4XjHgRnARz6gFZUWQjB-QvDdFas4lenl8ZU38c-qASqyVupLqlVivYVWq2O-X7w4n-uGzROz3Y.nF4eor-s_tss89sMIXj8Fo1RMwBI8GL3g3C9nHbUa4U&dib_tag=se&keywords=arduino+mega&qid=1720777726&sprefix=arduino+mega%2Caps%2C338&sr=8-1) | $20.99 |
| Arduino Nano | [Elegoo Nano](https://www.amazon.com/ELEGOO-Arduino-ATmega328P-Without-Compatible/dp/B0713XK923/ref=sr_1_3?crid=3LXMF1LLCBANU&dib=eyJ2IjoiMSJ9.UR9t6Z2D5rIVJlr8NPSrk3wUQkkYYp4UX0eOYfAC6mwdHPgMIqbxOJ8TeejlK37zg1QXGAF0C6ArdDoKJyOVIwnxinVsDln3ehvQg_Nro3S6ohoN9vJLBAQg6BOyX-3gJGpF_KsdSvVCENO3ydSfZDC0x-r1SuemdDs_FXMRdCAli9-XamhoXwyiggGGwLw7Ki7ln3n8GnXyJ3LDVOY83c-gqXOzlllzJXUbaSjyk2A.U03mCwsj-fssJEU9jA5t4RQjlvyfA42XmzFSPZUo16E&dib_tag=se&keywords=arduino+nano&qid=1720777808&sprefix=arduino+nano%2Caps%2C208&sr=8-3) | $19.99 |
| LCD Display | [20x4 LCD](https://www.amazon.com/Hosyond-Module-Display-Arduino-Raspberry/dp/B0C1G9GBRZ/ref=sr_1_3?crid=EOSQD673RJ96&dib=eyJ2IjoiMSJ9.F7lyw5aicun_ZLtx_ZjOVlG8_WO8FYkRux-9eFJXwbutV8pg7720M7oKZT1GfThrrtyXX5h4rQKT4o5ZxBQA7JPbkEOyJpJuZSCCVIZi81dKpDBciDKKEUw-ROeBc-kEpCOJs866sQQkoDaKnb2bbPaNC-y2IUXNZgjK1aqhDRPlwNyvAdfY3o6B5u6Xn8ZBrdotUkAUXKnoRY47ehYkDS1F57-dQjJX98rvtsAhkcM.UrsHAaJIulA6KiqJjblfHN152YSprM-6Gl96ZHtkzzY&dib_tag=se&keywords=20x4+lcd&qid=1720777911&sprefix=20x4+lc%2Caps%2C240&sr=8-3) | $15.99 |
| GPS Module | [Adafruit Ultimate GPS Breadkout](https://www.adafruit.com/product/746) | $29.95 |
| GPS Antenna | [Adafruit External Acive Antenna](https://www.adafruit.com/product/960) | $19.95 |
| Ultrasonic Sensor Kit (x2)| [Elegoo Ultrasonic Sensor](https://www.amazon.com/ELEGOO-HC-SR04-Ultrasonic-Distance-MEGA2560/dp/B01COSN7O6/ref=sr_1_5?crid=1V568VG93OAAB&dib=eyJ2IjoiMSJ9.E2SIkElJhtFWCJCHL5Q6Yys8UWphh18sr7FUgRDIlqcQDsO801BNsCYLbrRsXGjYr6MzH2ILd3js_JSLecWHwmu_UjmprGzGpjJ8KsWP7imSfZfeD3n4zG6_Dfw6axtgQej0KHkaS9Dhh-hznmbGpKaZV4BgnB5VQ7azewH_7ZQWuKAtRApeuYLpX032xy_g8dIp4x-6Rdhrn9o04dlD1q_ebXAskUlHEAlpQMSyRGo.qg0TpbpUvOKIv6lt3MxK7Op3wJtVzHInmZieaNE__aw&dib_tag=se&keywords=ultrasonic+sensor&qid=1720778093&sprefix=ultrasonic+sensor%2Caps%2C296&sr=8-5) | $19.98 |
| FPV Cam | [Foxeer Razer Mini](https://www.amazon.com/dp/B07ZKPDPLM?ref=nb_sb_ss_w_as-reorder-t1_k9_1_10&amp=&crid=2NOI97T4OOHRG&amp=&sprefix=fpv+camera) | $29.99 |
| Pan/Tilt | [Pan/Tilt servo mechanism](https://www.aliexpress.us/item/3256806249982525.html?spm=a2g0o.productlist.main.11.695117b6YvOyfg&algo_pvid=20fbc419-8274-433c-af50-04cedc37dbc2&algo_exp_id=20fbc419-8274-433c-af50-04cedc37dbc2-5&pdp_npi=4%40dis%21USD%2115.72%218.80%21%21%2115.72%218.80%21%402103080e17207783034157134e0e12%2112000037159170085%21sea%21US%212304647260%21&curPageLogUid=KPb2nMG1Gs6e&utparam-url=scene%3Asearch%7Cquery_from%3A) | $8.80 |
| VTX | [AKK X2 5.8GHz](https://www.aliexpress.us/item/3256805177163510.html?spm=a2g0o.productlist.main.15.37517932CTL5HI&algo_pvid=82a8b5fc-b984-4916-8c94-71ee85994e2c&aem_p4p_detail=202407120300213857750057489650001241770&algo_exp_id=82a8b5fc-b984-4916-8c94-71ee85994e2c-7&pdp_npi=4%40dis%21USD%2128.63%2122.90%21%21%2128.63%2122.90%21%40210307c317207784211531994ef850%2112000032746635284%21sea%21US%212304647260%21&curPageLogUid=ll2LBwZI1SjD&utparam-url=scene%3Asearch%7Cquery_from%3A&search_p4p_id=202407120300213857750057489650001241770_2) | $29.90 |
| VTX Antenna | [TBS RP-SMA Triumph](https://www.aliexpress.us/item/3256803252400674.html?spm=a2g0o.productlist.main.13.6fd04701EnOFnP&algo_pvid=d6291417-3f0d-4152-a5f1-d5b3256932e7&algo_exp_id=d6291417-3f0d-4152-a5f1-d5b3256932e7-6&pdp_npi=4%40dis%21USD%219.96%214.98%21%21%219.96%214.98%21%402103205117202476705524134e6039%2112000025793283795%21sea%21US%212304647260%21&curPageLogUid=fokkD49I81ke&utparam-url=scene%3Asearch%7Cquery_from%3A) | $4.98 |
| Cooling Fans | [12V 40mm Cooling Fan](https://www.amazon.com/WINSINN-Brushless-Cooling-Extruder-Makerbot/dp/B0757LXKST/ref=sr_1_9?crid=D3JOOKSII4S1&dib=eyJ2IjoiMSJ9.xJcqInh-gXvLg8MVumxDjAOdv1_gjXQVGztREaDhqNKjrYdG0OSsqqGWgR8feqCM0iUAwXW_sPmiSgfXOL-sEv1ly0lF6tQY7agojx3bwExn9zkWDLS5jR5xwmRaTz2aeL8PzNLB81VHDsm-WYNYUiWGZghpaUy4i3Jb1kgpoBuW8NYvrmmhirnk7cXeCJ4CFQ7fdn9j4G9Wunzbnw8aIJoRwUNDYaaw5IFWWMPOK-Q.Y2OFGmhynKVQdVoo-9Flg-rIrFXavhin4XYeFTnI5Yo&dib_tag=se&keywords=micro%2Bcooling%2Bfan&qid=1720778693&sprefix=micro%2Bcooling%2Bfan%2Caps%2C279&sr=8-9&th=1) | $10.99 |
| Battery (x2)| [Zeee 3S 5200mah lipo](https://www.amazon.com/Zeee-Connector-Hardcase-Helicopter-Airplane/dp/B08696WZMK/ref=sr_1_6?crid=1QVG577SZS5AX&dib=eyJ2IjoiMSJ9.JPyBzWZCyzJftyc9S9bDQJhwBpOYoa7nu_txsIvkJPn_i-eaW6E0iw3IVd4lQRXgQflj5TcXWtK5hZkTEd6mYDhovOILnZW_F3mQ7k-aO-2oVVW_3u7PomVLxk2y3bBoLhlNcDZqMu8dPJGCAxgagU-UqQbKn45B59IzwbJFYL4XAATn7BhSZ5slUvRLm-QzkPnImvQFfeW5_RO2TV4MeW99QkDZZaNQyaS6dA5uMAaaGA90D64_xlBrDHZgynt9IIu86yrv6uPdxRkzD2PIGpUUyeRhxmPhe6MGvVjDfNg.SZC5Jrq2WKxd_2fQsl2hrew5hVOOL37lWaEhgKlfKDY&dib_tag=se&keywords=3s+battery&qid=1720778838&sprefix=3s+battery%2Caps%2C259&sr=8-6) | $63.89 |
| Shock Absorber | [Upgrade Metal Shocks](https://www.amazon.com/Absorber-Upgrade-Damper-WLtoys-Monter/dp/B07W9H5HSD/ref=sr_1_3?crid=14RLDB3CNZHGD&dib=eyJ2IjoiMSJ9.c754f4Ew1BT-DESiiWU8YtKJ8aMZBmo64W7f6bbaTKWB1DKx0aC09l13BKWA8H9b1DJ1ixUwaLLSkQBo6K2lmTN2q9gaqT48ZAERGCbzCHHx2nBlGxwdfuQSza4uGUkds-HoMvzqlvErUt5eHE_ec231MMQ0FWP5IzGOclRFGMnrr9TuV7f3f7q9MXC24pbM0CZ8G49_ZBfFsxRS7r5kXUZsfW0vzinbGxRJIK9M21lH1_FMeTjiza41HWO57KgLCp889iynm-b39T22QlkbdmOLnb1H1PylZuqkKF1xMHI.xr_76Wy83A37JOsYeiXdh3vcN72MX1SGRHLGvaVh0s0&dib_tag=se&keywords=wltoys+12428shock+absorber&qid=1720779050&sprefix=wltoys+12428shock+absorber%2Caps%2C191&sr=8-3) | $14.55 |


# Chassis Design

![Chassis Prototype](CC.jpg)

To minimize cost, a widely availabe rc car chassis was selected. I picked this one because at 1:12 scale, it's large enough to mount arduino sized electronics and being a crawler chassis, its four wheel drive allows for good terrain crossing. To mount the equipment,an acrylic sheet was screwed into the roof of the crawler chassis. The arduino and circuits are taped to that acrylic sheet. While this design worked on the bench, the equipment was not secured rigidly enough to give accurate values
so a redesign was made moving all self driving equipment to a 3D printed backpack located at the rear of the vehicle.


{{< figure src="20191231_122851.jpg" title="initial hardware mounting" >}}
{{< figure src="IMG_20201217_180214.jpg" title="backpack style hardware mounting" >}}
{{< figure src="IMG_20210305_172547.jpg" title="basic wiring with backpack" >}}
{{< figure src="20210914_185641.jpg" title="most recent mounting" >}}

# Wiring

![Wiring Layout](20211223_231727.jpg)

The car has a simple wiring structure but it translates into a lot of wires. The main electricals systems can be split into power management, data processing, navigation, and drivetrain. Power management includes batteries and voltage sensors. data processing involves the arduino mega, arduino nano, buttons, potentiometers, oled, lcds, and data logging. Navigation includes sensors that help steer the car such as the GPS, IMU, and ultrasonic sensors. The drivetrain includes all components that move
and steer the car such as the motor, esc, steering servo, and RC transmitter system. To ensure that the operator always has control over the vehicle, the drivetrain can accept steering inputs from either the arduino, or RC receiver via a multiplexer that takes a PWM select signal from the RC receiver. The data processing unit is the most complex part of the car as it handles all the navigation and user interface. The arduino mega with its larger memory handles all sensor inputs and computations to get the angle the servo should turn to. The mega also talks with the nano which handles asynchronous tasks such as updating the screens and sensing voltage. When operating in waypoint mode, the arduino mega takes a GPS waypoint in the form of longitude and latitude coordinates from an onboard sd card. Once it arrives, a white light is triggered and the LCD is updated. When the mission ends, the car commands full stop and flashes the light.


{{< figure src="20211214_125317.jpg" title="exploded wiring view" >}}
{{< figure src="20211217_023227.jpg" title="solderless wiring (not recommended)" >}}
{{< figure src="20211223_231338.jpg" title="backpack top down view" >}}

# Code

The logic of the code is very similar to a line following robot only this time, the robot draws the line using gps coordinates. The process starts with the car getting its next waypoint. It then compares this waypoint to its current coordinates and use trigonometry to calculate the bearing relative to north (0-364 degrees). Finally, using the IMU, the car determines its own heading and by taking the difference between the heading and bearing, the car knows how far to turn the
steering servo. The distance to the waypoint is calculated using the haversine formula and once the car arrives within a radius of the waypoint, the next waypoint is loaded. If the car misses the waypoint, it will double back until it gets within range. In later iterations, ultrasonic sensors were introduced to correct for terrain features or obstructions that would prevent a straight line path to the waypoint.  

# Testing

The first series of test were conducted in my garage to see if I could get the servo to turn correctly. Afterwards, I tested in the park fields. The final test was over 2 miles through a hiking trai. During this test, I drove the car manually through, logging GPS coordinates so that on the next pass, the car could retrace my path. The testing gave good results on the open field and while it sort of worked on the trail, the limitation of the GPS module's accuracy prevented it from completing
the trickier sections. 

{{<youtube b3gWne98YPU>}}
{{<youtube 5-EC5Vh6f8I>}}
{{<youtube clXEDXiiAkk>}}
{{<youtube Gm9umyj9HV4>}}


# Conclusion

Overall, this was a great experience into microcontrollers as well as the troubleshooting skill required to plan out a robot. It was this project that first got me into robotics and drone tech.
