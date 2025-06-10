# 利用半导体二极管伏安特性进行朗缪尔探针性能测试研究

刘超 关燚炳 张爱兵 孙越强 梁金宝郑香脂 丁建京 孔令高 田峥 王文静

(中国科学院国家空间科学中心北京100190)

摘要研究讨论了一种利用半导体二极管伏安特性进行朗缪尔探针性能测试的方法.设计的朗缪尔探针性能测试方法对外界因素要求较低，在常温常压的通常实验室环境下即可进行，其测试结果可作为利用地面等离子体环境进行定标测试前的初步性能验证.通过实验室环境下的测试试验，验证了该方法的有效性和可行性，

关键词朗缪尔探针，性能测试,伏安特性,半导体二极管 中图分类号P354

# Study on Technology of Using Semiconductor Diode Volt-Ampere Characteristic to Test Langmuir Probe Performance

LIU Chao GUAN Yibin ZHANG Aibing SUN Yueqiang

LIANG Jinbao ZHENG Xiangzhi DING Jianjing

KONG Linggao TIAN Zheng WANG Wenjing

National Space Science Center,Chinese Academy of Sciences,Beijing 100190

Abstract A technique of using a semiconductor diode volt-ampere characteristic to test Langmuir probe performance is presented. The Langmuir probe is an important technique for in-suit detecting the space plasma,and its performance test is the key to ensure that its technical indicators can meet the mission requirements.The technique of using a semiconductor diode volt-ampere characteristic demands less of external factors,so it can be carried out in a laboratory environment. The test results can be used as preliminary performance verification before calibration test of ground plasma environment,and it is proved that the method is effective and feasible in a lab environment test.

Key words Langmuir probe, performance test,V-I characteristic, Semiconductor diode

# 0 引言

中国在“十二五”期间开展了电磁监测试验卫星的研究[1],用于获取全球电磁场、等离子体和高能粒子的观测数据，识别大地震发生前后相关的电磁、电离层和高能粒子异常，探索大地震短临预测与预警新方法[2]．朗缪尔探针作为科学载荷之一，可应用于空间等离子体的探测，就位测量空间等离子体的电子密度和温度等特性参数，提供大震短临期间电离层等离子体电子异常信息

在朗缪尔探针的设计研制过程中，仪器标定是确保其性能指标满足任务需求的关键．朗缪尔探针的标定试验通常利用地面等离子体设备产生等离子体近似模拟卫星轨道高度的空间等离子体环境[3]．将朗缪尔探针传感器浸入该等离子体环境中，通过测试获得等离子环境参数并与设定的等离子体环境参数进行比对，标定其性能指标

由于利用等离子体环境定标的周期、复杂度和成本均较大，通常是在仪器完成研制后开展此项定标工作的．因此难以对研制过程中的性能状态进行控制，存在最终定标试验结果不能达到任务要求的风险.为实现在研制过程中能够对朗缪尔探针进行初步的测试以验证其技术性能，本文设计了一种利用半导体二极管伏安特性进行朗缪尔探针性能测试的方法该测试方法可在实验室环境下进行，测试结果可为后续研制和等离子体环境标定起到重要的辅助作用，

# 1朗缪尔探针基本原理

朗缪尔探针的工作原理是将传感器浸入等离子体中，传感器会收集等离子体中的电子和离子，形成电流.当给传感器外加一个扫描电压 $V _ { \mathrm { s } }$ ，传感器收集的等离子体电流 $I$ 会随着外加扫描电压的变化而变化，从而得到传感器与等离子体相互作用的伏安特性曲线.通过分析该伏安特性曲线，可以得到等离子体密度、温度和电位等参数 $[ 4 \AA - 5 ]$ ·

# 1.1 朗缪尔探针的伏安特性

朗缪尔探针伏安特性曲线如图1所示，其可分为离子饱和区、阻滞区和电子饱和区三个区域[].

