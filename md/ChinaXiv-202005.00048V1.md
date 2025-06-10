# 射电干扰中基于测距的定位算法研究

赵清华¹，李建斌23，张涛1

（1.青海省无线电监测站，西宁 810002；2.中国科学院国家天文台，北京 100101；3.中国科学院大学，北京 100049）

【摘要】对于射电望远镜观测的天文研究，即使很微弱的射频干扰也会导致观测失败或降效。当前射电望远镜台址射频干扰越来越多，需尽快尽量将射频干扰源找到并予以消减。无线定位技术成为查找干扰源时，获取射频发射源准确位置的重要技术手段。基于测距的无线定位算法因其定位精度高，稳定性强而备受关注。本文对几种基于测距的无线定位算法进行研究，分析比对这几种测距定位算法的特点。通过比对，TDOA(Time Difference of Arrival，基于到达时间差)定位算法计算复杂度低，定位精度高；RSSI(ReceivedSignal Strength Indication，基于接收信号强度)定位算法简单易于实现。在此基础上提出了一种基于TDOA定位算法和RSSI定位算法数据融合的测距无线定位算法，该算法在通过TDOA定位算法获得多个初始位置估计值的基础上引入以信号接收强度作为初始位置估计值的权值的数据融合方式，通过线性加权归一化处理获得一个定位精度较高的位置估计值。因信号接收强度易于获得，该数据融合算法在TDOA定位算法基础上增加的计算量较小，且仿真结果表明该算法较单一的TDOA定位算法降低了约 $20 \%$ 的定位误差，有效提高了定位精度，便于快速低成本发现射频干扰源。

【关键词】无线定位射频干扰 测距 数据融合定位精度中图分类号：TNO；P161.4 文献标识码：A 基金项目（国家自然科学基金11173037）

# The Research on Range Based Location Algorithms in Radio Interference

Zhao Qinghua'，Li Jianbin2.³， Zhang Tao1 (1.Qinghai RadiooitoringStation,Xiing,0o;.atioalAstrooicalObervatoryofChin,Beijig,01;3Uesity of Chinese Academy of Sciences, Beijing,100049)

【Abstract】For astronomical studies observed by radio telescopes,even very weak radio frequency interference signals can cause observation failures or reduced efficiency.Radio frequency interference at radio telescope sites is increasing,and it is necessary to find and reduce the source of radio frequency interference as soon as possible.Wireless positioning technology has become an important technical means to obtain the accurate position of the radio frequency emission source when searching for the source of interference.Range based radio positioning algorithms have attracted much atention because of their high positioning accuracy and strong stability.This paper studies several radio positioning algorithms based on ranging,and analyzes and compares the characteristics of these several ranging positioning algorithms. Through comparison,the TDOA(Time Diference Of Arrival) positioning algorithm has low computational complexity and high positioning accuracy,and the RSSI(Received Signal Strength Indication) positioning algorithm is simple and easy to implement. On this basis,a ranging wireless positioning algorithm based on the data fusion of TDOA positioning algorithm and RSSI positioning algorithm is proposed.The algorithm introduces a data fusion method that uses signal reception strength as the weight of the initial position estimate based on multiple initial position estimates obtained by the TDOA positioning algorithm, then obtains a position with high positioning accuracy through linear weighted normalization processing estimated value.Because the signal reception strength is easy to obtain,the data fusion algorithm adds less calculation to the TDOA positioning algorithm,and the simulation results show that the algorithmreduces the positioning error by about $20 \%$ compared to the single TDOA positioning algorithm, effectively improving the positioning accuracy,It is convenient to find radio frequency interference sources quickly and at low cost.

# 【Keywords】 Wireless positioning; Radio Frequency Interference; Range Based; Data Fusion; Positioning Accuracy

# 1概述

