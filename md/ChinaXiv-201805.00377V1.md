# 地震前后基准站GPS数据异常提取算法

李南¹，孔祥增²，林岭²

(1．福建农林大学计算机与信息学院，福州 350000;2.福建师范大学 数学与信息学院，福州 350000)

摘要：目前对地震前兆异常的研究主要集中在“热”和“电”等方面，很少涉及基准站的GPS数据。然而，已经有学者证明震中附近基准站的GPS 时间序列坐标数据中也蕴含着大地震的前兆信息。针对 2001\~2010年间美国本土发生的具有代表性的三个地震进行了研究，首次将 Martingale理论运用于GPS 数据处理，提出一种异常提取算法，进而对地震前后，震中附近多个基准站的GPS 数据进行分析。实验结果表明算法能够有效的反映大地震前后GPS 数据中异常的变化趋势，为使用GPS数据对大地震进行预报提供了更多可能。

关键词：地震；Martingale理论；异常提取 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2017.09.0931

# Detection of anomalies in GPS data before and after earthquakes

Li Nan1, Kong Xiangzeng ², Lin Ling ² (1.CollegeofComputer&InformationScienceFujianAgriculture&Forestry UniversityFuzhou35oo0,China;2.Colege ofMathematics& InformationFujianNormal University,Fuzhou 35ooo,China)

Abstract: Mostresearch studies onforecastingofearthquakes focus on thermalorelectrical aspects.Scholars have proved GPS timeseries alsocontains precursory information for large earthquakes.For the problems mentionedbefore,three typical earthquakes hit America from 200lto 2010are investigated by using GPS dataof several GPSreference stations near the epicenters.AnalgorithmbasedonMartingale theoryisproposed todetecttheanomaliesinGPSdata.Theexperimentalresults showthat the proposedalgorithmcan effectivelyreflect thechange process inGPSdata beforeand afer large earthquakes, which offers more possibilities for earthquake forecast from GPS data.

KeyWords:earthquake; Martingale theory; anomaly detection

# 0 引言

