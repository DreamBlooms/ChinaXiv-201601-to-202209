# 京津冀地区AOD时空变化及影响因子的地理探测

景悦}²，孙艳玲，高爽，陈莉，潘隆，马含}(1天津师范大学地理与环境科学学院,天津300387；2 西安地球环境创新研究院,陕西西安710061)

摘要：基于MODIS $3 \ \mathrm { k m } \ A O D$ 遥感数据，利用空间自相关模型及地理探测器对2010—2016年京津冀地区 $A O D$ 的时空变化特征及其影响因子进行探测。结果表明：(1）2010—2016年京津冀地区年平均A0D值为0.83，其中天津市年均AOD值为研究区最高，河北省次之，北京市最低。研究区及各分区A0D的7a变化趋势大体一致，呈现先下降后上升再小幅波动的状态。（2）空间自相关分析表明京津冀地区 $A O D$ 空间分布呈现显著正相关。局部高高聚集区主要集中在北京市东南部、天津市南部及河北省的中南部，低低聚集区集中分布在西北部山区。研究区高低聚集区面积均呈减小趋势，不显著区呈扩大态势。（3）地理探测器结果表明不同区域的主导影响因子不同，北京市首要影响因子为NDVI,其次为人口密度，且二者交互作用明显。天津市主导因子为风速，人口密度、第二产业生产总值等人为因子的作用力也较大，风速与其交互作用较强。河北省主导因子为人口密度,GDP与第二产业生产总值等的作用力次之，整体交互作用偏弱。通过地理探测器解析京津冀地区AOD空间分异的影响机理，其结果对我国大气污染治理具有重要意义。

关键词：AOD；时空变化；地理探测器；影响因子；京津冀地区

大气气溶胶是指大量悬浮在空气中直径小于$1 0 0 ~ { \mu \mathrm { m } }$ 的液体或固体微粒，它不仅使能见度下降，也会对人体健康造成损害，是大气污染的重要组成部分[1]。气溶胶光学厚度简称 AOD（Aerosol Opti-calDepth)是衡量气溶胶的重要因子，可以用来表征大气浑浊度或气溶胶的总含量，有效反映区域空气污染程度[2]。一般来讲,AOD 值越小,空气中气溶胶含量越低，表明大气越清洁；反之，AOD值越大，空气中气溶胶含量越高，表明大气越混浊。目前AOD探测主要有地基遥感与卫星遥感两种手段，地面设备能够提供气溶胶浓度的持续变化特征，但不能得到良好的空间覆盖信息，难以反映其变化趋势的空间分布,而卫星遥感恰好弥补了这项不足[3]近年来,MODISAOD产品在大气污染研究领域应用最为广泛，其标准level2级AOD产品空间分辨率为$1 0 ~ \mathrm { k m }$ ,已被国内外大量学者证明具有显著的应用价值[4-6]。2014 年末美国国家航空航天局发布了更高分辨率的 $3 \ \mathrm { k m } \ A O D$ 产品，该产品2/3的数据都在允许误差范围内，可以被用于全球范围的气溶胶变化研究[7]。张西雅等[8]、孙晓雷等[9]也证明其在京津冀、新疆阿克苏地区具有较好的适用性，可以为区域尺度气溶胶研究提供更精确的数据支持。

关于京津冀地区AOD时空分布特征及其影响机理已经有了不少研究。张西雅等[8]对京津冀地区气溶胶时空分布状况进行研究，揭示了夜间灯光数据与AOD具有高度一致性。景悦等["0]对京津冀地区AOD及其影响因子的相关分析表明京津冀地区AOD与第二产业生产总值呈明显正相关，与风速呈现明显负相关。刘状等[1]对中国北方地区长时期的气溶胶时空变化特征进行分析，表明人口密度及地形分布是影响AOD空间分布的重要原因。关于气溶胶影响因子的研究，通常采用相关分析法、多元线性回归等方法得出AOD与其影响因子之间的线性关系[12-15]。而地理探测器工具对变量无线性假设，可以探测变量与影响因子之间的所有关系，它是基于空间分异理论，根据要素的空间异质性探测因子解释力，还可进一步寻找双变量的解释能力，其在解释变量驱动机理方面具有不可比拟的优势。目前已被广泛应用于自然、经济各个领域[16-18],其中，也有学者将其运用到空气质量AQI指数的风险因子分析及 $\mathrm { P M } _ { 2 . 5 }$ 驱动因子分析[19-20]。但在 A0D 影响因子识别方面研究报道较少，仅见郭春颖利用地理探测器对长江三角洲地区 $A O D$ 的风险因子进行分析[21]。因此,本文利用高精度气溶胶产品 MOD04_$3 \mathrm { ~ k ~ }$ 数据,结合空间自相关模型与地理探测器工具科学探测和诊断了京津冀地区气溶胶时空规律和动力机制,有效的验证了地理探测器在京津冀地区气溶胶驱动机理方面的适应性，也对区域大气污染特征认识与治理具有重要科学意义。

# 数据来源与研究方法

# 1.1 数据来源及预处理

（1）AOD：TerraMOD04_3k数据产品是从美国国家航空航天局的戈达德宇宙飞行中心（https：//ladsweb.nascom.nasa.gov/）网站上下载得到,时间序列为2010年1月～2016年12月，空间分辨率为$3 ~ \mathrm { k m }$ ,时间分辨率为1d,波段为 $5 5 0 \ \mathrm { n m }$ 的气溶胶level2 级产品,除去11d的缺失数据,共得到2547d数据。AOD数据利用ENVI的IDL 编程调用MCTK工具对其进行投影转换批处理，再进行图像拼接、掩膜提取，在剔除无效值及0值之后生成月平均数据，继而得到年平均数据。

（2）影响因子：分为自然因子和人为因子两种类型。其中，自然因子包括降水量、相对湿度、风速、归一化植被指数(NDVI)。气象数据来自中国气象数据共享网（http：/data.cma.cn/），选择克里金插值方法对风速、降水量、相对湿度数据进行处理[22] CNDVI数据选用MOD13A3产品数据，其空间分辨率为 $1 ~ \mathrm { k m }$ ,时间分辨率为15d,先对其进行投影转换、拼接、掩膜提取等预处理，进一步生成年平均数据，最后重采样生成 $3 ~ \mathrm { k m }$ 分辨率的栅格数据。人为因子包括国民生产总值（GDP）、第二产业生产总值和人口密度。数据来自于北京市、天津市、河北省2010一2017年统计年鉴，部分缺失数据从各省统计局官网获得，统计得到各省及各市县的社会经济数据并将其转化成矢量面数据。

京津冀地区AOD值及各影响因子的7a平均值空间分布如图1所示，通过地图判别可以得出AOD及各影响因子空间分布的相似性与差异性，为后续进行地理探测的结果给予一定的验证。

# 1.2 研究方法

1.2.1空间自相关分析地理学第一定律表明任何事物都相关，只是相近的事物关联更紧密，这为空间自相关分析提供了理论基础[23]。空间自相关通常分为全局空间自相关和局部空间自相关。反映全局空间自相关的重要指标是莫兰指数（Moran's $I$ ），Moran's $I { > } 0$ 表示空间正相关性,其值越大,空间相关性越明显，Moran's $I < 0$ 表示空间负相关性，其值越小,空间差异越大，否则，Moran's $I = 0$ ,空间呈随机性。全局空间自相关公式如下所示：

$$
I = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } W _ { i j } \left( x _ { i } - { \overline { { x } } } \right) \left( x _ { j } - { \overline { { x } } } \right) } { \displaystyle \left[ { \frac { 1 } { n } } \sum _ { i = 1 } ^ { n } \left( x _ { i } - { \overline { { x } } } \right) ^ { 2 } \right] ^ { 2 } \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } W _ { i j } } }
$$

