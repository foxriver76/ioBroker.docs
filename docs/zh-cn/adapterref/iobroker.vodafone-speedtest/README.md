---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.vodafone-speedtest/README.md
title: TR: ioBroker.vofo-speedtest
hash: 2OWK9bGidtbE4CoRu0md2lqebVJMbzOBGqPSf3kx2Iw=
---
![TR: Logo](../../../en/adapterref/iobroker.vodafone-speedtest/admin/vofo-speedtest.png)

![TR: NPM version](http://img.shields.io/npm/v/iobroker.vofo-speedtest.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.vofo-speedtest.svg)
![TR: Number of Installations (latest)](http://iobroker.live/badges/vofo-speedtest-installed.svg)
![TR: Number of Installations (stable)](http://iobroker.live/badges/vofo-speedtest-stable.svg)
![TR: Dependency Status](https://img.shields.io/david/peterbaumert/iobroker.vofo-speedtest.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/peterbaumert/ioBroker.vofo-speedtest/badge.svg)
![TR: NPM](https://nodei.co/npm/iobroker.vofo-speedtest.png?downloads=true)

TR: # ioBroker.vofo-speedtest
TR: **This adapter uses the service [TR: Sentry.io](https://sentry.io) to automatically report exceptions and code errors and new device schemas to me as the developer.** More details see below!

TR: ## vofo-speedtest adapter for ioBroker
TR: Speedtest of Vodafone.de

TR: Implements same technique as https://speedtest.vodafone.de

TR: ## What is Sentry.io and what is reported to the servers of that company?
TR: Sentry.io is a service for developers to get an overview about errors from their applications. And exactly this is implemented in this adapter.

TR: When the adapter crashes or an other Code error happens, this error message that also appears in the ioBroker log is submitted to Sentry. When you allowed iobroker GmbH to collect diagnostic data then also your installation ID (this is just a unique ID **without** any additional infos about you, email, name or such) is included. This allows Sentry to group errors and show how many unique users are affected by such an error. All of this helps me to provide error free adapters that basically never crashs.

TR: ## Disclaimer
TR: Vodafone is a trademark of Vodafone GmbH. I am in no way endorsed by or affiliated with Vodafone GmbH, or any associated subsidiaries, logos or trademarks

## Changelog

### 0.0.7 (2021-05-21)
* Fixed some vulnerabilities in dev-dependencies
* Fixed js-controller 3* issues
* Fixed node 16 compatability

### 0.0.6 (2021-01-21)
* Added Sentry.io Integration

### 0.0.5 (2020-05-26)
* Added ping results
* Added calculated values by actual raw data

### 0.0.4 (2020-04-30)
* Changed Adapter start type to scheduled (reinstallation might be needed)
* Bug fixes and feedback implementation

### 0.0.3 (2020-04-24)
* Implemented feedback from Forum and github issue

### 0.0.2 (2020-04-19)
* Added actual settings in Admin interface
* first version ready for testing

### 0.0.1 (2020-04-18)
* (Peter Baumert) initial release

## License
MIT License

Copyright (c) 2021 Peter Baumert <ioBroker.vofo-speedtest@outlook.com>

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