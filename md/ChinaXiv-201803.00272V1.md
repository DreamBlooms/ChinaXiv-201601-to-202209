# DOI: 10.5846/stxb201701180155

张泽民,吕昌河,谢苗苗,周伟.基于WorldView 2影像的矿区植被重建效果评估.生态学报,2018,38(4):1301-1310.ZhangZM,LieZaofeatstitsngresacta2018,38(4) :1301-1310.

# 基于WorldView2影像的矿区植被重建效果评估

张泽民1,²,吕昌河1,²，谢苗苗，\*，周伟,4

1中国科学院地理科学与资源研究所，北京100101  
2中国科学院大学，北京100049  
3中国地质大学(北京)土地科学技术学院，北京100083  
4国土资源部土地整治重点实验室，北京100035

摘要;植被盖度反映植被质量,是评价矿区复垦土地植被重建效果的重要指标。该文选择安太堡矿区为案例区,基于高空间分辨率WorldView 2（WV2)影像新波段,使用混合像元模型和实地数据验证相结合的方法计算得到研究区的植被盖度，并对植被重建效果进行了评估，主要得到以下结论：(1)基于WV2影像的近红外2波段和红波段,采用混合像元法得到的植被盖度反演值 $F c _ { 2 }$ 与实测值最为接近,相关性最强( $R ^ { 2 } = 0 . 9 3 4 ^ { ^ { \cdot } }$ ),均方根误差最小( $\mathrm { R M S E } = 0 . 0 4 8 )$ ;(2)研究区植被重建效果整体较好,中等、较高和高植被盖度区域占研究区的 $6 0 \%$ 以上,低植被盖度仅占 $2 2 . 0 9 \%$ 。受植被重建年限和管理措施的影响,不同复垦区域植被重建状况之间存在着差异,内排土场、西排土场、南排土场的植被重建效果较好,而西排土场扩大区植被状况相对较差,其中等及以上植被盖度所占比例依次为 $7 5 . 2 4 \%$ ， $6 8 . 3 5 \%$ ， $6 8 . 2 0 \% . 2 2 . 2 9 \%$ 。（3)就植被组合模式看,乔灌草模式重建效果(按冠层盖度)最好,其次是乔草模式,其他模式如灌草、草地、自然恢复地依次降低。土壤表层水分含量随着复垦地植被盖度的增大而增大,说明植被重建状况对土壤表层的水分保持具有重要作用。

关键词：WorldView2;植被盖度;安太堡矿;混合像元模型

# Evaluation of vegetation restoration effects in mining areas based on WorldView 2 images

ZHANG Zemin1,²，LU Changhe1,²，XIE Miaomiao3\*， ZHOU Wei3,4

1InstituteofGeographic SciencesandNaturalResourcesResearch，ChineseAcademyofSciences，Beijing10olo1,China   
2 University Chinese Academy of Sciences，Beijing 10oo49，China   
3 College of Land Scienceand Technology，China Universityof Geosciences （Beijing），Beijing 10oo83，China   
4 Key Laboratoryof Land Consolidationand Rehabilitation MinistryofLandand Resources，Beijing 10oo35，China

