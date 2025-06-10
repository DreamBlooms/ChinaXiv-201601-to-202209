# WUMa型食双星GMBootis测光研究

杨勇，张燕平，付建宁，苍天启(北京师范大学天文系，北京100875)

摘 要：GM Boo是一个已经被发现超过10年的短周期（约0.36天）相接双星。本研究获得了GM Boo在 2010到 2015年新观测的多波段时序测光数据及其低色散光谱。从光变曲线中提取了19个新的光变极小时刻，并结合历史数据推导出该双星轨道周期增长速率dP/dt $\ l =$ $1 . 0 6 \times 1 0 ^ { - 7 } \mathrm { d \cdot y r ^ { - 1 } }$ 。Wilson-Devinney 程序被用来分析GM Boo 的测光轨道解。得出它是一个典型的W次型的过相接双星系统，其质量比约为 $\tilde { \mathrm { ~ q ~ } ^ { 1 } } \cdot 2 2$ ，相接度约为 $\cdot$ 模型中添加了 2个黑子拟合不对称的光变曲线，说明此系统具有较强的活动性。

关键词：食双星;轨道周期;光变曲线中图分类号：P144文献标识码：A 文章编号：1672-7673

GM Boo(又称 GSC 02016-00830,ROTSE1 J144726.56+224515.0)在 ROSTE 巡天(2000)[1中被证认为是一个食双星系统，并给出轨道周期是 $0 . 3 6 1 1 0 3 0 0 \pm 0 . 0 0 0 0 1 7 8 7$ 天以及V星等是12.230 等·随后，Blattler和Diethelm $( 2 0 0 1 ) ^ { \textcircled { 1 } }$ 对包括GMBoo在内的一些双星进行了CCD 测光观测·他们获得了GMBoo的光变曲线，并且第一次给出了GMBoo的线性历元公式：

$$
M i n . I = H J D 2 , 4 5 2 , 0 0 1 . 4 0 3 2 + ( 0 ^ { d } . 3 6 1 1 1 2 ) \times E
$$

文[2]利用ROTSE-I数据联合2MASS的] $I , H , K$ 和近红外数据从ROTSE-I中证认出1022颗明亮的密近双星系统，并且给出了GMBoo的 $J - H$ 色指数 $0 . 1 9 2 \cdot H - K$ 色指数0.057，轨道周期0.361112天以及日心距 $5 8 6 \pm 7 p c$ 。文[3]认为 GM Boo 是一个W Ursae Majoris 类型的密近双星，同时给出轨道周期是0.36108天。

因为到自前为止，还没有任何对这颗食双星进一步详细的研究。所以，从2010年到2015年，对这颗食双星进行了V和 $R$ 两个波段的CCD测光观测，目的是分析GMBoo的轨道周期变化并得到它的测光轨道解。

# 1观测和数据处理

从2010年5月16日到2015年2月3日，利用3个望远镜对GMBoo进行了共计16 个夜晚的测光观测·其中，5个夜晚的数据是利用国家天文台兴隆观测站 $6 0 \mathsf { c m }$ 反射望远镜观测·该望远镜主焦点焦比是 $F / 4 . 2 3 \$ ，有效视场是 $1 8 ^ { \prime } \times 1 8 ^ { \prime }$ ，位于主焦点的 CCD 像素是 $1 0 2 4 \times 1 0 2 4$ 和像元分辨率是 $1 . 0 5 6 ^ { \prime \prime } / p i x e l \circ 1 0$ 个夜晚的数据是利用云南天文台的$6 0 c m$ 反射望远镜观测·该望远镜观测采用卡塞格林焦点，其焦比是 $F / 1 2 . 5$ ，有效视场是$\cdot$ CCD 型号是Andor/sDW 436·CCD 像素和像元分辨率分别是 $2 0 4 8 \times$ 2048和 $0 . 3 7 ^ { \prime \prime }$ /pixel·

仅有一个晚上数据是利用位于美国新墨西哥州TzecMaun望远镜远程观测·该望远镜是一个口径16英寸的反射望远镜，它的有效视场是 $2 6 ^ { \prime } . 1 \times 1 7 ^ { \prime }$ .4，焦比 $_ { \cdot F / 9 } \cdot \mathsf { C C D }$ 型号是SBIGSTL-6303，相应的像素和像元分辨率分别是 $3 0 7 2 \times 2 0 4 8$ 和 $0 . 5 1 ^ { \prime \prime } / p i x e l$ ·测光观测日志见表1·图1展示了兴隆60cm望远镜拍摄的一幅GMBoo 的图像·选择UCAC4564-052034作为比较星和TYC2016-1086-1作为校验星·表2列出了它们的坐标和V星等。利用IRAF程序

