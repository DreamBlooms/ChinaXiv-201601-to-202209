# DOI: 10.5846/stxb201602020243

宓春荣,郭玉民,Huetman Falk，韩雪松.基于物种分布模型的精确采样提高目标物种发现率——以黑颈鹤（Grusnigricolis）,白头鹤（Grusmonacha)为例.生态学报,2017,37（13）:4476-4482.  
MiCR,GuYueFlkHanXSesrieligtsotfifesekeacdCraneandHddCatssdelsedplingachoudltdceastoiestgditfdaesoeffectively re.cost and effort.Acta Ecologica Sinica,2017,37(13）:4476-4482.

# 基于物种分布模型的精确采样提高目标物种发现率以黑颈鹤（Grusnigricollis）,白头鹤（Grusmonacha）为例

宓春荣',郭玉民1,\*,HuettmannFalk²，韩雪松

1北京林业大学自然保护区学院，北京100083  
2EWHALELab,Departmentofiologyand Wilife,InstituteofArcticiolog，UniversityofAaskaFrbanks（UAF），AK97,UA

摘要：明确野生动植物的地理分布是基础生态学和应用生态学领域的一个基础但关键的步骤,为后续分析提供了重要的信息。而野生动植物分布调查是一项需要投入大量人力,精力和资金的工作,特别是稀有物种的调查。物种分布模型越来越受到广泛引用尤其是在生物保护方面。为了证明物种分布模型在野生生物调查中精确采样方法的可行性,以全球易危物种黑颈鹤和白头鹤的实际繁殖分布预测为例,使用随机森林(Random Forest)算法加以验证。比较发现物种分布模型预测实际调查分布点,随机样方法生成的随机点，系统样方法的规则点在空间相对出现概率具有显著差异( $\scriptstyle P < 0 . 0 0 1 { \mathrm { ~ , ~ } }$ ),实际分布点具有较高的相对出现概率。该结果表明若在物种分布相对出现概率较高区域设置样方能够减少实际调查区域,有效提高发现目标物种的概率,从而减少调查投入。基于物种分布模型的精确采样方法将有效地提高我们对稀有物种分布的了解,有利于野生动植物的保护规划。

关键词：物种分布模型;随机森林;精确采样;黑颈鹤;白头鹤

# Species distribution model sampling contributes to the identification of target species: take Black-necked Crane and Hooded Crane as two cases the modelbased sampling approach could help to reduce areas to be investigated and it can find target species more effectively re. cost and effort

MI Chunrong¹，GUO Yumin1,\* HUETTMANN Falk²， HAN Xuesong1   
1College of Nature Conservation，Beijing Forestry University，Beijing 1Ooo83,China   
2EWHALELabDepartmentofologndWdife,stutefArcticBology，UniversityflasaFirbanks（UA），AK7,U

Abstract:The identificationofthegeographic distributionof wildlifeis fundamental inapplied ecology，since itprovides important information for subsequent analyses.However,theinvestigationof wildlife is often expensiveand time consuming, especiallyforrare speciesand whenusing ineffcient sampling designs.To determine target species more eficiently，we tried to apply model-based sampling using predictions from species distribution models（SDMs).Weused black-necked (Grus nigricolis）and hooded（Grus monacha）cranes as two examples，and used the Random Forest algorithmcombining thebreding locationandenvironmentalinformation tomodelthebreedinggeographicdistributionofthetwocrane species. Weextracted therelative index of ocurrence（RIO）for the breeding locations（testing points，model-basedsampling method），random point locations （random sampling method），and regular point locations （regular sampling method）from the prediction map.Then,we used boxplots and ANOVA toanalyze thesedata；theresults indicated bredinglocations with higher RIOs，andasignificant diference was found between the other two methods.Therefore，the model-based sampling method helpedto reduce the sizeof the investigatedareasand determine targetspecies moreefectively.To conclude，a speciesdistribution model-basedsampling method forfieldwork would help to increaseour knowledgeofrarespecies distributions. More generally，we recommend using this approach to support conservation plans.

KeyWords:species distribution model（SDM）；Random Forest；sampling method；black-necked crane；hooded crane

明确物种的空间分布是许多保护工作如虫害防治,保护区建设的首要工作[1]。野外调查野生物种尤其是稀有物种是一项需要投入大量人力、时间和资金的艰巨任务。使用传统样方法和样线法调查野生物种时由于其数量稀少,大多数样方内并不能找到相应物种,所以样方的设计需要和物种分布情况相适应[2];而对于某一物种分布情况的了解程度常受限于是否有专家可以咨询以及由于专家所处位置的地理限制而造成的知识偏见[3」。因此,有助于在野外快速而有效地发现特定目标物种的方法具有重要的实用价值。

物种分布模型（Species distribution models,SDMs)或生态位模型（Ecological niche models）[4],是将物种的分布信息和对应的环境变量信息依据一定的算法得出物种分布与环境变量之间的关系,并将这种关系应用于所研究的区域,进而对目标物种分布进行估计的模型[5.6]。物种分布模型越来越成为生态学,生物地理学,保护生物学[7],影响评价[8],气候变化研究[9,10]的一个重要研究工具。物种分布模型在生物保护方面的其中一个重要应用是为稀有和濒危物种制作空间分布图,了解这些物种在哪些区域更可能出现[-13]。

黑颈鹤(Grusnigricolls）是世界15 种鹤类中唯一生活在高原的鹤类,被 IUCN 列为全球易危物种（VU）[14]。黑颈鹤是鹤科中科学纪录最晚的一个种,俄国探险家Przhevalsky于1876 年在青海湖取得标本,但自此以后的100 多年来,人们对黑颈鹤的状况几乎是一无所知[15]。近40年来,黑颈鹤的研究取得迅速进展,积累了较丰富的资料。黑颈鹤目前种群数量约11000 只,繁殖地点相对集中于西藏中西部、青海东部,四川北部[16],甘肃南部和北部。同时,有小部分种群分布于不丹和印度[15]。白头鹤（Grus monacha)被 IUCN列为易危物种（VU)[14],目前全球数量为11160只[17]。白头鹤繁殖于俄罗斯西伯利亚东南部以及黑龙江流域；大部分个体越冬于日本南部鹿儿岛地区,另外有少量个体越冬于韩国和我国的长江中下游地区。白头鹤的第一个繁殖巢于1974年在俄罗斯被发现[18],在我国首个白头鹤繁殖巢在 1993 年黑龙江小兴安岭地区的通北发现[19]。 1入7

