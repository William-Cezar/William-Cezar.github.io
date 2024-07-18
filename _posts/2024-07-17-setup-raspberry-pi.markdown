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
1. Download and install the Raspberry Pi Imager from the Raspberry Pi Foundation's [website][website].
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

##### **Once the OS is written to the card:**
1. Remove the MicroSD card from your computer and insert it into your Raspberry Pi.
2. Plug your Raspberry Pi into the power supply.
3. Connect your Raspberry Pi to your network via an Ethernet cable for a stable internet connection.
4. Since you will be accessing the Raspberry Pi using SSH, ensure SSH is enabled as explained in Step 2. If SSH is not enabled, you will also need to connect a monitor, keyboard, and mouse to configure your Raspberry Pi.
5. Connect the Raspberry Pi to the power source. It will boot automatically and should be ready for use shortly!

### Connecting to Your Raspberry Pi via SSH

With the Raspberry Pi up and running, it's time to connect via SSH. The steps described here are based on my setup, which uses Debian 11, an Ubuntu-based distribution.

1. Find the IP Address:
* Ensure your Raspberry Pi is connected to the same network as your computer, either through Ethernet or WiFi, based on your setup in the Raspberry Pi Imager.
* You can find the Raspberry Pi’s IP address from your router's DHCP lease table, which lists all devices connected to your network. The device name should start with raspberrypi unless you changed the hostname in the Imager settings.

2. Open Terminal:
* On your Ubuntu machine, open the Terminal application.
* Check for SSH Client:
  * Type the following command to see if SSH is installed:
  ```
  ssh -V
  ```
  * If SSH is installed, this command will display the version number of the SSH client.
* Install SSH Client:
  * If SSH is not installed, you can install it by running:
  ```
  sudo apt update
  sudo apt install openssh-client
  ``` 

3. Connect via SSH:
* Enter the following command to initiate an SSH connection:
```
ssh pi@<IP_ADDRESS>
```
* Replace `<IP_ADDRESS>` with the actual IP address of your Raspberry Pi.

4. Enter the Password:
* Enter the default password for the Raspberry Pi, which is raspberry, unless you set a different password during the OS setup phase with the Raspberry Pi Imager.
* If you have set up SSH keys and disabled password login, this step will be skipped, and you will be logged in automatically.

5. Successful Connection:
* Once logged in, you will see the command prompt of your Raspberry Pi, indicating that the SSH connection has been successfully established.

6. Troubleshooting:
* If you encounter any issues connecting, double-check the IP address and ensure that your Raspberry Pi is properly connected to the network and powered on. Also, verify that SSH was enabled during the OS setup.


[website]: https://www.raspberrypi.com/software/