![](images/e91e7e66544b2e9261f369ded59e62e25f2f269dacb0bbe42cb8f834ca8c3540.jpg)  
图1兴隆 $6 0 \mathrm { c m }$ 望远镜观测的一幅GM Boo 的CCD 图像Fig.1 A CCD image of GM Boo observed with the XL 60-cm telescope

对该

双星的测光数据进行了处理，主要过程包括减本底，除平场和孔径测光。

表1GM Boo 测光观测 Table 1 Photometric observations of GM Boo   

<html><body><table><tr><td>日期</td><td>望远镜</td><td>滤过片 帧数</td></tr><tr><td>2010-05-16</td><td>TM16-in</td><td>VR 139</td></tr><tr><td>2011-05-08</td><td>YN60-cm</td><td>VR 228</td></tr><tr><td>2011-05-09</td><td>YN60-cm</td><td>VR 254</td></tr><tr><td>2011-05-18</td><td>XL60-cm</td><td>VR 137</td></tr><tr><td>2011-05-21</td><td>XL60-cm</td><td>VR 260</td></tr><tr><td>2011-05-22</td><td>XL60-cm</td><td>VR 330</td></tr><tr><td>2012-02-07</td><td>YN60-cm</td><td>VR 152</td></tr><tr><td>2013-01-23</td><td>YN60-cm</td><td>VR 102</td></tr><tr><td>2013-01-31</td><td>YN60-cm</td><td>VR 112</td></tr><tr><td>2013-05-05</td><td>XL60-cm</td><td>VR 155</td></tr><tr><td>2014-02-17</td><td>XL60-cm</td><td>VR 34</td></tr><tr><td>2015-01-25</td><td>YN60-cm</td><td>VR 352</td></tr><tr><td>2015-01-28</td><td>YN60-cm</td><td>VR 187</td></tr><tr><td>2015-01-29</td><td>YN60-cm</td><td>VR 420</td></tr><tr><td>2015-02-02</td><td>YN60-cm</td><td>VR 213</td></tr></table></body></html>

2012年5月14日，使用位于兴隆站的 $2 . 1 6 \mathrm { - } \mathsf { m }$ 望远镜获得了GMBoo的低色散光谱·该光谱是用 BFOSC低色散光谱仪拍摄，其光栅为G7，狭缝宽度为1.8"，线色散为95A/mm，中心波长为530nm，波长范围为380-680nm·利用IRAF程序对原始光谱数据进行了处理，得到该双星低分辨率的光谱（见图2）。与Pickles光谱流量库[4进行对比·GMBoo 的光谱类型初步被证认为是 $F 3 V - F 5 V$ ，温度范围约为 $6 8 0 0 \sim 7 0 0 0 K$ 。

表2目标星、比较星和校验星的坐标和星等 Table 2Coordinates and magnitudes of the object， the check， and the comparison star   

<html><body><table><tr><td colspan="4"></td><td>V星等</td></tr><tr><td></td><td>名称</td><td>赤经(J2000)</td><td>赤纬(J2000)</td><td>/mag</td></tr><tr><td>目标星</td><td>GM Boo</td><td>14 47 26.520</td><td>+22 4514.49</td><td>11.89</td></tr><tr><td>比较星</td><td>UCAC4564-052034</td><td>144718.607</td><td>+22 43 53.27</td><td>12.34</td></tr><tr><td>校验星</td><td>TYC 2016-1086-1</td><td>14 47 20.948</td><td>+22 47 40.07</td><td>11.96</td></tr></table></body></html>

![](images/dd164dab952c6e39211689292fb37200cc59d8f492653363643f42375436dc0a.jpg)  
图2兴隆2.16m 望远镜观测的GMBoo光谱 Fig.2 The spectrum of GM Boo observed with XL $2 . 1 6 \mathrm { - m }$ telescope

# 2轨道周期变化

利用较差测光，提取了GMBoo所有的光变曲线·同时采用最小二乘法对光变极小值附近进行二次拟合，确定了19个新的极小值时刻·为了研究轨道周期的变化，从历史数据中收集了43个极小值时刻·所有极小值时刻是被列在表2·利用最小二乘法得到了GMBoo新的线性和二次历元公式：

