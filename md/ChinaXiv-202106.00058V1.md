# AMSR-E土壤水分产品评价及在干旱监测中的应用

王静¹，方锋²，黄鹏程²，岳平¹，李江萍³，王大为²  
(1.中国气象局兰州干旱气象研究所甘肃省干旱气候变化与减灾重点实验室中国气象局干旱气候变化与减灾重点开放实验室,甘肃 兰州730020；2.兰州区域气候中心,甘肃 兰州730020;3.兰州大学大气科学学院，甘肃 兰州730020)

摘要：土壤水分在地表能量交换和气候变化中有重要作用。干旱为常见的自然灾害,土壤水分是反映干旱最直观的指标,利用微波遥感监测地表土壤水分具有明显优势,微波土壤水分产品也在干旱监测中具有重要作用,但由于地表下垫面的差异和反演算法的精度,使土壤水分产品的应用受到了限制,因此，本研究对广泛使用的AMSR-E（Advanced Microwave Scanning Radiometer-Earth Observing System)土壤水分产品在中国范围内的精度及在干旱监测中的作用进行评价。结果表明：AMSR-E能较好的反映站点不同深度的土壤水分情况，大多数站点存在极显著相关关系，但 $2 0 \ \mathrm { c m }$ 相关性低于 $1 0 \ \mathrm { c m }$ ，且高相关系数区域明显缩小;下垫面为白地的农试站观测的土壤水分和AMSR-E土壤水分产品之间的相关性显著高于种植作物下的农田区这2种数据的相关性;对于大多数下垫面类型,站点土壤水分和AMSR-E土壤水分之间存在明显的正相关关系，且达到极显著相关，对 $1 0 \ \mathrm { c m }$ 土壤水分观测，相关性最好的是种植高梁下观测的土壤水分，相关性达到了0.579，对 $2 0 \ \mathrm { c m }$ 土壤水分观测，相关性最好的是棉花下观测的土壤水分,相关性达到0.528。春季、夏季和秋季的相关性较高,而冬季相关性略低;在种植作物的情况下,东北、华南和西北地区,站点和AMSR-E土壤水分观测相关性较好,仅考虑白地的情况下,西北、西南和华中区域,这2种数据的相关性更高些;AMSR-E较农试站土壤水分取值范围宽，但不同区域AMSR-E土壤水分取值峰值不同,华北区域2种土壤水分观测分布和波动较为一致;AMSR-E基本能反映北方干旱和南方多雨引起的土壤水分差异趋势;大多数站点和大多数作物类型下， $1 0 \ \mathrm { c m }$ 站点土壤水分和AMSR-E土壤水分相关性较好的情况下， $2 0 \ \mathrm { c m }$ 也会有这样的表现。其次,AMSR-E土壤水分产品提取的土壤水分距平百分率与同期的降水距平百分率之间的相关性较好，尤其在西北地区和北方大部分区域更明显，AMSR-E土壤水分产品能较好的反映降水的波动和干旱的发生状况。

关键词：AMSR-E土壤水分产品；土壤水分；降水距平指数；作物类型

干旱是最为突出的极端自然现象，与其他灾害相比，干旱出现次数多、持续时间长、影响范围大，所造成的损失在所有的自然灾害中比重也最大，因此监测反映干旱状况的土壤水分，以及利用现有的先进技术手段有效监测土壤水分有重要意义。

土壤水分对粮食安全、人类健康和生态系统功能有直接影响，同时它还在气候系统以及干旱、洪涝等极端天气事件的发生发展中发挥着关键作用[1]但土壤水分是一个很难在大范围内、快速监测的地表参数，利用先进的遥感技术手段能够从空间对地表进行大尺度、长周期的观测，尤其是利用微波遥感监测地表土壤水分具有十分重要的作用。同其他传感器相比，微波遥感具有全天时、全天候、穿透性以及对地表粗糙度、地物几何形状、介电性质的敏感性、多波段多极化的散射特征等性质监测的独特优势，已成为利用遥感技术研究土壤水分的热点，也成为对地观测中十分重要的前沿领域。

微波监测土壤水分的原理，主要是土壤的介电常数随着土壤的含水量变化而变化，土壤介电常数是气体、水、干土等组分的介电常数的综合，当土壤中水分增加时，土壤的介电常数迅速增长因而由微波辐射计观测到的亮度温度也随之变化。所以，土壤水分是影响被动微波辐射测量的关键因子，基于这一原理，国内外专家围绕土壤湿度与亮度温度之间的关系进行了大量的理论研究及野外和航空遥感实验，并且发展了具有应用价值的多种土壤水分反演算法和产品。但是通过长期的对现有土壤水分产品的验证结果表明，反演的土壤水分产品精度，与实际土壤水分产品存在一定的偏差[2],这也影响了这些产品的广泛应用。这些偏差主要的原因有以下几个，首先，反演算法需要大量的土壤参数，但由于下垫面的复杂性，这些参数在全球尺度难以精确获取，如美国1980年实施的农业和资源航空遥感调查计划(AgRISTARS)专门通过一系列的野外航空遥感试验，定量研究了植被、粗糙度、观测角、土壤纹理结构、大气等因子对微波遥感反演土壤湿度的影响，并对该工作进行了综述[3]。其次，定点观测的土壤水分数据的水平和垂直分辨率同遥感数据是不同的。此外，由于土壤水分反演算法和亮温观测的误差，也会造成偏差。因此，在应用前，利用地表土壤水分观测数据对现有的微波土壤水分产品进行精度评价是十分必要的。

目前的土壤水分产品中，由于被动微波传感器覆盖范围广，实用意义更大。其中，AMSR-E(Ad-vanced Microwave Scanning Radiometer-Earth Observ-ingSystem)数据是应用最为广泛的数据。AMSR-E传感器搭载于对地观测卫星EOS-Aqua卫星上，于2002年发射升空，该辐射计为6.9\~89GHz范围的双极化、6频率、12通道的微波辐射计，其主要任务之一就是在全球尺度上提供土壤水分观测数据。

