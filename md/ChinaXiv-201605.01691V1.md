引用格式:Yun Ting,Dong Xiaolong.Study of Image Reconstruction Techniques for Spaceborne Scatterometer[J].Remote Sensing Technologyand Application,2015,30(3）：495-503.[云婷,董晓龙.星载微波散射计高分辨率o°图像重构方法研究[J].遥感技术与应用，2015，30（3)：495-503.]  
doi:10.11873/j.issn.1004-0323.2015.3.0495

# 星载微波散射计高分辨率图像重构方法研究

云婷1²,董晓龙

（1.中国科学院国家空间科学中心中国科学院微波遥感技术重点实验室，北京100190；2.中国科学院大学，北京100049)

摘要：针对我国海洋二号卫星微波散射计（HaiYang-2 Scatterometer,HY2-SCAT)数据存在的空间分辨率较低、无法满足对于地球冰冻圈、生物圈探测需求的问题，以其数据拓展应用为目标，开展了微波散射计高分辨率后向散射系数 $( \sigma ^ { 0 }$ )图像重构技术仿真研究。采用仿真的方法实现并对比了AART(Additive Algebraic Reconstruction Technique）、MART(Multiplicative Algebraic Recon-struction Technique)、SIR(Scatterometer Image Reconstruction)3 种分辨率增强的图像重构算法,得出了AART算法没有噪声抑制能力、MART算法噪声抑制能力较弱、SIR算法具有较强的噪声抑制能力，能更好地重构图像，达到分辨率增强效果的结论。然后采用HY2-SCAT测量L1B数据对结论进行了验证，重构了岛屿的地貌特征，得到了分辨率增强、细节丰富、边界清晰的重构图像；重构后的图像还可以应用于植被、冰盖和台风观测等地球地理学研究领域。

关键词：海洋二号卫星；微波散射计;图像重构;分辨率增强中图分类号：TP732.1 文献标志码：A 文章编号：1004-0323(2015)03-0495-10

# 1 引言

随着海洋观测重要性的进一步提高，星载微波散射计成为海洋动力环境观测的重要遥感器[1]。星载微波散射计因具有观测刈幅宽，能在短时间内对全球进行覆盖并提供高精度的后向散射系数 $( \sigma ^ { \mathrm { 0 } } ) ^ { \mathrm { ~ } }$ 观测数据等特点，被广泛应用于海洋风场、海浪场、数值天气预报以及海洋和大气研究[2]。由于传统星载微波散射计分辨率较低，通常在几十千米量级，无法满足一些如近岸风场等千米量级的海洋现象的测量；同时，随着陆地探测需求的增加，迫切需要星载微波散射计应用于植被、积雪、冰川和土壤等的监测和探测研究。由于上述拓展应用需求，提高散射计分辨率具有非常重要的意义。通常提高散射计分辨率的方法有多普勒滤波、距离门滤波和脉冲压缩技术等，但是这些方法均受限于天线的尺寸。David等[3提出了利用AART算法、MART算法以及SIR算法对散射计测量数据进行图像重构，增强微波散射计的测量数据分辨率。这3种算法在散射计图像重构和分辨率提高方面做出了重要贡献，被广泛应用于陆地探测、植被研究和极地海冰探测。

海洋二号卫星散射计（HaiYang-2Scatterometer，HY2-SCAT)是我国第一个可业务化运行的星载微波散射计。它的固有空间分辨率大约为 $3 0 \sim$ $4 0 ~ \mathrm { k m }$ ，提供空间网格 $2 5 ~ \mathrm { k m } \times 2 5 ~ \mathrm { k m }$ 的后向散射数据产品用于海面风矢量场的反演。该散射数据产品用于大陆和海冰的观测应用时，分辨率较低的缺点更为突出。为了使HY2-SCAT能够进行更广泛的应用，需要对其数据进行图像重构，获得更高的分辨率。本文进行了AART、MART、SIR3种算法用于星载微波散射计图像分辨率增强算法的研究，并用仿真数据和HY2-SCAT测量数据进行验证。

# 2星载微波散射计图像重构模型与方法

星载微波散射计对地面自标进行观测时，其测量目标的分辨率由散射计天线孔径决定，得到的后向散射系数 $( \sigma ^ { \mathrm { 0 } } )$ 是测量目标单元内测量值的平均值，导致测量值和真实信号之间存在误差，因此需要用图像重构方法对目标进行重构。散射计对同一区域的多次、独立的测量之间存在重叠区域，可以利用这些重叠区域的信息进行散射计测量目标图像重构[4]。

假设测量目标图像 $f$ 在有限尺寸上足够连续，可以认为该图像在这个尺度上是有限采样或者离散的。因此可以把图像 $f$ 认为是由比测量采样小的、离散的、大小一致的像元组成的。所以，第 $j$ 次无噪声的测量值 $\boldsymbol { z } _ { j }$ 包含了很多小的像元，即：

$$
z _ { j } = \frac { 1 } { q _ { j } } \sum _ { i = 1 } ^ { M } h _ { j i } s _ { i }
$$

其中： $s _ { i }$ 表示图像 $f$ 的像元按行扫描得出的向量 $s$ 的元素， $h _ { j i }$ 表示第 $j$ 次测量、在第 $i$ 个像元上的有效孔径函数的值。 $M$ 表示图像中像元的个数， $N$ 表示测量值的个数，即 $h$ 矩阵的个数。

# 2.1 （20 $A A R T$ 算法

AART迭代算法首先对图像中的每个像元赋初值 $S ^ { \mathrm { \scriptsize 0 } }$ （初值通常是一个相同的数)，然后通过加性更新项进行迭代更新，使其不断逼近真实值。每个像元的更新项是测量值和前向估计值的差值，然后将更新项与当前估计值求和，从而实现对像元的更新[4-5]。

