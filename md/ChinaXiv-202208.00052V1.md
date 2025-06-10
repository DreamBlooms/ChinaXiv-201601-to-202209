# MODIS和Landsat时空融合影像在土壤盐渍化监测中的适用性研究以渭干河一库车河三角洲绿洲为例

赵巧珍1.2，丁建丽1.2.3，韩礼敬1,2，金晓叶12，郝建平4(1.新疆大学地理与遥感科学学院,智慧城市与环境建模自治区普通高校重点实验室,新疆 乌鲁木齐830046;2.新疆大学绿洲生态教育部重点实验室，新疆乌鲁木齐830046；3.自然资源部中亚地理信息技术开发应用工程技术创新中心,新疆 乌鲁木齐830046；4.新疆阿克苏地区渭干河流域管理处,新疆 阿克苏842000)

摘要：土壤盐渍化的遥感监测依赖于高时空分辨率影像，但受经费预算、卫星回访周期及天气的影响，高时空分辨率的遥感影像较难获取，这就限制了根据采样时间来获取对应时期遥感影像进行土壤盐渍化监测反演的应用。为此，提出融合MODIS和Landsat影像生成高时空分辨率影像来提取土壤盐渍化信息，为时空影像进行土壤盐渍化监测研究提供数据参考。以渭干河一库车河绿洲为研究区,利用增强型时空自适应融合率反射模型(Enhanced spatial and temporal adaptive reflec-tance fusion model,ESTARFM)和灵活的时空融合模型(Flexible spatiotemporal data fusion,FSDAF）,对MODIS和Landsat影像进行时空融合，并基于融合影像数据构建了关于土壤电导率(EC)的随机森林(RF)预测模型,对比分析时空融合影像应用于土壤盐渍化遥感监测的适用性。结果表明：ES-TARFM融合影像的特征波段反射率与Landsat验证影像对应波段反射率一致性决定系数 $R ^ { 2 } ( { \mathrm { R e d } } ) =$ $0 . 8 0 6 6 \mathrm { \ : } , R ^ { 2 } \mathrm { ( S W I R 2 ) } = 0 . 8 4 4 4$ ;FSDAF融合影像的特征波段与Landsat验证影像对应波段反射率一致性决定系数 $R ^ { 2 } ( \mathrm { R e d } ) { = } 0 . 6 9 9 9 \ . R ^ { 2 } ( \mathrm { S W I R } 2 ) { = } 0 . 7 4 9 3$ ；基于ESTARFM融合影像构建的EC值预测模型精度最高， $R ^ { 2 } { = } 0 . 9 2 6 8$ ，基于FSDAF融合影像构建的EC值预测模型精度良好， $R ^ { 2 } { = } 0 . 8 9 8 7$ ,基于验证影像构建的EC值预测模型 $R ^ { 2 } { = } 0 . 9 1 0 3$ ；ESTARFM模型的融合精度高于FSDAF模型，并且基于融合影像构建的EC值预测模型效果良好。

关键词：时空融合；随机森林；土壤电导率；土壤盐渍化

# 文章编号：

土壤盐渍化一般指易溶盐分在土壤中含量不断积累的现象或过程。发生盐渍化的耕地土壤不利于作物生长，使农作物减产或绝收，对粮食安全造成危害，同时会带来水土流失、土壤侵蚀、土地荒漠化等一系列的环境恶化问题，给生态环境以及物种多样性带来威胁[1]。定量有效预测土壤盐渍化情况，掌握土壤盐分分布规律，对于当地土壤盐渍化的治理具有重要意义。

随着空间信息技术的迅速发展，遥感技术在土壤盐分预测中应用前景广阔。然而，受预算经费和硬件技术条件等的限制，高时空分辨率的遥感影像依旧很难获取，当前常用的遥感影像数据仍存在“时空矛盾"问题[2]。Landsat等遥感卫星影像虽然空间分辨率较高，但其时间分辨率较低，且光学遥感影像易受到云层覆盖等大气条件的影响。MODIS等卫星传感器重访周期短，可获取高时间分辨率的遥感影像，但其空间分辨率较低。为此，提出多种多源遥感数据融合技术，以获取兼具高时间和高空间分辨率的遥感影像，来满足大范围、高精度、快速变化的地表监测与大气环境遥感的应用需求。目

# 干吴区地理

前较为流行的多源遥感数据融合算法包括：基于时空变化滤波的融合方法、基于空间信息分解的融合方法、基于机器学习的融合方法和组合型的融合方法[3]。其中基于权重滤波的时空融合模型原理简单，发展成熟，典型算法包括时空自适应的反射率融合模型（Spatial and temporal adaptive reflectancefusionmodel,STARFM）增强型时空自适应融合率反射模型(Enhanced spatial and temporal adaptive re-flectance fusion model,ESTARFM)等[4-5]。ESTARFM作为改进的时空自适应反射率融合模型，提升了该类方法对于异质性地表覆盖区域影像的融合效果以及对不同时相影像地物类型变化的预测能力[]而组合型的时空融合方法由于综合了其他不同类型融合方法的优势，较全面地应对了各类时空遥感影像融合方法的不足，通常具有较好的融合效果，因而具有更广泛的应用前景。灵活的时空融合模型（Flexible spatiotemporal data fusion,FSDAF）[7]组合了基于空间信息分解与时空变化滤波的2类融合方法，并融入了空间插值技术，提高了上述算法在异质性地表覆盖区的融合效果，并提高了其对地物类型变化的预测能力。

近年来，国内外学者基于遥感影像反演土壤盐分的有效方法，主要是利用多光谱影像和经典统计分析进行研究建模[8]。而土壤作为具有高度变异的时空连续体，土壤发育过程复杂，部分学者在建模过程中采用Pearson相关分析进行特征变量优选，忽略了环境因子对土壤的非线性作用9],这对土壤盐渍化反演精度产生影响。随着数据挖掘和机器学习技术迅速发展，它能够有效解决土壤与环境因子之间非线性问题，在土壤盐渍化反演中具有深远的应用价值。

