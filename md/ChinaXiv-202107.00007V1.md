# 基于地面粒子探测器阵列的一种新芯位重建方法

郑应，何钰，祝凤荣，张丰(西南交通大学物理科学与技术学院，四川省成都市，611756)摘要：芯位重建是地面宇宙线探测实验开展物理分析的前提和基础。本文基于广延大气簇射的对称性，结合探测器的特征，提出一种新的芯位重建算法——椭圆拟合法，用于模拟数据的芯位重建并与重心法对比。对于能量大于1TeV的芯内宇宙线质子事例，芯位分辨率在小于 $5 \mathrm { m }$ ，明显优于重心法；对于临近阵列边界 $2 0 \mathrm { ~ m ~ }$ 范围内能量大于1TeV的事例芯位分辨率小于 $1 0 \mathrm { ~ m ~ }$ ，相比于传统方法有显著优势。由于该方法能够在保证精度的前提下重建边沿事例和部分芯外事例，极大地增大了事例利用率，对于 $1 { \cdot } 1 0 \ \mathrm { P e V }$ 质子事例的探测器阵列面积利用率比重心法增大1倍左右。

关键词：宇宙线；广延大气簇射；事例重建；对称性；水切伦科夫阵列中图分类号：TN216 文献标识码：A 文章编号：1007-2276-(2004)4-0338-05

# 0.引言

宇宙线的能量跨越10多个量级、流强跨越30多个量级，能谱近似符合dN/dE $\propto \mathrm { E } ^ { - \gamma }$ ，其中谱指数γ的取值约为2.7[]。从MeV到\~400 TeV能区宇宙线流强较大，可以用卫星直接探测，更高能区宇宙线由于流强太低主要利用地面实验间接探测[1,2]。水切伦科夫探测器是地面宇宙线探测技术的一种，它具有全天候、宽视场等优势，主要是通过测量原初宇宙线进入大气后产生的广延大气簇射重建出原初宇宙线信息[1,30]。位于墨西哥的HAWC 和位于四川稻城的LHAASO-WCDA等多个宇宙线探测实验都采用了水切伦科夫探测器技术。

