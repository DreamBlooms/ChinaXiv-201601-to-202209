# 基于MODIS云参数的卷云反射率计算研究

赵凤美1,²，戴聪明²\*，魏合理1²，朱希娟³，马静³(中国科学技术大学环境科学与光电技术学院，安徽合肥2300262中国科学院安徽光学精密机械研究所中国科学院大气光学重点实验室，安徽合肥2300313北京环境特性研究所光学辐射重点实验室，北京100854)

摘要：卷云反射率是天气、气候和地球能量平衡研究中关注的重要参数。卷云反射率的快速算法在遥感反演卷云特性参数中具有重要应用。依据卷云反射率随卷云光学厚度、有效尺度、太阳天顶角、观测天顶角、相对方位角等参数的变化，利用离散坐标法（DISORT）计算卷云反射率，预先建立卷云反射率随相关参数变化的快速查找表，以此建立了卷云反射率的快速算法。将MDIS卫星探测的卷云光学厚度、太阳天顶角、观测天顶角、相对方位角等因素作为输入参数，计算得到了卷云反射率，比较了计算的卷云反射率和MODIS实际测量的卷云反射率值，相关系数达到0.94，平均偏差小于 $1 8 . 5 \%$ ，说明了卷云快速算法计算合理可行。

关键词：卷云；反射率；计算；MODIS

中图分类号：P401 文献标识码：A 文章编号：xxxx-xxxx-xxxx-xxxx-xx

# Calculating the reflectance of cirrus cloudsbased on cirrus properties from MODIS

ZHAO Feng-mei1,²， DAl Cong-ming2\*，WEl Heli1,2, ZHU Xi-juan², MA Jing ('School of Environmental Science and Optoelectronic Technology，University of Science and Technology of China，Hefei 230026，China

2Key Laboratory of Atmospheric Optics,Anhui Institute of Optics and Fine Mechanics, Chinese Academy of Sciences，Hefei，Anhui 230031，China

Science and Technology on Optical radiation Laboratory， Beijing Institute of Environmental Features, Bei jing，100854)

Abstract: The reflectance of cirrus clouds is an important parameter in weather,climate and earth energy balance studies.The fast algorithm for calculating the reflectance of cirrus clouds plays an importance role in the retrieval the characteristicsofcirrusclouds.Based on the variations of the reflectance of cirus clouds with the relevant factors，such as cirrus optical thickness,effective particle size，solar zenith angle, observation zenith angle,the relative azimuth angle et al,a prepared Look-Up-Table(LUT) was developed by using DISORT to compute the reflectance of cirrus clouds.A fast algorithm for calculating the cirrus reflectance was established with utilization of the LUT.The cirrus reflectivity was calculated from the parameters of cirrus clouds,including cirrus optical thickness,effective particle size,solar zenith angle, observation zenith angle,the relative azimuth angle,which were read from the cloud products of MODIS. A comparison between the derived reflectivity with the proposed fast algorithmand the measured one was performed.The correlation coefficient is O.94 and an average deviation isless than $1 8 . 5 \%$ . The result indicates that the fast algorithm for calculated cirrus reflectance is reasonable and feasible.

Keywords :Cirrus cloud;Reflectance; calculation;MODIS

# 0引言

卷云一般位于对流层上部和平流层下部，通过反射太阳辐射(反射率效应)、吸收地表和低层大气的热辐射以及自身发射的红外辐射（吸收效应）来调节地球大气的辐射收支[]。观测表明卷云与暖的水云不同，是由具有不同形状和大小的非球形冰晶组成，其形状、大小和光学厚度决定了是卷云反射率效应还是吸收效率在地球能量收支平衡中起主要作用，导致很难准确掌握卷云对地-气系统能量收支的影响，卷云辐射特性是大气科学中几个没有解决的难题之一[2]

