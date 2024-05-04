---
title: "Meshtastic and Device Drivers not available for Windows on ARM"
date: 2024-05-04T12:48:26-05:00
slug: 2024-05-04-meshtastic_device_drivers_windows_on_arm
type: posts
draft: false
categories:
  - Meshtastic
tags:
  - meshtastic
  - WindowsOnArm
  - DeviceDrivers
  - hardware
  - Heltec V3
---

![Windows Device Manager detail on a MeshTastic device that has an error due to no available driver.](/images/meshtastic_no_driver_windows_on_arm.png)

It's kind of unfortunate, but I've run into a problem several times flashing Meshtastic devices using a Windows on ARM computer. It seems these drivers either don't exist, or aren't available for automatic download via Windows Update. My only solution so far as been to switch to a Windows device running on x86_64.

Update:

I've found a solution for at least the Heltec V3. I'd been relying on the instructions from Meshtastic and experience with the LilyGo T-Deck. Heltec publishes their own instructions here:

https://docs.heltec.org/en/node/esp32/meshtastick.html

My steps were to follow the link from that page to https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads obtaining the Windows Universal driver. I unzipped the file. Then I connected the V3 using a USB-A to USB-C cable while holding the upper PROG button on the V3. Next, I opened the Windows Device Manager, right-clicked the Heltec in Device Manager and selected the Update Driver. I went through the wizard, directing it to the top level directory created by the zip file. After that, I was able to flash the Heltec V3 with no problems using Microsoft Edge.