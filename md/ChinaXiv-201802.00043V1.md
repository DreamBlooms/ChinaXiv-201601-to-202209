# DOI:10.5846/stxb201612232653

黎斌,何建华,屈赛,黄俊龙,李一挥.基于贝叶斯网络的城市生态红线划定方法.生态学报,2018,38(3):800-811.LiB,HeJHQuJbdedc2018,38(3) :800-811.

# 基于贝叶斯网络的城市生态红线划定方法

黎斌},何建华1,2,\*,屈赛¹,黄俊龙1,李一挥

1武汉大学资源与环境科学学院，武汉430079  
2 武汉大学地理信息系统教育部重点实验室，武汉430079  
3武汉大学测绘学院，武汉430079

摘要;生态红线划定是保护生态安全,协调城市建设、基本农田保护和生态保护之间矛盾的重要方法。目前,有关生态红线的划定方法多基于生态适宜性评价,忽视对土地利用变化的探究,缺少与城市建设发展相互协调,导致生态用地经常被占用,生态红线保护效果不好。在综合分析生态用地历史变化过程和生态适宜性条件的基础上,提出了基于贝叶斯网络的城市生态红线划定方法,并以鄂州市为研究区验证了模型划定的效果。划定结果表明,该方法符合鄂州市城市发展的趋势和生态用地空间分布特性,既有利于稳定且生态服务价值高的区域划入红线,又保证了生态红线空间的落地实施。与传统生态评价方法相比,贝叶斯网络模型划定方法的实效性更强,可以为城市生态红线划定方法研究提供参考和借鉴。

关键词：生态红线；贝叶斯网络;空间优化；划定方法

# A method of delimiting urban ecological red line protection area based on bayesian network

LI $\mathrm { B i n } ^ { 1 }$ ，HE Jianhua1,2,\*，QU Sai1，HUANG Junlong1，LI Yihui³

1 School of Resources and Environment Science，Wuhan University，Wuhan 43oo79,China   
2KeyLaboratoryofGeographic Information System MinistryofEducation，Wuhan University，Wuhan43Oo79,China   
3School of Geodesy and Geomatics，Wuhan University，Wuhan 43oo79,China

Abstract:Delimiting ecologicalred lines isthekeytoanswering spatial-allcationquestions forlandresources.Atpresent, most studiesonthedelimitationof ecologicalredlines have been basedontheevaluation of suitabilityconditionsof ecological land，without considering the process of historicalchange.Therefore，itcannotbe guaranteed thatthezoning results willadapttothetrends inecologicallandchangein thearea，leading tofrequentdesignationandadjustmentof ecologicalredlines.Inthisstudy，to guarantee the stabilityofecologicalredlines，weexaminedadelimitation method for ecological red lines basedona Bayesian network model，which included both factors concerning ecological suitability conditionsanddynamicchangeof theland.Next,the proposed model wasapplied toE-Zhou,acity nearthe mid-reachesof theYangtzeRiver.Inthisproposed model，ecological suitabilityfactors，whichrepresentedthequalityof theecological land，anddynamicchange factors，which ilustratedthe historyof theecologicalland，wereobtained.Using theecological land potential valueas the target variable，we definedthe structureof the network using expert knowledge.The Bayesian network was trained bythe maximum likelihood method with 2OoO random samplepoints.Theresultsshowedthat only $6 5 . 5 \%$ of ecological land remained stable from 2004 to 2O13 in E-Zhou City.For the two dynamic factors,the influenceof farmland occupancy was the greatest，and accounted for $4 3 . 6 \%$ ，whereas the influence of urban encroachment accounted for

$1 0 . 2 \%$ .The resultsof the sensitivity analysisalso indicated that farmland occupancy had the greatest influence on the potential value of the ecological land，with the highest variance reduction of $2 9 . 5 \%$ ，followed by eco-environmental sensitivity，and the importance of ecosystem services，which exhibited variance reductions of $8 . 5 5 \%$ and $1 . 8 4 \%$ ， respectively.The variancereductions for the distance toa water bodyand theecological protectionofa forest were greater thanthatofthedistancetoaroadorarailway,changeintraficfacilities，ndurbanconstruction,whichallhadlitleffect ontheecologicalland potential.Acausal link between influence factorsandthe targetvariablewasobtained during backward propagation in diagnostic analysis.Under theconditionthatthe value of ecological land potential was“yes”，the probability of the“extremely important”factors of ecosystem services and water conservation increased by $6 \%$ and $2 . 7 \%$ ： respectively.This indicated that thecontributions of ecosystem servicevaluesof a forest ecosystemand aquatic ecosystem increased.Furthermore，theprobabilitiesof“highlysensitive”and“extremelysensitive”factorsofecological sensitivity decreased by $1 3 . 4 \%$ and $1 . 8 \%$ ,respectively. This verified the improvement of the natural condition of the land by ecological land protection.Then，using thevalues for theecological suitabilityfactors in2O13，weobtaintherelative potential valueof each ecologicalland parcelastheecologicalredlinesthrough forwardreasoningof thetrained network，anddelimiting ecologicalland with the potentialvalueof thetarget variable.Theresultsshowed thatthis delimiting method worked in accordance withthetrends inurban development intheareaand spatialdistributionof ecologicalland inE-Zhou City.This methodcan improve the stabilityof ecosystem services，as well asensure thequantityandqualityof ecologicalred lines. This new and effective model could serve as a support for other cities.

