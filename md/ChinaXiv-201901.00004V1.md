# 一种双水平集模型分割左心室膜的方法\*

李林，李军华，邵晓宇

(南昌航空大学 江西省图像处理与模式识别重点实验室，南昌 330063)

摘要：针对目前左心室内外膜分割方法，存在分割出的轮廓正则性差、分割心室膜模糊边缘不完全和分割效率低等问题。提出新双阱势函数和各向异性梯度矢量流（AGVF）改进水平集模型能量函数，用融合0水平集和k水平集的双水平集，同时分割左心室内外膜的方法。首先，用改进Hough 变化圆检测算法，定位心室内外膜初始位置；然后利用双水平集模型同时分割内外膜。观察和对比分析实验结果，该方法能够分割出平滑的左心室内外膜轮廓；能够分割出的符合临床定义的左心室内外膜轮廓，且分割MRI图像左心室内外膜轮廓重叠率平均提高到0.9569。

关键词：新双阱势；AGVF；Hough变换；双水平集模型；分割左心室膜 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.09.0672

Double level set model for segmentation of left ventricular membrane

Li Lin, Li Junhua, Shao Xiaoyu (Key Laboratoryof Image Processing & Patern Recognition in Jiangxi Province, Nanchang Hangkong University, Nanchang 330063,China)

Abstract: In view of the existing endocardiumand epicardium contour of left ventricle segmentation methods,there are some problems such as the poor regularityof segmented contour,segmenting the fuzzy edge of ventricular membrane incompletely and low segmentation eficiency.This paper proposes anew double well potential function and anisotropy gradientvectorflow(AGVF)energy functionimproved levelsetmodel,with thefusionofzero level setandklevelsetof the doublelevelset,thedivisionofleftventricularinnerandouter membrane methodatthesametime.Firstof allwith the modified Hough change detectionalgorithm,positioning ventricularendocardiumandepicardiuminitial position;Then,the double level set model is used to segment the endocardiumand epicardium simultaneously.The experimental results show that the proposed method of this paper can segment smooth endocardium and epicardium contour of left ventricle.The analysis ofexperimental datum demonstrate thatthe methodof this papercan segment endocardiumand epicardium contour of left ventricleconfirms to theclinical definition,And increases averagely the overlaprateof the endocardium and epicardium contour on MRI images to O.9569.

Key words: the new double wellpotential; agvf; Houghtransform;two-level set model;segmentation of leftventricular membrane

# 0 引言

