# 基于MODISTVDI和模糊数学方法的藏北地区旱情等级遥感监测

刘一哲'，冯文兰¹，扎西央宗²，梁丽'，李潼'(1.成都信息工程大学资源环境学院,四川 成都610225；2．西藏自治区气候中心,西藏 拉萨850000）

摘要：为了实现对藏北区域范围内春夏旱情的动态连续监测,基于温度植被干旱指数(TVDI)和模糊数学方法建立了遥感干旱的划分标准,研究时段为1980—2017年。首先利用 MODIS 产品数据计算TVDI,然后根据气象干旱等级监测结果,采用模糊数学法建立基于MODIS TVDI的干旱等级划分标准，并对监测结果进行精度验证,最后分析了近年来藏北地区旱情的时空变化特征。得到的主要结论： $\textcircled{1}$ 基于归一化植被指数(NDVI)和增强植被指数(EVI)计算得到的温度植被干旱指数 $\mathrm { \Delta T V D I _ { N } }$ 和 $\mathrm { T V D I _ { E } }$ ,均与 $2 0 ~ \mathrm { c m }$ 实测土壤水分含量在0.05的水平达到显著相关， $\mathrm { T V D I _ { E } }$ 的决定系数更高； $\textcircled{2}$ 基于 $\mathrm { \Delta T V D I _ { E } }$ 将旱情划分为无旱、轻旱、中旱、重旱、特旱5个等级，其中,据此标准获得的藏北地区旱情等级与气象干旱等级监测结果大体一致； $\textcircled{3}$ 近年来藏北地区旱情整体不太严重，且总体趋缓，其中,2009年最严重，发生中旱及以上旱情的区域面积达 $2 4 \%$ ,年内旱情在6月最严重。就旱情的空间分布特征而言,研究区西南部和中部干旱比较严重,北部和东南部相对较轻。研究成果可为藏北地区干旱监测提供数据支撑，遥感干旱等级的划分方法可为其他地区的干旱研究提供参考。

关键词：温度植被干旱指数；模糊数学法；干旱等级；MODIS；藏北地区

旱灾是我国最严重的自然灾害之一，长时间较为严重的干旱不仅直接影响农业生产、社会经济，而且还会出现河水断流、绿洲缩减、土壤荒漠化、沙尘暴增多等衍生灾害[1]。旱灾是西藏最严重的农业气象灾害之一[2],每年均有不同程度的发生，对农牧业生产的影响极大[3]。然而,由于西藏高原基础台站观测资料不足，给干旱监测带来许多困难。在全球气候变暖的背景下，极端干旱的面积不断扩大，西藏西南部干旱发生频率较高[4]。因此,开展藏北地区的干旱动态监测具有重要的现实意义。

