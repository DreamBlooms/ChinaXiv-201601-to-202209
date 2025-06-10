# DOI: 10.5846/stxb201705030814

陈妍,宋豫秦,王伟.基于随机森林回归的草场植被盖度反演模型研究——以新疆阿勒泰地区布尔津县为例.生态学报,2018,38（7）：2384-2394.ChenY,SongYWangWGassadvegeatiocoeivesooelasedforesegeio：AcasesudiriotyaXinjiang Uygur Autonomous Region.Acta Ecologica Sinica,2018,38(7）:2384-2394.

# 基于随机森林回归的草场植被盖度反演模型研究以新疆阿勒泰地区布尔津县为例

陈妍¹，宋豫秦1\*,王伟²

1北京大学环境科学与工程学院，北京100871  
2中国环境科学研究院生物多样性研究中心，北京100012

摘要：作为草地资源大国,我国正面临严峻的草场退化形势。掌握草场植被盖度的历史演变趋势,是草场退化驱动力识别及风险评估的基础。目前已有研究多以参数回归方法估算植被盖度,但并未充分考虑其苛刻的使用条件。利用Landsat 系列卫星遥感影像及地面植被盖度监测资料建立非参数回归——随机森林回归模型,并与传统线性回归方法进行比较,在此基础上应用随机森林回归模型估算近10年来布尔津县草场植被盖度的变化趋势,并对结果的不确定性进行分析。结果显示：传统的线性回归方法很难满足其基本的统计学假设条件,而随机森林模型不但无需进行假设条件检验,而且预测的准确性也优于以往普遍应用的线性模型。基于Landsat ETM $^ +$ 标准数据得到的反演结果较之TM和OLI数据普遍偏小，地表反射率数据虽然可以大幅降低传感器不同对反演结果所造成的影响,但结果仍存在约 $\pm 1 0 \%$ 的不确定性。涉及的草场类型众多，为了提高反演精度,后续研究需要分别计算其植被指数,并尽量减低传感器差异带来的不确定性。

关键词：植被盖度；植被指数；随机森林;遥感影像

# Grassland vegetation cover inversion model based on random forest regression: A case study in Burqin County，Altay， Xinjiang Uygur Autonomous Region

CHEN Yan'， SONG Yuqin1,\*， WANG Wei² 1College of Environmental Sciences and Engineering,Peking University,Beijing 1Oo871,China 2Biodiversity Research Center，Chinese Research Academy of Environmental Sciences，Beijing 1Oool2,China

Abstract:As alarge country with extensive grassland resources，China is facing severe grasland degradation.Studying trends ngrassland vegetation cover change provides a basis for identifying the driving forces of grassland degradatio and associated risk assessmentIn previousstudies，parametric regression models have typically been applied to estimate vegetation cover.However,theharshassmptionsof parametricregression havealwaysbeenneglected.Inthecurrnt study, vegetation cover monitoring dataand vegetation indices（NDVI，SAVI，MSAVI，EVI），extracted from Landsatremote sensing images，wereused to build random forest regressions，which are non-parametric models.These modelswere subsequentlycompared with traditional linearregressionmodels.Tobuildandtest these models，2O5samples werecollected from2010 to 2015（data from 2012 were not included）in alpine meadow,mountain meadow,lower-flat meadow,temperate meadow steppe，desert steppe，steppe desert，and desert in Burqin County，Xinjiang Uygur Autonomous Region.Among these samples，15O samples wereused to build models，and theremainder wasused as testingdata.Two setsof Landsat remote sensing images，Level1 Standard Productand Surface Reflectance Product，wereappliedseparately，and both included TMdatafor 2011—2012andOLIdata for 2013—2015.In total,two random forest modelsand23linear models werebuilt.Theresultsindicatedthatthe predictiveabilityof therandomforest models wasclearlystrongerthanthatof most of thelinearmodels.Moreover,itwasnotnecessarytotesttheassumptions fortherandomforest models，whereas noneof thelinear models'asumptions inthisstudycouldbesatisfied perfectly.In thecase study，random forestregresion was applied to etimatethetrend in grassand vegetationcover changein the last decade inthe studyarea based on 663sampling points．Among these，data for 2005—2009 were based on Landsat $\mathrm { E T M ^ { + } }$ ，data for 2010—2011 were based on Landsat TM, and data for 2O13—2015were basedon Landsat OLI.It was clearthat sensor diferences would haveacertain influence on theinversionresults.Therefore，wealsosimultaneouslybuiltarandom forest modelfor MODIS-EVIdata,as this would not be affcted bysensor diferences，and theresultscalculatedusing MODIS data were considered tobe a standard.For Level 1 standard data，the results based on Landsat $\mathrm { E T M } +$ were significantly smaller than the results based on MODIS data. For surfacerflectance data,the influenceof diferent sensorsontheresultscould bemarkedlyreduced.Finally,toquantifythe uncertainty of vegetation cover change trendbasedonsurface reflectance data，weusedarandom forest model to verify vegetation cover extracted from diferent sensors during the same period，and found that the uncertainty was between $- 1 0 \%$ （20 and $1 1 \%$ .In conclusion，random forest regression is assumed tobe a better model to inverse vegetation coverthan linear models.For its aplication in time series studies，Landsat surface reflectance production could significantly reduce the influence of sensor difference，although the uncertainty was still approximately $\pm 1 0 \%$ . In the current study，we assessed many grassand types，and to improve the accuracyof prediction，vegetation indexes shouldbe calculated separately in further tudies.Inaddition，eforts should be made toreducetheuncertaintyasociated with thedata from diferent typesof sensor.

Key Words: vegetation cover；vegetation index； random forest；remote sensing images

我国是草地资源大国,但多年来的超载过牧、荒地过度开垦和滥挖乱采致使草场植被覆盖度大幅下降,水土流失和沙漠化日趋严重,牧区经济发展及草地生态系统的健康因此受到了严重威胁[1]。研究草场变化规律是揭示草场退化驱动力以及风险评估的基础,在缺乏长期监测数据的情况下,借助卫星遥感影像不失为有效的方法。当前可用的遥感数据一般为气象卫星NOAA的1km分辨率AVHRR 数据[2-3],terra 和aqua卫星的$2 5 0 \mathrm { m }$ 分辨率 MODIS 数据[4-5]和陆地卫星Landsat 系列数据。早期研究多采用分辨率较低的AVHRR 数据,MODIS 数据虽具有较高的完整性,但仍难以满足长时间序列研究的需求。Landsat 系列卫星自1975年开始已有7颗卫星相继运行，且其 $3 0 \mathrm { m }$ 的分辨率相较于AVHRR和MODIS 来说优势明显,因而被目前不少研究者所关注。 AN

利用遥感影像研究草场变化趋势大致可分为两种思路,其一是通过监督或非监督分类,分析草场分布或面积的变化[6-8],然而面积增减只能体现宏观变化,难以反映某一具体区域在时间序列上的退化或恢复情况;其二是利用光谱信息计算植被指数,通过植被指数变化直接表征生态系统的变化趋势[9-11],相对而言,这类方法的主要优势是将研究对象精确至像元尺度。然而干旱半干旱地区植被盖度低,植被光谱信息弱,植被指数往往非常小,在这种情况下用其变化情况说明草场生态的改善或恶化往往意义不大。而利用植被指数反演植被盖度不失为一种可行的替代思路。植被盖度计算主要可通过线性光谱混合模型[12-14]和回归模型两种方法实现。前者一般应用于缺乏地面监测数据的情况之下,其核心是获得纯像元下的地物光谱值。但在实际应用中,特别是植被盖度较低的草地生态系统中,典型光谱值很难获得,且计算误差较大[15]。因此,在具备地面监测数据的情况下，一般通过植被指数与植被盖度直接的相关关系建立参数模型,反演植被盖度,其中线性回归模型应用最为广泛[16-17]。然而以往的研究多未充分考虑参数回归苛刻的假设条件,以及多元回归对变量间非共线性的要求，这无疑会降低反演模型的可靠性。解决此问题的途径之一是寻求预测效果达到甚至超越参数模型的非参数方法。作为目前预测效果最好的非参数回归模型之一，随机森林模型与参数回归等方法相比,无需对变量的正态性和独立性等假设条件进行检验,同时也不需要考虑多变量的共线问题[18],且运算高效、结果准确,在环境以及生态学等领域都有着广泛应用[19-22]。在草场研究方面,随机森林虽曾用于植被分类[23],但作为回归模型的应用则几属空白。

数据源是保证反演模型可靠性的前提，长时间序列研究会不可避免地使用到来自不同传感器的光谱信息,而对于Landsat 系列卫星标准数据产品而言,同一时间段内从不同传感器所提取的光谱信息会存在一定差异,需要对非同源数据进行校正以及标准化处理[24-25]。但目前草场方面已有的研究既没有定量分析传感器差异对反演结果造成的影响,也没有计算校正和标准化处理对反演结果的改进效果。 2

鉴此,本文利用Landsat系列卫星TM,ETM $^ +$ 以及OLI的影像和植被盖度地面监测数据建立基于随机森林回归的草场植被盖度反演模型,并将反演结果与线性回归结果进行比对,探讨其优越性。继之将其应用于基于多源数据的草场植被盖度变化趋势分析,并探讨该方法的不确定性,以期为干旱半干旱地区长时间序列的草场变化研究提供方法支持。 SIAy

# 1研究区域

布尔津县位于新疆西北部阿勒泰地区,属阿尔泰山脉西南麓,介于86°25'—886'E,47°22'— $\cdot 4 9 ^ { \circ } 1 1 ^ { \prime } \mathrm { N }$ 之间,总面积 $1 0 3 6 9 \mathrm { k m } ^ { 2 }$ 。境内景观异质性强，北部山区最高蜂海拔 $4 3 7 4 \mathrm { m }$ ,中部为低山丘陵、河谷地带,南部为低平戈壁滩,海拔最低处仅为 $4 3 6 \mathrm { m }$ （图1)。全县生态系统多样,北部山区兼具水源涵养与生物多样性保护的功能,南部荒漠生态系统肩负防风固沙的生态功能。草地资源丰富,各类草地类型均有分布,农业以畜牧为主,放牧方式仍属传统游牧。当前北部林区载畜量快速增加,林牧矛盾突出,南部以荒漠植被为主,生态环境脆弱,生态保护形势更加严峻。丰富而多样的草场分布特征,不仅可使草场植被盖度反演模型为分析当地草场历史变化趋势乃至制定草场保护和畜牧业生产政策奠定基础,同时也可为其他地区的各类草场研究提供一定借鉴。

# 2数据获取与预处理

为了建立基于随机森林回归的草场植被盖度反演模型,本文所用之数据主要包括基于地面调查的草场盖度数据和卫星遥感影像。

植被盖度地面调查数据来源于布尔津县畜牧兽医局草原站提供的2010、2011、2013、2014、2015 年6—9月的草本、半灌木及矮小灌木草原样方调查表。调查样地涵盖全县8个典型草场类型,即低平地草甸、高寒草甸、山地草甸、温性草甸草原、温性草原化荒漠、温性荒漠以及温性荒漠草原。依据典型性原则,样方在能够代表整个样地草原植被、地形及土壤等特征的区域随机布设,监测样地共计 205个,分布及类型如图1所示，每个样地设置3个样方，样方大小为 $\mathrm { 1 m } { \times } 1 \mathrm { m }$ ,监测结果用3个样方的平均值表示。部分监测点位虽然超越了县界,但并未超越本文所用的遥感影像范围,因此本文将此类监测点也纳入分析范围。植被盖度是由目测法测定的样方内植物地上部分垂直投影面积占样方面积的比率,监测频次为每年一次。

遥感数据为下载自美国地质调查局(U.S.Geological Survey）网站（htp://glovis.usgs.gov/）的Landsat 系列卫星遥感影像,整个县域需要两景影像覆盖,行带号分别为144/26、144/27,影像时间及传感器信息如表1所示。

。本文所使用的每一景影像都包含有目前此类研究通用的一级标准数据产品（简称L1数据)以及经过校正和标准化处理的地表反射率数据产品（简称 SR 数据）,用以定量研究传感器差异对反演结果的影响。

本文的研究对象为草场,因此需要对影像进行监督分类,提取出草场范围。首先,利用ENVI5.1软件对2015 年Landsat8 OLI的两景L1影像(144/27、144/27)分别进行剪裁、辐射定标、融合以及FLAASH大气校正等预处理。其次初步将影像定义为林地、草地、荒地、水体、冰雪区五大类型,分别划定训练样本,通过最大似然法进行分类。经过分类后处理,以GoogleEarthPro.的高分辨率影像为基础,划定验证样本,通过混肴矩阵计算分类精度。两景影像（144/27、144/27)的总体分类精度分别为 $9 7 . 7 7 0 5 \%$ 和 $9 8 . 8 7 4 9 \%$ ,Kappa系数分别为0.9692和0.9642。合并草地、荒地两种类型的区域，通过目视解译去除其中的耕地和建设用地区域,得到布尔津县草场分布范围(图2）。

# 3研究方法

# 3.1随机森林模型的建立与验证

# 3.1.1 植被指数选择

归一化植被指数(NDVI)是草场退化研究中使用最为广泛的植被指数[26-28],本文首先选择其作为模型的解释变量之一。由于研究区南部大片区域为植被盖度较低的温性草原化荒漠、温性荒漠以及温性荒漠草原，仅使用NDVI作为解释变量，反演效果可能并不能达到预期,必须考虑土壤背景的影响[29],因此进一步引入可用于修正土壤背景敏感性以及气溶胶散射影响三个植被指数——土壤调节植被指数(SAVI)、修正土壤调节植被指数(MSAVI)、增强植被指数（EVI)。上述植被指数的计算方法如式1一式4所示，其中参数的选取依据了USGS发布的植被指数产品相关指南[30]

