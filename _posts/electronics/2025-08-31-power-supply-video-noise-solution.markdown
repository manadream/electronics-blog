---
layout: post
title:  "Power Supply Video Noise Solution"
tags: noise crt consoles fix
---
I run all my consoles through a receiver to select which one to display on my CRT. One day I noticed that there was a lot of noise in the video from my Sega Genesis.

![Genesis noise](/assets/img/IMG_20250831_194625.jpg)
![Genesis noise](/assets/img/IMG_20250831_194731.jpg)

As you can see, it's most noticeable on dark colors or a black screen, and it would slowly roll from the bottom of the screen to the top. I didn't see this same noise on my other consoles and so I looked into why that was. Turns out it was noise coming from the power supply. I tried 3 different ones and they all had some noise, the two larger ones from AliExpress were particularly bad.

![Bad power supplies](/assets/img/IMG_20250831_195122.jpg)

I then tried the power supply that I was using for my NES and SNES on the Genesis and the noise was gone!

![Genesis noise gone](/assets/img/IMG_20250831_201622.jpg)
![Genesis noise gone](/assets/img/IMG_20250831_195158.jpg)

I looked into what the difference was by opening them all up.

![Transformer power supply](/assets/img/IMG_20250812_181818.jpg)
![Switching power supply](/assets/img/IMG_20250831_213242.jpg)

The power supply I was using for my NES and SNES is one of those old heavy brick style power supplies that has nothing more than a transformer, a diode bridge, and a large capacitor. The others were all switching power supplies, a more efficient technology but clearly more noisy. 

There are probably higher quality switching power supplies than the ones I have (one of them did produce much less noise than the others), but using the simpler, heavier one got rid of the noise. So if you encounter this type of noise in the video of your retro consoles, it might be the power supply.