Abstract:Thevegetationcoverage fractionreflects thequalityofvegetationandis，thus，animportantindextoevaluate the vegetation restoration efect ofreclaimed land in miningareas.Thisstudy，considering Antaibao mining areas，evaluated the currency of diferent vegetation indices using the pixeldichotomymodel basedon thenew bandof WorldView2（WV 2) imagesand field-measured data，andthenabstracted the vegetationcoverage fraction of thestudyarea to indicate the vegetationrestoration effect.Theresultsshowthat（1）withanear-infrared 2andred-bandof WV2image，vegetation coverage fraction（ $\left( F c _ { 2 } \right)$ ）as calculated by the mixed-pixel method，was the closest to the field-measured values ( $R ^ { 2 } = 0 . 9 3 4$ ， RMSE $= 0 . 0 4 \&$ 3）.（2）The study areas had been wel restored as a whole:the vegetation coverage fraction was moderate-tohigh in more than $60 \%$ of the area，while in only $2 2 . 0 9 \%$ of the area was lower than $20 \%$ . Vegetation restoration affected by the durationand management measures differed among the plots：in Inner Dump，West Dump，and South Dump，better vegetation restoration was observed with moderate-to-high coverage，at $7 5 . 2 4 \%$ ， $6 8 . 3 5 \%$ ，and $6 8 . 2 0 \%$ ，respectively，than in the expanded West Dump ( $2 2 . 2 9 \%$ ).（3）The vegetation restoration pattern with the combination of grass，shrub，and tres hadthebestrestorationeffct,followedbythe inter-plantingofgrassandtrees，whilethecombinationofshrubgrass, onlygrass vegetation，andnatural restoration hadrelatively por efect.Thesoil moistureriseswith increasedvegetation coverage，implying that vegetation status plays an important role in soil surface-water retention.

Key Words:WorldView 2；vegetation coverage fraction；Antaibao mine；mixed pixel model

作为我国重要的能源,煤炭的大规模开采和利用在满足我国社会经济发展所需能源的同时也带来了严重的生态环境问题[1-3],尤其是露天煤矿,开采面积大、破坏性强,对当地的生态环境造成巨大的负面影响。作为矿区生态环境中最敏感的环境因子,植被是矿区生态系统全面恢复的关键,其生长状况会直接或间接影响到其他环境因子。因此快速、准确、有效地监测矿区复垦土地的植被重建效果,是科学评估和揭示复垦成效的重要手段[4]。

植被盖度是植被长势和质量的综合体现,是评价矿区复垦地土地植被重建效果的重要指标[5-8]。早期的植被盖度测量方法主要有目估法、照相法、采样法、仪器法等实地获取方法],虽然精度高但具有成本高、耗时长等缺点。上世纪七十以来,基于遥感技术的植被盖度提取方法得到快速发展,从早期基于Landsat MSS 5单一波段,通过简单线性回归来估算植被盖度[10],逐步深化,先后提出了多种基于 NOAA/A、TM、MODIS、SPOT等多波段影像的植被指数方法[1],如归一化植被指数 NDVI[1-15]、垂直植被指数 PV[16] $\mathrm { M V I } ^ { [ 1 7 ] }$ 、可见光抗大气指数VAR[18]、土壤调整植被指数 SAVI[19]修改型土壤调整植被指数 MSAVI[20],以及基于光谱混合分析（MSA)技术的像元分解模型方法[21-22]。这些指数和方法部分已在矿区复垦效果评估中得到应用,如 Liu等基于Landsat 影像,选择15期NDVI数据,对平朔安太堡煤矿复垦区植被长势变化进行了分析[23];胡振琪和陈涛基于Landsat TM影像得到的 NDVI指数使用像元二分模型估算榆林矿区植被盖度变化[24];赵云杰等采用基于 SMA方法得到的地表覆盖指数对晋西北河保偏矿区的植被退化进行的估测[25];苏伟等利用基于同种方法计算得到的植被盖度探讨了阜新市海州露天煤矿排土场多时相的植被生长状况及时空变化特征[26]。

以上数据和方法多基于空间分辨率较低的TM、MODIS 等影像,适用于较大区域的植被盖度反演。对于区域范围小、精度要求高的矿区植被恢复状况评估,难以满足要求。因此,本研究选择平朔矿区安太堡露天矿为案例区,基于高空间分辨率的WorldView 2（WV2)影像和实测数据,充分利用WV2影像新波段的优点,尝试采用混合像元模型方法,通过对比分析不同植被指数的盖度提取精度,确定适宜的指数方法,以此为基础，对案例区复垦地的植被重建效果进行评估,以期为复垦地植被恢复措施及闭矿后的土地复垦工作提供参考。

# 1研究区概况

安太堡露天煤矿位于山西省朔州市平鲁区境内(图1),属黄土丘陵区,生态脆弱。地形东北部高,西南部低,起伏较大;气候干旱,昼夜温差大,冬夏两季对比明显,多年平均降水量 $4 3 0 \mathrm { m m }$ 左右，并集中在7,8,9三个月份,夏季水土流失严重,平均年蒸发量是降水量的4—5倍,植被生长环境恶劣,主要地带性土壤为栗钙土、栗褐土、黄绵土。

自 20 世纪80年代投产以来,安太堡矿区挖损、塌陷、压占等行为不仅剧烈改变了原始地形和地层,而且对土壤和植被造成严重破坏[27]。安太堡煤矿开采后期,开始采取采、运、排、复一体化的模式,将采矿排弃的煤矸石堆积成高度差约为 $1 0 0 { - } 1 5 0 \mathrm { m }$ 的平台并覆上表土，每个台阶的高度差在 $2 0 { - } 4 0 \mathrm { m }$ 之间,间隔平台的斜坡坡面角一般大于 $3 0 ^ { \circ [ 2 8 ] }$ ,然后于各个平台和斜坡上相继进行了植被重建工作。研究区内共有四个排土场,即南排土场、西排土场、内排土场、西排土场扩大区(图1),不同排土场的复垦时间、年限和重建植被配置类型也存在着差别,其中,南排土场于1992年开始复垦,1997年停止复垦，面积为 $1 . 7 5 \mathrm { k m } ^ { 2 }$ ,主要植被类型为榆树、刺槐、油松、沙棘、紫花苜蓿及各种草类等;西排土场复垦始于1994年,终于1997年,面积约 $2 . 8 \mathrm { k m } ^ { 2 }$ ,植被配置模式为沙棘、新疆杨、榆树和草类间种或者套种;内排土场1997年开始复垦,是研究区内唯一的内排土场,复垦植被有沙棘、沙枣、榆树和和紫穗槐等;西排土场扩大区复垦时间最晚,开始于2001年,面积 $3 . 3 4 \mathrm { k m } ^ { 2 }$ ,植被类型以油松、榆树、沙棘为主,区域内自然恢复地面积较大[29]。各个排土场周边的防护林地带主要选取刺槐与榆树或新疆杨间种模式,中间套种柠条或沙棘[30]。