地震是一种常见的自然灾害，它会对震区人民群众的生命和财产造成巨大的损害。在过去的数十年中，不少学者致力于研究地震前兆异常，以对地震未来的发展趋势进行预测，涉及的指标主要包括“热”[1]和“电”[2]等方面。例如，Kong 等人[3]使用NOAA 卫星遥感射出长波辐射（outgoing long-waveradiation,OLR),探索汶川地震和庐山地震前OLR数据的异常。Han等人[4统计了2001\~2010年日本Kakioka站台的超低频段电磁发射数据，试图找出数据中异常和地震之间的关联。Nemec等人[5使用统计方法研究地震前低频电磁波数据，发现在地震前短时间内固定频率电磁波会出现异常。Liu等人[研究了台湾地区 $1 9 9 3 - 2 0 0 4$ 年电离层总电子含量异常和地震的相关性。Kuo 等人[7对日本2011Tohoku-OkiMw9.0级地震前，电离层总电子含量的预测值和观察值进行了对比，以研究地震前电离层TEC异常。

研究表明，基准站的GPS时间序列坐标数据经过前期处理，可以求出每日的坐标位移解，能反映中、低频地形形变信息，并且具有比较好的稳定性[8]。Wang等人[9]使用Molchan图表法，已经证明GPS形变中蕴含着地震的前兆信息。Sagiya等人[10]以多个GPS基准站时序坐标数据为对象，来研究地震等其他地壳变化。Yeha 等[I]基于多个GPS 基准站建立一个GPS 网络，发现GPS时序坐标数据在2013年台湾南投和花莲地震前出现了一定程度的扰动。文献[12]中尝试使用一种非线性过滤器来提取GPS数据中可能与地震有关的异常信号。赵等[13]利用中国大陆几个邻近GPS基准站数据，研究了日本2011年发生的9.0级地震的震前变化，认为震前运动速度变慢的趋势可能是地震的前兆。因此，尽管将GPS数据作为地震前兆异常中指标的研究还是相对较少，对其进行分析，寻找其中蕴含的地震前兆异常信息具有可行性。然而，现有成果主要局限于地理学科，结果分析主要是基于人工观察，直接受到领域专家知识和经验的影响，对于震前相关异常的判定具有很大的不确定性。

数据挖掘的目的就是从海量的、不完全的、有噪声的数据中提取出隐含的、未知的但是又潜在有用的知识和信息的过程。当前，已有部分学者将数据挖掘中异常检测的方法运用于分析地震前不同指标的变化。例如，Marzocchi等人[14]使用贝叶斯估值方法运用于分析地震数据，文献[15]中使用小波变换用于寻找地震前OLR数据的异常，文献[16]中使用模糊神经算法用于检测震前电磁异常，文献[17]中提出一种基于误差和关键点的地震前兆观测数据异常挖掘算法。

本文的贡献主要在于：目前涉及使用基准站的GPS数据来分析震前异常的研究还比较少，方法也主要是基于人工观察，对于异常的判定不确定性较大。因此，本文使用NevadaGeodeticLaboratory提供的GPS数据，基于Martingale理论[18]与GPS数据特点，提出了一种异常提取算法ADM（anomalydetectionbasedonmartingale theory forGPSdata）。针对发生在美国比较具有代表性的三个地震，运用该算法，对地震前后震中附近基准站的GPS时间序列数据进行了分析研究。结果不仅进一步证实了GPS数据中蕴藏着地震的前兆信息，而且为将数据挖掘算法运用于地理学科提供了借鉴。

# 1 相关数据

本文研究的对象是从2001年以来，发生在美国陆地上深度小于 $6 0 \mathrm { k m }$ 的地震中，震级最大的Ms7.2级地震，以及两个震中距离相对较近的地震。地震的相关信息来自美国地质调查局（USGS，https://earthquake.usgs.gov/earthquakes/)，具体如表1所示。

表1地震相关信息  

<html><body><table><tr><td>Date</td><td>Latitude</td><td>Longitude</td><td>Depth</td><td>Magnitude</td></tr><tr><td>(y-m-d)</td><td>( N)</td><td>(E)</td><td>(km)</td><td>(JMA)</td></tr><tr><td>01-02-28</td><td>47.149</td><td>-122.727</td><td>51.80</td><td>6.8</td></tr><tr><td>08-02-21</td><td>41.144</td><td>-114.872</td><td>7.90</td><td>6.2</td></tr><tr><td>10-04-04</td><td>32.286</td><td>-115.295</td><td>9.99</td><td>7.2</td></tr></table></body></html>

使用的GPS数据是GPS基准站站点坐标，分为东西向、北南向和垂直向三个方向，来源于 Nevada Geodetic Laboratory的数据共享服务网站（http://geodesy.unr.edu/)，数据使用IGS08框架[19]。综合考虑站点位置以及GPS 数据的完整性，实验中使用的GPS基准站的信息如表2所示。SEAT站和CLOV站分别对应2001-02-28与2008-02-21这两个发生在不同时间，震中位置相对较近的地震，以分析不同时期，同一地理位置附近，地震前后基准站的GPS数据。MEXI、IID2与P500 这三个站点对应的是发生在2010-04-04的M7.2 级地震，以研究对于同一地震，震中附近不同基准站的GPS 数据是否出现相似的异常。

# 2 研究方法

以 $D a t a = \{ d _ { 1 } , d _ { 2 } , . . . , d _ { t - 1 } \}$ 表示某基准站指定方向上的GPS 历史数据， $\boldsymbol { d } _ { t }$ 表示当前数据。显然，当地质板块的活动较为平稳时，Data中的样本分布应该维持在一个相对稳定的水平，样本之间具有某种相似的特征。因此，结合文献[3]，可以将 $D a t a \cup d _ { t }$ 看成按照时间顺序，以数据流形式到来的，来自同一个聚类中的样本进行分析。

表2GPS 站点相关信息  

<html><body><table><tr><td rowspan="2">Name</td><td>Latitude</td><td>Longitude</td><td>Height</td></tr><tr><td>( N)</td><td>(E)</td><td>(m)</td></tr><tr><td>SEAT</td><td>47.654</td><td>-122.309</td><td>44.211</td></tr><tr><td>CLOV</td><td>40.558</td><td>-114.874</td><td>2084.911</td></tr><tr><td>MEXI</td><td>32.633</td><td>-115.476</td><td>-22.339</td></tr><tr><td>IID2</td><td>32.706</td><td>-115.032</td><td>9.792</td></tr><tr><td>P500</td><td>32.690</td><td>-115.300</td><td>-20.595</td></tr></table></body></html>

承上所述，基于最小化同一聚类中各样本差异原则[20]，设$c$ 为 $D a t a$ 的聚类中心，以式（1）计算：

$$
C = \frac { 1 } { t - 1 } \sum _ { i = 1 } ^ { t - 1 } d _ { i }
$$

那么 $\mathbf { \nabla } d _ { t }$ 对于 $c$ 的偏移程度可以用式（2）衡量：

$$
s _ { t } = s ( D a t a , d _ { t } ) = \parallel d _ { t } - C \parallel
$$

其中 $\| \bullet \|$ 可以是任意的相异性度量函数，实验中使用欧式距离。

考虑 $d _ { 1 } , d _ { 2 } , . . . , d _ { t - 1 }$ 的分布情况，可以依据Data中 $d _ { t }$ 近邻对象的个数来衡量其异常程度。因此，ADM算法中用式（3）来衡量 $d _ { t }$ 所对应的当前指定方向上GPS数据的平稳程度：

$$
p _ { t } = \frac { \# \{ j | s _ { j } > s _ { t } \} + \theta _ { t } \# \{ j | s _ { j } = s _ { t } \} } { t }
$$

在式（3）中， $\theta _ { t }$ 是（0,1]内的随机数， $\# \{ \}$ 是一个函数，返回满足给定条件的样本的数量， $j = 1 , 2 , . . . , t$ ， $s _ { t }$ 采用式（2）计算。

从式（3）可以看出， $p _ { t } \in \left( 0 , 1 \right]$ 且 $p _ { t }$ 越大，表明 $d _ { t }$ 越符合之前样本的分布情况，相应的当天数据出现异常的可能性越小。然而，GPS数据中不可避免地会存在噪声（闪烁噪声以及随机漫步噪声等)，某天相对较小的 $p _ { t }$ 值并不足以说明当前GPS数据整体出现了异常，需要通过使用Martingale 理论[18]，综合考虑整个时间序列数据的变化趋势。

Martingale 理论[18]起源于赌博业和概率论，是最早的金融资产定价模型之一，现在已经被广泛运用于决策优化，投资分析等领域。为了真实反映GPS数据持续变化的情况，结合Martingale理论与GPS数据特点，所需要分析的每个数据 $d _ { t }$ 所对应的随机化的Martingale 值（以下简称 $M$ 值）以式（4）计算：

$$
M _ { t } = \prod _ { i = 1 } ^ { t } ( \varepsilon p _ { i } ^ { \varepsilon - 1 } ) = M _ { t - 1 } \cdot ( \varepsilon p _ { t } ^ { \varepsilon - 1 } )
$$

根据文献[21]，取 $\varepsilon = 0 . 8 2$ 并初始化 $M _ { 0 } = 1$ 。从式（4）中 $M$ 值的计算过程可以看出，越大的 $M$ 值表示之前一定时间内GPS

数据的异常越明显。

聚类算法中，初始聚类中心的选择会对聚类结果造成较大的影响。类似的，Data中首个样本 $d _ { 1 }$ 位置的选取也会对异常的提取造成较大的影响。因此，算法中设置了一个初始聚类样本个数参数num。在初始化 $C = \frac { 1 } { n u m } \sum _ { k = 1 } ^ { n u m } d _ { n u m }$ 以及$s _ { i } = \big \| d _ { i } - C \big \| , i = 1 , 2 , . . . , n u m$ 后，从 $d _ { n u m + 1 }$ 开始计算 $M$ 值。直观地说，就是将所分析数据前num天的平均数据作为初始中心，并从num天后开始分析以减少结果的不确定性。

此外，由于大地震发生前后地壳运动相对剧烈，表现为GPS  
数据有可能在短时间内出现较大波动。结合式（4)，此时 $M$ 值  
会迅速不断增大到不可控的程度。为了避免这种情况的发生，  
算法中设置了另一个停止参数 $h$ 。也就是说，如果 $M _ { i } > h$ ，那么  
从 $d _ { i + 1 }$ 开始重新开始算法。参数num与 $h$ 对算法效果的影响将实验部分进行进一步分析与验证。

综上所述，ADM算法的具体步骤如下：算法名称：ADM输 入：某基准站指定方向上的GPS 数据 Data，停止参数 $h$ ，初始聚类样本数num输 出：Data中每个样本对应的 $M$ 值Step.1 初始化样本中心： $C _ { n u m } = \frac { 1 } { n u m } \sum _ { i = 1 } ^ { n u m } d _ { i }$ 偏移程度： $s _ { i } = \big \| d _ { i } - C \big \| , i = 1 , 2 , . . . , n u m$ $M$ 值： $M _ { i } = 1 , i = 1 , 2 , . . . , n u m$ （204号当前处理样本序号： $k = n u m + 1$ （204号循环停止条件： $i s S t o p = f a l s e$ （204号当前批次样本开始序号：fron $^ { \cdot } = 1$ （204$/ /$ 如果检测到 $M _ { k } > h$ ，那么从 $d _ { k + 1 }$ 开始$/ /$ 一个新的批次(即算法重新启动)Step.2while $k \leq \left| D a t d \right|$ &&！isStop2.1使用 $d _ { k }$ 、 $C _ { k - 1 }$ 与式（2)，计算 $s _ { k }$ （202.2使用 $s _ { f r o n t } , s _ { f r o n t + 1 } , . . . . , s _ { k }$ 与式（3），计算 $p _ { k }$ （204号2.3使用 $M _ { k - 1 }$ 与式(4)，计算 ${ { M } _ { k } }$ （204号2.4计算 $d _ { f r o n t } , d _ { f r o n t + 1 } , . . . , d _ { k }$ 的聚类中心$C _ { k } = \frac { 1 } { k - f r o n t } \sum _ { i = f r o n t } ^ { k } d _ { k }$ 2.5使用 $C _ { k \mathrm { ~ \scriptsize ~ , ~ } } d _ { f r o n t } , d _ { f r o n t + 1 } , . . . , d _ { k }$ 与式$s _ { f r o n t } , s _ { f r o n t + 1 } , . . . , s _ { k }$ （204号2.6k++2.7if $M _ { k - 1 } > h$ （204（204号 $i s S t o p = t r u e$

end ifend whileStep.3if $i s S t o p = t r u e$ && $k + n u m + 1 \leq \left| { \cal D } a t d \right|$ 3.1isStop $\ c =$ false$3 . 2 ~ C _ { { k + n u m } } = \frac { 1 } { n u m } \sum _ { i = k } ^ { k + n u m } d _ { i }$ 3.3 $M _ { i } = 1 , i = k , k + 1 , . . . , k + n u m$ 3.4front $\mathbf { \sigma } ^ { \cdot } = k$ 3.5 $k = k + n u m + 1$ 3.6 转到 Step.2//开始一个新的批次end ifStep 4．输出 $M _ { i } , i = 1 , 2 , . . . , | D a t d$

# 3 结果与分析

a）SEAT站和CLOV站的原始GPS时间序列坐标数据以及对应的 $M$ 值如图1和2所示。两个基准站分别对应两个发生在不同时间、震中位置相对较近的地震。ADM算法中，参数num设置为 $4 5 , h$ 设置为1000。研究的数据从发生地震上年的10月开始，一直延续到地震后的一个月。为了降低 $\theta$ 的随机取值对结果造成的影响，图中使用10次实验的平均值。出于更好的观察GPS数据变化趋势的目的，原始值中只使用相应GPS数值的小数部分而忽略相同的整数部分，黄色竖线表示地震发生时间。

从图1（d）与图2（d）可以看出，前期各个方向上的M值几乎没有任何变化，说明GPS数据比较稳定。临近地震前后，两个基准站东西向和北南向的 $M$ 值均出现了显著变化，并且在地震后一周左右迅速达到峰值，这进一步证实了GPS数据中蕴含着和地震有关的信息。值得注意的是， $M$ 值在地震前出现波动，在地震后才达到峰值的原因可能在于：由于地震的生成机制，GPS数据的异常可能出现在地震前很短的一段时间内，而为了反映GPS数据的变化趋势以及减少噪声对结果造成的影响，算法需要在累积一定数量的异常样本之后， $M$ 值才会相应出现显著的变化，因此地震前GPS数据发生的异常有可能相应的表现为地震后短时间内M值达到峰值。虽然可以通过将参数$h$ 设置为较小的数值以将 $M$ 值峰值出现的时间提前，但是这有可能导致出现误报，本文将在实验c)中验证参数 $h$ 对算法效果的影响。

