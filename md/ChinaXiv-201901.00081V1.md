# 2000一2016年中亚天山植被变化及气候分异研究

陈秀妍1,²，付碧宏'，时丕龙'，郭强1,2(1中国科学院遥感与数字地球研究所,北京100094；2中国科学院大学,北京100049)

摘要：利用MODIS-NDVI产品生成中亚天山2000—2016年植被覆盖度,利用线性回归法和偏相关法分析了中亚天山植被时空变化特征及驱动因子。结果表明：中亚天山植被生长及变化趋势具有显著的区域分异性，纬度分区上，中天山和北天山西部植被覆盖度较高的草原、农田和森林在2000—2016年呈现退化趋势；南天山和北天山东部植被覆盖度较低的荒漠、草原和灌丛在同期表现出改善趋势，而中国境内的东天山与境外的西天山相比具有较低的植被覆盖度以及总体改善的变化趋势。中亚天山气候在2000—2016年显示出“暖湿化”特征，温度升高幅度 $( 5 . 9 \%$ )远大于降水增加幅度 $( 1 . 3 \%$ )，温度、降水与植被覆盖度的显著相关比例为 $1 8 . 0 \%$ 和 $4 2 . 6 \%$ ，降水是中亚天山植被变化的主要气候驱动因素。以巴音布鲁克草原为代表的东天山部分草原受到过度放牧的影响而退化严重，建议加强植被退化区的生态修复与保护力度。

关键词：植被覆盖度；气候驱动；巴音布鲁克草原；过度放牧；中亚天山文章编号： 1000 -6060(2019)01-0162 -10(0162\~0171)

天山山脉位于亚洲中部,其丰富的冰川和积雪成为中亚干旱地区水资源的重要组成部分[1]。同时，天山山脉的巨大山体改变了西风带及西伯利亚高压气流的进程，成为阻隔中亚各沙漠及新疆古尔班通古特沙漠的风沙南下的生态屏障，为荒漠区绿洲的形成和发展提供了保障[2]。作为对气候变化高度敏感的干旱区高山植被系统，中亚天山的植被生长状况不仅决定着当地的生态环境和畜牧业发展，更对整个中国和中亚地区的生态稳定及经济发展起到重要意义[3]。然而,天山山脉跨越国家和民族的多样性及自然地理单元的完整性，使得该区域的研究成果匮乏[4-5]。现有的研究主要以中国境内的新疆天山为研究对象，进行气候因子对植被变化的驱动研究：李杨等指出气候因子对新疆天山北坡植被生长的影响存在南北分异线[;冯志敏等发现2000一2009年新疆天山温度呈上升趋势，降水呈下降趋势,二者共同导致植被的退化趋势[7]。现有研究没有考虑天山山脉作为完整的地理单元其植被生态与区域气候的整体性，不能综合反映全球气候变化及不同国家和民族的人类活动差异对天山山脉植被生长的影响。

植被覆盖度（Vegetation Fractional Coverage,VFC)是衡量植物覆盖状况的一个综合指标，其对干旱半干旱地区的区域气候变化、土地沙漠化及环境退化很敏感[8]。传统的基于地面测量监测植被覆盖度的方法在大区域范围植被覆盖度的定量研究中具有较大的局限性，因而目前的研究常基于中低分辨率的遥感影像合成植被覆盖度。ZHANG等利用MODIS影像合成中亚沙漠地区植被覆盖度，并分析其对区域温度和降水的响应差异[5]

本文基于MODISNDVI数据、SRTMDEM数据及气温、降水数据，以中亚天山植被变化规律及驱动因子为研究对象，采用遥感数据处理和GIS地理统计方法，提取了2000—2016 年中亚天山生长季植被覆盖度，并采用线性回归分析、偏相关分析等方法探究了植被覆盖度在气候变化背景下所表现出的时空变化规律，以期为中亚天山生态重建与保护提供依据。

# 1研究区概况与数据源

# 1.1 研究区概况

