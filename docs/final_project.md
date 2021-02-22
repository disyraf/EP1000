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


| Original Design  | Modified Design |
| ----------- | ----------- |
| ![](/images/a12/pr15.jpg) | ![](/images/a12/pr16.jpg) |


Next, I modified the rack/pusher.

| Original Design  | Modified Design |
| ----------- | ----------- |
| ![](/images/a12/pr17.jpg) | ![](/images/a12/pr18.jpg) |


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

![](/images/a12/pr22.jpg)

I used super glue to bond the pinion gear to one of the attachments that was included with the servo motor.

![](/images/a12/pr23.jpg)
![](/images/a12/pr24.jpg)

## Laser Cutting

The case has to be laser cut, so I converted the sketches from fusion to DXF files. I then inserted them into AutoCad to position them.

![](/images/a12/pr25.jpg)

I used 3mm thick acrylic for the case and here are the pieces after laser cutting.

![](/images/a12/pr26.jpg)

I needed to make some more modifications to the pieces, the top piece and the front pieces. So, I use a drill, files and also used a saw to cut some these holes

![](/images/a12/pr27.jpg)

## Electronics

Electronics
When it comes to the electronics of my project, I used TinkerCad to virtually create and wire up my circuit to test it out. 

![](/images/a12/pr28.jpg)

After that, I wired up the circuit with the Arduino Uno and tested it physically. 

![](/images/a12/pr29.jpg)

Testing servo & rack and pinion: I programmed it such that the servo rotates the pinion gear back and forth.

{% include vid1.html %}

Testing Ultrasonic Sensor using a serial monitor 

![](/images/a12/pr30.jpg) 
{% include vid2.html %} 

Here is the code I wrote with reference to this [tutorial](https://dronebotworkshop.com/hc-sr04-ultrasonic-distance-sensor-arduino/) :

```
#include <Servo.h>
#define echoPin 3
#define trigPin 2
Servo myservo; 

long duration; 
int distance; 
int val;
int reset = 4;
int countdown = 90*60*1000; // 90mins

void setup() {
  digitalWrite(reset, HIGH);
  pinMode(reset, OUTPUT);
  myservo.attach(9);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT); 
  Serial.begin(9600);
  Serial.println("Ready");

  checkdistance();
  Serial.print("Distance = ");
  Serial.println(distance);

  myservo.write(180); // rack is pushed down
  delay(850);
  myservo.write(0); // rack is pulled back up
  delay(850);
  myservo.write(90); // servo is not moving
}

void checkdistance(){
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.034 / 2; 
}

void loop(){
  
  while(distance>7 && countdown!= 0){
  checkdistance();
  Serial.print("Distance = ");
  Serial.println(distance);
  
  if(distance<7){
    digitalWrite(reset, LOW);
  }
  countdown = countdown - 500;
  delay(500);
  }

  digitalWrite(reset, LOW);
  
}
```

How the code works:
1. Servo is activated when the program starts and countdown timer starts
2. While loop will actively check for distance and minus countdown timer
3. When distance is less than 7cm or when countdown timer has ended(countdown=0), program will restart to step 1

## Assembly

With all the testing being successful, it is now time to assemble all the pieces together. Assembly of the air freshener is pretty easy. The electronics does give a little bit of a challenge but here is how I put everything (almost everything) together. Do note that I have transferred all of the electronics from the Arduino Uno to the Arduino Nano in order to make it fit inside the enclosure.

1 . I peeled the adhesive behind the breadboard and attached it to the right piece of the case on the inside

![](/images/a12/pr31.jpg)

2 . Then I used M3 x 20 machince screws and nuts along with some spacers made from acrylic pieces to secure the rack & pinion system to the top piece

| ![](/images/a12/pr32.jpg) | ![](/images/a12/pr33.jpg) |

3 . The next step is to wire everything up and put the Ultrasonic Sensor in the hole made for it and put all the pieces together

| ![](/images/a12/pr34.jpg) | ![](/images/a12/pr35.jpg) | 

4 . That's it! It is now fully assembled!

| ![](/images/a12/pr37.jpg) | ![](/images/a12/pr38.jpg) | ![](/images/a12/pr39.jpg) | 

I ended up not being able to fit some of the pieces that I laser cut earlier. So these pieces were left out:

![](/images/a12/pr36.jpg) 


## Conclusion

In conclusion, the project turned out to be quite successful. There were some hiccups and the journey was not entirely smooth sailing. I ended up with a working project but it didn't look as planned with some of the pieces not being able to fit. However, I have learned quite a number of useful things along the way and there are some imporvements that I can make to make this project even better. 

1. I could have not used the rack & pinion system and instead made a simpler system that could push or pull down on the nozzle of the spray cannister.
2. The overall size and fit of the case is quite sloppy and could be imporved with some changes that can help with the tolerences, resulting in a better fit & finish and not forgetting reducing the overall size as well.
3. I could have not used the Ultrasonic Sensor as it is quite overkill for my use case. I could have went with a simple infrared sensor instead. 

## Presentation

![](/images/a12/auto_air_fresh.png)

## Video

 {% include vid3.html %} 

## Design files & Source Code

1. 
