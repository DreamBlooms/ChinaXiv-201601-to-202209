# 利用光变曲线估计猎鹰九号火箭末级的旋转状态研究

苏向泽1²，汤儒峰¹，李荣旺13,\*，李语强1，3（1.中国科学院云南天文台，云南昆明 650011；2.中国科学院大学，北京 100049；3.中国科学院空间目标与碎片观测重点实验室，江苏 南京 210034)

摘要：光度观测是地基观测空间目标的主要观测手段之一，利用空间目标的光度信息能够估计空间目标的相关特征信息。为了更好地了解空间目标旋转状态，选取具有代表性的猎鹰九号火箭末级作为研究对象，由其光变信息研究旋转状态。首先利用云南天文台1.2米光学望远镜获取猎鹰九号火箭末级的光度数据，再对目标星等进行斜距归一化，得到目标光变信息并分析目标星等随时间变化的光变曲线，估计其大致的旋转周期，再由相位离散最小化方法计算出会合周期。根据太阳、目标和测站之间的位置关系、惯性主轴指向、旋转轴指向、初始相位等因素，采用姿态旋转矩阵来计算理论星等，利用最小二乘原则确定惯性主轴方向及初相角度、旋转轴指向。最后给出了猎鹰九号火箭末级的旋转周期，会合周期以及旋转轴指向等参数，为后续开展其他空间目标光度信息研究提供参考。

关键词:空间碎片的旋转状态；光变曲线；火箭体；相位离散最小化；猎鹰九号;光度模型

中图分类号：P173.6

# 0.引言

随着人类航天活动的开展，地球轨道停留了越来越多的空间碎片，空间碎片的存在对在轨运行的航天器以及载人航天活动带来很大的威胁。其中火箭末级也属于空间碎片，是指将目标航天器推入运行轨道的最后一级火箭，在完成任务后会绕地球按一定的轨道飞行。火箭体尺寸、重量大且运行姿态不受控制，会严重影响附近正常工作的航天器，一旦相撞会产生更多的空间碎片产生连锁效应。因为无法控制火箭体的姿态和轨道，为了了解这些大型空间碎片的运行状态，需要对其进行观测获取来其相关信息。地基光度观测是最常用的观测手段，可以获取目标的光度信息。由于目标的光度信息与目标的运动、姿态、形状等不同因素息息相关，使用空间态势感知的不同方法可以分别将这些信息分离出来，从而得到目标的相关信息。

