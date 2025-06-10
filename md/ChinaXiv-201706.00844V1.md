# DOI:10.5846/stxb201605241005

张盛,王铁宇,张红,李奇锋,周云桥,宋帅.多元驱动下水生态承载力评价方法与应用——以京津冀地区为例.生态学报,2017,37（12)： 4159-4168. ZhangS，WangYangH,LiQFZouYQ，SongSUsingutivaratedriveoeltluatewaterologicalaingaciyo buildingandapplicationintheBeijing-Tianjin-Ji（HebeiProvince）rgion.ActaEcologica Sinica,20l7,37(12):4159-4168.

# 多元驱动下水生态承载力评价方法与应用一以京津冀地区为例

张盛1,²,王铁宇2,3，\*，张红¹，李奇锋2,3，周云桥2,3，宋帅²

1山西大学环境与资源学院，太原030006  
2中国科学院生态环境研究中心城市与区域生态国家重点实验室，北京100085  
3中国科学院大学，北京100049

摘要：水生态承载力通常是指在维持水生态系统自身及其支持系统健康的前提下,基于一定的生态保护和承载目标,自然水生态系统所能支撑的人类活动的阈值。从水生态承载力的概念出发,基于水资源、水环境和社会经济等要素,筛选出水资源利用率、污水处理率、万元GDP用水量等16个指标对水生态承载力评价的多元耦合作用进行分析,量化驱动因子与水生态承载力之间的关联度,建立了具有多元驱动功能的粒子群引力搜索算法-投影追踪(PSOGSA-PP)水生态承载力评价模型。并以京津冀地区为例，解析了区域水资源和水环境的生态效益，以及经济社会效益最大化的内在驱动，评价了水生态承载力并阐明其影响因素。进一步设定不同时间段的水生态承载力情景方案,通过具有较高寻优精度和较好算法执行能力的粒子群引力搜索算法,利用最佳投影方向 $\vec { a }$ 分别计算分级标准阈值的投影值 $z ^ { \prime } ( i )$ 和评价实例的投影值 $z ^ { \prime \prime } ( i )$ ,基于投影值 $z ^ { \prime } ( i )$ 构造水生态承载力评价等级,实现了水生态承载力的分级评价,结果表明,在多元因子共同驱动下，2008年—2030年京津冀所属13个地区的水生态承载力在波动中呈好转趋势,逐步由Ⅳ级(超载）、V级（严重超载)向趋于Ⅱ级（比较理想)状态的演变,张家口市始终保持着Ⅱ级水平,并在2030年达到I级(理想)的临界值。研究成果将为京津冀一体化的水资源开发利用与水源生态涵养提供重要的决策支持。 1

关键词：水生态承载力；多元驱动;评价方法与应用;京津冀地区；情景模拟

# Using a multivariate-driven model to evaluate water ecological carrying capacity : Method-building and application in the Beijing-Tianjin-Ji（Hebei Province) region

ZHANG Sheng1,²，WANG Tieyu2.3,\*， ZHANG Hong1，LI Qifeng2.3， ZHOU Yunqiao2.3， SONG Shuai²

1 College of Environment and Resource，Shanxi University,Taiyuan O3ooo6,China   
2StateKeyLaboratoryfUbnndRegioalcolog，eseachCenterforcoEiotalSciences，ChinseAcadeyofSciences，ejng 100085， China   
3 University of Chinese Academy of Sciences，Beijing 10oo49，China

Abstract:Water ecological carrying capacity refers to the degree that natural aquatic ecosystems can support human activitiesunder certainconservation goals，while maintaining ecosystem quality.To explorethisconcept，whichis basedon waterresources，environmentalconditions，and socioeconomicfactors，16 indicatorswere selectedto analyzethe multivariatecoupling effctof waterecologicalcarryingcapacityandtoquantifycorelationsbetwee this efectandrelated driving factors.A particle swarmoptimization gravitational search algorithm-projectionpursuit（PSOGSA-PP）model with a functionof multipledrivers wasestablished toevaluatewaterecologicalcaryingcapacity.TheBeijing-Tianjin-Ji（Hebei Province）region waschosen asacase studyforanalyzing thedrivers ofecological benefitsofregional waterresourcesand water qualityandfor maximizing theasociated economicandsocial benefits，aswellas toevaluate watercarryingcapacity and impact factors.Scenarios were developed based on carrying capacitiesduring different periods，and water ecological carrying capacity evaluation levels were established using PSOGSAs and the optimal projection direction $\vec { a }$ ,the classification standard threshold projectionz ${ \bf \Xi } ^ { \prime } ( i )$ ，and the projection value of evaluation instancez ${ \mathbf { \eta } ^ { \prime \prime } } ( i )$ .Water carrying capacity exhibited animproving trend,from levelIV（overload）andlevelV（extensive-overload）tolevelII（ideal），for13cities inthe Beijing-Tianjin-Hebeiregionfrom 2008 to2O3；projections indicated,forinstance,that ZhangjiakouCitywouldremainat level Ilforthe mostof theperiod,andattain levelI（ideal）by2O3O.Ourresultsofersupportfortheexploitationand utilization of waterresources，aswellasthe protectionof aquaticeco-systems，inthe Beijing-Tianjin-Hebeiregion in the future.

Key Words:water ecological carying capacity；multipledrivers；evaluation methodandapplication；Beijing-Tianjin- Ji （Hebei Province）；model-scenario simulation

