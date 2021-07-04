---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.rfxcom/README.md
title: TR: ioBroker.rfxcom
hash: sHn5GJunDJU2gCzbWU1P920vRVUfOaaV3gTF/zyrpN4=
---
![TR: Logo](../../../en/adapterref/iobroker.rfxcom/admin/rfxcom.png)

![TR: Number of Installations](http://iobroker.live/badges/rfxcom-stable.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.rfxcom.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.rfxcom.svg)

TR: # ioBroker.rfxcom
TR: ![TR: Test and Release](https://github.com/ioBroker/ioBroker.rfxcom/workflows/Test%20and%20Release/badge.svg) [![TR: Translation status](https://weblate.iobroker.net/widgets/adapters/-/rfxcom/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

TR: This adapter communicates with [TR: rfxcom](http://www.rfxcom.com).
Used for receiving the data from weather sensors and wireless power switches.

TR: Read detailed documentation for RfxCom [TR: here](http://www.rfxcom.com/WebRoot/StoreNL2/Shops/78165469/MediaGallery/Downloads/RFXtrx_User_Guide.pdf)

TR: ## Usage
TR: To enable the learning of sensors you must activate "Inclusion mode".
The inclusion mode by default will be enabled for 5 minutes (300000 ms) and after 5 minutes will be disabled automatically.

TR: To enable inclusion mode forever, just set "Inclusion timeout" to 0.

TR: ## Pair
TR: The devices get the new address every time the battery changed.

TR: So after the battery changed it must be learned anew.

TR: To do that press the pair button just before inserting the battery and the device will be learned with new address.

TR: ## ToDo
TR: **Just now only Somfy, Curtain and Lighting3 devices are supported.**

TR: <!-- Placeholder for the next version (at the beginning of the line):

TR: ### __WORK IN PROGRESS__ -->

## Changelog
### 2.0.1 (2021-06-29)
* (peterbaumert) update packages
* (bluefox) Breaking change: no linux with 32 bit support

### 1.0.1 (2020-08-05)
* (bluefox) Compact mode
* (bluefox) Support of node 10 added
* (bluefox) Refactoring

### 0.1.0 (2016-07-05)
* (bluefox) initial commit

## License
The MIT License (MIT)

Copyright (c) 2017-2021, Bluefox<dogafox@gmail.com>

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