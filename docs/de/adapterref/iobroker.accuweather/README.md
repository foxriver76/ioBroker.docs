---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.accuweather/README.md
title: TR: ioBroker.accuweather
hash: WdILwFFXh50ulU8fUrumN2VctPbMVRgQq67NIVy8DpY=
---
![TR: Logo](../../../en/adapterref/iobroker.accuweather/admin/accuweather.png)

![TR: NPM version](http://img.shields.io/npm/v/iobroker.accuweather.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.accuweather.svg)
![TR: Dependency Status](https://img.shields.io/david/algar42/iobroker.accuweather.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/algar42/ioBroker.accuweather/badge.svg)
![TR: NPM](https://nodei.co/npm/iobroker.accuweather.png?downloads=true)
![TR: Travis-CI](http://img.shields.io/travis/algar42/ioBroker.accuweather/master.svg)

TR: # ioBroker.accuweather
TR: ## accuweather adapter for ioBroker
TR: Weather forecast using AccuWeather API.

TR: Adapter receives Current Conditions (updated every hour), 5 Days daily forecast (update once daily at approximately 7am), and 12 hours forecast (updated every six hours at 12am, 6am, 12pm and 6pm).

TR: ## Getting started
TR: ### Get API Key
TR: To get API Key, register on https://developer.accuweather.com/ and create application in \"My Apps\" menu. Once the application created, you will have API key generated.
For free use it is possible to make 50 requests to API per day.
It was noted that to get API working the following settings are preferred (please choose your country!): ![TR: settings](../../../en/adapterref/iobroker.accuweather/admin/image.png)

TR: ### Get Location Key
TR: In order to get location key, go to https://www.accuweather.com/ and enter your city name, or try to enter your coordinates (latitude, longitude) as you have them e.g. in ioBroker settings.
Your location key wil be the number at the end of URL of forecast.

TR: ### Using in Lovelace visualization (starting version 1.1.0)
TR: Summary channel contains current and by-day forecast with role/types of states supported by type-detector.
New feature can be used in order to show weather forecast in Lovelace UI.
For better view a custom lovelace card is created - see https://github.com/algar42/IoB.lovelace.accuweather-card

TR: <!-- Placeholder for the next version (at the beginning of the line):

TR: ### __WORK IN PROGRESS__ -->
TR: ## v1.1.6 (2021-05-05) Minor bug fixes to `Object.common` section
TR: ### 1.1.5 (2021-01-25)
TR: * (algar42) Resolve log Warning for js-controller 3.2

TR: ### 1.1.4
TR: * (HGlab01) small bugfix regarding setTimeout range

TR: ### 1.1.3 (2020-03-04)
TR: * (algar42) Minor updates for compact mode

TR: ### 1.1.0 (2019-11-09)
TR: * (algar42) Summary channel added to support type-detector and automatic weather device creation

TR: ### 1.0.2 (2019-09-12)
TR: * (algar42) Production Release

## Changelog
### 1.1.7 (2021-06-24)
* (bluefox) Create device for device-detector

## License
MIT License

Copyright (c) 2021 algar42 <igor.aleschenkov@gmail.com>

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