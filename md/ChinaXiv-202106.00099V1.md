# 吉林280mm全天区可转动光电阵测光精度评估研究

牛炳力1²，刘承志‘，李振伟¹，康喆‘

(1.中国科学院国家天文台长春人造卫星观测站，吉林 长春 130117；2.中国科学院大学，北京100049)

摘要：位于吉林天文观测基地的280mm全天区可转动光电阵是一台用于空间碎片巡天观测的设备，为了研究该设备光度测量性能，评估其测光精度，选择M67疏散星团这一测光定标区中的测光标准星进行观测。首先，在IRAF中对观测图像进行预处理，之后进行较差测光。接着，提取测光数据并将整晚观测数据进行最小二乘直线拟合，拟合结果给出了主消光系数及相应的系统转换系数，并得到仪器星等至标准星等的转换公式。最后，利用计算得到的均方根误差对该设备的测光精度进行大致的评估。计算结果表明在标准测光夜测量亮度亮于13.8等的星时， $2 8 0 \mathsf { m m }$ 全天区可转动光电阵的测光精度可达0.13星等。同时将观测图像与UCAC2星表匹对识别，利用背景恒星中的UCAC2标准星做外符精度的校验，结果与前者基本相同。本设备的测光精度基本满足空间碎片巡天观测的要求。

关键词：测光精度；巡天观测；标准星；转换公式；UCAC2星表中图分类号：P111.2;P141.2 文献标识码：A 文章编号：

# 1.引言

吉林 280mm全天区可转动光电阵属于中国科学院国家天文台长春人造卫星观测站，坐落于吉林省吉林市天文观测基地。针对一台观测设备在同一时间只能对单一目标进行跟踪观测的模式非常限制对空间目标的编目能力，于是大视场、多目标的光电望远镜阵列观测模式应运而生。目前国际上大天区巡天观测设备越来越多，通过光学巡天观测不仅可以提高观测效率还可以获得更多的空间目标参数,因此这类设备的应用价值极大[I]。该光电阵由四台 $2 8 0 \mathrm { m m }$ 透射式光学望远镜及两台T型架结构赤道仪组成，通过实际检测得到该设备的指向精度在赤经和赤纬两个方向上各优于 ${ \mathfrak { g } } ^ { \prime \prime }$ ，在跟踪测量精度方面赤经方向上的平均误差为 $0 . 9 ^ { \prime \prime }$ ，赤纬方向上的平均误差为1"。每台望远镜有效通光口径为 $2 8 0 \mathrm { m m } \pm 2 \mathrm { m m }$ 并装备有科学级CMOS相机，像素为 $4 0 9 6 \times 4 0 9 6$ ，像元尺寸为 $9 \mu \mathrm { \ m } \times 9 \mu \mathrm { \ m }$ ，量子效率不小于 $7 0 \%$ 。四台望远镜的各项设计参数相同，在测光性能方面与单台望远镜基本一致，不同之处在于观测的天区范围得到极大提升。虽然在装调上存在难以避免的机械误差，但是通过同一终端进行控制，可以保证望远镜之间的协调一致。本设备的观测视场可覆盖160平方度的天区，在19 等天光观测条件下可探测到亮于16.5星等的目标。

