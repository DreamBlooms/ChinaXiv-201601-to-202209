# 空间蒸发液滴图像处理软件的设计与实现

冯艳辉1.2，于强1(1.中国科学院国家空间科学中心 北京 100190；2.中国科学院大学 北京 100049)

摘要：空间蒸发液滴图像处理软件是为研究空间液滴特性而设计开发的，它是实践十号科学卫星上蒸发与流体界面效应空间实验的重要数据处理平台。本软件采用边缘检测技术和轮廓拟合方法对液滴图像进行分析处理，以获取液滴的各项几何特性；采用 MYSQL数据库和CSV文件对数据进行存储，方便数据的使用。实验结果表明，该软件获得的液滴几何特性误差范围能够控制在 $5 \%$ 以内，每张图片的处理时间能够控制在1s之内。

关键词：图像处理；液滴几何特性；边缘检测；轮廓拟合中图分类号：TN919.81 文献标识码：A

# Design and implementation of space drops image processing software

FENG Yan-hui1²2, YU Qiang

(1.National Space and Science Center, Chinese Academy of Sciences,Beijing 1Oo19o, China; 2.University of Chinese Academy of Sciences,Beijing 10oo49, China)

Abstract: The space drops image processng software is used to investigate the geometrical characteristic of space drops,which is an important data analysis tool for the space experiment of evaporation and liquid interfacial effect on SJ1O satelite.The software can analyze and processdrop image by edge detection and contour fiting to calculate the geometrical characteristics of drops.And the data of drops is saved in MYSQL database and CSV file at the same time.The results indicate that the measurement eror of this software is within 5 percent,and the processing time of one image is less than 1s.

Key words: image processing; geometrical characteristics of drop； edge detection; contour fitting

