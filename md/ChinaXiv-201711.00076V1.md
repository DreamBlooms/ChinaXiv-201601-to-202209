# DOI:10.5846/stxb201608031598

金成伟，赵玉国，李徐生，支俊俊，张甘霖.祁连山中段高寒草甸草毡表层发育程度的空间分异及环境影响因子.生态学报,2017,37（20)：6732-6742.  
JinCW,Zaoalpine meadows in the middle of Qilian Mountains.Acta Ecologica Sinica,2017,37(2O):6732-6742.

# 祁连山中段高寒草甸草毡表层发育程度的空间分异及环境影响因子

金成伟1,²，赵玉国²\*，李徐生¹，支俊俊²，张甘霖

1南京大学地理与海洋科学学院，南京210023  
2中国科学院南京土壤研究所土壤与农业可持续发展国家重点实验室，南京210008

摘要：高寒草甸植被下的草毡表层能够发挥水土保持、水源涵养等生态环境效益,是高寒草甸植被生态功能发挥的核心,认识草毡表层发育程度的空间分异及环境影响因子有利于深入理解高寒草甸在高原生态系统中的作用。本研究以祁连山中段高寒草甸分布区为研究区,依据根系体积并结合草毡层厚度以及土壤容重,将草毡表层划分为弱发育、中等发育以及强发育草毡。分析了不同发育程度草毡的地形、植被、气候等环境特征，并采用支持向量机模型对其分布进行了空间制图。结果表明：祁连山中段发育程度较高的草毡表层趋向于分布在水分条件较好的低海拔、缓坡,低坡位以及北向坡的位置,以嵩草属植物为主,中等以上发育程度的草毡地表植被及水分条件都较好;发育程度较高的草毡表层年均温较高,各发育程度草毡表层降水量差异不显著。空间分布结果整体与现有的高寒草甸植被类型分布具有高度的一致性,但空间分辨率更为详细,并且实现了不同发育程度草毡表层的空间细分。

关键词：高寒草甸；草毡表层；祁连山中段；空间制图

# Spatial distribution and environmental factors affecting mattic epipedon at different developmental levels in alpine meadows in the middle of Qilian Mountains

JIN Chengwei1,²， ZHAO Yuguo2\*,LI Xusheng1， ZHI Junjun²， ZHANG Ganlin² 1School of Geographic and Oceanographic Sciences，Nanjing University，Nanjing 210o23，China 2StateKyLbooryofldstableicultustituteofiliecesedeofecesjn

Abstract:Matic epipedon，which has important ecological benefits such as water retentionand soil conservation，plays a pivotalrole in theecologicalfunctionof alpine meadows.Therefore,exploringtherelationshipsbetweenthe matic epipedon and environmentalfactors，aswellasspatialdistributionofthematicepipedonatdifferentdevelopmental levelsare essential to elucidating theroleof alpine meadows in the plateau ecosystem.Inthis study，samplesof maticepipedo were collected inalpine meadows inthemiddleofQilian Mountainsandwereclasifiedinto threedevelopmentallevels primarily basedonrot volume，folowed by thickness and bulk density.Therelationships between matic epipedonand environmental factors，such as topography，vegetation，and climate，were analyzed.The support vector machine model was used to map the spatialdistributionofthe matic epipedon.Theresults showedthat areas with relativelylow elevation，gentleslope,low slopeposition，andanorth-facingaspect，which were highlyrelated to high soilmoisturecontent，hadahigheroccurrence probabilityof maticepipedonathighdevelopmentallevels.Vegetationcoveringthemattcepipedonathigherlevelswas usually welldevelopedandcomposed primarilybyKobresiaandotherhygrophilousplants.Awell-developedmatticepipedon existed were there was significantly higher mean annual temperature，whereas there were no significant diferences nmean anual precipitationregarding theexistenceof maticepipedon at diferent developmental levels.The distributionof the matic epipedon was highlyconsistent with thedistributionareaof alpinemeadows，althoughatahigherspatialresolution. Furthermore，this study presented the spatial distribution of mattic epipedon at diffrent developmental levels. >

Key Words: alpine meadow；matic epipedon； the middle of Qilian Mountains；spatial mapping

草毡表层是高寒草甸植被下具有高量有机碳有机土壤物质、活根与死根根系交织缠结的草毡状表层[1-3],草毡表层能够有效截留降水,发挥水土保持以及水源涵养等生态环境效益[46],是高寒草甸植被生态功能的核心,在我国主要分布在青藏高原的东部和北部,在高原生态系统中具有极其重要的地位。

