# 表面光散射法液体黏度和表面张力实验系统研制

赵贯甲，毕胜山，吴江涛

(西安交通大学热流科学与工程教育部重点实验室，能源与动力工程学院，陕西 西安，710049)

（电话：029-82668143 E-mail: jtwu@mail.xjtu.edu.cn）

摘要：基于气液界面表面波理论和表面光散射原理，本文研制了表面光散射液体黏度和表面张力实验系统，实验系统包括，实验光路、耐高压样品池控温系统和数据采集和处理系统组成。实验系统压力测试范围为 $0 { \sim } 1 0  { \mathrm { M P a } }$ ，温度测试范围为 $2 8 3 { \sim } 4 0 0 \mathrm { K }$ 温度波动度小于 $\pm 1 0  { \mathrm { ~ m K / 1 0 ~ h ~ } }$ 。采用光频外差的方法提取液体表面波信息，并通过数值求解表面波色散方程获得液体黏度和表面张力。利用参考物质甲苯检验了实验系统，本文获得的黏度值与参考方程的最大偏差为 $1 . 3 \%$ ，平均偏差为 $0 . 5 2 \%$ ；表面张力值与拟合值的最大偏差 $0 . 3 9 \%$ ，平均偏差为 $0 . 2 3 \%$ 。通过不确定度分析，本文搭建的系统测量黏度和表面张力的不确定度为别为 $2 \%$ 和 $1 \%$ 。

关键词：光散射；表面张力；黏度；甲苯中图分类号：TK121文献标识码：A

# Liquid Viscosity and Surface Tension Measurement under Saturated Condition with Surface Laser Light Scattering Method

ZHAO Guan-jia, BI Sheng-shan, WU Jiang-tao (KeyLaboratoryofTero-FluidiencendEnginering,MinistryofEdcation,Xi'anJaotong UniversityXi'an09,Cina)

Abstract:Based on the light scattering theory,a new apparatus for liquid viscosityand surface tension measurement under saturated condition was built. A pressure vessel is designed and alowed to work under 10MPa. Heating wire scheme is adopt to control the temperature of the vessel and the temperatures can be well controlled between $2 8 3 \mathrm { ~ K ~ }$ and $4 0 0 ~ \mathrm { K }$ with a stability better than $\pm 1 0 \ \mathrm { m K }$ per 1O hours. Since the frequencies of capillary waves are much smaller than that of laser light, optical mixing technique and heterodyne scheme are used to extract physical information of capilary wave.Liquid viscosity and surface tension are obtained by numerically solving the dispersion equation of capilary wave in liquid-vapor phase.In order to check accuracy and reliability of the apparatus,viscosity and surface tension of toluene are investigated. The maximal deviation of viscosities between experimental values and reference equation is $1 . 3 \%$ and the mean deviation is $0 . 5 2 \ \%$ . The maximal and mean deviation for surface tension is less than $0 . 3 9 \%$ and $0 . 2 5 \%$ ,respectively. The total uncertainty for the measurement of viscosity and surface tension are estimated to be $2 \%$ and $1 \%$ respectively.

Keywords: Light Scattering; Surface Tension; Viscosity; Toluene

# 0引言

