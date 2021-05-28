---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.solarviewdatareader/README.md
title: TR: ioBroker.solarviewdatareader
hash: DGtXy5iIPV0aJXSBR+TGxY/qUvt9Dhwsqoorf7fJtlU=
---
![TR: Logo](../../../en/adapterref/iobroker.solarviewdatareader/admin/solarviewdatareader.png)

![TR: NPM version](https://img.shields.io/npm/v/iobroker.solarviewdatareader.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.solarviewdatareader.svg)
![TR: Number of Installations (latest)](https://iobroker.live/badges/solarviewdatareader-installed.svg)
![TR: Number of Installations (stable)](https://iobroker.live/badges/solarviewdatareader-stable.svg)
![TR: Dependency Status](https://img.shields.io/david/afuerhoff/iobroker.solarviewdatareader.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/afuerhoff/ioBroker.solarviewdatareader/badge.svg)
![TR: NPM](https://nodei.co/npm/iobroker.solarviewdatareader.png?downloads=true)

TR: # ioBroker.solarviewdatareader
TR: **Tests:** ![TR: Test and Release](https://github.com/afuerhoff/ioBroker.solarviewdatareader/workflows/Test%20and%20Release/badge.svg)

TR: ## solarviewdatareader adapter for ioBroker
TR: The adapter reads the data from the Solarview data logger.
Here you can find additional infos about Solarview: https://www.solarview.info/solarlogger.aspx

TR: ## Configuration
TR: ### IP address, Port
TR: To get the data from the datalogger you must enter the ip-address and the port from your solarview TCP server.
The standard port is 15000. Please refer to the Solarview documentation https://www.solarview.info/solarlogger.aspx.

TR: ### D0 converter
TR: If you have a D0 converter connected to the Solarview data logger you can enable this option.
For questions please refer to the Solarview documentation.

TR: ### Self consumption meter sum and 1 to 4
TR: If you have a S0 meter, you can enable this option.
You can have up to 4 self consumption meters and the sum from all meters.
For questions please refer to the Solarview documentation.

TR: ### Inverter 1 to 4
TR: Every inverter you can enable separately.
For questions please refer to the Solarview documentation.

TR: ### Interval, interval start, interval end
TR: Here you can configure the time range and the interval. The time range for 24h is 00:00 to 23:59.
Not 00:00 to 00:00.

TR: ### Set system variable CCU, System variable
TR: This ist a special feature for the homematic CCU. You can define a system variable in the CCU.
In this system variable the actual PAC value is saved.
You have to fill in the ioBroker state for that system variable -> **e.g. "hm-rega.0.12345"**

TR: ### Created states
TR: #### pvig, pvi1..4, d0supply, d0consumption
TR: daily = daily yield (kWh) montly = monthly yield (kWh) yearly = yearly yield (kWh) total = total yield (kWh) current = generator power in W UDC, UDCB, UDCC, UDCD = generator voltages in volt per MPP-Tracker IDC, IDCB, IDCC, IDCD = generator current in ampere per MPP-Tracker UL1, IL1 = mains voltage, mains power phase 1 UL2, IL2 = mains voltage, mains power phase 2 UL3, IL3 = mains voltage, mains power phase 3 TKK= Temperature inverter

## Changelog
<!--
	Placeholder for the next version (at the beginning of the line):
	### __WORK IN PROGRESS__
-->
### 1.0.2 (2021-05-07)
* (afuerhoff) node.js 14 and 16 compatibilty
* (afuerhoff) dependencies updated

### 1.0.1 (2021-05-01)
* (afuerhoff) changes due to js-controller 3.3.x

### 1.0.0 (2021-04-25)
* (afuerhoff) dependencies updated
* (afuerhoff) documentation changed
* (afuerhoff) minor changes
* (afuerhoff) due to stable state version set to 1.0.0

### 0.2.1
* (afuerhoff) self consumption meter optimized
### 0.2.0
* (afuerhoff) Error handling optimized, self consumption meter implemented

## License
MIT License

Copyright (c) 2019-2021 Achim Fürhoff <achim.fuerhoff@outlook.de>

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