在过去十几年，对AMSR-E土壤水分产品进行验证已经得到很大关注。这些验证计划包括西欧、美国、韩国、印度和澳大利亚的验证试验。如Sahoo等[4利用美国佐治亚洲的小河流域的实地观测数据对AMSR-E土壤水分观测数据进行评价，并提出了一个单参数迭代参数拟合算法来改进当前的土壤水分反演算法。Gruhier等[5利用Mali发展的土壤水分网评价了不同的卫星产品。Draper等利用澳大利亚东南部和西班牙中部的12个地面观测站对反演的VUA-NASA产品进行了评价，得到的相关系数均大于0.80，据此认为，VUA-NASA产品同地面观测土壤水分数据有较好的一致性。Rudiger等比较了ISBA模型模拟的土壤水分数据和AMSR-E-LPRM产品之间的相关性，认为这2组数据之间具有较好的相关性，尤其是低纬度植被覆盖度较低的区域。Choi等[8]利用韩国地面监测数据对AMSR-E土壤水分产品进行验证,结果表明，当NDVI高于0.4时,AMSR-E土壤水分和地面观测的土壤水分有较好的一致性,这同其他研究者得出的植被密集情况下,AMSR-E土壤水分同地面观测土壤水分一致性较差的结论有所差异。Jackson等[9采用位于美国不同气候区的7a的定点观测数据评价了4种AM-SR-E算法,发现每一种算法在每一个点的表现都是不一样的。Chaurasia等[10]对AMSR-E土壤水分产品在印度区域的精度进行了评价。Brocca等[1]对AM-SR-E土壤水分产品在欧洲的精度进行了评价。Lei等[12]利用美国多部门建立的包括270个观测站的土壤水分观测网评价了不同时期的AMSR-E-LPRM土壤水分产品,认为不同时期获取的土壤水分精度同地表特征紧密相关。Kolassa等[13]基于神经网络算法,发展了新的AMSR-E土壤水分产品,并利用国际土壤水分网对该产品进行了评价，认为该产品能较好的捕捉到干旱期土壤水分变化。近几年，一些研究者也开展了AMSR-E土壤水分产品在中国范围内的精度评价，如陈洁[14]对AMSR-E土壤水分产品在中国西北地区的精度进行了评价。Zhang等[15]评价了NSIDC 和VUA-NASA2种AMSR-E土壤水分产品，认为NSIDC 数据不能捕捉土壤水分动态信号，而VUA-NASA产品则能够较好的监测中国北方地区的土壤水分状况。Wu等[16]利用锡林郭勒的土壤水分数据,对AMSR-E土壤水分产品进行验证,认为AMSR-E土壤水分产品在中国北方草地的监测精度较好。Qiu等[17]对AMSR-E土壤水分产品在中国北方平原应用的精度进行了评价。此外，由于土壤冻结会引起土壤介电常数发生显著变化,导致土壤水分反演算法不能准确估计冻结状况下的土壤水分[18],因此,近年来,在中国高寒区域进行的土壤水分产品精度评价,均考虑了土壤水分冻融问题。如Zeng等[9利用青藏高原3个土壤水分观测网，区分冻融期,对8种土壤水分产品进行了评价，认为NASA产品和JAXA产品均低估了土壤含水量，并且不能捕捉到土壤水分的动态变化，LPRM产品同地面观测一致性较好,但明显高估了土壤含水量,并总结了LPRM产品误差的原因。Chen等[2]充分考虑了空间代表性,利用青藏高原中部土壤水分观测网的多个站点的观测均值评价了AMSR-E土壤水分，认为4种AMSR-E产品均不能达到期望精度的要求，难以提供可信的土壤水分估计，并发现冻结期，土壤水分产品的偏差和误差都比较大，认为目前的反演算法在半干旱寒冷地区有较大的改进空间。$\mathrm { S u }$ 等[20]利用玛曲和那曲土壤水分观测网分别评价了冬季和雨季AMSR-E土壤水分产品，认为冬季AMSR-E土壤水分偏高,可信度较差。Zhang等[21]也利用青藏高原的3个观测网，评价了多种土壤水分产品，并估计了观测和产品之间空间尺度不匹配引起的不确定性，以及冻结期与非冻结期土壤水分产品和观测之间的一致性,并总结了不确定性的原因。Zhang等[22]利用黄河源区玛曲县多个土壤水分站点观测数据，评价了非冻结期3种AMSR-E土壤水分产品的精度，认为VUA土壤水分产品一致性最好,且空间分布与降水分布较为一致。席家驹等[23]利用非冻结期的多个站点土壤水分观测均值评价了3种AMSR-E土壤水分产品在青藏高原地区的适用性，以及不同植被覆盖和降水对产品精度的影响。李哲等[24]利用青藏高原玛曲和那曲观测网,评价了2种AMSR-E土壤水分产品，认为NASA产品低估了这2个地区的土壤湿度，VUA-NASA产品在玛曲地区表现良好,但在那曲地区精度较差。同时，AMSR-E产品除了利用地面观测数据进行验证外，还常被用于同陆面过程模式模拟结果进行比较，如李昂等[25]利用ECWMF和NECP再分析资料对AM-SR-E土壤湿度产品进行评价，认为这三种数据空间分布特征一致性较好,但AMSR-E土壤湿度在数值上明显偏小。

上述验证结果表明，由于卫星资料本身的限制，以及反演算法、植被覆盖影响等问题，使得卫星数据产品包含了很大的不确定性，以至于利用卫星遥感技术精确反演全球土壤水分成为了一个巨大的挑战，所以对卫星产品进行精度评价，并辨识不确定性因素，以期为产品的应用和反演算法的改进提供科学依据是十分有必要的。但目前，AMSR-E在中国地区的验证研究，主要针对青藏高原区域，或者仅采用某一年份数据进行验证，具有局限性，因此有必要利用更大范围的、更长时间序列、更多农田区的地面观测数据对该产品进行全面的验证和评价，以便于为该产品在农业生产中的应用和干旱气象灾害减灾提供有益的参考。

本文针对以上目标，利用2种地面观测数据，即中国区域内已有的农业气象试验站常规土壤相对湿度观测资料和甘肃省土壤水分自动站观测数据，对AMSR-E土壤水分产品进行评价，分析AMSR-E土壤水分产品在中国范围内多种下垫面类型下的精度，以期为土壤水分产品的应用提供一些依据。另外，为了辨识土壤水分产品在干旱监测中的作用，在此，我们也获取了同期降水数据，并计算了反映干旱最直接的指标一一降水距平百分率，并同土壤水分产品计算的月距平指数进行比较，判断AM-SR-E土壤水分产品在干旱监测中的适用性，以期为土壤水分产品监测干旱事件提供一些参考[26]

# 1数据材料与方法

# 1.1AMSR-E数据及处理

1.1.1AMSR-E 数据AMSR-E数据从网站 http://www.falw.vu/\~jeur/lprm/下载，包括升轨和降轨数据，时间为2002年6月19日至2011年10月3日，空间分辨率为 $0 . 2 5 ^ { \circ }$ ,数据以netCDF格式保存。土壤水分反演算法采用LandParameterRetrievalModel(LPRM)模型，LPRM模型是一个前向辐射传输模型，用于反演地表土壤水分和植被光学厚度。

1.1.2AMSR-E数据处理首先将已有的所有AM-SR-E数据的\*.nc格式转换为\*.tiff格式，根据土壤水分观测点经纬度，提取同站点对应的AMSR-E微波土壤水分数据。根据陈洁[14]的研究，升降轨数据在表征土壤水分特征上有很好的一致性，因此对升降轨数据进行拼接，如果该日升降轨同时有数据，则当日的微波土壤水分数据为升降轨数据的平均值，如果仅升轨或降轨有数据，则仅采用升轨或者降轨的数据做为当日的微波土壤水分数据。

# 1.2土壤水分地面观测资料及处理

1.2.1土壤水分地面观测资料土壤水分地面观测数据采用中国气象局建立的农业气象站网观测的土壤湿度数据，该数据下载自中国气象局数据共享网（http://cdc.cma.gov.cn/home.do）的中国农作物生长发育和农田土壤湿度旬值数据集，该数据集包含了1991年9月至2012年12月的农作物生长发育状况报告，具体数据层包括：旬作物名称、发育期名称、发育期日期、发育程度、发育期距平、植株高度、生长状况、植株密度、到本旬末积温、积温距平、干土层厚度，以及 $1 0 \ \mathrm { c m } \cdot 2 0 \ \mathrm { c m } \ . 5 0 \ \mathrm { c m } \ . 7 0 \ \mathrm { c m }$ 和100cm土壤相对湿度。最终共下载从1991年9月至2012年7月31日共包含778个站点的386742条数据记录，并按照站点重新生成文件。

农业气象站观测的土壤水分数据为土壤相对湿度 $( \% )$ ,是土壤含水量与田间持水量的百分比，说明土壤实际含水量的饱和程度。土壤相对湿度每月观测3次，分别为每旬逢8观测。根据中国气象局农业试验站的观测规范规定，土壤水分只在非冻结期进行观测，具体观测期根据各站点冻融日期不同，而有所差异。土壤湿度观测采用烘干法，在固定地段和非固定地段用土钻取土，固定地段为农田或气象观测场周围自然植被覆盖的土壤，非固定地段为作物生长季农田，对不同作物的数据状况进行了分类。下垫面为白地、春玉米、夏玉米、其他作物类型的数据量较为丰富，而部分作物不仅数据量较少，且观测地也较为集中。其中春玉米数据最为丰富，观测区域最广泛，171个农试站点的土壤水分观测中均包含春玉米。

1.2.2土壤湿度地面观测资料处理由于地面观测的土壤湿度是土壤相对湿度，而AMSR-E反演的土壤水分产品是体积含水量，需将观测站土壤相对湿度数据转换为体积含水量，主要采用田间持水量、容重等土壤理化特征数据进行转换，具体转换公式如下：

$$
\theta _ { \phantom { } _ { v } } = q \times f c \times s c
$$

式中： $\theta _ { \phantom { } _ { v } }$ 为体积含水量 $( \% ) ; q$ 为土壤相对湿度$( \% )$ ; $f \bar { c }$ 为土壤田间持水量 $( \% )$ ： $s c$ 为土壤容重( $\mathbf { \_ g }$ $\mathrm { c m } ^ { - 3 }$ ）；

在此根据各个站点的土壤相对湿度，计算相应的体积含水量。其中容重和田间持水量数据，均来源于 Harmonized World Soil Database (HWSD)土壤质地数据集(http://www.fao.org/nr/land/soils/harmonized-world-soil-database/ download-data-only/zh/)[27],该数据集由国际粮农组织发布，包含了土壤田间持水量、土壤容重、土壤颗粒组成等数据

该数据集中国区域的土壤参数数据主要来自于中国第二次土壤普查数据。土壤类型已参考HWSD中的土壤单位，转换成了USDA的土壤分类，以便于同土壤属性数据集相关联。土壤物化和养分属性，部分是从中国的7292个剖面中获取，部分是基于遍布于全世界的9607个土壤剖面中获取，具有较高的可信度，已经广泛使用在许多研究中[28]通过已有的甘肃省的田间持水量和容重情况，对HWSD数据库的土壤质地数据进行验证，结果表明该数据库的数据质量较为可靠，因此，被用于提取每一站点的土壤质地数据，并应用于后续的全国土壤相对湿度资料转换为体积含水量资料的计算中。

# 1.3降水数据

降水是主要的土壤水分驱动因子，尤其是近地表土壤含水量同降水之间具有强烈的相关性。降水量也是反映干旱的最主要的指标，在此主要采用降水距平百分率来表征干旱的程度。日降水数据从中国气象局数据共享网下载，全国共778个站点，对数据质量分析后，选取遍布在全国的424个气象站点，2002年6月至2011年10月的日降水数据进行处理,生成逐月降水距平百分率 $( P A ) ^ { [ 2 9 ] }$ ,并提取同降水站点对应的AMSR-E土壤水分数据，计算各站点逐月AMSR-E土壤水分平均值，继而得到各站点逐月AMSR-E土壤水分距平百分率 $( S A )$ ，用于评价土壤水分产品在干旱监测中的应用效果。

$$
P A = \frac { P - \bar { P } } { \bar { P } }
$$

式中： $P A$ 为月降水量距平百分率 $( \% )  \} ; P$ 为月降水量 $( \operatorname* { m m } )$ ； $\bar { P }$ 为计算月份同期气候平均降水量$\left( \mathrm { m m } \right)$ ）

$$
S A = \frac { S _ { w } - \overline { { S _ { w } } } } { \overline { { S _ { w } } } }
$$

式中： $S A$ 为月土壤水分距平百分率 $( \% ) ; S _ { w }$ 为月土壤水分平均值 $( \% ) ; { \overline { { S _ { w } } } }$ 为计算月份同期平均土壤含水量 $( \% )$ 。

# 1.4土壤水分自动站数据

搜集甘肃省经过标定验收的20个自动站土壤水分数据，自动站土壤水分采用自动土壤水分观测仪观测，每 $1 0 \ \mathrm { c m }$ 一层，共20层土壤水分，每小时记录1次。自动站采用的观测仪器、观测原理、安装深度、安装位置、观测时间段均保持一致，为数据的可比性提供了高质量的、一致性强的地面观测数据。数据时间范围为2010年11月11日至2011年12月31日。

为了同AMSR-E土壤水分产品和农试站土壤水分观测进行比较，首先，对自动站每日 $2 4 \mathrm { ~ h ~ }$ 的纪录进行平均，获得自动站逐层土壤水分日均值；其次，基于地温资料，根据刘广岳等[30的冻结日期界定方法，即活动层起始融化时间和起始冻结时间分别以地表以下 $5 \mathrm { c m }$ 深度处日平均温度连续5d大于 $0 \%$ 和小于 $0 \mathrm { { ^ { \circ } C } }$ 为标准确定，获得各自动站2010年和2011年起始融化和起始冻结日期，继而对自动站数据进行整理，在此仅采用非冻结期 $1 0 \ \mathrm { c m }$ 土壤水分数据，同AMSR-E土壤水分进行对比。

# 2结果与分析

# 2.1AMSR-E土壤水分产品同农试站土壤水分观测数据的对比

2.1.1AMSR-E土壤水分产品同农试站 $1 0 \ \mathrm { c m }$ 土壤水分观测数据的相关性鉴于微波数据监测土壤水分的特性，在此首先比较了农试站观测的 $1 0 \ \mathrm { c m }$ 土壤含水量和AMSR-E土壤水分产品的相关性，相关性在全国的分布情况及相关系数在不同取值范围的分布情况如图1和图2所示。从图1可以看出，AMSR-E反演的土壤水分同大多数站点观测的10cm土壤水分存在正相关关系，尤其是仅考虑白地下垫面的情况，这种正相关关系更明显些，各站点的相关性也更高些。这2种数据相关性高的区域主要分布在甘肃东部、陕西中部、山西、湖南和福建，而相关性差的地区主要分布在陕西南部、湖北、云南、青海地区。

从相关系数的分布频率可以看出(图2)，如果不区分白地和种植作物的情况，AMSR-E土壤水分和农试站 $1 0 \ \mathrm { c m }$ 土壤水分观测数据之间的相关系数主要分布在0.4以下，超过0.5的站点仅占 $10 \%$ 左右。如果仅考虑监测白地状况下的土壤水分，这2种数据的相关性能略好些，相关系数超过0.5的站点明显增多，这也间接说明植被对微波监测土壤水分存在影响。

此外，分析了种植不同作物情况下， $1 0 \ \mathrm { c m }$ 站点土壤水分和AMSR-E土壤水分产品之间的相关性(表1)。从表中可以看出，大多数作物下垫面类型下，站点土壤水分和AMSR-E土壤水分之间存在明显的正相关关系，虽然多数相关系数不高，但均达到了极显著水平，其中相关性最好的是种植高梁下观测的土壤水分，相关系数达到了0.579。但也有部分作物类型下这2种数据相关性不高，如大麦、新植蔗、甘蔗、芝麻，相关性并不显著，甚至部分作物类型下，这2种数据为负相关，如种植的元麦、向日葵、宿根蔗、甜菜和长绒棉下观测的土壤水分。这说明AMSR-E能较好的监测多数作物下的土壤水分动态变化，但由于作物下垫面类型过于复杂，作物从株高、含水量、植株化学成分等都存在极大差异，AM-SR-E等被动微波技术监测农田土壤水分仍需不断改进，尤其是针对不同的作物种植区建立不同的反演算法和土壤水分监测技术。

另外，由于我国大多数地区年降水分布不均，存在明显的夏季多雨，冬季少雨的年内变化，也直接引起土壤水分显著的季节变化。因此，在此选择下垫面为白地的农试站土壤水分观测数据，分析不同季节，AMSR-E监测土壤水分的可靠性(表2)，其中春季为3—5月，夏季为6—8月，秋季为9—11月，冬季为12—2月。从表2可以看出，各季节AMSR-E土壤水分产品和农试站 $1 0 \mathrm { c m }$ 土壤水分观测数据都达到了极显著相关。其中，春季、夏季和秋季的相

![](images/f6e49c79f92060b7c948d3223a757cf1517d74df03afe431232e1f2cede7cce5.jpg)  
注：审图号GS(2021)701号；台湾、海南资料暂缺。下同。  
图1农试站 $1 0 \mathrm { c m }$ 土壤水分和AMSR-E土壤水分的相关性

Fig.1 Relationship of soil moisture between AMSR-E and $1 0 \mathrm { c m }$ observation of agricultural meteorological station

![](images/ca8ff8d4a169aa38c0e929f3975f181047e9bd680d62e8953bd598e36d15768e.jpg)  
图2农试站 $1 0 \mathrm { c m }$ 土壤水分和AMSR-E土壤水分相关系数频率分布 Fig.2 Frequency distribution of soil moisture correlation coefcients between AMSR-E and $1 0 \mathrm { c m }$ observation of agricultural meteorological station

# 表1种植不同作物下的 $\mathbf { 1 0 ~ c m }$ 站点土壤水分和AMSR-E土壤水分的相关性

Tab.1 Relationship of soil moisture between AMSR-E and $\mathbf { 1 0 ~ c m }$ observation of agricultural meteorological station under different crop region   

<html><body><table><tr><td></td><td>一季稻</td><td>元麦</td><td>麻类</td><td>冬小麦</td><td>向日葵</td><td>夏玉米</td><td>大豆</td><td>大麦</td><td>套玉米</td><td>宿根蔗</td><td>马铃薯</td></tr><tr><td>样本量</td><td>1401</td><td>3</td><td>103</td><td>26945</td><td>54</td><td>6577</td><td>3690</td><td>21</td><td>798</td><td>628</td><td>2085</td></tr><tr><td>相关系数</td><td>0.193**</td><td>-0.167</td><td>0.456**</td><td>0.224**</td><td>-0.248</td><td>0.295**</td><td>0.247**</td><td>0.209</td><td>0.249**</td><td>-0.138**</td><td>0.492**</td></tr><tr><td></td><td>新植蔗</td><td>早稻</td><td>春小麦</td><td>春玉米</td><td>晚稻</td><td>普通棉</td><td>棉花</td><td>油菜</td><td>烟草</td><td>牧草</td><td>高梁</td></tr><tr><td>样本量</td><td>229</td><td>407</td><td>4722</td><td>11683</td><td>361</td><td>5523</td><td>116</td><td>2395</td><td>166</td><td>4414</td><td>312</td></tr><tr><td>相关系数</td><td>0.086</td><td>0.200**</td><td>0.191**</td><td>0.328**</td><td>0.334**</td><td>0.363**</td><td>0.559**</td><td>0.302**</td><td>0.315**</td><td>0.523**</td><td>0.579**</td></tr><tr><td></td><td>甘蔗</td><td>甘薯</td><td>甜菜</td><td>白地</td><td>芝麻</td><td>花生</td><td>莜麦</td><td>谷子</td><td>长绒棉</td><td>青稞</td><td>其他作物</td></tr><tr><td>样本量</td><td>25</td><td>848</td><td>334</td><td>37808</td><td>38</td><td>759</td><td>57</td><td>760</td><td>5</td><td>523</td><td>4470</td></tr><tr><td>相关系数</td><td>0.322</td><td>0.300**</td><td>-0.161**</td><td>0.444**</td><td>0.299</td><td>0.171**</td><td>0.305**</td><td>0.391**</td><td>-0.352</td><td>0.235**</td><td>0.260**</td></tr></table></body></html>

注：\*\*表示在0.01水平(双侧)上显著相关。下同。

# 表2不同季节AMSR-E土壤水分和农试站观测土壤水分的相关性

Tab.2 Relationship of soil moisture between AMSR-E and agricultural meteorological station in different seasons   

<html><body><table><tr><td></td><td>春季</td><td>夏季</td><td>秋季</td><td>冬季</td></tr><tr><td>样本量</td><td>12193</td><td>9032</td><td>13800</td><td>2783</td></tr><tr><td>相关系数</td><td>0.462**</td><td>0.431**</td><td>0.440**</td><td>0.305**</td></tr></table></body></html>

关性较高，而冬季相关性略低。这说明AMSR-E可以用于监测全年的土壤水分动态变化，但冬季的可靠性略低。

2.1.2 AMSR-E土壤水分产品同农试站 $2 0 ~ \mathrm { c m }$ 土壤水分观测数据的相关性为了探索AMSR-E数据对较深层土壤水分的监测情况，以便于为卫星遥感监测土壤熵情，为农业干旱监测预警提供科学依据，在此，同时提取了农试站观测的 $2 0 \mathrm { c m }$ 土壤含水量，同AMSR-E土壤水分产品进行对比，评价结果如图3和图4所示。从图3可以看出，AMSR-E土壤水分资料同农试站观测的 $2 0 \mathrm { c m }$ 土壤水分也存在明显的正相关关系，但大多数站点的相关系数不超过0.4，仅在陕西中北部、山西、湖南和福建省份相关性能达到0.5以上，相关性高的区域同 $1 0 \mathrm { c m }$ 分析结果相似，并且也是不考虑种植作物区的情况下，AMSR-E土壤水分产品和农试站观测的 $2 0 \ \mathrm { c m }$ 土壤含水量相关性能更好些，相关系数大于0.4的比例较考虑作物类型的情况高。但同图1对比可以发现，相关系数高的区域明显缩小，2种数据的相关性差于10cm，这说明AMSR-E可以反映深层土壤水分动态变化趋势，但难以获取准确的深层土壤含水量结果。

分析了种植不同作物情况下， $2 0 ~ \mathrm { c m }$ 站点土壤水分和AMSR-E土壤水分产品之间的相关性，其表现同 $1 0 \ \mathrm { c m }$ 基本一致，大多数作物类型下，AMSR-E土壤水分和站点土壤水分能达到极显著相关，但大部分作物类型的相关系数都略低于 $1 0 \mathrm { c m }$ （表3）。

2.1.3不同区域AMSR-E土壤水分产品同农试站土壤水分观测数据的相关性由于中国地域辽阔、气候复杂多样，土壤水分区域差异较大，作物对土壤水分变化的耐受性不同，因此，在此分析了不同区域AMSR-E土壤水分和农试站土壤水分的相关性。

![](images/5bdbb77c2583b93f06ea47873523930db3e597090abbddfcbf45ed46bc3ba6f7.jpg)  
图3农试站 $2 0 \mathrm { c m }$ 土壤水分和AMSR-E土壤水分的相关性

Fig.3Relationship of soil moisture between AMSR-E and $2 0 \mathrm { c m }$ observation of agricultural meteorological statior根据气候条件和地理环境差异，在此将全国分为七个区域，即东北、华北、华东、华中、华南、西南和西北，其中东北包括辽宁、吉林、黑龙江，华北包括北京、天津、河北、山西、内蒙古，华东包括上海、江苏、浙江、安徽、福建、山东，华中包括江西、河南、湖北、湖南，华南包括广东、广西、海南，西南包括四川、贵州、云南、西藏，重庆，西北包括陕西、甘肃、宁夏、青海、新疆。7个区域AMSR-E土壤水分同农试站观测的 $1 0 \ \mathrm { c m }$ 土壤水分之间的相关性如表4所示。从表上可以看出，各区域AMSR-E土壤水分和农试站观测的 $1 0 \ \mathrm { c m }$ 土壤水分之间均达到极显著相关关系，在包含作物类型的情况下，东北、华南和西北地区，这2种数据的相关性略好些，而如果仅考虑白地的情况下，西北、西南和华中的相关性更高些。可以看出，种植作物对华南地区微波监测土壤水分影响较大。

![](images/509e569c49447560f91feb8b2aecc2ec81c4223ef6f7307676e5410220aee3ca.jpg)  
图4农试站 $2 0 \mathrm { c m }$ 土壤水分和AMSR-E土壤水分相关系数频率分布 Fig.4 Frequency distribution of soil moisture correlation coefficient between AMSR-E and $2 0 \mathrm { c m }$ observation of agricultural meteorological station

Tab.3 Relationship of soil moisture between AMSR-E and $2 0 ~ \mathrm { c m }$ observationof agricultural meteorological station under different crop regions   

<html><body><table><tr><td></td><td>一季稻</td><td>元麦</td><td>麻类</td><td>冬小麦</td><td>向日葵</td><td>夏玉米</td><td>大豆</td><td>大麦</td><td>套玉米</td><td>宿根蔗</td><td>马铃薯</td></tr><tr><td>样本量</td><td>1374</td><td>3</td><td>103</td><td>26715</td><td>54</td><td>6538</td><td>3690</td><td>18</td><td>787</td><td>627</td><td>2054</td></tr><tr><td>相关系数</td><td>0.151**</td><td>-0.305</td><td>0.384**</td><td>0.245**</td><td>-0.338*</td><td>0.298**</td><td>0.233**</td><td>0.042</td><td>0.261**</td><td>-0.185**</td><td>0.502**</td></tr><tr><td></td><td>新植蔗</td><td>早稻</td><td>春小麦</td><td>春玉米</td><td>晚稻</td><td>普通棉</td><td>棉花</td><td>油菜</td><td>烟草</td><td>牧草</td><td>高梁</td></tr><tr><td>样本量</td><td>228</td><td>332</td><td>4690</td><td>11643</td><td>364</td><td>5476</td><td>114</td><td>2386</td><td>165</td><td>4399</td><td>309</td></tr><tr><td>相关系数</td><td>0.066</td><td>0.170**</td><td>0.147**</td><td>0.314**</td><td>0.129*</td><td>0.332**</td><td>0.528**</td><td>0.287**</td><td>0.384**</td><td>0.513**</td><td>0.513**</td></tr><tr><td></td><td>甘蔗</td><td>甘薯</td><td>甜菜</td><td>白地</td><td>芝麻</td><td>花生</td><td>莜麦</td><td>谷子</td><td>长绒棉</td><td>青稞</td><td>其他作物</td></tr><tr><td>样本量</td><td>25</td><td>844</td><td>334</td><td>37560</td><td>38</td><td>765</td><td>57</td><td>761</td><td>5</td><td>522</td><td>4434</td></tr><tr><td>相关系数</td><td>0.462**</td><td>0.280**</td><td>0.107</td><td>0.433**</td><td>0.204</td><td>0.145**</td><td>0.251</td><td>0.374**</td><td>-0.348</td><td>0.153**</td><td>0.234**</td></tr></table></body></html>

注：\*表示在0.05水平(双侧)上显著相关;\*\*表示在0.01水平(双侧)上显著相关。下同。

此外，提取了不同区域AMSR-E和农试站土壤水分的分布频率，用于分析不同气候背景和地理环境条件下，AMSR-E获取的土壤水分能否和站点土壤水分的变化较为一致，结果如图5所示。从图上可以看出，AMSR-E土壤水分取值较宽，但不同区域土壤水分取值的峰值不同，如东北、华中、华东土壤水分在 $4 0 \%$ 左右的频率最高，西南和华南土壤水分在 $5 0 \%$ 的频率最高，而华北和西北土壤水分则在$3 0 \%$ 左右的频率最高。其次，西北和华北土壤含水量主要分布在 $3 0 \%$ 以下，西南和华南土壤含水量则主要分布在 $4 0 \%$ 以上。AMSR-E基本能反映北方干旱和南方多雨引起的北方土壤水分较低，南方土壤水分较高的趋势。此外，相较于其他区域，AMSR-E探测的华北土壤水分主要分布在 $2 0 \% { \sim } 4 0 \%$ ,华东土壤水分分布在 $30 \% { \sim } 5 0 \%$ ,这样变化幅度为 $2 0 \%$ 的较窄的范围，而其他5个区域，AMSR-E监测的土壤水分分布较宽，在 $30 \% { \sim } 4 0 \%$ 的波动幅度间变化。相较于AMSR-E土壤水分，农试站土壤水分取值范围较窄。东北、华中、华东和西南农试站土壤水分主要在 $30 \% { \sim } 4 0 \%$ ,波动幅度为 $1 0 \%$ 的范围内变化，西北和华北土壤水分则在 $2 0 \% { \sim } 4 0 \%$ ，波动幅度为 $2 0 \%$ 的范围内变化，华南土壤水分取值在 $30 \% { \sim } 5 0 \%$ ，波动幅度为 $2 0 \%$ 的范围内变化。总体来看，华北区域，AMSR-E和农试站土壤水分分布和波动较为一致。仅考虑白地的情况下，其规律和多种作物类型下监测的土壤水分分布区间和波动幅度相似。

2.1.4AMSR-E和农试站 $1 0 \mathrm { c m }$ 和 $2 0 \ \mathrm { c m }$ 土壤水分精度评价的相关性最后分析了农试站各站点利用

表3种植不同作物下的 $2 0 \ \mathrm { c m }$ 站点土壤水分和AMSR-E土壤水分的相关性  
表4不同区域 $\mathbf { 1 0 ~ c m }$ 站点土壤水分和AMSR-E土壤水分的相关性  
Tab.4 Relationship of soil moisture between AMSR-E and $1 0 \mathrm { { c m } }$ observation of agricultural meteorological station in different regions   

<html><body><table><tr><td></td><td></td><td>东北</td><td>华北</td><td>华东</td><td>华南</td><td>华中</td><td>西北</td><td>西南</td></tr><tr><td>多种作物类型</td><td>样本量</td><td>15755</td><td>36325</td><td>10512</td><td>12347</td><td>2860</td><td>28781</td><td>11982</td></tr><tr><td></td><td>相关系数</td><td>0.289**</td><td>0.207**</td><td>0.065**</td><td>0.289**</td><td>0.128**</td><td>0.280**</td><td>0.180**</td></tr><tr><td>白地</td><td>样本量</td><td>7319</td><td>14609</td><td>1805</td><td>766</td><td>2862</td><td>8082</td><td>2365</td></tr><tr><td></td><td>相关系数</td><td>0.307**</td><td>0.255**</td><td>0.317**</td><td>0.163**</td><td>0.337**</td><td>0.449**</td><td>0.354**</td></tr></table></body></html>

60 (a1）东北（多种 60 (a2)东北(白地) 60(b1)华中（多种 60 (b2)华中(白地) 作物类型) 作物类型)   
40 40 %40 %40   
/率新 率 /率新 /零新 频 20 20 20 20 o Ln n oLl m 0Lll lnal.- 0L . 10305070%130507000 103050701030507090 10305070%0103050700 10305070001030507000 土壤水分/% 土壤水分/% 土壤水分/% 土壤水分/% 60 (c1)华北（多种 60 (c2)华北(白地) 60 (d1)西北（多种 60 (d2)西北(白地) 作物类型) 作物类型)   
%40 40 40 40   
6/率新 /率 6/率新 /率新 20 20 20 20 ohin ohn 1 onnn 0n 10305070901030507090 10305070901030507090 1030507000103050709 10305070103050700 土壤水分/% 土壤水分/% 土壤水分/% 土壤水分/% 60 (e1)华东(多种 60 (e2)华东(白地) 60 (f1)西南(多种 60 (f2)西南(白地) 作物类型) 作物类型)   
0 40 0%40 40 6/率新 南 20 20 频 20 ob n 0L Jgn 0 0n 103050701030507000 103050700103050700 103050701030507000 10305070013050700 土壤水分/% 土壤水分/% 土壤水分/% 土壤水分/% 60 (g1)华南(多种 60 (g2)华南(白地) 作物类型)   
40 40 □AMSR-E农试站 南 频 20 20 oLn 0L 10305070901030507090 1030507000103050700 土壤水分/% 土壤水分/%

Fig.5Distribution frequency ofsoil moisture ofAMSR-Eand agricultural meteorological station in diferent regic

$1 0 \ \mathrm { c m }$ 土壤水分观测数据评价AMSR-E土壤水分产品的结果和利用 $2 0 ~ \mathrm { c m }$ 评价的结果之间的关联性（图6)，以及不同区域(表5）不同作物下垫面情况下(表6)，这2个深度评价结果的关联性。从图6可以看出，总体来说,2组相关系数基本分布在了1：1线上，两者关联度很高、相关性很好，即 $1 0 \ \mathrm { c m }$ 站点土壤水分和AMSR-E土壤水分相关性较好的情况下， $2 0 \ \mathrm { c m }$ 也会有这样的表现，其相关系数为0.863，达到了极显著相关水平。但从建立的回归方程来看， $R _ { 2 0 \mathrm { \ c m } } { = } 0 . 8 3 8 R _ { \mathrm { 1 0 \ c m } }$ $2 0 ~ \mathrm { c m }$ 的站点卫星相关性明显低于 $1 0 \mathrm { c m }$ 的相关性，仅考虑白地情况，也是这种规律，且这种趋势更明显，其回归方程斜率为0.776，低于多种作物类型下获得的回归曲线斜率。从分区域来看，2个深度土壤水分产品精度评价的相关性也很好，均达到极显著水平，大多数区域相关系数超过了0.8，但存在区域差异，如华东、华中和西北区域，2个深度评价结果的关联性超过其他区域，而西南和华北区域，相关性略差些。此外，从不同作物类型下垫面，2个深度土壤水分产品评价结果的关联度可以看出，大多数作物类型下，2个评价结果相关性达到了极显著水平，尤其是新植蔗、普通棉、甘蔗、芝麻、花生、青稞和高梁，相关系数达到了0.95以上，说明这些作物种植区， $1 0 \ \mathrm { c m }$ 站点土壤水分和AMSR-E土壤水分相关性较好时， $2 0 \ \mathrm { c m }$ 的相关性也

(a)多种作物类型 (b)东北(多种作物类型) (c)白地 (d)东北(白地)0.8 1. 1.0 1.00. 20 0. 数 2 0.5 0 0.5.0.2 山 0.2 Q 0.8-0400.8-0.8 0.4 0.8 0.8-0.402 0.4 0.8 -0.804 0.4. 0.80.4 -0.4 0 ·-0.5-0.6 y(20 cm)-0.838x(10 cm) -0.6 y(20.cm)=0.7652x(10cm) y(20cm)=0.776x(10cm） y(20 cm)=0.7295x(10 cm)-0.8 R²=0.774 -0.8 R²=0.6954 R²=0.544 R²=0.715-1.0 1.0 -1.0 -1.010 cm相关系数 10 cm相关系数 10cm相关系数 10cm相关系数(e)华北(多种作物类型) (f)华东(多种作物类型) (g)华北(白地) (h)华东(白地)1.8 1.8 1.0 1.0  
0 0.6 00 0. 20 0.5 0.5 出0.2 0.2 茶0.8-0.42 0.40.8 -0.8-0.42 00.40.8 0.8-040040.8 -0.8-0.4 0 0.40.8-0.4 0.4 > -0.5 20 -0.50 8 y(20cm)=0.8882x(10 0R00 y0 em=-0.80650R²=0.8062-1.0 -1.010 cm相关系数 10 cm相关系数 10cm相关系数 10 cm相关系数(i)华中(多种作物类型) (i)华南(多种作物类型) (k)华中(白地) (l)华南(白地)1.0 1.0 1.0 1.00.8 0.8 0.8 0.8  
0 0802 0. 海 X 0.6 1 数 0. 0.2 0 08008 0.0.8 0.8-0.402 9 0.8 -0.8-002 0 0.40.80 20 0-1.0 1.0 1.0 -1.010cm相关系数 10 cm相关系数 10 cm相关系数 10cm相关系数(m)西南(多种作物类型) (n)西北(多种作物类型) (o)西南(白地) (p)西北(白地)1.0 1.0 1.0 1.00.8 0.8  
2 0. 20 0.6 1 2 0.5 茶 2 0.5.0.2. 0.2-0.8 042 中 0 0.4 0.8 080004 0.8 -0.8-0.4 0 0 0.4 0.8 -0.8 -0.4 0 0.4.0.8.4 ·-0.5 -0.5-0.8 -0.6 y(20 cm)=0.8234x(10 cm) R²=0.5155 -0.6 -0.81 y(20cm)=0.8298x(10.cm) R²=0.8498 1.0 (20cm=0.5406x(10.m)） R²=0.1127 -1.0 y(20cm)=0.7984x(10 R²=0.720310cm相关系数 10 cm相关系数 10cm相关系数 10cm相关系数

表5不同区域 $\mathbf { 1 0 ~ c m }$ 和 $2 0 ~ \mathrm { c m }$ 观测站点土壤水分和AMSR-E土壤水分相关系数的相关性 Tab.5 Region features for relationship of correlation coefficients of $\mathbf { 1 0 ~ c m }$ and $2 0 \ \mathrm { c m }$ between AMSR-E and agricultural meteorological station   

<html><body><table><tr><td></td><td></td><td>全国</td><td>东北</td><td>华北</td><td>华东</td><td>华中</td><td>华南</td><td>西南</td><td>西北</td></tr><tr><td rowspan="2">多种作物类型</td><td>相关系数</td><td>0.863**</td><td>0.838**</td><td>0.849**</td><td>0.899**</td><td>0.930**</td><td>0.692**</td><td>0.732**</td><td>0.924**</td></tr><tr><td>样本数</td><td>629</td><td>80</td><td>180</td><td>64</td><td>70</td><td>23</td><td>75</td><td>134</td></tr><tr><td rowspan="2">白地</td><td>相关系数</td><td>0.738**</td><td>0.863**</td><td>0.606**</td><td>0.906**</td><td>0.910**</td><td>0.828**</td><td>0.377*</td><td>0.849**</td></tr><tr><td>样本数</td><td>476</td><td>75</td><td>153</td><td>43</td><td>45</td><td>16</td><td>35</td><td>106</td></tr></table></body></html>

# 表6不同作物类型下 $\mathbf { 1 0 ~ c m }$ 和 $2 0 ~ \mathrm { c m }$ 观测的站点土壤水分和AMSR-E土壤水分相关系数的相关性

Tab.6Relationship of correlation coefficients of $\mathbf { 1 0 ~ c m }$ and $2 0 ~ \mathrm { c m }$ between AMSR-E and agricultural meteorological station in different crop regions   

<html><body><table><tr><td></td><td>一季稻</td><td>其他作物</td><td>冬小麦</td><td>向日葵</td><td>夏玉米</td><td>大豆</td><td>套玉米</td><td>宿根蔗</td><td>新植蔗</td><td>早稻</td></tr><tr><td rowspan="2">相关系数 样本数</td><td>0.768**</td><td>0.668**</td><td>0.716**</td><td>0.356</td><td>0.884**</td><td>0.727**</td><td>0.939**</td><td>0.928*</td><td>0.991**</td><td>0.046</td></tr><tr><td>46</td><td>66</td><td>248</td><td>4</td><td>128</td><td>65</td><td>16</td><td>5</td><td>4</td><td>15</td></tr><tr><td></td><td>春小麦</td><td>春玉米</td><td>晚稻</td><td>普通棉</td><td>棉花</td><td>油菜</td><td>烟草</td><td>牧草</td><td>甘蔗</td><td>甘薯</td></tr><tr><td>相关系数 样本数</td><td>0.891**</td><td>0.917**</td><td>0.694**</td><td>0.974**</td><td>0.949**</td><td>0.736**</td><td>0.149</td><td>0.919**</td><td>0.989**</td><td>-0.005</td></tr><tr><td rowspan="2"></td><td>70</td><td>164</td><td>30</td><td>64</td><td>29</td><td>56</td><td>6</td><td>44</td><td>5</td><td>18</td></tr><tr><td>甜菜</td><td>芝麻</td><td>花生</td><td>谷子</td><td>青稞</td><td>马铃薯</td><td>高梁</td><td>麻类</td><td></td><td></td></tr><tr><td>相关系数 样本数</td><td>-0.919 4</td><td>0.997** 3</td><td>0.961** 25</td><td>0.897** 14</td><td>0.972**</td><td>0.870**</td><td>0.966**</td><td>0.760</td><td></td><td></td></tr></table></body></html>

很好，AMSR-E能反映这些种植区不同层次的土壤水分波动。而向日葵、早稻、烟草、甘薯区域相关性较差，甚至负相关，说明这些作物种植区， $1 0 \ \mathrm { c m }$ 站点土壤水分和AMSR-E土壤水分相关性较好时，20cm的相关性不一致。AMSR-E难以同时反映这2个深度土壤水分的动态变化。

# 2.2AMSR-E土壤水分产品在干旱监测中的应用

距平百分率指某一时段某一指标与同期平均状态的偏离程度，如降水距平百分率，可以用来确定某个时段的降水量，相对于降水量长期平均值是高还是低，是反映干旱的最常用的指标，因此，我们计算了各站点月降水距平百分率,并且根据距平百分率的概念，建立了AMSR-E土壤水分月距平百分率，用于评价AMSR-E在干旱监测中的作用。

2002—2011年的月降水距平百分率同AMSR-E土壤水分月距平百分率之间的相关性空间分布如图7所示，从图上可以看出，大部分地区，这2个指标之间存在正相关关系。从相关系数频率分布图(图8)可以看出，除个别站点外，大部分站点的相关系数在0.5以下。相关性较差的区域主要位于西南、华中和东北等地，相关性高的区域主要位于西北和北方大部分区域。

# 2.3自动站土壤水分同农试站观测及AMSR-E土壤水分产品的对比

由于全国农业气象观测试验站较少，且土壤水分为每旬观测，导致全国常规土壤水分观测也比较少，而大范围、密集建设的带有多种气象要素的自动站将是土壤水分观测的有利补充，也是目前评价卫星遥感产品的有利工具。因此，在此我们比较了甘肃省自动站土壤水分数据同农试站观测的土壤水分数据和AMSR-E土壤水分产品之间的相关性。AMSR-E数据和土壤水分自动站的数据，重合的时段为2010年11月11日至2011年10月3日，该时间段能较好的反映土壤水分的年际变化。在此，根据各站土壤冻融起始时间，仅采用非冻结期的土壤水分观测数据进行一致性对比。由于自动站是每小时记录1次，据此可以获取土壤水分日均值，相对于农试站旬观测，可以得到更多的土壤水分观测数据用于评价AMSR-E土壤水分产品，可以为AMSR-E数据的应用提供科学依据。

![](images/c524f2b914cf0cdc2dcb0865ee3e2f59b5fdca5b85ed4665c958c7a06d5549ef.jpg)  
图7AMSR-E土壤水分距平百分率同降水距平百分率的相关性  
Fig.7Relationship between AMSR-E soil moisture anomaly percentage and precipitation anomaly percentage

表7为自动站土壤水分观测和2种数据的相关性，表明自动站土壤水分同农试站观测的土壤水分之间存在明显的正相关关系，大多数站点的相关性很高，仅敦煌站的相关性比较低，其他站均达到极显著相关。其中宁县相关性最高，相关系数为0.948，这说明目前自动站观测的土壤水分是比较可靠的，可作为农试站土壤水分观测的有利补充，并用于未来越来越多的卫星遥感产品的精度验证和真实性检验。但从表7也可以看出，自动站土壤水分观测同AMSR-E土壤水分产品之间的相关性较差，部分站点相关性达到了显著相关或极显著相关，如甘肃中部的会宁以及东南部的成县和两当，但部分站点相关性不显著，甚至为负相关，如河西的永昌、凉州东和甘南的玛曲和合作，说明卫星产品对土壤水分的探测能力和反演算法尚需改进。

![](images/a34cca57a4f5895bfe6ad96772589ec5c4508c4b9976fb312d5cfce513502c1e.jpg)  
图8AMSR-E土壤水分距平百分率和降水距平百分率相关系数频率分布 Fig.8Distribution frequency of correlation coefficents between AMSR-E soil moisture anomaly percentage and precipitation anomaly percentage

表7自动站土壤水分观测同农试站观测及AMSR-E土壤水分之间的相关性  
Tab.7Relationship ofsoil moisture betweenAMSR-E,agricultural meteorological stationand automatic station   

<html><body><table><tr><td rowspan="2">站点</td><td colspan="2">同AMSR-E土壤 水分相关性</td><td colspan="3">同农试站观测土壤水分相关性</td><td rowspan="2">站点</td><td colspan="2">同AMSR-E土壤 水分相关性</td><td colspan="3">同农试站观测土壤水分相关性</td></tr><tr><td>相关 系数</td><td>样本量</td><td>相关 系数</td><td>样本量</td><td>地表作物类型</td><td>相关 系数</td><td>样本量</td><td>相关 系数</td><td>样本量</td><td>地表作物类型</td></tr><tr><td>敦煌</td><td>0.002</td><td>241</td><td>0.266</td><td>16</td><td>白地、普通棉</td><td>岷县</td><td>-0.058</td><td>260</td><td>0.811**</td><td>33</td><td>马铃薯、其他作物、白地</td></tr><tr><td>永昌</td><td>-0.034</td><td>204</td><td>0.614*</td><td>16</td><td>白地、大麦</td><td>文县北</td><td>-0.006</td><td>302</td><td>0.609**</td><td>52</td><td>冬小麦、夏玉米、白地</td></tr><tr><td>凉州东</td><td>0.077</td><td>216</td><td>0.614**</td><td>25</td><td>白地、春小麦、套玉米</td><td>武山</td><td>0.149°</td><td>269</td><td>0.870**</td><td>19</td><td>冬小麦、白地</td></tr><tr><td>景泰</td><td>0.071</td><td>251</td><td>0.929**</td><td>20</td><td>白地</td><td>成县东</td><td>0.229**</td><td>325</td><td>0.665**</td><td>39</td><td>冬小麦、春玉米、白地</td></tr><tr><td>会宁</td><td>0.167**</td><td>243</td><td>0.745**</td><td>19</td><td>白地、春小麦</td><td>两当</td><td>0.250**</td><td>328</td><td></td><td></td><td></td></tr><tr><td>崆峒</td><td>0.079</td><td>259</td><td>0.450**</td><td>33</td><td>冬小麦、春玉米、白地</td><td>敦煌东</td><td>0.223°</td><td>85</td><td></td><td></td><td></td></tr><tr><td>泾川</td><td>0.090</td><td>265</td><td>0.751**</td><td>29</td><td>冬小麦、高粱、白地</td><td>安定西</td><td>0.184**</td><td>258</td><td></td><td></td><td></td></tr><tr><td>宁县</td><td>-0.039</td><td>256</td><td>0.948**</td><td>17</td><td>冬小麦、白地</td><td>秦安</td><td>0.148*</td><td>258</td><td></td><td></td><td></td></tr><tr><td>玛曲</td><td>-0.131</td><td>211</td><td>0.775**</td><td>20</td><td>白地、牧草</td><td>张家川</td><td>0.084</td><td>278</td><td></td><td></td><td></td></tr><tr><td>合作</td><td>-0.141*</td><td>217</td><td>0.751**</td><td>31</td><td>牧草、青稞</td><td>成县西</td><td>0.242**</td><td>328</td><td></td><td></td><td></td></tr></table></body></html>

# 3结论

本文主要分析了利用2种土壤水分观测资料（全国农业气象试验站地面观测资料和甘肃省自动站观测资料)，评价了AMSR-E利用LPRM算法获得的土壤水分产品的精度。结果表明，大部分农试站站点AMSR-E土壤水分产品和地面观测资料显著相关，可以捕捉到大部分区域的土壤水分变化趋势，而利用自动站土壤水分资料进行验证、评价，虽然部分站点可达到显著或极显著相关，但总体相关性略差。由于自动站的土壤水分数据同农试站观测土壤水分之间相关性很高，在未来遍布全国的自动观测站，以无人值守、密集分布、自动传输等诸多优点，将会是农业气象要素观测的有利补充，也对越来越多的卫星遥感产品精度评价和真实性检验起到重要作用。

AMSR-E数据在监测部分地区时，不论从土壤水分的绝对含量，还是从土壤水分的变化趋势上来看，都存在一定的偏差，这可能和反演时，地表参数的取值、地表类型的分类有一定关系，这也间接说明了，在进行区域尺度土壤水分监测和干旱监测时，对反演算法的某些参数化过程，进行精细校正和完善，才能得到同实际情况更为相符的土壤水分监测结果。

通过对不同作物类型下垫面站点土壤水分和AMSR-E土壤水分数据进行相关性分析时，可以看出，某些下垫面相关性较差，一方面是数据量较少，另一方面是作物对土壤水分反演算法的影响。这说明，AMSR-E在监测中国区域农田土壤水分时，尚需针对不同作物，不同农田区域，对算法进行细致改进[31],这将有利于AMSR-E在中国区域的应用，以及同后续的微波数据进行拼接，获得比较完整的、长序列的、精度较高的土壤水分产品

同时为了评价AMSR-E数据在干旱监测中的作用，分析了由AMSR-E土壤水分产品提取的土壤水分距平百分率，和同期的降水距平百分率之间的相关性，结果显示这两种数据相关性较好，尤其在西北地区和北方大部分区域相关性较好，说明AMSR-E可以用于这些区域的干旱监测，也由于卫星遥感技术的巨大优势，类似的卫星遥感产品也可以在干旱监测中发挥越来越重要的作用。总体来说,本文从不同气候区域、不同作物类型、不同时间段、不同土层深度分析了AMSR-E土壤水分产品的监测效果，揭示了AMSR-E土壤水分产品的精度，可以看出，AMSR-E可以监测土壤水分动态变化，但具体到各区域、各作物类型、各季节，反演算法尚需改进，卫星产品精度还需提高，卫星遥感技术才能更好的监测土壤水分的动态变化。

# 参考文献(References):

[1] MccollKA,Alemohammad SH,AkbarR,etal.The global distribution and dynamics of surface soil moisture[J].Nature Geoscience,2017,10(2):100-104.   
[2] ChenYY,YangK,QinJ,etal.Evaluation ofAMSR-E retrievals and GLDAS simulations against observations of a soil moisture network on the central Tibetan Plateau[J]. Journal of Geophysical Research: Atmospheres,2013,118(10): 4466-4475.   
[3] Engman E T.Hydrologic research before and after Agristars[J]. IEEE Transactions on Geoscience & Remote Sensing,1986,GE24(1): 5-11.   
[4] Sahoo AK,HouserPR,Ferguson C,et al.Evaluation of AMSR-E soil moisture results using the in-situ data over the little river experimental watershed, georgia[J]. Remote Sensing of Environment, 2008,112: 3142-3152.   
[5]Gruhier C,Rosnay PD,Kerr Y,et al. Evaluation of AMSR-E soil moisture product based on ground measurements over temperate and semi-arid regions[J]. Geophysical Research Lettrs,2008,35 (10): L10405.   
[6]Draper C S,Walker JP,Steinle PJ,et al.An evaluation of AMSRE derived soil moisture over Australia[J]. Remote Sensing of Environment, 2009,113(4): 703-710.   
[7]Rudiger C, Calvet JC, Gruhier C,et al. An intercomparison of ERS-Scat and AMSR-E soil moisture observations with model sim ulationsoverfraneJ]Jualofdrometeorology0,2): 431-447.   
[8]Choi M.Evaluation of multiple surface soil moisture for Korean regional flux monitoring network sites: Advanced Microwave Scanning Radiometer E,land surface model,and ground measurements [J]. Hydrological Processes,2012,26: 597-603.   
[9]Jackson TJ, Cosh MH,Bindlish R.Validation of Advanced Microwave Scanning Radiometer soil moisture products[J]. IEEE Transactions on Geoscience and Remote Sensing, 2010,48(12): 4256- 4272.   
[10] Chaurasia S,Tung D T, Thapliyal P K,et al. Assessment of the AMSR-E soil moisture product over India[J]. International Journal of Remote Sensing,2011,32(23): 7955-7970.   
[11]Brocca L, Hasenauer S,Lacava T,et al. Soil moisture estimation through ASCAT and AMSR-E sensors: An intercomparison and validation study across Europe[J]. Remote Sensing of Environment, 2011,115: 3390-3408   
[12]Lei FN,Crow W T,Shen HF,et al. The impact of local acquisition time on the accuracy of microwave surface soil moisture retrievals over the contiguous United States[J].Remote Sensing, 2015,7: 13448-13465.   
[13]Kolassa J, Gentine P,Prigent C,etal.Soil moisture retrieval from AMSR-E and ASCAT microwave observation synergy.Part 2: Product evaluation[J]. Remote Sensing of Environment,2017,195: 202-217.   
[14] 陈洁.AMSR-E土壤湿度产品在我国西北部地区的精度验证 [D].北京:中国气象科学研究院,2010.[Chen Jie.Validation of AMSR-E Soil Moisture Products in the Northwest of China[D]. Beijing: Chinese Academy of Meteorological Sciences,2010.]   
[15]Zhang A Z, Jia G S,Wang HS,et al. Evaluation of AMSR-E: Derived soil moisture over northern China[J]. Atmospheric and Oceanic Science Letters,2011,4(4): 223-228.   
[16]Wu SL, Chen J. Validation of AMSR-E soil moisture products in Xilinhot grassland.Proceedings of Spie the International Society for Optical Engineering,2012, 8531: 85311J-85311J-7.   
[17]Qiu JX, Mo XG,Liu S X,et al. Intercomparison of microwave remote-sensing soil moisture data sets based on distributed eco-hydrological model simulation and in situ measurements over the North China Plain[J]. International Journal of Remote Sensing, 2013,34(19):6587-6610.   
[18]Wigneron JP,Kerr Y,Waldteufel P,et al.L-band Microwave Emission of the Biosphere (L-MEB) Model: Description and calibration against experimental data sets over crop fields[J]. Remote Sensing of Environment,2007,107(4): 639-655.   
[19] Zeng JY,Li Z,Chen Q,et al. Evaluation of remotely sensed and reanalysis soil moisture products over the Tibetan Plateau using insitu observations[J].Remote Sensing of Environment, 2O15,163: 91-110.   
[20]Su Z,Wen J,Dente L,et al. The Tibetan Plateau observatory of plateau scale soil moisture and soil temperature (Tibet- Obs) for quantifying uncertainties in coarse resolution satellite and model products[J]. Hydrology and Earth System Sciences,2011,15(7): 2303-2316.   
[21]Zhang Q,Fan K K, Singh V P，et al.Evaluation of remotely sensed and reanalysis soil moisture against in situ observations on the Himalayan- Tibetan plateau[J]. Journal of Geophysical Research: Atmospheres,2018,123:7132-7148.   
[22]Zhang T T,Gebremichael M, Koppa A,et al.An evaluation of soil moisture from AMSR-E over source area of the Yellow River, China[J]. Sciences in Cold and Arid Regions,2019,11(6): 461-469.   
[23] 席家驹,文军,田辉,等.AMSR-E遥感土壤湿度产品在青藏高 原地区的适用性[J].农业工程学报,2014,30(13):194-202.[Xi Jiaju,Wen Jun,Tian Hui,etal.Applicability evaluation of AMSRE remote sensing soil moisture products in Qinghai-Tibet plateau [J].Transactions of the Chinese Society of Agricultural Engineering,2014,30(13): 194-202.]   
[24] 李哲,王磊,王林,等.基于AMSR-E反演青藏高原夏季表层土 壤湿度[J].高原气象,2017,36(1):67-78.[Li Zhe,Wang Lei, Wang Lin,et al. Top-layer soil moisture retrieval over the Qinghaixizang Plateau in summer based on AMSR-E data[J]. Plateau Meteorology,2017,36(1): 67-78.]   
[25] 李昂,陆其峰,杨晓峰,等.AMSR-E卫星反演土壤湿度与ECWMFNECP再分析土壤湿度比较分析[J].遥感技术与应用,   
2013,28(4): 666-673.[Li Ang,Lu Qifeng,Yang Xiaofeng,et al. AMSR-E soil moisture compared with ECWMF and NECP soil moisture[J].Remote Sensing Technology and Application,2013,   
28(4): 666-673.] [26]孙博,钱静,陈曦,等.常见遥感干旱监测指标在哈萨克斯坦的 一致性分析[J].干旱区研究,2020,37(3):126-133.[Sun Bo, Qian Jing,Chen Xi,et al. Consistency and comparison among remote sensing drought indices and SMAP soil moisture in Kazakhstan[J]. Arid Zone Research,2020,37(3): 126-133.] [27]FAO,IIASA, ISRIC,et al. Harmonized World Soil Database (version 1.1)[R]. FAO,Rome,Italy and IIASA, Laxenburg,Austria,   
2009. [28]Dorigo WA,Wagner W,Hohensinn R,et al. The international soil moisture network:A data hosting facility for global in situ soil moisture measurements[J]. Hydrology and Earth System Sciences Discussions,2011, 15(5): 1675-1698. [29]中华人民共和国国家标准GB/T20481-2006.气象干旱等级 [M].北京:中国标准出版社,2O18.[National Standards of the People's Republic of China,GB/T 20481-2006.Grades of Meteorological Drought[M].Beijing: Standards Press of China, 2018.] [30] 刘广岳,谢昌卫,杨淑华.青藏公路沿线多年冻土区活动层起始 冻融时间的时空变化特征和影响因素[J].冰川冻土,2018,40 (6): 1067-1O78.[Liu Guangyue,Xie Changwei, Yang Shuhua. Spatial and temporal variation characteristics on the onset dates of freezing and thawing of active layer and its influence factors in permafrost regions along the Qinghai Tibet highway[J]. Journal of Glaciology and Geocryology,2018,40(6): 1067-1078.] [31] 魏宝成,银山,贾旭,等.蒙古高原植物生长期土壤水分时空变 化特征[J].干旱区研究,2016,33(3):467-475.[Wei Baocheng, Yin Shan, Jia Xu,et al. Spatiotemporal variation of soil moisture content in the Mongolia Plateau in plant growing season[J].Arid Zone Research,2016,33(3): 467-475.]

# Evaluation of Advanced Microwave Scanning Radiometer for EOS(AMSR-E) soil moisture products over China and its application in drought monitoring

WANG Jing'， FANG Feng²， HUANG Pengcheng²， YUE Ping',LI Jiangping'， WANG Dawei²

(1.Lanzhou Institute of Arid Meteorology,China Meteorological Administration,KeyLaboratory of Arid Climatic Change and Reducing Disaster of Gansu Province,Key Open Laboratory of Arid   
Climate Change and Disaster Reduction of China Meteorological Administration,Lanzhou 730020, Gansu, China; 2.Lanzhou Regional Climate Center,Lanzhou 73oO20, Gansu, China; 3.College of Atmospheric Sciences,Lanzhou University,Lanzhou 73oo2O, Gansu, China)

Abstract: Soil moisture plays an important role in surface energy exchange and climate change. Drought is a common natural disaster and soil moisture is the most intuitive index to reflect drought, therefore the use of microwave remote sensing to monitor surface soil moisture has obvious advantages. Microwave soil moisture products also playan important role in drought monitoring,but because of the difference of underlying surface and the accuracy of inversion algorithm,the application of soil moisture products is limited.Thus this study evaluated the accuracy of widely used AMSR-E (Advanced Microwave Scanning Radiometer for EOS) soil moisture products in china and their role in drought monitoring.The results showed that AMSR-Ecan beter reflect the soil moisture at different depths,most of the sites have a very significant correlation, but the correlation of $2 0 ~ \mathrm { c m }$ is lower than $1 0 \ \mathrm { c m }$ ,and the high correlation coefficient area is significantly reduced; The correlation at bare soil between AMSR-E and agricultural meteorological station is significantly higher than that offarmland.For most crop regions,there are obvious relationships of soil moisture between agricultural meteorological station and AMSR-E. For $1 0 \ \mathrm { c m }$ depth,the best correlation was observed under the planting sorghum with a coefficient of 0.579,while for $2 0 \ \mathrm { c m }$ depth, the best correlation was under cotton with a coefficient of 0.528.The correlation of spring,summer and autumn was higher,but the correlation in winter was slightly lower. In the case of planting crops,the correlations of soil moisture between station and AMSR-E are better in Northeast,South and Northwest China,while in the caseof white land those in Northwest,Southwest and Central China are higher; AMSR-E has a wider range of soil moisture values than the agricultural test station,but the peak values of AMSR-E are different in diffrent regions,and the distribution and fluctuation of the two kinds of soil moisture in North China are relatively consistent; AMSR-Ecan basically reflect the trend ofsoil moisture difference caused by drought in the north and rainy in the south; For most stations and most crop types,if the correlation of $1 0 \ \mathrm { c m }$ between agricultural meteorological station and AMSR-E is good, that of $2 0 \ \mathrm { c m }$ soil moisture will also have this performance.Secondly, there is a good corelation between AMSR-E soil moisture anomaly percentage extracted by AMSR-E and precipitation anomaly percentage, especially in the northwest and most areas of northern China. AMSR-E soil moisture products can beter reflect the fluctuation of precipitation and the occurrence of drought. Keywords: AMSR-E soil moisture; soil moisture; precipitation anomaly index; crop types