式中： $n$ 为单元的数量，为 $A O D$ 栅格数据转化成3$\mathrm { k m } \times 3 \ \mathrm { k m }$ 的矢量面数据对应的数量; $x _ { i } \ 、 x _ { j }$ 为单元$i _ { \surd } j$ 的 $A O D$ 的年均值; $\mathbf { \Pi } _ { x } ^ { - }$ 为所有单元的 $A O D$ 平均值;$\textstyle \mathcal { W } _ { i j }$ 为单元 $i _ { \surd } j$ 的空间权重矩阵，在ArcGIS中用原始方式生成默认的空间权重矩阵。另外，显著性水平通过 $Z$ 得分来评定，其计算公式为：

$$
Z ( I ) = { \frac { \left[ I - E ( I ) \right] } { \sqrt { V a r ( I ) } } }
$$

$$
E ( I ) = \frac { - 1 } { \left( n - 1 \right) }
$$

$$
\mathit { V a r } ( I ) = E ( I ^ { 2 } ) - E ( I ) ^ { 2 }
$$

式中： $Z ( I )$ 用来衡量Moran's $I$ 的显著性水平； $E ( I )$ 为Moran's $I$ 的数学期望; $V a r ( I )$ 为Moran's $I$ 的方差。

局部自相关用于检测要素的高值或低值的局部空间聚集性，一般分为4种局部空间相关关系：高高聚集表示该单元与其周围单元的AOD值均相对较高，低低聚集指该单元与周围区域的 $A O D$ 值相对较低，高低聚集指高值中心被低值所包围，低高聚集指低值中心被高值所包围。其公式如下所示：

$$
I _ { i } = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } W _ { i j } \left( x _ { i } - { \overline { { x } } } \right) \left( x _ { j } - { \overline { { x } } } \right) } { \displaystyle \left[ { \frac { 1 } { n } } \sum _ { i = 1 } ^ { n } \left( x - { \overline { { x } } } \right) ^ { 2 } \right] ^ { 2 } } }
$$

式中： $I _ { i }$ 为局部自相关指数。

114°E 116E 118E 114°E 116E 118E 114°E 116°E 118E  
N (a) N N N (b) N N N (c) NA 2 A 2承德 承德 承德W ? 2张家口 张家口 张家口  
NO 北京廊坊 唐山秦皇岛 No0V NoOV 1 北京廊坊 唐山秦皇岛 N0 No0V 北京廊坊 唐山秦皇岛 NOv天津 天津 天津保定 廊坊 保定 廊坊 保定 廊坊  
N.88 沧州 N.88 N88 沧州 N88 N88 沧州 N88石家庄 石家庄 石家庄邢台 衡水 平均GDP值／亿元 邢台 衡水 元 邢台 衡水 平均人口密度  
N.98 050100 邯郸 200km 高：19 487.80 低：1080.66 3 N N98 050100 邯郸 200km 高：6882.91 低：433.60 98 N N 3 050100 邯郸 200km 高：1276 低：95 N98F □ F 上 L114°E 116°E 118°E 114°E 116°E 118E 114°E 116°E 118E114°E 116E 118E 114°E 116E 118E 114°E 116E 118E  
NZ (d) N N N (e) N 2 (f) N NA 2 二 A承德 承德 承德? √  
NO 张家口 A 北京 廊坊 唐山 NoOV 张家口 A 北京 廊坊 唐山 NoOV 张家口 人 北京 廊坊 2 唐山 秦皇岛 NOv天津 天津 天津保定 廊坊 保定 廊坊 保定 廊坊  
N88 沧州 N88 N.88 沧州 N.88 N88 沧州 N88石家庄 衡水 平均降雨 石家庄 衡水 平均相对湿 石家庄 衡水 平均风速值邢台 量值/mm 邢台 度值/% 邢台 /m·s-1高：75.72 高：67.80 高：4.60  
N98 邯郸 N N98 邯郸 N N 邯郸 N.98050100 200km 低：7.31 3 050100 200km 低：11.28 98 98 050100 200km 低：0.33Lu1I LII114°E 116E 118°E 114°E 116°E 118E 114°E 116°E 118E114°E 116E 118E 114°E 116E 118ENZ i N N (h) N N2 A承德 承德?NO 张家口 A 北京 廊坊 唐山 秦皇岛 No0V N0V 5 张家口 人 北京 廊坊唐山 秦皇岛 NoOV天津 天津保定 廊坊 保定 廊坊N88 沧州 N.88 N88 沧州 N88石家庄 石家庄衡水 平均NDVI 衡水 平均AOD值邢台 邢台高：0.67 高：1.05N.98 050100 200km 低：-0.06 N.98 N.98 50100 1 200km 低：0.66 N.98LI114°E 116E 118°E 114°E 116°E 118°E

1.2.2地理探测器地理探测器是探测要素的空间分异性并揭示其背后驱动力的统计工具，它是基于空间分异理论，将自变量与不同离散分类的自变量放在同一空间尺度进行探测，若某个自变量对因变量有重要影响，那么二者的空间分布就具有一定相似性[24]。通过计算 $q$ 统计量来度量要素的空间异质性以及探测因子解释力，还可分析两变量真正的交互作用,进一步寻找双变量的解释能力。 $q$ 值值域范围在 $0 \sim 1$ 之间，表示自变量 $X$ 解释了 $1 0 0 \times$ $q \%$ 的 $Y$ ，值越大解释能力就越强。

因子探测的评价指标是 $q$ 统计量，其公式如下：

$$
q \ = \ 1 \ - \ \frac { \displaystyle \sum _ { i = 1 } ^ { n } N _ { i } \sigma _ { i } ^ { 2 } } { \displaystyle N \sigma ^ { 2 } } 
$$

式中： $i = 1 , 2 , \cdots , n$ 是指因子 $X$ 的分类; $N _ { i }$ 为层 $\mathbf { \chi } _ { i }$ 对应的单元数； $N$ 为研究区总单元数目； $\sigma _ { i } ^ { 2 }$ 和 $\sigma ^ { 2 }$ 分别为层 $i$ 与全区 $Y$ 值的方差。 $Y$ 代表 $A O D$ ,驱动因子 $X$ 包括降雨量、相对湿度、风速 $, N D V I \setminus G D P , G D P .$ 人口密度、第二产业生产总值，用 $3 \ \mathrm { k m } \times 3 \ \mathrm { k m }$ 空间分辨率的中心点共计24223个网格点将变量 $Y$ 与变量 $X$ 匹配起来进行探测。为了使数据在空间分布上满足分类区域具有显著差异性，根据自然断点法、几何间隔法以及百分位数法对影响因子进行分类处理，利用地理探测器计算每一种分类的 $q$ 值，最终选择解释力最大的分类方法及组数作为该因子最佳分类方法[24]

