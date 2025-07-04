# 2000—2019年中国脑瘤死亡趋势分析及预测

10.12114/j.issn.1007-9572.2022.0630

段朝晖」，张敏」，徐杰茹」，熊文婧²，陈磊」，赵湘铃」，张译匀」，让蔚清1\*基金项目：国家自然科学基金项目“基于肿瘤放射治疗的损伤预警指标体系筛选与预测模型研究”（项目编号：81673107)

1.421001湖南省衡阳市，南华大学公共卫生学院2.421001湖南省衡阳市，南华大学附属第一医院中医科\*通信作者：让蔚清，教授，硕士生导师；Email:nhurwq $@$ 126.com【摘要】背景在世界范围内脑瘤对人群健康的危害已获得广泛关注，但目前仍未有针对我国脑瘤死亡趋势分析与预测的有关研究。目的分析 2000—2019年中国脑及中枢神经系统癌症(简称脑瘤)的死亡变化趋势，并预测未来5年脑瘤的粗死亡率，为脑瘤防治提供参考。方法收集全球健康数据交换数据库(Global Health Data Exchange，GHDx)中 2000—2019 年中国脑瘤死亡数据，应用Joinpoint回归模型分析死亡趋势，采用内生因子估算法（intrinsic estimator，IE 算法）和年龄-时期-队列模型（Age-period-cohort model，APC 模型）估计死亡率的年龄、时期和出生队列效应。通过 R(4.1.3)对2000—2019 年脑癌死亡数据建立GM(1,1)模型进行预测。结果2000—2019 年中国男、女性脑瘤的标化死亡率呈下降趋势。APC 模型显示，中国男女脑瘤的死亡风险均随年龄和时期增加而增大，晚出生队列其脑瘤的死亡风险小于较早出生队列。模型预测 2019年后我国脑瘤的粗死亡率持续上升，2024年粗死亡率达到4.54/10万。结论2000—2019年，中国脑瘤的标化死亡率总体呈现下降趋势，死亡风险随着年龄的增大和时期的推移而增大，越早出生其死亡风险越大。预测结果显示未来5年脑瘤发病率与死亡率均持续上升，我国脑瘤防控形势依旧严峻，应加强我国脑瘤高发人群的防治宣传工作，提倡良好正确的生活方式，降低脑瘤的疾病负担。

【关键词】 脑瘤；死亡趋势；年龄一时期一队列模型；预测

Analysis and prediction of brain tumor death trend in China from 2OoO to 2019   
DUAN Zhaohui’， ZHANG Minl，XU Jieru’， XIONG Wenjing²，CHEN Lei’， ZHAO Xianglingl， ZHANG   
Yiyun'， Rang Weiqingl \*   
1.Shool of Public Health，University of South China，Hengyang， 421001   
2.Traditional Chinese Medicine Department， The First Affiliated Hospital Of University Of South China,   
Hengyang，421001   
\*Corresponding authors: Rang Weiqing， Professor， Master Supervisor; Email : nhurwq@126.com

【Abstract】BackgroundWorldwide,the harm of brain tumor to people's health has atracted extensive atention,but there is stillno research on the analysis of the death trend of brain tumor in China.Objective To analyze the death trend of brain and central nervous system cancer (brain tumor) in China from 2000 to 2019,and predict the crude mortality ofbrain tumor in the next five years, so as to provide reference for the prevention and treatment of brain tumor in China.MethodsThe mortality data of brain tumors in China from 2000 to 2019 in the Global Health Data Exchange(GHDx) were collected,and the mortality trend was analyzed by using Joinpoint regresson model,and the mortality rate was estimated by intrinsic estimator (IE) and Age-period-cohort model (APC model).Through R (4.1.3), GM(1,1） model is established for brain cancer death data from 20o0 to 2019,and the trend in the next five years is predicted.ResultsFrom 2000 to 2019,the standardized mortality rate of brain tumors in Chinese men and women showed a downward trend.The APC model shows that the death risk of brain tumors in Chinese men and women increases with the increase of age and period,and the death risk of brain tumors in the late birth cohort is lower than that in the early birth cohort.The model predicts that the crude mortality of brain tumors in China will continue to rise after 2O19,and the crude mortality will reach $4 . 5 4 / 1 0 ^ { 5 }$ in 2024.Conclusion From 2000 to 2019, the standardized mortality rate of brain tumors in China generally showed a downward trend,and the risk of death increased with the increase of age and the passage of time.The earlier the birth,the greater the risk of death.The prediction results show that the incidence rate and mortality of brain tumors will continue to rise in the next five years. The situation of brain tumor prevention and control in China is still grim. It is necessry to strengthen the prevention and control publicity of people with high incidence of brain tumors in China, advocate a good and correct lifestyle, and reduce the disease burden of brain tumors.

【Keywords】 Brain tumor; Death trend; Age-period-cohort model;Prediction

前言

据我国国家癌症中心数据显示，2016 年因脑瘤死亡的病例共 16351例，位居我国癌症死亡谱第10位1]。2020年脑瘤死亡例数最多的前三位国家分别是中国、印度和美国[2]。脑瘤一旦发生均会导致颅内压升高并压迫脑组织，患者发病痛苦且导致严重的中枢神经损伤[3]。也可能引起严重的残疾，包括癫痫发作、记忆不良或语言问题，以及身体功能障碍[4]。因脑瘤的发病部位特殊、诊断手段复杂以及我国人口老龄化的逐渐加重，我国脑瘤的疾病负担也正逐年加重[5.6]，是当前我国慢病防治的难点问题。因此，开展中国脑瘤长期的流行病学特征研究，适当预测未来变化有助于获取脑瘤的病因线索，并及时提供科学有效的预防控制手段。

