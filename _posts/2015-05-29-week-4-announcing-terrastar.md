---
layout: post
title: Announcing TerraStar
excerpt: Another big week, finished the sensor tray and brought on a new sponsor
headerImage: /blog/imgs/terrastar.png
headerColor: rgb(226, 240, 222)
---

We mentioned last week that we were working on bringing a new sponsor on board. Today, we are pleased to announce that TerraStar will be joining the sponsor team for this summer's prototype. TerraStar Precise Point Positioning (PPP) provides a feed of corrections data which allows GPS receivers to compensate for variations in the atmosphere and small errors in satellite paths. 

Practically speaking this means that by using TerraStar we are able to get a 10x more accurate GPS location out of the same receiver. This additional accuracy is very important to the prototype because we are determining what path to drive exclusively using GPS. TerraStar will be providing us with a 3-month trial of their TerraStar-C subscription, which allows us to know our posiiton anywhere in the world to within 10cm. Thank you so much TerraStar, we're really excited to work with you!

For those of you who are interested in learning more about our GPS rig we'll be doing a post later this term detailing how it works, look forward to that :).

This week has also been very productive on the sensor tray front, we CNC-ed all the plates for the sensor tray:

![Sensor tray plates](/blog/imgs/st_plates.jpg)

A little bit of forearm-melting rivetting later and we have the finished sensor tray attached to the cart, ready to start scanning for obstacles:

![Sensor tray mounted to the cart](/blog/imgs/sensor_tray_done.jpg)

We met with a couple of application engineers from NovAtel (the sponsor giving us our GPS receiver) on Monday, they were really friendly and excited about the project. One thing they suggested to us was that we would be best off if our receivers had a clear view of the sky, so in all likelyhood the receiver wont be mounted on the sensor tray - unlike the photo. Instead we are in the process of designing a custom roof to mount the receivers to.

Mike has also started working on the design for our steering retrofit. We wanted to make sure the steering wheel still works when self-driving is off, so we made sure to tap into the existing steering system, without altering the existing design. Here's a sneak peak of the new design:

![Steering mechanism](/blog/imgs/steering_cad.jpg)

We even have the first part made for steering, it's the only CNCed part on steering (mike's going to be making the rest on the manual mill). Consider this another challenge to find it in the photo above:

![Sprocket mount](/blog/imgs/sprocket_mount.jpg)

Now that the sensors are mounted we plugged them all into a network switch and now have them all streaming to the computer at once. With everything running, Alex got a chance to take advantage of his first cool feature in Robot Operating System. Using a tool called ROSbag we can record and playback the output of our GPS and LiDAR so that we can test algorithms against the data from previous runs all while sitting on the couch, pretty cool, huh?

Next week's gonna be a busy one, hopefully we'll have lots to share with you,

See you next week,

\- Mike & Alex