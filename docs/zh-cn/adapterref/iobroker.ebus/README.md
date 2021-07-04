---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.ebus/README.md
title: TR: ioBroker.ebus
hash: hwnSvGdtB2ANX+jFQ3fI09f8e+vlELKqck7xjXfp8Mg=
---
![TR: Logo](../../../en/adapterref/iobroker.ebus/admin/ebus.png)

![TR: Number of Installations](http://iobroker.live/badges/ebus-stable.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.ebus.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.ebus.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/rg-engineering/ioBroker.ebus/badge.svg)
![TR: NPM](https://nodei.co/npm/iobroker.ebus.png?downloads=true)

TR: # ioBroker.ebus
![TR: GitHub Actions](https://github.com/rg-engineering/ioBroker.ebus/workflows/Test%20and%20Release/badge.svg)

TR: **This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [TR: Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

TR: **If you like it, please consider a donation:**

[![TR: paypal](https://www.paypalobjects.com/en_US/DK/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=YBAZTEBT9SYC2&source=url)

TR: This adapter reads

TR: - data from ebusd using html

TR: In this case ebusd must run and must be able to send data to e.g. explorer via http://IP:port/data (http://192.168.0.123:8889/data) Current version of ebusd incl. configuration files can be copied from https://github.com/john30/ebusd All fields with data, lastup and from global section are parsed. All others are ignored at the moment.

TR: There is a possibillity to poll data which are not polled by ebusd directly. Command 'read -f' is used to force reading over ebus.

TR: Another feature is to send any command to ebusd and receive answer to work with e.g. scripts.

TR: current supported ebusd-version: 3.3

TR: ## known issues
TR: * please create issues at [github](https://github.com/rg-engineering/ioBroker.ebus/issues) if you find bugs or whish new features

TR: ## 2.2.7 (2021-07-03)
TR: * (René) dependencies updated
TR: * (René) see issue #48: bug fix for wrong data type logs

TR: ## 2.2.5 (2021-03-21)
TR: * (René) dependencies updated

TR: ## 2.2.4 (2021-02-17)
TR: * (René) see issue #42: Uncaught ReferenceError: oView is not defined in widget solved

TR: ## 2.2.3 (2020-10-24)
TR: * (René) create history DP if not available

TR: ## 2.2.0 (2020-09-06)
TR: * (René) change DP only if necessary to reduce system load
TR: * (René) update dependencies

TR: ## 2.1.1 (2020-06-27)
TR: * (René) issue #26: bug fix: "cmd not found" is only debug message instead of error

TR: ## 2.1.0 (2020-06-17)
TR: * (René) refactoring:  'async/await' used

TR: ## 2.0.0 (2020-04-26)
TR: * (René) "request" replaced by "bent"

TR: ## 1.0.0 (2019-12-15)
TR: * (René) update to my own flot 3.0

TR: ## 0.8.2 (2019-11-10)
TR: * (René) some more error messages in datapoint "error"

TR: ## 0.8.1 (2019-10-31)
TR: * (René) update flot to version 3.0

TR: ### 0.8.0 (2019-02-24)
TR: * (René) hcmode2 value 5 = EVU Sperrzeit

TR: ### 0.7.0 (2019-01-28)
TR: * (René) add adjustable timeout

TR: ### 0.6.0 (2019-01-06)
TR: * (René) support of compact mode

TR: ### 0.5.5 (2018-11-04)
TR: * (René) code clean up

TR: ### 0.5.4
TR: * (René) arduino support removed

TR: ### 0.5.3
TR: * (René) add error information

TR: ### 0.5.2
TR: * (René) bug fix: in vis 1.x some values are not stored

TR: ### 0.5.1
TR: * (René) bug fix: if nothing to poll then skip telnet connection

TR: ### 0.5.0
TR: * (René) write date over TCP to ebusd

TR: ### 0.4.2
TR: * (René) bug fix for admin V3

TR: ### 0.4.1
TR: * (René) logo changed

TR: ### 0.4.0
TR: * (René) reading data from ebusd

TR: ### 0.3.0
TR: * (René) support of ebusd
TR: * (René) admin3 support

TR: ### 0.2.0
TR: * (René) add history as JSON for vis
TR: * (René) add flot based widget to display temperatur, status and power graph

TR: ### 0.1.0
TR: * (René) scheduled adapter instead of deamon

TR: ### 0.0.3
TR: * (René) UTF8 coding

TR: ### 0.0.2
TR: * (René) initial release

## Changelog

## License
Copyright (C) <2017 - 2021>  <info@rg-engineering.eu>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.