$$
\mathrm { N D V I } { = } \frac { \mathrm { N I R - R E D } } { \mathrm { N I R + R E D } }
$$

MSAVI $\mathbf { \Sigma } = \mathbf { \Sigma }$ (2×NIR+1-√(2xNIR+1)²-8×(NIR-RED) ×0.5

# 3.1.2 模型建立

图1中监测点位的植被盖度数据分别来自2010、2011、2013、2014、2015年6—9月，经统计分析，在6—9月期间，植被盖度并无显著区别，因此在对应年份的6-9月中选择云量最少的影像加以利用，即利用2010—2011年8月的TM影像和2013—2015年7月的OLI影像计算相应点位的4个植被指数。

利用R软件在205组数数据（植被盖度及其对应植被指数)中随机抽取150组作为训练数据用于模型建立。

表1遥感影像信息列表  
Table1Information of satellite images   

<html><body><table><tr><td>影像时间 Image dates</td><td>传感器信息 Information of sensors</td></tr><tr><td>2016-08</td><td>Landsat8 OLI Landsat7 ETM+</td></tr><tr><td>2015-07</td><td>Landsat8 OLI Landsat7ETM+</td></tr><tr><td>2014-07</td><td>Landsat8 OLI</td></tr><tr><td>2013-07</td><td>Landsat8 OLI</td></tr><tr><td>2011-08</td><td>Landsat4-5 TM</td></tr><tr><td>2010-08</td><td>Landsat4-5 TM</td></tr><tr><td>2009-08</td><td>Landsat4-5TM Landsat7 ETM+</td></tr><tr><td>2008-08</td><td>Landsat7 ETM+</td></tr><tr><td>2007-08</td><td>Landsat7 ETM+</td></tr><tr><td>2006-07</td><td>Landsat7ETM+</td></tr><tr><td>2005-08</td><td>Landsat7 ETM+</td></tr></table></body></html>

