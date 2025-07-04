# Maucha图的Matlab实现及其在水化学中的应用

任孝宗'，刘敏'，李建刚²，李继彦¹

1太原师范学院地理科学学院,山西晋中030619；2白银市三北防护林工程建设管理站,甘肃白银730900)

摘要：水中可溶性离子的含量及各离子的比例关系是衡量水质的重要指标，但常用的方法不能同时反映这两种关系。Maucha 图既可以反映8种主要阴、阳离子的总浓度，同时也可以指示各离子的相对浓度,兼顾了离子的绝对含量和相对含量，具有较强的实用性。但由于缺乏绘制Maucha 图的专业软件，导致Maucha图在实际应用中受到很大限制。通过介绍Maucha图的演化过程，绘制Maucha图时建立坐标系及确定Maucha图各组成部分坐标值的方法，并阐述了基于Matlab语言实现Maucha图计算机输出的编程流程。最后以内蒙古浑善达克沙地东部地区为例，说明了Maucha图在天然水体水化学分析中的应用。该应用表明，Maucha图在反映样品矿化度、指示各离子的相对浓度和绝对浓度、判断水体水化学类型及水化学数据空间分析等方面均具有较强的优势，能显著提高水化学数据的可视化表达能力，丰富水化学图在水文地质中的应用，并为水化学数据更深层次的分析提供参考依据。

关键词：Maucha图；水化学；Matlab；绘图；应用

水资源是人类赖以生存和发展的基础，但我国水资源时空分布极不均匀、人均水资源占有量少，水资源安全面临很大挑战[1-3],特别是部分天然水体水质不达标，无法满足人们生产和生活的需要，因而水质分析成为水资源开发利用的前提之一。各类水化学图被广泛应用于水质分析[4-6],可反映水中可溶性离子的含量及其比例关系，其中常用折线图来反映水中各离子的绝对含量。该图以横坐标表示各类离子，纵坐标表示离子浓度。折线图虽然能准确反映各离子的真实浓度，但当同一个折线图内样品量较多时，数据点之间的重叠可能导致无法有效区分样点。此外，折线图反映的是离子的绝对浓度，并不能反映单个离子占所有阴/阳离子或总离子的比例，即不能反映单个离子的相对浓度。

Maucha图很好的解决了上述问题，既可以避免样品间的互相重叠，又可以指示样品各离子的相对浓度，其大小还可以反映离子的绝对浓度和矿化度。该图由匈牙利科学家Maucha于1932年以德语著作的形式提出[7],后经其他科学家数次修改。例如,原始型Maucha图只能指示各离子的相对浓度，不能反映样品的矿化度，因此HEDGPETH[8在原始型Maucha图旁增加了一个对数标尺，用以反映样品矿化度的大小，并对矿化度小于等于海水的样品用虚线绘制，而对矿化度大于海水的样品用实线绘制。但该改进方法仍无法直观的反映不同样品矿化度的差异。基于这个问题， $\mathrm { B R O C H } ^ { [ 9 ] }$ 为Maucha图的圆形部分引入了内切正十六边形的概念，该内切正十六边形并不需要绘制在Maucha图中，但可以用其面积来表示样品中8个主要阴、阳离子的总浓度。由于这8大离子是产生水样矿化度的主要成分，因而可以用其近似反映样品的矿化度。改进后的Maucha图既可以通过内切正十六边形的面积来反映样品的绝对含量，又可以通过表示各离子含量的四边形的面积指示其相对含量。因圆的面积与其内切正十六边形的面积相对应，因此实际应用中可直接根据圆的面积来比较不同样品的矿化度。本文以下所述均指经BROCH改进后的Maucha图。

Maucha图与雷达图（Radarchart）在外观上较为相似，但Maucha图并不能像雷达图那样用常见科学绘图软件实现。HASSELL基于Qbasic语言实现了Maucha 图的计算机输出[1o],但基于Qbasic 的操作系统过于陈旧，导致该方法不能得到有效推广。Matlab语言可在当前多数主流计算机操作系统上运行，是近年来被广大科技工作者广泛使用的计算机编程语言，其不但具有可读性强、调试简单等特点，且其强大的绘图功能在水化学图的计算机输出方面表现出很大优势[11]。本文在阐明Maucha 图绘制原理的基础上，以Matlab语言编程实现了Maucha图的计算机输出，并通过实例说明Maucha图在水化学中的应用，以期扩展该图在水化学中的应用范围。

# 1Maucha图的组成及其含义

Maucha图由1个圆和主体位于圆内的8个四边形组成，圆又被分为左右两个半圆。左半圆由四个四边形组成，其面积分别指示四种阴离子（按逆时针顺序从上到下依次为 $\mathrm { C O } _ { 3 } ^ { 2 - }$ 、 $\mathrm { H C O } _ { 3 } ^ { - }$ 、 $\mathrm { C l } ^ { - }$ 和$\mathrm { S O } _ { 4 } ^ { 2 - }$ )的浓度;相对应右半圆也由四个四边形组成,其面积分别指示四种阳离子（按逆时针顺序从下到上依次为 $\mathrm { M g } ^ { 2 + }$ ） $\mathrm { C a } ^ { 2 + }$ 、 $\mathrm { { N a } ^ { + } }$ 和 $\mathrm { ~ K ~ } ^ { + }$ )的浓度（图1）。圆的半径大小由其内切正十六边形的面积决定，其内切正十六边形的面积如前文所述由8大离子的总浓度决定。

