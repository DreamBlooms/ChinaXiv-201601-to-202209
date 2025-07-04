# AIMS太阳望远镜中像旋对稳像精度的影响分析

蒋佶松1²，姜爱民1,2（1．中国科学院国家天文台，北京100101;2.中国科学院空间天文与技术重点实验室，北京，100101;3．中国科学院大学，北京100049）

摘要：针对AIMS太阳望远镜地平式机架在跟踪目标时像场旋转的现象，研究了像旋对稳像系统校正精度的影响。首先理论分析了互相关因子算法和绝对差分算法在不同湍流强度及不同探测窗口大小时由像旋引起的计算误差。随后在光学分析软件ASAP中建立了包含装配误差的AIMS望远镜系统动态光学模型，统计了折轴系统装配误差在望远镜实时跟踪太阳运动时引起的像场平移及旋转。其中图像在半小时内的最大平移约为 $0 . 3 \mathrm { m m }$ ，最大像旋约为$2 0 0 ^ { \prime \prime }$ 。结果表明，在现有的误差分配情况下，装配误差引起的像旋对稳像精度的影响很小，而为了获得较高的稳像精度，互相关因子算法是首选的稳像算法，且在硬件处理速度允许的情况下，应该选择 $1 2 8 \times 1 2 8$ 像素的探测窗口。

关键词：像旋；太阳望远镜；轴系误差；稳像系统;中图分类号：P111 文献标识码：A

# 0引言

