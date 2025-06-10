# CAPS系统中iHCO卫星轨道演化分析

徐小钧1,²，林荣超¹，马利华¹，艾国祥1．中国科学院国家天文台，北京100012；2.中国科学院大学，北京100049

摘要：中国区域定位系统(Chinese Area Positioning System，CAPS)拟采用比地球静止轨道（Geostationary Earth Orbit，GEO）高 $1 5 0 \sim 3 0 0 ~ \mathrm { k m }$ 的倾斜高圆轨道（inclinedHighly CircularOrbit，iHCO)卫星组建导航通信星座。分析了在多种摄动力和卫星入轨偏差作用下的倾斜高圆轨道卫星的轨道演化过程。该项工作可用于倾斜高圆轨道的优化设计，为利用倾斜高圆轨道卫星组建优良的中国区域定位系统导航通信星座提供参考。

关键词：倾斜高圆轨道卫星；摄动力；入轨偏差；轨道演化中图分类号：V1 文献标识码：A 文章编号：1672-7673(2016)01-0070-05

基于地球静止轨道通信卫星的中国区域定位系统[1，计划将寿命末期的地球静止轨道通信卫星推到高于轨道约 $1 5 0 \sim 3 0 0 ~ \mathrm { k m }$ 的倾斜高圆轨道，并结合已有的地球静止轨道卫星和小倾角的倾斜地球同步轨道（Slightly Inclined Geostationary Orbit，SIGSO)卫星，组成在全球范围内可实现导航通信覆盖的中国区域定位系统星座[2]。在倾斜高圆轨道卫星的运行过程中，不做经度和纬度方向的位置保持，燃料主要用于对地姿态的调整，将大幅度延长卫星的在轨工作寿命。由于倾斜高圆轨道卫星的轨道高于地球静止轨道，其轨道角运动滞后地球自转角运动，卫星相对地球向西漂移。利用卫星向西漂移的特性，可以实现全球范围内的导航通信覆盖[3]。在摄动力作用下，倾斜高圆轨道卫星的轨道参数将发生变化，其轨道倾角逐渐增大，可以改善导航星座布局，提高中国区域定位系统的导航定位性能。在工程应用中，卫星不可能准确地进入设计轨道，实际轨道相对设计轨道存在一定的入轨偏差，入轨偏差在摄动力的作用下也会引起倾斜高圆轨道卫星的轨道参数相对设计值发生一定的改变。

本文重点研究了倾斜高圆轨道卫星的轨道在摄动力影响下的变化规律和入轨偏差引起的轨道演化特性，为选择合适的倾斜高圆轨道卫星的轨道设计指标，组成导航性能优良的中国区域定位系统提供参考。

# 1倾斜高圆轨道卫星的轨道演化

卫星在空间运行时，主要受到地球引力的作用，同时还受到太阳、月亮等天体引力，以及大气阻力、太阳辐射压力等摄动力的影响。在摄动力的作用下，卫星的轨道根数（半长轴 $\mathbf { \alpha } _ { a }$ 、偏心率 $e$ 、倾角i、升交点赤经 $\varOmega$ 、近地点幅角 $\omega$ 和平近点角 $M$ )会随时间变化。倾斜高圆轨道卫星属于高轨卫星，在对该类卫星轨道进行长期稳定性分析时，大气阻力的影响可以忽略不计，主要考虑地球非球形力、日月引力和太阳辐射压力的作用。

由于地球的质量分布不均匀，形状不规则，所以卫星在运行过程中受到地球非球形力的作用，其程度主要取决于卫星的位置和卫星到地球的距离。考虑到地球非球形引力位 $J _ { 2 }$ 项的影响，轨道的长期变化率主要用升交点赤经和沿迹角 $\lambda$ 描述，其中 $\lambda$ 表示卫星的相位：

$$
\varOmega _ { 1 } = \frac { 3 J _ { 2 } } { 2 p ^ { 2 } } n \mathrm { c o s } i ,
$$

