---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.upnp/README.md
title: TR: ioBroker.upnp
hash: HJxTPvVhDbLKVrCZXT6q+fgUyDw1V6xjVS/RgGT+afE=
---
![TR: Logo](../../../en/adapterref/iobroker.upnp/admin/upnp-discovery.png)

![TR: Number of Installations](http://iobroker.live/badges/upnp-stable.svg)
![TR: Logo](http://img.shields.io/npm/v/iobroker.upnp.svg)
![TR: Image](https://travis-ci.org/Jey-Cee/ioBroker.upnp.svg?branch=master)

TR: # ioBroker.upnp
TR: 1. [Deutsch](#german_description)
TR: 	 * [Was ist UPnP?](#was-ist-upnp)
TR: 	 * [Funktionsbeschreibung](#funktionsbeschreibung)
TR: 	 * [Objektstruktur](#objektstruktur)
TR: 	 * [Allgemeine Objekte](#allgemeine-objekte)
TR: 	 * [Upnp Objekte](#upnp-objekte)
TR: 	 * [Steuerung](#steuerung)
TR: 	 * [Geräte/Dienst Spezifische Besonderheiten](#gerätedienst-spezifische-besonderheiten)

TR: 2. [English](#english_description)
TR: 	* [What is UPnP?](#what-is-upnp)
TR: 	* [Functional description](#functional-description)
TR: 	* [Object structure](#object-structure)
TR: 	* [General Objects](#general-objects)
TR: 	* [Upnp Objects](#object-structure)
TR: 	* [Control](#control)
TR: 	* [Devices/Service Specific Features](#devicesservice-specific-features)

TR: 3. [Changelog](#changelog)

TR: ## German Description
TR: ### Verwendungszweck
TR: Dient der Kommunikation und Interaktion mit allen UPnP-Fähigen Geräten.

TR: #### Was ist UPnP?
TR: UPnP = Universal Plug and Play. Ist der versuch eine Standardisierung der Kommunikation zwischen Geräten im Netzwerk herzustellen.
Dazu gibt es sogenannte „Schemas“, diese werden in form einer xml Datei dargestellt. Sie enthalten alle Information über das Gerät oder die Software und deren Dienste die sie bereit stellen. Damit diese Dienste auch Nutzbar sind, wird auch eine Beschreibung zu jedem Dienst mitgeliefert. Diese Beschreibung folgt dem für den Dienst festgelegten Schema, dadurch können schnell Informationen und Befehle ausgetauscht werden ohne das es nötig ist zu wissen um welches Modell oder von welchem Hersteller das Gerät oder die Software ist.  In der Vergangenheit wurde diese Standardisierung vor allem für Mediengeräte und Software genutzt. Seit einiger Zeit gibt es Bestrebungen auch die Kommunikation des „IoT – Internet of Things“ mit dieser Standardisierung zu vereinheitlichen.
Dazu wurde 2016 die „Open connectivity Foundation“ gegründet, diese übernimmt die Aufgaben des UPnP-Forums, welches die Zertifizierung von UPnP-Fähigen Geräten durchgeführt und Standards erstellt hat.

TR: #### Funktionsbeschreibung
TR: Der Adapter führt beim ersten Start einen Broadcast durch und Wertet die Antworten aus. Die Antworten enthalten den Link zu den xml Dateien der Dienste. Anhand der xml Dateien werden die Objekte in ioBroker erzeugt und mit allen verfügbaren Informationen befüllt.

TR: Zeitverzögert wird ein Dienst gestartet der auf Nachrichten von Geräten/Diensten wartet die sich an- oder abmelden. Neu erkannte Geräte/Dienste werden automatisch zu den vorhandenen hinzugefügt. Ein zweiter Dienst meldet sich bei jedem verfügbaren Gerät an und Abonniert Statusmeldungen, damit bekommt ioBroker jede Änderung (die gesendet wird) des Gerätes/Dienstes automatisch mitgeteilt.

TR: #### Objektstruktur
TR: Jedes Gerät oder Software die auf den Broadcast reagiert wird als eigenständiges Objekt angelegt. Unterhalb dieses Objekts befinden sich alle bereitgestellten Dienste mit ihren Möglichkeiten. Die Möglichkeiten werden in 3 Kategorien (Rolle/role) eingeteilt: indicator.state, action und argument.

TR: **state –** ist eine Variable die den Aktuellen zustand eines Objekts/Datenpunkts im Gerät/Dienst darstellt. Jeder indicator.state hat einen bestimmten Type wie number, string, boolean,…. Darüber hinaus ist auch genau festgelegt welchen Wert oder Wertebereich der inidcator.state haben kann, diese Angaben sind im „native“ eines Objekts hinterlegt.
Bisher implementierte native’s:

TR: -	sendEvents		= Bedeutung bis jetzt Unbekannt.
TR: -	allowedValues		= Strings die Akzeptiert werden.
TR: -	minimum			= Gibt den niedrigsten Zahlen wert an der Akzeptiert wird.
TR: -	maximum			= Gibt den höchsten Zahlen wert an der Akzeptiert wird.
TR: -	step			=  Gibt an in welchen Schritten ein Wert verändert werden kann.

TR: **button –** "request" ist ein Befehl der an das Gerät/den Dienst geschickt werden kann und von diesem Aktzeptiert wird. Dieses Objekt hat im Regelfall ein Unterobjekt, das argument.

TR: **argument –** ist ein Unterobjekt von einer Aktion-Channel. Der Type ist „gemischt“ da er nicht vorgegeben wird. In den native’s des Objekts finden sich verschiedene Informationen, sie können von argument zu argument anders sein.
Bisher bekannte native‘s:

TR: -	direction 		=  	Gibt die Richtung an in der der Informationsfluss statt findet.

TR: „In“ bedeutet es wird kein Wert zurück geliefert.
„Out“ bedeutet es wird ein Wert zurück geliefert.

TR: -	relatedStateVariable	= 	Gibt den indicator.state an der für den Austausch der Daten

TR: 					Zuständig ist.

TR: -	argumentNumber		= 	Gibt an das wievielte Argument der Action es ist.

TR: ### Allgemeine Objekte
TR: Die folgenden Objekte finden sich für jedes Gerät/jeden Dienst und werden zur Verwaltung benötigt. Sie sind nicht Bestandteil des UPnP Standards oder der Geräte-/Dienstbeschreibung des jeweiligen Gerätes.

TR: **Alive –** wird vom Gerät/Dienst auf „true“ gesetzt und vom Adapter nach x Sekunden auf „null“ gesetzt, wenn das Gerät/Dienst diesen nicht wieder auf „true“ setzt. Die Ablauf zeit ist abhängig davon welche maximal Lebensdauer vom Gerät für das Alive signal mitgeteilt wurde. Wenn ein Gerät sich abmeldet wird der Status auf „false gesetzt. Es ist möglich dieses Objekt von Hand oder per Skript auf „true“ zu setzen, das sollte jedoch nur gemacht werden wenn man sicher ist dass das Gerät/Dienst erreichbar ist. Wenn Alive manuell auf „true“ gesetzt wurde sollte es auch manuell auf „false“ gesetzt werden wenn nicht mehr nötig, da andernfalls Fehler auftreten können.

TR: **Sid –** Dient als identifikation der Subscription. Diese sid wird jedesmal vom host erzeugt wenn eine Subscription von einem client angefordert wird. Die sid läuft nach einer vom host definierten Zeit ab, daher wird sie immer wieder Aktualisiert. Sie gilt nur für einen bestimmten Dienst.

TR: **request –** sendet einen SOAP request mit den gegebenen Optionen

TR: ### UPnP Objekte
TR: Die hier auf gelisteten Objekte finden sich im UPnP Standard und/oder den Geräte-/Dinestbeschreibungen. Es handelt sich hier nicht um eine Vollständige liste aller Objekte, diese Auswahl an Objekten stellt lediglich häufig vorkommende Objekte dar.

TR: **(A_ARG_TYPE_)InstanceID –** Die InstanceID ist am Häufigsten zu finden und wird zwingend benötigt da sie die Instanz eines Dienstes angibt der angesprochen werden soll. In den meisten fällen ist die InstanceID = 0. Diese ID wird bei jeder Event message von einem Dienst und jedem Befehl der an einen Dienst gesendet wird, mit übergeben.

TR: **(A_ARG_TYPE_)Channel(*) –** Das Channel Objekt findet sich im Zusammenhang mit Audio/Video Diensten. Ein Channel muss zum Beispiel angegeben werden wenn die Lautstärke verändert werden soll. Mögliche Werte können Beispielsweise „Master“, „LF“ oder „RF“ sein. In diesem Beispiel steht „Master“ für die Allgemeine Lautstärke, „LF“ für links vorne und „RF“ für rechts vorne. Wenn jetzt die Lautstärke nur rechts vorne verändert werden soll, gibt man „RF“ bei Channel an.

TR: **(Set/Get)Volume(*) –** Das Volume Objekt findet sich im Zusammenhang mit Audio/Video Diensten. Je nachdem wo es vorkommt wird es zum Anzeigen der Lautstärke genutzt oder zum einstellen der Lautstärke. Dieses Objekt hat immer einen Mindestwert und einen Maximalwert den man angeben kann, in den meisten fällen liegt der Wertebereich zwischen 0 und 100. Die Schrittweite liegt normal bei 1, das bedeutet es können nur glatte Zahlen angegeben werden.

TR: ### Steuerung
TR: **button –** "request" Eine Action stellt einen Befehl dar, der an das Gerät/den Dienst geschickt werden kann. Zu jeder Action gehören auch Argumente, die Zwingend angegeben werden müssen. Action’s erkennt man an ihrer Rolle/role, dort steht „action“. Beschreibt man die Action mit „send“ wird der Befehl an das Gerät/den Dienst gesendet.

TR: **state.argument.x –** Muss zwingend bei einer Action angegeben werden, wenn unter Rolle "state.argument.in" ist. Mögliche Werte die angegeben werden können/müssen findet man in der „Related State Variable“. Der name dieser „Related State Variable“ ist im Objekt unter „native“ -> „relatedStateVariable“ hinterlegt.  Die Argumente müssen in einer bestimmten Reihenfolge angegeben werden, hierzu gibt es „native“ -> Argument_No. Ein Argument erkennt man an seiner Rolle/role, dort steht „argument“.  Manche strings müssen mit einem „““ in den Datenpunkt geschrieben werden. Es kann nicht pauschal beantwortet werden wann das der Fall ist, aber bei komplexen strings wie zum Beispiel URL’s kann das der Fall sein. Hier hilft nur ausprobieren. Will man ein " in einem Argument übergeben muss man "&quot;" verwenden.

TR: **(Related State) Variable –** Es handelt sich um Variablen die für den Datenaustausch genutzt werden. In den Native‘s der Variablen finden sich verschiedene Informationen:

TR: -	allowedValues = gibt Auskunft über die möglichen Inhalte der Variable oder was als Argument mit einer Action gesendet werden kann.
TR: -	minimum = der niedrigste Wert den die Variable enthalten kann oder als Argument mit einer Action gesendet werden kann.
TR: -	maximum= der höchste Wert den die Variable enthalten kann oder als Argument mit einer Action gesendet werden kann.
TR: -	step = gibt an in welchen Schritten ein Wert angegeben wird.
TR: -	sendEvents = ? Mögliche Werte sind „yes“ oder „no“. Es ist aber völlig unklar was das zu bedeuten hat. Die Annahme dass die Werte für diese Variable nur dann von einem Gerät/Dienst automatisch gesendet werden wenn „yes“ bei sendEvents steht hat sich nicht bestätigt.

TR: Beispiel, wie man die Werte pollen kann:

```
// get every 10 seconds the values from device
schedule("*/10 * * * * *",  function () {
   setState( "upnp.0.FRITZ!Box_6590_Cable.WANDevice.WANCommonInterfaceConfig.GetCommonLinkProperties.request"/*GetCommonLinkProperties*/, true);
   setState( "upnp.0.FRITZ!Box_6590_Cable.WANDevice.WANCommonInterfaceConfig.GetAddonInfos.request"/*GetAddonInfos*/, true);
});
```

TR: Es gibt auch die Möglichkeit bei dem "request" Objekt das Polling im Admin einzustellen. Dafür Klickt man auf das Schraubenschlüssel Symbol bei dem Objekt.

TR: ### Geräte/Dienst Spezifische Besonderheiten
TR: **Sonos:** Für QPlay ist es nicht möglich eine Subscription zu erstellen. Möglicherweise ist hierfür eine Autentifikation notwendig

TR: **Phillips Hue Bridge 2:** Die implementierung des UPnP Standards in der Hue Bridge 2 ist Fehlerhaft, weshalb die Hue Bridge 2 zwar gefunden wird jedoch nicht via UPnP ansprechbar ist.

TR: **Yamaha:** Verwendet eine auf dem UPnP Standard basierende API, die jedoch ein eigenes Datenformat verwendet. Derzeit wird das vom UPnP Adapter nicht unterstützt.

TR: **Sony:** Verwendet eine ScalarWebApi genannte Schnittstelle die über UPnP ansprechbar ist jedoch ein eigenes Daten Format verwendet. Derzeit wird das vom UPnP Adapter nicht unterstützt.

TR: **Amazon Kindle:** Stellt einen UPnP Dienst bereit, jedoch wird keine UPnP-Dienstbeschreibung geliefert und kann daher nicht genutzt werden.

TR: ## English Description
TR: ***Translation by https://www.deepl.com/translator***

TR: ### Intended use
TR: Serves for communication and interaction with all UPnP-capable devices.

TR: #### What is UPnP?
TR: UPnP = Universal Plug and Play. The attempt to standardize communication between devices on the network. For this purpose there are so-called "schemas", which are displayed in the form of an xml file. They contain all information about the device or the software and its services that they provide. To ensure that these services can also be used, a description of each service is provided. This description follows the scheme defined for the service, allowing information and commands to be quickly exchanged without knowing which model or manufacturer the device or software is. In the past, this standardization was mainly used for media devices and software. For some time now, efforts have also been made to standardize the communication of the "IoT - Internet of Things" with this standardization. For this purpose, the "Open connectivity Foundation" was founded in 2016, which takes over the tasks of the UPnP forum, which has carried out the certification of UPnP-capable devices and created standards.

TR: #### Functional description
TR: The adapter broadcasts and evaluates the responses at the first start. The answers contain the link to the xml files of the services. The xml files are used to create the objects in ioBroker and fill them with all available information.

TR: Time delayed a service is started which waits for messages from devices/services which log on or off. Newly detected devices/services are automatically added to the existing ones. A second service logs in to each available device and subscribes to status messages, so that ioBroker is automatically notified of any changes (sent) to the device/service.

TR: #### Object structure
TR: Each device or software that reacts to the broadcast is created as a separate object. Below this object you will find all available services with their capabilities. The possibilities are divided into 3 categories (role/role): indicator. state, action and argument.

TR: **state -** is a variable representing the current state of an object/data point in the device/service. Each indicator.state has a certain type like number, string, boolean,..... In addition, it is also specified exactly what value or range of values the inidcator. state can have, these details are stored in the "native" of an object. Previously implemented native' s:

TR: - 	sendEvents 		= Meaning until now Unknown.
TR: - 	allowedValues 	= strings that are accepted.
TR: - 	minimum 		= Gives the lowest value at which the value is accepted.
TR: - 	maximum 		= Gives the highest value at which the acceptance is made.
TR: - 	step 			= Specifies in which steps a value can be changed.

TR: **button -** "reuqest" is a command that can be sent to and accepted by the device/service. This object usually has a subobject, the argument.

TR: **argument -** is a sub-object of an action. The type is "mixed" as it is not specified. The native's of the object contain different information, they can be different from argument to argument. Previously known native' s:

TR: - 	direction 		= Indicates the direction in which the information flow takes place. In "means that no value is returned. 					Out "means that a value is returned.
TR: - 	relatedStateVariable 	= Returns the indicator. state at which the exchange of data is responsible for.
TR: - 	argumentNumber 		= Returns the number of arguments of the action it is.

TR: ### General objects
TR: The following objects are found for each device/service and are required for administration. They are not part of the UPnP standard or the device/instruction manual of the respective device.

TR: **Alive -** set to "true" by the device/service and set to "null" by the adapter after x seconds if the device/service does not set it to "true" again. The expiration time depends on the maximum lifetime of the Alive signal given by the device. When a device logs off, the status is set to "false". It is possible to set this object to "true" by hand or script, but this should only be done if you are sure that the device/service is reachable. If Alive has been set manually to "true", it should also be set manually to "false" if not necessary anymore, otherwise errors may occur.

TR: **Sid -** Serves as an identification of the subscription. This page is created by the host each time a subscription is requested from a client. The sid runs after a time defined by the host, so it is updated again and again. It is only valid for a particular service.

TR: ### UPnP Objects
TR: The objects listed here can be found in the UPnP standard and/or the device/dinest-descriptions. This is not a complete list of all objects, this selection of objects represents only frequently occurring objects.

TR: **(A_ARG_TYPE_)InstanceID -** The instanceID is the most common and is required because it specifies the instance of a service to be addressed. In most cases, the instanceID is = 0. This ID is passed with every event message by a service and every command that is sent to a service.

TR: **(A_ARG_TYPE_)Channel (*) -** The channel object is associated with audio/video services. For example, a channel must be specified if you want to change the volume. Possible values can be, for example,"Master","LF" or "RF". In this example,"Master" stands for the general volume,"LF" for the left front and "RF" for the right front. If you want to change the volume only on the right front panel, you have to specify "RF" in Channel.

TR: **(Set/Get)Volume (*) -** The Volume object is associated with audio/video services. Depending on where it occurs, it is used to display the volume or to adjust the volume. This object always has a minimum and a maximum value that can be specified, in most cases the range of values is between 0 and 100. The step size is normally 1, which means that only even numbers can be entered.

TR: ### Control
TR: **button -** "request" action is a command that can be sent to the device/service. Each action also includes arguments that must be specified as mandatory. Action's can be recognized by its role/role, which says "action". If you describe the action with "send" the command is sent to the device/the service.

TR: **state.argument.x -** Mandatory for an action, if role is "state.argument.in". Possible values that can/must be specified can be found in the "Related State Variable". The name of this "Related State Variable" is stored in the object under "native" -> "relatedStateVariable". The arguments must be given in a certain order, for this there is "native" -> Argument_No. An argument can be recognized by its role/role, where it says "argument". Some strings have to be written with a """" in the data point. It is not possible to answer this question in a flat-rate way, but with complex strings like URL's this can be the case. It only helps to try it out. If you want to pass a " in an argument you have to use """.

TR: **(Related State) Variable -** These are variables used for data exchange. In the Native's of the variable, there is some information:

TR: -	allowedValues = gives information about the possible contents of the variable or what can be sent as an argument with an action.
TR: -	minimum = the lowest value that the variable can contain or be sent as an argument with an action.
TR: -	maximum = the highest value that the variable can contain or be sent as an argument with an action.
TR: -	step = indicates in which steps a value is specified.
TR: -	sendEvents = ? Possible values are "yes" or "no". But it is completely unclear what that means. The assumption that the values for this variable are only sent automatically by a device/service if "yes" is set at sendEvents has not been confirmed.

TR: Example how to poll the values:

```
// get every 10 seconds the values from device
schedule("*/10 * * * * *",  function () {
   setState( "upnp.0.FRITZ!Box_6590_Cable.WANDevice.WANCommonInterfaceConfig.GetCommonLinkProperties.request"/*GetCommonLinkProperties*/, true);
   setState( "upnp.0.FRITZ!Box_6590_Cable.WANDevice.WANCommonInterfaceConfig.GetAddonInfos.request"/*GetAddonInfos*/, true);
});
```

TR: You can enable polling in admin via objects configuration.

TR: ### Devices/Service Specific Features
TR: **Sonos:** It is not possible to create a subscription for QPlay. This may require authentication.

TR: **Phillips Hue Bridge 2:** The implementation of the UPnP standard in Hue Bridge 2 is faulty, which is why the Hue Bridge 2 is found but not accessible via UPnP.

TR: **Yamaha:** Uses an API based on the UPnP standard, but using its own data format. Currently, this is not supported by the UPnP adapter.

TR: **Sony:** Uses a ScalarWebApi interface called UPnP addressable but using its own data format. Currently, this is not supported by the UPnP adapter.

TR: **Amazon Kindle:** Provides an UPnP service, but no UPnP service description is provided and therefore cannot be used.

TR: <!-- Placeholder for the next version (at the beginning of the line):

TR: ### __WORK IN PROGRESS__ -->

## Changelog
### __WORK IN PROGRESS__
* (bluefox) added support for Admin5

### 1.0.17 (2021-02-21)
* (jey-cee) fix warning messages with js-controller 3.2.x [Github issue #63](https://github.com/iobroker-community-adapters/ioBroker.upnp/issues/63)

### 1.0.16 (2020-04-27)
* (jey-cee) fixes for js-controller 3

### 1.0.15 (2019-08-27)
* (jey-cee) make control of devices work again (including player controls)

### 1.0.14 (2019-08-04)
* (bluefox) Tried to fix error with player

### 1.0.11 (2019-03-07)
* (bluefox) Invalid characters in XML will be replaced

### 1.0.7 (2019-03-01)
Breaking change: naming was changed and command to poll has another name - "request"
* (bluefox) refactoring
* (bluefox) scheduling per action configurable from admin

### 0.3.9
* fix auto discover

### 0.3.8
* (jey-cee) changes for object name's
* (jey-cee) fix for empty USN
* (jey-cee) added simple media player controls

### 0.3.7
* (jey-cee) fixed auto discover

### 0.3.6
*(jey-cee) fixed problem with settings

### 0.3.5
* (jey-cee) added option in settings for disable auto discover

### 0.3.4
* (jey-cee) added Travis-CI Tests

### 0.3.3
* (jey-cee) try to fix bug that cause to crash the adapter when sending actions
* (jey-cee) added unsubscribe on subscription error
* (jey-cee) added sync between Arguments and the related State Variable
* (jey-cee) fixed bug when sending an action and there comes no answer

### 0.3.2
* (jey-cee) updated version number from 0.2.4 to 0.3.2

### 0.3.0
* (jey-cee) added native Argument_No for object type argument
* (jey-cee) changed state update handling for event messages, fix for A_ARG_TYPE states
* (jey-cee) added possibility for controling UPnP devices

### 0.2.4
* (jey-cee) updated npm package node-upnp-subscriptions to resolve max handler problem
* (jey-cee) added support for 2nd stage deviceList
* (jey-cee) bugfix: iobroker stops while updating a lot of objects
* (jey-cee) added handling for initial messages from devices

### 0.2.3
* (jey-cee) fixed Dead message handler
* (jey-cee) added Subscription to service (only event message handling)
* (jey-cee) when adapter stops Alive state is set to false and sid(subscription id) is cleared

### 0.2.2
* (jey-cee) added listener for Alive/Dead messages from devices
* (jey-cee) if new devices joining the network they will added automatically
* (jey-cee) replace whitespace chars in device id's on creation, because objects and sub-object with whitespace chars wasn't usable

### 0.2.1
* (jey-cee) bug fixing: corrected creation of native's and smaller Bugs

### 0.2.0
* (jey-cee) getting all xml data from UPnP devices

### 0.1.0
* (jey-cee) initial release

## License
The MIT License (MIT)

Copyright (c) 2016-2021 Jey Cee <jey-cee@live.com>

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