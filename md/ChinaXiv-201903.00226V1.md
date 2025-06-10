# 拼接镜面主动控制系统的定标

王斌1²，戴懿纯」，许方宇」，金振宇」，杨德华3（1.中国科学院云南天文台，云南昆明650011；2.中国科学院大学，北京100049；3.南京航空航天大学，江苏 南京 211106）

摘要：对拼接主镜进行主动控制是拼接镜技术的难点之一，8m环形拼接太阳望远镜主动光学的控制性能主要取决于倾斜探测的精度与控制模型建立的准确程度。在研制主动控制系统时，需要对倾斜探测精度定标以及建立较为准确的控制模型，即对主动控制系统定标。实验系统中搭建了用于实时探测拼接子镜倾斜的 Shack-Hartmann波前传感器，并对其重复测量精度进行了定标，精度达到0.O14arcsec，接近8mRST面形控制要求。然后利用边缘传感器和 Shack-Hartmann波前传感器测量了两镜主动控制系统的控制矩阵，建立较为准确的控制模型。

关键词：拼接镜；主动控制；Shack-Hartmann波前传感器中图分类号：P111.2 文献标识码：A 文章编号：

8m 环形太阳望远镜（Ring Solar Telescope）是中国巨型太阳望远镜（Chinese Giant SolarTelescope，CGST）计划的重要方案。8mRST计划采用24块面积约为 $1 \mathrm { m } ^ { 2 }$ 的等腰梯形子镜拼接，采用主动光学技术实现主镜的共相[。由于环形拼接形式的特殊性， $\mathrm { 8 m }$ RST 在子镜边缘探测的基础上要增加对子镜倾斜量的探测才能实现主动光学的闭环控制2]。即通过边缘探测器探测子镜边缘高度差的变化，倾斜测量探测子镜倾斜的变化量，从而反演出子镜位置的变化，并通过子镜背面的位移促动器对子镜的姿态进行调节，实现主镜的面形保持。

8mRST拼接镜面主动光学的控制性能主要取决于倾斜测量的精度与控制模型建立的准确程度。文献[2-3]指出了子镜倾斜测量对环形拼接镜面主动控制的重要作用，以及8mRST要实现衍射极限成像的主动面形控制精度所需要的倾斜测量精度。而理论的控制模型依赖于促动器与传感器的几何排布关系，主要描述传感器对促动器的响应情况。但是由于促动器与传感器的安装误差，以及在不同工况环境中传感器和促动器的增益变化，这些因素会引起实际的控制模型与理论控制模型出现偏差和模型的不确定性，影响控制系统的稳定性，导致控制性能的下降[4]。为了获得稳定有效的闭环控制，并对面形控制精度进行充分评估，需要定期对主动光学系统中的测量器件和控制模型进行定标。

在围绕8mRST主动光学关键技术研究的两镜系统主动光学平台中，为了实现其主动光学的闭环控制，在相邻子镜边缘探测的基础上，在子镜边缘增加了 Shack-Hartmann（S-H）波前探测器用于子镜倾斜的实时探测。为此，利用泰曼-格林型的4D干涉仪和子镜上安装的边缘传感器对子镜边缘的 Shack-Hartmann 倾斜测量系统进行了交叉定标，对其测量精度进行了定量评估；在此基础上，对包括边缘传感器和倾斜传感器的两镜系统主动控制模型进行了测量和定标，为两镜系统主动光学闭环实验，后续8mRST高精度倾斜测量技术和闭环控制技术的研制和实现提供了参考。

# 1 两镜主动光学系统的介绍

如图1所示，两镜主动光学系统的控制对象是两块直径 $3 0 0 \mathrm { m m }$ 、边缘厚度大约 $4 0 \mathrm { m m }$ 的半圆形子镜拼接而成的球面反射镜，其曲率半径为 $2 0 0 0 \mathrm { m m }$ 。其中一块固定不动，称之为固定子镜；另一块子镜作相对的3个自由度主动位移（piston、tip/tilt），称之为主动子镜。系统搭建在光学平台上，光轴水平放置。