国内外分析空间目标光度数据的方法主要有基于相位角的分析方法、基于极值点的分析方法[12]、基于光变曲线周期的分析方法[13]以及基于模型构建的分析方法等。前三种方法主要根据观测得到的光变曲线进行分析，针对不同种类的空间目标分析方法也有所不同。但是这三种方法的适用目标具有局限性，且只能针对某一特征进行分析。基于模型构建的分析方法主要包括基于非线性滤波的方法[2、基于封闭面元模型分析方法和基于机器学习方法等，其中基于非线性滤波的方法是分析空间目标特性的主要研究方法，通过构建目标运动和观测模型来预测其运动和姿态，需要精确的先验参数才能得到收敛的结果，不适用于先验参数较少的目标。本文主要根据观测到的火箭体光度数据，对处理后的光变曲线进行周期分析来确定火箭体的旋转周期，通过目标相位角和形状参数建立光度模型，通过比对观测光变曲线和理论计算得到的光变曲线估计旋转轴的指向。根据得到的收敛区间证明了构建光度模型方法的可行性，为后续研究其他类型的空间目标姿态研究提供参考。

# 1．猎鹰九号火箭末级信息

本文选择猎鹰九号火箭末级（编号：42968）作为研究目标。猎鹰九号火箭是 SpaceX公司研制的重型运载火箭，是现役运载能力最大的火箭之一，且其末级火箭的尺寸较其他火箭体更大，更易进行预报和进行光度观测，同时大尺寸也使得其对于正常工作的航天器影响更大。了解其姿态可以更好地预测它的运动从而使其他正常工作的航天器更好地规避碰撞风险。截止到2020年5月30日已经发射了83次。根据 SpaceX公司发布的数据，42968号目标是猎鹰九号中v1.2型火箭的火箭末级，如图1所示。其去除下底面引擎后长约为 $9 . 4 4 \mathrm { { m } }$ 底面直径为 $3 . 6 6 \mathrm { { m } }$ 。其轨道为大椭圆轨道，近地点 $2 3 0 \mathrm { k m }$ ，远地点33819km。具体信息如表1所示：

# 表1目标42968相关信息

Table 1informations of target 42968   

<html><body><table><tr><td>目标名称</td><td>国际编号</td><td>类型</td><td>发射日期</td><td>轨道周期</td><td>轨道倾角</td><td>近地点</td><td>远地点</td></tr><tr><td>FALCON 9 R/B</td><td>2017-063B</td><td>火箭体</td><td>2017-10-11</td><td>593.83min</td><td>27. 80</td><td>230km</td><td>33819km</td></tr></table></body></html>

![](images/c79e063e1c9b9b90434619d9a4b945a97bb99a854b685f066df7f053ca7bf64d.jpg)  
图1猎鹰九号火箭尺寸信息

# 2.光度数据的获取流程

本文采用地基光度测量的方法获取目标的光度信息，利用云南天文台 $1 . 2 \mathsf { m }$ 望远镜对目标进行观测。将采集到的图像进行本底和平场改正、流量定标、斜距归一化等处理后得到目标的视星等及星等随时间变化的光变曲线。

# 2.1图像采集

观测前从space-track 网站上获取卫星的轨道数据，一般为双行根数格式(TLE)。TLE 的预报精度不高，应用到激光测距中需要修正，张训方等人研究了实时修正预报的方法[15]，而本文观测使用的望远镜视场较大，可以不进行轨道修正。使用云南天文台 $1 . 2 \mathsf { m }$ 望远镜及30cm 导星镜、配套控制系统、CCD相机对目标进行观测并采集平场、定标星光度信息及目标的光度信息，使用SourceExtractor[14]软件提取定标星和待测目标的流量值信息。

观测时间：2019年12月13日，2019年12月15日，每次观测时间约为30分钟，具体信息如表2所示。图2是使用1.2m望远镜拍摄的目标光度图像，处于图像中间的亮点即为观测目标。图3表示13日和15日观测时段内目标相对于望远镜方位角和高度角随时间变化的曲线，以极坐标的形式表示出来。13日用实线表示，15日用虚线表示，每段曲线的初始方位和俯仰角通过曲线中标注的点表示出来，可以看出在观测时段内目标的方位和高度变化并不大。

表2：观测信息  
Tab.2 the information of observation   

<html><body><table><tr><td>观测日期</td><td>观测距离</td><td>观测时间</td><td>时长</td><td>曝光时间</td></tr><tr><td>2019年12月13日</td><td>20458.54—24682.70</td><td>12:21:59.86--12:52:23.33</td><td>31min</td><td>0.5s</td></tr><tr><td>2019年12月15日</td><td>17166.77--21655.37</td><td>14:08:25.15--14:37:33.19</td><td>29min</td><td>0.5s</td></tr></table></body></html>

![](images/cfc5823c3e91f6312038dcb9b2234801244fa60de161fcf6298c4ad6757dfe6c.jpg)  
图2目标光度图像

Theelevationandazimuth of42968inobserve time 0

![](images/6f4bf82c72f864d5caafecfd8957f959380b77eed0d4f0060a651eabd1a98f29.jpg)  
Fig2object's luminosity figure   
图3观测时段内目标方位角与俯仰角  
Fig 3space object's azimuth and elevation in observe periods

# 2.2平场、本底处理及流量定标

在采集到本底与平场图像后进行归一化处理。计算经过平场处理后的图像灰度值公式如下：

$$
\begin{array} { r } { G _ { a f } = \frac { G _ { O } - G _ { b i a s } } { G _ { f l a t } } } \end{array}
$$

其中 $G _ { O }$ 是原始图像的灰度值， $G _ { b i a s }$ 是本底灰度值， $G _ { f l a t }$ 是标准平场灰度值

根据现有的星表选择定标星并进行观测，由于望远镜视场较小，不能用场星定标，因此本文选择的是landolt 星表里的恒星G162，采集到其光度图像后经过本底、平场处理得到处理后的图像，这一过程是消除望远镜光学系统对于目标光度的影响。将处理后的图像与星

表中的位置进行比对来确定恒星，得到恒星光度流量值，再除以其曝光时间，得到定标星单位时间内的流量值 $f _ { c a l }$ ，其视星等值已知为 $M _ { c a l } = 1 3 . 0 1 2$ ，这样即可以获得仪器的星等零点：

$$
M _ { 0 } = 2 . 5 \cdot \log _ { 1 0 } ( f _ { c a l } ) + M _ { c a l }
$$

从而可以计算得到目标的视星等：

$$
M _ { o b j } = - 2 . 5 \cdot \log _ { 1 0 } ( f _ { o b j } ) + M _ { 0 }
$$

其中 $f _ { o b j }$ 为待测目标的流量值。

# 2.3异常点及斜距归一化处理

在使用SourceExtractor软件提取流量过程中会识别到非待测目标的流量信息，从而得到错误的星等值。在观测过程中望远镜对目标进行跟踪，因此目标在图像中的位置相对固定，因预报误差而缓慢变化，因此可在目标轨道预报精确或目标运动速度不快的情况下可以根据目标在fits图像中的坐标将错误识别的目标剔除如图4所示，从而计算得到正确的星等。图4表示了13日及15日的异常点在CCD坐标的相关信息，可以看到一部分点离散在目标坐标区域外，根据这一信息将坐标错误的点剔除。这一方法不能将被恒星污染、云层遮挡这样的情况剔除掉，而这两种情况下目标的星等值会发生突变，所以可以将距离平均光变曲线0.5星等的数据点fits图像与在平均光变曲线上数据点的fits图像进行比对，确认得到的是否是待测目标的光度信息，图4中15日目标坐标区域中的菱形点就是被恒星污染的异常点。

将异常点剔除后得到了关于目标的光度数据。为了去除待测目标斜距对于目标光度的影响，需要对得到的星等进行斜距归一化处理，通常将卫星斜距归一化到1000km 处。根据公式：

$$
\begin{array} { r } { M _ { u n i } = M _ { o b j } - 5 \cdot \log _ { 1 0 } ( \frac { R _ { o b j } } { R _ { u n i } } ) } \end{array}
$$

得到归一化后的星等 $M _ { u n i }$ 。其中 $R _ { o b j }$ 为卫星距测站的斜距， $R _ { u n i } = 1 0 0 0 k m .$ 0

图5为剔除异常点、斜距归一化后的光变曲线,其中横坐标表示时间，以s为单位；纵坐标表示星等。由图可见光度随时间的变化呈现出周期性特征，而且在观测时段内星等的变化周期基本保持不变，大致为125s。整体光变曲线曲线也有一个缓慢的变化趋势，这两天的星等整体有缓慢增大的趋势，曲线振幅在逐渐变大。下一步会针对这两条光变曲线进行分析以确定目标的旋转速率及旋转轴的指向。

![](images/a04fbb6ac1c7f2ca0b27d49f1bd60478c8fc4114152fa65d46ad22cb28a29644.jpg)  
图4目标异常点坐标分布  
Fig4Outlier of space object's coordinate distribution   
图5观测时段内目标42968的光变曲线  
Fig.5The lightcurve of 42968 in observation periods

Lightcurve of Satellite 42968 in 20191213 Lightcurve of Satellite 42968 in 20191215 -0.2 -0.1 0.0 To:2019-12-15714:08:25.149 0.0 To:2019-12-13712:21:59.855 0.1 wanmubea 0.2 M M AM MAAA wahputga 0.2 ? ： 二 A 0.3 4400 WWW WWW WW 445 \*\*\*\* 0.6 0.8 0 250 500 750 1000 1250 1500 1750 0 250 500 750 1000 1250 1500 1750 Time/s Time/s

# 3、火箭体旋转状态分析

火箭体属于空间碎片且其运行轨道和运行姿态不受地面控制。描述火箭体旋转状态主要包

括旋转周期、旋转轴指向和旋转初相位这几个参数。本节主要根据第2节得到的目标光变曲线来确定目标的旋转周期和旋转轴指向，并分析得到的结果。

# 3.1会合周期分析

会合周期是由一种相对周期，取决于卫星、测站及太阳的位置关系。根据网球拍定理[1]可知，自由刚体会逐渐绕着目标最大转动惯量的轴旋转。42968 号火箭末级入轨时间较长（从2017年10月发射至观测时刻约两年)，其几何形状近似为圆柱体，所以可以合理假设目标绕着垂直于目标侧面的轴旋转，对于测站来说观测到的星等变化周期只是旋转周期的一半，故其会合周期大约是 250s。为了更加精确地确定会合周期，本文采用了相位离散最小化方法(Phase Dispersion Minimization,简称 PDM)将数据点分段进行分析得到最优解。PDM的原理是将观测数据按试验周期计算，根据这些试验周期的计算相位矢量，将这些相位矢量按(0,1)区间划分为不同的子区间，计算子区间与整个区间的数据方差，使得二者之比最小的试验周期即是最精确的会合周期。

