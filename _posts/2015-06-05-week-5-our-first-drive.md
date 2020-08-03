---
layout: post
title: Our First Drive
excerpt: All the sensors are running, so we took the cart out for a drive
headerImage: imgs/pretty_cart.jpg
headerColor: white
headerHeight: auto
---

This week we started off working on our new roof. It's made of box-tube aluminum and adds a lot of rigidity to the top of the cart, which is important because that is where we're mounting the GPS antennas. Now we didn't want this to be just any boring grey roof, so we designed a roof decal to spice things up. We think you'll agree that it looks really good! (Shout out to Alex's sister, Syd, who pianted the whole thing).

![The new cart roof](imgs/roof.jpg)

We also mounted the GPS receiver module to the roof because well we can, and because GPS units love being upside down :).

![The ProPak6 hanging upside down](imgs/propak_upside_down.jpg)

For real though, it gives us a clear view to the diagnostics LEDs to make things easier for us when booting up and connecting to our Terrastar correction data.   

Next up was a lot of progress on the electrical system. All the systems on the cart are powered off the 4 12-volt batteries on our electric golf cart

![Picture of the batteries under the seat](imgs/batteries.jpg)

If you look closely in that photo you can see the main breakers for the autonomous systems. Since none of our systems run at the full 48 volts that the cart does each of them is hooked up to just one or two of the batteries. We tried to spread the systems across the batteries so no one battery gets more drained than the others.

The most used of all the breakers is the one running to the inverter. The inverter takes 24 volt DC power and converts it into standard household 110 volt AC power. This is great because it means we can plug many parts of our system dircetly into the inverter without any modifications (for example the laptop and the network switch). It's a bit of a nest of wires, but it works great, take a look:

![Inverter](imgs/inverter.jpg)

Since our GPS and our LiDAR are now mounted we got the chance to take the cart out for a drive on Monday, it was really cool watching the data stream past:

<iframe width="560" height="315" src="https://www.youtube.com/embed/MVqnN9qRX-M" frameborder="0" allowfullscreen></iframe>

This week Mike's been working a lot on building the steering mechanism. You saw the CAD last week, here's the real thing:

![Steering installed](imgs/steering.jpg)

Steering uses a couple of parts from our days in FIRST Robotics. It's powered by a Mini CIM motor running through a VexPRO versa-planetary gearbox finally going into a chain which transfers the motion to the steering column. To determine the current position of the wheel we  are using a simple potentiometer (a common rotation sensor).

Alex also got a hold of his first autonomy book. While a lot of the strategies we're using on this vehicle are entirely our own inventions, we want make sure we're drawing on the best practices that have already been established. No need to reinvent the wheel as they say.

![Autonomous Mobile Robots by Roland Seigwart](imgs/autonomous_mobile_robots.jpg)

Next week the cart will hopefully steer itself for the very first time, these are exciting days in the world of Varden Labs,

Until then,

\- Mike and Alex