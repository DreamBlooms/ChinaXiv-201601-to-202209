# DOI:10.5846/stxb201703290545

宫大鹏,李炳怡,刘晓东.草原火烧严重度燃烧指数的适用性比较分析.生态学报,2018,38（7)：2434-2441.   
GongDPtiloliisicta（ 2434-2441.

# 草原火烧严重度燃烧指数的适用性比较分析

宫大鹏，李炳怡，刘晓东北京林业大学林学院，北京100083

摘要：基于遥感影像的燃烧指数被广泛应用于火烧严重度(fire severity)研究,选取适宜燃烧指数定量评估草原火烧严重度,对草原生态系统植被的恢复与管理具有重要意义。以呼伦贝尔草原火烧迹地为研究区域，基于landsat8OLI影像分别构建4种燃烧指数（NBR、NSTV1、dNBR和 RdNBR)与综合燃烧指数(CBI)的回归模型并进行精度验证,对比分析不同燃烧指数识别草原火烧严重度等级的能力。结果表明：在燃烧指数与CBI构建的回归模型中,dNBR 指数的相关性 $( n = 7 0 , R ^ { 2 } = 0 . 8 5 6 )$ 最高；4种燃烧指数识别火烧严重度的精度存在差异，中度火烧区域( $1 { \mathrm { < C B I } } \leqslant 2 \$ )内，NSTV1指数识别精度最高，未过火（ $\mathrm { C B I } = 0$ ）、轻度火烧( $0 <$ $\mathrm { C B I } \leqslant 1$ )和重度火烧( $2 \mathrm { < C B I } \leqslant 3$ )区域内,dNBR指数识别精度均表现最好，分别为 $8 0 \% , 6 2 . 5 \%$ 和 $1 0 0 \%$ ;基于不同燃烧指数的草原火烧严重度制图中,dNBR 指数的总体精度同样高于其他燃烧指数,为 $8 2 . 1 \%$ ,Kappa 系数高达 $0 . 7 6 _ { \odot }$ 。综上所述,dNBR 指数是草原火烧严重度分析与评价的适宜遥感指数。 0

关键词：草原火；火烧严重度;Landsat8 影像;燃烧指数;差分归一化燃烧率

# Comparative analysis of burn index adaptability when evaluating grassland fire severity

GONG Dapeng，LI Bingyi，LIU Xiaodong CollgeofForestry，BeijingForestry University，BeijinglOoo83，China

