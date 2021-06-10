---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.meteoalarm/README.md
title: TR: ioBroker.meteoalarm
hash: WTSAKgVijJSIgYS1KHyy/KSxzMFRzASqr8S3BdDDI+A=
---
![TR: Logo](../../../en/adapterref/iobroker.meteoalarm/admin/meteoalarm.png)

![TR: NPM version](http://img.shields.io/npm/v/iobroker.meteoalarm.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.meteoalarm.svg)
![TR: Number of Installations](http://iobroker.live/badges/meteoalarm-stable.svg)
![TR: NPM](https://nodei.co/npm/iobroker.meteoalarm.png?downloads=true)

TR: # ioBroker.meteoalarm
TR: **This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [TR: Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

TR: meteoalarm Adapter for ioBroker ------------------------------------------------------------------------------ This adapter is pulling weather alarms from meteoalarm.eu, which includes wind, snow, rain, high and low temperature,etc. This information is available in local language and for detailed regions.

TR: ## How to use it
TR: There are two options how you can get the link to retrieve the meteoalarm information.

TR: Option 1: Choose your country, then press "load region", and then choose the region. The xml is then filled automatically. Just press save and you are ready.

TR: Option 2: Go to http://meteoalarm.eu and choose your region. Then go to the RSS symbol on the top right side, do a right click and copy the link. This is the link which you please add to the setup of the adapter.

![TR: Logo](../../../en/adapterref/iobroker.meteoalarm/screenshot.png)

TR: ## Available fields
| TR: |Field Name|Description|
|:---:|:---:|
| TR: |Last Update|Date when the adapter received data the last time|
| TR: |Link|Link to the RSS Feed|
| TR: |Location|Alarm Location|
| TR: |Publication Date|Publication Date of the alarm according to the website|
| TR: |HTMLToday|HTML Widget that displays Alarms for today|
| TR: |Weather Map Country|HTML Link to Weather Map of the Alarm Country|
| TR: |Today/Tomorrow|These datapoints are available for today and tomorrow:|
| TR: |   Text|Alarm Text in country specific language|
| TR: |   From|Alarm starting date|
| TR: |   To|Alarm ending date|
| TR: |   Type|Type of Alarm as number|
| TR: |   TypeText|Type of Alarm as text|
| TR: |   Level|Level of Alarm as number|
| TR: |   LevelText|Level of Alarm as text|
| TR: |   Color|Alarm color for widgets|
| TR: |   Icon|Alarm type icon|

TR: ## Alarm Types
| TR: |Alarm Type|Description|
|:---:|:---:|
| TR: |1|Wind|
| TR: |2|Snow/Ice|
| TR: |3|Thunder & Lightning|
| TR: |4|Fog|
| TR: |5|High temperature|
| TR: |6|Low temperature|
| TR: |7|Coast Event|
| TR: |8|Forrest fire|
| TR: |9|Avalanche|
| TR: |10|Rain|
| TR: |11|Unknown|
| TR: |12|Flood|
| TR: |13|Rain-Flood|

TR: ## Setup
TR: "No Background Color in HTML Widget": Ability to use the HTML Widget without background color (e.g. if you want to use the color object to fill your whole widget, not just the html widget)

TR: "Define Warning colors": Ability to define the colors for the various alarm levels in HEX code. Used for HTML widget and also for the color object to manually assign it to another widget

TR: "Use white icons": Use white icons instead of black ones

TR: "No symbols in widget": Don't use the symbol in the HTML widget. You can still access it in the objects. This is usefill if you want to show the icon seperatly from the widget - e.g. in a bigger size.

TR: ## Alarm Levels
| TR: |Alarm Level|Description|
|:---:|:---:|
| TR: |Green|There is no warning available at the moment.|
| TR: |Yellow|The weather is potentially dangerous. The predicted weather phenomena are not unusual, but increased attention should be paid to activities exposed to meteorological risks. Keep yourself informed about the meteorological conditions to be expected and do not take any avoidable risks.|
| TR: |Orange|The weather is dangerous. Unusual meteorological phenomena have been predicted. Damage and accidents are likely. Be very attentive and careful and keep up to date with the expected meteorological conditions. |
| TR: |Red|The weather is very dangerous. Unusually intense meteorological phenomena were predicted. Extreme damage and accidents, often over large areas, threaten life and property. |

TR: ## Supported countries
TR: * Austria
TR: * Croatia
TR: * Czech Republic
TR: * Finnland
TR: * Germany
TR: * Greece
TR: * Hungary
TR: * Ireland
TR: * Israel
TR: * Italy
TR: * Latvia
TR: * Lithuania
TR: * Luxembourg
TR: * Malta
TR: * Moldova
TR: * Montenegro
TR: * Netherlands
TR: * Norway
TR: * Poland
TR: * Romania
TR: * Serbia
TR: * Slovakia
TR: * Spain
TR: * Switzerland
TR: * Sweden

TR: If you don't find your country, please create an issue on github, and I will be happy to add it

TR: ## Not possible countries
TR: * France (no rss feed available)
TR: * Portugal (no splitting possible)
TR: * Slovenia (no rss feed available)

TR: ## Features to implement
TR: * Handle multiple alarms on one day

TR: ## 1.2.1 (2021-06-05)
TR: * (jack-blackson) Bugfix to handle incorrect XML (if country instead of region is used)
TR: * (jack-blackson) Added Luxembourg

TR: ## 1.2.0 (2021-05-16)
TR: * (jack-blackson) New Setup: "No Background Color in HTML Widget", "Define Warning colors" and "Use white icons"
TR: * (jack-blackson) New Icons

TR: ## 1.1.11 (2021-05-09)
TR: * (jack-blackson) Package Updates

TR: ## 1.1.9 (2021-05-07)
TR: * (jack-blackson) Package Updates

TR: ## 1.1.5 (2021-05-02)
TR: * (jack-blackson) Bugfix JS-Controller 3.3.1 errors, error handling no language defined

TR: ## 1.1.4 (2021-04-05)
TR: * (jack-blackson) Handle ENOTFOUND error message, added Sentry

TR: ## 1.1.3 (2021-03-29)
TR: * (jack-blackson) Error fixes adapter checker

TR: ## 1.1.2 (2021-03-29)
TR: * (jack-blackson) Bugfix for not working data update, removed link autogeneration due to CORS errors

TR: ## 1.1.1 (2020-10-28)
TR: * (jack-blackson) Bugfix HTML Data

TR: ## 1.1.0 (2020-03-29)
TR: * (jack-blackson) Bugfix Germany

TR: ## 1.0.9 (2020-02-06)
TR: * (jack-blackson) Bugfix Germany

TR: ## 1.0.8 (2019-11-15)
TR: * (jack-blackson) Added Poland, Moldova, Greece, Romania
TR: * (jack-blackson) Added new Datapoint to get Link to Weather Map

TR: ## 1.0.7 (2019-11-13)
TR: * (jack-blackson) Added Czech Republic, Ireland, Israel, Lithuania, Latvia, Montenegro, Malta, Serbia, Sweden

TR: ## 1.0.6 (2019-10-19)
TR: * (jack-blackson) Added Switzerland & Slowakia

TR: ## 1.0.5 (2019-09-22)
TR: * (jack-blackson) Small logging adjustments

TR: ## 1.0.4 (2019-09-11)
TR: * (jack-blackson) Travis error

TR: ## 1.0.3 (2019-09-09)
TR: * (jack-blackson) Small bugfixes, change from type "deamon" to "schedule"

TR: ## 1.0.2 (2019-08-25)
TR: * (jack-blackson) Reordered release infos

TR: ### 1.0.1 (2019-08-18)
TR: * (jack-blackson) Bugfix no alarm icon

TR: ### 1.0.0 (2019-08-12)
TR: * (jack-blackson) Release version

TR: ### 0.6.0 (2019-08-05)
TR: * (jack-blackson) Store weather icons local in adapter

TR: ### 0.5.0 (2019-07-21)
TR: * (jack-blackson) Handle Timeouts
TR: * (jack-blackson) Translations for all languages
TR: * (jack-blackson) URL checks

TR: ### 0.4.0 (2019-07-20)
TR: * (jack-blackson) Added data for NL,NO,HR,FI,ES
TR: * (jack-blackson) Added Type Text, Type is now empty if Level is 1 (No Warning)
TR: * (jack-blackson) Adjusted colors

TR: ### 0.3.0 (2019-07-13)
TR: * (jack-blackson) Added HTML Widget
TR: * (jack-blackson) Bugfix icon

TR: ### 0.2.0 (2019-07-12)
TR: * (jack-blackson) Added "Tomorrow" data

TR: ### 0.1.0 (2019-07-11)
TR: * (jack-blackson) initial version

TR: ## Credits
TR: Bell in icon designed by Freepik from www.flaticon.com

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