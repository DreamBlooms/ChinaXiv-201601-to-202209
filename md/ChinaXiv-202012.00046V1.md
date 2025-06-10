# 巴拉格尔河流域土壤传递函数构建与评估

房丽晶¹，高瑞忠¹²，刘廷玺¹²，张阿龙¹，王喜喜³(1.内蒙古农业大学水利与土木建筑工程学院,内蒙古 呼和浩特010018；2.内蒙古自治区水资源保护与利用重点实验室,内蒙古 呼和浩特010018；3.美国欧道明大学,弗吉尼亚诺福克23529)

摘要：以土壤理化性质数据建立传递函数是间接获取土壤水力参数的重要手段。采集巴拉格尔河流域土壤 $0 \sim$ $3 0 \ \mathrm { c m }$ 和 $3 0 \sim 6 0 ~ \mathrm { c m }$ 土层102个样品,测定粒径分布、干容重、有机质、饱和导水率、田间持水率等指标,利用数理统计、空间插值及主成分分析等方法揭示流域根系层土壤理化及水力特性空间特征，以土壤饱和导水率 $( K _ { s } )$ 为例对多种土壤传递函数模型进行适用性分析,结果表明：(1）以砂质壤土为主,随根系层土壤深度加大,砂质壤土含量减小,壤质砂土增多;(2）不同层饱和导水率空间分布具有相似性，土壤深层大于表层的 $K _ { s }$ ;(3）土壤根系层 $3 0 \sim 6 0 \$ cm土层的新建传递函数模拟效果较好,检验参数 $r$ 、 $\delta _ { \mathrm { { \scriptscriptstyle M E } } }$ 和 $\delta _ { \mathrm { R M S E } }$ 分别为0.73、0和1.62;(4）估计误差的大小与土壤类型有关，新建PTFs对于砂质壤土较为适用。

关键词：草地根系层；水力参数；土壤分类；传递函数；巴拉格尔河

土壤是植被生态系统的重要组成部分，土壤水力特性是土壤水分运动、溶质运移、植被生态研究的基础[1]。近 $3 0 \mathrm { ~ a ~ }$ ,土壤传递函数(pedo-transferfunctions，简称PTFs)作为估测土壤水力特性研究的重要方法，受到学者们的广泛关注[2-4]。PTFs是一种利用土壤质地、容重、有机质含量等土壤理化性质来快速、间接估算土壤水力参数的方法[5-9]

国内外学者通过建立基于不同理论和数据库的PTFs对土壤饱和导水率和土壤水分特征曲线进行模拟分析[019],常见模型主要有Cmpbl[]Cosby]、Wosten[13-14]、Saxton[15]、Pucket[16]、Rawls 模型[17]、vanGenuchten模型[18]与Rosetta模型[19],但这些PTFs在建模地区以外区域不具普适性。PTFs构建方法主要包括线性回归、非线性回归[20-22]、人工智能网络[23-24]、数据处理分组分类方法[25]等，进而适用于不同地区的土壤参数估算。学者们针对不同地区或土壤类型,如黄淮海平原[4]、沙丘-草地相间地区[5]、沙地[21]、稻田土[26]、农田[27]、丘陵区紫色土[28]等建立了适合当地的PTFs。

综上所述，鉴于鲜有对于内蒙古内陆河草原流域根系层土壤传递函数的研究，本文选取巴拉格尔河流域为典型研究对象，系统分析土壤理化性质和水力特征参数及空间分布规律，利用6种数理模型对土壤饱和导水率 $\left( \boldsymbol { K _ { s } } \right)$ 进行估算，建立适用于巴拉格尔河流域根系层的土壤饱和导水率传递函数，旨在为内蒙古内陆河草原流域土壤水力特征和草地生态系统研究提供科学依据，

# 研究区与研究方法

# 1.1 研究区概况

巴拉格尔河流域 $( 1 1 6 ^ { \circ } 2 1 ^ { \prime } \sim 1 1 9 ^ { \circ } 3 1 ^ { \prime } \mathrm { E } , 4 3 ^ { \circ } 5 7 ^ { \prime } \sim$ $4 5 ^ { \circ } 2 3 ^ { \prime } \mathrm { N } )$ 位于内蒙古锡林郭勒盟西乌珠穆沁旗境内，流域面积 $5 3 5 0 ~ \mathrm { k m } ^ { 2 }$ ,海拔高度 $8 8 5 \sim 1 8 7 6 \mathrm { ~ m ~ }$ （图1)，草地类型是以羊草和针茅为主的典型草原，为大陆型半干旱气候，冬季严寒、夏季炎热，年均降水量为 $3 3 4 ~ \mathrm { m m }$ ,蒸发量为 $1 1 4 9 \ \mathrm { m m }$ ,平均气温 $1 . 2 ~ \mathrm { ^ { \circ } C }$ ，最高气温可达 $3 7 . 5 ~ \mathrm { ^ { \circ } C }$ ，最低为 $- 3 8 . 5 ~ \mathrm { { ^ { \circ } C } }$ ,平均风速为$1 5 \mathrm { k m } \cdot \mathrm { h } ^ { - 1 }$ ,每年有 $2 8 \sim 1 4 8 \mathrm { ~ d ~ }$ 的风速可达到 $1 2 5 \mathrm { k m }$ ：$\mathbf { h } ^ { - 1 }$ 。

# 1.2数据来源与处理

按照《土壤环境监测技术规范》(HJ/T166-

http://azr.xjegi.com

1995)的布点要求，结合流域的地形地貌特征和土地利用/植被覆盖类型，布设51个土壤采样点（图1),在草地主要根系层深度 $0 \sim 3 0 ~ \mathrm { c m }$ 和 $3 0 \sim 6 0 ~ \mathrm { c m }$ 处采集102点位共408个土壤样品，测定土壤粒径、干容重、有机质、饱和导水率、田间持水率、给水度、毛管含水率和化学成分等指标。

土壤采样过程中，为保持土壤样品的一致性，采样点先除去地表浮土，再挖取土壤剖面，每个土层中间位置平行采取环刀样3个和土袋1个，环刀用于测定土壤水力特性参数，土袋用于物理化学特征指标测定。土壤饱和导水率用定水头法测定；饱和含水率采用环刀底部缠纱布浸水测定，若2次称重变幅小于 $2 \%$ ,即为饱和状态，取均值作为饱和含水率；土壤有机质通过重铬酸钾稀释热法测定；土壤粒径采用激光粒径仪(HELOS-OASIS型)和土壤筛（规格为 $5 \mathrm { m m }$ )测定。