$$
I = H J D 2 , 4 5 5 , 3 3 2 . 9 0 0 7 ( 3 ) + 0 ^ { d } . 3 6 1 1 1 8 6 3 ( 7 ) \times E
$$

$$
M i n . I = H J D 2 , 4 5 5 , 3 3 2 . 9 0 0 5 ( 2 ) + 0 ^ { d } . 3 6 1 1 1 9 3 ( 1 ) \times E + 1 ^ { d } . 0 5 ( 2 ) \times 1 0 ^ { - 1 0 } \times E ^ { 2 }
$$

因此，根据新的线性和二次历元公式推导该双星的O-C值（观测和计算得到的极小值时刻之差），列在表3·利用表3中的列出的 $( { \mathsf { O } } { - } { \mathsf { C } } ) _ { 1 }$ 值和圈数E·描绘了GMBoo 的O-C图（见图3），目的是分析该双星长期的轨道周期变化·图3中，红色实心圆点代表本文的数据，黑色空心圆代表文献中的数据。通过对图3中所有数据点进行二次拟合，得到一个向上的抛物线，表明GMBoo的轨道周期是正在增加·根据二次历元公式的二次项得到该双星轨道周期增加的速率是 $d P / d E = 1 . 0 5 \times 1 0 ^ { - 1 0 } d \cdot c y c l e ^ { - 1 }$ 或 $d P / d t = 1 . 0 6 \times 1 0 ^ { - 7 } d \cdot y r ^ { - 1 }$ 。相接双星轨道周期增加表明较小质量子星正在向较大质量子星进行物质转移[5]。

![](images/49d2c6e42b95a4933b9cea713762385a9cc94d81d35ca4092acc5cda720834e9.jpg)  
图 3GM Boo的0-C图。实点代表本文的数据，空心圆点代表文献中的数据。实线是对全部数据的二次拟合。 Fig3O-C diagram of GM Boo.The solid points represent our data and the open circles represent the data from the literature. The solid curve shows the quadratic fitting.

# 3测光数据的轨道解

使用2015 版的Wilson-Devinney（W-D）程序[6-9]获得 GM Boo 测光数据的轨道解。用于解轨的测光数据是来自2011年兴隆 $6 0 \mathrm { - } \mathsf { c m }$ 望远镜观测的3天数据（见表1），因为这3天数据质量相对较高·对这3天测光数据进行相位合并得到在V和R波段具有完整相位覆盖的光变曲线（见图4）。

![](images/90cefd2b6451011b6450f026e554c4cf65331ffdbd6579691243847746331e96.jpg)  
图4GMBoo 的光变曲线。空心圆点代表观测数据，实线是理论光变曲线。

Fig.4Light curves of GM Boo.The open circles represent observational data and the solid lines show theoretical light curves.

GM Boo 是被分类为WUMa类型的食双星[4]。因此·使用W-D 程序的Mode 3（overcontactbinary not in thermal contact）寻找轨道初解·根据 GM Boo 的光谱型是$F 3 V - F 5 V$ ，假设主星温度 $T _ { 1 } = 6 9 0 0 K$ ，取两子星的重力昏暗系数 $g _ { 1 } = g _ { 2 } = 0 . 3 2 ^ { [ 1 0 ] }$ ，两子星的热反照率 $A _ { 1 } = A _ { 2 } = 0 . 5 0 ^ { [ 1 1 ] }$ ，两子星的热临边昏暗系数和各个波段的临边昏暗系数从文[12]获得（见表3）·以上参量在解轨过程中固定不变·在W-D解轨过程中可以被调整的自由参量包括轨道倾角 $i$ ，次星温度 $T _ { 2 }$ ，两子星的表面势能 $\Omega _ { 1 }$ 和 $\Omega _ { 2 }$ ，两子星的质量比 $q =$ $m _ { 2 } / m _ { 1 }$ ，以及主星VR波段的相对单色光度·