随着空间碎片的日益增加，在轨航天器的安全运行受到严重威胁，因此需要通过观测获取空间碎片的位置及轨道信息[2]，从而进行碎片碰撞预警、航天器有效规避以及碎片编目等工作。中高轨空间碎片的光学观测在目标探测、目标跟踪、目标识别等领域具有广阔的前景，利用地基望远镜对空间碎片进行较长弧段的连续测光观测，可以获取目标空间碎片的光度变化和位置变化特征，进而对它的形状、尺寸及运行姿态等进行研究[3]。本设备实现了可动盲扫式观测，降低了观测人员的劳动量，可对大批量空间目标进行捕获，提升了空间目标的编目定轨能力。280mm全大区可转动光电阵的主要功能是空间碎片的巡大观测，设计谱线为$6 5 0 \mathrm { n m }$ ，在 $5 0 0 \mathrm { n m } - 8 0 0 \mathrm { n m }$ 复消色差，为了确保该设备探测空间暗弱目标的能力，并未安装滤光片。因此对该设备在可见光波段进行测光精度评估是很有意义的。本文选取M67疏散星团作为测光定标区，通过对星团中的测光标准星进行观测来测定主消光系数，并研究和确定仪器星等系统与标准星等系统之间的转换关系，将观测得到的仪器星等归算到大气外标准系统下的仪器星等并与标准星等做对比，计算均方根误差进而对本设备的测光精度进行评估。

# 2.观测及数据处理

280mm光电阵目前采用的观测模式为短曝光巡天观测模式，即根据预报指向特定的天区进行拍摄，且观测对象大多集中于中高轨及地球同步轨道的空间目标，因此本设备观测空间目标与观测恒星时的各项参数基本相同。通常地基望远镜测光系统的性能研究都是选用Landolt 标准星作为观测对象，而对于几十厘米口径望远镜来说，由于视场较大且视场中背景恒星众多，因此并不适用于观测单一目标恒星，同时空间碎片的位置及运动姿态不断变化，其光度信息时刻在改变，不能作为标定测光精度的观测对象。基于上述特性本文选取疏散星团作为观测对象，梅西耶67（也称为M67或 NGC2682，后文均用M67代称）是位于巨蟹座的一个疏散星团，大约有 500 颗成员，星场并不密集且亮度集中在10-11等，是理想的测光定标区。我们的测光工作就在这个星团中进行，所采用的测光标准星表由美国变星观测者协会（AAVSO）提供，选取其中的10颗标准星进行测光，如表1所示，同时该网站也提供M67疏散星团中变星的查询，这里不再赘述。

在2020年12月6日、12月7日、12月8日这三日分别对选取的标准星进行整夜观测，这几个观测夜的天气都较稳定。从M67由中天下落至地平高度 ${ 6 0 } ^ { \circ }$ 时开始拍摄，此时月光对测光几乎无影响，每隔0.1大气质量拍摄10张图像，每张图像的曝光时长为2s,直至M67星团降落至地平高度 $3 0 ^ { \circ }$ 左右时停止拍摄。根据平大气模型理论4，当天顶距 $\mathsf { z } { \langle 7 5 ^ { \circ } }$ 时，大气质量 $\mathrm { \mathop { M } \left( z \right) } \approx _ { \mathrm { s e c \left( z \right) } }$ ，整个拍摄过程大气质量数从1.1到2，变化比较明显。

表1观测M67疏散星团测光标准星  
Table 1 The observed M67 open cluster standard stars   

<html><body><table><tr><td>AUID</td><td>RA (J2000)</td><td>Dec (J2000)</td><td>B/mag</td><td>V/mag</td><td>B-V</td></tr><tr><td>000-BLG-886</td><td>08:51:17. 12</td><td>+11:48:16.4</td><td>11. 553</td><td>10.289</td><td>1.264</td></tr><tr><td>000-BLG-889</td><td>08:51:12.71</td><td>+11:52:42.6</td><td>11. 617</td><td>10.524</td><td>1. 093</td></tr><tr><td>000-BLG-891</td><td>08:51:43.58</td><td>+11:44:26.7</td><td>11.898</td><td>10.763</td><td>1. 135</td></tr></table></body></html>