交互探测是评估 $X _ { 1 }$ 与 $X _ { 2 }$ 因子相互作用是否会对Y解释力产生影响,通过分别比较各单因子的 $q$ 值与两因子叠加后的 $q$ 值，可以判断两因子交互作用的强弱。

# 2结果与分析

# 2. 1 京津冀地区AOD的时间变化特征

通过对2010—2016年的A0D年平均数据进行时间序列分析得到京津冀地区、北京市、天津市、河北省近7aAOD的变化趋势（图2）。结果表明2010—2016年研究区整体的年均A0D值围绕0.83波动，7a间AOD值呈现为先下降后上升再趋于稳定的状态，2010年A0D值最高为0.88，2012年AOD值下降到0.79，之后稳定为0.83。北京市的7a平均AOD值为0.79，各年份AOD值均低于研究区的整体水平，变化趋势与研究区总体一致。天津市7a平均AOD值为0.90，整体AOD值均高于研究区的平均水平，呈现“W”型变化趋势,2010年AOD值最高为0.94,2012 年出现第一个谷值0.87,2013 年达到峰值0.90，随后2014年达到第二个谷值0.88，之后2a又呈上升趋势。河北省7a平均AOD值为0.80,各年的AOD值均小于研究区整体水平，AOD值在2010年达到最高为0.84，2012年下降到0.76，之后在2013年有个小峰值0.80，随后呈现逐年缓慢下降的趋势。综合上述结果可以看出，各地区AOD的年变化趋势与研究区整体大致相同，均为先下降后上升再小幅波动的态势。天津市的AOD值为研究区内最高，北京市最低,河北省的AOD值属于中间水平。

![](images/b772e00c53affb22d3a82f6ed6541eb10d2a7f5bc5bf100eca095cb372fef184.jpg)  
图22010—2016年京津冀地区A0D的时间变化特征Fig.2Characteristics of the temporal variation of $A O D$ in Beijing-Tianjin-Hebei region in 201O—2016

# 2.2 京津冀地区AOD的空间变化特征

全局自相关分析结果表明（表1），研究时段内京津冀地区AOD的全局Moran's $I$ 指数均稳定居高，其中北京市最高，均在0.98以上，其次京津冀及河北省地区为 $0 . 9 6 ( \pm 0 . 0 3 )$ ，天津市相对较低为$0 . 9 5 ( \ \pm 0 . 0 1 )$ ，指示各地区AOD的空间分布呈现显著的正相关，同时也表明京津冀地区AOD呈现集中连片的状况且区域之间传输较为明显。

通过对2010—2016年京津冀地区AOD做局部自相关分析，可明确研究区AOD的局部聚集与分散情况，科学解释AOD的空间变化特征。根据结果将显著局部自相关的区域划分成3种类型，高高聚集型、低低聚集型及不显著区域。结合图3与图4可知，各地区AOD的局部聚集特征及变化趋势不尽相同。北京市的低低聚集型面积占比最大，平均占北京市总面积的 $4 5 . 5 6 \%$ ，主要分布在西北部的燕山山区且有进一步扩大的趋势。高高聚集型的面积次之，占到 $2 9 . 1 4 \%$ ,集中分布在城6区及大兴区和通

表1 2010—2016年京津冀地区 $A O D$ 全局自相关分析  
Tab.1 Global spatial autocorrelation analysis of AOD in Beijing-Tianjin-Hebei region in 2010—2016   