时空融合算法目前已被广泛应用于生态水文[10]、植被指数[1]、城市温度[12]、洪水监测[13]等遥感应用研究，但是在土壤盐渍化监测中的应用研究仍十分欠缺。本文以渭干河一库车河三角洲绿洲为研究区，采用ESTARFM模型和FSDAF模型对MO-DIS和Landsat影像进行时空融合，根据实际采样时间，获取与采样时间相对应的高时空分辨影像数据，并基于时空融合影像数据构建关于土壤电导率(EC)的随机森林(RF)预测模型，探究分析时空融合影像应用于土壤盐渍化遥感监测的建模效果和反演精度，为时空融合影像在干旱区土壤盐渍化遥感监测中的应用提供科学支持和参考。

# 数据与方法

# 1.1 研究区概况

渭干河一库车河三角洲绿洲[4]位于新疆南部的塔里木盆地中北部，隶属阿克苏地区，辖区范围包括沙雅县、库车县、新和县。根据实地采样区域确定研究区边界地理坐标为 $8 1 ^ { \circ } 3 7 ^ { \prime } { \sim } 8 3 ^ { \circ } 5 9 ^ { \prime } \mathrm { E } , 4 1 ^ { \circ } 0 6 ^ { \prime } { \sim }$ $4 2 ^ { \circ } 4 0 ^ { \prime } \mathrm { N }$ ,海拔 $8 9 2 { \sim } 1 1 0 0 \ \mathrm { m }$ ，总面积 $5 2 3 . 7 6 \times 1 0 ^ { 2 } { \mathrm { k m } } ^ { 2 }$ ○研究区属于典型的大陆性暖温带干旱气候，蒸发强烈，降水分布不均，山区多年平均降水量为243.0$\mathbf { m } \mathbf { m }$ ,平原区多年平均降水量为 $4 6 . 5 ~ \mathrm { m m }$ ,平原区年平均蒸发量为 $1 3 7 4 \mathrm { m m }$ 。渭干河一库车河三角洲绿洲土地利用类型主要包括农田、草地、林地、荒地、盐渍地等;主要土壤类型为潮土、草甸土，此外还分布有棕钙土、沼泽土和盐土等多种类型土壤。在平原区中下部地势较平坦，地下水位较高，土壤下层构成物颗粒细，透水性差，蒸发作用强烈，导致盐分随水运动，积累于地表造成土壤盐渍化,灌区内盐渍化面积已达 $5 0 \%$ 以上，其中严重盐渍化面积达$3 0 \%$ ，盐渍化土壤pH为8左右，含盐主要成份为氯化物。因此，选择地区作为研究区具有较好的代表性，对改善生态环境及农业生产的发展具有重要意义，研究区采样点分布如图1所示。

# 1.2数据来源与处理

实测数据：2018年7月11—7月23日对研究区开展野外调查，用五点法采集土样，在各采样点30$\mathrm { m } { \times } 3 0 \mathrm { m }$ 的样方内使用木铲采集5个土壤样品，采样深度为 $1 0 \ \mathrm { c m }$ ，并在现场进行混合以创建代表性的复合土壤样本，使用误差小于 $5 \mathrm { m }$ 便携式GPS（UniStrongG120)记录每个采样点的位置。待土壤样品自然风干后去除杂质，过 $2 \mathrm { m m } ( 1 0 \$ 目）孔筛，称量20g土壤样品与 $1 0 0 ~ \mathrm { { m L } }$ 去离子水配置成水土比5:1的土壤悬浊液，震荡 $3 0 ~ \mathrm { m i n }$ 后静置 $2 4 \mathrm { ~ h ~ }$ ,在室温 $2 5 ~ \mathrm { { ^ { \circ } C } }$ 下提取渗滤液，采用配备有复合电极（TetraCon925)的数字多参数测量设备（Multi3420SetB，WTW $\operatorname { G m b } \mathrm { { H } }$ ,德国)测量EC值，最终获得有效样本数量为69个。

![](images/e8544f9022ebd26957fa0ecf0177c740bbe6cdd399bb4b8ea22af871e5d45138.jpg)  
图1研究区采样点分布图  
Fig.1 Distribution of sampling points in the study area

遥感影像：Landsat影像来源于谷歌地球云计算(GoogleEarthEngine,GEE)平台的T1_SR数据集，MODIS影像来源于GEE平台的MOD09A1（全球$5 0 0 \mathrm { ~ m ~ }$ 地表反射率8d合成)地表反射率数据集(L38d)。遥感影像数据信息见表1。