Abstract:Theburn index，based onremote sensing images，is widelyusedtostudy fireseverity.Thequantitative evaluation of grassland fireseveritybyselecting asuitable burn indexhasgreat significance when studying vegetation recoveryand management.A burnt area of Hulunbuir pasture land was selected as the study area.Landsat8 OLI images were used todevelop a regresson model of the Composite Burn Index（CBI）using four different burn indices（Normalized Burn Ratio，NBR；NIR-SWIR-Temperature Version1，NSTV1；diferencedNormalized Burn Ratio，dNBR；and Relative diferenced Normalized Bum Ratio,RdNBR）,andtheacuracyofthe model was tested.Theabilitytodetect fireseverityat different levels by the four diferent burn indices was compared. The results showed that dNBR( $n = 7 0$ ， $R ^ { 2 } = 0 . 8 5 6$ ）had the best fiting efect inthe polynomial regression model；but there were some diferences between the fourburn indices when identifying grassland fire intensity at different levels.The NSTV1 index performed best at moderate severity ( $1 < \mathrm { C B I \leqslant }$ （20 2). For non-fire ( $\mathrm { C B I } = 0$ ），low severity（ $0 { \mathrm { < C B I } } \leqslant 1$ ），andhighseverity( $2 < \mathrm { C B I } \leqslant 3$ ），the dNBR index performed best with accuracies up to $80 \%$ ， $6 2 . 5 \%$ ，and $100 \%$ ， respectively；A map of grassland fire severity，which was drawn using the dNBR index， had the highest overall accuracy at up to $8 2 . 1 \%$ . The Kappa coefficient was also up to O.76.In conclusion, thedNBR index is the most suitable remote sensing index for analyzing and evaluating grassland fire severity.

Key Words:grassand fire； fire severity；landsat8 OLI；burn index；dNBR(diferenced Normalized Burm Ratio)

草原火是自然环境中重要的干扰因子之一[1],在全球范围内频繁发生[2],因其突发性强,破坏性大,极易导致草原生态的退化[3],给牧区经济尤其是畜牧业带来了巨大损失[4]。据统计,1994—2005 年间,呼伦贝尔地区年均发生草原火灾21次，年均受害草原面积高达12万 $\mathrm { { h m } } ^ { 2 }$ ,草原火灾已成为影响呼伦贝尔地区多发的自然灾害之一，因此在该地区开展草原火研究有助于揭示火干扰对草原生态系统各种生态过程的影响,对草原生态系统植被的恢复与管理具有一定的指导意义。 2

燃烧指数是通过选择对火灾较为敏感的波段进行组合运算,增强图像上火灾区域,可以获取火场范围、火烧严重度等信息,从而进行遥感评估,它被广泛用于火烧严重度研究[5-9]。而基于野外调查的综合燃烧指数（Composite Bum Index,CBI)[10]则是对遥感评估结果进行验证的通用方法,目前已经成为美国林务局（USForest Service)研究火烧严重度进行野外调查的标准,国内也进行大量尝试研究[1-3],但基本集中于林火烈度的评价。更多研究证明,差分归一化燃烧率(dNBR）比归一化燃烧率（Normalized Burn Ratio,NBR）,能更好地反映林火烈度的空间分布情况[7,4-15]。为减少过火前植被对火烈度遥感估测影响,2007年,Miler 和 Thode[16]提出了相对差分归一化燃烧率（Relative differenced Normalized Burn Ratio,RdNBR）,其研究结果表明 RdNBR指数优于NBR 和dNBR 指数。然而,Soverel等[17]在加拿大西部多个过火区的研究中发现,与dNBR 指数相比较,RdNBR指数并未带来火烈度估测精度的提高,这说明遥感定量估测的不确定性,燃烧指数的应用还有待进一步研究验证。近年来随着遥感技术在林火领域应用的成熟,部分学者基于 $\mathrm { E T M } +$ 、MODIS 等数据对NBR 等燃烧指数进行改进[18-19],得到亮温调整燃烧率（Normalized Burn Ratio Thermal，NBRT）、亮温调整燃烧率第一类型（NIR-SWIR-Temperature Version 1，NSTV1）、发射率调整燃烧率第一类型（NIR-SWIR-EmissivityVersionl，NSEV1)等燃烧指数,研究表明火灾后热红外波段监测到的亮温升高可以改进燃烧指数,同样能够很好的区分火烧严重度。

遥感影像提取植被信息具有精度高、范围广和成本低等特点，因此建立基于野外实测的综合燃烧指数（CBI)与遥感光谱指数之间的相关性来提取火烧严重度信息,成为林火烈度评价常用方法之一[6.8-9,20-2]。然而大部分研究利用单一指数进行评价，且指数选用又不尽相同,无法确定选取的遥感评估指数是否适用于研究区域。为此,本文尝试将适用于林火评价的燃烧指数应用于草原火,分析不同燃烧指数识别火烧严重度的差异,确定适用于草原火灾分析和评价的适宜燃烧指数,为火后植被恢复与管理研究提供一定的借鉴和参考。

# 1 研究区概况