代表某个离子的四边形的确定方法为：当圆被等分为8个扇形后，对于每个扇形而言，由组成扇形的两条半径及扇形内或外的一个点（该点须位于过圆的十六等分点的射线上)可确定一个四边形，该四边形的面积须等于该离子的浓度。同理，可确定代表其他离子的另外7个四边形，且这8个四边形的面积之和等于圆内切正十六边形的面积。需要注意的是，Maucha图中的离子浓度指的是当量浓度，且阴、阳离子电荷数相等，呈电中性

![](images/836b8f1f8f4eb30e22ebb9f55216b3ddcda7e15d1b9c39592bebc6a04112f06f.jpg)  
图1Maucha 图及其含义  
Fig.1Maucha diagram and its implications

# 2Maucha图的绘制原理

（1）单位转换。离子浓度一般以 $\mathbf { m } \mathbf { g } \cdot \mathbf { L } ^ { - 1 }$ 表示,因此需要将其转换为当量浓度 $( \mathrm { m e q } \cdot \mathrm { L } ^ { - 1 }$ ）。

(2）阴、阳离子电荷平衡及质量平衡原理检验。Maucha图用两个面积相等的半圆分别指示阴、阳离子总浓度，其前提条件是阴、阳离子总电荷数需符合电荷平衡原理。这是衡量水化学数据准确性和精度的标准，同时也是能否应用Maucha图的先决条件。因此在绘制Maucha图前需要对阴、阳离子电荷平衡进行检验。由于水中除Maucha图指示的八种主要离子外还含有其他带电微量离子、胶体以及有机物等，因此阴、阳离子电荷平衡常数满足 $\pm 5 \%$ 时通常被认为是符合电荷平衡原理的[12]。电荷平衡常数E.B.的计算公式[2]如下所示：

$$
E . \ B . \ = \frac { S C \ + S A } { S C \ - S A } \times 1 0 0 \%
$$

式中： $S C$ 为阳离子电荷总数; $S A$ 为阴离子电荷总数。此外，水化学数据还需满足质量平衡原理，要求样品矿化度等于8大离子含量之和，且精度控制在±5%[12] ○

（3）建立坐标系，确定坐标原点。如图2和图3,以圆心O为坐标原点，OG方向为 $x$ 轴,OD方向为 $y$ 轴，建立坐标系。

（4）圆的半径R和顶点B的确定。当 $\mathrm { C O } _ { 3 } ^ { 2 - }$ 、$\mathrm { H C O } _ { 3 } ^ { - }$ 、Cl-、 $\mathrm { S O } _ { 4 } ^ { 2 - }$ 、 $\mathbf { M } \mathbf { g } ^ { 2 + }$ 、 $\mathrm { C a } ^ { 2 + }$ 、 $\mathrm { { N a } ^ { + } }$ 和 $\mathrm { ~ K ~ } ^ { + }$ 中某离子的含量小于8大离子平均值时，代表某离子含量的四边形将位于圆内(图2);相应的，当某离子的含量大于8大离子平均值时，代表某离子含量的四边形将位于圆外(图3)；当某离子的含量等于8大离子平均值时，代表某离子含量的四边形将位于圆上。无论上述哪种情况，在确定Maucha图各参数的过程中均使用相同的公式，因此，这里以代表 $\mathrm { ~ K ~ } ^ { + }$ 的四边形ODBC为例说明圆的半径R和四边形顶点B的确定过程。图2和图3中 $\mathrm { ~ D ~ } , \mathrm { C ~ } , \mathrm { G } , \mathrm { H } , \mathrm { I } , \mathrm { J } , \mathrm { K }$ 和L为圆的8个八等分点，A为圆的1个十六等分点，线段AC为圆内切正十六边形的一条边，线段CF垂直于线段OA，线段AE垂直于线段OC，∠AOC为$2 2 . 5 ^ { \circ }$ 。

![](images/3e01bd56e8b211cb52b89408d20610cbab6454c0dc1a9fc1acf710297146df29.jpg)  
图2Maucha图各组成部分坐标的确定方法（顶点B位于圆内）

![](images/1aa26cd2c8ddbb2711c598c2602fad36a53fb61b64170269fc9e67110b651ca9.jpg)  
Fig.2Determining the coordinates of the components inMaucha diagram（vertex B inside the circle）  
Fig.3Determining the coordinates of the components in Maucha diagram（vertex B outside the circle)

根据Maucha图的组成特点可知：圆内切正十六边形的面积等于16倍的三角形OAC的面积，也等于8大离子当量浓度的总和，结合三角函数关系可得：

$$
R ^ { 2 } \cdot \sin 2 2 . 5 ^ { \circ } / 2 = T / 1 6
$$

式中： $R$ 为圆的半径; $T$ 为8大离子的当量浓度总和。

三角形OBC的面积等于 $\mathrm { ~ K ~ } ^ { + }$ 当量浓度的一半，结合三角函数关系可得：

$$
b \cdot R \cdot \sin 2 2 . 5 ^ { \circ } / 2 = P / 2
$$

式中： $b$ 为线段OB的长度； $P$ 为 $\mathrm { ~ K ~ } ^ { + }$ 当量浓度。

顶点B的坐标为：

$$
b x = b \cdot \sin 2 2 . 5 ^ { \circ }
$$

$$
b y = b \cdot \cos 2 2 . 5 ^ { \circ }
$$

式中： $b x \_ b y$ 分别为顶点B的横、纵坐标。

由公式(3)求得 $b$ ，再带入（4)和(5)即可求得顶点B的坐标 $b x , b y$ 。

