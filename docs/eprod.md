---
layout: default
---

# Electronics Production

## Individual Assignment

Make an in-circuit programmer by milling and stuffing the PCB. In this case, the FTDI board was chosen to be milled out on the CNC machine.

## FTDI Board

| Board | Trace | Outline |
| ![](docs/images/a1/p1.png) | ![](docs/images/a1/p2.png) | ![](docs/images/a1/p3.png) |

## Creating gcode files

Before milling out the PCB design, we first need to create gcode files. This is so that the CNC machine is able to read the file and then mill out the board accordingly. In order to create gcode files from our image files, we use [mods](https://skeatz.github.io/mods/). 

1. Select "mill 2D PCB png" under open server programs 

![](docs/images/a1/p4.jpg)

2. Import image file (.png) 

![](docs/images/a1/p5.jpg)

3. Select PCB default "mill traces"

![](docs/images/a1/p6.jpg)

4. Set cutting and plunge speeds 

![](docs/images/a1/p7.jpg)

5. Check final perimeters and calculate to get gcode file

![](docs/images/a1/p8.jpg)

Now you have the gcode file for the PCB traces, repeat for outline but change PCB default to "mill outline". By doing so, the following perimeters have been adjusted:

1. Tool diameter: 0.8mm

2. Cut depth: 0.35mm

3. Maximum depth: 1.680mm

4. Offset: 1

![](docs/images/a1/p9.jpg) 

## Milling out the PCB

Now that we have the gcode files for the PCB, we can start to mill the PCB out.

Firstly, we have to put some double-sided tape onto the back of out copper board and stick it onto the sacrificial layer of wood. Make sure that the tape is covering as much surface as it can, this will prevent the board from moving freely when milling.

![](docs/images/a1/p10.jpg)

Secondly, we insert our selected mill bit into the spindle head and tighten it into place. 

Thirdly, we load up our gcode file on to the program of the CNC machine, and start the to zero the axes to our desired location, this will be the starting point of the milling job. To zero our X and Y axes, move the spindle head to our desired location, and press the zero icon on the software's interface. To zero our Z axis, we have to use the Z probe. We first align the mill bit in the center of the probe and then press the Z probe icon on the software, this will the move the spindle down and click the probe. Now, we have successfully completed zeroing our axes.

Lastly, we turn on the spindle and start milling. While waiting for the job to finish, we can use a vacuum to clean up the dust that the machine has made from cutting the material. 

![](docs/images/a1/p11.jpg)

Once the milling is done, we turn off the spindle, use the vacuum once again to clear up the dust made and remove the board. 

![](docs/images/a1/p12.jpg)

Now, you have a milled out PCB board. The next step is to clean out the burrs on the board, making the board much more smoother and also easier to solder on our components. 