Key Words: ecological red line；Bayesian network ； spatial optimization； delimiting model

生态红线是指在生态空间范围内具有特殊重要生态功能、必须强制性严格保护的区域,是保障和维护国家生态安全的底线[1]。作为生态文明建设的一项制度创新,划定城市生态红线是保护城市生态的基础和协调城市生态环境与经济发展的重要举措,对城市生态可持续发展具有重要意义[2]。改革开放以来,伴随着城市化进程中的用地扩张和产业发展,城市生态空间不断遭受蚕食,区域生态景观格局破碎,生态系统服务功能受损,城市生态安全格局受到严重威胁[3-5]。为保护生态安全,2011年国家首次提出划定生态红线的生态保护策略[6]。2014年我国开展生态红线划定工作,生态红线从区域生态管理体系上升为国家生态保护战略[7]。然而,从实践来看,现阶段生态红线的划定工作缺少与城市建设发展相协调的综合考虑,划定的生态保护用地经常被占用。因此,对生态红线划定方法进行深入研究十分必要。

生态红线的划定不是单纯的进行生态用地保护,它是在综合考虑城市建设和耕地保护基础上的生态保护过程。生态红线的划定既要最大限度的划入生态服务价值高的优质地块,保护生态系统服务功能和生态景观安全格局[8];又要保证划人地块具有稳定性,保证生态红线空间有效落地实施[9]。科学合理的生态红线划定应当包括两个方面的内容：一是基于生态适宜性评价,选取生态潜力大、生态价值高的地块;二是在保证划入地块生态服务价值的同时,考虑区域生态用地演变规律,保证生态红线稳定性。本文在考虑原有生态重要性的原则下，兼顾生态用地历史变化规律,以期解决生态用地易被占用的现象,维持生态红线的稳定性。

目前,我国的生态红线划定并没有统一的方法。相关研究大多是依据国家出台的生态红线划定政策划定空间红线。例如,丁雨.[10]、凡非得[11]等基于生态空间布局和生态系统的服务价值研究生态红线的划定;符娜[12]、刘雪华[13]、蒋大林等[14]以生态脆弱性和生态系统服务功能作为依据对生态保护区划定进行探讨;李洁等[15]基于生态网络规划探讨生态红线的划定;许妍[16]、曾江宁[17]、黄伟等[18]从生态功能重要性、生态环境敏感性和生态灾害危险性三方面进行研究,对海洋生态红线空间边界进行了划定。同时,马世发等[19]从生态安全格局维持角度，提出了一种上下协同的参与式划定方法并基于单要素生态问题情景分析，划定省级尺度生态红线。陈明辉等[20]运用RS 和GIS 技术基于离散粒子群算法对生态红线区进行多情景模拟。然而,这些研究都是基于生态适宜性或生态功能性评价划定生态红线,忽略了对土地利用变化规律的学习。由于缺乏对划定区域生态用地历史变化规律的研究,不能保证划定结果与区域土地利用变化趋势相适应,生态保护用地被占用的风险很大。基于此,本文在划定生态红线时考虑了生态用地的历史变化规律和生态适宜性两个方面的内容。

贝叶斯网络(Bayesian network，BN)是一种基于贝叶斯因果概率推理的概率网络模型[21]。通过先验数据和经验构建初始概率模型,再利用新的观察数据对初始模型进行改进学习。BN模型可以将土地的动态变化规律(先验知识)和现状的影响要素(观察数据)结合起来,进行综合的生态红线划定[22]。与其他模型方法不同,BN 属于非黑箱模型,能够表达各因子间的定性因果关系,支持预测性与诊断性等定量分析[23]。本文结合生态用地历史变化规律和生态适宜性条件,提出了基于BN 模型的生态红线划定方法。 （）

# 1基于BN的生态红线划定模型

# 1.1生态红线划定模型框架