本文提取GBD 2019数据库中2000—2019 年中国脑瘤死亡数据，利用 Joinpoint回归模型、APC 模型对死亡率进行分析与评估，再通过灰色模型GM(1,1)对脑瘤未来5年的死亡趋势进行预测，为我国脑瘤的预防控制、减轻疾病负担提供依据。

# 1资料与方法

# 1.1 数据来源

数据来源于GBD 2019数据库（官网：https://www.healthdata.org/），可分析全球195个不同国家的328种疾病和伤害的流行病学特征(发病率、患病率、死亡率等)7]，来评估评估疾病负担。还能通过分析发病部位、获得治疗和治疗质量等指标分析疾病对患者生存的影响[8]。本文从GBD 2019数据库中提取出 2000—2019年中国脑瘤的死亡数据[9]：死亡粗率(crude mortality rate，CMR）。根据国际疾病分类（Intermational classification of disease，ICD）第十版代码(ICD10)来确定脑瘤病种，其中大脑、中枢神经系统为C70-C72。

# 1.2 研究方法

# 1.2.1 基本指标

整理并汇总从GBD 2019数据库中提取的 2000—2019 年中国脑瘤的死亡数据，按照性别与年龄进行分层，计算年龄标化死亡率(age-standardized mortality rates，ASMR)。其中标准人口构成是该数据库提供的 2019 年的全球人□数据[10]。

# 1.2.2Joinpoint回归模型

该模型由美国国立癌症研究中心研发，模型分析的基本思想是利用基于 Poissn 分布的对数线性模型拟合癌症的死亡率，将死亡率的变化趋势分成若干区段，不同区段的连接点称为转折点并通过蒙特卡洛置换检验法判断转折点的位置、个数以与 $P$ 值[11]。

模型方程为：

$$
E ( y \vert x ) = \beta _ { 0 } + \beta _ { 1 } x + \delta _ { 1 } ( x - \tau _ { 1 } ) ^ { + } + . . . + \delta _ { k } ( x - \tau _ { k } ) ^ { + }
$$

方程中:y代表脑瘤死亡率， $\mathbf { x }$ 代表观察年份， $\beta$ 是模型中的常数项, $\delta$ 是各个分段函数的回归系数 $( \mathrm { i } { = } 1 , 2 , 3 , { \ldots } { \ldots } )$ ，$\tau$ 表示转折点 $( \mathrm { i } { = } 1 , 2 , 3 , { \ldots } { \ldots } , \mathrm { k } )$ 。当 $( x - \tau _ { k } ) { \geq } 0$ 时， $\bigl ( x - \tau _ { k } \bigr ) ^ { + } = \bigl ( x - \tau _ { k } \bigr )$ 。当 $( x - \tau _ { k } ) < 0$ 时， $( x - \tau _ { k } ) = 0$ 。

# 1.2.3 APC模型