由于两个地震震中位置相对较近，成因相似，因此所提取的东西向和北南向的M值变化规律也比较类似，这从侧面上说明本文提出的ADM算法的可靠性。此外，这两个方向上的原始GPS数据图像并无出现明显的异常趋势，这证实了ADM算法提取GPS数据异常的有效性。因为垂直向GPS数值的测量误差要远远大于东西向和北南向[9，所以对比东西向和北南向的M值，两个基准站垂直向 $M$ 值波动都不明显，并没有呈现和地震明显相关的规律。

![](images/b1d1654f6654463cb7dbca09cd85131f07be0cb40ea4baaa747898b8535863c7.jpg)  
(a)SEAT站东西向原始值（2001-02-28地震）

0.25 0.24 trierielg 0.23 MMW 0.22 0.21 0.2 2000.75 2000.83 2000.91 2001 2001.08 2001.16 2001.24 Date

![](images/3b74693e0bf19fd0ab53122e3ba2b03ae119483d3a99e728006fa46ee501a6d9.jpg)  
(b)SEAT站北南向原始值(2001-02-28地震)

![](images/d536e78ee80487f0e2967358438b7cc97b9ac8f4f3ea6a8d50a7f95d52da968d.jpg)  
(d)SEAT站三个方向对应 $M$ 值（2001-02-28地震)   
图1