AIMS 太阳望远镜[主要用于中红外波段精确测量太阳磁场，系统主体为1m 的离轴格里高利双反射地平式望远镜系统，通过折轴光路将太阳光引入后端科学仪器，并且为减小附加偏振，采用五镜消旋结构消除像场旋转。AIMS系统对稳像部分提出的指标要求为稳像精度优于 $0 . 3 "$ ，探测帧频不小于2000帧/秒，系统0dB闭环误差带宽为 $5 0 \mathrm { { H z } }$ ，闭环时间在30秒以上。为了实现稳像的指标，需要有针对的对影响稳像精度的因素进行分析。

在地面望远镜系统中，引起成像面像场移动的因素有很多。一类为像场平移，主要由大气湍流[2、风扰[3、望远镜的指向和跟踪误差[4等引起；另一类为像场旋转，当地平式望远镜在跟踪目标时，由于高度轴和方位轴的运动，会导致成像面绕主光轴旋转。文献[5]和[6]利用光线追迹和矩阵光学等方法对抚仙湖1m太阳望远镜(NVST)的轴系运动及像旋进行了分析，文献[7]根据AIMS 望远镜离轴格里高利光学系统的特点对像旋进行了理论推导和计算。以上文献主要是从理想情况对太阳望远镜像旋问题进行讨论，但在望远镜的实际建造和装调过程中，不可避免的存在各种误差，这就需要根据实际的误差分配情况进一步的分析和验证。

由于稳像系统只能校正像场的平移，而对像旋没有校正作用，为了分析AIMS望远镜系统中像旋对稳像精度的影响，本文从理论上分析了两种稳像算法在不同湍流强度及不同探测窗口大小下由像旋引起的计算误差，并建立了包含装配误差的AIMS望远镜系统动态光学模型，统计出装配误差在望远镜实时跟踪太阳运动时引起的像场平移及旋转范围，为AIMS望远镜稳像控制系统的研制提供了参考。

# 1像旋对稳像精度影响的理论分析

# 1.1稳像算法介绍

太阳稳像系统中，对于米粒组织这类低对比度的扩展目标进行探测时，常用的图像位移探测算法为基于快速傅里叶变化的互相关因子算法(CFF,Covariance function in Fourierdomain)及绝对差分算法(ADF,Absolute difference function)[8]。假设参考图像为 $I _ {  { \boldsymbol { R } } } ( x , y )$ ，活动图像为 $I _ { \cal L } ( x , y )$ ，互相关因子算法的计算公式为：

$$
C _ { _ { L R } } ( x , y ) = I F F T \left\{ F F T \bigl [ I _ { _ { R } } ( x , y ) \bigr ] \times F F T ^ { ^ { \ast } } \bigl [ I _ { _ { L } } ( x , y ) \bigr ] \right\}
$$

其中， $F F T$ 和IFFT分别表示快速傅里叶变化和逆快速傅里叶变化， $\boldsymbol { C } _ { L R } ( x , y )$ 表示相关矩阵。

绝对差分的计算公式为：

$$
C _ { L R } ( x , y ) = \sum _ { i = 0 } ^ { M - 1 } \sum _ { j = 0 } ^ { M - 1 } \bigl | I _ { R } ( x , y ) - I _ { L } ( x + i , y + j ) \bigr |
$$

其中,参考图 $I _ {  { \boldsymbol { R } } } ( x , y )$ 的大小为 $M { \times } M$ ，活动图的大小为 $N { \times } N$ ，在互相关因子算法中 $\mathbf { M } { = } \mathbf { N }$ ，绝对差分算法中 $M { < } N$ 。

两幅图像的整像素偏移量 $( x _ { m } , y _ { m } )$ 为相关矩阵 $C _ { _ { L R } } ( x , y )$ 峰值(互相关因子算法为最大值，绝对差分算法为最小值)对应的位置。为了获得亚像素精度的偏移量，需要对相关矩阵的相关峰进行插值拟合，采用 $3 \times 3$ 抛物线插值法时在 $x$ 和 $y$ 方向的亚像素精度偏移量分别为：

$$
x _ { p } = x _ { m } - \frac { 1 } { 2 } \frac { s _ { 1 , 0 } - s _ { - 1 , 0 } } { s _ { 1 , 0 } - 2 s _ { 0 , 0 } + s _ { - 1 , 0 } }
$$

$$
y _ { p } = y _ { m } - { \frac { 1 } { 2 } } { \frac { s _ { 0 , 1 } - s _ { 0 , - 1 } } { s _ { 0 , 1 } - 2 s _ { 0 , 0 } + s _ { 0 , - 1 } } }
$$

其中， $s _ { i , j }$ 表示相关矩阵 $C _ { L R } ( x , y )$ 在峰值附近 $3 { \times } 3$ 区域的幅值， $\left( x _ { p } , y _ { p } \right)$ 表示参考图与活动图在亚像素精度的偏移量。

# 1.2图像数据

对于太阳望远镜稳像系统，太阳米粒组织是最常见的探测目标，目前常见的太阳望远镜稳像系统探测窗口像素分辨率为 $0 . 3 ^ { \prime \prime } / \mathrm { p i x e l }$ 。为了尽可能模拟实际系统的相关参数，选用Hinode卫星米粒组织图像[，其像素分辨率约为 $0 . 0 5 ^ { \prime \prime } .$ /pixel，因此采用 $6 { \times } 6$ 像素合并的方法产生后续模拟所需图像。

地面太阳望远镜台址的大气相干长度 $r _ { 0 }$ 主要集中在 $5 { \sim } 2 0 \mathrm { c m }$ 的区间内[10],大气湍流是影响成像质量的主要因素。对于稳像探测系统，由于探测帧频很高，大气湍流的影响可以用平均短曝光光学传递函数(OTF,Optical Transfer Function)来表示[1]:

$$
H _ { _ { a t m } } \left( \rho \right) = \exp \left\{ - 3 . 4 4 { \left( \frac { \lambda f \rho } { r _ { 0 } } \right) } ^ { 5 / 3 } { \left[ 1 - { \left( \frac { \lambda f \rho } { D } \right) } ^ { 1 / 3 } \right] } \right\}
$$

其中， $\rho$ 为空间频率， $f$ 和 $D$ 分别为光学系统的焦距和口径， $\lambda$ 为波长， $r _ { 0 }$ 为大气相干长度，选择 $r _ { 0 }$ 为 $7 \mathrm { c m }$ 和 $1 5 \mathrm { c m }$ 表示湍流较强和较弱的两种情况。当以上参数已知时，对OTF进行逆傅里叶变化得到对应的点扩散函数(PSF,Point Spread Function)，通过PSF 卷积原始图像的方法就可以模拟不同大气湍流强度下太阳米粒组织的成像情况。图1(a)为无湍流影响0 ${ \bf \Phi } _ { r _ { 0 } = \mathrm { I n f } ) }$ 的图像，图1(b)和图1(c)分别为 $r _ { 0 }$ 在 $1 5 \mathrm { c m }$ 及 $7 \mathrm { c m }$ 时的图像，探测窗口大小为 $3 2 \times 3 2$ 像素，对应像方视场约 $1 0 ^ { \prime \prime }$ 。

![](images/ff526a4927c16768f3aa7ac1216d5ec9fd836f2eecd77914de344e3a0a46f130.jpg)  
图1不同大气湍流情况下的太阳米粒组织成像结果。(a)无湍流 $( r _ { 0 } { = } \mathrm { I n f } )$ ； (b) $r _ { 0 } { = } 1 5 \mathrm { c m }$ ；(c) $r _ { 0 } { = } 7 \mathrm { c m }$ Fig.1 Imaging results of solar granulation under different atmospheric turbulence condition.(a）No atmospheric turbulence $( r _ { 0 } { = } \mathrm { I n f } )$ ;(b) $r _ { 0 } { = } 1 5 \mathrm { c m }$ （c) $r _ { 0 } { = } 7 \mathrm { c m }$

# 1.3 像旋影响的计算方法

为了分析像旋对稳像精度的影响，计算步骤如下：

1)在原始大图中随机选定 $M$ 个坐标作为子窗位置，分别得到探测窗口大小为 $3 2 \times 3 2$ 、$6 4 \times 6 4$ 及 $1 2 8 \times 1 2 8$ 的 $M$ 组参考图;

2)以参考图中心为旋转轴将原始大图旋转 $k$ 度；

3)由于在稳像系统闭环校正后，参考图与活动图的相对平移量一般在0.2像素以内，因此对旋转后的图像进行 $N$ 组 $\pm 0 . 2$ 像素内的随机平移，在参考图相同位置分别得到包含平移及像旋的 $N$ 组活动图。

假设活动图的实际相对平移量为 $( x _ { \mathrm { m o d e l } } , y _ { \mathrm { m o d e l } } )$ ，根据稳像算法得到的估计值为( $( x _ { \mathrm { { o b s } } } ,$ $y _ { \mathrm { o b s } } )$ ，则稳像精度可以用距离误差表示：

$$
E \left( k , i , j \right) = \sqrt { \left[ x _ { _ { \mathrm { o b s } } } \left( k , i , j \right) - x _ { _ { \mathrm { m o d e l } } } \left( k , i , j \right) \right] ^ { 2 } + \left[ y _ { _ { \mathrm { o b s } } } \left( k , i , j \right) - y _ { _ { \mathrm { m o d e l } } } \left( k , i , j \right) \right] ^ { 2 } }
$$

其平均值和标准差分别为：

$$
M e a n \big ( k \big ) = \frac { 1 } { M N } \sum _ { i = 1 } ^ { M } \sum _ { j = 1 } ^ { N } E \big ( k , i , j \big )
$$

$$
S t d \left( k \right) = \sqrt { \frac { 1 } { \left( M - 1 \right) \left( N - 1 \right) } \sum _ { i = 1 } ^ { M } \sum _ { j = 1 } ^ { N } [ E \left( k , i , j \right) - M e a n \left( k \right) ] ^ { 2 } }
$$

其中， $k$ 为活动图旋转的角度， $k { = } 0 , 1 , { \ldots } , 5 , i$ 为随机子图位置编号， $i { = } 1 , 2 , . . . , M \left( M { = } 1 0 0 \right)$ $j$ 为图像的随机平移编号， $j { = } 1 , 2 , . . . N ( N { = } 1 0 0 )$ 。

# 1.4计算结果

图2(a\~f)为互相关因子算法和绝对差分算法在不同像旋角度下计算误差的比较结果，线条表示平均误差，阴影为对应的标准差。从图中可以看出：

1)随着旋转角度的增大，计算误差逐渐增大，但不同湍流强度下，当像旋角度在 $2 ^ { \circ }$ 以内，均值与标准差变化均较小。

2)当像旋角度为0时，互相关因子算法的平均误差在0.04 像素左右，且随着探测窗口的增大误差逐渐减小，当探测窗口为 $1 2 8 \times 1 2 8$ 像素时误差最小；绝对差分算法的平均误差在0.07像素左右，探测窗口大小对绝对差分算法几乎无影响。

