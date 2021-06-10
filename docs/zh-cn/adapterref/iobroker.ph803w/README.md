---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.ph803w/README.md
title: TR: ioBroker.ph803w
hash: 8wZbHpuiBtQyAgZqIYG/VC/asesHfdIonX8K+2YJby0=
---
![TR: Logo](../../../en/adapterref/iobroker.ph803w/admin/ph803w.png)

![TR: Number of Installations](http://iobroker.live/badges/ph803w-stable.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.ph803w.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.ph803w.svg)

TR: # ioBroker.ph803w
TR: ![TR: Test and Release](https://github.com/Apollon77/iobroker.ph803w/workflows/Test%20and%20Release/badge.svg) [![TR: Translation status](https://weblate.iobroker.net/widgets/adapters/-/ph803w/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

TR: ## ph803w adapter for ioBroker
TR: **This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [TR: Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

TR: Query PH and Redox values from PH803-W devices in your network.

TR: ## Configuration
TR: The adapter do not need any configuration. It will automatically discover PH803W devices via UDP packages in your network. This means that the ioBroekr server and the device needs to be in the same network.
Discovery is done on adapter start which means that to discover new devices added while adapter is running might need an adapter restart.

TR: ## Todo
TR: * enhance testing: state checks and setState's
TR: * if needed allow to specify the local network interface to listen for UDP packages
TR: * if needed allow adding own devices by IP if discovery is not working
TR: * if needed add a state to send out another discovery package during run of the adapter to allow discovery of new devices without adapter restart

TR: ## How to report issues and feature requests
TR: Please use GitHub issues for this.

TR: Best is to set the adapter to Debug log mode (Instances -> Expert mode -> Column Log level). Then please get the logfile from disk (subdirectory "log" in ioBroker installation directory and not from Admin because Admin cuts the lines). If you do not like providing it in GitHub issue you can also send it to me via email (iobroker@fischer-ka.de). Please add a reference to the relevant GitHub issue AND also describe what I see in the log at which time.

## Changelog

### 0.1.5 (2021-06-09)
* (Apollon77) Optimize edge cases on device connection and try reconnect and make sure connection status is correct
* (Apollon77) Better handle pingpong related reconnects

### 0.1.4 (2021-06-09)
* (Apollon77) Remove unit from PH again after feedback

### 0.1.3 (2021-06-09)
* (Apollon77) Add title property

### 0.1.2 (2021-06-09)
* (Apollon77) Add unit for PH value

### 0.1.1 (2021-06-09)
* (Apollon77) Initial commit

## License
MIT License

Copyright (c) 2021 Ingo Fischer <github@fischer-ka.de>

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