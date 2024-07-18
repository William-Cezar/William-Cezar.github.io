---
layout: post
title:  "Setting up the Raspberry Pi 4!"
date:   2024-07-17 21:09:04 -0300
permalink: /setup-raspberry-pi.html
---


### Setting Up the Raspberry Pi with Raspberry Pi OS

Welcome to this tutorial on how to set up your Raspberry Pi using the Raspberry Pi OS. This guide will walk you through the initial steps needed to get your Raspberry Pi up and running, starting with the preparation of the SD card, writing the operating system image, and initial configuration settings.

This guide assumes you have all the necessary hardware for the Raspberry Pi 4 to function. Please read [this page](/getting-started.html) to verify the required components.

### Installing the Raspberry Pi OS

* Raspberry Pi 4 Model B
* MicroSD card
* MicroSD card reader
* Raspberry Pi Imager software
* Internet connection
* Working computer

#### Step 1: Preparing the SD Card

Since the Raspberry Pi OS image needs to be written to a MicroSD card, if you are using a card larger than 32GB, you'll typically need to format it to FAT32 before you can use it. This is because larger cards often come formatted with the exFAT file system, which isn’t natively supported for the boot process in Raspberry Pi at the moment. If your card is not larger than 32GB you can skip this step.

##### **Formatting to FAT32**
1. Insert your MicroSD card into the card reader and connect it to your computer.
2. Use a disk management tool to format the card to FAT32. On linux, you can use a tool like `gparted`

#### Step 2: Writing the Raspberry Pi OS Image

The Raspberry Pi Imager software makes it easy to write OS images to the MicroSD card.
1. Download and install the Raspberry Pi Imager from the Raspberry Pi Foundation's website.
2. Open the Raspberry Pi Imager and select the desired version of Raspberry Pi OS.
3. Choose the MicroSD card you prepared as the card to write to.
4. Before writing the image, you can set additional options by accessing the advanced settings.
* Enable SSH and set a default password or use public key authentication.
* Configure WiFi by entering your network name (SSID) and password.
* Set locale settings, such as timezone and keyboard layout.
* Predefine the hostname for your Raspberry Pi.
* Enabling SSH is highly recommended, especially if you are not planning to use a direct monitor connection.
5. Click on “Write” and wait for the process to complete. This will download the latest version of the OS and write it to your SD card.

#### Step 3: Initial Setup