---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.moma/README.md
title: 无题
hash: kib0AXGWoomKdqx4mLxIEgJU6gVuZDaqYBslywZ/meE=
---
![NPM版本](http://img.shields.io/npm/v/iobroker.moma.svg)
![资料下载](https://img.shields.io/npm/dm/iobroker.moma.svg)
![安装数量](http://iobroker.live/badges/moma-installed.svg)
![稳定版](http://iobroker.live/badges/moma-stable.svg)
![依赖状态](https://img.shields.io/david/AWhiteKnight/iobroker.moma.svg)
![已知漏洞](https://snyk.io/test/github/AWhiteKnight/ioBroker.moma/badge.svg)
![NPM](https://nodei.co/npm/iobroker.moma.png?downloads=true)
![特拉维斯](http://img.shields.io/travis/AWhiteKnight/ioBroker.moma/master.svg)

<h1><img src="admin/moma.png" width="64"/>ioBroker.moma</h1>

##适用于ioBroker的moma适配器
** MoMa **是用于基于ioBroker的家庭自动化安装的** Mo **针织和** Ma **维护的适配器。
** MoMa **的目标是家庭（自动化）安装，这比在一台机器上全部运行的一台机器或少数在一个网络内进行基本负载平衡的机器要复杂得多。

它不能替代** Puppet **** Chef** ** Salt **** Ansible** 管理工具。
它们用于具有许多计算机的大型环境，并且能够远程安装软件包。 **MoMa** 仅能远程更新现有安装，无远程安装且无远程配置。

**注意力：**

使用JavaScript适配器时，当出现错误“ RangeError：超出最大调用堆栈大小”时，请将“启动时不注册所有状态”标志设置为true。<br>当您在启动时注册所有状态时，每个状态更改事件也会为JavaScript适配器生成一个事件。特别是对于Windows，此大量事件可能会成为问题。<br>另一种解决方案是增加interval0的时间值。

MoMa使用平台独立的库“ systeminformation”（https://github.com/sebhildebrandt/systeminformation）来收集有关计算机的信息。公开了许多呼叫将在计时器间隔中使用-请参阅下面的参考。

MoMa至少需要nodejs版本10。

＃＃ 安装
在ioBroker存储库“最新”中可用

选择：

npm安装iobroker.moma

在多主机环境中也可以使用-确保在安装之前选择了正确的实例。

**注意：**当前，您需要在每个从站上安装一个Admin-Adapter实例作为解决方法。
管理员适配器不需要处于活动状态！

##核心概念
仍在建设中-欢迎提出想法，建议，提示...。

论坛：https://forum.iobroker.net/topic/22026/neuer-adapter-iobroker-moma

GitHub：https://github.com/AWhiteKnight/ioBroker.moma

基本思想是为每个实例+树（moma。\ <instance-id \>）包含实例正在运行的计算机的所有信息。
+公用树（moma.meta），在该树下，每个实例都会创建一个设备\ <主机名\>，其中包含对该实例的引用和一些监视信息。
+一个用于维护的管理标签（操作系统，js-controller，适配器的更新）

＃＃ 参考
管理员tabMoMa可用于启动更新或在必要时启动重新启动。

启动时将调用库系统信息的以下功能：

*底板-有关计算机主板的信息
*机箱-有关计算机机箱的信息
* BIOS-有关计算机BIOS的信息
*系统-有关计算机制造商的信息
* cpu-有关计算机CPU的信息
* cpuFlags-可用的CPU标志
* memLayout-有关计算机内存芯片的信息
* diskLayout-有关计算机硬盘的信息

库系统信息的以下功能在间隔0（每秒默认值）中被调用：

*时间-实际时间，时区和正常运行时间
* cpuCurrentSpeed-实际cpu和核心频率
* networkConnections-实际的网络连接
* currentLoad-实际cpu负载
*流程-使用process.list作为HTML表的流程概述

库系统信息的以下功能在间隔1中被调用（默认每10秒一次）：

* mem-有关内存使用情况的信息
* cpuTemperature-cpu和核心的温度
* networkStats-网络统计信息
* fullLoad-自上次启动以来的平均负载

在间隔2（每分钟默认）中调用以下库系统信息功能：

*电池-充电状态和有关电池的信息
*用户-当前用户会话
* fsSize-有关计算机文件系统的信息
* blockDevices-连接的块设备
* fsStats-文件访问统计信息-Windows不支持
* disksIO-块设备的IO统计信息-Windows不支持

在间隔3（每小时默认一次）中调用以下库系统信息功能：

* networkInterfaceDefault-默认网络接口
* networkInterfaces-可用的网络接口
*图形-有关计算机图形卡和连接的显示器的信息
* inetLatency-根据8.8.8.8检查互联网延迟
* dockerInfo-有关docker的一般信息-在机器上需要“ adduser iobroker docker”才能正常工作
* dockerContainers-所有Docker容器的列表-在机器上需要有“ adduser iobroker docker”才能正常工作

在间隔4（每天默认）中调用以下库系统信息功能：

* osInfo-有关计算机操作系统的信息
* uuid-UUID的安装
* shell-默认系统shell-Windows不支持
*版本-已安装软件包的版本

在间隔4（每天默认）中调用以下** MoMa **函数：

*更新-检查挂起的更新并显示moma.meta。\ <主机名\>。updates中的更新量（当前仅Ubuntu，Debian，openSUSE，RedHat）
* checkIob-检查所有适配器和js-controller是否有可用更新
* checkBatteries-检查电池状态变量（当前实现的状态名称：LOWBAT，LOW_BAT）

## Changelog

### 1.2.8 (2021-03-26)
* (AWhiteKnight) eliminate warning messages (issue #52), upgrade to systeminformation lib 5.6.8
	- in systeminformation many states of currentLoad have been renamed. The old ones will be deleted and the new ones created. Have a look into the logs.

### 1.2.7 (2020-10-18)
* (AWhiteKnight) remove leading i in names that are not a number, systeminformation lib 4.27.0 

### 1.2.6 (2020-04-27)
* (AWhiteKnight) fix typo, precise error location, systeminformation lib 4.23.6 

### 1.2.5 (2020-04-12)
* (AWhiteKnight) minor bugfixing, prepare stable release 

### 1.2.4 (2020-03-20)
* (AWhiteKnight) bugfixing: issues #45 #42 #24, controller update working again 

### 1.2.3 (2019-11-06)
* (AWhiteKnight) bugfixing, code cleanup 

### 1.2.2 (2019-09-12)
* (AWhiteKnight) ioBroker adapter/controller updates for windows, issue #24 

### 1.2.1 (2019-08-12)
* (AWhiteKnight) Bugfixing on 1.2.0 

### 1.2.0 (2019-07-26)
* (AWhiteKnight) Library 'systeminformation' version 4.14.4, 
                 check for update of Adapters and JS-Controller in Interval 4,
				 dockerInfo, dockerContainers in Interval 3,
				 moma admin-tab with update buttons for os, js-controller, adapters.

### 1.1.0 (2019-05-20)
* (AWhiteKnight) Performance optimization,
				 partial fix of Issu #24,
				 Check internet latency.

### 1.0.0 (2019-05-11)
* (AWhiteKnight) First release for adapter list 'stable'.

### 0.1.0 (2019-04-18)
* (AWhiteKnight) First release for adapter list 'latest'.

### 0.0.1
* (AWhiteKnight) initial version

## License
MIT License

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

Copyright (c) 2020 AWhiteKnight