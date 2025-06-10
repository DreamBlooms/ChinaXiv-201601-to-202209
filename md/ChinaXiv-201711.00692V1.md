编号：2016-0219

# 基于空气网络法的管路系统及阀门计算模型

孙科¹，刘高文¹，马春田²，牛嘉嘉¹（1、西北工业大学 动力与能源学院，陕西 西安，710072；2、东方汽轮机有限公司四川 德阳，618000)

摘要：空气网络法因其快速实用的特点，计算得到空气网络中各截面各种参数，在航空发动机空气系统的计算研究中得到广泛应用。将空气网络法的思想应用到压缩空气供应系统中，其中主要有阀门、管道、局部损失等主要元件。因原有程序中没有阀门计算方法，首先建立阀门的计算模型，通过实验得到阀门的流量特性，形成计算方法，写入空气网络程序中。设计了一种新型数据结构来表达空气网络，重新编写了面向对象语言程序。使用空气网络程序计算不同阀门开度工况下管路的流量及重要截面上的参数，并与实验值进行对比，偏差很小，从而验证计算方法的准确可信。由此得到压缩气体供应系统的空气网络模型，应用于管路系统调控中。进行空气网络计算，根据实验台所需的气体流量及状态参数得到所需阀门的开度，快速调整阀门到所需位置。

关键词：空气网络；阀门；管路系统；数据结构中图分类号：V233.5 文献标志码：A

# Calculation Model of Tube System and Value Based on 1D Network Model

SUN $\mathsf { K e } ^ { 1 }$ , LIU Gao-Wen1,MA Chun-Tian², Niu Jia-Jial (1、School of Power and Energy,Northwestern Poly-technical University, Xi'an 710o72,China;

2、DongFang turbine CO.LTD,Deyang618oo0,Chian)

Abstract: Because of its fast and practical characteristics,the 1D network model has been widely used in the research of secondary air system in engine.The 1D network model is applied to the compressed air supply system, which mainly has the main elements such as valves,tubes,losses and so on.Because there is no valve calculation methodin theoriginal program,the calculation model of the valve was established firstly,and the flowcharacteristic of the valve was obtained through the experiment,then the calculation method formed.A new data structure is designed to expressthe air network,and the object oriented programming language is recompiled. Using 1D network program to calculate the flow rate and the parameters of the main section of the system under diferent valve opening conditions,and the experimentalresults are compared withthe computational results,the deviation is very small,so as to verify the accuracy of the calculation method. Calculation model of compressed air supply system which is applied to control the supply system. Get the required opening of valve which control system to provide suitable compressed air for experiment. So fastly adjust opening in experiment.

Key words: Network model; Value; Tube-System; Data structure

# 0引言

