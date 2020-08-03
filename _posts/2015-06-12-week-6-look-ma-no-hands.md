---
layout: post
title: Look Ma, No Hands
excerpt: There was very little left to do before we could take our golf cart out for its first autonomous drive
headerImage: imgs/robo-rio_cover.jpg
headerColor: white
headerHeight: auto
---

With all our sensors mounted last week and our steering system in the works, there was very little left to do before we could take our golf cart out for its first autonomous drive.

Mike started the week by finishing and mounting the steering system permanently on the inside of the golf cart.  The main aluminum plate frame of the steering system is mounted to the frame of the golf cart via a set of high force screw clamps similar to that of the sensor tray, but with heavier duty steel components to withstand ever more screw torque and therefore clamping force.  Mounting proved to be quite difficult given the working space constraints but after climbing under the front of the cart and screwing down bolts a 1/6th of a turn at a time, it was finally mounted.

![The mounted steering system](imgs/steering_mounted.jpg)

With the steering system mounted, it was time to start working on all of our electronics systems as well as safety cut-offs in the event of failure.

Being an autonomously driving vehicle, for the most part, the computer, the micro controller and the motor controllers will have full control over all of the functions of the golf cart.  This includes the steering, the throttle and the brakes.  In order to stay safe, we needed to implement some form of override to disable the computers control of the golf cart in a moments notice.  To achieve this, Mike set up an inductive sensor to monitor the position of the brake pedal.  When the computer controls the brake, rather than pressing down on the pedal as a human would, the motor to pull the brake lever is situated closer to the actual brake itself and as a result, when activated, the brake pedal does not move.  This means that the only time that the brake should be pressed is when the driver deems the situation unsafe to proceed.  When the brake pedal is pressed, the connection to the inductive switch is broken, and through a set of electromechanical switches called relays, the connection from the computer the the motors is broken causing the computer to loose control of the golf cart.  Below is a video of this switch. if you listen closely, you can hear the relay switching back and forth when the pedal is pressed.

<iframe width="560" height="315" src="https://www.youtube.com/embed/cH59rFDirSA" frameborder="0" allowfullscreen></iframe>

In addition to this inductive switch, Mike mounted an e-stop to the roof of the golf cart.  This switch is electronically coupled to the inductive switch so that if either of the two are activated, the computer looses control of the golf cart.

![Picture of the e-stop](imgs/e-stop.jpg)

One last level of safety ended up being a bit of an accident but will serve as a final level of safety in the event of a failure with the relays.  Before deciding on a motor and gear ratio for the steering system, we conducted tests to see what a reasonable amount of force a human could produce if they needed to overpower the steering motor and steer the golf cart while the computer had control.  With these numbers, we made sure that in an emergency the driver could steer the golf cart out of trouble against the will of the computer.  By accident however, after about 4 seconds of fighting the steering motor, the brakers which were added to save the electronics in the event of a short circuit, trip and disable power to the steering motor controller and the micro controller which interacts with all three golf cart functions fully disabling computer control.

By the end of the weekend, the electrical system looked like this

![The electrical system](imgs/robo-rio.jpg)

The main board in the middle is a national instruments Robo-Rio another throwback to our FRC roots.  This controller is a repackaged version of NI's My-Rio which was designed for use in FRC and has a couple nice safety features in the event of a computer crash or failure which will again disable autonomous control.  The Robo-Rio takes all of our sensor inputs and relays them to the PID algorithms running internally which in turn issue commands to the motor controllers and therefore the motors.  On the golf cart, there are only two motors that were added to control the functions of the golf cart, this includes the steering motor and the motor for the brake which we will talk about a little later in this blog.  The throttle is actually controlled electronically by the Robo-Rio to save unnecessary complication. Pictured below is the throttle pedal and as you may be able to see, the throttle pedal simply rotates a rotary sensor called a potentiometer which intern produces a voltage from 0v to 5v indicating the position of the pedal.

![Throttle Potentiometer](imgs/throttle_pedal.jpg)

In order to control the throttle, Mike simply cut the connection between the pedal and the motor controller allowing Alex to inject a fake voltage from 0v to 5v with the Robo-Rio to act like the throttle pedal.  This switch of control is caused by the same safety relays from before so that the computer again looses control when any of the safeties are activated.

With everything wired up an ready to go, it was time for our first autonomous drive!

While Mike was busy setting everything up Mechanically, Alex was busy getting all of the sensors and the Robo-Rio interfaced into ROS so that we could write some code to make the golf cart drive.  This week, most of the time at the beginning of the week was spent attempting to get a ROS connection established with the Robo-Rio, this proved to be quite a challenging task, but after some programming trickery Alex managed to establish a stable connection with the Robo-Rio where he could issue commands and receive information back from it.  With this set up, all of the ROS infrastructure was ready for Alex to begin writing our first real code for controlling the golf cart.

To start, Alex set up a capture program which grabs the GPS co-ordinates while manually driving a route.  Once the route is established, Alex created a program which instructs the golf cart to steer to the first recorded point along the desired route which is no closer than 3 meters away from the golf cart.  This angle is established based off the golf carts current heading (given to us via the positions of the two GPS antennas on the roof), our position and the angle toward the next point.  With a calibrated desired angle input of the front wheels, this causes the golf cart to follow along this cookie trail of points as if it was a wagon being pulled along by a 3 meter long handle.  After only a morning of coding this in, we were able to take our golf cart out for an autonomous ride for the first time!

<iframe width="560" height="315" src="https://www.youtube.com/embed/5C7a6d1mzYY" frameborder="0" allowfullscreen></iframe>

Mike was still in control of the golf carts throttle at this point, but it was the computer directing the golf cart to steer in a fixed route!

For the rest of the week, Mike was away as he flew back to Ontario to meet with family and friends for a few days while Alex continued to work on the programming behind this newly born vehicle.  After dropping Mike off at the Calgary airport, Alex visited Novatel who has their headquarters close by to pick up a new sensor that they donated and they even gave Alex an awesome tour of their manufacturing facilities!  The new sensor is an IMU or inertia measurement unit and it not only increases the accuracy of our GPS system from 8cm to 2.5cm, but it also gives us a higher refresh rate on the position of the golf cart (up to 200 hz) as well as holding onto the position of the golf cart to within 0.5m under a GPS outage of up to 5 seconds, a very useful and necessary feature when navigating under overhanging trees.   Before leaving, Mike manufactured and assembled a mount for the IMU where one of the GPS antennas was originally meant to go on the top of the sensor tray and Alex was able to mount it and integrate it into our system.  What an awesome addition it is!

![IMU](imgs/IMU.jpg)

The last thing to add to the list of things done this week, is the design and some of the manufacturing of the brake mechanism.  Pictured below, the brake is essentially just a motor and gearbox with a winch spool on the output shaft.  The idea is that by changing the voltage applied to the motor via a motor controller, we can change the linear force being applied to the rope which attaches to the existing brake system.  The main advantage to this design is that we are not influencing the safety and reliability of the existing mechanical brake at all so that if anything fails, the manual brake does not.

![brake_design](imgs/brake_design.JPG)

Hopefully by next week, we have enough ready to attempt to drive our route while monitoring our surroundings and stop if a basic object like a human is in the way!  Yet again, everyday at Varden Labs is even more exciting than the last

Until next week,

\- Mike and Alex