<html><body><table><tr><td>000-BLG-892</td><td>08:51:27.04</td><td>+11:51:52.8</td><td>11. 042</td><td>10.946</td><td>0.096</td></tr><tr><td>000-BLG-895</td><td>08:51:26.46</td><td>+11:43:51.0</td><td>11.391</td><td>11.263</td><td>0.128</td></tr><tr><td>000-BLG-896</td><td>08:51:42.39</td><td>+11:51:23.3</td><td>12. 342</td><td>11. 266</td><td>1. 076</td></tr><tr><td>000-BLG-902</td><td>08:51:42.37</td><td>+11:50:07.9</td><td>12.686</td><td>11.636</td><td>1.050</td></tr><tr><td>000-BLG-904</td><td>08:51:39.41</td><td>+11:51:45.9</td><td>13.138</td><td>12.138</td><td>1.000</td></tr><tr><td>000-BLG-924</td><td>08:51:41.97</td><td>+11:43:37.5</td><td>13.278</td><td>12.708</td><td>0.570</td></tr><tr><td>000-BLG-940</td><td>08:51:30.16</td><td>+11:43:50.2</td><td>13.714</td><td>13.133</td><td>0.581</td></tr></table></body></html>

获取观测数据之后，在IRAF 中对观测图像进行本底约化、暗流改正、平场修正，对预处理之后的图像进行较差测光[5]获取不同大气质量下测光标准星的仪器星等，再结合表1中的标准星等测定主消光系数及系统转换系数。

# 2.1主消光系数的确定

在地平高度较高时，可将大气层看作为理想平大气，在这一假设条件下天体的消光星等与消光路程成正比，由此可推导出大气消光公式[6]:

$$
m _ { z } - m _ { 0 } = k M ( z )
$$

式中 $\mathfrak { m } _ { \mathrm { z } }$ 为在大气内观测天顶距为Z的天体的视星等， ${ \mathfrak { m } } _ { 0 }$ 为天体在大气外的视星等，k为大气消光系数， $\mathrm { ~ M ~ } ( \mathbf { \boldsymbol { \mathbf { \rho } } } _ { \mathrm { Z } } )$ 为天顶距为z方向上的大气质量。大气消光与色指数有关，因此，消光系数k 通常应包括两项：一项是与波长无关的主消光系数 $\mathrm { ~ k ~ } ^ { \prime }$ ，另一项是与色指数C有关的二次消光系数 $\mathrm { ~ k ~ } ^ { \prime \prime }$ 。即：

$$
k = k ^ { \prime } { + } C k ^ { \prime \prime }
$$

由于 $2 8 0 \mathrm { m m }$ 全天区可转动光电阵的望远镜并未加装滤光片，而且 $\mathrm { ~ k ~ } ^ { \prime \prime }$ 比 $\mathrm { ~ k ~ } ^ { \prime }$ 小得多通常可以忽略不计[7]，因此只考虑大气对天体亮度直接消光的主消光系数。即大气消光公式可简化为：

$$
m _ { z } - m _ { 0 } = k ^ { \prime } M ( z )
$$

以星等差 $\Delta \mathrm { m } = \mathrm { m } \mathrm { z } - \mathrm { m } 0$ 为纵坐标，大气质量 $\mathrm { ~ M ~ } ( \mathrm { \Omega } _ { \mathrm { Z } } )$ 为横坐标，为了提高拟合精度，利用最小二乘法对整夜测光数据进行拟合，图1给出 2020年12月6日-8日的数据拟合图，并同时确定出大气消光系数K’，也就是拟合直线的斜率，结果列于表2。

