---
layout: post
title:  "Sony KV-27V66 - RGB SCART Mod"
tags: CRT
---
This guide will cover how to RGB SCART mod the Sony KV-27V66. It will be necessary to remove or at least pull out the A board to do this mod.

![set](/assets/img/IMG_20260314_191057.jpg)

I installed the RGB mod using Sunthar's RGB MUX diagram and guide for the KV-27V42 (BA-4D Chassis) [here](https://sector.sunthar.com/guides/crt-rgb-mod/sony-kv-27v42.html). Though the way I installed the mod is slightly different than these guides.

## Step 1: Remove/Replace components

Open up your CRT and pull out the large PCB in the bottom center of the TV. You may have to unlatch some connectors to get the board loose, so take note of any that you do.

On the bottom of this board, locate R086, R087, R088 and remove them. They are located next to IC301 and IC001, to the left of IC001 and below on the right side of IC301 when reading the IC labels right side up. Sunthar's guide also has a pic of their location.

Then locate the resistors R025, R026 and R027. Lift the side of these resistors that is closest to IC301 (or opposite the side that is closes to IC001) and insert 1N4148 diodes into the holes the resistors were lifted from.

Be sure to insert the cathode (-) side of the diodes into the holes, leave some of this side of the diode exposed on top to solder RGB wires to, and solder them in place. Then, solder the other sides of the diodes to the lifted resistor legs.

![insert diodes and solder RGB wires](/assets/img/IMG_20260314_195245.jpg)

## Step 2: Connect Wires to go to SCART Port

RGB and Blanking wires will be soldered to the cathode (-) side of the diodes installed in the previous step. See the image above.

Connect Sync to the Y pin of the S-Video input connector. Connecting it here will prevent the picture from shifting like it would if Sync were going through the Comb filter by being connected to the composite input.

Connect the Left and Right audio wires to the negative (-) side of C256 and C257, respectively, on the main A board.

Connect ground (I used JW518) to the S-Video detect pin, which is the 4th pin from the left when viewing the S-Video connection to the A board from above with the connector facing you.

See the photos below for the wiring of these connections.

![Audio and Sync 1](/assets/img/IMG_20260314_195150.jpg)

![Audio and Sync 2](/assets/img/IMG_20260314_195207.jpg)

Connect the ground wire(s) from the mux board to any suitable ground point on board A (I used a jumper next to the IC302 label).

![ground](/assets/img/IMG_20260314_195230.jpg)

That's all the wires you'll need to connect to your SCART port.

## Step 3: Prepare your SCART Port

If you purchased a SCART port from Sunthar, you can follow the instructions on [his site](https://sector.sunthar.com/guides/crt-rgb-mod/sony-kv-27v42.html#step-5-build-your-mux-board) for this section.

CRT Database also has a [great guide](https://crtdatabase.com/modding/wiring-and-installing-a-scart-connector) on creating a clean SCART connector setup, so check that out as well for more info.

If you want to make your own, you can use [this](https://www.aliexpress.us/item/3256807009901234.html) SCART female socket from AliExpress, which you can find elsewhere. The Ali listing calls it a `21 PINS CS Type Scart Female Socket Connector Jack Female PCB Mount 21 PIN SCART`

Then you can use some prototyping board or solderable breadboard to hold the components. You can also do this without a board, you'll just need to make sure to connect your components with enough support that they won't break off during use/install/movement.

Use the following diagram [from Sunthar's page on another BA-4D set](https://sector.sunthar.com/guides/crt-rgb-mod/sony-kv-27v42.html#mux-diagram) to create your RGB SCART MUX.

![RGB MUX](/assets/img/kv-27s42-rgb-mux-diagram-ubBg0c7S.png)

TLDR info for making your own is:

- RGB inputs are 75 Ohm terminated then connect to your RGB wires from earlier with 1K Ohm resistors.
- The Blanking input is connected to a 1N4148 diode, then a 1K Ohm resistor to the blanking wire from earlier.
- Sync input is connected directly to the sync wire soldered earlier.
- Audio left and right are connected to the audio wires soldered earlier with 1K Ohm resistors inline.
- Ground is connected to the ground wires soldered earlier.

You can see an example "homemade" SCART mux below.

![SCART MUX](/assets/img/IMG_20251029_162126.jpg)

That's all for the wiring, you should now test your work to ensure that it is all functioning properly.

## Step 4: Mounting the SCART port

I used a [3D-printed SCART port panel](https://www.printables.com/model/1446440-scart-female-connector-plate) to cover up any not-so-perfect cutting I did for the port.

To do the actual cutting I drew an outline of the port using the 3D-printed part and then used a sharp razor blade box cutter to cut the outline out. Then I drilled holes to screw into the port using some screws I found that were the right size to thread into the plastic of the SCART port. You can see the final results below. I modified the SCART port cover a bit to extend over some exposed portions of the case because I cut a bit too much plastic off for the port location I chose.

![SCART Port](/assets/img/IMG_20260314_210513.jpg)

And that's it for the mod! The picture will appear on Video 1 or Video 2 when you plug in a console and turn it on.

![example](/assets/img/IMG_20260314_191057.jpg)
![example](/assets/img/IMG_20260314_191226.jpg)
![example](/assets/img/IMG_20260314_191019.jpg)
![example](/assets/img/IMG_20260314_190713.jpg)

This article is also hosted on [Sunthar.com](https://my.sunthar.com/manadream/article/sony-kv-27v66-rgb-scart-mod)