射电望远镜观测的天文研究与一系列国际天文热点问题联系密切，射电望远镜作为高灵敏无线电信号接收设备，也可服务于国防、导航授时和遥感遥测等应用服务。对所有观测，非常微弱的射频干扰信号也会导致观测失败或降效，需要极少射频干扰、极低电磁背景噪声的台址，对于高频观测还需要水汽很少，并对其持续监测和保护。射电天文使用的大多频段需与其它有源业务共用，在射电天文频段的上、下邻频段均存在有源业务，这些业务已经或将可能对射电天文业务造成有害干扰，导致部分观测波段、部分观测时间或部分天空覆盖的损失，降低了望远镜有效运行。射电望远镜台址通过设立电磁环境保护区的形式可减少来自地面的干扰，但由于新业务产生的新发射源，或故障导致发射源的特性改变，尤其是部分移动台站的突然闯入或违规发射，将极大地增加望远镜的运行风险。射电望远镜周边存在大量的有源发射业务，由于不同业务具有各自的发射特征，可利用定位技术及时发现对射电望远镜造成干扰的射频发射源，这对保护望远镜的有效运行非常重要。

无线定位技术作为一项关键技术在移动通信、卫星通信、无线传感网络、航空器定位以及无线电管理等无线通信技术中发挥着至关重要的作用，主要用于紧急救援定位、交通工具导航、无线通信干扰源的定位、移动台跟踪、手机用户区域切换和计费、传感器节点定位跟踪、非法无线电发射台站的查找等需要获得位置信息的诸多领域。因获取位置信息的重要性使无线定位技术无处不在，且随着定位算法的不断优化，定位精度的不断提高，其应用范围也越来越广泛。无线定位就是利用无线电波的传播特性确定电磁辐射源的位置，是指测量接收机通过对接收到的无线电信号的一些参数进行分析，根据特定的算法获取被测物体的位置信息2。测量参数一般为传输时间、幅度、相位、电场强度和到达角等。定位精度高、计算复杂度低，且具有良好的可靠性和鲁棒性是一个性能优良的定位算法必须具备的特性。影响定位精度的主要因素有：非视距传播(NLOS)、多径干扰、多址干扰、远近效应、噪声、定位算法的选择等。

将无线电定位技术应用于射电望远镜射频干扰的查找中，通过定位算法或其他手段及时发现射频干扰源并予以排除或减弱，保护射电望远镜的有效运行，一定程度上降低望远镜的运行风险。

# 2 测距定位算法

