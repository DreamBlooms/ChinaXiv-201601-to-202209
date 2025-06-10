# 基于数值历表的月球物理天平动研究

黄1，孙尚彪，杨永章¹，李祝莲，李语强(中国科学院云南天文台，云南 昆明 650216)(中国科学院大学，北京 100049)(吉林大学地球探测科学与技术学院，吉林 长春 130026)

摘 要：月球物理天平动是对月球运动在空间摆动的描述。确定月球物理天平动,可以推测物理天平动的激发与耗散机制，比如陨击、月震和核幔粘滞摩擦等,故测定月球物理天平动对认识太阳系中天体的起源、演化及结构等，都具有十分重要的意义。本文利用最新的INPOP19a历表的数据，完成了对历表提取的欧拉角到月球物理天平动的转换，得到的物理天平动数值分别与该系列历表INPOP17a以及被厂泛使用的DE430对比，发现不同历表的物理天平动之差存在着稳定周期。对比历表欧拉角的差别，计算出地心到月面反射器A15 的距离最大有30厘米的差别，此结果对月球激光测距的预报精度有较大的影响，为后续的高精度测月研究打下基础。研究结果表明，INPOP19a最为稳定，故在月球物理天平动研究中推荐使用 INPOP19a。

关键词：月球历表，欧拉角，月球天平动，傅里叶变换

# 0.引言：

月球天平动是对月球运动在空间摆动的描述，它是月球自转，公转轨道以及周围天体对月球的力的作用的综合表现。基于激光测月数据制作的月球历表是进行月球物理天平动研究的数据基础[1]。

根据卡西尼定则，月球的公转周期与自转周期一致，但由于月球质量的非球面分布，月球的自转并不是均匀的。这种与均匀旋转的偏离被称为物理天平动。物理天平动有两种类型，受迫天平动与自由天平动。受迫天平动是由于地球、太阳和行星的引力引起的月球形状上的时变力矩；自由天平动主要是地质活动引起的，如冲击，核-幔相互作用，或是与受迫天平动的共振[2]。在理论上，受迫天平动的振幅、相位和周期可以根据月球形状特征、弹性形变和旋转耗散的知识来计算。对于自由天平动，只能计算出周期，必须通过测量获得振幅和相位[3]。

自由天平动有三种模式，一种在经度，两种在极位。经度模式是围绕月球极轴的周期为2.9年的摆状振荡[3]。剩下的两种模式描述了月球极位与周期为18.6年的受迫进动和周期的

受迫天平动所决定的位置之间的变化。第一个极位模式被称为摆动模式，类似  
于地球的钱德勒摆动。另外一个极位模式是自由进动模式，并对应于空间中极  
轴周期为81年的运动。随着时间的推移，物理天平动会由于能量耗散而减弱  
[4]。

月球天平动可以使用解析法和数值法两种计算方式，在早期，受限于观测数据的缺乏以及数值算法的计算量太大，数值法相对于解析法并没有太大的优势，在工程上对精度的要求解析法的摄动理论完全可以达到[5]。但是随着深空探测的的不断发展，对精度的要求逐渐增高，解析法由于计算公式太过复杂，开始显示出其应用的劣势[6]。与此同时，在更多的观测数据和计算机技术的发展的支持下，数值法能达到更高的精度，随着地月数值历表的建立，使得数值法逐渐成为月球天平动研究的主要方法。月球历表中包含着月球在国际天球坐标系中的位置与速度状态信息[7][8]。本文对月球轨道及物理天平动的研究所使用的数据均来自地月历表。

目前，我国月球探测已经进入了月面着陆的快速发展期，特别是云南天文台和中山大学相继成功开展了月球激光测距试验，这为我们加入国际月球激光测距分析社区提供了技术基础[8][9]。随着地面测月站数量的不断增加，国内的激光测月往高精度的发展，未来会积累大量的高精度数据，这些数据为历表的研制和物理天平动的研究提供支撑。进入新世纪后，我国提出了月球探测和深空探测计划，并成功实施了月球探测项目。杨永章等在基于FFT分析的基础上，发展了一种频率提取和拟合的数值方法，从DE430历表数据中提取了月球自由天平动周期频率，与国际同行结果一致；在动力学模型方面，建立了基于国际上最新动力学模型的月球自转双层/单层模型及数值算法，结果精度与主流历表相当[9]。本研究将实现使用最新的INPOP19a历表实现对月球物理天平动的提取。计算新一代月球历表在物理天平动数值模型精度上的提高，为进一步高精度月球激光测距的研究打下基础。

# 1．月球转动欧拉角

月球历表中包含着各个天体在国际天球坐标系中的位置与速度状态信息，还包含了月球的转动欧拉角。利用INPOP19a,INPOP17a,DE430三个历表中跨度为600年的数据提取得到的欧拉角作差比较如图：

