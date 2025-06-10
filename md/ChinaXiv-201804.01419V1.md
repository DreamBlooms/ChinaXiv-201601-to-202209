# 面向聚类的平面反射数据扰动方法

汪小寒a,b，韩慧慧ab，张泽培aʰ，俞庆英ab，郑孝遥a,b(安徽师范大学 a.计算机与信息学院;b.网络与信息安全安徽省重点实验室，安徽 芜湖 241003)

摘要：面向聚类的数据隐藏通常使用数据扰动技术防止敏感信息泄露。针对现有的面向聚类的数据扰动方法隐私保护度低的问题，提出一种基于平面反射的数据扰动方法，将发布对象的全部属性两两配对构成平面上的点，再随机选择一条直线，作每对属性关于直线的对称点，转换后的数据即为发布的数据。实验结果表明，这种方法具有较好的隐私保护度和聚类可用性，且对高维数据有良好的适应性。

关键词：隐私保护；数据扰动；平面反射；聚类挖掘 中图分类号：TP309.2 doi: 10.3969/j.issn.1001-3695.2018.01.0005

# Planar reflection method of data perturbation for clustering

Wang Xiaohana, b, Han Huihuia, b, Zhang Zepeia, b, Yu Qingyinga,b, Zheng Xiaoyaoa, b (a.SchoolofComputer&Information,b.AnhuiProvincialKeyLaboratoryofNetwork &Information SecurityAnhui Normal University,Wuhu Anhui 241003,China)

Abstract:Data hiding for clustering usuallyuses dataperturbation technologyto preventsensitive information disclosure.In orderto solvetheproblem thatthe privacyprotectionof existing data-perturbation method for clustering is low,this paper proposes adataperturbation method basedonplane reflection.Allthe properties of the publishedobject are paired to formthe points nthe plane,thenrandomlyselectastraight lineforeachpairofsymmetrypointsontheline,sotheconverteddatais the data to be published.The experimentalresults showthat this method has good privacy protectionand clustering usability,and has good adaptability to high dimensional data.

Key words: privacy protection; data perturbation; plane reflection; clustering mining

# 0 引言

随着电子政务和电子商务的发展，个人数据在线交换不断增长，使数据收集变得越来越容易。数据挖掘者能从庞大的数据中提取许多有价值的信息，为广泛的应用提供支持。然而，这会引起个人隐私泄露和用户安全受到威胁的问题。因此，为了防止数据挖掘者收集大量隐私数据后泄露隐私信息，必须对原始数据进行处理。

