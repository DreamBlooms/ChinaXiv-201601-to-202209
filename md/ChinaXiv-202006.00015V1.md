# 基于FY-3D/MERSI-ⅡI归一化积雪指数和MOD10A1的精度对比分析

陈鹏，王勇，张 青，李悦 （乌鲁木齐气象卫星地面站，新疆 乌鲁木齐 830011)

摘要：风云三号D星(FY-3D)是我国新一代极轨气象卫星，中分辨率光谱成像仪I（MERSI-II)是其携带的核心传感器之一，MERSI-Ⅱ实现了云、气溶胶、水汽、陆地表面特性、海洋水色等大气、陆地、海洋参量的高精度定量反演。选取2018年7、8月无云时相的FY-3D/MERSI-I数据对天山中段终年积雪进行归一化积雪指数(NDSI)的计算。结合高分辨率Landsat-8 影像，利用混淆矩阵对FY-3D/MERSI-Ⅱ数据计算结果与同期MODIS日积雪产品数据MOD10A1进行精度对比分析。结果表明:FY-3D/MERSI-Ⅱ图像平均总体精度为0.855,MOD10A1图像平均总体精度为0.820,FY-3D/MERSI-Ⅱ积雪覆盖提取平均总体精度比 MOD10A1积雪覆盖提取平均总体精度高0.035。FY-3D/MERSI-II的Kappa 系数平均值为0.659,MOD10A1的Kappa 系数平均值为0.558,FY-3D/MERSI-Ⅱ的 Kappa 系数平均值大于MOD10A1的 Kappa 系数平均值。故FY-3D/MERSI-Ⅱ数据提取积雪覆盖面积精度更高，更接近高分辨率Landsat-8影像目视解译结果。

关键词：FY-3D/MERSI-II；MOD10A1；归一化积雪指数；精度对比分析文章编号：

积雪亦称雪被或雪盖，是覆盖在地球表面的雪层，具有极高的不稳定性，按积雪持续时间的长短，分为终年不消的永久积雪和冬季形成、夏季消失的季节积雪[1]。积雪不仅是气候变化的指示器,对土壤也有保温蓄水的作用，而且在我国高寒山区和干旱半干旱地区,积雪还是重要的淡水资源[2]。因此利用遥感技术准确监测积雪覆盖范围就成为地球系统科学的一项重要研究目标[3-4] ○

