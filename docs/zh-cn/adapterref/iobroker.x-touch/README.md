---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.x-touch/README.md
title: TR: ioBroker.x-touch
hash: WIHz2zmoIFHGH8dlrg2iIAKeaishdLYIfWK2QOSAv7c=
---
![TR: Logo](../../../en/adapterref/iobroker.x-touch/admin/x-touch.png)

![TR: NPM version](http://img.shields.io/npm/v/iobroker.x-touch.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.x-touch.svg)
![TR: Number of Installations (latest)](http://iobroker.live/badges/x-touch-installed.svg)
![TR: Number of Installations (stable)](http://iobroker.live/badges/x-touch-stable.svg)
![TR: Dependency Status](https://img.shields.io/david/Bannsaenger/iobroker.x-touch.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/Bannsaenger/ioBroker.x-touch/badge.svg)
![TR: NPM](https://nodei.co/npm/iobroker.x-touch.png?downloads=true)

TR: # ioBroker.x-touch
TR: ## x-touch adapter for ioBroker
TR: Communicate with a Behringer X-Touch Control Surface (DAW Controller)

TR: ## ToDo
TR: - Add the encoders and their LEDs -> done, left is sync_global and checks on database changes
TR: - Add the timecode display
TR: - Add the functionality of bank and fader channel switches -> done, needs additional testing
TR: - Add the syncGlobal functionality

## Changelog

### 0.0.1
* (Bannsaenger) initial release

### 0.0.2
* (Bannsaenger) prepared for checkin to iobroker.latest

### 0.1.0
* (Bannsaenger) introduced channel and page switching

### 0.2.0
* (Bannsaenger) introduced encoders

### 0.2.1
* (Bannsaenger) changed the way to send data. Added sendDelay

### 0.2.2
* (Bannsaenger) fixed fader handling and data distribution to the device group

### 0.2.3
* (Bannsaenger) fixed setting of diplay inverted

## License
MIT License

Copyright (c) 2021 Bannsaenger <bannsaenger@gmx.de>

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