本文利用BN 模型整合土地历史变化规律和生态适宜性条件,对生态用地进行模拟,划定生态红线。模型主要包括生态适宜性因子选取、生态用地动态变化过程分析、BN 模型结构学习与参数学习、敏感度分析和诊断性分析。基于BN模型的生态红线划定方法框架结构如图1所示。模型模拟过程综合考虑以下两个方面内容：(1)生态用地历史动态性。对两个时间段的生态用地状况进行叠加对比,得到研究区土地历史变化规律,用于BN 模型中生态用地变化规律学习,并与现状影响因子结合预测地块划分为生态红线区的概率,使模拟结果更真实准确。（2)生态适宜性因子层次性。通过对土地利用现状图的提取,获得图斑层次的生态适宜性因子,纳入生态红线划定的指标体系中,再对因子划分等级,提高模拟结果的科学合理性。通过 BN 模型的学习和推理,得到各地块的潜力值,并将潜力值按大小排序,达到划定生态红线面积。最后对生态红线划定结果进行验证和分析。

# 1.2生态适宜性指标选取

生态适宜性因子反映出生态用地的自然状况和区位条件。在自然条件中,地形条件包括坡度、高程和地形起伏度;水土保持条件包括水源涵养程度、水土流失程度、到水域距离和到生态公益林距离;土地质量包括生态用地敏感性、生态系统服务功能。这些生态适宜性因子体现出地块的生态潜力和耕地占用阻力。区位条件包括到公路的距离、到铁路的距离和到镇中心的距离。区位因子体现了建设用地和交通设施对生态用地的影响。 ）

# 1.3生态用地的演变过程

分析生态用地的历史变化过程可以确定导致生态用地变化的驱动因素,学习区域土地变化趋势。将生态用地的演变过程纳人生态红线划定指标体系既有利于实现划人地块的稳定，又能够协调生态保护和城市建设、基本农田保护之间的矛盾。理论上,生态用地演变过程分为两种类型：一是耕地占用生态用地;二是建设用地占用生态用地。

基于 BN 的生态红线划定模型指标体系(表1)由生态适宜性因子、生态用地历史变化因子和目标因子共同组成。

表1生态红线划定模型指标体系  
Table 1 Index system of ecological red line protection zoning model   

<html><body><table><tr><td>生态适宜性因子 Indicesof ecological suitability</td><td>生态环境敏感性,生态服务功能重要性坡度,水源涵养重要程度,水土流失严重程 度,坡度,高程,地形起伏度，距水域距离,距铁路距离,距公路距离，距镇中心距 离，距生态林距离</td></tr><tr><td>生态用地历史变化因子</td><td>建设占用，耕地占用</td></tr><tr><td>Indices of land change 目标变量 Target variable</td><td>生态用地潜力</td></tr></table></body></html>

![](images/17d5e6dc059123e579b6b5fc2a061101229de303bbbab2fe1c2636973aa5651e.jpg)  
图1基于BN的生态红线划定模型框架图  
Fig.1Framework of ecological red line protection zoning model based on BN

1.4贝叶斯网络模型结构构建和参数学习

网络结构的构建和节点参数的学习是构建BN的两个部分。网络结构构建的目的是体现因子间定性与定量两方面的联系。传统的算法如三阶段分析算法[24]和 SGS（Spirtes,Glymour,Scheines）算法[25]可以得到因子间的统计学联系,但无法获得因子间因果关系[26]。因此,本文采用专家经验法,基于因子间的因果联系,运用 Matlab 软件编写程序进行BN模型结构的构建,并根据相关的土地利用变化模型对网络结构进行修正,构建结果如图2所示。

图2中,目标变量"生态用地潜力"在受到生态敏感性和生态服务功能重要性影响的同时也受到耕地占用和建设占用的直接影响,以体现出生态适宜性因子和历史变化因子对生态红线划定的共同作用。耕地占用受到距水域距离和坡度的共同影响,模拟在土地灌溉和地形变化的条件下,耕地占用生态用地的情况。建设占用受到距公路、铁路、镇中心距离等可达性要素的影响,反映交通设施和城市建设对生态用地的占用情况。生态敏感性受到水土流失、地形起伏和到水域距离的共同作用,模拟土地的质量、地形和灌溉条件对生态环境的影响力;生态服务功能性受到水源涵养和到生态公益林距离的作用,模拟水域、林地对生态系统服务价值的评估。水土流失程度受到坡度、高程和到水域距离的影响。

BN 的参数学习通过从现有的观察数据中获得各因子的条件概率表进行学习。根据观察数据的状况,参数学习方法包括数据完整时最大似然估计法[27]、贝叶斯方法[28]和数据不完整时的最大期望算法[29]和吉布斯抽样算法[30]。本次实验训练数据完整,采用最大似然法进行参数学习,通过 Matlab 软件的 BN工具箱程序设计实现。将生态适宜性因子与生态用地动态变化因子(时间点1)作为训练数据,进行网络参数学习。训练结束后的 BN模型结果包含了因子间的相互联系及“生态用地潜力”概率值。再将新的生态适宜性因子数据（时间点2)代入已经学习好的BN 模型中,作为下一步模型推理的基础