压缩空气是航空发动机工作中必不可少的工质，同时也是模拟实验中的工质。实验室中，压缩空气供应系统为实验台供给所需质量、品质的空气。空气供应系统的设计，应该减小气流损失，并且准确无误为实验台服务。而阀门作为管路系统中调节气流的关键元件，有十分重要的作用。调节阀门的开度，得到气流在系统中的不同状态。通过空气网络计算得到阀门需要打开的开度，从而迅速调整到位。因此压缩气体供应系统的空气网络计算较有意义。国内外学者应用空气网络法进行了很多的研究，大部分研究是将网络法应用于发动机空气系统中。Yannick[1]等通过开源软件CalculiX $\textsuperscript { \textregistered }$ 进行喷气发动机二次空气系统模型综合热机械分析，模拟二次空气系统中流动特性及热结构特性的综合作用效果。Benra[2]等使用一维空气网络模型模拟预旋系统中的流动状态。一维计算的结果与数值计算结果和实验结果进行了对比。吴丁毅提出了关于内流系统流动换热的网络计算法，计算稳定性和收敛性较好。侯升平等开发了用于模拟发动机空气系统非稳态特性的程序。郭晓杰[5考虑空气系统流体特性(温度、压力与流量)和固体部件热力特性(温度分布)之间的相互作用，将空气系统计算与固体部件热分析结合起来，建立航空发动机空气系统与固体部件之间的稳态流-热耦合分析平台。吕亚国开发了发动机空气系统通用分析软件，软件前台采用图形建模方式生成网络计算模型，后台采用了网络自动识别技术。胡肖肖7等借助概率思想建立相应的计算连续性方程和能量方程，建立相应的随机游动模型，运用蒙特卡罗方法求解各节点的压力，再根据流量与元件两端压力的关系，计算流经各元件的流体流量，结果与Flowmaster 进行了对比，吻合较好。潘耘峰8以某型航空发动机为例，得到主要元件的计算方法，并建立空气网络模型。同时有很多研究，将空气网络法应用于其它工作中。陆霄露将一维计算方法应用于内燃机性能仿真，并开发了仿真软件。张光鹏、许诺等[0]应用Flowmaster对某一空调系统进行了数值模拟，结果表明Flowmaster对暖通空调设计有着积极地指导意义。

本文将空气网络法应用于压缩气体供应系统中，建立阀门的模型，通过实验得到特性参数，代入空气网络程序中。进行空气网络计算，结果与实验结果进行对比。通过空气网络计算可快速得到管道中重要截面的气流参数。

# 1空气网络及计算方法

# 1.1空气网络模型

根据某实验室压缩气体供应系统中管道、阀门的布置，简化得到相应的空气网络模型。图1为某实验室压缩气体供应系统的空气网络模型，该空气网络模型中有一个进口、一个出口，六个腔室，十个分支。I1 为进口(Inlet)，I2 为出口(Outlet)。C1-C6为6个腔室(Chamber)，E1-E43 为元件(Element)。网络中有管元件(Tube)、局部损失元件(Partloss)、阀门元件(Value)这三种，共有43个元件。表1所列为空气网络中各个分支的元件数量和分支的进口、出口。

![](images/e9691136fafd2e72f083c15b646cd961ec15c1c600a2bbd8c4e4259a8622ef43.jpg)  
图1.一维空气网络模型  
Fig1.1D network model

这些元件的流阻和传热特性计算模型和计算方法的建立可借助理论推导、已有实验数据和参考文献等，并通过将计算结果与已有实验数据进行对比来对计算模型和方法进行改进和完善。其中管元件[、局部损失元件[12][13]的计算方法在已有的空气网络程序中已经存在，经过多次使用，已经得到了验证。本文建立阀门元件的计算方法，根据实验得到实验室所采用阀门的流动特性，之后计算方法写入到空气网络程序中，进行整个空气网络模型的工程计算。

表1网络中的分支  

<html><body><table><tr><td colspan="4">Table1.Branchs in network model</td></tr><tr><td>ID ofbranch</td><td>Number of elements</td><td>Branch's inlet</td><td>Branch's outlet</td></tr><tr><td>1</td><td>3</td><td>I1</td><td>C1</td></tr><tr><td>2</td><td></td><td></td><td></td></tr><tr><td>3</td><td>2</td><td>C1</td><td>C2</td></tr><tr><td>4</td><td>2</td><td>C1</td><td>C2</td></tr><tr><td>5</td><td>2</td><td>C1</td><td>C2</td></tr><tr><td></td><td>2</td><td>C1</td><td>C2</td></tr><tr><td>6</td><td>7</td><td>C2</td><td>C3</td></tr><tr><td>7</td><td>7</td><td>C3</td><td>C4</td></tr><tr><td>8</td><td>9</td><td>C4</td><td>C5</td></tr><tr><td>9</td><td>4</td><td>C5</td><td>C6</td></tr><tr><td>10</td><td>5</td><td>C6</td><td>01</td></tr></table></body></html>

# 1.2元件计算方法

阀门是风洞系统中最常用的空气流量调节元件，实验室阀门调节的控制参数是开度。实验室中所采用的阀门是电力驱动阀门，单座套筒调节阀，流开型。通过阀门的流体可压缩，因此进口总压的计算存在阻塞流和非阻塞流两种情况。这里介绍三个参数： $F _ { K }$ 为比热比系数，对于空气取1，对非空气介质 ${ \cal F } _ { K } { = } k / 1 . 4$ $X$ 为阀门前后压差比，即阀门压降 $\varDelta p$ 与入口压力 $p _ { i }$ （由于管道内气体马赫数很小，动压远小于静压，因此静压近似等于总压)之比； $X _ { T }$ 为临界压差比，对于一个特定的阀门，当产生阻塞流时，其压差比是一个固定常数，对单座套筒型流开形式的取0.75。

当 $\scriptstyle \sum X _ { T } F _ { K }$ 时，出现阻塞流，进口总压计算式[14]为

$$
p _ { 1 } = \frac { Q _ { g } } { 2 . 5 8 K _ { \nu } } \sqrt { \frac { T _ { 1 } G Z } { \kappa X _ { { \scriptscriptstyle T } } } }
$$

式中 $Q _ { g }$ 气体标准状态下的体积流量， $Q _ { g } { = } m / \rho$

$m$ 为气体质量流量， $\rho$ 为气体标准状态下的密度；

$K _ { \nu }$ 为阀门的流量系数，定义是温度为 $( 5 { - } 4 0 ^ { \circ } \mathrm { C } )$ 的水在 $1 0 ^ { 5 } \mathrm { { P a } }$ 压降下，1小时内流过阀的立方米数;

$T _ { I }$ -阀门入口的绝对温度；

$G$ 气体的相对密度;

$Z .$ 压缩系数；

$k$ 绝热指数。

当 $X { < } X _ { I } F _ { K }$ 时，非阻塞流，进口总压计算式为

$$
p _ { 1 } = \frac { Q _ { g } } { 4 . 5 7 K _ { \nu } y } \sqrt { \frac { T _ { 1 } G Z } { X } }
$$

式中y—膨胀系数， $y = 1 - { \frac { X } { 3 F _ { k } X _ { T } } }$

# 1.3空气网络数据结构

大型空气网络中一般有很多元件，并且有多个进口、多个出口、多个腔室、多个分支，是非常复杂的图形结构，需要有效的组织空气网络数据结构才能使计算机轻松识别。文献[4]中通过定义各个元件的进出口节点编号，并且相邻的两个元件间，上游元件的出口节点号与下游元件的进口号严格保持一致。这种方法的原理简单，但对用户来说较为繁杂，需要特别熟悉编号规则，并且当网络中减少或增加一个元件时，几乎所有的节点序号和元件序号都需要重新定义才能保证分支中从上游到下游元件序号依次增大的顺序。为方便使用提出了一种新型的数据结构，如图2中简易的空气网络模型，以分支为单元，图中所示的分支间的有向连接可以使用如表2的二维整形数组表示，用数组元素 $\mathrm { \bf A } [ 0 ] [ 1 ] = 1$ 表示从分支1到分支2的有向连接关系，这个数组称为邻接矩阵，这是网络最顶层的数据结构。

![](images/c6c43cfc3c84d223749d726f4cf2fa1160187a72e045866111cfd7ffc7a9ee80.jpg)  
图2.网络数据结构  
Fig2.Data structure of network

# 表2网络邻接矩阵

Table 2.Network adjacent matrix   

<html><body><table><tr><td>A[I[J]</td><td>0</td><td>1</td><td>2</td><td>3</td></tr><tr><td>O(branch1)</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>1(branch2)</td><td>1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>2(branchs)</td><td>1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>3(branch4)</td><td>1</td><td>0</td><td>0</td><td></td></tr></table></body></html>

具体到每个分支的数据结构，如图3所示，每个元件中有pnext和plast两个指针将不同元件串联起来，组成双向链表。通过面向对象编程中类继承[的思想将标准类派生为不同元件类，从而不同类型元件能够组成一个线性链表。只需按照顺序输入各个元件的输入参数，无需对节点进行编号，计算机自动识别并且生成链表。

![](images/cde5553cdea4ba88569c7a9aef4172d537a70043a31bbb96ef99d57c6672b9eb.jpg)  
Fig 3.Data structure of branch

具体到每个元件的数据结构，如图4所示，每个元件类中有函数成员和数据成员，而元件计算函数Calelement(...)从标准类中派生而来，因而在代码编写时，不同元件计算只需调用这一个函数即可。另外由于数据成员也定义在类中，在程序调试过程中方便监测元件进出口参数的变化，而原有数据结构中，因为不同气动参数定义在不同数组中，通过节点序号索引该元件参数，在调试过程中需要反复切换数组。另外链表这样的数据结构对内存空间的节省使用也十分有利。

![](images/a9cf9df47021a91d07735cad59b5ebe4d2285cec6f7d685e6f90d8c9afc74bb7.jpg)  
图3.分支数据结构  
图4.元件类Fig 4.Classof element

# 2实验室阀门流动特性实验

# 2.1实验条件、测量技术

实验室所用的压缩空气来自螺杆空气压缩机，最大供气压力 $0 . 7 \mathrm { { M P a } }$ ，压缩气体在气罐中稳定后进入管路系统。

压力测量采用压力变送器。测量范围0-1MPa，精度等级0.2级。传感器显示屏输出压力示数，另外传感器输出 $4 { - } 2 0 \mathrm { m A }$ 电流信号，经信号隔离器转换成1-5V电压信号，电压信号由研华4711A板卡采集进入工业控制计算机中。温度测量技术介绍，温度测量采用K型热电偶，量程-40— $1 3 5 0 ^ { \circ } \mathrm { C }$ 。流量测量技术介绍，流量测量使用标准孔板节流装置配合差压变送器、压力变送器、热电偶组成。差压便送器精度等级0.1。使用差压变送器测量得到孔板前后压差△P，压力变送器测得孔板前压力，热电偶测量得到气流温度。

# 2.2阀门流动特性实验

实验室采用的电动阀为单座套筒阀，流开形式。该电动阀的流量特性需由实验得到。实验中，电动阀门前后各有一个压力传感器，在阀门上游处布置K型热电偶，下游有孔板流量计。

由式(1-a)得，当 $\mathrm { X { \geq } X _ { I } F _ { K } }$ 时，出现阻塞流，流量系数的表达式为

$$
K _ { \nu } = \frac { Q _ { g } } { 2 . 5 8 p _ { 1 } } \sqrt { \frac { T _ { 1 } G Z } { \kappa X _ { \scriptscriptstyle T } } }
$$

由式(1-b)得，当 $\mathrm { X } { < } \mathrm { X } _ { \mathrm { T } } \ \mathrm { F } _ { \mathrm { k } }$ 时，非阻塞流，流量系数的表达式为

$$
K _ { \nu } = \frac { Q _ { g } } { 4 . 5 7 p _ { 1 } y } \sqrt { \frac { T _ { 1 } G Z } { X } }
$$

# 表3.量纲分析

Table 3.Dimensional analysis   

<html><body><table><tr><td>Symbol</td><td>Result</td><td>Symbol</td><td>Result</td></tr><tr><td>Qg</td><td>LT1</td><td>k</td><td>dimensionless</td></tr><tr><td>P1</td><td>MTL1</td><td>XT</td><td>dimensionless</td></tr><tr><td>T</td><td></td><td>y</td><td>dimensionless</td></tr><tr><td>G</td><td>dimensionless</td><td>X</td><td>dimensionless</td></tr><tr><td>Z</td><td>dimensionless</td><td></td><td></td></tr></table></body></html>

流量系数表达式右端参数有量纲，现对流量系数的量纲进行分析。对式(2-a)和(2-b)中等式右边的参数量纲分析结果如表3。由表3量纲分析结果及式(2-a)

和(2-b)分析得流量系数的量纲为 $L ^ { 4 } T ^ { - 3 } M ^ { - 1 } \theta ^ { \frac { 1 } { 2 } }$

阀门不同开度下，流量系数值不同。实验中，根据阀门前后压力、通过阀门的流量、阀门前气流温度，便可计算得到阀门不同开度下，对应的流量系数值。

# 3空气网络计算结果与实验对比

# 3.1阀门流动系数特性曲线

阀门流动特性主要随开度变化，本文做了气源压力0.7MPa、0.5MPa、0.35MPa这三组实验。如图5为实验结果，图中3条曲线分别为3个不同气源压力时的流量系数曲线。三条曲线相近且符合阀门的等百分比特性曲线。根据不同气源压力下各开度对应流量系数的平均值得到表达式 $\mathrm { y } { = } 1 5 7 . 4 8 0 \mathrm { x } ^ { 2 } { + } 4 5 . 9 1 5 \mathrm { x } { + } 7 . 0 0 2$ 代入程序计算。

![](images/e11835c113d9efcfdb7328478873ed27fea453b95608ae436525448b477d6550.jpg)  
图5.阀门流量系数

# 3.2网络计算结果与实验对比

对管路的空气网络建模计算中，调整阀门的开度，形成不同的管路工况。针对不同的工况，编写空气网络程序输入文件，并进行计算。

首先是气源压力为 $0 . 7 \mathrm { M P a }$ (表压力)，branch5中电动阀门的开度为0.15时的工况。如图6为空气网络程序计算结果与实验测量值的对比。使用计算与实验值相对偏差衡量计算准确性，相对偏差的定义为计算值与实验值差的绝对值与实验值之比。实验测得网络中四个点的压力，计算与实验值的对比，最大偏差 $3 . 2 \%$ 最小偏差 $0 . 2 \%$ 。计算所得的流量值与实验测量结果偏差 $4 . 1 \%$ 。

![](images/88541957a1dd377431814233fb8761d51c2f2f7614b733b1484102789ef502a7.jpg)  
图6.沿程压力(气源 $0 . 7 \mathrm { M P a } )$ 号 Fig 6.Pressure along the way(0.7MPa)

其次是气源压力为 $0 . 7 \mathrm { { M P a } }$ (表压力),branch5中电动阀门的开度为0.8时的工况。如图7为空气网络程序计算结果与实验测量值的对比。在阀门处的压力损失比开度为0.15时小，计算所得的压力值与实验值的对比，最大相对偏差 $0 . 6 \%$ ，最小相对偏差 $0 . 1 \%$ 。计算所得的流量值与实验测量结果相对偏差 $3 . 9 \%$ 0

![](images/74fc2dfdaa71ceb65d59d4e78d59a3b276f5f24ca9a237f0c898c7553a3ef386.jpg)  
Fig 5.Discharge coefficient of value   
图7.沿程压力(气源0.7MPa) Fig7.Pressure along the way(0.7MPa)

其次是气源压力为 $0 . 5 \mathrm { { M P a } }$ (表压力)，branch5中电动阀门的开度为0.8时的工况。如图8为空气网络程序计算结果与实验测量值的对比。计算所得的压力值与实验值的对比，最大偏差 $2 . 3 \%$ ，最小偏差 $0 . 4 \%$ 。计算所得的流量值与实验测量结果偏差 $6 . 9 \%$ 。

# ChinaXiv合作期刊

![](images/012ee4245ca322d13321e230eef725d55cbae9cdd73f0b6ac5256b2dfbf2a6c7.jpg)  
图8.沿程压力(气源0.5MPa) Fig 8.Pressure along the way(0.5MPa)

如表4为气源压力 $0 . 7 \mathrm { M P a }$ 时，阀门不同开度工况下计算流量值与实验结果的对比，开度0.2工况下相对偏差最大，为 $1 0 . 4 7 \%$ ，这是因为小开度下流量值小，较小的计算偏差就会造成较大的相对偏差，并且实验中流量测量存在一定的误差，管路中较少量气流泄漏至环境中。

Table 4.Comparision of flow rate(O.7MPa)   

<html><body><table><tr><td>Value</td><td>Result of exp(kg/s)</td><td>Result of 1D network(kg/s)</td><td>Relative deviation</td></tr><tr><td>0.1</td><td>0.555</td><td>0.566</td><td>2.13%</td></tr><tr><td>0.2</td><td>0.900</td><td>0.995</td><td>10.47%</td></tr><tr><td>0.3</td><td>1.334</td><td>1.360</td><td>1.96%</td></tr><tr><td>0.4</td><td>1.617</td><td>1.704</td><td>5.39%</td></tr><tr><td>0.5</td><td>1.886</td><td>1.956</td><td>3.74%</td></tr><tr><td>0.6</td><td>1.977</td><td>2.141</td><td>8.30%</td></tr><tr><td>0.7</td><td>2.095</td><td>2.227</td><td>5.94%</td></tr><tr><td>0.8</td><td>2.185</td><td>2.270</td><td>3.89%</td></tr><tr><td>0.9</td><td>2.264</td><td>2.306</td><td>1.84%</td></tr><tr><td>1</td><td>2.234</td><td>2.330</td><td>4.32%</td></tr></table></body></html>

如表5为气源压力 $0 . 5 \mathrm { { M P a } }$ 时，阀门不同开度工况下计算流量值与实验结果的对比，在小开度下的相对偏差较大，开度为0.2下最大为 $12 . 2 4 \%$ 。

表5.流量对比(0.5MPa)  
Table 5.Comparision of flow rate(0.5MPa)   
Table 6.Comparision of flow rate(0.35MPa)   

<html><body><table><tr><td rowspan="2">Value</td><td rowspan="2">Result of exp(kg/s)</td><td rowspan="2">Result of 1D network(kg/s)</td><td rowspan="2">Relative</td></tr><tr><td>deviation</td></tr><tr><td>0.1</td><td>0.410</td><td>0.430</td><td>4.86%</td></tr><tr><td>0.2</td><td>0.626</td><td>0.702</td><td>12.24%</td></tr></table></body></html>

<html><body><table><tr><td>0.3</td><td>0.966 1.074 11.15%</td></tr><tr><td>0.4 1.209</td><td>1.325 9.57%</td></tr><tr><td>0.5 1.419</td><td>1.526 7.56%</td></tr><tr><td>0.6 1.519</td><td>1.655 8.96%</td></tr><tr><td>0.7 1.605</td><td>1.720 7.17%</td></tr><tr><td>0.8 1.626</td><td>1.738 6.88%</td></tr><tr><td>0.9 1.652</td><td>1.768 7.05%</td></tr><tr><td>1 1.660</td><td>1.788 7.68%</td></tr></table></body></html>

如表6为气源压力 ${ 0 . 3 5 } \mathrm { { M P a } }$ 时，阀门不同开度工况下计算流量值与实验结果的对比，小开度下的相对偏差较大，开度0.3工况条件下最大为 $1 1 . 8 \%$ 。综述所述，网络计算结果与实验测量结果相对偏差绝大部分工况下小于 $10 \%$ ，少数工况小于 $13 \%$ ，验证了空气网络模型和计算方法的准确合理。

表4.流量对比(0.7MPa)  
表6.流量对比 $( 0 . 3 5 \mathsf { M P a } )$   

<html><body><table><tr><td rowspan="2">Value</td><td rowspan="2">Result of exp(kg/s)</td><td rowspan="2">Result of 1D network(kg/s)</td><td rowspan="2">Relative deviation</td></tr><tr><td></td></tr><tr><td>0.1</td><td>0.293</td><td>0.326</td><td>11.37%</td></tr><tr><td>0.2</td><td>0.447</td><td>0.500</td><td>11.75%</td></tr><tr><td>0.3</td><td>0.671</td><td>0.750</td><td>11.80%</td></tr><tr><td>0.4</td><td>0.905</td><td>0.924</td><td>2.17%</td></tr><tr><td>0.5</td><td>1.034</td><td>1.039</td><td>0.49%</td></tr><tr><td>0.6</td><td>1.088</td><td>1.108</td><td>1.82%</td></tr><tr><td>0.7</td><td>1.161</td><td>1.176</td><td>1.30%</td></tr><tr><td>0.8</td><td>1.210</td><td>1.202</td><td>-0.69%</td></tr><tr><td>0.9</td><td>1.193</td><td>1.218</td><td>2.11%</td></tr><tr><td>1</td><td>1.219</td><td>1.228</td><td>0.72%</td></tr></table></body></html>

# 4结论

针对某实验室压缩气体供应系统，使用空气网络法对其进行研究。建立空气网络模型，通过实验完善计算方法及元件流动特性，进行空气网络一维计算。主要结论如下：

1)使用空气网络法研究压缩气体供应系统，建立专门的网络模型。空气网络中有阀门、局部损失、管道。提出新型数据结构应用于空气网络的组织，图形结构-链表-类这样的三级结构，便于用户使用，并且有利于节省计算机内存。

2)阀门元件使用一维方法计算，通过实验得到阀门的流动特性，流量系数随开度的变化曲线。并将计算方法及流量系数曲线写入空气网络程序中。

3)对整个空气网络进行一维计算，计算结果与实验测量结果进行对比。气源压力不超过0.7MPa时，压力及流量相对偏差较小，从而验证了计算方法的准确可信。针对压缩空气管路系统的一维计算模型研究有利于较为全面的了解系统流动特性，实验中对阀门进行快速调控。

