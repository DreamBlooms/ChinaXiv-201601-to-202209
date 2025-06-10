# 基于青冈和滇青冈生境模拟的湿润和半湿润常绿阔叶林替代分布及气候解释

（西南林业大学西南地区生物多样性保育国家林业局重点实验室，昆明650224)

摘要：为揭示湿润常绿阔叶林和半湿润常绿阔叶林替代分布的气候制约因子，选择其代表性优势树种青冈(Cyclobalanopsis glauca)和滇青冈(C.glaucoides)为研究对象，收集两个物种的标本分布点数据和19个生物气候因子图层数据，运用MaxEnt模型，模拟其潜在分布区，通过判别分析(DFA)、方差分析(ANOVA)和核密度分析三种方法量化两个树种的生态位差异，从而解释两类植被地理替代分布规律及其主导气候因子。结果表明：(1)青冈和与滇青冈MaxEnt拟合的AUC值分别为0.995和0.986，准确预测了两物种的潜在分布；青冈适宜于北纬 $2 0 ^ { \circ }$ ${ \sim } 3 0 ^ { \circ }$ 的亚热带及北热带地区，滇青冈集中分布于云贵高原亚热带区域。 (2)判别分析(DFA)和方差分析的结果一致表明昼夜温差月均值(bio2)、等温性(bio3)、降水季节性变化(bio15)是造成二者生态位分异的主导气候因子。(3)核密度分析显示昼夜温差月均值(bio2)、等温性(bio3)、温度季节性变动系数(bio4)是影响两物种生态位分化的主导温度因子；而降水季节性变化(bio15)、年降水量(bio12)、最干月降水量(bio14)、最干季降水量(bio17)、最冷季降水量(bio19)是两物种生态位分化的主导降水因子。上述结果说明等温性、温度季节性变异、季节性降水等表征气候季节性差异的变量是造成湿润与半湿润常绿阔叶林出现替代分布的主要原因。

关键词：青冈，滇青冈，湿润常绿阔叶林，半湿润常绿阔叶林，生态位模拟，替代分布中图分类号：Q948 文献标识码：A

# Displacement distribution and climax explanation on semi-humid and humid evergreen broadleaved forests using niche analysis of Cyclobalanopsis glauca and C. glaucoides in

# China

LIU Ying, TIAN Bin, OU Guanglong (1.Key LaboratoryofState Forestry Administration on Biodiversity Conservation in Southwest China,Southwest Forestry University,Kunming 650224, China)

