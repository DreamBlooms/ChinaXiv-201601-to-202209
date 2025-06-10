# 2套气象数据在资料缺乏地区的适用性评估以呼图壁河流域为例

孙铭悦1²，吕海深，朱永华1²，林瑜}²，张梅洁1,2（1.河海大学水文水资源与水利工程科学国家重点实验室,江苏 南京210098;2.河海大学水文水资源学院,江苏 南京 210098)

摘要：在无资料地区,降水、气温等观测资料缺乏,影响洪水预报的准确性,进而影响防汛抗旱、水资源规划等工作的开展。因此,研究无资料地区已有降水、气温数据的适用性分析十分必要。应用包含融雪径流模拟的HBV模型,在呼图壁河流域石门水文站以上区域,基于模拟出的融雪洪水径流与实测径流对比，分别对中国地面降水与气温日值 $0 . 5 ^ { \circ } { \times } 0 . 5 ^ { \circ }$ 格点数据集和气象站观测数据集进行了对比分析及其融雪型径流模拟的适用性分析。结果表明：格点数据驱动下水文模型的融雪径流模拟效果总体优于利用站点观测数据驱动的水文模型。格点数据驱动下水文模型模拟融雪径流的Nash系数在验证期为0.792,站点数据驱动下水文模型模拟融雪径流的Nash系数在验证期为0.433。同时分析了呼图壁河流域融雪洪水的一些特征，并结合驱动数据的不同,分析了模拟融雪径流出现误差的可能原因,为如何提高具有融雪特征的无资料地区融雪型洪水预报准确性提供支撑。

关键词：降水数据；无资料地区；融雪洪水；径流模拟；适用性评估；呼图壁河流域

在融雪融冰地区，进行准确的径流模拟与预报对水资源规划与管理、减少融雪洪水带来的损失十分重要[1-2]。大多数融雪过程发生在高寒地区或河流源头,这些地方往往缺乏实测资料[3]。因此,对于这些具有融雪特征的资料缺乏地区，研究如何提高水文预报准确性十分必要。在高寒山区，降水特征受地形影响较大，复杂的山区地形和局地小气候形成了迥异多变的降水时空分布格局[4]。气温的分布相当程度上也受到地形因素的影响，具有海拔引起的垂直差异[5]。在寒区水文模拟过程中，降水和气温是关键的变量数据[6。在融雪洪水模拟中，降水和气温数据是影响水文模型输入不确定性的重要数据7。降水量是重要的气象要素，往往是水文模型模拟径流时最重要的输入数据[8-10]。因此,对不同来源的驱动数据，如降水、气温数据进行适用性评估，对提高预报的准确性有重要意义。

新疆位于中国西北，是典型的内陆干旱区，内有许多高大山体，在低温条件下，高山区降水形成冰川与积雪,融化后会产生融雪洪水[1]。近 $2 0 \mathrm { a }$ 来,新疆融雪(冰)型洪水占新疆洪水的 $3 9 \% ^ { [ 1 2 ] }$ 。现阶段，我国的国家气象站基本保持在2200\~2400个左右，东南地区分布较多，西北地区分布较少[13]。新疆地区的气象站总体较为稀疏。在呼图壁河流域石门水文站以上的区域，全国2400个国家级地面气象观测站中没有站点在该区域中。除气象站点数据外，多机构发布了多种不同的降水、气温数据产品，不同数据产品在数据来源、时间序列长度、数据处理方式与数据用途上各有不同[14]。对资料缺乏地区，研究已有降水、气温数据的适用性十分必要。国家气象中心提供的中国地面气温与降水日值 $0 . 5 ^ { \circ } \times 0 . 5 ^ { \circ }$ 格点数据集包括1961年至今的逐日气温与降水数据，时间序列长度足够，且该数据是基于国家级高密度台站插值而来，是中国经纬度边界范围内的气温、降水数据，比诸多全球范围的气温、降水产品更有针对性[14]。网格降水数据产品可有效地替代地面实测数据，但需要经过评估验证[15]

Gao 等[16]以基于站点的中国格网日降水分析产品CGDPA为基准，评估了2套降水数据产品在2处无资料地区的精度，并驱动水文模型分析了其对洪水频率分析的适用性。Dembele等在评估总结多套不同降水和气温数据产品的组合驱动mHM水文模型的效果时，发现不存在始终保持最优的气温或降水数据集，一些区域性数据产品优于全球数据产品。Mazzoleni等[i8]在研究不同降水数据集驱动分布式水文模型模拟径流时发现，不同的流域有不同的最优降水数据，模拟结果对流域特征十分敏感。在以往研究中，研究区域的空间范围也往往较大。因此，对于具体的中小无资料流域，针对各自不同的情况，仍需要因地制宜，做进一步的分析与评估。

HBV（Hydrologiska ByränsVattenbalansavdelning)模型是瑞典气象和水文研究所(SMHI)于20世纪70年代开发的概念性水文模型[19-21]。对融雪径流作用机制明显的流域,HBV模型的适应性较强[22]。目前，HBV模型已被应用于全球50多个国家，被广泛应用于各种尺度，成为许多应用类型中更普遍的工具，在许多无资料或资料缺乏的地区也得到应用[23]

本文以气象站点稀疏的新疆呼图壁河流域石门站以上的区域为研究区域，选取中国气象局的气象站观测数据集和中国地面降水与气温日值 $0 . 5 ^ { \circ } \times$ $0 . 5 ^ { \circ }$ 格点数据集，应用包含融雪径流模拟的HBV模型，在呼图壁河流域石门水文站以上区域，基于模拟出的融雪洪水径流与实测径流对比，分别对选取的2套气温、降水数据集进行对比分析及其融雪型径流模拟的适用性分析，分析了呼图壁河流域模拟与实测融雪洪水的一些特征，也结合驱动数据的不同分析了模拟融雪径流出现误差的可能原因，为如何提高无资料地区融雪型洪水预报的准确性提供支撑。

# 数据和方法

# 1.1 研究区概况

