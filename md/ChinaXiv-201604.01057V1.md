# 空间“引力红移”实验研究

崔慰萍1， 苏建峰

1.华北科技学院电子信息工程学院，河北廊坊065201；2.中国科学院空间科学与应用研究中心，北京100190摘要：通过分析、讨论了在我国开展地面站原子钟与空间原子钟相比对精密测量引力红移的技术方案，并利用STK卫星仿真软件对卫星轨道参数进行了仿真设计.

关键词：相对论；原子钟；红移；轨道参数中图分类号：P228 文献标志码：A 文章编号：1673-9868(2016)01-0138-05

相对论是迄今为止描述自然界时空结构最为完美的理论[1]，爱因斯坦等效原理是相对论的基础[2]，引力红移是等效原理的一个重要物理效应.在过去的几十年里，科学家曾利用火箭及人造飞行器搭载高稳定度频率源测量引力红移[3]，试验中关键因素是时间频率的比对测量精度和原子钟频率稳定度.随着原子钟和空间技术的发展，特别是先进微波技术的发展，星地远程比对与空间环境下原子钟精度的提高，利用空间原子钟更高精度测量引力红移进一步检验相对论是当今空间科学的重要研究方向之一[4].世界各国也提出了很多专门为测量地球引力红移的技术方案[5-6]，美国最早于1976年开展的GP-A试验初步测试了引力红移7；我国亦即将在天宫二号上开展类似实验.但是由于天宫二号其本身轨道特点，在测量地球引力红移方面不是很理想，本文基于此目的，初步提出并分析了我国利用空间原子钟更高精度测量引力红移的空间试验技术方案，为我国开展此类空间科学实验提供参考.

在理想状态下，将地球看作一个球体，假设测量精度为 $\mathrm { c } ^ { - 2 }$ 量级上，根据广义相对论，地球引力红移为[8]：

$$
\varphi _ { \mathrm { 0 } } = \frac { \mathrm { G } M _ { \mathrm { e } } } { \mathrm { c } ^ { 2 } } \Big ( \frac { 1 } { R _ { \mathrm { e } } } - \frac { 1 } { r } \Big ) - \frac { v _ { \mathrm { s } } ^ { 2 } } { 2 \mathrm { c } ^ { 2 } }
$$

式中：G为重力引力常数， ${ M _ { \mathrm { e } } } , { R _ { \mathrm { e } } }$ 分别为地球质量和半径， $\mathrm { ~ c ~ }$ 为光速， $ { v _ { \mathrm { s } } }$ 为卫星速度， $\boldsymbol { r }$ 为卫星到地球表面距离.根据卫星总能量表达式(2）以及势能是动能的两倍可得出公式（3)、（4)，分别表示引力红移与卫星轨道长半轴 $\mathbf { \Delta } _ { a }$ 、引力红移与地球质心到卫星载荷矢量 $\boldsymbol { r }$ 之间的关系.

$$
\begin{array} { r l } & { E = { \mathbb { G } } \frac { M _ { \varepsilon } m } { 2 a } } \\ & { \varphi _ { c } - \frac { G M _ { \varepsilon } } { R _ { \varepsilon } c ^ { 2 } } \Big ( 1 - \frac { 3 R _ { \varepsilon } } { 2 a } \Big ) } \\ & { \varphi _ { c } = \frac { G M _ { \varepsilon } } { c ^ { 2 } } \Big ( \frac { 1 } { R _ { c } } + \frac { 1 } { 2 a } - \frac { 2 } { r } \Big ) } \\ & { r = \frac { a ( 1 - e ^ { 2 } ) } { 1 + e \cos \beta } } \\ & { \beta - \frac { w _ { \varepsilon } } { c } } \end{array}
$$