![](images/df80d7a64a9abddfdb25bf99c3abb0c2322421f2cabb1016d8c370ffaa275e0e.jpg)  
Fig.1Elevation and monitoring points'distribution of study area   
图1研究区地形及监测点位分布图

随机森林是由多棵相互没有关联的决策树组成的集成决策树，用 $\{ h ( X , \Theta k )$ ， $k = 1$ ， $\cdots \nmid$ 表示,其中 $X$ 为输入向量, $\{ \boldsymbol { \Theta } k \}$ 为独立同分布随机向量[31]。与经典回顾分析类似,随机森林可以解释多个自变量 $( X _ { 1 } , X _ { 2 } \cdots$ （20$X _ { k }$ )对因变量 $Y$ 的作用。此处将植被盖度的实地监测值作为因变量Y,NDVI、SAVI、MSAVI和EVI作为自变量。随机森林模型的建立通过调用R语言中“randomForests"程序包[32」来实现。该方法首先完成两个随机采样过程，即通过自助法重采样技术有放回的在150组训练数据中重复随机抽取150个训练样本，未被抽取到的数据被称为“袋外”（outofbag)数据。再从NDVI、SAVI、MSAVI和EVI的4个变量中随机选择若干个变量（以 $m _ { { } _ { t r y } }$ 表示)建立决策树,模型中 $m _ { { } _ { t r y } }$ 的省缺值一般为总变量的1/3,本文有4个变量，则 $m _ { { } _ { t r y } }$ 值为1。最后重复 $n$ 次上述过程，生成由 $n$ 棵决策树组成的随机森林， $n$ 值越大预测越好。随着 $\mathbf { \Omega } _ { n }$ 值的增大,袋外数据误差在显著降低后会基本保持稳定。为了节省计算时间， $n$ 值保证袋外数据误差稳定即可，本文 $n$ 值取150。

模型输出所有决策树计算结果的均值，并通过计算“解释方差百分比”来评定模型预测能力。对于各个自变量对因变量的影响程度，用方差增量以及节点纯度增量两个指标来定性表征。前者指将某一变量替换成随机变量后对预测结果造成的影响，若用于替换的随机变量显著改变了方差，则认为原变量重要性很高;后者从同质性增加的角度去表征变量的重要性[33]。随机森林模型的具体算法请参照Biau 等[34]的文章。

![](images/4b55de050e02ffc9c2f0287b197f74f8e06d7bbc95312c70fa4ab9c79f2e45ce.jpg)  
图2草场范围及抽样点分布图  
Fig.2Distribution of grassland and sampling points in study area

为了将随机森林回归方法与传统的线性回归进行比较,本文采用同样的训练数据同时建立了植被盖度与NDVI、SAVI、MSAVI和EVI的一元线性回归及多元线性回归模型。

# 3.1.3 模型验证

利用205 组数据经过随机抽样剩余的55组数据用于模型验证。应用前文建立的随机森林模型和各个线性回归模型分别计算55个点位的植被盖度预测值,并将实测值与预测值相减,根据差值分布情况比较模型的预测能力。此外,通过绘制残差散点图和正态Q-Q图来检验线性回归模型方差齐性以及残差的正态性,并通过Kappa系数来判断变量的共线性。

# 3.2 模型的应用及其不确定性分析

# 3.2.1 模型应用

利用AreMap10软件在研究区域内随机生成1000个相互间隔大于1km 的点位,去除草场范围之外的点位,得到草场抽样点。为了研究模型在基于多源数据的植被盖度反演领域的应用,本研究以2005—2008 年ETM $^ +$ 影像、2009—2011年TM影像、2013—2015年0LI影像为基础,分析 2005—2015年间（除 2012年）,植被盖度的变化趋势。

首先,剔除研究时段内落在云层和云影中的草场抽样点,最终得到的356个点位用于本小节的抽样分析（图2）。其次,分别利用上述影像的L1和 SR 数据计算各个点位的NDVI、SAVI、MSAVI和EVI值,将其输入3.1中建立的随机森林模型,分别得到监测点位基于L1数据和SR 数据的植被盖度值。最后,将每年356 个监测点位的植被盖度预测值求平均,绘制出基于L1数据和 SR 数据的植被盖度变化趋势图。

# 3.2.2 不确定性分析

由于 2005—2015年间遥感影像源自3个不同的传感器,而传感器的差异会给反演结果带来一定影响，因此本研究进一步应用下载自美国地质调查局地球资源观察和科学中心（Earth Resources Observation andScience Center)的MODIS—MOD13Q1V005 数据集建立随机森林模型,反演 2005—2015 年的植被盖度。由于

