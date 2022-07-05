---
# can edit: title, date, categories, and tags
layout: post
title: "Homelab: Proxmox Issues on R630"
date: 2022-06-24 07:00:00 -0500
categories: [Homelab]
tags: [Homelab, R630]
---

[![Proxmox](/assets/img/Proxmox.png)](https://www.proxmox.com/en/)
<br>
<br>

## Small Description

So what is Proxmox?
<br>
I could literally just say google it. ![Sarcastic-ass-gif](/assets/img/search_it.gif)
<br>
_but_, I guess I will be nice. Proxmox in its essence is an open-source plateform that allows the virtualization of any (if not, most) operating systems. The virtualization of them are called VMs (virtual machines), and also supports containers (like VMs but more lightweight).
<br>
In all honesty, it is an alright hypervisor (general software that allows virtualization). I prefer VMware's ESXi honestly since it is more robust and allows for greater features in my perspective. Then again, Proxmox is completely new to me.
<br>
<br>

## Actual Problem

I am having a very hard time wrapping my head around the GUI (Graphical User Interface, basically a "website" that you access through an IP). It doesn't seem that complicated but it still is. I don't necessarily like it honestly. It is so far out of my stretch and I am thinking of transferring back to ESXi. I know that Proxmox itself uses less system resources than ESXi since it is open source; this also means it requires less resources

I am unsure at this point in time how I can get used to the GUI. There are other things that took me awhile to understand in the first place like how to make a storage pool to hold data in. I had no idea that my SSDs that I had in the server were already formatted in ZFS (type of filesystem format). I then formatted them and cleared them of the ZFS it was set with. I was then able to make a pool. 

## Okay... Actual Problem Again
<u>The actual problem now is the fact I cannot spin up a VM without messing up the IP addresses and trying to connect it to the internet.</u>

## What I Understand & The Plan
What I want to do with Proxmox is run 2 VMs to run multiple services on. One VM will be designated for internal services that do not need to be reached from the outside (but may still have internet connection, still unsure about this), and external services (websites, VPNs, and other stuff). These "services" will be set up in the VMs as Docker Containers (I am not explaining, it is a ton of information already). Those containers will house everything, and I personally have to get better at networking when it comes to that. I need more experience within virtual networking and phyiscial networking.
<br>
<br>

# New song to listen to:
Honestly love this song, listen to it whenever I am hacking anything. Think of it as a pump up song. Enjoy!
<br>
<iframe style="border-radius:12px" src="https://open.spotify.com/embed/track/4rFbNHh4gX7kGTbfCGEOMF?utm_source=generator" width="100%" height="80" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"></iframe>



<br>
<br>

_Revision 0.1 - 6/24/2022: Initial Upload_

<br>