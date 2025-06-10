# 近15a陕西省植被时空变化与影响因素分析

岳辉，刘英（西安科技大学测绘科学与技术学院，陕西 西安710054)

摘要：利用2000—2014年MODIS/NDVI时间序列数据,采用栅格像元趋势分析、稳定性评价的方法,研究了陕西省近15a植被的时空变化特征和规律;利用Hurst指数对陕西省植被未来变化趋势进行了预测;并利用相关性分析法分析了NDVI与年均温度和降雨量的关系。结果表明：2000年、2015年陕西省NDVI均值分别为0.4273、0.4942，15a来增加了0.067，增长了 $1 6 . 0 \%$ ,其中陕北地区NDVI增加明显，关中部分地区出现负增长，陕南地区NDVI总体维持在较高水平。陕西省植被变化趋势具有明显的空间差异性，全省植被未变化的占 $5 2 \%$ ，改善部分占 $4 4 . 2 7 \%$ ，退化部分占$3 . 7 3 \%$ ，说明 $1 5 \mathrm { ~ a ~ }$ 间陕西省植被状况有所改善，植被覆盖改善面积大于退化面积，其中陕北地区植被改善区域面积较大，关中地区植被覆盖面积有所减少，陕南地区植被变化幅度较小。陕西省植被稳定区域占 $5 0 \%$ 以上（ $0 < C v < 0 . 1 )$ ，中等程度区域占 $2 8 \% ( 0 . 1 < C v < 0 . 2 )$ ，不稳定区域不足 $2 \%$ （$C v > 0 . 2 )$ ，说明 $1 5 \mathrm { ~ a ~ }$ 间陕西省植被较为稳定，变化程度不大;其中陕西省植被最稳定地区主要集中在陕南、延安南部，榆林部分、西安、渭南少部地区变化幅度较大。Hurst指数分析表明陕西省$4 4 . 5 4 \%$ 面积的植被未来有可能面临退化，主要分布在陕北和关中地区的北部，植被未来有可能退化也有可能改善的面积占 $4 9 . 7 8 \%$ ，主要分布在延安和陕南地区。陕西省近 $1 5 \mathrm { ~ a ~ }$ 气温和降水量总体呈增加趋势，增加速率分别为 $0 . 4 8 \mathrm { ~ ‰ ~ }$ 和 $6 9 . 5 \ \mathrm { m m } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ ；相关性分析结果表明，年均降雨量是影响NDVI的主要气象因子，同时陕西省植被变化也受到了退耕还林还草、防沙治沙、生态政治等人为因素的影响。

关键词：植被；MODIS；NDVI；趋势分析；稳定性评价；Hurst；陕西省文章编号： $1 0 0 0 - 6 0 6 0 ( 2 0 1 9 ) 0 2 - 0 3 1 4 - 0 1 0 ( 0 3 1 4 \sim 0 3 2 3 )$

植被是陆地生态系统中最重要的一部分[1],作为影响人类生存的生物地球化学循环中的关键因子易受自然环境和人类活动影响[2-3]。植被覆盖的变化会影响当地生态平衡与环境质量，植被动态变化研究已成为国内外学者们的关注热点[4-5]。遥感作为重要的植被研究技术手段近年来发展迅速，主要集中在植物及土地覆盖类型的识别、作物估产[7]、植被宏观监测[8]、生物量估算及生物物理参数反演[9]等方面。

陕西省位于我国西北内陆，北部跨黄土高原中部，水土流失、沙化等环境问题严峻。在人类活动和自然环境的演变下，陕西省植被覆盖情况也发生了改变。为此,近年来许多学者对植被变化进行了研究,并取得了一定的成果。秦超等[1]利用2000—2012年SPOT-VGTNDVI数据，通过差值及相关分析法，对陕西省植被覆盖特点及变化规律进行了研究，指出该区植被改善区域大于退化区域。李登科等[11]基于 2000—2013 年 MODIS NDVI 数据,运用混合像元分解模型计算植被覆盖度，评价陕西植被退化情况，结果表明关中城市群和陕北沙漠地带是植被退化的区域，陕西整体上植被呈增加趋势。刘英等[12]利用MODISNDVI数据,采用最大值合成法和像元二分模型对陕西省 2000—2014 年植被覆盖度进行提取并分析其时空变化规律，指出陕西省NDVI呈波动上升趋势，其与年降水量呈显著正相关关系。张君等[13]基于1982—2013 年 NDVI数据和植被类型图，利用趋势分析和聚类分析方法分析了