空间目标的离散观测值可以分为两个矢量：星等矢量m及观测时间矢量t，其中第i个观测点可以表示为： $( m _ { i } , t _ { i } )$ ，假设在一个观测时段内共有N个观测离散点，即 $i = 1 , 2 , \dots , N _ { \ast }$ 则星等矢量m的方差 $\sigma ^ { 2 }$ 为：

$$
\begin{array} { r } { \sigma ^ { 2 } = \frac { \sum ( m _ { i } - \overline { { m } } ) } { N - 1 } } \end{array}
$$

其中 $\begin{array} { r } { \overline { { m } } = \frac { \sum ( m _ { i } ) } { N } } \end{array}$ Σ(mi)是m的均值.

在星等矢量m中选取 $\mathtt { M }$ 个不同的数据子集，假设每个数据子集中包含 $n _ { j }$ 个数据且数据子集的样本方差为 $s _ { j } ^ { 2 } \left( { \mathrm { j } } { = } 1 , 2 , \cdots , \mathbb { M } \right)$ 。则所有数据集的总方差 $s ^ { 2 }$ 为：

$$
\begin{array} { r } { s ^ { 2 } = \frac { \sum ( n _ { j } - 1 ) s _ { j } ^ { 2 } } { \sum n _ { j } - M } } \end{array}
$$