由于到目前为止没有任何关于该双星质量比 $( q = m _ { 2 } / m _ { 1 } )$ 的信息，因此执行一个 $\boldsymbol { q }$ -search的过程寻找最佳质量比· $q$ -search的具体过程是选择一系列0.3到2之间的 $q$ 值，间隔步长0.1，然后对每个 $q$ 值分别执行W-D程序解轨，调整其它自由参量直到它们的校正值小于标准误差以及拟合光变曲线和观测到的曲线之间残差 $\sigma$ 达到最小值，最后对每个 $\boldsymbol { q }$ 值都得到一个相应的残差 $\sigma$ ·图5描绘了残差 $\sigma$ 与质量比 $q$ 之间的关系，在 $q = 1 . 2$ 找到残差 $\sigma$ 的最小值·因此，在 $q = 1 . 2$ 附近寻找最佳的质量比，放开 $q$ 值进行微调，最终确定最佳的质量比 $q = 1 . 2 2$ ·最终的解轨结果揭示其质量小但温度更高的子星在主极小时被质量大的子星遮掩·因此，GM Boo是一个典型的W次型过相接双星系统[13]。

![](images/44cd7164013f91f3050ae9ba46726e38a74e0c5e537793af3a1fcc90babe046d.jpg)  
图5残差 $\sigma { \boldsymbol { v } } { \boldsymbol { s } }$ 质量比 $q = m _ { 2 } / m _ { 1 }$ Fig.5The residual $\sigma$ versus mass ratio $q = m _ { 2 } / m _ { 1 }$

从图4光变曲线可以发现位于相位0.25处的双星主极大光度比相位0.75处的次极大更暗·即存在 $\bigcirc ^ { \prime }$ Connel效应②。该效应代表在双星表面可能存在黑子或者亮斑·此处假设在大质量子星表面存在两颗黑子，然后调整黑子的经度、纬度、角半径和温度系数拟合光变极大值·最终得到最佳的测光数据的轨道解，列在表4·图4实线描绘了通过轨道解拟合得到的V和R波段理论光变曲线·GMBoo的几何结构如图6。

![](images/41124dc13866aaff4c2d81a2536701e289254b56a630c8b261da2f8cac1f5ead.jpg)  
图6相位0.0、0.25、0.5和0.75处GMBoo的几何结构 Fig.6The geometry configurations of GM Boo at the phase 0.0,0.25,0.5 and 0.75,respectively

# 4总结与讨论

通过CCD测光观测，获得了GMBoo19个新的光变极小时刻，并推导出它的线性和二次历元公式·另外，通过与 Blattler和 Diethelm (2001)的光变曲线和历元公式进行对比发现，在本文的观测中，GMBoo的主极小和次极小时刻发生了反转，即光变主极小的相位对应Blattler和Diethelm光变次极小相位·类似的现象同样出现在Kepler卫星观测的部分食双星中[14]，该现象可能是由双星表面存在的黑子转移造成的。

在O-C图上展示了一个开口向上的抛物线，表明这十几年来GMBoo 的轨道周期一直在增加，相应的周期增加速率是 $d P / d E = 1 . 0 5 \times 1 0 ^ { - 1 0 } d \cdot c y c l e ^ { - 1 }$ 或 $d P / d t = 1 . 0 6 \times 1 0 ^ { - 7 } d$ ：$y r ^ { - 1 }$ ，这与近年来对相接双星周期变化研究的文[15-16]给出的结果相符·认为该双星周期增加可能是由于小质量伴星到大质量伴星之间存在物质转移，但是也不能完全排除第三体的存在，还需进一步的测光观测。

使用W-D 程序获得了GMBoo 的测光轨道解·并且因此确认了GMBoo 是一个典型的W 次型过相接双星系统·GMBoo 两子星的表面势能是 $\_$ ，利用f $\cdot$ $\_$ ，得出其填充因子 $\mathsf { f } = 1 1 . 1 1 ( \pm 0 . 3 9 ) \%$ ，即两子星相接度约为 $\cdot$ 。根据 $G M B 0 0$ 光变曲线极大值的不对称，表明存在 $\bigcirc ^ { \prime }$ Connel效应，利用W-D解轨得到在大质量伴星表面存在两个黑子·黑子的存在表明其表面存在活跃的磁场活动·说明作为F型的恒星，与较晚型的恒星（ $G \cdot K$ 型）一样，也存在较强的表面磁活动。

致谢： JNF acknowledges the support from the National Natural Science Foundation of China (NSFC) through the grant 11673003 and the National Basic Research Program of China(973 Program 2014CB845700 and 2013CB834900)． The authors acknowledge the support of the staff of the Xinglong 2.16m telescope. This work was partially Supported by the Open Project Program of the Key Laboratory of Optical Astronomy， National Astronomical Observatories， Chinese Academy of Sciences.

