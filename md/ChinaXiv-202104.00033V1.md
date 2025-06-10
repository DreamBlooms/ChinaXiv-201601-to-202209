# 内蒙古呼伦贝尔草原湖泊变化研究

耿晓庆¹，胡兆民¹，赵霞¹，沈海花'，方精云1.2（1.中国科学院植物研究所植被与环境变化国家重点实验室，北京100093;2.北京大学城市与环境学院，北京 100871)

摘要：内蒙古呼伦贝尔地区湖泊数量多，面积大，占内蒙古湖泊总面积的 $5 8 \%$ 。近年来该地区湖泊趋于萎缩，但是已有研究主要关注大型湖泊，缺乏对该地区湖泊整体，尤其是小型湖泊( $\left( < 1 \mathrm { k m } ^ { 2 } \right)$ 1的研究。通过利用Landsat系列(TM、ETM+、OLI)卫星数据,参照该地区湖泊图集、湖泊名录以及Google Earth高清影像,分析了1986—2017年呼伦贝尔草原地区湖泊数量和面积变化;在此基础上结合气候和人类活动资料，讨论湖泊变化的影响因素。研究表明：近30a呼伦贝尔地区湖泊显著萎缩，其中变化最为剧烈的是小型湖泊，新增5个，干涸19个，总面积减小超过 $3 0 \%$ 。2000年前各类型湖泊面积均有增加，1998年降水量最大，湖泊面积相应达到峰值;2000—2010年湖泊面积呈萎缩趋势;2010年以后有所回升。将湖泊面积与气候条件(气温、降水量、潜在蒸散量)及人为活动因子(放牧强度、原煤产量、有效灌溉面积)进行相关分析发现,湖泊面积变化主要受人类活动的影响，气候变化的影响相对较小。

关键 词：湖泊；Landsat；面积变化；数量变化；呼伦贝尔文章编号：

呼伦贝尔市位于内蒙古自治区东部，地处 $1 1 5 ^ { \circ } 3 1 ^ { \prime } .$ $1 2 6 ^ { \circ } 0 4 ^ { \prime } \mathrm { E } , 4 7 ^ { \circ } 0 5 ^ { \prime } { \sim } 5 3 ^ { \circ } 2 0 ^ { \prime } \mathrm { N }$ ，总面积约 $2 5 { \times } 1 0 ^ { 4 } \ \mathrm { k m } ^ { 2 }$ ，区域内湖泊星罗棋布。湖泊是地下水与地表水、陆地与大气间进行水气交换的重要环节，在维持土壤蓄水性、保持植被多样性、改善周边小气候条件等方面发挥着重要作用[2-3]。呼伦贝尔草原是我国的主要牧场[4-5],受人为活动以及气候暖干化等因素的影响,草地退化现象明显[6-8]。研究表明，该地区湖泊的萎缩加剧了草原生态系统退化并危及牧民生活[9-10]。因此,以呼伦贝尔草原为主要研究区,监测该区域湖泊的分布及变化至关重要

以往对呼伦贝尔地区湖泊的研究主要关注大型湖泊,如呼伦湖[1,1-14];然而关于中小湖泊群的变化却少有关注。相关研究表明这些广泛分布的湖泊群对于发展当地草原畜牧业和工农业生产意义重大[15]。因此,本研究采用Landsat TM、 $\mathrm { E T M + }$ 、OLI数据，结合气候、年鉴等资料，分析最近30a(1986一

2017年)呼伦贝尔地区湖泊的变化及其驱动因素，重点关注中小型湖泊，它们对环境的变化响应更为敏感，对草原畜牧业的影响也更广泛。由于呼伦贝尔湖泊主要分布于西南草原地区，故本研究选取呼伦贝尔市西南六旗(新巴尔虎右旗、新巴尔虎左旗、陈巴尔虎旗、海拉尔市、鄂温克族自治旗、满洲里市)为研究区域(图1)。

# 数据和方法

# 1.1数据来源

1.1.1遥感数据本研究采用美国地质调查局(USGS)提供的Landsat系列遥感卫星数据，其空间分辨率为 $3 0 \mathrm { m }$ 、重访周期 $1 6 \mathrm { d } _ { \odot }$ 。Landsat卫星自1972年发射成功以来,共发射8颗卫星。其中Landsat 5的ThematicMapper（TM)数据时间覆盖范围为1984——2O11年,Landsat 7的Enhanced Thematic Map-per-plus( $\mathrm { E T M } +$ )的时间覆盖范围为1999年至今（但多数ETM $^ +$ 影像因条带问题不能使用），Landsat8OperationalLandImager(OLI)的数据时间覆盖范围为2013年至今。针对具体的研究区域，本文利用1986—2011年的TM数据，2012年的 $\mathrm { E T M } +$ 数据和2013—2017年的0LI数据。

![](images/49720b8865b0f4d6ce79376f75004d9b03706583285e24be4ee11cf7a58449d7.jpg)  
图1研究区行政和海拔分布示意图Fig.1 Study area and altitudes

GoogleEarthEngine（GEE）是Google提供的可对多种全球尺度的地球科学资料（尤其是卫星数据)进行在线可视化计算分析处理的全新平台[16]该平台数据获取方便，拥有最近30a近地卫星存档数据，可以在线查询Landsat、MODIS等主流遥感卫星数据；利用Google提供的云计算服务功能，能够快速、批量处理目标遥感影像数据，分析时间大大缩短。本文的前期数据处理都是在GEE平台上进行的，其中GEE数据处理平台提供的Landsat Sur-faceReflectanceTier1数据，是经过大气校正的表面反射率数据。