当外加扫描电压电位低于等离子体电位，相对其为负电位，因而传感器排斥电子，吸收离子，随着外加电压的进一步降低，离子电流 $I _ { \mathrm { i } }$ 逐渐增大，电子电流 $\boldsymbol { I _ { \mathrm { e } } }$ 指数减小，其对传感器收集电流的贡献趋于零，探针收集的电流可认为全部为离子电流，这一区域称为离子饱和区.

![](images/31ae206df0a9a3a209e86d9c9a5163170966ca334b35238a41ed5bd012d15057.jpg)  
图1朗缪尔探针理想 $V { - } I$ 曲线  
Fig.1 Typical Langmuir probe V-I characteristic curve

当外加扫描电压电位相对于等离子体电位逐渐增加,即相对值向正电位变化时，电子排斥场减小，离子的吸引力增强，此时探针传感器收集的电子电流增加，而离子电流减小，并且电子电流逐渐趋于主导作用,这一区域称为电子阻滞区．在电子阻滞区内，传感器收集的电子电流随扫描电压呈指数变化.

当外加扫描电压电位高于等离子体电位时，传感器吸引电子而排斥离子，在传感器周围开始形成电子鞘.电子电流本身比离子电流高一个量级以上，随着外加电压值越来越大，传感器吸收越来越多的电子，而收集的离子已微不足道，几乎只有电子，因而此时的收集电流就是电子饱和电流，这一区域称为电子饱和区.

# 1.2 电子阻滞区的伏安特性

设定空间等离子体的粒子分布服从麦克斯韦分布，且粒子间无相互作用、无强磁场干扰等条件，可以得到朗缪尔探针收集电流 $I$ 、外加扫描电压 $V _ { \mathrm { s } }$ 与等离子体参数（电子温度 $\varUpsilon _ { \mathrm { e } }$ 、电子密度 $n _ { \mathrm { e } }$ 、离子温度 $T _ { \mathrm { i } }$ 、离子密度 $n _ { \mathrm { i } }$ 等)之间的关系[7]为

$$
\begin{array} { r } { I = f ( V _ { \mathrm { s } } , T _ { \mathrm { i } } , T _ { \mathrm { e } } , n _ { \mathrm { i } } , n _ { \mathrm { e } } , \cdot \cdot \cdot ) . } \end{array}
$$

在电子阻滞区，传感器收集的电子电流随扫描电压呈指数变化．由于此时 $I _ { \mathrm { e } } \gg I _ { \mathrm { i } }$ ，可以忽略离子电流 $I _ { \mathrm { i } }$ ，传感器收集电流可表示为

$$
\begin{array} { r } { I \approx I _ { \mathrm { e } } = I _ { \mathrm { e 0 } } \exp ^ { \frac { \mathrm { e } V _ { \mathrm { S } } } { k T _ { \mathrm { e } } } } . } \end{array}
$$

式中， $I$ 为探针传感器收集电流， $V _ { \mathrm { s } }$ 为传感器的外加扫描电压， $k$ 为玻耳兹曼常数 $( 1 . 3 8 \times 1 0 ^ { - 2 3 } \mathrm { J } . \mathrm { K } ^ { - 1 } )$ ： $T _ { \mathrm { e } }$ 为等离子体电子温度， $e$ 为电子电荷 $( 1 . 6 \times 1 0 ^ { - 1 9 } \mathrm { C } )$ $I _ { \mathrm { e 0 } }$ 为电子热随机电流， $I _ { \mathrm { e 0 } } = { \frac { 1 } { 4 } } { \bar { V } } _ { \mathrm { e } } e n _ { \mathrm { e } } S _ { \mathrm { e } } .$ 其中 $\bar { v } _ { \mathrm { e } }$ 为电子的平均热速度， $n _ { \mathrm { e } }$ 为等离子体的电子密度， $S _ { \mathrm { e } }$ 为传感器接收电子面积，可近似用传感器的几何面积（有效浸入等离子体中的部分）替代

对式（2）两边求对数可得

