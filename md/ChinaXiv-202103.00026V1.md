# 基于栅格累加法的塔里木盆地沙漠化分析

刘畅2，李诚志12.3，李胜辉1,2²，付小磊1，师庆东1.2.3（1.新疆大学干旱生态环境研究所，新疆乌鲁木齐830046；2.新疆大学资源与环境科学学院，新疆 乌鲁木齐830046；3.新疆大学绿洲生态教育部重点实验室,新疆 乌鲁木齐830046)

摘要：土地沙漠化是当今全球最严峻的环境问题之一，也是我国西北干旱区面临的主要生态环境问题。开展土地沙漠化动态研究有助于沙漠化灾害防治与国土资源空间开发。以2000—2018年MODIS-NDVI $1 \mathrm { k m }$ 月数据为基础,运用栅格累加法与转移矩阵法对塔里木盆地土地沙漠化的变化速率、空间特征及其成因进行探索分析，结果表明：(1)土地沙漠化是一个具有年际波动和累积效应的动态变化过程；(2）栅格累加法具有较强的连续动态分析能力，能准确分析土地沙漠化变化速率、演变趋势、变化的空间特征，可以定量分析土地沙漠化原因；(3)塔里木盆地沙漠化退化主要是草地的退化，沙漠化改善则主要是林地和耕地的改善；(4)2000—2018年，塔里木盆地土地沙漠化整体呈极重度沙漠化逐级向非沙漠化变化的改善趋势，转移路径为：极重度沙漠化 $$ 重度沙漠化$$ 中度沙漠化 $$ 轻度沙漠化 $$ 非沙漠化，改善区主要分布在绿洲区，恶化区主要在塔里木河中游与车尔臣河下游，土地沙漠化成因主要为人类活动。此文研究方法为土地沙漠化动态监测提供了一种新思路，其研究结果可为塔里木盆地国土资源开发和沙漠化治理提供理论依据。

关键词：土地沙漠化；栅格累加法；转移矩阵；动态变化；沙漠化成因

# 文章编号：

土地沙漠化是当今世界最严重的环境问题之一，影响全球2/3的国家和10余亿人口[1]。我国受土地沙漠化影响严重，沙漠化面积占国土面积达$2 7 \% ^ { [ 2 ] }$ 。新疆塔里木盆地尤为严重，每年沙漠向绿洲推移 $5 \mathrm { m }$ 以上， $1 2 9 6 \mathrm { k m } ^ { 2 }$ 土地遭受沙化威胁[3，农田、公路、铁路等遭受沙埋，风沙灾害频发，严重影响塔里木盆地甚至我国西北地区的人民生产和生活，亟需对塔里木盆地土地沙漠化动态变化开展研究。

植被是联系土壤、水体和大气之间的关键纽带，是土地沙漠化动态变化监测的重要指标[4],是遥感监测土地沙漠化的"指示器”[5]。归一化植被指数(Normalized difference vegetation index,NDVI）能较好反映荒漠植被盖度,在荒漠监测中运用广泛[6]国内外学者运用Mann-Kendall检验法、趋势分析法、主成分分析法、差值法等方法对NDVI动态变化进行了大量监测研究[7-0],其中差值法计算简单、结果直观被广泛采用[1I-14]。然而，大部分研究仅用几期遥感影像进行差值分析，其监测结果可能与实际情况存在一定差异。植被盖度受到降水量、气温、人类活动等因素影响，仅用几期影像进行监测存在偶然性偏差，更换不同年份的影像所得结果可能不相同。栅格累加法以长时间序列数据为基础进行差值计算可以避免此类偶然性缺陷[15],能真实地反映植被变化。

本文选择2000—2018年月尺度的MODISND-VI数据（MOD13A3），采用栅格累加法和转移矩阵法对塔里木盆地土地沙漠化变化进行研究，以期得到塔里木盆地准确的土地沙漠化变化过程与特征。其研究结果为塔里木盆地国土资源的开发利用做数据支撑，为“丝绸之路经济带”相似区域提供参考。

# 1研究区概况

塔里木盆地是典型的内陆盆地，盆地降水稀少、潜在蒸发大，植被稀疏，属于极端干旱区。盆地年均降水量 $< 5 0 ~ \mathrm { m m }$ ,潜在蒸发量达 $3 4 0 0 ~ \mathrm { { m m } }$ ，降水难以形成有效地表径流，难以满足植被正常生长需求，植被主要依靠河流水和地下水生长。盆地主要河流有塔里木河、阿克苏河、和田河、开都河、喀什噶尔河、车尔臣河(图1)。自然植被大多沿河分布，主要有胡杨（Populus euphratica）怪柳（Tamarix chi-nensis）骆驼刺(Alhagi sparsifolia）花花柴(Karelinia caspia）芦苇(Phragmites communis)等[16]。盆地土壤大多为风沙土，黏粒和有机质匮乏，质地较粗，易被风蚀。

![](images/8f337f56268fb27ff2096f25f582469f30347f892a1c854e7b703751762bfd4d.jpg)  
图1塔里木盆地示意图  
Fig.1 The sketch map of Tarim Basin

盆地人口 $1 0 9 5 . 9 6 \times 1 0 ^ { 4 }$ ，人类活动较为活跃。随着人口的增多，耕地面积逐步扩大，河水与地下水过度引用，河道断流和地下水位降低，下游河道廊道植被退化，导致沙漠化发展迅速。不科学灌溉耕地形成土壤盐渍化,大面积耕地被迫擢荒,进一步加剧土地沙漠化。虽然塔里木河输水工程取得了巨大的成效,但塔里木盆地的沙漠化依然严重[17]

# 2 数据来源

MODIS-NDVI数据质量稳定、周期性强、容易获取[12],被广泛应用[18-19]。本文数据选用美国USGS发布的MODIS植被产品（MOD13A3），空间分辨率1$\mathrm { k m }$ 。本文根据研究区需要，选择轨道号为h23v04、h23v05、h24v04、h24v05、h25v04、h25v05，2000—2018年月合成数据，共计1362景。为进一步分析土地沙漠化成因，从http://www.dsac.cn/下载新疆2010年土地利用图,空间分辨率为 $1 \mathrm { k m }$ ○

# 3研究方法

# 3.1植被盖度计算

运用MRT(MODIS reprojection tool)对影像进行拼接、裁剪、投影转换，得到塔里木盆地2000一2018年NDVI月数据集,值域为 $[ - 3 0 0 0 , 1 0 0 0 0 ]$ 。为消除大气、云、太阳高度角、季节等因素干扰2%，对NDVI月数据进行年最大值合成，生成年最大值NDVI数据。

$\mathrm { N D V I } _ { i } = \operatorname* { m a x } \Bigl ( \mathrm { N D V I } _ { i j } \Bigr ) , j = 1 , 2 , 3 , \cdots , 1 2$ (1)式中：NDVI代表第 $i$ 年的NDVI最大化合成数据；$\mathrm { N D V I } _ { i j }$ 表示第 $i$ 年 $j$ 月的NDVI数据。

影像中NDVI值小于-1000的区域为水域，为消除水域变化对沙漠化变化的影响，将其小于-1000的NDVI栅格值赋为 $1 0 0 0 0$ 。影像中0到-1000的区域为无植被区，NDVI赋值为0。

NDVI是利用植被光谱特征计算出来的一种植被指数，缺乏明确的物理意义，无法进行地面验证[14]。本文采用线性像元二分模型将NDVI转换成植被覆盖度，计算公式为：

$$
F _ { c } = { \frac { \mathrm { N D V I - N D V I } _ { \mathrm { s o i l } } } { \mathrm { N D V I } _ { \mathrm { v e g } } - \mathrm { N D V I } _ { \mathrm { s o i l } } } }
$$

式中： $\boldsymbol { F _ { c } }$ 为植被覆盖度; $\mathrm { N D V I _ { v e g } }$ 为植被盖度接近$100 \%$ 的NDVI值; $\mathrm { \Delta N D V I _ { s o i l } }$ 是无植被地的NDVI值。$\mathrm { N D V I _ { v e g } }$ 选择每年NDVI值都接近接近10000的区域；$\mathrm { \Delta N D V I _ { s o i l } }$ 选择无植被的塔克拉玛干沙漠流动沙丘。每年选择相同 $\mathrm { N D V I _ { v e g } }$ 与 $\mathrm { N D V I _ { \mathrm { s o i l } } }$ 区域减少土壤背景值对计算精度的影响。为方便计算，将像元值域线性调整到[0,100」，得到2000—2018年的植被盖度年度数据集。

# 3.2土地沙漠化分级

本文参考王涛提出的沙漠化分级体系[3],结合塔里木盆地实际情况进行分级，将研究区土地沙漠化分为非沙漠化、轻度沙漠化、中度沙漠化、重度沙漠化、极重度沙漠化5级(表1)。

# 3.3栅格累加计算

土地沙漠化受自然、人为等因素影响而呈波动

# 表1土地沙漠化分级

Tab.1 Desertificationclassification in Tarim Basin   

<html><body><table><tr><td>沙漠化分级</td><td>非沙漠化</td><td>轻度沙漠化</td><td>中度沙漠化</td><td>重度沙漠化</td><td>极重度沙漠化</td></tr><tr><td>植被盖度/%</td><td>[100.0,60.0)</td><td>[60.0,40.0)</td><td>[40.0,26.7)</td><td>[26.7,13.3)</td><td>[13.3,0)</td></tr></table></body></html>

变化，并具有一定累加效应，本文运用栅格累加法对多年土地沙漠化进行研究，分析多年土地沙漠化变化状态以及空间格局，计算公式如下：

$$
E _ { _ { d n } } = \sum _ { i = 1 } ^ { n } ( U _ { _ n } - U _ { 0 } ) / n
$$

式中： $E _ { d n }$ 为第 $n$ 年土地沙漠化累加效应; $U _ { n }$ 为第 $n$ 年土地沙漠化现状; $U _ { 0 }$ 为基准年土地沙漠化现状。

栅格累加的实质是计算多年各个栅格像元植被盖度的年平均变化速率，正值表示栅格像元植被盖度增加，负值表示减少，数值的大小表示平均变化的快慢。依据土地沙漠化的分级标准、实地调查数据分析和反复尝试，最终栅格累加分级标准如表2所示。

# 3.4土地沙漠化成因分析

计算相邻2期土地沙漠化等级图进行转移矩阵，分析不同沙漠化等级之间的转移量与空间分布,结合土地利用类型分析土地沙漠化成因。前人研究显示，塔里木盆地土地沙漠化主要由水资源不合理利用和垦荒造成2%,过度放牧、樵柴毁林、乱挖中草药相对较少。因此在分析土地沙漠化变化成因时，将耕地、建设用地上的土地沙漠化变化划为人类活动直接因素，草地、林地、水域、未利用地上的土地沙漠化变化划为人类活动间接因素。根据转移矩阵计算结果，统计分析土地沙漠化直接因素与间接因素比重，分析土地沙漠化的驱动缘由。

# 4结果与分析

# 4.1土地沙漠化时间变化

对2000一2018年塔里木盆地每年各级土地沙漠化面积进行统计，如图2所示。由图可知，2000—2018年，塔里木盆地植被盖度呈波动上升趋势。19a间盆地内植被盖度年栅格均值增长超过 $5 0 \%$ 。非沙漠化面积大幅增长，累计增长 $2 0 0 0 0 \ \mathrm { k m } ^ { 2 }$ ，增长1.67倍，其中2005、2010、2012、2014年增长较快，2012年增长最快，增长面积达 $9 3 3 2 . 9 4 \mathrm { k m } ^ { 2 }$ 。非沙漠化快速增长可能是塔里木河流域生态输水量增加和退耕还林还草政策共同作用的结果[21-22]。2006、2009、2011、2015、2018年非沙漠化面积则出现小幅下降，最大下降面积达 $3 0 0 0 \mathrm { k m } ^ { 2 }$ 。极重度沙漠化面积整体大幅下降，累积减少 $2 0 0 0 0 \mathrm { k m } ^ { 2 }$ 。2002、2007、2012、2015年极重度沙漠化面积出现大幅度减少，其中2012年面积减少最大，达 $5 3 8 4 ~ \mathrm { k m } ^ { 2 }$ ，而 $2 0 0 1$ ）2004、2006、2016年则出现小幅增加。轻度沙漠化、中度沙漠化、重度沙漠化面积变化较小,基本呈平稳状态。

# 4.2土地沙漠化空间变化

以2000年为基准年，对塔里木盆地进行栅格累加计算，结果如图3所示。塔里木盆地土地沙漠化整体呈改善趋势。盆地改善速率为 $4 4 7 4 9 . 8 0 \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ，恶化速率为 $3 0 0 0 . 5 2 \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ，改善速率远大于恶化速率，盆地土地沙漠化整体呈改善状态。改善主要以低速改善和中速改善为主，分别为 $2 0 9 1 4 . 3 \mathrm { { k m } ^ { 2 } \cdot \mathrm { { a } ^ { - 1 } } }$ 和 $1 9 1 9 6 . 3 \mathrm { ~ k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ;其次为高速改善和极高速改善，分别为 $3 5 6 0 . 6 \mathrm { k m } ^ { 2 } { \cdot } \mathrm { a } ^ { - 1 }$ 和 $1 0 2 4 . 8 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ;超高速改善较小，仅 $5 3 . 8 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 。改善区域广泛分布于绿洲内部及边缘，塔里木河下游沙漠化改善也较为明显。恶化速率相对较低，主要为低速恶化，速率2265.2$\mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ;其次是中速恶化， $6 3 3 . 6 \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ;高速恶化、极高速恶化、超高速恶化速率较小。恶化区域集中于塔里木河中游和车尔臣河下游，其中塔里木河中游(阿拉尔至恰拉水库段)恶化最为严重，盆地 $8 0 \%$ 的低速、中速、高速、极高速恶化均集中于此，恶化

表2土地沙漠化栅格累加速率分级  
Tab.2 Classification of desertification rate used in the grid accumulation method   

<html><body><table><tr><td>分级</td><td>超高速恶化</td><td>极高速恶化</td><td>高速恶化</td><td>中速恶化</td><td>低速恶化</td><td>无变化</td></tr><tr><td>值域范围</td><td>[-100.0,-60.0)</td><td>[-60.0,-40.0)</td><td>[-40.0,-26.7)</td><td>[-26.7,-13.3)</td><td>[-13.3,-6.0)</td><td>[-6.0,6.0]</td></tr><tr><td>分级</td><td>低速改善</td><td>中速改善</td><td>高速改善</td><td>极高速改善</td><td>超高速改善</td><td></td></tr><tr><td>值域范围</td><td>(6.0,13.3]</td><td>(13.3,26.7]</td><td>(26.7,40.0]</td><td>(40.0,60.0]</td><td>(60.0,100.0]</td><td></td></tr></table></body></html>

# 干旱区地理

![](images/6e19b2c42eec26cd2673594414810b6b0388d034f924164b57682c6afc2c38c4.jpg)  
图2 2000—2018年塔里木盆地土地沙漠化变化 Fig.2Desertification change in Tarim Basin during 2Ooo—2018

速率达 $2 3 7 6 \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 。车尔臣河下游恶化也较为明显，主要为低速、中速恶化。另外，叶尔羌河与喀什噶尔河交汇处出现超高速恶化区，不容忽视。

# 4.3土地沙漠化转移变化

2000一2018年各类土地沙漠化转移面积统计如图4所示。从图可知，盆地改善转移量明显高于恶化转移量。改善转移量达 $1 2 1 7 9 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ,恶化转移量仅 $8 9 1 6 ~ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 。塔里木盆地整体呈改善趋势。在改善转移中，极重度至重度转移量最高，年均转移量达 $3 9 2 0 \ \mathrm { k m } ^ { 2 }$ ，占改善量的 $3 2 . 1 8 \%$ ;其次为轻度至非沙漠化，年均转移量 $3 2 9 0 \mathrm { k m } ^ { 2 }$ ，占改善量的$2 7 . 0 1 \%$ 。重度至中度、中度至轻度转移量相对较小,转移量在 $2 4 0 0 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 左右，分别占改善量的

$2 1 . 1 8 \%$ ） $1 9 . 6 2 \%$ 。在恶化转移中，重度沙漠化至极重度沙漠化转移量最大，年均转移量达 $3 1 0 2 \mathrm { k m } ^ { 2 }$ ，占总恶化面积的 $3 4 . 7 9 \%$ ;其次为非沙漠化至轻度沙漠化，占总恶化量的 $2 5 . 7 9 \%$ ;再次为中度至重度，转移量 $2 4 0 0 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ;轻度至中度,转移量 $1 6 0 6 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 轻度至重度，转移量仅 $2 6 0 \ \mathrm { k m ^ { 2 } \cdot a ^ { - 1 } }$ 左右。其余转移量小于 $5 0 \mathrm { k m } ^ { 2 } { \cdot } \mathrm { a } ^ { - 1 }$ ,未在图4中表示。

各转移量均呈年际波动变化。波动量最大是轻度沙漠化到非沙漠化，振幅达 $8 0 0 0 { \mathrm { ~ k m } } ^ { 2 }$ ,其次是极重度至重度，振幅近 $4 0 0 0 { \mathrm { k m } } ^ { 2 }$ ;再次是非沙漠化至轻度、重度至极重度；中度与重度、轻度与中度之间相互转换振幅也较大。年际变化过程中波峰波谷相间出现。在改善转移中，2003、2005、2007、2010、2012、2014、2017年出现波峰，2012年达到顶峰；2004、2006、2009、2011、2013、2015、2018年出现波谷，波峰波谷呈相间分布。恶化转移与改善转移相似，也呈波动状态，但恶化转移的波峰波谷与改善转移的波谷波峰几乎相反。改善转移的波峰对应恶化转移的波谷，改善转移的波谷则对应于恶化转移的波峰。但改善转移量大于恶化转移量，盆地的土地沙漠化向改善方向发展。这种波动变化与盆地河流来水、生态输水存在较大关系[21]

为直观展示各转移类型的空间分布，选取典型4期(2001、2006、2008、2010年)转移分布图进行展示(图5)。从转移的空间分布上看，轻度至非沙漠

![](images/4736124b0eef3b6bd56c44727e1bcb64189ec34d4f6f4a4602b7ba2030f68799.jpg)  
图32000—2018年塔里木盆地土地沙漠化栅格累加空间分布

Fig.3Accumulate spatial distributionofdesertificationusing the gridacumulation methodinTarim Basin during 2000—2018

![](images/5552b4f5bd70dbd21d1d8fef0200494b42ef8cc34557fc1c23e23597c62e73cb.jpg)  
图42000—2018年塔里木盆地土地沙漠化转移量

![](images/14eaa699cab877e187dd771d3afeced8fa957cd529e09b8c47ba5a3c223e63b1.jpg)  
Fig.4 Transformed area of desertification in Tarim Basin during 2Ooo—2018   
图5塔里木盆地土地沙漠化转移空间分布  
Fig.5Spatial distribution of the transformed desertification in Tarim Basin

# 干吴区地理

化、非沙漠化至轻度数量大、分布广，其主要发生于绿洲区内；中度至轻度、轻度至中度，重度至中度、中度至重度,极重度至重度、重度至极重分布相对集中，主要分布于塔里木河中上游、车尔臣河下游、渭干河下游、叶尔羌河与喀什噶尔河交汇处。

# 5讨论

# 5.1土地沙漠化发展方向

上述分析可知，土地沙漠化各等级之间相互转换，且转换频繁，为进一步分析塔里木盆地土地沙漠化转移方向，本文将每年土地沙漠化各等级的转移来源统计如图6所示。非沙漠化与极重度沙漠化的转换来源比较单一。非沙漠化 $9 4 \%$ 来源于轻度沙漠化，极重度沙漠化 $9 6 \%$ 来源于重度沙漠化。轻度沙漠化、中度沙漠化、重度沙漠化则主要由2种土地沙漠化转换而来。轻度沙漠化 $4 9 \%$ 来自中度沙漠化， $4 2 \%$ 来自非沙漠化；中度沙漠化 $5 7 \%$ 来自重度沙漠化， $3 6 \%$ 由轻度沙漠化提供;重度沙漠化 $6 4 \%$ 由极重度沙漠化贡献， $3 3 \%$ 由中度沙漠化贡献。从转移数量上看，塔里木盆地的土地沙漠化转移主要发生在相邻的土地沙漠化等级之间，转移路径为：极重度沙漠化 $$ 重度沙漠化 $$ 中度沙漠化 $$ 轻度沙漠化 $$ 非沙漠化，这与塔里木盆地土地沙漠化改善现象相吻合。

非相邻的土地沙漠化等级之间转移量(跨级转移量)较小且相对较稳定。跨级转移存在2个明显阶段。2001—2009年，跨级转移量较小，2010—2018年转移量变大。在跨级转移中，跨一级转移量占比较多，如极重度与中度、重度与轻度、中度与非沙漠之间的相互转换；跨2级及2级以上转移量非常少。可见塔里木盆地土地沙漠化在年际间是一个逐步连续、逐年波动缓慢变化的过程。

# 5.2土地沙漠化成因

为分析塔里木盆地土地沙漠化成因，现将4.2部分中的栅格累加计算结果按土地利用类型（2010年土地利用图)进行统计，统计结果如图7所示。从统计结果可知，土地沙漠化变化主要发生在水域、草地、林地、耕地和未利用地上。

土地沙漠化恶化区主要发生在草地、水域、林地中。超高速恶化全部在水域地类上；极高速恶化主要在草地与水域地类上;高速和中速恶化主要在草地、林地上;低速恶化则主要在草地、建设用地、耕地和未利用地上。从地类上看，草地退化是沙漠化恶化的主要土地类型，其次是林地和水域，再次是耕地、建设用地和未利用地。

塔里木盆地草地主要分布于河流2岸和尾闾湖周边的湿地,群落种类单一，呈隐域性、中生性和不稳定性[1],极易受河水和地下水影响。当河水和地下水位下降，草地迅速响应而衰退，沙地裸露，沙漠化加重[23]。河水与地下水位具有年际波动特性，从而导致草地具有年际波动特性，这可能是塔里木盆地沙漠化年际波动的主要原因。塔里木盆地林地主要为河岸林和绿洲防护林。从4.2、4.3部分和野外验证调查可知,林地退化区域主要为河岸林,特别是远离河道的天然林，退化主要为灌木衰退。林地对河水和地下水水位的响应速度相比草地要慢一些,因此林地退化主要集中在中速恶化上。塔里木盆地水域面积受人类活动和气候变化而频繁波动，变化速度迅速，因此退化速度表现为超高速。虽然以植被盖度角度分析得出水域退化不一定能真实反映在水域地类上的沙漠化变化，但至少可以反映水域变化的速度。塔里木盆地耕地退化也不容忽视，在高速、中速和低速恶化过程中均有 $12 \%$ 来自耕田，耕地退化主要是耕地盐渍化造成的耕地退化和弃耕形成，分布比较分散。另外，在低速恶化中建设用地占近 $2 0 \%$ ,建设用地的退化原因还需要进一步深入探寻。综上所述，塔里木盆地沙漠化恶化的直接原因是因水资源变动而引起[24，特别是河水与地下水水位变动造成，因此水是塔里木盆地沙漠化治理的关键因子[25]。

土地沙漠化改善区主要发生在林地、未利用地和耕地中。超高速改善主要发生在未利用地；极高速和高速改善主要发生在林地；中速和低速改善则主要发生在林地和耕地。从发生地类可知，林地是改善的主要地类;其次是耕地和未利用地;再次是草地。与土地沙漠恶化相比,草地在改善过程中占比很小，仅占极高速和高速改善 $1 0 \%$ 左右。从沙漠化意识调查可知，大部分人认为治理土地沙漠化主要途径是植树造林[26]。塔里木盆地也一样,在绿洲内部和边缘进行大量的植树造林，林地得到改善;另外，塔河下游河岸林因塔河下游输水工程地持续实施恢复效果也较为显著[27]。绿洲防护林使得绿洲内部生态环境改善，但河岸和绿洲外围的荒漠林却依然在退化，天然林的生态环境在持续恶化。塔里木盆地耕地改善占比也较大。2002年塔里木盆地基本禁止大规模垦荒，耕地改善的原因可能是耕地质量的提升以及种植业转型的结果。随着滴灌技术的推广和土壤盐渍化治理技术的运用，困扰塔里木盆地耕地的盐渍化问题得到一定程度解决，耕地畧荒比例大幅下降。另外，塔里木盆地大面积开展特色林果业种植，林果树中套种作物，耕地盖度和生产力提高。同时耕地间的空地也被开垦出来种植果树，耕地面积得以扩大。这些因素使得耕地在沙漠化改善中较为明显。耕地改善是一个缓慢

![](images/844d1da6e834bc2fde99a6a687ce504dae6f6c80a610231c043a0488baf424f7.jpg)  
图6土地沙漠化转化来源  
Fig.6Sources of desertification transformation in TarimBasin

# 干旱区地理

![](images/af3db7643b3ba590b1bfedb6a5169ccbef759a654540cd6b5c7f2d08cb55a05a.jpg)  
图7各速率的地类分析  
Fig.7 Analysis of the desertification change rate of land-use type in Tarim Basin

的过程，因此改善速度多以低速和中速改善为主。未用地改善也十分显著，在极高速改善中占比较大。在大量资金支持下，塔里木盆地开展了大量的治沙工程，如且末 $7 6 . 7 \mathrm { k m } ^ { 2 }$ 河东治沙工程， $3 1 . 2 8 \mathrm { k m } ^ { 2 }$ 的沙漠公路防风林工程。这些治沙工程使未利用地植被盖度迅速提高，因此未用地改善主要为极高速改善。从改善地类和改善成因可知，塔里木盆沙漠化改善主要为人为因素，在大量的资金投入下沙漠化得以大面积改善。这种改善属于外来输入性改善，可持续性较差，一旦资源输入停止，改善区域面临恶化而恢复到原来的状况。塔里木盆地沙漠化治理的手段和方式还需要进一步深人研究。

# 5.3栅格累加分析法

从4.1和4.3部分可知，土地沙漠化是一个长时间波动变化过程，这种波动性可能是土地沙漠化进程中的一种常态，若不考虑这种波动性仅选取几期遥感影像进行分析，其结果往往具有偶然性，导致结果可能存在偏差，甚至得出完全相反的结论，同时波动变化过程中往往存在一些的累积效应,这种累积效应通常预示了一定的沙漠化发展方向，累积效应分析结果可为沙漠化演变研究提供帮助。因此，合理的土地沙漠化变化监测需要考虑沙漠化的波动性与累积效应。本文使用栅格累加法利用多年连续的遥感数据进行栅格累积分析，既去除波动产生的误差又分析了累加状态，以此得到较为真实的生态环境演变方向、演变趋势和变化速率。如果数据为空间数据还可以得到变化的空间分布，这为生态环境监测提供了一种有效地监测方法与思路。

本文基于栅格累加法分析塔里木盆地的土地沙漠化变化趋势和变化空间，定量确定了塔里木盆地土地沙漠化转移空间分布、转移过程和转移方向，对土地沙漠化变化有了更直观、更深刻的理解，其分析结果与前人的研究相一致[28-30]。栅格累加叠合土地利用类型定量给出塔里木盆地土地沙漠化的原因，为沙漠化治理提供了准确的空间和成因信息。

但本文仅考虑了NDVI这一指标，对气候、土壤、人类活动等探讨还远远不够，还需进一步改进。另外，本文使用的数据分辨率过低，更高分辨率数据也值得探讨。

# 6结论

本文以塔里木盆地2000—2018年MODIS-ND-$\mathrm { V I ~ 1 ~ k m }$ 月植被数据为基础，运用栅格累加法分析塔里木盆地土地沙漠化变化，得出以下结论：

（1）2000—2018年塔里木盆地土地沙漠化是一个年际波动变化过程。盆地内各等级土地沙漠化之间相互转换频繁，年际转换面积呈显著波动，造成土地沙漠化面积年际波动明显，

(2）栅格累加法原理简单、过程明了，能克服年际波动性产生的误差，为连续长时间空间数据的演变趋势、演变速率和空间分布提供了一种简单实用的新方法。2000一2018年塔里木盆地土地沙漠化分析揭示：盆地土地沙漠化整体呈改善趋势;改善速率 $4 4 7 4 9 . 8 0 \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ，改善以低速改善和中速改善为主,改善区域主要分布在绿洲内部和边缘;恶化速率 $3 0 0 0 . 5 2 \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ,主要为低速恶化；恶化区域主要分布于塔里木河中游和车尔臣河下游。

（3）栅格累加法结合转移矩阵分析为定量获取土地沙漠化转移路径、转移数量、转移空间分布提供了一种新的手段。本文首次定量地获取塔里木盆地土地沙漠化的转移路径，其转移路径为：极重度沙漠化 $$ 重度沙漠化 $$ 中度沙漠化 $$ 轻度沙漠化 $$ 非沙漠化；其中轻度沙漠化与非沙漠化之间的转移量最大，主要发生于绿洲区内，空间分布较广；中度与轻度、重度与中度、极重度与重度之间的转换量相对较小，分布相对集中，主要分布于塔里木河中游、车尔臣河下游、渭干河下游、叶尔羌河与喀什噶尔河交汇处。

(4）土地利用类型结合栅格累加法为土地沙漠成因定量分析提供了一种新的尝试。本文分析显示塔里木盆地土地退化主要是草地退化，改善主要为林地和耕地改善。林地以绿洲内部和外部防风林改善为主，耕地改善则主要是盐渍化改造和种植结构调整形成。改善主要是因人类主动活动形成。

致谢：感谢https://search.earthdata.nasa.gov/网站提供MODIS NDVI数据,http://www.resdc.cn/网站提供土地利用数据。

# 参考文献(References)

[1]刘兴文,姜小光.不同时相遥感图像光机复合处理提取土地荒 漠化信息研究[J].干旱区地理,1996,19(3):1-7.[Liu Xingwen, Jiang Xiaoguang. Extraction of the change information of land desertification form multitemporal remote sensing images by the method of combining optical false color composite with computer digital image processing[J]. Arid Land Geography,1996,19(3): 1-7.]   
[2]朱震达.中国土地荒漠化的概念、成因与防治[J].第四纪研究, 1998,18(2):145-155.[Zhu Zhenda. Concept,cause and control of desertification in China[J]. Quaternary Sciences,1998,18(2): 145-155.]   
[3]王涛.中国沙漠与沙漠化[M].石家庄:河北科学技术出版社, 2003,137-141.[Wang Tao.Deserts and desertification in China [M]. Shijiazhuang:Hebei Science and Technology Press,2003, 137-141.]   
[4] Meyer W B,Turner II B L.Human population growth and global land-use/cover change[J].Annual Review of Ecology & Systematics,1992,23(23): 39-61.   
[5]Jacquin A,Sheeren D,Lacombe JP,et al. Vegetation cover degradation assessment in Madagascar savanna based on trend analysis of MODIS NDVI time series[J].International Journal of Applied Earth Observations & Geoinformation,2010,12(13): S3-S10.   
[6]赵鸿雁,陈英,周翼,等.甘肃中东部植被生长季NDVI时空变 化及其对气候因子的响应[J].干旱区地理,2019,42(6):1427- 1435.[Zhao Hongyan, Chen Ying, Zhou Yi,et al.Land cover type clasification and potential desertificion area detecting in Xinjiang based on MODIS NDVI imagery[J].Arid Land Geography,2019, 42(6): 1427-1435.]   
[7]刘洋,李诚志,刘志辉,等.1982—2013年基于GIMMS-NDVI的 新疆植被覆盖时空变化[J].生态学报,2016,36(19):6198- 6208.[Liu Yang,Li Chengzhi,Liu Zhihui,et al.Assessment of spatio-temporal variations in vegetation cover in Xinjiang from 1982 to 2013 based on GIMMS-NDVI[J]. Acta Ecologica Sinica, 2016,36(19): 6198-6208.]   
[8lMuttiPR.Lficio P S.Dubrenil V.et al. NDVI time series stochas

tic models for the forecast of vegetation dynamics over desertification hotspots[J]. International Journal of Remote Sensing,2020,41 (7): 2759-2788.   
[9]唐亮,何明珠,许华,等.基于无人机低空遥感的荒漠植被覆盖 度与归一化植被指数验证及其对水热梯度的响应[J].应用生 态学报,2020,31(1): 35-44.[Tang Liang,He Mingzhu,Xu Hua, et al.Validation of vegetation coverage and NDVI based on UAV remote sensing method and its response to hydrothermal gradient [J]. Chinese Journal of Applied Ecology,2020,31(1): 35-44.]   
[10] Guo B,Zang W Q,Han B M,et al.Dynamic monitoring of desertifiCation in Naiman Banner based on feature space models with typical surface parameters derived from LANDSAT images[J].Land Degradation & Development, 2020,doi: 10.1002/idr.3533.   
[11] 周梦甜,李军,朱康文.近15a新疆不同类型植被 NDVI时空动 态变化及对气候变化的响应[J].干旱区地理,2015,38(4):779- 787. [Zhou Mengtian, Li Jun, Zhu Kangwen. Spatial-temporal dynamics of diferent typesof vegetation NDVIanditsresponse to climate change in Xinjiang during 1998—2012[J]. Arid Land Geography,2015,38(4): 779-787.]   
[12] 李诚志.新疆土地沙漠化监测与预警研究[D].乌鲁木齐:新疆 大学,2012.[LI Chengzhi.Study on the desertification monitoring and early-warning in Xinjiang[D]. Urumqi: Xinjiang University, 2012.]   
[13] 王涛,宋翔,颜长珍,等.近35a来中国北方土地沙漠化趋势的 遥感分析[J].中国沙漠,2011,31(6):1351-1356.[Wang Tao, Song Xiang,Yan Changzhen, et al. Remote sensing analysis on aeolian desertification trends in northern China during l975—2010 [J]. Journal of Desert Research,2011,31(6): 1351-1356.]   
[14] 张建生,闫正龙,王晓国,等.塔里木河下游沙漠化土地时空变 化遥感分析[J].农业工程学报,2009,25(10):161-165.[Zhang Jianshen,Yan Zhenglong,Wang Xiaoguo, et al. Remote sensing analysis of spatial-temporal changes of desertification land in lower reaches of Tarim River[J].Agricultural Engineering,2009,25 (10): 161-165.]   
[15] 宋豫秦,陈妍.荒漠化预警方法研究进展[J].中国沙漠,2017,37 (2): 205-213.[Song Yuqin, Chen Yan.A review of desertification early warning methods[J]. Journal of Desert Research,2O17,37(2): 205-213.]   
[16] 张立运.塔里木盆地诸大河沿岸的天然草地及其人为活动的影 响[J].干旱区资源与环境,1990,4(1): 68-76.[Zhang Liyun. The natural grassands on the flowing plains along the large rivers in Tarim Basin and the affctsof the mankind activities[J]. Journalof Arid Land Resources and Environment,1990,4(1): 68-76.]   
[17]史培军,严平,高尚玉,等.我国沙尘暴灾害及其研究进展与展 望[J].自然灾害学报,2000,9(3):71-77.[Shi Peijun,Yan Ping, Gao Shangyu, et al. The duststorm disaster in China and its research progres[J]. Journal of Natural Disasters,200o,9(3): 71- 77.]   
[18]李军,朱慧.重庆地区MODIS/NDVI时间序列数据重建研究[J]. 地理科学,2017,37(3):120-127.[Li Jun,Zhu Hui. The recon

# 干吴区地理

struction of MODIS/NDVI time series data in Chongqing[J]. Scientia Geographica Sinica,2017,37(3): 120-127.]   
[19] 邓煜霖,姜红涛,张飞,等.艾比湖流域NDVI垂直梯度变化特 征[J].中国沙漠,2015,35(2): 508-513.[Deng Yulin,Jiang Hongtao,Zhang Fei,et al.NDVI at a vertical gradient in the Ebinur Lake Basin,Xinjiang,China[J]. Journal of Desert Research,2015, 35(2): 508-513.]   
[20]TuckerCJ,Newcomb WW,Dregne HE.AVHRR data sets for determination of desert spatial extent[J]. International Journal of Remote Sensing,1994,15(17): 3547-3565.   
[21] 陈亚宁,李卫红,陈亚鹏,等.科技支撑新疆塔里木河流域生态 修复及可持续管理[J].干旱区地理,2018,41(5):901-907. [Chen Yaning,LI Weihong, Chen Yapeng,et al. Science in supporting the ecological restoration and sustainable development of the Tarim River Basin[J].Arid Land Geography,2018,41(5): 901-907.]   
[22]苏冰倩,王茵茵,上官周平.西北地区新一轮退耕还林还草规模 分析[J].水土保持研究,2017,24(4):59-65.[Su Bingqian,Wang Yinyin, Shangguan Zhouping.Analysis on the scale of a new period of returning farmland to forestland and grassland in northwest China[J].Research of Soil and Water Conservation,2O17,24(4): 59-65.]   
[23] 李诚志,张燕,刘志辉,等.新疆地区沙漠化对气候变化的响应 与治理对策[J].水土保持通报,2014,34(4):264-268.[Li Chengzhi,Zhang Yan,Liu Zhihui,et al. Response and control mechanism of desertification to climate change in Xinjiang region[J]. Bulletin of Soil and Water Conservation,2014,34(4): 264-268.]   
[24] 马金珠,李吉均.塔里木盆地南缘人类活动干扰下地下水的变 化及其生态环境效应[J].自然资源学报,2001,16(2):134-139. [Ma Jinzhu,Li Jijun.Impact of human activities on groundwater and the effect on eco-environment in southern Tarim Basin[J].Journal of Natural Resources,2001,16(2): 134-139.]   
[25] 赵明伟,王妮,施慧慧,等.2001—2015年间我国陆地植被覆盖 度时空变化及驱动力分析[J].干旱区地理,2019,42(2):104- 111.[Zhao Mingwei,Wang Ni,Shi Huihui,etal. Spatial-temporal variation and its driving forces of vegetation coverage in China from 2001 to 2015[J]. Quaternary Sciences,2019,42(2):104- 111.]   
[26] 李诚志,张燕,刘洋,等.塔里木河下游居民沙漠化认知[J].中国 沙漠,2016,36(5):1271-1277.[Li Chengzhi, Zhang Yan,Liu Yang,et al.Residents cognition to desertification in the lower reaches of the Tarim River[J].Journal of Desert Research,2016,36(5): 1271-1277.]   
[27] 陈亚宁,李卫红,陈亚鹏,等.新疆塔里木河下游断流河道输水 与生态恢复[J].生态学报,2006,27(2): 538-545.[Chen Yaning, Li Weihong, Chen Yapeng,et al. Water conveyance in dried-up river way and ecological restoration in the lower reaches of Tarim River, China[J]. Journal of Ecology,2006,27(2): 538-545.]   
[28] 杨光华,包安明,陈曦,等.1998—2007年新疆植被覆盖变化及 驱动因素分析[J].冰川冻土,2009,31(3):436-445.[Yang Guanghua,Bao Anming,Chen Xi,et al. Study of the vegetation cover change and its driving factors over Xinjiang during 1998—2007 [J].Journal of Glaciology and Geocryology,2009,31(3): 436-445.]   
[29] 王非,毋兆鹏,汪洋,等.基于RS和GIS的塔里木盆地荒漠化动 态监测[J].生态学杂志,2017,36(4):1029-1037.[Wang Fei,Wu Zhaopeng,Wang Yang,et al.Dynamic monitoring of dsertification in the Tarim Basin based on RS and GIS techniques[J]. Chinese Journal of Ecology,2017,36(4): 1029-1037.]

# Desertification analysis based on grid accumulation method in Tarim Basin, China

LIU Changl2，LI Chengzhi123，LI Shenghui1²，FU Xiaolei1²，SHI Qingdongt123 (1.InstituteofAridEcology&Environmentof XinjiangUniversityUrumqi83046,Xinjiang,China;2.ColegeofResources andEnvironmentalSciences,Xinjiang University,Urumqi3o46,Xinjiang,China;3.KeyLaboratoryofOasisEcology Ministry of Education, Xinjiang University,Urumqi 83OO46,Xinjiang, China)

Abstract: Currently,sandy desertification is one of the most serious environmental problems worldwide.It is also the most crucial ecological environmental problem in the arid areas in western China.The Tarim Basin, located in northwest China,is extremely arid, with litle precipitation,high evaporation,and sparse vegetation. This basin includes the second largest flowing desert,and the problem of sandy desertification is extremely serious.In this paper,the desertification was monitored yearly using the data that were synthesized from the monthly data of MODIS-NDVI $1 ~ \mathrm { k m }$ from 20oO to 2018 using the maximum synthesis method in the Tarim Basin. On the basis of the grid accumulation method,change rate,change trend,and spatial distribution,the causes of the sandy desertification were analyzed in the Tarim Basin.The results showed that: (1) the processof sandy desertification from 2Ooo to 2O18 in the Tarim Basin fluctuated annually,and if the deviation calculation method had been used to monitor the desertification with several remote sensing images,it would have obtained the wrong results.(2)The grid accumulation method can quantitatively analyze the change rate, evolution trend,and spatial characteristics of sandy desertification,and the method is suitable for the analysis of the process of the interannual fluctuation.(3)The new method,combining the grid accumulation method with the transfer matrix analysis method, was presented.This method was used to quantitatively obtain the transfer path, transfer quantity, and transfer spatial distribution of the sandy desertification in the Tarim Basin.Itrevealed thatthe transfer path of thesandy desertification in the Tarim Basin changed from extremely severe desertification to severe desertification,to moderate desertification,to mild desertification,and to non-desertification.Generally，the desertification trend in the Tarim Basin was from extremely severe desertification to non-desertification.The improved areas were distributed in the oases,butthe deteriorated areas were mainly located in the middle reaches of the Tarim River and lower reaches of the Qarqan River. (4) The causes of the desertification were quantitatively analyzed using the method that combined the land-use types and grid accumulation method. This method found that the most important cause of desertification was human activities,the main type of degradation was the degradation of the grassland,and the main types of improvement were those of forest land and cultivated land.This research provided a simple and easy method for the dynamic monitoring of desertification.Its results can accurately show the change rate,evolution trend,spatial distribution,and causes of land desertification,of which accurate information is necessary to control the desertification of the land.

Key Words: sandy desertification； grid accumulation method;transfer matrix method; dynamic change;causes of desertification