1.1.2气象数据及年鉴统计数据气候数据采用国家气象局(http://data.cma.cn/data/cdcindex.html)提供的1986—2016年内蒙古呼伦贝尔市4个气象站点的年降水量以及年均气温数据，并利用Thornthwaite方法[17-19]计算潜在蒸散量。1988—2017年呼伦贝尔市的原煤产量、放牧强度(大牲畜、羊、猪年末数总和）、有效灌溉面积数据均取自内蒙古统计年鉴[20]。

# 1.2分析方法

近年来发展了多种水体提取方法，主要包括单波段阈值法、多波段谱间关系法、水体指数法、还有神经网络、小波分析等方法[21]。水体在蓝绿波段反射率较强，其他波段反射率较低，近红外波段反射率基本为零，这一特征使得水体在遥感影像上与其他地物存在显著差异。水体指数法是基于水体的反射光谱特征，构建增强水体信息的指数模型并利用阈值直接提取水体的方法。其中，归一化差异水体指数（Normalized difference water index,NDWI)[22]在水体动态监测研究中取得了理想的效果，是目前最为常用并得到广泛认可的分析方法。因此，本研究也采用NDWI指数来提取湖泊覆盖范围。

$$
\mathrm { N D W I } = { \frac { G - \mathrm { N I R } } { G + \mathrm { N I R } } }
$$

式中： $\boldsymbol { G }$ 波段：Landsat5、7的band2、Landsat8的band 3;NIR波段:Landsat5、7的band5、Landsat8的band 6。

由于湖泊面积的本底值存在差异，为反映一个地区湖泊面积变化的整体趋势，本文利用相对湖泊面积（Relativewaterarea,RWA)[9.23]来描述某一地区所有湖泊不同年代的相对面积变化情况，RWA的计算方法如下：

$$
\mathrm { R W A } \big ( \mathcal { H } _ { o } \big ) = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } ( A _ { i } \big / A _ { i } ^ { s } ) \times 1 0 0 \
$$

式中： $n$ 表示湖泊数量： $A _ { i }$ 表示第 $i$ 个湖泊在某个时间段的平均面积 $( \mathrm { k m } ^ { 2 } ) ; A _ { i } ^ { s }$ 表示第 $i$ 个湖泊在基准年代$s$ 的面积 $\left( \operatorname { k m } ^ { 2 } \right)$ 。本文基准年代为数据的起始年代（1986—1990年）。

# 1.3数据处理步骤