水生态承载力以水循环过程为纽带,是指在保护水生态系统完整性下的水资源、水环境和社会经济要素共同作用的支撑能力。我国水生态系统问题由来已久,水资源过度开发、粗放利用和污染严重等问题突出。以水生态系统健康理念为核心的水生态承载力的相关研究日益引起国内外学者的广泛关注[1-2]。水生态承载力评价的根本宗旨是通过对关键指标的调控,在满足区域生态需水、栖息地环境和水质目标的前提下,评价区域可承载的最大人口数量和经济规模[3-4]。目前,水生态承载力的相关研究多集中在概念和评价方法上[4]。水生态承载力是一个多元动态的复合系统,多元性主要体现在其评价因子数量多,内容涉及面广[5];动态性主要体现在时间和空间上的动态变化[6,包括社会经济系统和水生态系统之间的相互影响;复合性主要体现其概念的组成上,涵盖了水资源承载力[7-]、水环境承载力[1-13]和社会经济承载力等,兼具自然属性和社会属性。

国内外研究水生态承载力的方法主要包括生态足迹法[14-5]、系统动力学[10,16-27]和统计学方法[6,19-20]等。其中,生态足迹方法在评价水资源承载力方面,优点在于数据资料易获取,计算方法可操作性强且简便,着重反映自然资源与经济社会发展的互补关系,但缺乏对水质、水量以及生物需求的综合考虑[5]。系统动力学方法优势在于研究解决非线性问题,如辽宁太子湖流域[21]、新疆叶尔羌河流域[22]和太湖流域[16.23]生态承载力的评价应用,但是模型对于数据要求较高,参数率定繁琐,求解条件苛刻限制了其推广。统计学方法,包括线性回归、聚类分析、时间序列和主成分分析等,具有目标相对单一的缺点。多元驱动下的PSOGSA-PP 水生态承载力评价模型,是利用粒子群引力算法求最优解,并采用投影追踪模型对最佳投影方向进行参数优化,有效的提高了模型的评价精度,具有参数少、易于操作、计算稳定性强和良好的全局搜索能力等优点[24]。该模型的优势在于借助粒子群引力搜索算法,多次运算,寻找最优投影方向,形成水生态承载力评价分级标准。本文将模型应用于京津冀地区,把北京、天津和河北省的11个地级市的水生态承载力进行分级评价,提出水生态承载力评价指标体系和分级标准,对于“京津冀一体化"新时期下协调区域水资源开发、水环境保护和区域社会经济发展具有理论和实践借鉴价值。

# 1模型构建

# 1.1水生态承载力评价指标体系

水生态承载能力评价是通过对关键指标的调控,在区域满足生态需水、栖息地环境和水功能分区水质目标的前提下,评价区域可承载的最大人口数量和经济规模[4]。本研究在水生态承载力评价指标选取时,采用频数分析法对已有研究文献中的指标进行汇总、统计和筛选,将有关水资源、水环境的频数累计百分比超过$8 0 \%$ 的作为主要指标,紧扣水生态承载力的概念和内涵,依托京津冀的区域特征,剔除与概念不相关指标,参阅国家颁布的相关指标体系进行相应调整更新,综合考虑专家评判结果,最后将所遴选指标做相关性分析。在常规指标体系的基础上,增加了有关水管理和水利用方面的指标[17.25-27]。严格按照系统性、代表性、区域差异性、层次性、指标定量性和可操作性的选取原则。据此,从水资源、水环境、社会经济3方面,构建了区域水生态承载力评价指标体系,包括目标层、准则层和指标层（表1）。

表1京津冀地区水生态承载力评价指标体系  
Table1The indicators of water ecological carrying capacity in Jing-Jin-Ji(Hebei Province）region   

<html><body><table><tr><td>目层l</td><td>Stdar层 evel</td><td>d层  level</td><td>单位</td><td>量化方法on method</td></tr><tr><td>水生态承载</td><td>水资源</td><td>水资源利用率C</td><td>%</td><td>区域用水总量/区域水资源总量×100%</td></tr><tr><td>能力评价</td><td></td><td>水资源密度C2</td><td>104m³/km²</td><td>区域水资源总量/区域国土面积</td></tr><tr><td>Assessment of water</td><td></td><td>人均水资源可利用量C</td><td>m/人</td><td>区域水资源可利用量/区域总人口</td></tr><tr><td>ecological carrying</td><td></td><td>降水深C4</td><td>mm</td><td>区域降水高度/区域面积</td></tr><tr><td>capacity</td><td>水环境</td><td>水功能区达标率C5</td><td>%</td><td>水功能区达标个数/水功能区总数×100%</td></tr><tr><td></td><td></td><td>集中式供水水源达标率C6</td><td>%</td><td>集中供水水源地达标个数/集中式供水水源地总数 x100%</td></tr><tr><td></td><td></td><td>入河污染物总量达标率C</td><td>%</td><td>水功能区COD、NH3-N排放总量小于水功能区纳污</td></tr><tr><td></td><td></td><td>污水处理率Cg</td><td>%</td><td>能力个数/水功能区总数×100% 废污水处理量/废污水排放总量×100%</td></tr><tr><td></td><td>经济社会</td><td>万元GDP 用水量Cg</td><td></td><td>区域用水总量/区域GDP</td></tr><tr><td></td><td></td><td>万元工业增加值用水量C10</td><td></td><td>区域工业用水总量/区域工业增加值</td></tr><tr><td></td><td></td><td>农田灌溉水有效利用系</td><td>%</td><td></td></tr><tr><td></td><td></td><td>数C11</td><td></td><td>农业实际利用渠道净水总量/渠道取水总量×100% 区域工业取水总量/区域(工业取水总量+重复利用</td></tr><tr><td></td><td></td><td>工业用水重复利用率 C12 用水总量控制红线达标</td><td>%</td><td>总量)×100% 辖区用水总量控制达标县(市)/辖区县（市)总数</td></tr><tr><td></td><td></td><td>率C13</td><td>%</td><td>×100%</td></tr><tr><td></td><td></td><td>计划用水实施率C14</td><td>%</td><td>区域计划用水总量/区域总用水量×100%</td></tr><tr><td></td><td></td><td>取水许可实施率C15</td><td>%</td><td>区域取水许可总量/区域总用水量×100%</td></tr><tr><td></td><td></td><td>人河排污口监控率C16</td><td>%</td><td>区域受监控污水排放量/区域污水排放总量×100%</td></tr></table></body></html>

水生态承载力是针对某一特定地区的相对概念,它既包含有横向上和其他地区的比较,也考虑了纵向时间上与过去的比较。最严格水资源管理制度和"水十条"的提出是一定时期及区域内开展水生态承载力研究的基础和前提。利用层次分析法,从水资源系统、水环境系统和经济社会系统（主要体现在水利用与水管理 2个方面)遴选出16项指标构成水生态承载力评价指标体系,并对每个指标进行分区分级量化,将水生态承载力评价分为目标层A、准则层B和指标层C3个层次。构建符合区域水生态承载力评价指标分级标准,将水生态承载力分为“理想”、“较理想”、“临界”、“超载”和“严重超载”5个等级,分别用I级—V级表示[17-18,28-32],并确定各指标合理的上限值和下限值（表2）。