虽然物种空间预测分布图已被应用于诸多领域,如保护区规划,但是空间预测结果的可信性尚未被野外调查真实数据充分证明。基于此,本文以易危物种黑颈鹤和白头鹤的繁殖空间分布预测为案例,采用随机森林模型算法来评估基于物种分布模型的精确采样方法的有效性和可行性。

# 1材料和方法

# 1.1研究区域

根据现有的黑颈鹤和白头鹤繁殖分布点,将其所在位置作为主体,再向外延伸一定距离作为研究区域,黑颈鹤研究区域为 $7 8 ^ { \circ } 1 3 ^ { \prime } - 1 0 4 ^ { \circ } 5 4 ^ { \prime } \mathrm { E } , 2 5 ^ { \circ } 4 0 ^ { \prime } - 4 2 ^ { \circ } 3 1 ^ { \prime } \mathrm { N }$ ；白头鹤研究区域为 $1 2 0 ^ { \circ } 2 0 ^ { \prime }$ 一 $1 4 5 ^ { \circ } 5 5 ^ { \prime } \mathrm { E }$ $4 3 ^ { \circ } 1 8 ^ { \prime }$ 一 ${ \cdot } 5 6 ^ { \circ } 1 7 ^ { \prime }$ N(图1)。

# 1.2 物种数据

