# 基础研究

# 基于动力学聚类与 $\pmb { \alpha }$ 散度测度的动态心肌PET图像因子分析

王沛沛,路利军，曹双亮，李华勇，陈武凡南方医科大学生物医学工程学院//广东省医学图像处理重点实验室,广东广州 510515摘要：目的建立一种基于动力学聚类与α散度测度的因子分析方法，分析从动态心肌PET图像中无创地提取血输入函数及局部组织的时间活度曲线。方法 通过最小化动态图像与因子模型间的α散度将动态PET图像做初步的分解，得到初始因子与因子图像，然后联合PET像素动力学聚类的先验信息解决因子分析模型中解的非唯一性问题，将初始因子与因子图像通过空间变换生成具有生理意义的组织活度曲线及组织空间分布。结果与传统的最小二乘法测度和最小化因子图像间重叠程度约束模型相比,本模型对噪声的敏感性较低,提取出的结果的精确性较高。结论通过选取最优的α值作为因子分析模型的测度，并引入PET图像像素的动力学聚类信息，能精确地获得血输入函数及局部组织的时间活度曲线，在视觉评价及量化评价均具有优质表现。

关键词：因子分析； $\alpha$ 散度；正电子发射计算机断层显像；动力学聚类

# Kinetic cluster and $\alpha$ -divergence-based dynamic myocardial factorial analysis of positron emission computed tomography images

WANG Peipei,LULijun,CAO Shuangliang,LI Huayong, CHENWufan   
GuangdonProncialKeyLboratoryofedicalImageProcessngScholofomdicalEngineeringSoutheedicaliy   
Guangzhou 510515,China

Abstract: Objective We purpose a novel factor analysis method based on kinetic cluster and $\alpha$ -divergence measure for extracting the blood input function and the time-activity curve of the regionaltisue from dynamic myocardial positron emission computed tomography(PET) images. Methods Dynamic PETimages were decomposed into initial factors and factor images by minimizing the $\alpha$ divergence between the factor model and actual image data. The kinetic clustering as a priori constraint was thenincorporated intothe model tosolvethenonuniquenessproblem,andthe tisue time-activitycurvesand thetisue space distributions withphysiological significance were generated.Results The model was aplied tothe RbPET myocardial perfusion simulationdataandcompared with the traditional model-based leastsquares measureand theminimal spatialoverlapconstraint.The experimentalresults showed that the proposed model performed beter thanthe traditional model in terms of both accuracy and sensitivity. Conclusion This method can select the optimal measure by $\alpha$ value, and incorporate theprior informationof theKineticclusteringofPETimagepixels toobtaintheacuratetime-activitycurves of the tissue, which has shown good performance in visual evaluation and quantitative evaluation.

Keywords: factor analysis; $\alpha$ -divergence; positron emission computed tomography; kinetic cluster