32a 间陕西植被覆盖状况,表明一年一熟粮作、耐寒经济作物及温带丛生禾草草原的植被覆盖改善程度最高。

本文利用2000—2014 年的 MODIS NDVI数据，基于栅格像元趋势分析、稳定性评价和Hurst指数预测的方法，分析陕西省植被时空变化特征及未来变化趋势，并探讨其变化原因，以期为保护和治理环境提供基础资料。

# 数据与方法

# 1.1 研究区概况

陕西省位于中国西北部，地处 $1 0 5 ^ { \circ } 2 9 ^ { \prime } \ \sim$ $1 1 1 ^ { \circ } 1 5 ^ { \prime } \mathrm { E }$ 和 $3 1 ^ { \circ } 4 2 ^ { \prime } \sim 3 9 ^ { \circ } 3 5 ^ { \prime } \mathrm { N }$ 之间，面积 $2 0 . 5 8 \times 1 0 ^ { 4 }$ $ { \mathrm { k m } } ^ { 2 }$ 。地域南北长,东西窄,南北长约 $8 8 0 ~ \mathrm { k m }$ ,东西宽约 $1 6 0 \sim 4 9 0 ~ \mathrm { k m }$ 。陕西省年平均降水量576.9$\mathbf { m } \mathbf { m }$ ,年平均气温 $1 3 \mathrm { ~ } \mathrm { { ~ ‰ ~ } }$ ,无霜期 $2 1 8 \mathrm { ~ d ~ }$ 左右，属大陆季风性气候，由于南北延伸 $8 0 0 ~ \mathrm { k m }$ 以上，所跨纬度多，从而引起境内南北间气候的明显差异。长城沿线以北为温带干旱半干旱气候、陕北其余地区和关中平原为暖温带半湿润气候、陕南盆地为北亚热带湿润气候、山地大部为暖温带湿润气候。陕西省2016年GDP $1 . 9 \times 1 0 ^ { 1 2 }$ 元,居全国第15位，常驻人口约 $3 ~ 8 1 2 \times 1 0 ^ { 4 }$ 人。

# 1.2 数据及处理

利用2000一2014年美国地球资源观测科学中心提供的空间分辨率为 $1 ~ \mathrm { k m }$ 的陕西省MODIS 植被指数产品（MOD13A3）、MODISTerra $^ +$ Aqua 三级土地覆盖类型年度全球 $5 0 0 \mathrm { ~ m ~ }$ 产品MCD12Q1（http://modis-land.gsfc.nasa.gov/landcover.html），根据国际地圈生物圈计划(IGBP)分类标准，该数据集包含了17个主要土地覆盖类型，即11个自然植被类型、3个土地开发和镶嵌的地类及3个非草木土地类型定义类。利用MRT（MODISReprojection Tool）工具完成数据的投影转换、批处理等过程。从中国气象数据网下载陕西省境内28个气象站点的气象数据，借助ArcGIS10.2使用克里金差值法对获得的气象数据进行差值，得到气象因子的面状栅格数据

# 1.3 研究方法

1.3.1栅格像元趋势分析栅格像元趋势分析可以模拟每个栅格单元的变化趋势，通过这种方法可以模拟出NDVI的变化趋势，进而分析植被覆盖的变化情况[14]

$$
S l o p e = \frac { n \times \displaystyle \sum _ { i = 1 } ^ { n } \left( i \times N D V I _ { i } \right) \ : - \ : \displaystyle \sum _ { i = 1 } ^ { n } i \times \sum _ { i = 1 } ^ { n } N D V I _ { i } } { n \times \displaystyle \sum _ { i = 1 } ^ { n } t _ { i } ^ { 2 } \ : - \ : ( \displaystyle \sum _ { i = 1 } ^ { n } t _ { i } ) ^ { 2 } }
$$