本文研究区域为新疆呼图壁河流域石门站以上的区域(图1)，呼图壁河流域位于天山北坡中段、准噶尔盆地南缘,地理位置介于 $8 6 ^ { \circ } 0 5 ^ { \prime } { \sim } 8 7 ^ { \circ } 0 8 ^ { \prime } \mathrm { E }$ ，$4 3 ^ { \circ } 0 7 ^ { \prime } { \sim } 4 5 ^ { \circ } 2 0 ^ { \prime } \mathrm { N }$ 之间。流域自上而下有石门水文站、青年渠首及芨芨坝分水闸站。石门站以上流域集水面积为 $1 8 4 0 \mathrm { k m } ^ { 2 }$ ,河道坡降达 $23 . 3 \text{‰}$ ,年径流量占呼图壁河全流域年径流量的 $9 3 . 3 \% ^ { [ 2 4 ] }$ 。呼图壁河径流年内分配极不均匀，在夏季相对集中，占全年径流量的 $8 0 \%$ 。流域地表径流补给主要来源于高山雪冰融水、季节性积雪融水、降水和地下水[24]

注：图中经纬度网格线亦为格点单元分割线。

![](images/b66296f21087f76521f6f57dc33959c5a8e8c00d06f34b757f75450f6fdcf00a.jpg)  
图1研究区示意图  
Fig.1 Schematic diagram of the study area

# 1.2HBV模型

HBV模型结构简单，易于理解。本文使用的HBV模型版本为AghaKouchak等[20]使用的HBV集总式日模型版本。值得注意的是，因为研究区域气象站点稀疏，没有足够的蒸散发数据作为驱动数据，因此，在求潜在蒸散发时，将HBV模型中原本用月平均气温、月平均潜蒸散发、日平均气温求修正的潜蒸散发的方法改为使用修正的Blaney-Criddle方程，根据风速、湿度、太阳辐射等因素，以日平均气温为主要驱动数据计算修正的潜在蒸散发量。修改后，模型输入的驱动数据为日降水量和日平均气温数据，模型的输出为日平均流量。

模型总体水平衡可描述为：

$$
P - E - R = \frac { \mathrm { d } } { \mathrm { d } t } \big ( S P + S M + U Z + L Z + L _ { \mathrm { a k e s } } \big )
$$

式中： $P$ 是降水量； $E$ 是蒸散发量； $R$ 是径流量； $S P$ 为积雪覆盖量； $S M$ 为土壤含水量; $U Z$ 为表层地下含水量； $L Z$ 为深层地下含水量； $L _ { \mathrm { a k e s } }$ 为流域中水体的水量。

HBV模型包含4个主要模块：融雪与积雪模块;土壤水分和有效降水模块;蒸散发模块；径流响应模块。

# （1）融雪与积雪模块

HBV模型假定融雪和积雪由观测的气温 $( T )$ 和阈值温度(TT)之间的相对关系控制。如果 $T \leqslant T T$ 则假定所有进入的降水都以降雪的形式积累，不产生径流。如果 $T { > } T T$ ，则积雪会融化，融雪用度日法计算。液态水量为降水量与融雪所得水量之和，并随后划分为入渗和径流成分。度日法计算公式为：

$$
S _ { \scriptscriptstyle m } = D D \big ( T - T T \big )
$$

式中： $S _ { m }$ 为融雪量 $\mathrm { ( m m \cdot d ^ { - 1 } ) }$ ： $D D$ 为度日因子 $\mathrm { ( m m \cdot ^ { \circ } C ^ { - 1 } }$ ：$\operatorname { d } ^ { - 1 } ) ; T$ 为日平均气温 $( ^ { \circ } \mathrm { C } ) { \mathrm { : } } T T$ 为阈值温度 $( ^ { \circ } \mathrm { C } )$ 。

（2）土壤水分和有效降水模块

根据降水时土壤含水量估算，模型将降水分为2个部分，一部分有助于渗透到土壤中，另一部分有助于产生地表径流，即有效降水 $P _ { \mathrm { e f f } \odot }$

$$
P _ { \mathrm { e f f } } = \left( { \frac { S M } { F C } } \right) ^ { \beta } \left( P + S _ { \it m } \right)
$$

式中： $P _ { \mathrm { e f f } }$ 表示有效降水 $( \mathrm { m m } ) ; S M$ 是实际土壤含水量$( \mathrm { m m } ) ; F C$ 是最大土壤持水量 $( \mathrm { m m } ) ; P$ 是日降水量$( \mathrm { m m } ) { : \beta }$ 是形状因子。