两种流体之间形成的界面，如气-液界面和液-液界面，从宏观上来看像“镜面”一样光滑。但是从微观上看，两相中的分子在做无规则的热运动，界面上的分子则以某一统计平衡位置波动，通常称这种波动为表面波。表面波的尺度很小：波长在微米级，振幅在纳米级。在这个尺度上，传统的实验手段很难对其进行研究，需要借助光散射技术。然而受到光源频宽和功率限制，直至上世纪60年代激光器发明前，表面波实验研究进展缓慢。激光器的发明推动了光散射实验的发展，大量的相界面研究开始采用光散射方法。Hard[1]（1976）发明了利用光栅分光方法搭建散射系统，并从理论上修正小角度散射带来的仪器加宽效应。在热物性研究领域，YujiNagasakal2最早开始才利用光散射的方法研究液体的界面性质，即黏度和表面张力，表面张力的测量精度为 $2 \%$ ，与传统方法的精度相当，但是黏度的测量不确定度达到了 $20 \%$ ，主要原因是作者采用了Hard方法修正仪器加宽效应，而hard模型必须已知光束在液面处的直径，测量光束直径引入了较大的不确定度。Andreas[3.4放弃了光栅分光而直接采用偏振分光棱镜分光，同时采用较大散射角度以避免或减弱仪器加宽效应，黏度和界面张力的测试不确定度宣称可以达到 $1 \%$ 。2006年，西安交通大学王风坤[5搭建了光散射实验系统，该系统可以实现常温常压下表面张力的测量，结果与文献值偏差 $2 \%$ 。

本文借鉴Andreas的实验方案，搭建了表面光散射液体表面张力和黏度实验系统，通过标准物质甲苯对系统进行了检验及不确定度分析。

# 1实验原理

# 1.1表面波模型

Lucassen（1970）通过简化Landau建立的黏性流体Navier-Stokes模型，得到了可以在适用范围非常广泛的表面波色散方程[6]：

$$
\begin{array} { r l } & { [ \eta ( q - m ) - \eta ^ { ' } ( q - m ^ { ' } ) ] ^ { 2 } + \mathrm { i } [ \eta ( q + m ) + } \\ & { \dot { \eta ^ { ' } } ( q + m ^ { ' } ) ] \times ( \sigma q ^ { 2 } / \omega + \mathrm { i } [ \eta ( q + m ) + } \\ & { \dot { \eta ^ { ' } } ( q + m ^ { ' } ) ] + g ( \rho - \rho ^ { ' } ) / \omega - } \\ & { \omega ( \rho + \dot { \rho ^ { ' } } ) / q ) = 0 } \end{array}
$$

其中， $\omega$ 为复数 $\scriptstyle { \omega = \omega _ { 0 } \pm \mathrm { i } T }$ ， $\omega _ { 0 }$ 表征表面波频率， $\boldsymbol { { \cal T } }$ 表征表面波衰减 $I { = } 1 / \tau _ { \mathrm { C } }$ ， $\pi _ { \mathrm { C } }$ 为表面波衰减的特征时间； $m { = } \left( q ^ { 2 } { + } \mathrm { i } \omega \rho / \eta \right) ^ { 1 / 2 }$ ， $m ^ { \prime } { = } ( q ^ { 2 } { + } \mathrm { i } \omega \rho ^ { \prime } / \eta ^ { \prime } ) ^ { 1 / 2 }$ ；其中未知参数为： $\omega , ~ q , ~ \eta , ~ \eta ^ { \prime } , ~ \rho , ~ \rho ^ { \prime }$ 和 $\sigma$ 分别为表面波圆频率、表面波波数、液相黏度、气相黏度、液相密度、气相密度和表面张力。 $\omega$ 、 $\pi _ { \mathrm { C } }$ 和 $q$ 可以通过实验的方法获得。由于式（1）是复数方程，已知气液相密度和气相黏度便可以获得高精度的黏度 $\eta$ 和表面张力 $\sigma$ 值。

# 1.2表面光散射几何图示

如图1所示，当一束单色光以角度γ入射到液面上，以反射光和折射光为轴心的立体角内会均匀地向外散射光。

![](images/749dcee752f546cd98096db35f75e14cf45cd83b13d0b80ed3f15e3f59a99130.jpg)  
图1表面光散射示意图  
Fig.1 Geometry of surface light scattering.

散射光的方向由几何关系决定，

$$
\vec { q } = \vec { k } _ { \mathrm { I } } - \vec { k } _ { \mathrm { S } }
$$

其中 $\vec { k } _ { \mathrm { I } }$ 为入射光波矢量， $\left| \vec { k } _ { \mathrm { I } } \right| { = } 2 \pi / \lambda _ { \mathrm { 0 } }$ ， $\lambda _ { 0 }$ 为入射光波长； $\vec { k } _ { \mathrm { s } }$ 为散射光波矢量； $\vec { q }$ 为液体表面波矢量， $\left| \vec { q } \right| { = } 2 \pi / \lambda _ { _ { \Lambda } }$ ， $\lambda _ { \Lambda }$ 为表面波波长。考虑到$\left| \vec { q } \right| < < \left| \vec { k } _ { \mathrm { I } } \right|$ 且 $\left| \vec { q } \right| < < \left| \vec { k } _ { \mathrm { s } } \right|$ ，因此， $\left| \vec { k } _ { \mathrm { I } } \right| \approx \left| \vec { k } _ { \mathrm { S } } \right|$ 成立。

本文研究折射光附近的散射，液体表面波数可以通过几何关系得到，

