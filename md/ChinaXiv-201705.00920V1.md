# 离心透平附属通流部件设计分析

谭鑫1.2李会1.2 宋艳苹1,2 黄典贵1.2

(1.上海理工大学能源与动力工程学院，上海200093;2．上海市动力工程多相流动与传热重点实验室，上海200093)

摘要离心透平的通流部件主要包括：进气道、静叶栅、动叶栅、无叶扩压器、出气道，本文对除静叶栅、动叶栅之外的附属通流部件的子午面进行设计。进气道子午面设计采用等截面法，保证级前进气均匀、轴向对称；无叶扩压器采用与叶栅等高的平行侧壁形式，最佳出口直径根据整机效率最优的原则得到；出气道子午面采用与叶栅等高的圆弧扩压弯管设计。结果表明，该方法设计附属通流部件简单易行，特别适合工程应用，以某一离心透平为例，数值模拟得到的级效率为$8 8 . 5 1 \%$ ，整机效率为 $9 0 . 3 4 \%$ ，轮周功为 $4 7 8 . 9 \mathrm { ~ k W }$ ，性能达到预期。

关键词离心透平；附属通流部件；数值模拟；等截面法图分类号：V14 文献标识码：A 文章编号：0253-231X(2017)04-0767-0

# Design of the Auxiliary Flow ComponentsQf the Centrifugal Turbine

TAN Xin $^ { 1 , 2 }$ （20 LI Hui1,2 SONG Yan Ping1,2 HUANG Dian-Gui $^ { 1 , 2 }$ （20 (1.SchoolofEnergyand Power Engineering, UniversityofShanghai for Scienceand Technology，Shanghai 20093,China; 2.Shanghai key laboratory of multiphase fow andheattransfer of power engineering， Shanghai 20o93, China)

AbstractCentrifugal turbine flow components mainly includes: inlet， stator and rotor cascade, vaneless difuser,outlet. In this paperthe meridian plane design of the throughflow sections without the statorandrotorcascade hadbeanalyzed.Thedesignofinlet meridianplaneobeytheuniform section method, which can ensure air enters uniformly and axial symmetry; the vaneless diffuser meridian plane side was/paralel,and the optimal outlet diameter according to the principle of the optimal overall effcienly: the outlet meridian plane adopt the contour of the circular bending pipe. With a centrifugal turbine as an example, which throughflow secti6ns are designed by using this method, the stage efficiency is $8 8 . 5 0 5 \%$ and machine efficiency wasup to 90.34% and wheel power was 478.9 kW obtained by numerical simulation,the performance in line with expectations. The results show that using this method to design auxiliary flow components is simple, specially suitable for the engineering application.

Key wordscentrifugal turbine; auxiliary throughfow sections; numerical simulation; uniform section method p

# 0前言

目前，透平主要分为轴流式透平和径流式透平。轴流式透平因不同半径处的旋转线速度不同，必须采用扭曲叶片，对于长叶片，反动度和速比从根部到顶部会有很大变化，不能够都设计在最佳速比处。径流式透平分为向心式透平和离心式透平。向心式透平研究比较成熟，常用于地热能发电、汽车涡轮增压、余热发电等。但向心式透平在气动与几何上不相容，即沿着流动方向，工质不断膨胀，比容急剧增大，但流动的旋成面周长减小，迫使叶片沿着径向流动方向高度急剧增大。对比上述两种传统透平，离心式透平气流流动过程中气动与几何是相容的，即沿着流动方向，工质不断膨胀，比容增大与流动的旋成面周长增大同步，使叶片沿着径向方向高度变化缓慢；离心式透平还可采用直叶片，沿叶高方向可设计在最佳反动度和最佳速比处，透平效率更高，叶片制造更简单，且直叶片顶部用围带固定做成闭式叶轮时，叶轮强度大，适合高速旋转。

