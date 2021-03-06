---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.binance/README.md
title: !!!
hash: BSYnXyUI001V3VbS9LwVPs800MPSIjbRqcpcK7c2COY=
---
# !!!

![TR: NPM version](http://img.shields.io/npm/v/iobroker.binance.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.binance.svg)
![TR: Number of Installations (latest)](http://iobroker.live/badges/binance-installed.svg)
![TR: Number of Installations (stable)](http://iobroker.live/badges/binance-stable.svg)
![TR: Dependency Status](https://img.shields.io/david/Kartax/iobroker.binance.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/Kartax/ioBroker.binance/badge.svg)
![TR: NPM](https://nodei.co/npm/iobroker.binance.png?downloads=true)

TR: # Please note, that this plugin/repository is discontinued (open for adoption)
# !!!
![TR: Logo](../../../en/adapterref/iobroker.binance/admin/binance.png)

TR: # ioBroker.binance
TR: ## Introduction
TR: Adapter to communicate with the crypto trading platform binance

TR: The adapter pulls prices of currencies in the configured update interval.
If you configure an API Key and the corresponding secret, it will pull account balances as well.
You may create an API Key on binance.com - i suggest to restrict it to "read-only".

![TR: screenshot-1](screenshot-1.png) ![screenshot-2](../../../en/adapterref/iobroker.binance/screenshot-2.png)

## Changelog
### 1.1.3
- dependency update: lodash
### 1.1.2
- version label fix
### 1.1.1
- Possibility to disabled download of all prices. Polished options and translations.
### 1.1.0
- added 24hr data for selected symbols
### 1.0.5
- fixed interval handle
### 1.0.4
- npmjs repackage
### 1.0.3
- enrypted storage of apiKeySecret
### 1.0.2
- added translations
- additonal timeout options
- Travis CI
### 1.0.1
- some loggin cleanup
- adjusted documentation
### 1.0.0
- first fully functional release (polling of prices and account balances)
- introduces cropty-js to accomplish binance quthentication requirements
- moved from type schedule to daemon with setTimeout

## License
MIT License

Copyright (c) 2020 Kartax

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