(3）蒸散发模块

实际蒸散发量由实际土壤含水量与 $P W P$ 的关系经以下的计算得到：

$$
E _ { _ a } = \left\{ \begin{array} { l l } { E _ { _ { T P } } { \left( \frac { S M } { P W P } \right) } , } & { S M \leqslant P W P } \\ { E _ { _ { T P } } } & { , } & { S M > P W P } \end{array} \right.
$$

式中： $E _ { \scriptscriptstyle T P }$ 表示潜在蒸散发 $\left( \mathrm { m m } \right)$ $E _ { a }$ 表示实际的蒸散发量 $( \mathrm { m m } ) ; P W P$ 表示实际蒸散发达到潜在蒸散发时的土壤含水量 $\mathrm { ( m m ) }$ 。

（4）径流响应模块

HBV模型利用线性水库的概念来模拟估算流域出口处的径流。系统由2个虚拟的水库组成，第1个水库用来描述近地表径流过程，第2个水库用来模拟基流。这2个水库通过恒定的渗透速率相互连接。总的模拟径流量通过将第1个和第2个水库流出量相加得出。

# 1.3数据来源

采用的数据集为中国气象局的气象站公布的2套数据集。第1套数据为站点观测数据，选取全国2400国家级地面气象观测站中的3个站点和石门水文站的观测数据。在全国2400国家级地面气象观测站中没有气象站在研究区域内，选取距离研究区域最近的天山大西沟站与较近的呼图壁站、小渠子站，分别距研究区边界 $1 7 ~ \mathrm { k m } \ 、 3 9 \mathrm { k m } \ 、 4 5 \mathrm { k m }$ 左右(图1)。对选取的4个站点求其气温、降水数据的算术平均值，作为第1套驱动数据。

第2套数据为气温与降水格点数据，降水格点数据来自中国地面降水日值 $0 . 5 ^ { \circ } \times 0 . 5 ^ { \circ }$ 格点数据集（V2.0）,数据集代码：SURF_CLI_CHN_PRE_DAY_GRID_0.5。气温格点数据来自中国地面气温日值$0 . 5 ^ { \circ } \times 0 . 5 ^ { \circ }$ 格点数据集（V2.0），数据集代码：SURF_CLI_CHN_TEM_DAY_GRID_0.5。选取本文研究区所在的3个格点单元(图1)，并按流域在格点单元中所占的面积比例大小对所选格点单元的降水、气温数据加权平均，将得到的降水、气温日数据作为另1套驱动数据。

本文的研究区内有石门水文站，位于研究区出口。石门水文站的气温、降水与径流数据均来自水文年鉴。

# 1.4统计指标

应用HBV模型对研究区进行融雪洪水模拟，率定期为2000年1月1日至2007年12月31日，验证期为2008年1月1日至2011年12月31日。

径流模拟的结果用Nash效率系数与流量平均相对误差判定：

$$
{ \mathrm { N S E } } = 1 - { \frac { \sum ( Q _ { \mathrm { { o b s } } } - Q _ { \mathrm { { s i m } } } ) ^ { 2 } } { \sum ( Q _ { \mathrm { { o b s } } } - { \overline { { Q _ { \mathrm { { o b s } } } } } } ) ^ { 2 } } }
$$

$$
\mathrm { M R E } = \left| \frac { \overline { { Q _ { \mathrm { o b s } } } } - \overline { { Q _ { \mathrm { s i m } } } } } { \overline { { Q _ { o b s } } } } \right| \times 1 0 0 \%
$$

式中： $Q _ { \mathrm { { o b s } } }$ 为实测流量 $( \mathbf { m } ^ { 3 } \cdot \mathbf { s } ^ { - 1 } )$ $Q _ { \mathrm { s i m } }$ 为模拟流量值 $( \mathbf { m } ^ { 3 }$ ·$\mathbf { s } ^ { - 1 } )$ ; $\overline { { Q _ { \mathrm { o b s } } } }$ 为观测流量平均值 $( \mathrm { m } ^ { 3 } \cdot \mathrm { s } ^ { - 1 } )$ ： $\overline { { Q _ { \mathrm { s i m } } } }$ 为模拟流量平均值 $( \mathbf { m } ^ { 3 } \cdot \mathbf { s } ^ { - 1 } )$ 。NSE为Nash效率系数（Nash-SuttcliffeEfficiency），MRE为平均相对误差（MeanRelativeError）。Nash系数NSE介于 $- \infty \sim 1$ 之间，其值越接近1，则模拟结果越精确。流量平均相对误差MRE用来评估总体流量是否平衡。

# 2 结果与分析

# 2.1站点数据与格点数据的对比分析

首先，将2套驱动数据一一站点气温、降水数据与格点气温、降水数据做对比(图2)。

从图2a可以看出，站点日平均气温整体高于格点日平均气温。从2000年1月1日至2011年12月31日的日平均气温特征值来看,2000—2011年，站点日平均气温的最大值为 $2 4 . 3 ~ \mathrm { \textdegree C }$ ，在2004年7月14日，格点日平均气温的最大值为 $1 7 . 5 ~ \mathrm { ^ { \circ } C }$ ,在2006年7月31日。站点日平均气温的最小值为2011年1月7日的 $- 2 4 . 8 ~ \mathrm { { ^ { \circ } C } }$ ，格点日平均气温的最小值为2006年1月4日的 $- 2 6 . 6 \mathrm { ~ \textdegree C }$ O

从季节尺度看，在2000年1月1日至2011年12月31日，夏季站点日平均气温数据的多年平均值为$1 6 . 1 ~ \mathrm { { ^ { \circ } C } }$ ，比格点日平均气温数据的夏季多年平均值$9 . 7 ^ { \circ } \mathrm { C }$ 高 $6 . 4 ~ \mathrm { { ^ { \circ } C } }$ ，在4个季节中相差最大。2套日平均气温数据的春季多年平均值之差次之,春季站点日平均气温数据的多年平均值为 $4 . 4 ~ \mathrm { { ^ circ C } }$ ，比格点数据的 $- 0 . 8 \mathrm { ~ \textdegree C }$ 高 $5 . 2 ^ { \circ } \mathrm { C }$ 。秋季的情况与春季较为接近，秋季站点日平均气温的多年平均值为 $3 . 8 ~ \mathrm { { ^ { \circ } C } }$ ，比格点数据的 $- 0 . 6 \mathrm { { ‰ } }$ 高 $4 . 4 ^ { \circ } \mathrm { C }$ 。在4个季节中，冬季2套日平均气温数据的多年平均值相差最小,站点日平均气温数据的冬季多年平均值为 $- 1 1 . 7 \mathrm { { ^ { \circ } C } }$ ,比格点日平均气温数据的 $- 1 3 . 4 \mathrm { { ^ { \circ } C } }$ 高 $1 . 7 ^ { \circ } \mathrm { C }$ O

从多年尺度看，在2000年1月1日至2011年12月31日，站点日平均气温数据的多年平均值为$3 . 2 ~ \mathrm { ^ { 9 ~ C } }$ ，格点日平均气温数据的多年平均值为$- 1 . 2 \mathrm { { ^ { \circ } C } }$ ,站点日平均气温数据的多年平均水平比格点数据高 $4 . 4 ^ { \circ } \mathrm { C }$ U

![](images/ee10cbd4cb152e18ba254857173e240ed8da007909a271902a0d04b888164931.jpg)  
图2站点数据与格点数据对比  
Fig.2 Comparison of station data and grid data

分析图2b可知，在每年日降水量最大的几天，2种降水数据产品有较大偏差，所用站点的日降水数据往往小于格点日降水数据。以2000年为例，在2000年，站点数据和格点数据的日降水量最大值均在6月11日,这一天站点数据日降水量为 $1 8 . 7 \mathrm { m m }$ ，格点数据日降水量为 $3 9 . 9 \mathrm { m m }$ 。在2000年，站点数据最大3日降水量为 $3 6 . 5 \mathrm { ~ m m }$ ,格点数据最大3日降水量为 $6 5 . 0 \mathrm { m m }$ 。站点数据中，根据 $2 4 \mathrm { h }$ 降水量，属于中雨( $1 0 { \sim } 2 5 ~ \mathrm { m m }$ )的有9d,属于小雨 $( 0 . 1 { \sim } 1 0 \ \mathrm { m m } )$ 0的有171d,其余( $< 0 . 1 \ \mathrm { m m } ,$ 的有 $1 8 6 \mathrm { ~ d ~ }$ 。格点数据中，根据 $2 4 \mathrm { ~ h ~ }$ 降水量，属于大雨( $2 5 { \sim } 5 0 ~ \mathrm { m m }$ 的有2d,属于中雨( $1 0 { \sim } 2 5 ~ \mathrm { m m }$ )的有13d，属于小雨 $( 0 . 1 \sim$ $1 0 ~ \mathrm { m m } .$ 的有234d，其余( $< 0 . 1 \ \mathrm { m m } ,$ 的有 $1 1 7 \mathrm { d }$ O

从季节尺度来看，在春季，站点数据日降水量平均值为 $1 . 2 \ \mathrm { m m }$ ,格点数据日降水量平均值为1.0$\mathbf { m } \mathbf { m }$ 。在夏季,站点数据日降水量平均值为 $2 . 4 ~ \mathrm { m m }$ ，格点数据日降水量平均值为 $3 . 5 ~ \mathrm { m m }$ 。在秋季，站点数据与格点数据日降水量平均值均为 $0 . 7 ~ \mathrm { m m }$ 。在冬季，站点数据日降水量平均值为 $0 . 3 ~ \mathrm { m m }$ ,格点数据日降水量平均值为 $0 . 2 \mathrm { m m }$ ○

从多年尺度来看，在2000年1月1日至2011年12月31日，站点数据的多年平均降水量为426.3$\mathbf { m } \mathbf { m }$ ,格点数据的多年平均降水量为 $4 9 4 . 2 \ \mathrm { m m }$ 。格点降水数据总体大于站点降水数据

从2000年1月1日至2011年12月31日各种降水类型的天数看，格点数据日降水量最大值为39.9$\mathbf { m } \mathbf { m }$ ,根据 $2 4 \mathrm { ~ h ~ }$ 降水量，属于大雨( $2 5 { \sim } 5 0 ~ \mathrm { m m } ,$ 的有$1 4 \mathrm { ~ d ~ }$ ，属于中雨( $1 0 { \sim } 2 5 ~ \mathrm { m m }$ 的有 $9 5 \mathrm { ~ d ~ }$ ，属于小雨0 $\mathrm { 0 . 1 { \sim } 1 0 ~ m m }$ 的有2771d，其余（ $< 0 . 1 \ \mathrm { m m } ,$ 有1503d。站点数据日降水量最大值为 $3 3 . 0 \mathrm { m m }$ ,根据 $2 4 \mathrm { h }$ 降水量，属于大雨 $( 2 5 { \sim } 5 0 ~ \mathrm { m m } )$ )的有1d,属于中雨1 $1 0 { \sim } 2 5 ~ \mathrm { m m }$ )的有81d，属于小雨 $( 0 . 1 { \sim } 1 0 ~ \mathrm { m m } )$ 的有2067d，其余( $< 0 . 1 \ \mathrm { m m } ,$ 有 $2 2 3 4 \mathrm { d }$ O

从降水的空间分布来看，对于站点数据，2000年1月1日至2011年12月31日，呼图壁站多年平均降水量为 $2 1 0 . 0 \ \mathrm { m m }$ ，小渠子站多年平均降水量为$5 8 6 . 5 ~ \mathrm { m m }$ ,天山大西沟站多年平均日降水量为$5 0 2 . 9 ~ \mathrm { m m }$ ,石门站多年平均降水量为 $4 0 5 . 8 ~ \mathrm { m m }$ 。如图1,结合海拔高度可以看出，在本文研究区内，海拔越高，站点数据的多年平均降水量越大。对于格点数据，2000年1月1日至2011年12月31日，按流域在格点单元中所占的面积比例大小加权之前，左上格点单元( $4 3 . 5 ^ { \circ } { \sim } 4 4 ^ { \circ } \mathrm { N }$ $8 6 ^ { \circ } { \sim } 8 6 . 5 ^ { \circ } \mathrm { E }$ )的多年平均降水量为 $5 4 2 . 2 ~ \mathrm { m m }$ ，左下格点单元 $( 4 3 ^ { \circ } { \sim } 4 3 . 5 ^ { \circ } \mathrm { N }$ .$8 6 ^ { \circ } { \sim } 8 6 . 5 ^ { \circ } \mathrm { E }$ )的多年平均降水量为 $4 6 9 . 0 \mathrm { m m }$ ,右上格点单元 $( 4 3 . 5 ^ { \circ } { \sim } 4 4 ^ { \circ } \mathrm { N } , 8 6 . 5 ^ { \circ } { \sim } 8 7 ^ { \circ } \mathrm { E } )$ 的多年平均降水量为 $5 2 6 . 2 \ : \mathrm { m m }$ 。在本文研究区内，格点数据的多年平均降水量随格点单元的平均海拔高度的变化规律不明显。

# 2.2融雪洪水径流模拟

首先，采用算术平均法将2000年1月1日至2007年12月31日的站点气温、降水数据和格点气温、降水数据进行融合，得到一套融合的气温、降水数据，用以率定模型参数。

本文所用的HBV模型共有参数10个，其中度日因子 $D D$ 、田间持水量FC、壤中流退水系数 $k _ { 1 }$ 是敏感参数，其余为不敏感参数[25]。首先对参数进行人工率定，通过人工率定的过程理解每个参数对模拟结果的影响，再采用遗传算法对敏感参数进行率定(表1)。

使用率定好的参数，分别用站点数据和格点数据驱动HBV模型模拟融雪洪水的结果如表2所示。

分别绘制融合数据与站点数据、格点数据驱动HBV模型模拟的融雪洪水流量与实测流量过程线，如图3所示。

使用融合的气温、降水数据驱动HBV模型率定参数，率定期融雪洪水模拟的Nash系数为0.680，平均流量相对误差为 $1 . 6 3 \%$ ，率定期模拟的洪水过程如图3a所示。可以看出，融合数据模拟出的夏季洪水的洪峰部分普遍偏小，2001年、2003年、2004年、2005年、2006年、2007年的春季模拟出的融雪径流偏大，会模拟出实测不存在的洪水过程。在部分年份最后1个洪水之后的部分时段，如2000年9月至10月上旬、2001年10月中旬、2002年10月、2003年10月、2004年10月、2005年10月、2007年10月，融合数据驱动HBV模型模拟出的流量减少的过程与实测过程拟合较好。在流量较低的冬季，2004年1—2月与2005年2月融合数据驱动HBV模型模拟出的流量与实测流量拟合较好，其余年份冬季融合数据驱动HBV模型模拟出的流量普遍低于实测

Tab.1 Parameters'range and calibration results of HBV model   

<html><body><table><tr><td>模块</td><td>参数</td><td>参数含义</td><td>参数范围</td><td>率定结果</td><td>参考文献</td></tr><tr><td rowspan="2">融雪与积雪模块</td><td>TT</td><td>阈值温度/℃</td><td>-1.0~2.7</td><td>2.40</td><td>[25]</td></tr><tr><td>DD</td><td>度日因子/(mm·C-·d1)</td><td>0.5~4.0</td><td>0.5</td><td>[22]</td></tr><tr><td>有效降水与土壤含</td><td>FC</td><td>最大土壤持水量/mm</td><td>100~450</td><td>132.88</td><td>[25]</td></tr><tr><td>水量模块</td><td>β</td><td>形状系数</td><td>1~5</td><td>2.3</td><td>[25]</td></tr><tr><td>蒸散发模块</td><td>PWP</td><td>蒸散发达到潜在蒸散发时的土壤水 量/mm</td><td>90~180</td><td>106</td><td>[21]</td></tr><tr><td rowspan="5">径流响应模块</td><td>h</td><td>地表径流退水系数/d-</td><td>0.05~0.2</td><td>0.0500</td><td>[21]</td></tr><tr><td>l</td><td>阈值水位/mm</td><td>2~5</td><td>2</td><td>[21]</td></tr><tr><td>h</td><td>壤中流退水系数/d-1</td><td>0.01~0.2</td><td>0.0143</td><td>[25]</td></tr><tr><td>h</td><td>基流退水系数/d</td><td>0.001~0.1</td><td>0.0050</td><td>[25]</td></tr><tr><td>kp</td><td>渗透系数/d'</td><td>0.01~0.05</td><td>0.0200</td><td>[21]</td></tr></table></body></html>

# 表2使用不同驱动数据的流量模拟结果

表1HBV模型的参数范围与率定结果  
Tab.2 Flow simulation results using different driving data   

<html><body><table><tr><td>时期</td><td>驱动数据</td><td>年份</td><td>NSE</td><td>MRE/%</td></tr><tr><td>率定期</td><td>融合数据</td><td>2000- -2007</td><td>0.680</td><td>1.63</td></tr><tr><td>验证期</td><td>站点数据</td><td>2008- -2011</td><td>0.433</td><td>14.64</td></tr><tr><td></td><td>格点数据</td><td>2008- -2011</td><td>0.792</td><td>2.44</td></tr></table></body></html>

流量。

用站点数据驱动HBV模型模拟融雪洪水过程（图3b)，验证期融雪洪水模拟的Nash系数为0.433，平均流量相对误差为 $1 4 . 6 4 \%$ 。用格点数据驱动HBV模型模拟融雪洪水过程(图3c），验证期融雪洪水模拟的Nash系数为0.792，平均流量相对误差为$2 . 4 4 \%$ 。从Nash系数与平均相对误差来看，格点数据驱动HBV模型的融雪径流模拟效果比站点数据驱动HBV模型的融雪径流模拟效果更好，格点数据在研究区进行融雪洪水模拟的适用性更强。

结合2套数据的对比结果，对比2套数据驱动HBV模型模拟出的融雪洪水过程与实测洪水过程，分析2套数据在研究区的精度与误差情况。在每年夏季的洪峰部分，2套数据驱动HBV模型模拟出融雪洪水的洪峰均小于实测洪水的洪峰，站点数据的这一问题更为突出，站点数据模拟出的这里的洪峰流量低于格点数据模拟出的流量。实测洪水过程中，洪峰前的涨洪过程往往比较迅速，如2008年7月28—29日,实测流量由 $6 0 . 7 \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 }$ 涨为 $1 0 3 \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 }$ ，2009年7月13—14日，实测流量由 $6 0 . 1 ~ \mathrm { m } ^ { 3 } \cdot \mathrm { s } ^ { - 1 }$ 涨为$1 1 1 \ \mathrm { m ^ { 3 } \cdot s ^ { - 1 } }$ ,2011年6月18—19日，实测流量由57.4$\mathbf { m } ^ { 3 } \cdot \mathbf { s } ^ { - 1 }$ 涨为 $1 1 6 ~ \mathrm { m ^ { 3 } \cdot s ^ { - 1 } }$ 。而2套数据模拟出的融雪洪水流量的涨洪过程则相对平缓。对比相应时段的气温、降水数据，2008年7月28日格点数据降水量为 $1 1 . 4 \mathrm { m m }$ ,站点数据降水量则仅有 $4 . 2 \ \mathrm { m m } ; 2 0 0 9$ 年7月13日格点数据与站点数据的降水量分别为6.6$\mathbf { m } \mathbf { m }$ 与 $4 . 1 \ \mathrm { m m } ; 2 0 1 1$ 年6月18日，格点数据降水量为$2 1 . 0 \mathrm { m m }$ ，站点数据降水量为 $1 0 . 0 \mathrm { m m }$ 。根据模型结构，夏季站点数据驱动HBV模型模拟出的洪峰流量过低可能的原因是，在夏季，所用站点的降水数据偏低或者所用站点的气温数据偏低，结合2.1的分析，事实上，在夏季，所用站点数据的气温普遍高于格点数据。由此可见，在夏季，站点数据驱动HBV模型模拟出的洪峰流量过低的原因是所用站点的降水数据偏低的可能性更大。此外，格点数据驱动HBV模型模拟出的洪峰流量也低于实测流量，只有对应着较大降水的情况下，模拟的洪水过程才体现出陡涨的过程，因此2套降水数据在夏季的降水量大的部分的精度均有待提高，站点数据在降水量大的部分的精度比格点数据低。

2008年上半年，2套数据驱动HBV模型模拟出融雪洪水的流量均小于实测值，主要原因是模型状态变量的初始值为0，需要运行一段时间。总体来看，除了2009年，2010年，2011年的春季，2009年的8—10月，2011年的秋季外，在2008—2011年的其他时段，用站点数据驱动HBV模型模拟出的融雪洪水流量普遍小于实测值。根据2.1中站点数据与格点数据对比分析的结果，推测可能的原因是所用站点降水数据偏低，导致模拟出的融雪洪水流量偏低。

在2009年、2010年、2011年的4—5月，站点数据驱动HBV模型模拟出的融雪洪水流量普遍远大于实测流量过程，且会模拟出若干洪峰，而实测流量过程则没有这些洪峰。根据2套数据对比分析的结果和HBV模型的结构，推测其主要原因是4月往往处于一年中气温刚开始持续大于融雪阈值温度的时候，气温升高，而站点气温数据偏高，因此导致从4月开始模型计算出的融雪量偏高，从而计算出的春季融雪洪水流量偏高。相比之下，格点数据驱动HBV模型模拟出的洪水流量过程的峰现时间与实测流量过程总体较为吻合。

![](images/6d53333aa7e3feed4fff13957f42b1a679399ccaf00a0a539c8f0990709edd75.jpg)  
图3融合数据与2套数据驱动下的模拟结果  
Fig.3Simulation results driven by syncretic data and two sets of data

在每年的冬季，实测流量往往在 $1 . 8 { \sim } 3 . 8 ~ \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 }$ 左右，格点数据与站点数据驱动HBV模型模拟出的冬季流量过程均小于实测流量过程，站点数据驱动HBV模型模拟出的冬季流量更小,基本小于 $2 \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 }$ ，格点数据驱动HBV模型模拟出的冬季流量往往维持在 $1 . 5 { \sim } 2 . 5 ~ \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 }$ 左右，当冬季实测流量在 $2 \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 }$ 左右时，格点数据驱动HBV模型模拟出的冬季流量与实测流量过程较为吻合。

从数据集的制作过程分析误差原因，格点数据是基于国家气象信息中心基础资料专项最新整编的中国地面高密度台站的降水、气温资料，利用ANUSPLIN软件的薄盘样条法(TPS，ThinPlateSpline)进行空间插值，生成中国地面水平分辨率$0 . 5 ^ { \circ } { \times } 0 . 5 ^ { \circ }$ 的日值降水与气温格点数据。而本文的站点数据所选取的站点为研究区外的3个邻近气象站与研究区内1个水文站。在山区，降水受地形影响较大，有很强的空间变异性，气温也具有海拔高度引起的垂直差异。这些站点的气温与降水数据在研究区代表性比较差，精度较低，但是在研究区再没有别的站点。因此，在后续的研究中，为减小融雪洪水模拟的误差，可以根据海拔高程、坡向坡度等因素，对临近站点数据进行修正，

# 2.3融雪洪水特征分析

由图3可以看出，在研究区，每一年中最大的洪水均出现在夏季，且往往涨洪迅速，洪峰陡峭。实测日平均流量常常出现某一天突然陡涨的现象。选取2000年、2001年、2008年为例，2000年7月15—16日、7月17—18日、2001年7月29—30日和2008年7月28—29日实测流量增长均接近2倍。每年第1场洪峰所在的日平均流量超过 $5 0 \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 }$ 的洪水往往出现在夏季。夏季是全年洪水流量最大的季节，2000—2011年夏季石门站实测日平均流量的多年平均值为 $4 3 . 9 ~ \mathrm { m } ^ { 3 } \cdot \mathrm { s } ^ { - 1 }$ 。2000—2011年间，最大的日平均流量为2007年7月10日的 $1 7 1 ~ \mathrm { m ^ { 3 } \cdot s ^ { - 1 } }$ 。对于洪峰部分的日平均流量，2套数据驱动HBV模型模拟出的流量往往偏小。