本研究的实验区域位于中国内蒙古自治区呼伦贝尔地区，范围在 $1 1 7 ^ { \circ } 1 8 ^ { \prime } 2 2 ^ { \prime \prime } \mathrm { - } 1 1 7 ^ { \circ } 4 0 ^ { \prime } 5 8 ^ { \prime \prime } \mathrm { E }$ 和 $4 9 ^ { \circ } 2 1 ^ { \prime }$ $2 6 ^ { \prime \prime } { - } 4 9 ^ { \circ } 3 5 ^ { \prime } 2 8 ^ { \prime \prime } \mathrm { N }$ 之间,东西长约 $2 7 . 5 \mathrm { k m }$ ,南北宽 $2 8 . 5 \mathrm { k m }$ ,地处呼伦贝尔草原西北部,额尔古纳河为界与俄罗斯接壤,海拔 $6 5 0 { \mathrm { - } } 7 0 0 { \mathrm { m } }$ ,坡度比较平缓。研究区属于中温带大陆性草原气候,降水量小,季节分配不均,最高、最低温度出现在夏季和冬季,年平均气温 $0 . 7 \%$ ,年均降水量 $3 0 0 \mathrm { m m }$ 左右，降水集中在7、8月份,土壤类型以栗钙土为主。生态系统植被资源丰富,主要的植被群落有贝加尔针茅（Stipa baicalensis）群落,线叶菊（Filifolium sibiricum)群落和羊草(Leymus chinensis）群落。呼伦贝尔地区春秋两季枯枝落叶丰厚,气候干旱，草原火频繁发生,2015年4月16 日呼伦贝尔地区新巴尔虎右旗和满洲里交界处,发生一起草原大火,过火面积约为 $6 0 0 0 \mathrm { { h m } } ^ { 2 }$ （图1）。

# 2研究方法

# 2.1遥感数据

本研究使用遥感数据从美国地质调查局（United States Geological Survey,USGS）网站下载,经过几何精校正处理的L1T级别Landsat8 OLI影像。由于草地更新速度较快,火灾对草地的影响主要在火后早期[22],为保证信息提取的精确性，选取火前（2015年4月14日）和火后(2015年5月16日）相距时间最短的2景云量较少的遥感影像，轨道号为PATH125/ROW26，分辨率$3 0 \mathrm { m }$ （其中全色波段分辨率 $1 5 \mathrm { m }$ )，质量满足使用需求。Landsat8OLI影像为L1T级别，经过地面控制点和数字高程模型数据进行精确校正,但还未进行辐射定标、大气校正和影像剪裁等预处理。使用ENVI5.2软件对图像数据进行以上预处理后，利用SpectralIndices和Bandmath工具对预处理后的影像分别计算归一化燃烧率（NormalizedBurnRatio，NBR）亮温调整燃烧率第一类型（NIR-SWIR-Temperature Version 1，NSTV1）、差分归一化燃烧率（differenced Normalized Burn Ratio，dNBR）和相对差分归一化燃烧率（RelativedifferencedNormalizedBurnRatio，RdNBR），4种燃烧指数由预处理后影像内的不同波段计算而来，见表1。

![](images/aa153ebcaf3536b6c09efd676a5cbf66e16ba2d25d0dede475bf77ac03f7818e.jpg)  
图1火烧迹地位置  
Fig.1 Position of burned area

表1燃烧指数  
Table1Burn index   

<html><body><table><tr><td>指数名称 Index name</td><td>英文名称 English name</td><td>公式 Formula</td><td>参考文献 References</td></tr><tr><td>归一化燃烧率</td><td>Normalized Burn Ratio(NBR)</td><td>NIR-LSWIR NBR = NIR+LSWIR</td><td>[23]</td></tr><tr><td>亮温调整燃烧率第一类型</td><td>NIR-SWIRTemperaureersin</td><td>NSTV1 =NIR-LSWIRxT</td><td>[18]</td></tr><tr><td>差分归一化燃烧率</td><td>differenced Normalized Burn Ratio (dNBR)</td><td>dNBR =NBR火前－NBR火后</td><td>[10]</td></tr><tr><td>相对差分归一化燃烧率</td><td>Relative differenced Normalized Burn Ratio(RdNBR）</td><td>RdNBR= NBR火前－NBR火后 √ABS（NBR火前）</td><td>[16]</td></tr></table></body></html>

NIR:近红外,Near Infrared;LSWIR;长短波红外,Longer Short-wave Infrared;T:亮温/10O0,Temperature/10000

# 2.2综合燃烧指数(CBI)

综合燃烧指数(CBI)是基于野外地面调查，通过多层次多因子叠加后所求得的平均变化值。本研究结合该地区草原的演替历史、植被类型等特征,对 Key 和 Benson[10]的调查标准进行改进（表2）,在每个调查样地按垂直高度分2个层次调查;A)地表可燃物和土壤;B)草本和低矮灌木。在每一调查层都有若干个观测变量,变量取值范围为0—3（0代表未火烧;1代表轻度火烧;2代表中度火烧;3代表重度火烧）,然后对各层的估测值加以综合,最终求出样点CBI平均值。根据每个样点CBI均值,划分为3个等级,即为轻度火烧（lowseverity , $0 { \mathrm { < C B I } } \leqslant 1$ ）、中度火烧(moderate severity， $1 { \mathrm { < C B I } } \leqslant 2$ ）和重度火烧(high severity， $2 < \mathrm { C B I } \leqslant 3$ ）。

为保证实际测得CBI和OLI遥感影像最小像元在空间位置和大小保持一致，选取 $3 0 \mathrm { m } \times 3 0 \mathrm { m }$ 的矩形样地进行调查,于2015年5月中旬共获取研究区域内98个样点的CBI数据,将其随机分为两组,70个CBI样点用于构建回归模型,剩余28个CBI样点用于精度验证（表3）。不同CBI阈值均有样点分布,能够满足模型构建和精度验证需要。

# 2.3 研究方法

首先利用 ENVI5.2软件的 Spectral Indices 和Band Math工具对预处理后的影像分别计算4 种燃烧指数（表1）。同时利用ArcGIS 10.2软件 Spatial Analyst Tools 中的Extract Value to Points 工具,获得与地面实际调查CBI样点对应的各燃烧指数值。而后利用 SPSS 19.0工具,建立CBI值和各燃烧指数值的回归方程,分析相关性。根据回归方程所确定的各燃烧指数阈值,利用ENVI5.2软件的Color Slices工具,绘制基于各燃烧指数的草原火烧严重度分级图。最后,基于CBI验证样点数据,利用混淆矩阵进行拟合结果的分析评价。混淆矩阵(confusion matrix)通常用于遥感影像分类后的精度评价,是通过将每个地表真实像元的位置和分类与分类图象中的相应位置和分类像比较计算。

Table 2Investigation items and evaluation criterion of Composite Burn Index（CBI)   

<html><body><table><tr><td rowspan="2">分层 Strata</td><td rowspan="2">火烧特征 Burn attributes</td><td colspan="4">草原火烧严重度Grassland fire severity</td></tr><tr><td>未过火0 Non-fire</td><td>轻度0—1Low</td><td>中度1—2 Moderate</td><td>重度2-3High</td></tr><tr><td rowspan="5">A</td><td>枯枝落叶等可燃物消耗</td><td>无变化</td><td></td><td>50%枯枝落叶被消耗100%枯枝落叶被消耗80%细可燃物被消耗</td><td></td></tr><tr><td>半腐殖质</td><td>无变化</td><td>轻度燃烧</td><td>50%消耗</td><td>100%消耗</td></tr><tr><td>新生裸露岩石、</td><td>无变化</td><td>10%发生改变</td><td>40%发生改变</td><td>>80%发生改变</td></tr><tr><td>土壤的盖度/颜色 叶片变化率/%</td><td>无变化</td><td>30</td><td></td><td></td></tr><tr><td>存活率/%</td><td>100%</td><td>90</td><td>80</td><td>>95</td></tr><tr><td rowspan="4"></td><td></td><td>无变化</td><td>低</td><td>50</td><td><20</td></tr><tr><td>植物定植</td><td></td><td></td><td>中</td><td>高一无</td></tr><tr><td>物种组成/多样性</td><td>无变化</td><td>变化小</td><td>变化中等</td><td>变化大</td></tr><tr><td>盖度变化率/%</td><td>无变化</td><td>15</td><td>70</td><td>>90</td></tr></table></body></html>

A:地表可燃物和土壤,surface fueland soil;B：草本和低矮灌木,herb and low shrul

表2综合燃烧指数(CBI)调查内容和评价标准  
表3CBI样点统计  
Table3Statistics for the CBI plots   

<html><body><table><tr><td>CBI阈值 Thresholds</td><td>样点数(建模/验证) Number</td><td>最小值 Minimum</td><td>最大值 Maximum</td><td>均值 Mean</td><td>标准差 Standard deviation</td></tr><tr><td>0</td><td>12,5</td><td>0</td><td></td><td>0</td><td>0</td></tr><tr><td>(0,1]</td><td>18,8</td><td>0.05</td><td>1.00</td><td>0.55</td><td>0.342</td></tr><tr><td>(1,2]</td><td>20,7</td><td>1.10</td><td>2.00</td><td>1.50</td><td>0.277</td></tr><tr><td>(2,3]</td><td>20,8</td><td>2.01</td><td>3.00</td><td>2.53</td><td>0.307</td></tr></table></body></html>

# 3结果和分析

3.1 燃烧指数与CBI相关性分析

基于Landsat8 影像提取的燃烧指数 NBR、NSTV1、dNBR 和RdNBR,分别与野外调查获取的CBI数据进行相关性分析，结果如图2所示。

(1)回归分析结果表明,随着综合燃烧指数(CBI)的升高,NBR 和 NSTV1指数均呈现明显下降趋势,表现为负相关关系（图2),相反,dNBR和RdNBR 指数呈现上升趋势,表现为正相关关系（图2）。与谭柳霞等[7]关于林火烈度的研究结果一致。由于过火区域植被种类数量和土壤侵蚀程度存在差异,同一场火烧使得不同空间位置的生态系统破坏程度出现差异,即存活植被的类型数量越少土壤侵蚀严重,则生态系统破坏程度越高，CBI值也就越高;同理,草原火过后利用植被状态敏感波段的光谱反射率构建的 NBR 和 NSTV1指数,能够在一定程度上反映火后不同空间位置存活植被的状态,存活植被数量和类型越多,NBR 和 NSTV1 指数值越高,CBI则越低。因此,NBR 和NSTV1指数与CBI之间表现为负相关。而dNBR 和RdNBR 指数是基于火前和火后两景遥感图像获取的差分燃烧指数,即遥感指数的减少量越大,火烧破坏程度越大,CBI值也就越高,因此，呈正相关。

