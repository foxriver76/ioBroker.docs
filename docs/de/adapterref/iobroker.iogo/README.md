---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.iogo/README.md
title: TR: ioBroker.iogo
hash: QL2wzeIR6M4+eTIT45OnCbDxi4/yh6wmTyVyBdUwvKI=
---
![TR: Logo](../../../en/adapterref/iobroker.iogo/admin/iogo.png)

![TR: Number of Installations](http://iobroker.live/badges/iogo-stable.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.iogo.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.iogo.svg)
![TR: Travis-CI](http://img.shields.io/travis/nisiode/ioBroker.iogo/master.svg)
![TR: NPM](https://nodei.co/npm/iobroker.iogo.png?downloads=true)

TR: # ioBroker.iogo
TR: This adapter is adding extra features to the smarthome app ioGo https://play.google.com/store/apps/details?id=de.nisnagel.iogo.
Please visit www.iogo.app for more information on how to get started.

TR: ## Configuration
TR: You need a valid licence key to use this adapter.
A licence can be bought after creating an account at https://www.iogo.app.

TR: Please enter your account information (email/password) in the instance configuration.

TR: ## Usage
TR: You can send message to all authenticated users over messageBox `sendTo('iogo', 'New message')` or to specific user `sendTo('iogo', {user: 'Username', text: 'Test message'})`.
User must be created before (please read the application documentation for further details).

TR: It is possible to specify more than one recipient (just separate the Usernames by comma). For example: Recipient: "User1,User4,User5"

TR: Example how to send notification customized message with javascript:

```
sendTo('iogo', {
    user:                   'Username',
    text:                   'New message',
    title:                  'VIP News'
});
```

TR: And one example with blockly:

![TR: blockly](../../../en/adapterref/iobroker.iogo/img/blockly.png)

TR: Callbacks are supported as well:

```
sendTo('iogo', {title: 'News', text: 'New message'}, function (res) {
    console.log('Sent to ' + res + ' users');
});
```

TR: Just send the path to your image instead of text or use url attribute `sendTo('iogo.0', 'absolute/path/file.png')`

```
sendTo('iogo', {
    user:                   'Username',
    text:                   'New message',
    title:                  'VIP News',
    url:                    'absolute/path/file.png'
});
```

TR: **Possible options**:

TR: - `user`: Single user or list of users
TR: - `text`: The message itself
TR: - `title`: The notification's title
TR: - `url`: Absolute path to an image
TR: - `expiry`: Expiration time in seconds

TR: <!-- Placeholder for the next version (at the beginning of the line):

TR: ### __WORK IN PROGRESS__ -->

## Changelog
### 0.7.0 (2021-05-24)
* (bluefox) Added support of Admin5

### 0.6.x
* (nisio) Changes for ioGo app version 2.3.0+ (older versions no longer supported)

### 0.5.x
* (nisio) Changes for ioGo app version 2.1.0+ (older versions no longer supported)
* (nisio) Split main.js into several files

### 0.4.x
* (nisio) Changes for ioGo app version 2.0.0+ (older versions no longer supported)

### 0.3.x
* (nisio) added support of compact mode
* (nisio) added support node 12

### 0.2.x
* (nisio) added pro features

### 0.1.x
* (nisio) initial release

## License
The MIT License (MIT)

Copyright (c) 2018 - 2021 Nis Nagel <info@iogo.app>

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