式中：变量 $i$ 为年合成影像按时间排列的序号； $n$ 为样本数; $N D W _ { i }$ 为第 $\mathbf { \chi } _ { i }$ 景影像的NDVI值; $t _ { i }$ 为第 $\mathbf { \chi } _ { i }$ 景影像对应的时间，Slope是2000—2014 年 $N D W$ 的线性回归斜率，若 $S l o p e > 0$ ,则说明该时期内NDVI呈上升趋势,植被覆盖有所改善,反之NDVI下降，植被覆盖情况恶化。

1.3.2稳定性评价年际NDVI的波动是植被受到干扰后在生产力和植被覆盖度上发生年际波动的重要体现，是植被群落健康状况的重要标志。波动值大说明植被群落受到干扰强度大，不稳定;波动值小说明植被群落状态稳定[15]。利用公式(2)和（3)计算2000一2014年NDVI的变异系数，以此来反映研究区域内不同像元上15a来的植被相对波动程度。

$$
S = \sqrt { \frac { \displaystyle \sum _ { i = 1 } ^ { n } \left( N D V { I _ { i } } - \overline { { N D V { I } } } \right) ^ { 2 } } { n - 1 } }
$$

$$
C _ { v } = \frac { S } { N D V I }
$$

式中： $s$ 为NDVI指数的标准差， $C _ { v }$ 为变异系数，为全省 $1 5 \ a$ 的NDVI平均值， $i$ 值从2000 年开始的第 $i$ 年。

1.3.3未来趋势预测对植被未来变化趋势预测采用重标极差分析法，即通过分析时间序列样本的长程依赖性和自相关性得到赫斯特(Hurst)指数，用以描述时间序列未来变化趋势[16]。根据Hurst 指数$H$ 值的不同，可分为：

(1) $H = 0 . 5$ ，说明植被指数时间序列是随机变化的，相互之间不存在依赖关系，是完全独立的。

