# 祁连山国家公园森林地上碳密度遥感估算

宋洁1.2，刘学录1.2

1.甘肃农业大学资源与环境学院，甘肃 兰州730070；2.甘肃农业大学土地利用研究所，甘肃 兰州730070)

摘要：准确、及时地绘制森林地上碳密度图是了解全球碳循环的必要条件。虽然星载激光雷达（如ICESat/GLAS)数据已被广泛用于估算大尺度的森林地上碳密度分布,但地形坡度对GLAS提取冠层高度精度的影响往往限制了其在山区森林的应用。通过以祁连山国家公园为研究区域，结合GLAS数据、Landsat OLI(Operational land imagery)数据、样地调查数据,对祁连山地区进行区域性的森林地上碳密度估算。首先通过改进后的地形校正模型减小坡度对GLAS数据提取森林冠层高度精度的影响，使得更多的GLAS数据可用于后续的研究;其次将所建立的不同类型森林地上生物量估算模型与相关碳含量转换系数结合，得到GLAS激光光斑(脚印点)的森林地上碳密度;最后利用非参数化算法最大熵(MaxEnt)模型得到祁连山国家公园2018年森林地上碳密度分布图。结果表明：祁连山国家公园2018年平均森林地上碳密度为 $4 0 . 7 2 { \scriptstyle \pm 6 . 7 2 \ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } }$ ，总蓄积量为 $2 8 . 5 8 { \scriptstyle \pm 4 . 7 2 } \mathrm { T g }$ 海拔 $2 7 7 0 { \sim } 3 7 7 0 \ \mathrm { m }$ 区域的森林植被碳储量最大，且阴坡的碳储量明显高于阳坡。采用森林资源清查数据独立验证估算结果的准确性,模型估测均方根误差(Root mean square error,RMSE)为18.946$\mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ 。本研究结果可以为监测区域乃至国家尺度的森林碳储量变化以及制定可持续的森林管理措施提供依据。此外，本文所采用的方法在山区森林碳储量估算方面也具有较大的潜力。

关键词：星载激光雷达；LandsatOLI；森林地上碳密度；非参数化算法；祁连山

# 文章编号：

森林作为陆地生态系统中最大的碳库，在维持全球碳平衡和减缓气候变化方面发挥着重要的作用[1]。尽可能准确地估算森林地上碳密度及其空间分布，是理解全球碳循环以及制定减缓气候变化相关措施的关键[2]