在春季，日平均流量由冬季的 $1 . 8 { \sim } 3 . 8 ~ \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 }$ 左右开始缓慢上升。受温度升高、积雪融化与降水的影响，部分年份，如2000年、2002年、2003年、2006年、2007年、2008年、2009年在4月底或5月会形成较小的洪峰,洪峰位置的日平均流量在 $2 0 { \sim } 3 5 ~ \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 }$ 左右。2000—2011年春季实测日平均流量的多年平均值为 $5 . 6 6 \mathrm { m } ^ { 3 } \cdot \mathrm { s } ^ { - 1 }$ 。站点数据驱动HBV模型模拟出的春季流量过程常常偏大。

每年的9月开始，秋季位于一年中最后1场较大的洪水的退水过程，退水过程往往比较缓慢，部分年份的日平均流量在这一段退水过程中有上下波动过程，如2007年9月上旬，2009年9月上旬、2010年9月上旬。2000—2011年秋季石门站实测日平均流量的多年平均值为 $1 0 . 5 ~ \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 }$ 。

冬季流量普遍较小，一般保持在 $1 . 8 { \sim } 3 . 8 ~ \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 }$ 左右，波动很小。2000—2011年冬季实测日平均流量的多年平均值为 $2 . 8 0 \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 }$ 。