![](images/da2907385f00e1fa4d993187a0e694ccebf30046b149aa85244504f6147f7d97.jpg)  
(c)SEAT站垂直向原始值（2001-02-28地震）  
图2

b）2010-04-04地震震中邻近MEXI站、IID2站和P500站的GPS数据原始值以及对应的 $M$ 值分别见图3、图4与图5,原始值中同样只显示相应的小数部分，黄色竖线表示地震发生时间。实验的目的是研究对于同一地震，震中附近不同基准站GPS数据的异常。ADM算法中，参数num设置为45,h设置为1000。由于此次地震后短时间内，各个基准站特定方向上的GPS数据会突然出现“断崖”式的变化，因此研究的数据从发生地震上年的10月开始，一直延续到地震后的两个月。为了更清晰的展示地震前后，三个方向GPS数据的异常趋势，图3\~5中分别单独列出对应三个方向上的 $M$ 值。

对比图3(c)(d)可以看出，由于地震后基准站特定方向上的GPS 数据出现的“断崖”式的变化，相应的 $M$ 值也在之后对应的一段时间内达到峰值。类似的情况也出现在图 4(a)(b)，图5(c)(d)等。波峰的延后出现，一方面说明本文提出的ADM算法能够真实反映GPS数据中的异常，另一方面也说明了实验1中导致M值出现峰值的GPS数据异常可能是在震前出现的。图1(a)与图1(b)中，MEXI站东西向没有出现类似情况的原因在于：GPS 数据在地震前就出现了潜在的剧烈变化，导致M值超过了预先设置的停止参数 $h = 1 0 0 0$ ，于是算法重新启动并拟合了这部分“断崖”数据。