遥感技术为大范围、长时间序列的干旱监测提供了有效的手段[5]。大量研究表明,温度植被干旱指数(TVDI)模型能较好地反映大范围的土壤水分状况[。这种方法在我国的适用性也得到了广泛的证明，如薛天翼等研究表明，土壤相对湿度和降水量数据与TVDI都呈明显的负相关。近年来，不少学者对TVDI监测土壤水分进行了发展和改进，改进后的TVDI监测干旱效果更好。王行汉等[8]基于增强植被指数对华南农业旱情进行遥感监测，结果能够准确地体现出不同等级旱情的空间区域分布状况。杨秀海等[9 曾成功地采用温度植被干旱指数(TVDI)评价了青藏高原的旱情，宋春桥等[亦采用TVDI对于藏北的土壤湿度分布进行了研究。

为准确把握干旱对农牧业生产的实际影响，干旱监测需要对旱情的严重程度进行准确的评估。基于遥感于旱指数TVDI进行旱情等级的估算，TVDI分级标准人为性很大，从当前发表的文献中可以看到不同研究中TVDI的分级标准不尽相同(1]。目前多采用经验方法,如自然断点法[12]。显然,这种估算方法未考虑到干旱等级在区域中的适用性，因此，有必要科学地建立干旱等级的区域标准。关于干旱等级评估的标准，尽管监测方法和指标众多，但气象部门普遍认为基于降水距平获得的干旱等级评估结果更加符合实际情况。因而，在气象业务工作中多采用基于降水距平率的干旱等级标准。为此，参考气象干旱监测的结果，建立基于遥感干旱指数的干旱等级划分标准，并用于旱情的监测与分析，对于及时获取藏北地区区域尺度的旱情分布及发展情况具有重要的意义。

根据模糊数学的隶属度理论可对受到多种因素制约的事物或对象作出一个总体的评价。它具有结果清晰，系统性强的特点，能较好地解决模糊的、难以量化的问题,适合各种非确定性问题的解决[13]李祚泳[14]利用规范值表示的湖泊富营养化指标（即指标总体)用同一个“等效”规范指标代替，继而采用模糊数学地方法成功地划分了湖泊富营养化的评价标准，并在福州市山仔水库水质监测上取得了很好的效果。在遥感干旱等级的评价中，TVDI可被视为一个综合的干旱监测指标，依据降水距平获得的干旱等级结果可作为参考的标准，利用TVDI建立干旱等级的划分特征满足模糊数学使用标准。因此，本文拟采用模糊数学方法建立藏北地区基于TVDI的干旱等级划分标准，以期在藏北地区建立更加符合客观事实的干旱等级的监测方法和标准，为气象部门更好地服务于农牧业生产提供科学依据，也为其他区域建立基于遥感指数的旱情等级监测提供方法的借鉴。

# 数据基础与方法

# 1.1 研究区概况

藏北地区是指我国西藏范围内介于 $7 8 ^ { \circ } 2 3 ^ { \prime } 4 0 ^ { \prime \prime } \sim$ $9 5 ^ { \circ } 1 0 ^ { \prime } 4 6 ^ { \prime \prime } \mathrm { E } , 2 9 ^ { \circ } 4 0 ^ { \prime } 4 0 ^ { \prime \prime } \sim 3 5 ^ { \circ } 4 2 ^ { \prime } 5 5 ^ { \prime \prime } \mathrm { N }$ 之间的区域（图1)。该区平均海拔 $4 ~ 5 0 0 ~ \mathrm { { \ m } }$ ，气候寒冷干燥，年降水量 $2 4 7 . 3 \sim 5 1 3 . 6 ~ \mathrm { m m }$ 。降水东南多，西北少，且季节性强，时空分布不均。受地形和气候分异的影响，植被类型由东南到西北依次是亚高山疏林一灌丛草甸、高寒草甸、高寒草原、高寒荒漠草原4大基带及相邻的过渡亚带。区内拥有广阔的天然草地资源，各类天然草地面积占到全区总面积的 $8 0 \%$ ，占西藏天然草地面积的 $5 9 \%$ ，因而是西藏重要的畜牧业生产基地[15]。根据宋春桥等[10]的研究成果,受水平和垂直地带性气候的影响，藏北地区水热和气候条件差异很大，因而，全区可分为昆仑高山高原亚寒带十旱区、羌塘高原湖盆亚寒带半十旱区、青南高原亚寒带干旱区和那曲高山谷地高原亚寒带半湿润区4个气候区(图1a）。该区域的旱情主要发生在春、夏两季[16]。特别是2009 年人夏以来,西藏降水量偏少，气温持续偏高，西藏出现大面积中度旱情，部分地方出现了30年一遇的气象干旱。受高原地形的限制，全区的气象站数量稀少且分布不合理（图1b)，难以为农牧业提供准确全面的气象干旱数据支持。

# 1.2 数据与处理

使用MODIS产品组按照统一算法研发的MOD13A2全球 $1 ~ \mathrm { k m }$ 分辨率植被指数 $1 6 \mathrm { ~ d ~ }$ 合成产品和 MOD11A2全球 $1 ~ \mathrm { k m }$ 分辨率地表温度8d合成L3产品。数据的时间为2002—2018年每年的3—8月，所用区域标识为h24v05、 $\mathtt { h 2 5 v 0 5 }$ 、 $\mathrm { h } 2 5 \mathrm { v } 0 6$ 、$\mathtt { h } 2 6 \mathrm { v } 0 5$ 。其中,植被指数产品包含 NDVI、EVI产品,通过 NASA 提供的 MODIS Reporjection Tool(MRT)读取文件、拼接、投影，并通过S-G滤波17 降噪处理后生成TIF格式的植被指数影像。温度产品取平均方法合成16d数据[18]

为验证MODISTVDI对旱情的监测能力，分别于2015年8月和2016年6月利用FieldScoutTDR土壤水分计在实地采集获取藏北地区 $2 0 ~ \mathrm { c m }$ 土壤水分含量，采样点分布如图1a所示。实地采集土壤水分数据时，以 $1 \ \mathrm { k m } \times 1 \ \mathrm { k m }$ 为样方，每个样方按照 S形间隔，取10个土壤水分实测值，取平均值作为该采样点的土壤水分体积含量。

![](images/9a8ffbcb9324983291eb9eaaccdf03ce9b10c96d047c7808aed4d37e669a680c.jpg)  
图1藏北地区基本情况  
Fig.1Basic situation in north Tibet

藏北地区国家站和自动站(图1b)的月降水量数据由西藏高原气象研究所提供，数据格式为.txt的文本格式，时间为1980一2015年，用于计算旱情等级的参考标准和评估结果的验证。其中，由于9个国家站建站时间较长，且为人工监测站，数据准确，因此，利用国家站的数据计算出36a内3—8月的月平均降水量，再计算研究时段内月降水距平百分率,据此获得站点所在区域的气象干旱等级。自动站的数据时间较短，剔除异常值处理后，用于对遥感旱情等级监测的结果准确性验证。

# 1.3 研究方法

1.3.1温度植被指数的计算先用 MODIS 植被指数(NDVI)和增强植被指数(EVI)分别与MODIS陆表温度(LST)建立TVDI,然后通过实测 $2 0 ~ \mathrm { c m }$ 土壤水分验证两种TVDI监测的精度，选取更优数据。考虑到藏北地区植被稀疏、返青期和生长期较短，为此，计算时将植被指数在0以上的MODIS数据全部参与干湿边拟合。应用经过S-G滤波平滑降噪处理后的NDVI、EVI以及LST预处理后的产品数据，按照每个时期的干湿边方程系数，反演求得所有像元的TVDI值。

1.3.2基于TVDI的干旱标准划分方法考虑到研究区内气候特征的空间差异和气象站点的分布情况，首先将研究区分为半湿润区和半干旱区两部分[10]。其中,图1中的那曲高山谷地高原亚寒带半湿润区归为半湿润区，其余3个气候区为半干旱区。然后，采用模糊数学法对两部分分别建立各自的干旱等级标准，基本步骤包括：第一，确定被评价对象的因素集，其中，因素集为刻画评价对象的各种评价因素，在这里是9个国家站所在栅格的降水距平百分率等级和TVDI值。为了使干旱标准具有代表性，本文取2002—2014年的降水距平百分率和 TV-DI平均值用于构建因素集;第二,确定评语集，评语集是评价者对被评价对象可能作出的各种总的评价结果组成的评语等级的集合，依据气象干旱等级的标准,评语集为无旱、轻旱、中旱、重旱、特旱;第三，将TVDI干旱分级特征向量归一化确定评价对象的权重向量：

$$
X _ { i } ^ { * } = \frac { X _ { i } } { X _ { 1 } + X _ { 2 } + \cdots + X _ { n } }
$$

式中： $\boldsymbol { X } _ { i } ^ { * }$ 表示归一化后第 $i$ 个特征向量值; $X _ { i }$ 表示第 $\mathbf { \chi } _ { i }$ 个特征向量值， $i = 1 , 2 , \cdots , n$ 。本研究中 $n = 4$ 。

其次，依据不同干旱指标等级的常规分级标准，进行各类指标评价函数设计；然后，根据评价函数以及评价矩阵，计算模糊隶属度，即得到模糊关系矩阵R[19]。

$$
R = { \left| \begin{array} { l l l l } { r _ { 1 1 } } & { r _ { 1 2 } } & { \cdots } & { r _ { 1 n } } \\ { r _ { 2 1 } } & { r _ { 2 2 } } & { \cdots } & { r _ { 2 n } } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { r _ { m 1 } } & { r _ { m 0 } } & { \cdots } & { r _ { m n } } \end{array} \right| }
$$

式中： $r _ { m n }$ 表示某个被评价对象从综合指标 $\boldsymbol { u } _ { m }$ (TV-DI)来看对等级模糊子集 $\boldsymbol { v } _ { n }$ 的隶属度,这里 $\boldsymbol { v } _ { n }$ 为气象干旱等级。

最后，将模糊关系矩阵与因素的权重矢量进行模糊运算,得到模糊综合评价结果[20] ○

$$
B = X \times R
$$

式中： $B$ 为得到的TVDI等级值; $X$ 为归一化确定评价对象的权重向量集。

1.3.3干旱等级划分标准的检验利用研究区23个自动站(图1b)2010—2017年的数据计算气象降水距平率评估干旱等级，并与其所在栅格的同期遥感干旱等级监测结果进行对比，以验证遥感旱情等级监测结果的正确性。需要指出的是，由于研究区北部的昆仑高山高原亚寒带半干旱区和东北部的青南高原亚寒带半干旱区缺少气象站点数据,其监测结果不能准确订正。但由于两个区域的气候特征与羌塘高原湖盆亚寒带半干旱区中北部和东北部相似，地理位置上前者距狮泉河、改则气象站点较近，后者与双湖、扎仁气象站相近，故认为本研究所建立的半干旱区的干旱等级划分标准适用于该区域。另外,那曲高山谷地高原亚寒带半湿润区以及羌塘高原湖盆亚寒带半干旱区南部的普兰县所在区域，由于降水较多，气候相对湿润，故采用半湿润区的干旱等级划分标准。

# 2结果与分析

# 2.1 TVDI模型的建立与验证

2.1.1植被指数一温度特征空间图2为2017 年3—8月每个月第2期NDVI-LST与EVI-LST特征空间与干湿边方程，由图2可以看出，研究区植被指数一地表温度特征空间的特点： $\textcircled{1}$ 特征空间呈现出三角形，干边斜率小于0,说明随着植被的增加，最大值呈减小趋势； $\textcircled{2}$ 当NDVI数值超过某一阈值时，近地表温度的最大值随着NDVI数值的增加不断降低，而最小值却不断增加，因此，干边方程拟合效果优于湿边方程; $\textcircled{3}$ NDVI和EVI两种数据源的散点分布大体相同，但NDVI范围主要集中在 $0 \sim$ 0.8,EVI范围则集中在 $\textstyle 0 \sim 0 . 6 ; \textcircled { 4 }$ 基于增强植被指数(EVI)得出的拟合系数高于同时期植被指数NDVI,因而整体上EVI数据拟合结果精度较好。 $\textcircled{5}$ 在3月、4月和5月植物生长初期，LST与EVI存在正相关关系，6月、7月和8月时，LST与EVI相关关系为负。

![](images/425216c610995d5a503659b02c54ef0833d1eb1486d4b28e37016503d0d2cdae.jpg)  
注： $T _ { s }$ 为像元地表温度值。  
图22017年 MODIS NDVI-LST和EVI-LST特征空间Fig.2Feature space of MODIS NDVI-LST（left）and EVI-LST（right）in 2017

在植物生长受能量或温度作为主要限制因子时，LST与EVI呈正相关关系，在植物生长受水分作为主要限制因子时,LST与 NDVI呈负相关关系[21]故本文选取6一8月对藏北干旱进行研究。

2.1.2TVDI模型的验证性评价根据前人研究TVDI与土壤水分含量的验证结果,TVDI与 $2 0 \ \mathrm { c m }$ 土壤水分的相关性最佳(22]。据此,本文利用 2015年和2016年实测 $2 0 \ \mathrm { c m }$ 土壤水分与同期反演得到的TVDI进行相关性分析，以检验TVDI对土壤含水量的表达能力。

分别以 $\mathrm { \Delta T V D I _ { N } }$ （基于NDVI计算得到）和 $\mathrm { \Delta T V D I _ { E } }$ (基于EVI计算得到)为横坐标，实测 $2 0 \ \mathrm { c m }$ 土壤水分为纵坐标，制成散点图（图3）。从图3中可以看出，两种指数反演的TVDI与实测 $2 0 \ \mathrm { c m }$ 土壤水分的相关性都达到了0.05的显著性标准。其中，$\mathrm { \Delta T V D I _ { E } }$ 与实测 $2 0 ~ \mathrm { c m }$ 土壤水分的相关系数高于 TV-$\mathrm { D I } _ { \mathrm { N } }$ 与实测 $2 0 ~ \mathrm { c m }$ 土壤水分的相关系数。该结果进一步反映出基于增强植被指数(EVI)与地表温度计算得到的 $\mathrm { \Delta T V D I _ { E } }$ 更适用于藏北地区的干旱监测。

# 2.2基于模糊数学方法的干旱等级划分

2.2.1干旱等级划分标准的建立采用模糊数学的方法，建立基于 $\mathrm { \Delta T V D I _ { E } }$ 干旱等级的标准,具体过程如下：

（1）确定评价对象因素(指标)集 $U = \left\{ \begin{array} { l l } { \begin{array} { r l r } \end{array} } \end{array} \right.$ 降水距平率等级、 $\mathrm { T V D I _ { E } }$ ；这里的降水距平率等级是根据国家站6一8月的月平均降水量数据计算得到，等级标准根据《GBT20481—2006气象干旱等级》划分为无旱、轻旱、中旱、重旱和特旱。 $\mathrm { \Delta T V D I _ { E } }$ 为气象数据同期站点所在栅格的 $\mathrm { \Delta T V D I _ { E } }$ 平均值。为了使模型具有通用性，对2002—2014 年每年得到TVDI求平均值作为最终评价矩阵的结果。

（2）确定评价对象评语集 $\begin{array} { r } { V = \left\{ \begin{array} { l l } \end{array} \right. } \end{array}$ 无旱、轻旱、中旱、重旱、特旱。

（3）利用降水距平百分率按照《GBT20481—2006气象干旱等级》得到5级干旱等级的气象干旱分级结果，再统计同一分级结果对应的所有 $\mathrm { T V D I _ { E } }$ 均值。考虑到热量是高海拔地区春季植物的生长限制因子,此时LST与EVI存在正相关关系，TVDI不适合干旱监测[21]，故只选取夏季6—8月每个月按降水等级统计对应 $\mathrm { \Delta T V D I _ { E } }$ 均值，最后组成评价矩阵(表1)。

（4）根据模糊数学的方法,设 $\boldsymbol { X } = \left( \begin{array} { l } { x _ { 1 } , x _ { 2 } , \cdots , } \end{array} \right.$ $x _ { m }$ )为权重(权数)分配模糊矢量，其中 $\boldsymbol { x } _ { i }$ 表示第 $\mathbf { \chi } _ { i }$ 个因素的权重，要求 $x _ { i } > 0 , \Sigma x _ { i } = 1$ 。这里的因素权重指常规TVDI干旱分级标准 $0 . 4 0 \AA . 0 . 6 0 \AA . 0 . 7 5 、$ $0 . 8 6 ^ { [ 2 3 ] }$ ,将它们归一化后得到评价对象的权重向量$X = ( 0 . 1 5 , 0 . 2 3 , 0 . 2 9 , 0 . 3 3 )$ 。

（5）指标评价函数的设计如表2所示，其中，建立2个气候区的标准时采用相同的评价函数。

（6）根据评价函数构建评价矩阵，计算模糊隶属度，即得到模糊关系矩阵，分别获得半湿润区和半干旱区2个模糊隶属度矩阵(表3）。

（7）计算得到阈值向量，建立藏北地区MODIS$\mathrm { \Delta T V D I _ { E } }$ 干旱等级划分标准，具体结果如表4所示。2.2.2标准的适用性讨论与验证气象干旱是指降水与蒸散收支不平衡造成的异常水分短缺现象，

![](images/6fc21a77235e958c42a67effac2ec4e8503e77c1ce9f641b14c58593223f052d.jpg)  
图3 $\mathrm { T V D I } _ { \mathrm { N } }$ 和 $\mathrm { T V D I _ { E } }$ 与实测 $2 0 ~ \mathrm { c m }$ 土壤水分散点图  
Fig.3 $\mathrm { T V D I } _ { \mathrm { N } }$ and $\mathrm { T V D I _ { E } }$ with a $2 0 \mathrm { - } \mathrm { c m }$ -deep soil water dispersion plot

# 表1评价矩阵

Tab.1The evaluation matrix   

<html><body><table><tr><td rowspan="2">月份</td><td colspan="4">半湿润区</td><td colspan="4">半干旱区</td></tr><tr><td>无旱</td><td>轻旱</td><td>中旱</td><td>重旱</td><td>无旱</td><td>干旱</td><td>中旱</td><td>重旱</td></tr><tr><td>6</td><td>0.25</td><td>0.42</td><td>0.60</td><td>0.74</td><td>0.58</td><td>0.65</td><td>0.78</td><td>0.88</td></tr><tr><td>7</td><td>0.38</td><td>0.58</td><td>0.66</td><td>0.79</td><td>0.61</td><td>0.69</td><td>0.82</td><td>0.91</td></tr><tr><td>8</td><td>0.41</td><td>0.40</td><td>0.64</td><td>0.75</td><td>0.64</td><td>0.60</td><td>0.74</td><td>0.85</td></tr></table></body></html>

Tab.2Evaluation functions of the indexes   
表3模糊隶属度矩阵  

<html><body><table><tr><td>评价指标</td><td>评价函数</td><td>取值范围</td><td>评价指标</td><td>评价函数</td><td>取值范围</td></tr><tr><td>无旱</td><td>0.40 - TVDIE TVDIE</td><td>0 <TVDIE ≤0.40</td><td>中旱</td><td>5- -0.g</td><td>0 <TVDIE ≤0.75</td></tr><tr><td rowspan="4">轻旱</td><td>TVDIe-0.40</td><td>TVDIE >0.40</td><td></td><td>TvDIg-0.75</td><td>TVDIE >0.75</td></tr><tr><td>0.60 - TVDIE TVDIE -0.40</td><td>0<TVDIE ≤0.60</td><td>重旱</td><td>0.86 -TVDIE TVDIE -0.75</td><td>0<TVDIE ≤0.86</td></tr><tr><td>TVDIE -0.60</td><td></td><td></td><td>TVDIE-0.86</td><td></td></tr><tr><td>TVDIE -0.40</td><td>TVDIE >0.60</td><td></td><td>TVDIE -0.75</td><td>TVDIE >0.86</td></tr></table></body></html>

Tab.3Fuzzy membership matrix   
表4基于MODIS $\mathbf { T V D I } _ { \mathrm { E } }$ 的干旱等级监测划分标准  

<html><body><table><tr><td rowspan="2">月份</td><td colspan="4">半湿润区</td><td colspan="4">半干旱区</td></tr><tr><td>无旱</td><td>轻旱</td><td>中旱</td><td>重旱</td><td>无旱</td><td>干旱</td><td>中旱</td><td>重旱</td></tr><tr><td>1</td><td>0.28</td><td>0.47</td><td>0.64</td><td>0.68</td><td>0.43</td><td>0.57</td><td>0.76</td><td>0.82</td></tr><tr><td>2</td><td>0.34</td><td>0.42</td><td>0.56</td><td>0.62</td><td>0.62</td><td>0.69</td><td>0.80</td><td>0.87</td></tr><tr><td>3</td><td>0.43</td><td>0.66</td><td>0.79</td><td>0.81</td><td>0.64</td><td>0.74</td><td>0.85</td><td>0.92</td></tr></table></body></html>

表2各指标评价函数表  
Tab.4Classification standard of drought based on the MODIS $\mathbf { T V D I } _ { \mathbf { E } }$   

<html><body><table><tr><td>等级</td><td>类型</td><td>半湿润区</td><td>半干旱区</td><td>等级</td><td>类型</td><td>半湿润区</td><td>半干旱区</td></tr><tr><td>1</td><td>无旱</td><td>TVDIE ≤0.37</td><td>TVDIE ≤0.52</td><td>4</td><td>重旱</td><td>0.69 <TVDIE ≤0.83</td><td>0.82 <TVDIE ≤0.91</td></tr><tr><td>2</td><td>轻旱</td><td>0.37<TVDIE≤0.55</td><td>0.52<TVDIE ≤0.71</td><td>5</td><td>特旱</td><td>TVDIE ≥0.83</td><td>TVDIE ≥0.91</td></tr><tr><td>3</td><td>中旱</td><td>0.55 <TVDIE ≤0.69</td><td>0.71<TVDIE ≤0.82</td><td></td><td></td><td></td><td></td></tr></table></body></html>

主要研究天气的干湿程度。农业干旱是指作物生长过程中因供水不足，阻碍作物正常生长而发生水量供需不平衡的现象[24]。本文所用的 TVDI数据不是单时次数据，而是半月合成数据。根据薄燕飞[25研究的不同土地类型下TVDI与气象干旱指数的关系中,TVDI与 $1 0 \ \mathrm { c m }$ 土壤水分、TVDI与 $2 0 \ \mathrm { c m }$ 土壤水分、TVDI与SPI（标准化降水指数）、TVDI与MI（相对湿润度指数)分别在对应旬上相关程度最高。同时，干旱常用土壤含水量作为判定指标，结合实测$2 0 \ \mathrm { c m }$ 土壤水分与同期TVDI相关性分析（图3）可知，采用TVDI指数在藏北地区进行旱情的监测是可行的。

在 ArcGIS中将 2015—2017年每月2期的$\mathrm { \Delta T V D I _ { E } }$ 进行平均值合成后，以23个自动站为中心周围9个栅格值取平均后，根据表4标准计算遥感干旱等级，再将结果与依据降水距平率计算得到的干旱等级(气象干旱等级)进行比较。图4为6一8月2 种监测结果等级差值。从图4可以看出：遥感干旱等级与气象干旱等级多数情况下是一致的。夏季(6一8月)遥感干旱等级与气象干旱等级监测结果一致的比例均为 $8 5 . 3 \% \sim 8 9 . 7 \%$ 。每月2种评价等级相差1级的比例均大于 $9 5 \%$ 。由于当惹雍措气象站地理位置距离湖面只有 $2 0 \mathrm { ~ m ~ }$ ,对应的卫星数据中一定包含了湖面的信息，不适合与卫星数据对比，故做剔除处理。以上结果表明，基于MODIS$\mathrm { \Delta T V D I _ { E } }$ 及干旱等级划分标准的遥感干旱监测方法适用于藏北地区区域范围内的干旱等级监测，其监测结果与气象干旱监测结果基本相符。

# 2.3旱情遥感监测结果的时空动态特征

# 2.3.1旱情的时序特征

（1）不同等级旱情的年际变化特征

统计2002—2017年各年份6—8月发生中旱及以上等级旱情的面积比例，制作中旱及以上年际变化比例柱状图（图5a），可以看出： $\textcircled{1}$ 藏北地区发生旱灾的情况比较常见，平均每年有 $20 \%$ 左右的地方会发生中旱及以上旱情; $\textcircled{2}$ 2009 年灾情最为严重，发生中旱及以上灾情的区域面积达到 $2 4 \%$ ，根据西藏自治区防汛抗旱指挥部的监测结果，2009年西藏全区遭遇了10a不遇的干旱，这与本研究的监测评价结果一致。其次，2002年和2015年的旱情也相对较重; $\textcircled{3}$ 2016年和2017年研究区发生中旱以上旱情的面积比例相对较低，为 $1 1 \% \sim 1 2 \%$ 。其次，

(a)6月 (b)7月 (c）8月32 1 12.9 4.4 %/ 32 1 C 32 1 4 2.9 %  
值 值 值  
差 0 85.3 差 0 88 差 0 89.7-1 5.9 -1 -1 5.9-2 1.4 -2 各 -2 0-3 0 -3 0 -3 00 10203040506070 010203040506070 010203040506070验证点个数 验证点个数 验证点个数

Fig.4Differenceof droughtlevelbetweentheremotesensingresultsmonitoredbytheautomaticstationandthemeteorological

![](images/3536506ebf5ae831a1cf20896c4ee8b8bf4348bd1ea5baa0222f2acfbf77e5d4.jpg)  
图46一8月自动站遥感干旱监测与气象干旱等级差值  
图5中旱及以上面积比例与各等级干旱面积比例

2011 年的比例也较低,为 $1 2 . 7 2 \%$ 。

从各类旱情发生面积比例的多年变化情况（图5b)可以看出，藏北地区的旱情以轻旱和中旱居多，重旱和特旱发生的面积比例相对较小。在严重干旱的年份，重旱和特旱的面积比例明显升高。

# （2）不同等级旱情的年内特征

统计2002—2017年每年6—8月同期不同干旱等级遥感监测面积比例的平均值，制作成柱状图，从图6可以看出：研究区在6月发生较严重的旱情，发生中旱及以上旱情的面积均在 $20 \%$ 以上，对应为夏旱。夏旱持续到7月，随着降雨增多开始逐渐缓解。分析6月干旱严重的主要原因，可能在于夏季高原温度升高，蒸发量加大，加之主降水期还未到来，因而相对干旱。7月和8月受高原低压的夏季降水影响，中旱及以上的比例分别降到16. $32 \%$ 和$1 2 . 5 1 \%$ ,整个区域的旱情得到缓解。

![](images/7003671eb3a9f5f0cd051809150b0f7b067ac6e3209cd756dd9aec3eb7d35656.jpg)  
Fig.5Proportions of moderate and above drought area and the drought area at diferent levels   
图6不同旱情等级的面积比例构成及变化 Fig.6Composition and change of the area proportions with different drought levels

2.3.2旱情的空间分布规律将2002—2017 年每个像元发生中旱及以上的次数比例统计作图（图7），可以更加直观地分析研究区旱情发生的空间分布规律。可以看出，常受较严重干旱影响的地区主要集中在研究区的西南部和中部，研究区北部和东南部受旱灾影响相对较轻，这与藏北东部地区降水较多有关。应该指出的是，由于半湿润区的遥感干旱划分标准低于半干旱区，所以在半湿润区西侧旱情略重于东侧。

以旱情最严重的2009年为例，制作连续的干旱等级监测结果图以直观地显示研究区旱情在空间上的发展过程(图8）。从图8可以看出，研究区旱情注：绿色代表16a内发生中旱及以上旱情所占比例在 $0 \sim 2 0 \%$ 之间，红色代表比例在 $8 0 \% \sim 1 0 0 \%$ 。

![](images/8a6cd087f717936431867bbac69bf3fdbbfb36e9de65c596cb70864e394cc371.jpg)  
图82009年6—8月藏北地区旱情分布特征

![](images/09075f4895a1d1add54006bf706935f9ae17a80993d536779192a1202669ef40.jpg)  
图72002—2017年藏北发生中旱及以上的次数比例分布Fig.7Frequencies of moderate and above droughts in northTibet From 2002 to 2017  
Fig.8Distribution of drought in north Tibet from June to August 2009

的发生大体从中部和西部开始，逐渐扩大影响范围后，从东部开始减弱。旱情最为严重的是6月2期，中旱及以上所占比例达到 $4 0 . 8 \%$ 。根据中国气象局全国干旱监测资料显示，2009年4月1日至6月19日，西藏中部及东南部降水量为近10a来同期最少，特别是进入6月以来，西藏中南部区域较常年偏少6成以上，符合监测结果。旱情加重时，研究区中北部随之发生一定程度的旱情，主要为中旱，不过该区域干旱影响时间较短，旱情能随降水增加较快消退。根据西藏自治区气象局的气象站点降水数据，7月和8月藏北地区降水量较之前月份显著增加，特别是中东部的那曲地区，因此7月以后旱情开始由东向西减轻，东部和北部地区逐渐恢复正常。

# 3结论与讨论

# 3.1结论

（1）根据MODIS产品数据获得 $\mathrm { \Delta T V D I _ { N } }$ 和$\mathrm { \Delta T V D I _ { E } }$ 反演结果,可以很好地适用于藏北干旱监测，与 $2 0 \ \mathrm { c m }$ 土壤水分的相关性分析证明， $\mathrm { \Delta T V D I _ { E } }$ 对干旱监测效果更好。

（2）采用模糊数学方法，考虑气候区差异，在藏北地区建立了MODISTVDI的干旱等级划分标准。基于参照气象上降水距平率的气象干旱等级划分标准,遥感干旱等级也划分为无旱、轻旱、中旱、重旱、特旱5个等级。其中，半湿润区5个等级的划分标准依次为 $( \mathrm { ~ 0 ~ } \sim \mathrm { 0 } . \mathrm { ~ } 3 7 )$ 、 $\left( 0 . \ 3 7 \ \sim 0 . \ 5 5 \right)$ 、(0.55\~0.69）、 $\left( 0 . 6 9 \sim 0 . 8 3 \right)$ 、 $( 0 . 8 3 \sim 1 )$ ;半干旱区5个等级的划分标准依次为 $( 0 \sim 0 . 5 2 )$ 、 $( 0 . 5 2 \sim 0 . 7 1 )$ 、$( 0 . 7 1 \sim 0 . 8 2 )$ ）、 $( 0 . 8 2 \sim 0 . 9 1 \$ ）、 $( 0 . 9 1 \sim 1 )$ 。遥感干旱等级和气象干旱等级的结果对比表明，本研究建立的干旱等级监测方法和标准适用于藏北地区，根据气候区建立不同干旱等级标准是必要的，遥感监测的结果与气象干旱监测结果大多情况下一致，个别区域和时间范围内存在1个等级差，极少出现2个或以上等级差。

(3）藏北地区的旱情以轻旱和中旱为主，重旱和特旱发生的面积比例相对较少。根据中旱及以上干旱发生的频次分布图，干旱严重地区主要集中在研究区的西南部和中部。从干旱发生的时间过程来看，年内6月旱情最严重，7月中后期旱情开始缓解。2002—2017年，中旱及以上旱情发生比例在2009年达到最高，旱情最严重。从旱情频发的区域来看，主要旱情的发生从中部、西部开始，从东部结束。

# 3.2讨论

根据西藏自治区防汛抗旱指挥部的气象干旱监测，2009年6月以来降水偏少，遭遇10年一遇的旱灾，而在6月末西藏部分地区迎来降雨，旱情开始缓解，这与本文的旱情演变规律一致。但基于TVDI的干旱监测对干旱发生的空间分布更详细，很适合西藏缺少台站的地区旱情监测。本研究与柳锦宝等[26]基于TVDI的遥感干旱监测相比,使用EVI代替NDVI得到的拟合系数更高，等级监测结果更贴近气象部门的服务要求，能更好地为防灾减灾决策提供依据。

# 参考文献(References）:

[1]王凤杰,冯文兰，扎西央宗,等.基于植被光谱和FY-3A/VIRRL1B数据的藏北地区土壤水分估算[J].干旱区研究,2018, 35（3）:532-539.[Wang Fengjie,Feng Wenlan,Zhaxiyangzong, et al.Estimation of soil moisture content in North Tibet based on vegetation spectra and FY-3A/VIRR L1B Data[J].Arid Zone Research,2018,35(3):532-539.]   
[2]杨世琦,高阳华,易佳.干旱遥感监测方法研究进展[J].高原 山地气象研究,2010,30（2）:75-78.[Yang Shiqi,Gao Yanghua,Yi Jia.Progress on drought monitoring by remote sensing[J]. Plateau and Mountain Meteorology Research,2010,30（2）:75- 78.]   
[3]齐述华.干旱监测遥感模型和中国干旱时空分析[D].北京： 中国科学院研究生院（遥感应用研究所）,2004.〔QiShuhua. Drought Monitoring Models with Remote Sensing and SPatio-Temporal Characteristics of Drought in China[D].Beijing:Graduate School of the Chinese Academy of Sciences(Institute of Remote Sensing Applications）,2004.]   
[4]Zhao S,Cong D,He K,et al. Spatial-temporal variation of drought in China from 1982 to 2010 based on a modified temperature vegetation drought index（mTVDI）[J].Scientific Reports,2017,7 (1) :17 473.   
[5]Hosseini M,Saradjian M R.Soil moisture estimation in a vegetated area using combination of AIRSAR and landsat 5-TM images[J]. Journal of the Indian Society of Remote Sensing,2014,42(4）:719 -726.   
[6]曹雷,丁建丽,牛增懿.基于TVDI的艾比湖地区土壤水分时空 变化分析[J].水土保持研究,2016,23（3）：43－47.[Cao Lei, Ding Jianli,Niu Zengyi.Analysis of spatiotemporal change of soil moisture of the Ebinur Lake area based on TVDI[J].Research of Soil and Water Conservation,2016,23(3）:43-47.]   
[7」薛天翼,白建军.基于TVDI和气象数据的陕西省春季旱情时 空分析[J].水土保持研究,2017,24(4)：240-246.[Xue Tia

nyi,Bai Jianjun. Spatiotemporal variations of spring drought based on TVDI and meteorological index in Shaanxi Province[J].Research of Soil and Water Conservation,2017,24(4):240 -246.] [8]王行汉,刘超群,丛沛桐,等.基于增强温度植被指数的农业旱 情遥感监测[J].干旱区资源与环境，2018，32（5）：165-170. [Wang Xinghan,Liu Chaoqun,CongPeitong,etal.Agriculture drought monitoring using remote sensing based on enhanced temperature vegetation dryness index[J].Journal of Arid Land Resources and Environment,2018,32(5）:165-170.]

[9]杨秀海,卓嘎,罗布.基于MODIS 数据的青藏高原旱情监测研究[J].中国沙漠,2014,34（2）：527-534.[YangXiuhai,Zhuoga,Luo Bu.Drought monitoring in the Tibetan Plateau basedon MODIS dataset[J].Journal Of Desert Research,2014,34（2）：527 -534.]

[10]宋春桥,游松财,刘高焕，等.基于TVDI的藏北地区土壤湿度空间格局[J].地理科学进展,2011,30（5）：569-576.[SongChunqiao,You Songcai,Liu Gaohuan,et al. The spatial pattern ofsoilmoisture in Northern Tibetbased on TVDImethod[J].Pro-gress in Geography,2011,30(5） :569-576.]

[11」郭锯，王小平.遥感干旱应用技术进展及面临的技术问题与发展机遇[J].干旱气象,2015,33（1）：1-18.[GuoNi，WangXi-aoping.Advances and developing opportunities in remote sensing ofdrought[J].Journal of Arid Meteorology,2015,33（1）:1-18.](12]齐述华，王长耀，牛铮.利用温度植被旱情指数(TVDI)进行全国旱情监测研究[J].遥感学报，2003，7（5）：420-427.〔QiShuhua,Wang Changyao,Niu Zheng.Evaluating soil moisture sta-tus in China using the temperature/vegetation dryness index(TV-DI)[J].Journal Of Remote Sensing,2003,7(5） :420-427.]

[13］张敏,高东东，何成江，等.基于模糊数学的德阳市平原地下水 环境质量评价[J].环境工程,2016,34（4）：151-155.[Zhang Min,Gao Dongdong,He Chengjiang,et al.Environmental quality evaluation of Deyang plain groundwater based on fuzzy mathematics [J].Environmental Monitoring& Assessment,2016,34（4）:151 - 155.]

[14]李祚泳.环境信息规范对称与普适性[M].北京：科学出版社， 2011:191-199.[Li Zuoyong.Normalization Symmetry and Universality on Environmental Information[M].Beijing:Science Press, 2011:191-199.]

[15］卓嘎，尼玛央珍，唐小萍.1980—2009 年西藏西北部潜在蒸散 时空分布特征及其影响因素[J].干旱区研究,2016,33（4）： 698-7O7.[Zhuo Ga,Nima Yangzhen,Tang Xiaoping. Spatiotemporal distribution of potential evapotranspiration and its affecting factors in Northwest Tibet during the period of 198O -2009[J]. Arid Zone Research,2016,33(4):698-707.]

[16]曹志翔,林瑞杰，宋新伟.西藏农牧区干旱状况分析[J].青海农林科技,2016（4）：31－33.[Cao Zhixiang,Lin Ruijie,SongXinwei.Analysis of drought situation agricultural and pastoral areasin Tibet[J].QinghaiNonglin Keji,2016(4） :31-33.]

[17]边金虎，李爱农，宋孟强，等.MODIS植被指数时间序列Savitzky-Golay 滤波算法重构[J].遥感学报，2010，14（4）：725- 741.[Bian Jinhu,Li Ainong,Song Mengqiang,et al.Reconstruction of NDVI time-series datasets ot MUDiS based on Savitzky-Go lay filter[J]. Journal of Remote Sensing,2010,14（4）:725- 741.]

[18］柯灵红,王正兴,宋春桥,等.青藏高原东北部 MODIS 地表温 度重建及其与气温对比分析[J].高原气象,2011,30（2）：277 - 287.[Ke Linghong,Wang Zhengxing,Song Chunqiao,et al. Reconstruction of MODIS land surface temperature in Northeast Qinghai-Xizang Plateau and its comparison with air temperature[J]. Plateau Meteorology,2011,30(2）:277 -287.]   
[19］梁斌,齐实.北京山区土壤养分空间变化特征研究[J].土壤, 2018,50(4）:769-777.[Liang Bin,Qi Shi.Spatial distributions of soil nutrients in Beijing mountainous area[J]. Soils,2018,50 (4) :769 - 777. ]   
[20］饶清华,邱宇,王菲凤,等.福建省山仔水库生态安全评价[J]. 水土保持研究,2011,18(5）:221-225.[Rao Qinghua,Qiu Yu, Wang Feifeng,et al.Evaluation on ecological security in Shanzi reservoir region of Fujian Province[J].Research of Soil and Water Conservation,2011,18(5） :221-225.]   
[21]Karnieli A,Panov N,Goldberg A,et al. Use of NDVI and land surface temperature for drought assessment: Meritsand limitations. [J].Journal of Climate,2010,23(3）:618-633.   
[22］朱小强,塔西甫拉提·特依拜,丁建丽,等.基于 MODIS 与 Landsat 8的艾比湖湿地旱情时空变化及其影响因素分析[J]. 生态学报,2018,38（8）:383-393.[Zhu Xiaoqiang,Tashpolat Tiyip,Ding Jianli,et al.Analysis of spatiotemporal changes in the drying of the Ebinur Lake Basin and its influencing factors based on MODIS and Landsat 8 satelltes[J].Acta Ecologica Sinica, 2018,38(8) :383 -393.]   
[23］沙莎,郭锯,李耀辉,等.我国温度植被旱情指数 TVDI的应用 现状及问题简述[J].干旱气象,2014,32（1）：128－134.［Sha Sha,Guo Ni,Li Yaohui,etal.Introduction of application of temperature vegetation dryness index in China[J]. Journal of Arid Meteorology,2014,32(1) :128-134.]   
[24］王艺璇.基于SWAT模型的不同类型干旱指标关系分析及预 测[D].河南:郑州大学,2014.[Wang Yixuan.Based on SWAT Models Drought Index of Diffrent Types Relationship Analysis and Forecast[D]. Henan:Zhengzhou University,2014.]   
[25］薄燕飞.不同土地利用类型下TVDI与气象干旱指数的关系研 究[D].西安:陕西师范大学,2016.[Bao Yanfei.Study on the Relationship between TVDI and Meteorological Drought Index under Different Land Use Types[D].Xi'an:Shaanxi Normal University,2016. ]   
[26］柳锦宝,何政伟,段英杰.MODIS 数据支持下的西藏干旱遥感 监测[J].干旱区资源与环境,2013,27（6）：134－139.[Liu Jinbao,He Zhengwei,Duan Yingjie.Monitoring the droughts in Tibet based on remote sensing using modis data[J]. Journal of Arid Land Resources and Environment,2013,27(6）:134-139.]

# Remote Sensing Monitoring of Drought Level in North Tibet Based on MODIS TVDI and Fuzzy Mathematics

LIU Yi-zhe'，FENG Wen-lan’，Zhaxi Yangzong²，LIANG Li’，LI Tong' (1.CollgefoucdoneshgduUesityfftionogdun; 2．Tibet Autonomous Region Climatic Center,Lhasa 85oooo,Tibet,China)

Abstract：A dynamic and continuous monitoring of spring and summer drought in north Tibet during the period of 1980-2017 was carried out.The temperature vegetation drought index（TVDI）,fuzzy mathematics and monitored results of meteorological drought level were used to develop the clasification standard of remote sensing drought,andthe accuracy of monitored results was verified.The spatiotemporal variationof drought in north Tibet in recent years was analyzed. The main conclusions are as follows: $\textcircled{1}$ TVDI $\mathrm { \Delta N }$ and $\mathrm { T V D I _ { E } }$ calculated based on the normalized vegetation index（NDVI）and enhanced vegetation index（EVI） were significantlycorrelated with the soil moisture content at $2 0 ~ \mathrm { c m }$ in depth at O.O5 significance level. The determination coeffcient of $\mathrm { T V D I _ { E } }$ was higher ; $\textcircled{2}$ Based on $\mathrm { \Delta T V D I _ { E } }$ ,drought could be divided into four levels including without drought,slight drought,moderate drought,heavy drought and severe drought.On which it was obtained thatthe drought level in north Tibet was consistent with the monitored results of meteorological drought level; $\textcircled{3}$ Drought in the study area was not very serious in recent years,and the holistical drought situation was somewhat aleviative.Thedrought was the most serious in 2009,and the area proportion of moderate and above drought was as high as $24 \%$ .Monthly,the drought was the most serious inJune.In terms of the spatial distribution,the drought in the southwestand thecentral part of the studyarea was relatively serious,and it was relatively slight in the north and southeast.The research results could be referred in monitoring drought in north Tibet.

Key words:temperature vegetation drought index； fuzzy mathematics；drought level； MODIS； north Tibet