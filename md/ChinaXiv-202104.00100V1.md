# 多特征辅助下的GF-6WFV影像准噶尔山楂识别研究

陈春秀²，陈蜀江}²，徐世薇³，陈孟禹4，贾翔¹，黄铁成'，李春蕾ら(1.新疆师范大学地理科学与旅游学院,新疆 乌鲁木齐8300054；2.乌鲁木齐空间遥感应用研究所，新疆乌鲁木齐830054；3.额敏县自然资源局,新疆 塔城834600；4.北京林业大学林学院，北京100083；5.中国林业科学研究院森林生态环境与保护研究所,北京100091)

摘要：针对高分六号WFV数据应用研究基础相对薄弱,准噶尔山楂遥感识别在算法、数据源等方面存在不足的问题,联合GF-6WFV和ZY-3号影像数据提取多种分类特征,基于面向对象分割、特征选择、特征重要性评价与组合以及多分类器联合等方法对准噶尔山楂的遥感识别开展研究，提出优选特征辅助下的面向对象多分类器组合的准噶尔山楂识别算法。研究表明：(1)GF-6WFV数据能够很好的对准噶尔山楂进行识别，特别是新增的红边波段对树种识别具有重要作用;(2）面向对象分割、特征选择和多特征组合都对准噶尔山楂识别的精度具有正向提升作用;（3）多分类器组合算法能够弥补单一分类器表征力差异造成的误差,显著提高识别精度和算法的稳定性。

关键词：高分六号；特征选择；面向对象；多分类器组合；准噶尔山楂

准噶尔山楂(Crataerus songarica)在新疆霍城县果子沟、大西沟、小西沟以及伊宁县吉尔格朗沟等地区分布，是新疆特有珍稀濒危植物，被列入国家优先保护物种名录[]。准噶尔山楂具有很高的药用和营养价值，对于干旱区生态稳定和天山野果林生物多样性保护具有重要意义。气候变化和人为干扰的加剧导致准噶尔山楂其生境遭到破坏，实际面积不断减少[2]。准噶尔山楂资源的保护已经刻不容缓，准噶尔山楂空间分布信息的准确提取研究具有重要意义。考虑到天山脆弱的生态系统和复杂的地形环境，传统森林调查方法已无法满足应用要求，而遥感技术凭借准确、快速、生态无损和对地形敏感度低的特点在生态脆弱区监测领域具有天然优势和巨大潜力。

近些年，国内外众多专家对遥感树种识别技术开展了一系列的研究，取得了丰硕的成果。总结近10a的研究发现，影像识别算法经历了从传统参数模型(最大似然算法、迭代自组织算法和K-最近邻算法等)到非参数决策算法(支持向量机、随机森林和传统人工神经网络等)再到数据驱动的深度学习算法和基于像元分类到顾及分类对象空间分布特性的面向对象分类的过程[3-5]。随着航天技术的发展，遥感数据获取途径更加多样、稳定。多源数据融合并构建能够多角度反映森林群落属性的分类特征集辅助识别研究成为主流，以期解决森林复杂群落结构下“同物异谱”与“同谱异物"造成的分类难题。但是树种识别在算法研究、分类特征构建等方面仍存在进一步研究的空间。首先，从分类算法研究角度上看，传统单一分类算法易受到算法原理、分类系统等因素影响，难以完整有效的对目标进行特征化的表达，分类精度表现不稳定。如Kou-$\mathrm { k a l }$ 等和Yang等分别利用多光谱数据和激光雷达数据结合随机森林算法,对阿尔卑斯山附近的森林和北方森林进行分类识别，而总体精度一个高达$9 2 \%$ ,另一个仅有 $6 6 \%$ 。而能够依靠数据进行特征自学习，在分类精度上表现出极大优势的深度学习算法则因对样本集和运算能力要求过高，工程化应用难度很大[8]。多分类器融合算法通过分类权重自适应或组合投票等方式,能够在一定程度上弥补单一分类器特征表征能力不足造成的影响，提高分类的精度，且其基本单元为发展成熟的传统分类算法，易于实现，是目前最有可能推动树种识别产业化应用的识别算法，具有较大的研究价值。如王怀警等[使用多分类器组合策略将支持向量机和随机森林算法进行组合，进一步提高了森林类型识别的精度。其次，在选择数据构建分类特征集时，机载平台数据受到越来越多的关注，如机载高光谱数据和激光雷达数据。刘怡君等[]利用机载高光谱数据与激光雷达数据融合结合支持向量机对普洱市王掌山试验区的主要树种进行分类,取得了良好的效果；刘丽娟等[1使用机载激光雷达和CASI高光谱数据结合分层掩膜和光谱微分技术对伊春市带岭区凉水国家级自然保护区内5种主要树种进行识别，总体精度高达 $8 3 . 8 8 \%$ 。虽然机载数据在很多研究中表现优异，但是数据获取成本较高，应用难度大。2019年升空的GF-6号卫星携带的WFV传感器具有高时间分辨率、多波段和宽覆盖的特点，特别是相对于GF-1WFV传感器新增了红边、黄光和紫光波段，对树种识别具有重要意义，但是其相关研究基础较为薄弱。此外，在树种识别研究对象的选择方面，大部分研究都集中在资源储量较大的树种上，如天山云杉、马尾松等[13]。但是对准噶尔山楂这类分布不广、资源储量相对较小，但对当地生态环境保护具有重要意义的群落遥感识别研究极少。近年来,对准噶尔山楂的研究主要集中在其理化特性、群落特征和保护策略上，如李利平等[14]通过野外调查和资料收集的方式获取67个野果林群落样方，分析了新疆伊犁地区野果林群落结构和分布特征。数据主要通过野外调查的方式获取，而对应用成本更低、信息获取效率更高的遥感提取技术研究较少。

基于上述遥感树种识别研究的趋势和薄弱点，本文以准噶尔山楂作为研究对象，基于国产ZY-3影像、GF-6WFV影像和地面实测样本数据，以随机森林和支持向量机分类器为工具，开展以下工作：（1）基于线性聚类算法对影像进行分割，结合实测数据进行评价，探究准噶尔山楂识别最优分割尺度；（2）基于影像数据提取多种分类特征因子，分析不同分类因子对准噶尔山楂提取的重要度，构建优选分类特征集；（3）基于随机森林(random forest,

RF)和支持向量机(support vector machine,SVM)算法构建组合分类器，实现准噶尔山楂分布信息的提取，以期弥补单一分类器的不足并为准噶尔山楂的保护和GF-6WFV数据在林业上的应用提供一定科学的参考。

# 1研究区概况

在新疆伊犁霍城县天山北坡大西沟科古尔琴山南坡选取长宽分别为 $1 0 . 9 6 \mathrm { k m }$ 和 $1 0 . 2 1 \mathrm { k m }$ 的矩形区域作为研究区 $( 8 0 ^ { \circ } 4 5 ^ { \prime } 0 0 ^ { \prime \prime } \mathrm { E } { \sim } 8 0 ^ { \circ } 5 2 ^ { \prime } 3 0 ^ { \prime \prime } \mathrm { E } , 4 4 ^ { \circ } 2 5 ^ { \prime } \mathrm { N } { \sim }$ $4 4 ^ { \circ } 3 0 ^ { \prime } \mathrm { N } )$ （图1)，图中影像由ZY-3多光谱数据4、3、2波段假彩色合成。研究区位于第四季冰川改造而成的U型谷内，海拔 $8 0 0 { \sim } 1 5 0 0 ~ \mathrm { m }$ ，属温带湿润性气候，年平均温度 $8 . 7 ~ \mathrm { ^ { \circ } C }$ ,平均降水 $2 6 6 . 9 \ \mathrm { m m }$ ,无霜期$1 6 5 \mathrm { ~ d ~ }$ 。土壤多为沙壤土和草甸土，土质松软,肥力适中。在特殊的立地因子和温和湿润气候条件下，研究区内植被生长茂密，乔木高 $3 { \sim } 4 \mathrm { m }$ ,郁闭度 $0 . 5 \sim$ 0.7，形成了以新疆准噶尔山楂为主要树种的植被群落。