蒸发与流体界面效应是当前国际微重力流体物理研究的热点[1-4]，我国研究工作者通过与国外研究机构合作，在落塔和失重飞机上进行了相关实验[5.6。但由于条件的限制，无法长时间观察微重力环境下的液滴蒸发特性。为开展进一步相关研究，在我国实践十号科学卫星上搭载了蒸发与流体界面效应空间实验平台，它主要研究微重力条件下的蒸发相变流体界面过程[。该实验中的液滴状态变化是由CCD 照相机进行记录的，所以在进行数据分析时需要对液滴图像进行处理，获取液滴的几何特性。

本文所实现的空间蒸发液滴图像处理软件是基于QtCreator编程实现的，可跨平台使用。它能够高效率的计算出液滴的各项几何特性，能够可视化的显示液滴处理的动态过程和处理结果。在微重力环境下液滴蒸发特性的研究中，该软件起到了重要的作用。

# 1图像处理软件模块设计

Qt Creator是一款跨平台的 $\mathrm { C } { + } { + }$ 集成开发环境，可在Windows、Linux、MacOS等桌面操作系统上运行[8]。本图像处理软件就是使用QtCreator平台进行开发的，其开发代码可以方便进行地平台间的移植，提升了软件平台的适用性。该软件从功能上主要分为文件处理、预处理、图像处理、数据处理、批处理五个模块，如图1所示。

蒸发液滴图像处理软件文件处理 预处理 图像处理 数据处理 批处理文件打开 文件保存 文件关闭 参数设置 区域选择 灰度化 二 边缘检测 轮廓拟合 几何 数据保存值化 特性计算

# 2文件处理模块

1）文件打开

文件打开是将液滴图片载入显示区域。在文件打开对话框中，设置了文件过滤和文件路径记忆选项，以便高效地选择符合要求的图片。其中，文件路径记忆功能是通过 QSetting类实现的，该类可以键-值对的形式读写INI文件中的路径信息[9]。

# 2）文件保存和关闭

在进行图像处理时，为方便观察图像的处理过程，确定图像结果是否正确，使用者可以通过保存功能，保留当前图像处理状态，以便后续观察。程序设计中，作者使用 ImgType枚举类型储存图像的中间状态，具体对应关系如表1所示。

表1图像当前处理状态的记录  

<html><body><table><tr><td>ImgType</td><td>图像处理状态</td></tr><tr><td>SRC</td><td>原图</td></tr><tr><td>GRAY</td><td>灰度化后的图像</td></tr><tr><td>BIN</td><td>二值化化后的图像</td></tr><tr><td>EDGE</td><td>边缘检测后的图像</td></tr><tr><td>FIT</td><td>轮廓拟合后的图像</td></tr><tr><td>FINA</td><td>几何参数计算完毕</td></tr></table></body></html>

文件关闭是关闭当前文件的显示区。当进行文件关闭操作时，如果图像处理状态不是FINA，则提醒用户是否放弃处理当前图像；否则，关闭图片显示区，释放资源。

# 3预处理模块

# 1）参数设置

在对液滴进行几何特性的计算时，需要首先设置基座高度、图像比例尺以及几何特性文件路径。在本软件中，参数设置的交互方式为模式对话框，参数状态以键-值对的方式存储，通过QSetting类进行读取和保存。

# 2）区域选择

由于实验环境并不总是处于理想状态下，获取的液滴图像会伴有明显的边缘噪声[10]，此时可以通过图像截取的方式，选择合适的目标区域，消除边缘噪声干扰。区域选择的处理逻辑如图2所示。

![](images/87704c1f7a211a7674fd9c05d4b8d72528e5c08e08be37c5873583ea373f7543.jpg)  
图1图像处理软件的模块设计  
图2区域选择功能的处理逻辑

# 4图像处理模块

1）灰度化和二值化原始液滴图像为RGB三通道彩色图像，而复杂的数据结构并不利于图像处理操作。本软

件中首先将彩色图像转化为灰度图像，然后进行二值化操作，这样图像数据由三通道降为单通道，方便了数据的读取和修改操作。

# 2）边缘检测

边缘检测是图像处理领域中最经典的研究内容之一，为人们解释图像提供了一个重要的特征参数[1]。这里使用边缘检测技术获取液滴的轮廓信息，并将液滴轮廓显示在软件的绘图区。本软件中使用的边缘检测算子为Canny算子，该检测算子具有良好的抗噪能力，能够获得较细的边缘[12]，在工程实践中被大量使用。

# 3）轮廓拟合

由边缘检测得到的液滴轮廓具有较大的数据量，并伴有一定的冗余信息，这里通过对获取的液滴轮廓进行稀疏提取来降低数据量，消除冗余信息。稀疏提取的步骤包括：

a．获取液滴轮廓的最大行序号maxr，并设置当前的行序号为 $\boldsymbol { \mathsf { r } } =$ maxr;  
b．获取第r行最左、最右的列序号Ic、rc，则该行的轮廓坐标为(lc,r)、(rc,r);  
c.令 $r = r + 1$ ，判断r值是否越界。如果越界则稀疏提取结束，否则回到步骤b，继续执行。

轮廓的稀疏提取结束后，根据获取的轮廓数据进行轮廓拟合，轮廓拟合采取基于表面张力方程的寻优迭代方法。

# 5数据处理模块

1）几何特性计算

a.表面积、体积、高度、接触面半径的计算

根据液滴的形状，可以以纵坐标为分割点将液滴分割为数个圆台。根据液滴轮廓曲线的特点，可令液滴的轮廓点为

$$
( x _ { 1 } , z _ { 1 } ) , ( x _ { n - 1 } , z _ { 1 } ) , ( x _ { 2 } , z _ { 2 } ) , ( x _ { n - 2 } , z _ { 2 } ) , \ldots , ( x _ { m } , z _ { m } ) , ( x _ { n - m } , z _ { n - m } ) ,
$$

设图像的比例尺为y，则液滴高度为 $h = m * y$ ，半径 $\begin{array} { r } { \mathrm { r } = \frac { x _ { n - 1 } - x _ { 1 } } { 2 } * \gamma } \end{array}$ 。液滴表面积和体积采用积分的方法进行求取，表面积为 $\begin{array} { r } { \mathsf { S } = \sum _ { i = 1 } ^ { m } s _ { i } + s _ { 0 } } \end{array}$ ，其中 $s _ { i }$ 为第i个小圆台的侧面积， $s _ { 0 }$ 为顶层圆台的上表面积。体积为 $\textstyle | \nabla = \sum _ { i = 1 } ^ { m } v _ { i }$ ，其中 $\boldsymbol { v } _ { i }$ 为第i个小圆台的体积。

# b.接触角的计算

液滴的几何特性如图3所示[13]，以液滴的顶点为坐标原点0，以该点切线为x轴，切线垂线为z轴分析液滴表面几何特性。其中 $O _ { 1 }$ 、 $O _ { 2 }$ 为点P的曲率圆圆心， $R _ { 1 }$ 、 $R _ { 2 }$ 为点P的曲率圆半径， $s _ { 1 }$ 为点P到原点0的弧长， $\varphi$ 为该点切线和数据平面的偏转角。

![](images/5339b5ccc9bc17f93157ae826089453449ab36f1ace16ea0a8bc2d8a1fdca220.jpg)  
图3液滴的几何特性

Young-Laplace方程经推导后满足

$$
{ \cfrac { d \varphi } { d s _ { 1 } } } = { \cfrac { 2 } { R _ { 0 } } } + \beta z _ { 1 } - { \cfrac { \sin \varphi } { x _ { 1 } } }
$$

其中 $\beta = \frac { ( \Delta \rho ) g } { \gamma }$ γ，Ro为O点对应的曲率半径，边界条件是𝑥i(0)= Z1(0)=φ(0)=0。使用文献中提出牛顿-拉夫逊迭代法结合坐标轮换法[14,15]即可快速、准确的求取各点的 $\varphi$ 值。液滴的左、右接触角分别为A、B点所对应的 $\varphi$ 值。

# 2）数据保存

计算得到的液滴几何特性即为该软件的测试结果。为了提高数据储存的安全性，该软件对测试结果进行了两路存储。

其中一路使用MYSQL数据库进行存储。MYSQL数据库是一种开源数据库,提供了 $\mathsf { C } / \mathsf { C } + +$ Java 等多种编程语言的编程接口，支持源代码的移植，能够很好的实现程序的跨平台使用。本次需要存储的数据规模适中，MYSQL作为一种轻量化的数据库，拥有较高的插入和查询速度[16]，可以胜任此次数据存储需求。

另外一路使用CSV（逗号分隔值）格式文件进行存储。CSV 格式文件包括两种分隔符：逗号分隔符和换行分隔符。逗号分隔符是将字段/列分隔开，而换行分隔符是将记录/行分隔开。需要注意的是除数值外，其他的数据必须放在引号内。CSV文件作为一种结构简单的数据存储的文本文件，方便程序的读写操作，而且该文件能够以 Excel形式打开，有利于用户对科学数据进行二次处理。

# 6批处理模块

批处理模块主要用于处理同一工况下的液滴图像，它的处理逻辑如图4所示

![](images/7dd56f117d9f3990d606cd15435a8cbe0390febab4d88f45672115e9b42fe155.jpg)  
图4批处理模块的处理逻辑

其中预处理须知是指使用者在进行批处理操作时需要注意的事项，包括处理对象需为同一工况下的液滴图像，图像尺寸必须是相同的；批处理前需要首先进行参数设置。

# 7实验结果

1）误差测量

为了测试软件所计算的数据是否准确，本文使用标准球冠的最大纵向截面作为测试对象。根据球冠的表面积和体积公式可求出不同圆心角所对应的球冠的几何特性。在测试中，选择了半径300，圆心角分别为130度、140度、150度、160度、170度的球冠进行测量，测量误差如表2所示。

表2软件的测量误差  

<html><body><table><tr><td>圆心角/度</td><td>高度</td><td>半径</td><td>表面积</td><td>体积</td><td>接触角</td></tr><tr><td>130</td><td>0.45%</td><td>0.04%</td><td>2.70%</td><td>1. 01%</td><td>2.93%</td></tr><tr><td>140</td><td>0.31%</td><td>0.03%</td><td>3.24%</td><td>1.07%</td><td>0.21%</td></tr><tr><td>150</td><td>0.29%</td><td>0.08%</td><td>3.75%</td><td>0.98%</td><td>1.68%</td></tr><tr><td>160</td><td>0. 44%</td><td>0.19%</td><td>4.24%</td><td>0.64%</td><td>1.80%</td></tr><tr><td>170</td><td>0. 42%</td><td>0.38%</td><td>4. 34%</td><td>0.60%</td><td>2.94%</td></tr></table></body></html>

由表2的测量结果可以看出，该软件对液滴图像的测量误差均能够控制在 $5 \%$ 范围之内，能够满足数据使用的要求。

# 2）实验数据图像

此处，选择同一工况下的一组液滴图像进行批处理，得到液滴的体积变化如图5所示。

![](images/a6c03f23dcdf3bc9ea62aa98467887013817051276189dada8ca33b24a9aca12.jpg)  
图5液滴表面积随时间的变化

在图5中，AB段为注滴过程，体积和表面积逐渐增加；BC 段为液滴的饱和状态，此时液滴在表面张力和重力的作用下体积和表面积达到了最大；CD段为液滴的蒸发过程，由该段的变化趋势可以看出，液滴的蒸发过程是平稳的。图5曲线的变化过程符合液滴注滴和蒸发的特点，进一步验证软件测量结果的准确性。

# 8结论

该软件使用QTCreator平台进行编程，采用模块化设计思想，具有良好的适用性和可靠性。该软件已经成功应用在液滴图像的分析处理中，实验结果表明，该软件能够为研究者提供可靠的液滴数据，达到了设计要求。

# 参考文献：

[1]朱志强，纪岩，刘秋生,等．蒸发效应与热毛细对流耦合现象的实验研究[J].空间科学学报，2008,  
28(1):12-16.[2] 纪岩，刘秋生，朱志强．微重力环境下蒸发液层热毛细对流的数值模拟[J].空间科学学报，2008,  
28(4):350-355.[3] 孙凤贤，王银燕．辐射与对流耦合加热下正十二烷液滴的蒸发特性[J]．航空动力学报，

2008(11):2043-2048.[4] 刘荣，朱志强，刘秋生．蒸发液层对流稳定性理论与实验研究进展[J]．力学进展,2007,37(2):246-256.[5] Zhu Z Q,BrutinD,Liu QS,etal.Experimental InvestigationofPendantand Sesile Drops inMicrogravity[J].Microgravity Science & Technology,2010,22(3):339-345.[6] Brutin D,Zhu ZQ,Rahli O,et al.Evaporation of Ethanol Drops on a Heated Substrate Under MicrogravityConditions[J].Microgravity Science & Technology,2010,22(3):387-395.[7] 康琦，胡文瑞．微重力科学实验卫星——“实践十号”[J]．中国科学院院刊,2016,31(5):574-580[8]李文帆，刘志刚，伍文城，等．基于Qt 的电力系统地理接线图绘制软件设计[J]．电力系统自动化，2013,37(7): 72-76.[9] 布兰切特. $\mathbf { C } { \mathrel { + } } { + } \mathbf { G } \mathbf { U } \mathbf { I } \operatorname { Q } \mathrm { t } { \mathbf { \Omega } } 4$ 编程[M]．电子工业出版社,2013.[10]刘秋生，解京昌，朱志强,等．搭载实践十号卫星的蒸发液滴空间实验研究[J]．力学与实践，2016,38(2):201-202.[11]高朝阳，张太发，曲亚男．图像边缘检测研究进展[J]．科技导报,2010,28(20):112-117.[12]王智文．几种边缘检测算子的性能比较研究[J]．制造业自动化,2012,34(11):14-16.[13]Rotenberg Y,BoruvkaL,Neumann A W.Determination of surface tension and contact angle from the shapesof axisymmetric fluid interfaces[J].Journal of Coloid & Interface Science,1983,93(1):169-183.[14]宁乔，朱志强，吕旭涛,等．图像法求液滴表面张力和接触角[J].空间科学学报,2008,28(1):74-79.[15] Qiang Y,Cai S,Zhu Z,et al.Droplet Image Feedback Control System in Evaporation Experiment[J].Microgravity - Science and Technology, 2010,22(2):139-144.[16] 施瓦茨，扎伊采夫,等．高性能MySQL[M]．电子工业出版社,2013.

# 第一作者简介：

冯艳辉（1990—)，男，河北省廊坊市人，硕士，研究生，研究方向：计算机应用技术。