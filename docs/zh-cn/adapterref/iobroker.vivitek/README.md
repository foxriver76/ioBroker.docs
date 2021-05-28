---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.vivitek/README.md
title: TR: ioBroker.vivitek
hash: t+Ah+LoEx9Tq5fdmj9fc8ljk00si9IGbuXy7TvSePFo=
---
![TR: Logo](../../../en/adapterref/iobroker.vivitek/admin/vivitek.png)

![TR: NPM version](http://img.shields.io/npm/v/iobroker.vivitek.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.vivitek.svg)
![TR: Number of Installations (latest)](http://iobroker.live/badges/vivitek-installed.svg)
![TR: Number of Installations (stable)](http://iobroker.live/badges/vivitek-stable.svg)
![TR: Dependency Status](https://img.shields.io/david/Bannsaenger/iobroker.vivitek.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/Bannsaenger/ioBroker.vivitek/badge.svg)
![TR: NPM](https://nodei.co/npm/iobroker.vivitek.png?downloads=true)

TR: # ioBroker.vivitek
TR: ## vivitek adapter for ioBroker
TR: Control a Vivitek Projector via Network (RS 232 commands via telnet)

TR: The Adapter is designed for communication with a vivitek projector via its telnet interface.
This should behave like the serial port.
Unfortunately the telnet implementation lacks some basic commands.
For now its only possible the communicate via a network to RS232 comserver.
I run it with a Wieseman & Theis Comserver.

TR: ## ToDo
TR: As when the implementation on the projector side gets fully working there should be added more commands to fully control the projector.
As i know for now, the protocol covers a whole family of projectos.

## Changelog

### 0.0.1
* (Bannsaenger) initial release

### 0.0.2
* (Bannsaenger) prepared for checkin to iobroker.latest

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