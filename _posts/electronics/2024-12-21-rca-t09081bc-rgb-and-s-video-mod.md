---
layout: post
title:  "RCA T09081BC - RGB and S-Video Mod"
tags: crt mod rgb svideo
---
This little 9" travel TV has a pretty good looking image, and modding it only makes it better. But is RGB better than S-Video and composite for this CRT? That's a matter of opinion, which you should decide for yourself.

![set](/assets/img/IMG_1106_edited.JPG)

![composite](/assets/img/IMG_1023_edited.JPG)
![s-video](/assets/img/IMG_1034_edited.JPG)
![rgb](/assets/img/IMG_1046_edited.JPG)

You can see in the comparison photos that S-Video is noticeably more crisp than composite, while still keeping the color blending that comes from running S-Video through the jungle chip's filters.

RGB on the other hand, is a bit brighter (I compensated for that in the pictures) and the color accuracy is better. You do lose some of the color blending that S-Video and Composite have, while getting the (perhaps) most crispy video.

I installed the RGB mod using Sunthar's guide, which you can see [here](https://sector.sunthar.com/guides/crt-rgb-mod/samsung-cxf0933.html) The guide is for a Samsung CRT, which this RCA is just a rebrand of the same model.

Using the schematic from [Sunthar's RGB Mod guide](https://sector.sunthar.com/guides/crt-rgb-mod/samsung-cxf0933.html), I made this simple mod that can toggle between S-Video and composite:
1. Lift pin 45 of the jungle chip (Toshiba TA1201AN)
2. Solder a wire to pin 45 and solder the other end to the center pin of a SPDT switch
3. Solder a wire to the via left open from lifting pin 45 and solder the other end of that wire to one of the pins on the SPDT switch
4. Prepare your S-Video jack by connecting pins 1 and 2 to ground (there are various grounds in the CRT, but the easiest is probably the ground of the stock composite input jack)
5. Solder a 75ohm resistor between pin 1 or 2 (ground) and pin 4 (chroma) of the S-Video jack
6. Solder a wire connecting pin 3 (luma) of the S-Video jack to the center pin (not ground) of the stock composite input jack.
7. Solder a wire connecting pin 4 (chroma) of the S-Video jack to the last pin on the SPDT switch.

And that's it! You can now use S-Video on this CRT as well as composite.

![schematic](/assets/img/S-Video%20Mod_schem.png)

A simplified schematic of the S-Video mod.

![super mario world](/assets/img/IMG_20250710_140952.jpg)

![side panel](/assets/img/IMG_1007.JPG)

A custom 3D-printed AV panel. The green switch is for turning on and off RGB input and the silver switch is for selecting S-Video or Composite. Print file available [here](https://www.printables.com/model/1116782-rca-t09081bc-t09082-samsung-cxf0933-av-side-panel)

![back](/assets/img/IMG_1025.JPG)
![front](/assets/img/IMG_1031.JPG)

![jungle chip](/assets/img/IMG_20241221_124912.jpg)

Jungle chip showing S-Video mod wires. The white wire is soldered to the via that pin 45 was connected to and the yellow wire is soldered to the lifted pin 45. Hot glue was used as a strain relief.

![insides](/assets/img/IMG_20250710_140341.jpg)

![rgb injection points](/assets/img/IMG_20250710_140348.jpg)

RGB injection points

![OSD chip](/assets/img/IMG_20250710_140358.jpg)

The OSD chip.

This article is also hosted on [Sunthar.com](https://electron.sunthar.com/manadream/product/rca-t09081bc---rgb-and-s-video-mod)