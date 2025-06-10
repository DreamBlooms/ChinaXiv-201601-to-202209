# 基于CA-Markov模型的多时间跨度土地利用变化模拟

靳含,²，杨爱民,²，夏鑫鑫²，朱磊1,²，张青青}（1新疆农业大学草业与环境科学学院,新疆乌鲁木齐830052;2 新疆土壤与植物生态过程实验室,新疆乌鲁木齐830052)

摘要：土地利用/覆被变化（Land Use and Cover Change，LUCC)模拟是LUCC 研究的主要内容和重要手段。时间间隔是模拟过程中的重要参数，对模拟结果精度有何影响，有待深入研究。以新疆玛纳斯河流域典型绿洲区四道河子镇为例，基于遥感影像提取1975、1985、1995、2000、2005、2010年和2015年的土地利用数据,分别以20a、15a、10a和5a为时间间隔构建CA-Markov模型,模拟2015年土地利用结构，定量探讨时间间隔对CA-Markov模型精度的影响。结果表明：1975—2015年,四道河子镇LUCC 以耕地和草地为主,期间耕地、建设用地迅速扩张,林地、草地和未利用地大幅减少，水域在1985—2000年呈现小幅增长。耕地的增加和草地及林地的减少是研究区近40 aLUCC 最显著的特征。对比模拟结果与实际结果，时间间隔为 $2 0 \mathrm { ~ a ~ } , 1 5 \mathrm { ~ a ~ } , 1 0 \mathrm { ~ a ~ } , 5$ a的TFOM分别为$7 0 . 3 5 \%$ ,69. $18 \%$ ， $7 6 . 3 2 \%$ 和 $8 8 . 0 0 \%$ 。基于2005—2010年转移概率的模拟结果更接近于2015年实际结果，适合模拟四道河子镇未来的土地利用变化。土地利用模拟应依据区域LUCC特征确定最佳的时间间隔，提高模拟精度。

关键词：玛纳斯河流域；土地利用变化；CA-Markov；时间间隔文章编号： 1000-6060(2019)06-1415-12(1415\~1426)