![](images/b4a910fbb80925bd11079637a57fcde428fb2b120baa21de06ec317f262ce3de.jpg)  
图12020-12-06,12-07,12-08 主消光系数（(a):12-06 $k ^ { ' }$ (b):12-07 k(c):12-08 k)  
Fig.1The extinction coefficients of Dec 6，Dec 7，Dec 8，2020 ((a):Dec 6 $k$ (b):Dec 7 $k$ (c):Dec 8 $k ^ { ' }$ ）

# 表2主消光系数

Table 2 The values of the main extinction coefficients $k ^ { \prime }$   

<html><body><table><tr><td colspan="3">2020-12-06</td><td colspan="3">2020-12-07</td><td colspan="3">2020-12-08</td></tr><tr><td>主消光系 数</td><td>误差</td><td>线性相关 系数</td><td>主消光系 数</td><td>误差</td><td>线性相关 系数</td><td>主消光系 数</td><td>误差</td><td>线性相关 系数</td></tr><tr><td>0.4021</td><td>0.091</td><td>0.9927</td><td>0.3327</td><td>0.088</td><td>0.9971</td><td>0.3375</td><td>0.089</td><td>0.9914</td></tr></table></body></html>

# 2.2系统转换系数的测定

通过观测得到的仪器星等在进行大气消光改正后转化为大气外仪器星等，为使该结果与标准星等具有可比性，还需做标准星等系统的转换[8。由于未加装滤光片，因此仅考虑观测星等到标准系统星等的转换，这里我们采取如下的星等转换方程：

$$
V = \nu _ { 0 } + \varepsilon ( B - V ) + \xi
$$

式中V是标准星等，v0是大气外仪器星等，ε为系统转换系数，(B-V)为标准系统下色指数，为常数项。类似于确定主消光系数的方法，利用最小二乘法拟合确定转换系数ε和，结果列于表3。

对仪器星等进行大气消光改正和系统转换后得到星等转换综合公式：

$$
V = \nu - 0 . 3 5 7 4 M ( z ) + 0 . 4 3 2 2 ( B - V ) - 0 . 1 6 6 6
$$

表3系统转换系数  
Table 3 The instrument-related transformation coefficients   

<html><body><table><tr><td>2020-12-06</td><td></td><td colspan="2">2020-12-07</td><td colspan="2">2020-12-08</td><td colspan="2">平均转换系数</td><td>RMS</td></tr><tr><td>w</td><td>0.4546</td><td>w</td><td>0.4309</td><td>w</td><td>0.4112</td><td>w</td><td>0.4322</td><td>0. 0217</td></tr><tr><td>w</td><td>-0.1201</td><td>w</td><td>-0.2026</td><td></td><td>-0. 1773</td><td></td><td></td><td></td></tr><tr><td>转换标准误差</td><td>0.101</td><td>转换标准误差</td><td>0.102</td><td>转换标准误差</td><td>0.107</td><td>W</td><td>-0.1666</td><td>0.0423</td></tr></table></body></html>

# 3.测光精度分析

将M67疏散星团中观测目标的仪器星等进行大气消光改正和系统转化，然后再与相应的标准星等V做差,根据公式 $R M S E = \sqrt { \frac { 1 } { n } \sum _ { i = 1 } ^ { n } { ( \nu _ { i } - V ) ^ { 2 } } }$ 计算均方根误差来评估测光精度，结果如表4所示。

图3（a）（b）（c）分别显示了2020年12月6日、7日、8日三天数据中M67观测目标观测值转换后星等与标准星等的对比，对角线斜率分别1.026、1.031、1.051说明转换后星等与标准星等比较接近，在标准测光夜测量亮度亮于13.8等的星时，测光精度可达0.13星等。测光精度的大小受多方面因素的影响，例如城市光污染。对于 $2 8 0 \mathrm { m m }$ 望远镜来说，测光精度主要与未加装滤光片有关，这导致观测标准星获取的仪器星等并不完全是V波段的星等，这是主要误差所在。

由于 280mm望远镜用于空间目标的巡天观测，视场中出现的背景恒星具有随机性，因此选取背景恒星进行外符精度评估是很有参考价值的。在这项工作中我们用到UCAC2 星表，UCAC2 是由美国海军天文台出版的一份高密度、高精度的天体测量星表，它囊括了48,330,571颗恒星，覆盖天区较广，在一些区域甚至达到 $+ 5 2$ 度，星表中所有恒星都能提供自行和光度测定，位置在历元J2000.0中给出[9]。用户可以通过UCAC2星表提供的FORTRAN语言和C语言的访问接口进行调用查询。

2020年12月10日利用280mm望远镜对M67疏散星团附近天区进行巡天观测，将观测图像与UCAC2星表进行匹对，识别图像中的UCAC2标准星，并选取亮度范围在9.76星等到14.79 星等的一批UCAC标准星进行测光精度评估，如表5所示。利用式(5)将观测得到的仪器星等进行转换，然后与星表中的标准星等进行比较[10]并计算均方根误差，结果如图2（d)所示对角线斜率为1.081，RMSE见表4。

![](images/6671427532ac6ff6a58fd4e5af62c90d23408c12afeb94714db4a5239af88bba.jpg)  
图2标准星等（ $\mathrm { \nabla _ { V _ { s t d } } } ^ { \cdot }$ ）与转换后星等（ $\bf ( V _ { t r f } )$ 的比较（（a）（b）（c）分别为M67成员星在2020-12-06、12-07、12-08三天的星等对比图；（d）UCAC2星表成员的星等对比图）

Fig.2Relations between transformed magnitudes ( $\mathrm { \Delta V _ { t r f } ) }$ and standard magnitudes $\mathrm { ( V _ { s t d } ) }$ ((a):M67 for Dec 6(b):M67 for Dec 7(c):M67 for

Dec 8(d):UCAC2)

Table 4 RMSE of transformed magnitude and standard magnitud   

<html><body><table><tr><td colspan="2">2020-12-06</td><td colspan="2">2020-12-07</td><td colspan="2">2020-12-08</td><td colspan="2">2020-12-10</td></tr><tr><td>观测对象</td><td>M67测光标准</td><td>观测对象</td><td>M67测光标</td><td>观测对象</td><td>M67测光标准</td><td>观测对象</td><td>UCAC2测光标</td></tr><tr><td></td><td>星</td><td></td><td>准星</td><td></td><td>星</td><td></td><td>准星</td></tr><tr><td>RMSE</td><td>0.123</td><td>RMSE</td><td>0.136</td><td>RMSE</td><td>0.137</td><td>RMSE</td><td>0.141</td></tr></table></body></html>

上述计算结果表明，目标恒星的仪器星等在经过转换后与标准星等的线性相关系数接近于1，在标准测光夜下观测亮于14.8等星时，测光精度可达到0.14星等，与观测 M67疏散团标准星的测光精度大致相同。

表4转换后星等与标准星等的均方根误差  
表52020年12月10日观测的UCAC2标准星  
Table 5 The observed UCAC2 standard stars in December 10,2020   

<html><body><table><tr><td>Star ID</td><td>RA (J2000)</td><td>Dec (J2000)</td><td>B</td><td>V</td><td>B-V</td></tr><tr><td>33927639</td><td>8:54: 45. 40</td><td>+6:19:41. 26</td><td>13.196</td><td>12. 046</td><td>1.15</td></tr><tr><td>33927630</td><td>8:54:41. 08</td><td>+6:23:21. 39</td><td>14.182</td><td>13.623</td><td>0.559</td></tr><tr><td>33927652</td><td>8:54:54.12</td><td>+6:26:17. 49</td><td>12. 703</td><td>12. 286</td><td>0.417</td></tr></table></body></html>

<html><body><table><tr><td>35022955</td><td>8:43:36. 30</td><td>+9:13:00. 86</td><td>13.267</td><td>11.993</td><td>1. 274</td></tr><tr><td>35022948</td><td>8:43:31.72</td><td>+9:15:33. 50</td><td>13. 744</td><td>13.095</td><td>0. 649</td></tr><tr><td>35022970</td><td>8:43:51. 78</td><td>+9:22:26. 53</td><td>11. 372</td><td>10.838</td><td>0.534</td></tr><tr><td>35393641</td><td>9:03:21. 99</td><td>+10:18:06. 71</td><td>9.776</td><td>9.233</td><td>0.543</td></tr><tr><td>35393564</td><td>9:02:04. 55</td><td>+10:20:50.10</td><td>11. 918</td><td>11. 298</td><td>0. 62</td></tr><tr><td>35393643</td><td>9:03:27. 69</td><td>+10:24:04. 27</td><td>11. 749</td><td>11. 091</td><td>0. 658</td></tr><tr><td>35393663</td><td>9: 03:50.75</td><td>+10:25:39.38</td><td>13. 077</td><td>11. 788</td><td>1. 289</td></tr><tr><td>35932643</td><td>8:59:43.98</td><td>+11:35:03.83</td><td>10.580</td><td>10.089</td><td>0.491</td></tr><tr><td>35932553</td><td>8:58: 26. 62</td><td>+11:36:03. 13</td><td>12. 761</td><td>12. 126</td><td>0. 635</td></tr><tr><td>35932623</td><td>8:59:28. 46</td><td>+11 : 40:43. 80</td><td>13.550</td><td>12.517</td><td>1. 033</td></tr><tr><td>35932583</td><td>8:58: 49. 42</td><td>+11:50:30. 50</td><td>14. 609</td><td>12. 957</td><td>1. 652</td></tr><tr><td>35932500</td><td>8:57: 45. 94</td><td>+11:58:47. 25</td><td>14.792</td><td>13.743</td><td>1. 049</td></tr></table></body></html>

# 4.结语

本文对 $2 8 0 \mathrm { m m }$ 全天区可转动光电阵的测光精度进行科学评估，结果表明在标准测光夜测量亮度亮于13.8等的星时，测光精度可达0.13星等，该结果比较理想。望远镜未加滤光片，这是因为该设备多用于空间碎片的巡天观测，加装滤光片会影响空间暗弱目标的获取，在不配备滤光片的情况下可以充分发挥光电阵的探测能力。该设备的优势在于利用大视场开展空间碎片的监测工作，上述精度评估结果满足空间碎片巡天观测的精度要求。同时本文将巡天观测图像与UCAC2星表匹对，选取图像中的UCAC2成员星做外符精度校验，结果表明在标准测光夜下观测亮于14.8等星时，测光精度可达到0.14星等，说明 $2 8 0 \mathrm { m m }$ 全天区可转动光电阵的测光系统具有较好的稳定性与可靠性。

在完成测光精度评估的同时，还测定了吉林观测基地的主消光系数，然而对于观测台站消光系数的测量是个长期的过程，因此主消光系数的测量结果是比较粗糙的。接下来我们会改进观测方法，利用吉林观测基地其它设备在更好的测光夜对标准星进行测光，从而测定更精准的大气消光系数。

# 参考文献：

[1] 袁海龙，张彦霞，张昊彤，等.恒星大气参数测量[J].天文研究与技术，2018，15(3)：257-265.Yuan Hailong，Zhang Yanxia，Zhang Haotong,et al.Survey of Stellar Atmosphere Parameter Estimation [J].Astronomical Research & Technology,2018,15(3):257-265.  
[2] 胡静静，刘静，崔双星，等.地基光电望远镜对GE0 空间碎片探测能力分析[J].天文研究与技术，2017，14(1)：39-44.Hu Jingjing，Liu Jing，Cui Shuangxing,etal.Analysisof Detected Ability for Ground-Based Electro-OpticTelescope to GEO Region[J].Astronomical Research & Technology,2017，14(1):39-44.  
[3] 杜俊举.空间碎片的测光观测与图像处理[D].山东：山东大学，2015：2-11.Du Junju.Photometric Observation and Image Processing of Space Debris [D].SHANDONG UNIVERSITY,2015:2-11.  
[4] 胡波.高美古观测站大气消光系数测定的初步结果[J].天文学报,2010,51(4)：422-431.Hu Bo.Preliminary results of the measurement of atmospheric extinction coefficient a Gaomeigu ObservingStation [J]． Acta Astronomica Sinica,2010,51(4):422-431.  
[5] 张周生，陈培生，周吉光.丽江高美古的大气消光系数测定[J].云南天文台台刊，1996，S1：97-102.Zhang Zhousheng，Chen Peisheng，Zhou Jiguang.Determinationof the Extinction Coefficient at Gaomeigu [J].Publications of the Yunnan Observatory，1996,S1:97-102.  
[6] 钱伯辰，陶隽，潘红鉴.1.56m 望远镜 CCD 照相机系统的消光系数和转换系数测定［J].上海天文台年刊，1997,18：190-195.Qian Bochen,Tao Jun,Pan Hongjian.Thedeterminationof extinctionand transformation coefficients fro CCDcamera system of 1.56m telescope ［J].Annals of Shanghai Observatory Academia Sinica，1997，18：190-195  
[7] LIM B,SUNG H,BESSELL M S,KARIMOV R,et al.CCD Photometry of the Standard Stars atMaidanak AstronomicalObservatory in Uzbekstan:Transformation and Comparisons [J].Korea Astron Soc [J],2oo9,41(6):1-12.  
[8] 石火明，乔琪源，胡景耀，等.兴隆 60cm 望远镜主焦 CCD 系统测光性能的研究[J].天体物理学报，1998，18(1)：99-105.Shi Huoming,QiaoQiyuan,Hu Jingyao,etal.Characterization of the CCD Systemat the BAO 60cm Reflector forPhotometry[J]．Acta Astrophysica Sinica，1998，18(1) :99-105.  
[9] 邵红会.基于 UCAC2 星表的索引数据库的设计与实现[D].山东：山东大学，2010：7-16.Shao Honghui.The Design And Implementation Of Indexed Database Based On UCAC2 Catalog[D].SHANDONG UNIVERSITY,2010:7-16.  
[10] 郑伟康，裘予雷，王竞，等.兴隆 80cmTNT 望远镜测光性能的研究[J].天文研究与技术——国家天文台台刊，2009,6(2)：136-141.Zheng WeiKang，Qiu Yulei,Wang Jing，etal.Photometric accuracy of the Xinglong 80cm Tsinghuo-NAC Telescope(TNT）[J].Astronomical Research &Technology——Publications of National Astronomical Observatories ofChina,2009,6(2):136-141.

# Study on the photometric accuracy evaluation of 280 mm rotatable photoelectric array in Jilin astronomical observation base

NiuBingLi1,²,Liu ChengZhi1,Li ZhenWei1,KangZhe1 igchunsateliteerationationatioaltronocalbeatoryisecademyofiences,Cangca 2.University of the Chinese Academy of Sciences,Beijing 10o049,China)

Abstract: In this paper,the photometric accuracies of $2 8 0 \mathrm { m m }$ whole sky area rotatable photoelectric array which sited in Jilin astronomical observation are studied.A set of photometric standard stars of M67 open star cluster are observed.Firstly, we prepocess the image in IRAF and the photometry data is acquired by using the method of differential photometry.Then, the data is extracted for least square linear fitting, the fiting results show the main extinction coefficient and the transformation equations from instrument magnitude to standard magnitude.Finally, the root mean square error between transformed magnitude and standard magnitude is calculated to evaluate the photometric accuracy of the equipment.Our results indicate that the photometric precisions of this equipment is $0 . 1 3 \mathrm { \ m a g }$ for objects brighter than $1 3 . 8 \mathrm { \ m a g }$ under photometric conditions.In order to check this result we match the image with UCAC2 star catalogue and calculated the photometric accuracy.The results basically similar ot the former.The photometry accuracy of this equipment can basically meet the requirements of space debris observation.

Key words: photometry precision; sky survey； standard star; transformation equations;UCAC2 star catalogue