---
title: What Is a Printed Circuit Board (PCB)?
excerpt: 什么是印刷电路板（PCB）？
author: Robert Keim
tags:
  - Electricity
categories:
  - Area
date: 2023-11-18 20:11:40 
---

_本文翻译自 [What Is a Printed Circuit Board (PCB)? - Technical Articles (allaboutcircuits.com)](https://www.allaboutcircuits.com/technical-articles/what-is-a-printed-circuit-board-pcb/)，作者是[Robert Keim - Author Profile on All About Circuits](https://www.allaboutcircuits.com/author/robert-keim)。__

> This FEQ (Frequent Engineering Question) gives you essential information about the most important and widespread technique for converting a theoretical circuit into a functional physical device.

这个 FEQ（常见工程问题）为您提供了将理论电路转化为功能性物理设备的最重要、最普遍技术的基本信息。

> We typically learn about, analyze, and design electrical or electronic circuits using a diagram, called a **schematic**, that consists of [component symbols](https://www.allaboutcircuits.com/technical-articles/schematic-symbols-electronic-components-passives-resistors-capacitors/) connected by lines. The symbols represent everything from basic passive components such as resistors or capacitors to sophisticated [integrated circuits](https://www.allaboutcircuits.com/video-tutorials/introduction-to-integrated-circuits/) such as [microcontrollers](https://www.allaboutcircuits.com/technical-articles/what-is-a-microcontroller-introduction-component-characteristics-component/), and the lines represent conductive pathways that allow electrical current to flow freely from one portion of the circuit to another.

我们通常使用一种称为原理图的图表来学习、分析和设计电气或电子电路，原理图由用线条连接的元件符号组成。这些符号代表了从电阻器或电容器等基本无源元件到微控制器等复杂集成电路的所有内容，而线条则代表了让电流从电路的一部分自由流向另一部分的导电通路。


> One thing that all schematics have in common is the utter inability to drive a motor, or blink an LED, or filter out noise, or do any of the other useful and interesting things that we expect electrical systems to do. A schematic is, after all, just a drawing. To actually accomplish something with a circuit, we need to translate its schematic into physical components and physical interconnections. Simple schematics can often be realized on a [breadboard](https://www.allaboutcircuits.com/textbook/direct-current/chpt-5/building-simple-resistor-circuits/), but the vast majority of circuit designs enter the physical realm in the form of a **printed circuit board**, or **PCB** for short.


所有原理图都有一个共同点，那就是完全无法驱动电机、闪烁发光二极管、滤除噪音，或做任何其他我们期望电气系统做的有用和有趣的事情。原理图毕竟只是一张图纸。要真正实现电路的功能，我们需要将原理图转化为物理元件和物理互连。简单的原理图通常可以在面包板上实现，但绝大多数电路设计都是以印刷电路板（简称 PCB）的形式进入物理领域的。



## The Structure of a PCB （印刷电路板的结构）


> A very basic printed circuit board is a flat, rigid, insulating material that has thin conductive structures adhering to one side. These conductive structures create geometric patterns consisting of, for example, rectangles, circles, and squares. Long, thin rectangles function as interconnections (i.e., the equivalent of wires), and various shapes function as connection points for components.


最基本的印刷电路板是一种扁平、坚硬的绝缘材料，一面粘有薄薄的导电结构。这些导电结构形成几何图案，如矩形、圆形和正方形。细长的矩形起到互连（即相当于导线）的作用，而各种形状的矩形（rectangles）则充当元件的连接点。



![](https://www.allaboutcircuits.com/uploads/articles/what-is-a-printed-circuit-board-pcb-rk-aac-image1.jpg)

_This is an example of a very basic PCB. This board is actually homemade; see AAC’s [guide to home PCB fabrication](https://www.allaboutcircuits.com/projects/home-pcb-fabrication/) for more information. （这是一个非常基本的 PCB 的例子。这个电路板实际上是自制的；有关更多信息，请参阅 AAC 的家庭 PCB 制作指南。）_ 


> A printed circuit board such as the example in the image has only one conductive layer. A single-layer PCB is very restrictive; the circuit realization will not make efficient use of available area, and the designer may have difficulty creating the necessary interconnections.


印刷电路板（如图片中的例子）只有一层导电层。单层印刷电路板具有很大的局限性；电路实现将无法有效利用可用面积，设计人员可能难以创建必要的互连。

加入额外的导电层可使印刷电路板更紧凑，更易于设计。与单层电路板相比，双层电路板有了很大改进，大多数应用都能从至少四层电路板中获益。四层电路板由顶层、底层和两个内层组成。(顶层 "和 "底层 "似乎不是典型的科学术语，但它们却是电路板设计和制造领域的正式名称）。

## PCB Stackup（PCB 堆叠结构）

> The **stackup** is the arrangement of conductive and insulating layers in a multilayer PCB. The following side-view diagram shows the stackup of a four-layer board.

堆叠结构是多层PCB中导电和绝缘层的排列方式。以下是一个四层板的堆叠结构的侧视图图表。

![](https://www.allaboutcircuits.com/uploads/articles/what-is-a-printed-circuit-board-pcb-rk-aac-image2.jpg)  


> The conductive material of choice is copper. Prepreg is an insulating material that is pre-impregnated (hence the name) with resin, and the core (also insulating) is similar in composition to the prepreg.  

导电材料选择铜。**预浸料（Prepreg）** 是一种预先用树脂浸渍（因此得名）的绝缘材料，**芯材（core）** （也是绝缘材料）的成分与预浸料相似。 


> I recommend that you use a four-layer structure whenever possible. A four-layer board allows you to devote one internal layer to the reference potential (i.e., ground) and another internal layer to power-supply voltages. The top, and if necessary the bottom, will be a component layer. This arrangement facilitates PCB design and also helps you to achieve improved circuit performance.

我建议您尽可能使用四层结构。四层电路板允许您将一个内部层用于参考电位（即接地），另一个内部层用于电源电压。顶层（必要时底层）为元件层。这种安排不仅方便了 PCB 设计，还有助于提高电路性能。



## Understanding PCB Features and Terminology 了解印刷电路板的特点和术语

> There’s quite a bit of specialized vocabulary that arises in discussions of printed circuit boards. This section describes physical structures found on PCBs and gives you the words that we use to identify them.

在讨论印刷电路板时会用到很多专业词汇。本节将介绍印刷电路板上的物理结构，并给出我们用来识别它们的词汇。

> - A conductive interconnection is called a **trace**, and connection points for components are called **pads** (for pins that rest on the surface of the board) and **through-holes** (for pins that are inserted into holes drilled in the board). Basic PCB design consists of arranging pads and through-holes so that components can be properly installed, and then connecting these pads and through-holes using traces.
> - Not all drilled holes are for through-hole components. We often need to transfer a signal or supply voltage from one PCB layer to another, and this is accomplished using small, conductive holes called **vias**.
> - Many PCBs also include **mounting holes**, which have a mechanical rather than an electrical function and therefore don’t need to be **plated**. The term “plating” in this context refers to conductive material that has been deposited onto the interior of a drilled hole.
> - A **copper pour** is a relatively large section of a PCB layer that is filled with conductive material. Copper pours can be used to provide a very low-resistance or low-inductance connection between components and to improve [thermal performance](https://www.allaboutcircuits.com/technical-articles/pcb-thermal-management-techniques/).
> - A PCB layer that consists entirely of one large copper pour is called a **plane** layer. We frequently use an internal layer as a **ground plane** and create ground connections by placing vias next to component pins.
> - A through-hole or via begins as a circle of copper and then becomes a hole when a drill bit passes through the circle (ideally through the _center_ of the circle). The term **annular ring** refers to the width of copper that remains after the hole has been drilled.
> - Printed circuit boards include a variety of “supplemental” information that have no role in the electrical functionality of the device. For example, **reference designators** uniquely identify components, dots indicate proper component orientation, and project titles or serial numbers help us to keep track of the many circuit boards that accumulate in a lab. We refer to this information as the **silkscreen**.

- 导电的互连被称为**走线（trace）**， 元件的连接点称为**焊盘（pads）** （位于电路板表面的引脚）和**通孔（through-holes）** （插入电路板钻孔的引脚）。基本的印刷电路板设计包括安排焊盘和通孔，以便正确安装元件，然后使用线路连接这些焊盘和通孔。
- 并非所有的钻孔都是为了通孔元件。我们经常需要将信号或供电电压从一个 PCB 层传输到另一个层，这需要使用称为**通孔（vias）** 的导电小孔来实现。
- 许多印刷电路板还包括**安装孔（mounting holes）** ，这些孔具有机械功能而非电气功能，因此不需要电镀。这里的 "**电镀 （plated）**"指的是沉积在钻孔内部的导电材料。
- **铜浇注**是在印刷电路板层的一个相对较大的区域，填充有导电材料。铜浇注可用于在元件之间提供极低电阻或低电感的连接，并改善热性能。
- 完全由一个大铜浇注层组成的 PCB 层称为**平面层** 。我们经常使用内部层作为**接地层**，并通过在元件引脚旁放置通孔来创建接地连接。
- 通孔或过孔开始时是一圈铜，当钻头穿过这圈铜时（最好穿过这圈铜的中心），就变成了一个孔。所谓**环形圈** 是指钻孔后剩余的铜的宽度。
- 印制电路板包括各种 "补充 "信息，这些信息对设备的电气功能没有任何作用。例如，参考代号可以唯一标识元件，圆点表示正确的元件方向，项目名称或序列号可以帮助我们跟踪实验室中堆积的众多电路板。我们将这些信息称为丝印。
  
![](https://www.allaboutcircuits.com/uploads/articles/what-is-a-printed-circuit-board-pcb-rk-aac-image3.jpg)



## Conclusion 结论

> I hope that this article has provided an interesting introduction to the structure and features of printed circuit boards (which, by the way, are sometimes called printed wiring boards). If there are any PCB-related topics that you would like us to cover in future articles, please let us know in the comments section below.

我希望这篇文章能为我们介绍印刷电路板（有时也称为印制电路板）的结构和特点提供一个有趣的视角。如果您希望我们在今后的文章中介绍任何与印刷电路板相关的话题，请在下面的评论区告诉我们。