![](images/7e9c0c6bf4b842d6b8ce2731e2375d14bd27a18e0f13dddeaaa29468bfa5440b.jpg)  
图1 两块拼接子镜示意图。(a)设计参数； (b)实物照片Fig.1 Schematic diagram of the 2-segment mirror.(a)Design Parameters；(b) Photograph of the segmented mirror

两镜主动光学系统的执行机构是位于主动子镜背部的三个位移促动器，呈等腰三角形分布。促动器一端固定在基座上，另一端与主动子镜的镜室连接，位移促动器的执行量产生轴向位移，从而实现控制三个自由度的目的（piston、tip/tilt）。促动器的行程范围是 $\pm 5 \mathrm { m m }$ ，可实现5nm分辨率的轴向位移。

两镜主动光学系统的测量器件包括两部分：

（1）边缘传感器，用于子镜边缘高度的测量。边缘传感器采购的德国PI公司的单极电容位移传感器及其采集系统（D-E30.100型单极电容传感器与E-E12.009型模块化数字机箱及中央处理单元及附件），动态范围 $\pm 1 0 0 \mathrm { u m }$ ，动态分辨率为 $2 \mathrm { n m }$ ，安装在子镜背后的拼缝上。

（2）Shack-Hartmann（S-H）测量系统，用于子镜倾斜的测量[5]。S-H测量系统的核心是微透镜阵列和CCD，整个测量光路如图2(a)所示。测量系统中采用了 $5 ^ { * } 5$ 的微透镜阵列置于出瞳处，如图 2(b)所示。两子镜的拼缝对准最中间一列子孔径。拼缝左侧的两列子孔径用于参考镜倾斜的探测，右侧两列子孔径用于主动镜倾斜的探测。中间一列子孔径可用于子镜间 piston 探测。表1给出了S-H倾斜测量系统的基本参数。

![](images/b2bc0431091397fb1995b98c6274c2e595b535e211b5b7dc0d0e0cc02288c35d.jpg)

表1 S-H测量系统参数  
Table 1 The parameters of the S-H measuring system   

<html><body><table><tr><td>系统通光孔径</td><td>准直镜焦距</td><td>子孔径尺寸</td><td>微透镜阵列焦距</td><td>CCD分辨率</td><td>像元尺寸</td><td>像元分辨率</td></tr><tr><td>12.5mm</td><td>125mm</td><td>2.2mm</td><td>209mm</td><td>2056*2060</td><td>7.4um</td><td>0.2282arcsec/pixel</td></tr></table></body></html>

# 2 S-H倾斜测量系统的精度定标

在两镜主动控制系统中，对S-H探测器倾斜测量的精度进行定标能够为主动控制实施的可能性，最终的面形控制精度以及高精度实时倾斜探测的研制提供评估依据，同时也是建立准确控制模型的基础。在两镜主动控制系统中，对 S-H进行定标首先要解决的问题是“已知像差”或者“基准量”的选取。在这里定义子镜绕Y轴的倾斜为tiltX，绕X轴的倾斜为tiltY，由于子镜拼缝上安装了两个边缘传感器，当子镜具有一定的tiltY时，两个边缘传感器的读数将发生变化，并且由于边缘传感器的具有很高的动态分辨率，因此可以利用两个边缘传感器读数的差值作为已知基准量对S-H的倾斜测量值进行标定。同时，为了验证定标的精度，在S-H测量光路分光棱镜的前端，还引入了泰曼-格林型的4D干涉仪（PhaseCam@6000，测量精度达到0.00012入， $\lambda @ 6 3 2 . 8 \mathrm { n m }$ ），如图2(a)所示，平面反射镜用于4D干涉仪和S-H探测器的切换。采用交叉定标的方式标定S-H倾斜探测的线性度和重复精度。由于两个边缘传感器只能反映子镜tiltY的变化，不能反映子镜tiltX的变化，而 S-H对两个方向倾斜探测算法相同，因此可以通过子镜tiltY倾斜测量的定标精度估算tiltX倾斜测量的精度。

