---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.eufy-security/README.md
title: TR: ioBroker.eufy-security
hash: cEwbuVh0ESWcs7RKS4gY8WFx0kUKseQ91JtyK5S1GIs=
---
![TR: Logo](../../../en/adapterref/iobroker.eufy-security/admin/eufy-security.png)

![TR: NPM version](https://img.shields.io/npm/v/iobroker.eufy-security.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.eufy-security.svg)
![TR: Number of Installations (latest)](https://iobroker.live/badges/eufy-security-installed.svg)
![TR: Number of Installations (stable)](https://iobroker.live/badges/eufy-security-stable.svg)
![TR: Dependency Status](https://img.shields.io/david/bropat/iobroker.eufy-security.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/bropat/ioBroker.eufy-security/badge.svg)
![TR: Build Status](https://travis-ci.org/bropat/ioBroker.eufy-security.svg?branch=master)
![TR: AppVeyor](https://ci.appveyor.com/api/projects/status/github/bropat/ioBroker.eufy-security?branch=master&svg=true)
![TR: NPM](https://nodei.co/npm/iobroker.eufy-security.png?downloads=true)

TR: # ioBroker.eufy-security
TR: This adapter uses the [TR: eufy-security-client](https://github.com/bropat/eufy-security-client) library to comunicate with Eufy devices.

TR: If you appreciate my work and progress and want to support me, you can do it here:

[![TR: ko-fi](https://www.ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/E1E332Q6Z)

TR: ## Description
TR: This adapter allows to control [TR: Eufy security devices](https://us.eufylife.com/collections/security) by connecting to the Eufy cloud servers and local/remote stations.

TR: You need to provide your Cloud login credentials. The adapter connects to your cloud account and polls for all device data via HTTPS. Now a local or remote P2P connection to the Eufy stations/devices is also supported. However, a connection to the Eufy Cloud is always a prerequisite.

TR: One Adapter instance will show all devices from one Eufy Cloud account and allows to control them.

TR: ## Features
TR: * Supports local and remote p2p connection to station
TR: * Two factor authentication
TR: * Livestream as HLS stream (supports all platforms, but introduce a latency)
TR: * Last HLS live stream is always saved for later viewing
TR: * Downloads event video when push notification is received (async)
TR: * Takes jpeg thumbnail of the livestream or downloaded video
TR: * Base station:
TR:     * States:
TR:         * Configured Guard mode
TR:         * Current Guard mode
TR:         * Name
TR:         * Model
TR:         * Serial number
TR:         * Software version
TR:         * Hardware version
TR:         * MAC address
TR:         * LAN ip address
TR:     * Actions:
TR:         * Change guard mode
TR:         * Reboot station
TR:     * Events:
TR:         * Alarm mode change
TR: * Camera:
TR:     * States:
TR:         * Online / offline etc.
TR:         * Battery %
TR:         * Battery temperature
TR:         * Name
TR:         * Model
TR:         * Serial number
TR:         * Software version
TR:         * Hardware version
TR:         * MAC address
TR:         * Wifi RSSI
TR:         * Filtered false events since last charge
TR:         * Saved/Recorded events since last charge
TR:         * Total events since last charge
TR:         * Used days since last charge
TR:     * Actions:
TR:         * Start livestream (hls; supports also local livestream)
TR:         * Stop livestream (hls)
TR:         * Enable/disable device
TR:         * Enable/disable auto night vision
TR:         * Enable/disable led (only camera 2 products, indoor cameras, floodlight camera, solo cameras and doorbells)
TR:         * Enable/disable anti-theft detection (only camera 2 products)
TR:         * Enable/disable motion detection
TR:         * Enable/disable pet detection (only indoor cameras)
TR:         * Enable/disable sound detection (only indoor cameras)
TR:         * Enable/disable RTSP stream (only camera2 products, indoor cameras and solo cameras)
TR:         * Change video watermark setting
TR:     * Events:
TR:         * Motion detected
TR:         * Person detected
TR:         * Ringing (only Doorbell)
TR:         * Crying detected (only Indoor cameras)
TR:         * Sound detected (only Indoor cameras)
TR:         * Pet detected (only Indoor cameras)
TR: * Sensor
TR:     * Entry sensor:
TR:         * States:
TR:             * Online / offline etc.
TR:             * Low battery
TR:             * Name
TR:             * Model
TR:             * Serial number
TR:             * Software version
TR:             * Hardware version
TR:         * Events:
TR:             * Open / closed
TR:     * Motion sensor:
TR:         * States:
TR:             * Online / offline etc.
TR:             * Low battery
TR:             * Name
TR:             * Model
TR:             * Serial number
TR:             * Software version
TR:             * Hardware version
TR:         * Events:
TR:             * Motion detected
TR: * Keypad:
TR:     * States:
TR:         * Online / offline etc.
TR:         * Low battery
TR:         * Name
TR:         * Model
TR:         * Serial number
TR:         * Software version
TR:         * Hardware version
TR: * Lock:
TR:     * States:
TR:         * Online / offline etc.
TR:         * Battery %
TR:         * Lock status
TR:         * Name
TR:         * Model
TR:         * Serial number
TR:         * Software version
TR:         * Hardware version
TR:         * Wifi RSSI
TR:     * Actions:
TR:         * Lock/unlock
TR: * more to come...

TR: ## Configuration
TR: See [TR: here](./docs/en/README.md)

TR: ## Known working devices
TR: * HomeBase (T8001)
TR: * HomeBase E (T8002)
TR: * HomeBase 2 (T8010)
TR: * Smart Lock Wi-Fi Bridge (T8021)
TR: * eufyCam (T8111)
TR: * eufyCam E (T8112)
TR: * eufyCam 2 (T8114)
TR: * eufyCam 2C (T8113)
TR: * eufyCam 2 Pro (T8140)
TR: * eufyCam 2C Pro (T8141)
TR: * Floodlight (T8420)
TR: * Wired Doorbell 2k (T8200)
TR: * Wired Doorbell 1080p (T8201)
TR: * Battery Doorbell 2K (T8210)
TR: * Battery Doorbell 1080p (T8222)
TR: * Entry Sensor (T8900)
TR: * Motion sensor (T8910)
TR: * Indoor Cam Pan&Tilt 2K (T8410)
TR: * Indoor Cam 2K (T8400)
TR: * Indoor Cam Pan&Tilt 1080p (T8411)
TR: * Indoor Cam 1080p (T8401)
TR: * Smart Lock Front Door (T8500)

TR: If more devices work (or also not) please report them by opening a GitHub issue.

TR: ## How to report issues and feature requests
TR: Please use GitHub issues for this.

TR: Best is to set the adapter to Debug log mode (Instances -> Expert mode -> Column Log level or see [TR: here](https://github.com/bropat/ioBroker.eufy-security/wiki/Howto-enable-debug)). Then please get the logfile from disk (subdirectory "log" in ioBroker installation directory and not from Admin because Admin cuts the lines).

## Changelog

### 0.5.4 (2021-05-26)
* (bropat) Fixed issue with video corruption in p2p livestream
* (bropat) Updated versions of the package dependencies

### 0.5.3 (2021-05-14)
* (bropat) Fixed issue [#121](https://github.com/bropat/ioBroker.eufy-security/issues/121)
* (bropat) Fixed push notification for indoor and floodlight cams (issue [#130](https://github.com/bropat/ioBroker.eufy-security/issues/130))
* (bropat) Fixed refresh of properties/settings of standalone devices (issue [#130](https://github.com/bropat/ioBroker.eufy-security/issues/130))
* (bropat) Updated versions of the package dependencies

### 0.5.2 (2021-04-02)
* (bropat) Try to add support for FreeBSD - issue [#106](https://github.com/bropat/ioBroker.eufy-security/issues/106)
* (bropat) Updated package dependency ffmpeg-static for FreeBSD support

### 0.5.1 (2021-04-01)
* (bropat) Fixed issue [#105](https://github.com/bropat/ioBroker.eufy-security/issues/105)

### 0.5.0 (2021-03-30)
* (bropat) Added support for smart lock products
* (bropat) Added new P2P feature: lock/unlock smart lock products
* (bropat) Optimized speed of P2P connection establishment
* (bropat) New setting: P2P connection setup preference: local prefered, local only or quickest connection
* (bropat) Dropped support for NodeJS 10.x (min. requirement 12)
* (bropat) Updated versions of the package dependencies

### 0.4.3 (2021-03-19)
* (bropat) Code enhancements for publishing the adapter to the central repository
* (bropat) Updated versions of the package dependencies

### 0.4.2 (2021-03-14)
* (bropat) Fixed roles of states according to ioBroker documentation

### 0.4.1 (2021-03-14)
* (bropat) Removed legacy password encryption support for admin adapter (requires admin adapter >= 4.0.9)
* (bropat) Added admin adapter as global dependency
* (bropat) Updated license

### 0.4.0 (2021-03-11)
* (bropat) Added handling of adapter updates with breaking changes
* (bropat) Added new P2P feature: enable/disable pet detection for indoor cameras
* (bropat) Added new P2P feature: enable/disable sound detection for indoor cameras
* (bropat) Added new P2P feature: enable/disable led for wired doorbell
* (bropat) Unlocked state: last_event_video_url
* (bropat) Fixed parsing of push notification to download video events for battery doorbells and indoor cameras
* (bropat) Fixed enable/disable device (for wired doorbells, indoor cameras, floodlight camera and solo cameras)
* (bropat) Fixed enable/disable led (for battery doorbells, indoor cameras, floodlight camera and solo cameras)
* (bropat) Fixed enable/disable motion detection (for indoor cameras, floodlight camera and solo cameras)
* (bropat) Fixed change video watermark setting (for indoor cameras and floodlight camera)
* (bropat) Updated versions of the package dependencies

### 0.3.1 (2021-03-06)
* (bropat) Fixed regression on livestream with h265 codec

### 0.3.0 (2021-03-05)
* (bropat) Implemented feature request [#88](https://github.com/bropat/ioBroker.eufy-security/issues/88): Enable/disable motion detection for camera products
* (bropat) Implemented feature request [#81](https://github.com/bropat/ioBroker.eufy-security/issues/81): Enable/disable RTSP stream (added also RTSP stream url)
* (bropat) Implemented asynchronous download of event videos when receiving a push notification
* (bropat) Optimized ffmpeg implementation to only muxing video data to HLS
* (bropat) Optimized HLS livestream video start delay (10-15 sec.)
* (bropat) Fixed possible race condition with ffmpeg when using fallback to Eufy RTMP live stream
* (bropat) Fixed issue with livestream when p2p connection is lost
* (bropat) Updated versions of the package dependencies

### 0.2.5 (2021-02-20)
* (bropat) Fixed possible race condition that brokes sometime the livestream
* (bropat) Updated versions of the package dependencies

### 0.2.4 (2021-02-20)
* (bropat) Fixed issue [#86](https://github.com/bropat/ioBroker.eufy-security/issues/86)
* (bropat) Fixed not correctly identifying if the livestream is still active or not

### 0.2.3 (2021-02-17)
* (bropat) Fixed wired doorbell p2p livestream (should fix also indoor, floodlight and solo cameras)
* (bropat) Fixed issue that treats known push notifications as unknown
* (bropat) Fixed relative path for state last_event_pic_url
* (bropat) Updated versions of the package dependencies

### 0.2.2 (2021-02-16)
* (bropat) Fixed web extension settings for serving videos and pictures (issue [#79](https://github.com/bropat/ioBroker.eufy-security/issues/78))

### 0.2.1 (2021-02-15)
* (bropat) Fixed device_enable state
* (bropat) Fixed battery doorbell start livestream over p2p (issue [#78](https://github.com/bropat/ioBroker.eufy-security/issues/78))
* (bropat) Implemented fallback for failed P2P livestream to RTMP livestream

### 0.2.0 (2021-02-14)
* (bropat) Implemented P2P livestream over HLS
* (bropat) Last livestream is always saved and is still available later
* (bropat) Implemented device and station parameter refresh over P2P
* (bropat) Revised push notification implementation
* (bropat) Fixed issue [#71](https://github.com/bropat/ioBroker.eufy-security/issues/71) by implementing retry mechanism on HTTP error 404 (max. 5 retries with increasing delay) 
* (bropat) Fixed issue [#12](https://github.com/bropat/ioBroker.eufy-security/issues/12)
* (bropat) Eufy client library extracted as standalone library and adapters ported to new shared library: [eufy-security-client](https://www.npmjs.com/package/eufy-security-client)
* (bropat) Removed following states: last_captured_pic_url, last_captured_pic_html
* (bropat) Updated versions of the package dependencies

### 0.1.5 (2021-01-14)
* (bropat) Fixed issue [#50](https://github.com/bropat/ioBroker.eufy-security/issues/50) and [#53](https://github.com/bropat/ioBroker.eufy-security/issues/53)
* (bropat) Updated versions of the package dependencies

### 0.1.4 (2021-01-05)
* (bropat) Fixed: Accept only valid modes for station guard mode (for invalid mode, an error is logged)
* (bropat) Fixed reset of an event (motion, ringing, etc.)
* (bropat) Updated versions of the package dependencies

### 0.1.3 (2021-01-02)
* (bropat) Fixed issue [#37](https://github.com/bropat/ioBroker.eufy-security/issues/37) and [#41](https://github.com/bropat/ioBroker.eufy-security/issues/41)
* (bropat) Updated versions of the package dependencies

### 0.1.2 (2021-01-02)
* (bropat) Revised captured_pic_url state (renamed to last_captured_pic_url and added last_captured_pic_html)
* (bropat) Fixed p2p issue passing wrong user id (action_user_id instead of admin_user_id)
* (bropat) Revised push notification to properly support doorbell notifications
* (bropat) Updated versions of the package dependencies

### 0.1.1 (2020-12-29)
* (bropat) Fixed issue [#37](https://github.com/bropat/ioBroker.eufy-security/issues/37)
* (bropat) Fixed version numbering
* (bropat) Updated versions of the package dependencies

### 0.0.9 (2020-12-28)
* (bropat) Finished implementation for feature request: [#1](https://github.com/bropat/ioBroker.eufy-security/issues/1)
* (bropat) Little progress for feature request: [#5](https://github.com/bropat/ioBroker.eufy-security/issues/5)
* (bropat) Now supports also cloud P2P communication if local P2P comunication isn't possible
* (bropat) Implemented set Guard Mode with CMD_SET_PAYLOAD for certain devices
* (bropat) Added back USA ip addresses for P2P cloud discovery
* (bropat) Using the correct local time zone for communication with the Eufy Cloud
* (bropat) HUB filtering by device type 0 (station) removed
* (bropat) Added documentation for 2FA
* (bropat) Updated versions of the package dependencies

### 0.0.8 (2020-12-13)
* (bropat) Fixed issue [#16](https://github.com/bropat/ioBroker.eufy-security/issues/16)
* (bropat) P2P communication revisited
* (bropat) Added reconnect functionality for P2P communication
* (bropat) Added heartbeat for P2P communication
* (bropat) Added local caching of last event picture as image url or html image (removed old state: last_camera_url)
* (bropat) Updated versions of the package dependencies

### 0.0.7 (2020-12-08)
* (bropat) Fixed issue [#11](https://github.com/bropat/ioBroker.eufy-security/issues/11)

### 0.0.6 (2020-12-06)
* (bropat) Fixed issue [#13](https://github.com/bropat/ioBroker.eufy-security/issues/13)

### 0.0.5 (2020-12-05)
* (bropat) Added event states for camera (motion detected, person detected)
* (bropat) Added event states for entry sensor (open/closed)
* (bropat) Added event states for motion sensor (motion detected)
* (bropat) Added event states for doorbell (motion detected, person detected, ringing)
* (bropat) Added event states for indoor camera (motion detected, person detected, crying detected, sound detected, pet detected)
* (bropat) Added entry sensor state (online, offline, etc.)
* (bropat) Added entry sensor low battery
* (bropat) Added motion sensor state (online, offline, etc.)
* (bropat) Added motion sensor low battery
* (bropat) Added keypad state (online, offline, etc.)
* (bropat) Added keypad low battery

### 0.0.4 (2020-12-03)
* (bropat) Better exception handling
* (bropat) Fixed push token handling
* (bropat) Added push connection retry mechanism
* (bropat) Added camera state (online, offline, etc.)
* (bropat) Added camera wifi RSSI
* (bropat) Added camera total events since last charge
* (bropat) Added camera saved/recorded events since last charge
* (bropat) Added camera filtered false events since last charge
* (bropat) Added camera used days since last charge
* (bropat) Added camera battery temperature

### 0.0.3 (2020-11-21)
* (bropat) Fixed issue with push notification credentials initialization

### 0.0.2 (2020-11-21)
* (bropat) Added push notification support for event notification (raw notifications!)
* (bropat) Added 2FA (token renewal needs manual intervention)
* (bropat) Added P2P communication with station (event: Alarm mode change)
* (bropat) Added more device classes (sensors, locks, keypads) with no actions (at the moment! WIP!)
* (bropat) Added all eufy camera devices release to date
* (bropat) Added battery state to eufy cameras

### 0.0.1 (2020-10-04)
* (bropat) initial release

## License
MIT License

Copyright (c) 2021 bropat <patrick.broetto@gmail.com>

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