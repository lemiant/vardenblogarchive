---
layout: post
title: The Cart Arrives
excerpt: Arrive in Calgary and straight to business. We bought a golf cart and had our first look at our new control system. There are a lot of aluminum chips in our future...
headerImage: /blog/imgs/golf_car_hill.jpg
headerColor: "#E2EAE3"
---

It's been a very productive first week of build. When we arrived in Calgary we immediately set to work getting our office set up. We have our very own workshop in the garage, complete with drill press, bandsaw, mill and lathe.

![Photo of the garage workshop](/blog/imgs/workshop.jpg)

The final key tool we needed was, of course, a whiteboard (despite all the fancy productivity tools out there, we still prefer a good whiteboard). For maximum productivity we got the biggest one we could find.

![Photo of the whiteboard](/blog/imgs/whiteboard.jpg)

With that settled we went out to go get ourselves a golf cart. We picked up a used electric Yamaha golf car on the cheap and, after trying it out for a bit, set about taking it apart:

![Photo of the golf cart in pieces](/blog/imgs/dissassembled_golf_cart.jpg)

The next few days were a blur of CADing, sourcing and machining. We've even got our first parts, straight from the CNCs:

![Photo of the pivots](/blog/imgs/pivots.jpg)

See if you can spot those parts in the screengrab below. It's is a picture of the assembly we're calling the "sensor tray". The sensor tray supports our LiDAR and GPS sensors on the front of the car. The parts in the photo are the pivots for the arms, which allow us to adjust the orientation of the sensors by sliding the mounitng points at the back up and down.

![Photo of CAD](/blog/imgs/sensor_tray.jpg)

While Mike was busy managing the fabrication Alex worked on getting the control system ready to roll. Happily we sourced most of our sensors last term while we were in school so we were able to hit the ground running. Alex installed Linux on our control computer (not as fun as it sounds :P) and connected up our LiDAR and GPS units. For this project we are using a framework known as ROS. ROS stands for [Robot Operating System](http://www.ros.org/), and is used as the base for many robotics projects from little class projects all the way up to startups like Cruise Automation which are leading the autonomous space. 

We wanted to share one really cool picture from this process. This shot was taken from the LiDAR sitting in the middle of the living room. It's a top down visualization of the data and you can clearly make out the 3d position of couches and other objects in the room.

![LiDAR output](/blog/imgs/living_room.jpg)

Next we will be starting assembly on some of the mechanisms and begining to try basic steering and object avoidance tasks in simulations.

We're also really excited about possibly bringing a big new sponsor on board, hopefully we'll be able to tell you more about that in our next update.

Happy trails,

\- Mike & Alex