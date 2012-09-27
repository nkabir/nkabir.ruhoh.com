---
title: Environment Setup
date: '2012-09-14'
description: Setting up your development environment
categories: sysadmin
tags:
    - ubuntu
    - precise
    - blackbox

type: draft

---
<div class="alert alert-success">
<button type="button" class="close" data-dismiss="alert">×</button>
Adapted from <a href="https://tomdru.bitbucket.org/environment.html">tomdru.bitbucket.org</a>
</div>

## Setting Up Your Environment

#### Install VirtualBox

Download the latest VirtualBox package for [your host system](https://www.virtualbox.org/wiki/Downloads). Run the installer.

Download the 64bit Desktop version of Xubuntu from [http://xubuntu.org/getxubuntu/](http://xubuntu.org/getxubuntu/)

Open VirtualBox, and click the "New" button in the upper left hand corner.
Use the following settings:

* **Name**: *stemcell*
* **Operating System**: *Linux*
* **Version**: *Ubuntu (64 bit)*
* **Memory**: *2048 MB*
* **Hard disk**: *VDI, Dynamically allocated, 500 GB*

In **Settings -> Storage**, click *Add CD/DVD device*, Choose the hard disk and locate the Xubuntu ISO in the Downloads folder.

In **Settings -> Network**, choose *Attached to: Bridged Adapter*.

Now *Start* your virtual machine and configure Xubuntu.

#### Install Xubuntu Desktop 12.04

You will first need to install Xubuntu on your empty virtual machine. This is done through a series of graphical menus:

* **Welcome** - The default language is *English*. Select *Install Xubuntu*.

* **Preparing to install Xubuntu** - Check *Download updates while installing* and *Install this third-party software*. Select *Continue*.

* **Installation type** - Check *Erase disk and install Xubuntu*. Select *Continue*.

* **Erase disk and install Xubuntu** - Use the default for *Select drive*. Select *Install now*.

* **Where are you?** - Use *New York*. Select *Continue*.

* **Keyboard layout** - For keyboard layout, choose *English (US)*. Select *Continue*.

* **Who are you?** - Create a guest account. We will create your actual user a little later
  * Your name: *Ubtunu*
  * Your computer's name: *stemcell*
  * Pick a username: *ubuntu*
  * Choose a password: *secret*
  * Confirm your password: *secret*
  * Choose whether you would like to log in automatically or always be prompted for your password. The system will begin installing.

* **Installation Complete** - Select *Restart Now*.

The .iso will be ejected automatically. Press ENTER and the system will reboot. 

#### Create a User

Let us pretend that your user's name is Alice Smith. To add Alice as a user, type the following
    
    $ sudo adduser asmith
    $ sudo usermod -a -G sudo asmith
    
The second line gives *asmith* "sudo" powers. Give *asmith* a private password. Log out and log in as *asmith*.

#### Install Guest Additions

Go to the *Devices* tab in the VirtualBox Manager and select *Install Guest Additions*. Inside your virtual machine a CD will appear on the desktop. Execute the following

    $ sudo apt-get install dkms
    $ cd /media/VBOXADDITIONS
    $ sudo ./VBoxLinuxAdditions.run
    
At this stage, you should take a snapshot.

#### Take a Snapshot

A good practice is to take a snapshot of your virtual machine every time you make a significant change. This will ensure that you have a clean system to go back to in case you accidentally corrupt your environment. A clean system is essential when developing software that other people are going to use.

After the system has rebooted, *Shut Down* your machine (in the upper right hand menu). It is good to take a snapshot while your machine is off. In the Oracle VM VirtualBox Manager window, click on the Snapshots tab, and click the camera icon to make a snapshot of the fresh install. Call it "fresh-install".

#### Install Updates

Open *Accessories > Terminal Emulator*. Execute the following commands:

    $ wget https://raw.github.com/gist/2703110/25dd6b7be4752b2d3c5932ac1f9e30f38b401139/sources.list
    $ sudo cp sources.list /etc/apt/
    $ sudo apt-get update
    $ sudo apt-get upgrade

You will need to reboot.

#### Install Dropbox

Execute

    $ sudo apt-get install nautilus-dropbox
    $ dropbox start -i

Then enter your login and password information. You will be prompted to install the latest version. Do not select this. Select "Don't Ask Again". Choose the "Typical" installation.

The following video demonstrates how to set up a VirtualBox virtual machine

<iframe frameborder="0" style="border:1px solid #AAA; width:480px; height:290px;" src="http://video.google.com/a/ife/330fd0392083ed2c"></iframe>

and this video shows how to set up Xubuntu 12.04

<iframe frameborder="0" style="border:1px solid #AAA; width:480px; height:290px;" src="http://video.google.com/a/ife/21c5d20afb54bb99"></iframe>