可能是由于地震成因不同并且2010-04-04地震的震级较大，因此三个基准站东西向的 $M$ 值，MEXI站与IID2 站北南向的 $M$ 值都在地震前一段时间就达到过峰值，说明在地震发生前GPS 数据就有较大的异常发生，从侧面证明了GPS形变中蕴含着地震的前兆信息，尽管此时原始GPS数据图像并无明显的异常趋势。这为使用本文提出的ADM算法，利用GPS数据对大地震进行预报提供了可能。各个基准站第一次 $M$ 值达到峰值后又出现平缓的原因在于：算法重新启动，需要拟合mum天的数据后再判定异常，这段时间内 $M$ 值始终为初始值1。与MEXI站与IID2站类似，P500 站北南向的 $M$ 值在地震前也出现了一定程度的变化，只不过变化程度要远低于上述两个基准站，这可能与基准站的具体位置有关。与实验a）情况类似，三个基准站垂直向 $M$ 值的变化并没有呈现一致的规律，只有IID2站垂直向的 $M$ 值比较明显地在地震前后出现了波动，MEXI站垂直向的波动可能来源于数据“断崖”式的变化，而P500站垂直向M值的峰值出现在地震后一段时间内。

(d)MEXI站北南向 $M$ 值(2010-04-04地震)