参考文献   
[1]Yannick M. Secondary Air System Model For Integrated Thermomechanical Analysis Of A Jet Engine[R]. ASME Turbo Expo 2O08:Powerfor Land,Sea and Air, GT2008-50078.   
[2]Benra F K, Dohmen H J, Schneider O. Application of An Enhanced 1D Network Model To Calculate The Flow Properties of a Pre-swirl Secondary Air System[R]. ASME Turbo Expo 2008:Power for Land,Sea and Air, GT2008-50442.   
[3]吴丁毅．内流系统的网络计算法[J]．航空学报, 1996,06:16-20. WU Dingyi. Network Technique of Internal System[J]. Acta Aeronautica et Astronautica Sinica,1996,06:16-20 (in Chinese).   
[4]侯升平，陶智等．非稳态流体网络方法在发动机空气冷却 系统中的应用[J]．航空动力学报,2009,03,494-498. HOU Shengping,Tao Zhi,etal. Application of Unsteady Fluid Network to Air Cooling System in Engine[J]. Journal of Aerospace Power,2009,03,494-498 (in Chinese).   
[5]郭晓杰．航空发动机空气系统与热分析耦合方法研究[D]. 上海交通大学,2014:10-17. GUOXiaojie. Coupling Computational Approach of Secondary Air System and Heat Transfer in Aero-engine[D]. Shanghai: Shanghai Jiao Tong University2014:10-17（in Chinese) .   
[6]吕亚国，刘振侠等．航空发动机内流空气系统通用分析软 件设计[J]．计算机仿真,2009,26(7):99-103. LU Yaguo,LIU Zhenxia. General Analysis Software Design of Aeroengine Internal Air System[J]. Compuer Simulation, 2009,26(7): 99-103(in Chinese).   
[7]胡肖肖,李育隆等.基于蒙特卡罗法的航空发动机稳态空 气系统网络计算[J]．航空发动机,2014,Vol40,No.6,28-32. HU Xiaoxiao, LI Yulong. Aeroengine Steady Air System Calculation Based on Monte Carlo Method[J]. Aeroengine, 2014, Vol40,No.6,28-32(in Chinese).   
[8]潘耘峰．燃气透平冷却空气系统流体网络法研究[D].中 国科学院研究生院,2011: 53-56. PAN Yunfeng. Investigation on Fliud Network Method for The Analysis of Turbine Air Cooling System[D]. Beijing: Graduate School of the Chinese Academy of Sciences,2011: 53-56(in Chinese).   
[9]陆霄露．内燃机一维流动计算方法研究及性能仿真软件 设计[D]．上海交通大学,2014:15-25. LU Xiaoxiao. Computational Study on One-dimensional Fluid Flow and Desing of Performance Simulation Software for Internal Combustion Engine[D]. Shanghai: Shanghai Jiao Tong University,2014: 15-25(in Chinese).   
[10]张光鹏,许诺,张武平.FLOWMASTER 在暖通空调中的 应用[J]．制冷与空调,2006,No.03:34-36. ZHANG Pengguang, Xu Nuo, Zhang Wu-ping. Application of FLOWMASTER in HVAC[J]. Refrigeration & AirCondition,2006,No. 03: 34-36(in Chinese).   
[11]Meitner PL. Computer Code for Predicting Coolant Flow and Heat Transfer in Turbomachinery[R].NA- SATP-2985,1990.   
[12]王新月．气体动力学基础[M]．西安：西北工业大学出版社. 2006: 94-98,204-209. WANG Xinyue. Fundamentals of Gas Dynamics[M]. Xi'an: Northwestern Polytechnical University Press.20O6:94-98, 204-209(in Chinese).   
[13]Shapiro A H. The Dynamics and Thermodynamics of Compressible Fluid Flow Volume I[M]. New York: Ronald Press Co,1954.   
[14]吴国熙．调节阀使用与维修[M].北京：化学工业出版社, 1999: 67-70. WU Guoxi. The Regulator Using and Maintenance[M]. Beijing: Chemical industry press,1999: 67-70(in Chinese).   
[15]Ivor Horton,苏正泉,李文娟(译).Visual $C { \ + } +$ 2010入门经 典(第5版)[M].北京：清华大学出版社,2010:459-539. IvorHorton,SU Zhengquan,LI Wenjuan(translate). Beginning Visual $\mathrm { C } { \mathrm { + + } }$ 2010(Fifth edition)[M].Beijing: Tsinghua University Press,2010: 459-539(in Chinese).