3)当像旋角度在0到 $2 ^ { \circ }$ 之间时，互相关因子算法的误差随着像旋角度的增大而增大，绝对差分算法的误差有一定的减小。

0.4 0.4 0.4 32x32 32x32 32x32 arrnr geelrer 64x64 irrninir] 64x64 errrlgerlirsa 64x64 0.3 128x128 0.3 128x128 0.3 128x128 Max shift Max shift Max shift 0.2 0.2 0.2 0.1 arsrtsr 0.1 0.1 CFF,Inf CFF,15cm CFF,7cm 0 0L 0 0 1 2 3 4 5 0 1 2 3 4 5 0 1 2 3 4 5 Rotate angle/deg Rotate angle/deg Rotate angle/deg (a) (b) (c) 0.4 0.4 0.4 32x32 32x32 32x32 64x64 128x128 riris 0.3 64x64 128x128 e 64x64 128x128 Max shift Max shift Max shift 0.2 0.2 0.1 Ferer 0 ADF,Inf oL ADF,15cm 0 ADF,7cm 0 1 2 3 4 5 0 1 2 3 4 5 0 1 2 3 4 5 Rotate angle/deg Rotate angle/deg Rotate angle/deg (d) (e) (f)

# 2AIMS望远镜中的像旋

# 2.1AIMS 模型的建立