数据已进行辐射矫正和大气矫正，结合实地采样时间和云量( $\left. < 1 0 \% \right.$ ），选用2018年6月的一对MO-DIS、Landsat影像与2018年8月的一对MODIS、Landsat影像进行时空融合，选取2018年7月20日的Landsat影像作为验证影像，作为融合结果影像的比对参考。所有影像数据包括红光(Red)、蓝光（Blue）、绿光（Green）、近红外（NIR）、中红外1(SWIR1）、中红外2(SWIR2)6个特征波段，并在谷歌云计算平台对数据进行合成、去云、裁剪的预处理。利用ENVI5.3软件对MODIS影像进行重投影，并重采样为空间分辨率 $3 0 \mathrm { ~ m ~ }$ 的数据，与Landsat影像分辨率保持一致。

# 1.3 研究方法

1.3.1时空融合模型ESTARFM3模型是在STARFM算法的基础上进行改进的一种经典时空融合模型，ESTARFM模型融合质量高，具有较广泛的应用。

本文通过 $\mathrm { E N V I } 5 . 3 \substack { + \mathrm { I D L } 8 . 5 }$ 实现模型ESTARFM的时空融合算法过程，主要步骤包括：基于每个参考时刻内的高空间分辨率图像(Landsat影像)选取相似像元；相似像元权重计算；预测时刻 $T _ { \mathrm { p r e } }$ 目标像元值计算。其中，中心像元重建的表达式为：

$$
\begin{array} { r } { R _ { \mathrm { p r e } } ( x _ { \omega / 2 } , y _ { \omega / 2 } , T _ { \mathrm { p r e } } ) = T _ { 1 } R _ { 1 } ( x _ { \omega / 2 } , y _ { \omega / 2 } , T _ { 1 } ) + } \\ { T _ { 2 } R _ { 2 } ( x _ { \omega / 2 } , y _ { \omega / 2 } , T _ { 2 } ) } \end{array}
$$

式中： $R _ { \mathrm { { _ { p r e } } } }$ 为预测时相的高分辨率融合数据；$( x _ { \omega / 2 } , y _ { \omega / 2 } )$ 为预测时刻 $( \mathrm { \Delta } T _ { \mathrm { p r e } }$ )的中心像元值; $R _ { 1 } \setminus R _ { 2 }$ 为2个基础时相的高空间分辨率数据; $T _ { 1 } , T _ { 2 }$ 为2个基础时相数据的时间权重； $\omega$ 为滑动窗口的大小,本实验中模型参数滑动窗口大小 $\omega$ 为20，类别数class设置为4。

本文通过ENVI $5 . 3 \substack { + } \mathrm { I D L } 8 . 5$ 实现模型FSDAF的时空融合算法过程，在影像基对数上与ESTARFM算法保持一致,选用一对影像进行时空融合。FSDAF[7]综合了混合像元分解和加权函数对方法，能够比较好的对地物类型变化的区域进行预测。该算法利用初始时刻 $t _ { 0 }$ 的已知高、低分辨率影像、预测时刻 $t _ { k }$ 低分影像，融合得到 $t _ { k }$ 时刻高分影像。FSDAF5融合模型主要包括6个步骤：(1)进行 $t _ { 0 }$ 时刻的高空间分辨率影像(Landsat影像)分类;(2）估计从 $t _ { 0 }$ 时刻到 $t _ { k }$ 时刻高时间分辨率影像(MODIS影像)每个类别的时间变化；(3)计算 $t _ { k }$ 时刻的Landsat影像使用类别尺度的时间变化和计算MODIS影像每个像素预测的残差；(4）利用 $t _ { k }$ 时刻的MODIS影像，使用薄板样条函数预测高空间分辨率影像(Landsat影像）；(5)基于薄板样条函数的残差分布计算;(6)利用邻域信息得到Landsat影像的最终预测。

1.3.2预测模型构建 $\mathrm { R F } ^ { [ 1 5 ] }$ 是一种统计学习理论,它使用自举重采样方法从原始样本中提取多个样

表1遥感影像数据信息  
Tab.1 Remote sensing image data information   

<html><body><table><tr><td>波段名称</td><td>Landsat波段</td><td>分辨率/m</td><td>波谱范围/nm</td><td>波段名称</td><td>MODIS波段</td><td>分辨率/m</td><td>波谱范围/nm</td></tr><tr><td>Blue</td><td>2</td><td>30</td><td>450~515</td><td>Blue</td><td>3</td><td>500</td><td>459~479</td></tr><tr><td>Green</td><td>3</td><td>30</td><td>525~600</td><td>Green</td><td>4</td><td>500</td><td>545~565</td></tr><tr><td>Red</td><td>4</td><td>30</td><td>630~680</td><td>Red</td><td>1</td><td>500</td><td>620~670</td></tr><tr><td>NIR</td><td>5</td><td>30</td><td>845~885</td><td>NIR</td><td>2</td><td>500</td><td>841~876</td></tr><tr><td>SWIR1</td><td>6</td><td>30</td><td>1560~1651</td><td>SWIR1</td><td>5</td><td>500</td><td>1628~1652</td></tr><tr><td>SWIR2</td><td>7</td><td>30</td><td>2100~2300</td><td>SWIR2</td><td>6</td><td>500</td><td>2105~2155</td></tr></table></body></html>

注:Blue、Green、Red、NIR、SWIR1、SWIR2分别为蓝光、绿光、红光、近红外、中红外1、中红外2波段。下同。

# 干吴区地理

本，为每个自举样本构建决策树，然后将多个决策树的预测合并为最终预测结果的平均值，它构造的不同训练集可以增加回归模型之间的差异，从而提高组合回归模型的外推预测能力，因此在土壤盐渍化预测方面具有广泛应用，并且效果良好，本文通过Python3.7实现该模型的算法过程。本研究按照7:3对样本进行划分， $7 0 \%$ 作为预测集， $3 0 \%$ 作为验证集。在模型构建中，各个特征变量对EC值的贡献率存在差异[15]。本文基于影像数据提取了6个特征波段反射率、以及应用范围较广的植被指数和盐分指数，以EC值作为目标值，应用极端梯度提升[15]算法对提取的指数进行特征重要性筛选，优选出重要性高于0.01的6个植被指数和9个盐分指数参与建模(表2)。

# 3结果与分析

# 3.1融合结果与精度评估

对融合影像和验证影像进行假彩色合成，以假彩色显示，在目视解译的基础上，对比分析融合影像和验证影像可知（图2），ESTARFM模型、FSDAF模型的时空融合效果良好，各种地物大体上纹理清晰，图中所显示的水体、农田、道路轮廓特征清晰准确，与原始影像在空间上基本保持一致。为了清楚观察融合影像空间细节，将融合影像的放大到像素级，对比2幅融合影像和验证影像细节差异可知，

FSDAF融合影像对水体反映效果较明显。

为进一步验证两种融合模型的精度，分别对两种模型融合影像的6个特征波段反射率与Landsat验证影像对应波段反射率进行对比分析(表3)，并选取融合一致性程度较高的2个波段(Red、SWIR2)进行2D散点图显示(图3)。

从表3可以看出，ESTARFM模型的融合精度 $R ^ { 2 }$ 高于模型FSDAF;两种融合模型均是SWIR2波段融合效果最好，SWIR1波段融合效果最差，融合结果分析显示，ESTARFM模型的 $R ^ { 2 } ( \mathrm { S W I R } 2 ) { = } 0 . 8 4 4 4$ ，$R ^ { 2 }$ (SWIR1) $\scriptstyle = 0 . 6 3 5 8$ ;FSDAF模型的 $R ^ { 2 } \left( \mathrm { S W I R } 2 \right) =$ $0 . 7 4 9 3 , R ^ { 2 } ( \mathrm { S W I R 1 } ) = 0 . 4 9 0 9 ,$ 。ESTARFM融合影像的各个特征波段一致性程度均高于FSDAF融合影像，其中ESTARFM融合影像的Red、Green、Blue 波段融合精度 $R ^ { 2 }$ 分别为 $0 . 8 0 6 6 , 0 . 6 9 9 6 , 0 . 6 4 4 3$ ;FSDAF融合影像的Red、Green、Blue 波段融合精度 $R ^ { 2 }$ 分别为0.6999、0.5525、0.4959。

ESTARFM模型的融合影像中，对土壤盐渍化信息较为敏感的Red波段、SWIR2波段反射率与Landsat验证影像对应的波段反射率的一致性 $R ^ { 2 }$ 分别达到0.8066、0.8444（图3），2D散点图结果显示良好；在FSDAF模型的融合影像中，对土壤盐渍化信息较为敏感的Red波段、SWIR2波段反射率与Landsat验证影像对应的波段反射率的一致性 $R ^ { 2 }$ 分别达到0.6999、0.7493（图4），融合效果较次于ESTARFM注：Red为红光波段;SWIR2为中红外2波段。下同。

表2参与反演的变量指数及计算公式  
Tab.2Variable indicesandcalculation formulas involved ininversion   

<html><body><table><tr><td>指数</td><td>公式</td></tr><tr><td>归一化植被指数(NDVI)[16]</td><td>(NIR-Red)/(NIR+Red)</td></tr><tr><td>增强型植被指数(EVI)[16]</td><td>2.5×[(NIR-Red)/(NIR+6Red-7.5Blue+1)]</td></tr><tr><td>扩展差值植被指数(EDVI)[17]</td><td>NIR+SWIR1-Red</td></tr><tr><td>比值植被指数(RVI)[1]</td><td>NIR/Green</td></tr><tr><td>扩展的归一化植被指数(ENDVI)19]</td><td>(NIR+SWIR2-Red)/(NIR+SWIR2+Red)</td></tr><tr><td>扩展的增强型植被指数(EEVI)20]</td><td>2.5×[(NIR+SWIR1-Red/(NIR+SWIR1+6Red-7.5Blue+1)]</td></tr><tr><td>盐分指数(SIT)21)</td><td>(Red/NIR)×100</td></tr><tr><td>盐分指数(SI)22)</td><td>(BluexRed)0.5</td></tr><tr><td>盐分指数(SI1)[22]</td><td>(GreenXRed)0.5</td></tr><tr><td>盐分指数(SI2)22]</td><td>(Green²+Red²+NIR²)0.5</td></tr><tr><td>盐分指数(SI3)[23]</td><td>(Red+Green2) 0.5</td></tr><tr><td>归一化盐分指数(NDSI)[24)</td><td>(Red-NIR)/(Red+NIR)</td></tr><tr><td>盐分指数(S1)[25]</td><td>Blue/Red</td></tr><tr><td>盐分指数(S2)[26]</td><td>(Blue-Red)/(Blue+Red)</td></tr><tr><td>盐分指数(S3)[26]</td><td>(GreenXRed)/Blue</td></tr></table></body></html>

![](images/cf67f8361f822275d99b7fb6fbb14e321f6889a998c92161e7e7723ab77a7cf6.jpg)  
Fig.2 Partial comparison of false color synthesized from fusion image and verification image

表3融合影像与验证影像波段反射率特征分析  
Tab.3Analysis of the reflectance characteristics of the fusion image and the verification image band   

<html><body><table><tr><td>模型</td><td>Blue</td><td>Green</td><td>Red</td><td>NIR</td><td>SWIR1</td><td>SWIR2</td></tr><tr><td>ESTARFM</td><td>y=-128.8+1.0848x</td><td>y=-113.7+1.0552x</td><td>y=-272.8+1.1213x</td><td>y=-91.10+1.0880x</td><td>y=407.07+0.8961x</td><td>y=-59.69+1.0485x</td></tr><tr><td>模型</td><td>R²=0.6443</td><td>R=0.6996</td><td>R²=0.8066</td><td>R²=0.7496</td><td>R=0.6358</td><td>R²=0.8444</td></tr><tr><td>FSDAF</td><td>y=-263.2+1.2043x</td><td>y=-411.1+1.2268x</td><td>y=-521.9+1.2656x</td><td>y=-11.97+1.1058x</td><td>y=445.28+0.9519x</td><td>y=-267.6+1.1818x</td></tr><tr><td>模型</td><td>R²=0.4959</td><td>R²=0.5525</td><td>R²=0.6999</td><td>R²=0.6202</td><td>R²=0.4909</td><td>R²=0.7493</td></tr></table></body></html>

注：x为验证影像波段反射率： $; y$ 为融合影像波段反射率； $R ^ { 2 }$ 为融合精度。

![](images/17f3d598837589d56e3ce1cdd09481ae7ac7a9b350609f7b387af2fe084fee8d.jpg)  
图2融合影像与验证影像合成假彩色局部对比图  
图3ESTARFM模型融合影像与验证影像2D散点图  
Fig.3 2D scatter plot of ESTARFM model fusion image and verification image

![](images/bcc0e6502dcdaa87a61bf9b9e75d05e06ff4ab7b51679ff5b9e5289ea307c029.jpg)  
干辛区地理  
图4FSDAF模型融合影像与验证影像2D散点图

模型的融合效果。综合分析可知，ESTARFM模型的6个特征波段的融合结果精度 $R ^ { 2 }$ 均在0.6以上，相较于FSDAF模型的融合效果更优。

# 3.2不同EC值的光谱反射率

为了可视化实测土壤EC值与时空融合影像各波段反射率之间的关系，根据土壤盐渍化程度划分标准，绘制出不同盐度水平区间与对应光谱反射率均值的光谱曲线关系图(图5)。对比两种时空融合影像在不同盐度的光谱曲线图(图5)可知，针对ES-TARFM融合影像，随着EC值升高，土壤光谱反射率也在升高，各波段光谱反射率曲线变化趋势一致，从可见光Red波段开始陡然上升，在NIR波段处达到一个峰值;当EC值在 $0 { \sim } 2 ~ \mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ （非盐渍化土壤)之间时，光谱反射率最低，当EC值在 $2 { \sim } 4 ~ \mathrm { m S } { \cdot } \mathrm { c m } ^ { - 1 }$ （轻度盐渍化)之间时，光谱曲线从Red波段开始陡然升高，并且从可见光Red波段到SWIR2的反射率一直处于最高状态。