假设 $\vec { P }$ 为试验周期矢量， $\vec { P }$ 中的元素为 $p _ { k }$ ，根据试验周期计算时间矢量的相位矢量 $\vec { \phi }$ 。对于相位矢量 $\vec { \phi }$ 中的每个元素 $\phi _ { i }$ 来说，

$$
\phi _ { i } = \frac { t _ { i } } { p _ { k } } - [ \frac { t _ { i } } { p _ { k } } ]
$$

其中 $[ \frac { t _ { i } } { p _ { k } } ]$ 表示 $\frac { t _ { i } } { p _ { k } }$ 的整数部分，即相位矢量 $\vec { \phi }$ 为时间向量与试验周期取模后的结果。

假设从m中选取的 $\mathtt { M }$ 个子数据集有相似的相位矢量 $\vec { \phi }$ 。将全相位间隔 $( 0 , 1 )$ 分为固定大小的等长区间。定义统计量： $\Theta = { \frac { s ^ { 2 } } { \sigma ^ { 2 } } }$ ，其中 $\sigma ^ { 2 }$ 和 $s ^ { 2 }$ 分别由公式（6）和公式（7）得到。如果$p _ { k }$ 不是正确的周期， $\Theta \approx 1$ ；如果 $p _ { k }$ 是正确的周期，0在试验周期内会达到最小值，且趋近于0.

由火箭体光度数据， $\vec { t }$ 为观测时段的时间点，m为观测时段的目标星等值，会合周期大约为250s，所以试验周期矢量 $\vec { P }$ 取值为200—300，步长取0.1。相位间隔步长取0.1，即将（0，1）区间划分为10个子区间。使用上述参数及相位离散最小化方法计算得到更为准确的火箭体会合周期。

图6表示了两个观测时段内试验周期及通过相位离散最小化方法计算得到的试验周期对应的0值。由图6的两条曲线可以发现在试验周期内都存在一个极小值点，13日在0最小处时对应的周期为249.23s，由图6中的下图可以得到15日在0最小处对应的周期为248.29s。

![](images/dd557c8301df7b1b966a5c895f3f56c18059b9f85d21483a5cdb973a8e64a248.jpg)  
图6火箭体会合周期分析  
Fig.6Analysis ofRocket Body's Synodic Period

