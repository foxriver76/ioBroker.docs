---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.sonoff/README.md
title: TR: ioBroker Sonoff
hash: VDlcSKuA7whtiJQgKK9PL2zdKYwGkNcFtmHhOcwoe9c=
---
![TR: Logo](../../../en/adapterref/iobroker.sonoff/admin/sonoff.png)

![TR: Number of Installations](http://iobroker.live/badges/sonoff-stable.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.sonoff.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.sonoff.svg)

TR: # ioBroker Sonoff
TR: ![TR: Test and Release](https://github.com/ioBroker/ioBroker.sonoff/workflows/Test%20and%20Release/badge.svg) [![TR: Translation status](https://weblate.iobroker.net/widgets/adapters/-/sonoff/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

TR: **This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [TR: Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

TR: ## Usage
TR: This adapter communicates with Sonoff devices with Tasmota firmware or ESP devices via MQTT.

TR: Following topics are expected:

TR: - `tele/DeviceNAME/STATE`
TR: - `tele/DeviceNAME/SENSOR`
TR: - `tele/DeviceNAME/INFOx`
TR: - `tele/DeviceNAME/ENERGY`
TR: - `cmnd/DeviceNAME/POWERx`
TR: - `stat/DeviceNAME/POWERx`
TR: - `/DeviceNAME/BM280/Temperature`
TR: - `/DeviceNAME/BM280/Humidity`
TR: - `/DeviceNAME/BM280/Temperatur`
TR: - `/DeviceNAME/BM280/Feuchtigkeit`
TR: - `/DeviceNAME/BM280/Vcc`
TR: - `/DeviceNAME/BM280/VCC`
TR: - `/DeviceNAME/BM280/Laufzeit`
TR: - `/DeviceNAME/BM280/RSSI`
TR: - `/DeviceNAME/BM280/POWER`
TR: - `/DeviceNAME/BM280/POWER1`
TR: - `/DeviceNAME/BM280/POWER2`
TR: - `/DeviceNAME/BM280/POWER3`
TR: - `/DeviceNAME/BM280/POWER4`
TR: - `/DeviceNAME/BM280/Switch1`
TR: - `/DeviceNAME/BM280/Switch2`
TR: - `/DeviceNAME/BM280/Total`
TR: - `/DeviceNAME/BM280/Today`
TR: - `/DeviceNAME/BM280/heute`
TR: - `/DeviceNAME/BM280/Yesterday`
TR: - `/DeviceNAME/BM280/gestern`
TR: - `/DeviceNAME/BM280/Faktor`
TR: - `/DeviceNAME/BM280/Factor`
TR: - `/DeviceNAME/BM280/Power`
TR: - `/DeviceNAME/BM280/Leistung`
TR: - `/DeviceNAME/BM280/Voltage`
TR: - `/DeviceNAME/BM280/Spannung`
TR: - `/DeviceNAME/BM280/Current`
TR: - `/DeviceNAME/BM280/Strom`
TR: - `/DeviceNAME/BM280/Punkt`
TR: - `/DeviceNAME/BM280/Counter1`
TR: - `/DeviceNAME/BM280/Counter2`
TR: - `/DeviceNAME/BM280/Counter3`
TR: - `/DeviceNAME/BM280/Counter4`
TR: - `/DeviceNAME/BM280/Pressure`
TR: - `/DeviceNAME/BM280/SeaPressure`
TR: - `/DeviceNAME/BM280/Druck`
TR: - `/DeviceNAME/BM280/Approx. Altitude`
TR: - `/DeviceNAME/BM280/Module`
TR: - `/DeviceNAME/BM280/Version`
TR: - `/DeviceNAME/BM280/Hostname`
TR: - `/DeviceNAME/BM280/IPAddress`
TR: - `/DeviceNAME/BM280/IPaddress`
TR: - `/DeviceNAME/BM280/RestartReason`
TR: - `/DeviceNAME/BM280/CarbonDioxide`
TR: - `/DeviceNAME/DHT11/Illuminance`
TR: - `/DeviceNAME/SonoffSC/Light`
TR: - `/DeviceNAME/SonoffSC/Noise`
TR: - `/DeviceNAME/SonoffSC/AirQuality`
TR: - `/DeviceNAME/SDS0X1/PM2.5`
TR: - `/DeviceNAME/SDS0X1/PM10`
TR: - `/DeviceNAME/SDS0X1/UvLevel`
TR: - `/DeviceNAME/SDS0X1/Latitude`
TR: - `/DeviceNAME/SDS0X1/Longitude`
TR: - `/DeviceNAME/SR04/Distance`

TR: **Note**: The list could be easily extended. Please send `Pull Requests` or *debug data* for unknown states to developer (via issue).

TR: ## Auto-creation of objects
TR: In the web config you can determine which MQTT telegrams create the new objects not in default data points:

TR: * `TELE_SENSOR` - creates objects from `tele/xxx/SENSOR` telegrams
TR: * `TELE_STATE` - creates objects from `tele/xxx/STATE` telegrams
TR: * `STAT_RESULT` - creates objects from `stat/xxx/RESULT` telegrams

TR: Usually TELE_SENSOR should be sufficient for most users.

TR: * `Create object tree` creates objects as tree structure

TR: **Warning!** This option will mess up your sonoff object tree! You have to redo all the settings for storage...
Store the object structure as JSON file, so you can recreate your old structure.
Best is to stop the adapter, delete all objects under sonoff and start the adapter again.

TR: ## Flags for LED controllers
TR: The mode states will be created only if device has one of the states:

TR: - `Red`, `Green`, `Blue`, `WW`, `CW`, `Color`, `RGB_POWER`, `WW_POWER`, `CW_POWER`, `Hue`, `Saturation`

TR: States:

TR: * `modeLedExor` - exor for white LEDs and color LEDs => if the white LEDs are switched on, color LEDs are switched off and vice versa (default true)
TR: * `modeReadColors` - allow for color read from MQTT (default false)

TR: <!-- Placeholder for the next version (at the beginning of the line):

TR: ### __WORK IN PROGRESS__ -->

## Changelog
### 2.4.3 (2021-07-18)
* (bluefox) Better type detection for non-described states

### 2.4.2 (2021-07-17)
* (bluefox) Optimize for js-controller 3.3

### 2.4.1 (2021-07-17)
* (Apollon77/bluefox) Optimize for js-controller 3.3
* (Apollon77) Add Sentry for error reporting with js-controller 3.x+

### 2.4.0 (2021-02-04)
* (anwa) add several data points
* (anwa) Fix translation for 'ignorePings'
* (anwa) Fix wrong unit for humidity
* (anwa) Config option to create a complete object tree instead of a flat structure
* (anwa) Change Action type to string
* (Apollon77) js-controller 2.0 is required at least

### 2.3.3 (2019-11-27)
* (bluefox) Error with empty packet was caught

### 2.3.2 (2019-10-23)
* (bluefox) Fixed the password input in the configuration
* (bluefox) Allowed to set the IP interface for server
* (bluefox) Fixed tests for js-controller 2.0
* (bluefox) Fixed the monitoring of the client connection
* (bluefox) Changed "indicator.connected" to "indicator.reachable" for clients
* (bluefox) Supported `{POWERn: "true"}`
* (bluefox) Correct processing of `{temp: nan}`

### 2.2.3 (2019-01-10)
* (simatec) Support for compact mode

### 2.2.2 (2018-06-22)
* (bluefox) Configuration was fixed

### 2.2.1 (2018-06-20)
* (bluefox) '-' in names was allowed again

### 2.2.0 (2018-05-22)
* (gemu2015) auto generate objects, support for arrays (channel), led-controllers improved

### 2.1.3 (2018-05-08)
* (bluefox) Added HC-SR04 Ultrasonic Sensor

### 2.1.2 (2018-04-23)
* (bluefox) Added support of UvLight, Longitude and Latitude

### 2.1.1 (2018-04-13)
* (bluefox) Support of the particle concentration sensor

### 2.1.0 (2018-03-30)
* (gemu2015) Support of the devices control (many thanks :)
* (gemu2015) Support of many new values
* (modmax) Update alive status of the clients
* (modmax) Added POWER5-8 and Switch3-4

### 2.0.2 (2018-03-19)
* (modmax) Fixing reconnection of clients
* (bluefox) Add SeaPressure

### 2.0.1 (2018-03-17)
* (bluefox) Replace stream handler
* (bluefox) Add timeout for clients
* (bluefox) Add Light/Noise/AirQuality
* (bluefox) Do not send pingresp for invalid clients

### 1.0.3 (2018-03-03)
* (bluefox) Add Analog0/1/2/3 sensor

### 1.0.2 (2018-02-17)
* (Apollon77) Add Illuminance sensor

### 1.0.1 (2018-02-05)
* (bluefox) Ready for admin3
* (bluefox) Added CO2 sensor

### 1.0.0 (2017-11-27)
* (AlZiBa) typo @ alive
* (AlZiBa) add Today's power consumption for Sonoff POW
* (AlZiBa) unit of power consumption is kWh

### 0.3.3 (2017-11-03)
* (bluefox) Add counters

### 0.3.2 (2017-10-22)
* (Tan-DE) Small change for Switch1. Switch2 and additional IPaddress added.

### 0.3.1 (2017-10-12)
* (bluefox) Fix tests and LWT

### 0.3.0 (2017-10-06)
* (bluefox) Add INFO and ESP

### 0.2.0 (2017-10-05)
* (bluefox) Add ENERGY and DS18x20

### 0.1.0 (2017-10-01)
* (bluefox) initial commit

## License

The MIT License (MIT)

Copyright (c) 2017-2021, bluefox <dogafox@gmail.com>

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