FSDAF融合影像，当EC值在 $0 { \sim } 2 ~ \mathrm { m S } { \cdot } \mathrm { c m } ^ { - 1 }$ （非盐渍化土壤)之间时，光谱反射率最低，当EC值 $\geqslant 1 6$ $\mathrm { m } \mathrm { S } \cdot \mathrm { c m } ^ { - 1 }$ (盐土)时，光谱反射率最高，并且光谱曲线在SWIR1波段处达到峰值；其余波段的光谱曲线从可见光Blue波段开始，反射率不断升高，在NIR波段处，反射率达到峰值，这与ESTARFM时空融合影像的变化趋势一致。此外，ESTARFM时空融合影像和FSDAF时空融合影像中的NIR波段处，不同EC值水平的光谱特征不明显，这一点与前人研究结果一致。

# 3.3预测模型精度评估

土壤电导率(EC)能够有效地反映土壤盐渍化程度，在整个研究区实测样本中，EC值变化范围较大，介于 $0 . 0 4 7 6 { \sim } 1 0 8 . 7 ~ \mathrm { m S ^ { . } c m ^ { - 1 } }$ 之间，建模输入样本数据中，剔除2个异常值，样本 $7 0 \%$ 作为预测集( $\overset { \cdot } { n } = \overset { \cdot } { \underset { \cdot } { \longrightarrow } }$ 46）， $3 0 \%$ 作为验证集（ $\scriptstyle { \overbrace { n { = } 2 1 } }$ )。本研究共有6个植被指数、9个盐分指数、6个特征波段参与建模，采用10倍交叉验证方法进行模型验证。为评估预测模型的性能，选用 $R ^ { 2 }$ 作为预测建模的评价指标， $R ^ { 2 }$ 值越大，模型精度越高。