(2)4种燃烧指数与CBI指数拟合结果的相关系数由大到小依次为dNBR( $R ^ { 2 } = 0 . 8 5 6$ ）,NSTV1( $R ^ { 2 } = { }$ 0.762）,NBR( $R ^ { 2 } = 0 . 7 4 9 \rangle$ 和RdNBR( $R ^ { 2 } = 0 . 5 7 4 \rangle$ 。因此,dNBR值和CBI值之间的非线性正相关关系( $n = 7 0$ ，$R ^ { 2 } = 0 . 8 5 6$ )表现最好,说明dNBR 阈值的选取对该地区草原火烧严重度的分类具有相对可靠性。

（3)NBR 和 NSTV1是基于火后一景遥感图像获取的单一燃烧指数,而dNBR 和RdNBR 是基于火前和火

![](images/2aa5f4e7951f1f4857fa034bbe99b593c8b945ce0b1e145c121129ce77b79bb3.jpg)  
图2研究区燃烧指数和CBI的相关性分析图  
Fig.2Correlation analysis plot of burn index values and CBI values in study area

NBR:归一化燃烧率,Normalized Bum Ratio;NSTV1;亮温调整燃烧率第一类型,NIR-SWIR-Temperature Version1;dNBR;差分归一化燃烧率， diferenced Normalized Burn Ratio;RdNBR:相对差分归一化燃烧率,Relative diferenced Normalized Burn Ratio

后两景遥感图像获取的差分燃烧指数。从图2上可以看出,单一燃烧指数 NBR 和 NSTV1变化趋势一致,与CBI呈现负相关,两者对火烧严重度信息提取的精度相差很少（ $\Delta R ^ { 2 } = 0 . 0 1 3 { \mathrm { ~ , ~ } }$ 。而差分燃烧指数dNBR和RdNBR表现正相反,与CBI呈现均为负相关,但两者对于火烧严重度信息提取的精度相差很大( $\Delta R ^ { 2 } = $ 0.282）,dNBR优于RdNBR。 LO

3.2基于不同燃烧指数的草原火烧严重度分级图

根据不同燃烧指数与 CBI 的相关性分析结果,获得 NBR、NSTV1、dNBR 和 RdNBR 指数与 CBI之间的回归方程,分别为：

$$
\mathrm { N B R } = 5 . 5 3 ~ \mathrm { C B I } ^ { 2 } { - 9 8 . 8 2 ~ \mathrm { C B I } { - 2 9 . 2 5 } ~ , ~ R } ^ { 2 } { = 0 . 7 4 9 }
$$

$$
\mathrm { N S T V 1 } = 1 5 5 . 3 \mathrm { C B I } ^ { 2 } - 2 9 0 4 \mathrm { C B I } - 1 0 6 2 , R ^ { 2 } = 0 . 7 6 2
$$

$$
\mathrm { d N B R } = - 1 7 . 3 4 ~ \mathrm { C B I } ^ { 2 } + 1 6 9 . 0 0 ~ \mathrm { C B I } + 2 9 . 9 7 ~ , ~ R ^ { 2 } = 0 . 8 5 6
$$

$$
\mathrm { R d N B R } = - 1 0 9 . 6 6 ~ \mathrm { C B I } ^ { 2 } + 5 9 2 . 7 7 ~ \mathrm { C B I } + 3 1 3 . 9 1 ~ , ~ R ^ { 2 } = 0 . 5 7 4
$$

根据CBI火烧严重度的阈值,通过回归方程分别确定4种燃烧指数的分级阈值（表4）,利用ENVI5.2软件Color Slices工具,分别绘制出基于不同燃烧指数的草原火烧严重度分级图（图3）,用于后续拟合结果的分析评价。

表4各燃烧指数火烧严重度阈值  
Table 4Thresholds of each burn index of fire severity   

<html><body><table><tr><td>火烧严重度Fire severity</td><td>NBR</td><td>NSTV1</td><td>dNBR</td><td>RdNBR</td></tr><tr><td>未过火0 Non-fire</td><td>>-29</td><td>>-1062</td><td><30</td><td><314</td></tr><tr><td>轻度（0,1] Low</td><td>（-123,-29]</td><td>（-3811,-1062]</td><td>[30,182)</td><td>[314,797)</td></tr><tr><td>中度（1,2] Moderate</td><td>(-205,-123]</td><td>(-6240,-3811]</td><td>[182,299)</td><td>[797,1061)</td></tr><tr><td>重度(2,3]High</td><td><-205</td><td><-6249</td><td>>299</td><td>>1061</td></tr></table></body></html>

