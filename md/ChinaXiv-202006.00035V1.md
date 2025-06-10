# 基于CloudSat卫星资料对中亚低涡暴雨个例的诊断分析和数值模拟

丁明月1,2.3，王俐俐²，辛渝1，刘琼²，陈勇航²，张广兴1，杨莲梅1，梁倩²，黄观²，刘统强²

(1.中国气象局乌鲁木齐沙漠气象研究所,新疆 乌鲁木齐 830002;2.东华大学环境科学与工程学院,上海201620;3.北京金风慧能技术有限公司,北京100176)

摘要:利用 ECMWF 再分析资料作为初始场和边界条件，用 WRF(eather esearch and orecasting model，WRF)模式对新疆地区中亚低涡暴雨个例进行模拟,结合区域自动气象站每小时降水数据、CloudSat卫星2B-CWCRO数据产品和FY-2E卫星TBB 资料评估Lin方案、WSM6方案、Thompson 方案和WDM6方案在新疆地区的适用性。结果表明：Thompson 方案在小雨（ $0 . 1 { \sim } 5 . 0 ~ \mathrm { m m }$ ）和中雨（ $5 . 1 \sim 1 0 . 0 \ \mathrm { m m }$ ）的 $^ { 1 2 \mathrm { ~ h ~ } }$ 累积降水模拟中占有优势。4种云微物理参数化方案模拟的云顶亮温分布图均与FY-2E卫星观测十分相似，但在数值上均低于观测。从CloudSat 剖面平均的冰水含量的垂直分布情况看，Thompson 方案模拟冰水含量在数值和高值区的高度上模拟的最好，Lin方案的模拟效果最差。从 $3 \mathrm { k m }$ 区域平均冰水含量的垂直分布情况看，Thompson 方案模拟的云冰含量最高，WSM6方案与WDM6方案模拟的云冰含量次之，且两者的冰水含量-高度廓线图几乎重合，Lin方案模拟的云冰含量最低。

关键词：WRF；云微物理参数；CloudSat；中亚低涡；暴雨