$$
s _ { i } ^ { k + 1 } = s _ { i } ^ { k } + \frac { 1 } { \mathcal { P } _ { i } } \sum _ { j = 1 } ^ { N } h _ { j i } ( z _ { j } - f _ { j } ^ { k } )
$$

其中： $M$ 表示图像中像元的个数； $N$ 表示测量的次数，即 $h$ 矩阵的个数， $s _ { i k }$ 为第 $k$ 次迭代对 $\boldsymbol { s } _ { i }$ 的估计值， $\mathbf { \nabla } _ { P _ { i } }$ 表示覆盖到像元 $i$ 的测量的总次数， $f _ { j k }$ 为前向映射， $f _ { j k }$ 和 $\mathbf { \nabla } _ { \boldsymbol { { p } } _ { i } }$ 分别为：

$$
f _ { j } ^ { k } = \frac { 1 } { q _ { j } } \sum _ { l = 1 } ^ { M } h _ { j l } s _ { l } ^ { k }
$$

$$
\mathbf { \mathit { p } } _ { i } = \sum _ { l = 1 } ^ { N } h _ { l i }
$$

其中： $q _ { j }$ 表示第 $j$ 次测量覆盖的像元的个数，即为：

$$
q _ { j } = \sum _ { l = 1 } ^ { M } h _ { j l }
$$

2.2 MART算法

MART算法与AART算法类似，通过迭代算法对图中的每一个像素点进行更新，与AART不同的

是，它的迭代更新项是乘性的，每一个像元的更新项是测量值与前向估计值的比值，再与当前估计值相乘，完成对像元的更新。

在第 $k$ 次迭代的时候，图像 $S ^ { k }$ 的每一个像元 $s _ { i k }$ 用下列更新项进行更新[2]：

$$
s _ { i } ^ { k + 1 } = s _ { i } ^ { k } \frac { 1 } { \mathcal { P } _ { i } } \sum _ { j = 1 } ^ { N } h _ { j i } \left( \frac { z _ { j } } { f _ { j } ^ { k } } \right) ^ { w }
$$

其中：参数 $w$ 为可调参数， $\mathit { \Pi } _ { \overline { { \tau } } \overline { { \boldsymbol { v } } } } ~ = ~ 1 \$ 是无加权的MART, $ \ w \neq 1$ 是加权的MART。应用于有噪声的散射计数据时，根据经验取 $ \mathrm { w } = 1 / 2$ 时可以得到较好的重构图像。为了简便迭代式写成如下形式：

$$
s _ { i } ^ { k + 1 } = \frac { 1 } { \mathit { P } _ { i } } \sum _ { j = 1 } ^ { N } h _ { j i } u _ { i j } ^ { k }
$$

其中，更新项 $u _ { i j k }$ 如下定义：

$$
u _ { i j } ^ { k } = s _ { i } ^ { k } \Big ( \frac { z _ { j } } { f _ { j } ^ { k } } \Big ) ^ { w } = s _ { i } ^ { k } d _ { j } ^ { k }
$$

其中：

$$
d _ { j } ^ { k } = \Big ( \frac { z _ { j } } { f _ { j } ^ { k } } \Big ) ^ { w }
$$

# 2.3 SIR 算法

