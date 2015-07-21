---
layout: post
title: Lots of random things over the past two weeks
excerpt: This week we are going to do things a little differently. Rather than just talking about this week alone, we are going to talk about the past two weeks together. So here we go.
headerImage: /blog/imgs/chilling_in_the_bed.jpg
headerColor: white
headerHeight: auto
---

This week we are going to do things a little differently. Rather than just talking about this week alone, we are going to talk about the past two weeks together. So here we go.

Lets start with the big and exciting news, we made it into the finals of the 25K VFF pitch competition! To give a little bit of background, the velocity program is a Waterloo based program designed for young startup companies. They have incubators for startups and offer money to them as well. Every 4 months, they give out $125,000 in prize money at their Velocity Fund Finals pitch competition. There are two levels of competition, the 5K competition featuring 3 prizes of 5K each, and the 25K competition featuring 4 prizes of 25K each in addition to a 10K prize awarded to the best hardware based company. After a 15 minute long interview with 4 judges, the 60+ applicants for the 25K competition were filtered down to the top 10 who will be competing on July 23rd in Waterloo, that means us too!  We are very excited and hope to bring back good news. Here is a photo of Alex pitching 4 months ago in the 5K competition, we unfortunately did not win anything.

![VFF5K](/blog/imgs/VFF5K.jpg)

In light of making it into VFF 25K finals, we figured that it was appropriate to get some shirts made up with our logo so that we can represent Varden Labs at events like this. Here is what the design looks like.

![t-shirt design](/blog/imgs/t-shirts.jpg)

Last blog we mentioned that we were starting to work on a new project, a wireless e-stop. The idea behind the wireless e-stop is that we can have the golf cart running safely without anyone inside as we have the ability to stop the golf cart by simply letting go of a deadman switch. Now we would like to go a bit in-depth and tell you how it works, but first a picture of the design so that you have an idea of what it looks like.

![wireless_e-stop design](/blog/imgs/wireless_e-stop_design.jpg)

A while ago we talked about how we are using a Robo-Rio computer to control the various functions of the golf cart. This controller was designed specifically to function for FIRST robotics. As a result, they added a bunch of safety functions that are designed to prevent first robotics robots from having control of their motors when they are "disabled". One of these safety features is that in order to "enable" the outputs of the Robo-Rio, it must first receive a specific packet of data every 20 milliseconds. Using various tools, we were able to reverse engineer their protocol and up until now, our laptop has been providing this "heartbeat" as we call it.

Inside the e-stop, there is a small micro-processor called the [Particle Core](https://store.particle.io) which communicates over WiFi to a router on the golf cart. When the button on the e-stop is pressed and held, the Core sends the correct heartbeat to the Robo-Rio over Wifi which enables the golf cart.  Also inside are the internals of an external battery pack designed to charge your phone, which can be recharged and provides power to the Core. We also packed a long-range antenna inside the unit which gives us more than enough range. Here is a picture of the finished product. It took a solid 16 hours of machining time for Mike to make the 4 parts required in addition to the 4 hours of time it took to make machining drawings.

![wireless_e-stop](/blog/imgs/wireless_e-stop.jpg)

The last piece of the e-stop puzzle has to do with how the golf cart stops when the heartbeat is killed. Normally, when the Robo-Rio is disabled, the golf cart will simply coast to a stop which takes a fair amount of time. To fix this, we discovered that if you flick the forward/reverse switch into reverse while driving, the golf carts controller starts an electrical regenerative brake which stops the vehicle in about twice the distance that the mechanical brake does. We hacked into the electrical system a little bit more, and now, when the Robo-Rio is disabled, the golf cart switches from forward to reverse via mechanical relays which slows the golf cart down to a stop. We have future plans to make the e-stop control the mechanical brake as well, but these are future additions that we will add down the road. Here is a photo of the new electrical system after all of the changes.

![new_electrical](/blog/imgs/new_electrical.jpg)

Moving on, one of the few other little things that were left to do mechanically was to mount wheel encoders to the back two wheels of the golf cart.  These encoders measure the rotation of the wheels and gives us the speed of the golf cart.  With this information, we created a cruise control algorithm that takes in a desired speed in meters per second and controls the golf carts speed to maintain that “setpoint” even when going up and down hills.

![encoders](/blog/imgs/encoders.jpg)

While Mike was busy building and programming the e-stop, Alex was hard at work adding features and fixing bugs on the golf cart's code.  One of the first feature additions was the ability to start autonomously driving from anywhere along a recorded route. The code will run along our path until it gets to a point close enough to the golf cart in front of the direction that it is facing and will start driving to there.  This also gave us the ability to prevent the golf cart from starting if it was too far away from the path or at too steep of an angle away from the path.  

Some other interesting features that were added include slowing down as the golf cart enters a corner. The idea here is that we keep centripetal acceleration (g force) constant as we go around a corner, which causes us to slow down more, the tighter the turn is.  

Also, as we speed up now, the range in front of us where we look for obstacles increases according the stopping distance at that speed. This way we both slow down gradually for obstacles that are in our way and slam on the brake when an obstacle jumps in front of the golf cart. 

One last added feature is that not only do we stop when obstacles are in our way, but we slow down as obstacles get closer and closer to the route in front of us. This means that when there are people near the path, we slow down so that we can stop quicker if they were to jump out in front of the vehicle.

In addition to these added features, a bunch of small bugs were fixed that caused the golf cart to stop for no reason.  This includes things like processes crashing, which caused exceptions to be thrown resulting in the golf cart hitting the brake.

With the completion of all of these additions and features, we thought it would be appropriate to go and try them all out on a more "road like" setting. About an hour east of Calgary, there is a go-cart track (Calgary cart racing club, North Star Track). We managed to convince them to let us go out there and test out golf cart out on their 1.2 km long track, so we packed out golf cart up and headed out on the golf carts first road trip!

![track_roadtrip](/blog/imgs/track_roadtrip.jpg)

We ran our golf cart for a couple hours, made a bunch of routes around the track and tested all of our features.  They all worked great!  In addition to running on the track, we set up a time next week where we could come back during the day and run for a few hours.  Once we had this date set up, we called CTV and they agreed to have a crew come out and record what we are doing!  In addition to CTV, we managed to convince Darren Harmon from [Forefront Video Tours](http://www.forefrontvideotours.com/#home) to come out and bring his quad-copter with an attached go-pro. By next week, we should get some awesome shots of our golf cart in action! Make sure to check that out!

We have a bunch of demos lined up for next week and we look forward to telling you guys all about them.

Until next week, 

Mike and Alex