![](images/6a19dc426cc47ae40631ce0a12ef01a2923801156f6b019fbb28be21419d6095.jpg)  
Fig.1 The difference of Euler angle between INPOP19a and INPOP17a

(se)Φ 0.05 1t1<j<1<1/y -0.05   
(se) 0.02 WAwmww -0.02 -5.28768e8 0.50   
(se) 0.25 0.00 0 100 200 300 400 500 600 year

![](images/b349378ba20cbf6f9b574a8c8170eb38f4f17c70a3f2e2bc99cdcdb450b73557.jpg)  
图一INPOP19a与INPOP17a 欧拉角的差别  
图二INPOP17a与DE430欧拉角的差别

结果如图所示，INPOP17与DE430欧拉角差别较大，INPOP19则更为稳定。其中对于不同历表之间的差别稳定在0.05角秒来回震荡。但是的差别随着时间逐渐增大，说明历表中对于的拟合模型并不稳定。对比历表欧拉角的差别，计算出地心到月面反射器A15的距离最大有30厘米的差别，对月球激光测距的预报精度有较大的影响。对结果进行频谱分析：

# 表1对欧拉角进行频谱分析得到的周期 (单位：天)

Tab.1 The period obtained by performing spectrum analysis on Euler angles (unit: day)   

<html><body><table><tr><td>INP0P19a-DE430</td><td>INPOP19a-INPOP17a</td><td>INP0P17a-DE430</td></tr><tr><td>27.3</td><td>27.32</td><td>27.3</td></tr><tr><td>27.3</td><td>27.32</td><td>27.3</td></tr><tr><td>27.3</td><td>27.32</td><td>27.3</td></tr></table></body></html>

Fig.3 The difference of Euler angle between INPOP19a and DE430

以上过程完成了对天平动欧拉角的提取，并利用FFT算法对历表中提取出的欧拉角之差进行了频谱分析，获得的结果如表1所示。27.3天的差异是极位置在惯性坐标系下自由天平动的周期。

# 2．月球天平动与月球转动的力学模型

月球天平动是对月球运动在空间摆动的描述，它是月球自转，公转轨道以及周围天体对月球的力的作用的综合表现[10]。月球天平动指的是地面观测者所观测到的月球可见面上下左右小幅度的摆动，由于天平动效应，使观测者能看到 $6 9 \%$ 的月面，其中 $1 9 \%$ 时多时少。

因月球相对于地心的月面的经度天平动和纬度天平动又称光学天平动或几何天平动。几何天平动中的经度项纬度项除了与月球本身的物理天平动有关系外，还主要与月球的公转轨道有密切的关系。因月球实际摆动形成的天平动则称物理天平动，物理天平动是月球自身相对于空间坐标的转动欧拉角，与月球自身的内部结构，自转动量，转动惯量有关。本项研究具体实现从历表中所获得的欧拉角到月球物理天平动的转换过程。

月固坐标系分为月球主轴坐标系（PrincipalAxisFrame,PA）与平均地球指向坐标系（Mean Earth,ME)。在描述月球的转动时，我们以月球质心为原点，月球三个惯量主轴为三个坐标轴，建立随月球一起转动的月球主轴参考系

（PA）。同时，我们可以得到坐标指向与ICRS一致的月心天球参考系。两个坐标系通过三个欧拉角进行转换。

这三个欧拉角及其变化率即为月球天平动的数值表达，反应月球自转的状态。依据卡西尼定则：月球自转周期等于其公转周期；月球赤道与黄道的夹角成；月球自转轴，月球轨道平面的法线以及黄道面的法线三者共面，且第三者处于前两者之间。月球的物理天平动的理论基础，主要是刚体转动微分方程，此处方程由卡西尼第一定律简化得到，对于刚体月球转动微分方程为经典的欧拉-刘维尔方程：

在DE历表中我们可直接读取出月心天球参考系到月球主轴坐标系的转换矩阵，利用旋转矩阵到欧拉角的转换可采用以下方法：

此转换过程中的旋转分别为

此时有：

此公式即为月心天球坐标系到月球主轴坐标系的转换理论基础。将这一向量转换到瞬时黄道坐标系中：

其中，B,N,P分别代表坐标偏差，岁差和章动矩阵。代表瞬时真黄道坐标系的旋转。

将PA坐标系中的单位向量和通过上述坐标转换过程至瞬时黄道坐标系中得到和。分别代表在黄道坐标系下沿着，和的单位向量。代表坐标原点指向月球赤道与黄道的升交点的单位向量。此时有：

![](images/420c6537ef1b56956bdae32b3e97134eec92826a7666c75b6cc4bd58102d9ba8.jpg)