其中 $ { \boldsymbol { v } } _ { \mathrm { { s } } }$ 为卫星径向速度.根据公式(3)可推算出地球所产生的引力红移最大为 $\mathrm { G } M _ { \mathrm { e } } / R _ { \mathrm { e } } c ^ { 2 } = 6 . \ 9 4 \times 1 0 ^ { - 1 0 }$ 由公式4可看出原子钟红移在地球引力场中的情况，即卫星到达远地点时引力红移 $\varphi _ { \mathrm { 0 } }$ 最大，卫星在近地点时 $\varphi _ { \mathrm { 0 } }$ 最小.根据公式(4)，(5)，(6)分析得出卫星近地点到远地点之间红移变化量与卫星轨道偏心率之间的关系（图1).由图1可知，利用星载原子钟测量引力红移，需采用尽可能大的卫星轨道偏心率.

# 1星地时频传递

根据广义相对论在引力场中，在 $c ^ { - 2 }$ 精度上，不同引力势处两钟的频率差[]为：

![](images/8f0ed390211375c2635767e7214d0ac28d9f6609ed7e3fbde0bd04d1f88884f6.jpg)  
图1卫星近地点到远地点之间红移变化量与卫星轨道偏心率的关系

$$
{ \frac { { \mathrm { d } } \tau _ { \mathrm { s } } } { { \mathrm { d } } t } } - { \frac { { \mathrm { d } } \tau _ { \mathrm { G } } } { { \mathrm { d } } t } } = { \frac { f _ { \mathrm { s } } - f _ { \mathrm { e } } } { f _ { \mathrm { 0 } } } } = { \frac { \varphi _ { \mathrm { s } } - \varphi _ { \mathrm { e } } } { c ^ { 2 } } } - { \frac { v _ { \mathrm { s } } ^ { 2 } - v _ { \mathrm { e } } ^ { 2 } } { 2 c ^ { 2 } } } - { \frac { a _ { \mathrm { e } } } { c ^ { 2 } } }
$$

式中： $f _ { \mathrm { s } } - f _ { \mathrm { e } }$ 为总的频率偏移量， $f _ { \mathrm { ~ 0 ~ } }$ 为星载原子钟频率， $\varphi _ { \mathrm { s } } - \varphi _ { \mathrm { e } }$ 为卫星星载原子钟和地面原子钟之间的引力势差， $v _ { \textrm { e } } , v _ { \textrm { s } }$ 分别为地面原子钟和卫星速度， $\textbf { \em a }$ 。为地面站和卫星之间的矢量.第一项为两钟之间的引力势差所产生的引力红移；第二项是狭义相对论的二阶多普勒效应；第三项是由于地球自转引起的一阶运动多普勒效应.

在地面上各国原子钟实验室，原子钟比对方式通常是秒脉冲直接时间比对得出钟差.如果采用调制秒脉冲方式开展星地原子钟比对，假定空间原子钟不确定度为 ${ 1 0 } ^ {  { - } 1 6 }$ ，卫星定位精度为 $\Delta r$ ，则时间分辨率为$\Delta T = \Delta r / \mathrm { c }$ ．假设卫星定位精度为厘米级，则最小绝对比对时间为 $T _ { \mathrm { m i n } } { \approx } 1 0 ^ { 6 } \ \mathrm { s } { \approx } 2 7 7 \ \mathrm { h }$ ，很明显采用直接秒脉冲时间比对测量时间间隔方式不是很理想，

实际在测红移中采用相位相干测量，即多普勒跟踪消除法测量相对频率偏移.其中，三链星地原子钟多普勒跟踪消除系统，原理图见图2.卫星发播信号 $\mathbf { \nabla } \cdot \mathbf { v } _ { 0 }$ 与原子钟频率锁定同步，地面接收到的频率为 $\boldsymbol { v } _ { 0 } ^ { ' }$ ，同时地面发射站向卫星发播同样信号 $\mathbf { \nabla } \cdot \mathbf { v } _ { 0 }$ ，卫星星载转发器接收到后转发地面站，地面站接收到二倍二次多普勒频移项信号，再与单向微波数据链接收到的数据相减，即可得到引力红移.1976年美国NASA联合SAO（史密松天体物理天文台)联合开展的GPA（GravityProbeA)测量引力红移实验即采用此方法，依据该公式精确到引力红移的多普勒二次项特性 $( \Delta \varphi / \mathrm { c } ^ { 2 } ) ^ { 2 }$ 上．并取得初步的预期效果.

电离层误差是影响时间传递的最主要误差之一，如果不能彻底消除电离层的影响将直接决定测量引力红移的成败.可喜的是在GP-A试验中，已经对此问题提供了参考解决方案（图3).在国际空间上的ACES计划以及类似的科研项目均是采用与GP-A相同原理的方法来消除电离层误差源.电离层误差为

