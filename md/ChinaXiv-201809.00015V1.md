# 1961一2014年新疆北部地区气温时空变化特征

谭娇²，丁建丽1,²，张钧泳1²，武鹏飞3（1．新疆大学资源与环境科学学院智慧城市与环境建模自治区普通高校重点实验室,新疆乌鲁木齐830046;2．绿洲生态教育部重点实验室,新疆 乌鲁木齐 830046；3．新疆乌鲁木齐气象卫星地面站,新疆 乌鲁木齐 830011)

摘要：利用新疆北部地区(下称北疆)41个气象站1961—2014年月平均气温资料,运用线性倾向率、滑动平均、基于ArcGIS 的混合插值法、累积距平分析、Mann-Kendall突变检验,基于 Matlab 的 Morlet 小波分析等方法对北疆地区年及季节气温变化进行分析。结果表明： $\textcircled{1}$ 北疆地区年及季节平均气温出现多次冷暖波动,均呈显著增温趋势。其中,年及春、夏、秋季从20纪90年代以后增温显著，冬季20世纪80年代以后增温显著。 $\textcircled{2}$ 北疆地区年平均气温倾向率为 $0 . 3 5 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ ,增温幅度较大区域主要在准噶尔盆地、塔城地区及富蕴。 $\textcircled{3}$ 北疆地区年及四季平均气温均发生突变。其中,年、春、夏、秋季平均气温突变主要发生在20世纪90年代,冬季气温突变主要发生在70年代末。 $\textcircled{4}$ 北疆地区年平均气温在近 $5 4 \mathrm { ~ a ~ }$ 存在27a主周期和 $1 4 \mathrm { ~ a ~ }$ 次周期,气温冷暖交替,周期表现具有全域性。

关键词：气温变化；区域差异；突变分析；小波分析；新疆北部地区