数据匿名通过更改或模糊化原始数据方式更改或发布，改变后的数据即使与其他信息结合，也不能推理出任何关键信息。Sweeney[1]首先提出 $k \mathrm { . }$ 匿名隐私保护模型，它的基本思想是发布用户信息的时候，用户的真实信息不能从k-1个用户中区分出来。后续基于 $k \mathrm { . }$ 匿名模型的各种隐私改进原则，提出t-closeness[2], $( c , \ l )$ -diversity[3]，Hybrid $k$ -anonymity[4]等模型。并在不同的隐私保护领域广泛应用，如数据挖掘中[5]和位置服务中[。然而，经过匿名化处理后，会造成不同程度的信息损失，数据可用性降低。相比之下，扰动通过修改原始数据，并尽可能保留原始数据的特征，扰动后不仅保护了数据隐私，还能维持数据集的可用性，更适用于数据挖掘。

因此，数据扰动方法被广泛用于面向聚类的隐私保护中。现有面向聚类的扰动大多采用平移、缩放和旋转几何数据转换方法，存在几何数据变换函数是可逆的缺点，会导致处理后的数据隐私保护级别太低[7。针对该问题，本文提出基于平面反射的数据扰动方法，不仅提高了隐私保护水平，还保留了良好的数据特征，更有利于聚类分析。

本文的主要贡献如下:a)提出一种新的数据扰动方法，利用平面反射改变原始数据，将发布对象的全部属性两两配对构成平面上的点，再随机选择一条直线，作每对属性关于直线的对称点，可以隐藏敏感信息，保护数据隐私;b）用理论证明了本文提出的方法是一种完全保距变换，扰动后的数据保持着良好的聚类可用性;c）采用真实数据集，从隐私保护度和运行时间两个方面进行了实验与分析，结果表明提出方法隐私保护度较好，对高维数据有良好的适应性和高效性。

# 1 相关工作

为了保护用户的敏感信息，研究者提出了不同的数据扰动方法。黄茂峰等人[8利用对数螺线的几何性质，对原始数据进行扰动，能够有效的保护数据隐私，但是这种方法所选择的投影子集分割范围较小，对低维数据点进行扰动时，隐私保护强度不高。Guang等人[9]利用奇异值分解方法，对不同的样品数据进行不同程度的扰动，代替原始数据，这种方法有效的平衡了数据隐私与数据的可用性，但只能用于分类问题，而数据挖掘是不限于分类的。为了提供云服务中的范围查询和KNN 查询服务数据安全和保护，Xu等人[10提出一种随机空间扰动的数据扰动方法，然而，这种方法专门用于扰乱云服务中上传的数据，将用户的数据安全保存在云数据库中。

几何数据转换方法是面向聚类的数据扰动常用方法。Oliveira 等人[1I:12]利用平移、缩放和旋转转换方法，实现对数值数据聚类隐私保护。这种方法可用于低维数据和高维数据，算法的复杂度低，可扩展性强，但是隐私保护度较低。Rajalaxmi等人[13]提出基于几何数据变换混合数据转换方法，对每个敏感属性从平移、缩放和旋转方法中随机选择两种进行操作，以满足隐私保护要求，保持一般聚类分析功能，但是这种方法主要解决分类中的聚类隐私保护问题。王静等人[14]提出了一种基于二次反射的数据转换方法(DRDP)，采用沿着对称轴反射的方法，得到新的点坐标，转换后的数据与原始数据相差较大，但是原始数据很容易被还原。Giannella等人[15]指出当已知的原始数据元组少于数据维数时，攻击者只要有一组已知的原始数据元组(或输入)，做很少的工作就能导致原始数据的泄露。

目前，国内外针对基于平面反射数据扰动方法的研究也取得了较好的效果。Achlioptas[16]提出基于随机映射的数据转换方法，通过乘以随机矩阵来扰动，达到隐私保护的目的，但是该方法聚类结果高度不确定，且只适用于高维数据的聚类。Oliveira 和Zaiane[1]利用旋转的数据转换方法，将数据集的所有属性两两分组，当属性数目为奇数时，将剩余的那个属性与已扰动的某个属性组合在一起，每个属性对对应一个 $\mathtt { n } ^ { * } 2$ 的矩阵，将其乘以一个变换矩阵，从而实现对隐私数据的保护，但是这种方法攻击者只要利用矩阵的某些理论性质，就可以公开原始数据值。王静和汪晓刚[14]提出一种基于二次反射的数据转换方法，取敏感属性最大值和最小值之和的平均值向下取整得到的数值作为对称轴，沿着对称轴进行反射得到新的坐标点，但是这种方法原始数据很容易被还原。刘杰等[17]提出了一种基于平面反射几何数据转换方法，将发布对象的属性两两配对构成平面上的点，当属性数目为奇数时，将剩下的一个未配对的属性与一个已配对的属性进行配对，然后作关于一条直线的平面反射，但是它只对低维数据进行研究，并未涉及高维数据。

在许多情况下，攻击者没有任何先验知识似乎是不合理的假设，因此，现有的面向聚类扰动方法大多数具有隐私保护度低的缺点。本文提出的基于平面反射数据扰动方法，通过一些属性随机生成，所有属性随机两两配对，再经过任意一条直线的反射，对原始数据进行扰动，即使攻击者获得任意一组已知的原始数据元组，也不会导致原始数据的泄露，因此，本文提出的方法可以实现更高的隐私保护度。

# 2 预备知识

# 2.1基本概念

定义1反射[18]。设 $\mathbf { \xi } _ { l }$ 是平面上的一条定直线，平面上任意一点 $p$ 关于1对称点为 $p ^ { ' }$ 。从点 $p$ 以 $l$ 为轴映射到另一点 $p ^ { ' }$ ，这种映射是平面上以 $l$ 为轴的反射。

反射具有两个基本特征：a）点 $p$ 与 $p ^ { ' }$ 连线的中点在直线1上;b）点 $p$ 与 $p ^ { ' }$ 连线的斜率与直线 $l$ 的斜率的乘积为-1。

定义2变换[18]。把平面中的每一个点，变成和它同一个平面内相应的唯一点，并且平面中的每一个点都是由相应的某一个点变换的，把这种平面中点的位置变化称作平面中一个点的变换。

定义3保距变换[18]。如果一个变换（记为 $f$ ）把任意的两个点A、 $B$ 变成 $\ddot { A ^ { ' } } \cdot \enspace B ^ { ' }$ ，使 $d \big ( f \big ( A \big ) , f \big ( B \big ) \big ) = d \big ( A ^ { \cdot } , B ^ { \cdot } \big )$ ，则这个变换具有保距性，称为保距变换。即经过变换，使任意两个原象之间的距离与转换后相对应的两个象之间的距离相等。

定理1从点 $P \left( X , Y \right)$ 到点 $p ^ { \prime } \bigl ( \boldsymbol { X } ^ { \prime } , \boldsymbol { Y } ^ { \prime } \bigr )$ 的映射 $\delta \ : \delta \ :$ 在平面直角坐标系下表达式为

$$
\left\{ \begin{array} { c } { { X ^ { ' } = a _ { 1 1 } X + a _ { 1 2 } Y + b _ { 1 } } } \\ { { Y ^ { ' } = a _ { 2 1 } X + a _ { 2 2 } Y + b _ { 2 } } } \end{array} \right.
$$

其系数 $\begin{array} { r } { \left[ \begin{array} { l l } { a _ { 1 1 } } & { a _ { 1 2 } } \\ { a _ { 2 1 } } & { a _ { 2 2 } } \end{array} \right] } \end{array}$ 是正交矩阵，那么映射 $\delta$ 为保距变换。

证明设点 $M \left( X _ { 1 } , Y _ { 1 } \right)$ ， $N \big ( X _ { 2 } , Y _ { 2 } \big )$ 是平面上的任意两点，他们关于映射 $\delta$ 的对称点分别为 $\boldsymbol { M } ^ { \prime } \left( \boldsymbol { X } _ { 1 } ^ { \prime } , \boldsymbol { Y } _ { 1 } ^ { \prime } \right)$ ， $N ^ { ' } \left( X _ { 2 } ^ { ' } , Y _ { 2 } ^ { ' } \right) \circ$

由式（1）可知：

$$
{ \left[ \begin{array} { l } { X _ { 1 } ^ { ' } - X _ { 2 } ^ { ' } } \\ { Y _ { 1 } ^ { ' } - Y _ { 2 } ^ { ' } } \end{array} \right] } = { \left[ \begin{array} { l l } { a _ { 1 1 } } & { a _ { 1 2 } } \\ { a _ { 2 1 } } & { a _ { 2 2 } } \end{array} \right] } { \left[ \begin{array} { l } { X _ { 1 } - X _ { 2 } } \\ { Y _ { 1 } - Y _ { 2 } } \end{array} \right] }
$$

由欧氏距离得：

$$
\left| M ^ { ' } N ^ { ' } \right| ^ { 2 } = \left( X _ { 1 } ^ { ' } - X _ { 2 } ^ { ' } , Y _ { 1 } ^ { ' } - Y _ { 2 } ^ { ' } \right) \left[ X _ { 1 } ^ { ' } - X _ { 2 } ^ { ' } \right]
$$

由式（2）（3）得

$$
\begin{array} { r l } & { \left| M ^ { \prime } N ^ { ' } \right| ^ { 2 } = \left( X _ { 1 } ^ { ' } - X _ { 2 } ^ { ' } , Y _ { 1 } ^ { ' } - Y _ { 2 } ^ { ' } \right) \left[ \begin{array} { l l } { a _ { 1 1 } } & { a _ { 1 2 } } \\ { a _ { 2 1 } } & { a _ { 2 2 } } \end{array} \right] \left[ \begin{array} { l } { X _ { 1 } - X _ { 2 } } \\ { Y _ { 1 } - Y _ { 2 } } \end{array} \right] } \\ & { = \left( X _ { 1 } - X _ { 2 } , Y _ { 1 } - Y _ { 2 } \right) \left[ \begin{array} { l l } { a _ { 1 1 } } & { a _ { 1 2 } } \\ { a _ { 2 1 } } & { a _ { 2 2 } } \end{array} \right] ^ { T } \left[ \begin{array} { l l } { a _ { 1 1 } } & { a _ { 1 2 } } \\ { a _ { 2 1 } } & { a _ { 2 2 } } \end{array} \right] \left[ \begin{array} { l } { X _ { 1 } - X _ { 2 } } \\ { Y _ { 1 } - Y _ { 2 } } \end{array} \right] } \\ & { = \left| M N \right| ^ { 2 } } \end{array}
$$

因此，定理1中映射 $\boldsymbol { \delta }$ 为保距变换。

定理2反射变换是保距变换。

证明设直线方程为 $Y = k X + b$ ，任意一点 $M ( X , Y )$ 关于直线的对称点为 $M ^ { ' } \left( \boldsymbol { X } ^ { ' } , \boldsymbol { Y } ^ { ' } \right)$ 。根据反射的两个基本特征得如下方程：

$$
\left\{ \begin{array} { c } { { { \displaystyle { \frac { Y + Y ^ { ' } } { 2 } } } = k { \frac { X + X ^ { ' } } { 2 } } + b } } \\ { { { \displaystyle { \frac { Y - Y ^ { ' } } { X - X ^ { ' } } } } = - { \frac { 1 } { k } } } } \end{array} \right.
$$

由式（5）得

$$
\left\{ { \cal X } ^ { ' } = \frac { 1 - k ^ { 2 } } { 1 + k ^ { 2 } } { \cal X } + \frac { 2 k } { 1 + k ^ { 2 } } { \cal Y } - \frac { 2 k b } { 1 + k ^ { 2 } } \right.
$$

因为 ${ \left[ \begin{array} { l l } { { \frac { 1 - k ^ { 2 } } { 1 + k ^ { 2 } } } } & { { \frac { 2 k } { 1 + k ^ { 2 } } } } \\ { { \frac { 2 k } { 1 + k ^ { 2 } } } } & { { \frac { k ^ { 2 } - 1 } { 1 + k ^ { 2 } } } } \end{array} \right] } { \left[ \begin{array} { l l } { { \frac { 1 - k ^ { 2 } } { 1 + k ^ { 2 } } } } & { { \frac { 2 k } { 1 + k ^ { 2 } } } } \\ { { \frac { 2 k } { 1 + k ^ { 2 } } } } & { { \frac { k ^ { 2 } - 1 } { 1 + k ^ { 2 } } } } \end{array} \right] } ^ { T } = E$ =E，所以矩阵$\left[ \begin{array} { l l } { \displaystyle \frac { 1 - k ^ { 2 } } { 1 + k ^ { 2 } } } & { \displaystyle \frac { 2 k } { 1 + k ^ { 2 } } } \\ { \displaystyle \frac { 2 k } { 1 + k ^ { 2 } } } & { \displaystyle \frac { k ^ { 2 } - 1 } { 1 + k ^ { 2 } } } \end{array} \right]$ 是正交矩阵，根据定理1，该变换是保距变换。

# 2.2 聚类的可用性

在聚类挖掘时，通过分析聚类数据记录之间的相似性和聚类外部的相异性来划分聚簇。其中，在聚类分析中，距离是用来衡量数据记录之间的相似或相异的常用工具。如果一个数据集中的任意两个数据记录修改前后距离关系保持不变，就可以实现良好的聚类可用性。面向聚类的数据隐藏为了维持较高聚类可用性，需要保证修改前的数据集和修改后的数据集具有尽可能相似的聚簇结构和特征，并且应该保持数据集内的每个数据记录修改前后的聚簇标志尽可能不改变。本文提出的基于平面反射的数据扰动方法完全是一种保距变换，因此聚类可用性好，不影响数据挖掘结果的准确性。

# 2.3几何数据转换方法

几何数据转换是基于图形成像原理，通过平移、缩放、旋转和反射等方式对原始数据进行扰动来隐藏敏感数值属性，同时保留原始属性的特征。

a)平移是指在同一个平面内，把一个图形上的所有位置坐标点沿着某一方向移动相同的距离，即对发布对象的每个敏感属性使用加法噪声扰动，使用的噪声项是常数且可以是正的或负的。

b)缩放变换常用于改变图形的尺寸，即对发布对象的每个敏感属性使用乘法噪声扰动，使用的噪声项也是常数且可以是正的或负的。

c)二维旋转是将图形沿着xy平面内的圆弧路径重新定位，即将发布对象的全部属性随机配对，配对后构成的点为旋转点的位置。噪声项是旋转角度 $\theta$ ，旋转角的正值为绕旋转点的逆时针方向旋转，负值则是绕旋转点的顺时针旋转。

d)混合数据转换是指对发布对象的多个敏感属性任意选取平移、缩放和旋转等不同方式的变换，噪声项是常数或旋转角度 $\theta$ □

e)二次反射转换是指沿着对称轴反射的方法，获得新的坐标点。所谓二次反射是指点的横坐标和纵坐标都进行了反射，即属性对同时进行反射。设发布对象中共有 $n$ 对敏感属性， $O P _ { i }$ （204表示反射操作， $a _ { i } \left( 1 \leq i \leq n \right)$ 是发布对象的任意敏感属性，对称轴取该 $a _ { i }$ 的最大值与最小值之和的平均值向下取整得到的数值。对敏感属性 $a _ { i }$ 进行 $O P _ { i }$ 操作，就是将 $a _ { i }$ 沿着对称轴进行反射。

下面把几何数据转换各种方法分别定义了统一噪声矢量，具体说明如表1所示。

表1定义统一噪声矢量  

<html><body><table><tr><td>数据转换方法</td><td>统一噪声矢量</td></tr><tr><td>平移</td><td>(<add，常数1>，<add，常数 2>）</td></tr><tr><td>缩放</td><td>(<mult，常数1>，<mult，常数 2>）</td></tr><tr><td>旋转</td><td>(<rotate，>)</td></tr><tr><td>混合数据转换</td><td>(<mult，常数1>，<add，常数 2>)</td></tr><tr><td>二次反射转换</td><td>(<ai，OP:>)</td></tr></table></body></html>

# 3 基于平面反射数据扰动方法

本文提出的基于平面反射数据扰动方法，通过把原始数据集的全部属性随机配对，然后任意选择一条直线作每对属性的对称点，以此对原始数据进行修改，从而把敏感信息隐藏起来，实现隐私保护。同时攻击者无法根据扰动后的数据恢复或重构出真实和完整的原始数据，但是从扰动后的数据中可以得到与原始数据聚类相同的信息，从而保持数据聚类可用性不变。

# 3.1基本思路

首先将发布对象的全部属性两两配对构成平面上的点，再任意选择一条直线，作每对属性关于该直线的对称点，转换后的数据即为要发布的数据，具体方法概述如下：

a)将发布对象的所有属性两两配对构成平面上的点，如果发布对象所拥有的属性数目为偶数直接两两配对，否则随机生成一组与发布对象属性数目相同的数据，然后再两两配对。

b)手动随机设置直线的斜率和截距，产生一条直线，然后根据式（5）解得的等式（6）将配对后的每对属性作关于直线的对称点。

c)发布的数据即为转换后的数据。

# 3.2算法实现

本文提出的基于平面反射数据扰动算法详细描述如下。其中， $D _ { m ^ { * } n }$ 表示原始数据集， $D _ { m ^ { * } n } ^ { \phantom { * } }$ 表示转换后的数据集， $\mathbf { \nabla } _ { m }$ 表示原始数据集数据实例的个数， $n$ 表示原始数据集属性的个数。设直线的斜率为 $k$ ，直线的截距为 $b$ 。

算法：基于平面反射的数据扰动方法输入：原始数据集Dm\*

输出：转换后的属性集 $D _ { m ^ { * } n } ^ { \phantom { * } }$   
1）get $D _ { m ^ { * } n }$ ; $/ /$ 读取原始数据集  
2）If $( n \ \% 2 = = 0$ ）//判断属性数目 $n$ 是否为偶数  
3） $\mathrm { t e m p \_ n } = n$ ；//将属性数目值暂存于temp_n中  
4）Else  
5） temp $\scriptstyle \mathtt { n } = n + 1$ ；//属性数目加1  
6）end if  
7）producepq()；//随机产生属性对  
8）for each $D _ { i ^ { * } t i m e s } \in D _ { m ^ { * } t e m p _ { - } n }$ |/每个数据实例  
9） If（times<temp_n）//随机生成一个数据  
10) data.push_back ( $\cdot D _ { i ^ { * } t i m e s }$ ）  
11) ++times;  
12) Else  
13) times=0;  
14) data.push_back (rand());  
15) end if  
16) for each attributes $( X , \ Y )$ //每对属性进行转换  
17) $\begin{array} { c } { { X ^ { ' } = \displaystyle \frac { 1 - k ^ { 2 } } { 1 + k ^ { 2 } } X + \displaystyle \frac { 2 k } { 1 + k ^ { 2 } } Y - \displaystyle \frac { 2 k b } { 1 + k ^ { 2 } } ~ ; } } \\ { { { } } } \\ { { Y ^ { ' } = \displaystyle \frac { 2 k } { 1 + k ^ { 2 } } X + \displaystyle \frac { k ^ { 2 } - 1 } { 1 + k ^ { 2 } } Y + \displaystyle \frac { 2 b } { 1 + k ^ { 2 } } ~ ; } } \end{array}$   
18)  
19) end for  
20）end for  
21）Output Dm\*n" ;

