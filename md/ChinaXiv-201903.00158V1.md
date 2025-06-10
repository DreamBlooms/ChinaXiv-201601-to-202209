# 分层分类和多指标结合的西北农牧交错带植被信息提取

何鸿杰'，穆亚超，魏宝成¹，杜婷¹，薛晓玉'，颉耀文1,2(1 兰州大学资源环境学院,甘肃兰州 730000；2 兰州大学西部环境教育部重点实验室,甘肃兰州 730000）

摘要：参照《中国植被》中的植被分类体系，结合野外考察结果,建立了适合中国西北农牧交错带的植被分类体系。以覆盖研究区的多幅Landsat影像为基础，按“分层分类，逐层验证”的思路，实现了对研究区植被信息的提取。提取时，先利用完全约束的最小二乘模型对遥感影像进行混合像元分解,将整个研究区划分为植被区和非植被区；在植被区，基于光谱特征、纹理特征和地形特征，构建CART决策树，获得了乔木林、灌丛和草原等7种主要植被型组;在植被型组内,基于不同植被类型NDVI的季节差异特征,构建NDVI差值比值指数（NDVI_DR)，将乔木林和灌丛区分为常绿和落叶植被型,使用温度植被干旱指数(TVDI),将草原划分为荒漠草原、典型草原和草甸草原3种类型,从而得到各个植被型的空间分布范围。经验证，最终分类的总体精度能达到 $7 9 . 5 1 \%$ ,kappa系数为0.773。本文所采用的分类方法充分利用了遥感数据既有的光谱信息和纹理信息，同时辅以地形信息。实践结果表明，分层分类和多种指标相结合的方法可以有效实现对影像跨幅的、以复杂镶嵌结构为主要特征的农牧交错带植被信息提取，精度较高，技术可行。

关键词：农牧交错区；植被信息提取；CART决策树；谱间关系法；差值比值指数(NDVI_DR)；温度植被干旱指数(TVDI)  
文章编号： 1000-6060(2019)02-0332-09(0332\~0340)

植被的研究一直以来都备受关注[1],因为掌握植被的分布特征有利于推动生态环境建设，协调区域可持续性发展。本文所选的研究区西北农牧交错带，常年降水较少、蒸发量大且植被稀疏，是典型的生态脆弱区。

在西北农牧交错带，由于地形和地貌的复杂性、气候的特殊性以及人类活动的影响，植被类型的变化极为复杂。以往的研究表明，对于西北农牧交错带这样的地表覆盖复杂区域，采用“分步骤，分层次，分类别”的方法能有效的提高最终的分类精度[2-5]。此外,主成分变换、缨帽变换（又称K-T 变换）、波段优选和一些常见的遥感指数的组合也可以提高分类精度[6-13]。KhatamiR等[14]发现纹理信息和多时相图像的使用能够改善分类的整体精度。遥感影像能够捕获植被生长变化中的一些生理特征和物候规律[15],而这些特征大多具有季节性,因此使用这些季节性变化的特征并结合多时相的遥感影像能够充分利用遥感影像反映出的特征完成植被信息提取[16]。在具体操作时,一般采用不同时相NDVI 的组合来提取植被的落叶和常绿信息[17]。上述遥感植被分类方法，多集中于植被覆盖度较高的区域，但是将以上方法结合起来用于西北农牧交错带植被信息提取的研究较少。

本文以遥感影像为主要数据源，探索出适合于地表覆盖复杂、植被稀疏区域的植被信息提取方法。本研究最终得到的西北农牧交错带的植被分布为深入分析该区域地表水热格局提供基础数据，为该区的生态保护提供理论支撑。

# 研究区概况与方法

# 1.1 研究区概况