中亚低涡是造成新疆暴雨的主要天气系统，虽然新疆位于干旱半干旱地区，发生暴雨的次数并不多，但由于生态环境脆弱，一旦出现暴雨就会造成巨大的人员伤害及财产损失[，例如：2016年7月31日至8月1日，新疆西部出现了一次突发性特大暴雨天气过程，引发的洪水造成了近亿元的经济损失[2]。云微物理过程及其与大气其他过程的相互作用是模式预报存在不确定性的主要因素之一。为了减少暴雨预报的不确定性，合理选择云微物理参数化方案就显得尤为重要。

在模式的降水模拟中，如何处理云微物理过程起着主要作用[3]，目前各种云微物理过程在处理方法中均有所不同，采用不同云微物理过程会显著影响降水的湿微物理过程，进而影响降水的预报、模拟，因此合理的选用云微物理过程很大程度上能够改善预报、模拟结果。董昊等[4]针对一次胞线过程采用不同微物理过程开展不同云凝结核(CCN)浓度的敏感性试验，分析了CNN对不同降水率、总降水的影响，指出不同云微物理过程中CNN 对降水的影响既有差别又有相似；而 Thompson 中CCN 对降水的影响最为显著，WDM6 影响最小。朱格利等[3通过对比8种不同云微物理参数化方案的模拟效果，分析了华南的一次暴雨过程，结果表明，总体上WSM5方案对暴雨模拟效果最好，最差的是Lin方案，模式云微物理过程的选择比模式分辨率对模拟效果的影响更大。黄海波等[5对新疆的一次暴雨过程进行了研究，分析了不同云微物理方案与不同水平分辨率对模式降水预报的影响，认为在 $4 5 \mathrm { k m }$ 和 $1 5 \mathrm { k m }$ 的水平分辨率下，WSM3方案总体模拟效果最好，其次为WSM5方案，Kessler方案效果最差。

上述研究从宏观角度（总降水量、降水落区等）对比分析了云中不同的微物理过程对降水预报的影响，但基于卫星获得的云和亮温资料对不同云微物理参数化方案在新疆地区的适用性的研究较少。本研究基于CloudSat卫星、FY-2E 静止卫星及降水量等观测资料，分析不同云微物理参数化方案对新疆区域云微物理特征的再现能力，为新疆业务预报系统选取合理的WRF模式云微物理参数化方案，以及进一步提高新疆区域云微物理过程参数化数值预报能力提供依据。

# 1资料与模式

# 1.1资料

选用CloudSat卫星2B-CWC-RO 数据集中云冰相粒子含量(IWC)资料、定标在 $8 6 . 5 ^ { \circ } \mathrm { ~ E ~ }$ 的FY-2E卫星的云顶亮温资料，及区域自动气象站每1h降水资料与模式输出结果进行对比分析。

CloudSat卫星是第一颗利用主动毫米波雷达在全球范围内观测研究云量、云的分布和垂直结构、辐射特性以及降水信息的卫星。卫星上的有效载荷主要是 $9 4 \mathrm { G H z }$ （ $3 \mathrm { m m }$ 波）云廓线雷达(Cloud Profiling Radar，CPR）。CPR 的敏感性约是天气雷达的 1000 倍，因此，可用来探测更小的液态水粒子和冰晶粒子[。采用该雷达提供的2B-CWC-RO 数据集中冰相粒子含量来检验分析4种云微物理参数化方案模拟的云微物理结构。

风云二号气象卫星(FY-2)是我国自行研制的第一代地球同步轨道气象卫星，其提供的云顶亮温是卫星红外探测通道获取的云顶和无云或少云地区地球表面的向外辐射，以相当黑体亮温（TBB）表征，是形成云图和多种增强显示云图最原始的观测资料[7]。

# 1.2模式及个例概况简介

利用新疆区域自动气象站资料，结合CloudSat卫星2B-CWC-RO，在新疆地区发生强降雨天气过程期间CloudSat卫星轨迹线经过降水中心的天气过程进行筛选分析。其中一个筛选个例由典型的中亚低涡引发，该个例发生在2015年6月14—19日，前期乌拉尔山为低槽区，新疆受高压脊控制， $5 0 0 \mathrm { { h P a } }$ 欧亚范围为两槽两脊经向环流。14一16日，乌拉尔山低槽东移南下，造成北疆大部出现降水天气。本研究对2015年6月14日18:00UTC到2015年

6月15日18:00UTC的模拟效果进行分析， $5 0 0 \mathrm { { h P a } }$ 形势场演变见图1。根据马淑红等的研究结果8]，新疆大部分区域性强降水是由中亚低涡引发的，这也是本文选用中亚低涡降水个例的原因。根据《新疆降水概论》，规定中亚低涡为 $5 0 0 \mathrm { { h P a } }$ 图低值中心位于 $4 0 ^ { \circ } \ \sim 6 0 ^ { \circ } \ \mathrm { ~ N ~ }$ ，$6 0 ^ { \circ } \ \sim 9 0 ^ { \circ }$ E，存在两条以上的闭合等值线，维持时间 $4 8 \mathrm { h }$ 以上的冷性涡旋系统。根据中亚低涡对新疆的影响，可以分为干涡和湿涡两种，干涡主要造成新疆的大风、降温以及长时间的低温天气，降水较弱，有时也不会造成影响，而湿涡则会造成新疆明显的降水天气[9-]。

![](images/a0da98a4a360788b979484bba85cc1be675d9efd62b2d5f2d3e894e9434db676.jpg)  
图 $1 5 0 0 \mathrm { { h P a } }$ 逐6h天气形势图  
Fig.1Every 6 h weather map in four cases

采用中尺度数值天气模式WRF3.8进行模拟，模式采用两层嵌套网格，其中，粗网格区覆盖了整个中亚地区，水平分辨率为 $9 ~ \mathrm { k m }$ ，记为D01；细网格区覆盖了新疆地区，水平分辨率为 $3 \mathrm { k m }$ ，记为D02。模拟嵌套划分如图2所示。垂直方向为38层，模式层顶为 $5 0 \mathrm { { h P a } }$ 积分步长为 $6 0 ~ \mathrm { s }$ ，模式初值和侧边界条件采用每6h的EC再分析资料，主要物理过程与参数化方案使用ACM2边界层方案[12]，在 $9 \mathrm { k m }$ 分辨率网格区使用Kain-Fritsch积云对流方案[13-14]，该方案在一定的闭合假设条件下，通过一组参数定义对流激发函数，当模式大气满足这一组参数后激发对流运动，可以更真实地模拟中尺度系统的内部结构和演变特征[5]，如RRTM长波辐射方案、Dudhia 短波辐射方案[4]，RevisedMM5Monin-Obukhov 近地层方案和 Noah陆面模式，云微物理参数化方案分别选用 $\mathrm { L i n } ^ { [ 1 6 ] }$ 、WSM6[17]、Thompson[18]和 WDM6[19]方案。

![](images/5736ff0399acecf06dd67448d9be0935b3d53c1a9ea4145feb978d2658339a22.jpg)  
图2WRF模式模拟区域Fig.2Themodel domains

# 1.3云微物理过程参数化方案

WRF 模式包含14种云微物理过程参数化方案，根据描述水成物的粒子谱分布描述函数不同，可以将参数化方案分为单参数方案、双参数方案和三参数方案。单参数方案固定截距$N _ { 0 }$ ，粒子谱谱型的演变由斜率入决定，入由水成物比质量决定。双参数方案引入了数浓度方程，使谱型由截距 $N _ { 0 }$ 和斜率入两个参数决定，谱型参数为常数。三参数方案的粒子谱分布由谱型参数 $\mu$ 、截距 $N _ { 0 }$ 和斜率 $\lambda$ 决定，需要3个方程求解，但实际的参数化过程中只有比质量和数浓度方程，因此，实际参数化过程的谱型常定为常数[20]。本文选用WSM6和Lin作为单参数方案，WDM6和 Thompson 方案作为双参数方案。

# 1.3.1Lin方案

该解决方案来自Purdue的云模型。考虑到6种水成物，包括云水、水汽、云冰、雨、雪和霰。在参数化方案中，各种水物质生产的算法主要来自于Lin[16]和Rutledge[21]等，但在饱和度调整和冰晶沉降方面做了一些修改。Lin方案考虑了冰、雪和霰的过程，这是WRF 中一个比较全面的方案，高分辨率实时数值预报也可以很好地应用。

# 1.3.2WSM6方案

WSM6是在WSM3和WSM5的基础上改进而来，增加了霰的质量比浓度预报变量以

及相关物理过程，包含霰在内的六类水成物。

# 1.3.3 Thompson 方案

Thompson 方案是改进后的 Reisner 方案。该方案主要针对冻雨事件的预测和一套微物理方案的设计，以提高飞机的安全性。这些包括预测变量，如冰晶浓度和6种水成物质。但Thompson 方案中存在低估流动区域中冰晶数量，但在微观物理过程中高估了雪的总量的问题。

# 1.3.4WDM6方案

WDM6方案是在单参数方案WSM6的基础上改进而来，预报水汽、云水、雨水、云冰、雪和霰粒子混合质量比，同时预报云水和雨水数浓度，并对云凝结核进行预报。

# 1.4检验方法

TS 评分和 BIAS 评分是目前使用较多的降水预报水平标准评估模式之一，本文将模式模拟的结果采用反距离权重法插值到站点上，然后对模拟结果做统计检验。根据新疆 $1 2 \mathrm { h }$ 累积降水标准将 $0 . 1 { \sim } 5 . 0 \mathrm { m m }$ 降水称为小雨， $5 . 1 { \sim } 1 0 . 0 \mathrm { m m }$ 降水称为中雨，大于 $1 0 . 1 \mathrm { m m }$ 的大雨和暴雨统称为大到暴雨[22]。

TS 评分的公式为[3]:

$$
\mathrm { T S } = { \frac { N _ { A } } { N _ { A } + N _ { B } + N _ { C } } }
$$

式中， $N _ { A }$ 为预报降水且预报正确的站点数（站点和预报都出现某量级降水的站点数）；$N _ { B }$ 为空报站点数（预报出现某量级的降水而观测非此量级降水的站点数）； $N _ { C }$ 为漏报站点数（观测出现某量级的降水而预报非此量级降水的站点数）。所以，TS评分值显示有降水时模式预报某一等级降水的正确率，其值介于0和1之间，当预报的降水区域的降水量级与观测一致时， $\mathrm { T S } { = } 1$ ，预报效果好，而TS 越小，模拟效果越差3]。

BIAS评分的公式为：

$$
{ \mathrm { B I A S } } = { \frac { N _ { A } + N _ { B } } { N _ { A } + N _ { C } } }
$$

BIAS 评分反应了达到某一阈值的降水预报范围的大小，检验降水落区的预报效果好坏，越接近于1预报效果越好。本文Bias 的检验阈值按照新疆 $1 2 \mathrm { ~ h ~ }$ 累积降水标准定为 $0 . 1 ~ \mathrm { m m }$ 、$5 . 1 \mathrm { m m }$ 和 $1 0 . 1 \ \mathrm { m m }$ 。

为便于突出模式对天山山区及北疆降水预报性能的检验，所选的检验站点均在 $4 2 ^ { \circ } \mathrm { ~ N ~ }$ 以北。

# 2 模拟结果分析

# 2.1 降水

在 $3 ~ \mathrm { k m }$ 水平分辨率上，采用不同云微物理方案模拟的 $4 2 ^ { \circ } \mathrm { N }$ 以北的新疆区域自动气象站平均降水时间序列图（图3），可以看出模式经过6h的 spin-up 时间后，采用的4种云微物理参数化方案都能较好地模拟出降水天气过程的演变趋势，尤其是 $6 \mathord { \sim } 1 8 \mathrm { h }$ 期间降水趋势与观测十分相似，而 $1 8 \sim 2 4 \mathrm { h }$ 的预报与观测偏差较大，因此,模式的 $1 2 \mathrm { h }$ 累积降水量的检验使用2015年5月15日00:00—12:00UTC时间段。

![](images/b6df025c6a1998d78b3f6193283351f36571dc2f9158757d91ba7d216a5b3400.jpg)  
图3区域自动气象站及4种云微物理参数化方案每小时降水量时间序列  
Fig.3 Hourly precipitation time series of area automatic stations and four kinds of cloud microphysical parameterization schemes

图4为2015年6月15日00:00到12:00UTC的 $1 2 \mathrm { ~ h ~ }$ 累计降雨分布，从图4可以看出Lin 方案、WSM6方案和 Thompson方案均在空间分布特征上与区域自动站观测数据十分相似，Thompson方案和WDM6方案没有模拟出哈密地区的降雨，WSM6方案和WDM6方案均没有模拟出阿勒泰西部的降雨，WDM6方案没有模拟出北天山一带的降雨，四种方案均在昌吉西南部存在较大强度的空报。

![](images/1c45f811d040336b52866055bf1d3dbd07efeb87bf4533d66668b8845cf607f4.jpg)  
新S(2018)041号

# 图4区域自动气象站及4种云微物理参数化方案模拟2015年6月15日00:00—12:00UTC12h累计降雨分布

Fig $. 4 1 2 \mathrm { h }$ accumulated precipitation of area automatic stations and four cloud microphysical parameterization schemes from 00:00-12:00UTC15 June 2015

![](images/84efc9f74cd986121ea51057c3796b9bc2e1647b53ba60d1ad2021b538a1a7cb.jpg)  
图52015年6月15日00:00—12:00UTC12h累积降水概率分布

Fig. $5 1 2 \mathrm { h }$ accumulated precipitation probability distribution from OO:0o-12:00 UTC15 June 2015

对比不同降水等级出现的概率分布（图5），发现WDM6方案的小雨和中雨出现概率偏低，这与Hong 等[23]与邓琳等[24]试验结果一致 ；Thompson 方案的弱降水出现概率高于其他3种云微物理参数化方案，且与实测最相近。

对各降水等级进行TS 评分(图6)的计算统计发现，Thompson 方案对小雨和中雨的预报效果最好，其他3种方案均有不同程度的漏报。 $9 \mathrm { k m }$ 分辨率的结论与 $3 \mathrm { k m }$ 分辨率的结论一致。整体上，4种云微物理参数化方案均对小雨的预报效果最好，中雨次之，大到暴雨的模拟效果最差，仅有 Thompson 方案在小雨和中雨模拟上有明显优势。将各参数化方案模拟结果与地面站观测结果做相关性统计(表1)，平均TS 评分较低的个例其相关系数也较低。

从BIAS评分（表2）可以看出，在 $3 \mathrm { k m }$ 和 $9 \mathrm { k m }$ 分辨率下，模式对小雨的预报范围与实际情况是最为接近的，其中 Thompson 方案模拟效果最好，其次是Lin 方案，最差的是WDM6方案。对中雨范围有明显的过度预报，在 $3 \mathrm { k m }$ 分辨率下，Thompson方案的模拟效果最好， $9 \ \mathrm { k m }$ 分辨率下WSM6模拟效果最好。对大到暴雨的预报效果是最差的， $9 \ \mathrm { k m }$ 分辨率下的预报效果优于 $3 \mathrm { k m }$ 分辨率。

TS 评分和BIAS 评分所得结论基本一致，整体上，模式体现了较好的模拟结果，总的来说 Thompson方案模拟效果最好，WDM6方案最差。

![](images/c38611a859b20ea033aa625abdffb91019b03fbd7a28d1f2736178d10831d811.jpg)  
图 $6 3 \mathrm { k m }$ 和 $9 \mathrm { k m }$ 分辨率不同降水等级2015年6月15日00:00—12:00UTC12h累积降水TS评分 Fig. 6 TS score of $1 2 \mathrm { h }$ accumulated precipitation with different precipitation levels with different $3 \mathrm { k m }$ resolution and $9 \mathrm { k m }$ resolution from 00:00-12:00UTC15 June 2015

# 表14种云微物理参数化方案模拟的2015年6月15日00:00—12:00UTC $1 2 \mathrm { h }$ 累积降水与区域自动气象站实况的相关系数

Tab.1 Correlation coeficient between the simulated and obserbed precipitation Correlation coefficient table between $1 2 \mathrm { h }$ cumulative precipitation and regional automatic weather station simulated by four cloud microphysical parametric schemes from O0:00-12:00 UTC 15 June 2015   

<html><body><table><tr><td>分辨率</td><td>云微物理量</td><td>相关系数</td></tr><tr><td rowspan="6">3 km</td><td>Lin</td><td>0.16</td></tr><tr><td>WSM 6</td><td>0.25</td></tr><tr><td>Thompson</td><td>0.25</td></tr><tr><td>WDM 6</td><td>0.19</td></tr><tr><td>Lin</td><td>0.36</td></tr><tr><td>WSM 6</td><td>0.35</td></tr><tr><td>Thompson</td><td></td><td>0.42</td></tr><tr><td></td><td>WDM 6</td><td>0.36</td></tr></table></body></html>

表 $2 3 \mathrm { k m }$ 和 $9 \mathrm { k m }$ 分辨率不同降水等级2015年6月15日00:00—12:00UTC12h累积降水BIAS评分 Tab.2 BIAS score of $1 2 \mathrm { h }$ accumulated precipitation with different precipitation levels with different $3 \mathrm { k m }$ resolution and 9 km resolution from O0:00-12:00 UTC 15 June 2015   

<html><body><table><tr><td>分辨率</td><td>阈值 方案</td><td>小雨（0.1mm）</td><td>中雨（5.1 mm）</td><td>大到暴雨（10.1 mm）</td></tr><tr><td>3km</td><td>Lin</td><td>0.82</td><td>1.54</td><td>0.10</td></tr><tr><td rowspan="6">9 km</td><td>WSM 6</td><td>0.77</td><td>1.50</td><td>0.20</td></tr><tr><td>Thompson</td><td>0.91</td><td>1.36</td><td>0.05</td></tr><tr><td>WDM 6</td><td>0.59</td><td>2.00</td><td>0.15</td></tr><tr><td>Lin</td><td>0.93</td><td>1.63</td><td>0.35</td></tr><tr><td>WSM6</td><td>0.85</td><td>1.30</td><td>0.30</td></tr><tr><td>Thompson</td><td>0.98</td><td>1.54</td><td>0.25</td></tr><tr><td></td><td>WDM 6</td><td>0.68</td><td>1.41</td><td>0.25</td></tr></table></body></html>

# 2.2云宏微观物理特征比较分析

# 2.2.1 云顶亮温

为了检验模式对云顶亮温的模拟效果，参考RTTOV 辐射传输模式对辐射亮温进行计算。假设大气处于局地热力平衡的情况下，不考虑气体的散射，大气层顶向上的辐射量可如公式（1）。

$$
L ( \nu , \theta ) = ( 1 - N ) L _ { \mathrm { C l r } } ( \nu , \theta ) + N L _ { \mathrm { C l d } } ( \nu , \theta )
$$

式中： $\nu$ 是卫星观测通道的频率; $\theta$ 是观测角度； $L _ { \mathrm { C l r } } ( \nu , \theta )$ 和 $L _ { \mathrm { C l d } } ( \nu , \theta )$ 表示天顶角为0时，卫星接收到的频率为v的晴空辐射和云区辐射； $N$ 表示云量。

首先分析各参数化方案对云顶亮温(TBB)模拟的分布情况，在云区中，黑体亮温一般≤0℃，且TBB越低，说明云顶越高，云层越厚，云团内对流发展越旺盛，降水潜势越大[6]。据统计， $8 7 . 3 \%$ 以上的暴雨发生在 ${ \cdot 6 3 \sim - 8 0 }$ ℃的云顶亮温区域，强降雨区总是位于云团前进的方向，而云团后部降雨较小[26]。

由 FY-2E卫星每小时云顶亮温分布图可以看出，2015年6月14日，伊犁河谷上空有一中心云顶亮温为 $. 4 4 . 5 ~ ^ { \circ } \mathrm { C }$ 的云系，云系向东北方向移动，途径博尔塔拉蒙古自治州、塔城，在15日06:00时从塔城北部离开新疆地区，在上述3个地区造成降雨，其中伊犁部分地区6h累积降雨量达暴雨级别（ $> 2 4 . 1 \ \mathrm { m m }$ ）。14日，巴音郭楞蒙古自治州大部分地区与和田部分地区上空被云顶亮温最低为 ${ \bf \nabla } \cdot 4 5 \ ^ { \circ } \bf { C }$ 的大片云系覆盖，云系向东北方向移动，在15 日13:15 UTC，从巴音郭楞蒙古自治州与哈密地区的交界处离开新疆，从降水场并未观察到此处有大范围降水，这是由于此区域自动气象站站点稀疏，卫星资料则弥补了常规资料这一缺点。6月15日，先后从伊犁和阿克苏地区进入两个云系，均向东北方向沿天山移动并发展旺盛，最低云顶亮温为 $. 4 9 ^ { \circ } \mathrm { C }$ ，造成了天山一带大范围降水，伊犁部分地区00:00一12:00累积降水达暴雨（ $> 2 0 . 1 \ \mathrm { m m }$ ），随后云团沿天山向东移动，在北天山一带造成大范围降雨。

从WRF模式模拟的每小时云顶亮温分布图发现，4种云微物理参数化方案模拟的云顶亮温分布图均与FY-2E 卫星观测十分相似，在数值上均低于观测值，导致大部分地区模拟的降水高于实测。

![](images/672e010fa3a6b13ed62dfe40246d745dd7124c04087c5ea130d5584f4383e6b8.jpg)  
图7FY-2E卫星在2015年6月15日10:15UTC、11:15UTC和12:15UTC观测的云顶亮温与4种云微物理参数化方案在06:00UTC、07:00UTC和08:00UTC模拟结果分布图Fig.7 Cloud top temperature observed (10:15 UTC,11:15 UTC and 12:15 UTC15 June 2015)byFY-2E sateliteand simulated (10:00 UTC,11:00 UTC and 12:00 UTC 15 June 2015) by four cloud microphysics

parameterization

在模拟开始的 $1 5 \sim 1 8 \mathrm { ~ h ~ }$ ，即2015年06月15日10:00－12:00，区域自动气象站资料平均每小时降水量不断增加，在12:00UTC 有一个高值，然后下降。因此，选用FY-2E卫星在 2015年6月15日10:15UTC、11:15UTC、12:15UTC 观测的云顶亮温与4种云微物理参数化方案在同日10:00 UTC、11:00UTC、12:00UTC模拟结果进行对比（图7），结果发现 4 种参数化方案均没有模拟出阿克苏地区的云顶亮温低值区，导致4 种参数化方案均没有还原出阿克苏地区东部的降水。4 种参数化方案在喀什和克孜勒苏柯尔克孜自治州模拟出的云系，云顶亮温小于 ${ \boldsymbol { - 3 0 } } \ { \boldsymbol { \circ } } { \boldsymbol { \mathrm { C } } }$ 的区域远大于观测值，导致4种方案在克孜勒苏柯尔克孜自治州南部地区模拟的降水大于实况。

# 2.2.2 云冰水含量

图8a是2015年6月15日07:48时CloudSat卫星沿卫星轨道在伊犁强降水地区监测到的冰水含量-高度剖面图，卫星扫描轨迹为 $4 0 . 0 0 { \sim } 4 5 . 0 1 ^ { \circ } \mathrm { N }$ ， $8 1 . 2 0 ^ { \circ } { \sim } 8 2 . 8 8 ^ { \circ } \mathrm { E }$ 。可见，沿卫星轨道在 $5 \sim 1 2 ~ \mathrm { k m }$ 高度上存在明显云系，卫星监测的冰水含量主要分布在 $4 0 . 1 { \sim } 4 1 . 3 ^ { \circ } \mathrm { N }$ ，$8 2 . 4 { \sim } 8 2 . 7 ^ { \circ } \mathrm { E } , 4 2 . 2 { \sim } 4 3 . 4 ^ { \circ } \mathrm { N } , 8 1 . 8 { \sim } 8 2 . 2 ^ { \circ } \mathrm { E }$ 及 $4 4 . 0 { \sim } 4 5 . 0 ^ { \circ } \mathrm { N }$ ， $8 1 . 2 { \sim } 8 1 . 4 ^ { \circ } \mathrm { E }$ 。在 $4 2 . 2 { \sim } 4 3 . 4 ^ { \circ } \mathrm { N }$ $8 1 . 8 \sim 8 2 . 2 ^ { \circ } \mathrm { E }$ 范围内云系发展最为旺盛，对流强烈，云系中心冰水含量最高达 $1 \ 6 4 0 \ \mathrm { m g \cdot m \bar { } }$ 3,该地区出现较大范围降水,与地面实际观测降水区域相吻合，此时降水量最高为 $1 0 . 3 \mathrm { m m }$ h1。

图 $8 \mathrm { b } \sim 8 \mathrm { e }$ 分别采用Lin、WSM6、Thompson 和WDM64 种云微物理参数化方案模拟得到的冰水含量-高度剖面图。4种参数化方案模拟的冰水含量都聚集在 $4 2 . 0 { \sim } 4 3 . 3 ^ { \circ } \mathrm { N } , 8 2 . 1 { \sim }$ $8 2 . 7 ^ { \circ } \mathrm { E }$ 范围内，与CloudSat卫星一致，但4种参数化方案都没有模拟出位于 $4 0 . 3 { \sim } 4 1 . 1 ^ { \circ } \mathrm { N }$ $8 2 . 4 \sim 8 2 . 7 ^ { \circ } \mathrm { E }$ 和 $4 4 . 0 { \sim } 4 5 . 0 ^ { \circ } \mathrm { N }$ ， $8 1 . 2 { \sim } 8 1 . 4 ^ { \circ } \mathrm { E }$ 的云系。4种方案模拟的冰水含量分布在 $1 2 \mathrm { k m }$ 以下，与地形线相接，这是由于CloudSat卫星可以准确地探测到云，并给出云内冰水含量，但模式给出的是 $0 { \sim } 1 5 \mathrm { k m }$ 整层大气的冰水含量。从垂直空间形态上，Thompson 方案模拟的冰水含量与观测值最相近，Lin方案与观测值相差最远。

为了探究各参数化方案在高度上对冰水含量的模拟，本文将剖面图所示范围（ $4 0 . 0 0 \sim$ $4 5 . 0 1 ^ { \circ } \mathrm { N }$ ， $8 1 . 2 0 { \sim } 8 2 . 8 8 ^ { \circ } \mathrm { E }$ ）的每一高度上冰水含量做平均，得到冰水含量-高度的廓线图(图8f)从CloudSat卫星观测数据的廓线可以看出，在所关注的强降水范围内云中冰水含量分别在 $6 . 5 \ \mathrm { k m }$ 和 $9 . 4 ~ \mathrm { k m }$ 处有峰值，平均冰水含量分别达到 $1 0 4 . 5 ~ \mathrm { m g } { \cdot } \mathrm { m } ^ { - 3 }$ 和 $1 0 2 . 2 ~ \mathrm { m g } { \cdot } \mathrm { m } ^ { - 3 }$ 。四种参数化模拟结果中，WSM6方案和Thompson方案在两个高度处有较明显的峰值，WSM6方案在 $4 . 3 \mathrm { k m }$ 高度处冰水含量为 $1 5 0 . 1 9 \mathrm { m g } { \cdot } \mathrm { m } ^ { - 3 }$ ，在 $8 . 7 \ \mathrm { k m }$ 高度处冰水含量为 $4 2 . 8 7 \mathrm { m g } { \cdot } \mathrm { m } ^ { - 3 }$ ，Thompson 方案在 $4 . 1 ~ \mathrm { k m }$ 高度处冰水含量为 $1 7 4 . 4 4 ~ \mathrm { m g } { \cdot } \mathrm { m } ^ { - 3 }$ ，在 $7 . 9 ~ \mathrm { k m }$ 高度处冰水含量为

$1 6 8 . 1 1 ~ \mathrm { m g } { \cdot } \mathrm { m } ^ { - 3 }$ ，可见，两种参数化方案冰水含量峰值所在高度均比观测值低。在 $6 . 5 \ \mathrm { k m }$ 高度处，Lin方案、WSM6方案、Thompson方案和WDM6方案模拟的冰水含量分别为 53.83$\mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ 、 $7 5 . 9 3 \ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ 、 $1 5 5 . 4 9 \mathrm { m g } { \cdot } \mathrm { m } ^ { - 3 }$ 和 $9 9 . 8 7 ~ \mathrm { m g } { \cdot } \mathrm { m } ^ { - 3 }$ ；在 $9 . 4 \mathrm { k m }$ 高度处，Lin方案、WSM6 方案、Thompson方案和WDM6方案模拟的冰水含量分别为 $3 3 . 2 3 \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ 、 $4 0 . 4 3 \mathrm { m g } { \cdot } \mathrm { m } ^ { - 3 }$ 、$1 3 6 . 3 4 ~ \mathrm { m g } { \cdot } \mathrm { m } ^ { - 3 }$ 和 $3 7 . 2 6 ~ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ 。综上所述，Thompson 方案模拟的冰水含量在垂直高度上的分布最接近观测值。由于只平均了4种参数化方案中CloudSat卫星划过范围内的各高度层的冰水含量，样本数量少，导致各高度上冰水含量廓线图不平滑，但仍然可以看出，Thompson方案在冰水含量数值上和高值区的高度上模拟效果最好，Lin方案模拟结果中的冰水含量明显低于其他3种参数化方案和观测值，模拟效果最差。

为了观察4种参数化方案模拟空间内大气冰水含量随高度的变化情况，本文将 $3 \mathrm { k m }$ 网格范围内每个高度上的冰水含量进行平均，得到了区域平均冰水含量-高度廓线图（图 $8 \mathrm { g }$ ）区域平均的冰水含量-高度廓线图补充了 $3 \mathrm { k m }$ 高度以下的冰水含量数据，可以看出Lin 方案模拟出的冰水含量明显低于其他三种参数化方案，WSM6方案与WDM6方案的冰水含量-高度廓线图基本重叠。其中，Lin 方案冰水含量最高值为 $2 7 . 5 9 \mathrm { m g } { \cdot } \mathrm { m } ^ { - 3 }$ ，发生在 $4 . 3 \mathrm { k m }$ 高度上。WSM6方案、Thompson 方案和WDM6方案冰水含量最高值均发生在 $4 . 9 \mathrm { k m }$ 高度，最高值分别为 $6 9 . 8 9 \mathrm { m g } { \cdot } \mathrm { m } ^ { - 3 }$ 、 $7 5 . 7 2 \mathrm { m g } { \cdot } \mathrm { m } ^ { - 3 }$ 和 $7 0 . 3 2 \mathrm { m g } { \cdot } \mathrm { m } ^ { - 3 }$ 。

![](images/f5f73acb523759ad2581b2837bb5e39a9100677dc64f195586dec88ff02b1c35.jpg)  
图8CloudSat卫星在2015年6月15日07:48UTC观测与4种参数化方案在08:00UTC时模拟的冰水含量

Fig.8 The cloud ice contend observed (07:48 UTC 15 June 2015) by CloudSat satellite and

# 3结论

利用每6h一次，空间分辨率为 $1 ^ { \circ } \times 1 ^ { \circ }$ 的ECMWF再分析资料作为初始场和边界条件，使用WRF中尺度数值模式对中亚低涡造成的新疆地区暴雨个例进行模拟，以区域自动气象站每小时降水数据为观测值，从宏观尺度（ $^ { 1 2 \mathrm { ~ h ~ } }$ 累积降水场、每小时降水率）对已有WRF 版本中不同云微物理参数化方案的模拟表现进行评估。进一步结合FY-2E卫星逐时的TBB 资料、CloudSat卫星2B-CWC-RO 数据产品中云冰水含量数据，对中亚低涡暴雨个例进行云内微物理特征模拟的对比分析，得出模式中表现较优的云微物理参数化方案，主要结论如下：

（1）在每小时降水率上，中尺度天气模式WRF在进行 $2 4 \mathrm { h }$ 模拟时， $6 \mathrm { \sim } 1 8 \mathrm { h }$ 的模拟结果相对贴近实测。没有哪一种云微物理参数化方案优于其他方案的绝对优势。

（2）Thompson方案在小雨（ $0 . 1 \sim 5 . 0 \mathrm { m m }$ ）和中雨 $\left( 5 . 1 \sim 1 0 . 0 \mathrm { m m } \right)$ ）的预报模拟中占优势，模拟结果中云系和雨区形状位置均与实况最为接近，其他3种云微物理参数化方案均在不同程度上存在漏报情况，在垂直高度上，Thompson 方案模拟出的冰水含量在高度上的分布情况与实况最为接近。但云系中心云顶亮温低值区过大，云顶亮温数值过低，云中冰水含量也高于实况和其他3种云微物理参数化方案。

（3）与CloudSat卫星数据对比，Thompson 方案在冰水含量数值上和高值区的高度上模拟效果最好，Lin方案模拟结果中的冰水含量明显低于其他3种参数化方案和观测值，模拟效果最差。垂直高度 $3 ~ \mathrm { k m }$ 区域平均冰水含量的分布情况看，4种云微物理参数化方案的冰水含量均集中在 $4 . 2 \mathrm { k m }$ 高度，而CloudSat卫星在4个样本处采集到的冰水含量均集中在大于 $5 . 5 \mathrm { k m }$ 的高度。数值上，Thompson方案模拟出的冰水含量最大，WSM6方案与WDM6方案的冰水含量-高度廓线图几乎重合，Lin方案的冰水含量明显低于观测和其他3种参数化方案。

建议今后关于云冰的模拟也可使用 NCAR 的 UPP（Unified Post Processing System）后处理软件，对WRF 模式输出进行后处理，使用UPP 输出的云冰可以直接与CloudSat 的观测值进行对比。

# 参考文献（References）：

[1]张扬,楚新正,杨少敏,等.近 56a新疆北部地区气候变化特征[J].干旱区研究,2019,36(1):212-219.[Zhang Yang,ChuXinzheng,YangShaominetal.ClimatechangeinorthXinjiangirecent56years[J]AridZoneResearch,O19,6(1):219.][2]彭军,周雪英,赵威,等.新疆巴州“6·4”罕见大暴雨中尺度特征分析[J].沙漠与绿洲气象，2016，10(1):68-75.[Peng Jun,Zhou

Xueying,ZhaoWeietsosalearacteristsofaetoetialaiangoliongolutonomousrefecureJeertad Oasis Meteorology2016,10(1):68-75.]

[3] 朱格利,林万涛,曹艳华,等.用 WRF 模式中不同云微物理参数化方案对华南一次暴雨过程的数值模拟和性能分析[J].大气科 学,2014,38(3):5-5ZuGeliLinWantaoCaoYanhuaetalNumericalsimulationofaainstoeventoversouthchinabyusing various cloudmicrophysicsparameterzationschemes inWRFmodelanditsperformanceanalysis[J].ChineseJoualofAtospheric Sciences,2014,38(3):513-523.]   
[4]董昊,徐海明,罗亚丽,等.云凝结核浓度对WRF模式模拟胞线降水的影响:不同云微物理参数化方案的对比研究[J].大气科学， 2012,36(1):145-169.DongHaoXuHamingLuoYalietalEectsofloudodesationucleicocentrationopreiiation convectionpermitingsimulationsofasqualineusing WRFmodel:sensivittooudmicrophysicalschemes[J].ChineseJoualof Atmospheric Sciences,2012,36(1):145-169.]   
[5] 黄海波,陈春艳,朱雯娜,等.WRF 模式不同云微物理参数化方案及水平分辨率对降水预报效果的影响[J].气象科 技,2011,39(5):52-6uangHibCheuyn,Zu Wenaetal.Wea.Ipactsofdieretloudicopsicalpro horizontalresoutiosofodelopreciptionfrcasteect[J]eteorologicalieneadTchology2139(5):-6 [6]周毓荃,赵姝慧.CloudSat卫星及其在天气和云观测分析中的应用[J].南京气象学院学报,2008,31(5):603-614.[Zhou Yuquan,Zhao ShuuiCloutsateliteditsaineadoudetioJ]asctiosfmospicies()6 614.]   
[7]游景炎.云降水物理和人工增雨技术研究[M].北京:气象出版社,1994:202-205.[You Jingyan．Study on physics and artificial precipitation enhancement technologyof cloud precipitation[M].BeiJing: China Meteorological Press,1994:202-205.]   
[8]马淑红,席元伟.新疆暴雨的若干规律性[J].气象学报,1997,55(2):239-248.[Ma Shuhong,Xi Yuanwei.Some regularitiesof storm rainfallin XinJiang,China[J].Acta Meteorologica Sinica,1997,55(2):239-248.]   
[9]杨莲梅,李霞,张广兴,等.新疆夏季强降水研究若干进展及问题[J].气候与环境研究,2011,16(2):188-198.[Yang Lianmei,Li Xia,ZhangGuangxingetal.SomedvancesandproblemsinthesudyofheavyraininXinjiang[J].ClimaticadEnvionmentalResearch, 2011,16(2):188-198.]   
[10]杨莲梅,关学锋,张迎新,等.亚洲中部干旱区降水异常的大气环流特征[J].干旱区研究,2018,35(2):249-259.[Yang Lianmei,Guan Xuefeng,ZhangYinin,etaAmospricilationaracteristsofpreiiationoalyinridiointralAsia[Jidoe Research,2018,35(2):249-259.]   
[11]Hu XM,NielsengamoJW,ZhangF,etal.Evauationofthe planetaryboudarylyerschemesintheWRFmodel[J].Joalof Applied Meteorology & Climatology,2010,49(9):181-1844.   
[12]Dudhia J.Numerical Studyofconvectionobserved duringthewinter monsoon experiment using a mesoscaletwo-dimesional model[J]1. Journal of Atmospheric Sciences,1989,46(20):3077-3107.   
[13]KainJS,FritschM.Convectiveparameterzationfomesoscalemodels:theKain-Fritschscheme[J].MeteorologicalMoograps, 1993,24(46):165-170.   
[14]Kain,JohS.eKaiFrisovctiverameterzatio:adate[J].Joualofppledeteorology4,4():7181. [15]张大林．各种非绝热物理过程在中尺度模式中的作用[J].大气科学,1998,22(4):548-561[Zhang Dalin.Roles ofvarious diabatic physical processes in mesoscale models[J].Chinese Journal of Atmospheric Sciences,1998,22(4):548-561.]   
[16]LinYL,FarleyRDrvillHD,etalBkpaameterzatioofthesofeldinododelJ].Joualofimatedld Meteorology,1983,22(6):1065-1092.   
[17]LimKSS,HongSY.Developmentofanefectivedouble-momentcloud mcrophysicsscheme ith prognosticcloudcondensation nuclei(CCN) for weather and climate models[J]. Monthly Weather Review,2010,138(138):1587-1612.   
[18]ThompsoGeld,asseRetal.Explicitrecastsfterprecipitatisingaproedulkcoi part I: implementationofanew snow parameterization[J].Monthly Weather Review,20o8,136(12): 5095-5115.   
[19]HogSY,LimKSS,LeeYH,etal.EvaluationoftheWRFdouble-moment6-classmicrophysicsschemeforprecipitating convection[J].Advances in Meteorology,2010,(2):185-194.   
[20]尹金方,王东海,翟国庆,等.区域中尺度模式云微物理参数化方案特征及其在中国的适用性[J].地球科学进展,2014,29(2):238-