计算卷云的反射辐射对于遥感和研究大气背景辐射等方面具重要的意义。精确计算卷云反射率的前向模式是利用散射法反演卷云的微物理性质的前提；卷云反射太阳辐射和发射辐射对于处于对流层以上的光学探测仪器具有不可忽略的影响；薄卷云影响晴空大气背景辐射，对于研究全球气候变化也具有重要的影响。因此，对卷云的研究是一个科学热点和难点问题。

对卷云的观测主要包括飞机取样和遥感探测两种方式，其中卫星遥感探测为提高、检测云物理模型、气候预报模型等提供了大量基础数据。1996年在美国东部Kansas的超音速飞机尾气和云效应专项研究试验SUCCESS(SUbisonicaircraft Contrail & Clouds Effect SpecialStudy) (http://cloudl.arc.nasa.gov/espo/success/)对卷云进行了系统的观测，研究卷云冰晶粒子的微物理性质，卷云的形成、演化，卷云的辐射性质以及对大气的影响；Goldfarb 等[3]利用地基雷达观测卷云发生频率、卷云光学厚度等进而分析卷云气候特征；MODIS（ModerateResolution Imaging Spectroradiometer）卫星利用 $1 . 3 7 5 \mathrm { ~ \textmu ~ m ~ }$ 水汽强吸收带的反射及其与$0 . 6 4 5 {  { \mu \mathrm { ~ m ~ } } }$ 波段反射率之间关系测得卷云的反射率。

采用数值模拟的方法来计算卷云反射率是遥感反演卷云的基础。赵燕杰等[5利用逐线积分法计算了大气分子吸收并结合离散坐标法(DIScreteOrdinateRadiative Transfermethods，DISORT)建立了卷云条件下的光辐射传输模式，模拟计算了实心六棱柱状冰晶粒子组成的卷云在 $1 . 0 6 4 \mu \mathrm { ~ m ~ }$ 时的散射特性。曹亚楠等[6]利用通用辐射大气传输计算软件（CART）[7]模拟计算了 $0 . 4 \substack { - 2 . 5 \mu \mathrm { ~ m ~ } }$ 波段卷云大气反射率，分析了卷云大气的反射率随波长、光学厚度、有效尺度、卷云高度和地表类型变化情况，并模拟计算和分析了 $0 . 5 5 \ \mu \mathrm { \ m } , \ 1 . 3 8 \ \mu \mathrm { \ m } , \ 2 . 7 5 \ \mu \mathrm { \ m }$ 波段卷云大气反射率之间的关系。

本文基于卷云反射率查找表(LUTs)，建立了卷云反射率的快速算法，研究卷云反射率与卷云特性参数及观测和太阳几何的变化特性。在此基础上，将计算的卷云反射率与MODIS卫星实际观测卷云反射率对比，检验卷云反射率快速算法的准确性。

# 1卷云反射率计算方法

# 1.1卷云的平均单次散射特性

卷云单次散射特性与卷云冰晶粒子形状、大小等参数有关，并且是波长的函数。利用 Yang等[8计算的几种冰晶粒子的散射特性数据库，采用「分布描述卷云中冰晶粒子的尺度分布，结合样条拟合方法可以获得各种有效尺度和波长下由单一冰晶粒子组成的卷云平均单次散射特性数据库[9]。本文考虑粒子形状、种类和尺度谱分布，并融合不同种类冰晶粒子的加权比例系数，得到卷云的平均单次散射特性参数：

平均单次散射反照率：

$$
\varpi = \frac { \overline { { \beta } } _ { s } } { \overline { { \beta } } _ { e x t } } = \sum _ { \mathrm { i } = 1 } ^ { 3 } f _ { _ i } \tilde { \omega } _ { i }
$$

平均消光系数：

$$
\overline { { \beta } } _ { _ { e x t } } = \int _ { D _ { \operatorname * { m i n } } } ^ { D _ { \operatorname * { m a x } } } \biggr [ \sum _ { i = 1 } ^ { 3 } f ( i , D ) _ { \sigma _ { e x t } } ( i , D ) n ( D ) \biggr ] d D
$$

平均散射相函数：

$$
\begin{array}{c} \begin{array} { r l } & { \qquad \overset { D _ { \mathrm { m a x } } } { \underset {  [ \Theta ] } { \prod } } \Biggl [ \underset { i = 1 } { \overset { 3 } { \sum } } f ( i , D ) P ( \Theta , i , D ) \pmb { \sigma } _ { s c a } ( i , D ) n ( D ) \Biggr ] \overset { } { d } D } \\ & { \qquad \overset { \overline { { D } } _ { \mathrm { m i n } } } { \underset {  [ D _ { \mathrm { m i n } } ] } { \sum } } \Biggl [ \underset { i = 1 } { \overset { 3 } { \sum } } f ( i , D ) \pmb { \sigma } _ { s c a } ( i , D ) n ( D ) \Biggr ] \overset { } { d } D } \end{array} = \sum _ { i = 1 } ^ { 3 } f _ { i } \mathbf { P } _ { i } ( \Theta )  \end{array}
$$

其中， $i$ 表示第 $i$ 种形状的冰晶粒子， $D$ 表示冰晶粒子的尺度参数， $f _ { _ i } \cdot \ \sigma _ { \mathrm { e x t } } .$ P(0)分别表示第i种冰晶粒子所占的百分比、消光截面、相函数。目前认为热带卷云主要是由聚合物、实心六棱柱、子弹花瓣三种形状的冰晶粒子组成，对应的比例系数依次是： $4 1 . 6 \%$ 、 $3 3 . 7 \%$ ， $2 4 . 7 \%$ 。

图1给出了卷云在 $0 . 6 6 ~ \mu \textrm { m }$ 波长的平均单次散射反照率和平均散射效率因子随有效尺度的变化。从图1（a）中可以看出平均单次散射反照率基本接近1（均大于0.99)，而图1（b）中可以看到当冰晶粒子尺度大于等于 $2 0 ~ \mu \textrm { m }$ 时，平均散射效率因子基本为2,这说明了卷云在0.64um 附近对于可见光的影响主要是散射，吸收在消光中仅仅占很小的一部分，可以忽略。图 2给出了平均相函数随散射角的分布图,从图中可以看出综合三种冰晶粒子的结果，前向散射很强，导致相函数前向非常尖锐。在散射角为 $2 2 ^ { \circ }$ 和$4 6 ^ { \circ }$ 附近出现明显的晕、峰值，在 $1 4 0 ^ { \circ } \ \stackrel { \sim } { \sim } 1 6 0 ^ { \circ }$ 之间有一个较为宽阔的极大值，这是由于卷云的外反射以及内反射产生。而在 $7 ^ { \circ }$ 附近产生的极值主要是由于子弹花瓣状冰晶的散射2特性造成的。

![](images/52de5d750caeddc9d05527c2789a5c0d46b562d153c793741e44ae6ea46c1ddc.jpg)  
图1平均单次散射反照率、散射消光效率随冰晶有效尺度的变化 Fig1 Average Single scattering albedo and absorption efficiency versus the effective size

![](images/7a0ecee68e3f26bf6302de5b597eb4d7916c5cafb43bd5750aa692916032a60f.jpg)  
图2平均相函数随散射角变化

Fig2 Average Phase functionversus scattering angle

# 1.2建立卷云反射函数查找表（LUTs）

DISORT是Chandrasekhar(1950)为了求解辐射在行星大气中传输提出的一种方法，可以计算的波长涵盖了紫外到微波波段，Liou(1973a）证明了DISORT对于计算气溶胶和有云大气中的辐射场是一种既有用又有效的方法[2]。本文采用StamnesDISORT 2.0β版计算卷云反射率[10]，将散射相函数展开为勒让德Legendre）多项式，用δ－fit方法截断相函数前向函数系数[11]。

卷云双向反射率：

$$
{ \mathrm R } ( \mu , \phi ; \mu _ { \mathrm { 0 } } , \phi _ { \mathrm { 0 } } ) = \frac { \pi I ( 0 ; \mu , \phi ) } { \mu _ { \mathrm { 0 } } F _ { \otimes } }
$$

其中 $I$ 表示辐射强度， $F _ { \otimes }$ 是大气层顶部太阳直接辐射通量, $\mu _ { \circ } \cdot \ \phi _ { \circ } \cdot \ \mu \cdot \ \phi$ 分别指太阳天顶角余弦、太阳方位角、观测天顶角余弦、观测方位角。由公式（4）可知，卷云反射率与卷云光学性质、太阳天顶角、观测天顶角、相对方位角等有关，卷云光学性质包括光学厚度、单次散射反照率和散射相函数。

利用DISORT计算了不同太阳位置和观测几何下的卷云反射率，其中太阳天顶角和观测天顶角范围均是 $0 ^ { \circ } \sim 7 5 ^ { \circ }$ （根据观测几何特点确定的)，各16个取样点，每 $5 ^ { \circ }$ 一个间隔，观测和太阳的相对方位角范围为 $0 ^ { \circ } \ \sim 1 8 0 ^ { \circ }$ ，共19个取样点，每 $1 0 ^ { \circ }$ 一个间隔。卷云光学厚度范围是 $0 . 0 0 2 { \sim } 9 0$ ，冰晶粒子的有效尺度设为 $5 0 ~ \mu \textrm { m }$ 。这样建立了在 $0 . 6 6 \mu \mathrm { ~ m ~ }$ 波段下各光学厚度、太阳和观测几何角度下对应的卷云反射率数据库。

![](images/684426f4997244fc3a54a4dfedd1b6cc2bb2e17fa024af6ecc4cf04cf92fd5c6.jpg)  
图3卷云反射率随光学厚度、有效尺度、太阳天顶角、相对方位角的变化  
Fig3Cirrus reflectance versus Optical thickness,Effective diameter, Solar zenith,Azimuth.

图3显示了在 $0 . 6 6 ~ \mu \textrm { m }$ 波段卷云反射率随光学厚度τ、有效尺度De、太阳天顶角、相对方位角的变化。图3（a）中可以看出卷云反射率R随光学厚度的增加迅速增大，当τ大于等于 3时，反射率随光学厚度的增大而增大的趋势不变，但是增长率变小了（由于光学厚度大于20 时，反射率变化很小，故未画出)；当τ小于3时，反射率和光学厚度几乎成线型关系。图3（b）显示了 $0 . 6 6 \mu \mathrm { ~ m ~ }$ 波段卷云反射率随冰晶粒子的有效尺度的变化。在粒子有效尺度很小时，比如小于 $1 5 \mu \mathrm { m }$ ，反射率随粒子尺度增大而减小（特别是在光学厚度比较大的情况下)。对于大粒子的一般情况下，反射率随冰晶粒子的有效尺度变化不明显，因此，本文把粒子尺度设为固定值$5 0 \mu \mathrm { m }$ 。从图3（c）可以看出卷云反射率随太阳天顶角的增大而增大；根据计算结果还发现卷云反射率随观测天顶角的增大而增大（文中未画出)。由图3(d)可以看出当相对方位角小于 $2 0 ^ { \circ }$ 或者大于 $1 4 0 ^ { \circ }$ 时，相对方位角的变化，对反射率的影响很小，在其它相对方位角，反射率随方位角的变化需要考虑。从图3中可以看出，光学厚度对卷云反射率的影响最大，至于观测天顶角、太阳天顶角、相对方位角等几何角度对于反射率的影响比较复杂，可分段考虑，有效尺度的影响在粒子尺度较大时可以忽略不计。