# 2数据与方法

# 2.1数据来源与处理

为探究多特征联合识别的优势，融合多源数据提高准噶尔山楂识别精度，本次研究选择成像时间为2019年8月的GF-6WFV数据和同期的ZY-3号全色及多光谱数据。借助高空间分辨率的ZY-3号数据实现超像素分割和纹理特征提取，利用光谱通道更为丰富的GF-6WFV数据提取光谱和植被指数特征。遥感数据具体参数如表1所示。

![](images/423eddfde47b00b96d286dbf99017a7909d975fe7f50c27a629ba68abf220a6d.jpg)  
图1研究区位置  
Fig.1 Location of study area

表1GF-6WFV及ZY-3数据参数 Tab.1 GF-6WFV and ZY-3 data parameters   

<html><body><table><tr><td>数据类型</td><td>成像时间</td><td>波段名</td><td>波长 范围/μm</td><td>空间 分辨率/m</td></tr><tr><td>GF-6WFV</td><td>2019-08-06</td><td>蓝波段</td><td>0.45~0.52</td><td>16.0</td></tr><tr><td></td><td></td><td>绿波段</td><td>0.52~0.59</td><td></td></tr><tr><td></td><td></td><td>红波段</td><td>0.63~0.69</td><td></td></tr><tr><td></td><td></td><td>近红外</td><td>0.77~0.89</td><td></td></tr><tr><td></td><td></td><td>红边波段1</td><td>0.69~0.73</td><td></td></tr><tr><td></td><td></td><td>红边波段2</td><td>0.73~0.77</td><td></td></tr><tr><td></td><td></td><td>紫波段</td><td>0.40~0.45</td><td></td></tr><tr><td>ZY-3</td><td></td><td>黄波段</td><td>0.59~0.63</td><td></td></tr><tr><td></td><td>2019-07-24</td><td>蓝波段</td><td>0.45~0.52</td><td>6.0</td></tr><tr><td></td><td></td><td>绿波段</td><td>0.52~0.59</td><td></td></tr><tr><td></td><td></td><td>红波段</td><td>0.63~0.69</td><td></td></tr><tr><td></td><td></td><td>近红外</td><td>0.77~0.89</td><td></td></tr><tr><td></td><td></td><td>全色波段</td><td>0.50~0.80</td><td>2.1</td></tr></table></body></html>