具体的交叉定标方案为：以一定的步长移动位移促动器，即改变子镜的tiltY，记录两个边缘传感器的读数差，作为基准量，分别用4D干涉仪和 S-H探测器对子镜的倾斜进行测量，为了平滑大气湍流以及局部温度对倾斜探测的影响，4D干涉仪采用了32帧测量数据进行积分，S-H探测器采用了50帧。图3是子镜的tiltY连续改变10次，边缘传感器读数差与4D干涉仪倾斜测量值的对应关系；图4是子镜的tiltY连续改变10次，边缘传感器读数差与 S-H 倾斜测量值的对应关系。以边缘传感器读数差为自变量，对上述测量数据按式（1)进行最小二乘拟合。

$$
f ( x ) = p 1 x + p 2
$$

图3的拟合参数为：p1：0.000804 arcsec/nm，p2：-0.0103 arcsec，均方根误差（RMSE）：0.01346 arcsec；图4的拟合参数为：p1：0.0008067 arcsec/nm，p2：-0.00927 arcsec，均方根误差（RMSE）：0.01697arcsec。

![](images/09439def2a23090dc6c232fb40d9d75719380f3580ced4b5795e4738222f317f.jpg)  
图2（a）S-H测量系统光路；（b）子镜与微透镜子孔径对应图 Fig.2(a) The experimental system of S-H sensor；(b)The S-Hlens corresponds to sub-segments   
图3边缘传感器读数差与4D干涉仪测量的tiltY拟合直线 Fig.3The fitting line between the numeric difference of edge sensor and TiltYof 4D interferometer

![](images/5c2e40821fc76c57ddafd0c09a3c71de5f26f57f01a1247177417ab0d11f1cc5.jpg)  
图4边缘传感器读数差与S-H探测器测量的tiltY拟合直线 g.4The fitting line between the numeric difference of edge sensor and TiltY of S-H sensor

分别采集8组测量数据，对每组数据都进行线性拟合，8组数据拟合参数的均值和标准差如表2，表3所示。

# 表2边缘传感器读数差与4D干涉仪tiltY测量值的拟合参数

Table 2The fitting parameters between the numeric difference of edge sensorand TiltY of 4D interferometer   

<html><body><table><tr><td></td><td>P1(arcsec/nm)</td><td>P2(arcsec)</td><td>RMSE(arcsec)</td></tr><tr><td>均值</td><td>8.017×10-4</td><td>0.0112</td><td>0.0117</td></tr><tr><td>标准差</td><td>7.496×10-6</td><td>0.0139</td><td>0.0029</td></tr></table></body></html>

# 表3边缘传感器读数差与S-H探测器tiltY测量值的拟合参数

Table 3The fitting parameters between the numeric difference of edge sensor and TiltY of S-H sensor   

<html><body><table><tr><td></td><td>P1(arcsec/nm)</td><td>P2(arcsec)</td><td>RMSE(arcsec)</td></tr><tr><td>均值</td><td>8.064×10-4</td><td>0.0061</td><td>0.0144</td></tr><tr><td>标准差</td><td>3.829×10</td><td>0.012</td><td>0.002</td></tr></table></body></html>

从拟合的结果看，S-H测量的重复线性度非常好，与4D干涉仪的测量结果也非常近似。在目前的实验条件下S-H重复测量精度达到了0.014arcsec，此测量精度与两镜系统位移促动器的执行精度相匹配。

# 3 两镜系统主动控制模型的实测定标

# 3.1理论的主动控制模型

两镜系统的主动控制模型在传感器和促动器的线性范围内可用（2）式表示，

$$
\mathbf { y _ { m } } = \mathbf { A x } + \mathbf { n } ,
$$

其中 ${ \bf y _ { m } }$ 为探测向量，由边缘传感器测量值和倾斜传感器测量值共同组成； $\mathbf { x }$ 为位移促动器的执行量； $\mathbf { n }$ 为探测噪声；矩阵A为控制矩阵，其反应了位移促动器和传感器之间的几何对应关系[7]。