Abstract: To explain the geographical displacement law and the dominant climate factors between humidevergreen broadleaved forests(HEBF） and semi-humid evergreen broadleaved forests(SHEBF)， Cyclobalanopsis glauca and C. glaucoides were selected as research objects because both species are the typical dominant tree species of the HEBF and SHEBF, then the specimens data of both species and the 19 bio-climate factors map layer were collected to simulate their distribution area using MaxEnt model. Moreover, the niche differences were quantitatively analyzed by the kernel density analysis,discriminant function analysis (DFA）and analysis of variance (ANOVA） to reveal the dominant climate factors which afect the niche differentiation between both species, then analyzed the geographical displacement law and the dominant climate factors between the HEBF and SHEBF. The results were as follows: (1) The AUC values of $C$ glauca and $C _ { }$ ：glaucoides are O.995 and 0.986 respectively, and it accurately predicted the potential distribution of the two species; $C .$ glauca is suitable for the subtropical and North-tropical regions of $2 0 ^ { \circ }$ to $3 0 ^ { \circ } \mathrm { ~ N ~ }$ but $C$ ：glaucoides is mainly distributed in subtropical area of Yunnan-Guizhou Plateau. (2)The results of DFA and ANOVA were consistent, and the mean diurnal range (bio2), isothermality (bio3）and the precipitation seasonality (biol5） were the climate variables that promoted the niche differentiation of the two species.(3） The mean diurnal range (bio2), isothermality (bio3） and temperature seasonality (bio4） are the dominant temperature factors affecting the niche differences of the both species; However the precipitation seasonality (bio15), precipitation of the driest month (bio14),precipitation of the driest quarter (biol7) and precipitation of the coldest quarter (biol9) also significantly afect the difference of geographical distribution. Therefore, it can be found that the seasonal difference of temperature and precipitation are the main factors determining geographical displacement distribution of the HEBF and SHEBF from the niche simulation of $C$ ：glauca and C. glaucoides.

Key words: Cyclobalanopsis glauca, Cyclobalanopsis glaucoides,humid evergreen broadleaved forest, semi-humid evergreen broadleaved forest, niche model, displacement distribution

植被地理替代分布呈现出水平和垂直变化特征(王铁娟，2004；李静等，2006；刘彬彬等，2013；于明茜，2015；李缓，2019)，造成地理替代现象的原因比较复杂，包括地理阻隔、遗传分化、气候以及地史等多方面因素(罗艳和周浙昆，2001；李缓，2019)，其中气候是预测树木及植被类型分布的主要因子，并与其他驱动因素相互作用影响森林的功能和动态过程，从而成为植被替代分布形成的主导因子之一(Boisvert-Marshet et al.,2014；Grunig et al.,2017;郑维艳和曹坤芳，2020；Zouetal.,2020)，明晰植被分布与气候的关系并揭示其影响机制对于准确分析植被分布规律、植被功能过程及其生态恢复等具有重要理论和实践意义(Fang etal.，2002；Buitenwerf & Higgins，2016)。

亚热带常绿阔叶林作为森林生态系统中的重要组成部分，在维持生态系统平衡与稳定方面发挥着不可替代的作用(丁圣彦和宋永昌，2004；Wang etal.,2007)，中国作为常绿阔叶林分布最为广泛的国家，在秦岭-淮河线以南，青藏高原以东，云南、福建、东海岸沿线以内的广大区域成片分布(吴征镒，1980；Dunmei etal.,2012；Zhu，2017)，其中东部湿润常绿阔叶林和西部半湿润常绿阔叶林是主要的两个地带性植被亚型，且存在明显的替代分布特征(吴征镒，1980；吴征镒和朱彦丞，1987；李昌华，1997；宋永昌等，2005；曾觉民，2018)。气候和海拔的梯度变化会造成植被的替代分布差异(Ge＆Xie,2017；Elsen etal.,2018)，Fang&Yoda(1991)揭示了中国常绿阔叶林分布上限与气候因子的关系，倪健和宋永昌(1997)通过青冈的地理分布与气候因子的关系得出常绿阔叶林对气候变化的反应不十分敏感和剧烈，且寒冷指数等反映整体年际气候变化的指数不能说明其对分布界限的影响(Chiuetal.,2014)，而反映气候的季节变化甚至日变化特征的气候指标对植被分布分异带来更大的影响(Emakovich etal.,2014；Chan et al.,2016；Allen et al.,2017；Ge et al.,2019)。可见，学者们已经对亚热带常绿阔叶林的替代分布现象以及常绿阔叶林这一植被型与气候因子的关系进行了较为详细的阐述，但对于植被亚型间替代分布的主导因子及其替代分布影响机制，尤其是植被亚型替代分布的季节性气候变化影响的研究鲜有报道。

物种分布模型可以准确预测和分析物种的适宜生境范围，模型运行稳定，还可揭示植被分布的影响气候变量而被广泛应用于生态学、保护生物学和生物地理学等领域(Elith &Leathwick,2009)。目前最大熵模型(MaxEnt)、基于遗传算法的规则组合模型(GARP)、CLIMEX模型、生态位因子分析模型(ENFA)和生物气候分析和预测系统模型(BIOCLIM)是最常用的五种物种分布模型。其中MaxEnt模型可以通过物种的已知分布数据和气候变量建立物种地理分布与气候之间的联系(Phillips etal.,2008)，且能在大尺度空间上获取更多的物种信息，为建立系统全面的物种与环境的关系提供更为丰富的环境信息(庄鸿飞等，2018)，是目前物种分布模拟中认可度最高、拟合度较好的模型(Phillips et al.,2006；曹向锋等，2010)。

基于优势种的生态位模拟及差异分析，揭示造成其分布差异的气候制约因素，尤其是气候季节性变化的影响机制对于阐明中国东西部两类地带性常绿阔叶林植被亚型的替代分布规律具有重要理论和实践意义。鉴于此，本研究选择湿润和半湿润常绿阔叶林中具有代表性的优势树种青冈(Cyclobalanopsis glauca)和滇青冈(C.glauca)为研究对象，收集标本分布点数据，结合气候变量，运用MaxEnt 模型，模拟预测两者的适生区范围，分析造成两个树种生态位分化的气候因素，进而探讨湿润与半湿润常绿阔叶林的替代分布格局，以及与气候条件的相互关系，揭示其替代分布的主导因素，从而为亚热带常绿阔叶林分布和影响机制研究提供重要的科学依据。

# 1材料与方法

# 1.1标本点数据

收集中国数字植物标本数据库(CVH，http://www.cvh.org.cn)中青冈与滇青冈的标本信息,筛除样本采集地存疑和出现重复的样点，获取精确样本记录地点的经纬度坐标，作为物种生境模拟的基础数据。共获取两个物种603个标本点，其中包括 432个青冈标本点和171个滇青冈标本点(图1d)。

# 1.2气候变量数据

气候变量由 Worldclim(http://www.worldclim.org/)下载收集19 个生物气候图层(表1)，数据空间分辨率为 $3 0 ^ { \prime \prime }$ (Hijmans et al., 2005)。

表119个生物气候因子  
Table119 bio-climate factors   

<html><body><table><tr><td>简写 Abbreviation</td><td>气候变量 Climate variables</td><td>简写 Abbreviation</td><td>气候变量 Climatevariables</td></tr><tr><td>bio1</td><td>年均温 Annual mean temperature</td><td>bio11</td><td>最冷季平均气温 Mean temperature of the coldest quarter</td></tr><tr><td>bio2</td><td>昼夜温差月均值 Mean diurnal range</td><td>bio12</td><td>年降水量 Annual average precipitation</td></tr><tr><td>bio3</td><td>Isoeality</td><td>bio13</td><td>Precipitat最湿月水量est month</td></tr><tr><td>bio4</td><td>温度季节性变动系数 Temperature seasonality</td><td>bio14</td><td>最干月降水量 Precipitation of the driest month</td></tr><tr><td>bio5</td><td>最热月最高气温 Max temperature of the warmest month</td><td>bio15</td><td>降水量季节性变化 (变异系数) Precipitation seasonality (variable coefficient)</td></tr><tr><td>bio6</td><td>最冷月最低气温 Min temperature of the coldest month</td><td>bio16</td><td>最湿季降水量 Precipitation of the wettest quarter</td></tr><tr><td>bio7</td><td>气温年变化范围 Range of annual temperature</td><td>bio17</td><td>最干季降水量 Precipitation of the driest quarter</td></tr></table></body></html>

<html><body><table><tr><td>bio8</td><td>Mean tempaus 平f 均气ltestqurter</td><td>bio18</td><td>Precitatin 委降水量est quarter</td></tr><tr><td>bio9</td><td>Mean tem干e 均气ist quarter</td><td>bio19</td><td>Precipiti最N冷fh 水量estquarter</td></tr><tr><td>bio10</td><td>最暖季平均气温 Mean temperature of the warmest quarter</td><td></td><td></td></tr></table></body></html>

# 1.3生态位模型

利用物种分布模型，以物种标本点和19个气候变量为数据，拟合青冈与滇青冈的适宜生境。在MaxEnt3.3.1中使用默认设置为评估模型的有效性(Philips etal.,2008)，设置 $7 5 \%$ 的物种分布点作为训练数据，剩余 $2 5 \%$ 作为交互检验的数据集据，运行10次重复进行交互验证(Pearson et al.，2007)。MaxEnt模型提供刀切法(Jackknife)检验气候变量对模型构建的贡献率(Migueletal.,2010)，并将模拟结果进行数据转换后生成物种适宜生境分布图，在ArcGIS10.5中利用分类功能进行适生等级分类，共划分为5个等级：非适生区 $0 . 0 0 { \sim } 0 . 0 2$ ，低适生区0.02\~0.25，中适生区0.25\~0.50，高适生区0.50\~0.75，最适生区 $> 0 . 7 5$ 。

# 1.4生态位差异分析

本研究采用三种统计方法分析青冈与滇青冈的生态位差异。首先，利用SPSS 22软件用判别分析(DFA)评估各气候变量对物种分布的贡献度；其次，运用SPSS 22软件，用方差分析(ANOVA)定量描述两物种在各生物气候因子的种内及种间差异；第三，基于Eviews10软件，采用核密度分析(kermel density analysis)将样本数据进行拟合，得到整个样本集的概率密度函数，通过核密度曲线描述19个气候变量的生态位变化幅度，由此确定两物种在各气候变量中的差异。

# 2结果与分析

# 2.1分布区预测

通过生态位模拟，两个物种平均模型的测试 AUC 值均高于0.9，其中青冈模拟的 AUC值为0.995，滇青冈模拟的AUC值为0.986，表明预测结果具有较高的可靠性，可得到两个物种准确的适生区分布范围(图1)。青冈分布于中国亚热带地区及热带北缘，以及日本南部和印度北部，其中最适生区是贵州东部以东、南岭以北和秦岭以南，基本涵盖了中国亚热带东部地区(图1：A)；滇青冈的分布区则集中在中国西南部云南、四川、贵州、重庆、西藏等地，以及喜马拉雅山地区，最适生区则以云南中北部、四川南部和贵州西北部为主(图1：B)。从两个树种的最适生区 $( > 0 . 7 5$ 分布概率)来看，二者几乎在云南东部和贵州西部形成明显的替代分布(图1：C)。

![](images/3b8af940094c9d4aa14029ee58d4c065e48195f3f787d59e7f7a57ad6d2ca8da.jpg)

A.青冈的适宜生境分布情况；B.滇青冈的适宜生境分布情况；C.青冈与滇青冈最适生区分布情况；D.青 冈与滇青冈的样本分布点。 A.Suitable habitat distributionof Cyclobalanopsis glauca;B.Suitable habitat distributionofC.glaucoides；C.The most suitable area for $C$ ：glauca and C. glaucoides；D.The specimens point of C. glauca and C. glaucoides.

图1青冈与滇青冈的适生区分布和样本分布点示意图

Fig.1 Suitable distribution area and the specimens points of Cyclobalanopsis glauca and $C$ glaucoides

# 2.2生态位差异分析

MaxEnt模拟的刀切法(Jackknife)给出19个气候变量对青冈和滇青冈的相对贡献率(表2)。青冈的分布主要受最干月降水量(bio14)、年降水量(bio12)和最暖季降水量(bio18)的影响，三者的贡献率分别为 $3 8 . 0 \%$ 、 $2 2 . 1 \%$ 和 $1 5 . 8 \%$ ，累计贡献率为 $7 5 . 9 \%$ ，这说明了降水及降水的季节分配是影响青冈分布的主导因子；而滇青冈的分布则主要受气温年变化范围(bio7)、最暖季降水量(bio18)和温度季节性变动系数(bio4)的影响，三者的贡献率分别为 $2 5 . 3 \%$ 、 $2 5 . 1 \%$ 和$1 8 . 0 \%$ ，累计贡献率为 $6 8 . 4 \%$ ，这说明滇青冈分布受温度和降水季节性变化的限制。

通过判别函数分析(DFA)可以看出(表2)，造成两物种间分布差异的主要气候因子是等温性(bio3)、昼夜温差月均值(bio2)和降水季节性变化(bio15)，其差异贡献率分别为0.81、0.73和0.71；温度季节性变动系数(bio4)、最热月最高气温(bio5)、最暖季平均气温(bio10)、最干月降水量(bio14)、最干季降水量(bio17)和最冷季降水量(bio19)对两物种的分布差异的贡献值均在0.6\~0.7之间。可见，反映温度和降水的季节性差异的气候因子是造成两物种分布差异的主要气候因子。

此外，通过方差分析发现，昼夜温差月均值(bio2)、等温性(bio3)、降水季节性变化(bio15)的种间差异大于种内差异，最暖季降水量(bio18)种间差异与种内差异的方差值相等，而其余变量的种间差异均大于种内差异(表3)，这说明青冈与滇青冈生态位分化的原因是两物种对温度变化幅度以及降水季节性分配的适应存在差异性。

# 表2青冈与滇青冈气候变量的贡献率和两两之间判别分析(DFA)的相对贡献

Table 2 Contribution rate and the relative contributions of the 19 climate variables in pairwise comparisons of Cyclobalanopsis glauca and C. glaucoides by discriminant function analysis (DFf   

<html><body><table><tr><td rowspan="2">气候变量 Climate variables</td><td colspan="3">贡献率(%) Percent contribution</td><td rowspan="2">气候变量 Climate variables</td><td colspan="3">贡献率 (%) Percent contribution</td></tr><tr><td>青冈 C. glauca C. glaucoides</td><td>滇青冈</td><td>青冈-滇青冈 CA-CS</td><td>青冈</td><td>滇青冈 C. glauca C. glaucoides</td><td>青冈-滇青冈 CA-CS</td></tr><tr><td>bio1</td><td>0.2</td><td>0.2</td><td>-0.25</td><td>bio11</td><td>5.0</td><td>2.6</td><td>0.03</td></tr><tr><td>bio2</td><td>0.8</td><td>0.9</td><td>0.73</td><td>bio12</td><td>22.1</td><td>5.8</td><td>-0.44</td></tr><tr><td>bio3</td><td>0.6</td><td>0.7</td><td>0.81</td><td>bio13</td><td>0.2</td><td>9.3</td><td>-0.16</td></tr><tr><td>bio4</td><td>1.0</td><td>18.0</td><td>-0.61</td><td>bio14</td><td>38.0</td><td>0.1</td><td>-0.63</td></tr><tr><td>bio5</td><td>0.1</td><td>2.7</td><td>-0.60</td><td>bio15</td><td>2.6</td><td>0.1</td><td>0.71</td></tr><tr><td>bio6</td><td>9.7</td><td>1.6</td><td>-0.16</td><td>bio16</td><td>0.2</td><td>0.9</td><td>-0.16</td></tr><tr><td>bio7</td><td>2.4</td><td>25.3</td><td>-0.38</td><td>bio17</td><td>0.2</td><td>0.1</td><td>-0.64</td></tr><tr><td>bio8</td><td>0.2</td><td>0.1</td><td>-0.24</td><td>bio18</td><td>15.8</td><td>25.1</td><td>0.03</td></tr><tr><td>bio9</td><td>0.1</td><td>6.0</td><td>-0.08</td><td>bio19</td><td>0.5</td><td>0.3</td><td>-0.59</td></tr><tr><td>bio10</td><td>0.3</td><td>0.2</td><td>-0.60</td><td></td><td></td><td></td><td></td></tr></table></body></html>

注：青冈与滇青冈黑体显示的值表示贡献率排前四位的变量；青冈-滇青冈黑体显示的值表示两两比较中贡献率最高的三个变量。

Note: Values in boldface of Cyclobalanopsis glauca and C.glaucoides are represent the top four contributors; Values in boldface are for the three most significant variables for Cyclobalanopsis glauca-Cyclobalanopsis glaucoides(CA-CS).

表3不同气候变量的青冈与滇青冈方差分析 Table 3 ANOVA of the climate variables between Cyclobalanopsis glauca and C. glaucoides   

<html><body><table><tr><td rowspan="2">气候变量 Climate variables</td><td colspan="2">平方和 Sum of squares</td><td colspan="2">均方 Mean square</td><td colspan="2">方差百分比 Percentage of variance (%)</td></tr><tr><td>种间</td><td>种内</td><td>种间</td><td>种内</td><td>种间</td><td>种内</td></tr><tr><td></td><td>Among species</td><td>Within species</td><td>Among species</td><td>Within species Among species</td><td></td><td>Within species</td></tr><tr><td>bio1</td><td>83 885.36</td><td>511 236.60</td><td>83 885.36</td><td>854.91</td><td>14.10</td><td>85.90</td></tr><tr><td>bio2</td><td>106 304.03</td><td>70 608.44</td><td>106 304.03</td><td>118.07</td><td>60.09</td><td>39.91</td></tr><tr><td>bio3</td><td>30 553.70</td><td>18 393.09</td><td>30 553.70</td><td>30.76</td><td>62.42</td><td>37.58</td></tr><tr><td>bio4</td><td>604600000.00</td><td>705 700 000.00604 600000.00</td><td></td><td>1 180 093.52</td><td>46.14</td><td>53.86</td></tr><tr><td>bio5</td><td>433 523.75</td><td>486 933.45</td><td>433 523.75</td><td>814.27</td><td>47.10</td><td>52.90</td></tr><tr><td>bio6</td><td>68 274.61</td><td>788 039.79</td><td>68 274.61</td><td>1 317.79</td><td>7.97</td><td>92.03</td></tr><tr><td>bio7</td><td>157 713.11</td><td>539 908.89</td><td>157 713.11</td><td>902.86</td><td>22.61</td><td>77.39</td></tr><tr><td>bio8</td><td>102 762.38</td><td>495 930.34</td><td>102 762.38</td><td>829.32 1 544.66</td><td>17.16</td><td>82.84</td></tr><tr><td>bio9</td><td>15 090.19</td><td>923 708.61</td><td>15 090.19</td><td>737.62</td><td>1.61</td><td>98.39</td></tr><tr><td>bio10</td><td>394 464.16</td><td>441 097.96</td><td>394 464.16</td><td>1 277.82</td><td>47.21</td><td>52.79</td></tr><tr><td>bio11 bio12</td><td>285.64 25 080 000.00</td><td>764 133.50</td><td>285.64</td><td>81 587.61</td><td>0.04 33.95</td><td>99.96</td></tr><tr><td>bio13</td><td>139 788.96</td><td>48 790 000.00 1 844 872.50</td><td>25 080000.00 139 788.96</td><td>3 085.07</td><td>7.04</td><td>66.05</td></tr><tr><td>bio14</td><td>84 199.56</td><td>94 874.03</td><td>84 199.56</td><td>158.65</td><td>47.02</td><td>92.96</td></tr><tr><td>bio15</td><td>108 789.61</td><td>77 821.88</td><td>108 789.61</td><td>130.14</td><td>58.30</td><td>52.98</td></tr><tr><td>bio16</td><td>852 539.79</td><td>12 650 000.00</td><td>852 539.79</td><td>21 161.15</td><td>6.31</td><td>41.70</td></tr><tr><td>bio17</td><td>1 084 009.07</td><td>1 237 251.63</td><td>1 084 009.07</td><td>2 068.98</td><td>46.70</td><td>93.69</td></tr><tr><td>bio18</td><td>2 590.74</td><td>2 590.74</td><td>2 590.74</td><td>18 694.60</td><td>50.00</td><td>53.30 50.00</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>bio19</td><td>1 579 401.18</td><td>2 011 965.09</td><td>1 579 401.18</td><td>3 364.49</td><td>43.98</td><td>56.02</td></tr></table></body></html>

核密度分析直观反映两个物种对19个气候变量的生态位幅度变化(图2)。两物种在昼夜温差月均值(bio2)、等温性(bio3)、温度季节性变动系数(bio4)三个温度因子表现出明显的分异，这说明温度年内变化及日内变化差异是造成二者分布差异的主要温度制约因素；而其余温度因子变化幅度较为相近，尤其在最冷月最低气温(bio6)上较为相似，说明两树种对极端低温的适应是相似的(图2)。另外，两物种对降水因子上的适应差异较大，尤其是在降水季节性变化(bio15)上分异最为突出，且滇青冈在每个降水因子上表现出较高的波动，说明滇青冈对降水季节性变化产生了适应。综上所述，通过两物种在不同气候因子生态位幅度变化差异可以看出，表征温度和降水年内或日内分配差异的变量是造成二者分布差异的主导气候因子。

![](images/8f73cdcd406e716f57ac952389a6c11e438f1b0215f0972e4cba87391fbc6580.jpg)  
图2 青冈与滇青冈随不同气候变量的核密度分布 Fig.2 Kernel density distribution of Cyclobalanopsis glauca and C. glaucoides with the climate variables

# 3讨论与结论

自 Phillips etal.(2006)首次引入MaxEnt 模型预测物种潜在分布之后，让生态位量化研究成为可能(Kozak etal.,2008),本研究青冈和滇青冈生境模拟的AUC值分别为0.995 和0.986，均高于0.90，刘艳梅等(2018)认为，AUC高于0.9说明两个物种的生境预测结果具有较高的可信度。本研究预测的青冈与滇青冈适宜生境中，在中国的分布范围与《中国植物志》的分布区位置基本一致(陈焕镛和黄成就，1998)，国外分布向南延伸至印度、缅甸北部，向东、东北散布到朝鲜半岛、日本，与周浙昆(1992)绘制的青冈属物种的分布区相符，进一步印证了本文青冈与滇青冈生境模拟的准确性。此外，从青冈和滇青冈的最适分布区 $( > 0 . 7 5 )$ 可以看出，青冈主要分布于北纬 $2 0 ^ { \circ } { \sim } 3 0 ^ { \circ }$ 之间的亚热带及北热带地区，滇青冈集中分布在滇中地区以及四川南部，二者以云南东部、贵州西部为界形成明显分异，这也为分析两个物种的生态位差异，以及基于这两个代表性优势树种的湿润和半湿润常绿阔叶林的替代分布规律分析提供了准确的数据保障。

本研究通过影响青冈与滇青冈分布的19个气候因子的方差分析、判别分析(DFA)和核密度分析发现，等温性(bio3)和降水季节性变化(bio15)是两物种之间的差异贡献率最高的温度因子和降水因子，其贡献率分别为0.81和0.71，昼夜温差月均值(bio2)的贡献率也达到了0.73，且三个气候因子的种间差异显著大于种内差异；核密度分析表明青冈和滇青冈在昼夜温差月均值(bio2)、等温性(bio3)、温度季节性变动系数(bio4)、降水季节性变化(bio15)等气候因子上呈现出显著的生态位分化。气候及因为海拔差异带来的气候因子间接变化会影响植被分布(Ge& Xie,2017；Elsen etal.,2018)，Fang&Yoda(1991)，温度和降水因素限制了常绿阔叶林的分布界限；倪健和宋永昌(1997)基于常绿阔叶林的主要优势种与气候指数的关系将青冈和滇青冈分别归为低中温湿润型和低温湿润型，这些研究说明了温度因子是造成二者分异的主导因子，但是该研究仅采用反映温度和降水总体特征的Kira指数等气候指数来分析。但反映整体年际气候变化的指数不能很好解释物种及植被分布界限的影响(Chiu etal.,2014)，不能解释温度和降水的季节分配差异对物种及植被分布的影响；而气候的季节性变化甚至是日变化特征都会对植被的分布产生影响(Ernakovich et al.,2014；Chan et al.,2016；Allen et al.,2017；Ge etal.,2019)，甚至起到相反的作用(Chan etal.,2016)。可见，昼夜温差月均值(bio2)、等温性(bio3)、降水季节性变化(bio15)等表征温度和气候季节性差异的气候因子是造成二者生态位分化的主导因子，进而限制了青冈与滇青冈的地理分布范围，使得两个物种的集中分布区在中国东西部呈现明显的替代分布。

优势种是对群落生境及其功能发挥具有重要控制作用的物种(宋永昌，2016)，基于优势树种分布可以揭示植被分布规律及影响因素(倪健和宋永昌，1997)。滇青冈作为西部半湿润常绿阔叶林区的代表性物种，其集中分布的云贵高原具有海拔高，降水季节分配不均的特点，在每年11月至次年4月份存在一个相对干旱的旱季，植被大多具有耐旱特性(吴征镒和朱彦丞，1987)，而青冈集中分布的亚热带东部地区则是湿润型气候，海拔较低、热量充足、生境湿润(倪健和宋永昌，1997)。本研究发现温度和气候季节性差异的气候因子是造成青冈和滇青冈两个物种生态位分化的主导因子，也就是说中国亚热带区域自东向西等温性逐渐降低、温度季节性变异增大、降水量相对减少，尤其是冬春两季降水显著减少，使得常绿阔叶林植被亚型呈现由喜温喜湿逐步变为喜温耐旱变化，从而使得湿润常绿阔叶林到半湿润常绿阔叶林沿经度和海拔梯度的替代分布变化。由此可见，反映温度和降水的年际变化差异会对常绿阔叶林替代分布产生一定影响，但温度和降水的季节分配差异才是青冈与滇青冈生态位分化的主要气候因子，也是造成湿润常绿阔叶林与半湿润常绿阔叶林替代分布的重要气候因素。

此外，中国亚热带常绿阔叶林区域跨度大，水热条件差异大(蔡永立和达良俊，2002),常绿阔叶林中普遍存在替代分布规律，以青冈与滇青冈这对优势树种表征湿润常绿阔叶林和半湿润常绿阔叶林的替代分布具有一定的代表性，有助于学者在大尺度上清晰认识湿润与半湿润常绿阔叶林植被分布特点与气候的相互关系，并明确造成常绿阔叶林替代分布的气候因素，但不同植被分布往往还受到地形、土壤条件、物种间关系等其它因素的影响(丁圣彦和宋永昌，2004；Wei et al.,2020；Long et al.,2021)，考虑多种环境因子及森林结构差异，从多种角度分析解释其替代规律，揭示中国常绿阔叶林的分布变化规律有待进一步研究。

# 参考文献：

ALLEN K, DUPUY JM, GEI M, et al., 2O17. Will seasonally dry tropical forests be sensitive or resistant to future changes in rainfall regimes? [J]. Environ Res Lett, 12: O23001.   
BOISVERT-MARSHL,PERIE, CATHERINE,et al., 2O14. Shifting with climate? Evidence for recent changes in tree species distribution at high latitudes[J]. Ecosphere, 5(7): art83.   
BUITENWERF R, Higgins S I, 2O16. Convergence among global biogeographical realms in the physiological niche of evergreen and deciduous vegetation[J]. Global Ecol Biogeogr, 25: 704-715.   
CAI YL,DA LJ, 2OO2. Ecological leaf anatomy of six evergreen species of Fagaceae in the eastern subtropical area of China[J]. Chin JAppl Environ Biol, (5): 460-466.[蔡永立，达良俊，2002. 亚热带东部壳斗科6种常绿植物叶的生态解剖[J]．应用与环境生物学报，(5)：460-466.]   
CAO XF, QIAN GL,HU BS,et al., 2010.Prediction of potential suitable distribution area of Flaveria bidentis in China based on niche models[J]. Chin JAppl Ecol, (12): 3063-3069.[曹 向锋，钱国良，胡白石，等,2010．采用生态位模型预测黄顶菊在中国的潜在适生区[J]．应 用生态学报，(12)：3063-3069.]   
CHAN W P, CJEN I C, COLWELL R K, et al., 2016. Seasonal and daily climate variation have opposite effects on species elevational range size[J]. Science,351: 1437-1439.   
CHEN HY, HUANG CJ, 1978. Flora Reipublicae Popularis Sinicae (Vol. 22)[M]. Beijing: Science Press:315-317.[陈焕镛，黄成就，1978．中国植物志(第 22卷)[M]．北京：科学出版社： 315-317]   
CHIU CA， CHIOU CR，LIN JR， et al.,2014. Coldness index does not indicate the upper limit of evergreen broad-leaved forest on a subtropical island[J]. JFor Res,19: 115-124.   
DING SY, SONG YC, 2O04. Research advances in vegetation dynamic of evergreen broad-leaved forest[J].Acta Ecol Sin,(8): 1769-1779.[丁圣彦，宋永昌，2004．常绿阔叶林植被动态研究 进展[J].生态学报，(8)：1769-1779.]   
DUNMEI L, JIANGSHAN L, HELENCE C, et al.,2012. Topographic variation in aboveground biomass in a subtropical evergreen broad-Leaved forest in China[J]. PLoS ONE,7(10): e48244.   
ELITH J, LEATHWICK JR,2O09a. Species distribution models: ecological explanation and prediction across space and time[J]. Ann Rev Ecol Evol S,40: 677-697.   
ELSEN PR,MONAHAN WB,MERENLENDER AM, 2018. Global paterns of protection of elevational gradients in mountain ranges[J]. Proc Natl Acad Sci USA,115: 6O04-6009.   
ERNAKOVICHJG,HOPPING K A, BERDANIER AB, et al.,2014. Predicted responses of arctic and alpine ecosystems to altered seasonality under climate change[J]. Global Chang Biol, 20: 3256- 3269.   
FANG J, Song Y,LIU H, et al., 2OO2. Vegetation-climate relationship and its application in the division of vegetation zone in China[J]. JIntegr Plant Biol, 44: 1105-1122.   
FANG JY, YODA K, 1991. Climate and vegetation in China V. Effect of climatic factors on the upper limit of distribution of evergreen broadleaf forest[J]. Ecol Res,6: 113-125.   
GE J,BERG B,XIE Z,2019. Climatic seasonality is linked to the occurrence of the mixed evergreen and deciduous broad-leaved forests in China[J]. Ecosphere,10(9).   
GE J, XIE Z, 2017. Geographical and climatic gradients of evergreen versus deciduous broadleaved tree species in subtropical China: implications for the definition of the mixed forest[J]. Ecol Evol, 7: 3636-3644.   
GRUNIG M, BEERLI N,BALLESTROS-MEJIA L, et al., 2017． How climatic variability is linked to the spatial distribution of range sizes: seasonality versus climate change velocity in sphingid moths[J]. JBiogeogr, 44: 2441-2450.   
HIJMANS RJ, CAMERON SE, PARRA JL, et al., 2O05. Very high resolution interpolated climate surfaces for global land areas[J]. Int J Climatol, 25: 1965-1978.   
KOZAK KH, GRAHAM CH, WIENS JJ, 20O8. Integrating GIS-based environmental data into evolutionary biology[J]. Trends Ecol Evol, 23: 141-148.   
LI CH,1997. The distribution of evergreen broad-leaves forests in East Asia[J]. Nat Resouc, (2): 36-45.[李昌华，1997．亚洲东部常绿阔叶林的分布[J]．自然资源，(2)：36-45.]   
LI J, CAO HL,LIAN JY, et al., 2OO6. Study on classification and geographical distribution of Castanopsis hystrix forest in China[J].Guihaia,26(1):22-27.[李静，曹洪麟，练琚藩，等, 2006．中国刺栲林的分类与分布初探[J]．广西植物，26(1)：22-27.]   
LI Y,2019. Species composition and geographical differentiation of the Fagaceae community in subtropical evergreen broad-leaved forest in China[D]. Hefei: Anhui Agricultural Univeristy. [李缓,2019.中国亚热带常绿阔叶林壳斗科群落的物种组成及其地理分异[D].合肥：安 徽农业大学.]   
LIU BB,LOU LB,LIU GY,2013.A floristic analysis of Fagaceae in Zhejiang Province, China[J]. JZhejiangA&FUniv,30(5):698-705.[刘彬彬，楼炉焕，刘广宁，2013．浙江省壳斗科植 物区系特征分析[J]．浙江农林大学学报，30(5)：698-705.]   
LIU YM, ZHOU SD, XIE DF, et al., 2018. Potential distribution of Fritillaria unibracteata predicted by the MaxEnt model[J].Guihaia,38(3):352-360.[刘艳梅，周颂东，谢登峰，等, 2018．基于最大熵模型(MaxEnt)预测暗紫贝母的潜在分布[J]．广西植物，38(3)：352-360.]   
LONG J, TANG M, CHEN G, 2021. Influence of strata-specific forest structural features on the regeneration of the evergreen broad-leaved forest in Tianmu Mountain[J]. PLoS ONE,16(2): e0247339.   
LUO Y, ZHOU ZK, 2001. Phytogeograph of Quercus subg. Cyclobalanopsis[J]. Plant Divers, 23(1): 1-16.[罗艳，周浙昆，2001．青冈亚属植物的地理分布[J]．植物分类与资源学报，23(1): 1-16.]   
MIGUEL B,ARAUJO RG, PEARSON WT, et al., 2010. Validation of species-climate impact models under climate change[J]. Global Change Biol,11(9): 1504-1513.   
NI J, SONG YC,1997. Relationships between geographical distribution of Cyclobalanopsis glauca and climate in China[J].Acta Bot Sin,39(5): 451-460.[倪健，宋永昌，1997．中国青冈的地 理分布与气候的关系[J]．植物学报，39(5)：451-460.]   
PEARSON RG, RAXWORTHY CJ, NAKAMURA M, et al., 20O7. Predicting species distributions from smallnumbers of occurence records: a test case using cryptic geckos in Madagascar[J]. J Biogeogr, 34(1): 102-117.   
PHILLIPS SJ, 2Oo8. Transfer ability, sample selection bias and background data in presence-only modelling: A response to Peterson [J]. Ecography, 31: 272-278.   
PHILLIPS SJ, ANDERSON RP, SCHAPIRE RE, 2006. Maximum entropy modeling of species geographic distributions[J]. Ecol Model, 190: 231-259.   
SONGYC,2016. Vegetation ecology [M]. 2nd ed. Beijing: Higher Education Pres: 353-360. [宋 永昌，2016.植被生态学[M].2版．北京：高等教育出版社：353-360.]   
SONG YC, CHEN XY, WANG XH, 2005. Study on evergreen broad-leaved forests of China: A retrospect and prospect[J].JEast Chin Norm Univ(Nat Sci Ed)(1): 1-8.[宋永昌，陈小勇，王 希华,2005．中国常绿阔叶林研究的回顾与展望[J].华东师范大学学报(自然科学版)，(1): 1-8.]   
WANG TJ, 2O04. Studies on Kinships, geographical replacement law and reasons of the six sand plants of Artemisia in northern China[D]. Huhhot: Inner Mongolia University.[王铁娟，2004. 中国北方六种沙蒿亲缘关系、替代分布规律与成因的研究[D]．呼和浩特：内蒙古大学.]   
WANG XH, KENT M, FANG XF, 2007. Evergreen broad-leaved forest in Eastern China: Its ecology and conservation and the importance of resprouting in forest restoration[J]. For Ecol Manag,245(1-3): 76-87.   
WEI SZ, TIE LH, LIAO J, et al., 2O2O. Nitrogen and phosphorus co-addition stimulates soil respiration in a subtropical evergreen broad-leaved forestJ]. Plant Soil, 45O(10): 171-182. WU ZY,1980.China vegetation[M].Beijing:Science Press: 306-355.[吴征镒，1980.中国植被 [M]．北京：科学出版社：306-355.] WU ZY,ZHU YC,1987. Yunnan vegetation[M]. Beijing:Science Press:193-230.[吴征镒，朱彦 丞，1987．云南植被[M]．北京：科学出版社：193-230.] YU MQ, 2O15. The xylem anatomy and germination of geographical substitute Garagana species[D].Lanzhou:Lanzhou University.[于明茜，2015．锦鸡儿属植物典型地理替代分布 种解剖结构特征和种子萌发特性研究[D]．兰州：兰州大学.] ZENG JM, 2O18.The classification system of natural forests and its geographic distribution in Yunnan[J].JSWFor Univ(Nat Sci Ed),38(6):1-18.[曾觉民,2018．云南自然森林分类系统 及地理分布研究[J]．西南林业大学学报(自然科学),38(6)：1-18.] ZHENG WY, CAO KF, 2O20. Impact of future climate change on potential geographical distribution of four Litsea species in China [J]. Guihaia, 40(11): 1584-1594.[郑维艳，曹坤芳,   
2020．未来气候变化对四种木姜子地理分布的影响[J]．广西植物，40(11)：1584-1594.] ZHOU ZK,1992. Origin phylogeny and dispersal of Quercus from China[J]. Acta Bot Yunnan, (3):   
227-236.[周浙昆，1992．中国栎属的起源演化及其扩散[J]．云南植物研究，(3)：227-236.] ZHU H, 2O19. Studies on the evergreen broad-leaved forests of Yunnan, Southwestern China[J]. Bot Rev, 85(1): 1-20. ZHUANG HF, ZHANG YB,WANG W, et al.,2018. Optimized hot spot analysis for probability of species distribution under different spatial scales based on MaxEnt model: Manglietia insignis case[J].Biodivers Sci,26(9):931-940.[庄鸿飞，张殷波，王伟，等，2018．基于最大熵模 型的不同尺度物种分布概率优化热点分析：以红色木莲为例[J]．生物多样性，26(9):   
931-940.] ZOU S, ZHANG Q, ZHOU G, et al., 2O20. Functional composition changes of a subtropical monsoon evergreen broad-leaved forest under environmental change[J]. Forests,11(2): 191.