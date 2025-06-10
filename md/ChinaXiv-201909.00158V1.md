# 基于SPI的黑龙江省干旱时空特征分析

于家瑞¹，艾萍¹²，袁定波，熊传圣}（1河海大学水文水资源学院,江苏南京210098；2河海大学计算机与信息学院,江苏南京210098）

摘要：利用黑龙江省10个气象站点1953—2015年逐日降水数据，计算不同尺度下的标准化降水指数(SPI),并结合游程理论分析黑龙江省干旱的时空演变特征。结果表明：降水仍是黑龙江省干旱的主要影响因素；黑龙江省干旱夏季和秋季呈增强趋势，SPI变化速率分别为每 $1 0 \mathrm { ~ a ~ }$ 下降0.029、0.135，春旱和冬旱呈缓解趋势，速率为每10a上升0.061、0.074，年 $S P I$ 变化速率为每10a下降0.044;黑龙江省20世纪60年代中后期 $\sim 7 0$ 年代末，干旱较为频繁，且干旱的持续时间长、干旱程度大、干旱强度大，出现了1974—1980年的连续干旱期，80年代 $\sim 9 0$ 年代中期较为正常，90年代末及之后,干旱频率及其持续时间、程度、强度呈增加趋势;干旱事件的持续时间从西北向东南呈增加一减少趋势，黑龙江省中部的干旱事件持续时间最长。

关键词：干旱；黑龙江省； $S P I$ ；时空特征

干旱是人类面临的主要自然灾害之一，其特点是波及范围广、持续时间长、影响行业多[1]。黑龙江省地处湿润半湿润地区，是我国的产粮大省，干旱的频繁发生严重影响了黑龙江省的粮食产量，进而影响我国的粮食安全。受干旱影响，黑龙江省1949—1990 年粮食减产 $2 . 3 9 \times 1 0 ^ { 1 0 } \mathrm { k g } ^ { [ 2 ] }$ ;2010年黑龙江省出现两次干旱过程，对农业的影响较大;2011年,干旱共造成农作物受灾面积 $7 . 0 3 \times 1 0 ^ { 5 } \ \mathrm { h m } ^ { 2 }$ ,绝收面积 $3 . 0 0 \times 1 0 ^ { 4 } ~ \mathrm { h m } ^ { 2 }$ ;2012 年干旱造成黑龙江省农作物受灾面积 $1 . 2 0 \times 1 0 ^ { 6 } \mathrm { h m } ^ { 2 }$ ,直接损失达 $1 . 2 3 \times$ ${ 1 0 } ^ { 9 }$ 元。因此,对黑龙江省干旱的时空特征进行深入研究的需求更加迫切。

