---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.rpi2/README.md
title: TR: no title
hash: R9fOiJyoT2DZytnnC+cE6C+nwMWndONVOBFvcpla20A=
---
![TR: Number of Installations](http://iobroker.live/badges/rpi2-stable.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.rpi2.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.rpi2.svg)

TR: ![TR: Logo](../../../en/adapterref/iobroker.rpi2/admin/rpi.png) ioBroker RPI-Monitor Adapter

==============

[![TR: Translation status](https://weblate.iobroker.net/widgets/adapters/-/rpi2/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

TR: RPI-Monitor implementation for integration into ioBroker. It is the same implementation as for iobroker.rpi, but with GPIOs.

TR: ## Important Information
TR: Works only with node >= 0.12

TR: **ioBroker needs special permissions to control GPIOs.** On most Linux distributions this can be achieved by adding the ioBroker user to the `gpio` group (recommended) or running ioBroker under `root` (less secure).

TR: ## Installation
TR: After installation you have to configure all required modules via administration page.

TR: After start of iobroker.rpi, all selected modules generates an object tree in ioBroker within rpi.<instance>.<modulename> e.g. rpi.0.cpu

TR: Be sure, that python and build-essential are installed:

```
sudo apt-get update
sudo apt-get install -y build-essential python
```

TR: Following Objects are available after selection:

TR: #### **CPU**
TR: - cpu_frequency
TR: - load1
TR: - load5
TR: - load15

TR: #### **Raspberry (vcgencmd is required)**
TR: - cpu_voltage
TR: - mem_arm
TR: - mem_gpu

TR: #### **Memory**
TR: - memory_available
TR: - memory_free
TR: - memory_total

TR: #### **Network (eth0)**
TR: - net_received
TR: - net_send

TR: #### **SDCard**
TR: - sdcard_boot_total
TR: - sdcard_boot_used
TR: - sdcard_root_total
TR: - sdcard_root_used

TR: #### **Swap**
TR: - swap_total
TR: - swap_used

TR: #### **Temperature**
TR: - soc_temp

TR: #### **Uptime**
TR: - uptime

TR: #### **WLAN**
TR: - wifi_received
TR: - wifi_send

TR: ## Configuration
TR: On configuration page you can select following modules:

TR: - CPU
TR: - Raspberry
TR: - Memory
TR: - Network
TR: - SDCard
TR: - Swap
TR: - Temperature
TR: - Uptime
TR: - WLAN

TR: ## Logfiles / Configuration Settings
TR: ## Features
TR: ## Todo
TR: ## Tested Hardware
TR:  - Odroid C1
TR:  - Raspberry Pi 1

TR: ## GPIOs
TR: You can read and control GPIOs too.
All what you need to do is to configure in the settings the GPIOs options (additional tab).

![TR: GPIOs](../../../en/adapterref/iobroker.rpi2/img/pi3_gpio.png)

TR: After some ports are enabled following states appear in the object tree:

TR: - rpi.0.gpio.PORT.state

TR: The numeration of ports is BCM (BroadComm pins on chip). You can get the enumeration with ```gpio readall```.
For instance PI2:

```
+-----+-----+---------+------+---+---Pi 2---+---+------+---------+-----+-----+
| BCM | wPi |   Name  | Mode | V | Physical | V | Mode | Name    | wPi | BCM |
+-----+-----+---------+------+---+----++----+---+------+---------+-----+-----+
|     |     |    3.3v |      |   |  1 || 2  |   |      | 5v      |     |     |
|   2 |   8 |   SDA.1 | ALT0 | 1 |  3 || 4  |   |      | 5V      |     |     |
|   3 |   9 |   SCL.1 | ALT0 | 1 |  5 || 6  |   |      | 0v      |     |     |
|   4 |   7 | GPIO. 7 |   IN | 1 |  7 || 8  | 0 | IN   | TxD     | 15  | 14  |
|     |     |      0v |      |   |  9 || 10 | 1 | IN   | RxD     | 16  | 15  |
|  17 |   0 | GPIO. 0 |   IN | 0 | 11 || 12 | 0 | IN   | GPIO. 1 | 1   | 18  |
|  27 |   2 | GPIO. 2 |   IN | 0 | 13 || 14 |   |      | 0v      |     |     |
|  22 |   3 | GPIO. 3 |   IN | 0 | 15 || 16 | 0 | IN   | GPIO. 4 | 4   | 23  |
|     |     |    3.3v |      |   | 17 || 18 | 0 | IN   | GPIO. 5 | 5   | 24  |
|  10 |  12 |    MOSI |   IN | 0 | 19 || 20 |   |      | 0v      |     |     |
|   9 |  13 |    MISO |   IN | 0 | 21 || 22 | 1 | IN   | GPIO. 6 | 6   | 25  |
|  11 |  14 |    SCLK |   IN | 0 | 23 || 24 | 1 | IN   | CE0     | 10  | 8   |
|     |     |      0v |      |   | 25 || 26 | 1 | IN   | CE1     | 11  | 7   |
|   0 |  30 |   SDA.0 |   IN | 1 | 27 || 28 | 1 | IN   | SCL.0   | 31  | 1   |
|   5 |  21 | GPIO.21 |   IN | 1 | 29 || 30 |   |      | 0v      |     |     |
|   6 |  22 | GPIO.22 |   IN | 1 | 31 || 32 | 0 | IN   | GPIO.26 | 26  | 12  |
|  13 |  23 | GPIO.23 |   IN | 0 | 33 || 34 |   |      | 0v      |     |     |
|  19 |  24 | GPIO.24 |   IN | 0 | 35 || 36 | 0 | IN   | GPIO.27 | 27  | 16  |
|  26 |  25 | GPIO.25 |  OUT | 1 | 37 || 38 | 0 | IN   | GPIO.28 | 28  | 20  |
|     |     |      0v |      |   | 39 || 40 | 0 | IN   | GPIO.29 | 29  | 21  |
+-----+-----+---------+------+---+----++----+---+------+---------+-----+-----+
| BCM | wPi |   Name  | Mode | V | Physical | V | Mode | Name    | wPi | BCM |
+-----+-----+---------+------+---+---Pi 2---+---+------+---------+-----+-----+
```

TR: ## DHTxx/AM23xx Sensors
TR: You can read from DHT11, DHT22 and AM2302 temperature/humidity sensors.

TR: Connect such a sensor to a GPIO pin as described on the [TR: node-dht-sensor](https://www.npmjs.com/package/node-dht-sensor) package page. Multiple sensors can be connected to *multiple* pins (this is *not* a bus system) as discussed.

## Changelog

### 1.3.1 (2021-07-16)
* (Apollon77) Prevent js-controller 3.3 warnings

### 1.3.0 (2021-07-16)
* (asgothian) Fix to get CPU frequencies also on Raspi 4
* (raintor) Add support for DHTxx/AM23xx Sensors
* (raintor) Configure internal Pull UP/Down Resistor
* (raintor) Add port 'label'/'friendly name' to GPIO config

### 1.2.0 (2020-01-17)
- (janfromberlin) GPIO configuration as output with defined initial value
- (foxriver76) No longer use adapter.objects
- (Apollon77) Adjust gpio errors

### 1.1.1
- (Apollon77) Error messages for not existing values are logged only once

### 1.1.0
 - (Apollon77) Nodejs 10 support 

### 1.0.0 (2018-08-20)
 - (bluefox) Admin3 support 

### 0.3.2 (2017-11-29)
 - (Homoran) fixed Mem available readings on Stretch

### 0.3.1 (2017-01-11)
 - (olifre) Fixup swap_used calculation.

### 0.2.2 (2016-12-01)
 - (bluefox) Add GPIO direction indication

### 0.2.2 (2016-11-22)
 - (bluefox) Use BCM enumeration

### 0.2.1 (2016-10-29)
 - (bluefox) fix start of adapter

### 0.2.0 (2016-10-23)
 - (bluefox) just version change

### 0.1.1 (2016-10-13)
 - (bluefox) implement GPIOs control

### 0.0.4 (2016-03-25)
 - (bluefox) Try catch by eval
   (bluefox) do not process if exec fails

### 0.0.3 (2015-12-28)
 - (husky-koglhof) Fixed value calc.
   Set Value to 2 digits

### 0.0.2 (2015-12-26)
 - (husky-koglhof) Workaround for node 0.10.x
 - (bluefox) Some Fixes

### 0.0.1 (2015-12-23)
 - Initial commit. Alpha Version.

## License

Copyright (c) 2015-2021 husky-koglhof <husky.koglhof@icloud.com>

MIT License