![](images/bf5fa0e431c73f58d8ddd9f90dca1e21944edae9ae2c2a13e72d89ac959bb541.jpg)  
图5子镜促动器与边缘传感器几何排布情况 Fig.5Geometric arrangement of actuator and edge sensor

根据图5所示的几何排布形式，当促动器M1有变化 $\Delta \mathrm { m }$ ，整个子镜会以促动器 M2和 M3

的连线为轴进行旋转，每个边缘传感器的变化量为：

$$
\Delta s = \frac { r \Delta m } { h }
$$

其中r是边缘传感器到旋转轴的垂直距离， $\mathbf { h }$ 是促动器到旋转轴的垂直距离[8]。根据表达式（3），可以列出子镜上每个边缘传感器的变化量与促动器变化的关系：

$$
\Delta s _ { \mathrm { 1 } } = \frac { r _ { \mathrm { 1 1 } } \Delta m _ { \mathrm { 1 } } } { h _ { \mathrm { 1 1 } } } + \frac { r _ { \mathrm { 2 1 } } \Delta m _ { \mathrm { 2 } } } { h _ { \mathrm { 2 1 } } } + \frac { r _ { \mathrm { 3 1 } } \Delta m _ { \mathrm { 3 } } } { h _ { \mathrm { 3 1 } } }
$$

$$
\Delta s _ { 2 } = \frac { r _ { 1 2 } \Delta m _ { 1 } } { h _ { 1 2 } } + \frac { r _ { 2 2 } \Delta m _ { 2 } } { h _ { 2 2 } } + \frac { r _ { 3 2 } \Delta m _ { 3 } } { h _ { 3 2 } }
$$

而子镜自身绕 $\mathrm { \Delta Y }$ 、X轴的倾斜变化用位移促动器的变化可以表示为：

$$
T x = \frac { \Delta m _ { 1 } + \Delta m _ { 3 } } { 2 } - \Delta m _ { 2 }
$$

$$
T y = \Delta m _ { 1 } - \Delta m _ { 3 }
$$

为了将其与边缘探测统一起来，需要将式（6）和（7）转换成子镜边缘高度的变化， $T x , T y$ 分别乘以各自边缘高度转换系数，即 $\Delta s _ { t x } = a _ { t x } T x$ ， $\Delta s _ { t y } = a _ { t y } T y$ 。从而，两镜系统的主动控制模型为：

$$
\left( \begin{array} { c } { \Delta s _ { 1 } } \\ { \Delta s _ { 2 } } \\ { \Delta s _ { \iota _ { w } } } \\ { \Delta s _ { \iota _ { v } } } \end{array} \right) = \left( \begin{array} { c c c } { \frac { r _ { 1 1 } } { h _ { 1 1 } } } & { \frac { r _ { 2 1 } } { h _ { 2 1 } } } & { \frac { r _ { 3 1 } } { h _ { 3 1 } } } \\ { \frac { r _ { 1 2 } } { h _ { 1 2 } } } & { \frac { r _ { 2 2 } } { h _ { 2 2 } } } & { \frac { r _ { 3 2 } } { h _ { 3 2 } } } \\ { 0 . 5 a _ { \iota _ { w } } } & { - a _ { \iota _ { w } } } & { 0 . 5 a _ { \iota _ { w } } } \\ { a _ { \iota _ { v } } } & { 0 } & { - a _ { \iota _ { v } } } \end{array} \right) \left( \begin{array} { c } { \Delta m _ { 1 } } \\ { \Delta m _ { 2 } } \\ { \Delta m _ { 3 } } \end{array} \right)
$$

根据设计的理论值可以计算出两镜系统的控制矩阵为：

$$
\begin{array} { r } { \mathbf { A } = \left( \begin{array} { c c c } { - 1 . 5 4 0 4 } & { 0 . 6 4 } & { - 0 . 0 9 9 5 } \\ { - 0 . 0 9 9 5 } & { 0 . 6 4 } & { - 1 . 5 4 0 4 } \\ { 0 . 6 8 } & { - 1 . 3 6 } & { 0 . 6 8 } \\ { 1 . 5 2 8 1 } & { 0 } & { - 1 . 5 2 8 1 } \end{array} \right) } \end{array}
$$