孙滨峰等[3]利用标准化降水蒸发指数研究了东北地区的干旱时空特征，利用主成分分析和聚类分析将东北划分为8个干旱相似区，黑龙江省大部分地处干旱增加区;赵茹欣等[4]运用标准化降水指数（SPI)和主成分分析法对黑龙江省气象干旱的时空特征进行了分析，得出黑龙江省气象干旱空间分布呈现整体一致性和西北一东南对立分布两种态势，以及在2000年后干旱趋势显著的结论；马建勇等[5]运用 SPI和相对湿润指数对东北地区5\~9月干旱趋势进行了分析，得出黑龙江省大部分地区呈干旱化趋势的结论。当前多数研究都是基于某种指数对黑龙江省的干旱进行评估，重点关注干旱发生的频率、程度、分布特征，对于干旱的持续时间、时空演变特征的研究较少。芦佳玉等[运用标准化降水蒸发指数、游程理论以及经验正交函数对云贵地区干旱历时以及干旱强度的变化规律及特征进行了研究，较好的揭示了云贵地区干旱变化趋势;杨好周等[7]运用游程理论结合降水距平百分率来估计区域干旱历时的重现期，认为该方法确实能够为确定干旱的分布规律提供依据。

SPI作为一种计算简单、适用于多尺度且较为准确的干旱指数，在东北地区获得了较为广泛的应用[8-9]。本文利用 SPI对黑龙江省干旱进行评估,并结合游程理论，分析黑龙江省干旱的持续时间、时空演变等特征，以期为农业抗旱、灌溉以及水资源规划提供科学依据。

# 1研究区概况与研究方法

# 1.1 研究区概况

黑龙江省位于我国最东北部（ $1 2 1 ^ { \circ } 1 1 ^ { \prime }$ \~$1 3 5 ^ { \circ } 0 5 ^ { \prime } \mathrm { E }$ ， $4 3 ^ { \circ } 2 5 ^ { \prime } \sim 5 3 ^ { \circ } 3 3 ^ { \prime } \mathrm { N }$ ;图1）。黑龙江省西北部为东北一西南走向的大兴安岭山地，北部为西北一东南走向的小兴安岭山地，东北部为三江平原，东南部为东北一西南走向的张广才岭、老爷岭、完达山。地势西北部、北部、东南部高，东北部、西南部低。黑龙江省属寒温带大陆性气候，春季少雨干旱，夏季湿热多雨，秋季冷凉，冬季漫长干燥。多年平均气温 $- 5 \sim 5 \mathrm { ~ } \mathrm { ~ \mathcal { C } ~ }$ ,由南向北降低。年降水量 $4 0 0 \sim 6 5 0$ $\mathbf { m } \mathbf { m }$ ,中部山区多，西、北部少。

![](images/5214d0008ff6201bced525ac2bdaf0aa746a937959a6c174587048dd192c0b46.jpg)  
图1研究区气象站点分布 Fig.1Location and meteorological stations of Heilongjiang Province

# 1.2 数据来源

本文所用的数据来源于中国气象局发布的《中国地面气候资料日值数据集》中黑龙江省10个地面基准气象观测站1953—2015年的逐日降水数据和气温数据，且选择的站点分布较为均匀，该资料是无缺值连续资料，在我国气候研究中已得到广泛认可和应用。63a的数据资料，时间跨度较大，可在一定程度上反映黑龙江省的降水变化情况，代表性较好。

# 1.3 研究方法

1.3.1标准化降水指数标准化降水指数(SPI)认为降水量分布不是正态分布，而是一种偏态分布，采用I分布概率来描述降水量的分布，计算出降水量I分布概率后，经正态标准化处理，最终用标准化的降水累积频率分布来划分干旱等级。SPI1、SPI3、SPI6和SPI12分别指1、3、6个月和12个月尺度的SPI值。具体计算公式可参考国家气候中心制定的《气象干旱等级标准》。等级划分见表1。

# 表1标准化降水指数(SPI)干旱等级划分

Tab.1 Classification scales for SPI   

<html><body><table><tr><td>干旱等级</td><td>指数范围</td></tr><tr><td>无旱</td><td>SPI > -0.5</td></tr><tr><td>轻旱</td><td>-1<SPI≤-0.5</td></tr><tr><td>中旱</td><td>-1.5<SPI≤-1</td></tr><tr><td>重旱</td><td>-2<SPI≤-1.5</td></tr><tr><td>特旱</td><td>SPI≤-2</td></tr></table></body></html>

1.3.2游程理论一个有限取值序列中，满足一定条件的同一符号(即同类事件)的一连串称为一个“游程”，一个游程中同一符号连续出现的次数为游程长度[10]。袁文平[1]也指出,引起干旱有两种直接原因，一个是当前的降水缺乏引起的土壤水分亏缺，另一个是长期的降水缺乏导致的用于补给的水分亏缺。持续时间久的 $S P I < 0$ 事件会导致水资源不足,产生与干旱有关的问题[12],因此将 $S P I { \leqslant } 0$ 时定义为发生了一次干旱事件，游程长度为干旱持续时间 $( D ; D = 1 , 2 , 3 , \cdots$ ·月）,在游程中反映干旱事件累积干旱缺水状况为干旱程度 $s$ ，公式如下：

$$
S = \sum _ { j = 1 } ^ { D } S P I _ { j }
$$

反映干旱事件平均干旱缺水状况为干旱强度I,公式如下：

$$
I = { \frac { S } { D } }
$$

式中： $0 < I < 1$ 时为轻度干旱；当 $1 \leqslant I < 1 . 5$ 时为中度干旱;当 $1 . { \ 5 \leqslant I < 2 }$ 时为重度干旱；当 $I { \geq } 2$ 时为极端干旱。

# 2结果分析

# 2. 1 SPI适用性验证

干旱的实质是水分亏缺，其与降水、气温密切相关[13],二者都可以影响水分情况,气温是通过潜在蒸发量影响地区水分，进而对干旱的发生产生影响。本文对降水、气温以及Thornthwaite方法计算的潜在蒸发量进行计算分析，结果表明（表2），降水多年均值为 $4 3 8 . 2 6 \ \mathrm { m m }$ ,潜在蒸发量仅为 $2 9 . 8 2 \ \mathrm { m m }$ ,在东北作物生长关键期（5\~9月），降水最大倾向率为-5.56,而潜在蒸发量仅为0.22。可见，由气温引起的潜在蒸发量，多年来量级较小且变化较小，降水量无论是量还是变化程度，都是潜在蒸发量的数倍，因此在黑龙江省，降水仍是干旱的主要影响因

# 表2黑龙江省降水与潜在蒸发量

Tab.2Precipitation characteristics and potential evaporation characteristics in HeilongjiangProvince   

<html><body><table><tr><td rowspan="2">月份</td><td colspan="2">均值／mm</td><td colspan="2">倾向率／mm·a-1</td></tr><tr><td>降水</td><td>潜在蒸发量</td><td>降水</td><td>潜在蒸发量</td></tr><tr><td>1</td><td>39.60</td><td>0.00</td><td>-0.07</td><td>0.00</td></tr><tr><td>2</td><td>43.82</td><td>0.00</td><td>0.06</td><td>0.00</td></tr><tr><td>3</td><td>96.37</td><td>0.00</td><td>0.48</td><td>0.00</td></tr><tr><td>4</td><td>224.42</td><td>2.90</td><td>0.11</td><td>0.11</td></tr><tr><td>5</td><td>449.18</td><td>43.03</td><td>1.56</td><td>0.22</td></tr><tr><td>6</td><td>826.35</td><td>77.58</td><td>1.39</td><td>0.18</td></tr><tr><td>7</td><td>1 418.42</td><td>94.73</td><td>0.68</td><td>0.06</td></tr><tr><td>8</td><td>1 144.98</td><td>86.72</td><td>-2.93</td><td>0.05</td></tr><tr><td>9</td><td>592.24</td><td>49.62</td><td>-5.56</td><td>0.03</td></tr><tr><td>10</td><td>258.48</td><td>3.22</td><td>-0.12</td><td>0.06</td></tr><tr><td>11</td><td>98.37</td><td>0.00</td><td>0.78</td><td>0.00</td></tr><tr><td>12</td><td>66.86</td><td>0.00</td><td>0.65</td><td>0.00</td></tr><tr><td>平均</td><td>438.26</td><td>29.82</td><td></td><td></td></tr></table></body></html>

子，可以用SPI来研究黑龙江干旱情况。

本文以黑龙江省2004年、2010年、2011年干旱事件记载，与3个时间尺度的SPI值对比，来验证其适用性。据记载,2004年春播前期土壤干旱，5月降水偏多，6月全省发生大规模严重干旱；2004年春旱连初夏旱;2010 年5月降水为1961年以来历史同期最多，后春至初夏干旱，9月干旱严重；2011年8月部分地区出现重旱，入秋后发生干旱。从表3、图2中可知，SPI1在2014年识别出2次干旱，4月监测结果为轻旱，6月为重旱，在2010年识别出2次干旱，6月（-0.88)是轻旱，9月是重旱，在2011年监测出3次干旱，为8月、9月和10月，均监测为轻旱；SPI3的结果表明，在2004年 $4 \sim 6$ 月干旱,即春旱以及初夏旱，在2010年仅识别出1次干旱，8～9月干旱，等级为中旱,2011年8～10月均为中旱，

表3黑龙江省2004年、2010年和2011年部分月SPI1、SPI3SPI12值Tab.3SPI1、SPI3 and SPI12 in HeilongjiangProvincein 2004,2010 and 2011  

<html><body><table><tr><td>年份</td><td>月份</td><td>SPI1</td><td>SP13</td><td>SPI12</td></tr><tr><td rowspan="3">2004</td><td>4</td><td>-0.90</td><td>-1.00</td><td>-1.01</td></tr><tr><td>5</td><td>0.78</td><td>-0.54</td><td>-0.58</td></tr><tr><td>6</td><td>-1.90</td><td>-1.03</td><td>-0.72</td></tr><tr><td rowspan="3">2010</td><td>6</td><td>-0.88</td><td>-0.13</td><td>-0.48</td></tr><tr><td>9</td><td>-1.54</td><td>-1.35</td><td>-0.75</td></tr><tr><td>8</td><td>-0.67</td><td>-1.34</td><td>-0.15</td></tr><tr><td>2011</td><td>9</td><td>-0.93</td><td>-1.24</td><td>-0.08</td></tr><tr><td></td><td>10</td><td>-0.95</td><td>-1.08</td><td>0.71</td></tr></table></body></html>

即入秋后干旱;SPI12在2014年4\~6月监测出干旱,在2010年9\~12月识别出1次干旱。可见随着时间尺度的增加，干旱等级会发生变化，干旱持续时间变长，这也充分说明了前期降水的累计影响。时间尺度越小，SPI对于一次降水或短期降水的变化越显著，值的变化幅度大，甚至是正负变化，时间尺度越大，则对于一次降水的反应越不显著，只有持续的多次降水才会使其发生波动。这对于监测长时间的水分变化情况是合理的[14]。以上分析表明,SPI与黑龙江省干旱记载较为吻合，能较好的反应黑龙江省的干旱情况，且SPI1和SPI可以用来分析黑龙江省短期的干旱特征，SPI12可以用来分析黑龙江省长期的干旱变化。

# 2.2 干旱变化特征

不同季节变化及等级频次的分布存在较大差异，如图3所示，夏秋两季的变化速率分别为每10a下降0.029和0.135，春冬两季的变化速率为每10a增长0.061和0.074，说明从长期变化趋势上看，黑龙江省夏季与秋季干旱呈增强趋势，冬季和春季干旱呈减轻趋势，且秋季趋势要强于夏季。春季干旱的频次为18次，夏季干旱的频次为19次，秋季干旱的频次为20次，冬季干旱的频次为17次，发生干旱的频率分别为 $2 8 . 5 7 \% . 3 0 . 1 6 \% \ . 3 1 . 5 7 \%$ 和 $2 6 . 9 8 \%$ ;极旱季分别出现在1992年春季（SPI值为-1.31），1954年和2007年夏季（SPI值分别为－1.86和-1.55），2001年秋季（-1.66）以及1967年冬季（-2.32）。据《中国气象灾害年鉴》中记载，2007年夏季，黑龙江大部分地区高温少雨，发生了历史罕见的夏旱,平均降水量为 $1 4 3 . 1 \ \mathrm { m m }$ ,为历年同期次少值（仅次于1954年）。

图4所示，黑龙江省近63a的SPI值呈弱降低趋势，速率为每10a下降0.044，干旱年的频次为16次。20世纪60 年代,黑龙江省干旱的频率约为3a一次,70年代约为2a一次,80 年代约为5a一次，90 年代约为3a一次,2000—2009 年，约为2.5a一次。黑龙江省在70 年代干旱最为频繁,在 $8 0 \sim$ 90 年代略有减缓,在2000 年之后，干旱频率开始上升。

# 2.3干旱事件时间变化特征

在1个月尺度、3个月尺度和12个月尺度下，将一次干旱事件开始的年份作为该次事件的名称。据图5可知，1个月尺度、3个月尺度、12个月尺度干旱事件持续时间的变化率分别为每10a下降

![](images/f1256881c9378163fda5fdc2b0c62625825ea18ecd93b3f5efd012e5804e8c64.jpg)  
图21953—2015 年黑龙江省 SPI1、SPI3 和 SPI12 值  
Fig.2SPI1,SPI3 and SPIl2 in Heilongjiang Province during 1953—2015

0.006、0.022和1.014，平均持续时间为3.44个月、5.14个月、12.38个月。1个月尺度下干旱时间持续时间在1\~8月之间，持续时间最长的是2002 年11月开始的干旱事件，持续了8个月；3个月尺度下，持续时间最长的是1974年10月开始的干旱事件,持续了16个月；12个月尺度下，持续时间最长的是1974年9月开始的干旱事件，持续了71个月。在1974年9月 $\sim 1 9 8 0$ 年8月这71个月里，1个月和3个月的SPI识别出多次干旱事件，持续时间较12个月的要小，1个月尺度下，识别出17次干旱事件,持续时间介于1\~7个月之间，三个月持续下识别出8次干旱事件，持续时间介于 $3 \sim 1 6$ 个月之间。1个月尺度下，1974—1977年是干旱事件持续时间最长的阶段,1978—2001年是干旱事件持续较短的阶段，2001年之后，干旱时间持续时间又开始增多。3个月尺度下，1964—1967年、1974—1979 年是干旱事件持续较长的阶段，1980—1998年是干旱时间持续时间较短的阶段，之后持续时间又开始增多。12个月尺度下，1974—1980年是干旱事件持续最长的阶段，之后1981一1996年是持续时间较短的阶段，之后持续时间开始增多。通过上述分析，3个尺度下的干旱事件持续时间的变化趋势是基本一致的，在时间上的一些差异，可能是由于小尺度SPI对一次降水较更大尺度的要更敏感，

![](images/4e399471f4db0a98fe69674e0efbf09156a2da0c3414a6df99f38173e72f5324.jpg)  
图31953—2015 年黑龙江四季的 SPI值变化  
Fig.3Change of different seasons $S P I$ in Heilongjiang Province during 1953—2015

由图6可以看出，1个月、3个月尺度下，干旱程度变化的速率分别为每10a上升0.005和0.02，12个月尺度下，干旱程度变化的速率为每10a下降0.395，平均干旱程度分别为1.27、2.27和6.38。1个月尺度下，1966年11月开始的干旱事件干旱程度最大，为4.78；3个月尺度下，1974年10月开始的干旱事件干旱程度最大，为10.19;12个月尺度下，1974年9月开始的干旱事件干旱程度最大，为

![](images/74a4e29b4a3821116b717747ffb1f83444c1422a41573046cd58af5f41fd61b3.jpg)  
Fig.4Evolution of annual $S P I$ in Heilongjiang Province during 1953-2015

![](images/9a5d683e5582c4e07bcf061d35d667fee5fedba6a456ebc714eefa52c8fd06dc.jpg)  
图41953—2015 年黑龙江省年 SPI值变化  
图51953—2015 年黑龙江省 SPI1、SPI3 和 SPI12干旱持续时间变化  
Fig.5Changes of $S P I 1$ ， $S P I 3$ and $S P I 1 2$ drought events duration in Heilongjiang Province during 1953—2015

![](images/f72ded61fd33481ae600d8ccc480d935b3c821f916efe762294dab29f4cfd981.jpg)  
图61953—2015 年黑龙江省 SPI1、SPI3 和 SPI12干旱事件干旱程度变化  
Fig.6Changes of SPI1,SPI3 and $S P I 1 2$ drought events severity in Heilongjiang Province during 1953—2015

58.9。从整体上看，干旱程度与干旱持续时间的分布相似。1个月尺度下，1964—1969年、1974—1976年是干旱程度较大的阶段，之后1977一2000年是干旱程度较小的阶段，2000年以后干旱程度增加。3月尺度下，1969年、1974—1976年是干旱程度较大阶段，之后干旱程度较小，直到1999年开始变大。12个月尺度下，1974—1980 年是干旱程度较大阶段，之后干旱程度较小，至1998年开始增大。从整体上看，3个尺度下干旱程度变化的趋势也基本一致。

由图7可以看出，1个月和3个月尺度下，干旱强度变化的速率分别为每10a上升0.006和0.01，12个月尺度下，干旱强度变化的速率为每10a下降0.012，平均干旱强度分别为0.61、0.52和0.37。1个月尺度下，2002年9月开始的干旱事件，干旱强度最大，为2.39;4个月尺度下，1968年12月开始的干旱事件，干旱强度最大，为1.59;12个月尺度下，1998年9月开始的干旱事件，干旱强度最大，为1.02。从整体上看，干旱强度的趋势同干旱持续时间、干旱程度相似，但在具体时间上与两者有一定的区别。如1个月尺度下，1964—1967年、1974—1976年是干旱持续时间较长和干旱程度较大的阶段，但干旱强度却不是最大;3个月尺度下，干旱强度最大的是1968年12月开始的干旱事件，而非在1974—1976年阶段里;12个月尺度下，干旱强度最大的是1998年9月开始的干旱事件，1974—1980年阶段的干旱强度是第4大值。

![](images/a1d1e701b76547d9ec538806628203846af010debfe02e46114ccb5fb9f7db20.jpg)  
图71953—2015 年黑龙江省 SPI1、SPI3 和 SPI12 干旱事件干旱强度变化  
Fig.7Changes of SPI1,SPI3 and $S P I 1 2$ drought events intensity in Heilongjiang Province during 1953—2015

黑龙江省干旱事件在时间上的变化特征，从整体上来说，大致可以分为4个阶段：（1）20世纪60年代以前,发生持续时间长、干旱程度大或干旱强度大的干旱事件较少。（2）60年代到70年代末，黑龙江省呈现干旱化现象,发生连续性干旱,干旱程度大，强度较大。（3）80年代到90年代中期，干旱事件的持续时间较短，干旱程度较小，干旱强度较小。（4）90年代末及2000年以后，干旱事件的持续时间开始变长，干旱程度增大，干旱强度增大。上述结果与王学哲等[15]利用修正Z指数对黑龙江省旱涝时空特性的分析基本一致,与韩晓君[16]统计的黑龙

江省历史记录相吻合。

# 2.4干旱事件空间变化特征

如表4所示，1个月尺度下，黑龙江省牡丹江干旱事件持续时间最短，为2.76个月，尚志的持续时间最长，为3.43个月；3个月尺度下，哈尔滨市干旱事件持续时间最短，为4.43个月，安达最长，为5.64个月；12个月尺度下，克山持续时间最短，为10.70个月，海伦最长，为13.46个月。黑龙江省，从西北向东南，干旱事件持续时间平均值呈增加一减少趋势，在黑龙江省中部，干旱的持续时间最长。

1个月和3个月尺度下，干旱事件干旱程度的空间变化不明显，其值分别在 $2 . 3 6 \sim 2 . 8 3 \$ 与3.87\~4.70间波动，12个月尺度下，干旱事件干旱程度的变化明显大于1个月和3个月尺度，其最大值在安达，为11.97，最小值在克山，为9.05。

表4黑龙江省不同地区1953—2015年SPI1、SPI3和 SPI12干旱事件  
Cab.4SPI1,SPI3 and SPI12 drought events features in different areas in Heilongjiang Province during 1953—2(   

<html><body><table><tr><td rowspan="2">站点</td><td colspan="3">干旱持续时间/月</td><td colspan="3">干旱程度</td><td colspan="3">干旱强度</td></tr><tr><td>SPI1</td><td>SPI3</td><td>SPI12</td><td>SPI1</td><td>SPI3</td><td>SPI12</td><td>SPI1</td><td>SPI3</td><td>SPI12</td></tr><tr><td>克山</td><td>2.86</td><td>4.81</td><td>10.70</td><td>2.45</td><td>4.37</td><td>9.05</td><td>1.15</td><td>0.92</td><td>0.47</td></tr><tr><td>海伦</td><td>2.92</td><td>4.48</td><td>13.46</td><td>2.57</td><td>3.87</td><td>11.77</td><td>1.06</td><td>0.85</td><td>0.59</td></tr><tr><td>安达</td><td>3.05</td><td>5.64</td><td>13.42</td><td>2.79</td><td>4.70</td><td>11.97</td><td>1.05</td><td>0.81</td><td>0.65</td></tr><tr><td>哈尔滨</td><td>3.24</td><td>4.43</td><td>12.15</td><td>2.58</td><td>3.96</td><td>10.10</td><td>0.93</td><td>0.90</td><td>0.65</td></tr><tr><td>尚志</td><td>3.43</td><td>4.79</td><td>11.27</td><td>2.83</td><td>4.44</td><td>10.19</td><td>1.03</td><td>0.95</td><td>0.68</td></tr><tr><td>牡丹江</td><td>2.76</td><td>4.72</td><td>11.23</td><td>2.36</td><td>4.07</td><td>9.19</td><td>1.01</td><td>0.88</td><td>0.53</td></tr></table></body></html>

干旱事件强度的空间分布差异不明显。1个月尺度下，干旱强度最大值位于克山，最小值位于哈尔滨，差值为0.23;3个月尺度下，干旱强度最大值位于尚志，最小值在安达，差值为0.14;12个月尺度下，干旱强度最大值在尚志，最小值在克山，差值为0.21。

# 3结论

（1）SPI能较好的反应黑龙江省的干旱情况，时间尺度越小，SPI对于一次降水或短期降水的变化越显著。

(2）夏季与秋季干旱呈增强趋势，冬季和春季干旱呈减轻趋势，且秋季趋势要强于夏季，总体上，黑龙江省干旱呈弱增加趋势。

（3）黑龙江省20世纪60年代中后期至70年代末，干旱较为频繁，且干旱的持续时间长、干旱程度大、干旱强度大，80年代至90年代中期较为正常，90年代末及之后，干旱频率及其持续时间、程度、强度呈增加趋势。且时间尺度越小,持续时间、干旱程度以及干旱强度的值变化幅度越大。1974—1980年是黑龙江省干旱较为严重的阶段

（4）黑龙江省干旱事件的持续时间从西北向东南呈增加一减少趋势，黑龙江省中部的干旱事件持续时间最长。干旱程度及干旱强度在空间上分布的差异不明显。

# 参考文献(References)

[1］陈晓楠，段春青,刘昌明,等.基于两层土壤计算模式的农业干旱风险评估模型[J].农业工程学报，2009，25（9）：51-55.[CHEN Xiaonan,DUAN Chunqing,LIU Changming,et al.Model

of risk assessment for agricultural drought based on two-layer soil computing model[J].Transactions of the Chinese Society of Agricultural Engineering,2009,25（9）:51-55.]   
[2]周秀杰,那济海,潘华盛.黑龙江省夏季干旱气候特征及成因 分析[J].自然灾害学报,2011,20（5）:131-135.[ZHOU Xiujie,NA Jihai,PAN Huasheng. Climatic characteristics and cause of summer drought in Heilongjiang Province[J]. Journal of Natural Disasters,2011,20(5）:22 -28.]   
[3]孙滨峰,赵红,王效科.基于标准化降水蒸发指数(SPEI)的东 北干旱时空特征[J].生态环境学报,2015,24（1)：22－28. [SUN Binfeng,ZHAO Hong,WANG Xiaoke. Spatiotemporal characteristics of drought in Northeast China based on SPEI[J].Ecology and Environmental Sciences,2015,24（1）:22-28.]   
[4］赵茹欣,王会肖,杨会彩,等.基于标准降水指数的黑龙江省气 象干旱特征分析[J].节水灌溉,2017（12）：56-62.[ZHAO Ruxin,WANG Huixiao,YANG Huicai,et al. Meteorological drought characteristics in Heilongjiang Province based on standardized precipitation index[J].Water Saving Irrigation,2017(12）:56-62.]   
[5］马建勇,许吟隆,潘婕.基于 SPI与相对湿润度指数的1961— 2009 年东北地区5\~9月干旱趋势分析[J].气象与环境学报， 2012,28（3）:90-95.[MA Jianyong,XU Yinlong,PAN Jie. Drought tendency based on standardized precipitation index（SPI) and relative moisture index over Northeast China from May to September during 1961—2009[J].Journal of Meteorology and Environment,2012,28（3）:90-95.]   
[6］芦佳玉,延军平,李英杰.基于 SPEI及游程理论的云贵地区 1960—2014年干旱时空变化特征[J].浙江大学学报（理学 版）,2018,45（3）:363-372.[LU Jiayu,YANJunping,LI Yingjie.The temporal variation characteristics of drought in YunanGuizhou area during 196O to 2014 based on SPEI and run-length theory[J].Journal of Zhejiang University（Science Edition）, 2018,45(3) :996 -1007. ]   
[7］杨好周,梁忠民,胡义明,等.游程理论在云南省干旱重现期分 析中的应用[J].水电能源科学,2013,31（12）:8-12.[YANG Haozhou,LIANG Zhongmin,HU Yiming,et al.Application of runlength theory to drought return period analysis of Yunnan Province [J].Water Resources and Power,2013,31(12）:8 -12.]   
[8］邹文秀,韩晓增,江恒,等.东北黑土区降水特征及其对土壤水 分的影响[J].农业工程学报,2011,27（9）：196-202.[ZHOU Wenxiu,HAN Xiaozeng,JIANG Heng,et al.Characteristics of precipitation in black soil region and response of soil moisture dynamics in Northeast China[J]. Transactions of the CSAE,2011,27 (9):196 -202. ]   
[9]卢洪健,莫兴国,孟德娟,等.气候变化背景下东北地区气象干

旱的时空演变特征[J].地理科学，2015，35（8)：1051-1059. [LU Hongjian,MO Xingguo,MENG Dejuan,et al.Analyzing spatiotemporal patterns of meteorological drought and its responses to climate change across Northeast China[J].Scientia Geographica Sinica,2015,35(8):1051-1059.]

[10］张利利，周俊菊，张恒玮,等.基于SPI的石羊河流域气候干湿变 化及干旱事件的时空格局特征研究[J].生态学报,2017,37 (3）:996-10O7.[ZHANG Lili,ZHOU Junju,ZHANG Hengwei,et al.Temporal and spatial patterns of climate drought-wet and drought eventbased on standard precipitation index in Shiyang River Basin [J].Acta Ecologica Sinica,2017,37(3):996-1007.]

[11］袁文平，周广胜.标准化降水指标与 $Z$ 指数在我国应用的对比 分析［J].植物生态学报,2004,28(4）：523-529.[YUANWenping,ZHOU Guangsheng. Comparison between standardized precipitation index and $Z$ -indexin China[J].Chinese Journal ofPlant Ecology,2004,28(4) :523-529.]

[12］肖名忠，张强，陈晓宏.基于多变量概率分析的珠江流域干旱特征研究[J].地理学报,2012,67（1）:83-92.[XIAO Ming-zhong,ZHANGQiang,CHEN Xiaohong.Spatial-temporal patterns

of drought risk across the Pearl River Basin[J].Acta Geographica Sinica,2012,67(1):83-92.]   
[13］章大全，张璐，杨杰，等.近50年中国降水及温度变化在干旱 形成中的影响［J].物理学报，2010，59（1）：655－663. [ZHANG Daquan,ZHANGLu,YANG Jie,et al.The impact of temperature and precipitation variation on drought in China in last 50 years[J].Acta Physica Sinica,2010,59(1）:655-663.]   
[14]SEILER RA,HAYESM,BRESSAN L.Using the standardized precipitation index for flood risk monitoring[J].International Journal of Climatology,2002,22（11).   
[15］王学哲,孙才志,曹永强.基于修正 $Z$ 指数的黑龙江省旱涝时空 特性分析[J].水电能源科学,2017,35（10)：1-4.[WANGXuezhe,SUN Caizhi,CAO Yongqiang. Spatio-temporal characteristics of drought and flood in Heilongjiang Province based on the revised $Z$ index[J].Water Resources and Power,2017,35(10):1-4.]   
[16］韩晓君.黑龙江省旱涝特征分析［J].东北水利水电，1999， (1）:27-28.[HANG Xiaojun.Characteristics of drought and waterlogging in Heilongjiang Province[J].Water Resources&Hydropower of Northeast China,1999,（1）:27-28.]

# Spatial-temporal characteristics of drought in Heilongjiang Province based on standardized precipitation index

YU Jia-rui，AIPing²，YUAN Ding-bo’，XIONG Chuan-sheng (1College of Hydrology and Water Resources,Hohai University,Nanjing 210098,Jiangsu,China; 2College of Computer and Information,Hohai University,Nanjing 210o98,Jiangsu,China)

Abstract:Asone of the major grain-producing provinces,Heilongjiang Province,China is susceptible to suffring from drought risk.Drought happened much more frequently in recent years. Only afew studies focused on drought in the studyarea at present and mostof them paid more attention to the frequencyand degree ofdroughtthan the changes of the spatial-temporal characteristics of drought events.Thechanges of droughtand the spatial-temporal characteristicsof drought events in Heilongjiang Province were showed basedon daily precipitation data from1953 to 2015 by different scales of Standardized Precipitation Index $( S P I )$ ,combined with Run-length theory.The results showed that precipitation,compared with temperature,has been the main factor related to drought.The research indicated that the $S P I$ is an effective index for assessing drought conditions in Heilongjiang Province.The trend of summer drought and autumn drought was increased,while the trend of winter drought and spring drought was decreased.The summer $S P I$ and autumn $S P I$ were decreased with average rates of O.O29 and O.135 per ten years respectively, while the spring $S P I$ and winter $S P I$ were increased with average rates of O.O61 and O.O74 per ten years separately. Annual $S P I$ was decreased with an average rate of 0.044 per ten years.From the middle of 196Os to the late 1970s, drought in Heilongjiang Province happened frequently.The durationof drought events was long.The degree of drought was bigandthe intensityof drought was high.A consecutive drought period occurred in the years from 1974 to 1980.During this timeperiod,droughtshappened ata higher frequencyand fora longer duration.Thesituation was comparatively normal from198Os to the middleof199Os.The duration,the severityand the intensityof drought events showedan increasing trend from the late199Os.From the Northwest tothe Southeast,the durationof drought events was decreased afterthe first increase.This study could make contribution to monitoring and assessment of drought.And it could be used in guidelines of water resource management and agricultural production.

Key words:drought；Heilongjiang Province；SPI； spatial-temporal characteristic