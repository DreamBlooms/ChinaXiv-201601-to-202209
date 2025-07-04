# 地平式太阳望远镜库德焦面指向跟踪误差建模研究

刘荣辉'²，刘辉'，穆恒宇'，柳光乾1(中国科学院云南天文台，云南 昆明 650011²中国科学院大学，北京 10049)

摘 要：为提高地平式太阳望远镜库德焦面的指向跟踪精度，文章首先仿真了库德光路中主光轴、方位轴、高度轴、消旋轴不同心时在库德焦面上引入的跟踪误差，分析了库德焦面指向跟踪误差的复杂性，这一问题无法用夜天文望远镜卡焦指向模型解决。然后文章提出了一种基于机器学习的支持向量回归方法来构建太阳望远镜库德焦面的指向跟踪模型，并在NVST望远镜进行了实测建模和实验论证。实验结果表明：在模型改正之前，NVST在库德焦面的指向误差最大值是650.55角秒、RMS是115.88角秒，30分钟跟踪误差是6.46角秒；模型改正之后，指向误差最大值是25.02角秒、RMS值是3.98角秒，30分钟跟踪误差是1.10角秒。由此可见，基于机器学习的支持向量回归建模方法能有效提高地平式太阳望远镜库德焦面的指向跟踪精度。

关键词：指向跟踪精度；指向模型；地平式太阳望远镜；库德焦面；支持向量回归中图分类号：P111.2 文献标识码：A 文章编号：

# 0引言

大口径地平式太阳望远镜是当今太阳地基观测仪器的一个发展方向[1]，为实现对太阳高时空分辨率的观测，大口径太阳望远镜对指向跟踪精度的要求也非常高。指向精度是指望远镜光轴对准观测目标的精确程度2，跟踪精度是指望远镜长时间跟踪观测目标的精确程度，高精度指向跟踪能使太阳望远镜精确指向日面的某一微小观测目标并使目标长时间稳定在视场中，以待高精度长时间成像或光谱等观测。例如，云南天文台的 1m 新真空太阳望远镜(New VacumSolar Telescope，NVST)的指向精度要求是5角秒，国家天文台的用于太阳磁场精确测量的中红外观测系统(Accurate Infrared Magnetic field measurements of the Sun，AIMS)的指向精度要求是10 角秒，美国的 DKIST太阳望远镜（Daniel Ken Inouye Solar Telescope，DKIST）指向精度是要求5角秒，这些望远镜的开环跟踪精度都要求达到30分钟内1-2角秒。

太阳望远镜的科学仪器比较特殊，对系统稳定性要求非常高，通常固定安放在库德焦面，不像夜天文望远镜安放在卡焦并随望远镜转动。因而太阳望远镜主副镜系统后端需要比较复杂的引导光路，并使主光轴穿过高度轴、方位轴和消旋轴，最后延伸到不随望远镜转动的库德焦点。如图1（a）所示的丽江2.4m望远镜RC 系统，终端仪器工作在卡焦位置，光路相对简单[2]。如图1（b）的抚仙湖的NVST太阳望远镜，格里高利光学系统的格里高利焦点（卡焦）到库德焦面有复杂的引导光路[3]。

