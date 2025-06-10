# 一种天线副面位置快速重构方法研究

苏照阳1,2,，许谦 $^ { 2 , 3 , 4 ^ { * } }$ ，王娜 2,3,4，朱春花1\*  
(1.新疆大学物理科学与技术学院，乌鲁木齐，830046)(2.中国科学院新疆天文台，乌鲁木齐，830011)  
(3.中国科学院射电天文重点实验室，乌鲁木齐830011)  
(4.新疆射电天体物理重点实验室，乌鲁木齐 830011)

摘要：为了快速获取副反射面随天线俯仰角变化的位置，并通过调整机构对副面位置进行修正来提高天线综合性能，提出一种虚拟双目视觉测量方法，通过高速相机与平面镜组成的虚拟双目视觉系统对天线观测时副面位置进行模拟实验,获取被测物随实验平台空间移动产生的位置变化图像，并对图像进行预处理、去噪、边缘检测、特征点提取等操作，重建了被测物随实验平台移动而在三维方向上的运动情况，重建结果在三个方向上误差均小于 $1 \%$ ，表明该方法具有较高的测量精度，能够较好的对副面位置情况进行重构。

关键词：天线副面；虚拟双目视觉；位置；重构中图分类号：P111.44 文献标识码：A 文章编号：

# 1引言

随着科学技术的发展，射电望远镜观测技术取得了长足的进步，对天文学的发展起到了极大的推动作用。与此同时，大型双反射面天线的口径、频段也在不断增加，对天线的指向精度、增益等指标要求越来越高[1]。天线副面位置与主面位置的匹配对天线指向精度而言起着至关重要的作用。但在天线实际运行过程中，其副反射面的位置会受到风荷、重力、温度等因素的影响而发生变化，导致主副面位置匹配失调，使天线的综合性能下降，对天线的效率及指向精度产生影响[2]。因此，如何快速、实时、准确地重构天线副面位置，对提高天线指向精度有十分重要的意义。

为获得高精度天线副面位置，王锦清等人推导并仿真了副面位姿和全息口径面相位的解析关系，通过口径面相位数据，计算获得上海天马65米望远镜（以下简称“TM65m”）副面位姿随俯仰角改变的变化情况[3]。许谦等人基于应变传感器和模态叠加原理，分别通过采集天线发生变形后副反射面撑腿、副反射面自身应变值重构了副反射面的位姿[4]。Martin

Suss 等人采用摄影测量，对天线副面随俯仰角变化而产生的位置变化进行测量，获得了x、y、z三个方向上的位置变化曲线。该方法获取数据量较大，对计算体系要求较高，不能够获取天线副面的实时位置[5]。Tonino Pisanu等人和江永琛等人都采用 PSD 法测量了天线副面随俯仰角变化而在x、y两个方向上产生的位置变化。该方法可以获取天线副面在x、y两个方向上的高精度位置，但在 $z$ 轴方向上的位置需要通过其他方法来获得[6-7]。侯雷雨等人采用激光跟踪仪测量了副面调整机构在 $0 ^ { \circ }$ 和 $4 5 ^ { \circ }$ 条件下副面的位姿情况，该方法具有较高的精度，在对天线副面调整机构的高精度标定中起到很好的作用，但代价太大[8]。尹航等人基于惯性测量和嵌入式技术，解决了大型射电望远镜副面摆动较大无法精确定位问题。但该方法使用惯性测量技术，会造成误差累积，系统误差越来越大，需要及时调整[9]。

本文将采用虚拟双目测量系统，对天线副面在空间中移动过程中的三维位置进行模拟测量，得出目标物体在空间运动的三维运动曲线。该方法只需要对目标物体进行一次拍摄，就可以获得副面在该位置的三维信息，不需要很复杂的程序，同时不会造成误差累积。运用该方法不仅能节约成本，且能够解决双目视觉左右相机同步难的问题。

# 2虚拟双目视觉原理

交汇式双目视觉是基于同一物体在两图像中的视差以及两相机之间的平移和旋转关系对该物体空间三维位置进行求解[10]。其原理如图1所示。为降低成本，同时提高拍摄同步性，使用两个平面镜与一台高速相机组成虚拟双目视觉系统，该方法与交汇式双目视觉原理基本相同，其原理如图2所示。