3.2实测的主动控制模型

利用边缘传感器和倾斜传感器对位移促动器的实际响应，对两镜系统的主动控制矩阵进行定标。根据式（8）前两行，通过促动器的执行量和实测的边缘传感器变化，求取相应的响应系数。测量方法：首先固定促动器M2、M3不动，M1一次执行10步，执行后记录边缘传感器1和2的变化值，重复执行25次；接着M2、M3也分别重复上述操作，并记录边缘传感器的变化值。促动器变化引起的边缘高度变化的均值与标准差如表4所示。

表4 促动器执行引起边缘传感器的变化  
Table 4 Change of edge sensor caused by actuator execution   

<html><body><table><tr><td></td><td colspan="2">M1</td><td colspan="2">M2</td><td colspan="2">M3</td></tr><tr><td></td><td>均值/nm</td><td>标准差/nm</td><td>均值/nm</td><td>标准差/nm</td><td>均值/nm</td><td>标准差/nm</td></tr><tr><td>△s1</td><td>-74.73</td><td>2.61</td><td>28.03</td><td>1.69</td><td>-5.71</td><td>1.94</td></tr><tr><td>△s</td><td>-5.73</td><td>1.63</td><td>30.13</td><td>1.87</td><td>-78.66</td><td>2.41</td></tr></table></body></html>

根据式（8）后两行，通过促动器的执行量和实测的子镜倾斜量，求取相应的倾斜响应的转换系数。测量方法：固定促动器M1和M3，促动器M2一次执行20步，执行后记录S-H探测器tiltX测量值，重复执行45次；固定促动器M2，促动器M1一次执行20步，促动器M3一次执行-20步，执行后记录S-H探测器tiltY测量值，重复测量45次。子镜 tiltX、tiltY探测的均值和标准差如表5所示：

# 表5促动器执行引起 S-H传感器的变化

Table 5Change of S-H sensor caused   

<html><body><table><tr><td>探测量</td><td>均值/arcsec</td><td>标准差/arcsec</td></tr><tr><td>tiltX</td><td>0.2864</td><td>0.0218</td></tr><tr><td>tiltY</td><td>0.2279</td><td>0.0216</td></tr></table></body></html>

根据上述实测探测器响应得到的控制矩阵为：

实测的主动控制矩阵与理论的控制矩阵存在明显的偏差，偏差项最大可达 $1 4 . 1 6 \%$ 。事实上在动镜系统理论的设计方案中，促动器M1和M3的位置是关于半圆对称的，而两个边缘传感器的安装位置在半圆子镜的边缘也是对称，因此当促动器M1和M3执行相反方向的相同位移，两个边缘传感器的变化量应该相同，只是方向相反。但是经过测量发现边缘传感器1的变化量始终小于边缘传感器2的变化量。这说明促动器和边缘传感器之间存在一定的安装误差，这种安装误差连同促动器的执行误差导致了边缘传感器的实际响应以及倾斜探测的实际边缘高度转换系数与理论值的偏差，从而造成了实际控制矩阵偏离理论控制矩阵。

# 4 讨论和结论

本文利用4D干涉仪和子镜的边缘传感器对两镜系统的S-H倾斜探测器的倾斜测量线性度和重复测量精度进行了定标，其重复测量精度达到0.014arcsec。这种精度接近8mRST实现在1微米波长衍射极限的面形控制要求，但是目前的测量精度是在实验室内大气条件较为平稳的情况下获得的，在具有明显湍流影响下的倾斜测量精度还需要进一步实验确认，而本文采用的交叉定标方法可以用于不同实施条件下S-H倾斜探测和其他倾斜测量方案精度的定标。