$$
\left| \vec { q } \right| { = } 2 n \left| \vec { k } _ { \mathrm { I } } \right| \mathrm { s i n } { \frac { \theta } { 2 } } \mathrm { c o s } ( \alpha - { \frac { \theta } { 2 } } )
$$

其中， $n$ 为液相相对气相的折射率， $\alpha$ 为折射角。特别地，当 $\theta = \alpha$ ，即在竖直方向接收散射光，考虑到折射定律，表面波数可以简化为，

$$
\left| \vec { q } \right| { = } { \left| \vec { k } _ { I } \right| } \sin \gamma
$$

因此，可以通过选择不同的散射角或入射角来选择所要研究的表面波。实验中，入射角度y可以通过旋转台测量，由式（4）可进而获得液体表面波数。

# 1.3光子相关技术

在表面光散射中，可以利用被表面波散射的散射光的时间相关方程来描述表面波的色散特征。对于本文研究的振荡衰减的表面波，散射光强度时间相关方程可以表示为，

$$
G ^ { 2 } ( \tau ) = A + B \cos ( \omega \tau + \varphi ) \exp ( \tau / \tau _ { \mathrm { c } } )
$$

其中， $A$ 为相关函数的基线； $B$ 为比例常数;$\varphi$ 为相位偏移量，表征了提取到的表面波功率谱相对于标准洛仑兹函数的偏差。一般地，表面光散射所研究的液体表面波频率为 $2 0 \mathrm { { M H z } }$ 以下[7]，相对于激光频率可以忽略不计，因此传统干涉仪很难分辨和解析。需要采用光学混频和外差技术，所谓混频，是指在散射光中混叠一部分未被表面波调制的参考光，从而通过测量两束光之间的拍频来确定液体表面波频率；外差探测是指所叠加的参考光强度远远强于散射光的强度。采用外差探测可以有效保证测量的可靠性[7]。

# 2实验系统

# 2.1光路设计

本文研制了表面光散射实验系统，如图2所示。由实验光路、耐高压实验本体、控温系统和数据采集和处理系统组成。

![](images/8f993314111cba0e21b88b6a59c636210b59e83211ec44c3cdd045ecc25837ae.jpg)  
图2表面光散射实验系统示意图  
Fig.2 Scheme of surface light scattering apparatus

激光器采用低功率连续型固体激光器，其波长为 $\lambda _ { 0 } { = } 5 3 2 \ \mathrm { n m }$ 。为了减小激光光束的发散角，充分利用激光器功率获得更强的散射光，本文采用焦距为 $2 \mathrm { m }$ 的长焦透镜对出口光斑进行准直。经过准直的光束被分光平片一分为二，透射光作为探测光，反射光作为参考光。首先考虑探测光，本文采用零级二分之一玻片和偏振分光棱镜来实现同时调整探测光功率和偏振态的要求。样品池窗口上部的高反射率反射镜（简称高反）安装在一个高精度旋转台上，旋转台通过直角板固定在可以左右移动的一维高精度数显位移台上。旋转台的直径为 $8 0 \mathrm { m m }$ 角度分辨率为 $0 . 0 0 0 6 7 ^ { \circ }$ ，经过校正角度测量的精度可以达到 $\pm 0 . 0 5 \%$ 。一维位移台的行程 $2 0 0 \mathrm { m m }$ ，位移分辨率 $0 . 0 1 \mathrm { m m }$ ，配合高精度旋转台可以实现不同散射角度的测量。本实验中采用式（4）的方式来选择液体表面波数，即在沿竖直方向探测散射光，使散射角等于折射角（ $\theta = \alpha$ )。其次，考虑参考光。为了保证外差探测方案，本文在散射光中混叠了足够强的参考光。混频信号经小孔PH1和PH2进入光子计数器，利用数字相关器计算两路信号的相关函数，将相关数据拟合成式（5）的形式，其中拟合获得的参数 $\omega$ 和 $\pi _ { \mathrm { C } }$ 即为色散方程中的输入参数。

# 2.2耐高压实验本体设计