(2） $0 . 5 < H < 1$ ，说明植被指数时间序列具有持续性， $H$ 值越接近于1，持续性越强。未来植被指数的变化趋势与过去植被变化趋势一致，如果植被在过去呈增加趋势，则未来植被变化趋势也是增加的，反之亦然。

（3） $0 < H < 0 . 5$ ，说明植被指数时间序列具有反持续性， $H$ 值越接近于0，反持续性越强。未来植被指数变化趋势与过去植被变化趋势相反，如果植被过去呈减少趋势，则未来植被变化趋势是增加的，

反之亦然。

1.3.4相关系数法相关分析借助Pearson相关系数，来获得NDVI与年降水量和年平均气温的相关性大小。Pearson相关系数计算公式为：

$$
\begin{array} { c } { { r = \left( n \times \displaystyle \sum X _ { i } y _ { i } - \displaystyle \sum X _ { i } \displaystyle \sum y _ { i } \right) \Bigg / } } \\ { { { } } } \\ { { \Big [ ~ \sqrt { n \times \displaystyle \sum X _ { i } ^ { 2 } - \displaystyle \left( \displaystyle \sum X _ { i } \right) ^ { 2 } } ~ \times } } \\ { { { } } } \\ { { { } \sqrt { n \times \displaystyle \sum ^ { 2 } y _ { i } - \displaystyle \left( \displaystyle \sum y _ { i } \right) ^ { 2 } } ~ \Big ] } } \end{array}
$$

式中： $r$ 为Pearson相关系数; $X _ { i }$ 为 $N D V I ; y _ { i }$ 为气象因子。 $\boldsymbol { r }$ 值的范围为 $\left[ { \begin{array} { l } { - 1 , 1 } \end{array} } \right] , \left| { \boldsymbol { r } } \right|$ 等于0时表明两者无相关性； $\mid r \mid$ 越接近于1表明两者相关性越强；当 $\boldsymbol { r }$ 大于0时为正相关,且越接近于1正相关性越强，当 $r$ 小于0时为负相关，且越接近于-1负相关性越强。

# 2 结果与分析

# 2.1 陕西省土地利用与NDVI空间分布特征

根据IGBP分类结果统计的陕西省土地利用情况，由图1可知2002—2013年陕北土地利用变化情况为从以草地为主，转变为农用地和草地混合，主要集中在榆林市中东部地区；关中地区则是大片农用地，中间分布城镇建设用地，变化不大;陕南地区则以森林灌木为主，陕南森林与灌木面积增加，农用地面积明显减少，汉中市、安康市仅在中部有小片农用地。

为进一步分析土地利用现状，将IGBP中的16类土地利用类型进行合并和聚类分析，将水和永久湿地合并为水/湿地，将常绿针叶林、常绿阔叶林、落叶针叶林、落叶阔叶林、混交林、稠密灌丛、稀疏灌丛合并为林地和灌丛，将木本热带稀疏草原、热带稀疏草原、草地和稀疏植被合并为草地，农用地和农用地/自然植被合并为农用地，城市和建筑用地保持不变。由图2可知，合并后的陕西省2002年土地利用情况为：陕北多分布为草地，关中地区农用地分布最多，陕南山区分布为林地和灌丛、并稀疏分布有农用地；林地和灌丛占 $3 3 . 2 6 \%$ 、草地占 $3 6 . 2 6 \%$ 、农用地占 $2 9 . 5 8 \%$ 。合并后陕西省2013年土地利用情况为：陕北多分布为草地和农用地，关中地区农用地分布最多，陕南山区分布为林地和灌丛,农用地分布减少;林地和灌丛占 $4 2 . 0 7 \%$ 、草地占 $2 7 . 8 9 \%$ 、农用地占 $2 9 . 1 3 \%$ 。需要说明的是IGBP的分类效果对城市和建筑用地以及水体/永久湿地的效果不明显，在2002年和2013年的两次分类对比中两种土地利用类型差别不大，这与实际情况不符，但是草地，农用地和林地/灌丛的分类情况能够反映土地利用的实际情况。

# 2.2 陕西省NDVI时空分布特征

由陕西省2000—2014年NDVI均值图3a可知，陕西省高NDVI的地区主要为陕南、宝鸡市大部分地区、延安市东南与西南部地区；关中地区及延安市中南部地区NDVI处于中等水平，城镇集中地区略低于其他地区;延安市北部、榆林全市 NDVI整体偏低,其中延安市略高，而榆林市西北地区非常低。选取典型年份2002、2007年和2014年(图3b\~3c)进行分析，整体而言陕西省植被覆盖状况呈增加趋势，NDVI总体增大,其中陕北变化最明显,绝大部分地区的植被指数上升，但总体仍较低( $N D V I < 0 . 4 \$ ；关中地区城镇集中，且城镇一直在加速发展，植被类型主要为农用地，受人类活动影响大，NDVI增长较缓慢，部分地区出现负增长；陕南地区高NDVI的面积有明显增加，而且总体依旧维持在较高水平。

# 2.3 陕西省NDVI变化趋势分析

从陕西省植被NDVI变化趋势来看，有很强的空间差异，陕西省NDVI变化趋势线斜率在 $- 0 . 1 \sim$ 0.1之间(图4a），而陕北西、西南部分地区不变或轻微退化，中、东部分地区明显改善，其余地区为轻微改善;关中地区轻微退化面积较大，主要集中在宝鸡中部、咸阳南部、西安大部、渭南中部，这些都是城镇主要集中地区，其余地区轻微改善。陕南大部分地区为轻微改善,但在汉中中部、安康南部、商洛东部有较大面积的轻微退化。全省大部分植被呈轻微改善的趋势（图4b），陕北地区植被明显改善面积较大，主要由于国家退耕还林还草、“三北”防护林工程草、生态恢复重建、和防沙治沙等政策的实施；关中地区人口集中，植被类型多为农作物，易受人类活动影响，随着人口数量的增加，城镇化建设，植被覆盖面积有所减少。陕南秦巴山地，植被种类丰富，数量大，且地形地貌复杂，受人类活动影响小，因而变化幅度小，主要在城镇集中地区有所减少。

全省植被未变化的占了 $5 2 \%$ ,轻微改善的占了$4 2 . 8 \%$ ,轻微退化的占了 $3 . 5 \%$ ，中度改善的占了$1 . 4 6 \%$ ,中度退化的占了 $0 . 1 5 \%$ ,而严重退化和明显改善所占比例均不超过 $0 . 0 1 \%$ 。说明 $1 5 \mathrm { ~ a ~ }$ 间陕西省植被覆盖情况改善，在向好的方向发展。

![](images/2936d0d89a90f7a0171482faafd46675195683d527f5c7c15677a502ea1385b5.jpg)  
岳辉等：近15a陕西省植被时空变化与影响因素分析  
图12002 年陕西省土地利用分类图

![](images/5d000a540c61a6a1f50575b52be2703815b0a8f5b5987ad73ff3490c5c8dccb0.jpg)  
Fig.1Land cover of Shaanxi Province in 2002   
图22013年陕西省土地利用分类图  
Fig.2Land cover of Shaanxi Province in 2013

![](images/6cf429fa89e56009be8ab7b544666919e4fd13c520576ab22c363ea73040322f.jpg)  
图32000—2014 年陕西省NDVI均值空间分布  
Fig.3Spatial pattern of average NDVI of vegetation in Shaanxi Province from 2Ooo -2014

# 2.4陕西省NDVI稳定性分析

计算得到陕西省NDVI变异系数 $( C _ { v } ) , C _ { v }$ 越大，说明越不稳定。全省变异系数范围在 $0 . \ 0 0 4 \ \sim$ 4.475之间（图5a），植被最稳定地区主要集中在陕南、延安南部，变异系数在 $0 \sim 0 . 1$ 之间；西安城区部分、咸阳中部、渭南北部、延安北部、榆林绝大部分地区变化幅度中等，变异系数在 $0 . 1 \sim 0 . 2$ 之间;榆林部分地区、西安、渭南少部地区变化幅度较大，变异系数在 $0 . 2 \sim 1$ 之间;榆林北部一小片地区变化幅度很大，变异系数超过1（图5b）。全省植被稳定区域占 $5 0 \%$ 以上，中等程度区域占 $28 \%$ ，不稳定区域不足 $2 \%$ 。说明 $1 5 \mathrm { ~ a ~ }$ 间陕西省植被较为稳定，变化程度不大。

# 2.5 陕西省NDVI变化预测

根据重标极差分析法的原理，利用MATLAB语言编程实现Hurst指数的逐像元空间计算。由图6a可知，总体上看，陕西省Hurst指数偏低，均值为0.396;陕北地区Hurst指数较高，陕南和关中地区Hurst指数偏低。结合15a来陕西省NDVI的变化趋势(图6b)可得，改善与较弱反持续性区域主要分布在陕北和关中地区的北部，说明植被未来有可能退化，占 $4 4 . 5 4 \%$ ;不变与较弱反持续性和不变与较强反持续性区域主要分布在延安和陕南地区，说明未来有可能退化也有可能改善，共占 $4 9 . 7 8 \%$ ；退化与较弱反持续性主要分布在关中地区和陕南零星地区，说明未来这些地区植被有改善的可能。

![](images/77d3f3d88486e3c63014ffefb4d754862df0d3ae71553189673c5b89d86011b2.jpg)  
岳辉等：近15a陕西省植被时空变化与影响因素分析  
图4陕西省NDVI变化趋势图

![](images/273a94382f74db5056704b5a209c5728c533a7bc6060cae77d8e14b646d3365f.jpg)  
Fig.4NDVI trend map of Shaanxi Province   
图5陕西省NDVI稳定性分析图  
Fig.5Stability analysis diagram of Shaanxi NDVI

![](images/984611a309fb662fe969ad2d53e47f702cb2c09c8e52706e357070cb808be567.jpg)  
干旱区地理  
图6陕西NDVI变化预测图

# 2.6 影响因素分析

由图7a可得，陕西省近15a内平均气温也呈现上升趋势，上升速率为 $0 . \ 4 8 \ \mathrm { ~ \textcircled ~ { ~ C ~ } ~ } \cdot \mathrm { ~ \left( ~ 1 0 ~ \ \mathrm { ~ a ~ } ~ \right) ~ } ^ { - 1 }$ 。2000一2014年间年平均气温变化与NDVI年变化大致相同，说明气温对植被产生一定的影响。由图7b可知,近 $1 5 \mathrm { ~ a ~ }$ 来,陕西省降雨量以 $6 9 . 5 \ \mathrm { m m } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ 的速度增加( $\textstyle P < 0 . 0 5 )$ 。根据NDVI与年均气温的相关性分析可知（图8a），NDVI与年均温存在正相关和负相关，负相关地区比重较大，占研究区面积的$6 5 . 7 \%$ ,通过显著性检验面积不足 $7 . 5 ~ \%$ ,主要分布在榆林、延安及宝鸡和汉中西部地区，这些地区多以耕地为主，说明温度变化并不是陕西省植被变化的主要因素。根据NDVI与年均降雨量相关性分析可知（图8b），NDVI与年均降雨量整体上呈正相关关系，占总面积比例为 $7 5 . 9 \%$ ,其中 $1 6 \%$ 的面积通过了 $P < 0 . 0 1$ 显著性检验，主要分布在陕北和汉中西部;呈负相关的区域主要分布在关中平原，说明主要受人工灌溉影响，受降雨量影响较弱。

![](images/6807b1d35fbb559264dd8da9c64de90bcdfa2e24ba9f458f40894f930f9e227e.jpg)  
Fig.6Shaanxi NDVI change forecast map in 15 a   
图72000—2014 年陕西年平均NDVI与气候因子的年变化 Fig.7Annual variations of climate factors and annual average NDVI Shaanxi during the period of 20oO -2014

![](images/60d585340526e014bc0a3bf66ad88bb8affda43bc820b8185541d2136ffefbc9.jpg)  
岳辉等：近 $1 5 \mathrm { ~ a ~ }$ 陕西省植被时空变化与影响因素分析  
图82000—2014年陕西NDVI与气候因子的相关性  
Fig.8Correlations among Shaanxi NDVI and climate factors in 15 a

# 3结论

（1）15a间，陕西省植被NDVI均值由2000年的0.4273增加到2015年的0.4942，15a来NDVI增加了0.067，增长了 $1 6 . \ : 0 \%$ 。陕北NDVI增加明显，但总体仍较低；关中地区NDVI增长较缓慢，部分地区出现负增长;陕南地区高NDVI的面积有明显增加，且依旧维持在较高水平。陕西省植被变化趋势具有明显的空间差异性，全省大部分植被呈轻微改善趋势，其中陕北地区明显改善面积较大，关中地区植被覆盖面积有所减少，陕南地区变化幅度小。

（2）15a间，陕西省植被最稳定地区主要集中在陕南、延安南部，西安城区部分区域、咸阳中部、渭南北部、延安北部、榆林绝大部分地区变化幅度中等，榆林部分、西安、渭南少部地区变化幅度较大。Hurst分析表明，陕西省 $4 4 . 5 4 \%$ 面积的植被未来有可能面临退化的可能，主要分布在陕北和关中地区的北部，未来变化趋势不明确的面积占 $4 9 . 7 8 \%$ ，主要分布在延安和陕南地区。

（3）年均气温、年均降雨量与NDVI相关性分析可知，年均降雨量与NDVI相关性的空间结构与NDVI变化的空间结构较为相似，说明年均降雨量是陕西省植被变化的主要影响因素，而年均气温不是主要影响因素。

为了防止陕北地区环境恶化，植被退化,应继续大力实施国家退耕还林还草、“三北”防护林工程、生态恢复重建、和防沙治沙等政策；关中地区建设用地扩大应有序进行，尽量减少对植被的破坏。

# 参考文献(References)

[1] WANGQ,ZHANG B,DAI SP,et al.Dynamic changes in vegetation coverage in the Three-North Shelter Forest Program based on GIMMS AVHRR NDVI[J].Resources Science,2011,33（8）: 1613-1620.   
[2] 刘爽，宫鹏.2000—2010 年中国地表植被绿度变化[J].科学通 报,2012,57（16）:1423-1434.[LIU Shuang,GONG Peng. Change of surface cover greenness in China between 2OoO to 2010 [J].Chinese Science Bulletin,2012,57(16）:1423-1434.]

[3]AN Y Z,LIU C S,SHI R H,et al. Spatio-temporal analysis of the vegetation changes based on MODIS time-series data in the Yangtze River Delta region[J].Ecology and Environment Sciences, 2012,21(12):1923-1927.

[4］张华,张改改,吴睿.基于GF-1卫星数据的面向对象的民勤 绿洲植被分类研究[J].干旱区地理，2017，40（4)：831-838. [ZHANG Hua,ZHANG Gaigai,WU Rui. Object-based vegetable classification based on GF-1 imagery in Minqin Oasis[J].Arid Land Geography,2017,40(4）:831-838.]

[5]李净，刘红兵,李龙，等.基于多源遥感数据集的近30a西北地 区植被动态变化研究[J].干旱区地理，2016，39（2）：387- 394.［LI Jing,LIU Hongbing,LI Long,et al.Vegetation dynamic changes in northwest China based on multi-source remote sensing datasets in recent 30 years[J].Arid Land Geography,2016,39 (2):387 -394]

[6]宋开山,张柏,王宗明,等.大豆叶绿素含量高光谱反演模型研 究[J].农业工程学报,2006,22（8）:16-21.［SONG Kaishan, ZHANG Bai,WANG Zongming,et al.Inverse model for estimating soybean chlorophyll concentration using in-situ collected canopy hyperspectral data[J].Transactions of the Chinese Society of Agricultural Engineering,2006,22（8）:16-21.]

[7］徐新刚,王纪华,黄文江,等.基于权重最优组合和多时相遥感的作物估产[J].农业工程学报，2009，25（9）：137-142.［XUXingang,WANG Jihua,HUANGWenjiang，et al.Estimationofcrop yield based on weight optimization combination and multi-temporal remote sensing data[J].Transactions of the Chinese Soci-etyof Agricultural Engineering,2009,25（9） :137-142.]

[8］马磊,闫浩文,何毅,等.2001—2015 年喜马拉雅南麓地区植被 变化遥感监测[J].干旱区地理,2017，40（2）：405-414.［MA Lei,YAN Haowen,HE Yi,et al.Vegetation changes in south Himalayas areas based on remote sensing monitoring during 2001 - 2015[J].Arid Land Geography,2017,40(2）:405-414.]

[9]方秀琴,张万昌.叶面积指数(LAI)的遥感定量方法综述[J].国土资源遥感,2003,15（3）：58-62.［FANGXiuqin，ZHANGWanchang.The application of remotely sensed data to the estima-tion of the leaf area index[J].Remote Sensing for Land and Re-courses,2003,15(3):58-62.]

[10］秦超,李君轶，陈宏飞，等.陕西省植被覆盖时空演变特征及其

与气候因子的关系[J].中国农业气象,2015,36（1)：108- 114.［QIN Chao,LI Junyi,CHEN Hongfei,et al. Temporal and spatial evolution of vegetation cover and its relationship with climate factors in Shaanxi Province[J].Chinese Journal of Agrometeorology,2015,36(1) :108-114.]   
[11］李登科,范建忠,权文婷.陕西省植被退化及其驱动因素分析 [J].生态学杂志,2015,34（10）:2907-2913.[LIDengke,FAN Jianzhong,QUAN Wenting.Analysis of vegetation degradation and its driving factors in Shaanxi Province[J].Chinese Journal of Ecology,2015,34(10):2907 -2913.]   
[12］刘英,侯恩科,岳辉.基于MODIS 的陕西省植被变化遥感监测 分析[J].人民黄河,2017,39(3）:90-94.[LIU Ying,HOU Enke,YUE Hui. Remote sensing monitoring of vegetation changes in Shaanxi Based on MODIS[J].Yellow River,2017,39（3）:90 - 94.]   
[13］张君,延军平.1982—2013 年陕西不同植被类型 NDVI变化特 征分析［J].干旱区资源与环境，2017，31（4)：86－92. [ZHANG Jun,YAN Junping.Characteristics of NDVI changes under the different vegetation types in Shaanxi Province from 1982 to 2013[J]. Journal of Arid Land Resources and Environment,2017, 31(4) :86-92.]   
[14]STOW D,PETERSEN A,HOPE A,et al.Greenness trends of Arctic tundra vegetation in the 199Os:Comparison of two NDVI datasets from NOAA AVHRR system[J].International Journal of Remote Sensing,2007,28(21） :4807 -4822.   
[15］侯美亭,赵海燕,王筝,等.基于卫星遥感的植被 NDVI对气候 变化响应的研究进展[J].气候与环境研究,2013,18（3）： 353-364.[HOU Meiting,ZHAO Haiyang,WANG Zheng,et al. Vegetation responses to climate change by using the satelite-derived normalized difference vegetation index：A review[J].Climatic and Environmental Research,2013,18（3）:353-364.]   
[16］王桂钢,周可法,孙莉,等.近10a新疆地区植被动态与R/S分 析[J].遥感技术与应用,2010,25（1）：84－90.[WANG Guigang,ZHOU Kefa,SUN Li,et al. Studyon the vegetation dynamic change and $\mathrm { R } / \mathrm { S }$ analysis in the past Ten Years in Xinjiang [J].Remote Sensing Technology and Application,2010,25（1）： 84 -90.]

# Vegetation spatiotemporal variation and its driving factors of Shaanxi Province in recent 15 years

YUE Hui，Liu Ying (College of Geomatics,Xi'an University of Science and Technology,Xi'an71Oo54,Shaanxi,China)

Abstract：Based on NDVI from MODIS during the time period from 2O00 to 2O14,the spatial and temporal variation of vegetation in Shaanxi Province,China was analyzed using the methods of raster pixel trend analysis and stability evaluation.The vegetation change trends in the future were forecasted by $\mathrm { R } / \mathrm { S }$ （Rescaled range analysis） method in Shaanxi Province.The correlation analysis was applied between annual temperature,precipitation and NDVI in Shaanxi Province.The results showed that the mean values of NDVI in 200O and 2O14 were O.427 3and 0.4942,respectively,which indicated an NDVI increase of O.O67,or $16 \%$ equivalently.The NDVI was increased significantly in northern region of Shaanxi and there was a negative growth in some parts of Guanzhong area,while the NDVI in southernregionof Shaanxi was stillmaintainedata higher level and changedalitle.Thevegetation variation in Shaanxi Province has obvious spatial regularity.The areas with vegetation of litle change accounted for $5 2 . 0 \%$ in the whole province,while the areas with improved vegetation coverage accounted for $4 4 . 2 7 \%$ ,and the areas where the vegetation was degraded accounted for $3 . 7 3 \%$ . It explained that the overall vegetation coverage in Shaanxi Province was improved in the past15 years.The stability region of vegetation in Shaanxi Province accounted for more than $50 \%$ and the $\boldsymbol { C v }$ value was between O and O.1.The moderate area of vegetation accounted for $28 \%$ and the $\boldsymbol { C v }$ value was between O.1 and O.2.The unstable area of vegetation in Shaanxi Province was less than $2 \%$ and the $\boldsymbol { C v }$ value was greater than O.2.It shows that vegetation condition was relatively stable in Shanxi Province in the past 15 years.The vegetation status was most stable in southern area of Shaanxi Province,southern area of Yan' an City whilevegetation status varied greatly in some partof Yulin City,Xi'an City and the southern partof Weinan City.The analysis of Hurst index showed that $4 4 . 5 4 \%$ area of vegetation in Shaanxi Province may face degradation of vegetation in the future.It is possbly distributed mainly in the northern area and the Guanzhong area. $4 9 . 7 8 \%$ （204 area of vegetation in Shaanxi Province may face improving or degrading in thefuture which is mainlydistributed in Yan'an City and southern area of Shaanxi Province.The annual temperature and precipitation showed an increasing trend in Shaanxi Province in the past 15 years and the increasing rates were $0 . 4 8 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ } ( 1 0 \mathrm { ~ a ~ } ) ^ { \mathrm { ~ - 1 ~ } }$ and $6 9 . 5 \ \mathrm { m m } \ \cdot$ （204号 （204号 $\mathbf { a } ^ { - 1 }$ respectively.The correlation analysis results showed that the annual precipitation was the main meteorological factors affectingthe NDVI.The changes of vegetation in Shanxi Province hadalso been influenced byartificial factors such as the project of returning farmland to forest and grass,sand prevention and ecological politics.

Key Words:vegetation；MODIS；NDVI； trend analysis；stability evaluation；Hurst； Shaanxi