鉴于草毡表层在高原生态系统中的重要作用,很多学者针对高寒草甸草毡表层的发育机理[7、退化过程及其对生态环境的影响展开了研究[8-10],然而多数研究将草毡表层的概念等同于高寒草甸植被类型[1-3],现有植被分类体系多是针对高寒草甸地表覆盖度进行区分,未见有关地下草毡表层特征差异的划分。地形、植被以及局部水热环境条件的差异,会导致高寒草甸草毡表层的发育程度不同,使根系体积和厚度等理化属性存在显著差异。然而,目前的研究缺乏针对草毡表层不同发育程度的划分规则,其空间分布规律也不清晰。对草毡表层不同发育程度差异的辨识将有助于我们对草毡表层发育机理的进一步认知,也有益于提高对区域生态环境质量及其演变模拟的精度。

对于草毡表层这一特定生境下土壤与地表植物综合作用下的发生对象,中国土壤系统分类将其定义为草毡表层诊断层[1],用以草毡寒冻雏形土的定量识别,草毡表层的空间分布预测可以借鉴数字土壤制图的思路[1416],即建立草毡表层与环境要素之间的知识模型,预测模拟不同发育程度草毡表层的分布。由于土壤与环境关系复杂、多呈非线性,随机森林[17-18]以及人工神经网络[19-20]等模型常用于模型的构建,其中支持向量机模型（Support vector machine,SVM)由于在分类以及函数拟合方面优异的表现[2I-2],在土壤有机碳和土壤光谱[23-24]等方面得到了很好的应用。

本研究以祁连山中段高寒草甸草毡表层为研究对象,基于物理特征对草毡表层发育程度进行划分,尝试阐明不同发育程度草毡表层的地形 植被以及气候等环境因子的差异及其相对影响,并运用支持向量机模型对不同发育程度草毡表层的空间分布状况进行预测。本研究可为进一步研究青藏高原草毡表层的分布及其在高原生态环境中的作用提供数据支撑与理论依据。

# 1材料与方法

# 1.1、研究区概况

研究区位于青藏高原东北部边缘的祁连山中段（图1）,地理位置在 $9 8 ^ { \circ } 3 4 ^ { \prime } 2 2 ^ { \prime \prime } - 1 0 1 ^ { \circ } 9 ^ { \prime } 2 4 ^ { \prime \prime } \mathrm { E }$ ， $3 7 ^ { \circ } 4 3 ^ { \prime } 1 3 ^ { \prime \prime }$ 一$3 9 ^ { \circ } 5 ^ { \prime } 1 9 ^ { \prime \prime } \mathrm { N }$ ,总面积约 $1 { \times } 1 0 ^ { 4 } \mathrm { k m } ^ { 2 }$ 。海拔高度在 $1 7 0 0 \mathrm { m }$ 至 $5 1 0 0 \mathrm { m }$ 之间。本区属大陆性高寒山区气候,冬季漫长、寒冷而干旱,夏季短暂、温和而湿润,年均降水量从西北向东南呈现增加趋势,平均年降水 $3 2 7 \mathrm { m m }$ ,主要集中在5月至9月。区域植被以高寒草甸为主,集中分布在区域中东部[25]。

# 1.2样品采集与分析

为使采样点能够表征区域不同的海拔、植被以及气候特征,需要将样点布设于典型区域,运用模糊 $ { \mathbf { \phi } } _ { \mathrm { ~ c ~ } }$ 均值聚类对地形、气候、母质、生物等环境因子进行聚类,得到以环境隶属度表示的环境因子组合分布图,隶属度的高低体现了区域生态环境的典型性,将隶属度高于0.8的区域视为生态环境因子组合的典型区域,结合道路可达度以及采样便利性,最终样点布设于环境因子组合的中心位置，这就是基于典型点的目的性采样方法[2]。分别于2012年及2013年7月至8月在该区域用该方法采集了54个典型剖面（图1）,其中符合中国系统分类中草毡表层定义的草毡类型剖面31个,非草毡类型剖面23个。在每一典型剖面,取表层土样和环刀样,调查地表植被状况,测定草毡表层厚度,并根据专家知识经验判别根系体积。

![](images/147ef554d26c63686e6e5679acb43f7513224552ff80c3ac522a30e538ea10de.jpg)  
图1研究区位置以及主要环境因素分布图  
Fig.1Location of study area and spatial distribution of main enviroment factors

