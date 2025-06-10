# 基于不同卫星光谱模拟的土壤电导率估算研究

曹肖奕,²，丁建丽1,2.3，葛翔宇1,²，梁，静²，陈 陈文倩1,2.,3，陈香月1,²，唐普恩1,2

(1新疆大学资源与环境科学学院,新疆乌鲁木齐830046；2新疆大学绿洲生态教育部重点实验室,新疆乌鲁木齐830046；3新疆大学智慧城市与环境建模自治区普通高校重点实验室,新疆乌鲁木齐830046)

摘要：土壤电导率（Electricalconductivity， $E C$ )是评价土壤盐渍化的重要指标。通过实测新疆艾比湖湿地自然保护区土壤EC及可见光—近红外光谱数据，利用波谱响应技术模拟Landsat8OLI、Sentinel2、Sentinel3卫星的宽波段数据。构建宽波段模拟数据及其5种预处理后的三维光谱指数（Three-dimensional spectral index,TDSI），采用梯度提升回归树算法（Gradientboostingregressiontree，GBRT）建立3种卫星土壤 $E C$ 估算模型，并比对加入TDSI后模型精度的变化。结果表明：在不同土壤 $E C$ 条件下,3种卫星具有相似的光谱趋势,均在红、近红外波段附近反射率较高;TDSI与土壤EC 相关性基本均在0.4以上，最大程度保留了与土壤 $E C$ 敏感度高的红、绿、蓝、近红外、短波红外波段信息;GBRT对于土壤 $E C$ 估算能力表现突出,3种卫星对土壤 $E C$ 的最佳预测精度 $R ^ { 2 }$ 分别为 $0 . 8 3 1 \ 、 0 . 8 4 7 \ 、 0 . 9 0 3$ ，在加入TDSI后， $R ^ { 2 }$ 分别提高至 $0 . 8 3 5 , 0 . 8 5 7 , 0 . 9 3 5$ ，综合分析发现，Sentinel3对土壤 $E C$ 估算效果最佳（ $R ^ { 2 } = 0 . 9 3 5$ ,均方根误差 $R M S E = 2 . 9 8 6 ~ \mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ ，赤池信息准则$A I C = 5 7 . 5 0 0$ ）。通过利用波谱响应技术结合TDSI深度挖掘波段间的协同信息，采用GBRT验证了不同卫星对土壤 $\ E C$ 的估算效果，二者相结合可以有效提升模型预测精度，为干旱区土壤盐渍化定量监测与防控提供有利指导。

关键词：波谱响应；土壤电导率；光谱预处理；三维光谱指数；梯度提升回归树文章编号： 1000-6060(2020)01-0172-10(0172\~0181)

土壤盐渍化是中亚乃至全球干旱区重要的环境问题之一，它不仅阻碍植物的正常生长，影响农业系统的生产力，同时还在一定程度上造成土地退化[1-2]。新疆维吾尔自治区位于我国西北干旱区,是国家重要的粮食产业基地，为确保稳定的粮食产出和粮食安全，及时监测和防控土壤盐渍化显得十分必要[3]。因此,实现干旱区土壤盐分的精准监测和有效管理对该区域可持续发展和维持生态稳定具有重要意义。

地物光谱特征作为遥感技术及应用中的重要物理基础与理论依据，是反映地物信息的有效手段，已有众多国内外学者在土壤、植被、水体等领域开展地物光谱相关研究工作[4-5]。地物光谱能够准确反映地物的光谱特性，常见的光谱研究形式主要有光谱预处理法、光谱指数法等，光谱预处理能够有效减少背景噪声，增强光谱特征，而通过构建光谱指数则可以深度挖掘光谱间的协同信息、减少信息冗余，并在一定程度上提升对地物的响应程度[6]。但现阶段光谱指数大多仅考虑两波段间的相互关系，这可能会忽略部分地物敏感信息，造成估算偏差，而三维光谱指数在增加一维波段的基础上，增加了光谱有效信息，尽可能地保证了估算精度，是光谱指数研究的新思路。

传统的土壤盐分监测依靠野外实地采样、实验室室内理化分析的方法，该方法虽具有较高测量精度，但难以满足大尺度上的监测需求。遥感技术依靠其覆盖范围广、时间连续性强等优点，成功实现宏观、多时相的土壤盐分监测，为土壤盐渍化的监测和防控提供了有利保障[7]。当前,相关研究主要集中于利用不同遥感数据针对不同区域的土壤盐渍化信息反演，并将实测样点数据与遥感反演数据进行精度评估，结合不同模型实现土壤盐渍化信息监测[8-9]。其中,部分学者还探讨不同算法对土壤盐分的估算精度，进而选择最佳算法实现土壤盐分的精确估算[10-12]。在以上研究分析中发现,利用遥感数据反演土壤盐渍化信息是切实可行的监测手段，且研究结果表明，土壤电导率与土壤盐渍化具有较高的相关性，可在一定程度上作为衡量盐渍化程度的指标[13]。通过既得文献梳理归纳发现,利用地物实测光谱数据模拟不同卫星传感器波段信息，将近感与遥感技术协同融合，进而实现土壤盐分定量监测的研究尚不多见。新疆地区土壤盐渍化类型丰富，程度复杂，在全球干旱区的土壤盐渍化研究中非常典型，加之该区域下垫面均一，数据获取质量较高，因此，尝试利用地物实测光谱与遥感卫星传感器进行波谱响应研究，以期为全球十旱区的土壤盐渍化精确监测与数字制图提供依据。

本研究以新疆维吾尔自治区艾比湖湿地自然保护区为研究靶区，通过实测光谱数据模拟Landsat8OLI、Sentinel2、Sentinel3宽波段，利用多种预处理方式构建三维光谱指数（Three-dimensional spectralindex，TDSI)，遴选最优光谱指数。将实测土壤电导率（Electrical conductivity， $E C$ )数据结合梯度提升回归树算法（Gradient boosting regression tree,GBRT)建立土壤EC估算模型,并比较三种卫星对土壤EC的估算潜力，为干旱区土壤盐渍化监测与防控提供有利指导。

# 1研究区概况与方法

# 1.1 研究区概况

艾比湖湿地地处博尔塔拉蒙古自治州，位于天山北麓准葛尔盆地西南隅 ( $4 3 ^ { \circ } 3 8 ^ { \prime } \sim 4 5 ^ { \circ } 5 2 ^ { \prime } \mathrm { N }$ $7 9 ^ { \circ } 5 3 ^ { \prime } \sim 8 5 ^ { \circ } 0 2 ^ { \prime } \mathrm { E } ^ { \prime }$ ),是典型的干旱区尾闾盐湖湿地。该区域全年平均降水量约为 $1 0 5 ~ \mathrm { m m }$ ,年均潜在蒸发量 $1 \ 3 1 5 \ \mathrm { m m }$ ,年均温 $8 . 3 ~ \mathrm { { ^ { \circ } C } }$ ，王壤类型以荒漠土、灰漠土为主要，主要植被有怪柳（Tamarix）、盐节木(Halocnemumstrabliaceum）盐爪爪（Kalidium foliatum)等[14-15]。由于处在大陆腹地,加之特殊的地形地貌，全年大风、沙尘、浮尘天气现象频发。受自然和人为因素的影响，艾比湖湖面面积持续缩减，土壤盐渍化程度不断加剧，严重危害当地的生态环境与农业生产。