![](images/30cd1d6a1b5a1a3af6e7f921a95e9c8864ffe87778edb42b33d0c33afe8ceaf5.jpg)  
Fig.42D scatter plot of FSDAF model fusion image and verification image   
注：Blue、Green分别为蓝光、绿光波段;NIR为近红外波段;SWIR1为中红外1波段。  
图5不同盐度土壤在时空融合影像中反射光谱曲线  
Fig.5Reflectance spectrum curves of soils with different salinities in spatio-temporal fusion images

![](images/75a3b82ef94b8d39a8e2f31eada22444b74116cf60b19fb9fe0df336f1236480.jpg)  
图6基于3种影像EC值拟合  
Fig.6 EC values fitting based on 3 kinds of image

对比分析融合影像、验证影像的EC值建模，结果显示(图6)，基于时空融合影像构建的EC预测模型精度良好，其中，基于ESTARFM融合影像构建的EC 值预测模型效果最好( $R ^ { 2 } { = } 0 . 9 2 6 8$ ）；基于Landsat影像次之（ $R ^ { 2 } { = } 0 . 9 1 0 3 \$ ；FSDAF融合影像构建的EC值预测模型精度最低（ $\scriptstyle \cdot { \cal R } ^ { 2 } = 0 . 8 9 8 7$ )。预测模型结果理想，说明选用的两种时空融合模型对MODIS和Landsat影像进行时空融合，能够获取高时空分辨率影像，并在EC值预测模型构建中应用效果良好。

# 4讨论

地表与大气环境需要实时精细的遥感监测，高时空分辨率的遥感影像又较难获取，时空遥感影像融合技术具有成本低、可靠性强等优点，近年来取得了较大的研究进展,在植被长势[11]、洪水监测[12]、温度监测[3等方面已取得一定的研究成果。本研究选用两种较为成熟的时空融合算法，对Landsat和MODIS遥感影像进行时空融合，使融合影像兼具Landsat数据的空间特征和MODIS数据的时间特征，而现今时空融合算法都无法准确预测土地覆盖类型的微小变化，因此时空融合后的影像在空间特征上与Landsat原始影像产生差异，只能不断改进时空融合算法来减小差异。而ESTARFM模型是在STARFM模型基础上进行改进，提升了对异质性区域预测的精度和适用性，研究显示，ESTARFM模型对盐渍化特征波段的时空融合精度优于FSDAF模型，对土壤盐分的拟合精度也更高。FSDAF模型结合混合像元分解，加入薄板样条函数插值、距离加权，能准确预测土地覆盖类型发生突变的区域，已有研究显示FSDAF算法对洪水预测效果良好[2],本研究中土壤盐渍化是缓慢发生过程，对FSDAF算法的优势体现不明显，因此基于ESTARFM融合影像的土壤盐分拟合效果更好，ESTARFM融合影像对土壤盐渍化预测更具适用性。此外，土壤盐渍化发生过程复杂，为确保采样获取的“点状"信息能代表土壤盐渍化分布的“面状"信息，本研究进行设计采样时，借助MODIS数据，以及DEM衍生变量（坡度和地形湿度指数)和土壤质地数据，基于代表性等级设计采样，每个采样点样方为 $3 0 \mathrm { m } { \times } 3 0 \mathrm { m }$ ,使用五点采样法采集土壤样品，并选取与采样时间相对应的遥感影像，重采样为 $3 0 \mathrm { m }$ 分辨率后再进行时空融合，使采样点的样方范围与遥感影像的像素相匹配，确保土壤盐渍化的预测精度。在基于融合影像预测的非盐渍土EC均值为 $0 . 3 8 ~ \mathrm { m S \cdot c m ^ { - 1 } }$ ,面积占比为 $8 . 9 6 \%$ ;轻度盐渍土EC均值为 $2 . 6 1 \mathrm { m S ^ { . } c m ^ { - 1 } }$ ,面积占比为 $3 7 . 2 0 \%$ ;中度盐渍土EC值为 $5 . 8 9 ~ \mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ ，面积占比为 $1 2 . 0 9 \%$ ；重度盐渍土EC均值为11.83$\mathrm { m } \mathrm { S } \cdot \mathrm { c m } ^ { - 1 }$ ,面积占比为 $9 . 5 5 \%$ ;盐土EC均值为31.19