(e)MEXI站垂直向原始值(2010-04-04地震)

![](images/d7ce98d9163aafc46d1f62e2655084804d58da9f9e57633a27a53daa8b80e31b.jpg)  
(f)MEXI站垂直向 $M$ 值(2010-04-04 地震)   
图3

![](images/9093c4e9c066f983e5fdfa409b723148b822f93b56f95d1fe6e95ab5cc4f88fe.jpg)  
图4

![](images/006be6c8e8b08bbeb83bc18a21c303f51810cf41bc19bb922d1c06deaf9d7956.jpg)  
  
(f)P500 站垂直向 值(2010-04-04 地震)   
图5

从基准站分布的位置上看，图3\~5中可以看出，由于三个基准站都位于震中附近，因此在测量误差相对较小的东西向和北南向上，各个基准站 $M$ 值第一次出现波峰的时间并不存在显著差异。但是，三个基准站中距离震中最近的MEXI站两个方向上波峰第一次出现的时间会早于IID2站与P500站。这说明距离震中越近的基准站， $M$ 值可能越早出现波峰，即GPS 数据潜在异常越早发生。

结合图1\~5，同样从测量误差相对较小的东西向和北南向上，进一步分析地震震级、发生时间与 $M$ 值之间的关系。本文研究的三个地震中，震级最大的2010-04-04地震（Ms7.2）所对应的三个基准站的M值第一次波峰出现的时间均在地震发生前三个月左右，变化一直持续到地震发生时。而震级相对较小的2001-02-28地震（ $\mathrm { M s } 6 . 8 \AA \AA ^ { \cdot }$ ）与2008-02-21地震（ $\mathrm { ~ M s 6 . 2 ) }$ 各自对应基准站的 $M$ 值则最早在地震前一个月左右开始变化，并在地震后较短的一段时间内达到波峰。这说明地震震级越大，之前需要积攒的能量越多，GPS数据潜在的异常可能更早发生，因此M值相应越早出现波动。此外，2001-02-28地震(Ms6.8)M值波动出现的时间要迟于2008-02-21地震（ $\mathrm { M s } 6 . 2$ ）的原因可能在于前者的震源深度( $\cdot 5 1 . 8 0 \mathrm { k m } ^ { \cdot }$ )要远大于后者（ $7 . 9 0 \mathrm { k m } ,$ )，因此地震发生前期GPS数据潜在变化相对不明显。

c）为了评价参数 $h$ 对算法效果的影响，本文在MEXI站北南向上，分别将 $h$ 设置为250,500,1000,2000进行了测试，参数num设置为45。实验结果如图6所示。

![](images/f4294753bef5d5c15b3aa49a6db8fada7a255479c4a36798186574231be51558.jpg)  
  
图6 $h$ 值对算法效果的影响(MEXI站北南向)

从图6中可以看出，当GPS数据中出现异常时， $M$ 值将以指数级别迅速增长。显然，当num相同时，通过将参数 $h$ 设置为较小的数值，可以将首次 $M$ 值峰值出现的时间提前。对比500,1000,2000，将 $h$ 设置为250时，第二次波峰出现的时间并没有提前的原因在于：当第一次检测到 $M \geq h$ 后，算法需要重新启动。此时，不同 $h$ 值重新开始的位置不同，在GPS数据中已经出现异常的前提下，再次获得的新批次样本的初始聚类中心会有较大的差异，这有可能导致波峰出现滞后。由于过小的值有可能会导致过多的误报，因此 $h = 1 0 0 0$ 是一个相对合理的取值。

d）为了评价参数num对算法效果的影响，本文同样在MEXI站北南向上，分别将num设置为25,35,45,55进行了测试，参数 $h$ 设置为1000。实验结果如图7所示。