本文利用边缘传感器和S-H实测了两镜主动控制系统的控制矩阵，由于促动器和传感器的安装误差，实测控制矩阵与理论控制矩阵存在明显差异，后续将结合主动控制系统的闭环实验研究控制矩阵差异对主动控制性能的影响，从而对促动器和传感器的安装误差容限提出要求。文中所述的定标主要用于标定由于传感器和促动器安装误差导致的准静态的主动控制矩阵误差。定期对控制矩阵进行实测定标是解决控制矩阵误差随机性的一个可能方案，在后续的工作中进一步分析和分解误差的来源，研究合理的定标周期。

# 参考文献：

[1] Liu Zhong,Deng Yuanyong, Jin Zhenyu,et al. Introduction to the Chinese Giant Solar Telescope[J]. Proc SPIE, 2011, 8444(1): 844405-9.   
[2] Dai Y C, Yang D H, Zago L, et al. Dynamic analysis of the active control system for the CGST[J].Proceedings of SPIE 2012,8449:84491A.   
[3] Dai Y C， Yang D H, Jin Z Y，et al. Active control of the Chinese Giant Solar Telescope[J].Proceedings of SPIE,2014,9145:914550.   
[4] Macmynowski D G,et al. Interaction matrix uncertainty in active(and adaptive) optics[J].Applied Optics ,2009,48(11):2105-2114.   
[5] 袁沭，金振宇，李银柱 等．大气湍流对环形拼接望远镜主动控制中光学倾斜测量的 影响 [J].光学学报,2012,32(12): 26-31. Yuan Shu, Jin Zhenyu, Li Yinzhu, et al. Effect of Atmospheric Turbulence on Optical Tip Measurement of Active Control of Ring Segmented Telescope [J]. Acta Optica Sinica, 2012,32(12):26-31.   
[6] 李新阳，姜文汉.哈特曼-夏克传感器的泽尼克模式波前复原误差[J].光学学报,2002, 22(10): 1236-1240. Li Xinyang, Jiang Wenhan. Zernike modal wavefront reconstruction error of Hartmann Shack wavefront sensor [J].Acta Optica Sinica, 2002, 22(10): 1236-1240.   
[7] Chanan G, Macmartin D G, Nelson J,et al.Control and Alignment of Segmented-Mirror Telescopes:Matrices, Models and Error Propagation[J].Applied Optics,2004,43(6):1223.   
[8] Yichun Dai, Zhong Liu, Zhenyu Jin, et al. Active control of a $3 0 \mathrm { m }$ ring interferometric telescope primary mirror [J]. Applied Optics,2009, 48(4): 664-71.   
[9] 袁述．局地大气温度梯度对环形拼接望远镜主动控制中光学测量的影响[J]．天文研 究与技术,2013,10(4):410-415. Yuan Shu，et al.Effects of a Local Atmospheric Temperature Gradient on Optical Measurement for the Active Control of a Segmented-Ring telescope[J].Astronomical Research&Technology, 2013,10(4):410-415.

# Calibration of the Active Control System of Segmented Mirror

Wang Bin1,2，Dai Yichun’，Xu Fangyu1，Jin Zhenyu1，Yang Dehua³ (1.Yunnan Observatories，Chinese Academy of Sciences，Kunming 65ool1，China，Email: daiyichun@ ynao.ac.cn; 2.University of Chinese Academy of Sciences，Beijing 1Ooo49，China; 3.Nanjing University of Aeronautics and Astronautics，Nanjing 2111O6，China)

Abstract: Active control of the segmented primary mirror is one of the key technologies.The control performance of the active optics of the $8 \mathrm { m }$ ring solar telescope mainly depends on the accuracy of the tip/tilt detection and the accuracy of the control model.When developing an active control system, it is necessary to calibrate the tip/tilt detection accuracyand establish a more accurate control model, that is,to calibrate the active control system.A Shack-Hartmann wavefront sensor for detection of the tip/tilt of the segmented mirrors is built in the experimental system,and the repeating measurement accuracy is scaled to an accuracy of O.O14 arcsec, which is close to the 8mRST shape control requirement.Then the edge sensor and Shack-Hartmann wavefront sensor are used to measure the control matrix of the two-segment mirror active control system, and a more accurate control model is established.

Keywords: Segmented primary mirror； Active control； Shack-Hartmann wavefront sensor