APC 模型以Poisson 分布为基础，将研究对象死亡率的趋势情况用年龄、时期、出生队列这三个维度表示，在控制交互效应后定量分析影响事件发生风险大小的多元回归模型[12,13]。由于APC 模型中出生队列等于时期减去年龄，三者间存在严重的共线性，这导致APC 模型可以求出无数组解却无法求出唯一的效应估计值，且Poisson 分布要求各参数之间相互独立所以应解决独立性问题。为避免这些缺点，本文应用了内生因子估算法(intrinsic estimator，IE 算法），IE 算法是一种可解决效应参数唯一值不可估计问题的方法，在解决模型可估性问题的同时又可以得到唯一的解，该方法不需要限制条件假设、应用范围广泛[14,15]。

本研究应用 Stata15.0，采用APC 模型，来描述和估计年龄、时期与出生队列效应对脑瘤死亡的影响。APC 模型的表达式为：

$$
I n [ R _ { i j k } ] = \mu + \alpha _ { i } + \beta _ { j } + \gamma _ { k }
$$

表达式中： $I n [ R _ { i j k } ]$ 表示中国脑瘤死亡率的自然对数； $\mu$ 为截距； $\alpha _ { i }$ 为第 $\mathrm { ~ i ~ }$ 个年龄组的年龄效应； $\beta _ { j }$ 代表第j个时期的时期效应；表示第 $\mathbf { k }$ 个队列的队列效应。

# 1.2.4 GM(1,1)模型

GM(1,1)模型是灰色预测模型的核心与基础，主要由灰导数、关联度等数学思想建立，是数量经济模型的一个

子结构[I。该模型的优点是不依靠大量样本数据，也不利用统计学思想去挖掘信息规律，更多的是依靠累加生成对原始数据序列进行变换，并从累加生成序列中挖掘数据的规律[16]。

GM(1,1)模型应用于社会各领域，尤其是在"小样本，贫信息，数据不完全掌握"的情况被广泛地使用[17]。

灰色数列GM(1,1)模型的建立与预测步骤如下：

（1）设原始数据序列：

$$
X _ { ( 0 ) } = ( X _ { ( 0 ) } ^ { ( 1 ) } , X _ { ( 0 ) } ^ { ( 2 ) } , . . . , X _ { ( 0 ) } ^ { ( n ) } )
$$

（2）生成累加序列与滑动平均序列：

将上述原始数据序列进行一次累加生成 AGO（Accumulating Generationo Perator）的递增数列： $X _ { ( 1 ) }$ ，并计算出滑动平均序列： $X _ { ( k ) }$ 。

$$
\begin{array} { c } { { \displaystyle { \cal X } _ { ( 1 ) } = \big ( { \cal X } _ { ( 1 ) } ^ { ( 1 ) } , { \cal X } _ { ( 2 ) } ^ { ( 1 ) } , . . . , { \cal X } _ { ( n ) } ^ { ( 1 ) } \big ) } } \\ { { \displaystyle { \cal X } _ { ( k ) } ^ { 2 } = \displaystyle \frac { 1 } { 2 } ( { \cal X } _ { k } ^ { 1 } + { \cal X } _ { k - 1 } ^ { 1 } ) } } \end{array}
$$

（3）指数规律检验与光滑性检验：

当 $\scriptstyle \mathrm { t } > 3$ 时， $\sigma _ { \left( t + 1 \right) } \bigtriangledown$ （1，1.5）则满足准指数规律， $\rho ( t + 1 ) < 0 . 5$ 满足准光滑条件。

(4）建立GM(1,1)方程：

$$
\stackrel { \wedge } { X } { } ^ { ( 1 ) } = ( X _ { ( 1 ) } ^ { ( 0 ) } - \frac { u } { a } ) e ^ { - a ( k - 1 ) } + \frac { u } { a }
$$

其中a为发展系数， $\mathrm { ~  ~ u ~ }$ 为灰色作用量,k=0,1,2,3,..，n

（5）生成预测值 $X _ { ( 0 ) } ^ { \wedge }$ ：该过程通过累减还原实现。

（6）预测效果检验

GM(1,1)模型的预测效果检验，可用后验差比值（C）和小误差概率（p）来检验。

$$
C = \frac { S _ { 2 } } { S _ { 1 } }
$$

$$
p = p \Big \{ | \varepsilon ( t ) - \stackrel { \wedge } { \varepsilon } \ \big | < 0 . 6 7 4 5 S _ { 1 } \ \Big \}
$$

式中： $\mathbf { S } _ { 1 }$ 、 $\mathbf { S } _ { 2 }$ 分别为实际数、残差的标准差； $\varepsilon$ 为残差的平均数。模型预测效果判断的标准是：□模型判为优：$\mathrm { p } { \geq } 0 . 9 5$ 且 $\mathrm { C } { \le } 0 . 3 5$ ；□模型判为良： $\mathfrak { p } { \geq } 0 . 8 0$ 且 $\mathrm { C } { \le } 0 . 5 0$ ；□模型判为中： $\mathrm { p } { \geq } 0 . 7 0$ 且 $\mathrm { C } { \leq } 0 . 6 5$ ；□模型判为差： $\mathrm { p } { < } 0 . 7 0$ 且$_ { \mathrm { C > 0 } . 6 5 ^ { [ 1 4 ] } }$ 。

（7）精度检验

GM(1,1)模型的精度检验，可用平均绝对百分比误差（meanabsolutepercenterror，MAPE）与模型精度 $\rho$ 。若MAPE□ $10 \%$ ，可认为模型满足精度要求。

# 1.3 统计学方法

使用Joinpoint Regression Program 4.7.0.0软件进行回归分析，分别用男女两组人群的脑瘤 ASMR拟合Joinpoint模型计算年度变化百分比（annual percent change，APC)和平均年度变化百分比（average annual percent change,AAPC)，评价2000—2019 中国的脑瘤死亡趋势。Joinpoint 模型将拟合分析出脑瘤 ASMR 在不同年份间的转折变化情况，当 $\mathbf { A P C } { < } 0$ 时表示死亡率随时间下降；当 $\mathrm { A P C } { > } 0$ 时表示死亡率随时间上升；若无转折点，则APC $\displaystyle : =$ AAPC,表示该组数据总体趋势呈单调下降或上升[18]。

根据IE 算法估算年龄、时期和出生队列效应的APC模型中，将研究对象的年龄以5岁为一组距进行划分，共分 20 个年龄组。APC 模型中要求时期组距与年龄组距相等，因此以不间断的年为一组距将 2000—2019年划分为4个时期；相应的将1904—2018年出生队列以不间断的5年为一组距，共划分为23个出生队列。评价中国脑瘤在不同的年龄、时期、出生队列上的死亡率变化情况。并计算出模型的效应系数，当系数小于零时表明死亡率降低，大于零时表示死亡率增加，数值越高则表明死亡率越高。以上所有检验均为双侧检验，检验水准 $\scriptstyle { \mathfrak { a } } = 0 . 0 5$ 。

GM(1,1)模型采用R(4.1.3)软件建立并进行预测。检验水准 $\scriptstyle { \mathfrak { a } } = 0 . 0 5$ 。

# 2结果

2.1 脑瘤粗死亡率及标化死亡率的变化趋势

2000—2019中国脑瘤CMR呈现上升趋势。全国脑瘤CMR从3.59/10万升至4.47/10万；男性CMR从 $3 . 8 6 / 1 0$ 万升至4.92/10万；女性CMR从3.29/10万升至4.00/10万。中国脑瘤ASMR总体呈现下降趋势。全国脑瘤 ASMR从4.10/10万降至3.63/10万，在 2000—2019 年间下降了 $1 1 . 4 6 \%$ ；男性ASMR从 $4 . 5 8 / 1 0$ 万降至 $4 . 2 0 / 1 0$ 万，在2000—2019 年间下降了 $8 . 3 0 \%$ ；女性脑瘤 ASMR从3.66/10万降至3.11/10万，在2000—2019年间下降了 $1 5 . 0 3 \%$ 。见图1。

![](images/aeec8cdb84a7d3ee5f13f77f059f35e4bddb4c86e3879668d296c56e1151fea3.jpg)  
图12000一2019 年中国脑瘤CMR 和ASMR在全国、性别间的变化趋势 Figure1Trends ofCMR and ASMR ofbrain tumors in China from 2000 to 2019 acrossthe country and between sexes

Joinpoint回归模型分析显示：从整体上看全国脑瘤ASMR与不同性别ASMR均呈现下降趋势，AAPC值分别为： $- 0 . 6 8 \%$ 、 $- 0 . 4 7 \%$ 、 $- 0 . 8 7 \%$ ，经检验均有统计学意义，说明在2000—2019 年期间全国脑瘤ASMR平均每年下降$0 . 6 8 \%$ ，全国男性脑瘤ASMR平均每年下降 $0 . 4 7 \%$ ，全国女性脑瘤ASMR平均每年下降 $0 . 8 7 \%$ 。其中全国脑瘤ASMR在2014—2019年的APC 值经检验无统计学意义，说明在这个期间内全国脑瘤的ASMR无变化，而男性脑瘤在2000—2004、2015—2019年的APC 值无统计学意义，说明这两个时期中国男性脑瘤的ASMR无变化。见表1。

表12000—2019 年中国脑瘤 ASMR 的变化趋势  
Table1Trends of brain tumor ASMR in China from 20oO to 2019   

<html><body><table><tr><td rowspan="2">性别</td><td colspan="7">标化死亡率(/105)</td></tr><tr><td rowspan="2">年份</td><td colspan="3">年变化百分比（APC)</td><td colspan="3">年平均变化百分比（AAPC)</td></tr><tr><td></td><td>APC(95%CI)</td><td>T值</td><td>P值</td><td>AAPC(95%CI)</td><td>T值</td><td>P值</td></tr><tr><td>全国</td><td>2000—2014</td><td>-1.02a(-1.08—-0.96)</td><td>-34.06</td><td><0.001</td><td>-0.68a(-0.76—-0.60)</td><td>-16.68</td><td><0.001</td></tr></table></body></html>