遥感技术由于其具有覆盖范围广、重复观测能力强等特点，目前已成为大尺度森林地上碳密度估算的首选。特别是激光雷达遥感(Lightdetectionandranging,LiDAR），由于其具有直接测量森林垂直结构的能力，能够克服光学及微波遥感在高生物量地区出现的信号饱和问题，已被IPCC(TheInter-governmentalPanelonClimateChange)推荐为森林碳密度估算的有力工具3，并被广泛应用于目前的森林地上碳密度估算研究[4-5]。虽然机载激光雷达数据能够提供更高精度的森林垂直结构信息，但较高的使用成本和较大的数据处理量通常限制了其在大尺度的应用[。而星载激光雷达如搭载在冰、云和陆地高程卫星上的地球科学激光测高系统(GLAS)，虽然只能对激光光斑(脚印点)照射范围内的植被进行采样，但由于其全球范围的采样策略以及能够免费获取的数据”，目前已有众多学者将其与光学遥感数据相结合对森林地上生物量/碳储量进行估算并取得了较好的结果[8-10]

采用GLAS数据估算森林地上碳密度的一个关键问题是如何准确获取脚印点内森林垂直结构信息。由于GLAS波形对地形较为敏感，当坡度大于$1 0 ^ { \circ }$ 时,植被高度的估计精度明显降低[]。因此，许多森林碳储量估算研究去除了坡度较大地区的GLAS数据以避免误差[12-14],这造成了对山地森林碳储量的低估。而山地森林由于其受人为干扰相对

# 干吴区地理

较小，在维持碳贮存方面发挥着关键作用，且不同区域森林的固碳能力也存在差异，因此，提升GLAS数据在山区获取的森林垂直结构精度，尽可能准确地估算山地森林地上碳密度，补充以往研究对山地森林碳储量的低估，对理解区域乃至全球碳循环具有重要的意义。

祁连山作为我国西北干旱地区主要山系之一，是我国西部重要的生态屏障和固碳场所[15-16]。目前针对祁连山地区森林碳储量的估计仅限于较小地区的特定树种[17-18]。在此背景下,本研究结合GLAS数据、LandsatOLI数据和样地调查数据，对祁连山国家公园森林地上碳密度进行估算，旨在完善目前山地区域的森林碳储量现状分析，为监测区域乃至国家尺度的森林碳储量变化以及制定可持续的森林管理措施提供依据。

# 1 研究区概况

祁连山国家公园地理位置在 $3 6 ^ { \circ } 4 5 ^ { \prime } { \sim } 3 9 ^ { \circ } 4 7 ^ { \prime } \mathrm { N }$ $9 4 ^ { \circ } 5 0 ^ { \prime } { \sim } 1 0 2 ^ { \circ } 5 9 ^ { \prime } \mathrm { E }$ 之间，总面积 $5 . 0 2 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,其中甘肃省 $3 4 4 0 0 { \mathrm { k m } } ^ { 2 }$ ,青海省 $1 5 8 0 0 { \mathrm { k m } } ^ { 2 }$ （图1)。该地区海拔 $1 7 7 0 { \sim } 5 7 4 0 \ \mathrm { m }$ ，坡度 $0 ^ { \circ } { \sim } 5 8 ^ { \circ }$ 。属典型的温带大陆性山地气候,年平均降水量 $4 5 0 { \sim } 6 5 0 ~ \mathrm { m m }$ ,年平均气温 $- 3 { \it { \sim } } 1 \mathrm { ~ } \mathrm { \mathcal { C } }$ 。区内森林主要由青海云杉(Piceacrassi-folia）、祁连圆柏(Juniperusprzewalskii）、山杨(Populusdavidiana)和白桦(Betulaplatyphylla)组成。其他散生树种有油松（Pinustabuliformis）、蒙古栎（Quercus mongolica）和侧柏（Platycladus orientalis）等。区内灌木树种主要有高山绣线菊(Spiraea alpi-na）冷地卫矛（Euonymus frigidus）驼绒藜（Ceratoi-deslatens）金露梅(Potentillafruticosa)等,草本植物主要有凸脉苔草（Carex lanceolata）珠芽蓼（Polygonum viviparum)和高山蒿草(Kobresia pygmaea）等。青海云杉主要分布在海拔 $2 5 0 0 { \sim } 3 3 0 0 \mathrm { m }$ 的阴坡和半阴坡上，祁连圆柏主要分布在海拔 $2 7 0 0 { \sim } 3 3 0 0 \mathrm { m }$ 的阳坡、半阴坡或半阳坡上，常与云杉混交。山杨和白桦是次生林的主要树种，山杨主要分布在沟壑、溪流边和海拔 $2 7 0 0 \mathrm { m }$ 以下的洪泛区。

# 2数据来源和研究方法

# 2.1数据来源与处理

2.1.1GLAS数据本研究所用GLAS数据为通过美国国家冰雪数据中心(https://NSIDC.org/data/ice-sat)下载的2级GLA14产品[19]。下载的详细数据集包括L3F（2006年5—6月）、L3G（2006年10—11月）、L3H（2007年3—4月）、L3I（2007年10—11月）、L3J(2008年2—3月）和L3K（2008年10月）。研究区内GLAS脚印点的空间分布如图1所示。

![](images/a0a116c0e905bc365f20ad53672f7146b2605e85c99bd2758a70a07ee5f66925.jpg)  
图1研究区位置示意图  
Fig.1 The location of the study area

下载后首先依照以下2个规则对无效数据进行过滤：(1)使用GLA14产品中记录的检测标志(i_satNdx $_ { = 0 }$ ,i_FRir_qaFlag $_ { ; = 1 5 }$ )识别无饱和以及无云的GLAS数据并保留[20]；（2）将GLA14数据中记录的高程( $\left( \boldsymbol { d } _ { - } \mathrm { e l e v } \right)$ 与DEM数据进行比较,将高差阈值设为略大于该地区最大冠层高度( $( 5 0 ~ \mathrm { m } )$ ，将大于此高差的数据视为潜在的低云数据并删除[21]。过滤后，共有571个GLAS波形数据可用，将其转换为WGS84坐标系以与其他数据相匹配。

2.1.2LandsatOLI数据本研究所使用的Land-satOLI数据从美国地质调查局国家地球资源观测与科学中心(http://GLOVIS.usgs.gov/)获取，下载云量小于 $3 \%$ 的LandsatL1T数据共9景（P131R34_20180721，P132R34_20180712，P133R33_20180715，P133R34_20180621，P134R33_20180729，P135R3320180717，P136R32_20180809，P136R33_20180825，P137R33_20180612)。获取后首先对其进行辐射定标及大气校正处理,并通过实地调查建立51个地面控制点，采用二次多项式数学模型对影像进行几何精校正，将误差控制在0.5个像元以内[22]。最后，利用直方图匹配算法对图像进行拼接并裁剪以使其完整覆盖研究区域

2.1.3样地调查数据本研究的样地调查分为两阶段进行：2018年10月及2019年7月。GLAS脚印点的实地调查于2018年10月进行。由于不同地形坡度对GLAS波形的影响可能不同，因此我们首先将研究区坡度分为5级： $0 ^ { \circ } \sim 5 ^ { \circ } \cdot 5 ^ { \circ } \sim 1 5 ^ { \circ }$ 、 $1 5 ^ { \circ } { \sim } 2 5 ^ { \circ }$ ） $2 5 ^ { \circ } \sim$ $3 5 ^ { \circ } , 3 5 ^ { \circ } { \sim } 5 8 ^ { \circ }$ ，并分别在各坡度级别选取位于森林区域的GLAS脚印点进行调查，其中14个脚印点位于$0 ^ { \circ } { \sim } 5 ^ { \circ }$ ,30个脚印点位于 $5 ^ { \circ } \sim 1 5 ^ { \circ }$ ,20个脚印点位于$1 5 ^ { \circ } { \sim } 2 5 ^ { \circ }$ ,26个脚印点位于 $2 5 ^ { \circ } { \sim } 3 5 ^ { \circ }$ ,7个脚印点位于$3 5 ^ { \circ } { \sim } 5 8 ^ { \circ }$ 。

采用样方调查法对GLAS脚印点进行调查。由于本研究中使用的GLAS数据仅来自3号激光器且其脚印点椭圆度最小并接近直径为 $5 5 \mathrm { m }$ 的圆[23],为将样地调查样点分辨率与GLAS数据分辨率相匹配，我们以所选GLAS脚印点中心为圆心建立直径为 $5 5 \mathrm { ~ m ~ }$ 的圆形采样点进行采样，每个样地分为4个圆形子样地，1个位于主样地的中心，另3个位于中心地块 $3 6 0 ^ { \circ } \cdot 2 4 0 ^ { \circ }$ 和 $1 2 0 ^ { \circ }$ 的方位角，每个子样地的直径为 $1 5 \mathrm { ~ m ~ }$ ,每个子样地中心之间的距离为 $2 0 ~ \mathrm { m }$ 具体样地布局如图2所示。使用精度约为 $3 \mathrm { m }$ 的手持全球定位系统(GPS)接收器确定采样点中心坐标。用手持激光高度计(高度分辨率为 $0 . 0 1 \mathrm { { m } } \dot { }$ 测量样地内胸径大于 $5 \mathrm { c m }$ 的每棵树的高度，并记录其胸径。同时记录样地内树种、冠层郁闭度、林分类型和地形。脚印点样地平均冠层高度定义为各子样地平均冠层高度的平均值。

![](images/6ab981888db329082575571f0a16875a89555bfd8c7dc68e6a458c8b9432ae22.jpg)  
图2GLAS脚印点样地布局图 Fig.2 Conceptual layout of sample plot for measuring canopy heights in the GLAS footprints

由于GLAS数据的不连续性，位于GLAS脚印点内的森林并不能代表祁连山典型林分。为建立更准确的森林地上生物量估算模型，于2019年7月进行了第二次样地调查。此次调查选取研究区内具有代表性树种和林龄的林区共设置98个直径为15$\mathrm { ~ m ~ }$ 的圆形样地。记录样地内胸径大于 $5 \ \mathrm { c m }$ 树的高度及胸径。同时记录样地中心坐标、树种、冠层郁闭度、林分类型和地形。此外，在2次样地调查的过程中记录了研究区具有代表性的景观，以验证土地覆被类型的分类精度。2次样地调查点的分布如图3所示。

2.1.4辅助数据本研究使用的DEM数据由研究区1:50000地形图数据生成。DEM数据在本研究中除了用来过滤GLAS数据以及消除地形对GLAS数据的影响之外，由其生成的研究区海拔、坡度及坡向分布图还被用来作为环境数据与GLAS数据相结合估算森林地上碳密度的空间分布。

本研究使用的环境数据包括从世界气候数据网站（http://www.WorldClim.org/)下载的空间分辨率为 $1 \mathrm { k m }$ 的19个生物气候变量GeoTiff文件24以及从中科院资源环境数据云平台下载的土壤质地空间

# 干辛区地理

注：底图为从DEM数据中提取的坡度图，所有样地调查点均位于甘肃省境内。

![](images/6c5991854676eb5ffdc4339dd06cdb5f35b2ea57bad1fd5060136e9090255e9c.jpg)  
图3样地调查点分布图  
Fig.3Distributionof field inventory plots

分布数据。所有辅助影像数据均利用3次卷积采样方法将影像像元重采样为 $3 0 \mathrm { ~ m ~ }$ 。采用研究区森林资源二类调查小班数据(以下简称森林资源清查数据)对森林冠层高度估算结果及森林地上碳密度估算结果进行独立验证。

# 2.2 研究方法

2.2.1研究区土地覆盖分类研究区的土地覆盖分类采用监督分类法。森林类型训练样本来自于森林资源清查数据,其他类别的训练样本来自GoogleEarthTM高分辨率影像，各类别训练样本具体信息如表1所示。训练样本确立后，将其输入到最大似然分类器中得到分类结果，以实地调查数据作为验证样本,得到该区域的分类总体精度为 $9 1 . 5 9 \%$ ,Kappa系数为0.89。通过分类结果，提取位于森林区域的GLAS脚印点共计273个，其中针叶林91个，阔叶林55个，针阔混交林127个。

2.2.2 GLAS脚印点的森林冠层高度估算在GLA14产品中，记录了GLAS原始波形通过高斯滤波器拟合的1个波形信号开始范围增量(d_SigBegOff)以及最多6个高斯波峰质心范围增量(d_gpCntRngOff)，本研究以d_SigBegOff作为植被冠顶波形信号，以最后2个 $d _ { - } \mathrm { { g p C n t R n g O f f } }$ 中较强峰近似表示地表波形信号。对其求差得到的波形幅度( $\boldsymbol { L } _ { \mathrm { e x t } }$ )可以表示GLAS提取冠层高度。

表1训练样本详细信息  
Tab.1 Detailed information of training samples   

<html><body><table><tr><td>土地覆被类别</td><td>样本数量/个</td><td>栅格数量/个</td></tr><tr><td>农田</td><td>100</td><td>12937</td></tr><tr><td>灌木</td><td>102</td><td>9180</td></tr><tr><td>草地</td><td>132</td><td>11223</td></tr><tr><td>森林</td><td>115</td><td>8511</td></tr><tr><td>针叶林</td><td>157</td><td>20567</td></tr><tr><td>阔叶林</td><td>109</td><td>16459</td></tr><tr><td>针阔混交林</td><td>48</td><td>5769</td></tr><tr><td>建设用地</td><td>76</td><td>8360</td></tr><tr><td>裸地</td><td>103</td><td>8652</td></tr><tr><td>水域</td><td>157</td><td>15563</td></tr></table></body></html>

$$
{ \cal L } _ { \mathrm { e x t } } = d _ { - } \mathrm { g p } \mathrm { C n t R n g O f f } - d _ { - } \mathrm { S i g B e g O f f }
$$

在平坦地区， $L _ { \mathrm { e x t } }$ 可以近似表示实际的森林冠层高度，但在山区，由于地形起伏影响，GLAS波形会发生变化，由此引起的偏差值Bias会直接影响森林冠层高度的估计结果(图4)。

本文采用1种基于几何模型的地形校正方法[25]对Bias进行量化：

![](images/5345b56e2dbc71f2e0af7e90f4e14e0250ea2c51f83fa4098427a85c8acd2550.jpg)  
Fig.4 Effects of different topographical conditions on GLAS-derived canopy height

注 ${ : \cal H } _ { \mathrm { c } }$ 为实际冠层高度 $\mathrm { ( m ) }$ ;0为地表坡度()； $d$ 为GLAS脚印直径 $\mathrm { ( m ) }$ 。图4不同地形条件对GLAS提取森林冠层高度的影响

$$
L _ { \mathrm { e x t } } = H _ { \mathrm { C } } + \mathrm { B i a s }
$$

$$
{ \mathrm { B i a s } } = d \times \tan \theta + { \frac { c \times { \mathrm { F W H M } } } { 2 } }
$$

式中： $H _ { \mathrm { c } }$ 表示实际冠层高度 $\mathrm { ( m ) }$ ;Bias为偏差值； $d$ 表示GLAS足迹直径，本研究中取值为 $5 5 ~ \mathrm { m } ; \theta$ 表示足迹所在的坡度等级的平均坡度值 ${ \bf \Pi } ^ { ( \circ } ) ; c$ 表示光速$\left[ \mathbf { m } \cdot \left( \mathbf { n } \mathbf { s } \right) ^ { - 1 } \right]$ ; FWHM(Fullwidthathalfmaximum)表示激光脉冲宽度，为 $6 \mathrm { n s }$ 。

由于GLAS数据与样地调查数据以及森林资源清查数据间存在约10a的时间差，因此，我们引入平移系数 $\boldsymbol { a }$ 和 $b$ 对此模型进行改进，并采用通用全局优化算法(Levenberg marquard,LM)基于GLAS 脚印点实地调查数据拟合 $\mathbf { \alpha } _ { a }$ 和 $b$ 的最优估计值，从而使GLAS提取的冠层高度更接近研究区实际的冠层高度。模型改进后从GLAS数据中提取的冠层高度为：

$$
H _ { \mathrm { G L A S } } = L _ { \mathrm { e x t } } - \left[ a \times \left( d \times \tan \theta + \frac { c \times \mathrm { F W H M } } { 2 } \right) + b \right]
$$

2.2.3GLAS脚印点碳密度估算研究区典型林分调查共建立针叶林样地42个，阔叶林样地38个，针阔混交林样地18个。按照森林类型统计各样地的平均树高 $( H )$ 和平均胸径 $( D )$ 。借鉴地区物种的异速生长方程(表2)，随机选取每种类型森林 $7 0 \%$ 的样地调查数据,拟合 $H , D , D ^ { 2 } H , \lg H , \lg D$ 和 $ { \mathrm { l g } } D ^ { 2 } H$ 这6个自变量与地上生物量(AGB)的函数。同时以平均胸径 $( D )$ 为因变量，以平均树高 $( H )$ 为自变量，拟合$D , \lg D , D ^ { 2 }$ 与 $H , \lg H , H ^ { 2 }$ 之间的函数关系。使用剩余$3 0 \%$ 的样地数据交叉验证各函数的拟合效果，以模型决定系数 $R ^ { 2 }$ 判定拟合效果的优劣

因利用与树种相关的碳含量转换系数可以将地上生物量转换为地上碳储量时得到最准确的估计[33]。因此,对进行实地调查的97个GLAS脚印点，根据表2选择特定的碳含量转换系数计算其碳密度。对于剩余的176个GLAS脚印点，根据区域相关研究[34]，分别将针叶林、阔叶林和针阔混交林的地上生物量按照0.4927、0.4682和0.4682的碳含量转换系数转化为地上碳储量，并结合森林资源清查数据中记录的林分密度计算脚印点地上碳密度。

2.2.4 研究区森林地上碳密度制图由于GLAS脚印点的不连续性，需要与辅助数据结合以获得空间连续的森林地上碳密度分布。将激光脚印点的碳密度外推到整个研究区域的方法通常分为两类：参数化算法和非参数算法。参数化算法，一般使用具有空间连续性的光学遥感数据建立基于像素的生物量/碳储量与光学指数间的回归模型["]，但实际上，森林生物量受多种因素的影响，其与遥感数据的关系很难用简单的线性或非线性模型表达[12]。因此，越来越多的研究选择使用非参数化算法将激光雷达脚印点生物量/碳储量外推到整个研究区域[35-37]

本研究采用非参数化算法最大熵模型(MaxEnt)获取研究区森林地上碳密度分布图。最大熵模型是基于最大熵原理用于预测物种潜在地理分布的预测模型[38]。运行时首先确定物种己知点的分布区域，寻找限制物种分布的约束条件即环境变量，构建约束集合，根据物种实际分布点和环境变量得出预测模型，再对模拟目标物种在目标区域的可能分布进行预测，以所有满足已知约束条件集合中熵最大的概率分布为最优分布。

运行模型时以研究区环境及地形数据共计23个图层(19个生物气候变量图、土壤质地空间分布数据以及海拔、坡度和坡向图)作为环境变量，以GLAS脚印点和样地调查点的地上碳密度作为训练数据。将样地调查点和GLAS脚印点地上碳密度估算结果划分为12个等级区间： $5 { \sim } 1 0 ~ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ ） $1 0 \sim$ $2 0 \ { \mathrm { t } } \cdot { \mathrm { h m } } ^ { - 2 } , 2 0 { \sim } 3 0 \ { \mathrm { t } } \cdot { \mathrm { h m } } ^ { - 2 } , \cdots , 1 0 0 { \sim } 1 1 0 \ { \mathrm { t } } \cdot { \mathrm { h m } } ^ { - 2 } , 1 1 0 { \sim }$ $1 1 9 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ ，分别将每一等级碳密度的样地调查和GLAS脚印点的地理位置输入以构建该等级地上碳密度分布的约束环境集合，并生成该等级地上碳密度在每个栅格概率值分布，并使用以下函数将其转换为每个像素的地上碳密度[2]：

$$
\mathrm { A G C } _ { _ { \mathrm { d e n s i t y } } } = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } P _ { i } ^ { n } \times C _ { i } } { \displaystyle \sum _ { i = 1 } ^ { n } P _ { i } ^ { n } } }
$$

式中： $\mathrm { A G C } _ { \mathrm { d e n s i t y } }$ 是森林地上碳密度； $n$ 是最佳迭代次数； $P _ { i } ^ { n }$ 是通过最大熵的第 $n$ 次运算得到的每个等级

# 干辛区地理

表2祁连山地区相关树种异速方程和碳含量转换系数  
Tab.2 Species-specific allometric equations and carbon content conversion factor in Qilian Mountains   

<html><body><table><tr><td>树种</td><td>异速生长方程</td><td>参考文献</td><td>碳含量转换系数</td></tr><tr><td>青海云杉</td><td>Ws =0.0478(D2²H),86S</td><td>王金叶等[26]</td><td>0.5200[26]</td></tr><tr><td>Picea crassifolia</td><td>WB =0.0122(D' H),.905</td><td></td><td></td></tr><tr><td rowspan="6">祁连圆柏</td><td>WL= 0.2650(D²H)4701</td><td></td><td></td></tr><tr><td>W=Ws +WB+WL</td><td></td><td></td></tr><tr><td>W = 0.2738(D²H).6912</td><td>王金叶等[27]</td><td>0.4650[28]</td></tr><tr><td>WB = 0.0061(D²H)0945S</td><td></td><td></td></tr><tr><td>WL = 0.0042(D²H),398</td><td></td><td></td></tr><tr><td>W=Ws +WB +WL</td><td></td><td></td></tr><tr><td rowspan="5">侧柏 Platycladus orientalis</td><td>Ws = 0.0427(D²H),.8545</td><td>关晋宏等[29]</td><td>0.5034[30]</td></tr><tr><td>W = 0.0128(D²H),8916</td><td></td><td></td></tr><tr><td>WL = 0.0258(D²H)0.7037</td><td></td><td></td></tr><tr><td>W=Ws+WB+WL</td><td></td><td></td></tr><tr><td></td><td>程堂仁等[31]</td><td>0.5108[32]</td></tr><tr><td rowspan="5">蒙古栎</td><td>WB=e63807D²H)1242</td><td></td><td></td></tr><tr><td>WL,=5327D H)081</td><td></td><td></td></tr><tr><td>W=Ws+WB+WL</td><td></td><td></td></tr><tr><td>Ws = 0.0493(D H),814</td><td>关晋宏等[29]</td><td>0.5004[30]</td></tr><tr><td>WB = 0.0026(D'H),1887</td><td></td><td></td></tr><tr><td rowspan="3"></td><td>WL = 0.0119(D²H).,850</td><td></td><td></td></tr><tr><td>W=Ws +WB +WL</td><td></td><td></td></tr><tr><td>Ws = e,*3,82(D²H)0.961</td><td>程堂仁等[31]</td><td>0.4956[30]</td></tr><tr><td rowspan="7">Populus davidiana</td><td>WB= e5.07(DH)00</td><td></td><td></td></tr><tr><td>We30108(D² H)0610</td><td></td><td></td></tr><tr><td>W=Ws +WB +WL</td><td></td><td></td></tr><tr><td>Ws = e-3.8023(D²H).63</td><td>程堂仁等[31]</td><td>0.5025[32]</td></tr><tr><td>WB= e-5.907(D²H)0 .090</td><td></td><td></td></tr><tr><td>WL =e³3.9108( D²H)</td><td></td><td></td></tr><tr><td>W=Ws + WB+ WL</td><td></td><td></td></tr></table></body></html>

注：Ws为干生物量 $\mathrm { ( k g ) }$ ; $W _ { \mathrm { B } }$ 为枝生物量 $( \mathrm { k g } )$ ： $\mathbb { W } _ { \mathrm { L } }$ 为叶生物量 $\left( \mathrm { { k g } } \right)$ ;W为地上生物量 $( \mathrm { k g } ) { ; } D$ 为胸径 $\mathrm { ( c m ) }$ 1 $H$ 为树高 $\mathrm { ( m ) }$ 。

地上碳储量密度分布的概率； $C _ { i }$ 是每个地上碳密度等级区间的中值。经过多次迭代和与测试数据的交叉验证，发现当 $\scriptstyle n = 3$ 时，地上碳密度分布收敛到最优值。另外，使用每个碳密度等级的最大值和最小值来创建概率分布图以包含估计的上下界。最后根据研究区土地覆被分类的森林范围对所得结果进行掩膜提取，以避免保留毁林和灌丛地区地上碳密度值而对研究区森林地上碳密度造成高估。

# 3结果与分析

# 3.1GLAS脚印点森林冠层高度估算结果

通过运行LM算法获得各坡度等级平移系数 $a$ 和 $b$ 的最佳估计值。按照不同坡度等级对GLAS脚印点提取的森林冠层高度进行校正，并随机选择51个GLAS脚印点以森林资源清查数据独立验证GLAS数据提取的冠层高度精度及地形校正效果，地形校正效果如图5所示。

结果表明，与校正前相比，通过改进后的地形校正模型提取的冠层高度更接近1:1拟合线，即更接近森林资源清查数据中记录的冠层高度。表3显示了各坡度等级地形校正模型的统计精度。

由表3可知，地形校正后，各坡度等级地形校正模型的 $R ^ { 2 }$ 可以解释 $6 5 \% { \sim } 6 7 \%$ 的冠层高度的变化程度，与校正前的 $R ^ { 2 }$ 相比变化并不明显，表明改进后

![](images/627dcfd5ea393683d9395f09c58c9e179ffd682c90f666b8bf462e1746b06d3e.jpg)  
图5地形校正前后不同坡度等级GLAS冠层高度估计精度对比

Fig.5ComparisonofGLAS derivedcanopyheightbeforeandafter topographiccorectionindifferent slope gradient classe

# 表3不同坡度等级地形校正前后GLAS提取冠层高度的精度比较

Tab.3 Accuracy comparison ofGLASderived canopyheights before and after topographic correction in different slope gradient classes   

<html><body><table><tr><td rowspan="3">坡度等级</td><td colspan="2">R</td><td colspan="2">RMSE/m</td></tr><tr><td>校正前</td><td>校正后</td><td>校正前</td><td>校正后</td></tr><tr><td>0°~5°</td><td>0.62</td><td>0.66</td><td>2.83</td><td>1.84</td></tr><tr><td>5°~15°</td><td>0.64</td><td>0.65</td><td>3.32</td><td>2.23</td></tr><tr><td>15°~25°</td><td>0.66</td><td>0.67</td><td>6.74</td><td>3.51</td></tr><tr><td>25°~35°</td><td>0.63</td><td>0.65</td><td>8.00</td><td>3.91</td></tr><tr><td>35°~58°</td><td>0.65</td><td>0.67</td><td>12.59</td><td>3.48</td></tr></table></body></html>

注： $R ^ { 2 }$ 为模型决定系数;RMSE为模型均方根误差。

的地形校正模型并没有改变数据的拟合优度。另外,地形校正前，随着坡度的增加， $L _ { \mathrm { e x t } }$ 的RMSE从$2 . 8 3 \mathrm { m }$ 增加到 $1 2 . 5 9 \mathrm { ~ m ~ }$ 。地形校正后，不同坡度等级的 $H _ { \mathrm { G L A S } }$ 的RMSE稳定在 $1 . 8 4 { \sim } 3 . 9 1 \mathrm { ~ m }$ 之间,因此,我们认为改进后的地形修正模型性能良好，且对较高坡度等级的地形修正效果更加明显

# 3.2GLAS脚印点地上碳储量密度估算结果

根据研究区典型林分调查结果和树种异速生长方程，建立不同类型森林的地上生物量估算模型。拟合过程中发现，仅加入树高信息时模型拟合精度最低，而同时加入树高胸径信息时模型估测精

# 干吴区地理

度最高。最终针叶林和阔叶林的地上生物量估算模型以幂函数拟合效果最佳，其模型决定系数 $R ^ { 2 }$ 分别为0.979和0.983，针阔混交林的地上生物量估算模型以二次项函数拟合效果最佳， $R ^ { 2 }$ 为 $0 . 9 8 7$ 。3种不同森林类型的地上生物量估算模型如式(6)\~式(8):

$$
\mathrm { A G B } ( \sharp \mathrm { f } \cdot \sharp + \sharp \mathcal { K } ) = 0 . 1 2 7 \times ( D ^ { 2 } H ) ^ { 0 . 8 1 6 }
$$

$$
\mathrm { A G B } ( \vert \overrightarrow { \ast } \vert \vert \vert + / \ast / \ast ) = 1 . 4 4 4 \times ( D ^ { 2 } H ) ^ { 0 . 5 6 2 }
$$

$$
\mathrm { A G B } \left( \ddagger \lvert \ddagger \rvert \ddagger \lvert \ j \rvert _ { \mathrm { t k } } ^ { \boxplus } \xrightarrow { * } \ k \rvert \right) = 2 7 5 . 4 2 \times ( \lg D ^ { 2 } H ) ^ { 2 } -
$$

$$
1 8 0 8 . 3 8 3 \times \lg D ^ { 2 } H + 3 0 7 8 . 1 3 8
$$

由于未进行实地调查的GLAS脚印点缺少树木胸径数据，另外按照不同森林类型对其树高和胸径的关系进行拟合。最终针叶林树高与胸径间的关系方程以S函数拟合效果最佳， $R ^ { 2 }$ 为0.787；阔叶林以二次项函数拟合效果最佳， $R ^ { 2 }$ 为0.778；针阔混交林以复合函数拟合效果最佳， $R ^ { 2 }$ 为0.734。3种不同类型森林树高胸径关系如式(9)\~式(11)：

$$
\lg D ( \sharp \{ \sharp \} \# + \# \# \hbar ) = \mathrm { e } ^ { ( 0 . 7 8 7 - 0 . 4 8 1 / \mathrm { l g } H ) }
$$

$$
D ^ { 2 } \big ( \lvert \Re \rvert \lvert \mathbf { + } \# \rvert \lvert \mathbf { \cdot } \rvert \big ) = 0 . 0 0 3 4 \times ( H ^ { 2 } ) ^ { 2 } + 1 . 1 2 7 \times H ^ { 2 } + 3 8 4 . 9 6
$$

利用典型林分样地调查数据交叉验证以上模型单木水平的估计精度：针叶林、阔叶林和针阔混交林森林地上生物量估算的均方根误差RMSE分别为 $1 7 . 8 8 \mathrm { ~ k g } \setminus 7 . 1 3 \mathrm { ~ k g }$ 和 $4 . 6 5 \mathrm { k g }$ ，胸径估计的RMSE分别为 $5 . 2 \mathrm { c m } \ 、 6 . 9 8 \mathrm { c m }$ 和 $4 . 0 4 ~ \mathrm { c m }$ ○

按照以上生物量估算模型及树高胸径关系计算位于不同森林类型GLAS脚印点内的地上生物量，并根据各森林类型的碳含量转换系数以及森林调查数据中记录的林分密度得到森林区域GLAS脚印点森林地上碳密度，估算结果如图6所示。

# 3.3研究区森林地上碳密度分布估算结果

通过MaxEnt模型将GLAS脚印点森林地上碳密度外推至整个研究区域，得到2018年祁连山国家公园 $3 0 \mathrm { ~ m ~ }$ 分辨率的森林地上碳密度空间分布如图7所示。

为验证估算结果的准确性，从与GLAS脚印点及样地调查点至少相距 $1 ~ \mathrm { k m }$ 的森林资源清查数据中随机选取181个样本点独立验证估算精度，得到本次森林地上碳密度估算均方根误差RMSE为$1 8 . 9 4 6 ~ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ 。此结果满足REDD $^ +$ 计划MRV（Mea-suring,reporting,andverification)指南的要求,即利用卫星遥感数据估算森林碳储量时，应将估算值与实地测量值之间的误差控制在 $2 0 \mathrm { ~ t ~ } { \cdot } \mathrm { h m } ^ { - 2 }$ 或 $2 0 \%$ 以内。

结果显示,2018年祁连山国家公园森林地上碳密度主要分布在 $2 0 . 6 7 { \sim } 6 2 . 6 2 \ \mathrm { t \cdot h m ^ { - 2 } }$ 之间，最高值为$1 1 9 . 1 8 ~ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ 。平均森林地上碳密度为 $4 0 . 7 2 { \scriptstyle \pm 6 . 7 2 }$ $\mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ ,森林地上总碳储量为 $2 8 . 5 8 { \pm } 4 . 7 2 \mathrm { T g } ( 1 \mathrm { T g } =$ $1 0 ^ { 9 } \mathrm { k g } )$ 。其中甘肃省境内森林地上碳储量为23.67$\mathrm { { T g } }$ ,远高于青海省 $( 5 . 2 1 \mathrm { T g } )$ ,甘肃省森林地上碳密度平均值为 $4 4 . 9 0 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ ,也高于青海省地上碳密度平均值 $2 8 . 7 1 ~ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ 。不同类型森林中,针叶林的平均地上碳密度最高 $\left( 5 0 . 6 9 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } \right)$ ，接下来依次是阔叶林 $( 4 1 . 4 2 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } )$ 和针阔混交林 $( 3 8 . 0 6 ~ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } )$ ，针叶林、阔叶林和针阔混交林的地上碳储量分别占祁连山国家公园森林地上总碳储量的 $5 3 . 2 8 \%$ 、 $1 6 . 5 7 \%$ 和 $3 0 . 1 5 \%$ 。

![](images/6d7591089d42553e61b082271bcd6d696377b8f4fb4fa76636ea7c1bf3f8a1f1.jpg)  
图6森林区域内GLAS脚印点森林地上碳密度估算结果  
Fig.6Estimation of forest aboveground carbon density ofGLAS footprints in forest area

![](images/619bdbd2f5cb614c2d55d40aad9918b15a7ba848f53c359f25de08929a25dc2b.jpg)  
图72018年祁连山国家公园森林地上碳密度分布图  
Fig.7Forest aboveground carbon density map of Qilian Mountains National Park in 2018

由于植被分布主要受气候变化的驱动特别是温度和降水的影响，而山区高原复杂的地形对气候因子的空间格局作用较大[39],因此，我们通过地学统计进一步对位于不同海拔等级( $( 1 7 7 0 { \sim } 2 7 7 0 \ \mathrm { m } .$ $2 7 7 0 { \sim } 3 7 7 0 \ \mathrm { m } , 3 7 7 0 { \sim } 4 7 7 0 \ \mathrm { m } , 4 7 7 0 { \sim } 5 7 4 0 \ \mathrm { m } )$ 、坡度等级 $( 0 ^ { \circ } \sim 5 ^ { \circ } , 5 ^ { \circ } \sim 1 5 ^ { \circ } , 1 5 ^ { \circ } \sim 2 5 ^ { \circ } , 2 5 ^ { \circ } \sim 3 5 ^ { \circ }$ 和 $3 5 ^ { \circ } { \sim } 5 8 ^ { \circ }$ 以及坡向(阳坡、阴坡、半阳坡以及半阴坡)的森林地上碳储量进行分析。结果显示，对不同的海拔等级而言，海拔 $2 7 7 0 { \sim } 3 7 7 0 \mathrm { m }$ 地区森林地上碳储量最大，约占研究区森林地上总碳储量的 $6 4 . 4 7 \%$ ,其次是海拔

$1 7 7 0 { \sim } 2 7 7 0 \ \mathrm { m }$ 地区 $( 2 1 . 0 5 \% )$ 以及海拔 $3 7 7 0 { \sim } 4 7 7 0 \ \mathrm { m }$ 地区( $1 3 . 9 9 \%$ )，海拔 $4 7 7 0 { \sim } 5 7 4 0 \ \mathrm { m }$ 地区基本没有森林地上碳储量分布。对不同的坡度等级而言，除$3 5 ^ { \circ } { \sim } 5 8 ^ { \circ }$ 地区森林地上碳储量较少外，其余坡度的森林地上碳储量基本相同。对不同坡向而言，阴坡及半阴坡的森林地上碳储量基本为阳坡及半阳坡的2倍。

# 4讨论与结论

# 4.1 讨论

本研究结果小于Wagner等[40]通过采样法获得的祁连山区东北缘青海云杉林地上碳密度(82.70$\mathrm { t } \cdot \mathrm { h m } ^ { - 2 } .$ ),这可能是因为该区域树木生长状况较好且青海云杉林为区域优势树种。本研究结果与Zhao等[30结合LPJ-GUESS和HASM模型对中国西北地区森林地上碳密度的估计结果 $( 3 6 . 1 0 { \sim } 6 4 . 1 7 ~ \mathrm { t \cdot h m } ^ { - 2 } )$ 接近。将本研究结果与其他山区森林地上碳密度估算结果进行比较，本研究祁连山区森林地上平均碳密度估算结果（ $4 0 . 7 2 { \scriptstyle \pm 6 . 7 2 \ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } } ,$ 与川西米亚罗自然保护区[41]森林地上平均碳密度( $\cdot 5 3 . 1 4 \mathrm { ~ t } \cdot \mathrm { h m } ^ { - 2 } )$ 以及内蒙古大兴安岭生态站[4]森林地上平均碳密度中 $3 8 . 2 9 \mathrm { ~ t } \cdot \mathrm { h m } ^ { - 2 }$ )接近，说明祁连山与其他重要的山地

# 干吴区地理

自然保护区一致，是重要的高海拔森林固碳场所。

本研究依据GLAS数据提供的森林垂直结构信息估测森林地上碳密度。目前从GLAS数据中提取森林冠层高度的方法主要分为两类：第一类是将第一个波峰和地面波峰之间的距离作为植被冠层的高度值，而地面波峰通常被认为是最低处的高斯峰值或最低2个高斯峰值中较强的高斯峰值25；第二类是根据波形范围或其他波形参数通过统计分析拟合植被高度[43]。比较而言，第一类方法较为简单，可以灵活地应用于不同的地区，特别是结合DEM数据等其他辅助数据时，能够较为直观的消除地形对GLAS波形的影响，同时该方法也被诸多研究证实在山区森林冠层高度估算方面具有较好的性能[23.44]。因此,本研究采用第一类方法,结合改进后的地形校正模型从GLAS数据中提取森林冠层高度。另外，本研究选择已经过统一滤波和拟合处理的GLA14产品而非GLA01产品，可以减少处理GLA01产品中记录的原始波形时的一些偶然误差。

本研究采用MaxEnt模型将GLAS脚印点森林地上碳密度外推至整个研究区域。MaxEnt是1种基于概率框架从一组不完全信息中生成预测或推断的通用算法[12]。它依赖于不完全经验概率分布的假设，在一定的环境约束下，该假设可以近似为具有最大熵的概率分布(MaxEnt分布），并且该分布接近于潜在的地理分布[36]。考虑到研究区内物种分布主要受气候因素的控制且复杂地形对物种分布也有很大影响，本研究采用MaxEnt模型基于GLAS脚印点和样地调查点的地上碳密度及其分布的气候、土壤及地形数据作为训练数据，模拟接近实际情况的森林地上碳密度分布。

已有研究证实利用遥感数据估算森林地上生物量/碳储量的主要误差源是不同数据源之间的空间异质性[45]。而本研究的空间异质性问题主要涉及GLAS足迹的位置精度以及所有数据空间分辨率的一致性。因此，我们首先依据GLA14产品中记录的高程用DEM数据检查GLAS足迹定位精度。其次，我们选择仅来自3号激光器的GLAS数据并设计了与其分辨率匹配的样地调查方案，同时还将所有影像数据分辨率重采样到 $3 0 \mathrm { m }$ ，以最大程度的消除由空间异质性引起的误差。

本研究的不确定性包括以下几个方面：（1）样地调查时的测量误差；（2）土地覆被分类图的误分类；（3）冬季获取的GLAS数据导致的由落叶树种或冠层积雪引起的森林冠层高度估计误差。

# 4.2结论

本研究基于GLAS数据、LandsatOLI数据以及样地调查数据，在建立不同类型森林地上生物量估算模型的基础上，利用GLAS数据提取的森林冠层高度对其脚印点森林地上碳密度进行估算，并通过MaxEnt非参数化方法将脚印点森林地上碳密度外推到整个研究区域。结果表明：

（1）从GLAS数据中提取森林冠层高度时，通过改进后的地形校正模型提升GLAS数据提取的精度，这不仅为GLAS脚印点森林地上碳密度的准确估算提供了保证，也使得更多的GLAS数据可用于后续的研究。

（2）所得的祁连山国家公园森林地上碳密度估算结果满足REDD $^ { + }$ 计划MRV指南对利用卫星遥感数据估算森林碳储量的误差要求，可为监测区域乃至国家尺度的森林碳储量变化以及制定可持续的森林管理措施提供依据。此外，本文所采用的方法在山区森林碳储量估算方面也具有较大的潜力。

# 参考文献(References)

[1] PanY,BirdseyR A,FangJ,etal.Alarge and persistent carbon sink in the world's forests[J]. Science,2011,333(6045): 988-993.   
[2] Houghton R A,House JI, Pongratz J,et al. Carbon emissions from land use and land-cover change[J]. Biogeosciences,2O12, 9(12): 5125-5142.   
[3] Shang X, ChazetteP.Interest of a full-waveform flown UVLidar to derive forest vertical structures and aboveground carbon[J].Forests,2014, 5(6): 1454-1480.   
[4] Narine L L,Popescu S,Neuenschwander A,et al. Estimating aboveground biomass and forest canopy cover with simulated ICESat-2 data[J].Remote Sensing of Environment,2019,224:1-11.   
[5] Neigh C SR,NelsonRF,Ranson KJ,et al. Taking stock of circumboreal forest carbon with ground measurements,airborne and spaceborne LiDAR[J].Remote Sensing of Environment,2013, 137: 274-287.   
[6] Wulder M A,White JC,Nelson RF,et al.Lidar sampling for large-area forest characterization: A review[J].Remote Sensing of Environment,2012,121:196-209.   
[7] Nelson R,Boudreau J,Gregoire TG,et al.Estimating Quebec provincial forest resources using ICESat/GLAS[J]. Canadian Journal of Forest Research,2009,39(4): 862-881.   
[8] Baccini A,Goetz SJ,WalkerWS,etal.Estimated carbon dioxide emissions from tropical deforestation improved by carbon-density maps[J]. Nature Climate Change,2012,2(3):182-185.   
[9]Tyukavina A,Stehman SV,Potapov PV,et al. National-scale estimation of gross forest aboveground carbon loss: A case study of the Democratic Republic of the Congo[J]. Environmental Research Letters,2013,8(4): 044039,doi: 10.1088/1748-9326/8/4/044039.   
[10] 池泓,黄进良,邱娟,等.GLAS 星载激光雷达和Landsat/ETM $^ +$ 数据的森林生物量估算[J].测绘科学,2018,43(4):9-16,23. [Chi Hong,Huang Jinliang,Qiu Juan,et al.Estimation of forest aboveground biomassusing ICESat/GLAS dataand Landsat/ ETM $+$ imagery[J]. Science of Surveying and Mapping, 2018,43(4): 9-16,23.]   
[11]Hilbert C, Schmullius C. Influence of surface topography on ICESat/GLAS forest height estimation and waveform shape[J]. Remote Sensing,2012,4(8): 2210-2235.   
[12]Satchi S S,Harris NL, Brown S,et al. Benchmark map of forest carbon stocks in tropical regions across three continents[J]. Proceedings of the National Academy of Sciences of the United States of America,2011,108(24): 9899-9904.   
[13]Huang H, Liu C,Wang X,et al.Integration of multi-resource re motely sensed data and allometric models for forest aboveground biomass estimation in China[J].Remote Sensing of Environment, 2019,221: 225-234.   
[14]Wang Y,Li G,Ding J,et al.A combined GLAS and MODIS estimation of the global distribution of mean forest canopy height[J]. Remote Sensing of Environment,2016,174: 24-43.   
[15] 程鹏,孔祥伟,罗汉,等.近60a以来祁连山中部气候变化及其 径流响应研究[J].干旱区地理,2020,43(5):1192-1201.[Cheng Peng,Kong Xiangwei, Luo Han,et al. Climate change and its runoff response in the middle section of the Qilian Mountains in the past 60 years[J]. Arid Land Geography,2020,43(5): 1192-1201.]   
[16] 马剑,刘贤德,李广,等.祁连山北麓中段青海云杉林土壤水热 时空变化特征[J].干旱区地理,2020,43(4):1033-1040.[Ma Jian,Liu Xiande,Li Guang,et al. Spatial and temporal variations of soil moisture and temperature of Picea crassifolia forest in north piedmont of central Qilian Mountains[J].Arid Land Geography, 2020,43(4): 1033-1040.]   
[17]Fang S, He Z,Du J, et al. Carbon mass change and its drivers in a boreal coniferous forest in the Qilian Mountains,China from 1964 to 2013[J]. Forests,2018,9(2): f9020057,doi: 10.3390/f9020057.   
[18] Yue JW, Guan JH, Deng L, et al. Allocation pattern and accumulation potential of carbon stock in natural spruce forests in northwest China[J]. Peerj,2018(6): e4859,doi: 10.7717/peerj.4859.   
[19]Zwally HJ,Schutz R,Hancock D,et al.GLAS/ICESat L2 global land surface altimetry data (HDF5),version 34[DB/OL]. [2014]. NASA National Snow and Ice Data Center Distributed Active Archive Center.   
[20]Chi H, Sun G,Huang J,et al.National forest aboveground biomass mapping from ICESat/GLAS data and MODIS imagery in China [J]. Remote Sensing,2015,7(5): 5534-5564.   
[21]WeiL,Feng Q,Deo R C.Changes in climatic elements in the PanHexi region during 1960—2014 and responses to global climatic changes[J]. Theoretical and Applied Climatology,2018,133(1-2): 405-420.   
[22] 王晓学,沈会涛,林田苗,等.利用多信息源提高半干旱地区TM 影像的森林类型制图精度:以北京西部山区为例[J].自然资源 学报,2017,32(7):1217-1228.[Wang Xiaoxue, Shen Huitao,Lin Tianmiao,et al.Improving the forest type mapping accuracy in semiarid mountainous areas based on TM images: Take the west mountain of Beijing as an example[J]. Journal of Natural Resources,2017,32(7): 1217-1228.]   
[23]Park T,Kennedy R E,Choi S,et al.Application of physicallybased slope correction for maximum forest canopy height estimation using waveform Lidar across diffrent footprint sizes and locations: Tests on LVIS and GLAS[J]. Remote Sensing, 2014, 6(7): 6566-6586.   
[24]Fick SE,Hijmans R J.WorldClim 2: New 1-km spatial resolution climate surfaces for global land areas[J]. International Journal of Climatology,2017,37(12): 4302-4315.   
[25]Lee S,Ni-Meister W,Yang W,et al. Physically based vertical vegetation structure retrieval from ICESat data: Validation using LVIS in White Mountain National Forest,New Hampshire,USA [J]. Remote Sensing of Environment, 2011,115(11): 2776-2785.   
[26]王金叶,车克钧,蒋志荣.祁连山青海云杉林碳平衡研究[J].西 北林学院学报,2000(1): 9-14.[Wang Jinye,Che Kejun,Jiang Zhirong.A study on carbon balance of Picea crassfolia in Qilian Mountains[J]. Journal of Northwest Forestry College,20O0(1): 9-14.]   
[27] 王金叶,车克钧,傅辉恩,等.祁连山水源涵养林生物量的研究 [J].福建林学院学报,1998(4):34-38.[Wang Jinye,Che Kejun, Fu Hui'en,et al. Study on biomass of water conservation forest on north slope of Qilian Mountains[J]. Journal of FuJian College of Forestry,1998(4): 34-38.]   
[28] 罗艳,唐才富,辛文荣,等.青海省云杉属(Picea)和圆柏属(Sabina)乔木含碳率分析[J].生态环境学报,2014,23(11):1764- 1768.[Luo Yan, Tang Caifu,Xin Wenrong,et al. Carbon content rate of Picea and Sabina trees in Qinghai Province[J]. Ecology and Environmental Sciences,2014,23(11): 1764-1768.]   
[29]关晋宏,杜盛,程积民,等.甘肃省森林碳储量现状与固碳速率 [J].植物生态学报,2016,40(4):304-317.[Guan Jinhong,Du Sheng, Cheng Jimin, et al. Current stocks and rate of sequestration of forest carbon in Gansu Province,China[J].Chinese Journal of Plant Ecology,2016,40(4): 304-317.]   
[30]Zhao M, Yue T, Zhao N,et al.Combining LPJ-GUESS and HASM to simulate the spatial distribution of forest vegetation carbon stock in China[J]. Journal of Geographical Sciences,2O14,24(2): 249-268.   
[31] 程堂仁,马钦彦,冯仲科,等.甘肃小陇山森林生物量研究[J].北 京林业大学学报,2007(1):31-36.[Chen Tangren,Ma Qinyan, Feng Zhongke,et al.Research on forest biomass in Xiaolong Mountains,Gansu Province[J]. Journal of Beijing Forestry Univer

# 干旱区地理

sity,2007(1): 31-36.]

[32] 程堂仁,冯菁,马钦彦,等.甘肃小陇山森林植被碳库及其分配 特征[J].生态学报,2008,28(1):33-44.[Cheng Tangren,Feng Jing,Ma Qinyan,et al. Carbon pool and alocation of forest vegetations in Xiaolong Mountains,Gansu Province[J].Acta Ecologica Sinica,2008,28(1): 33-44.]   
[33] Sileshi G W.A critical review of forest biomass estimation models, common mistakes and corrective measures[J].Forest Ecology and Management,2014,329: 237-254.   
[34] 程堂仁.甘肃小陇山森林生物量及碳储量研究[D].北京:北京 林业大学,2007.[Cheng Tangren.Research on the forest biomass and carbon storage in Xiaolong Mountains,Gansu Province[D]. Beijing: Beijing Forestry University,2007.]   
[35]Baccini A,Laporte N,Goetz SJ,et al.A first map of tropical Africa's above-ground biomass derived from satellite imagery[J]. Environmental Research Letters,2008,3(4):045011,doi: 10.1088/ 1748-9326/3/4/045011.   
[36]Cao L,Pan J,Li R,et al. Integrating airborne LiDAR and optical data to estimate forest aboveground biomass in arid and semi-arid regions of China[J].Remote Sensing,2018,10(4): 532, doi:10.3390/ rs10040532.   
[37]EiHajj M,Baghdadi N,Fayad I, etal. Interest of integrating spaceborne LiDAR data to improve the estimation of biomass in high biomass forested areas[J]. Remote Sensing, 2017,9(3): 213,doi: 10.3390/rs9030213.   
[38]Phillips S J,Anderson RP, Schapire RE.Maximum entropy modeling of species geographic distributions[J].Ecological Modeling, 2006,190(3-4):231-259.   
[39]Peng J,Liu Z, Liu Y,et al. Trend analysis of vegetation dynamics in Qinghai-Tibet Plateau using Hurst exponent[J]. Ecological Indicators,2012,14(1):28-39.   
[40]Wagner B,Liang E,Li X,et al.Carbon pools of semi-arid Picea crassifolia forests in the Qilian Mountains (north-eastern Tibetan Plateau)[J].Forest Ecology and Management, 2015,343:136-143.   
[41]巫明焱,董光,王艺积,等.川西米亚罗自然保护区森林地上碳 储量遥感估算[J].生态学报,2020,40(2):621-628.[Wu Mingyan,Dong Guang,Wang Yiji,et al. Estimation of forest aboveground carbon storage in Sichuan Miyaluo Nature Reserve based on remote sensing[J]. Acta Ecologica Sinica,2020,40(2): 621-628.]   
[42] 穆喜云,刘清旺,庞勇,等.基于机载激光雷达的森林地上碳储 量估测[J].东北林业大学学报,2016,44(11):52-56.[Mu Xiyun, Liu Qingwang,Pang Yong,et al.Forest aboveground carbon storage using RF algorithmic model and airborne LiDAR data[J]. Journal of Northeast Forestry University,2016,44(11): 52-56.]   
[43]Wu J,Wang X, Zhang H,et al. Development of a forest canopy height estimation model using GLAS full waveform data over sloping terrain[J]. International Journal of Remote Sensing,2O18,39 (23): 9073-9091.   
[44] 胡凯龙,刘清旺,庞勇,等.基于机载激光雷达校正的ICESat/ GLAS 数据森林冠层高度估测[J].农业工程学报,2017,33(16): 88-95.[Hu Kailong, Liu Qingwang,Pang Yong,et al. Forest canopy height estimation based on ICESat/GLAS data by airborne Lidar correction[J]. Transactions of the Chinese Society of Agricultural Engineering,2017,33(16): 88-95.]   
[45]Liu K,Wang J, Zeng W,et al. Comparison and evaluation of three methods for estimating forest above ground biomass using TM and GLAS data[J].Remote Sensing,2017,9(4):341,doi:10.3390/ rs9040341.

# Estimation of forest aboveground carbon density in Qilian Mountains National Park based on remote sensing

SONG Jie'²， LIU Xuelu12 (1.College of Natural Resources and Environment,Gansu Agricultural University,Lanzhou 73Oo7o,Gansu,China; 2.Land Use Research Institute,Gansu Agricultural University,Lanzhou 73oo7o,Gansu, China)

Abstract: An accurate,up-to-date,and spatially explicit estimate of the forest aboveground carbon (AGC) density is indispensable for understanding the global carbon cycle and implementing measures to mitigate climate change such as reducing emissions from deforestation and forest degradation (REDD $+$ ). Geoscience Laser Altimeter System (GLAS)data have proven to be a powerful candidate for estimating the forest AGC density distribution over largescale areas because of its global-scale sampling strategy and freely available data. However, the influenceof terrain slopes on the accuracy of the GLAS-derived canopy height often limits its utility in mountainous regions. Nevertheless, mountain forests play a key role in carbon storage because of the relatively smallinfluence of human activities,and the carbon sequestration capacities of forests differ according to the region.In this study, we integrated GLAS data,Landsat 8 OLI imagery,and field inventory data to estimate the forest AGC density distributionof Qilian Mountains National Park in northwestern China, which is an essential ecological barrierand carbon sequestration site in western China.We aimed to address the underestimation of carbon storage by mountai forests in previous studies by improving the estimation accuracy of the GLAS-derived canopy height and in turn the forest AGC density in the study area. We first improved upon a physical terrain correction model to derive the canopy height from GLAS data according to five diferent slope gradient clases.The canopy height could be reliably estimated with a root-mean-squared error (RMSE) of $1 . 8 4 - 3 . 9 1 \mathrm { ~ m ~ }$ on the basis of independent validation with forest inventory data.We subsequently calculated the AGC density of GLAS footprints located in different forest types as accurately as possble by using an aboveground biomass estimation model of different forest types and a carbon content conversion factor,as wellas the stand density recorded in the forest inventory data. We took a nonparametric approach and applied a MaxEnt model to extrapolate AGC data at the GLAS footprint scale to the whole forest as extracted from Landsat 8 OLI imagery.We also made great efforts to spatiotemporally match all data sources in this study.The results showed that the average forest AGC density in Qilian Mountains National Park was $4 0 . 7 2 { \scriptstyle \pm 6 . 7 2 \ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } }$ in 2018,and the total aboveground carbon storage was $2 8 . 5 8 { \scriptstyle \pm 4 . 7 2 } { \mathrm { ~ T g } }$ ，Forest vegetation in areas at $2 7 7 0 - 3 7 7 0 \mathrm { ~ m ~ }$ above sea level had the largest carbon storage,and shaded slopes had significantly greater carbon storage than sunny slopes.The accuracy of the estimation results was independently verified by comparison with the forest resource inventory data and resulted in an RMSE of （204号 $1 8 . 9 4 6 ~ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ ，which meets the measuring, reporting,and verification guidelines of REDD $+$ . The results of this study can provide abasis for monitoring regional- and even national-scale changes in forest carbon reserves and for formulating sustainable forest management policies.Additionally，the method used in this study can potentially be applied to estimating the carbon storage of forests in mountainous areas.

Key words: satelite LiDAR system; Landsat OLI； forest aboveground carbon density； non-parametric algo-rithm;Qilian Mountains