# 3.2旋转轴指向分析

空间目标的旋转状态包含旋转周期及旋转轴指向，其会合周期已经通过PDM方法得到，对于此观测目标，其星等变化周期比较稳定且相对于测站及太阳的相位角变化不大，所以该目标的会合周期可近似看作其旋转周期。

在赤道惯性坐标系下旋转轴以矢量 $\vec { P }$ 表示，转化为赤经 $\alpha$ 、赤纬δ表示：

$$
P = { \left[ \begin{array} { l } { P \cdot x _ { i } } \\ { P \cdot y _ { i } } \\ { P \cdot z _ { i } } \end{array} \right] } = { \left[ \begin{array} { l } { c o s \delta c o s \alpha } \\ { c o s \delta s i n \alpha } \\ { s i n \delta } \end{array} \right] }
$$

在分析旋转轴指向之前需要建立目标光度模型。火箭体本身并不发光而是反射太阳光，测站观测到的目标图像其实是火箭体的反射光，与目标表面材料、目标形状等因素相关、太阳一目标一测站之间的几何关系相关，三者的几何关系如图7所示，其中 $\overrightarrow { u _ { o b s } }$ 和 $\overrightarrow { u _ { s u n } }$ 分别表示目标到地球和太阳的方向单位矢量， $\overrightarrow { u _ { n } }$ 表示目标表面面元的法线方向单位矢量， $\overrightarrow { u _ { o b s } }$ 和$\overrightarrow { u _ { s u n } }$ 之间的夹角即相位角 $i _ { P A } , \overrightarrow { u _ { h } }$ 是相位角平分线方向单位矢量。由目标的双行根数得到其位置信息，13日的双行根数历元为2019-12-12T18:50:17Z，15日的双行根数历元为2019-12-14T10:29:09Z，太阳的位置信息由JPL的 $\mathrm { d e 4 3 0 }$ 星历给出，测站位置：（25.0299N,102.7974E)，海拔高度为 $1 9 9 1 . 8 3 \mathrm { m }$ 。将这三者的位置转换到惯性系下表示为位置矢量，根据三者的位置矢量即可求出 $\overrightarrow { u _ { o b s } }$ ， $\overrightarrow { u _ { s u n } }$ ，则相位角 $i _ { P A }$

$$
\begin{array} { r } { i _ { P A } = a r c c o s ( \frac { \overrightarrow { u _ { o b s } } \cdot \overrightarrow { u _ { s u n } } } { \vert \overrightarrow { u _ { o b s } } \vert \cdot \vert \overrightarrow { u _ { s u n } } \vert } ) } \end{array}
$$

观测时段内相位角的变化如图8所示

![](images/7fcb04b5949c9324072124d516ddbfee08a25ef249dd59c58b8490c587d734c0.jpg)  
图7太阳-目标-测站之间的几何关系

![](images/e90a83bcfa76e8aecebf1a629727f84938db5a0c56ee5815aafe4fd0961c964f.jpg)  
Fig.7The geometry relationship of sun-space object-observation station   
图8观测时段内目标相位角变化曲线  
Fig.8variation trend of object's phase angle in observation period

火箭体的形状可看作圆柱体，根据此假设可以计算火箭体的等效面积。假设太阳光在火箭体表面为漫反射，圆柱体侧面的法线方向定义为：圆柱的上下底中心连线，向上底方向为正，圆柱体侧面面元的法线方向为垂直于面元方向向外，对圆柱体侧面面元积分就可以得到侧面的等效面积。太阳入射角为 $i _ { s u n }$ ，卫星一测站方向矢量与法线方向矢量夹角为 $i _ { o b s }$ 。则圆柱体侧面等效效面积为：

$$
A _ { c y e a } = \int _ { s } ^ { } \sin ( i _ { s u n } ) c o s \varphi \cdot \sin ( i _ { o b s } ) \cos ( \varphi - \theta ) \cdot h \frac { d } { 2 } d \varphi = \frac { A _ { c y } \cdot \sin ( i _ { s u n } ) \cdot \sin ( i _ { o b s } ) } { 4 \cdot \pi } \cdot [ s i n \theta + ( \pi - \pi ) \cdot \sin ( \theta ) ]
$$

0) · cos0]

其中 $\theta$ 满足：