$$
\lambda _ { 1 } = \omega _ { 1 } + M _ { 1 } = \frac { 3 J _ { 2 } } { 2 p ^ { 2 } } n \biggl [ \biggl ( 2 - \frac { 5 } { 2 } \sin ^ { 2 } i \biggr ) + \biggl ( 1 - \frac { 3 } { 2 } \sin ^ { 2 } i \biggr ) \sqrt { 1 - e ^ { 2 } } \biggr ] .
$$

其中， $p { = } a { \left( 1 { - } e ^ { 2 } \right) }$ ; $n = \sqrt { \mu / a ^ { 3 } }$ 为卫星的平均角速度； $\mu$ 为地球中心引力常数； $\omega _ { 1 }$ 、 $M _ { 1 }$ 、 $\varOmega _ { 1 }$ 和 $\lambda _ { 1 }$ 为卫星轨道参数 $\omega$ 、M、 $\varOmega$ 和 $\lambda$ 的一阶长期变化项。可见，对于轨道半长轴、偏心率和倾角相同的卫星，在地球非球形力摄动作用下的轨道长期变化相同。通过简单的时间平移和坐标变换可知，由这样一组倾斜高圆轨道卫星组成的导航星座，地球非球形力虽然会导致星座中的绝对相位和轨道平面发生变化，但是卫星之间的相位差和轨道平面之间的相对关系保持不变，因此不会引起星座的空间几何结构和全球覆盖性能的变化[4]。

地球非球形力和日月引力的摄动，可以通过高精度轨道动力学模型仿真分析，而太阳辐射压力的影响主要取决于卫星、太阳和地球之间的相对位置，而且与卫星表面反射特性和面质比有关，无法预测，通常采用模型仿真。以下利用卫星软件工具包(STK)的高精度轨道模型（HPOP)研究上述3种主要摄动力对倾斜高圆轨道卫星的轨道的影响[5-6]。采用倾斜高圆轨道卫星的初始轨道参数为： $a = 4 2 \ 3 6 4$ $\mathrm { k m }$ 、 $e = 0$ 、 $i = 7 ^ { \circ }$ 、 $\varOmega = 1 0 0 ^ { \circ }$ 、 $\omega = 0 ^ { \circ }$ 、 $M = 0 ^ { \circ }$ ，计算中采用 $2 1 \times 2 1$ 阶次的WGS84/EGM96地球模型，太阳辐射压力选择理想模型(球模型)，选用双锥形地影模型，并设置太阳辐射压力系数为1.0，卫星的受晒面质比为 $0 . 0 2 \mathrm { ~ m } ^ { 2 } / \mathrm { k g }$ 。

图 $1 ( \mathrm { a } ) \sim ( \mathrm { d } )$ 分别给出了倾斜高圆轨道卫星在地球非球形力、日月引力和太阳辐射压力作用下的轨道参数演化情况。图1(a)表示在上述3种主要摄动力作用下倾斜高圆轨道卫星的轨道半长轴的年变化。可见，轨道长半轴呈现短周期变化，起伏在 $6 \mathrm { k m }$ 以内。轨道半长轴不存在长期项的原因是地球非球形力和日月引力是保守力，太阳辐射压力在理想模型和不考虑地影作用的情况下，也属于保守力，所以不会引起轨道能量的耗散。由图1(b)可知，在太阳辐射压力的主要作用下，轨道偏心率呈长周期变化，变化量级很小（约 ${ { 1 0 } ^ { - 4 } }$ )，因此倾斜高圆轨道卫星可以长期保持近圆轨道，且可以不考虑近地点幅角的长期稳定性。由图1（c)可知，轨道倾角具有大幅度的长期变化，一年内增加约 $0 . 7 5 ^ { \circ }$ ，其中半年周期变化和半月周期变化分别由太阳和月亮的引力引起。日月引力摄动是引起轨道倾角变化的主要因素，地球非球形力和太阳辐射压力对倾角变化的影响可以忽略不计。由于倾斜高圆轨道卫星倾角在摄动力的作用下不断增大，因此利用倾斜高圆轨道卫星能大大改善中国区域定位系统导航星座的空间布局，提高系统导航定位的性能。由图1(d)可知，地球非球形力引起升交点赤经的长期摄动，同时日月引力引起升交点赤经的长期和长周期变化，每年变化约 $6 ^ { \circ }$ 。