在2002—2014年间,通过收集文献资料和当地居民提供的黑颈鹤信息，借助高倍望远镜辅以实地地毯式调查。记录观察点经纬度,黑颈鹤距观察点的角度和距离,然后确定黑颈鹤出现位置经纬度信息，共收集到黑颈鹤繁殖点58个,在本研究中作为黑颈鹤模型的训练点;调查范围包括甘肃、青海和四川三省,基本涵盖已知的黑颈鹤所有繁殖分布区。2014年在西藏南部的定结定日县湿地发现17个黑颈鹤繁殖点，系为首次调查发现[20],将其作为黑颈鹤模型验证点。2002—2014 年期间运用黑颈鹤调查相同方法在中国境内共发现白头鹤繁殖巢33个,本研究中作为白头鹤模型训练点;这些点涵盖已知的国内所有繁殖分布区。2014年利用GPS-GSM卫星跟踪器对白头鹤跟踪。繁殖期间个体移动速度为0的跟踪点大量聚集( $> 2 0 0$ )在一个半径为2—$3 \mathrm { k m }$ 的区域,则将该区域中心经纬度作为繁殖点。以此在俄罗斯境内共发现繁殖点12个,在本研究中作为白头鹤模型的验证点（图1）。

![](images/d2c9c7061279ea5eefc6eaa1e91cccbab495a983f6d988b50f0871d736951752.jpg)  
两种鹤的研究区域位置  
图1黑颈鹤和白头鹤研究区图,其中红点表示建立模型所用的训练点,黑点表示验证模型准确度的验证点Fig.1Thestudyarea of Black-necked Craneand Hooded Crane.Red dots displaythe Trainingsamples used toconstruct speciesdistribution models,black dots display the Test samples used to evaluate model accuracy

# 1.3 环境变量

选取了21个分辨率为30弧秒的环境变量作为模型自变量,包括4个地形地理变量(海拔、坡度、坡向、离海岸线距离),2个水源变量(离河流距离、离湖泊距离),3个人为干扰变量(离公路距离、离铁路距离、离居民点距离),1个土地覆盖因子,11个生物环境气候变量(表1）。

# 1.4模型建立

本研究选择随机森林(Random Forest[21])作为物种分布模型算法。选择随机森林模型是基于其出色的预测能力和被研究人员广泛应用[2-24]。随机森林是一种相对新颖的机器学习方法,属于组合模型（Ensemblemodels）的一种。其基本算法思想是:假设建模人知道单个分类树的构建,随机森林通过自举法（bootstrap）随机选择变量生长成分类“树”,每棵树都会完整生长而不作修剪（pruning)。并且在生成树的时候,每个节点的变量都仅由随机选出的几个变量中产生[25]。一般情况下,随机森林随机地生成几百个至几千个分类树,然后选择重复程度最高的树作为分类和回归的最终结果[26]。随机森林能够得到很高的预测准确性而不产生过拟合现象[21,27],然而这点尚有争议[26,28]。本研究使用 Salford Predictive Modeler（SPM)软件中的Random Forest算法构造模型及分布于预测。SPM软件对随机森林模型进行了内部优化[29]

表1环境变量图层描述  
Table 1 GIS layers for environmental variables   

