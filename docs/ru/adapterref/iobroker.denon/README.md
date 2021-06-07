---
BADGE-Number of Installations: http://iobroker.live/badges/denon-stable.svg
BADGE-NPM version: http://img.shields.io/npm/v/iobroker.denon.svg
BADGE-Downloads: https://img.shields.io/npm/dm/iobroker.denon.svg
BADGE-NPM: https://nodei.co/npm/iobroker.denon.png?downloads=true
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.denon/README.md
title: TR: ioBroker.denon
hash: QJOQw2ySmAxZxcy7FlzxYF/KQ/SiBO4lyLxKnHMYyBE=
---
![TR: Logo](../../../en/adapterref/iobroker.denon/admin/denon.png)

![TR: Number of Installations](http://iobroker.live/badges/denon-stable.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.denon.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.denon.svg)
![TR: NPM](https://nodei.co/npm/iobroker.denon.png?downloads=true)

TR: # ioBroker.denon
===========================

![TR: Build Status](https://github.com/foxriver76/ioBroker.denon/workflows/Test%20and%20Release/badge.svg)

TR: ## Installation
TR: You can either install the adapter via the ioBroker web interface or on your local machine via npm.

TR: ### Browser-based
TR: 1. Open your ioBroker web interface in a browser (eg: 192.168.30.70:8081)
TR: 2. Click on Tab "Adapters"
TR: 3. Type "Denon" in the Filter
TR: 4. Click on the three points and then on the "+" symbol of the DENON AVR adapter

![TR: Add Adapter](../../../en/adapterref/iobroker.denon/docs/en/media/plusAddAdapter.png)

TR: ### Local machine
TR: Navigate into your iobroker folder and execute the following command:

```bash
npm i iobroker.denon
```

TR: ## Setup
TR: Additional to the adapter installation you have to make sure that your AVR is correctly configured.

TR: ### ioBroker
TR: 1. Open your ioBroker interface in a browser (eg: 192.168.1.33:8081)
TR: 2. Navigate to Tab "Adapters"
TR: 3. Click on the three points and then on the "+" symbol of the DENON AVR adapter

![TR: Add Adapter](../../../en/adapterref/iobroker.denon/docs/en/media/plusAddAdapter.png)

TR: 4. Now you can see the adapter configuration page --> type in the ip-address of your DENON AVR or click on the search

TR: icon to find AVRs in your network (via UPnP) ![TR: Adapter Configuration](../../../en/adapterref/iobroker.denon/docs/en/media/fillInIp.png)

TR: 5. If you also want to adjust the request/poll interval, make sure to click on the "Advanced Settings" Tab.

TR: By decreasing the Poll Interval the adapter will decrease the time between updating the display contents.
By decreasing the request interval the time between sending commands will be decreased.
The default settings should fit well for the most users.
![TR: Advanced Settings](../../../en/adapterref/iobroker.denon/docs/en/media/advancedSettings.png)

TR: 6. Click on Save & Close

TR: ### Network Setup of AV Receiver
TR: 1. Press SETUP button, then Menu appears on FL-display(and GUI)
TR: 2. Select "Network" --> "Settings"
TR: 3. Set parameters described below

TR:    *DHCP: "ON" (Use this setting when DHCP server is on the local network.)*

TR:    *IP Address: When <DHCP> sets "Off”, please set IP address.*

TR:    *Subnet Mask: When <DHCP> sets "Off", please set Subnet Mask.*

TR:    *Gateway: Set the address of Gateway when Gateway is on the local network.*

TR:    *Primary DNS: Do not set this parameter.*

TR:    *Second DNS: Do not set this parameter.*

TR:    *Proxy: Set this parameter "Off".*

TR: 4. Press SETUP button, then Menu appears on FL-display (and GUI)
TR: 5. Select “Network" --> Network Control/IP Control"
TR: 6. Set this parameter to "Always On".

TR: ## Usage
TR: Take note, that the AVRs can only manage a single telnet connection. If you are having an active telnet connection e. g. with the javascript adapter, the AVR will refuse the connection of this adapter.
Here you can find a description of the states and how to use them.

TR: ### Buttons
TR: The adapter creates the following buttons:

TR: #### Channel: zoneMain / zone2 / zone3
TR: * zoneMain.playPause

TR:    *Play and pause music from Bluetooth, Online, USB/iPod sources.*

TR: * zoneMain.play

TR:    *Play music from Bluetooth, Online, USB/iPod sources.*

TR: * zoneMain.pause

TR:    *Pause music from Bluetooth, Online, USB/iPod sources.*

TR: * zoneMain.skipMinus

TR:    *Skip to previous title.*

TR:    *NOT FULLY SUPPORTED FOR HEOS AVR'S*

TR: * zoneMain.skipPlus

TR:    *Skip to next title.*

TR:    *NOT FULLY SUPPORTED FOR HEOS AVR'S*

TR: * zoneMain.volumeDown / zone2.volumeDown / zone3.volumeDown

TR:    *Decrease volume of Main Zone / Zone2 / Zone3.*

TR: * zoneMain.volumeUp / zone2.volumeUp / zone3.volumeUp

TR:    *Increase volume of Main Zone / Zone2 / Zone3.*

TR: * zoneMain.equalizerBassUp / zone2.equalizerBassUp / zone3.equalizerBassUp

TR:    *Button which increases bass level of the Zone.*

TR:    *Bass and treble settings can be adjusted when Dyn EQ is set to OFF and Tone Control is on*

TR: * zoneMain.equalizerBassDown / zone2.equalizerBassDown / zone3.equalizerBassDown

TR:    *Button which decreases bass level of the Zone.*

TR:    *Bass and treble settings can be adjusted when Dyn EQ is set to OFF and Tone Control is on*

TR: * zoneMain.equalizerTrebleUp / zone2.equalizerTrebleUp / zone3.equalizerTrebleUp

TR:    *Button which increases treble level of the Zone.*

TR:    *Bass and treble settings can be adjusted when Dyn EQ is set to OFF and Tone Control is on*

TR: * zoneMain.equalizerTrebleDown / zone2.equalizerTrebleDown / zone3.equalizerTrebleDown

TR:    *Button which decreases treble level of the Zone.*

TR:    *Bass and treble settings can be adjusted when Dyn EQ is set to OFF and Tone Control is on*

TR: #### Channel: settings
TR: * settings.subwooferLevelDown / settings.subwooferTwoLevelDown

TR:    *Reduce subwoofer level by pressing the button.*

TR: * settings.subwooferLevelUp / settings.subwooferTwoLevelUp

TR:    *Increase subwoofer level by pressing the button.*

TR: * settings.containmentAmountDown

TR:    *Decrease Audyssey LFC amount. The button will only be created, if it is supported by your AVR.*

TR: * settings.containmentAmountUp

TR:    *Increase Audyssey LFC amount. The button will only be created, if it is supported by your AVR.*

TR: * settings.cursorUp / settings.cursorDown / settings.cursorLeft / settings.cursorRight

TR:    *Simulates the cursor buttons of your remote control*

TR: * settings.enter

TR:    *Simulates the enter button of your remote control*

TR: * settings.return

TR:    *Simulates the return/back button of your remote control*

TR: * settings.option

TR:    *Simulates the option button of your remote control*

TR: * settings.info

TR:    *Simulates the info button of your remote control*

TR: ### States
TR: Following states will be created by the adapter:

TR: #### Channel: info
TR: * info.connection

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |boolean|R|

TR:    *Read-only boolean indicator. If your broker is connected to your DENON AVR, the state is true otherwise false.*

TR: * info.friendlyName

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R|

TR:    *Read only string. Contains the friendly name of the connected AVR.*

TR: * info.onlinePresets

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R|

TR: *String in JSON array format, which represents the current saved favorites by its id and channel.
The names of each channel are limited by 20 digits. You can save the current channel to an id by setting settings.savePreset and load one by setting settings.loadPreset to the related id.*

TR: #### Channel: zoneMain / zone2 / zone3
TR: * zoneMain.volume / zone2.volume / zone3.volume

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |number|R/W|

TR: *Number value which represents the current Main Zone / Zone2 / Zone 3 volume of your AVR. You can also set the volume here.
The volume is represented in dB too in separate states, e. g. mainVolumeDB*

TR:    *Range is from 0 to 98 (maybe lower due to maximumVolume), where 80 = 0 dB*

TR:    *Example:*

```javascript
setState('denon.0.zoneMain.volume', 45.5); // Sets volume of Main Zone to 45.5
```

TR: * zoneMain.maximumVolume

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |number|R|

TR:    *Read-only number which represents the maximum possible volume, where 80 = 0 dB. The volume is also set in dB in the maximumVolumeDB state.*

TR: * zoneMain.muteIndicator / zone2.muteIndicator / zone3.muteIndicator

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |boolean|R/W|

TR:    *Boolean value, which is true if the Main Zone / Zone2 / Zone3 is muted, otherwise false. You can mute your AVR with this state.*

TR:    *Example:*

```javascript
setState('denon.0.zoneMain.muteIndicator', true); // Mutes the Main Zone of your AVR
```

TR: * zoneMain.powerZone / zone2.powerZone / zone3.powerZone

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |boolean|R/W|

TR:    *Boolean value, which is true if the Zone is turned on, otherwise false. You can turn your AVR / Zone on and off with this state.*

TR: * zoneMain.selectInput / zone2.selectInput / zone3.selectInput

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR:    *The string value contains the current input source. You can also set the input source with the following encoding:*

TR:    *0: 	PHONO*

TR:    *1: 	CD*

TR:    *2: 	TUNER*

TR:    *3: 	DVD*

TR:    *4: 	BD*

TR:    *5: 	TV*

TR:    *6: 	SAT/CBL*

TR:    *7: 	MPLAY*

TR:    *8: 	GAME*

TR:    *9: 	NET*

TR:    *10:	SPOTIFY*

TR:    *11:	LASTFM*

TR:    *12:	IRADIO*

TR:    *13:	SERVER*

TR:    *14:	FAVORITES*

TR:    *15:	AUX1*

TR:    *16:	AUX2*

TR:    *17:	AUX3*

TR:    *18:	AUX4*

TR:    *19:	AUX5*

TR:    *20:	AUX6*

TR:    *21:	AUX7*

TR:    *22: BT*

TR:    *23: USB*

TR: *Please note, that not every input source is available on every AVR model. If your AVR has additional inputs, they will be appended to the list, once they have been detected.*

TR:    *Example:*

```javascript
 setState('denon.0.zoneMain.selectInput', '5'); // Selects TV as input for Main Zone
```

TR: * zoneMain.quickSelect / zone2.quickSelect / zone3.quickSelect

| TR:    |Data type|Permission|
   |:---:|:---:|
| TR:    |number|R/W|

TR:    *Emulates the quick select buttons of your remote, with numbers from 1 to 5 for Main Zone / Zone2 / Zone3.*

TR: * zoneMain.sleepTimer / zone2.sleepTimer / zone3.sleepTimer

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |number|R/W|

TR:    *Number-value to read and set the sleep timer for the selected zone. The value will be updated in less than 10 seconds.*

TR: * zoneMain.iconURL

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R|

TR:    *Contains a link where you can find the cover of the channel/song which is currently played.*

TR:    *NOT SUPPORTED FOR HEOS AVR'S*

TR: * zoneMain.equalizerBass / zone2.equalizerBass / zone3.equalizerBass

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |number|R/W|

TR:    *Number value which represents the bass level of the Zone. Value range is from -6 to +6 dB.*

TR:    *Bass and treble settings can be adjusted when Dyn EQ is set to OFF and Tone Control is on*

TR: * zoneMain.equalizerTreble / zone2.equalizerTreble / zone3.equalizerTreble

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |number|R/W|

TR:    *Number value which represents the treble level of the Zone. Value range is from -6 to +6 dB.*

TR:    *Bass and treble settings can be adjusted when Dyn EQ is set to OFF and Tone Control is on*

TR: * zoneMain.channelVolumeFrontLeft / zone2.channelVolumeFrontLeft / zone3.channelVolumeFrontLeft / ...

| TR:    |Data type|Permission|
   |:---:|:---:|
| TR:    |number|R/W|

TR: *Number value which represents the current channel volume for each speaker. Each speaker has a separate state. The settings affect the current Select Input Mode. The state can be adjusted from -12 dB to +12 dB.*

TR: #### Channel: display
TR: * display.displayContent

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R|

TR:    *Read-only string which contains the content of your AVR display. It has nine states 0 - 9.*

TR:    *DISPLAY CONTENT IS NOT SUPPORTED FOR HEOS AVR'S*

TR: * display.brightness

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR:    *String value which represents the display brightness. The value can also set the display brightness by the following encoding:*

TR:    *0: Off --> turns display off*

TR:    *1: Dark --> turns display dark*

TR:    *2: Dimmed --> turns display dimmed*

TR:    *3: Bright --> turns display bright*

TR:    *Example:*

```javascript
setState('denon.0.display.brightness', '3'); // Sets display brightness to "Bright"
```

TR: #### Channel: settings
TR: * settings.powerSystem

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |boolean|R/W|

TR:    *Boolean value which is true, if the AVR is turned on, otherwise false. You can also turn your AVR on and off with this state.*

TR: * settings.surroundMode

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR:    *The string value contains the current Surround mode. You can also change the source with the following encoding:*

TR:    *0:	STEREO*

TR:    *1:	VIRTUAL*

TR:    *2:	VIDEO GAME*

TR:    *3:	MCH STEREO*

TR:    *4:	DTS SURROUND*

TR:    *5:	DOLBY DIGITAL*

TR:    *6:	MOVIE*

TR:    *7:	MUSIC*

TR:    *8:	DIRECT*

TR:    *9:	PURE DIRECT*

TR:    *10:	AUTO*

TR:    *11:	GAME*

TR:    *12:	AURO3D*

TR:    *13:	AURO2DSURR*

TR:    *14:	WIDE SCREEN*

TR:    *15:	SUPER STADIUM*

TR:    *16:	ROCK ARENA*

TR:    *17:	JAZZ CLUB*

TR:    *18:	CLASSIC CONCERT*

TR:    *19:	MONO MOVIE*

TR:    *20:	MATRIX*

TR:    *Please note, that not every Surround mode is available on every AVR model.*

TR:    *Example:*

```javascript
setState('denon.0.settings.surroundMode', '3'); // Sets Multi Channel Stereo as surround mode
```

TR: * settings.lfeAmount

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |number|R/W|

TR: *Amount of subwoofer signal additional directed to speakers in dB.
Range is from 0 dB to -10 dB. Where 10 = -10 dB.*

TR: * settings.expertCommand

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR:    *You can send your own custom commands with this state. You can find an overview about the existing commands in the [TR: AVR-Control-Protocol.pdf](docs/AVR-Control-Protocol.pdf)*

TR:    *Example:*

```javascript
setState('denon.0.settings.expertCommand', 'ECOON'); // Turns Main Zone ECO mode on
```

TR: * settings.expertReadingPattern

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR: *If you want to get specific answers stored in `settings.expertReadingResult` you have to set a RegEx to this state.
RegEx has to be set, so that a RegEx Constructor can use it. It is recommended to use a [TR: RegEx tester](https://regexr.com/).
Do not set `/` at the beginning or end of the RegEx.*

TR:     *Example:*

```javascript
setState('denon.0.settings.expertReadingPattern', '(MV.+)|(SSINFAISFSV.+)');

ttings.expertReadingResult

|Data type|Permission|
|:---:|:---:|
|string|R|

*Incoming data, which matches the RegEx of `settings.expertReadingPattern` will be set to this state.*


ttings.dialogControl

|Data type|Permission|
|:---:|:---:|
|number|R/W|

*The dialog control, which can be operated from 0 dB to 6 dB.*

ttings.dialogLevelAdjust

|Data type|Permission|
|:---:|:---:|
|boolean|R/W|

*Turns the dialog level adjustment on, which allows to modify the dialog volume of DTS content.*

ttings.dialogLevel

|Data type|Permission|
|:---:|:---:|
|boolean|R/W|

*If dialog level adjustment is turned on you can modify the dialog volume of DTS content between -12 dB and +12 dB.*

ttings.outputMonitor

|Data type|Permission|
|:---:|:---:|
|string|R/W|

Select the output monitor of your AVR. This state will only be created if your AVR supports two HDMI outputs. You can switch the state between:*

0: AUTO --> Auto detection of monitor*

1: 1 --> Outputs signal to monitor 1*

2: 2 --> Outputs signal to monitor 2*

Example:*

``javascript
etState('denon.0.settings.outputMonitor', '2'); // Sets monitor 2 as active monitor
``

TR: * settings.videoProcessingMode

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR:    *Select the video processing mode of your AVR. This state will only be created if your AVR supports it. You can switch the state between:*

TR:    *0: AUTO*

TR:    *1: GAME*

TR:    *2: MOVIE*

TR:    *Example:*

```javascript
setState('denon.0.settings.videoProcessingMode', '2'); // Sets Video Processing Mode to "MOVIE"
```

TR: * settings.centerSpread

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |boolean|R/W|

TR:    *Boolean-value which is true if center spread is truned on, else false. You can also turn on/off center spread with this state.*

TR: * settings.dynamicEq

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |boolean|R/W|

TR:    *Boolean value which represents the state of Dynamic EQ. You can also set Dynamic EQ on and off with this state.*

TR: * settings.subwooferLevelState

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |boolean|R/W|

TR:    *Boolean value, if it's true, you are able to make changes on the subwoofer level.*

TR: * settings.subwooferLevel / settings.subwooferTwoLevel

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |number|R/W|

TR: *Number value which indicates the current subwoofer level. The value has a range from -12 to 12 (-12 dB to +12 dB).
The SubwooferTwoLevel state will only be created if it is supported by your AVR.*

TR: * settings.audysseyLfc

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |boolean|R/W|

TR: *Boolean value, which contains and is able to control Audyssey Low Frequency Containment status (on/off).
The state will only be created, if it is supported by your AVR.*

TR: * settings.containmentAmount

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |number|R/W|

TR: *Number value to set the Low Frequency Containment Amount. The value can be between 1 and 7. The state will only be created, if it is supported by your AVR.*

TR: * settings.multEq

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR:    *String value, to set the MultEQ function of your AVR with the following encoding:*

TR:    *0: OFF*

TR:    *1: AUDYSSEY*

TR:    *2: BYP.LR*

TR:    *3: FLAT*

TR:    *4: MANUAL*

TR: * settings.dynamicVolume

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR:    *String value to select the Dynamic Volume by following encoding:*

TR:    *0: OFF --> turns Dynamic Volume off*

TR:    *1: LIT --> turns Dynamic Volume to light*

TR:    *2: MED --> turns Dynamic Volume to medium*

TR:    *3: HEV --> turns Dynamic Volume to heavy*

TR: * settings.referenceLevelOffset

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR:    *String value to select the Reference Level Offset by the following encoding:*

TR:    *0: 	0 dB*

TR:    *5:	5 dB*

TR:    *10:	10 dB*

TR:    *15: 15 dB*

TR:    *Example:*

```javascript
setState('denon.0.settings.referenceLevelOffset', '5'); // Sets Reference Level Offset to 5 dB
```

TR: * settings.pictureMode

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR:    *String value to set the Picture Mode Direct Change. This state will only be created when your AVR supports it*

TR:    *You can set the following values as string:*

TR:    *'Off'*

TR:    *'Standard'*

TR:    *'Movie'*

TR:    *'Vivid'*

TR:    *'Stream'*

TR:    *'Custom'*

TR:    *'ISF Day'*

TR:    *'ISF Night'*

TR:    *Example:*

```javascript
setState('denon.0.settings.pictureMode', 'Standard'); // Set Picture Mode Direct Change to Standard
```

TR: * settings.toneControl

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |boolean|R/W|

TR:    *Boolean value, which indicates Tone Control status. You can turn it off/on with this state.*

TR:    *Tone Control can only be turned on when Dyn EQ is set to OFF*

TR: * settings.setupMenu

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |boolean|R/W|

TR:    *Boolean indicator, which indicates if setup menu is currently open or closed. You can open and close it with this state.*

TR: * settings.savePreset

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |number|R/W|

TR: *Number value, which can be set to a value of info.onlinePresets. Then the current channel will be saved as a preset to the given number.
Only numbers which are contained in info.onlinePresets can be used. The state will not get an acknowledge, no matter the command was successful or not. You can check info.onlinePresets to check if the command has worked as aspected.*

TR: * settings.loadPreset

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |number|R/W|

TR: *Number value, which can be set to a value of info.onlinePresets. This will load the related channel.
This state will not get an acknowledge, no matter the command has been successful or not.*

TR: ### Other States
TR: Due to the fact that some AVRs like the DENON POA-3012CI use another logic there are some differences in the states.
The states which are equal to the ones listed above are: settings.powerSystem, settings.expertCommand, display.brightness and info.connection. Additional the following states are created for each zone 2-12 (even):

TR: * zoneX.speakerOneVolume / zoneX.speakerTwoVolume

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |number|R/W|

TR: *Number value, which represents the volume of the AVR's speaker. If operationMode is set to 'BRIDGED' the speakers cannot independently controlled and the control of one also controls the other ones volume.*

TR: * zoneX.selectInputOne / zoneX.selectInputTwo

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR: *Key value pair, which represents the selected input of the AVR's speaker. If operationMode is set to 'BRIDGED' the speakers cannot independently controlled and the control of one also controls the other ones input.*

TR:     *The following values are possible:*

TR:     *'0': 'BUS L'*

TR:     *'1': 'BUS R'*

TR:     *'2': 'BUS M'*

TR:     *'3': 'AUX'*

TR: * zoneX.operationMode

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR: *Key value pair, which represents the operationMode of the AVR. If operationMode is set to 'BRIDGED' the speakers cannot independently controlled and controlling speaker one also controls speaker two.*

TR:     *The following values are possible:*

TR:     *'0': 'NORMAL'*

TR:     *'1': 'BRIDGED'*

TR: * zoneX.lowCutFilterSpeakerOne / zoneX.lowCutFilterSpeakerTwo

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |boolean|R/W|

TR: *Boolean value, which indicates if the low cut filter for the speaker is enabled or disabled. In bridged mode both speakers will depend on each other.*

TR: * zoneX.zoneTurnOnModeChange

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |string|R/W|

TR: *Key value pair, which represents the zone turn on mode change of the zone. You can also control your AVR with this state.*

TR:     *The following values are possible:*

TR:     *'0': 'Constant'*

TR:     *'1': 'Trigger in'*

TR:     *'2': 'Audio signal'*

TR:     *'3': 'Off'*

TR: * zoneX.triggerInput

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |boolean|R/W|

TR:     *Turn trigger input on or off with this boolean value.*

TR: * zoneX.audioSignalInput

| TR:     |Data type|Permission|
    |:---:|:---:|
| TR:     |boolean|R/W|

TR:     *Boolean value which indicates and controls the audio signal input of your AVR.*

TR: ## Missing functions & bugs
TR: If you are missing any functions or detected a bug, please open an [TR: issue](https://github.com/foxriver76/ioBroker.denon/issues).

TR: The adapter is tested with an DENON AVR-X1200W and a Marantz SR5009.

## Changelog
<!--
	Placeholder for the next version (at the beginning of the line):
	### __WORK IN PROGRESS__
-->

### 1.11.0 (2021-06-06)
* (foxriver76) implemented dialog level adjustment for DTS content (closes #143)
* (foxriver76) new datapoints are `settings.dialogLevelAdjust`, `settings.dialogLevel`, `settings.dialogControl`

### 1.10.7 (2021-05-12)
* (foxriver76) fix missing conversion to db on equalizer states for additional zones (fixes #137)

### 1.10.6 (2021-05-03)
* (foxriver76) we fixed some more types

### 1.10.5 (2021-05-02)
* (foxriver76) we fixed some datapoints having wrong types or wrong state values set (fixes #130)

### 1.10.4 (2021-02-20)
* (foxriver76) if an older model (e.g. AVR 3808) just sends `NSE`, we do not set displayContent state anymore (fixes #112)

### 1.10.3 (2021-01-28)
* (foxriver76) don't poll whole online presets after change, it is unnecessary load

### 1.10.2 (2021-01-28)
* (foxriver76) return after detecting NSH command
* (foxriver76) use release script

### 1.10.0 (2021-01-17)
* (foxriver76) auto-detect selectInput of all zones

### 1.9.4 (2021-01-03)
* (foxriver76) added missing rear height speaker states
* (foxriver76) revert the last added options because they are not working as intended
* (foxriver76) no longer remove digits and spaces from surroundMode response

### 1.9.2 (2021-01-03)
* (foxriver76) added some missing options for surroundMode

### 1.9.1 (2020-12-03)
* (foxriver76) prevent writing in destroyed socket on adapter unload
* (foxriver76) add subwoofer states for main zone
* (foxriver76) internal optimizations

### 1.8.1 (2020-11-29)
* (foxriver76) added states for atmos speakers `channelVolumeSurroundDolbyRight/Left` and `channelVolumeFrontDolbyLeft/Right`
* (foxriver76) fixed bug with setting channelVolume of other zones than main
* (foxriver76) added states `channelVolumeFrontHeightRight/Left` and `channelVolumeSurroundHeightLeft/Right`

### 1.7.7 (2020-04-28)
* (foxriver76) fixed timing issue which could lead to state creation procedure triggered more than once

### 1.7.5 (2020-04-21)
* (foxriver76) better error handling

### 1.7.4 (2020-04-01)
* (foxriver76) fix potential timeout issues

### 1.7.2 (2020-01-08)
* (foxriver76) another fix for DENON Picool to keep connection alive when turned off

### 1.7.1 (2019-11-19)
* (foxriver76) added ability to read desired data by expertReading states

### 1.6.1 (2019-10-08)
* (foxriver76) fixed bug with selectInput for zone2 and 3

### 1.6.0
* (foxriver76) added new state settings.lfeAmount

### 1.5.1
* (foxriver76) fix to detect DENON Ceol

### 1.5.0
* (foxriver76) added channel volumes for zone2 + 3
* (foxriver76) other optimizations
* (foxriver76) support of DENON POA-3012CI and similar AVRs
* (foxriver76) create db volumes everytime

### 1.3.2
* (foxriver76) compact mode compatibility added

### 1.2.7
* (foxriver76) make sure states are never set before creation
* (foxriver76) minor fixes and improvements

### 1.2.6
* (foxriver76) only updating sleep timer and quick select on change
* (foxriver76) using promises wherever possible
* (foxriver76) minor improvements

### 1.2.4
* (foxriver76) fix verbose logging on network issues
* (foxriver76) as long as connection error stays the same, logging happens on debug

### 1.2.3
* (foxriver76) add missing usb to selectInput for all zones

### 1.2.2
* (foxriver76) use adapter core

### 1.2.1
* (foxriver76) info.onlinePresets converted to JSON array to work properly with widgets

### 1.2.0
* (foxriver76) added info.onlinePresets which is a JSON string containing all presets
* (foxriver76) settings.savePreset and loadPreset to save and load presets according to the info.onlinePresets

### 1.1.0
* (foxriver76) added Bluetooth as select input (BT)

### 1.0.0
* (foxriver76) formal version increment

### 0.6.0
* (foxriver76) fix that enables Marantz receiver to use the quickSelect functionality
* (foxriver76) quick select is now acknoledged
* (foxriver76) remove old quick select buttons

### 0.5.0
* (foxriver76) added possibility to control channelVolume per speaker for Main Zone
* (foxriver76) new states added to readme and documentation

### 0.4.4
* (foxriver76) fix bug where picture mode command was sent as undefined

### 0.4.3
* (foxriver76) fallback for advanced settings
* (foxriver76) fix double reconnection when AVR closes the socket
* (foxriver76) fix a problem where callback for pictureMode is called to early

### 0.4.2
* (foxriver76) pictureMode role fixed

### 0.4.1
* (foxriver76) added picture mode direct change

### 0.3.9
* (foxriver76) only create containment amount, audyssey lfc, subwoofer two level if supproted
* (foxriver76) readme updated

### 0.3.8
* (foxriver76) add state to control center spread
* (foxriver76) readme updated
* (foxriver76) addded video processing mode control
* (foxriver76) optimizations and minor fixes

### 0.3.7
* (foxriver76) minor code optimization
* (foxriver76) fixes on readme
* (foxriver76) logging undhandled commands on debug

### 0.3.6
* (foxriver76) fixed displayState non-readable chars for old AVRs
* (foxriver76) fixes on readme
* (foxriver76) capital chars in mainZone volumeUp/down names, are now lowercase

### 0.3.5
* (foxriver76) removed isPlaying state, because not working properly
* (foxriver76) update readme

### 0.3.4
* (foxriver76) fix that HEOS does not create http and display content related states

### 0.3.3
* (foxriver76) added state for setup button
* (foxriver76) added cursors and remote control buttons
* (foxriver76) readme update

### 0.3.2
* (foxriver76) Added isPlaying state for non-HEOS AVR's, thanks to bluefox
* (foxriver76) Added link to cover for non-HEOS AVR's
* (foxriver76) displayContent, isPlaying, coverURL will only be generated for non-HEOS
* (foxriver76) Updated readme

### 0.3.1
* (foxriver76) Added placeholder ip in config gui
* (foxriver76) fixed volume in db for main zone

### 0.3.0
* (bluefox & foxriver76) Names and roles were refactored
* (bluefox) Discovery added
* (foxriver76) Update Readme
* (foxriver76) Implemented separate Play & Pause button
* (bluefox & foxriver76) Internal improvements

### 0.2.4
* (foxriver76) prevent adapter from doing more than one reconnect attempt at the same time
* (foxriver76) improved stability
* (foxriver76) update readme

### 0.2.3
* (foxriver76) added possibility to handle states in dB additional
* (foxriver76) minor changes

### 0.2.2
* (foxriver76) removed unneeded files
* (foxriver76) state lists are now of type string due to better compatibility
* (foxriver76) optimized matching for state lists
* (foxriver76) some state lists can be set by the value additionaly to the key

### 0.2.1
* (foxriver76) small bug fixes on connection error handling
* (foxriver76) improvements on module size

### 0.2.0
* (foxriver76) preparations for offical repository

### 0.1.9
* (foxriver76) improved stability
* (foxriver76) improved fault tolerance on volume (e. g. for use as smart device)

### 0.1.8
* (foxriver76) adapter sepcific connection error handling
* (foxriver76) minor reconnect fix

### 0.1.7
* (foxriver76) subwoofer level is now in dB
* (foxriver76) added control of treble, bass and tone control state
* (foxriver76) readme updated

### 0.1.6
* (foxriver76) connection stability improvements
* (foxriver76) some parameter settings added
* (foxriver76) readme updated

### 0.1.5
* (foxriver76) sleep timer for every zone
* (foxriver76) admin2 compatibility
* (foxriver76) minor fixes

### 0.1.4
* (foxriver76) HEOS bug fix (timeout)
* (foxriver76) new state for custom commands (expertCommand)
* (foxriver76) enhanced readme

### 0.1.3
* (foxriver76) bug fixes for Zone3
* (foxriver76) new state for main zone power
* (foxriver76) minor other improvements

### 0.1.2
* (foxriver76) Performance optimization
* (foxriver76) Faster display update
* (foxriver76) More appropriate reconnect intervall

### 0.1.1
* (foxriver76) new readme for npm

### 0.1.0
* (foxriver76) handling up to three zones
* (foxriver76) handling display content
* (foxriver76) setting display brightness

### 0.0.1
* (foxriver76) initial release

## License
The MIT License (MIT)

Copyright (c) 2018-2021 Moritz Heusinger <moritz.heusinger@gmail.com>

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