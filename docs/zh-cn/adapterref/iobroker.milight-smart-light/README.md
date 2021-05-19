---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.milight-smart-light/README.md
title: TR: ioBroker.milight-smart-light
hash: 5pIHYWxLRBx9JzitGECa91GS6s7APvK2vcMJLXLqx1Y=
---
![TR: milight-smart-light Logo](../../../en/adapterref/iobroker.milight-smart-light/admin/milight-smart-light.png)

![TR: NPM version](http://img.shields.io/npm/v/iobroker.milight-smart-light.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.milight-smart-light.svg)
![TR: stable](http://iobroker.live/badges/milight-smart-light-stable.svg)
![TR: installed](http://iobroker.live/badges/milight-smart-light-installed.svg)
![TR: Dependency Status](https://img.shields.io/david/steiger04/iobroker.milight-smart-light.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/steiger04/ioBroker.milight-smart-light/badge.svg)
![TR: NPM](https://nodei.co/npm/iobroker.milight-smart-light.png?downloads=true)

TR: # ioBroker.milight-smart-light
![TR: Test and Release](https://github.com/steiger04/ioBroker.milight-smart-light/workflows/Test%20and%20Release/badge.svg)

TR: This adapter for ioBroker controls Milight LED bulbs and LED strips and based on the node module from mwittig.

TR: mwittig / [TR: node-milight-promise](https://github.com/mwittig/node-milight-promise)

TR: With adapter you can use both: **v6 Bridge** and **Legacy Bridge**.

TR: **v6 Bridge:**

TR: - bridge (only iBox1)
TR: - white
TR: - rgb(w)
TR: - fullColor
TR: - fullColor8Zone

TR: **Legacy Bridge:**

TR: - white
TR: - rgb(w)

TR: **Description**

TR: A detailed description can be found [TR: here](https://steiger04.github.io/milight-smart-light-doku/).

TR: ### Versions
TR: - **Node.js**: use v. 10.18.1 or higher
TR: - **iobroker.admin**: use v. 3.5.10 or higher

## Changelog
### 1.2.1 (2020-05-18)
- (steiger04) Compatibility with socketio v3.1.4
### 1.2.0 (2020-01-16)
- (steiger04) compact mode added
### 1.0.5 (2020-01-10)
- (steiger04) Small bug fix
### 1.0.1 (2020-11-21)
- (steiger04) Added admin-UI based on Vue and Quasar
### 0.6.0 (2020-05-23)
- (steiger04): Added effectBrightness, effectOn, effectOff, effectOnOff for iBox1 and iBox2

### 0.5.0 (2020-05-21)
- (steiger04): Bug fix in rgb(w)

## License

The MIT License (MIT)

Copyright (c) 2017-2021 Steiger04 <steiger04@posteo.de>