我们根据已经建立的卷云反射率数据查找表，给定的卷云的光学厚度、太阳天顶角、观测天顶角、相对方位角等，可快速从查找表中查询到对应的卷云反射率。

# 2计算结果与分析

中分辨率成像光谱仪 MODIS是EOS 计划的Terra 和 Aqua 卫星携带的重要传感器[6]，覆盖可见到长波红外波段，共36个光谱波段。本文采用的是Terra 卫星上MODIS 传感器获得的云产品 MOD06以及MOD03 数据地理定位产品，其中MOD06是MODIS数据产品中的大气2级标准数据产品中的云产品，其不仅给出了云的光学厚度、有效尺度、云相态等，还给出了测得的卷云反射率。MOD06中测得的卷云反射率是利用 $1 . 3 8 {  { \mu \mathrm { ~ m ~ } } }$ 和可见光波段双通道算法得到的。由于 $1 . 3 8 {  { \mu \mathrm { ~ m ~ } } }$ 波段是水汽强吸收波段，太阳辐射透过卷云后被大气中的底层水汽几乎完全吸收，该波段的反射辐射仅是卷云的反射，故MODIS采用该波段遥感卷云的反射率[12]。

利用从MOD06 中的云相态产品中找出冰云像元，并得到选定区域每个冰云像元的有效尺度、光学厚度，从与MOD06同时刻同地区的MOD03产品中读取该像元的几何参数，包括经、纬度、太阳天顶角、观测天顶角、太阳方位角、观测方位角。用这些数据作为输入，结合查找表LUTs用线型插值法快速找到对应像元的反射率。

