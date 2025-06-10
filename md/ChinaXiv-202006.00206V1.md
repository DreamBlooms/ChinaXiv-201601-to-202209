# 基于小波分析的巴尔喀什湖水位变化特征及其影响因素

黄坤1,2,3，马龙1,2.3，吉力力·阿不都外力1,2,3（1.中国科学院新疆生态与地理研究所 荒漠与绿洲生态国家重点实验室,新疆 乌鲁木齐830011;2.中国科学院中亚生态与环境研究中心,新疆 乌鲁木齐830011；3.中国科学院大学,北京 100049)

摘要：根据巴尔喀什湖年平均湖水位、伊犁河中下游径流以及流域气象数据,采用线性倾向率、小波时频分析等方法,研究了巴尔喀什湖1880—2016年平均水位变化特征及规律,针对湖泊水量平衡分析得出伊犁河下游径流量是控制湖水位变化的关键因子,通过交叉小波进一步分析了影响湖水位变化的各种气象因素。结果表明： $\textcircled{1}$ 巴尔喀什湖水位在2002 年左右发生了突变,并存在以 $8 3 \mathrm { ~ a ~ }$ 为中心尺度的主周期,该尺度下水位变化的平均周期为54a左右,经历了3个丰枯转换时期，今后将逐步进入枯水期。 $\textcircled{2}$ 交叉小波分析表明，自然状态下降水是影响湖水位变化的主要原因;径流与气温的共振周期相位在20 世纪80 年代末发生了由负向正的转变,指示气温升高对湖水位的综合影响表现为由蒸发损耗转变为融水补给增加。 $\textcircled{3}$ 大气环流因子通过控制降水，从而影响研究区内入湖径流和湖水位变化,北大西洋涛动(NAO)相较南方涛动(SOI)与径流的关系更为紧密,对湖水位变化的影响较大。

关键词：巴尔喀什湖；水位；径流；气候变化；小波分析；中亚

中亚干旱区受西风环流、北冰洋高纬和印度洋暖湿气流的交错作用，极端气候事件频发、生态系统脆弱，成为全球变化的敏感区域。近百年来，全球气候系统显著变暖，北半球平均气温在过去的130a上升了 $0 . 8 5 \mathrm { ~ } ^ { \circ } \mathrm { C } ^ { [ 1 ] }$ ,中亚干旱区变暖幅度是北半球的2 倍多[2-3]。干旱区湖泊变化是流域气候变化和人类活动的综合体现，近几十年来，受气候和人类活动的影响，中亚地区湖泊面积萎缩、水体咸化趋势加剧。湖泊萎缩以及由此带来的一系列生态环境问题已严重制约了中亚国家的社会经济发展。