所有样品经室内自然风干后,过筛研磨备测。土壤容重主要采用环刀法测定,其中18个样点由于无法采样,致使数据缺失,鉴于土壤有机质与容重普遍存在的高度相关性[27],采用有机碳含量进行指数回归模型拟合获得,拟合方程( $b d = 1 . 4 5 \mathrm { e } ^ { - 0 . 0 1 \mathrm { s o c } }$ ， $b d$ 为容重( $\ \mathrm { \ g / c m } ^ { 3 }$ ）,soc为有机碳 $( \mathbf { \underline { { g } } } / \mathrm { k g } )$ ，其中 $1 . 0 3 \ \mathrm { g } / \mathrm { k g } < \sec < 1 5 4 . 8 7 \ \mathrm { g } /$ $\mathbf { k g } ^ { \mathbf { \sigma } } ,$ ，拟合精度 $R ^ { 2 }$ 达到0.82,其中土壤有机碳测定采用重铬酸钾-硫酸消化容量法。

# 1.3 发育程度划分

草毡表层在中国土壤系统分类中的定义包括草毡层厚度、根系体积以及土壤容重3个主要物理指标,要

求草毡层厚度大于 $5 \mathrm { c m }$ ,根系体积大于 $5 0 \%$ ,并且容重在0.5- $- 1 . 1 \mathrm { g / c m } ^ { 3 [ 1 ] }$ 。本研究主要依据草毡根系体积,并结合草毡层厚度、容重对各样点草毡表层发育程度进行划分(表1),共划分为弱发育、中等发育以及强发育3 种发育程度（图2）。

表1不同发育程度草毡的主要划分依据  
Table1Main basis of classifing the developmental levels of mattic epipedon   

<html><body><table><tr><td rowspan="2">发育程度 Developmental levels</td><td rowspan="2">样点数 Samples</td><td rowspan="2">根系体积/% Root volume</td><td colspan="2">草毡层厚度 Mattic depth/cm</td><td colspan="2">容重 Bulk density/(g/cm³)</td></tr><tr><td>范围Range</td><td>均值Mean</td><td>范围Range</td><td>均值Mean</td></tr><tr><td>弱发育Weakly developed</td><td>11</td><td><65</td><td><10</td><td>7.8</td><td>>0.7</td><td>0.84</td></tr><tr><td>中等发育 Moderately developed</td><td>11</td><td>65-75</td><td>7-13</td><td>11.8</td><td>0.6-0.9</td><td>0.73</td></tr><tr><td>强发育 Strongly developed</td><td>9</td><td>>75</td><td>>10</td><td>13.3</td><td><0.8</td><td>0.64</td></tr></table></body></html>

![](images/0c694a4f66f588ae4966696f52c53bfec3bb2fe63012ee87af102f0132db3a65.jpg)  
图2不同发育程度草毡表层典型剖面及景观(a1&a2弱发育,b1&b2中等发育,c1&c2强发育)

Fig.2Typicalprofileandlandscapeofmaticepipedonatdierentdevelopmentallevels（al&aweaklydeveloped，bl&bmoderately developed,c1&c2 strongly developed)

# 1.4 环境因子分析

地形、植被以及气候等生态环境要素的差异造成了祁连山中段草毡表层发育程度的差异。针对地形、植被、气候3个方面,所选择的环境因子包括;海拔、坡度、坡位、坡向、NDVI指数、年均气温以及年均降水量。

地形数据基于ASTERGDEM第二版的 $3 0 \mathrm { m }$ 空间分辨率的数字高程模型;NDVI数据采用MODIS 植被指数产品中的 MOD13Q1,空间分辨率为 $2 5 0 \mathrm { m }$ ,时间范围为2012年至2013年7月；气候数据采用 $1 \mathrm { k m }$ 分辨率的近30年平均气温和平均降水量分布图,气候数据由全国673个气象站点插值获得。所有环境因子重采样到250m 空间分辨率。

本研究对三种发育程度草毡表层的上述环境因子数据运用箱线图、圆盘图等图表进行统计分析,同时对环境因子进行因子分析。

以上地形数据的处理采用 Arcgis10.1,植被遥感数据处理采用 ENVI5.1,统计分析采用 SPSS 19.0软件,图表绘图软件采用Origin 9.1。

# 1.5 空间分布预测

由于地形、气候等生态环境要素与草毡的发育联系紧密,运用支持向量机(SVM)可以对具有不同环境要素的样点类型进行判别,建立生态环境要素与草毡发育类型的生态学模型,从而预测不同发育程度草毡的空间分布。

http ://www.ecologica.cn

# 1.5.1 模型基本原理

SVM的基本原理是确定一个分类超平面，将线性可分的两类样点进行分离，样点与超平面的距离（几何间隔)表示分类预测的准确程度，当所有样本点到超平面的几何间隔达到最大，这个超平面即最优超平面[21-22]。当两类样点线性不可分时,则选择合适的内积核函数，将两类线性不可分的点集映射到高维空间（Hibert空间），从而使样本空间的非线性分类问题能在特征空间中应用线性方法解决，同样确定最优超平面将样点分离，使得最小几何间隔达到最大，落在间隔边界上的样点即支持向量(图3）。

# 1.5.2模型构建与预测

本研究具体采用SVM的流程如下：首先基于区域54个样点，建立环境要素与样点是否为草毡的分类生态模型，对区域草毡分布状况进行判别，得到草毡表层分布概率图，然后选择草毡分布概率高于0.5的区域作为草毡分布区,基于31个草毡表层样点,选用相同环境变量,建立环境要素与各发育程度类型草毡的分类模型,对草毡分布区内草毡表层发育程度进行判别,得到草毡表层发育程度空间分布图。

![](images/2eda757922cb89ef7d6bfad8aa1d45975b1aff4e6daceaa9a2d7ea8464509a93.jpg)  
图3最优超平面示意图 $( x _ { 1 , x _ { 2 } ^ { \mathscr { X } } , x _ { 3 } }$ 支持向量， $\mathbf { \nabla } _ { L }$ 最优超平面， $\mathbf { \Omega } _ { a }$ 几何间隔)Fig.3Diagram of optimal hyperplane $\left. x _ { 1 } \right. \left. \mathrm { , } x _ { 2 } \right. \left. \langle x _ { 3 } \right.$ Support vector,LOptimal hyperplane,a Geometric interval)

