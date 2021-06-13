---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.trivum/README.md
title: TR: ioBroker.trivum
hash: OPUUq+XSk/V6xvZboFDmtK4R9e9OgPnZxtJRc9Tor10=
---
![TR: Logo](../../../en/adapterref/iobroker.trivum/admin/trivum.png)

![TR: NPM version](http://img.shields.io/npm/v/iobroker.trivum.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.trivum.svg)
![TR: Number of Installations (latest)](http://iobroker.live/badges/trivum-installed.svg)
![TR: Number of Installations (stable)](http://iobroker.live/badges/trivum-stable.svg)
![TR: Dependency Status](https://img.shields.io/david/TheBam1990/iobroker.trivum.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/TheBam1990/ioBroker.trivum/badge.svg)
![TR: NPM](https://nodei.co/npm/iobroker.trivum.png?downloads=true)

TR: # ioBroker.trivum
TR: **Tests:** ![TR: Test and Release](https://github.com/TheBam1990/ioBroker.trivum/workflows/Test%20and%20Release/badge.svg)

TR: ## trivum adapter for ioBroker
TR: Trivum Multiroom System

TR: ## User manual
TR: Enter the IP address of the device in the main settings tab.
The adapter then automatically searches for the available zones and writes them with the associated objects in the object list.

TR: The following are created as general variables (global):

TR: -Turn everything off

TR: -Active zones (how many zones are currently on)

TR: Then the respective control elements under the individual zones:

TR: -Mute (mute and reactivate)

TR: -Defoult-Stream (activating the zone with the standard webstream)

TR: -Defoult tuner (activating the zone with the standard tuner)

TR: -Volume (display the volume and change it)

TR: -Zone-Off (switch off the zone)

TR: -Status of the zone (shows whether the zone is on or off)

## Changelog

### 0.0.4 (2021-06-12)
* (TheBam) Paging added and info.connection fixed for admin 5

### 0.0.3 (2021-04-29)
* (TheBam) Cleaning the code

### 0.0.2
* (TheBam) Cleaning the code

### 0.0.1
* (TheBam) First version to control your Trivum Multiroom Systems

## License
MIT License

Copyright (c) 2021 TheBam <elektrobam@gmx.de>

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
SOFTWARE."# ioBroker.trivum"