# 干旱区地理

$\mathrm { m } \mathrm { S } \cdot \mathrm { c m } ^ { - 1 }$ ，面积占比为 $3 2 . 2 0 \%$ 。而马国林对此研究区土壤EC值预测结果显示，非盐渍土的EC均值为 $0 . 4 1 ~ \mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ ,轻度盐渍化土壤EC均值为2.45$\mathbf { m } \mathbf { S \cdot } \mathbf { c m } ^ { - 1 }$ ,中度盐渍化土壤EC均值为 $6 . 2 5 \mathrm { m S \cdot c m ^ { - 1 } }$ ，重度盐渍化土壤EC均值为 $1 2 . 0 7 ~ \mathrm { m S \cdot c m ^ { - 1 } }$ ,盐土EC均值为 $4 0 . 2 5 ~ \mathrm { m S \cdot c m ^ { - 1 } }$ ,经非参数检验，其结果与本文预测结果并没有显著差异。

时空融合影像在土壤盐渍化研究中具有很大应用空间， $\mathrm { H a n }$ 等基于时空融合影像探究突发降水事件对土壤盐分预测的影响。本文研究利用目前较为成熟的时空融合算法应用于土壤盐渍化预测的适用性，但不同时空融合算法的优势有待挖掘，需要进一步寻求对土壤盐渍化特征提取更具优势的时空融合算法，提升遥感影像在土壤盐渍化预测中的应用价值。

# 5结论

（1）应用ESTARFM模型、FSDAF模型能够较好的融合出基于MODIS和Landsat遥感影像的高时空分辨率影像，从目视解译结果来看，融合影像空间细节信息比较清晰，与验证影像空间信息基本一致，说明融合结果理想。不同模型对于影像各个波段的融合结果均有差异，这可能是由不同模型的精度误差所造成[4-5]