模型最终采用的生态环境变量包括地形(海拔、坡度）植被(NDVI)以及气候(年均降水、年均温）。模型基本参数中,核函数采用径向基函数,gamma值为0.1,约束违反成本cost为1。模型的运行基于R3.2.5 软件，软件包为e1071。 A

# 1.5.3 模型评价验证

模型评价方面,由于缺乏可以独立验证的样点，而交叉验证是模型泛化能力评价的常用验证方法[28-29],本研究模型评价采用留一验证以及十折交叉验证,其中留一交叉验证是取 $\mathbf { \Omega } _ { n }$ 个样本中 $n { - } 1$ 份用于建模,剩下1份用于验证,重复 $n$ 次；十折交叉验证是将 $n$ 个样本分成10份，其中9份用于建模，1份用于验证，重复10次。

# 1.5.4评价环境因子重要性

由于 SVM模型不能直接进行环境因子重要性评价,而模型的精度与环境因子的选择关系密切,通过改变模型预测的环境因子,比较全部环境因子与部分环境因子参与的模型精度结果差异,可以评价环境因子的相对重要性[30]。本研究主要对草毡发育程度分类模型的环境因子重要性进行评价,通过比较全部环境因子、单独某一环境因子以及移除某一环境因子3种情形下,草毡发育程度分类模型的10次十折交叉验证精度的平均值大小，从而评价不同环境因子的重要性。

# 2结果

# 2.1环境因子分析

”本研究对不同发育程度草毡表层的地形、植被以及气候等环境因子的差异进行了分析。

# 2.1.1 地形

不同发育程度草毡表层分布的海拔、坡度、坡位及坡向分析如图所示(图4),不同发育程度草毡表层的地形特征具有明显差异。草毡表层分布在海拔 $3 0 0 0 { \mathrm { - } } 4 0 0 0 { \mathrm { m } }$ 之间，随着发育程度增高，海拔高度逐渐降低，强发育、中等发育以及弱发育草毡分别集中分布在 $3 0 0 0 { \mathrm { - } } 3 3 0 0 { \mathrm { m } } { \mathrm { , } } 3 2 0 0 { \mathrm { - } } 3 6 0 0 { \mathrm { m } }$ 以及 $3 5 0 0 \mathrm { m }$ 以上的部位,弱发育草毡与其他类型草毡海拔差异显著( $\scriptstyle P < 0 . 0 5 )$ 。随着草毡发育程度的增高，坡度逐渐降低,弱发育以及强发育草毡分别主要分布在坡度大于 $2 5 ^ { \circ }$ 以及小于 $1 6 ^ { \circ }$ 的区域，中等发育草毡分布的坡度较为适中。随着草毡发育程度的增高,坡位逐渐降低,弱发育草毡主要分布在坡上,中等发育的草毡主要分布在中坡,强发育草毡主要分布在坡下;草毡表层主要分布在北向坡,且草毡发育程度越高,坡向越朝北。

![](images/6c49f7cf515c10444f39f2f713f0817b2039f1a6ba16e0f8eeadeb7a43f9afec.jpg)  
图4不同发育程度草毡表层地形特征分布(a:海拔b：坡度c:坡位d：坡向)  
Fig.4Topograpicalfeaturesdistrbutionofmaticepipedonatdiferentdevelopmentallevels（a：levationbslope：sloeositiond aspect)

# 2.1.2 植被

不同发育程度草毡表层的NDVI和地表植物类型图如图所示（图5）,草毡发育程度越高,植被覆盖越高，NDVI值也越高。草毡发育由弱到强,植被NDVI指数均值分别为0.72、0.85及0.85,弱发育草毡与其他类型草毡的 NDVI差异显著( $\scriptstyle ( P < 0 . 0 5 )$ 。从植物类型来看,各发育程度草毡表层优势植物都是嵩草属（KobresiaWilld)植物,弱发育草毡表层优势种包括耐低温,耐干旱的委陵菜属（Potentilla）和芨芨草（Achnatherum）等植物,部分样点甚至出现狼毒（Stellera）等有毒物种，中等及以上发育程度草毡表层多伴生例如蓼属（Polygonum）植物等喜湿植物。

# 2.1.3气候

不同发育程度草毡表层气候特征分析如图所示(图6),草毡表层发育程度越高,环境年均气温越高,但都低于 $0 ^ { \circ } \mathrm { C }$ 。弱发育、中等发育以及强发育草毡的年均温均值分别为 $- 3 . 0 ^ { \circ } \mathrm { C } _ { \mathrm { ~ } \cdot } - 1 . 3 ^ { \circ } \mathrm { C }$ 以及 $- 1 . 1 \mathrm { { ^ { \circ } C } }$ ,强发育草毡年均温差异较小且更为集中。草毡表层发育由弱到强,年均降水均值分别为 $3 5 4 , 3 5 7 \mathrm { { m m } }$ 以及 $3 1 4 \mathrm { m m }$ ,各发育程度草毡表层降水量差异不显著( $0 . 0 5 { < } P { < } 0 . 1 )$ ,弱发育和中等发育草毡表层的年均降水范围较广泛,分别是301— $4 2 9 \mathrm { m m }$ ,297— $4 5 4 \mathrm { m m }$ ,而强发育草毡集中在 $3 2 0 \mathrm { m m }$ 左右。

# 2.1.4 因子分析

通过比较地形、植被以及气候等环境因子的相关性(表2),可见海拔与年均温的相关性最为显著( $r =$ 0.93, $P { < } 0 . 0 1$ )，而海拔与年均降水也有显著的正相关性( $r = 0 . 4 8$ ， $P { < } 0 . 0 1$ )。NDVI指数与海拔呈显著负相关,而与年均温呈显著正相关( $r = 0 . 6 1$ ， $P { < } 0 . 0 1$ ),坡度以及坡向与其他环境因子没有显著相关性。

![](images/f52dacfc28bfc6f0bf23aeda8efffecc4933ad2cd2f5ec82f392c2cf20d11ad6.jpg)  
Fig.5NDVI and plant types of mattic epipedonat different developmental levels

![](images/5ebbfc65713d69d87d1d95189ce5b2acf1e583f62cdbba7190d9aab5d002ad28.jpg)  
图5不同发育程度草毡NDVI及植物类型  
图6不同发育程度草毡表层年均温以及年均降水分布  
Fig.6Mean annual temperature and mean annual precipitation of matic epipedon at different developmental lev

表2环境因子相关性  

<html><body><table><tr><td colspan="6">Table 2 Pearson correlations between environmental factors</td></tr><tr><td>归一化植被指数</td><td>海拔</td><td>坡度</td><td>坡向</td><td>年均降水</td><td>年均温</td></tr><tr><td>NDVI</td><td>Elevation</td><td>Slope</td><td>Aspect</td><td>MAP</td><td>MAT</td></tr><tr><td>归一化植被指数NDVI V1</td><td>-0.66 **</td><td>-0.17</td><td>-0.19</td><td>-0.30</td><td>0.61 **</td></tr><tr><td>海拔Elevation</td><td>1</td><td>0.18</td><td>0.02</td><td>0.48 **</td><td>-0.93 **</td></tr><tr><td>坡度 Slope</td><td></td><td>1</td><td>0.16</td><td>-0.03</td><td>-0.08</td></tr><tr><td>坡向 Aspect</td><td></td><td></td><td>1</td><td>0.12</td><td>0.06</td></tr><tr><td>年均降水MAP</td><td></td><td></td><td></td><td>1</td><td>-0.30</td></tr><tr><td>年均温MAT</td><td></td><td></td><td></td><td></td><td>1</td></tr></table></body></html>

\*\* ${ P { < } 0 . 0 1 }$ ；MAP：Mean annual precipitation；MAT：Mean annual temperature

对地形、植被以及气候等环境因子进行 KMO(Kaiser-Meyer-Olkin)检验,KMO 值为0.547,大于0.5适合做因子分析。通过因子分析,根据特征值大于1提取了两个主成分（表3）,第一主成分贡献率为 $45 \%$ ,累计贡献率为 $6 5 \%$ 。根据因子载荷矩阵,第一主成分主要由海拔、年均温、NDVI以及年均降水组成,可以归纳为大环境因子,其中海拔以及年均温因子载荷较大,年均降水载荷较小,第二主成分主要由坡向和坡度组成,可以归纳为局部地形因子。

表3旋转因子载荷矩阵   
Table 3 Rotated factor load matrix   

<html><body><table><tr><td></td><td>归一化植被 指数NDVI</td><td>海拔 Elevation</td><td>坡度 Slope</td><td>坡向 Aspect</td><td>年均降水 MAP</td><td>年均温 MAT</td></tr><tr><td>第一主成分First principal component</td><td>0.771</td><td>-0.964</td><td>-0.104</td><td>0.07</td><td>-0.562</td><td>0.920</td></tr><tr><td>第二主成分 Second principal component</td><td>-0.275</td><td>0.044</td><td>0.688</td><td>0.809</td><td>0.044</td><td>0.084</td></tr></table></body></html>

MAP：Mean annual precipitation；MAT：Mean annual temperature

# 2.2空间分布预测结果

# 2.2.1 草毡表层空间分布概率图

运用支持向量机模型对研究区草毡表层的分布进行预测的结果如图所示（图7）。草毡分布概率大于0.5的区域占总面积的 $6 3 . 9 \%$ ,草毡表层分布概率较大的区域呈西北东南走向,可分为西北和东南两个部分，西北部草毡表层主要分布在山坡以及坡麓、河谷两侧地带,东南部草毡表层集中连片地分布在高原面上。草毡分布概率较高的区域与该区域7月至9月的TM影像图中植被信息丰富的区域以及高寒草甸植被类型分布区具有高度一致性。

![](images/3728b59c37ef8341edf6f09847eadcd8945ac7d9dce57240a8d6bce907e8aab8.jpg)  
图7草毡表层分布概率图及LandsatTM影像（RGB：波段543组合）

Fig.7Occurring probability of mattic epipedon and Landsat TM image（RGB:combination of band543)