<html><body><table><tr><td rowspan="2">年份</td><td colspan="3">全局自相关(Moran'sI)</td></tr><tr><td>京津冀地区 北京市</td><td>天津市</td><td>河北省</td></tr><tr><td>2010</td><td>0.93 0.98</td><td>0.95</td><td>0.93</td></tr><tr><td>2011</td><td>0.97 0.98</td><td>0.94</td><td>0.97</td></tr><tr><td>2012</td><td>0.95 0.99</td><td>0.94</td><td>0.95</td></tr><tr><td>2013</td><td>0.96 0.99</td><td>0.96</td><td>0.96</td></tr><tr><td>2014</td><td>0.95 0.99</td><td>0.95</td><td>0.96</td></tr><tr><td>2015</td><td>0.96 0.99</td><td>0.96</td><td>0.95</td></tr><tr><td>2016</td><td>0.98 0.99</td><td>0.94</td><td>0.98</td></tr></table></body></html>

114°E 116E 118E 114°E 116°E 118E 114°E 116°E 118E  
N 2010年 N N 2011年 N 4 2012年 N N  
No0 北京市 No0 NO 北京市 NO NO 北京市 N0好天津市 天津市 天津市  
N88 河北省 N88 N88 河北省 N.88 N88 河北省 N88?图例 图例 图例  
N.98 0.50100200km N98 N.98 [0 50100200km N.98 N98 0 50100200km N.98上 E EE114°E 116E 118°E 114°E 116E 118°E 114°E 116°E 118°E114°E 116°E 118E 114E 116°E 118E 114°E 116°E 118E  
N 2013年 2 2014年 N N 2015年 N  
NOV 北京市 N0 NO 北京市 No0V NoOV 北京市 NO天津市 天津市 天津市  
N88 河北省 N88 N88 河北省 N88 N.88 河北省 N88图例 图例 图例■ 不显著区域 不显著区域 不显著区域  
N.98 [0 50100200km 高高聚集区 ■低低聚集区 N98 N.98 [0 50100200km 高高聚集区 低低聚集区 N.98 N.98 0 50100 200 km 高高聚集区 ■ 低低聚集区 N.98F FE FE114°E 116°E 118E 114°E 116E 118E 114°E 116E 118E114°E 116E 118EN 2016年 N NNoO 北京市 NOV囍天津市N88 河北省 N88 图32010-2016年京津地区AOD局部图例 Fig.3Local spatial autocorrelation analysis of AOD不显著区域N.98 050100_200km 高集区 N98 inBeijing-Tianjin-Hebei regionin 2O1O—2016114°F 116E 118F

州区，呈现轻微减小的态势。不显著区域面积占比最小为 $2 5 . 2 9 \%$ ,主要位于高低值过度地带，呈减小的趋势。天津市的低低聚集型平均占到 $1 . 3 1 \%$ ，分布区域极少但呈现增加的态势。高高聚集型平均占天津市总面积的 $6 4 . 0 1 \%$ ,分布在武清一宁河区的以南地区，呈下降趋势。不显著区域占比为$3 4 . 6 7 \%$ ，主要集中在北部山区且无明显变化趋势。河北省的低低聚集型平均占比为 $3 5 . 1 4 \%$ ，分布在太行一燕山山地地区，有逐渐减小的趋势。中部及东南部的平原地区分布有 $2 7 . 5 1 \%$ 的高高聚集型及

$3 7 . 4 5 \%$ 的不显著区域,其中,不显著区域有进一步增加的可能，而高高聚集型呈减小的态势。总体而言，京津冀地区的高值聚集区、低值聚集区及不显著区域各占总面积的大约1/3，空间上大致呈现东南高西北低状况。北京市东南部、天津市南部、河北省中南部始终是三大高高聚集区，且短时间内并不会发生改变，不过河北省南部的高值片状区向城市中心回拢、北京市、天津市高值片区的轻微减少可能导致高值聚集区有下降的趋势。河北省及北京市的西北部低低聚集区的减少可能造成京津冀地区低低聚集区面积的下降。另外，河北省南部的部分高值聚集区将转化为不显著区会进一步增加京津冀地区的不显著区域面积。

![](images/803ce97eb4a578ab6de77125685a51a7db8935b06afcf7fd73fcfe1df4f1d055.jpg)  
图42010—2016年京津冀地区局部聚集区面积变化趋势  
Fig.4Area change trend of local gathering area in Beijing-Tianjin-Hebei region in 2O1O—2016

# 2.3京津冀地区AOD 的影响因子分析

AOD的空间变化受气候、地形、人类活动等多种因素的综合影响。一般来讲，相对湿度增加会使气溶胶粒子吸湿增长，AOD增大;静稳天气的环境促进污染物聚集，大风天气会加快扩散；降水日数较多利于颗粒物的吸收与沉降，AOD随之减小；NDVI反映地表植被覆盖情况，植被覆盖好对调控、吸收大气污染物具有明显的效果；GDP反映一个地区经济发展程度，第二产业生产总值反映工业聚集情况，这些都与AOD呈现明显的正相关；人口密度反映地区人口活动程度，人口越多，表明该地区人们生产生活频率越快，生活的废气及汽车尾气排放量就越大。因此，研究从自然和人为两方面选取7个具有代表性的影响因子，探测其对京津冀地区AOD的影响机理。利用地理探测器工具首先对不同地区各影响因子贡献率进行分析（图5），再通过因子探测与交互探测得出京津冀地区不同年份的主导驱动因子及不同区域的主导驱动因子（表2）。

2.3.1影响因子贡献率分析从京津冀地区各影响因子的贡献率可以看出（图5）,2010—2016 年各因子对AOD平均作用强弱的排名依次为：人口密度$( 2 6 . 4 1 \%$ ） $>$ 第二产业生产总值 $( 2 2 . 3 8 \%$ ）>GDP$( 2 1 . 8 2 \%$ ） $>$ 相对湿度 $\left( 1 2 . 7 1 \% \right) > N D V I ( 7 . 6 6 \% )$ $>$ 降水量 $( 5 . 7 1 \% ) >$ 风速 $( 3 . 3 1 \%$ ）,3个人为因子的贡献率都较大，总和占到 $7 0 . 6 1 \%$ ，说明人为因子是该区域AOD的主要驱动力。从时间序列来看，各影响因子在不同年份对 $A O D$ 的贡献率也略有不同，其中，GDP与人口密度在各年的贡献率基本变化不大。第二产业生产总值在2011年及2014年贡献率占比略微下降到 $1 8 . ~ 8 5 \%$ ，其余年份近似为$2 3 . 7 8 \%$ 。降水量对 $A O D$ 的贡献率在2011年、2012年较高为 $1 1 . 4 8 \%$ ，其余年份都影响力较低，为$3 . 4 0 \%$ 。相对湿度贡献率的变化呈现倒“U”型趋势，总体平均贡献率为 $1 2 . 7 1 \%$ ,最高贡献率出现在2013年为 $1 8 . 7 2 \%$ 。 $N D V I$ 的变化情况与降水量呈相反态势，NDVI的贡献率恰好在2011和2012年降到最低 $4 . 5 0 \%$ ，其余5a平均贡献率为 $8 . 9 1 \%$ 。风速对AOD贡献率的变化趋势与降水量相似，整体呈现单峰分布，峰值出现在2010年，贡献率为 $6 . 2 2 \%$ 。

北京市驱动因子的探测结果显示（图5），各因子平均贡献率强弱依次为： $N D V I ( 2 1 . 3 2 \%$ ） $>$ 人口密度 $\left( 1 7 . 7 2 \% \right) > \mathrm { G D P } \left( 1 5 . 7 6 \% \right)$ $>$ 第二产业生产总值（ $1 4 . 3 9 \%$ ） $>$ 风速( $1 3 . 4 3 \%$ ） $>$ 相对湿度（ $1 0 . 0 5 \%$ ） $>$ 降水量 $( 7 . 3 3 \%$ )，前三者贡献率总和占比为 $5 4 . 8 0 \%$ ，说明北京市的NDVI与其AOD变化规律较一致，且人口高密度区及经济快速发展区的地理分布与AOD高值区具有高度的空间耦合。从不同年份各因子贡献率的变化中看出，NDVI、人口密度、GDP相对比较稳定。第二产业生产总值的贡献率7a间出现小幅震荡，其中2012年、2014年、2015年出现了较低贡献率为 $1 2 . 6 5 \% ( \ \pm 0 . 7 6 )$ ，其余年份贡献率的均值达到 $1 5 . 6 9 \%$ 。降水量的贡献率在2010—2015 年均稳定在 $8 . 3 3 \%$ ,到2016年急剧下降到 $1 . 2 5 \%$ 。相对湿度的贡献率在2010—2011 年较低，为 $5 . 0 1 \%$ ,在 2012 年达到一个峰值,贡献率高达 $1 6 . ~ 8 8 \%$ ，但随后又下降并稳定在$1 0 . 8 7 \%$ （ $\pm 2 . 5 4 \rangle$ ）。风速对AOD的贡献率在2013年有一个谷值为 $9 . 3 1 \%$ ，其余年份的贡献率约为$1 4 . 7 2 \%$ 。

天津市因子探测的结果具有自身的独特性（图5），7a平均的各因子贡献率排名依次为风速$( 2 1 . 2 4 \%$ ） $>$ 人口密度（19. $0 5 \%$ ） $>$ NDVI$\left( 1 6 . 7 3 \% \right) > \mathrm { G D P } ( 1 3 . 5 6 \%$ ） $>$ 第二产业生产总值（ $1 2 . 8 8 \%$ ） $>$ 降水量 $( 9 . 1 6 \%$ ） $>$ 相对湿度( $( 7 . 3 8 \%$ ）。说明天津市人口高密度区及强风速地区的 $A O D$ 值较高，而北部人口稀疏、山区植被覆盖较好恰好与AOD低值区的范围近似。从时间序列来看，风速、NDVI、人口密度3个因子的贡献率变化不大，较为稳定。GDP的贡献率在7a间有小幅震荡，2010 年及2012年贡献率偏低为 $1 0 . 4 9 \%$ ,其余年份平均贡献率基本一致为 $1 4 . 7 9 \%$ 。第二产业生产总值的贡献率呈U型分布，在2013年、2014年有一个低谷值为 $8 . 6 6 \%$ ,其他年份平均为 $1 4 . 5 7 \%$ 。降水量的变化趋势波动频繁，2011年与2015年降水量的贡献率仅为 $1 . 5 7 \big ( \ \pm 0 . 4 8 \big )$ ，几乎没有影响，2016年贡献力轻微上升到 $3 . 9 9 \%$ ，其余年份贡献率较高稳定在$1 4 . 2 5 \%$ 。相对湿度对天津市AOD的影响总体呈现逐渐上升的过程，2016年贡献率达到最高为$1 1 . 8 8 \%$ 0

![](images/36eb6ee206a0b0f1e044ebeded3bc96d24af017521236cee67e43e0979444797.jpg)  
图52010—2016 年京津冀地区 $A O D$ 的各影响因子贡献率  
Fig.5Contribution rate of influence factors of $A O D$ in Beijing-Tianjin-Hebei region in 201O—2016

河北省单因子贡献率的分析中（图5），各因子7a平均的影响力排序依次为人口密度 $( 2 5 . 3 8 \%$ ）$> \mathrm { G D P } ( 2 3 . 4 7 \%$ ） $>$ 第二产业生产总值 $( 2 1 . 7 5 \%$ ）$>$ 相对湿度( $( 1 3 . 5 7 \%$ ） $>$ 降水量 $( 6 . 5 6 \% ) > N D V I$ $( 4 . 7 7 \% ) >$ 风速 $( 4 . 5 0 \%$ )。河北省的因子探测结果也显示人为因素三者总体贡献率达到 $7 0 . 0 6 \%$ ，说明经济发展活动及人类生活排放是影响河北省AOD的主要决定因素。不同年份各影响因子的变化也各不相同，人口密度与GDP两个人为因子的逐年变化最为稳定，而第二产业生产总值的贡献率在2012 年出现一个低谷值为 $1 5 . 6 1 \%$ ,其余年份均较高为 $2 2 . 7 7 \%$ 。降水量贡献率的变化趋势呈先上升后下降的过程，2012年达到峰值为 $1 1 . 9 9 \%$ ,2016年降到最低值为 $2 . 7 8 \%$ 。相对湿度的呈波动上升的趋势,2016年达到贡献率的最高值 $1 7 . 8 1 \%$ 0NDVI的变化趋势呈现轻微震荡，2010年与2015 年NDVI的贡献率较高为 $7 . 0 6 ( \pm 0 . 3 5 )$ ,其余年份的贡献率都较低，平均为 $3 . 8 6 \%$ 。风速的变化趋势与降水量一致，不过，其整体平均贡献率都较低，最高才达到 $7 . 4 3 \%$ 。

河北省因子探测结果与京津冀整体结果类似，影响因子的逐年变化规律也大致相同。而北京市、天津市各因子贡献率确大有不同，证明了全局因子探测与局部因子探测的重要性，同时也启示区域大气污染治理应该因地制宜、找准各区问题的关键。

2.3.2主导因子分析京津冀地区AOD的成因复杂、驱动因子多样，准确把握主导因子是解决区域气溶胶污染的关键。将地理探测器分别运用于京津冀地区、北京市、天津市、河北省4个区域，探测各个地区逐年的主导因子及交互主导因子（表2），结果表明,最大 $\scriptstyle q$ 值对应的因子随着不同年份、不同地区会产生一定的变化，其中不同地区之间的主导因子差异巨大。就单一主导因子而言，京津冀地区2010年、2011年、2014—2016年主导因子为人口密度，2012 年和2013年主导因子为第二产业生产总值，7a间单一主导因子的平均 $q$ 值为0.39，其中2010年、2011年、2016年最大 $q$ 值接近0.5，说明该时期

# 表22010—2016年京津冀地区主导因子及交互主导因子影响强度(q值)表

Tab.2Influence of dominant factors and interacting dominant factors in Beijing-Tianjin-Hebei region in 2010—2016(q value)   

<html><body><table><tr><td>地区</td><td>年份</td><td>主导因子</td><td>q值</td><td>主导交互因子</td><td>q值</td></tr><tr><td>京津冀</td><td>2010</td><td>人口密度</td><td>0.45</td><td>人口密度NDVI</td><td>0.62</td></tr><tr><td>地区</td><td>2011</td><td>人口密度</td><td>0.48</td><td>人口密度风速</td><td>0.56</td></tr><tr><td></td><td>2012</td><td>第二产业生 产总值</td><td>0.37</td><td>第二产业生产总值 降水量</td><td>0.46</td></tr><tr><td></td><td>2013</td><td>第二产业生 产总值</td><td>0.32</td><td>第二产业生产总值 相对湿度</td><td>0.43</td></tr><tr><td></td><td>2014</td><td>人口密度</td><td>0.31</td><td>人口密度风速</td><td>0.44</td></tr><tr><td></td><td>2015</td><td>人口密度</td><td>0.32</td><td>人口密度风速</td><td>0.42</td></tr><tr><td></td><td>2016</td><td>人口密度</td><td>0.50</td><td>人口密度相对湿度</td><td>0.63</td></tr><tr><td>北京市 2010</td><td></td><td>NDVI</td><td>0.63</td><td>NDVIN风速</td><td>0.78</td></tr><tr><td></td><td>2011</td><td>NDVI</td><td>0.65</td><td>NDVIN人口密度</td><td>0.84</td></tr><tr><td></td><td>2012</td><td>NDVI</td><td>0.64</td><td>NDVIN人口密度</td><td>0.83</td></tr><tr><td></td><td>2013</td><td>NDVI</td><td>0.67</td><td>NDVIN人口密度</td><td>0.82</td></tr><tr><td></td><td>2014</td><td>NDVI</td><td>0.67</td><td>NDVIN人口密度</td><td>0.85</td></tr><tr><td></td><td>2015</td><td>NDVI</td><td>0.64</td><td>NDVIN人口密度</td><td>0.84</td></tr><tr><td></td><td>2016</td><td>NDVI</td><td>0.72</td><td>NDVIN人口密度</td><td>0.85</td></tr><tr><td>天津市 2010</td><td></td><td>风速</td><td>0.40</td><td>风速人口密度</td><td>0.46</td></tr><tr><td></td><td>2011</td><td>风速</td><td>0.39</td><td>风速相对湿度</td><td>0.50</td></tr><tr><td></td><td>2012</td><td>风速</td><td>0.46</td><td>风速人口密度</td><td>0.54</td></tr><tr><td></td><td>2013</td><td>风速</td><td>0.45</td><td>风速相对湿度</td><td>0.68</td></tr><tr><td></td><td>2014</td><td>风速</td><td>0.35</td><td>风速相对湿度</td><td>0.52</td></tr><tr><td></td><td>2015</td><td>风速</td><td>0.36</td><td>风速n第二产业生产 总值</td><td>0.51</td></tr><tr><td></td><td>2016</td><td>人口密度</td><td>0.51</td><td>风速人口密度</td><td>0.69</td></tr><tr><td>河北省 2010</td><td></td><td>第二产业生 产总值</td><td>0.21</td><td>第二产业生产总值 NDVI</td><td>0.26</td></tr><tr><td></td><td>2011</td><td>人口密度</td><td>0.48</td><td>人口密度降水量</td><td>0.54</td></tr><tr><td></td><td>2012</td><td>人口密度</td><td>0.35</td><td>人口密度n风速</td><td>0.43</td></tr><tr><td></td><td>2013</td><td>人口密度</td><td>0.30</td><td>人口密度相对湿度</td><td>0.40</td></tr><tr><td></td><td>2014</td><td>人口密度</td><td>0.30</td><td>人口密度降水量</td><td>0.44</td></tr><tr><td></td><td>2015</td><td>人口密度</td><td>0.32</td><td>人口密度n风速</td><td>0.40</td></tr><tr><td></td><td>2016</td><td>人口密度</td><td>0.52</td><td>人口密度相对湿度</td><td>0.64</td></tr></table></body></html>

对应的单一主导因子可以解释了 $5 0 \%$ 的 $A O D$ 态势。北京市的单一主导因子7a均为 $N D V I$ ,平均 $q$ 值高达0.66，各年份 $q$ 值均大于0.6,最高 $q$ 值为2016年的0.72，表明2016年的NDVI分布状况可以反映$7 2 \%$ 的 $A O D$ 空间规律。天津市 2010—2015 年均为风速作用强度最大，且其 $q$ 值变化不大，稳定在$0 . 4 0 \big ( \ \pm 0 . 0 6 \big )$ 上下，2016年主导因子转变为人口密度， $q$ 值达到0.51，可以看出该年份人为活动影响已经超过了风速对AOD的作用强度。河北省2010年的主导因子为第二产业生产总值，2011年之后均为人口密度,7a平均 $q$ 值在0.35上下浮动，较大 $q$ 值出现在2011年、2016年，这2a主导因子可以解释接近一半的AOD分布情况。在交互主导因子中，最大 $q$ 值的交互主导因子都是该年度的单一主导因子与另一因子交互的结果，而且任意两个因子交互后的作用强度都明显大于单一因子，但不同地区交互作用强弱略有差异，京津冀地区主导交互因子的平均 $q$ 值为0.51，比单一主导因子增加了0.12。北京市主导交互因子的 $q$ 值增加幅度较大，交互后的平均 $q$ 值为0.83。天津市主导因子交互作用后 $q$ 值增加了0.14，平均达到 $56 \%$ 的解释能力。河北省交互作用最不显著，平均 $q$ 值增加了0.09，交互后平均解释能力为 $44 \%$ 。可以看出,交互作用在北京市最为显著，京津冀地区及天津市的交互作用次之，河北省的作用最不明显，因此，今后对于北京市大气污染的防控更应该注意NDVI与人口密度的交互作用，天津市应注重风速与人口密度、相对湿度、第二产业等的复合作用力。

综合上述不同地区的因子探测的结果,进一步提出各个区域精准治理大气污染的对策与建议。其中，北京市与天津市属于自然一人为因子双重驱动型，河北省属于人为因子驱动型。北京市首要主导因子为NDVI,其次为人口密度，该因子对AOD的影响力稳定居高且与NDVI交互作用巨大。启示北京市应该提高植被覆盖率，有效发挥其对气溶胶粒子的稀释作用，降低污染，并控制人类活动的影响，推崇使用公共交通，减少汽车尾气的排放。天津市的主导因子为风速,人口密度及NDVI的影响力次之，GDP的作用力逐年升高，且风速与人为因子、相对湿度的复合作用力显著。进一步提出天津市应有效利用风力这一自然条件,控制污染企业的合理布局，促进本地污染物扩散，增加植被覆盖度有效防治扬尘地块，减少风蚀起尘，最后应重点控制人类生产生活废气的排放，防止人为污染的进一步加剧。河北省属于人为因子驱动型，人口密度是AOD的首要影响因子，GDP及第二产业的作用力次之，相对湿度的影响力有逐渐增加的趋势，针对上述主导因素，河北省应着重降低人类活动对污染物的排放，杜绝散煤烟煤的使用，发展清洁能源，提倡公众绿色生活，同时应该调整产业结构，促进第二产业的能源优化，鼓励发展第三产业等。

# 3讨论

本文采用AOD遥感数据来反映区域空气污染情况而未采用AOD反演的 $\mathrm { P M } _ { 2 . 5 }$ 数据进行研究，主要原因在于 $A O D$ 本身就可有效反映区域气溶胶（直径小于 $1 0 0 ~ { \mu \mathrm { m } }$ 的液体或固体微粒)状况，而且精度较高[7]。通过 $A O D$ 反演 $\mathrm { P M } _ { 2 . 5 }$ 后,多种不确定性因素会导致反演的 $\mathrm { P M } _ { 2 . 5 }$ 浓度存在一定的误差，目前比较先进的模型（时空地理加权模型、两步骤混合效应模型、贝叶斯模型等)反演 $\mathrm { P M } _ { 2 . 5 }$ 浓度的平均预测误差也达到 $1 2 \sim 1 8 ~ { \mu \mathrm { g } } \cdot { \mathrm { ~ m } } ^ { - 3 [ 2 5 - 2 7 ] }$ ,甚至不同模型添加不同的辅助因子，会得到不同的结果。同时李成才等[3]也证明了高分辨率的 MODIS AOD 数据研究城市地区的空气污染具有显著的可行性。因此本研究选择NASA 提供的MODISAOD数据直接分析。

另外， $A O D$ 定义为介质的消光系数在垂直方向上的积分，是描述一定的垂直高度上气溶胶对光的削减作用。若将AOD垂直订正为地面消光系数，与地面气象因子及人为因子进行影响分析显然更为合理，但由于获取2547d不同地区的边界层高度数据困难较大，本文利用整个区域的年平均边界层高度数据进行试验，研究结果显示京津冀地区年际边界层高度变化不大，用其进行垂直订正的效果不明显，最终将其统一视为AOD估算的系统误差。在未来的研究中，应该使用每日不同地区的边界层高度数据进行垂直订正，才能保证订正结果的准确性。

与前人对京津冀地区AOD的影响因子的研究结果对比可知,本文结果表明京津冀全区及河北省的首要影响因子为人口密度,这与张西雅等[8]、刘状等[1]研究结果一致。但本文基于不同区域的探测结果显示北京和天津的自然因子也起到较大的作用，这与刘壮等认为AOD受自然源影响较小的结论不一致，造成两者结论不同的原因可能是刘状等并未进行AOD与自然因子的定量分析，只是认为人口密度增长与AOD增长趋势及范围十分一致，进一步推测说明自然因子影响较小，而本文对自然与人为因子均进行定量分析，结果相对更为可靠。

AOD与其影响因子的Pearson相关分析结果显示，京津冀地区及河北省是人为因子占主导，与地理探测结果一致，而天津市与北京市相关性较明显的均为自然因子，地理探测器的结果则表明两地区AOD的空间分异是受自然与人为双重作用的结果。两者结果既有相似性也存在一定的差异性，这主要与两个统计方法的原理不同有关，Pearson相关系数分析法主要是衡量AOD及影响因子之间线性关系，而地理探测器则对变量无线性假设，可以探测变量与影响因子之间的所有关系。且京津冀地区AOD及其影响因子的空间差异较大，将AOD与其影响因子看成一个整体进行Pearson相关分析，显然忽视了要素的空间异质性，而地理探测器基于空间分异理论，探测导致要素空间分异的驱动因子，从这个角度看，地理探测器对AOD的影响机理探测可能更加合理。目前对京津冀地区AOD驱动因子的空间探测前所未有，因此，本文的研究结果对该地区的大气环境监测以及工农业生产布局等具有重要意义。

# 4结论

（1）2010—2016 年京津冀地区A0D 的年均值为0.83，其中，天津市AOD的年均值为研究区最高，河北省次之，北京市最低。研究区整体及各分区AOD的年变化趋势大体一致，呈现先下降后上升再小幅波动的态势。

（2）空间自相关结果表明研究时段内京津冀地区AOD空间分布呈现显著的正相关。局部高高聚集区、低低聚集区及不显著区域各占总面积的大约1/3。北京市东南部、天津市南部、河北省中南部始终是三大高高聚集区，呈现轻微缩小的态势，低低聚集区位于西北部山区，呈现减小趋势，其余地区均为不显著区域，面积呈扩大态势。

（3）地理探测器的结果显示北京市首要影响因子为NDVI,其次为人口密度，且二者交互作用后对AOD影响巨大。天津市主导因子为风速，人口密度、第二产业生产总值等人为因子的作用力逐渐增大，风速与其交互作用较强。河北省主导因子为人口密度，GDP与第二产业生产总值等的作用力次之，整体交互作用偏弱。启示北京市与天津市应有效发挥自然因子的正效应，并同时防控好人类活动的影响，河北省应重点减少人为活动的排放。

# 参考文献(References)

[1]VINEIS P,HUSGAFVEL-PURSIAINEN K.Air polution and canc-er:Biomarker studies in human populations[J].Carcinogenesis,2005,26(11) :1846-1855.  
[2］刘浩,高小明,谢志英,等.京津冀晋鲁区域气溶胶光学厚度的时空特征[J].环境科学学报,2015,35（5）：1506-1511.［LIU

Hao,GAO Xiaoming,XIE Ziying,et al. Spatio-temporal character

istics of aerosol optical depth over Beijing-Tianjin-Hebei-ShanxiShandong region during 20o0—2013[J].Acta Scientiae Circumstantiae,2015,35(5）:1506 -1511.]   
[3]李成才,毛节泰,刘启汉,等.利用 MODIS 光学厚度遥感产品 研究北京及周边地区的大气污染[J].大气科学,2003,27（5）： 869 -880.[LI Chengcai,MAO Jietai,Alexis Kaihon LAU,et al. Research on the air pollution in Beijing and its surroundings with MODIS AOD products[J].Chinese Journal of Atmospheric Sciences,2003,27(5） :869-880.]   
[4]CHU D A,KAUFMAN YJ,ICHOKU C,et al.Validation of MODIS aerosol optical depth retrieval over land[J].Geophysical Research Letters,2002,29（12） :8007.   
[5］罗云峰,吕达仁,周秀骥,等.30 年来我国大气气溶胶光学厚度 平均分布特征分析[J].大气科学,2002,（6）：721-730.[LUO Yunfeng,LYU Daren,ZHOU Xiuji,etal. Analyseson the spatial distribution of aerosol optical depth over China in recent 3O years [J].Chinese Journal of Atmospheric Sciences,2002,（6）:721- 730.]   
[6］关佳欣,李成才.我国中、东部主要地区气溶胶光学厚度的分 布和变化[J].北京大学学报,2010,46(2）:185－191.[GUAN Jiaxin,LI Chengcai.Spatial distributions and changes of aerosol optical depth over eastern and central China[J].Acta Scientiarum Naturalium Universitatis Pekinensis,2010,46(2）:185-191.]   
[7]MUNCHAK L A,MATTOO S,LEVY R C,et al. The MODIS $3 ~ \mathrm { k m }$ aerosol product:Applications over an urban/suburban landscape during DISCOVER-AQ[C]. Agu Fall Meeting,2012,12.   
[8］张西雅,启海波.京津冀地区气溶胶时空分布及与城市化关系 的研究[J].大气科学,2017,41（4）:797-810.[ZHANG Xiya, QI Haibo.Spatio-temporal characteristicsof aerosoloptical depth and their relationship with urbanization over Beijing-Tianjin-Hebei region[J].Chinese Journal of Atmospheric Sciences,2017,41 (4) :797 -810. ]   
[9]孙晓雷,甘伟,林燕,等.MODIS $3 ~ \mathrm { k m }$ 气溶胶光学厚度产品检 验及其环境空气质量指示[J].环境科学学报,2015,35（6)： 1657-1666.[SUN Xiaolei,GAN Wen,LIN Yan,et al.Validation of MODIS $3 ~ \mathrm { k m }$ aerosol optical depthproductanditsairqualityindication[J].Acta Scientiae Circumstantiae,2015,35(6）:1657- 1666. ]   
[10］景悦,孙艳玲,付宏臣,等.2010—2016 年京津冀A0D 时空变 化及其影响因子分析[J].环境科学与技术,2018,41（8): 104-113.[JING Yue,SUN Yanling,FU Hongchen,et al. Temporal and spatial variation of aerosol optical depth and analysis of influencing factors in Beijing-Tianjin-Hebei region from 2OlO to 2016 [J].Environmental Science & Technology,2018,41（8）:104 - 113.]   
[11］刘状,孙曦亮,刘丹,等.2001—2017年中国北方省份气溶胶光 学厚度的时空特征[J].环境科学学报,2018,38（8）：3177- 3184.[LIU zhuang,SUN Xiliang,LIU Dan,et al. Spatio-temporal characteristics of aerosol optical depth over Beijing-Tianjin-HebeiShandong-Henan-Shanxi-Shaanxi region during 2001—2017[J]. Acta Scientiae Circumstantiae,2018,38（8）:3177 -3184.]   
[12］董自鹏,余兴,李星敏,等.基于MODIS 数据的陕西省气溶胶 光学厚度变化趋势与成因分析[J].科学通报,2014,59（3）： 306-316.[DONG Zipeng,YU Xing,LI Xingmin,et al.Analysis of aerosol optical thickness variation and its causes in Shaanxi Province based on MODIS data[J].Chinese Science Bulletin, 2014,59(3):306-316.]   
[13］张宸赫,赵天良，王富，等.2003—2014年东北三省气溶胶光学 厚度变化分析[J].环境科学,2017,38（2）：476－484. [ZHANG Chenhe,ZHAO Tianliang,Wang Fu,et al.Variations in aerosol optical depth over three northeastern provinces of China in 2003—2014[J]. Environmental Science,2017,38（2）:476- 484.]   
[14］张静怡,卢晓宁,洪佳,等.2000—2014 年四川省气溶胶时空格 局及其驱动因子定量研究［J].自然资源学报,2016,31（9）： 1514-1525.［ZHANG Jingyi,LU Xiaoning,HONG Jia,et al. Quantitative study on temporal and spatial patterns of aerosol optical depth and its driving forces in Sichuan Province during 2000一 2014[J]. Journal of Natural Resources,2016,31（9）: 1514- 1525.]   
[15］高宇潇,刘志辉,王敬哲.乌鲁木齐市 $\mathrm { P M } _ { 2 . 5 }$ 浓度与MODIS 气溶 胶光学厚度相关性分析[J].干旱区地理,2018,41（2）：298- 305.[GAO Yuxiao,LIU Zhihui,WANG Jingzhe. Correlation analysis of $\mathrm { P M } _ { 2 . 5 }$ concentration and MODIS aerosol optical depth in Urumqi City[J].Arid Land Geography,2018,41(2）:298 -305.]   
[16]WANG JF,HU Y.Environmental health risk detection with GeogDetector[J].Environmental Modelling & Software,2005,20（10）： 114 - 115.   
[17］刘小鹏,王可,叶均艳,等.宁夏水贫困地域分异的WPI-Geodetector 测度与分析[J].干旱区地理,2018,41（1）：160－169. [LIU Xiaopeng,,WANG Ke,YE Junyan,et al. Measurement and analysis of spatial-temporal differentiation of water poverty in Ningxia based on WPI-geodetector[J]. Arid Land Geography, 2018,41(1):160 -169.]   
[18]LOU C R,LIU H Y,LI YF,et al.Socioeconomic drivers of $\mathrm { P M } _ { 2 . 5 }$ in the accumulation phase of air pollution episodes in the Yangtze River Delta of China［J].International Journal of Environmental Research & Public Health,2016,13（10） :928.   
[19］马小雯,章笑艺,来丽芳,等.基于地理探测器的浙江省空气质

量风险因子分析[J].浙江大学学报（理学版）,2018,45（3）：

351-362.[MA Xiaowen,ZHANG Xiaoy1,LAl Litang,et al. Study on risk factors of air quality in Zhejiang Province based on geographical detectors[J]. Journal of Zhejiang University（Science Edition）,2018,45(3) :351-362.]   
[20］周亮,周成虎,杨帆,等.2000—2011年中国 $\mathrm { P M } _ { 2 . 5 }$ 时空演化特 征及驱动因素解析[J].地理学报,2017,72(11)：2079-2092. [ZHOU Liang,ZHOU Chenghu,YANG Fan,et al. Spatio-temporal evolution and the influencing factors of $\mathrm { P M } _ { 2 . 5 }$ in China between 2000 and 2011[J].Acta Geographica Sinice,2017,72（11）: 2079 -2092.]   
[21］郭春颖,施润和,周云云，等.基于遥感与地理探测器的长江三 角洲空气污染风险因子分析[J].长江流域资源与环境,2017， 26（11）:1805-1814.[GUO Chunying,SHI Runhe,ZHOU Yunyun,et al.Analysis on risk factors of air pollution over the Yangze River Delta using remote sensing and geographical detector[J]. Resources and Environment in the Yangtze Basin,2017,26（11）: 1805-1814.]   
[22］魏继德.空间插值方法的比较与优化［D].福州：福州大学, 2010.［WEI Jide.The comparison and optimization of spatial interpolation approaches[D].Fuzhou:Fuzhou University,2010.]   
[23］王振波,方创琳,许光,等.2014 年中国城市 $\mathrm { P M } _ { 2 . 5 }$ 浓度的时空 变化规律[J].地理学报,2015,70（11）：1720-1734.［WANG Zhenbo,FANG Chuanglin,XU Guang,etal.Spatial-temporal characteristics of the $\mathrm { P M } _ { 2 . 5 }$ in China in 2014[J].Acta Geographica Sinice,2015,70(11）:1720 -1734.]   
[24］王劲峰,徐成东.地理探测器：原理与展望[J].地理学报, 2017,72（1）:116-134.[WANG Jinfeng,XU Chengdong.Geodetector:Principle and prospective[J].Acta Geographica Sinice, 2017,72(1) :116 -134.]   
[25]HE Q,HUANG B.Satellite-based mapping of daily high-resolution ground $\mathrm { P M } _ { 2 . 5 }$ in China via space-time regression modeling[J].Remote Sensing of Environment,2018,206:72-83.   
[26]MA Z,HU X,SAYER AM,et al.Satellite-Based Spatiotemporal Trends in $\mathrm { P M } _ { 2 . 5 }$ Concentrations:China,2004—2013[J].Environ Health Perspect,2016,124(2） :184-192.   
[27]LYU B,HU Y,CHANG HH,et al. Daily estimation of ground-level $\mathrm { P M } _ { 2 . 5 }$ concentrations at4 km resolution over Beijing-Tianjin-Hebei by fusing MODIS AOD and ground observations[J].Science of the Total Environment,2017,580:235 -244.

# Spatiotemporal variations of AOD and geographical detection of its influence factors in Beijing-Tianjin-Hebei region

JING Yue1•²，SUN Yan-ling’，GAO Shuang'，CHEN Li’，PAN Long’，MA Han1 (1College ofGeographyand Environment Science,Tianjin Normal University,Tianjin 3Oo387,China) 2Xi'an Institute for Innovative Earth Environmental Research,Xi'an 71oo61,Shaanxi,China)

Abstract：The Beijing-Tianjin-Hebei region,which is located in the BohaiRim,isthe most economicall developed region in northern China.It is also one ofthe most poluted regions in China.Aerosol optical depth（AOD）can effctively reflectthe degree of airpollution.In this study,the MODIS 3 kmAODremote sensing data was analyzed and the research results would beof greatsignificance to China's air pollution.Firstly,the temporal variation characteristics and spatial autocorrelation characteristics of $A O D$ in Beijing-Tianjin-Hebei region from 201O to 2016 were analyzed.The factorsof precipitation,wind speed,relative humidity,normalized diference vegetation index（ND（204号 $\boldsymbol { W }$ ）,gross domestic product（GDP）,secondary industry GDP,population density were selected as the afecting factors of $A O D$ ,using geographical detection to analyze the trend of the factors contribution ratio and its dominant affecting factors indiffrentregionsanddiferent times in Beijing-Tianjin-Hebeiregion.Theresultsshowedas follows : （1） The annual average $A O D$ of the Beijing-Tianjin-Hebei region was 0.83 from 2010 to 2016.The annual average $A O D$ of Tianjin was the highest inthe study area,followed by Hebei and Beijing.The annual variation trend of $A O D$ （20 was shown an overall state of decline first followed by riseand then asmall fluctuation change and a similar status in each local region as well.（2）The spatial autocorrelation analysis indicated a significant positive correlation among spatial distribution of $A O D$ in Beijing-Tianjin-Hebei region.Local high-accumulation areas were mainly concentrated in the southeastern partof Beijing,southern part of Tianjin,and central-southernpartof Hebei Province. The low-accumulation areas were concentrated in the mountains ofthe northwest.The area of the high and low accumulationareas inBeijing-Tianjin-Hebei regionshowedadecreasing trend,hilethearea of the non-significantareas showed an increasing trend.（3）Geographic detection analysis indicated that theprimary influencing factor was NDVI in Beijing,followed by population density,and their interaction was significant.The dominant factor was wind speed in Tianjin.The efect of human factors such as population density and the GDPof the secondary industry were also important.The effect of interactions between wind speed and theabove factors were also significant.The dominant factor was population density in Hebei Province,follwed by GDPand thesecondary industry’s GDP,and the overallinteraction wasrelatively weak.In thepast,thecorrelation analysisof the influencing factors was basedon linear relationshipofthe overallarea,while the geographical detection notonly haswirelessassumptions,but also reveals the linear,nonlinearandspatial relationshipsof thedriving factors.From thisperspective,the geographical detection is morereliable in studying the influencing factors.This studyapplied geographical detection to analysis of the impacting factors of $A O D$ in Beijing-Tianjin-Hebei region,which proved its feasibility in this field and this region.At the same time,theresults also had importantreference value for air polution prevention,industrial and agricultural layout and urban construction in Beijing-Tianjin-Hebei region.

Key words:aerosol optical depth(AOD）；spatial-temporal variations；geographical detection； influencing factors；Beijing-Tianjin-Hebei region