![](images/db0436ecba58c7a5ae6566be6f804428cac47c337c49b41ecec318a6bb6cebcb.jpg)  
图4UTC时间13/07/200202：55M0DIS云图中冰云光学厚度及所选定的区域

Fig4 Optical thickness of cirrus in selected tropical area

![](images/616b28e0c5f17ea7f11dd58c3006f4b63d6ecd63688024fbd1c5556adbc661f0.jpg)

![](images/ef0fc8436f6ab65d55cd8e7ecf2b83fe563e8045ded96868171f1bbba9eec414.jpg)  
图5选取区域框内计算的卷云反射率

Fig5.Reflectance of cirrus clouds by DISORT in the selected

boxes.

![](images/2eb9515daac72cc490db4865de2e6973975a74e474ec606d629e50c850e29235.jpg)  
图6选取区域中框内MODIS观测的卷云反射率

Fig6.Themeasurements reflectance of cirrus clouds within the boxesfrom MODIS product.

图4为从MOD06中读取的卷云光学厚度，左图是 $8 5 ^ { \circ } \mathrm { ~ \ E \sim 1 1 5 ^ { \circ } ~ }$ E、 $5 ^ { \circ } \ \mathrm { ~ S } { \sim } 1 0 ^ { \circ } \ \mathrm { ~ N ~ }$ 区域在UTC时间为 $1 3 / 0 7 / 2 0 0 2 0 2 \colon 5 5$ 云相态为冰云像元的光学厚度。选定两块区域作为研究区域，如图中红色框 $( 9 0 ^ { \circ } ~ \mathrm { { E } } , 7 ^ { \circ } ~ \mathrm { { N } }$ 附近)和黄色框区域( $9 8 ^ { \circ } \mathrm { ~ E ~ }$ $9 ^ { \circ } \mathrm { ~ N ~ }$ 附近)。图5是根据MODIS卷云产品参数从查找表中快速得到的反射率值，其中图5中的（a）（b）分别对应于是图4（a）中红色框、黄色框内区域。图4和图5中黑色区域为云相态为非冰云的像元。对比图4(b)和图5(a)可知，卷云反射率的变化和光学厚度变化相一致。图6显示的是从MOD06中读取的卷云反射率值，图6（a）、（b）图分别对应于图4中的红、黄色框区域。对比图5和图6的(a)、（b）可以看出从快速查找表中计算出的卷云反射率值和MODIS的测量值变化一致。MOD06产品中卷云反射率是用$1 . 3 8 ~ \mu \mathrm { ~ m ~ }$ 水汽强吸收带卷云对太阳的散射遥感得到的，卷云光学厚度、有效尺度等参数是依据大气窗区的 $1 . 6 \mu \mathrm { { m } }$ 和 $2 . 1 \mu \mathrm { ~ m ~ }$ 通道采用Nakajima-King 的方法遥感得到的[13]。我们采用不同机制遥感的卷云特性参数，根据我们建立的LUTs计算出卷云反射率与MODIS遥感测得的卷云反射率具有一致性，说明了利用DISORT根据卷云实际参数计算反射率的有效性，证明了快速算法的正确性。