模型预测精度方面，总体精度达到 $8 3 . 3 \%$ ,留一交叉验证精度达到 $8 1 . 5 \%$ ,10次十折交叉验证的平均值达到 $7 8 . 5 \%$ ,模型精度可以接受。

# 2.2.2 草毡表层发育程度的空间分布

不同发育程度草毡的空间分布如图所示（图8）。从分布面积来看，弱发育草毡分布面积较大，占草毡面积的 $57 \%$ ,中等发育草毡和强发育草毡分别占草毡面积的 $3 6 \%$ 和 $7 \%$ 。从西北向东南，草毡发育程度逐渐增高,其中弱发育草毡主要分布在西北部，中等发育草毡主要分布在中北部山麓以及东南部地区，强发育草毡主要沿中部河谷山麓呈西北东南向带状分布。

模型预测总体精度达到 $8 7 . 1 \%$ ,留一交叉验证精度  
达到 $8 0 . 6 \%$ ,10 次十折交叉验证平均精度达到 $7 9 . 0 \%$ 。  
从采样点分布来看，31个草毡样点以及23个非草毡样  
点中分别有21个和16个准确分布在相应预测类型中。模型的精度基本能够达到要求,预测结果可接受。

![](images/a265e6845257c1693452da198e09c74b8072ebfd89b37810e5a3f1283a80699e.jpg)  
图8不同发育程度草毡表层空间分布  
Fig. 8 Spatial distribution of mattic epipedon at different developmental levels

