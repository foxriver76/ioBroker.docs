---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.knmi-weather/README.md
title: ioBroker.knmi-Wetter
hash: B8pknfSa8cIgxU53BXnwLLPudRQIfKsjCLRD8Hp+1bc=
---
![Logo](../../../en/adapterref/iobroker.knmi-weather/admin/knmi-weather.png)

![NPM-Version](http://img.shields.io/npm/v/iobroker.knmi-weather.svg)
![Downloads](https://img.shields.io/npm/dm/iobroker.knmi-weather.svg)
![Anzahl der Installationen (spätestens)](http://iobroker.live/badges/knmi-weather-installed.svg)
![Anzahl der Installationen (stabil)](http://iobroker.live/badges/knmi-weather-stable.svg)
![Abhängigkeitsstatus](https://img.shields.io/david/DrozmotiX/ioBroker.knmi-weather.svg)
![NPM](https://nodei.co/npm/ioBroker.knmi-weather.png?downloads=true)

# IoBroker.knmi-Wetter
![Testen und freigeben](https://github.com/DrozmotiX/ioBroker.coronavirus-statistics/workflows/Test%20and%20Release/badge.svg)

## KNMI-Wetterdaten und Alarme für ioBroker
KNMI bietet eine API, deren Daten alle 10 Minuten basierend auf allen vom Institut gesammelten Sensordaten aktualisiert werden.
Mit diesem Adapter können Sie diese API lesen (Registrierung erforderlich!) Und alle relevanten Werte in benutzerfreundlichen Zuständen speichern, um sie in Benachrichtigungen (Beispiel: Telegramm / Pushover) oder Visialisierungen weiterzuverarbeiten.

Die API kann bis zu 300 Mal am Tag kostenlos verwendet werden, daher wird der Adapter alle 5 Minuten geplant.

Folgende Daten sind verfügbar:

* Wetteralarme
* Aktuelle Klimabedingungen
* Prognose heute, morgen, übermorgen
* Karten des aktuellen Regenradars von "[Buienradar] (https://www.buienradar.nl)"

Standortdaten beziehen sich auf GPS-Koordinaten, die in der Administratorkonfiguration gespeichert sind.

Weitere Informationen finden Sie unter: http://weerlive.nl/index.php Holen Sie sich Ihren kostenlosen API-Schlüssel hier: http://weerlive.nl/delen.php

## Unterstütze mich
Wenn Ihnen meine Arbeit gefällt, können Sie gerne eine persönliche Spende leisten (dies ist ein persönlicher Spendenlink für DutchmanNL, keine Beziehung zum ioBroker-Projekt!) [![Spenden] (https://raw.githubusercontent.com/DrozmotiX/ioBroker.knmi-weather/master/admin/button.png)](http://paypal.me/DutchmanNL)

## Changelog
<!--
	Placeholder for the next version (at the beginning of the line):
	### __WORK IN PROGRESS__
-->

### 1.0.0 (2020-09-15)
* (DutchmanNL) Final version release
* (DutchmanNL) Bugfixes

### 0.2.1
* (DutchmanNL) Updated dependency's
* (DutchmanNL) Release to stable repository
* (DutchmanNL) Bugfix : Solve incorrect Latitude/Longtitude configuration

### 0.2.0
* (DutchmanNL) improve propper adapter termination instead of guessing by timer
* (DutchmanNL) Release to stable repository

### 0.1.1
* (DutchmanNL) implement states for RainRadar

### 0.1.0
* (DutchmanNL) initial release

## License
MIT License

Copyright (c) 2020 DutchmanNL <rdrozda86@gmail.com>

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