1.3.1影像数据处理考虑到水域面积随季节发生变化，湖泊面积研究应尽量选择同时相影像数据，针对呼伦贝尔的气候特征，本文选取6一9月丰水期期间,单幅影像云量 $< 1 0 \%$ 的影像数据[24]。首先利用GEE平台获取Landsat5、Landsat7、Landsat8的Sur-faceReflectanceTier1数据，并利用相匹配的像元质量评价数据去除云、云阴影、冰雪等非晴空目标像元，空间叠加拼接获取每年的影像数据。对拼接生成的影像数据再次进行整体质量评估(统计在32a水体累积出现的最大区域内像元缺失率是否低于$2 \%$ ），去除影像整体质量较差的年份（1987、1990、2003、2004年和2012年）。

1.3.2水体特征识别利用上述NDWI公式计算水体指数，将满足阀值范围(NDWI>O)的区域提取出来，即为所要求的水体区域。

1.3.3分类精度评价采用误差矩阵计算的总体精度和Kappa系数2个指标对水体的识别结果进行精度评价。以2001年分类结果为例，利用GoogleEarth高分辨率历史影像数据，选取9668个验证样点（验证样点的选取方法是以经纬度 $0 . 0 1 ^ { \circ }$ 为间隔，

# 干吴区地理

在32a水体累积出现的最大区域范围内均匀采样），人工目视判别建立验证数据集，经统计分类总体精度为 $9 5 . 5 1 \%$ ,Kappa系数 $( K )$ 为 $9 0 . 1 3 \%$ (表1)，说明提取结果的精度是相当高的，满足分析要求。 $K$ 计算公式如下：

$$
K = \frac { N \displaystyle \sum _ { i = 1 } ^ { r } x _ { i i } - \sum _ { i = 1 } ^ { r } ( x _ { i + } \times x _ { + i } ) } { N ^ { 2 } - \displaystyle \sum _ { i = 1 } ^ { r } ( x _ { i + } \times x _ { + i } ) }
$$

式中： $r$ 为误差矩阵中总列数(即总的类别数)； $x _ { i i }$ 是误差矩阵中第 $i$ 行、第 $i$ 列上样点数量（即正确分类的数目）; $x _ { i + }$ 和 $x _ { + i }$ 分别是第 $i$ 行和第 $i$ 列的总样点数量； $N$ 是总的用于精度评价的样点数量

# 表1误差矩阵

Tab.1 Errormatrix   

<html><body><table><tr><td rowspan="2">实际类型</td><td colspan="3">分类结果</td></tr><tr><td>非水体</td><td>水体</td><td>总和</td></tr><tr><td>非水体</td><td>6078</td><td>46</td><td>6124</td></tr><tr><td>水体</td><td>388</td><td>3156</td><td>3544</td></tr><tr><td>总和</td><td>6466</td><td>3202</td><td>9668</td></tr><tr><td colspan="4">总体精度=95.51%,K=90.13%</td></tr></table></body></html>

1.3.4湖泊变化分析因本研究关注的是开放状态的湖泊水体，参照湖泊图集[25]、湖泊名录[26]以及GoogleEarth高清影像，将河流等一些水体去除，并按照湖泊的面积大小，划分为小湖泊 $( 0 . 5 { \sim } 1 ~ \mathrm { k m } ^ { 2 } )$ ）、中湖泊( $\scriptstyle 1 \sim 1 0 \mathrm { k m } ^ { 2 } ,$ 、大湖泊 ${ \bigl ( } { > } 1 0 \ { \mathrm { k m } } ^ { 2 } { \bigr ) } 3$ 类。首先统计1986—1990年、2014—2017年首末2个年代的湖泊个数和面积，分析湖泊整体变化状况，然后详细分析各类型湖泊数量及面积的年际变化特征，重点关注中小型湖泊的增加与消亡情况，并讨论湖泊变化的驱动因素。

# 2结果与分析

# 2.1 湖泊分布

研究区域内，1980年代末面积大于 $0 . 5 \mathrm { k m } ^ { 2 }$ 的湖泊共有128个(图2、表2)，总面积约 $2 4 1 6 \mathrm { k m } ^ { 2 }$ 。其中新巴尔虎左旗湖泊数量最多，约50个，占湖泊总个数的 $3 9 \%$ ;其次是新巴尔虎右旗，约40个，占湖泊总数的 $3 1 \%$ 。而湖泊面积最大的是新巴尔虎右旗(约$2 2 0 2 \mathrm { k m } ^ { 2 }$ )，占湖泊总面积的 $91 \%$ ；其次是新巴尔虎左旗，面积约 $1 3 7 \mathrm { k m } ^ { 2 }$ ，占湖泊面积的 $6 \%$ ○

按照湖泊面积分等级统计结果表明，小型湖泊数量最多的是新巴尔虎右旗(23个），其次是新巴尔虎左旗(22个)；中型湖泊数量最多的是新巴尔虎左旗(26个），其次是新巴尔虎右旗与陈巴尔虎旗（均14个）；大型湖泊数量最多的是新巴尔虎右旗(3个）,其次是新巴尔虎左旗(2个)。大型湖泊和小型湖泊面积最大的是新巴尔虎右旗(分别为 $2 1 5 2 \mathrm { k m } ^ { 2 }$ 和 $1 6 \mathrm { k m } ^ { 2 } .$ );而中型湖泊面积最大的是新巴尔虎左旗1 $( 4 7 \mathrm { k m } ^ { 2 }$ ）。

# 2.2湖泊数量和面积变化

1986一2017年，呼伦贝尔的湖泊呈现萎缩态势，变化最剧烈的为小型湖泊(图3)，约干涸19个，新增5个；中型湖泊干涸5个;大型湖泊干涸1个（哈达乃浩来湖，呼伦湖东北部的一个附属湖)。分区域分析(表2)，变化较为剧烈的是新巴尔虎右旗和新巴尔虎左旗。其中新巴尔虎右旗小型湖泊干涸10个，新增1个；中型湖泊干涸4个;新巴尔虎左旗小型湖泊干涸6个，中型湖泊干涸1个，大型湖泊干涸1个。

过去 $3 0 \mathrm { ~ a ~ }$ ,小型湖泊面积共减少了 $1 3 . 9 \ \mathrm { k m } ^ { 2 }$ ，约

![](images/75323660327783f349e40ea191724c1258644085d12da71b2aef809b15a353b8.jpg)  
图2研究区湖泊分布图及按照面积大小分类示意图  
Fig.2Lake distribution of the study area and the lake classification based on lake area

58 ar r iturlilr enalrtr lrrrr rre lrr laharr erlr lrtt sensneltrrir   
  
  

<html><body><table><tr><td rowspan="2">区域</td><td rowspan="2">湖泊等级</td><td colspan="2">湖泊数量/个</td><td colspan="2">湖泊面积/km</td><td rowspan="2">干涸湖泊 数量/个</td><td rowspan="2">新增湖泊 数量/个</td><td rowspan="2">湖泊数量 净变化/个</td><td rowspan="2">湖泊数量变化 百分比/%</td><td rowspan="2">湖泊面积 变化/km</td><td rowspan="2">湖泊面积变化 百分比/%</td></tr><tr><td>1986—1990年</td><td>2014—2017年</td><td>1986—1990年</td><td>2014—2017年</td></tr><tr><td>合计</td><td>小</td><td>60</td><td>46</td><td>41.8</td><td>27.9</td><td>19</td><td>5</td><td>-14</td><td>-23.3</td><td>-13.9</td><td>-33.3</td></tr><tr><td rowspan="5"></td><td>中</td><td>62</td><td>57</td><td>130.4</td><td>134.4</td><td>5</td><td>0</td><td>-5</td><td>-8.1</td><td>4.0</td><td>3.1</td></tr><tr><td>大</td><td>6</td><td>5</td><td>2243.6</td><td>2170.3</td><td>1</td><td>0</td><td>-1</td><td>-16.7</td><td>-73.3</td><td>-3.3</td></tr><tr><td>小</td><td>4</td><td>6號</td><td>2.7</td><td>3.5</td><td>0</td><td>2</td><td>2</td><td>50.0</td><td>0.8</td><td>29.6</td></tr><tr><td>中</td><td>14</td><td>14</td><td>36.9</td><td>51.0</td><td>0</td><td>0</td><td>0</td><td>0.0</td><td>14.1</td><td>38.2</td></tr><tr><td>大</td><td>1</td><td>1</td><td>18.4</td><td>18.0</td><td>0</td><td>0</td><td>0</td><td>0.0</td><td>-0.4</td><td>-2.2</td></tr><tr><td rowspan="3">新巴尔虎 右旗</td><td>小</td><td>23</td><td>14</td><td>16.0</td><td>7.3</td><td>10</td><td>1</td><td>-9</td><td>-39.1</td><td>-8.7</td><td>-54.4</td></tr><tr><td>中</td><td>14</td><td>10</td><td>34.6</td><td>15.3</td><td>4</td><td>0</td><td>-4</td><td>-28.6</td><td>-19.3</td><td>-55.8</td></tr><tr><td>大</td><td>3</td><td>3</td><td>2151.5</td><td>2132.3</td><td>0</td><td>0</td><td>0</td><td>0.0</td><td>-19.2</td><td>-0.9</td></tr><tr><td rowspan="3">新巴尔虎 左旗</td><td>小</td><td>22</td><td>16</td><td>15.9</td><td>9.9</td><td>6</td><td>0</td><td>-6</td><td>-27.3</td><td>-6.0</td><td>-37.7</td></tr><tr><td>中</td><td>26</td><td>25</td><td>47.4</td><td>57.3</td><td>1</td><td>0</td><td>-1</td><td>-3.9</td><td>9.9</td><td>20.9</td></tr><tr><td>大</td><td>2</td><td>1</td><td>73.7</td><td>20.1</td><td>1</td><td>0</td><td>-1</td><td>-50.0</td><td>-53.6</td><td>-72.7</td></tr><tr><td rowspan="4">满洲里</td><td>小</td><td>1</td><td>1</td><td>0.5</td><td>0.5</td><td>1</td><td>1</td><td>0</td><td>0.0</td><td>0.0</td><td>0.0</td></tr><tr><td>中</td><td>0</td><td>0</td><td>0.0</td><td>0.0</td><td>0</td><td>0</td><td>0</td><td>0.0</td><td>0.0</td><td>0.0</td></tr><tr><td>大</td><td>0</td><td>0</td><td>0.0</td><td>0.0</td><td>0</td><td>0</td><td>0</td><td>0.0</td><td>0.0</td><td>0.0</td></tr><tr><td>小</td><td>2</td><td>1</td><td>1.6</td><td>1.0</td><td>1</td><td>0</td><td>-1</td><td>-50.0</td><td>-0.6</td><td>-37.5</td></tr><tr><td rowspan="4"></td><td>中</td><td>0</td><td>0</td><td>0.0</td><td>0.0</td><td>0</td><td>0</td><td>0</td><td>0.0</td><td>0.0</td><td>0.0</td></tr><tr><td>大</td><td>0</td><td>0</td><td>0.0</td><td>0.0</td><td>0</td><td>0</td><td>0</td><td>0.0</td><td>0.0</td><td>0.0</td></tr><tr><td>小</td><td>8</td><td>8</td><td>5.1</td><td>5.7</td><td>1</td><td>1</td><td>0</td><td>0.0</td><td>0.6</td><td>11.8</td></tr><tr><td>中</td><td>8</td><td>8</td><td>11.4</td><td>10.8</td><td>0</td><td>0</td><td>0</td><td>0.0</td><td>-0.6</td><td>-5.3</td></tr><tr><td></td><td>大</td><td>0</td><td>0</td><td>0.0</td><td>0.0</td><td>0</td><td>0</td><td>0</td><td>0.0</td><td>0.0</td><td>0.0</td></tr></table></body></html>

70 (a)各类型湖泊数量 5 (b)各类型湖泊数量变化60 11986—1990年 12015—2017年 小50√/鲁 40 √/雪3020 净变化量10 增加数量萎缩数量0 -20小湖泊 中湖泊 大湖泊 小湖泊 中湖泊 大湖泊湖泊类型 湖泊类型

占1986—1990年小湖泊面积的 $3 3 . 3 \%$ ，中型湖泊面积增加了 $4 . 0 \mathrm { k m } ^ { 2 }$ ,约占1986—1990年中型湖泊面积的 $3 . 1 \%$ ,大型湖泊面积减少了 $7 3 . 3 \mathrm { k m } ^ { 2 }$ ,约占1986—1990年大型湖泊面积的 $3 . 3 \%$ ○

# 2.3湖泊年际变化趋势

2.3.1湖泊数量、面积逐年变化为了更细致地研究1986—2017年呼伦贝尔各类型湖泊在数量及面积上的变化特征，本文逐年统计了湖泊的数量及面积。结果显示，32a间湖泊总数量及总面积均显著下降(图4)。按类型统计结果表明，1986—2017年大型湖泊数量减少一个，面积呈现显著下降趋势（204号 $( - 1 3 . 2 \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ $\scriptstyle P < 0 . 0 1 { \dot { } }$ );小型湖泊数量显著减小，每10a大约减少8个；小型湖泊总面积平均每年减小$0 . 7 \mathrm { k m } ^ { 2 }$ ;中型湖泊数量每 $1 0 \mathrm { a }$ 减少3个，但面积变化趋势并不明显。

2.3.2中小型湖泊萎缩和新增个数呼伦贝尔湖泊数量的变化集中体现在中小型湖泊上，因此本文重点关注中小型湖泊数量的萎缩与新增状况。首先将1986—2017年每隔5a划分为1986—1990、1991—1995、1996—2000、2001—2005、2006—2010、2011—2014、2015—2017年7个时间段，然后统计中小型湖泊数量每隔5a的增加、萎缩以及净变化量(图5)。1990s期间中小型湖泊新增数量较多（累计15个），萎缩数量较少（累计1个），净增加14个;2000年后湖泊萎缩数量急剧增加,2001—2010年湖泊个数净减少22个；尽管2010年后，湖泊数量略有增加，但最近几年(2015一2017年)又有减少。

![](images/eb8445c444bb9a3718cae641ac2f917d6921884079e8a77786c4a3a52e306427.jpg)  
干吴区地理  
图31980年代末及2010年代中期各类型湖泊数量及变化  
Fig.3Changes in the numberof lakes of various types and details of specific changes in the late 198Os and mid-20l   
图41986—2017年各类型湖泊数量及面积变化情况  
Fig.4Changes in the number and area of various types of lakes from 1986 to 2017

2.3.3湖泊面积变化的整体趋势以1986—1990年的湖泊面积为基准，利用RWA指数，统计各类型湖泊面积的相对变化情况。总的来说，湖泊面积在2000一2010年快速萎缩，之后略有回升(图6)。具体来看，2000年前各类型湖泊面积均有增加，1998年降水量最大，湖泊面积相应达到峰值；2000—2010年湖泊面积呈萎缩趋势；2010年以后有所回升，2015年后大型湖泊面积依然略有增加，但是中小型湖泊面积有下降趋势。

15 10 5 0 IT1 √/鲁 -5 -10 净变化量 -15 增加数量 -20 萎缩数量 -25 1991—1995 1996—2000 2001—2005 2006—2010 2011—2014 2015—2017 年份

![](images/275828d43401c6830f52f1c82bf3ef19188fe9fc505b4a558bfe7e6484f40b6f.jpg)  
耿晓庆等：内蒙古呼伦贝尔草原湖泊变化研究  
图5研究区中、小型湖泊每5a的数量变化  
图6各类型湖泊面积的年代变化趋势

# 3自然及人为因素对湖泊面积变化的影响

本文分析了1986—2017年呼伦贝尔市的自然因素(降水量、气温、潜在蒸散量)和人为影响因素（原煤产量、放牧强度、有效灌溉面积)等指标的年际变化(图7)，及其对各类型湖泊变化(主要是面积变化)的影响(表3)。本文选取影响湖泊变化的直接因素来分析人类活动对于湖泊的影响。相关研究表明呼伦贝尔露天开采煤矿会破坏埋藏较浅的含水层[27],1t煤的耗水量高达 $2 . 5 \mathrm { ~ t ~ } ^ { [ 2 8 ] }$ 。另外,耕地面积的扩张[29-30]导致灌溉用水增加,加剧了水资源

![](images/6a73301845ed7bb6110f004e886ac89a6c4f889c9db5277e3834edf2b198840d.jpg)  
Fig.5Changes in the number of small and medium lakes in the study area every 5 years   
Fig.6Temporal changes in relative water area (RWA,in percent) for various types of lakes   
图71986—2017年呼伦贝尔气候及人类活动变化情况  
Fig.7Changes of climate and human activities in Hulun Buir from 1986 to 2017

# 干旱区地理

表3各湖泊面积与气候变化、人类活动相关性统计分析  
Tab.3 Statistical analysis between lake area and climate change and human activity   

<html><body><table><tr><td rowspan="2">因素类型</td><td colspan="2">小湖泊面积</td><td colspan="2">中湖泊面积</td><td colspan="2">大湖泊面积</td><td colspan="2">总湖泊面积</td></tr><tr><td>SS/%</td><td></td><td>SS/%</td><td>r</td><td> SS/%</td><td></td><td>SS/%</td><td>1</td></tr><tr><td>降水量</td><td>35.40**</td><td>0.42*</td><td>34.10*</td><td>0.34</td><td>0.70</td><td>0.10</td><td>2.40</td><td>0.16</td></tr><tr><td>气温</td><td>0.04</td><td>-0.06</td><td>2.60</td><td>-0.14</td><td>14.30**</td><td>0.23</td><td>11.30**</td><td>0.19</td></tr><tr><td>潜在蒸散量</td><td>4.90</td><td>-0.29</td><td>9.90</td><td>-0.03</td><td>16.20**</td><td>-0.27</td><td>12.90**</td><td>-0.26</td></tr><tr><td>原煤产量</td><td>24.10**</td><td>-0.39</td><td>0.90</td><td>-0.01</td><td>32.10**</td><td>-0.60**</td><td>31.10**</td><td>-0.57**</td></tr><tr><td>有效灌溉面积</td><td>31.20**</td><td>-0.63**</td><td>38.50*</td><td>-0.17</td><td>29.10**</td><td>-0.79**</td><td>33.50**</td><td>-0.77**</td></tr><tr><td>放牧强度</td><td>1.40</td><td>-0.67**</td><td>3.80</td><td>-0.27</td><td>6.70*</td><td>-0.81**</td><td>6.80*</td><td>-0.80**</td></tr><tr><td>残差</td><td>2.90</td><td>0.42*</td><td>10.00</td><td>0.34</td><td>1.70</td><td>0.10</td><td>2.00</td><td>0.16</td></tr></table></body></html>

注：\*表示 $P { < } 0 . 0 5$ ；\*\*表示 $P { < } 0 . 0 1$ ;SS表示变量的方差贡献率;r表示相关系数。

的短缺，造成湖泊面积的衰减。

从自然因素方面看，1986—2016年降水量整体变化不显著，但在2001—2010年，降水量相对较低，这10a的湖泊面积和数量也急剧下降;年均温略有上升,但趋势不显著;而潜在蒸散量增加趋势显著，呼伦贝尔气候的暖干性较为明显[14]。从人为因素方面看，2000年以后，呼伦贝尔市辖区的工业、农业、畜牧业取得了迅猛发展，加速了自然资源的消耗，尤其是加大了水资源供给压力。呼伦贝尔市的原煤产量自2000年开始，出现猛增，2013年达到最大值，之后开始减少，但产量依然保持较高水平。有效灌溉面积、放牧强度在2000年以后也迅速增加，之后虽有波动，但基本保持较高水平上。

利用相关分析及线性回归分析定量描述上述各因素对各类型湖泊面积变化的贡献(表3)，结果表明：中、小湖泊面积的变化，降水量分别解释了 $34 \%$ 和 $3 5 \%$ ,其次是有效灌溉面积,解释了 $3 8 \%$ 和 $3 1 \%$ ·而原煤产量对大湖泊面积的变化解释率最高$( 3 2 \% )$ )，有效灌溉面积其次（ $2 9 \%$ )，潜在蒸散量和气温分别解释 $1 6 \%$ 与 $14 \%$ 。这与前人针对内蒙古省区尺度大型湖泊的研究结果一致[9]。整体看来，中小型湖泊的面积变化的影响因素主要是有效灌溉面积与降水量，原煤的开采在一定程度上影响了小湖泊的消亡，但对中湖泊面积的变化影响不大;而大湖泊面积的变化主要受原煤产量及有效灌溉面积的影响，增温在一定程度上加剧了湖泊面积的减少。由此看来，该地区湖泊面积的萎缩更大程度上受人类活动的影响[9.31-32],而气候暖干性趋势加剧了这一变化。

# 4小结

本文利用1986—2017年Landsat卫星数据研究了呼伦贝尔市湖泊面积和数量变化，结果表明：近30a该市湖泊数量及面积均呈下降趋势，尤其是小湖泊个数变化颇为剧烈，干涸19个，面积减少超过$30 \%$ ;大湖泊中仅有一个出现干涸，中湖泊有5个出现干涸,但面积变化不显著。具体来看,2000年前各类型湖泊面积均有增加，1998年降水量最大，湖泊面积相应达到峰值；2000一2010年湖泊面积呈萎缩趋势；2010年后有所回升。统计分析表明，湖泊面积变化受人类活动影响较大，尤其是土地利用类型变化带来的农业用地面积和灌溉用水的增加，是导致中小湖泊数量下降和面积减少的主要原因；同时原煤开采消耗地下水，也会造成湖泊的干涸。此外，整个区域气候暖干化趋势明显，是导致湖泊萎缩的另一个重要因素。因此，产业结构的调整，新型的灌溉方式，以及更为规范的煤炭开采形式，是呼伦贝尔湖泊保护工作的重要途径。

致谢：研究工作得到北京大学的陶胜利博士帮助，表示衷心感谢。

# 参考文献(References)

[1]赵澍,冀玮强,高鹏,等.1986—2016年呼伦湖水域面积动态变 化及与气候因素关系研究[J].中国农业资源与区划,2018,39 (4): 53-58.[Zhao Shu,Ji Weiqiang,Gao Peng,et al. Study on dynamic change of Hulun Lake water area and the relationship with the climatic factors during 1986—2O16[J].Chinese Journal of Agricultural Resources and Regional Planning,2018,39(4): 53-58.]   
[2] Ma R H, Yang G H,Duan H T,et al. China's lakes at present: Number,area and spatial distribution[J]. Science China-Earth Sciences,2010,54(2): 283-289.   
[3] Xie P,Chen YY.Threats to biodiversity in Chinese inland waters [J]. Ambio, 1999,28(8): 674-681.   
[4] 张玉静,杨秀春,郭剑,等.呼伦贝尔草原物候变化及其与气象 因子的关系[J].干旱区地理,2019,42(1):144-153.[Zhang Yujing,Yang Xiuchun,Guo Jian, et al.Phenological variation and its relationship with meteorological factors in Hulun Buir grasslands [J]. Arid Land Geography,2019,42(1): 144-153.]   
[5]封建民,王涛.呼伦贝尔草原沙漠化现状及历史演变研究[J].干 旱区地理,2004,27(3):356-360.[Feng Jianmin,Wang Tao.Study on the actualtyand historical evolution of desertification in the Hulun Buir grassands[J].Arid Land Geography,2004,27(3): 356- 360.]   
[6]叶佳琦,李政海,乌云其其格,等.呼伦贝尔草原、湿地和森林植 被对气候变化的响应[J].中国草地学报,2018,40(6):26-32. [Ye Jiaqi,Li Zhenghai,Wu Yunqiqige,et al. The response of steppe,wetland and forest vegetation to climate change in Hulun Buir[J]. Chinese Journal of Grassland,2018,40(6): 26-32.]   
[7]Addison J,Friedel M,Brown C,etal.Acritical review of degradation assumptions applied to Mongolia's gobi desert[J].Rangeland Journal,2012,34(2): 125-137.   
[8]代海燕,李丹,娜日苏,等.内蒙古干湿环境演变与地区生态建 设优势气候背景分析[J].干旱区地理,2019,42(4):745-752. [Dai Haiyan,Li Dan,Na Risu,et al. Dry and wet environment evolution and climatic background analysis of regional ecological constrction in Inner Mongolia[J].Arid Land Geography,2019,42(4): 745-752.]   
[9]Tao SL,Fang JY,Zhao X,et al. Rapid loss of lakes on the Mongolian Plateau[J].Proceedings of the National Academy of Sciences of the United States of America,2015,112(7): 2281-2286.   
[10] 杨会彩,姜明媛,阿膺兰,等.呼伦湖自然保护区土地利用及景 观格局变化研究[J].北京师范大学学报(自然科学版),2013,49 (增刊1): 318-325.[Yang Huicai,Jiang Mingyuan,A Yinglan,et al. Changes in land use and landspace patern in Hulun Lake Nature Reserve[J].Journal of Beijing Normal University (Natural Science),2013,49(Suppl. 1): 318-325.]   
[11] 褚永海,李建成,姜卫平,等.利用Jason-1数据监测呼伦湖水位 变化[J].大地测量与地球动力学,2005,25(4):11-16.[Chu Yonghai,Li Jiancheng,Jiang Weiping,etal.Monitoring of water level variations of Hulun Lake with Jason l altimertic data[J]. Journal of Geodest and Geodynamics,2005,25(4): 11-16.]   
[12]Li S, Chen J, Xiang J,et al. Water level changes of Hulun Lake in Inner Mongolia derived from Jason satelite data[J]. Journal of Visual Communication and Image Representation, 2019,58: 565-575.   
[13]Hu S,Wang S,Appel E,et al. Environmental mechanism of magnetic susceptibility changes of lacustrine sediments from Lake Hulun,China[J]. Science in China Series D: Earth Sciences,2000,43 (5): 534-540.   
[14] 赵慧颖,乌力吉,郝文俊.气候变化对呼伦湖湿地及其周边地区 生态环境演变的影响[J].生态学报,2008,28(3):1064-1071. [Zhao Huiying,Wu Liji,Hao Wenjun.Influences of climate change to ecological and environmental evolvement in the Hulun Lake wetland and its surrounding areas[J].Acta Ecologica Sinica, 2008, 28(3): 1064-1071.]   
[15] 任俊娴,陈红兵,柯杰,等.天然湿地在湖泊生态系统保护中的 研空讲展m 湖南生太私学学报 2018 5/1).52-57 [Ran Inv

ian, Chen Hongbing,Ke Jie,et al.Advance of natural wetlands in lake ecosystem protection[J]. Journal of Hunan Ecological Science,2018,5(1): 52-57.]   
[16]Jones S,FremierA,Declerck F,et al. Big data and multiple methods for mapping smal reservoirs: Comparing accuracies for applications in agricultural landscapes[J]. Remote Sensing, 2017,9 (12): 1307,doi: 10.3390/rs9121307.   
[17]Thornthwaite C W,Hare F K. Climatic classification in forest[J]. Unasylva,1955,9(2): 51-59.   
[18] 张新时.植被的PE(可能蒸散)指标与植被-气候分类(二)—几 种主要方法与PEP程序介绍[JJ.植物生态学与地植物学学报, 1989,13(3): 197-207.[Zhang Xinshi. The potential evapotranspiration (PE) index for vegetation and vegetation-climatic classification(2):An introduction of main methods and PEP program[J]. Acta Phytoecologica et Geobotanica Sinica,1989,13(3):197-207.]   
[19]Fang JY,Yoda K. Climate and vegetation in China V.Effect of climatic factors on the upper limit of distribution of evergreen broadleaf forest[J]. Ecological Research,1991,6(1): 113-125.   
[20] 内蒙古自治区统计局.内蒙古统计年鉴[M].北京:中国统计出 版社,1986—2017.[Inner Mongolia Autonomous Region Statistics Bureau.Inner Mongolia statistical year book[M].Beijing: China Statistics Press,1986—2017.]   
[21] 程磊,徐宗学,左德鹏,等.基于Landsat TM数据的黄土高原区 水体识别方法研究[J].北京师范大学学报(自然科学版),2010, 46(3): 424-430.[Cheng Lei, Xu Zongxue, Zuo Depeng, et al. Identification of water bodies in the Loess Plateau based on Landsat TMdataset[J]. Journal of Beijing Normal University (Natural Science),2010,46(3): 424-430.]   
[22]MacFeeters S K. The use of normalized difference water index (NDWI) in the delineation of open water feature[J]. International Journal of Remote Sensing,1995,17(7): 1425-1432.   
[23]Fang JY,Wang Z H, Zhao S Q,et al.Biodiversity changes in the lakes of the central Yangtze[J].Frontiers in Ecology& the Environment,2006,4(7): 369-377.   
[24] 马超,刘玮玮,赵鹏飞,等.1962—2016年达里诺尔流域水、草 退化及气候响应[J].地理研究,2017,36(9):1755-1772.[Ma Chao,Liu Weiwei, Zhao Pengfei,etal. Wetlandand grasslandegradation and the response to climate in Dalinor Basin during 1962—2016[J]. Geographical Research,2017,36(9):1755- 1772.]   
[25] 中国科学院南京地理与湖泊研究所.中国湖泊分布地图集[M]. 北京：科学出版社,2015.[Nanjing Institute of Geography & Limnology,Chinese Academy of Sciences. Chinese lake distribution atlas[M]. Beijing: Science Press,2015.]   
[26] 牧寒.内蒙古湖泊[M].呼和浩特:内蒙古人民出版社,2003. [Mu Han.Inner Mongolia lake[M]. Hohhot: Inner Mongolia People Publishing Press,2003.]   
[27] 马秀芬,翟立娟,傅耀军,等.鄂尔多斯盆地煤炭基地含水层及 其保护研究[J].中国煤炭地质,2012,24(8):36-42.[Ma Xiufen, Zhai Lijuan,Fu Yaojun,et al.A study on aquifers and their protection in Ordos Basin coal base[J]. Coal Geology of China,2012,24 (8): 36-42.]

# 干吴区地理

[28]李强,李永春,陈大勇,等.神东矿区水资源可持续利用问题研究[J].干旱区资源与环境,2013,27(9):141-147.[LiQiang,LiYongchun,Chen Dayong,et al.The water resource utilization inShendong mining area[J]. Journal of Arid Land Resources and En-vironment,2013,27(9): 141-147.]  
[29]王治良,路春燕.呼伦贝尔草原区土地利用及景观格局变化特征分析[J].干旱区资源与环境,2015,29(12):91-97.[Wang Zhil-iang, Lu Chunyan. Dynamic change of land use and landscape pat-tern in Hulun Buir grassland, China[J]. Journal of Arid Land Re-sources and Environment,2015,29(12): 91-97.]  
[30]张德平.内蒙古呼伦贝尔市土地利用现状及变化分析[J].中国

土地科学,2011,25(11): 43-48.[Zhang Deping.Analysis on the current status and the changes of land use in Hulun Buir Inner Mongolia[J]. China Land Science,2011,25(11): 43-48.]   
[31] 张浩然,清华,刘华民,等.呼伦湖湖泊动态变化及其驱动力分 析[J].内蒙古大学学报(自然科学版),2018,49(1):102-107. [Zhang Haoran,Qing Hua,Liu Huamin,et al.Dynamics and its driving forces of Hulun Lake[J].Journal of Inner Mongolia University (Natural Science Edition),2018,49(1): 102-107.]   
[32]Niu ZG, Zhang HY,Wang X W,et al. Mapping wetland changes in China between 1978 and 2Oo8[J]. Chinese Science Bulletin, 2012,57(22): 2813-2823.

# Three-decadal changes of lakes in Hulun Buir grasslands, Inner Mongolia

GENG Xiaoqing'， HU Zhaomin'， ZHAO Xia'， SHEN Haihua'， FANG Jingyun1,2(1.State KeyLaboratoryof VegetationandEnvironmental Change,InstituteofBotany,Chinese Academyof Sciences,Beijing10o093,China；2.Collgeof UrbanandEnvironmental Science,Peking University,Beijing100871,China)

Abstract: Lakes are important water reservoirs that play an important role in water supply and climate regulation,especially in arid regions.A large number of lakes are distributed across the Hulun Buir grasslands, which account for as high as $58 \%$ of the total area of lakes in Inner Mongolia, China. Subjected to significant climate change and intensive anthropogenic activities,lakes in the Hulun Buir grasslands have shrunk significantly. Shrinkage of the lakes in this region may accelerate grassand degradation and reduce the lakes’ecosystem services.However,long-term changes in the number and area of these lakes,especially the small ones $( < 1 \ \mathrm { k m } ^ { 2 } )$ ， are poorly understood. Using the Landsat data (TM,ETM+,and OLI),in this study, we asessthe changes inthe number and area of lakes and their drives in Hulun Buir between 1986 and 2017.The assessment especially focuses on smallakes because they are more sensitive to environmental changes and have more widespread influences on livestock production compared to large lakes.We first used Google Earth Engine to analyze the Landsat surface reflectance data and extract the water body coverage of the lakes based on the normalized diferential water index.Then,we explored the changes in the lakes and their possble driving forces over the past three decades.The results showed a significant shrinkage in the lake area during the last three decades with the most dramatic change occurring in small lakes. Specifically, the number and area ofsmall and large lakes showed a significant decrease,whereas the decline in the area of medium-sized lakes was insignificant.The temporal change in the area of the lakes was nonlinear,showing an increase before 2OoO and a decrease after 2Ooo.A correlation analysis of the regional changes in the lake area with climatic factors (temperature,precipitation,and potential evapotranspiration)and human factors (grazing,mining,and irrigation)indicated that the areal shrinkage of small lakes was mainly due toan increase in the cropland area and water consumption by irigation and that the impacts of climate change is relatively minor. The decrease in the area of large lakes was mainly caused by water consumption because ofcoal mining.In addition,the warmer and drier climate contributes to the shrinkage in the lakes’area.Due to an increase in the area of agricultural land and exploitation of groundwater for coal mining, water consumption in this region stayed at a high level.The findings ofthis study recommend the optimization of industrial structure,upgrading of irigation systems,and improvement ofcoal mining technology to protect lakes from further shrinkage and achieve a sustainable supply of water resources.

Key words:ake；Landsat; area change; number change； Hulun Buir