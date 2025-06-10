LiuNannan,ZhouBin.Infuenceoffuxgate magnetometerontheevennessoffeedback magneticfeld (inChinese).Chin.J Space Sci., 2015,35(2):211-216,doi:10.11728/cjss2015.02.211

# 反馈磁场均匀性对磁通门磁强计的影响分析

刘楠楠1,2 周斌1

1(中国科学院空间科学与应用研究中心北京 100190)

2(中国科学院大学北京 100049)

摘要针对磁通门传感器的特点，研究了反馈线圈对磁通门传感器探测数据的影响，并对比了几种典型结构的传感器：磁通门传感器要求激励线圈工作在均匀磁场环境下，非均匀场会引入误差信号.根据磁通门原理进行了理论推导，非均匀性会导致反馈原理工作的磁通门传感器线性系数发生变化．针对应用于空间磁场探测的几种磁通门传感器常见结构，即分立结构型、亥姆霍兹型和紧凑球面型等，分析了传感器内部磁场的均匀性及对磁场探测的影响：经仿真计算分析发现，紧凑球型传感器的内部均匀性和稳定性优于分立结构传感器，更有利于空间磁场探测！

关键词磁场探测，磁通门磁强计，反馈线圈 中图分类号V447，P353.1

# Influence of Fluxgate Magnetometer on the Evenness of Feedback Magnetic Field

LIU Nannan $_ { . } ^ { 1 , 2 }$ （204号 ZHOU Bin1

1(Center for Space Science and Applied Research,Chinese Academy of Sciences,Beijing 100190)

2(University of ChineseAcademyofSciences,Beijing lo0049)

Abstract Efects of the nonuniform feedback magnetic feld on the fuxgate sensor is studied,and several typical types of the sensor are analyzed and compared mutually. It is required that the drive cores of fluxgate sensor should work in a uniform magnetic field in principle.When the magnetic feld is nonuniform,error signal will be caused.Resultingly,the nonuniformity of the feedback magnetic field will lead to the change of fluxgate sensor's linear coeffcient. Typical types of fuxgate sensors which work for space magnetic exploration include discrete form,Helmholtz form and Compacted Spherical Configuration (CSC) form, etc. The nonuniformity of the three fedback coils are analyzed as well as the performance of the fuxgate sensor when the feedback magnetic field is nonuniform. Compared to the simulation results,uniformity and stability of CSC sensor are much better than that of the discrete sensor,and CSC sensor is more conducive to the space magnetic field detection. Key wordsMagnetic field exploration, Fluxgate magnetometer, Feedback coil

# 0 引言

