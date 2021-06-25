---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.myvbus/README.md
title: TR: ioBroker.myvbus
hash: vrblLAmPDLheq6IrG8M5j1mev6UNtfmV+UTYNM4yR74=
---
![TR: Number of Installations (latest)](http://iobroker.live/badges/myvbus-installed.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.myvbus.svg)
![TR: Number of Installations (stable)](http://iobroker.live/badges/myvbus-stable.svg)
![TR: NPM version](https://img.shields.io/npm/v/iobroker.myvbus.svg)
![TR: Dependency Status](https://img.shields.io/david/iobroker-community-adapters/iobroker.myvbus.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/iobroker-community-adapters/ioBroker.myvbus/badge.svg)
![TR: NPM](https://nodei.co/npm/iobroker.myvbus.png?downloads=true)
![TR: Travis-CI](http://img.shields.io/travis/iobroker-community-adapters/ioBroker.myvbus/master.svg)

TR: # ioBroker.myvbus
![TR: Logo](../../../en/adapterref/iobroker.myvbus/admin/myvbus.png)

TR: ## ioBroker Adapter for Resol VBus
TR: This adapter connects ioBroker to various VBus-based devices using resol-vbus, a JavaScript library for the acquisition of RESOL VBus data, provided by Daniel Wippermann.

TR: <https://github.com/danielwippermann/resol-vbus>

TR: <https://www.npmjs.com/package/resol-vbus>

TR: ## Features
TR: * Enables reading of the measurement data from various RESOL(R) VBus(R) devices - preferably solar and system controllers from the DeltaSol(R) series including built-in heat quantity meters (HQM) - using DL3 or DL2 data loggers, KM2 communication modules, VBus/LAN interface adapters or serial/LAN gateways locally via TCP/IP.
TR: * Device access using the VBus/USB serial interface adapter or via VBus.net(R) using DLx/KMx is also supported.
TR: * Processes live VBus data streams and makes them available as ioBroker states.
TR: * Values are updated with a configurable cycle time.
TR: * Reading or setting the VBus device configuration parameters is not supported. The tools provided by Resol should be used for this, e.g. via VBus.net or the parameterization tool RPT.
TR: * Reading DL3 channel 0 (sensors directly connected to the DL3 device) is not supported due to limitations of the DL3 interface.

TR: ## Configuration hints
TR: * The default setting for the connection type is VBus/LAN, but it must be explicitly selected even for VBus/LAN, otherwise no connection will be established.
TR: * The correct settings for direct LAN access for VBus/LAN, DL3, DL2, KM2 are:
TR:   * Connection type: VBus/LAN or KM2 or DL2 or DL3
TR:   * Connection identifier: IP address (e.g. 192.168.178.188) or FullyQualifiedHostName (e.g. host1.example.com)
TR:   * VBus password: YourVBusPassword (default: vbus)
TR:   * Connection port: Default setting 7053 should not be changed
TR:   * DL3 channel: Only relevant for DL3 (values 1-6, channel 0 can not be read out)
TR:   * Update interval: Time between updates of the measured values (default 30s)
TR: * The correct settings for the DL3, DL2, KM2 access via VBus.net are:
TR:   * Connection type: DL3 or DL2 or KM2
TR:   * Connection identifier: vbus.net (or vbus.io) - both without http:// and Via identifier!
TR:   * Connection port: Default setting 7053 should not be changed
TR:   * VBus password: YourVBusPassword (default: vbus)
TR:   * DL3 channel: Only relevant for DL3 (values: 1-6, channel 0 cannot be read out)
TR:   * Via identifier: YourViaIdentifier (e.g. d1234567890) - without http:// before or .vbus.io behind
TR:   * Update interval: Time between the update of the measured values (default 30s)

TR: ## Legal Notices
TR: RESOL, VBus, VBus.net, DeltaSol and others are trademarks or registered trademarks of RESOL - Elektronische Regelungen GmbH <https://www.resol.de/en>

TR: All other trademarks are the property of their respective owners.
The authors are in no way endorsed by or affiliated with RESOL GmbH, or any associated subsidiaries, logos or trademarks.

## Changelog
### 0.1.1 (2021-05-18)
* Fixes for supporting js-controller >=3.2.x


### 0.1.0
* (grizzelbee) Fix: config page shows current settings now (not default anymore)
* (grizzelbee) Fix: "Connected" state is updated correctly now if connection is disrupted.
* (grizzelbee) New: Added Badge for latest(npm) version to readme
* (grizzelbee) Fix: removed default password from config to ensure it's encrypted on first config
* (grizzelbee) Fix: removed Force-ReInit
* (grizzelbee) Fix: sensor maintenance indicators are booleans now
* (grizzelbee) New: added activity indicator states for relays
* (pdbjjens) Fix: Prevent warnings regarding non-existent objects upon adapter instance creation and start-up with js-controller 3.2.x
* (pdbjjens) Fix: updated dependencies and vulnerabilities

### 0.0.6
* (pdbjjens) alpha 6 release updated dependencies

### 0.0.5
* (pdbjjens) alpha 5 release improved type and role mapping of adapter values

### 0.0.4
* (pdbjjens) alpha 4 release updated dependency on resol-vbus library to 0.21.0

### 0.0.3
* (pdbjjens) alpha 3 release tested with DL3 over local LAN and VBus.net and DeltaSol SLT (0x1001) incl. HQM (0x1011)

### 0.0.2
* (pdbjjens) alpha 2 release tested with VBus/LAN, KM2, VBus.net and DeltaSol E (0x7721 & 0x7722), DeltaSol M (0x7311 & 0x716), DeltaSol CS Plus (0x2211), Oventrop RQXXL (0x7541)

### 0.0.1

* (pdbjjens) initial release tested only with VBus/USB (Serial) and DeltaSol(R) BS2009 (0x427B)

## License

MIT License

Copyright (c) 2021 Jens-Peter Jensen <jjensen@t-online.de>

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