农牧交错带是一种植被类型、气候特征和生产方式均具有过渡性的特殊地理区域。本文所研究的西北农牧交错带地理位置为 $1 0 5 ^ { \circ } 3 5 ^ { \prime } - 1 1 0 ^ { \circ } 5 4 ^ { \prime } \mathrm { E }$ ，$3 6 ^ { \circ } 4 9 ^ { \prime } - 4 0 ^ { \circ } 1 1 ^ { \prime } \mathrm { N }$ ，位于鄂尔多斯高原和毛乌素沙地区域(如图1），为干旱区和半干旱地区。西北农牧交错带具有典型的生态脆弱性，其南部为毛乌素沙地、北临库布其沙漠、西接乌兰布和沙漠。研究区海拔范围在 $6 4 0 \sim 2 ~ 0 6 0 ~ \mathrm { ~ m ~ }$ 之间，总体呈现出西高东低、南高北低的特点。研究区总面积约达 $8 \times 1 0 ^ { 4 }$ $ { \mathrm { k m } } ^ { 2 }$ ,包含内蒙古、宁夏、陕西的10个县（旗）。植被类型主要为适合干旱和半干旱环境的乔木、灌木和人工栽培植物。

# 1.2 分类体系

本文以《中国植被》中植被分类体系[18]为参考，充分利用可获取的研究区其他相关资料和多次实地考察所获取的数据制定了相对合适的分类体系。其中考虑了以下原则：

（1）以优势种为主：植被类型特征的分类标准由植物群落中的优势种确定。对于本研究区，植被类型多为荒漠植被，不可能包含所有《中国植被》中提到的植被类型。因此将研究区内的植被亚型直接分为植被型,将研究区分布极少或无分布的类型不列入本分类体系。

（2）考虑动态特征：考虑植被的次生性质和演替关系，将部分植被型合并。例如，不再将灌草丛单独划分为一个植被型，而是将其纳入灌丛所属的植被型中。

（3）可操作性：多光谱遥感影像的空间分辨率与高分数据相比较低，其光谱分辨率与高光谱数据相比较低，因此使用多光谱遥感影像难以区分特征相近的植被类型。例如，针叶林和阔叶林在多光谱遥感影像上难以区分，因此将他们合并为乔木林。

![](images/bfb92cba44cc52e970241bb2ed3d15e2f0ee1f52f6b7c2145a9d380e046b5fae.jpg)  
图1研究区概况图  
Fig.1Location of study area

参考《中国植被》，将植被型组作为分类系统中的最高级别，将具有相似生活型和相似形态和外观的植物群落划分为相同的植被型组。植被型为最重要的分类级别，是在植被型组的基础上，根据植被的生活型和对水热条件的生态关系进一步划分的[18]最终建立的分类体系如表1所示。

表1西北农牧交错带植被分类体系  

<html><body><table><tr><td>植被型组</td><td>植被型</td></tr><tr><td>乔木林(A)</td><td>温性常绿针叶林(A1)</td></tr><tr><td>灌丛(C)</td><td>典型落叶阔叶林(A2) 常绿针叶灌丛(C1)</td></tr><tr><td rowspan="4">草原(D)</td><td>温性落叶阔叶灌丛（C2)</td></tr><tr><td></td></tr><tr><td>草甸草原(D1)</td></tr><tr><td>典型草原(D2)</td></tr><tr><td>荒漠(E)</td><td>荒漠草原(D3)</td></tr><tr><td></td><td>荒漠(E1)</td></tr><tr><td>草甸(H)</td><td>草甸(H1)</td></tr><tr><td>沼泽(I)</td><td>沼泽(I1)</td></tr><tr><td>农作物(K)</td><td>农作物(K1)</td></tr></table></body></html>

# 1.3 数据源

本文在多光谱遥感影像Landsat8OLI数据的基础上，使用地形数据DEM提供分类所用的辅助信息。实地考察和高清影像数据用于辅助采集分类用的样本点。此外，道路、行政区划数据等研究区域的基础数据主要用于制图。

Landsat8OLI数据下载于USGS官网（http：//glovis.usgs.gov/）。为了提取乔木林和灌丛的常绿和落叶信息，本文选取研究区内植被的生长季和非生长季内质量较高的影像各一期，影像信息见表2。本文基于ENVI5.1软件对卫星影像数据进行辐射定标、大气校正等预处理以获取真实地物的反射率信息。

$3 0 \mathrm { m }$ 的DEM数据下载于地理空间数据云平台（http：//www.gscloud.cn/）。对数据进行拼接、投影和裁剪后获得研究区的DEM数据。通过对研究区的多次野外实地调查，在积累了先验知识的同时获取了大量的样本点。这些样本点结合google高清影像可以提供足够的样本点用于影像分类和精度验证。

# 表2遥感影像信息表

Tab.1Vegetation classification system in agro-pasturage ecotone of northwest China   
Tab.2Table of image information   

<html><body><table><tr><td>轨道号</td><td>成像日期</td><td>云量／%</td><td>平均海拔／m</td></tr><tr><td>127/33</td><td>2016/03/13</td><td>0.09</td><td>1 234</td></tr><tr><td rowspan="3">127/34</td><td>2015/07/01</td><td>0.02</td><td></td></tr><tr><td>2016/02/26</td><td>0.09</td><td>1 172</td></tr><tr><td>2015/07/01</td><td>0.01</td><td></td></tr><tr><td rowspan="2">128/33</td><td>2015/02/14</td><td>0.37</td><td>1338</td></tr><tr><td>2016/08/27</td><td>0.84</td><td></td></tr><tr><td rowspan="2">128/34</td><td>2015/02/14</td><td>0.27</td><td>1 412</td></tr><tr><td>2016/08/27</td><td>0.01</td><td></td></tr><tr><td rowspan="2">129/32</td><td>2015/03/09</td><td>0.35</td><td>1 251</td></tr><tr><td>2015/09/01</td><td>0.1</td><td></td></tr><tr><td rowspan="2">129/33</td><td>2015/03/09</td><td>0.25</td><td>1 343</td></tr><tr><td>2015/09/01</td><td>0.08</td><td></td></tr><tr><td rowspan="2">129/34</td><td>2016/03/11</td><td>0.47</td><td>1 483</td></tr><tr><td>2015/09/01</td><td>0.27</td><td></td></tr></table></body></html>

