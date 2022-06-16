---
# can edit: title, date, categories, and tags
layout: post
title: "Homelab: Updating the BIOS & iDRAC on R630/R730 series Servers"
date: 2022-06-14 12:00:00 -0500
categories: [Homelab]
tags: [Homelab, R630, R730, R730XD, iDRAC, BIOS]
---

<h1 align="center"><u>Updating the BIOS & iDRAC on RX30 Series Server</u></h1>

_Note: I cried during this whole process, this documentation is to help you cry less than I did._

* Requirements:
  * Need to plug in RX30
  * Make sure there is an ethernet cable plugged into the iDRAC port
  * Must have PC to download firmware (Doesn't matter what Operating System, recommended is Windows)
  * Banana for potassium 🍌

First, you will want to pull the drivers off of [Dell's Website](https://www.dell.com/support/home/en-us/product-support/product/poweredge-r630/drivers). You will specifically be looking for BIOS 2.13.0 and iDRAC version 2.83.83.83.

## BIOS

![BIOS](/assets/img/Dell_BIOS-Site.png)

## iDRAC

![iDRAC](/assets/img/Dell_iDRAC-Site.png)
<br>

### After Downloading

You will want to create a "dump" folder for the iDRAC executable. Most likely, you are in your downloads folder. If you would like to stay in there, that is fine. I do recommend though of moving both `.exe` files to a separate folder (I called mine 'Dell' originally).

Make another new folder called 'iDRAC_dump'. Click on the `iDRAC-with-Lifecycle-Controller_Firmware---.exe` executable. You should see something similar to this...

<br>

![iDRAC_Firmware](/assets/img/iDRAC_firmware_software.png)
<br>

You will want to click on 'extract' and extract the files to the 'iDRAC_dump' folder (you will want to create one). Once in there you will see a folder called 'payload', within that folder you will see a file called `firmimg.d7`. __That__ file is the firmware file you will need for the next step.

### iDRAC

You will head to the iDRAC hosted site using the IP address of the iDRAC card. You can usually find this within your router's IP table. Heading to the page, you will need to put in the Username and Password of the iDRAC. Once you are in, you will see a page like this:
![R630_iDRAC_&_BIOS](/assets/img/R630_iDRAC_and_BIOS.png)
<br>
In the green box is the current version I have loaded onto the R630 for BIOS and iDRAC, we will be getting you there shortly. In the meantime, click 'Update and Rollback' (shown with the red box around it).

### Uploading
##### iDRAC Upload
The page is pretty simple, by default it is on the 'Update' tab. You will want to click on 'Choose File' and input the path for that `firmimg.d7` file mentioned earlier. After that you will want to click 'upload'. From there you will be moved to another page in which it will show that it is loading the firmware. This can definitely take some time. Once it is done installing the firmware, the RX30 will restart and thus kick you out of the iDRAC management page.
<br>

Hit the refresh button and log back into the page. Depending on what firmware version you had before, you will notice some very heavy changes. You will then navigate back to 'Update and Rollback' to then upload the BIOS. 

##### BIOS Upload
Within the 'Update and Rollback' page again, you will upload the file named `BIOS_74DF9_WN64_2.13.0.EXE`. You do not have to extract the file and pull the firmware, just upload the entire `.exe` file. This will take some time again with a restart at the finish.

### Finished
You can now thank yourself that you were able to get this done with minimal tears. Go and do it to the rest of your servers, and cry less. 

<br>

# New song to listen to:

<iframe style="border-radius:12px" src="https://open.spotify.com/embed/track/51rv0PwUdnFJNdf04pPLB2?utm_source=generator" width="100%" height="380" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"></iframe>


_Revision 0.1 - 6/15/2022: initial upload_<br>
_Revision 0.2 - 6/16/2022: Grammar, and rewording things_<br>