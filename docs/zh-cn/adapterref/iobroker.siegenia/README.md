---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.siegenia/README.md
title: TR: ioBroker.siegenia
hash: rHbPlGxnGQWGgWc6lrO0q1AyYILl0gKk7ZcQ7fSvqw4=
---
![TR: Number of Installations](http://iobroker.live/badges/siegenia-stable.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.siegenia.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.siegenia.svg)

TR: # ioBroker.siegenia
TR: <img src="./admin/siegenia_logo.jpg"/>

TR: ![TR: Test and Release](https://github.com/Apollon77/ioBroker.siegenia/workflows/Test%20and%20Release/badge.svg) [![TR: Translation status](https://weblate.iobroker.net/widgets/adapters/-/siegenia/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

TR: **This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [TR: Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

TR: This adapter provides ioBroker support for Siegenia Climate and Air control Devices (https://www.siegenia.com).

TR: The adapter requires minimum Nodejs 8.x.

TR: ## Featureset
TR: All current devices are support by this adapter:

TR: * AEROPAC
TR: * AEROMAT VT
TR: * DRIVE axxent DK/MH
TR: * SENSOAIR
TR: * AEROVITAL ambience
TR: * MHS Family
TR: * AEROTUBE
TR: * Universal Module

TR: The adapter is capable to automatically detect the Siegenia devices in the same network as ioBroker and will list them in it's Admin interface. You only need to correct the user and password after the detection. But you can also enter IPs and login data manually.

TR: All available data fields of the detected device are shown in objects and provide current data and/or allow data to be changed.

TR: Timers and other more complex data are shown by the adapter, but can be changed only through the Siegenia App.

## Changelog

### 1.1.1 (2021-07-06)
* (thost96/Apollon77) Optimize for js-controller 3.3

### 1.1.0 (2021-01-22)
* (Apollon77) Prevent crash case (Sentry IOBROKER-SIEGENIA-1)
* (Apollon77) js-controller 2.0 is now required at least

### 1.0.1 (2020-12-24)
* (Apollon77) update dependencies
* (Apollon77) disconnect device if authentication was not successful

### 1.0.0
* (Apollon77) initial release

## License
MIT License

Copyright (c) 2019-2021 Apollon77 iobroker@fischer-ka.de

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