对于地平式望远镜，像旋主要由折轴系统跟踪目标引起，为了研究折轴系统误差对稳像精度的影响，在对AIMS望远镜及稳像系统的集成建模时，对建模工具提出了以下要求：1、能建立准确的光学系统模型并实现光线追迹成像。2、能方便的修改光学元件的参数，如平移、旋转等，实现对望远镜机架实时运动的模拟。综合考虑以上要求，选用了BRO(Braultresearch organizaition)公司开发的光学分析软件 ASAP(Advanced System Analysis Program)作为集成建模的主体软件。它能够快速的进行光线追迹，实现对折射、衍射、干涉的高精度仿真分析。除此之外，通过ASAP脚本语言，不仅可以方便的搭建光学系统并修改任意光学元件参数，也能通过调用外部可执行程序对数据进行交互处理。

图3为通过ASAP软件建立的AIMS望远镜系统的示意图。系统主要分为五个部分：离轴格里高利系统(M1\~M2)、折轴系统(M3\~M6)、消旋镜(MR1\~MR5)、准直折轴系统(M7\~M8)及稳像系统(M9、探测CCD、计算与控制单元)。在折轴系统中，M4到M5的主光线与高度旋转轴重合，M6反射的主光线与方位旋转轴重合。稳像系统中，摆镜采用PI公司的 S-340压电偏摆台，其最大偏转角为±1mrad，稳像光路总焦距为 $1 2 5 \mathrm { m m }$ ，因此摆镜能校正的成像面最大平移为：

$$
S = 2 \times 1 2 5 \times \mathrm { t a n } \left( 2 \times 0 . 0 0 1 \mathrm { r a d } \right) = 0 . 5 \mathrm { m m }
$$

![](images/c1c8f005fa94c95523ae6b1f8b49612ee0a5c1a271413197449093f91446e6fb.jpg)  
图3AIMS太阳望远镜系统Fig.3 Aims solar telescope system

# 2.2AIMS望远镜机架运动及像旋分析

在AIMS望远镜中，当光线经过离轴格里高利系统后成像在库德焦点时，成像目标会绕主光轴旋转，造成其旋转的原因主要有两个：一是由地平式结构引起的物方视场旋转，二是由折轴系统反射镜之间的相对运动引起的像方视场旋转。

对于地平式结构，高度轴与方位轴均不与地轴平行，需要各运动轴系的配合才能实现对天体的跟踪。由于天球上的不同天体在地平坐标系中的运动不同步，导致所跟踪目标及周围目标绕视轴中心旋转，所对应的旋转角通常用星位角 $P$ 表示[]：

$$
P = a \tan \left( { \frac { \sin H } { \cos \delta \tan \phi + \sin \delta \cos H } } \right)
$$

$$
\cdot
$$

$$
-
$$

其中， $\phi$ 为观测地的纬度， $\delta$ 和 $H$ 分别为天体的赤纬和时角， $A$ 和 $E$ 分别为天体的方位角和高度角。

在图3所示AIMS太阳望远镜系统中，M1\~M4 镜的位置相对固定并随着高度轴和方位轴旋转，M5\~M6镜的位置相对固定并随着方位轴旋转，而M7所在的准直折轴系统与地面

固定，仅起到提供准直光束的作用。在望远镜跟踪目标天体时，随着高度轴的转动，M4与M5之间产生相对旋转，方位轴转动时M6与M7之间产生相对旋转，因此像方视场的旋转角为两轴转动角度之和，成像目标最终的旋转角为[12]：

$$
P _ { \theta } = P + A + E
$$