意大利米兰理工大学的 Persico G、PiniM[1-4]等人在离心透平方面做了一些工作，主要还集中在热力设计与翼型设计方面，谭鑫、李银各等[5-7」研究了离心透平热力气动设计和翼型设计，但是都尚未对整机通流部件进行研究。国内外，在离心压气机[8-10]和向心透平[11-12]的通流部件设计方法上有少量研究，对离心透平的通流部件设计有借鉴意义。

如图1所示，离心透平的通流部件主要包括：进气道、静叶栅、动叶栅、无叶扩压器、出气道，一定压力、温度、流量的工质经进气道流入离心透平，在静叶中膨胀加速，将工质的热能转换为动能，随后进入动叶轮，在动叶轮中继续膨胀加速，推动叶轮旋转，将动能转换为机械能，以轴功的形式输出，带动发电机发电，气体通过无叶扩压器，压力略有回升，最后从出气道流出。离心透平的气动性能由进气道、无叶扩压器、出口道等附属通流部件形状和静叶、动叶的形状共同决定。因而设计出合理的附属通流部件是离心透平设计的关键技术之一。

![](images/2fa1ba0ae649b2318c3f2dfb10e0f5a494148c886ba6ebb5cc72a929c411ad7d.jpg)  
图1离心透平通流部件子午面示意图Fig.1 Centrifugal Turbine Throughflow Sections MeridianPlane

# 1数值模拟

合理的一维气动计算，是透平通流部件优化设计的基础。本文以文献 $[ 5 ] \sim$ [7]中的离心透平级一维气动设计参数和优化的翼型形状[7]作为附属通流部件设计的基础。该离心透平级在设计工况下的参数见表1，静叶和动叶的几何参数见表2、几何形状见图2。

Table 1 The design parameters of the centrifugal turbine   
表2离心透平的主要几何参数  

<html><body><table><tr><td>参数</td><td>设计值</td></tr><tr><td>进口总温To/K</td><td>550</td></tr><tr><td>进口总压Po/Pa</td><td>320000</td></tr><tr><td>出口背压P2/Pa</td><td>200000</td></tr><tr><td>设计转速n/r·min-1</td><td>6000</td></tr><tr><td>质量流量G/kg·s-1</td><td>8</td></tr><tr><td>透平功率W/kW</td><td>480</td></tr><tr><td>轮周效率nu/%</td><td>86.59</td></tr></table></body></html>

表1离心透平设计参数  
Table 2 The main geometrical parameters of the centrifugal turbine   

<html><body><table><tr><td>几何参数</td><td>静叶</td><td>动叶</td></tr><tr><td>入口直径Di/mm</td><td>528.9</td><td>621.3</td></tr><tr><td>出口直径D2/mm</td><td>616.3</td><td>708.8</td></tr><tr><td>高H/mm</td><td>40</td><td>40</td></tr><tr><td></td><td></td><td></td></tr><tr><td>/m</td><td>2.5</td><td>1555</td></tr><tr><td>叶型入口角βi/()</td><td>90</td><td>27.86</td></tr><tr><td>叶型出口角β2/()</td><td>12</td><td>16.21</td></tr></table></body></html>

![](images/2419e2106a15fa6f1d9f38fce8f33579ac183599dac72279700ae0c3ed7cfd96.jpg)  
图2文献的静叶、动叶 Fig.2 The stator and rotor of references

本文采用计算流体力学方法对离心透平整机三维稳态流动进行数值模拟，湍流模型为 $k { - } \varepsilon$ 模型。网格如图3所示，动、静叶采用单流道网格，进出口为全流道网格。进口边界条件为总温、总压，出口边界条件为流量，其值按表1所示设计值给出。

优化前首先对附属部件进行了网格无关性验证，分别采用4套网格进行计算和对比，计算结果如表3所示。从表3中可以看到，当网格数在50万和100万时计算的各项结果基本一致，效率偏差小于 $0 . 1 \%$ 因此本文采用第3套网格。

![](images/5d4c4cd973c89196d45b86207c51d5b6450e8f510f7f3c1a3dbe0b9710cdd7c8.jpg)  
图3离心透平数值计算网格Fig.3 The centrifugal turbine grid

# 表3网格无关性验证

为使进气道流动均匀且轴向对称，假定在进气道中是均匀定常的绝热等熵流动，那么流道的截面速度 $C$ 、密度 $\rho$ 为定值： $C _ { 0 } \mathrm { = } C$ ， $\rho _ { 0 } = \rho$ 业

进气道流动遵守流量守恒定理： $G = \rho _ { 0 } C _ { 0 } A _ { 0 } =$ $\rho C A$ ，式中下标‘ $\langle 0 ^ { \dag }$ 代表的是静叶栅进口处的状态参数， $A$ 为过流截面积。由进气道截面速度 $C$ 、密度$\rho$ 为定值可得出，进气道设计应遵循等截面法： $A =$ $A _ { 0 }$ 。对于进气道，进口过流截面积 $A = \frac { \pi } { 4 } D _ { \mathrm { i n } } ^ { 2 } $ ，出□过流截面积 $A _ { 0 } ~ = ~ \pi D _ { 0 } H _ { 0 }$ ，则进气道进口直径$D _ { i n } = 2 \sqrt { D _ { 0 } H _ { 0 } }$ 0

Table 3 The grid independent research   

<html><body><table><tr><td></td><td>进气道 网格数</td><td>出气道 网格数</td><td>级效 n1/%</td><td>整机效 n2/%</td><td>W/kW</td><td>G/kg.s-1</td></tr><tr><td>1</td><td>97036</td><td>66418</td><td>88.14</td><td>88.67</td><td>455.9</td><td>8 理学报》</td></tr><tr><td>2</td><td>299544</td><td>176961</td><td>88.24</td><td>88.97</td><td>457.4</td><td></td></tr><tr><td>3</td><td>535040</td><td>297857</td><td>88.38</td><td>89.19</td><td>457.9</td><td></td></tr><tr><td>4</td><td>977878</td><td>503979</td><td>88.34</td><td>89.22</td><td>457.3</td><td></td></tr></table></body></html>

如图5所示，将进气道中不同位置处的过流截线中点连接成中心流线，过流截线由圆弧简化为直线，那么，过流截面积等于以过流截线为母线的圆台侧面积： $A \equiv 2 \pi R L$ ，式中 $R$ 为过流截线中点的半径值， $L$ 为过流截线的长度。根据等截面法 $( A = A _ { 0 }$ ）可知中心流线不同半径处的截线长度： $L = \frac { D _ { 0 } H _ { 0 } } { 2 R }$ （20

# 2 进气道子午面设计

类似于离心压气机[13],进气道对离心透平的作用是把气体引入透平。本文采用如图4的进气道结构形式，该类进气道特点是：进气均匀且轴向对称，流动损失少，结构简单和紧凑。

![](images/f5bba055c9bc53e20a691bce655d3b5bbccee683550dfc25f1a13d68043a2a04.jpg)  
图4进气道结构形式示意图Fig.4 The inlet structure diagram

![](images/ef8b13c23a32dee28f88fccb884d40fc619fc264a3fb1b9b55631e503c2339b4.jpg)  
图5进气道中心流线形成图Fig.5 The inlet c enter streamline form figure

如图5所示，为确保中心流线头、尾处分别与轴向和径向相切，用 $1 / 4$ 椭圆来表达中心流线，轴Do_Din=Do-VDoHo，轴a可以取不同值。当 $a = b$ 时，中心流线实际上是 $1 / 4$ 圆弧，求出不同半径 $R$ 处的截线长度 $L$ ，用两条样条曲线分别连接截线的两端，形成Hub线和Shroud线，如图6所示，所做出的即为进气道的子午面形状。另外，我们还对子午面的Hub 线和Shroud两条曲线进行近似处理，用与中心流线椭圆同圆心的 $1 / 4$ 椭圆表示，头、尾处均与轴向和径向相切。

图7是选择了4个不同的中心流线椭圆的轴 $\mathbf { \Omega } _ { a }$ 长度，它们分别为 $a = 0 . 7 5 b$ ， $a = b$ ， $a = 1 . 5 b$ ， $a = 2 b$ 5得到的进口流道。将这四种按照等截面法设计与椭圆近似设计的进气道，连同静叶、动叶一起进行数值模拟，计算网格如图8所示，模拟结果见表4。

![](images/b4ff44115701fec53eb7687dbbca4ab5e79a3f5406faf848afdd0f03bef7701e.jpg)  
图6进气道子午面形成图Fig.6 The inlet meridian plane form figuree

表4中级效率 $\eta _ { 1 }$ 和整机效率 $\eta _ { 2 }$ 分别定义如

$$
\eta _ { 1 } = \frac { 1 - \displaystyle \frac { T _ { 2 } ^ { * } } { T _ { 0 } ^ { * } } } { 1 - \displaystyle \left( \frac { P _ { 2 } } { P _ { 0 } ^ { * } } \right) ^ { \left( \frac { k - 1 } { k } \right) } } , \eta _ { 2 } = \frac { 1 - \displaystyle \frac { T _ { 3 } ^ { * } \ll \gg } { \sqrt [ ] { T _ { \mathrm { i n } } ^ { * } } } } { \displaystyle \sum _ { k } ^ { k \ll \gg } \stackrel { \gg } { \left( \frac { P _ { 3 } ^ { * } } { P _ { \mathrm { i n } } ^ { * } } \right) ^ { ( \frac { k - 1 } { k } ) } } }
$$

式中，下标“in”、 $^ { 6 6 } 0 ^ { 3 }$ 、“1”、2”、“3”分别为进气道进口、静叶栅前缘、动叶栅尾缘、无叶扩压器出口。

![](images/b113480196bcab79b9e392d93fe08b57c7cceed6972219418e10539938f97a08.jpg)  
图7四种不同中心流线椭圆轴 $\mathbf { \alpha } _ { a }$ 长度的进气道Fig.7 Four different axis length of inlet center streamline

从表4可看出，进气道完全按照等截面设计时，不同的中心流线形状对性能的影响是不同的，中心流线椭圆轴 $\boldsymbol { a }$ 越小，离心透平的级效率、整机效率、轮周功都较高。这是由于进气口越接近叶栅，气流转弯的过程越短，叶栅进气越均匀，图 $9 { \sim } 1 2$ 为不同轴 $\mathbf { \Omega } _ { a }$ 值的轴截面马赫数云图， $a$ 为0.75b时，叶栅进口的马赫数最接近均匀。总体上，中心流线的椭圆轴 $\boldsymbol { a }$ 值的变化对离心透平性能影响较小，其中效率的最大与最小值相差小于 $0 . 5 \%$ ，轮周功的最大与最小值相差小于 $2 \%$ 。

![](images/ceaf49de7e3075b1cee42eeb791fe36df20dc5d587fcd62b9eba608a15dfeb27.jpg)  
图8进气道数值计算网格Fig.8 The inlet grid

从表4还可看出，进气道按照椭圆近似设计与等截面设计对比时，离心透平的效率和轮周功都没有较大偏差。因此，本文以近似设计的 $a = b$ 的进气道作为后续的基础。

# 表4不同中心流线的进气道数值计算结果

Table 4 The numerical results of inlet with   

<html><body><table><tr><td colspan="4">differentcenterstreamlines</td></tr><tr><td>中心流线 X轴a</td><td>级效率</td><td>整机效率</td><td>轮周功</td></tr><tr><td rowspan="3">a = 0.75b 等截面设计 a=b</td><td>n1/%</td><td>n2/%</td><td>P/kW</td></tr><tr><td>88.35</td><td>89.34</td><td>478.1</td></tr><tr><td>88.28</td><td>89.33 89.20</td><td>477.6 475.9</td></tr><tr><td rowspan="3">a=2b a=0.75b a = 1.5b Liet</td><td>88.12</td><td>89.10</td><td>475.4</td></tr><tr><td>88.01</td><td></td><td></td></tr><tr><td>88.20</td><td>89.28 89.28</td><td>475.9</td></tr><tr><td rowspan="3">近似设计 a=b a=1.5b a=2b</td><td>88.20</td><td>88.82</td><td>475.5</td></tr><tr><td>87.83</td><td></td><td>475.7</td></tr><tr><td>88.18</td><td>89.24</td><td>475.6</td></tr></table></body></html>

![](images/74c01f1d5019ee9ac61475526d97c0207aa873e10538a964564b352850184f02.jpg)  
图9 $a = 0 . 7 5 b$ 等截面设计的进气道轴截面马赫数分布云图 Fig.9 The Mach number distribution of inlet axial cross designed with uniform section and $a = 0 . 7 5 b$

![](images/896a36b9de8b39526a2666529935d3908750423cde63fd4931c8d4b3ba0efec5.jpg)  
图10 $a = b$ 等截面设计的进气道轴截面马赫数分布云图 Fig.10 The Mach number distribution of inlet axial cross designed with uniform section and $a = b$ （20

![](images/790b5c325ec0fbe0669581485263eb24559a63688f4e46cd899d1f3e97fa4255.jpg)

![](images/9a48e2efe4f369c691cc06490aeef13260faa774b3bf755458ca939e10236750.jpg)  
图11 $a = 1 . 5 b$ 等截面设计的进气道轴截面马赫数分布云图 Fig.11 The Mach number distribution oSimlet axial cross designed with uniform sectionand $\bar { a } = 1 . 5 b$ （204号   
图12 $a = 2 b$ 等截面设计的进气道轴截面马赫数分布云图 Fig.12 The Mach number distribution of inlet axial cross designed with uniform section and $a = 2 b$

# 3无叶扩压器设计

离心透平出口处气流绝对速度 $C _ { 2 }$ 一般已不大，但仍有一定的动能，如果能有效回收这部分能量，对离心透平的效率提高是显著的，无叶扩压器恰能使气流的速度降低、压气升高。表4中整机效率就是考虑无叶扩压器后得到的，比级效率高出 $1 \%$ 。

无叶扩压器是由两壳体侧壁构成的环形通道，其通道截面为一系列同心的圆柱面。无叶扩压器一般具有平行侧壁形式或收缩侧壁形式，本文采用与叶栅等高的平行侧壁形式设计，如图13所示， $D _ { 2 }$ 为动叶栅尾缘处直径，那么无叶扩压器的设计关键是要确定一个的最佳出口截面直径 $D _ { \mathrm { { 3 o p t } } }$ 。

一般在无叶扩压器流动中，不计密度 $\rho$ 的变化,当不考虑摩擦时，无叶扩压器中不同直径 $D$ 的速度$C$ 、压力 $P$ 、整机效率 $\eta _ { 2 }$ 可由下面的公式求出：

![](images/4c850c71be8ce673fdc6b7da7c366bbaed2c7f6d061e052aeab94408836550ef.jpg)  
图13无叶扩压器示意图Fig.13 The vaneless diffuser diagram

本文在已设计好的进气道、静叶栅、动叶栅的基础上，加上一段稍长的无叶扩压器，进行数值模拟计算，该无叶扩压器其实就是动叶尾缘后面的计算域，因此计算网格也如图8所示。图 $1 4 { \sim } 1 6$ 是初始无叶扩压器不同直径处 $D$ 的速度 $C$ 、压力 $P$ 和密度 $\rho$ 的公式理论结果与数值模拟结果对比，从图中可以看出，除去还受动叶栅斜切影响的一小段偏差较大，随直径 $D$ 的增大，公式计算的理论结果和数值模拟的结果相当吻合，说明按照密度不变计算无叶扩压器的速度、压气是可行的。

图17是初始无叶扩压器不同直径 $D$ 处的整机效率 $\eta _ { 2 }$ 的理论结果与数值模拟结果对比，从图中可看出，实际数值模拟得到的整机效率 $\eta _ { 2 }$ 并不会随直径 $D$ 一直增大，而是大概在 $1 . 0 3 D _ { 2 }$ 直径位置处出现最大值，之后实际整机效率 $\eta _ { 2 }$ 随直径 $D$ 增大而缓慢减少了。这是由于无叶扩压器并不是理想的无摩擦流动，实际流动过程中不同直径处的总温 $T _ { 3 } ^ { * }$ 增大，从而整机效率 $\eta _ { 2 }$ 公式中的分子也会减少，当整机效率 $\eta _ { 2 }$ 公式中分子减少的程度大于分母减少的程度时，整机效率 $\eta _ { 2 }$ 就会下降，图18为初始无叶扩压器不同直径 $D$ 处的总温 $T _ { 3 } ^ { * }$ 的理论结果与数值模拟结果对比，它的值确实是不断增大的。

基于上述讨论，无叶扩压器最佳出口截面直径$D _ { \mathrm { 3 o p t } }$ 可由初始无叶扩压器最佳整机效率对应的直径来确定，该最佳直径是无叶扩压器扩压降速和摩擦发热相互博弈的结果，本文最佳直径 $D _ { \mathrm { 3 o p t } }$ 为$1 . 0 3 D _ { 2 }$ 。

![](images/a3393b1cbf227ad3eaca540db3e0a646a5f67638639afe6deb8041660f85ee51.jpg)  
图14无叶扩压器理论与数值计算的速度随直径变化对比 Fig.14 The comparison of speed changewith diameter of the theory and numerical calculation in the vaneless diffuser

![](images/bf8e83feafefe11f1807e0202077ff72bc17c747d1be4d7e078176554cc8e500.jpg)  
图15无叶扩压器理论与数值计算的压力随直径变化对比 Fig.15 The comparison of press change with diameter of the theory and numerical calculation in the vaneless diffuser

![](images/d657b357448ced40f6560ff38adfd3ff6becc86e8bb43a76d2c32570dbc1d0ad.jpg)

![](images/23d5b4f0dc1193652117d7a9f9f135c94da2e4f0b07dc8380a74a72583d7773a.jpg)  
图16无叶扩压器理论与数值计算的密度随直径变化对比 Fig.16 The comparison of density change with diameter of the theory and numerical calculation in the vaneless diffuser

![](images/9c6747cebc5d71939b23bfb75ece892868ada05a70651a2ad079ec1c4b7b88bb.jpg)  
图17无叶扩压器理论与数值计算的效率随直径变化对比 Fig The comparison of efficiency change with diameter of the theory and numerical calculation in the vaneless diffuser   
图18无叶扩压器理论与数值计算的总温随直径变化对比 Fig.18 The comparison of total temperature change with diameter of the theoryand numerical calculation in the vaneless diffuser

# 4出气道设计

出气道的作用是集气和排气。一般来说，由无叶扩压器出来的气体在出气道还要继续降速和升压。图19为离心透平出气道的子午面示意图。

类似进气道，在出气道先按照等截面法来设计，出气道子午面的中心流线设计为 $a = b$ 的圆，Hub和 Shroud用 $1 / 4$ 椭圆近似。由出气道截面面积相等： $A { = } { \pi } D _ { 3 } H _ { 0 } { = } { \pi } D _ { 4 } L$ ，因为 $D _ { 4 }$ 大于 $D _ { 3 }$ ，所以出气道过流截线长度 $L$ 必然小于无叶扩压器宽度$H _ { 0 }$ 。现取两个出气道中心流线出口直径： $D _ { 4 } \ =$ $4 / 3 D _ { 3 }$ 、 $D _ { 4 } ~ = ~ 8 / 7 D _ { 3 }$ ，对应的出气道出口截线长度： $L \ = \ 3 / 4 H$ 、 $7 / 8 H$ ，对这两种出气道子午面进行设计，如图 20、21所示。

![](images/4ae45bfc4df6100d2ec6ff506026347708b6833404171005b577ea4c0f1dd531.jpg)  
图19出气道子午面示意图 Fig.19 The outlet meridian plane

![](images/26313ba8335cee20be00b9f0c248d50a17fa1cdf81335a263bce23cf3fe7a63c.jpg)  
图20 $D _ { 4 } { = } 4 / 3 D _ { 3 }$ 时，扩压设计和等截面设计 Fig.2O The outlet meridian plane design with diffusion and uniform section when $D _ { 4 } = 4 / 3 D _ { 3 }$

压器进行整机的数值模拟，数值模拟结果见表5。图$2 2 { \sim } 2 5$ 为四个不同出气道子午面的马赫数云图。

![](images/7bda43b312a41c979bb511514675bfd1a223d39e626db666a831f5eb5b66ac13.jpg)  
图2 $\downarrow D _ { 4 } = 8 / 7 D _ { 3 }$ 时，扩压设计和等截面设计Fig. 21 Outlet meridian plane designwithdiffusion anduniform section when $D _ { 4 } = 8 / 7 D _ { 3 }$

W从表5可看出,等截面设计时 (透平1,透平3),两个不同出口直径 $D _ { 4 }$ 的出气道的离心透平，透平的级效率基本一样，大出口直径！ $( D _ { 4 } = 4 / 3 D _ { 3 } )$ 的透平1要比小出口直径 $\left( D _ { 4 } = 8 / 7 D _ { 3 } \right)$ 的透平3整机效率高 $1 . 1 \%$ ，而轮周功只小 $0 . 2 \%$ ，同时对比图22、图24，大出口直径 $\left( D _ { 4 } = 4 / 3 D _ { 3 } \right)$ 的出气道轴截面马赫数分布要比小出口直径 $\left( D _ { 4 } = 8 / 7 D _ { 3 } \right)$ 的均匀；分别对比表5中的透平1、2和透平3、4，采用扩压设计$\begin{array} { r } { ( L = H _ { 0 } ) } \end{array}$ )之后，离心透平的级效率仍维持基本不变，整机效率和轮周功都有提高，从马赫数分布云图上也可看出，图23、图25的出口道轴截面马赫数分别比图22、图24低，出气道达到扩压降速的效果。

# 表5不同出口直径的出气道数值计算结果

Table 5 The numerical results ofdifferent outlet diameter   

<html><body><table><tr><td></td><td>出口直 径D4</td><td>出口截 线长度L</td><td>级效率 n1/%</td><td>整机效率 n2/%</td><td>轮周功 W/kW</td></tr><tr><td>透平1</td><td>4/3D3</td><td>3/4Ho</td><td>88.45</td><td>90.16</td><td>478.94</td></tr><tr><td>透平2</td><td>4/3D3</td><td>Ho</td><td>88.51</td><td>90.34</td><td>478.9</td></tr><tr><td>透平3</td><td>8/7D3</td><td>7/8Ho</td><td>88.5</td><td>89.06</td><td>479.8</td></tr><tr><td>透平4</td><td>8/7D3</td><td>Ho</td><td>88.48</td><td>89.62</td><td>482.7</td></tr><tr><td></td><td>一维气动计算</td><td></td><td>86.59</td><td></td><td>480</td></tr><tr><td></td><td>级模拟</td><td></td><td>88.22</td><td>89.41</td><td>486.1</td></tr></table></body></html>

如图20、21中扩压设计，为使出气道继续降速、升压，还对当前两个出口直径 $\langle D _ { 4 } = 4 / 3 D _ { 3 }$ 、 $D _ { 4 } =$ $8 / 7 D _ { 3 } )$ 的出气道出口截线进行延长，使其等于无叶扩压器宽度 $H _ { 0 }$ ，这时，Hub、Shroud 和中心流线为同圆心的 $1 / 4$ 圆弧。对如图20、21所示的4种出气道，加上设计好的进气道、静叶栅、动叶栅和无叶扩