土地利用/覆盖变化（LandUse andCoverChange，LUCC)是全球变化的主要组成，对全球气候变化、局地生态系统循环以及人类生存与发展具有重要影响，对其时空过程的量测和动力学机制的理解已经成为科学界关注的前沿内容[1-2]。土地利用过程模拟则成为LUCC研究的主要内容和定量探讨土地利用变化过程、驱动机制以及评估土地利用对生态环境影响的重要工具[3]。土地利用变化模拟方法日渐趋于多样化，主要包括：经验一统计模型，如马尔科夫（Markov）模型、逻辑回归（Logistic Re-gression）模型[4]等；动力学模型，如元胞自动机（Cellular Automata,CA)模型[5] 多智能体（Multi-A-gent System,MAS)模型[等;集成模型,如CLUE-S模型[7等;综合模型,如土地转换模型(Land Trans-formationModel)等[8]。这些方法在模拟不同时空尺度的LUCC时各有优势。其中，元胞自动机一马尔科夫(CA-Markov)模型结合了马尔科夫链长时间序列预测的能力和元胞自动机模拟复杂系统空间变化的优势[9],具有模拟动态、多情景LUCC 的能力和较好的模拟精度[10-12],被广泛应用于土地利用变化模拟与预测研究。

运用CA-Markov模型模拟土地利用变化，需先从两期历史土地利用数据中提取各地类的转换规则,进而预测未来某时刻的土地利用状态[13]。时间间隔是模拟过程中的重要参数之一[14],现有研究多将预测模拟时段与规则提取时段设置为相同，即基于过去 $k$ 年的土地利用变化特征预测未来 $k + 1$ 年的土地利用状态。也有研究通过对历史数据中土地利用转移概率进行内插来预测未来不同时间尺度的土地利用变化[15]。已有众多学者在不同区域内选择不同的时间跨度建立基于CA-Markov 的土地变化预测模型,预测时间间隔包括短期( $( 1 \sim 1 0 \mathrm { ~ a ~ } )$ [16]、中期 $( 1 0 \sim 2 0 \mathrm { ~ a ~ } )$ [17]和长期（20a以上）[18],模拟结果精度均能满足要求。但限于数据的可获取性，大部分研究中未对模拟过程中时间跨度的确定进行说明或探讨，不同的时间间隔对预测结果精度有何影响，有待深入研究。

新疆位于我国西北干旱区，区域内人工绿洲面积仅占 $9 \%$ ，但却集中了 $90 \%$ 以上的人口与 $9 5 \%$ 以上的社会财富[19],是干旱区的生命线和人类主要聚居区。玛纳斯河流域位于天山北麓中段，准噶尔盆地西南部，古尔班通古特沙漠南缘，从南到北呈现出典型的"山地一绿洲一荒漠”结构，土地利用程度总体呈北部沙漠区最低、中部绿洲区最高、南部山区居中的特点[20]。近40a来,大规模的水土开发使该流域土地利用发生显著变化，中部绿洲区扩张速度较快，成为新疆最大的绿洲农耕区和我国第四大灌溉农业区。但在人工绿洲扩张和农业发展的同时，生态环境问题也日益突出，破坏了绿洲生态安全和土地的可持续发展[20]。因此,研究和模拟预测玛纳斯河流域土地利用变化，为管理和规划该流域土地资源提供参考。鉴于此，本研究以玛纳斯河流域四道河子镇为例，基于多期遥感影像提取土地利用变化信息，以 $2 0 \textrm { a } , 1 5 \textrm { a } , 1 0$ a和5a为时间间隔，建立CA-Markov模型，模拟2015年该区域土地利用状态，并与实际结果对比，定量研究不同时间间隔对模拟精度的影响。

# 1研究区概况

四道河子镇( $4 4 ^ { \circ } 7 5 ^ { \prime } \sim 4 4 ^ { \circ } 8 3 ^ { \prime } \mathrm { ~ N ~ }$ $8 5 ^ { \circ } 6 7 ^ { \prime } \ \sim$ $8 5 ^ { \circ } 7 9 ^ { \prime } \mathrm { E }$ )地处玛纳斯河流域中部绿洲区，古尔班通古特沙漠南缘，东与老沙湾镇毗邻，西与农8师121团接壤，南接农8师144团，北至沙漠边缘，总面积为 $2 4 2 . 1 7 ~ \mathrm { k m } ^ { 2 }$ （图1)。该区域属大陆干旱性气候，夏季炎热干燥，冬季寒冷多风，年均降水 $1 3 4 ~ \mathrm { m m }$ ，年均温 $6 . 8 ~ \mathrm { { ^ { \circ } C } }$ ,年均蒸发量 $1 5 0 0 \sim 2 1 0 0 \mathrm { m m }$ ,年均风速 $1 . 7 \ : \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 。区域土地利用类型主要以耕地和草地为主,种植作物以棉花为主，经济发展较快[21]

![](images/0558026687181fcf57b8603507dfaa1a2182c4a531eb54230544d0e494347580.jpg)  
图1研究区位置  
Fig.1Location of the study area

# 2 数据与研究方法

# 2.1 数据来源与处理

本研究采用的数据包括1975年的Landsat-MSS影像，1985年、1995年的Landsat-TM影像，2000年、2005 年、2010 年的Landsat-ETM 影像和 2015 年的Landsat-OLI影像，成像时间均在7\~8月，影像云量少，质量较高。基于ENVI平台对影像进行辐射校正，MSS影像采取421波段假彩色合成，TM和ETM影像采用432波段假彩色合成，OLI影像采用543波段合成。用 $1 : 1 0 0 \ 0 0 0$ 地形图对2015年的OLI影像进行几何校正后作为参考图像，采用二次多项式转换方程对其它影像进行纠正，平均位置误差控制在0.5个象元以内，采用双线性内插法将图像重采样到 $3 0 \mathrm { ~ m ~ } \times 3 0 \mathrm { ~ m ~ }$ 。结合研究区实际情况和影像地物特征，将研究区土地利用类型划分为耕地L $\left( C _ { 1 } \right)$ ）、林地 $( C _ { 2 }$ ）、草地 $( C _ { 3 } )$ 、水域（ $C _ { 4 }$ )、建设用地$( C _ { 5 } )$ 和未利用地 $( C _ { 6 } ) 6$ 类。其中，水域包括天然陆地水域和水利设施用地，建设用地包括城乡、工矿、居民用地。通过人机交互解译，得到7期土地利用

数据(图2）。

# 2.2土地利用转移概率矩阵

土地利用转移矩阵能够反映区域在某一时段内各地类之间相互转化的动态过程[22],转移概率为该时段内某一土地利用类型转换为其他类型（或保持不变)的似然概率，可作为马尔科夫预测中的状态转移概率，计算公式[23如下：

$$
S _ { t + 1 } = P _ { i j } \times S _ { t }
$$

$$
\begin{array} { r c l c r c l } { { } } & { { } } & { { P _ { _ { 1 1 } } } } & { { \cdots } } & { { } } & { { P _ { _ { 1 n } } } } & { { } } \\ { { } } & { { } } & { { } } & { { } } & { { } } & { { } } \\ { { P _ { _ { i j } } = } } & { { \cdots } } & { { } } & { { \cdots } } & { { } } & { { \cdots } } & { { 0 \leqslant P _ { _ { i j } } < 1 } } \\ { { } } & { { } } & { { } } & { { } } & { { } } & { { } } \\ { { } } & { { } } & { { \cdots } } & { { } } & { { P _ { _ { n n } } } } & { { } } \end{array}
$$

$$
\exists \sum _ { j = 1 } ^ { n } \ P _ { i j } \ = 1 ( i , j \ = 1 , 2 , \cdots , n )
$$

式中： $\boldsymbol { S } _ { t } \setminus \boldsymbol { S } _ { t + 1 }$ 为 $\smash { t _ { \perp } t + 1 }$ 时刻的土地利用状态； $P _ { \it i j }$ 为状态转移概率矩阵； $n$ 为土地利用类型

将1975—2015年划分为4种不同的时间间隔$T _ { i }$ ,分别为长期（1975—1995—2015年， $T _ { \scriptscriptstyle 1 } = 2 0$ ）、中期（1985—2000—2015 年， $T _ { \scriptscriptstyle 2 } \ = \ 1 5$ ；1995—2005—2015年， $T _ { \scriptscriptstyle 3 } \ = \ 1 0$ ）和短期（2005—2010—2015 年，$T _ { \scriptscriptstyle 4 } = 5$ ），基于不同时间间隔下土地利用数据提取各时段土地利用类型的转移概率，作为模拟的参数，分别模拟2015年土地利用状态。

![](images/35280df03225d165264c6f7a28963673a606ea4b1c1d7c4428c9e042880302b0.jpg)  
图2四道河子镇土地利用解译图  
Fig.2Interpretation maps of land use in Sidaohezi Town

# 2.3 土地利用动态度

土地利用动态度反映一定时段内各土地类型的变化幅度和速度，有助于了解区域LUCC的总体态势和结构变化。计算公式[23]如下：

$$
K = \frac { U _ { b } - U _ { a } } { U _ { a } } \times \frac { 1 } { T } \times 1 0 0 \%
$$

式中： $K$ 为研究时段内某一土地利用类型的动态度；$U _ { a }$ 和 $U _ { b }$ 分别为研究期始、末某一种土地利用类型的面积； $T$ 为研究时段。

# 2.4 CA-Markov模型

马尔科夫模型通过系统当前的状态及其变化概率预测该系统未来的状态，其核心是不同时期土地利用类型之间的转移概率。元胞自动机是一种时间、空间、状态都离散，空间相互作用和时间因果关系都为局部的网络动力模型，通过设定元胞、元胞空间、元胞状态、邻域和转换规则等来控制土地利用变化模拟过程[24] C

本研究利用IDRISI平台的Markov模块和CA-Markov 模块，基于1975—1995年、1985—2000 年、1995—2005 年和 2005—2010 年的土地利用转移概率,分别以 $1 9 9 5 \ 、 2 0 0 0 \ 、 2 0 0 5 \ 、 2 0 1 0$ 年为初始年,以20a、15a、10a和5a为时间间隔模拟2015年的土地利用状态，并与2015年实际土地利用状态进行对比分析。CA-Markov模型中设置元胞大小为 $3 0 \mathrm { ~ m ~ } \times 3 0 \mathrm { ~ m ~ }$ ,滤波器大小为 $5 \mathrm { ~ m ~ } \times 5 \mathrm { ~ m ~ }$ ,循环次数分别为 $2 0 , 1 5 , 1 0 , 5$ ○

# 2.5 精度检验

2.5.1解译精度检验研究选取Kappa系数检验遥感影像分类精度，计算公式如下：

$$
K a p p a = \frac { P _ { c } - P _ { o } } { P _ { p } - P _ { c } }
$$

式中： $\boldsymbol { P } _ { c }$ 为随机情况下期望的正确模拟比例； $\boldsymbol { P } _ { o }$ 为正确模拟的比例； $\boldsymbol { P } _ { \boldsymbol { p } }$ 为理想分类情况下的正确模拟比例。如果两个土地利用变化图像完全一样，则$K a p p a = 1$ ；当 $K a p p a \geqslant 0 . 7 5$ 时,表明一致性较高,误差较小;当 $K a p p a { \leqslant } 0 . 4$ 时，一致性较差,两幅图相差较大[25]。

1975年、1985年和1995年的解译结果分别采用20世纪70年代的 $1 : 4 7 \ 0 0 0$ 黑白航片、80年代和90年代的彩色航片和地形图进行检验;2000 年、2005年、2010年、2015年解译结果经野外调查和GoogleEarth历史高空间分辨率影像检验。本文依据研究区土地利用类型的空间分布特征，选取分层随机抽样方法[26],在各期土地利用分类图上抽取100 个样点，分别与上述参考数据进行比较，并将解译结果中正确和错误的样点数代入公式（4），得到各期Kappa系数分别为0.78、0.76、0.77、0.76、0.79、0.81和0.84，满足土地利用变化研究的需求[27]。

2.5.2模拟结果精度检验研究时段内，区域土地利用类型是否发生变化是LUCC研究关注的重点，也是评价模拟精度的重要依据。FOM（FigureofMerit)指数在LUCC研究中主要用于针对某一区域、某一时段内实际发生变化部分的模拟精度进行评价，并能够通过对实际变化部分和模拟变化部分进行比较，定量分析模拟结果和实际结果的一致性构成[28],但缺乏对实际未变化部分模拟精度的验证。为评价区域土地利用变化模拟的整体精度，本研究在FOM基础上加入针对实际未变化区域的模拟结果，采用TFOM(TotalFigureofMerit)指数作为评价模拟结果的标准。该指数为研究时段内模拟结果和实际结果一致的部分与总体模拟结果的比值，取值范围为 $0 \sim 1 0 0 \%$ ，0表示实际结果与模拟结果没有重叠部分， $100 \%$ 表示实际结果与模拟结果完全重合，计算公式如下：

$$
T F O M = \left( S _ { 1 } + S _ { 2 } \right) \bigg / \left( S _ { 1 } + S _ { 2 } + S _ { 3 } + \right.
$$

$$
S _ { 4 } + S _ { 5 } ) \times 1 0 0 \%
$$

式中： $S _ { 1 }$ 指某区域在某时段内土地利用类型未发生变化，且模拟结果和实际结果一致； $S _ { 2 }$ 指实际土地利用类型发生变化，且模拟结果和实际结果一致； $S _ { 3 }$ 指实际土地利用类型发生变化，但模拟结果和实际结果的转换地类不一致; $S _ { 4 }$ 指实际土地利用类型发生变化，但模拟结果未变化； $S _ { 5 }$ 指实际土地利用类型未发生变化，但模拟结果发生变化。以时间间隔 20a（1975—1995—2015年）为例，1995年作为预测起始年，土地利用状态为a,模拟结果和实际结果也为a,此种情况！ $( S _ { 1 } )$ 正确；1995作为预测起始年，土地利用状态为a,模拟结果为b,实际结果为a,此种情况 $( S _ { 4 } )$ 错误，其它依此类推，具体见表1。

# 表1土地利用变化模拟结果和实际结果的一致性构成 表2四道河子镇不同时期土地利用结构 $/ \left| \mathbf { k m } ^ { 2 } \right.$

Tab.1 Agreement component of simulated results and observed results of land use change   

<html><body><table><tr><td>构成</td><td>初始状态</td><td>实际结果</td><td>模拟结果</td><td>备注</td></tr><tr><td>S</td><td>a</td><td>a</td><td>a</td><td>模拟正确</td></tr><tr><td>S2</td><td>a</td><td>b</td><td>b</td><td></td></tr><tr><td>S</td><td>a</td><td>b</td><td>c</td><td>模拟错误</td></tr><tr><td>S4</td><td>a</td><td>b</td><td>a</td><td></td></tr><tr><td>S</td><td>a</td><td>a</td><td>b</td><td></td></tr></table></body></html>

注： ${ \bf a } , { \bf b } , { \bf c }$ 为不同的土地利用类型

# 3结果

# 3.1 土地利用变化

3.1.11975—2015年土地利用动态变化特征近40a来,四道河子镇主要以耕地和草地为主,各时期二者之和占比均在 $80 \%$ 之上,2015 年达到 $9 2 . 9 3 \%$ 0该区域土地利用/覆盖在各时期呈现出不同的变化特征,主要表现为耕地、建设用地的增加和草地、水域及未利用地的减少。其中，耕地增加幅度较大，从1975年的 $4 2 . 6 6 \%$ 增加到2015年的 $7 6 . 6 0 \%$ ，建设用地则从1975年的 $2 . 0 7 \%$ 增加到2015年的 $4 . 8 \%$ 0草地减少幅度较大，从1975 年的 $3 7 . 7 6 \%$ 减少到2015年的 $1 6 . 3 3 \%$ ,林地从1975年的9. $61 \%$ 减少到2005年的 $1 . 5 8 \%$ ，水域和未利用地分别从1975年的 $3 . 5 6 \%$ 和 $4 . 3 4 \%$ 减少到2015年 $0 . 1 5 \%$ 和 $1 0 . 5 4 \%$ (表2）。

四道河子镇不同时期内的各地类动态度存在明显的差异。耕地动态度变化在整个时期内呈现“两头高、中间低”的特征，1985—2000 年最低，2005—2010 年为最高;林地的动态度处于先减少后增加的过程,其2005—2010 年的动态度为各土地利用/覆被类型中最高；草地的动态度在1995—2005年最小，2005一2010年变化最大；水域的动态度先减少后增加，变化幅度在2005—2010年最大;建设用地动态度变化在研究期初和期末最高，1995—2005 年的动态度变化最小;未利用地动态度的幅度为前两期增加、后两期减少，且1995一2005年变化幅度最大。在整个研究时段,耕地、水域和建设用地的变化幅度在研究始末两端较大，土地利用变化较剧烈;草地和林地在2005—2010 年变化较剧烈;未利用地在1995—2005年变化幅度较大（图3）。

Tab.2Land use structure of different periods in Sidaohezi Town／ $\mathbf { k m } ^ { 2 }$   

<html><body><table><tr><td>年份</td><td>C1</td><td>C</td><td>C</td><td>C4</td><td>C5</td><td>C6</td></tr><tr><td>1975</td><td>103.32</td><td>23.27</td><td>91.44</td><td>8.62</td><td>5.01</td><td>10.51</td></tr><tr><td>1985</td><td>122.21</td><td>17.30</td><td>85.69</td><td>2.14</td><td>5.93</td><td>8.90</td></tr><tr><td>1995</td><td>135.23</td><td>13.66</td><td>72.03</td><td>2.33</td><td>8.14</td><td>10.78</td></tr><tr><td>2000</td><td>138.05</td><td>13.69</td><td>69.20</td><td>2.16</td><td>8.53</td><td>10.54</td></tr><tr><td>2005</td><td>155.34</td><td>6.54</td><td>66.95</td><td>1.92</td><td>8.94</td><td>2.48</td></tr><tr><td>2010</td><td>179.59</td><td>3.58</td><td>45.12</td><td>1.20</td><td>10.68</td><td>2.00</td></tr><tr><td>2015</td><td>185.50</td><td>3.82</td><td>39.55</td><td>0.37</td><td>11.63</td><td>1.30</td></tr></table></body></html>

注： $C _ { 1 }$ -耕地， $C _ { 2 }$ -林地， $C _ { 3 }$ -草地, $C _ { 4 }$ -水域, $C _ { 5 }$ -建设用地, $C _ { 6 }$ 1未利用地

3.1.2不同时间间隔的土地利用变化转移概率研究基于Markov模型得到不同时间间隔下各地类的转移面积和概率，能够定量地分析和深入了解各类土地利用转移面积矩阵、土地利用类型的转移方向及补充来源，了解研究区土地利用时空演变的过程。

从表3可知，整个时期耕地的净增面积比例最大，主要由草地转入，是区域主要的土地转移类型。草地呈递减态势，从1975年的 $9 1 . 4 4 ~ \mathrm { k m } ^ { 2 }$ 下降至2015的 $3 9 . 5 5 \mathrm { k m } ^ { 2 }$ 。1975—1995年、1985—2000

![](images/4d5dbb6e64d9d5b57334b804d63b2482bbd4a7d906631f750b36499ed8244a9a.jpg)  
图31975—2010 年四道河子镇土地利用变化动态度  
Fig.3Land use change dynamic degree of Sidaohezi Town from 1975 to 2010

# 干旱区地理

表3不同时段四道河子镇土地利用概率转移矩阵  
Tab.3 Transition probability matrix of land use types in Sidaohezi Town during different periods   

<html><body><table><tr><td>时间间隔</td><td>土地利用类型</td><td>C</td><td>C</td><td>C3</td><td>C4</td><td>C5</td><td>C6</td></tr><tr><td>1975—1995 年</td><td>C1</td><td>0. 946 7</td><td>0.0017</td><td>0.0411</td><td>0.001 4</td><td>0.006 7</td><td>0.002 4</td></tr><tr><td rowspan="8">1985—2000 年</td><td>C2</td><td>0.320 7</td><td>0.440 1</td><td>0.156 5</td><td>0.0060</td><td>0. 0431</td><td>0.033 6</td></tr><tr><td>C</td><td>0. 253 7</td><td>0.027 9</td><td>0.671 7</td><td>0.004 0</td><td>0.013 7</td><td>0.029 0</td></tr><tr><td>C4</td><td>0.514 3</td><td>0.050 4</td><td>0.187 3</td><td>0.230 0</td><td>0.000 0</td><td>0.0181</td></tr><tr><td>C5</td><td>0.000 0</td><td>0.000 0</td><td>0.000 0</td><td>0.000 0</td><td>1.000 0</td><td>0.000 0</td></tr><tr><td>C6</td><td>0.198 6</td><td>0.0203</td><td>0.145 4</td><td>0.000 0</td><td>0.013 3</td><td>0.622 4</td></tr><tr><td>C1</td><td>0.9108</td><td>0.022 9</td><td>0.054 6</td><td>0.001 2</td><td>0.005 7</td><td>0.004 9</td></tr><tr><td>C</td><td>0.216 7</td><td>0.537 0</td><td>0.119 2</td><td>0.0038</td><td>0. 050 9</td><td>0. 072 5</td></tr><tr><td>C</td><td>0. 253 4</td><td>0.0178</td><td>0.688 0</td><td>0.003 5</td><td>0.005 4</td><td>0.0318</td></tr><tr><td rowspan="6">1995—2005 年</td><td>C4</td><td>0. 014 7</td><td>0.000 0</td><td>0.128 7</td><td>0.856 6</td><td>0.000 0</td><td>0.000 0</td></tr><tr><td>C5</td><td>0.000 0</td><td>0.000 0</td><td>0.005 5</td><td>0.000 0</td><td>0. 994 5</td><td>0.000 0</td></tr><tr><td>C6</td><td>0.163 4</td><td>0.007 4</td><td>0.125 6</td><td>0.000 0</td><td>0.015 7</td><td>0. 687 9</td></tr><tr><td>C1</td><td>0.958 6</td><td>0.000 7</td><td>0.034 7</td><td>0.000 0</td><td>0.0041</td><td>0.0019</td></tr><tr><td>C</td><td>0.332 5</td><td>0.389 5</td><td>0.2660</td><td>0.000 0</td><td>0.012 0</td><td>0.000 0</td></tr><tr><td>C</td><td>0.235 1</td><td>0.008 6</td><td>0.7434</td><td>0.0011</td><td>0.002 4</td><td>0.009 4</td></tr><tr><td rowspan="8">2005—2010 年</td><td>C4</td><td>0.136 6</td><td>0.028 0</td><td>0.111 8</td><td>0.723 6</td><td>0.000 0</td><td>0.000 0</td></tr><tr><td>C5</td><td>0.010 1</td><td>0.0041</td><td>0.017 2</td><td>0.000 0</td><td>0.968 6</td><td>0.000 0</td></tr><tr><td>C6</td><td>0.399 7</td><td>0.038 7</td><td>0.404 4</td><td>0.000 0</td><td>0.013 4</td><td>0.1438</td></tr><tr><td>C1</td><td>0.950 7</td><td>0.0058</td><td>0.029 7</td><td>0.002 9</td><td>0.004 5</td><td>0.006 4</td></tr><tr><td>C</td><td>0.429 3</td><td>0.286 6</td><td>0.221 5</td><td>0.000 0</td><td>0. 053 8</td><td>0.0088</td></tr><tr><td>C</td><td>0.392 6</td><td>0.0111</td><td>0.542 8</td><td>0.005 8</td><td>0. 035 7</td><td>0.012 0</td></tr><tr><td>C4</td><td>0.214 0</td><td>0.016 5</td><td>0.522 6</td><td>0.222 2</td><td>0.016 5</td><td>0.008 2</td></tr><tr><td>C5</td><td>0.095 2</td><td>0.0009</td><td>0.000 0</td><td>0.000 0</td><td>0.903 9</td><td>0.000 0</td></tr><tr><td></td><td>C6</td><td>0.6318</td><td>0.0101</td><td>0.3311</td><td>0.0000</td><td>0.0101</td><td>0.0169</td></tr></table></body></html>

年、1995—2005 年和 2005—2010 年草地减少面积分别为 $1 9 . 4 1 \ \mathrm { k m } ^ { 2 } \setminus 1 6 . 4 9 \ \mathrm { k m } ^ { 2 } \setminus 5 . 0 8 \ \mathrm { k m } ^ { 2 }$ 和22.78$\mathrm { k m } ^ { 2 }$ 。减少的草地主要转移为耕地,反映了土地需求类型的改变，且各时段的转移概率分别为$2 5 . 3 7 \% . 2 5 . 3 4 \% . 2 3 . 5 1 \% . 3 9 . 2 6 \%$ 。林地面积呈下降趋势，转出面积主要流入耕地,40a间的转移概率在 $2 1 \% \sim 4 3 \%$ 之间。水域的面积先减后增再减，在1975—1995 年、1995—2005 年和2005—2010 年，水域面积变化幅度较大，主要转为耕地且转移状态概率分别为 $5 1 . 4 3 \% . 1 3 . 6 6 \% . 2 1 . 4 0 \%$ 。在城市化的推动下，建设用地持续扩张，主要由草地转化而来。未利用地主要转化为耕地和草地，在整个研究时段，二者的转移概率超过 $30 \%$ ,其中 2005—2010年的转移概率达到 $9 6 . 2 9 \%$ ，在该时期变化剧烈且达到最高值。

# 3.2 土地利用变化模拟

分别将1995、2000、2005年和2010年作为起始年，基于1975—1995年、1985—2000 年、1995—2005年和2005—2010年土地利用变化数据中提取的 4个时段内土地利用转移概率作为转换规则，模拟

20a、15a、10a和5a时间间隔条件下四道河子镇  
2015 年的土地利用空间格局 $( R _ { 1 } \ 、 R _ { 2 } \ 、 R _ { 3 } \ 、 R _ { 4 } )$ ，并与  
2015年实际结果 $( R )$ 进行比较，模拟结果见图4。

基于不同时间间隔的模拟结果与2015年实际土地利用现状之间存在差异（图4、图5）。 $R _ { 1 } , R _ { 2 }$ 、$R _ { 3 }$ 模拟结果中各地类面积与实际结果差异较大，耕地差异分别为 $3 0 . 8 8 \ \mathrm { k m } ^ { 2 } \ 、 3 6 . 8 3 \ \mathrm { k m } ^ { 2 }$ 和 $1 6 . 7 9 \ \mathrm { k m } ^ { 2 }$ ，草地为 $1 8 . 5 5 \ \mathrm { k m } ^ { 2 } \setminus 1 8 . 6 8 \ \mathrm { k m } ^ { 2 }$ 和 $1 8 . 3 1 ~ \mathrm { k m } ^ { 2 }$ ,未利用土地为 $7 . 8 7 \ \mathrm { k m } ^ { 2 } \ . 9 . 8 6 \ \mathrm { k m } ^ { 2 }$ 和 $0 . 0 6 \ \mathrm { k m } ^ { 2 }$ ,林地、水域和建设用地的变化差异较小。 $R _ { 4 }$ 模拟结果与2015年土地利用实际结果最为接近，各地类面积差异分别为 $7 . ~ 7 0 ~ \mathrm { { \ k m } ^ { 2 } \setminus 1 . ~ 2 8 ~ \mathrm { { \ k m } ^ { 2 } \setminus 8 . ~ 7 7 ~ \mathrm { { \ k m } ^ { 2 } \setminus 0 . ~ 7 0 ~ \mathrm { { \ k m } ^ { 2 } \setminus 0 . ~ } } } }$ $1 . 2 4 ~ \mathrm { k m } ^ { 2 }$ 和 $0 . 4 1 ~ \mathrm { k m } ^ { 2 }$ 。结果表明随着时间间隔的缩小，土地利用模拟精度随之增加。其中，各土地利用类型的模拟精度存在差异，耕地和草地在所有类型中模拟精度较低，其变化幅度差异均在 $2 0 ~ \mathrm { k m } ^ { 2 }$ 和16$ { \mathrm { k m } } ^ { 2 }$ ,由于耕地和草地受人类活动影响较多，驱动因素较复杂，精度随之降低。林地、水域、未利用地的模拟结果较稳定，误差比例均在 $5 \%$ 以内。建设用地的模拟精度均超过 $8 0 \%$ ,模拟效果较好。

![](images/29d90c1db6ed7fa98a6348c5442c9023405f2dad9dd775528a17a41f3323ca68.jpg)  
图42015年四道河子镇实际与模拟土地利用现状图

![](images/bbce0940604a7e313baa2e07509465ff37e0c25d8d1682cfcc0ed92092612d08.jpg)  
Fig.4Observed and simulated land use map of Sidaohezi Town in 2015   
图5四道河子镇2015年土地利用真实与模拟面积比  
Fig.5Observed and simulated area ratio of land use in Sidaohezi Town in 2015

2015年土地利用现状与模拟结果进行比较，验证不同时间间隔的模拟精度。结果表明： $R _ { 1 } , R _ { 2 }$ 、$R _ { 3 } \ 、 R _ { 4 }$ 的TFOM为 $7 0 . 3 5 \%$ 、69. $18 \%$ 、 $7 6 . 3 2 \%$ 和$8 7 . 7 0 \%$ 。CA-Markov模型可以用来模拟预测四道河子镇的土地利用空间分布。此外， $R _ { 4 }$ 模拟结果和实际土地利用类型分布有着较高的一致性，误差较小，可见,短期时间间隔更适合模拟四道河子镇的土

地利用变化。

4种时间间隔模拟结果 $\mathbf { \Phi } ( R _ { i } )$ 的一致性构成 $( S _ { i } )$ 在数量、空间分布上存在较大差异。从图6可知， $R _ { 1 }$ 中的 $S _ { 1 }$ 和 $S _ { 2 }$ 分别为 $6 5 . 4 0 \%$ 和 $4 . 9 4 \%$ ， $S _ { 3 } \setminus S _ { 4 }$ 和 $S _ { 5 }$ 分别为 $2 . 9 7 \%$ （20 ${ , 2 0 . 8 9 \% }$ 和 $5 . 8 0 \%$ $R _ { 2 }$ 中的 $S _ { 1 }$ 和 $S _ { 2 }$ 分别为66. $30 \%$ 和2. $89 \%$ ， $S _ { 3 } , S _ { 4 }$ 和 $S _ { 5 }$ 分别为$2 . 9 0 \%$ 、21. $18 \%$ 和 $6 . 7 4 \%$ ： $R _ { 3 }$ 中的 $S _ { 1 }$ 和 $S _ { 2 }$ 分别为

![](images/bfb7669d33a149a3ba63011be32855a88a9984456dc06aabc6f8db1605a5d967.jpg)  
图6四道河子镇土地利用一致性和不一致性模拟图  
Fig.6Map representation of agreement and disagreement components in Sidaohezi Town

$7 3 . 3 3 \%$ 和 $2 . 3 0 \%$ ， $S _ { 3 }$ 、 $S _ { 4 }$ 和 $S _ { 5 }$ 分别占 $1 . \ 0 4 \%$ 、$1 6 . 1 1 \%$ 和 $6 . 5 4 \%$ 。 $R _ { 1 } , R _ { 2 }$ 和 $R _ { 3 }$ 的构成模式相似，$S _ { 4 }$ 所占比例较高且分布在四道河子镇的东北区域,由于耕地受人类活动、社会经济发展影响，草地、未利用地多转为耕地,在预测过程中未模拟出此种情况； $R _ { 4 }$ 中 $S _ { 1 }$ 和 $S _ { 2 }$ 分别为 $8 7 . 4 3 \%$ 和 $0 . 2 7 \%$ ， $S _ { 1 }$ 为各模拟结果中最大, $S _ { 3 } , S _ { 4 }$ 和 $S _ { 5 }$ 分别为0. $2 7 \%$ 、$2 . 7 3 \%$ 和 $9 . 3 0 \%$ ， $S _ { 5 }$ 所占比例较大，提取转换规则发展过程快于预测模拟阶段，转移概率过大造成模拟结果较差，如草地大部分转为耕地，但没有考虑该地区水资源是否满足耕地的扩张，与研究区现实情况存在差异。

# 4讨论

（1）绿洲是干旱区生态系统结构的核心，玛纳斯河流域人工绿洲位于天山北坡经济带，是新疆绿洲区的重要组成部分，而绿洲的稳定性和可持续发展一直是需要解决的关键科学问题之-[29]1975一2015年，玛纳斯河流域LUCC发生了显著变化，尤以耕地的增加和林地、草地的减少为其最明显的特征。随着区域经济社会的迅速发展，玛纳斯河流域的绿洲农业耕作区扩张活动导致土地利用发生了显著变化[30]。过度的人类活动,使得大量自然资源被不合理地开采和利用，导致玛纳斯河流域生态环境发生了巨大变化。其中，耕地面积扩张过快、水资源过度开采、山区林地与草地面积退化及土壤污染加剧等不当的人类活动，对玛纳斯河流域土地的可持续发展造成严重的影响[31]。因此,在未来的土地利用开发过程中，要适度地控制耕地的无序扩张，合理地优化配置耕地资源，促进玛纳斯河流域的可持续发展。

（2）LUCC是典型的时空变化过程，时间间隔是基于CA-Markov 的LUCC 模拟的重要参数之一。现有大部分研究多是依据现有遥感数据确定模拟时段，而较少考虑某时段区域LUCC特征是否与该区域未来变化相吻合。本研究采用长期、中期和短期3种时间间隔来模拟区域LUCC，结果表明时间间隔为5a的模拟结果优于其它，即在模拟目标年确定的前提下，较短的时间间隔能够更为精准地反映LUCC的特征与趋势，模拟精度随着模拟时间间隔的增加而降低,SAMAT等[32]的研究结果也证实了这一点。

政策。近40a间玛纳斯河流域土地利用发生了较大的变化，不同时段内的变化幅度有所差异。1975—1995年,林地、草地和未利用地变化幅度相对较小,期间该流域水土开发规模急剧下降,工农业结构调整,耕地扩张缓慢;建设用地变化幅度较大,1978 年工业发展迅速，人口增长过快,建设用地随之增加[33]。该时期土地利用变化特征和 1995-2015 年的发展过程不同,导致转换类型不一致，模拟精度较低。1985—2000 年耕地、林地和水域变化幅度在整个时期最小,由于城市化进程加快,耕地面积扩张速率减缓[34];草地和未利用地变化幅度较平缓,该时期流域实行毁草开荒政策[31],草地和未利用地相互转换,变化幅度较一致。与2000—2015 年变化幅度相比，1985—2000 年各土地利用类型变化幅度整体趋于缓慢,转换概率不一致导致结果偏低。1995—2005 年,林地和未利用地变化幅度较大，草地和建设用地在整个时期变化幅度最小,2000 年草场面积逐年下降,过度放牧导致草场严重退化;以裸地开垦或弃耕地收复为主,耕地弃耕后主要转移为盐碱地草地[35]。耕地和水域的变化幅度较平缓，由于土地利用范围继续扩张,开始有计划地开发水资源,农田灌溉以集约、内涵挖潜为主[36]。耕地、草地在该时期与 2005—2015 年面积变化的差异造成模拟精度较低。2005—2010 年耕地、林地、草地、水域和建设用地在4个时期内变化幅度最大,由于2000—2015年“三生用地"政策的实施造成，该时期玛纳斯河流域的生态用地(林地、草地和未利用地)和生产生活用地(耕地和建设用地)所占的面积较大，且两者之间发生剧烈的相互转移，生态用地减少,生产生活用地快速增加[37],造成 2005—2010 年和 2010—2015 年土地利用转换类型和速率较一致、模拟结果精度高的原因。基于长期和中期的转移概率,模拟精度会降低,并与实际结果差异明显。不同时间尺度土地利用变化过程各异,模拟时间间隔的确定应以区域土地利用的变化幅度、速度和研究区的开发力度、发展政策等为基准。此外,不同土地利用类型的模拟精度会有所差别,部分土地利用类型的模拟精度较高[38],如林地、建设用地和水域等,这类土地变化幅度相对较稳定,而耕地和草地的变化很复杂,受人类活动、政策等因素影响较大，所以该土地类型模拟结果的误差相对较大，ONAT-EVALDIVIESO 等[39]也提到过此种情况。

（3）LUCC过程往往受自然条件、社会经济和人类活动等因素共同影响，部分因素既难量化又具有不确定性[40]。本研究关注时间跨度对CA-Mark-ov模型的影响，但驱动土地利用变化的其它因素也不容忽视。例如水资源是干旱区土地可持续发展的重要制约因素，有限的水资源数量和分布状况是控制景观荒漠化和绿洲化进程的主导因子,是干旱地区最为活跃的自然因素，对土地开发利用起着重要的作用[41]。1950 年起,玛纳斯河流域水利工程修建和灌溉方式不断改进，绿洲迅速扩张。水资源（人工渠系）在1987—1998 年增长速度最快，1998年以后由于节水滴灌技术的推广,耕地面积持续扩张,水域面积有所减少[31]。随着玛纳斯河流域耕地规模的不断扩大，对农业用水的需求量也随之增加，在未来一段时间水资源将处于严重的超负荷运行状态。CA-Markov 模型是一种基于转换概率的预测模型,没有考虑耕地扩张与水资源总量之间的联系，若仅按照转换概率进行模拟,未来区域内耕地将不断扩张，林地和草地所需的水资源将无法保证,这会对生态环境产生难以估计的影响[20,42],这是不符合实际的。CA-Markov 模型虽然可以较好地模拟四道河子镇的土地利用变化过程,但在建模过程中如缺少对社会、经济等因素的考虑，加上遥感影像空间分辨率和解译精度的影响，在一定程度上制约了模型模拟结果的精度。因此LUCC模拟还要结合研究区的实际情况和限制因素等，才能进一步提高模拟精度，得到更为接近实际的结果。

# 5结论

研究以玛纳斯河流域四道河子镇为例,基于1975、1985、1995、2000、2005、2010、2015年7期土地利用数据，运用马尔科夫转移矩阵和土地利用变化动态度模型，对新疆典型绿洲区玛纳斯河流域四道河子镇近40a土地利用变化过程进行定量分析，并以不同时间间隔构建CA-Markov模型，模拟2015年土地利用结构，经与实际数据对比定量探讨时间间隔对CA-Markov模型精度的影响。结论如下：

（1）近 $4 0 \mathrm { ~ a ~ }$ 来，四道河子镇的耕地面积大幅增加,1975—2015 年增加了 $8 2 . 1 8 ~ \mathrm { k m } ^ { 2 }$ ,在所有土地利用类型中变化最为显著。林地、水域和未利用地经历了“减少一增加一减少”的变化过程，净面积减少。草地呈现持续减少的态势，,而建设用地持续增加。整个研究时段，耕地和草地始终是研究区所占比例最大的两种土地利用类型，且二者之间的相互转换较频繁。

（2）研究以20a、15a、10a和5a的时间跨度提取土地利用转移概率，分别构建CA-Markov模型模拟2015年四道河子镇土地利用变化。结果显示随着时间间隔的缩小，模拟精度逐渐增加，基于2005一2010年的土地利用转移概率模拟的2015年土地利用结果更接近于实际情况。（3）基于CA-Markov模型，通过定量分析，探讨了土地利用变化模拟过程中时间间隔的选择( $2 0 \textrm { a } .$ $1 5 \mathrm { ~ a ~ } , 1 0 \mathrm { ~ a ~ } , 5 \mathrm { ~ a ~ } ,$ )对于模拟精度的影响，为土地利用变化模拟中时间间隔的选择提供了一定的科学依据。土地政策在社会发展的各阶段是有差异的，不同政策会导致土地利用方式发生不同的转换变化。因此，在今后的土地利用预测建模中，时间跨度的选择还应考虑该地区的历史发展过程，依据不同时期的开发特征，参照研究区的现实状况和限制因素等，确定最佳的模拟时间间隔，以提高区域土地利用变化模拟的精度。

# 参考文献(References)

[1]FOLEY JA,DEFRIESR,ASNERGP,etal.Global consequences of land use[J].Science,2005,309(5734）:570-574.   
[2]刘纪远,宁佳,匡文慧,等.2010—2015 年中国土地利用变化的 时空格局与新特征[J].地理学报，2018，73（5）：789-802. [LIUJiyuan,NING Jia,KUANGWenhui,et al.Spatio-temporal patterns and characteristics of land-use change in China during 2010—2015[J].Acta Geographica Sinica,2018,73（5）:789 - 802.]   
[3] 李少英,刘小平,黎夏,等.土地利用变化模拟模型及应用研究 进展［J].遥感学报,2017,21（3）:329-340.［LI Shaoying,LIU Xiaoping,LI Xia,et al. Simulation model of land use dynamics and application:Progress and prospects[J].Journal of Remote Sensing,2017,21(3):329-340.]   
[4]张新焕,肖艳秋,杨德刚,等.基于Logistic 模型的三工河流域 农户节水灌溉驱动力分析［J].中国沙漠，2013，33（1）：288- 294.[ZHANG Xinhuan,XIAO Yanqiu,YANG Degang,et al.Analysis on driving forces households water-saving irrigation decision-making in the Sangonghe River Basin using the logistic model [J].Journal of Desert Research,2013,33（1）:288-294.]   
[5］任君,刘学录,岳健鹰,等.基于MCE-CA 模型的嘉峪关市城市 开发边界划定研究［J].干旱区地理，2016,39（5)：1111- 1119.[REN Jun,LIU Xuelu,YUE Jianying,et al.Delimiting the urban development boundary of Jiayuguan City based on MCE-CA model[J]. Arid Land Geography,2016,39(5）:1111-1119.]   
[6]ZHANG H,ZENG Y,JIN X,et al. Simulating multi-objective land use optimization alocation using multi-agent system: A case study in Changsha,China[J].Ecological Modelling,2016,320;334- 347.   
[7］张丁轩,付梅臣,陶金,等.基于CLUE-S 模型的矿业城市土地 利用变化情景模拟[J].农业工程学报,2013,29（12）:246- 256.［ZHANG Dingxuan,FU Meichen,TAO Jin,et al. Scenario simulation of land use change in mining city based on CLUE-S model[J].Transactions of the Chinese Society of Agricultural Engineering,2013,29(12）:246 -256.]   
[8]LOSIRI C,NAGAI M,NINSAWAT S,et al. Modeling urban expansion in Bangkok Metropolitan region using demographic-economic data through cellular Automata-Markov chain and multi-layer Perceptron-Markov chain models[J].Sustainability,2016,8（7）： 686.   
[9]BALZTER H,BRAUN P W,KOHLER W. Cellular automata models for vegetation dynamics[J].Ecological Modelling,1998,107 (2 -3) :113 -125.   
[10]MEMARIAN H,BALASUNDRAM S K,TALIB JB,et al. Validation of CA-Markov for simulation of land use and cover change in the Langat Basin,Malaysia[J]. Journal of Geographic Information System,2012,4(6):542 -554.   
[11］解修平,周杰,张海龙,等.关中—天水经济区土地利用变化模 拟预测及景观格局动态变化[J].干旱区地理,2013,36（3)： 482-490.[XIE Xiuping,ZHOU Jie,ZHANG Hailong,et al. Land use change simulation and landscape pattern change of the Guanzhong-Tianshui region[J].Arid Land Geography,2013,36 (3):482-490.]   
[12]LUO G P,AMUTI T,ZHU L,et al. Dynamics of landscape patterns in an inland river delta of Central Asia based on a cellular automata-Markov model[J]. Regional Environmental Change,2015,15 (2) :277 -289.   
[13］汪佳莉,吴国平,范庆亚,等.基于CA-Markov 模型的山东省临 沂市土地利用格局变化研究及预测[J].水土保持研究,2015, 22(1):212 -216.[WANG Jiali,WU Guoping,FAN Qingya,et al. Change and prediction of the land use in Linyi City,Shandong Province based on CA-Markov model[J].Research of Soil and Water Conservation,2015,22(1) :212-216.]   
[14]CHEN H,PONTIUS R G JR.Diagnostic tools to evaluate a spatial land change projection along a gradient of an explanatory variable [J].Landscape Ecology,2010,25(9）:1319-1331.   
[15]OLMEDO M T C,PONTIUS R G,Jr,PAEGELOW M,et al. Comparison of simulation models in terms of quantity and allocation of land change[J].Environmental Modellng & Software,2015,69: 214 -221.   
[16]SINHA P.Markov land cover change modeling using pairs f timeseries satellte images[J].Photogrammetric Engineering & Remote Sensing,2015,79(11） :1037 -1051.   
[17］侯西勇,常斌,于信芳.基于CA-Markov 的河西走廊土地利用 变化研究[J].农业工程学报,2004,20（5）:286-291.[HOU Xiyong,CHANG Bin,YU Xinfang.Land use change in Hexi Coridor based on CA-Markov methods[J].Transactions of the Chinese Society of Agricultural Engineering,2004,20(5）:286-291.]

[18]PARSA VA,SALEHI E.Spatio-temporal analysis and simulation pattern of land use/cover changes,case study:Naghadeh,Iran[J]. Journal of Urban Management,2016,5(2）:43-51.

[19］韩德林.新疆人工绿洲［M].北京:中国环境科学出版社, 2001:21-23.[HAN Delin.The artificial oasis in Xinjiang[M]. Beijing:China Environmental Science Press,2001:21-23.]   
[20］冯异星,罗格平,尹昌应,等.干旱区内陆河流域土地利用程度 变化与生态安全评价——以新疆玛纳斯河流域为例[J].自然 资源学报,2009,24（11）：1921-1932.［FENGYixing，LUO Geping,YIN Changying,et al. Change of land-use degree and ecological security assessment of inland river basins in the arid area :A case study on Manas River Basin in Xinjiang[J]. Journal of Natural Resources,2009,24(11):1921-1932.]   
[21］杨卫红.玛纳斯河流域绿洲经济—生态景观空间分异研究 [D].石河子:石河子大学,2016.［YANGWeihong.The spatial diferentiation research of oasis economic：Ecological landscape in the Manas River Basin[D].Shihezi：Shihezi University,2016.]   
[22］乔伟峰,盛业华,方斌,等.基于转移矩阵的高度城市化区域土 地利用演变信息挖掘—以江苏省苏州市为例[J].地理研 究,2013,32(8）:1497-1507.[QIAO Weifeng,SHENG Yehua, FANG Bin,et al.Land use change information mining in highly urbanized area based on transfer matrix:A case study of Suzhou, Jiangsu Province[J].GeographicalResearch,2O13,32（8）： 1497 -1507.]   
[23］刘淑燕,余新晓,李庆云,等.基于CA-Markov 模型的黄土丘陵 区土地利用变化[J].农业工程学报,2010,26(11）：297-303. [LIU Shuyan,YU Xinxiao,LI Qingyun,et al. Land use change in loess hilly region based on CA-Markov model[J].Transactions of the Chinese Society of Agricultural Engineering,2010,26（11）： 297 -303.]   
[24］冯雪力,吴世新,陈红.新疆地区近15 年来土地利用时空变化 及驱动力分析[J].干旱地区农业研究,2010,28（3）：224- 230.[FENG Xueli,WU Shixin,CHEN Hong.LUCC analysis of Xinjiang based on GIS and Markov process[J].Agricultural Research in the Arid Areas,2010,28(3):224-230.]   
[25］杨俊,解鹏,席建超,等.基于元胞自动机模型的土地利用变化 模拟——以大连经济技术开发区为例[J].地理学报,2015,70 (3）:461-475.[YANG Jun,XIE Peng,XIJianchao.LUCC simulation based on the cellular automata simulation;A case study of Dalian economic and technological development zone[J].Acta Geographica Sinica,2015,70(3）:461-475.]   
[26］尹昌应,罗格平,鲁蕾,等.内陆干旱区土地利用变化的景观格 局特征分析—以新疆白杨河流域为例[J].干旱区地理, 2008,31(1）:67-74.[YIN Changying,LUO Geping,LU Lei,et al.Characteristics of landscape patterns of land use change in arid areas:A case study of oasis at the Baiyang River Watershed in Xinjiang[J].Arid Land Geography,2008,31（1）:67-74.]   
[27]JANSSEN L L F,WEL F JM. Accuracy assessment of satelite derived land cover data: A review[J].Photogrammetric Engineering & Remote Sensing,1994,60(4）:419 -426.   
[28]MEMARIANH,BALASUNDRAMSK,TALIBJB,etal.Validation of CA-Markov for simulation of land useand cover change in the Langat Basin,Malaysia[J]. Journal of Geographic Information System,2012,4(6):542-554.   
[29］罗格平,周成虎,陈曦.干旱区绿洲景观尺度稳定性初步分析 [J].干旱区地理,2004,27(4）:471-476.[LUO Geping,ZHOU Chenghu,CHEN Xi,et al.Preliminary analysis on the oasis stability at the landscape level in the arid regions[J].Arid Land Geography,2004,27(4) :471 -476.]   
[30］王丹,吴世新,张寿雨.新疆20 世纪80 年代末以来耕地与建 设用地扩张分析[J].干旱区地理,2017,40（1)：188－196. [WANG Dan,WU Shixin,ZHANG Shouyu.Expansion of both cultivated and construction land in Xinjiang since the late 1980s[J]. Arid Land Geography,2017,40(1) :188 -196.]   
[31］张青青,徐海量,樊自立,等.玛纳斯河流域人工绿洲扩张对社 会经济和生态环境的影响分析[J].中国沙漠,2012,32（3）： 863- 871.[ZHANG Qingqing,XU Hailiang,FAN Zili,et al. Effect of artificial oasis expansion on social economy and ecological environment in Manas River Basin,Xinjiang of China[J]. Journal of Desert Research,2012,32（3）:863 -871.]   
[32]SAMAT N,HASNI R,ELHADARY Y A E.Modelling land Use changes at the Peri-Urban areas using geographic information systems and Cellular Automata model[J]. Journal of Sustainable Development,2011,4(6) :72 -84.   
[33］程维明,周成虎,李建新.天山北麓经济发展与绿洲扩张［J]. 地理学报,2002,57（5）:561-568.[CHENG Weiming,ZHOU Chenghu,LI Jianxin. Economic development and oasis growth at the northern fotof the Tianshan Mountains[J].Acta Geographica Sinica,2002,57(5） :561 -568.]   
[34］程维明,周成虎,刘海江,等.玛纳斯河流域50 年绿洲扩张及 生态环境演变研究[J].中国科学:地球科学,2005,35（11）： 70 -82.[CHENG Weiming,ZHOU Chenghu,LIU Haijiang,et al. Oasis expansion and ecological environment evolution in Manas River Basin in the past 5O years[J].Science China:Earth Sciences,2005,35（11) :70-82.]   
[35]王渊刚,罗格平,冯异星,等.近50a玛纳斯河流域土地利用/ 覆被变化对碳储量的影响[J].自然资源学报,2013,28（6）： 994 - 1006.[WANG Yuangang,LUO Geping,FENG Yixing,et al.Effects of land use/land cover change on carbon storage in Manas River Watershed over the past 5O years[J].Journal of Natural Resources,2013,28(6) :994-1006.]   
[36］王永静,闫周府.新疆玛纳斯河流域用水结构演变及其驱动力 分析[J].干旱区研究,2017,34（2）：243－250.[WANG Yongjing,YAN Zhoufu.Evolution and driving forcesof water consumption structure in the Manas River Basin in Xinjiang[J].Arid Zone Research,2017,34(2）:243-250.]   
[37］李菊荣,王延华,唐湘玲,等.新疆玛纳斯河流域土地利用变化 特征及影响因素研究[J].土壤通报,2018,49(1):61-68.［LI Jurong,WANG Yanhua,TANG Xiangling,etal.The spatial-temporal characteristics of land use change in the Manas River Basin and influencing factors[J].Chinese Journal of Soil Science,2018,49 (1) :61 -68.]   
[38]PEREZ-VEGGA A,LIGMANN-ZIELINSKA A. Comparing two approaches to land use/cover change modeling and their implications for the assessment of biodiversity loss in a deciduous tropical forest [J].Environmental Modelling& Software,2012,29(1）:11-23.   
[39]ONATEVALDIVIESO F,SENDRA J B. Application of GIS and remote sensing techniques in generation of land use scenarios for

hydrological modeling[J]. Journal of Hydrology,2010,395（3- 4):256 -263.

[40］何丹，周璟，高伟，等.基于CA-Markov 模型的滇池流域土地利用变化动态模拟研究[J].北京大学学报（自然科学版）,2014，50（6):1095-1105.［HEDan,ZHOUJing,GAO Wei,et al.Anintegrated CA-Markov model for dynamic simulation of land usechange inLake Dianchi Watershed[J].Acta Scientiarum Naturali-um Universitatis Pekinensis（Natural Science Edition）,2O14,50(6):1095-1105.]

[41］凌红波，徐海量，乔木，等.1958—2006 年玛纳斯河流域水系结 构时空演变及驱动机制分析[J].地理科学进展，2010,29（9）： 1129-1136.[LING Hongbo,XU Hailiang,QIAO Mu,et al. Temporal-spatial evolution of stream construction and its driving forces in Manas River Basin during 1958—2006[J].Progress in Geography,2010,29(9):1129-1136.]

[42］朱磊，刘雅轩.基于GIS和元胞自动机的玛纳斯河流域典型绿 洲景观格局优化[J].干旱区地理，2013,36（5)：946-954. [ZHU Lei,LIU Yaxuan.Landscape optimization of typical oasis in Manas River Basin based on GIS and Cellular Automata[J].Arid Land Geography,2013,36(5):946-954.]

# Simulation of land use change at different time spans based on CA-Markov model

JIN Han12，YANG Ai-min1，XIA Xin-xin1，ZHULei1²，ZHANG Qing-qing1 (1CollgeofPrataculturalandEnvironmental Siences,XinjangAgriculturalUniversity,Urumqi3o52,Xinjang,China; 2Xinjiang Key Laboratory of Soil and Plant Ecological Processes,Urumqi 830o52,Xinjiang,China)

Abstract：The study of Land Use/Cover Change（LUCC）and its dynamics is crucial for human existence and sustainable development.LUCC simulation is the main content and effctive method in LUCC research and time span is oneof the most important parameters inthe simulation process,and thus its efect on the simulation accuracy needs tobe further studied.Inorder to explore LUCC simulation accuracyat diferenttime spans,we took Sidaohezi Town of Manas River Basin in Xinjiang,Chinaas the studyarea.Seven land use maps were created from remote sensing images（MSS images in the1975,TMimagesin1985and1995,ETMimages in2000,2005and 2010,and OLI images in2Ol5）andtheland surfaces were clasified into six landcover categories:cultivatedland,woodland, grassland,water area,construction land and unused land.Then the landuse transition probabilityduring fourdiferent periods（1975—1995,1985—2000,1995—2005and 2005—2010）were used to establish the CA-Markov model to simulate landuse in 2015using long-term（20-years）,medium-term（15-and10-years）and short-term （5-years）intervals respectively.The simulation processwascompleted by the CA-Markov module in IDRISI software.Finally,four simulated land use maps for 2015 $( R _ { 1 } , R _ { 2 } , R _ { 3 } , R _ { 4 } )$ were compared with the real land use map in 2015 $( R )$ ,and the Total Figure of Merit （TFOM） indexes were used to evaluate the models accuracy.The results showed that from1975 to 2O15,cultivated land and grassland were the dominant land use types in Sidaohezi Town. During the study period,cultivated landand construction land expanded rapidly,whereas forest land,grassland and unused land have been greatly reduced,and the water area has experienced a slight increase from 1985 to 2000. Throughout the study period,the increase of cultivated land and decrease of grassand and woodland were the most significant features of LUCC.Compared the simulated results with real land use map in 2015,fivecomponents of agreement and disagreement were detected as $S _ { 1 } , S _ { 2 } , S _ { 3 } , S _ { 4 }$ and $S _ { 5 }$ . The TFOM indices of 20-,15-,10- and 5-years intervals were $7 0 . 3 5 \%$ ,69. $18 \%$ ， $7 6 . 3 2 \%$ and $8 8 . 0 0 \%$ respectively.It was indicated that smaller time intervals produced higher accuracy.The time span of 5-years was the optimum time interval to simulate the landuse change of Sidaohezi Town from1975 to 2015.This study provided a scientific basis forthe selection of time interval in land usechange simulation.Moreover,the simulation accuracy depends not merely on the land use transition probability within acertain periodof time,but the local land policiesand social development characteristics in thesame time should also be considered.

Key words:Manas River Basin; land use and cover change; CA-Markov; time span