# 参考文献：

[1] Akerlof C, Amrose S, Balsano R, et al. Rotse all-sky surveys for variable stars. I. test fields[J]. The Astronomical Journal, 2OOo, 119(4): 1901-1913.   
[2] Gettel S J, Geske M T,McKay T A. A catalog of 1022 bright contact binary stars[J]. The Astronomical Journal, 2006, 131(1): 621-632.   
[3] Hoffman D I, Harrison T E,McNamara B J. Automated variable star classification using the northern sky variability survey[J]. The Astronomical Journal, 2009, 138(2): 466-477.   
[4] Pickles A J. A stellar spectral flux library: 1150-25000 A[J].   
Publications of the Astronomical Society of the Pacific,1998, 110(749): 863-878.   
[5] Hoffman D I, Harrison T E,McNamara B J, et al. The case for third bodies as the cause of period changes in selected Algol systems[J]. The Astronomical Journal, 2006, 132(6): 2260-2267.   
[6] Wilson R E, Devinney E J. Realization of accurate close-binary light curves: application to MR Cygni[J]. The Astrophysical Journal, 1971,166: 605-619.   
[7]Wilson R E. Accuracy and efficiency in the binary star reflection   
effect[J]. The Astrophysical Journal, 1990, 356: 613-622.   
[8] Wilson R E. Binary star light-curve models[J]. Publications of the Astronomical Society of the Pacific, 1994, 106(703): 921-941.   
[9] Wilson R E, Van Hamme W. Unification of binary star ephemeris solutions[J]. The Astrophysical Journal, 2013, 780(2): 151-167.   
[10] Lucy L B. Gravity-darkening for stars with convective envelopes[J]. Zeitschrift fur Astrophysik, 1967, 65: 89-92.   
[11] Rucinski S M. The W UMa-type systems as contact binaries. I. two methods of geometrical elements determination. degree of contact[J]. Acta Astronomica, 1973, 23: 79-120.   
[12] Van Hamme W. New limb-darkening coefficients for modeling binary star light curves[J]. The Astronomical Journal, 1993, 106: 2096-2117. [13] Binnendijk L. The orbital elements of W Ursae Majoris systems[J]. vistas in Astron0my, 1970, 12: 217-256.   
[14] Tran K, Levine A, Rappaport S, et al. The anticorrelated nature of th primary and secondary eclipse timing variations for the kepler contac binaries[J]. The Astrophysical Journal, 2013, 774(1): 81-94.   
[15] Qian S B, Li K, Liao W P, et al. The first photometric investigation c the neglected W-UMa-type binary star UZ CMi[J]. The Astronomic& Journal, 2013, 145(4):91-96.

[16] Qian S B, Liu N P, Liao W P, et al. First photometric investigation of the newly discovered W UMa-type binary star MR Com[J]. The Astronomical Journal, 2013, 146(146):38-44.

# Photometric study of WUMatype eclipsing binary GM Bootis

Yang Yong， Zhang Yanping，Fu Jianning，Cang Tianqi (Department of Astronomy，Bei jing Normal University， Beijing 100875) Abstract:GM Boo is a short period ( ${ \widetilde { \mathbf { \Gamma } } } 0 . 3 6$ days) contact binary system discovered for over 10 years. In this work， new multi-color photometric light curves from 2010 to 2015 and low-resolution spectra of GM Boo are obtained. We extracted 19 new eclipse timings of GM Boofrom the light curves， deriving a longterm increasing rate of the orbital period $-$ combined with historical data. Photometric solution is derived with the Wilson-Devinney Code, which shows that GM Boo is a typical W-type contact binary with mass ratio of $\cdot$ and contact degree of $\cdot$ . Two cool spots are assumed in the model in order to fit the asymmetrical light curves， which indicated that GM Boo is an active system.

Key words:eclipsing binary; orbital period; light curves

表3GMBoo的极小值时刻和0-C值  