广延大气簇射(Extensive Air Shower，EAS)[3.4]是高能原初宇宙线进入大气层后与大气成份发生相互作用，通过强子级联和电磁级联产生大量次级粒子的过程，通常用纵向发展和横向分布来描述其物理特征。常用于描述纵向发展的模型有 Gaisser-Hillas function [27.31]、Greisen function[28.311和 Gaussian-in-Age[293]，三者都与实验测量值吻合得很好。EAS 的横向分布则通常用横向分布函数（Lateraldistributionfunction，LDF）和Nishimura-Kamata-Greisen (NKG）函数来描述[3.5,16.31]。LDF 是简单导出的、纯数学拟合的、描述平均分布的经验公式，它的参数不直接关联广延大气簇射的物理特性[4.8.16]。NKG 函数比LDF 更接近物理本质,一方面NKG 函数能够反映EAS 的横向分布和纵向发展等物理特征，另一方面在拟合过程中还充分考虑了EAS 的统计涨落[3-5.31]。

地面宇宙线探测实验通过探测包括电子（e+、e-）、缪子 $( \mu - , \mu + )$ ，和光子在内的EAS次级粒子密度分布和前锋面到达时间反演事例的芯位、方向和能量等信息[5.6.9]，这个过程称为宇宙线事例重建或EAS 重建，芯位重建是EAS 重建的重要内容。常用的芯位重建方法有重心法、树形分析法、最大似然法、二维高斯拟合法等，这些方法各自都有独特的优势和不足[3,10,5.17]。重心法和树形分析法的优势在于计算量小，节省计算资源；其不足在于重建时破坏了事例的对称性特征。芯位重建的精度依赖重建出的芯位到探测器中心的距离。最大似然法重建芯位精度高，但是精度也依赖探测器单元触发数量 $( N _ { h i t } ) ^ { \top }$ ），当 $N _ { h i t }$ 大于1000时其芯位分辨率小于2米，精度相比前两者显著提高；但是一方面该方法计算量较大需要占用大量计算资源，另一方面其精度依赖于能量、方向和 $\mathbf { N } _ { \mathrm { h i t } }$ 等诸多因素。 二维高斯拟合法是一种简单的数学拟合方法，克服了重心法和树状分析法的部分缺点，对于芯位位于探测器阵列内部的事例（芯内事例）重建效果较好，而对于芯位位于探测器阵列外的事例不能准确重建[3,1,12.17]。除最大似然法外，这些重建方法都需要通过筛选条件丢弃大量数据，只保留芯位在阵列中心附近小范围的事例，以牺牲探测器有效面积的方式来保证重建结果的可靠性，造成大量观测数据的浪费[5.10]。此外水切伦科夫探测器数据的低信噪比也是重建的挑战之一，如LHAASO-WCDA 的观测数据在去噪之前其信噪比约为70/218，通过遍历法去噪之后其噪声比约为 22/70，也就是说对于触发70 个探测器单元的事例，其中约有 22个通道的信号是噪声，这些噪声会给精确重建带来很大的困难，而上述方法几乎都不能很好地处理噪声带来的影响[10]。

本文基于广延大气簇射的对称性和水切伦科夫探测器阵列的物理特征，提出了一种新的芯位重建方法——椭圆拟合法。该方法充分利用 EAS 的对称性，消除噪声对芯位重建的影响。在满足芯位重建精度的前提下，能够重建出芯位落在探测器边沿的事例和芯外事例，扩大探测器事例利用率。

# 1.水切伦科夫探测器技术

水切伦科夫光探测器是利用纯水作为介质，通过光电倍增管收集带电粒子在水中运动产生的切伦科夫光子来测量广延大气簇射的地面粒子探测技术。现有各实验采用的水切伦科夫探测器阵列的单元探测器构造和探测原理基本相同，探测器单元的各种性能参数和布局上存在一定的差别。LHAASO-WCDA 是最具代表性的水切伦科夫探测器阵列之一。当宇宙线粒子在WCDA视场内产生广延大气簇射，次级粒子会进入阵列内的纯水中做超光速（介质中的光速）运动激发切伦科夫光，每个基本单元的光电倍增管（PMT）收集到的切伦科夫光电子数（NPE）与该位置的 EAS 次级粒子密度成正比[321；探测器单元触发时间可精确到纳秒量级，通过这些数据可以重建芯位、方向等信息[1,18,19]。其他实验的水切伦科夫探测器阵列如 HAWC 的结构和布局与 LHAASO-WCDA 有所不同,但是其探测基本一致[30]。LHAASO-WCDA由3个水池组成，具有3120个单元探测器以及后级的电子学、定时、数据采集、触发判选、数据处理、标定等功能系统。单元探测器(图1)为 $5 \mathrm { m } \times 5 \mathrm { m }$ 的水域,深度为 $4 . 4 \mathrm { m }$ ，两个单元之间用隔光帘隔开，主要目的是避免来自同一次级粒子，尤其是缪子信号的串扰。WCDA共采用 3120 支大尺寸光电倍增管(PMT)分别布设于每个单元的中央，置于水底，向上观测。另外还在水池中放置3120支小尺寸PMT，小尺寸PMT放置在大尺寸PMT 旁边，用于扩大簇射粒子数测量动态范围，从而实现高能宇宙线的高精度测量[1,18,19]。本文将以 $1 5 0 \mathrm { m } { \times } 1 5 0 \mathrm { m }$ 的LHAASO-WCDA1水且伦科夫探测器阵列为样本，阐述椭圆拟合法重建芯位的物理思路和算法设计。

# 2.椭圆拟合法

![](images/e6c5d248e2699f3c0c07de04e77b814e53e4bd9a0bc3de6797164ae4c55e44dd.jpg)  
图1：LHAASO-WCDA单元探测器结构示意图（左）和探测示意图(右）

Figure 1: Schematic diagram of LHAASO-WCDA unit detector structure (left)and detection diagram (right)

如图1（右）所示，当EAS以一定的天顶角入射到地面，到达探测器阵列平面EAS 次级粒子集中在很薄的前锋面内，次级粒子横向分布用可以 NKG 函数描述[3-8.311:

$$
\rho ( r ) = \frac { N _ { e } } { r _ { M } ^ { 2 } } \frac { \Gamma ( 4 . 5 - s ) } { 2 \pi \Gamma ( s ) \Gamma ( 4 . 5 - 2 s ) } ( \frac { r } { r _ { M } } ) ^ { s - 2 } ( 1 + \frac { r } { r _ { M } } ) ^ { s - 4 . 5 }
$$

（1）式中 $N _ { e }$ 是EAS的总粒子数，主要依赖于原初宇宙线粒子的能量； $r _ { M }$ 是莫里哀半径与原初宇宙线的成分有关； $s$ 是描述EAS发展阶段的参数，被称为EAS的年龄，当 $s { = } l$ 时EAS 发展到极大，2π(s)(4.5-2s) 是归一化系数。（1）式表明的是年龄为s的EAS 前锋面次级粒子随距离前锋面距离 $\mathbf { r }$ 增大而减小，年龄越大减小越慢次级粒子密度分布函数越平坦。当一个天顶角为 $\varphi$ 的 EAS 前锋面接近探测器阵列时，近似认为在前锋面到达探测器的几十纳秒内次级粒子密度变化忽略不计，那么到达任意位置 $( x , y$ ）处探测器单元的次级粒子密度为：

$$
\sigma ( x , y ) = \rho ( r ) \cos \varphi
$$

其中

$$
r = { \frac { \left( x - x _ { 0 } \right) ^ { 2 } ( 1 - \sin ^ { 2 } \varphi \cos ^ { 2 } \theta ) + ( y - y _ { 0 } ) ^ { 2 } ( 1 - \sin ^ { 2 } \varphi \sin ^ { 2 } \theta ) - 2 ( x - x _ { 0 } ) ( y - y _ { 0 } ) \sin ^ { 2 } \varphi \sin \theta \cos \theta } { \sqrt { \left( x - x _ { 0 } \right) ^ { 2 } + \left( y - y _ { 0 } \right) ^ { 2 } } } }
$$

$( \boldsymbol { x } _ { O } , \boldsymbol { y } _ { O } )$ 是地平面上的芯位， $( \theta , \varphi )$ 是EAS 的方向，其中 $\theta$ 是方位角， $\varphi$ 是天顶角， $\left( x , y \right)$ 是平面上任意位置探测器单元的坐标。从表达式可以看出 $\sigma ( x , y )$ 与 EAS的芯位和方向有关，其数学结构十分复杂不方便分析其特征。为了更加直观地理解前锋面次级粒子分布情况，进行了数值计算并得到不同天顶角和方位角事例投射到地面的次级粒子分布情况如图2所示。从图2可以看出EAS次级粒子密度呈现出明显地对称性，当天顶角为 $0 ^ { \circ }$ 时次级粒子密度等高线为同心圆，当天顶角不为零时其等高线为同心椭圆，天顶角越大椭圆的离心率越大。因此可以用椭圆系方程来描述次级粒子密度等高线：

$$
\frac { \left[ ( x _ { n } - x _ { 0 } ) \cos \theta + ( y _ { n } - y _ { 0 } ) \sin \theta \right] ^ { 2 } } { { a _ { n } } ^ { 2 } } + \frac { \left[ ( x _ { n } - x _ { 0 } ) \sin \theta + ( y _ { n } - y _ { 0 } ) \cos \theta \right] ^ { 2 } } { { b _ { n } } ^ { 2 } } = 1
$$

其中 $( \boldsymbol { x } _ { O } , \boldsymbol { y } _ { O } )$ 是这一系列椭圆的共同中心， $a _ { n } , b _ { n }$ 分别是第 $\mathbf { n }$ 个椭圆方程的长短轴， $\theta$ 是EAS的方位角，椭圆长短轴之比 $a _ { n } / b _ { n } { = } f ( \varphi , s )$ 是EAS天顶角 $\varphi$ 和年龄s的函数。

![](images/f878dfb68bb5fa6b40e56f4f691f4db95d0811dc252bba27ba6c386a0d297290.jpg)

图2：利用NKG 函数数值计算得到的不同天顶角 EAS 带电次级粒子密度其方位角都是 $4 5 ^ { \circ }$ ，其中a,b,c的天顶角分别为 $0 ^ { \circ }$ ，$3 0 ^ { \circ }$ ， $4 5 ^ { \circ }$ ，色度图为次级粒子密度的常用对数，d，e， $\textsf { f }$ 分别为a，b，c的等高线表示。

Figure2:TheazimuthanglesoftechargedsecondaryparticledensityofEASatdiffrentznithanglescalculatedbyusingtheNKG function are all $4 5 ^ { \circ }$ ,where the zenith angles of a,b,and c are $0 ^ { \circ }$ $3 0 ^ { \circ }$ ,and $4 5 ^ { \circ }$ ,respectively. The degree diagram is the common logarithm of the secondaryparticle density,andd,e,and farerepresented bythecontour lines of a,b,and c,respectively.

WCDA各基本单元PMT探测到的NPE与该位置的次级粒子密度之间是线性关系，因此其NPE 高线可近似为椭圆。用椭圆方程拟合NPE的等高线可以得到一系列的同心椭圆，这些椭圆的共同中心就是EAS 的芯位，椭圆的长短轴之比反映 EAS 天顶角信息，椭圆的长轴反映了EAS 的方位角信息。拟合NPE 的等高线系列来重建芯位，一方面对于芯位位于探测器边沿使得 EAS 对称性严重破坏的事例，可以通过局部信息来"补齐"椭圆等高线（如图3所示），利用对称性来重建出准确的芯位；另一方面利用所有椭圆应该"同心"的特点，舍弃掉信噪比较低的数据组，从而实现抑制噪声的效果，具体算法流程如图4所示：

第一步：读取事例获取对芯位重建有用的单元探测器坐标 $( \boldsymbol { x } _ { i } , \boldsymbol { y } _ { i } )$ ’  
第二步：把数据按照 $N _ { P E }$ 降序排列，并把数据分成 $\mathfrak { n }$ 组，  
第三步：拟合得到 $\mathfrak { n }$ 个椭圆方程得到 $\mathfrak { n }$ 个 $( { \boldsymbol { x } } _ { O i } , { \boldsymbol { y } } _ { O i } )$ ，  
第四步：求出其平均值 ${ \overline { { X } } } _ { 0 } , { \overline { { y } } } _ { 0 }$ 、标准差 $x _ { 0 S D } , ~ y _ { 0 S D }$ ，偏差值 $\big | \overline { { x } } _ { 0 } - x _ { 0 i } \big | , \big | \overline { { y } } _ { 0 } - y _ { 0 i } \big |$ ，

第五步：判断是否满足 $\left| \overline { { x } } _ { 0 } - x _ { 0 i } \right| < d e _ { c u t }$ && $\left| { \overline { { y } } } _ { 0 } - y _ { 0 i } \right| < d e _ { c u t }$ ，如果满足进入下一步，否则去掉偏差值最大的点，回到第四步，直到满足条件或者 $\mathrm { n } { < } 3$ ，

第六步：计算芯位30米内的圆形区域与30到40米区域环形区域的 $N _ { P E }$ 总和之比NBN,并且判断 NBN 是否大于 $N B N _ { m i n }$ ，若大于则输出上一步得到的 $( \overline { { x } } _ { 0 } , \overline { { y } } _ { 0 } )$ 为重建芯位，否则判断重建失败，该事例不纳入统计。

![](images/83323e0424bec5c8a2e18ac4834d7b7e466a42c82fbfcb582cdb781f06588014.jpg)  
图3：椭圆拟合法重建芯位示意图

Figure 3: Schematic diagram of core position reconstruction by ellipse fitting method 该方法中涉及到的几个参数的选择和使用：

1.NPE最大的点。对于芯内事例，NPE最大的点不能用于拟合椭圆。这个点很可能位于椭圆中心附近。

2.椭圆系中拟合椭圆所用的数据点的个数。离芯位越远的椭圆等高线上的探测器单元越  
多，因此用于拟合一个椭圆的点就应该越多，并且理论上与离芯位距离成正比，因此我们采  
用从内到外线性增加的分组方式来对数据进行分组。上文的推导表明拟合平面上任意椭圆最  
少需要5个点，故取每组数据为 $5 n$ $( n { = } I , 2 , 3 \cdots )$ ，即第一组数据5个点，第二组数据10 个  
点，第三组15个点以此类推。由此可得触发探测器单元数 $N _ { h i t }$ 与拟合椭圆数 $\mathfrak { n }$ 有如下关系：  
$\frac { 5 n ( n + 1 ) } { 2 } < N _ { h i t }$ (5)

![](images/11fa7a67fb83488cdf2310a2fbd860375abfcbdbb90012ec8510c7a75b61d62d.jpg)  
图4：椭圆拟合法算法流程图  
Figure 4: Algorithm flow chart of ellipse fitting method

3. $d e _ { c u t }$ 。椭圆拟合法的核心是用椭圆方程拟合NPE 等高线得到椭圆中心 $( \boldsymbol { x } _ { O } , \boldsymbol { y } _ { O } )$ 作为宇宙线事例的芯位。由于所有的椭圆等高线应该是“同心"的，理论上只需要拟合一条等高线就可以得到芯位，但是为了减小统计误差提高芯位重建的精度，需要充分利用数据拟合尽可能多的椭圆。由于物理涨落和探测器单元差异等原因，拟合得到的椭圆系列中心坐标会有一定的偏差。通常会出现以下三种情况：（1）椭圆系中心坐标分布在很小的区域内，可以取这些点的重心作为最终的重建芯位坐标；（2）椭圆系中心坐标总体密集分布、个别偏离较远，需要去除掉偏离较远的那些坐标值，以密集点群的重心作为芯位（如图5所示）；（3）椭圆系中心坐标分布极为离散，这种事例作为无效事例处理。 $d e _ { c u t }$ 是用来量化判断离散度的标准，通常选择 $d e _ { c u t }$ 的值越小得到的芯位精度越高，但是选择太小的 $d e _ { c u t }$ 可能会丢掉部分有效数据导致重建效率很低，通过多次尝试比对，选择了 $5 \mathrm { m }$ 这一数值，能够兼顾芯位精度与重建效率。在上述第（2）种情况中，通常中低能事例的小NPE 数据组拟合的椭圆中心坐标与芯位偏差较大，这是由于NPE比较小的探测器单元信号信噪比低；而高能事例的大 NPE数据组拟合的椭圆中心坐标与芯位偏差较大，可能是因为高能事例芯位附近的光电倍增管已经饱和。

4. $x _ { O i }$ 和 $\mathrm { y _ { 0 i } }$ 的标准差。用 $x _ { O i }$ 和 $y _ { O i }$ 的标准差作为评判参数来判断这一系列椭圆中心的离散程度，若其标准差很大（如上的（2）（3）两种情况），说明一些数据组几乎不包含芯位信息，这些 NPE 主要是由噪声造成的，因此把这些数据当做噪声去除掉；而椭圆中心坐标很集中则表明与之对应的数据中噪声比很低，保留其对芯位坐标的贡献。图5是一个事例分组重建出的各个椭圆中心坐标，最终只保留红框内的密集点求平均作为最终的芯位重建结果。

![](images/482b02d9e780ba460265f15a99a6fdb516f73b0acd732cc2f56f3c519f8f30ae.jpg)  
图5：椭圆拟合法重建出的各个椭圆中心和真实芯位，其中蓝色“+”是各组数据重建得到的椭圆中心，红色 $" * "$ 是真实芯位。 Figure 5:Thecenterof each elipseand therealcore positionreconstructedbytheelipse fiting method,where the blue $" \cdot "$ is the center of the ellipse reconstructed from each group of data,and the red "\*" is the real core position.

5..NBN与 $N B N _ { m i n }$ 。得到满足离散度要求的椭圆中心坐标平均值 $( \overline { { x _ { 0 } } } , \overline { { y _ { 0 } } } )$ 后，还需要利用其附近10米圆和10到20米的环内NPE总和之比 $N B N { = } N _ { I O } / N _ { 2 O }$ 判断该点周围的NPE分布符合芯位附近的NPE 分布特点， $N B N { > } N B N _ { m i n }$ 表明重建芯位误差小于 $1 0 \mathrm { m }$ ，可以把计算结果作为重建芯位的最终结果，其中 $N B N _ { m i n }$ 的取值选择可以通过数值估计和数据统计得到。在需要重建阵列边界附近的芯外事例的时候，考虑到 $N _ { I O }$ 可能为0，可以用 $N B N { = } N _ { 2 O } / N _ { 3 O }$ 或$N B N { = } N _ { 3 O } / N _ { 4 O }$ 也能达到同样的判断效果，只是涨落变大且精度变差，只能分别判断重建芯位误差是否低于 $2 0 \mathrm { m } , 3 0 \mathrm { m }$

# 3.椭圆拟合法重建结果

蒙特卡罗模拟是研究宇宙线物理的重要手段，本文借助Corsika模拟的广延大气簇射和Geant4 模拟的探测器响应数据来验证椭圆拟合法重建芯位的实际效果。选取能量为10TeV到 $1 0 \mathrm { P e V }$ 的质子事例，其天顶角为 $0 { - } 4 0 ^ { \circ }$ 服从 $c o s ^ { 2 } \theta$ 分布，方位角为 $0 { - } 3 6 0 ^ { \circ }$ 服从均匀分布。探测器参考LHAASO-WCDA1，各项参数均保持一致，在坐标系中探测器阵列区域为（-75$\mathrm { m { < x < 7 5 ~ m , - 7 5 ~ m < y < 7 5 ~ m ) } }$ ，在数据中加入 $6 0 \mathrm { k H z }$ 的噪声并利用遍历法取 $2 0 0 ~ \mathrm { { n s } }$ 的时间窗口去噪之后信噪比约为70/22。分别用重心法和椭圆拟合法来重建事例并比较其重建精度和事例利用率。首先需要验证本算法对于芯位位于探测器阵列边沿事例的重建能力，选取真实芯位 $\displaystyle ( \mathbf { \boldsymbol { x } } _ { \mathrm { c t } } , \mathbf { \boldsymbol { y } } _ { \mathrm { c t } } )$ 位于 $7 5 \ \mathrm { m } { < } \mathrm { x } { < } 8 5 \ \mathrm { m } , 7 5 \ \mathrm { m } { < } \mathrm { y } { < } 7 5 \ \mathrm { m } )$ ）探测器阵列外紧贴边界的能量为10-100TeV质子事例重建芯位，得到结果如图6所示。从图中可以看出，重建芯位与真实芯位分布基本一致，从右图可以看出大多数重建芯位的偏差 $d r = \sqrt { ( x _ { c t } - x _ { t r } ) ^ { 2 } + ( y _ { c t } - y _ { t r } ) ^ { 2 } }$ 小于 $1 0 \mathrm { m }$ 取 $d r$ 的 $6 8 \%$ 作为分辨率约为9.6米。

![](images/3d23b0a085eccfb694b2196cd190a46e15d25fab1aba8147614dc3eca345db03.jpg)  
图6：真实芯位和重建芯位分布(左），重建芯位偏差统计（右)

Figure6:Realcorepositionndecostructionorepositiodistrbution(left)ecostructioncorepositiodviatiostatisticsight)

为了定量描述该方法重建芯位的精度和对探测器面积的利用率，分别取4000个能量为1-10 TeV、10-100 TeV、100-1000 TeV、 $1 { \mathrm { - } } 1 0 \mathrm { P e V } ,$ ，真实芯位均匀分布在 $- 1 5 0 \mathrm { m } { < } \mathrm { x } { < } 1 5 0 \mathrm { m } , - 1 5$ 0$\mathrm { m } { < } \mathrm { y } { < } 1 5 0 \mathrm { m }$ ）区域的质子事例，用重心法和椭圆拟合法重建芯位。由于真实芯位均匀分布在$3 0 0 \mathrm { m } { \times } 3 0 0 \mathrm { m }$ 的区域，而探测器阵列区域为 $1 5 0 \mathrm { m } { \times } 1 5 0 \mathrm { m }$ ，因此取重建成功的事例数与芯位$\begin{array} { r } { \eta = \frac { N _ { r } } { N _ { i n } } } \end{array}$ $d r$ $6 8 \%$ 位分辨率，得到结果如下图7所示。

从图7中可以看出对于所有能量段的质子事例，椭圆拟合法芯位重建精度都比重心法要好，并且椭圆拟合法能够显著提高探测器阵列利用率，并且随着能量增大其增幅更加显著。对于 $\boldsymbol { 1 - 1 0 } \mathrm { T e V }$ 的事例椭圆拟合法的探测器面积利用率略小于1,这意味着只有少数芯位落在探测器边沿的事例重建不好，面积利用率随着能量增大而增大，对于能量为 $\boldsymbol { 1 - 1 0 \mathrm { P e V } }$ 的事例其面积利用率大于1.3，这意味着约有 $30 \%$ 位于探测器阵列外部事例的芯位重建符合精度要求。左图中椭圆拟合法重建芯位分辨率随着能量增大而增大的现象不符合预期，这是由于把大量芯外事例纳入统计量导致面积利用率增大造成的，通过归一化面积利用率后的芯位分辨率可以得到证实。

![](images/d421c4c9843a90a6376b16262105e381f0120e6f0100f77b4649bf066a959955.jpg)  
图7：椭圆拟合法和重心法芯位重建分辨率 (左）和探测器阵列面积利用率（右)

Figure7:Ellpsefiting methodandcenterof gravitymethodcorepositionreconstructionresolution(left）anddetectorarayarea utilization (right)

各能段面积利用率都为0.67的情况下椭圆法和重心法的重建分辨率如图8所示，在重建效率相同的情况下，椭圆拟合法的芯位分辨率显著优于重心法；并且两种方法的芯位分辨率都随着能量增加而降低，其中椭圆拟合法由于本身能够排除大部分噪声干扰，其重建精度随能量变化不显著。

![](images/2a4a35c1a107a57e94982dbace3ad5dcbee14af195df9006dc141df23afd6cc2.jpg)  
图8：面积利用率为0.69时各能段的芯位重建分辨率

Figure 8:Reconstruction resolution of core positions for each energy segment when the area utilization ratio s 0.69

# 4.结论和展望

通过蒙特卡罗模拟数据检验，椭圆拟合法相比重心法具有明显优势，椭圆拟合法的优势主要体现在两个方面，一是充分考虑了EAS 的对称性特征，利用其对称性能够准确重建探测器阵列边沿乃至探测器区域之外的事例，二是通过分组重建的方式有效消除了噪声对芯位重建的影响，从而显著性提高芯位重建的精度。从 $1 5 0 ~ \mathrm { m } \times 1 5 0 ~ \mathrm { m }$ 的 WCDA-I模拟数据的重建结果来看，椭圆拟合法重建芯内事例芯位重建精度可以达到5米以下，各能段分辨率不到重心法的 $5 0 \%$ ，重建精度相比于重心法有显著提高；另一方面能够解决重心法无法准确重建探测器阵列边沿事例芯位的问题，重建低能事例的面积利用率约比重心法高 $4 0 \%$ ，重建高能事例的面积利用率则接近重心法的2倍；相比于重心法其芯位重建精度和探测器阵列面积利用率两方面都有显著改善。

椭圆拟合法的噪声抑制能力源自于EAS 次级粒子触发的 $\mathbf { N } _ { \mathrm { P E } }$ 信号等高线为一系列同心椭圆而噪声信号均匀分布，可以根据这一原理设计去噪算法，在遍历法去噪的基础上利用芯位信息实现深度去噪。此外发现前锋面次级粒子到达时间也关于簇芯对称分布，可以基于这一特征通过分区重建方向规避锥面修正参数依赖带来的问题，并且利用方向信息实现进一步的深度去噪。后续研究主要沿着这一方向展开。

参考文献：   
[1] CAO ZHEN,CHEN MINGJUN, et al. Introduction to Large High Altitude Air Shower Observatory(LHAASO) [J.Chinese Astronomy and Astrophysics,2019, 43(4): 457-478.   
[2] 祝凤荣．用ARGO-YBJ实验的 SPT 寻找 ${ \sim } \mathrm { G e V }$ 的伽玛暴[M]．西南交通大学出版社,2013.   
[3] VIKAS, JOSHI, et al .A template-based $\gamma$ -ray reconstruction method for air shower arrays[J].Journal of Cosmology and Astroparticle Physics, 2019,2019(1).   
[4] FENG YOU LIANG,ZHANG YI, et al. Lateral distribution of EAS muons measured for the primary cosmic ray energy around 100 TeV[J]. Chinese Physics C,2019,43(7):97-102.   
[5]Antonov,R.A. Spatial and temporal structure of EASreflected Cherenkov light signal[J]. Astroparticle physics,   
2019,108:24-39.   
[6] LI CONG, HE HUIHAI. Measurement of muonic and electromagnetic components in cosmic ray air showers using LHAASO-KM2A prototype array[J]. Physical Review D,2018, 98(4): 042001- 042001.   
[7] Rajat, K. A novel approach for deducing the mass composition of cosmic rays from lateral densities of EAS particles[J].EPL (Europhysics Letters),2019,127(3).   
[8] B BARTOLI. EAS age determination from the studyof the lateral distribution of charged particles near the shower axis with the ARGO-YBJ experiment[J]. Astroparticle physics,2017, 93: 46-55.   
[9]I M Brancus .Correlated features of arrival time and angle-of-incidence distributions of EAS muons[J]. Astroparticle physics,1997, 7(4): 343-356.   
[10] 王晓洁.LHAASO--WCDA 本底噪声过滤与簇射事例重建方法的研究[D].中国科学院大学,2017.   
[11] D RAVIGNANI. Reconstruction of air shower muon densities using segmented counters with time resolution[J]. Astroparticle physics,2016, 82:108-116.   
[12] WD APEL. Cosmic rayenergy reconstruction from the S(500） observable recorded in the KASCADE-Grande air shower experiment[J]. Astroparticle physics, 2016,77:21-31.   
[13]D,Beznosko. Extensive air showers event reconstruction using spatial and temporary particle distribution at Horizon-Texperiment[J].1st Tensor Polarized Solid Target Workshop,2019,1342(1).   
[14] M.,ERDMANN. A deep learning-based reconstruction of cosmic ray-induced air showers[J]. Astroparticle physics,2018,97: 46-53.   
[15] H HEDAYATI. A STATISTICAL METHOD FOR RECONSTRUCTING THE CORE LOCATION OF AN EXTENSIVE AIR SHOWER[J]. The Astrophysical journal,2015, 810(1): 1-1.   
[16] TOMA G. Investigation of the EAS Lateral Particle Density at $5 0 0 \ \mathrm { m }$ Distance from Shower Core[J]. AIP Conference Proceedings,2008, 972(1): 549-553.   
[17] CHEN SONG ZHAN .Status of LHAASO offcial software:Simulation and Reconstruction[C]. The 8th International Workshop on Air Shower Detection At High Altitudes.2O17:1-37.   
[18] CAO ZHEN.A future project at tibet: the large high altitude air shower observatory (LHAASO)[J].中国物 理C（英文版， 2010,34(2):249-252.   
[19] 曹臻,陈明君,陈松战等．高海拔宇宙线观测站LHAASO 概况[J].天文学报,2019,60(3):3-18.   
[20]IN KIROV. Constant efficiency selection of EAS with energies 105-107 GeV at observation level $7 0 0 ~ \mathrm { g }$ cm-2[J]. Journal of Physics G: Nuclear and Particle Physics,1994,20(9):1515-1526.   
[21]WU SHA.Study of the trigger mode of LHAASO-KM2A[J].Astroparticle physics,2018,103: 41-48.   
[22]An Y X.The performance of a prototype array of water Cherenkov detectors for the LHAASO project[J] .Nuclear Instruments & Methods in Physics Research Section A,2013,724: 12-19.   
[23] CAO ZHEN.A future project at tibet: the large high altitude air shower observatory (LHAASO)[J].中国 物理C（英文版）,2010,34(2): 249-252. CII CUII WANG

[24] YUJUAN. LIU. LHAASO-KM2A simulation[C], 32ND INTERNATIONAL

COSMICRAYCONFERENCE， BEIJING 2011.   
[25] CUI SHU WANG. Simulation on gamma ray astronomy research with LHAASO-KM2A[J]. Astroparticle physics,2014,54:86-92.   
[26] CAO ZHEN.Observation of the Crab Nebula with LHAASO-KM2A-a performance study.[J].中国物理 C：英文版,Vol.45，No.2(2021) 025002.   
[27] GAISSER,T.,Hillas,A.M.,1977,15th ICRC,vol.8,p. 353.   
[28] GREISEN,K.,1956,Prog. Cosmic Ray Phys., 3,1.   
[29] ABU ZAYYAD T,et al.,2001,APh,16,1.   
[30] COLLABORATIONH，ABEYSEKARAA U，ALFAROR ，et al. The HAWC Gamma-Ray   
Observatory: Design, Calibration and Operation[J].Physics,2013.   
[31]ZHANG BING KAI. CHEN BAO MIN ,GAO BO ，et,al. Development and Testing of WCDA Time Calibration System [J].ASTRONOMICAL RESEARCH& TECHNOLOGY，Vol17,No 3.Jul.,2020.   
[32] 吴文雄，左雄，肖刚,等.LHAASO-MD光电倍增管性能测试[J],天文研究与技术,Vol17,No 2.Apr.,2020.

# A New Core Position Reconstruction Method Based on Ground Particle Detector Array

Abstract:Core position reconstruction is the prerequisite and basis for physical analysis of ground cosmic ray detection experiments.Based on the symmetry of the extended air shower and the characteristics of the detector, this paper proposes a new core position reconstruction algorithm—elipse fiting method,which is used to reconstruct the core position of simulated data and compare it with the center of gravity method.Forthe event of cosmic ray protons in the core with an energy greater than $1 \ \mathrm { T e V } .$ ，the core position resolution is less than $5 \mathrm { ~ m ~ }$ ， which is significantly better than the center of gravity method; for the event with an energy greater than $1 \ \mathrm { T e V }$ （204号 within a range of $2 0 \mathrm { ~ m ~ }$ near the array boundary,the core position resolution is less than $1 0 \mathrm { ~ m ~ }$ .It has significant advantages over traditional methods.Because this method can reconstruct edge events and some out-of-core events under the premise of ensuring accuracy, the utilization rate of the events is greatly increased.For the $1 { - } 1 0 \ \mathrm { P e V }$ proton event, the area utilization rate of the detector array is about twice that ofthe center of gravity method.

Keywords: Cosmic rays; Extended air shower; Events reconstruction; symmetry; Water Cherenkov array