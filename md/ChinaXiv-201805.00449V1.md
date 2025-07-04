# 基于渗流理论的三维无线传感网络的渗流密度与覆盖节点密度研究

康琳，韩亚君，高文华(太原科技大学 电子信息工程学院，太原 030024)

摘要：为保证无线传感器网络的覆盖与连通，探索通信半径和感知半径的比值对三维无线传感网络覆盖与连通的影响，基于渗流理论，得到三维无线传感器网络中协作传输路径的重叠体积函数。考虑到通信半径和感知半径的比值与重叠体积函数的关系，得到重叠体积函数与通信半径和感知半径的比值对三维无线传感器网络渗流密度的影响。在此基础上，当通信半径和感知半径相等时，将得到的渗流密度与覆盖的节点密度结合，得到指定的覆盖率与覆盖的节点密度的关系。仿真实验证明，在三维无线传感器网络中，重叠体积与渗流密度成正比；通信半径和感知半径的比值与渗流密度成反比；随着指定的覆盖率的增加，所得到的覆盖的节点密度也随着增加。

关键词：无线传感器网络；三维覆盖；渗流密度；重叠体积函数 中图分类号：TP301 doi:10.3969/j.issn.1001-3695.2018.01.0175

# Study on seepage density and coverage node density of three dimensional wireless sensor networks based on seepage theory

Kang Lin, Han Yajun, Gao Wenhua (School ofElectronic Information Engineering,Taiyuan UniversityofScience &Technology,Taiyuan O3o24,China)

Abstract:In order to ensure thecoverage and connectivity of wireless sensor networks,the influence of theratioof communication radius to perceived radius on thecoverage and connectivityoftree-dimensional wirelesssensornetworks is explored.Basedontheseepagetheory,theoverlappingvoumefunctionsofcooperativetransmissonpathsinthree-dimensional wirelessensor networks are obtained.The relationship between theratioof communication radius and perceived radius to overlapped volume functionis obtained.Theinfluence oftheratioofoverlappedvolume functionto communication radius and perceivedradiusonthesepagedensityofthree-dimensional wirelesssensornetworks isobtained.Onthisbasis,when theradius ofcommunication andthe perceived radius areequal,the relationshipbetween seepage densityand node densityisobtained, andtherelationship between the specified coverage and node density is obtained.Simulationresults show thattheoverlap volume is proportionaltothe seepagedensityin three-dimensional wirelesssensor networks.Theratioof thecommunication radiustotheperceivedradius is inversely proportional totheseepagedensity.With the increaseofthe specified coverage,the node density of the covered nodes Increase.

Key words: wirelesssensor networks; three-dimensional coverage; density of seepage; overlapped volume function

# 0 引言

无线传感器网络有感知、计算和通信的能力，广泛应用于军事侦察、环境监测、基础设施、灾害搜救、设备诊断和其他工业应用[1-2]。在无线传感器网络中，节点又称为传感器，配有低电力电池，为了增加网络寿命，可以考虑减少节点的耗能。覆盖与连通可以为无线传感器网络提供更优质的服务，更加节省能量。