![](images/fe1e993a5a20570ddb7c1beffced3300f650a6c6f6e7cdbacd1e83a334331548.jpg)  
图四：PA坐标系到ICRS中的旋转欧拉角 Fig.4Rotated Euler angle from PA coordinate system to ICRS   
图五：PA坐标系到黄道坐标系的欧拉角  
Fig.5Euler angle fromPAcoordinate system to ecliptic coordinate system

利用图五中的关系式，可以得到：

根据Newhal1[10]:

在上述过程中，我们把图五中赤道坐标系下的欧拉角转换为图六黄道坐标系中的。Eckhardt分别使用来表示天平动中解得周期项。其中是由分离出来，被定义为解的周期部分，由公式（19）定义，是一个线性多项式。根据公式（18）是轨道节点的经度，是两个节点之间的瞬时差，将公式（18）变为，将定义为以由一个常数和解的周期部分组成。同时（20）式可变化为，定义由一个常数和结果的周期部分组成。至此，分别使用来表示月球的物理天平动，根据上述过程计算得到结果最终如图所示：

图六利用inpop19a历表实现对月球物理天平动的提取  
![](images/5b46d6f90f60fd3cb37b9ba09a2b941661be3c9210c70502b2842a304f8564b5.jpg)  
Fig.6 Using inpop19a Ephemeris to Extract the Lunar Physical librations

至此完成了利用数值历表中欧拉角对物理天平动的转换。

利用上述的方法，从INPOP17a与DE430中分别提取出物理天平动与INPOP19a作差比较结果如图所示。

![](images/c1eb0a38269d4cc82937c79d7340979157e1604f94d5e720e606f9efd8c0dc07.jpg)  
图七INPOP19a与INPOP17a物理天平动差别

![](images/9f7371872f8faf4c0fb1dfbbf42f36289564bd80b9f18e851d09a23b312580de.jpg)  
图八INPOP19a与DE430物理天平动差别 Fig.8 the difference between INPOP19a and de430

结果显示INPOP19a与INPOP17a物理天平动差别更为稳定。

# 3．物理天平动的频谱分析

由图六物理量绘制的图与图八中INPOP19a与INPOP17a之差对比发现存在一个稳定频率的周期，且此频率与本身的固有频率不同。故在研究过程中重点对此频率进行分析。

首先，根据上述过程，利用INPOP19a,INPOP17a,DE430三个历表中跨度为600年的数据提取得到的物理天平动作差比较如图：

![](images/fc7adf785c4e3c4dac3d168826eddd5895525c3398dcb8360dfaac5145ff6be3.jpg)  
图九INPOP17a与DE430物理天平动的差别

![](images/3bc76a6b7b5e4d6bd7efbe632faf13b676c85c1b2ac9a22b016c99cc0b2cc9fc.jpg)  
Fig.9 The difference of physical librations between DE43O and INPOP17a   
图十INPOP19a与DE430物理天平动的差别

![](images/31d9f35c6e3a1420ae4bf35fb5c2fbc3280b46fc8c699be53e5f47d180421730.jpg)  
Fig.10 The difference of physical librations between INPOP19a and DE430   
图十一INPOP19a与INPOP17a物理天平动的差别  
Fig.11 The difference of physical librations between INPOP17a and INPOP19a

利用FFT算法对上面的图像进行频谱分析得到如表2的结果：

# 表2对物理天平动进行频谱分析得到的周期 (单位：天)

Tab.2 The period obtained by performing spectrum analysis on physical librations

(unit: day)   

<html><body><table><tr><td>INPOP19a-INP0P17a</td><td>INPOP19a-DE430</td><td>INPOP17a-DE430</td></tr><tr><td>27.21</td><td>27.18</td><td>27.18</td></tr><tr><td>1056.53</td><td>1056.53</td><td>1056.53</td></tr><tr><td>27.21</td><td>27.18</td><td>27.18</td></tr></table></body></html>

其中1056天的周期是经度方向上的自由天平动周期，21.21天和21.18天则是F和wobble引起的。

# 4.总结

本研究利用已有的数值历表数据，开展对月球物理天平动的研究。得到

INPOP19a历表中三个欧拉角的相位时间图像，与INPOP17a,DE430历表进行对比，发现其差值存在着27.3天的周期，识别出了极位置在惯性系下的自由天平动。进一步利用历表数据对月球天平动进行分析，根据卡西尼定则以及国际天球参考系到月球PA坐标系的转换模型，提取得到月球相对于空间的摆动即月球的物理天平动。结果显示，月球的物理天平动存在着一定的周期，但振幅在200毫角秒内，与我们能看到的月面是 $6 9 \%$ 相比，是一个极其微小的摆动量。即在地球上观测月球的天平动时，月球的几何天平动为主要影响因素。把三个历表提取得到的物理天平动作差比较，发现存在一个稳定周期，且此周期与本身的固有周期不同，频谱分析以后得到的此周期并进行了比较。

