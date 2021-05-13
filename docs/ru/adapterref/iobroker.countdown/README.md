---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.countdown/README.md
title: TR: ioBroker.countdown
hash: UR3SrC6/ISooSboGsloFdNGal7zBM/aIsqWdrp/Le3c=
---
![TR: Logo](../../../en/adapterref/iobroker.countdown/admin/countdown.png)

![TR: Greenkeeper badge](https://snyk.io/test/github/jack-blackson/ioBroker.countdown/badge.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.countdown.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.countdown.svg)
![TR: Number of Installations](http://iobroker.live/badges/countdown-stable.svg)
![TR: NPM](https://nodei.co/npm/iobroker.countdown.png?downloads=true)

TR: # ioBroker.countdown
[![TR: Build Status Travis](https://travis-ci.com/jack-blackson/ioBroker.countdown.svg?branch=master)](https://travis-ci.com/jack-blackson/ioBroker.countdown)

TR: **This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [TR: Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

TR: Countdown Adapter for ioBroker ------------------------------------------------------------------------------

TR: The goal of the adapter is to provide you a possibility to run countdowns for future events, with years, months, days, hours and minutes. It will provide you each of those valies seperately, and also two strings with a short and long version of the date.

TR: ## Displaying countdowns
TR: The adapter prowides you automatically a json table. You just need to use it with the json table widged. Please tick "No Header" there. It is possible to either display the short text or the long text.
![TR: Logo](../../../en/adapterref/iobroker.countdown/admin/countdown_json.png)

TR: ## How to create countdowns
TR: There are two ways to set up countdowns:

TR: * You can create a countdown in the adapter settings, in the tab "Create Countdown".
TR: * You can create a manual state in the device "setup". The name of the object is the alarm name, and the value will be the date. The date neets to be in the format "DD.MM.YYYY HH:mm:ss".
TR: * You can create an alarm with sendto. There, you can either send the components (minimum is Year Month Date) or a date string. For the date string, you can adjust the format in the setup of the adapter.

![TR: Logo](../../../en/adapterref/iobroker.countdown/admin/countdown_blocky.png)

TR: * You can add days, months and years with sendto to todays date. Therefore, please send the component "name" and either "addminutes", "addhours", "adddays", "addmonths" or "addyears" as int value.

![TR: Logo](../../../en/adapterref/iobroker.countdown/admin/countdown_blocky_add.png)

TR: ## How to delete countdowns
TR: You  can delete a countdown with the sendto. Therefore, send just the name with sendto to the adapter, and the countdown will be deleted automatically.

TR: ## Repeating countdown
TR: If you want a countdown to repeat in a defined period (e.g. you cant a countdown for your wedding day every year) you can also do this with this adapter. Therefore either fill the field "Repeat period" in the settings of the adapter, or add the period after the date when you create a countdown with the type "date". A sendTo would look like that for a countdown which should end on the 1st of April 2020 and repeat every year:

TR: sendTo("countdown.0", "send", { "name": 'Wedding Day', "date": '01.04.2020 00:01+1Y' });

TR: Parameters here are:

TR: * Y: Years
TR: * M: Months
TR: * D: Days
TR: * H: Hours
TR: * m: Minutes

TR: ## Available outputs
| TR: |Data type|Description|
|:---:|:---:|
| TR: |minutes|Minutes until countdown end (not total!)|
| TR: |hours|Hours until countdown end (not total!)|
| TR: |days|Days until countdown end (not total!)|
| TR: |months|Months until countdown end (not total!)|
| TR: |years|Years until countdown end (not total!)|
| TR: |name|Countdown name|
| TR: |endDate|End date of count down - formated as in the setup defined|
| TR: |inWordsShort|Combined value of minutes, hours,... - e.g. 1Y 5M 4D|
| TR: |inWordsLong|Combined value of minutes, hours,... - e.g. 1 Year 5 Months 4 Days|
| TR: |totalHours|Total No. of hours until the end date|
| TR: |totalDays|Total No. of days until the end date|
| TR: |totalWeeks|Total No. of weeks until the end date|
| TR: |reached|Boolean field defining if the end date was reached or not|
| TR: |repeatEvery|Countdown is repeted by this period after reaching the enddate|

TR: ## Features to add
TR: * Possibility to add a script as a parameter and start it when countdown ends
TR: * Possibility to use plus and minus in addminutes and the other add functions

TR: ## 1.2.0 (2021-05-09)
TR: * (jack-blackson) Updated packages, added Sentry
TR: * (jack-blackson) Fixes for JS-controller 3.3
TR: * (jack-blackson) Fix that countdowns are created immediatly

TR: ## 1.1.0 (2020-04-02)
TR: * (jack-blackson) bugfix Read-Me link
TR: * (jack-blackson) bugfix repeatCycle

TR: ## 1.0.9 (2020-03-31)
TR: * (jack-blackson) Bugfix log messages

TR: ## 1.0.8 (2020-03-31)
TR: * (jack-blackson) Repeat countdown in defined period (e.g. every year)

TR: ## 1.0.7 (2020-03-30)
TR: * (jack-blackson) Added new date-type for settings: YYYY-MM-DD
TR: * (jack-blackson) Add countdown directly in adapter settings

TR: ## 1.0.6 (2020-03-20)
TR: * (DutchmanNL) Fixed adapter type

TR: ## 1.0.5 (2020-02-05)
TR: * (jack-blackson) Bugfix for alarm at midnight -> thanks to @Lueghi

TR: ## 1.0.4 (2019-08-25)
TR: * (jack-blackson) Reordered release infos

TR: ## 1.0.3 (2019-08-10)
TR: * (jack-blackson) Changes for Compact Mode
TR: * (jack-blackson) Various bugfixes
TR: * (jack-blackson) Having multiple instances of the adapater are now possible

TR: ## 1.0.2 (2019-07-22)
TR: * (jack-blackson) Release version

TR: ## 0.7.0 (2019-07-07)
TR: * (jack-blackson) Bugfixes
TR: * (jack-blackson) addminutes and addhours are now also possible
TR: * (jack-blackson) datapoint in setup is now editable
TR: * (jack-blackson) added total no. of weeks

TR: ## 0.6.0 (2019-07-06)
TR: * (jack-blackson) adjustable date format for input and output
TR: * (jack-blackson) delete countdowns with sendto
TR: * (jack-blackson) ability to add countdowns by "days/months/weeks from now)

TR: ## 0.5.0 (2019-07-04)
TR: * (jack-blackson) adjust the data in the table
TR: * (jack-blackson) bugfix date import

TR: ### 0.4.0 (2019-06-04)
TR: * (jack-blackson) restructuring - creation of alarms with sendto or manually with datapoint is now possible

TR: ### 0.3.0 (2019-05-24)
TR: * (jack-blackson) added total No. of days and hours

TR: ### 0.2.0 (2019-05-21)
TR: * (jack-blackson) adjusted packages

TR: ### 0.1.0 (2019-04-29)
TR: * (jack-blackson) initial version

## Changelog

## License
The MIT License (MIT)

Copyright (c) 2019-2021 jack-blackson <blacksonj7@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.