透平2是较好的设计，数值模拟出来的级效率为 $8 8 . 5 1 \%$ ，整机效率为 $9 0 . 3 4 \%$ ，轮周功为 $4 7 8 . 9 \mathrm { k W }$ 性能均超过一维气动设计，相比单独的级模拟，级效率也提高 $0 . 3 \%$ ，整机效率提高 $1 . 1 \%$ 。因此在设计出气道子午面时，可采用扩压弯管设计，Hub、Shroud和中心流线采用同圆心的 $1 / 4$ 圆弧，在透平整体尺寸允许的范围内，尽量让出气道出口直径 $D _ { 4 }$ 大一些。

![](images/058144bac7d7b3d2987a7ae8fbe6dbd790dedef23b565f3dbbc9f6caf11027ea.jpg)  
图22 $D _ { 4 } { = } 4 / 3 D _ { 3 }$ 时，等截面设计出气道轴截面马赫数云图 Fig.22 The Mach number distribution of outlet axial cross designed with uniform section when $D _ { 4 } { = } 4 / 3 D _ { 3 }$

![](images/7ec6fa9a09ae264b6075a5a0a1b71f85e4df2a093a85918a823d1babd056d9cd.jpg)

![](images/3753c55bafe58fafda97fe3330f6ca3dd125cf650e6e93f595b1797c44aa450c.jpg)  
图23 $D _ { 4 } { = } 4 / 3 D _ { 3 }$ 时，扩压设计的出气道轴截面马赫数云图 Fig.23 The Mach number distribution of outletaXial cross designed with diffusion when D44/3D3