<html><body><table><tr><td>环境图层 Environmental layer</td><td>描述 Description</td><td>黑颈鹤 (均值±标准差) Black-necked crane （Mean±SD)</td><td>白头鹤 (均值±标准差) Hooded Crane （Mean±SD)</td><td>来源 Source</td><td>网站 Website</td></tr><tr><td>Bio_1</td><td>年平均气温</td><td>49.24 ± 90.55</td><td>-18.21 ± 41.77</td><td>WorldClim</td><td>http://worldclim.org/</td></tr><tr><td>Bio_2</td><td>月平均昼夜较差</td><td>134.9 ± 20.00</td><td>119.00 ± 19.69</td><td>WorldClim</td><td>http://worldclim.org/</td></tr><tr><td>Bio_3</td><td>月平均昼夜较差/温度 年较差</td><td>36.54±5.63</td><td>21.48±2.24</td><td>WorldClim</td><td>http://worldclim.org/</td></tr><tr><td>Bio_4</td><td>温度季节性变异</td><td>8406.00 ± 2433.64</td><td>15108 ± 2033.68</td><td>WorldClim</td><td>http://worldclim.org/</td></tr><tr><td>Bio_5</td><td>年最高气温</td><td>223.20 ± 90.65</td><td>236.30 ± 30.07</td><td>WorldClim</td><td>http ://worldclim.org/</td></tr><tr><td>Bio_6</td><td>年最低气温</td><td>-149.70 ± 103.95</td><td>-304.60 ± 68.34</td><td>WorldClim</td><td>http://worldclim.org/</td></tr><tr><td>Bio_7</td><td>气温年较差</td><td>372.90 ± 79.98</td><td>541.00 ± 68.40</td><td>WorldClim</td><td></td></tr><tr><td>Bio_12</td><td>年降水量</td><td>247.00 ± 610.25</td><td>618.90 ± 147.04</td><td>WorldClim</td><td>http://worldclim.org/</td></tr><tr><td>Bio_13</td><td>最湿润季节降水量</td><td>113.30 ± 144.01</td><td>135.80 ± 21.99</td><td>WorldClim</td><td>http://worldclim.org/</td></tr><tr><td>Bio_14</td><td>最干燥季节降水量</td><td>2.65 ± 3.98</td><td>9.29 ± 9.32</td><td>WorldClim</td><td>http://worldclim.org/</td></tr><tr><td>Bio_15</td><td>降水季节性变异</td><td>98.37 ± 16.99</td><td>85.05 ± 21.01</td><td>WorldClim</td><td>http://worldclim.org/</td></tr><tr><td>Altitude</td><td>海拔</td><td>2908.00 ± 1762.89</td><td>465.90 ± 335.87</td><td>WorldClim</td><td>http://worldclim.org/</td></tr><tr><td>Aspect</td><td>坡向</td><td>174.45 ±107.32</td><td>175.60 ± 103.93</td><td>来自海拔图层</td><td></td></tr><tr><td>Slope</td><td>坡度</td><td>4.39 ± 5.43</td><td>2.33 ± 2.42</td><td>来自海拔图层</td><td></td></tr><tr><td>Landcover</td><td>土地覆盖</td><td></td><td></td><td>ESA 公路图层来自</td><td>http://www.esa-landcover-cci.org/</td></tr><tr><td>Disroad</td><td>离公路距离</td><td>37.95 ± 41.82</td><td>79.00 ± 113.73</td><td>Natural Earth</td><td>http://www.naturalearthdata.com/</td></tr><tr><td>Disrard</td><td>离铁路距离</td><td>260371 ± 219608.5</td><td>104.72 ± 139.21</td><td>铁路图层来自 Natural Earth</td><td>http://www.naturalearthdata.com/</td></tr><tr><td>Disriver</td><td>离河流距离</td><td>122.76 ± 136.76</td><td>91.10 ± 69.33</td><td>河流图层来自 Natural Earth</td><td>http://www.naturalearthdata.com/</td></tr><tr><td>Dislake</td><td>离湖泊距离</td><td>328.57 ± 239.73</td><td>344.41 ± 209.21</td><td>湖泊图层来自 Natural Earth</td><td>http://www.naturalearthdata.com/</td></tr><tr><td>Discoastline</td><td>离海岸线距离</td><td>1515.49 ± 549.06</td><td>664.38 ± 459.82</td><td>Coastline layer from Natural Earth</td><td>http://www.naturalearthdata.com/</td></tr><tr><td>Dissettle</td><td>离居民点距离</td><td>226.04 ± 166.37</td><td>180.20 ± 170.97</td><td>居民点图层来自 Natural Earth</td><td>http://www.naturalearthdata.com/</td></tr></table></body></html>

分别在黑颈鹤和白头鹤的研究区内生成 10000 个“伪不存在（Pseudo-absence）”点。用GeospatialModeling Environment(GME)软件分别为两个物种的分布点和“伪不存在点"提取21个环境变量信息,然后用Salford Predictive Modeler（SPM）软件建立预测模型。模型设置1OO0 棵树,权重为平衡（Balance）,其他设置选择默认[10]。