# 3结论

（1）格点数据驱动下水文模型的融雪径流模拟效果总体优于利用站点观测数据驱动的水文模型的模拟效果。格点数据驱动下水文模型模拟融雪径流的Nash系数在验证期为0.792，高于站点数据驱动下的0.433。格点数据驱动下水文模型模拟融雪径流的平均相对误差为 $2 . 4 4 \%$ ，低于站点数据驱动下的 $1 4 . 6 4 \%$ 。基于国家级高密度台站插值而来的格点数据在研究区融雪洪水模拟的适用性比本文所选取的研究区外的3个邻近气象站与研究区内1个水文站的气温与降水数据更高。

(2）分析模拟与实测的融雪洪水特征，在大洪水的部分，实测洪水过程涨洪迅速，2套数据模拟出的洪峰流量都普遍偏小，站点数据驱动HBV模型模拟出的融雪洪水洪峰部分的误差大于格点数据驱动HBV模型的模拟结果。在春季，站点数据驱动HBV模型模拟出的流量过程比实测过程偏大，这主要是因为所用站点的气温数据偏高。在每年的11月下旬至次年2月上旬，2套数据驱动HBV模型得到的流量模拟值都普遍低于实测值。对于格点数据，当实测流量在 $2 \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 }$ 左右时，模拟值与实测值会比较吻合。冬季站点数据在研究区的精度则有待提高。

