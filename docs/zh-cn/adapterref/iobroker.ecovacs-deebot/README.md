---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.ecovacs-deebot/README.md
title: TR: Ecovacs Deebot adapter for ioBroker
hash: 49L0KJ5YoprBrRIjUEykIuGtjd3pyv4qd/iYj/AVN7s=
---
![TR: Logo](../../../en/adapterref/iobroker.ecovacs-deebot/admin/ecovacs-deebot.png)

![TR: Stable version](http://iobroker.live/badges/ecovacs-deebot-stable.svg)
![TR: Latest version](http://img.shields.io/npm/v/iobroker.ecovacs-deebot.svg)
![TR: Number of Installations](http://iobroker.live/badges/ecovacs-deebot-installed.svg)
![TR: Number of Downloads](https://img.shields.io/npm/dm/iobroker.ecovacs-deebot.svg)
![TR: npm](https://img.shields.io/npm/dt/iobroker.ecovacs-deebot.svg)
![TR: Dependency Status](https://img.shields.io/david/mrbungle64/iobroker.ecovacs-deebot.svg)
![TR: Travis-CI](https://travis-ci.org/mrbungle64/ioBroker.ecovacs-deebot.svg?branch=master)

TR: # Ecovacs Deebot adapter for ioBroker
TR: This adapter uses the [TR: ecovacs-deebot.js](https://github.com/mrbungle64/ecovacs-deebot.js) library.

TR: ## Features
TR: Some noteworthy features are:

TR: * Retrieve information (e.g. battery, cleaning log, consumable, cleaning and charging status)
TR: * Send clean commands (e.g. auto, spot area, custom area)
TR: * Send some other commands (e.g. play sound, reset consumables, move)
TR: * Save the last run custom area and rerun the saved areas
TR: * Adjustment of vacuum power (clean speed) and water level
TR: * Retrieve information during the cleaning process (e.g. current position and area)
TR: * Retrieve information of the maps incl. spot areas and virtual boundaries
TR: *Delete, save and recreate single virtual boundaries as well as a full set of virtual boundaries*

TR: *) Experimental

TR: Please note: Some features are only available for some models

TR: ## Models
TR: ### Supported models
TR: * Deebot 900/901
TR: * Deebot OZMO 930
TR: * Deebot OZMO 920/950

TR: The models listed are those that I have in use myself or which are technically identical to these.

TR: ### These models should work properly or at least partially
TR: * Deebot Slim 2
TR: * Deebot N79 series
TR: * Deebot M88
TR: * Deebot 600/601/605
TR: * Deebot 710/711/711s
TR: * Deebot OZMO 610
TR: * Deebot OZMO 900/905
TR: * Deebot OZMO Slim 10
TR: * Deebot OZMO T5
TR: * Deebot U2 series
TR: * Deebot N3 MAX
TR: * Deebot N7
TR: * Deebot N8 series
TR: * Deebot (OZMO) T8 series
TR: * Deebot T9 series

TR: The models listed are either already known to work or are technically similar to these models.
Nevertheless, the functionality may be partially limited.

TR: I try to achieve a wide range of functionality, but decide this case by case depending on complexity and various other criteria.
There is of course no claim to full functionality.

TR: ## Installation
TR: It is recommended to use version 10.x, 12.x or 14.x of Node.js. The minimum required version is 10.x

TR: This adapter uses the [TR: node-canvas](https://www.npmjs.com/package/canvas) library for some map-related functionality which may require the installation of some additional packages.
This is optional and not necessary for models without map functionality, but for full functional range please install the following packages.

TR: For Debian-based Linux systems the following commands should be executed:

```bash
sudo apt-get update
sudo apt-get install build-essential libcairo2-dev libpango1.0-dev libjpeg-dev libgif-dev librsvg2-dev
```

TR: For instructions for other systems visit https://www.npmjs.com/package/canvas#compiling

TR: ## Usage
TR: * Information on how to use this adapter can be found [here](https://github.com/mrbungle64/ioBroker.ecovacs-deebot/wiki)

TR: ### States
TR: * Information about the states can be found [here](https://github.com/mrbungle64/ioBroker.ecovacs-deebot/wiki/States-%28EN%29) (English) and [here](https://github.com/mrbungle64/ioBroker.ecovacs-deebot/wiki/Datenpunkte-%28DE%29) (German)

TR: ## FAQ
TR: * Frequently asked questions can be found [here](https://github.com/mrbungle64/ioBroker.ecovacs-deebot/wiki/FAQ)

TR: ## Known issues
TR: * For some models (e.g. Deebot OZMO 930) it is recommended to [schedule a restart](https://www.iobroker.net/#en/documentation/admin/instances.md#The%20page%20content) once a day because there are some reports that the connection is lost after approx. 24 hours
TR: * Some cleaning functions may not work with Deebot 710/711/711s. Please use version 0.5.8 for now.
TR: * The "edge" function does not work with Deebot U2 (starts auto clean instead)

TR: ## Disclaimer
TR: I am in no way affiliated with ECOVACS.

## Changelog

### 1.2.0 (alpha)
* Using library version 0.6.1
* Added functions for deleting, saving and recreating saved virtual boundaries (e.g. 920, 950, T8 series)
* Added functions for saving and recreating sets of virtual boundaries (e.g. 920, 950, T8 series)
* Added options to control clean speed and water level separately for each spot area
* Added function to save current spot area values
* Added some cleaning log values and some states for current cleaning stats
* Removed "Use alternative API call for lastCleaningMapImageURL and lastCleaningTimestamp" option
* Moved some states from "info" channel to sub channels "info.library" and "info.network"
* Quite a lot of improvements for processing map data, spot areas and virtual boundaries
* Some optimisations for js-controller 3.3
* Improved support for N8 series
* Initial support for T9/T9+
* Some improvements and fixes

### 1.1.1
* Using library version 0.6.0-alpha.3
  * Updated login process
  * Support for Chinese server login
* Initial support for some models (e.g. N3, N7 and N8 series)

### 1.1.0
* Stable release

### 1.0.13
* Using library version 0.5.6
* Some improvements and fixes

### 1.0.12
* Using library version 0.5.5
* Added some more T8 models
* Several improvements and fixes

### 1.0.11
* Enabled some features for OZMO 900
* Several minor improvements

### 1.0.10
* Using library version 0.5.4
* Several improvements and fixes
* Added available spot area boundaries to "map" channel (read only)

### 1.0.9
* Using library version 0.5.3
* Added some experimental features (for a few models only)
* Added option for virtual boundaries and some further improvements to adapter config
* Some improvements for js-controller 3.2.x

### 1.0.8
* Using library version 0.5.2 (0.5.2-beta.1)
* Added available virtualBoundaries channel for Deebot 900/901 and Ozmo 930 (read only)
* Added "volume" and buttons for resetting consumable values for 950 type models (920/950/T8)
* Improved synchronization of spot area buttons
* Add option for setting the language for spot area names
* Added some experimental features (for a few models only)
* Several enhancements and fixes
* Bump some dependencies

### 1.0.7
* Using library version 0.5.1 (0.5.1-beta.3)
* Initial support for Deebot U2 series
* Improved support for Ozmo T8 models
* (boriswerner) Fixed cleaning log for 950 type models (920/950/T8)
* (boriswerner) Added available virtualBoundaries to "map" channel (currently read only)
* Improved handling of device classes
* Several enhancements and fixes

### 1.0.6
* Using library version 0.5.0-beta.0
* Fix for running multiple devices
* Support for additional Ozmo T8 models
* Add option to synchronize spotArea buttons
* Set state value for triggered buttons to false
* Add option to suppress "unknown" value for "map.deebotPositionCurrentSpotAreaID" state
* Further enhancements and fixes

### 1.0.5
* Bump library to 0.4.25
* Initial support for Ozmo T8 and T8+
* Implement buttons for resetting consumable values (currently Deebot 900/901 and Ozmo 930 only)
* Several enhancements and fixes

### 1.0.4
* Bump library to 0.4.21
* Remove canvas from dependencies
* Several bugfixes and improvements (especially for N79 series)
* Possibility to specify the number of reruns for a spot area
* Spot areas in the "control" channel are now created automatically
* Remove number of spot areas from adapter settings
* Some refactoring
* Bump dependencies

### 1.0.1 - 1.0.3
* Added support for Ozmo T8 AIVI
* Compact mode support
* Added a button to save the last used custom area values
* Added buttons to rerun saved custom areas
* Some enhancements and fixes

### 1.0.0
* Stable release

### 0.0.1 - 0.6.5
* [Changelog archive](https://github.com/mrbungle64/ioBroker.ecovacs-deebot/wiki/Changelog-(archive)#059)

## License

MIT License

Copyright (c) 2021 Sascha Hölzel <mrb1232@posteo.de>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.