当测量图像的信噪较低时，MART算法因无法最终收敛，从而无法取得较好的图像重构效果。针对散射计目标测量的信噪比较低的特点，David[3提出了对MART迭代算法改进的SIR算法，增强了算法的噪声容限，得到了更好的重构效果。改进的算法用一种非线性的权重和前向测量估计代替了MART算法中的 $u _ { i j k }$ ,具体公式如下[3]：

$$
u _ { i j } ^ { k } = \left\{ \begin{array} { l l } { \displaystyle \Big [ \frac { 1 } { 2 } \frac { 1 } { f _ { j } ^ { k } } \Big ( 1 - \frac { 1 } { d _ { j } ^ { k } } \Big ) + \frac { 1 } { s _ { i } ^ { k } d _ { j } ^ { k } } \Big ] ^ { - 1 } } & { d _ { j } ^ { k } \geqslant 1 } \\ { \displaystyle \Big [ \frac { 1 } { 2 } f _ { j } ^ { k } ( 1 - d _ { j } ^ { k } ) + s _ { i } ^ { k } d _ { j } ^ { k } \Big ] } & { d _ { j } ^ { k } < 1 } \end{array} \right.
$$

SIR算法通过对比例因子 $d _ { j k }$ （即测量值与前向估计的比值的平方根)大小的判断，而改变更新项。在理想环境下，随着迭代次数的增加，比例因子会达到单位值1，说明所有像元的前向估计和测量值相一致，迭代收敛。但是在散射计实际测量情况下，因为存在噪声，比例因子不会最终收敛到1，由于SIR算法根据比例因子的大小提供了不同的非线性更新项，这就限制了对前向估计和测量值之间的大的偏差的更新，从而限制了最终估计值的大小，对噪声起到了限制作用，降低了算法对噪声的敏感程度。

# 3 重构算法仿真

3.1HY2-SCAT系统参数与性能指标海洋二号卫星是我国第一颗海洋动力环境卫星，主要用于全球海面风场观测。HY2-SCAT采用笔形波束圆锥扫描体制，采用VV（外波束）、HH（内波束)两种极化方式，通过天线圆锥扫描和卫星运动，对同一目标区域进行外波束前视、内波束前视、内波束后视和外波束后视4次扫描，分别得到测量值 $\boldsymbol { \sigma } ^ { \mathrm { 0 } }$ 。海洋二号散射计的内波束入射角为 $4 1 ^ { \circ }$ ，外波束入射角为 $4 8 ^ { \circ [ 6 ] }$ ；内波束3dB波束宽度为$1 . 5 ^ { \circ } \times 1 . 5 ^ { \circ }$ ，外波束 $3 ~ \mathrm { d B }$ 波束宽度为 $1 . 5 ^ { \circ } \times 1 . 5 ^ { \circ }$ ；所对应的内波束足印大小为 $3 4 ~ \mathrm { k m } \times 2 6 ~ \mathrm { k m }$ ，外波束足印大小为 $4 2 ~ \mathrm { k m } { \times } 2 8 ~ \mathrm { k m } ^ { [ 7 ] }$ 。地面重叠区域的大小由采样间隔决定，方位向上的采样间隔由卫星地面速度和天线旋转速度来决定，距离向的采样间隔由脉冲重复频率(PRF)和天线旋转速度决定。卫星地面速度约为 $6 . 4 ~ \mathrm { k m / s }$ ，天线旋转速度为 $1 6 . 6 7 ~ \mathrm { r / m i n }$ ，距离向地面足迹间隔为 $2 3 \ \mathrm { k m }$ ，脉冲重复频率为 $1 8 5 ~ \mathrm { H z }$ .方位向内波束地面足迹间隔为 $1 3 \ \mathrm { k m }$ ，外波束足迹间隔为 $1 8 ~ \mathrm { k m }$ ，重叠区域至少为 $1 / 3$ 足印大小」，保证了重构算法的可实施性。

# 3.2 HY2-SCAT仿真

为了获取重构图像，首先应获得散射计每次测量的后向散射系数 $\boldsymbol { z } _ { j }$ 和孔径函数 $h$ 矩阵，在真实情况下，散射计的测量值就是后向散射系数，但是在仿真时，应该首先模拟散射计的扫描过程，通过计算得出每一次扫描后向散射系数 $\boldsymbol { z } _ { j }$ 的值，并同时得出每一次扫描相应的 $h$ 矩阵。

仿真区域大小设置为 $4 0 0 ~ \mathrm { k m } \times 4 0 0 ~ \mathrm { k m }$ 。设重构图像的像元大小为 $d _ { x } \times d _ { v }$ ，将地面区域离散化为$ { \boldsymbol { N } } _ {  { \boldsymbol { { x } } } } \times  { \boldsymbol { N } } _ {  { \boldsymbol { v } } }$ 个网格，并满足 $N _ { x } \times d _ { x } = L _ { x }$ ， $N _ { v } \times d _ { v } =$ $L _ { v }$ ，此次重构选择的区为 $L _ { x } = \ L _ { v } = 4 0 0 \ { \mathrm { k m } }$ 。卫星行下点以 $6 . 4 ~ \mathrm { k m / s }$ 的速度自坐标原点沿 $y$ 轴正向运动，正方形仿真区域在坐标系第一象限。天线每隔 $5 . 2 3 ~ \mathrm { m s }$ 发射一个脉冲，脉冲长度为 $1 . 5 ~ \mathrm { m s }$ ，内外波束间隔发射。首先计算每个脉冲照射到地面中心点的位置和视轴方向；然后，通过地面像元的坐标判断它是否在这次照射的足印椭圆内，得到相应的$h$ 矩阵；最后通过式(1)计算每次脉冲照射到的足印的后向散射系数。