# ChinaXiv合作期刊

<html><body><table><tr><td rowspan="5">男性</td><td>2014—2019</td><td>0.27(-0.01—0.55)</td><td>2.03</td><td>0.060</td><td></td><td></td><td></td></tr><tr><td>2000—2004</td><td>-0.16(-0.52—0.20)</td><td></td><td>-0.99</td><td>0.346</td><td></td><td></td></tr><tr><td>2004—2007</td><td>-1.33a(-2.24—-0.24)</td><td></td><td>-2.74</td><td>0.023</td><td>-0.47a(-0.66—0.29)</td><td>-5.11 <0.001</td></tr><tr><td>2007—2015</td><td>-0.60a(-0.74—-0.46)</td><td></td><td>-9.57</td><td><0.001</td><td></td><td></td></tr><tr><td>2015—2019</td><td>0.11(-0.20—0.42)</td><td></td><td>0.81</td><td>0.441</td><td></td><td></td></tr><tr><td rowspan="3">女性</td><td>2000—2006</td><td>-1.55a(-1.73—-1.37)</td><td></td><td>-18.87</td><td><0.001</td><td></td><td></td></tr><tr><td>2006—2014</td><td>-1.21a(-1.35—-1.07)</td><td>-19.10</td><td><0.001</td><td>-0.87a(-0.96—-0.79)</td><td>-19.17</td><td><0.001</td></tr><tr><td>2014—2019</td><td>0.49a(0.27—0.71)</td><td>4.88</td><td><0.001</td><td></td><td></td><td></td></tr></table></body></html>

注：a表示 $P { < } 0 . 0 5$ ，差异有统计学意义 Note: a means $P { < } 0 . 0 5$ , and the difference is statistically significant.

# 2.2 脑瘤死亡效应的APC模型分析

2.2.1 中国男性脑瘤死亡APC模型分析

年龄效应结果显示，中国男性脑瘤死亡风险随年龄的变化呈现先降低后升高再降低的趋势， $2 0 \sim 2 5$ 岁年龄组死亡风险最低，效应系数 $\mathrm { : = } \mathrm { - } 1 . 2 8$ 。 $9 0 \mathrm { \sim } 9 5$ 岁年龄组死亡风险最高，效应系数 $: = 1 . 2 5$ 。从最低效应值到最高效应值增长幅度为 $1 9 7 . 6 6 \%$ 。时期效应结果显示，中国男性脑瘤死亡风险随时期的变化呈现逐渐上升的趋势，2000—2004 年死亡风险最低，效应系数 $\scriptstyle : = - 0 . 0 9$ ，2015—2019年死亡风险最高，效应系数 $_ { = 0 . 0 8 }$ 。出生队列效应结果显示，中国男性脑瘤死亡风险随队列的变化呈现逐渐下降的趋势，效应系数从1904—1908年队列组的0.62降低至2014—2019年队列组的-1.28。见图2。

![](images/b90e7407646ff4e43a15c20efb675f69f0fc9ceba626bc6ac74ef7582da40713.jpg)  
图22000—2019 年中国男性脑瘤死亡风险的年龄、时期、队列效应系数及 $9 5 \% C \mathrm { I }$

Figure 2Age,period, cohort effect coefficient and $9 5 \% C \mathrm { I }$ of Chinese male brain tumor mortality from 20o0 to 2019

# 2.2.2中国女性脑瘤死亡APC 模型分析

年龄效应结果显示，中国女性脑瘤死亡风险随年龄的变化呈现升高的趋势， $2 5 \sim < 3 0$ 岁年龄组死亡风险最低，效应系数 $\mathrel { \mathop : } = - 1 . 1 9$ 。95岁以上年龄组死亡风险最高，效应系数 $: = 1 . 2 9$ 。从最低效应系数到最高效应系数增长幅度为