$$
\begin{array} { r } { c o s \theta = \frac { \cos ( i _ { P A } ) - \cos ( i _ { s u n } ) * \cos ( i _ { o b s } ) } { \sin ( i _ { s u n } ) * \sin ( i _ { o b s } ) } } \end{array}
$$

其中 $A _ { c y }$ 为圆柱体侧面面积, $\varphi$ 为圆柱体柱坐标系的方位角参数， $h$ 为圆柱体高度， $d$ 为圆柱体底面直径。

圆柱体上下两底可近似看作平面，平面的等效面积为：

$$
A _ { p l e a } = A _ { p l } \cdot \cos ( i _ { s u n } ) \mathrm { c o s } ( i _ { o b s } )
$$

不考虑下底的火箭体喷嘴，火箭体上下底的法线方向分别沿着上下底平面从里向外，分别使用公式(11)计算火箭体上下底的等效面积。根据火箭体侧面及上下底的等效面积就可以确定火箭体的等效面积从而计算目标的模型光度。

给定火箭体姿态初始参数： $\Delta _ { 0 }$ ， $\Delta _ { 1 }$ ：目标惯性主轴与旋转轴夹角； $\lambda _ { 0 }$ ， $\theta _ { 0 }$ ：目标旋转轴指向， $\lambda _ { 0 }$ 即惯性系的赤经， $\theta _ { 0 }$ 为惯性系的余纬（旋转轴与惯性系 $\mathrm { ~ z ~ }$ 轴的夹角)； $\phi _ { 0 }$ ：旋转初始相位； $T _ { 0 }$ ：目标旋转周期。随着时间的变化相位 $\phi$ 也在变化， $\begin{array} { r } { \phi = \phi _ { 0 } + d t \cdot \frac { 2 \pi } { T _ { 0 } } } \end{array}$ ，dt 表示时间的变化。将 $\Delta _ { 0 } , \Delta _ { 1 } , \lambda _ { 0 } , \theta _ { 0 } , \phi$ 通过姿态旋转矩阵从惯性坐标系转换到星体坐标系下表示，并将这些旋转矩阵相乘得到新的矩阵 $R$ ， $R$ 和表面法向量的点积即为不同时刻下法向量在星体坐标系下的指向。再根据太阳单位入射辐射流量密度照射在有效面积上反射的流量及太阳的视星等计算出模型星等值。根据前文所述，旋转周期近似采用会合周期，目标绕最大转动惯量轴(短轴)转动，即惯性主轴与旋转轴夹角 $\Delta _ { 0 } = 0$ 0 $\Delta _ { 1 } = 9 0$ ，旋转周期 $T _ { 0 } = 2 4 9 . 2 3 s$ 只需要确定描述旋转轴指向的两个角 $\lambda _ { 0 }$ ， $\theta _ { 0 }$ 及旋转初相 $\phi _ { 0 }$ ，通过参数搜索，以最小二乘为判据确定旋转参数。

以13日的数据为例，已知 ${ | \Delta _ { 0 } = 0 ^ { \circ } , \Delta _ { 1 } = 9 0 ^ { \circ } , T _ { 0 } = 2 4 9 . 2 3 s }$ 。遍历三个参数： $\lambda _ { 0 } \in [ 0 , 3 6 0 ]$ 步长为： $\displaystyle \boldsymbol { \mu } _ { 0 } \in [ 0 , 1 8 0 ]$ ，步长为1； $\phi _ { 0 } \in [ 0 , 3 6 0 ]$ ，步长为10。每次循环计算观测时段内观测星等与模型星等之差的方差。遍历完所有参数后得到总体方差分布，以 $\phi _ { 0 }$ 划分共有36 个0-C 方差分布图，在每个方差分布图中横坐标表示旋转轴指向 $\lambda _ { 0 }$ ；纵坐标表示旋转轴指向 $\theta _ { 0 }$ ，发现每张0-C方差分布图都有两个方差极小值区域，分别位于每张子图中的左下方及右上方，且关于中心点对称。这是由于建立光度模型时假设火箭体上底及下底面积相等导致的对称性，根据这一推论可知在两个方差极小值区域分别存在使得方差最小的参数组合。在每个方差极小值区域内都有两个最小方差收敛区域，0-C方差最小值点在其中一个方差收敛区间内。