MODIS 数据不存在传感器差异问题，因此可将基于此数据反演出的植被盖度变化趋势作为参考,将3.2.1中得到的基于L1和SR数据的趋势曲线与之相比较,变化趋势越接近基于MODIS 数据的反演结果,则说明该数据中不同传感器给反演结果造成的误差越小。

前文提到SR数据是L1数据经过校正和标准化处理的地表反射率数据产品，可在一定程度上克服传感器的差异对结果带来的影响。为了定量分析 SR数据对反演结果的改进效果及不确定性,本研究进一步比对同一时期内,基于不同传感器的反演结果之间存在的差异。

研究区范围草场生长期内，同时具有TM和ETM $^ +$ 影像的时段是2009年8月，同时具有ETM $\cdot +$ 和OLI影像的时段是2015年7月和2016年8月。在草场抽样点中去除09、15、16年3年内云层、云影中的点位以及$\mathrm { E T M } +$ 数据中坏条带中的点位后,剩余663个点位用于不确定分析。利用随机森林模型分别计算同一时段基于不同传感器的反演结果并相减,分别绘制基于L1数据和SR数据的TM—ETM $^ +$ 、OLI—ETM+的盖度反演结果差异概率密度图。 C/5

# 4结果与讨论

# 4.1拟合结果

随机森林模型的计算结果显示,基于L1数据和 SR 数据而建立的随机森林回归模型输出的解释方差百分比分别为 $6 9 . 8 2 \%$ 和 $7 2 . 4 2 \%$ ,因此后者的预测效果优于前者;重要性方面,各个植被指数并未表现出明显的差别(表2)。 2

表2随机森林回归模型变量重要性  
Table 2The variables'importance in random forest models   