![](images/edb50cd9dd24a16a51ab936da19592e347ddbeef3dd613154997df3abfdaada2.jpg)  
图1倾斜高圆轨道卫星轨道演化  
Fig.1The orbit evolution of the iHCO satellite

由此可知，地球非球形力、日月引力和太阳辐射压力作为主要摄动力对倾斜高圆轨道卫星的轨道稳定性的影响主要体现在倾角和升交点赤经的漂移。因此，可以用倾角和升交点赤经的漂移描述倾斜高圆轨道卫星的轨道稳定性。

# 2入轨偏差影响

在卫星组网的过程中，卫星不可能准确地进入设计轨道。实际轨道和设计轨道之间的偏差称为入轨偏差[7]。人轨偏差通常在设计指标允许的范围内，但是仍然会引起实际轨道和设计轨道在摄动力影响下的不可忽略的差异，所以需要研究入轨偏差对倾斜高圆轨道卫星的轨道演化的影响。

假设倾斜高圆轨道卫星的轨道参数初始偏差为 $( \Delta a , \Delta e , \Delta i , \Delta \varOmega , \Delta \omega , \Delta M )$ ，在 $J _ { 2 }$ 项的影响下卫星升交点赤经、沿迹角的长期摄动变化为

$$
\Delta \varOmega _ { 1 } = - \mathrm { \frac { 7 } { 2 } } \varDelta _ { 1 } \Delta a + \mathrm { \frac { 4 } { \rho } } \mathrm { \frac { \partial } { \partial \rho } } \Delta e - \mathrm { \frac { \sin } { \cos } } \mathrm { \frac { \partial \Delta \varOmega _ { 1 } } { \partial \varDelta { i } } } \Delta i ,
$$

$$
\Delta \lambda _ { 1 } = - \frac { 7 \lambda _ { 1 } } { 2 a } \Delta a + \frac { a e } { p } \left[ \frac { 3 J _ { 2 } } { 2 p ^ { 2 } } n \left( 2 - \frac { 5 } { 2 } \sin ^ { 2 } i \right) + 3 \lambda _ { 1 } \right] \Delta e - \frac { 3 J _ { 2 } } { 4 p ^ { 2 } } n \left( 5 + 3 \sqrt { 1 - e ^ { 2 } } \right) \sin 2 i \Delta i .
$$

其中， $\textit { a , e , i }$ 为设计标称值。另外，半长轴偏差会导致平均角速度的偏差，从而引起沿迹方向的长期变化：

$$
\Delta \lambda = - \frac { 3 n } { 2 a } \Delta a ( t - t _ { 0 } ) ,
$$

其中， $t _ { 0 }$ 为初始时刻。由上式可知，当轨道偏心率接近为0时，偏心率的入轨偏差对轨道的影响可以忽略不计，轨道的升交点赤经和沿迹角在 $J _ { 2 }$ 项作用下的长期变化只与轨道半长轴和倾角的入轨偏差有关，所以对于偏心率几乎为0的倾斜高圆轨道卫星来说，人轨偏差导致的轨道长期变化为

$$
\left[ \begin{array} { l } { \Delta \varOmega _ { 1 } } \\ { \Delta \lambda _ { 1 } } \end{array} \right] = \left[ \begin{array} { c c } { - \displaystyle \frac { 7 \varOmega _ { 1 } } { 2 a } } & { - \displaystyle \frac { \sin i \varOmega _ { 1 } } { \cos i } } \\ { \displaystyle - \frac { 7 \lambda _ { 1 } } { 2 a } - \displaystyle \frac { 3 n } { 2 a } } & { - \displaystyle \frac { 6 J _ { 2 } R _ { \mathrm { e } } ^ { 2 } } { a ^ { 2 } } n \sin 2 i } \end{array} \right] \left[ \begin{array} { l } { \Delta a } \\ { \Delta i } \end{array} \right] .
$$