# 1.4基于遥感的植被信息提取方法

西北农牧交错带土地覆被情况较为复杂，使用一般的分类方法难以取得较好的分类结果。因此,本文采用“分层分类、逐层验证”的方法提取植被信息。首先，由于混合像元分解模型可以有效且准确的提取植被覆盖度[19],据此可以将遥感影像分为植被区域与非植被区域;其次，利用CART决策树结构清晰且准确性高[20]的优势,将植被区域进一步分类为植被型组;最后，通过创建NDVI差值比值（NDVI_DR)指数对类别比较复杂的乔木林和灌丛进一步细分，得到其落叶和常绿特征，并通过使用TVDI值对草原进行了分类，得到了三种草原类型，最终获得本研究区的植被信息提取结果。图2所示为本文采用的技术路线。

![](images/27733583b742fd4407ef28cddd086be071dafb585f79be1c84ef59f0ace5ea2f.jpg)  
图2技术路线  
Fig.2Technical route of the study

# 2 植被信息的提取

# 2.1植被覆盖区域的提取

植被覆盖度是评判地表植被覆盖状况的重要指标之一，因此也常被用于区分植被与非植被区。本文选取线性光谱混合模型进行混合像元分解以获取研究区植被覆盖度信息。该模型一般包括以下几个步骤：MNF变换、端元选取与提纯和混合像元分解。

这里使用完全约束最小二乘法模型进行混合像元分解，这一过程可以通过加载ENVI附加模块完成。对所得误差波段的值进行统计，可得大部分像元的误差都较小，以128/33为例，其平均误差为0.019。

由于研究区在西北干旱与半干旱区，植被盖度普遍偏低，一般盖度为 $5 \% \sim 2 0 \%$ 。因此，植被覆盖度大于 $5 \%$ 的区域均可认为是有植被覆盖区域（图3）。研究区总面积为 $8 6 ~ 4 5 3 . 4 4 ~ \mathrm { k m } ^ { 2 }$ ,植被覆盖区域总面积为 $7 1 ~ 4 5 0 . 7 2 ~ \mathrm { k m } ^ { 2 }$ 。在ArcGIS 软件中生成1000个随机点，并结合高清影像判定提取结果的精度。精度验证的结果显示，提取结果总精度为

![](images/67ad01929c481029d5ba4e88bfc44a98512798367a83ed421b087c9ff5570b44.jpg)  
图3研究区植被覆盖度分布图Fig.3Vegetation coverage in the study area

$9 3 . 5 \%$ ,Kappa系数为0.782,结果较为理想。

# 2.2 植被型组分类

2.2.1分类指标遥感分类的指标很多，使用多种指标能够有效提高分类精度，但是指标过多也可能导致数据冗余和过分类（过拟合）。因此，有必要选择合适的分类指标进行分类。不同的地物在各原始波段有不同的反射率差异，但是任一波段所包含的信息量不同，选取信息量最大的几个波段能够在保证分类精度的同时提高分类效率。在原始波段的基础上，结合一些辅助信息可以有效地提高分类精度。已有的研究主要用光谱特征、纹理特征和地形特征完成植被的分类。光谱特征主要考虑植被冠层的水分含量、地表覆被的水分含量以及常用的多种遥感分类和环境监测指数[21]。本文选取的光谱特征有波段优选后的原始波段、改进的归一化差异水体指数（Modified Normalized Difference Water Index,MNDWI）、归一化差异湿度指数（NormalizedDiffer-enceMoistureIndex,NDMI)以及缨帽变换、主成分变换后的结果以及植被指数NDVI（NormalizedDifferenceVegetationIndex）。地形特征有数字高程模型（DigitalElevationModel，DEM）,而纹理特征则选用均值(表3)。

研究表明[22]，影像的原始波段的标准差越大，相关系数越小，则影像的信息量越大。以影像 $12 8 /$ 33为例：NIR,SWIR1，SWIR2（分别为影像的第5，6，7波段)的标准差相对较大，其中，NIR与其他各波段的相关系数均较小，其次为SWIR1和SWIR2，而两个短波红外波段之间的相关系数较大。通过统计7大植被型组的各600个样本点，可知不同的植被型组在NIR和SWIR1的差异相对较大。因此，本文选取NIR和SWIR1作为用于分类的原始波段。

NDVI[23]、EVI（增强型植被指数,Enhanced Veg-etation Index）［24]、SAVI（土壤调节植被指数[25]，Soil-AdjustedVegetationIndex）、GEMI（全球环境监测指数,Global Environment Monitoring Index）[26]GRNDVI(绿光与红光波段归一化植被指数，GreenRed NDVI)[27]和 TDVI(转换型差值植被指数,Trans-formed difference vegetation index）[28]是从目前常用的遥感植被指数中选取的适合干旱与半干旱区的植被指数。通过比较分析，从这六个指数中选取合适的植被指数用于分类。定边县北部的一块区域（影像128/34)地表植被覆盖复杂，因此分别在该区域计算上述六个指标。结果显示NDVI在高植被覆盖