本文设计了同时适用于表面光的实验本体，温度范围为 $2 5 0 { \sim } 4 0 0 \ \mathrm { K }$ ，压力范围为 $0 { \sim } 1 0 \ \mathrm { M P a }$ 。为兼顾强度和耐腐蚀性能等要求，实验本体采用304号不锈钢材料。由于液体的表面张力作用，靠近本体内壁的液面会因吸附在内壁面而发生弯曲，为保证液面中心区域水平，实验本体内部直径设计为70$\mathrm { m m } ^ { [ 8 ] }$ 。实验本体的容积为 $1 5 0 \mathrm { c m } ^ { 3 }$ ，实验中所需的样品体积约为 $5 0 \mathrm { c m } ^ { 3 }$ 。

# 2.3温度控制

实验本体放置在环氧树脂板制成的箱体内，温度控制采用电加热方式，在本体外壁面均匀地缠绕电加热丝。采用高精度温度控制器控制加热功率，实现对实验本体的温度控制，温度波动度好于 $\pm 7$ mK/2h。

# 3实验数据处理与结果分析

# 3.1 实验样品

本文采用黏度数据较为准确的甲苯来检验新的实验系统。采用国药集团生产的甲苯，其甲苯含量大于 $9 9 . 5 ~ \%$ ，蒸发残渣小于 $0 . 0 0 1 \%$ ，水分含量小于 $0 . 0 3 \%$ ，使用前未做进一步提纯。

# 3.2数据处理

通过拟合相关函数式（5）可以提取出液体表面波的频率 $\omega$ 和弛豫时间 $\pi _ { C }$ 。在实验中，散射角一般选择 $3 { \sim } 5 ^ { \circ }$ 以避免仪器加宽的影响。如图3所示为 $T { = } 3 7 3 . 0 5 \ \mathrm { K }$ ， $q { = } 6 . 1 1 9 3 8 \mathrm { x } 1 0 ^ { - 5 } \mathrm { m } ^ { - 1 }$ 时获得的相关函数。拟合得到的表面波频率 $\omega { = } 2 . 3 2 6 7 { \pm } 0 . 0 0 2 5$ $\mathrm { \mathbf { M H z } }$ ，弛豫时间 $\tau _ { \mathrm { { C } } } { = } 4 . 4 2 7 8 { \pm } 0 . 0 5 1 1 ~ \mu \mathrm { { s } } .$ 。表面波频率和弛豫时间的拟合偏差分别为 $0 . 1 \%$ 和 $1 . 2 \%$ 。图3中数字相关器的每个通道的实验值与拟合方程的最大偏差不超过 $0 . 0 5 \%$ ，且偏差均匀分布，说明方程（5）可以较好地反映表面波的特征。

