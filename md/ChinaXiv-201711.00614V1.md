# 槽式集热器聚光过程误差因素耦合研究

王志　赵力　赵晴　卢培　邓帅（中低温热能高效利用教育部重点实验室，天津大学，天津300072）

摘要在实际运行过程中，槽式太阳能集热器的聚光过程可能受到太阳光入射角、安装误差、镜面误差和跟踪误差等各种实际因素的影响。本文用空间坐标变换的方法结合蒙特卡罗光线追踪法，分别计算出了各种实际因素单独存在时和多种实际因素耦合时的槽式集热器热流分布。结果显示，安装误差和跟踪误差使聚焦热流的不均匀性增大，镜面误差使聚焦热流的不均匀性减小；计算出的实际因素耦合热流分布，可以为槽式集热器光学性能和热性能的分析提供依据。

关键词 槽式集热器；聚光过程；热流分布；光学误差中图分类号： 文献标识码： 文献编号：

# Investigation on coupled optical factors of concentration process in parabolic trough collectors

Wang ZhiZhao Li Zhao Qing Lu Pei Deng Shuai (KeyLaboratoryofEficient UtilizationofLowandMediumGrade EnergyTianjinUniversityTianjin30o72,China) Abstract The concentration processofa parabolic trough colector canbe affected by incidence angle,instalation error,reflector slope error and tracking error in operation.The coordinate transformation method and the Monte Carlo Ray Trace method are integrated to compute heat flux distributions under individual and coupled optical errors respectively in thisstudy.Itisshown that installation errorandtracking error increase the non-uniformityof the heat flux distribution while reflector slope eror tends to decrease it.Besides,the heat flux distribution under coupled optical errors can provide foundations for thermal and optical analysis of parabolic trough collectors.

Key Words parabolic trough collector; concentration process; flux distribution; optical factor

# 0引言

槽式太阳能集热器（PTC）是太阳能热发电的一种重要方式，在对PTC进行研究时，集热管外聚焦热流的计算常常是第一步。何雅玲[1使用蒙特卡罗光线追踪法（MCRT)计算了理想情况下PTC的聚焦热流，证明了MCRT方法的实用性，MCRT方法得到了广泛的应用[2-3]。与理想情况相比，PTC的聚光过程受到各种实际因素包括太阳光入射角、安装误差、跟踪误差和镜面误差的影响。赵东明等[4]采用空间坐标变换的方式研究了集热管安装误差、跟踪误差和太阳光入射角对 PTC 聚焦热流的影响，程泽东等[5]对镜面误差和跟踪误差进行了详尽的敏感性分析，均发现当这些实际因素存在时，聚焦热流将发生很大的改变，因此需要对各种实际因素存在时PTC的集热管外聚焦热流进行研究。

目前的文献常常只计算出只有一种实际因素存在时的PTC聚焦热流，而实际应用中，PTC的聚光过程可能会同时受到多种实际因素的影响。本文先计算各种实际因素单单独存在时PTC的聚焦热流并进行分析，然后在MCRT方法的基础上使用空间坐标转换，计算出多种实际因素耦合时的聚焦热流。

# 1.1热流分布模拟方法

图1是槽式集热器的示意图，为简便起见没有画出玻璃管。反射镜张口宽度、焦距和集热器长度分别用 $w , f$ 和 $L$ 表示，坐标原点建立在吸热管的进□截面圆心。

MCRT方法的细节见文献[1].在MCRT方法中，假如入射光线方向向量为 $\mathbf { \Pi } _ { M } ^ { \mathbf { u } }$ ，反射面的法向量为山$N$ ，那么反射光线方向向量 $\breve { P }$ 的计算公式为：

$$
\stackrel { \mathbf { u } } { P } = - 2 \big ( \stackrel { \mathbf { u } \mathbf { u } } { N } \cdot \stackrel { \mathbf { u } \mathbf { u } } { M } \big ) \stackrel { \mathbf { u } \mathbf { u } } { N } + \stackrel { \mathbf { u } \mathbf { u } } { M }
$$

各种实际因素实际上是对集热管位置、入射光线或镜面法线方向产生影响，在MCRT的算法中，这三者间互不干涉。为了研究各种因素的影响，只需要改变集热管的位置，或用空间坐标变换的方法计算新的 $\overset { \vartriangle } { M }$ 或N即可。