# 干吴区地理

# 表3分类指标

Tab.3Used indicesintheclassification   

<html><body><table><tr><td>特征</td><td>指标类型</td><td>分类指标</td><td>描述</td></tr><tr><td rowspan="6">光谱特征</td><td>原始波段</td><td>NIR,SWIR1</td><td>影像信息量最大且植被类型光谱差异较大</td></tr><tr><td>植被指数</td><td>NDVI</td><td>常用的植被指数中分类效果最好</td></tr><tr><td>水体指数</td><td>MNDWI</td><td>探测地表覆被水分含量</td></tr><tr><td>湿度指数</td><td>NDMI</td><td>研究植被冠层含水量</td></tr><tr><td>缨帽变换结果</td><td>Brightness, Greenness, Wetness</td><td>常用于遥感地物分类与遥感生态环境监测</td></tr><tr><td>主成分</td><td>PC1,PC2,PC3</td><td>减少影像冗余信息</td></tr><tr><td>纹理特征</td><td>纹理特征</td><td>Mean</td><td>各类地物的区分度最大</td></tr><tr><td>地形特征</td><td>数字高程模型</td><td>DEM</td><td>不同地形条件生长不同植被类型</td></tr></table></body></html>

区和低植被覆盖区的分类效果均好于其他几个。因此本文最终采用NDVI作为分类的指标。

将纹理特征与光谱特征相结合可以有效提高遥感分类的精度[29]。在研究区内选取试验区域（影像条带号为128/34），分别计算区域内的8种纹理指标（均值，方差，对比度，协同性，相异性，熵值，二阶矩,相关性)。8种指标中，均值、方差和对比度对应的标准差较大，但在均值的单波段影像中，不同植被型组呈现出不同的色调，即区分度较大。因此，最终选取均值(Mean)作为用于影像分类的纹理特征。

2.2.2植被型组分类样本点选取。每种植被类型均选取一定量的样本点，在选取样本点时需要考虑：（1）样本点要具有典型代表性，选取样本点时要考虑每个植被类型的各主要植物类型；（2）样本点应当均匀分布于整个研究区；（3）选择尽可能多的野外实地采样点（共693个点）。

统计汇总所有样本点的所有13个指标和类别信息，并将汇总结果导入Clementinel2.0软件中，生成分类CART决策树。在得到的影像127/33的分类决策树(图4)中可以看出上述13个指标并未全部用到。软件可以自动生成评价决策树的误差矩阵，结果显示其标准中误差为0.003。在ENVI软件中运行所得到的CART决策树，得到如图5所示的植被型组分类结果。

# 2.3 植被型的分类

2.3.1乔木林和灌丛分类自2015年8月起，项目组共对本研究区进行四次野外考察。在基本覆盖整个研究区的多次考察中，未见到常绿针叶林林地。即使研究区确实有少量常绿针叶林林地存在，也很难从 $3 0 \mathrm { ~ m ~ }$ 分辨率的Landsat多光谱数据中将其提取出来。

在单一时相的Landsat 影像上区分植被的落叶和常绿特征是非常困难的，但是由于落叶植被在其非生长季会落叶，在影像上的光谱信息变化较为明显。因此，可以使用多时相的影像来区分落叶植被和常绿植被。本文基于植被生长季(主要是夏季)和植被非生长季(主要是冬季)的影像，利用落叶植被和常绿植被在不同季节的NDVI的变化的差异完成两种植被类型的分类。两种类型的植被在生长季的NDVI值 $( N D V I _ { - } S )$ 均高于非生长季的NDVI值$( N D V I _ { - } W )$ ，而常绿植被在生长季和非生长季的NDVI值的差异较小，落叶植被的差异较大。基于以上特征,创建了NDVI差值比值植被（NDVI_DR)指数。这一指数的定义为：生长季的NDVI和非生长季的NDVI的差值和非生长季的NDVI的比值，即：

![](images/6d41b3946834aba095f7fe35c2faade41cf4ff2285387a7548454c8ad3565419.jpg)  
图4基于多指标参与的CART决策树  
Fig.4CART decision tree classification model based on multi-index participation

![](images/41e12b66ab4dd3b4feeeedf9ddd3246e1104c9125d4b0a82f796d784c1435107.jpg)  
图5研究区植被型组分类结果

$$
N D V I \_ D R = \frac { N D V I \_ S - N D V I \_ W } { N D V I \_ W }
$$

NDVI_DR可以很好地反映出NDVI在不同季节的变化强度。比较了样本点的 $N D V I _ { - } D R$ 和NDVI$W$ 之后，可以得到如下的乔木林分类规则：