![](images/fc3fc5d85381f575ad00d87e49e4be44f9f04bcaaa2bf6bd06d9946440e7cfed.jpg)  
图2贝叶斯网络模型结构  
Fig.2The structure of Bayesian network

# 1.5贝叶斯网络模型敏感度分析与诊断性分析

敏感度分析和诊断性分析都是量化BN模型中因子依赖程度的方法[31]。通过BN 的正向推理,对目标因子“生态用地潜力"进行敏感度分析,可以得到各因子对生态用地的影响力大小。敏感度分析结果用方差缩减来表示,方差缩减值越大,输入因子的影响力就越大。与敏感度分析相反,诊断性分析是通过给予目标变量一个特定的状态,来观察影响因子的概率分布变化。诊断性分析结果用概率变化来表示,概率变化程度越大，则表示两者联系程度越紧密。本文通过Netica 软件对 BN 变量进行敏感度分析和诊断性分析。

# 2鄂州市生态红线划定实例

# 2.1 研究区域概况

本文选取湖北省鄂州市为研究区。鄂州市位于湖北省东南部， $1 1 4 ^ { \circ } 3 2 ^ { \prime } - 1 1 5 ^ { \circ } 0 5 ^ { \prime } \mathrm { E } , 3 0 ^ { \circ } 0 0 ^ { \prime } - 3 0 ^ { \circ } 0 6 ^ { \prime } \mathrm { N } ,$ 长江中游沿岸,紧邻武汉市。鄂州市拥有丰富的生态资源，是国家重要的水源涵养区,生态保护研究的典型区域,是维护长江流域中游水环境安全的重要城市,也是武汉城市圈的重要节点城市（图3）。近年来,鄂州市发展速度较快,生态保护与城市建设 耕地保护之间的矛盾凸显,土地供需矛盾尖锐。2004 年至 2013年间,城镇建设用地由 $5 4 . 4 8 \mathrm { k m } ^ { 2 }$ 增长到 $9 3 . 0 4 \mathrm { k m } ^ { 2 }$ 。部分湖泊被填埋占用,生态环境遭到进一步破坏。在此形势下，开展鄂州市生态红线划定工作,对保障城市生态环境安全、维护长江中游生态系统健康具有重要意义。

# 2.2数据来源与数据处理

研究数据包括鄂州市 2004年和2013年两个年份的土地利用现状矢量图、土地利用规划生态红线管控分区图、水土流失分布图、鄂州市行政区划图和通过遥感影像获取的高程、坡度、地形起伏度栅格图。同时利用ArcGIS 空间分析和距离工具得到了水源涵养分布图、生态敏感性分布图、生态服务功能重要性分布图和划定模型要素栅格图。基础数据如图4所示。

以 2004 年鄂州市生态用地为生成范围,按面积比例生成 20000 个随机样本点。将样本点与基础数据栅格图进行空间叠加，获取各样本点要素变量值。另外，通过与2013年土地利用现状图的叠置分析,获取各样本点生态属性信息。将这些样本点作为训练数据,用于BN模型参数学习。BN 处理离散数据的效果较好,需要进一步对模型各要素值进行离散处理。变量离散分级情况如表2所示。

考虑到模型的精度和复杂性,参考相关政策及专家经验知识的情况下将连续变量离散为两到四个等级。例如,根据我国《第二次土地调查技术规程》,将坡度分为"0—2”,“2—5”，“5—15”和“ $\geqslant 1 5$ ”四个等级。二元变量的等级根据土地利用变化状况设定。例如,将“生态用地潜力”为“是”的设为1，“否”的设定2。

![](images/64123aac8921ad4bf75d505621698b81cfadbceecacd966b740401e595f0864d.jpg)  
图3研究区域Fig.3Study area

表2变量离散分级表  
Table2Discretization and classification of variables   

