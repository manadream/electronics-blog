---
layout: post
title:  "Notch and Comb Filter Comparison for Composite Video Decoding and Retro Gaming"
tags: Video
---
When it comes to Composite video, there are two means of decoding the analog video stream, Notch and Comb filtering.
This article will compare the two in the context of retro gaming by comparing several different external Notch and Comb filters.

This article has the following sections:

[Basic Composite Video Theory](#basic-composite-video-theory)

[Why Use Composite?](#why-use-composite)

[Aren't Comb Filters the Best Option?](#arent-comb-filters-the-best-option)

[Comb Filter Comparisons](#comb-filter-comparisons)

- [Extron YCS SW6 (3-line comb)](#extron-ycs-sw6-three-line-comb-filter)
- [Kramer VP-413 (3D comb)](#kramer-vp-413-3d-comb-filter)

[Notch Filter Comparisons](#notch-filter-comparisons)

- [Tributaries C2S](#tributaries-c2s)
- [Kramer 401D](#kramer-401d)
- [Extron VYC 100N](#extron-vyc-100n)
- [Entech CSVC-1](#entech-csvc-1)
- [manadream Notch Filter](#manadream-notch-filter)

[Side-By-Side Comparisons](#side-by-side-comparisons)

[Bonus Images](#bonus-images)

[References/Further Reading](#referencesfurther-reading)


## Basic Composite Video Theory

Composite video (the Yellow RCA connector on a console's AV cable) is constructed by overlaying separate Luma (brightness) and Chroma (color) signals on top of each other so that only one wire (aside from ground) is needed to transmit the video.
This is typically done inside a game console, which makes Composite video one of the output options the console has.

![Composite encoding](/assets/img/Ntsc_channel.png)

External Notch and Comb filters decode Composite video back into separate Luma and Chroma signals, typically known as S-Video.
Inside any CRT there is going to be an internal filter that does this for you when you plug Composite video into it.
Using an external filter takes this job away from the TV and allows you to choose the means and quality of this conversion.

![Composite decoding](/assets/img/ntscdb2fig2.png)

In order to use an external filter, the TV or Capture device you are connecting to needs to have S-Video input available. This is what that connector looks like:

![S-Video connector](/assets/img/S.video.socket.png)


## Why Use Composite?

A lot of people consider Composite video to be the worst option (aside from RF) when it comes to video output.
This is simply not true as Composite video offers some artistic benefits that other output options do not (including raw S-Video output from your console.)

[This Article by Eli Krause](https://crtdatabase.com/articles/art-design) goes into great detail on why Composite is the best video format for a lot of retro games, even into the PS1/Saturn/N64 era.
I highly recommend giving that article a read to better understand why Composite video is important.

The TL;DR of that article is, Composite video allows for blending of colors that are especially important for dithering (Sonic Waterfall and Streets of Rage 2 lamp lighting are classic examples).
It also allows for a wider range of colors than the console could normally create by using two different colors next to each other that get blended into a new color.

![Composite art example](/assets/img/CRT%20Art.png)


## Aren't Comb Filters the Best Option?

Comb filters are good for live video footage, but they are not good for retro gaming or computer visuals. Here's a few info-graphics that will explain why:

![Notch and Comb comparison from JVC](/assets/img/JVC%20Catalog%20Info.jpeg)

![Extron Comb chroma mesh failure](/assets/img/ExtronInfo.jpeg)

![Retro Tink on Notch](/assets/img/tinknote.jpeg)

Here's what that looks like in an actual game:

![Notch and Comb comparison](/assets/img/Example%202.jpg)

Notch filters do not exhibit this issue. This is often referred to as dot crawl, but the correct term is "hanging dots".

[Dot crawl](https://en.wikipedia.org/wiki/Dot_crawl) is an artifact of the Luma information being polluted by the Chroma signal, which looks like this:

![dot crawl](/assets/img/Crawl.jpg)

Another type of interference you will see is called "rainbowing" or "rainbow banding", which results from the Chroma information being polluted by the Luma signal.

![rainbow artifacts](/assets/img/Kramer%2008.png)

_**NOTE**: The amount of rainbow artifacts and dot crawl are also dependant on the console itself. A lot of stock Genesis consoles have bad rainbowing, but modding them can improve or eliminate it. 
The Wii has very good composite output, for example. How the picture looks depends on the encoding **AND** the decoding._

Both Comb filters and Notch filters will exhibit dot crawl and rainbow artifacts to varying degrees, this is the nature of Composite video.
The only way to not have these artifacts is to keep Chroma and Luma separate from the very beginning, but you then lose some of the artistic qualities that Composite offers.

The goal, then, is to use a filter that minimizes dot crawl and rainbow artifacts, and does not have hanging dots. This can only be done with a Notch filter, as you'll see.


## Comb Filter Comparisons

Comb filters work by splitting the Composite signal into Luma(Y) and Chroma (C) signals using delay lines and adding and subtracting multiple lines of video to extract the Y and C information. They are much more complex than notch filters, if you want to know more about how they work, check out [this article by Extron](https://www.extron.com/article/ntscdb3).

![comb filter diagram](/assets/img/comb_filter_diagram.png)

I purchased two different external comb filters to compare them to each other, and to the Notch filters later in this article.

All comparisons were done using an I-O DATA GV-USB2 S-Video capture device or an HDMI capture device with a VGA to HDMI adapter, and the following consoles' composite output:

- Sega Genesis Model 1 VA 6.5, recapped with no mods
- NES-001 Front Loader, recapped and modded with Lava RGB v1
- SNES SHVC-CPU-01, recapped with no mods
- N64 NUS-CPU-04, recapped with no mods

All 240p Test Suite images are from the Sega Genesis. This console has some jailbars and pretty bad rainbowing, so the video isn't the best, but I think it is a good test because it shows how well different filters handle the imperfect video, plus this is what most stock Genesis consoles are going to look like.


### Extron YCS SW6 (Three-Line Comb Filter)

![YCS SW6](/assets/img/ycssw6mx-lg.jpg)

I bought this on Ebay for $34. You may be asking, why buy a video switcher for this test? Well this particular video switcher has a built-in 3-line comb filter made by Extron. So it can switch between video sources and also convert them to S-Video using the built in comb filter. It has 6 composite BNC inputs and can output composite, or S-Video using the comb filter (which is what I used).

![240p Menu](/assets/img/ExtronYCSSW6%2007.png)
![SMTP Color Bars](/assets/img/ExtronYCSSW6%2006.png)
![240p Girl](/assets/img/ExtronYCSSW6%2005.png)
![SoR2](/assets/img/ExtronYCSSW6%2004.png)
![Sonic](/assets/img/ExtronYCSSW6%2008.png)
![Mario 64](/assets/img/ExtronYCSSW6%2003.png)
![SMW](/assets/img/ExtronYCSSW6%2002.png)
![Duck Tales](/assets/img/ExtronYCSSW6%2001.png)

For whatever reason, this filter had a lot of noise in the Chroma signal, which you can see as horizontal sections looking off-color. I did what I could to reduce noise as much as possible, but this unit might have something wrong with it.

If you ignore that oddity, you can see the kinds of horizontal dot artifacts combs have, hanging dots, very clearly in:

- The Streets of Rage 2 screenshot along the top of the fence and the bottom of the windows and the top of the bricks.
- The top and bottom of the red letters in the 240p test suite.
- The railing and large star door in Mario 64.
- The top and bottom lines of text and graphics in Super Mario World
- The text in Duck Tales

Lots of CRTs have 2-line and 3-line comb filters built into them, so the picture will look something like this (minus the weird color banding).


### Kramer VP-413 (3D Comb Filter)

![VP-413](/assets/img/IMG_20251204_123442.jpg)

I bought this on Ebay for $27. It converts Composite to VGA using a very sophisticated 3D comb filter which represents the most advanced type of comb filters available. As you will see, it has some of the same problems as the 3-Line comb above, but not as badly.

One thing to note is that sophisticated comb filters like this one can also revert to a Notch filter if the hardware decides that would be better for whatever reason it's programmed to. That seems to be the case with Sega Genesis video content for some reason. So the screenshots of Genesis games will look more like what a Notch filter would, although the notch in this device is pretty bad and has a lot of rainbowing, as you'll see.

![240p Menu](/assets/img/Kramer%20VP-413%2007.png)
![SMTP Color Bars](/assets/img/Kramer%20VP-413%2006.png)
![240p Girl](/assets/img/Kramer%20VP-413%2005.png)
![SoR2](/assets/img/Kramer%20VP-413%2004.png)
![Sonic](/assets/img/Kramer%20VP-413%2008.png)
![Mario 64](/assets/img/Kramer%20VP-413%2003.png)
![SMW](/assets/img/Kramer%20VP-413%2002.png)
![Duck Tales](/assets/img/Kramer%20VP-413%2001.png)

As you can see, the Genesis content has a lot of rainbowing and does not demonstrate hanging dots like the N64, SNES and NES. This is why I say it is reverting to a notch for that video content as notch filters do not exhibit hanging dots (they do exhibit other dot artifacts that are common to both notch and comb filters, as you'll see).

You can see clearly the presence of typical comb hanging dot artifacts in:

- The railing, large star door, some parts of the Sun floor pattern, and the top of the coins in Mario 64.
- The top and bottom of the text in Duck Tales.
- The top and bottom lines of the border graphic in Super Mario World.

It does do a better job than the 3-line comb, but it still has dot artifacts that all comb filters have.


## Notch Filter Comparisons

Notch filters work by splitting the Composite vide signal into Luma (Y) and Chroma (C) signals using a band-stop filter (also called a notch filter) for the Luma part of the signal and a band-pass filter for the Chroma part of the signal.

![notch filter diagram](/assets/img/ntscdb2fig2.png)

[This article by Eli Krause](https://crtdatabase.com/articles/decoding-240p) goes into detail explaining how this works, as well as how comb filters work and the technical differences. It is a relatively short and informative read which I recommend checking out if you want to understand better what is going on with these filters.

I purchased 4 different notch filters to compare to each other, and to [the one I have made](https://manadream.shop/product/notch-filter-composite-to-s-video-converter). I will go over each one and talk about how they compare to each other.

All comparisons were done using an I-O DATA GV-USB2 S-Video capture device and the following consoles' composite output:

- Sega Genesis Model 1 VA 6.5, recapped with no mods
- NES-001 Front Loader, recapped and modded with Lava RGB v1
- SNES SHVC-CPU-01, recapped with no mods
- N64 NUS-CPU-04, recapped with no mods

Again, the 240p Test Suite images are from the Sega Genesis. This console has some jailbars and pretty bad rainbowing, so the video isn't the best, but I think it is a good test because it shows how well different filters handle the imperfect video, plus this is what most stock Genesis consoles are going to look like.


### Tributaries C2S

![C2S](/assets/img/Tributaries.jpg)

I bought this on eBay for about $30, but I'm not sure how easy they are to find.

![240p Menu](/assets/img/Tributaries%2007.png)
![SMTP Color Bars](/assets/img/Tributaries%2006.png)
![240p Girl](/assets/img/Tributaries%2005.png)
![SoR2](/assets/img/Tributaries%2004.png)
![Sonic](/assets/img/Tributaries%2008.png)
![Mario 64](/assets/img/Tributaries%2003.png)
![SMW](/assets/img/Tributaries%2002.png)
![Duck Tales](/assets/img/Tributaries%2001.png)

It has noticeable ghosting/echoing which is very obvious on the right side of Mario's hat in the Mario 64 pic.
It also has a lot of dot crawl, so I don't recommend it.


### Kramer 401D

![401D](/assets/img/Kramer.jpg)

I got this one as a gift, but it looks like they can go for around $15-$90 on eBay. It has a BNC connector for Composite video.

![240p Menu](/assets/img/Kramer%2007.png)
![SMTP Color Bars](/assets/img/Kramer%2006.png)
![240p Girl](/assets/img/Kramer%2005.png)
![SoR2](/assets/img/Kramer%2004.png)
![Sonic](/assets/img/Kramer%2008.png)
![Mario 64](/assets/img/Kramer%2003.png)
![SMW](/assets/img/Kramer%2002.png)
![Duck Tales](/assets/img/Kramer%2001.png)

The dot crawl on this one is very bad, especially on Duck Tales. It doesn't have as much ghosting/echoing as the Tributaries though.


### Extron VYC 100N

![VYC 100N](/assets/img/Extron.jpg)

I purchased this one for about $30 on eBay, there are quite a few of these available on eBay. 
It has a BNC connector for Composite video, and two BNC connectors for S-Video in addition to the standard 4-pin S-Video connector.

![240p Menu](/assets/img/Extron%2007.png)
![SMTP Color Bars](/assets/img/Extron%2006.png)
![240p Girl](/assets/img/Extron%2005.png)
![SoR2](/assets/img/Extron%2004.png)
![Sonic](/assets/img/Extron%2008.png)
![Mario 64](/assets/img/Extron%2003.png)
![SMW](/assets/img/Extron%2002.png)
![Duck Tales](/assets/img/Extron%2001.png)

The dot crawl on this one is better than the Tributaries and the Kramer, though the rainbow artifacts are about the same (which you can see on the left side of the white text in the SMW screens and in the Sonic image).


### Entech CSVC-1

![CSVC-1](/assets/img/Entech.jpg)

Thanks to kitty666cats/Mike Lindquist, a fellow member of the CRT community, I got this one for about $30 [on eBay](https://www.ebay.com/itm/227126035252). It has a male RCA connector, so I had to use a coupler to connect it to the male RCA connectors from my consoles.

![240p Menu](/assets/img/Entech%2007.png)
![SMTP Color Bars](/assets/img/Entech%2006.png)
![240p Girl](/assets/img/Entech%2005.png)
![SoR2](/assets/img/Entech%2004.png)
![Sonic](/assets/img/Entech%2008.png)
![Mario 64](/assets/img/Entech%2003.png)
![SMW](/assets/img/Entech%2002.png)
![Duck Tales](/assets/img/Entech%2001.png)

This one has less dot crawl and rainbow artifacts than the Tributaries, Kramer and Extron. It still exhibits a fair bit of dot crawl on NES games however.


### manadream Notch Filter

![manadream notch filter](/assets/img/manadream.jpg)

Full disclosure, I designed this filter myself with the goal of being better for retro gaming than anything available on the market.
I believe I have accomplished this goal, but you can decide for yourself.

This filter comes with a knob that lets you adjust the strength of the filter, and thus the sharpness of the picture.
It is the nature of a notch filter that the stronger it is, the more frequencies it will cut from the Luma signal, and thus the more blending there will be.
The goal is to dial it in for your specific TV set to get the sharpest image possible that also does not have dot artifacts.

These images are all captured with the sharpness knob at maximum sharpness.

![240p Menu](/assets/img/manadream%20max%20sharp%2007.png)
![SMTP Color Bars](/assets/img/manadream%20max%20sharp%2006.png)
![240p Girl](/assets/img/manadream%20max%20sharp%2005.png)
![SoR2](/assets/img/manadream%20max%20sharp%2004.png)
![Sonic](/assets/img/manadream%20max%20sharp%2008.png)
![Mario 64](/assets/img/manadream%20max%20sharp%2003.png)
![SMW](/assets/img/manadream%20max%20sharp%2002.png)
![Duck Tales](/assets/img/manadream%20max%20sharp%2001.png)

It's very similar to the Entech filter, though with more vibrant colors and slightly less dot crawl and less ghosting.

But if we sacrifice just a little bit of sharpness, we can eliminate a lot of it.

These images were captured with the sharpness knob at 75% of max sharpness.

![240p Menu](/assets/img/manadream%20less%20sharp%2007.png)
![SMTP Color Bars](/assets/img/manadream%20less%20sharp%2006.png)
![240p Girl](/assets/img/manadream%20less%20sharp%2005.png)
![SoR2](/assets/img/manadream%20less%20sharp%2004.png)
![Sonic](/assets/img/manadream%20less%20sharp%2008.png)
![Mario 64](/assets/img/manadream%20less%20sharp%2003.png)
![SMW](/assets/img/manadream%20less%20sharp%2002.png)
![Duck Tales](/assets/img/manadream%20less%20sharp%2001.png)

As you can see, the dot crawl is significantly reduced. It can be reduced even further by lowering the sharpness more.

On a CRT, the visible sharpness difference between 100% sharp and 75% sharp is going to be barely noticeable, especially from a normal viewing distance.

Having this sharpness knob allows you to dial in the sharpness vs dot artifacts to your preference.

The way these results are achieved is by having multiple stages of filtering in addition to video amplification.

The manadream Notch Filter is a proper, 75-ohm input terminated, 75-ohm output impedance video filter and amplifier for NTSC composite video.
You'll notice more vibrant colors and a brighter picture than other filters using this filter.

The manadream Notch Filter is available for purchase [on my store](https://manadream.shop/product/notch-filter-composite-to-s-video-converter). I also sell other retro gaming products and modding services, let me know if there's something you'd like that I don't have listed!


## Side-By-Side Comparisons

Here are some of these filters compared side-by-side. I have chosen the images that show the differences most clearly.


### Notch Side-By-Sides

![Side by Side 1](/assets/img/Side%20By%20Side%2001.png)

![Side by Side 2](/assets/img/Side%20By%20Side%2002.png)

![Side by Side 3](/assets/img/Side%20By%20Side%2003.png)

![Side by Side 4](/assets/img/Side%20By%20Side%2004.png)


### Comb and Notch Side-By-Sides

![Side by Side 5](/assets/img/Side%20By%20Side%2005.png)

![Side by Side 6](/assets/img/Side%20By%20Side%2006.png)

![Side by Side 7](/assets/img/Side%20By%20Side%2007.png)

![Side by Side 8](/assets/img/Side%20By%20Side%2008.png)


## Bonus Images

These are some images/comparisons that were provided to me by others and/or are on CRTs instead of direct captures.
I'm showing them here to further demonstrate the difference between Comb filters and Notch filters in general.

Comb filter dot artifacts on a PVM, you can see it in the red squares on the bottom very clearly (might need to open the image in a new tab and zoom in):

![PVM artifacts](/assets/img/IMG_20251205_000357.jpg)


Comb dot artifacts on an RCA set:

![RCA dot artifacts](/assets/img/IMG_20251124_202230.jpg)


Comb dot artifacts on a Sony Trinitron, visible in the red text:

![Trinitron dot artifacts](/assets/img/IMG_20251202_013223.jpg)


Streets of Rage 2 on a CRT:

![SoR2 1](/assets/img/Example%201.jpg)

![SoR2 2](/assets/img/Example%202.jpg)

![SoR2 3](/assets/img/Example%203.jpg)


An example of a really bad external Notch (in one of those tiny, inline adapters) not removing Chroma information from Luma, on a CRT:

![bad notch adapter](/assets/img/comp2svidbad.jpg)

![bad notch](/assets/img/CRT%20Cheapo%20CV2.jpg)


An example of a typical 2-line comb filter on a CRT (notice the hanging dots):

![typical 2-line comb](/assets/img/CRT%20Comb%20CV2.jpg)


The comb on my Toshiba MW24FM3 CRT (again, notice the hanging dots):

![toshiba comb](/assets/img/IMG_20250920_142259.jpg)


A mediocre comb on an LCD:

![lcd comb](/assets/img/LCD%20Comb%20CV2.jpg)


Comb (Top) vs. Notch (bottom) on Castlevania 2's title screen text:

![CV2 Comb Notch](/assets/img/signal-2025-08-21-10-14-19-560.jpg)


The notch filter on a RetroTink 5x on an LCD:

![RetroTink Notch](/assets/img/tink%20notch.jpg)


And that's all I got!

I hope this article was helpful. Feel free to [contact me](http://manadream.blog/about/) if you have any questions or suggestions for how to improve this article for others, and [go to my shop](https://manadream.shop) to check out the manadream notch filter and other stuff I've made/modded.


## References/Further Reading:

[https://en.wikipedia.org/wiki/NTSC](https://en.wikipedia.org/wiki/NTSC)

[https://crtdatabase.com/articles/art-design](https://crtdatabase.com/articles/art-design)

[https://en.wikipedia.org/wiki/Dot_crawl](https://en.wikipedia.org/wiki/Dot_crawl)

[https://crtdatabase.com/articles/decoding-240p](https://crtdatabase.com/articles/decoding-240p)

[https://www.extron.com/article/ntscdb1](https://www.extron.com/article/ntscdb1)

[https://www.extron.com/article/ntscdb2](https://www.extron.com/article/ntscdb2)

[https://www.extron.com/article/ntscdb3](https://www.extron.com/article/ntscdb3)

[https://www.extron.com/article/ntscdb4](https://www.extron.com/article/ntscdb4)

[https://nicole.express/2021/composite-conflict-completed.html](https://nicole.express/2021/composite-conflict-completed.html)