同理，另外7个四边形的顶点也可以由上述方法确定。

# 3Maucha图的编程流程

Maucha图的Matlab实现流程见图4。首先，将被测样品的离子浓度 $( \mathbf { m g \cdot L ^ { - 1 } }$ )转化为当量浓度（204号 $( \mathrm { m e q } \cdot \mathrm { L } ^ { - 1 }$ )。其次，判断样品是否符合电荷平衡原理及质量平衡原理。如果电荷不平衡或不满足质量平衡原理，则在程序运行窗口显示：“样品电荷不平衡或不满足质量平衡原理，无法绘制Maucha图”，然后退出程序；如果阴、阳离子电荷数平衡且满足质量平衡原理，程序继续运行。再次，以圆心为坐标原点、两条相互垂直的半径方向为 $\mathbf { \sigma } _ { \mathbf { X } }$ 轴和y轴建立直角坐标系。根据上文所述公式(1)计算圆的半径$R$ ，并用plot命令绘制圆，然后根据公式（3）、（4）和(5)及循环语句计算顶点B的坐标bx、by以及另外七个四边形的顶点。最后用plot命令绘制出8个四边形。

![](images/e704f6a507a45e6f8ce7d501a4abce40a8355bc7c735ea68896e0fc1c13897e8.jpg)  
图3Maucha图各组成部分坐标的确定方法（顶点B位于圆外)  
图4Maucha 图的编程流程  
Fig.4Program flow for plotting Maucha Diagram

在整个Maucha图的Matlab实现过程中，几乎不出现精度的损失。首先,将离子浓度从 $\mathbf { m } \mathbf { g } \cdot \mathbf { L } ^ { - 1 }$ 转换为当量浓度 $\mathrm { { m e q } } \cdot \mathrm { { L } } ^ { - 1 }$ 时,所采用的原子量数值取3位有效数字，单位转换过程中的数值类型采用Matlab中精度最高的双精度浮点数。其次，在计算圆的半径 $R$ 和顶点B的坐标时，数值类型仍然采用双精度浮点数。以上措施能最大限度的保障结果具有较高精度。