无创测定局部心肌血流量(RMBF)一直是临床心脏学所追求的目标之一[1-3]。通过从动态图像中估计血输入函数与输出函数[45],并应用动力学模型，可以得到绝对的定量参数(如物质转运速率、代谢速度和受体结合率等功能参数等)，从而实现对心肌血流的定量分析[6-8]。在动力学模型的应用中,血输入函数的估计是非常关键的，结果的准确与否直接影响到后期的定量分析，目前广泛采用的估计血输入函数方法为基于感兴趣区域法，该方法简单易行，但极度依赖于医生手工勾画的感兴趣区域，而感兴趣区域的准确性又受医生个人经验及部分容积效应影响。因子分析作为从变量群中提取公共因子的统计技术，已经被用来从动态图像中无创地提取血输入函数和组织的时间活度曲线[10-11],如基于主成分分析[12-15]、独立成分分析[16-17]、最小二乘法[6,15]最大似然法[18的因子分析模型相继被提出。然而，用因子分析方法获得的结果存在非唯一性，各种基于先验信息的方法被提出用来解决结果的非唯一性[18-20],另外,Sitek等[9提出基于最小化各因子图像间的重叠程度的优化方法可以获得唯一的结果。

合理地构建因子模型与实际数据之间的测度是精确建模的关键，目前在因子分析模型中常见的是基于高斯噪声模型的最小二乘测度与基于泊松噪声模型的最大似然测度[6.18.21]。而临床获取动态PET图像噪声很难直接用高斯或泊松模型进行刻画，因此,本文提出基于 $\alpha$ 散度的因子分模型， $\alpha$ 散度由S.Amari提出，是诸多信息散度族中的一种，通过选取不同的 $\overset { \cdot } { \alpha }$ 值，可以用于任意噪声模型的数据测度[22-23]。

针对因子分析模型中解的非唯一性，传统上利用最小化因子图像间的重叠程度这一约束来解决该问题，但由于受到PET图像分辨率和部分容积效应的影响，心肌信号经常会掺杂着 $1 0 \% { \sim } 1 5 \%$ 的血液信号，基于最小化因子图像之间的重叠程度的约束未能考虑到这一事实。在动态PET研究中，每一个像素的时间行为可以通过曲线时间活力(TAC)来描述，我们将具有相同时间行为的像素进行聚类24，把这一聚类结果作为先验约束用来解决因子分析模型中的非唯一性，得到具有生理意义的组织活度曲线。因子分析模型应用于基于XCAT(Extended Cardiac-Torso phantom)体模[25仿真的 $^ { 8 2 } \mathrm { R b }$ PET心肌灌注仿真数据中，实验均表明我们的方法在视觉评价及量化评价等方面优于传统的因子分析模型

# 1方法

# 1.1PET图像的获取

对于动态序列PET图像I,像素点j在第 $m$ 帧的示踪剂活度 $x _ { j m }$ 可通过以下积分式计算得到[26]：

$$
\boldsymbol { x } _ { j m } = \int _ { t _ { m , s } } ^ { t _ { m , e } } \boldsymbol { c } \big ( j , t \big ) e ^ { - \lambda \tau } \mathrm { d } t
$$

其中， $c ( j , t )$ 表示像素点在时间点 $t$ 的示踪剂活度， $t _ { m , s }$ 和 $t _ { m , e }$ 分别表示第 $\mathrm { m }$ 帧的起始时间和终止时间。那么

$$
I = \left( \begin{array} { c c c c } { { x _ { 1 1 } } } & { { x _ { 1 2 } } } & { { \cdots } } & { { x _ { 1 n _ { m } } } } \\ { { x _ { 2 1 } } } & { { x _ { 2 2 } } } & { { \cdots } } & { { x _ { 2 n _ { m } } } } \\ { { \vdots } } & { { \vdots } } & { { \ddots } } & { { \vdots } } \\ { { x _ { n _ { j 1 } } } } & { { x _ { n _ { j 2 } } } } & { { \cdots } } & { { x _ { n _ { j } n _ { m } } } } \end{array} \right)
$$

其中 $\boldsymbol { I } { \in } \boldsymbol { R } ^ { n _ { j } \times n _ { m } }$ . $I$ 的一列表示一帧图像， $I$ 的一行表示单个像素点的时间活度曲线。

动态PET序列图像可分解为有限的时间序列向量F和与其相对应体素的空间分布 $C _ { i }$ ,这一分解模型可用下式来表示

$$
I { = } C F { + } \varepsilon
$$

其中动态PET图像 $I$ 的大小为 $N { \times } T ,$ 其中 $N$ 表示每一帧PET图像的像素点数目， $T$ 表示动态图像的帧数。因子矩阵F的大小为 $K { \times } T _ { ; }$ ，因子图像 $C$ 的大小为 $N { \times } K$ 其中 $K$ 为所需提取的因子数目。表示剩余信号，即图像的噪声和被模型所忽略的小部分信号。在这里，为保证模型的实际应用价值，因子数目 $K$ 要满足 $K < < N , K < < T _ { \circ }$

图1表示对动态序列PET图像做因子分析的示意图，在理想状况下，因子矩阵 $F$ 对应于动态图像中各个生理组织的时间活度曲线，因子图像 $C$ 对应于各个生理组织的空间分布。

8 6 ×105 Blood -Myocardium 5 rTlr) it 4 X 3 2 0L 0 20 40 60 80 100 120 Time (s)   
Dynamic sequence Factor images Factors

# 1.2 提出的因子分析模型

因子分析模型的求解主要由两个步骤来完成：(1)通过最小化模型与真实图像之间的测度来分解图像，得到初始的因子与因子图像。2)解决模型中的非唯一问题。

我们通过 $\overset { \cdot } { \alpha }$ 散度来测定图像I与模型CF之间的偏差， $\boldsymbol { a }$ 散度由S.Amari提出，是诸多信息散度族中的一种，用于测量两个数据分布 $p ( x )$ 和 $q ( x )$ 之间的偏差，其定义为：

$$
D _ { \alpha } ( p , q ) = { \frac { 1 } { \alpha ( 1 - \alpha ) } } { \sum _ { i } \left( { \alpha p _ { i } + ( 1 - \alpha ) q _ { i } - p _ { i } ^ { ~ \alpha } q _ { i } ^ { ~ 1 - \alpha } } \right) } , \alpha \in R
$$

结合信息散度的特点，本文提出最小化基于 $\overset { \cdot } { \alpha }$ 散度测度的目标函数来估计因子 $F$ 与因子图像 $C$

$$
f _ { \alpha } ( { \cal C } , { \cal F } ) = \frac { 1 } { \alpha ( 1 - \alpha ) } { \sum _ { i } \sum _ { f } } { \binom { \alpha I _ { i f } + ( 1 - \alpha ) ( { \cal C } { \cal F } ) _ { i f } } { - { I _ { i f } } ^ { \alpha } ( { \cal C } { \cal F } ) _ { i f } ^ { \ 1 - \alpha } } } , \alpha \in { \cal R }
$$

基于 $\scriptstyle { a }$ 散度的动态PET图像的因子分析模型可表示为以下凸优化问题：

$$
( C , F ) { = } \underset { C _ { i k } \geq 0 , F _ { k f } \geq 0 } { \arg \operatorname* { m i n } } f _ { \alpha } ( C , F )
$$

我们采用一种迭代的方式去解决上式，具体算法如下：

i.初始化 $\scriptstyle { C , F }$ ：设置C中元素为0-1之间的随机数， 再根据 $C$ 估计初始 $F$

ii.迭代：

(a)C-step:根据当前的动态图像 $I$ 和 $F$ 估计 $C$   
(b)将C中的小于零的元素置为0:;  
(c)F-step:根据当前的动态图像I和 $C$ 估计 $F$ (d)将 $F$ 中的小于零的元素置为0：;  
(e)检查是否收敛,若不收敛,则返回步骤 $a$   
iii.归一化因子图像 $C$ ，再根据缩放的比例缩放 $F$   
其中,在C-step中,令 $\frac { \partial f _ { a } ( C , F ) } { \partial C _ { i k } } = 0$ 得到  
$C _ { m + 1 } ^ { \alpha } = \frac { C _ { m } ^ { \alpha } { \displaystyle \sum _ { i , f } } F _ { k f } \Biggl ( \frac { I _ { i f } } { ( F C _ { m } ) _ { i f } } \Biggr ) ^ { \alpha } } { \displaystyle \sum _ { f } F _ { k f } } ~ ;$   
在F-step中,令 $\frac { \partial f _ { \alpha } ( C , F ) } { \partial { F _ { k f } } } = 0$ ,得到  
$F _ { _ { m + 1 } } ^ { \alpha } = \frac { F _ { _ m } ^ { \alpha } { \displaystyle \sum _ { i , f } } C _ { i k } \Biggl ( \frac { I _ { i f } } { ( C F _ { _ m } ) _ { i f } } \Biggr ) ^ { \alpha } } { \displaystyle \sum _ { i } C _ { i k } }$

1.3 唯一性约束

容易发现，式1描述的因子模型的结果在数学上并不是唯一的2，因子和因子图像的非唯一性可以通过下式说明

$$
I { = } ( C R ) ( R ^ { - 1 } F ) { = } C ^ { \prime } F ^ { \prime }
$$

其中， $C$ 和 $F$ 表示真实的因子图像矩阵和因子矩阵，通过一个可逆的矩阵 $R$ ，理论上能得到无数组符合模型描述的因子图像 $C$ 和 $F$ 。因此，我们必须找到合理的约束条件确保结果的唯一性。

A.传统方法：最小化因子图像之间的重叠程度约束

sitek.A假设因子图像之间的重叠程度最小(MSO,minimalstructureoverlap)的作为唯一性约束条件，因子间重叠程度的计算公式为

$$
f _ { u n i } \big ( R \big ) = \sum _ { p = 1 } ^ { P } \sum _ { q = p + 1 } ^ { P } \sum _ { i = 1 } ^ { N } \frac { \big | C R \big | _ { i p } } { \sqrt { \sum _ { i = 1 } ^ { N } ( C R ) _ { i p } ^ { 2 } } } \frac { \big | C R \big | _ { i q } } { \sqrt { \sum _ { i = 1 } ^ { N } ( C R ) _ { i q } ^ { 2 } } }
$$

惩罚项 $f _ { n } ( C R , R ^ { \cdot I } F )$ 保证因子和因子图像的值为非负，可用下式表示：

$$
f _ { n } ( \boldsymbol { R } ) = \sum _ { i = 1 } ^ { N } \sum _ { k = 1 } ^ { K } H \bigl ( ( \boldsymbol { C } \boldsymbol { R } ) _ { i k } \bigr ) + \sum _ { f = 1 } ^ { T } \sum _ { k = 1 } ^ { K } H \bigl ( ( \boldsymbol { R } ^ { - 1 } \boldsymbol { F } ) _ { k f } \bigr ) ,
$$

其中 $H ( x ) = \left\{ 0 \ , \quad x \ge 0 \right.$

最小化目标函数 $( f _ { u n i } { + } b _ { I } f _ { n } )$ ，求得 $R$ 的最优解，并获得最终的因子图像 $( C R )$ 和代表每个组织活度曲线 $\left( { \cal R } ^ { \prime } { \cal F } \right)$ 的具有实际生理意义的因子。

B.新方法：基于动力学聚类的约束

由于受到PET图像分辨率和部分容积效应的影响，心肌信号经常会掺杂着 $10 \% { \sim } 1 5 \%$ 的血液信号，最小化因子图像之间的重叠程度约束未能考虑到这一事实。因此，本文提出一种基于动力学的时间活度曲线聚类(KB,KineticBased)的先验约束来解决因子分析模型中的非唯一问题。

在动态PET研究中，每一个像素的时间行为可以通过TAC曲线来描述，因此，我们基于像素的动力学对图像进行分类。我们的目标是通过动态序列图像的TAC曲线的形状和级数对图像进行分类，使得像素TAC在同一类是同质的，而不同类之间是异质的。假设动态图像 $I$ 具有 $K$ 个不同特征的类，模糊 $C$ 均值聚类算法基于最小化目标函数

$$
J = \sum _ { j = 1 } ^ { n _ { j } } { \sum _ { k = 1 } ^ { K } { u _ { k j } ^ { q } \Big | \Big | I _ { j } - \nu _ { k } \Big | \Big | ^ { 2 } } }
$$

其中 $\| \cdot \|$ 代表欧氏距离 $J _ { j }$ 表示图像I中第j个像素的TAC曲线, $\nu _ { k }$ 是第 $k$ 个聚类的中心的TAC， $u _ { k j }$ 表示第j个像素属于第 $k$ 类的隶属度， $q ( q { > } 1 )$ 是模糊参数。

目标函数的解可以通过如下迭代式得到：

i.设置初始的类数 $K$ 和停止准则ε;

ii.随机初始化模糊隶属度矩阵 $U ^ { ( 0 ) }$ 包含每一个单独${ u _ { k j } } ^ { ( 0 ) }$ 值；

ii.设置循环初始值 $b { = } 0$

iv.由 $U ^ { ( b ) }$ 计算聚类中心 $\nu _ { k } ^ { ( b ) }$

$$
\nu _ { k } ^ { ( b ) } = \frac { \displaystyle \sum _ { j } ( u _ { k j } ^ { ( b ) } ) ^ { q } I _ { j } } { \displaystyle \sum _ { j } ( u _ { k j } ^ { ( b ) } ) ^ { q } }
$$

v.计算隶属度矩阵 ${ U } ^ { ( b + l ) }$

$$
u _ { k j } ^ { ( b + 1 ) } = 1 / \sum _ { i = 1 } ^ { K } \left( \frac { \left. I _ { j } - \nu _ { k } \right. _ { w } ^ { 2 } } { \left. I _ { j } - \nu _ { i } \right. _ { w } ^ { 2 } } \right) ^ { 1 / ( q - 1 ) }
$$

vi.如果 $\operatorname* { m a x } \Big \{ U ^ { ( b ) } - U ^ { ( b + 1 ) } \Big \} < \varepsilon$ 则停止;否则,设 $b = b +$ 1返回第 $i \nu$ 步。

将聚类中心 $\nu _ { k }$ 通过式(11)作为像素动力学先验信息应用到因子分析唯一性约束当中，

$$
f _ { _ { T A C } } ( \boldsymbol { R } ) = \sum _ { k = 1 } ^ { K } \Bigl \| ( \boldsymbol { R } ^ { - 1 } \boldsymbol { F } ) _ { k } - \boldsymbol { \nu } _ { k } \Bigr \| _ { 1 }
$$

通过最小化目标函数 $( f _ { \mathit { T A C } } + b _ { \mathit { 2 } } f _ { n } )$ 来解决因子分析中的非唯一问题，求得 $R$ 的最优解，最终获得因子图像(CR)和代表每个组织活度曲线 $( R ^ { \prime } F )$ 的具有实际生理意义的因子。

# 2实验

# (1)计算机仿真数据

在计算机仿真实验中，本文使用基于如图2所示的XCAT数字体膜，心脏区域由血池，心肌组织两个部分构成,在这里将心脏区域单独分离出来。模型的体素点个数为 $6 4 \times 6 4 \times 3 0$ ，体素点尺寸大小为 $3 . 2 7 ~ \mathrm { m m } { \times } 3 . 2 7 ~ \mathrm { m m } { \times }$ $3 . 2 7 \mathrm { m m }$ 。我们基于单房室模型28模拟心脏区域生理代谢的功能成像过程，使用的放射性核素为 $^ { 8 2 } \mathrm { R b }$ ，半衰期为 $1 . 2 7 \mathrm { m i n } _ { \odot }$ ，仿真过程中，血输入函数以及各组织对应的动力学参数的测量值均来自美国约翰霍普金斯大学PET医学中心的5位志愿者[26]。基于单房室模型、血输入函数以及相应的动力学参数(设置动力学参数 $K _ { l } =$ $1 . 4 8 2 2 ~ \mathrm { m L / m i n / g } , \mathrm { k } _ { 2 } { = } 0 . 3 1 5 9 / \mathrm { m i n }$ 及血体积分数为 $\begin{array} { r } { V _ { p } = } \end{array}$ 0.3829)生成心肌组织的时间活度曲线，各组织时间活度曲线及空间分布如图3所示。整个动态PET扫描协议设置为： $1 2 \times 5 \ \mathrm { s } , 6 \times 1 0 \$ s共计18个时间帧。将每一帧血池与心肌组织的时间活度赋值到其对应组织的空间分布位置上，生成模拟心脏区域的动态PET图像。

将动态图像进行正向投影得到随时间变化的无噪投影数据。投影数据仿真过程中产生的总光子计数设置为 $5 \times 1 0 ^ { 6 }$ 。在投影数据中加入泊松噪声便可得到仿真的加噪投影数据。本文采用FBP重建算法对加噪的投影数据进行重建。得到重建图像之后，用 $\mathrm { F W H M = } 4 ~ \mathrm { m m }$ 的高斯滤波器对重建出的动态图像进行去噪。本研究仿真实验均基于该仿真数据。

![](images/a417edf75edfcd7b252f195fd6c2e32a0d2000d852f51edca65eed2c53df5bd9.jpg)  
图2 (A)4DXCAT数字体膜的正位像(左：男性，右：女性)及(B)女性心脏区域水平切片 Fig.2Anterior views of the 4D XCAT digital phantom(A;left:male,right: female)and the female horizontal plane of myocardial region (B).

![](images/b6e40dc1fabe42474b8380e29bdb95217653d67aa41c75051bac233727f672db.jpg)  
图3血池与心肌组织的时间活度曲线及空间分布位置(横截面第14层)Fig.3Time-activity curve and spatial distribution position of blood pool andmyocardial tissue (14th slice of the horizontal plane).

(2)对照方法及评价指标

在模型的求解中的第一步中，引入了 $\alpha$ 散度作为测度量化模型与真值图像之间的距离，我们将其与传统的最小二乘测度进行比较。本文采用归一化误差 $\cdot \delta _ { \scriptscriptstyle I }$ 评价不同测度在每一帧的剩余信号 $\mathbf { \hat { \boldsymbol { \varepsilon } } } _ { \varepsilon }$ ，用归一化误差 $\delta _ { 2 }$ 评价不同测度评价所有帧的剩余信号：。

$$
R M S E = \frac { \displaystyle \sum _ { f } W \cdot \big | n o r m ( F ) - n o r m ( F _ { \mathit { r e f } } ) \big | } { \displaystyle \sum _ { f } W \cdot n o r m ( F _ { \mathit { r e f } } ) } \times 1 0 0 \%
$$

其中F代表因子曲线， $F _ { r e f }$ 代表各组织的活度曲线。W代表每一帧的时间间隔， $n o r m ( F )$ 代表将 $F$ 进行归一化,即 $n o r m ( F ) = \frac { F } { \sum _ { f } F } ~ .$

$$
\delta _ { 1 } = \frac { \sqrt { \displaystyle \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \Bigl ( I _ { i f } - \bigl ( C F \Bigr ) _ { i f } \Bigr ) ^ { 2 } } } { \displaystyle \frac { 1 } { N } \sum _ { i = 1 } ^ { N } I _ { i f } } ,
$$

$$
\delta _ { 2 } = \frac { \sqrt { \displaystyle \frac { 1 } { N \cdot T } \sum _ { f = 1 } ^ { T } \sum _ { i = 1 } ^ { N } \biggl ( I _ { i f } - \left( C F \right) _ { i f } \biggr ) ^ { 2 } } } { \displaystyle \frac { 1 } { N \cdot T } \sum _ { f = 1 } ^ { T } \sum _ { i = 1 } ^ { N } I _ { i f } }
$$

为了验证本文中动力学聚类在解决非唯一性问题的准确性，我们将基于动力学聚类约束的因子分析模型与传统的最小化因子间重叠程度(MSO)的模型进行比较。除了视觉评价外，采用量化指标RMSE对因子与仿真的组织活度曲线分布进行比较：

# 3结果

3.1α散度与最小二乘测度建模的精确性的比较

通过最小化模型与真实图像之间的测度得到初始因子和因子图像后，可用剩余信号来评价不同测度的优劣。图4是最小二乘测度与 $\dot { \alpha }$ 散度测度 $( \alpha { = } 1 , 1 0 , 2 0 , 3 0$ 40,50)所得出的模型归一化误差 $\delta _ { l }$ ，图5是动态图像所有帧的归一化误差 $\cdot \delta _ { 2 }$ 随α的变化情况，由图可知，仅当 $\scriptstyle { a = }$ 1时α测度与最小二乘测度的归一化误差相等，当 $\alpha .$ 取其它值时， $\alpha ^ { \mathrm { i } }$ 散度测度的结果的归一化误差均优于最小二乘测度。

![](images/90dac729ff7776327794f1af182de1aa27d5a92640eb4ff9e80bb539e57d2907.jpg)  
图4不同测度下模型在每帧的归一化误差 $\delta _ { \scriptscriptstyle 1 }$ Fig.4 Normalization error $\delta _ { 1 }$ of the model in eachframeunderdifferentmeasures.

![](images/c77bd461b20116971b2210c50de462ba262a4e37d691bdc738fd21a3db67ba47.jpg)  
图5不同测度下模型的归一化误差 $\cdot \delta _ { 2 }$ Fig.5 Normalization error $\delta _ { 2 }$ of the model underdifferent measures.

# 3.2唯一性约束

得到初始因子后，用最小化因子间重叠程度(MSO)和基于动力学聚类(KB)的两种约束方法解决因子分析模型中的非唯一问题。图6、图7分别给出了对我也燥比（ $\mathrm { \ S N R } ) { = } 1 0$ 的动态序列用两种不同约束方法（模型的测度为a散度测度，且 $\scriptstyle a = 2 5$ 所得到的因子和因子图像，由图可知，所得出的因子1与因子2分别对应于血池TAC与心肌TAC，所得到的因子图像1与因子图像2(图中绘制的是第14层横断面图)也对应于心脏的血池和心肌组织，对于血池的活度曲线，两种方法所得到的因子的精确程度无显著差别，而对于心肌活度曲线，用KB约束得到的因子比MSO约束得到的因子精确度高。

# 3.3α值的选取

为了进一步验证a散度在本模型中的有效性基选取最优的a值，本文选取不同的 $| \alpha \rrangle$ 值在两种约束模型下进行因子分析，为避免实验受噪声的随机性影响，针对每种方法运行30次求平均值，绘制出不同 $\overset { \cdot } { \alpha }$ 值在MSO和KB两种约束下各因子的RMSE图8,在KB约束中，心肌因子的RMSE基本保持稳定，当 $a = 5$ 时估计的血池因子RMSE最小，因此选取5作为本文的最优的 $\alpha$ 值；而在MSO约束中，两因子在 $a { > } 1 2$ 时基本趋于稳定。选取了最优的值后，将 $\alpha$ 散度测度与最小二乘测度在两种不同约束下作比较见表1，结果说明 $\alpha$ 散度的RMSE比最小二乘的低，即该测度更能提取出更准确的结果。此外，由图8可知无论a取何值，用KB约束模型得出的两因子的平均RMSE曲线位于MSO的下方，这亦说明了动力学聚类约束要优于小化因子间重叠程度约束

![](images/67583ada331eb6ca9d80e4c2f710fb08177bb08b8153304966d7c2feb1cd2c2a.jpg)  
图6用MSO约束所得因子及因子图像 Fig.6 The factors and factor images obtained by MSO constraints.

![](images/29f00175e66bef595ec1fb6d9697adf6650f585aa130378ae9c0a87fa8e68178.jpg)  
图7用KB约束所得因子及因子图像 Fig.7Factors and factor images obtained byKB constraints.

# 3.4模型对噪声的敏感度

为了评价噪声对模型的影响，我们通过在图像的投影域中加人不同规模的噪声，重建出不同信噪比的图像。表2表示对不同信噪比的动态序列，用MSO和KB两种不同约束所得到的各因子的RMSE。由表可知，当噪声逐渐增大时，因子的RMSE也相应增大，估计的血池的时间活度曲线比心肌活度曲线精确。

# 4讨论

α散度测度的目的是将动态图像做一个初步的分解，由于分解的结果具有非唯一性，所以根据聚类中心作为先验信息将其中一组解线性变换为具有实际生理意义的时间活度曲线。值得注意的是，动力学聚类结果不能作为最终的TAC，因为聚类与聚类中心过于粗糙，不能较精确地反应真实的动态图像，尤其是对于噪声较大的动态图像。

在加入唯一性约束时，我们引入一个惩罚项 $f _ { n }$ 来保证我们得到的结果是非负的，对于两个正则化参数 $b _ { I }$ 和$b _ { 2 }$ ，实验发现当 $b _ { I } , b _ { 2 } { \in } [ 1 0 , 5 0 0 ]$ 时，结果无明显差异，鉴于此在本实验中将 $b _ { I } , b _ { 2 }$ 均设置为 $1 0 0 _ { \cdot }$ 。对于不同的数据，我们可以参考本数据选取合适的 $b$ 值，若结果出现负值，我们只需要适当地增加 $b$ 的值保证结果是非负的即可。

从该心脏体膜中提取的结果我们我发现，在同样规模噪声的情况下，估计出的血池的时间活度曲线比心肌组织的活度曲线要精确，主要原因是血池的体素数比心肌体素数多，受部分容积效应及噪声的影响较小。在心肌壁的某些部分仅有2\~3个体素的厚度，极容易受到部分容积效应及噪声的影响降低结果的精确度。

![](images/34c4bf132d6e0ff6a62fe33ef7cfd9b34c3892de2460f9a6c0e5a806862a9914.jpg)  
图8不同α值在MSO和KB两种约束下各因子的RMSE Fig.8RMSE of the obtained factors with MSO constraints and KB constraints underα divergence measure.

表1两种测度下应用MSO约束和KB约束的所得各因子的 RMSE Tab.1 RMSE of the obtained factors with MSO constraints and KB constraintsunder two measures   

<html><body><table><tr><td rowspan="2">Item</td><td colspan="2">Least square measure</td><td colspan="2">αdivergence measure (α=5)</td></tr><tr><td>MSO</td><td>KB</td><td>MSO</td><td>KB</td></tr><tr><td>Blood</td><td>4.07%</td><td>1.6%</td><td>2.43%</td><td>0.52%</td></tr><tr><td>Myocardium</td><td>4.89%</td><td>1.48%</td><td>4.43%</td><td>1.45%</td></tr></table></body></html>

表2不同信噪比下各因子的RMSETab.2RMSEof various factorsunderdifferentSNRs  

<html><body><table><tr><td rowspan="2">Item</td><td colspan="2">No noise</td><td colspan="2">SNR=10</td><td colspan="2">SNR=5</td></tr><tr><td>MSO</td><td>KB</td><td>MSO</td><td>KB</td><td>MSO</td><td>KB</td></tr><tr><td>Blood</td><td>0</td><td>0</td><td>2.90%</td><td>0.64%</td><td>8.96%</td><td>1.33%</td></tr><tr><td>Myocardium</td><td>0</td><td>0</td><td>4.44%</td><td>1.44%</td><td>11.32%</td><td>0.467%</td></tr></table></body></html>

Notes:MSO representsMinimal Spatial Overlap constraint method and KB represents Kinetic Basedconstraint method.

本研究提出一种基于动力学聚类与α散度测度的动态三维心脏PET图像因子分析研究模型，实现了对心脏PET图像各组织的时间活度曲线进行精确提取。传统的因子分析模型利用最小二乘模型，用最小化因子图像间重叠程度来解决因子分析模型中的非唯一性问题，本文通过最小化动态图像与因子分析模型的a散度测度，可以通过不同的α值选取比最小二乘适合的测度得到初始因子及因子图像，并在旋转因子时引入PET图像像素的动力学聚类先验信息，我们将模型应用于基于XCAT的仿真数据上，通过实验分析发现，用a散度测度以及基于动力学聚类的先验约束均对组织活度曲线的提取的准确性有积极的作用，在高噪声下( $\mathrm { S N R } { = } 5$ 仍能准确的提取出各组织的时间活度曲线，用视觉评价及量化评价等方法优势明显。然而，本方法在旋转因子时引入正则化参数无法自适应选择,在下一步工作中将进一步研究正则化参数自适应选择问题。

# 参考文献：

[1］王荣福.PET/CT:分子影像学新技术应用[M].北京:北京大学医学出 版社,2011:108-13.   
[2]Su Y,Arbelaez AM, Benzinger TLS,et al. Noninvasive estimation of the arterial input function in positron emission tomography imaging of cerebral blood flow[J].J Cereb Blood Flow Metab, 2013,33(1): 115-21.   
[3]Schupbach WMM,Emese B,Loretan P,et al. Non-invasive diagnosisof coronary artery disease using cardiogoniometry performed at rest[J].Swiss Med.Wkly,2008,138(15-16): 230-8.   
[4]Bisker J.Principles and practice of positron emission tomography [J].Am JRoentgenol, 2012,180(5): 1238.   
[5]Garbarino S,Caviglia G,Brignone M, et al. Compartmental analysis of renal physiology using nuclear medicine data and statistical optimization[J].Physics,2012,3(24): 625-37.   
[6]Fakhri GE,Sitek A,Guerin B,et al. Quantitative dynamic cardiac 82Rb PET using generalized factor and compartment analyses[J]. J Nucl Med,2005,46(8): 1264-71.   
[7]Moody J, Lee BC,Corbett JR,et al. Precision and accuracy of clinical quantification of myocardial blood flow by dynamic PET:A technical perspective[J].JNucl Cardiol, 2015,22(5): 935-51.   
[8]Tio RA,Dabeshlim A,Siebelink HM,et al. Comparison between the prognostic value of left ventricular function and myocardial perfusion reserve in patients with ischemic heart disease[J].JNucl Med,2009,50(2): 214-9.   
[9]Dehak N,Kenny PJ,Dehak R,et al.Front-end factor analysis for speaker verification[J].IEEE Trans Speech Audi P,2011,19(4):788- 98.   
[10]Kim J,Herrero P, Sharp T,et al. Minimally invasive method of determining blood input function from PET images in rodents[J].J Nucl Med,2006,47(2): 330-6.   
[11]Klein R,Beanlands RS,Wassenaar RW,et al.Kinetic model-based factor analysis of dynamic sequences for 82-rubidium cardiac positron emission tomography[J].Med Phys,2010,37(8):3995- 4010.   
[12]Ketata I, Sallemi L,Morainnicolier F,et al.Factor analysis-based approach for early uptake automatic quantification of breast cancer by 18F-FDG PET images sequence [J].Biomed Signal Proces, 2014:19-31.   
[13]Paola RD, Bazin JP,Aubry F,et al. Handling of dynamic sequences in nuclear medicine[J].IEEE Trans Nucl Sci,1982,29(4):1310-21.   
[14]Wu HM,Hoh CK,Choi Y,et al.Factor analysis for extraction of blood time-activity curves in dynamic FDG-PET studies[J].JNucl Med,1995,36(9): 1714-22.   
[15]Whitle P. On principal components and least square methods of factor analysis[J]. Scand Actuar J,2012,35(3-4): 223-39.   
[16] Lord S,Galna B,Verghese J,et al. Independent domains of gait in older adults and associated motor and nonmotor attributes: validation of a factor analysis approach[J].J Gerontol Ser A,2013, 68(7): 820-7.   
[17]Mabrouk R,Dubeau F,Bentabet L. Dynamic cardiac PET imaging: extraction of time-activity curves using ICA and a generalized Gaussian distribution model[J].IEEE Trans Biomed Eng.2013,60 (1): 63-71.   
[18] Su Y,Welch M J, Shoghi K,et al. The application of maximum likelihood factor analysis(MLFA）with uniqueness constraints on dynamic cardiac microPET data[J].Phys Med Biol,2007,52(8): 2313-34.   
[19]Sitek A,Gullberg GT,Huesman RH. Correction for ambiguous solutions in factor analysis using a penalized least squares objective. [J].IEEE Trans Med Imaging,2002,21(3): 216-25.   
[20]Boutchko R,Mitra D,Baker SL,et al. Clustering-initiated factor analysis application for tissue classification in dynamic brain positron emission tomography[J].J Cereb Blood Flow Metab, 2015,35(7):1104-11.   
[21] Jia S,Qian Y. Constrained nonnegative matrix factorization for hyperspectral unmixing［J].IEEE Trans Geosci Electron,2009,47 (1): 161-73.   
[22]Critchley F,Marriott P. Computing with Fisher geodesics and extended exponential families[J]. Stat Comput, 2014,26(1):1-8.   
[23]Teng Y, Zhang T. Generalized EM-type reconstruction algorithms for emission tomography[J].IEEE Trans Med Imaging,2012,31 (9):1724-33.   
[24] Lu L,Karakatsanis NA,Tang J,et al. 3.5D dynamic PET image reconstruction incorporating kinetics-based clusters [J].Phys Med Biol,2012,57(15): 5035-55.   
[25]Segars WP,Mahesh M,Beck TJ,et al. Realistic CT simulation using the 4D XCAT phantom[J].Med Phys,2008,35(8): 3800-8.   
[26]马晓勉,路利军,高园园,等.基于低秩框架的心肌灌注动态PET图像 恢复[J].暨南大学学报:自然科学与医学版,2016,37(1):78-86.   
[27]El Fakhri G,Trott CM, Sitek A,et al.Dual-tracer PET using generalized factor analysis of dynamic sequences[J].Mol Imaging Biol,2013,15(6): 666-74.   
[28]Watabe H, Ikoma Y,Kimura Y,et al.PET kinetic analysis-- compartmental model[J].Ann Nucl Med,2006,20(9): 583-8. （口

（编辑：吴锦雅）