$$
\left\{ { \begin{array} { l } { N D V I \_ D R > N D V I \_ W } } \\ { N D V I \_ D R \leqslant N D V I \_ W }  \end{array}  \right.
$$

通过统计常绿和落叶灌丛的样本点在不同季节影像上的NDVI值，可知他们与乔木林的常绿和落叶相似，因此可以使用相同的分类规则完成常绿针叶灌丛和落叶灌丛的分类。

2.3.2草原分类根据《中国植被》对不同草原类型的定义可知，不同类型的草原有着不同的湿度和植被盖度，因此区分不同的草原类型需要同时考虑这两个特征。温度植被干旱指数（Temperature Veg-etationDrynessIndex,TVDI)基于NDVI和地表温度很好地结合了湿度和植被盖度的特征。因此本文通过反演得到的TVDI来细分3种草原类型。在分类前，对3种草原类型各采集160个样本点，计算其TVDI值并进行统计分析。最终使用不同草原类型的TVDI平均值作为分类阈值,在ENVI中适当调整阈值后，建立草原分类的决策树，完成草原的精细化分类。最终决策树使用的分类阈值为0.4091和0.7349。

# 2.4分类后处理及精度评价

分类结果需要进行主次要分析以消除分类结果中过于破碎的斑块。在ENVI软件中，主次要分析的变换核大小有多种。不同的变换核对分类结果的影响程度不同，其中较大的变换核对分类结果的影响较大。为了在优化分类结果的同时减少这种影响，在分析中使用 $3 \times 3$ 大小的变换核。由于所获取的影像的小部分区域有云覆盖，因此这些区域中的植被信息无法被正确的提取。利用其它时相的遥感影像作为辅助对分类结果进行修正后，得到最终的结果(图6）。

根据实地调查获得的先验知识，基于google高清影像选取用于精度评价的样本。将整理后的样本点和分类结果加载到ENVI软件，计算混淆矩阵以评价分类结果的精度。表4即为计算所得的精度评价结果（表中0代表其他，即非植被）。最终的分类

![](images/b2016b846d20ab5a33f3997d85ebab39a833152b9b1a9ed9309ea2ab78f93c4f.jpg)  
Fig.5Classification result of the vegetation type group   
图6西北农牧交错带植被信息提取最终结果Fig.6Final extraction result of vegetation information

# 干吴区地理

# 表4精度评价表

Tab.4Accuracy evaluation table   

<html><body><table><tr><td>类型</td><td>A1</td><td>A2</td><td>C1</td><td>C2</td><td>D1</td><td>D2</td><td>D3</td><td>E1</td><td>H1</td><td>I1</td><td>K1</td><td>0</td><td>总计</td></tr><tr><td>A1</td><td>405</td><td>0</td><td>42</td><td>0</td><td>0</td><td>0</td><td>0</td><td>6</td><td>2</td><td>19</td><td>5</td><td>3</td><td>482</td></tr><tr><td>A2</td><td>51</td><td>948</td><td>30</td><td>11</td><td>22</td><td>2</td><td>0</td><td>1</td><td>3</td><td>5</td><td>14</td><td>1</td><td>1 088</td></tr><tr><td>C1</td><td>1</td><td>0</td><td>194</td><td>6</td><td>0</td><td>9</td><td>5</td><td>6</td><td>9</td><td>0</td><td>0</td><td>0</td><td>230</td></tr><tr><td>C2</td><td>1</td><td>43</td><td>60</td><td>609</td><td>18</td><td>17</td><td>14</td><td>5</td><td>17</td><td>3</td><td>7</td><td>0</td><td>794</td></tr><tr><td>D1</td><td>43</td><td>243</td><td>0</td><td>26</td><td>500</td><td>37</td><td>1</td><td>0</td><td>42</td><td>38</td><td>63</td><td>11</td><td>1 004</td></tr><tr><td>D2</td><td>4</td><td>19</td><td>63</td><td>55</td><td>38</td><td>1085</td><td>56</td><td>27</td><td>15</td><td>21</td><td>92</td><td>0</td><td>1 475</td></tr><tr><td>D3</td><td>0</td><td>1</td><td>0</td><td>9</td><td>3</td><td>44</td><td>847</td><td>42</td><td>1</td><td>1</td><td>18</td><td>0</td><td>966</td></tr><tr><td>E1</td><td>0</td><td>0</td><td>3</td><td>0</td><td>0</td><td>8</td><td>152</td><td>817</td><td>4</td><td>0</td><td>3</td><td>79</td><td>1 066</td></tr><tr><td>H1</td><td>5</td><td>17</td><td>2</td><td>2</td><td>29</td><td>15</td><td>0</td><td>0</td><td>419</td><td>65</td><td>36</td><td>5</td><td>595</td></tr><tr><td>I1</td><td>3</td><td>3</td><td>0</td><td>0</td><td>9</td><td>2</td><td>0</td><td>0</td><td>3</td><td>350</td><td>12</td><td>35</td><td>417</td></tr><tr><td>K1</td><td>10</td><td>18</td><td>0</td><td>9</td><td>27</td><td>7</td><td>0</td><td>0</td><td>27</td><td>8</td><td>1 276</td><td>0</td><td>1 382</td></tr><tr><td>0</td><td>5</td><td>0</td><td>1</td><td>1</td><td>4</td><td>0</td><td>12</td><td>31</td><td>5</td><td>24</td><td>9</td><td>856</td><td>948</td></tr><tr><td>总计</td><td>528</td><td>1 292</td><td>395</td><td>728</td><td>650</td><td>1 226</td><td>1087</td><td>935</td><td>547</td><td>534</td><td>1 535</td><td>990</td><td>10 447</td></tr><tr><td colspan="2">总体分类精度</td><td></td><td>79.51%</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td colspan="4">Kappa系数</td><td>0.773</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

结果总体精度为 $7 9 . 5 1 \%$ ,Kappa系数为0.773，相较于植被分布破碎复杂的实际情况，这一分类结果较好。

# 3结论

本文使用Landsat多光谱遥感影像数据，按"分层分类，逐层验证"的思路，对西北农牧交错区的植被信息进行了比较精细的提取，得到以下结论：

混合像元分解模型能够很好地区分植被和非植被的分布范围。通过在MNF变换后的影像波段组成的二维特征空间中手动提取端元，使用 $\mathbf { n }$ -DVisu-alizer对所选端元进行提纯，最后使用完全约束的最小二乘模型完成混合像元分解，区分有植被覆盖区域和无植被覆盖区域。验证结果显示，有植被覆盖区域的提取结果的总体精度为 $9 3 . 5 \%$ ,Kappa系数为0.782，结果较为理想。

基于多指标参与的CART决策树能够准确快速地对复杂地表的植被型组进行分类。通过筛选，使用表征光谱特征、纹理特征和地形特征的13个指标，对所选样本点进行分类，以训练CART决策树。最终用于分类的指标仅包含NDVI、PC2、SWIR1、NIR、DEM和MNDWI六个。软件生成的用于评价决策树的误差矩阵表显示，其标准中误差仅为0.003，说明决策树的分类结果较好。

创建的NDVI_DR结合谱间关系法能够很好地区分植被的常绿和落叶特征，使用TVDI阈值能够很好地区分不同草原类型。通过对不同季节NDVI的特征进行分析，构建了NDVI_DR。基于谱间关系法，构建了用于区分植被常绿和落叶特征的分类规则。利用常绿植被和落叶植被在NDVI_DR与NDVI_W大小关系的差异，实现了乔木林和灌丛的植被型分类。根据草甸草原、典型草原和荒漠草原在遥感影像上的差异，使用TVDI并设置阈值实现了三者的区分。最终分类结果的总体精度达到79.$5 1 \%$ ,kappa系数为0.773。

本文提出的提取方法比较适于中等分辨率多光谱遥感影像数据条件下的大区域信息提取，能在提高提取效率的同时，减少主观因素的影响。在以后的研究中，要尽可能使用多源、多时相的数据以进一步提高分类精度。在评价分类精度时，应进一步降低主观性对评价结果的影响。

# 参考文献（References）

[1］李秋月,潘学标.气候变化对我国北方农牧交错带空间位移的 影响[J].干旱区资源与环境,2012,26(10):1-6.[LIQiuyue, PAN Xuebiao.The impact of climate change on boundary shift of farming pasture ecotone in northern China［J]. Journal of Arid Land Resources and Environment,2012,26(10):1-6.]   
[2] 贾科利.基于遥感、GIS 的陕北农牧交错带土地利用与生态环 境效应研究[D].杨凌：西北农林科技大学，2007.［JIAKeli.A study on the land use and eco-environment effects assessment based on remote sensing and GIS in agriculture and pasturage interlaced zone of northern Shaanxi[D].Yangling:Northwest A&F

University,2007.]