图7是不同像元的卷云反射率计算值和MODIS实际观测值的对比图。通过分析发现两者的相关性达到0.94，除个别点外，卷云反射率的计算值比观测值略大，拟合斜率为1.1，产生差异可能原因有：MODIS对很薄的卷云定量遥感可能有一定的误差，造成小光学厚度时本文计算与观测的相对误差较大；遥感云相态和卷云特性的算法中采用的红外通道的分辨率与1.38微米通道的空间分辨率也不完全一致；本文的算法中假设的卷云冰晶粒子的各形状所占的比例与实际冰晶粒子的成分差别造成的误差；在冰云和水云的混合像元中，MODIS卷云反射率的反演可能有一定的误差。

![](images/7ea6b6b807552b40091749a248ae697a9a6d96309fa0ac33c60127161cbbe1a9.jpg)  
图7卷云反射率计算值与观测值对比

Fig7.Reflectance computed by DISORT versus measured by MODIS

图8统计了不同的光学厚度的计算和观测值的平均值，（图中每个值的横坐标对应一定范围t)，发现在不同光学厚度范围内卷云反射率的平均计算值比平均测量值略大，与图7显示的结果相一致，总平均相对误差为 $1 6 . 8 \%$ ，并且随着光学厚度的增大，相对误差减小。当光学厚度在$0 { \sim } 1$ 时，相对误差最大为 $2 0 \%$ ，当光学厚度大于7时，相对误差最小约为 $7 . 8 \%$ 。当光学厚度处于$1 { \sim } 3$ 时，相对误差有一个波动，这是由于个别地区卷云光学厚度虽然较大，但是由于设备自身、以及卷云周围环境等因素使得卷云误判造成测量值很小，进而影响卷云内平均测量值。

