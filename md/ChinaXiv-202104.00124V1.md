# 基于指数平滑和ARIMA模型的西北地区饱和水汽压差预测

韩永贵1,²，韩磊123，黄晓宇1²，高阳1.2（1.宁夏大学资源环境学院,宁夏 银川750021；2.教育部中阿旱区特色资源与环境治理国际合作联合实验室，宁夏 银川750021；3.宁夏大学环境工程研究院,宁夏 银川 750021)

摘要：饱和水汽压差是土壤-植被-大气连续体水分传输过程的关键影响因素,在全球气候变化背景下,预测西北地区饱和水汽压差,对于植被恢复和农林业气象灾害风险评估具有重要的现实意义。基于西北五省(区)1990—2019年月饱和水汽压差值，采用趋势分析和小波分析等方法研究了西北地区饱和水汽压差年际变化特征和周期性变化规律;采用指数模型和ARIMA模型,筛选最佳样本步长和预测步长,对西北地区饱和水汽压差进行模拟和预测。结果表明：(1)西北五省(区)中,新疆年均饱和水汽压差最高，其次为宁夏、陕西、甘肃和青海;近30a整体上西北地区饱和水汽压差呈上升趋势,其中宁夏和新疆饱和水汽压差上升幅度最大,分别为 $0 . 0 3 6 \mathrm { ~ k P a } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 和0.033$\mathrm { { k P a } \cdot ( 1 0 \mathrm { { a } ) ^ { - 1 } } }$ ,其次为甘肃 $\left[ 0 . 0 2 6 \mathrm { ~ k P a } \cdot \left( 1 0 \mathrm { a } \right) ^ { - 1 } \right] ^ { - }$ 、青海 $\left[ 0 . 0 2 1 \mathrm { ~ k P a } \cdot \left( 1 0 \mathrm { a } \right) ^ { - 1 } \right]$ 和陕西 $\left[ 0 . 0 1 2 \mathrm { k P a } \cdot \left( 1 0 \mathrm { a } \right) ^ { - 1 } \right]$ ;(2）西北各省(区），16a尺度周期对小波方差贡献最大，为饱和水汽压差变化的主周期。此外，陕西、甘肃和新疆还存在24\~27a的周期特征,方差贡献较小;(3）相对于指数模型，ARIMA模型均方根误差平均减少 $4 2 . 3 \%$ ，决定系数 $R ^ { 2 }$ 平均提高 $1 1 . 1 \%$ Nash-Sutclife效率系数平均提高 $1 7 . 7 \%$ ,有效提高了饱和水汽压差预测精度；(4)未来一段时间内,西北各地区饱和水汽压差均存在不同程度的升高趋势，以宁夏和新疆地区的饱和水汽压差增幅最为明显，分别为 $9 . 5 \%$ 和 $8 . 9 \%$ 。

关键词：饱和水汽压差；指数平滑；ARIMA模型；预测；西北地区

饱和水汽压差是量化大气干燥程度的重要指标，是陆地生态系统植物群落发挥生态功能的主要驱动力，也是干旱引起植物死亡的重要驱动因素[1]。随着气温升高，饱和水汽压显著增大，水汽压差也增大[2]。饱和水汽压差通过改变植物的气孔行为从而影响蒸腾，在一定条件下饱和水汽压差驱动植被蒸腾作用，超过一定阈值，会导致植物气孔导度下降和光合作用降低[3],甚至造成农作物减产和林木死亡[4-6]。研究表明：近几十年来，全球饱和水汽压差急剧增长[7-8],这将进一步改变土壤-大气系统水分分配，加剧土壤温度升高和土壤水分散失，增加了植物干旱胁迫的风险[10]

我国西北地区位于亚欧大陆内地，远离海洋，降水稀少，植被覆盖率低，属典型的气候敏感带和生态脆弱区[11]。自20世纪90年代起，西北地区升温明显[12],潜在蒸散量增加[13]。近几十年来，西北全区降水量呈微弱的上升趋势，而东部区域降水量明显下降，干旱发生频率增加[14]。全球气候变化下，单以温度和降水难以清晰地描述区域自然气候变异，而饱和水汽压差能够综合反映大气的温度和湿度状况，指示地区气候的干燥程度。同时，饱和水汽压差也是影响净生态系统交换量[15]、潜热通量[以及植物叶片气孔变化[的主要因素。因此,饱和水汽压差的变化，不仅会影响陆地植被生长，而且可能会对区域水循环产生重要影响。众多研究关注于气候变化条件下的植被动态[18]、生态系统碳交换[5和蒸散发特征，以及植被蒸腾和气孔导度对饱和水汽压差变化的响应[20-21],对于我国西北地区的饱和水汽压差特征、模拟和预测研究鲜有报道。因此，选择适用性好的模型对其进行模拟和预测，无论是对于未来气候变化情境下植被格局演变研究，还是农林业气象灾害风险评估都尤为重要。

传统的经验回归模型需要输人的参数较多，且所需数据量很大,计算过程繁杂[22];神经网络在气候预测方面具有一定的优势[23],但是输出结果对参数的敏感性高，而部分参数多依靠经验公式确定，这极大的影响了模型的预测能力；灰色系统进行气候预测不失为一种好方法24，但对于振荡序列误差较大[25],在一定程度上限制了其气候模拟和预测方面的应用。指数模型是预测时序未来值的常用模型，结构简单，短期预测能力好；自回归求积移动平均模型（Autoregressive Integrated Moving Averagemodel,ARIMA)能根据非平稳时序历史数据对未来值预测，且不依赖外部变量，能够在一定程度上克服外部参数引起模型精度不足的问题26，在粮食产量预测27、干旱预测28和温度预测29等方面均取得了较好的预测结果。本研究以西北五省（区）1990一2019年月饱和水汽压差数据为样本，分析西北地区饱和水汽压差年际变化特征和周期性变化规律；引入指数模型和ARIMA模型，通过比较不同模型结构，建立适宜模拟西北各地区饱和水汽压差的最优模型；通过比较不同样本长度和预测长度对模型精度的影响，筛选出预测模型的最佳样本步长和预测步长，提高模型的精度，并对未来一段时间饱和水汽压差进行预测，以期为未来应对气候变化条件下的干旱半干旱地区生态建设和农林产业合理布局提供科学依据。

# 1研究区概况与研究方法

# 1.1 研究区概况

西北地区包括陕西（ $( 3 1 ^ { \circ } 4 2 ^ { \prime } { \sim } 3 9 ^ { \circ } 3 5 ^ { \prime } \mathrm { N }$ . $1 0 5 ^ { \circ } 2 9 ^ { \prime }$ ）$1 1 1 ^ { \circ } 1 5 ^ { \prime } \mathrm { E } { \cdot }$ 、甘肃 $( 3 2 ^ { \circ } 1 1 ^ { \prime } { \sim } 4 2 ^ { \circ } 5 7 ^ { \prime } \mathrm { N } , 9 2 ^ { \circ } 1 3 ^ { \prime } { \sim } 1 0 8 ^ { \circ } 4 6 ^ { \prime } \mathrm { E } )$ 、宁夏回族自治区 $( 3 5 ^ { \circ } 1 4 ^ { \prime } \sim 3 9 ^ { \circ } 1 4 ^ { \prime } \mathrm { ~ N ~ }$ ， $1 0 4 ^ { \circ } 1 7 ^ { \prime } \ .$ ）$1 0 9 ^ { \circ } 3 9 ^ { \prime } \mathrm { E }$ ）、青海 $( 3 1 ^ { \circ } 3 6 ^ { \prime } { \sim } 3 9 ^ { \circ } 1 9 ^ { \prime } \mathrm { N } , 8 9 ^ { \circ } 3 5 ^ { \prime } { \sim } 1 0 3 ^ { \circ } 0 4 ^ { \prime } \mathrm { E } )$ 和新疆维吾尔自治区 $( 3 4 ^ { \circ } 2 5 ^ { \prime } { \sim } 4 8 ^ { \circ } 1 0 ^ { \prime } \mathrm { N }$ $7 3 ^ { \circ } 4 0 ^ { \prime } .$ ）$9 6 ^ { \circ } 1 8 ^ { \prime } \mathrm { E }$ )，占我国陆地总面积的三分之一以上。研究区属于干旱半干旱地区，以温带大陆性气候为主,年均温 $8 \mathrm { { ^ \circ C } }$ ,年均降水量 $4 0 0 \ \mathrm { m m }$ 以下,由东到西递减。主要地形以山地、盆地和高原为主，植被覆盖稀少，是典型的全球生态环境脆弱区[]

# 1.2数据与模型构建

1.2.1数据来源通过国家气象数据中心获取  
1990—2019年各省(区)共计118个气象站点的温度

和相对湿度月观测数据。各省实际月饱和水汽压差(VPD)计算公式如下[19]：

$$
\mathrm { V P D } = 0 . 6 1 1 \mathrm { e } ^ { \left[ \frac { 1 7 . 5 0 2 T } { T + 2 4 0 . 9 7 } \right] } ( 1 - \mathrm { R H } )
$$

式中： $T$ 为大气温度( $\mathrm { ^ \circ C } )$ ;RH为相对湿度 $( \% )$ 。

1.2.2验证序列平稳性和确定 $d$ 值饱和水汽压差是温度和相对湿度的函数，受季节等因素影响呈周期性变化，具有一定的趋势项和季节效应。因此初步采用Holt指数平滑[30]和Holt-Winters 指数平滑[31]对样本数据进行模拟;建立ARIMA $( \boldsymbol { p } , \boldsymbol { d } , \boldsymbol { q } )$ 模型前,需判断时序的平稳性，主要判断方法有自相关图观察和单位根检验。其中自相关图观察法虽然操作简单，但不够严格，因此，本文采用单位根检验法对序列稳定性进行检验[2]，以确保验证的可靠性，并判断序列数据达到平稳所需的差分值。对于非稳定序列数据需要进行差分处理，即确定 $d$ 值。

1.2.3确定 $p$ 值和 $q$ 值 $p$ 和 $q$ 分别为 $\mathrm { A R I M A } \left( p , d , \right.$ （2$\cdot \mathrm { ~  ~ \omega ~ } _ { q } .$ 模型中的自回归项数和移动平均项数。为筛选最优参数组合，本文采用判断 $d$ 次差分后平稳序列自相关(ACF)和偏自相关(PACF)系数的截尾、拖尾和周期性，并结合建立不同参数模型进行比较的方法来确定最佳模型结构。

# 1.3模型评价指标

调整的 $R ^ { 2 }$ 表征了模型的拟合优度，因此在模型选择时采用调整的 $R ^ { 2 }$ 作为参考依据。同时结合最小信息量AIC（AkaikeInformationCriterion）准则来确定最优模型，调整的 $R ^ { 2 }$ 越大，AIC越小，模型效果越好；采用统计量Ljung-BoxQ来检验残差序列是否显著自相关，若 $P > 0 . 0 5$ ，说明拟合后的残差序列为白噪声序列;采用绝对误差绝对值平均(AE)、相对误差绝对值平均(RE）、均方根误差(RMSE)评价模型参数;采用Nash-Sutclife效率系数(NSE)对模型进行评价。其中NSE被用来验证实测值与模拟值间的拟合情况，该值越接近于1,模型的效率越高，适用性越强。各指标公式如下：

$$
\mathrm { A I C } = - 2 \ln { \cal L } + 2 k
$$

$$
\mathrm { A E = \left| E T _ { \mathrm { { s } } } - E T _ { \mathrm { { u } } } \right| }
$$

$$
\mathrm { R E } = \left| ( \mathrm { E T _ { s } } - \mathrm { E T _ { u } } ) / \mathrm { E T _ { u } } \times 1 0 0 \% \right|
$$

$$
\mathrm { R M S E } = \sqrt { \frac { \sum ( \mathrm { E T _ { s } - E T _ { M } } ) ^ { 2 } } { N _ { s } } }
$$

$$
\mathrm { N S E } = 1 . 0 - \frac { \sum ( \mathrm { E T _ { s } - E T _ { M } } ) ^ { 2 } } { \sum ( \mathrm { E T _ { M } - E T _ { A V E } } ) ^ { 2 } }
$$

式中： $L$ 为模型极大似然函数; $k$ 为模型独立参数个数； $N _ { s }$ 为样本数; $\mathrm { E T _ { s } }$ 为模拟值; $\mathrm { E T _ { M } }$ 为实测值; $\mathrm { E T _ { A V E } }$ 为 $\mathrm { E T _ { M } }$ 的平均值。

# 1.4数据处理

采用Excel2010软件对数据进行预处理；采用SPSS19.0和Eviews7.2软件进行数据分析和建模；采用Origin9.4软件绘图;采用LSD(Least SignificantDifference)法对饱和水汽压差值进行多重比较；采用小波方差确定序列变化的主周期。

# 2 结果与分析

# 2.1西北地区饱和水汽压差变化特征

由图1可以看出，1990—2019年，各省(区)年均饱和水汽压差为新疆(XJ) $>$ 宁夏(NX) $>$ 陕西$\left( \mathrm { S N } \right) >$ 甘肃 $\mathrm { ( G S ) > }$ 青海(QH)。QH的饱和水汽压差年际波动相对较小，而SN、GS、NX和XJ四省（区）的饱和水汽压差年际波动较大。各省(区)饱和水汽压差年际变率分别为 $0 . 3 2 \%$ (SN）、 $0 . 2 4 \%$ (GS）、$0 . 3 2 \%$ (NX）、 $0 . 1 9 \%$ (QH)和 $0 . 2 9 \%$ (XJ）。对各省（区）年际饱和水汽压差进行线性趋势判断，NX和XJ年际倾向斜率较高,分别为 $0 . 0 3 6 \mathrm { \ k P a } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 } ( k _ { 3 } )$ 和 $0 . 0 3 3 \mathrm { \ k P a } { \cdot } ( 1 0 \mathrm { a } ) ^ { - 1 } ( k _ { 5 } )$ 。其次为GS、QH和SN，分别为 $0 . 0 2 6 \mathrm { \ k P a } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 } \left( k _ { 2 } \right)$ ） $0 . 0 2 1 \mathrm { \ k P a } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 } \left( k _ { 4 } \right)$ 和$0 . 0 1 2 \mathrm { \ k P a } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 } ( k _ { 1 } )$ 。说明 $3 0 \mathrm { a }$ 来宁夏和新疆的饱和水汽压差整体水平上升趋势比其他省份明显，其注： $k _ { 1 } { \sim } k _ { 5 }$ 分别表示陕西、甘肃、宁夏、青海和新疆的饱和水汽压差倾向斜率；字母SN表示陕西省，GS表示甘肃省，NX表示宁夏回族自治区，QH表示青海省，XJ表示新疆维吾尔族自治区。下同。

他各省的饱和水汽压差上升趋势较小。

各省(区)饱和水汽压差演变过程存在周期性振荡特征(图2)，表现为年代际的变化，且各省（区）的周期性变化规律较为相似，主要表现为15\~20a的振荡周期，此周期的振荡周期信号能力最强，周期性变化最为明显。该尺度周期在整个研究期表现稳定且具有全域性，说明近30a来西北地区饱和水汽压差周期性变化表现较为平稳。小波方差可以反映饱和水汽压差序列的波动随时间尺度的分布，可用来确定饱和水汽压差变化过程存在的主周期。由图2还可以看出，各省(区)在5a、16a时间尺

![](images/02585292ec80a40fcc14bf7b7fc316d6b3df093d144ae752ef7918de73838ca8.jpg)  
图11990—2019年西北五省(区)饱和水汽压差 Fig.1VPD of five provinces (regions) in Northwest China from 1990-2019   
图2各省(区)饱和水汽压差小波分析  
Fig.2 Wavelet coefficients and wavelet variance of VPD among the five provinces (regions)

-0.90-0.70-0.50-0.30-0.100.10 0.30 0.500.70 0.901.101.3030252015105 30252015105 b 30252015105 BON 30252015105e/阳物秘物 1990 你物物加 2012019 现的物物物 1990 海物物物 阳你物s 初初 3 5 6年份 年份 年份 年份 年份0.15 0.12 0.18 0.06 0.360 0.08 0.12 0.04 0.240.04 0.06 0.02 0.120.00 0.00 0.00 0.00 0.0015101520 2530 151015 20 2530 151015 202530 151015202530 15 10 15 20 25 30时间尺度/a 时间尺度/a 时间尺度/a 时间尺度/a 时间尺度/a

度存在极值， $1 6 \mathrm { ~ a ~ }$ 左右的尺度周期对小波方差贡献率最高，达 $7 . 7 5 \%$ ，为饱和水汽压差变化的主周期。同时，陕西、甘肃和新疆还存在24\~27a的周期特征，但方差贡献率较小，为 $2 . 8 0 \% { \sim } 3 . 1 4 \%$ Q

由图3可以看出，西北五省中，XJ月最高饱和水汽压差达 $2 . 3 4 \mathrm { \ k P a }$ ,其次为NX、SN、GS 和QH,分别为 $1 . 6 8 , 1 . 4 2 , 1 . 1 5 \mathrm { k P a }$ 和 $0 . 7 8 \mathrm { k P a }$ 。各省(区)年均饱和水汽压差以XJ最高（图4)，为 $0 . 6 1 \mathrm { \ k P a }$ ，其次为NX、SN、GS和QH,分别为 $0 . 5 4 , 0 . 4 8 , 0 . 4 6 \mathrm { ~ k P a }$ 和$0 . 3 6 \mathrm { k P a }$ 。由图5可以看出，1月和2月SN月均饱和水汽压差无显著差异，其余各省(区)各月均存在显著性差异( $\left( P < 0 . 0 5 \right)$ ,7—12月各省(区)饱和水汽压差各月均存在显著性差异 $( P < 0 . 0 5 )$ 。12、1月和2月GS和NX无显著性差异，11、12、1月和2月SN和GS存在显著性差异 $\left( P < 0 . 0 5 \right)$ 。另外，1月和2月GS和NX无显著性差异，11、12、1月和2月SN和GS存在显著性差异( $\cdot P < 0 . 0 5 ,$ 。

![](images/e28d56126582bc33ead5b7c11c2790d5528d545c0686691ccc08810e12075f4c.jpg)  
图41990—2019年西北五省(区)年饱和水汽压差特征Fig.4 Characteristics of annual VPD in five provinces(regions) of Northwest China from 1990-2019

# 2.2模型选择及参数率定

由表1可以看出，QH和XJ饱和水汽压差原始序列单位根统计 $( T )$ 均大于 $1 \% . 5 \%$ 和 $1 0 \%$ 水平的值，因此不能拒绝原假设，即序列非平稳。NX和GS饱和水汽压差原始序列 $T$ 值小于 $5 \%$ 和 $1 0 \%$ 水平的值，大于 $1 \%$ 水平的值，说明在 $1 \%$ 水平下不能拒绝原假设。SN饱和水汽压差原始序列 $T$ 值均小于 $1 \%$ /$5 \%$ 和 $1 0 \%$ 水平的值，但仍存在 $0 . 1 \%$ 的概率接受原假设。对序列一阶差分后，各省(区)饱和水汽压差原始序列 $T$ 值均小于 $1 \% . 5 \%$ 和 $1 0 \%$ 水平的值，接受原假设概率为0，说明在 $1 \% . 5 \%$ 和 $10 \%$ 水平下拒绝原假设。因此可以确定序列平稳，ARIMA模型参数$d$ 取值为1。

由图6可以看出，一阶差分后各省平稳序列自相关系数(ACF)均在1期后衰减为小值波动的过程较为突然，可视为一阶截尾，由此可以确定一阶差分序列服从MA（1)。对于SN、GS、NX和QH，偏自相关系数(PACF)在1期后衰减波动较大，3期后逐

2.5 250383 SNZZGSNXQHXJ Ae Af Bf Bd Ad Cd D Cccd Aa Ba Ba Ba Ca AN AaBbBCbCbDb X ABb Bc Ac 直网 Cc Ac Dd 1 Aa 2 Ab 3 4 5 6 Ba Ac 105 CaCa 泰 CbCb 泰 Bb CcCcBc Do CdcaBd Dd Ad AeCe ABDBCe Af BCf Bf Cf Df 0.0 Z网 X IAN 7 8 9 10 11 12 月份

![](images/53fb41730d1a215923dbb4a921d0e03dc4ea665770812738176fa126b5c0b55d.jpg)  
图31990—2019年西北五省(区)月饱和水汽压差特征Fig.3Characteristics of monthly VPD in five provinces(regions) ofNorthwest China from 1990-2019  
注：小写字母表示同一省份各月份水汽压差差异显著性，大写字母表示同一月份各省份水汽压差差异显著性，不同字母表示差异显著( $\cdot P < 0 . 0 5$ 。  
图51990—2019年西北五省月均饱和水汽压差比较  
Fig.5 Comparison of monthly mean VPD in five provinces of Northwest China from 1990-2019

# 表1各省(区)饱和水汽压差序列ADF检验结果

Tab.1 ADF test results of VPD series among the five provinces (regions)   

<html><body><table><tr><td colspan="2"></td><td>SN</td><td>GS</td><td>NX</td><td>QH</td><td>XJ</td></tr><tr><td rowspan="5">原始序列</td><td>T</td><td>-4.20</td><td>-2.87</td><td>-3.01</td><td>-2.52</td><td>-2.05</td></tr><tr><td>1%</td><td>-3.45</td><td>-3.45</td><td>-3.45</td><td>-3.45</td><td>-3.45</td></tr><tr><td>5%</td><td>-2.86</td><td>-2.86</td><td>-2.86</td><td>-2.86</td><td>-2.86</td></tr><tr><td>10%</td><td>-2.57</td><td>-2.57</td><td>-2.57</td><td>-2.57</td><td>-2.57</td></tr><tr><td>AP/%</td><td>0.10</td><td>4.90</td><td>3.50</td><td>11.20</td><td>26.56</td></tr><tr><td rowspan="5">一阶差分</td><td>T</td><td>-17.68</td><td>-15.18</td><td>-15.36</td><td>-18.36</td><td>-22.37</td></tr><tr><td>1%</td><td>-2.58</td><td>-2.58</td><td>-2.58</td><td>-2.58</td><td>-2.58</td></tr><tr><td>5%</td><td>-1.94</td><td>-1.94</td><td>-1.94</td><td>-1.94</td><td>-1.94</td></tr><tr><td>10%</td><td>-1.62</td><td>-1.62</td><td>-1.62</td><td>-1.62</td><td>-1.62</td></tr><tr><td>AP/%</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td></tr></table></body></html>

注：AP表示接受概率;SN表示陕西省,GS表示甘肃省,NX表示宁夏回族自治区,QH表示青海省，XJ表示新疆维吾尔族自治区。下同。

渐在置信区间内小范围波动，因此可认为服从AR(1）、AR(2)或AR(3)。对于XJ，PACF在2期后快速衰减至置信区间范围波动，因此可以考虑AR(2)或AR(3)。综上所述，初步选择ARIMA模型如表2所示，对不同模型进行比较，最终筛选出SN、GS和XJ的最优ARIMA模型为：ARIMA（3,1,1)；NX为ARI-MA(1,1,1)；QH为ARIMA(2,1,1)。筛选的最优指数模型如表3所示。

# 2.3模型模拟及效果分析

模型残差检验发现，当指数模型样本步长至少为4a，ARIMA模型样本步长至少为6a时，模型才有效。因此对指数模型设置了步长为 $4 { \sim } 3 0 \mathrm { a }$ 间隔为2a的样本数据；对ARIMA模型设置了步长为 $6 \sim$ $3 0 \mathrm { ~ a ~ } .$ 间隔为2a的样本数据。经分析比较，筛选出各模型最佳样本步长(表4)。为实现序列的连续性并对各省(区)2020年及以后的饱和水汽压差进行预测，因此确定了指数模型拟合时段为2016一2019年，ARIMA(3,1,1)和ARIMA(2,1,1)模型拟合时段为2004—2019年，ARIMA（1,1,1）模型拟合时段为1998—2019年。

设置预测步长分别为3、5、7a和9a,以最佳样本步长建立模型并进行回归分析(表5)。预测步长为3a时Holt指数平滑的 $R ^ { 2 }$ 和NSE均表现最高，随着预测步长增加拟合度下降。不同预测步长下，Holt-Winters指数平滑模型的 $R ^ { 2 }$ 相差不大，但在预测步长为3a时误差最小，且模型的NSE最大，说明模型效率更高。ARIMA(3,1,1)和ARIMA(1,1,1)模型分别在预测步长为7a和5a时拟合度和模型效率更高。ARIMA(2,1,1)模型在各预测步长条件下 $R ^ { 2 }$ 无明显差异，但步长为7a时误差表现更小，NSE更高。

综上所述，指数模型最佳预测步长为3a;ARI-MA(3.1.1)和ARIMA(2.1,1)模型最佳预测步长为7a;ARIMA(1,1,1)模型最佳预测步长为 $5 \mathrm { ~ a ~ }$ 。相对于指数模型，ARIMA模型的RMSE平均减少 $4 2 . 3 \% , R ^ { 2 }$ 平均提高 $1 1 . 1 \%$ ,NSE平均提高 $1 7 . 7 \%$ ○

# 2.4模型预测

根据筛选的最佳预测步长，确定指数模型的预测尺度为2020—2022年；ARIMA（3,1,1)和ARIMA(2.1,1)模型的预测尺度为2020—2026年；ARIMA(1,1,1)模型的预测尺度为2020—2024年。对各省(区)饱和水汽压差进行预测，结果显示(表6)，未来3a(2020—2022年)陕西和新疆的饱和水汽压差将分别增加 $3 . 6 \%$ 和 $6 . 7 \%$ ,而甘肃、宁夏和青海的饱和水汽压差将有所减小;未来5a(2020—2024年），宁夏饱和水汽压差增加 $9 . 5 \%$ ;2020—2026年，陕西、甘肃、青海和新疆饱和水汽压差均呈不同程度的升高趋势，分别增加 $3 . 6 \% . 8 . 0 \% . 7 . 9 \%$ 和 $8 . 9 \%$ ○

# 3讨论

饱和水汽压差是用于模拟植被气孔导度2和估算蒸散量[32]等生态模型的重要气象参数之一，也是生态系统碳通量及水汽通量研究的主要参考变量[33-34]。饱和水汽压差升高可能会限制陆地生态系统中植物碳吸收和水分利用。部分研究表明，近年来全球饱和水汽压差急剧增长，可能是由于海洋蒸发减少，陆地水汽含量降低[8]。全球气候变暖背景下，近年来西北地区气温升高，极端高温事件发生频次增加[35-36]，这将可能引起饱和水汽压差增大。本研究结果显示，1990—2019年，宁夏和新疆的饱和水汽压差升高趋势明显，这可能与地区温度升高,干燥事件发生频次增加有关[37-38]。降水主要通过影响空气温度和湿度来影响饱和水汽压差[3]，而饱和水汽压差的变化会影响陆面实际蒸散发[39]，从而影响区域的降水状况。近年来，我国西北东部区域降水有明显下降趋势[40],说明降水的减少在一定程度上对饱和水汽压差变化起到了正向作用，使得饱和水汽压差增长趋势明显。本文对西北各省（区）饱和水汽压差进行预测，研究表明，2020—2026年各省(区)饱和水汽压差均呈上升趋势，这可能意味着西北地区的暖干化趋势仍会维持较长一段时间。有研究表明，在温度与降水的双重作用下，整个西北地区仍呈变干的趋势[41],这与本研究结果基本一致。另外，陕西饱和水汽压差年际上升趋势较小，而年际变率相对较大，因此短期的预测可能具有不确定性。但对各省(区)的预测结果进行综合评价分析，从饱和水汽压差与温度变化直接相关这一角度出发，这与前人的研究结果具有较好的一致性[42]。以2016—2019年实测饱和水汽压差和预测饱和水汽压差平均水平进行比较(表7)，发现指数模型预测值在整体上相对于ARIMA模型偏低，即指数模型预测结果会低估饱和水汽压差的平均水平。ARIMA模型预测结果更接近于实际水平，却并不能反映出饱和水汽压差短时间内的波动变化，但分别从指数模型和ARIMA模型对新疆地区饱和水汽压差的预测结果来看，均高于过去阶段的饱和水汽压差水平，预计在未来一段时间内（2020一2026年），新疆地区的饱和水汽压差可能持续上升。而长期保持这种水汽压差升高趋势，将可能产生潜在的土壤干旱和植被退化的风险，因此亟需采取相应的措施，如通过农林产业结构调整，进行水

![](images/09f1876be55d53309346e2aeb3a0cac2dd184811be49e67c410c67bc9b1d040f.jpg)  
图6饱和水汽压差一阶差分序列自相关 Fig.6First-order differential sequence autocorrelation diagram of VPD

Tab.2 Comparison ofARIMA model effects   
表3指数模型效果对比  

<html><body><table><tr><td>省份</td><td>模型</td><td>调整的R</td><td>AIC</td></tr><tr><td>SN</td><td>ARIMA(1,1,1)</td><td>0.45</td><td>-0.32</td></tr><tr><td rowspan="5">GS</td><td>ARIMA(2,1,1)</td><td>0.46</td><td>0.25</td></tr><tr><td>ARIMA(3,1,1)</td><td>0.47</td><td>0.43</td></tr><tr><td>ARIMA(1,1,1)</td><td>0.39</td><td>-0.78</td></tr><tr><td>ARIMA(2,1,1)</td><td>0.45</td><td>-0.02</td></tr><tr><td>ARIMA(3,1,1)</td><td>0.46</td><td>0.22</td></tr><tr><td rowspan="2">NX</td><td>ARIMA(1,1,1)</td><td>0.38</td><td>-0.04</td></tr><tr><td>ARIMA(2,1,1)</td><td>0.38</td><td>0.70</td></tr><tr><td rowspan="3">QH</td><td>ARIMA(3,1,1)</td><td>0.37</td><td>0.92</td></tr><tr><td>ARIMA(1,1,1)</td><td>0.43</td><td></td></tr><tr><td>ARIMA(2,1,1)</td><td></td><td>-1.80</td></tr><tr><td rowspan="3">XJ</td><td></td><td>0.47</td><td>-0.99</td></tr><tr><td>ARIMA(3,1,1)</td><td>0.47</td><td>-0.76</td></tr><tr><td>ARIMA(2,1,1) ARIMA(3,1,1)</td><td>0.49 0.50</td><td>1.81 2.06</td></tr></table></body></html>

表2ARIMA模型效果对比  
表4模型最佳样本步长  

<html><body><table><tr><td>省份</td><td>指数模型</td><td>调整的R</td><td>均方根误差</td></tr><tr><td>SN</td><td>Holt</td><td>0.67</td><td>0.130</td></tr><tr><td>GS</td><td>Holt-Winters</td><td>0.70</td><td>0.081</td></tr><tr><td>NX</td><td>Holt-Winters</td><td>0.69</td><td>0.120</td></tr><tr><td>QH</td><td>Holt-Winters</td><td>0.71</td><td>0.046</td></tr><tr><td>XJ</td><td>Holt-Winters</td><td>0.68</td><td>0.103</td></tr></table></body></html>

Tab.3 Comparison of exponential model effects   
Tab.4 Optimum sample step among the five models   

<html><body><table><tr><td>模型</td><td>最佳样本步长/a</td><td>均方根误差</td><td>平均绝对误差</td></tr><tr><td>Holt</td><td>4</td><td>0.086</td><td>0.067</td></tr><tr><td>Holt-Winters</td><td>4</td><td>0.076</td><td>0.053</td></tr><tr><td>ARIMA(3,1,1)</td><td>16</td><td>0.113</td><td>0.079</td></tr><tr><td>ARIMA(2,1,1)</td><td>16</td><td>0.048</td><td>0.036</td></tr><tr><td>ARIMA(1,1,1)</td><td>22</td><td>0.130</td><td>0.092</td></tr></table></body></html>

Tab.5 Comparison of output parameters of models with different predicted steps   
表6指数模型和ARIMA模型的预测结果  

<html><body><table><tr><td>模型</td><td>模拟步长/a</td><td>R</td><td>均方根误差</td><td>相对误差/%</td><td>绝对误差/kPa</td><td>NSE</td></tr><tr><td rowspan="4">Holt</td><td>3</td><td>0.76</td><td>0.1809</td><td>21.3</td><td>0.1196</td><td>0.6713</td></tr><tr><td>5</td><td>0.75</td><td>0.1935</td><td>22.3</td><td>0.1327</td><td>0.6383</td></tr><tr><td>7</td><td>0.73</td><td>0.1924</td><td>22.5</td><td>0.1320</td><td>0.6233</td></tr><tr><td>9</td><td>0.73</td><td>0.1910</td><td>23.2</td><td>0.1347</td><td>0.6292</td></tr><tr><td rowspan="4">Holt-Winters</td><td>3</td><td>0.95</td><td>0.0939</td><td>9.8</td><td>0.0584</td><td>0.9207</td></tr><tr><td>5</td><td>0.96</td><td>0.1003</td><td>11.7</td><td>0.0688</td><td>0.9128</td></tr><tr><td>7</td><td>0.95</td><td>0.1080</td><td>12.9</td><td>0.0734</td><td>0.9013</td></tr><tr><td>9</td><td>0.94</td><td>0.1154</td><td>14.4</td><td>0.0802</td><td>0.8901</td></tr><tr><td rowspan="4">ARIMA(3,1,1)</td><td>3</td><td>0.97</td><td>0.0926</td><td>17.1</td><td>0.0735</td><td>0.9543</td></tr><tr><td>5</td><td>0.96</td><td>0.0878</td><td>15.9</td><td>0.0699</td><td>0.9566</td></tr><tr><td>7</td><td>0.97</td><td>0.0854</td><td>17.7</td><td>0.0697</td><td>0.9589</td></tr><tr><td>9</td><td>0.96</td><td>0.0878</td><td>17.4</td><td>0.0718</td><td>0.9553</td></tr><tr><td rowspan="4">ARIMA(2,1,1)</td><td>3</td><td>0.94</td><td>0.0537</td><td>9.6</td><td>0.0363</td><td>0.9096</td></tr><tr><td>5</td><td>0.94</td><td>0.0512</td><td>9.2</td><td>0.0363</td><td>0.9114</td></tr><tr><td>7</td><td>0.94</td><td>0.0461</td><td>8.7</td><td>0.0326</td><td>0.9256</td></tr><tr><td>9</td><td>0.92</td><td>0.0497</td><td>8.8</td><td>0.0347</td><td>0.9154</td></tr><tr><td rowspan="4">ARIMA(1,1,1)</td><td>3</td><td>0.92</td><td>0.1111</td><td>15.0</td><td>0.0852</td><td>0.9098</td></tr><tr><td>5</td><td>0.93</td><td>0.1063</td><td>14.9</td><td>0.0794</td><td>0.9250</td></tr><tr><td>7</td><td>0.93</td><td>0.1081</td><td>14.9</td><td>0.0807</td><td></td></tr><tr><td>9</td><td>0.92</td><td>0.1024</td><td>14.7</td><td>0.0806</td><td>0.9243 0.9222</td></tr></table></body></html>

表5不同预测步长下模型输出参数比较  

<html><body><table><tr><td></td><td>SN</td><td>尺度/a</td><td>GS</td><td>尺度/a</td><td>NX</td><td>尺度/a</td><td>QH</td><td>尺度/a</td><td>XJ</td><td>尺度/a</td></tr><tr><td>MV/(kPa·mon-1)</td><td>0.55</td><td>1</td><td>0.50</td><td>1</td><td>0.63</td><td>1</td><td>0.38</td><td>1</td><td>0.90</td><td>1</td></tr><tr><td>PV-E/(kPa·mon-1)</td><td>0.57</td><td>3</td><td>0.43</td><td>3</td><td>0.61</td><td>3</td><td>0.32</td><td>3</td><td>0.96</td><td>3</td></tr><tr><td>PV-A /(kPa·mon-1)</td><td>0.57</td><td>7</td><td>0.54</td><td>7</td><td>0.69</td><td>5</td><td>0.41</td><td>7</td><td>0.98</td><td>7</td></tr></table></body></html>

注：MV表示实测值;PV-E表示指数模型预测值;PV-A表示ARIMA模型预测值。下同。

# 表7水汽压差预测值与实测值水平比较

Tab.6Prediction resultsof exponential models and ARIMA models   
Tab.7 Comparison between predicted values and measured values ofVPD   

<html><body><table><tr><td>省份</td><td>SN</td><td>GS</td><td>NX</td><td>QH</td><td>XJ</td></tr><tr><td>MV/(kPa·mon-1)</td><td>0.58</td><td>0.53</td><td>0.68</td><td>0.40</td><td>0.95</td></tr><tr><td>PV-E/(kPa·mon-1)</td><td>0.57</td><td>0.52</td><td>0.66</td><td>0.39</td><td>0.94</td></tr><tr><td>PV-A /(kPa·mon-1)</td><td>0.56</td><td>0.54</td><td>0.68</td><td>0.41</td><td>0.95</td></tr></table></body></html>

资源合理分配等来降低这种风险。

指数平滑和ARIMA模型广泛应用于各个研究领域[28.43],尤其是ARIMA模型的预测能力具有显著优势[28]。李俐等[27]采用ARIMA模型和径向基神经网络预测夏玉米单产量，结果表明ARIMA模型精度更高。Duan等[43]等采用指数平滑模型预测地下水位取得较好结果。本文应用指数模型和ARIMA模型对西北五省(区)饱和水汽压差进行模拟和预测，结果表明，相对于指数模型，ARIMA模型均方根误差平均减少 $4 2 . 3 \%$ ，决定系数 $R ^ { 2 }$ 平均提高 $1 1 . 1 \%$ ，Nash-Sutclife效率系数平均提高 $1 7 . 7 \%$ ,ARIMA模型的拟合度更高，预测能力更好。

影响饱和水汽压差变化的因素错综复杂，包括与其直接相关的大气温度和湿度，而大气温度和湿度又受经纬度、海拔、太阳辐射以及人类活动等多种要素的影响。饱和水汽压差预测精度的关键是模型选择，为进一步提高模型的适用性和预测精度，在今后的研究中可尝试更多的优化模型和组合模型，以期增强模型对饱和水汽压差趋势变化的识别能力。另外,样本和预测步长均会对预测结果产生影响。本文通过对比分析不同模型、不同样本步长和预测步长对模型产生的误差，筛选最优模型结构、最佳样本步长和预测步长，建立的饱和水汽压差指数预测模型可解释 $7 6 \%$ 以上的变量，纳什效率系数达0.6以上；ARIMA模型可解释 $9 3 \%$ 以上的变量，纳什效率系数达0.9以上，有效提高了饱和水汽压差的预测精度。ARIMA模型结构简洁直观，准确率高，适用性好，可为西北地区饱和水汽压差的预测提供参考。

# 4结论

（1）近 $3 0 \mathrm { ~ a ~ }$ 来，整体上西北地区饱和水汽压差呈上升趋势。宁夏和新疆的饱和水汽压差增幅最为明显,分别为 $0 . 0 3 6 \mathrm { k P a } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 和 $0 . 0 3 3 \mathrm { { k P a } } \cdot ( 1 0 \mathrm { { a } } ) ^ { - 1 }$ ，其次为甘肃、青海和陕西，分别为 $0 . 0 2 6 , 0 . 0 2 1 \mathrm { ~ k P a }$ .$\left( 1 0 \mathrm { a } \right) ^ { - 1 }$ 和 $0 . 0 1 2 \mathrm { ~ k P a } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ;西北各省(区)饱和水汽压差存在以5a和16a为中心尺度的周期，16a周期对方差贡献最大，达 $7 . 7 5 \%$ ，为饱和水汽压差变化的主周期。

（2）根据现有观测资料，预计未来7a(2020—2026年)西北地区饱和水汽压差继续升高。至2026年，陕西、甘肃、青海和新疆的饱和水汽压差将分别增加 $3 . 6 \% . 8 . 0 \% . 7 . 9 \%$ 和 $8 . 9 \%$ ;至2024年，宁夏饱和水汽压差增加 $9 . 5 \%$ ；甘肃、宁夏和青海地区的饱和水汽压差在2020—2022年有所回落，但总体仍呈上升趋势。

（3）相较于指数模型，ARIMA模型误差小，拟合度好，对变量的解释度高，适用性强，能更好的对饱和水汽压差进行预测，在今后的研究中，ARIMA模型可以作为西北地区气候预测模型选择的重要参考。

# 参考文献(References):

[1]Grossiord C, Buckley T N, Cernusak L A, et al.Plant responses to rising vapor pressure deficit[J]. The New Phytologist, 2O20. DOI: 10.1111/nph.16485.   
[2]Hatfield JL, Prueger JH. Temperature extremes: Effct on plant growth and development[J]. Weather and Climate Extremes,2015, 10(PA): 4-10.   
[3]Kimm H, Guan K Y,Gentine P,et al. Redefining droughts for the U.S. Corn Belt: The dominant role of atmospheric vapor pressure deficit over soil moisture in regulating stomatal behavior of Maize and Soybean[J].Agricultural and Forest Meteorology,2020,287. DOI: 10.1016/j.agrformet.2020.107930.   
[4]Williams A P,Allen C D,Macalady A K,et al. Temperature as a potent driver of regional forest drought stress and tree mortality[J]. Nature Climate Change,2013,3(3): 292-297.   
[5]Asseng S,Ewert F, Martre P,et al. Rising temperatures reduce global wheat production[J]. Nature Climate Change,2O15,5(2): 143-147.   
[6]Zhao C,Liu B,Piao S L,et al. Temperature increase reduces global yields of major crops in four independent estimates[J]. Proceedings of the National Academy of Sciences of the United States of America,2017,114(35): 9326-9331.   
[7]Zhang K, KimballJS, Nemani R R,et al. Vegetation greening and climate change promote multidecadal rises of global land evapotranspiration[J]. Scientific Reports,2015,5: 15956.DOI: 10.1038/ srep15956.   
[8]Yuan W P, Zheng Y,Piao S L,et al. Increased atmospheric vapor pressure deficit reduces global vegetation growth[J]. Science Advances,2019,5(8): eaax1396.   
[9]Massmann A,Gentine P,Lin C J. When does vapor pressure deficit drive or reduce evapotranspiration?[J]. Journal of Advances in Modeling Earth Systems,2019,11(10): 3305-3320.   
[10]Dai A G.Increasing drought under global warming in observations and models[J]. Nature Climate Change,2013,3(1): 52-58.   
[11] 李旭谱,张福平,胡猛,等.基于SPOT NDVI的植被覆盖时空演 变规律分析——以西北五省为例[J].干旱地区农业研究, 2012,30(5): 180-184,199.[Li Xupu,Zhang Fuping,Hu Meng,et al.Analysis of the regulation of spatial-temporal variation of the vegetation coverage based on SPOT NDVI data: A case study in Northwest China[J].Agricultural Research in the Arid Areas, 2012,30(5): 180-184,199.]   
[12] 赵传成,王雁,丁永建,等.西北地区近50年气温及降水的时空 变化[J].高原气象,2011,30(2):385-390.[Zhao Chuancheng, Wang Yan,Ding Yongjian,et al. Spatial- temporal variations of temperature and precipitation in Northern China in recent 5O years [J].Plateau Meteorology,2011,30(2): 385-390.]   
[13] 刘宪锋,潘耀忠,张锦水,等.1960—2011年西北五省潜在蒸散 的时空变化[J].应用生态学报,2013,24(9):2564-2570.[Liu Xianfeng,Pan Yaozhong, Zhang Jinshui,et al. Spatiotemporal variation patterns of potential evapotranspiration in five provinces of Northwest China in 1960-2011[J]. Chinese Journal of Applied Ecology,2013,24(9): 2564-2570.]   
[14] 黄小燕,李耀辉,冯建英,等.中国西北地区降水量及极端干旱 气候变化特征[J].生态学报,2015,35(5):1359-1370.[Huang Xiaoyan,Li Yaohui, Feng Jianying,et al. Climate characteristics of precipitation and extreme drought events in Northwest China[J]. Acta Ecologica Sinica,2015,35(5): 1359-1370.]   
[15] 陈小平,刘廷玺,王冠丽,等.温度和水分对科尔沁草甸湿地净 生态系统碳交换量的影响[J].应用生态学报,2018,29(5): 1523-1534.[Chen Xiaoping,Liu Tingxi, Wang Guanli,et al.Effects of temperature and moisture on net ecosystem CO $2$ exchange over a meadow wetland in the Horqin, China[J]. Chinese Journal of Applied Ecology,2018,29(5): 1523-1534.]   
[16] 蒋浩,葛继稳,刘垚垚,等.大九湖亚高山泥炭湿地潜热通量特 征及其对环境因子的响应[J].安全与环境工程,2020,27(4): 31-40.[Jiang Hao,Ge Jiwen,Liu Yaoyao,et al. Characteristics of latent heat flux in Dajiuhu sub-alpine peat wetland and its response to environmental factors[J]. Safety and Environmental Engineering,2020,27(4): 31-40.]   
[17] CardosoAA,Brodribb TJ,Kane C N,et al.Osmoticadjustment and hormonalregulatioof stomatalresponses to vapourpressure deficit in sunflower[J].AobPlants,2020,12(4).DOI: 10.1093/aobpla/plaa025/5860156.   
[18] 曾红霞,刘强,赵强.西北地区昼夜增温的不对称性对植被动态 的影响[J].生态环境学报,2020,29(2):260-265.[Zeng Hongxia, Liu Qiang, Zhao Qiang. Asymmetry of day and nightime warming and their effcts on vegetation dynamics in the Inland areas of Northwest China[J]. Ecology and Environmental Sciences,2020, 29(2): 260-265.]   
[19] 张静,王力.黄土塬区苹果园蒸散与环境因素的关系[J].林业科 学,2018,54(3): 29-38.[Zhang Jing,Wang Li. The relationship between the evapotranspiration and the environmental factors in the apple orchards in the Loess Tableland Area[J]. Scientia Silvae Sinicae,2018,54(3): 29-38.]   
[20] 姚增旺,褚建民,吴利禄,等.民勤绿洲荒漠过渡带梭梭树干液 流的时滞特征[J].应用生态学报,2018,29(7):2339-2346.[Yao Zengwang, Chu Jianmin,Wu Lilu, et al. Time lag characteristics of the stem sap flow of Haloxylon ammodendron in the Minqin oasis-desertectone,China[J].Chinese Jouralof AppliedEcology, 2018,29(7): 2339-2346.]   
[21] 韩磊,何俊,齐拓野,等.宁夏河东沙区侧柏冠层气孔导度对环 境因子的响应及其模拟[J].生态学杂志,2018,37(9):2862- 2868. [Han Lei, He Jun, Qi Tuoye, et al. Responses and modeling

of canopy stomatal conductance of Platycladus orientalis to envi

ronmental factors in Hedong sandy land,Ningxia[J]. Chinese Journal of Ecology,2018,37(9): 2862-2868.]   
[22]肖晶晶,李正泉,郭芬芬,等.浙江省1901—2017年降水序列构 建及变化特征分析[J].气候变化研究进展,2018,14(6):553- 561.[Xiao Jingjing,Li Zhengquan, Guo Fenfen, et al. Construction and analysis of annual precipitation series from 190l to 2O17 in Zhejiang province[J]. Climate Change Research,2018,14(6): 553-561.]   
[23] 沈皓俊,罗勇,赵宗慈,等.基于LSTM网络的中国夏季降水预 测研究[J].气候变化研究进展,2020,16(3):263-275.[Shen Haojun,Luo Yong, Zhao Zongci, et al.Prediction of summer precipitation in China based on LSTM network[J]. Climate Change Research,2020,16(3): 263-275.]   
[24] 张遇春,张勃.黑河中游近49年降水序列变化规律及干旱预测 以张掖市为例[J].干旱区资源与环境,2008,22(1):84-88. [Zhang Yuchun, Zhang Bo. Study on the prccipitation change and drought prediction of middle reach of Heihe river in current 49 years: Take Zhangye City as an example[J]. Journal of Arid Land Resources and Environment, 2008, 22(1): 84-88.]   
[25] 史亚军,彭勇,徐炜.基于灰色离散微分动态规划的梯级水库优 化调度[J].水力发电学报,2016,35(12):35-44.[Shi Yajun, Peng Yong,Xu Wei. Optimal operation model of cascade reservoirs based on grey discrete differential dynamic programming[J]. Journal of Hydroelectric Engineering,2016,35(12):35-44.]   
[26] 张姝玮,郭忠印,陈立辉.基于自回归求积移动平均的制动器温 度预测方法[J].吉林大学学报(工学版),2020,50(6):2080- 2086.[Zhang Shuwei, Guo Zhongyin, Chen Lihui. Brake temperature prediction method based on autoregressive integrated moving average model[J]. Journal of Jilin University(Engineering and Technology Edition),2020,50(6): 2080-2086.]   
[27] 李俐,许连香,王鹏新,等.基于叶面积指数的河北中部平原夏 玉米单产预测研究[J].农业机械学报,2020,51(6):198-208. [LiLi,Xu Lianxiang,Wang Pengxin,et al.Summer maize yield forecasting based on leaf area index[J]. Transactions of the Chinese Society for Agricultural Machinery,2020,51(6): 198-208.]   
[28] Zhang YH, Yang HR,Cui HJ,et al. Comparison of the ability of ARIMA,WNN and SVM models for drought forecasting in the Sanjiang Plain, China[J]. Natural Resources Research,2O20,29(2): 1447-1464.   
[29]田东,韦鑫化,王悦,等.基于MA-ARIMA-GASVR的食用菌温 室温度预测[J].农业工程学报,2020,36(3):190-197.[Tian Dong,Wei Xinhua,Wang Yue,et al.Prediction of temperature in edible fungi greenhouse based on MA-ARIMA-GASVR[J]. Transactions of the Chinese Society of Agricultural Engineering,2020, 36(3): 190-197.]   
[30] 刘立龙,陈军,黄良珂,等.基于Holt指数平滑模型的 Klobuchar 模型精化[J].武汉大学学报(信息科学版),2018,43(4):599-604. [Liu Lilong,Chen Jun,Huang Liangke,et al.A sophisticated Klobuchar model based on the Holt exponential smoothing model

[J].Geomatics and Information Science of Wuhan University,

2018,43(4): 599-604.]   
[31] 杨刚,张浩.基于三次指数平滑法的水泡陈化钢渣中f-CaO含 量长期变化趋势研究[J].材料导报,2015,29(24):112-116. [Yang Gang, Zhang Hao,Research on long-term variation tendency of f-CaO content in sodden aging steel slag based on Holt-winters[J]. Materials Reports,2015,29(24): 112-116.]   
[32] 段利民,童新,吕扬,等.固沙植被黄柳、小叶锦鸡儿蒸腾耗水尺 度提升研究[J].自然资源学报,2018,33(1):52-62.[Duan Limin,Tong Xin,Lyu Yang,et al. Upscaling of the transpiration and water consumption of sand-fixing vegetation Salix gordejevi and Caragana microphylla[J]. Journal of Natural Resources,2018,33 (1): 52-62.]   
[33] 葛蓉,何洪林,任小丽,等.基于模型数据融合的中国温带和亚 热带典型森林生态系统碳通量模拟[J].生态学报,2017,37(5): 1409-142O.[Ge Rong,He Honglin,Ren Xiaoli,et al. Carbon flux simulation of typical temperate and subtropical forest ecosystems in China based on model-data fusion approach[J]. Acta Ecologica Sinica,2017,37(5): 1409-1420.]   
[34] 刘玉莉,江洪,周国模,等.安吉毛竹林水汽通量变化特征及其 与环境因子的关系[J].生态学报,2014,34(17):4900-4909. [Liu Yuli, Jiang Hong,Zhou Guomo,et al.Water vapor flux variation characteristic and the relationship with its environment factors in phyllostachys edulis forest in Anji[J].Acta Ecologica Sinica,2014,34(17): 4900-4909.]   
[35] 杨秋萍,徐长春,张晋霞,等.2001—2017年开都-孔雀河流域 植被物候特征及其对气候变化的响应[J].干旱区研究,2020, 37(3):729-738.[Yang Qiuping,Xu Changchun, Zhang Jinxia,et al.Phenological characteristics of vegetation and its response to climatic change in the Kaidu-Kongqi River basin,Xinjiang,during 2001-2017[J]. Arid Zone Research,2020,37(3): 729-738.]   
[36] 李博,陈婷,王楠,等.2017年与2014年西安极端高温天气及其 环流特征对比分析[J].干旱区研究,2019,36(3):645-656.[Li Bo, Chen Ting,Wang Nan, et al. Extremely high temperature and circulation features in Xi'an in 2017 and 2014[J].Arid Zone Research,2019,36(3): 645-656.]   
[37] 戴新刚,任宜勇,陈洪武.近50年新疆温度降水配置演变及其 尺度特征[J].气象学报,2007,65(6):1003-1010.[Dai Xingang, Ren Yiyong,Chen Hongwu. Multi-scale feature of climate and climate shift in Xinjiang over the past 5O years[J].Acta Meteorologica Sinica,2007,65(6): 1003-1010.]   
[38] 孔祥伟,黄玉霞,王勇.1960—2010年宁夏降水和温度极端气 候事件变化分析[J].安徽农业科学,2014,42(9):2683-2688. [Kong Xiangwei,Huang Yuxia,Wang Yong.Changes in extreme climate events of precipitation and temperature in Ningxia from 1960 to 2010[J]. Journal of Anhui Agricultural Sciences,2014,42 (9): 2683-2688.]   
[39] 郭梦瑶,余敦先,张利平,等.渭河流域潜在蒸散量变化的气候 归因[J].资源科学,2020,42(5):907-919.[Guo Mengyao,She Dunxian, Zhang Liping, et al. Climate explanation of the potential evapotranspiration changes in Weihe River Basin[J]. Resources Science,2020,42(5): 907-919.]   
[40] 姬凯,王士新,左洪超,等.东亚副热带急流经向位置对中国西 北东部盛夏降水的影响[J].干旱区研究,2020,37(1):10-17.[Ji Kai,Wang Shixin, Zuo Hongchao,et al. Effect of meridional position of east asian subtropical jet on midsummer precipitation in eastern part of Northwest China[J].Arid Zone Research,2020,37 (1): 10-17.]   
[41] 杨金虎,江志红,刘晓芸,等.近半个世纪中国西北干湿演变及 持续性特征分析[J].干旱区地理,2012,35(1):10-22.[Yang Jinhu,Jiang Zhihong,Liu Xiaoyun,et al．Influence research on spring vegetation of Eurasia to summer drought-wetness over the northwest China[J].Arid Land Geography,2012,35(1): 10-22.]   
[42] 徐影,丁一汇,赵宗慈.人类活动引起的我国西北地区21世纪 温度和降水变化情景分析[J].冰川冻土,2003,25(3):327-330. [Xu Ying,Ding Yihui, Zhao Zongci. Scenario of temperature and precipitation changes in Northwest China due to human activity in the 2lst century[J]. Journal of Glaciology and Geocryology,2003, 25(3): 327-330.]   
[43]Duan G H,Chen D,Niu RQ.Forecasting groundwater level for soil landslide based on a dynamic model and landslide evolution pattern[J]. Water,2019,11(10).DOI: 10.3390/w11102163.

# Prediction of vapor pressure deficit in Northwest China based on exponential and ARIMA models

HAN Yonggui1²2，HAN Lei1,2,3，HUANG Xiaoyu1²，GAO Yang1,2   
(1.School of Recourses and Environment,Ningxia University,Yinchuan 75oO21,Ningxia, China;   
2.China-Arab Joint International Research Laboratory for Featured Resources and Environmental   
Governance in Arid Regions,Yinchuan 75OO21,Ningxia, China; 3.Institute of Environmental Engineering,Ningxia University,Yinchuan 75oO21,Ningxia, China)

Abstract: Vapor pressure deficit (VPD) is a key factor affcting water transport in the soil-plant-atmosphere continum; in the context of global climate change,predicting VPD has practical significance for vegetation management and risk asessment of meteorological disasters affcting agriculture and forestry in Northwest China.Using VPD data from five provinces (regions) in Northwest China from 1990 to 2019,we analyzed the characteristics of VPD interannual variation and periodic variation using trend and wavelet analyses.The optimal sample step and prediction step were selected; exponential models and autoregressive integrated moving average (ARIMA） models were used to simulate and predict VPD in Northwest China.Among the five provinces, Ningxia had the highest trend slope of VPD $[ 0 . 0 3 6 \mathrm { k P a } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 } ] ,$ ，followed by Xinjiang $[ 0 . 0 3 3 \mathrm { ~ k P a } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 } ]$ .The annual average VPD in Xinjiang was the highsest at $0 . 6 1 \mathrm { k P a }$ , followed by Ningxia, Shaanxi, Gansu, and Qinghai 中 $\mathrm { 2 . 5 4 \ k P a }$ ， $0 . 4 8 ~ \mathrm { k P a }$ ， $0 . 4 6 \mathrm { k P a }$ ，and $0 . 3 6 \mathrm { k P a }$ ，respectively).Over the past 30 years,the VPD in Northwest China followed an upward trend; Ningxia and Xinjiang had the largest increases in VPD at 0.036 and $0 . 0 3 3 \mathrm { ~ k P a } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ respectively, followed by Gansu $[ 0 . 0 2 6 \mathrm { k P a } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 } ]$ ,Qinghai $[ 0 . 0 2 1 \mathrm { ~ k P a } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 } ] .$ ,and Shaanxi $[ 0 . 0 1 2 \mathrm { k P a } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 } ]$ Compared with the exponential model, the root mean square error (RMSE)of the ARIMA model was reduced by $42 . 3 \%$ ，the $R ^ { 2 }$ was increased by $1 1 . 1 \%$ , and the Nash-Sutcliffe efficiency coefficient increased by $1 7 . 7 \%$ . Thus, the VPD prediction accuracy was efectively improved. The VPD in Northwest China is expected to increase by varying degrees; Ningxia and Xinjiang showed the highest VPD growth rates of $9 . 5 \%$ and $8 . 9 \%$ ,respectively.

Keywords: vapor pressure deficit; exponential smoothing; ARIMA model; prediction; Northwest China