研究区为中亚天山，大致覆盖 $3 7 ^ { \circ } ~ 3 6 ^ { \prime } ~ \sim$ $4 5 ^ { \circ } 5 0 ^ { \prime } \mathrm { N } , 6 6 ^ { \circ } 2 5 ^ { \prime } \sim 9 5 ^ { \circ } 5 0 ^ { \prime } \mathrm { E }$ 的地理范围（图1a），东西长约 $2 ~ 5 0 0 ~ \mathrm { k m }$ ,平均南北宽为 $2 5 0 \sim 3 5 0 ~ \mathrm { k m }$ ,面积大约为 $5 9 . 7 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 。天山横跨中国以及哈萨克斯坦、吉尔吉斯斯坦、塔吉克斯坦和土库曼斯坦5国，平均海拔为 $2 \ 4 8 0 \ \mathrm { m }$ 。天山由一系列高大山地、山间盆地和谷地组成，按照纬度特征将其分为北、中、南3列平行的山体(图1a），东西方向又分为中国境内的东天山以及境外的西天山（图1b）。

天山在中亚及中国西北荒漠地区的包围下，形成了独特的湿润气候[2],其降水主要来自大西洋水汽，少量来自北冰洋水汽，因而西部高于东部，北坡多于南坡[9]。天山共发育15 953 条冰川,是世界现代冰川最多的山系之一,被誉为“中亚水塔”[10],其丰富的冰川和积雪成为中亚及中国西北干旱区最重要的水资源之一，但同时对气候变化十分敏感。有研究表明，中亚天山的气温在1998—2013 年间，比之前的30a升高了约 $1 . 0 \mathrm { ~ \textdegree C }$ ，而降水则呈现极缓慢的增加状态,增加速率仅为8.4mm·（10 a）-1[4]天山气温和降水变化的差异性将对其周边地区生态环境的稳定发展带来巨大的影响。

中亚天山主要的植被类型为草原、森林、灌丛、农田和荒漠，各植被类型所占的面积比例分别为$6 8 . 6 \% . 2 . 2 \% . 1 . 2 \% . 6 . 6 \% . 2 1 . 4 \%$ （图1b）。受到降水影响，植被生长北坡明显好于南坡，西部优于东部，因而荒漠植被主要分布于中国境内的东天山南部的山前区域，森林则主要分布于东、西天山的北部地区。

# 1.2 数据源与预处理

本研究植被信息主要遥感数据源为搭载于Ter-ra卫星的MODIS NDVI16d合成数据 MOD13Q1,空间分辨率为 $2 5 0 \mathrm { ~ m ~ }$ ,影像序列为2000年2月—2016年12月，对NDVI影像进行拼接、裁剪与重投影等预处理，随后利用HANTS滤波算法消除影像中的云、雪及随机误差的干扰，利用像元二分模型法合成VFC，利用平均值法合成生长季VFC，最后利用GIS进行空间处理与统计分析工作。

本研究气温数据源为NOAAESRL（Earth SystemResearchLaboratory）的全球地表温度再分析数据集GHCNCAMS,空间分辨率为 $0 . 5 ^ { \circ } \times 0 . 5 ^ { \circ }$ 。降水数据源为TRMM（Tropical RainfallMeasuring Mis-sion)的测雨产品3B42，空间分辨率为 $0 . 2 5 ^ { \circ } \times$ $0 . 2 5 ^ { \circ }$ ,TRMM降水数据因其较高的精度及可靠性而被国内外的研究学者所广泛使用[1]。本研究温度和降水数据类型均为NetCDF（NetworkCommonDataFormat)格式，首先使用Matlab软件读取研究区及时段内的数据，之后利用GIS进行克里金差值及其他空间处理与统计分析工作。

![](images/954418904d00019f887c45f7e052710848766425c8bc53d69166854591e373f4.jpg)  
图1中亚天山地理位置(a)及植被类型分布(b)  
Fig.1Geographical location（a）and vegetation types（b）of Tianshan,Central Asia

本研究植被类型数据源为MODISMCD12Q1数据集，空间分辨率为 $5 0 0 \mathrm { ~ m ~ }$ ,采用IGBP（InternationalGeosphere-BiosphereProgram）土地覆盖分类体系。本文首先将中亚天山植被类型合并为五种：森林、灌丛、草原、农田以及荒漠，并与冰雪、水体、聚落、湿地共同构成研究区9种土地覆盖类型（图1b）。在后续研究中，进一步将冰雪、水体、聚落以及面积比例不足 $0 . 0 2 \%$ 的永久湿地划定为无植被区。

本研究DEM数据来源于SRTM（ShuttleRadarTopographyMission）DEM数据集,空间分辨率为90m,对DEM影像进行拼接、重投影、裁剪等预处理工作。

# 2 研究方法

# 2.1年际NDVI影像的滤波处理

本文基于HANTS 滤波算法重建2000—2016 年时间序列NDVI影像，利用该算法的目的是消除原始影像中包含的随机噪声及云、雪等干扰，使时序数据更符合植被的物候变化特征[12]。HANTS 算法的主要流程为：

（1）确定曲线拟合过程中的参数，包括：数据的有效值域、周期长度、频率个数、高低抑制标志、数据剔除阈值以及最少保留点数。（2）按照设定的谐波变量拟合现有数据点，并生成一条光滑的拟合曲线。（3）将每一个数据点与拟合曲线进行比较，由于云、雪干扰会导致图像中的NDVI值降低，因此将偏差大于数据剔除阈值的数据点删除，并返回到步骤(2)生成新的拟合曲线。（4）当所有点均不能被剔除或剩余点数达到最少保留点数时，程序结束。

# 2.22000—2016年生长季植被覆盖度合成

对HANTS算法重建的NDVI时间序列数据进行植被覆盖度(VFC)合成。植被覆盖度是指单位面积内被地上部分的垂直投影面积所占的百分比值，采用像元二分模型法合成植被覆盖度。模型可表示为：

$$
V F C = \left( N D V I - N D V _ { s o n L } \right) \bigg / \left( N D V _ { _ { V E G } } - V D V _ { s o n L } \right)
$$

# 2.32000—2016年 $V F C$ 、温度及降水的变化趋势分析

本文将6\~9月4个月作为中亚天山植被的生长季，计算生长季VFC均值、温度均值以及降水累积值[8]。利用线性回归分析法逐像元研究三者的时空变化趋势,并用回归曲线的斜率Slope表示。Slope的计算方法如下所示：