土壤数据分析中，数理统计运用SPSS22，空间克里金插值及制图选用ArcGIS10.3，主成分分析采用DPS数据处理软件系统， $F$ 检验采用Excel2010。

# 1.3 研究方法

黏粒、粉粒和砂粒含量是土壤分类命名和传递函数模型建立的主要输入要素，根据国际土壤质地分级标准进行分类，土壤粒径分级标准为：黏粒( $\mathbf { \bar { \rho } } <$ $0 . 0 0 2 ~ \mathrm { m m }$ ），粉粒 $( 0 . 0 0 2 \sim 0 . 0 5 ~ \mathrm { m m } )$ ，砂粒 $( 0 . 0 5 \sim 2 \$ mm)(表1)[29-30]

土壤平均粒径 $d _ { \mathrm { g } }$ 的标准差 $\sigma _ { \mathrm { { g } } }$ 可作为传递函数模型建立的主要输入要素[5],以增加模型的有效性：

![](images/56df598aff7198983925884052b14108cf82e24f4fa460aadb134f56ec452448.jpg)  
图1研究区地理位置及采样点布设图  
Fig.1 Location of the study area and sampling points

表1国际制土壤质地分级标准  
Tab.1 International standard for soil texture classification   

<html><body><table><tr><td>质地名称</td><td>黏粒(<0.002 mm)/%</td><td>粉砂(0.02~0.002 mm)/%</td><td>砂粒(2~0.02 mm)/%</td></tr><tr><td>壤质砂土</td><td>0~15</td><td>0~15</td><td>85~100</td></tr><tr><td>砂质壤土</td><td>0~15</td><td>0~45</td><td>55~85</td></tr><tr><td>壤土</td><td>0~15</td><td>30~45</td><td>40~55</td></tr><tr><td>粉砂质壤土</td><td>0~15</td><td>45~100</td><td>0~55</td></tr><tr><td>砂质黏壤土</td><td>15~25</td><td>0~30</td><td>55~85</td></tr><tr><td>黏壤土</td><td>15~25</td><td>20~45</td><td>30~55</td></tr><tr><td>粉砂质黏壤土</td><td>15~25</td><td>45~85</td><td>0~40</td></tr><tr><td>砂质黏土</td><td>25~45</td><td>0~20</td><td>55~75</td></tr><tr><td>壤质黏土</td><td>25~45</td><td>0~45</td><td>10~55</td></tr><tr><td>粉砂质黏土</td><td>25~45</td><td>45~75</td><td>0~30</td></tr><tr><td>黏土</td><td>45~65</td><td>0~55</td><td>0~55</td></tr></table></body></html>

$$
\ d _ { \mathrm { g } } = { \frac { \displaystyle \sum _ { 1 } ^ { i } ( f _ { i } \times d _ { i } ) } { 1 0 0 } }
$$

$$
\sigma _ { \mathrm { g } } = \sqrt { \frac { \displaystyle \sum _ { 1 } ^ { i } f _ { i } \big ( d _ { \mathrm { g } } - d _ { i } \big ) ^ { 2 } } { 1 0 0 } }
$$

式中： $d _ { i }$ 为粒径区间中间值； $f _ { i }$ 为粒径区间的粒径百分含量。

采用Campbel[]、Cosby[12]、Wosten[13-14]、Saxton[15]Puckett[16]和统计回归[6等土壤传递函数进行土壤饱和导水率的计算与适用性分析。

PTFs适用性精度评估采用平均误差 $\delta _ { \mathrm { { M E } } } ( \mathrm { { m } \cdot d ^ { - 1 } ) }$ 、均方根误差 $\delta _ { \mathrm { R M S E } } \ ( \mathrm { m } \cdot \mathrm { d } ^ { - 1 } )$ 和相关系数 $\boldsymbol { r } _ { \mathrm { ~ o ~ } } \boldsymbol { r }$ 越接近1,说明计算值与实测值变化趋势越相似; $\delta _ { \mathrm { { \scriptscriptstyle M E } } }$ 反映计算值对实测值总体偏离程度，平均误差绝对值越接近0越好，取值为正说明高估了实测值，反之，低估了实测值; $\delta _ { \mathrm { R M S E } }$ 反映了计算值与实际值的吻合程度，此值越小说明计算精度越高。

$$
\delta _ { \mathrm { { M E } } } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } ( y _ { i } - \hat { y } _ { i } )
$$

$$
\delta _ { \mathrm { R M S E } } = \sqrt { \frac { 1 } { N } \sum _ { i = 1 } ^ { N } ( y _ { i } - \hat { y } _ { i } ) ^ { 2 } }
$$

$$
r = \sqrt { \frac { \mathrm { c o v } ( y , \hat { y } ) } { \mathrm { v a r } ( y ) \mathrm { v a r } ( \hat { y } ) } }
$$

式中： $N$ 为土壤样本个数; $y _ { i }$ 为第 $i$ 个样本值; $\widehat { y _ { i } }$ 为

第i个土壤样本计算值。

# 2结果与分析

# 2.1土壤质地及空间分布特征

依据国际制土壤质地分级标准对102采样点数据进行分析统计，植被根系层 $0 \sim 3 0 ~ \mathrm { c m }$ 和 $3 0 \sim 6 0 \$ cm土壤质地基本一致，大部分砂粒含量在 $6 0 \% \sim$ $9 5 \%$ ,黏粒含量低于 $5 \%$ (图2)。研究区土壤在 $0 \sim$ $3 0 \ \mathrm { c m }$ 以砂质壤土为主，沿河道分布在流域中部，面积占比 $7 0 \%$ 以上，其次为壤质砂土，分散分布于流域边界区域，面积占比达到 $2 5 \%$ 以上，不到 $2 \%$ 的粉砂质壤土零星分布于局部区域; $3 0 \sim 6 0 ~ \mathrm { c m }$ 土层以砂质壤土为主，占 $5 0 \%$ 以上，主要分布于流域中部和南部，壤质砂土占 $3 1 \%$ ，分布于流域的东南部和西北部，低于 $1 0 \%$ 的少量壤土分布于流域的西南部(表2,图3)。总体可知，研究区土壤类型以砂质壤土为主，随着根系层土壤深度的加大，砂质壤土减少，壤质砂土增多，土壤类型增多。

植被根系层 $K _ { s }$ (图4)高值区主要出现在流域上游及下游的柴达木苏木南部，呈现块状分布， $K _ { s }$ 低值区主要分布在流域边界附近，即河谷两侧区域。总体来看， $0 \sim 3 0 ~ \mathrm { c m }$ 和 $3 0 \sim 6 0 ~ \mathrm { c m }$ 区域 $K _ { s }$ 存在相似的空间分布特征，土壤深层大于表层的 $K _ { s }$ 。沿巴拉格尔河干支流河谷地形低洼位置出现 $K _ { s }$ 高值区域，在流域边界附近河谷两侧出现低值区域，上游的 $K _ { s }$ 值高于下游，这与河水、地下水由运动的冲淤积作用有关，与空间降水分布不均匀、草地植被差异、人类放牧强度等因素有关，这种分布特征体现了流域产汇流下垫面的复杂性。

![](images/05ecb46e99534c29beeb2f28391e30f3894f45b9a3c0ad4571997133a2a737cc.jpg)  
图2草地根系层不同土壤层岩性组成百分含量  
Fig.2Percentage of lithological composition of different soil layers in grass root layer

表2不同土壤类型面积百分比  
Tab.2 Percentage of the different soil types area   
1%   

<html><body><table><tr><td>土层/cm</td><td>壤土</td><td>黏壤土</td><td>壤质砂土</td><td>砂质壤土</td><td>粉砂质壤土</td><td>粉砂质黏壤土</td></tr><tr><td>0~30</td><td>0</td><td>0</td><td>25.49</td><td>72.55</td><td>0</td><td>1.96</td></tr><tr><td>30~60</td><td>9.80</td><td>1.96</td><td>31.37</td><td>50.98</td><td>3.92</td><td>1.96</td></tr></table></body></html>

![](images/e04e4e687ae2112922e9ec726b92c4947aeca68472b9a1a4b647345b05695f57.jpg)  
Fig.3Spatial distribution of the soil types in the root layer

![](images/099bf2f9d6b4074863b06284979f81a337d8bc3dd677e1302b75fcea00a7c6fc.jpg)  
图3根系层土壤类型空间分布  
图4根系层 $K _ { s }$ 空间分布  
Fig.4Spatial distribution of $K _ { s }$ in the root layer

$0 \sim 3 0 ~ \mathrm { c m }$ 土层的 $K _ { s }$ 与土壤粉粒含量、砂粒含量和标准差极显著相关（ $\scriptstyle { \overbrace { a = 0 . 0 1 } }$ )，与土壤平均粒径显著相关( $\scriptstyle ( a = 0 . 0 5 )$ ，因此，初步选定土壤粉粒含量、砂粒含量、标准差和平均粒径作为 $0 \sim 3 0 ~ \mathrm { c m }$ 土壤层传递函数建立的输入变量; $3 0 \sim 6 0 ~ \mathrm { c m }$ 土层的 $K _ { s }$ 与土壤粉粒含量、砂粒含量、平均粒径和标准差极显著相关 $\scriptstyle ( a = 0 . 0 1$ )，与干容重、黏粒含量显著相关( $\scriptstyle { \frac { } { } } a =$ 0.05)，因此，初步选定土壤粉粒含量、砂粒含量、黏粒含量、平均粒径、标准差和干容重作为 $3 0 \sim 6 0 ~ \mathrm { c m }$ 土层传递函数建立的输入变量(表3)，进一步结合主成分分析，选取累计贡献率 $5 8 5 \%$ 的因子作为模型建立的自变量，最终确定 $0 \sim 3 0 ~ \mathrm { c m }$ 土层选用粉粒含量、标准差为传递函数建立的输入要素，干容重和粉粒含量为 $3 0 \sim 6 0 ~ \mathrm { c m }$ 土层传递函数建立的要素（表4），以Campbell、Cosby、Wosten、Saxton、Puckett等5种传统土壤传递函数及新建统计回归的PTFs

表3 $K _ { s }$ 与物理化学指标统计检验  

<html><body><table><tr><td rowspan="2">土层/cm</td><td colspan="3">岩土颗粒含量/%</td><td colspan="2">基础物理化学指标</td><td colspan="2">统计指标</td></tr><tr><td>黏粒</td><td>粉粒</td><td>砂粒</td><td>干容重/(g·cm-3)</td><td>有机质/%</td><td>平均粒径(dg)</td><td>标准差(σg)</td></tr><tr><td>0~30</td><td>-0.105</td><td>-0.394**</td><td>0.378**</td><td>0.154</td><td>0.157</td><td>0.345*</td><td>-0.449**</td></tr><tr><td>30~60</td><td>-0.284*</td><td>-0.482**</td><td>0.469**</td><td>0.311°</td><td>-0.067</td><td>0.469**</td><td>-0.615**</td></tr></table></body></html>

注：\*和\*\*分别表示在0.05和0.01的水平上具有显著性(双尾检验）。

# 表4 $K _ { s }$ 的物理化学指标主成分提取

Tab.3 Statistical test between $K _ { s }$ and the physic-chemical indices   

<html><body><table><tr><td>土层/cm</td><td>因子</td><td>特征值</td><td>百分率/%</td><td>累计百分率/%</td></tr><tr><td rowspan="2">0~30</td><td>1</td><td>3.84</td><td>76.06</td><td>76.06</td></tr><tr><td>2</td><td>1.12</td><td>13.00</td><td>89.06</td></tr><tr><td rowspan="2">30~60</td><td>1</td><td>4.36</td><td>72.69</td><td>72.69</td></tr><tr><td>2</td><td>1.05</td><td>15.92</td><td>88.61</td></tr></table></body></html>

进行饱和导水率计算(表5)。

# 2.3模型适用性评估

以平均误差 $\delta _ { \mathrm { { M E } } }$ 、均方根误差 $\delta _ { \mathrm { R M S E } }$ 和相关系数$r$ 作为检验指标对6种土壤传递函数102个样品（表5)进行适用性评估，对比分析Cosby、Saxton、Wosten、Puckett、Campbell和新建PTFs的计算值与实测值(图5)。

$0 \sim 3 0 \ \mathrm { c m } \cdot 3 0 \sim 6 0 \ \mathrm { c m }$ 土层中，新建PTFs都较为均匀的分布在 $4 5 ^ { \circ }$ 线上及两侧，拟合效果较好，其他模型均呈现不同程度的下移，即计算值低于实测值,其中Saxton相比其他模型更适用于本地区土壤饱和导水率的估算。 $0 \sim 3 0 ~ \mathrm { c m }$ 土层中，新建PTFs模型拟合效果较佳， $\boldsymbol { r }$ 为0.5,RMSE为1.7,ME为0,相关性较高，无偏离，吻合度高；Saxton次之， $\boldsymbol { r }$ 为0.44,RMSE为1.62，ME为0.53。 $3 0 \sim 6 0 ~ \mathrm { c m }$ 土层，新建PTFs模型拟合效果最佳，无论对于 $r$ 、ME、RMSE,新建PTFs都明显高于其他传统土壤传递函数，相关性高达0.73，对于已有传统方程均提高了 $0 . 2 \sim 0 . 3$ ,ME为0,无偏离，RMSE为1.62,吻合度高。传统PTFs中,Saxton 和Cosby精度高于其他函数,相关性分别为0.53、0.52,RMSE为2.1、2.2,ME为0.6、0.87;Cos-by和Saxton分布相似,计算值均略低于实测值，相对于其他传统PTFs更适用于饱和导水率的计算与推求，但因为Cosby只考虑了土壤黏粒和砂粒，难免会有一些局限性，Saxton的精度低于新建PTFs。Wosten和Campell总体低于 $4 5 ^ { \circ }$ 线，Puckett偏离更为明显。综前所述，新建PTFs更适合于研究区饱和导水率的估算。

Tab.4 $K _ { s }$ principal component extraction of thephysic-chemical indices   
表5土壤饱和导水率传递函数表述式  
Tab.5 Transfer-functions of soil saturated hydraulic conductivity   

<html><body><table><tr><td>名称</td><td></td><td>PTFs数学模型</td></tr><tr><td colspan="3">=.45</td></tr><tr><td rowspan="2">Campbell</td><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td colspan="3">b=e</td></tr><tr><td rowspan="2"></td><td>K0.336x1(45</td><td></td></tr><tr><td>壤土：Ks=1.13×10²×e</td><td></td></tr><tr><td colspan="3"></td></tr><tr><td rowspan="2"></td><td colspan="3"></td></tr><tr><td colspan="3">K 砂:K1x</td></tr><tr><td>Pucket</td><td colspan="3">Ks=156.96 exp(-0.198C)</td></tr><tr><td></td><td colspan="3">0~30 cm:Ks=-1.12lnC-2.78 lngg+3.14</td></tr><tr><td>新建PTFs</td><td colspan="3">30~60 cm:Ks=6.94×p-1.82×lnC-1.34</td></tr></table></body></html>

注： $C _ { _ { 1 } } , C _ { _ { 2 } } \setminus C _ { _ { 3 } }$ 为黏粒、粉粒、砂粒的含量 $( \% )$ ， $\rho \mathrm { ~ , ~ } C _ { \mathrm { ~ , ~ } }$ 为土壤容重 $\left( \mathrm { g } \cdot \mathrm { c m } ^ { - 3 } \right)$ 和土壤有机质含量 $( \mathbf { g } \cdot \mathbf { k } \mathbf { g } ^ { - 1 } ) , b$ 为与粒径有关的变量,0为土壤饱和含水率， $\sigma _ { _ { \mathrm { ~ g ~ } } }$ 为平均粒径的标准差。

![](images/93ce7c63aaddeb44e68587a752afddad11a37a1048606ae530c7dddb59203a5a.jpg)  
图5不同土层饱和导水率计算值与实测值对比  
Fig.5Comparisonbetweencalculatedand measured valuesofsaturated hydraulicconductivity indiferentsoillayers

由图6可以看出， $3 0 \sim 6 0 \mathrm { c m }$ 土层的 $K _ { s }$ 的计算值与实测值的绝对误差小于 $0 \sim 3 0 ~ \mathrm { c m }$ ，估算效果较好。两层土壤误差较大的原因不同， $0 \sim 3 0 ~ \mathrm { c m }$ 绝对误差的大小与土壤类型有关系，新建PTFs对于砂质壤土较为适用，绝对误差高值均出现在壤质砂土分布区域。 $3 0 \sim 6 0 ~ \mathrm { c m }$ 误差变化原因相对复杂，对于砂质壤土 $K _ { s }$ 的估算较为准确，对于壤质砂土、壤土误差较大。局部地区误差不具有规律性，如柴达木苏木东部，这可能与取样所处的地形、下垫面条件有关，结合实地观察，此区域存在局部砂土与砂质壤土相间，土壤类型较复杂，理化性质差异较大，且地形坡度较陡，新建PTFs并未考虑这些要素，进而导致估算误差较大。

![](images/e2f0277efeae7da00c0e822ef2dfa492f77441dfddd6d18f2a1ce69403b0063e.jpg)  
图6不同土层饱和导水率计算值及计算误差空间分布

# 3讨论与结论

# 3.1 讨论

土壤饱和导水率 $\left( K _ { s } \right)$ 虽然在田间测量和实验室分析都能得到准确数据，但由于测定方法的局限，费时费力，通过实测方法获取大尺度下的饱和导水率数据十分困难[31],因此，间接计算土壤饱和导水率具有重要意义。土壤饱和导水率PTFs建立时选择干容重与颗粒作为输入变量，与王改改等32]的研究结果一致，说明干容重与颗粒对饱和导水率起主导作用。Saxton相对于其他PTFs模型更适合于半干旱草原对于饱和导水率的推求,与黎明扬等[33]的研究结果相同，如果采用经验模型计算时，可以选择Saxton模型。砂粒含量随土层深度的增大而减少，与甘淼等[34所得规律相同。估算 $K _ { s }$ 的空间分布与施枫芝等[31]所得规律一致，不同土壤层饱和导水率分布具有相似性，深层土壤饱和导水率大于浅层。对于 $K _ { s }$ 在同一个地区，最大值与最小值差距较大，这可能是部分采样点位于坡地的凹部，局地疏松物质的堆积致使表层土壤疏松，容重较正常偏小，孔隙较多，导致饱和导水率呈现出较大变化。新建PTFs与孙丽等5所得结果的精度相近，虽然模型可用，但精度还有待于进一步提高。

土壤层 $K _ { s }$ 估算效果与取样数据受到人为因素影响，地形、坡度、植被覆盖等也是主要因素。基于Landsat8影像[35对巴拉格尔河流域进行NDVI计算（图7)，可以看出，研究区植被覆盖度较高，敖包邵仍、浩勒图高勒镇及达青宝力东部及南部地区植被茂盛，巴拉嘎尔苏木、柴达木苏木及浩勒图高勒镇北部植被相对稀少，巴彦胡苏木附近植被覆盖度最低，总体趋势植被茂盛程度由巴拉格尔河上游到下游逐渐降低，这种空间分布与土层 $K _ { s }$ 存在一定程度的相关性，因此，可以考虑基于土壤理化性质数据，在PTFs中融入NDVI数据，进一步提高土壤水力特性参数的估算精度。

廖凯华等通过对点估计、线性回归、非线性和人工神经网络进行对比，认为非线性模拟土壤水力特性参数效果较好，因此，将此方法也用于田间持水率的估算，估算精度(表6)与易湘生等[3相近。田间持水率传递函数估算效果优于饱和导水率土壤传递函数的估算效果

![](images/7734f8dbf98ab55ad5422cf6786778599c6b75c0582d4955fdfe36fb1fd81487.jpg)  
Fig.6Spatial distribution of the calculation error   
图7研究区NDVI空间分布Fig.7Spatial distribution of NDVI

# 表6土壤田间持水率传递函数及检验

Tab.6 Transfer-functions of soil water-holding ratio   

<html><body><table><tr><td rowspan="2">土层/cm</td><td colspan="3">检验指标</td><td rowspan="2">PTFs数学模型</td></tr><tr><td>r</td><td>SME</td><td>SRNSE</td></tr><tr><td>0~30</td><td>0.8</td><td>0</td><td>2.61</td><td>y = 1.73C4-25.35p+42.41</td></tr><tr><td>30~60</td><td>0.72</td><td>0</td><td>4.58</td><td>y=-23.8C4-0.50 +6.7lnC + 60.5</td></tr></table></body></html>

# 3.2结论

（1）巴拉格尔河草原流域以砂质壤土为主，随着根系层深度加大，砂质壤土含量减小，壤质砂土增多，土壤类型增多；不同层饱和导水率空间分布具有相似性，土壤深层大于表层的 $K _ { s }$ □

(2）植被根系层深层土壤的新建PTFs估算水力特性参数效果较好，估计偏差的大小与土壤类型有关，新建PTFs对于砂质壤土较为适用，偏差高值主要出现在壤质砂土分布区域;水力特性参数估算精度Saxton和Cosby劣于新建PTFs,但优于其他模型。

（3）草原植被NDVI空间分布与土壤层 $K _ { s }$ 存在一定程度的相关性，可以考虑基于土壤理化性质数据,在PTFs传递函数中融入NDVI数据，进一步提高土壤水力特性参数的估算精度。

研究成果对于内蒙古内陆河草原流域生态系统保护、降水入渗、土壤水运动和溶质运移等方面研究具有一定参考，可以为社会经济发展中的生态治理和农牧业管理提供科学依据

# 参考文献(References):

[1] 王改改,张玉龙,虞娜.多数据源土壤传递函数模型在水分模 拟中的不确定性[J].农业机械学报,2012,43(11):45-50. [Wang Gaigai, Zhang Yulong,Yu Na. Soil pedotransfer function of multiple data source and its uncertainty in water simulation[J]. Transactions of the Chinese Society for Agricultural Machinery, 2012,43(11): 45-50.]   
[2] 刘继龙,马孝义,张振华,等.基于联合多重分形的土壤水分特 征曲线土壤传递函数[J].农业机械学报,2012,43(3):51-56. [Liu Jilong,Ma Xiaoyi, Zhang Zhenhua,et al.Pedotransfer function of soil water retention curve based on joint multifractal[J]. Transactions of the Chinese Society for Agricultural Machinery, 2012,43(3): 51-56.]   
[3] NemesA,RobertsRT,RawlsWJ,etal.Software to estimate-33 and-15Oo kPa soil water retention using the non-parametric-nearest neighbor technique[J].Environmental Modelling & Software, 2008,23(2): 254-255.   
[4]朱安宁,张佳宝,陈效民,等.封丘地区土壤传递函数的研究[J]. 土壤学报,2003,40(1):53-58.[Zhu Anning,Zhang Jiabao,Chen Xiaomin,et al.Study on pedo-transfer function inFengqiu[J].Acta Pedologica Sinica,2003,40(1):53-58.]   
[5]孙丽,刘廷玺,段利民,等.科尔沁沙丘-草甸相间地区表土饱 和导水率的土壤传递函数研究[J].土壤学报,2015,52(1):68- 76.[Sun Li,Liu Tingxi,Duan Limin,etal.Prediction of saturated hydraulic conductivity of surface soil in sand-dune-and-meadow interlaced region of horqin with pedo-transfer fuctions method[J]. Acta Pedologica Sinica,2015,52(1): 68-76.]   
[6]廖凯华,徐绍辉,吴吉春,等.土壤饱和导水率空间预测的不确 定性分析[J].水科学进展,2012,23(2):200-205.[Liao Kaihua, Xu Shaohui,Wu Jichun,et al. Uncertainty analysis for spatial prediction of soil saturated hydraulic conductivity[J].Advances in Water Science,2012,23 (2): 200-205.]   
[7]Bouma J. Using soil surveydata for quantitative land evaluation[J]. Advances in Soil Science,1989,9: 177-233.   
[8]Tietje O, Hennings V.Accuracy of the saturated hydraulic conductivity prediction by pedo-transfer functions compared to the variability within FAO textural classes[J]. Geoderma,1996,69(1-2): 71-84.   
[9]Rawls W J, Gimenez D,Grossman R. Use of soil texture,bulk density,and slope of the water retention curve to predict saturated hydraulic conductivity[J]. Transactions of the Asae,1998,41(4): 983-988.   
[10] 刘建立,徐绍辉,刘慧.估计土壤水分特征曲线的间接方法研究 进展[J].水利学报,2004,35(2): 68-76.[Liu Jianli, Xu Shaohui, Liu Hui.A review of development in estimating soil water retention charateristics from soil data[J]. Journal of Hydraulic Engineering, 2004,35(2): 68-76.]   
[11]Campbell G S.Soil Physics with Basic: Transport Models for SoilPlant Systems[M].Amsterdam: Elsevier,1985.   
[12]Cosby BJ,Hornberger G M, Clapp RB,et al.A statistical exploration of the relationships of soil moisture characteristics to the physical properties of soils[J]. Water Resources Research,1984,20(6): 682-690.   
[13]Wosten JH M.Pedo-transfer functions to evaluate soil quality[C]// Gregorich EG,Carter MR. Soil Quality for Crop Production and Ecosystem Health.Amsterdam: Elsevier Science Publishers,1997, 25: 221-245.   
[14]Wosten JH M,Lilly A,Nemes A,et al. Development and use of a database of hydraulic properties of European soils[J]. Geoderma, 1999,90(3-4): 169-185.   
[15]Saxton K E,Rawls W J,Romberger J S.Estimating generalized soil water characteristics from texture[J]. Soil Science Society of America Journal,1986,50(4): 1031-1036.   
[16] Pucket WE,Dane JH, Hajek BF.Physical and mineralogical data to determine soil hydraulicproperties[J]. Soil Science Society of America Journal,1985,49(4): 831-836.   
[17]Rawls W J, Brakensiek DL. Prediction of soil water properties for hydrologic modeling[J].American Society of Civil Engineers, 1985: 293-299.   
[18] 姚姣转,刘廷玺,王天帅,等.科尔沁沙地土壤水分特征曲线传 递函数的构建与评估[J].农业工程学报,2014,30(20):98-108. [Yao Jiaozhuan,Liu Tingxi,Wang Tianshuai,et al.Development and evaluation of pre-transfer functions of soil water characteristic curves in Horqin sandy land[J]. Transaction of the CSAE,2014,30 (20): 98-108.]   
[19]Schaap M G,Leij FJ, Genuchten M TV. Rosetta: Acomputer program for estimating soil hydraulic parameters with hierarchical pedotransfer functions[J].Journal of Hydrology，2001,251(3): 163-176.   
[20] 廖凯华,徐绍辉,程桂福,等.基于不同PTFs的流域尺度土壤持 水特性空间变异性分析[J].土壤学报,2010,47(1):33-41.[Liao Kaihua,Xu Shaohui, Cheng Guifu,et al. Spatial variability analysis of soil water retention capability at basin scale based on different PTFS.[J].Acta PedologicaSinica,2010,47(1):341.]   
[21]王志强.科尔沁沙地土壤水力特性的推算[D].呼和浩特:内蒙 古农业大学,2003.[Wang Zhiqiang.Estimationof Soil Hydraulic Characteristics Properties of Keerqin Sandy land[D].Hohhot: Inner Mongolia Agricultural University,2003.]   
[22] 邹刚华,李勇,李裕元,等.亚热带小流域稻田土壤饱和导水率 传递函数构建[J].土壤通报,2013,44(2):302-307.[Zou Ganghua, Li Yong, Li Yuyuan, et al. Developing a pedo-transfer function for estimating saturated soil hydraulic conductivity of paddy soils of a catchment in southern subtropical China[J]. Chinese Journal of Soil Science,2013,44 (2): 302-307.]   
[23] 刘继龙,马孝义,张振华.土壤入渗特性的空间变异性及土壤转 换函数[J].水科学进展,2010,21(2): 214-221.[Liu Jilong,Ma Xiaoyi, Zhang Zhenhua.Spatial variabilityof soil infiltration characteristics and its pedo-transfer function [J].Advances in Water Science,2010,21(2): 214-221.]   
[24]Stumpp C,Engelhardt S,Hofmann M,et al.Evaluation of pedotransfer functions for estimating soil hydraulic properties of prevalent soils in a catchment of the Bavarian Alps[J]. European Journal of Forest Research,2009,128(6): 609-620.   
[25]Minasny B,McBratney A B.The neuro-m method for fitting neural network parametric pedotransfer functions[J]. Soil Science Society of America Journal,2002,66(2): 352-361.   
[26] 张均华,刘建立,张佳宝,等.常熟地区水稻土饱和导水率的间 接方法研究[J].土壤通报,2010,41(4):778-782.[Zhang Junhua, Liu Jianli, Zhang Jiabao,et al. Indirect method to estimate saturated soil hydraulic conductivity in paddy soil of Changchun[J]. Journal of Soil Science,2010,41(4): 778-782.]   
[27]孙美,张晓琳,冯绍元,等.基于交叉验证的农田土壤饱和导水 率传递函数研究[J].农业机械学报,2014,45(10):147-152. [Sun Mei, Zhang Xiaolin, Feng Shaoyuan, et al.Pedo-transfer function for saturated hydraulic conductivity of agricultural soil based on cross-validation[J].Transactions of the Chinese Society forAgricultural Machinery,2014,45(10): 147-152.]   
[28]汪明星.重庆山地丘陵区紫色土饱和导水率传递函数研究[D]. 重庆：西南大学,2017.[Wang Mingxing. Study on Pedo-transfer function of Saturated Hydraulic Conductivity of Purple Soil in Hilly AreasofChongqingD].Chongqing:Southwest Universty 2017.]   
[29] 张保刚,梁慧春.草地土壤机械组成研究综述[J].辽宁农业科 学,2009(6): 38-41. [Zhang Baogang, Liang Huichun. Review of grassand soil mechanical composition research[J]. Liaoning Agricultural Sciences,2009(6): 38-41.]   
[30] 吴克宁,赵瑞.土壤质地分类及其在我国应用探讨[J].土壤学 报,2019,56(1): 227-241.[Wu Kening,Zhao Rui. Soil texture classification and itsapplication in China [J].Acta Pedologica Sinica,2019,56 (1): 227-241.]   
[31] 施枫芝,赵成义,叶柏松,等.基于PTFs的干旱地区土壤饱和导 水率的尺度扩展[J].中国沙漠,2014,34(6):1584-1589.[Shi Fengzhi, Zhao Chengyi, Ye Baisong,et al. The scaling-up of soil saturated hydraulicconductivity based on PTFs in aridarea[J]. Journal of Desert Research,2014,34(6): 1584-1589.]   
[32] 李祥东,邵明安,赵春雷.西北干旱区土壤水力参数空间变异与 模拟[J].干旱区研究,2019,36(6):1325-1332.[Li Xiangdong, Shao Mingan, Zhao Chunlei. Spatial variation and simulation of soil hydraulic parameters in northwest arid region[J].Arid Zone Research,2019,36(6): 1325-1332.]   
[33] 黎明扬,刘廷玺,罗艳云,等.半干旱草原型流域表层土壤饱和 导水率传递函数及遥感反演研究[J].土壤学报,2019,56(1): 90-100.[Li Mingyang,Liu Tingxi,Luo Yanyun,et al. Pedo-transfer function and remote-sensing-based inversion saturated hydraulic conductivity of surface soil layer in Xilin River basin[J].Acta Pedologica Sinica,2019,56(1): 90-100.]   
[34] 甘淼,贾玉华,李同川.黄土区坡沟系统容重、饱和导水率和土 壤含水量变化分析[J].干旱区研究,2018,35(2):315-324.[Gan miao, Jia Yuhua,Li Tongchuan.Variation analysis of bulk density,saturated hydraulic conductivity and soil moisture content in a slope-gully unit on the Northern Loess Plateau[J].Arid Zone Research,2018,35(2):315-324.]   
[35]马驰.基于Landsat 8吉林中北部地区土壤有机质定量反演研 究[J].干旱区资源与环境,2017,31(2):167-172.[Ma Chi. Study on the quantitative retyieval of soil organic matter in the north and middle part of Jilin based on Landsat 8[J]. Journal of Arid Land Resources and Environment,2017,31(2): 167-172.]   
[36] 易湘生,李国胜,尹衍雨.青海三江源地区土壤水分常数转换 函数的建立与比较[J].中国生态农业学报,2012,20(8):1096- 1104.[Yi Xiangsheng,Li Guosheng,Yin Yanyu.Establishment and comparison of pedotransfer functions of soil moisture constant in the Three-River headwaters region of Qinghai province [J]. Chinese Journal of Eco- Agriculture,2012,20 (8):1096- 1104.]

# Construction and evaluation of pedo-transfer functions in the Balager River Basin

FANG Li-jing'， GAO Rui-zhong1²， LIU Ting-xi'²， ZHANG A-long'， WANG Xi-xi3 (1.InstituteofWater Conservancy and Civil Engineering,Inner Mongolia Agricultural University,Hohhot 010018,Inner Mongolia, China; 2.Inner Mongolia Key Laboratory of Water Resources Protectionand Utilization, Hohhot 010018,Inner Mongolia,China;3.Old Dominion University,Norfolk 23529,USA)

Abstract:It is important to understand thesoil characteristics of thegrass rot layer for therestoration and protection of the grassland ecosystem.The pedo-transfer functions (PTFs) based on soil physical and chemical property data were the primary means to indirectly obtain soil hydraulic parameters.The Inner Mongolian Balager River Basin was selected as the typical study area,and 102 soil samples were collcted in the depths of O to 60 cm of the grass roots.The indices of soil physical,chemical,and hydraulic characteristics were tested,including particle size distribution,dry density,organic mater,saturated hydraulic conductivity,and water-holding capacity. Kriging and principal component analysis were used for revealing the spatial pattrnof thesoil physical,chemical, and hydraulic characteristics parameters in the plateau inland grassand basin.Taking soil saturated hydraulic conductivity ( $K _ { s }$ ), for instance,the transfer functions were built and validated. The results showed that (1) sandy loam was the main soil,and sandy loam content decreased and loamy sandy increased with the soil depth increasing in the study area; (2) $K _ { s }$ spatial distribution of different soil layers was similar,and the $K _ { s }$ of deeper layer soil was biggerthan that of the surface layer;(3)the simulation effect of the new transferfunction was beter in depths of 30- 60 cm of soil layer,and ther, $\delta _ { \mathrm { { \scriptscriptstyle M E } } }$ ,and $\delta _ { \mathrm { R M S E } }$ were 0.73,O,and 1.62 respectively; and (4) the calculated error was related to the soil type,and the new PTFs of sandy loam was beter than loamy sandy.

Keywords: grass root soil;； hydraulic parameter; soil classification; transfer function； Balager River Basin