---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.tino/README.md
title: TR: ioBroker.tino
hash: z+wiZ/y+sdVnU+uJ+GMOYAsNHn8nfPUr4zCLYb0CAA4=
---
![TR: Logo](../../../en/adapterref/iobroker.tino/admin/tino.png)

![TR: NPM version](http://img.shields.io/npm/v/iobroker.tino.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.tino.svg)
![TR: Dependency Status](https://img.shields.io/david/bowao/iobroker.tino.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/bowao/ioBroker.tino/badge.svg)
![TR: NPM](https://nodei.co/npm/iobroker.tino.png?downloads=true)
![TR: Travis-CI](https://img.shields.io/travis/com/bowao/ioBroker.tino/master)

TR: # ioBroker.tino
TR: ## TiNo adapter for ioBroker
TR: (German version see below)

TR: Read wireless sensordata received via TiNo Protocol Version 1.01 and TiNo Protocol Version 2.2.
The corresponding protocol version is automatically detected on the basis of the received data.

TR: The wireless transceiver and receiver TiNo were developed by nurazur.

TR: Project-page: https://nurazur.wordpress.com/

TR: Github: https://github.com/nurazur/TiNo

TR: "**TI**ny **NO**de": battery powered wireless sensor or wireless actor. Target of the project is the development of small size , cost effective battery powered wireless sensors. The sensors communicate with gateways, like a raspberry pi. The targets are:

TR: * low cost (BOM under 5 Euro)
TR: * very small size (matchbox)
TR: * ultra low sleep current
TR: * long battery life time: 5 years and more on a CR2032 cell
TR: * long range (what ever this means :-), but its realy long)
TR: * simple to build up
TR: * communication security
TR: * Plug&Play Firmware

TR: Sensors can be almost any, like temperature, relative humidity, air pressure, altitude meter, light intensity, UV Index, movement detectors, Reed switches, etc.

TR: In the adapter configuration, the serial interface and the associated baud rate can be set.
When the learning mode has been activated, the sensors are automatically created with their node-id and all recognized data points after the first message reception.
The learning mode ends automatically after 10 minutes and can be reactivated for another 10 minutes under "info" via datapoint "learningMode".
The associated offset data points are created under "config", so that the sensor values can be corrected if necessary.
The calculated data points humidity absolute and dew point are created under "calculated", but only if the sensor supplies the values temperature and relative humidity.

TR: The following data points would be created for receiver protocol Version 1.01:

TR: * NodeId
TR: * RSSI
TR: * Battery voltage
TR: * Message Counter
TR: * Temperature
TR: * Humidity
TR: * Heartbeat (Only in Protocol Version 1.01)
TR: * Interupt 1, 2 and 3
TR: * Frequency error indicator (Only in Protocol Version 1.01)
TR: * RFM69 Temperature (Only in Protocol Version 1.01)
TR: * Bit errors

TR: In addition, the following data points are created for the receiver protocol version 2.2 (if available).

TR: * Interrupt 4 to 8
TR: * synchronized
TR: * Link quality Indicator
TR: * Frequency offset
TR: * Distance (Only with distance sensor installed)
TR: * Height (Only with height sensor installed)
TR: * Air pressure (Only with air pressure sensor installed)
TR: * Contact (Only with reed contact installed)
TR: * Temperature 1
TR: * Temperature 2

-------------------------------------------------------------------------------------------

TR: ## TiNo adapter für ioBroker
TR: Einlesen der vom TiNo Version 1.01 und TiNo Version 2.2 empfangenen Funksensordaten.
Die entsprechende Protokoll-Version wird automatisch anhand der empfangen Daten erkannt.

TR: Der Funksender und -empfänger TiNo wurden von nurazur entwickelt.

TR: Projekt-Seite: https://nurazur.wordpress.com/

TR: Github: https://github.com/nurazur/TiNo

TR: "**TI**ny **NO**de" : Batteriebetriebener Funksensor oder Funk-Aktor. Ziel dieses Projekts ist die Entwicklung schnurloser Funk Sensoren, die über Batterien versorgt werden und z.B. mit dem Raspberry Pi kommunizieren. Die Entwicklung hat zum Ziel:

TR: * minimale Kosten (Stückkosten unter 5 EUR)
TR: * minimale Grösse (Streichholzschachtel)
TR: * minimaler Stromverbrauch
TR: * maximale Batterielebensdauer (5 Jahre oder mehr)
TR: * maximale Reichweite
TR: * maximal einfach nachzubauen
TR: * Plug&Play Firmware

TR: Als Sensor kann man so ziemlich alles verwenden, ob Temperatur, Luftfeuchtigkeit, Luftdruck, Höhenmesser, Lichtintensität, UV Index, Anwesenheitssensoren, Magnetschalter, Erschütterungs-Sensoren, Feuchtigkeitsmesser usw also im Prinzip alle Arten von Sensoren.

TR: In der Adapter Konfiguration lässt sich die Serielle Schnittstelle und die zugehörige Baudrate einstellen.
Wenn der Anlermodus aktiviert ist, werden die Sensoren nach dem ersten Nachrichten-Empfang automatisch mit ihrer Node-Id und allen erkannten Datenpunkten angelegt.
Der Anlernmodus wird nach 10min. automatisch beendet und kann unter "info" über den Datenpunkt "learningMode" für weitere 10min. erneut aktiviert werden.
Unter "config" werden die zugehörigen offset Datenpunkte erstellt, damit die Sensorwerte bei Bedarf korrigiert werden können.
Unter "calculated" werden die erechneten Datenpunkte Feuchte absolut und Taupunkt angelegt, jedoch nur wenn der Sensor die Werte Temperatur und relative Feuchte liefert.

TR: Folgende Datenpunkte werden für das Empfänger-Protokoll Version 1.01 angelegt:

TR: * NodeId
TR: * Signalstärke (RSSI)
TR: * Batteriespannung
TR: * Nachrichtenzähler
TR: * Temperatur
TR: * Feuchte
TR: * Heartbeat (Nur in Protokoll Version 1.01)
TR: * Interrupts 1 bis 3
TR: * Frequenzfehler Indikator (Nur in Protokoll Version 1.01)
TR: * RFM69 Temperatur (Nur in Protokoll Version 1.01)
TR: * Bitfehler

TR: zusätzlich werden für das Empfänger-Protokoll Version 2.2 folgende Datenpunkte angelegt (wenn vorhanden).

TR: * Interrupt 4 bis 8
TR: * Synchronisation
TR: * Kanalgüte
TR: * Frequenzversatz
TR: * Entfernung (Nur bei installiertem Entfernungssensor)
TR: * Höhe (Nur bei installiertem Höhensensor)
TR: * Luftdruck (Nur bei installiertem Luftdrucksensor)
TR: * Reed-Kontakt (Nur bei installiertem Reed-Kontakt)
TR: * Temperatur 1
TR: * Temperatur 2

## Changelog
### 1.1.0
- Add TiNo Protocol V2.2 support
- (Add Datapoints temperature 1 and Temperatur 2)
- (max value of data point temperature increased to 600)
- Add connectionType and dataSource in io-package.json
- Add testing for Node.js 16

### 1.0.3
- Displays the interrupt value only for short time

### 1.0.2
- (AndrObe) Fix for negative temperature values
- (bowao) Update devDependencies

### 1.0.1
- fix bug in interrupt detection for protocol V2

### 1.0.0
- Update dependencies
- BREAKING CHANGE: Drop node 8 support, requires node 10 or above
- BREAKING CHANGE: js-controller v2.4.0 or above required

### 0.1.3
- Update travis.yml, License, Readme

### 0.1.2
- (bowao) learningMode set to true if not defined

### 0.1.1
- (bowao) New learning mode with 10min. auto-timeout

### 0.1.0
- (bowao) Add tino protocol V2.0 support
- (bowao) Add option to search new data points on already created sensors
- (bowao) Add calculated data points humidity_absolute and dew point

### 0.0.5
- (bowao) Add datapoints interrupt an heartbeat
- (bowao) Set default baudrate to 38400
- (bowao) Close serialport on unload and cleanup

### 0.0.4
- (bowao) Resize logo

### 0.0.3
- (bowao) Update readme

### 0.0.2
- (nurazur) Add logo

### 0.0.1
- (bowao) initial release

## License
MIT License

Copyright (c) 2021 bowao <cryolab@web.de>

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