![](images/b1d8c6bb04cec34f088894360e4e8af4dcec1125e27144eb3f0d8351bbccd78b.jpg)  
图24 $D _ { 4 } { = } 8 / 7 D _ { 3 }$ 时，等截面设计出气道轴截面马赫数云图 Fig.24 The Mach number distribution of outlet axial cross designed with uniform section when $D _ { 4 } { = } 8 / 7 D _ { 3 }$ X   
图25 $D _ { 4 } { = } 8 / 7 D _ { 3 }$ 时，扩压设计的出气道轴截面马赫数云图 Fig.25 The Mach number distribution of outlet axial cross designed with diffusion when $D _ { 4 } { = } 8 / 7 D _ { 3 }$

# 5总结与展望

按照本文的方法设计的离心透平附属通流件具有较好的气动性能，能够完美得匹配动、静叶栅，设计方法简单、高效。最终设计出来的离心透平，数值模拟的级效率为 $8 8 . 5 1 \%$ ，整机效率为 $9 0 . 3 4 \%$ ，轮周功为 $4 7 8 . 9 \mathrm { k W }$ ，相比单独的级模拟，整机效率提高$1 . 1 \%$ 。其中各附属部件设计方法简要如下：

1）进气道子午面按照等截面法设计，中心流线采用1/4椭圆弧，设计了不同轴 $a$ 值的中心流线进气道子午面，数值计算结果表明，轴 $\mathbf { \Omega } _ { a }$ 值越小透平效率越高，但是总体影响确实不大，因此推荐采用轴长 $a = b$ 的圆弧作为中心流线。为使工程设计方便，可将Hub和Shroud设计成与中心流线同圆心的 $1 / 4$ 椭圆，头、尾处均与轴向和径向相切，近似设计之后的进气道对透平的气动性能影响极小，因此该近似方法是可行的。