需要指出,水生态承载力评价指标分级标准是相对的。由于地域条件的不同,所选取的评价指标各异,各指标之间的相互影响程度和各自权重大小也不同。利用指标体系，一个地区也可以评价随时间推移的水生态承载力变化情况，为环境政策制定和考核制度的实施提供技术依据。

# 1.2 PSOGA-PP模型原理与技术路径

投影追踪（Projection Pursuit,PP)是用于处理和分析高维数据的一类新型统计方法,其基本原理是将高维数据构建某种组合投影到低维子空间上，通过极小化投影指标来反映原高维数据的结构或特征，并在低维空间上对数据结构进行分析,以达到研究和分析高维数据的目的[334]。在实际应用过程中,投影寻踪模型最佳投影方向 $\vec { a }$ 的选取对于模型的泛化性能及评价结果有着关键的影响。本文以粒子群引力搜索算法[35]（Particle Swarm Optimization Gravitational Search Algorithm,PSOGSA）对投影寻踪模型最佳投影方向参数进行优化,它汲取了引力搜索算法的全局勘探能力和粒子群算法的局部搜索开发能力,具有良好的收敛精度和全局搜索能力[36-38]。引力搜索算法通过个体间的万有引力相互作用实现优化信息共享,引导群体向最优解区域搜索,具有较好的全局搜索能力,易陷入局部极值。粒子群优化算法是一种简单、高效的仿生物群体智能算法,其收敛速度快、局部搜索能力强。无论是高位单峰函数还是高位多峰函数，粒子群引力搜索算法的寻优效果都全面优于标准引力搜索算法和粒子群优化算法,表现出较高的寻优精度和较好的算法执行能力,这说明基于粒子群优化算法改进的引力搜索算法在高维复杂函数的寻优中具有较好的计算稳定性和全局搜索能力[39]。

表2京津冀地区水生态承载力评价指标分级标准  
Table2The grading standard of water ecological carrying capacity yin Jing-Jin-Ji(Hebei Province )region   