# 4Maucha图在浑善达克沙地的应用

Maucha图在水化学分析中使用较为广泛，其应用方式可归纳为两种：一是将不同样品的Maucha图绘制在同一图中，以便进行样品间的比较，例如HAROLD等将Maucha图应用于南非的研究工作[13];其二是将样品的 Maucha 图绘制到研究区概况图中，利用Maucha图对水化学数据进行空间分析，例如CONZONNO和ULIBARRENA将Maucha图应用于阿根廷的研究工作[14]

本文以浑善达克沙地天然水体为例，采用公开发表的水化学数据[15],说明 Maucha 图在水化学中的应用。浑善达克沙地位于我国内蒙古高原东部，主要以固定和半固定沙丘为主[16-20]。沙地天然水体的 $\mathrm { C O } _ { 3 } ^ { 2 - }$ 含量很低或者不含 $\mathrm { C O } _ { 3 } ^ { 2 - }$ ,而其天然水体特别是地下水由于受到人类活动的影响 $\mathrm { N O } _ { 3 } ^ { - }$ 含量较高，研究 $\mathrm { N O } _ { 3 } ^ { - }$ 含量的变化比研究 $\mathrm { C O } _ { 3 } ^ { 2 - }$ 含量的变化更有意义。因此本文对Maucha图做了调整，用$\mathrm { N O } _ { 3 } ^ { - }$ 替代 $\mathrm { C O } _ { 3 } ^ { 2 - }$ ,并在等比例条件下将浑善达克沙地东部地区天然水体的Maucha图绘制在同一图中（图5）。绘制Maucha图前，先对其是否满足电荷平衡原理及质量平衡原理进行判断，经程序判断，该数据满足电荷平衡原理及质量平衡原理。图中g1、g2…g11为地下水样品,共11个； $1 1 \cdot 1 2 \cdots 1 6$ 为湖水样品，共6个； $\mathrm { r 1 , r 2 } \cdots \mathrm { r 5 }$ 为河水样品，共5个;s1和s2为泉水样品，共2个。

![](images/3faf72449710aa21dea2536af4c01f7f297a4d15d54ab1a6c3564ba033bc1dc6.jpg)  
图5Maucha图在浑善达克沙地的应用 Fig.5Application of Maucha diagram in Hunshandake Sandy Land

如前文所述，可用圆的面积指示样品的矿化度。从图5可知，大多数地下水样品的矿化度高于湖水、河水和泉水样品，这可能和地下水与含水层物质的水一岩作用时间长、溶解较多的物质有关[15]。和典型西部沙漠如巴丹吉林沙漠的湖水样品[21-23]相比,浑善达克沙地东部地区湖水样品的矿化度并不高，暗示该地区的蒸发量小于我国西部沙漠。通过对比代表各离子浓度的四边形的面积可以判断该样品的优势阴、阳离子。如图5所示，地下水各样品的优势阴离子并不相同,为 $\mathrm { N O } _ { 3 } ^ { - }$ 或 $\mathrm { H C O } _ { 3 } ^ { - }$ 或 $\mathrm { S O } _ { 4 } ^ { 2 - }$ 或 $\mathrm { C l } ^ { - }$ ：而大多数地下水样品的优势阳离子较为一致，主要是 $\mathrm { C a } ^ { 2 + }$ ,其次是 $\mathrm { { N a } ^ { + } }$ 。湖水、河水和泉水样品的优势阴、阳离子相对一致，除泉水样品 $\mathrm { \Pi _ { s l } }$ （优势阴离子为 $\mathrm { S O } _ { 4 } ^ { 2 - }$ ,其次为 $\mathrm { H C O } _ { 3 } ^ { - }$ )外,其他样品的优势阴离子均为 $\mathrm { H C O } _ { 3 } ^ { - }$ ,而优势阳离子和地下水的优势阳离子相同,主要是 $\mathrm { C a } ^ { 2 + }$ ,其次是 $\mathrm { { N a } ^ { + } }$ 。

优势离子也可以通过计算获取，一般将百分含量(基于摩尔浓度)大于 $2 5 \%$ 的阴、阳离子统计制成水化学类型表[24]。结果表明（表1）,多数地下水样品的优势阴离子较复杂,而优势阳离子主要是 $\mathrm { C a } ^ { 2 + }$ （204号和 $\mathrm { { N a } ^ { + } }$ ;多数地表水的优势阴离子是 $\mathrm { H C O } _ { 3 } ^ { - }$ 而优势阳离子是 $\mathrm { C a } ^ { 2 + }$ 和 $\mathrm { { N a } ^ { + } }$ 。该结果与基于Maucha图的分析基本一致但略有差别（原因是Maucha图使用当量浓度而水化学类型表使用摩尔浓度），表明Maucha图可以直观的反映样品的优势离子。