现举例说明上述的算法的转换结果，表2为原始数据，表3为转换后的数据。表2是由2014年全省县级常住人口调查主要数据公报得到的安徽省16个市县的部分区域数据。其中，Index 表示序列号，Area表示每个市县的占地面积，Population表示各个市县年末常住人口的数量，Population density 表示各个市县的人口密度。算法过程如下。

首先，1\~7行，由于发布对象的属性（Area、Population、Populationdensity）数目为奇数，因此，将属性数目加1，对属性进行编号，随机组成属性对，属性组的选取为：（Area，Population），（Populationdensity，randomattribute）；然后，8\~15行，读取表2中发布对象的每个数据实例，并随机生成一个属性数据；最后，16\~20行，按照选择的属性配对方式，随机选取 $k { = } 8$ ， $b { = } 1 0$ 来对每对属性进行平面反射数据转换。转换后的数据如表3所示，21行输出即为最终要发布的数据。

# 3.3算法复杂度分析

在基于平面反射数据扰动方法中，步骤a）时间复杂度为$O ( n )$ ，步骤b）时间复杂度为 $O ( m ^ { * } n )$ ，所以总的时间复杂度为 $O ( m ^ { * } n )$ 。算法空间开销最大的是对发布对象的所有属性进行随机配对，需要开辟额外 $O ( n )$ 的内存空间来存储配对好的数据，因此算法的空间复杂度为O(n)。

