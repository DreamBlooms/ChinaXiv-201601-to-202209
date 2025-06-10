# 荒漠土壤成分对陆面过程的影响

李火青'，金莉莉'，买买提艾力·买买提依明¹，赵佳伟²(1．中国气象局乌鲁木齐沙漠气象研究所,新疆 乌鲁木齐830002；2．新疆师范大学,新疆 乌鲁木齐摘要：采集塔克拉玛干沙漠北缘肖塘观测站附近的土壤,应用 Mastersizer-2000 激光粒度仪测定土壤粒径,按照伍登－温德华粒级标准进行土壤成分分类,发现土壤类型并非均质沙土，在 $0 \sim 3 0 ~ \mathrm { c m }$ 深度的浅层存在 $1 0 \% \sim 2 4 \%$ 的黏土,根据土壤成分比例对Noah陆面模式的土壤参数重计算,然后利用肖塘站2011年3月22日至7月25日的观测数据驱动Noah模式,对比修正土壤参数前后的模拟效果。结果表明：更新土壤参数后 $1 0 \ \mathrm { c m }$ 土壤温度模拟偏差减少 $0 . 6 2 ~ \mathrm { ^ { \circ } C }$ ,土壤热通量偏差减小 $1 0 . 4 7 \mathrm { ~ W ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ,感热通量偏差减少 $7 . 0 2 \mathrm { ~ W ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ,地表净辐射偏差减少5.48$\mathrm { ~ \mathbb ~ W ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ,且效率系数达到更高的接受程度。通过泰勒图分析了土壤参数修正对 Noah 模拟效果的整体作用,表明修正土壤参数后的模式中热量传输扩散有一定的优化作用， $1 0 \ \mathrm { c m }$ 土壤温度和热通量土壤温度模拟效果得到改进。

关键词：荒漠；土壤成分；陆面过程；Noah模式；塔克拉玛干沙漠

陆气相互作用是地球系统中对陆面与大气之间的物质能量交换过程，并始终影响着不同时空尺度的天气和气候变化[1]。陆面为天气和气候模式提供必要的下垫面条件，大气强迫陆面的物理特征发生变化，与大气之间能量及物质的交换是影响天气系统的重要因素[2]。不同类型下垫面的陆面物理特征有明显差异，因此，其陆面过程也存在很大差异[3]。沙漠是一种特殊的下垫面,沙漠地表反照率大，比辐射率小，土壤热容量小，含水量低，是地球系统的重要感热源，对区域能量平衡及气候特征具有重要的作用[4]。沙漠地表以及陆面过程与全球其他区域相比有着明显的差异，由于降水量极低，植被稀疏，潜热通常可以忽略不计，感热输送作为沙漠地区地气间能量交换的主要方式[5-7]。在土壤热力学研究中，土壤成分决定了其焓、比热容、热传导率、热扩散率等热力学性质[8]。由于沙漠地表的独特性，其土壤成分及土壤参数是影响土壤中热量传输的主要因素，通用的陆面模式中沙漠土壤成分信息和参数与实际值存在一定偏差[9],导致陆面模式对沙漠下垫面的陆面过程模拟效果还不理想[10]。因此,对沙漠土壤成分测定和陆面过程模拟分析是一种提升沙漠区域能量平衡模拟效果的科学方法。

近年来，国内外开展了土壤观测和陆面过程实验,Liu 等[1基于塔克拉玛干沙漠腹地的陆气相互作用观测试验数据，修正了CoLM（commonlandmodel)模式中的土壤热传导率等参数，能量通量模拟效果有了明显提升。吴小波等[12]基于 Noah 陆面过程模型模拟青藏高原植被和土壤特征对多年冻土的影响，发现不同时期的土壤状态对Noah的模拟效果有明显差异。土壤成分的差异会导致其热力学参数和水力学参数有明显差别,何玉洁等[13]对青藏高原含砂砾石土壤导热率实验研究发现，砂砾石对土壤导热率有显著影响，提出在陆面过程模拟研究中必须考虑砂砾石对土壤热力学参数的作用，进而提高陆面过程模拟的精度。一般在陆面模式中默认土壤为均质分布，会导致能量通量的模拟结果有不确定性。Han 等[14]认为,CLM（community land mod-el)的土壤参数存在不确定性,更新了模式中的土壤参数后，CLM模式的土壤温湿度、热通量等的模拟效果有一定改善。土壤性质在不同的空间尺度上表现出高度的非均质性，其准确估算混合下垫面的土壤参数仍然是一个重要挑战,Baroni 等[15]提出了3种描述土壤性质不确定性的微扰方法，在较大程度上探索出土壤参数的时空分异特征，进一步完善了水文模式对土壤中水热传输的估算。曹寰琦等[16]对塔克拉玛干沙漠北缘不同季地表能量平衡闭合特征进行了分析，研究表明：地表以下 $5 \ \mathrm { c m }$ 深度的能量闭合程度最高，浅层土壤的能量通量对陆面能量平衡非常重要。不同土壤成分的热力学参数对陆面模式的模拟效果有重要作用，这些参数既能影响土壤热量传递的速度和深度，又能改变土壤水分传输。沙漠环境不便于观测实验，对沙漠区域土壤成分及参数的测定和估算存在较大空白，本项目利用Mas-tersizer-2000激光粒度仪测定塔克拉玛干沙漠北缘肖塘观测站的土壤成分，根据成分比例计算Noah模式层土壤参数，通过Noah模式对比试验分析，探索沙漠土壤成分对陆面过程的影响。

# 1 研究区和数据

# 1.1 研究区概况

塔克拉玛干沙漠是中国面积最大的沙漠（总面积 $3 . 3 8 \times 1 0 ^ { 5 } \ \mathrm { k m } ^ { 2 }$ ,东西相距 $1 ~ 0 0 0 ~ \mathrm { k m }$ 、南北相距$4 0 0 ~ \mathrm { k m } { \cdot }$ ），分布范围 $3 7 ^ { \circ } \sim 4 1 ^ { \circ } \mathrm { N } \sqrt { , 7 7 ^ { \circ } } \sim 9 0 ^ { \circ } \mathrm { E }$ ，位于塔里木盆地中央[17],该沙漠大多为流动沙丘和沙丘链，如 $3 0 0 ~ \mathrm { ~ m ~ }$ 高的金字塔形沙丘和新月形沙丘[18-19]。塔克拉玛干沙漠也是中国极端干旱气候区,年平均降水量小于 $1 0 0 ~ \mathrm { { m m } }$ ,最低只有 $4 \sim 5 ~ \mathrm { m m }$ 而年平均蒸发量达 $3 ~ 4 0 0 ~ \mathrm { m m }$ ，有显著的大陆性气候特征[20] O

肖塘陆气相互作用观测试验站（ $( 4 0 ^ { \circ } 4 8 ^ { \prime } \mathrm { ~ N ~ }$ ，$8 4 ^ { \circ } \mathrm { 1 8 ^ { \prime } E }$ ,海拔 $9 3 3 \mathrm { ~ m ~ }$ ,简称肖塘站），位于塔克拉玛干沙漠北缘（图1a），距离塔里木河 $4 0 ~ \mathrm { k m }$ ，位于平坦的风蚀裸露古河床上，下垫面为自然沙面，周围的新月形沙丘及沙丘链一般宽度为 $6 \sim 1 5 \mathrm { ~ m ~ }$ 。该观测站配置有 $1 0 0 \mathrm { ~ m ~ }$ 的11层梯度观测铁塔、 $1 0 \mathrm { ~ m ~ }$ 通量观测塔、7层土壤温湿度和通量观测系统，以及9种辐射观测仪（图1b）。

# 1.2 数据

于2018年4月27日在塔克拉玛干沙漠北缘新月形沙丘及平地挖断面，如图2a所示。新月形沙丘及平地、沙漠南缘金字塔沙丘及绿洲平地采集不同部位不同深度的沙粒样本开展粒度实验分析。其中，沙漠北缘肖塘平地沙粒样本采集10层剖面，分别为 $0 \mathrm { ~ , ~ } 3 \mathrm { ~ , ~ } 6 \mathrm { ~ , ~ } 1 2 \mathrm { ~ , ~ } 2 0 \mathrm { ~ , ~ } 4 0 \mathrm { ~ , ~ } 6 0 \mathrm { ~ , ~ } 1 0 0 \mathrm { ~ , ~ } 1 7 0 \mathrm { ~ , ~ } 2 0 0 \mathrm { ~ c m }$ ;其余各沙丘部位及平地均采集5层剖面，分别为0、5、10、$2 0 \ : 4 0 \ : \mathrm { c m }$ 深度。所有剖面中未发现有植被根系，为均值沙土或伴有少量黏土成分。

![](images/570df940a93ad77218792886567cd4b0aca2a1f7555830004ddd90baf805da41.jpg)  
Fig.1Locations of the observation station and the $1 0 \mathrm { ~ - ~ } \mathrm { m }$ -high observation tower

![](images/7ff7ff501d86114b0769ee5e4a8cce0ecf42f5f856c9a7e745e2348692165649.jpg)  
图1观测站位置示意图和 $1 0 \mathrm { ~ m ~ }$ 观测塔  
图2土壤成分采样剖面和Mastersizer-2000 激光粒度仪 Fig.2Sampling profile of soil composition and Masterizer-2OOo Laser Particle Sizer

# 2 研究方法

# 2.1 Noah陆面模型

NoahLSM是基于OSU陆面模型发展而来，遵循强迫-恢复原理。Noah将土壤分为2层，地表分为单层积雪和冠层。基于热扩散方程和Richardson方程分别计算土壤温度和土壤水含量，采用Penman公式计算潜热通量，其植被分类采用USGS（U.S.geological survey)分类方案，土壤数据采用世界粮农组织全球土壤数据集。计算模块包括：生物气候、能量、冠层辐射传输、动量/感热/潜热通量交换、土壤和积雪温度、水文、动态植被等模块。Noah能够全面考虑大气、植被、积雪等局部因素对地面热状态的影响，描述了土壤-积雪-植被与大气的相互过程，能够模拟土壤温度、土壤含水量、冠层含水量、雪深、水汽、能量通量、向上长短波辐射强度等[21]。Noah模式被美国环境预报中心广泛应用于天气/气候模式，目前已经耦合到WRF（weatherresearchand fore-casting model） $\operatorname { R e g C M }$ （regional climatemodel）等模式，经过应用和检验得到了持续的发展，主要改进有：土壤分层改为4层 $( 0 . 1 \ 、 0 . 3 、 0$ .6m和 $1 . 0 \ \mathrm { m } ^ { \cdot }$ ；增加了冠层传导方程[22];裸地蒸散和植被物候学[23];新的径流模式[24];热力学粗糙度的参数化方案及地表层感热交换系数[21]。Noah 的能量、土壤温度计算方程可以表示为[25]：

$$
R _ { \mathrm { n e t } } = \left( 1 - \alpha \right) S _ { \mathrm { D } } + \varepsilon ( L _ { \mathrm { D } } - \sigma T _ { \mathrm { \ s f c } } ^ { 4 } )
$$

$$
R _ { \mathrm { { n e t } } } = H + L E + G _ { 0 }
$$

式中： $R _ { \mathrm { n e t } }$ 为净辐射； $S _ { \mathrm { { D } } }$ 和 $L _ { \mathrm { D } }$ 分别为向下的短波、长波辐射，是输入数据中必要的驱动要素； $T _ { \mathrm { s f c } }$ 是地表温度; $\sigma$ 是Stefan-Boltzmann 常数; $\alpha$ 和 $\boldsymbol { \varepsilon }$ 分别为地表反照率和地表比辐射率。在能量平衡方程（2)中， $H$ 是感热通量； $L E$ 为潜热通量; $G _ { 0 }$ 为土壤热通量。感热通量 $H$ 在NoahLSM的计算可以表示为：

$$
H = \ - \rho c _ { \mathrm { p } } C _ { \mathrm { h } } u \big ( T _ { \mathrm { a i r } } ^ { \mathrm { } } - T _ { \mathrm { s f c } } ^ { \mathrm { } } \big )
$$

式中： $_ { \cdot \rho }$ 为空气密度； $c _ { \mathrm { p } }$ 是空气定压比热； $u$ 为风速;$T _ { \mathrm { a i r } }$ 为距离地面一定高度在绝热调整后的空气温度;$T _ { \mathrm { s f c } }$ 为地表温度; $C _ { \mathrm { h } }$ 为感热交换系数，是一个非常重

要量。土壤热通量 $G _ { 0 }$ 的计算方式为：

$$
G _ { 0 } = k _ { \mathrm { T } } ( \Theta _ { 1 } ) \frac { T _ { \mathrm { s f c } } - T _ { 1 } } { h _ { 1 } }
$$

式中： $k _ { \mathrm { T } }$ 为土壤热传导率，一般由土壤含水量()和土壤类型决定； $T _ { 1 }$ 为土壤上层温度; $h _ { 1 }$ 是第一层土壤的中间深度。在干燥的土壤条件下， $\Theta$ 是非常小的，它的变化在大多时候基本可以忽略; $k _ { \mathrm { T } }$ 在固定的站点是根据土壤参数表匹配的固定值，因此，在干旱区土壤热通量 $G _ { 0 }$ 主要依赖于 $\left| k _ { \mathrm { T } } \right.$ 和地表温度$T _ { \mathrm { s f c } }$ 。土壤温度的计算如下：

$$
\frac { \partial T } { \partial t } = \frac { \partial } { \partial z } \left[ \lambda \frac { \partial T } { \partial z } C ( \theta ) \right]
$$

式中： $T$ 为土壤温度; $\mathbf { \Psi } _ { t } \mathbf { \Psi } _ { t }$ 为时间； $\lambda$ 为土壤热传导率$( \mathrm { ~ W ~ } \cdot \mathrm { ~ m ~ } ^ { - 1 } \cdot \mathrm { ~  ~ \mathcal ~ { ~ C ~ } ~ } ^ { - 1 } \cdot$ ; $C ( \theta )$ 为土壤纹理函数； $z$ 为土壤深度。

# 2.2土壤成分测定方法

沙粒样本分析应用Mastersizer-2000 激光粒度仪测定（图2b）,测量粒度范围为 $0 . 0 2 \sim 2 ~ 0 0 0 ~ upmu \mathrm { m }$ 。粒度划分标准按照伍登-温德华粒级标准进行，粒度参数分析应用公式(5)计算平均粒径。

$$
\phi = - \log _ { 2 } d
$$

式中： $d$ 是沙粒直径; $\phi$ 为伍登－温德华 ${ } - \phi$ 值,用于对土壤质地分类。

# 2.3 分析方法

在本次研究中，利用2011年3月22日至7月24日的观察数据驱动NoahV3.4模式，这期间肖塘无降水，有多云/沙尘等天气，为客观分析土壤成分差异对陆面过程的影响，需晴好天气，因此，选择7月1—10日模拟结果分析，采用4种评估指标对模型的模拟结果进行分析，分别为：绝对平均误差(meanabsoluteerror,MAE）;效率系数（nash-sutcliffeefficiency，NSE），NSE值从负无穷到1，越接近1表示模拟结果越接近观测值， $\mathrm { N S E } = 1$ 时,表明模拟值与观测值一致, $\mathrm { N S E } > 0 . 5$ 表示模拟效果可以接受，当 $\mathrm { N S E } < 0$ 时则表示模拟效果差；均方根误差（rootmeansquareerror，RMSE），常用于模拟值与观测值之差的平方的期望值;决定性系数 $( R ^ { 2 } )$ ,用于表征模拟值与观测值之间的相关性。其中，前3个指标主要用于评价模型的模拟性能， $R ^ { 2 }$ 用于泰勒图分析模拟效果的整体性能。MAE、RMSE、NSE和 $R ^ { 2 }$ 分别定义为：

$$
\mathrm { M A E } = \frac { 1 } { n } { \sum _ { i = 1 } ^ { n } ( \begin{array} { l } { | } \end{array}  } S _ { i } - O _ { i } \ | \ )
$$

$$
{ \mathrm { N S E } } = 1 - \sum _ { i = 1 } ^ { n } { \big ( } S _ { i } - O _ { i } { \big ) } ^ { 2 } { \Bigg / } \sum _ { i = 1 } ^ { n } ( \left. O _ { i } - { \overline { { O } } } \right) ^ { 2 }
$$

$$
{ \mathrm { R M S E } } = { \sqrt { { \frac { 1 } { n } } { \sum _ { i = 1 } ^ { n } ( S _ { i } - O _ { i } ) ^ { 2 } } } }
$$

$$
R ^ { 2 } =  [ \begin{array} { c } { { \sum } } \\ { { i } } \end{array} ( { \cal O } _ { i } - \overline { { { \cal O } } } { } ) ( S _ { i } - \overline { { { \cal S } } } ) \ ] ^ { 2 } /
$$

$$
\sum _ { i } { ( O _ { i } - \overline { { O } } ) ^ { 2 } } \sum _ { i } { ( S _ { i } - \overline { { S } } ) ^ { 2 } }
$$

式中： $S _ { i }$ 为模拟值; $O _ { i }$ 为观测值； $\mathit { \Pi } _ { \overline { { S } } } ^ { - }$ 为模拟值的平均值； $\overline { { o } }$ 为观测值的平均值； $n$ 为样本量。

# 3 结果分析

# 3.1 土壤成分测定

在剖面采样的土壤根据伍登-温德华粒级标准粒度划分分类，计算出每一层的土壤成分比例，表1为多层土壤成分的比例，经统计得到模式层的土壤成分比例（图3），其中第一层砂质占 $7 5 . 4 7 \%$ ,黏土$2 4 . 5 3 \%$ ，第二层砂质占 $8 7 . 8 \%$ ,黏土 $1 2 . 2 \%$ ，下两层均为砂质土壤，然后按照Noah模式中沙地和黏土混合层的参数，见表2。通过表2可以了解到，重新测定的土壤参数有较大差异，土壤热力学参数减小，土壤水力学参数增大。

# 3.2 土壤温度

土壤温度(ST)是陆面过程重要的物理量，直接影响着土壤中水分、水汽的保持和运移，对土壤中的物理过程均有影响。图4给出了Noah的 $1 0 \ \mathrm { c m }$ 土壤温度观测值与2组模拟对比曲线，Noah模式均能够较好地反映塔中站的土壤温度变化，原始土壤参数模拟的土壤温度早正午时明显偏高，在夜间有偏低现象，修正土壤参数后的模拟结果较好地改善了这种情况。根据表3可知，修正后的土壤热传导率系数明显减小，其绝对平均偏差从 $1 . 3 3 2 \mathrm { ~ } ^ { \circ } \mathrm { ~ C ~ }$ 减至$0 . 7 1 2 \mathrm { ~ } ^ { \circ } \mathrm { C }$ ,RMSE由 $1 . 5 6 \mathrm { ~ \textdegree C }$ 减小到 $0 . 7 8 \mathrm { ~ } \mathrm { ~ } ^ { \circ } \mathrm { C }$ ,模拟效率系数也有明显提升。土壤的热量来源是太阳辐射，每种土壤吸收一定热量后温度变化的程度存在差异，主要是其土壤热力学参数不同，通过表2可看出，按砂质和黏土比例计算的热传导系数减小了0.36，根据土壤温度计算公式(5)可知，土壤热传导率的减小会导致土壤温度振幅减小，改善了中午高估和夜间的低估程度。

# 3.3土壤热通量

土壤热通量 $G _ { 0 }$ 作为地表能量平衡方程中的重要分量之一，是表征地表接收到太阳辐射向下传到下层土壤的热量，一般定义为向下传导热量为正通量，反正为负。土壤热通量的计算主要取决于地表温度，土壤热力学参数、土壤水含量。通过图5可以看出，Noah能够较好模拟出土壤热通量的变化趋势，但原始参数模拟值在中午明显偏高，最高超过观测 $2 0 0 \mathrm { \ : W \cdot \ m } ^ { - 2 }$ 。根据土壤成分重新计算土壤参数

表1多层土壤成分比例 Tab.1composition ratios of multi-layer soil   

<html><body><table><tr><td></td><td>粗砂</td><td>中砂</td><td>细砂</td><td>粗粉砂</td><td>细粉砂</td><td>黏土</td></tr><tr><td>0cm</td><td>0</td><td>0.55</td><td>17.79</td><td>12.45</td><td>47.72</td><td>21.49</td></tr><tr><td>3cm</td><td>0</td><td>0.11</td><td>0.98</td><td>12.52</td><td>50.78</td><td>35.62</td></tr><tr><td>6cm</td><td>0</td><td>0</td><td>1.74</td><td>28.72</td><td>41.98</td><td>27.55</td></tr><tr><td>12 cm</td><td>0</td><td>0</td><td>2.45</td><td>23.7</td><td>44.33</td><td>29.51</td></tr><tr><td>20 cm</td><td>0</td><td>0.69</td><td>56</td><td>14.45</td><td>16.66</td><td>12.2</td></tr><tr><td>40 cm</td><td>0</td><td>4.22</td><td>93.9</td><td>1.87</td><td>0</td><td>0</td></tr><tr><td>60 cm</td><td>0</td><td>4.02</td><td>94.09</td><td>1.89</td><td>0</td><td>0</td></tr><tr><td>100 cm</td><td>0</td><td>5.69</td><td>92.4</td><td>1.91</td><td>0</td><td>0</td></tr><tr><td>平均值</td><td>0</td><td>2.425</td><td>53.88</td><td>10.909</td><td>20.147</td><td>12.637</td></tr></table></body></html>

![](images/d512e8ff81961031c4d61640642d5405dfe4cde9fa52b86b258a98905b88074e.jpg)  
图3土壤分层及成分信息示意图  
Fig.3Information of soil stratification and composition

# 表2土壤参数

Tab.2Soil parameters   

<html><body><table><tr><td>Sand</td><td>BB</td><td>DRYSMC</td><td>F11</td><td>MAXSMC</td><td>REFSMC</td><td>SATPSI</td><td>WLTSMC</td><td>QTZ</td></tr><tr><td>SP-0rg</td><td>2.79</td><td>0.011</td><td>-0.472</td><td>0.339</td><td>0.236</td><td>0.069</td><td>0.01</td><td>0.92</td></tr><tr><td>SP-Res</td><td>4.67</td><td>0.037</td><td>-0.832</td><td>0.339</td><td>0.274</td><td>0.154</td><td>0.037</td><td>0.77</td></tr></table></body></html>

注;SP-Org 为原始土壤参数;SP-Res 为重新测定后土壤参数。BB为计算水势的B参数；DRYSMC 为干土壤蒸发阈值;F11为土壤热传导系数；MAXSMC 为饱和土壤湿度;REFSMC为水分传输时相对土壤湿度;SATPSI为土壤基质势饱和湿度;WLTSMC为冰冻层熔融点湿度；QTZ为土壤石英含量。

# 表3误差统计分析

Tab.3Statistical results of errors   

<html><body><table><tr><td rowspan="2">指标/ 变量</td><td colspan="2">MAE</td><td colspan="2">RMSE</td><td colspan="2">NSE</td></tr><tr><td>Org</td><td>Res</td><td>0rg</td><td>Res</td><td>Org</td><td>Res</td></tr><tr><td>ST</td><td>1.332</td><td>0.712</td><td>1.56</td><td>0.78</td><td>0.72</td><td>0.93</td></tr><tr><td>G0</td><td>39.28</td><td>28.81</td><td>61.63</td><td>45.88</td><td>0.47</td><td>0.71</td></tr><tr><td>H</td><td>18.67</td><td>11.65</td><td>9.32</td><td>9.30</td><td>0.98</td><td>0.99</td></tr><tr><td>Rnet</td><td>28.83</td><td>23.35</td><td>31.40</td><td>15.09</td><td>0.97</td><td>0.99</td></tr></table></body></html>

注： $\mathrm { 0 r g }$ 为原始土壤参数模拟;Res为修正土壤参数后模拟。

——Go-Obs(观测）—Go-Org(原始)-1·M/ M $G _ { 0 }$ MuM0 2 8 4 00 6 0 80- 09 10 -20 7 07 07 7 0 07 7 0日期/月-日

![](images/e51b4eccd0fc271754e749b5479515f98425243313ed6e1b771ae3baed74b8b5.jpg)  
图4 $1 0 \ \mathrm { c m }$ 土壤温度模拟分析曲线  
Fig.4Simulated result of soil temperature at $1 0 \mathrm { ~ - ~ } \mathrm { c m }$ depth   
图5土壤热通量模拟分析曲线图Fig.5Simulated result of soil heat flux  
图6感热通量模拟分析曲线图  
Fig.6Simulated result of sensible heat flux   
图7净辐射模拟分析曲线图Fig.7Simulated result of net radiation

后的模拟结果有一定改善，绝对平均偏差减小$1 0 . 4 7 \mathrm { ~ W ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ,RMSE 减小 $1 5 . 7 5 \mathrm { ~ W ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ,但仍然高估。考虑到肖塘站长期没有降水，土壤极其干燥，由于石英的比热容小且热传导率较高，修正后土壤参数石英(QZT)成分减少，所以，表层混合土壤计算的热传导系数减小。根据土壤热通量计算公式（4)可知,导致土壤热通量高估减小的原因主要是土壤热力学参数的改变，减小了热量向下层土壤传递速度与热量。

# 3.4 感热通量

感热通量 $H$ 是地表能量传输的主要分量，是塔克拉玛干沙漠的主要热源，能反映出地面与大气之间的热量交换强度，是评价陆面过程模式模拟效果的关键物理量。从图6可知，感热通量模拟值均能够较好地反映其变化趋势，原始土壤参数的感热通量模拟值在中午有局部偏高，修正土壤参数后有微弱改善,绝对平均偏差减小了 $7 . 0 2 \mathrm { ~ W ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ,均方根误差和效率系数提升效果甚微，均没有反映出7月5日夜间感热通量的剧烈波动。测定土壤参数可知，土壤热传导系数有所减小,根据感热通量计算公式(3），沙漠区域的感热通量主要取决于地表温度和土壤温度差，由上已知，土壤温度的高估得到改善，因此，在正午时的感热通量高估有所降低。

H-Obs(观测) H-Org(原始)（-·M/ 400 H-Res(修正土壤参数后模拟)300 WMuuu200100001 2 8 4 0 6 ∠0- 8 0 107 7 7 7 0 7 7 7 07 7日期/月-日

# 3.5 净辐射

地表净辐射 $R _ { \mathrm { n e t } }$ 是地表吸收的太阳辐射能量，是估算地表能量平衡的关键要素，对天气/气候预测有重要的作用，也是评估太阳能资源的重要指标。图7为Noah净辐射模拟值与观测值对比曲线图，2组净辐射模拟值的变化趋势与观测值非常接近，但是原始土壤参数的模拟结果在正午有偏高，平均偏高 $5 0 \mathrm { ~ W ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ,修正土壤参数后的模拟结果改善了这种情况，其模拟结果基本和观测值吻合。从误差统计可知，修正土壤参数后净辐射模拟结果的绝对平均偏差减小了 $5 . 4 8 \mathrm { W } \cdot \mathrm { ~ m } ^ { - 2 }$ ,RMSE减小了16.31

1 $R _ { \mathrm { n e t } }$ -Obs(观测）— $R _ { \mathrm { n e t } }$ -Org(原始)(-W·M/t 600 1 $R _ { \mathrm { n e t } }$ -Res(修正土壤参数后模拟)450 MMMNM3001500-15001 2 8 44 05 6 0 8 9 17 0 7 7 7 07 7 7 7 7日期/月-日

$\mathbb { W } \cdot \textrm { m } ^ { - 2 }$ ,效率系数 NSE 达到更高的接受程度。干燥环境的潜热通量基本可以忽略，通过能量平衡公式(2)可知，净辐射结果取决于感热通量和土壤热通量的计算，因此，符合环境的土壤参数，有利于能量的准确估算。

# 3.6 小结

综合以上对土壤温度、土壤热通量、感热通量、净辐射的2组模拟结果分析，本次研究加入泰勒图对模型模拟性能进行了评估，泰勒图是一种能从多方面评估模型模拟性能的分析图，可以同时反映相关性和误差情况。图8为土壤参数修正前后Noah的模拟性能评估泰勒图，归一化标准差用直径表示，相关性用角度表示，当点越靠近横轴，则相关性越高。从图中可以看出，土壤温度改进效果最明显，感热通量提升效果甚微，土壤热通量模拟结果的相关性有降低。但是总体来看，模式对能量通量的模拟效果有改善，说明符合环境的土壤成分信息有助于提高模式模拟性能。

![](images/f7e2e04e642a1cf570881c82c52606c53eb12b156d3fdd51ade88a5db07a066f.jpg)  
图8泰勒图  
Fig.8Taylor diagram

（1）塔克拉玛干沙漠北缘沙漠土壤极其干燥，但其中不仅只有沙质，在 $0 \sim 3 0 ~ \mathrm { c m }$ 深度的浅层存在$10 \% \sim 2 4 \%$ 的黏土，石英的比例减小，根据沙和黏土成分比例重新计算土壤参数后发现，混合土壤的参数有较大差异，其中表层土壤热传导率减小，其他土壤水力学参数增大。

（2）在更新土壤参数表后，Noah模式对 $1 0 \ \mathrm { c m }$ 土壤温度的模拟效果有明显提升，修正后的土壤热传导率系数减小，改善了土壤温度在中午和夜间偏差较大现象，在这期间无降水，土壤水分基本没变化，土壤水力学参数的增大不会对热传输过程产生影响，说明模式默认的沙质土壤的热传导率偏高，修正后的土壤热传导率减小，能够减缓热量向下传递的速度，因此，减小了温度变化的振幅。

(3）更新土壤参数表后，表层土壤热传导系数有所减小，土壤热通量在修正土壤参数后的模拟结果一定程度上减小了中午模拟偏高的现象，表明土壤成分对热量向下传输有明显作用。正午时的感热通量高估有所降低，有微弱改善，但均方根误差和效率系数提升效果甚微，说明地表感热通量对土攘热力学参数不是非常敏感。另外，修正土壤参数后，净辐射模拟结果与观测值更加吻合，净辐射的模拟效果提升取决于感热通量和土壤热通量的结果。误差统计指标表明均有改进，因此，修正土壤参数更符合肖塘的环境，有利于提高地表能量平衡闭合率。

综上可知，模式默认每一类土壤为均质成分，真实环境中表层土壤一般会混合多种土壤成分，Noah模式的土壤参数表并不符合实际情况，本研究表明，更符合环境特征的土壤成分信息有助于提高模式对热传输模拟性能。但是大面积区域土壤属性的时空异质性测定通过剖面采样观测是不现实的，探索多光谱遥感和地面观测联合反演多种土壤参数是未来面向区域研究和应用的科学方法。

# 4结论

在陆面模式中土壤参数一般由参数表匹配，认为是均值类型的土壤，然而在实际中存在混合土壤类型情况较多，本文研究对肖塘的土壤成分采集和粒径分类，测定不同层的土壤成分和比例，根据沙和黏土成分比例重新计算了Noah的土壤参数，并利用该站的观测数据驱动作了2组陆面过程模拟和分析，得到以下几个结论：

# 参考文献（References）：

[1] Dickinson R E.Land-atmosphere interaction[J].Reviews of Geophysics,1995,33(33）:917 -922.   
[2] Chen F,Zhang Y.On the coupling strength between the land surface and the atmosphere:From viewpoint of surface exchange coefficients [J].Geophysical Research Letters,2009,36(36）:207 -213.   
[3] WeiJ,Dirmeyer P,Guo Z,et al.How much do different land models matter for climate simulation?Part I:Climatology and Variability[J].Journal of Climate,2010,23（11）:3135-3145.   
[4] Yang T,Wang X,Zhao C,et al.Changes of climate extremes in a typical arid zone: Observations and multimodel ensemble projections[J]. Journal of Geophysical Research Atmospheres,2011,116 (D19):106-124. [5]Rodwell MJ,Hoskins B J. Monsoons and the dynamics of deserts [J].Quarterly Journal of the Royal Meteorological Society,1996,   
122(534) :1 385 -1 404. [6]王超,韦志刚,李振朝,等.西北干旱区戈壁下垫面陆面过程特 征的模拟研究[J].太阳能学报,2016,37（9)：2422-2 429. [Wang Chao,Wei Zhigang,Li Zhenchao,et al. Simulation analysis of land surface process over Gobi at arid region Northwest China during summer[J]. Acta Energiae Solaris Sinica,2016,37（9）:   
2 422 -2 429.] [7]李万莉,吕世华,傅慎明,等.金塔绿洲的辐射平衡特征和地表 能量研究[J].太阳能学报,2009,30（12）:1614-1 620.[Li Wanli,Lu Shihua,Fu Shengming,etal.Astudyonradiation balance and surface energy in Jinta Oasis[J].Acta Energiae Solaris Sinica,2009,30(12):1 614 -1 620.] [8]Alkhaier F,Flerchinger G N,Su Z. Shallow groundwater effect on land surface temperature and surface energy balance under bare soil conditions:Modeling and description[J]. Hydrology and Earth System Sciences,2012,16(7):1 817 -1 831. [9]李火青,吴新萍,买买提艾力·买买提依明,等.塔克拉玛干沙 漠地表浅层土壤热扩散率、温度和热通量计算方法的比较研 究[J].土壤通报,2016,47（4）:805-813.［Li Huoqing,Wu Xinping,Ali Mamtimin,et al.Comparation between the diferent methods toestimate soil thermal diffusivity,temperature and heat Flux in Sub-surface of Taklimakan Desert[J].Chinese Journal of Soil Science,2016,47(4):805 - 813.] [10」郑辉,刘树华.沙漠陆面过程参数化与模拟[J].地球物理学 报,2013,56(7）:2 207-2 217.[Zheng Hui,Liu Shuhua.Land surface parameterization and modeling over desert[J]. Chinese Journal of Geophysics,2013,56(7):2 207-2 217.] [11]Liu YQ,He Q,Ali Mamtimin.Improving the CoLM in Taklimakan desert hinterland with accurate key parameters and an appropriate parameterization scheme[J]. Advances in Atmospheric Sciences,   
2012,29(2) :381 -390. [12］吴小波,南卓铜,王维真,等.基于 Noah 陆面过程模型模拟青 藏高原植被和土壤特征对多年冻土的影响[J].冰川冻土，   
2018,40（2）: 280- 286.[Wu Xiaobo,Nan Zhuotong，Wang Weizhen,et al.Simulation of the impact of vegetationand soil characteristics on permafrost over the Tibetan Plateau based on the Noah land surface model[J]. Journal of Glaciology and Geocryology,   
2018,40(2) :280 -286.] [13］何玉洁,宜树华,郭新磊.青藏高原含砂砾石土壤导热率实验 研究［J].冰川冻土,2017,39（2）:119－126.[He Yujie,Yi Shuhua,Guo Xinlei. Experimental study on thermal conductivity of soil with gravel on the Qinghai—Tibet Plateau[J]. Journal of Glaciology and Geocryology,2017,39(2）:119-126.]   
[14]Han X,Franssen H,Montzka C,et al.Soil moisture and soil properties estimation in the Community Land Model with synthetic brightness temperature observations[J]. Water Resources Research ,2014, 50(7) :6 081 -6 105.   
[15]Baroni G,Zink M,Kumar R,et al. Effects of uncertainty in soil properties on simulated hydrological states and fluxes at diferent spatio-temporal scales[J]. Hydrology & Earth System Sciences,， 2017,21(5) :1 -37.   
[16］曹寰琦,何清,金莉莉,等.塔克拉玛干沙漠北缘夏秋冬季地表 能量平衡闭合特征[J].干旱区研究,2018,35（4)：830－839. [Cao Huanqi,He Qing,Jin Lili,et al.Surface energy balance closure of summer,autumn and winter in the Northern Margin of Taklimakan Desert[J].Arid Zone Research,2018,35(4) :830 -839.]   
[17]Sun J.The age of the Taklimakan Desert[J].Science,2006,312 (5 780):1 621-1 621.   
[18]钱正安，宋敏红,李万元.近50 年来中国北方沙尘暴的分布及 变化趋势分析[J].中国沙漠,2002,22（2）：106-111.[Qian Zhengan,Song Minhong,Li Wanyuan,etal.Analysis of distribution and trend of sandstorm in North China in recent 5O years[J]. Journal of Desert Research,2002,22(2）:106 -111.]   
[19］魏文寿.沙漠气象学[M].北京：气象出版社,2008:197.[Wei Wenshou.Desert Meteorology[M].Beijing:Meteorological Publishing House,2008:197.]   
[20]金莉莉,李振杰,何清,等.CoLM模式对塔克拉玛干沙漠北缘 陆面过程模拟评估及修正[J].中国沙漠,2018,38（6）：173- 188.[Jin Lili,Li Zhenjie,He Qing,et al.Evaluation on modeling of land-atmosphere interaction in the Northern marginal zone of Taklimakan Desert with CoLM and correction[J]. Journal of Desert Research,2018,38(6) :173 -188.]   
[21]Chen F,Janji c Z,Mitchell K. Impact of atmospheric surface-layer parameterizations in the new land-surface scheme of the NCEP mesoscale Eta model[J].Boundary-Layer Meteorology,1997,85（3）： 391-421.   
[22]Chen F,Mitchell K,Schaake J,et al. Modeling of land surface - vaporation by four schemes and comparison with FIFE observations [J].Journal of Geophysical Research Atmospheres,1996,101 (D3) :7 251-7 268.   
[23]Bets A K.Assessment of the land surface and boundary layer models in two operational versions of the NCEP Eta model using FIFE data[J].Monthly Weather Review,1997,125（11）: 2 896- 2 916.   
[24]Schaake JC,Koren V,Duan QY,et al. Simple water balance model for estimating runoff at diffrent spatial and temporal scales[J]. Journal of Geophysical Research Atmospheres,1996,101（D3）: 7 461 -7 475.   
[25]Chen YY,Yang K,He J,et al.Improving land surface temperature modeling for dry land of China[J].Journal of Geophysical Research Atmospheres,2011.https://doi.org/10.1029/2011JD015921.

# Effects of Desert Soil Composition on Land Surface Processes

LI Huo-qing¹，JIN Li-li1， ALI Mamtimin’， ZHAO Jia-wei² (1.Institute of Desert Meteorology,China Meteorological Administration,Urumqi 83ooO2,Xinjiang,China; 2.Xinjiang Normal University,Urumqi 830013,Xinjiang,China)

Abstract:In this study,the values ofsoil compositionat Xiaotang Observation Station inthe northern margin of the Taklimakan Desert were measured by Mastersizer-2OOO Laser Particle Sizer and analyzed.Soil composition was clasified acording to the Wooden-Wendward Particle Size Standard.It was found that the soil was not the homogeneous sandy soil,and there was $10 \% - 2 4 \%$ clay in the shallow soil layer at $0 - 3 0 - \mathrm { c m }$ depth.The soil parameters in the Noah Land Surface Model were recalculated according to the proportions of soil compositions.The data observedatXiaotang Stationfrom March22to July25,2O1l were used todrivetheNoah model,andthesimulatedresults before and after amending the soil parameters were compared.The results showed that,after updating the soil parameters,the simulation efectof soil temperature was improved,thedeviations of soil temperature,soil heat flux, sensible heat flux and surface net radiation were reduced by $0 . 6 2 \mathrm { ~ \textcircled { C } , 1 0 . 4 7 \mathrm { ~ W } \cdot m \textsuperscript { - 2 } , 7 . 0 2 \mathrm { ~ W } \cdot m \textsuperscript { - 2 } }$ and 5.48 W $\cdot \mathrm { ~ m ~ } ^ { - 2 }$ respectively,and the effciency coefficient was more acceptable.The overalleffect of soil parameter modification for the Noah simulation wasanalyzed by Taylor diagram.Theresults showedthat the heat transferand difusion in the modified soil parameter model couldbe improved toacertain extent,andthe simulation effctof soil temperature could be improved obviously.

Key words:desert； soil composition； land process ；Noah model; Taklimakan Desert