---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.twinkly/README.md
title: TR: ioBroker.twinkly
hash: /lG0DQSc6EvjJOdXRtxZRURjSWcr9Iiujz1V4IHVEOE=
---
![TR: Logo](../../../en/adapterref/iobroker.twinkly/admin/twinkly.png)

![TR: Number of Installations (latest)](http://iobroker.live/badges/twinkly-installed.svg)
![TR: Number of Installations (stable)](http://iobroker.live/badges/twinkly-stable.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.twinkly.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.twinkly.svg)
![TR: Dependency Status](https://img.shields.io/david/patrickbs96/iobroker.twinkly.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/patrickbs96/ioBroker.twinkly/badge.svg)
![TR: NPM](https://nodei.co/npm/iobroker.twinkly.png?downloads=true)
![TR: AppVeyor](https://ci.appveyor.com/api/projects/status/github/patrickbs96/ioBroker.twinkly?branch=master&svg=true)

TR: # ioBroker.twinkly
TR: **Tests:** Linux/Mac: [![TR: Travis-CI](https://travis-ci.com/patrickbs96/ioBroker.twinkly.svg)](https://travis-ci.com/github/patrickbs96/ioBroker.twinkly)

TR: ## twinkly adapter for ioBroker
TR: Adapter to communicate with the [TR: Twinkly lights](https://www.twinkly.com/).

TR: **This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [TR: Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

TR: ## Settings
TR: The following Settings are available: ![TR: admin.png](../../../en/adapterref/iobroker.twinkly/img/admin.png)

TR: In the table you can add all the Twinkly lights you want to control.

| TR: | Column       | Description                        |
| ------------ | ---------------------------------- |
| TR: | `Enabled`    | Shall this connection be accessed  |
| TR: | `IP Address` | IP-Address to the Twinkly Lights   |
| TR: | `IP Address` | IP-Address to the Twinkly Lights   |

TR: The following additionals States are created per device when checked:

TR: * Device Info (read)
TR: * Network Status (read)
TR: * MQTT (read/write)

[TR: Private API information](https://xled-docs.readthedocs.io/en/latest/) by [Pavol Babinčák](https://github.com/scrool)

## Changelog

### 0.1.x
* 8 - (patrickbs96) Changes from the Review
* 6 - (patrickbs96) Update dependencies
* 5 - (patrickbs96) Prevent Crash Case at HTTP Error (Sentry IOBROKER-TWINKLY-3)
* 4 - (patrickbs96) Temporary removing Reset as API path not exists
* 1 - (patrickbs96) Prevent Crash Case at HTTP Error (Sentry IOBROKER-TWINKLY-3)

### 0.0.x
* 10 - (patrickbs96) Restructured CreateStates (dynamic)
*  9 - (patrickbs96) Network-Status (read)
*  8 - (patrickbs96) Transform JSON into states: Details, MQTT and Timer
*  7 - (patrickbs96) Moved Twinkly Connection into own library
*  6 - (patrickbs96) Implemented Ping to check if Twinkly is connected. `Connected State` is no longer needed.
*  3 - (patrickbs96) finalized Admin and Coding
*  1 - (patrickbs96) initial release

## License
MIT License

Copyright (c) 2021 patrickbs96 <patrickbsimon96@gmail.com>

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