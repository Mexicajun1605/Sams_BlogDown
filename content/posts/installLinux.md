---
date: "2024-05-14"
tags:
- Computers
- Linux
- Technology
title: How to install Linux
---

# How to install Linux 
In this guide I will teach you how to install Linux on your computer. This will not teach you how to install linux on a partition, rather to replace your current operating system with Linux. 
To do this you will need, 
1. A computer 
2. A USB Thumb Drive
3. USB Formatting software. 

## Step 1: Which Linux Distribution should I install? 
This guide will cover the installation of Linux Mint. If you spend any amount of time looking into how to install Linux, you will come across a variety of "distros" or variations of the OS. For most people, I would recommend ignoring everything but Mint. 
Mint is graphically similar to Windows, comes with an installer, and is 100% free and open source. Believe it or not, there are some rather closed off distros. 
This leads us to step 1. Download Linux Mint. 
Navigate to this [page](https://www.linuxmint.com/edition.php?id=311). 
As you scroll down the page, you will see a variety of locations with servers from where you can download the Operating System. Yes, you will download all 3 Gigabytes of the operating system. So first, select the area closest to you, download, grab a coffee, and touch grass for a little bit. The file will end in .iso. 

## Step 2: Format your USB thumb drive 

For the next step, you will have to format your USB thumb drive to become "bootable". What this means is that we are designing the USB to be the starting point for your computer to load an operating system instead of the hard drive. 
First go and download the [Rufus](https://rufus.ie/en/). Rufus is a software that allows you to format your USB drive to do what we need. 

### Step 1 with Rufus 
Download. If you are unsure which version to download, go for the one at the top of the list. 

### Step 2 Open Rufus and format 
When you open Rufus, you should see a dropdown menu at the top for your formattable hardware. Select the USB drive. Below there should be another dropdown menu that says Boot Selection. Select the option that says ISO. That should also be the last three letters of your Linux Mint file name. 
Leave the next three sections as their defaults. 
Click start and wait until Rufus finishes doing its job. 

### Step 3: Navigate to the boot menu 
Remember that the bootloader is the program that turns on your operating system. To navigate here, turn off your computer and turn it back on. As your computer is turning on, press and hold down the bootloader key on your computer before the Windows logo shows up. The bootloader key will be different depending upon the manufacuturer of the device. Below are some common keys and the corresponding manufacturer. 

- Acer: Del or F2
- Asus: F9
- Dell: F12
- HP: Esc or F10
- Lenovo: F1 or F2
- Samsung: F2 

If you are still having difficulties accessing the bootloader, consult this [guide](https://www.wikihow.com/Get-to-the-Boot-Menu-on-Windows).

Once you are there, you should see an option called "Use a device." Click on it and navigate to the USB with Linux Mint installed. Click on it and voila! You are now booting up Linux for the first time!

## Step 3 Follow the Installation Prompts 

Finally, we have arrived at the easiest portion of our task. On the desktop screen, you should see an icon for "install" or "installation." Click it and follow the installer prompts. While you can choose to partition your hard drive to be able to boot both Linux and Windows, why would you want that? You can either do that or fully install Linux. At the end of the installer, you will restart the computer and remove the USB. Start up the computer again, and you now have a Linux machine. 