(3)结合2套数据的对比结果与融雪径流的模拟情况可知，本文所选取的研究区外的3个邻近气象站与研究区内1个水文站的气温与降水数据在研究区的精度较低，特别是日降水数据的算术平均值在夏季偏低，日平均气温算术平均值在春季偏高。因为在山区，降水受地形影响较大，有很强的空间变异性，气温也具有海拔高度引起的垂直差异。这些站点的气温与降水数据在研究区代表性比较差，精度较低，但在研究区无其他站点。本文仅基于水文模型模拟出的融雪洪水径流与实测径流对比，分别对2套数据集进行了对比分析及其融雪型径流模拟的适用性分析。在后续的研究中，可以根据海拔高程、坡向坡度等因素，对临近站点数据进行修正，以减小融雪洪水模拟的误差。

# 参考文献(References)：

[1] Abudu S, Cui C-L,Saydi M,et al.Application of snowmelt runoff model (SRM) in mountainous watersheds:A review[J].Water Science and Engineering,2012,5(2): 123-136.   
[2] 徐凯莉，吕海深,刘名文，等.数值模拟方法在河流冰塞水位模 拟中的应用——以黄河三湖河口弯道段为例[J].干旱区研究, 2021,38(6): 1556-1562.[Xu Kaili,Lyu Haishen,Liu Mingwen,et al.Numerical simulation of the ice jam stage in the Sanhuhekou bend reach of the Yellow River[J].Arid Zone Research,2O21,38 (6): 1556-1562.]   
[3]Qiu L, You J, Qiao F,et al. Simulation of snowmelt runoff in ungauged basins based on MODIS: A case study in the Lhasa River basin[J]. Stochastic Environmental Research and Risk Assessment, 2014,28(6): 1577-1585.   
[4]韩春坛,王磊,陈仁升,等.祁连山高寒山区降水观测网络及其 数据应用[J].资源科学,2020,42(10):1987-1997.[Han Chuntan,Wang Lei, Chen Rensheng,et al.Precipitation observation network and its data application in the alpine region of Qilian Mountains[J]. Resources Science,2020,42(10): 1987-1997.]   
[5]卢爱刚,康世昌,庞德谦,等.地形对中国气温季节分布格局的 差异影响[J].生态环境,2008,17(4):1450-1452.[Lu Aigang, Kang Shichang,Pang Deqian,et al. Different landform effects on seasonal temperature patterns in China[J]. Ecology and Environment, 2008,17(4): 1450-145.]   
[6]陈仁升,康尔泗,丁永建.中国高寒区水文学中的一些认识和参 数[J].水科学进展,2014,25(3):307-317.[Chen Rensheng, Kang Ersi,Ding Yongjian. Some knowledge on and parameters of China' s alpine hydrology[J]. Advances in Water Science,2014,25(3): 307- 317.]   
[7]Zhang J,Li Y,Huang G,etal. Evaluation of uncertainties in input data and parameters of a hydrological model using a Bayesian Framework:A case study of a snowmelt-precipitation-driven watershed[J]. Journal of Hydrometeorology,2016,17(8): 2333-2350.   
[8]刘俊峰,陈仁升,卿文武,等.基于TRMM降水数据的山区降水 垂直分布特征[J].水科学进展,2011,22(4): 447-454.[Liu Junfeng, Chen Rensheng,Qin Wenwu,et al. Study on the vertical distribution of precipitation in mountainous regions using TRMM data [J]. Advances In Water Science,2011,22(4): 447-454.]   
[9]Tuo Y,Duan Z,Disse M,et al. Evaluation of precipitation input for SWAT modeling in Alpine catchment: A case study in the Adige River Basin (Italy)[J].Science of the Total Environment, 2016,573: 66-82.   
[10] 陈庭兴,吕海深,朱永华.基于GEV分布的西营河流域洪水特 性分析[J].干旱区研究,2021,38(6):1563-1569.[Chen Tingxing,Lyu Haishen, Zhu Yonghua. Analysis of flood characteristics in Xiying River Basin based on GEV distribution[J].Arid Zone Research,2021,38(6): 1563-1569.]   
[11]李燕.近40a来新疆河流洪水变化[J].冰川冻土,2003,25(3): 342-346.[Li Yan. Change of river flood and disaster in Xinjiang during past4Oyears[J].Journalof GlaciologyandGeocryology 2003, 25(3): 342-346.]   
[12] 张俊兰,罗继,王荣梅.近20a新疆升温融雪(冰)型洪水频次时 空变化及大气环流型分析[J].干旱区研究,2021,38(2):339- 350.[Zhang Junlan,Luo Ji, Wang Rongmei. Combined analysis of the spatiotemporal variations in snowmelt (ice) flood frequency in Xinjiang over 2O years and atmospheric circulation patterns[J]. Arid Zone Research,2021,38(2): 339-350.]   
[13] Shen Y, Xiong A. Validation and comparison of a new gaugebased precipitation analysis over mainland China[J]. International Journal of Climatology,2016,36(1): 252-265.   
[14] 唐榕,王运涛,李敏,等.尼尔基水库上游格点降水数据适用性 评估[J].水资源与水工程学报,2019,30(5):26-31,9.[Tang Rong,Wang Yuntao,Li Min,et al. Suitability evaluation of gridded precipitation dataset for the upstream of Nierji Reservoir[J]. Journal of Water Resources and Water Engineering,2019,30(5): 26-31,9.]   
[15]Kumar M,Hodnebrog $\boldsymbol { \mathrm { \Omega } } _ { \mathrm { { \Omega } } }$ , Daloz A S,et al. Measuring precipitation in Eastern Himalaya: Ground validation of eleven satelite,model and gauge interpolated gridded products[J]. Journal of Hydrology, 2021, 599: 126252.   
[16]Gao Z,Long D,Tang G,et al.Assessing the potential of satelltbased precipitation estimates for flood frequency analysis in ungauged or poorly gauged tributaries of China’s Yangtze River basin[J]. Journal of Hydrology,2017,550: 478-496.   
[17]Dembélé M, Schaefli B,Van De Giesen N,et al. Suitability of 17 gridded rainfall and temperature datasets for large-scale hydrological modeling in West Africa[J].Hydrologyand Earth System Sciences,2020,24(11): 5379-5406.   
[18]Mazzoleni M, Brandimarte L,Amaranto A. Evaluating precipitationdatasetsforlarge-scaledistributedhydrologicalmodeing[J] Journal of Hydrology,2019,578: 124076.   
[19] 崔逸凡,吕海深,朱永华,等.考虑大孔隙下渗的HBV模型及其 在山洪预报中的应用[J].水资源与水工程学报,2019,30(2): 43-49.[CuiYifan,LyuHaishen,Zhu Yonghua,etal.Aplicability of the HBV model in flash flood forecasting by considering the infiltration of macropore[J]. Journal of Water Resources and Water Engineering,2019,30(2): 43-49.]   
[20] Aghakouchak A,Habib E.Application of a conceptual hydrologic model in teaching hydrologic processes[J]. International Journal of Engineering Education, 2010,26: 963-973.   
[21]Lyu H, Crow W T,Zhu Y,et al. The impact of assumed error variances on surface soil moisture and snow depth hydrologic data assimilation[J]. IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing,2015, 8(11): 5116-5129.   
[22] 金浩宇,鞠琴,谢季遥.HBV模型在尼洋河流域的应用研究[J]. 中国农村水利水电,2019(6):23-28,34.[Jin Haoyu,Ju Qin,Xie Jiyao.The application of HBV model in the Nyang River Basin[J]. China Rural Water and Hydropower, 2019(6): 23-28,34.]   
[23]Bergstrom S.Experience from applications of the HBV hydrological model from the Perspective of prediction in ungauged basins [J]. IAHS,2006,307(1): 97-109.   
[24]耿峻岭,高玲,陈建江,等.新疆呼图壁河流域水文特征分析[J]. 干旱区研究,2005,22(3):371-376.[Geng Junling,Gao Ling, Chen Jianjiang,et al.Analysis on the hydrological characteristics in the Hutubi River Basin, Xinjiang[J].Arid Zone Research,2005, 22(3): 371-376.]   
[25] 高红凯,何晓波,叶柏生,等.1955—2008年冬克玛底河流域冰 川径流模拟研究[J].冰川冻土,2011,33(1):171-181.[Gao Hon

# Applicability assessment of two meteorological datasets in areas lacking data with the Hutubi River Basin as an example

SUN Mingyuel²，LYU Haishen1²， ZHU Yonghual²，LIN $\mathrm { Y u } ^ { 1 , 2 }$ ，ZHANG Meijiel,2 (1. State Key Laboratory of Hydrology-Water Resources and Hydraulic Engineering,Hohai University, Nanjing 21Oo98,Jiangsu,China; 2.College of Hydrology and Water Resources,Hohai University, Nanjing 210098, Jiangsu, China)

Abstract: In ungauged areas,a lack of observational data (e.g.,precipitation and temperature data) can affect the accuracy offlood forecasting,which in turnaects the implementationofflood control,droughtrelief,and water resources planning.Therefore,it is necessry to conduct applicability analysis of existing precipitation and temperature data in ungauged areas.By applying the HBV(Hydrologiska Byrans Vatenbalansavdelning) model, including a snowmelt runoff simulation,to the area upstream of the Shimen hydrological station in the Hutubi River Basin,and based on a comparison of simulated snowmelt flood runoff and measured runoff,a dataset including gridded daily precipitation and temperature in China and observational data from meteorological stations were analyzed and compared.The applicability of the snowmelt runoff simulation was also analyzed. Results showed that the snowmelt runoff simulation was more efective when used with the hydrological model drivenby grid data than with the hydrological model driven by station observation data.The Nash coefcients of the snowmelt runoff from the hydrological model driven by grid dataand the hydrological model driven by station observation data were 0.792 and 0.433,respectively，within the verification period.In addition,some characteristics of the snowmelt floods in the Hutubi River Basin were analyzed and the possble causes of errors in the simulated snowmelt runoff were also assessed based on differences in driving data.These results can help improve the accuracy of snowmelt flood forecasts in areas that lack data on snowmelt characteristics.

Keywords: precipitation data;ungauged area;snowmelt flood; runoff forecast；applicability assessment; Hutubi River Basin