![](images/b068b44a4a274f769d1d5aa1912739fa7ef9f807254f297f28ed02bff1e932e6.jpg)  
图1交汇式双目视觉原理

![](images/320a4d911de2cb082f1b17776038a6ff841fb14766eb2348275e7dcdfe618cad.jpg)  
图2虚拟双目视觉原理  
Fig.2 The principle of virtual binocular vision

Fig.1 The principle of convergent binocular vision

如图2， $ { \mathrm { P } } ( \mathrm { x } , \mathrm { y } , \mathrm { z } )$ 为空间中任意一点，会分别在左镜面和右镜面上成像,高速相机对左右镜面上成的像进行拍摄，对所拍摄图像进行分割，会得到两幅关于点 $ { \mathrm { P } } ( \mathrm { x } , \mathrm { y } , \mathrm { z } )$ 的像，相当于有两台虚拟相机对点 $ { \mathrm { P } } ( \mathrm { x } , \mathrm { y } , \mathrm { z } )$ 进行拍摄。其分析方法与真实双目视觉分析方法比较起来基本相同[10]。

$\mathrm { O } _ { \mathrm { w } } – \mathrm { X } _ { \mathrm { w } } \mathrm { Y } _ { \mathrm { w } } Z _ { \mathrm { w } }$ 为世界坐标系， $\mathbf { O } _ { 1 ^ { - } } \mathbf { X } _ { 1 } \mathbf { Y } _ { 1 } Z _ { 1 }$ 为左相机摄像机坐标系， $\mathrm { O } _ { 2 } { - } \mathrm { X } _ { 2 } \mathrm { Y } _ { 2 } \mathrm { Z } _ { 2 }$ 为右相机摄像机坐标系。 ${ \bf P } _ { 1 }$ 点为空间点 $\mathrm { P _ { w } }$ 在左相机所成像中的像点， ${ \bf P } _ { 2 }$ 点为空间点 $\mathrm { P _ { w } }$ 在右相机所成像中的像点。

双目视觉测量中，世界坐标系与摄像机坐标系的关系为：

$$
\begin{array} { r l } & { z _ { c } \Bigg [ \begin{array} { l } { u } \\ { \nu } \\ { 1 } \end{array} \Bigg ] = \left[ \begin{array} { l l l l } { 1 \ / \ d x } & & { 0 } & { u \circ } \\ { 0 } & & { 1 \ / \ d y } & & { \nu \circ } \\ { 0 } & & { 0 } & & { 1 } \end{array} \right] \left[ \begin{array} { l l l l } { f } & { 0 } & { 0 } & { 0 } \\ { 0 } & { f } & { 0 } & { 0 } \\ { 0 } & & { 0 } & { 1 } & { 0 } \end{array} \right] \left[ \begin{array} { l l } { R } & { T } \\ { 0 } & & { 1 } \end{array} \right] \left[ \begin{array} { l } { x \cdot w } \\ { y \cdot w } \\ { z _ { w } } \\ { 1 } \end{array} \right] = } \\ & { \left[ \begin{array} { l l l l } { f \ / \ d x } & & { 0 } & & { u \circ } & { 0 } \\ { 0 } & & { f \ / d y } & & { \nu \circ } & { 0 } \\ { 0 } & & { 0 } & & { 1 } \end{array} \right] \left[ \begin{array} { l l } { R } & & { T } \\ { 0 } & & { 1 } \end{array} \right] \left[ \begin{array} { l } { X \cdot w } \\ { y \cdot w } \\ { z _ { w } } \end{array} \right] \left[ \begin{array} { l l } { K } & & { 0 } \end{array} \right] \left[ \begin{array} { l l } { R } & { T } \\ { 0 } & & { 1 } \end{array} \right] X \ = \ M . } \end{array}
$$