所以当一组轨道高度、偏心率和倾角均相同的倾斜高圆轨道卫星组成导航星座时，地球非球形力不会引起星座空间几何构型的变化，但是入轨偏差会导致卫星间的相对位置发生变化，从而导致星座结构和覆盖性能发生变化。

对于轨道半长轴为 $4 2 ~ 3 6 4 . ~ 1 4 ~ \mathrm { k m }$ 、倾角为 $7 ^ { \circ }$ 的倾斜高圆轨道卫星，假设入轨倾角偏差为 $0 . 1 ^ { \circ }$ ，分别计算人轨半长轴偏差为 $1 0 0 \mathrm { ~ m ~ }$ 、 $2 0 0 \mathrm { ~ m ~ }$ 和 $5 0 0 \mathrm { ~ m ~ }$ 时的倾斜高圆轨道卫星相位和轨道面变化，结果列于表1。其中综合影响是指 $\Delta a$ 和 $\Delta i$ 的总影响。由此可以看出， $\Delta a$ 是影响沿迹角 $\Delta \lambda _ { \scriptscriptstyle 1 }$ 变化的主要因素，因此半长轴入轨偏差需要满足设计指标要求。

进一步研究倾斜高圆轨道卫星入轨时倾角偏差和半长轴偏差对升交点赤经和沿迹角在一年内轨道演化情况，结果见图2。其中图2(a)和(b)分别表示半长轴入轨偏差为0时，在不同倾角和倾角入轨偏差的影响下，轨道的升交点赤经和沿迹角的长期变化。可见，在轨道倾角一定时，升交点赤经和沿迹角的长期摄动变化随着倾角入轨偏差的不断增加而增大。图2(c)和(d)分别表示在倾角入轨偏差为0的条件下，不同的倾角和半长轴偏差对轨道升交点赤经和沿迹角的长期影响。可以看到，半长轴入轨偏差对升交点赤经变化的影响较小，所以倾角入轨偏差是影响升交点赤经的主要因素。在半长轴入轨偏差的影响下，沿迹角的变化十分剧烈，在倾角一定时，呈线性增长趋势。

表1入轨偏差对卫星相位和轨道面的影响  
Table 1The effect of the bias of the injecting orbit on the phase and plane of the satellite   

<html><body><table><tr><td rowspan="2">影响</td><td colspan="2">△a= 100 m</td><td colspan="2">△a= 200 m</td><td colspan="2">△a= 500 m</td></tr><tr><td>△a</td><td>综合</td><td>△a</td><td>综合</td><td>△a</td><td>综合</td></tr><tr><td>△(°/年)</td><td>3.949 × 10-5</td><td>1.064× 10-3</td><td>7.898 × 10-5</td><td>1.103 × 10-3</td><td>1.975 × 10-4</td><td>1.222 × 10-3</td></tr><tr><td>△(°/年)</td><td>-0. 463</td><td>-0.471</td><td>-0. 927</td><td>-0. 935</td><td>-2.316</td><td>-2.324</td></tr></table></body></html>

![](images/3b8a315cf2b87fd2064300a8613a863bdb50b5c1d263cf8f60ec8de002875e62.jpg)  
图2倾角和半长轴入轨偏差对轨道演化的影响  
Fig.2The eect of the bias of the semi-major axis and the inclination on the orbit evolution

# 3结论

通过以上倾斜高圆轨道卫星的轨道演化及入轨偏差研究，有如下结论：

(1)在日月引力等摄动力的作用下，倾斜高圆轨道卫星的轨道倾角不断增大，可以优化中国区域定位系统的空间布局，提高系统导航的定位性能;

(2)当中国区域定位系统采用半长轴、偏心率和倾角相同的一组倾斜高圆轨道卫星组成导航星座时，在摄动力的作用下，星座的相对几何结构不会发生变化，系统的全球覆盖性能不变，但会造成地域性的整体漂移;

