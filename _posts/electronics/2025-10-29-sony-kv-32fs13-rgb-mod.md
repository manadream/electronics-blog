---
layout: post
title:  "Sony KV-32FS13 - RGB SCART Mod"
tags: CRT
---
This guide will cover how to RGB SCART mod the 32" Sony KV32-FS13. RGB Modding this CRT isn't too difficult, the hardest part is making the RGB SCART hole for the port imo.

![set](/assets/img/IMG_20251027_010053.jpg)

I installed the RGB mod using Sunthar's guide, which you can see [here](https://sector.sunthar.com/guides/crt-rgb-mod/sony-kv-32fs13.html) for additional references.

## Step 1: Remove/Replace components

Open up your CRT and pull out the PCB on the left side of the TV (There are 3 in total, the center main board, the left board, and a small power board on the right). You may need to unplug some connectors and pull the other two boards out in order to pull this board out.

On the bottom of this board, locate R086, R087 and R088 and remove them.

![remove resistors](/assets/img/IMG_20251026_200401.jpg)

Then locate the three jumper wires shown in the image below and remove them. They are just above the resistors you removed and are labelled on the top as JW341, JW342 and JW343.

![remove jumpers](/assets/img/IMG_20251026_201545.jpg)

Insert three 1N4148 diodes where those jumpers were removed. Make sure the cathode (the black line on the diode) is on the left side when reading the jumper labels on the top of the board, or on the side closest to the connector CN303.

![insert diodes](/assets/img/IMG_20251026_202140.jpg)

## Step 2: Connect Wires to go to SCART Port

As you can see in the previous image, we will be injecting the RGB and Blanking signals at the cathode sides of the diodes you inserted for RGB, and into the jumper wire for Blanking.

**IMPORTANT NOTE**: I highly recommend you use shielded cable for the RGB signals, otherwise you will most likely get a lot of noise in your RGB signals that will appear in the video on screen. It looks really bad, like there's moving noise across the screen. You can get shielded 3-wire cable on the internet pretty easily.

Connect RGB and Blanking leads from your shielded wire to the board as shown below.

![connect RGB and Blanking](/assets/img/IMG_20251029_162201.jpg)

Then connect the ground of your shielded wire to the anode side of D301 as shown below (or any suitable ground point).

![ground](/assets/img/IMG_20251029_162153.jpg)

Next, connect wires to the back of the S-Video input jack on the main, center board as shown below. Sync connects to the Y input of the S-Video jack, the other wire is for ground (if using the shielded cable ground this is not necessary but I used it anyway for an extra ground connection).

![sync](/assets/img/IMG_20251026_203529.jpg)

Then connect wires to the underside of the main board S-Video AV jack for your Left and Right Audio.

![audio](/assets/img/IMG_20251026_205233.jpg)

That's all the wires you'll need to connect to your SCART port.

## Step 3: Prepare your SCART Port

If you purchased a SCART port from Sunthar, you can follow the instructions on [his guide](https://sector.sunthar.com/guides/crt-rgb-mod/sony-kv-32fs13.html#step-3-build-your-mux-board) for this section.

CRT Database also has a [great guide](https://crtdatabase.com/modding/wiring-and-installing-a-scart-connector) on creating a clean SCART connector setup, so check that out as well for more info.

If you want to make your own, I used [this](https://www.aliexpress.us/item/3256807009901234.html) SCART female socket from AliExpress, which you can find elsewhere. The Ali listing calls it a `21 PINS CS Type Scart Female Socket Connector Jack Female PCB Mount 21 PIN SCART`

I then used some prototyping board I had laying around and broke a piece large enough to connect what I needed to it. You can also do this without a board, you'll just need to make sure to connect your components with enough support that they won't break off during use/install/movement.

Use the following diagram [made using Sunthar's mux calculator](https://sunthar.com/rgb-mux-calculator?data=eyJjciI6NTYwMCwiY2ciOjY4MCwidCI6NzUsImkiOjEwMDAsImJnIjoiIiwiYmkiOjEyMDAsImNzIjp0cnVlLCJ2cHAiOiIiLCJtb2RlIjoib3V0cHV0Vm9sdGFnZSIsImNiciI6MTAwMCwiY2JnIjozMzAwLCJjbiI6IkMzOTUsIEMzNTMsIEMzNTIiLCJjdiI6IjAuMDEiLCJvcCI6IjY0LDYzLDYyLDYxIiwianAiOiI0Myw0Miw0MSw0MCIsInJpIjoiUjAyNSxSMDI2LFIwMjcsUjAyOCIsImdpIjoiUjA4NixSMDg3LFIwODgsUjAwNCIsInJkIjp0cnVlLCJiZCI6dHJ1ZSwiaWQiOnRydWUsIm10IjpmYWxzZSwiZGkiOmZhbHNlLCJjaSI6ZmFsc2UsImJsIjpmYWxzZSwiY2wiOmZhbHNlLCJiZHAiOnRydWUsImJhbCI6ZmFsc2UsInJhbCI6dHJ1ZSwiYmluIjoiTE4wMDMiLCJ2IjowLjY5LCJvc2RfdiI6NSwibSI6IlNvbnkgS1YtMzJGUzEzIiwibyI6bnVsbCwiaiI6bnVsbCwiZGljIjp7ImM0IjowLjEsImM1IjowLjEsImM2IjowLjF9LCJyMTIiOjEwMDB9) to create your RGB SCART MUX.

![RGB MUX](/assets/img/RGB_MUX_Diagram_Sony_KV-32FS13.png)

TLDR info is:

- RGB inputs are 75 Ohm terminated then connect to your shielded RGB wires from earlier with 1K Ohm resistors.
- The Blanking input is connected to a 1N4148 diode, then a 1.0K-2.2K Ohm resistor to the blanking jumper from earlier (I used 1.2K Ohms but 1K works fine and Sunthar recommended 2.2K)
- Sync input is connected directly to the S-Video sync wire soldered earlier.
- Audio left and right are connected to the audio wires soldered earlier with 1K Ohm resistors inline.
- Ground is connected to ground through the Shielded RGB cable's ground, or through another ground, or both.
- MAKE SURE to connect your shielded cable's ground to the chassis and to the SCART port.

You can see how I made my SCART board in the image below.

![SCART MUX](/assets/img/IMG_20251029_162126.jpg)

That's all for the wiring, you should now test your work to ensure that it is all functioning properly.

## Step 4: Mounting the SCART port

I used a [3D-printed SCART port panel](https://www.printables.com/model/1446440-scart-female-connector-plate) to cover up any not-so-perfect cutting I did for the port.

To do the actual cutting I drew an outline of the port using the 3D-printed part and then used a dremel to cut the outline out. I then needed to use a razor blade to trim the plastic more until it fit snug. Then I drilled holes to screw into the port with using some screws I found that were the right size to thread into the plastic of the SCART port. You can see the final results below.

![SCART Port](/assets/img/IMG_20251027_124305.jpg)

And that's it for the mod! You'll need to be on the Video 1 input and the picture will appear when you plug in a console and turn it on. If you go to other video inputs when the SCART connected console is on, you will see a scrolling image because it is not getting sync since sync is tied to input 1. If you want SCART to be a different input you can wire Sync to that input.

![example](/assets/img/IMG_20251027_010443.jpg)
![example](/assets/img/IMG_20251027_010752.jpg)
![example](/assets/img/IMG_20251029_162744.jpg)
![example](/assets/img/IMG_20251029_162755.jpg)

This article is also hosted on [Sunthar.com](https://electron.sunthar.com/manadream/article/sony-kv-32fs13-rgb-scart-mod)