式中： $( \mu \upsilon )$ 为像点在图像像素坐标系中的坐标，（ $\mathrm { \nabla { X } _ { w } \ Y _ { w } \ Z _ { w } }$ ）为目标点在世界坐标系中的坐标。 $\mathrm { ~ K ~ }$ 为摄像机的内参矩阵，由 f/dx、f/dy、μ、 $\mathfrak { v }$ 组成，由摄像机自身决定。R为世界坐标系与摄像机坐标系之间的旋转矩阵，T为世界坐标系与摄像机坐标系之间的平移矩阵。R、T称为摄像机的外参矩阵。若要求得目标点在三维空间的准确位置，就必须求得摄像机的内参矩阵和摄像机的外参矩阵，这个过程称为摄像机的标定。

若摄像机标定已完成，且像点 ${ \bf P } _ { 1 }$ 、 ${ \bf P } _ { 2 }$ 的像素坐标均已获取，那么由式（1）可得：

$$
z 1 { \left[ \begin{array} { l } { u 1 } \\ { \nu _ { 1 } } \\ { 1 } \end{array} \right] } = M , { \left[ \begin{array} { l } { x  w } \\ { y w } \\ { z w } \\ { 1 } \end{array} \right] } = { \left[ \begin{array} { l l l l } { m 1 1 } & { m 1 2 1 } & { m _ { 1 3 1 } } & { m _ { 1 4 1 } } \\ { m 2 1 1 } & { m 2 2 1 } & { m _ { 2 3 1 } } & { m _ { 2 4 1 } } \\ { m 3 1 1 } & { m 3 2 1 } & { m 3 3 1 } & { m _ { 3 4 1 } } \\ { m 3 1 1 } & { m 3 2 1 } & { m _ { 3 3 1 } } & { m _ { 3 4 1 } } \end{array} \right] } { \left[ \begin{array} { l } { x _ { w } } \\ { y _ { w } } \\ { z _ { w } } \\ { 1 } \end{array} \right] }
$$

$$
z 2 { \left[ \begin{array} { l } { u _ { 2 } } \\ { \nu _ { 2 } } \\ { 1 } \end{array} \right] } = M 2 { \left[ \begin{array} { l } { x _ { w } } \\ { y _ { w } } \\ { Z _ { w } } \\ { 1 } \end{array} \right] } = { \left[ \begin{array} { l l l l } { m _ { ^ { 1 1 2 } } } & { m _ { ^ { 1 2 2 } } } & { m _ { ^ { 1 3 2 } } } & { m _ { ^ { 1 4 2 } } } \\ { m _ { ^ { 2 1 2 } } } & { m _ { ^ { 2 2 2 } } } & { m _ { ^ { 2 3 2 } } } & { m _ { ^ { 2 4 2 } } } \\ { m _ { ^ { 3 1 2 } } } & { m _ { ^ { 3 2 2 } } } & { m _ { ^ { 3 3 2 } } } & { m _ { ^ { 3 4 2 } } } \end{array} \right] } { \left[ \begin{array} { l } { x _ { w } } \\ { y _ { w } } \\ { z _ { w } } \\ { 1 } \end{array} \right] }
$$