(3)在设置中国区域定位系统导航星座设计指标时，需要考虑倾斜高圆轨道卫星的入轨偏差，由于每颗卫星的入轨偏差具有随机性，在地球非球形力、日月引力和太阳辐射压力等摄动力的影响下，卫星的相位和轨道面会发生变化，进而影响到星座的几何结构;

(4)轨道半长轴入轨偏差是导致卫星实际轨道偏离设计轨道的主要因素，

综上所述，利用倾斜高圆轨道卫星组建中国区域定位系统星座时，需要充分考虑摄动力作用下的倾斜高圆轨道卫星的轨道演化特性，并充分利用倾斜高圆轨道卫星的轨道倾角增加的特性，选择合适的轨道高度，提升中国区域定位系统的导航覆盖性能。采用半长轴、偏心率和倾角相同的倾斜高圆轨道卫星组成中国区域定位系统导航星座时，可以维持星座的空间几何结构的稳定性。同时应该充分考虑入轨偏差对倾斜高圆轨道卫星相位和轨道面的影响，确定合适的倾斜高圆轨道卫星设计指标，使得中国区域定位系统导航性能满足设计任务的需求。

# 参考文献：

[1] Ai Guoxiang，Shi Huli，Wu Haitao,et al.A positioning system based on communication satellitesand the Chinese Area Positioning System（CAPS）[J].Chinese Journal of Astronomy andAstrophysics，2008，8(6) :611-630.  
[2] 林荣超，马利华，艾国祥，等.基于iHCO 通信卫星的CAPS 星座优化研究［J].天文研究与技术——国家天文台台刊，2014，11(3)：230-238.Li Rongchao，Ma Lihua，Ai Guoxiang，et al.A study of the optimization of CAPS constellationsof iHCO communication satellites [J]. Astronomical Research & Technology-Publications ofNational Astronomical Observatories of China，2014，11(3）:230-238.  
[3] 马利华，艾国祥，崔君霞，等.一种利用iHCO 通信卫星实现全球导航定位的方法：中国，201310325604.9[P].2013-7-30.  
[4] 刘林，胡松杰，王歆.航天动力学引论［M]．南京：南京大学出版社，2006.  
[5] 杨颖，王琦.STK在计算机仿真中的应用［M].北京：国防工业出版社，2005.  
[6] 马利华，经姚翔，季海福，等.基于STK的寿命末期GEO卫星轨道演化分析［J]．天文研究与技术—国家天文台台刊，2011，8(4)：347-353.Ma Lihua，Jing Yaoxiang，Ji Haifu，et al.Analysis of evolution of orbits of GEO satellites nearend of life based on the STK software [J].Astronomical Research & Technology———Publicationsof National Astronomical Observatories of China，2011，8(4）:347-353.  
[7] 胡松杰，陈力，刘林.卫星星座的结构演化［J]．天文学报，2003，44(1)：46-54.Hu Songjie，Chen Li，Liu Lin.The structure evolution of satelite constellation ［J].ActaAstronomica Sinica，2003，44(1）:46-54.

# The Orbit Evolution of the iHCO Satellite in the CAPS System

Xu Xiaojun $^ { 1 , 2 }$ ，Lin Rongchao’，Ma Lihua’，Ai Guoxiang1 (1.National Astronomical Observatories，Chinese Academyof Sciences，Beijing 10ol2,China,Email：mlh@nao.cas.cn； 2.University of Chinese Academy of Sciences，Beijing 1Ooo49,China)

Abstract：The inclined Highly Circular Orbit （iHCO）communication satelites，which are on their orbits $1 5 0 - 3 0 0 \mathrm { k m }$ above the Geostationary Earth Orbit（GEO），can build the navigation and communication constellation of Chinese Area Positioning System（CAPS).This paper analyzes the orbit evolution of the iHCO sateliteundertheinfluence of avarietyof perturbation forcesandthebias of thesatelite injecting orbit, which can be used to optimize the design of the iHCO and provide a referenceforthe optimization of the CAPS constellation used of the iHCO satellites.

Key words：Inclined Highly CircularOrbit（iHCO)；Perturbation force；Bias of injecting orbit；Orbit evolution