# 1.2土壤样品采集与土壤EC 分析

2018年7月研究团队依据研究区景观类型，选取绿洲、荒漠以及交错带等景观，按照五点采样法采集 $0 \sim 1 0 \ \mathrm { c m }$ 土壤样品共计40个，用样品袋封装带回实验室。经过自然干燥后，研磨通过 $2 \ \mathrm { m m }$ 孔筛，并将每个样品分为2份，分别用来测定土壤EC和可见光—近红外光谱数据（Visibleandnearinfrared，VIS-NIR）。过筛后的土壤样品按照土水质量比1：5的比例提取土壤浸出液，使用德国WissenschaftlichTechnischeWerkstätten公司生产的Cond731O型土壤测试仪测定土壤 $E C$ 。

# 1.3 光谱采集

利用美国Analytical SpectralDevices公司生产的ASDFieldSpec3型光谱仪（波段 $3 5 0 \sim 2 ~ 5 0 0 ~ \mathrm { n m } ,$ ，在暗室内测定样品的VIS-NIR数据。将制备好的40个土壤样品分别装入直径为 $1 2 \ \mathrm { c m }$ 、深 $3 \ \mathrm { c m }$ 盛样皿中，将表面刮平。光源为50W的卤素灯，距土壤样品表面 $5 0 ~ \mathrm { c m }$ ,天顶角为 $1 5 ^ { \mathrm { ~ \circ ~ } }$ ,探头至待测样品的表面距离为 $1 0 \ \mathrm { c m }$ ，每次光谱测定之前均进行白板标定以消除暗电流的影响[16]。本实验各土壤样品于8个方向共采集24条光谱曲线，取24条光谱曲线的算术平均值作为该土样的原始光谱数据。

# 1.4卫星宽波段光谱模拟及预处理

使用ENVI5.5软件中内置的光谱重采样功能，利用Landsat8OLISentinel2、Sentinel3卫星各自的波谱响应函数（图1），将实测VIS-NIR数据模拟重采样为每个卫星传感器的宽波段反射率数据，再利用 ENVI5.5、MatlabR2016b 软件对其进行一阶微分（Firstderivative，FD）、二阶微分（Secondderiva-tive,SD）连续统去除（Continuumremoval,CR）、吸光度变换（Absorbance，ABS）多元散射校正（Mult-ivariate scatteringcorrection,MSC)5种预处理。光谱模拟计算公式为：

$$
\begin{array} { r } { R \ = \frac { \displaystyle \sum _ { \lambda = \lambda _ { \operatorname* { m i n } } } ^ { \lambda _ { \operatorname* { m a x } } } S _ { \lambda } R _ { \lambda } } { \displaystyle \sum _ { \lambda = \lambda _ { \operatorname* { m i n } } } ^ { \lambda _ { \operatorname* { m a x } } } S _ { \lambda } } } \end{array}
$$

式中： $R$ 为模拟卫星宽波段的反射率; $\lambda _ { \operatorname* { m a x } } \setminus \lambda _ { \operatorname* { m i n } }$ 为传

![](images/2f4acc367f9cb21c33c69af6e2ed8868e65f6d129f44c4cfba66bfeb73323154.jpg)  
图13种卫星波谱响应函数图  
Fig.1Spectrum response function of three satellites

感器光谱探测的起始和终止波长； $S _ { \lambda }$ 为传感器在 $\lambda$ 波长处的波谱响应函数值； $R _ { \lambda }$ 为土壤光谱在 $\lambda$ 波长处的反射率。

# 1.5 三维相关系数

光谱指数通过波段间简单组合即可提高光谱信息的利用率，降低信息冗余度，最大程度上保留土壤EC 的敏感光谱信息[17-18]。光谱指数与土壤 $E C$ 间的三维相关系数可以提供关于土壤EC的3个独立波段组合的综合信息，进一步考虑波段间的协同作用，增加相关信息量，为后续提升模型预测精度奠定基础。本研究构建两种TDSI：

$$
T D S I _ { 1 } = ( R _ { \lambda 1 } - R _ { \lambda 2 } ) \bigg / ( R _ { \lambda 2 } - R _ { \lambda 3 } )
$$

$$
\begin{array} { c } { { T D S I _ { 2 } = \left( R _ { _ { \lambda 1 } } - R _ { _ { \lambda 2 } } \right) \bigg / \left[ \left( R _ { _ { \lambda 1 } } - R _ { _ { \lambda 2 } } \right) - \right. } } \\ { { \left. \left( R _ { _ { \lambda 2 } } - R _ { _ { \lambda 3 } } \right) \right] } } \end{array}
$$

式中： $R _ { \lambda 1 } \ 、 R _ { \lambda 2 } 、 R _ { \lambda 3 }$ 分别为波长在 $\lambda _ { 1 } , \lambda _ { 2 } , \lambda _ { 3 }$ 处的反射率。

光谱指数与土壤 $E C$ 的相关性计算以及三维相关系数图的呈现均在MatlabR2016b中实现

# 1.6集合划分与建模方法

本研究采用基于联合 $\cdot - y$ 距离方法（Simple setportioning based on joint $x$ -ydistance,SPXY)对40个样本进行划分，该方法能够有效覆盖到所有样本，增加模型预测稳定性。基于SPXY方法是综合考量了光谱反射率向量与土壤 $E C$ 向量的情况下，确保样本在上述两个向量空间中具有相同的权重，本文最终确定了30个建模集样本,10个验证集样本[19]

本研究采用GBRT算法构建土壤EC估算模型，该算法是由FRIEDMAN提出的一种迭代的决策树算法[20],旨在通过集成若干个弱学习器,经过多次迭代最终组合而成一个强学习器，每一次迭代都在上一次迭代的基础上减少残差，并改进上一次的计算结果，同时根据残差减少的梯度方向来构建新的组合模型。模型预测的运算机制大体为：输入一个样本实例，首先对其赋予一个初始值，之后遍历每一棵决策树，每棵树都会有不同的权值，并且对预测值进行相应地调整修正，最终的结果是将每一棵决策树的结果累加得到最后的预测结果，计算公式如下：

