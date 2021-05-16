---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.mielecloudservice/README.md
title: TR: ioBroker.MieleCloudService
hash: kkSktIrdhuN2rLvgkbAYfJcBEo8WMtlHoRqWRIw9uW0=
---
![TR: Logo](../../../en/adapterref/iobroker.mielecloudservice/admin/mielecloudservice.svg)

![TR: Number of Installations](http://iobroker.live/badges/mielecloudservice-stable.svg)
![TR: NPM version](https://img.shields.io/npm/v/iobroker.mielecloudservice.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/Grizzelbee/ioBroker.mielecloudservice/badge.svg?targetFile=package.json)
![TR: NPM](https://nodei.co/npm/iobroker.mielecloudservice.png?downloads=true)
![TR: License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.mielecloudservice.svg)

TR: # ioBroker.MieleCloudService [![TR: Build Status](https://travis-ci.com/Grizzelbee/ioBroker.mielecloudservice.svg?branch=master)](https://travis-ci.com/Grizzelbee/ioBroker.mielecloudservice)
TR: ## Description
TR: This adapter is for retrieving information about all your Miele@Home devices from the official Miele 3rd-party API.
Regardless if they are connected directly via Wi-Fi or XGW3000 Gateway. It implements the **Miele 3rd Party API V1.0.4**

TR: ## sentry.io
TR: This adapter uses sentry.io to collect details on crashes and report it automated to the author. The [TR: ioBroker.sentry](https://github.com/ioBroker/plugin-sentry) plugin is used for it. Please refer to the [TR: plugin homepage](https://github.com/ioBroker/plugin-sentry) for detailed information on what the plugin does, which information is collected and how to disable it, if you don't like to support the author with you're information on crashes.

TR: ## Prerequisites
TR: * Miele@Home User (Smartphone App)
TR: * Miele@Home Password (Smartphone App)
TR: * Miele Client_id (from https://www.miele.com/developer/)
TR: * Miele Client_secret (from https://www.miele.com/developer/ )

TR: ## Installation
TR: To install, do the following:

TR: 1. Install via Admin using the
TR:  * stable Repo - to get the current stable version
TR:  * latest Repo - to get the latest test version (maybe not stable)
TR:  * via: https://github.com/Grizzelbee/ioBroker.mielecloudservice.git - to get the latest development version
TR: 2. create an App-Account for Miele@Home in the Miele Smartphone App
TR: 3. Create a developer account at https://www.miele.com/f/com/en/register_api.aspx
TR: 4. Add your Miele-Devices to the App (if not added automatically)
TR: 6. Fill in the client_secret and client_id received from Miele-developer Team and account-id and password from the App.

TR: ## Controlling your devices
TR: All currently supported and documented Actions for all devices are implemented (API V1.0.4).
> Please remember that Actions will only work if you put your device into the appropriate state (e.g. Mobile Control, powerOn, ...).
Please refer to [TR: Miele-Documentation](#documentation) for more Information on actions.

TR: ## Known Issues
TR: * none

TR: ## Documentation
TR: Please mainly refer to the main API documentation published by Miele

TR: * [General Documentation](https://www.miele.com/developer/swagger-ui/index.html)
TR: * [Preconditions to perform an action on a device](https://www.miele.com/developer/swagger-ui/put_additional_info.html)

TR: There are some data points available in 2 kinds. As a human-readable text and as a number.
These numeric data fields belonging to a text field have the same name, but a "_raw" appended.
Those fields which have a general meaning are listed below.
The fields which aren't listed vary in their meaning from device to device and are not documented by Miele.
If you need to refer in scripts to these fields, always use the _raw values.
The text values may change in the future and also depend on the language.
Here is a list of what these raw values stand for:

TR: ### DeviceTypes
| TR:  | Raw value | State|
 |----------|-------|
| TR:  |1 | WASHING MACHINE|
| TR:  |2 | TUMBLE DRYER|
| TR:  |7 | DISHWASHER|
| TR:  |8 | DISHWASHER SEMI-PROF|
| TR:  |12 | OVEN|
| TR:  |13 | OVEN MICROWAVE|
| TR:  |14 | HOB HIGHLIGHT|
| TR:  |15 | STEAM OVEN|
| TR:  |16 | MICROWAVE|
| TR:  |17 | COFFEE SYSTEM|
| TR:  |18 | HOOD|
| TR:  |19 | FRIDGE|
| TR:  |20 | FREEZER|
| TR:  |21 | FRIDGE-/FREEZER COMBINATION|
| TR:  |23 | VACUUM CLEANER, AUTOMATIC ROBOTIC VACUUM CLEANER|
| TR:  |24 | WASHER DRYER|
| TR:  |25 | DISH WARMER|
| TR:  |27 | HOB INDUCTION|
| TR:  |28 | HOB GAS|
| TR:  |31 | STEAM OVEN COMBINATION|
| TR:  |32 | WINE CABINET|
| TR:  |33 | WINE CONDITIONING UNIT|
| TR:  |34 | WINE STORAGE CONDITIONING UNIT|
| TR:  |39 | DOUBLE OVEN|
| TR:  |40 | DOUBLE STEAM OVEN|
| TR:  |41 | DOUBLE STEAM OVEN COMBINATION|
| TR:  |42 | DOUBLE MICROWAVE|
| TR:  |43 | DOUBLE MICROWAVE OVEN|
| TR:  |45 | STEAM OVEN MICROWAVE COMBINATION|
| TR:  |48 | VACUUM DRAWER|
| TR:  |67 | DIALOGOVEN|
| TR:  |68 | WINE CABINET FREEZER COMBINATION|

TR: ### State/Status
| TR:  | Raw value | State|
 |----------|-------|
| TR:  |1|   OFF|
| TR:  |2|   STAND_BY|
| TR:  |3|   PROGRAMMED|
| TR:  |4|   PROGRAMMED_WAITING_TO_START|
| TR:  |5|   RUNNING|
| TR:  |6|   PAUSE|
| TR:  |7|   END_PROGRAMMED|
| TR:  |8|   FAILURE|
| TR:  |9|   PROGRAMME_INTERRUPTED|
| TR:  |10|  IDLE|
| TR:  |11|  RINSE_HOLD|
| TR:  |12|  SERVICE|
| TR:  |13|  SUPERFREEZING|
| TR:  |14|  SUPERCOOLING|
| TR:  |15|  SUPERHEATING|
| TR:  |144| DEFAULT|
| TR:  |145| LOCKED|
| TR:  |146| SUPERCOOLING_SUPERFREEZING|
| TR:  |255| Device offline|

TR: ### ProgramType/Programmart
| TR: | Raw value | State|
|----------|-------|
| TR: |0 | Normal operation mode  |
| TR: |1 | Own program            |
| TR: |2 | Automatic program      |
| TR: |3 | Cleaning-/Care program |

TR: ### dryingStep/Trockenstufe
| TR:  | Raw value | State|
 |----------|-------|
| TR:  |0 |   Extra dry|
| TR:  |1 |   Normal Plus|
| TR:  |2 |   Normal|
| TR:  |3 |   Slightly Dry|
| TR:  |4 |   Hand iron level 1|
| TR:  |5 |   Hand iron level 2|
| TR:  |6 |   Machine iron|

TR: ### Programmbezeichnung
| TR: | Raw value | State                   | available for   |
|-----------|-------------------------|-----------------|
| TR: |         1 | "Baumwolle" / "Cotton"  | Washing Machine |
| TR: |         3 | "Pflegeleicht"          | Washing Machine |
| TR: |         4 | "Feinwäsche"            | Washing Machine |
| TR: |         8 | "Wolle"                 | Washing Machine |
| TR: |         9 | "Seide"                 | Washing Machine |
| TR: |        21 | "Pumpen/Schleudern"     | Washing Machine |
| TR: |        23 | "Oberhemden"            | Washing Machine |
| TR: |        27 | "Imprägnieren"          | Washing Machine |
| TR: |        29 | "Sportwäsche"           | Washing Machine |
| TR: |        31 | "Automatic plus"        | Washing Machine |
| TR: |        37 | "Outdoor"               | Washing Machine |
| TR: |        48 | "Flusen ausspülen"      | Washer Dryer    |
| TR: |        50 | "Dunkle Wäsche"         | Washer Dryer    |
| TR: |        52 | "Nur Spülen/Stärken"    | Washing Machine |
| TR: |       122 | "Express 20"            | Washer Dryer    |
| TR: |       123 | "Dunkles/Jeans"         | Washing Machine |

TR: ### ProgramPhase
| TR: | Raw value | State| available for |
|----------|-------|---------------|
| TR: |258 | "Einweichen"           | Washing Machine |
| TR: |260 | "Waschen" / "Washing"  | Washing Machine |
| TR: |261 | "Spülen"  / "Rinse"    | Washing Machine |
| TR: |265 | "Pumpen" | Washing Machine |
| TR: |266 | "Schleudern" / "Spinning" | Washing Machine |
| TR: |267 | "Knitterschutz" / "" | Washing Machine |
| TR: |268 | "Ende" / "End" | Most devices |
| TR: |256 | "Vorbügeln" | Washing Machine |
| TR: |514 | "Trocknen" | Washer Dryer |
| TR: |519 | "Abkühlen" | Washer Dryer |
| TR: |532 | "Flusen ausspülen" | Washer Dryer |

TR: ## Copyright
TR: Copyright (c) 2019, 2021 grizzelbee <open.source@hingsen.de>

## Changelog

### V4.1.0 (2021-05-15) (Carry me over)
* (grizzelbee) New: [149](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/149) Adding support (Start, Stop, Pause) for Miele Scout RX2 vacuum cleaner robots
* (Stan23)     New: Added new program phase  soak/Einweichen

### V4.0.22 (2021-05-06) (Twisted mind)
* (grizzelbee) Fix: [142](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/142) Reintroduced TargetTemp for washing machines

### V4.0.21 (2021-05-03) (The Edge)
* (grizzelbee) Fix: Fixed accidental function name: createStateSpinAPIStartActionningSpeed
* (grizzelbee) Fix: Fixed State value to set for "*.PlateStep_1" has to be type "number" but received type "string"

### V4.0.20 (2021-04-30) (Sleepwalkers)
* (grizzelbee) Fix: [137](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/137) Fixed Read-only state "info.connection" has been written without ack-flag with value "false"
* (grizzelbee) Fix: [138](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/138) Fixed State value to set for ".Schleuderdrehzahl" has wrong type "string" but has to be "number"
* (grizzelbee) Fix: [139](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/139) Fixed State value to set for ".ACTIONS.Light" has wrong type "number" but has to be "string" 
* (grizzelbee) Upd: Changed device group from channel to folder  as documented [here](https://github.com/ioBroker/ioBroker.docs/blob/master/docs/en/dev/objectsschema.md)

### V4.0.19 (2021-04-29) (The scarecrow)
* (grizzelbee) Fix: Fixed light switch bug causing an exception when switching - 2nd attempt
* (grizzelbee) Fix: Fixed No-Icon Bug when appliance is unknown

### V4.0.18 (2021-04-28) (Ghostlights)
* (grizzelbee) Fix: Fixed light switch bug causing an exception when switching 

### V4.0.17 (2021-04-27) (Ghost in the moon)
* (grizzelbee) New: Added ioBroker sentry plugin to report issues automatically
* (grizzelbee) New: Added Light-Switch to washing machines, Tumble Dryers, Washer dryers and Dish washers
* (grizzelbee) Upd: Updated dependencies

> **Hint:** 
> The behavior of the light-switch has slightly changed with this release. It not only tests the action capabilities of 
> the device but also shows the state of the light state delivered by the API. If no actions are reported by the API, the 
> switch will be without function and only show the current state. If actions have been reported the switch will work as you expect.
> If your device reports no light state and no actions the switch will show 'None' and won't do anything.

### V4.0.16 (2021-04-21) (Black Orchid)
* (grizzelbee) Fix: Units for EcoFeedback will be shown now, even machine is not running during setup
* (stan23)     New: added new program states

### V4.0.15 (2021-04-19) (Moonglow)
* (grizzelbee) Fix: [130](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/130) targetTemp for fridges and freezers will now correctly been updated in action section with current values

### V4.0.14 (2021-04-18) (Alchemy)
* (grizzelbee) Fix: [127](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/127) targetTemp for fridges caused exception and crash of adapter

### V4.0.13 (2021-04-12) (The toy master)
* (grizzelbee) Fix: [90](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/90) targetTemp addresses zones for fridges and freezers dynamically now

### V4.0.12 (2021-04-12) (Promised land)
* (grizzelbee) Fix: [90](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/90) targetTemp addresses zones for fridges and freezers dynamically now

### V4.0.11 (2021-04-11) (Cry just a little)
* (grizzelbee) Fix: targetTemp min and max values are now taken from API - no constant values anymore

### V4.0.10 (2021-04-10) (Another angel down)
* (grizzelbee) Fix: targetTemp min and max values are now taken from API - no constant values anymore

### V4.0.9 (2021-04-09) (Farewell)
* (grizzelbee) Fix: Errors during action execution will be shown correctly
* (grizzelbee) Fix: Actions will be executed correctly

### V4.0.8 (2021-04-09) (The seven angels)
* (grizzelbee) Fix: fixed datatype of VentilationStep data point
* (grizzelbee) Fix: fixed ventilation step switch for hoods (attempt 4)

### V4.0.7 (2021-04-09) (Lost in space)
* (grizzelbee) Fix: [90](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/90) added missing path to object ID; data point will be created in the correct place now
* (grizzelbee) New: targetTemp min and max values are now taken from API - no constant values anymore

### V4.0.6 (2021-04-08) (The great mystery)
* (grizzelbee) Fix: fixes Light switch for hoods and other devices supporting light
* (grizzelbee) Fix: fixes ventilation step switch for hoods (attempt 3)

### V4.0.5 (2021-04-08) (The haunting)
* (grizzelbee) Fix: fixes ventilation step switch for hoods (attempt 2)
* (grizzelbee) Fix: fixes error on creating TargetTemperature data points

### V4.0.4 (2021-04-07) (Wastelands)
* (grizzelbee) Fix: fixes ventilation step switch for hoods
* (grizzelbee) Fix: fixed missing getLightState

### V4.0.3 (2021-04-07) (The raven child)
* (grizzelbee) Fix: [109](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/109) fixes 404 error when querying possible actions for device.
* (grizzelbee) Fix: fixes errors when executing actions on devices with API-Id!=fabNumber

### V4.0.2 (2021-04-07) (Angel of Babylon)
* (grizzelbee) Fix: [107](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/107) fixes #107 and 404 error when device is unknown.

### V4.0.1 (2021-04-06) (Sign of the cross)
* (grizzelbee) Fix: [90](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/90) setting the targetTemperature should work now.
* (grizzelbee) Fix: [96](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/96) Added missing ACTIONS.Action_Information again
* (grizzelbee) Fix: [97](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/97) removed unneeded additional "VentilationStep/Lüfterstufe" in path and fixed warning with this. VentilationStep-switch should work properly now.
* (grizzelbee) Fix: [98](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/98) Color-Action has now valid type 'String'
* (grizzelbee) Fix: [102](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/102) Fixed ACTIONS.VentilationStep has no existing object
* (grizzelbee) Fix: Power switch is write protected now when in state 'None'. State 'None' means: No action permitted.
* (grizzelbee) Fix: Light switch is write protected now when in state 'None'. State 'None' means: No action permitted.
* (grizzelbee) Fix: http error 404 will be catched when requesting device actions

### V4.0.0 (2021-03-18) (Symphony of life)
> ***Hint:*** The adapter received a complete code refactoring! This means that most of the code has been changed and some parts are working now differently than ever before. Update with care and read the change log!
* (grizzelbee) New: FULL support of Miele cloud API v1.0.4
* (grizzelbee) Upd: [83](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/83) estimatedEndTime isn't shown anymore after the device has finished
* (grizzelbee) Upd: [85](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/85) full code refactoring and split into multiple files. 
* (grizzelbee) Upd: [86](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/86) every folder and device now gets a nice little icon
* (grizzelbee) Upd: [89](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/89) Washer dryers are fully supported now
* (grizzelbee) Upd: [90](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/90) implemented targetTemperature for fridges & freezers
* (grizzelbee) Upd: Devices get fully created on startup and aren't modified afterwards - only updated
* (grizzelbee) Upd: New folder ecoFeedback to group ecoFeedback states 
* (grizzelbee) Upd: New folder IDENT to group ident states
* (grizzelbee) Upd: Removed signalActionRequired - since there is no signalDoor for washing machines, dryers and dishwashers this approach doesn't work
* (grizzelbee) Upd: All folders and states which are being created depend on the capabilities of their devices as described in [this Miele documentation](https://www.miele.com/developer/assets/API_V1.x.x_capabilities_by_device.pdf). So there shouldn't be useless states anymore caused by the generic Miele cloud API.

### V3.0.2 (2021-03-05)
* (grizzelbee) Fix: [79](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/79) When a devices serial is missing, the identNumber is assigned instead.
* (grizzelbee) Upd: Changed folder name cooktops to hobs since this is the more common name
* (grizzelbee) Upd: added PowerOn/Off buttons for Coffee-systems & hoods
* (grizzelbee) Upd: [74](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/74) testing actions better before sending to permit errors

### V3.0.1 (2021-02-25)
> *Hint:* Action_Information and Action_Status objects are created on first action execution and contain infos to the last executed action.
> Please take care of notes regarding [Controlling your devices](#Controlling your devices).
* (grizzelbee) Upd: Improved logging in some parts - objects get stringified.
* (grizzelbee) Fix: [74](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/74) Actions are working again
* (grizzelbee) Upd: Actions are tested before sending whether they are permitted in current device state
* (grizzelbee) Upd: estimatedEndTime doesn't show seconds anymore
* (grizzelbee) Upd: Improved documentation
* (grizzelbee) Upd: removed unused function decrypt
* (grizzelbee) Upd: removed superfluent parameters


### V3.0.0 (2021-02-18)
> Hint: ecoFeedback objects are created on the first run of the device. This allows to only create them, when they contain data.
* (grizzelbee) New: BREAKING CHANGE: Making use of build-in password de-/encryption. This raises the need to re-enter your passwords again, because the old ones can't be decrypted anymore.
* (grizzelbee) New: [70](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/70) Implements Miele API 1.0.4
* (grizzelbee) New: [64](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/64) Introduces data point estimatedFinishingTime
* (grizzelbee) New: [54](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/54) Poll interval can now freely be selected in seconds and minutes
* (grizzelbee) Upd: [73](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/73) BREAKING CHANGE: Removed white-spaces from any ID in device tree. This creates completely new device trees. So please delete the old ones.
* (grizzelbee) Upd: removed david-dm badge
* (grizzelbee) Upd: updated dependencies
* (grizzelbee) Fix: added passwords to encryptedNative
* (grizzelbee) Fix: added passwords to protectedNative
* (grizzelbee) Fix: [63](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/63) added missing info.connection object to io-package
* (grizzelbee) Fix: [63](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/63) Fixed new Warnings introduced with js-controller 3.2
* (grizzelbee) Fix: [74](https://github.com/Grizzelbee/ioBroker.mielecloudservice/issues/74) Light-Actions should work now

### V2.0.3 (2020-09-15)
* (grizzelbee) Upd: Updated country list in config dialog
* (grizzelbee) New: Some more debug code

### V2.0.2 (2020-09-15)
* (grizzelbee) New: Added some debug Code to find an Error
* (grizzelbee) Fix: fixed error on failed authentication preventing a valid error message

### V2.0.1 (2020-09-14)
* (grizzelbee) New: Added some debug Code to find an Error
* (grizzelbee) Fix: fixed error on logout while invalidating token

### V2.0.0 - Support for Miele API V1.0.3 (2020-08-25)
Some breaking changes in this release. Some data points changed their type. May require fixes in scripts. **Update with care!**
Due to the fix that data points with invalid values aren't created any longer, I recommend deleting all data points in Object view.
* (grizzelbee) Change: New Icon
* (grizzelbee) Fix: Number-data points are no longer created as strings due to their unit. They are correct numbers with units now.
* (grizzelbee) Fix: Unit °Celsius is now shown as °C - not longer °Celsius
* (grizzelbee) New: Introduced support for °Fahrenheit
* (grizzelbee) New: Introduced support for new Value "plateStep" for Hobs.
* (grizzelbee) New: Performing a LogOut from Miele API on shutdown to invalidate the Auth-Tokens.
* (grizzelbee) Fix: Data points with invalid values (null/-32768) are no longer created.

### V1.2.4 (2020-06-09)
* (grizzelbee) Fix: fixed No-Data Bug (introduced in V1.2.3)

### V1.2.3 (2020-06-07)
* (grizzelbee) Upd: fixed snyk badge
* (grizzelbee) Upd: Improved error handling

### V1.2.2 (2020-05-23)
* (grizzelbee) Upd: removed node 8 from testing on travis.com
* (grizzelbee) Fix: signalActionRequired should work better now
* (grizzelbee) Upd: Updated documentation
* (grizzelbee) Upd: Improved error handling in function APISendRequest
* (grizzelbee) Fix: Moved testing of Config to On(Ready) and fixed unit tests with this.

### V1.2.1 (2020-04-22)
* (grizzelbee) New: Introduced new boolean state (**signalActionRequired**) that indicates that the machine has finished running, but a human action, like putting the wet clothes to the dryer, ... is needed. State is cleared automatically when the door of the appliance is opened, or it is restarted. State is implemented for washing machines, tumble dryers, washer dryer and dishwashers. **Doesn't work perfectly currently.**
* (grizzelbee) Upd: Updated Documentation
* (grizzelbee) Fix: Fixed warnings with js-Controller >=3.0 (Issue #23)

### V1.2.0 (2020-04-18)
* (grizzelbee) New: Added new boolean state (**Connected**) that indicates whether the device is connected to WLAN or a gateway.
* (grizzelbee) New: Added new boolean state (**signalInUse**) that indicates whether the device is switched off (false) or in Use (true).
* (grizzelbee) Change: replaced the deprecated http-library **request** with **axios**
* (grizzelbee) Change: Made functions communicating with API asynchronous

### V1.1.0 (2020-03-07)
* (grizzelbee) New: Added Actions - Implemented all currently supported and documented Actions for all devices.
> Please remember that Actions will only work if you put your device into the appropriate state (e.g. Mobile Control)
please refer to [Miele-Documentation](#documentation) for more Information on actions.

### V1.0.5 (2020-02-14)
* (grizzelbee) removed node-schedule as a dependency
* (grizzelbee) implemented scheduling via setTimeout, which raises the opportunity
  to schedule with less than a minute in the future

### V1.0.4 (2020-02-12)
* (grizzelbee) removed unneeded setTimeout from main
* (grizzelbee) Clearing scheduler on unload of adapter
* (grizzelbee) Minor updates and fixed typos in Readme

### V1.0.3 (2020-02-06)
* (grizzelbee) removed an overseen logging of Passwords
* (grizzelbee) Fixed createTemperatureDatapoint to work with less than 3 values delivered from API
* (grizzelbee) Added some documentation
* (grizzelbee) Started implementation of DeviceActions


### V1.0.2 (2020-02-05)
* (grizzelbee) removed any logging of Passwords
* (grizzelbee) Fixed bug in config interface introduced during password encryption that config values aren't loaded properly

### V1.0.1 (2020-02-04)
* (grizzelbee) Fixes in environment for getting adapter into the Repo
* (grizzelbee) Passwords are stored encrypted now

### V1.0.0 (2020-02-03)
* (grizzelbee) renamed to MieleCloudService to get the ability to publish; the old Name is still blocked by hash99
* (grizzelbee) Rewritten adapter from scratch - therefore it's incompatible with prior versions and needs to be installed freshly.
* (grizzelbee) Fix: fixed all build-errors
* (grizzelbee) Fix: Fixed "NRefreshToken is not a function"-Bug
* (grizzelbee) Chg: removed Push-API checkbox (maybe introduced newly when API supports this)
* (grizzelbee) Chg: New Icon
* (grizzelbee) New: added support for non-german Miele-Accounts (ALL should be included)
* (grizzelbee) Complete new layout of data points
* (grizzelbee) Device types are grouped now

### 0.9.1 (2019-07-26)
* (grizzelbee) Fix: Fixed small bug introduced in V0.9.0 throwing an exception in debugging code

### 0.9.0 (2019-07-26)
* (grizzelbee) Upd: New versioning due to completeness and stability of the adapter (about 90%)
* (grizzelbee) New: make poll interval configurable  (currently 1,2,3,4,5,7,10,15 Minutes)
* (grizzelbee) Fix: fixed ESLint config
* (grizzelbee) Upd: Changed order of config fields in UI
* (grizzelbee) New: Set 5 Minutes poll interval and english response language as default to get initial values
* (grizzelbee) New: Parent-Datapoint of time values will be used to get a pretty readable time in the format h:mm. The deeper datapoints 0 and 1 will still be updated, but his will be removed in a future version to reduce workload.

### 0.0.5 (2019-07-25)
* (grizzelbee) Upd: some code maintenance
* (grizzelbee) New: added reply-language to config
  - Miele API is currently able to reply in German or English, now you can choose.
* (grizzelbee) New: created new Icon
* (grizzelbee) Fix: fixed translation issues and translated adapter UI using gulp
* (grizzelbee) Upd: Made changes to travis requested by apollon77

### 0.0.4
* (hash99) add devices configuration

### 0.0.3
* (hash99) adapter conform

### 0.0.1
* (hash99) initial release

## License
The MIT License (MIT)

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