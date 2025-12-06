---
layout: post
title:  "Toshiba MW24FM3 S-Video Mod"
tags: CRT
---
Adding S-Video input to this CRT requires injecting the signal at the DVD player, as it outputs S-Video to the VCR PCB which is what handles displaying it on the screen.

![set](/assets/img/IMG_20241223_011025.jpg)

![composite](/assets/img/IMG_1195.JPG)
![s-video](/assets/img/IMG_1184.JPG)

To preserve DVD player functionality, you will need some kind of DPDT switch. I used a push button switch made for guitar pedals but there are others.

Installing the mod (and preserving DVD player functionality) is as follows:

1. Open the CRT and disassemble it so that you can pull out the PCB case completely. Be sure to properly discharge the anode so you can take the anode off the tube.
2. Drill a hole for the S-Video Jack and mount it to the case near the other AV jacks.
3. Drill a hole for the DPDT Switch near the S-Video jack.
4. Remove the DVD player module so that you can access the bottom of the DVD player's PCB.
5. Remove components R8522 and R8523.
6. Solder a 75 Ohm resistor to the left pad of R8522 when viewing it with D8051 above it (see photo below)
7. Solder a 1K Ohm resistor to the left pad of R8523 when viewing it with D8052 above it (see photo below)
8. Solder wires that are long enough to reach the DPDT Switch to the single terminals of D8051 and D8052 (see photo below)
9. Solder wires that are long enough to reach the DPDT Switch to the ends of the two resistors you added (see photo below)
10. Reinstall the DVD player module.
11. Solder the wire from the 75 Ohm resistor you added to the DVD player (DVD Chroma output) to the leftmost bottom pin of the DPDT switch.
12. Solder the wire from the 1K Ohm resistor you added to the DVD player (DVD Luma output) to the rightmost bottom pin of the DPDT switch.
13. Solder the wire from D8051 (Chroma input) to the leftmost center pin of the DPDT switch. 
14. Solder the wire from D8052 (Luma Input) to the rightmost center pin of the DPDT switch. .
15. Solder a wire from the S-Video input jack's Chroma (C) lead to the leftmost top pin of the DPDT switch.
16. Solder a wire from the S-Video input jacks Luma (Y) lead lead to the rightmost top pin of the DPDT switch.
17. Solder a wire to ground, either directly to the chassis or find a ground on the PCB to solder to.
18. Connect the ground wire to the ground of the S-Video jack.
19. Solder a resistor that is around 83 Ohms (I used a 75 Ohm and a 10 Ohm in series) from ground to the S-Video Luma (Y) pin.

That's it. You don't need to 75ohm terminate the Chroma signal on the S-Video jack because the VCR PCB where the signal is injected already has termination resistors.

The reason an 83 Ohm resistor is used to terminate the Luma signal is because the VCR PCB has an 820 Ohm termination resistor on the Luma signal trace, and by having around 83 Ohms in parallel with that resistor we get a termination resistance of around 75 Ohms when the S-Video input is used. The DVD player expects 820 Ohm termination and not 75 Ohm termination for Luma, so we can't just replace the 820 Ohm resistor with a 75 Ohm. Plus this makes it so we don't have to take the VCR PCB out at all.

Now turn on the CRT and switch to the DVD player using the remote or the buttons on the TV, you should see either the DVD menu or the S-Video signal you are injecting. Toggle the DPDT switch in the back to change which source you see when in the DVD mode of the TV.

If you don't want to preserve the DVD player functionality, you can simply connect the wires from D8051 and D8052 straight to the S-Video connector instead of to the center of the DPDT switch, and you also don't need to add the resistors to the DVD PCB.

![schematic](/assets/img/MW24FM3_SM_TOSHIBA_EN_0079.jpg)
![schematic](/assets/img/MW24FM3_SM_TOSHIBA_EN_0070.jpg)

![example soldering job](/assets/img/IMG_20251206_023658.jpg)

![inside back](/assets/img/IMG_20251206_023918.jpg)

![back](/assets/img/IMG_20241222_153827.jpg)

![anode cap removed](/assets/img/IMG_20241222_224857.jpg)

![PCB case](/assets/img/IMG_20241222_225232.jpg)

![overhead](/assets/img/IMG_20241222_225650.jpg)

![DVD closeup](/assets/img/IMG_20241222_225704.jpg)

This article is also hosted on [Sunthar.com](https://electron.sunthar.com/manadream/product/toshiba-mw24fm3-s-video-mod)