$$
\ln { I } = \ln { I _ { \mathrm { e 0 } } } + { \frac { e V _ { \mathrm { s } } } { k T } } = C + { \frac { e V _ { \mathrm { s } } } { k T _ { \mathrm { e } } } } .
$$

式中， $\boldsymbol { C } , \boldsymbol { e } , \boldsymbol { k }$ 均为常数.因此，在获得扫描电压 $V _ { \mathrm { s } }$ 和传感器收集电流后，通过计算可以得到等离子体电子温度 $T _ { \mathrm { e } }$ 元

# 2半导体二极管特性

半导体二极管是由PN结的P区和N区分别引出两根电极引线，并加上管壳封装而成.半导体二极管的外形、结构分别如图2和图3所示[8].

# 2.1 PN结的伏安特性

在一块半导体晶体上，采用一定掺杂工艺，使得一边形成P型区，另一边形成N型区，则在P区与N区的交界面两侧即形成一层很薄的正负离子层，称为空间电荷区，也称为耗尽区或阻挡层，从而形成PN结，如图4所示.

PN结的伏安特性曲线如图5所示，可分为正向特性、反向特性和反向击穿特性三种不同情况

当PN结外加正向电压时，PN结处于导通状态呈现的电阻为正向电阻，其阻值很小.外加正向电压愈大，流过的正向电流愈大，两者呈指数关系.

当PN结外加反向电压时，PN结处于截止状态，呈现的电阻为反向电阻，其阻值很大.流过的反向电流主要是由少子的漂移运动形成的，不随外加反向电压的增加而变化，故称之为反向饱和电流 $I _ { \mathrm { s } }$ 业

当PN结外加反向电压增大到一定数值时，反向电流会突然增加，此时PN结发生了反向击穿.引起击穿所需的反向电压 $V _ { \mathrm { B R } }$ 称为反向击穿电压

综上所述，PN结具有单向导电特性，其伏安特性可表示为

$$
\begin{array} { r } { \dot { i } _ { \mathrm { D } } = { i } _ { \mathrm { s } } \big ( \exp ^ { \frac { V _ { \mathrm { D } } } { V _ { \mathrm { T } } } } - 1 \big ) . } \end{array}
$$

![](images/515f164bc81897d87c59ed03d07c7fa4cb07951c36e110203d671c4be8591608.jpg)  
图2二极管物理结构

![](images/dabccc058898fdfbe89f249099fa4965ffb0d97346445e869ed6716c310d5c73.jpg)  
图4PNjunctionformationFig.4PN结的形成

+ 十

![](images/e8c615b30d0c3745d429a58f7dedcf98de81cd80d3cd516262a9e7148c54cc1b.jpg)  
Fig.2 Diode physical structure   
图3二极管电气符号 Fig.3 Diode electronic symbols   
图5PN结伏安特性曲线  
Fig.5 PNjunctionV-Icharacteristic curve

式中， $i _ { \mathrm { D } }$ 为通过PN结的电流； $V _ { \mathrm { D } }$ 为PN结两端的外加电压； $V _ { \mathrm { T } }$ 为温度的电压当量，有 $V _ { \mathrm { T } } = k T / q$ 这里 $T$ 为热力学温度即绝对温度， $q$ 为电子电荷 $( 1 . 6 \times$ $1 0 ^ { - 1 9 } \mathrm { C } )$ $I _ { \mathrm { s } }$ 为反向饱和电流，对于分立器件，其典型值在 $1 0 ^ { - 8 } \sim 1 0 ^ { - 1 4 }$ A范围内.

# 2.2 二极管的伏安特性

实际的二极管伏安特性如图6所示，可以看出二极管伏安特性与PN结伏安特性基本是相同的