表2原始数据  

<html><body><table><tr><td></td><td>Index Area(km²)</td><td colspan="2">Population（人） Population density（人/km²））</td></tr><tr><td>1</td><td>6911</td><td>7696000</td><td>1113.6</td></tr><tr><td>2</td><td>3317</td><td>3617000</td><td>1090.4</td></tr><tr><td>3</td><td>5952</td><td>3258000</td><td>547.4</td></tr><tr><td>4</td><td>2526</td><td>2375000</td><td>940.2</td></tr><tr><td>5</td><td>4049</td><td>2229000</td><td>550.5</td></tr><tr><td>6</td><td>2802</td><td>2159000</td><td>770.5</td></tr><tr><td>7</td><td>1113</td><td>738000</td><td>663.1</td></tr><tr><td>8</td><td>15329</td><td>5376000</td><td>350.7</td></tr></table></body></html>

表3转换后数据  

<html><body><table><tr><td></td><td>Index Area（km²)</td><td>Population（人）</td><td>Population density （人/km²）</td></tr><tr><td>1</td><td>1887700</td><td>7460900</td><td>3013.46</td></tr><tr><td>2</td><td>887121</td><td>3506520</td><td>1672.5</td></tr><tr><td>3</td><td>796198</td><td>3159220</td><td>2394.98</td></tr><tr><td>4</td><td>582165</td><td>2302550</td><td>533.16</td></tr><tr><td>5</td><td>544750</td><td>2161410</td><td>1395.3</td></tr><tr><td>6</td><td>528728</td><td>2093260</td><td>3282.99</td></tr><tr><td>7</td><td>180580</td><td>715567</td><td>7355.58</td></tr><tr><td>8</td><td>1308460</td><td>5214360</td><td>2963.72</td></tr></table></body></html>