为了进行空间预测,用GME 软件分别在黑颈鹤和白头鹤研究区域内生成 $5 ~ \mathrm { k m } \times 5 ~ \mathrm { k m }$ 规则格网点（regularpoints）,同时提取经纬度和21个环境变量信息。使用 SPM软件将之前生成的黑颈鹤和白头鹤模型文件预测每个格网点的适宜分布指数,然后在 ArcGIS 10.1中使用反距离加权方法(Inverse Distance Weighted，IDW)插值得到预测图。

# 1.5 模型验证和分析

本研究使用 AUC（area under the curve of receiver operator characteristic（ROC）curves）值[3-31]来评价模型,因为 AUC 值不受阈值的影响,而被广泛的应用于物种分布模型的评价[32-34]。AUC 评价模型的标准[30]是：极好,0.90—1.00;好,0.80—0.90;一般,0.70—0.80;差,0.60—0.70;失败,0.50—0.60。使用 SPM软件分别计算黑颈鹤和白头鹤验证点和在研究区域内生成的100个随机点的相对出现概率,然后利用R软件的

SDMTools包计算AUC值。此外,为了比较基于物种分布模型进行采样设计的方法与传统取样方法的差异，在黑颈鹤和白头鹤的研究区内分别生成 $5 0 ~ \mathrm { k m } { \times } 5 0 ~ \mathrm { k m }$ 的格网点用来模拟系统采样，并比较验证点，100个随机点(模拟随机采样)和规则点的相对出现概率。

# 2结果分析

# 2.1 AUC模型评价结果

黑颈鹤模型的AUC值为0.74,白头鹤模型的AUC 值为0.75。根据 Swets[24]和Allouche等[35]的分级,模型准确度属于一般等级（Fair）。

# 2.2模型准确性空间分析

图2展示了黑颈鹤和白头鹤的预测分布图。从图中可以看到验证点很好地叠加在预测到的适宜分布区范围内。尤其是白头鹤验证点很好的覆盖在狭长的高适宜分布区域内。比较验证点,随机点和规则点所在位置的相对出现概率值（图3）,发现验证点的出现概率要远高于随机点和规则点,方差分析表明具有显著差异（ $\scriptstyle P < 0 . 0 0 1 { \mathrm { ~ , ~ } }$ 。

![](images/81e6421d1acf32d0c96f70e2e69062909e23807584e020aed5f9b0425623fca0.jpg)  
图2黑颈鹤预测图和白头鹤预测图  
Fig.2Prediction maps of two cranes.prediction map of Black-necked Crane and prediction map of Hooded Crane【其中红点表示建立模型所用的训练点，黑点表示验证模型准确度的验证点

# 3讨论和结论

本研究结果表明利用物种分布模型预测到黑颈鹤和白头鹤实际分布点验证点的物种相对出现概率要高于传统的随机采样方法,系统采样方法设计的采样点的出现概率,并具有显著差异( $P { < } 0 . 0 0 1$ ）。说明物种分布模型具有很好的识别物种真实分布的能力。借助于物种分布模型将物种出现概率高的区域作为实际需要调查区域,将大大缩小实际需要调查的区域,进而提高了调查效率[36],从而减少调查投入,为野外调查提供了一个有效而可靠的工具。

以往研究中对物种分布模型或生态位模型的验证往往是从总体样本中选取部分样本用于验证[10,25,37]，而本研究的验证数据与训练数据来源不同,并不是从总体中选取部分，且大都位于训练数据围成的不规则区域外,距离远于训练数据内部距离。与来源于与训练数据同一数据集的部分样本来评价模型的方法相比更为客观,对模型验证更具有说服力,虽然模型准确度系数会相对偏低。

本研究的研究对象为黑颈鹤和白头鹤繁殖分布预测,黑颈鹤和白头鹤分别在高原湿地和森林沼泽区域繁殖,环境差异大。在2002—2014 年间共调查得到75 个黑颈鹤繁殖点和45个白头鹤繁殖点,数据获取困难。所建模型基于的样本数分别为58个和33个,属于小样本模型,但是对实际调查所获得的验证数据仍具有很

![](images/2fd009fa11ea65ff85edbf516e8b5a27093708443cbd1601cad2a73f7602ae8b.jpg)  
图3黑颈鹤和白头鹤随机点，规则点和验证点比较的箱线图

Fig.3Boxplots of Random points and Regular points versus Testing points for Black-necked Cranes and Hooded Cranes好的预测能力。说明利用物种分布模型方法对濒危物种和分布数据难以获取（如偏远区域和难以到达区域，像本研究的两个例子)的物种的调查以及保护规划将起到巨大作用。

