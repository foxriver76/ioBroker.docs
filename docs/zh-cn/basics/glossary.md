---
Title: Begriffserklärungen
lastChanged: 02.05.2021
translatedFrom: de
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/basics/glossary.md
title: 无题
hash: pNXghnzEUIUGnqswpze2CJ8dmBmPOIWjCZiDbzPOvVA=
---
为了使上手变得容易并使进一步的帮助更易于理解，在此说明了ioBroker中及其周围出现的最重要的术语。

* **适配器**

设备，服务或提供数据的模块或驱动程序。得益于ioBroker的模块化结构，几乎所有东西都是适配器：管理界面，可视化，脚本编写，...

* **行政**

管理适配器提供用于配置ioBroker的Web界面。这包括安装适配器，创建实例，创建和检查对象，状态，编辑脚本等等。

* **列表**

    英文术语：enum（eration）

枚举是已分组在一起的特定对象的列表。

* **块状**

借助可链接功能块，Blockly允许以图形方式组装简单的控件和脚本。不需要编程知识。

保存块式脚本后，将生成JavaScript代码，然后执行该代码。

* **CCU**

是制造商eQ-3的Homematic Smarthome Central。有2个版本，较旧的CCU1和较新的型号CCU2，以及全新的CCU3。

    CCU代表中央控制单元

使用CCU2和CCU3，可以控制所有Homematic和HomematicIP设备。 CCU1只能处理Homematic设备。
Homematic设备有无线电和有线版本（有线总线）。

* **CSS**

级联样式表。使用CSS，可以独立于内容来描述网站的表示形式。作为HTML中定义的页面结构的补充，CSS定义了页面的显示方式。

* **Cubietruck / Cubieboard 3**

单板计算机，类似于Raspberry PI / Odroid，但具有SATA接口和2GB RAM

* **设备**

    英文术语：Device

在ioBroker中，设备通常是适配器下的下一层，并将设备的所有通道和状态分组。

* **Homematic**

Homematic是由eQ-3制造并由elv分发的智能家居系统。另请参阅CCU。

* **主持人**

    主机是运行ioBroker的计算机/服务器。

在多主机模式下，有几台主机，其中一台是主机，另一台是从机

* **HTML**

超文本标记语言。页面描述语言（基于WWW），用于在Web浏览器中显示内容（文本，链接，图形，视频等）。

* **实例**

每个适配器至少有一个实例（但也可以有多个）。
使用多个实例有不同的原因。
例如，您可以使用JavaScript适配器的第二个实例进行测试，而不会出现重要脚本失败的风险，因为在发生错误的情况下，仅会影响测试实例。

大多数适配器可以启动多个实例，以便能够寻址相同类型或相同协议的多个设备。一个实例对应于主机上正在运行的进程。
示例：2个色相桥将集成到ioBroker中。由于每个适配器只能配置一个网桥，因此可以轻松创建Hue适配器的第一个实例和第二个实例，并且在适配器的相应实例中配置每个网桥。实例化还可以轻松区分数据点，因为对象结构的前面是实例名称（例如hue.0和hue.1）。

* **Javascript**

编程语言，可以在ioBroker上对所有内容进行编程，还可以对自己的脚本进行编程。

* ** js控制器**

js-controller是ioBroker的主要过程，并为所有其他模块提供了必要的中央基本功能。
它还提供对中央对象和状态数据库的访问，协调和监视所有正在运行的适配器实例和进程。如有必要，可通过js控制器重新启动适配器。

* **渠道**

通道将主题相关的状态进行分组，通常位于设备下方。每个设备可以有多个通道。

* **掌握**

主机是主机，它主要负责管理所有实例（包括从属实例！）。当主服务器终止时，从属实例也将终止。主机为所有从机提供连接的所有从机的中央对象和状态数据库。

* **多主机模式**

ioBroker的多主机模式可用于将控制任务分配给多台计算机，如果这些计算机需要特殊的接口（例如，读出地下室的电表）。此外，可以使用几台主机以平均分配负载或内存消耗。在多主机模式下，将一台主机定义为主机。所有其他人都是奴隶。主机控制所有从机，并控制实例到从机的分配。

* **节点红色**

图形化编程表面，其中可以通过简单的链接（流程）将完成的模块（节点）链接到复杂程序。

* **对象和状态**

    基本定义可以在[此处]找到

* **对象**

对象更详细地描述了状态，并提供了元信息，配置和描述。对象具有类型，例如主机，适配器，实例，枚举，设备，通道或数据点...

元数据还定义状态的数据类型，例如数字，布尔值，字符串以及状态应如何在可视化界面中显示。

* **Odroid**

与Raspberry PI相似的单板计算机。有几种具有不同硬件设备的版本。

* **解析器适配器**

通过指定所谓的文本组成的适配器，无论其来源如何。
正则表达式切出可以写成状态的部分。然后可以在脚本等中使用这些值。被进一步处理。

* **Raspberry PI**

信用卡大小的单板计算机（由Raspberry PI Foundation开发）。操作计算机所需的所有组件都位于电路板上（CPU，GPU，RAM等）。与传统计算机相比，其优势在于功耗和尺寸最小。缺点：CPU，RAM等无法交换或升级。

* **Redis**

一个无SQL数据库，可将您的数据保存在内存中，并且可以在ioBroker中用于存储状态数据。可选用于提高性能，因为写入和读取操作不需要访问硬盘驱动器，SSD或SD卡。要将Redis DB与ioBroker一起使用，必须在js-controller基本配置中指定它。

* **状态**

    看到状态或物体

* ** **

VIS适配器使您可以为ioBroker创建自己的操作和可视化界面，并将其显示在各种设备上。这些表面由可自定义的小部件和您自己的HTML代码组成，可以使用CSS更改其外观。

* **小部件**

Vis中的控件。小部件用于显示或控制状态。例如，使用根据开关状态改变其外观的按钮来打开和关闭灯。

* **州或州**

状态包含ioBroker中数据点的当前值。
此外，它还描述了时间戳，最后更改的时间以及发送者或接收者的确认。

    状态可以保存在JSON文件或Redis数据库中。

[hier]: https://github.com/ioBroker/ioBroker.docs/blob/master/docs/en/dev/objectsschema.md