http ://www.ecologica.cn

![](images/487b74d0580aeb9b89b5f89ff9affcdcff762ec72101bb4672a27e3bee7b6031.jpg)  
基于NBR指数的草原火烧严重度分级  
基于NSTV1指数的草原火烧严重度分级  
图3基于不同燃烧指数的草原火烧严重度分级图  
Fig.3Map of fire severity based on different burn index

# 3.3拟合结果评价

利用混淆矩阵可以直接计算分类后的总体分类精度、用户精度和Kappa 系数等评价指标。

表5基于验证样点的精度评价   
Table 5Accuracy evaluation based on test plot   

<html><body><table><tr><td>燃烧指数 Burn index</td><td>未过火/% Non-fire</td><td>轻度火烧/% Low severity</td><td>中度火烧/% Moderate severity</td><td>重度火烧/% High severity</td><td>总体分类精度/% Overall accuracy</td><td>Kappa系数 Kappa coefficient</td></tr><tr><td>NBR</td><td>80.0</td><td>50.0</td><td>85.7</td><td>87.5</td><td>75.0</td><td>0.665</td></tr><tr><td>NSTV1</td><td>60.0</td><td>37.5</td><td>100.0</td><td>87.5</td><td>71.4</td><td>0.618</td></tr><tr><td>dNBR</td><td>80.0</td><td>62.5</td><td>85.7</td><td>100.0</td><td>82.1</td><td>0.760</td></tr><tr><td>RdNBR</td><td>60.0</td><td>37.5</td><td>57.1</td><td>75.0</td><td>57.1</td><td>0.422</td></tr></table></body></html>