计算每张等高线图内最小方差及所对应的 $( \lambda _ { 0 } , \theta _ { 0 } , \phi _ { 0 } )$ 组合，得到了36 个最小方差点，再在这36 种组合中选择最小方差对应的组合： $\lambda _ { 0 } , \theta _ { 0 } , \phi _ { 0 } = ( 2 1 2 , 1 1 6 , 1 2 0 )$ 。图9中左图给出了最小方差组合所对应的方差分布图，等高线颜色越接近蓝色表示方差越小，越接近红色表示方差越大。根据0-C方差的对称性可知在方差分布图的左下方也应存在使得0-C方差最小的参数组合，计算关于左下方差极小值区域0-C方差最小值的参数组合，得到了图9右图，方差极小值点对应的参数为： $\lambda _ { 0 } , \theta _ { 0 } , \phi _ { 0 } = ( 3 2 , 6 4 , 2 9 0 )$ ，处于0-C 方差收敛区间内。

根据以上得到的两个参数组合，将其分别代入到光度模型中，并比对模型光变曲线和观测光变曲线，比对结果如图10所示。图10中的左右图分别对应图9中左右图得到的参数，图中标识出了每个参数组合对应的0-C方差值，可以发现左图0-C方差值更小。不过右图的方差与左图方差相差并不大并且目标星等的变化趋势也很好的拟合了出来。以左图为例可以看到光度模型将火箭体光度整体的变化趋势表示了出来，包括振幅逐渐变大的趋势及每个周期星等极大值点的变化。不过对于每个周期星等极小值点处的光度突变光度模型并没有很好的拟合出来，这一部分的突变可能是由于火箭体侧面镜反射导致的，而光度模型只考虑了目标漫反射的情况。

根据以上分析可以确定卫星编号为42968 的目标旋转轴指向可能包含两种组合，分别是$\lambda _ { 0 } , \theta _ { 0 } = ( 2 1 2 , 1 1 6 )$ 及 $\lambda _ { 0 } , \theta _ { 0 } = ( 3 2 , 6 4 )$ ，对应的旋转初相位分别是120，290，二者之差为170度，而且求得的两个旋转轴指向赤纬 $\lambda _ { 0 }$ 相差180度，两个余纬 $\theta _ { 0 }$ 与 $9 0 ^ { \circ }$ 之差的绝对值都为26度，正好对应了光度建模时火箭末级上下底面积相等而导致求得的两个旋转轴指向关于惯性系原点对称的情况。

![](images/e9a395dfeeb1d0dc0b0abe2d143bb45c75dcf7c355b0d90e1e1d9e4fd1c2610a.jpg)  
图913日0-C方差分布等高线图

![](images/3edeb6fcf4eed35a8a7934a8bc461627d25ec4aaf403060f56903acb6b2efac8.jpg)  
Fig9distribution of variance between observation value and calculate Value's diference in 2O19.12.13   
图1013日模型及观测光变曲线  
Fig.10lightcurve of observation and calculate in 2O19.12.13

# 4.结论

本文通过分析猎鹰九号火箭体(NORAD 编号：42968)的光变曲线确定其旋转状态。根据2019年12月13日和15日实测的数据得到的目标光变曲线存在明显的周期性。这说明目标的运动姿态较为稳定。由于在两天的观测时段内目标相位角的不同造成了归一化处理后的目标绝对星等的细微差别。由光变曲线的周期并通过PDM 确定了目标的会合周期：13日该目标的会合周期为249.23s，15日该目标的会合周期为248.29s，在两天的时间里目标的周期并没有发生的明显变化。通过建立光度模型的方法计算目标的模型星等，搜寻旋转轴指向和旋转初始相位，以模型星等与观测星等之差的方差最小为判据确定目标的旋转轴指向。本文计算了13日的0-C方差，由于模型假设火箭体的上底及下底面积相等所以得到了两个可能的旋转轴指向，分别为 $\lambda _ { 0 } , \theta _ { 0 } = ( 2 1 2 , 1 1 6 )$ 及 $\lambda _ { 0 } , \theta _ { 0 } = ( 3 2 , 6 4 )$ ，若要更加精确地确定旋转轴指向还需更多的观测数据及完善光度模型。

# 参考文献：