2）无叶扩压器设计为与叶片等高的平行侧壁形式，具有降速扩压的作用，随着直径的增大，气流流动速度降低、压力升高，能使离心透平的效率提高，但是在实际流动中，气流在无叶扩压器中的摩擦发热会使效率降低，直径越大发热越多，因此存在一个最佳的直径使整机效率最高，本文最佳直径 $D _ { \mathrm { 3 o p t } }$ 为 $1 . 0 3 D _ { 2 }$ 。

3）出气道子午面设计成与叶栅等高的圆弧扩压弯管形式,Hub、Shroud和中心流线设计为同圆心的$1 / 4$ 圆弧，间距为叶高 $H _ { 0 }$ ，出口直径 $D _ { 4 }$ 在透平整体尺寸允许的范围内可设计较大些。

# 参考文献

[1] Casati E, Vitale S,Pini M, et al. Centrifugal Turbines for Mini-organic Rankine Cycle Power Systems [J]. Journal of Engineering for Gas Turbines and Power, 2014,136(12): 122607   
[2] Persico G,Pini M,Dossena V,et al.Aerodynamic Design and Analysis of Centrifugal Turbine Cascades [C]//ASME Turbo Expo 2O13: Turbine Technical Conference and Exposition.American Society of Mechanical Engineers, 2013:V06CT40A019   
[3]Persico G,Pini M,Dossena V,et al.Aerodynamics of Centrifugal Turbine Cascades [J]. Journal of Engineering for Gas Turbines and Power,2015,137(11):112602   
[4] Pini M,Persico G,Casati E,et al. Preliminary Design of a Centrifugal Turbine for Organic Rankine Cycle Applications [J].Journal of Engineering for Gas Turbines and Power,2013,135(4):042312   
[5]谭鑫，李银各，林显巧，等.离心式透平的变工况特性研究 [J].工程热物理学报,2016,37(6)：1201-1207 TAN Xin,LI Yinge,Lin Xiangqiao,et al. Research on OffDesign Characteristics of Centrifugal Turbine [J].Journal of Engineering Thermophysics,2016,37(6):1201-1207   
[6]李银各，谭鑫，林显巧，等.离心式透平的热力设计与分析 [J].工程热物理学报，2016,37(10)：2103-2109 LI Yinge,TAN Xin,Lin Xiangqiao,et al.The Thermal Design and Analysis of Centrifugal Turbine [J].Journal of Engineering Thermophysics,2016,37(10):2103-2109   
[7]谭鑫,郭慧婧,李会,等.基于NURBS 曲线的离心透平叶型 设计[J].热能动力工程,2017(3)：52-58 TAN Xin,GUO Huijing,LI Hui,et al. The Centrifugal Turbine Blade Design Based on the NURBS Curve [J]. Journal of Engineering for Thermal Energy and Power, 2017(3): 52-58   
[8] Wang Y,Wang K,Tong Z,et al. Design and Optimization ofa Single Stage Centrifugal Compressor fora Solar Dish-Brayton System [J]. Journal of Thermal Science, 2013,22(5):404-412   
[9]Hathaway MD,ChrissRM,WoodJR,et al.Experimental and Computational Investigation of the NASA LowSpeed Centrifugal Compressor Flow Field [J].Journal of Turbomachinery, 1993,115(3):6350-6359   
10]高丽敏，刘波，王欢．无叶扩压器对离心压缩机流场及性能 影响的数值研究[J].中国机械工程，2008，19(17)：2098- 2102 GAO Liming,LIU Bo,WANG Huang. Numerical Investigation of the Influence of Vaneless Diffusers on the Flow and Performance of a Centrifugal Compressor [J].China Mechanical Engineering,2008,19(17):2098-2102   
[11]李莹，陈榴,戴韧,等.径向涡轮叶片子午面型线的优选设计 [J].工程热物理学报,2013,34(5)：853-857 LI Ying,CHENG Liu DAI Reng. Meridional Shape Op timization of Radial Inflow Turbine Impeller [J].Kung Cheng Je Wu LIHsueh Pao/journal of Engineering Thermophysics,2013,34(5):853-857   
[12]王慧,李水莲，魏新利．向心透平叶轮子午面形状等腰梯形 设计法[J].机械科学与技术,2015,34(5)：678-682 WANG Hui,LI Shuilian,WEI Xinli.Isosceles Trapezoid Design Method to Develop the Meridional Profile on Impeller[J].Mechanical Science& Technology forAerospace Engineering,2015,34(5):678-682   
[13]王仲奇，秦仁.透平机械原理[M].北京：机械工业出版 社，1981:310-336 WANG Zhongqi, QIN Ren. Turbomachinery Principle [M] Beijing Mechanical Industry Press,1981: 310-336

![](images/6b7a1f622171f8cad5b498458712acaeacbfd71f97427f880fd528c17b4f58b5.jpg)