0.260品 甲苯，T=373.05K东0.259 中中  
（2）(2）0 0.2580.2570.04 □ □品 888 品品 品 品  
%psasstss 0.02 8 品 □ 品品品 中 品0.00 □ □ 品 品 品 品 8 电-0.02 品品 8品 □ 3 品 品 □□ Doo □ 品 品 Ernoo0 品品x00 □ □ □ 品□品-0.04 品 □ □□-0.06 上 上 1 L 10 2 4 6 8 10 12 14τ/us

# 3.3结果分析

表1给出了甲苯的黏度和表面张力实验值。表1甲苯黏度和表面张力实验数据

Table1 Viscosity and surface tension of toluene   

<html><body><table><tr><td>T</td><td>p</td><td>p'</td><td>n'</td><td>n</td><td>0</td></tr><tr><td>/K</td><td>/kg·m3</td><td>/kg·m3</td><td>/μPa·s</td><td>/mPa-s</td><td>/mN·m-1</td></tr><tr><td>293.16</td><td>866.8</td><td>0.11</td><td>6.74</td><td>0.6737</td><td>28.27</td></tr><tr><td>303.17</td><td>857.5</td><td>0.18</td><td>6.95</td><td>0.6105</td><td>27.27</td></tr><tr><td>313.15</td><td>848.1</td><td>0.28</td><td>7.16</td><td>0.5461</td><td>25.95</td></tr><tr><td>323.13</td><td>838.7</td><td>0.42</td><td>7.38</td><td>0.5028</td><td>24.87</td></tr><tr><td>333.09</td><td>829.2</td><td>0.62</td><td>7.61</td><td>0.4652</td><td>23.70</td></tr><tr><td>343.06</td><td>819.6</td><td>0.89</td><td>7.84</td><td>0.4242</td><td>22.58</td></tr><tr><td>353.03</td><td>809.9</td><td>1.24</td><td>8.08</td><td>0.3889</td><td>21.45</td></tr><tr><td>362.97</td><td>800.1</td><td>1.69</td><td>8.32</td><td>0.3632</td><td>20.44</td></tr><tr><td>373.05</td><td>790.0</td><td>2.27</td><td>8.58</td><td>0.3407</td><td>19.29</td></tr><tr><td>382.98</td><td>779.9</td><td>2.99</td><td>8.84</td><td>0.3233</td><td>18.08</td></tr></table></body></html>

其中气液相的密度和气相黏度来自NISTREFPROP9.0，不确定度分别为 $0 . 2 \%$ 、 $0 . 0 5 \ \%$ 和$5 \%$ 。将本文获得的黏度实验数据与甲苯的参考方程相比较，如图4所示，最大偏差为 $1 . 3 \%$ ，平均偏差为 $0 . 5 2 \%$ ，在本文研究的温度范围内，本文实验数据与文献数据的偏差均在 $2 \%$ 以内。

![](images/0839c3dc34a1d89cc1a6b1adcacd426075255529533a5947b715a6e35a80d98b.jpg)  
Fig.3Fitting of the correlation function for toluene and its deviations   
图4甲苯黏度实验值与标准方程和文献值的比较 Fig.4 Comparisons between the experiment viscosity of toluene and the reference equation and literature data.

$( \boxed { } )$ 本文； $( \bigcirc )$ Dymond(1995)[9]； $( \triangle )$ Charles(1987)[10];$( \bigtriangledown ) \mathrm { G o n a i v e s } ( 1 9 8 7 ) ^ { [ 1 1 ] } ; ( \bigtriangleup ) \mathrm { K a i s e r } ( 1 9 9 1 ) ^ { [ 1 2 ] } .$ (☆)Assael(2000)[13]；(—） Santos and Castro(2006)[14]将甲苯表面张力数据拟合为VanDeWaals形式，

$$
\sigma = \sigma _ { 0 } ( 1 - T / T _ { c } ) ^ { n }
$$

其中， $T$ 的单位为 $\mathrm { ~ K ~ }$ ； $T _ { \mathrm { c } }$ 为甲苯的临界温度，${ \cal T } _ { \mathrm { c } } { = } 5 9 3 . 9 5 \mathrm { K }$ ;拟合值 $\sigma _ { 0 } { = } 6 5 . 8 2 4 9 \ \mathrm { m N { \cdot } m ^ { - 1 } }$ $n { = } 1 . 2 4 5 3$ 。如图5所示，实验值与拟合值的最大绝对偏差为$0 . 3 9 \%$ ，平均绝对偏差为 $0 . 2 3 \%$ 。如图5所示本文数据和方程与大多数实验数据的偏差在 $12 \%$ 之内。

![](images/cf5ee249764458b3a7ec2cf9f4da1ef3a64ade6b00810595c7cedf477becab3e.jpg)  
图3甲苯相关函数拟合及偏差  
图5甲苯表面张力实验值与标准方程和文献值的比较 Fig.5 Comparisons between the experiment surface tension of toluene and the reference equation and literature data. (□，一)本文；（ $\cdot \diamondsuit .$ Stephan(1987)[15]; (△)Morino(1932)[16]；( $\bigtriangledown )$ Segado(1992)[17]; (O)Prabhakar(1986)[18]； $( \triangleleft )$ Kremann(1914)[19]; (>)Renard(1907)[20]；(☆)Jarger(1917)[21];

# 3.4实验不确定度分析

本实验系统的测量不确定度由色散方程中的测量、输入参数和温度测量引入。本文中采用文献[4]中推荐的方法来估计实验系统的测量不确定度。实验系统黏度和表面张力测量不确定度分别估计为 $2 \%$ 和 $1 \%$ 。

# 4结论

本文搭建的表面光散射同时测量液体黏度和表面张力实验系统。为了检验系统的可靠性，本文利用标准物质甲苯对装置进行了检验，结果表明黏度和表面张力的实验值与理论值最大偏差和平均偏差分别为 $1 . 3 \%$ 、 $0 . 5 2 \%$ 和 $0 . 3 9 \ \%$ 、 $0 . 2 3 \ \%$ ，可以满足黏度和表面张力的高精度测试要求。

# 参考文献

[1]Hard S, Hamnerius Y,Nilsson O.Laser heterodyne apparatus for measurementsof liquid surface properties-Theory and experiments[J]. Journal of Applied Physics,1976,47 (6): 2433-2442.   
[2]Nishio T,Nagasaka Y. Simultaneous measurement of surface tension and kinematic viscosity using thermal fluctuations[J]. International Journal of Thermophysics,1995,16(5): 1087-1097.   
[3] Froba A P,Leipertz A.Viscosity and Surface Tension of Saturated Toluene from Surface Light Scattering(SLS)[J]. InternationalJournalof Thermophysics,2001,22(1): 41-59.   
[4] Froba A P,Leipertz A. Accurate Determination of Liquid Viscosity and Surface Tension Using Surface Light Scattering (SLS): Toluene Under Saturation Conditions Between 260 and 380 K[J]. International Journal of Thermophysics,2003，24 (4): 895-921.   
[5] 王凤坤．激光散射法测量液体表面张力实验系统 的研制[D]．西安：西安交通大学,2006. Wang Fengkun. Development of light scattering apparatus for surface tension measurement[D]. Xi'an Xi'an Jiaotong University, 2006.   
[6]Lucassen-Reynders E H,Lucassen J. Properties of capillarywaves[J]. Advancesin Colloidand Interface Science,1970,2(4): 347-395.   
[7]Leipertz A,Froba A P.Diffusion Measurements in Fluids by Dynamic Light Scattering. In: Heitjans P, Kärger J,editors.Diffusion in Condensed Matter. Springer Berlin Heidelberg,2005: 579-618.   
[8] Langevin D. Capillary-wave techniques for the measurement of surface tension and surface viscoelasticity[J]. Colloids and Surfaces, 1990,43 (2): 121-131.   
[9]Dymond J, Glen N, Isdale J,et al. The viscosity of liquid toluene at elevated pressures[J]. International Journal of Thermophysics,1995,16 (4): 877-882.   
[10] Byers C H,Williams D F. Viscosities of pure polyaromatic hydrocarbons[J]. Journal of Chemical and Engineering Data, 1987,32 (3): 344-348.   
[11] Goncalves F, Hamano K, Sengers J, et al. Viscosity of liquid toluene in the temperature range $2 5 { - } 7 5 ^ { \circ }$ C[J]. International Journal of Thermophysics,1987, 8 (6): 641-647.   
[12] Kaiser B, Laesecke A, Stelbrink M. Measurements of the viscosity of liquid toluene in the temperature range 218-378 K[J]. International Journal of Thermophysics,1991,12 (2): 289-306.   
[13] Assael M, Dalaouti N, Dymond J. The Viscosity of Toluene in the Temperature Range 210 to 370 K[J]. International Journal of Thermophysics,2000,21 (2): 291-299.   
[14] Santos F J, Nieto de Castro CA, Dymond J H, et al. Standard reference data for the viscosityof toluene[J]. Journal of physical andchemical reference data,2006,35 (1): 1-8.   
[15] Stephan K, Hildwein H. Recommended data of selected compoundsandbinary mixtures[M]. Dechema Frankfurt am Main, 1987.   
[16]Morino Y. Thesurfacetensions_of_binary mixtures[J]. Bull Inst Phys-Chem Res(Tokyo), 1932,11: 1018-1043.   
[17] Segado A,Aguilar A,Cota G J. The effects of surface tension and interphase breakageon rectification[J].Chemicalandbiochemical engineering quarterly, 1992, 6 (1): 13-18.   
[18] Prabhakar J, Kumar K A， Swamy V N,et al. Thermophysical properties of alkylbenzene-chloroethane systems viscosity and surface tension[J].J Indian Inst Sci,1986,66: 449-456.   
[19] Kremann R,Meingast R. Energy Changes in Binary Systems.II.SurfaceTensionofBinary Mixtures[J]. Monatsh Chem,1914, 35: 1323-1364.   
[20] Wohlfarth C, Wohlfarth B, Lechner M. Numerical Data and Functional Relationships in Science and Technology，Vol. 16 Surface Tension of Pure LiquidsandBinary LiquidMixtures[J]. Landoldt-Börnstein, New Series Group IV Physical Chemistry， Springer， Verlag Berlin， Heidelberg, 1997.   
[21] Jäger F. Uber die Temperaturabhängigkeit der Molekularen FreienOberflächenenergievon Fluissigkeiten im Temperaturbereich von-80 bis+ $1 6 5 0 ^ { \circ }$ C[J]. Z Anorg Allg Chem, 1917,101: 1-214.