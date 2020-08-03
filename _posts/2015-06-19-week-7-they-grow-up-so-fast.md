---
layout: post
title: They Grow Up So Fast
excerpt: We are extremely excited to have achieved our minimum viable product in such a short period of time.
headerImage: imgs/ground_segmentation_large.jpg
headerColor: white
headerHeight: auto
---

This weekend while Mike was still in Ontario Alex spent a lot of time working the programming of the golf cart. The first thing he did is connect the golf carts throttle to the roboRIO controller and get the golf cart to drive forward under computer control.  After a little bit of debugging and integrating a switch that was on the throttle pedal into out computer system, we were good to go.

Next was our first strategy to avoid running into stuff, ground segmentation. This works by looking at the data from our LiDAR scans and separating points into ground and obstacles. We divide the world into a grid of 0.5 meter squares and classify each square as ground or obstacle. Here's a picture of our ground segmentation code in action it shows the raw points from the LiDAR and the grid colored with: black = obstacle, white = ground, grey = unknown:

![screenshot of ground segmentation](imgs/ground_segmentation.jpg)

By being able to detect where obstacles are, all that is left to do is check that our route doesn't hit any obstacles. This is done by projecting a line of grid squares forward along our route and checking all of the grid squares around the line up to a specific radius to make sure that there are no objects both on our route and around it.  When an obstacle appears inside this projected route, the computer tells golf cart to stop.

As soon as Mike got back from Ontario, he got straight to work finishing machining assembling and mounting the brake.  Some of the parts had already been CNCed before Mike left, so it was only a matter of 24 hours before everything was assembled and the mounting process started.  What a process that was!

![Mike under the golf cart](imgs/installing_brake.jpg)

After climbing under the golf cart (it was quite the cozy place to be) the brake was installed and does it ever work great!  The brake doesn’t compromise any of the manual brakes working, so there is always a level of safety there.  In addition it has the ability to apply slightly more force than a human is capable of applying, so we will never be without the best brake possible. This was a fairly easy system to get integrated electrically and it operates much like the steering does so after about an hour of work on code, we had the computer controlling the brake.  Here is a picture of the mounted assembly.

![mounted brake](imgs/mounted_brake.jpg)

With the brake done, the last major mechanical sub-system was the laptop tray.  The laptop tray was partly designed on the plane to and from Ontario, and was finished up after the brake was completed.  The tray offers a place to store the laptop on the golf cart and uses standard drawer slides to give us a comfortable typing position while sitting on the seat, and a pushed forward position so that we can watch the screen while driving in the drivers seat.

![design of the laptop tray](imgs/laptop_tray_design.jpg)

Nearing the end of the week, we got a bunch of the laptop tray parts CNCed, bought all of the raw material to manually machine the rest of the parts, and ordered everything required from McMASTER-CARR.

![laptop tray parts](imgs/laptop_tray_parts.jpg)

We worked extremely hard this week. We mentioned last week that we might have a golf cart that stops for obstacles by the end of the week, and what better way to spend a Friday night here at Varden Labs than celebrating our accomplishment. Ladies and gentlemen, enjoy!

<iframe width="560" height="315" src="https://www.youtube.com/embed/1JJEkjLfsWA" frameborder="0" allowfullscreen></iframe>

We are extremely excited to have achieved our minimum viable product in such a short period of time. Over the next few weeks, we hope to both improve and work with what we now have to produce a vehicle capable of driving confidently amongst people and slow moving cars.  Additionally, we plan on now starting to reach out to companies in various target markets to setup demos and hopefully land an initial partnership deal to help expand our reach.

We hope that you are just as excited as we are,

See you next week,

Mike and Alex.
