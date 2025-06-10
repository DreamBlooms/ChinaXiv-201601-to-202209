# 基于Landsat影像的柴达木盆地湖泊提取方法

文广超，李兴，吴冰洁，王晓鹤，谢洪波(河南理工大学资源环境学院,河南 焦作454000)

摘要：柴达木盆地内的湖泊对维系区域生态平衡、满足生产及生活用水、保护生态环境具有重要的作用。随着区域气候变化和人类活动影响的增强,盆地内湖泊格局发生了一系列变化,为了分析湖泊变化特征,查明变化原因,以快速、精确、适用性强为目标,基于Landsat系列遥感影像,通过分析可鲁克湖流域湖泊水体TOA(Top-of-atmo-sphere)反射率与其他地物TOA反射率的差异,提出了一种湖泊水体自动提取方法——湖泊水体差分模型。利用该模型处理了柴达木盆地的近百个Landsat图像场景,提取了不同时间节点、不同空间位置的湖泊水体,使用总体分类精度、Kappa 系数及用户精度对其精度进行评价,并与NDWI(Normalized Difference Water Index）、MNDWI（ModifiedNormalized Diference Water Index)方法对该地区湖泊水体提取结果进行了比较分析。结果表明：（1）利用TOA反射率差异,可区分目标与非目标地物;(2)基于稳定的阈值,湖泊水体差分模型可实现湖泊水体信息快速提取，与NDWI、MNDWI等水体信息提取方法相比,能够更加有效抑制地表河流、冰雪、阴影、沼泽湿地等干扰因素,在模型应用的区域内，平均总体分类精度与用户精度均达到 $9 9 \%$ 以上，Kappa达到0.9877;(3）湖泊水体差分模型的输入数据既可以是TOA反射率,也可以是Landsat(Level-2)的地表反射率数据；(4）湖泊水体差分模型适用于柴达木盆地内大范围区域的湖泊水体提取，能够为湖泊水体动态变化规律研究提供技术支持。

关键词：Landsat；湖泊；TOA反射率；湖泊水体差分模型；柴达木盆地

湖泊参与流域水循环,对维持区域水量平衡[1]满足生产生活用水[2]、河流流量调节[3]发挥着重要作用。柴达木盆地地处青藏高原东北部，盆地内湖泊众多，且多位于盆地中心的低洼地带[4],为地表与地下水的汇集区和河流水系的尾闾，是气候变化与人类活动的敏感指示器[5],湖泊及其引起的生态环境的变化在一定程度上可以反映区域乃至全球的气候事件,在干旱的内陆盆地区，湖泊是维持区域生态系统的重要支撑，同时，盆地内的盐湖作为资源也是当地的经济支柱[。近年来，随着全球气候变化和人类活动干扰的加剧，盆地内湖泊出现了面积萎缩乃至干涸的现象[8-9]。湖泊面积的变化不仅影响当地的社会经济和生态环境的可持续发展，而且对区域乃至青藏高原气候变化均具有重要影响[0]。因此,精准监测柴达木盆地湖泊水体动态,揭示自然与人类活动对湖泊的影响规律，对合理开发利用和保护湖泊水域，维系区域生态平衡具有重

要的意义[]

卫星遥感技术以其探测范围广、信息容量大、实时性与动态性强、免费共享等优势，在湖泊水体信息提取中得到了国内外学者的青睐[12-16],湖泊水体的提取最早主要依靠目视解译，目视解译提取水体的效果好坏受人为主观因素影响，而且耗费的时间成本，人力成本高。用计算机自动提取水体的早期研究主要是利用水体在单个波段上表现出的与非水体截然不同的特性,如1985年,Jupp等[17]通过对TM7(TM影像的第七波段)设定阈值识别水体信息；1992年陆家驹等[18通过对TM5设定阈值识别水体信息，受限于分辨率，对于 $1 0 0 0 { \sim } 4 0 0 0 ~ \mathrm { m } ^ { 2 }$ 之间的水体识别起来还有困难。随后的研究利用了水体在多个波段上的组合特征，产生了多种水体指数方法，以1996年McFeeters[19]提出的归一化差异水体指数NDWI(NormalizedDifferenceWaterIndex)为代表，通过抑制植被和土壤信息，提取了水体信息，但其对建筑物、阴影、云影、细小河流的区分度不高;杨存建等[20]利用水体在TM2波段与TM3波段的亮度值之和大于TM4波段与TM5波段的亮度值之和这一特征提取水体;徐涵秋[21提出了改进的归一化差异水体指数法MNDWI(ModifiedNDWI）,较好地提取了城镇水体信息，该方法仅适用于拥有SWIR的传感器，易受冰雪的影响;闫霈等[22]提出增强型水体指数EWI(EnhancedWaterIndex）,在提取水体时区分了半干涸河道与背景噪声，但对细小水体分离效果差，出现湖泊漏提现象；丁凤[23将TM7波段应用于构建新型水体指数NWI(NewWaterIndex)上，能够清晰提取水体信息，但无法区分山体;2014年王晴晴等[24]提出简单比值型水体指数SRWI(Sim-ple RatioofWaterIndex)用来增强水体与植被、建筑物、裸地和阴影的差异；丁占峰等[25]基于对鄱阳湖水体信息提取的研究提出ONDWI(OverrideNDWI)用来去除水体中含有的沼泽湿地，同时抑制植被和土壤信息，但对冰雪和阴影的区分度不高。此外，在沙漠水体信息提取[26-27]、城市水体信息提取[28-29]、水域边界或河流信息提取[30-31]、背景噪音去除[32-33]及提高土壤、植被与水体信息区分度[34-35]等方面，学者们也做了较为深入的研究，建立了一系列有效实用的水体指数。针对柴达木盆地湖泊水体动态变化,前人主要利用目视解译、单波段阈值法、NDWI、MNDWI等方法开展研究，取得了一系列成果[36-38]。以上水体提取方法中，单波段阈值法与比值法依赖动态的阈值对湖泊水体信息进行提取，且对阴影、冰雪噪声的去除效果不理想;基于各种水体指数法提取水体信息的阈值基本稳定为正值，因此将经水体模型运算后结果大于0的区域判别为水体来提取信息，然而试验表明NDWI在提取西部湖泊水体信息时会将沼泽湿地与冰雪一起提取出来，MNDWI、EWI、NWI、ONDWI等方法则存在湖泊漏提和误提冰雪的情况。

随着信息处理、定量遥感等相关技术的发展，遥感解译正由半自动化向全自动智能化解译方向发展[39]，对遥感解译的速度、分类精度与适用性提出了更高的要求。为了解决上述问题，本文以青海省德令哈市境内的可鲁克湖流域为试验区，以可鲁克湖、托素湖、尕海为试验对象建立水体识别模型，为了验证模型的识别精度，选择了柴达木盆地中的大柴旦湖、小柴旦湖、尕斯库勒湖和察尔汗盐湖4个典型湖泊作为模型的验证区域。同时，为了验证模型在柴达木盆地以外区域的适用性，将该模型应用于邻近柴达木盆地的青海湖、尕海湖，以及太湖、天池和滇池的水体提取中。基于Landsat系列卫星影像，进行湖泊水体信息自动提取方法研究，以精度高、速度快、适用性强为目标，旨在提出一种适合柴达木盆地区域的自动提取湖泊水体信息的方法，进而为湖泊水体的动态监测提供可靠的技术支撑。

# 1研究区概况与方法

# 1.1 研究区概况

柴达木盆地位于青藏高原东北缘，地处青海省西北部 $( 3 4 ^ { \circ } 4 0 ^ { \prime } { \sim } 3 9 ^ { \circ } 2 0 ^ { \prime } \mathrm { N } \mathrm { , } 9 0 ^ { \circ } 0 0 ^ { \prime } { \sim } 9 9 ^ { \circ } 2 0 ^ { \prime } \mathrm { E }$ ,图1)。中部的平原区海拔 $2 6 7 6 { \sim } 3 0 0 0 \mathrm { m }$ ,地势低洼，四周高山环绕，西南暖湿气流难以进入，降水稀少、蒸发量大、日照充足，属于内陆极端干旱高寒气候。盆地内共有大小河流79条，这些河流以盆地为中心，呈聚合状分布，河水通过地表及地下径流最终注入各自的汇水中心，形成尾闾湖[40]

![](images/33970c204fcd7eb570c9a921477d97045d2f25f88f625a7fd7c939c1babfd6b6.jpg)  
图1研究区位置及采样点分布  
Fig.1 Location of the study area and the distribution of sampling points

# 1.2数据来源与方法

1.2.1遥感数据选用Landsat系列卫星影像数据作为数据源,数据从美国地质勘探局网站(https:/earthexplorer.usgs.gov/)下载,空间分辨率 $3 0 \mathrm { m }$ ，影像级别为Level1TP(地形校正)级。除了柴达木盆地内的影像外，还收集了柴达木盆地内外其他区域不同时期、不同传感器的共计90个Landsat图像场景数据，旨在验证本文提出的湖泊水体提取方法在不同时间、空间以及传感器的普遍适用性。本文选取自2000—2020年可鲁克湖、小柴旦湖、尕斯库勒湖、察尔汗盐湖、青海湖等区域的部分影像进行论述，数据基本信息见表1。

1.2.2遥感数据预处理由于影像上的DN(digitalnumber)是由辐射亮度值经过线性变换拉伸到( $( 0 \sim$ 255)范围内后得到的灰度值，不能准确表征地物在每个波段真实的反射率，因此在ENVI软件中利用产品提供的影像定标文件将DN值转换成TOA(Top-of-atmosphere)反射率。TOA反射率相对于DN值有两大优点：一是消除了传感器在不同时间获取数据时太阳天顶角带来的余弦效应；二是补偿了外大气太阳辐照度的不同值[41]

1.2.3采样点布设为了获取不同地物的波谱曲线，在对影像进行图像增强的基础上，结合谷歌地球上同区域高分辨率影像，采用目视判读法共收集了55615个样本点，其中包括26676个水体样点，28939个非水体样点。

此外，在青海湖区域2018年7月的影像发布后，于当月在距青海湖东北 $3 \mathrm { k m }$ 的尕海湖周边，对尕海湖水体和非水体之间的边界线采集了8406个实测定位点数据，这些采样点组成的虚线代表实际的湖岸线，用于湖泊水体信息提取结果的视觉评估以及精度评价参考。

1.2.4技术路线模型建立分三步完成:第一步，基于下载的Landsat系列影像，借助ENVI软件，利用Landsat产品提供的元数据文件，将DN值转换为TOA反射率值;第二步，通过实地调研，结合目视解译，构建不同地物的波谱曲线，分析湖泊水体与干扰地物要素之间的差异，初步提出湖泊水体信息提取模型;第三步，对模型提取精度进行验证，检验精度超过 $9 5 \%$ 时，确定建立湖泊水体信息提取模型，检验精度较低时，重复第二和第三步操作，湖泊水体信息提取模型建立的思路见图2。

1.2.5精度评价方法为了验证湖泊水体信息提取的精度，引入视觉评估法和混淆矩阵 $^ { [ 4 2 ] } 2$ 种方法。

混淆矩阵[43-44]中的总体分类精度OA（公式1)，Kappa系数（公式2）,以及用户精度User accuracy(公式3)等参数可以定量反映分类效果。

$$
\mathrm { O A } = \frac { \overrightarrow { \mathrm { I E } } \overrightarrow { \mathrm { H } } \overrightarrow { \mathrm { H } } \cdot \overrightarrow { \mathrm { J } } \cdot \overrightarrow { \mathrm { H } } \cdot \overrightarrow { \mathrm { J } } / \overrightarrow { \ddagger } \cdot \overrightarrow { \mathrm { J } } \cdot \overrightarrow { \mathrm { K } } \cdot \overrightarrow { \mathrm { x } } \cdot \overrightarrow { \mathrm { x } } } { \overrightarrow { \mathrm { K } } \cdot \overrightarrow { \mathrm { J } } / \overrightarrow { \mathrm { H } } \cdot \overrightarrow { \mathrm { J } } \cdot \overrightarrow { \mathrm { L } } \cdot \overrightarrow { \mathrm { x } } \cdot \overrightarrow { \mathrm { x } } \cdot \overrightarrow { \mathrm { x } } \cdot } \times 1 0 0 \
$$

$$
{ \mathrm { K a p p a } } = { \frac { n { \displaystyle \sum _ { k = 1 } ^ { q } } n _ { k k } - { \displaystyle \sum _ { k = 1 } ^ { q } } n _ { k + } n _ { + k } } } { n ^ { 2 } - { \displaystyle \sum _ { k = 1 } ^ { q } } n _ { k + } n _ { + k } } 
$$

式中： $n$ 是总采样测试点； $n _ { k k }$ 是第 $k$ 类地物样本点的总数; $n _ { k + }$ 是从分类数据中导出第 $k$ 类样点的总数； $n _ { + k }$ 是从数据集导出的第 $k$ 类地物样本点的总数； $\boldsymbol { q }$ 是样本类别的总数。

$$
{ \mathrm { U s e r a c c u r a c y } } = { \frac { n _ { k k } } { n _ { k + } } } \times 1 0 0 
$$

表1所用部分遥感影像基本信息  
Tab.1 Basic information of some remote sensing images used   

<html><body><table><tr><td>地区</td><td>传感器</td><td>日期/年-月-日</td><td>条带号</td><td>行号</td><td>云量/%</td></tr><tr><td>可鲁克湖</td><td>TM</td><td>2000-04-10</td><td>135</td><td>34</td><td>13.45</td></tr><tr><td>可鲁克湖</td><td>ETM+</td><td>2002-04-08</td><td>135</td><td>34</td><td>3</td></tr><tr><td>可鲁克湖</td><td>OLI</td><td>2016-07-27</td><td>135</td><td>34</td><td>2.36</td></tr><tr><td>小柴旦湖</td><td>TM</td><td>2004-06-15</td><td>136</td><td>34</td><td>0.79</td></tr><tr><td>尕斯库勒湖</td><td>TM</td><td>2002-05-14</td><td>139</td><td>34</td><td>14.42</td></tr><tr><td>青海湖</td><td>OLI</td><td>2018-07-19</td><td>133</td><td>34</td><td>20.49</td></tr><tr><td>察尔汗盐湖</td><td>OLI</td><td>2020-04-08</td><td>136</td><td>34</td><td>6.88</td></tr></table></body></html>

![](images/83d9827b6c6909a27bf7ba0efeeadc5623d78e2f678b0f671c40d9d7472643c1.jpg)  
图2湖泊水体信息提取模型建立的技术路线 Fig.2 Technical route for establishing lake water body information extraction model

总体分类精度（OA）、Kappa系数和用户精度的值越大，说明分类效果越好。

# 2湖泊水体提取模型的提出

# 2.1湖泊水体的波谱特征

不同类型的地物对一定波长的电磁波表现出不同的反射特性，地物反射电磁波特性在遥感影像上的定量表现就是TOA反射率数值不同，通常用波谱曲线来刻画地物在不同波段的TOA反射率表现。根据不同地物TOA反射率的差异构建模型，即通过增强目标地物抑制非目标地物的方式，将目标地物与其他地物区分开。

在柴达木盆地内，湖泊水体的矿化度存在较大的差异，有淡水湖、半咸水湖、咸水湖和盐湖4类，平均高程约 $2 7 8 8 \ \mathrm { m } ^ { [ 4 0 ] }$ 。在可鲁克湖流域,有可鲁克湖(淡水湖）托素湖(咸水湖)与尕海(盐湖)3个湖泊，矿化度分别为： $0 . 8 0 { \sim } 0 . 8 8 \ \mathrm { g } \cdot \mathrm { L } ^ { - 1 } \cdot 2 9 . 6 2 { \sim } 3 0 . 2 0 \ \mathrm { g } \cdot \mathrm { L } ^ { - 1 } \nonumber$ $1 0 3 . 6 { \sim } 1 5 6 \ \mathrm { g } \cdot \mathrm { L } ^ { - 1 }$ ,流域平均高程 $2 9 8 0 \ \mathrm { m } ^ { [ 4 5 ] }$ 。无论从地形地貌还是矿化度上看，可鲁克湖流域地物要素的光谱特征在柴达木盆地均具有典型性。为此，本文选择可鲁克湖流域作为试验区开展湖泊水体信息提取方法研究。

基于上述思路，在可鲁克湖周边区域，在实地调研的基础上，通过目视解译选择对湖泊水体信息提取干扰较大的沼泽湿地、冰雪、阴影、裸地、建筑物等5类典型要素，通过样本点(图1)获取其在不同波段上的TOA反射率，分别求取其平均TOA反射率，以波段为横坐标，TOA反射率为纵坐标，绘制5类典型地物和湖泊水体的波谱曲线(图3)。

![](images/347d71e8cad0c4474709a9ee66c40b3aae14b82102b57ed78e9523667945e21e.jpg)  
Fig.3Spectral signatures of six major land use classes in the study area

注：Blue为蓝光;Green为绿光;Red为红光；NIR为近红外；SWIR1为短波红外1;SWIR2为短波红外2。图3研究区6种地类的波谱曲线

从图3可以看出，湖泊水体的TOA反射率与其他5类地物有明显的不同,表现在以下2个方面：一是湖泊是唯一一类波谱曲线整体呈下降趋势的地物；二是湖泊在Blue、Green波段的反射率值接近其他地物，而在Red、NIR、SWIR1、SWIR2波段明显低于其他地物。基于上述差异，在研究区内，可以根据TOA反射率来区分湖泊水体和其他地物。

# 2.2湖泊水体差分模型的提出

对于清水，在Blue-Green波段反射率为 $4 \% \sim 5 \%$ ，波长 $0 . 6 ~ \mu \mathrm { m }$ 以上的Red波段反射率降到 $2 \% \sim 3 \%$ ,在NIR波段上几乎吸收全部的入射能量[46]。对于柴达木盆地的湖水来说，随着悬浮物浓度的增加，与清水相比，反射率数值会发生一定的影响[47],但整体的反射率峰值仍然处于Blue、Green波段范围内，且反射率随波长的增加而减小[48-49]。基于此,对1.2.3小节中的采样结果，取TOA反射率，执行(Blue $^ +$ Green-Red-NIR-SWIR1-SWIR2)运算，结果表明,湖泊水体中，所有湖泊样本点的TOA反射率运算结果均大于0,而几乎所有的其他地物样本点表现出相反的运算结果。由此可以初步得出以下结论：(Blue $^ +$ Green-Red-NIR-SWIR1-SWIR2)运算可以将湖泊水体信息增强为大于0的值，将其他非水体信息抑制为小于0的值。据此，提出了基于Landsat系列卫星影像的湖泊水体信息提取模型一—湖泊水体差分模型（LakeWater DifferentialModel,LWDM)。

Blue $^ +$ Green-Red-NIR-SWIR1-SWIR2>0

# 3结果与分析

为了验证模型的可行性，对比不同模型的提取效果，本文选择位于柴达木盆地东部的可鲁克湖、尕海和托素湖，中部的大柴旦湖、小柴旦湖，西部的尕斯库勒湖，以及察尔汗盐湖为验证对象，利用不同传感器数据，对LWDM模型进行验证。同时，为证明模型在更大空间尺度的普遍适用性，还选择了临近柴达木盆地东部边缘的青海湖、尕海湖作为验证对象。

# 3.1湖泊水体信息提取结果

采用LWDM、NDWI和MNDWI方法部分提取结果如下图所示(图4\~图5)。图4a采用真彩色影像合成并进行平方根拉伸，图5a采用真彩色影像合成并进行高斯增强，旨在突出湖泊在原影像上的位置。

在可鲁克湖流域内，由图4可知，3种方法均可以将湖泊水体信息提取出来，但NDWI方法在提取湖泊信息(图4c)的同时提取了河流水体、沼泽湿地和部分阴影的信息，MNDWI方法同时提取了河流水体、沼泽湿地、阴影和冰雪的信息(图4d)；这种情况在小柴旦湖周边区域以及尕斯库勒湖区域同样存在。

![](images/b9a7f4f64542a614a4e916110474ae11e6c81e7d73e232cb621a0fb5e27a620f.jpg)  
(a)真彩色合成影像  
图4可鲁克湖区域湖泊水体提取结果   
Fig.4Results of lake water extraction in Keluke Lake

![](images/03cb6385557249aa691f0502f53498547a898f49aca18de6f909ccea4754321e.jpg)  
图5青海湖区域湖泊水体提取结果  
Fig.5Results of lake water extraction in Qinghai Lake

在青海湖区域，选择同一时间段(2018年7月），对比野外实测湖岸线与基于LWDM的湖泊提取结果(图6)，可以看出，提取结果与实测湖岸线误差在一个像素内，能够反映实际湖水岸线的曲折情况。

虽然，在模型建立之初就已经考虑到了柴达木盆地不同湖泊水体矿化度的差异，作为测试对象的尕海，其矿化度已经达到了卤水的标准，但与察尔汗盐湖矿化度高达 $4 0 0 \ \mathrm { g \cdot L } ^ { - 1 }$ 相比，还存在较大的差距，为了进一步验证模型的适用性，运用本文提出的方法，提取了察尔汗盐湖及其周边的湖泊水体信息（图7），由图7可知，LWDM较为完整的提取了湖泊水体信息，有效去除了区内的道路、建筑物等干扰信息，总体分类精度为 $9 7 . 9 8 \%$ ,Kappa系数为0.9339，用户精度 $9 9 . 9 4 \%$ ，说明LWDM模型在柴达木盆地内具有较好的适用性。

通过上述对比可以得出如下结论：LWDM在提取湖泊水体信息的同时，不仅可以去除植被、裸地、建筑物等干扰信息，也可以较好地去除绝大部分雪、阴影、沼泽湿地和地表河流等干扰因素，与NDWI、MNDWI等水体提取方法相比，LWDM方法可以更好地提取柴达木盆地内的湖泊水体信息，

# 3.2精度评价

根据原始的混淆矩阵，经过公式(1) $\sim$ (3)的运算，得到精度评价结果(表2)。

由表2可知，湖泊水体信息的提取精度表现为：LWDM>NDWI>MNDWI。在青海湖区域附近，3种方法提取湖泊水体信息的精度接近，而在柴达木盆地内的可鲁克湖区域、小柴旦湖区域、尕斯库勒湖区域、察尔汗盐湖区域，3种水体提取方法在湖泊提取精度上表现出显著的差异，其原因是NDWI、

![](images/049b1b726300fca480ec7a3ec29301a17d43d194bf528fb0edad153667a4a8fd.jpg)  
图6青海湖区域LWDM方法水体局部提取结果

![](images/eee8705c761d41f33bdc04a4f8f17dc9b1099839a227044f8ba35833371a6e10.jpg)  
Fig.6 Results of lake water extraction byLWDM in Qinghai Lake   
图7察尔汗盐湖水体提取结果   
Fig.7Resultsof lake water extraction byLWDMin Chaerhan SaltLake

MNDWI在提取湖泊水体时，会同时提取地表河流、冰雪、沼泽湿地等非湖泊水体信息，从而降低了用户精度。

此外，在柴达木盆地的其他区域不同时期、不同传感器共计90个Landsat图像场景数据中，OA达到 $9 9 . 4 8 \%$ ,Kappa值达到0.9877。

由此可以得出如下结论：基于Landsat系列影像,LWDM可以较好地提取柴达木盆地湖泊水体信息，相对于NDWI、MNDWI等水体信息提取方法，去噪能力强，提取精度显著提高。对于柴达木盆地之外的其他区域，针对不同清洁度的湖泊，LWDM方法的适用性有待进一步的研究。

# 3.3提取结果分析

以LandsatTM、ETM $\cdot +$ 和OLI多光谱遥感影像为数据源，通过分析可鲁克湖流域内湖泊水体与冰雪、阴影、沼泽湿地、裸地、建筑物等对象的TOA反射率差异，根据湖泊水体在Blue、Green波段的TOA反射率高于其余波段，且不同波段TOA反射率值呈整体下降趋势的特征，利用蓝光、绿光、红光、近红外与短波红外波段，构建了柴达木盆地湖泊水体信息提取模型——湖泊水体差分模型(LWDM)。将该模型应用于柴达木盆地的可鲁克湖、托素湖、尕海、尕斯库勒湖、小柴旦湖以及盆地附近青海湖地区的尕海湖等湖泊水体信息的提取，与Mcfeeters[19]的NDWI和徐涵秋的MNDWI相比，LWDM不仅可以较为准确地提取出湖泊水体信息，而且可以有效去除冰雪、阴影、沼泽湿地、建筑物等干扰信息。模型提出后，利用Landsat(Level-2产品)的地表反射率作为输人数据对模型进行进一步测试，结果表明其提取精度与TOA反射率作为输入数据的提取精度基本一致。因此，本文提出的湖泊水体差分模型既可以将TOA反射率作为输人数据，也可以将地表反射率作为输入数据;同时应用不同时段、不同季节的Landsat系列影像数据进行了测试，结果表明，该模型所反映的湖泊水体规律在不同年份、不同季节是一致的。此外，NDWI和MNDWI提出的目的是提取地表水体信息[19.21],并未考虑湖泊水体信息与河流水体信息的差异，因此，在提取湖泊水体信息的同时，也混入了地表河流水体信息（图 $4 \mathrm { c } \sim$ 图4d)。而LWDM建立的目标就是提取湖泊水体信息，在前期试验研究过程中充分考虑了湖泊水体与地表水体信息之间的差异，在提取湖泊水体信息的同时，较好地剔除地表河流的水体信息（图4b）。

表2湖泊水体信息提取精度评价结果  
Tab.2Evaluation result of information extraction accuracy of lake water   

<html><body><table><tr><td>试验区域</td><td>传感器</td><td>成像时间/年-月-日</td><td>方法</td><td>0A/%</td><td>Kappa</td><td>用户精度/%</td></tr><tr><td>可鲁克湖</td><td>TM</td><td>2000-04-10</td><td>LWDM</td><td>99.65</td><td>0.9958</td><td>99.39</td></tr><tr><td>可鲁克湖</td><td>ETM+</td><td>2002-04-08</td><td></td><td>99.43</td><td>0.9932</td><td>100</td></tr><tr><td>可鲁克湖</td><td>OLI</td><td>2016-07-27</td><td></td><td>99.87</td><td>0.9987</td><td>99.47</td></tr><tr><td>小柴旦湖</td><td>TM</td><td>2004-06-15</td><td></td><td>99.65</td><td>0.9948</td><td>100</td></tr><tr><td>尕斯库勒湖</td><td>TM</td><td>2002-05-14</td><td></td><td>99.91</td><td>0.9988</td><td>99.65</td></tr><tr><td>青海湖</td><td>OLI</td><td>2018-07-19</td><td></td><td>99.87</td><td>0.9984</td><td>99.20</td></tr><tr><td>察尔汗盐湖</td><td>OLI</td><td>2020-04-08</td><td></td><td>97.98</td><td>0.9339</td><td>99.94</td></tr><tr><td>平均值</td><td></td><td></td><td></td><td>99.48</td><td>0.9877</td><td>99.66</td></tr><tr><td>可鲁克湖</td><td>TM</td><td>2000-04-10</td><td>NDWI</td><td>95.42</td><td>0.9450</td><td>79.12</td></tr><tr><td>可鲁克湖</td><td>ETM+</td><td>2002-04-08</td><td></td><td>95.07</td><td>0.9409</td><td>77.18</td></tr><tr><td>可鲁克湖</td><td>OLI</td><td>2016-07-27</td><td></td><td>97.83</td><td>0.9728</td><td>90.20</td></tr><tr><td>小柴旦湖</td><td>TM</td><td>2004-06-15</td><td></td><td>95.60</td><td>0.9340</td><td>88.34</td></tr><tr><td>尕斯库勒湖</td><td>TM</td><td>2002-05-14</td><td></td><td>96.38</td><td>0.9517</td><td>87.34</td></tr><tr><td>青海湖</td><td>OLI</td><td>2018-07-19</td><td></td><td>99.63</td><td>0.9956</td><td>97.84</td></tr><tr><td>察尔汗盐湖</td><td>OLI</td><td>2020-04-08</td><td></td><td>96.27</td><td>0.7363</td><td>99.89</td></tr><tr><td>平均值</td><td></td><td></td><td></td><td>96.60</td><td>0.9252</td><td>88.56</td></tr><tr><td>可鲁克湖</td><td>TM</td><td>2000-04-10</td><td>MNDWI</td><td>77.67</td><td>0.7320</td><td>42.74</td></tr><tr><td>可鲁克湖</td><td>ETM+</td><td>2002-04-08</td><td></td><td>64.77</td><td>0.5773</td><td>32.12</td></tr><tr><td>可鲁克湖</td><td>OLI</td><td>2016-07-27</td><td></td><td>96.80</td><td>0.9599</td><td>86.19</td></tr><tr><td>小柴旦湖</td><td>TM</td><td>2004-06-15</td><td></td><td>65.74</td><td>0.4861</td><td>49.31</td></tr><tr><td>尕斯库勒湖</td><td>TM</td><td>2002-05-14</td><td></td><td>71.10</td><td>0.6147</td><td>46.38</td></tr><tr><td>青海湖</td><td>OLI</td><td>2018-07-19</td><td></td><td>91.10</td><td>0.8932</td><td>65.19</td></tr><tr><td>察尔汗盐湖</td><td>OLI</td><td>2020-04-08</td><td></td><td>96.27</td><td>0.7301</td><td>89.91</td></tr><tr><td>平均值</td><td></td><td></td><td></td><td>80.49</td><td>0.7133</td><td>58.83</td></tr></table></body></html>

注：加粗的数据表示不同水体提取方法对不同湖泊水体信息提取结果精度的平均值。

从提取精度评价的结果来看，LWDM方法的提取精度要高于NDWI和MNDWI,原因有三：第一，NDWI是在分析植被与水体在可见光波段和近红外波段的反射强度特征后提出的[9]，目的是最大程度地抑制植被信息，增强水体信息。而MNDWI是针对NDWI不能很好区分城市范围内的水体而改进的一种水体指数[2]，目的是增加建筑物和水体的差异，进而更精确的提取城市范围内的水体，但是不能很好地抑制含水量较大的土壤干扰信息。二者以提取地表水体(包括河流、湖泊、水库等)为目标，建立时更多地关注植被、建筑物对水体信息提取的干扰。第二，虽然徐涵秋在提出MNDWI时，选择河流、湖泊、海洋3种水体对NDWI和MNDWI进行了水体信息提取试验，实验结果证明，MNDWI具有一定的阴影去除效果，但未考虑像柴达木盆地这样复杂的环境：一是盆地属于高原型内陆盆地，极高山、高山、戈壁、丘陵、平原、盐沼等地貌并存；二是区内湖泊、河流密布，沼泽湿地普遍存在，不同湖泊矿化度差异较大；三是盆地周边的极高山、高山区有冰雪覆盖区。这在一定程度上降低了MNDWI模型提取柴达木盆地湖泊水体信息的精度。第三，LWDM模型以提取柴达木盆地湖泊水体信息为目标，建立时不仅考虑了上述背景条件，而且借助波谱曲线捕获到了湖泊水体与其他地物要素的TOA反射率差异，模型在精确刻画地物差异的同时，提高了提取结果的可靠性。

LWDM在建立时既考虑了可鲁克湖流域内水体在可见光波段，特别是蓝光与绿光波段反射率相对较强，在近红外与短波红外强吸收的特征，又考虑了DN值在表征地物时失真的不足。模型建立过程中采用差值运算方法并引入较多的波段，一方面可以有效避免由于比值运算造成局部信息丢失的现象；另一方面引入多波段可以探测到更多的水体微细变化信息，对与柴达木盆地相似的不同矿化度湖泊水体信息并存的区域，可取得比NDWI、MND-WI更好的提取效果。在阈值选择方面，有学者采用神经网络技术自动计算样本阈值，得到了水体信息自动提取模型，但该方法容易得到局部极小值而延长计算时间，而本文提出的LWDM模型将提取湖泊水体信息的阀值设定为0，与NDWI和MNDWI在局部地区信息提取时需要调整阈值2操作及采用神经网络技术导致计算时间较长相比，LWDM提取湖泊水体信息操作更加便捷。

为了考证LWDM的适用性，选择柴达木盆地以外位于不同地区的天池、太湖、滇池作为验证对象，利用LWDM对其周边区域的湖泊水体信息进行了提取，借助总体分类精度OA、Kappa系数及用户精度对提取结果进行了精度评价(表3)，由表3可知，天池的提取结果较好，太湖和滇池的效果稍差，原因是太湖和滇池的水质相对较差，说明LWDM模型对清洁水体的适用性较好，而对受污染水体的适用性相对较差，前期笔者对太湖含蓝藻水体进行了专题研究，提出了基于Landsat影像的含蓝藻水体提取方法（Blue $^ +$ Green-Red-SWIR1-SWIR $2 { > } 0$ )[50]，通过对比发现，提取结果优于NDWI、MNDWI、MBWI、NWI、WI2o1s,后续针对不同清洁度的湖泊水体信息，还需要对模型进行完善，以提高其适用性。利用MODIS数据（成像时间，2005年5月25日）进一步对LWDM的适用性进行分析，选择盆地内外的哈拉湖、青海湖作为试验对象，对提出的水体提取指数进行了试验验证，采用LWDM提取了2个湖泊水体，提取结果的总体分类精度为 $9 9 . 8 1 \%$ ,Kaapa系数为0.9973，用户精度 $9 9 . 7 8 \%$ ，说明对于不同的传感器，在青藏高原地区该方法也有较好的适用性。

由于湖泊水体信息受制于多种因素，当前的研究方法尚不能完成全面、系统的湖泊水体信息提取，特别是对较差水质的湖泊水体信息，模型还有待进一步完善。本文基于前人的研究成果，对柴达木盆地的湖泊水体分布自动提取方法进行了探索性研究，后续还要在以下2个方面加强研究：一是引人机器学习等人工智能技术，自动识别青藏高原湖泊水体与冰雪、沼泽湿地、阴影等要素的TOA反射率差异，完善湖泊水体信息提取模型，将其应用到塔里木盆地、云贵高原、四川盆地等不同区域，在应用中不断改进模型，增强模型的普适性；二是考虑SPOT、QuickBird、ASTER、IKONOS及国产高分辨率对地观测等卫星遥感数据，采用多源遥感影像数据融合技术，关注气象变化与人类活动的影响，提高湖泊水体分布信息的提取精度，进而为湖泊水体动态变化及其周边区域生态环境演化提供理论与技术支撑。

表3滇池、太湖、天池湖泊水体信息提取精度评价结果  
Tab.3Evaluationresultsofwaterbody informationextractionaccuracyof DianchiLake,TaihuLakeandTianchiLake   

<html><body><table><tr><td>实验区域</td><td>传感器</td><td>成像时间/年-月-日</td><td>方法</td><td>0A/%</td><td>Kappa</td><td>用户精度/%</td></tr><tr><td>滇池</td><td>OLI</td><td>2021-03-25</td><td>LWDM</td><td>90.13</td><td>0.6295</td><td>89.86</td></tr><tr><td>太湖</td><td>OLI</td><td>2021-06-23</td><td></td><td>96.03</td><td>0.8185</td><td>96.32</td></tr><tr><td>天池</td><td>OLI</td><td>2021-06-18</td><td></td><td>99.79</td><td>0.9413</td><td>99.82</td></tr></table></body></html>

# 4结论

本文基于Landsat系列遥感影像，通过对比分析可鲁克湖流域不同地物要素的TOA反射率差异，建立了基于Landsat影像的湖泊水体分布自动提取方法一一湖泊水体差分模型(LWDM)，将该方法应用于柴达木盆地、青海湖、尕海湖、太湖、天池、滇池等湖泊水体信息提取，并分析了同一卫星不同传感器、不同成像时间、不同卫星不同传感器的提取结果。主要结论如下：

（1）在统计分析的基础上，根据地物在遥感影像不同波段的TOA反射率差异特征，通过增强目标地物信息，抑制非目标地物信息，可以有效提取所需信息。

（2）基于TOA反射率差异特征提出的湖泊水体差分模型(LWDM)可以用稳定的阀值(O)实现区域湖泊水体信息的快速提取，与NDWI、MNDWI等方法相比，在柴达木盆地内，该方法能有效抑制地表河流、冰雪、沼泽湿地、阴影等干扰因素，显著提高湖泊水体信息提取的精度。

（3）基于Landsat系列卫星影像，LWDM可用于柴达木盆地湖泊水体分布快速识别，基于不同传感器不同时期的遥感影像，通过对比不同湖泊提取结果,OA达到 $9 9 . 4 8 \%$ ,Kappa值达到0.9877,用户精度达到 $9 9 . 6 6 \%$ 。基于不同卫星传感器，利用MODIS遥感影像数据，提取了青海湖和哈拉湖水体信息，OA达到 $9 9 . 8 1 \%$ ,Kappa值达到0.9973,用户精度达到$9 9 . 7 8 \%$ ,结果具有较高的可信度，可为柴达木盆地湖泊水体动态监测及湖泊周边生态环境保护提供技术支持。

# 参考文献(References):

[1]曹国亮,李天辰,陆垂裕,等.基于遥感的湖泊水域动态变化监 测研究进展[J].遥感技术与应用,2009,24(5):674-684.[Cao Guoling,Li Tianchen,Lu Chuiyu,et al.Dynamic variation and evaporation of seasonal lakes in arid areas:A case study for the Aiding Lake[J]. Arid Zone Research,2020,37(5): 674-684.]   
[2] 杨桂山，马荣华,张路，等.中国湖泊现状及面临的重大问题与 保护策略[J].湖泊科学,2010,22(6):799-810.[Yang Guishan, Ma Ronghua,Zhang Lu,et al.Lake status,major problems and protection strategy in China[J]. Journal ofLake Sciences,2O10,22 (6): 799-810.]   
[3]卢娜.柴达木盆地湖泊面积变化及影响因素分析[J].干旱区资 源与环境,2014,28(8):83-87.[Lu Na. Changes of lake area in Qaidam basin and the influence factors[J]. Journal of Arid Land Resources and Environment, 2014,28(8): 83-87.]   
[4]王永贵,李义民,刘丽峰,等.对柴达木盆地形成过程的初步探 讨[J].青海科技,2007,14(5): 24-26.[Wang Yonggui,Li Yimin, Liu Lifeng,etal.Preliminary discussion onthe formation process of the Qaidam Basin[J]. Qinghai Science and Technology,2007,14 (5): 24-26.]   
[5]董斯扬,薛娴,尤全刚,等.近40年青藏高原湖泊面积变化遥感 分析[J].湖泊科学,2014,26(4): 535-544.[Dong Siyang, Xue Xian, You Quangang,et al.Remote sensing monitoring ofthe lake area changes in the Qinghai-Tibet Plateau inrecent 4O years[J]. Journal of Lake Sciences,2014,26(4) : 535-544.]   
[6]胡争光,王祎婷,池天河,等.基于混合像元分解和双边界提取 的湖泊面积变化监测[J].遥感信息,2007(3):34-38.[Hu Zhengguang,Wang Yiting,Chi Tianhe,et al. Monitoring lake areas based on mixed pixel decomposition combined with double-edge extraction[J]. Remote Sensing Information,2007(3): 34-38.]   
[7]段水强.1976—2015年柴达木盆地湖泊演变及其对气候变化 和人类活动的响应[J].湖泊科学,2018,30(1):256-265.[Duan Shuiqiang.Lake evolution in the Qaidam Basin during 1976-2015 and their changes in response to climate and anthropogenic factors [J]. Journal of Lake Sciences,2018,30(1): 256-265.]   
[8]丁永建,刘时银,叶柏生,等.近50a中国寒区与旱区湖泊变化 的气候因素分析[J].冰川冻土,2006,28(5):623-632.[Ding Yongjian,Liu Shiyin,Ye Bosheng,etal. Climatic implications on variations of lakes in the cold and arid regions of China during the recent 50 years[J]. Journal of Glaciology and Geocryology,2006, 28(5): 623-632.]   
[9]张超,韩琳,陈亮.柴达木盆地湖泊水面变化遥感监测分析[J]. 人民黄河,2010,32(12): 54-55.[Zhang Chao,Han Lin,Chen Liang.Remote sensing monitoring and analysis of lake surface changes in Qaidam Basin[J]. Yellow River,2010,32(12): 54-55.]   
[10] 徐浩杰,杨太保.1981—2010年柴达木盆地气候要素变化特征 及湖泊和植被响应[J].地理科学进展,2013,32(6):868-879. [Xu Haojie, Yang Taibao.Climate factors change and its impact on lake area and vegetation growth in the Qaidam Basin during 1981-2010[J]. Progress in Geography,2013, 32(6): 868-879.]   
[11] 魏善蓉,金晓媚,王凯霖,等.基于遥感的柴达木盆地湖泊面积 变化与气候响应分析[J].地学前缘,2017,24(5):427-433.[Wei Shanrong,Jin Xiaomei,Wang Kailin,etal.Response of lake area variation to climate change in Qaidam Basin based on remote sensing[J]. Earth Science Frontiers,2017,24(5): 427-433.]   
[12] Jiang H,Feng M, ZhuY,et al.Anautomated methodfor extracting rivers and lakes from landsat imagery[J]. Remote Sensing,2014,6 (6): 5067-5089.   
[13]Olmanson L G, Bauer M E,Brezonik PL.A 2O-year landsat water clarity census of Minnesota’s 1OooO lakes[J]. Remote Sensing of Environment,2008,112(11): 4086-4097.   
[14] Li W,Du Z,Ling F,et al.Acomparisonof land surface water mapping using the normalized diference water index from TM,ETM $^ +$ and ALI[J]. Remote Sensing,2013,5(11): 5530-5549.   
[15]Mcfeeters S K.Using the Normalized Difference Water Index (NDWI) within a geographic information system to detect swimming pools for mosquito abatement: A practical approach[J]. Remote Sensing,2013,5(7): 3544-3561.   
[16] 黄帅,宋开宏,罗菊花,等.基于梯度变换的浅水湖泊围网区遥 感提取算法[J].湖泊科学,2017,29(2): 490-497.[Huang Shuai, Song Kaihong,Luo Juhua, et al.A remote sensing extraction algorithm of enclosure culture area in shalow lakes based on gradient transform[J]. Journal ofLake Sciences,2017,29(2): 490-497.]   
[17]Jupp D L B, Mayo K K,Kucher D.A. et al. Landsat Based Interpretation of the Cairns Section of the Great Barrier Reef Marine Park[R]. CSIRO Division of Water & amp; Land Resources, 1985.   
[18] 陆家驹,李士鸿.TM资料水体识别技术的改进[J].环境遥感, 1992,7(1): 17-23.[Lu Jiaju,Li Shihong.Improvement of the techniques for distinguishing water bodies from TM data[J]. Environmental Remote Sensing 1992,7(1): 17-23.]   
[19]McFeeters S K.The use of the Normalized Diffrence Water Index (NDWI) in the delineation of open water features[J]. International Journal of Remote Sensing,1996,17(7): 1425-1432.   
[20] 杨存建,徐美,黄朝远,等.遥感信息机理的水体提取方法的探 讨[J].地理研究,1998,17(增刊):86-89.[Yang Cunjian,Xu Mei, Huang Chaoyuan,et al.Approaches of water extraction based on remote sensing[J]. Geographical Research,1998,17(Suppl. ): 86- 89.]   
[21] 徐涵秋.利用改进的归一化差异水体指数(MNDWI)提取水体信 息的研究[J].遥感学报,2005,9(5):589-595.[Xu Hanqiu.A study on information extraction of water body with the Modified Difference Water Index(MNDWI)[J]. National Remote Sensing Bulletin, 2005,9(5): 589-595.]   
[22]闫霈,张友静,张元.利用增强型水体指数(EWI)和GIS 去噪音 技术提取半干旱地区水系信息的研究[J].遥感信息,2007(6): 62-67.[Yan Pei, Zhang Youjing, Zhang Yuan. A study on information extraction of water system in semi-arid regions with the Enhanced Water Index(EWI) and GIS based noise remove techniques [J]. Remote Sensing Information, 2007(6): 62-67.]   
[23]丁凤.基于新型水体指数(NWI)进行水体信息提取的实验研究 [J].测绘科学,2009,34(4):155-157.[Ding Feng.Study on information extraction of water body with a New Water Index(NWI)[J]. Science of Surveying & Mapping,2009,34(4): 155-157.]   
[24] 王晴晴,余明.基于简单比值型水体指数(SRWD)的水体信息提 取研究[J].福建师范大学学报(自然科学版),2014,30(1):39- 44.[Wang Qingqing,Yu Ming. Study on information extraction of water body based on Simple Ratio of Water Index (SRWI)[J]. Journal of Fujian Normal University (Natural Science Edition),2014, 30(1): 39-44.]   
[25] 丁占峰,李大军.基于ONDWI水体指数的鄱阳湖水域信息提取 [J].安徽农业科学,2015,43(6): 348-350.[Ding Zhanfeng, Li Dajun. The water region extraction of the Poyang Lake based on the ONDWI[J]. Journal of Anhui Agricultural Sciences,2O15,6(6): 348-350.]   
[26] 朱金峰,王乃昂,李卓仑,等.巴丹吉林沙漠湖泊季节变化的遥 感监测[J].湖泊科学,2011,23(4):657-664.[Zhu Jinfeng,Wang Nai'ang, Li Zhuolun, et al.RS-based monitoring seasonal changes of lake in Badain Jaran Desert[J]. Journal of Lake Sciences,2011, 23(4): 657-664.]   
[27] 金晓媚,高萌萌,柯珂,等.巴丹吉林沙漠湖泊遥感信息提取及 动态变化趋势[J].科技导报,2014,32(8):15-21.[Jin Xiaomei, Gao Mengmeng,KeKe,et al.Extractionof remote sensing information of lakes in Badan Jaran Desert and trend of their dynamic changes[J]. Science & Technology Review,2014,32(8): 15-21.]   
[28] 莫伟华,孙涵.MODIS水体指数模型(CIWI)研究及其应用[J]. 遥感信息,2007(5):16-21.[Mo Weihua,Sun Han.Research on the CIWI model and its application[J]. Remote Sensing Information, 2007(5): 16-21.]   
[29] 杨宝钢,陈昉,罗擎擎.基于MODIS 的改进型组合水体指数 (MCIWI)提取复杂水体信息的试验[J].西南大学学报（自然科 学版）,2011,33(1): 112-119.[Yang Baogang,Chen Fang,Luo Zizi.A study on information extraction of water body with the modified-combined index using MODIS data[J].Journal of Southwest University (Natural Science Edition),2011,33(1): 112-119.]   
[30] 章斯腾,陆欣,陆瑶,等.青藏高原河流网络高分CubeSat遥感 监测[J].遥感学报,2021,25(10):2142-2152.[Zhang Siteng,Lu Xin,LuYao,etal.Tracking dynamic river networks in the Tibetan Plateau with high-resolution CubeSat imagery[J]. National Remote Sensing Bulletin, 2021,25(10): 2142-2152.]   
[31]Li Ming, Zheng Xiaoshen.A Second Modified Normalized Difference Water Index (SMNDWI) in the case of extracting the shoreline[J]. Marine Science Bulletin,2016,18(2): 15-27.   
[32]Mallinis G,Koutsias N,Tsakiri-Strati M,etal.Object-based clasification using Quickbird imagery for delineating forest vegetation polygons in a mediterranean test site[J]. ISPRS Journal of Photogrammetry and Remote Sensing,2008,63(2): 237-250.   
[33] 聂欣然,刘荣,杜神斌.一种经验型归一化差异水体指数模型 [J].北京测绘,2017,31(5):41-45.[Nie Xinran,Liu Rong,Du Shenbin.A kind of water extraction model based on empirical normalized difference water index[J]. Beijing Surveying and Mapping, 2017, 31(5): 41-45.]   
[34] 曹荣龙,李存军,刘良云.基于水体指数的密云水库面积提取及 变化监测[J].测绘科学,2008,33(2):158-160.[Cao Ronglong,Li Cunjun,Liu Liangyun. Extracting Miyun reservoir swater area and monitoring itschangebasedonrevised normalized diferent water index[J]. Science of Surveying and Mapping, 2008,33(2):158- 160.] [35]陆吉贵.利用组合水体指数(NCIWI)提取水体信息研究[J].安徽 农业科学,2018,46(3):49-52.[Lu Jigui.Information extraction of water body with the new combined index using MODIS data[J]. Journal of Anhui Agricultural Sciences,2018,46(3): 49-52.] [36] 刘晓雪,温忠辉,束龙仓,等.近40年可鲁克湖-托素湖面积变 化及影响因素分析[J].水资源保护,2014,30(1):28-33.[Liu Xiaoxue,Wen Zhonghui, Shu Longcang,et al.Analysis of surface area changes of Keluke and Tuosu lakes over past 4O years and influencing factors[J]. Water Resources Protection,2014,3O(1): 28-33.] [37] 骆成凤,许长军,曹银璇,等.1974—2016年青海湖水面面积变 化遥感监测[J].湖泊科学,2017,29(5):1245-1253.[Luo Chengfeng,Xu Changjun, Cao Yinxuan,et al.Monitoring of water surface area in Lake Qinghai from 1974 to 2016[J]. Journal of Lake Sciences,2017,29(5): 1245-1253.] [38] 刘雅清,王磊,赵希妮,等.基于GF-1/WFV时间序列的绿洲作 物类型提取[J].干旱区研究,2019,36(3):781-789.[Liu Yaqing,Wang Lei, Zhao Xini, et al. Extraction of crops in oasis based on GF-1/WFV times series[J].Arid Zone Research,2019,36(3):   
781-789.] [39] 杨桄,刘湘南.遥感影像解译的研究现状和发展趋势[J].国土资 源遥感,2004,16(2):7-10.[Yang Guang,Liu Xiangnan.The present research condition and development trend of remotely sensed imagery interpretation[J]. Remote Sensing for Land & Resources,   
2004,16(2): 7-10.] [40] 王永贵,郭宏业,李健,等.柴达木盆地地下水资源及其环境问 题调查评价[M].北京:地质出版社,2008:191.[Wang Yonggui, Guo Hongye,Li Jian,et al.Investigation and Assessment of Groundwater Resources and Their Environment Issue in the Qaidam Basin[M]. Beijing: Geological Publishing House,2008: 191.] [41]Ko B C, Kim HH, Nam JY. Classification of potential water bodies using Landsat 8 OLI and a combination of two boosted random forest classifiers[J].Sensors,2015,15(6): 13763-13777. [42]Foody G M. Status of land cover classification accuracy assessment [J.Remote Sensing of Environment, 2002,80(1): 185-201.   
[43]Lark R M. Components of accuracy of maps with special reference to discriminant analysis on remote sensor data[J]. International Journal of Remote Sensing,1995,16(8): 1461-1480.   
[44] Stehman S V.Selecting and interpreting measures of thematic classification accuracy[J]. Remote Sensing of Environment, 1997,62 (1): 77-89.   
[45]赵英时.遥感应用分析原理与方法[M].北京:科学出版社, 2003.[Zhao Yingshi. Principles and Methods of Remote Sensing Applied Analysis[M].Beijing:Science Press,2003.]   
[46]文广超.巴音河流域地下水文过程及其生态效应[D].西安:长 安大学,2O18.[Wen Guangchao.Groundwater Hydrological Processes and Its Ecological Effects in Bayin River Basin[D].Xi'an: Chang'an University,2018.]   
[47]Murat K,Nihal C.The spectral reflectance responses of water with diferent levels of suspended sediment in the presence of algae[J]. Turkish Journal of Engineering and Environmental Sciences, 2005,29(6): 351-360.   
[48]孙章丽.达里诺尔湖水体光谱测量与分析[J].安徽农业科学, 2013,41(9): 4182-4186.[Sun Zhangli. Measurement and analysis of water spectrum in Dalinuoer Lake[J]. Journal of Anhui Agricultural Sciences,2013,41(9): 4182-4186.]   
[49] 申茜,张兵,李俊生,等.太湖水体反射率的光谱特征波长分析 [J].光谱学与光谱分析,2011,31(7):1892-1897.[Shen Qian, Zhang Bing,Li Junsheng,et al. Characteristic wavelengths analysis for remote sensing reflectance on water surface in Taihu Lake [J]. Spectroscopy and Spectral Analysis,2011,31(7): 1892-1897.]   
[50] 王琳,谢洪波,文广超,等.基于Landsat8 的含蓝藻湖泊水体信 息提取方法研究[J].国土资源遥感,2020,32(4):130-136. [Wang Lin,Xie Hongbo,Wen Guangchao,et al.A study on water information extraction method of cyanobacteria lake based on landsat8[J].Remote Sensing for Land and Resources,2O2O,32(4): 130-136.]

# An automatic method for delineating lake surfaces in Qaidam Basin using Landsat images

WEN Guangchao， LI Xing， WU Bingjie， WANG Xiaohe， XIE Hongbo Institute of Resource and Environment,HenanPolytechnic University,Jiaozuo 4540oo,Henan, Chin&

Abstract: Lakes in the Qaidam Basin maintain regional ecological balance,supply production and domestic water consumption,and protect the ecological environment. These lakes have undergone a series of changes in response to enhanced regional climate change and human activities.To analyze characteristics of lake changes and investigate casual factors, an automatic method for lake surface delineation based on Landsat remote sensing images with a different series of sensors (the Lake Water Diffrential Model) was proposed by understanding TOA (top-of-atmosphere)reflectance diferences between water and non-water surfaces in the Koruk Lake Basin. This model is applied to extract lake information at varying times or locations.Model performance is evaluated using overallaccuracy,the Kappa coefficient,and user's accuracy,and the derived lake surfaces were compared to those from the NDWI(Normalized Diference Water Index) and MNDWI (Modified Normalized Difference Water Index) methods.These results show the folowing: (l)target and non-target objects are distinguished bya TOA reflectance difference. (2) Based ona stable threshold, the Lake Water Differential Model can delineate lake surfaces.Compared with the NDWI, MNDWI,and other water body information extraction methods,the Lake Water Differential Model can more effectively suppress interference factors,such as surface rivers,ice, snow, shadows,swamps,and wetlands.In areas of model application,our proposed method can achieve a performance of $9 9 . 4 8 \%$ of the average OA, $9 9 . 6 6 \%$ of user accuracy, and O.9877 of Kappa. (3) Input data of the model can be either TOA or Landsat (level-2） surface reflectance data.(4) The model is suitable for extracting lake water information in a large area of Qaidam Basin and provides technical support for the study of lake surface dynamics. Keywords: Landsat; lake； TOA reflectance; lake water differential model; Qaidam Basin