# 3讨论

# 3.1草毡表层发育程度的影响因子

在较为干旱的祁连山地区,水分是影响植物生长的最为重要的环境因子。随着海拔高度的降低,地势趋于平缓,较低的坡度和坡位有利于土壤中水分的汇集与保持,对于高寒草甸的根系生长有积极的意义,因而有利于草毡的发育。而海拔与年均温呈显著负相关,在直观表现上,随着海拔的降低,年均温升高,较高的温度有利于植物的光合作用和根系的生长,草毡发育程度更高,但是草毡表层在海拔 $3 0 0 0 \mathrm { { m } }$ 左右存在分布下限，这与Miehe等人的研究成果一致[31],可能原因是低于 $3 0 0 0 \mathrm { { m } }$ 的区域,气候偏暖干,更高的温度提高土壤中微生物的活性,增大根系的分解作用,不利于草毡的发育。而海拔与年均降水呈显著正相关,所以海拔 $3 0 0 0 \mathrm { m }$ 以上总体为冷湿的气候环境，有利于草毡的发育。

草毡表层的植被特征表明，草毡发育越好，植被覆盖也越高，且多伴生喜湿植物，而NDVI与海拔呈显著负相关，所以在草毡表层分布区，NDVI较高的区域通常与海拔较低、水分充足的区域是一致的，而研究表明海拔和植被是影响高寒草甸土壤水分的主要因子[32]所以海拔以及NDVI所体现的良好水分状况可能是草毡表层发育的关键。

