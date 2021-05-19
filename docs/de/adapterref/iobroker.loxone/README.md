---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.loxone/README.md
title: TR: ioBroker.loxone
hash: 8fE4m8tPLb1oVSWM01sOObUj31hSSnV2f20hSlYJKg8=
---
![TR: Logo](../../../en/adapterref/iobroker.loxone/admin/loxone.png)

![TR: NPM version](http://img.shields.io/npm/v/iobroker.loxone.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.loxone.svg)
![TR: Number of Installations (latest)](http://iobroker.live/badges/loxone-installed.svg)
![TR: Number of Installations (stable)](http://iobroker.live/badges/loxone-stable.svg)
![TR: Dependency Status](https://img.shields.io/david/UncleSamSwiss/iobroker.loxone.svg)
![TR: NPM](https://nodei.co/npm/iobroker.loxone.png?downloads=true)

TR: # ioBroker.loxone
[![TR: Translation status](https://weblate.iobroker.net/widgets/adapters/-/loxone/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

TR: **Tests:** ![TR: Test and Release](https://github.com/UncleSamSwiss/ioBroker.loxone/workflows/Test%20and%20Release/badge.svg)

TR: ## loxone adapter for ioBroker
TR: **_This adapter requires at least nodejs 10.x!_**

TR: Fetches all information available in Loxone Miniserver (and Loxone Miniserver Go) and provides changes in realtime.

TR: **This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [TR: Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

TR: ## Install
TR: Install this adapter via ioBroker Admin:

TR: 1. Open instance config dialog
TR: 2. Enter the IP address or host name and HTTP port (80 by default) of your Loxone Miniserver
TR: 3. Create a new user in the Loxone Miniserver (using the Loxone Config application) to which you only give read and write rights to all required variables.
TR: 4. Enter this user's name and its password in the config dialog
TR: 5. Save the configuration
TR: 6. Start the adapter

TR: ## Configuration
TR: ### Miniserver Hostname / IP
TR: This is the IP address or host name of your Loxone Miniserver or Miniserver Go.

TR: ### Miniserver Port
TR: This is the HTTP port of your Loxone Miniserver.

TR: By default the Miniserver is configured to listen on port 80, but you might have changed it.

TR: ### Miniserver Username
TR: Provide a valid username to access the Loxone Miniserver.

TR: It is strongly suggested to use a user different from "admin" for security reasons.

TR: The user only needs read access to the variables you want to use from ioBroker.

TR: ### Miniserver Password
TR: Provide the password for the given username (see above).

TR: ### Synchronize Names
TR: This will update names in ioBroker whenever they change in the Loxone configuration.
If this is disabled, names will only be synchronized the first time a control is detected.

TR: ### Synchronize Rooms
TR: This will populate the enum.rooms enumeration with all rooms provided by the Loxone Miniserver and will link all controls.

TR: ### Synchronize Functions
TR: This will populate the enum.functions enumeration with all categories provided by the Loxone Miniserver and will link all controls.

TR: ### Weather Server
TR: Choose what weather data you wish to synchronize:

TR: -   "Don't synchronize weather data" will not synchronize anything related to the Weather Server
TR: -   "Synchronize current weather only" will synchronize the data under "Actual"
TR: -   "Synchronize 24 hours of weather forcast" will synchronize the current weather and 24 hours of weather forcast
TR: -   "Synchronize entire weather forcast" will synchronize the current weather and the entire weather forcast (96 hours)

TR: ## States
TR: The adapter automatically connects to the configured Loxone Miniserver and creates states for each control state it finds.

TR: The IDs of the states are formatted like this: `loxone.<instance>.<control>.<state>`

TR: -   `<instance>` is the ioBroker adapter instance index (usually "0")
TR: -   `<control>` is the UUID of the control
TR: -   `<state>` is the state within the control (see [Supported Control Types](#supported-control-types) for more information).

TR: The name provided when configuring a control in Loxone Config will only be used as its display name in ioBroker.
This is because a user may choose the same name for multiple controls.

TR: For more information about controls and their states, please also have a look at the Loxone API (especially the Structure File): https://www.loxone.com/enen/kb/api/

TR: ## Control Visibility
TR: By default Loxone Miniserver hides many controls (and thus their states) from the Web interface.

TR: That means, they are also hidden from this ioBroker adapter.

TR: ### Use in User Interface
TR: To ensure, all your states are properly reported to ioBroker, please verify that they have "Use" in the "User Interface" section checked:

![TR: Use in User Interface settings](../../../en/adapterref/iobroker.loxone/doc/loxone-config-use-in-visualization.png)

TR: ### Display diagnostic inputs
TR: To see diagnostic inputs (e.g. battery status of Air devices), please verify that the device has "Display diagnostic inputs" checked:

![TR: Display diagnostic inputs settings](../../../en/adapterref/iobroker.loxone/doc/loxone-config-display-diagnostics.png)

TR: ## Global States
TR: The following global states are currently provided by this adapter:

TR: -   `operatingMode`: the current operating mode number of the Loxone Miniserver
TR: -   `operatingMode-text`: the current operating mode of the Loxone Miniserver as text
TR: -   `sunrise`: the number of minutes after midnight when the sun rises today
TR: -   `sunset`: the number of minutes after midnight when the sun goes down today
TR: -   `notifications`: the number of notifications
TR: -   `modifications`: the number of modifications
TR: -   all other global states are simply reported as texts

TR: ## Supported Control Types
TR: The following control types are currently supported by this adapter.

TR: Behind the name of the state, you can see the type of the state:

TR: -   `(rw)`: readable and writable: this state can be changed from ioBroker
TR: -   `(ro)`: read-only: this state can't be changed from ioBroker
TR: -   `(wo)`: write-only: this state's value isn't reported by this adapter, but it can be changed, triggering some action on the Loxone Miniserver

TR: ### AalSmartAlarm
TR: Provided by AAL Smart Alarm control.

TR: -   `alarmLevel` (ro) the ID of the current alarm level
TR:     -   0 = No alarm
TR:     -   1 = Immediate alarm
TR:     -   2 = Delayed alarm
TR: -   `alarmCause` (ro) A string representing the last cause for an alarm
TR: -   `isLocked` (ro) Reset active, inputs will be ignored and therefore no alarms will be executed
TR: -   `isLeaveActive` (ro) Leave input is set, no alarms will be executed
TR: -   `disableEndTime` (ro) End time for the control to be disabled
TR: -   `confirm` (wo) Confirm pending alarm
TR: -   `disable` (wo) Disable control for a certain period of time, no alarms will be executed. Setting it to 0 will reenable the Smart Alarm
TR: -   `startDrill` (wo) Execute test alarm

TR: ### AalEmergency
TR: Provided by AAL Smart Emergency Button control.

TR: -   `status` (ro) the ID of the current status
TR:     -   0 = running, normal operation, waiting for emergency button press
TR:     -   1 = alarm triggered
TR:     -   2 = reset input in config asserted, control is shut down
TR:     -   3 = app has temporarily disabled control
TR: -   `disableEndTime` (ro) End time for the control to be disabled
TR: -   `resetActive` (ro) text state with the active reset input (if control is in reset)
TR: -   `trigger` (wo) trigger an alarm from the app
TR: -   `quit` (wo) quit an active alarm
TR: -   `disable` (wo) disable the control for the given time in seconds. Set to 0 to start control again if it is disabled

TR: ### Alarm
TR: Provided by burgler alarm control.

TR: -   `armed` (rw) boolean state (true / false) of the alarm; writing `true` to this value will immediately turn the alarm on (without the predefined delay)
TR: -   `nextLevel` (ro) the ID of the next alarm level
TR:     -   1 = Silent
TR:     -   2 = Acustic
TR:     -   3 = Optical
TR:     -   4 = Internal
TR:     -   5 = External
TR:     -   6 = Remote
TR: -   `nextLevelDelay` (ro) the delay of the next level in seconds
TR: -   `nextLevelDelayTotal` (ro) the total delay of the next level in seconds
TR: -   `level` (ro) the ID of the current alarm level
TR:     -   1 = Silent
TR:     -   2 = Acustic
TR:     -   3 = Optical
TR:     -   4 = Internal
TR:     -   5 = External
TR:     -   6 = Remote
TR: -   `startTime` (ro) the timestamp when alarm started
TR: -   `armedDelay` (ro) the delay of the alarm control being armed
TR: -   `armedDelayTotal` (ro) the total delay of the alarm control being armed
TR: -   `sensors` (ro) the list of sensors
TR: -   `disabledMove` (rw) the movement is disabled (true) or not (false)
TR: -   `delayedOn` (wo) writing any value to this state arms the alarm with the configured delay
TR: -   `quit` (wo) writing any value to this state acknowledges the alarm

TR: ### Central Alarm
TR: Provided by central burgler alarm control.

TR: -   `armed` (rw) boolean state (true / false) of the alarm; writing `true` to this value will immediately turn the alarm on (without the predefined delay)
TR: -   `delayedOn` (wo) writing any value to this state arms the alarm with the configured delay
TR: -   `quit` (wo) writing any value to this state acknowledges the alarm

TR: ### AlarmClock
TR: Provided by alarm clock control.

TR: -   `isEnabled` (rw) boolean state (true / false) of the alarm clock
TR: -   `isAlarmActive` (ro) boolean (true / false) whether the alarm is currently ringing
TR: -   `confirmationNeeded` (ro) boolean (true / false) whether the user needs to confirm the alarm
TR: -   `ringingTime` (ro) countdown in seconds how long the alarm clock will be ringing until it’s going to snooze again
TR: -   `ringDuration` (rw) duration in seconds the alarm clock is ringing
TR: -   `prepareDuration` (rw) preparation time in seconds
TR: -   `snoozeTime` (ro) seconds until snoozing ends
TR: -   `snoozeDuration` (rw) duration in seconds of snoozing
TR: -   `snooze` (wo) writing any value to this state snoozes the current alarm
TR: -   `dismiss` (wo) writing any value to this state dismisses the current alarm

TR: ### AudioZone
TR: Provided by Music Server Zone.

TR: -   `serverState` (ro) state of the music server:
TR:     -   -3 = unknown/invalid zone
TR:     -   -2 = not reachable
TR:     -   -1 = unknown
TR:     -   0 = offline
TR:     -   1 = initializing (booting, trying to reach it)
TR:     -   2 = online
TR: -   `playState` (rw) the playback state:
TR:     -   -1 = unknown (this value can't be set)
TR:     -   0 = stopped (setting this value will pause playback)
TR:     -   1 = paused (setting this value will pause playback)
TR:     -   2 = playing (setting this value will start/resume playback)
TR: -   `clientState` (ro) state of the client:
TR:     -   0 = offline
TR:     -   1 = initializing (booting, trying to reach it)
TR:     -   2 = online
TR: -   `power` (rw) whether or not the client power is active
TR: -   `volume` (rw) current volume
TR: -   `maxVolume` (ro) zones can be assigned a maximum volume
TR: -   `shuffle` (rw) whether or not playlist shuffle is enabled
TR: -   `sourceList` (ro) list containing all zone-favorites
TR: -   `repeat` (rw) repeat mode:
TR:     -   -1 = unknown
TR:     -   0 = off
TR:     -   1 = repeat all
TR:     -   2 = -not used-
TR:     -   3 = repeat current item
TR: -   `songName` (ro) song name
TR: -   `duration` (ro) how long the whole track is, -1 if not known (stream)
TR: -   `progress` (rw) current position in the track
TR: -   `album` (ro) album name
TR: -   `artist` (ro) artist name
TR: -   `station` (ro) station name
TR: -   `genre` (ro) genre name
TR: -   `cover` (ro) song/album cover image URL
TR: -   `source` (rw) current selected source identifier (see `sourceList` above)
TR: -   `prev` (wo) writing any value to this state moves to the previous track
TR: -   `next` (wo) writing any value to this state moves to the next track

TR: ### Central Audio
TR: Provided by central Music Server.

TR: -   `control` (wo) sets the play state of all players (`true` = play, `false` = pause)

TR: ### Colorpicker
TR: This device only appears inside a LightController.

TR: -   `red` (rw) red value of the color picker
TR: -   `green` (rw) green value of the color picker
TR: -   `blue` (rw) blue value of the color picker

TR: Setting one or more of the above states from ioBroker will only send a command to the Miniserver after about 100 ms.
This is to prevent the color from changing multiple times for a single user input.

TR: ### Colorpicker V2
TR: This device only appears inside a Light Controller V2 in Loxone software version 9 and above.

TR: -   `red` (rw) red value of the color picker
TR: -   `green` (rw) green value of the color picker
TR: -   `blue` (rw) blue value of the color picker

TR: Setting one or more of the above states from ioBroker will only send a command to the Miniserver after about 100 ms.
This is to prevent the color from changing multiple times for a single user input.

TR: ### Dimmer
TR: Provided by dimmers.

TR: -   `position` (rw) current position for the dimmer
TR: -   `min` (ro) current minimum value
TR: -   `max` (ro) current maximum value
TR: -   `step` (ro) current step value
TR: -   `on` (wo) writing any value to this state sets the dimmer to the last known position
TR: -   `off` (wo) writing any value to this state disables the dimmer, sets position to 0 but remembers the last position

TR: ### EIBDimmer
TR: Provided by EIB/KNX dimmers.

TR: -   `position` (rw) current position for the dimmer
TR: -   `on` (wo) writing any value to this state sets the dimmer to the last known position
TR: -   `off` (wo) writing any value to this state disables the dimmer, sets position to 0 but remembers the last position

TR: ### Gate
TR: Provided by gate controls.

TR: -   `position` (ro) the position from 1 = up to 0 = down
TR: -   `active` (rw) current direction of the gate movement
TR:     -   -1 = close
TR:     -   0 = not moving
TR:     -   1 = open
TR: -   `preventOpen` (ro) whether preventing opening of door
TR: -   `preventClose` (ro) whether preventing closing of door

TR: ### Central Gate
TR: Provided by central gate control.

TR: -   `open` (wo) opens all gates
TR: -   `close` (wo) closes all gates
TR: -   `stop` (wo) stops all gate motors

TR: ### InfoOnlyDigital
TR: Provided by virtual states as well as the Loxone Touch switch.

TR: -   `active` (ro) boolean state (true / false) of the control
TR: -   `active-text` (ro) if configured, the text equivalent of the state
TR: -   `active-image` (ro) if configured, the image equivalent of the state
TR: -   `active-color` (ro) if configured, the color equivalent of the state

![TR: InfoOnlyDigital settings](../../../en/adapterref/iobroker.loxone/doc/loxone-config-info-only-digital.png)

TR: ### InfoOnlyAnalog
TR: Provided by virtual states as well as the Loxone Touch switch.

TR: -   `value` (ro) the state value (number) of the control
TR: -   `value-formatted` (ro) if configured, the formatted value of the state (using the "Unit" format from Loxone Config)

TR: ### Intercom
TR: Provided by door controllers.

TR: -   `bell` (ro) whether the bell is ringing
TR: -   `lastBellEvents` (ro) array containing the timestamps for each bell-activity that wasn't answered
TR: -   `version` (ro) Loxone Intercoms only - text containing the currently installed firmware

TR:     versions

TR: -   `answer` (wo) writing any value to this state will deactivate the bell

TR: This type of channel might contain other devices. See the respective chapter for more information.

TR: ### Intelligent Room Controller V2
TR: Provided by the intelligent room controller V2 since Miniserver 10.0.

TR: TODO: Documentation currently missing

TR: ### Jalousie
TR: Provided by different kinds of blinds (automatic and manual).

TR: -   `up` (rw) whether Jalousie is moving up
TR: -   `down` (rw) whether Jalousie is moving down
TR: -   `position` (ro) position of the Jalousie, a number from 0 to 1
TR:     -   Jalousie upper position = 0
TR:     -   Jalousie lower position = 1
TR: -   `shadePosition` (ro) shade position of the Jalousie (blinds), a number from 0 to 1
TR:     -   Blinds are not shaded = 0
TR:     -   Blinds are shaded = 1
TR: -   `safetyActive` (ro) only used by ones with Autopilot, this represents the safety shutdown
TR: -   `autoAllowed` (ro) only used by ones with Autopilot
TR: -   `autoActive` (rw) only used by ones with Autopilot
TR: -   `locked` (ro) only by ones with Autopilot, this represents the output QI in Loxone Config
TR: -   `infoText` (ro) informs e.g. on what caused the locked state, or what did cause the safety to become active.
TR: -   `fullUp` (wo) writing any value to this state triggers a full up motion
TR: -   `fullDown` (wo) writing any value to this state triggers a full down motion
TR: -   `shade` (wo) writing any value to this state shades the Jalousie to the perfect position

TR: ### Central Jalousie
TR: Provided by the central blinds control.

TR: -   `autoActive` (rw) only used by ones with Autopilot
TR: -   `fullUp` (wo) writing any value to this state triggers a full up motion
TR: -   `fullDown` (wo) writing any value to this state triggers a full down motion
TR: -   `shade` (wo) writing any value to this state shades of all blinds to the perfect position

TR: ### Light Controller
TR: Provided by (hotel) lighting controllers.
Scenes can only be modified in the Loxone applications, but can be selected in ioBroker.

TR: -   `activeScene` (rw) current active scene number
TR:     -   0: all off
TR:     -   1..8: user defined scene (definition/learning of scenes has to be done with the Loxone tools)
TR:     -   9: all on
TR: -   `sceneList` (ro) list of all scenes
TR: -   `plus` (wo) changes to the next scene
TR: -   `minus` (wo) changes to the previous scene

TR: This type of channel might contain other devices. See the respective chapter for more information.

TR: ### Light Controller V2
TR: Provided by (hotel) lighting controllers in Loxone software version 9 and above.
Moods can only be modified in the Loxone applications, but can be selected and combined in ioBroker.

TR: -   `moodList` (ro) list of all configured mood names
TR: -   `activeMoods` (rw) currently active list of mood names
TR: -   `favoriteMoods` (ro) list of the favorite mood names
TR: -   `additionalMoods` (ro) list of the non-favorite mood names
TR: -   `plus` (wo) changes to the next mood
TR: -   `minus` (wo) changes to the previous mood

TR: This type of channel might contain other devices. See the respective chapter for more information.

TR: ### Central Light Controller
TR: Provided by central lighting controller.

TR: -   `control` (wo) turns all lights on or off

TR: ### Mailbox
TR: Provided by Paketsafe Air / Tree.

TR: -   `notificationsDisabledInput` (ro) State of the notifications disabled input
TR: -   `packetReceived` (ro) State if a packet has been received
TR: -   `mailReceived` (ro) State if mail has been received
TR: -   `disableEndTime` (ro) timestamp until the notifications are disabled
TR: -   `confirmPacket` (wo) Confirm receive of a packet
TR: -   `confirmMail` (wo) Confirm receive of mail
TR: -   `disableNotifications` (wo) Disable the notifications for x seconds; 0 seconds for cancelling timer

TR: ### Meter
TR: Provided by utility meters.

TR: -   `actual` (ro) the actual value (number)
TR: -   `actual-formatted` (ro) if configured, the formatted actual value of the state (using the "Unit" format from Loxone Config)
TR: -   `total` (ro) the total value (number)
TR: -   `total-formatted` (ro) if configured, the formatted total value of the state (using the "Unit" format from Loxone Config)
TR: -   `reset` (wo) writing any value to this state resets the total value

TR: ### Presence Detector
TR: Provided by presence detector.

TR: -   `active` (ro) presence state
TR: -   `locked` (ro) locked state
TR: -   `events` (ro) the number of events
TR: -   `infoText` (ro) reason why the presence detector is locked

TR: ### Pushbutton
TR: Provided by virtual push-button inputs.

TR: -   `active` (rw) the current state of the pushbutton
TR: -   `pulse` (wo) writing any value to this state will simulate the button being pushed only for a very short time

TR: ### Slider
TR: Provided by analog virtual inputs.

TR: -   `value` (rw) the current value of the slider
TR: -   `value-formatted` (ro) if configured, the formatted value of the state (using the "Unit" format from Loxone Config)
TR: -   `error` (ro) indicates an invalid value of the slider

TR: ### SmokeAlarm
TR: Provided by utility meters.

TR: -   `nextLevel` (ro) the ID of the next alarm level
TR:     -   1 = Silent
TR:     -   2 = Acustic
TR:     -   3 = Optical
TR:     -   4 = Internal
TR:     -   5 = External
TR:     -   6 = Remote
TR: -   `nextLevelDelay` (ro) delay of the next level in seconds
TR: -   `nextLevelDelayTotal` (ro) total delay of the next level in seconds
TR: -   `level` (ro) the ID of the current alarm level
TR:     -   1 = Silent
TR:     -   2 = Acustic
TR:     -   3 = Optical
TR:     -   4 = Internal
TR:     -   5 = External
TR:     -   6 = Remote
TR: -   `sensors` (ro) the list of sensors
TR: -   `acousticAlarm` (ro) state of the acoustic alarm false for not active and true for active
TR: -   `testAlarm` (ro) whether testalarm is active
TR: -   `alarmCause` (ro) the cause of the alarm:
TR:     -   1 = smoke detector only
TR:     -   2 = water only
TR:     -   3 = smoke and water
TR:     -   4 = temperature only
TR:     -   5 = fire and temperature
TR:     -   6 = temperature and water
TR:     -   7 = fire, temperature and water
TR: -   `startTime` (ro) timestamp when alarm started
TR: -   `timeServiceMode` (rw) delay until service mode is disabled
TR: -   `mute` (wo) writing any value to this state mutes the sirene
TR: -   `quit` (wo) writing any value to this state acknowledges the smoke alarm

TR: ### Switch
TR: Provided by virtual input switches.

TR: -   `active` (rw) the current state of the switch

TR: ### Text State
TR: Provided by "state".

TR: -   `textAndIcon` (ro) the current value of the state

TR: ### TimedSwitch
TR: Provided by stairwell and multifunction switches.

TR: -   `deactivationDelayTotal` (ro) seconds, how long the output will be active if the timer is used
TR: -   `deactivationDelay` (ro) countdown until the output is deactivated
TR:     -   0 = the output is turned off
TR:     -   -1 = the output is permanently on
TR:     -   otherwise it will count down from deactivationDelayTotal
TR: -   `on` (wo) writing any value to this state enables the switch permanently without deactivation delay
TR: -   `off` (wo) writing any value to this state disables the switch
TR: -   `pulse` (wo) pulses the switch:
TR:     -   deactivationDelay = 0
TR:         -   Will start the countdown, from deactivationDelayTotal to 0
TR:     -   if this is a stairwell switch:
TR:         -   deactivationDelay = -1
TR:             -   No effect, will remain permanently on.
TR:         -   deactivationDelay > 0
TR:             -   Restarts the countdown
TR:     -   if this is a multifunction switch
TR:         -   turns it off (from countdown or permanent on state)

TR: ### Tracker
TR: Provided by stairwell and multifunction switches.

TR: -   `entries` (ro) list of entries returned from the miniserver

TR: ### UpDownAnalog
TR: Provided by Virtual Input (Up-Down buttons).

TR: -   `value` (rw) the current value of the input
TR: -   `value-formatted` (ro) if configured, the formatted value of the state (using the "Unit" format from Loxone Config)
TR: -   `error` (ro) indicates an invalid value of the slider

TR: ### ValueSelector
TR: Value selection.

TR: -   `value` (rw) current value
TR: -   `min` (ro) current minimum value
TR: -   `max` (ro) current maximum value
TR: -   `step` (ro) current step value

TR: ### WindowMonitor
TR: Provided by utility meters.

TR: -   `numOpen` (ro) number of open windows & doors
TR: -   `numClosed` (ro) number of closed windows & doors
TR: -   `numTilted` (ro) number of tilted windows & doors
TR: -   `numOffline` (ro) number of windows & doors that are not available
TR: -   `numLocked` (ro) number of locked windows & doors
TR: -   `numUnlocked` (ro) number of unlocked windows & doors

TR: The sum of the values from all these states is equal to the number of windows & doors monitored.? The windows/doors with two states will always be counted to the "worst" state.

TR: For each monitored window / door there will be a device with an index as its ID and the given name. They have the following states:

TR: -   `closed` (ro) the window / door is closed
TR: -   `tilted` (ro) the window / door is tilted
TR: -   `open` (ro) the window / door is open
TR: -   `locked` (ro) the window / door is locked
TR: -   `unlocked` (ro) the window / door is unlocked

TR: ## Weather Server
TR: The weather server information is provided as a device with multiple channels.
The device is called `WeatherServer`.
It contains:

TR: -   the channel `Actual` with the current weather values
TR: -   one channel for each forecast hour called `HourXX` where `XX` is the number of hours from now

TR: Every channel contains the following states:

TR: -   `barometricPressure`: numeric barometric pressure value
TR: -   `barometricPressure-formatted`: formatted barometric pressure value with unit
TR: -   `dewPoint`: numeric dew point value
TR: -   `dewPoint-formatted`: formatted dew point value with unit
TR: -   `perceivedTemperature`: numeric perceived temperature value
TR: -   `perceivedTemperature-formatted`: formatted perceived temperature value with unit
TR: -   `precipitation`: numeric precipitation value
TR: -   `precipitation-formatted`: formatted precipitation value with unit
TR: -   `relativeHumidity`: numeric relative humidity value
TR: -   `relativeHumidity-formatted`: formatted relative humidity value with unit
TR: -   `solarRadiation`: solar radiation value
TR: -   `temperature`: numeric temperature value
TR: -   `temperature-formatted`: formatted temperature value with unit
TR: -   `timestamp`: timestamp of the data as `value.time` (JavaScript time)
TR: -   `weatherType`: numeric weather type enumeration value
TR: -   `weatherType-text`: text representation of the weather type
TR: -   `windDirection`: wind direction value
TR: -   `windSpeed`: wind speed value
TR: -   `windSpeed-formatted`: formatted wind speed value with unit

TR: ## Unsupported Control Types
TR: When Loxone adds new control types, they are most often not immediately supported by this adapter.

TR: In this case, the control will have "Unknown:" in front of its name. E.g. `Unknown: Wallbox`

TR: Those controls will contain all states reported by the Miniserver, but they will all be read-only strings.

TR: If you need better support for a new control type, please follow the steps in the next section to requeset a new feature.

TR: **Sentry:** unsupported control types will be reported to the developers using Sentry. This way you might get new controls in the next release without having to request it yourself.

TR: ## Bug Reports and Feature Requests
TR: Please use the GitHub repository to report any bugs or request new features.

TR: If you require an unsupported control type, please provide the name as it is reported in the error log of ioBroker as well as the entire raw contents of the device in the ioBroker object tree:

TR: Log file example for "LightController":

![TR: Log of missing LightController control](../../../en/adapterref/iobroker.loxone/doc/log-missing-control-type.png)

TR: Native value from ioBroker &gt; Objects

![TR: Details of missing LightController control](../../../en/adapterref/iobroker.loxone/doc/details-missing-control-type.png)

TR: ## Legal
TR: This project is not affiliated directly or indirectly with the company Loxone Electronics GmbH.

TR: Loxone and Miniserver are registered trademarks of Loxone Electronics GmbH.

## Changelog

<!--
    Placeholder for the next version (at the beginning of the line):
    ### **WORK IN PROGRESS**
-->

### 2.2.1 (2021-05-18)

-   (UncleSamSwiss) Fixed typo causing "Cannot read property 'off' of undefined" (IOBROKER-LOXONE-2R, #72)
-   (UncleSamSwiss) Improved Sentry reporting for structure file

### 2.2.0 (2021-05-17)

-   (UncleSamSwiss) Unknown/unsupported controls are now shown with their states as read-only strings
-   (raintonr) Fixes for auto-position based on percentage (#76)
-   (raintonr) Added support for IRoomControllerV2 (#22)
-   (UncleSamSwiss) Added experimental support for EIBDimmer (#15)
-   (UncleSamSwiss) Added support for ValueSelector (#36)
-   (UncleSamSwiss) Added support for TextState (#73)
-   (UncleSamSwiss) Added support for UpDownAnalog (#57)
-   (UncleSamSwiss) Fixed some "State has wrong type" warnings (#99, #128)
-   (UncleSamSwiss) Added support for Lumitech color picker (#44)
-   (UncleSamSwiss) Weather server data can now be filtered (#131)
-   (UncleSamSwiss) Added support for PresenceDetector (IOBROKER-LOXONE-1R)
-   (UncleSamSwiss) Added support for AAL Smart Alarm (IOBROKER-LOXONE-1X)
-   (UncleSamSwiss) Added support for AAL Emergency Button (IOBROKER-LOXONE-1W)
-   (UncleSamSwiss) Added support for Paketsafe (IOBROKER-LOXONE-1P)

### 2.1.0 (2020-12-21)

-   (raintonr) Fixed: activeMoods can get stuck/not sync properly; all events is now handled with a queue (#58, #61, #62)
-   (raintonr) Added open/close buttons to Garage/Gate Control (#59, #60)
-   (pinkit) Added support for virtual text inputs (#48)
-   (UncleSamSwiss) Updated to the latest adapter template
-   (UncleSamSwiss) Changed log level of "Currently unsupported control type" message to "info" (#65)

### 2.0.2 (2020-10-26)

-   (UncleSamSwiss) Fixed color picker updates (#52)
-   (UncleSamSwiss) TimedSwitch to have `on`/`off` instead of `active` (#53)
-   (UncleSamSwiss) Cleaning illegal characters for room and function names (#54)

### 2.0.1 (2020-09-24)

-   (UncleSamSwiss) Fixed percentage states always showing 0% (#49)
-   (UncleSamSwiss) Fixed analog virtual inputs wouldn't set the value 0 from ioBroker (#47)
-   (UncleSamSwiss) Added translations to package information.

### 2.0.0

-   **BREAKING:** Since the password is now encrypted, you will need to enter the password again after an update to this version!
-   (UncleSamSwiss) Updated to the latest development tools and changed to the TypeScript language

### 1.1.0

-   (UncleSamSwiss) Added support for Miniserver Gen 2
-   (sstroot) RGB for LightControllerV2
-   (Apollon77) Updated CI Testing

### 1.0.0

-   (UncleSamSwiss) Fixed issue that was resetting the custom settings and cloud smartName
-   (alladdin) Fixed connection issues with Loxone Miniserver 10
-   (UncleSamSwiss) Changed all write-only "switch"es to "button"s
-   (UncleSamSwiss) Added support for AlarmClock control
-   (Apollon77) Updated CI Testing

### 0.4.0

-   (UncleSamSwiss) Improved support for Loxone Config 9
-   (UncleSamSwiss) Changed all color choosers (i.e. color lights) to use RGB (previously HSV/HSL was completely wrong)

### 0.3.0

-   (UncleSamSwiss) Control names only synchronized on the first time by default (configurable); users can change control names the way they want

### 0.2.1

-   (UncleSamSwiss) Added support for Slider control

### 0.2.0

-   (UncleSamSwiss) Added proper support for Alexa for the following controls: Alarm, AudioZone, Gate, Jalousie and LightController

### 0.1.1

-   (UncleSamSwiss) Added support for synchronizing rooms and functions (categories) from Loxone Miniserver

### 0.1.0

-   (UncleSamSwiss) Added support for many more controls including commands from ioBroker to Loxone Miniserver

### 0.0.3

-   (Bluefox) Formatting, refactoring and Russian translations

### 0.0.2

-   (UncleSamSwiss) Added creation of an empty device for all unsupported controls (helps figure out its configuration)

### 0.0.1

-   (UncleSamSwiss) Initial version

## License

Copyright 2021 UncleSamSwiss

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.