![](images/7fd7bc31475e8003d8b25cfdda31c2cd0c0637426926347bc9ce9d5261ba17a6.jpg)  
(a)截面示意图

# 1 模型描述

![](images/1e8371925533813ec757c7e8b8669af41675a928338804a06008b99bc3e54b48.jpg)  
图1槽式集热器示意图 Fig.1. Schematic of a PTC(a) cross sectional view (b) 3D view

# 1.2安装误差

当集热管的安装误差使吸热管的位置发生平移时，假设管子圆心线在 $y$ 和 $z$ 方向新的坐标分别为$y _ { I }$ 和 $z _ { I }$ ，则吸热管外壁方程变为：

$$
\left( y - y _ { 1 } \right) ^ { 2 } + \left( z - z _ { 1 } \right) ^ { 2 } = r ^ { 2 }
$$

$\boldsymbol { r }$ 是吸热管的外壁半径。集热管安装误差或者支撑架的形变也可能会造成集热管的位置与焦点线不平行。当PTC采用双轴跟踪系统时，光子被吸热管接收位置的 $x$ 坐标等于镜面上入射点的 $x$ 坐标（用$x _ { 0 }$ 表示)，所以只要知道吸热管中心线的坐标方程，光子到达吸热管的位置仍然可以求出来。

简单起见，假设吸热管的进口截面圆心坐标为(0,0,0)，出口截面圆心坐标为 $( \mathrm { L } , \boldsymbol { y } _ { I } , z _ { I } )$ ，那么在反射光线所在的垂直于焦点线的平面内，吸热管外壁的坐标方程为：

$$
\left( y - { \frac { x _ { 0 } } { L } } y _ { 1 } \right) ^ { 2 } + \left( z - { \frac { x _ { 0 } } { L } } z _ { 1 } \right) ^ { 2 } = r ^ { 2 }
$$

将吸热管新的坐标方程(2)或(3)代入MCRT算法中，保持其他部分不变，即可求得有集热管安装误差的管外不均匀热流分布。

对于单轴跟踪系统，由于入射角的存在，反射光线和集热管外壁的交点不易确定，情况更为复杂，本文不作研究。

# 1.3太阳光入射角

PTC对太阳位置的跟踪有单轴跟踪和双轴跟踪两种，只有双轴跟踪系统才能使太阳光线保持直射入射，但是由于双轴跟踪系统结构复杂，工程实际中PTC一般采取单轴跟踪系统，这种情况下入射太阳入射角往往不为 $0 ^ { \circ }$ ，如图2所示。