![](images/826e77d1efcf8608eefc9d2594c3f0eb26e2f123952a815063318eb03833f948.jpg)  
图7num值对算法效果的影响(MEXI站北南向)

显然，当GPS数据稳定时，只要 $n u m$ 足够大，受其影响的，不同num值所对应的初始聚类中心 $c$ 差别应该不大。因此，从图7中可以看出，num值的不同对 $M$ 值第一次波峰出现的时间几乎没有影响。然而，与实验（3）类似，当算法重新启动时，随着GPS数据中潜在异常的出现，不同num值所对应的初始聚类中心 $c$ 有所差别，因此 $M$ 值第二次出现波峰的时间存在一定的差异。虽然实验（4）中，将num设置为55时 $M$ 值出现波峰的时间最早，但是考虑到将来实际应用中，过大的num值有可能使得M值两次波峰出现的间隔过长，因此本文中将num设置为45。

e）为了比较本文提出的ADM算法与目前常用的利用领域专家知识和经验来判断地震前兆异常的方法[22]，本文在SEAT站北南向的数据上进行了实验，数据异常判定采用 $k \sigma$ 准则。在$k \sigma$ 准则中，以 $\textstyle { \overline { { x } } }$ 表示观测结果的平均值， $\sigma$ 表示观测结果的标准差，如果数据超出了 $[ \overline { { x } } - k \sigma , \overline { { x } } + k \sigma ]$ 的范围，则认为有异常发生。实验中依据文献[22]将 $k$ 值设定为2，结果如图8所示。

![](images/4e91ccca9144a252954dbe341cf6eabf5df0ff95cbf07b1b8823db038155851d.jpg)  
图8 $k \sigma$ 准则实验结果(SEAT站北南向)

从图8中可以看出， $k \sigma$ 准则不但没能及时发现震前异常，反而是地震发生数周后，数据多次超出了 $[ \overline { { { x } } } - k \sigma , \overline { { { x } } } + k \sigma ]$ 的范围，这表明 $k \sigma$ 准则并没有效果。对比图1(d)中，地震前后短时间内，$M$ 值不仅出现了波峰，同时数值能够反映大地震前后GPS 数据中异常的变化趋势，显然本文提出的ADM算法更具有优势。

# 4 结束语

本文首次将Martingale理论运用于GPS数据，提出了一种针对GPS数据的异常提取算法ADM，并用该算法分析地震前后，震中附近基准站的GPS时间序列坐标数据。从结果中可以看出，对比于局限于地理学科，基于领域专家知识和经验，直接观察数据的传统方法， $M$ 值的变化能够真实反映GPS数据的潜在的变化趋势。即使原始GPS数值没有明显异常，在地震前后一段时间内其对应的 $M$ 值也会出现较大的变化，而且有可能在地震前就达到峰值。这不仅进一步证实了GPS形变中蕴涵着地震的前兆信息，也为使用GPS数据对地震进行预报提供了可能。然而，基于目前的数据量和研究水平，探究使用基准站GPS数据对大地震进行预报将是一项长期工作。本文提出的ADM算法所提取的震中附近基准站GPS数据所对应的 $M$ 值的异常已经揭示了一些初步规律，但还需要在更多的地震实例上进一步验证 $M$ 值的变化趋势与地震各参数（震级、位置、发生时间等）之间的关系并对其进行统计可靠性分析，这也是本文下一步的研究方向。

# 参考文献：

