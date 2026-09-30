> [!NOTE]
**Hey that was fast!** 
You got here early, which means this guide isn't complete yet! All the files should uploaded but the full detailed guide will be added over the next few days. 
If you know what you're doing, great! Everything you need should be here. If you're new to this and aren't sure what to do, check back here in a few days for more details! Thanks!

# Smart mmWave Presence Sensor
This repository contains all the 3D models, PCB production files, ESPHome software configurations, and links to parts used to build the mmWave Presence Sensor featured on [the channel](https://www.youtube.com/@FeatureNAB). 

[![Watch the video](https://img.youtube.com/vi/FTkbSREjxcw/0.jpg)](https://www.youtube.com/watch?v=FTkbSREjxcw)

The device uses an ESP32 and a mmWave sensor to track you location in 2D and this can be used to trigger zone based automations (basically if you occupy a certain section of a room you can trigger a specific action, e.g. a corner reading lamp turns on when you sit in the armchair or an overhead kitchen light when you approach the countertop). 

It connects natively to [Home Assistant](https://www.home-assistant.io/) and the firmware is written using [ESPHome](https://esphome.io/).
  
## What's in this Repository?

If you just want the final ready-to-go files, check the [Releases tab](../../releases) on the right!

## Getting Started

### 1. Parts
Some of these links are affiliate links, which either cost you nothing or in some cases actually save you a small amount. They help support the channel, which is very sincerely appreciated!

Please note: The proces on some items have changed slightly since I started working on this project, but they are all still in the same ballpark, about $10-12 for the basic configuration.
LD2450 version:
*   [Seeed XIAO ESP32-C6](https://www.seeedstudio.com/Seeed-StudioXIAO-ESP32C6-3PCS-p-5918.html?sensecap_affiliate=dzMqXsY&referring_service=link) microcontroller
*   [LD2450 mmWave board](https://s.click.aliexpress.com/e/_c3RyXVX3)
*   2x [7-pin Header](https://mou.sr/3U0VYMP). These connect the ESP32 board to the PCB. You need 2.
*   [Dual Row 4-pin Header](https://mou.sr/3VlU9um). This is For connecting the LD2450 to the custom PCB.
*   Optional [5-pin Header](https://mou.sr/4jxkbEL). This can be used for the I2C connector if you want to connect things like a temperature sensor.


DFRobot version:
*   [Seeed XIAO ESP32-C6](https://www.seeedstudio.com/Seeed-StudioXIAO-ESP32C6-3PCS-p-5918.html?sensecap_affiliate=dzMqXsY&referring_service=link) microcontroller
*   [DFRobot mmWave board](https://mou.sr/3TrZVKl) (see the video for differences)
*   2x [7-pin Header](https://mou.sr/3U0VYMP). These connect the ESP32 board to the PCB. You need 2
*   [5-pin Header](https://mou.sr/4jxkbEL). This connect the DFRobot board to the PCB. It can also be used for the I2C connector if you buy a second one.


### 2. PCB
I designed the PCB to be manufactured and assembled by [JLCPCB](https://jlcpcb.com/?from=FEATURE). The ordering process is shown in the video.
1. Head to the **[Releases tab](../../releases)** and download the `LD2450_HAT.zip `.
2. Upload the Gerber zip to JCLPCB.
3. Choose your finish, I used ENIG and black soldermask, which was entirely based on aesthetics and is not essential.
5. All the other settings should be fine on their defaults. Order and wait for the goods to arrive!
   
### 3. Firmware

ESPHome has a [desktop installer](https://esphome.io/install/) now! Use the ESPHome yaml to install over USB to the ESP32. `secrets.yaml` is used for wifi passwords etc, so fill those in and save it in the same root directory.


#### 4. 3D Printing the Enclosure
Note: This project has a bunch of variations, I just uploaded the simplest versions to start, the others will be added very soon!
Download the `3D_Files.zip` from the Releases tab and print the enclosure. 
*   The `.3mf` file is pre-configured and ready to print.

## Home Assistant Dashboard

If you are connecting this to Home Assistant and want the UI dashboard card shown in the video, you will need to install HACS (Home Assistant Community Store) and download the **[Zone Mapper Lovelace Card](https://github.com/ApolloAutomation/zone-mapper-card)**.

## Support the project
[Patreon](https://www.patreon.com/FEATURE418) for anyone interested, so I can continue making projects like this. Thanks!

Some of the links on this page are affiliate links and help support these projects at no cost to you.
