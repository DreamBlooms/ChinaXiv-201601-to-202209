# 关中平原极端降水时空变化及其与大气环流的关系

丁莹莹¹，邱德勋²，吴常雪¹，穆兴民¹²，高鹏12(1.西北农林科技大学水土保持研究所,黄土高原土壤侵蚀与旱地农业国家重点实验室,陕西 杨凌712100;2.中国科学院水利部水土保持研究所，陕西杨凌712100）

摘要：基于关中平原13个气象站1957—2019年逐日降水资料,运用一元线性回归、Pearson相关分析和小波相干分析等方法,计算各极端降水指数,分析其时空变化特征，探讨极端降水与大气环流的关系。结果表明：（1）在时间上，除极端降水强度以 $0 . 0 0 7 \ \mathrm { m m \cdot d ^ { - 1 } \cdot ( 1 0 a ) ^ { - 1 } }$ 速率的上升外，其他极端降水指数均呈下降趋势，其中年均极端降水总量(PRCPTOT)下降最快,下降速率为 $- 5 . 5 2 8 ~ \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ,并且各极端降水指数均无显著突变点。(2）在空间上,极端降水指数南高北低,空间差异显著。（3）反映大气环流的南方涛动指数(SOI)对极端降水影响最为显著。SOI越大,关中平原越易出现少雨现象。本研究可为关中平原洪水灾害防治提供科学理论依据。

关键词：关中平原；极端降水；时空变化；大气环流

水循环是联系海洋与内陆实现水资源循环更新的重要物质循环之一，降水是水循环的四个基本环节中的重要一环。在全球气候变化和人类活动的影响下，水循环过程加剧，极端降水事件频发。极端降水事件虽是小概率事件1，但它具有较强的持续时间不确定性，持续多天的极端降水事件往往具有较大的致灾性],易诱发山洪、泥石流和滑坡等地质灾害,严重威胁着人类的生命财产安全[3]。

目前，有关极端降水的研究集中在极端降水的时空变化规律、极端降水与大气环流的关系、极端降水事件模拟以及基于人工神经网络和机器学习的未来极端降水事件预测等方面[4-6]。研究的区域范围覆盖华南、西南和七大流域等。戴声佩等基于华南地区1959—2016年逐日实测降水资料分析了极端降水的时空变化特征，发现大尺度的大气环流对华南地区极端降水有显著影响。杜懿等8通过信号分析和机器学习方法建立BPNN、WANN、TSNN、SVM、ELM降水量预测模型，得出除BPNN外，其他模型能理想的预测降雨量。罗志文等9基于地区线性矩法探究了陕西省极端降水时空变化特征，发现极端降水的分布特征与独特的地理位置有关。

关中平原因秦岭和陕北高原环绕，地理位置特殊，水汽输送过程受阻，水循环过程也相应发生变化。刘燕飞等["通过一次暴雨的数值模拟研究发现关中平原东部降水量低于西部，可能与秦岭的阻挡有关。白爱娟等["研究发现关中地区受副热带高压影响，暖湿气流不易通过季风环流到达欧亚大陆北部地区，导致陕西省冬春季少雨。大气环流异常是引起气候变化的直接原因，极端降水事件频发与大气环流异常有密切关系[12]。东西太平洋气压差变化影响风向从而影响大气环流、水汽传送，进而影响降水过程。其中反应大气环流的南方涛动(SOI)与厄尔尼诺现象(ENSO)的活跃程度息息相关，张冲等[13研究发现关中地区1951—2008年EN-SO增强时，降水量下降。周旗等5对渭河极端降水进行上中下游对比分析，认为在20世纪90年代以前和2000年以后，降水情况年际差异大，中游变化更为明显。关中平原是渭河冲积平原，地处渭河中游，对气候变化敏感[14],且近年来西北地区强降水有增多趋势。但是关于大气环流影响关中地区极端降水的潜在机制尚不明确，因此有必要对该区域的极端降水与大气环流的关系做进一步研究，以期为关中平原水资源调配、工农业发展和洪水灾害防治提供理论支撑。

# 1研究区概况

关中平原位于陕西中部，有13个气象站(图1)，介于秦岭与渭北北山，所指为渭河冲积平原，西起宝鸡，东至潼关，包括宝鸡、咸阳、铜川、渭南和西安5个地级市,地势西高东低,海拔约为 $3 2 5 { \sim } 8 0 0 \mathrm { ~ m }$ ，面积约为 $3 . 4 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,属大陆性气候，年均温 $6 \sim$ $1 3 ^ { \circ } \mathrm { C }$ ,年降水量为 $5 0 0 { \sim } 8 0 0 ~ \mathrm { m m }$ ，受季风气候影响降水主要集中在夏秋季6一9月，多为短时暴雨。关中平原自然经济条件优越，人口密集，自古以来就是农业富庶之地，在全国区域经济发展中占据重要地位[15]

![](images/59850bfe12f174086be4973e86c7e5d6aab1adb40d8b1c8e0cea18662c8652eb.jpg)  
图1关中平原气象站点分布  
Fig.1 Distribution of meteorological stations in Guanzhong Plain

# 2数据与方法

# 2.1数据来源

利用关中平原13个气象站1957—2019年逐日降水资料，分析近63a6个极端降水指数的时空变化及其与大气环流的相关关系。各气象站逐日降水资料来源于中国气象科学数据共享服务网(http://data.cma.cn），部分缺测数据通过临近站点插补，利用RClimate软件对降水数据进行质量和一致性检验，数据均表现良好。关中平原数字高程(DEM)数据来源于地理空间数据云(http://www.gscloud.cn/search），美国太空总署(NASA)和国防部国家测绘局(NIMA)联合测量的 $9 0 ~ \mathrm { m }$ 分辨率数字高程数据产品。AMO（大西洋年际振荡指数）、AO（北极涛动指数）、NAO（北大西洋涛动指数）、NP（北太平洋遥相关指数）、PDO（太平洋年代际振荡指数）、WP（西太平洋指数)和SOI(南方涛动指数)等反映大气环流的指数数据来源于美国国家海洋和大气管理局地球系统研究实验室（https://psl.noaa.gov/data/cli-mateindices/)。

# 2.2 研究方法

2.2.1 极端降水指数的选取根据世界气象组织（WorldMeteorological Organization,WMO）以及气候学委员会(CCI)组建的气象监测专家组推荐的极端降水指标再结合关中平原的气候类型选取6个极端降水指数。这些降水指数分别能反映研究区域的降水量、降水日数和降水强度(表1)。

2.2.2一元线性回归利用线性回归最小二乘法和10a滑动平均进行极端降水指数的时间变化趋势分析，线性回归方程的斜率为线性倾向率。线性倾向率为正值时，表明对应序列呈上升趋势；反之，呈下降趋势，线性倾向率的绝对值大小表示序列的变化程度[17]。非参数检验是不依赖于总体分布的数据分析方法，利用Mann-Kendall进行非参数检验，检验各个极端降水指数得到反映各指数变化显著性水平Z值。如果 $Z { > } 0$ ，说明变量呈增加趋势；反之，说明序列呈减少趋势。当 $\scriptstyle \alpha = 0 . 0 5$ 和 $\scriptstyle \alpha = 0 . 0 1 , Z$ 值对应绝对值为1.96和 $2 . 5 8 , Z$ 值的绝对值远远大于1.96或2.58时，表明序列增加或减少的趋势越显著[18]

表1极端降水指数及定义  
Tab.1 Extreme precipitation index and definition   

<html><body><table><tr><td>极端降水指数</td><td>名称</td><td>单位</td><td>意义和说明</td></tr><tr><td>CWD</td><td>持续湿期</td><td>d</td><td>日降水量>1mm的最大持续日数</td></tr><tr><td>SDII</td><td>日降水强度</td><td>mm·d-1</td><td>降水总量与有雨日数之比(日降水量>1mm)</td></tr><tr><td>PRCPTOT</td><td>降水总量</td><td>mm</td><td>日降水量>1mm的年累积降水量</td></tr><tr><td>R10mm</td><td>中雨日数</td><td>d</td><td>日降水量>10mm的总日数</td></tr><tr><td>RX1day</td><td>最大1日降水量</td><td>mm</td><td>每年最大日降水量</td></tr><tr><td>RX5day</td><td>连续5日最大降水量</td><td>mm</td><td>每年连续5日最大降水量</td></tr></table></body></html>

用一元线性回归极端降水指数的年际变化趋势：

$$
\ y = b t + a
$$

运用最小二乘法对一元线性回归方程进行求解,过程如下：

$$
a = y - t b
$$

$$
b = \sum \left[ { \big ( } t _ { i } - t { \big ) } { \big ( } y _ { i } - y { \big ) } \right] { \Big / } \sum { \big ( } t _ { i } - t { \big ) } ^ { 2 }
$$

式中： $y$ 为极端降水指数； $b$ 为线性倾向率; $\mathbf { \chi } _ { t }$ 为时间序列。

利用Mann-Kendall进行突变点检验，其原理如下：

得到的 $U F _ { \mathrm { \Delta _ { k } } } \mathrm { ~ , ~ } U B _ { \mathrm { \Delta _ { k } } }$ 曲线,如果 $U F _ { k }$ 与 $U B _ { k }$ 出现交点，且交点在临界线之内，那么交点就是突变开始的时间。 $U F _ { k } > 0$ 表示序列呈上升趋势,反之,呈下降趋势。 $U F _ { k }$ 和 $U B _ { k }$ 超出临界值时,表示变化趋势显著。

2.2.3小波相干分析小波相干来源于傅立叶相干，小波相干分析能通过交叉小波相干谱直观反映影响因子与径流的位相关系和局部相关程度[19]。图谱中锥形细线区域为有效谱值区，图中粗实线区表示通过了 $5 \%$ 的显著性水平的置信区间，箭头所指方向反映了两时间序列的位相关系，箭头向右表示影响因子与径流之间同相位，两序列具有正相关关系；箭头向左，反之。箭头向下，表示影响因子变化超前径流变化 $9 0 ^ { \circ }$ （对应时间为3个月）；箭头向下，表示影响因子变化落后径流变化 $9 0 ^ { \circ }$ ，有效谱值区可避免边界效应及小波高频假信息[20-21]。

对于2个时间序列 $X$ 与 $Y$ 之间的交叉小波功率谱(XWT)定义为[22]

$$
\boldsymbol { W } _ { j } ^ { X Y } \big ( \boldsymbol { s } \big ) = \boldsymbol { W } _ { j } ^ { X } \big ( \boldsymbol { s } \big ) \boldsymbol { W } _ { j } ^ { Y ^ { * } } \big ( \boldsymbol { s } \big )
$$

式中： $W _ { j } ^ { X Y } \big ( s \big )$ 表示要素 $X , Y$ 的交叉小波结果; $\boldsymbol { W } _ { j } ^ { X } ( s )$ 表示要素 $X$ 的连续小波变换结果； $\boldsymbol { W } _ { j } ^ { Y } \left( s \right)$ 表示要素

Y的连续小波变换结果； $\boldsymbol { W } _ { j } ^ { Y ^ { * } } ( s )$ 表示 $Y$ 的复共轭; $s$   
为伸缩尺度。

小波相干谱定义[2]如下

$$
R _ { j } ^ { 2 } ( s ) = \frac { \left| S \big [ s ^ { - 1 } W _ { j } ^ { \scriptscriptstyle X Y } ( s ) \big ] \right| ^ { 2 } } { S \Big [ s ^ { - 1 } \big | W _ { j } ^ { \scriptscriptstyle X } ( s ) \big | ^ { 2 } \Big ] S \Big [ s ^ { - 1 } \big | W _ { j } ^ { \scriptscriptstyle Y } ( s ) \big | ^ { 2 } \Big ] }
$$

式中： $s$ 为平滑算子。

本文利用小波相干谱来分析极端降水指数与大气环流因子的局部相关程度。

# 3结果与分析

# 3.1极端降水的时空变化

3.1.1时间变化基于各气象站点逐日降水数据，利用泰森多边形法推求极端降水指数，并计算各极端降水指数在时间序列上的多年均值，分析关中平原极端降水指数63a来的变化趋势(图2)。关中平原属暖温带半湿润气候区，总体来看，所有的极端降水指数变化趋势均不显著，除SDII以 $0 . 0 1 \ \mathrm { m m ^ { \cdot } d ^ { - 1 } }$ ：$( 1 0 \mathrm { a } ) ^ { - 1 }$ 速率增大外，其余均呈不显著的减少趋势。20世纪90年代以前和2000年以后，通过10a滑动平均法所作趋势线可看出，极端降水指数表现出了往复的变化趋势，有微弱的往复变化特点，其中CWD在90年代以前呈下降趋势,2000—2009年有较明显的上升趋势。其余极端降水指数以年际震荡为主。PRCRPTOT以 $- 5 . 5 2 8 ~ \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 速率减少,多年平均值为 $5 1 3 . 3 6 ~ \mathrm { m m }$ ,最小值为 $3 3 2 . 6 ~ \mathrm { m m }$ 出现在1997年(表2)；RX1day以 $- 0 . 1 0 5 \mathrm { ~ m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 的速率减少，RX5day和CWD分别以 $- 0 . 0 9 6 ~ \mathrm { m m } \cdot$ $( 1 0 \mathrm { a } ) ^ { - 1 }$ 和 $- 0 . 1 7 1 \mathrm { ~ d } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 的速率下降。表征降水大小持续日数的 $\mathrm { R 1 0 m m }$ 的线性倾向率为 $- 0 . 0 0 5 \mathrm { ~ d ~ }$ ：$( 1 0 \mathrm { a } ) ^ { - 1 }$ ,整体上呈不显著的下降趋势，波动性较大。经Mann-Kendall突变检验发现各极端降水指数且未发生显著性突变。

3.1.2空间变化依据13个站点极端降水指数多年均值以及各站点的极端降水指数的线性倾向率，通过地学分析模块中的反距离权重法插值(IDW)得到关中平原各极端降水指数的空间分布及变化趋势(图3)。

在空间分布上，极端降水呈现南高北低的分布规律，空间差异显著，各极端降水指数均呈现出自西南部佛坪站和东南部向西北部递减的趋势。关

![](images/6a38f9ab0f789ae8e923fc8ee763a013382306c03906e04f36c7807a1936173a.jpg)  
图2极端降水指数变化趋势   
Fig.2 Trend of extreme precipitation indices

# 表2极端降水指数特征值

Tab.2 Characteristic values of extreme precipitation index   

<html><body><table><tr><td></td><td>CWD/d</td><td>PRCPTOT/mm</td><td>R10mm/d</td><td>RX1day/mm</td><td>RX5day/mm</td><td>SDII/(mm·d-1)</td></tr><tr><td>多年均值</td><td>7.87</td><td>513.36</td><td>14.35</td><td>29.4</td><td>61.47</td><td>5.58</td></tr><tr><td>最大值</td><td>17</td><td>765.6</td><td>23</td><td>45.07</td><td>108.79</td><td>7.3</td></tr><tr><td>最小值</td><td>4</td><td>332.6</td><td>7</td><td>17.41</td><td>35.74</td><td>4.6</td></tr><tr><td>最大值出现年份</td><td>2007</td><td>1964</td><td>1983</td><td>2010</td><td>2003</td><td>1983</td></tr><tr><td>最小值出现年份</td><td>1995、2004、2012</td><td>1997</td><td>1997</td><td>1987</td><td>1987</td><td>1977、2015</td></tr></table></body></html>

中南部佛坪站CWD最大，为7.38d,西部地区CWD较东北部较长，东南部CWD最大值发生在华山站$6 . 2 5 \mathrm { ~ d ~ }$ 。受气候地形等因素影响，PRCPTOT自西南和东南向西北递减，中部降水较少，关中东南部华山站PRCPTOT较大为 $7 8 3 . 4 5 ~ \mathrm { m m }$ ,武功、西安站降水量相对较少，年均极端降水总量最大值发生在佛坪站，为 $9 1 0 . 5 3 ~ \mathrm { { m m } }$ ,PRCPTOT最小值发生在关中平原西北部的崆峒站，为 $4 9 5 . 9 1 ~ \mathrm { m m }$ 。 $\mathrm { R } 1 0 \mathrm { m m }$ 最大值发生在佛坪站，为27.57d,最小值发生在崆峒站，为$1 5 . 5 6 \mathrm { d }$ 。 $\mathrm { R } 1 0 \mathrm { m m }$ 呈现出由东南和西南向西北递减的趋势。西安站RX1day最小为 $5 0 . 7 6 ~ \mathrm { m m }$ ,RX1day最大值在佛坪站为 $7 5 . 9 7 ~ \mathrm { m m }$ 。崆峒站RX5day最小，为 $8 1 . 3 5 \mathrm { m m }$ ,RX1day的极大值发生在佛坪站，陇县站RX5day最大，多年均值为 $1 6 5 . 2 ~ \mathrm { m m }$ ;崆峒站多年平均SDII最小,佛坪站SDII多年平均值最大，为$1 0 . 2 5 \ \mathrm { m m ^ { \cdot } d ^ { - 1 } }$ 。

![](images/0df56d71da1ab662eaafd7cd009ae5d186eb082682e370c92e8de98199500131.jpg)  
图3极端降水指数空间变化趋势   
Fig.3Spatial variation trend of extreme precipitation index

在空间变化趋势上， $6 9 . 2 \%$ 的站点PRCPTOT呈下降趋势， $9 2 . 3 \%$ 的站点 $\mathrm { R 1 0 m m }$ 呈下降趋势（表3)。除商州、陇县站以外，其他站的CWD都呈下降趋势;崆峒、长武、佛坪站和陇县站PRCPTOT均呈上升趋势，其他站均呈下降趋势，镇安站PRCPTOT下降幅度最大，下降速率为 $1 8 . 7 \ \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ,其次是华山站，下降速率为 $1 4 . 3 5 \ \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 。除崆峒站$\mathrm { R } 1 0 \mathrm { m m }$ 以 $0 . 1 5 \mathrm { d } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 的速率上升外,其他站均呈下降趋势。宝鸡、华山和蒲城站RX1day分别以$- 0 . 4 7 \ \mathrm { m m \cdot ( 1 0 a ) ^ { - 1 } \setminus { 0 . 5 1 } \ \mathrm { m m } \cdot ( 1 0 a ) ^ { - 1 } }$ 和 $- 0 . 7 5 \ \mathrm { m m }$ ：

$( 1 0 \mathrm { a } ) ^ { - 1 }$ 的速率下降，其他站RX1day均呈上升趋势，长武站RX1day上升幅度最大，上升速率为3.59$\mathrm { m } \mathrm { m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ,佛坪和商州站RX1day上升幅度相近。宝鸡、耀县、武功、华山、镇安、陇县和蒲城站RX5day均呈下降趋势，蒲城站下降趋势更显著，下降速率达 $- 4 . 4 8 ~ \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ,其他站RX5day均呈上升趋势，长武站上升幅度最大,上升速率为 $5 . 4 5 ~ \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 其次是佛坪站，上升速率为 $2 . 4 8 ~ \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 。耀县站SDII未发生显著性变化，除华山站和蒲城站SDI以 $- 0 . 0 6 \ \mathrm { m m \cdot d ^ { - 1 } \cdot ( 1 0 a ) ^ { - 1 } }$ 和 $- 0 . 0 7 3 \mathrm { ~ m m } \cdot \mathrm { d } ^ { - 1 } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 的速率减小外，其他站的SDII均呈增大趋势。除关中平原东南部外其他区域SDII均呈显著上升趋势，且关中平原西北部PRCPTOT和SDII呈增加趋势，CWD呈减少趋势，未来极端降水事件发生的可能性增大。

表3极端降水指数空间变化趋势   
Tab.3 Statistical analysis of spatial variation trend of extreme precipitation index   

<html><body><table><tr><td>指数</td><td>上升趋势 站点个数</td><td>占比/%</td><td>下降趋势 站点个数</td><td>占比/%</td></tr><tr><td>CWD</td><td>2</td><td>15.4</td><td>11</td><td>84.6</td></tr><tr><td>PRCPTOT</td><td>4</td><td>30.8</td><td>9</td><td>69.2</td></tr><tr><td>R10mm</td><td>1</td><td>7.7</td><td>12</td><td>92.3</td></tr><tr><td>RX1day</td><td>10</td><td>76.9</td><td>3</td><td>23.1</td></tr><tr><td>RX5day</td><td>6</td><td>46.2</td><td>7</td><td>53.8</td></tr><tr><td>SDII</td><td>11</td><td>84.6</td><td>2</td><td>15.4</td></tr></table></body></html>

# 3.2各极端降水指数变化的一致性

除CWD以外，其他极端降水指数之间都存在显著正相关性，相关系数在 $0 . 2 9 \mathrm { \sim } 0 . 8$ 之间，且通过了0.05的显著性水平检验。 $\mathrm { R } 1 0 \mathrm { m m }$ 、RX5day 和SDII与PRCPTOT的相关性均通过了0.01的显著性水平检验，且与PRCPTOT表现出良好的相关性，表明所选取的极端降水指数对年降水总量具有很好的指示作用，极端降水指数的增加或减少能反映出降水量的增加或减少(表4)。

表4极端降水指数相关系数  
Tab.4 Correlation coefficient of extreme precipitation index   

<html><body><table><tr><td></td><td>CWD</td><td>PRCPTOT R10mm</td><td></td><td>RX1day</td><td>RX5day</td><td>SDII</td></tr><tr><td>CWD</td><td>1</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>PRCPTOT</td><td>0.320*</td><td>1</td><td></td><td></td><td></td><td></td></tr><tr><td>R10mm</td><td>0.242</td><td>0.875**</td><td>1</td><td></td><td></td><td></td></tr><tr><td>RX1day</td><td>-0.073</td><td>0.319*</td><td>0.289°</td><td>1</td><td></td><td></td></tr><tr><td>RX5day</td><td>0.296*</td><td>0.488**</td><td>0.478**</td><td>0.482**</td><td>1</td><td></td></tr><tr><td>SDII</td><td>0.143</td><td>0.748**</td><td>0.806**</td><td>0.443**</td><td>0.547**</td><td>1</td></tr></table></body></html>

注：\*\*表示在0.01水平上显著相关，\*表示在0.05水平上显著相关。下同。

表5极端降水指数与大气环流因子的相关系数  
Tab.5 Correlation coefficients between extreme precipitation indices and atmospheric general circulation factors   

<html><body><table><tr><td></td><td>月份</td><td>CWD</td><td>PRCPTOT</td><td>R10mm</td><td>RX1day</td><td>RX5day</td><td>SDII</td></tr><tr><td>AMO</td><td>1-3</td><td>0.030</td><td>0.100</td><td>0.120</td><td>0.131</td><td>0.052</td><td>0.246</td></tr><tr><td rowspan="5"></td><td>4-6</td><td>-0.072</td><td>0.038</td><td>0.094</td><td>0.136</td><td>0.020</td><td>0.234</td></tr><tr><td>7-9</td><td>-0.064</td><td>-0.044</td><td>0.027</td><td>0.125</td><td>0.059</td><td>0.139</td></tr><tr><td>10—12</td><td>-0.008</td><td>-0.001</td><td>0.050</td><td>0.172</td><td>0.034</td><td>0.193</td></tr><tr><td>1-3</td><td>-0.059</td><td>0.013</td><td>0.004</td><td>-0.042</td><td>-0.074</td><td>-0.120</td></tr><tr><td>4-6</td><td>0.067</td><td>0.192</td><td>0.034</td><td>-0.089</td><td>0.010</td><td>-0.033</td></tr><tr><td rowspan="4">NAO</td><td>7-9</td><td>-0.019</td><td>0.131</td><td>0.093</td><td>0.121</td><td>0.080</td><td>0.028</td></tr><tr><td>10—12</td><td>-0.044</td><td>0.070</td><td>0.068</td><td>-0.013</td><td>-0.070</td><td>0.020</td></tr><tr><td>1-3</td><td>-0.162</td><td>-0.139</td><td>-0.103</td><td>-0.082</td><td>-0.126</td><td>-0.155</td></tr><tr><td>4-6</td><td>-0.141</td><td>0.088</td><td>-0.100</td><td>-0.143</td><td>-0.145</td><td>-0.079</td></tr><tr><td rowspan="4">NP</td><td>7-9</td><td>0.070</td><td>0.092</td><td>0.026</td><td>-0.004</td><td>0.044</td><td>0.045</td></tr><tr><td>10—12</td><td>-0.014</td><td>-0.016</td><td>-0.061</td><td>-0.188</td><td>-0.134</td><td>-0.108</td></tr><tr><td>1-3</td><td>0.042</td><td>-0.107</td><td>-0.133</td><td>-0.164</td><td>-0.101</td><td>-0.276*</td></tr><tr><td>4-6</td><td>0.063</td><td>0.208</td><td>0.149</td><td>0.073</td><td>0.048</td><td>-0.004</td></tr><tr><td rowspan="4">PDO</td><td>7-9</td><td>0.008</td><td>0.090</td><td>0.027</td><td>0.052</td><td>-0.043</td><td>0.023</td></tr><tr><td>10—12</td><td>-0.077</td><td>0.230</td><td>0.193</td><td>0.262*</td><td>0.056</td><td>0.270*</td></tr><tr><td>1-3</td><td>-0.022</td><td>0.183</td><td>0.136</td><td>-0.014</td><td>0.001</td><td>0.149</td></tr><tr><td>4-6</td><td>-0.153</td><td>0.004</td><td>0.001</td><td>-0.004</td><td>-0.036</td><td>0.120</td></tr><tr><td rowspan="4">WP</td><td>7-9</td><td>-0.162</td><td>-0.133</td><td>-0.133</td><td>-0.249*</td><td>-0.101</td><td>-0.123</td></tr><tr><td>10—12</td><td>-0.185</td><td>-0.195</td><td>-0.188</td><td>-0.216</td><td>-0.119</td><td>-0.151</td></tr><tr><td>1-3</td><td>-0.062</td><td>0.103</td><td>0.143</td><td>0.032</td><td>0.053</td><td>0.088</td></tr><tr><td>4-6</td><td>0.058</td><td>-0.066</td><td>-0.093</td><td>-0.200</td><td>0.026</td><td>-0.172</td></tr><tr><td rowspan="6">SOI</td><td>7-9</td><td>0.064</td><td>0.033</td><td>-0.078</td><td>0.014</td><td>0.048</td><td>-0.102</td></tr><tr><td>10—12</td><td>-0.006</td><td>-0.069</td><td>-0.068</td><td>-0.157</td><td>0.028</td><td>0.016</td></tr><tr><td>1-3</td><td>0.059</td><td>-0.237</td><td>-0.257°</td><td>-0.165</td><td>-0.131</td><td>-0.425**</td></tr><tr><td>4-6</td><td>0.294*</td><td>0.359**</td><td>0.354**</td><td>0.261*</td><td>0.202</td><td>0.249*</td></tr><tr><td>7-9</td><td>0.149</td><td>0.393**</td><td>0.412**</td><td>0.275*</td><td>0.159</td><td>0.356**</td></tr><tr><td>10-—12</td><td>0.230</td><td>0.332**</td><td>0.324**</td><td>0.285*</td><td>0.167</td><td>0.370**</td></tr></table></body></html>

# 3.3极端降水与大气环流的关系

3.3.1Pearson相关性分析选取1957—2019年间的反应大气环流的AMO、AO、NAO、NP、PDO、WP和SOI指数与同时间序列的6个极端降水指数进行不同季度尺度相关分析发现除RX5day以外，关中平原各极端降水指数都一定程度上受SOI、NP和PDO等反映大气环流的因子的影响。SOI与极端降水关系密切。在 $9 9 \%$ 的显著性水平下，4—12月SOI因子都与 $\mathrm { R 1 0 m m }$ 呈显著正相关。4—12月的SOI因子与PRCPTOT呈显著正相关（ $\scriptstyle { \cdot } P < 0 . 0 1 { \dot { } } ,$ ），且SOI越大，年均PRCPTOT减少趋势越显著。NP与SDII在1—3月呈显著负相关( $( P { < } 0 . 0 5 )$ ，与RX1day 和 SDII在10—12月呈显著正相关 $( P { < } 0 . 0 5 )$ 。PDO与RX1day在7一9月呈显著负相关，显著性水平为 $9 5 \%$ （表5）。

3.3.2极端降水指数与 SOI的关联分析使用小波相干分析法进一步探究 SOI与PRCPTOT、 $\mathrm { R 1 0 m m }$ 、SDII和CWD在低能量区的相互关系(图4)。SOI与CWD在1965—1968年相位差约为 $1 5 0 ^ { \circ }$ 存在相关系数约为0.83的负相关性，具有2\~4a的共振周期。$\mathrm { R 1 0 m m }$ 和SOI在1980—1989年间正相关程度较大，周期在5\~6a之间出现显著共振周期，局部相关系数达0.8以上。在1973—1988年之间SOI与PRCP-TOT存在相关系数可达0.85的显著正相关性，具有准5a的共振周期。SOI与 $\mathrm { R } 1 0 \mathrm { m m }$ 在1980—1985年存在4\~5a的共振周期,位相差约为 $3 0 ^ { \circ }$ 相关系数可达0.9,通过了 $9 5 \%$ 的置信度检验。在1980—1985年，SOI与SDII也存在4\~5a的共振周期且二者呈正相关，位相差约为 $6 0 ^ { \circ }$ ，局部相关系数可达0.82。反映大气环流的SOI对各极端降水指数的周期性影响具有一致性。

![](images/01a396c0a32b56418eec1dd48b664144190ae1b7f88abad45aaa2f34c45a5e87.jpg)  
图4大气环流因子与极端降水指数的小波相干谱  
Fig.4Wavelet coherence spectrum of atmospheric general circulation factors and extreme precipitation indice

# 4结论

（1）在时间上，除SDII呈上升趋势外，CWD、PRCPTOT、 $\mathrm { R } 1 0 \mathrm { m m }$ 、RX1day和RX5day均呈不显著的下降趋势。PRCPTOT下降速度最快，下降速率为 $- 5 . 5 2 8 ~ \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ,且无突变点。

(2）在空间上，关中平原各极端降水指数南高北低。关中平原极端降水指数最大值主要发生在东南部和西南部地区，西北部易发生集中性的极端降水。其中位于关中平原南部的佛坪站CWD、PRCPTOT、 $\mathrm { R } 1 0 \mathrm { m m }$ 、RX1day 和SDI最大。

（3）在所选择的反映大气环流的因子中，SOI对极端降水有显著影响。SOI与PRCPTOT存在准5a的共振周期。SOI与极端降水指数具有显著局部正相关性，SOI越大，关中平原越易出现少雨现象。

# 参考文献(References):

[1]赵一飞,邹欣庆,许鑫王豪.珠江流域极端降水事件及其与大气 环流之间的关系[J].生态学杂志,2014,33(9):2528-2537. [Zhao Yifei, Zou Xinqing,Xu Xinwanghao.Extreme precipitation events in the Pearl River Basin and its relationship with atmospheric circulation[J]. Chinese Journal of Ecology,2O14,33(9): 2528-2537.]   
[2] 陈星任,杨岳,何佳男,等.近60年中国持续极端降水时空变化 特征及其环流因素分析[J].长江流域资源与环境,2020,29(9): 2068-2O81.[Chen Xingren,Yang Yue,He Jianan,et al.Analysis on the characteristics of temporal and spatial changes of continuous extreme precipitation in China and its circulation factors in the past 6O years[J]. Resources and Environment in the Yangtze Basin,2020,29(9): 2068-2081.]   
[3]刘昌新,张海玲,吴静.基于SSPs情景的中国极端降水影响评 估[J].环境保护,2021,49(8):29-34.[Liu Changxin, Zhang Hailing,Wu Jing.Assessment of the impact of extreme precipitation in China based on SSPs scenarios[J].Environmental Protection,2021, 49(8): 29-34.]   
[4] 马梦阳,韩宇平，王庆明,等.海河流域极端降水时空变化规律 及其与大气环流的关系[J].水电能源科学,2019,37(6):1-4. [Ma Mengyang,Han Yuping,Wang Qingming,et al. The temporal and spatial variation of extreme precipitation in the Haihe River Basin and its relationship with atmospheric circulation[J].Hydropower Energy Science,2019,37(6): 1-4.]

[5]周旗,张海宁,任源鑫.1961—2016年渭河流域极端降水事件

研究[J].地理科学,2020,40(5): 833-841.[Zhou Qi, Zhang Haining,Ren Yuanxin.A study on extreme precipitation events in the Weihe River Basin from 1961 to 2016[J]. Chinese Journal of Geography,2020,40(5): 833-841.]   
[6]邹磊,余江游,王飞宇,等.渭河流域极端降水时空演变规律及 其对大气环流因子的响应[J].干旱区研究,2021,38(3):764- 774.[Zou Lei, Yu Jiangyou,Wang Feiyu,et al. The temporal and spatial evolution of extreme precipitation in the Weihe River Basin and its response to atmospheric circulation factors[J].Arid Zone Research,2021,38(3): 764-774.]   
[7]戴声佩,罗红霞,李茂芬,等.1959—2016年华南地区极端降水 事件变化特征[J/OL].中国农业资源与区划:1-17[2021-11-30]. http: //kns.cnki.net/kcms/detail/11.3513.S.20210607.1505.040.ht - ml.[Dai Shengpei,Luo Hongxia,Li Maofen,et al. Variation characteristics of extreme precipitation events in South China from 1959 to 2O16[J/OL]. China Agricultural Resources and Regional Planning:1-17[2021-11-30].htp://kns.cnki.net/kcms/detail/11.3 513.S.20210607.1505.040.html.]   
[8]杜懿,龙铠豪,王大洋,等.基于机器学习方法的安徽省年降水 量预测[J].水电能源科学,2020,38(7):5-7,41.[Du Yi,Long Kaihao,Wang Dayang, et al.Prediction of annual precipitation in anhui province based on machine learning method[J]. Hydropower Energy Science, 2020,38(7): 5-7,41.]   
[9]罗志文,王小军,刘梦洋,等.基于地区线性矩法的陕西省极端 降水时空特征[J].干旱区研究,2021,38(5):1295-1305.[Luo Zhiwen,Wang Xiaojun,Liu Mengyang,etal.Temporal andspatial characteristics of extreme precipitation in Shaanxi Province based on regional linear moment method[J].Arid Zone Research, 2021, 38(5): 1295-1305.]   
[10] 刘燕飞,隆霄,王晖.陕西中西部地区一次暴雨过程的数值模拟 研究[J].高原气象,2015,34(2):378-388[Liu Yanfei,Long Xiao,Wang Hui.Numerical simulation studies on a rainstorm in central Western Shaanxi Province[J].Plateau Meteorology,2015, 34(2): 378-388.]   
[11] 白爱娟,施能.东亚冬、夏季风强度指数及其与陕西降水变化的 关系[J].南京气象学院学报,2004,37(4): 519-526.[Bai Aijuan, Shi Neng. East Asian winter/summer monsoon intensity index and itsrelationship with precipitation change in Shaanxi Provine[J]. Journal of Nanjing Institute of Meteorology,2004,37(4): 519-526.]   
[12] 周雅蔓,刘晶,赵勇,等.春季热带海温与北疆夏季极端降水的 关系研究[J].冰川冻土,2021,43(4):1166-1178.[Zhou Yaman, Liu Jing,Zhao Yong,et al. Study on the relationship between spring tropical sea temperature and extreme summer precipitation innorthern Xinjiang[J].Journal of Glaciologyand Geocryology, 2021, 43(4): 1166-1178.]   
[13] 张冲,赵景波.厄尔尼诺/拉尼娜事件对陕西气候的影响[J].陕 西师范大学学报(自然科学版),2010,38(5):98-104.[Zhang Chong,Zhao Jingbo.The impact of El Nino/La Nina event on the climate of Shaanxi[J]. Journal of Shaanxi Normal University(Natu

ral Science Edition),2010,38(5): 98-104.]

[14] 窦睿音,延军平.1960—2010年关中地区旱涝灾害对气候变化 的响应[J].湖南农业大学学报(自然科学版),2012,38(5):542-   
547.[Dou Ruiyin,Yan Junping.Responses of drought and flood disasters in Guanzhong area from 196O to 2O1O to climate change [J].Journal of Hunan Agricultural University (Natural Science Edition),2012,38(5): 542-547.] [15] 刘岩,李晶,秦克玉,等.基于情景的关中平原土地利用和生态 系统服务预测及变化分析[J].陕西师范大学学报（自然科学 版),2018,46(2): 95-103.[Liu Yan,Li Jing,Qin Keyu,et al. Scenario-based prediction and change analysis of land use and ecosystem services in the Guanzhong Plain[J]. Journal of Shaanxi Normal University(Natural Science Edition),2018,46(2): 95-103.] [16]Zhou B,Xu Y,Wu J,et al.Changes in temperature and precipitation extreme indices over China: Analysis of a high-resolution grid dataset[J]. International Journal of Climatology,2O16,36(3): 1051-   
1066. [17]王刚,严登华,张冬冬,等.海河流域1961—2010年极端气温与 降水变化趋势分析[J].南水北调与水利科技，2014,12(1):1-6. [Wang Gang,Yan Denghua,Zhang Dongdong,et al.Analysis on the trend of extreme temperature and precipitation in the Haihe River Basin from 1961 to 201O[J].South-to-North Water Diversion and Water Conservancy Science and Technology,2014,12(1): 1-6.]   
[18]Khaled H Hamed. Trend detection in hydrologic data: The MannKendall trend test under the scaling hypothesis[J]. Journal of Hydrology,2008,349(3-4): 350-363.doi: 10.1016/j.jhydrol.2007. 11.009.   
[19]Grinsted A,Moore JC,Jevrejeva S.Application of the cross wavelet transform and wavelet coherence to geophysical time series[J]. Nonlinear Processes in Geophysics,2004,11(5/6): 561-566.doi: 10.5194/npg-11-561-2004.   
[20] 邵骏.基于交叉小波变换的水文多尺度相关分析[J].水力发电 学报,2013,32(2):22-26.[Shao Jun.Hydrological multi-scale correlation analysis based on cross wavelet transform[J].Journal of Hydroelectric Engineering,2013,32(2): 22-26.]   
[21] 张菁,张珂,王晟,等.陕甘宁三河源区1971—2017年极端降水 时空变化分析[J].河海大学学报(自然科学版),2021,49(3): 288-294.[Zhang Jing, Zhang Ke,Wang Sheng,et al. Analysis of the temporal and spatial changes of extreme precipitation in the source area of the Three Rivers in Shaanxi,Gansu and Ningxia from 1971 to 2O17[J]. Journal of Hohai University (Natural Science Edition),2021,49(3): 288-294.]   
[22]Lachaux JP,Lutz A,Rudrauf D,et al.Estimating the time-course of coherence between single-trial brain signals:An introduction to wavelet coherence[J]. Neurophysiologie Clinique/Clinical Neurophysiology,2002,32(3): 157-174.

# Spatial-temporal variations in extreme precipitation and their relationship with atmospheric circulation in the Guanzhong Plain

DING Yingying'， QIU Dexun²， WU Changxue'， MU Xingmin'²， GAO Peng1,² (1.State KeyLaboratoryof Soil Erosionand DrylandFarming onthe Loess Plateau,Instituteof Soil and Water Conservation,Northwest A&F University,Yangling 712100,Shaanxi,China; 2.Institute ofSoiland Water Conservation,Chinese AcademyofSciencesand Ministryof Water Resources,Yangling 7121Oo,Shaanxi,China)

Abstract: Based on daily precipitation data collected from 13 meteorological stations in the Guanzhong Plain in 1957-2019,the extreme precipitation indices were calculated and their spatial-temporal variation characteristics were analyzed. Specifically,the correlation between extreme precipitation and atmospheric general circulation was explored using a unitary linear regression method,Pearson correlation analysis,and wavelet coherence analysis.The results showed the following.(1） Extreme precipitation intensity showed an increasing trend at a rate of $0 . 0 0 7 \ \mathrm { m m \cdot d ^ { - 1 } \cdot ( 1 0 a ) ^ { - 1 } }$ , whereas other extreme precipitation indices showed a decreasing trend in which the annual total extreme precipitation showed the most pronounced decreased with a rate of $- 5 . 5 2 8 ~ \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ Aditionaly， none of the extreme precipitation indices had a significant mutation point. (2） The extreme precipitation indices were higher in the south and lower in the north, with a significant spatial difference detected. (3) Only the southern oscilltion index (SOl) had a significant effect on extreme precipitation.The larger the SOI value,the more likely it was to rain lesson the Guanzhong Plain.These results provide a theoretical basis for flood disaster prevention and control on the Guanzhong Plain.

Keywords: Guanzhong Plain; extreme precipitation; spatial-temporal variation; atmospheric circulation