从因子分析的结果以及模型精度所体现的环境因子重要性来看（图9），海拔以及NDVI作为大环境因子对草毡表层的发育程度起关键作用，而年均温和年均降水与海拔关系密切，可能存在信息的重叠，其中年均降水因子无论是因子载荷还是因子重要性都相对较低，总体来看海拔较低的位置，植被覆盖高，水分充足，偏冷湿的气候和土壤环境利于草毡表层的发育，而坡度、坡向等地形因子也体现了水分条件对草毡表层发育的重要作用。

![](images/d762191bf1c428e23d65cf11c402258b091f73103a1061133cd2a84eae0a0bcd.jpg)  
图910次十折交叉验证平均精度  
Fig.9 Mean accuracy of10-fold cross-validation running 10 times

黑色，全部变量参与的模型;深灰色，无该变量参与的模型;浅灰色，只有该变量参与的模型

# 3.2草毡表层发育程度的空间分异

从草毡表层整体分布来看，海拔高于 $4 0 0 0 \mathrm { m }$ 以及低于 $3 0 0 0 \mathrm { { m } }$ 的位置都少有草毡发育，而其与NDVI较高的区域以及高寒草甸植被分布区高度一致性共同体现了海拔以及植被环境因子的重要作用。从发育程度来看,一方面草毡发育较好的区域既是高寒草甸植被覆盖较高的区域,又是海拔和坡位较低的坡麓、河谷两侧以及坡向朝北的区域,这表明良好的植被覆盖以及水分条件有利于草毡表层的发育,而从西北到东南,草毡表层发育程度逐渐增高,与年均降水的趋势一致,而因子分析中并没有足够体现年均降水与草毡表层发育的良好相关性,这可能是由于采样布设的局限性导致,这也是今后亟待解决的问题。另外强发育草毡并没有集中在年均降水和年均温更高的东南部,而是出现在海拔较高、蒸散发较弱,水分条件更好的中部河谷山麓沿线,这也体现出优越的水分条件是草毡表层发育的关键。总体来看由地形及植被所体现的水分条件在空间上的分布不均造成了草毡表层发育程度的空间分异。

# 4结论

(1)海拔较低、坡度较缓、坡位较低以及坡向朝北的地形部位具有优越的水分条件以及较高的植被覆盖，这些因素可能是影响草毡表层发育程度的关键。

(2)本文构建的预测不同发育程度草毡表层空间分布的支持向量机模型是有效的,弱发育草毡表层分布

面积较大,集中在较干燥的西北部,中等发育草毡主要分布在相对湿润的北部山麓以及东南部地区,强发育草毡集中沿中部河谷山麓呈带状分布。

(3)本文采用以根系体积为主,草毡表层厚度以及土壤容重为辅的方法有效地对草毡表层发育程度进行了划分,实现了对高寒草甸植被类型内部差异性的区分,对探究高寒草甸在高原生态系统中发挥的作用具有参考意义。

致谢：黑河流域 2010年TM影像由黑河计划数据中心提供,杨琳老师,杨帆、杨飞以及杨仁敏博士对本研究野外工作给予帮助,特此致谢。

# 参考文献（References）：