自20世纪80年代以来，国内外积雪监测普遍用到的卫星遥感数据主要有Landsat卫星数据、SPOT卫星数据、NOAA/AVHHR卫星数据以及MODIS/TERRA卫星数据[4-5]。特别是NOAA/AVHHR卫星数据和MODIS/TERRA卫星数据，在积雪监测领域进行了大量的科学研究，取得了一系列的研究成果[6]。马虹等[7]利用NOAA-AVHRR数据进行积雪监测与制图的方法研究。季泉[通过对遥感卫星资料中云和雪的光谱特征分析，提出利用 MODIS数据进行云、雪监测和分离的方法。郝晓华等[9]以祁连山中部山区为例对 MODIS 雪盖制图中 NDSI阈值进行了检验。萨楚拉等[10]利用2002—2012年 MODIS 积雪产品数据 MOD10A2对新疆积雪面积时空变化进行了研究。刘金平等[1]利用MODIS遥感积雪产品对2001—2013年中亚干旱区季节性积雪进行了监测以及分析了积雪时空分布特征。

风云三号（简称FY-3）气象卫星是为了满足我国天气预报、气候预测和环境监测等方面的迫切需求建设的第二代极轨气象卫星，其目标是获取地球大气环境的三维、全球、全天候、定量、高精度资料，实现大范围气象及其衍生自然灾害和生态环境变化监测[12]。风云三号A星、B星、C 星以及D星分别于2008年、2010年、2013年、2017年成功发射。风云三号D星是该系列的第四颗卫星，将接替2010年发射的风云三号B试验卫星，作为下午星，与2013年发射的上午星风云三号C星开展全球对地组网观测。与C星相比,D星技术更加成熟,在进一步提高核心遥感仪器的可靠性、稳定性和高探测精度的基础上，新增了红外高光谱大气探测仪、高光谱温室气体监测仪、广角极光成像仪、电离层光度计在内的4个新型遥感仪器，提高了与气候变化密切关联的温室气体监测能力，增强了空间环境综合探测能力[13-14]。其影像已在大雾、冰凌、积雪覆盖、水情、火情等方面得到一定范围的应用[15-16]。其空间分辨率和波段设置与EOS/MODIS卫星相近，部分性能和参数还优于EOS/MODIS卫星，因此开展基于FY-3D卫星的积雪监测研究不仅保证了积雪监测业务的连续性，也可进一步推动国产卫星数据的应用研究[6,17]

目前国内学者利用FY3/MERSI数据进行了植被长势监测和类型分布研究、旱情空间分布和动态发展、洪涝灾害动态监测评估、水体污染监测等方面的研究[1,18-21]。特别是在植被方面,冯锐等[22]、武鹏飞等[23]对FY3/MESRI和EOS/MODIS归一化植被指数进行差异分析，结果表明二者所得NDVI存在很好的线性一致性。积雪覆盖监测是FY-3系列卫星的重要应用领域之一，本文旨在利用归一化积雪指数(NDSI)得到FY-3D/MERSI-II积雪覆盖提取结果，结合高分辨率Landsat-8影像，利用混淆矩阵与同期MODIS日积雪产品数据MOD10A1进行精度对比分析。

# 1研究方法与数据处理

# 1.1 研究方法

1.1.1冰雪覆盖遥感监测原理根据张旭等[17]基于FY3/VIRR数据的积雪遥感监测分析研究以及张永宏等[6FY3/VIRR 资料积雪多阀值综合判识方法研究可知：冰雪在近红外、远红外、可见光和微波波段的光谱特征是冰雪覆盖遥感监测的主要依据。雪在可见光波段有较强的反射特性，在短波红外波段有较强的吸收特性。可见光波段和远红外波段雪和云的反射率很相近，而在 $1 . 6 ~ \mu \mathrm { m }$ 和 $2 . 1 ~ \mu \mathrm { m }$ 附近的近红外波段上，云和雪的反射率有很大的差异，在这两个波段范围内云反射来自太阳的辐射，表现出较高的反射率；而积雪则吸收来自太阳的辐射，反射率很低。因此，利用这两个波段可以很好的区分云、雪，为冰雪覆盖遥感监测提供依据。

1.1.2积雪遥感方法归一化积雪指数是指：Nor-malizedDifferenceSonwIndex,简写为NDSI,类似于归一化植被指数(NDVI)，通过波段比可以有效区分积雪与其他地物。其原理是利用积雪在可见光波段的强反射及近红外波段低反射的物理特性进行归一化处理，使积雪明显的与云和非积雪覆盖的地表区分开,同时还部分消除了大气的影响[24]。计算公式如下[25]：

$$
\left. N D S I = ( \left. b _ { \tt H B U X } - b _ { \tt i f f i b } \right) \right/ ( \left. b _ { \tt i f f i b j \tt t } + b _ { \tt i f f b } \right)
$$

式中： $b _ { \perp \perp \perp \perp \perp }  b _ { \mathrm { i } \perp \perp \perp \perp \rrangle  }$ 分别在 MODIS 积雪覆盖产品MOD10A1中是第 $4 ~ ( ~ 0 . ~ 5 4 5 ~ \sim ~ 0 . ~ 5 6 5 ~ \mu \mathrm { m } )$ 、第6二 $\cdot 1 . 6 2 8 \sim 1 . 6 5 2 ~ \mu \mathrm { m } )$ 波段,在FY-3D/MERSI- $\mathbb { I }$ 中是第 $2 ( 0 . 5 2 5 \sim 0 . 5 7 5 ~ \mu \mathrm { m } )$ ）、第 $6 \left( 1 . 5 9 0 \sim 1 . 6 9 0 ~ \mu \mathrm { m } \right)$ 波段。

# 1.2 数据处理

选取的FY-3D/MERSI-Ⅱ数据来源于本单位接收，将其进行转投影、几何校正、辐射定标、裁剪等预处理之后，通过公式1计算得到NDSI值，其计算所需波段的可见光中心波长为 $0 . 5 5 0 ~ \mu \mathrm { m }$ ,空间分辨率$2 5 0 \mathrm { ~ m ~ }$ ,近红外中心波长为 $1 . 6 4 0 ~ { \mu \mathrm { m } }$ ,空间分辨率$1 ~ \mathrm { k m }$ 。MODIS日积雪产品数据MOD10A1，其空间分辨率为 $5 0 0 \mathrm { ~ m ~ }$ ，通过美国国家航空航天局官网（ht-tps://ladsweb.modaps.eosdis.nasa.gov/）下载得到。将MOD10A1数据进行转投影、裁剪等预处理之后，统计积雪覆盖结果。高分辨率影像Landsat-8，来源于网站（https://landsatlook.usgs.gov/）下载,对其目视解译将积雪覆盖区域手动画出，将此分类结果作为精度分析的基准。最后将所有数据统一到相同空间分辨率，以便下一步分析。由于新疆区域比较大，因此每期影像选择位于天山中段终年积雪区进行分析，天山山区内有大量的季节性积雪在夏季融化[26-28],而未融化的积雪属于永久性积雪,通常都覆盖在高海拔的冰川上,性质比较稳定[10],最终影像资料选择2018年7月11日、17日，8月15日、21日4d无云天气。

# 2 结果分析

# 2.1 积雪分类结果分析

由前人的研究可知，对于一幅影像来说，阈值取值越大，识别出的积雪像元越小，进而出现积雪面积的低估[28]。为了选取合适的阈值,将FY-3D/MER-SI-Ⅱ影像按照公式1进行处理后，按照 $0 . 2 5 < N D S I$ $< 0 . 4 0 , 0 . 0 1$ 为步长提取积雪像元。将FY-3D/

MERSI-Ⅱ所提取出的积雪像元个数与Landsat-8目视解译结果相比较，发现当NDSI取0.35时，所识别的积雪像元个数与目视解译结果最为接近。图1a为2018年7月17日积雪像元提取结果，图1b为高分辨率Landsat-8影像示意图，其中白色部分为积雪覆盖。由图1可以看出，NDSI阈值选取0.35时，FY-3D/MERSI-ⅡI所提取出的积雪覆盖面积与左图的高分辨率Landsat-8积雪覆盖大体一致。故将所有FY-3D/MERSI- $\mathbb { I }$ 影像按照 $N D S I > 0 . 3 5$ 进行积雪像元的提取。

MOD10A1产品中，当 $N D S I > 0 . 4 0$ 、区别水体引入第2通道的反射率 $> 1 1 \%$ 、排除阴影等造成的暗目标影响设定第4通道的反射率 $< 1 0 \%$ ，同时还必须满足上述3个条件时，则认为陆面是雪。这种阈值判别可以很好的区分水体、植被、阴影等被误判为积雪。图2为2018年7月17日FY-3D/MERSI-Ⅱ和MOD10A1积雪像元对比图。不论是FY-3D/MERSI-ⅡI提取的积雪覆盖面积，还是MOD10A1的积雪覆盖面积均小于目视解译结果，且FY-3D/MERSI-Ⅱ提取出的积雪像元要多于MOD10A1结果。其中FY-3D/MERSI-Ⅱ积雪像元个数为10322个，MOD10A1积雪像元个数为9269个，特别是在边缘处，MOD10A1所识别的积雪像元比FY-3D/MERSI-Ⅱ少。

# 2.2 总体精度分析

混淆矩阵是用来表示精度评价的一种标准格式，对角线上的像元个数为被正确分类的样本数，非对角线上的像元个数为错分的样本数。总体分类精度是具有概率意义的一个统计量，表述的是对每一个随机样本，所分类的结果与参考数据所对应区域的实际类型相一致的概率。它等于被正确分类的像元总和除以总像元数，被正确分类的像元数目沿着混淆矩阵对角线分布，它显示出被分类到正确地表真实分类中的像元数，像元总数等于所有地表真实分类中的像元总和[27]。计算公式如下：

![](images/17da1e841de84df9b4422e0e3e03790db398a4fb316abc58e87c3fb82e9ed1c5.jpg)

![](images/6993d6d608af1c46e4cbdc0691f721e410b8b4a5e4dfb36924420dc6aa40e250.jpg)  
图1FY-3D/MERSI-ⅡI提取积雪结果( $N D S I > 0 . 3 5$ 与Landsat-8影像示意图Fig.1Snow pixels of the FY-3D/MERSI- II( $N D S I > 0 . 3 5$ ）and Landsat-8  
图2FY-3D/MERSI-ⅡI和 MOD10A1 积雪比较示意图Fig.2Snow pixels of the FY-3D/MERSI-II and MOD10A1

$$
P _ { C } \ = \ \sum _ { k \ : 1 } ^ { n } P _ { k k } \bigg / P
$$

式中： $P _ { c }$ 为总体精度； $P$ 为样本总数; $P _ { \mathit { k } k }$ 为正确分类的像元数量。

针对FY-3D/MERSI- $\mathbb { I }$ 积雪覆盖提取结果和MOD10A1影像数据进行总体精度对比，结果如表1所示。通过对比2种影像各时段数据总体精度，发现FY-3D/MERSI-I影像总体精度在 $0 . 8 2 2 \sim 0 . 8 9 5$ 之间，MOD10A1影像总体精度在 $0 . 8 0 2 \sim 0 . 8 5 1$ 之间。由表1可知：FY-3D/MERSI-Ⅱ总体精度均大于MOD10A1，其中2018年7月11日总体精度二者相差最大，达到0.050，而2018年8月15日二者总体精度差最小,为0.006。FY-3D/MERSI-Ⅱ影像数据平均总体精度为0.855，MOD10A1影像数据平均总体精度为0.820,FY-3D/MERSI-ⅡI积雪覆盖提取平均总体精度比MOD10A1积雪覆盖平均总体精度高0.035。

表1FY-3D/MERSI-II和MOD10A1影像总体精度表 Tab.1Overall accuracy comparison between FY-3D/MERSI- II and MOD10A1   

<html><body><table><tr><td>时间</td><td>FY-3D/MERSI-II</td><td>MOD10A1</td></tr><tr><td>2018年7月11日</td><td>0.862</td><td>0.812</td></tr><tr><td>2018年7月17日</td><td>0.840</td><td>0.802</td></tr><tr><td>2018年8月15日</td><td>0.822</td><td>0.816</td></tr><tr><td>2018年8月21日</td><td>0.895</td><td>0.851</td></tr></table></body></html>

Kappa 系数是一种测定两幅图之间吻合度的指标，相对总体精度，可以更客观的评价分类质量。Kappa系数不仅考虑了被正确分类的像元，还考虑了不在混淆矩阵对角线上被错分和漏分的误差[28]计算公式如下：

$$
= \frac { N \sum X _ { k k } - \sum X _ { k + } X _ { + k } } { N ^ { 2 } - \sum X _ { k + } X _ { + k } }
$$

式中： $N$ 为像元总数； $X _ { k k }$ 为矩阵中第 $k$ 行、第 $k$ 列上的像元数量（即正确分类的数量）； $X _ { k + }$ 和 $X _ { + k }$ 为某一类真实参考像元数与该类中被分类像元总数之积后所有类别的求和。

将FY-3D/MERSI-ⅡI和 MOD01A1 积雪分类结果分别进一步分为4类：仅在分类图有积雪、仅在目视解译有积雪、分类图与目视解译共同非积雪和分类图与目视解译共同有积雪。然后利用混淆矩阵对分类图进行统计，之后进行Kappa 系数计算。FY-3D/MERSI-II和MOD01A1的Kappa分析结果如表2。

由表2可知,与总体精度一样，MOD10A1的积雪覆盖Kappa系数均小于FY-3D/MERSI-ⅡI积雪覆盖提取结果。FY-3D/MERSI-ⅡI的Kappa 系数最高值达到0.723，Kappa系数平均值也达到0.659；MOD10A1的Kappa系数最高值为0.596,Kappa系数平均值为0.558。参照表3可知FY-3D/MERSI-Ⅱ所提取的积雪覆盖精度为较好，而MOD10A1积雪分类结果仅为好。

<html><body><table><tr><td>时间</td><td>FY-3D/MERSI-II</td><td>MOD10A1</td></tr><tr><td>2018年7月11日</td><td>0.553</td><td>0.532</td></tr><tr><td>2018年7月17日</td><td>0.682</td><td>0.596</td></tr><tr><td>2018年8月15日</td><td>0.676</td><td>0.521</td></tr><tr><td>2018年8月21日</td><td>0.723</td><td>0.584</td></tr></table></body></html>

# 表3Kappa统计值与分类精度对应关系

表2FY-3D/MERSI-ⅡI和MOD10A1影像Kappa分析结果 Tab.2Kappa index comparison between FY3D/MERSI- II andMOD10A1   
Tab.3Kappa statistical values correspond to the classification accuracy relations   

<html><body><table><tr><td>Kappa统计值</td><td>分类精度</td><td>Kappa 统计值</td><td>分类精度</td></tr><tr><td><0.0</td><td>较差</td><td>0.4~0.6</td><td>好</td></tr><tr><td>0.0~0.2</td><td>差</td><td>0.6~0.8</td><td>较好</td></tr><tr><td>0.2~0.4</td><td>正常</td><td>0.8~1.0</td><td>非常好</td></tr></table></body></html>

# 3结论

风云三号D星(FY-3D)是我国新一代极轨气象卫星，中分辨率光谱成像仪I（MERSI-ⅡI)是其携带的核心传感器之一，FY-3D对于全球数值天气预报、大气定量探测以及气候变化监测等具有重要意义。其影像已在大雾、冰凌、积雪覆盖、水情、火情等方面得到一定范围的应用。

（1）FY-3D/MERSI-ⅡI积雪覆盖提取平均总体精度略高于MOD10A1平均总体精度，提高了$3 . 5 0 \%$ 。FY-3D/MERSI-ⅡI积雪覆盖提取结果Kap$p a$ 系数平均值为0.659，与高分辨率Landsat-8影像目视解译结果存在高度一致性，MOD10A1影像数据Kappa系数平均值为0.558，与高分辨率Landsat-8影像目视解译结果仅存在中等一致性。FY-3D/

MERSI-ⅡI积雪覆盖提取结果要优于MOD10A1影像数据。

（2）FY-3D/MERSI-I数据可以接替MODIS数据提供积雪监测数据源。利用FY-3D/MERSI-Ⅱ可以进行积雪覆盖分布和变化研究、积雪对气候的反馈及影响、雪灾预警和预报、模拟融雪径流过程等方面的研究。积雪覆盖监测可以成为FY-3D/MERSI-Ⅱ数据业务化产品之一。

总之，FY-3D/MERSI-ⅡI资料在积雪遥感方面的应用具有巨大的潜力，它将促进对地表生态环境及其变化的监测，使人们加深对整个地球环境的了解，为我国自主新型遥感数据的应用和相关部门减灾防灾提供借鉴和决策支持。

# 参考文献(References)

[1]黄晓东,张学通,李霞,等.北疆牧区 MODIS 积雪产品 MODIOA1和MOD10A2 的精度分析与评价[J].冰川冻土,2007,29 （5）:722-729.[HUANG Xiaodong,ZHANG Xuetong,LI Xia,et al.Accuracy analysis for MODIS snow products of MOD10A1 and MOD10A2 in northern Xinjiang area[J]. Journal of Glaciology and Geocryology,2007,29(5） :722 -729.]   
[2］卢元涛,张廷军.干旱、半干旱地区积雪变化及其与气候变化 的关系——以新疆维吾尔自治区为例[J].兰州大学学报（自 然科学版）,2018,54（5）：577-585.［LUYuantao,ZHANG Tingjun.Variability of snow cover and the relationship with climate change in arid and semi-arid areas: A case study of the Xinjiang Uygur Autonomous Region[J]. Journal of Lanzhou University(Natural Science）,2018,54(5） :577-585.]   
[3]XIAO X,ZHANG Q,BOLES S,et al. Mapping snow cover in the pan-Arctic zone using multi-year（1998-2001） images from optical VEGETATION sensor[J].International Journal of Remote Sensing,2004,25(24):5731- 5744.   
[4]RUTGER D,STEVEN M,DE J. Monitoring snow cover dynamics in northern Fennoscandia with SPOT VEGETATION images[J]. International Journal of Remote Sensing,2004,25（15）: 2933- 2949.   
[5］傅华,李三妹,黄镇,等.MODIS 雪深反演数学模型验证及分析 [J].干旱区地理,2007,30(6）:907-914.[FU Hua,LI Sanmei,HUANG Zhen,et al.Verification and analysis of mathematical model for retrieved snow depth based on MODIS data[J].Arid Land Geography,2007,30(6）:907-914.]   
[6]张永宏,任伟,曹庭,等.FY-3/VIRR资料积雪多阈值综合判识 方法研究[J].遥感技术与应用,2015,30（6)：1076-1084. [ZHANG Yonghong,REN Wei,CAO Ting,et al. Method of snow multi-threshold comprehensive discrimination with FY-3/VIRR data[J].Remote Sensing Technology and Application,2O15,30（6）： 1076 -1084.]   
[7］马虹,姜小光,余素芬,等.利用NOAA-AVHRR 数据进行积雪

监测与制图的方法研究[J].干旱区地理，1998，21（3）：73-

80.[MA Hong,JIANG Xiaoguang,YU Sufeng,et al. Sonw cover monitoring and mapping using NOAA-AVHRR data[J].Arid Land Geography,1998,21(3） :73-80.]   
[8］季泉.利用 MODIS 资料对积雪的遥感监测[J].广西气象,2005， 26(4）:21 -23.［JI Quan.Snow remote sensing monitoring by meansof MODISdataJ].Journalof Guangxi Meteorolog,00, 26(4):21-23.]   
[9］郝晓华,王建,李弘毅.MODIS 雪盖制图中NDSI阈值的检验一 以祁连山中部山区为例[J].冰川冻土.2008,30（1)：132 - 138.［HAO Xiaohua,WANG Jian,LI Hongyi.Evaluation of the NDSI threshold value in mapping snow cover of MODIS:A case study of snow in the middle Qilian Mountains[J]. Journal of Glaciology and Geocryology.2008,30（1）:132-138.]   
[10］萨楚拉,刘桂香,包刚,等.近10a新疆积雪面积时空变化研究 [J].测绘科学,2013,38（1）:72-74.[SA Chula,LIUGuixiang, BAO Gang,et al. Sptial-temporal changes ofsnow cover in Xinjiang in recent 10 years[J].Science of Surveying and Mapping,2013,8 (1):72 -74.]   
[11］刘金平,包安明,李均力,等.2001—2013 年中亚干旱区季节性 积雪监测及时空变异分析[J].干旱区地理,2016,39(2）：405 - 412.[LIU Jinping,BAO Anming,LI Junli,et al. Spatial and temporal characteristics of snow cover in arid area of Central Asia from 2001to2013[J].AridLand Geography,2016,39(2）:405 412.]   
[12］杨军,咸迪,唐世浩.风云系列气象卫星最新进展及应用[J]. 卫星应用,2018,（11）:8-14.［YANG Jun,XIANDi,TANG Shihao.The latest development andappication of Fengyun series meteorological satellites[J].Satelite Application,2018,（11）:8- 14.]   
[13］瞿建华,鄢俊洁,薛娟,等.基于深度学习的 FY3D/MERSI 和 EOS/MODIS 云检测模型研究［J].气象与环境学报,2019,35 (3）:87-93.[QU Jianhua,YAN Junjie,XUE Juan,et al.Research on cloud detection model of FY3D/MERSI and EOS/MODIS based on deep learning[J]. Journal of Meteorology and Environment,2019,35(3）:87-93.]   
[14］赵宏宇,郝晓华,郑照军,等.基于FY-3D/MERSI-ⅡI的积雪面 积比例提取算法[J].遥感技术与应用,2018,33(6):1004- 1016.[ ZHAO Hongyu,HAO Xiaohua,ZHENG Zhaojun,et al. A new algorithm of fractional snow cover basing on FY-3D/MERSIⅡ[J].Remote Sensing TechnologyandAplication,2018,33 (6):1004 -1016.]   
[15］蒋金雄,王铭实,鞠诗尧,等.基于FY-3D MERSI-2 数据的干 旱/半干旱地区地表温度反演[J].地球科学前沿,2019,9（8）： 693-702.[JIANG Jinxiong,WANG Mingshi,JU Shiyao,et al. Land surface temperature retrieval from FY-3D MERSI-2 data in the arid/semi-arid area[J].Advances in Geosciences,2019,9 (8):693 -702.]   
[16］朱爱军,胡秀清,林曼筠,等.风云三号D气象卫星全球数据获 取方法及数据分发[J].海洋气象学报,2018,38（3）:63-68. [ ZHU Aijun,HU Xiuqing,LIN Manyun,et al. Global data acquisition methods and data distribution for FY-3D meteorological satellite[J].Journal of Marine Meteorology,2018,38(3):63-68.]   
[17］张旭,杨志华,杨昌军,等.基于FY3/VIRR 数据的积雪遥感监 测分析[J].沙漠与绿洲气象,2016,10(3）:83－88.[ZHANG Xu,YANG Zhihua,YANG Changjun,et al.Analysis on snow cover in Altay region based on FY3/VIRR data[J].Desert and Oasis Meteorology,2016,10(3）:83-88.]   
[18］朱琳，刘健,张晔萍,等.FY-3A/MERSI数据在中国北方干旱监 测中的应用[J].遥感学报,2010，14（5）：1004－1016.［ZHU Lin,LIU Jian,ZHANG Yeping,et al.Application of FY-3A/MERSI satellite data to drought monitoring in north China[J].Journal of Remote Sensing,2010,14(5）:1004-1016.]   
[19］黄永璘,农民强,孙涵.基于FY-3A/MERSI的洪涝灾害遥感监 测初探[J].气象研究与应用,2009,30（2）：59-62.［HUANG Yonglin,NONG Minqiang,SUNHan.Flood disaster remote monitoringbased on FY-3A/MERSI data[J].Meteorological Research and Application,2009,30(2）:59-62.]   
[20］韩秀珍,郑伟,刘诚,等.基于MERSI和 MODIS 的太湖水体叶 绿素a含量反演[J].地理研究，2011,30(2）：291-300.［HAN Xiuzhen,ZHENGWei,LIU Cheng,etal.Estimation of chlorophylla using MERSI and MODIS images in Taihu Lake,China[J].Geographic Research,2011,30(2):291-300.]   
[21］陈鹏,张青,李倩.基于FY3A/MERSI影像的几种常用水体提 取方法的比较分析[J].干旱区地理，2015，38（4）：770-778. [CHEN Peng,ZHANG Qing,LI Qian. Comparative analysis of several commonly used water extraction method based on FY3A/ MERSI imagery[J].Arid Land Geography,2015,38（4）:770 - 778.]   
[22］冯锐,纪瑞鹏,武晋雯,等.FY3/MERSI和 EOS/MODIS 归一化 植被指数差异分析[J].中国农学通报，2010,26（19)：359- 362.[FENG Rui,JIRuipeng,WU Jinwen,etal.Analysis on differ

encebetween FY3/MERSI-NDVI and EOS/MODIS-NDVI[J].

Chinese Agricultural Science Bulletin,2010,26(19）:359-362.] [23］武鹏飞，胡列群，李贵才，等.基于棉田光谱的FY-3A/MERSI 与MODIS植被指数关系研究［J].沙漠与绿洲气象，2011，5 (4）:49-52.[WUPengfei,HULiequn,LIGuicai,etal.Relationshipbetween FY-3A/MERSI and MODIS vegetation indexesbased on cotton spectrum[J].Desert and Oasis Meteorology,2011,5 (4):49-52.]

[24］曹梅盛,李新，陈贤章，等.冰冻圈遥感［M].北京：科学出版 社,2006.[CAO Meisheng,LI Xin,CHEN Xianzhang,et al.Remote sensing of cryosphere[M].Beijing:Science Press,2006.] [25]HALL DK,RIGGSG A,SALOMONSONVV.MODIS snOW-cover products[J].Remote Sensing of Environment,2002,（83）:181- 194.

[26］陈丽萍，李忠勤，张慧，等.2001—2014年新疆阿尔泰地区积雪时空分布特征研究[J].干旱区资源与环境，2017，31（3）：152-157.［CHENLiping,LI Zhongqin,ZHANGHui,etal.Temporaland spatial distribution of snow cover in Altai region,Xinjiang from2001 to 2O14[J]. Journal of Arid Land Resources and Environ-ment,2017,31(3):152-157.]

[27］胡汝骥.中国天山自然地理[M].北京：中国环境科学出版社，2004:248-254.［HU Ruji.Physical geography of the TianshanMountains in China［M].Beijing：China Environmental SciencePress,2004:248 -254.]

[28］赵明洋,别强，何磊,等.基于去云处理的祁连山积雪覆盖遥感监 测研究[J].干旱区地理,2014,37(2）:325-332.[ZHAO Mingyang,BIE Qiang,HELei,et al.Estimating snow cover accuracy from MODIS and AMSR-E with cloud removal methodology in Qilian Mountains[J].AridLand Geography,2014,37(2) :325-332.]

# Comparison of the accuracy of normalized snow cover indices between FY-3D/MERSI-II and MODIS

CHEN Peng， WANG Yong， ZHANG Qing， LI Yue(Urumqi Meteorological Satelite Ground Station,Urumqi 83oO11,Xinjiang,China)

Abstract：In 2O17,China launched FY-3D,a next-generation meteorological satelite,into polar orbit.Oneof its core sensors is the Medium-Resolution Spectral Imager II（MERSI-II）that is capable of high-precision quantitative inversioofatmospheric,terrestrial,andoceanicparameters,includingmetricsofcloud,erosol,waterapor,land surface characteristics,and ocean color.We established thetrue snow cover extent of the middle Tianshan Mountains,Xinjiang,China with visual interpretationof high-resolution Landsat-8 images.We then used FY-3D/ MERSI-II data,captured during cloudless conditions in July and August 2O18,tocalculate the normalized snow cover index.Wecompared the accuracy of FY-3D/MERSI-II datacalculated by confusion matrix against MODIS daily snow product data. With an average overallsnow cover extraction accuracyof O.855,the FY-3D/MERSI-Il imagery outperformed MODIS that had an accuracy of 0.820.The average Kappa coeficient of FY-3D/MERSI-II（0.659) was also higher than that of MODIS(O.558).Overall,the accuracy of the snow cover area extracted from FY-3D/ MERSI-II data was higher than from MODIS,achieving a closer match to the high-resolution Landsat-8 images.

Key words:FY-3D/MERSI-II； MOD1OA1； NDSI； accuracy contrast analysis