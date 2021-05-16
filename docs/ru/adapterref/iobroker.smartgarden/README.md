---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.smartgarden/README.md
title: TR: ioBroker.smartgarden
hash: bbKCZ49g0LWG4EJYAGtuSSRM1C6FmTKx/qpQ3e+qTHY=
---
![TR: Logo](../../../en/adapterref/iobroker.smartgarden/admin/smartgarden.png)

![TR: Installed](http://iobroker.live/badges/smartgarden-installed.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.smartgarden.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.smartgarden.svg)
![TR: Build Status](https://travis-ci.org/jpgorganizer/ioBroker.smartgarden.svg?branch=master)
![TR: Stable](http://iobroker.live/badges/smartgarden-stable.svg)
![TR: NPM](https://nodei.co/npm/iobroker.smartgarden.png?downloads=true)

TR: # ioBroker.smartgarden
TR: **If you like it, please consider a donation:**

[![TR: paypal](https://www.paypalobjects.com/en_US/DK/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=8C7M7MH3KPYDC&source=url)

TR: ## ioBroker smartgarden adapter for GARDENA smart system
TR: An adapter for GARDENA smart system using official [TR: GARDENA smart system API](https://developer.husqvarnagroup.cloud/apis/GARDENA+smart+system+API#/general) and service.

TR: The adapter allows the development of an application (e.g. with VIS) that can be used in parallel with the official GARDENA app. The adapter and its additional features do not affect any of the basic functions of the GARDENA app and vice versa.

TR: The adapter is not a complete replacement for the GARDENA app, but an addition to integrate the GARDENA devices into a smart home with ioBroker.
The most important actions can be carried out with the adapter. It also offers the opportunity to implement your own ideas that are not possible with the GARDENA app.

TR: ## Supported devices
TR:   - GARDENA smart SILENO robotic lawnmowers
TR:   - GARDENA smart Irrigation Control
TR:   - GARDENA smart Pressure Pump
TR:   - GARDENA smart Water Control
TR:   - GARDENA smart Power Adapter
TR:   - GARDENA smart Sensor

TR: For more information about the devices see at [TR: GARDENA German website](https://www.gardena.com/de/produkte/smart/smartsystem/) and [TR: here in English](https://www.gardena.com/uk/products/smart/smart-system/).

TR: ## Requirements
TR: To use this adapter you need two things:

TR: 1. an GARDENA smart system account
TR: 1. an GARDENA application key

TR: To get both things please go to [TR: https://developer.husqvarnagroup.cloud/docs#/docs/getting-started/](https://developer.husqvarnagroup.cloud/docs#/docs/getting-started/).

![TR: getting_application_key](../../../en/adapterref/iobroker.smartgarden/getting_application_key.jpg)

TR: **Note:**

TR:   - If you already have a Husqvarna Automower® Connect or a

TR: GARDENA smart system account, you can Sign In with that account and continue with Step 2, Create application to get the application key.

	---

TR: ***And it's almost certain that you have an account.*** *Please use the same account as for the GARDENA app in which your GARDENA devices are registered. Otherwise you will not 	get access to your devices.*

	---

TR:   - Make sure that you've connected the application (from Step 2) to the API's
TR:     - Authentication API ***and***
TR: 	- GARDENA smart system API.

TR: And of course you need a running ioBroker installation and you should own at least one [TR: GARDENA smart device](#supported-devices).

TR: ## Table of Contents
TR:   * [ioBroker smartgarden adapter for GARDENA smart system](#iobroker-smartgarden-adapter-for-gardena-smart-system)
TR:   * [Supported devices](#supported-devices)
TR:   * [Requirements](#requirements)
TR:   * [Table of Contents](#table-of-contents)
TR:   * [Installation](#installation)
TR:   * [Setup adapter](#setup-adapter)
TR:   * [Getting support](#getting-support)
TR:   * [Data points of the adapter](#data-points-of-the-adapter)
TR:      * [General things to know about data points](#general-things-to-know-about-data-points)
TR:      * [For SERVICE_MOWER](#for-service_mower)
TR:      * [For SERVICE_VALVE_SET](#for-service_valve_set)
TR:      * [For SERVICE_VALVE](#for-service_valve)
TR:      * [For SERVICE_POWER_SOCKET](#for-service_power_socket)
TR:      * [For SERVICE_SENSOR](#for-service_sensor)
TR:      * [For SERVICE_COMMON](#for-service_common)
TR:   * [Rate Limits](#rate-limits)
TR:   * [Irrigation not allowed while mowing](#Irrigation-not-allowed-while-mowing)
TR:      * [What's the problem?](#whats-the-problem)
TR: 	 * [What is being done?](#what-is-being-done)
TR: 	 * [Basic behaviour -- WARNING](#basic-behaviour----warning)
TR:   * [Wishes for data points](#Wishes-for-data-points)
TR:   * [Note](#note)
TR:   * [Changelog](#changelog)
TR:      * [1.0.5](#105)
TR:      * [1.0.4](#104)
TR:      * [1.0.3](#103)
TR:      * [previous versions](#102)
TR:   * [Credits](#credits)
TR:   * [License](#license)

TR: ## Installation
TR: Adapter is available

TR: - at npm: Install with `npm install iobroker.smartgarden`
TR: - at GitHub under https://github.com/jpgorganizer/ioBroker.smartgarden.

TR: An description how to install from GitHub is available [TR: here](https://www.iobroker.net/docu/index-235.htm?page_id=5379&lang=de#3_Adapter_aus_eigener_URL_installieren) (German language).

TR: ## Setup adapter
TR: 1. Install the adapter
TR: 2. Create an instance of the adapter
TR: 3. Check and complete instance configuration

TR:    **If you change any value of those settings please restart your adapter.**

TR: 3.1 Edit username, password and application key in main instance configuration

| TR:       | Parameter | Description |
      | - | - |
| TR:       | user name | user name for GARDENA smart system |
| TR:       | password | corresponding password |
| TR:       | API Key |  API Key (application key), e.g. under [TR: Requirements](#requirements) |

TR: Please note that password and application key are encoded and stored within the adapter and become just decoded for authentication with the GARDENA application host.

TR: 3.2 Verify default values of miscellaneous settings and switch on/off options in instance configuration. For most users the default values will be ok.

| TR:       | Parameter | Description |
      | - | - |
| TR:       | pre-define states | pre-define all states of Gardena API regardless they are currently transmitted; switch on or off; if switched on then all states of the GARDENA smart system API are created regardless if they are currently transmitted by GARDENA service or not; default: off; *(new in v0.4.0)*|
| TR:       | forecast | use forecast for charging time and mower remaining time; switch forecast charging and mowing time of mower on/off; default: off; *(new in v0.5.0)*|
| TR:       | cycles | number of MOWER history cycles; you can use any number from 3 (minimum), but 10 (default) seems to be a good value; only relevant if the above *'forecast'* is on; *(new in v0.5.0)*|
| TR:       | irrigation check| use the check whether irrigation is allowed while mowing; switch on/off; default: off; *(new in v0.6.0)*|

TR: 3.3 Verify default values of systems settings and switch on/off options in instance configuration. **Most users will not have to change anything on this tab.**

| TR:       | Parameter | Description |
      | - | - |
| TR:       | Loglevel | Loglevel: 0 = no log, 1 = some logs, 2 = some more logs, 3 = all logs; default: 0|
| TR:       | beautify log | make state ids shorter in log; switch on/off; default: on; *(new in v1.0.5)*|
| TR: 	  | monitoring Rate Limits | use monitoring for the rate limits of Gardena smart system API; switch on/off; default: off; *(new in v1.0.2)*|
| TR:       | connection retry interval | interval for retry to connect to Gardena Webservice in case of an error (in seconds); default: 300, minimum: 60; *(new in v1.0.3)*|
| TR:       | ping frequence | Frequence for sending Ping's to Gardena Webservice (in seconds); default: 150, minimum: 1, maximum: 300|
| TR:       | auth factor  | Factor for validity of authentication token; default: 1.001 |
| TR:       | Auth-URL| Authentication host URL; default: [TR: https://api.authentication.husqvarnagroup.dev](https://api.authentication.husqvarnagroup.dev)|
| TR:       | Base-URL| Webservice Base-URL; default: [https://api.smart.gardena.dev](https://api.smart.gardena.dev)|

TR: ## Getting support
TR: To get help read this [TR: README](README.md) and the [FAQ](FAQ.md) carefully.
If you need further support please join the [TR: ioBroker forum thread](https://forum.iobroker.net/topic/31289/neuer-adapter-smartgarden-adapter-for-gardena-smart-system).

TR: ## Data points of the adapter
TR: The adapter is designed to monitor and control GARDENA smart system devices.
For this there will be one `LOCATION` and one or many `DEVICE`'s.
For each `DEVICE` there will be

TR:   - one `SERVICE_COMMON_<id>` and
TR:   - one or more `SERVICE_<servicelink_type>_<id>`.

TR: Where `<servicelink_type>` is a type description for the device, for example MOWER or VALVE and `<id>` is a (encoded) GARDENA device id used by the API.
See description for ServiceLink at [TR: https://developer.husqvarnagroup.cloud/apis/GARDENA+smart+system+API#/swagger](https://developer.husqvarnagroup.cloud/apis/GARDENA+smart+system+API#/swagger).

TR: Controlling/monitoring for each device is possible via the `SERVICE_<servicelink_type>` listed in the following table. The `SERVICE_COMMON` provides general information about the device.

| TR:   | device | SERVICE_<servicelink_type> |
  | - | - |
| TR:   | smart SILENO robotic lawnmower | SERVICE_MOWER and SERVICE_COMMON |
| TR:   | smart Irrigation Control | SERVICE_VALVE_SET, SERVICE_VALVE and SERVICE_COMMON |
| TR:   | smart Pressure Pump | SERVICE_VALVE and SERVICE_COMMON |
| TR:   | smart Water Control | SERVICE_VALVE and SERVICE_COMMON |
| TR:   | smart Power Adapter | SERVICE_POWER_SOCKET and SERVICE_COMMON |
| TR:   | smart Sensor | SERVICE_SENSOR and SERVICE_COMMON |

TR: If you need more information about the data points please have a look at [TR: https://developer.husqvarnagroup.cloud/apis/GARDENA+smart+system+API#/swagger](https://developer.husqvarnagroup.cloud/apis/GARDENA+smart+system+API#/swagger).
There you'll find a description for every data point; except for those which are marked as data points of the adapter and not of the GARDENA smart system API.

TR: The adapter creates its own data points for various features / options when the feature is selected. These data points are not automatically deleted when the feature is deselected. If you no longer need these data points, they can be deleted manually.

TR: ### General things to know about data points
TR: The adapter doesn't change any values transmitted by the GARDENA smart system API.
The only thing that is done (from version 1.0.0) is to check the type of *timestamps* and *numbers*.

| TR: | check for | description |
| - | - |
| TR: | timestamps | all timestamps are given in UTC; if a received timestamp is not a valid timestamp, `01 Jan 1970 00:00:00Z` (Unix time zero) is used instead. So if you see this date/time please report. |
| TR: | numbers | if a number is not a valid number, `-1` is used instead.  So if you see this number please report. |

TR: Requests to control a device will succeed as soon as the command was accepted by the smart Gateway. A successful execution of the command on the device itself can be observed by a respective state change.
*Example:* sending a command to start the VALVE service of a smart Water Control will result in the `activity_value` data point of the service to be changed after the device processed the command.

TR: **Notes:**

TR:   - Requests to control a device cannot be sent while the smartgarden adapter is not

TR:     connected to GARDENA smart system API.

TR:   - Please check that you set the value for a command with `ack=false`. See [Chapter Commands and Statuses in Guide for adapter developers](https://github.com/ioBroker/ioBroker.docs/blob/master/docs/en/dev/adapterdev.md#commands-and-statuses)

TR: ### For SERVICE_MOWER
TR: #### Controlling
TR: To control the device use data point

TR: - `activity_control_i`

TR:   *This data point is generated by the adapter and is not required due to the GARDENA smart system API.*

TR:   Change this data point to start the mower.

TR:   - To start for a defined time set the value to the planned duration in

TR:   seconds (please use multiples of 60)

TR:   - for automatic operation set string `START_DONT_OVERRIDE`
TR:   - to cancel the current operation and return to charging station use

TR:   string `PARK_UNTIL_NEXT_TASK`

TR:   - to cancel the current operation, return to charging station and ignore

TR:   schedule use string `PARK_UNTIL_FURTHER_NOTICE`

TR:   **Note:** The mower only starts with a fully charged battery.

TR: #### Monitoring
TR: All other data points are just for monitoring and information.

TR: Special data points:

TR: - `activity_mowing_i`

TR:   *This data point is generated by the adapter and is not required due to the GARDENA smart system API.*

TR:   This data point shows two different states for the mower:

TR:   - `true`: mowing or
TR:   - `false`: not mowing.

TR: This data point can be used for further actions where it is important to know whether the mower is safely on the lawn or not.

TR: Depending on the value of data point `activity_value` this data point is set.
Please see following table for details.

| TR:   | `activity_value` | `activity_mowing_i` |
| TR:   |`OK_CHARGING` The mower has to be mowing but insufficient charge level keeps it in the charging station. | false |
| TR:   |`PARKED_TIMER` The mower is parked according to timer, will start again at configured time. | false |
| TR:   |`PARKED_PARK_SELECTED` The mower is parked until further notice. | false |
| TR:   |`PARKED_AUTOTIMER` The mower skips mowing because of insufficient grass height. | false |
| TR:   |`PAUSED` The mower is in a waiting state with hatch closed. | false |
| TR:   |`OK_CUTTING` The mower is cutting in AUTO mode (schedule). | true |
| TR:   |`OK_CUTTING_TIMER_OVERRIDDEN` The mower is cutting outside schedule. | true |
| TR:   |`OK_SEARCHING` The mower is searching for the charging station. | true |
| TR:   |`OK_LEAVING` The mower is leaving charging station. | true |
| TR:   |`NONE` No activity is happening, perhaps due to an error. | true |
| TR:   |`NONE` No activity is happening, perhaps due to an error. | true |
| TR:   |all other values | true |

TR: - `batteryState_chargingTime_remain_i` *(under SERVICE_COMMON...)* and <br/>

TR: `activity_mowingTime_remain_i` *(under SERVICE_MOWER...)*

TR:   *Both data points are generated by the adapter and are not required due to the GARDENA smart system API.*

TR: Those data points show an forecast for remaining charging and mowing time in seconds of the mower.
They are only created when the function is selected in the instance configuration.

TR: To forecast a value an history of the last few charging and mowing cycles is saved in two states `info.saveMowingHistory` and `info.saveChargingHistory`.

TR: This feature can be switched on/off in adapter instance configuration along with the number of saved charging and mowing cycles in history.

TR: To put this function into operation, **please make sure that at least one cycle of mowing and charging runs without errors (e.g. not interrupted manually or sensor control).** It is better if at least three runs are completed without errors.
This function tries to recognize the normal case and initially assumes that the next process is a normal case. If this is faulty, then this faulty run is regarded as a normal case and the runs that then pass through normally as a fault case. If there is an error during the run, please stop the adapter, delete the two data points and start again.

TR: For more information about general forecasting mechanisms see [TR: FORECAST.md](FORECAST.md).

TR:   **Notes:**

TR:     1. Forecast values are only available if at least one complete

TR: 	charging and mowing cycle is saved in history.

TR:     2. The history is saved under `info` so that if the `LOCATION` needs

TR: 	to be deleted, e.g. in the event of a future update, it is not lost.

TR:     3. If you disconnect your mower from the GARDENA smart system and

TR: reconnect it again the history is lost, because your mower get's a new id within the GARDENA smart system. This means that the adapter cannot recognize the mower as the previous mower - may be it's a second one.
In this case it is recommended to delete these two data points and to restart the adapter so that the previous (now old) history sets are not constantly read and written. The adapter then begins to build a new history.

TR: 	4. This function should work for more than one mower, but it is

TR: not tested *(I can't do that, because I've only one mower)*.
If you have more than one mower please test and report errors and of course report if it works as intended. Thanks in advance for that.

TR: - `lastErrorCode_value`

TR: Please pay special attention to data point `lastErrorCode_value`.
A description of possible values can be found at https://developer.husqvarnagroup.cloud/apis/GARDENA+smart+system+API#/swagger, see "MowerService - lastErrorCode"

TR: ### For SERVICE_VALVE_SET
TR: #### Controlling
TR: To control the device use data point

TR: - `stop_all_valves_i`

TR:   *This data point is generated by the adapter and is not required due to the GARDENA smart system API.*

TR:   Change this data point to stop all valves.

TR:   - To stop all valves immediately use string `STOP_UNTIL_NEXT_TASK`

TR: **Note:** Do not display the value of this data point in your application, as the value is mostly undefined. Furthermore, this data point cannot serve as a trigger for your own actions, because it is just set to value *null* after the command was triggered.

TR: #### Monitoring
TR: All other data points are just for monitoring and information.

TR: ### For SERVICE_VALVE
TR: #### Controlling
TR: To control the device use data point

TR: - `duration_value`

TR:   Change this data point to start the valve.

TR:   - To start for a defined time  set the value to the value in seconds

TR:   (please use multiples of 60).

TR: **Note:** There are some limitations for the allowed values.
Please report if you see other limitations.

| TR:     | device | limit |
    | - | - |
| TR:     |GARDENA smart Irrigation Control| 3540 seconds (59 minutes) |
| TR:     |GARDENA smart Pump | 36000 (10 hours) |
| TR:     |GARDENA smart Water Control | 36000 (10 hours) |

TR:   - To cancel the current watering and continue with the schedule use string

TR:   `STOP_UNTIL_NEXT_TASK`

TR:   - To skip automatic operation until specified time, the currently active

TR: operation might or might not be cancelled (depends on device model) use string `PAUSE_<number_of_seconds>`, e.g. `PAUSE_86400` to pause for 24 hours (please use multiples of 60)

TR:   - To restore automatic operation if it was paused use string `UNPAUSE`

TR: - `irrigationWhileMowing_allowed_i` and `irrigationWhileMowing_mowerDefinition_i`

TR:   *This data points are generated by the adapter and are not required due to the GARDENA smart system API.*

TR: Those data points give control over the feature *Irrigation not allowed while mowing*.
They are only created when the function is selected in the instance configuration.
For description of this feature see chapter [TR: Irrigation not allowed while mowing](#Irrigation-not-allowed-while-mowing).

TR: #### Monitoring
TR: All other data points are just for monitoring and information.

TR: Special data point:

TR: - `duration_leftover_i`

TR:   *This data point is generated by the adapter and is not required due to the GARDENA smart system API.*

TR: The value describes the number of minutes till the valve is closed and watering stops.

TR:     - An integer, one (`1`) or more.
TR:     - `null` if undefined

TR: ### For SERVICE_POWER_SOCKET
TR: #### Controlling
TR: To control the device use data point

TR: - `duration_value`

TR:   Change this data point to start the power socket.

TR:   - To start for a defined time  set the value to the value in seconds

TR:   (please use multiples of 60)

TR:   - To switch on the device forever please use the string `START_OVERRIDE`.
TR:   - To stop the device use `STOP_UNTIL_NEXT_TASK`.
TR:   - To skip automatic operation until specified time. The currently active operation

TR: will NOT be cancelled. Use string `PAUSE_<number_of_seconds>`, e.g. `PAUSE_86400` to pause for 24 hours (please use multiples of 60)

TR:   - To restore automatic operation if it was paused use string `UNPAUSE`

TR: #### Monitoring
TR: All other data points are just for monitoring and information.

TR: Special data point:

TR: - `duration_leftover_i`

TR:   *This data point is generated by the adapter and is not required due to the GARDENA smart system API.*

TR:   The value describes the number of minutes till the power socket is shut off.

TR:     - An integer, one (`1`) or more.
TR:     - `null` if undefined

TR: ### For SERVICE_SENSOR
TR: #### Controlling
TR: No control functions available.

TR: #### Monitoring
TR: All data points are just for monitoring and information.

TR: ### For SERVICE_COMMON
TR: The `SERVICE_COMMON` provides general information about the device.
Description is integrated into description of other SERVICE_... where necessary.

TR: ## Rate Limits
TR: There are some limits you shoud be aware of.
Please see chapter *Rate Limits* in [TR: *README*](https://developer.husqvarnagroup.cloud/apis/GARDENA+smart+system+API#/readme) of GARDENA smart system API description.

TR: To help you to see if you hit those rate limits you can switch on monitoring in instance configuration with parameter *monitoring Rate Limits*.

TR: If you've enabled monitoring state `info.RateLimitCounter` gets actualized with every request.
This state saves a data structure with the number of requests per month, day, hour and for the last 30 and 31 days.

TR: The structure is in [TR: JSON](https://en.wikipedia.org/wiki/JSON) and looks like

```
{
  "2020": {                          <<< year
    "2020-08": {                     <<< month
      "count": 21,                   <<< number of requests for month
      "2020-08-27": {                <<< day
        "11": {                      <<< hour
          "count": 3                 <<< number of requests for hour
        },
        "12": {                      <<< hour
          "count": 13                <<< number of requests for hour
        },
        "count": 16                  <<< number of requests for day
      },
      "2020-08-28": {                <<< day
        "14": {                      <<< hour
          "count": 5                 <<< number of requests for hour
        },
        "count": 5                   <<< number of requests for day
      }
    }
  },
     ...
  "last30days": {
    "count": 2021                    <<< number of requests in last 30 days
  },
  "last31days": {
    "count": 2098                    <<< number of requests in last 31 days
  }
}
```

TR: **Note:**

TR:   - That hour is hour of time in UTC
TR:   - That the actual number of requests may be higher. Especially as

TR:   long as the respective period is not fully covered by the monitoring.

TR:   - That this structure becomes very large and is never deleted by the

TR: adapter. So please delete it manually from time to time or switch off monitoring - at least if you don't have any issues with the rate limits.

TR: ## Irrigation not allowed while mowing
TR: ### What's the problem?
TR: If you have both a mower and an irrigation system with pop-up sprinklers, there is a risk that your mower will run into a pop-up sprinkler while the irrigation is running and damage it or cause damage itself.

TR: To prevent this, the irrigation system or better individual valves should be switched off when the mower is mowing.

TR: ### What is being done?
TR: With this function it is possible to stop irrigation when the mower is on the lawn. This can be defined separately for each valve.

TR: One or more mowers can be defined for each valve, for which the valve is not allowed to be open while the mower is mowing.
Basically, the mower has priority over irrigation, i.e. if the conflict arises that the mower is mowing and a valve is open, the valve is closed and a corresponding warning is set.

TR: Additionally it is possible to define that a valve should never open regardless of a mower. E.g. can be used if a valve or the pipe behind it is damaged.

TR: The whole check can be switched on or off in instance configuration with parameter *irrigation check*.

TR: There are three data points available for each `SERVICE_VALVE`.
They are used for configuration and for reporting warnings.

| TR:   | data point | writeable | Description of data points |
  | - | - | - |
| TR:   |`irrigationWhileMowing_allowed_i` | yes |set to `false` if it should be checked if irrigation is allowed while the mower is mowing on the lawn, `true` otherwise |
| TR:   |`irrigationWhileMowing_warningCode_i`| no | warning code is set if valve opens. Possible warning codes see next table. If more than one warning is set, codes are concatenated with `+` (e.g. `STOPPED+UNKNOWN_MOWER`).|
| TR:   |`irrigationWhileMowing_warningCode_i`| no | warning code is set if valve opens. Possible warning codes see next table. If more than one warning is set, codes are concatenated with `+` (e.g. `STOPPED+UNKNOWN_MOWER`).|

TR: * ***mower id format***

TR:   `smartgarden.0.LOCATION_xxxxxxxx-xxxxxx-xxxxxx-xxxxxx-xxxxxxxxxxxxxx.DEVICE_xxxxxxxx-xxxxxx-xxxxxx-xxxxxx-xxxxxxxxxxxxxx.SERVICE_MOWER_xxxxxxxx-xxxxxx-xxxxxx-xxxxxxxxxxxxxxxxxxxxx`

TR: You can copy this mower id from the objects tab of ioBroker, see red arrow in the following picture.

  ![TR: mower id](../../../en/adapterref/iobroker.smartgarden/mowerid.jpg)

TR: * ***warning codes*** </br>

| TR:   | warning code| description|
  | - | - |
| TR:   |  `NO_WARNING` |no warning, valve opened |
| TR:   |  `STOPPED` |valve automatically closed because mower is mowing |
| TR:   |  `FORBIDDEN` |valve closed because special code `IRRIGATION_FORBIDDEN` is set in data point `irrigationWhileMowing_mowerDefinition_i`|
| TR:   |  `FORBIDDEN` |valve closed because special code `IRRIGATION_FORBIDDEN` is set in data point `irrigationWhileMowing_mowerDefinition_i`|

TR: This function is runnig every time when

TR: - a valve becomes opened or
TR: - a mower starts mowing

TR: It doesn't run when you change the values in the data points listed above.
That means: if there is a conflict situation and you change `irrigationWhileMowing_allowed_i` from `true` to `false`, the conflict is not recognized and the conflict will continue. The same behaviour applies to a change of `irrigationWhileMowing_mowerDefinition_i`.

TR: ### Basic behaviour -- WARNING
TR: This feature cannot prevent a valve from opening while the mower is mowing. E.g. this can be done manually through the GARDENA app or automatically through a schedule.

TR: This function can only close the valve as quickly as possible in the event of a conflict. And a conflict may not be recognized either.
So it can happen that water is let through.
**E.g. it cannot be prevented that the pop-up sprinklers extend and that the mower hits the pop-up sprinklers**, but the likelihood that this will happen has been minimized.
**So it is up to your application to make sure that this conflict will never happen.**

TR: ## Wishes for data points
TR: This adapter reports **every value** as a data point that is supplied via the GARDENA smart system API. If someone wants more values, please contact GARDENA and inform them that this value will also be included in the API. To do this, please go to ***Contact us & Leave feedback*** in the footer on the [TR: GARDENA Developer Portal](https://developer.husqvarnagroup.cloud).

TR: ## Note
TR: This is a private project. I am not in any association with GARDENA or Husqvarna.

TR: ## Credits
TR: Many thanks to GARDENA/Husqvarna for providing this [TR: public API](https://developer.husqvarnagroup.cloud/apis/GARDENA+smart+system+API#/general) and special thanks to your support team for providing very good and very fast support.

TR: smartgarden logo: http://www.freepik.com Designed by Freepik

## Changelog
### 1.0.5
* (jpgorganizer) 2021-May-13
  - necessary adjustments due to js-controller v3.3; e.g. [Issue 29](https://github.com/jpgorganizer/ioBroker.smartgarden/issues/29)
    - nearly all data points get deleted and created again with intended role/unit
    - data types for following data points changed from `string` to `number`: 
	  - for all devices: `rfLinkLevel_value` 
      - for mower: `batteryLevel_value`, `operatingHours_value` 
      - for sensor: `batteryLevel_value`, `soilHumidity_value`, `soilTemperature_value`, `lightIntensity_value`, `ambientTemperature_value`
  - compatibility test with node.js v14 and node.js v16 and added to Travis CI test; 
    compatibility test with the upcoming Admin 5 React UI;
    e.g. [Issue 30](https://github.com/jpgorganizer/ioBroker.smartgarden/issues/30)
  - new parameter *beautify log* in instance configuration; makes state ids a little bit shorter in log if switched on

### 1.0.4
* (jpgorganizer) 2021-Feb-22
  - necessary adjustments due to js-controller v3.2
  - option `useTestVariable` in adapter/instance configuration removed

### 1.0.3
* (jpgorganizer) 2021-Jan-26
  - improved error handling
  - new parameter `connection retry interval`
  - axios vulnerability solved, using version `>=0.21.1`
  
### 1.0.2
* (jpgorganizer) 2020-Aug-30
  - monitoring rate limits, see chapter [Rate Limits](#rate-limits) and discussion at 
  [Issue 18](https://github.com/jpgorganizer/ioBroker.smartgarden/issues/18)


### 1.0.1
* (jpgorganizer) 2020-Aug-17
  - better reconnection to GARDENA smart system server in case of your internet connection was broken
  - textual changes in io-package.json
  - improved README and FAQ
  
### 1.0.0
* (jpgorganizer) 2020-Jun-13
  - code rework, no functional change expected
  - support `PAUSE` for SERVICE_VALVE, SERVICE_POWER_SOCKET. e.g. 
	[Issue 14](https://github.com/jpgorganizer/ioBroker.smartgarden/issues/14)
  - internal representation for all timestamps changed from format like 
    `2020-05-26T05:03:47.613+0000` to `2020-05-26T05:03:47.613Z` to 
    support Safari browser e.g. 
	[Issue 12](https://github.com/jpgorganizer/ioBroker.smartgarden/issues/12).
  - support forecast values for mower id's in format with suffix, 
    e.g. `d8a1faef-2ee3-421d-a3f8-f8ed577c2ad3:suffix`, e.g. 
	[Issue 12](https://github.com/jpgorganizer/ioBroker.smartgarden/issues/12)
  - making the adapter more fault tolerant at startup, e.g. trimming 
    whitespaces from username, etc.
  - README: new chapter *Getting support*, 
  - README: chapter *Known Errors* deleted, should be resolved by GARDENA 
  - README: links to GARDENA/Husqvarna developer portal adjusted to the new address

### 0.6.0
* (jpgorganizer) 2020-May-03
  - new feature *Irrigation not allowed while mowing*, 
    for detailed description see 
	[Irrigation not allowed while mowing](#Irrigation-not-allowed-while-mowing); 
    e.g. 
	[Issue 5](https://github.com/jpgorganizer/ioBroker.smartgarden/issues/5)
  - rework instance config dialog
  - improvement of documentation

### 0.5.1
* (jpgorganizer) 2020-Apr-26
  - some corrections (sensor, typo)
  - integration of travis-ci
  
### 0.5.0
* (jpgorganizer)  2020-Apr-25
  - MOWER: forecast for remaining charging time and remaining mowing time 
  integrated, e.g. [Issue 1](https://github.com/jpgorganizer/ioBroker.smartgarden/issues/1)
  - **IMPORTANT CHANGE** for existing users: the id for LOCATION, all 
    DEVICE's and all SERVICE's has changed due to support of History adapter. 
	(History adapter cannot handle id's with `%` (percent) character 
	within id's, although the `%` is not forbidden in id's in ioBroker), e.g. 
	[Issue 8](https://github.com/jpgorganizer/ioBroker.smartgarden/issues/8). 
  
    So you **must delete all states** of the adapter instance to 
    install this release and please check your application carefully for 
    necessary adjustments regarding the change of the id names.

  - devices *Water Control* and *Smart Pump* tested (many thanks to user 
    gammler2003 and xengosam at 
    [ioBroker Forum](https://forum.iobroker.net/topic/31289/neuer-adapter-smartgarden-adapter-for-gardena-smart-system/) for testing)
  - some code rework and improvement of documentation
  - dependency corrected, important for js-controller v3, e.g. 
    [Issue 7](https://github.com/jpgorganizer/ioBroker.smartgarden/issues/7)
  - adapter now available at npm
  
### 0.4.2
* (jpgorganizer) 2020-Apr-01
  - error *missing SENSOR data* fixed (many thanks to user dslraser and 
  muckel at 
  [ioBroker Forum](https://forum.iobroker.net/topic/31289/neuer-adapter-smartgarden-adapter-for-gardena-smart-system/) for testing)

### 0.4.1
* (jpgorganizer) 2020-Mar-31
  - Dependency get's resolved now
  
### 0.4.0 
* (jpgorganizer) 2020-Mar-31
  - **NOTE:** with this version an additional dependency is necessary at runtime. 
  If it does not get installed together with the installation of this adapter, 
  please install seperately with 
  `npm install https://github.com/jpgorganizer/ioBroker.utils` or 
  `npm i @jpgorganizer/utils`
  - **NOTE:** you **must delete all states** of the adapter instance to 
  install this release and please check your application carefully for 
  necessary adjustments regarding type/role changes (see below) 
  - data types of (nearly) all data points adjusted for compliance with 
  ioBroker guidance: 
    * states now have special ioBroker type and role instead of former 
	`string`/`text` where applicable, e.g. `number`/`value.battery` for 
	`batteryLevel_value`, see 
	[Issue 3](https://github.com/jpgorganizer/ioBroker.smartgarden/issues/3)
  - data point `activity_value_i` replaced by `activity_mowing_i` with 
    type/role `boolean`/`indicator.working`: `true` means *mowing*, `false` 
  means *not mowing*
  - possibility to pre-define states integrated, see new switch 
  `PreDefine States` in adapter/instance configuration, see 
  [Issue 2](https://github.com/jpgorganizer/ioBroker.smartgarden/issues/2)
  - states are readonly now; except states for commands, see 
  [Issue 4](https://github.com/jpgorganizer/ioBroker.smartgarden/issues/4)
  - input field for `useTestVariable` in adapter/instance configuration 
  switched to a *checkbox* (former: *text*); please check your settings
  - error in command  `stop_all_valves_i` in VALVE_SET fixed
  
### 0.3.0
* (jpgorganizer) 2020-Mar-25
  - create all states read/write 
  - error TypeError: Cannot read property 'val' of null with useTestVariable 
  fixed



### 0.2.0
* (jpgorganizer) 2020-Mar-24
  - **IMPORTANT** : data point for MOWER control (command) changed from  
  `duration_value` to `activity_control_i`
  - rework leftovertimer 
  - improved error handling
  - improved logging (see  loglevel in adapter configurations)

### 0.0.1 
* (jpgorganizer) 2020-Mar-01
  - initial release

## License

Copyright (c) 2020, 2021 jpgorganizer, https://github.com/jpgorganizer 

smartgarden by jpgorganizer is licensed under a 
Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License 
[(CC-BY-NC-SA-4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/) 
Based on a work at https://github.com/jpgorganizer/ioBroker.smartgarden. 
 

<!--- SVN: $Rev: 2507 $ $Date: 2021-05-13 18:07:01 +0200 (Do, 13 Mai 2021) $ --->