表中未过火、轻度、中度、重度火烧对应的精度均为混淆矩阵结果中的用户精度(User's Accuracy)

(1)从表5可以看出,基于dNBR 指数的火烧严重度分级图总体精度最高,达到 $8 2 . 1 \%$ ,相对应的 Kappa系数也高达0.76。而RdNBR指数表现最差,总体精度为 $5 7 . 1 \%$ ,Kappa系数为0.422。这一精度验证结果与

http://www.ecologica.cn

回归分析精度 $R ^ { 2 }$ 的表现一致。RdNBR 的提出[16],旨在减少过火前植被数量对火烈度遥感估测的影响,通常在植被类型差异比较大的情况下RdNBR 的精度高于 $\mathrm { d N B R } ^ { [ 2 4 - 2 5 ] }$ 。对于研究区域内以典型草原、沙生和盐生植被为主的植被群落,相对于森林生态系统结构单一,垂直变化幅度小,火烧的影响主要体现在植被盖度,可燃物消耗以及土壤侵蚀等方面,因此,RdNBR在研究区域内反而会表现不如dNBR,这与 Soverel等[12]的研究结果一致。由此说明,遥感燃烧指数的估测能力受估测精度及其背景因素的影响较大。

(2)4种燃烧指数对于未过火区域( $\mathrm { C B I } = 0 \$ )和重度火烧区域( $2 < \mathrm { C B I } \leqslant 3$ )均能较好的识别,其中dNBR 精度最高，分别为 $8 0 \%$ 和 $100 \%$ ;4种燃烧指数对于不同的火烧严重度分级存在一定差异,未过火、轻度和重度火烧区域内,dNBR提取精度均表现最好，在中度火烧区域( $1 < \mathrm { C B I } \leqslant 2$ )内，NSTV1的提取精度最高;然而相对于其他火烧严重度，4种燃烧指数对轻度火烧区域( $0 < \mathrm { C B I } \leqslant 1$ )的提取能力表现较差，精度范围为 $3 7 . 5 \% -$ $6 2 . 5 \%$ 。 2

（3)从图2和图3中可以看出,NSTV1的拟合精度为 $7 6 . 2 \%$ ,略高于NBR 的 $7 4 . 9 \%$ ,NSTV1的火烧分级图效果相对较好,主要原因NSTV1是在 NBR 的基础上,使用了一个热红外波段,对火灾后光谱特征变化进行非线性拉伸增强,能更好的分离燃烧区和非燃烧区。而在精度验证时,NBR和 NSTV指数提取火烧严重度信息的总体精度比较接近，分别为 $7 5 . 0 \%$ 和 $7 1 . 4 \%$ ,NBR指数表现稍好,原因在于验证样本数量限制,不能全面系统的反应整个火场的火烧严重度分级情况。