![](images/28b652554353edbab7ac3e593f069f7f4df48f572e898fb1ebf3f409199da301.jpg)  
图8不同光学厚度下卷云反射率观测和计算的平均值

Fig8.The observed and calculated mean reflectance of cirrus clouds versus the optical thickness.

为了进一步验证卷云快速算法在不同地区的适用性，我们选取了UTC时间为

12/7/200202:05的中高纬度地区（ $3 8 ^ { \circ } \mathrm { ~ N ~ }$ ，$1 2 8 ^ { \circ } \mathrm { ~ E ~ }$ 附近）进行分析，计算得到该区域的卷云反射率计算值以及观测值。与图7类似，卷云反射率的计算值与观测值变化趋势相同，只是平均相对误差比图7略大为 $1 8 . 5 \%$ 。由于中高纬度地区组成卷云的冰晶粒子形状更为复杂，与低纬度地区卷云LUTs可能会有一定的差异，因此，本算法在高纬度地区使用误差可能会增大。

# 3结论

文中模拟计算了由三种冰晶粒子组成的卷云反射率随各参数的变化，显示卷云反射率随卷云光学厚度的增大而增大，与太阳、观测方位有着复杂的空间几何关系。文中运用的预先建立查找表，结合插值法建立了卷云反射率的快速算法，在快速遥感反演卷云特性参数研究中具有重要应用。利用MOD06中卷云光学性质相关的数据作为输入项，计算得到的卷云反射率和MODIS1.38观测的卷云反射率大致相同，低纬度地区拟合斜率为1.1，平均相对误差为 $1 6 . 8 \%$ ，中高纬度地区平均相对误差为 $1 8 . 5 \%$ 。初步验证了本文基于DISORT建立卷云反射率快速查找表的卷云反射率算法。我们将把该算法扩展到各个波长，应用于卷云的光学特性和微物理参数的反演；同时也有助于研究卷云背景下大气和云的辐射特性。

