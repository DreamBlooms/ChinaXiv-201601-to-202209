# 陆面同化及再分析降水资料在内蒙古地区的适用性

宋海清}²，朱仲元¹，李云鹏²(1.内蒙古农业大学水利与土木建筑工程学院,内蒙古 呼和浩特010018;2.内蒙古自治区生态与农业气象中心，内蒙古 呼和浩特010051)

摘要：利用1982—2018年内蒙古地区115个气象站点的月降水观测资料评估了FLDAS、ERA5、CRA40/Land 和GLDAS 4种陆面同化及再分析降水资料在内蒙古地区的可靠性。结果表明：（1)4种降水资料均能较好地表征降水量在内蒙古地区从东北向西部递减和冬季降水少、夏季降水多的时空变化特征。（2）相关系数、绝对平均误差、均方根误差和纳什效率系数的计算结果表明,4种降水资料在夏季表现最优、冬季表现最差，在东部半湿润区和半干旱区好于西部干旱区和极干旱区。（3)ERA5资料在绝大多数时间对内蒙古的降水有高估现象,GLDAS却对降水存在低估,尤其是在冬季,GLDAS对固态降水几乎没有观测能力,而新发布的FLDAS资料表现较好。总体来看,相对于ERA5和GLDAS,FLDAS和CRA40/Land降水资料与观测值之间的差别最低，有着最优的统计特征。

关键词：降水；陆面同化资料；再分析资料；适用性

降水是全球水循环中重要的控制因子，也是天气和气候中最为活跃的部分，能够影响和调节气候系统[1-3]。降水是目前最具挑战性的预报预测变量之一[4],旱涝预报和滑坡泥石流等次生气象灾害预测的准确程度在很大程度取决于降水预报的精度[5]。准确可靠的降水资料对天气气候研究、水文模拟、水资源管理等起着至关重要的作用[6-8]。目前降水资料的获取途径主要有3种：观测站雨量筒观测、天气雷达或卫星遥感反演和数值模式模拟。观测站观测的降水最准确，但其空间代表性有限，同时受地形等条件的影响，且空间分布不均，复杂地形区或者偏远地区观测站点稀疏[9]。近年来在获取空间上高分辨率格点化降水资料，通过卫星反演获取降水资料这一手段得到快速发展，如常用的TropicalRain Measuring Mission(TRMM)资料、Global Precipi-tation Measurement Mission(GPM)资料、Climate Pre-diction Center Morphing Technique（CMORPH）资料以及 Climate Hazards group Infrared Precipitationwith Stations(CHIRPS)降水资料等[10-15]。此外陆面数据同化资料和再分析资料也提供了时空连续的全球和区域的降水资料，弥补了无降水观测资料区域资料的不足，成为无资料区降水研究和应用不可或缺的资料[2.16],例如时空分辨率较高的全球陆面数据同化系统(GLDAS)资料[、欧洲大气再分析资料-过渡产品(ERA-Interim)再分析资料[18]、欧洲第五代大气再分析资料(ERA5)9和气候预测系统再分析资料(CFSR)[20-2I]等。近年来，随着计算能力的飞速发展、数值模式的不断改进和资料同化方法的持续创新，陆面数据同化资料和再分析资料的时空分辨率更高、准确度有大幅提升。

观测站雨量筒观测、天气雷达或卫星遥感反演，以及数值模式模拟这3种降水获取方式优缺点并存[3I1],利用站点观测资料对天气雷达或卫星遥感反演和数值模式模拟降水资料进行评估和检验，获取这些降水资料的误差特征和适用性能够为降水资料的算法改进和精度提高起到借鉴作用。随着一系列格点降水产品的出现，诸多学者对不同降水资料在不同区域的质量和表现的关注度越来越高，尤其是一些新生产的降水资料,被广泛应用于高山区域、各个大洲和中国及国内部分研究区域的降水和水文研究，并取得了很好的应用成果。例如，Chen等2]为了评估ERA-Interim、ERA5、ERA5-Land