![](images/7664efe4a1c94063b84aa3b8902590ce849b9b75168a3a4189f6f177b1c2671b.jpg)  
图1研究区地理位置图  
Fig.1Schematic geographical location of study area

# 2数据与方法

# 2.1 数据源与预处理

该研究采用的遥感数据为2012年10月份的WV2影像，包括 $0 . 5 \mathrm { m }$ 空间分辨率的全色波段和由8个 $1 . 8 \mathrm { m }$ 分辨率的多光谱波段组成的多光谱影像(表1)[31-32]。WV 2影像的多光谱波段更加丰富,新增的4个彩色波段分别为海岸波段、黄色波段(红色边缘波段和近红外2波段。这4个波段可以直接或间接反映出植被生长状况，也可用于植被参数的反演,对于植被质量指标的定量计算和分析具有重要的意义,其中近红外2波段部分重叠在近红外1波段上,受大气的影响较小,可以增强植被特征,支持植被分析和植被生物量方面的研究。

表1WV2影像的波段介绍  
Table 1Spectrum range and spatial resolution WV 2 image bands   

<html><body><table><tr><td>波段 Band</td><td></td><td>波谱范围 Spectral range/μm 空间分辨率 Spatial resolution/m</td></tr><tr><td>海岸波段Coastal</td><td>0.40—0.45</td><td></td></tr><tr><td>蓝色波段 Blue</td><td>0.45—0.51</td><td></td></tr><tr><td>绿色波段Green</td><td>0.51—0.58</td><td></td></tr><tr><td>黄色波段Yellow</td><td></td><td>0.59—0.63 1.8</td></tr><tr><td>红色波段Red</td><td></td><td>0.63—0.69</td></tr><tr><td>红边波段Red Edge</td><td></td><td>0.71—0.75</td></tr><tr><td>近红外1NIR1</td><td></td><td>0.77—0.89</td></tr><tr><td>近红外2NIR2</td><td></td><td>0.86—1.04</td></tr><tr><td>全色波段 Panchromatic band</td><td></td><td>0.45—0.80</td></tr></table></body></html>

http://www.ecologica.cn

对遥感影像数据,首先进行辐射定标,确定遥感传感器每个波段的中心波长和带宽,将DN值转化为辐射亮度值;然后进行大气校正,消除大气散射、吸收、反射等引起的误差,转化为地表反射率;最后对影像数据进行几何校正、数据融合,预处理后的影像不仅具有多光谱波段的特点,而且空间分辨率提高到 $0 . 5 \mathrm { m }$ 。最后将整幅影像以研究区范围作为边界进行裁剪，得到研究区的真彩色影像。以2012年同月获取的MODIS 影像为数据源计算研究区的温度植被干旱指数 Temperature Vegetation Drought Index（TVDI）,并利用高程数据及实测的土壤干湿数据对反演结果进行校正[33-34]。植被种类分布图则以 WV 2 影像为数据源,利用监督分类方法得到研究区的植被种类配置图（图2）[35]。 2

![](images/7fdde13af9e752c882e050ff7a681a26363323582cc42ea64c7ce0d44ceab91f.jpg)  
图2安太堡排土场真彩色影像(a）、TVDI分布图(b)、植被种类(c)Fig.2True color image（a），TVDI distribution（b），vegetation types（c）of Antaibao dumps

# 2.2 冠层盖度反演

混合像元模型是在假设地表由纯植被覆盖与无植被覆盖地表两部分组成的前提下,将遥感影像的像元分为土壤和植被两部分,那么像元中植被覆盖的面积比例即为该像元的植被盖度。混合像元模型就是以此假设为基础将植被指数与像元二分模型相结合计算植被盖度所构建的模型[36]。传统的计算植被盖度的混合像元模型主要基于传统影像的红外波段 NIR与红色波段 $R$ 得到的归一化植被指数 NDVI进行计算(式1)。根据实地获得的裸地和全植被覆盖样点区域与遥感影像计算得到的对应值,确定置信区间,得出 NDVI和 NDVI值,利用式2计算得到整个研究区的植被盖度(式1）。

基于WV2影像特有的红边波段 $R E$ 、近红外2波段 NIR2与传统波段 $R$ 、NIR1组合计算得到不同形式的NDVI指数(式2—式4）。再根据实地获得的裸地和全植被覆盖样点区域与各不同计算方式得到的对应值，确定置信区间,得出各计算方式的 $\mathrm { N D V I } _ { v n }$ 和 $\mathrm { N D V I } _ { s n }$ 值,计算出基于不同波段组合得到的研究区植被盖度（式5）。

$$
\mathrm { N D V I } _ { 1 } = ( \mathrm { N I R } 1 - R ) / ( \mathrm { N I R } 1 + R )
$$

$$
\mathrm { N D V I } _ { 2 } = ( \mathrm { N I R } 2 { - } R ) / ( \mathrm { N I R } 2 { + } R )
$$

$$
\mathrm { \Delta N D V I { _ 3 } } = ( \mathrm { \Delta N I R } 2 { - } R E ) / ( \mathrm { \Delta N I R } 2 { + } R E )
$$

$$
\mathrm { \Delta N D V I { } } _ { 4 } { = } \left( \mathrm { \Delta N I R } 1 { - } R E \right) / \left( \mathrm { \Delta N I R } 1 { + } R E \right)
$$

$$
F c _ { _ n } = \frac { \mathrm { N D V I } _ { _ n } \ - \ \mathrm { N D V I } _ { _ { S n } } } { \mathrm { N D V I } _ { _ { v n } } \ - \ \mathrm { N D V I } _ { _ { S n } } } ( \ n = 1 , 2 , 3 , 4 )
$$

式中,NDVI第 $n$ 种波段组合计算得到的NDVI值， $F c _ { n } \ 、 \mathrm { N D V I } _ { s n } \ 、 \mathrm { N D V I } _ { v n }$ 分别为基于第 $\mathbf { \Omega } _ { n }$ 种波段组合计算得到

的像元植被盖度、裸地NDVI值、纯植被NDVI值。

# 2.3 精度验证

为定量评估基于不同波段组合得到的冠层盖度反演精度，选取研究区的4个永久样地进行布点,主要分布于南排土场。考虑到样点的植被分布,本研究在不同高度的平台上共布设103个样点。根据布设好的样点,进行实地数据采集。具体操作时,使用数码相机对样点所在地进行拍照,在拍照时尽量使相机垂直向上或向下拍摄,使照片能够正确反映植被垂直投影到地面的覆盖面积所占比例[37。同时,使用手持全球定位系统(GPS)实时定位,并记录每个样点的周边环境,以作数据筛选的参考因素。经整理,得到80个有效样点数据，使用图形处理软件PS CS5分析每个有效样点照片中植被所占比例,即为该样点所对应的实地植被盖度。

为了比较基于不同波段计算植被盖度的精度,将实地采集的数据与四组不同的反演结果进行叠加处理,使用 SPSS Statistics 20统计软件对实地植被盖度与四组结果分别进行相关性分析,并分别进行回归分析,得到两者之间的相关性系数 $( R )$ 和均方根误差（RMSE）[38-39]。 (575

$$
R = \frac { \displaystyle \sum _ { i = 1 } ^ { K } X _ { i } Y _ { i } - \frac { \sum _ { i = 1 } ^ { K } X _ { i } \sum _ { i = 1 } ^ { K } Y _ { i } } { K } \mathbb { O } \bigcap _ { \lambda = 1 } \mathbb { S } } { \sqrt { [ \displaystyle \sum _ { i = 1 } ^ { K } X _ { i } ^ { 2 } - \frac { \big ( \displaystyle \sum _ { i = 1 } ^ { K } X _ { i } \big ) ^ { 2 } \Big ] [ \displaystyle \sum _ { i = 1 } ^ { K } Y _ { i } ^ { 2 } - ( \frac { \displaystyle \sum _ { i = 1 } ^ { K } Y _ { i } } { K } ) ^ { 2 } ] } } } \mathcal { V }
$$

$$
\mathrm { R M S E } = \sqrt { \frac { 1 } { K } \sum _ { i = 1 } ^ { K } \ ( \left. Y _ { i } \right. \sqrt { - X _ { i } ) ^ { 2 } } ) }
$$

式中， $R$ 为相关系数,RMSE为均方根误差， $K$ 为样点个数,i为样点序号， $X$ 为影像植被盖度， $Y$ 为实地植被盖度。

# 3结果分析

# 3.1 结果及精度验证

根据上文描述的混合像元模型法,基于WV2影像新波段反演研究区的植被盖度。图3为分别基于WV2 不同波段组合得到的研究区植被盖度 $F c _ { 1 } , F c _ { 2 } , F c _ { 3 }$ 和 ${ F c } _ { 4 }$ 。从图3可以看出,不同波段组合得到的研究区植被盖度空间分布有一定的相似性,但也存在着明显差异。

表2展示了上述四种冠层盖度反演结果的精度。结果表明,基于WV2的近红外2波段和红波段得到的植被盖度反演结果 $\bar { F } c _ { 2 }$ 与实地真实的植被盖度相关性最强( $R = 0 . 9 5 8 \rangle$ ）,均方根误差最小( $\mathrm { ^ { - } R M S E } = 0 . 0 4 8$ )，其次为近红外1波段和红波段得到的反演结果 $F c _ { 1 } ( R = 0 . 9 2 8 )$ ,均方根误差RMSE为0.500，其他两种组合的精度较低(图4)。究其原因,可能是由于研究时点位于研究区植被生长季末期,植被叶片开始枯萎,叶绿素正逐渐被叶黄素替代,导致红边波段红移，此时的植被对红边波段和近红外2波段反射率出现相应调整等一系列复杂现象[40-41

表2实地测得与不同波段组合计算得到冠层盖度的相关性  
Table 2Correlation coefficients between the observed and estimated coverage:   

<html><body><table><tr><td></td><td>反演植被盖度 Estimated coverage fraction</td><td>Fc1</td><td>Fc2</td><td>Fc3</td><td>Fc4</td></tr><tr><td>实地植被盖度</td><td>样点数</td><td></td><td></td><td>80</td><td></td></tr><tr><td rowspan="3">Observed vegetation coverage</td><td>Pearson 系数及显著性(双侧)</td><td>0.928 **</td><td>0.958 **</td><td>0.458 **</td><td>0.667**</td></tr><tr><td>R²</td><td>0.913</td><td>0.934</td><td>0.326</td><td>0.492</td></tr><tr><td>RMSE</td><td>0.500</td><td>0.048</td><td>0.370</td><td>0.355</td></tr></table></body></html>

$F c _ { 1 } \ 、 F c _ { 2 } \ 、 F c _ { 3 } \ 、 F c _ { 4 }$ 分别为基于WV2影像的NIR1和 $R$ 、NIR2 和 $R$ 、NIR2和 $R E$ 、NIR1和 $R E$ 波段使用混合像元模型反演得到的植被覆盖度；$^ { * * }$ ：表示在0.01水平(双侧)上显著相关

![](images/208e0f4c71bc6dfafc41bbc887ba1fff78a44cfc41c092669d20e330edf9f7dd.jpg)  
图3基于WV2不同波段组合计算得到的研究区植被盖度分布图

Fig.3 Distribution map of vegetation coverage in the study area based on combinations of diferent WV2 ban

$F c _ { 1 } \ 、 F c _ { 2 } \ 、 F c _ { 3 } \ 、 F c _ { 4 }$ 分别为基于WV2影像的NIR1和 $R$ 、NIR2 和 $R$ 、NIR2和RE、NIR1和RE 波段使用混合像元模型得到的植被覆盖度

![](images/26b21ac45c1904c91a0b55025f20a5106f4f8f8307dfa2f93901b948974619f5.jpg)  
图4WV2影像与实地样点的植被盖度的散点图  
Fig.4Scater plot of vegetation coverage fraction obtained by WV 2 image and field measurements

# 3.2植被重建效果评估

基于上述的验证结果,利用WV2的近红外2波段和红波段,计算得到了研究区的植被盖度 $\left( F c _ { 2 } \right)$ 。结果显示,研究区中南排土场的大部和西排土场的中部区域颜色较深,植被盖度较高,植被重建状况较好;而南排土场西北部、内排土场南部和西排土场扩大区大部区域颜色较浅,在西排土场扩大区和南排土场的西北区域甚至出现了颜色较浅的亮白色,这些区域植被生长状况很差或基本无植被覆盖。使用Arc Map分别计算得到各个排土场的平均植被盖度,并将整个研究区的植被盖度分为5个等级,即低植被盖度(0—0.2）、较低植被盖度(0.2—0.4）、中植被盖度(0.4—0.6）、较高植被盖度(0.6—0.8）、高植被盖度(0.8—1.0)[42],绘制出整个研究区及各个排土场的植被盖度等级分布图（图5）。

从数量上来看，整个研究区的植被盖度平均值为0.407,中等以上植被盖度所占比例达到 $5 3 . 7 0 \%$ ，低植被盖度占整个研究区的 $2 2 . 0 9 \%$ ,较低和中植被盖度二者分别占整个研究区的 $2 4 . 2 2 \%$ 和 $3 2 . 4 7 \%$ ,较高和高植被盖度区域共占研究区的 $2 1 . 2 2 \%$ 。南排土场、西排土场、内排土场和西排土场扩大区的平均植被盖度分别为0.501、0.488、0.473和0.260,各排土场中等及以上植被盖度所占比例依次为 $6 8 . 2 0 \% . 6 8 . 3 5 \% . 7 5 . 2 4 \% . 2 2 . 2 9 \%$ （图5）。值得关注的是,西排土场扩大区植被盖度在0—0.2之间的比例高达 $4 7 . 1 1 \%$ ，仅该区域的低植被盖度区域占整个研究区的比例达 $1 6 \%$ ,贡献最大,而内排、西排和南排土场植被盖度在0一0.2之间的像元占整个研究区的总比重仅为 $6 . 0 9 \%$ 。因此,研究区中较高和高植被盖度主要集中在内排土场、西排土场和南排土场,而西排土场扩大区的较高和高植被盖度区域所占比例与其他3个排土场差距较大。从以上数据可以看出，不同排土场复垦区域之间存在着较大差异,内排土场、西排土场、南排土场的植被重建状况较好,西排土场扩大区状况相对较差，植被重建效果不佳。 2

![](images/2d28ee13ef634ac7c5f4f714e9c1ce7d82f03ae32fbdba22a9e3409f21fc8b77.jpg)  
图5研究区植被盖度分布状况和各排土场盖度等级状况

Fig.5Distributionof vegetationcoverage fractioninthestudyareaand compositionof diferentcoverage grades of each dump

# 3.3 效果分析

矿区复垦地植被重建效果的好坏主要受植被配置种类、复垦措施和复垦年限等立地条件的影响。采用遥感影像的监督分类方法对安太堡矿区植被复垦模式,即乔灌草(刺槐、杨树、柳树等乔木、紫花苜蓿、沙打旺、黄芪等草种)、灌草(沙棘、柠条、沙枣、紫花苜蓿)、乔草(榆树、杨树、柳树等乔木、紫花苜蓿）、草地(红豆草、冰草、紫花苜蓿)、自然恢复模式(裸地、黄芪、冰草等)五种类型[43]分类和分析发现,随着时间的推移及植被与环境因子的交替影响,重建植被复合配置模式的区域变得更加多样、层次结构更为复杂;而草地、乔木等单一复垦模式的区域植被类型和层次结构相对来说较为简单,生态环境较为脆弱。

在恢复年限和重建植被的配置模式方面,南排土场复垦时间最早,复垦区已形成相对完善的生态系统并趋于稳定状态,西排土场和内排土场紧随其后,并且主要以乔灌草、乔草等复合植被配置模式为主,而西排土场扩大区于2001年才开始复垦,复垦时间最晚,区域内以乔草和草地重建模式为主,并且自然恢复地较多,植被相对稀疏,因此南排土场的平均植被盖度最高,高植被覆盖度比例也最大,西排土场扩大区较低和低植被盖度像元所占比例比其他三个排土场大,重建效果相对较差。另一个因素是煤矸石自燃,煤矸石自燃会给复垦区的植被造成不可逆的伤害,而南排土场和西排土场发生的煤矸石自燃现象相对较多,导致地表植被遭受破坏,区内的植被状况良莠不均,因此相比内排土场,南排土场的高植被盖度比例较小,平均植被盖度较高[4]针对植被配置对植被重建效果的影响,本研究基于TVDI指数使用Arc Map 软件进行了分析。结果显示：植被盖度及复垦效果受复垦时植被种类配置的影响较大,植被盖度从大到小的植被组合类型依次是乔灌草、乔草、灌草、草地、自然恢复地,同时随着植被盖度增加,TVDI值出现减小的趋势(表3）,说明土壤表层的水分含量随着复垦地植被盖度的增大而增大,植被恢复对土壤表层的水分保持具有重要作用。

表3植被盖度与植被种类配置、TVDI之间的关系  
Table 3Changes in vegetation coverage fraction with different vegetation restoration types and TVDI   

<html><body><table><tr><td>植被种类配置 Vegetation types allocation</td><td>乔灌草 Combination of grass, shrub and trees</td><td>乔草 Inter-planting of grass and trees</td><td>灌草 Combination of shrub grass</td><td>草地 Grass vegetation</td><td>自然恢复地 Natural restoration vegetation</td></tr><tr><td>植被盖度平均值 Average vegetation coverage</td><td>0.780</td><td>0.666</td><td>0.413</td><td>0.358</td><td>0.290</td></tr><tr><td>温度植被干旱指数(TVDI) Temperature Vegetation Drought Index</td><td>0.359</td><td>0.398</td><td>0.455</td><td>0.460</td><td>0.469</td></tr></table></body></html>

TVDI值与土壤表层水分含量呈反比,TVDI值越低,土壤水分含量越高[45]

# 4结论与讨论

# 4.1结论

使用混合像元模型和实地数据验证相结合的方法,通过比较反演植被盖度不同波段组合的精度,得到植被盖度反演的最佳组合,并对反演结果进行统计分析,主要得到以下结论：

(1)基于WV2影像的近红外2波段和红波段计算得到的植被盖度反演值 $F c _ { 2 }$ 与实地的植被盖度最为接近,相关性最强( $R ^ { 2 } = 0 . 9 3 4 )$ ,两者间的均方根误差最小( $\mathrm { \ R M S E } = 0 . 0 4 8 )$ ，其次为基于近红外1波段和红波段得到的植被盖度反演值 $F c _ { 1 } ( R ^ { 2 } = 0 . 9 1 3 , { \mathrm { R M S E } } = 0 . 5 0 0 )$ 。

(2)研究区的植被重建状况整体较好,中等以上植被盖度区域共占研究区的 $6 0 \%$ 以上。受复垦年限、植被配置种类及矸石自燃等的影响,研究区内不同区域植被盖度之间存在着差异,南排土场、西排土场、内排土场和西排土场扩大区的平均植被盖度分别为0.501、0.488、0.473 和0.260,中等及以上植被盖度所占比例依次为 $6 8 . 2 0 \% . 6 8 . 3 5 \% . 7 5 . 2 4 \% . 2 2 . 0 9 \%$ ,内排土场、西排土场和南排土场的植被重建效果较好,而西排土场扩大区相对较差。

(3)植被盖度受复垦时植被种类配置的影响较大,植被盖度从大到小的植被种类依次为乔灌草,乔草,灌 草,草地,自然恢复地,并且随着植被盖度的增大,土壤表层的水分含量相应增加,说明植被重建有助于土壤表 层的水分保持。 ） C

# 4.2讨论

基于高空间分辨率和多光谱波段的特点，WV2影像在植被盖度反演方面具有明显的可行性。从反演的结果来看,经过若干年的复垦措施,研究区植被重建效果良好,说明采取复垦措施的区域植被状况要远比自然恢复的区域佳。但需要注意的是,对于局部区域,由于存在自燃或者其他胁迫因素,并不一定是复垦时间越久植被盖度越高,并且复垦区内部个别区域的植被生长状况仍不容盲目乐观,需要人工措施继续跟进养护。

分析其原因可能是因为当地气候条件比较恶劣，年降水量在 $4 0 0 \mathrm { { m m } }$ 以下,无法满足复垦植被的用水需求,因此复垦区植被重建时,宜选择当地有助于土壤表层保水保肥功能的灌木、乔木和草地等混合配置的种植模式,而不应选择外来植被种类或某类单一植被进行重建;加之复垦地多为煤矸石山,内部复杂的物理化学变化对植被生长状况影响较大,发热或自燃都会给植被造成不可逆的伤害,影响植被重建的效果。总之,受多种复杂因素的影响,复垦地植被重建是一个相当漫长的过程,亟需建立一套多指标、多时点的监测体系,准确监测植被生长状况,以对复垦地植被重建措施及闭矿后的土地复垦工作提出可行的建议。

# 参考文献（References）:

[1］常青,邱瑶,谢苗苗,彭建.基于土地破坏的矿区生态风险评价;理论与方法.生态学报,2012,32(16);5164-5174.  
[2]吴钢,魏东,周政达,唐明方,付晓.我国大型煤炭基地建设的生态恢复技术研究综述.生态学报,2014,34(11):2812-2820.  
[3]翟孟源,徐新良,江东,姜小三.1979—2010年乌海市煤矿开采对生态环境影响的遥感监测.遥感技术与应用,2012,27(6);933-940.  
[4］张鹏,赵洋,黄磊,胡宜刚,韩旭.植被重建对露天煤矿排土场土壤酶活性的影响.生态学报,2016,36(9);2715-2723.

http://www.ecologica.cn

[5］徐嘉兴,李钢,陈国良,赵华,渠俊峰.土地复垦矿区的景观生态质量变化.农业工程学报,2013,29(1)：232-239.  
[6]PurevdojTtish,saHndaYRelatioshisetwnpecetvegeatiooverdvgeatioindicsIteatioalJoualfRemote Sensing,1998,19(18):3519-3535.  
［7］周伟,曹银贵,白中科,王金满.煤炭矿区土地复垦监测指标探讨.中国土地科学,2012,26(1）:68-73.  
[8]李登科,范建忠,王娟.陕西省植被覆盖度变化特征及其成因.应用生态学报,2010,21(11);2896-2903.  
[9］程红芳,章文波,陈锋.植被覆盖度遥感估算方法研究进展.国土资源遥感,2008,20(1)：13-18.  
[10]Graetz R D,Pech RP,Davis A W. The & t and monitoring of sparsely vegetated rangelands using calibrated Landsat data.Journal of Remote Sensing,1988,9(7）:1201-1222.  
[11］贾坤,姚云军,魏香琴,高帅,江波,赵祥.植被覆盖度遥感估算研究进展.地球科学进展,2013,28（7):774-782.  
[12]CarlsopleOaewfctialgeatovedeotesigofi962(3): 241-252.  
[13]DeAlmedaES，BatistaG,DosSantosJRTemporalAnalysisofDandPrecipitationDataofSletedVegeatioCovesofoaISPRS International Archives of Photogrammetry and Remote Sensing Commission，1994,7(30）:B1-B7.  
[14]JacqineDcoeVegedtetindgadalsoseries.International Journal of Applied Earth Observationand Geoinformation,2010,12(S1):S3-S10.  
[15] RodriguesA，MarcalARS，Furlan D，BallsterMV，CunhaM.LandcovermapproductionforBrazlian Amazonusing NDVI SPOTVEGETATION time series. Canadian Jourmal of Remote Sensing，2013,39(4):277-289.  
[16]Richardson A J，Wiegand C L. Distinguishing vegetation from soil background information hotogrammetric Engineering and Remote Sensing，1977,43(12) :1541-1552.  
[17]McDaniel K C,， Haas R H. Assessing mesquite-grass vegetation condition from landsat. Photogra neering and Remote Sensing，1982,48(3): 441-450.  
18]GitelsoAAYark，dstovegritfotetiafvgefrctieotesingofit,2002,80(1) :76-87.  
[19] Huete A R.A soil-adjusted vegetation index（SAVI).Remo ironment，1988,25(3）:295-309.  
[20]QiJ,oiueteKerodlsteveateotesingoit9(2): 119-126.  
［21］高云,谢苗苗,付梅臣,曹翊坤.高原河谷城市植被时空变化及其影响因素一 -以青海省西宁市为例.生态学报，2014,34(5)：1094-1104.  
[22］李华朋,张树清,孙妍.基于光谱混合分析的城市植被覆盖度与地表温度关系的研究.中国科学院研究生院学报,2010,27(6)：739-747.  
[23]Liu X Y, Zhou W, Bai Z K. Vegetation ragechange and stability in large open-pit coal mine dumps in China during 1990-2015.EcologicalEngineering，2016,95:447-451.  
[24］胡振琪,陈涛.基于ERDAS 的矿区植被覆盖度遥感信息提取研究——以陕西省榆林市神府煤矿区为例.西北林学院学报,2008,23（2)：164- 167.  
[25］赵云杰,杨丹青,毛菲.晋西北河保偏矿区土地利用变化对土地退化风险的影响.中国水土保持科学,2010,8（5）:98-103.  
[26］苏伟,孙中平,李道亮,朱翔,郭祥云.基于多时相 Landsat 遥感影像的海州露天煤矿排土场植被时空特征分析.生态学报,2009,29（11)：5860-5868.  
[27］郭逍宇,张金屯,宫辉力,张桂莲,董志.安太堡矿区复垦地植被恢复过程多样性变化.生态学报,2005,25(4)：763-770.  
[28] 尚涛,才庆祥,张幼蒂,李克民.我国大型露天煤矿若干生产工艺问题分析.中国矿业大学学报,2005,34（2):138-142.  
[29] 王洪丹,王金满,曹银贵,卢元清,秦倩,王宇.黄土区露天煤矿排土场土壤与地形因子对植被恢复的影响.生态学报,2016，36(16)：5098-5108.  
[30] 王丽媛,郭东罡,白中科,上官铁梁.露天煤矿生态复垦区刺槐 $^ +$ 油松混交林下草本植物组成及空间分布格局.应用与环境生物学报,2012,18(3): 399-404.  
[31]Tarantidasell,veinoseliBaetareingoftdvieeliWide Area of Applications.Italy：National Council of Researches,2012.  
[32]ColiAaesSatisteaddof4sineuberotesingoftrocaloassapQucid-2sodi2//Procedingsof the1EEInterationalGeoscienceandRemoteSensingSymposium.Vancouver,BC,Canada；EEE,2011；65-2168.  
[33］杨曦，武建军,闫峰,张洁.基于地表温度-植被指数特征空间的区域土壤干湿状况.生态学报,2009,29(3)：1205-1216.  
[34］李正国,王仰麟,吴健生,张小飞.基于植被/温度特征的黄土高原地表水分季节变化.生态学报，2007,27(11)：4563-4575.  
[35］徐艳芳，王克林，祁向坤,岳跃民,童晓伟.基于TM影像的白云岩与石灰岩上喀斯特植被时空变化差异研究.生态学报，2016,36(1)：180-189.  
[36]丁关青,陈松岭,郭云开.基于遥感的土地复垦植被覆盖度评价.中国土地科学,2009,23(1)：72-75.  
[37］胡健波,张璐,黄伟,吴世红,刘长兵.基于数码照片的草地植被覆盖度快速提取方法.草业科学,2011,28(9)：1661-1665.  
[38]崔天翔,宫兆宁,赵文吉,赵雅莉,林川.不同端元模型下湿地植被覆盖度的提取方法——以北京市野鸭湖湿地自然保护区为例.生态学报,2013,33(4):1160-1171.  
[39］谢秋霞,孙林,韦晶,李秀瑞.基于遥感估算方法的干旱区植被覆盖度适应性评价.生态学杂志,2016,35(4):117-1124.  
[40]HorlerDockayarbreedgefpantafrflctace.IteratioalJoualofemoteSensing98，42）8.  
[41] 卢艳丽,李少昆,白由路,谢瑞芝,宫永梅.冬小麦冠层光谱红边参数的变化及其与氮素含量的相关分析.遥感技术与应用，2007,22（1)：1-7.  
[42］李晓琴,孙丹峰,张凤荣.基于遥感的北京山区植被覆盖景观格局动态分析.山地学报,2003（03）：272-280.  
[43］张耀,周伟.安太堡露天矿区复垦地植被覆盖度反演估算研究.中南林业科技大学学报,2016,36(11):113-119.  
[44]樊文华,李慧峰,白中科,乔俊耀,许建伟.黄土区大型露天煤矿煤矸石自燃对复垦土壤质量的影响.农业工程学报,2010,26(2):319-324.  
[45]王纯枝,毛留喜,何延波,韩丽娟,陈健,宇振荣.温度植被干旱指数法(TVDI)在黄淮海平原土壤湿度反演中的应用研究.土壤通报,2009,40(5):998-1005.