当消旋镜的旋转速度是像场旋转速度的二分之一时，就可以起到消除地平式望远镜像场旋转的效果。AIMS望远镜暂定台址冷湖的位置为北纬 $3 8 ^ { \circ } 3 3 ^ { \prime } 1 4 ^ { \prime \prime }$ ，东经 $9 3 ^ { \circ } 4 8 ^ { \prime } 4 4 ^ { \prime \prime }$ ，以太阳为跟踪目标，望远镜在两分两至时的运动情况如图4所示。

![](images/4b2a473ca0dfc69ace634669569241d8bf812fd7e92883562bb9500498b82824.jpg)  
图4轴系及物、像方视场随时间的旋转角度。(a)春分；(b)夏至；(c)秋分；(d)冬至 Fig.4Therotationangleofaxis,objectandimage fieldwithtime.(a)Springequinox;(b)Summersolstice;(c)Autumnalquiox;(d) Winter solstice

# 2.3误差分配及成像统计结果

表1为参考AIMS系统设计方案给出的折轴系统偏心偏轴和位置间隔误差，为获得误差对成像的影响，产生误差分配范围内均匀分布的随机误差带入AIMS 望远镜模型中，高度轴、方位轴及消旋镜按图4中的角度运动，时间间隔为0.5h，采用光线追迹的方法得到轴上点$\mathbf { O } _ { 1 }$ 及两个正交方向轴外点 $\mathbf { O } _ { 2 }$ 、 $\mathrm { O } _ { 3 }$ 的运动结果，共统计1000次，得到的望远镜像点运动分布情况如图5所示。需要注意的是由于M3与M6为准直补偿元件，在实际的工程装配过程中，通过调节M3与M6可以有效的降低成像的漂移，因此根据表1得到的结果仅代表未经优化的装配情况。

图6(a)和图6(b)分别为根据图5中像点相对运动计算得到的像场最大平移及旋转统计情况。可以看出，在夏至时像场的平移及旋转都是最大的，冬至时最小，春秋分时位于两者之间。在夏至时像场的平移最大约为 $0 . 3 \mathrm { m m }$ ，在摆镜 $0 . 5 \mathrm { m m }$ 平移量校正范围内，而像场旋转最大约为 $2 0 0 ^ { \prime \prime }$ ，也在上文分析得出的对稳像精度影响较小的 $2 ^ { \circ }$ 像旋范围内。

# 表1折轴系统误差分配

Tab.1 Error distribution of coude optical systems   

<html><body><table><tr><td>Element</td><td>Surface decenter/mm</td><td>Surfacetilt/deg</td><td>Surface position/mm</td></tr><tr><td>M4</td><td>±0.400</td><td>±0.017</td><td>±2.000</td></tr><tr><td>M5</td><td>±0.500</td><td>±0.017</td><td>±2.000</td></tr><tr><td>MR</td><td>±1.000</td><td>±0.017</td><td>±2.000</td></tr><tr><td>M7</td><td>±1.000</td><td>±0.017</td><td>±2.000</td></tr><tr><td>M8</td><td>±1.000</td><td>±0.017</td><td>±2.000</td></tr></table></body></html>