![](images/1d4c11929a3b28dc8e0ae10b429ec8c499d321ed5f8a062e77b4f18b96909abc.jpg)  
图1夜天文望远镜与太阳望远镜光机结构比较（a）丽江2.4米望远镜光学结构；（b）NVST光学结构 Fig.l Comparison of optical and mechanical structures between night telescope and solar telescope (a)Optical structure of Lijiang 2.4m telescope；(b Optical structure of NVST.

地平式太阳望远镜指向跟踪运动过程中，引导光学系统需要随望远镜高度轴、方位轴、消旋轴运动。以NVST望远镜为例，M1、M2、M3、M4、M5、M6、M7与望远镜的方位同步运动；M1、M2、M4位置相对固定，但与望远镜高度轴同步运动；最后为了对目标进行消旋，光路还要随消旋轴运动[4。由于光机制造和装调误差的必然存在，望远镜主光轴、高度轴、方位轴、消旋轴不可能完全重合，这就导致即使格里高利焦点的像保持静止，但库德焦面的像还会有非常复杂运动，这就是库德焦面的二次跟踪误差，是地平式太阳望远镜库德焦面实现高精度指向跟踪所面临的难题。对于离轴格里高利系统的AIMS 太阳望远镜，库德焦面的图像运动还会更加复杂。

指向模型是提高天文望远镜指向精度和开环跟踪精度的一种控制策略，其过程是事先通过均匀密集采集全天区已知位置的星的指向误差来建立模型，然后用模型实时预测望远镜需要修正的误差进而提高望远镜的指向跟踪精度。针对夜天文望远镜的指向模型已经发展的比较成熟，最为广泛应用的是TPOINT指向模型和STARCAL等。但将这些模型应用到地平式太阳望远镜库德焦面时，无法得到理想的指向精度和开环跟踪精度。究其原因：这些模型都是基于望远镜卡焦的物理机制建立的模型，比如望远镜方位轴的不铅锤、高度轴不水平、主副镜光轴弯沉等误差描述项。但这些模型对于卡焦之后的库德光路中的旋转轴不同心等误差没有相关描述项，因为这些误差项与主光轴、高度轴、方位轴、消旋轴的同心度有很大关系，与每台太阳望远镜的穿轴误差密切关联，需要事先知道这些轴在库德焦面的旋转中心位置才能在模型中建立相应的误差描述项。

# 1.库德焦面跟踪误差仿真分析

地平式太阳望远镜库德焦面复杂的二次跟踪误差是由于主光轴、高度轴、方位轴、消旋轴不可能完全重合引入的。望远镜跟踪过程中，库德焦面的图像是旋转的，为了消除图像的旋转，消旋系统需要反方向运动来抵消图像的旋转。在地平式太阳望远镜的库德焦面上，图像的旋转由三个分量组成。它们分别是围绕主副镜系统主光轴的旋转分量，这个分量是由于赤道坐标系与地平坐标系之间的转换产生的，另外还有围绕高度轴的旋转分量和围绕方位轴的旋转分量，这是由于地平式望远镜跟踪运动引起的，库德光路需要围绕望远镜高度轴和方位轴旋转，这三个分量的旋转角根据文献[5」，可用公式（1）描述。

$$
\begin{array} { l } { \displaystyle \theta = \operatorname { a c o s } \Biggl ( \frac { \sin \left( \phi \right) - \sin \left( E \right) \sin \left( \delta \right) } { \cos \left( E \right) \cos \left( \delta \right) } \Biggr ) } \\ { \displaystyle E = \arcsin \left( \sin \left( \phi \right) \sin \left( \delta \right) + \cos \left( \phi \right) \cos \left( \delta \right) \cos \left( H \right) \right) } \\ { \displaystyle A = \operatorname { a c o s } \Biggl ( \frac { \sin \left( \delta \right) - \sin \left( E \right) } { \cos \left( E \right) \cos \left( \phi \right) } \Biggr ) } \end{array}
$$

式中： $\theta$ 为地平坐标产生的物方视场旋转角， $E$ 为高度角， $A$ 为方位角，在此处 $A$ 和 $E$ 都为像方视场旋转角分量， $\phi$ 为地理纬度， $\delta$ 为目标赤经， $H$ 为时角。

由于这三个分量在库德焦面的旋转中心位置及其关系是由望远镜具体的光机制造和装调误差决定的，除了消旋轴中心能方便实测之外，光轴是无法实测的，高度轴和方位轴也难以实测。为了分析地平式太阳望远镜库德焦面复杂的跟踪误差，参考库德光路中各反射镜的装调公差[6]，假设这三个旋转中心在CCD上的位置，如2（a）中所示。CCD上一个像素对应0.3角秒。以 NVST为例，分析在夏至日过中天半小时内望远镜在库德焦面产生的二次跟踪误差。

![](images/277163452938cd79f24ecb86e40a5e89c4d27e1a51808f4bcc95ba03284a7e1c.jpg)  
图2 库德焦面二次跟踪误差示意图 (a)三个旋转分量中心及消旋前后运动轨迹；(b)30分钟跟踪误差随时间的变化ig.2Schematicagraofoudefocalplaescoarytacigeor(a)Tecenteroftrotatiocompotsadthrackefodfterracemization;(b) Variation of 3O minutes tracking error with time

从图2（a）中消旋前后的运动轨迹对比可知，消旋系统虽然将库德焦面的图像旋转的消除了，但是由于几个旋转轴的中心不同，导致消旋后图像回不到原来的位置，产生了另外的图像移动，这就是二次跟踪误差。图2（b）中选取了夏至日太阳中天的30分钟来分析指向跟踪误差，最大达到了8.90角秒。如果光机装调误差更大，各轴系的旋转中心在库德焦面分散得更开，跟踪误差还会更大。

根据仿真分析可知，地平式太阳望远镜库德焦面上的二次跟踪误差是十分复杂的，要从物理机制上完成建模，就必须事先准确测量光轴、方位轴、高度轴和消旋轴在库德焦面的具体位置，这是极其困难的工作。为了解决这样问题，论文发展了基于机器学习的实测建模方法。

# 2.基于机器学习的库德焦面指向跟踪误差建模

2.1概述

机器学习可以在模型未知的情况下，通过算法对实测指向误差数据进行归纳和抽象，生成指向跟踪误差模型，通过模型实时预测观测目标对应的望远镜方位坐标和高度坐标，以此来实现望远镜高精度的指向跟踪。在库德焦面实测指向误差时，控制系统能记录待测星的地平坐标方位 $\mathrm { A _ { s } }$ 、高度 $\mathrm { E _ { s } }$ ，以及星在焦面探测器（CCD）中心位置时望远镜的地平坐标方位Ar、高度Er。理想情况下， $\mathrm { { A _ { s } } }$ 与 $\mathrm { A _ { T } }$ 相等， $\mathrm { E _ { s } }$ 与 $\mathrm { E } _ { \mathrm { T } }$ 相等，实际情况由于指向误差的存在，它们是不相等的。Ar是 $\mathrm { { A _ { s } } }$ 与 $\mathrm { E _ { s } }$ 的函数 $\mathrm { f _ { A } ( A _ { s } , \ E _ { s } ) }$ ,Er也是 $\mathrm { A _ { s } }$ 与 $\mathrm { E _ { s } }$ 的函数 $\mathrm { f _ { E } \left( A _ { s } , \ E _ { s } \right) }$ ，这可以理解为两个误差曲面拟合，这是一个典型的回归问题。

机器学习中常用的回归算法有支持向量回归(Support Vector Regression,SVR)、逻辑回归、广义局部线性模型、多项式回归等[7]。一般回归算法都需要大量的训练集，也就是要求事先获得大量的实测指向误差，这使得实际观测中工作量非常大，难以实现。所以本文采用能很好地处理小样本数据的支持向量回归建模，这个算法还具有较强的泛化能力[8]。

# 2.2支持向量回归的原理

支持向量回归中，采用文献[8-9]的方法，简化描述为：首先，把样本集作为S={𝑥i,yi}i-,其中 $\mathrm { ~ x ~ }$ 为输入向量， $x _ { i } \in R ^ { n }$ ， $\mathrm { \Delta y }$ 为相应的输出向量， $y _ { i } \in R ^ { n }$ 。这个算法是利用非线性映射将样本集从低维空间映射到高维空间，最终拟合训练集样本。该映射可以这样定义[：

$$
f \left( x \right) = \omega \phi \left( x \right) + b
$$

式中：x为输入数据， $\phi ( x )$ 为非线性映射函数； $\omega$ 为权重；b为截距。根据结构风险最小化原则，f(x)可等效于求解优化问题，即：

$$
f ( x ) = { \frac { 1 } { 2 } } \omega ^ { 2 } + C \sum _ { i } ^ { n } L { \bigl ( } f \left( x _ { i } \right) , y _ { i } { \bigr ) }
$$

式中： $ { L }$ 为损失函数； $c$ 为惩罚因子。加入松弛变量 $\left\{ \boldsymbol { \xi } _ { i } \right\} _ { i = 1 } ^ { n }$ 和 $\left\{ \boldsymbol { \xi } _ { i } ^ { * } \right\} _ { i = 1 } ^ { n }$ 来纠正不规则的因子，可得[9]：

$$
\operatorname* { m i n } { R \big ( \omega , b , \xi \big ) } = \frac { 1 } { 2 } \omega ^ { 2 } + C \sum _ { i } ^ { n } \big ( \xi _ { i } + \xi _ { i } ^ { * } \big )
$$

$$
s . t . \left\{ \begin{array} { c } { y _ { i } - \omega \phi \big ( \boldsymbol { x } \big ) - b , \varepsilon + \xi _ { i } } \\ { \omega \phi \big ( \boldsymbol { x } \big ) + b , \varepsilon + \xi _ { i } ^ { * } } \\ { \xi _ { i } , \xi _ { i } ^ { * } . 0 } \end{array} \right.
$$

式中： $\boldsymbol { \varepsilon }$ 为不敏感损失因子（允许的最大误差）， $\varepsilon > 0$ 。将回归问题转换为求取目标函数的最小化问题，利用对偶原理，同时引入拉格朗日乘法算子，可转换为[9]：

$$
\begin{array} { l } { \operatorname* { m a x } { R \big ( \alpha _ { i } ^ { * } , \alpha _ { i } \big ) } = - \displaystyle \frac { 1 } { 2 } \sum _ { i , j } ^ { n } \big ( \alpha _ { i } ^ { * } - \alpha _ { i } \big ) \big ( \alpha _ { j } ^ { * } - \alpha _ { j } \big ) \phi \big ( x _ { i } \big ) \phi \big ( x _ { j } \big ) } \\ { \displaystyle \qquad - \sum _ { i } ^ { n } \alpha _ { i } \big ( y _ { i } - \varepsilon \big ) + \sum _ { i } ^ { n } \alpha _ { i } ^ { * } \big ( y _ { j } - \varepsilon \big ) } \\ { \displaystyle \qquad \le t . t . \left\{ \sum _ { i = 1 } ^ { n } \big ( \alpha _ { i } ^ { * } - \alpha _ { i } \big ) = 0 \right. } \\ { \displaystyle \qquad ( \operatorname* { s u p } _ { i \in \mathcal { I } } \alpha _ { i } , \alpha _ { i } ^ { * } \textbf {  { c } } } \end{array}
$$

式中： $\alpha _ { i }$ 和 $\alpha _ { i } ^ { * }$ 为拉格朗日乘数。引入Mercer 定理，上述表达式可变换为[9]：

$$
f \left( x \right) = w \phi \left( x \right) + b = \sum _ { i = 1 } ^ { n } \left( \alpha _ { i } ^ { * } - \alpha _ { i } \right) \cdot K \left( x _ { i } , x \right)
$$

式中： $K \left( x _ { i } , x \right) { = } \phi \left( x _ { i } \right) \phi ( x _ { j } )$ 为核函数， $0 { \leqslant } { \alpha } _ { i } , { \alpha } _ { i } ^ { * } { \leqslant } C$ 。考虑到实测数据误差分布及模型实际应用，本文选取多项式核函数，其可定义为

$$
K _ { _ { p o l y } } \left( x _ { i } , x \right) = \left( x \cdot x _ { i } + 1 \right) ^ { d }
$$

式中，d表示多项式的阶数，d越大，多项式越复杂，计算量会越大。在实际的指向误差建模过程中，自变量可以表示为(x,x)=(A,E)。

公式（4）惩罚因子 $c$ 表示对模型复杂度与误差精度之间的折中， $c$ 越大模型泛化能力越差，$c$ 越小模型的训练误差越大， $\boldsymbol { \varepsilon }$ 表示样本之间的区分程度，这两个参数直接决定了支持向量回归的准确性。由于原始数据中，指向误差是关于高度值和方位值的函数关系，比较简单直观，再结合实际的模型训练效果， $C$ 值设置为500， $\boldsymbol { \varepsilon }$ 值设置为0.01。

# 3实测与建模

3.1指向误差实测

在指向误差实测过程中，采用表1的格式进行数据记录。Ar和Er的具体测量过程：给望远镜控制系统输入某一颗较亮恒星的理论地平坐标（As，Es），然后控制望远镜指向该星并处于跟踪状态，通过库德焦面成像探测器（CCD）实时采集星像并给出星像的重心。理想情况下，星像重心位置应该在CCD的中心（认为是视场中心），但是由于望远镜系统误差的存在，星像重心位置并不在CCD的中心，微动望远镜，使星像重心位置处在CCD中心。这时记录下望远镜的（Ar，$\mathrm { E } _ { \mathrm { T } }$ ）。它与（As,Es）之间的差值，就是该星的指向误差。

表1实测误差数据Table 1 Record formatof observation data  
unit: degree   

<html><body><table><tr><td>Number</td><td>Ar</td><td>ET</td><td>As</td><td>Es</td></tr><tr><td>1</td><td>149.745463</td><td>42.520237</td><td>149.7003</td><td>42.52303</td></tr><tr><td>2</td><td>170.781463</td><td>61. 170897</td><td>170.78662</td><td>61. 158965</td></tr><tr><td></td><td>··</td><td>.·</td><td>··</td><td>··</td></tr></table></body></html>

As的取值范围是0-360度，正北方向为0度，顺时针取值；Es的取值范围为0-90度，当望

远镜光轴指向天顶时，Es为90度。

实测工作在NVST望远镜上进行，成像通道选取的是TiO通道，CCD像元比是0.04，由于受NVST工作范围的影响，实测数据只能在一部分天区进行。观测时间是2021年1月14日晚，共测得138颗星的指向误差。图3是实测数据指向误差分布，最大误差是650.55角秒,RMS是115.88角秒。

![](images/add29fad56d1a14feb9259695a6a4dac93f3c49b4f84796c32a0d30a4eaa3994.jpg)  
图3数据的误差分布Figure 3.Error distribution of data

模型评价指标采用的是RMS（RootMean Square）值，RMS 越小表示模型的预测效果越好在地平坐标系，其公式如下。

$$
E r r o r = \sqrt { \left[ \Delta A \cos E _ { s } \right] ^ { 2 } + \Delta E ^ { 2 } } , \Delta A = A _ { s } - A _ { T } , \Delta E = E _ { s } - E _ { T }
$$

$$
R M S = \sqrt { \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \Bigl ( \Bigl [ \Delta A _ { i } \cos E _ { s } ^ { i } \Bigr ] ^ { 2 } + \Delta E _ { i } ^ { 2 } \Bigr ) }
$$

# 3.2模型的建立

为了在建模时多有几组不同的测试集和训练集，以及测试建模方法对数据是否敏感。将实测的138 颗星的误差数据抽样为6份，抽样方法是将星的位置尽量均匀分布在138 颗星所在的天区。将138颗星的误差数据抽样为6份后，每份有23颗星的指向误差数据，分别标记为trainO0O，train001，train002，train003，train004，train005。第一测建模时，把 train000，train001,train002，train003，train004合并为训练集（即建模数据，115个数据），train005为测试集（23个数据）。第二测建模时，把 train001，train002，train003，train004，train005合并为训练集（即建模数据，115个数据），第 train000组为测试集（23个数据）。如此不断换测试集和训练集的数据。最后对比六次测试集的统计结果，看是否有太大差别。

实验1结果如图4所示，图4（a）描述的是测试集的预测值和原始值的拟合程度，拟合的结果比较好。图4（b）描述的是测试集中预测值和实际值之间的误差，在图中测试集中最大的预测误差是12.89角秒，RMS是2.89角秒。这说明训练的模型对测试集的预测效果比较好。

(a) Testsets_Or iginal Error 12 (b） Testsets_Adjusted Error   
350 10   
300   
250   
Freeg 0 ese WWwMAA   
150 W I DeteNunber 20 10 15 20 25 30 Data Number

利用 SVR 模型对训练集做反向预测，得到的结果如图5所示。训练集的预测RMS 值是 2.84角秒，最大的预测误差是8.92角秒。通过对训练集的预测误差和测试集的预测误差相对比，二者的误差相差不大。

6 5- 20 40 60 80 100 Data Number

之后采用不同的训练集和测试集，进行了六次实验，得到的结果如表2所示。从表中可以看到，测试集的RMS 值都在3到4角秒，这说明使用支持向量回归方法构建的指向模型是有效的。

表2不同测试集的预测误差统计  
Table 2Error distribution of prediction of different test sets （unit:arcsec）   

<html><body><table><tr><td>实验次数</td><td>测试集</td><td>误差RMS</td><td>误差最大值</td></tr><tr><td>1</td><td>train000</td><td>2.89</td><td>12.89</td></tr><tr><td>2</td><td>train001</td><td>3.29</td><td>13.43</td></tr><tr><td>3</td><td>train002</td><td>3.59</td><td>12.15</td></tr><tr><td>4</td><td>train003</td><td>3.34</td><td>11.27</td></tr><tr><td>5</td><td>train004</td><td>3.28</td><td>11.06</td></tr><tr><td>6</td><td>train005</td><td>3.06</td><td>11.94</td></tr></table></body></html>

Fig.5 Error distribution of prediction of training set

# 3.3实测结果

为了验证模型在望远镜实际观测中的效果，将模型加载到控制系统，并在NVST上进行了指向误差实测和跟踪误差实测。

指向误差实测：星数为138颗，图6（a）是这138颗星在天区中的分布。如图6（b）数建模后的实测误差所示，最大的误差为25.02 角秒，其RMS 值为3.98角秒。

![](images/caa46b825534ddd0f540d12507d5067678b334a2206c7c52d6179eaf17340bd2.jpg)  
图6 指向精度实测效果的分析（a）138 颗星的在天区中的分布；（b）实测误差的分布Fig.6Measurement of pointing accuracy(a)Thedistributionof138 stars in thesky; (b)Distributionof measured error.

跟踪误差实测：在 NVST望远镜上，2022年1月22日晚选取某一恒星做长时间的跟踪观测，加模型和不加模型的跟踪时长各为30分钟。实验结果如图7所示。7（a）是星像在探测器上的运动轨迹，圆点表示的是加了模型的星的运动轨迹，方块表示没加模型的星的运动轨迹，7（b）是望远镜30分钟内的跟踪误差统计。由图可知，模型修正前的跟踪误差为6.46角秒，模型修正后的跟踪误差为1.10角秒。

![](images/8d3249ef41faae55b4330d8421e522a1e70dfdd41c412e672af1d51661642e86.jpg)  
图7跟踪误差实测结果 (a)星象的运动轨迹（b）跟踪误差统计 Fig.7Measured results of tracking error(a) Star image trajectory(b) Tacking error statistics

# 4结论

地平式太阳望远镜主光轴、高度轴、方位轴和消旋轴的同心度是影响库德焦面跟踪误差的主要因素之一，由于难以实测这些轴在库德焦面的具体位置，所以夜天文望远镜上常用的TPOINT等软件无法对这类误差进行建模。为了提高地平式太阳望远镜库德焦面的指向跟踪精度，本文提出了一种基于支持向量回归构建库德焦面指向跟踪模型的新方法，并在NVST上进行了实测建模。实测结果也表明，新的模型可以有效校正库德焦面的指向跟踪误差。在模型改正之前，NVST在库德焦面的指向误差 RMS 是115.88角秒，30分钟跟踪误差是6.46 角秒。经过模型改正之后，NVST在库德焦面的指向误差RMS值是3.98角秒，30分钟跟踪误差是1.10角秒。由此可见，基于机器学习的支持向量回归建模方法能有效提高地平式太阳望远镜库德焦面的指向跟踪精度。

# Study on Pointing and Tracking Model of Coude Focal Plane of Altazimuth Solar Telescope

Liu Ronghui1,2， Liu Hui1， Mu Hengyu’， Liu Guangqian' (1 Yunnan Astronomical Observatory,Chinese Academy of Sciences,Kunming,Yunnan65o01,China; 2University of Chinese Academy of Sciences,Beijing10049,China)

Abstract: In order to improve the pointing and tracking accuracy of the coude focal plane of the altazimuth solar telescope.Firstly, this paper simulates the tracking error introduced on the coude focal plane when the main optical axis,azimuth axis,height axis and racemic axis of the folded optical axis of the horizon solar telescope are not concentric,and analyzes the complexity of the pointing and tracking error of the coude focal plane,This problem can't be solved by the usual night telescope focal pointing model. Then, the paper constructs pointing model based on support vector regresson,and carries out an experiment on NVST.The experimental results show that before the model correction, the maximum pointing error of NVST on the coude focal plane is 650.55 arcsec,RMS is 115.88 arcsec,and the 3O minutes tracking error is 6.46 arcsec； After model correction，the maximum pointing error is 25.02 arcsec,the RMS value is 3.98 arcsec,and the 30 minutes tracking error is 1.10 arcsec. It can be seen that the support vector regression modeling method based on machine learning can effectively improve the pointing and tracking accuracy of coude focal plane of altazimuth solar telescope.

Key words: Pointing and tracking accuracy; Pointing model; Altazimuth solar telescope; Coude focal plane; Support vector regression

# 参考文献：

[1]Liu Z,DengYY,YangDH,etal.Chinese GiantSolarTelescope (inChinese).Sci Sin-Phys MechAstron,2019,49:059604.  
[2]王欣，潘君驿.2.4m天文望远镜光学系统的设计及副镜检验的几种可能方案[J].云南天文台台刊,2002(02)：41-49.Wang X,PanJH.Optic System Designofa2.4mClass Telescopeand Several Methods forTesting the SecondaryMirror[J].Publications of Yunnan Observatory,20o2(O2):41-49.  
[3]LiuZ,XuJ,GuBZ,etal.NewVacumSolarTelescopeandObservationswithHighResolution[J].ResearchinAstronomyandAstrophysics,2014(6):705-718.  
[4]陈宇超,柳光乾.NVST的长期跟踪误差分析及改正[J].天文研究与技术,2016，13(2)：8.ChenYC,LiuGQ.TheErrorAnalysisndCorrectionofNVTsLong-TrTracking.AstronomicalResearchandTechnology,2016,13(2):8.  
[5]柳光乾，付玉，程向明．1米太阳望远镜光谱仪像旋转及消旋控制[J]．天文研究与技术，2012，9(1)：7.Liu GQFuYChengXMImage-FieldRotatioandControlofCounterRotationfortheSpectrographof the1mSolarTelescopeoftheYunnan Observatory.Astronomical Research and Technology, 2012,9(1):7.  
[6］张丽敏,明名,杨飞,等.大口径望远镜Coude光路光机结构设计研[J].光电工程，2011，38(5)：5.ZhangLM,Ming M,YangF,etal.Design forCoude Optic-mechanicalStructureofLargeAperture Telescope[J].Opto-ElectronicEngineering,2011,38(5):5.  
[7]刘辉,季凯帆,金振宇.机器学习在太阳物理中的应用[J].中国科学:物理学 力学 天文学，2019，v.49(10):105-117.Liu H,JiKF,JinZThaplcationofmacheleaminginolarphsics[J]CENACA:hsicachanica&Astrooica2019,v.49(10):105-117.  
[8]Cortes C,Vapnik V. Support-vectornetworks[J].Machine Learning,1995,20(3): 273-297.  
[9]徐佳宁,倪裕隆,朱春波.基于改进支持向量回归的锂电池剩余寿命预测[J].电工技术学报,2021,36(17):12.XuJN,NiYL,ZhuCB.Remaining UsefulLifePredictionforLithium-IonBateriesBasedonImproved Support Vectol  
Regression[J].Transaction of China Electrotechnical Society,1995,2O(3): 273