通常直接使用PN结伏安特性方程描述二极管伏安特性.但由于半导体二极管的尺寸、材料以及通过二极管的电流值等影响因素，二极管伏安特性方程与PN结伏安特性方程略有不同[9，即在二极管伏安特性方程的指数项中会存在一个发射系数 $n$ 表示实际的伏安特性，其表达式为

$$
i = I _ { \mathrm { s } } \big ( \exp ^ { \frac { V } { n V _ { \mathrm { T } } } } - 1 \big ) .
$$

式中 $i$ 为通过二极管的电流， $V$ 为二极管两端的外加电压， $V _ { \mathrm { T } }$ 为温度的电压当量， $I _ { \mathrm { s } }$ 为反向饱和电流$n$ 为经验常数，数值在 $1 { \sim } 2$ 之间，其取值主要由二极管的材料和物理结构决定，对于集成电路二极管，$n = 1$ ；而对分立二极管， $n = 2$ 元

当 $V > 0$ ，且 $V \gg V _ { \mathrm { T } }$ 时， $\exp ^ { \frac { V } { n V _ { \mathrm { T } } } } \gg 1$ ，式（5）中的1可以忽略.这样流过二极管的电流 $i$ 与外加电压 $V$ 呈指数关系，式（5）可表示为

$$
\begin{array} { r } { i \approx I _ { \mathrm { s } } \exp ^ { \frac { V } { n V _ { \mathrm { T } } } } = I _ { \mathrm { s } } \exp ^ { \frac { q V } { n k T } } . } \end{array}
$$

两边求对数可得

$$
\ln i = \ln I _ { \mathrm { s } } + { \frac { q V } { n k T } } = C + { \frac { q V } { n k T } } .
$$

式中， $C , q , k , n$ 均为常数.因此，在已知二极管两端

![](images/71fc6c8ea744e10a75a71968b9125b93b0384c158981bfc5c6e83f3b1531f0b4.jpg)  
图6二极管伏安特性曲线

外加电压 $V$ 和流过二极管的电流 $i$ 的情况下，通过计算可以获得当前环境的热力学温度 $T$

# 3半导体二极管特性在朗缪尔探针测试中的应用分析

朗缪尔探针测量空间等离子体参数的原理是测量扫描电压和相应收集电流，从而得到传感器和等离子体相互作用的伏安特性曲线．通过分析该伏安特性曲线，得到等离子体密度、温度和电位等参数．因此，决定朗缪尔探针测量性能的关键指标是其对扫描电压和收集电流的测量精度

利用二极管特性推导环境温度的原理是测量二极管两端外加电压和流过二极管的电流，从而得到二极管伏安特性曲线.通过分析该伏安特性曲线，得到当前环境的热力学温度.因此，其测量结果正确性的主要指标也是其对外加扫描电压以及流过电流的测量精度.

从式（3）和式（7）分析可知，朗缪尔探针伏安特性推导等离子体电子温度的原理公式与二极管伏安特性推导环境温度的原理公式基本相同[10]．因此，朗缪尔探针可以通过对二极管伏安特性曲线的测试得到当前环境的热力学温度.从而可以得到朗缪尔探针对二极管两端外加电压和流过二极管电流的测量精度，模拟朗缪尔探针对其扫描电压和收集电流的测量精度，验证朗缪尔探针的初步性能

# 4测试试验

# 4.1 试验情况

通过上述分析，利用二极管伏安特性可进行朗缪尔探针的性能测试.图7为朗缪尔探针测量电路，将图中传感器更换为二极管和电阻网络，即组成了相应的测试电路[11],如图8所示

![](images/98332059cf041f3bac740a60f1571c78fff09f829b8b55bbbd8a25a2a7c2c6fa.jpg)  
Fig.6DiodeV-Icharacteristic curve   
图7朗缪尔探针测量电路  
Fig.7Langmuirprobemeasurement circuit

试验电路中，选择分立二极管2CK75D作为试验器件，电阻 $R _ { 1 }$ ， $R _ { 2 }$ 为限流保护电阻.通过扫描电压加载单元外加 $- 2 \sim + 4 \ : \mathrm { V }$ 的扫描电压 $V _ { \mathbf { s } }$ ，由运算放大器组成的测量电路将流过二极管的电流 $I$ 转换为电压 $V _ { \mathrm { o u t } }$ 输出．电压 $V _ { \mathrm { o u t } }$ 与电流 $\boldsymbol { \mathit { I } }$ 的关系为

$$
V _ { \mathrm { o u t } } = I R _ { \mathrm { f } } .
$$

当扫描电压为负值时，二极管处于反向截止状态，电流流过电阻 $R _ { 1 } , R _ { 2 }$ ．当扫描电压为正值时，二极管处于正向导通状态，电流流过二极管.记录每个扫描电压 $V _ { \mathbf { s } }$ 及其对应的测量输出电压 $V _ { \mathrm { o u t } }$ ，即可得到二极管的伏安特性曲线.

# 4.2 试验结果

在常温常压的实验室条件下开展了试验，获得的二极管伏安特性曲线(半对数坐标)如图9所示

通过对该伏安特性曲线进行计算，得到测试时大气环境的热力学温度为298.4K，即摄氏温度$2 5 . 2 5 ^ { \circ } \mathrm { C }$ ．在试验过程中实际记录的大气环境温度为 $2 5 . 5 ^ { \circ } \mathrm { C }$ (温度计测量值)．考虑测量误差及测试过程中的环境温度波动，可见利用二极管测试获得了精确的大气环境温度.

![](images/ace0c4affdf91c2ae1837751bfa406fb5b4664a21ea154bd1d18a1c471caba3a.jpg)  
图8测试试验电路 Fig.8 Test circuit

![](images/66000c985f8a7ccacba5fad6660a39ddf5c173436f087bea937722193bc0d0c7.jpg)  
图9测试结果Fig.9 Test result

该测试结果表明朗缪尔探针对二极管两端外加电压和流过二极管电流的测量精度满足测试要求，验证了朗缪尔探针对其扫描电压和收集电流测量精度的性能.

# 5结论

通过对朗缪尔探针和二极管的伏安特性分析可知，二者均具有随施加电压指数变化的特性，因此可以利用对二极管伏安特性的测试获得大气环境温度，以模拟朗缪尔探针测量等离子体电子温度的性能

本文设计的方法在常温常压的通常实验室环境下即可进行，并在测试试验中获得了精确的大气环境温度，可应用在研制过程中对朗缪尔探针进行初步性能验证,从而进一步实现朗缪尔探针在研制过程中的技术改进和性能完善，

# 参考文献

[1] Shen Xuhui,Wu Yun, Shan Xinjian.Remote sensing application in earthquake science and general proposal for earthquake satellite project in China [J].Recent Develop. World Seismol.,2007(8):38-45.In Chinese(申旭辉,吴云, 单新建．地震遥感应用趋势与中国地震卫星发展框架[J].国际 地震动态，2007(8):38-45)   
[2] Yang Fang,Shen Xuhui,Wu Yun,et al. Electromagnetic satellite and its application in the field of seismo-precursor detection[J].Spacecr.Eng.,2008,17(1):68-73．In Chinese(杨芳，申旭辉,吴云，等.电磁环境卫星系统及在地震短临 预测中的应用[J].航天器工程,2008,17(1):68-73)   
[3]Pang Yongjiang,Xu Yuemin.The measurement ofa simulated outer space plasma environment in ground lab[J]. Chin.J. Space Sci.,2001,21(3):259-265.In Chinese (庞永 江,徐跃民．地面实验室模拟空间等离子体环境的初步测试[J]. 空间科学学报，2001,21(3):259-265)   
[4] Liu Chao,Wang Shijin，Guan Yibing，et al.Rocketborne Langmuir probe in-situ measurement technology of the ionosphere[J]. Chin. J. Radio Sci.,2012,27(6):1081- 1086．In Chinese（刘超，王世金，关燚炳，等.箭载朗缪尔探 针电离层就位探测技术研究[J]．电波科学学报，2012，27(6): 1081-1086)   
[5] Guan Yibing,Wang Shijin,Liang Jinbao,et al.The design of Langmuir probe onboard sounding rocket [J].Chin. J.Geophys.,2012,55(6):1795-1803.In Chinese (关燚炳, 王世金，梁金宝，等.基于探空火箭的朗缪尔探针方案设计[J]. 地球物理学报,2012,55(6):1795-1803)   
[6] Jiao Weixin. Space Exploration [M].Beijing:Peking University Press,2002:226-232(焦维新.空间探测[M].北京：北 京大学出版社，2002:226-232)   
[7] GuanYibing，Wang Shijin,Liu Chao. The design and simulation for the sensor of the space based Langmuir probe[J].Chin.J.Space Sci.,2012，32(5):750-756．In Chinese (关燚炳，王世金，刘超．天基朗缪尔探针传感器设计 与仿真[J].空间科学学报，2012,32(5):750-756)   
[8] Tong Shibai.Simulation Electronic Technology Foundation [M].Beijing:Higher Education Press,1998:7-9．In Chinese (童诗白.模拟电子技术基础[M].北京：高等教育出版 社，1998:7-9)   
[9] Milman J.Microelectronics Digital and Analog Circuitsand Systems [M].Beijing:People's Education Press, 1980:52-53.In Chinese(MilmanJ.微电子学:数字和模拟电 路及系统(上册)[M].北京：人民教育出版社，1980:52-53)   
[10] Brussaard G J H,Steen Van Der M,Carrere M,et al. Langmuir probe measurements in expanding magnetized argon，nitrogen and hydrogen plasmas [J].Surf. Coat. Tech.,1998,98:1416-1419   
[11]Durkin C,Smith LG.A rocket-borne Langmuir Probe for HighResolution Measurement of the Ionospheric Electron Temperature Profile [Rl.Aeronomy Report,No.95,1981

# 2016年国际地球科学与遥感大会（IGARSS2016）征文通知

由美国电子与电气工程师协会(IEEE）地球科学与遥感分会（Geoscience and Remote Sensing Society，GRSS）主办，中国科学院国家空间科学中心承办的 2016 年国际地球科学与遥感大会 (International Geoscience And Remote SensingSymposium 2016,IGARSS 2016)将于2016年7月10 日至15 日在北京召开。地球科学与遥感大会(IGARSS)每年召开一次，是全球该领域最具影响力的学术会议。会议组委会诚挚邀请您踊跃投稿，积极参会。

会议时间2016年7月10－15日 会议地点国家会议中心 (北京)

会议主题 Advancing the Understanding of Our Living Planet

# 会议议题

Standard Topics: Atmosphere,Biosphere,Cryosphere,Data Fusion and Management,Electromagnetic Scattering and Radiative Transfer,Hydrology,Land,Ocean,Planetary Exploration,Sensors and Systems.

Special Topics: New Satelite Missions,Global Change Study,Data Assimilation and Fusion,Hyperspectral Image Processing, Natural Hazards and Environmental Polution, Microwave Remote Sensing - Active,Microwave Remote Sensing- Passive,Modeling,Simulation and Validation,Inversion & Information Retrieval,Big Data in Geoscience, Interdisciplinary Topics, Student Paper Competition.

# 重要日期

Abstract Submission System Available:November 20,2015   
Abstract Deadline:January 8,2016   
Travel Support Application Deadline: January 8,2016   
Student Paper Competition Deadline: January 8,2016   
Abstract Status Available On-line:April 8,2016   
Registration Opens:April 11,2016   
Early Registration Deadline:May 20,2016   
On-line Registration Deadline:July 1,2016   
Full Paper Submission Deadline:May 20,2016

承办单位中国科学院国家空间科学中心，复旦大学，中国科学院遥感与数字地球研究所  
联系方式 E-mail:info.igarss2016@nssc.ac.cn  
具体情况请见会议网址 http://www.igarss2016.org