---
local: true
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.tr-064/README.md
title: 的ioBroker.tr-064
hash: D59HzSVYkdStJaSDx6e91FA6u2/6TTOD7QeUisJd0X0=
---
![商标](../../../en/adapterref/iobroker.tr-064/media/tr-064.png)

＃ioBroker.tr-064
###信息
该适配器从AVM Fritz！Box读取主要信息，例如呼叫列表或答录机上的消息数。
基于此[AVM文档](https://avm.de/service/schnittstellen/)

###简单状态和功能
-打开/关闭2.4GHz和5GHz的wifi，
-打开/关闭访客wifi，
-重新启动Fritz！Box，
-开始WPS流程，
-重新连接互联网
-外部IP地址

###响铃（拨一个号码）
-当使用内部号码（例如** 610）时，响铃状态将使该内部电话响铃。

例如：** 610 [，超时]

-使用外部号码时，振铃状态会将您连接到该外部号码。

当拾起被叫电话时，FritzBox将呼叫外部号码，并且您的默认电话将响铃。
可以在FritsBox中配置以下默认电话：Telefonie / Anrufe / [Tab] Wahlhilfe /Wählhilfeverwenden

### ToPauseState
-值：响铃，连接，结束
-可用于在来电（响铃）或拿起电话（连接）时暂停视频播放器。
-可以对最终值进行恢复。

###存在
您可以配置要收听的设备列表。
可以由mDNS触发。使用MDNS时，不需要轮询，而且速度更快

### AB-Anrufbeantworter（答录机）
可以打开/关闭。
可以将状态cbIndex设置为应答机的地址＃。

###通话监控
呼叫监视器将为每个入站和出站呼叫创建实时状态。
如果启用了电话簿（默认），则号码将解析为“名称”。还有一个状态，指示电话正在振铃。

＃＃＃ 电话簿
-电话簿（如果启用）将用于获取呼叫者电话号码的名称。
-此外，有三种状态可解析数字或名称。如果有的话，您还将获得联系人的图像URL。

  例如：如果您设置状态电话簿。将所有3个状态都编号，则姓名，号码和图像将设置为找到的联系人。请注意，按名称搜索将首先比较完整名称，如果找不到，则使用其中的一部分。

###通话清单
输出格式：

-json
-HTML

通话清单为：

- 所有通话
- 未接来电
-来电
-外拨电话

通话次数：通话次数可以设置为0。下一个通话增加1。

html输出可以通过模板配置

###命令和命令结果状态
使用命令状态，您可以从此[文件资料](https://avm.de/service/schnittstellen/)调用每个tr-064命令。
例如

```
command = {
    "service": "urn:dslforum-org:service:WLANConfiguration:1",
    "action": "X_AVM-DE_SetWPSConfig",
    "params": {
        "NewX_AVM-DE_WPSMode": "pbc",
        "NewX_AVM-DE_WPSClientPIN": ""
    }
};
```

应该将命令状态设置为以上各行的JSON。因此{...}（不包含命令=和换行符）调用的回调将设置commandResult状态。

###启用通话监控
要使用呼叫监控功能，必须首先在AVM Fritz！Box中启用它。
要启用呼叫监控器拨盘```#96*5*```，将打开TCP / IP端口1012。要关闭端口拨盘```#96*4*```。

###预发行版本
预发布版本可在npm处使用标签dev获得。
您无法使用以下命令从ioBroker根目录安装它们：

```
npm install iobroker.tr-064@dev
iobroker upload tr-064
```

## Changelog

### 4.2.13 (2021-07-12)
* (Apollon77) Optimize for js-controller 3.3 and prevent warnings (you pot. need to delete datapoints if you still see errors, they will be recreated)

### 4.2.12 (2021-04-16)
* (Apollon77) prevent html template for calllists to be overwritten by default one
* (Apollon77) fix crash case (Sentry IOBROKER-TR-064-2M)

### 4.2.11 (2021-03-12)
* (Apollon77) fix id-reset detection for single calls

### 4.2.10 (2021-03-11)
* (Apollon77) better handle caller id resets by reboots/FW updates to also update list specific counter and log when this happened

### 4.2.9 (2021-03-10)
* (Apollon77) try to better handle calllist resets on FW updates
* (Apollon77) Make sure jsonDeviceList do not get deleted on start
* (Apollon77) Better handle not initialized calllist templates

### 4.2.8 (2021-03-09)
* (Apollon77) Optimize customized HTML templates if state is empty

### 4.2.7 (2021-03-08)
* (Apollon77) Allow customized HTML templates again

### 4.2.6 (2021-02-18)
* (Apollon77) Fix crash case (IOBROKER-TR-064-20)
* (Apollon77) Get calllists working again

### 4.2.4 (2021-02-02)
* (Apollon77) Prevent crash case (Sentry IOBROKER-TR-064-1T)

### 4.2.3 (2021-01-16)
* (Apollon77) Crash case prevented (Sentry IOBROKER-TR-064-1N)

### 4.2.2 (2020-12-25)
* (Apollon77) Crash case prevented (Sentry IOBROKER-TR-064-1K)

### 4.2.1 (2020-11-13)
* (Apollon77) try to fix pot. not working disabling commands

### 4.2.0 (2020-11-09)
* (Apollon77) Crash case prevented (Sentry IOBROKER-TR-064-15, IOBROKER-TR-064-16)
* (Apollon77) Try to solve error 500 problem with offline devices
* (SliX185) Add IPv6 states
* (foxriver76) optimizations
* (Apollon77) Fix initialization if ip/host

### 4.1.0 (2020-09-17)
* (Apollon77) Fix crash case (Sentry IOBROKER-TR-064-14)
* (bazidibavaria) added tablesort to device search
* (bazidibavaria) added Fritzbox link to admin

### 4.0.13 (2020-08-17)
* (Apollon77) Crash prevented (Sentry IOBROKER-TR-064-10)

### 4.0.12 (2020-08-06)
* (Apollon77) Crash prevented (Sentry IOBROKER-TR-064-Y)

### 4.0.11 (2020-07-26)
* (Apollon77) Crash prevented (Sentry IOBROKER-TR-064-W)

### 4.0.9 (2020-07-01)
* (Apollon77) handle cases correctly when no hosts are existing on device (Sentry IOBROKER-TR-064-R)

### 4.0.8 (2020-06-20)
* (Apollon77) Make sure states are only subscribed if initialization is done (Sentry IOBROKER-TR-064-J)

### 4.0.7 (2020-06-09)
* (Apollon77) Fix Admin UI to allow setting poll Interval correctly again

### 4.0.4 (2020-06-05)
* (Apollon77) Make sure adapter do not crash of no calls were returned (Sentry IOBROKER-TR-064-D)
* (Apollon77) Make sure adapter do not crash when invalid parameter are provided (Sentry IOBROKER-TR-064-B)
* (Apollon77) https is not supported right now (Sentry IOBROKER-TR-064-E)

### 4.0.3 (2020-05-11)
* (Apollon77) Make sure adapter do not crash of no calls were returned (Sentry IOBROKER-TR-064-7)
* (Apollon77) Make sure adapter do not crash when providing a non string to "ring" state (Sentry IOBROKER-TR-064-8) 

### 4.0.1 (2020-04-23)
* (Apollon77) handle case where no Phone deflections are available (Sentry IOBROKER-TR-064-1/2)

### 4.0.0 (2020-04-12)
* (Apollon77) update dependencies, use auto decrypt features with js-controller 3.0
* (foxriver76) make callmonitor compatible with js-controller 3.0

### 3.1.4 (2020-01-26)
* (Apollon77) fix error and check some other code check comments
* (Apollon77) Add proper meta data for buttons

### 3.1.1 (2020-01-25)
* (bluefox) Configuration dialog was improved
* (bluefox) Soef library was removed

### 3.0.0 (2020-01-24)
* (Apollon77) Switch Name back to tr064 because ewe got it from npmjs
* (maeb3) Enhance call handling and fix wrong data for currently active calls 
* (Apollon77) Remove unused state phonebook.ringing

### 2.0.3 (2019-12-17)
* (Jey Cee) fix delete last device from list

### 2.0.2 (2019-12-16)
* __requires js-controller v2__
* (foxriver76) no longer use adapter.objects
* (Apollon77) several fixes, Call lists working again, Phonebook fixed and many more

### 1.1.0 (2019-11-10)
* (jey cee) added Admin v3 support

### 1.0.0 (2019-04-01)
* (ldittmar) first version for the community

## License
The MIT License (MIT)

Copyright (c) 2015-2021 soef <soef@gmx.net>

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