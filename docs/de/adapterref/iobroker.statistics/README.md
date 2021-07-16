---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.statistics/README.md
title: TR: ioBroker.statistics
hash: 50F3oa1dUN0ZXS5QMiPgTULKjXr2Y6gjxR/q4zvXj1k=
---
![TR: Logo](../../../en/adapterref/iobroker.statistics/admin/statistics.png)

![TR: Number of Installations](http://iobroker.live/badges/statistics-stable.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.statistics.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.statistics.svg)

TR: # ioBroker.statistics
TR: ![TR: Test and Release](https://github.com/iobroker-community-adapters/ioBroker.statistics/workflows/Test%20and%20Release/badge.svg) [![TR: Translation status](https://weblate.iobroker.net/widgets/adapters/-/statistics/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

TR: **This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [TR: Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

TR: ## Description
TR: This adapter will make the configuration of statistics easier.

TR: `The adapter only reacts on state changes (state.ack=true), not on commands!`

TR: choose from the following settings:

TR: * count impulses or on/off changes (Only for binary values and positive edge)
TR: * calculate costs from the counted values (Only for binary values)
TR: * how long was status true/ON and how long false/OFF (Only for binary values)
TR: * delta between logged analogue values (Only for analog values)
TR: * daily max, min and average (Not for delta calculations)
TR: * min/max over the year
TR: * counts within 5 min and daily max, min and average of it (Not for delta calculations)
TR: * sum up of grouped values

TR: The adapter subscribes to the configured objects and creates his own states in the statistics tree.

TR: 2 separate trees are created:

TR: * `statistics.0.save` -> final values of the time frame
TR: * `statistics.0.temp` -> temporary values up to the moment of transfer to save, then temp starts again

TR: The structure of the state is: `statistics.0.{save|temp}.{kind of stat}.{original observed state}.{state of statistical value}`

TR: A german HowTo doc is available here: [TR: howto_de](./doc/howto_de.md)

TR: ## Settings
TR: * specify the relevant groups in the instance configuration page (admin => instances => statistics config)
TR: * specify the configuration in the settings of the state (admin => objects)

TR: <!-- Placeholder for the next version (at the beginning of the line):

TR: ### __WORK IN PROGRESS__ -->

## Changelog
### __WORK IN PROGRESS__
* (Apollon77) prepare for js-controller 3.3
* (Apollon77) make sure all tasks are processed to prevent missing objects
* (bluefox) added the support of Admin5 

### 1.0.4
* (foxthefox) changed the state change to BOTH positive and negative edges, hence it causes a lot of log entries

### 1.0.3 (2021-02-08)
* (Apollon77) fix from sentry crash reports

### 1.0.2 (2021-01-06)
* (foxthefox) try catch around the cronjobs

### 1.0.1 (2020-12-22)
* (Black-Thunder) Precision in rounding set to 4

### 1.0.0 (2020-05-01)
* (bluefox) Caught error if structure is invalid
* (bluefox) Added sentry
* adapter.getObjectView -> controller > 2.0

### 0.2.3 (2020-01-02)
* (HIRSCH-DE) bugfix main.js
* (foxthefox) delete messagehandler

### 0.2.2 (2019-06-29)
* (foxthefox) adapter logs a warning when invalid values arrive and cancels further processing

### 0.2.1 (2019-06-15)
* (foxthefox) correction, timecount value was milliseconds instead seconds
* (foxthefox) other calculations with 2 decimal places after comma
* (foxthefox) min/max for day/week/month/quarter/year
* (foxthefox) set of daily min/max starting point from actual value
* (foxthefox) fixing the PR with dayMin 0 at 00:00
* (foxthefox) improvement for timecount when receiving status updates and no real status change

### 0.2.0 (2019-01-08)
* (foxthefox) compact mode

### 0.1.4 (2019-01-07)
* (foxthefox) license added in io-package.json
* (foxthefox) ReadMe updated
* (foxthefox) type = misc-data

### 0.1.3 (2019-01-06)
* first npm release
* (foxthefox) german doc added
* (foxthefox) error corrections
* (foxthefox) travis testing corrections

### 0.1.2 (2018-09-08)
* (bluefox) total refactoring

### 0.0.3
* admin3 implemented
* complete rewrite to have configuration through the settings of the individual states instead in admin page

### 0.0.2
* setup running

### 0.0.1
* initial release

## License

The MIT License (MIT)

Copyright (c) 2018-2021 foxthefox <foxthefox@wysiwis.net>,

Copyright (c) 2018-2021 bluefox <dogafox@gmail.com>