<html><body><table><tr><td colspan="4">变量名称 数值类型</td><td colspan="4">等级代码 Classification code 3 4</td></tr><tr><td colspan="4">Variable names Value type</td><td colspan="4">2</td></tr><tr><td colspan="4">坡度Gradient/° 连续变量</td><td colspan="4">0-2 2-5</td></tr><tr><td colspan="4">连续变量</td><td colspan="4"><20</td></tr><tr><td colspan="4">高程 Altitude /m</td><td colspan="4">20-30</td></tr><tr><td colspan="4">地形起伏度 Relief amplitude/ 连续变量</td><td colspan="4">2-5 5-15</td></tr><tr><td colspan="4">距水域距离 Distance to water body /m 连续变量</td><td colspan="4">500—1000 1000—2000</td></tr><tr><td colspan="4">距铁路距离 Distance to railway /m 连续变量</td><td colspan="4">5000—15000 15000—30000</td></tr><tr><td colspan="4">距公路距离 Distance to road /m 连续变量</td><td colspan="4"></td></tr><tr><td colspan="4">距镇中心距离 Distance to township /m 连续变量</td><td colspan="4">1000—2000 2000—4000</td></tr><tr><td colspan="4">连续变量</td><td colspan="4">2000—4000 4000—6000</td></tr><tr><td colspan="4">距生态公益林距离 Distance to ecological forest /m 离散变量</td><td colspan="4">500—1000 1000—2000</td></tr><tr><td colspan="4">水源涵养重要程度 Importance of water conservation</td><td colspan="4">比较重要 重要</td></tr><tr><td colspan="4">水土流失严重程度 Soil erosion degree 离散变量</td><td colspan="4">中度侵蚀 强度侵蚀</td></tr><tr><td colspan="4">生态环境敏感性 Eco-environmental sensitivity</td><td colspan="4">中度敏感</td></tr><tr><td colspan="4">离散变量 离散变量</td><td colspan="4">高度敏感</td></tr><tr><td colspan="4">生态服务功能重要性 Importance of ecosystem services 离散变量</td><td colspan="4">中度重要 高度重要</td></tr><tr><td colspan="4">建设占用 Urban encroachment</td><td colspan="4">否</td></tr><tr><td colspan="4">耕地占用Farmland occupancy</td><td colspan="4">否</td></tr><tr><td>生态用地潜力 Ecological land potential</td><td colspan="4">离散变量 离散变量</td><td colspan="4"></td></tr></table></body></html>

# 2.3贝叶斯网络模型训练

在构建网络结构后,将离散化后的样本点数据作为训练数据,采用最大似然法对模型进行参数学习。经过参数学习后的BN 模型可以得到两种土地利用类型的动态变化结果及各因子的概率分布情况（图5）。2004 年至2013 年间,鄂州市有 $3 4 . 5 \%$ 的生态用地转变成其他用地类型,维持稳定的地块仅 $6 5 . 5 \%$ ,生态用地被占用情况较为严重。其中,土地动态变化因子中“耕地占用"情况达到 $4 3 . 6 \%$ ,建设占用为 $1 0 . 2 \%$ 。此外，水土流失程度中度侵蚀以上比例达到 $3 5 \%$ ,土壤侵蚀明显;生态敏感性中等程度以上比重达到 $5 0 \%$ ,区域生态系统受干扰程度高，生态环境问题较为突出;生态服务功能重要性中等程度及以上则是 $8 0 \%$ ，生态系统服务功能贡献价值高。

# 2.4 敏感度分析

以目标变量"生态用地潜力"为分析变量,对BN 模型进行敏感度分析,可以表现出历史变化因子和生态适应性因子对“生态用地潜力"的影响。敏感性分析结果用方差缩减的百分比表示,方差缩减能反映出特定变量对目标变量的影响大小,分析结果如表3所示。

![](images/0184f72a3c9e4a170251f1f898b0538a78e8cbf60be88d04950c494ee41f8a71.jpg)  
图4部分基础数据  
Fig.4Part of the base data

表3敏感度分析结果  
Table 3Sensitivity to target variable   

<html><body><table><tr><td>变量类型 Types of the variable</td><td>变量名称 Variable</td><td>方差缩减/% Variance reduction</td></tr><tr><td>生态用地历史变化因子</td><td>耕地占用</td><td>29.5</td></tr><tr><td> Indices of land change</td><td>建设占用</td><td>0.62</td></tr><tr><td>生态适宜性因子</td><td>生态环境敏感性</td><td>8.55</td></tr><tr><td>Indices of ecological suitability</td><td>生态服务功能重要性</td><td>1.84</td></tr><tr><td></td><td>距水域距离</td><td>0.40</td></tr><tr><td></td><td>水源涵养重要性</td><td>0.26</td></tr><tr><td></td><td>地形起伏度</td><td>0.24</td></tr><tr><td></td><td>高程</td><td>0.24</td></tr><tr><td></td><td>距生态公益林距离</td><td>0.14</td></tr><tr><td></td><td>坡度</td><td>0.07</td></tr><tr><td></td><td>水土流失程度</td><td>0.06</td></tr></table></body></html>

T P粤星景景中料有限 县山26100器酒限 1?星  
L 是否重有用 国 中用用用 1 81.0994y 国  
比重极E 是否中 中高极 海  
13732 感感感轻敏敏无中甄重  
025≥4 国  
H 嫂 W  
品 无是否城5025≥