<html><body><table><tr><td colspan="6">Table 3Minimum times and O-C residuals of GM Boo</td></tr><tr><td>HJD(2,400,000+)</td><td>Min.</td><td>E</td><td>(0-C)1</td><td>(0-C) 2</td><td>参考文献</td></tr><tr><td>51996.5287</td><td>I</td><td>-9239</td><td>0.0092</td><td>0.0004</td><td>BBS 125</td></tr><tr><td>52001.4034</td><td>II</td><td>-9225.5</td><td>0.0088</td><td>0.0001</td><td>BBS 125</td></tr><tr><td>52001.5836</td><td>I</td><td>-9225</td><td>0.0084</td><td>-0.0003</td><td>BBS 125</td></tr><tr><td>52022.3507</td><td>II</td><td>-9167.5</td><td>0.0112</td><td>0.0026</td><td>BBS 125</td></tr><tr><td>52022.5291</td><td>I</td><td>-9167</td><td>0.0090</td><td>0.0004</td><td>BBS 125</td></tr><tr><td>52033.3584</td><td>I</td><td>-9137</td><td>0.0047</td><td>-0.0038</td><td>BBS 125</td></tr><tr><td>52041.4856</td><td>II</td><td>-9114.5</td><td>0.0068</td><td>-0.0018</td><td>BBS 125</td></tr><tr><td>52367.3979</td><td>I</td><td>-8212</td><td>0.0089</td><td>0.0020</td><td>BBS 128</td></tr><tr><td>52763.3562</td><td>II</td><td>-7115.5</td><td>-0.0001</td><td>-0.0052</td><td>BBS 129</td></tr><tr><td>53081.5055</td><td>II</td><td>-6234.5</td><td>0.0031</td><td>-0.0008</td><td>BBS 130</td></tr><tr><td>53445.5102</td><td>II</td><td>-5226.5</td><td>-0.0005</td><td>-0.0031</td><td>IBVS 5653</td></tr><tr><td>53815.4769</td><td>I</td><td>-4202</td><td>-0.0005</td><td>-0.0022</td><td>BAVM 186</td></tr><tr><td>53900.8800</td><td>II</td><td>-3965.5</td><td>-0.0021</td><td>-0.0036</td><td>OEJV 0162</td></tr><tr><td>53936.4531</td><td>I</td><td>-3867</td><td>0.0007</td><td>-0.0006</td><td>IBVS 5781</td></tr><tr><td>54174. 4301</td><td>I</td><td>-3208</td><td>0.0001</td><td>-0.0008</td><td>IBVS 5781</td></tr><tr><td>54186.5265</td><td>II</td><td>-3174. 5</td><td>-0.0010</td><td>-0.0018</td><td>BAVM186</td></tr><tr><td>54201.5136</td><td>I</td><td>-3133</td><td>-0.0003</td><td>-0.0012</td><td>BAVM 186</td></tr><tr><td>54213.4318</td><td>I</td><td>-3100</td><td>0.0009</td><td>0.0001</td><td>BAVM 186</td></tr><tr><td>54570.3954</td><td>II</td><td>-2111. 5</td><td>-0.0019</td><td>-0.0022</td><td>BAVM 201</td></tr><tr><td>54570.5776</td><td>I</td><td>-2111</td><td>-0.0003</td><td>-0.0005</td><td>BAVM 201</td></tr><tr><td>54631.0653</td><td>II</td><td>-1943.5</td><td>0.0000</td><td>-0.0002</td><td>VSB 48</td></tr><tr><td>54888.9036</td><td>II</td><td>-1229.5</td><td>-0.0009</td><td>-0.0009</td><td>IBVS 5929</td></tr><tr><td>54933.5024</td><td>I</td><td>-1106</td><td>-0.0004</td><td>-0.0003</td><td>BAVM 209</td></tr><tr><td>54961.8511</td><td>II</td><td>-1027.5</td><td>0.0005</td><td>0.0006</td><td>IBVS 5894</td></tr><tr><td>54968.5305</td><td>I</td><td>-1009</td><td>-0.0008</td><td>-0.0007</td><td>BAVM 209</td></tr><tr><td>55015.4787</td><td>I</td><td>-879</td><td>0.0019</td><td>0.0020</td><td>IBVS 5920</td></tr><tr><td>55315.3853</td><td>II</td><td>-48.5</td><td>-0.0011</td><td>-0.0009</td><td>BAVM 214</td></tr><tr><td>55315.5660</td><td>I</td><td>-48</td><td>-0.0010</td><td>-0.0008</td><td>BAVM 214</td></tr></table></body></html>