# 4 实验与分析

实验环境为处理器Intel(RCoreTMi5-6300HQ，内存4GB,操作系统Windows 10，程序编译环境Visual Studio community2015。实验的数据选自DIM-sets(high)（http://cs.joensuu.fi/sipu/datasets/）中的聚类数据集，DIM-sets(high)是合成的数据，拥有6个高维数据集，维数分别是32、64、128、256、512、1024，除了维数256的数据集数据数量是1020，其他维数的数据数量均为1024。实验结果至少测试6遍以上取测试平均值求得。主要从隐私保护度和运行时间两个方面来分析算法的性能。

# 4.1隐私保护度

数据扰动后，可以通过计算原始属性值与扰动后的属性值之间的差异来评估隐私保护安全程度[19]，可以描述为：$S = V a r \big ( X - X ^ { ' } \big ) \big / V a r \big ( X \big ) = \sigma _ { \left( X - X ^ { ' } \right) } ^ { 2 } \Big / \sigma _ { X } ^ { 2 }$ （ $\sigma$ 是方差函数)。其中，$V a r ( X - X ^ { ' } )$ 的值越小，扰动前后的属性值越接近，反之扰动前后的属性值差别越大。

针对不同维度的数据，隐私度的定义为： $ { \boldsymbol { S } } ^ {  { ' } } = \sum _ { i = 1 } ^ { i = n }  { \boldsymbol { S } } _ { i } \Biggl / n$ ，其中，n表示数据集维度个数，当数据集是单维度时， $\boldsymbol { S ^ { ' } } = \boldsymbol { S ^ { \mathrm { ~ \circ ~ } } } \boldsymbol { S ^ { ' } }$ 越大，扰动前后数据集的属性值差别越大，隐私保护安全度越高。

表4给出了当直线斜率 $k$ 和直线截距 $b$ 取值不同时，第1维、第2维和第5维数据的隐私保护度。

表4隐私保护度  

<html><body><table><tr><td>序号</td><td>k</td><td>b</td><td>Var（第1维）</td><td>Var（第2维）</td><td>Var（第5维）</td></tr><tr><td>1</td><td>1</td><td>0</td><td>1.0020</td><td>1.3850</td><td>1.8901</td></tr><tr><td>2</td><td>1</td><td>43000</td><td>1.0020</td><td>1.3850</td><td>1.8362</td></tr><tr><td>3</td><td>1</td><td>-43000</td><td>1.0020</td><td>1.3850</td><td>2.0293</td></tr><tr><td>4</td><td>2</td><td>43000</td><td>2.5600</td><td>1.5097</td><td>2.0204</td></tr><tr><td>5</td><td>5</td><td>43000</td><td>3.6994</td><td>1.7621</td><td>1.8499</td></tr><tr><td>6</td><td>-5</td><td>43000</td><td>3.6985</td><td>2.2379</td><td>2.1788</td></tr><tr><td>7</td><td>50</td><td>43000</td><td>3.9968</td><td>1.9753</td><td>1.5996</td></tr><tr><td>8</td><td>-50</td><td>43000</td><td>3.9968</td><td>2.0244</td><td>2.2096</td></tr><tr><td>9</td><td>500</td><td>43000</td><td>0.0000</td><td>1.9976</td><td>1.7995</td></tr><tr><td>10</td><td>-500</td><td>43000</td><td>0.0000</td><td>2.0024</td><td>2.5574</td></tr><tr><td>11</td><td>50000</td><td>43000</td><td>4.0000</td><td>2.0000</td><td>1.8000</td></tr></table></body></html>

分析表4，从1\~3行可知，隐私保护度几乎不受 $b$ 取值的任何影响，因为 $b$ 值的改变相当于对直线作平移，即对原始属性值作平移。因此，b值的随机选取有利于提高隐私保护度。由7\~10行可以看出，k取正值或负值对隐私保护度的影响不大。由1、4、5、7、9和11行可以看出，随着 $k$ 值的增加，第1维的隐私保护度先增加再急速减少最后又急速增加，第2维的隐私保护度逐渐缓慢增加，第5维的隐私保护度围绕1.8000上下波动，由此可见，随着数据维数的增加数据隐私保护度适应性越好，即对高维数据有良好的适应性。

表5 是几何数据转换各种方法，即平移（TDP）[12]、缩放（SDP）[12]、旋转（RDP）[12]、混合数据转换（HDP）[12]和基于二次反射的数据转换方法（DRDP)[14]，噪声矢量取不同值，第1维、第2维和第5维数据的隐私保护度的变化结果。

表5隐私保护度的比较  

<html><body><table><tr><td rowspan="2">数据 转换法</td><td rowspan="2">噪声矢量</td><td rowspan="2">Var (第1维）</td><td rowspan="2">Var</td><td rowspan="2">Var （第5维）</td></tr><tr><td>（第2维）</td></tr><tr><td>TDP</td><td>(<add,5>,<add,-5>)</td><td>0</td><td>0</td><td>0</td></tr><tr><td>TDP</td><td>(<add,500>,<add,-500>)</td><td>0</td><td>0</td><td>0</td></tr><tr><td>SDP</td><td>(<mult,1.01>,<mult,0.99>)</td><td>0.0001</td><td>0.0001</td><td>0.0001</td></tr><tr><td>SDP</td><td>(<mult,100>,<mult,0.01>)</td><td>9801</td><td>4900.99</td><td>5580.992</td></tr><tr><td>RDP</td><td>(<rotate,50>)</td><td>0.0012</td><td>0.07</td><td>0.05786</td></tr><tr><td>RDP</td><td>(<rotate,-50>)</td><td>3.3822</td><td>3.6744</td><td>3.5896</td></tr><tr><td>HDP</td><td>(<mult,0.5>,<add,2>)</td><td>0.25</td><td>0.125</td><td>0.15</td></tr><tr><td>HDP</td><td>(<mult,100>,<add,2>)</td><td>9801</td><td>4900.5</td><td>5880.6</td></tr><tr><td>DRDP</td><td>(<ai，OP,>)</td><td>4</td><td>4</td><td>4</td></tr></table></body></html>

分析表5可知，对于TDP方法，经过它变换的属性值看起来与原始属性值很相近，但隐私保护度几乎为0。对于SDP、RDP和HDP方法，它们的隐私保护度会随着噪声矢量的选取，而急剧变化，因此隐私保护度不稳定，而DPDR方法采用二次反射的数据转换方法，在隐私保护度上有很大改进，但是原始数据很容易被还原。以上分析可知，几何数据转换的这些方法的隐私保护度非常低，其中DPDR方法在列出的五种方法中隐私保护度最好。列出的五中方法中，只要攻击者获得任意一个敏感属性数据，用户的敏感属性就会被泄露[15]，而本文方法所有属性两两配对具有随机性，b值和k值的选取也是随机的，由于随机不确定性无法还原，即使攻击者获得任意一个敏感属性对，也不会泄露用户的全部敏感属性。表4也显示该方法基本不受b值和k取正值或负值干扰，且随着数据维度的增加，数据隐私保护度越稳定，本文提出的方法具有更好的隐私保护度。

# 4.2配对方式对隐私保护度和运行时间的影响

本节验证发布对象的属性之间不同的配对方式对隐私保护度和运行时间的影响。选用属性为6和数据记录数量是1000的数据集，对所有属性随机配对会产生不同的配对方式，本次实验只选取了部分配对方式，实验结果如表6所示。

表6不同的配对方式下隐私保护度和运行时间的结果  

<html><body><table><tr><td>序号</td><td>配对方式</td><td>隐私保护度</td><td>运行时间</td></tr><tr><td>1</td><td>(3,1)(4,2)(5,0)</td><td>2.4604</td><td>0.288</td></tr><tr><td>2</td><td>(0,1)(4,2)(5,3)</td><td>2.4414</td><td>0.288</td></tr><tr><td>3</td><td>(2,0)(4,3)(5,1)</td><td>4.4001</td><td>0.284</td></tr><tr><td>4</td><td>(1,3)(2,0)(5,4)</td><td>1.9493</td><td>0.284</td></tr><tr><td>5</td><td>(0,3)(4,2)(5,1)</td><td>2.438</td><td>0.282</td></tr><tr><td>6</td><td>(0,2)(1,5)(3,4)</td><td>4.7646</td><td>0.269</td></tr><tr><td>7</td><td>(0,2)(1,5)(3,4)</td><td>4.7646</td><td>0.280</td></tr><tr><td>8</td><td>(0,2)(1,4)(3,5)</td><td>3.2526</td><td>0.282</td></tr></table></body></html>

从表6可以看出，有七种配对方式且每种配对方式的隐私保护度都不相同，表明不同的配对方式隐私保护度不同。从1和2行、3和4行，以及5和8行可知，不同的配对方式运行时间可能相等。从6和7行可知，即使配对方式相同，运行时间也可能不同。因此，算法的运行时间不受配对方式的影响，而隐私保护的强度却受配对方式的影响，同时配对方式的多样性，可以更好的保护隐私信息。

# 4.3不同维数下运行时间的对比

为了验证维数对运行时间的影响，实验中分别选择2、32、128、700、850和1024维数据集，每个数据集分别在数据记录数量为500、1000、1500、2000、2500和5000下进行实验，算法的运行时间在不同维度下随着数据记录数量增加的比对结果如图1所示。

分析图1可知，当数据记录数量一定时，运行时间随着数据集维数增加而增加，曲线趋近于线性变化状态，时间复杂度较低，对高维数据具有良好的适应性，算法具有较好的稳定性。从图中可以看出，在1024维、5000条记录的数据集下，运行时间是160多秒，算法性能很高。是由于发布对象的属性数目是偶数时，直接对每个属性进行编号并两两配对，读取属性数据和平面反射转换同步进行；当发布对象的属性数目是奇数时，先将属性数目加1，再对每个属性进行编号，然后对编号进行随机配对，其中，读取发布对象的属性数据和随机生成一个属性数据，以及每对属性进行平面反射数据转换均同步进行。

![](images/f0d7785a5664686d92c165abafe7e789eda6f4a863e6b667bc4d05e823e87589.jpg)  
图1不同维数下运行时间比对结果

现有的多媒体数据、时间序列数据、空间数据、基因数据等聚类数据，常常会随着维数的增长，聚类的时间迅速增加导致算法性能下降，因此，本文算法更适合此类数据挖掘中对时间性能高要求的场景。

# 4.4数据记录数量对运行时间的影响

本节验证了数据记录数量的变化对算法运行时间的影响。本次实验选用6维数据集，分别测试了数据记录数量是500、1000、1500、2000、2500、3000、3500、4000、4500和5000上的运行时间，并分别记录了每组数据多次测试的运行时间，然后结果取平均值，实验结果如图2所示。

![](images/4d14b30e4240a83fd9d124516f76fd0f77dae4a9926d4f743473f64f91e6c61c.jpg)  
图2数据记录数量对运行时间的影响

分析图2可以看出，随着数据记录的增长，运行时间在不断增加，即数据记录越多运行时间越长，当数据记录为5000时，运行时间分别是数据记录为500、1000和2500的运行时间的10倍、5倍和2倍，数据记录条目为2000时，运行时间分别是数据记录条目为500和1000的运行时间的4倍和2倍，由此可见，数据记录与运行时间成正比。同时表明，该算法能够处理大量的数据。同理，其他维数的数据集也呈现如此规律。

# 5 结束语

本文针对聚类的数据隐私保护问题，提出了一种基于平面反射数据扰动的方法，利用平面反射来干扰原始数据点的属性值，可以更好地保护数据隐私，保持聚类的数据可用性，使得数据挖掘结果准确度较高、算法的复杂性较低，且对高维数据有良好的适应性，但是该方法仅仅用于处理数值型属性，并没有对其他数据类型属性进行研究。

本文随机选择发布对象的所有属性两两配对，没有选取最优的配对方式，下一步将对提高隐私保护度进行更加深入的研究。

# 参考文献：

[1]Sweeney L. k-anonymity: a model for protecting privacy [J]. International Journal of Uncertainty,Fuzziness and Knowledge-Based Systems,2002,10 (5): 557-570.   
[2]Li N,Li T, Venkatasubramanian S. Closeness: a new privacy measure for data publishing [J]. IEEE Trans on Knowledge and Data Engineering,2010 22 (7): 943-956.   
[3] Chakraborty S,Ambooken JG,Tripathy B K,et al. Analysisand performanceenhancementtoachieverecursive(c,l） diversity anonymization in social networks [J]. Trans on Data Privacy,2Ol5,8 (2): 173-215.   
[4]Aldeen YAA S,Salleh M.A hybrid k-anonymity data relocation technique forprivacypreserveddataminingincloudcomputing[J]. ,2016,17(5):51-58.   
[5]Bhaladhare PR, Jinwala D C.Novel approaches for privacy preserving data mining in k-anonymity model [J]. Journal of Information Science and Engineering,2016,32(1): 63-78.   
[6]Jia J, Zhang F. Nonexposure accurate location k-anonymity algorithm in LBS [J]. ScientificWorldJournal,2014,2014 (3): 619357.   
[7]Banu R V, Nagaveni N. Evaluation of a perturbation-based technique for privacy preservation in a multi-party clustering scenario [J]. Information Sciences,2013,232 (5): 437-448.   
[8] 黄茂峰，倪巍伟，王佳俊，等．一种面向聚类的对数螺线数据扰动方法 [J]．计算机学报,2012,35(11):2275-2282.   
[9] Guang L I,Wang Y D.An improved privacy-preserving clasification mining method based on singular value decomposition [J].Acta Electronica Sinica,2012,9(6): 529-534.   
[10] Xu H, Guo S,Chen K.Building confidential and eficient queryservices in thecloud with RASP data perturbation [J]. IEEE Trans on Knowledge and Data Engineering,2012,26 (2): 322-335.   
[11] Oliveira S R M, Zaiane OR. Achieving privacy preservation when sharing data for clustering [C]// Proc of Secure Data Management Workshop.2004: 67-82.   
[12] Oliveira S R M, Zaane OR,Agropecuaria EI. Privacy preserving clustering by data transformation [C]// Proc of Brazilian Symposium on Databases. 2003: 37-52.   
[13] Rajalaxmi RR,Natarajan A M.An effective data transformation approach for privacy preserving clustering [J]. Journal of Computer Science,2008, 4 (4): 320-326.   
[14]王静.汪晓刚．一种新的保护原始数据隐私性的聚类算法「CI//第十

届中国科协年会论文集．北京：国防工业出版社，2008:7.

[15] Giannella CR,Liu K, Kargupta H.Breaching euclidean distance-preserving data perturbation using few known inputs [M].[S.1.]:Elsevier Science Publishers,2013.

[16] Achlioptas D.Database-friendly random projections [C]//Proc of the 20th ACM Sigmod-Sigact-Sigart Symposium on Principles of Database Systems. NewYork:ACMPress,2001:274-281

[17]刘杰，徐一凤，张健沛，等．面向隐私保护聚类的平面反射数据扰动方 法[J].计算机工程与应用,2013,49(6):135-138.   
[18]丘维声．解析几何[M].北京：北京大学出版社,2015:194-199.   
[19]Lakshmi MN.Privacy preserving clustering by hybrid data transformation approach [J]. International Journal of Emerging Technology and Advanced Engineering,2013,3(8): 2250-2459.