从表中可以看出,历史变化因子中耕地占用对“生态用地潜力”产生最大影响,方差缩减结果为 $2 9 . 5 \%$ ，表明耕地占用生态用地现象十分严重；建设占用方差缩减结果为 $0 . 6 2 \%$ ,这是因为生态用地的分布更多是远离建成区。在生态适宜性因子中,生态敏感性和生态服务功能重要性的方差缩减结果分别为 $8 . 5 5 \%$ 和 $1 . 8 4 \%$ ，两个变量对区域的生态安全格局意义重大，基于生态敏感性评价和生态服务功能评价的生态红线划定十分重要。距水域距离和水源涵养重要性的敏感度分析结果分别为 $0 . 4 \%$ 和 $0 . 2 6 \%$ ,水域作为生态用地的重要组成部分对生态可持续发展具有重要影响。相比之下,水土流失程度与坡度的分析结果较低,分别占 $0 . 0 6 \%$ 和$0 . 0 7 \%$ ,体现出土壤条件和地形条件并不是阻碍鄂州市生态保护的主要原因。 ？

# 2.5 诊断性分析

选取影响力较大的因子,进行诊断性分析。利用贝叶斯网络反向推理,获取影响因子与目标变量之间的定量因果关系。将“生态用地潜力"值设定为1,观察影响因子概率表的变化情况,结果如表4所示。

表4诊断性分析结果  
Table 4 Diagnostic to target variable   

<html><body><table><tr><td>变量名称 Variable</td><td>变量状态 States</td><td>概率变化/% Probability</td><td>变量名称 Variable</td><td>概率变化/% Probability</td></tr><tr><td>生态服务功能重要性</td><td>一般重要</td><td>-0.5</td><td>水源涵养重要程度 一般重要</td><td>-3.0</td></tr><tr><td rowspan="3">Importance of ecosystem services</td><td>中度重要</td><td>-7.3</td><td>Importance of water conservation 比较重要</td><td>+0.0</td></tr><tr><td>高度重要</td><td>+1.8</td><td>重要</td><td>+0.3</td></tr><tr><td>极重要</td><td>+6.0</td><td>极重要</td><td>+2.7</td></tr><tr><td>生态环境敏感性</td><td>无或轻度</td><td>+0.5</td><td>水土流失程度 无或轻微 Soil erosion degree</td><td>+2.2</td></tr><tr><td rowspan="3">Eco-environmental sensitivity</td><td>中度敏感</td><td>+14.7</td><td>中度侵蚀</td><td>-0.5</td></tr><tr><td>高度敏感</td><td>-13.4</td><td>强度侵蚀</td><td>-1.0</td></tr><tr><td>极度敏感</td><td>-1.8</td><td>重度侵蚀</td><td>-0.7</td></tr><tr><td>距生态公益林距离</td><td><0.5km</td><td>-2.1</td><td><0.5km</td><td>-3.7</td></tr><tr><td rowspan="3">Distance to ecological forest</td><td>0.5—1km</td><td>+0.5</td><td>Distance to water body 0.5—1km</td><td>+0.5</td></tr><tr><td>1—2km</td><td>+0.1</td><td>1—2km</td><td>+1.5</td></tr><tr><td>≥2km</td><td>+1.5</td><td>≥2km</td><td>+1.8</td></tr></table></body></html>

可以看出,在已知“生态用地潜力"取值为“是”,即假定地块划入生态红线区时，“生态服务功能重要性"因子“极重要”的概率升高 $6 \%$ ；“水源涵养重要程度”因子“极重要”的条件概率上升 $2 . 7 \%$ 。这表明在生态红线区内,受保护的绿地生态系统和水域生态系统因子的生态服务价值贡献程度明显提升。“生态环境敏感性”的“高度敏感”和“极度敏感”因子概率分别下降 $- 1 3 . 4 \%$ 和 $- 1 . 8 \%$ ,其概率分布向中低敏感度集聚。这验证了生态红线区内土地自然条件的改善,同时作为保护区受到人为干扰因素的影响也大幅度降低。“距生态公益林距离”和“距水域距离”因子“ $\geqslant 5 0 0 \mathrm { m } ^ { \prime }$ '的概率分别上升 $2 . 1 \%$ 和 $3 . 7 \%$ 。这体现了红线区内的林地和水域得到很好的保护,稳定性得到提升。“水土流失程度”中“无或轻微”的概率上升 $2 . 2 \%$ ,在已知地块划入生态红线区后，水土流失程度得到很好的改善。

# 2.6划定结果及其分析

以 2013 年为基期,利用鄂州市 2013年土地利用现状数据,对鄂州市生态红线做具体的划定。通过空间叠加得到各图斑12种适宜性条件评价因子属性值,作为已知观察数据代入构架好的贝叶斯网络模型中,通过正向推理得到目标变量“生态用地潜力”的后验概率,将其作为各生态用地图斑划入生态红线的依据。将后验概率由大到小排序,选取生态用地图斑划入生态红线范围,直到总面积与鄂州市规划生态红线面积一致（号 $( 4 1 6 6 9 \mathrm { h m } ^ { 2 }$ )。最终得到生态红线区域如下图6所示。