[1]Doyle Hall，John Africano，David Archambeault,etal.AMoS Observationsof NASA’s IMAGE Satellite[C]．The Advanced Maui Optical and Space Surveillance Technologies Conference.2006.   
[2] Richard Linares，Moriba K.Jah，JohnL.Crassidis,etal.Astrometric and photometric data fusion for inactive space object feature estimation[J].Acta Astronautica.20l4,99,1-15   
[3]R.F.Stellingwerf.Period determination using phase dispersion minimization[J].The Astrophysical [4]J.C.Hinks and J.L.Crassidis.Angular velocity bounds via light curve glint duration[C].In AIAA Guidance,Navigation,and Control Conference,page O627，2016   
[5］李荣旺，李语强，周钰．利用双行根数计算太阳相位角的精度评估［J].天文研究与技术,2014(04),369-377   
[6]汤儒峰，李语强等．基于高重频卫星激光测距测算AJISAI卫星自转速率[J].中国激光,2015(06),287-292   
[7] Thomas Schildknecht.Optical surveys for space debris[J],The Astronomy and Astrophysics Review， 2007(01),41-111   
[8]李斌成.空间目标的光学特性分析[J].光学工程,1989(02),21-26   
[9]王阳，杜小平，范椿林.地基光度曲线反演空间目标特征技术研究进展[J].科学通报,2017,62(15),1578-1590   
[10]陈思，黄建余，王东亚.基于归一化光变函数的空间目标识别研究[J].飞行器测控学报.2013,32(03),273-280 [1]Mark S.Ashbaugh,Carmen C.Chicone,Richard H.Cushman.The Twisting Tennis Racket[J].Journalof Dynamicsand Differential Equations,1991,3(1),67-85.   
[12]VrbaF，Hutter D,Shankland P,etal.Asurveyof geosynchronous satelliteglints[C].In:Proceedings of the Advanced Maui Optical and Space Surveillance Technologies Conference.Kihei: Maui Economic Devepment，2009 [13]Hall D. Separating attitude and shape effects for non-resolved objects[C].In:Proceedings of the Advanced Maui Optical and Space Surveillance Technologies Conference. Kihei:Maui Economic Devepment，2007   
[14] E.BERTIN.SExtractor v2.13 User’s manual． Institut d'Astrophysique & Observatoire de Paris.   
[15]张训方，赵雪，李荣旺等．非合作目标激光测距预报的实时修正方法研究[J].天文研究与技术,2019(01),25-32

# Research on estimating the rotation state of the upper stage of Falcon 9 Rocket by using lightcurve

Su Xiangzel1²,Tang Rufeng',LiRongwang13,LiYuqiang3

1.Yunnan Observatories，Chinese Academy of Science，Kunming 65O216，Chin&

2.University of Chinese Academy of Science，Beijing 1OoO49，China

3.Key Laboratory of Space Object&Debris Observation,PMO,CAS,Nanjing 210o34,China）

Abstract: Lightcurve measurement is one of the main methods for ground-based space-target observation,as the photometric information of the targets can be used to estimate their relevant characteristics. Aiming at better understanding of the rotational state of the space target, a representative upper stage of the Falcon-9 rocket is selected as the object to analyze its rotational state through light curve study. Firstly, the photometric data of the upper stage of the Falcon-9 rocket is obtained with the $1 . 2 – \mathrm { m }$ optical telescope of the Yunnan Observatories. Then the target's magnitude is processed with slant-range normalization. The photometric changing information is obtained,and the time-dependent light curve of the target magnitude is analyzed. Accordingly, the approximate rotation period of the target is estimated, and then the accurate synodic period is calculated by the phase discrete minimization method.Based on the position relationship between the Sun,the target and the observatory,the main inertial axis pointing,the rotation axis pointing, the initial phase and other factors,the theoretical magnitude is calculated using the attitude rotation matrix.The main inertial axis direction,the initial phase angle and the rotation axis pointing direction are determined as well. Finally, the parameters such as the rotational period, the synodic period and the pointing direction of the rotational axis of the upper stage of the Falcon 9 rocket are given, which can serve as a reference for following studies on the photometric information of other space targets.

Key Words: Space debris rotation; Lightcurve;Rocket body; Phase dispersion minimization;Falcon 9 rocket; Photometric model