249.[YinJinfng,WangDonghai,Zhaiuoigetal.Astudyofharacteristicsoftheloudmicrophsicalparametezationsin mesoscale models and itsapplicability to China[J].Advances in Earth Science,2014,29(2):238-249.]

[21]StevenA.RutledgeandPeterV.Hobs.The Mesoscaleand Microscale StructureandOrganizationofCloudsandPrecipitationin MidlatitudeCyclones.XI:ADiagnosticodelingStudyofPrecipitationDevelopmentinNarrowCold-FrontalRainbands[J].Joualof the Atmospheric Sciences,1984,41(6):2949-2972.

[22]肖开提·多莱特.新疆降水量级标准的划分[J].新疆气象,2005(3):7-8[Xiaokaiti·Duolaite.Formulationof precipitation intensity standard of Xinjiang[J].Bimonthlyof Xinjiang Meteorology,2005,28(3):7-8].

[23]HongSY,SunyLimKS,KiJH,etal.Sensitivitystudyofcloud-resovingconvectivesimulationswithWRFusingtwobulk microphysicalparameterzatios:ce-paseicrophsicsversussedimentatioects[J].JoualofAppledMeteoroogyandlitology 2009,48(1):61-76.

[24] 邓琳,端义宏,高文华,等.超强台风“威马逊”(2014)云微物理特征的模拟与对比分析[J].气象学报,2016,74(5):697-714.[Deng Lin,Duan Yihong,GaoWenhua,etal.Numericalsimulationandcomparisonofcloudmicrophysicalfeaturesofsupertyphoon Rammasun(2014)[J].Acta Meteorologica Sinica,2016,74(5):697-714.]