$$
\begin{array} { c } { { f ( x ) = F _ { \mathrm { 0 } } + \beta _ { \mathrm { 1 } } T _ { \mathrm { 1 } } ( X ) + \beta _ { \mathrm { 2 } } T _ { \mathrm { 2 } } ( X ) + \cdots + } } \\ { { } } \\ { { \beta _ { M } T _ { M } ( X ) } } \end{array}
$$

式中： $F _ { \mathrm { 0 } }$ 为初值； $\beta$ 为权重系数; $T ( X )$ 为每一棵决策树的结果。

# 1.7 建模精度评价

为量化模型的拟合度，评价模型的估算能力，本研究选用决定系数（Coefficientofdetermination,$R ^ { 2 }$ ）、均方根误差（Root mean squared error,RMSE）和赤池信息准则（AkaikeInformation Criterion,AIC）3种参数来进行评估。 $A I C$ 准则是检验统计模型拟合度的一项指标，其基于熵的概念，平衡模型构建中的偏差和方差，一般认为， $A I C$ 值越低代表模型拟合效果越好[21]。 $A I C$ 计算公式如下：

$$
A I C \ = \ n \log \left( { \frac { S S R } { n } } \right) \ + 2 k
$$

式中： $n$ 是样本量; $S S R$ 是模型拟合残差平方和； $k$ 是模型自由变量个数。

# 2结果分析

# 2.1样本土壤 $E C$ 统计分析

表1为土壤 $E C$ 的特征统计描述。全样本土壤$E C$ 均值为 $7 . 2 4 0 ~ \mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ ,标准差为7.586,建模集与验证集各自均值分别为 $7 . ~ 1 7 5 ~ \mathrm { \ m S ~ } \cdot \mathrm { ~ c m ~ } ^ { - 1 }$ $7 . 8 6 0 ~ \mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ ,各自标准差分别为7.270、8.791，全样本均值与标准差均介于建模集与验证集之间。

# 2.2不同卫星宽波段模拟反射率分析