巴尔喀什湖是亚洲中部干旱区最大的湖泊生态系统之一[4],其湖泊水位的变化是流域内水量平衡的重要体现[5],在20 世纪中后期湖水位迅速降低,直到90年代以后水位出现回升，湖泊水位的变化引起了国内外相关学者的关注[6-8]。Stone[9]研究认为，流域内水资源利用将导致巴尔喀什湖在50a内缩小成数个小湖泊，面积不超过 $5 ~ 0 0 0 ~ \mathrm { k m } ^ { 2 }$ 。针对巴尔喀什湖现状及未来可能面临的问题，国内外学者基于器测数据对巴尔喀什湖水量平衡[4,8]以及水位/面积变化[5,10-13]等进行了一系列研究,邓铭江等[5]研究认为,卡普恰盖水库的兴建和伊犁河中下游水资源开发利用，导致了近年来入湖径流减少、湖泊水位下降。王姣妍等[4研究表明,气候变化是湖泊水位动态变化的主导因素，而人类活动是湖泊水量变化的强化因素，对于自然状态下出现的湖泊水位大幅涨落的原因还有待深入研究。总体而言，干旱区湖泊水环境变化的响应过程研究的欠缺，导致湖泊水环境未来变化的不确定性显著增强，给科学制定湖泊流域管理与保护对策带来显著影响。因此，本研究试图从基础层面通过突变检验、小波分析阐释巴尔喀什湖水位变化特征，利用交叉小波并结合入湖径流进一步研究气温、降水及大气环流指标等因素对湖泊水环境变化的影响因素，以期为巴尔喀什湖水环境保护及其应对全球变化提供决策支持。

# 1 研究区概况

巴尔喀什湖位于哈萨克斯坦东南部（图1），

![](images/18e76150a6d2766b223660a2ed104d9d03d5058e0b353dd9eda70b888c46b673.jpg)  
图1巴尔喀什湖流域水文站点及其1880—2016 年水位变化  
Fig.1Distribution of main hydrologic station,and the changes of water level inLake Balkhash in1880-2016

2014 年湖泊面积约 $1 7 \ 0 0 0 \ \mathrm { k m } ^ { 2 [ 1 1 ] }$ 。巴尔喀什湖被乌曾阿拉尔半岛分为东西两个大致相等的湖区，西半部广而浅，水深不超过 $1 1 \mathrm { ~ m ~ }$ ,东半部窄而深,平均水深 $2 5 \mathrm { ~ m ~ }$ 。流入巴尔喀什湖的主要河流有伊犁河、卡拉塔尔河、列普西河、阿亚古兹河等。由于近$80 \%$ 入湖径流的伊犁河经伊犁河三角洲注入西湖[10],导致西湖水体矿化度明显低于东湖。巴尔喀什湖流域面积 $4 . 1 3 \times 1 0 ^ { 5 } ~ \mathrm { k m } ^ { 2 }$ ,其中 $14 \%$ 位于中国境内,流域属大陆性气候,年平均气温 $3 \sim 1 0 ~ \mathrm { { ^ { \circ } C } }$ ，降水量在 $1 3 0 \sim 4 5 0 ~ \mathrm { m m }$ ,且在空间上存在明显差异,其中东南部天山地区受海拔影响最为湿润[14]。湖区气候干旱,年均降水仅有 $1 5 0 \ \mathrm { m m }$ ，而蒸发量达到$1 \ 0 0 0 \ \mathrm { m m } , 7$ 月平均气温 $3 0 \ \mathcal { C } \ , 1$ 月平均气温-14C,年平均气温6℃[15]

# 2资料与方法

# 2.1 数据来源

气温、降水数据使用英国东英吉利亚大学气象格点数据集cru_ts_4.O1（http://data.ceda.ac.uk/badc/cru/data/cru_ts/cru_ts_4.01/）,时间为1931—2016年，在ArcGIS中根据巴尔喀什湖流域矢量图裁剪，得到流域范围内空间分辨率为 $0 . 5 ^ { \circ } \times 0 . 5 ^ { \circ }$ 的网格化数据，使用R语言逐一计算流域内各年份格点的平均值，得到气温和降水的时间序列。1880—2016年平均湖水水位引自文献［8，12］，1931—2000年伊犁河上游4站平均、卡上 $1 7 1 ~ \mathrm { k m }$ 站、卡普恰盖水库出库站、乌斯热尔玛站以及卡拉塔尔河的托宾斯基站年均径流数据引自文献5」。北大西洋涛动指数(NAO)来自美国国家海洋和大气气候预测中心（http://www.cpc.ncep.noaa.gov/data/teledoc/nao.shtml），南方涛动指数（SOI)来自澳大利亚气象局（http://www.bom.gov.au/climate/current/soi2.shtml）。

# 2.2 研究方法

2.2.1线性倾向率、滑动平均法本文运用线性倾向率、滑动平均对流域气象因子进行分析，研究全球变化背景下巴尔喀什湖流域气候要素时间上的变化趋势及特点。

2.2.2连续小波变换采用连续小波变换（CWT)[16]来揭示水位时间序列中的周期时频变化特征，预估其未来发展趋势。本文选取复Morlet小波函数作为基函数进行小波变换[17-18]：

$$
\Psi _ { 0 } ( t ) = \pi ^ { - 1 / 4 } \mathrm { e } ^ { i \omega _ { 0 } t } \mathrm { e } ^ { - t ^ { 2 } / 2 }
$$

式中： $\psi ( t )$ 为小波函数； $i$ 表示虚数； $\mathbf { e }$ 为自然对数； $\mathbf { \Phi } _ { t }$   
为时间； $\omega _ { 0 }$ 为无量纲频率。

对于给定时间序列和Morlet小波，其连续小波变换为：

$$
W _ { \mathrm { f } } ( a , b ) = \frac { 1 } { \sqrt { a } } \int _ { - \infty } ^ { + \infty } \mathrm { f } ( t ) \varPsi \biggl ( \frac { t - b } { a } \biggr ) \mathrm { d } t
$$

式中： $\boldsymbol { a }$ 为时间尺度，反映时间序列的周期长度； $b$ 为时间变化; $W _ { f } ( a , b )$ 为小波变换系数。湖水位小波系数实部的等值线能够反映不同时间尺度下湖水位的周期变化以及在时间域上的分布[19],实部系数为正表示水位为上升阶段，负数则表示水位下降，等值线越密集表明信号越强。

2.2.3交叉小波变换交叉小波功率谱(XWT)可以从多时间尺度显示两个时间序列在时频域中高能量区的相关关系。对于两个时间序列 $x ( t )$ 和 $y ( t )$ 之间交叉小波功率谱如下[20]：

$$
W _ { X Y } ( a , \tau ) = C _ { \scriptscriptstyle X } ( a , \tau ) C _ { \scriptscriptstyle Y } ^ { * } ( a , \tau )
$$

式中： $W _ { X Y } ( a , \tau )$ 为交叉小波功率谱； $C _ { X } ( a , \tau )$ 为尺度伸缩参数 $\mathbf { \alpha } _ { a }$ 和时间平移参数 $\boldsymbol { \tau }$ 下的小波变换系数； $C _ { Y } ^ { * } \left( a , \tau \right)$ 为序列 $y ( t )$ 小波变换系数的复共轭。