[25]谷晓平,王长耀,王汶,等.GMS5红外卫星云图参数化及在降水预测中的应用[J].遥感学报,2005,9(4):459-467.[Gu Xiaoping,Wang Changyao,WangWentarametezatiooffredtelitudimagynditsplicatioininallpedcationJJoalf Remote Sensing,2005,9(4):459-467.]

# Diagnostic analysis and numerical simulation of Central Asian vortex rainstorm based on CloudSat satellite data

Ding Ming-yuel 2 3， Wang Li $\cdot \mathrm { l i } ^ { 2 }$ ，Xin $\mathrm { Y u ^ { 1 } }$ ，Liu Qiong²， ChenYong-hang², Zhang Guang-xin1， Yang Lian-mei1， Liang Qian²， Huang Guan² Liu， Tong-qiang² (1.Institute of Desert Meteorology, China Meteorological Administration,Urumqi 83002, Xinjiang, China; 2. College of Environmental Science and Engineering,Donghua University, Shanghai 201620; 3.Beijing JinFeng HuiNeng Technology Company.,Lmited, Beijng 100176)

Abstract: A Central Asian Vortex rainstorm episode was simulated using WRF (Weather Research and Forecasting model, WRF) model based on ECMWF reanalysis data. Hourly precipitation data from regional automatic weather stations, CloudSat satelite 2B-CWC-RO data, FY-2D/E satellite TBB data are used to evaluate the applicability of Lin, WSM 6,Thompson and WDM 6 schemes in forecasting precipitation in Xinjiang. The results are as follows: Thompson scheme has an advantage in the simulation of the light rain ( $0 . 1 { \sim } 5 . 0 \mathrm { m m }$ )and the mid-rain ( $( 5 . 1 \sim 1 0 . 0 \ \mathrm { m m } )$ ). The distribution of the cloud top bright temperature simulated by four schemes is similar to FY-2E satellite observation,but the value is lower than that of FY-2E.According to the vertical distribution of the average ice-water content through the CloudSat observation, the Thompson scheme is the best in the numerical simulation of ice water content and the height in the high value region,and the simulation results of Lin scheme are the worst.According to the vertical distribution of the average ice water content in the $3 ~ \mathrm { k m }$ area, the cloud ice content simulated with Thompson scheme is the highest, WSM 6 scheme and the WDM 6 scheme is the second, and the ice-water content-height profile of the two are almost coincident, the Lin scheme is the lowest.

Keyword: WRF; Cloud microphysical parameter; CloudSat; FY-2； Central-Asia vortex;Rainstorm