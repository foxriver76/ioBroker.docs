---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.discovery/README.md
title: TR: ioBroker Discover Adapter
hash: RdRGHBIkYaCIaGJ7onXI7yxUdEBVYhhNzPC8GMrMFtQ=
---
![TR: Logo](../../../en/adapterref/iobroker.discovery/admin/discovery.png)

![TR: Number of Installations](http://iobroker.live/badges/discovery-stable.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.discovery.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.discovery.svg)

TR: # ioBroker Discover Adapter
TR: ![TR: Test and Release](https://github.com/ioBroker/iobroker.discovery/workflows/Test%20and%20Release/badge.svg) [![TR: Translation status](https://weblate.iobroker.net/widgets/adapters/-/discovery/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget) **Detect devices with all known methods.**

TR: This is special adapters, that tries to find all possible devices, that can be reachable from host.
Just now it can detect via ping, UPnP (serial planned).

TR: **This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [TR: Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

TR: ## Actually supported
TR: ### Automatically Discovered
TR: - Beckhoff PLC
TR: - Bosch Smart Home
TR: - Bose Soundtouch
TR: - Broadlink
TR: - BSBLan
TR: - Chromecast
TR: - Daikin climate control
TR: - deConz
TR: - Denon /Marantz
TR: - DoorBird
TR: - ebus
TR: - ekey
TR: - energymanager (E.ON/Solarwatt)
TR: - enet (Jung)
TR: - Epson Stylus PX830
TR: - Fakeroku (harmony)
TR: - FHEM
TR: - FireTV
TR: - Fritzdect
TR: - Fronius
TR: - G-Homa plugs
TR: - Harmony
TR: - Heos
TR: - Home Assistant
TR: - Homematic CCU (hm-rpc, hm-rega)
TR: - Homepilot
TR: - HP-lio
TR: - Philips HUE
TR: - Plex
TR: - InfluxDB
TR: - KLF-200
TR: - KNX (disabled actually)
TR: - Kodi
TR: - Landroid
TR: - LGTV
TR: - Lightify
TR: - Loxone
TR: - Lupusec
TR: - MAX! Cube
TR: - McLighting
TR: - MegaD
TR: - Miele
TR: - Miele Cloud Service
TR: - Mi Home Smarthome
TR: - Mikrotik
TR: - MiLight bridge (v6)
TR: - Mpd
TR: - Musiccast
TR: - myDlink
TR: - Mysensors USB/Serial (9600, 38400, 57600, 115200)
TR: - nanoleaf Light Panels / Canvas
TR: - Net Tools
TR: - Nuki2
TR: - Nut
TR: - Onkyo
TR: - OpenHAB
TR: - Ping
TR: - Plex
TR: - Proxmox
TR: - RFLink (Serial 57600baud)
TR: - SamsungTV
TR: - Smappee
TR: - Solarlog
TR: - Sonnen
TR: - Sonos
TR: - Stiebel-Eltron/Tecalor ISG (plus)
TR: - SQL (MySQL, MSSQL, PostgreSQL)
TR: - Squeezebox
TR: - SqueezeboxRPC
TR: - Synology
TR: - TR-064
TR: - Trådfri
TR: - UPnP
TR: - ValloxMV
TR: - Wifilight
TR: - Yamaha
TR: - Yeelight
TR: - Z-wave USB (Tested with Aeon Labs)

TR: ### Offered as additional adapters
TR: - Cloud
TR: - History (if no SQL or InfluxDB found)
TR: - IoT
TR: - flot (offered when a History-Adapter is present)
TR: - JavaScript
TR: - Info
TR: - Vis
TR: - Web

TR: ## If the adapter can not find IPs ...
TR: The adapter pings the network of the IP of the current host (x.y.z.1..255). Additionally UPnP and mDNS is used to detect IPs.

TR: If not all IPs are found then please check that the iobroker user can execute /bin/ping. Pot execute `sudo setcap cap_net_raw+p /bin/ping` to add missing capabilities/permissions.

TR: ## Todo
TR: - artnet? (Bluefox)
TR: - B-Control-Em? (Bluefox)
TR: - cul / maxcul (Bluefox)
TR: - Foobar200 (Instalator)
TR: - fritzbox (ruhr70)
TR: - km200 (frankjoke)
TR: - megaesp (ausHaus)
TR: - modbus (Bluefox)
TR: - mqtt/mqtt-client (Bluefox)
TR: - owfs (Bluefox)
TR: - rpi2 (if ioBroker runs on Raspberry)
TR: - rwe-smarthome (PArns)
TR: - s7 (Bluefox)
TR: - smartmeter (Apollon77)
TR: - unifi (jens-maus)
TR: - wolf (smiling-jack)
TR: - xs1 (frankjoke)

TR: <!-- Placeholder for the next version (at the beginning of the line):

TR: ### __WORK IN PROGRESS__ -->

## Changelog

### 2.7.0 (2021-07-01)
* (hacki11) Add discovery for BSBLan and ValloxMV
* (Apollon77) Optimize for js-controller 3.3

### 2.6.3 (2021-05-03)
* (bluefox) Added support of Admin5 

### 2.6.2 (2021-04-13)
* (Apollon77) Fix crash case in mihome discovery (Sentry IOBROKER-DISCOVERY-30)
* (Apollon77) Fix crash case in ping logic (Sentry IOBROKER-DISCOVERY-2Y)
* (Apollon77) Fix crash case in hf-lpb100 logic (Sentry IOBROKER-DISCOVERY-34)

### 2.6.1 (2021-02-28)
* (JeyCee) added iot and net-tools
* (Apollon77) Adjust and optimize UDP and UPnP discoveries
* (Apollon77) Add option to specify the "own IP address" and netmask to also allow discovery for e.g. docker cases where an external network should be scanned
* (Apollon77) Fix ping progress counter when scanning multiple ip ranges
* (JeyCee) removed mobile
* (Apollon77) fix sonos and synology
* (JeyCee) UI adjustments
* (Apollon77) Fix crash cases (Sentry IOBROKER-DISCOVERY-2Q)

### 2.5.0 (2021-01-11)
* (Zefau) Replace nuki2 with nuki-extended
* (Zefau) Suggest jarvis for discovery as advice
* (Apollon77) Add checks on broadlink2 discovery to prevent crash case (Sentry IOBROKER-DISCOVERY-2H)

### 2.4.1 (2020-12-06)
* (Apollon77) Fix potential crash case in lightify (Sentry IOBROKER-DISCOVERY-2D)
* (Apollon77) Fix potential crash case (Sentry IOBROKER-DISCOVERY-2C)

### 2.4.0 (2020-11-29)
* (withstu) add heos

### 2.3.11 (2020-08-08)
* (Grizzelbee) Added MieleCloudService 

### 2.3.10 (2020-07-26)
* (MiSchroe) Discovery Velux KLF-200 updated to new firmware

### 2.3.9 (2020-07-17)
* (Apollon77) Add error handling to onvif discovery (Sentry IOBROKER-DISCOVERY-13)
* (Apollon77) Add error handling to smapee discovery (Sentry IOBROKER-DISCOVERY-14)
* (Apollon77) Add error handling to synology discovery (Sentry IOBROKER-DISCOVERY-1A)
* (Apollon77) Update mndp library to prevent crashes (Sentry IOBROKER-DISCOVERY-15+)

### 2.3.7 (2020-06-11)
* (Apollon77) Add error handling for Synology detection (Sentry IOBROKER-DISCOVERY-E)

### 2.3.6 (2020-05-02)
* (Garfonso) add mydlink adapter
* (haba1234) New adapter added: Onvif
* (Apollon77) serial device discovery fixed

### 2.3.4 (2020-04-30)
* (Apollon77) make sure to check if initialization was done when ending (Sentry IOBROKER-DISCOVERY-8) 
* (APollon77) fix megad discovery error

### 2.3.3 (2020-04-23)
* (Apollon77) correct access to wrong variable (Sentry IOBROKER-DISCOVERY-3)
* (Apollon77) catch http errors better (Sentry IOBROKER-DISCOVERY-2)

### 2.3.2 (2020-04-18)
* (Apollon77) Fix potential crash in knx discovery

### 2.3.1 (2020-04-16)
* (instalator) Add Synology, Onkyo, Mpd, Mikrotik
* (instalator) Fixed eKey, Mihome, Broadlink2, Plex
* (instalator) Several optimizations and fixing of crash causes
* (Apollon77) Add Sentry Crash Reporting for js-controller 3.0
* (bluefox) Refactoring

### 2.2.2 (2020-02-13)
* (dkleber89) Add discovery for Beckhoff PLC
* (forelleblau) Add discovery for Solarlog
* (oweitman) Add discovery for SqueezeboxRPC

### 2.1.0 (2020-01-21)
* (foxriver76) no longer use adapter.objects
* __js-controller > 2.0.0 required__

### 2.0.0 (2019-05-15)
* (thewhobox) Code refactoring
* (thewhobox) add emby detection
* (frankjoke) boradlink => broadlink2
* (bluefox) Small fixes
* (Apollon77) Support for nodejs 12 added, nodejs 4 is no longer supported!

### 1.3.0 (2019-01-04)
* (bluefox) Support of compact mode
* (ldittmar) info Adapter added

### 1.2.4 (2018-09-22)
* (bluefox) Small GUI update was made
* (rg-engineering) Added ebus

### 1.2.3 (2018-09-13)
* (bluefox) Proxmox was fixed
* (unltdnetworx) solarwatt
* (Michael Schroeder) klf200
* (bluefox) Use OpenStreetMap
* (MeisterTR) yeelight
* (unltdnetworx) stiebel-isg
* (BuZZy1337) doorbird

### 1.2.1 (2018-07-28)
* (bluefox) New adapter added: DENON

### 1.1.1 (2018-03-27)
* (bluefox) New adapter added: ekey, Home Assistant, FHEM

### 1.1.0 (2018-01-23)
* (Apollon77) Upgrade Serialport Library

### 1.0.2 (2018-01-13)
* (bluefox) ready for admin3

### 1.0.1 (2017-12-28)
* Fix Epson Stylus PX830
* Add Bose Soundtouch

### 1.0.0 (2017-10-18)
* (pix) Add Epson Stylus PX830
* (pix) Add Homepilot
* (Samuel Weibel) Loxone

### 0.4.5 (2017-08-25)
* (Apollon77) Fixes in mihome

### 0.4.4 (2017-06-01)
* (bluefox) Add lgtv
* (bluefox) disable serial by default. It must be explicit enabled every time
* (bluefox) add mihome

### 0.4.2 (2017-05-17)
* (bluefox) Add discovery methods selection

### 0.4.0 (2017-05-01)
* (soef) add SamsungTV, Lightify, Miele and yamaha
* (soef) add new discovery method mDNS
* (bluefox) add openhab, Broadlink

### 0.3.3 (2017-04-15)
* (bluefox) add philips HUE

### 0.3.2 (2017-04-12)
* (bluefox) Add mysensors USB/Serial

### 0.3.1 (2017-04-01)
* (apollon77) Add Daikin climate control

### 0.3.0 (2017-03-27)
* (bluefox) Fixed serial discovery

### 0.2.3 (2017-03-18)
* (bluefox) fix license dialog
* (bluefox) add zwave
* (bluefox) add sqllite and flot
* (bluefox) ack => ignore
* (bluefox) add megad
* (apollon77) add history
* (apollon77) enhance/fix sql-sqlite
* (apollon77) add InfluxDB
* (ykuendig) german translation updated

### 0.2.2 (2017-03-18)
* (bluefox) Fix typo

### 0.2.1 (2017-03-15)
* (bluefox) initial commit

## License

The MIT License (MIT)

Copyright (c) 2017-2021, Bluefox <dogafox@gmail.com>

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