对提取得到的欧拉角进行分析，计算得到新一代数值历表INPOP19a与DE430，INPOP17a提取得到的欧拉角差别换算到月球激光测距上最多有30厘米的差别。此差别对月球激光测距的预报精度产生较大的影响。INPOP19a在与DE430，INPOP17a对比中，显示出较高的稳定性，故在月球激光测距或者研究物理天平动时，推荐采用历表INPOP19a。

# Research on Lunar Physical Iibrations Based on

# Numerical Ephemeris

Abstract: Lunar librations is a description of the movement of the moon in space. To determine the lunar librations makes it possible to speculate about the excitation and dissipation mechanisms of the libration, such as meteor strikes, moon earthquakes, and viscous friction between the core and mantle. Therefore, the determination of the lunar librations is useful for understanding the origin, evolution, and structure of celestial bodies in the solar system.During the research,I use the latest INPOP2O19a ephemeris data, the conversion of Euler angle extracted from the ephemeris to the lunar physical librations was completed.The numerical model of the physical librations is compared with the ephemeris INPOP17a and DE430.It is found that the difference in physical librations of different ephemerides has a stable period .It is calculated that there is a maximum difference of $3 0 \mathrm { c m }$ between the center of the earth and the lunar reflector A15. This result has a greater impact on the prediction accuracy of the lunar laser ranging.It provides theoretical support for the highprecision lunar laser ranging.The results show that the accuracy of INPOP19a is significantly higher than INPOP17a and DE430, so INPOP19a is recommended in the

research oflunarlibrations.

Keywords: lunar ephemeris,Euler angle,lunar librations,Fourier transform

# 参考文献：

[1]X X Newhal,J. G.Willams.Estimation of the lunar physical librations[J].CELESTIAL MECHANICSAND DYNAMICAL   
ASTRONOMY,1997,66(1). [2]YiQi,AntondeRuiter.Transferstolunarlibrationpointorbits[J].CommunicationsinNonlinearScienceandNumerical   
Simulation,2019,74. [3]N.K.PetrovaYu.A.NfedyevA.A.agidulln,A.O.AdrevUseofanAnalyticalTeoryforthePhysicalLibratiooftheoto   
Detect Free Nutation of the Lunar Core[J]. Astronomy Reports,2018,62(12). [4]Yang YZ,LiJL,ingJS,etal.Determinationof tefreelunarlibration modes fromephemerisDE43OJ].Research inAstronomy and Astrophysics,2017,17(12):91-96. [5]Yang,Yongzhang,etal.“ComparisonandAnalysisonLunarRotationwithLunarGravityFieldModels.”AstrophysicsandSpace Science,vol.363,no.9,2018,p.190. [6]Yang,Yongzhang,etal."Estimationofthelunarfreelibrationmodesbasedotherecentephemerides.”AstrophysSpace Sci (2019) 364: 218. https://doi.0rg/10.1007/s10509-019-3684-z. [7]李金岭,聂昭明,金文敬.用激光测月法测定月球自由天平动[J].科学通报,1989(22):1718-1720 LijinlinniezhaomingjinwenjinMeasuringtheFreelibrationoftheMoonbyLaserLunarRanging[J]ChineseScience Bulletin,1989(22):1718-1720 [8]李广宇,田兰兰.PMOE2003行星历表框架(V)历表文件的生成和使用[J].紫金山天文台台刊,2004(Z1):160-170. Li guangyutialanlan.PMOE203PlanetaryEphemerisFramework(V)CreatingAndUsingofephemerisfiles[J],04(Z1):6-70 [9]李语强,伏红林,李荣旺,汤儒峰,李祝莲,翟东升,张海涛,皮晓宇,叶贤基,熊耀恒.云南天文台月球激光测距研究与实验[J].中国激光, 2019,46(01):188-195. Liyuqiangfuonglin,liongwangtangufengzaidongsheng,zangitaopiiaouyeianjiiongaoeng[J]eseachnd Experiment ofLunar Laser Ranging at Yunnan Observatories[J].Chinese Journal ofLasers,20l9,46(01):188-195 [10]郑向明,郭锐,李语强,等.我国月球激光测距研究与进展[J].天文研究与技术:国家天文台台刊,2007,4(3):231-237. Zheng xiangmingguorui,lyuqiangetal.ResearchandExperimentofunarLaserRanginginChina[J]AstronomicalResearchand Technology: Journal of the National Astronomical Observatory,2007,4(3):231-237.