而小波凝聚谱（WTC）更侧重于两时间序列在低能量区的相关性[19],交叉小波凝聚谱定义如下[20]：

$$
R ^ { 2 } ( a , \tau ) = \frac { \mid S [ a ^ { - 1 } W _ { X Y } ( a , \tau ) ] \mid ^ { 2 } } { S [ a ^ { - 1 } W _ { X } ( a , \tau ) ] S [ a ^ { - 1 } W _ { Y } ( a , \tau ) ] }
$$

式中： $s$ 为平滑算子。

在交叉小波功率谱与交叉小波凝聚谱的图中，黑色实线边界效应影响椎，粗黑线表示通过显著性水平为0.05的红噪声检验，箭头表示两个时间序列的相位关系， $$ 表示二者为同相位， $$ 表示为反相位或后者领先前者 $1 8 0 ^ { \circ }$ ，」和↑分别表示后者领先$9 0 ^ { \circ } , 2 7 0 ^ { \circ [ 1 9 , 2 1 ] }$ U

# 3结果与讨论

# 3.1 巴尔喀什湖湖水位变化的周期性

巴尔喀什湖水位始测于1931年，1880—1930年为延长资料[4]，由图1可知,1880—2016 年巴尔喀什湖水位经历了频繁的波动，具有明显的丰枯交替变化特征。3个枯水年分别发生在1884年、1946年和1987年，在人类活动较弱的19世纪及20世纪上半叶湖泊依然出现过极低水位，说明巴尔喀什湖水位变化易受自然气候影响。

采用Morlet小波对巴尔喀什湖1880—2016 年年均湖泊水位变化进行连续小波变换(图2)可以看出，百年来巴尔喀什湖水位的变化具有多时间尺度的频率结构，主要表现为年代际的变化，以80a为中心尺度的周期信号贯穿了整个研究期，等值密集表明信号较强。20世纪70年代之前存在以 $4 5 \sim$ 50a尺度为主的周期振荡，在时域中表现为逐渐增大的趋势，70年代后的消失表明，湖水位受外部环

![](images/d7a8114681022a575af3d19aab2e67f24bf4da0eeee82d441094ca6ffbf1b466.jpg)  
图21880—2016 年巴尔喀什湖年均湖水水位小波分析

Fig.2Isolineoftherealpartof Morlet waveletcoeffcients,waveletvarianceandthewaveletcoeffcientcurves forthelake

level ofLake Balkhash in 1880-2016境影响发生突变，指示受到该时期卡普恰盖水库蓄水等人类活动影响，从而引起入湖径流减少。小波方差能够反映水位时间序列的波动能量随尺度的分布情况，可用来确定水位演化过程中存在的主周期[17],巴尔喀什湖年均水位小波方差图（图 2b)显示，在 $8 3 \mathrm { ~ a ~ } . 4 7$ a存在极值,83a左右周期对小波方差贡献较大，为湖水位变化的主周期。小波系数过程线可以反映数据序列在该尺度下的波动信息[22]，在83a时间尺度上，水位变化的平均周期为54a左右,约经历了3个丰枯转换时期，相对偏高的时期包括1895—1933 年、1952—1978 年、2005—2016 年,而在1880—1894 年、1934—1951年、1979—2004 年湖水位处于相对偏低时期[21]。而在47a时间尺度上，水位变化的平均周期为32a左右，约经历了4个丰枯转换时期。湖水变化的主周期显示，现阶段湖水位处于丰水期的中心时段，根据其水位丰枯交替规律，巴尔喀什湖水位在此后将逐步进入枯水期。

![](images/08464c41f45d4ffe1395226f889ec1132dc306f11dbc0e971b8b9a26de27bc84.jpg)  
注：SOI为南方涛动指数，NAO为北大西洋涛动指数。  
图31931—2016年巴尔喀什湖流域气象因子年际变化及趋势  
Fig.3Inter-annul variationand tendency of meteorological factors inLake Balkhash basin from 1931 to 2016

# 3.2 气候变化特征

巴尔喀什湖流域年平均气温自1931年以来呈上升趋势（图3），气温变化率为0.259 $\mathrm { { ^ \circ C } }$ ·（10a）-1，高于同时期全球平均陆地表层气温变化速率 $\left[ 0 . 1 6 ^ { \mathrm { ~ \circ ~ } } \mathrm { C } \cdot \left( 1 0 \mathrm { a } \right) ^ { \mathrm { ~ - 1 ~ } } \right] ^ { \left[ 5 \right] }$ 以及新疆地表气温变化率 $\left[ 0 . 2 2 9 \mathrm { ~ \% ~ } \cdot \mathrm { ~ ( ~ 1 0 a ) ~ } ^ { - 1 } \right]$ ,5a的滑动平均显示出，20 世纪30一80 年代气温呈波动上升，至80 年代中后期气温上升的速率加快。流域年平均降水量以$5 . 2 3 3 \ \mathrm { \ m m } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { a ) ~ } ^ { - 1 }$ 的速率缓慢增加,变化范围基本集中在 $2 0 0 \sim 3 5 0 ~ \mathrm { m m }$ ,在1944年和1974年出现极小值，1958年出现极大值，到90年代以后降水量快速增加。从 $5 \mathrm { ~ a ~ }$ 滑动平均可以看出，在50年代中期以前降水变化波动较小（其标准差为 $\mathrm { s d } = 4 2 . 2 \$ ，而后变化的波动性明显增大( $\mathrm { \ s d } = 4 8 . 7 1$ )，与前人利用巴尔喀什湖流域站点气象数据分析结果基本一致[15,23],流域整体气候向暖湿化转变。NAO 和 SOI的线性倾向率分别为 $0 . 0 2 2 \mathrm { ~ a ~ } ^ { - 1 }$ $0 . 5 2 3 \mathrm { ~ a ~ } ^ { - 1 }$ 。