本文只选取随机森林算法作为物种分布模型,这是因为在前期工作中发现相较于TreeNet（StochasticGradient Boosting[38]），CART（Classification and Regression Tre[39)），Maxent（Maximum Entropy Models[40]）和4种模型的组合模型，随机森林模型对小样本具有更好的预测能力。不同物种的生活环境不同,异质性不同，不同物种的空间预测基于的基础单元(grid)是否也需不同,以及环境变量不同需要在未来继续研究。本研究的结论有助于物种分布模型方法在实际保护规划和物种调查中尤其是濒危物种的应用。

# 参考文献（References）：

[1]LeLayG,EgerR,FrancE，usanrospeivesaplingaseoodeleblesproesthetecioofarescoay2010,33(6)：1015-1027.  
[2]YoccozNGicholsJoulieroitogofologicaldiversiinsaceadteredsinEolog&Evoluio（8）：446-453.  
[3]MurrayJV,AW,LearRA,lpineCA,saH,CSL.HuefulisexperpiforpredictigthistrofaspecieswitdydtgionofxpertisecasesudusingusailedrcwalsetrogleeiclltJalofdEcology，2009,46(4) :842-851.  
[4］朱耿平，刘强，高玉葆.提高生态位模型转移能力来模拟入侵物种的潜在分布.生物多样性，2014,.22（2)：223-230.  
[5］李国庆，刘长成，刘玉国，杨军，张新时，郭柯.物种分布模型理论研究进展.生态学报，2013,33（16)：4827-4835.  
[6] 许仲林，彭焕华，彭守璋.，物种分布模型的发展及评价方法.生态学报，2015,.35(2)：557-567.  
[7 GuisanA,TingleyR,arterJB,ujokaitis-LewisI,utclff,llchA,gnT,rotosL，MDoal-Maden,ntPringleC,MartiTG,RodesJR,MinR,SeerfeldSA,Eith,ShwartzMW，WintBA,BroeimaO,Autin,r,KearneyMR,PosinghamHBuckleyYM.Predictingspeciesdistributionsforonservationdecisions.EcologyLettrs，2O1，6（1）：1424- 1435.  
[8] HumphriesGRHueF.utingodetdus：apidentofrcticabidoivesiidatesotetialfitsihshipping lanes and human activity.Diversity and Distributions,2014,20(4)：478-490.  
[9]ZhangL,LuSR,Su,WngTComparativeevaluatifultileoelsoftefetsoflatechageotepotetialsrifPinus massoniana.Chinese Journal of Plant Ecology，2011,35(11）：1091-1105.  
[10] MiCR,HueaF,GuoYM.CliateeveloepredictiosdicateanlargedsuitablewinteringdistributionforGreatBustads（tisrddybowskii）in China for the 21st century.PeerJ,2016,4：e1630  
11]GrifS，WalerB,HartMUsingGStdelueforberliesaoiotesteMtaaNestSc,77(1): 54-63.  
[12]AitkenobtDWSulLMelntrbutiosfareplantsinGeatBsinsteNorthmcaWstcaNaturalist,2007,67(1)：26-38.  
[13]EdwardsJr，CuterD，ZimeaNE,eiserLlegiaJModel-asedsratfatiosancgeetectioofeolicalevents.Ecology，2005，86(5）：1081-1090.  
[14]IUCN.IUCN Red List of Threatened Speies Version 2013.2013. htp://www.iucnredlist.org.  
[15] 李来兴.黑颈鹤(Grus nigricollus）种群生态及濒危等级评估.生物多样性，1997,5（2）：84-89.  
[16] HarrisJ,MirandeC.Aglobaloverviewofcranes：status，threatsandconservationpriorities.Chinese Birds，0l3,4（3）：189-209.  
[17]Birdlife International. IUCN Red List for birds.2014. http://www.birdlife.org  
[18] Meine CD,Archibald G W.The Cranes：Status Survey and Conservation Action Plan. Gland,Switzerland:IUCN,1996.  
[19] 李林.我国首次发现白头鹤繁殖地.野生动物，1993，（5)：16-16.  
[20] HanXS,GuoY,WenLJ,iCR.NewackckedCraeGuicolissubpopulatiorecoedioutTbet,inaFl,31: 116-118.  
[21]Breiman L.Random forests.Machine learning，2001,45(1）：5-32.  
[22]ElithJ,raaCHdersR,keSsaA,jsRJ,HueF,LeathJ,eaA,LJG,LoiseleBA,MnoG,MoitzC,Nakamura,aazawY,OvertonJM,PetersnAT,illpsSJichadsonK,Sche-eeiraR,SchapireRE,bJ,Wils，Wisz,iE.ovelmeodiproepredictfspeciesdistibsfrocdata.Ecography，2006,29(2）：129-151.  
[23]MiCR,HueaF,GuoYOtangthstpossblepredictiosfhabiateleiofoteireatstarsiCagu，eiProvince with rapid machine learning analysis.Chinese Science Bulletin，2014,59(32）：4323-4331.  
[24］翟天庆，李欣海.用组合模型综合比较的方法分析气候变化对朱鹦潜在生境的影响.生态学报，2012，32（8)：2361-2370.  
[25］张雷，王琳琳，张旭东，刘世荣，孙鹏森，王同立.随机森林算法基本思想及其在生态学中的应用——以云南松分布模拟为例.生态学报，2014，34(3):650-659.  
[26］李欣海.随机森林模型在分类与回归分析中的应用.应用昆虫学报，2013，50(4)：1190-1197.  
[27]PrasdAL,easifidesotreesdosforicioEcosystems,2006,9(2):181-99.  
[28]ElithJraaCDeddohiOdingeasofoiepefoaesfseesdistboe.Ecography，2009,32（1）: 66-77.  
[29]HeickKA，HuetmanF,idgrenM.Aglobaodelofvianifuenzapredictoninwildids：eiportanceofothgio.Veterinary Research，2013，44：42-42.  
[30]Swets JA. Measuring the accuracy of diagnostic systems. Science，1988,240(4857）: 1285-1293.  
[31]FieldinHellJFArevifetosforeessmentofpreitioesiseatiopreseeabsnceodelsvotalconservation，1997,24(1)：38-49.  
[32]ManelS，ilisHCOeodSJEvauatingpreseceabseceodelsinoedtontfoprevaleceJouaofliedEcology，2001,38(5)：921-931.  
[33]McPsoJetzgerJtsfseiesguacofistroelsolalpeoeitclartefact? Journal of applied ecology，2004,41(5）：811-823.  
[34］黄建，Huettmann F,郭玉民.黑龙江流域白头鹤繁殖栖息地选择模型预测.北京林业大学学报，2015,37（8)：40-47.  
35]AlouhrdReigeacfeeistroelsrevaapdsllit).Journal of Applied Ecology，2006,43(6) :1223-1232.  
[36]GuisanA BroenimannO,EnglerR,VustM,YoccozNG,LehmannA,ZimmermannNE.Usingniche-basedmodelstoimprovethesaplingofrare species.Conservation Biology，2006，20(2）: 501-511.  
[37］王琦，魏宇昆，黄艳波.中国弧隔鼠尾草亚属(唇形科)的分布格局.生态学报，2015，35(5)：1470-1479.  
[38]Friedman JH. Stochastic gradient boosting.Computational Statistics & Data Analysis,2002,38(4):367-378.Breiman L,Friedman J,StoneCJ，Olshen RA.ClasificationandRegresson Trees，NewYork:Chapman and Hall/CRC，1984.  
[40]/PilipJdkhaiR.auochtospestrbtoodeli//rinofhstialConference on Machine Learning. New York：ACM,2004.