![](images/f299670f9080bc23e0a83e83951b84a9c7b1e1899a9638dc3cb33e9bf024fc56.jpg)  
图2多普勒频率消除原理

$$
\mid f _ { _ { D I } } \mid = - \frac { 4 0 . 5 } { f _ { \mathrm { c } } } \frac { \mathrm { d } } { \mathrm { d } t } \int _ { \rho } \rho ( t ) \mathrm { d } s
$$

采用微波双向三链时间传递的办法，即从星载原子钟一路直接下行载波用来测量电离层，其误差为：

$$
\Delta f _ { \mathrm { c } } = \frac { 4 0 . ~ 5 } { c f _ { h } } \Big ( \frac { \mathrm { d } } { \mathrm { d } t } \Big ) \rho ( t ) \mathrm { d } s \Big ) \frac { Q } { P }
$$

由于其载波带宽高，星载和地面原子钟精度高，所以该方法测量电离层具有很高的精度，胜过利用GPS等导航系统测量电离层精度.另外一路上行载波信号经微波转发下行产生两次的电离层效应，其误差为

$$
\Delta f _ { \mathrm { u d } } = \frac { 4 0 . 5 } { c f _ { h } } \Big ( \frac { \mathrm { d } } { \mathrm { d } t } \bigg \lbrack \rho ( t ) \mathrm { d } s \Big ) \left( \left( 1 + \frac { N ^ { 2 } } { M ^ { 2 } } \right) \frac { S ^ { 2 } } { R ^ { 2 } } \frac { P } { 2 Q } \right)
$$

最终输出电离层误差为

$$
|  { f } _ { \mathrm { e r r o r } } \ | = \frac { 4 0 . 5 } { c f _ { h } } \frac { \mathrm { d } } { \mathrm { d } t } { \int _ { \rho } ( t ) \mathrm { d } s \cdot \left[ \frac { Q } { P } - \left( 1 + \frac { N ^ { 2 } } { M ^ { 2 } } \right) \frac { S ^ { 2 } } { R ^ { 2 } } \frac { P } { 2 Q } \right] }
$$

即：

$$
{ \frac { Q } { P } } = { \frac { 7 6 } { 4 9 } } , { \frac { N } { M } } = { \frac { 2 2 1 } { 2 4 0 } } , { \frac { R } { S } } = { \frac { 8 2 } { 5 5 } }
$$

然后根据公式（9）即可彻底消除电离层影响，

根据公式(10)计算载波的频率关系，同时考虑大椭圆轨道等因素可以综合考虑设计微波载波频率.

![](images/d753e927ba6b5362f06d7e149979d4affc375a7801073fb89f918da0544105f0.jpg)  
图31976年美国GP-A测量引力红移消除电离层原理图

常用的还有四链微波跟踪系统[7]，也是同样的空间实验原理消除多普勒效应.如图4所示，地面和空间系统抵消多普勒效应后输出信号为 $E _ { \scriptscriptstyle 0 } ( t ) , S _ { \scriptscriptstyle 0 } ( t )$ ，即：

$$
E _ { \circ } \left( t \right) = \frac { \varphi _ { \mathrm { s } } - \varphi _ { \mathrm { e } } } { c ^ { 2 } } - \frac { v _ { \mathrm { s } } ^ { 2 } - v _ { \mathrm { e } } ^ { 2 } } { 2 c ^ { 2 } } - \frac { a _ { \mathrm { e } } } { c ^ { 2 } }
$$

$$
S _ { \circ } \left( t \right) = \frac { \varphi _ { \mathrm { s } } - \varphi _ { \mathrm { e } } } { c ^ { 2 } } - \frac { v _ { \mathrm { s } } ^ { 2 } - v _ { \mathrm { e } } ^ { 2 } } { 2 c ^ { 2 } } - \frac { a _ { \mathrm { e } } } { c ^ { 2 } }
$$