（2）两种时空融合影像在不同EC值水平的光谱特征曲线变化明显，基于ESTARFM融合影像构建的EC值预测模型精度最好， $R ^ { 2 } { = } 0 . 9 2 6 8$ ;基于FS-DAF融合影像构建的EC值预测模型精度良好， $R ^ { 2 } { = }$ 0.8987;基于Landsat验证影像构建的EC值预测模型精度较好， $R ^ { 2 } { = } 0 . 9 1 0 3$ 。由此说明时空融合技术在土壤盐渍化遥感监测中具有很好的应用价值和发展空间，对比两种常用的时空融合影像在盐分预测方面的应用效果，基于ESTARFM的融合影像更适用于盐分预测。不同环境协变量对土壤盐渍化遥感监测精度都有影响[15，已有学者尝试选用不同的建模因子、不同的模型进行土壤盐分预测[8]

（3）基于MODIS和Landsat的时空融合影像能有效提升遥感影像的时空分辨率，解决时相数据缺失问题，对比ESTARFM模型和FSDAF模型的时空融合结果可知，ESTARFM模型能够融合出精度更高的时空分辨率影像。在土壤盐渍化遥感监测中，深入挖掘时空融合影像在土壤盐渍化遥感监测方面的应用前景，有助于提升遥感数据的利用价值，提升盐渍化遥感监测在实际应用中的经济效益和实用性。另外，本文选用GEE平台获取影像数据，平台在线完成预处理过程，高效快捷，提升数据预处理速度，也说明利用谷歌云计算平台获取遥感影像，进行土壤盐渍化监测同样可以提升效率，为土壤盐渍化遥感监测提供了与时俱进的利用价值和发展空间。

# 参考文献(References)

[1]吴亚坤,刘广明,苏里坦,等.多源数据的区域土壤盐渍化精确 评估[J].光谱学与光谱分析,2018,38(11):3528-3533.[Wu Yakun, Liu Guangming,Su Litan, et al.Accurate evaluation of regional soil salinization using multi-source data[J]. Spectroscopy and Spectral Analysis,2018,38(11): 3528-3533.]   
[2]Han L J, Ding JL, Zhang JY,et al.Precipitation events determine the spatiotemporal distribution of playa surface salinity in arid regions: Evidence from satelite data fused via the enhanced spatial and temporal adaptive reflectance fusion model[J]. Catena, 2021, 206: 105546,doi: 10.1016/J.CATENA.2021.105546.   
[3]Zhu X L, Chen J, Gao F,et al. An enhanced spatial and temporal adaptive reflectance fusion model for complex heterogeneous regions[J]. Remote Sensing of Environment,2010,114(11): 2610- 2623.   
[4]黄波.时空遥感影像融合研究的进展与趋势[J].四川师范大学 学报(自然科学版),2020,43(4):427-434,424.[Huang Bo.Research progress and trend of spatial and temporal remote sensing image fusion[J]. Journal of Sichuan Normal University (Natural Science Edition),2020,43(4): 427-434,424.]   
[5]Hilker T,Wulder MA,Coops N C,et al.A new data fusion model for high spatial-and temporal-resolution mapping of forest disturbance based on Landsat and MODIS[J]. Remote Sensing of Environment,2009,113(8): 1613-1627.   
[6]Zhao Y Q, Huang B,Song HH.A robust adaptive spatial and temporal image fusion model for complex land surface changes[J]. Remote Sensing of Environment,2018,208: 42-62.   
[7]Meng L H, Liu HJ, Ustin S L, et al. Assessment of FSDAF accuracy on cotton yield estimation using different MODIS products and landsat based on the mixed degree index with different surroundings[J].Sensors (Basel,Switzerland)，2021,21(15):5184,doi: 10.3390/S21155184.   
[8]马倩倩,董博,许旺旺,等.干旱区耕地质量等级评价及土壤养 分与盐渍化的分析研究——以民勤绿洲为例[J].干旱区地理, 2021,44(2): 514-524.[Ma Qianqian, Dong Bo, Xu Wangwang,et al.Evaluation of cultivated land quality and analysis of soil nutrients and in arid areas: Taking Minqin Oasis as an example[J].Arid Land Geography,2021, 44(2): 514-524.]   
[9]柳菲,陈沛源,于海超,等.民勤绿洲不同土地利用类型下土壤 水盐的空间分布特征分析[J].干旱区地理,2020,43(2):406- 414.[Liu Fei, Chen Peiyuan, Yu Haichao,etal. Spatial distribution characteristics of soil water and salt under different land use types in Minqin Oasis[J].Arid Land Geography,2020,43(2): 406- 414.]   
[10] 张晓川,王杰.基于遥感时空融合的升金湖湿地生态水文结构 分析[J].遥感技术与应用,2020,35(5):1109-1117.[Zhang Xiaochuan,Wang Jie.The analysis of eco-hydrological structure of Shengjin Lake Wetland based on spatial and temporal fusion technology of remote sensing[J]. Remote Sensing Technology and Application,2020,35(5): 1109-1117.]   
[11] 李超,李雪梅,田亚林,等.温度植被干旱指数时空融合模型对 比[J].遥感技术与应用,2020,35(4): 832-844.[Li Chao,Li Xuemei,Tian Yalin,etal.Time and space fusion model comparison of temperature vegetation drought index[J]. Remote Sensing Technology and Application ,2020,35(4): 832-844.]   
[12] 石晨烈,王旭红,张萌.3种时空融合算法在洪水监测中的适用 性研究[J].国土资源遥感,2020,32(2):111-119.[Shi Chenlie, Wang Xuhong,Zhang Meng.Analysis of the applicability of three remote sensing spatiotemporal fusion algorithms in flood monitoring[J]. Remote Sensing for Land and Resources,2O20,32(2):111- 119.]   
[13] 王爽,王承武,张飞云.基于FSDAF模型的干旱区典型绿洲城 市夏季地表热岛效应时空演变研究[J].干旱区地理,2021,44 (1): 118-130.[Wang Shuang,Wang Chengwu, Zhang Feiyun. Spatiotemporal variations of the summer daytime surface urban heat island of oasiscity in arid area basedon FSDAF model[J].Arid Land Geography,2021, 44(1): 118-130.]   
[14] 何珍珍,王宏卫,杨胜天,等.渭干河一库车河绿洲景观生态安 全时空分异及格局优化[J].生态学报,2019,39(15):5473- 5482.[He Zhenzhen,Wang Hongwei, Yang Shengtian, et al. Spatial-temporal differentiation and pattrn optimization of land scape ecological security in the Ugan-Kuqa River oasis[J].Acta Ecologica Sinica,2019,39(15): 5473-5482.]   
[15] 马国林,丁建丽,韩礼敬,等.基于变量优选与机器学习的干旱 区湿地土壤盐渍化数字制图[J].农业工程学报,2020,36(19): 124-131.[MaGuolin,DgaliHanLjieal.Digia of soil salinization in arid area wetland based on variable optimized selection and machine learning[J]. Transactions of the Chinese Society of Agricultural Engineering,2020,36(19): 124-131.]   
[16]LobellD B,Lesch S M, Corwin D L,et al. Regional-scale asessment of soil salinity in the Red River Valley using multi-year MODIS EVI and NDVI[J]. Journal of Environmental Quality,2010,39 (1): 35-41.   
[17]郑裕东,徐云成,严海军,等.基于近地遥感系统的小麦玉米冠 层RVI和NDVI获取影响因素分析[J].光谱学与光谱分析, 2021,41(8): 2578-2585.[Zheng Yudong, Xu Yuncheng,Yan Haijun,et al.Analysisof influencingfactorsin wheat/maizeanopy RVI and NDVI acquisition using ground-based remote sensing system[J].Spectroscopy and Spectral Analysis,2021,41(8):2578- 2585.]   
[18] 魏阳,丁建丽,王飞.基于Landsat OLI的绿洲灌区土壤盐度最 优预测尺度分析[J].中国农业科学,2017,50(15):2969-2982. [Wei Yang,Ding Jianli,Wang Fei.Optimal scale analysis of soil salinity prediction in oasis irrigated area of arid land based on Landsat OLI[J]. Scientia Agricultura Sinica,2017, 50(15): 2969- 2982.]   
[19]王飞,丁建丽,魏阳,等.基于Landsat 系列数据的盐分指数和植 被指数对土壤盐度变异性的响应分析——以新疆天山南北典 型绿洲为例[J].生态学报,2017,37(15): 5007-5022.[Wang Fei, Ding Jianli,Wei Yang,et al.Sensitivity analysis of soil salinity and vegetation indices to detect soil salinity variation by using Landsat series images: Applications in different oases in Xinjiang, China[J]. Acta Ecologica Sinica,2017,37(15): 5007-502.]   
[20] 陈红艳,赵庚星,陈敬春,等.基于改进植被指数的黄河口区盐 渍土盐分遥感反演[J].农业工程学报,2015,31(5):107-114. [Chen Hongyan, Zhao Gengxing,Cheng Jingchun,et al.Remote sensing inversion of saline soil salinity based on modified vegetation index in estuary area of Yellow River[J]. Transactions of the Chinese Society of Agricultural Engineering,2015,31(5):107- 114.]   
[21] 冯娟,丁建丽,杨爱霞,等.干旱区土壤盐渍化信息遥感建模[J]. 干旱地区农业研究,2018,36(1):266-273.[Fen Juan,Ding Jianli, Yang Aixia,et al. Remote sensing modeling of soil salinization information in arid areas[J].Agricultural Research in the Arid Areas,2018,36(1): 266-273.]   
[22] 樊彦国,张维康,刘敬一.基于植被指数-盐分指数特征空间的 黄河三角洲盐渍化遥感监测研究[J].山东农业科学,2016,48 (5):137-141. [Fan Yanguo, Zhang Weikang,Liu Jingyi. Remote sensing monitoring model of soil salinization in the Yellow River Delta Zone based on vegetation index-salt index feature space[J]. Shandong Agricultural Sciences,2016,48(5): 137-141.]   
[23] 曹雷,丁建丽,玉米提·哈力克,等.基于国产高分一号卫星数据 的区域土壤盐渍化信息提取与建模[J].土壤学报,2016,53(6): 1399-1409.[Cao Lei,Ding Jianli,Halik Umut,etal. Extraction and modeling of regional soil salinization basedon data from GF-1 satelite[J]. Acta Pedologica Sinica,2016,53(6): 1399-1409.]   
[24]Kamh G M E, Ismael B,Oguchi C T.Pore size distribution and wall side orientation controlling salt susceptibility index“SSI" and weathering rate of stratified pharaonic rock art[J]. Restoration of Buildings and Monuments,2013,19(5): 341-362.   
[25] Sahana M,Rehman S,Patel PP,et al. Assessing the degree of soil salinity in the Indian Sundarban Biosphere Reserve using measured soil electrical conductivity and remote sensing data-derived salinity indices[J].Arabian Journal of Geosciences,2O20,13(24): 1289,doi:10.1007/S12517-020-06310-W.

# 干吴区地理

[26]Nguyen KA,Liou YA,Tran HP,et al. Soil salinity assessment by using near-infrared channel and vegetation soil salinity index derived fromLandsat 8 OLI data:A case study in the Tra Vinh Province,Mekong Delta,Vietnam[J].Progress in Earth and Planetary Science,2020,7(1): 1-16.

[27]马国林.耦合多源传感器与机器学习算法的渭-库绿洲土壤盐 分估测[D].乌鲁木齐:新疆大学,2021.[MaGuolin.Estimation of soil salinity in Weigan-Kuqa Oasis coupling multi-source sensors and machine learning algorithms[D]. Urumqi: Xinjiang University,2021.]

# Exploring the application of MODIS and Landsat spatiotemporal fusion images in soil salinization: A case of Ugan River-Kuqa River Delta Oasis

ZHAO Qiaozhen²，DING Jianli'2³3，HAN Lijing¹²， JIN Xiaoye $^ { 1 , 2 }$ ，HAO Jianping4

(1.KeyLaboratoryof Smart CityandEnvironmental Modelingof Autonomous Region Universities,SchoolofResourcesand EnvironmentalSciences,XinjingUniversityUrumqi3O6,Xinjiang,China;2.KeyLboratoryofOasisEcology,styf Education,XinjangUnversity,UumqiO6,Xinjang,hina;3.instryofaturalResources,CentralAsiGoaic Information Technology DevelopmentandApplicationEngineringTechnologyInnovation Center,Urumqi 83046,Xinjiang, China;4.Ugan River Basin Management Ofice,Aksu Prefecture,Xinjiang,Aksu 842Ooo,Xinjiang, China)

Abstract: Remote sensing monitoring of soil salinization relies on high spatiotemporal resolution images, which are difcult to obtain due to high cost,revisit period of the satellite,and weather efects.The spatiotemporal fusion technology of remote sensing images has the advantages of low cost and good reliability and has been widely used in several studies,such as vegetation growth,flood monitoring,and temperature monitoring.This study ivestigates the efectiveness of spatiotemporal fusion images in soil salinization monitoring at Ugan River-Kuqa River Delta Oasis,south Xinjiang,China.An enhanced spatial and temporal adaptive reflectance fusion model and flexible spatiotemporal data fusion model were employed to fuse MODIS and Landsat images and generate high spatiotemporal resolution images.A random forest prediction model for soil conductivity (EC) was created using the fusion images.Furthermore,the precision of both models was evaluated.Results show that the fusion images made by the ESTARFM and FSDAF models have high spatial resolution and good uniformity compard with the verification image.Verification revealed the reliability of the fusion results from the ESTARFM algorithm, $R ^ { 2 } ( \mathrm { R e d } ) { = } 0 . 8 0 6 6$ and $R ^ { 2 } ( \mathrm { S W I R } 2 ) { = } 0 . 8 4 4 4$ ，and the FSDAF algorithm, $R ^ { 2 } ( \mathrm { R e d } ) { = } 0 . 6 9 9 9$ and $R ^ { 2 } ( \mathrm { S W I R } 2 ) { = } 0 . 7 4 9 3$ . The EC prediction model created using the ESTARFM fusion images had the best accuracy with $R ^ { 2 }$ of 0.9268.Meanwhile, the $R ^ { 2 }$ of the EC prediction model constructed from FSDAF was O.8987 and that constructed based on Landsat verification images was 0.9103.This finding showed that spatiotemporal fusion technology has good application in the remote sensing monitoring of soil salinization. Comparison of the salinity prediction results from the two spatiotemporal image fusion models revealed that the ESTARFM model is suitable for salinity prediction.

Key words: temporal and spatial fusion; random forest; electric conductivity； soil salinization