<html><body><table><tr><td>55332.7195</td><td>II</td><td>-0.5</td><td>-0.0006</td><td>-0.0004</td><td>This paper</td><td></td></tr><tr><td>55332.9005</td><td>I</td><td>0</td><td>-0.0002</td><td>0.0000</td><td>This paper</td><td></td></tr><tr><td>55398.4414</td><td>II</td><td>181.5</td><td>-0.0025</td><td>-0.0023</td><td></td><td>IBVS 5960</td></tr><tr><td>55625.5890</td><td>II</td><td>810.5</td><td>0.0011</td><td>0.0012</td><td></td><td>OEJV0160</td></tr><tr><td>55644.9063</td><td>I</td><td>864</td><td>-0.0015</td><td>-0.0014</td><td></td><td>IBVS 5992</td></tr><tr><td>55649.6020</td><td>I</td><td>877</td><td>-0.0004</td><td>-0.0003</td><td></td><td>OEJV 0160</td></tr><tr><td>55654. 4777</td><td>I</td><td>890.5</td><td>0.0003</td><td>0.0004</td><td></td><td>BAVM 220</td></tr><tr><td>55671. 4512</td><td>II</td><td>937.5</td><td>0.0012</td><td>0.0013</td><td></td><td>BAVM 220</td></tr><tr><td>55672.5338</td><td>II</td><td>940.5</td><td>0.0004</td><td>0.0005</td><td></td><td>OEJV 0160</td></tr><tr><td>55690.0428</td><td>I</td><td>989</td><td>-0.0049</td><td>-0.0048</td><td></td><td>This paper</td></tr><tr><td>55690.2275</td><td>II</td><td>989.5</td><td>-0.0007</td><td>-0.0007</td><td></td><td>This paper</td></tr><tr><td>55695.8251</td><td>I</td><td>1005</td><td>-0.0005</td><td>-0.0004</td><td></td><td>IBVS 5992</td></tr><tr><td>55700.1582</td><td>I</td><td>1017</td><td>-0.0008</td><td>-0.0007</td><td></td><td>This paper</td></tr><tr><td>55703.0484</td><td>I</td><td>1025</td><td>0.0004</td><td>0.0005</td><td></td><td>This paper</td></tr><tr><td>55703.2292</td><td>II</td><td>1025.5</td><td>0.0007</td><td>0.0007</td><td></td><td>This paper</td></tr><tr><td>55704.1316</td><td>I</td><td>1028</td><td>0.0003</td><td>0.0003</td><td></td><td>This paper</td></tr><tr><td>55704.3134</td><td>II</td><td>1028.5</td><td>0.0015</td><td>0.0016</td><td></td><td>This paper</td></tr><tr><td>55965.3968</td><td>II</td><td>1751. 5</td><td>-0.0044</td><td>-0.0045</td><td></td><td>This paper</td></tr><tr><td>56008.5570</td><td>I</td><td>1871</td><td>0.0021</td><td>0.0020</td><td></td><td>OEJV 0160</td></tr><tr><td>56009.4585</td><td>II</td><td>1873.5</td><td>0.0008</td><td>0.0006</td><td></td><td>BAVM 228</td></tr><tr><td>56009.6398</td><td>I</td><td>1874</td><td>0.0015</td><td>0.0014</td><td></td><td>BAVM 228</td></tr><tr><td>56015.4167</td><td>I</td><td>1890</td><td>0.0005</td><td>0.0003</td><td></td><td>BAVM 228</td></tr><tr><td>56015.5986</td><td>II</td><td>1890.5</td><td>0.0019</td><td>0.0017</td><td></td><td>BAVM 228</td></tr><tr><td>56316.4089</td><td>II</td><td>2723.5</td><td>-0.0002</td><td>-0.0008</td><td></td><td>This paper</td></tr><tr><td>56324.3527</td><td>II</td><td>2745.5</td><td>-0.0010</td><td>-0.0016</td><td></td><td>This paper</td></tr><tr><td>56355.5875</td><td>I</td><td>2832</td><td>-0.0031</td><td>-0.0037</td><td></td><td>OEJV 0160</td></tr><tr><td>56418.0657</td><td>I</td><td>3005</td><td>0.0015</td><td>0.0008</td><td></td><td>This paper</td></tr><tr><td>56418.2485</td><td>II</td><td>3005.5</td><td>0.0037</td><td>0.0030</td><td></td><td>This paper</td></tr><tr><td>57048.4044</td><td>II</td><td>4750.5</td><td>0.0065</td><td>0.0043</td><td></td><td>This paper</td></tr><tr><td>57051.2930</td><td>II</td><td>4758.5</td><td>0.0061</td><td>0.0039</td><td></td><td>This paper</td></tr><tr><td>57052.3763</td><td>II</td><td>4761. 5</td><td>0.0061</td><td>0.0039</td><td></td><td>This paper</td></tr><tr><td>57056.3468</td><td>II</td><td>4772. 5</td><td>0.0042</td><td>0.0020</td><td></td><td>This paper</td></tr><tr><td>57057.4284</td><td>II</td><td>4775.5</td><td>0.0025</td><td>0.0003</td><td></td><td>This paper</td></tr><tr><td>57186.7186</td><td>II</td><td>5133.5</td><td>0.0120</td><td>0.0094</td><td></td><td>JAAVSO 44-1</td></tr></table></body></html>

