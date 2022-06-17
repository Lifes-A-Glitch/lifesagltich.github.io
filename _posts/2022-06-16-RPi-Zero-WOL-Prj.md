---
# can edit: title, date, categories, and tags
layout: post
title: "Wake-On-Lan Controller"
date: 2022-06-17 01:00:00 -0500
categories: [Tech Projects]
tags: [Homelab, Raspberry Pi]
---

<h1 align="center"><u>Raspberry Pi Zero 2 W Wake-On-Lan Controller</u></h1>

## Introduction
Recently I have been thinking about a way to make a small 'keychain-like' controller that allows me to essientally "wake up" any computer that I want. This would be localized to my network. I can have a VPN client on the RPi Zero which I can have a VPN server at my house then! This means from anywhere in the world, as long as I have Wi-Fi I can immediately boot the PCs/Servers/IoT devices. 

### Outline

Explaination of the overall goal.
 + Interface
    + Scroll menu - Allows for quick access for selection of any device.
    + Wi-Fi - allows for either checking to see if it is connected to the internet, or allows for the user to answer the password (can be tasking...).
    + VPN selection/connection - Allows for the user to immediately connect to VPN server at home and checks connection.
    + May want Python to be the driver behind this.

 + Parts
    + [Raspberry Pi Zero 2 W](https://www.raspberrypi.com/products/raspberry-pi-zero-2-w/)
    + [Adafruit 128x64 OLED Bonnet for Raspberry Pi](https://www.adafruit.com/product/3531) - Possible option
    + [Adafruit 1.3" Color TFT Bonnet for Raspberry Pi - 240x240 TFT + Joystick Add-on](https://www.adafruit.com/product/4506) - First option
    + [SAMSUNG (MB-ME32GA/AM) 32GB 95MB/s (U1) microSDHC EVO Select Memory Card with Full-Size Adapter](https://www.amazon.com/Samsung-MicroSDHC-Adapter-MB-ME32GA-AM/dp/B06XWN9Q99?ref_=ast_sto_dp&th=1)
    + 3D Printed Case (most likely)

### Notes
Using the programs such as `etherwake` and `wakeonlan`, the main program would have to be written in python to show a GUI (Graphical User Interface) at least. Storage of the information of the IP addresses and MAC addresses could be difficult. It could be in a file which we just parse it out, or just straight hard-coded (which is not a good idea if I want this to be secure). 
<br>
<br>
Either with the OLED Screen or the TFT screen, this can be accomplished. I would prefer the TFT screen mainly on the fact that it is color, and the fact that it is square which would make the design of this more simple.
<br>
<br>
It is also a very good idea to try and make this a password protected so that if it timed out, you would have to input a specific combination to gain access to the program. I am thinking roughly 30 seconds of timeout is a good space to do so.
<br>
<br>
Another thing is, if this is going to be portable, I am thinking of incorporating a battery into it and a battery meter as well. I believe that would be more liking as I wouldn't have to carry a battery pack and try to convert it for the usage itself. I will just have to take into account on how much power everything will draw. I will have to make a dedicated sleep function as well to make sure that usage of power is minimal.

# New song to listen to:

<iframe style="border-radius:12px" src="https://open.spotify.com/embed/track/6Rqn2GFlmvmV4w9Ala0I1e?utm_source=generator" width="100%" height="380" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"></iframe>
<br>
<br>

_Revision 0.1 - 6/17/2022: initial upload_
<br>

_Revision 0. - 6/1/2022: Minor change of Title_
<br>