# 4结论与讨论

基于landsat8 OLI影像分别构建4种燃烧指数(NBR、NSTV1、dNBR和RdNBR)与综合燃烧指数（CBI)的回归模型并进行精度验证,对比分析不同燃烧指数识别草原火烧严重度等级的能力。结果表明：对于植被相对单一的草原生态系统,以火灾发生前后遥感指数的减少量作为火烧严重度评价标准的dNBR指数,是草原火烧严重度分析与评价的适宜遥感指数。4种燃烧指数由OLI影像内的不同波段计算获得,而不同波段对于火烧迹地的区分度存在差异[26],因此4种燃烧指数识别不同等级火烧严重度的精度也存在差异,如 NSTV1的火烧分级图效果好于NBR,主要原因在于NSTV1在NBR 的基础上,使用了一个热红外波段,对火灾后光谱特征变化进行非线性拉伸增强,能更好的分离燃烧区和非燃烧区。与 NBR、NSTV1和 RdNBR 相比较,dNBR指数在构建模型( $R ^ { 2 } = 0 . 8 5 6 )$ 和精度验证（总体精度： $8 2 . 1 \%$ )中均表现最好。

与谭柳霞等[7]、Musyimi等[9]关于森林火灾的研究相比,本研究中dNBR指数拟合与验证精度更高,这与综合燃烧指数(CBI)的野外实测有着直接关系。与森林生态系统相比,草原火烧严重度调查的层次减少,影响因子也因此更少,所以CBI与dNBR指数拟合结果更为接近。同时遥感数据源的空间分辨率也是影响模型拟合和结果验证的重要因素。燃烧指数评估火烧严重度的能力由于受气候、地形和植被类型等因素的影响，表现出空间异质性,现阶段大量研究集中于林火烈度。未来可以借助高分辨率遥感影像,结合地面调查,开展广域尺度上草原火研究,深入研究地形、气象、可燃物及其相互作用对火烧严重度空间异质性的影响等。

# 参考文献（References）：