磁场探测对于地磁场模型研究、空间环境探测、深空探测等具有重要意义．早期磁场探测所用磁强计注重于分辨率性能，例如美国NASA的Themis卫星[1]、ESA 和 NASA 共同研发的Cluster 卫星[2]以及中国双星系列卫星和萤火一号火星探测器[3上搭载的磁强计，在应用于空间环境探测时，注重探测磁场的相对变化.近年来由于技术的日益成熟，磁场探测逐渐重视磁强计的准确性和稳定性，例如丹麦科技大学（DTU）的Orsted卫星[4]、ESA 的Champ和 Swarm 等卫星上搭载的磁强计[5]，用于地磁场测绘，注重测绘数据的绝对精度.

磁通门磁强计是主要的磁场探测载荷，其优点为灵敏度及可靠性高，可测量矢量和梯度，技术成熟;缺点是测量准确性低，需要地面定标．目前磁通门磁强计的工作模式一般为反馈模式，依靠反馈线圈提供的反馈磁场保持激励线圈在稳定的小场模式下工作，反馈磁场直接影响磁通门磁强计的线性度、稳定度等性能指标.目前磁通门传感器的结构有分立结构、亥姆霍兹结构和紧凑球型结构，其区别主要是反馈线圈的实现形式．本文针对反馈磁场均匀区对磁场探测的影响进行了研究.

# 1非均匀磁场对磁通门探测的影响分析

磁通门传感器主要部分由高磁导率磁芯、激励线圈、信号线圈和反馈线圈组成.磁芯通常采用铁、钴、镍及其合金等高导磁材料.沿磁芯绕制的线圈称为激励线圈，激励线圈外层绕制的是信号线圈，最外层则是反馈线圈．反馈线圈的作用是产生大小等同外场而方向与其相反的反馈磁场来抵消外界磁场，此时激励线圈与信号线圈处于零场中，磁通门磁强计工作在闭环状态.

激励线圈一般采用环形磁芯，信号线圈绕制在激励线圈外,如图1所示.磁芯材料通常为坡莫合金，由于坡莫合金导磁率高且矫顽力低，其磁化曲线可近似表示为图2(a）的形式．激励线圈中通入正弦交流激励电流，激励磁场强度 $H _ { 1 }$ 如图2(c)所示，有

$$
H _ { 1 } ( t ) = H _ { \mathrm { m } } \cos 2 \pi f t .
$$

其中， $H _ { \mathrm { m } }$ 为激励磁场幅值．当外界磁场为0时，左右半环磁芯中产生的感应磁场强度大小相等,方向相反，正好相互抵消，如图2(b)所示.

当外界磁场 $H _ { \mathrm { e } }$ 存在时,有

$$
\begin{array} { r } { B _ { 1 } = \mu [ H _ { \mathrm { e } } + H _ { 1 } ( t ) ] , } \\ { B _ { 2 } = \mu [ H _ { \mathrm { e } } - H _ { 1 } ( t ) ] . } \end{array}
$$

$B _ { 1 }$ 和 $B _ { 2 }$ 如图3(c）中实线所示. $B _ { 1 } + B _ { 2 } \neq 0$ ，由于外场的存在而产生周期性畸变，磁芯中磁感应强度之

1 1 $\textstyle H _ { \mathrm { e } }$ ） A X Z A driving core signal core 和如图3(d）中实线所示.信号线圈中感应电动势

![](images/4ecd1152daacb59ef60f4bc275b134895d21004c558ac9904e93010f9c856099.jpg)  
图1环形激励线圈与信号线圈Fig.1Drive coil and pick-up coil  
图2无外场时激励磁场在磁芯中感生磁场 $B _ { 1 }$ 和 $B _ { 2 }$ Fig.2Ring core's magnetic field $B _ { 1 }$ and $B _ { 2 }$ caused by drive coil when extra magnetic is zero

$$
e ( t ) = - S N { \frac { \mathrm { d } } { \mathrm { d t } } } ( B _ { 1 } + B _ { 2 } ) .
$$

其中， $N$ 为信号线圈匝数， $\boldsymbol { S }$ 为磁芯横截面积．如图3(e）中实线所示．对 $e ( t )$ 进行傅里叶展开，得到的结果中二次谐波分量幅值 $e _ { \mathrm { m } }$ 与外磁场强度成正比 $\left[ 6 - 7 \right]$ ，定义其比例系数为 $k$ ，有

$$
H _ { \mathrm { e } } = k e _ { \mathrm { m } } .
$$

反馈线圈内部产生均匀磁场，以此补偿外磁场，使磁芯工作在零场附近，以提高磁通门系统的线性度和信号稳定度.当外场完全抵消时，此时测量反馈电流的大小来度量外磁场沿轴向分量的大小，因此反馈线圈的性能很大程度上影响着传感器的性能．假设外场反馈线圈产生的反馈磁场不均匀，激励线圈一半工作在零场，一半工作在磁场强度为 $H _ { 2 }$ 的磁场中.当外界磁场 $H _ { \mathrm { e } }$ 存在时，式(2）可转化为

$$
\begin{array} { l } { { B _ { 1 } = \mu [ H _ { \mathrm { e } } + H _ { 1 } ( t ) + H _ { 2 } ] , } } \\ { { B _ { 2 } = \mu [ H _ { \mathrm { e } } - H _ { 1 } ( t ) ] . } } \end{array}
$$

为便于计算，简化磁芯磁导率模型，设导磁率 $\mu$ 可 使 $B$ 满足

$$
B = \left\{ \begin{array} { l l } { 0 . 6 , } & { H \geqslant 3 ; } \\ { 0 . 2 H , } & { - 3 \leqslant H < 3 ; } \\ { - 0 . 6 , } & { H < - 3 . } \end{array} \right.
$$

$B _ { 1 }$ 变化如图3(c)中虚线所示， $B _ { 1 } + B _ { 2 }$ 变化如图3(d)中虚线所示, $e ( t )$ 变化如图3(e)中虚线所示.测得 $e _ { \mathrm { m } }$ 后，按照式(4)得到的外磁场强度 $H _ { \mathrm { e } } ^ { \prime }$ 与真实的外磁场强度 $H _ { \mathrm { e } }$ 存在差值.

根据实际情况，式（1）中 $H _ { \mathrm { m } } = 5 \mathrm { T }$ ， $\begin{array} { r l } { f } & { { } = } \end{array}$ $1 0 0 0 0 \mathrm { { H z } }$ ．当反馈磁场均匀时，外场 $H _ { \mathrm { e } }$ 与二次谐波幅值 $e _ { \mathrm { m } }$ 的关系为

$$
H _ { \mathrm { e } } = 7 . 6 7 9 9 \times 1 0 ^ { - 4 } e _ { \mathrm { m } } .
$$

假设反馈磁场不均匀，实际反馈磁场的不均匀程度与外场大小成正比，设 $H _ { 2 } = 0 . 0 1 H _ { \mathrm { e } }$ ，外场强度与二次谐波幅值关系为

因此反馈磁场不均匀时会导致灵敏度改变，

磁通门磁强计反馈线圈由于绕线的对称性，产生的反馈磁场也是对称的.严格将激励线圈沿反馈磁场对称中心放置，可以利用反馈磁场的对称性避免反馈磁场不均匀带来的影响．但是磁强计在安装和使用过程中，不可避免会有装配公差、应力释放或者热膨胀，导致激励线圈不处于反馈磁场正中心，这种影响等效于反馈磁场不均匀，会给传感器带来灵敏度偏差．因此传感器反馈线圈的均匀性对整个磁通门磁强计的稳定性有很大影响，

# 2 反馈线圈均匀性分析

卫星磁测常用的磁通门磁强计类型有紧凑球面型、亥姆霍兹型和分立结构型，其区别主要在于反馈线圈的实现形式，如图4所示.

以下对这三种反馈线圈的均匀性进行分析．设均匀区为外磁场 $5 0 0 0 0 \mathrm { n T }$ 时反馈磁场波动 $1 0 0 0 \mathrm { n T }$ 以内的区域.

紧凑球面型反馈线圈采用环形反馈线圈沿球面对称排布，正交三方向的每个方向排列4对大小相等的环形线圈，每个线圈通过相同大小的电流.通过调整各反馈线圈的匝数，使所有反馈线圈形成的总磁场均匀且等于外界磁场.这类型的磁通门磁强计搭

$$
H _ { \mathrm { e } } = 7 . 7 1 8 3 \times 1 0 ^ { - 4 } e _ { \mathrm { m } } .
$$

![](images/6e03bbc5452141f6fd1010f38ef3452bd0384c17899090c032dee098df7274a7.jpg)  
图3信号线圈感生电动势原理及不均匀反馈磁场的影响 (虚线)  
Fig.3Electromotive force induced in the sense coil and the effect of nonuniform feedback magnetic (dotted line)

载于Swarm,Champ，Oersted等卫星上.任意方向反馈线圈中轴线附近的磁场分布可根据环电流中轴线磁场分布叠加得到，即

$$
B = \sum _ { i = 1 } ^ { n } B _ { i } = { }
$$

$$
\sum _ { i = 1 } ^ { n } \frac { \mu _ { 0 } N _ { i } I } { 2 } \frac { R _ { i } ^ { 2 } } { \left[ R _ { i } ^ { 2 } + \left( \frac { R _ { i } } { 2 } + x _ { i } \right) ^ { 2 } \right] ^ { \frac { 3 } { 2 } } } .
$$

其中, $\mathbf { \chi } _ { i }$ 为 $1 \sim 8$ ， $\mu _ { 0 }$ 为真空磁导率, $N _ { i }$ 为线圈匝数，$I$ 为线圈中通入的电流强度0.002A, $R _ { i }$ 为线圈半径，$x _ { i }$ 为中轴线上点到线圈的距离，各对线圈直径从小到大分别为35，60，75， $8 0 \mathrm { m m }$ ：根据仿真结果，相应线圈匝数分别为355，486，500，436时能产生比较均匀的磁场.

亥姆霍兹型反馈线圈由三组轴向相互正交的亥姆霍兹线圈嵌套而成.这种类型的磁通门磁强计搭载于Rosetta,Themis,Venus Express 等卫星上.亥姆霍兹线圈为一对互相平行且共轴的载流圆环,其间距等于半径．特点是线圈轴中心附近磁场是近似相等的，磁场分布可认为是紧凑球面型的特例，即只有一对线圈的紧凑球面型.根据仿真结果，线圈匝数600、电流强度 $\mathrm { 0 . 0 0 5 A }$ 、线圈半径 $3 6 \mathrm { m m }$ 时能产生需要的反馈磁场.

分立结构型反馈线圈是早期磁测卫星采用的结构．环形激励线圈放在方形的线圈骨架里，方形线圈骨架外先绕制的是信号线圈，后绕制的是反馈线圈．这种类型的磁通门磁强计广泛应用于各类磁测卫星，例如双星计划、萤火一号、GOES以及Clus-ter等.分立结构型反馈线圈外形为方形，反馈磁场类似于螺线管，可利用比奥萨法尔定律积分得到．按照分立结构型的一般设计，反馈线圈紧紧包围着信号线圈和激励线圈.可以设反馈线圈长 $\mathrm { 3 0 m m }$ 宽 $2 4 \mathrm { m m }$ 高 $\mathrm { 1 5 m m }$ ：由于分立结构型反馈线圈分为三个，每个线圈各为其中的激励线圈提供反馈磁场，计算均匀度时,按一个反馈线圈计算

根据以上数据对三种类型的反馈线圈一个方向分量建立3D模型并进行电磁场仿真，得到过中轴线截面的磁感应强度分布，如图5所示.图中圆形粗实线代表激励线圈位置，虚线包围区域代表 $1 0 0 0 \mathrm { n T }$ 均匀区.

在分析磁通门磁强计反馈磁场均匀性时，设定均匀度为一个统一的比较标准,即反馈线圈 $1 0 0 0 \mathrm { n T }$ 均匀区体积与传感器体积的比值.根据仿真结果可以还得到三种结构的磁强计均匀度性能，结果列于表1.

![](images/112eef82542e5c1f580c98c9463b9a0d35783d282069ef8b29c0e4df7b2b500c.jpg)  
图4三种结构磁通门磁强计.(a)紧凑球面型，(b)亥姆霍兹线圈型，(c)分立结构型 :Three forms of fluxgate sensors.(a) CSC sensor,(b) Helmholtz sensor,(c) discrete sensc

![](images/e6c0277891ca164e522f38d70606e995c8027ff0763e469f4114f54333c0251d.jpg)  
图5反馈磁场分布.(a)紧凑球面型，(b)亥姆霍兹型,(c)分立结构型rig.5Feedback magnetic.(a) CSC coils,(b） Helmholtz coils,(c) discrete coils

# 3反馈线圈非均匀性对磁强计稳定性的影响分析

由于磁通门磁强计的设计不可避免地存在公差装配后激励线圈的位置与原设计位置可能存在偏差磁通门磁强计在使用过程中遇到机械震动、应力释放或热膨胀等情况时也可能造成激励线圈位置偏差考虑到环境温度的变化还会造成线圈的形变，原本处于对称的均匀反馈磁场中的激励线圈（图6中实线圆)在发生热变形后 (图6中虚线圆)处于了不均匀反馈磁场中.根据前面结论，图6中激励线圈的位置变化等效于反馈磁场不均匀，从而导致磁强计的灵敏度发生改变，造成磁强计性能不稳定．因此反馈线圈的均匀性对磁强计稳定性有很大影响，

设激励线圈磁芯材料为高温钢，三种磁通门传感 器均采用直径 $2 0 \mathrm { m m }$ 的环形激励线圈.环境温度从

# 表1三种类型磁强计均匀度

Table 1 Nonuniformity of the three fluxgate sensors   

<html><body><table><tr><td>类型</td><td>紧凑球面型</td><td>亥姆霍兹型</td><td>分立结构型</td></tr><tr><td>均匀度/(%)</td><td>16.64</td><td>1.01</td><td>0.48</td></tr></table></body></html>

![](images/97d091ae84580566a3b314298d7a967aeebfd5fa45baf4ecf5454b0355538be9.jpg)  
图6激励线圈的热变形 Fig.6Ring core's thermal deflection

# 表2热变形对三种类型磁强计的影响

Table 2 Effect of ring core's thermal deflection   

<html><body><table><tr><td>类型</td><td>紧凑 球面型</td><td>亥姆</td><td>分立结</td></tr><tr><td>灵敏度偏差(×10-4)</td><td>0.052</td><td>霍兹型 0.83</td><td>构型 3.1</td></tr><tr><td>偏移量/nT</td><td>+0.34</td><td>+4.00</td><td>+15.55</td></tr></table></body></html>

注偏移量为测量 $5 0 0 0 0 \mathrm { n T }$ 外场时测量值与实际 值的差值.

$- 1 0 0 ^ { \circ } \mathrm { C }$ 到 $1 0 0 ^ { \circ } \mathrm { C }$ 时，对三种类型磁强计的激励线 圈进行热学仿真，结果表明 $1 0 0 ^ { \circ } \mathrm { C }$ 时激励线圈直径 比 $- 1 0 0 ^ { \circ } \mathrm { C }$ 时大 $0 . 0 5 2 \mathrm { m m }$ ．根据上述仿真分析，激励 线圈热变形后对三种磁强计性能的影响列于表2.

由表2可知，反馈线圈均匀度越大，在激励线圈偏移时，灵敏度偏差则越小.反馈磁场的不均匀程度对磁强计的稳定性具有一定影响.

# 4结语

根据磁通门原理，磁通门磁强计反馈磁场的不均匀性会造成测量结果偏差，影响磁通门磁强计的灵敏度.工程上加工装配误差以及装配后的应力释放或者冷热膨胀，都会使激励线圈所处反馈磁场不能保证均匀和一致，进而会导致应用过程中灵敏度发生变化，使测量出现误差．对三种常用类型磁通门磁强计的反馈磁场进行了仿真分析，结果表明反馈线圈均匀度越大，灵敏度偏差越小.因此均匀的反馈磁场可以大大提高磁强计的稳定性.随着弱磁场测量技术的发展，卫星磁测对磁强计的性能要求越来越高，在对磁强计稳定性要求极高的磁测领域，紧凑球面型磁强计具有更大的优势

# 参考文献

[1]Auster H U,Glassmeier K H,Magnes W，et al.The THEMIS fluxgate magnetometer[J]．Space Sci. Rev., 2008,141:235-264   
[2] Balogh A,Dunlop MW,Cowley SWH,et al. The Cluster magnetic field investigation [J].Space Sci.Reu.,1997, 79:65-91   
[3] Zhou Bin，Zhao Hua,Wang Jindong,Chen Siwen,Liao Huaizhe,Zhu Guangwu,Wang Chi,Zhang Xin,Li Lei, Sun Yueqiang,Feng Yongyong,Zhou Jingxuan,Tao Ran. Martian space environment magnetic field investigationHigh accuracy magnetometer[J].Chin.J. Space Sci., 2009，29(5):467-474．In Chinese(周斌，赵华，王劲东，陈 斯文，廖怀哲,朱光武，王赤,张鑫,李磊,孙越强,冯永勇，周敬 萱，陶然.火星空间环境磁场探测研究—高精度磁强计[J].空 间科学学报，2009,29(5):467-474)   
[4] Nielsen O V,Petersen JR,PrimdahlF,et al.Development,construction and analysis of the 'OErsted’fluxgate magnetometer[J].Meas.Sci.Tech.,1995(6):1099-1115   
[5] Merayo JMG,Jorgensen JL,Friis-Christensen E,et al. The Swarm magnetometry package [C]//Small Satellites forEarth Observation.Berlin:6th Symposium on Small Satellites for Earth Observation of IAA,2007   
[6] Zhang Xuefu,Lu Yiliang.Fluxgate Technology [M].Beijing:National Defense Industry Press,1995.In Chinese (张学孚，陆怡良．磁通门技术[M]．北京：国防工业出版社, 1995)   
[7] Primdahl F.The fluxgate magnetometer[J].J.Phys.E: Sci.Inst.,1979,12:241-253