无线定位技术按照定位过程中是否进行距离测量分为以下两类：1、基于非测距（Range free）的定位：该定位算法在定位过程中不需要获取距离信息，而是通过节点间的连通性以及节点邻近信息定位，其计算复杂度低，成本低，多用于无线传感器网络（Wireless Sensor Networks，WSN）中。基于非测距的算法有：质心算法(Centroid)、DV-hop 算法（Distance-Vector hop）算法、近似三角形内点测试算法(ApproximationPoint-in-triangulation Test,APIT)、多维尺度法（Multidimensional Scaling,MDS)算法等[3]; 2、基于测距(Rangebased）的定位：该定位法是基于节点间的长度和方位角等距离信息进行定位的，其算法有：基于到达角(Angle of Arrival，AOA)定位算法、基于接收信号强度(Received Signal Strength Indication，RSSI)定位算法、基于到达时间(Time of Arrival，TOA)定位算法、基于到达时间差(Time Difference of Arrival，TDOA)定位算法[4]、差分多普勒(Frequency Difference of Arrival，FDOA)定位算法等。如图1所示：

![](images/d0a3b609b127800c7c42e41bfc60554d55e9c2e836676249a4cdb6bc06ee54f3.jpg)  
图1.按测距与否无线定位技术分类

![](images/ed50d8c62e190ff555bdba598abd62ed89703be6b1c56bf7b1e7eee46d8fd0a9.jpg)  
Fig1. Classification of wireless positioning technologies   
图2.AOA定位原理示意图Fig2.Schematic diagramof AOA

# 2.1基于到达角（AOA）定位算法

AOA定位算法即为交叉测向定位法。它是通过在不同的位置上多次测量方位，测得待定位信号源的方位角，再利用方位线的交汇实现定位或者通过地面固定多站的测角系统所测得的指向线交汇实现定位[5]。

其定位原理如图2所示，A、B为测向监测站，T为待定位的射频信号源。测向监测站根据参考方向，可以测得 $\mathfrak { a }$ 与β两个方位角，继而得到两条方位线，方位线交点处即为T的位置所在。AOA工作原理简单，其定位精度受监测站和信号源之间的距离影响较大，距离越大，定位精度越低。多径干扰对AOA定位算法影响较大，会导致误差变大，定位精度降低。

# 2.2基于到达时间（TOA）定位算法

TOA定位算法是指由两个或多个监测站测得待定位信号源发射的信号到达监测站的传播时间，根据

$$
\mathrm { L = c \Gamma \left( T + T _ { n } \right) + g }
$$

其中，L为信号源与监测站之间的距离；c为电磁波传播速度，自由空间中可取 $\scriptstyle \mathbf { c } = 3 \times 1 0 ^ { 8 }$ 米/秒；T为信号到达时间； $\mathrm { \Delta T _ { n } }$ 为钟差及传播过程导致的时间误差；ε为未知因素、模型误差等，计算出信号源与监测站之间的距离。以各监测站为圆心，监测站到信号源之间的距离为半径作圆，得到两个或者多个圆，这些圆的交点理论上就是待定位信号源的位置[]。

![](images/a51491a7e1b7bee936cf08b253f5121b1e6e24e6578952d7110ebb769277d487.jpg)  
图3.TOA定位原理示意图Fig3.Schematic diagramof TOA

![](images/a4c0c3d1b78b05ab0057b43236eb3b97bf29934fc1d537de3e6f2f83c638e111.jpg)  
图4.TDOA定位原理示意图Fig 4.Schematic diagram of TDOA

如图3所示，有A、B、C三个监测站对信号源T进行定位，设其坐标分别为 $\mathsf { A } ( x _ { 1 } , y _ { 1 } )$ ， $\mathbf { B } ( x _ { 2 } , y _ { 2 } )$ ， $\mathbf { C } ( x _ { 3 } , y _ { 3 } )$ ，T $( x , y ) ^ { \cdot }$ ）根据监测站得到的信号到达时间计算得出信号源到各个监测站之间的距离为D1、D2、D3，分别以D1、D2、D3为半径作圆，建立如下式方程组，求解方程组，三圆交点处即为信号源的位置。

$$
\left\{ \begin{array} { l l } { ( x - x _ { 1 } ) ^ { 2 } + ( y - y _ { 1 } ) ^ { 2 } = \mathbf { D _ { 1 } } ^ { 2 } } \\ { ( x - x _ { 2 } ) ^ { 2 } + ( y - y _ { 2 } ) ^ { 2 } = \mathbf { D _ { 2 } } ^ { 2 } } \\ { ( x - x _ { 3 } ) ^ { 2 } + ( y - y _ { 3 } ) ^ { 2 } = \mathbf { D _ { 3 } } ^ { 2 } } \end{array} \right.
$$

TOA 定位算法在网络中实现相对容易，也能达到较高的精度，GPS 定位技术主要就是基于到达时间机理的。但是TOA 算法要求各个监测站之间以及监测站与待定位信号源之间要在时间上严格同步，微小的误差也会使得定位精度大大降低，且因时间同步要求高使TOA定位系统较为复杂。

# 2.3 基于到达时间差(TDOA)定位算法

TDOA定位算法是通过信号源发出的电磁波信号到达不同监测站的时间差即TDOA测量值实现对信号源的定位7。其原理如图4所示，A、B、C三点为监测站，设其坐标分别为A $( x _ { 1 } , 0 )$ ， $\mathbf { B } ( x _ { 1 } , y _ { 1 } )$ ， $\mathbf { C } ( x _ { 2 } , 0 )$ ，T为待定位的信号源，坐标为T $( x , y ) ^ { \cdot }$ ），可以得到下式：

$$
d = { \sqrt { \left( x - x _ { _ { 1 } } \right) ^ { 2 } + y ^ { 2 } } } - { \sqrt { \left( x - x _ { _ { 2 } } \right) ^ { 2 } + y ^ { 2 } } }
$$

其中， $d$ 为监测站A到信号源T的距离与监测站C到发射源T的距离的差值。根据测得的时间差T就可以得到d。再将d代入(3)式，可以得到一个关于 $x .$ 和y的双曲线方程。同理，根据监测站A、B与信号源T的距离

差，可得另外一个关于 $x$ 和y的双曲线方程。多个双曲线方程联立方程组求解，双曲线的交点即为信号源位置。TDOA定位算法的计算复杂度低，定位精度高，同步要求较TOA定位算法低，易于实现。

# 2.4基于信号到达强度(RSSI)定位算法

RSSI定位算法是监测站通过检测来自待定位信号源的接收信号的强度，一般为场强值，再通过选择合适的电波传播损耗模型估算出信号源与监测站间的距离，从而确定信号源的位置8。传播损耗模型选择不当会对RSSI测量值带来很大的误差，户外环境一般选择自由空间传播模型和对数—常态分布模型。自由空间传播模型主要计算视距传播（LOS）条件下的接收信号强度，在该模型中，接收端的接收功率可以表示为：

$$
\operatorname* { P r } ( d ) = { \frac { \operatorname* { P } _ { \mathrm { t } } \mathbf { G } _ { \mathrm { t } } \mathbf { G } _ { \mathrm { r } } { \lambda } ^ { 2 } } { ( 4 \pi ) ^ { 2 } d ^ { 2 } \mathbf { L } } }
$$

其中，P为发射机发射功率， $\mathbf { G } _ { \mathrm { t } }$ 为发射天线增益， $\mathbf { G } _ { \mathrm { r } }$ 为接收天线增益， $\lambda$ 为波长， $d$ 为接收机到信号源的距离，L为系统损耗因子。

对数一常态分布模型中，接收端的接收信号强度为：

$$
\mathbf { P } _ { \mathrm { r } } = \mathbf { P } _ { 0 } - 1 0 n \mathbf { l g } ( \frac { d } { d _ { 0 } } ) + \mathbf { N } _ { 0 }
$$

其中， $\mathbf { P } _ { 0 }$ 为参考场强， $d _ { 0 }$ 为参考距离， $d$ 为信号传播距离， $\mathbf { N } _ { 0 }$ 为服从高斯分布的随机噪声变量， $n$ 为衰减因子。

WiFi、蓝牙定位技术是通过接收信号的强度实现的，室内定位也以RSSI为主。它具有低成本，设备少，距离远，易获取的特点，但是RSSI定位算法对电磁信号传播环境的依赖性很大，如果信号传播过程中存在反射、多径传播、NLOS等问题会对定位结果产生很大的误差。因此，在无障碍物的视距传播环境下，RSSI值更加准确，定位精度越高。为尽量避免测量误差，需考虑各监测站的实际要求和几何分布，选择合适的高处布站，同时参考一些国标。如规划、建设VHF/UHF频段无线电监测站时,须按国际电信联盟〈ITU)规定的监测站周边障碍物的最小保护间距进行建站，对已建设和使用的VHF/UHF频段无线电监测站，为减少周边障碍物对测量结果和测向精度的影响，周边障碍物必须满足规定的限制要求[9]。

# 2.5 差分多普勒(FDOA)定位算法

FDOA定位算法是根据多普勒效应实现定位的。当信号源与监测站之间有相对运动时，接收信号的频率或相位与其静止不动时接收信号的频率或相位不同。多普勒关系式如下：

$$
\Delta f = ( \nu / c ) ( \cos \alpha \cos \theta ) f
$$

其中， $\nu$ 为相对运动速度， $\mathbf { \Psi } _ { c }$ 为电磁波传播速度， $f$ 为信号的频率， $\scriptstyle a$ 为运动方向与信号传播方向的夹角，0为来波倾角。根据几何关系，由（6）式可知频差是一个关于信号源位置、监测站位置和监测站运动状态的函数，通过求解可确定多个包含信号源在内的曲面，多个曲面的交点即为待定位信号源的位置[10]。

FDOA 定位算法具有不模糊、定位精度高等优点，但是当信号的多普勒频率分量与信号源的发射频率相比太小时，多普勒频率分量的变化很难被精确测量，导致测量误差增大。因此，差分多普勒定位算法要求测量精度很高、成本高，在实际应用中仍然有许多问题。

# 3基于数据融合的定位算法

无线电通信技术的飞速发展，无线通信业务及台站类型的不断增加，电磁环境的日益复杂对无线定位技术提出了更高的要求。单一的定位算法较难满足高精度定位的需求，多算法数据融合，高精度、高稳定度成为无线定位技术的发展趋势。数据融合的目的是合并或合成多个数据集，成为一个完整的性能更好的数据集[11]。TDOA 定位算法定位精度较高，定位系统复杂性低、系统简单、易于组网，RSSI算法简单，成本低，易于实现。本文结合TDOA与RSSI定位算法的特点，提出了以RSSI测量值为权值对TDOA 定位结果进行数据融合的定位算法，消除了TDOA定位模糊问题的同时，有效提高了定位精度。

# 3.1 算法的实现

该算法在电磁环境较为良好，信号传播模型较为理想的情况下利用多个监测站联合协同定位，通过对TDOA 定位算法和RSSI定位算法进行数据融合确定信号源位置。首先依次选择两个监测站参与定位，由TDOA定位算法获得多个误差较大的初始位置估计值；其次以参与定位的两个监测站的接收信号强度RSSI值的平均值作为对应初始定位结果的权值，对多个初始位置估计值进行线性加权的数据融合处理，从而获得精度更高的位置估计值。其实现过程如图5所示：

![](images/5edde6040e52bfadfd3c573169ed2c329d3127fdafd5718ce33d5300524b3515.jpg)  
图5.TDOA/RSSI数据融合定位算法示意图Fig 5. Schematic diagram of TDOA/RSSI data fusion positioning algorithm

# 3.2 TDOA定位算法

以五个监测站A、B、C、D、E对待定位信号源T进行TDOA定位为例，各监测站位置坐标分别为A$\scriptstyle \cdot _ { x _ { 1 } = 0 , y _ { 1 } = 0 }$ ）、B $( x _ { 2 , } y _ { 2 } )$ ）、C $( x _ { 3 } , y _ { 3 } ) ^ { . }$ ）、D $( x _ { 4 } , y _ { 4 } )$ ）、E $( x _ { 5 } , y _ { 5 } )$ ，待定位信号源位置坐标为T $( x , y$ ），得到如下所示的到达距离差的方程组：

$$
{ \begin{array} { r } { ( { \sqrt { x ^ { 2 } + y ^ { 2 } } } - { \sqrt { ( x _ { 2 } - x ) ^ { 2 } + { ( y _ { 2 } - y ) } ^ { 2 } } } = d _ { 1 2 }  } \\ {  { \sqrt { x ^ { 2 } + y ^ { 2 } } } - { \sqrt { ( x _ { 3 } - x ) ^ { 2 } + { ( y _ { 3 } - y ) } ^ { 2 } } } = d _ { 1 3 }  } \\ {  { \sqrt { x ^ { 2 } + y ^ { 2 } } } - { \sqrt { ( x _ { 4 } - x ) ^ { 2 } + { ( y _ { 4 } - y ) } ^ { 2 } } } = d _ { 1 4 }  } \\ {  { \sqrt { x ^ { 2 } + y ^ { 2 } } } - { \sqrt { ( x _ { 5 } - x ) ^ { 2 } + { ( y _ { 5 } - y ) } ^ { 2 } } } = d _ { 1 5 } } \end{array} }
$$

其中 $d _ { 1 2 } , d _ { 1 3 } , d _ { 1 4 } , d _ { 1 5 }$ 可由 $\mathbf { t } _ { i }$ 即 TDOA测量值获得。简化以上方程组，待定位信号源坐标T $( x , y )$ ），参与定位监测站的位置坐标为 $\mathbf { B } _ { i } ~ ( \boldsymbol { x } _ { i } , \boldsymbol { y } _ { i } )$ ，则信号源到监测站之间的距离为：

$$
\mathbf { D } _ { i } = \sqrt { ( \mathbf { X } _ { i } - x ) ^ { 2 } + ( \mathbf { Y } _ { i } - y ) ^ { 2 } }
$$

$$
\mathbf { D _ { \lambda } } ^ { 2 } = ( \mathbf { X } _ { i } - x ) ^ { 2 } + ( \mathbf { Y } _ { i } - y ) ^ { 2 } = \mathbf { K } _ { i } - 2 \mathbf { X } _ { i } x - 2 \mathbf { Y } _ { i } y + x ^ { 2 } + y ^ { 2 }
$$

其中， $\mathbf { K } _ { i } { = } \mathbf { X } _ { i } ^ { 2 } { + } Y _ { i } ^ { 2 }$ ，经计算：

$$
\mathbf { D } _ { i , 1 } ^ { \phantom { } 2 } + 2 \mathbf { D } _ { i , 1 } D _ { 1 } = \mathbf { K } _ { i } - 2 \mathbf { X } _ { i , 1 } x - 2 \mathbf { Y } _ { i , 1 } y - K _ { 1 }
$$

式中， $\mathbf { X } _ { i , 1 } { = } \mathbf { X } _ { i } - X _ { 1 }$ ， $\mathbf { Y } _ { i , 1 } { = } \mathbf { Y } _ { i } - Y _ { 1 }$ ，将 $x$ ， $y$ 、 $\mathbf { D } _ { 1 }$ 看作未知数，则(9)式成为线性方程组，可利用Chan算法、Taylor算法、Fang算法等双曲线方程组的求解算法求解该线性方程组的未知数 $\dot { \boldsymbol { x } }$ 、y、 $\mathbf { D } _ { 1 }$ ，就可以得到待定位信号源位置坐标。

# 3.3数据融合算法

(1)测量各参与定位的监测站接收到的来自信号源的接收信号强度 $\mathrm { R S S I _ { i } }$ ，并将当前参与定位的两个监测站接收信号强度的平均值 $\mathrm { \mathbf { R } _ { A V i } }$ 作为当前定位获得的初始位置估计值 $\mathbf { P _ { i } }$ 的权值，并利用（11）式求取所有监测站接收信号强度平均值 $\mathrm { \bf R } _ { \mathrm { A V } }$ 。

$$
\mathbf { R } _ { \mathrm { A V } } = { \frac { \sum \mathbf { R } _ { \mathrm { A V } i } } { i } }
$$

(2）由计算出来的加权值 $\mathrm { \mathbf { R } _ { A V i } }$ 对获得的多个初始位置估计 $\mathbf { P } _ { i }$ 值进行对应线性加权，并利用所有监测站接收信号强度平均值为 $\mathrm { \bf R } _ { \mathrm { A V } }$ 进行归一化，由（12）式获得最终较优的待定位信号源的位置估计值P。

$$
\mathbf { P } { = } \frac { 1 / i \bigl ( \sum \mathbf { R } _ { \mathrm { A V i } } { \times } \mathbf { P } _ { i } \bigr ) } { \mathbf { R } _ { \mathrm { A V } } }
$$

# 3.4仿真结果分析

本文利用 MATLAB仿真工具进行验证。待定位信号源发射正弦信号，电波传播模型为对数—常态分布模型，引入AWGN加性高斯白噪声，仿真过程中引入测量误差与噪声误差，相关参数如表1所示。

# 表1仿真参数

Table 1. Simulation parameters   

<html><body><table><tr><td>Parameters</td><td>Formula & Value</td></tr><tr><td>Signal</td><td>f(t)=4×sin(2π×3x108t)</td></tr><tr><td>Frequency</td><td>300MHz</td></tr><tr><td>Power</td><td>25W, 41.94dBm</td></tr><tr><td>Measurement error</td><td>Uniform Distribution, Mean=0.5</td></tr><tr><td>Noise error</td><td>Gaussian distribution, N(0,1)</td></tr></table></body></html>

以定位结果的均方根误差值RMSE作为衡量定位精度的标准。如下式：

$$
{ \mathrm { R M S E } } = { \sqrt { \left( x - \mathbf { X } \right) ^ { 2 } + \left( y - \mathbf { Y } \right) ^ { 2 } } }
$$

其中 $\mathrm { ~ \bf { P } ( { \boldsymbol { x } } , { \boldsymbol { y } } ) ~ }$ 为仿真定位坐标值， $\mathrm { P _ { r e a l } ( X , Y ) { = } P _ { r e a l } ( 8 . 6 0 0 0 }$ ，6.8000)为真实坐标值。通过多次仿真验证，随机抽取一组定位结果如下表2所示，可以看出，经过数据融合的定位结果更接近于待定位信号源的真实坐标位置。

表2.定位结果对比   
Table 2. Comparison of positioning results   
表3.定位误差均方差对比   
Table 3. Comparison of mean square error of positioning error   

<html><body><table><tr><td>Coordinate</td><td colspan="4">Positioning resultswithout data fusion</td><td></td><td>Positioning results with data fusion</td></tr><tr><td>X</td><td>8.6103</td><td>8.6250</td><td>8.4862</td><td>8.6243</td><td>8.5638</td><td>8.6037</td></tr><tr><td>y</td><td>6.8133</td><td>6.7865</td><td>6.4600</td><td>6.8171</td><td>6.8399</td><td>6.8086</td></tr></table></body></html>

<html><body><table><tr><td>Positioning results without data fusion</td><td>Positioning results with data fusion</td></tr><tr><td>0.3403</td><td>0.0680</td></tr><tr><td>0.1893</td><td>0.0564</td></tr><tr><td>0.1692</td><td>0.0652</td></tr></table></body></html>

![](images/3aff9905b86d822179ad6a0c99790415c3978cd4b49b9f5cac4573900ee20e85.jpg)  
图6.定位结果均方根误差比较 Fig 6. Comparison of root-mean-square error of positioning results

![](images/f68a78de2a5e65ecabd8e2546c236b5147c70d75bd2574c26c800f6b69078fd4.jpg)  
图7.定位结果均方根误差方差比较 Fig 7. Comparison of root mean square error Variance of positioning results

图6仿真结果表明，经过RSSI加权数据融合处理的TDOA算法定位结果的均方根误差小于未经过数据融合处理的TDOA算法定位结果的均方根误差；表3为经过仿真的3组定位误差均方差数据的对比，通过比较，经过数据融合处理的TDOA定位算法的定位误差的均方差明显小于未经数据融合的TDOA算法定位误差的均方差，且数据比较集中，稳定度较高；图7仿真结果表明且经过数据融合后定位结果的误差方差值较未经过数据融合处理的误差方差值明显减小且平缓。且通过多次仿真试验，经过数据融合后的定位误差较未经数据融合单一的TDOA定位误差下降了约 $20 \%$ 。综上，说明该基于TDOA定位算法和RSSI定位算法数据融合的测距无线定位算法定位精度较高，稳定性较好。

# 4结论

本文在分析和研究各测距无线定位算法的基础上，提出了利用多监测站协同、多测距算法融合的无线定位算法，该算法实现了TDOA定位算法与RSSI定位算法的数据融合，有效消除了TDOA定位算法的定位模糊问题，较好地提高了定位精度，且稳定性强，定位性能更加优良。便于快速准确的及时发现射频干扰源的位置和移动规律，并尽可能在技术或管理层面上予以消除。

# 参考文献

[1]李建斌，彭勃，刘东亮．大型射电望远镜电磁环境频谱监测[J]．电波科学学报,2015.04,30(2):378-382.[2] Zhao Junhui, Wang Dongming. Wireless location technologyand its application[J].Engineering Sciences，中国工程科学(英文版),2011,9(4):32-37.  
[3]孙顺远．无线传感器网络定位算法及应用研究[D].江南大学,2014.6.  
[4] 于天意．复杂环境下的无线定位技术研究[D]．北京交通大学,2019.6.  
[5] 常娥，冷卫杰．工业互联网无线室内定位技术概述[J]．物联网学报,2020.3,4(1):1-7.  
[6]夏禹，张效艇，王嵘．TOA定位算法的坐标解析优化方法综述[J].单片机与嵌入式系统应用,2019(12):15-22.  
[7] 刘磊，姚剑，谢学锋，景超．TDOA无源定位系统的原理与影响因素分析[J].无线通信技术,2017(4):42-46.  
[8] 张珮琪．基于RSSI的室内无线定位与跟踪技术研究[D]．西安电子科技大学,2016.2.  
[9]中华人民共和国国家质量监督检验检疫总局，中国国家标准化管理委员会．VHF/UHF频段无线电监测站电磁环境保护要求和测试方法:GB/T25003-2010[S].2010.12.  
[10] 季海福,马利华,艾国祥,王萌.GNSS中结合多普勒频移的DS-R定位新方法[J]．天文研究与技术,2014.1, 11(1):13-18.  
[11] 魏彦飞，耿建平，施浒立，李景景，李 林，徐希坤．一种新的数据融合方法—广义融合法[J].天文研究与技术,2016.7,13(3):318-325.