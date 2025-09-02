---
layout: post
title:  "Toshiba MW24FM3 S-Video Mod"
tags: crt mod svideo
---
Adding S-Video input to this CRT requires injecting the signal at the DVD player, as it outputs S-Video to the VCR PCB which is what handles displaying it on the screen.

![set](/assets/img/IMG_20241223_011025.jpg)

![composite](/assets/img/IMG_1195.JPG)
![s-video](/assets/img/IMG_1184.JPG)

Installing the mod is as follows:

1. Open the CRT and disassemble it so that you can pull out the VCR/DVD PCB case completely (see the disassembly pics near the bottom).
2. Drill a hole for the S-Video Jack and mount it to the case near the other AV jacks.
3. Remove the DVD player module so that you can access the bottom of the DVD player's PCB.
3. Remove components R8522 and R8523.
4. Solder wires to the single terminals of D8051 and D8052 that are long enough to reach the S-Video jack
5. Connect the wire from D8051 (Chroma input) to the S-Video input jack's Chroma (C) lead.
6. Connect the wire from D8052 (Luma Input) to the S-Video input jacks Luma (Y) lead.
7. Solder a wire to ground, either directly to the chassis or find a ground on the PCB to solder to.
8. Connect the ground wire to the ground of the S-Video jack.
9. Reinstall the DVD player module.

That's it. You don't need to 75ohm terminate the signals because the VCR PCB where the signal is injected already has termination resistors.

Now turn on the CRT and switch to the DVD player, you should see whatever S-Video signal you are injecting instead of the usual DVD menu.

If you want to preserve the DVD player functionality:
1. Solder wires to the pads of the resistors you removed (the side that is not connected to your new input wires) solder the resistors you removed inline, and connect the ends to one side of a DPDT switch
2. Solder the two wires you soldered to the single leads of D8051 and D8052 (the C IN and Y IN wires) to the center of the DPDT switch
3. Solder the S-Video C and Y wires to the other side of the DPDT switch

And you now have a toggle for switching between the DVD player and the S-Video input. Make sure that Y connects to Y and C connects to C on the DPDT switch, and that you soldered the correct resistors inline with the wires that provide the DVD video signal. Refer to the diagram if you don't remember which is which.

![schematic](/assets/img/MW24FM3_SM_TOSHIBA_EN_0079.jpg)
![schematic](/assets/img/MW24FM3_SM_TOSHIBA_EN_0070.jpg)

A simplified schematic of the S-Video mod.

![back](/assets/img/IMG_20241222_153827.jpg)
![inside back](/assets/img/IMG_20241222_225620.jpg)
![overhead](/assets/img/IMG_20241222_225650.jpg)
![DVD closeup](/assets/img/IMG_20241222_225704.jpg)

This article is also hosted on https://electron.sunthar.com/manadream/product/toshiba-mw24fm3-s-video-mod