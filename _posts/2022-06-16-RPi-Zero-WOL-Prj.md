<!-- ---
# can edit: title, date, categories, and tags
layout: post
title: "Raspberry Pi Zero W WOL controller"
date: 2022-06-14 12:00:00 -0500
categories: [Tech Projects]
tags: [Homelab, Raspberry Pi]
--- -->

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
    + [Adafruit 128x64 OLED Bonnet for Raspberry Pi](https://www.adafruit.com/product/3531)
    + [SAMSUNG (MB-ME32GA/AM) 32GB 95MB/s (U1) microSDHC EVO Select Memory Card with Full-Size Adapter](https://www.amazon.com/Samsung-MicroSDHC-Adapter-MB-ME32GA-AM/dp/B06XWN9Q99?ref_=ast_sto_dp&th=1)
    