$20 8 . 4 0 \%$ 。时期效应结果显示，中国女性脑瘤死亡风险随时期的变化呈现逐渐上升的趋势，2000—2004年效应系数最低，为-0.03，2015—2019年效应系数最高，为0.04。出生队列效应结果显示，中国女性脑瘤死亡风险随队列的变化呈现先升高后下降的趋势，效应系数从1904—1908年队列组的0.36升高到1929—1933年队列组的0.57，随后逐渐降低，2014—2019年队列组的效应系数最低，为-1.16。见图3。

![](images/408862ce70d2aef971ec3d49d42dc723b0d74272c637100d9bb8615f455e3dc1.jpg)  
图32000—2019 年中国女性脑瘤死亡风险的年龄、时期、队列效应系数及 $9 5 \% C \mathrm { I }$ Figure 3Age, period, cohort effect coefficient and $9 5 \% C \mathrm { I }$ of Chinese female brain tumor mortality from 20o0 to 2019

# 2.3 GM(1,1)模型预测结果

# 2.3.1 GM(1,1)模型可行性检验

首先对原始数据序列进行累加并计算滑动平均序列， $\mathbf { X } _ { ( 0 ) }$ 做光滑性检验与指数规律检验。结果显示当 $\mathbf { k } { > } 3$ 时，检验结果为 $\rho _ { ( k ) } < 0 . 5$ ， $\sigma _ { ( k ) } \sqcap ( 1 , 1 . 5 )$ ，满足光滑条件和指数规律。见表2。

表22000—2019 年中国脑瘤粗死亡率(/10万)序列及其可行性检验  
.able 2sequence and feasibility test of crude mortality rate $( / 1 0 ^ { 5 } )$ of brain tumors in China from 2000 to 201   

<html><body><table><tr><td>年份(k)</td><td>粗死亡率</td><td>累加序列</td><td>滑动平均序列</td><td>指数规律性 检验(级比)</td><td>光滑性检验 （光滑比）</td></tr><tr><td>2000</td><td>3.59</td><td>3.59</td><td></td><td>-</td><td></td></tr><tr><td>2001</td><td>3.62</td><td>7.20</td><td>5.39</td><td>2.01</td><td>1.01</td></tr><tr><td>2002</td><td>3.64</td><td>10.84</td><td>9.02</td><td>1.51</td><td>0.51</td></tr><tr><td>2003</td><td>3.64</td><td>14.48</td><td>12.66</td><td>1.34</td><td>0.34</td></tr><tr><td>2004</td><td>3.68</td><td>18.16</td><td>16.32</td><td>1.25</td><td>0.25</td></tr><tr><td>2005</td><td>3.69</td><td>21.85</td><td>20.00</td><td>1.20</td><td>0.20</td></tr><tr><td>2006</td><td>3.68</td><td>25.53</td><td>23.69</td><td>1.17</td><td>0.17</td></tr><tr><td>2007</td><td>3.70</td><td>29.24</td><td>27.38</td><td>1.15</td><td>0.15</td></tr><tr><td>2008</td><td>3.75</td><td>32.98</td><td>31.11</td><td>1.13</td><td>0.13</td></tr><tr><td>2009</td><td>3.79</td><td>36.78</td><td>34.88</td><td>1.12</td><td>0.12</td></tr><tr><td>2010</td><td>3.83</td><td>40.61</td><td>38.70</td><td>1.10</td><td>0.10</td></tr><tr><td>2011</td><td>3.85</td><td>44.46</td><td>42.54</td><td>1.09</td><td>0.09</td></tr><tr><td>2012</td><td>3.88</td><td>48.34</td><td>46.40</td><td>1.09</td><td>0.09</td></tr><tr><td>2013</td><td>3.91</td><td>52.25</td><td>50.30</td><td>1.08</td><td>0.08</td></tr><tr><td>2014</td><td>3.99</td><td>56.25</td><td>54.25</td><td>1.08</td><td>0.08</td></tr><tr><td>2015</td><td>4.05</td><td>60.30</td><td>58.27</td><td>1.07</td><td>0.07</td></tr></table></body></html>

<html><body><table><tr><td>2016</td><td>4.15</td><td>64.45</td><td>62.38</td><td>1.07</td><td>0.07</td></tr><tr><td>2017</td><td>4.24</td><td>68.69</td><td>66.57</td><td>1.07</td><td>0.07</td></tr><tr><td>2018</td><td>4.35</td><td>73.05</td><td>70.87</td><td>1.06</td><td>0.06</td></tr><tr><td>2019</td><td>4.47</td><td>77.51</td><td>75.28</td><td>1.06</td><td>0.06</td></tr></table></body></html>

# 2.3.2模型构建与模型精度检验

由于模型通过了可行性检验故可对 $\boldsymbol { X } _ { ( k ) } ^ { 1 }$ 建立灰色数列GM(1,1)模型。利用 R4.1.3 软件构建GM(1,1)模型。结果显示：粗死亡率GM(1,1)模型的发展系数a 为-0.0112，灰色作用量b为3.4511。模型的方程为$\mathrm { Y _ { ( k ) } } = 3 1 1 . 7 4 8 3 \mathrm { e } ^ { 0 . 0 1 1 2 ( \mathrm { k } - 2 0 0 0 ) } - 3 0 8 . 1 6 1 8 \mathrm { , }$ 。用该模型预测 2000—2019 年死亡率与实际死亡率相比，残差检验其 MAPE 为$1 . 6 8 \%$ ，模型精度 $\rho$ 为 $9 8 . 3 2 \%$ ;后验差比值C为0.16，小误差概率p为1.00。模型的判断模型精度均为优，可用于未来5年的趋势预测。

# 2.3.3 模型预测结果

模型预测结果显示，未来5年中国脑瘤粗死亡率呈逐年上升趋势，在2020—2024年粗死亡率将会达到4.34/10万、4.39/10万、4.44/10万、4.49/10万、4.54/10万。见图4。

