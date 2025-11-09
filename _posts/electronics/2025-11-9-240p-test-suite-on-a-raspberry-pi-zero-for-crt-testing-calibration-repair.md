---
layout: post
title:  "240p Test Suite on a Pi Zero for CRT Testing, Calibration and Repair"
tags: CRT
---
I wanted a single, portable device for all my CRT repair needs, so I used a spare raspberry pi I had to run the 240p Test Suite.
I was unsatisfied with all the guides I found on getting composite output from a raspberry pi, they were all missing something or just no longer worked with the latest emulation distros.
I wanted something that accurrately outputs 240p content, boots up as fast as possible, and has a simple, flexible UI. After some digging, I decided to use Lakka as the distro, with some key modifications for this use case.

Lakka is a Linux emulation distribution that directly uses RetroArch as its means of running games as well as for UI. There is no fancy EmulationStation-like interface to scroll around in and it has as little bloat as possible.
In addition to those benefits, using RetroArch as the means of rendering video allows us to customize the specifics of that output for each core that we want to use. This was the key to getting this to work how I wanted.

This guide will go over how to set this up on a Rapspberry Pi Zero, but it will work with most other Pis as well with the difference being where to solder the composite video wires.

## Step 1: Flash Lakka and Set Config

Download the latest Lakka image for your Pi [from their website](https://www.lakka.tv/get/linux/) and flash it onto an SD card using one of the following USB flashers (or something you already know how to use):

- Raspberry Pi Imager
- Popsicle USB Flasher
- Balena Etcher
- win32diskimager

Once it is done flashing, insert it into your pi and plug it into an HDMI monitor. Let it run and do its thing to finish setting up. Once it's done and is booted to the Lakka menu, turn off the Pi and take the SD card out.

## Step 2: Configuring Lakka

I created these configs to be as close as possible to the output of an actual SNES, NES and Genesis. I loaded the same 240p suite on the Pi and my consoles and went back and forth and adjusted the Pi's core configs until the pictures were the same size and positioning as my consoles. You can adjust these to your liking, but they should be accurate and thus good for calibration and repair. I also set the Lakka UI layout and scale such that it is usable in 240p with these configs.

Reinsert the SD card into you computer so you can access the files on the SD card and modify them.

Editing text files on a Pi's SD card can be tricky depending on the OS your computer uses, but the following steps should more or less apply to any OS you use. If you need specific guidance, [this guide on Lakka's site](https://www.lakka.tv/doc/Accessing-Lakka-filesystem/) has more info and there are guides elsewhere for how to edit files on a flashed SD card in your OS. Once you understand and are able to edit text files on the SD card, do the following:

1. Open the SD card partition labelled `LAKKA_DISK` in your file manager.
2. Navigate to the folder `.config/retroarch/config/` (you may need to access it as root/admin).
3. Create the folder `FCEUmm` and place the following text in a file called `FCEUmm.cfg` in the `FCEUmm` folder you just created (this is the NES core that will be used).
```
aspect_ratio_index = "23"
custom_viewport_height = "224"
custom_viewport_width = "642"
custom_viewport_x = "45"
custom_viewport_y = "6"
video_fullscreen_x = "720"
video_fullscreen_y = "240"
xmb_layout = "1"
menu_scale_factor = "0.75"
```
4. Create the folder `PicoDrive` and place the following text in a file called `PicoDrive.cfg` in the `PicoDrive` folder you just created (this is the Genesis/Mega Drive core that will be used).
```
aspect_ratio_index = "23"
custom_viewport_height = "224"
custom_viewport_width = "642"
custom_viewport_x = "37"
custom_viewport_y = "8"
video_fullscreen_x = "720"
video_fullscreen_y = "240"
xmb_layout = "1"
menu_scale_factor = "0.75"
```
5. Create the folder `Snes9x` and place the following text in a file called `Snes9x.cfg` in the `Snes9x` folder you just created (this is the SNES core that will be used).
```
aspect_ratio_index = "23"
custom_viewport_height = "224"
custom_viewport_width = "646"
custom_viewport_x = "37"
custom_viewport_y = "7"
video_fullscreen_x = "720"
video_fullscreen_y = "240"
xmb_layout = "1"
menu_scale_factor = "0.75"
```

Next you'll want to set up Lakka to output composite video:

1. Open the SD card partition labelled `LAKKA` in your file manager.
2. Open the file `config.txt` in a text editor.
3. Find the line that has `include distroconfig.txt` and comment it out by adding a `#` to the beginning of the line.
4. Find the line that has `#include distroconfig-composite.txt` and uncomment it by removing the `#` at the beginning of the line.
5. Save these changes. Those two lines should now look like this:
```
#include distroconfig.txt
include distroconfig-composite.txt
```
6. Next, open the file `cmdline.txt` in a text editor.
7. Add `video=Composite-1:720x480@60ie` to the end of the one line in the file and save it. It should look like this:
```
boot=UUID=1704-1837 disk=UUID=b6a5e937-7d11-4142-87f9-3c4a5a54cfa6 quiet console=tty0 video=Composite-1:720x480@60ie
```

## Step 3: Copy 240p Test Suites to the Pi

With your SD card still inserted, download the SNES and Genesis 240p Test Suites [from here](https://artemiourbina.itch.io/240p-test-suite), rename them to `SNES-240p.sfc` and `Genesis-240p.bin` (or whatever you want) and copy them to the `roms` folder on `LAKKA_DISK`.

Then download the NES 240p Test Suite [from here](https://github.com/pinobatch/240p-test-mini/releases) (it's the file called 240pee.nes), rename it to `NES-240p.nes` and copy it to the `roms` folder.

Finally, add whatever other test roms you want to the `roms` folder.

## Step 4: Getting Composite Output From Your Pi

All Rapspberry Pis can output composite video, but where the signal is output is different depending on the model.

For a Raspberry Pi Zero 1, the output is made available via 2 through-holes on the Pis PCB. They are labelled by a box around them with the text `TV` screen printed next to it.

Simply get a spare RCA or BNC cable that you can cut and use for this and solder the center/hot/signal wire to the left and the shield/ground wire to the right when looking at the board with the SD card on the left side. See the photo below.

![TV Out](/assets/img/IMG_20251109_102049.jpg)

For other Raspberry Pis it will be different where the video signal comes from:

- Pi 1 through Pi 4: TRRS port with a specific cable.
- Pi Zero 2: Solder to the TV and GND pads on the bottom of the PCB.
- Pi 5: 2 through-holes on the PCB in a box labelled `VID` in between the `HMDI1` and `CAM/DISP 1` ports.

If you get a weird thick, jagged white line and shifting video when you boot up your Pi using composite video, you soldered the wires in reverse.

Or, in the case of Pi 1 through 5, the cable you are using doesn't have the correct polarity, check with a multimeter that the TRRS output is

|Left Audio|Right Audio|Ground|Video|

and if it is not, that's your problem.

Some Pi Zero 1s have the `TV` label on the left side of the box and some have it on the right, but where the wires go is not different. The video signal comes from the left side and the ground on the right.

## Step 5: Connect a Controller and Boot it up

Get a USB controller and a micro USB to USB A adapter so that you can connect it to your pi. I used a simple SNES style controller.

![Controller](/assets/img/IMG_20251109_104258.jpg)

If you want you can get a case or 3D print one. I printed [this case](https://www.printables.com/model/877991-raspberry-pi-zero-2-w-case).

![In a case](/assets/img/IMG_20251109_104315.jpg)

Connect the controller to the pi, connect the Composite video output to a CRT, and then connect power.

You should see it boot up and display the main menu in 480i mode.

![Lakka Menu](/assets/img/IMG_20251109_125337.jpg)

You're going to want to set the hotkey controller combo to get back to the Lakka menu from running a game.

1. With your controller, go right to the gears icon and down to `Input` and select it.

![Input Menu](/assets/img/IMG_20251109_125356.jpg)

2. Go down to `Hotkeys` and select it, then go down to `Menu Toggle (Controller Combo)` and select it.
3. Choose a combo that makes sense for you and your controller. I selected `Hold Start (2 seconds)`, but whatever you want is fine so long as your controller actually has the button combo chosen.

![Hotkey](/assets/img/IMG_20251109_125423.jpg)

Then back out all the way back to the top menu. You can now test out your 240p setup to make sure it's working right.

1. Go down to `Load Content` and select it.
2. Choose `Start Directory` and you should see the roms you put in the `roms` folder
3. Go down to `SNES-240p.sfc` and select it, then select `Nintendo - SNES / SFC (Snes9x)` as the core. This is very important as the settings override was set for this core only.
4. You should see the 240p Test Suite boot up and be rendering in 240p. If the image is flickering at all (which means it's in 480i) or if the picture is really narrow in the center, then you need to go back and make sure you set the configs correctly.

![240p Test Suite on SNES](/assets/img/IMG_20251109_125454.jpg)

5. Press the hotkey controller combo you set and you should see the Lakka menu appear.
6. Go down and select `Close Content` and you should be brought back to the main Lakka menu.

If this all went well and looks correct, do the same for the NES 240p suite on the `Nintendo - NES / Famicom (FCEUmm)` core and Genesis 240p on the `Sega - MS/GG/MD/CD/32X (PicoDrive)` core.

If something looks off with any of them or it's not rendering in 240p, go back and check that the configuration was done correctly.

To make it easier to access the roms with the correct core, from the menu you access with the controller combo hotkey you can select `Add to Favorites` and then you will be able to launch the rom from the Lakka main menu's Favorites section which looks like a Star icon.

And that's it! You now have a portable CRT testing device :)

If you want my exact setup, you can also [download my retroarch.cfg file](/assets/txt/retroarch.cfg) and replace yours with it.

--------

Files:

[FCEUmm.cfg](/assets/txt/FCEUmm.cfg)

[PicoDrive.cfg](/assets/txt/PicoDrive.cfg)

[Snes9x.cfg](/assets/txt/Snes9x.cfg)

[retroarch.cfg](/assets/txt/retroarch.cfg)