$$
{ \cal S } l o p e = \left( \ \sum { } _ { i = 1 } ^ { n } X _ { i } Y _ { i } \ - n \overline { { { X } } } \overline { { { Y } } } ) \bigg / \ \sum { } _ { i = 1 } ^ { n } X \ { } _ { i } ^ { 2 } - n \overline { { { X } } } ^ { 2 } \ \right)
$$

式中： $n$ 为研究时段的年数， $X _ { i \setminus Y _ { i } }$ 是第 $\mathbf { \chi } _ { i }$ 年变量 $X$ 与 $Y$ 的值，而 $\bar { X }$ 和 $\bar { Y }$ 则表示两变量在研究时段内的平均值。 $S l o p e > 0$ 表示上升趋势，反之则为下降趋势。采用 $F$ 检验法进行变化趋势的显著性检验，$P < 0 . 0 5$ 为显著变化， $P < 0 . 0 1$ 为极显著变化。

# 2.4VFC与气候因素的偏相关分析

本文采用偏相关分析法分别研究VFC与温度和降水的关系。该方法在研究VFC与温度的相关性时消除降水的影响，而在研究VFC与降水的相关性时消除温度的影响。偏相关分析的公式如下：

$$
\gamma _ { n t , p } = \left( \gamma _ { n t } - \gamma _ { n p } \gamma _ { t p } \right) \bigg / \sqrt { \left( 1 - \gamma _ { n p } ^ { 2 } \right) \left( 1 - \gamma _ { t p } ^ { 2 } \right) }
$$

$$
\gamma _ { n p , t } = \left( \gamma _ { n p } - \gamma _ { n t } \gamma _ { p t } \right) \bigg / \sqrt { \left( 1 - \gamma _ { n t } ^ { 2 } \right) \left( 1 - \gamma _ { p t } ^ { 2 } \right) }
$$

式中： $n$ 为生长季 $V F C , t$ 为平均温度， $\mathbf { \nabla } _ { \cdot } p$ 为累积降水，$\gamma _ { n p , t }$ 为 $\mathit { V F C }$ 与温度的偏相关系数， $\gamma _ { n p , t }$ 为 $\mathit { V F C }$ 与降水的偏相关系数。采用 $\mathbf { \chi } _ { t }$ 检验法进行偏相关程度的显著性检验， $P < 0 . 0 5$ 为显著相关， $P < 0 . 0 1$ 为极显著相关。同时，将VFC与温度和降水的偏相关结果叠加，得到VFC与气候因素的综合相关关系。

# 3结果与分析

# 3.1 2000—2016年VFC时空变化特征

研究区17a生长季VFC的均值为0.36，北、中、南天山VFC的均值分别为0.37、0.49以及0.26，东、西天山VFC的均值为0.29、0.43。中亚天山生长季VFC在空间上主要呈现北坡高于南坡、西部高于东部的特点（图2a）。天山周边主要城市点的分布特征为乌鲁木齐、石河子、博乐、伊宁、阿拉木图、比什凯克、塔什干地处天山北坡，杜尚别地处天山西部，这些城市均位于天山中高植被区附近，较好的植被生态及降水使这些地区相对湿润，成为温带干旱一半干旱区内更适合人类居住的城市。而位于天山南坡的喀什、阿克苏、库尔勒、吐鲁番以及哈密均处于塔里木盆地和塔克拉玛干沙漠边缘的河流绿洲内，这些地区干旱少雨，植被覆盖程度较低，是南疆炎热干旱气候的典型城市。

2000一2016年中亚天山植被生长总体呈现轻微改善趋势，改善与退化的面积比例为 $67 \%$ 和$3 3 \%$ ,其中显著改善与显著退化的比例为 $1 5 . 7 \%$ 和$3 . 9 \%$ （图2b)。退化像元在北、中、南天山的面积比例分别为 $2 4 . 0 \%$ $. 4 6 . 3 \%$ 和 $2 9 . 7 \%$ ,在东、西天山的面积比例为 $4 2 . 1 \%$ 和 $5 7 . 9 \%$ 。结合天山植被类型图可知，植被退化像元主要为中天山和北天山西部VFC高值区（ $V F C > 0 . 5 )$ 内的草原、农田和森林,且西天山植被发生退化的情况较东天山更加显著；改善像元在北、中、南天山的面积比例分别为 $2 5 . 8 \%$ 、$2 5 . 8 \%$ 和 $4 8 . 4 \%$ ，在东、西天山的面积比例为 $56 \%$ 和 $44 \%$ ，因此，植被改善像元主要为南天山和北天山东部VFC中低值区 $( 0 . \ 0 5 < V F C < 0 . \ 5 )$ 的草原、荒漠和灌丛，且由于荒漠植被主要分布于东天山，因此东天山植被改善情况较西天山更为显著。