近年，心血管疾病的高死亡率，致使心脏左心室内外膜分割成为研究的热点。常用方法包含阈值法[I、聚类法[2]、区域生长法[3]、主动轮廓模型法[4]、水平集法[5]和动态规划方法[]。Lee 等人[7]利用区域生长和迭代阈值法分割做心室内膜，用提取的内膜边界引导主动轮廓模型提取外膜；李晓宁等人[8融合Mean-Shift聚类算法的视觉显著性方法对心内膜初定位，利用GVFSnake模型分割内外膜；朱错等人[用结合K均值的自适应核函数带宽的Mean-Shift算法分割图像，区域生长法提取目标区域；Dharanibai等人[1o]利用动态规划分割心室外膜用融合Otsu 算法的主动轮廓模型分割心室内膜，；王兴家等人[1提出用嵌入先验知识的耦合水平集算法模型分割左心室内外膜。由于人体心脏的复杂性，在临床上定义肌小梁和乳头肌属于左心室内腔；且认为只要腔室凸出部分的周长超过 $5 0 \%$ 被心肌包围，就认定为该部分心室为心肌的一部分；每个心跳周期影像数据量巨大，容易出现伪影、灰度分布差别大等问题，导致这些分割算法分割左心室内外膜模糊边缘时，会出现提取边缘不符合临床要求且正则性较差等问题。

针对分割心室内外膜弱边缘正则性差，小梁肌和乳头肌的分割不彻底问题。提出用融合改进Hough圆检测定位的双水平集模型方法分割左心室内外膜。用改进Hough圆检测进行定位，定位的轮廓作为内外膜分割初始位置；用融合各向异性梯度矢量流（anisotropic gradient vector flow，AGVF）的双水平集模型分割出内外膜轮廓。

# 1 心室膜自动分割方法

# 1.1心室膜自动分割流程

本文提出自动分割左心室内外膜方法主要步骤：包含改进Hough变换定位和双水平集模型分割，分割方法流程图如图1所示。为简化心室内外膜分割流程，解决人为干预手动设置模型分割初始位置问题，采用改进Hough变换圆检测方法，定位心室内外模型分割初始位置；针对心室膜模糊边缘和凹陷区域，提出融合新双阱势（newdouble-wellpotential,NDWP）和AGVF的双水平集模型方法分割心室内外膜。

![](images/d9596a5025c87e5f8aa07986e789bd1f915cfafabd244052c8b83e614c92669b.jpg)  
图1心室内外膜分割流程图

# 1.2定位模型初始轮廓

传统水平集模型需要人为设置分割初始位置，造成分割流程复杂且低效，容易受人为主观性影响，为克服这一问题，提出用图像边缘信息约束的改进Hough变换圆检测方法自动获取初始轮廓。

传统Hough变换[12]的算法原理是利用点与线的的对偶性，将图像空间的线条变为空间的聚焦点，从而检测给定图像是否存在给定性质的曲线。圆的方程为

$$
\left( x - a \right) ^ { 2 } + \left( x - a \right) ^ { 2 } = r ^ { 2 }
$$

其中： $( a , b )$ 为圆心， $\boldsymbol { r }$ 为半径。首先用算子对图像进行边缘检测得到二值图像；Hough变换会将图像空间对应到 $( a , b , r )$ 参数空间，取和图像平面一样的参数平面，以二值图像中每一个非零点为圆心，用设定的半径在参数平面上画圆，符合$( a , b , r )$ 的点进行累加，即对圆覆盖的坐标点进行投票，随着半径步长一直循环运算到设定半径的最大值；最后找出参数平面上的峰值，得到 $( a , b , r )$ 值及其在图像对应位置显示形状，而后通过调整阈值得到目标圆形。传统Hough变换中有三个自由参数 $( a , b , r )$ ，三个参数在三维空间中进行投票累加（设自适应圆检测半径范围为 $R$ )，则总共进行了RN投票计算，复杂度函数为： $f \left( N \right) = O \left( N ^ { 3 } \right)$ 。其中， $N$ 为图像边缘检测后，边缘像素点数。

![](images/3c8df8d6abe9d371286aed39043c7acbd8d2ecb318362cbaffce408aeb2ffafc.jpg)  
Fig.1The flow chart ofthe endocardium and epicardium segmentation   
图2Hough 变换圆检测 Fig.2Hough transform round detection   
图3优化算法定位过程  
Fig.3Localization process of optimization algorithm

传统Hough方法是对检测出边缘像素点进行遍历运算，最后输出累加像素最多的圆。图2中，(c)是未输入圆心大致位置，对边缘检测图遍历运算后输出的定位结果，(d)是输入圆心位置，得到的左心室内腔定位结果。这种遍历运算耗时较久，且检测结果定位效果较差。

传统Hough变换圆检测自适应定位，定位结果不满足要求；输入圆心位置后对内腔进行定位，依然无法避免人为对分割心室膜初始位置的干预。为解决人为干预圆心种子点设置，提高定位精度和效率。改进Hough变换圆检测方法，在对图像进行找圆定位前，对输入图像进行OTSU自适应阈值分割处理，像素较大点连成区域设为前景区域，累加器先累加前景区域的像素点；为避免检测出多个无用圆，利用图像边缘信息进行约束，在有限时间间隔内只允许沿着梯度方向的像素点进行投票[13]。改进后半径沿着边缘点 $\left( x , y \right)$ 法线方向变化，而不是所有方向的遍历变化。圆心计算公式为

$$
\scriptstyle { \left\{ { a = x - r \cos \theta } \atop { b = y - r \cos \theta } \right.}  
$$

其中： $\theta { = } \arg \bigl ( G _ { y } / G _ { x } \bigr )$ ， $G _ { y } , G _ { x }$ 是对应 $y , x$ 方向的梯度。计算过程中，

$$
\scriptstyle { \left\{ \begin{array} { l l } { \sin \theta = { \frac { G _ { y } } { \sqrt { { G _ { y } } ^ { 2 } + { G _ { x } } ^ { 2 } } } } } \\ { \cos \theta = { \frac { G _ { x } } { \sqrt { { G _ { y } } ^ { 2 } + { G _ { x } } ^ { 2 } } } } } \end{array} \right. }
$$

改进Hough变换圆检测的具体步骤：

a）根据左心室图像特征，利用先验知识确定半径的变化区间；b）对输入图像进行OTSU自适应阈值分割处理，提取出像素较大点连成的前景区域；c）利用图像边缘信息，约束前景区域像素点沿着边缘梯度方向进行投票；d)输出所有像素投票后，累加数组中值最大像素对应的圆。

对改进后Hough变化圆检测方法进行复杂度分析。由于图像边缘信息的约束，沿着梯度方向的像素点进行投票，变成了三个自由参数在二维空间中进行投票，则共进行了RN2投票计算，算法复杂度函数为： $f _ { 1 } \left( N \right) = O \left( N ^ { 2 } \right)$ 。其中， $N$ 为图像经过OTSU自适应阈值分割处理后，像素为1的像素点总数。

对比图2和3可以看出，使用改进后方法定位效果较好，定位结果被整个内膜包围，提高了对内膜的定位精度。对比$f _ { 1 } ( { \cal N } )$ 和 $f ( N )$ ，改进后检测圆算法，降低了算法空间复杂度，提高了运算效率。原Hough变换圆检测耗时3.209秒，改进后只需要0.3920秒就能准确定位到心室内膜。

可(a)Otsu 处理 (b)定位结果(a)Otsu processing (b)Locating result

# 1.3双水平集模型分割方法

# 1.3.1水平集算法原理

水平集[14]的算法思想就是用高维度表示低维度，在高维曲面用隐函数等值点来表示平面上闭合曲线轮廓。在传统的水平集算法模型中，出现反复初始化、曲线结果正则性差等问题，Li 等人[15]提出了一种距离正则项水平集（distanceregularizedlevelset evolution，DRLSE）模型算法，解决了传统水平集模型反复初始化问题。根据曲线的运动规律，定义能量泛函为

$$
\varepsilon \left( \phi \right) = \mu R _ { \scriptscriptstyle p } \left( \phi \right) + \varepsilon _ { \mathrm { e x t } } \left( \phi \right)
$$

其中： $R _ { p } \left( \phi \right)$ 是定义的距离正则项， $\mu$ 是大于零的常数，外部能量项 $\varepsilon _ { \mathrm { e x t } } \left( \phi \right)$ 由图像先验信息或图像底层视觉特征决定。

水平集的距离正则项被定义为

$$
R _ { p } \left( \phi \right) = \int _ { \Omega } p ( | \nabla \phi | ) d x
$$

其中： $p$ 为势函数， $p : [ 0 , \infty )  R$ 。传统势函数（double-wellpotential，DWP）定义为

$$
p _ { 1 } ( | \nabla \phi | ) = \left\{ \begin{array} { l l } { \displaystyle \frac { 1 } { \left( 2 \pi \right) ^ { 2 } } \big ( 1 - \cos \big ( 2 \pi | \nabla \phi | \big ) \big ) , | \nabla \phi | \leq 1 } \\ { \displaystyle \frac { 1 } { 2 } ( | \nabla \phi | - 1 ) ^ { 2 } , \qquad | \nabla \phi | \geq 1 . } \end{array} \right.
$$

偏微分方程为

$$
\frac { \partial \phi } { \partial t } = \left\{ \begin{array} { l l } { d i \nu \big ( \sin c \big ( 2 | \nabla | \big ) | \nabla | \big ) } & { | \nabla | \le 1 } \\ { d i \nu \Bigg ( \Bigg ( 1 - \frac { 1 } { | \nabla | } \Bigg ) | \nabla | \Bigg ) } & { | \nabla | \ge 1 } \end{array} \right.
$$

扩散率为

$$
r _ { 1 } ( \lvert \nabla \phi \rvert ) = \left\{ \begin{array} { l l } { \sin c ( 2 \lvert \nabla \phi \rvert ) } & { \lvert \nabla \phi \rvert \leq 1 } \\ { 1 - \displaystyle \frac { 1 } { \lvert \nabla \phi \rvert } } & { \lvert \nabla \phi \rvert \geq 1 } \end{array} \right.
$$

# 1.3.2新双阱势函数

水平集函数的正则性在水平集曲线演变中是内在保持的，DRLSE水平集分割模糊边界得到的边界正则性太差，为得到更加平滑的分割轮廓曲线，在水平集模型中提出NDWP代替传统势函数约束模型曲线演化。

定义新双阱势函数NDWP为

$$
p _ { 2 } \left( \left| \nabla \phi \right| \right) = \left\{ \begin{array} { l l } { \displaystyle \frac { 1 } { 2 } ( | \nabla \phi | \left( | \nabla \phi | - 1 \right) ) ^ { 2 } , } & { | \nabla \phi | \leq 1 } \\ { \displaystyle \frac { 1 } { 2 } ( | \nabla \phi | ^ { 2 } - 1 ) - \log ( | \nabla \phi | ) , } & { | \nabla \phi | \geq 1 . } \end{array} \right.
$$

如此定义，知双阱势函数有两个最小值分别是 $\mid \nabla \phi \mid = 0$ 和$\lvert \nabla \phi \rvert = 1$ 。

NDWP扩散率为

$$
r _ { 2 } \left( \left| \nabla \phi \right| \right) = \left\{ \begin{array} { l l } { \displaystyle ( 2 | \nabla \phi | - 1 ) ( | \nabla \phi | - 1 ) } & { \displaystyle | \nabla \phi | \leq 1 } \\ { \displaystyle 1 - \frac { 1 } { | \nabla \phi | ^ { 2 } } \ast \log _ { 1 0 } e } & { \displaystyle | \nabla \phi | \geq 1 } \end{array} \right.
$$

偏微分方程为

$$
\frac { \partial \phi } { \partial t } = \left\{ \begin{array} { l l } { \displaystyle \lvert \nabla \rvert ( 2 \lvert \nabla \phi \rvert - 1 ) ( \lvert \nabla \phi \rvert - 1 ) } & { \displaystyle \lvert \nabla \phi \rvert \leq 1 } \\ { \displaystyle \lvert \nabla \rvert - \frac { 1 } { \lvert \nabla \phi \rvert } ^ { * } \log _ { 1 0 } e } & { \displaystyle \lvert \nabla \phi \rvert \geq 1 } \end{array} \right.
$$

且

$$
\operatorname* { l i m } _ { | \nabla \phi | \to 0 } r = \operatorname* { l i m } _ { | \nabla \phi | \to \infty } r = 1
$$

证明了势函数的扩散速率是有界的。得到一个NDWP的距离正则化项，水平集的演化是一个梯度流，它可以使能量函数最小化；且对水平集函数的梯度模进行约束，避免传统水平集曲线演化中的重新初始化。由图4可得

a)当 $| \nabla \phi | ~ > 1$ ， $r _ { 2 } > r _ { 1 } > 0$ ，曲线正向扩散，越扩散 $| \nabla \phi |$ 越小，曲线运动到 $| \nabla \phi | \substack {  1 }$ ，NDWP需要的迭代次数明显少于DWP模型方法；

b)当 $1 / 2 < | \nabla \phi | < 1$ ， $r _ { 1 } < r _ { 2 } < 0$ ，曲线反向扩散，越扩散 $| \nabla \phi |$ 越大，NDWP模型方法分割效率高于DWP分割方法；

c)当 $\vert \nabla \phi \vert ~ < 1 / 2$ ，曲线正向扩散，越扩散 $| \nabla \phi |$ 越小，曲线演化的的结果是 $\mid \nabla \phi \mid = 0$ ， $\vert \nabla \phi \vert ~ < 1 / 2$ 区域内距模型方法等值线较近，模型扩散速率对曲线演化影响较小；

总之，曲线扩散向着使 $| \nabla \phi | \mathrm { \to } 0$ 或 $| \nabla \phi | \substack {  1 }$ 的方向进行。

![](images/688fedbe02547930cbb992569296b383f164e66d3e95f215af03e651be4f332a.jpg)  
图4双阱势函数及对应扩散速率

Fig.4Double well potential function and corresponding diffusion rate 1.3.2构造AGVF模型

由于DRLSE模型在分割凹陷区域时，容易出现欠分割现象，很难正确分割出目标轮廓。因梯度矢量流[16]能将模型分割曲线演化引向边缘深凹处，为使模型有较好分割效果，在水平集模型中提出用AGVF改变图像的外力场分布。

构造扩散矩阵，定义结构四通道张量 $\textbf {  { J } } ^ { [ 1 7 ] }$ 为

$$
J = { \left[ \begin{array} { l l } { J _ { 1 1 } } & { J _ { 1 2 } } \\ { J _ { 1 2 } } & { J _ { 2 2 } } \end{array} \right] } = \nabla u \nabla u ^ { \mathrm { T } } = { \left[ \begin{array} { l l } { u _ { x } ^ { 2 } } & { u _ { x } u _ { y } } \\ { u _ { x } u _ { y } } & { u _ { y } ^ { 2 } } \end{array} \right] }
$$

对各个通道进行非线性处理：

$$
\frac { \partial J _ { i j } } { \partial t } = \mathrm { d i v } \Bigg ( \varphi \Bigg ( \sum _ { k , l = 1 } ^ { 2 } \boldsymbol { \nabla } J _ { k l } ^ { \mathrm { T } } \ \boldsymbol { \nabla } J _ { k l } \Bigg ) \boldsymbol { \nabla } J _ { i j } \Bigg )
$$

$$
\varphi ( | \nabla u | ^ { 2 } ) = \frac { 1 } { | \nabla u | }
$$

分解非线性结构张量，由于 $J$ 是正定对称阵，利用$( J - \lambda E ) x = 0$ ，其中 $E$ 为单位矩阵， $x$ 是非零向量，得到法线和切线方向对应特征值 $\lambda _ { 1 } , \lambda _ { 2 }$ 。

$$
\left\{ \begin{array} { l } { { \displaystyle \lambda _ { 1 } = \frac { 1 } { 2 } \Big ( J _ { 1 1 } + J _ { 2 2 } + \sqrt { \big ( J _ { 1 1 } + J _ { 2 2 } \big ) ^ { 2 } + 4 J _ { 1 2 } ^ { 2 } } \Big ) } } \\ { { \displaystyle \lambda _ { 2 } = \frac { 1 } { 2 } \Big ( J _ { 1 1 } + J _ { 2 2 } - \sqrt { \big ( J _ { 1 1 } + J _ { 2 2 } \big ) ^ { 2 } + 4 J _ { 1 2 } ^ { 2 } } \Big ) } } \end{array} \right.
$$

再利用 $\lambda _ { 1 } , \lambda _ { 2 }$ ，

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { \big ( J - \lambda _ { 1 } E \big ) \mu _ { 1 } = 0 } \\ { \big ( J - \lambda _ { 2 } E \big ) \mu _ { 2 } = 0 } \end{array} \right. } \end{array}
$$

求相应特征向量 $\mu _ { 1 } , \mu _ { 2 }$

$$
\left\{ \begin{array} { c } { \mu _ { \mathrm { 1 } } { = } \displaystyle { \left[ \frac { \lambda _ { \mathrm { 1 } } - J _ { \mathrm { 1 2 } } - J _ { \mathrm { 2 2 } } } { J _ { \mathrm { 1 1 } } + J _ { \mathrm { 1 2 } } - \lambda _ { \mathrm { 1 } } } , 1 \right] ^ { \mathrm { T } } } } \\ { \mu _ { \mathrm { 2 } } { = } \displaystyle { \left[ 1 , \frac { J _ { \mathrm { 1 1 } } + J _ { \mathrm { 1 2 } } - \lambda _ { \mathrm { 2 } } } { \lambda _ { \mathrm { 2 } } - J _ { \mathrm { 1 2 } } - J _ { \mathrm { 2 2 } } } \right] ^ { \mathrm { T } } } } \end{array} \right.
$$

根据特征值对其进行重新定义，即

$$
\left\{ \begin{array} { l l } { \lambda _ { 1 } ^ { \prime } = C _ { 1 } } \\ { \lambda _ { 2 } ^ { \prime } = \left\{ C _ { 1 } , \lambda _ { 1 } = \lambda _ { 2 } \atop { C _ { 1 } + \left( 1 - C _ { 1 } \right) \exp \left( - C _ { 2 } / \left( \lambda _ { 1 } - \lambda _ { 2 } \right) ^ { 2 } \right) , \lambda _ { 1 } \neq \lambda _ { 2 } } \right. } \end{array} \right.
$$

其中 $C _ { 1 } \in ( 0 , 1 ) , C _ { 2 } > 0$ 常数。定义扩散矩阵为

$$
D = { \lambda _ { 1 } } ^ { \prime } \mu _ { 1 } \mu _ { 1 } ^ { \mathrm { r } } + { \lambda _ { 2 } } ^ { \prime } \mu _ { 2 } \mu _ { 2 } ^ { \mathrm { r } }
$$

则推出各向异性扩散方程为

$$
\frac { \partial \boldsymbol { u } } { \partial t } = d i \nu ( D \nabla \boldsymbol { u } )
$$

同理推出：

$$
\frac { \partial \nu } { \partial t } { = } d i \nu ( D \nabla \nu )
$$

根据图像信息构建AGVF模型，设 $f ( x , y )$ 是左心室内外膜边缘梯度，左心室图像梯度矢量流为$V ( x , y ) = ( u ( x , y ) , \nu ( x , y ) )$ ，对其分量进行处理，得到极小化能量泛函数[18]

$$
\varepsilon = \int \int \mu { \left( { \mu _ { x } ^ { 2 } + \mu _ { y } ^ { 2 } + \nu _ { x } ^ { 2 } + \mu _ { y } ^ { 2 } } \right) } + | \nabla f | ^ { 2 } { \left| { \nu - \nabla f } \right| ^ { 2 } } \ d x d y
$$

其中： $u _ { x } , u _ { y } , \nu _ { x } , \nu _ { y }$ 为 $u , \nu$ 对 $x , y$ 的一阶偏导数； $\mu$ 是由图像噪声控制的参数，与噪声成正比关系。通过求解变分法推出的欧拉方程组，可以得到GVF场：

$$
\begin{array} { c } { { \{ \mu \nabla ^ { 2 } u - ( u - f _ { x } ) ( f _ { x } ^ { 2 } + f _ { y } ^ { 2 } ) = 0 }  }  \\ { {  \mu \nabla ^ { 2 } \nu - ( \nu - f _ { x } ) ( f _ { x } ^ { 2 } + f _ { y } ^ { 2 } ) = 0 } } \end{array}
$$

其中： $\nabla ^ { 2 }$ 是拉普拉斯算子，控制边缘梯度量向周围空间扩散;$\left( u - f _ { x } \right)$ 和 $\left( \nu - f _ { x } \right)$ 保真项，主要为保护图像每点像素梯度值保持原图一致； $\left( f _ { x } ^ { 2 } + f _ { y } ^ { 2 } \right)$ 为保真系数，在分割区域边界处取得最大值。给定一点 $\left( x , y \right)$ ，由欧拉方程组推出能量方程为

$$
\begin{array} { l } { \varepsilon = \displaystyle \iint g \big ( \big | \nabla f \big | \big ) \big ( \mu _ { x } ^ { 2 } + \mu _ { y } ^ { 2 } + \nu _ { x } ^ { 2 } + \mu _ { y } ^ { 2 } \big ) + } \\ { \big ( 1 - g \big ( \big | \nabla f \big | \big ) \big ) \Big ( \big ( \boldsymbol { u } - \boldsymbol { f } _ { x } \big ) ^ { 2 } - \big ( \boldsymbol { u } - \boldsymbol { f } _ { y } \big ) ^ { 2 } \Big ) d x d y } \end{array}
$$

其中： $g \left( \left| \nabla f \right| \right) = \exp \left( - ( \left| \nabla f / K \right) \right)$ ， $K$ 梯度敏感参数。

由GVF 的数值实现[]知，当 $\Delta t \leq \frac { \Delta x \Delta y } { 4 \mu }$ 时，保证GVF能量泛函是收敛的。其中 $\Delta t$ 是时间步长， $\Delta x , \Delta y$ 为空间步长。可以看出，当图像比较粗糙（即 $\Delta x$ 或 $\Delta y$ 较大）和控制参数 $\mu$ 较小时，收敛速度较快。

为了减小 $\Delta x , \Delta y$ 对收敛速度的影响，在GVF模型中引入图像的各向异性，在GVF能量泛函中加入各向异性函数$\ d _ { d i \nu } ( D \nabla u )$ 和 $\boldsymbol { d i \nu } \big ( D \boldsymbol { \nabla } \nu \big )$ ，为更好的收敛到图像边缘凹陷处，添加约束分割区域和边缘的函数 $g \left( x \right)$ 和 $h ( x )$ ，$g ( | \nabla U _ { i }  | ) = \exp ( - ( \mid \Delta U _ { i }  / K ) )$ ， $h ( | \nabla U _ { i } | ) = 1 - g \left( | \nabla U _ { i } | \right)$ ， $\boldsymbol { K }$ 梯度敏感参数， $\boldsymbol { K }$ 值与图像梯度相同处的收敛速度相关， $\kappa$ 值越大，梯度值相同处的收敛速度就越快； $U _ { i }$ 分割区域内第 $i$ 类信息矩阵。得AGVF模型能量泛函：

$$
\begin{array} { l } { \displaystyle { E = \iint _ { \mathbf { \Omega } } \big ( g \big ( | \nabla U _ { i } | \big ) + g \big ( | \nabla f | \big ) \big ) \big ( \mathrm { d i v } \big ( D \nabla u \big ) + \mathrm { d i v } \big ( D \nabla \nu \big ) \big ) } } \\ { \displaystyle ~ + \big ( h | U _ { i } | \big ) + \mu h ( | \nabla f | \big ) \big ( V - \nabla U _ { i } \big ) \mathrm { d } x \mathrm { d } y } \end{array}
$$

由 $\begin{array} { r } { J = \left[ { \boldsymbol { U } } _ { 1 1 } \ { \boldsymbol { U } } _ { 1 2 } \right] } \\ { { \boldsymbol { U } } _ { 1 2 } \ { \boldsymbol { U } } _ { 2 2 } } \end{array}$ （24 根据上述扩散矩阵构造过程推出 $\textit { D }$ 。令$U = U _ { i }$ ，当AGVF能量函数取极小值时，推导出 AGVF模型的计算方法为

$$
\begin{array} { r l } & { \quad \quad \left\lceil \frac { \widehat { \alpha } u } { \widehat { \alpha } t } = ( g \left( | \nabla U | \right) + g \left( | \nabla f | \right) ) ( \operatorname { d i v } ( D \nabla u ) ) - \right. } \\ & { \quad \quad \quad \left. ( h \left( | \nabla U | \right) + \mu h \left( | \nabla f | \right) ) ( u - U _ { x } ) \right. } \\ & { \quad \quad \left\lceil \frac { \widehat { \alpha } \nu } { \widehat { \alpha } t } { = } ( g \left( | \nabla U | \right) + g \left( | \nabla f | \right) ) ( \operatorname { d i v } ( D \nabla \nu ) ) - \right. } \\ & { \quad \quad \quad \left. ( h \left( | \nabla U | \right) + \mu h \left( | \nabla f | \right) ) \left( \nu - U _ { y } \right) \right. } \end{array}
$$

通过以上公式推导，理论上本文提出的AGVF模型处理图像时扑捉范围更大。图5用U型图来验证提出模型的优越性。图5(b)图像原始外立场凹陷处呈水平状态，通过比较，图5(c）GVF外力场改进外力场范围，但没有图5(d）AGVF外立场的凹陷区域收敛性更强，范围更大。对比发现引入

AGVF处理图像，扩大了模型的扑捉范围。

![](images/e138aed3e0d73b56b56ffe3bb09969a6ef782a59c46334ec18bfe9da31a68cbc.jpg)  
图5外力场分布  
Fig.5Distribution of external force field

1.3.3双水平集能量函数

由于单一水平集曲线演化模型分割心室内外膜边缘，需要进行两次分割；且由于心室内外膜边缘像素点对比度不同，同一模型分割内外膜，内外膜会出现边缘泄漏。为提高模型分割效率和模糊边缘分割精度，提出用改进后水平集模型的0水平集和 $\mathbf { k }$ 水平集融合的双水平集模型，同时分割心室内外膜。

双水平集方法的能量函数为

$$
\varepsilon _ { \varepsilon } \left( \phi \right) = \mu R ( \varphi ) + \lambda L ( \varphi ) + \alpha A ( \varphi )
$$

其中： $R ( \varphi )$ 模型距离正则项, $L ( \varphi )$ 是模型边缘约束项， $A ( \varphi )$ 是模型演化速度控制项。 $R ( \varphi )$ 保持双水平集模型演化过程中曲线的正则性； ${ \cal L } ( \varphi )$ 融合AGVF约束0水平集和 $\mathbf { k }$ 水平集朝着内外膜边缘及边缘凹陷处演化； $A ( \varphi )$ 约束模型曲线朝目标边缘速率。定义 $R ( \varphi )$ ， $L ( \varphi )$ ， $A ( \varphi )$ 如下：

$$
R ( \varphi ) = \int _ { \Omega } p ( | \nabla \phi | ) \mathrm { d } x
$$

$$
L ( \varphi ) = \lambda _ { 1 } \intop _ { \Omega } \boldsymbol { g } \delta _ { \varepsilon } \left( \phi \right) \left| \nabla \phi \right| \mathrm { d } x + \lambda _ { 2 } \intop _ { \Omega } \boldsymbol { g } \delta _ { \varepsilon } \left( ( \phi ) - k \right) \left| \nabla \phi \right| \mathrm { d } x
$$

$$
\operatorname { A } ( \phi ) = \alpha _ { 1 } { \underset { \Omega } { \int } } g H _ { \varepsilon } \left( - \phi \right) \operatorname { d } x + \alpha _ { 2 } { \underset { \Omega } { \int } } g H _ { \varepsilon } \left( k - \phi \right) \operatorname { d } x .
$$

且 $\delta$ 和 $H$ 分别为狄拉克函数和赫维赛德函数：

$$
\delta _ { \varepsilon } \left( \chi \right) = \left\{ \begin{array} { l l } { \displaystyle \frac { 1 } { 2 \pi } \Biggl [ 1 + \cos \biggl ( \frac { \pi \chi } { \varepsilon } \biggr ) \Biggr ] , } & { \displaystyle | \chi | \leq \varepsilon } \\ { 0 , } & { \displaystyle | \chi | > \varepsilon . } \end{array} \right.
$$

和

$$
H _ { \varepsilon } \left( \chi \right) = \left\{ \begin{array} { l l } { \displaystyle \frac { 1 } { 2 } \Biggl ( 1 + \frac { \chi } { \pi } + \frac { 1 } { \pi } \sin \Biggl ( \frac { \pi \chi } { \varepsilon } \Biggr ) \Biggr ) , } & { | \chi | \leq \varepsilon } \\ { 1 , } & { \chi > \varepsilon } \\ { 0 , } & { \chi < - \varepsilon } \end{array} \right.
$$

边缘指定符为

$$
g = \frac { 2 } { 6 + | \nabla G _ { \sigma } * I | ^ { 2 } }
$$

$G _ { \sigma }$ 为标准偏差 $\sigma$ 的高斯核函数， $I$ 的定义在整个图像区域。

双水平集模型将水平集演化导出为梯度流，用优化距离正则化项和外部能量来最小化能量泛函，从而驱动零水平集向目标边缘运动。距离正则项约束拓扑水平集演化具有唯一的向后和向前扩散效应，在水平集附近有符号距离分布，它能够维持水平集函数的期望形状，约束模型对模糊边缘的分割。距离正则化消除了传统水平集中需要的重新初始化，简化了运算。选用有限差分法来量化图像梯度，外部能量函数引入AGVF，促使模型完全分割凹陷边界，减少迭代次数的同时保证应有的计算精度。

双水平集模型分割方法主要部分的伪代码如下：获得定位内外膜的初始轮廓像素点数据集；计算出图像像素点到内外膜初始轮廓的欧氏距离；While（双水平集能量泛函取得最小值）%迭代n次{距离正则项函数约束初始轮廓曲线沿法线方向扩散；图像边缘梯度控制曲线演化速度；}

对双水平集模型算法进行复杂度分析。设内外膜初始定位半径为 $R , r$ ，则双水平集获得的初始像素点数共有$l = 2 \pi { \left( R + r \right) }$ ，设图像像素点数为 $m$ ，则计算图像像素点到初始轮廓欧氏距离的时间应为 $\mathrm { T } _ { 1 } = l ( m - l )$ 。进入迭代循环内，曲线演化过程中选用有限差分方式进行表示，$\left( \phi _ { i , j } ^ { n + 1 } - \phi _ { i , j } ^ { n } \right) / \Delta \mathrm { t } = L \left( \phi _ { i , j } ^ { n } \right)$ ，其中 $\Delta t$ 是时间步长， ${ \cal L } \big ( \phi _ { i , j } ^ { n } \big )$ 为曲线第n次演化的像素点集合。曲线每次演化过程中涉及到像素点数为 $\phi _ { i , j } ^ { n }$ ，曲线迭代过程中的时间复杂度 $\mathbf { T } _ { 2 } = \phi _ { i , j } ^ { 1 } + \phi _ { i , j } ^ { 2 } + \cdots \phi _ { i , j } ^ { \mathrm { n } }$ ，由左心室内外膜分割结果推出， $\mathbf { T } _ { 2 } \leq n * \phi _ { i , j } ^ { \mathrm { n } }$ 。因为 $\phi _ { i , j } ^ { \mathrm { n } } \leq m$ ，所以双水平集模型分割的时间复杂度为： $\mathrm { T } ( m ) = { \cal O } ( m )$ 。

水平集方法就是求解一个曲线随时间变化的偏微分方程。而双水平集模型是在三维空间上，找到满足0水平集和k水平集曲线点的集合，即将三维问题利用二维知识解决。所以双水平集的空间复杂度为， $S ( \mathbf { d } ) { = } O \left( d ^ { 2 } \right)$ ， $\textit { d }$ 代表维数。

# 2 实验结果与分析

本文实验数据集采用了鲁昂大学计算机工程与科学MRI心脏影像库[20]和中原大学CT心脏影像库，鲁昂大学数据库包含48人心脏序列，每份包含279张图像，图像大小为 $2 5 6 \times 2 1 6$ ；中原大学数据库包含一心脏的10个振动周期，每个心脏振动周期有387张图像，图像大小 $2 5 6 \times 2 5 6$ 。程序处理过程中，本文采用改进Hough变换圆检测定位和双水平集模型分割方法，实验参数由多次实验所得，设置 $\varepsilon = 1 . 5$ ，$\mu = 0 . 2$ ， $\lambda _ { 1 } = 5$ ， $\alpha _ { 1 } = - 3 . 0$ ， $\lambda _ { 2 } = 6$ ， $\alpha _ { 2 } = - 4 . 0$ 。实验配置处理器为Intel $^ { ( \mathrm { R } ) } _ { } \mathrm { X e o n ( R ) } @ 1 . 6 0 \mathrm { G H z } 1 . 6 0 \mathrm { G H z }$ ，RAM8GB开发软件平台为Windows7，matlab2014a。

# 2.1分割结果

本文分别用CT图像和MRI图像展示分割效果，其中案例一为CT图像分割结果，案例二是MRI图像分割结果。用MRI图像阐述本文方法分割心脏内外膜主要过程。图6中，(a)是左心室原图，(b)是利用改进Hough 变换圆检测定位心室内外膜结果，(c)是利用双水平集模型方法同时分割内外膜效果，(d)是分割效果的三维能量图。

![](images/2623a9392d8fbf7fa619092d2a7112fe67cf1069dd6446c0ea14c56f4391cdcf.jpg)  
图6本文方法分割过程  
Fig.6The segmentation process of this method

为了更好地证明本文算法的精准、高效性，做了多组对比实验，即与经典RSF 模型[2I]、CV 模型、基于区域的主动轮廓模型(Snake)、传统DRLSE模型方法分割左心室内外膜结果进行对比。用图7(a)和图8(a)手动分割结果作为标准。图7(b)和图8(b)是Snake 模型方法分割结果;图7(c)和图8(c)是DRLSE 模型方法分割结果；图8(d)是RSF模型分割方法结果；图8(e)是CV模型方法分割结果。

![](images/e50488e21da39f89dc7c7a557c0a6924a895bcd95dcde9529bbe0f43c892a858.jpg)

![](images/f9783c4afb39f46ff458ff69245cc46f697338de8a2c82e39dc56ed409acec94.jpg)  
图8案例2分割结果  
Fig.8Segmentation results of case two

# 2.2实验结果分析

为定量分析模型分割左心室内外膜效果，引入重叠率（Dice）和误分割率（ $M E$ ）[22]量化分析实验结果，客观对比各模型方法分割效果；

$$
D i c e = \frac { 2 \times | F _ { \mathrm { M a n u a l } } | \bigcap F _ { \mathrm { A u t o } } | } { | F _ { \mathrm { M a n u a l } } | + | F _ { \mathrm { A u t o } } | }
$$

$$
M E = 1 - \frac { |  B _ { \mathrm { M a u n a l } } \cap B _ { \mathrm { A u t o } }  | + | \mathrm { F _ { M a u n a l } } + F _ { \mathrm { A u t o } }  | } { |  B _ { \mathrm { M a u n a l } }  | + | \mathrm { F _ { M a u n a l } } | }
$$

其中： $F _ { \mathrm { M a u n a l } }$ 和 $B _ { \mathrm { M a u n a l } }$ 是专家手动分割左心室外膜的目标区域和背景的像素集， $F _ { \mathrm { A u t o } }$ 和 $B _ { \mathrm { A u t o } }$ 是用方法分割左心室外膜的目标区域和背景的像素集，||集合基数表示某一集合所属的类。

直接从视觉角度分析图7案例1。基于区域的Snake 模型方法分割对比明显边界时，分割效果良好，分割模糊边界误差较大；模糊边缘需要人工二次分割校正，图7(b）较粗蓝线为手动校正二次分割位置；虽然 Li引入势能函数解决传统水平集模型演化过程中反复初始化问题，但模型对初始位置比较敏感且仍需要手动设置，分割弱边缘凹陷处时，易出现欠分割现象；文献[21]方法在模糊边缘处出现过分割现象;本文方法分割边缘为类圆形符合左心室外膜临床定义，没有边缘泄露现象。

表1不同方法分割左心室  
Table1Segmentation of left ventricle by different methods   

<html><body><table><tr><td>算法</td><td>程序运行时间</td><td>Dice</td><td>ME</td></tr><tr><td rowspan="4">Snake 模型半自动分割</td><td>40.0521</td><td>0.9478</td><td>0.0261</td></tr><tr><td>40.0364</td><td>0.9513</td><td>0.0379</td></tr><tr><td>39.2635</td><td>0.9486</td><td>0.0279</td></tr><tr><td>39.2973</td><td>0.9457</td><td>0.0158</td></tr><tr><td rowspan="4">DRLSE 模型</td><td>20.7844</td><td>0.9001</td><td>0.0261</td></tr><tr><td>30.4342</td><td>0.8933</td><td>0.0249</td></tr><tr><td>26.2163</td><td>0.9054</td><td>0.0308</td></tr><tr><td>27.8563</td><td>0.9038</td><td>0.0302</td></tr><tr><td rowspan="4">文献[21]</td><td>33.1733</td><td>0.9175</td><td>0.0348</td></tr><tr><td>32.6621</td><td>0.9235</td><td>0.0441</td></tr><tr><td>31.2753</td><td>0.9246</td><td>0.0371</td></tr><tr><td>31.2315</td><td>0.9241</td><td>0.0361</td></tr><tr><td rowspan="4">本文方法</td><td>15.2223</td><td>0.9337</td><td>0.0198</td></tr><tr><td>17.6135</td><td>0.9334</td><td>0.0201</td></tr><tr><td>14.8946</td><td>0.9355</td><td>0.0168</td></tr><tr><td>15.6873</td><td>0.9362</td><td>0.0173</td></tr></table></body></html>

结合表1案例一数据，本文提出方法用二维平面解决三维空间问题，虽然模型空间复杂度与DRLSE 模型和文献[21]模型仍属于同一数量级，但在分割时间上明显少于DRLSE模型和文献[21]的分割时间，大幅度提高了分割效率；在分割精度方面，Snake模型半自动手动二次校正分割，分割结果Dice平均才只有0.9484，ME平均为0.0269；DRLSE 模型方法分割结果Dice平均为0.9006，ME平均为0.0280；文献[21]分割结果结果Dice平均为0.9224，ME平均为0.0380；本文方法分割结果Dice平均为0.9347，接近与半自动手动方法分割结果，且均高于需要手动设置初始位置的文献[21]方法和DRLSE方法的分割结果；ME平均为0.0185，得到了最低的误分割率。本文方法避免分割过程人为干预，解决了人为因素的客观影响，降低了模型对轮廓初始位置的要求，得到正则性良好内外膜，提高了心室内外膜模糊边缘和凹陷区域的分割精度。

表2案例2分割结果对比  
Table 2 Compared segmentation results of case two   

<html><body><table><tr><td>方法模型</td><td>Dice</td></tr><tr><td>Snake 模型</td><td>0.9244</td></tr><tr><td>DRLSE 模型</td><td>0.9438</td></tr><tr><td>RSF模型</td><td>0.9298</td></tr><tr><td>CV模型</td><td>0.9125</td></tr><tr><td>本文方法</td><td>0.9569</td></tr></table></body></html>

其次，为验证本文算法具有良好的分割效果，分割MRI图像时，加入了基于边缘分割的RSF模型方法和基于区域的CV模型方法作对比。RSF模型方法分割边缘时，模糊边缘约束条件较弱，出现边缘过分割现象；CV模型方法分割模糊区域时，出现多个拓扑结构，边缘发生泄漏。由图8直接从视觉角度就能看出RSF、CV、Snake、DRLSE 模型方法分割左心室外膜时，图像像素间对比度明显区域效果良好，但在心室膜没有明确界定处，分割所得边缘正则性差，甚至在弱边缘处出现边缘泄露现象。对比图8(f)本文算法分割的左心室外膜结果，本文算法由于引入AGVF，在边缘凹陷区域也能进行充分分割，新双阱势函数NDWP的提出，使距离正则项能够更好的约束边缘正则性，得到符合临床定义的平滑类圆形轮廓；比较表2多种模型方法分割左心室，得到的Dice数据，发现本文提出方法分割左心室内外膜Dice高至0.9565，得到了高精度的左心室内外膜轮廓。

通过上述分析，本文算法虽然空间复杂度任和水平集模型是同一数量级，但在分割时间上，由于是对内外膜进行同时分割，耗时仅约为单水平集分割的一半，自动初始定位，降低了模型对初始位置的敏感性，自动分割左心室内外膜，提高了心室内外膜弱边缘处和凹陷区域的分割精度，避免了人工分割的主观性影响。图7和8证实本文算法无论分割CT心室图像还是MRI心室图像，都能有效的完成左心室内外膜的自动分割。

# 3 结束语

本文提出基于双水平集模型的左心室内外膜的分割方法，利用NDWP提高模型分割左心室膜的演化速度，平滑模糊边缘分割轮廓；用加入AGVF的外部能量函数驱动曲线引向凹陷区域边缘，自动分割左心室内外膜。根据心脏左心室医学影像的特点对图像进行定位，利用改进Hough变换检测到的圆形，作为双水平集模型的初始轮廓，通过双水平集模型分割得到左心室内外膜轮廓。与Snake 模型算法、RSF模型算法和CV模型算法的分割结果相比，本文算法无论分割CT图像还是MRI图像，保证分割的内外膜边缘的正则性，均提高了内外膜的分割精度和分割效率，避免了初始轮廓的人为设置，实现了左心室外膜的自动化分割。然而，观察分割过程发现，内膜边缘像素间对比明显，应充分利用局部信息优化内膜分割。接下来工作针对模型不足进行优化，提高本文方法分割精度，构建左心室三维模型。

# 参考文献：

[1]吕福起，李霄民．基于粒子群优化算法和模糊熵的多级阈值图像分 割算法[J/OL].计算机应用研究，2019，36(10）.(2018-06-19). http://www.arocmag.com/article/02-2019-10-045.html. (Lu Fuqi,Li Xiaomin.Multilevel threshold image segmentation algorithm based on particle swarm optimization and fuzzy entropy [J/OL].Computer Application Research，2019，36(10)．(2018-06-19)．http://www. arocmag.com/article/02-2019-10-045.html.)

[]DIan A, Goyal A,Duua M Λ,el ul. age-Daseu pixel ciusterg anu connected component labeling in left ventricle segmentation of cardiac MR images [C]//Proc ofInternational Congress on Ultra Modern TelecommunicationsandControlSystemsandWorkshops. Piscataway,NJ:IEEE Press,2016: 339-342.   
[3] 陆剑锋，林海，潘志庚．自适应区域生长算法在医学图像分割中的 应用[J].计算机辅助设计与图形学学报,2005,17(10):2168-2173. (Lu Jianfeng,Lin Hai,Pan Zhigeng.Application of adaptive region growing algorithm in medical image segmentation [J]. Journal of Computer Aided Design and Graphics,2005,17 (10): 2168-2173.)   
[4]Wang Chengjie.Research on snake model-based image segmentation [J].Intelligent Computer & Applications,2013,3 (2): 82-85   
[5]Liu Yu,Li Chunming,Guo Shuxu,et al.A novel level set method for segmentation of left and right ventricles from cardiac MR images [C]//Proc of the 36th Annual International Conference of the IEEE Engineering in Medicine and Biology Society.2014:4719-4722.   
[6] 徐胜舟，许向阳，胡怀飞，等．基于改进动态规划的MR图像左心室 分割[J]．广西师范大学学报：自然科学版，2014,32(2):35-41.(Xu Shengzhou，Xu Xiangyang，Hu Huaifei,et al.Left ventricle segmentation of MR images based on improved dynamic programming [J].Journal of Guangxi Normal University:Natural Science Edition, 2014,32(2): 35-41.)   
[7]Lee H Y,Codella N C,Cham M D,et al.Automatic left ventricle segmentation using iterative thresholding and an active contour model with adaptation on short-axis cardiac MRI.[J]．IEEE Trans on Bio-Medical Engineering,2010,57 (4): 905-13.   
[8] 李晓宁，厉元杰，幸浩洋，等．一种带心肌瘢痕的心脏磁共振图像左 室壁分割方法[J]．四川大学学报：自然科学版，2016,53(5): 1011-1017.(Li Xiaoning,Li Yuanjie,Hao Yang Xing,et al.A left ventricular wall segmentation method for cardiac magnetic resonance imaging with myocardial scar[J]. Journal of Sichuan University: Natural Science Edition,2016,53(5):1011-1017.)   
[9]朱锴，付忠良，朱硕．基于自适应均值漂移的超声心动图左心室分 割方法[J].生物医学工程学杂志，2018(2):273-279.(Zhu Kai，Fu Zhongliang,Zhu Shuo.Echocardiographic left ventricular segmentation based on adaptive mean shift [J]. Journal of Biomedical Enginering, 2018 (2):273-279.)   
[10] Dharanibai G, Chandrasekharan A,Alex Z C.Automated Segmentation of Left Ventricle Using Local and Global Intensity Based Active Contour and Dynamic Programming [J]. International Journal of Automation & Computing,2017 (2): 1-16.   
[11]王兴家，董利娜，李传富，等．用改进的耦合水平集方法从MSCT中 分割左心室[J]．中国生物医学工程学报，2011，30(4):494-499. (Wang Xingjia,Dong Lina,Li Chuanfu,et al. Segmentation of left ventricle from MSCT by improved coupled level set method [J]. Chinese Journal ot Biomedical Engineering,201l,30 (4): 494-499.)   
[12]孔媛媛，李军华，王艳，等．基于 Hough 变换和GVFSnake 模型的 脑肿瘤分割方法 [J].2018,35(11):3469-3471,3475.(Kong Yuanyuan, Li Junhua,Wang Yan,et al. Segmentation method of brain tumor based on Hough transform and GVFSnake model [J].2018，35 (12): 3469-3471,3475.)   
[13] Chen Xing,Lu Ling,Gao Yang.A new concentric circle detection method based on Hough transform [C]//Proc ofInternational Conference on Computer Science & Education.IEEE,2012:753-758   
[14] Li Chunming,Huang Rui, Ding Zhaohua,et al,A level set method for image segmentation in the presence of intensity inhomogeneities with application to MRI [J]. IEEE Trans on Image Processing,2011,20(7): 2007-2016.   
[15] Li Chunming，Xu Chengyang，Gui Chengfeng，et al.Distance regularized level set evolution and itsapplication toimage segmentation [J].IEEE Trans on Image Processing，2O1O,19 (12): 3243-3254   
[16] Shivakumara P,Phan T Q,Lu S,et al.Gradient vector flow and grouping-based method for arbitrarily oriented scene text detection in video images [J].IEEE Trans on Circuits & Systems for Video Technology,2013,23(10):1729-1739   
[17]王利，陈允杰，汤杨，等．相关扩散方程在图像修补中的应用[J]. 中国图象图形学报,2009,14(1):71-76.(Wang Li,Chen Yunjie,Tang Yang，et al.Application of correlation diffusion equation in image repairing [J]. Chinese Journal of Image Graphics,2009,14 (1): 71-76)   
[18]王宇，张建伟，陈允杰，等．一种新的基于各向异性扩散的GVF 模 型[J].计算机工程,2010,36(4):215-217.(Wang Yu,Zhang Jianwei, Chen Yunjie,et al.A new GVF model based on anisotropic diffusion [J]. Computer Engineering,2010,36 (4): 215-217.)   
[19]付永清，张宪民．基于梯度矢量流的柔顺机构拓扑图轮廓提取方法 [J]．组合机床与自动化加工技术，2017(7):55-59.(Fu Yongqing, Zhang Xianmin. Contour extraction method of topological diagram of compliant mechanism based on gradient vector flow[J]. Modular machine tool and automatic machining technology,2017(7):55-59.)   
[20] Projet R V Segmentation Challenge in cardiac MRI[EB/OL]. 2017.http://www.litislab.fr/?sub_project=how-to-download-the-data.   
[21]程兆宁，宋志坚.RSF 模型的优化及其在MRI脑肿瘤分割中的应用 [J]．生物医学工程学杂志，2013(2):55-61.(Cheng Zhaoning，Song Zhijian.Optimization of RSF model and its application in MRI brain tumor segmentation [J]. Journal of Biomedical Engineering,2013(2): 55-61.)   
[22] Mehmet Sezgin，Byulent Sankur. Survey over image thresholding techniques and quantitative performance evaluation [J].Journal of Electronic Imaging,2004,13(1): 146-168.