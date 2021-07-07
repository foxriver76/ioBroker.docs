---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.yr/README.md
title: TR: ioBroker.yr
hash: kHJRFHx1Jtc5V1ZJAdTrNxLCKuWfpgZQIgTYS78ts54=
---
![TR: Logo](../../../en/adapterref/iobroker.yr/admin/yr.png)

![TR: Number of Installations](http://iobroker.live/badges/yr-stable.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.yr.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.yr.svg)

TR: # ioBroker.yr
TR: ![TR: Test and Release](https://github.com/ioBroker/ioBroker.yr/workflows/Test%20and%20Release/badge.svg) [![TR: Translation status](https://weblate.iobroker.net/widgets/adapters/-/yr/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

TR: **This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [TR: Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

TR: ## yr.no adapter for ioBroker
TR: fetches 10d weather forecast from [TR: yr.no](yr.no)

[TR: yr.no](yr.no) is a joint service by the [Norwegian Meteorological Institute](met.no) and the [Norwegian Broadcasting Corporation](nrk.no)

TR: https://api.met.no/weatherapi/locationforecast/2.0/documentation

TR: **Note** - if _"Send missing translations to iobroker.net"_ is activated (default) missing translations will be sent to iobroker.net server. No IPs or any additional info will be stored or analysed. Just missing translation.

TR: ## Icons
TR: Icons are taken from here [TR: https://api.met.no/weatherapi/weathericon/2.0/documentation](https://api.met.no/weatherapi/weathericon/2.0/documentation) and belongs to yr.no.

TR: ## TODO
TR: * Add meteogram (png probably will discontinue with new API)
TR: * Add daily forecast based on hourly forecast
TR: * Add html table

TR: <!-- Placeholder for the next version (at the beginning of the line):

TR: ### __WORK IN PROGRESS__ -->
TR: ## 1.0.4 [2016-07-06]
TR: * (bluefox) fix link to readme

TR: ### 1.0.3 [2016-05-17]
TR: * (bluefox) change readme path

TR: ### 1.0.2 [2016-05-16]
TR: * (bluefox) add translations

TR: ### 1.0.1 [2016-04-25]
TR: * (bluefox) add translations

TR: ### 1.0.0 [2016-03-15]
TR: * (bluefox) change parsing of cities

TR: ### 0.1.9 [2015-10-28]
TR: * (bluefox) fix error with translations

TR: ### 0.1.8 [2015-10-27]
TR: * (bluefox) translations
TR: * (bluefox) automatically upload of missing translations to iobroker.net

TR: ### 0.1.7 [2015-07-10]
TR: * (bluefox) make yr works with metro widgets

TR: ### 0.1.6 [2015-06-12]
TR: * (bluefox) translations

TR: ### 0.1.5 [2015-03-26]
TR: * (bluefox) translations

TR: ### 0.1.4 [2015-03-24]
TR: * (bluefox) remove unit "%" for "wind direction"

TR: ### 0.1.3 [2015-03-22]
TR: * (bluefox) fix error with tomorrow and day after tomorrow

TR: ### 0.1.2 [2015-03-08]
TR: * (bluefox) correct links to yr.no web site

TR: ### 0.1.1
TR: * (bluefox) add translates for the weather states in other languages

TR: ### 0.1.0
TR: * (bluefox) update yr on the new objects model

TR: ### 0.0.4
TR: * (hobbyquaker) prepend "forecast." to state IDs

TR: ### 0.0.3
TR: * (hobbyquaker) settings ui with autocomplete for location
TR: * (hobbyquaker) renamed yr_forecast to forecast
TR: * (hobbyquaker) added children attribute
TR: * (hobbyquaker) decreased log verbosity
TR: * (hobbyquaker) fixes

TR: ### 0.0.2
TR: * (hobbyquaker) fixes

TR: ### 0.0.1
TR: * (hobbyquaker) first release

TR: ## Todo
TR: * setState forecast_object

## Changelog

### 3.0.1 (2021-07-06)
* (Apollon77) Optimizations and Fixes
* (Apollon77) Add Sentry crash reporting

### 3.0.0 [2021-06-06]
* (withstu) Switch to new JSON API and change data Structure (breaking)
* (withstu) Update project dependencies
* (arteck) Type of state was corrected  

### 2.0.3 [2018-10-10]
* (bluefox) add translations

### 2.0.2 [2018-08-01]
* (bluefox) Warning! Breaking changes! States are renamed.
* (bluefox) Refactoring of states and roles

### 1.0.6 [2017-05-27]
* (Andre) Update iconset

### 1.0.5 [2016-10-10]
* (bluefox) move weather widgets to this adapter

## License
The MIT License (MIT)

Copyright (c) 2014-2021 hobbyquaker <hq@ccu.io>, Bluefox

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