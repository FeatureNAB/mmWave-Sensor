> [!NOTE]
**Hey that was fast!** 
You got here early, which means this guide isn't complete yet! All the files should uploaded but the full detailed guide will be added over the next few days. 
If you know what you're doing, great! Everything you need should be here. If you're new to this and aren't sure what to do, check back here in a few days for more details! Thanks!

# Smart mmWave Presence Sensor
This repository contains all the 3D models, PCB production files, ESPHome software configurations, and links to parts used to build the mmWave Presence Sensor featured on [the channel](https://www.youtube.com/@FeatureNAB). 

[![Watch the video](https://img.youtube.com/vi/FTkbSREjxcw/0.jpg)](https://www.youtube.com/watch?v=FTkbSREjxcw)

The device uses an ESP32 and a mmWave sensor to track you location in 2D and this can be used to trigger zone based automations (basically if you occupy a certain section of a room you can trigger a specific action, e.g. a corner reading lamp turns on when you sit in the armchair or an overhead kitchen light when you approach the countertop). 

It connects natively to [Home Assistant](https://www.home-assistant.io/) and the firmware is written using [ESPHome](https://esphome.io/).

If you just want the final ready-to-go files, check the [Releases tab](../../releases) on the right!

## Getting Started

### Parts
**Note on Links & Pricing:** Some of the links below are affiliate links, which cost you nothing (or in some cases, save you a small amount) but help support the channel - this is very sincerely appreciated! Prices may fluctuate slightly from when this project started, but the basic configuration should still run you about $10-12 plus shipping and duties depending on where you live.

A lot of my parts came from Mouser. You may be able to get headers etc from Aliexpress too to save on shipping, just note the 2x4P header is 2mm pitch! Also the friction fit of the enclosure requires specific physical dimensions. I will look into AliExpress and if I find any promising alternatives I will add them here

### 1. Core Components (Required for all builds)
These parts are required regardless of which mmWave sensor you choose to use. 

| Part Name | Qty | Notes | Sourcing Options |
| :--- | :---: | :--- | :--- |
| **Seeed XIAO ESP32-C6** | 1 | The main microcontroller. Cheaper from Seeedstudio directly, bundle of 3 means $4.35 per board | [SeeedStudio](https://www.seeedstudio.com/Seeed-StudioXIAO-ESP32C6-3PCS-p-5918.html?sensecap_affiliate=dzMqXsY&referring_service=link) <br> [AliExpress](https://s.click.aliexpress.com/e/_c4aRdovX) |
| **7-pin Header** | 2 | Connects the XIAO ESP32 to the custom PCB. | [Mouser](https://mou.sr/3U0VYMP) |

---

### 2. Radar Variants (Choose ONE)
This PCB supports two different mmWave radar modules, but only one can be connected at a time.

#### Option A: LD2450 
| Part Name | Qty | Notes | Sourcing Options |
| :--- | :---: | :--- | :--- |
| **LD2450 mmWave Board** | 1 | Target tracking mmWave sensor. | [AliExpress](https://s.click.aliexpress.com/e/_c3RyXVX3) |
| **Dual Row 4-pin Header (2mm)** | 1 | Connects the LD2450 module to the custom PCB. **Note: This is 2mm pitch! Not the typical 2.54mm pitch - this is dictated by the connector the LD2450 uses** | [Mouser](https://mou.sr/3VlU9um) |

#### Option B: DFRobot SEN0609
| Part Name | Qty | Notes | Sourcing Options |
| :--- | :---: | :--- | :--- |
| **DFRobot mmWave Board** | 1 | DFRobot human presence sensor. | [Mouser](https://mou.sr/3TrZVKl) |
| **5-pin Header** | 1 | Connects the DFRobot module to the custom PCB. | [Mouser](https://mou.sr/4jxkbEL) |

---

### 3. Optional Upgrades
Want to add temperature sensing or improve power stability? These parts are completely optional but supported by the PCB.

| Part Name | Qty | Notes | Sourcing Options |
| :--- | :---: | :--- | :--- |
| **5-pin Header** | 1 | Required if you want to expose the I2C connector. | [Mouser](https://mou.sr/4jxkbEL) |
| **Adafruit SHTC3** | 1 | I2C Temperature & Humidity Sensor. | [Mouser](https://mou.sr/4xZLXgK) |
| **SMD Capacitors** | 2 total | One of each. Both 0805 package size, one 100nF and one 10uF. Basically any caps with the same rating and size will do. | [100nF 0805](https://mou.sr/3TBZTj8) <br> [10uF 0805](https://mou.sr/4AOrj5Q) |


### PCB
I designed the PCB to be manufactured and assembled by [JLCPCB](https://jlcpcb.com/?from=FEATURE). The ordering process is shown in the video.
1. Head to the **[Releases tab](../../releases)** and download the `LD2450_HAT.zip `.
2. Upload the Gerber zip to JCLPCB.
3. Choose your finish, I used ENIG and black soldermask, which was entirely based on aesthetics and is not essential.
5. All the other settings should be fine on their defaults. Order and wait for the goods to arrive!
   
### Firmware

ESPHome has a [desktop installer](https://esphome.io/install/) now! Use the ESPHome yaml to install over USB to the ESP32. `secrets.yaml` is used for wifi passwords etc, so fill those in and save it in the same root directory.


#### 3D Printing the Enclosure
Note: This project has a bunch of variations, I just uploaded the simplest versions to start, the others will be added very soon!
Download the `FullAssembly.3mf` from the repo or the Releases tab and print the enclosure. 

**Very Important!** - The tightening ring MUST be printed at 0.12mm layer height or the threads will come out weird. I think everything else should be fine at 0.2mm, let me know if it isnt!

## Home Assistant Dashboard

If you are connecting this to Home Assistant and want the UI dashboard card shown in the video, you will need to install HACS (Home Assistant Community Store) and download the **[Zone Mapper Lovelace Card](https://github.com/ApolloAutomation/zone-mapper-card)**.

## Support the project
[Patreon](https://www.patreon.com/FEATURE418) for anyone interested, so I can continue making projects like this. Thanks!

Some of the links on this page are affiliate links and help support these projects at no cost to you.