![](images/f5d5feca99e05f7bdb7bb0c2375efd3c638d5ac10f7f384bd87e4a03f70b9716.jpg)  
图5两分两至时不同装配误差下像点的运动分布。(a)春秋分；(b)夏至；(c)冬至。 Fig.5Themotiondistrbutioofimagewithdieretassemblyerors iequnoesandsolstices.(a)SpringandAutumaleqnoxes;( Summer solstice;(c)Winter solstice.

![](images/ef4a356473318f1ecd1bb069ef6c8aca484300060d73bf4ac93eee1e8fc9d7bb.jpg)  
图6两分两至时不同装配误差下像点的平移及旋转统计结果。(a)平移统计结果；(b)旋转统计结果。 Fig6Thestatiscalrsultsofimaesiftdotatiwiteresmblyrsiqosdsosis.()Statisticalsultsf image shift; (b) Statistical results of image rotate.

# 3结论

本文首先通过理论分析得出互相关因子算法和绝对差分算法在不同湍流强度及不同探测窗口大小时像旋引起的计算误差，结果表明当像旋角度在 $2 ^ { \circ }$ 以内时对稳像精度的影响较小，而为了获得较高的稳像精度，互相关因子算法是首选的稳像算法，且计算误差随着探测窗口的增大而减小，因此在硬件处理速度允许的情况下，应该选择 $1 2 8 \times 1 2 8$ 像素的探测窗口。随后通过光学分析软件ASAP建立了包含机架及消旋镜实时运动的AIMS太阳望远镜模型，统计了折轴系统误差在望远镜实时跟踪太阳运动时引起的成像平移及旋转结果。其中图像在半小时内的最大平移约为 $0 . 3 \mathrm { m m }$ ，在摆镜最大 $0 . 5 \mathrm { m m }$ 平移量校正范围内，最大像旋约为 $2 0 0 ^ { \prime \prime }$ ，在对稳像精度影响较小的 $2 ^ { \circ }$ 像旋范围内。因此，在现有的误差分配情况下，装配误差引起的像旋对稳像精度的影响很小，并且在实际装配中可以通过调节M3与M6 对成像漂移进行校正，图像的平移及旋转还将进一步缩小。

# The Influence of lmage Rotation on Accuracy of Stabilization System of AlMS Solar Telescope

Jiang Jisong1,2, Jiang Aiming1,2 (1．National Astronomical Observatories,Chinese Academy of Sciences,Beijing lOo1o1,China; 2．KeyLaboratoryof Space Astronomy and Technology,Chinese Academyof Sciences,Beijing 1Ool01,China; 3.University of Chinese Academy of Sciences,Beijing 10oo49, China）

Abstract: Aiming at the phenomenon of image rotation when the coude system of AIMS solar telescope tracks the targets,the influence of image rotation on the correction accuracy of image stabilization system is studied.Firstly,the calculation error caused by the image rotation of the covariance function in Fourier domain and the absolute difference function at different atmospheric turbulence intensity and different detection window sizes is theoretically analyzed. Then,the dynamic optical model of AIMS solar telescope is established in the optical analysis software ASAP.The imaging shift and rotation by the coude system error in the real-time tracking of the sun's motion are calculated. The maximum shift and rotation of the image within half an hour are about $0 . 3 \mathrm { m m }$ and $2 0 0 ^ { \prime \prime }$ respectively. The results show that under the existing error distribution situation,the image rotation caused by the assembly error has litle effect on the image stabilization accuracy.In addition,in order to obtain higher image stabilization accuracy,the covariance function in Fourier domain is the preferred image stabilization algorithm. And the detection window with $1 2 8 \times 1 2 8$ pixels should be selected as far as the hardware processing speed allows.

Key word: Image rotation; Solar telescope; Axis error; Image stabilization system

# 参考文献：

[1] XIAY B,XIE YONGJUN,WANG PENG,etal.Evaluationon miror seeing forAIMSsolartelescope[C].SPIE,2019,11052:1105200.  
[2]王子跃，任德清．差分像运动视宁度优化监测法[J].天文研究与技术,2019,16(1):114-122.  
[3]MACMYNOWSKIDG,ANGELIGZ,VOGIATZIS K,et al.Parametric modelingand control of telescope wind-inducedvibration[C]. SPIE,2004,5497:266-277.  
[4]马锦，顾伯忠．地平式望远镜轴系误差对指向精度和跟踪精度的影响[J].天文研究与技术,2011,8(2):132-138..  
[5]鞠青华,李语强,熊耀恒.1.2m地平式望远镜视场旋转角的理论计算[J].天文研究与技术,2009.(1):28-35..  
[6]柳光乾，付玉，程向明.1米太阳望远镜光谱仪像旋转及消旋控制[J].天文研究与技术,2012,9(1):86-92..  
[7]GONGYB,XIEYJDONGRG,etal.ModelingandanalysisofimagerotationfortheMSsolaropticaltelescopeC].SE,19,11052:1105207.  
[8]饶长辉，姜文汉，凌宁，等．低对比度扩展目标跟踪算法[J].天文学报,2001,42(3):329-338.  
[9] National Astronomical Observatory of Japan.Solar granulation [EB/OL]. (2007-01-10)[2019-10-18]  
http://darts.isas.jaxa.jp/solar/hinode  
[10]楼柯，刘忠，吴铭蟾，等．云南红外太阳塔选址及其结果[J].云南天文台台刊,2002(4):60-67.  
[11]郑建华，饶长辉．不同像素尺度下太阳表面米粒结构相关跟踪算法的有效性分析[J].大气与环境光学学报,2010,5(5):327-333.  
[12]胡企千，姚正秋.天文望远镜设计[M].北京:中国科学技术出版社,2013,193-196.