![](images/b70033e36379e30ef18993881d25632ecfbf49febd1d8867c84a11725bece167.jpg)  
图42000—2024年中国脑瘤死亡率模型拟合与预测结果

Figure 4Model fiting and prediction results of brain tumor mortality in China from 20oo to 2024

# 3讨论

世界范围内癌症的发病率和死亡率正在迅速增长。原因大多都与人口老龄化和人口增长，以及癌症主要风险因素的流行率和分布的变化，社会经济发展等有关[19]。脑瘤作为癌症的一种主要的类型，其发病率在近几十年来一直在上升[20]。全球脑瘤新病例的检出率存在巨大差异[21]，全球人口和流行病学趋势表明，在未来几十年里，脑瘤的发病率将急剧增加，特别是在低收入和中等收入国家[22]。2020 年全球癌症报告（GLOBOCAN 2020）的估计数。据估计，2020年全球脑瘤发病人数为308102人占总癌症发病人数的 $1 . 6 \%$ ，发病顺位居第19位；死亡人数为251329人占全部因癌症死亡的 $2 . 5 \%$ ，死亡顺位居第13 位[19]。我国脑肿瘤世界人口年龄调整的死亡率为3.63/10 万，其中男性脑肿瘤世标率为4.20/10万，女性脑肿瘤世标率为3.11/10万，均高于世界平均水平，提示我国脑瘤死亡负担依旧严峻。本研究结果显示,2000—2019年中国脑瘤 ASMR有起伏变化但总体呈现下降趋势。值得注意的是脑瘤ASMR下降至最低点后近年来又呈现出上升趋势，这也提示我国脑瘤死亡负担进一步加重。因此，了解脑瘤死亡趋势并对未来做出合理预测，对于降低脑瘤的疾病负担，控制我国脑瘤的进展有重要的实际意义。

随着年龄的增加，我国脑瘤死亡风险不论男女均呈现出先下降后持续增加再下降的趋势。我国男性与女性脑瘤死亡风险的年龄因素效应值在 $5 0 \mathrm { \sim } 5 5$ 岁年龄组及以下均为负值，55岁后均增长为正值。这表明55岁以上的人群随着年龄的增长脑瘤死亡风险也逐渐增大，这可能与环境的致癌因素如放射性、电磁波、微波、N一亚硝基化合物等暴露增加有关[23]，也可能与中老年人群的身体机能下降，我国人口老龄化有关[5]。国家卫生健康委发布的《2020年度国家老龄事业发展公报》提示，我国60周岁及以上人口为26402万人，占总人口的 $1 8 . 7 0 \%$ ；65周岁及以上人口为19064万人，占总人口的 $1 3 . 5 0 \% ^ { [ 2 4 ] }$ 。人口老龄化的加快导致脑瘤死亡风险及疾病负担加重。

脑瘤的死亡时期效应分析也发现。我国男性与女性脑瘤死亡时期效应在2010—2014年时期组以后均由负转正。这表明在 2000—2019 年期间，我国脑瘤死亡率随着时期的推移不论男女均呈现上升的趋势。这可能与我国经济社会的发展，不断推进城镇化、工业化、环境致癌因素的增多、人群接触危险因素的概率增加，人群不良生活方式如暴饮暴食、熬夜、吸烟、缺乏锻炼等有关。而男性的不健康生活习惯比例高于女性，同时男性的职业暴露机会也高于女性[25]，这些因素均可能会导致脑瘤的疾病负担在男性群体里更高。

研究发现，不论男女脑瘤死亡的队列效应均随着出生队列的推移先增大后持续减小。我国男性与女性脑瘤死亡风险在 1964一1968 出生队列组前为正值，这表示出生越晚的人群脑瘤的死亡风险越低。但达到最大队列效应的出生队列组男女之间并不一致。其中男性脑癌死亡的出生队列效应在1924—1928出生队列组最大，效应系数为0.63。而女性脑癌死亡的出生队列效应在1929—1933出生队列组最大，效应系数为0.57。在达到最大效应之后，出生队列效应出现下降的原因可能有：口上世纪30年代前出生的人群生活在战争时期，社会环境差、生活条件落后、生活资源缺乏、医疗卫生条件低下等都增加了人群脑瘤的死亡率。□随着我国经济水平的提高，医疗卫生系统的逐步完善，越来越多的早期脑瘤得到了提前的干预，一旦发生了脑瘤，患者也可以通过手术、放疗和中医药等手段来延长寿命。这大大降低了脑瘤的死亡率[26]。□随着健康教育信息的普及，不健康的生活习惯减少，人们的健康意识有了大幅提升[27]。

用GM(1,1)模型拟合我国脑瘤粗死亡率数据，模型精度判断为优可以进行外推。预测结果发现：未来5年我国脑瘤死亡率呈现持续上升的趋势，在2024年将达到4.54/10万。死亡率的持续升高也可能与我国缺乏简单易行的脑瘤早期筛查技术，早期脑瘤的症状与普通的偏头痛等类似并无明显特异症状，容易误诊漏诊[28]等有关。且截止目前脑瘤的治疗手段多为手术治疗，术后效果不理想也是脑瘤死亡率持续升高的重要原因之一。我国作为世界上最大的发展中国家，经济迅速发展的同时也带来了诸多健康问题电子产品的广泛使用、空气污染日益加重、杀虫剂等农药的使用及其他因素均可能与脑肿瘤的发病和死亡相关[29-31]。