# 3.3水位变化的影响因素

湖泊水位变化是其水量平衡的直接结果，巴尔喀什湖水量收入包括入湖径流和湖面降水，支出项主要为湖面蒸发。研究显示[8],自1930 年以来湖泊水量平衡的支出项湖面蒸发基本稳定，但主要收项入湖径流受到流域气候以及人类活动影响而变化剧烈，而这其中以伊犁河（占入湖径流的 $78 \%$ )与卡拉塔尔河（占入湖径流的 $1 5 \%$ )注入水量最大（表1)[10],因此,这二者的入湖水量在一定程度上对湖水位有决定性的影响。

表1伊犁河各段径流与卡拉塔尔河径流的相关系数[10]  
Tab.1Correlation coefficient for runoff of Ili River and Karatal River   

<html><body><table><tr><td></td><td>乌斯热尔玛站</td><td>卡普恰盖站</td><td>卡上171 km</td><td>萨雷托加站</td><td>上游四站综合</td></tr><tr><td>相关系数</td><td>0.737</td><td>0.831</td><td>0.876</td><td>0.866</td><td>0.923</td></tr><tr><td>P值</td><td>6.64×10-10</td><td>4.50 ×10 -14</td><td>3.73 ×10-17</td><td>2.18 ×10-16</td><td>1.93 ×10 -19</td></tr></table></body></html>

![](images/fba1bc648885aa48376180bfe9519d078a8f3a5a6b802aa18af053048d6a9e14.jpg)  
图4巴尔喀什湖主要入湖河流水文站点径流量与湖水位变化对比  
Fig.4Comparison of runoff variation forthe hydrologic station of main inflow rivers and water level of LakeBalkhasl

