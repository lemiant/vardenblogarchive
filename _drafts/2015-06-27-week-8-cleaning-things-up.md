---
layout: post
title: Cleaning Things Up
excerpt: We are extremely excited to have achieved our minimum viable product in such a short period of time.
headerImage: /blog/imgs/cleaned_up_large.jpg
headerColor: white
headerHeight: auto
---

This week, Mike started by finishing up the laptop tray.  There were a few parts still to make, a couple things left to pickup, but it wasn’t long before everything was mounted and working as expected.

![finished laptop tray](/blog/imgs/finished_golf_cart.jpg)

The next thing on the list of things to do requires a little bit of backstory. While testing and running on the various fields, we have experienced many LiDAR related random points and anomalies which pop up in the middle of no where. One specific anomaly which we call lasers we will talk about in another blog post specifically about it. The rest of them seem to be randomly distributed pointe that only appear for one frame and then disappear. Our best theory is that dust and bugs in the air are intersecting the lasers paths and cause them to appear as objects. This became a problem when the golf cart reports these as objects in its way and brakes momentarily before continuing as if nothing had happened. To solve this issue, we have talked about a few different algorithms which we are going to try in order to filter theses points.  One of these algorithms is shown in the photo below where red represents real points, and the white represents points that have been filtered.

![dust filter snapshot]()

One of the drawbacks of this specific algorithm is that points that live on their own but are actually objects such as leaves etc are filtered out too.  lucky, this does not cause any issues with object detection as we still have enough points to work with, but we do have plans to experiment with some other filtering techniques that are hopefully more reliable and filter out less real points.

While Alex was working on the filtering code, Mike spend some time tidying up the golf cart a bit.  All exposed wires were surrounded in wire wrap for looks and protection, the original plastic body of the golf cart was re-attached with minor modifications to accommodate all of our added frame, and a few components we rearranged to make the wiring cleaner and more contained.

![cleaned up golf cart]

The next item on the list was a tricky one.  Our LiDAR only gives us the coordinates of our surroundings relative to the sensor itself.  Unfortunately, as the sensor moves, we need to correct for this movement so that our map remains in an absolute frame relative to the earth.
// NovAtel to Velodyne


// Rebuild golf cart