本文收集了GBD中近20年中国脑瘤的死亡数据，且利用IE 法解决 APC模型的多重共线性问题，使结果更加可靠有助于更深入的挖掘出我国脑瘤死亡趋势背后的特征。但仅对我国脑瘤的死亡趋势进行了分析，缺少发病率数据难以分析与脑瘤发病有关的危险因素。GBD 数据库未将中国脑瘤城镇和农村死亡数据区分开，若在后续研究中获得了相关地区死亡数据，研究会更深入。综上所述，我国日益突出的人口老龄化问题也可能在未来进一步加重脑瘤的疾病负担。因此我国脑瘤防治工作应重点关注老年人群，同时减少职业暴露，戒烟、限酒、维持体重在适宜范围内，加强脑瘤预防知识的宣传教育。针对 50 岁以上的中老年脑瘤高发人群要进一步强化早诊早治工作[32]，寻找对脑瘤治疗效果较好的治疗手段，减轻疾病负担。强化我国脑瘤的肿瘤登记数据的收集与整理，特别是不同病理类型的脑瘤进行全面了解，这对于进一步降低我国脑瘤的疾病负担具有重要意义[6]。

作者贡献：段朝晖进行文章的构思、设计与撰写论文初稿；段朝晖、张敏负责资料的收集、整理与绘制图表等；张敏、徐杰茹、熊文婧进行论文修订；陈磊、赵湘铃、张译匀负责文章的质量控制与审校，对文章整体负责，监督管理；所有作者确认了论文的最终稿。

本文无利益冲突。

参考文献[1]赫捷，魏文强.2019中国肿瘤登记年报［M］．北京：人民卫生出版社，2019：193-197.

HE J,WEI WQ. China cancer registryannual report in 2O19[M].Beijing: People's Medical Publishing House,2019: 193-197.

[2] FERLAY J，ERVIK M，LAM F. Global cancer observatory ： cancertoday [ EB/OL][2022-03-10].https://gco.iarc.fr/today.

[3]沈洪兵．肿瘤分子流行病学［M］．北京：人民卫生出版社，2013：425-438.

SHENG HB.Molecular epidemiology of tumor [M].Beijing:People's Medical Publishing House，2013: 425-438. [4]DEANGELIS LM. Global consequences of malignant CNS tumours: acal to action [J].The Lancet Neurology,2019, 18(4). DOI: 10.1016/S1474-4422(19)30083-3.

[5]韩仁强，周金意，郑荣寿，等.2014年中国脑瘤发病与死亡分析[J]．中国肿瘤，2019,28(03):161-166.DOI:10.11735/j.issn.1004-0242.2019.03.A001.

Han RQ， Zhou JY， Zhen R S，et al.Incidence and Mortality of Brain Tumorin China， 2014 [J].China Cancer, 2019,28(03): 161-166.DOI: 10.11735/j.issn.1004-0242.2019.03.A001.

[6] 韩仁强，周金意，张思维，等.2015 年中国脑瘤发病与死亡分析[J]．中国肿瘤，2021,30(01):29-34.DOI:10.11735/j.issn.1004-0242.2021.01.A002.

HanRQ，Zhou JY， Zhang S W，et al.Incidence and Mortality of Brain Tumor in China，2015[J].China Cancer, 2021,30(01):29-34.DOI: 10.11735/j.issn.1004-0242.2021.01.A002.

[7] 李茜瑶，周莹，黄辉，等．疾病负担研究进展［J]．中国公共卫生，2018，34(05):777-780.DOI:10.11847/zgggws1118319.

Li X Y，Zhou Y，Huang H,etal. Progress in disease burden researches [J].Chinese Journal of Public Health,2018, 34(05): 777-780. DO1: 10.11847/zgggws1118319.

[8]CAMLLA M, GIUSEPPEL. Cancer statistics: a comparison between World Health Organization (WHO)and Global Burden of Disease (GBD)[J] .European jourmal of public health,2019,30(5). DOI:10.1093/eurpub/ckz216.