将不同样品的Maucha图按等比例原则绘制在采样图的对应位置，可用以分析样品的矿化度及各离子相对浓度在空间上的变化关系。本文选取了9个样品，将其绘制在DEM底图上（图6)。从图6中可以看到，地下水样品主要分布在西拉木伦河源头西南方向，其矿化度高于地表水样品，其与其他地表水样品的距离约为 $5 0 ~ \mathrm { k m }$ ,因此气候并不是引起它们较大差异的主要因素。通过氢氧同位素等指标的进一步分析，发现引起这种差异的主要因素是水体的补给方式不同[15]

该空间分析方法存在一定局限性，例如，由于Maucha图所占面积较大，当样品较多时，很难将所

# 表1浑善达克沙地天然水体水化学分类表

Tab.1 Hydrochemical classification of natural water in   

<html><body><table><tr><td colspan="3">Hunshandake Sandy Land</td></tr><tr><td>样品 编号</td><td>水体 类型</td><td>水化学类型</td></tr><tr><td>g1</td><td>地下水</td><td>HCO³-Ca²+</td></tr><tr><td>g2</td><td>地下水</td><td>HCO−-Ca² +</td></tr><tr><td>g3</td><td>地下水</td><td>HCO³-Cl−-Ca²+-Na+</td></tr><tr><td>g4</td><td>地下水</td><td>Cl−-HCO³-SO²−-Ca²+ -Na+-Mg²+</td></tr><tr><td>g5</td><td>地下水</td><td>Cl−-HCO³-SO4−-Ca²+ -Na+</td></tr><tr><td>g6</td><td>地下水</td><td>Cl−-HCO³- Na+- Ca²+</td></tr><tr><td>g7</td><td>地下水</td><td>NO -Ca²+ - Na+</td></tr><tr><td>g8</td><td>地下水</td><td>HCO³-NO-Na+-Ca² +</td></tr><tr><td>g</td><td>地下水</td><td>HCO³-Ca²+</td></tr><tr><td>g10</td><td>地下水</td><td>HCO³- NO-Ca²+-Na+</td></tr><tr><td>g11</td><td>地下水</td><td>HCO−- SO--Ca²+- Na+</td></tr><tr><td>l1</td><td>湖水</td><td>HCO−- Na+- Ca²+</td></tr><tr><td>12</td><td>湖水</td><td>HCO³- Na+- Ca² +</td></tr><tr><td>13</td><td>湖水</td><td>HCO³-Ca²+ -Na+ - Mg² +</td></tr><tr><td>14</td><td>湖水</td><td>HCO−-K+- Ca²+- Mg² +</td></tr><tr><td>15</td><td>湖水</td><td>HCO³- Na+- Ca² +</td></tr><tr><td>16</td><td>湖水</td><td>HCO³- Na+- Ca²+ - Mg²+</td></tr><tr><td>rl</td><td>河水</td><td>HCO³- Na+- Ca² +</td></tr><tr><td>r2</td><td>河水</td><td>HCO³- Na+ - Ca²+</td></tr><tr><td>r3</td><td>河水</td><td>HCO³- Na+ - Ca² +</td></tr><tr><td>r4</td><td>河水</td><td>HCO³- Ca²+- Na+</td></tr><tr><td>r5</td><td>湖水</td><td>HCO³-Ca²+- Na+</td></tr><tr><td>s1</td><td>泉水</td><td>HCO- SO−- Na+- Ca²+</td></tr><tr><td>s2</td><td>泉水</td><td>HCO³- Ca²+- Na+</td></tr></table></body></html>

![](images/4983c3c9786b679e36072f5c92dbfb5706eefe4201b045389741a64d64b08d86.jpg)  
图6Maucha图在水化学数据空间分析中的应用Fig.6Application of Maucha diagram in spatial analysisfor hydrochemical data