无线传感器网络中，运用最少的节点数达到最大的覆盖区域，是无线传感器网络一直以来研究的目标。Alam[3提出在实际通信中的三维随机覆盖连通问题，用最少的节点数保证 $100 \%$ 的覆盖，使三维覆盖问题得到系统化。在无线传感器网络的覆盖连通研究中，有许多模型：Wang[4研究了无线传感器网络三维晶格模型中的局部覆盖问题；Ammari[5]研究了三维无线传感器网络的球状模型的节点覆盖问题；在本文的研究中采用的是球状模型。在解决覆盖问题的研究中，Wang[ 提出一种带状的节点部署模式使区域得到覆盖；Wang[7运用节点要求率来表示随机三维无线传感器网络中的部署效率问题； $\mathrm { S u i ^ { [ 8 ] } }$ 提出差分进化算法优化传感器节点的分布；Dang[9,10]运用调度算法和邻节点分类调度算法提高节点部署效率；Gupta[1]运用异构定向解决三维无线传感器网络的随机覆盖与连通问题；Yan[12]提出一种改进的三维无线传感器部署算法；Broadbent[13]运用渗流理论解决无线传感器网络的连通问题。解决网络覆盖的方法很多，同时影响因素也很多。Pompili[14]研究了在三维无线传感器网络中几个基本性能对覆盖与连通性的影响，在此基础上，Adlakha[15]研究了无线传感器网络的覆盖与连通性与通信半径和感知半径比值之间的关系，在本文中也将考虑这两种因素，并对其进行分析。

本文研究了影响三维无线传感器网络覆盖与连通性能中的重叠覆盖体积函数与通信半径和感知半径的比值。运用几何学原理得到一个协作传输路径中的两个球的实际重叠体积函数，得到重叠体积函数与渗流密度间的关系，讨论在实际重叠体积函数下的渗流密度比近似重叠体积函数下的渗流密度小，实际重叠体积函数更具有优势。在此基础上，得到实际重叠体积函数与通信半径和感知半径的比值之间的关系，讨论了通信半径和感知半径的比值在1,2区间内，随着比值的增大，渗流密度逐渐减少，且在比值一定的情况下，重叠体积函数越小，渗流密度越小，更加具有优势。在此基础上，将重叠体积函数与覆盖的节点密度结合，得到指定的覆盖率与覆盖的节点密度的关系，随着指定的覆盖率的增加，覆盖的节点密度也随之增加。

# 1 定义与定理

定义1 空间泊松分布。 $X _ { \lambda } = \left\{ \xi _ { i } : i \geq 1 \right\}$ 是密度为 $\lambda$ 的三维空间的均匀泊松分布，其中 $\xi _ { i }$ 是中心为 $s _ { i }$ 的定向传感器[16]。

假设1单位球模型）[5]

传感器 $s _ { i }$ 的感知范围的半径为球的半径 $r$ ，由点的集合定义：

$$
B _ { i } \left( r \right) = \left\{ \xi \in I R ^ { 3 } : \left| \xi _ { i } - \xi \right| \leq r \right\}
$$

其中 $\left| \xi _ { i } - \xi \right|$ 为 $\xi _ { i }$ 与 $\xi$ 之间的欧氏距离。

传感器 $s _ { i }$ 的通信范围的半径为球的半径 $R$ ，由点的集合定义：

$$
B _ { i } \left( \boldsymbol { r } \right) = \left\{ \xi \in I R ^ { 3 } : \left| \xi _ { i } - \xi \right| \leq R \right\}
$$

假设2均匀传感模型[16]

所有部署的传感器具有相同的传感半径 $r$ 和相同的通信半

径 $R$ 。

定义2协作与通信传感器[13]。两个传感器 $s _ { i }$ 和 $s _ { j }$ 协作的条件是，当且仅当两个感知磁盘中心间的欧氏距离满足$\left| \xi _ { i } - \xi _ { j } \right| \leq 2 r$ ，即两个传感磁盘相切或重叠（如图1(a)所示）。协作的一组传感器 $s _ { i }$ ，用 $C o l { \left( s _ { i } \right) }$ 表示：

$$
C o l \left( \boldsymbol { s } _ { i } \right) = \left\{ \boldsymbol { \xi } _ { j } : \left. \boldsymbol { s } _ { i } - \boldsymbol { s } _ { j } \right. \leq 2 r \right\}
$$

两个传感器 $s _ { i }$ 和 $s _ { j }$ 通信的条件是，当且仅当两个感知磁盘中心间的欧氏距离满足 $\left| \xi _ { i } - \xi _ { j } \right| \leq R$ （如图1(b)所示）。通信的一组传感器 $s _ { i }$ ，用 $C o m { \left( s _ { i } \right) }$ 表示：

$$
C o m \big ( \boldsymbol { s } _ { i } \big ) = \Big \{ \boldsymbol { \xi } _ { j } : \big | \boldsymbol { s } _ { i } - \boldsymbol { s } _ { j } \Big | \leq R \Big \}
$$

![](images/1f3a6eb4a3b843e4593517b794fd40f9650445c3754082af7f05dfe1e3579bcd.jpg)  
图1(a)协作传感器

![](images/82b104746c6022183d6eebe99a06aacb1a278f4ce5db46b42b2b09121886e6d3.jpg)  
图1(b）通信传感器

定义3覆盖与连通传感器[16]。两个传感器 $s _ { i }$ 和 $s _ { j }$ 同时满足协作与通信的条件，才可达到覆盖与连通，如图2所示。

![](images/c79e8e5b22ba0b9e8e594f85940093d4987f7474b381e7e3c1bcf85f43b695b3.jpg)  
图2覆盖与连通传感器

定义4协作与传输路径[16]。两个传感器 $s _ { i }$ 和 $s _ { j }$ 之间的协作路径是一个传感器序列 $s _ { i } , s _ { i + 1 } , \cdots , s _ { j - 1 } , s _ { j }$ ，任何一对传感器 $s _ { l }$ 和 $s _ { l + 1 }$ 都可协作，其中 $i \leq l \leq j - 1$ （如图3(a)所示）。

两个传感器 $s _ { i }$ 和 ${ \boldsymbol { s } } _ { j }$ 之间的传输路径是一个传感器序列$s _ { i } , s _ { i + 1 } , \cdots , s _ { j - 1 } , s _ { j }$ ，任何一对传感器 $s _ { l }$ 和 $s _ { l + 1 }$ 都可通信，其中$i \leq l \leq j - 1$ （如图3(b)所示）。

![](images/bc13607dbf86374469d6c73ae367fc20fa9d978b5f2fbdea211b3d94d6e5eccd.jpg)  
图3(a)协作路径

![](images/4bf338058a8fded8325ca364dd0b0a01d6d4e79b2a55450b70bfbda7c744fdf2.jpg)  
图3(b）传输路径

定义5布尔模型[5]。布尔模型由两个部分组成，点过程$X _ { \lambda }$ 和连接函数 $h$ 。其中 $X _ { \lambda } = \left\{ \xi _ { i } : i \geq 1 \right\}$ 为三维欧几里得空间 $I R ^ { 3 }$ 中密度为 $\lambda$ 的均匀泊松过程。 $X _ { \lambda }$ 的原理是在定向传感器中覆盖一定的区域。连接函数 $h$ 是两个相邻的点 $\xi _ { i } , \xi _ { j }$ 之间满足：

当 $\left| \xi _ { i } - \xi _ { j } \right| \leq d$ 时， $h \big ( \big | \xi _ { i } - \xi _ { j } \big | \big ) = 1$ 当 $\left| \xi _ { i } - \xi _ { j } \right| > d$ 时， $h \left( \left| { \xi } _ { i } - { \xi } _ { j } \right| \right) = 0$ 。其中 $d \geq 0$ ， $\left| { \xi } _ { i } - { \xi } _ { j } \right|$ 为 $\xi _ { i }$ 与 $\xi _ { j }$ 之间的欧氏距离。

定理1覆盖与连通性的临界渗流密度[5]。在三维无线传感器网络中的临界渗流密度可以表示为

$$
\lambda _ { _ c } ( r , \omega _ { s } , \alpha ) = \frac { 0 . 9 5 5 } { \left( 1 - \omega _ { s } \right) \alpha ^ { 3 } r ^ { 3 } }
$$

其中： $R = \alpha r$ ，且 $1 \leq \alpha \leq 2$ ， $\omega _ { s } = V _ { \operatorname* { m i n } } / V _ { 0 }$ 。

定理2覆盖的节点密度。在边长为 $a$ 的三维监测区域内，达到指定覆盖率 $\phi$ 前提下，节点的覆盖区域所覆盖的节点数，用 $n$ 表示，是评价节点覆盖面积的一个重要的标准，即为该区域覆盖的节点密度。可以表示为[9]

$$
n = \frac { \mathrm { l g } \left( 1 - \phi \right) } { \mathrm { l g } \left( 1 - \omega _ { s } \right) }
$$

其中： $\phi$ 为指定的覆盖率，取值范围为[0,1]，其中$\omega _ { s } = V _ { s } / V _ { 0 }$ ， $V _ { s }$ 为重叠体积的最小值， $V _ { 0 }$ 为球体的体积。

# 2实际重叠体积函数

在实际生活中节点的传感范围是在三维空间中的，将一个节点的连通区域看作是一个球体，在保证覆盖连通条件的情况下，两个节点之间的距离 $d \leq R \ , \ R$ 为节点的连通半径。在一个节点对中，令一个节点位于三维坐标中的原点，另一个节点位于 $\mathbf { x }$ 轴的 $\mathtt { R }$ 处，则两个球体的函数可表示为

$$
x ^ { 2 } + y ^ { 2 } + z ^ { 2 } = R ^ { 2 }
$$

$$
\left( x - R \right) ^ { 2 } + y ^ { 2 } + z ^ { 2 } = R ^ { 2 }
$$

将（7）式代入（6）式可得：

$$
x ^ { 2 } + y ^ { 2 } + z ^ { 2 } = ( x - R ) ^ { 2 } + y ^ { 2 } + z ^ { 2 }
$$

即：

$$
x ^ { 2 } = \left( { \overset { } { x } { - } } R \right) ^ { 2 }
$$

可解得

$$
x = \frac { R } { 2 }
$$

两个球面交点的横坐标为 $R / 2$ ，交面平行于 $y z$ 平面。将 式(11)代入式(7)可得

$$
{ \frac { R ^ { 2 } } { 4 } } + y ^ { 2 } + z ^ { 2 } = R ^ { 2 } \boxplus y ^ { 2 } + z ^ { 2 } = { \frac { 3 R ^ { 2 } } { 4 } }
$$

式(12)是切面圆的方程，半径为 $\frac { \sqrt { 3 } R } { 2 }$

两个球体的重叠体积的实际值可以分为两个部分：a)两个圆锥（底面半径为 $\frac { R } { 2 }$ 高为 ${ \frac { { \sqrt { 3 } } R } { 2 } } \ \rangle$ ;b)球体减去两个圆台的剩余部分的 $\frac { 4 } { 6 }$ 。球体的半径为 $\mathtt { R }$ ，圆台的上底面半径为 $\frac { R } { 2 }$ 下底面半径为 $\mathtt { R }$ ，高为 $\frac { \sqrt { 3 } R } { 2 }$

两个球重叠的平面图为图4所示，其中第一部分的两个圆锥为图5所示，第二部分的计算为图6所示。

![](images/4d0092b1ccd862cc1ba25a1715c2ed5fa1310344dcd41ccba04836d9975c9dfe.jpg)  
图4两球重叠的平面图

![](images/0c6d1d61c6f04cd88274c618c5e6139bfef9446bb4c3934dec9f230407a4ac14.jpg)  
图5重叠区域第一部分的体积

![](images/58cd4f0b873b382eacb84ded8915122f301995fb56f0658b0b78550bd8b8b24c.jpg)  
图6重叠区域第二部分计算分析图

第一部分的体积可以用 $V _ { 1 }$ 表示为

$$
V _ { 1 } = 2 \times \left[ \frac { 1 } { 3 } \times \pi \times \left( \frac { R } { 2 } \right) ^ { 2 } \times \frac { \sqrt { 3 } R } { 2 } \right] = \frac { \sqrt { 3 } \pi R ^ { 2 } } { 1 2 }
$$

第二部分的体积的计算如下：

圆台的上底面的面积为 $S _ { \mathrm { \perp } }$ ：

$$
S _ { \mathrm { { \scriptsize ~ E } } } { = } \pi { \left( \frac { R } { 2 } \right) } ^ { 2 } = \frac { \pi R ^ { 2 } } { 4 }
$$

圆台的下底面的面积为 $S _ { \mathrm { { \bar { F } } } }$ ：

$$
S _ { \mathrm { { F } } } = \pi R ^ { 2 }
$$

圆台的体积可以表示为 $V _ { \perp | \lesseqgtr }$

$$
\begin{array} { l } { \displaystyle V _ { \mathrm { B G } , \oplus } = \frac { \left( S _ { \mathrm { { \scriptscriptstyle { E } } } } + S _ { \mathrm { { \scriptscriptstyle { F } } } } + \sqrt { S _ { \mathrm { { \scriptscriptstyle { E } } } } S _ { \mathrm { { \scriptscriptstyle { F } } } } } \right) \times h } { 3 } } \\ { \displaystyle = \frac { \left( \frac { \pi R ^ { 2 } } { 4 } + \pi R ^ { 2 } + \sqrt { \frac { \pi R ^ { 2 } } { 4 } \times \pi R ^ { 2 } } \right) \times \frac { \sqrt { 3 } R } { 2 } } { 3 } } \\ { \displaystyle = \frac { 7 \sqrt { 3 } \pi R ^ { 3 } } { 2 4 } } \end{array}
$$

球的体积为 $V _ { ☉ }$

$$
V _ { _ { ☉ } } \mathrm { = } \frac { 4 \pi R ^ { 2 } } { 3 }
$$

图6中除了两个圆台后的六个小区域的体积为：

$$
V _ { \mathrm { \scriptsize ~ \stackrel { . } { \cdot } \stackrel { . } { \cdot } \mathrm { \scriptsize ~ \downarrow } \mathrm { \scriptsize ~ \cdot } } } = V _ { \tt \oplus \tt \oplus } - 2 V _ { \tt \oplus \tt \oplus } =
$$

$$
\frac { 4 \pi R ^ { 2 } } { 3 } - 2 \times \frac { 7 \sqrt { 3 } \pi R ^ { 3 } } { 2 4 } = \frac { \left( 1 6 - 7 \sqrt { 3 } \right) \pi R ^ { 3 } } { 1 2 }
$$

一个小区域的体积为：

$$
V _ { , | \setminus } = \frac { V _ { \vec { \operatorname { \cap } } \times | \setminus } } { 6 } = \frac { \left( 1 6 - 7 \sqrt { 3 } \right) \pi R ^ { 3 } } { 7 2 }
$$

四个小区域的体积为：

$$
V _ { _ { \perp \parallel } , \parallel \setminus } = 4 \times V _ { , \parallel \setminus } = \frac { \left( 1 6 - 7 \sqrt { 3 } \right) \pi R ^ { 3 } } { 1 8 }
$$

因此重叠的最小的体积为：

$$
V _ { \mathrm { m i n } } = V _ { \mathrm { 1 } } + V _ { \mathrm { p q / \uparrow \mathrm { { h } } } } = \frac { \left( 3 2 \mathrm { { - 1 } } 1 \sqrt { 3 } \right) \pi R ^ { 3 } } { 3 6 }
$$

由式(5)可知，其中：

$$
V _ { 0 } = \frac { 4 \pi } { 3 } r ^ { 3 }
$$

可得：

$$
\omega _ { s \operatorname* { m i n } } = \frac { \left( 3 2 - 1 1 \sqrt { 3 } \right) } { 4 8 } \kappa ^ { 3 }
$$

式(5)中的未知数的取值范围为：

$$
\frac { \left( 3 2 - 1 1 \sqrt { 3 } \right) } { 4 8 } \kappa ^ { 3 } \leq \omega _ { s } < 1
$$

$$
1 \leq \kappa \leq 2
$$

# 2 数值结果分析

# 2.1 $R$ 与 $r$ 的比值对临界渗流密度的影响

令式(21)中 $R = 1$ ，得到连通情况下的重叠的最小的实际体积为

$$
V _ { _ { \mathrm { m i n } } } = \frac { 3 2 - 1 1 \sqrt { 3 } } { 3 6 } \pi
$$

得到

$$
\omega _ { s \mathrm { m i n } } = \frac { 3 2 - 1 1 \sqrt { 3 } } { 4 8 }
$$

得到此状态下的实际的渗流密度为

$$
\lambda _ { { \scriptscriptstyle c 1 } } = \frac { 0 . 9 5 5 } { 1 - \omega _ { s } } , \Re \# \# \frac { 3 2 - 1 1 \sqrt { 3 } } { 4 8 } \le \omega _ { s } < 1
$$

近似的渗流密度为[16]

$$
\lambda _ { _ { c 2 } } = \frac { 0 . 9 5 5 } { 1 - \omega _ { s } } , \# \# 0 . 3 1 2 5 \leq \omega _ { s } < 1
$$

图7中在渗流密度函数中左边的点为重叠体积的实际值将本文得到的实际的渗流密度与之前的近似渗流密度比较，得到如图7所示的仿真图。

y1 由式(28)得到，y2 由式(27)得到，其中实际值y2从左边的蓝线开始存在密度，近似值y1从右边的蓝线开始存在密度，即实际的重叠体积的最小值比近似的重叠体积的最小值小，得到的实际的渗流密度比近似的渗流密度小。

如图8中，随着重叠体积分数的增加，渗流密度减小，y1，y2，y3，y4中，重叠体积分数逐渐增大，但是渗流密度减小；并且随着 $R$ 与 $r$ 比值的增大，渗流密度减小。图中y1为实际的重叠体积分数，y2为近似的重叠体积分数，y3的重叠体积分数为0.5，y4的重叠体积分数为0.75。实际值的密度相比近似值及其他，其密度都小，因而更具有优势。

![](images/e85b2abf192a62cfe4e9497e29a47b9c14b9978fc2eefc06a04bcb66fc9763cf.jpg)  
图7临界渗流密度随体积分数的变化图

![](images/aeca91c9327656b153bbaf320ea39a8c3729bd79b4a3a38d6f60253d5f733352.jpg)  
图8R与r的比值对临界渗流密度的影响

# 2.2覆盖的节点密度

由式(7) (25) (26)可得实际的最小的重叠体积下的覆盖的节点密度为

$$
n _ { \mathrm { m i n } } = \frac { \displaystyle \log \left( 1 - \phi \right) } { \displaystyle \log \left( 1 - \omega _ { s _ { \mathrm { m i n } } } \right) } = \frac { \displaystyle \lg \left( 1 - \phi \right) } { \displaystyle \lg \left( 1 - \frac { 3 2 - 1 1 \sqrt { 3 } } { 4 8 } \right) } = \frac { \displaystyle \lg \left( 1 - \phi \right) } { \displaystyle \lg \left( \frac { 1 6 + 1 1 \sqrt { 3 } } { 4 8 } \right) } { \displaystyle \lg \left( 1 - \frac { 3 2 - 1 1 \sqrt { 3 } } { 4 8 } \right) } { \displaystyle \lg \left( 1 - \frac { 3 2 - 1 1 \sqrt { 3 } } { 4 8 } \right) } ,
$$

近似的重叠体积的覆盖的节点密度可以表示为

$$
V _ { _ { s 0 } } = { \frac { 5 } { 1 2 } } \pi r ^ { 3 } \omega _ { _ { s 0 } } = { \frac { 1 5 } { 4 8 } }
$$

$$
n _ { 0 } = \frac { \lg ( 1 - \phi ) } { \lg ( 1 - \omega _ { s 0 } ) } = \frac { \lg ( 1 - \phi ) } { \lg \left( 1 - \displaystyle \frac { 1 5 } { 4 8 } \right) } = \frac { \lg \left( 1 - \phi \right) } { \lg \left( \displaystyle \frac { 3 3 } { 4 8 } \right) }
$$

由式(29)(30)可得如图9所示的仿真结果图。图9中y1为在我所得到的实际的重叠体积下的渗流密度中，指定的覆盖率与覆盖的节点密度间的关系，y2为近似的重叠体积得到的渗流密度中指定的覆盖率与覆盖的节点密度间的关系，当指定的覆盖率在[0,1]区间内，随着指定覆盖率的逐步增加，覆盖的节点密度也随之增加，y1与y2相比，y1的增长速度比y2快，因此在相同的指定的覆盖率的情况下，y1的覆盖的节点密度比 y2大，因此y1情况下所得到的重叠体积的方法比y2更加具有优势。

![](images/aee4d5a726b0a638397a6c5fc5880039ef8e6ba463344934a8bfc8f473d98007.jpg)  
图9指定的覆盖率与覆盖的节点密度关系

在对于覆盖的节点密度的计算中，文献[9]中对协作传输路径的两节点间的距离分为两种情况，分别为： ${ \frac { 1 } { 2 } } r$ 与貨 $\frac { 3 } { 2 } r$ ，在这两种情况下得到的覆盖的节点密度可以分别表示为：

当两节点间的距离为 ${ \frac { 1 } { 2 } } r$ 时，重叠体积可以计算为

$$
V _ { \mathrm { 1 } } = { \frac { 2 } { 3 } } \pi { \left( r - { \frac { 1 } { 2 } } r \right) } ^ { 2 } { \left( 2 r + { \frac { 1 } { 2 } } r \right) } = { \frac { 2 7 } { 3 2 } } \pi r ^ { 3 }
$$

由式(5)可得

$$
\omega _ { s 1 } = { \frac { V _ { 1 } } { V _ { 0 } } } = { \frac { \frac { 2 7 } { 3 2 } \pi r ^ { 3 } } { \frac { 4 } { 3 } \pi r ^ { 3 } } } = { \frac { 8 1 } { 1 2 8 } }
$$

由式(6)(31)(32)可得指定的覆盖率与覆盖的节点密度间的关系为

$$
n _ { 1 } = \frac { \mathrm { l g } \left( 1 - \phi \right) } { \mathrm { l g } \left( 1 - \omega _ { s 1 } \right) } = \frac { \mathrm { l g } \left( 1 - \phi \right) } { \mathrm { l g } \left( 1 - \displaystyle \frac { 8 1 } { 1 2 8 } \right) } = \frac { \mathrm { l g } \left( 1 - \phi \right) } { \mathrm { l g } \left( \displaystyle \frac { 4 7 } { 1 2 8 } \right) }
$$

当两节点间的距离为 $\frac { 3 } { 2 } r$ 时，重叠体积可以计算为

$$
V _ { 2 } = \frac { 2 } { 3 } \pi \left( r - \frac { 3 } { 2 } r \right) ^ { 2 } \left( \cfrac { 3 } { 2 r + \frac { 2 } { 2 } } r \right) = \frac { 1 1 } { 9 6 } \pi r ^ { 3 }
$$

由式(5)可得：

$$
\omega _ { s 2 } = { \frac { V _ { 2 } } { V _ { 0 } } } = { \frac { \displaystyle { \frac { 1 1 } { 9 6 } } \pi r ^ { 3 } } { \displaystyle { \frac { 4 } { 3 } } \pi r ^ { 3 } } } = { \frac { 1 1 } { 3 2 } }
$$

由式(6)(34)(35)可得指定的覆盖率与覆盖的节点密度间的关系为

$$
n _ { 2 } = \frac { \lg \left( 1 - \phi \right) } { \lg \left( 1 - \omega _ { s 2 } \right) } = \frac { \lg \left( 1 - \phi \right) } { \lg \left( 1 - \displaystyle \frac { 1 1 } { 3 2 } \right) } = \frac { \lg \left( 1 - \phi \right) } { \lg \left( \displaystyle \frac { 2 1 } { 3 2 } \right) }
$$

由式(29)(33)(36)可得如图10所示的仿真结果，在图10中，y1为所得到的覆盖的节点密度，y2为两节点间的距离为 ${ \frac { 1 } { 2 } } r$ 时的覆盖的节点密度，y3 为两节点间的距离为 $\frac { 3 } { 2 } r$ 时的覆盖的节点密度。当指定的覆盖率在1,2内时，随着指定的覆盖率的逐步增加，覆盖的节点密度也随之增加，在这三种情况下，y1的增加速度比y2、y3大，即在相同的指定的覆盖率的情况下，y1得到的覆盖的节点密度最大，因此y1更加具有优势。

![](images/a51809737953d2bb6a8cad7a4d52d752881cd8864f39b7f887988bc071e4a114.jpg)  
图10三种情况下的指定覆盖率与覆盖的节点密度间关系通过图9、10的数值结果比较，在相同的指定的覆盖率的清况下，所得到的覆盖的节点密度最大，因此最具有优势。

# 3 结束语

本文研究了三维无线传感器网络的覆盖与连通问题，考虑到影响三维无线传感器网络渗流密度的因素，重叠体积函数与通信半径和感知半径的比值。通过对实际的重叠体积函数的计算，与近似的重叠体积进行比较，实际的重叠体积比近似的重叠体积更小，得到的渗流密度更小，更具有优势；在[1,2]内，通信半径和感知半径的比值对渗流密度的影响更加显著，随着比值的增大，渗流密度逐渐减小，与渗流密度成反比。且随着指定的覆盖率的增加，覆盖的节点密度也随之增加。可得在得到的实际重叠体积函数的情况下，在一定的目标区域内，用最少的节点数可将目标区域达到覆盖与连通。

# 参考文献：

[1]Yun Ziqiu,Bai Xiaole, Xuan Dong,et al. Optimal deployment patterns for full coverage and $\mathbf { k }$ -connectivity $\mathrm { k } \leqslant \ 6 ,$ ）wireless sensor networks [J]. IEEE//ACM Trans on Networking,2010,18 (3): 934-947.   
[2]Solmaz G,Turgut D. Tracking pedestrians and emergent events in disaster areas [J]. Journal of Network & Computer Applications,2017,84: 55-67.   
[3]Alam S M N,Haas ZJ.Coverage and connectivity in three-dimensional networks with rondow node deployment [J].Ad Hoc Network,2015,34: 157-169.   
[4]Wang Yun,Chu William, Xiao Zhifeng,et al.Partial sensing coverage in 3D wireless lattce sensor networks [C]// Proc ofIEEE International Conference on Communications. 2014: 24-29.   
[5]Ammari H M,Das S K. Critical density for coverage and connectivity in three-dimensional wireles sensor networks using continuum percolation[J]. IEEE Sensors Jourmal,2015,57(6):169-181.   
[6]Wang Bang, Xu Han,Liu Wenyu,et al. The optimal node placement for long belt coverage in wireless networks [J].IEEE Trans on Computers,2015,64 (2): 587-592.   
[7]Wang Yun. Over provisioning rate in thre-dimensional wireless sensor networks for partial sensing coverage [C]/ Proc of IEEE International Conference on Computational Intelligence and Virtual Environments for Measurement Systems and Applications. 2015: 1-6.   
[8] 孙顺远，孙丽，陈树．三维环境下无线传感器网络的部署覆盖方法[J]. 吉林大学学报：理学版,2016,54(5):1109-116. (Sun Shunyuan Sun Li, Chen Shu. 3D environment to the deployment of wireless sensor network coverage method [J].Journal of Jilin University: Science Edition,2016,54 (5): 1109-1116.   
[9] 党小超，蒲世强，郝占军．基于相对局部密度的三维节点调度算法[J]. 计算机工程与应用,2016,52(20):132-137.Dang Xiaochao,Pu Shiqiang, Hao Zhanjun. Three-dimensional node scheduling algorithm based on relative local density[J]. ComputerEngineering And Application,2016, 52 (20): 132-137.   
[10]党小超，蒲世强，郝占军．一种三维无线传感器网络节点调度算法[J]. 计算机工程与应用,2016,52(7):117-121.Dang Xiaochao,uShiqiag, Hao Zhanjun.A three-dimensional wirelessensor network node scheduling algorithm[J].Computer Engineering and Application,2016,52(7): 117-121   
[11] Gupta H P,Rao S V, Venkatesh T.Analysis of stochastic coverage and connectivity in three-dimensional heterogeneous directional wireless sensor networks [J].Pervasive & Mobile Computing,2016,29 (C): 38-56.   
[121 Xn Van 7huang Vi Gu linging An imnrnved 3D lncalizatin algnrithm far

the wireless sensor network [J].International Journal of Distributed Sensor Networks,2015,2015:98.   
[13]Broadbent S R,Hammersley JM.Percolation processes:I.Crystals and mazes [C]// Proc of the Cambridge Philosophical Society. Cambridge University Press,1957,53 (3): 629-641.   
[14]Ravelomanana V.Extremal properties of three-dimensional sensor networks with applications [J].IEEE Trans on Mobile Computing,2004,3(3):246- 257.   
[15] Xing Guoliang,Wang Xiaorui, Zhang Yuanfang,et al. Integrated coverage and connectivity configuration for energy conservation in sensor networks [J].ACM Trans on Sensor Networks,2005,1(1): 36-72.   
[16]Ammari HM,Das SK.Integrated coverage and connectivity in wireless sensor networks:a two-dimensional percolation problem [J].IEEE Trans on Computers,2008,57(10):1423-1434.