[9]屈彦，王天一，杨津，等.GBD 数据库的数据提取方法与流程[J］．中国循证心血管医学杂志，2019，11(09):1043-1046. DOI: 10.3969/j.issn.1674-4055.2019.09.04.

Qu Y，Wang TY，Yang J，et al.GBD database aplication and data extraction methods and processs [J] . Chinese Journal of Evidence-Based Medicine，2019，11(09): 1043-1046.DOI: 10.3969/jissn.1674-4055.2019.09.04.

[10] WANG H,ABBAS K M, ABBASIFARDM, etal. Global age-sex-specific fertilitymortalityhealthylifeexpectancy (HALE),and population estimates in 204 countries and teritories,1950-2019: a comprehensive demographic analysis fortheGlobal Burden of Disease Study2019[J]．The Lancet，2020，396(10258).DOI : 10.1016/S0140-6736(20)30977-6

[11] HYUNEJK,MICHAELPF,ERIC JF, et al. MIDTHUNE,etal. Permutation tests for joinpoint regresion with applications to cancer rates [J] . Statistics in medicine,20oo,19(3).

[12]许忠宇.2001\~2015 年深圳市肺癌发病的年龄—时期—队列模型分析［D」．华中科技大学，2018.

XU Z Y.Analysis of trends in incidence of lung cancer in Shenzhen during 2001-2015 with Age-Period-Cohort model [ D] .Huazhong University of Science and Technology， 2018.

[13] CLAYTON D,SCHIFFLERS E.Models for temporal variation incancer rates.I: Age-period-cohort models [J]. Statistics in medicine, 1987, 6(4).   
[14]FIENBERG SE,MASON WM.Identification and Estimation of Age-Period-Cohort Models in the Analysisof Discrete Archival Data [J] . Sociological Methodology, 1979,10.   
[15]YANG Y,SCHULHOFER WS,FU WJ.The intrinsic estimator forage-period-cohort analysis: what it is and how to use it[J] .American Journal of Sociology, 2008,113(6): 1697-1736.   
[16]张鹏,李颖男.GM(1,1)模型的优化与应用[J]．太原师范学院学报(自然科学版)，2021，20(04)：14-19+54. Zhang P，Li Y N.Optimization and Application of the GM(1,1） Model[J]. Journal of Taiyuan Normal University(Natural Science Edition)， 2021， 20(04): 14-19+54.   
[17]刘丽娜．灰色GM（1,1）模型的优化及其应用［D」．燕山大学，2014. LIU L N.Optimization and Application of the GM(1,1) Model [ D] . Yanshan University， 2014.   
[18]何家赓，侯建忠，闫贻忠.2005-2013年中国肿瘤登记地区女性乳腺癌死亡及疾病负担时间趋势分析［J］．中 华肿瘤防治杂志，2019，26(08):523-528.DOI:10.16073/j.cnki.cjcpt.2019.08.001. He JG，Hou J Z， Yan Y Z.Analysis on the time trends of female breast cancer death and disease burden in cancer registration areas in China,2005-2013 [J]. Chinese Journal of Cancer Prevention and Treatment，2019，26(08): 523-528. DOI: 10.16073/j.cnki.cjcpt.2019.08.001.   
[19] HYUNA S,JACQUES F,REBECCAL S,et al. Global Cancer Statistics 2020: GLOBOCANEstimates of Incidence and Mortality Worldwide for 36 Cancers in185 Countries[J]. CA: A Cancer Journal for Clinicians,2021,71(3).DOI: 10.3322/caac.21660.   
[20] SUNDEEP D,CHARLES FL, ZITA A S,TIMOTHY CR. Trends inbrain cancer incidence and survival in the United States: surveilance,epidemiologyand end results program,1973 to 2001[J].Neurosurg Focus.206;20(4):E1.DOI: 10.3171/foc.2006.20.4.E1.   
[21] SOHEIL H,GHOLAMREZA N,MOHAMMAD F, et al.The incidence of brain tumours in Iran: a systematic review and meta-analysis [J] .Adv Hum Biol. 2019;9(1):2-7.DOI: 10.4103/AIHB.AIHB_60_18.   
[22] PARKIN D M,BRAY F,FERLAY J,et al. Cancer in africa 2012[J].Cancer Epidemiol Prev Biomark. 2014;23(6):953-66.DOI: 10.1158/1055-9965.EPI-14-0281.   
[23] OSTROMQT,FRANCIS S S,BARNHOLTZ S JS.Epidemiology of Brain and Other CNS Tumors [J].Current Neurology and Neuroscience Reports,2021,21(12). DOI: 10.1007/s11910-021-01152-9.   
[24]本刊讯．国家卫生健康委老龄健康司发布《2020 年度国家老龄事业发展公报》[J]．上海护理，2021，21(11): 19. News of this journal. The Department of Aging Health of the National Health and Health Commission issued the 2020 National Bulletin on the Development of Ageing [J] . Shanghai Nursing， 2021，21(11):19.   
[25] POUCHIEU C,BALDII, GRUBER A ,et al. Descriptive epidemiologyand risk factors of primary central nervous systemtumors: Currnt knowledge [J].Revue Neurologique, 2016,172(1). DOI:10.1016/j.neurol.2015.10.007.   
[26]张云飞，刘培民．中医药治疗脑瘤的研究进展［J]．中医临床研究，2015，7(29)：145-146.DOI: 10.3969/j.issn.1674-7860.2015.29.080. Zhang YF,Liu PM.Areview on treating brain tumor with TCM medicine [J] . Clinical Joumal of Chinese Medicine, 2015， 7(29): 145-146. DOI: 10.3969/j.issn.1674-7860.2015.29.080.   
[27] ZENG H,CHEN W Q,ZHENG R S,et al. Changing cancer survival in China during 2003-15: apooled analysis of 17 population-based cancer registries[J]． The Lancet Global Health，2018，6(5): 55-567.DOI : 10.1016/S2214-109X(18)30127-X.   
[28]Brain GBD,Other CNSCC.Global,regionaland nationalburdenofbrain andother CNScancer,1990-2016:asystematic analysis for the Global Burden of Disease Study2016[J].Lancet Neurol，2019，18(4):376-393.ODI: 10.1016/S1474-4422(18)30468-X.   
[29]PIEL C,POUCHIEU C,TUAL S,et al. Central nervous system tumors and agricultural exposures in the prospective cohort AGRICAN [J] . Int JCancer,2017,141(9): 1771-1782. DOI: 10.1002/ijc.30879.   
[30] VIENNE JA,TAFANI C,RICARD D.Environmental risk factors of primary brain tumors: areview [J].Rev Neurol (Paris),2019, 175(10): 664-678. DO1: 10.1016/j.neurol.2019.08.004.   
[31] OSTROMQT,ADELFM, COTEDJ,et al.Risk factors for childhood and adult primary brain tumors [J].Neuro Oncol,2019,21(11): 1357-1375.DOI: 10.1093/neu0nc/noz123   
[32]查震球，刘志荣，郑荣寿，等．2008-2012 年中国肿瘤登记地区脑及神经系统肿瘤发病与死亡分析[J]．中华疾 病控制杂志，2018，22(11):1101-1105.DOI:10.16462/j.cnki.zhjbkz.2018.11.003. Zha Z Q，Liu ZR， Zheng R S， et alAnalysis of incidence and mortality rates of brain and nervous system cancer in registration areas of China from 2008 to 2012[J].Chinese Journal of Disease Control & Prevention,2018,22(11): 1101-1105.DOI: 10.16462/j.cnki.zhjbkz.2018.11.003.