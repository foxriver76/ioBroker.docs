---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.sbfspot/README.md
title: TR: ioBroker.sbfspot
hash: AmUOKGNs+9jMar8oo7NBMt5/OVdBe1LIQxXvFOe4zOs=
---
![TR: Logo](../../../en/adapterref/iobroker.sbfspot/admin/sbfspot.png)

![TR: Number of Installations](http://iobroker.live/badges/sbfspot-stable.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.sbfspot.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.sbfspot.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/rg-engineering/ioBroker.sbfspot/badge.svg)
![TR: NPM](https://nodei.co/npm/iobroker.sbfspot.png?downloads=true)

TR: # ioBroker.sbfspot
![TR: GitHub Actions](https://github.com/rg-engineering/ioBroker.sbfspot/workflows/Test%20and%20Release/badge.svg)

TR: **This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [TR: Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

TR: **If you like it, please consider a donation:**

[![TR: paypal](https://www.paypalobjects.com/en_US/DK/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=YBAZTEBT9SYC2&source=url)

TR: This adapter reads data from SMA power inverters using sbfspot.
Now both database types (mySQL and sqlite) are supported.
Since version 0.2.3 there is a own vis widget based on flot available to show historical data.

TR: ## Installation
TR: please follow installation instructions for sbfspot under https://github.com/SBFspot/SBFspot/wiki

[TR: detailed installation on arm based systems](docs/en/install_arm.md)

TR: ## Hints
TR: * use latest version from sbfspot from https://github.com/SBFspot/SBFspot
TR: * adapter, sbfspot and databases (mySQL or sqlite) must run on the same system e.g. Raspberry PI
TR: * installation manual for sbfspot on Raspberry Pi (or similar) can be found under https://github.com/SBFspot/SBFspot/wiki/Installation-Linux-SQLite or https://www.rg-engineering.eu/index.php/produkte/software/plugin-fuer-iobroker-sbfspot
TR: * for Raspberry Pi there is a semi-automated configuration tool available under https://github.com/SBFspot/sbfspot-config

TR: ## known issues
TR: * sometimes installation of npm package sqlite3 fails.

TR: in that case reinstall all npm packages

TR: > cd /opt/iobroker/node_modules/iobroker.sbfspot > sudo npm install

TR: sometimes npm intall must be called more then one time to successfully install all necessray packages

TR: * please create issues at [github](https://github.com/rg-engineering/ioBroker.sbfspot/issues) if you find bugs or whish new features

TR: ## 4.0.4 (2021-02-14)
TR: * (René) dependencies updated

TR: ## 4.0.3 (2021-01-15)
TR: * (René) bug fix based on CI tests

TR: ## 4.0.2 (2020-10-09)
TR: * (René) bug fix based on CI tests

TR: ## 4.0.0 (2020-07-28)
TR: * (René) rework to use async/await
TR: * (René) use mysql2

TR: ## 3.0.0 (2020-04-25)
TR: * (René) sqlite3 package replaced by better-sqlite3
TR: * (René) roles of DP overworked
TR: * (René) see issue #19: get data only when daylight added as an option
TR: * (René) see issue #29: default color for widget axis label changed
TR: * (René) widget: log if widget is too small added

TR: ## 2.4.3 (2020-04-02)
TR: * (René) bugfix in DB_CalcHistory_Today used for widget

TR: ## 2.4.2 (2020-02-01)
TR: * (René) bugfix widget

TR: ## 2.4.0 (2019-12-28)
TR: * (René) update to my own flot 3.0

TR: ## 2.3.4 (2019-10-31)
TR: * (René) update flot to version 3.0

TR: ### 2.3.3 (2019-02-03)
TR: * (René) due to install problems downgrade of sqlite3 package

TR: ### 2.3.1 (2019-02-02)
TR: * (René) bug fix: with sqlite "today" data were not shown

TR: ### 2.3.0 (2019-01-20)
TR: * (René) support of compact mode
TR: * (René) add additional error information in log

TR: ### 2.2.5 (2018-11-26)
TR: * (René) upgrade packages

TR: ### 2.2.5 (2018-11-04)
TR: * (René) reset yield if no new value from today

TR: ### 2.2.4 (2018-08-19)
TR: * (René) bugfix for ticks on X

TR: ### 2.2.3
TR: * (René) the same as 2.2.2

TR: ### 2.2.2
TR: * (René) add timestamp of last update

TR: ### 2.2.1
TR: * (René) close of database connection after last query result is available (e.g. to support more than one inverter)

TR: ### 2.2.0
TR: * (Nis) background color and border
TR: * (René) bug fixes in admin3

TR: ### 2.1.0
TR: * (René) Support MariaDB

TR: ### 2.0.1
TR: * (René) Support of admin3

TR: ### 2.0.0
TR: * (René) since we always use one graph per widget, only one is supported now

TR: 		Attention: widget is not compatible with version 1.x.x; just check settings in widget after installation!

TR: ### 1.1.0
TR: * (René) autoscale of y axis
TR: * (René) color for y axis
TR: * (René) adjustable date format

TR: ### 1.0.1
TR: * (René) bug fix for sqlite

TR: ### 1.0.0
TR: * (René) first stable release

TR: ### 0.2.6
TR: * (René) bug fix for android app > 1.0.6

TR: ### 0.2.5
TR: * (René) use install date to calculate historical values

TR: ### 0.2.4
TR: * (René) logo changed

TR: ### 0.2.3
TR: * (René) adding historical data as datapoint (JSON)
TR: * (René) new vis widget to show historical data

TR: ### 0.2.2
TR: * (René) renamed to sbfspot

TR: ### 0.2.1
TR: * (René) index.html updated

TR: ### 0.2.0
TR: * (René) support of sqlite and license changed to MIT

TR: ### 0.1.1
TR: * (René) UTF8 coding

TR: ### 0.1.0
TR: * (René) first release

TR: ### 0.0.1
TR: * (René) initial release

## Changelog

### 4.0.5 (2021-03-21)
* (René) dependencies updated

## License
Copyright (C) <2017-2021>  <info@rg-engineering.eu>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.