Vir牛小贝料在喜马拉雅南坡的尼泊尔地区的性能，利用549个站点观测降水资料进行评估，得出再分析资料在低海拔地区均表现出相似的性能,而在高海拔地区高分辨率降水资料才能够反映地形对降水的影响的结论。Sharma等[13]评估了GPM-era降水资料在喜马拉雅南坡的适用性，Dinku等[4对比了CMORPH和TRMM降水资料在非洲和南美洲的适用性,发现卫星降水资料有低估的现象；Sahlu等[利用观测站资料，在东非地区检验了高分辨率多卫星和再分析降水资料，得出调整后的卫星降水资料有最优的精度。而在中国及国内部分研究区域，诸多降水资料研究也得到了广泛评价和应用,例如,闫燕等[3]评估了两种卫星反演降水和4种再分析降水资料在重庆区域的逐日和日内变化，得出再分析资料高估了研究区域日降水、卫星资料的降水好于再分析资料的结论。Jiang等[6对多种卫星降水产品在湘江支流的迷水流域进行了综合评价并使用降水资料运行新安江水文模型进行水文模拟,得出TRMM3B42V6质量最好的结论。王玉丹等8利用陕西省站点观测资料对CMORPH降水产品和ITPCAS降水进行了适用性评估，发现ITPCAS资料显著优于CMORPH资料。Lu等[12]评估了卫星降水GPM资料和GSMap资料在青藏高原的适用性,得出GSMap-Gauge卫星降水资料适用于水文应用。王文等[7对比分析了GL-DAS-1和GLDAS-2降水资料在中国区域的适用性，发现GLDAS降水资料在中国东部的质量高于西部地区，总体性能存在地区和季节差异。Li等[22]评估了中国全球大气再分析降水资料，结果显示CRA和CFSR高估了中国东部暖季主雨带的降水量。可见再分析降水资料一般倾向于高估降水，而卫星降水资料倾向于低估降水，且卫星降水资料质量略好，总体而言,陆面同化降水产品和再分析降水资料的精度受地形、海拔和季节等因素影响而存在时空差异。

内蒙古位于我国北方地区，地处季风和非季风区交界处，是我国北部重要的生态屏障，自东向西依次为半湿润区、半干旱区和干旱区（含极干旱区），地形地貌复杂多样。内蒙古面积约占中国总面积的八分之一，地广人稀，气象站点较为稀疏，在林区和干旱区气象观测亟缺，因而研究评估多种卫星及再分析格点降水资料具有重要的意义。此外，美国国家航天局(NASA)制作的全球第一版FLDAS资料、中国气象局制作的中国陆面 $4 0 \mathrm { ~ a ~ }$ 再分析资料(CRA40/Land)均为2020年发布的最新资料，其在内蒙古地区的精度如何，极有必要对其适用性进行系统性评估。本研究利用内蒙古自治区115个气象站观测逐月降水资料，对内蒙古地区4种长时间序列且空间分辨率较高的FLDAS、CRA4O/Land、GL-DAS3种陆面同化降水资料和ERA5大气再分析降水资料的时空分布和统计特征进行评估。检验4种资料的可靠性，为较好的研究内蒙古降水变化特征和时空分布奠定基础。

# 1资料来源与方法

# 1.1资料来源

1.1.1观测降水资料1982—2018年内蒙古地区115个国家地面观测站逐月降水资料来自于内蒙古自治区气象局。为了评估4种降水资料在不同气候区的适用性，根据1982—2018年观测年均降水将内蒙古地区分为4个气候区，分别为半湿润区（400$\mathrm { m m } { \leqslant }$ 年均降水 $< 8 0 0 \ \mathrm { m m }$ ）、半干旱区( $2 0 0 ~ \mathrm { m m } \leqslant$ 年均降水 ${ < } 4 0 0 ~ \mathrm { m m }$ ）、干旱区( $1 0 0 ~ \mathrm { { m m } \leqslant }$ 年均降水 $< 2 0 0$ $\mathbf { m m } .$ )和极干旱区(年均降水 $< 1 0 0 ~ \mathrm { { m m } }$ )。内蒙古气候分区与气象站点统计见表1。

1.1.2陆面同化及再分析降水资料采用FLDAS、ERA5、CRA40/Land与GLDAS4种高分辨率逐月降水资料，对内蒙古地区的适用性进行评估。FLDAS降水资料是由美国NASA基于CHIRPS卫星降水[15]和MERRA-2(The Modern-Era Retrospective AnalysisforResearch and Applications,Version 2)降水资料[23]合成的全球降水资料，其在CHIRPS覆盖区域( $5 0 ^ { \circ } \mathrm { S } \sim$ $5 0 ^ { \circ } \mathrm { N }$ )之外采用MERRA-2降水资料填补。FLDAS降水资料被开发并应用于粮食和水安全监测评估[24-25]。本文使用的FLDAS降水资料时间分辨率为月，空间分辨率为 $0 . 1 ^ { \circ } \times 0 . 1 ^ { \circ }$ ,时间范围为1982—

表1内蒙古气候分区  
Tab.1 Climate division overInner Mongolia   

<html><body><table><tr><td>气候分区</td><td>年均降水/mm</td><td>气象站数量</td></tr><tr><td>半湿润区</td><td>400≤年均降水<800</td><td>28</td></tr><tr><td>半干旱区</td><td>200≤年均降水<400</td><td>68</td></tr><tr><td>干旱区</td><td>100≤年均降水<200</td><td>16</td></tr><tr><td>极干旱区</td><td>年均降水<100</td><td>3</td></tr></table></body></html>

2018年。

ERA5再分析资料是由欧洲中期天气预报中心(ECMWF)最新发展的第5代全球再分析资料[19]分辨率为 $3 1 ~ \mathrm { k m } { \times } 3 1 ~ \mathrm { k m }$ ，同化方法采用10个集合成员的 $4 \mathrm { D V a r }$ 。输出时间分辨率为 $^ { \textrm { 1 h } }$ ,ERA5资料覆盖时间长度为1979—2021年。本研究采用的ERA5降水资料时间分辨率为月，时间范围为1982—2018年。

中国陆面 $4 0 \mathrm { ~ a ~ }$ 再分析资料CRA40/Land是由中国气象局制作的中国第一代陆面再分析资料[22],空间分辨率为 $3 4 ~ \mathrm { k m }$ ，时间分辨率为 $6 \mathrm { { h } }$ 。CRA40/Land降水资料是使用数据融合方法融合了全球地面雨量计分析资料(CPCU)和全球卫星降水(GPCP)资料生成的全球降水产品，其时间范围是1979—2020年。本研究采用的CRA40/Land降水资料时间范围是1982—2018年，时间分辨率为月。

GLDAS降水资料是指美国NASA开发的第二代全球陆面数据同化系统生成的GLDAS-Noah降水产品,其时间分辨率为月，空间分辨率为 $0 . 2 5 ^ { \circ } { \times } 0 . 2 5 ^ { \circ }$ ，时间范围是1982—2018年[17]。由于GLDAS-2时间范围为1948—2014年，本文使用的2015—2018年的GLDAS降水资料由GLDAS-2.1降水补齐。

采用中国科学院青藏高原研究所研发的中国区域地面气象要素驱动数据集(CMFD)中的降水资料，计算4种降水资料的多年平均降水的偏差分布。CMFD降水资料以GLDAS和TRMM卫星降水为背景场，融合了中国气象局常规降水观测数据制作而成，研究显示，该数据在中国区域有着较好的精度[8.26]。本文使用的CMFD降水资料的时间分辨率为月，空间分辨率为 $0 . 1 ^ { \circ } \times 0 . 1 ^ { \circ }$ ，时间范围是1982—2018年。

# 1.2 研究方法

为了定量评估4种降水资料在内蒙古的适用性，分析计算了4种降水资料与观测资料的相关系数（CorrelationCoefficients，CC）、绝对平均偏差（Mean AbsoluteErrors，MAE）、均方根误差（RootMeanSquareErrors，RMSE)和纳什效率系数(Nash-SutcliffeEficiencyCoefficients,NSE）,4个统计特征计算方法如下所示：

$$
\mathrm { C C } = \frac { \displaystyle \sum _ { i = 1 } ^ { n } \bigl ( M _ { i } - \bar { M } \bigr ) \bigl ( O _ { i } - \bar { O _ { i } } \bigr ) } { \displaystyle \sqrt { \sum _ { i = 1 } ^ { n } \bigl ( M _ { i } - \bar { M } \bigr ) ^ { 2 } } \ \sqrt { \sum _ { i = 1 } ^ { n } \bigl ( O _ { i } - \bar { O } \bigr ) ^ { 2 } } }
$$

$$
\mathrm { M B E } = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \bigl ( | M _ { i } - O _ { i } | \bigr )
$$

$$
\mathrm { R M S E } = \sqrt { \frac { 1 } { n } { \sum _ { i = 1 } ^ { n } } \big ( M _ { i } - O _ { i } \big ) ^ { 2 } }
$$

$$
\mathrm { N S E } = 1 - \frac { \displaystyle \sum _ { i = 1 } ^ { n } \bigl ( O _ { i } - M _ { i } \bigr ) ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { n } \bigl ( O _ { i } - \bar { O } \bigr ) ^ { 2 } }
$$

式中： $n$ 为样本总数； $i$ 为时间变量； $M _ { i }$ 为每种降水资料的数值； $\bar { M }$ 为每种降水资料的均值; $O _ { i }$ 为观测降水； $\bar { O }$ 为观测降水的均值。同时，采用Taylor图更加直观的呈现4种降水资料与观测降水之间的整体评价情况。

考虑到使用的各种资料空间分辨率不尽相同，本文采用双线性插值法，将4种降水资料的空间分辨率插值为与CMFD降水资料一致的空间分辨率。另外，为了避免格点数据插值到站点产生误差，采用距离站点最近的格点数据与该站点观测数据进行比较[27]

# 2结果与分析

# 2.14种降水资料的多年平均降水分布

从1982—2018年内蒙古地区不同降水资料多年平均降水空间分布可知(图1),4种年均降水资料在内蒙古地区的空间分布特征与观测较为一致，均呈现出从东北向西部递减的特征。4种降水资料的空间分布较为相似，其中ERA5降水在量值上普遍偏高，高估了内蒙古大部分区域的年均降水。FL-DAS、CRA40/Land和GLDAS降水与观测差距较小，很好的再现了内蒙古年均降水的空间分布特征，尤其是FLDAS降水资料局部细节上表现最优。从内蒙古地区不同降水资料年均降水与CMFD资料的差值空间分布可以看出(图2)，空间差别较大的区域主要分布在内蒙古东北部的呼伦贝尔市和中部偏南地区；FLDAS仅在呼伦贝尔北部和内蒙古东南部地区高估了降水，其余地区略低估了降水，因而在大部分地区表现较好，误差较小；ERA5在研究区的绝大部分区域高估了降水，尤其是呼伦贝尔市和内蒙古中部偏南地区，偏大 $8 0 ~ \mathrm { m m }$ 以上;CRA40/Land在呼伦贝尔市大部分区域高估了降水，尤其是呼伦贝尔市北部,偏大 $8 0 \mathrm { m m }$ 以上,在内蒙古中部偏南地区和阿拉善盟东南部低估了降水，个别区域低估80$\mathbf { m } \mathbf { m }$ 以上，而GLDAS除了在通辽市南部高估了降水外，其他地区低估了降水，尤其是内蒙古中部偏西南区域偏低 $8 0 ~ \mathrm { m m }$ 以上。总的来说，4种降水资料均能较好的反映内蒙古地区年均降水的空间分布特征，FLDAS相对更优，偏差介于 $- 2 0 { \sim } 2 0 ~ \mathrm { m m }$ 的区域最多。

![](images/9b9bcdd91c1e92f712709dbef074cf52907b6ea5be04f1e6801efe1ad18810cc.jpg)  
注：底图采用自然资源部标准地图制作，审图号：GS(2020)4630,底图无修改。下同。  
图1内蒙古地区不同降水资料多年平均降水的空间分布  
Fig.1The distribution of averaged annual precipitation based on different precipitation datasets in Inner Mongol

# 2.24种降水资料的时间变化

为了比较观测降水与4种降水资料在内蒙古及

4个气候分区的逐月变化，计算了1982—2018年4种降水资料与观测资料在内蒙古地区不同区域逐月平均降水变化(图3)。可以看出，4种降水资料与观测降水在时间变化上均具有较好的一致性；内蒙古地区和4个气候分区的逐月降水时间变化较为相似，呈现出夏季降水最多，冬季降水最少的特点。内蒙古地区降水的时间变化特征与半湿润区和半十旱区相似程度最高，干旱区和极干旱区降水时间变化与其他气候分区一致性较差，这可能是因为干旱区和极端干旱区降水量小，同时气象观测站点相对较少，故不能显著影响整个内蒙古地区的降水时间特征。从4种降水资料逐月偏差时间变化可以看出（图4)，ERA5资料在内蒙古和半湿润、半干旱和干旱区均呈现高估现象，在极干旱区ERA5降水高估程度低于在其他气候分区，另外ERA5的偏差呈减小的趋势;FLDAS资料的偏差小于ERA5，但仍然有高估的现象，同时可以看出FLDAS降水资料在内蒙古、半湿润区和半干旱区的偏差有增大的现象。CRA40/Land降水资料在1983—1986年前后表现出较大的负偏差，呈低估特征，在其他时段偏差小于FLDAS、ERA5和GLDAS3种资料。GLDAS出现负偏差的时段多于正偏差的时段，说明GLDAS资料大部分时间低估了降水。另外，4种降水资料的偏差随着季节的变化而变化，在夏季降水多时段的偏差大于冬季降水少时段的偏差。

![](images/8a6c291e9d7df6361f577be2c21a2f682c93f502e28a034d98e880b7bee30315.jpg)  
图2内蒙古地区4种降水资料的多年平均分别与CMFD资料的差值空间分布  
g.2The distributionof biases ofaverage annual precipitation between4 precipitation datasetsand CMFDdata in Inner Mo

# 2.3月降水统计分析

为了比较4种降水资料对不同月份的降水时间变化，分别选择了1月、4月、7月和10月区域平均月降水进行分析(图5)。由图5可以看出，在1月份，GLDAS对固态降水几乎没有捕捉能力，说明GLDAS对降雪的再现能力不足，而在2015年前后，GLDAS的固态降水观测能力提升，表明GLDAS系统升级后解决了冬季固态降水捕捉能力不足的缺陷。在1月和7月份，GLDAS亦不能很好的再现降水的时间变化，原因可能也是固态降水捕捉能力不足。CRA40/Land在1982—1986年的7月份出现低估现象，表明图4中显示的内蒙古地区、半湿润区和半干旱区CRA40/Land低估区域平均降水，主要由于CRA40/Land在1982—1986年的7月份或夏季其他月份出现低估导致。另外，从图5中看出ERA5均高估了4个月份的降水量。

从内蒙古地区4种降水资料的统计特征来看（表2）,4种降水资料的时间相关系数均高于0.97，

![](images/51eaa4d3ef1d72e1a5392aaae2df89c21af8192aebf83cd72777857c38c48eb2.jpg)  
图3内蒙古地区及其4个气候分区1982—2018年4种月降水资料与观测资料的比较 Fig.3 Comparison between the observed and 4 precipitation datasets of monthly precipitation over Inner Mongolia and its 4 climatic division areas in 1982-2018

![](images/1b10d2762b11a4076e33caab71c18e3c513aff4b39691d9f6ebaa6bc0e9697ad.jpg)  
图41982—2018年4种降水资料在内蒙古地区及其4个气候分区的月降水偏差时间序列 Fig.4Time series of monthly precipitation bias of 4 precipitation datasets over Inner Mongolia and its 4 climatic division areas in 1982-2018

![](images/71d9bc77619547dc35f260fe935388b3c2db80a526a2b534eb20bcbfe948eca5.jpg)  
图54种降水资料在内蒙古地区逐月平均降水变化  
g. 54 precipitation datasets and observed monthly precipitation averaged over Iner Mongolia in 4 months of 1982.

# 表21982—2018年内蒙古地区4种降水资料的统计特征

Tab.2 The statistical characteristics of four precipitation datasetsoverInner Mongolia from1982 to 2018   

<html><body><table><tr><td>资料</td><td>相关系数</td><td>平均绝对误差</td><td>均方根误差</td><td>纳什效率系数</td></tr><tr><td>FLDAS</td><td>0.984*</td><td>3.7578</td><td>6.119</td><td>0.9607</td></tr><tr><td>ERA5</td><td>0.9865*</td><td>7.3865</td><td>9.1851</td><td>0.9116</td></tr><tr><td>CRA40/ Land</td><td>0.9874*</td><td>2.5021</td><td>5.0748</td><td>0.973</td></tr><tr><td>GLDAS</td><td>0.9789*</td><td>4.0333</td><td>6.4475</td><td>0.9564</td></tr></table></body></html>

注：\*表示通过了 $9 9 . 9 \%$ 的信度检验。

通过了 $9 9 . 9 \%$ 的信度检验，4种降水资料的相关系数差距较小；从绝对平均偏差来看，CRA40/Land绝对平均偏差最小，ERA5最大，FLDAS优于GLDAS；从均方根误差来看，CRA40/Land最小，其次为FLDAS,ERA5依然最大，说明ERA5资料离散度稍大；从纳什效率系数来看，CRA40/Land最接近1，说明CRA4O/Land性能最优，FLDAS次之，GLDAS稍差于FLDAS，但仍然超过了0.9，说明4种资料对降水的再现性能均较好。综合以上来看，在统计意义上CRA4O/Land最优，FLDAS次之。

从时间和空间两个角度对4种降水资料与观测资料进行统计分析。从时间角度，逐月计算4种降水资料与站点观测资料的统计特征；从空间角度，计算每个站点1982—2018年逐月观测资料与4种降水资料之间的统计特征。

从不同月份4种降水资料与观测资料的统计特征可以看出(图6)，在相关系数方面，除GLDAS在冬季、春初和秋末较差外，其余3种资料相关系数均在0.6以上，表明3种资料对降水时间变化描述较好，CRA40/Land和ERA5的相关系数显著好于FLDAS和GLDAS，GLDAS最差;FLDAS和GLDAS的相关系数有着明显的季节特征，均为相关系数在冬季最差，表明FLDAS和GLDAS资料对冬季降水的时间变化再现能力差于其他时间段。4种资料在不同月份的平均绝对误差和均方根误差有着类似特征，即冬季最小，夏季最大，春秋次之，季节变化明显，即4种资料在夏季离散度最高，冬季最低。在平均误差方面，ERA5在夏季最大冬季最小，FLDAS在夏季最大，其他季节均较小;CRA40/Land和GLDAS分别在7月和6月负偏差明显，其他月份较小，说明ERA5和FLDAS在夏季高估降水，CRA4O/Land和GLDAS则分别在7月和6月低估了降水。在纳什效率系数方面，ERA5在6一8月较好，其余月份较差;FLDAS、CRA40/Land和GLDAS相似，除在冬季稍差外，其他月份均较好，表明ERA5仅在夏季质量和可信度较好，其余3种降水在除冬季外，资料质量较好，可信度高。综上分析，在统计特征上CRA4O/Land最优，其次为FLDAS。

![](images/66247d999b672e8f2634287ee69377582027d3546c6f1c9ffa4b49140efd9de5.jpg)  
图6不同月份4种降水资料与观测资料的统计特征  
Fig.6 Statistical characteristics between 4 precipitation datasets and observed data in diffrent months

1982—2018年4种降水资料在各个观测站处的相关系数和均方根误差空间分布由图7和图8所示。从图7可以看出，4种资料的相关系数呈现从东北向西部递减的分布特征，说明4种降水资料均对内蒙古中东部的半湿润、半干旱区降水变化趋势把握较好，对西部干旱和极干旱区降水变化再现能力稍差，其中CRA40/Land的相关系数总体最好，GL-DAS最差。从图8可以看出，4种降水资料的均方根误差自半湿润区依次向半干旱、干旱区递减，即在降水量大的区域RMSE大于干旱和极干旱区的RMSE，这主要是因为半湿润区和半干旱区相对来说降水量大，在干旱区和极干旱区降水量小，所以其RMSE也相对较小，CRA4O/Land在RMSE方面表现最优、FLDAS次之、ERA5稍差、GLDAS最差。

# 2.44种降水资料精度的总体评价

逐月降水量随时间的波动对评估4种降水资料有重要作用。从内蒙古地区及其4个气候分区的区域平均1982—2018年逐月、1月、4月、7月和10月降水的泰勒图中可以看出(图9)，4种资料在不同区域的相关系数均在0.7以上，4种资料之间差距不显著，从规范化标准差看，ERA5偏大较多，其余3种较为接近1，综合性能在半湿润、半干旱区显著好于干旱区和极干旱区，CRA4O/Land和FLDAS最优。从1月、4月、7月和10月降水量的泰勒图来看，CRA40/Land相关系数最优、ERA5的相关系数次之，但ERA5在冬季高估2倍多，GLDAS在冬季偏少较多，FLDAS质量仅次于CRA40/Land；在4月和10月，4种资料相关系数均高于0.5，CRA40/Land和ERA5的相关系数最优，FLDAS和GLDAS均出现低估现象，其中GLDAS低估严重;在7月，4种资料的模拟性能均较好,相关系数均高于0.7,规范化标准差也接近1；总的来说CRA4O/Land性能最优，FLDAS次之，ERA5稍差于FLDAS，主要体现在ERA5总是高估降水,GLDAS性能最差。

# 3讨论

内蒙古地区降水空间分布东西差异大，区域差异性明显，降水呈现由东向西逐渐增多的分布特征。降水的空间分布主要受由纬度、海拔、坡度和地形的影响[28-29]。内蒙古从东向西有大兴安岭、阴山山脉和贺兰山等地形阻挡影响，而这些山脉也位于东亚季风边缘区，山坡东部和南部受东亚季风影响强于西北坡3%，来自东南部的水汽抬升易形成降水，到达山脉西北部的水汽较少，故而东南部降水量大于西北部。然而这些山区也是气象模拟的复杂区域之一。再分析降水资料中地形降水的计算受到数值模式分辨率和物理过程的影响[31]。在这些山区区域，较粗分辨率的数值模拟将地形变得更加平滑，ERA5资料采用的IFS数值模式空间分辨率为 $3 4 ~ \mathrm { k m } \times 3 4 ~ \mathrm { k m }$ ，无法较好的模拟出与实际地形相似的山区地形和粗糙的地表[32]

![](images/4a9afbb62e58b601e73b025bf822db22aed55cf4bcbcc3c633e5bf651867e8e0.jpg)  
图74种降水资料的相关系数空间分布  
Fig.7Spatial distribution of correlation coefficients of 4 precipitation datasets

FLDAS降水资料和GLDAS降水资料均为NASA开发的陆面数据同化产品，在内蒙古区域FL-DAS降水质量显著好于GLDAS资料，主要原因在空间分辨率和融合的观测资料两方面。FLDAS空间分辨率为 $0 . 1 ^ { \circ } \times 0 . 1 ^ { \circ }$ ，显著高于GLDAS的 $0 . 2 5 ^ { \circ } \times$

$0 . 2 5 ^ { \circ }$ ，能够分辨解析更多的局地降水信息。另外，研究采用邻近格点法以减小站点与格点匹配的误差[27],GLDAS网格较粗，而气象站点降水观测代表性有限，气象站对 $0 . 2 5 ^ { \circ } \times 0 . 2 5 ^ { \circ }$ 的网格代表性要差于对$0 . 1 ^ { \circ } { \times } 0 . 1 ^ { \circ }$ 的网格代表性。在融合观测资料方面，FL-DAS降水资料主要来源为CHIRPS降水，CHIRPS降水是卫星红外观测资料、CHPclim监测月降水、TRMM3B42降水产品和站点观测降水数据融合后的资料，观测信息要多于GLDAS使用的普林斯顿降水资料。FLDAS降水中融合了更多观测资料，使得FLDAS降水资料的统计特征明显好于GLDAS，明显改进了GLDAS无法模拟冬季降水的缺陷。

CRA40/Land降水资料融合了地面雨量计资料和卫星降水，在中国区域融合了更多的站点观测，故而CRA40/Land降水资料的相关系数是4种资料中最优的；但CRA40/Land降水资料在1983—1986年出现较大的负偏差，分析显示，CRA40/Land降水资料在1983—1986年7月出现明显低估是CRA40/

![](images/057e60ac0629b9ce97e0a8327e9a448407fd6659823d681a56183b5a52343e12.jpg)  
图84种降水资料的均方根误差分布  
Fig.8 Spatial distribution ofRMSE of 4 precipitation datasets

Land降水资料出现负偏差的主要原因。综合研究表明，高时空分辨率的陆面同化降水资料FLDAS对内蒙古的降水具有很好的再现能力，优于ERA5再分析降水资料和GLDAS降水资料；虽然再分析降水资料的相关系数较高，但偏差较大。另外，4种降水资料在半湿润区和半干旱区的模拟能力优于在干旱区和极干旱区的模拟能力，主要由于4种降水资料对降水较少的区域模拟能力不足有关。高时空分辨率、高质量的格点降水资料是对无站点观测区域和站点观测稀疏区域的降水观测有益的补充，对区域性降水引发的灾害监测提供了途径，也为无资料区域陆面模式、水文模式模拟提供数据源。

尽管对4种降水资料在内蒙古及不同气候分区的质量进行了评估，由于内蒙古各区域站点观测并不均匀，因而给评估带来一定的不确定性，尤其是极干旱区仅有3个站点，因而评估可信度可能受影响。另外，CRA40/Land同化了中国区域气象站观测降水资料，因而本次评估得到的各项统计特征均较高，但从空间分布上来看，FLDAS资料更优，解析出更多局地细节，与此同时FLDAS资料分辨率更精细；鉴于CRA40/Land同化了站点观测资料，统计特征计算结果为非独立性检验，故今后需要使用区域站点观测资料进一步评估CRA40/Land的降水再现能力。

# 4结论

本文利用1982—2018年内蒙古地区115个气象站观测月降水资料对FLDAS、ERA5、CRA40/Land和GLDAS4种月降水资料的可靠性进行了系统评估。得出如下主要结论：

(1）4种降水资料在内蒙古地区从东北向西部递减，与气象站观测降水的分布特征一致。从降水空间分布上看，FLDAS和CRA4O/Land降水资料最优，尤其是FLDAS的空间分辨率最高。ERA5降水高估较多。从时间变化的模拟上看，4种降水资料在夏季的偏差最高，冬季最低，ERA5降水资料的偏差在2000年以后有明显下降的趋势，FLDAS降水资料的偏差有增高的趋势

![](images/e0d4a1b3fe5be68e46d475b98eb7aa4ec5d1911d787b725e8d49201d6fd0421c.jpg)  
注：1代表内蒙古地区;2代表半湿润区;3代表半干旱区;4代表干旱区;5代表极干旱区。 图94种降水资料在内蒙古地区及其4个气候分区的月降水与观测降水的泰勒图 Fig.9Taylor diagrams for monthly precipitation among 4 precipitation datasets with observed precipitation over Inner Mongolia and its 4 climate divisions

（2）统计分析表明，4种降水资料对降水的再现能力与降水量的时间变化有关，在夏季4种降水资料对区域平均降水的相关系数模拟能力明显优于其他季节，在冬季最差，但偏差表现与相关系数相反。在空间统计特征上，4种降水资料的相关系数从东北向西部递减，均方根误差在半湿润和半干旱区高于在干旱和极干旱区。4种资料中CRA40/Land的统计特征最优，FLDAS次之，GLDAS最差。

（3）从整体性能来看，CRA4O/Land和FLDAS有着最优的质量。且4种降水资料在半湿润、半干旱区的质量显著优于其在干旱、极干旱区的质量。4种降水资料在各月的整体性能不一，在夏季性能表现最好，冬季性能表现最差。

# 参考文献(References)：

[1]Kidd C,Huffman G.Global precipitation measurement[J]. Meteorological Applications,2011,18(3): 334-353.   
[2]Chen Y, Sharma S, Zhou X,et al. Spatial performance of multiple reanalysis precipitation datasets on the southern slope of central Himalaya[J].Atmospheric Research,2020,250:105365.   
[3]闫燕,刘罡,何军,等.重庆地区卫星及再分析降水资料评估[J]. 高原气象,2020,39(3): 594-608.[Yan Yan,Liu Gang,He Jun,et al.Assessment of satellite and reanalysis precipitation data in Chongqing[J]. Plateau Meteorology,2020,39(3): 594-608.]   
[4]Tapiador FJ,Turk FJ,Petersen W,et al.Global precipitation measurement: Methods,datasets and applications[J]. Atmospheric Research,2012,104-105:70-97.   
[5]汪君,王会军,洪阳.一个新的高分辨率洪涝动力数值监测预报 系统[J].科学通报,2016,61(增刊):518-528.[Wang Jun,Wang Huijun,Hong Yang.A high-resolution flood forecasting and monitoring system for China using satellite remote sensing data[J]. Chinese Science Bulletin, 2016, 61(Suppl. ): 518-528.]   
[6]Jiang S,Ren L, Hong Y,et al.Comprehensive evaluation of multisatelite precipitation products with a dense rain gauge network and optimally merging their simulated hydrological flows using the Bayesian model averaging method[J]. Journal of Hydrology,2012, 452-453:213-225.   
[7]王炳尧,刘星辰,刘立超.1957—2017年腾格里沙漠地区降水 量[J].中国沙漠,2020,40(4):163-170.[Wang Bingyao,Liu Xingchen,Liu Lichao. Characteristics of precipitation in the surrounding area of Tengger Desert in 1957-2017[J].Journal of Desert Research,2020,40(4): 163-170.]   
[8]王玉丹,陈浩,刘璨然,等.ITPCAS 和CMORPH两种遥感降水 产品在陕西地区的适用性研究[J].干旱区研究,2018,35(3): 579-588.[Wang Yudan,Chen Hao,Liu Canran, et al.Applicability of ITPCAS and CMORPH precipitation datasets over Shaanxi province[J].Arid Zone Research,2018,35(3): 579-588.]   
[9]刘田,阳坤,秦军,等.青藏高原中、东部气象站降水资料时间序 列的构建与应用[J].高原气象,2018,37(6):1449-1457.[Liu Tian,Yang Kun,Qin Jun,at al. Construction and applications of time series of monthly precipitation at weather stations in the central and eastern Qinghai-Tibetan plateau[J]. Plateau Meteorology, 2018, 37(6): 1449-1457.]   
[10] 宇婧婧,沈艳,潘肠,等.概率密度匹配法对中国区域卫星降水 资料的改进[J].应用气象学报,2013,24(5):544-553.[Yu Jingjing,Shen Yan,Pan Yang,at al. Improvement of satellitebased precipitation estimates over China based on probability density function matching method[J]. Journal of Applied Meteorological Science,2013,24(5): 544-553.]   
[11] 潘旸,谷军霞,宇婧婧,等.中国区域高分辨率多源降水观测产 品的融合方法试验[J].气象学报,2018,76(5):755-766.[Pan Yang,Gu Junxia,Yu Jingjing,et al.Test of merging methods for multi-source observed precipitation products at high resolution over China[J]. Acta Meteorologica Sinica,2018,76(5): 755-766.]   
[12]Lu D,Yong B.Evaluation and hydrological utility of the latest GPM IMERG V5 and GSMaP V7 precipitation products over the Tibetan Plateau[J]. Remote Sensing,2018,10(12): 2022.   
[13] Sharma S,Chen Y,Zhou X,et al.Evaluation of GPM-Era satelite precipitation products on the southern slopes of the central Himalayas against rain gauge data[J]. Remote Sensing,2O2o,12(11): 186.   
[14]Dinku T,Connor S J, Ceccato P.Comparison of CMORPH and TRMM-3B42 over Mountainous Regions of Africa and South America: SatellteRainfall Applications for Surface HydrologyM]. Dordrecht: Springer Press, 2010.   
[15]Funk C,Peterson P,Landsfeld M,et al. The climate hazards infrared precipitation with stations:A new environmental record for monitoring extremes[J].Scientific Data,2015,2(1): 1-21.   
[16]Sahlu D,Moges SA,Nikolopoulos EI,et al. Evaluation of highresolution multi-satelite and reanalysis rainfall products over East Africa[J]. Advances in Meteorology,2017,2017: 1-14. https: //doi. org/10.1155/2017/4957960.   
[17]王文,汪小菊,王鹏.GLDAS 月降水数据在中国区的适用性评 估[J].水科学进展,2014,25(6):769-778.[Wang Wen,Wang Xiaoju,Wang Peng.Assessing the applicability of GLDAS monthlyprecipitation data in China[J].Advances in Water Science, 2014, 25(6): 769-778. ]   
[18]Dee D P, Uppala S M, Simmons A J,et al. The ERA-Interim reanalysis: Configuration and performance of the data assimilation system[J]. Quarterly Journal of the Royal Meteorological Society, 2011, 137(656): 553-597.   
[19]Hersbach H,BellB,Berrsford P,etal. The ERA5 global reanalysis[J].QuarterlyJournaloftheRoyal MeteorologicalSociety, 2020,146(730): 1999-2049.   
[20]Saha S,Moorthi S,Pan HL,et al. The NCEPclimate forecast system reanalysis[J]. Bulletin of the American Meteorological Society, 2010, 91(8): 1015-1058.   
[21] 张蒙,黄安宁,计晓龙,等.卫星反演降水资料在青藏高原地区 的适用性分析[J].高原气象,2016,35(1):34-42. [Zhang Meng, Huang Anning,Ji Xiaolong,etal.Validationofsatelite precipitation products over Qinghai-Xizang Plateau Region[J]. Plateau Meteorology,2016,35(1): 34-42.]   
[22]Li Chunxiang,Zhao Tianbao,Shi Chunxiang,et al.Evaluation of daily precipitation product in China from the CMA global atmospheric interim reanalysis[J]. Journal of Meteorological Research, 2020,34(1): 117-136.   
[23]Molod A,Takacs L, Suarez M,et al.Development of the GEOS-5 atmospheric general circulation model: Evolution from MERRA to MERRA2[J]. Geoscientific Model Development, 2015,8(5):1339- 1356.   
[24]McNally A,Arsenault K,Kumar S,et al.A land data assimilation system for sub-Saharan Africa food and water security applications [J]. Scientific Data, 2017,4(1): 1-19.   
[25]McNally A,Verdin K,Harrison L,et al.Acute Water-Scarcity monitoring for Africa[J].Water,2019,11(1O):1968.   
[26]He J,Yang K,Tang W,etal.The first high-resolution meteorological forcing dataset for land process studies over China[J]. Scientific Data,2020, 7(25): 1-12.   
[27] 刘川,余晔,解晋,等.多种土壤温湿度资料在青藏高原的适用 性[J].高原气象,2015,34(3):653-665.[Liu Chuan,Yu Ye,Xie Jin,et al.Applicability of soil temperature and moisture in several datasets over Qinghai- Xizang Plateau[J].Plateau Meteorology, 2015,34(3): 653-665.]   
[29]Smith R B, Barstad I.A linear theory of orographic precipitation [J]. Journal of Atmospheric Sciences,2004,61(12): 1377-1391.   
[29]Blocken B,Poesen J,Carmeliet J.Impact of wind on the spatial distribution of rain over micro-scale topography-numerical modellingand experimental verification[J].Hydrological Processes, 2006,20:345-368.   
[30] 申露婷,张方敏,黄进,等.1961—2018 年内蒙古生长季昼夜降 水气候特征[J].干旱区研究,2020,37(6):1519-1527.[Shen Luting,Zhang Fangmin,Huang Jin,et al.Climate characteristics of day and night precipitation during the growing season in Inner Mongolia from 1961 to 2018[J].Arid Zone Research,2020,37(6): 1519-1527.]   
[31]Fallah A,Rakhshandehroo GR,Berg P,et al.Evaluation of precipitation datasets against local observations in southwestern Iran[J]. International Journal of Climatology,2020,40(9): 4102-4116.   
[32]Wang Y,YangK,Zhou X,etal. Synergy of orographic drag parameterization and high resolution greatly reduces biases of WRF-simulated precipitation in central Himalaya[J]. Climate Dynamics, 2020,54:1729-1740.

# Validation of land data assimilation and reanalysis precipitation datasets over Inner Mongolia

SONG Haiqing'²， ZHU Zhongyuan'， LI Yunpeng² (1.Water Conservancyand CivilEngineeringColege,Inner MongoliaAgriculturalUniversity,HohhotOO18,Inner Mongolia,China;2.Ecologyand AgrometeorologyCenterofInner Mongolia,HohhotO1Oo51,Inner ongolia,China)

Abstract: Monthly precipitation data observed at115 weather stations in Inner Mongolia during 1982-2018 was compared with land data assmilation and reanalysis precipitation datasets [Famine Early Warning Systems Network (FEWS NET) Land Data Assmilation System (FLDAS), the Fifth Generation of ECMWF Reanalysis (ERA5), China Meteorological Administration, Global Land surface Reanalysis (CRA40/Land),and Global Land Data Assimilation System (GLDAS)]. The reliability of the four precipitation datasets was analyzed and accuracy of monthly variation was also evaluated.The results showed that the four precipitation datasets captured features of precipitation distribution.Precipitation levels decreased from the northeast to west and were lower in wnter and higher in summer.By analyzing correlation coefficients,mean absolute errors,mean bias errors,root mean square errors，and Nash- Sutcliffe effciency coeficients，the four precipitation datasets showed the best performance in summer and the worst performance in winter,and better values in eastern semi-humid and semiarid areas than westerm arid and extremely arid areas. Compared with ERA5 and GLDAS,FLDAS,and CRA40/Land showed the lowest differences from observed values and the best statistical characteristics.ERA5 data mostly overestimated precipitation in Inner Mongolia during most of the study period,while GLDAS underestimated it. Particularly in winter, GLDAS showed almost no observation capability for snow precipitation, while the newly released FLDAS data performed beter. Overall,FLDAS and CRA40/Land precipitation datasets performed best with better statistical power.

Keywords: precipitation； land assimilation data; reanalysis data; applicability