---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.schwoerer-ventcube/README.md
title: TR: ioBroker.schwoerer-ventcube
hash: aBfWMJanRauvuqMhJ8iYqrkhjzBVlq3oBmX+Gd6wvyc=
---
![TR: Logo](../../../en/adapterref/iobroker.schwoerer-ventcube/admin/schwoerer-ventcube.png)

![TR: NPM version](http://img.shields.io/npm/v/iobroker.schwoerer-ventcube.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.schwoerer-ventcube.svg)
![TR: Dependency Status](https://img.shields.io/david/Excodibur/iobroker.schwoerer-ventcube.svg)
![TR: Number of Installations (latest)](http://iobroker.live/badges/schwoerer-ventcube-installed.svg)
![TR: Number of Installations (stable)](http://iobroker.live/badges/schwoerer-ventcube-stable.svg)
![TR: Language grade: JavaScript](https://img.shields.io/lgtm/grade/javascript/g/Excodibur/ioBroker.schwoerer-ventcube.svg?logo=lgtm&logoWidth=18)
![TR: NPM](https://nodei.co/npm/iobroker.schwoerer-ventcube.png?downloads=true)

TR: # ioBroker.schwoerer-ventcube
![TR: Github release status](https://github.com/Excodibur/iobroker.schwoerer-ventcube/workflows/Build%2C%20Test%20and%20Release/badge.svg)

TR: ## schwoerer-ventcube adapter for ioBroker
TR: Adapter for Schwoererhaus Ventcube system. More information about Ventcube Fresh can be found [TR: here](https://www.bauinfocenter.de/lueftung/lueftungsanlagen/).

TR: **Disclaimer**: This adapter is neither developed nor officially supported by the company [TR: Schwoererhaus KG](https://www.schwoererhaus.de/) which distributes the Ventcube system. Instructions should be followed with care and at your own risk.

TR: ### Preconditions
TR: In order to access the network-interface of Ventcube the following (known) preconditions need to be met:

TR: - The Ventcube needs to be connected to your internal network (usually via network-cable)
TR: - Modbus TCP interface needs to be supported (Control-Panel: >= V1.05, VentCube: >= V02.11) and often has to be enabled manually first
TR:     * On Control Panel login to "Service" section (use standard password from docs)
TR: 	* In Basic Settings check that Network Connection is established and "9. Network Interface" and "10. Modbus TCP" are both active.
TR: 	* If the last two settings are not active, activate them and restart the Ventcube (e.g. by cutting the power temporarily)

TR: ### Configuration parameters
TR: Depending on the building-specific Ventcube setup not all parameters that can be retrieved from or changed via the Ventcube interface will be used. Each parameter in the "parameters" folder goes side-by-side with an entry in the "lastUpdate" folder that indicates the last fetch timestamp for each parameter.

TR: All parameters mentioned in the specification referenced below were added to the adapter and can be accessed via ***Advanced Functions*** option that is configurable during adapter deployment. Enabling this option will cause the adapter to periodically retrieve data for 100+ parameters, of which most might not be used in common households. Test scope was limited to ***Basic Functions*** (enabled by default).

TR: The following default config-values likely will need to be changed during adapter deployment for it to connect to Ventcube properly:

| TR: | Parameter                             | Default Value | **Should be**                                         | Explanation |
| TR: | `Server`                              | localhost     | ***HERMES-LT*** or ***local network IP of Ventcube*** | Default value is used for tests and definitely needs to be changed! |
| TR: | `Port`                                | 10502         | ***502***                                             | Default value is used for tests and definitely needs to be changed! |
| TR: | `Interval`                            | 30            | 30                                                    | After how many seconds should metrics be refreshed from server |
| TR: | `Request Timeout`                     | 5000          | 5000                                                  | How many milliseconds to wait until requests to Ventcube time out |
| TR: | `Reconnection Attempts`               | 10            | 10                                                    | In case connection is lost to Ventcube, how many times a reconnect should be attempted |
| TR: | `Delay between reconnection attempts` | 10000         | 10000                                                 | How long to wait between reconnection attempts (in milliseconds) |
| TR: | `Advanced Functions`                  | &#10003;      |                                                       | While basic functions might be sufficient if Ventcube is just used for air ventilation, advanced functions should be activated if heating/cooling functions, or system metrics (error codes, fan details) are needed. |
| TR: | `Advanced Functions`                  | &#10003;      |                                                       | While basic functions might be sufficient if Ventcube is just used for air ventilation, advanced functions should be activated if heating/cooling functions, or system metrics (error codes, fan details) are needed. |

TR: #### Interesting functions (to start with)
TR: - ***Betriebsart***, changeable
TR: - ***Stoßlüftung*** (30 minute level 4 air burst), changeable
TR: - ***Ist Temp Raum 1*** (temperature inside house)
TR: - ***T10 Außentemperatur***

TR: ### Reference system
TR: The ioBroker adapter was tested sucessfully with:

| TR: | Control Panel | Ventcube | Modbus specification              |
|---------------|----------|-----------------------------------|
| TR: | V01.10        | V02.26   | [TR: Parameterliste_Modbus_TCP_03.2020](https://schwoerer-service.com/storage/files/Community/2020/Parameterliste_Modbus_TCP_032020.pdf) |

## Changelog
See [Changelog](https://github.com/Excodibur/ioBroker.schwoerer-ventcube/blob/master/CHANGELOG.md).

## License
MIT License

Copyright (c) 2020-2021 Excodibur

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