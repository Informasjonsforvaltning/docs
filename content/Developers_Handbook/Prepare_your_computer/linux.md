---
title: Linux
weight: 1
description: A howto decsribing how to create and run a linux virtual machine
---

## HOWTO create and run a linux developer virtual machine on your non-linux laptop.

1. Install [VMware Workstation Player for Windows 64-bit Operating Systems](https://my.vmware.com/en/web/vmware/free#desktop_end_user_computing/vmware_workstation_player/15_0|PLAYER-1510|product_downloads)  
+ Download [Ubuntu Desktop iso](https://ubuntu.com/download/desktop)  
+ Open VMware Workstation Player and create a new Virtual Machine  
  1. In the dialogue, choose "I will install the operating system later":  
      1. Choose "Linux" Version Ubuntu 64-bit  
      +  Give it a suitable name and Location should be on your computer, preferably a SSD. Do NOT install on network-drive.  
      +  Maximum disk size should be set to e.g. 100GB, single file is OK.  
      +  Review your settings and press Finish.  
+ Select your new virtual machine, and press "Edit virtual machine settings".  
  1. Under Hardware, choose  
      1.  CD/DVD (SATA), choose "Use ISO image file:" and point to the location on your disc with the iso image from step 2.  
      + Memory: > 8GB  
      + Processors: 4 cores. Check the box for "Virtualize Intel VT-x/EPT or AMD-V/RVI"  
  + Press OK.  
+ Select your new virtual machine, and press "Play virtual machine". Installation of os will start.  
  1. Follow instructions. They should be self explained.  
      1. Choose "Norsk bokmål" and press "Installer Ubuntu"  
  + After successful installation of os, your virtual machine will reboot. Make sure the ISO image file is removed from the settings.  