有样品的Maucha图绘制到一幅底图上，限制了Maucha图在空间分析中的应用。针对应用出现的问题,有两种解决办法。其一，绘制大比例尺的研究区底图，其二，按比例缩小Maucha图，以便最大限度的将所有样品的Maucha图涵盖到同一研究区底图上。另外，也可以通过将所有样品的Maucha图绘制到一幅图中，然后对照研究区概况图，间接实现Maucha图的空间分析功能。

# 5结论

Maucha图既可以反映8大离子的矿化度，又可以指示各离子的相对浓度和绝对浓度，具有较强的实用性，但由于缺乏绘制Maucha 图的专业软件导致该方法不能得到普遍应用。本文介绍了Maucha图的演化过程，阐述了绘制Maucha图时坐标系统的建立及其各组成部分（圆半径和四边形顶点）坐标值的确定方法,并以Matlab 语言为工具说明了实现计算机输出Maucha图的编程流程。在此基础上，本文以内蒙古浑善达克沙地东部地区天然水体水化学数据为例，根据研究区天然水体水化学特点，用 $\mathrm { N O } _ { 3 } ^ { - }$ 替换 $\mathrm { C O } _ { 3 } ^ { 2 - }$ 绘制了基于Matlab语言的Maucha图。结果表明,Maucha图在反映样品矿化度、指示各离子相对浓度和绝对浓度、判断水体水化学类型及水化学数据空间分析等方面具有较强的优势。相比其他编程语言，基于Matlab绘制的Maucha图具有更广泛的计算机操作系统基础、更好的可读性和更强的可视化能力。此外，在该方法的基础上还可以进行二次开发，根据研究区的水化学特点，用其他离子替换原Maucha图中的离子（如用 $\mathrm { N O } _ { 3 } ^ { - }$ 替换 $\mathrm { C O } _ { 3 } ^ { 2 - }$ ），以实现特定的研究目的。该方法的应用将有助于推动Maucha图在水文地球化学过程的识别和解释中的应用，提高水化学数据的可视化能力，为更深层次的水化学数据分析提供参考依据。

# 参考文献(References)

[1］夏军,翟金良，占车生.我国水资源研究与发展的若干思考[J].地球科学进展,2011，26（9）：905-915.［XIAJun,ZHAIJinliang,ZHAN Chesheng.Some reflections on the research and ofdevelopment water resources in China[J].Advances in Earth Sci-ence,2011,26(9):905-915.]