影像预处理主要包含以下部分，首先利用中国资源卫星应用中心提供的定标参数对GF-6和ZY-3数据进行辐射定标，使用FLAAH方法对二者进行大气校正，结合数字高程模型(digitalelevationmodel,DEM)和几何成像模型参数文件(rationalpolynomialcoefficient,RPC)对二者进行几何精准校正，保证均方根误差控制在1个像元以内，消除地形对影像的影响，实现二者的空间配准。然后使用G-S算法(Gram-Schmidt Spectral Sharpening)将ZY-3号全色和多光谱数据进行融合，并使用主成分分析方法(principal componentanalysis,PCA）对融合后 ZY-3数据进行信息压缩，将可用信息集中到第一主成分中，用于后续纹理特征提取及图像分割。

# 2.2样本集的构建与划分

为合理构建训练与验证样本集，保证分类器构建的精度和后续精度验证的可靠性，将一类森林清查数据和野外调查数据作为辅助数据参与样本构建。其中一类清查数据为霍城县林业部门在2013年第八次森林资源清查数据的基础上逐年更新获得，野外调查数据于2019年8—9月野外调查获得。考虑到一类森林清查数据是以小班为单位，记录小班内的主要树种，相对于遥感影像而言，尺度较大，而野外调查点数量有限，仅依靠野外调查点构建样本，在训练时会因样本不足导致过拟合。为了保证样本分布均匀且具有足够代表性，将研究区均匀划分为3025个长宽为 $1 8 2 \mathrm { m } { \times } 1 7 0 \mathrm { m }$ 的规格矩形区域。参照外业调查数据和林业局提供的森林资源清查数据，结合面向对象分割结果，进行叠置分析。在每个矩形区域内尽可能的选择出一个面积不小于 $9 0 0 \mathrm { m } ^ { 2 }$ ,同时地类足够单一的样本点。考虑到可及性和样本设置的科学性，最终选择出样本2517个，其中，准噶尔山楂样本1029个、草地样本638个、裸地样本691个和其他林地样本159个。按照等比随机分割的方式，将各类样本划分为5份，其中3份用于分类器的训练，1份用于特征优选和分类器参数选择时的交叉验证，1份用于最后分类结果的精度验证。

# 3试验方法

# 3.1面向对象多尺度分割

传统的基于像元进行影像信息提取，运行效率较低且易产生“椒盐现象”。同时，在不同尺度的分类特征进行融合时，像元级的融合需要对数据进行重采样，统一像元尺度，这就不可避免的造成信息的丢失或者是运算力的浪费。为有效的解决上述问题，本文采取面向对象多尺度分割的方式，通过试错法选择最优尺度进行分割，在对象层面上实现分类特征融合和准噶尔山楂识别。

线性谱聚类算法(linear spectral clustering,LSC)是基于归一化切割(normalizedcut,NC)改进的新型分割算法。该方法使用内核相似度来度量函数，在像素高维特征空间内，通过加权K-means度量目标函数，达到归一化分割的目的[15]。LSC能够有效避免相关联矩阵的分解，具有较高的内存效率和较低的运算复杂性。其中加权K-means度量定义如下：

$$
F _ { \mathrm { { K - m } } } = { \sum _ { k = 1 } ^ { K } \sum _ { p } w ( p ) \left\| \phi ( p ) - d _ { k } \right\| ^ { 2 } }
$$

式中： $w ( p )$ 为像元 $p$ 在高维空间中的权重; $d _ { k }$ 为聚类中心点; $\phi ( p )$ 为颜色和空间坐标构成的空间多维向量空间特征; $\mathrm { K } { \cdot } \mathrm { m }$ 是K-mean的缩写； $k$ 为聚类中心序号； $K$ 为聚类中心总数。

考虑到林地结构复杂、边界不清晰等特点，本文以一类清查数据和实地调查数据为参考，利用试错法确定最佳分割尺度。为了保证分割对象内具有足够的纯净度，采用过分割策略，即在分割对象内部无明显混合地类后，再将分割尺度调小5。最终确定分割尺度为50,形状因子为0.6，紧致度为0.3。如图2所示，通过试错法和过分割方式得到的分割对象能够有效的对不同地物进行区分。

# 3.2多分类特征提取

为充分融合不同传感器数据的优势特征，利用GF-6WFV数据提取光谱特征与植被指数特征，利用经过融合和主成分分析后的ZY-3号数据进行纹理特征提取，共提取分类特征71个。在面向对象分割的基础上提取光谱特征包括GF-6WFV号数据8个波段的亮度值(Brightness,BN）、对象特征最大像元值(maximum pixel value,MAX）最小像元值(min-imumpixel value，MIN）和像元偏度（skewness,SKE)。利用波段计算工具和GF-6WFV数据提取7种植被指数特征：归一化植被指数(normalizeddif-ferencevegetationindex,NDVI）、比值植被指数(ratiovegetation index,RVI）、差值植被指数(difference veg-etation index,DVI）、红边指数(vogelmann red edge in-dex,VRE）、光化学植被指数（photochemical reflec-tance index,PRI)和两种花青素反射指数(anthocyan-in reflectance index,ARI)。使用灰度共生矩阵（gray-level co-occurrence matrix,GLCM)和PCA后的 ZY-3数据提取4个方向的8种纹理特征：熵(entropy,ENT）、均值(mean,MEA）、方差(variance,VAR）、对比度（contrast,CON）、均匀性（homogeneity,HOM）、角二阶矩（second Moment,ASM）、相关性（correla-tion,COR)和相异性(dissimilarity,DIS）。研究共提取32种光谱特征、7种植被指数特征和32种纹理特征，为消除特征量级对评价和分类结果的影响，采用最大最小值归一化的方式对各类特征进行归一化处理。另外，需要说明的是经过试错法发现纹理特征提取窗口大小为 $7 { \times } 7$ 时，能够有效避免林分冠层和阴影的影响，提高准噶尔山楂识别精度，故将纹理提取窗口设置为 $7 { \times } 7$ 。各植被指数特征计算公式及表征含义如表2所示。

# 3.3分类特征优选与评价

为了降低特征间的相关性，减少冗余，使用特征递归消除法(recursive feature elimination,RFE)进行特征集的优选，并基于随机森林模型，通过平均纯度减少(mean decrease impurity,MDI)对特征的重要性进行排序和分析。

RFE作为一种用于特征优选的算法，该算法可以通过迭代的移除特征变量和循环反复的建模达到剔除贡献较低的特征，达到筛选最佳分类特征的目的。本文利用scikit-learn内嵌模块进行特征消除和交叉验证(图3)。由图3可以看出，总体上通过RFE筛选的特征数量与分类总体精度具有较强的相关性。最初，随着参与分类的特征数量增加，分类精度呈现出正向响应，分类总体精度不断升高；特征数量达到15个时，总体精度提升速度达到最大，增加速度开始减缓;最后，当参与分类特征数量达到21个时，分类总体精度达到最大值 $9 6 . 8 \%$ ，总体精度不再提升，并开始出现震荡。据此，本文将利用这21个特征因子构建最优特征集。

为了更好的探究特征因子对准噶尔山楂识别结果的影响，基于RF模型利用MDI对优选特征的重要性进行评价，该值越大特征越重要。特征重要性评价结果如图4所示，其中光谱特征来自GF-6WFV的8个波段，其后缀表示提取该特征的波段，如 $\mathrm { B N \_ x }$ 表示波段x的亮度值。纹理特征来自融合、降维后的ZY-3数据，其后缀代表纹理特征提取的

![](images/b4387eb833591fe9f4e8684a9fe4d8e9c1e94f0d81adcbe0811aa2b36872027b.jpg)  
图2面向对象分割结果(局部)  
Fig.2Object-oriented segmentation results(local)

# 表2植被指数概览

Tab.2Tableofvegetation index   

<html><body><table><tr><td>植被指数</td><td>计算公式</td><td>表征意义及取值范围</td></tr><tr><td>NDVI</td><td>(PNIR−PRED)/(PIR +PRED)</td><td>表征植被绿地，植被茂密时其灵敏度会降低;取值范围-1~1，一般植被范围是0.2~0.8</td></tr><tr><td>RVI</td><td>P NIR/PRED</td><td>大气敏感,在植被茂密时分辨力更强;取值范围0~30+，一般植被范围2~8</td></tr><tr><td>DVI</td><td>PNIR−PRED</td><td>土壤敏感，在植被相对稀疏时，表征能力更强;取值范围量级差异较大</td></tr><tr><td>VRE</td><td>P740/P720</td><td>对叶绿素浓度、叶冠层和水分含量的综合灵敏;取值范围0~20，一般植被范围4~8</td></tr><tr><td>PRI</td><td>(p531−P570)/(ρ531 + P570)</td><td>对活林木的类胡萝卜素变化反应灵敏;取值范围-1~1，一般植被区范围-0.2~0.2</td></tr><tr><td>ARI1</td><td>1/p550-1/p700</td><td>对叶片中的花青素非常敏感;取值范围0~0.2+，一般植被范围0.001~0.1</td></tr><tr><td>ARI2</td><td>Ps00×X(1/p550-1/p700)</td><td>ARI2 是ARI1的改进,在高花青素浓度时更加有效;取值范围0~0.2+,一般植被范围0.001~0.1</td></tr></table></body></html>

注： $\rho _ { { } _ { x } }$ 代表波长 $x$ 处植被的反射率。

![](images/0a1c82139659af197238931b9e168550a3e0525adad7ae2964eb0cd30d675975.jpg)  
图3分类精度与特征优选关系

![](images/837f7a24be5ed61f7baeea972ee5a925781c2af16124de6853642e29ef6cef81.jpg)  
Fig.3 Relationship between classification accuracy and feature optimization   
图4优选特征重要性评价  
Fig.4Importance evaluation of preferred features

角度，如ASM_y表示y角度方向上的角二阶矩。可以看出：通过特征优选的21个分类特征中，光谱特征有10个，重要性从低到高排序为：BN_3、SKE_6、BN_5、BN_4、BN_2、SKE_3、BN_1、BN_6、MAX_5和MIN_4;植被指数特征5个，分别是NDVI、DVI、RVI、ARI2和PRI;纹理特征6个，按重要性排序为：MEA_0、ASM_45、ENT_0、COR_0、HOM_90和DIS_0。在光谱特征中，第3、4、5、6波段所提取的特征因子对于树种识别更加重要，而在纹理特征中， $0 ^ { \circ }$ 方向上提取的各类特征表现更加优越。植被指数特征在分类中尤为重要，本文提取的7种植被指数特征，5种进入优选特征集，NDVI更是各类特征中最为重要的分类特征。

# 3.4分类器及分类方案构建

针对单一分类器在不同场景下表现能力差异化的问题，使用被大量研究证明识别性能良好且稳定的SVM和RF分类器进行准噶尔山楂的识别，并基于二者构建权重自适应的组合投票分类器(weightedadaptivevotingcombinationclassifier,WAVCC)。SVM的学习策略就是间隔最大化，可形式化为一个求解凸二次规划的问题，在解决小样本、非线性及高维模式识别中表现出良好的性能。本文SVM核函数为径向基核函数。RF以决策树为基础分类器进行集成，比单个决策树更加稳定，泛化性能更好。RF的随机特性使得其具有优秀的降噪能力，不易陷入过拟合，几乎不需要人工干预，且基于对比计算进行树种分类使得算法运算效率相对较高。基于最优特征集和网络搜索验证对SVM和RF模型的参数进行优化，最后确定SVM模型样本影响半径倒数 $\mathrm { \ g a m m a } { = } 0 . 0 0 5$ ,惩罚因子 $\mathrm { C } { = } 1 5 0 0$ RF模型特征数 $\mathbf { m }$ 设置为3,决策树数量 $N { = } 4 0 0$ ○

对SVM和RF模型的分类结果进行精度验证，将用户精度和制图精度的均值作为算法对地物的识别精度，该精度作为该算法对此类地物识别权重。算法对地物识别归属拥有1乘以该方法对这一地物识别权重分的投票权，结合SVM和RF识别算法结果并行的方式对研究区树种分布进行组合投票以确定研究区树种识别最后结果。组合方法和

投票组合规则公式如下：

$$
\begin{array} { r } { e ( X ) = \left\{ { \begin{array} { c } { P _ { k } \big ( X \in C _ { j } \big ) , e _ { k } \big ( x \big ) = j \boxplus j \in \Lambda } \\ { 0 , \bigoplus } \end{array} } \right. } \end{array}
$$

$$
e ( X ) = \left\{ \begin{array} { l l } { j , \displaystyle \sum T _ { K } \Bigl ( X \in C _ { j } \Bigr ) = \operatorname* { m a x } \sum T _ { K } \bigl ( X \in C _ { i } \bigr ) } \\ { M + 1 , \not \exists \not \in / \Psi } \end{array} \right.
$$

式(2)和式(3)分别为投票组合方法和改进后投票组合规则，对于输入的 $X$ 分类，分类器 $\boldsymbol { e } _ { \boldsymbol { k } }$ 输出的投票分数为 $\boldsymbol { P } _ { \boldsymbol { k } }$ ,即用户精度与制图精度的平均数； $C _ { j }$ 表示影像内是 $j$ 的对象; $T _ { \kappa } \Big ( X \in C _ { j } \Big )$ 表示类别$C _ { j }$ 经过分类器 $C _ { j }$ 输出后得到的分数； $M$ 为类别总数， $M + 1$ 表示分类器拒绝识别 $X$ □

为了更好的评价面向对象分割方法、特征优选和权重自适应的多分类器组合算法对分类结果的影响，同时探究不同特征因子与准噶尔山楂识别精度之间的响应关系，按照控制变量的方式设置了7种分类方案(表3)。通过对比方案1和方案2的识别结果，分析特征优化对准噶尔山楂识别的影响。比较方案1和方案3的识别精度，研究对象尺度与像元尺度准噶尔山楂识别的差异。通过方案1、方案4和方案5的对比，验证权重自适应的多分类器组合算法的性能。对比方案1、方案6和方案7准噶尔山楂识别的精度，探究不同特征因子对识别精度的影响。

# 表3分类方案

Tab.3 Classification schemes   

<html><body><table><tr><td>分类方案</td><td>分类特征因子</td><td>分类算法</td><td>是否分割</td></tr><tr><td>方案1</td><td>优化全部特征(21)</td><td>WAVCC</td><td>是</td></tr><tr><td>方案2</td><td>未优选全部特征(71)</td><td>WAVCC</td><td>是</td></tr><tr><td>方案3</td><td>优化后像元尺度特征(17)</td><td>WAVCC</td><td>否</td></tr><tr><td>方案4</td><td>优化后全部特征(21)</td><td>SVM</td><td>是</td></tr><tr><td>方案5</td><td>优化后全部特征(21)</td><td>RF</td><td>是</td></tr><tr><td>方案6</td><td>优化光谱特征+优化纹理特征(16)</td><td>WAVCC</td><td>是</td></tr><tr><td>方案7</td><td>优化光谱特征+优化植被指数特征(15)</td><td>WAVCC</td><td>是</td></tr></table></body></html>

# 4结果与分析

基于上述7种分类方案和预留的验证样本集，利用混淆矩阵计算各分类方案制图精度(produceraccuracy,PA）用户精度（user accuracy,UA）、总体精度(overall accuracy,OA)和Kappa系数4个精度衡量指标对分类结果进行评判。

# 4.1特征优化和组合对识别的影响

在识别算法和计算器硬件保持一致的前提下，根据各方案对准噶尔山楂进行识别和精度验证，同时记录分类耗时(elapsedtime,ET)（表4)，其中UA和PA均是指准噶尔山楂精度，OA和Kappa系数则是指整个分类系统的精度。对比方案1和方案2可以看出：使用优化后特征集的方案2相较于方案1虽然在0A上略低 $0 . 0 2 \%$ ,但是具体到准噶尔山楂的识别上，方案1的UA和OA都要显著高于方案2。另外，方案1的Kappa系数显著高于方案2,说明方案1的随机性更低，性能更加稳定。在运算时间上，未通过特征选择的方案2的运算耗时是方案1的

# 表4分类方案评价

Tab.4 Evaluation of classification schemes   

<html><body><table><tr><td>分类方案</td><td>0A/%</td><td>Kappa</td><td>UA/%</td><td>PA/%</td><td>ET/min</td></tr><tr><td>方案1</td><td>95.27</td><td>0.92</td><td>93.85</td><td>94.72</td><td>17.0</td></tr><tr><td>方案2</td><td>95.29</td><td>0.71</td><td>90.33</td><td>94.51</td><td>38.8</td></tr><tr><td>方案3</td><td>92.43</td><td>0.88</td><td>89.41</td><td>86.99</td><td>30.4</td></tr><tr><td>方案4</td><td>93.46</td><td>0.76</td><td>92.72</td><td>89.96</td><td>9.4</td></tr><tr><td>方案5</td><td>91.96</td><td>0.81</td><td>88.86</td><td>91.21</td><td>5.7</td></tr><tr><td>方案6</td><td>87.34</td><td>0.91</td><td>87.33</td><td>87.10</td><td>12.9</td></tr><tr><td>方案7</td><td>90.59</td><td>0.83</td><td>91.22</td><td>89.57</td><td>11.3</td></tr></table></body></html>

2.28倍。通过RFE进行特征选择可以在保证识别精度的前提下，有效的降低运算量，提升分类器的稳定性。

对比方案1、方案6和方案7，探究不同特征组合与识别精度之间的响应关系。可以看出：光谱、纹理和植被指数特征联合进行分类取得最高的识别精度，多特征的联合能够有效的提高准噶尔山楂识别的准确率，但是随着参与分类的特征因子变多,算法耗时也会相应增加。方案7除Kappa系数略低于方案6，在其他各个衡量指标上相较于方案6都具有优势，这说明纹理特征和植被指数特征都能有效提高准噶尔山楂的识别精度，且植被指数特征对准噶尔山楂识别精度提升的贡献要大于纹理特征。

# 4.2面向对象分割对识别的影响

通过对比方案1和方案3的识别精度和运算耗时，对基于像元和基于对象2种分类方法在准噶尔山楂识别上性能的差异进行评价。在这里需要说明的是，因为MAX、MIN和SKE三类光谱特征只存在于对象尺度，在像元层次不存在这三类特征，所以方案3中参与分类的特征因子相较于方案1少了

4个，另外，此处的运算耗时仅指依靠WAVCC算法进行分类所需的识别，不包括基于像元分类前期需要做的重采样和融合等操作(表4和图5)。从结果可以看出：相较于方案1,基于像元的识别方案出现明显的“椒盐现象”，识别结果出现十分破碎的像元块，整体性较差，导致其各类精度衡量指标都显著低于基于对象分类。同时，因为WAVCC分类算法需要在单一分类器识别的基础上逐一单元的进行投票判定，同一区域数据像元数量远高于分割对象数量，导致基于像元的WAVCC算法在耗时上也明显高于基于对象的算法。

![](images/c4169a17cafeeca2da5972d3720e3be8ff8afc657e5f1599d808fb156141aeea.jpg)  
Fig.5Importance evaluation of preferred features

# 4.3多分类算法联合对识别的影响

单一分类器在进行识别分类时，因分类算法机理和性能的差异，对不同分类对象表征能力不同，难免会造成一定的误差。为了尽可能的避免上述问题的出现，提高准噶尔山楂识别精度，本文基于自适应权重投票将RF和SVM算法进行组合得到了WAVCC分类算法。如表4和图6所示，对比方案1、方案4和方案5可以看出，联合RF和SVM算法的WAVCC分类算法在各项精度评价指标上都要显著优于单一分类器算法，这表明该分类器能够很好的集成RF和SVM分类器的优点，抵消一部分单一分类器表征能力不足带来的误差，提高分类算法的精度和稳定性。当然，因为WAVCC识别结果是在RF和SVM识别和精度验证的基础上，按照投票权重对分类单元逐一计算权重得来的，所以在运算耗时上要高于单一分类器耗时。

![](images/8d63e2cd7561a408ecd916f47d787174a9543de11a9058ba94422665c47d3449.jpg)  
图5不同层次分类对比  
图6不同分类算法精度对比 Fig.6 Accuracy comparison of different classification algorithms

# 5结论

本文利用面向对象分割、多源特征提取、特征递归消减和分类器组合等方法对多特征因子辅助的GF-6WFV数据准噶尔山楂识别问题开展一系列研究，探究分类尺度、特征选择、特征组合和分类算法等因素对准噶尔山楂识别影响，得到以下结论：

（1）利用GF-6WFV数据能够很好的识别准噶尔山楂，GF-6WFV数据在林业生产中具有很大的应用潜力。在GF-6WFV影像参与的各分类方案中，无论是何种分类算法和特征组合，是否进行面向对象分割和特征优选，识别结果的OA均大于$87 \%$ ,Kappa系数优于0.7，证明GF-6WFV数据可以用于准噶尔山楂空间分布信息提取，且具有一定优势。

(2）GF-6WFV相较于GF-1WFV新增的2个红边波段对准噶尔山楂的识别具有重要作用。特征优选能够有效降低分类特征间的冗余，提高运算效率和算法的稳定性。选择后的特征对准噶尔山楂识别的精度具有显著的提升作用，其中植被指数特征的提升作用大于纹理特征，

（3）基于对象进行准噶尔山楂识别相较于传统基于像元的方式，能够有效解决“椒盐现象”，显著提高识别精度、算法运行效率和鲁棒性。基于对象进行分类识别将算法OA、UA和PA分别提高了$2 . 8 6 \% . 4 . 4 4 \%$ 和 $7 . 7 3 \%$ ,Kappa系数提升了0.04，而运行时间较少了近 $8 0 \%$ 。

（4）权重自适应的多分类器投票组合算法能够综合不同算法的优势，有效规避单一分类器地物类型表征力差异造成的部分“混淆”，提高识别精度。联合2种分类器的WAVCC算法相较于单一的SVM和RF算法识别的总体精度和Kappa系数分别提升了 $1 . 8 1 \% . 3 . 3 1 \%$ 和0.16、0.11。

# 参考文献(References):

[1]杨蕾,吕海英,李进,等.新疆天山野果林准噶尔山楂种群结构 与动态分析[J].西北植物学报,2018,38(12):2314-2323.[Yang Lei,Lyu Haiying,Li Jin,et al. Structure and dynamic analysis of Crataegus songarica K.Koch population in Tianshan wild fruit forest of Xinjiang[J].Acta Botanica Boreali-Occidentalia Sinica, 2018, 38(12): 2314-2323.]   
[2] 盛芳,陈淑英,田嘉,等.新疆准噶尔山楂不同居群的遗传多样 性[J].生物多样性,2017,25(5):518-530.[Sheng Fang,Chen Shuying,Tian Jia,et al.Genetic diversity of Crataegus songorica in Xinjiang[J]. Biodiversity Science,2017,25(5):518-530.]   
[3] 邬亚娟,刘廷玺,童新,等.基于面向对象的干旱半干旱地区植 被分类[J].干旱区研究,2020,37(4):1026-1034.[Wu Yajuan, Liu Tingxi,Tong Xin,et al.Vegetation classification in arid and semi-arid areas based on object-oriented method[J].Arid Zone Research,2020,37(4): 1026-1034.]   
[4]樊雪,刘清旺,谭炳香.基于机载PHII高光谱数据的森林优势 树种分类研究[J].国土资源遥感,2017,29(2):110-116.[Fan Xu, Liu Qingwang,Tan Bingxiang. Classification of forest species using airborne PHII hyperspectral data[J]. Remote Sensing for Land and Resources, 2017, 29(2): 110-116.] [5]赵希妮,王磊,刘雅清,等.基于GF-1/WFV时间序列的葡萄识 别模型——以宁夏红寺堡区为例[J].干旱区研究,2019,36(3):   
630-638.[Zhao Xini,Wang Lei,Liu Yaqing,etal. Grape recognition model based on GF-1/ WFV time series: A case study of hongsipao District, Ningxia[J]. Arid Zone Research,2019,36(3):   
630-638.] [6]Koukal T,Atzberger C,Schneider W.Evaluation of semi-empirical BRDF models inverted against multi-angle data from a digital airborneframecamera for enhaning forest typeclassfication[J]Re mote Sensing of Environment, 2014,151: 27-43. [7]Yang X H,Rochdi N, Zhang JK, et al. Mapping tree species in a boreal forest area using RapidEye and Lidar data[J]. Internatioal Geoscience and Remote Sensing Symposium, 2014: 69-71. [8]Yuan Q Q,Shen HF,Li TW,et al. Deep learning in environmentalremote sensing: Achievementsandchallnges[J]. Rmote Sens ing of Environment, 2020,241: 111716. [9] 栗旭升,李虎,陈冬花,等.联合GF-5与GF-6卫星数据的多分 类器组合亚热带树种识别[J].林业科学,2020,56(10):93-104 [Li Xusheng,Li Hu, Chen Donghua, etal. Multiple classifiers combination method for tree species identification based on GF-5 and GF-6[J]. Scientia Silvae Sinicae,2020,56(10): 93-104.] [10] 王怀警,谭炳香,王晓慧,等.多分类器组合森林类型精细分类 [J].遥感信息,2019,34(2):107-115.[Wang Huaijing,Tan Binxiang,Wang Xiaohui,et al.Multiple classifiers combination methodforpreciseclaificationofforest type[J]. RemoteSensing Information, 34(2): 107-115.] [11] 刘怡君,庞勇,廖声熙,等.机载LiDAR和高光谱融合实现普洱 山区树种分类[J].林业科学研究,29(3):407-412.[Liu Yijun, Pang Yng,Liao Shengxi, et al. Merged airborne LiDARand hyperspectral data for tree species clasification in puer's mountainous area[J].ForestResearch,2016,29(3): 407-412.] [12] 刘丽娟,庞勇,范文义,等.机载LiDAR 和高光谱融合实现温带 天然林树种识别[J].遥感学报,2013,17(3):679-695.[Liu Lijuan,Pang Yong,Fan Wenyi, etal.Fused airborne LiDAR and hyperspectral data for tree species identification in a natural temperate forest[J]. Journal of Remote Sensing,2013,17(3): 679-695.] [13] 刘雅清,王磊,赵希妮,等.基于GF-1/WFV时间序列的绿洲作 物类型提取[J].干旱区研究,2019,36(3):781-789.[LiuYaqing Wang Lei, Zhao Xini,et al.Extraction of crops in oasis based on GF-1/WFV time series[J].Arid Zone Research,2019,36(3): 781-   
789.] [14] 李利平,海鹰,安尼瓦尔·买买提,等.新疆伊犁地区野果林的群 落特征及保护[J].干旱区研究,2011,28(1): 60-66.[Li Liping, Hai Ying,Anwar Mohammat, et al. Community structure and con servation of wild fruit forests in theIi Valley,Xinjiang[J].Arid Zone Research,2011, 28(1): 60-66.]

# Crataegus songarica recognition using Gaofen-6 wide-field-view data assisted by multiple features

CHEN Chunxiu'²， CHEN Shujiang1²， XU Shiwei， CHEN Mengyu4, JIA Xiang'， HUANG Tiecheng'， LI Chunlei5   
(1. College of Geography and Tourism, Xinjiang Normal University,Urumqi 830054,Xinjiang, China;   
2. Urumqi Institute of Spatial Remote Sensing Applications, Urumqi 830o54,Xinjiang, China; 3.Emin   
County Bureau of Natural Resources,Tarbagatay 8346Oo, Xinjiang, China; 4.Forestry Institute, Beijing   
Forestry University,Beijing 1OOo83,China; 5.Institute of Forest Ecological Environment and Protection, Chinese Academy of Forestry Sciences,Beijing 100091, China)

Abstract: Our ability to extract spatial distribution information for Crataegus songarica by remote sensing is relatively weak,and the performanceof a single algorithm in information extraction is diferent.To address this problem,we explored the application potential of domestic Gaofen-6(GF-6) wide-field-view (WFV) data in tree species recognition in arid and semi-arid areas.Using GF-6 WFVand Ziyuan-3 (ZY-3) data,we constructed a combined clasifier recognition algorithm with multi-feature assistance.First，we combined a linear spectral clustering algorithm for ZY-3 data super-pixel segmentation with the sample set to determine the optimal scale, avoid the salt-and-pepper phenomenon and improve the recognition accuracy. Second,we extracted spectral features,texture features,and vegetation index features based on multi-source data,using the recursive feature elimination method to select classfication features.Feature importance was evaluated based on the mean decrease impurity to construct the optimal classification feature set, improve the separability between feature classes，and reduce the redundancy between features. Finaly， we constructed a weight- adaptive voting combination clasifier based on the support vector machine algorithm and random forest algorithm. Combined with a variety of classification schemes，the spatial distribution of Crataegus songarica was extracted and verified to evaluatethe influenceof object-orientedalgorithm, multi-classifier combination algorithm,and feature selection on the classification accuracy.The results showed that GF-6 WFV data can be used to identify Crataegus songarica and have great application potential in forestry production. Compared with GF-1 WFV, two new red-edge bands of GF-6 WFV play an important role in the identification of Crataegus songarica. Compared with traditional pixel-based methods,the object-based recognition of Crataegus songarica effectively mitigated the pepper salt phenomenon and significantly improved the recognition accuracy,algorithm effciency, androbustness.Moreover,the feature selection effectively reduced the redundancy between clasification features and improved the computational efciency and algorithm stability;the selected features significantly improved the accuracy. Using a weight-adaptive multi-clasifier voting combination algorithm can integrate the advantages of different algorithms,effectively avoid the partial ‘confusion’ caused by the representation force difference of the single classfier, and improve the recognition accuracy.

Keywords: GF-6； feature selection; object-oriented; multi classifier combination; Crataerus songarica