<html><body><table><tr><td rowspan="2">变量 Variables</td><td colspan="2">-级标准数据产品 Levell standard data product</td><td colspan="2">地表反射率数据产品 Surface reflectance data products</td></tr><tr><td>方差增量 Increase in mean</td><td>节点纯度增量 Increase in node</td><td>方差增量 Increase in mean</td><td>节点纯度增量 Increase in node</td></tr><tr><td>NDVI</td><td>squared error 12.927</td><td>35899.58 purity</td><td>squared error 9.119</td><td>purity 27067.63</td></tr><tr><td>SAVI</td><td>10.777</td><td>31475.49</td><td>9.080</td><td>29956.79</td></tr><tr><td>MSAVI</td><td>11.111</td><td>38354.48</td><td>7.008</td><td>23012.77</td></tr><tr><td>EVI</td><td></td><td>1</td><td>7.837</td><td>26277.86</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

由于L1数据未经过标准化处理,TM和OLI数据计算的EVI值不在同一数量级,无法用于模型的建立;NDVI:归一化植被指数,NomalizedDiference VegeationIndex;SAVI土壤调节植被指数,SoilAdjustedVegetationIndex;MSAVI;修正土调节植被指数,ModifedSoilAdustedVegetation Index;EVI:增强植被指数,Enhanced Vegetation Index

本研究一共建立线性回归模型23个,其中 $P$ 值显著的模型及相应参数如表3所示。由表3可知,对于一元线性回归模型来说L1数据和SR数据的 $\textstyle R ^ { 2 }$ 差别不大;对于多元回归来说所有的L1数据都无法得到显著结果；从 $R ^ { 2 }$ 的数值上来看 SR数据的多元回归的效果要明显优于一元回归。

# 4.2模型比较

为了进一步分析上述模型的预测能力,本文将 55个验证点位的监测值和预测值作差,结果的分布情况如图3所示。首先,虽然L1和SR数据的一元回归效果在表3中无法通过 $R ^ { 2 }$ 判断，但通过比较红色和绿色箱线图可明显看出,SR数据实测值和预测值的差异明显小于L1数据;第二,随机森林回归模型的预测能力略优于多元回归模型，且这两者明显优于一元线性回归;第三,所有线性回归的结果较真实值来说普遍偏小,但随机森林的预测偏差相对均衡。

在本文所建立的所有模型中,预测效果最好的是基于L1和SR数据的随机森林模型,以及由变量 SAVI-MSAVI建立的SR数据二元回归模型。

http://www.ecologica.cn

表3线性回归模型结果  
Table3The resultsof linear models   

<html><body><table><tr><td colspan="2" rowspan="2">模型 Models</td><td colspan="3">-级标准数据产品 Level1 standard data product</td><td colspan="3">地表反射率数据产品 Surface reflectance data products</td></tr><tr><td>值Value</td><td>P</td><td>R²</td><td>值Value</td><td>P</td><td>R²</td></tr><tr><td rowspan="2">EVI</td><td>常量Constant</td><td></td><td>一</td><td></td><td>25.13</td><td><0.001</td><td>0.65</td></tr><tr><td>系数Parameter</td><td></td><td></td><td></td><td>0.01</td><td><0.001</td><td></td></tr><tr><td rowspan="2">NDVI</td><td>常量Constant</td><td>32.49</td><td><0.001</td><td>0.68</td><td>20.54</td><td><0.001</td><td>0.73</td></tr><tr><td>系数 Parameter</td><td>124.42</td><td><0.001</td><td></td><td>0.01</td><td><0.001</td><td></td></tr><tr><td rowspan="2">SAVI</td><td>常量Constant</td><td>32.49</td><td><0.001</td><td>0.68</td><td>22.46</td><td><0.001</td><td>0.69</td></tr><tr><td>系数Parameter</td><td>83.07</td><td><0.001</td><td></td><td>0.01</td><td><0.001</td><td></td></tr><tr><td rowspan="2">MSAVI</td><td>常量Constant</td><td>32.1</td><td><0.001</td><td>0.66</td><td>26.55</td><td><0.001</td><td>0.64</td></tr><tr><td>系数Parameter</td><td>85.69</td><td><0.001</td><td></td><td>0.01</td><td><0.001</td><td></td></tr><tr><td rowspan="2">SAVI+MSAVI</td><td>常量Constant</td><td></td><td>不显著</td><td></td><td>9.63</td><td><0.001</td><td>0.77</td></tr><tr><td>系数1Parameterl</td><td></td><td></td><td></td><td>0.08</td><td><0.001</td><td></td></tr><tr><td rowspan="3">SAVI+EVI</td><td>系数2 Parameter2</td><td></td><td></td><td></td><td>-0.06</td><td><0.001</td><td></td></tr><tr><td>常量Constant</td><td></td><td>不显著</td><td></td><td>17.94</td><td><0.001</td><td>0.73</td></tr><tr><td>系数1Parameterl</td><td></td><td></td><td></td><td>0.05</td><td><0.001</td><td></td></tr><tr><td rowspan="4">NDVI+SAVI+EVI</td><td>系数2Parameter2</td><td></td><td></td><td></td><td>-0.04</td><td><0.001</td><td></td></tr><tr><td>常量Constant</td><td></td><td>不显著</td><td></td><td>17.93</td><td><0.001</td><td>0.74</td></tr><tr><td>系数1Parameterl</td><td></td><td></td><td></td><td>0.01</td><td><0.05</td><td></td></tr><tr><td>系数2Parameter2</td><td></td><td></td><td></td><td>0.03 -0.02</td><td><0.05</td><td></td></tr></table></body></html>

由于L1标准化处理,TM和OLI数据计算的EVI值不在同一数量级，无法用于模型的建立

