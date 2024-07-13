---
title: "High Payload Fixed Wing Testbed"
date: "2024-07-05T03:24:40Z"
draft: false
cover:
  image: "posts/skywalker-titan/20230524_111557.jpg"
  alt: "titan cover"
  hidden: false
  hiddenInList: false
  hiddenInSingle: false
  relative: true
---

A high capacity cargo platform capable of lifting test equipment into the air remain on station for extended periods of time.

# Overview

The purpose of this airframe is to test experimental avionics and payloads. The airframe has high internal volume to fit bulky cargo as well as hardpoints on both wings for external loads. While the original intention was for this plane to fly, I've deemed the risk too high and as such, this airframe is to remain on the ground for testing. Even without flying, it has proved invaluable when I need to verify new firmware and plan layouts for other vehicles. I have many plans to implement the
equipment installed on this plane to my other airframes.

# Construction

![construct](20230201_132238.jpg)

I picked the Skywalker Titan 2160mm survey drone as the airframe due to its large wing area, modular cargo compartment, and twin motor design. The wings also have flaps built in which is rather unique among survey airframes. The plane arrived as a series of large foam parts along with a bag of smaller acrylic and plastic parts. While the kit was well thought out, it didn't come with instructions so I had to guess a fair bit of the installation. I glued most of it together, leaving
several critical panels unglued so I could install the wing embedded electricals.

{{< figure src="20230116_161445.jpg" title="it's very large compare to my vtol">}}

# Airframe Construction/Hardware Modifications

{{< figure src="20230504_160444.jpg" title="nose landing gear and pitot tube probe">}}

One of the first airframe modes was the addition of retractable landing gear. This allows me weigh the plane down more than what can be hand launched. It also allows me to test automated takeoffs and landings. 

{{<youtube WF5YNnRYopU>}}

{{< figure src="20230421_190448.jpg" title="initial landing gear layout">}}
{{< figure src="20230504_160348.jpg" title="reinforced landing gear mounts">}}

Another modification is the addition of wing pylons for external loads. I originally added this to mount air sample collection modules but It can be used for various purposes. The hardpoints were designed with as much modularity as possible and can be fitted with static mounts or drop mechanisms (not developed yet).

![extended flaps](20230504_160359.jpg)

While the stock flaps work alright, to improve low speed performance, I modified them into extended flaps. By using long, nylon flap hinges, the angle of movement of these flaps are extended significantly to the point where they are almost perpendicular to the airfoil. While I don't have test data, I figure when deployed, the flaps could lower the stall speed especially with the powerful motors.

{{< figure src="20240713_161110.jpg" title="side view of fully extended flaps">}}

To cover the GPS receiver, a 3D printed dome was installed over the receiver. It also provides a convenient place to place the upper strobe light.

![nylon hinge](20240713_162636.jpg)

Most RC planes are made from injection molded foam. The wings are molded with foam hinges for the control surface. While this works for smaller airframes, larger ones are at risk of having their hinges rip when the airframe is under high stress. To remedy this, I cut all the control surfaces off, inserted nylon hinges, and replaced the control surfaces.

# Wiring/Electrical Modifications

![wiring](20230504_160426.jpg)

In order to lift heavier payloads, I speced a significantly more powerful thrust package than used for survey drones of this size. Each wing nacelle houses a 3520 520KV motor connected to a V-Good 120A esc. The entire system is driven by a 6S 10,000mah lipo pack with a li ion pack in production. This allows a max takeoff weight of over 9kg and a crusing time of roughly an hour. 

![tail servo](20240713_161738.jpg)

Ailerons, the V-tail, and flaps are driven by EMAX es08 maii mg servos which theoretically work but I plan to upgrade to EMAX 3054 servos. All other functions are handled by smaller plastic 9g  servos. The only servos not in their stock position are the tail servos which I embedded into the tail for better leverage over the surface. 

![matek](20240713_161724.jpg)

A Matek H743 V3 Wing controls the entire system. I selected it because H7s have significantly more memory than other processors and Matek has some of the best documentations available. For navigation, a Matek m10q-5883 GNSS receiver is used and for telemetry, data is sent through both the ELRS receiver to the pilot's radio and a Holybro SIK 915mhz telemetry radio. Desipte having 13 servo outputs, I am reaching the upper limit and will need to figure out how to increase that number. To power the payload, the cargo compartment has a xt90 bulkhead delivering power from the main battery. Controls are handled via either spare servo ports or a separate telemetry radio. 

![nav lights](20230504_160434.jpg)

For better visibility in low light environments, the plane is equipped with wingtip red/green light as well as an upper and lower strobe light.

{{< figure src="20230424_234455.jpg" title="wing internal wiring">}}

# Testing

There's not much test footage because most are firmware related or amount to a few movements in the control surfaces. Here's a video of the plane taxiing:

{{<youtube dq9G4iCxFeQ>}}

# Conclusion