利用相关系数来研究上述两条河流不同水文站点径流量的关系，得到卡拉塔尔河年均径流量与伊犁河卡普恰盖上游多个水文站点5 径流的相关系数均在0.85以上( $P < 0 . 0 1 \rangle$ ，表明二者对环境变化响应的一致性较好。从图4可以看出，1970年以前伊犁河3个水文站点径流与湖水位变化趋势较为相近，之后卡普恰盖水库建成蓄水等人类活动影响，造成水库上下游径流差异显著，湖水位出现迅速下降。综上所述，考虑以卡普恰盖水库上游径流代表自然状态下的入湖径流，并通过交叉小波进一步分析其与气温、降水等区域气象因素之间的关系。

3.3.1区域气象因素对连续小波变换后的系数进行双时间序列的交叉小波变换，得到气象因素与伊犁河径流的交叉小波功率谱和小波凝聚谱[24]（图5）。从气温与径流的交叉小波功率谱(图5a)中可以看到，二者存在3个显著的共振周期，其中1956—1963年和1964—1969年的 $5 \sim 6 \mathrm { ~ a } \lrcorner 2$ a共振周期显示为反相位，而1981—1987年的 $8 \sim 1 1$ a周期为同相位。交叉小波凝聚谱(图5c)中存在3个显著的负相关关系，分别在20世纪40年代之前、

1955—1962年、90年代以后，而40年代和80年代，存在两个在统计上不显著但正相关的区域，正反相位的转变说明巴尔喀什湖流域气温对径流量的影响方式可能出现变化。一般来说,对于存在雪冰融水补给的河流，气温的升高能够加快雪冰的消融，提供河流更多的补给；但另一方面，也会加大流域的蒸发损耗，从而减少径流。1960年前后的负相关，气温经历了先下降再上升，巴尔喀什湖水位的变化与径流量几乎同步上升再下降，气温升高的综合结果以蒸发为主。80年代后的 $8 \sim 1 1$ a尺度共振周期内，气温与径流均表现为正相关，说明气温的快速升高[变化率为 $0 . 3 3 8 \mathrm { ~ \textdegree ~ { ~ } ~ } \cdot \left( 1 0 \mathrm { { a } ~ } \right) ^ { - 1 } \mathrm { { J } }$ 在短期内加剧了雪冰消融，河流补给的增多掩盖了由增温引起的蒸发损耗，并造成了湖水位的上涨。

交叉小波功率谱(图5b)显示，降水量和流域径流有5个显著的共振周期，全部为同相位，其中两个能量较高的共振周期包括5\~7a（1954—1963年）、6\~11a(1971—1995年），其中 $6 \sim 1 1$ a的正相关在频域上表现为由低频向高频过渡。此外，还有6a左右 $\phantom { - } \cdot 1 \sim 3 \ a \phantom { - } _ { \cdot } 3$ a左右的共振周期，但能量相对较弱，且通过置信检验的区域面积较小，为间歇性准周期震荡[25]。小波凝聚谱中(图5d)显示的通过 $9 5 \%$ （204号的红噪声检验的区域占据了影响椎的大部[24],表明二者在低能量区的相关程度大于高能量区， $6 \sim 1 2$ a的主周期近乎穿越影响椎的时域，在1939一1945年、1965—1980年间分别存在 $6 \sim 8 \mathrm { ~ a ~ } , 1 \sim 5$ a的正相关，相关系数在0.9以上，表明降水相较于气温对径流变化起主导作用，进而影响湖水位变化

![](images/f800f161b3a9c2480b4f97c1714c4d0b6233998671c9d381d8a4ded1f7c91240.jpg)  
图5径流与气温和降水的交叉小波图  
Fig.5Cross wavelet transform between annual temperature,annual average precipitation and runoff

3.3.2大气环流因素大气环流异常可能通过影响中亚地区水汽输送，从而改变径流的主要控制因素降水。亚洲中部干旱区降水的水汽主要来源于西风环流,戴新刚等[26研究认为，在NAO的极端负位相年，西风增强，从欧洲南部向中亚的水汽输送增强,中亚地区降水增加。此外,相关研究[27]发现,当厄尔尼诺事件发生时，强烈的西南暖湿气流带来了大量的水分，穿过阿拉伯半岛进一步向北移动，导致亚洲中部降水增加。

NAO与径流的交叉小波功率谱显示，在高能区（图6a)存在4个显著的共振周期，在5～6a（1936—1944年）1\~2a（1985—1989年)及7\~11a(1972一1988年)尺度上二者表现为负相关，而在1990—1998年4\~6a的显著共振周期，两者为正相关。二者的共振周期在1990年左右发生突变，表明伊犁河进入丰水周期。在低能区（图6c)共有3个共振周期，1955—2000 年 $7 \sim 1 4$ a共振周期显示相关系数达到0.9以上，表明伊犁河径流在此期间受NAO影响明显，二者相位差为 $9 0 ^ { \circ }$ ，径流滞后NAO约 $2 \sim 4 \mathrm { ~ a ~ }$ ，自1974年起的自然枯水期正对应了NAO从1971年由负相位转为正相位，进一步加速了水库蓄水引起的湖水位下降。

SOI与径流的小波功率谱显示（图6b），在1953—1962 年、1987—1994 年存在4\~7a 的共振周期，SOI分别领先径流 $1 2 0 ^ { \circ } , 9 0 ^ { \circ }$ ,1967—1974年$3 \sim 4 \mathrm { ~ a ~ }$ 的周期中二者为负相关,小波凝聚谱(图6d)中通过显著性检验的共振周期范围较小,但20世纪90年代出现了 $1 \sim 2 \mathrm { ~ a } \mathrm { , } 7$ a $\cdot ^ { 1 6 }$ a的3个显著共振周期，径流的变化可能与这一时期的厄尔尼诺事件有关。对1980—2000 年卡普恰盖站径流量和南方涛动指数的相关分析显示，相关系数达到0.43（ $P <$ 0.05），表明二者之间具有较强的相关性。此外，伊犁河径流对1986—1987年、1991—1994年、1997—1998 年3个厄尔尼诺年均有良好的响应且呈增加趋势（图3），相应地巴尔喀什湖水位在90年代前后呈波动性上升。

分析可知，巴尔喀什湖流域在人类活动较弱的20世纪70年代以前，湖水位主要受流域的气候条件影响，特别是流域的降水状况决定了湖水位的升降，气温升高在不同时期则存在正负效应的转换。

![](images/299dcd3341b0859c18d07b4471f865af681a272823d0a6773bfce463a9ffd34f.jpg)  
图6径流与NAO 和SOI的交叉小波图  
Fig.6Cross wavelet transform between annual NAO,annual SOI and runoff

70年代后的湖水位迅速下降除了由于正处于降水偏少的枯水期外，更受到卡普恰盖水库蓄水和哈萨克斯坦境内灌区耕地扩张[28]等人类活动影响。到80年代中后期气温在短时间内急剧上升，雪冰对这种信号发生响应，融水补给增多，使得伊犁河径流以及巴尔喀什湖水位出现上涨趋势。宏观上，受到西风环流与印度洋暖湿气流影响的巴尔喀什湖流域，NAO和SOI均与其降水有关，从而能够影响径流以及湖水位变化，NAO与径流的相关性更强，而 SOI反映的厄尔尼诺事件则与1987年后水位间歇性回升存在一定联系。

处于亚洲中部干旱区的伊塞克湖[17]、博斯腾湖[29]艾比湖[30]等湖泊，自20 世纪50—60 年代受流域人口快速增加，农业耗水剧增等影响，湖面萎缩水位迅速下降,20世纪末人类活动强度减弱，加上区域降水增加使水位上涨，总体来说湖水位变化与人类活动关系密切。相比于上述中亚湖泊，巴尔喀什湖水位变化受人类活动影响时间较短、程度较小，且在自然状态下具有明显的周期性，这些不同尺度的周期可能来自于大气环流以及太阳活动的准周期变化[31]。此外,巴尔喀什湖存在雪冰融水补给,流域内气温从20世纪80年代末转暖，给湖水位变化带来了不确定性。Propastin[1o]认为气温快速上升近二十多年来，虽然降水依旧是维持湖泊水位的重要来源，但同时雪冰融水补给的不断增多使其与降水几乎已同等重要。研究显示[32],作为巴尔喀什湖重要补给来源天山积雪和冰川，近50年来其面积缩小了 $1 1 . 5 \%$ ,其中伊犁河流域的冰川面积减少最多，储量亏损占天山冰川总亏损的 $20 \%$ 。因此,尽管巴尔喀什湖水位在自然状态下就存在较大的周期性变化，但20世纪90年代起的水位回升与伊犁河上游积雪覆盖及冰川平衡关系紧密，这意味着巴尔喀什湖水位未来可能受到全球变暖背景下天山冰川进一步退缩而出现下降。

# 4结论

本文基于小波时频分析法分析了巴尔喀什湖水位变化特征，探讨了湖泊水量平衡的关键要素以及气象因子的变化特征，并采用交叉小波对湖水位变化影响因素进行了研究，结论如下：

（1）近百年来，巴尔喀什湖水位波动频繁。湖水位存在以83a和47a为中心尺度的周期，其中

83a周期对小波方差贡献最大，为主周期，在该尺度下目前湖水位正处于相对较高的时期，此后将逐步进入枯水期。

（2）气温与径流在20世纪80年代的显著共振周期相位由负转正，指示增温加快导致雪冰融水补给的增加超过蒸发引起的损耗，加之，同时期降水量的增加使湖水位的迅速回升。总体上降水是自然状态下影响径流和湖水位变化的主要原因。

（3）大气环流因子通过控制降水从而影响研究区内入湖径流和湖水位变化。其中，NAO对湖水位变化起主导作用,并存在2～4a的滞后，而 SOI反映的厄尔尼诺事件则与1987年后湖水位回升联系密切。

# 参考文献（References）:

[1］沈永平，王国亚.IPCC第一工作组第五次评估报告对全球气候 变化认知的最新科学要点[J].冰川冻土,2013,35（5）：1068-   
1076.［Shen Yongping,Wang Guoya. Key finding and assessment results of IPCC WGI Fifth Assessment Report[J].Journal of Glaciology and Geocryology,2013,35（5） :1068-1076.] [2］姚俊强,刘志辉,杨青,等.近130 年来中亚干旱区典型流域气 温变化及其影响因子[J].地理学报,2014,69(3）：291-302. [Yao Junqiang,Liu Zhihui,Yang Qing,et al. Temperature variability and its possible causes in the typical basins of the arid Central Asia in recent 130 years[J].Acta Geographica Sinica,2014,69 (3):291-302.] [3]Chen F,Wang J,Jin L,et al.Rapid warming in mid-latitude central Asia for the past 1OO years[J].Frontiers of Earth Science in China,2009,3(1) :42 -50. [4]王姣妍,龙爱华,邓铭江,等.巴尔喀什湖分湖水平衡及其影响 与优化保护研究［J].冰川冻土,2011,33（6）：1353－1362. [Wang Jiaoyan,Long Aihua,Deng Mingjiang,etal.Water balances of east and west Lake Balkhash and their optimization management [J].Journal of Glaciology and Geocryology,2011,33（6）:1353 -   
1362.] [5］邓铭江,王志杰,王姣妍.巴尔喀什湖生态水位演变分析及调 控对策[J].水利学报,2011,42（4）:403－413.[Deng Ming jiang,Wang Zhijie,Wang Jiaoyan.Analysis of Balkhash Lake ecological water level evolvement and its regulation strategy[J]. Journal of Hydraulic Engineering,2011,42(4）:403-413.] [6］杨川德.巴尔喀什湖水位变化及其原因［J].干旱区地理,   
1993,16（1）:36-42.[Yang Chuande.Water level of Balkhash Lake and its reason for change[J].Arid Land Geography,1993,16 (1) :36 -42.] [7]Panyushkina IP,Meko D M,Macklin M G,et al.Runoff variations inLake Balkhash Basin,Central Asia,1779-2O15,inferred from

tree rings[J].Climate Dynamics,2018,51(7-8）:3161-3177.

[8］龙爱华,邓铭江,谢蕾,等.巴尔喀什湖水量平衡研究[J].冰川 冻土,2011,33（6）:1341-1352.[Long Aihua,Deng Mingjiang, Xie Lei,etal.A study of the water balance of Lake Balkhash[J]. Journal of Glaciology and Geocryology,2011,33（6）:1341- 1352.]

[9]Stone R.For China and Kazakhstan,no meeting of the minds on water[J].Science,2012,337(6093）:405 -407.   
[10]Propastin P.Paterns of Lake Balkhash water level changes and their climatic correlates during 1992- 2010 period[J].Lakes & Reservoirs Research & Management,2012,17(3):161-169.   
[11］高彦华,王洪亮,周旭,等.巴尔喀什湖近30 余年动态变化遥 感监测与分析［J].环境与可持续发展,2016,41（1)：102- 106.[Gao Yanhua,Wang Hongliang,Zhou Xu,et al. Remote sensing monitoring and analyses of the dynamic change of Balkhash Lake in the last 3O years[J].Environment and Sustainable Development,2016,41(1):102 -106.]   
[12］郭利丹,夏自强,王志坚.咸海和巴尔喀什湖水文变化与环境 效应对比[J].水科学进展,2011,22（6)：764-770.［Guo Lidan,Xia Ziqiang,Wang Zhijian. Comparisons of hydrological variations and environmental effects between Aral Sea and Lake Balkhash[J].Advances in Water Science,2011,22（6）:764- 770.]   
[13]Myrzakhmetov A,Dostayzh,Alimkulov S,et al.Level regime of Balkhash Lake as the indicator of the state of the environmental ecosystems of the region[J].International Journal of Advanced Research in Science,Engineering and Technology,2017,4（9） :4554 -4563.   
[14］杨川德.亚洲中部湖泊近期变化［M].北京:气象出版社, 1993:15-25.[Yang Chuande.Recent Changes of Lakes in Central Asia[M].Benjing:China Meteorological Press,1993:15- 25.]   
[15]Guo L,Xia Z. Temperature and precipitation long-term trends and variations in the Ii-Balkhash Basin[J].Theoretical & Applied Climatology,2014,115(1-2):219 -229.   
[16］孙卫国,程炳岩,杨沈斌,等.区域气候变化对华东地区水稻产 量的影响[J].中国农业气象,2011,32（2）:227-234.[Sun Weiguo,Cheng Bingyan,Yang Shenbin,et al.Impact of the regional climate variation on rice yield in East China[J].Chinese Journal of Agrometeorology,2011,32（2）:227 -234.]   
[17］米热古力·艾尼瓦尔,海米提·依米提,麦麦提吐尔逊·艾则 孜,等.基于小波分析的伊塞克湖水位变化特征[J].水土保持 研究,2014,21（1）:168-172.[Mihrigul Anwar,Hamid Yimit, Mamatursun Eziz,et al.Water level variations of Issyk-Kul Lake based on wavelet analysis[J].Research of Soil and Water Conservation,2014,21(1) :168-172.]   
[18］王涛,霍彦峰,罗艳,等.近300 a来天山中西部降水与太阳活 动的小波分析［J].干旱区研究,2016,33（4）：708－717. [Wang Tao,Huo Yanfeng,Luo Yan,et al.Precipitation and sunspots in the Central-West Tianshan Mountains in recent 3OO years

[J].Arid Zone Research,2016,33(4):708 -717.]

[19］侯迎,郑芳,邵议.基于交叉小波的多尺度气候变化及其对径 流的影响[J].水资源研究,2016,5(6）:564-572.[Hou Ying, Zheng Fang,Shao Yi.The multi-timescale climate change and its impact on runoff based on cross-wavelet transformation[J]. Journal of Water Resources Research,2016,5(6):564-572.]   
[20］刘友存,刘志方,郝永红,等.基于交叉小波的天山乌鲁木齐河 出山径流多尺度特征研究[J].冰川冻土,2013,35(6)：1564- 1572.[Liu Youcun,Liu Zhifang,Hao Yonghong,et al.Multi-time scale characteristics of the runoff in the up stream of Urumchi River,Tianshan Mountains,based on cross-wavelet transformation[J]. Journal of Glaciology and Geocryology,2013,35（6）:1564- 1572. ]   
[21］王大伟,师庆东,董弟文,等.新疆克里雅河径流量变化的气候 响应[J].干旱区研究,2018,35（6）:1271-1279.[Wang Dawei,Shi Qingdong,Dong Diwen,et al.Response of runoff volume change to climatein the Keriya Riverin Xinjiang[J].Arid Zone Research,2018,35(6):1271-1279.]   
[22］谭娇,丁建丽,张钧泳,等.1961-2014 年新疆北部地区气温时 空变化特征[J].干旱区研究,2018,35(5）:1181-1191.[Tan Jiao,Ding Jianli,Zhang Junyong,et al. Spatiotemporal variation of temperature in North Xinjiang during the period of 1961- 2014 [J].Arid Zone Research,2018,35(5）:1181-1191.]   
[23］郭利丹，夏自强,李捷,等.巴尔喀什湖流域气候变化特征分析 [J].河海大学学报（自然科学版）,2008,36（3）：316-321. [Guo Lidan,Xia Ziqiang,Li Jie,et al. Characteristics of climatic change in the Balkhash Lake Basin[J].Journal of Hohai University（Natural Sciences Edition）,2008,36(3）:316-321.]   
[24］胡胜,邱海军,宋进喜,等.气候变化对秦岭北坡径流过程的影 响机制研究—以灞河流域为例[J].干旱区地理,2017,40 (5）:46 -57.[Hu Sheng,Qiu Haijun,Song Jinxi,et al.Influencing mechanisms of climate change on runoff process in the north slope of Qinling Mountains:A case of the Bahe River Basin[J]. Arid Land Geography,2017,40(5） :46-57.]

[25］刘志方，刘友存，郝永红，等.黑河出山径流过程与气象要素多 尺度交叉小波分析[J].干旱区地理，2014，37（6)：1137- 1146.[Liu Zhifang,Liu Youcun,Hao Yonghong,et al. Multi-time scale cross-wavelet transformation between runoff and climate factors in the upstream of Heihe River[J].Arid Land Geography, 2014,37(6):1137-1146.]

[26］戴新刚，汪萍，张凯静.近60年新疆降水趋势与波动机制分析 [J].物理学报,2013,62（12）:527-537.[Dai Xingang,Wang Ping,Zhang Kaijing.A study on precipitation trend and fluctuation mechanism in Northwestern China over the past 6O years[J].Acta Physica Sinica,2013,62(12):527-537.]

[27]Mariotti,Annarita.How ENSO impacts precipitation in SouthwestCentral Asia[J].Geophysical Research Letters,2OO7,34（16）：1-5.

[28]Kezer K,Matsuyama H.Decrease of river runoff in the Lake Balkhash basin in Central Asia[J].Hydrological Processes,2O10,20 (6):1407 -1423.

[29］伊丽努尔·阿力甫江，海米提·依米提，麦麦提吐尔逊·艾则孜，等.1958—2012年博斯腾湖水位变化驱动力［J].中国沙漠,2015,35(1）:240-247.[Ilnur Ghalip,Hamid Yimit,Mamat-tursun Rusuli,et al.The driving forces of the Bosten Lake waterlevel variations in 1958-2012[J].Journal of Desert Research,2015,35(1) :240-247.]

[30］吴敬禄,林琳.新疆艾比湖湖面波动特征及其原因[J].海洋与 第四纪地质,2004,24（1）：11-19.［WuJinglun，LinLin.Characteristics and reasons of fluctuation of lake sueface of the Aibi Lake,Xinjiang autonomous region[J]. Journal of Lake Sciences, 2004,24(1):11-19.]

[31]Pérez-Peraza JA,YLI.Highlights in Helioclimatology:About Possible Analysis of Solar Activity Influence on Terrestrial Processes [M].Boston:Elsivier,2012.

[32］王圣杰,张明军,李忠勤,等.近50年来中国天山冰川面积变化 对气候的响应［J].地理学报,2011,66（1)：38-46.［Wang Shengjie,Zhang Mingjun,Li Zhongqin,et al.Response of glacier area variation to climate change in chinese tianshan mountains in the past 50 years[J].Acta Geographica Sinica,2011,66(1) :38-46.]

# A study of the water level variation of Lake Balkhash:Its influencing factors based on wavelet analysis

HUANGKun，， (1.StateKeyLaboratoryofDesertandOasisEcology,Xinjiang InstituteofEcologyand Geography,Chinese AcademyofSciences, Urumqi 830011,Xinjiang,China;   
2.ResearchCenterforEcologyndEnvironmentofCentralAsia,hinesecademyofSiencesUrumqi8ol1,Xinjanghna;   
3.University of Chinese Academy of Sciences,Beijing 10oo49,China)

Abstract：Basedon the annualaveragelakelevel of the Lake Balkhash,runoffof Ii River,and the meteorological data in the basin,we analyzed the characteristics and regularity of the average water level change of Lake Balkhash from 188O to 2O16 by using the wavelet time-frequency analysis method.Water balance data showed that therunoffinthe lowerreaches ofthe Ili River is akeyfactor controllng variation in thelakelevel.Cros-waveletanalysis was applied to further analyze the relationship between the lake level changes and the main meteorological factors.The results suggested that the main cycle for83 ais thecentral scale,with an average period of lake level change for $5 4 \mathrm { ~ a ~ }$ .The lake level has experienced three transitions in water abundance and dryness since l88O,and it will graduallyenterthe next dryseason in the future.The cros-wavelet analysisrevealed that precipitation is the main driver of lake level change under natural conditions.Inaddition,the transition of theresonance cycle phase between temperature and runoff inthe late 198Os indicates that the increasing meltwater supply due to rising temperatureresults in therecoveryoflake level,instead of anegative efect of evaporation los.The variation in runoff and lakelevelcan be influenced by atmospheric circulation in the region through itscontrol on precipitation.The relationshipof cross-wavelet analysis between NAOand runoffis more closely related than SOI,which plays a more important role in lake level changes.

Key words:Lake Balkhash ；water level； runoff； climate change； wavelet analysis； Central Asia