图2为不同土壤 $E C$ 对3种卫星宽波段模拟反射率的影响。分析图2可以得知，随着土壤 $E C$ 的增加，Landsat8OLI、Sentinel2、Sentinel3各波段的反射率也相应增高，其中反射率最低波段均为B1$( 0 . 4 3 3 \sim 0 . ~ 4 5 3 ~ \mu \mathrm { m } , 0 . ~ 4 2 9 \sim 0 . ~ 4 5 7 ~ \mu \mathrm { m } , 0 . ~ 3 9 1 ~ \sim$ $0 . 4 0 9 ~ \mu \mathrm { m } \dot { }$ ），而反射率最高波段分别为B6（ $1 . 5 6 1 \sim$ $1 . 6 5 1 ~ { \mu \mathrm { m } }$ ）、B11（ $( 1 . \ 5 6 2 \ \sim \ 1 . \ 6 6 3 \ \mu \mathrm { m } )$ 、B21$( 0 . 9 9 7 \sim 1 . 0 1 7 ~ \mu \mathrm { m } )$ 。3种卫星光谱反射率整体上均呈升高趋势,在Landsat8OLI与Sentinel2中，短波红外波段（B7、B12）反射率均略微下降，Sentinel3反射率则持续升高。3种卫星均存在反射率陡增的波段,Landsat8OLI为B4（ $0 . 6 3 0 \sim 0 . 6 8 0 ~ \mu \mathrm { m } ,$ ）B5( $0 . 8 4 5 \sim 0 . 8 8 5 ~ { \mu \mathrm { m } }$ ）,Sentinel2为B4（ $\left( 0 . 6 4 1 \sim \right.$ $0 . 6 9 0 ~ { \mu \mathrm { m } }$ ）、B10（ $1 . 3 5 5 \sim 1 . 3 9 3 ~ { \mu \mathrm { m } } ,$ ）,Sentinel3为B7 $( 0 . 6 1 3 \sim 0 . 6 2 8 ~ \mu \mathrm { m }$ ）、B12（ $0 . 7 4 8 \sim 0 . 7 6 0 ~ { \mu \mathrm { m } }$ ）、

表1土壤样品 EC 特征统计 $/ \mathbf { m } \mathbf { S } \cdot \mathbf { c m } ^ { - 1 }$   
Tab.1Statistical characteristics of soil electrical conductivity of soil samples $/ \mathrm { \bf m } \mathrm { \bf S } \cdot \mathrm { c m } ^ { - 1 }$   

<html><body><table><tr><td>样本类型</td><td>样本数</td><td>最大值</td><td>最小值</td><td>均值</td><td>标准差</td></tr><tr><td>全集</td><td>40</td><td>28.079</td><td>0.059</td><td>7.240</td><td>7.586</td></tr><tr><td>建模集</td><td>30</td><td>28.079</td><td>0.059</td><td>7.175</td><td>7.270</td></tr><tr><td>验证集</td><td>10</td><td>27.309</td><td>0.466</td><td>7.860</td><td>8.791</td></tr></table></body></html>

B17 $( 0 . 8 5 3 \sim 0 . 8 7 3 \ \mu \mathrm { m } )$ 。通过分析发现，不同卫星反射率最高、陡增波段大致均位于红光、近红外附近,这与前人研究结果一致[22-23],主要是由于土壤中 $\mathrm { O H } ^ { - 1 }$ 、Si-OH键以及土壤硅酸盐矿物及其他阳离子的影响。

# 2.3 三维相关系数分析

在 MatlabR2016b软件中，计算3种卫星基于宽波段模拟数据及5种预处理方式与土壤 $E C$ 的相关系数，最终得到6种光谱形式下的 $T D S I _ { 1 } \setminus T D S I _ { 2 }$ 的三维相关系数。

通过表2可知，在3种卫星不同光谱形式的三维相关系数中，仅基于CR预处理下Landsat8OLI卫星的 $T D S I _ { 1 } \setminus T D S I _ { 2 }$ 以及Sentinel2卫星的 $T D S I _ { 1 }$ 在0.01水平上不显著（显著性检验阈值 $P _ { * * } = \pm$ 0.403）。在Landsat8OLI卫星中，基于ABS预处理下三维相关系数最高，分别为 $0 . 6 2 5 , - 0 . 6 2 6$ ；在Sentinel2、Sentinel3卫星中,基于SD预处理下 $T D S I _ { 1 }$ 三维相关系数均最高，分别为 $- 0 . 6 3 4 , - 0 . 7 2 0$ ,基于ABS预处理下 $T D S I _ { 2 }$ 三维相关系数同样最高，分别为 $- 0 . 6 0 0 _ { \setminus } - 0 . 6 7 8$ 。已有研究表明，土壤盐分在蓝红光、近红外、短波红外附近具有较高的敏感程度[23],而通过分析表2中通过指数所遴选出的波段可以发现,大部分波段同样分布在上述范围内，少许分布在绿光附近，这与已有研究结果相吻合，充分映证了三维光谱指数在兼顾遥感光谱机理的同时，最大程度上保留了土壤EC的相关信息，具有一定的合理性与科学性。图3列出3种卫星代表性的三维相关系数图。

# 2.4不同卫星土壤EC建模分析

将3种卫星宽波段模拟数据及预处理数据分别作为土壤EC估算模型的独立变量，实测土壤EC数

0.7 不同土壤 $\mathrm { E C / m S \cdot { c m } ^ { - 1 } }$ 0.7-不同土壤 $E C / \mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ 0.7-不同土壤EC/mS·cm-11.638 ? ? ·1.638 ·1.6380.6 ·2.460 △ 0.6 ·2.460 0.6 ·2.460密南区 504 5850 →区 ■ . 1 11:111 8 :0 业鑫1 8 ， Y0.3 0.3 0.30 1 2 3 4 5 6 7 8 0123456788A910111213 0 2 4 6 81012141618 20 22波段号 波段号 波段号

表23种卫星不同预处理下三维相关参数  
Tab.2Three-dimensional correlation parameters of three satellites under different pretreatment   

<html><body><table><tr><td>卫星</td><td>光谱形式</td><td>TDSI</td><td>相关系数(r)</td><td>TDSI2</td><td>相关系数(r)</td></tr><tr><td>Landsat 8 OLI</td><td>R</td><td>B1、B3、B2</td><td>-0.594</td><td>B2、B3、B1</td><td>-0.595</td></tr><tr><td></td><td>FD</td><td>B1、B6、B2</td><td>-0.599</td><td>B1、B2、B6</td><td>-0.604</td></tr><tr><td></td><td>SD</td><td>B2、B7、B5</td><td>0.423</td><td>B6、B3、B4</td><td>-0.415</td></tr><tr><td></td><td>CR</td><td>B1、B1、B1</td><td>0</td><td>B1、B1、B1</td><td>0</td></tr><tr><td></td><td>ABS</td><td>B2、B3、B1</td><td>0.625</td><td>B2、B3、B1</td><td>-0.626</td></tr><tr><td></td><td>MSC</td><td>B1、B3、B2</td><td>-0.594</td><td>B1、B3、B2</td><td>0.594</td></tr><tr><td>Sentinel 2</td><td>R</td><td>B1、B3、B2</td><td>-0.567</td><td>B1、B3、B2</td><td>0.567</td></tr><tr><td></td><td>FD</td><td>B1、B10、B2</td><td>-0.595</td><td>B1、B10、B2</td><td>0.589</td></tr><tr><td></td><td>SD</td><td>B2、B6、B4</td><td>-0.634</td><td>B4、B8A、B3</td><td>-0.583</td></tr><tr><td></td><td>CR</td><td>B3、B4、B2</td><td>-0.363</td><td>B5、B8、B2</td><td>0.518</td></tr><tr><td></td><td>ABS</td><td>B2、B1、B3</td><td>-0.599</td><td>B2、B3、B1</td><td>-0.600</td></tr><tr><td></td><td>MSC</td><td>B1、B2、B3</td><td>-0.567</td><td>B1、B3、B2</td><td>0.567</td></tr><tr><td>Sentinel 3</td><td>R</td><td>B3、B5、B4</td><td>-0.675</td><td>B3、B5、B4</td><td>0.673</td></tr><tr><td></td><td>FD</td><td>B17、B18、B8</td><td>-0.583</td><td>B8、B18、B9</td><td>-0.597</td></tr><tr><td></td><td>SD</td><td>B5、B10、B7</td><td>-0.720</td><td>B10、B8、B12</td><td>0.579</td></tr><tr><td></td><td>CR</td><td>B4、B5、B2</td><td>-0.468</td><td>B5、B17、B12</td><td>- 0.565</td></tr><tr><td></td><td>ABS</td><td>B3、B5、B4</td><td>-0.684</td><td>B4、B5、B3</td><td>-0.678</td></tr><tr><td></td><td>MSC</td><td>B3、B5、B4</td><td>-0.675</td><td>B3、B5、B4</td><td>0.673</td></tr></table></body></html>

0.634 0.720 0.625 12378677 0.375 24 0.380 36 0.432   
音 0.125 号6 8 -.127 0141 -0.375 12, -0.380 2121 -0.432 波段号 66 4 波段号 67 -0.625 1086 波段号 42 24 681012 波段号 -0.634 19612 波段号 9 63 36912151821 波段号 -0.720 TDSILandsat 8 OLI_ABS TDSISentinel 2_SD TDSI1 Sentinel 3_SD 0.60 0.678 0.626   
12 0.376 2 0.36 369 0.407 4 0.125 6802 0.12 多 2582 0.36 波段号 16643 112345 波段号 6 -0.376 -0.626 1210 波段号 86 42 2 4 6810 波段号 12 -0.60 -0.36 21 波段号 195129 63 369121518 波段号 21 -0.407 -0.678 TDSI Landsat8OLI_ABS TDSI Sentinel 2_ABS TDSI Sentinel 3_ABS

据作为响应变量，结合GBRT算法构建土壤EC 估算模型，分析3种卫星不同光谱形式对土壤 $E C$ 的估算效果，模型结果、精度评价如表3所示。

由表3可知，Landsat8OLI卫星基于FD预处理的土壤 $E C$ 估算精度最佳（ $\mathit { \Delta } R ^ { 2 } = 0 . 8 3 1 , R M S E =$ $4 . 4 8 4 ~ \mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ $A I C = 2 9 . 0 3 4$ ）,基于CR预处理的土壤 $E C$ 估算精度最低（ $R ^ { 2 } = 0 , 3 2 0$ ， $R M S E = 6 . 9 3 9$ $\mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ $A I C = 3 2 . 8 2 5$ ),各光谱形式的估算精度依次为 $\mathrm { F D } > \mathrm { M S C } > \mathrm { S D } > \mathrm { R } > \mathrm { A B S } > \mathrm { C R }$ 。Sentinel 2卫星基于 SD 预处理的土壤 $E C$ 估算精度最佳( $R ^ { 2 } = { }$ 0.847, $R M S E = 4 . 9 3 1 \mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ ， $A I C = 4 0 . 9 8 9$ ），基于R的土壤 $E C$ 估算精度最低（ $( R ^ { 2 } = 0 , 4 3 6$ ，$R M S E = 6 . 6 0 5 ~ \mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ ， $A I C = 4 4 . 3 9 8 { \mathrm { ~ } }$ ），各光谱形式的估算精度依次为 $\mathrm { S D } > \mathrm { F D } > \mathrm { M S C } > \mathrm { C R } > \mathrm { A B S } >$ R。Sentinel3卫星基于SD预处理的土壤 $E C$ 估算精度最佳( $= 0 . \ 9 0 3 \mathrm { \ : , } R M S E = 3 . \ 5 1 5 \mathrm { \ : \ m S \cdot \ c m \textsuperscript { - 1 } }$ ，$A I C = 5 4 . 9 1 8$ )，基于R的土壤 $\ E C$ 估算精度最低0 $\langle R ^ { 2 } = 0 . 3 5 9$ $= 0 . 3 5 9 , R M S E = 6 . 9 0 0 ~ \mathrm { { \ m S } ~ \cdot ~ \ c m ~ ^ { - 1 } }$ ， $A I C =$ （2060.777），各光谱形式的估算精度依次为 $\mathrm { S D } > \mathrm { M S C }$ $> \mathrm { F D } > \mathrm { C R } > \mathrm { A B S } > \mathrm { R }$ 。综合比较最佳估算精度后认为，Sentinel3对于土壤 $E C$ 的估算效果最好，其次为Sentinel2,最后为Landsat $8 ~ \mathrm { O L I }$ 。图4为3种卫星在构建土壤 $E C$ 估算模型中各波段的重要性，分析发现3种卫星重要性较大的波段主要是蓝波段、红波段、近红外波段、短波红外波段以及绿波段,这与前文所得发现一致。

表33种卫星宽波段模拟土壤EC估算结果  
Tab.3Results of soil EC estimation for broadband simulation of three satellites   

<html><body><table><tr><td rowspan="2">卫星</td><td rowspan="2">光谱形式</td><td rowspan="2">参量</td><td colspan="2">建模集</td><td colspan="3">验证集</td></tr><tr><td>RMSE／mS·cm-1</td><td>R²</td><td>RMSE／mS·cm-1</td><td>R²</td><td>AIC</td></tr><tr><td>Landsat 8 OLI</td><td>R</td><td>7</td><td>4.422</td><td>0.774</td><td>6.627</td><td>0.434</td><td>32. 427</td></tr><tr><td rowspan="10">Sentinel 2</td><td>FD</td><td>7</td><td>3.884</td><td>0.829</td><td>4.484</td><td>0.831</td><td>29.034</td></tr><tr><td>SD</td><td>7</td><td>3.570</td><td>0.823</td><td>5.198</td><td>0.772</td><td>30.317</td></tr><tr><td>CR</td><td>7</td><td>5.478</td><td>0.521</td><td>6.939</td><td>0.320</td><td>32.825</td></tr><tr><td>ABS</td><td>7</td><td>4.424</td><td>0.781</td><td>6.661</td><td>0.431</td><td>32.471</td></tr><tr><td>MSC</td><td>7</td><td>3.796</td><td>0.794</td><td>4.775</td><td>0.792</td><td>29.579</td></tr><tr><td>R</td><td>13</td><td>4.204</td><td>0.822</td><td>6.605</td><td>0.436</td><td>44.398</td></tr><tr><td>FD</td><td>13</td><td>3.662</td><td>0.855</td><td>5.084</td><td>0.824</td><td>42.124</td></tr><tr><td>SD</td><td>13</td><td>3.356</td><td>0.864</td><td>4.931</td><td>0.847</td><td>40.989</td></tr><tr><td>CR</td><td>13</td><td>4.197</td><td>0.784</td><td>5.780</td><td>0.697</td><td>43.239</td></tr><tr><td>ABS</td><td>13</td><td>4.202</td><td>0.82</td><td>6.493</td><td>0.461</td><td>44.248</td></tr><tr><td rowspan="7">Sentinel 3</td><td>MSC</td><td>13</td><td>3.556</td><td>0.876</td><td>4.461</td><td>0.810</td><td>41.858</td></tr><tr><td>R</td><td>21</td><td>4.777</td><td>0.703</td><td>6.900</td><td>0.359</td><td>60. 777</td></tr><tr><td>FD</td><td>21</td><td>3.501</td><td>0.822</td><td>4.650</td><td>0.823</td><td>57.349</td></tr><tr><td>SD</td><td>21</td><td>2.263</td><td>0.946</td><td>3.515</td><td>0.903</td><td>54.918</td></tr><tr><td>CR</td><td>21</td><td>3.405</td><td>0.866</td><td>5.239</td><td>0.686</td><td>58.385</td></tr><tr><td>ABS</td><td>21</td><td>4.891</td><td>0.693</td><td>6.779</td><td>0.399</td><td>60.623</td></tr><tr><td>MSC</td><td>21</td><td>3.516</td><td>0.837</td><td>4.258</td><td>0.832</td><td>56.584</td></tr></table></body></html>

注： $R ^ { 2 }$ 为决定系数，RMSE为均方根误差， $A I C$ 为赤池信息准则。下同

TDSI能够提供与土壤EC更敏感的相关信息，本研究为减少建模过程中敏感度较低波段对建模精度的影响，将各光谱形式下通过显著性检验的三维光谱指数作为光谱参量加入建模当中，分析模型效果，精度评价如表4所示。

在加入TDSI后构建的3种卫星不同光谱形式的土壤 $E C$ 估算模型， $R ^ { 2 }$ 较之前均有所提高，且均达到0.6以上。综合分析发现,3种卫星基于R的土壤 $E C$ 估算模型精度提升幅度最为明显，其中Senti-nel2卫星精度提升 $8 2 . 3 4 \%$ ,提升幅度最大,其次为Sentinel3卫星，提升 $7 6 . 8 8 \%$ ，最后为Landsat8OLI卫星，提升 $7 2 . 8 1 \%$ ;基于ABS预处理的模型提升幅度也较大，分别提升 $6 6 . 5 9 \% . 7 4 . 4 4 \% . 6 8 . 2 1 \%$ 。Landsat8OLI卫星基于FD预处理的土壤 $E C$ 估算精度最佳 $( R ^ { 2 } = 0 . \ 8 3 5 , R M S E = 4 . \ 3 4 8 \ \mathrm { m S } \cdot \ \mathrm { c m } ^ { \ - 1 }$ ，$A I C = 3 2 . 7 6 5$ )，基于ABS预处理的土壤EC估算精度最低( $R ^ { 2 } ~ = 0 . ~ 7 2 5 , R M S E = 5 . ~ 6 0 1 ~ \mathrm { m S } ~ \cdot ~ \mathrm { c m } ^ { - 1 }$ ，$A I C = 3 4 . 9 6 5$ )，各光谱形式的估算精度依次为 $\mathrm { F D } >$ $\mathrm { M S C } > \mathrm { S D } > \mathrm { R } > \mathrm { A B S } _ { \circ }$ 。Sentinel2卫星基于SD预处理的土壤EC估算精度最佳( $R ^ { 2 } = 0 . 8 5 7$ ， $R M S E =$ $4 . 5 9 6 ~ \mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ ， $A I C = 4 5 . 2 4 7$ ),基于CR 的土壤 $E C$ 估算精度最低 $( R ^ { 2 } = 0 . 7 0 5 , R M S E = 5 . 7 9 9 \mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ ，

![](images/1dc6f7dbf35b97a57e5bf37e4078d4aa348345a52ce3cad667132547a44c158e.jpg)  
图43种卫星各波段重要性  
Fig.4Importance of each band of the three satellites

# 表4加入三维光谱指数土壤EC估算结果

Tab.4Results of soil EC estimation for adding three-dimensional spectral index   

<html><body><table><tr><td rowspan="2">卫星</td><td rowspan="2">光谱形式</td><td rowspan="2">参量</td><td colspan="2">建模集</td><td colspan="3">验证集</td></tr><tr><td>RMSE／mS·cm-1</td><td>R²</td><td>RMSE/mS·cm-1</td><td>R</td><td>AIC</td></tr><tr><td>Landsat 8 OLI</td><td>R</td><td>9</td><td>4.160</td><td>0.757</td><td>5.680</td><td>0.750</td><td>35.086</td></tr><tr><td rowspan="9">Sentinel 2</td><td>FD</td><td>9</td><td>3.786</td><td>0.813</td><td>4.348</td><td>0.835</td><td>32.765</td></tr><tr><td>SD</td><td>9</td><td>3.517</td><td>0.834</td><td>5.276</td><td>0.777</td><td>34.447</td></tr><tr><td>ABS</td><td>9</td><td>4.075</td><td>0.778</td><td>5.601</td><td>0.725</td><td>34.965</td></tr><tr><td>MSC</td><td>9</td><td>3.645</td><td>0.809</td><td>5.459</td><td>0.804</td><td>34.743</td></tr><tr><td>R</td><td>15</td><td>3.908</td><td>0.803</td><td>5.873</td><td>0.795</td><td>47.377</td></tr><tr><td>FD</td><td>15</td><td>3.192</td><td>0.875</td><td>4.817</td><td>0.843</td><td>45.656</td></tr><tr><td>SD</td><td>15</td><td>3.158</td><td>0.865</td><td>4.596</td><td>0.857</td><td>45.247</td></tr><tr><td>CR</td><td>14</td><td>4.186</td><td>0.803</td><td>5.799</td><td>0.705</td><td>45.267</td></tr><tr><td>ABS</td><td>15</td><td>3.912</td><td>0.803</td><td>5.383</td><td>0.768</td><td>46.937</td></tr><tr><td rowspan="7">Sentinel 3</td><td>MSC</td><td>15</td><td>3.308</td><td>0.888</td><td>4.392</td><td>0.834</td><td>45.853</td></tr><tr><td>R</td><td>23</td><td>4.306</td><td>0.823</td><td>5.986</td><td>0.635</td><td>63.543</td></tr><tr><td>FD</td><td>23</td><td>3.381</td><td>0.844</td><td>4.636</td><td>0.833</td><td>61.324</td></tr><tr><td>SD</td><td>23</td><td>2.136</td><td>0.956</td><td>2.986</td><td>0.935</td><td>57.500</td></tr><tr><td>CR</td><td>23</td><td>3.271</td><td>0.889</td><td>5.142</td><td>0.725</td><td>62.223</td></tr><tr><td>ABS</td><td>23</td><td>4.269</td><td>0.801</td><td>5.680</td><td>0.696</td><td>63.087</td></tr><tr><td>MSC</td><td>23</td><td>3.494</td><td>0.859</td><td>4. 177</td><td>0.840</td><td>60.417</td></tr></table></body></html>

$A I C = 4 5 . 2 6 7$ ），各光谱形式的估算精度依次为 $\mathrm { S D } >$ $\mathrm { F D } > \mathrm { M S C } > \mathrm { R } > \mathrm { A B S } > \mathrm { C R }$ 。Sentinel3卫星基于SD预处理的土壤 $\boldsymbol { \mathrm { \Sigma } } _ { E C }$ 估算精度最佳（ $R ^ { 2 } = 0 . 9 3 5$ ，$R M S E = 2 . 9 8 6 ~ \mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ ， $A I C = 5 7 . 5 0 0 { \mathrm { \Omega } }$ ),基于R的土壤 $E C$ 估算精度最低（ $R ^ { 2 } = 0 . 6 3 5$ ， $R M S E = 5 . 9 8 6$ $\mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ $A I C = 6 3 . { \ } 5 4 3 { \mathrm { ~ } }$ ),各光谱形式的估算精度依次为 $\mathrm { S D } > \mathrm { M S C } > \mathrm { F D } > \mathrm { C R } > \mathrm { A B S } > \mathrm { R }$ 。综合比较发现,Sentinel3卫星依旧为土壤 $E C$ 估算最佳卫星，其次为Sentinel2，最后为Landsat $8 ~ \mathrm { O L I }$ 。图5为3种卫星基于GBRT的土壤 $\ E C$ 最佳估算结果图。

# 3讨论

综合表3、表4分析后认为，微分预处理方式对于提高3种卫星土壤 $E C$ 估算精度具有极好的效果,Sentinel3卫星为土壤 $E C$ 估算的最佳选择,由于其27d的重访周期以及 $3 0 0 \mathrm { ~ m ~ }$ 的空间分辨率[24],较适用于大尺度乃至全球范围内土壤盐渍化监测与数字化制图;Sentinel2卫星具有空间分辨率高（最高为 $1 0 \mathrm { ~ m ~ }$ )、重访周期短 $( 5 \mathrm { ~ d ~ } )$ ）的优势[25],对于土壤盐渍化精细分类以及快速动态监测具有一定潜力；

30 Landsat8 OLI 30 Sentinel 2 30 Sentinel 3 建模集 建模集 △建模集 25 ·验证集 25 ·验证集 25 ·验证集 △ ： △ .- + D 15 . 15 4 公 2 15 4 . △ & 土 10 A △ 44 R2=0.835 土 10 △△ 1 R2=0.857 土 10 R2=0.935 5 RMSE=4.348 mS·cm-1 5 RMSE=4.596 mS·cm-1 5 RMSE=2.986 mS·cm-1 AIC=32.765 AIC=45.247 AIC=57.500 0 0 0 5 10 15 20 25 30 0 5 10 15 20 25 30 0 5 10 15 20 25 30 土壤EC实测值 土壤EC实测值 土壤EC实测值

Landsat8OLI卫星虽然相对前两者土壤 $E C$ 估算精度较低，但最佳 $R ^ { 2 }$ 也达0.835，加之其数据连续性较强，可以为区域土壤盐渍化动态变化及预测提供可靠支撑。

利用地面实测VIS-NIR数据通过不同卫星的波谱响应函数模拟各自宽波段数据，从而构建土壤EC估算模型，从理论上为土壤EC的估算与土壤盐渍化的监测提供了科学指导。但是卫星实际观测过程中还会受到大气以及地物单元复杂等因素的干扰，造成卫星实际宽波段数据与模拟数据存在差异，因此模型的普适性还需大量数据及实验进行验证，同时今后需增加卫星传感器类型，并对土壤其他属性进行对比研究，以期探寻最佳的土壤属性估算模型及确定最适卫星观测平台。

# 4结论

本研究通过模拟3种卫星宽波段数据，采用5种预处理方式，结合GBRT算法构建艾比湖土壤EC估算模型，并构建TDSI充分挖掘波段间的相互关系，最大程度上保留土壤EC的敏感信息，有效提升了建模精度。研究发现，在不同土壤EC条件下，3种卫星宽波段模拟数据具有相似的光谱趋势，均在红、近红外附近有较高反射率。构建的TDSI与土壤EC 相关性基本均在0.4以上，保留了与土壤 $E C$ 高度敏感的红、绿、蓝、近红外、短波红外波段信息。GBRT算法对于土壤EC估算表现出较高的预测能力，Landsat8OLI、Sentinel2、Sentinel3最佳估算 $R ^ { 2 }$ 分别为 $0 . 8 3 1 , 0 . 8 4 7 , 0 . 9 0 3$ ,在加入TDSI后，精度得到显著提升,3种卫星最佳估算 $R ^ { 2 }$ 也分别提高到0.835、0.8570.935，各卫星预测效果依次为Senti-nel $3 >$ Sentinel $2 >$ Landsat8OLI。本研究为土壤盐渍化监测提供一种新的思路及方法，为针对不同尺度盐渍化灾害预测防控提供科学参考。

# 参考文献(References)

[1]SINGH A.Soil salinization and waterlogging:A threat to environmentand agricultural sustainability［J].Ecological Indicators, 2015,57:128 -130.   
[2]MACHADO R,SERRALHEIRO R.Soil salinity:Effect on vegetable crop growth management practices to prevent and mitigate soil salinization[J].Horticulturae,2017,3(2）:30.   
[3］梁静,丁建丽,王敬哲,等.基于反射光谱与Landsat8OLI多光 谱数据的艾比湖湿地土壤盐分估算[J].土壤学报,2019,56 (2）:320-330.[LIANG Jing,DING Jianli,WANG Jingzhe,et al. Quantitative estimation and mapping of soil salinity in the Ebinur Lake Wetland based on Vis-NIR reflectance and Landsat 8 OLI data[J].Acta Pedologica Sinica,2019,56(2）:320-330.]   
[4]CHEN Y,ZHAO X,JIA X. Spectral-spatial classification of hyperspectral data based on deep belief network［J].IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing,2015,8(6) :2381-2392.   
[5]ROSSEL RAV,BEHRENS T,BEN-DOR E,et al.A global spectral library to characterize the world's soil[J].Earth-Science Reviews,2016,155:198-230.   
[6]王敬哲,丁建丽,马轩凯,等.基于光谱指数的绿洲农田土壤含 水率无人机高光谱检测[J].农业机械学报,2018,49（11)：1- 14.［WANG Jingzhe,DING Jianli,MA Xuankai,et al.Detection of soil moisture content based on UAV-derived hyperspectral imagery and spectral index in oasis cropland[J].Transactions of the Chinese Society for Agricultural Machinery,2018,49(11）:1-14.]   
[7］史舟,梁宗正,杨媛媛,等.农业遥感研究现状与展望[J].农业 机械学报,2015,46（2）:247-260.[SHI Zhou,LIANG Zongzheng,YANG Yuanyuan,et al. Status and prospect of agricultural remote sensing[J].Transactions of the Chinese Society for Agricultural Machinery,2015,46(2）:247 -260.]   
[8］黄权中,徐旭,吕玲娇,等.基于遥感反演河套灌区土壤盐分分 布及对作物生长的影响[J].农业工程学报,2018,34（1）： 102-109.[HUANG Quanzhong,XU Xu,LYU Lingjiao,et al. Soil salinity distribution based on remote sensing and its efect on crop growth in Hetao Irrigation District[J].Transactions of the Chinese Society of Agricultural Engineering,2018,34(1）:102-109.]   
[9]厉彦玲,赵庚星,常春艳,等.OLI与 HSI影像融合的土壤盐分 反演模型[J].农业工程学报,2017,33（21)：173-180.［LI Yanling,ZHAO Gengxing,CHANG Chunyan,et al. Soil salinity retrieval model based on OLI and HSI image fusion[J]. Transactions of the Chinese Society of Agricultural Engineering,2O17,33（21）: 173 -180.]   
[10]NAWAR S,BUDDENBAUMH,HILL J. Estimation of soil salinity using three quantitative methods based on visible and near-infrared reflectance spectroscopy: A case study from Egypt[J].Arabian Journal of Geosciences,2015,8（7）:5127 -5140.   
[11]WANG X,ZHANG F,DING J,et al. Estimation of soil salt content (SSC）in the Ebinur Lake Wetland National Nature Reserve（ELWNNR）,northwest China,based on a Bootstrap-BP neural network model and optimal spectral indices[J].Science of the Total Environment,2018,615:918 -930.   
[12］王涛,喻彩丽,姚娜,等.MLR 和 PLSR 的沙壤土盐分含量光谱 检测对比研究[J].干旱区地理,2018,41（6）：1295－1302. [WANG Tao,YU Caili,YAO Na,et al.A comparison of the salt content in sandy soil between the MLR model and PLSR model [J].Arid Land Geography,2018,41(6）:1295-1302.]   
[13］姚远,丁建丽,张芳,等.基于高光谱指数和电磁感应技术的区 域土壤盐渍化监测模型[J].光谱学与光谱分析,2013,33（6)： 1658-1664.[YAO Yuan,DING Jianli,ZHANG Fang,et al. Research on model of soil salinization monitoring based on hyperspectral index and EM38[J].Spectroscopy and Spectral Analysis, 2013,33(6):1658 -1664.]   
[14］张桉赫,丁建丽,董煜,等.新疆艾比湖绿洲干燥指数变化特征 [J].干旱区研究,2019,36（1）:244-252.[ZHANG Anhe, DING Jianli,DONG Yu,etal.Change of aridity index in the Ebinur Lake Oasis,Xinjiang[J].Arid Zone Research,2019,36（1）： 244 -252.]   
[15］王敬哲,丁建丽,王飞,等.艾比湖湿地不同盐渍化土壤粒度组

成及可蚀性研究［J].土壤，2018，50（3）：598-605.［WANG

Jingzhe,DING Jianli,WANG Fei,et al.Particle size distribution （PSD）and erodibility of soils under different salinization degrees in Ebinur Lake Wetland[J].Soils,2018,50(3）:598-605.]   
[16]WANG J,DING J,ABULIMITI A,et al. Quantitative estimation of soil salinity by means of different modeling methods and visiblenear infrared（VIS-NIR）spectroscopy,Ebinur Lake Wetland, northwest China[J].PeerJ,2018,6:e4703.   
[17]EL HARTI A,LHISSOU R,CHOKMANI K,et al. Spatiotemporal monitoring of soil salinization in irigated Tadla Plain（Morocco） using satelite spectral indices[J]. International Journal of Applied Earth Observation and Geoinformation,2016,50:64-73.   
[18］李哲,张飞,冯海宽,等.基于波段组合的植被叶片盐离子估算 研究［J].光学学报,2017,37（11）:325-339.［LIZhe,ZHANG Fei,FENG Haikuan,et al.Research on the estimation of salt ions of vegetation leaves based on band combination[J].Acta Optica Sinica,2017,37(11) :325-339.]   
[19]GALVAO RKH,ARAUJO MC U,JOSEG E,et al.A method for calibration and validation subset partitioning[J].Talanta,2005,67 (4) :736 -740.   
[20]MCGOVERN A,ELMORE KL,GAGNE D J,et al. Using artificial intelligence to improve real-time decision-making for high-impact weather［J].Bulletin of the American Meteorological Society, 2017,98(10) :2073 -2090.   
[21]DZIAK JJ,COFFMAN D L,LANZA S T,et al. Sensitivity and specificity of informationcriteria[J].Briefings in Bioinformatics, 2019,20(1) :1 -13.   
[22]PENG J,BISWAS A,JIANG Q,et al. Estimating soil salinity from remote sensing and terrain data in southern Xinjiang Province ,China[J].Geoderma,2019,337:1309 -1319.   
[23]NAWAR S,BUDDENBAUM H,HILL J,et al. Modeling and mapping of soil salinity with reflectance spectroscopy and landsat data using two quantitative methods[J]. Remote Sensing,2O14,6(11）： 10813 -10834.   
[24]DONLON C,BERRUTIB,BUONGIORNO A,et al. The global monitoring for environment and security（GMES） sentinel-3 mission [J].Remote Sensing of Environment,2012,120:37 -57.   
[25]DRUSCH M,DEL BELLO U,CARLIER S,et al. Sentinel-2:ESA's optical high-resolution mission for GMES operational services[J]. Remote Sensing of Environment,2012,120:25-36.

# Estimation of soil conductivity based on spectral simulation of different satellites

CAO Xiao-yi1,2，DING Jian-li1,2.3，GE Xiang-yu12， LIANG Jing1,2, CHEN Wen-qian12,3，CHENXiang-yue12²2，TANG Puen² (1College of Resources and Environmental Science,Xinjiang University,Urumqi 83oo46,Xinjiang,China; 2KeyLaboratoryofOasis Ecologyunder Ministryof Education，Xinjiang University，Urumqi 830046,Xinjiang,China; 3Key Laboratoryof Smart Cityand Environment Modelling of Higher Education Institute,Xinjiang University, Urumqi 800046,Xinjiang,China)

Abstract：Asone of the importantenvironmental problems in the global arid region,soilsalinization notonlyrestricts agricultural production,but alsocausesserious land degradation.This problem hasatracted wideattention from many scholarsat homeand abroad.In the recent stage,the monitoring and evaluationof soil salinization is mainly based on the useof diferent remote sensing data combined with diferent model inversion methods,and few research was seen on the integration of ground measured spectra and satelite remotely sensed data to obtain soil salinization information.Therefore,this studyexplores thefectof differentsatelitebroadband simulationsonsoil conductivityand reflects soil salinization.Inthis study,the Ebinur Lake Wetland Nature Reserve in Xinjiang Uygur Autonomous Region,China was taken asan example.4O soil samples werecollected in the field,and the soil conductivity $( E C )$ and visible-near-infrared（VIS-NIR） spectral data were measured.The broadband data of the Landsat 8 OLI,Sentinel2,and Sentinel3 satelites were simulated by spectral response techniques.The three-dimensional spectral index was constructed by simulating wide-band data and its six spectral forms after five pretreatments : first-order diffrential（FD）,second-order diferential（SD）,continuum removal（CR）,absorbance conversion （ABS）,and multivariate scattering correction（MSC）.Three satellite soil $E C$ estimation models were established by combining the gradientboosting regresion tree（GBRT）algorithm,and the accuracy of the model estimation was compared afteradding the three-dimensional spectral index.Then thesoil estimation potential of the three satelites was analyzed.Theresults show that:Landsat 8OLI,Sentinel 2,and Sentinel 3 have similar spectral trends under differentsoilECconditions.Withthe increaseofsoilEC,thereflectanceofeachbandofthethree satelites iscorespondingly increased,andboth have high reflectance inredand near infrared.The correlation between TDSI and soil $E C$ was basically above O.4,and Sentinel 3 had the highest correlation based on SD pretreatment,which was -0.720.TDSI retains the information of red,green,blue,near-infraredand short-wave infrared bands sensitive to soil $E C$ ,which indicates that TDSI increases the effective information of soil $E C$ while taking into account the remote sensing mechanism,which has certain scientific significance.GBRT algorithm has outstanding performance for soil $E C$ estimation.Landsat 8OLI,Sentinel2,Sentinel 3 based on the estimation model of broadband simulation data produced the best prediction accuracy $R ^ { 2 }$ as 0.831,0.847 and 0.903 respectively. After adding the TDSI,the estimationaccuracyof different spectrum forms of the threesatelites has been significantly improved.The corresponding prediction accuracy $R ^ { 2 }$ of the three satellites was increased to 0.83 5,0.857 and 0.935,respectively. The comprehensive analysis found that Sentinel 3 had the best estimation effect for soil $E C$ （ $R ^ { 2 } = 0$ .935, $R M S E = 2$ .986 $\mathrm { m S } \cdot \mathrm { c m } ^ { - 1 }$ ， $A I C = 5 7 . 5 0 0$ ）,followedby Sentinel 2 $\mathit { ^ { \prime } R ^ { 2 } = 0 . 8 5 7 , R M S E = 4 . 5 9 6 ~ m S \cdot { \mathrm { c m } } ^ { - 1 } }$ ， $A I C = 4 5 . 2 4 7$ ),and finally Landsat 8 OLI ( $\mathit { R } ^ { 2 } = 0 . 8 3 5 , \mathit { R M S E } = 4 . 3 4 8 \ : \mathrm { \ m S } \cdot \mathrm { c m } ^ { - 1 }$ $A I C = 3 2 . 7 6 5$ ). In this study,the spectral response techniquecombined with GBRTalgorithm hasbeen verifiedthat Landsat 8OLI,Sentinel2and Sentinel3satelites have a good estimation effect on soil $E C$ in arid area. TDSI can deeply mine the synergy information between bands and improve the prediction accuracy of the model.The combination of the two methods could provide favorable guidance for quantitative monitoring and prevention of soil salinization in arid areas.

Key words:spectral response；soil conductivity；spectral pretreatment；three-dimensional spectral index；gradient boosting regression tree