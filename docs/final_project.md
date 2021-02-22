---
layout: default
---

# Final Project

## Concept

I have an air freshener at home that is no longer working. It has given a great service to make my room smell nice for a long time. I also have some spare spray cans left that I thought would be a waste to throw away.

So I was thinking how awesome it would be if I could make an air freshener to make use of the leftover spray cans I have lying around at home.

## Project Brief

Title: Automatic Air Freshener
Function: To dispense a spray of aromatic scent from a spray can every 90 minutes 
Features: Able to sense a hand to dispense a spray also

To help me manage and track the progress of my project, I decided to make a time table. I was given 4 weeks with 8 hours per week to spend on the project.

![](/images/a3/timetable.JPG)

## Research

Before I went into starting my project, I decided to do some research on what is needed. 

Rack and Pinion to push down on the nozzle. Here is one that I found on [thingiverse](https://www.thingiverse.com/thing:3170748).

![](/images/a12/pr0.jpg)

Servo Motor with enough torque to push the spray nozzle

![](/images/a12/pr1.jpg)

Ultrasonic Sensor to detect a hand 

![](/images/a12/pr2.jpg)

From my research, I found out the items I needed for my project

| Item        | Quantity    |
| ----------- | ----------- |
| Arduino Microcontroller | 1 |
| Servo Motor    | 1 |
| HC-SR04 Ultrasonic Sensor | 1 | 
| Acrylic | - |
| 3D Printed PLA | - |

## Design

Now that I have done my research, I start designing. 

### The Case

The design process for me was simple as all I needed was a case or a box to be able to enclose every other component. I first sketched the design and then used fusion 360 to model it.

I only have 2 designs that I came up with. This is the first one:

![](/images/a3/sketch-air.jpg)

The issue here is that the nozzle of the spray can is too far in which means that the mist will not be able to leave the enclosure. So I made a simple revision.

![](/images/a12/pr3.jpg)

This design takes into account the placement of the nozzle in the enclosure.

After being satisfied by the sketch, I then created a 3D model of it in Fusion 360. Here is how I did it in Fusion 360:

1 . I started by creating some parameters 

![](/images/a12/pr4.jpg)

2 . I created a new component and created a sketch of the left piece. I then extruded it

![](/images/a12/pr5.jpg)
![](/images/a12/pr6.jpg)

3 . I made a new component for the right piece and created a sketch, projecting the sketch made on the left side. I extruded it and moved it accordingly

![](/images/a12/pr7.jpg)
![](/images/a12/pr8.jpg)

4 . I made another component for the base, created a sketch and extruded it. Then I used the combine tool. 

![](/images/a12/pr9.jpg)
![](/images/a12/pr10.jpg)

5 . I made a new component for the front pieces, created a sketch, extruded and combined them

![](/images/a12/pr11.jpg)

6 . I then made a new component for the back piece, sketced, extruded and combined it.

![](/images/a12/pr12.jpg)

7 . I then created a component for the top piece, projected the sketch made for the base and then extruded and combined it.

![](/images/a12/pr13.jpg)

8 . I then created 3 new components for the remaining 3 front pieces, created the sketches, extruded and combined them.

![](/images/a12/pr14.jpg)

The case is now done!

### Rack and Pinion
As I mentioned earlier, I need to use a rack and pinion system to push down in the nozzle of the spray. I downloaded the design from thingiverse and modified it to make it more suitable for my use case. I inserted the STL files into Fusion 360 and then started to modify them.

Firstly, I modified the motor bracket to change the mounting system

![](/images/a12/pr15.jpg)
![](/images/a12/pr16.jpg)
Original design 
Modified design

Next, I modified the rack/pusher.

![](/images/a12/pr17.jpg)
![](/images/a12/pr18.jpg)
Original design 
Modified design 


## 3D Printing
The Rack and Pinion system require 3D printing so I first converted the 3D designs into STL files and inserted them into Ultimaker Cura to slice them. 

![](/images/a12/pr19.jpg)

Slicer settings:
1. Layer Height: 0.16mm
2. Generate Support Materials: Touching Buildplate
3. Support Pattern: Grid
4. Support Density: 15%
5. Infill Density: 20%
6. Infill Pattern: Grid
7. Speed: 50mm/s
8. Build Plate Adhesion: Skirt & Skirt Line Count: 3

Here are the results:

![](/images/a12/pr20.jpg)

The rack did take multiple tries and revisions as I had different designs.

![](/images/a12/pr21.jpg)

I did have a failed print for the motor bracket where the print became loose and moved off the bed while printing. 

![](/images/a12/pr22.jpg))


## Testing

Describe the testing process for the various sub-systems that make up your project and how you integrated the different sub-systems.

## Results

What result did you get from the full testing of your final project?

## Conclusion

What conclusions can you draw from your final project? What are the issues/problems encountered? How did you resolve them? What are the improvements that can be made to your project?

## Design files & Source Code

Include all original design files and source code for your project.