![](images/dafc18ec1c517383153d9c0aac0f3dce7a5c0db789a952a383ef1e9e15e081d2.jpg)  
图3植被盖度的实测值与预测值差异  
Fig.3The difference between monitoring values and predicted value!

NDVIL1:基于L1数据NDVI指数的线性回归模型,LinearmodelbasedonNDVIfromlevel1standard product;SAVIL1:基于L1数据SAVI指数的线性回归模型,Linear modelbasedonSAVIfromlevel1standard product；MSAVIL1:基于L1数据 MSAVI指数的线性回归模型,Linear modelbased on MSAVIfromlevel1standard product;NDVISR:基于SR数据NDVI指数的线性回归模型,Linear modelbasedonNDVIfromsurfacerefletanceproduct;SAVISR:基于SR数据SAVI指数的线性回归模型,LinearmodelbasedonSAVIfromsurfacereflecance product;MSAVISR;基于SR数据MSAVI指数的线性回归模型,Linear modelbasedon MSAVIfromsurface reflectance product;EVISR:基于SR数据EVI指数的线性回归模型,LinearmodelbasedonEVIfromsurface reflectance product;SRSM:基于SR数据 SAVI及MSAVI指数的线性回归模型,Linear modelbasednSAVIandMSAVIfromsurfce eflectance product;SRSE基于SR数据SAVI及EVI指数的线性回归模型,LinearmodelbasedonSAVIandEVIfromsurfacereflectanceproduct;SRNSE:基于SR数据NDVISAVI及EVI指数的线性回归模型,LinearmodelbasedonNDVISAVIandEVIfromsurfaceeflectanceproduct;rfL基于L数据的随机森林回归模型,RandomforestodelbasedonlevelstandardproductS基于SR 数据的随机森林回归模型,Random forest model based on surface reflectance product

图4为 SRSM方差齐性和残差正态性检验结果。理想状态下,残差-拟合值关系图上的点应随机分布,而正态QQ图中的点应分布于虚线之上,但 SRSM模型并不能满足其基本假设条件,特别是残差的正态分布性。不仅如此,本研究所有其他的线性回归模型也都不能很好的满足其基本假设。此外,SRSM的各变量应满足非共线性,即 Kappa值小于100,但经过计算该模型的 Kappa 值高达 5570。从对模型的诊断结果看,SRSM 模型虽然预测效果较好,但应用于植被盖度的反演存在较大的缺陷。 2

![](images/6b0452e0e5c70de079c84e78acd50992e3b7f055be4c45ae7dee691328640a22.jpg)  
Fig.4Hypotheses testing of SRSM model

SRSM;基于SR数据SAVI及 MSAVI指数的线性回归模型,Linear model basedonSAVIand MSAVIfromsurface reflectanceproduct

综上,本文认为随机森林模型相较于线性回归模型来说不但不受诸多假设条件和非共线性要求的制约，并能达到更好的预测效果，因此更适合作为植被盖度的反演模型。

4.32005—2015年草场植被盖度变化趋势及不确定性分析

基于L1、SR以及MODIS 数据分别得到的草场盖度平均值变化趋势如图5所示。除2006年之外，SR和L1数据反演得到的植被盖度变化情况基本保持了一致的变化趋势，但2005一2009年，也即数据源为 $\mathrm { E T M } +$ 的时间段内，基于L1的反演结果要明显小于SR数据的反演结果。SR数据与不存在传感器差异问题的MODIS数据反演所得的植被盖度值相比，差异小于 $5 \%$ ,但L1数据的偏差较大， $\mathrm { E T M } +$ 数据的预测结果普遍偏小，2006年的植被盖度均值甚至偏小超过 $2 0 \%$ 。

为了分析传感器差异给反演结果造成的影响,本文进一步对比了同一时期内源自不同传感器光谱信息反演得到的植被盖度，对比结果如图6所示。该图显示了2009年ETM $^ +$ 数据与TM数据，以及2015—2016年ETM $^ +$ 数据与OLI数据分别反演得到的植被盖度的差异。

![](images/034b64a8ee4d1dfddf63a7fd0b7445986eae109d25fb9c9f613ebc96ab9141fe.jpg)  
图4SRSM模型的假设检验  
图5基于MODIS、SR及L1数据的抽样点盖度平均值 Fig.5Mean vegetation cover of sampling points based on MODIS，SRandL1dataL1：一级标准数据产品Level1 Standard DataProduct;SR：经过校正和标准化处理的地表反射率数据产品 Surface Reflectance Data Products ,

由图6的概率密度曲线可知,同一时段L1数据不同传感器对计算结果差异巨大,特别是 $\mathrm { E T M } +$ 数据的预测结果普遍小于TM数据,上述结果与图5的结论一致。从具体计算的数值来看;对于 SR数据,几乎 $9 0 \%$ 的测试点位上不同传感器对计算结果产生的影响都能落在 $( - 1 0 \% , 1 1 \% )$ 的区间之中；但对于L1数据， $90 \%$ 测试点位的 $\mathrm { E T M } +$ 与OLI的差异落在( $- 3 0 \%$ ， $1 1 \%$ )范围内，而 $\mathrm { E T M } +$ 与 TM的差异更是落在了 $\left( - 4 0 \% , 9 \% \right)$ 之中。由此可见，不同传感器的差异在L1数据上表现的尤为突出，该数据不适于基于多元数据的草场植被盖度变化趋势研究，即便是经过校正以及标准化处理的SR数据，反演结果也存在约 $\pm 1 0 \%$ 的不确定性。

# 4.4讨论