[3]刘强,宋松柏,步永伟.基于RS 和GIS 的水土流失综合评价方 法——以安吉县为例[J].浙江水利科技,2016,44（3)：31-   
34.［LIU Qiang,SONG Songbai,BU Yongwei.The comprehensive evaluation method of soil erosion based on RS and GIS:Taking Anji County as an example[J]. Zhejiang Hydrotechnics,2016,44 (3) :31 -34.] [4］刘炜.土地利用/覆被变化信息遥感图像自动分类识别与提取 方法研究[D].杨竣:西北农林科技大学,2012.［LIU Wei.Auto-identify classification technology for LUCC information based on remote sensing data[D]. Yangling: Northwest A&F University，   
2012.] [5]LIU T,YANG X. Mapping vegetation in an urban area with stratified classfication and multiple endmember spectral mixture analysis[J].Remote Sensing of Environment,2013,133（12）:251   
264. [6]于文婧,刘晓娜,孙丹峰,等.基于HJ-CCD 数据和决策树法的 干旱半干旱灌区土地利用分类[J].农业工程学报,2016,32 (2）:212-219.[YU Wenjing,LIU Xiaona,SUN Danfeng,et al. Land use classification in arid and semi-arid irrigated area based on HJ-CCD data and decision tree method[J].Transactions of the Chinese Societyof Agricultural Engineeing,2016,32（2）:212   
219.] [7］张熙,鹿琳琳,王萍,等.基于决策树的漓江上游土地覆盖分类 [J].测绘科学,2016,41（3）:100-103.[ZHANG Xi,LU Linlin,WANG Ping,et al. Classification of land cover in upstream of Lijiang River Basin based on decision tree technologies[J].Science of Surveying and Mapping,2016,41(3）:100 -103.] [8］马骊驰,王金亮,刘广杰,等.基于改进型决策树遥感分类的土 地利用变化研究[J].地理空间信息,2016,14（7):12－16. [MA Lichi,WANG Jinliang,LIU Guangjie,et al.Research on land use change based on improved decision tree's remote sensing classification[J].Geospatial Information,2016,14(7） :12-16.] [9]王晓学,沈会涛,林田苗,等.利用多信息源提高半干旱地区 TM 影像的森林类型制图精度：以北京西部山区为例[J]．自然 资源学报,2017,32（7）:1217-1228.[WANG Xiaoxue,SHEN Huitao,LIN Tianmiao,etal.Improving the forest type mapping accuracy in semiarid mountainous areas based on TM images：Take the West Mountain of Beijing as an example[J]. Journal of Natural Resources,2017,32(7) :1217 -1228.] [10］方朝阳,邬浩,陶长华,等.鄱阳湖南矶湿地景观信息高分辨率 遥感提取[J].地球信息科学学报,2016,18(6）:847－856.[ FANG Chaoyang ,WU Hao,TAO Changhua,et al.2016.The wetland information extraction research of Nanji wetland in Poyang Lake based on high resolution remote sensing image[J]. Journal of Geo-information Science,18(6） :847 -856.] [11]AI-BASSAM B F.Land use/cover change analysis using reote sensing data:A case study,Zhengzhou Area,Henan Province,China[J].Al-Khawarizmi Engineering Journal,201O,6(2）:72-82. [12］裴欢,房世峰.基于地物光谱特征和空间特征的干旱区绿洲土 地分类[J].地理科学,2013,33（11）:1395-1399.[PEI Huan, FANG Shifeng.Land clasification of arid oasis based on spectral and spatial feature of ground objects[J].Scientia Geographica Sinica,2013,33（11):1395-1399.] [13]LI W,DU J,YI B. Study on classification for vegetation spectral feature extraction method based on decision tree algorithm[C]// Image Analysis and Signal Processing（IASP）,2011 International Conference on IEEE,2011:665 - 669.   
[14]KHATAMI R,MOUNTRAKIS G,STEHMAN S V.A meta-analysis of remote sensing research on supervised pixel-based land-cover image clasification processes: General guidelines for practitioners and future research[J].Remote Sensing of Environment,2016, 177 :89 - 100.   
[15］侯智庭.时间序列遥感数据植被分类中的特征选择方法研究 [D].昆明：云南师范大学,2017.[HOU Zhiting.Study on the feature selection method in time series remote sensing data vegetation classfication［D]. Kunming：Yunnan Normal University, 2017.]   
[16］靳彦华,熊黑钢,张芳.水浇地与旱地春小麦冠层高光谱反射 特征比较[J].国土资源遥感,2014,26(3）:24-30.[JIN Yanhua,XIONG Heigang,ZHANG Fang. Comparative study of canopy spectral reflectance characteristics of spring wheat in irigated land and dry land[J].Remote Sensing for Land & Resources,2014,26 (3):24 -30.]   
[17］雷光斌,李爱农,边金虎,等.基于阈值法的山区森林常绿、落 叶特征遥感自动识别方法——以贡嘎山地区为例[J].生态学 报,2014,34（24）:7210-7221.[LEI Guangbin,LI Ainong,BIAN Jinhu,et al.An practical method for automatically identifying the evergreen and deciduous characteristic of forests at mountainous areas:A case study in Mt. Gongga Region[J].Acta Ecologica Sinica,2014,34(24) :7210 -7221.]   
[18］中国植被编委会.中国植被[M].北京:科学出版社,1980. [China Vegetation Editorial Board.Chinese vegetation[M].Beijing: Science Press,1980.]   
[19]WU J,PENG D L. A research on extracting information of the arid regions'vegetation coverage using improved model of spectral mixture analysis[C]//Multimedia Technology（ICMT）,2010 International Conference on IEEE,2010:1-5.   
[20］刘欣.利用CART算法从LandSat8 卫星影像提取居民地的研 究[D].兰州:兰州大学,2015.[LIU Xin.Using CART algorithm to extract residential land from LandSat8 satellite image[D]. Lanzhou:Lanzhou University,2015.]   
[21］张娟.绿洲开发对干旱区生态环境的影响评价[D].兰州：兰 州大学,2016.[ZHANG Juan.The impact of the oasis development on ecological environment[D].Lanzhou:Lanzhou University, 2016.]   
[22］丁小辉,李华朋,张树清.基于多态蚁群算法的高光谱遥感影 像最优波段选择[J].遥感技术与应用,2016,31（2)：275- 284.[DING Xiaohui,LI Huapeng,ZHANG Shuqing. Optimized band selection of hyperspectral remote sensing image based on polymorphic ant colony algorithm[J]. Remote Sensing Technology and Application,2016,31(2）:275-284.]   
[23]Rouse JW. Monitoring the vernal advancement and retrogradation （greenwave effct） of natural vegetation[J]. NASA,1974.   
[24]Liu HQ,Huete A.A feedback based modification of the NDVI to minimize canopy background and atmospheric noise[J].IEEE Transactions on Geoscience & Remote Sensing,1995,33（2）:457 -465.   
[25] Huete A $\mathrm { \mathrm { R } , A }$ Soil-Adjusted Vegetation Index[J]. Remote Sensing of Environment,1988,27(3）:295-309.   
[26]Pinty B,Verstraete M M.GEMI:A non-linear index to monitor global vegetation from satellites[J].Plant Ecology,1992,11（1）：

15-20.

[27]Yang Z,Zhao H,DiL,et al.A Comparison of Vegetation Indices forCorn and Soybean Vegetation Condition Monitoring[C]//IEEE International Geoscience & Remote Sensing Symposium,IGARSS 2009,July 12-17,2009,University of Cape Town,Cape Town, South Africa,Proceedings,2009:IV-801-IV-804.   
[28]Bannari A,Asalhi H,Teillet PM.Transformed difference vegeta

tion index（TDVI） for vegetation cover mapping[C]//Geoscience and Remote Sensing Symposium,2002.IGARSS '02.2002 IEEE International,2002:3053-3055 vol.5.

[29]P.V.Narasimha Rao,M.V.R.Sesha Sai,K.Sreenivas,et al.Textural analysis of IRS-1D panchromatic data for land cover classification［J].International Journal of Remote Sensing,2OO2,23 (17):3327-3345

# Vegetation information extraction in farming-pastoral ectones in northwest China using hierarchical classification and multiple indices

HE Hong-jie'，MU Ya-chao¹，WEI bao-cheng1，DU Ting1，XUE Xiao-yu’， XIE Yao-wen1,2 (1ThecolegeofEarthandEnvironment,Lanzhou University,Lanzhou73Oo,Gansu,China；2KeyaboratoryofWester China's Environmental System（Ministryof Education）,Lanzhou University,Lanzhou 73ooo,Gansu,China)

Abstract：Based on Chinese vegetation classification criteria described in the book“Chinese Vegetation”,the vegetation clasification systemsuitable for the farming-pastoral ectones in Northwestern China was established with thefield investigation.Using theLandsat images,theterrindataand fielddataof the studyarea,thevegetation information inthe study area was refined according to the implementation strategyas“hierarchical classfication and layer by layer verification”.During the extraction process,the mixed pixels decomposition of preprocessed remotely sensed images was performed by using the fully constrained least-squares model,and the vegetation fraction of the study area was obtained.We clasified the study area into vegetation area where the vegetation fraction is larger than （204号 $5 \%$ and non-vegetation area where the vegetation fraction is less than $5 \%$ . In the vegetation area,it was further classified into 7 main vegetation type groups which include the tree group,shrub group and grassland group using the CART decision tree based on the spectral characteristic,texture characteristic（Mean）and terrin characteristic (Digital Elevation Model,DEM).Each vegetation type group was again further classfied intodifferent sub types based on the refined indexes.The tree group and shrub group were categorized into evergreen vegetation type and deciduous vegetation type based on the NDVI diference ratio index which was established using the seasonal variations of their $N D W s$ of different plants.The grassland type group was categorized into desert grassand,the typical grassland and meadow grassand using the temperature vegetation dryness index（TVDI).After this step,the spatial distribution of each vegetation type wasobtained.It was proved that the overallaccuracyof the final classification can reach $7 9 . 5 1 \%$ and the kappa coefficient is O.773.The classification method used in this study makes full use of the spectral informationand texture informationof theremotely sensed images,and cooperates withterrain nformation.Experimental result shows that the method of using hierarchical classification and multiple indexes could extractthevegetation information eficiently fromthe images of the farming-pastoral ectoneswith high acuracy.The classification result in thisarea provides the basic data for the furtherresearch ontherelationship betweensurface hydrothermal processand landcover change,especiallyvegetation cover change.Meanwhile,it provides reference for the conservation of vegetation area and ecological environment construction in this area.

Key Words:the farming-pastoral ectone；vegetation information extraction； LSMA；CART decision tree； NDVIdifference ratio (NDVI_DR）； temperature vegetation dryness index(TVDI)