为了验证模型划定生态红线的精度,本文使用相同的数据(不考虑生态用地历史变化),基于传统的生态适宜性评价法,划定了鄂州市生态红线区,如图7所示。随后,本文对两种方法进行了对比。对比结果显示，两种方法之间存在多个地块的冲突区，主要的冲突区放大图如图8所示。

![](images/02cb81f7dd2cbe0fe9c1b27f169c41837a9317162b2781030cf03c82196d755d.jpg)  
图6生态红线保护区划定结果图

![](images/7616254ded6bd4e9ade79d0ef728b7811c32d3e65ac841e31074fdf8fbaca50b.jpg)  
图7传统生态评价法划定生态红线图

![](images/4b7617335432312f5de4d2780f5148d72ef14b342771491ae1f7b80e26a09510.jpg)  
Fig.6Result of ecological red line protection zoning   
Fig.7（ Result of ecological red line zoning based on traditional method   
图8传统方法与贝叶斯网络方法划定生态红线对比图及其冲突区域放大图Fig.8Magnification of theconflict areas of zoned and traditional method ecological red line area图中A一G表示主要冲突区位置;图右侧放大区域中黄色为耕地，蓝色为滩涂湿地

采用贝叶斯网络模型划定的生态红线没有划入E、F、G区域。E零星分布在涂家恼镇和太和镇周边;F位于沙窝乡和泽林镇之间,是鄂州市规划优先发展区;G分布在碧石渡镇交通干线两侧。单纯考虑传统生态适宜性条件划定的红线缺少空间紧凑性以及与其他规划的衔接，划定的结果没有现实指导性和针对性。相比之下,模拟结果主要新增了 $_ { \textrm { A } , \textrm { B } , \textrm { C } , \textrm { D } 4 }$ 个区域。因为在多个地块生态功能同等重要的情况下，本文的划定方法还考虑到地块的稳定性,保证生态红线有效的落地实施。A为鄂州市北部段店镇长江流域沿岸,附近有长江华容泥矶饮用水源地;D为杨叶镇长江流域滩涂湿地。这两个地块不仅分布集中,而且生态服务价值大,对维护周边水域生态系统和绿地生态系统的良性循环十分重要,应当划入生态红线区。B为严家湖和武四湖边缘滩涂坑塘区,具有较大的资源潜力、生产功能以及调节功能,生态利用价值高、稳定性强,因此划入生态红线区。C为沙窝乡西南方生态林地分布区,基于传统的生态评价法划定的红线部分划入了此区域,而基于贝叶斯网络的方法完整画出生态红线分布范围。 Am

由此可以看出,相比于传统的生态红线划定方法,基于贝叶斯网络模型的生态红线划定方法能够综合地考虑生态适宜性条件和生态用地演变等因素,在满足地块生态功能同等重要的前提下,将生态用地中潜力和稳定性较大的部分划入红线，从而使划定结果更加科学合理。 ，（

# 3结论与讨论

生态红线划定对于协调生态保护、城市建设和基本农田保护三者关系具有重要意义。本文在综合分析生态用地历史变化过程和生态适宜性条件的基础上,提出了基于贝叶斯网络的城市生态红线划定方法。与传统的生态评价方法相比,模型划定的生态红线能够更好的维护城市生态系统良性循环,规避人为占用造成的生态用地频繁调整,保证生态红线的稳定性和持续性,呈现生态建设、城市建设和经济建设协调发展的良好格局。

贝叶斯网络模型能够有效地应用于生态红线划定过程中,弥补现有划定方法的不足,具体表现在以下两个方面：(1)贝叶斯网络模型具有整合先验知识和现有证据的能力。能够将生态用地的现状观察数据和动态变化数据结合,学习土地变化规律,模拟出真实的土地发展动态,有利于划定结果的客观有效性。（2)贝叶斯网络模型具有因果推理的能力。能够获取变量间定性和定量关系,分析各变量对目标变量的影响方向和强度。通过前向和后向推理,得到目标变量的概率值,作为划分生态红线的科学依据。

目前我国尚未形成完善的城市生态红线划定方法体系,本文的研究可以为生态红线划定提供新的模型方法。同时,研究也存在不足之处。生态红线划定是一个多层次的决策过程,如何将多层次模拟融入贝叶斯网络模型进行生态红线划定还需要深人研究。此外,本次研究没有考虑空间异质性对生态红线划定的影响。城市生态红线是在明确不同区域资源环境承载能力和发展潜力的基础上进行划定的,在生态红线的划定过程中利用贝叶斯网络模型结合主体功能区理念,加入分区思想实现城市生态红线划定是下一步研究重点。

# 参考文献（References）:

［1］环境保护部.生态保护红线划定技术指南.北京;环境保护部,2015.姚佳,王敏，黄宇驰,白杨,黄沈发.我国生态保护红线三维制度体系—以宁德市为例.生态学报,2015,35（20):6848-6856.  
[3 傅伯杰,周国逸,白永飞,宋长春,刘纪远,张惠远，吕一河,郑华,谢高地.中国主要陆地生态系统服务功能与生态安全.地球科学进展，2009,24(6)：571-576.SunDQ,ZangJ,gJZouLatialalisofa'svioeaualit99Jualofoaa,2013,23(4) :695-709.  
[5]HoekstraAY,Wiedmann TO.Humanity'sunsustainableenvironmental fotprint.Science,2014,344(6188）:4-117.  
［6］中共中央国务院.国务院关于加强环境保护重点工作的意见.北京;中共中央国务院,2011.  
[7] 高吉喜.国家生态保护红线体系建设构想.环境保护,2014,42(2)：17-21.  
［8］林勇,樊景凤,温泉,刘述锡,李滨勇.生态红线划分的理论和技术.生态学报,2016,36(5):1244-1252.  
[9］高吉喜.划定生态保护红线,推进长江经济带大保护.环境保护,2016,44(15）：21-24.  
[10]丁雨晖,冯长春,王利伟.山地区域土地生态红线划定方法与实证研究——以重庆市涪陵区义和镇为例.地理科学进展,2016,35（7)：851-859.  
[11］凡非得,罗俊,王克林,陈洪松,张伟.桂西北喀斯特地区生态系统服务功能重要性评价与空间分析.生态学杂志,2011,30(4)：804-809.  
[12］符娜.土地利用规划的生态红线区的划分方法研究——以云南省为例.北京;北京师范大学,2008.  
[13]刘雪华,程迁,刘琳,彭羽,武鹏峰,石翠玉,朱洪辉.区域产业布局的生态红线区划定方法研究——以环渤海地区重点产业发展生态评价为例.中国环境科学学会 2010学术年会论文集.上海：中国环境科学学会，2010:711-716.  
[14］蒋大林,曹晓峰,匡鸿海,蔡满堂,黄艺,尹春燕.生态保护红线及其划定关键问题浅析.资源科学,2015,37(9):1755-1764.  
[15］李洁,曹红英,梁涛,王凌青,王静.基于城市生态系统研究范式构建生态功能红线理论方法及其应用.生态学杂志,2016,35（4)：1097-1107.  
[16］许妍,梁斌,鲍晨光,兰冬东,于春艳,马明辉.渤海生态红线划定的指标体系与技术方法研究.海洋通报,2013,32（4):361-367  
[17］曾江宁,陈全震,黄伟,杜萍,杨辉.中国海洋生态保护制度的转型发展——从海洋保护区走向海洋生态红线区.生态学报,2016,36(1)：1-10.  
[18] 黄伟,曾江宁,陈全震,杜萍,汤雁滨,杨辉.海洋生态红线区划——以海南省为例.生态学报,2016,36(1):268-276.  
[19] 马世发,马梅,蔡玉梅,念沛豪.省级尺度国土空间生态保护红线划定——以湖南省为例.热带地理,2015,35(1)：43-50.  
[20] 陈明辉,欧金沛,刘小平.基于离散粒子群算法的城市生态控制线划定方法研究.中国科技论文在线精品论文,2012,5(6):559-570.  
[21] 李德毅,刘常昱,杜鹤,韩旭.不确定性人工智能.软件学报,2004,15(11)：1583-1594.  
[22] 关小东,何建华.基于贝叶斯网络的基本农田划定方法．自然资源学报,2016,31(6):1061-1072.  
[23]FrayerSunZL,lrDuneDK,XuJAalyngthediversoftreplantinginuanChinitayesianetokndUsePolicy,2014,36:248-258.  
24]AliferisataroualoalpbbiliteoaiteaoeProcedingsof teInteatioalConfereceonathematicsndEngineingechquesinMedicinendiologicalSiencesLasVegas，V,United States:METMBS,2003：371-376.  
[25]SprtesorR.usatioreac，dditRodalys2001,6669:25-32.  
[26]SunZLMlAfreorkforodelingtsosssigetbdodelsaeseliefetodndynamics models. Environmental Modelling and Software,2013,45:15-28.  
[27]PEARL J. Causality:Models,Reasoning and Inference.2nd ed. Cambridge:Cambridge University Press,2009.  
[28]CoperGHrskovitsE.yesiaethodtuctioofprobbitcetoksfrotaaceLang99,9（4)347.  
[29]KnaapGsonACeEetsofegioalLandUseotrolrg：AoreticadEmpricalReviRevifRegiuie，1988,18.  
[30]HeckenDGeigerDChiceringDLeangByesianetwoks:TeCobatioofKnoledgedStatiticalDataaceLeag，1995,20(3):197-243.  
[31]PolncooKbHartaeesatidEaatioofsnokfoUaskAssessment.Environmental Modeling and Software,2007,22(8）:1140-1152.7