<html><body><table><tr><td>方法 Method</td><td>指标层C Indicator level</td><td>I级(理想) I level ( Ideal)</td><td>Ⅱ级(较理想) I level (Relatively ideal)</td><td>Ⅲ级(临界) III level (Critical)</td><td>V级(超载) IV level</td><td>V级(严重超载) Vlevel</td></tr><tr><td>评价等级</td><td>C1</td><td></td><td>[50,60)</td><td>[60,80)</td><td>(Overload)</td><td>(Severe overload)</td></tr><tr><td>Evaluation level</td><td>C</td><td><50 ≥80</td><td>[60,80)</td><td>[40,60)</td><td>[80,100） [20,40)</td><td>≥100 <20</td></tr><tr><td></td><td>C3</td><td>≥2000</td><td>[1500,2000)</td><td>[1000,1500)</td><td>[500,1000)</td><td><500</td></tr><tr><td></td><td>C4</td><td>≥1000</td><td>[800,1000)</td><td>[600,800)</td><td>[400,600)</td><td><400</td></tr><tr><td></td><td>C5</td><td>≥95</td><td>[80,95)</td><td>[60,80)</td><td>[40,60)</td><td><40</td></tr><tr><td></td><td>C6</td><td>≥99</td><td>[90,99)</td><td>[80,90)</td><td>[70,80)</td><td><70</td></tr><tr><td></td><td>C7</td><td>≥95</td><td>[80,95）</td><td>[60,80)</td><td>[40,60)</td><td><40</td></tr><tr><td></td><td>Cg</td><td>≥90</td><td>[80,90)</td><td>[70,80)</td><td>[50,70)</td><td><50</td></tr><tr><td></td><td>C9</td><td><60</td><td>[60,80）</td><td>[80,100)</td><td>[100,120)</td><td>≥120</td></tr><tr><td></td><td>C10</td><td><10</td><td>[10,20)</td><td>[20,40)</td><td>[40,50)</td><td>≥50</td></tr><tr><td></td><td>C11</td><td>≥0.7</td><td>[0.6,0.7)</td><td>[0.5,0.6)</td><td>[0.4,0.5)</td><td><0.4</td></tr><tr><td></td><td>C12</td><td>≥95</td><td>[80,95)</td><td>[60,80)</td><td>[40,60)</td><td><40</td></tr><tr><td></td><td>C13</td><td>≥90</td><td>[80,90)</td><td>[70,80)</td><td>[50,70)</td><td><50</td></tr><tr><td></td><td>C14</td><td>≥90</td><td>[80,90)</td><td>[70,80)</td><td>[40,70)</td><td><40</td></tr><tr><td></td><td>G15</td><td>≥90</td><td>[80,90)</td><td>[70,80)</td><td>[40,70)</td><td><40</td></tr><tr><td></td><td></td><td>≥95</td><td>[85,95)</td><td>[70,85)</td><td>[50,70)</td><td><50</td></tr></table></body></html>

[)为数学符号,表示区间,区间是数集的一种表示形式;半开半闭区间 $\{ x \mid a { \leqslant } x { < } b \} = [ a , b )$

其中,PSOGA-PP 模型的主要算法过程如下[40]：

Stepl 数据预处理。预设待评价的数据集为 $\{ x ( i , j ) \mid i = 1 , 2 , \cdots , n ; j = 1 , 2 , \cdots , m \}$ ,对于指标值越大其评价结果越高的指标采用以下公式进行数据处理：

$$
x ( i , j ) = \frac { x ( i , j ) - x _ { \operatorname* { m i n } } ( j ) } { x _ { \operatorname* { m a x } } ( j ) - x _ { \operatorname* { m i n } } ( j ) }
$$

式中， $\mathbf { \chi } _ { x } ( i , j )$ 为第 $i$ 组第 $j$ 个评价指标值; $x _ { \mathrm { m a x } } \left( j \right) \mathbf { \Omega } \setminus x _ { \mathrm { m i n } } \left( j \right)$ 分别为评估数据集中第 $j$ 个评价指标的最大值、最小值； $\textit { n , m }$ 分别为数据集数量及评估数据数目。对于指标值越小其评价结果越理想的指标,对其取倒数乘100,再按(1)进行处理。

Step2构造投影指标函数。投影追踪方法就是将 $\mathbf { \nabla } _ { m }$ 维数据 $\{ x ( i , j ) \mid j = 1 , 2 , \cdots , m \}$ 综合成 $\textbf { \textit { a } } =$ $\{ a ( 1 ) , a ( 2 ) , \cdots , a ( m ) \}$ 为投影方向的一维投影值 $z ( i )$ ：

$$
z ( i ) = \sum _ { j = 1 } ^ { m } \vec { a } ( j ) x ( i , j )
$$

式中， $\vec { a }$ 为单位长度向量。

确定投影指标时,要求投影值 $z ( i )$ 的局部投影点尽可能密集，因此,构造的投影函数为：

$$
Q ( a ) = S _ { \scriptscriptstyle z } D _ { \scriptscriptstyle z }
$$

式中， $S _ { z }$ 为投影值 $z ( i )$ 的标准差； $D _ { z }$ 为投影值 $z ( i )$ 的局部密度，即

$$
S _ { z } = \sqrt { \sum _ { i = 1 } ^ { n } { \ ( z ( i ) \ - \bar { z } ) ^ { 2 } } / ( n \mathrm { ~ - ~ } 1 ) }
$$

$$
D _ { z } = \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m } \left[ R - r ( i , j ) \ : \right] \cdot o \left[ R - r ( i , j ) \ : \right]
$$

式中， $\bar { z }$ 为序列 $z ( i )$ 的平均值; $R$ 为局部密度的窗口半径; $r ( i , j )$ 为样本之间的距离; $\mathbf { \sigma } _ { o } ( \tau )$ 为单位阶跃函数，当 $\tau \geqslant 0$ 时,其值为1,当 $\tau < 0$ 时,其值为0。

Step3优化投影指数函数。当投影指标函数取得最大值时，所对应的 $\vec { a }$ 方向最能反映数据特征的最优投影方向。因此搜寻最优投影方向问题就转化成非线性最优解的问题,即： .

$$
\left\{ \begin{array} { l l } { \displaystyle \operatorname* { m a x } : Q ( a ) = S _ { z } D _ { z } } \\ { \displaystyle s . t : \sum _ { j = 1 } ^ { m } \ ( a ) ^ { 2 } ( j ) = 1 a \ \in \ [ 0 , 1 ] } \end{array} \right.
$$

反之,当投影指标函数取得最小值时,所对应的 $\vec { a }$ 方向最能反映数据特征的最优投影方向。其公式为：

$$
\left\{ \begin{array} { l l } { \operatorname* { m i n } \colon Q ( a ) = 1 / ( S _ { z } D _ { z } ) } \\ { \qquad \displaystyle \vphantom { \operatorname* { m i n } \operatorname* { m i n } } \mathrm { ~ s ~ } t : \sum _ { j = 1 } ^ { m } \ ( a ) ^ { 2 } ( j ) = 1 a \ \in \ [ 0 , 1 ] } \end{array} \right. \mathcal { V }
$$

Step4 构造分级标准。利用公式(1)对各评价因子等级阈值进行归一化处理,将最佳投影方向 $\vec { a }$ 代入(2)得到各分级标准投影值 $z ^ { ' } ( k )$ ， $k$ 为分级数, $z ^ { ' } ( k )$ 即为评价分级标准。

Step5评价。同理，计算得到待评价因子投影值 $z ( i )$ ,并依据 $z ^ { ' } ( k )$ 进行评价。

与粒子群优化算法寻优结果相比,粒子群引力搜索算法巡游精度提高了8个数量级以上,4个测试函数的寻优成功率也均为 $100 \%$ ,与标准引力搜索算法寻优结果相比,粒子群引力搜索算法中的Quadric 函数的寻优精度比标准引力搜索算法提高了15个数量级以上。所以,PSOGSA-PP 模型利用粒子群引力搜索算法搜寻投影寻踪模型的最佳投影方向 $\vec { a }$ ,不但有效提高了投影寻踪模型的评价精度,而且为解决投影追踪模型最佳投影方向 $\vec { a }$ 提供了一种全新的途径和方法。其模型原理与实现步骤见图1。

# 2案例研究

2.1 京津冀地区水生态概况

京津冀地区位于海河流域的中下游,包括北京市、天津市以及河北省的保定、廊坊、唐山、张家口、承德、秦皇岛、沧州 衡水、邢台市、邯郸、石家庄等11个地级市,是全国主要的高新技术和重工业基地,也是我国政治、文化、经济、科技发展的核心区。属于“资源型"缺水地区,多年平均水资源总量分别为 $3 2 . 9 \times 1 0 ^ { 8 }$ ） $1 4 . 3 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ 和 $1 9 8 . 3 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,据《2014年中国水资源公报》显示,京津冀人均水资源占有量仅 $2 8 6 \mathrm { ~ m } ^ { 3 }$ ,为全国平均水平的$1 / 8$ ,世界人均占有量的 $1 / 3 2$ ,也远低于联合国制定的人均 $1 0 0 0 \mathrm { m } ^ { 3 }$ 的缺水线。京津冀地区约为 $1 2 \times 1 0 ^ { 4 } \mathrm { k m } ^ { 2 }$ ，人口约为9000 万,面积和水资源仅占全国的 $2 . 3 \%$ 和 $1 \%$ ,却承载着全国 $8 \%$ 的人口和 $1 1 \%$ 的经济总量[41]。据《2014年环境质量公报》,京津冀水质相对较差,国控断面中，I类水质断面占 $4 . 7 \%$ ,同比上升3.1个百分点;Ⅱ类占 $1 4 . 1 \%$ ,同比下降4.6个百分点;Ⅲ类占 $2 0 . 3 \%$ 同比上升1.6个百分点； $\mathrm { \Delta I V }$ 类占 $1 4 . 1 \%$ ，同比上升4.7个百分点；V类占 $9 . 3 \%$ ,同比下降3.2个百分点;劣V类占 $3 7 . 5 \%$ ,同比下降1.6个百分点，远远超过国家十大水系 $1 3 . 7 \%$ 的平均水平。由水利部水规总院调查整理的 2013 年京津冀供水结构表表明,京津冀地区水资源开发程度高达 $109 \%$ ,平水年份生态环境用水年均赤字近90亿 $\mathbf { m } ^ { 3 }$ ,其中地下水68亿 $\mathbf { m } ^ { 3 }$ ,年均挤占河湖生态用水量15亿 $\mathbf { m } ^ { 3 }$ ,枯水年份挤占生态环境问题更加突出。京津冀一体化的提出意味着京津冀地区政策互动和资源共享,但面临着水资源不匹配、降水时空分布不均、开发利用难度大、水质污染逐年加重和水资源配置能力不足等诸多问题。“十二五"以来,随着京津冀地区经济社会的快速发展,水资源供需矛盾日益突出,f水污染日趋严峻,导致水生态系统结构、功能等随之发生变化。

![](images/b8ed7c73c16fd644dbcddbc1d1bd115231d543bf72521bb9f93c900b8a1ce953.jpg)  
图1PSOGSA-PP模型原理与技术路径图  
Fig.1The theory of PSOGSA-PP model and research flow chart

# 2.2情景方案设定与模拟

2008 年为保障北京奥运会成功举办,京津冀各地政府统筹协作以制度和政策为驱动力,在水生态保护、水环境健康、水生态安全以及水生态补偿措施等方面取得丰硕成果。2015 年颁布的《京津冀协同发展生态环境保护规划》指出,到2020年,京津冀地级及以上城市集中式饮用水水源水质全部达到或优于Ⅲ类,重要江河湖泊水功能区达标率达到 $7 3 \%$ ;同时，京津冀用水总量控制在296亿 $\mathbf { m } ^ { 3 }$ ,地下水超采退减率达到 $7 5 \%$ 以上；到2030年,京津冀水生态承载能力、水生态文明水平将得到进一步提升,一体化协同水治理管控能力增强,应对风险能力和水安全保障程度提高，基本实现水利现代化。

基于水生态承载力的内涵,从已有成功经验、污染现状和环境治理水平以及政策规划等要素综合考虑,设定水生态承载力在"过去-现在-未来"的动态变化过程情景,历史年为2008年,基准年为2014年,规划水平年为 2020 年和 2030年（表3）。

# 2.3优化结果与评价分析

依据2.2所收集各地区不同年份的指标参数值与水生态承载力优化模型（PSOGSA-PP）,计算出水生态承载力评价指标最佳投影方向 $\vec { a }$ ,利用最佳投影方向 $\vec { a }$ 分别计算分级标准阈值投影值 $z ^ { ' } ( k )$ 和京津冀各地区不同年份的投影值 $z ^ { \prime \prime } ( k )$ ，利用 $z ^ { ' } ( k )$ 确定水生态承载力评价等级，以下是京津冀地区2008年、2014年、2020 年和 2030年水生态承载力评价结果（图2）。

京津冀地处海河流域,其中天津处在京津冀下游,为海河流域的入海口,北京市和河北省的大部分地区父亲位于上游,而承德市和张家口市又处于北京市上游,为北京重要的水源地。从图2可以看出,就2008 年而

# 言,基于外来人口压力,产业结构不合理以及本身水资源匮乏等因素的多重胁迫,北京市水生态承载力为

表3京津冀地区水生态承载力情景方案  
Table 3Water ecological carrying capacity scenarios of Jing-Jin-Ji(Hebei Province）Region   

<html><body><table><tr><td>方案名称 Scheme name</td><td>情景设计 Scenario design</td></tr><tr><td>历史成就 Historic achievement(2008)</td><td>奥运会成功举办年,京津冀率先采取跨界联动措施，人均水资源 293m，I—Ⅲ类水质断面占28.6%;V类 水质断面占14.3%、V类水质断面占6.3%;劣V类水质断面占50.8%。水资源相对较足,水环境得到明显 改善。京津冀常住人口为0.97亿,GDP 总量占全国11.3%万元GDP用水量达到95m以下 “十二五"规划末期,京津冀一体化战略制定的一年,北京、天津和河北水污染防治考核结果均为差。京津</td></tr><tr><td>现状过渡 Current situation(2014)</td><td>冀人均水资源仅239m,地表水劣V类(丧失使用功能的水)断面比例达30%以上,受污染的地下水占三 分之一;I类以上污染水超过60%,劣V类水评价河长超过45%;平原区河流普遍断流,湿地萎缩,功能衰 退,河道淤积,地表水灌溉减少,地下水超采,地下漏斗分布广。京津冀常住人口为1.1亿,GDP 总量占全 国10.4%，万元GDP用水量约为100m</td></tr><tr><td>中期蓝图 Mid-blueprint(2020)</td><td>迎接 2022冬奥会的攻坚阶段,京津冀将构建水资源统一调配管理平台,实行水量联合调度,人均水资源将 达到300 m,京津冀监测网全面建成水源水质全部达到或优于Ⅲ类，京津冀地区用水总量控制在305.6 X 10m,地下水超采退减率达到75%以上。京津冀常住人口将达到1.2亿,万元GDP用水量达到80m</td></tr><tr><td>长期愿景 Long-term vision(2030)</td><td>水生态文明提升年,基本实现水利现代化。用水效率和节水水平显著提高,京津冀地区用水总量控制在 339.8×108m,水源地水质全部达到或者优于Ⅱ类,I、Ⅱ类达标率占 90%以上。饮用水达标率100%,人 均水资源超过300m,万元GDP 用水量控制在50m以下,常住人口控制在1.1亿以内</td></tr></table></body></html>

好的水生态环境不仅为奥运会的成功举办增添了优美的景观，也是奥运会成功举办的重要条件。但是位于北京下游的保定该模型所需数据和参数设定主要依据以下参考资料计算所得：《北京市城市总体规划（2004—2020）》《天津市城市总体规划（2005—2020）》、 $\langle 2 0 0 8$ 年北京市环境保护工作总结》、 $\langle \langle 2 0 1 5 \$ 年北京十三五规划建议全文》、《天津市十三五规划纲要全文》、《天津市未来科技城总体规划（2013—2030)》、《天津市国土规划（2002—2030）》、《河北省生态环境保护“十二五"规划》、《河北省十三五规划全文》《京津冀协同规划纲要(全文)》、河北省《关于实施实行最严格水资源管理制度的意见》、《关于实施实行最严格水资源管理制度的意见》附件、《天津市污水处理及其再生水利用行业企业排名统计报告》 ${ \langle \langle 2 0 0 9 }$ 年—2013年河北省污水处理及其再生利用行业年度经营状况统计分析报告》、河北省《污水垃圾处理专项提升行动工作方案》 $\langle \langle 2 0 0 8 \$ 年天津市环境状况公报》、 $\langle \langle 2 0 1 4$ 年天津市环境状况公报》、《2008 年中国环境统计年鉴》、《2014 年中国环境统计年鉴》、《河北省人口战略发展研究报告》等[42-45] 1

级,处于临界状态;天津市和位于首都上游的张家口市、承德市水生态承载力均为Ⅱ级,处于比较理想状态；良市、衡水市和沧州市水生态承载力为V级,出现严重超载的局面;廊坊市、邢台市和邯郸市也不容乐观,水生态承载力为V级,表现为超载;石家庄市、唐山市和秦皇岛市相对居中,水生态承载力为Ⅲ级,处于临界状态。京津冀同属于海河流域为主体的半干旱地区,2008年—2014年间,河北平原过量开采地下水,导致地下超采区域漏斗达20 多个，面积达 $7 \times 1 0 ^ { 4 } \mathrm { k m } ^ { 2 }$ ,由地下水面下降形成地下水降落漏斗,产生地面沉降达 $9 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,年沉降速率大于 $3 0 \mathrm { m m }$ 的严重沉降区面积约为 $2 . 5 3 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,部分地区最大沉降量达到 $1 6 0 \mathrm { m m } ^ { [ 4 6 ] }$ ,沉降中心主要分布在沧州市、衡水市、邢台市和邯郸市境内,同时保定市也出现地下水超采和水质恶化情况。因此,2014 年京津冀水生态承载力较2008年,大部分地区出现下滑态势,北京市基于人口和经济转型的压力,表现为V级，天津市和承德市为Ⅲ级,张家口市为仍呈现Ⅱ级,投影值达到全区域最大为2.4688,沧州市、衡水市、邢台市和邯郸市为V级,其余地区投影值均小于2.1893 和北京一样同为 $\mathrm { I V }$ 级，。2020 年是《京津冀协同发展规划纲要》全面实施阶段,京津保中心区生态过渡带即将建成,同时也是2022北京—张家口国际冬奥会举办的攻坚阶段,京津冀将构建水资源统一调配管理平台和水环境统一监管制度,实行水量联合调度,水质统一评价。预计京津冀重点流域水质优良(达到或优于Ⅱ类)比例总体 $70 \%$ 以上,地级及以上城市黑臭水体均控制在 $10 \%$ 以内，地级及以上城市集中式饮用水水源水质达到或者优于Ⅲ类比例高于 $9 3 \%$ ,京津冀区域丧失使用功能(劣于V类)的水体断面比例下降 $1 5 \%$ 左右。水生态承载力分级如下：北京市出现好转,投影值由2.3573上升为2.3733,达到Ⅱ级临界值,但是呈现Ⅲ级,天津市、承德市和张家口市为Ⅱ级,达到较理想状态,投影值分别为2.5032,2.4489 和2.5804,沧州市、衡水市、邢台市和邯郸市地处河北平原地下水下渗漏斗带仍处于超载状态,评定为V级，其余地区投影值均位于2.3037与2.3896之间评定为Ⅲ级。到2030年,京津冀地区将率先建成节水型社会，一体化协同水生态管控能力进一步加强,重点流域水质优良比例总体 $7 5 \%$ 以上,城市建成区黑臭水体总体得到消除,地级及以上城市集中式饮用水水源水质达到或者优于Ⅲ类比例高于 $9 5 \%$ 左右,基本实现水利现代化。水生态承载力分级结果可以看出，各个地区的投影值 $z ^ { \prime \prime } ( i )$ 均有所上升,除沧州市、衡水市、邢台市和邯郸市为Ⅲ级外,其余全部地区均为Ⅱ级。其中张家口市和承德市分别为2.6878和2.7227,已经达到I级的临界值。

![](images/b341986bfd0f3989f42ab66ad47674d228f287c9bd4e4e7ff991ebcba7ef0a0c.jpg)  
图2多元驱动模型下的京津冀水生态承载力分级评价  
Fig.2Water ecological carrying capacityevaluationin Jing-Jin-Ji（Hebei Province）area based the multivariate drivenmodel

# 3结论

(1)本文利用水资源、水环境和社会经济数据来综合表征水生态承载力,选取具有独立性和代表性的参数构建评价指标体系，建立了多元驱动模型(PSOGSA-PP)模拟其相互关系和动态变化，并进行承载指数计算和分级评价,揭示了各地区是否超载以及超载程度问题,模拟预测了京津冀地区在2008年、2014年、2020 年和2030 年水生态承载力的演化态势。

(2)利用粒子群引力投影寻踪模型模拟结果表明,2008年—2030 年京津冀所属13个地区的水生态承载力在呈先恶化再逐步好转趋势(逐步由V级、 $\mathrm { \Delta V }$ 级趋于 $\mathbb { I }$ 级）。2008年—2014年，河北省GDP总量的过快增长导致河北平原地下水严重超采区占 $6 3 . 2 \%$ ,一般超采区占 $2 0 . 5 \%$ ,严重影响了京津冀三地的水生态承载力。2014 年—2020年,随着京津冀一体化战略的实施、“水十条”和最严格水资源管理制度的推行和水生态修复工作的完善,预期到2030 年京津冀地区水生态整体将得到极大程度改善。

(3)由于京津冀地区长期受水资源短缺、水生态环境破坏、城市发展不平衡等因素制约,京津冀地区的总体水生态承载能力不容乐观。因此,水生态的改善必须按照分类、分区、分阶段的梯级模式逐步开展,水生态系统、水资源系统、水环境系统和社会经济系统之间存在着相互影响和相互作用关系,2008—2030 年京津冀13个市区水生态承载力的分级评价与发展态势,可望为水生态保护、水环境修复以及水资源可持续开发利用提供决策支撑。

# 参考文献（References）：

[1]PengJ,,Xsliilithe view of coupled human and natural systems.Ecological Indicators,2016,6O：1017-1030.  
[2］张林波,李兴，,李文华，王维，刘孝富.人类承载力研究面临的困境与原因.生态学报，2009,29(2)：889-897.  
[3]Chambers，imosC，WackeragelaringNture'sterest：EologcalFotprintssnIicatorofStanabilityYork:Routledge，2000.  
[4] 王西琴，高伟，张家瑞.区域水生态承载力多目标优化方法与例证.环境科学研究，2015，28（9)：1487-1494.  
[5] 刘子刚，蔡飞.区域水生态承载力评价指标体系研究.环境污染与防治，2012，34(9)：73-77.  
[6] 焦雯珺，闵庆文，李文华,FULLER AM.基于ESEF 的水生态承载力：理论、模型与应用.应用生态学报,2015,26(4)：1041-1048.  
[7] 夏军，张永勇，王中根，李浩.城市化地区水资源承载力研究.水利學報，2006,37（12)：1482-1488.  
[8] DessuSB,Melese,atG,cinesseofasoesavalbiltdadinearaiersinatea,,115: 104-114.  
[9]LiG,JinFprsieevaatiofoaacitfalateeoucatesoagt（）：2505-2513.  
[10]FengLH,ZagXC,uoYesearchoheswatersoragderpacityofateesousinYuiaHEcological Risk Assessment:An International Journal,2009,15(4):714-726.  
[11] WangTX,uctal,52:134-146.  
[12] 赵卫，刘景双，苏伟，窦晶鑫.辽宁省辽河流域水环境承载力的多目标规划研究.中国环境科学,2008，28(1)：73-77.  
[13] GaoGQ.WaterenviroentalaringapacityalculationadprotetionmeasuresonHefangeservoirAppledechanics&ateals11,90-93:2537-2540.  
[14]MooreJ，isser，eesW.AurbanmetabolismndolgicaloitsntofetrVcouerualofiotalManagement，2013，124: 51-61.  
[15]WeinzeertGelioaltofa：asrocsalsand hybrid multiregional input-output analysis.Ecological Economics，2014,101:115-126.  
[16] 张万顺，齐迪，幸娅，彭虹，杨寅群.区域水生态承载力的量化研究与应用.武汉大学学报：工学版，2011,44（5)：560-564.  
[17] ZhangZ,LuWXZYogevelotealysdvatiofateolalapacityineiigefJilin Province in China basedonsystemdynamicsandanalytic hierarchy process.Ecological Modeling，2014,275：9-21.  
18] WangS,XuL，YangFL，WangH.AementofwatecologcalaringapacituderthetwopoliesineingCitohebasisoftheintegrated system dynamics model.Science of the Total Environment,2013,472：1070-1081.  
[19] 张星标，邓群钊.江西省水生态承载力分析.南昌大学学报：理科版，2011，35(6)：607-612.  
[20] ZengC,LiuY,HuJiXG,gXaeacoesaocalgcityfwujindistrictintheTaiLkeBasin,China.InteatioalJoualofEnviromentalResearchandublicHealth,Ol1,8（1)：64-8.  
[21]SunXstilfodits application to Taihu Lake Basin，China.Ecological Modelling,2015,295：216-226.  
[22］李靖，周孝德.叶尔羌河流域水生态承载力研究.西安理工大学学报，2009,25(3)：249-255  
[23］王西琴，高伟，曾勇.基于 SD模型的水生态承载力模拟优化与例证.系统工程理论与实践，2014，34（5）：1352-1360.  
[24］陈广洲，汪家权，解华明.粒子群算法在投影寻踪模型优化求解中的应用.计算机仿真，2008,25（8）：159-165.  
[25]YangJF,LeiK，uS，engWiaoFAssessntofwatereviotalcaingapacityfstaaleeveloeusingoupedsystemdynamicaproachapliedteTelingofteLiaRiverBsin，hina.EnviromentalEarthiences，Ol5,（9）：-5183.  
[26］严子奇，夏军，左其亭，张永勇.淮河流域水环境承载能力计算系统的构建.资源科学，2009,31（7)：1150-1157.  
27]YangilivAdvanced Materials Research,2013，869:627-633.  
[28］唐克旺.水生态文明的内涵及评价体系探讨.水资源保护，2013，29(4)：1-4.  
[29］崔东文，金波.基于随机森林回归算法的水生态文明综合评价.水利水电科技进展，2014，（5）：56-60.  
[30]GuoSL,XuC,ChenH,LiuDReviedAemetofInteractioetweenWatersedHydrologndSocietySysteJalfWateResources Research,2016,5(1)：1-15.  
[31］杨俊峰，乔飞，韩雪梅，柴淼瑞.流域水生态承载力评价指标体系研究//2013中国环境科学学会学术年会论文集(第六卷).昆明：中国环境科学学会，2013.  
[32]Jago-OnKAB,KanekoS,FujkuraR,FujwaraA,ImaiT,MatsumotoT,ZhangJY,TanikawaH,Tanaka K,LeeB,TaniguchiM.Urbanizationdsufaceviotals：ntatelatiisiitftalEvot,407(9)：3089-3104.  
［33］付强，赵小勇.投影寻踪模型原理及其应用.北京：科学出版社，2006.  
[34]王柏，张忠学，李芳花，孙艳玲，丁红.基于改进双链量子遗传算法的投影寻踪调亏灌溉综合评价.农业工程学报，2012,28（2）：84-89.  
[35]HuangKW，ChenJL，YangCS,TsaiCW.Amemetic graitationsearchalgoritforsolvingcusterigprobles/15IEEECogesEvolutionary Computation（CEC）.Sendai：IEEE,2015.  
[36］张维平，任雪飞，李国强，牛培峰.改进的万有引力搜索算法在函数优化中的应用.计算机应用,2013，33（5)：1317-1320.  
[37] 刘勇，马良.非线性极大极小问题的混沌万有引力搜索算法求解．计算机应用研究，2012，29(1）：47-48.  
[38] 唐柱，丁学明，刘灿.基于引力搜索和粒子群混合优化算法的 T-S 模型辨识.上海理工大学学报,2013,35(4)：351-354.  
[39] 李春龙，戴娟，潘丰.引力搜索算法中粒子记忆性改进的研究.计算机应用,2012，32（10)：2732-2735.  
[40］库路巴依·吾布力.投影追踪模型在新疆农业灌溉用水系数影响因子分析中的应用.水利规划与设计，2016，（2）：21-23.  
[41] 王晶，李云鹤，郭东阳.京津冀区域水资源需求分析与供水保障对策.海河水利，2014，（3)：1-3.  
[42] 张京成，刘利永.绿色奥运—一个碧水蓝天的承诺.北京：科学出版社，2008.  
[43］孟庆华.基于生态足迹的京津冀人口容量研究.林业资源管理，2014，（4)：8-13.  
[44] 王少剑，方创琳，王洋.京津冀地区城市化与生态环境交互耦合关系定量测度.生态学报，2015，35（7)：2244-2254.  
[45］吴健，昌敦虎，孙嘉轩.京津冀一体化进程中的水环境保护策略.环境保护，2014，42（17）：34-37.  
[46］李新斗，席志敏.河北平原深层地下水开采程度评价.南水北调与水利科技，2013，11(6)：129-132.