[1]Saradjian M R,Alhoondzadeh M.Thermal anomalies detection before strong earthquakes $( \mathrm { M } { > } 6 , 0 )$ using interquartile,wavelet and Kalman filter method [J].Natural Hazards and Earth System Sciences,2011,11(1):1099- 1108.   
[2]Honkura Y,Oshiman N,Matsushima M,etal.Rapid changes in the electrical state of the 1999 izmit earthquake rupture zone [J]. Nature Communications, 2013,4 (2116): 1-10.   
[3]Kong X, Bi Y, Glass D H. Detecting seismic anomalies in outgoing longwave radiation data [J].IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing,2015,8 (2): 649-660.   
[4]Han P,Hattori K,Hirokawa M,et al.Statistical analysis of ULF seismomagnetic phenomena at Kakioka,Japan during 2Oo1-2010 [J]. Journal of Geophysical Research: Space Physics,2014,119 (6): 4998-5011.   
[5]Nemec F,Santol KO,Parrot M.Decrease of intensity of ELF//VLF waves observed in the upper ionosphere close to earthquakes: A statistical study [J]. Journal of Geophysical Research Atmospheres,2009,114(4):1-10.   
[6]Liu JY,Chen YI, Huang C H,et al.A statistical studyof lightning activities and $\mathrm { ~ M ~ } \geqslant ~ 5 . \mathrm { ~ 0 ~ }$ earthquakes in Taiwan during $1 9 9 3 - 2 0 0 4$ [J]. Surveys in Geophysics,2015,36(6): 851-859.   
[7]Kuo C L,Lee L C,Heki K.Preseismic TEC changes for Tohoku-Oki earthquake: Comparisons between simulations and observations.[J]. Terrestrial,Atmospheric & Oceanic Sciences,2015,26(1): 63-72.   
[8] 张燕，吴云，段维波，等.GPS 长趋势变化与大地震的关系[J].武汉大 学学报：信息科学版,2012,37(6):675-678.   
[9]Wang T, Zhuang J,Kato T, et al.Assessing the potential improvement in short-term earthquaks forcasts from incorporation of GPS data [J]. Geophysical Research Letters,2013,40 (11): 1-5.   
[10] Sagiya T,Miyazaki S,Tada T.Continuous GPS array and present-day crustal deformation of Japan [C]// Proc of the lst Workshop of the APEC Cooperation for Earthquake Simulation.[S.l.]:IEEE Press,20oo:2303- 2322.   
[11]Yeha YL,ChengaKC,Wanga WH,etal.Very short-term earthquake precursors from GPS signal interference based on the 2O13 Nantou and Rueisuei earthquakes,Taiwan [J]. Journal of Asian Earth Sciences,2015, 114 (2): 312-320.   
[12] Wang T,Bebbington M.Identifying anomalous signals in GPS data using HMMs:An increased likelihood of earthquakes [J].Comptutational Statistics and Data Analysis,2013,58(1): 27-44.   
[13]赵国强，李鹏．中国大陆GPS 连续观测站测得的日本9.0级地震同震 位移与震前变化[J].地震,2012,32(2):129-134.   
[14] Marzocchi W, Zechar J,Jordan T.Bayesian forecast evalution and ensemble earthquake forcasting[J].Bulletin of the Seismological Society of America, 2012,102 (6): 2574-2584.   
[15] Xiong P,Shen X,Bi Y,et al.Study of outgoing longwave radiation anomalies associated with Haiti earthquake [J].Natural Hazards& Earth System Sciences,2010,10 (10): 2169-2178.   
[16]Konstantaras A,Varley M,Vallianatos F,etal.Detection of weak seismoelectric signals upon the recordings of the electrotelluric field by means of neuro-fuzzy technology[J].IEEE Geoscience & Remote SensingLetters, 2007,4(1): 161-165.   
[17]李正媛，陈晶，王丽娜，等．一种基于误差和关键点的地震前兆观测数 据异常挖掘算法[J].计算机应用研究,2011,28(8):2987-2901.   
[18] Ho S S,Wechsler H.A Martingale framework for detecting changes in data streams by testing exchangeability [J].IEEE Transactions on Software Engineering,2010,32(12): 2113-2127.   
[19] Rebischung P,Griffiths J,Ray J,et al.IGSO8:the IGS realization of ITRF2008 [J].GPS Solutions,2012,16 (4): 483-494.   
[20] Kanungo T,Mount D M,S. Netanyahu N,et al.An efficient $\mathbf { k }$ -means clustering algorithm:Analysis and inplemention [J].IEEE Trans on Pattern Analysis and Machine Intelligence,2002,24(7): 881-892.   
[21] Vork V,NouretdinovI,Gammerman A.Testing exchangeability on-line [C]/ Proc of the 12th International Conference on Machine Learning,San Francisco:Morgan Kaufmann,2003:768-775.   
[22] Wu LX,Qin K,Liu S J.GEOSS-Based thermal parameters analysis for earthquake anomaly recognition [J].Proceedings of the IEEE,2012,100 (10): 2891-2907.