（13）、（14)两式相加消除第一项引力红移部分，得到二阶多普勒项；两式相减，消除二阶多普勒项，得到引力红移部分.

依照本文卫星轨道参数设置，根据前面公式可得红移约为 $5 . ~ 8 3 \times 1 0 ^ { - 1 0 }$ ，假设星载原子钟不确定度为 $1 0 \times 1 0 ^ { - 1 6 }$ ，其红移测量精度为（2 $0 . ~ 1 7 \times 1 0 ^ { - 6 }$ ，约为GP-A 测量精度 $( 7 0 \times 1 0 ^ { - 6 }$ ）的400倍，而国际空间站以及国内天宫二号轨道高度约为 $4 5 0 ~ \mathrm { k m }$ ，其红移为 $0 . ~ 4 5 \times 1 0 ^ { - 1 0 }$ ，同样原子钟情况下红移测量精度约为 $2 \times 1 0 ^ { - 6 }$ ，相比之下比空间站及天宫二号测量精度高出至少10倍.如果将星载原子钟最终定为于地一月

![](images/e903af90edf89915dda87863d5b8c80a3c43ef1a878306573abd326ade8537af.jpg)  
图4星地频率比对系统

之间的拉格朗日 $L _ { \textrm { l } }$ 点上[4]，其地球红移达到最大，地球红移测量精度也达到最大约为（ $) . \ 1 4 4 \times 1 0 ^ { - 6 }$ ：

# 2在我国国土上空开展实验STK轨道仿真设计

由前文分析可知，利用星载空间原子钟测量地球引力红移，卫星轨道偏心率越大越好，在满足最小观测角前提下，为进一步提高实验的可靠性以及测量精度，要求保证 $2 4 \mathrm { ~ h ~ }$ 可视的情况下，星地原子钟实现连续比对，其优点是提高重复测量精度.采用STK（SateliteToolKit）软件对卫星轨道进行设计，STK软件被广泛应用于航天工业领域的商业分析软件，可以为卫星工程提供最佳解决方案.通过STK辅助分析，在海南三亚观测站(经度 $1 0 9 . 5 ^ { \circ }$ 、纬度 $1 8 . \ 2 ^ { \circ } \ \cdot$ )放置地面原子钟，卫星轨道可采用大椭圆同步轨道，以实现星一地原子钟连续 $2 4 \mathrm { ~ h ~ }$ 重复比对.卫星可见性见图5、星下点轨迹见图6.表1给出了卫星轨道参数设计.相比美国1976年GP-A试验以及其他测试引力红移试验具有很好的优势，可以更高精度地直接测量地球引力红移.这也是我国开展引力红移试验具有的独特的地理优势.

表1卫星轨道参数配置表  
三亚地面站到卫星可视时间  

<html><body><table><tr><td>周期</td><td>24h</td><td>周期</td><td>24h</td></tr><tr><td>倾角</td><td>45°</td><td>近地点高度</td><td>1.980 26 *Re</td></tr><tr><td>偏心率</td><td>0.55</td><td>最小观测仰角</td><td>10°</td></tr><tr><td>远地点高度</td><td>9.265 3*Re</td><td>地面观测站</td><td>109. 5°，18. 2°</td></tr></table></body></html>

![](images/4906a6c7ced48b8a72880947fcffc771c45d41871630e3bc08e3bd671b90f7c1.jpg)  
图5卫星可见性分析

![](images/2333c9688c550e8c8c8bd1d469925bcddcec8872c28f40c6f83dfbb25452a131.jpg)  
图6卫星星下点轨迹

# 3结论