[2]周迪，周丰年,钟绍军.我国人均水资源量分布的俱乐部趋同研究——基于扩展的马尔科夫链模型[J].干旱区地理,2018，41（4）:867-873.[ZHOUDi,ZHOUFengnian,ZHONG Shao-jun.“Club convergence"of per capita water resource distribution in

China:Based on extended Markov chain model[J].Arid Land Geography,2018,41(4) :867 -873.]   
[3］李锋瑞,刘七军,李光棣.水资源管理模式评述与展望[J].中 国沙漠,2008,28（6）:1174-1179.[LI Fengrui,LIU Qijun,LI Guangdi.Patterns of water resources management: Overviews and prospects[J]. Journal of Desert Research,2018,41（4）:867 - 873.]   
[4］韩知明,贾克力,史小红,等.克鲁伦河流域下游水体氢氧同位 素与水化学特征[J].干旱区地理,2019,42(1）:85-93.［HAN Zhiming,JIA Keli,SHI Xiaohong,et al.Hydrochemical and hydrogen and oxygen isotopic characteristics of water in the low reach of Kherlen River[J].Arid Land Geography,2019,42(1):85-93.]   
[5］王利杰,曾辰,王冠星,等.西藏山南地区沉错湖泊与径流水化 学特征及主控因素初探[J].干旱区地理,2017,40（4)：737- 745.[WANG Lijie,ZENG Chen,WANG Guanxing,et al. Chemical characteristics and impact factors of the Drem-tso Lake and supplying runof in the Southern Tibet[J].Arid Land Geography,2017, 40(4) :737 -745.]   
[6]文广超,王文科,段磊,等.基于水化学和稳定同位素定量评价 巴音河流域地表水与地下水转化关系［J].干旱区地理,2018, 41(4）:734 -743.[ WEN Guangchao,WANG Wenke,DUAN Lei, et al.Quantitatively evaluating exchanging relationship between river water and groundwater in Bayin River Basin of Northwest China using hydrochemistry and stable isotope[J].Arid Land Geography,2018,41(4) :734-743.]   
[7]MAUCHA R.Hydrochemische methoden in der limnologie[J]. Binnengewasser,1932,12:173.   
[8]HEDGPETHJW.Some preliminary considerations of the biology of inland mineral waters[J].Arch Oceanog Limnol,1959,11（Suppl. ) :111 - 141.   
[9]BROCH E S.A modification of Maucha's ionic diagram to include ionic concentrations[J].Limnology and Oceanography,1969,14： 933-935.   
[10]HASSELL A,MARTIN D F.A computer-generated(q-basic）program to construct maucha diagrams[J].Florida Scientist,1995,58 (3):300 -254.   
[11］任孝宗,刘敏,张迎珍,等.基于 Matlab 的 Durov 三线图的实现 [J].干旱区地理,2018,41(4）:744-750.[REN Xiaozong,LIU Min,ZHANG Yingzhen,et al.Plotting Durov Diagram based on Matlab[J].Arid Land Geography,2018,41(4）:744-750.]   
[12]APPELO A,POSTMA D.Geochemistry,groundwater and pollution $\left[ \mathbf { M } \right] . 2 ^ { \mathrm { { n d } } }$ ed.Amsterdam;Taylor &Francis,2005.   
[13]HAROLD V,SILBERBAUER M,MALULEKE M. Geographical differences in the relationship between total dissolved solids and electrical conductivity in South African Rivers[J].Water SA,2014, 40(1) :133 - 138.   
[14］CONZONNO V H,ULIBARRENA J. Hydrochemistry of lakes of the Patagonian Province of Tierra del Fuego(Argentina）［J].Environmental Earth Sciences,2010,59(7）:1431-1436.   
[15]REN X,ZHU B,LIU M,et al.Mechanism of groundwater rcharge in the middle-latitude desert of Eastern Hunshandake,China diffuse or focused recharge?[J]Hydrogeology Journal,2018,27 (2):761-783.   
[16］靳鹤龄,苏志珠,孙良英,等.浑善达克沙地全新世气候变化 [J].科学通报,2004,49（15）：1532－1536.［JIN Heling,SU Zhizhu,SUNLiangying,et al.Climate change in Holocene,Hunshandake Sandy Land[J].Chinese Science Bulletin,2O04,49 (15):1532-1536.]   
[17］张洪,靳鹤龄,苏志珠,等.全新世浑善达克沙地粒度旋回及其 反映的气候变化[J].中国沙漠,2005,25（1）：1-7.［ZHANG Hong,JIN Heling,SU Zhizhu,etal. Climate changes revealed by grain-size cycles of Holocene in Hunshandake Desert[J]. Journal of Desert Research,2005,25(1） :1 -7.]   
[18]YANG X,LI H,CONACHER A. Large-scale controls on the development of sand seas in Northern China[J].Quaternary International,2012,250(2012):74-83.   
[19］朱震达,吴正,刘恕,等.中国沙漠概论［M].北京:科学出版 社,1980.[ZHU Zhenda,WU Zheng,LIU Shu,et al.An Outline of Chinese Deserts[M]. Beijing:Science Press,1980.]   
[20]YANG X,ZHU B,WANG X,et al. Late Quaternary environmental changes and organic carbon density in the Hunshandake Sandy Land,Eastern Inner Mongolia,China[J].Global andPlanetary Change,2008,61(1-2) :70 -78.   
[21]YANG X,WILLIAMS M J. The ion chemistry of lakes and late Holocene desiccation in the Badain Jaran Desert,Inner Mongolia, China[J]. Catena,2003,51(1）:45-60.   
[22］吴月,王乃昂,赵力强,等.巴丹吉林沙漠诺尔图湖泊水化学特 征与补给来源[J].科学通报,2014,59（12）：1140-1147.［WU Yue,WANG Nai'ang,ZHAO Liqiang,et al. Hydrochemical characteristics and recharge sources of Lake Nuoertu in the Badain Jaran Desert[J]. Chinese Science Bulletin,59(12）:1140 -1147.]   
[23］陈立,王乃昂,王浩,等.巴丹吉林沙漠湖泊与地下水化学参数 初步研究［J].中国沙漠,2012,32(2）:531-538.［CHENLi, WANG Nai'ang,WANG Hao,et al.Spatial patterns of chemical parameters of lakes and groundwater in Badain Jaran Desert[J]. Journal of Desert Research,2012,32(2）:531-538.]   
[24］朱秉启,杨小平.塔克拉玛干沙漠天然水体的化学特征及其成 因[J].科学通报,2007,52（13）:1561－1566.[ZHU Binqi, YANG Xiaoping.Chemical composition of natural waters and its origin in the Taklamakan Desert[J].Chinese Science Bulletin, 2007,52(13):1561-1566.]

# Plotting Maucha Diagram based on Matlab and its applications on hydrochemistry

REN Xiao-zong’，LIU Min'，LI Jian-gang²，LI Ji-yan' (1Taiyuan Normal University,School of Geographical Sciences,Jinzhong O3o619,Shanxi,China; The constructionand management stationof three North Shelterbelt Project in Baiyin,Baiyin7309o,Gansu,China)

Abstract：The content and the proportion of soluble ions in water are important indicators to assess water quality, but common methods used in hydrochemistry cannot reflect the two relationships simultaneously.Maucha diagram not only reflects the total concentration of eight main anions and cations in water(i. e. $\mathrm { C O } _ { 3 } ^ { 2 - }$ ， $\mathrm { H C O } _ { 3 } ^ { - }$ ,Cl-, $\mathrm { S O } _ { 4 } ^ { 2 - }$ ， $\mathrm { M g } ^ { 2 + }$ ， $\mathrm { C a } ^ { 2 + }$ ， $\mathrm { { N a } ^ { + } }$ and $\mathrm { ~ K ~ } ^ { + }$ ）,but also indicates relative and absolute concentrations for each ion simultaneously. Thus,the Maucha diagram is deemed to be very practical.However,due to the lack of professional software to plot Maucha diagram,theapplicationof this diagram isvery limited in hydrochemical research.Inthis paper,firstly,we introduced the evolution history of Maucha diagram which was proposed by Maucha in 1932 and developed by Hedgpeth and BROCH.Secondly,we introduced the components of Maucha diagramand its implications.This diagram makesup ofa circle and eight quadrangles inside.The area of the tangent 16-sided polygon in the circle is utilized to representthe total concentrationof eight anions andcations,andthearea of the eight quadrangles represents thecontentof eight ions.In addition,the total cationsand anionsare supposed to submit thecharge balance principleandthe mass balance principle.Thirdly,the methods of how to establish a coordinate system and determine the coordinates of the circle and quadrangles in Maucha diagram were introduced in detail.Fourthly,the program flow of how to plot Maucha diagram basedon Matlab was stated.Finally,taking the eastern Hunshandake Sandy Land in Inner Mongolia,Chinaasan example,this paper ilustrated the applications of Maucha diagram in the fieldof hydrochemical analysis for natural waters.The Hunshandake Sandy Land belongs toa climate transition zone near the middle-latitudeboundaryof semi-humidandsemi-arid toarid climate.Elevations in Hunshandake SandyLand decrease from ca.1 30O m in the southeastto ca.1O m a.s.l.in the northwest,while mean annual precipitation decreasing from $\sim 4 5 0 \ \mathrm { m m }$ in the southeast to $1 5 0 \ \mathrm { m m }$ or so in the northwest. Since natural water in Hunshandake Sandy Land is characteristic of high concentration of $\mathrm { N O } _ { 3 } ^ { - }$ and very low concentration of $\mathrm { C O } _ { 3 } ^ { 2 - }$ ,we used $\mathrm { N O } _ { 3 } ^ { - }$ instead of $\mathrm { C O } _ { 3 } ^ { 2 - }$ to plot Maucha diagram with Matlab.Before ploted Maucha diagram,we checked the ion data and only charge balance and massbalance data were used.Applications show that Maucha diagram has strong advantages inreflecting the total concentrationof anionsandcations,indicating the relativeandabsolute concentrations ions, judging the hydrochemical type of water body and spatial analysis for hydrochemical data.Compared to other computer languages,the Maucha diagram program writen by Matlab can run on almost allkinds of computer systems, and have beterreadabilityand visualization.Moreover,based on hydrochemical characteristicsof certainstudyarea,the program can be developed to adapt to new situations,such as in this paper we use $\mathrm { N O } _ { 3 } ^ { - }$ rather than $\mathrm { C O } _ { 3 } ^ { 2 - }$ to plot Maucha diagram.Thus,the application ofthe diagram may improve the visual expression ability forhydrochemical data,enrich theapplication of diagrams inhydrochemistry,and provideareference for further analysisofhydrochemical data.

Key words:Maucha Diagram；hydrochemistry；Matlab；plotting；applications