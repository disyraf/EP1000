---
default: layout
---

# 3D Printing

## What is 3D printing?

3D printing is a new revolution in the manufacturing industry as it allows manufacturing to be placed in the hands of common people like you and I. 3D printing is yet to be used as a permanant technique and it is nowhere near in replacing the current methods of manufacturing. 3D printing, however, has a number of benefits and advantages and they are;

* It places manufacturing in the hands of the public
* Able to create almost anything
* Ideal for rapid prototyping
* It is relatively affordable 

However, there are also disadvantages with 3D printing;

* 3D printing is a slow process
* Limited materials - strength affected
* Restricted build size

In my case, I am going to be using the Ultimaker 2+ 3D printer that is available in the SP FabLab

## 3D Printing Exercise: Knight Chess Piece

I am going to design a knight chess piece model and 3D print it. Here is the model that I designed:

![](images/a9/p1.jpg)

Here are the steps I took to get the final design:

1. Find an image of a knight chess piece head to use a a canvas & resize the image 
2. Sketch the outline of the image
3. Extrude the head of the knight 
4. Sketch the base of the piece 
5. Use the revolution function to create the base and set the pivot accordingly
6. Modify the base of the piece and set an offset to make the base hollow

### Using Cura for 3D Printing

Ultimaker Cura is the software that I am going to use to as the slicer software 3D printing. A slicer converts the model you made to into layers but before you use a slicer software, you will need to export your model as an .STL file. Ultimaker Cura has some parameters that you can tune to get the best print. 

Here are the the values I set for the parameters:

* Layer Height: 0.25mm
* Infill Percentage: 5%
* Infill Pattern: Grid
* Generate Support: Checked
* Build Plate Adhesion: Skirt

This is the preview of the piece in Cura:

![](images/a9/p2.jpg)

Now, all that is left is to print it. The time taken to print the knight chess piece for me is 55 minutes. This is longer than expected but it is due to the piece being quite big and complex to make. 

Here is part of the process:

![](images/a9/p3.jpg)

![](images/a9/p4.jpg)

![](images/a9/p5.jpg)

This is what the final product looks like after removing most of the support pieces:

![](images/a9/p6.jpg)

## Why was I given this exercise?

There are multiple reasons why this assignment was given out. 

1. When designing the model, it uses most of the basic functions in <strong>Fusion 360</strong>. - Extrude, Revolve, Offset etc.
2. The design is complex where support pieces are needed
3. We are able to see how the 3D printer handle the settings of the parameters that we set earlier.
