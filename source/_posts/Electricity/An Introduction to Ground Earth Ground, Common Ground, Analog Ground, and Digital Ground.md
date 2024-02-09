---
title: 接地简介： 接地、公共接地、模拟接地和数字接地
excerpt: 接地简介： 接地、公共接地、模拟接地和数字接地
author: Sal Khan
tags:
  - Electricity
categories:
  - Electricity
date: 2023-12-16 06:14:37 
---



https://www.allaboutcircuits.com/technical-articles/an-introduction-to-ground/

了解有关接地和接地符号的基础知识。并非所有的接地都是相同的。本文将讨论接地、公共接地、模拟接地和数字接地。

## 什么是接地？

在电子和电气工程中，我们习惯将电路中的一点定义为参考点。这个参考点被称为地（或 GND），其电压为 0V。电压测量是相对测量。也就是说，电压测量必须与电路中的另一点进行比较。否则，测量结果将毫无意义。

接地参考点通常由标准接地符号表示，但并非总是如此--稍后详述。参见图 1。



![](https://www.allaboutcircuits.com/uploads/articles/Davis_ground_1.jpg)

_**Figure 1.** Common ground symbol._



通常情况下，该参考点是电路中所有其他电压测量的基准点。不过，并非所有电压测量都以该参考点为基准。例如，如果您要测量电阻分压器中上电阻两端的电压，参考点就不是地。参见图 2。


![](https://www.allaboutcircuits.com/uploads/articles/Davis_ground_2.jpg)

 _**Figure 2.** Not all voltage measurements are in reference to ground._

## 接地

接地就像它的名字一样。它是通过铜、铝或铝合金等导电材料与大地相连的物理（和电气）接地。

根据美国国家电气规范 (NEC) 的定义，真正的接地由一根导电管或导电杆组成，导电管或导电杆实际插入大地的深度至少为 8 英尺。

大地提供了一个电气中性体，由于大地几乎处于无限的中性状态，因此不会受到电气波动的影响。但需要注意的是，"大地不受电气波动影响 "实际上只是一种概括。实际上，鉴于构成地球的各种变量和材料，接地是一个相当复杂的问题。而且，地球的电势确实会因为闪电击中等事件而在一些孤立的区域发生变化。遍布社区的电线杆也与大地相连。图 3 显示了连接在电线杆上的接地线。

![](https://www.allaboutcircuits.com/uploads/articles/Davis_ground_3.jpg)

 _**Figure 3.** Power poles have earth grounding wires connected to them._


电源插座上的第三个插孔（见图 4）与大地相连。



![](https://www.allaboutcircuits.com/uploads/articles/Davis_ground_4.jpg)

 _**Figure 4.** The third prong 110VAC outlet._



插座与大地的连接为测试设备与大地的连接提供了一种方式，例如，电源线上的绿色导线与设备的内部框架或底盘相连。将各种测试设备连接到接地端时，它们都连接到一个共同的接地点，因此有一个共同的参考点。您可以通过测量任意两台测试设备的接地端子之间的电阻来验证这一点。

对于用户来说，这个公共参考点就是接地引线端子。题外话：台式电脑的底盘也与接地相连。


![](https://www.allaboutcircuits.com/uploads/articles/Davis_ground_5.jpg)

 _**Figure 5.** Test Equipment provides the user with earth ground lead terminals. Original image courtesy of [cal-center.us](http://www.cal-center.us/images/products/DSO1014A_1355493755_9230.jpg). Note added by author._


遗憾的是，接地符号在电子和电气工程的许多应用中都有使用，对不同的人往往有不同的含义，因此可能会让一些初学者感到有些困惑。 例如，接地符号也被用作公共接地符号或 0V 基准。这有点误导，因为 0V 基准实际上并不与接地相连。图 6 显示了使用共地/接地符号的各种接地连接。

图 6. 使用接地符号的各种接地连接


![](https://www.allaboutcircuits.com/uploads/articles/Davis_ground_6.jpg)

 _**Figure 6.** Various ground connections using the earth ground symbol._



## 模拟和数字接地



当数字信号改变状态时，数字电路会产生尖峰电流。当模拟电路中的负载电流发生变化时，又会产生尖峰电流。


虽然有多种正确的接地技术，但在混合信号接地时，无论采用哪种接地技术，最重要的是将 "噪声较大 "的数字回流与 "噪声较小 "的模拟回流分开。这种地线分离有助于最大限度地减少或防止因地线电流而在电路中产生噪声。


这种接地电流（将其视为变化的电流）作用于接地回流路径时，会产生电压变化（请回顾欧姆定律），即噪声。您可能听说过 "噪声接地 "这个术语。这种噪声会损害本地电路中的敏感信号。接地一直是设计、系统和测试工程师面临的主要障碍。



一种可能的接地技术是所谓的 "星形 "接地，这种技术在某些情况下可能有用，但并非所有情况下都有用。这种理念的理论基础是电路中的所有电压都指向一个接地点。


图 7 描述了模拟和数字接地点的单一接地点连接。


![](https://www.allaboutcircuits.com/uploads/articles/Davis_ground_7.jpg)

 _**Figure 7.** A single point grounding for digital and analog grounds._

使用单点接地（或星形接地）的方法在纸面上看起来很不错。但在实际应用中，根据设计的复杂程度，这种方法很难实现。另一种方法是使用接地母线。


不过请记住，一般情况下并不需要将模拟接地和数字接地物理分离，因为即使设计使用单一（共享）接地平面，也可以通过适当的 PCB 布局来管理回流电流。


## 常见接地错误


三端直流电源（如图 8 所示）可能会让初学者有些困惑。该电源有一个正极 (+)、一个负极 (-) 和一个 GND（接地）端子。如前所述，接地端子（接地）与底盘相连，而底盘又与电源线内的接地线相连，最后通过三孔插座与大地相连。


![](https://www.allaboutcircuits.com/uploads/articles/Davis_ground_8.jpg)

 _**Figure 8.** DC power supply with earth ground connection (green terminal in the center). Image courtesy of [GWInstek.com](http://www.gwinstek.com/en-global/products/DC_Power_Supply/Single_Channel_DC_Power_Supplies/SPS-Series)._

初学者常犯的一个错误是在正极 (+) 和接地端子之间连接负载。这种错误的连接方式无法让电流返回其能量源（电源本身），因此不会有电流流过。正确的连接方式是在正 (+) 和负 (-) 端子之间连接负载。

## 静电放电 (ESD) Electrostatic Discharge

测试设备的接地也有助于消除静电放电（ESD）。静电放电发生在静态带电体（如您）与测试设备接触时。有些测试设备非常敏感，很容易受到静电放电事件的影响。

集成电路 (IC) 非常容易受到 ESD 事件的影响。接地垫（称为 ESD 垫）、接地椅和腕带可在接触任何敏感元件之前将您接地，从而释放您身体上的静电，为集成电路提供充分的 ESD 保护。大多数工程师和技术人员在使用印刷电路板和集成电路时还会穿上防静电夹克，以加强保护，避免损坏元件和设备。

## 接地符号

以下是设计中可能出现的一些接地符号：


![](https://www.allaboutcircuits.com/uploads/articles/Davis_ground_9.jpg)

 _**Figure 9.** General ground symbol, or earth ground ([IEEE Std 315-1975 section 3.9.1](https://www.ee.iitb.ac.in/~spilab/Tips/ansii_graphic_symbols_for_electrical_and_electronics_daigrams_1993.pdf) and [IEC 60417-5017](https://www.iso.org/obp/ui#iec:grs:60417:5017))._

![](https://www.allaboutcircuits.com/uploads/articles/Davis_ground_10.jpg)

_**Figure 10.** Low-noise ground, or functional earthing ([IEEE Std 315-1975 section 3.9.1.1](https://www.ee.iitb.ac.in/~spilab/Tips/ansii_graphic_symbols_for_electrical_and_electronics_daigrams_1993.pdf) and [IEC 60417-5018](https://www.iso.org/obp/ui#iec:grs:60417:5018))._

![](https://www.allaboutcircuits.com/uploads/articles/Davis_ground_11.jpg)

 _**Figure 11.** Safety or protective ground ([IEEE Std 315-1975 section 3.9.1.2](https://www.ee.iitb.ac.in/~spilab/Tips/ansii_graphic_symbols_for_electrical_and_electronics_daigrams_1993.pdf) and [IEC 60417-5019](https://www.iso.org/obp/ui#iec:grs:60417:5019))._

![](https://www.allaboutcircuits.com/uploads/articles/Davis_ground_12_.jpg)

 _**Figure 12.** Chassis or frame connection ([IEEE Std 315-1975 section 3.9.2](https://www.ee.iitb.ac.in/~spilab/Tips/ansii_graphic_symbols_for_electrical_and_electronics_daigrams_1993.pdf) and [IEC 60417-5020](https://www.iso.org/obp/ui#iec:grs:60417:5020))._

![](https://www.allaboutcircuits.com/uploads/articles/Davis_ground_13.jpg)

 _**Figure 13.** Common connections/potential level not specified ([IEEE Std 315-1975 section 3.9.3.2](https://www.ee.iitb.ac.in/~spilab/Tips/ansii_graphic_symbols_for_electrical_and_electronics_daigrams_1993.pdf))_