爱因斯坦广义相对论等效原理的直接结果是：在一个重力势 $U _ { \mathrm { s } }$ 处的辐射源对另一种重力势 $U _ { \mathrm { o } }$ 处的观测者来说，其频率将偏移 $\frac { \Delta f } { f } = - \frac { ( u _ { \mathrm { S } } - u _ { \mathrm { 0 } } ) } { C ^ { 2 } }$ ，通过精密测量引力红移不仅可以在更高精度上验证广义相对论，而且也只有在更高精度上测量引力红移才有可能发现更多未知的现象．比如可能发现暗物质、引力波等．因此高精度测量验证引力红移具有重要的科学意义，可进一步促进人们对自然界的认识.

本文讨论了在我国开展利用空间精密原子钟测量引力红移的方案，通过分析仿真指出了利用我国地理位置优势可以实现更高精度的测量，可以为我国空间科学实验提供参考.当然实际试验中还存在很多需要考虑的因素，比如卫星精密定轨精度将是影响实验精度的一个重要因素.假设测量频移精度为 $\pm 3 \times { 1 0 } ^ { - 1 6 }$ ，则在轨道远地点需要 $\pm 1 0 \mathrm { ~ m ~ }$ 轨道定位精度以及 $\pm 6 \ \mathrm { m m / s }$ 的速度精度，在轨道近地点则需要 $\pm 1 . 6 \mathrm { ~ m ~ }$ 轨道定位精度以及 $\pm 1 ~ \mathrm { m m / s }$ 的速度精度.其他比如地球的四极矩的影响、太阳引力势、Sagnac效应的影响，等等[9-11]，都需要精密计算.

# 参考文献：

[1]GONG Yan-xiang，WU Xiao-mei,CAO Hui-guo,et al.The Post-Post-Newtonian Equations of the Photon in the Ein-stein-Aether Theory［J].西南大学学报（自然科学版），2011，33(3)：27—32.  
[2]邓昭镜.等效原理与引力场的能量一动量表示[J].西南大学学报(自然科学版)，2008，30(9)：11—15.  
[3] 翟造成，李玉莹，刘铁新.氢原子钟的空间应用前景[J].空间电子技术，2011，8(4)：55—60.  
[4]苏建峰，尹冬梅.高精度时间频率在空间科学技术中的应用探讨[J].宇航计测技术，2013，33(5)：34—38.  
[5]VESSOT RFC. Clocks and Spaceborne Tests of Relativistic Gravitation[J]. Advances in Space Research，1989,9（9):21—28.  
[6]赵城，倪维斗.中法激光时间比对和探测基本物理的相关空间计划[J].物理学进展，2008，28(2)：191—203.  
[7]VESSOT R FC,LEVINE M W,MATTISION E M,et al. Test of Relativistic Gravitation with a Spacebore HydrogenMaser[J].PhysRev Lett，1980，45(26)：2081—2084.  
[8]ZHAO Min，WANG Yun-zhi，MU Xiao-yun.The Error Caused by Relativity in GPS Positioning System[J].Advancesin Natural science，2011，4(2)：18-21.  
[9]WOLF P,BORDE C J, CLAIRON A A，et al. Quantum Physics Exploring Gravity in the Outer Solar System: the SA-GAS Project[J].Exp Astron，2009，23(2)：651-687.  
[10］刘晓刚，吴晓平，刘雁雨，等.基于GEO和IGSO卫星的Sagnac效应的求解［J].测绘科学，2009，34(2)：30—32.  
[11]KLEPPNER D,VESSOT RFC,RAMSEY NF.An Orbiting Clock Experiment to Determine the Gravitational RedShift [J]. Astrophysics & Space Science,1970，6(1):13-32.

# An Experiment Study of Space Gravitational Red Shift

CUI Wei-ping1， SU Jian-feng² 1．North China Institute of Science and Technology，Langfang Hebei O65201,China ; 2．National Space Science Center，Chinese Academy of Sciences，Beijing 100190，China

Abstract:Measurement of the gravitational red shift by the highprecision space atomic clock is one of the important methods to test relativity theory. Plans are discussd for an experiment to measure the red shift by comparing a ground-based and a satelite-borne atomic clocks in our country，and simulated design is made of the satellite orbit parameters by the STK software. It is hoped that this work may be of some value for the related space science researches in our country.

Key words:relativity theory;atomic clock；red shift；orbit parameter