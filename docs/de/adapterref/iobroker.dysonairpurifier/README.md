---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.dysonairpurifier/README.md
title: TR: ioBroker.dysonAirPurifier
hash: O6SB+OXHA3GdSIb3tZpGPsvoVJplaZxuEOC575VGttE=
---
![TR: Number of Installations (latest)](http://iobroker.live/badges/dysonairpurifier-installed.svg)
![TR: NPM version](https://img.shields.io/npm/v/iobroker.dysonairpurifier.svg)
![TR: Number of Installations (stable)](http://iobroker.live/badges/dysonairpurifier-stable.svg)
![TR: Dependency Status](https://img.shields.io/david/Grizzelbee/iobroker.dysonairpurifier.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/Grizzelbee/ioBroker.dysonairpurifier/badge.svg)
![TR: Travis-CI](https://travis-ci.org/Grizzelbee/iobroker.dysonairpurifier.svg?branch=master)
![TR: NPM](https://nodei.co/npm/iobroker.dysonAirPurifier.svg?downloads=true)
![TR: License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.dysonairpurifier.svg)

TR: # ioBroker.dysonAirPurifier
![TR: Logo](admin/dyson_logo.svg)![Logo](../../../en/adapterref/iobroker.dysonairpurifier/admin/dyson_pure_cool.jpg)

TR: ## ioBroker Adapter for Dyson Air Purifiers and fans
TR: This adapter connects ioBroker to various Dyson Air Purifiers.

TR: Fan-Icon in Logo created by [TR: Freepik](https://www.flaticon.com/de/autoren/freepik) from [www.flaticon.com](https://www.flaticon.com/de/).

TR: ### supported devices
TR: * Dyson Pure Cool Link Tower (TP02, ProductType 475)
TR: * Dyson Pure Cool Tower, 2018 model (TP04, ProductType 438)
TR: * Dyson Pure Cool Tower, 2018 model (TP07, ProductType 438E)
TR: * Dyson Pure Cool Link Desk (DP01, ProductType 469)
TR: * Dyson Pure Cool Desk, 2018 model (DP04, ProductType 520)
TR: * Dyson Pure Hot+Cool Link (HP02, ProductType 455)
TR: * Dyson Pure Hot+Cool, 2018 model (HP04, ProductType 527)
TR: * Dyson Pure Hot+Cool (HP07, ProductType 527E)
TR: * Dyson Pure Humidify+Cool (PH01, ProductType 358)

TR: ## Features
TR: Connects your Dyson fans, fan heaters, air purifiers, and air humidifiers to ioBroker.

TR: * Reads values from devices and sensors
TR: * Can control devices by giving you the ability to change some values (main power, oscillation, heating, fan speed, ...)
TR: * Reads device list from Dyson servers

TR: ## Installation
TR: ### sentry.io
TR: This adapter uses sentry.io to collect details on crashes and report it automated to the author. The [TR: ioBroker.sentry](https://github.com/ioBroker/plugin-sentry) plugin is used for it. Please refer to the [TR: plugin homepage](https://github.com/ioBroker/plugin-sentry) for detailed information on what the plugin does, which information is collected and how to disable it, if you don't like to support the author with you're information on crashes.

TR: ### Prerequisites
TR: * This adapter needs Node.js >= version 10
TR: * At least js-Controller 3.0.0 is required
TR: * At least Admin 4.0.9 is required
TR: * To get this adapter running you'll need a Dyson account.
TR: * Make sure to add your fan to your account. Either via App or online.

TR: ### Adapter installation
TR: #### Using npm
TR: Run ```npm install iobroker.dysonairpurifier``` on your ioBroker installation to grab the latest version of this adapter from the npm repository.

TR: #### Alternative: Using GitHub URL
TR: Install through the ioBroker Admin UI by pointing it to the latest stable release on GitHub: <https://github.com/Grizzelbee/ioBroker.dysonairpurifier/tarball/master/>

TR: You can also install older release versions using this methods (by pointing to a version tag, e.g., ```v0.6.0``` instead of ```master```in the URL), but the most recent one is generally preferred.

TR: ### Config-data needed
TR: * Dyson account username
TR: * Dyson account password (this adapter can handle passwords up to 32 characters)
TR: * your fans/air purifiers IP address in your LAN.

TR: *Please note*: Due to early development state and a non conform mDNS implementation by Dyson you'll need to provide the local IP of the device *after the first run*.

TR: *Additional Note*: Since Version 0.7.1 the adapter tries to connect to the device by it's hostname (serialnumber) when no host address/IP ist given. This will work under two prerequisites:

TR: 1. There is a DNS Server running in your LAN. Either in your router (e.g. FritzBoxes have a DNS running) or a dedicated one.
TR: 2. You haven't changed the default devicename.

TR: > On the first start of this adapter the Dyson API is queried for all your devices and all supported devices will be created in the devicetree -- with their basic information provided by the API and an additional field "Hostaddress".
> > So please run the adapter once, and your Dyson devices will be created in the device tree with their basic settings.
> > Then stop the adapter, enter the IP(s) into the Hostaddress field(s) and restart the adapter. After that your Dyson devices in the device tree should be populated with data.

TR: ### 2 factor Authentication (since V0.9.0)
TR: After installation of the adapter it should be started automatically - if not please start it first.
After an update it will also restart automatically. In both cases it will remain in "yellow" state and probably show some errors in the log - that's fine for now.

TR: * Open the config dialog of the adapter
TR: * At least fill in your eMail address, the password and the country code - the rest is optional
TR: * Click the 2FA-Code Email button to initiate the process
TR: * You'll receive a "challengeId" automatically in the according field, an eMail and a dialog with further instructions
TR: * enter the 6-digit code from the eMail into the field "dyson one time password"
TR: * Click the "Finish" button
TR: * after that you should have received a token from dyson (invisible for security purposes)
TR: * Click save & close after you have completed your setup - the adapter should start anew and turn green.

TR: All the values will be saved and shown furthermore.
> Usually you don't need to do this 2 FA on a scheduled basis - but you may repeat it when needed.

TR: ## Controlling your device(s)
TR: This adapter is currently able to control the following states of your devices:

TR: * FanSpeed                  , Current fan speed
TR: * Nightmode                 , Night mode state
TR: * Oscillation               , Oscillation of fan.
TR: * ContinuousMonitoring      , Continuous Monitoring of environmental sensors even if device is off.
TR: * MainPower                 , Main Power of fan.
TR: * AutomaticMode             , Fan is in automatic mode.
TR: * Flowdirection             , Direction the fan blows to. ON=Front; OFF=Back (aka Jet focus)
TR: * Jetfocus                  , Direction the fan blows to. ON=Front; OFF=Back (aka Jet focus)
TR: * HeatingMode               , Heating Mode [ON/OFF]
TR: * HeatingTargetTemp         , Target temperature for heating
TR: * AirQualityTarget          , Target air quality for auto mode.
TR: * HumidificationMode        , On / Off
TR: * HumidifyAutoMode          , Auto / Off
TR: * AutoHumidificationTarget  , Auto HumidificationTarget
TR: * HumidificationTarget      , Manual HumidificationTarget
TR: * WaterHardness             , Soft, Medium, Hard

TR: Possible values for these states are documented below, as far as known.
Fan speed only allows values from 1 to 10 and Auto. If you like to set your fan speed down to 0 you'll need to power off the main power.
Which is what the dyson app does also.

TR: ### Known issues
TR: * No automatic IP detection of devices

TR: ## Explanation of Dyson API data (message payload)
TR: Information copied and extended from <https://github.com/shadowwa/Dyson-MQTT2RRD/blob/master/README.md>

TR: ### CURRENT-STATE
| TR: | name | meaning | possible values | Unit |
| ------------- | ----- | ----- | ----- |
| TR: | mode-reason | Current Mode has been set by RemoteControl, App, Scheduler | PRC, LAPP, LSCH, PUI | |
| TR: | state-reason | | MODE | |
| TR: | rssi | WIFI Strength| -100 - 0| dBm|
| TR: | channel| WIFI Channel| 52 | |
| TR: | fqhp | | 96704 | |
| TR: | fghp | | 70480 | |

TR: #### product-state
| TR: | name | meaning | possible values | Unit |
| ------------- | ----- | ----- | ----- |
| TR: | ercd | Last Error Code | NONE , or some hexa values |  |
| TR: | filf | remaining Filter life | 0000 - 4300 | hours|
| TR: | fmod | Mode | FAN , AUTO | |
| TR: | fpwr | Main Power | ON, OFF | |
| TR: | fnst | Fan Status | ON , OFF, FAN | |
| TR: | fnsp | Fan speed | 0001 - 0010, AUTO | |
| TR: | fdir | Fandirection aka. Jet focus/ ON=Front, OFF=Back | ON, OFF | |
| TR: | ffoc | JetFocus | ON, OFF |
| TR: | nmod | Night mode | ON , OFF | |
| TR: | oson | Oscillation | ON , OFF| |
| TR: | osal | OscillationAngle Lower Boundary | 0005 - 355| °  (degrees)|
| TR: | osau | OscillationAngle Upper Boundary | 0005 - 355 | °  (degrees)|
| TR: | oscs | OscillationActive | ON, OFF, IDLE | |
| TR: | ancp | OscillationAngle  | CUST, 0180 |° (degrees)|
| TR: | qtar | Air Quality target | 0001=Good, 0002=Normal, 0003=Bad, 0004=Very bad | |
| TR: | rhtm | Continious Monitoring | ON, OFF | |
| TR: | auto | AutomaticMode | ON, OFF | |
| TR: | nmdv | NightMode Max Fanspeed? | 0004 | |
| TR: | cflr | Status Carbonfilter  | 0000 - 0100 | Percent |
| TR: | cflt | Carbonfilter | CARF | |
| TR: | hflr | Status HEPA-Filter | 0000 - 0100 | Percent |
| TR: | hflt | HEPA-Filter | GHEP | |
| TR: | sltm | Sleeptimer | ON, OFF ||
| TR: | hmod | Heater Mode [ON/OFF] | HEAT | |
| TR: | hmax | Target temperature for heating | 0 .. 5000 | K |
| TR: | hume | HumidificationMode     | ON, OFF, |
| TR: | haut | Humidify Auto Mode| |
| TR: | humt | Humidification Target| |
| TR: | cdrr | CleanDurationRemaining| |
| TR: | rect | AutoHumidificationTarget| |
| TR: | cltr | TimeRemainingToNextClean| |
| TR: | wath | WaterHardness| |
| TR: | wacd | WarningCode? | NONE... |
| TR: | rstf | reset filter lifecycle |
| TR: | bril |  | 0002 |
| TR: | corf |  | ON, OFF |
| TR: | psta | [HP0x] Unknown |  |
| TR: | hsta | [HP0x] Unknown |  |
| TR: | tilt | [HP0x] Unknown |  |
| TR: | dial | [DP0x] Unknown |  |
| TR: | fqhp | fqhp||
| TR: | msta | msta||

| TR: |Error-Codes| Meaning |
| ----- | ----- |
| TR: | NONE | There is no error active |
| TR: |57C2| unknown |
| TR: |11E1| Oscillation has been disabled. Please press Button "Oscillation" on your remote to continue.|

TR: #### scheduler
| TR: | name | meaning | possible values | Unit |
| ------------- | ----- | ----- | ----- |
| TR: | dstv | daylightSavingTime | 0001... | |
| TR: | srsc | ? | 7c68... | |
| TR: | tzid | timezone? | 0001... | |

TR: ### ENVIRONMENTAL-CURRENT-SENSOR-DATA
TR: #### data
| TR: | name | meaning | possible values | Unit |
| ------------- | ----- | ----- | ----- |
| TR: | hact | Humidity (%) | 0000 - 0100 | Percent |
| TR: | pact | Dust | 0000 - 0009 | |
| TR: | sltm | Sleeptimer | OFF... 9999 | Minutes |
| TR: | tact | Temperature in Kelvin | 0000 - 5000 | K|
| TR: | vact | volatil organic compounds | 0001 - 0009 | |
| TR: |pm25|  PM2.5 |0018||
| TR: |pm10|  PM10 |0011||
| TR: |va10|  volatil organic compounds|0004||
| TR: |noxl|  NO2 |0000 - 0014||
| TR: |p25r|  |0019||
| TR: |p10r|  |0018||

TR: ### ENVIRONMENTAL-AND-USAGE-DATA
TR: Redundant values?

TR: #### data
| TR: | name | meaning | possible values | Unit |
| ------------- | ----- | ----- | ----- |
| TR: | pal0 - pal9 | number of second spend in this level of dust since the begining of hour | 0000 - 3600 | |
| TR: | palm | seems to be a median value of palX |  | |
| TR: | vol0 - vol9 | number of second spend in this level of voc since the begining of hour | 0000 - 3600 | |
| TR: | volm | seems to be a median value of volX |  | |
| TR: | aql0 - aql9 | number of second spend in this level of air quality | max (pal, vol)) since the begining of hour | 0000 - 3600 | |
| TR: | aqlm | seems to be a median value of aqlX |  | |
| TR: | fafs | seems to be a number of seconds spend in a specific time | 0000 - 3600 | |
| TR: | faos | seems to be a number of seconds spend in a specific time | 0000 - 3600 | |
| TR: | fofs | seems to be a number of seconds spend in a specific time | 0000 - 3600 | |
| TR: | fons | seems to be a number of seconds spend in a specific time | 0000 - 3600 | |
| TR: | humm | humidity ? (%) | 0000 - 0100 | |
| TR: | tmpm | temperature in kelvin ? | 0000 - 5000 | |

TR: ## Legal Notices
TR: Dyson, pure cool, pure hot & cool, and others are trademarks or registered trademarks of [TR: Dyson Ltd.](https://www.dyson.com) All other trademarks are the property of their respective owners.

## Changelog

### V0.9.0 (2021-04-26) (Still breathing)
* (grizzelbee) New: Added ioBroker sentry plugin to report errors automatically 
* (grizzelbee) New: Added support for Dyson Pure Cool TP07 (438E)
* (grizzelbee) New: Added support for Dyson 2-factor login method
* (grizzelbee) New: Added "keep Sensorvalues" to config to prevent destroying old values when continuous monitoring is off and fan is switched off (TP02)  
* (grizzelbee) Fix: FilterLife should now be correctly in hours and percent in two separate data fields for fans supporting this (e.g. TP02)

### V0.8.2 (2021-04-09) (Still breathing)
* (grizzelbee) Fix: [#80](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/80) fixed npm install hint in documentation
* (grizzelbee) Fix: [#82](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/82) fixed common.dataSource type with type >poll<
* (grizzelbee) Fix: [#95](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/95) Added support for dyson Hot+Cool Formaldehyde (527E)
* (grizzelbee) Fix: [#94](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/94) Fixed dustIndex


### V0.8.1 (2021-02-19) (Fall into the flames)
* (grizzelbee) New: added icons to each fan type in device tree
* (grizzelbee) New: Showing Filter type correctly - not as code anymore
* (grizzelbee) Upd: updated dependencies

### V0.8.0 (2021-02-18) (Beyond the mirror)
* (grizzelbee) New: Log as info if account is active on login; else log as warning. 
* (grizzelbee) New: [#21](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/21) Improvement for humidifier support
* (grizzelbee) Fix: [#67](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/67) Adapter sometimes wrote objects instead of values.

### V0.7.5 (2021-02-12) (I won't surrender)
* (grizzelbee) Fix: [#65](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/65) Adapter get online again after changes to dyson cloud API login procedure.
* (grizzelbee) New: Adapter reconnects with new host address when it gets changed manually

### V0.7.4 (2021-02-10) (Human)
* (grizzelbee) Fix: fixed adapter traffic light for info.connection
* (grizzelbee) Fix: Minor fixes

### V0.7.3 (2021-02-10) (When angels fall)
* (theimo1221) Fix: [#59](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/59) added default country
* (theimo1221) New: added function to mask password to dyson-utils.js
* (grizzelbee) New: extended config test and error logging
* (grizzelbee) New: added password to protectedNative in io-package.json
* (grizzelbee) Fix: fixed showing password in config (leftover from testing/fixing)
* (grizzelbee) Fix: fixed detection of needed js-controller features
* (grizzelbee) Fix: fixed detection if IP is given or not
* (grizzelbee) Upd: creating all data points with await 


### V0.7.2 (2021-02-10) (Songs of love and death)
* (grizzelbee) Fix: [#59](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/59) Fixed bug while loading/saving config which led to wrong values displayed for country and temperature unit
* (grizzelbee) Upd: switched "Skipping unknown ..." message from info to debug 

### V0.7.1 (2021-02-06) (Horizons)
* (grizzelbee) New: When no host address is given - adapter tries to connect via default hostname of the device
* (grizzelbee) Fix: [#13](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/13) Filterlifetime is now correctly displayed in hours and percent for devices supporting this
* (grizzelbee) Fix: [#48](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/48) Fixed countrycodes for UK and USA
* (grizzelbee) Fix: [#52](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/52) Fixed VOCIndex
* (grizzelbee) Fix: Removed option to control Fan state since it corresponds to the state of the fan in auto-mode. Controlling it is senseless.
* (grizzelbee) Fix: Fixed await...then antipattern.
* (grizzelbee) Fix: Fixed undefined roles
* (grizzelbee) Fix: Fixed some bad promises and moved code to dysonUtils
* (grizzelbee) Fix: Fixed encrypting password using js-controller 3.0 build-in routine
* (grizzelbee) Upd: Added topic "Controlling your device(s)" to readme
* (grizzelbee) Upd: Removed unnecessary saving of MQTT password
* (grizzelbee) Upd: [#9](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/9) Added some more dyson codes for heaters and humidifiers


### V0.7.0 (2021-01-08) (Afraid of the dark)
* (jpwenzel)   New: Removing crypto from package dependency list (using Node.js provided version)
* (jpwenzel)   New: Introducing unit tests
* (jpwenzel)   New: At least NodeJs 10.0.0 is required
* (grizzelbee) New: [#23](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/23) - Introduced new data field AirQuality which represents the worst value of all present indexes.
* (grizzelbee) New: BREAKING CHANGE! - switched over to the adapter-prototype build-in password encryption. Therefore you'll need to enter your password again in config.
* (grizzelbee) New: At least js-controller 3.0.0 is required
* (grizzelbee) New: At least admin 4.0.9 is required
* (jpwenzel)   Fix: General overhaul of readme
* (jpwenzel)   Fix: Code refactoring
* (grizzelbee) Fix: fixed some datafield names - please delete the whole device folder and get them newly created.
* (grizzelbee) Fix: [#18](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/18) - Fixed creating the indexes when there is no according sensor
* (grizzelbee) Fix: [#13](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/13) - Displaying Filter life value in hours again
* (grizzelbee) Fix: [#13](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/13) - Creating additional Filter life value in percent
* (grizzelbee) Fix: removed materializeTab from ioPackage
* (grizzelbee) Fix: calling setState now as callback in createOrExtendObject
* (grizzelbee) Fix: Removed non compliant values for ROLE
* (grizzelbee) Fix: calling setState in callback of set/createObject now
* (grizzelbee) Fix: ensuring to clear all timeouts in onUnload-function

### V0.6.0 (2020-10-29) (Rage before the storm)
* (grizzelbee) New: [#17](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/17) - Added online-indicator for each device
* (grizzelbee) New: [#19](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/19) - Extended Password length from 15 characters to 32
* (grizzelbee) New: [#20](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/20) - Improved errorhandling on http communication with Dyson API
* (grizzelbee) Fix: Fixed typo within data field anchorpoint - please delete the old ancorpoint manually.
* (grizzelbee) Fix: [#13](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/13) - Filter life value is now displayed in percent not in hours

### V0.5.1 (2020-10-27) (Heart of the hurricance)
* (grizzelbee) Fix: Added missing clearTimeout

### V0.5.0 (2020-10-27) (Heart of the hurricance)
* (grizzelbee) New: Editable data fields have now appropiate value lists
* (grizzelbee) New: Added more country codes
* (grizzelbee) New: Target temperature of heater can now be set - **in the configured unit!**
* (grizzelbee) Fix: [#13](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/13) - Filter life value is now displayed in percent not in hours
* (grizzelbee) Fix: [#6](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/6) - Changing the fanspeed does now fully work.  

### V0.4.1 (2020-10-16) (unbroken)
* (grizzelbee) New: [#8](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/8) - Documented ProductTypes for better overview and user experience in ReadMe
* (grizzelbee) New: [#9](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/9) - Added some Hot&Cool specific datafields
* (grizzelbee) New: Logging of from devices, when shutting down the adapter
* (grizzelbee) New: [#10](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/10) - Pollig device data every X (configurable) seconds for new data, hence sensors don't send updates on changing values
* (grizzelbee) New: [#11](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/11) - Added Austria and France to Country-List
* (grizzelbee) Fix: Fixed bug in error handling when login to Dyson API fails
* (grizzelbee) Fix: [#12](https://github.com/Grizzelbee/ioBroker.dysonairpurifier/issues/12) - Fixed Dyson API login by completely securing via HTTPS.
* (grizzelbee) Fix: Updated some descriptions in config
  
### V0.4.0 (2020-09-29)
* (grizzelbee) New: devices are now **controllable**
* (grizzelbee) New: state-change-messages are processed correctly now
* (grizzelbee) Fix: Added missing °-Sign to temperature unit
* (grizzelbee) Fix: Terminating adapter when starting with missing Dyson credentials
* (grizzelbee) Fix: NO2 and VOC Indices should work now
* (grizzelbee) Fix: Fixed build errors

### V0.3.0 (2020-09-27) - first version worth giving it a try
* (grizzelbee) New: Messages received via Web-API and MQTT getting processed
* (grizzelbee) New: datapoints getting created and populated
* (grizzelbee) New: Added config item for desired temperature unit (Kelvin, Fahrenheit, Celsius)
* (grizzelbee) New: Added missing product names to product numbers
* (grizzelbee) New: Hostaddress/IP is editable / configurable
* (grizzelbee) New: calculate quality indexes for PM2.5, PM10, VOC and NO2 according to Dyson App

### V0.2.0 (2020-09-22) - not working! Do not install/use
* (grizzelbee) New: Login to Dyson API works
* (grizzelbee) New: Login to Dyson AirPurifier (2018 Dyson Pure Cool Tower [TP04]) works
* (grizzelbee) New: mqtt-Login to [TP04] works
* (grizzelbee) New: mqtt-request from [TP04] works
* (grizzelbee) New: mqtt-request to [TP04] is responding

### V0.1.0 (2020-09-04) - not working! Do not install/use
* (grizzelbee) first development body (non functional)

## License

MIT License

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

Copyright (c) 2020 Hanjo Hingsen <hanjo@hingsen.de>