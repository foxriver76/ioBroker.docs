---
BADGE-Number of Installations: http://iobroker.live/badges/bring-installed.svg
BADGE-Stable version: http://iobroker.live/badges/bring-stable.svg
BADGE-NPM version: http://img.shields.io/npm/v/iobroker.bring.svg
BADGE-Downloads: https://img.shields.io/npm/dm/iobroker.bring.svg
BADGE-NPM: https://nodei.co/npm/iobroker.bring.png?downloads=true
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.bring/README.md
title: TR: ioBroker.bring
hash: OZhjDNOBP7gPGWiHnvQq6ZDL5FVpF0lZ7JnqtpmifNM=
---
![TR: Logo](../../../en/adapterref/iobroker.bring/admin/bring.png)

![TR: Number of Installations](http://iobroker.live/badges/bring-installed.svg)
![TR: Stable version](http://iobroker.live/badges/bring-stable.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.bring.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.bring.svg)
![TR: NPM](https://nodei.co/npm/iobroker.bring.png?downloads=true)

TR: # ioBroker.bring
===========================

![TR: Build Status](https://github.com/foxriver76/ioBroker.bring/workflows/Test%20and%20Release/badge.svg)

TR: ## Disclaimer
TR: The developers of this module are in no way endorsed by or affiliated with Bring! Labs AG, or any associated subsidiaries, logos or trademarks.

TR: ## States
TR: For a description of the created states, see below.

TR: ### Channel: info
TR: * info.connection

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |boolean|R|

TR:    *Read-only boolean indicator. If your broker is logged in on bring, the state is true otherwise false.*

TR: * info.user

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R|

TR:    *Read only string. Contains the name of the logged-in user.*

TR: ### Shopping lists
TR: For every shopping list a channel with the following states will be created:

TR: **list*.content /* ist*.contentHtml/NoHead

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R|

TR: *Read only json/html string formatted as a list or html table. Contains the items which are currently on your shopping list.
The NoHead Html tables are w/o table headers.*

TR: **list*.recentContent /* ist*.recentContentHtml/NoHead

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R|

TR: *Read only json/html string formatted as a list or html table. Contains the items which were recently on your shopping list.
The NoHead Html tables are w/o table headers.*

TR: * *list*.removeItem

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR: *Select an item which should be removed from the shopping list and recent content list.
The state will be acknowledged when the command is acknowledged by the Bring! API.*

TR: * *list*.moveToRecentContent

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR: *Select an item which should be moved or added to recent content list.
The state will be acknowledged when the command is acknowledged by the Bring! API.*

TR: * *list*.saveItem

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR: *Select an item which should be added to the shopping list. You can also specify additional information of the item, by setting the state by the following schema:*

```Apple, 2.50 $, the green ones```

TR: *Note, that everything behind the comma describes the specification.
The state will be acknowledged when the command is acknowledged by the Bring! API.*

TR: **list*.users /* ist*.usersHtml/NoHead

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R|

TR: *Read only json/html string formatted as a list or html table. Contains the users which are part of the shopping list, as well as their email address.
The NoHead Html tables are w/o table headers.*

TR: * *list*.count

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |number|R|

TR:    *Read only number, which represents the number of contained items of the list.*

TR: * *list*.messageTrigger

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |button|R/W|

TR: *If you press this button, the shopping list will be sent to the configured instances, e. g. Pushover, Telegram or/and E-Mail.*

TR: * *list*.enumSentence

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R|

TR: *Read only string, which contains an enumeration of the shopping list items in a speakable form.
This can be used e. g. for voice output via smart assistants.*

TR: * *list*.translation

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R|

TR:     *Read only json string, which contains a dictionary to translate the swiss item names to the list language.*

## Changelog
### 1.7.7 (2020-12-12)
* (foxriver76) fix potential crash on `pollAllLists` function

### 1.7.6 (2020-12-05)
* (foxriver76) we now use a unique name for widget rendering function to avoid conflicts
* (foxriver76) if we cannot render widget immediately we try again after one second (see #57)

### 1.7.4 (2020-12-04)
* (foxriver76) we now render the widget immediately

### 1.7.3 (2020-10-26)
* (foxriver76) bring module now returns real errors instead of strings, handle them correct

### 1.7.2 (2020-04-23)
* (foxriver76) fixed potential issue on rendering widget

### 1.7.1 (2020-02-13)
* (foxriver76) we are now using AES-256-CBC as encryption

### 1.6.8 (2019-12-31)
* (foxriver76) ensure compatibility with older browsers

### 1.6.6 (2019-11-21)
* (foxriver76) improved error handling in widget

### 1.6.5 (2019-09-22)
* (foxriver76) re-auth when bearer token is no longer valid

### 1.6.3 (2019-08-28)
* (foxriver76) fixed bug which only allowed one registered event handler
* (foxriver76) by using obj with wid instead of var because vis handles global variables of widgets global
* (foxriver76) now more bring widgets can be used in one vis project
* (foxriver76) bump version of textFit to 2.3.1 -> 2.4.0 and use minified version

### 1.6.2 (2019-08-04)
* (foxriver76) also use translations for enumSentence and notifiations (e. g. email)

### 1.6.1 (2019-07-13)
* (foxriver76) fixed bug, that prevent html states and other from being set

### 1.6.0 (2019-07-12)
* (foxriver76) get translations according to list language
* (foxriver76) translations will be stored in datapoint
* (foxriver76) use bring-node-api at least 1.2.1
* (foxriver76) widget now uses configured language
* (foxriver76) bugfixes and optimizations in front- and backend

### 1.4.0 (2019-06-07)
* (foxriver76) use textFit to fit text to one line in widget
* (foxriver76) internal reworks on widget

### 1.3.4
* (foxriver76) add possibility to use this widget multiple times on same page

### 1.3.3
* (foxriver76) also change height and div sizes according to users specification
* (foxriver76) when item is on recent list and added by text input it is now instantly removed from recent list

### 1.3.2
* (foxriver76) enable configuration of width for items in widget

### 1.3.1
* (foxriver76) api module outsourced

### 1.3.0
* (foxriver76) added widget
* (foxriver76) add possibility to move items to recentContent

### 1.2.1
* (foxriver76) uri encode login request because it can contain special character

### 1.2.0
* (foxriver76) added state which contains a speakable enumeration of each shopping list

### 1.1.0
* (foxriver76) add possibility to send messages
* (foxriver76) respect in app list renaming / recreate channel on name change

### 1.0.0
* (foxriver76) stable release
   
### 0.0.10
* (foxriver76) set info.connection state to false, when cannot get data
   
### 0.0.9
* (foxriver76) also update no head states on normal polling
* (foxriver76) fix bug where polling could grow exponentially
* (foxriver76) fix unhandled error when no internet connection

### 0.0.8
* (foxriver76) add html states w/o header
* (foxriver76) minor fixes
   
### 0.0.7
* (foxriver76) fixed a potential memory leak by setTimeout functions

### 0.0.6
* (foxriver76) add equivalent html states for json states
* (foxriver76) add counter for every list

### 0.0.4
* (foxriver76) fix when login fails

### 0.0.3
* (foxriver76) initial release

## License
The MIT License (MIT)

Copyright (c) 2019-2020 Moritz Heusinger <moritz.heusinger@gmail.com>

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