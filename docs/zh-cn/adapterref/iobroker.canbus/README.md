---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.canbus/README.md
title: TR: ioBroker.canbus
hash: tMg9bs8laDd02JYcEJwNoU9LIeXIWbRTszVkW2f7KfE=
---
![TR: NPM version](https://img.shields.io/npm/v/iobroker.canbus.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.canbus.svg)
![TR: Number of Installations (latest)](https://iobroker.live/badges/canbus-installed.svg)
![TR: Number of Installations (stable)](https://iobroker.live/badges/canbus-stable.svg)
![TR: Dependency Status](https://img.shields.io/david/crycode-de/iobroker.canbus.svg)
![TR: NPM](https://nodei.co/npm/iobroker.canbus.png?downloads=true)

TR: # ioBroker.canbus
![TR: Logo](../../../en/adapterref/iobroker.canbus/admin/canbus.png)

[![TR: Translation status](https://weblate.iobroker.net/widgets/adapters/-/canbus/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

TR: **Tests:** ![TR: Test and Release](https://github.com/crycode-de/ioBroker.canbus/workflows/Test%20and%20Release/badge.svg)

TR: ## CAN bus adapter for ioBroker
TR: This adapter connects ioBroker to a Controller Area Network (CAN bus).

TR: **This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [TR: Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

TR: ## Features
TR: * Receive and send raw messages using standard frames and extended frames
TR: * Each message may be configured for receiving and/or sending data
TR: * Ability to automatically add objects for seen CAN messages which are not already configured
TR: * Configure parsers for each message to read/write data from/to the raw message buffer
TR:   * Numeric types
TR:   * Booleans including bitmask support
TR:   * Strings in different character encodings
TR:   * Custom scripts to read/write from/to the buffer of raw data
TR: * Advanced import/export feature
TR:   * Import message configurations to extends your existing configuration
TR:   * Import predefined "well known" configurations from GitHub within the admin interface
TR:   * Export and import your message configurations as `json` or `csv` files
TR: * Optional support for fixed data lengths (DLC)
TR: * Optional support for the RTR flag
TR: * Optional raw states containing raw CAN message objects
TR: * Optional automatically set a certain value in a given interval for each parser (usefull for polling data)

TR: ## Requirements
TR: * Linux operating system (because of the used socketcan library)
TR: * CAN Hardware which is supported by the kernel and creates an interface like `can0`
TR: * Some knowledge about the messages send on you CAN bus

TR: ## Parsers
TR: Using parsers you are able to read data from or write data to the CAN message buffer.

TR: There are predefined parsers for the following data types.
Additionally you may write you own scripts to read/write values with a *custom parser*.

TR: ### Numeric types in *big-endian* and *little-endian* reperesentation
TR: * Signed and unsigned 8, 16 and 32 bit integer
TR: * 32 bit float
TR: * 64 bit double

TR: ### Boolean
TR: * 1 byte including bitmask support

TR: ### String
TR: * 1 to 8 byte length
TR: * Encoding: *ascii*, *base64*, *hex*, *latin1*, *utf8*, *utf16le*

TR: ### Custom
TR: For a custom parser you have to provide you own read and write script.
These scripts should be pure javascript and will run in a sandbox.

TR: In the scripts you are able to use the following features:

TR: * Most of Node.js build in functions
TR: * `async`/`await`
TR: * Adapter log functions `log.warn('something')`, `log.info('something')`, `log.debug('something')`
TR: * `getStateAsync('id')` and `getObjectAsync('id')` where `id` is the full ID of the state/object

TR: Errors in the scripts will be logged by the adapter.

TR: In both scripts the variables `buffer` and `value` are predefined.
`buffer` always contains the current CAN message content as a Node.js Buffer.

TR: #### Custom read script
TR: In a read script you have to read the `value` from the `buffer` variable.

TR: At the beginning of the custom read script, `buffer` will be the received/current CAN message data (like in the `.json` state).
`value` will be `undefined` and should be set by the script.

TR: The content of the `value` variable at the end of the custom read script will be used as new value for the state.
If `value` is `undefined`, it will be ignored. Using this you are able to filter messages in the custom read script by data parts.

TR: ##### Example for a custom read script
TR: Check the first three bytes in the received buffer to match fixed values.
If matched, read an 16 bit signed integer value from the buffer bytes 3 and 4 and divide it by 10.

```js
if (buffer[0] === 0xC2 && buffer[1] === 0x10 && buffer[2] === 0x0F) {
  value = buffer.readInt16BE(3) / 10;
}
```

TR: Cause of `value` is only set when the first three bytes matched, all other data will be ignored and won't set a new value to the state.

TR: #### Custom write script
TR: In a write script you have to modify (or replace) the `buffer` variable.

TR: At the beginning of the custom write script, `buffer` will be the current CAN message data (like in the `.json` state).
`value` is set to the value of the state which should be written into the `buffer`.

TR: The content of the `buffer` variable at the end of the custom write script will be used as new data for the CAN message.

TR: ##### Example for a custom write script
TR: Prepare a new buffer with fixed values.
Write the state value into the buffer as a signed 16 bit integer, beginning at the fifth byte in the buffer.

```js
buffer = Buffer.from([0x30, 0x00, 0xFA, 0x06, 0x7E, 0x00, 0x00]);
buffer.writeInt16BE(value, 5);
```

TR: The new `buffer` will then be set as the `.json` state.
If the *autosend* option is enabled for the message, the message will be automatically send.

TR: ## Usage in scripts
TR: You can handle/modify the `<messageId>.json` or `<messageId>.<parserId>` states in your scripts.

TR: Additionally you may use the `raw.received` and `raw.send` states, if you have them enabled in the adapter config.
They hold the stringified JSON data of the message data and can be used to handle each received or send message independent from the configured messages.
By writing JSON data to the `raw.send` state you are able to send CAN messages containing any data you like.

TR: ### Raw message object example
```js
{
  "id": 42,
  "ext": false,
  "data": [0, 13, 37, 255],
  "rtr": false
}
```

TR: `ext` and `rtr` are optional and default to `false`.

## Changelog

### 1.2.1 (2021-06-22)
* (crycode-de) Added option to automatically set a certain value in a given interval for each parser
* (crycode-de) Added checks for duplicate parser IDs
* (VeSler) Russian translation updates
* (crycode-de) Use inline sourcemaps for the adapter build files to make remote debugging work
* (crycode-de) Updated dependencies

### 1.1.4 (2021-04-30)
* (crycode-de) Added license information to import of well-known configurations
* (crycode-de) Fixed "Parser returned wrong data type undefined" log message
* (crycode-de) Updated dependencies

### 1.1.3 (2021-04-12)
* (crycode-de) Added definition of possible state values in admin
* (crycode-de) Added selection of the state role for each parser in admin
* (crycode-de) Fixed display bug of floating action buttons in admin
* (crycode-de) Export uses defaults if some config parts are not defined (e.g. if the config is from an older version)
* (crycode-de) Fixed wrong validation if a message/parser was deleted

### 1.1.2 (2021-04-06)
* (crycode-de) Added copy/paste function for message and parser configurations in admin

### 1.1.1 (2021-04-02)
* (crycode-de) Import bugfixes
* (crycode-de) Prevent wrong log warning if a parser returned undefined
* (crycode-de) Added react errorboundary for better clientside error handling

### 1.1.0 (2021-04-01)
* (crycode-de) Added import/export feature for messages in json or csv format
* (crycode-de) Added import of well known configurations from GitHub
* (crycode-de) Fixed config import in admin
* (crycode-de) Added ioBroker state data type option for custom parsers

### 1.0.2 (2021-03-26)
* (crycode-de) Fixed issue where missing state prevented custom parser write
* (DutchmanNL) Dutch translation updates
* (UncleSamSwiss) French translation updates
* (VeSler) Russian translation updates

### 1.0.1 (2021-03-12)
* (crycode-de) Use a queue to process _parser_ and _send_ state changes in the correct order
* (crycode-de) Fixed some spelling issues
* (crycode-de) Updated dependencies

### 1.0.0 (2021-02-23)
* (crycode-de) Sort messages in admin
* (VeSler) Russian admin translations
* (crycode-de) Updated dependencies

Older changelog is in CHANGELOG_OLD.md

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)

Copyright (c) 2020-2021 Peter Müller <peter@crycode.de> (https://crycode.de/)