# 4致谢

感谢 NASA Goddard Earth SciencesDistributed Active Archive Center(GES DAAC)提供的MODIS二级云分类产品数据。

# 参考文献：

[1] Dowling D R,Radke L F.A Summary of the Physical Properties of Cirrus Clouds[J].Journal of Applied Meteorology，1990,29(9):970-978.   
[2] K. N. LIOU. An Introduction To Atmospheric Radiation(SecondEdition)[M].GuoCaili,ZhouShi jian Translated. Bei jing:ChinaMeteorological Press,2004.   
[3] Goldfarb L，Keckhut P,Chanin M， et al.Cirrus

climatological results from lidar measurements at OHP (44°N, $6 ^ { \circ }$ E)[J].Geophysical Research Letters,2001, 28(9) :1687-1690.

[4] Baum B A，Platnick S. Introduction to MODIS cloud products[M]．Springer Berlin Heidelberg，2006:74-91.

[5] Zhao Yanjie,Wei Heli,Chen Xiuhong,et al.Simulation study on the reflectance of cirrus clouds at the wavelength of 1.064 μ m[J].Laser Technology,2008, 32(5):523-526.

赵燕杰，魏合理，陈秀红，等． $1 . 0 6 4 \mu \mathrm { ~ m ~ }$ 波长卷云反射率的模拟研究[J]．激光技术，2008，32(5)：523-526.

[6] Cao Yanan，Wei Heli,Chen Xiuhong，et al.Simulations of the reflectance of cirrus clouds in shortwave spectral region[J].ActaOpticaSinica, 2012, 32(8):19-25.

曹亚楠，魏合理，陈秀红，等．卷云短波反射特性的模拟计算研究[J]．光学学报，2012，32(8)：19-25.

[7] Wei Heli， Chen Xiuhong， Dai Congming.Combined atmospheric radiative transfer(CART)model and its applications [J].Infrared and Laser Engineering,2012,41(12):3360-3366.

魏合理，陈秀红，戴聪明.通用大气辐射传输软件（CART）及其应用[J].红外与激光工程，2012，41(12)：3360-3366.

[8] YangP,Liou KN,Wyser K,et al.Parameterization of thescatteringand absorptionpropertiesof individual ice crystals[J].Journal of Geophysical Research Atmospheres，2000,105(D4) :4699-4718.

[9] ZHAO Yanjie,Wei Heli,Chen Xiuhong，et al．ScatteringProperties of Cirrus Clouds in the Shortwave SpectralRegion[J].Journal of Atmospheric and environmentalOptics，2007，2(3):169-174.赵燕杰,魏合理,陈秀红,等.卷云短波光学特性[J].大气与环境光学学报,2007，2(3):169-174.

[10] Stamnes K，Tsay S C,WiscombeW,et al. Numerically stable algorithm for discrete-ordinate-method radiative transfer in multiple scattering and emitting layered media[J].Applied Optics,1988,27(12) :2502-2509.

[11] HuYX,Wielicki B,LinB,et al.δ-Fit:A fast and accurate treatment of particle scattering phase functions withweighted singular-value decomposition least-squares fitting[J].Journal of Quantitative Spectroscopy & Radiative Transfer, 2000, 65(4):681-690.

[12] Gao B C， Yang P, Han W, et al.An algorithm usingvisible and 1.38-/spl mu/m channels to retrieve cirrus cloud reflectances fromaircraft and satellite data[J].IEEE Transactions on Geoscience & Remote Sensing，2002，40(8):1659-1668.

[13] Nakajima T,King M D. Determination of the optical thickness and effective particle radius of clouds from reflected solar radiation measurements.I Theory[J]．Nature，1991，517(7536):1878-1893.