式中：（ $\left( \mathsf { \mu } _ { 1 } \mathsf { \upsilon } _ { 1 } \mathsf { \up1 } \right)$ 、（ $\mu _ { 2 } \upsilon _ { 2 } \ 1$ ）为像点 ${ \bf P } _ { 1 }$ 、 ${ \bf P } _ { 2 }$ 的齐次像素坐标， $( \mathbf { x } _ { \mathrm { w } } \mathbf { y } _ { \mathrm { w } } \mathbf { z } _ { \mathrm { w } } \mathbf { 1 }$ ）为目标点P 的齐次世界坐标。对式（2）、（3）进行拆分并消去未知数 $z _ { 1 } , \ z _ { 2 }$ 可得到关于 $\mathbf { X } _ { \mathrm { W } }$ 、yw、 $z _ { \mathrm { w } }$ 的四个线性方程组成的方程组：

$$
\left\{ \begin{array} { l l } { { \left( u { \ i } m { 3 1 1 } - m { 1 1 1 } \right) x _ { w } + \left( u { \ i } m { 3 2 1 } - m { 1 2 1 } \right) y _ { w } + \left( u { \ i } m { 3 3 } 2 - m { 1 3 } \right) z _ { w } = m { 1 4 1 } - u { 1 m 3 } 4 1 } } \\ { { \left( { \nu } { 1 m 3 1 } - m { 2 1 1 } \right) x _ { w } + \left( { \nu } { 1 m 3 } { 2 1 } - m { 2 2 1 } \right) y _ { w } + \left( { \nu } { 1 m 3 } { 2 } 2 - m { 2 3 } { 1 } \right) z _ { w } = m { 2 4 1 } - \nu { 1 m 2 } 4 1 } } \\ { { \left( u { 2 m 3 } { 1 2 } - m { 1 1 } { 2 } \right) x _ { w } + \left( u { 2 } m { 3 } { 2 } 2 - m { 1 2 } { 2 } \right) y _ { w } + \left( u { 2 } m { 3 } { 3 } { 2 } - m { 1 3 } { 2 } \right) z _ { w } = m { 1 4 } 2 - u { 2 m 3 } 4 2 } } \\ { { \left( { \nu } { 2 } m { 3 1 } { 2 } - m { 2 1 } { 2 } \right) x _ { w } + \left( { \nu } { 2 } m { 3 } { 2 } { 2 } - m { 2 2 } { 2 } { 2 } \right) y _ { w } + \left( { \nu } { 2 } m { 3 } { 3 } { 2 } - m { 2 3 } { 2 } \right) z _ { w } = m { 2 } q { 2 } 4 2 - \nu { 2 m 3 } 4 2 } } \end{array} \right.
$$

对式（4）采用最小二乘法求解，即可求得目标点在空间内的准确三维坐标[1]。

# 3实验及图像处理

测量系统如图3所示，由一台高速相机，两个平面镜，一个棋盘格标定板，以及高精度四维平台和一台电脑组成。通过电脑控制平台在X、Y、Z三个方向移动，高速相机对被测物运动图像进行采集并通过数据线传输到电脑，并由电脑对图像进行处理计算。实验获取图片如图4所示：

![](images/e7ce7a9bb8fc03fae88829ea0626759a85cb8d03f0c7d929ba5a8817bf0910f8.jpg)  
图3：测量系统  
Fig.3 The measuring system   
图4：实验获取图片  
Fig.4 The pictures obtained from the experiment

0

在获取实验图像后，我们对图像进行分割，分别得到左右虚拟相机的图像，并采用张正友标定法对摄像机进行标定，标定结果为：

$$
K l = \left[ \begin{array} { c c c } { { 8 3 5 5 . 8 2 3 1 4 } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { 8 4 3 6 . 6 8 8 1 8 } } & { { 0 } } \\ { { - 7 4 . 2 8 1 3 1 } } & { { 3 7 3 . 9 7 0 2 5 } } & { { 1 } } \end{array} \right]
$$

$$
K r = { \left[ \begin{array} { l l l } { 8 4 7 8 . 4 1 7 3 4 } & { 0 } & { 0 } \\ { 0 } & { 8 4 8 2 . 7 6 5 7 1 } & { 0 } \\ { 4 7 9 . 5 0 0 0 0 } & { 5 3 9 . 5 0 0 0 0 } & { 1 } \end{array} \right] }
$$

$$
R = \left[ \begin{array} { c c c } { { 0 . 9 9 0 0 1 } } & { { - 0 . 0 3 3 0 7 } } & { { 0 . 1 3 7 0 5 } } \\ { { 0 . 0 3 4 7 9 } } & { { 0 . 9 9 9 3 4 } } & { { - 0 . 0 1 0 1 9 } } \\ { { - 0 . 1 3 6 6 2 } } & { { 0 . 0 1 4 8 6 } } & { { 0 . 9 9 0 5 1 } } \end{array} \right]
$$

经过摄像机标定得到摄像机内外参数，就可以对目标物体进行测试。在拍摄过程中，由于设备自身影响，以及拍摄环境中噪声、光照等因素的影响，会对拍摄图片的成像质量造成干扰，使图像质量下降。故在得到图片之后，需要对图片进行一系列的处理，来提高图像的质量，尽可能的接近目标物体的真实情况。

以其中一幅图像为例，如图5中a图像所示为虚拟相机所得到的图片。首先，通过摄像机的标定参数，对图片进行畸变修正，并且对修正过的图像进行掩膜处理，保留特征点的像素信息，将特征点以外的像素值设置为0。这个过程称之为图片的预处理，处理过后的图像如图5中b图像所示。

接下来对图像进行滤波。通过滤波来去除由于拍摄环境中光线对图片造成的影响，主要有椒盐噪声与高斯噪声。采用高斯滤波能够在很大程度上保留图像的边缘信息[I]。滤波过后的图像如图5中c图像所示。

对于滤波处理过后的图片进行边缘检测，提取像素值发生突变的位置，所构成的曲线即为特征点的边缘。边缘检测结果如图5中d图像所示。

![](images/5e33b34f0a09b204d58d575e5b7f30173fd90d3193cba8da6726c228ffe31ff0.jpg)  
图5：图像处理  
Fig.5 The image processing

对于经过一系列图像处理过后的图像，对其特征点中心坐标进行提取，并以左虚拟相机的摄像机坐标系为世界坐标，由式（4）可得特征点在空间的三维坐标。

模拟实验分为两组进行，第一组模拟实验两平面镜距离被测物 $0 . 5 \mathrm { m }$ 左右，第二组模拟实验两平面镜距离被测物 $2 \mathrm { m }$ 左右。

在第一组模拟实验过程中， $\mathbf { x }$ 方向以 $5 \mathrm { m m }$ 为一个步长，y方向以 $1 \mathrm { m m }$ 为一个步长，z方向以6mm为一个步长，特征点在空间三维位置坐标重构结果如表1所示：

表1：特征点三维坐标重构结果  
Tab.1 The result of 3D coordinate reconstruction of feature points   

<html><body><table><tr><td></td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>X</td><td>50.437</td><td>55.477</td><td>60.525</td><td>65.570</td><td>70.609</td><td>75.638</td><td>80.669</td><td>85.621</td></tr><tr><td>y</td><td>23.282</td><td>24.285</td><td>25.289</td><td>26.291</td><td>27.298</td><td>28.303</td><td>29.309</td><td>30.314</td></tr><tr><td>Z</td><td>1076.258</td><td>1070.216</td><td>1064.247</td><td>1058.299</td><td>1052.358</td><td>1046.386</td><td>1040.359</td><td>1034.395</td></tr></table></body></html>

由三维坐标绘制x、y、z方向运动图像如图6所示：

![](images/5136e5dc3132d98a80c0696c192c4beed29ac383328e36a2460b9774341d3a29.jpg)  
Fig.6 The coordinate change diagram

已知平台在x、y、z方向上的移动步长，通过相邻两点坐标之差可求出计算结果与实际运动距离之间的误差，计算结果与实际运动距离之间的误差如表2所示：

Tab.2 The error between the calculated result and the actual motion distance   

<html><body><table><tr><td></td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td></tr><tr><td>×</td><td>0.8%</td><td>0.96%</td><td>0.9%</td><td>0.6%</td><td>0.58%</td><td>0.62%</td><td>0.96%</td></tr><tr><td>y</td><td>0.3%</td><td>0.4%</td><td>0.2%</td><td>0.7%</td><td>0.5%</td><td>0.6%</td><td>0.5%</td></tr><tr><td>Z</td><td>0.7%</td><td>0.51%</td><td>0.86%</td><td>0.98%</td><td>0.46%</td><td>0.45%</td><td>0.6%</td></tr></table></body></html>

为了排除数据的偶然性，在第二组实验过程中选择不同步长进行测量， $\mathbf { x }$ 方向以 $3 \mathrm { m m }$ 为一个步长，y方向以 $1 \mathrm { m m }$ 为一个步长， $z$ 方向以 $7 \mathrm { m m }$ 为一个步长，特征点在空间三维位置坐标重构结果如表3所示：

表2：计算结果与实际运动距离误差  
表3：特征点三维坐标重构结果 Tab.4 The result of 3D coordinate reconstruction of feature points   

<html><body><table><tr><td></td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>X</td><td>153.921</td><td>156.943</td><td>159.968</td><td>162.986</td><td>166.009</td><td>169.022</td><td>172.048</td><td>175.065</td></tr><tr><td>y</td><td>47.927</td><td>46.920</td><td>45.915</td><td>44.911</td><td>43.902</td><td>42.899</td><td>41.893</td><td>40.883</td></tr><tr><td>Z</td><td>2689.469</td><td>2682.529</td><td>2675.566</td><td>2668.563</td><td>2661.520</td><td>2654.457</td><td>2647.436</td><td>2640.378</td></tr></table></body></html>

由三维坐标绘制x、y、z方向运动图像如图7所示：

![](images/3a94113f56a2744b9fa44b052f8d884abe741986793d30ea0b2c1259ae922c19.jpg)  
图6：坐标变化图  
图7：坐标变化图  
Fig.7The coordinate change diagram

# 本组模拟实验计算结果与实际运动距离误差如表4所示：

# 表4：计算结果与实际运动距离误差

Tab.5 The error between the calculated result and the actual motion distance   

<html><body><table><tr><td></td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td></tr><tr><td></td><td>0.73%</td><td>0.83%</td><td>0.59%</td><td>1.0%</td><td>0.43%</td><td>0.84%</td><td>0.59%</td></tr><tr><td>y</td><td>0.7%</td><td>0.49%</td><td>0.48%</td><td>0.86%</td><td>0.24%</td><td>0.62%</td><td>0.99%</td></tr><tr><td>Z</td><td>0.85%</td><td>0.53%</td><td>0.04%</td><td>0.61%</td><td>0.89%</td><td>0.29%</td><td>0.83%</td></tr></table></body></html>

由两组模拟实验结果x、y、z方向坐标变化图上能够看出，计算出的 $\mathbf { x }$ 、y、z三个方向上的坐标变化与实验平台在三维方向上的运动有较好的线性关系。通过计算结果与实际运动距离之间的误差，可以看出相邻两点之间的距离与实际平台运动距离之间的误差均小于 $1 \%$ 能够较好的符合真实情况。且当两平面镜与被测物距离为 $0 . 5 \mathrm { m }$ 时求得结果误差与两平面镜同被测物距离为 $2 \mathrm { m }$ 时求得误差均小于 $1 \%$ ，证明该算法有较好的稳定性。

# 4虚拟双目视觉与真实双目视觉的比较

为评价虚拟双目视觉精度与真实双目视觉精度的差距，评估虚拟双目视觉的可行性，采用真实双目视觉对被测物三维位置进行测量。两相机与被测物距离为 $2 \mathrm { m }$ 左右，实验平台在X、Y、Z三个方向分别以 $5 \mathrm { m m }$ 、 $1 \mathrm { m m }$ 、6mm为步长进行移动，通过对图像的处理与一系列的计算，得到被测物在空间中的三维位置如表5所示：

表5：真实双目视觉特征点三维坐标重构结果  
表6：真实双目视觉计算结果与实际运动距离误差  

<html><body><table><tr><td colspan="9">Tab.5 The results of 3D coordinate reconstruction of feature points in real binocular vision</td></tr><tr><td>1</td><td></td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>X</td><td>10.728</td><td>15.753</td><td>20.777</td><td>25.800</td><td>30.820</td><td>35.841</td><td>40.863</td><td>45.882</td></tr><tr><td>y</td><td>32.112</td><td>33.117</td><td>34.122</td><td>35.126</td><td>36.131</td><td>37.135</td><td>38.139</td><td>39.143</td></tr><tr><td>Z</td><td>2044.055</td><td>2050.086</td><td>2056.115</td><td>2062.145</td><td>2068.172</td><td>2074.197</td><td>2080.221</td><td>2086.244</td></tr></table></body></html>

计算结果与实际运动距离之间误差如表6所示：

Tab.8 The error between the calculation result of real binocular vision and the actual motion distance   

<html><body><table><tr><td></td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td></tr><tr><td>X</td><td>0.50%</td><td>0.48%</td><td>0.46%</td><td>0.40%</td><td>0.42%</td><td>0.44%</td><td>0.38%</td></tr><tr><td>y</td><td>0.51%</td><td>0.49%</td><td>0.45%</td><td>0.47%</td><td>0.44%</td><td>0.43%</td><td>0.37%</td></tr><tr><td>z</td><td>0.51%</td><td>0.48%</td><td>0.50%</td><td>0.45%</td><td>0.41%</td><td>0.40%</td><td>0.38%</td></tr></table></body></html>

对比虚拟双目视觉计算误差与真实双目视觉计算误差，两者均小于 $1 \%$ ，虚拟双目视觉与真实双目视觉之间的误差之间的差距仅为 $0 . 3 \%$ 左右，说明虚拟双目视觉能够较好的达到真实双目视觉的精度，同时能够说明该方法具有较好的可行性。

# 5结论

本文通过对虚拟双目视觉原理及构成系统的研究，通过高速相机与平面镜组成的虚拟双目视觉系统对天线副面随俯仰角变化而在空间中产生的位置变化进行模拟实验，重建了被测物随实验平台移动而在三维方向上的运动情况，结果能够较好的符合真实情况。同时对虚拟双目视觉与真实双目视觉进行对比，表明该方法具有较好的可行性，为快速重建和修正天线副面位置提供了一个有效的方法。

# 6应用设想

本研究方法将针对大口径望远镜因不同工况导致副面位置的变化，进而造成天线指向精度及效率下降的问题，通过对副面位姿的实时测量为后续的修正提供重要支持。该测量系统将靶标固定于天线副面上，两平面镜固定于天线主面，高速相机固定于天线副面撑腿位置。调试两平面镜之间夹角以及镜面与高速相机的相对位置，保证靶标能够在两镜面内完全呈现，同时保证高速相机能够对两平面镜中的成像情况进行记录。通过实验验证测量精度达到$0 . 0 1 \mathrm { m m }$ 量级，由于系统简易、数据处理方法成熟使得系统长期工作可靠性高，能够较好的满足天线整体技术要求。

# Research on a Fast Reconstruction Method of Antenna

Subreflector Position

Su Zhaoyang1,2,, Xu Qian2.3.4 ,WangNa2.3,4 ,Zhu Chunhua1 (1 School of Physics and Technology, Xinjiang University, Urumqi 830046)   
(2 Xinjiang Astronomical Observatory, Chinese Academy of Sciences, Urumqi 830011)   
(3 KeyLaboratory of Radio Astronomy, Chinese Academy of Sciences, Urumqi 830011) (4 The Key Laboratory of Xinjiang Radio Astrophysics, Urumqi 830011)

Abstract: In order to quickly obtain the position of the subreflector changing with the elevation angle of the antenna, and to improve the comprehensive performance of the antenna by adjusting the position of the subreflector,a virtual binocular vision measurement method is proposed. The position of the subreflector of the antenna is simulated by the virtual binocular vision system composed of high-speed camera and plane mirror,and the position change image of the measured object moving with the space of the experimental platform is obtained. The image preprocessing, denoising，edge detection， feature point extraction and other operations are carried out to reconstruct the movement of the measured object in the three-dimensional direction with the movement of the experimental platform, and the reconstruction results have errors of less than $1 \%$ in the three directions.The results show that this method has high measurement accuracy and can better reconstruct the position of the subreflector.

Keywords: Antenna subreflector; Virtual binocular vision; Position; Reconstruction

参考文献：   
[1]魏善祥,王启明,孔德庆,赵保庆,朱明,王清梅.大型双反射面天线指向误差评估算法[J].天文研究与技术,2020,17(04):513-521.Wei Shanxaing,WangQiming,Kong Deqing,Zhao Baoqing,Zhu Ming,WangQingmei.AlgorithmforEstimating PointingErorofLarge Dual-reflector Antenna[J].Astronomical Research& Technology,2020,17(04):513-521.   
[2]王锦清,虞林峰,赵融冰,KESTEVEN Michael,付丽,蒋甬斌,苟伟,郭文,江永琛.大型射电望远镜高精度指向偏差检测方法[J].中国 科学:物理学力学天文学,2017,47(12):125-134.WANGJinQing,YULinFeng,ZHAORongBing,KESTEVENMICHAEL,FULi,JIANG YongBin,GOU Wei,GUO Wen& JIANG YongChen.High precisionpointingerrordetectionmethodforlargeradiotelescope[J]. SCIENTIA SINICAPhysica, Mechanica& Astronomica,2017,47(12):125-134.   
[3]王锦清,赵融冰,虞林峰,江永琛,蒋甬斌,付丽,张娟,芮萍,董健,苟伟,夏博,沈志强,刘庆会,范庆元,郑为民.基于干涉全息法测量射电 望远镜主面重力变形和副面位姿[J].中国科学:物理学 力学天文学,2019,49(10):135-144.WANG JinQing,ZHAO RongBing,YU LinFeng,JIANG YongChen,JIANGYongBin,FULi,ZHANG Juan,RUIPing,DONGJian,GOU Wei,XIABO,SHNZhiQiang,LIU QingHui,FANQinYuan&ZHENGWeiMin.Mainreflectorgravitydformationandsub-reflectorpositionmeasurementforradio telescope based on interferometer[J]. SCIENTIA SINICA Physica,Mechanica & Astronomica,2019,49(10):135-144.   
[4]许谦,王从思,易乐天.基于应变的变形副反射面位姿形貌快速重构方法[J].天文学报,2020,61(05):46-53.XUQian,WANG Cong-si,YILe-tianRapidReconfigurationMetodforDeformedSubrefectorPositionAtitudeandShapeBasedonStrain[J].ACTA ASTRONNMICA SINICA,2020,61(05):46-53.   
[5]MartinSus,DietmarKoch,Heikoalusek.TheSardinaRadioTelescope(SR)opticalaligment.12,844:8444G-844G-16. [6]ToninoPisauancouff,imondooncuetal.ADposiiosesingevietaestadiltofesoa mirror. 2014,9145:91454U-91454U-9.   
[7]江永琛,王锦清,苟伟,虞林峰,蒋甬斌.PSD 法测量大型射电望远镜副面位姿[J].天文学报,2019,60(06):98-107.JIANG Yong-chen,WANGJiningGOUWeiYULin-feng,JIANGYong-bin.TeMeasurementofSub-reflector'sisplacementsofLrgRadio Telescopes by PSD Method[J].ACTA ASTRONNMICA SINICA,2019,60(06):98-107.   
[8]侯雨雷,段艳宾,窦玉超,姚建涛,金超,李建军,赵永生 $. 6 5 \mathrm { m }$ 射电望远镜天线副面调整机构标定研究[J].中国机械工 程,2013,24(24):33-32+328.HouYulei,DuanYanbDouYchao,YaoJantaoIinChaoLiJanjun,ZhaoYongshengCaibatif AdjustingMechnisforubreflectorof65eteradioelescopeJ]hinachanialEnginering234(24):3- [9]尹航,陈卯蒸,刘志勇.基于惯性测量的天线副面位姿测量系统的设计[J].天文研究与技术,2018,15(04):390-396.Yin Hang,Chen

Mao Zheng,Liu Zhiyong.ThePositionandPostureof DeputyReflection Surface Measurement SystemDesignBasedonInertial Measurement Technology[J] Astronomical Research & Technology,2018,15(04):390-396.

[10]孙瑞轩,董浩,肖磊,张田龙.基于双目立体视觉技术的运动物体空间位置信息测量方法研究[J].河北工业科技,2017,34(01):30-35.SUNRuixuan,DONGHao,XIAOLeiZHANGTianlong.Rescarchonmeasurementmethodof spatialostioninformationofmovingobjectsbasedonbinocularstereovisiontechnologyJ].HebeiJournalofIndustrialScienceandTechnology2017,34(01):30-35.

[11]林碧华,张开淋,刘向军.基于虚拟双目视觉的电器电弧弧根三维运动特性的研究方法[J].电器与能效管理技术，2017(23):1 $5 +$ 22.LINBihua,ZHANG Kailin,LIU Xiangjun.Research Method forThree-Dimensional ElectricArc Root MovemenCharacteristics Basedon Virtual BinocularVision[J].Electrical&EnergyManagement Technology,2017(23):1-5+22.