就反演方法而言，以往类似的研究多基于相关分析线性回归以及多项式模型[16-17,35-37],且模型的筛选通常仅仅通过 $P$ 值以及决定系数 $R ^ { 2 }$ 来评判,而不对模型预测结果做进一步验证。从本文的线性回归结果看，L1数据和SR数据的一元线性模型都具有显著性且 $R ^ { 2 }$ 水平相当，在以MSAVI作为解释变量时，L1数据的拟合效果甚至要优于SR数据(表3)。但从图3中可以清楚地看到前者的误差要远远大于后者。可见， $P$ 值以及$R ^ { 2 }$ 并未帮助研究者对比出 SR数据的优越性。更为重要的是，上述模型都属于参数估计类,若不对其基本假设进行验证，就无法保证所得结论的可靠性。本研究显

![](images/909146418602f907ac758e74a38da744b29db24b7e2ed5cce40a912187f4c950.jpg)  
图6同时段不同数据源的预测结果差异  
Fig.6Difference in predicted values based on different dada sources in the same period

SRrfETM_TM:SR数据基于ETM+传感器与TM传感器随机森林反演结果的差异；SRrfETM_OLI：SR数据基于 $\mathbf { \mathrm { E T M } } +$ 传感器与OLI传感器随机森林反演结果的差异；LIrfETM_TM：L1数据基于ETM $^ +$ 传感器与TM传感器随机森林反演结果的差异；L1rfETM_OLI：L1数据基于ETM+传感器与OLI传感器随机森林反演结果的差异

示,所有的线性模型都未能通过方差齐性和残差正态性检验。而遗憾的是,迄今大多数研究都忽略了这种统计学的基本要求。

需要强调的是,除了模型本身之外,数据源也是影响预测效果的重要因素。由图5中基于 MODIS 数据反演得到的变化趋势可知,近10年来草场盖度的平均值总的变化幅度不足 $20 \%$ 左右，而2006 年L1数据反演所得之盖度平均值与MODIS数据计算结果的偏差就已经超过了 $20 \%$ 。该问题在图6中体现得更加突出。这便意味着,传感器差异带来的影响甚至可能超过草场变化本身。虽然本研究所用的SR数据与传统研究常用的L1数据相比,已经在一定程度是减少了这类影响[38],但仍未将其完全消除。因此,在涉及长时间序列草场植被变化以及驱动力的研究中,对这种影响进行量化就显得尤为必要。

本文的局限性主要体现在以下几个方面：首先,使用的实地监测数据为 $\mathrm { 1 m } \times \mathrm { 1 m }$ 样方的测量值,而遥感影像为 $3 0 \mathrm { m } \times 3 0 \mathrm { m }$ 精度,如果监测点周围数 $1 0 \mathrm { m }$ 范围内不能保持均一性,拟合结果会因此受到影响;其次,本研究所涉及的草场种类众多,但植被指数计算涉及的参数均采用了USGS 网站提供产品指南中的推荐值,后续研究中应对不同类型草场分别设定参数,以提高结果的可靠程度;再次,本研究初步估算了2005—2015 年草场盖度的平均值,今后可进一步应用随机森林模型分析草场植被盖度的空间变化特征;最后,本文仅初步研究了传感器差异给反演结果造成的影响,如何通过归一化处理等方法减小这种差异将是未来研究中需要探索的问题。

# 5结论

1）本文通过随机森林回归方法建立了基于 Landsat 系列卫星数据的草场植被盖度反演模型,并应用该模  
型分析了近10年来布尔津县草场盖度的变化趋势。2）通过与线性回归反演模型的对比可知,随机森林回归方法不但能规避线性回归苛刻的假设条件，同时  
可超越绝大多数线性回归模型的预测能力。3）模型不确定性方面,LandsatETM $+$ 的标准数据反演得到的植被盖度较之TM和OLI数据普遍偏小;地  
表反射率数据虽然可以大幅降低Landsat系列不同传感器对反演结果的影响，但反演得到的植被盖度仍存在

$\left( - 1 0 \% , 1 1 \% \right)$ )的不确定性。

致谢：北京大学生命科学学院王昊老师提供MODIS 数据,中国环境科学研究院张玉波博士和付刚在遥感影像处理方面给予帮助,大理大学东喜马拉雅资源与环境研究所任国鹏老师为本研究提出建议,特此致谢。

# 参考文献（References）:

[1］樊江文，钟华平，陈立波，张文彦.我国北方干旱和半干旱区草地退化的若干科学问题.中国草地学报,2007,29(5)：95-101.  
[2］黄敬峰，桑长青.天山北坡中段天然草场牧草产量遥感动态监测模式.干旱区资源与环境，1993,7（2)：53-59.  
[3］李京，陈晋，袁清.应用NOAA/AVHRR 遥感资料对大面积草场进行产草量定量估算的方法研究.自然资源学报，194,9（4)：365-368.  
[4]HmiminaG,DufreneE,PontailerJY,DelpierrN,AubinetM,aquetB,DeGradortA,urbanB,FlechardC,GranierA,os,HeineschB,LongdozB,oureauC,OurcivalJambalS,intAdreL,SoudaniK.Evaatiof hepotetialofSsatelitapredictvegetatiooogindieret：anestigatiousiggoudbasedeasureetseotesingofEviont1132: 145-158.  
[5]GeerelitSPOT VEGETATION data analyses.International Journal of Remote Sensing，2005,26(20）: 4499-4526.  
[6]ChenSaoLndgrdooitogusingulaldsatT/Eatarasieetweegssddopadfnortheast China.International Journal of Remote Sensing，2008,29（7）：2055-2073.  
[7]FengY,olgXetfasddtioatyrviesLand Degradation & Development,2009,20(1）：55-68.  
[8]GerkenR，ZaitchikB，EvansP.ClassfyingrangelandvegeationtyeandcoveragfromNDVtieseriesusingFourierFileredCycleSimilarity. International Journal of Remote Sensing，2005,26(24):5535-5554.  
[9]CaiHgX,udgdstralaatetsand restoration projects.Ecological Engineering，2015,83：112-119.  
[10]WeelscbJefgeldsatheory.Ecological Applications,2007,17(3）：815-827.  
［11］魏小琴.阿勒泰地区NDVI变化及其主要驱动因子分析[D].乌鲁木齐：新疆农业大学，2015.  
[12]Roder A,Udelhoven T,Hill J,Del Barrio G，Tsiourlis G Trend analysis of Landsat-TMand -ETM $^ +$ imagery to monitor grazing impact in arangeland ecosystem in Northern Greece. Remote Sensing of Environment，2008,112(6): 2863-2875.  
[13]LiJY,YangXC,JinYX,YangZHuang WG,ZhaoLN,GaoT,YuHD,MaHL,QinZH,XuB.Monitoingandanalysisofasaddesertification dynamics using Landsat images in Ningxia,China.Remote Sensing of Environment，2O13,138：19-26.  
[14］杨强，王婷婷，陈昊，王运动.基于MODIS EVI数据的锡林郭勒盟植被覆盖度变化特征.农业工程学报，2015,31（22）：191-198.  
[15］吕长春，王忠武，钱少猛.混合像元分解模型综述.遥感信息，2003，（3）：55-58,60-60.  
[16］郭辉，黄粤，李向义，包安明，宋洋，孟凡浩.基于多尺度遥感数据的塔里木河干流地区植被覆盖动态.中国沙漠，2016，36(5)：1472- 1480.  
[17］马中刚，孙华，王广兴，林辉，余宇晨，邹琪.基于Landsat 8-OLI的荒漠化地区植被覆盖度反演模型研究.中南林业科技大学学报，2016,36(9) : 12-18.  
[18] 李欣海，随机森林模型在分类与回归分析中的应用.应用昆虫学报，2013，50(4)：1190-1197.  
[19] Cutler DR，EdardsJr,eardK,rA，HessK,bnJ,wlerJJRandoforestsrasifaoologEo,88(11): 2783-2792.  
20 金宇，周可新，方颖，刘欣.基于随机森林模型预估气候变化对动物物种潜在生境的影响.生态与农村环境学报，2014,30(4)：416-422.21 王盼，陆宝宏，张瀚文，张巍，孙银凤，季妤.基于随机森林模型的需水预测模型及其应用.水资源保护,2014，30（1)：34-37，89-89.22 Rodriguez-Veig，WelerJousVTanseK，Balzer.QuantifingforestomasscarbostocksfrosaceCurentreteports，2017,3(1) : 1-18.  
2]Masitesof Applied Remote Sensing，2012,6(1)：063558.  
[24]ChanderG,MarkhamBL,HelderDL.Summaryofcurentradiometriccalibrationcoefcients forLandsat MSS,TM,ETM $^ +$ ，and EO-1 ALIsensors.Remote Sensing of Environment，2009,113(5）：893-903.  
[25]VogeaE，tAZuerspeivalaottofatsdata.Remote Sensing of Environment，2016,185：258-270.  
[26] PravalieR,Srod,epteatuetectiglateagctsofrstcossinuthesteoansinnsatata.Journal of Geographical Sciences，2014，24(5）：815-832.  
[27]PatisoR,JgesoJCasK，WekerJTredsindundraouityopositioinecticfasaeeen1984 and 2009.Ecosystems，2015，18(4)：707-719.  
[28] 毛志春，宋宇，李蒙蒙.基于 MODIS 反演数据的河套地区荒漠化研究.北京大学学报：自然科学版，2015,51(6)：1102-1110.  
[29] Liu B,YouGY,Li，ShnWS，ueY,LinNFSpetralchacteistisoflpiegrassandandeirhagesespodingtdegradation on the Tibetan Plateau.Environmental Earth Sciences，2015,74(3）：2115-2123.  
30]US.dsatsufacetacdsptrald，s.tpsdsaustfdocuments/si_product_guide.pdf  
[31] Breiman L.Random forests.Machine Learning，2001,45(1）：5-32.  
[32] Liaw A，Wiener M. Classification and regression by randomForest.R News,2002,2(3）：18-22.  
[33] Echevey-alvisetesoJKuloacesRalstokretructureestplacntiKeaeavebd.PLoS One，2014,9(2):e88761.  
[34] Biau G，Scornet E.A random forest guided tour.TEST,2016,25(2)：197-227.  
[35] BrinkmanK,DichoferUhchtE，uerketAQuantfioofabovegodgeadprodctitydtpogicegtiootArabian Peninsula using Landsat imageryand fieldinventory data.Remote Sensingof Environment，2011,115(2):465-474.  
[36] 万红梅，李霞，董道瑞.基于多源遥感数据的荒漠植被覆盖度估测.应用生态学报，2012，23（12）：3331-3337.  
[37] 董建军，牛建明，张庆，康萨如拉，韩芳.基于多源卫星数据的典型草原遥感估产研究.中国草地学报，2013,35(6)：64-69.  
[38] Claverie M,VermoteEF，FranchB，MasekJG.EvaluationoftheLandsat-5TandLandsat-7ET+surfacereflectanceprodctsRemoteSensing of Environment，2015，169：390-403. >