
[![](https://img.shields.io/github/v/release/litinoveweedle/SmartIR.svg?style=flat-square)](https://github.com/litinoveweedle/SmartIR/releases/latest) [![](https://img.shields.io/badge/HACS-Custom-orange.svg?style=flat-square)](https://github.com/custom-components/hacs)

## Overview
SmartIR is a custom integration for controlling **climate devices**, **media players** and **fans** via infrared controllers.

SmartIR currently supports the following controllers:
* [Broadlink](https://www.home-assistant.io/integrations/broadlink/)
* [Xiaomi IR Remote (ChuangmiIr)](https://www.home-assistant.io/integrations/remote.xiaomi_miio/)
* [LOOK.in Remote](http://look-in.club/devices/remote)
* [ESPHome User-defined service for remote transmitter](https://esphome.io/components/api.html#user-defined-services)
* [MQTT Publish service](https://www.home-assistant.io/docs/mqtt/service/)

More than 120 climate devices are currently supported out-of-the-box, mainly for the Broadlink controller, thanks to our awesome community.

Don't forget to **star** the repository if you had fun!

## Disclaimer ##

This is a fork of the original repository smartHomeHub/SmartIR which seems to be unmaintained at the time with many pull requests pending. As some of those were useful to my usage I decided to fork and merge the work of the corresponding authors to allow for simple usage of the integration through HACS. Therefore all the corresponding rights belong to the original authors. I also lately started to fix some additional users issues, implementing HomeAssistant future compatibility changes and adding some functionality, trying to keep compatibility but please note, that there may be some **breaking changes** from the original version.

## Installation
### *HACS*
If you want HACS to handle installation and updates, add SmartIR url `https://github.com/litinoveweedle/SmartIR` as a [custom repository](https://hacs.xyz/docs/faq/custom_repositories/) in the HACS. This is preffered instalation method as it would allow for automatic updates.

### *Manual*
Download latest smartir.zip file and place it's content in the `custom_components` folder in your HomeAssistant configuration `custom_component/smartir` directory.
The resulting directory structure should look similar to this:
```
<config directory>/
|-- custom_components/
|   |-- smartir/
|       |-- __init__.py
|       |-- climate.py
        |-- controller.py
|       |-- fan.py
|       |-- media_player.py
|       |-- codes/
|           |-- climate/
|               |-- 1000.json
|               |-- .....
|           |-- fan/
|               |-- 1000.json
|               |-- .....
|           |-- media_player/
|               |-- 1000.json
|               |-- .....
|       |-- custom_codes/
|           |-- climate/
|               |-- 1000.json
|               |-- .....
|           |-- fan/
|               |-- 1000.json
|               |-- .....
|           |-- media_player/
|               |-- 1000.json
|               |-- .....
```

## Device Data - IR Codes
To properly function, specification of your controlled device data including IR codes shall exists either in `codes` or in `custom_codes` directory as a .JSON file. When installed both using HACS or manual method, `codes` directory is populated by device data files maintained by this project. If you would like to create your own device data file, place it in the `custom_codes` class `climate|fan|media_player` subdirectory, this directory is persistent and will be manitained accross HACS updates. **Please don't forget to create [PR](https://github.com/litinoveweedle/SmartIR/pulls) for this new device data file and I will try to include it in a new releases.**

## Platform setup instructions
Click on the links below for instructions on how to configure each platform.
* [Climate platform](/docs/CLIMATE.md)
* [Media Player platform](/docs/MEDIA_PLAYER.md)
* [Fan platform](/docs/FAN.md)

## See also
* [Discussion about SmartIR Climate (Home Assistant Community)](https://community.home-assistant.io/t/smartir-control-your-climate-tv-and-fan-devices-via-ir-rf-controllers/)