1 BBS $\ c =$ BuletinderBedeckungsveraenderlichen-BeobachterderSchweizerischenAstronomischen Geselschaf.; BAVM $\ c =$ BAV- Mitteilungen (Berliner/Bundesdeutsche Arbeitsgemeinschaft fur Veranderliche Sterne); IBVS $\mathbf { \sigma } = \mathbf { \sigma }$ Information Bulletin on Variable Stars; OEJV $\mathbf { \bar { \rho } } = \mathbf { \bar { \rho } }$ Open European Journal on Variable Starst $\cdot \mathsf { V S B } = \mathsf { 1 }$ Variable Star Bulletin (Japan); JAAVSO $\ O =$ Journal of the American Association of Variable Star Observers.

表4GM Boo 的轨道解Table 4 Orbital solution of GM Boc  

<html><body><table><tr><td>参数</td><td>最佳拟合值</td><td>误差</td></tr><tr><td>q = m2/m1</td><td>1.220</td><td>±0.002</td></tr><tr><td>T1 (K)</td><td>6900a</td><td></td></tr><tr><td>T2(K)</td><td>6725</td><td>±11</td></tr><tr><td>91 = 92</td><td>0.32 a</td><td></td></tr><tr><td>i()</td><td>64.452</td><td>±0.072</td></tr><tr><td>A1 = A2</td><td>0.50</td><td></td></tr><tr><td>Ω = Ω1</td><td>4.0288</td><td>±0.0025</td></tr><tr><td>X1 = X2(bolo)</td><td>0.172 a</td><td></td></tr><tr><td>Y = Y2(bolo)</td><td>0.553 a</td><td></td></tr><tr><td>x1 = x2(V)</td><td>0.061 a</td><td></td></tr><tr><td>x1 = x(R)</td><td>0.033 a</td><td></td></tr><tr><td>y1 = y2(V)</td><td>0.726 a</td><td></td></tr><tr><td>y1 =y2(R)</td><td>0.725 a</td><td></td></tr><tr><td>L1/(L+L2) (V)</td><td>0.485</td><td>±0.002</td></tr></table></body></html>

<html><body><table><tr><td>L1/(L1+ L2)(R)</td><td>0.477</td><td>±0.001</td></tr><tr><td>r1(pole)</td><td>0.3477</td><td>±0.0002</td></tr><tr><td>r1(side)</td><td>0.3657</td><td>±0.0003</td></tr><tr><td>r1(back)</td><td>0.4019</td><td>±0.0005</td></tr><tr><td>r2(pole)</td><td>0.3811</td><td>±0.0004</td></tr><tr><td>r2(side)</td><td>0.4029</td><td>±0.0005</td></tr><tr><td>r2(back)</td><td>0.4371</td><td>±0.0008</td></tr><tr><td>Spot1 latitude(rad)</td><td>1.4835</td><td></td></tr><tr><td>Spot1 longitude(rad)</td><td>4.7124</td><td></td></tr><tr><td>Spot1 radius(rad)</td><td>0.1745</td><td></td></tr><tr><td>Spot1 temp factor</td><td>0.9</td><td></td></tr><tr><td>Spot2 latitude(rad)</td><td>1.2217</td><td></td></tr><tr><td>Spot2 longitude(rad)</td><td>1.3962</td><td></td></tr><tr><td>Spot2 radius(rad)</td><td>0.349</td><td></td></tr><tr><td>Spot2 temp factor</td><td>0.93</td><td></td></tr><tr><td>f</td><td>0.1111</td><td>±0.0039</td></tr><tr><td>(0-C)²0.013</td><td></td><td></td></tr></table></body></html>

Note.‘Assumed