MN 雒瑞森.全球火格局的时空变异及其机理分析[D].杭州：浙江大学，2013.  
[2 张正祥，张洪岩，李冬雪，许嘉巍，周道玮.呼伦贝尔草原人为火空间分布格局.生态学报，2013，33（7)：2023-2031.  
[3] 周广胜，卢琦.气象与森林草原火灾.北京：气象出版社，2009：4-5.  
[4] 陈世荣.草原火灾遥感监测与预警方法研究[D].北京：中国科学院研究生院（遥感应用研究所)，2006.  
[5] 常禹，陈宏伟，胡远满，冯玉婷，李悦.林火烈度评价及其空间异质性研究进展.自然灾害学报，2012，21（2)：28-34.  
[6]StambaughMCHammerLD，Gofreyerfoanceof-severitymetricsndclasifationinoakwooandsdgassadeoteSensing，2015，7（8）：10501-10522.  
［7］谭柳霞，曾永年，郑忠.林火烈度遥感评估指数适应性分析.国土资源遥感，2016，28（2）：84-90.  
[8]ChangYZuZL,FgY,LiH,uRC,HuYM.esatiavariatioforestbueveritiHeilojiangPrice,CaauraHazards,2016,81(2):981-1001.  
[9] Musyimi Z，SaidMY，ZidaD,RosenstockTS,UdelhovenT,SavadogoP，deLeeuwJ，AynekuluE.EvaluatingfireseverityinSudaninecosystems of Burkina Faso using Landsat8 satelite images.Journal of Arid Environments,2O17,139：95-109.  
[10]KeyCH,BensonNC.Landscape Asessmentsampling andanalysis methods/LutesDC,KeaneRE,CaratiJF,KeyCH,Benson $\mathrm { ~ N ~ C ~ }$ ，SutherlandS,GangiLJ，eds.FREMON：FireEfectsMonitringandInventorySystem.GeneralTechnicalReportRMRS-GTR-64-CD.ortCollins，CO：U.S.Department of Agriculture,Forest Service,Rocky Mountain Research Station,2006.  
[11] 孔博，张树清，张柏，那晓东,李晓峰，卢晓宁.扎龙湿地火烧严重度分析及火灾对丹顶鹤生境的影响.湿地科学,200,5(4)：348-355  
[12] 王晓莉，王文娟，常禹，冯玉婷，陈宏伟，胡远满，池建国.基于NBR 指数分析大兴安岭呼中森林过火区的林火烈度.应用生态学报2013,24(4): 967-974.  
[13] 杨达，吴志伟，梁宇，贺红士.林火烈度的量化指标构建.林业资源管理，2014，（6)：140-145.  
[14] van Wagtendonk JW,Root RR,Key C H.Comparison of AVIRIS and Landsat $\mathrm { E T M } +$ detection capabilities for burn severity. Remote Sensing ofEnvironment，2004，92(3）：397-408.  
[15] AlenJL,SobelAsestfeedoalduatiosiltaueveitinalenddrasfAlaska's national parks. International Journal of Wildland Fire，2Oo8,17(4)：463-475.  
[16] MillerD,TodeAE.QuantfeeitinergesdsapeielatieversioofthelaoaldBuatid).Remote Sensing of Environment，2007，109(1)：66-80.  
[17] SoverelNO,PerakisDDB,CoopsNC.EstimatingburseverityfroLandsatdNBRandRdBRindicesacrosswesterCanda.RemoteSensingof Environment，2010,114(9)：1896-3219.  
[18] VeraverbekeS,HarisS,HokS.EvaluatigspectralidicesforbuedareadiscriatiousingOS/ER（MATR）irbesilatordata.Remote Sensing of Environment，2011,115(10）：2702-2709.  
[19]SmithAMS,DrakeNA，WosterMJ,HudakAT,HoldenZA,GibbonsCJProductiofLandsatET+referenceimageryofbureaswithinsouthernAfrcansaaasomparisoofethosandalicatiotoSInteatioalJualofReoteesingO8（）：2753-2775.  
[20] OttoR，Garca-del-ReyE，MunozPG，Ferndez-PalaciosJM.Theetoffireseveritonfrst-yarsdingestablishmentaPinuscanariensis forest on Tenerife,Canary Islands.European Journal of Forest Researeh,2010,129(4）: 499-508.  
[21]ZhengZ,ZengYiSuangW.AneitdesedndfcetepatureadecedgeatiodeialJournal of Applied Earth Observation and Geoinformation,2016,45:84-94.  
[22]Perer,CrdaA,rtiD,UdaX,DepeegiD,NovaaA,artie-uilJF,revikE,MesmR,etermlow-severitsggassandfireipactsoletractableementsdsilrtiosiLiuaaencfteTtalEviont1,578: 469-475.  
23]Lopez-seldaloresatioateial99  
[24] MilerJD,KnappEE，KeyCH,kinerCN,IsbellCJ，CreasyRMSerlockJW.Calibrationandvalidationf herelativedifreNormalizedBuRatodB）tohemeasuresoffreseverityintheSiera NvadndKlamathMountains，Califoia，USA.Remoteesingof Environment,2009,113(3): 645-656.  
25]Miler,fdHso.QantiativeeveefeasiforestieeveritievdndouCascade Mountains，California and Nevada,USA. Ecosystems，2009,12(1): 16-32.  
[26] 吴立叶，沈润平，李鑫慧，杨恒.不同遥感指数提取林火迹地研究.遥感技术与应用，2014，29（4)：567-574.