中亚天山五种植被类型的分布面积：草原 $>$ 荒漠 $>$ 农田 $>$ 森林 $>$ 灌丛，草原和荒漠是中亚天山的显域植被，且五种植被类型的VFC均值为：农田(0.68) $>$ 森林（0.58） $>$ 草原（0.46） $>$ 灌丛(0.42) $>$ 荒漠（0.11），无植被区的VFC均值为0.07。5种植被类型中，农田、草原和森林的生长季VFC均值在 $1 7 \ a$ 内总体呈现退化趋势，且农田的退化程度达到显著；灌丛和荒漠的生长季VFC总体呈现改善趋势，其中荒漠的改善程度达到极显著（图$3 \mathrm { a } \sim 3 \mathrm { e }$ )。从(图3f)可以得到：农田和森林的退化面积均大于改善面积，且农田的显著退化比例最高（ $14 \%$ )；草原、灌丛、荒漠的改善面积比例：荒漠 $>$ 灌丛 $>$ 草原，且荒漠的显著改善比例最高( $2 7 \%$ ）。由此可得，研究区VFC值最高的农田和森林在 $1 7 \ a$ 内主要呈现退化趋势，VFC值最低的荒漠和灌丛主要呈现改善趋势，分布最广的草原改善面积略大于退化面积。

# 3.2中亚天山气候因素变化特征

本研究对中亚天山生长季平均温度与累积降水的空间分布及变化趋势的区域性差异进行了分析ig.3Tempo-spatial variationof growing season VFCfordiferent vegetation types during 20oo—2016（（a）grassland;（b）desert vegetation；（c）farmland;（d） forest；（e） shrubland;（f） change trends of all vegetation types）

![](images/b9f3394c3a1ca1d28b73bbb6bff800ec8130ff8bd997028ca43bac81788cb7fa.jpg)  
图2研究区2000—2016年生长季VFC均值(a)及变化趋势空间分布图(b)  
Fig.2Spatial distribution of growing season VFC（a） and its change trends（b）from 2OoO to 2016

![](images/08da48e95a86b89e33657f34e3d2f385939dc6633ce75a0a24eb14a4cb67c031.jpg)  
图32000—2016年中亚天山不同类型植被时空变化

（表1）。中亚天山生长季温度与降水的均值分别为$1 3 . 6 2 ~ \mathrm { ^ { q } C }$ 和 $1 3 4 . 7 6 \ \mathrm { m m }$ 。温度分布：北天山 $>$ 南天山 $>$ 中天山，东天山 $>$ 西天山;降水分布：中天山 $>$ 北天山 $>$ 南天山，东、西天山相近。因此中天山具有较适宜植被生长的水热条件，而降水最少的南天山植被生长较差，分布着大面积的荒漠。同时，东天山东部荒漠植被区的高温以及南部地区的干旱共同导致了其植被生长远差于西天山的结果。

中亚天山生长季温度与降水的变化速率均值分别为 $0 . 0 5 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ 与 $0 . 1 1 \ \mathrm { m m } \cdot \mathrm { a } ^ { - 1 }$ ,即17a内温度和降水分别增加 $0 . 8 0 ~ \mathrm { ^ { q } C }$ 和 $1 . 7 6 \ \mathrm { m m }$ ，总体呈“暖湿化”趋势，且温度和降水的增加量相对其均值分别为 $5 . 9 \%$ 和 $1 . 3 \%$ ,即温度的升高幅度远大于降水的增加幅度。

生长季平均温度在各区域内均呈现升高趋势，且升高速率中天山 $>$ 南天山 $>$ 北天山，西天山 $>$ 东

# 表1中亚天山生长季温度、降水及变化趋势

Tab.1Tempo-spatial variation of growing season temperature and precipitation in Tianshan,Central Asia   

<html><body><table><tr><td>生长季温度 17a均值 /℃</td><td>生长季降水 17a均值 /mm</td><td>生长季温度 变化趋势 Slope / C·a-1</td><td>生长季降水 变化趋势 Slope / mm·a-1</td></tr><tr><td>北天山均值</td><td>15.72</td><td>135.51</td><td>0.02 -0.05</td></tr><tr><td>中天山均值 11.72</td><td>166.99</td><td>0.07</td><td>-0.38</td></tr><tr><td>南天山均值</td><td>13.85 108.65</td><td>0.05</td><td>0.59</td></tr><tr><td>东天山均值</td><td>14.55 134.92</td><td>0.04</td><td>0.18</td></tr><tr><td>西天山均值</td><td>12.67 134.60</td><td>0.05</td><td>0.03</td></tr></table></body></html>

天山。中亚天山整体降水呈现增加趋势，但三个纬度分区内北、中天山均呈现减少趋势，且减少速率中天山远大于北天山，而南天山降水的增加速率高达$0 . 5 9 \mathrm { ~ m m ~ } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ 。受南天山降水显著增加的影响,东天山降水增加速率远高于西天山。因此，研究时段内中天山呈现温度的显著升高以及降水的显著减少，可能是其植被退化的主要原因；南天山温度上升的同时降水显著增加，改善了植被生长条件。而北天山的温度和降水总体变化不明显，但其东西部存在明显的差异性，进而导致其植被生长条件的东西差异。相应地，温度和降水的变化可能是东、西天山植被生长分别呈现改善和退化趋势的主要原因。

本文对生长季温度和降水的变化趋势 Slope 进行显著性检验，结果显示：温度降低和升高的面积比例为 $1 6 \%$ 和 $84 \%$ ，其中显著降低和显著升高的比例为0和 $3 4 . 1 \%$ ;降水减少和增加的面积比例为 $40 \%$ 和 $6 0 \%$ ，其中显著减少和显著增加的比例为 $5 . 5 \%$ 和 $8 . 9 \%$ 。因而，中亚天山在 $1 7 \mathrm { ~ a ~ }$ 内气候呈现“暖湿化”趋势，且温度升高较降水增加更为显著。

# 3.3植被覆盖度与气候因子的关系

本文采用偏相关分析法比较温度和降水对植被变化的驱动强度。中亚天山生长季VFC变化与温度呈正相关和负相关的面积比例为 $5 3 \%$ 和 $47 \%$ ,其中达到显著正相关和显著负相关的比例为： $9 . 9 \%$ 和$8 . 1 \%$ （图4a），说明温度对中亚天山植被变化的驱动力较弱，且正负驱动强度相当。生长季VFC变化与降水呈正相关和负相关的面积比例为 $7 7 \%$ 和

$23 \%$ ，其中达到显著正相关和显著负相关的比例为：$3 8 . 1 \%$ 和 $4 . 5 \%$ ，降水对中亚天山植被变化的驱动力较强，且以正向驱动为主(图4b)。而将中亚天山植被变化与温度和降水的偏相关结果进行叠加（图4c），得到： $9 . 3 \%$ 的植被区仅与温度显著相关，$3 3 . 9 \%$ 的植被区仅与降水显著相关， $8 . 7 \%$ 的植被区与温度和降水均显著相关。因此，中亚天山大部分$( 5 1 . 9 \%$ )区域植被变化受到气候因素的显著影响，且受降水影响的区域较大，受温度影响的区域较小。

从区域尺度分析中亚天山VFC变化与气候因子的偏相关性：VFC与温度的偏相关系数在北、中、南天山的均值分别为 $- 0 . \ 0 0 5 \ _ { \mathrm { s } } - 0 . \ 0 1 1 \ _ { \mathrm { s } } 0 . \ 0 5 9$ ，在东、西天山的均值为0.017和0.023；VFC与降水的偏相关系数在北、中、南天山的均值分别为0.290、0.206、0.274，在东、西天山的均值为0.278和0.224。说明水分条件是植被生长的主要限制因素，降水减少和温度升高导致中天山和北天山西部植被退化，而降水增加则导致南天山和北天山东部植被改善。同时，东天山东部及南部荒漠植被区受到降水大幅增加及温度轻微上升的影响而总体呈现改善趋势；由于西天山大部分山体位于纬度分区的中天山内，因而受到降水减少和温度升高的影响，其总体植被生长呈现退化趋势。

由以上研究可得，温度、降水与中亚天山植被变

![](images/a3d395b3d8b7f5ef90b53f3e12a68d45ff77cae62bfe8c7d8768e9e338953e47.jpg)  
图4研究区生长季VFC与温度(a）降水(b)的偏相关及叠加(c)结果

Fig.4Separate effctsof temperature(a）and precipitation(b）ongrowing season VFC,and combined effcts(c）of them化的显著相关比例为 $1 8 . 0 \%$ 和 $4 2 . 6 \%$ ，图5与表2给出不同植被类型与温度、降水的显著相关情况，对其分析得到以下结论：

![](images/2d2d7380d58f1e5199e44997354185ad9d955e775e53afac4c5933a107c602d2.jpg)  
Fig.5Distribution of vegetation types significantly correlated with temperature（a）and precipitation（b)

（1）五种类型植被变化与降水显著相关的面积  
比例均大于与温度显著相关的比例;（2）与温度显著相关的植被像元包括草原的  
$1 9 . 7 \%$ 、荒漠的 $1 1 . 5 \%$ 、农田的 $2 1 . 5 \%$ 、森林的  
$1 6 . 5 \%$ 以及灌丛的 $2 0 . 0 \%$ ;（3）与降水显著相关的植被像元包括草原的

# 表2不同植被类型VFC变化趋势与温度和降水的相关性面积比例

Tab.2Partial correlations between VFC trends and climatic factors for different types of vegetation/ $\%$   

<html><body><table><tr><td rowspan="3">植被 类型</td><td colspan="2">VFC与温度</td><td colspan="2">VFC与降水</td></tr><tr><td>显著正相关</td><td>显著负相关</td><td>显著正相关</td><td>显著负相关</td></tr><tr><td>草原</td><td>11.6</td><td>8.1</td><td>38.0</td><td>4.7</td></tr><tr><td>荒漠</td><td>6.4</td><td>5.1</td><td>48.6</td><td>1.2</td></tr><tr><td>农田</td><td>4.7</td><td>16.8</td><td>16.1</td><td>11.3</td></tr><tr><td>森林</td><td>7.0</td><td>9.5</td><td>12.4</td><td>10.0</td></tr><tr><td>灌丛</td><td>9.0</td><td>11.0</td><td>26.7</td><td>3.0</td></tr></table></body></html>

![](images/aac7a0c95e31801de7a9d84595902e4f7b09d7f83cc55a3576f2f4956ed1282d.jpg)  
图5与温度(a)降水(b)显著相关的植被类型分布  
图6人类活动对东天山草原植被生长的影响  
Fig.6Effects of human activities on grassland in eastern Tianshan

42. $7 \%$ 、荒漠的 $4 9 . 8 \%$ 、农田的 $2 7 . 4 \%$ 、森林的$2 2 . 4 \%$ 以及灌丛的 $2 9 . 7 \%$ ;

（4）草原是中亚天山的显域植被，与温度、降水显著相关的草原像元广泛分布于整个研究区，但相较而言，与降水显著相关像元在西天山中部分布较集中，这是因为该区域位于天山温度的低值中心以及降水的高值中心附近，植被生长较好，且在研究时段内升温缓慢，因此草原生长随降水增加而呈现改善趋势;

(5）荒漠在五种植被类型中与降水显著相关比例最大而与温度最小,这是由于其主要位于东天山南部的山前平原区，在整个研究区内温度最高且降水最低，因而研究时段内不断增加的降水导致其生长始终呈现改善趋势；

(6）农田主要位于河流、湖泊附近，以伊犁河谷内分布面积最大，森林主要位于中天山和北天山的阴坡内，这两种类型植被受到人类活动的影响较大，受到气候因素的影响为气温升高和降水减少导致的植被退化;

（7）灌丛主要分布在天山的西南角以及荒漠带内，其主要受到降水增加的影响而呈现改善趋势。

以上结果说明，中亚天山植被生长主要受到的气候影响因素为降水；气候升温和降水减少对VFC值最高的农田和森林生长产生较强的抑制作用，导致其VFC值的退化;而气候由"暖干"转为"暖湿"则促进了草原、荒漠和灌丛植被的生长，导致其VFC值的改善。

# 3.4过度放牧对东天山草原变化的影响

本文将温度、降水与中亚天山植被VFC 的偏相关结果进行叠加，结果显示，人类活动等非气候因素对植被变化的贡献率达到 $4 8 . 1 \%$ ,这其中包括面积为 $4 5 \ 6 7 7 \ \mathrm { k m } ^ { 2 }$ 的草原, $1 3 \ 5 0 7 \ { \mathrm { k m } } ^ { 2 }$ 的荒漠,5481$ { \mathrm { k m } } ^ { 2 }$ 的农田 $, 2 \ 0 2 7 \ \mathrm { k m } ^ { 2 }$ 的森林以及 $9 6 8 ~ \mathrm { k m } ^ { 2 }$ 的灌丛（图4c）。草原是中亚天山最主要的植被类型，其对整个中亚和中国西北干旱地区的生态稳定和经济发展都起到重要的意义。然而，随着区域气候变暖与周围城市群的扩张和发展,天山地区已出现十分严重的草地退化、荒漠化与盐碱化（合称“三化”）[13]研究表明，中亚天山已出现退化的草原面积为$3 5 ~ 4 3 6 ~ \mathrm { k m } ^ { 2 }$ ,占草原总面积的 $3 6 . 2 \%$ ,其中退化面积的 $4 7 . 8 \%$ 由人类活动等非气候因素导致。因此深入探究人类活动对草原变化的影响具有十分重要的意义。考虑到文章的篇幅以及相关数据的限制，本文主要对中国境内的东天山草原变化情况进行分析。

图6为东天山草原在人类活动等非气候因素影响下的变化情况，其中退化草原的面积比例为$3 3 \%$ ,退化广泛地发生在整个草原植被区。人类活动主要以过度放牧、非法采矿、旅游开发、道路建设等形式造成草原的“三化”，而尤以过度放牧影响最为严重。本文以东天山草原退化最显著的巴音布鲁克草原为例[（图6)中黄色框线区域]，简要分析人类的放牧活动对天山草原生态造成的破坏。

巴音布鲁克草原植被VFC发生退化的面积比例为 $5 1 \%$ ,显著退化比例为 $6 . 5 \%$ ,其中小尤尔都斯盆地草原的退化最为剧烈。该区域草原退化的自然原因为干旱一半干旱的气候使得区域降水少而蒸发剧烈，生态稳定性及恢复力较差，一旦遭到破坏则极难恢复[14]。作为夏季牧场的小尤尔都斯盆地理论载畜量为 $4 5 . 3 \times 1 0 ^ { 4 }$ 羊单位,而实际上其被用作四季牧场,且载畜量达到理论值的3倍以上[15]。过度放牧导致草场质量下降，草原生态环境被破坏，同时引发了严重的生物灾害。认识到以上问题之后，巴音郭楞蒙古自治州(以下简称巴州)政府于2005 年起开始推行草畜平衡和禁牧休牧轮牧政策，统计资料显示，2010 年底巴音布鲁克草原畜牧存栏量比上年同期减少约 $5 \times 1 0 ^ { 4 }$ 头，且2013年巴音布鲁克自然遗产区成立以来，巴州政府围绕生态核心区与脆弱带，不断加强生态保护措施,并坚决打击非法占用林地、滥砍滥伐、毁林开荒等违法行为，遗产区草原生长呈现改善趋势。但是，小尤尔都斯盆地等区域因为过度放牧而引起的生态破坏却始终无法恢复，植被生长在2000年以来呈现退化趋势。因此，巴州政府应加大生态保护力度，调整生态恢复策略，合理规划旅游开发，实现人与自然的和谐相处。

# 4结论与讨论

# 4.1 结论

本文基于长时间序列遥感数据分析了2000一2016年中亚天山植被时空变化特征及影响因素，得到的认识与结论如下：

（1）空间格局上，中亚天山生长季植被覆盖度  
总体呈现北坡高于南坡，西部高于东部的空间特征。（2）时间序列上,2000—2016 年中亚天山植被  
生长整体呈现改善趋势（面积比例为 $67 \%$ ），植被改

善主要发生在南天山和北天山东部VFC值较低的荒漠、灌丛和草原区，植被退化主要发生在中天山和北天山西部VFC值较高的农田、森林和草原区；同时，中国境外的西天山植被退化较明显，而境内的东天山则植被改善较明显。

(3）影响因素上，中亚天山植被区的 $5 1 . 9 \%$ 受气温、降水的显著影响，且降水是植被变化的主要气候驱动因子。以巴音布鲁克草原为代表的草原植被区受到过度放牧的影响而呈现较严重的退化。

# 4.2讨论

中亚天山植被覆盖在纬度分区上呈现北坡高于南坡的特征，在东西分区上中国境外的西天山高于境内的东天山。吴晓全等认为新疆天山植被NPP在空间上表现为西高东低且自北向南降低的分布特征[16];ZHANG 等的研究表明,地形导致中亚天山的迎风面具有更高的降水量，进而使得天山西部及西北部山脚下的沙漠具有较高的植被覆盖度[5],本文结论与上述学者的研究成果相似。研究时段内，中亚天山植被生长总体呈现改善趋势，与郑艺等得出的全球干旱区植被改善[17]以及邓兴耀等得出的中亚干旱区“变绿”9]的结论一致。气候是驱动大区域植被生长变化的主要因素，水分条件是制约位于干旱一半干旱区内的中亚天山植被生长的主要限制因素。本研究结果与冯志敏等认为降水是影响新疆天山草地NDVI变化的主要因素 的结论一致。而陈亚宁等认为中亚天山在过去的十余年内，气温持续震荡升高,降水基本不变[4],该结论也与本文对中亚天山气候的研究结果相似。因此，本文基于大尺度遥感数据，对中亚天山植被覆盖度的变化进行长时间序列的研究，并对气候驱动机制进行分析，所得结果可以为全球气候变暖背景下天山植被生态的保护与重建提供科学依据。

# 参考文献(References)

[1] SORG Annina,BOLCH Tobias,STOFFEL Markus,et al.Climate change impacts on glaciers and runoff in Tien Shan （Central Asia) [J].Nature Climate Change,2012,2(10）:725-731.   
[2] LI Guoqiang,RAO Zhiguo,DUAN Yanwu,et al.Paleoenvironmental changes recorded in a luminescence dated loess/paleosol sequence from the Tianshan Mountains,arid central Asia,since the Penultimate Glaciation[J].Earth and Planetary Science Letters, 2016,448:1 -12.   
[3] COWAN P J.Geographic usage of the terms Middle Asia and Central Asia[J]. Journal of Arid Environments,20O7,69（2):359- 363. [4］陈亚宁,李稚,方功焕,等.气候变化对中亚天山山区水资源影 响研究[J].地理学报,2017,72（1）:18-26.[CHEN Yaning, LI Zhi,FANG Gonghuan,et al.Impact of climate change on water resources in the Tianshan Mountains,Central Asia[J].Acta Geographica Sinica,2017,72(1):18 -26.] [5]ZHANG Chi,LU Dengsheng,CHEN Xi,et al. The spatiotemporal patterns of vegetation coverage and biomass of the temperate deserts in Central Asia and their relationships with climate controls [J].Remote Sensing of Environment,2016,175:271 -281. [6］李杨,刘艳,马丽云,等.天山北坡气候因子对植被影响的空间 分异性研究[J].干旱区资源与环境,2011,25（7）:91-95.[LI Yang,LIU Yan,MALiyun,etal.Spatial variation of the vegetation effected byclimatic factors in the north slope of Tianshan Mountains[J].Journal of Arid Land Resources and Environment,   
2011,25(7) :91 -95.] [7］冯志敏,赵玲,安沙舟,等.基于 MODIS 的天山山区草地类型 植被指数变化特征及其与气候因子的关系[J].沙漠与绿洲气 象,2015,9（2）:57-62.[FENG Zhimin,ZHAO Ling，AN Shazhou,et al. Change characteristics of MODIS NDVI and its relations to climate factors in the Tianshan Mountains[J].Desert and Oasis Meteorology,2015,9（2）:57 -62.] [8]JIN Xiaomei,LIU Jintao,WANG Songtao,et al. Vegetation dynamics and their response to groundwater and climate variables in Qaidam Basin,China[J]. International Jourmal of RemoteSensing,   
2016,37(3) :710 - 728. [9］邓兴耀,姚俊强,刘志辉.基于GIMMS NDVI 的中亚干旱区植 被覆盖时空变化[J].干旱区研究,2017,34（1)：10 －19. [DENG Xingyao,YAO Junqiang,LIU Zhihui. Spatiotemporal dynamics change of vegetation coverage inarid regions in Central Asia based on GIMMS NDVI[J].Arid Zone Research,2017,34 (1):10 -19.] [10］刘潮海.中亚天山冰川资源及其分布特征［J].冰川冻土,   
1995,17(3）:193-203.[LIU Chaohai.Glacier resources and distributive characteristics in the Central Asia Tianshan Mountains [J]. Journal of Glaciology and Geocryology,1995,17（3）:193-   
203.] [11］李相虎,张奇,邵敏.基于 TRMM 数据的鄱阳湖流域降雨时空 分布特征及其精度评价[J].地理科学进展,2012,31(9)：1164 -1170.［LI Xianghu,ZHANG Qi,SHAO Min.Spatio-temporal distribution of precipitation in Poyang Lake Basin based on TRMM data and precision evaluation[J].Progress in Geography,2012,31 (9):1164 -1170.] [12]BRADLEY Bethany A,JACOB Robert W,HERMANCE John F,et al.A curve fitting procedure to derive inter-annual phenologies from time series of noisy satellte NDVIdata[J].Remote Sensing of Environment,2007,106(2）:137 -45. [13］杨齐,赵万羽,李建龙,等.新疆天山北坡荒漠草地退化现状及 展望[J].草原与草坪,2009,（3）:86-91.[YANGQi,ZHAO Wanyu,LI Jianlong,et al.Analysis of present situation and research progress of desert grassland degradation in northern slope of Tianshan Mountains in Xinjiang[J].Grassland and Turf,2009, (3) :86-91.] [14］李毓堂.巴音布鲁克草原生态破坏调查和治理对策[J].草原 与草坪,2006,（4）:12-14.[LI Yutang.Ecological damage investigation and management countermeasuresof Bayinbuluke Grassland[J].Grassland and Turf,2006,（4):12-14.]

[15］李文利，何文革.新疆巴音布鲁克草原退化及其驱动力分析[J].青海草业,2008,17（2）:44-47.[LI Wenli,HEWenge.The analysison driven forces of degeneration of BayinbulakeGrassland in Xinjiang[J].Qinghai Prataculture,20o8,17（2）：44 -47.]

[16］吴晓全，王让会，李成，等.天山植被NPP时空特征及其对气候 要素的响应［J].生态环境学报，2016，25（11）：1848-1855. [WUXiaoquan,WANGRanghui,LI Cheng,etal. Spatial-temporal characteristics of NPP and its response to climatic factors in Tians han Mountains region[J].Ecology and Environmental Sciences, 2016,25(11) :1848 -1855.]

[17］郑艺，张丽，周宇，等.1982—2012年全球干旱区植被变化及驱动因子分析[J].干旱区研究，2017，34（1）：59-66.［ZHENGYi,ZHANG Li,ZHOU Yu,et al.Vegetation change and its drivingfactors in global drylands during the period of 1982-2012［J].Arid Zone Research,2017,34(1):59 -66.]

# Vegetation dynamics in response to climate change in Tianshan, Central Asia from 2000 to 2016

CHEN Xiu-yan1,²，FU Bi-hong1，SHI Pi-long'，GUO Qiang1,2 (1Institute of Remote Sensing and Digital Earth，Chinese Academy of Sciences,Beijing 1Ooo94,China; 2University of the Chinese Academy of Sciences,Beijing 10oo49,China)

Abstract：The Tianshan Mountains plays a key role in the sustainable development of ecological environment in aridandsemi-arid regions along the Silk Road Economic Belt as an important ecological shield connecting the Central Asiaand Xinjiang,China.Previousstudies indicated thatthe global warming led toaseries of ecological problems in Tianshan,such as a decrease in snowfallrate,severe glacier melting,and significant grassland degradation. It has become an important and urgent task to monitorthe dynamic changes of vegetation in the region and analyze its driving factors. Based on MODIS NDVI data,we calculated the Fractional Vegetation Coverage（ $F V C$ ）of the Tianshan from 20OO to 2O16 using the harmonic analysis of time series（HANTS）algorithm and the dimidiate pixel model.The linear regression and partial correlation analysis were used to map the tempo-spatial variations of $F V C$ （20 and to analyzethe correlation results with the precipitation and temperature.The major conclusions were drawn as follows :（1） The vegetation growth in Tianshan had significant regional differentiation,the mean $F V C$ in the northern,central and southern part of Tianshan was O.37,O.49 and O.26,respectively.In addition,the $F V C$ value was 0.29 in the eastern Tianshan,which is inside China,andO.43 inthe western Tianshan,which isoutside China.The FVC was higher on northern slope and western part.（2）There were $6 6 . 8 \%$ of the vegetation pixels displayed in an improving trend.The farmland and forest with the highest $F V C$ showed degradation trend with the area proportions of $66 \%$ and $5 3 \%$ ,respectively.However,the shrub-desert and shrubland with the lowest $F V C$ showed improving trend with the area proportions of $8 8 \%$ and $74 \%$ ,respectively. Moreover,the most widely distributed grassland has an improvement ratio of $64 \%$ .（3）The temperature and precipitation of Tianshan were increased by $0 . 8 5 ~ \mathrm { { ^ circ C } }$ （20 and $1 . 8 7 ~ \mathrm { m m }$ respectively during the time period from 2O0O to 2016,which indicated equivalentlyan increment of $6 . 2 \%$ of the average temperature and an increment of $1 . 4 \%$ of the precipitation,respectively.（4）The correlation ratios of temperature and precipitation with the $F V C$ were $1 8 . 0 \%$ and $4 2 . 6 \%$ respectively. The precipitation was thedominant factor affcting the change of vegetation in Tianshan.（5）The vegetation in the typical regions like Bayinbuluke Grassand was greatly disturbed byovergrazing. We suggested that the ecological restoration in the vegetation degeneration area should be strengthened and the regional governments should make the reasonable plan for the sustainable tourism development.

Key words:fractional vegetation coverage；climatic factors；Bayinbuluke Grassand；overgrazing,Tianshan Mountains ； Central Asia