气温变化及其影响研究一直都是当今全球气候变化的热点问题。IPCC评估报告指出，最近100 a全球平均地面温度上升了 $0 . 7 4 { \mathrm { ~ } } ^ { \circ } \mathrm { C } ^ { [ 1 ] }$ 。同样有大量的研究表明，中国的气候变化与全球气候变化的总趋势保持一致[2-5],中国近54 a 增温速率约0.25$\mathrm { { ~ \mathcal { C } ~ } } \cdot \mathrm { ~ ( ~ 1 0 a ) ~ } ^ { - 1 }$ ;我国西北气候区也发生了很大变化,气候变化由暖干向暖湿转变。新疆地区气候也发生明显变化[,北疆地区水资源相对丰富，农牧业经济发达,但是,由于气候变化[7-8},北疆地区自然灾害也相对比较严重。

针对北疆地区气候变化研究[9-I],认为大部分地区出现气温升高、降水增多[12]。对北疆区域气候的研究主要集中在长时间序列的趋势变化，单一的反映北疆地区气温及降水突变研究的[13较少。马建勇等[14]研究发现,近55a北疆地区年平均气温以 $0 . 3 3 2 \mathrm { ~ \% ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { a } \mathrm { ) } ^ { - 1 }$ 的速率上升，四季气温也呈增加趋势,冬季增温最大;何毅等[15]研究了南北疆近 $6 0 \mathrm { ~ a ~ }$ 气温变化发现,北疆增温幅度较南疆明显，并且北疆气温突变发生在1987—1989年，存在30a和14a的周期变化,但对北疆气温空间分布特征的研究较少(16],北疆地区气候主要体现在气温上升、降水增多和蒸发量减少的暖湿化发展[17-18]。考虑到不同学者对气象站点的选择、分析时间尺度和研究方法的不同，北疆地区气候变化研究结果有所差异。

本文为进一步了解北疆地区独特的地理环境导致气温年及季节变化的特点，通过对前人研究的梳理，采用线性倾向率趋势变化，基于地统计的多元回归混合插值，Mann-Kendall突变检测及Matlab的复小波周期分析，对北疆地区1961—2014年长时间序列气温时空变化特征进行分析，确立气温时空域的变化特征，以期深化对北疆地区的气温变化科学认识和定量化研究，为短期气候趋势预测奠定基础，揭示北疆地区的气候变化规律，为北疆地区适应气候变化提供科学依据。

# 1资料与研究方法

# 1.1 资料来源

本研究采用的气象数据来源于中国气象科学数据共享服务（http：/cdc.cma.gov.cn）的中国地面气候资料月值数据集，考虑到气象要素记录的起始时间不尽一致，且个别站点数据缺失，最终选取北疆地区41个气象台站具备完整数据的1961—2014年近54a气温月值数据集（图1）。气象因子包括气象站点的台站号、站点名称、经纬度、海拔高度和月平均气温等指标。本文的季节划分为春季(3—5月）、夏季(6—8月）、秋季(9一11月）、冬季(12月至翌年2月）。根据世界气象组织（WMO)推荐的新气候标准值，以北疆地区各站点气温的平均序列代表北疆的气温序列，分别计算北疆地区全年及季节气温的均值、距平值及累积距平值。

![](images/6ed87b1903059813c28d162d32919c47b2e81ba6a24ba211c0632df7649304ee.jpg)  
图1北疆地区气象站点分布图  
Fig.1Spatial distribution of meteorological stations in north Xinjiang

# 1.2 研究方法

运用线性倾向率、滑动平均，基于ArcGIS的混合插值法、累积距平分析[19]、Mann-Kendall 突变检验及Matlab的Morlet小波分析等方法，对北疆地区年及季节气温变化进行分析。

Mann-Kendall非参数检验法是一种非参数统计检验方法，在气候变化序列平稳的前提下，对于具有$n$ 个样本量的时间序列 $x$ ,构造一秩序列, $d _ { k } = \sum _ { i = 1 } ^ { k } r _ { i }$ ，（ $2 \leqslant k \leqslant n$ )， $r _ { i }$ 表示第 $\mathbf { \chi } _ { i }$ 个样本 $x _ { i }$ 大于 $x _ { j } \left( 1 \leqslant j \leqslant i \right)$

的累计值。

$$
E [ d _ { k } ] = { \frac { k ( k - 1 ) } { 4 } } , V _ { a r } [ d _ { k } ] = { \frac { k ( k - 1 ) ( 2 k + 5 ) } { 7 2 } } \ ,
$$

$$
2 \leqslant k \leqslant n
$$

在时间序列随机独立的假设下，定义统计量，公式为：

$$
U F _ { _ k } = { \frac { d _ { _ k } - E [ } { \sqrt { V _ { _ { a r } } [ } } } , k = 1 , 2 , \cdots , n
$$

在给定显著性水平（取 $\alpha = 0 . \ 0 5$ ，则 $U _ { 0 . 0 5 } ~ =$ $\pm 1 . 9 6 { \dot { } }$ ，当 $\mid U F _ { k } \mid > U _ { \alpha }$ 时,表明序列存在明显的增加或减少趋势。同时，将同样的方法应用到反序列中，得到曲线 $U B _ { k }$ 。 $U F$ 值大于0,表明序列呈上升趋势,小于0表明序列呈下降趋势。统计曲线 $U F$ 、$U B$ ,当超过临界线时，表明上升或下降趋势显著。如果 $U F$ 和 $U B$ 两条曲线相交，且交点在临界线之间，交点所对应的时间便是突变开始的时间。

北疆地区地势起伏悬殊，位于以天山山脊为界的北部地区，地形复杂，形成了新疆复杂的气候类型[20]。气温随海拔的升高而降低,为提供气温空间分布模拟精度，本文采用混合插值（多元线性回归 $^ +$ 残差插值)对北疆年及季节平均气温进行栅格化的空间插值模拟[21-23] O

小波分析是一种信号、时频局部化分析的方法，广泛应用于水文水资源多时间尺度分析、水文时间序列变化特性分析，本研究周期分析采用Morlet小波变换法[24-25] 。

# 2气温变化分析

# 2.1年及季节变化趋势

从图2可以看出，北疆地区年及季节的平均气温呈明显的上升趋势。1961—2014年北疆地区年平均气温变化在 $4 . 0 4 \sim 7 . 6 3 \mathrm { ~ \normalfont ~ \cdot ~ }$ ，气候倾向率为$0 . 3 5 \mathrm { ~ \textcircled { C } ~ } \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { - 1 }$ 。从5a滑动平均趋势线可以看出，北疆地区年平均气温从20世纪60年代初期至70年代初呈下降趋势，在1970年达到气温最低点，1970—1995 年呈冷一暖交替波动，气温呈小幅度波动上升趋势，增温显著。总体上1990 年之前年平均气温相对偏低，1990年以后逐渐偏高，特别在2001年以后升温迅速,年平均气温比多年平均值高0.78$\mathcal { \mathrm { C } }$ ,上升趋势为 $0 . 1 9 \mathrm { ~ \% ~ } \cdot \mathrm { ~ ( ~ 1 0 a ) ~ } ^ { - 1 }$

北疆地区四季平均气温与年气温变化趋势一致。其中秋季增温幅度最大，上升趋势为 $0 . 4 3 \mathrm { ~ } \mathrm { { ^ circ C } }$ ·（10a）-1，冬季次之，为 $0 . 3 9 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { - 1 }$ ,春季为$0 . 3 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ ,夏季为 $0 . 2 4 \mathrm { ~ \textdegree ~ { ~ } ~ } \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { \mathrm { ~ - ~ 1 ~ } }$ 。利用SPSS软件对气温变化线性倾向率进行检验，达到$\alpha = 0 . 0 0 1$ 显著性水平。北疆地区年平均气温和四季平均气温变化趋势与全国年平均气温和四季平均气温变化趋势基本保持一致，但增暖速率明显高于全国水平，尤其是中国东部 $\left[ 0 . 2 6 \mathrm { ~ \% ~ } \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { - 1 } \right]$ ）西部 $\left[ 0 . 1 8 \mathrm { ~ \textdegree C ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { a ~ ) ~ } ^ { - 1 } \right] ^ { \left[ 2 3 \right] }$ 。北疆地区春季平均气温在1960—1990 年呈现大幅波动暖—冷交替的下降趋势，在1969年气温出现最低值，1990年开始气温呈小幅度波动暖一冷交替的上升趋势，在2005一2009年存在一个小的起伏，但春季的总体趋势为上升趋势;夏季平均气温在1960—1972 年呈下

![](images/d8edce3fa7023897344aedf96048b5e1c78a90020eebeab58b52376513354610.jpg)  
图2北疆地区气温年际变化、线性趋势及5a滑动平均

Fig.2Inter-annual variation,linear trend and 5-year moving average of temperature in north Xinjiang降趋势，从1972一2014呈上升趋势，值得说明的是，在1986一1996年经历了较长的偏冷年，之后呈小幅度波动上升趋势，从2001年开始，增温趋势显著；秋季气温1961—2014年呈显著的上升趋势，波动性较强，周期明显，暖一冷多次交替出现;夏季和秋季从2001—2014年增温显著，比多年平均值高 $0 . 6 ~ \mathrm { ^ { 9 } C }$ 和$1 . 0 8 ~ \mathrm { { ^ { \circ } C } }$ ;冬季气温70年代经历了偏冷期，之后呈现上升趋势，波动较小，趋于平稳。虽然北疆地区不同年代、季节平均气温存在差异，但总的发展趋势一致，其中春、夏、秋季和全年平均气温从90年以后增温明显，冬季从80年代开始呈现增温趋势。

# 2.2 气温标准值变化

为了更好地表示近54a来的气候变化趋势，本文以1961—1990 年、1971—2000 年及1981—2014年的气温标准值分析北疆地区大时间尺度上气温变化。如图3所示，1961—1990 年与1971—2000 年相比，北疆地区年、四季气温标准值均增加，分别增加0 $1 . 3 1 \mathrm { ~ \mathcal ~ { C } ~ } , 0 . \ 0 5 \mathrm { ~ \mathcal ~ { C } ~ } , 0 . \ 1 7 \mathrm { ~ \mathcal ~ { C } ~ } , 0 . \ 3 4 \mathrm { ~ \mathcal ~ { C } ~ }$ 和 $0 . 6 8 \mathrm { ~ \textdegree C }$ 。1971—2000 年与1981—2014 年相比,北疆地区年、四季气温标准值分别增加 $0 . 4 9 \mathrm { ~ \sc ~ \circ ~ } _ { \mathbb { C } } \mathrm { ~ , ~ } 0 . 7 2 \mathrm { ~ \sc ~ \circ ~ } _ { \mathbb { C } } \mathrm { ~ , ~ } 0 . 3 3$ $\mathcal { C } \ 、 0 . 5 4 \ \mathrm { ^ c }$ 和 $0 . 3 9 \mathrm { ~ \textdegree C }$ 。可见,北疆地区年及季节标准值在逐渐增加，并在冬季最为明显。

# 2.3线性倾向率空间分布

对41个气象站点气温的年、季节气候倾向率进行插值，得到北疆地区气温增幅变化的空间分布（图4)。近54a来，北疆地区年平均气温呈上升趋势,41站增温显著( $\ P < 0 . 0 5 )$ ，平均增温幅度0.35$\mathrm { { ^ { q } C } \cdot ( 1 0 a ) \Sigma ^ { - 1 } }$ ,气温上升幅度较大的地区位于准噶尔盆地东北部和塔城西北部，升温中心位于富蕴县（204号 $\left[ 0 . 6 7 \mathrm { ~ \% ~ } \cdot \left( 1 0 \mathrm { a } \right) ^ { - 1 } \right]$ ;增温幅度较小的地区为天山伊犁河谷、天山天池及阿勒泰地区，其中北疆天池为气温变化幅度最小的地区 $\left[ 0 . 1 3 \mathrm { ~ \% ~ } \cdot \mathrm { ~ ( ~ 1 0 a ) ~ } ^ { - 1 } \right] .$ （图4a)。

![](images/55f8cab148b165981aefdcf6d167d790e6eb2c63535d967f681dd01934218d48.jpg)  
图3北疆地区气温标准值变化  
Fig.3Standard value change of temperature in north Xinjiang

北疆地区春季气温增温趋势与年气温变化一致,平均升温幅度为 $0 . 3 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ ,空间分布特征为低纬度向高纬度增温幅度逐渐增大，山区增温幅度较小。气温上升幅度较大的地区位于塔城北部和准噶尔盆地北部，增温幅度最大值出现在准噶尔盆地东北部的富蕴县 $\left[ 0 . 5 6 \mathrm { ~ \textdegree C ~ } \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { - 1 } \right]$ ,增温幅度较小的地区为天山北坡伊犁河谷、北疆东部地区及阿勒泰地区，增幅温度最小值出现在温泉[0.001$\mathrm { { } ^ { q } C \cdot ( 1 0 a ) ^ { - 1 } } \mathrm { { ] } }$ （图4b）。

北疆地区夏季气温增温幅度最小，平均增温幅度为 $0 . 2 4 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ ,41个气象台站中37站点$9 0 . 2 \%$ )增温趋势显著( $\cdot P < 0 . 0 5 )$ 。天山山区伊犁河谷地区增温幅度为 $0 . 3 \sim 0 . 6 \ \mathrm { ~ \% ~ } \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { - 1 }$ ,北疆中部准噶尔盆地及阿勒泰地区增温幅度较小，为$0 . 0 7 \sim 0 . 3 \mathrm { ~ \% ~ } \cdot \left( 1 0 \mathrm { { a } } \right) ^ { - 1 }$ ,其中乌鲁木齐、奇台、温泉和阿勒泰气温增幅为负值(图4c）。

北疆地区秋季气温增温幅度为 $0 . 4 3 \mathrm { ~ } ^ { \circ } \mathrm { ~ C ~ }$ ：（10a）-」,空间分布上天山北坡伊犁河谷、天山天池一带及阿勒泰地区增温幅度较小，而塔城大部及准噶尔盆地东北部增温幅度较大，增温幅度均高于$0 . 5 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ （图4d）。

北疆地区冬季气温增温幅度为 $0 . 3 9 \mathrm { ~ \textdegree C }$ ：$( 1 0 \mathrm { { a } } ) ^ { - 1 }$ ,冬季增温较明显的地区为准噶尔盆地东北部、北疆东南部，空间上呈现“山区高、盆地低”的特点，增温幅度最大值出现在乌鲁木齐 $[ 1 . 2 8 \mathrm { ~ } ^ { \circ } \mathrm { C }$ ·$\left( 1 0 \mathrm { a } \right) ^ { - 1 } \cdot$ 1。增温幅度较小的地区为准噶尔盆地东南部、北疆中部地区及阿勒泰地区（图4e）。

# 2.4气温的空间分布特征

高程及经纬度等因素对气温的相关性都较高[26-27],郭春霞等[28]选择经度、纬度和高程等因子进行逐步回归模拟，得出西北地区的模型经度达到0.7以上,胡义成等[29]得出,除冬季外,其他季节 $R ^ { 2 }$ 均高于0.8。本文考虑气温与对应经纬度和海拔高度的关系，建立北疆 $5 4 \mathrm { ~ a ~ }$ 年及季节平均气温(41个气象台站)与气象站经度、纬度和海拔高度的多元回归方程，其中 $x$ 代表气象台站的经度， $y$ 代表气象台站的纬度， $z$ 代表气象台站的高程，方程的 $P$ 小于0.01，达到极显著水平，其方程参见表1。从表1可以看出，回归方程的 $R ^ { 2 }$ 都在0.82以上，春季 $R ^ { 2 }$ 最高达到0.94。

气温随着海拔上升一般呈递减趋势，递减趋势随区域或季节不同而有所差异。利用SPSS软件回归结果获得研究区平均气温随海拔高度变化的直减率，年平均气温随海拔高度变化的气温直减率为$0 . 4 9 1 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ } ( 1 0 0 \mathrm { m } ) ^ { \mathrm { ~ - 1 ~ } }$ ，与标准气温直减率不同，说明不同区域海拔与气温的变化趋势不同。基于Arc-GIS采用多元回归 $^ +$ 残差内插法，对41个气象站气温的年、季节变化插值，得到北疆地区气温的空间分布（图5）。从北疆地区气温栅格数据来看，近 $5 4 \mathrm { ~ a ~ }$ 年平均气温在 $- 8 . 8 3 \sim 1 1 . 6 3 \ \mathrm { ^ { \circ } C }$ ,春季、夏季、秋季和冬季平均气温分别在 $- \ 1 5 . \ 7 6 \ \sim \ 1 4 . \ 5 4 \ \mathrm { ~ \textdegree C } .$ $- 1 2 . 9 3 \sim 2 5 . 7 9 \mathrm { ~ \% ~ } - 9 . 8 9 \sim 1 2 . 2 5 \mathrm { ~ \% ~ }$ 和 $- 1 9 . 9 6 \sim$ $2 . 8 9 \mathrm { ~ \textdegree C }$ 。年及季节平均气温的分布与北疆地形具有一致性。北疆地区春季、夏季和秋季平均气温与年平均气温分布一致。

![](images/42c3676bf3e82dd3e85986a4efd3a5ba1e5f725cc682e49633e7f17e9a0c7905.jpg)  
图4北疆地区年、季节平均气温倾向率空间分布  
Fig.4Spatial distribution of annual and seasonal average temperature trends in north Xinjiang

表1平均气温回归模型  
Tab.1 Regression models of average air temperature   

<html><body><table><tr><td>回归方程</td><td>R</td><td>显著水平</td></tr><tr><td>T年 =64.19-0.2423x-0.7651y-0.003 5z</td><td>0.82</td><td>0.01</td></tr><tr><td>T春 =73.66-0.194 9x-0.985 3y-0.005 4z</td><td>0.94</td><td>0.01</td></tr><tr><td>T夏 =39.44+0.148 9x-0.5571y-0.006 9z</td><td>0.93</td><td>0.01</td></tr><tr><td>T秋 =65.19-0.2324x-0.7863y-0.003 9z</td><td>0.87</td><td>0.01</td></tr><tr><td>T冬 =78.33-0.690 3x-0.729 2y+0.002 2z</td><td>0.88</td><td>0.01</td></tr></table></body></html>

在 $- 1 5 . 7 6 \sim 1 4 . 5 4 ~ \mathrm { ^ { \circ } C }$ ，区域气温空间变幅在 $3 0 \ \mathrm { ^ { \circ } C }$ 以上，这是由北疆独特的地理条件决定的。由图5b可以看出，北疆地区春季气温空间分布总体呈现“山区低,盆地和河谷高”的特点。北疆的阿尔泰山山区、塔城地区东北部和天山山区气温较低，气温多低于 $- 6 ~ \mathrm { { ^ circ C } }$ ;高温区主要出现在伊犁河谷、塔城中部和南部、昌吉大部、哈密地区大部、准噶尔盆地，温度最高出现在伊犁河谷的霍城，为 $1 1 . 9 3 \mathrm { ~ } \mathrm { ^ { \circ } C }$ O

![](images/6851f0cfa246a2c6bae6e12432afb2eb6f1a774fa719d85002a9f5367d7a3fc4.jpg)  
2.4.1春季气温 北疆地区近54a春季平均气温  
图5北疆地区年、季节平均气温空间分布  
Fig.5Spatial distribution of annual and seasonal average temperature in north Xinjiang

2.4.2夏季气温夏季是北疆气温最高的季节，平均气温 $2 1 . 2 9 \mathrm { ~ \textdegree C }$ ,平均气温在 $- 1 2 . 9 3 \sim 2 5 . 7 9 \mathrm { ~ \textdegree C }$ 区域气温空间变幅在 $3 8 ~ \mathrm { { ^ { \circ } C } }$ 以上。由图5c看出，北疆地区夏季气温空间分布呈现“盆地和河谷区域高，山区低"的特点。北疆的阿尔泰山、天山山区气温较低;伊犁河谷、塔城南部、哈密地区、石河子，天山北部准噶尔盆地南部气温较高，温度在 $2 3 \mathrm { ~ \textdegree C }$ 以上。

2.4.3秋季气温北疆地区秋季平均气温6.77$\mathcal { \mathrm { C } }$ ,平均气温在 $- 9 . 8 9 \sim 1 2 . 2 5 \mathrm { ~ ‰ ~ }$ ,区域气温空间变幅在 $2 2 ~ \mathrm { ^ { \circ } C }$ 以上。由图5d看出，北疆地区秋季气温空间分布呈现"盆地河谷高，山区低”的格局。北疆的阿尔泰山山区、天山山区气温较低；伊犁河谷、塔城中南部，昌吉大部、哈密地区及准噶尔盆地南部气温较高，气温在 $8 \ \mathrm { { ^ circ C } }$ 以上。

2.4.4冬季气温北疆地区冬季平均气温-11.48$\mathcal { \mathrm { C } }$ ,平均气温在 $- 1 9 . 9 6 \sim 2 . 8 9 \mathrm { ~ } \mathrm { ~ } ^ { \circ } \mathrm { C }$ ,区域气温空间变幅在 $2 2 ~ \mathrm { ^ { \circ } C }$ 以上。由图5e可以看出，北疆地区冬季气温由西南向东北方向逐渐降低，呈现明显的纬度地带性，天山山区、塔城北部和伊犁河谷地区气温较高 $( \mathbf { \nabla } - 4 \sim 2 . 8 9 ~ \mathrm { \textdegree C }$ )，塔城南部、昌吉大部、准噶尔盆地及准噶尔盆地北部的青河、富蕴和福海等地气温较低。

# 3年、季节气温突变及周期变化

# 3.1 气温突变分析

气温突变是普遍存在于气候变化中的一个重要现象，是气候预测和模拟的重要因素。本文采用Mann-Kendall法绘制北疆地区年及季节平均气温时间序列的M-K统计曲线，显著性水平 $\alpha = 0 . 0 5$ （临界值为 $\pm 1 . 9 6$ )，并结合累积距平法对北疆地区1960一2014年及季节平均气温进行突变检验分析。由累积距平曲线可以看出（图6a），北疆地区年平均气温经历了明显的升降变化过程，1961一1964年呈上升趋势，1965—1990 年呈下降趋势,1991—2014年呈上升趋势，1991年年平均气温出现最低值。Mann-Kendall突变检验结果显示（图6b）， $U F$ 曲线在置信区间与 $U B$ 曲线有一个交点（1991年），且1995年气温上升趋势超过 $\alpha = 0 . 0 5$ 显著性水平。结合Mann-Kendall和累积距平分析，对突变点前后的气温差异进行显著性检验，均通过显著性检验$9 5 \%$ 信度检验），判断得出北疆地区年平均气温在

1991年发生突变，突变前1960—1991年平均气温为 $5 . 7 7 ~ \mathrm { ^ { \circ } C }$ ,突变后年平均气温为 $6 . 7 6 ~ \mathrm { ^ { \circ } C }$ ,突变后比突变前气温上升了 $0 . 9 9 \mathrm { ~ } ^ { \circ } \mathrm { ~ C ~ }$ 。四季平均气温UF与UB曲线在信度区间内均存在交叉点，春季(图6c)在信度区间存在2个交点，1997年和1999 年，结合对春季累积距平值极值的 $\mathbf { \chi } _ { t }$ 检验表明，春季气温突变年为1997年，突变后较突变前气温上升 $1 . 2 ~ \mathrm { ^ { \circ } C }$ ：夏季(图6d)、秋季(图6e)和冬季(图6f)平均气温UF、UB均存在交点且突破临界值，结合累积距平分析突变点 $\mathbf { \chi } _ { t }$ 检验得出，夏季、秋季和冬季平均气温分别在1996年、1994年和1978年发生增温性突变，突变后比突变前气温分别上升了 $0 . 9 0 7 \mathrm { ~ \textcircled { C } } . 1 . 3 7 \mathrm { ~ \textcircled { C } }$ 和 $1 . 7 2 ~ \mathrm { ^ { \circ } C }$ ，其中冬季气温增温最明显。

总的来看，北疆地区年平均气温在1991年发生突变，除冬季外，其他季节平均气温在90年代以后均出现统计意义上的暖突变。

# 3.2气温周期变化分析

北疆地区近54a平均气温变化小波分析反映了小波变化系数随时间周期分布，小波系数实部等值线反映年均气温长序列的不同时间尺度的周期变化及其在时间域的空间分布，小波系数实部为正值，表示气温偏高，负值表示气温偏低，中心值的大小可以反映出波动的震荡强度，等值线中心为冷暖中心。由图7a可以看出，北疆地区年平均气温在1961—2014 年变化过程中存在14a和27a左右时间尺度上震荡周期,在主震荡周期时间尺度27a上出现3个偏低中心和2个偏高中心，分别对应1970 年、1979年、1987年、1996 年和2006年。小波方差反映波动的能量随尺度的分布特征，通过北疆地区年平均气温小波方差图(图7b)显示，小波方差在4a、14a和27a存在极值,说明28a左右周期震荡强烈,对小波方差贡献大。因此，在54a尺度内北疆地区年平均气温变化的主周期约为27a、次周期为14a,其中1961一2014年平均气温主周期经历了冷一暖3次循环交替。提取该尺度的小波系数做图,得到主周期和次周期下年平均气温变化的小波系数过程图（图7c），由于小波系数过程线是对特定尺度下原数据序列信息的提取，因此，小波系数过程线可以反映数据序列在该尺度下的波动信息。从图7c 中可以看出，主周期27a尺度下，北疆地区年平均气温相对偏高阶段为：1961—1966年、1975—1984年、1992一2002年，2011年至今，年平均气温相对偏低阶段为：1967—1974年、1985—1991年、

![](images/bb256754fc10f95467a3dd9fcda36ec51a700d9f088bae7256edf71d41ba5c97.jpg)  
图6北疆地区年及季节平均气温Mann-Kendall突变检验和年平均气温累积距平 Fig.6Mann-Kendall test for abrupt change of annual and seasonal average temperature and accumulated anomalyof annual average temperature in north Xinjiang

2003—2010 年。

20 世纪60—70 年代初表现为11a震荡周期，70 年代中期至21世纪表现为14a震荡周期，且趋于稳定，说明北疆地区年平均气温周期逐渐增大，年平均气温变化渐趋稳定，周期变化具有全域性。

# 4 结果与讨论

本文利用北疆地区41个气象站1961—2014年月气温资料,采用滑动平均、线性倾向率估计，基于ArcGIS混合插值、Mann-Kendall检测及Morlet小波周期等方法，对北疆地区气温的时空变化特征进行分析。结果表明：

（1）北疆地区年及季节平均气温呈显著上升趋势,年平均气温以 $0 . 3 5 \mathrm { ~ \% ~ } \cdot \mathrm { ~ ( ~ 1 0 a ) ~ } ^ { - 1 } \mathrm { ~ ( ~ } P < 0 . 0 1 \mathrm { ~ ) ~ }$ 的速率上升，出现多次冷暖波动过程，四季平均气温均呈上升趋势，且秋季增温幅度最大。气温上升幅度较大的地区位于准噶尔盆地东北部和塔城北部地区；增温幅度较小的地区为天山北坡及阿勒泰东南部,年、春、夏、秋季气温具有空间一致性，呈现“山区低、盆地河谷高”的特点，而北疆冬季平均气温由西南向东北方向逐渐降低。

(2）除冬季外，北疆地区年及季节气温逐渐增加,20世纪90年代以后增温明显，其中北疆地区年、春、夏、秋、冬季平均气温均发生突变,年、春、夏、秋季平均气温突变主要发生在20世纪90年代，冬季平均气温突变发生在1978年。

（3）通过Morlet小波分析表明，北疆地区年平均气温在主周期27a时间出现2个偏高中心和3个偏低中心，此外,还包括14a和5a尺度的变化周

![](images/7b5b483cc0729a6811018bb249d8dab58993a73643bae60da2c7d4036accd4a9.jpg)  
图7小波分析图  
Fig.7Isoline of the real part of Morlet wavelet coefficients, wavelet variance and the wavelet coefficient curves in the principle period scales

期，全域性明显。

本研究发现，北疆地区年平均气温上升趋势显著，该结果与前人研究结果增暖趋势估计值略有差异[15],其主要原因是受到气候要素时间序列不同和研究区域站点的数量及分布不同等所致。北疆地区年、四季平均气温出现多次冷暖波动过程,造成北疆地区气温突变的原因比较复杂，既包括全球气候变暖的连锁效应，也与人类活动的影响密不可分。另外，北疆特殊的地理位置、气候条件、山脉地形阻挡等都会对气温变化产生影响。增温的变化除了与气候系统内部反馈过程、下垫面性质等原因有关外，还包括土地利用方式的改变及温室气体的排放[30],今后的研究应扩大对气候突变的研究，提高自然生态系统对气候变化负面效应的适应能力，避免造成生

# 态环境的恶化。

# 参考文献(References）：

[1]IPCC.Summa for Policymakers of Climate Change 2OO7:The Physical Science Basis.Contribution of Working Group Ito the Fourth Assessment Report of the Intergovernmental Panel on Climate Change[M].Cambridge,UK:Cambridge University Press,2007.

[2]易湘生,尹衍雨,李国胜，等.青海三江源地区近50 年来的气 温变化[J].地理学报,2011,66(11）:1451-1465.[Yi Xiangsheng,Yin Yanyu,Li Guosheng,etal.Temperature variation in recent 5O years in the Three-River Headwaters Region of Qinghai Province[J].Acta Geographica Sinica,2011,66（11）:1 451 - 1 465.]

[3]左洪超,吕世华,胡隐樵.中国近50 年气温及降水量的变化趋势分析〔J].高原气象，2004，23（2）：238－244.［ZuoHongchao,Lv Shihua,Hu Yinqiao.Variations trend of yearly meanair temperature and precipitation in china in the last 5O years[J].Plateau Meteorology,2004,23(2）:238-244.]

[4]任国玉,郭军,徐铭志,等.近50 年中国地面气候变化基本特征[J].气象学报,2005,63（6）：942-956.[RenGuoyu,GuoJun,Xu Mingzhi,et al.Climate changes of China's mainland overthe past half century[J].Acta Meteorological Sinica,2O05,63(6) :942 -956.]

[5]窦睿音,延军平,王鹏涛.全球变化背景下甘肃近半个世纪气温时空变化特征[J].干旱区研究，2015，32（1）：73-79.［DouRuiyin,Yan Junping,Wang Pengtao.Spatiotemporal distribution oftemperature in Gansu Province under global climate change duringtheperiod from1956to 2012[J].Arid ZoneResearch,2015,32(1):73 -79.]

[6]成鹏.乌鲁木齐地区近50a降水特征分析[J].干旱区地理, 2010,33（4）:580-587.[Cheng Peng.Characteristics of precipitationin the Urumqi regions over the past 5O years[J].Arid Land Geography,2010,33（4):580-587.]

[7]关学峰,孙卫国,李敏姣,等.1965—2012 年新疆北部地区气候变化及其对北极涛动的响应[J].干旱区研究,2016,33（4）：681-689.[Guan Xuefeng,Sun Weiguo,Li Minjiao,et al.Climatechange in North Xinjiang and its response to Arctic Oscillation dur-ing the period of1965-2012[J].Arid Zone Research,2016,33(4):681-689.]

[8]杨莲梅，曾勇，刘雯.北疆冬季持续性低温事件特征及大气环流异常分析[J].气候变化研究进展，2016，12（6)：508-518.[YangLianmei,Zeng Yong,Liu Wen.Characteristics of persistentlow temperature events and analysis of atmospheric circulation a-nomaly in winter in Northern Xinjing[J].Climate Change Re-search,2016,12(6):508-518.]

[9]刘波,冯锦明，马柱国,等.1960—2005 年新疆气候变化的基本特征[J].气候与环境研究，2009，14（4）：414-426.[LiuBo，Feng Jinming,Ma Zhuguo,et al.Characteristics of climate changesin Xinjiang from1960 to 2005[J].Climatic & Environment Re-

search,2009,14(4) :414 -426.]

[10]殷剑虹，徐予洋.伊犁河谷气候变化特征分析[J].沙漠与绿洲 气象,2007,1（6）:20-23.[Yin Jianhong,Xu Yuyang.Analysis ofclimatechangecharacteristicsin Yili Valley[J].Desertand OasisMeteorology,2007,1(6) :20-23.]

[11］沈伟.1953—2008年新疆北部地区降水变化趋势分析[J].水资源与水工程学报，2010，21（4）：130-134.［ShenWei.Trendanalysis of precipitation in Northern Xinjiang during 1953-2008[J].Journal of Water Resources& Water Engineering,2010,21(4):130-134.]

[12]张家宝，史玉光.新疆气候变化及短期气候预测研究[M].北 京：气象出版社,2OO2.[Zhang Jiabao,Shi Yuguang.Study on Climate Change and Short-term Climate Prediction in Xinjiang[M]. Beijing:China MeteorologicalPress,2002.]

[13]张新,刘兴旺，卢戈，等.新疆博州地区降水量、降水日的时空 变化[J].沙漠与绿洲气象,2008,2(3）：12-17.[Zhang Xin, Liu Xingwang,Lu Ge,et al.Spatial-temporal change of the precipitation and wet daysin Bole region of Xinjiang[J].Desert and OasisMeteorology,2008,2(3):12-17.]

[14]马建勇，潘婕,姜江,等.北疆地区1955—2009 年气温、降水变化特征的时间序列分析[J].沙漠与绿洲气象，2012,6（2）：18-24.[Ma Jianyong,Pan Jie,Jiang Jiang,et al.The time series a-nalysis of temperature and precipaitation in Northern Xinjiang dur-ing1955-2009[J].Desert and Oasis Meteorology,2012,6（2）：18 -24.]

[15]何毅，杨太保，陈杰，等.1955一2012年南北疆气温、降水及相对湿度趋势分析[J].水土保持研究，2015，22（2）：270-277.[HeYi,Yang Taibao,ChenJie,etal.Long-term trend of tempera-ture,precipitation and relative humidity in the Northern and South-ernregions of the Xinjiang from 1955 to 2012[J].Research of Soiland Water Conservation,2015,22(2）:270-277.]

[16]张延伟，葛全胜，姜逢清，等.北疆地区1961—2010 年极端气温事件变化特征[J].地理科学，2016，36（2）：296-302.[Zhang Yanwei,Ge Quansheng,Jiang Fengqing,et al.Evolutioncharacteristics of the extreme high and low temperature event inNorthern Xinjiang in 1961-2010[J].Scientia Geographica Sini-ca,2016,36(2):296-302.]

[17]施雅风,沈永平，李栋梁，等.中国西北气候由暖干向暖湿转型的特征和趋势探讨[J].第四纪研究，2003，23（2）：152-164.[Shi Yafeng,Shen Yongping,Li Dongliang,et al.Discussion on thepresent climate change from warm dry to warm wet in NorthwestChina[J].Quaternary Sciences,2003,23（2）:152-164.]

[18］刘昌明,张丹.中国地表潜在蒸散发敏感性的时空变化特征分 析[J].地理学报,2011,66（5）:579-588.[Liu Changming, Zhang Dan.Temporal and spatial change analysis of the sensitivity of potential evapotranspiration to Meteorological influencing factors in China[J].Acta Geographica Sinica,2011,66(5）:579 -588.] [19]魏凤英.现代气候统计诊断预测技术[M].北京：气象出版社， 2007:42-113.[Wei Fengying.Modern Technology of Statistics, Diagnosis and Forecast for Climate[M].Beijing:China Meteoro

logical Press,2007:42-113.]

[20]张山清，普宗朝.新疆参考作物蒸散量时空变化分析[J].农业 工程学报,2011,27（5）：73－79.［Zhang Shanqing，Pu Zongchao.Study on temporal and spatial variation characteristics of reference evapotranspiration in Xinjiang[J].Transactions of the CSAE,2011,27(5):73-79.]

[21]李景林，张山清，普宗朝,等.近50a新疆气温精细化时空变化 分析[J].干旱区地理,2013,36（2）:228-237.[LiJinglin， Zhang Shanqing,Pu Zongchao,et al.Spatial-temporal variation of seasonal and annual air temperature in Xinjiang during 1961 - 2010[J].Arid Land Geography,2013,36(2）:228 -237.]

[22]普宗朝，张山清，宾建华，等.新疆一乌昌地区干湿气候要素时空变化分析[J].资源科学，2011，33（12）：2314-2322.[PuZongchao,Zhang Shanqing,Bin Jianhua,et al.Dry-wet climate ele-ments spatial-temporal variation analysis in Urumqi-Changji Regionof Xinjiang[J].Resources Science,2011,33（12）:2 314-2 322.]

[23]普宗朝，张山清，宾建华，等.新疆乌昌地区热量资源精细化时 空变化分析[J].中国农业气象，2011,32（4)：598-606.［Pu Zongchao,Zhang Shanqing,Bin Jianhua,etal.Analysis of fine spatial-temporal variation of agroclimatic heat resource in UrumqiChangji Region of Xinjiang[J].Chinese Journal of Agrometeorology,2011,32(4) :598-606.]

[24]张星，彭云峰，谢怡芳，等.闽江河口湿地气候变化趋势与突变 分析[J].中国农业气象,2010,31(3）:364-368.[Zhang Xing， PengYunfeng,Xie Yifang,et al.Analysis on climate change in Minjiang estuary wetland[J]. Chinese Journal of Agrometeorology, 2010,31(3) :364-368.]

[25]王建兵，王素萍，汪治桂.1971—2010 年若尔盖湿地潜在蒸散量及地表湿润度的变化趋势[J].地理科学，2015，35（2）：245-250.[Wang Jianbing,Wang Suping,Wang Zhigui.The varietycharacters of potential evapotransiration and soil surface humidityindex in the Zoige Wetland in1971-2010[J].Scientia Geograph-ica Sincia,2015,35(2):245-250.]

[26]王艳霞，黄晓园，赵璠，等.气温场的云南纬度与气温关系分析 [J].遥感信息,2016,31(6）:44-50.[Wang Yanxia,Huang Xiaoyuan,Zhao Pan,et al.Analysis of relationship between latiyude and temperature in Yunnan Province using temperature fields[J]. Remote Sensing Information,2016,31(6）:44-50.]

[27]马新萍，白红英，郭帅，等.秦岭太白山气温垂直递减率研究 [J].干旱区资源与环境,2017,31（7）：139-144.［MaXinping,Bai Hongying,Guo Shuai,et al.Verification of temperature vertical lapse rate and mountain climate characteristics of Taibai Mountains in Qinling Mountains[J].Journal of Arid Land Resources and Environment,2017,31(7）:139-144.]

[28]郭春霞，粟忠魁，诸云强，等.局部回归克里格在气温栅格化中的应用[J].首都师范大学（自然科学版），2016，37（6)：85-92.[Guo Chunxia,Li Zhongkui,Zhu Yunqiang,et al.Appliction oflocal regresson kriging in mean annual air temperature estimation[J].Journal of Capital Normal University（NaturalScience Edi-

tion),2016,37(6):85 -92.]

[29]胡义成，姚作新，秦荣茂，等.基于KBSI模型的新疆平均气温空间插值研究[J].沙漠与绿洲气象，2016，10（3）：66-71.[Hu Yicheng,Yao Zuoxin,Qin Rongmao,et al. Study on spatialinterpolation of mean temperature based on KBSI model in Xinjiang

[J].Desert and Oasis Meteorology,2016,10(3）:66-71.] [30]丁一汇,张锦,徐影,等.气候系统的演变及其预测[M].北京： 气象出版社,2003：51-64.[Ding Yihui,Zhang Jin,Xu Ying,et al.Evolution and Forecast of Climatic System[M].Beijing:China Meteorological Press,2003:51 -64.]

# Spatiotemporal Variation of Temperature in North Xinjiang during the Periodof1961—2014

TAN Jiao $^ { 1 , 2 }$ ，DING Jian-l²，ZHANGJun-yong $^ { 1 , 2 }$ ， WU Peng-fei² (1.Key Laboratoryof Wisdom City and Environmental Modeling of Ministry of Education,Xinjiang University, Urumqi 830046,Xinjaing,China ; 2.Key Laboratory of Oasis Ecology of Ministry of Education,Urumqi 830046,Xinjiang,China ; 3.Urumqi Meteorological Satelite Ground Station,Urumqi 830o11,Xinjiang,China)

Abstract:Inthis study,the monthlyaverage temperature data from 41 meteorological stations in north Xinjiang duringthe period from 196l to 2014 were used to analyze the annual and seasonal abrupt changes of temperature. The methods of lineartrend analysis,moving average,three-dimensional quadratic trend surface simulation based on GIS,cumulative anomaly analysis，Mann-Kendalltest and Morlet analysis based on Matlab were applied.The main results are as follows : $\textcircled{1}$ The average annual and seasonal temperatures in north Xinjiang were characterized by several coldand warm fluctuations,however,the average temperature was holisticall in asignificant increase trendat statistically significance level since the 199Os except that in winter; $\textcircled{2}$ The increase of average annual temperature in north Xinjiang was $0 . 3 5 \mathrm { ~ \textcircled { C } ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ . The significant temperature increase occurred in the Junggar Basin, Tacheng and north Fuyun County ; $\textcircled{3}$ There were the abrupt changes in average seasonal temperature and annual temperature in north Xinjiang.The abrupt changes in average annual,spring,summer and autumn temperature occurred mainly in the late 199Os,but those in average winter temperature mainly in the late 1970s ; $\textcircled{4}$ There was a 27 - year main period of the changes of annual and seasonal temperature in north Xinjiang,and alsoal4 -year sub-period during the period from 1961 to 2014.The high-low temperature alternations were global.

Key words:temperature variation ;regional difference ;abrupt change ; wavelet analysis ; north Xinjiang