取 $t = 0$ 时对应的卫星地面坐标为 $( 0 , 0 )$ ，天线方位角为 $0 ^ { \circ }$ ，卫星沿 $y$ 轴正向运动。对任意 $\mathbf { \Psi } _ { t }$ 时刻，卫星照射地面的观测几何由下式表达：

$$
t { = } N _ { \mathrm { p l u s e } } { \times } 5 . 2 3 { \times } 1 0 ^ { - 1 0 }
$$

$$
\mathrm { S a t \_ l o c a t i o n } { = } t \times \tau _ { \mathrm { s a t } }
$$

$$
\varphi _ { \mathrm { a n t } } = \scriptstyle t \times 2 \pi / 3 . 6
$$

$$
{ \mathrm { f o o t c e n t e r } } \_ x { = } R \times \cos ( \varphi _ { \mathrm { a n t } } )
$$

footcenter $\underline { { { y } } } \mathrm { = } R \times \mathrm { s i n } ( \varphi _ { \mathrm { a n t } } ) + \mathrm { S a t \_ l o c a t i o n }$ (15)其中： $N _ { \mathrm { p l u s e } }$ 表示脉冲的个数，Sat_location表示 $\mathbf { \Psi } _ { t }$ 时刻卫星的位置， $ { v _ { \mathrm { s a t } } }$ 表示卫星的对地速度， $\varphi _ { \mathrm { a n t } }$ 表示天线的旋转角度， $R$ 表示波束的地面斜距，外波束为$8 7 2 . 6 ~ \mathrm { k m }$ ，内波束为 $6 9 8 ~ \mathrm { k m }$ ，(footcenter $\underline { { x } }$ ,footcenter$\lrcorner$ 表示足印中心的坐标。通过上述公式，可以得到每一个脉冲照射到地面的足印的中心坐标，通过足印的大小则可以判断地面被照射到的区域，从而确定 $h$ 矩阵。设在足印内的点 $\boldsymbol { h }$ 矩阵值为1;不在足印内的点 $h$ 矩阵值为0。通过计算像元的中心坐标到足印椭圆的两焦点的距离的和是否大于椭圆长轴来判断像元是否在足印内。如果小于或等于长轴，则在足印内，如果大于长轴，则在足印外，公式表达如下：

$$
h _ { j i } = \left\{ \begin{array} { c c } { { 1 , } } & { { d _ { 1 } + d _ { 2 } \leqslant 2 a } } \\ { { 0 , d _ { 1 } + d _ { 2 } > 2 a } } & { { } } \end{array} \right.
$$

其中： $d _ { 1 } \ldots d _ { 2 }$ 是像元中心到足印椭圆两焦点的距离，$a$ 是足印椭圆的半长轴长度。

本文采用图像处理的经典图像fruits，如图1（a），作为仿真图像，测试在不同像元大小下AART、

![](images/6ec8edc30989535ccf319bbfa6a7ee99529b9a1edbf9058457f96238c8dc5141.jpg)  
图1仿真图像  
Fig.1Original image

MART和SIR算法的重构效果。

3.3AART、MART、SIR算法无噪仿真

# 3.3.1 无噪仿真结果

从图 $2 \sim 4$ 可以看出，在无噪声的情况下，

AART、MART、SIR算法都能很好地重构图像，重构图比仿真的散射计测量图像细节更丰富，效果更清晰，分辨率更高。随着像元减小，重构图像的纹理更加接近真实图像。

![](images/3ff7d3eb89169460216ff725e2bcc4f33c21890c2e4a5ae691cf252ca1280c5f.jpg)  
Fig.2Simulation results of AART without noise

![](images/2392cfd80e2c0af64eebbe9708fb8d2eb07e5ee75134c90db8c186efda9313b0.jpg)  
图2AART无噪仿真结果图  
图3MART无噪仿真结果图

![](images/bf002ab0f478a588781e148cad8487bcbd1c1109285d73a2cad564f5346b0dbd.jpg)  
Fig.3Simulation results of MART without noise   
图4SIR无噪仿真结果图  
Fig.4Simulation results of SIR without noise

# 3.3.2 无噪情况下3种算法的对比

从表1可知，无噪声情况下AART、MART和SIR3种算法在相同像元尺寸的条件下，相关系数和均方差基本相同，都能很好地重构图像，SIR算法性能稍差于AART和MART算法。

如图5所示，通过对比各算法相关系数随迭代次数的变化可以得出，在无噪声的情况下AART、MART和SIR3种算法在迭代若干步后均可以达到收敛，AART算法像元的更新项趋于O，MART和SIR算法像元的更新项趋于1，完成对图像的重构。AART算法收敛速度最快，可以以最少的迭代次数完成对图像的重构，同时重构后的图像和原图像的相关系数最高，重构效果最好；MART算法收敛速度缓于AART算法，但也能较快地完成收敛，重构后的图像和原图像的相关性比AART算法稍差，也能较好地逼近原图像；SIR算法的收敛速度最慢，相关系数最低，但是在收敛之后也能较好地逼近原图像，和AART、MART算法的性能相差不多。

表1无噪情况下AART、MART、SIR 算法性能比较Table1Comparisons of AART,MART,SIR without noise  

<html><body><table><tr><td>算法名称</td><td>像元大小</td><td>相关系数</td><td>均方差</td></tr><tr><td>AART</td><td></td><td>0.96</td><td>11.9</td></tr><tr><td>MART</td><td>2 km×2km</td><td>0.96</td><td>11.9</td></tr><tr><td>SIR</td><td></td><td>0.96</td><td>12.4</td></tr><tr><td>AART</td><td></td><td>0.99</td><td>7.0</td></tr><tr><td>MART</td><td>6 km×6km</td><td>0.98</td><td>7.4</td></tr><tr><td>SIR</td><td></td><td>0.98</td><td>8.3</td></tr><tr><td>AART</td><td></td><td>0.99</td><td>2.5</td></tr><tr><td>MART</td><td>10 km×10km</td><td>0.99</td><td>3.5</td></tr><tr><td>SIR</td><td></td><td>0.99</td><td>5.0</td></tr></table></body></html>

![](images/676d45fb9173c5c992b0b925c4c529723daa99d5abdd94904469ba26dd6eb281.jpg)  
图5无噪条件下各算法性能随迭代次数变化关系  
Fig.5Comparisons of AART,MART,SIR without noise

通过对比各算法均方差随迭代次数的变化可以得出，在无噪声情况下AART、MART、SIR3种算法都可以很好地逼近原图像。AART算法收敛后的均方差最小，能够最大程度地接近原图像；MART虽然收敛较慢，但在迭代150次后，均方差与AART相差很小，仍能很好地逼近原图；SIR算法逼近速度最慢，收敛后的均方差比AART和MART略大，但是仍可以很好地逼近原图像；在3种算法迭代200次后，均方差的差别很小，算法性能相差不大。

# 3.4 HY2-SCAT噪声模拟

散射计的测量误差主要来自于回波信号的测量精度、内定标精度和天线波束指向偏差。

散射计系统中一般采用 $\boldsymbol { \sigma } ^ { \mathrm { 0 } }$ 测量值的相对标准偏差 $K _ { \rho }$ 来评估回波信号的测量精度[1,8-9]， $K _ { \rho }$ 决定于系统的信噪比和进行平均的独立测量样本的数目。

定义式如下：

$$
K _ { P } = \frac { \sqrt { \operatorname { v a r } \{ \sigma _ { \mathrm { m e a s } } ^ { 0 } \} } } { \sigma ^ { 0 } }
$$

$$
K _ { P } = \sqrt { \frac { 1 } { T _ { r } \bullet B _ { r } } { \left[ 1 + \frac { 2 } { S N R } + \left( 1 + \frac { B _ { r } } { B _ { n } } \right) \bullet \left( \frac { 1 } { S N R } \right) ^ { 2 } \right] } }
$$

带噪声的 $\boldsymbol { \sigma } ^ { \mathrm { 0 } }$ 测量结果可以用式（19）仿真获得[10]：

$$
\sigma ^ { 0 } = \sigma _ { m } ^ { 0 } \bullet ( 1 + K _ { P } \bullet N ( 0 , 1 ) )
$$

其中： $T _ { r }$ 是接收时间， $\boldsymbol { B } _ { r }$ 是接收机信号带宽， $\textstyle B _ { n }$ 是接收机噪声带宽， $S N R$ 是散射计信噪比，信噪比可以由下式计算得出：

$$
S N R = \frac { P _ { r } } { P _ { n } }
$$

其中： $P _ { r }$ 表示系统接收功率， $\boldsymbol { P } _ { n }$ 表示系统噪声功率，其中 $\boldsymbol { P } _ { r }$ 可以用式（21）计算得出：

$$
P _ { r } = { \frac { P _ { t } G ^ { 2 } \lambda ^ { 2 } A \sigma ^ { \mathrm { ( } } } { ( 4 \pi ) ^ { 3 } R ^ { 4 } L _ { F } } }
$$

其中： $\boldsymbol { P } _ { t }$ 表示系统发射功率， $G$ 表示天线增益， $\lambda$ 表

示雷达波长， $A$ 表示足印面积， $R$ 表示斜距， $L _ { F }$ 表示系统差损。

$$
P _ { n } = k _ { \beta } \bullet ( n _ { f } - 1 ) \bullet T _ { r e f } \bullet B _ { n }
$$

其中： $k _ { \beta }$ 表示波尔兹曼常数， $n _ { f }$ 表示接收机噪声系数，取值为5dB， $T _ { \mathrm { r e f } }$ 表示环境温度，取 $2 9 0 ~ \mathrm { K } ^ { [ 1 1 ] }$

# 3.5AART、MART、SIR有噪仿真

# 3.5.1AART有噪仿真结果

如图6所示，在有噪声情况下AART算法的重构能力有限，图像的细节可以恢复一部分，但是，因为每个像元的更新项是测量值和前向估计的差值，

在算法运行过程中会对图像中的高频分量进行放大，所以图像中存在很强的点状噪声。

# 3.5.2 MART有噪仿真结果

如图7所示，在有噪声的情况下，MART算法的性能比AART算法好。因为MART的迭代更新项是乘性的，每一个像元的更新项是测量值与前向估计的比值，再与当前估计值相乘，完成对像元的更新。在有噪声的条件下，像元的更新项逐渐收敛、在单位值1附近震荡，所以算法对高频分量的放大作用有限，有一定抑制噪声的能力。

![](images/46ac0b3444b3cb235c607e895659af69e4a0a774e4b9ecfcc4e5da7d8362a9ee.jpg)  
Fig.6Simulation results of AART with noise

![](images/7570a5d6be6044785499207481d7ea6010f7168671bc651f715060fe95daadc1.jpg)  
图6AART有噪仿真结果图  
图7MART有噪仿真结果图  
Fig.7 Simulation results of MART with noise

# 3.5.3 SIR有噪仿真结果

如图8所示，在有噪声情况下SIR算法的复原能力最强，噪声影响很小，图片细节清晰，重构效果好。这是因为，每个像元的更新项不再是简单的测量值与前向估计的比值，而是通过对比例因子 $\boldsymbol { d } _ { j k }$ 大小的判断改变更新项。在存在噪声的情况下，比例因子不会最终收敛到1，但是因为算法根据比例因子的大小提供了不同的非线性更新项，这就限制了对前向估计和测量值之间的大的偏差的更新，从而限制了最终估计值的大小，对噪声起到了限制作用，拥有很强的噪声抑制作用。

# 3.5.4有噪情况下3种算法的对比

从表2可知，在有噪声的情况下AART算法的相关系数和均方差最差，MART算法的相关系数和均方差优于AART算法，SIR算法的相关系数和均方差最好。这说明SIR算法对噪声的抑制效果最好，MART有一定的抑制噪声效果，而AART对噪声几乎没有抑制效果。

![](images/30e82c33c877db70c6e1bd44d4768f2fe1074ce001e8d66909c03ff0b9606934.jpg)  
Fig.8Simulation results of SIR with noise

表2有噪情况下AART、MART、SIR 算法性能比较Table2Comparisons of AART,MART,SIR with noise  

<html><body><table><tr><td>算法名称</td><td>像元大小</td><td>相关系数</td><td>均方差</td></tr><tr><td>AART</td><td></td><td>0.89</td><td>21.5</td></tr><tr><td>MART</td><td>2 km×2km</td><td>0.93</td><td>16.8</td></tr><tr><td>SIR</td><td></td><td>0.95</td><td>13.6</td></tr><tr><td>AART</td><td></td><td>0.92</td><td>18.6</td></tr><tr><td>MART</td><td>6 km×6km</td><td>0.95</td><td>13.7</td></tr><tr><td>SIR</td><td></td><td>0.97</td><td>10.0</td></tr><tr><td>AART</td><td></td><td>0.95</td><td>14.2</td></tr><tr><td>MART</td><td>10 km×10km</td><td>0.97</td><td>10.9</td></tr><tr><td>SIR</td><td></td><td>0.99</td><td>7.2</td></tr></table></body></html>

如图9所示，通过对比各算法相关系数随迭代次数的变化可以得出，在有噪声的情况下AART、MART和SIR算法随着迭代步骤的增加，最后不能收敛，即AART算法的更新项无法收敛至0，而MART、SIR算法的更新项无法收敛至1，始终存在震荡。AART算法的相关系数随着迭代次数的增加，先迅速上升随后快速下降；相应地均方差随着迭代次数的增加，先迅速下降随后快速上升。MART算法的相关系数随迭代次数的增加先迅速上升后快速下降，但是上升速率和下降速度和幅度都低于AART算法；相应地，均方差随着迭代次数的增加先下降后上升，上升和下降的速度和幅度都小于AART算法。SIR算法的相关系数随着迭代次数的增加上升，上升速度低于AART、MART算法，但是在上升至峰值后，随着迭代次数的增加，下降幅度很小，基本保持在很高的水平；相应地，均方差随着迭代次数的增加，先快速下降，随后有小幅度上升，但是基本保持在一个很低的水平。造成AART、MART和SIR算法在有噪情况下，相关系数和均方差变化的原因在于：图像的误差由两部分构成，一部分是重构误差，另一部分是噪声放大。算法会降低重构误差，但是会将存在于图片中的噪声放大。迭代开始时，算法降低的重构误差大于对噪声的放大，所以相关系数上升、均方误差下降，逐渐逼近算法性能的最佳值；但随着迭代次数的增加，算法对于重构误差的降低小于对噪声的放大，所以出现了相关系数下降和均方误差增加。从图9可以看出，AART算法对噪声的抑制最差，所以在最佳值过后相关系数和均方差严重恶化；MART算法对噪声有一定的抑制能力，在最佳值过后相关系数和均方差的恶化程度小于AART算法；SIR算法对噪声的抑制最好，在最佳值过后，相关系数只是小范围下降，均方差只有小范围的增加，总体处在很好的水平。所以，在有噪声的情况下SIR算法的性能最好。同时，在有噪声的情况下AART、MART和

![](images/57102fe982fd233db8cf7588153b16b88a44b1492b00077a7fa0c44db767e8e3.jpg)  
图8SIR有噪仿真结果图  
图9有噪条件下各算法相关系数和均方差随迭代次数变化关系  
Fig.9Comparisons of AART,MART,SIR with noise

SIR3种算法都不能最终收敛，图像重构的效果与迭代次数相关，存在迭代次数的最佳值，所以在以后进行真实数据处理时，要特别注意迭代次数，使算法性能发挥到峰值，重构图像效果更好。

# 4HY2-SCAT散射测量数据图像重构

# 4.1 HY2-SCAT数据

本文采用HY2-SCAT散射计L1B级数据，提取位置区域的经度、纬度、方位角、天线方位角和后向散射系数信息，通过3种算法重构目标区域图像。

本文选取 $1 2 0 \ { ^ \circ } { \sim } 1 2 6 \ { ^ \circ } \mathrm { E } , 1 0 \ { ^ \circ } { \sim } 1 6 \ { ^ \circ } \mathrm { N }$ 的区域作为重构目标区域，目标区域为菲律宾部分海岛，散射计原始后向散射系数所构成的散点图如图10（a)所示。

![](images/072ffd639afd6d66e8c52a2e2766db3a73d9e1e7d123b857621a33e8c6664c7b.jpg)  
图10HY2-SCAT真实数据重构结果 Fig.10Image reconstruction of HY2-SCAT data

从图中可知，散射计后向散射系数直接做出的图无法细致区分出陆地、海洋和海岸线，不能满足对陆地的观测需求。

# 4.2HY2-SCAT真实数据重构结果

从图1O可知，AART、MART和SIR3种算法都可以从散射计的后向散射系数测量值中较好地恢复出地貌特征，可以较为细致地区分出陆地、海洋和海岸线。但是3种算法对噪声的抑制作用有着明显区别。AART算法对噪声有很明显的放大作用，从图中可以看到在陆地部分有很多的高频分量，影响对陆地的观测；MART算法对噪声有一定的抑制作用，从图中可以看到陆地上的高频分量明显少于AART算法，但仍有较多的点状噪声；SIR算法对噪声的抑制作用最好，从图中基本无法看到被放大的噪声高频分量，图像细节丰富、轮廓清晰、噪声抑制效果好。

# 5 结语

传统的星载微波散射计分辨率较低，多用于测量海洋风场。随着地球探测需求的不断增加，星载散射计开始进行陆地、海洋、冰盖和植被的测量，传统星载散射计分辨率精度不能满足要求，所以需要提高星载散射计的分辨率。

本文采用图像重构算法对散射计测量所得后向散射系数进行高分辨处理，仿真了AART、MART和SIR3种算法在无噪声和有噪声的情况下图像重构，并得出在无噪声情况下，3种算法都可以很好地进行图像重构，重构出的图像相比仿真的测量图像轮廓更清晰、细节更丰富的结论。在有噪声的情况下，SIR算法拥有最强的噪声抑制能力，重构出的图像边缘清晰、细节丰富，而AART、MART算法对噪声的抑制效果较差，有非常明显的点状噪声。

在仿真的基础上进行了HY2-SCAT测量数据的重构，得出了与仿真结果一致的结论。AART、MART和SIR3种算法都可以较好地重构图像，但是SIR算法有较强的噪声抑制作用，重构的图像基本不存在点状噪声，对陆地的刻画更清晰。重构后的图像可以应用于植被、冰盖和台风观测等地球地理学研究领域。

# 致谢：感谢国家卫星海洋应用中心提供的海洋二号卫星微波散射计L1B数据！

# 参考文献(References）：

[1] TsaiWY,Nghiem SV,HuddlestonJN,etal.Polarimetric Scatterometry:A Promising Technique for Improving Ocean Surface Wind Measurements from Space[J].IEEE Transactions on Geoscience and Remote Sensing,2000,38(4):1903-1921.   
[2] Zhang Yong，Sun Qiang，Lu Daren.Overview of Sea Surface Wind Vector Retrieval Using Fully Polarimetric Microwave Signal[J].Remote Sensing Technology and Application, 2013,28(3)：533-542.[张勇，刘强，吕达仁.全极化微波信号 海面风场反演技术现状与发展趋势［J].遥感技术与应用， 2013,28(3):533-542.]   
[3]Long DG,Hardin P J,Whiting P T.Resolution Enhancement of Spaceborne Scatterometer Data[J]. IEEE Transactions on Geoscience and Remote Sensing,1993,31(3):700-715.   
[4]Early D S,Long D G.Image Reconstruction and Enhanced Resolution Imaging from Irregular Samples[J]. IEEE Trans actions on Geoscience and Remote Sensing，2oo1,39(2):291- 302.   
[5]Early D S,Long D G. Enhanced Resolution Imaging from Ir regular Samples[C]//IEEE International Geoscience and Remote Sensing Symposium. Singapore IEEE 1997.   
[6]Jiang X,Lin M,Liu J,et al. The HY-2 Satellite and Its Preliminary Assessment[J].International Journal of Digital Earth,2012,5(3):266-281.   
[7]Xiaoning W,Lixia L,Haoqiang S,et al.In-orbit Calibration and Performance Evaluaiotn of HY-2 Scatterometer[C]// IEEE International Geoscience and Remote Sensing Symposium. Munich German IEEE 2012.   
[8]Long D G,Spencer M W.Radar Backscatter Measurement Accuracy for A Spaceborne Pencil-beam Wind Scatterometer with Transmit Modulation[J].IEEE Transactions on Geoscience and Remote Sensing,1997,35(1) :102-114.   
[9]Long D G,Oliphant T.Wind Measurement Accuracy for the NASA Scatterometer[C]//Earth Observing Systems II San Diego,CA，1997.   
[10]Zhu Jintai,Dong Xiaolong,Lin Wenming,et al.Calibration of the Ku-band Rotating Fan-beam Scatterometer Using Land Extended-area Targets[J].Journal of Electronics & Information Technology,2013,35（8)：1793-1799.[朱金台，董晓龙， 林文明，等.Ku 波段旋转扫描扇形波束散射计地面扩展目标 在轨定标[J].电子与信息学报,2013,35(8)：1793-1799.]   
[11]Zou Juhong,Lin Mingsen,Zou Bin,et al. Simulation Study of Image Reconstruction for HY2-SCAT Backscatter Measur ments and Its Application in Retrieval of Wind Field in Ty phoon Conditions[J].Chinese High Technology Letter,2012, 22(7）：713-720.[邹巨洪，林明森，邹斌，等.HY2散射计高分 辨率 sigmaO图像重构技术在台风风场反演中的仿真研究 [J].高技术通讯,2012,22(7)：713-720.]

DEM were extracted based on images captured by UAV platform by means of splicing stereo pairs,and were compared with GPS measured data,ASTER GDEM data and SRTM data.The result shows that,the DEM extracted based on UAV images has the closest difference with GPS measured result ( ${ \mathrm { R M S E } } =$ 8.96）,which has higher precision than ASTER GDEM( $\mathrm { R M S E } { = } 1 3 . 6 8 \rangle$ and SRTM ( $\mathrm { R M S E } { = } 1 1 . 8 1 \$ data;The closest result( $\mathrm { R M E S } = 1 . 8 1 3 \$ ）of max tree heights and max elevation differences in each sample plot,shows that UAV DEM has an ability to reflect more hierarchical information between canopy and ground,which shows a greater potential in the construction of DEM in mountain plantation landscape.

Key words: DEM; UAV;Plantation;Landscape;Orthophotos

# Study of Image Reconstruction Techniques for Spaceborne Scatterometer

Yun Tingl'² ,Dong Xiaolong

(1.The CAS Key Laboratory of Microwaue Remote Sensing ,Center for Space Science and Applied Research ,Chinese Academy of Sciences ,Beijing 1Oo19o,China; 2.University of Chinese Academy of Sciences ,Beijing lOoo49,China)

Abstract: High-resolution reconstruction techniques are investigated for Hai Yang-2 Scatterometer （HY2- SCAT） backscatter measurements for a variety of application purposes including land and polar ice detection and the studies of cryophere and biosphere.Three resolution enhancement algorithms,including Additive Algebraic Reconstruction Technique （AART）,Multiplicative Algebraic Reconstruction Technique （MART） and Scaterometer Image Reconstruction （SIR),are compared by simulation approach.The re sults that SIR has the best performance in noise suppression and resolution enhancement of the backscatter measurements than AART and MART algorithms. This study is verified using HY2-SCAT Level-1B （L1B）backscatter measurements.The $\sigma ^ { \ast }$ measurements over some sites with particular backscattering characteristics(e.g.islands）are reconstructed.

Key words:HaiYang-2 scatterometer;Microwave scatterometer;Image reconstruction;Resolution enhance ment