[1］中国科学院南京土壤研究所土壤系统分类课题组，中国土壤系统分类课题研究协作组.中国土壤系统分类检索(第三版).合肥：中国科学技术大学出版社，2001.  
[2]KaiserK,MieheGarthelesA,EanO,charfA，Schult,chltzFdamczykS,renzelBTuf-bearigtopsoilotralTibetan Plateau,China:pedology，botany，geochronology.Catena，2008,73（3）：300-311.  
[3]YangR,ZhangGL,YangF,ZiJJ,YangF,LiuF,ZhaoYG,LiDC.PreciseestimationofsoilrganicCarbonstocksioreastTibetan Plateau. Scientific reports，2016,6：21842.  
［4］林丽，曹广民,李以康，张法伟，郭小伟，韩道瑞.人类活动对青藏高原高寒矮嵩草草甸碳过程的影响.生态学报，2010,30（15）：4012-4018.  
[5]YangF,ZhangGL，YangJL,LiDC,ZhaoYG,LiuF,YangRM,YangF.Organicmatercontrolofsoil waterretentioninanalpinegrassland and its significance for hydrological processes.Journal of Hydrology ，2014，519:3086-3093.  
[6］李婧，杜岩功，张法伟，郭小伟，韩道瑞，刘淑丽，曹广民.草毡表层演化对高寒草甸水源涵养功能的影响.草地学报，2012，20（5)：836-841.  
[7］岳广阳，赵林，王志伟，邹德富，张乐乐，乔永平，赵拥华，牛丽.多年冻土区高寒草甸根系分布与活动层温度变化特征的关系.冰川冻土，2015,37(5)：1381-1387.  
[8］杜岩功，梁东营，曹广民，王启兰，王长庭.放牧强度对嵩草草甸草毡表层及草地营养和水分利用的影响.草地学报，2008，17（3)：146-150.  
[9］曹广民，杜岩功，梁东营，王启兰，王长庭.高寒嵩草草甸的被动与主动退化分异特征及其发生机理.山地学报,207,25(6)：641-648.  
[10]梁东营，林丽，李以康，王溪，曹广民.三江源退化高寒草甸草毡表层剥蚀过程及发生机理的初步研究.草地学报,2010,18(1)：31-36.  
[1]ChangXF,aXY,WngS,ZuXXLoC,ZgZhiesExplorinfeivesapligesigforoitornglonin degraded Tibetan grasslands. Journal of environmental management， 2016,173:121-126.  
[12]WangGX，WangYB,LiYS，hngHY.IfuencesofalpineecossteesponsestoliaticchangeonsolpropertisoteQingtPlateau,China.Catena，2007,70(3）：506-514.  
[13]ZengC，ZangF，WangQhYY,JoswakRIpactflieeadoegdatioosoilhdralicpropertisvthQaplateau. Journal of Hydrology，2013，478(2）：148-156.  
[14]McBratney A B,Mendonca Santos ML, Minasny B.On digital soil mapping.Geoderma,2003,117(1/2）: 3-52.  
[15] HenglT,HeuelikGe.ricokfoatialpicflblesdogese(1/2) : 75-93.  
[16] 朱阿兴，李宝林，杨琳，裴韬，秦承志，张甘霖，蔡强国，周成虎.基于GIS、模糊逻辑和专家知识的土壤制图及其在中国应用前景.土壤学报，2005，42(5)：844-851.  
[17] GrimmR,BhesrkersebrHSlancarbocoentratiosdocsoBlodosadgialolaingusinRandom Forests analysis.Geoderma，2008，146(1/2）：102-113.  
18]Wistagebialagfeselisteppe ecosystem.Plant and Soil,2011,340(1/2）: 7-24.  
[19]AgyarearkSkrtflaletotiuratedrlicdcivitdoeZJal（：423-431.  
[20]ZhaoZYngenoG,owingZ,esHW,MengFRUingrtifaleuraletwokodelstoprodcelcbncontent distribution maps across landscapes. Canadian Journal of Soil Science,2O1O,9O(1）：75-87.

http://www.ecologica.cn

[21] Meyer D,Leisch F,Hornik K.The support vector machine under test.Neurocomputing,2003,55(1/2）：169-186.  
22]BallbSpatipdctoofpropetierateoutaingortcesod/）：338-350.  
23]Somara,gslcoteouthWalessralilocalGeoderma Regional,2016,7(1）：38-48.  
[24]Aldana-JagueE,HeckrathG,Macdonald.vanWesemaelBas，VanOostK.UAS-basedsoilarbonmapingusingVS-NIR（48O00m）multi-spectral imaging：Potential and limitations.Geoderma，2016,275：55-66.  
[25］杨帆，黄来明，李德成，杨飞，杨仁敏，赵玉国，杨金玲，刘峰，张甘霖.高寒山区地形序列土壤有机碳和无机碳垂直分布特征及其影响因素.土壤学报，2015,52(6)：1226-1236.  
[26]ZhuAX,YangL,LiBLQinC,EnglishE,urtJE,ZouCHposivesaligfordigitalsolapingforreasithliata/HarteminkAE,MBrateyA，Mendoca-SntosMDLds.DigitalSoilMappingWithLimitedData.Ntherlands：Springer，O08：3-245.  
[27] XuL,HeN,uGetodsofaatigllksitypactotatingargealesolanicrbage.Catea4494- 101.  
[28］孙孝林，赵玉国，刘峰，王德彩，梁传平.数字土壤制图及其研究进展.土壤通报，2013,44（3)：752-759.  
[29] BrusDJ,KempeB,HuvelinkGBaplingforvalidationofdigitallapsuroanJalofSlSience，1,62（3）94-40.  
RodrigsliJAigacgrieladetallSoftware，2014，57：192-201.  
[31]MieheG,MieheS,KaiserK,LiuJQ,ZhaoXQ.StatusandDyamicsoftheKobresiapymaeaEcosysteontheTetanPlateauAio：AJournal of the Human Environment，2008,37(4)：272-279.  
[32］王军德，王根绪，陈玲.高寒草甸土壤水分的影响因子及其空间变异研究.冰川冻土，2006,28（3)：428-433.