太阳光线 $A B$ 以入射角 $\theta$ 照射到反射镜边缘上的点 $B$ ，然后被反射到吸热管上的点 $c$ ，距离 $C D$ 即为经过 $B$ 点的太阳光线不能照射到的长度。文献[求出$C D$ 的最大值和最小值分别为

$$
L _ { \mathrm { m a x } } = \left( f + { \frac { w ^ { 2 } } { 1 6 f } } \right) \tan \theta
$$

$$
L _ { \mathrm { m i n } } = f \tan \theta
$$

$L _ { \mathrm { m a x } }$ 是PTC末端损失效应能够影响到的最大距离，即与末端 $D$ 距离大于 $L _ { \mathrm { m a x } }$ 的区域总的聚焦热流不变，而与末端 $D$ 距离小于 $L _ { \mathrm { m i n } }$ 的管段则不能接收到反射后的太阳光。

![](images/22aa54d71f308d161b8939a996eec53e08dda648a3e45eb1192e4a2b9e8519e3.jpg)

图3(a)中光线1是MCRT法计算出来的直射入射光线，光线2是入射角为 $\theta$ 的斜射入射光线。图3(b)中的坐标系 $0 { - } x ^ { \prime } y ^ { \prime } z$ 是坐标系 $o$ -xyz绕 $y$ 轴旋转角度 $\theta$ 后得到的，光线1在此坐标系中的坐标就是光线2在坐标系 $o$ -xyz中的坐标，用 $\mathbf { \Pi } _ { M ^ { \prime } } ^ { \mathrm { u u } }$ 在表示，则：

$$
M ^ { \prime } { = } A \cdot M
$$

![](images/48c2fe6d40b0ccc09213fe1502c9b88f0e3b9f961ade6ce22ed363e0c32e1531.jpg)  
Fig.2.Diagram of an incident ray on the sun-facing end of the reflector

其中 $A$ 是从坐标系 $- { O } _ { -  { x }  { y } z }$ 到坐标系 $0 { - } x ^ { \prime } y ^ { \prime } z$ 的空间坐标变换矩阵：

$$
A = \left[ \begin{array} { c c c } { \cos \theta } & { 0 } & { \sin \theta } \\ { 0 } & { 1 } & { 0 } \\ { - \sin \theta } & { 0 } & { \cos \theta } \end{array} \right]
$$

将得出的 $\overset {  } { M ^ { \prime } }$ 代入公式(1)中，保持其他部分不变，即可求得太阳光入射角不等于 $0 ^ { \circ }$ 时的热流分布。

(a）直射入射光线1和斜射入射光线2

![](images/f964bd06ebecc4fdf40a9720c981dc7edf83b1483386dd4eef98a68951ab0b4c.jpg)  
图2 太阳光斜射入射图  
图3单轴系统太阳光入射角坐标计算  
Fig.3.The calculation of the incident direction of a single-axis PTC(a) different incident conditions where ray1is the vertical incident ray and ray 2is the oblique incident ray (b) the coordinate transformation for the incidence angle $\theta$

# 1.4跟踪误差

跟踪误差是由于跟踪不准确导致的集热器位置的偏差，如图4(a)所示。由于跟踪误差的存在，集热器1相对于正确的位置（集热器2）逆时针旋转了 $\beta$ 角度。如图4(b)所示，空间坐标变换矩阵等于：

$$
B = \left[ { \begin{array} { c c c } { 1 } & { 0 } & { 0 } \\ { 0 } & { \cos \beta } & { \sin \beta } \\ { 0 } & { - \sin \beta } & { \cos \beta } \end{array} } \right]
$$

则修正后的入射光线坐标 $\mathbf { \Pi } _ { M ^ { \prime } } ^ { \mathrm { u u } }$ 为：

$$
\overrightarrow { M ^ { \prime } } = B \cdot \overrightarrow { M }
$$

将得出的 $\mathbf { \Pi } _ { M ^ { \prime } } ^ { \mathrm { u u u } }$ 代入公式(1)中，保持其他部分不变，即可求得有跟踪误差的热流分布。

![](images/8d5cf0cc220365c3c6279d35b25d078d3143255a7f3c86314d8f22a4adb74026.jpg)  
图4跟踪误差及其坐标变换  
Fig.4 Tracking error and its coordinate transformation (a) diagram of tracking error (b) the coordinate transformation for the tracking error $\beta$

# 1.5镜面误差

镜面误差考虑的是反射面微观的缺陷或宏观的变形等原因所造成的反射误差。镜面误差包含的种类很多，把所有的镜面误差叠加起来后可以用实际的与理想的镜面法线方向的偏差来代替[7]，认为此偏差角度在 $x$ 方向和 $y$ 方向分解后得到的两个分量分别符合相同的高斯分布[8]，镜面实际法线坐标向量 $\mathbf { \Pi } _ { N ^ { \prime } } ^ { \mathbf { u u } }$ 可以由理想的镜面法线方向 $N$ 经过两次坐标变换得到：

$$
\overset { \mathbf { u } } { N ^ { \prime } } = \boldsymbol { B } \cdot \left( \boldsymbol { A } \cdot \overset { \mathbf { u } } { N } \right)
$$

其中 $A$ 和 $B$ 用公式(7)和(8)来计算，公式中的角度 $\theta$ 和 $\beta$ 的概率密度函数相同：

$$
\theta = { \frac { 1 } { \sqrt { 2 \pi } \sigma } } \mathrm { e x p } \left( - { \frac { x ^ { 2 } } { 2 \sigma ^ { 2 } } } \right)
$$

$$
\beta = \frac { 1 } { \sqrt { 2 \pi } \sigma } \mathrm { e x p } \left( - \frac { x ^ { 2 } } { 2 \sigma ^ { 2 } } \right)
$$

$\sigma$ 是标准方差，也是镜面误差角度。将得出的 $_ { N ^ { \prime } } ^ { \mathbf { u u } }$ 代入公式(1)中，保持其他部分不变，即可求得有镜面误差的热流分布。

# 1.6实际因素耦合

对于安装误差，与理想模型相比，吸热管坐标发生了变化，用式(2)或式(3)来考虑其影响即可。对于跟踪误差、镜面误差、太阳光入射角等实际因素，可以用以下公式计算反射光线方向：

$$
\begin{array} { r } { \overset { \mathbf { u } } { P } = - 2 \Big ( \overset { \mathbf { u u } } { N ^ { \prime } } \cdot \overset { \mathbf { u u } } { M ^ { \prime } } \Big ) \overset { \mathbf { u u } } { N ^ { \prime } } + \overset { \mathbf { u u } } { M ^ { \prime } } } \end{array}
$$

其中 $\mathsf { \Pi } _ { N ^ { \prime } } ^ { \mathbf { u } }$ 和 $\overrightharpoon { M ^ { \prime } }$ 分别是考虑了跟踪误差、镜面误差和太阳光入射角等因素的实际反射镜法线和实际入射光线坐标向量。

需要注意的是，由于矩阵乘法不满足交换律，所以坐标变换的顺序不是随意的。例如，当同时考虑入射角影响和跟踪误差时，实际入射光线坐标 $\mathbf { \Pi } _ { M ^ { ' } } ^ { \mathrm { u u } }$ 为：

$$
\stackrel { \mathrm { u u u } } { M ^ { \prime } } = B \cdot \left( A \cdot M \right)
$$

采用 $\stackrel { \mathrm { u u u } } { M ^ { \prime } } = B \cdot \left( \ A \cdot \stackrel { \mathrm { u u } } { M } \right)$ 或 $\stackrel { \mathrm { \tiny ~ u u m } } { M ^ { \prime } } = A \cdot \left( B \cdot M \right)$ 得到的结果并不一样。矩阵 $A$ 把直射光线转变为斜射入射光线，矩阵 $B$ 考虑跟踪误差，考虑到实际过程，应该采取 $\stackrel { \mathrm { u u u } } { M ^ { \prime } } = B \cdot \left( A \cdot \stackrel { \mathrm { u u } } { M } \right)$ 来计算跟踪误差存在时单轴跟踪系统的热流分布。

# 2结果与讨论

下面利用空间坐标变换矩阵，对安装误差、太阳光入射角度等实际因素分别进行模拟和分析，最后将多种实际因素耦合在一起计算。因为管外热流分布的相对大小与直射辐射强度没有关系，所以分析结果时管外热流取的是当地聚焦比（LCR)。本文模拟时采用LS-3型槽式太阳能集热器作为物理模型，几何尺寸等参数见表1。关于其他型号集热器的结论可以通过用相同的方法分析得到。

表1LS-3槽式集热器数据  
Table1 Parameters of the LS-3 PTC   

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>吸热管半径/m</td><td>0.035</td></tr><tr><td>焦距/m</td><td>1.71</td></tr><tr><td>反射镜张口宽度/m</td><td>5.76</td></tr><tr><td>玻璃管透射率</td><td>0.95</td></tr><tr><td>吸热管吸收率</td><td>0.96</td></tr><tr><td>反射镜反射率</td><td>0.93</td></tr></table></body></html>

# 2.1安装误差的影响

$y$ 方向和z方向安装误差的定义分别为[4]： $Y { = } y _ { I } / w$ 和 $\scriptstyle { Z = z _ { I } / f _ { \circ } }$ 图5中显示的是平移安装误差下的热流分布。集热管安装误差达到毫米数量级时，管外热流形状就已发生明显改变。图6和图7比较了两方向安装误差都存在时 $y$ 或z方向安装误差对管外热流分布的影响。图6保持Z不变改变Y的大小，热流分布形状的改变非常大；图7保持Y不变改变Z的大小，热流分布形状的改变相对较小。因此，与z方向安装误差相比，y方向安装误差的影响大。所以，在集热管的安装过程中要格外注意减少在 $y$ 方向的安装误差。

![](images/c4e9d71624e8ce2c02072056d001e654fd4898b86865b6eb2db1d01765cd92d7.jpg)

![](images/81733d3eac23067be6d0885cdb53e059dded03406461c17101233c6ece6af221.jpg)  
Fig.5Flux distributions for installation errors(a) z direction installation errors (b) $y$ direction installation errors

![](images/8df0c9bf7db7aece48ef809199c07152870323c6d6031d48085630184c8dec3c.jpg)  
(b) $Z { = } 0 . 5 \%$ 图 $_ { 6 Z }$ 相同时不同 $Y$ 对聚焦热流的影响 g. 6 Flux distributions for different $Y$ when $Z$ is constant (a $Z { = } 0 . 2 \%$ (b) $Z { = } 0 . 5 \%$   
图 $7 ~ Y$ 相同时不同 $Z$ 的影响Fig.7Flux distributions for different $Z$ when $Y$ is constant (a)$Y { = } 0 . 2 \%$ (b) $Y { = } 0 . 5 \%$

图8显示的是不平行安装对热流分布的影响。集热管进口截面圆心坐标为(0.0.0)，出口截面圆心坐标为 $( 4 , y _ { I } , z _ { I } )$ ，其中 $y _ { I }$ 和 $z _ { I }$ 分别对应 $Y { = } 0 . 1 \%$ 和$Z { = } 0 . 1 \%$ 。虽然图中热流分布在轴线上是不均匀的，但可以看成无数个平移安装误差的热流分布连续排布而成。

![](images/5fda9ef13608708fe8b3e9d2fde3c0627c723f3de144fe0107c8d58dbee5cade.jpg)  
(b) $y$ 方向安装误差图5平行安装误差下的热流分布  
图8出口截面 $Y { = } 0 . 1 \%$ ， $\scriptstyle z = 0 . 1 \%$ 热流分布 Fig.8 Flux distributions in case of $Y { = } 0 . 1 \%$ and $Z { = } 0 . 1 \%$ for

# 2.2入射角的影响

图9(a)显示的是直射辐射强度相同时双轴跟踪和单轴跟踪系统热流沿管长的分布，纵轴为截面吸收的总能量。对于单轴跟踪的系统，图中画出了 $L _ { \mathrm { m a x } }$ 和 $L _ { \mathrm { m i n } }$ 的位置，可以看到MCRT方法模拟的结果和公式计算结果吻合得很好，证明了MCRT方法对太阳光斜射入射时热流分布模拟的准确性。在不受末端损失效应影响的区域，集热管每个截面接收的总的聚焦热流等于太阳光以相等的直射辐射强度直射入射时接收的聚焦热流，且在轴向上仍然可以认为是不变的。从图9(b)中可以看到，在集热管末端，吸热管接收到的聚焦能量从零开始连续地增大，最终成为周向不均匀、轴向上不变的聚焦热流。

![](images/532f32674a35769b8b576c19309f1a0726b4602348f5f653ac310bcca1c9f2d5.jpg)

# 2.3镜面误差和跟踪误差影响

图10显示的是镜面误差对聚光过程的影响。从图10(a)可以看出，周向热流分布仍然是对称的，镜面误差的作用是使聚焦热流由不均匀趋向均匀，这种作用有利于减小管壁温差，且镜面误差越大越明显。图10(b)显示的是镜面误差角度对未受末端损失影响区域的拦截系数的影响，当镜面误差大于 $0 . 1 2 ^ { \circ }$ 时，PTC的拦截系数小于1，应该避免这种情况。

图11显示的是跟踪误差对聚光过程的影响。从图11(a)可以看出，跟踪误差使太阳光偏离垂直于反射镜张口平面的方向入射，增大了热流的不均匀性。图11(b)显示的是跟踪误差角度对未受末端损失影响区域的拦截系数的影响，当跟踪误差大于 $0 . 6 ^ { \circ }$ 时，拦

截系数小于1。

![](images/4db98656ad286b49d5a80acc7e4e3af47fccfcb61ba0d5d1e47a2fc417a7d64d.jpg)  
(b)镜面误差对拦截系数的影响 图10镜面误差对聚光过程的影响 Fig.10 Effects of reflector slope error on concentration process (a) circumferential heat flux distributions (b) variation of the intercept factor

![](images/076904d16d94424772c1dc9711425984ac259c15ac1bb604039e1be220e220fa.jpg)  
图9太阳光 $3 0 ^ { \circ }$ 入射角热流分布 Fig.9 Flux distributions at $3 0 ^ { \circ }$ incidence angle (a) axial distribution (b) 3D distribution   
(b）跟踪误差对拦截系数的影响 图11跟踪误差对聚光过程的影响 .11 Effects of tracking error on concentration process (a)

circumferential heat flux distributions(b) variation of the intercept factor

# 2.4实际因素耦合

![](images/3651d0a4b4753b0b3f484bb896767474cc0b3f83a2b235bad9493cf722ba97ee.jpg)  
(b）周向热流分布 图12 太阳光入射角 $3 0 ^ { \circ }$ ， $Y { = } 0 . 1 \%$ ， $Z { = } 0 . 1 \%$ ，跟踪误差 $0 . 2 ^ { \circ }$ 镜面误差 $0 . 1 ^ { \circ }$ 时的热流分布 Fig.12 Flux distributions in case of $3 0 ^ { \circ }$ incidence angle, $\scriptstyle Y = 0 . 1 \%$ ， $Z { = } 0 . 1 \%$ ， $0 . 2 ^ { \circ }$ tracking error and $0 . 1 ^ { \circ }$ reflector slope error(a) 3Ddistribution (b) circumferential distribution

图12显示了多种实际因素耦合时的热流分布，太阳光入射角为 $3 0 ^ { \circ }$ ， $Y { = } 0 . 1 \%$ ， $Z { = } 0 . 1 \%$ ，跟踪误差为 $0 . 2 ^ { \circ }$ ，镜面误差为 $0 . 1 ^ { \circ }$ 。图12(b)显示的是未受末端损失影响区域的周向热流。由于各种实际误差角度的大小不一，所以管外聚焦热流的形状变化多样，可以计算出集热管外实际因素耦合的热流分布，从而为管内三维温度场的计算提供依据。

# 3结论

本文分别分析了集热管安装误差、太阳光入射角、镜面误差和跟踪误差等实际因素对PTC热流分布的影响，计算出了多种实际因素耦合时的PTC热流分布，得出了以下结论；

1）集热管安装误差达到毫米数量级时，聚焦热流形状就已发生明显改变，y方向的安装误差比z方向对热流分布影响更大，集热管安装过程中要格外注意减少在y方向的安装误差；

2）在末端损失影响区域，吸热管接收到的聚焦能量沿轴向从零开始连续地增大，在此区域以外，集热管每个截面总的聚焦热流等于太阳光以相等的直射辐射强度直射入射时总的聚焦热流，且在轴向上可以认为不变；

3）镜面误差的作用是使聚焦热流由不均匀趋向均匀，这种作用有利于减小管壁温差，镜面误差越大越明显；而跟踪误差增大聚焦热流的不均匀性，影响集热管的安全性，当镜面误差大于 $0 . 1 2 ^ { \circ }$ 或跟踪误差大于 $0 . 6 ^ { \circ }$ 时，PTC的拦截系数小于1;

（4）由于各种实际误差角度的大小不一，所以管外聚焦热流的形状变化多样，可以计算出集热管外实际因素耦合的聚焦热流，从而为光学性能和热性能的分析提供依据。

# 参考文献

[1] He YL,Xiao J,Cheng Z D,et al. A MCRT and FVM coupled simulation method for energy conversion process in parabolic trough solar collector[J]. Renewable Energy, 2011,36(3):976-985.   
[2] WangF,ShuaiY,YuanY,etal.Thermal stress analysisof eccentric tube receiver using concentrated solar radiation[J]. Solar Energy,2010,84(10):1809-1815.   
[3] Wu Z,Li S,Yuan G, et al. Three-dimensional numerical study of heat transfer characteristics of parabolic trough receiver[J].AppliedEnergy,2014,113(113):902-911.   
[4] Zhao Dongming， Xu Ershu， Wang Zhifeng， et al. Influences of installation and tracking errors on the optical performance ofa solarparabolic trough collector[J]. Renewable Energy,2016,94:197-212.   
[5] Cheng Z D,He YL,Cui FQ,et al.Comparative and sensitive analysis for parabolic trough solar collectors with adetailed Monte Carlo ray-tracing optical model[J]. Applied Energy,2014,115(4):559-572.   
[6] Xu C,Chen Z,Li M, et al. Research on the compensation oftheend losseffect forparabolic trough solar collectors[J].Applied Energy,2014,115(4):128-139.   
[7] Cooper T, Steinfeld A. Derivation of the Angular Dispersion Error Distribution ofMirror Surfaces for Monte Carlo Ray-Tracing Applications[J]. Journal of Solar Energy Engineering,2011,133(4):125-134.   
[8] Grena Roberto.Optical simulation of a parabolic solar trough collector[J].International Journal of Sustainable Energy,2010,29(1):19-36.