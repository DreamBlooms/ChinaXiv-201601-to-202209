# 基于随机森林算法的土壤有机质含量高光谱检测

包青岭1,²，丁建丽1,²，王敬哲¹,²，蔡亮红1,2（1新疆大学资源与环境科学学院智慧城市与环境建模自治区普通高校重点实验室,新疆乌鲁木齐830046；2绿洲生态教育部重点实验室，新疆乌鲁木齐830046)

摘要：为了探讨既能保留光谱信息又能准确对土壤有机质含量进行快速检测。以新疆南部渭干河—库车绿洲内部73个土壤样点及其对应的高光谱数据为研究对象，采用小波变换与数学变换进行光谱数据预处理,分析各小波分解重构光谱在不同有机质含量与不同土壤类型下光谱曲线差异，通过相关分析确定最大小波分解层并筛选敏感波段，结合灰色关联分析与随机森林预测分类模型对各小波分解特征光谱进行重要性分析，最后基于最优特征光谱建立多元线性预测模型并进行分析。结果表明：(1）耕作土壤与林地土壤光谱曲线波段相较盐渍土壤和荒漠土壤光谱曲线变化较为平缓，同时在水分吸收波段处，盐渍土壤光谱曲线吸收谷最深。（2）小波变换分解光谱与土壤有机质含量的相关性随着分解层数增加呈现先减后增趋势,在第6层中,特征光谱曲线与敏感波段数量变化趋于稳定，确定为小波变换最大分解层。（3）随机森林模型相比灰色关联分析对于各小波分解层因子的筛选符合预期，按照对土壤有机质含量影响从高到低排序为 $L 3 \mathrm { - } ( \mathrm { ~ } 1 / \mathrm { L g } R \mathrm { ~ } ) ^ { \prime } .$ L4-(1/LgR)'L6-（1/LgR)'L5-(1/LgR)'、L2-（1/LgR)'L0-1/LgR、L1-1/LgR。（4）在小波分解光谱中，中频范围特征光谱对干旱区土壤有机质含量的估测能力优于高频与低频范围特征光谱，同时基于L-MC建立的模型精度最高。研究表明：基于机器学习分类方法结合小波分解的土壤光谱有机质含量监测，可以有效的减少噪声波段干扰，并提高特征波段的分类预测精度。

关键 词：高光谱；土壤有机质含量；小波变换；随机森林

土壤有机质(Soilorganicmatter,SOM)是地球表面土壤中重要组成物质，作为反映土壤肥力以及土地生产能力的重要因子。国内外不同学者利用高光谱技术对不同土壤类型估测SOM含量，发现SOM在土壤光谱曲线不存在明显吸收峰，对于可见光至近红外范围存在明显光谱敏感区[1-2]。众多学者利用高光谱数据对SOM含量进行定量估算，均取得了不错效果[3-9]。由于土壤中存在与 SOM 含量不相关的噪声波段，所以有效减少噪声影响并保留光谱有效信息是 SOM光谱定量估算的难点[10]

现今比较成熟的光谱平滑去噪技术包括Savitz-ky-Golay滤波、中值滤波、移动平均法等。MORGAN等[1]使用移动加权算法进行土壤有机碳含量的估测,RIENZI等[12]和NOCITA等[13]选用不同采样窗□Sdavitzky-Gplayl滤波进行土壤有机碳检测中光谱数据平滑去噪。上述研究虽然能对光谱反射率数据起到去噪和压缩的效果，但是对于白噪声，尤其是随机和低频信号，难以做到去除噪声又不影响有用信号。小波变换方法作为一种新的光谱平滑去噪技术，已经成功应用在高光谱数据处理中。LIAO等[14]采用4种常用光谱变换方式对 SOM含量进行分析建模，结果表明小波变换对于减少噪声波段方面有很好效果。YANG 等[15]对反射光谱采用小波分析捕捉土壤有机碳和总氮的吸收特征，结果表明连续小波变换对于定位有机碳与总氮光谱特征和区分土壤其它成分是一种高效的方法。LIN 等[16]基于 $4 0 0 \sim 1 ~ 0 0 6 ~ \mathrm { n m }$ 光谱范围内主要吸收谷，通过小波变换放大被噪声掩盖的有用信息，构造偏最小二乘模型，结果表明小波变换具有很好光谱降噪效果。张锐等[17]研究发现,中频范围小波分解层对SOM含量的预测较为精确，陈红艳等[18]与王延仓等[19]研究发现高频范围小波分解特征光谱对于SOM含量的预测较为适合。以上研究表明，相比较传统的光谱去噪方法，小波变换能实现光谱信号的去噪与特征光谱选择[20]

前人的研究多集中在小波分解特征光谱与SOM进行定量估算，但是较少考虑通过数据挖掘模型进行小波分解重构光谱结合数学变换的优选并进行SOM含量的预测，因此本文选择渭干河一库车河三角洲（简称渭一库绿洲)为研究区，选取表层SOM含量与相对应的土壤光谱进行定量分析并进行建模反演。分析不同SOM含量下与不同土地利用方式下土壤光谱反射率在各波段与各分解层的差异，根据各层特征光谱曲线与SOM含量之间相关性确定最佳分解层，并对原始土壤光谱数据和重构光谱分别进行9种数学变换，利用随机森林数据挖掘模型与灰色关联分析方法，对小波分解特征光谱因子进行重要性分类，最后进行干旱区SOM含量的多元线性建模预测，为干旱区土壤养分的研究与当地精准农业提供科学参考与支持。

# 1研究区概况与研究方法

# 1.1 研究区概况

以新疆维吾尔自治区的渭一库绿洲内部区域$( 4 1 ^ { \circ } 0 6 ^ { \prime } \sim 4 1 ^ { \circ } 3 8 ^ { \prime } \mathrm { N } , 8 1 ^ { \circ } 2 6 ^ { \prime } \sim 8 3 ^ { \circ } 1 7 ^ { \prime } \mathrm { E } )$ 为实验区，其中包括库车、沙雅、新和3个县。渭一库绿洲位于新疆塔里木盆地中北部，是新疆具有代表性的干旱区绿洲。年内平均气温范围在 $0 . 5 \sim 1 4 . 4 \mathrm { ~ \textdegree C }$ ,年内平均降水在 $6 7 . 5 \ \mathrm { m m }$ 左右。属于典型的极端干旱区域。土壤类型主要以潮土、灌淤土和棕漠土等为主，同时也有水稻土、盐土、草甸土、沼泽土等[21]。依据野外实地采样单元确定研究区范围，如图1所示（由Landsat-OLL8影像红绿蓝波段合成）。

# 1.2 研究方法

1.2.1土样采集与光谱处理在2017年7月中旬，采集了分布于绿洲区域内部的73个土壤样品（图1），覆盖了绿洲内部区域的不同土地利用方式，包括农田、荒地、盐渍地和林地。按照5点梅花状采集表层( $0 \sim 1 0 ~ \mathrm { c m } )$ 土样且将5个土样进行混合，将土样带回实验室，进行自然风干、研磨并将土样中的杂质进行剔除后过筛。SOM含量的测定采用重铬酸钾容量一外加热法(油浴)测定。土壤反射率数据的测定采用ASDFieldspec3便携式光谱仪在暗室内进行，将过 $0 . 2 5 \ \mathrm { m m }$ 筛的土壤样品装载进深$1 . 8 ~ \mathrm { c m }$ 、直径 $1 2 \ \mathrm { c m }$ 盛样皿内，波谱范围在( $3 5 0 \sim$ $2 5 0 0 \ \mathrm { n m }$ ），室内光源为 $5 0 \mathrm { ~ W ~ }$ 的卤素灯，采用 $5 ^ { \circ }$ 视场角光纤探头。光谱测定前均进行白板校正，每个土样测量10次，算术平均以后得到土样的实际反射光谱曲线，去除边缘波段( $3 5 0 \sim 3 9 9 ~ \mathrm { n m }$ 和 $( 2 ~ 4 0 1 \sim$ $2 5 0 0 \ \mathrm { n m }$ )。为了消除光谱数据受实验环境、光谱高频随机噪声、杂散光等干扰影响，采用Savitaky-Golay(2次多项式,5个点)平滑去噪[22-23] 。

![](images/483d525d77090ce5b45acec367be93b992cb2ae441dfe0528d486f75c09d5da7.jpg)  
图1 研究区示意图  
Fig.1Map of the study area

1.2.2小波分解小波分析是一种基于傅里叶变换法发展起来的数据分析方法，小波多尺度分解是通过构造小波基函数对分析函数进行多尺度分解，常见的小波变换有连续小波变换（Continuouswave-lettransform，CWT)和离散小波变换（Discretewave-lettransform，DWT）。小波分解将原始光谱信号分解为不同子频带的时频分量，从而更好地观察原始信号的特定频率特征，小波分解的每一层子频带可表示为原始光谱某一频率的吸收特征，相对应的高频光谱信号则被小波滤波器去除[24-25]。根据王延仓等研究结论，因此本研究选取db5小波母函数对原始光谱进行8层小波变换，并构建各层特征光谱，以 $L 1 \sim L 8$ 表征，最后再选取与SOM含量相关性较好的 $L 1 \sim L 6$ 层特征光谱进行进一步的分析。

1.2.3随机森林模型随机森林模型（RandomForestModel，RFM)属于机器学习的一大分支一集成学习（EnsembleLearning）方法。RFM算法是基于决策树分类集成算法，其中每一棵树都依赖于一个随机向量，通过对数据集的列变量和行变量观测进行随机化，生成多个分类数，最终将分类树结果进行汇总。RFM对于非线性问题有很好的解释能力，相比于神经网络，降低了运算量的同时也提高了预测精度。本文在R语言中，利用RandomForest工具包进行预测分类，在进行拟合前，分别对需要生成树的数量( $B = \mathrm { n t r e e }$ )参数设定为600，每个节点处用于分割节点的预测变量树( $\begin{array} { r } { d = \operatorname* { m t r y } . } \end{array}$ )参数设定为3。模型的重要性分类指标由平均下降精度参数（MeanDecreaseAccuracy)提供，模型的预测性能可以通过预测相关系数 $( R ^ { 2 } )$ 、均方根误差(RMSE)2个指标来衡量RFM预测性能。RFM的 $R ^ { 2 }$ 越大,RMSE越小，其RFM估算准确性越高，反之则准确性越差[26]。

1.2.4数据预处理在确定最大小波分解尺度的基础上，将经过小波分解的各层光谱特征数据进行9种常规数学变换，这9种数学变换包括对数$( \mathrm { L g } R )$ 、倒数 $( 1 / R )$ 、倒数的对数( $\mathrm { [ g 1 / } R )$ 、对数的倒数 $\mathrm { \Omega } _ { \mathrm { ( 1 / L g } R ) }$ 、一阶微分 $( R ^ { \prime } )$ 、倒数的对数的一阶微分$[ \left( \mathrm { L g } 1 / R \right) ^ { \prime } ]$ 、对数的倒数的一阶微分 $\big ( 1 / \mathrm { L g } R \big ) ^ { \prime } \big ]$ 、对数的一阶微分 $\left[ { \bf \Phi } ( \mathrm { L g } R ) ^ { \prime } \right]$ 、倒数的一阶微分[（1>$R ) ^ { \prime } ]$ 。这些数学变换在Excel和Oringin9.2中进行,小波分解在 MatlabR2012a 进行操作[27] O

1.2.5数据分析与建模验证选取原始光谱与重构光谱与SOM相关性最大的波段为多元逐步回归模型的自变量，SOM含量为模型的因变量。并且参照SOM含量与重构光谱随机森林分类结果对应的特征波段作为多元逐步回归建模自变量L-MC，SOM含量作为模型因变量。模型精度评价参数有：校正决定系数（Determinationof cofficients， $R _ { c } ^ { 2 }$ ）、验证决定系数（Determination coefficients of validation, $R _ { p } ^ { 2 }$ ）残留预测偏差（Residual prediction deviation, $R P D )$ ，其中当 $R P D \geqslant 2$ 时，模型达到精准;当 $1 . 4 \leqslant R P D \leqslant 2$ 时,模型精度可靠；当 $R P D < 1 . ~ 4$ 时，模型并不可靠[28]。

# 2结果

# 2.1 研究区土壤有机质含量描述

SOM含量的基本描述情况如表1所示。可知研究区所有土样集的 SOM含量平均值为 $3 2 . 9 3 \mathrm { ~ g ~ }$ ：$\mathbf { k g } ^ { - 1 }$ ,校正集与验证集对应的有机质含量分别为$3 0 . 6 3 \mathrm { ~ g ~ } \cdot \mathrm { ~ k g ~ } ^ { - 1 }$ 和 $4 1 . 2 1 \mathrm { ~ g ~ } \cdot \mathrm { ~ k g ~ } ^ { - 1 }$ 。全样本集、校正集和验证集的变异系数（Coefficientofvariation， $C V )$ 分别为 $4 0 . 5 7 \% , 3 9 . 3 5 \%$ 和 $2 9 . 5 3 \%$ ,属于中等变异。由表2可知，不同土地利用类型中，林地 $s o M$ 含量均值最大,为 $4 7 . 8 0 \ \mathrm { g \cdot k g ^ { - 1 } }$ ,依次为农田、盐渍地与荒地。标准差最大值与最小值分别为林地$1 4 . 0 5 ~ \mathrm { g \cdot k g ^ { - 1 } }$ 与荒地 $8 . 5 9 \mathrm { ~ g ~ } \cdot \mathrm { ~ k g ~ } ^ { - 1 }$ ,各地类变异系数属于中等变异。

# 2.2不同SOM含量小波变换分析

选取SOM含量差异较大的3种土样，分别为$4 1 . 3 2 \mathrm { ~ g ~ } \cdot \mathrm { k g } ^ { - 1 } \ 、 3 3 . 9 1 \mathrm { ~ g ~ } \cdot \mathrm { k g } ^ { - 1 }$ 和 $2 2 . 7 1 \ \mathrm { g } \cdot \mathrm { k g } ^ { - 1 }$ ，探究各土样小波分解特征光谱之间的差异。

同SOM含量下小波变换后重构光谱如图2所示，从不同含量SOM经小波分解后的室内光谱曲线图2可以看出，不同 $s o M$ 含量光谱曲线在 $L 1 \sim L 8$ 小波分解层中形态较为一致，整体上呈现上凸的抛物线形。根据以往研究[29],当 SOM含量大于 $2 \%$ 时，SOM含量则在描述土壤光谱反射率特性中起主要作用。在 $L 0 \sim L 8$ 小波分解重构光谱中，每一层光谱反射率都是随着 $s o M$ 含量增加而降低。在 $4 0 0 \sim$ $8 0 0 \ \mathrm { n m }$ 之间，每一层重构光谱都形成一个陡坡，反射率在此波段范围内增加较快，同时随着分解层数的增加，光谱曲线逐渐变得平滑，消除了大部分噪声，直到 $L 7$ 层,光谱曲线逐渐变成一条直线。在近红外区域，反射率变化较为平缓，同时形成以$1 \ 4 0 0 \ \mathrm { n m } \ . 1 \ 9 0 0 \ \mathrm { n m } \ . 2 \ 2 0 0 \ \mathrm { n m }$ 波段为主的水分吸收谷，随着分解层数的增加，水分吸收谷逐渐变得平坦,直到L8层 $3 3 . 9 1 \ \mathrm { g \cdot k g ^ { - 1 } }$ 和 $2 2 . 7 1 \ \mathrm { g } \cdot \mathrm { k g } ^ { - 1 }$ 有机

Tab.1Statistical characteristics of SOM of soil samples   

<html><body><table><tr><td>样品集</td><td>土样 数</td><td>均值 /g·kg-1</td><td>标准差 g·kg-1</td><td>最小值 g·kg-1</td><td>最大值 g·kg-1</td><td>变异系数 g·kg-1</td></tr><tr><td>全样本集</td><td>73</td><td>32.93</td><td>15.16</td><td>15.13</td><td>70.77</td><td>40.57</td></tr><tr><td>校正集</td><td>51</td><td>30.63</td><td>14.56</td><td>15.13</td><td>70.77</td><td>39.53</td></tr><tr><td>验证集</td><td>22</td><td>41.21</td><td>13.79</td><td>13.04</td><td>69.66</td><td>29.53</td></tr></table></body></html>

# 表2土壤表层不同土地利用方式下SOM含量

表1SOM含量描述性统计  
Tab.2SOM contents in top soil under different type of land use   

<html><body><table><tr><td>类型</td><td>土样 数</td><td>最小值 /g·kg-1</td><td>最大值 g·kg-1</td><td>均值 /g·kg-1</td><td>标准差 /g·kg-1</td><td>变异系 数/%</td></tr><tr><td>农田</td><td>31</td><td>18.55</td><td>70.77</td><td>35.01</td><td>13.40</td><td>38.29</td></tr><tr><td>林地</td><td>5</td><td>27.85</td><td>69.66</td><td>47.80</td><td>14.05</td><td>29.41</td></tr><tr><td>盐渍地</td><td>30</td><td>15.13</td><td>53.53</td><td>32.13</td><td>10.43</td><td>32.46</td></tr><tr><td>荒地</td><td>6</td><td>13.04</td><td>37.21</td><td>29.05</td><td>8.59</td><td>29.57</td></tr></table></body></html>

(a)LO (b)L1 (c)L2 0.7 0.7 0.7 0.6 0.6 0.6 0.5 0.3 33.91g·kg-1 0.3 33.91g·kg-1 0.3 33.91 g·kg-1 0.2 2.31g.g 0.2 22.71 0.2 22.78 0.1 009 30 000I 000 00[ 009I 008I 000 2 0.10 30 008 000I 1000 00 0.1 30 008 000I 0000 00 009 008 波长 波长 波长 (d)L3 (e)LA (f)L5 0.7 0.7 0.7 0.6 0.6 0.6 0.5 0.5 0.4 新04 0.4 0.3 32.91g kg 反0.3 32.91g: kg 反0.3 22.91g. g 0.2 41.32 g·kg-1 0.2 41.32g·kg-1 0.2 41.32 g·kg-1 0.10 009 008 000[ 2000 00 009 008I 000 000 2 100V 2 0.1 00 008 000I 0000 00 009[ 0.1 009 008 000I 2000 00[ 009I 008 波长 波长 波长 (g)L6 (h)L7 ()L8 0.7 0.7 0.7 0.6 0.6 0.6 A 1% 0.5 % 0.5 22 22 0 22 2 0. 反 2 0.10 00 008 000[ 1000 000 009I 008I 2 0.1 30 3 000[ 0000 00 009 008[ 000 3202 0.10 009 008 000I 0000 000I 009I 008 000 波长 波长 波长

质含量的光谱曲线已经看不到水分吸收谷，在850$\mathbf { n m }$ 波段范围内有明显吸收。

# 2.3不同土地利用方式下小波变换分析

图3为4种不同土地利用方式下经小波变换后的土壤光谱曲线,分别为耕作土壤、林地土壤、盐渍土壤和荒漠土壤，同时4种不同类型土壤的SOM含量均在 $2 2 . 6 3 \mathrm { ~ g ~ } \cdot \mathrm { ~ k g ~ } ^ { - 1 }$ 附近。通过 $L 0$ 原始光谱曲线发现,在 $4 0 0 \sim 8 0 0 ~ \mathrm { n m }$ 范围内，4种土壤类型光谱曲线随着波长增加，反射率急剧上升，形成4个反射峰,荒漠土壤反射率上升最快,曲线斜率最大,直到$9 0 0 \ \mathrm { n m }$ 左右超越其它类型土壤,之后保持反射率第一的位置，荒漠土壤与盐渍土壤的光谱曲线在 $5 0 0 \sim$ $9 0 0 \ \mathrm { n m }$ 之间存在一个明显的弓形突起区，该发现与高志海等[29研究相符。在以 $1 ~ 4 0 0 ~ \mathrm { n m } \ 、 1 ~ 9 0 0 ~ \mathrm { n m }$ 和$2 \ : 2 0 0 \mathrm { n m }$ 波段为主的水分吸收谷，盐渍土壤的水分吸收谷最深,依次为荒漠土壤、耕作土壤与林地土壤，同时随着小波分解的进行到L8层，只有盐渍土壤光谱曲线还有着明显水分吸收谷。在可见光范围内，这4种土壤类型光谱曲线出现交叉现象，这与李洪等[30]的研究较为一致。在 $1 \ 0 0 0 \sim 2 \ 4 0 0 \ \mathrm { n m }$ 波段范围内，林地土壤光谱曲线变化较为平衡，盐渍土壤光谱曲线波动最为剧烈，接下来为荒漠土壤与耕作土壤。经过小波变换后，在 $L 4$ 与 $L 5$ 层去噪效果达到最佳，光谱曲线基本无毛躁现象，同时又很好的保留了不同土壤类型光谱曲线的特征，但是在 $L 7$ 与L8 层中，已经消除了大部分光谱特征。

# 2.4SOM与重构光谱相关性分析

对每个土壤样本反射率进行小波变换,变换后得到各层分解特征光谱，并且在此基础上进行9种常规数学变换，最后得到土壤反射光谱的敏感波段。选取8层分解光谱反射率与SOM含量进行相关性分析，表3与表4中的相关系数均通过0.01置信水

0.60 (a)LO 0.60 (b)L1 0.60 (c)L20.55 0.55 0.55  
% 0% %  
0 4 060.40 一耕作土壤 --林地土壤 0.40 -耕作土壤--林地土壤 0.40 耕作土壤 --林地土壤0.35 盐渍土壤 -荒漠土壤 0.35 盐渍土壤 = 荒漠土壤 0.35 . 盐渍土壤 --荒漠土壤005 30 30 000 000 000 009 008 000 000 00 0 300 30 000 000 000 009 008 000 000 100 000 30 008 000 000 000I 009I 008A 1 1 I 2 2 2 1 1 1 I I 2 2 I波长/nm 波长/nm 波长/nm0.60 (d) L3 0.60 (e)LA 0.60 (f)L50.55 0.55 0.55  
10% % 0%  
0.50 率 0.50 0.50  
财0.45 谢 0.45  
反0.40 一耕作土壤 --林地土壤 反 0.40 耕作土壤 -林地土壤 反0.40 一耕作土壤 --林地土壤盐渍土壤 ---荒漠土壤 盐渍土壤 = -荒漠土壤 、 盐渍土壤 ---荒漠土壤0.35 0.35 0.350 009 1008 000[ 2000 00VI 009I 008I 40 300 008 000[ 0000 000 009I 008[ 000 0 80 000I 0000 000I 009I 008波长／nm 波长/nm 波长/nm(g)L6 (h)L7 ()L80.60 0.60 0.600.55 0.55 0.55%/率 0.50  
反0.40 -耕作土壤 --林地土壤 反 0.40 耕作土壤 -林地土壤 0.40 耕作土壤 --林地土壤盐渍土壤 ---荒漠土壤 盐渍土壤 --荒漠土壤 盐渍土壤 ---荒漠土壤0.35 0.35 0.3540 30 008 000[ 0000 000 009 008[ 0000 2000 200 0 009 008 000[ 0000 00 009 008 0000 000 80 008 000I 0000 000 1009 008I 0000 000 001 1 1 1 2 2波长／nm 波长/nm 波长／nm

平下的 $F$ 检验。在表3中， $L 1 \sim L 3$ 层通过相关性显著性检验波段的数量几乎一致，同时敏感波段基本集中在 $2 \ 3 3 7 \ \mathrm { n m }$ 附近，最大相关系数为0.4358，变化趋势不明显，随着分解层数的增加，SOM的显著性波段在 $L 6$ 达到最多，但是在L7与 $L 8$ 分解光谱的显著性波段数快速减少，同时最大相关系数也迅速减少。由于 $L 6$ 层分解光谱不仅能去噪，还能最大程度保留光谱信息，因此本研究选择最大分解层数为6层，并在 $L 1 \sim L 6$ 的基础上进一步分析。

表3SOM与各层特征光谱相关分析  
Tab.3Correlation analysis between SOM and spectra from wavelet analysisineach level   

<html><body><table><tr><td>小波分解层</td><td>敏感波段数</td><td>波段</td><td>最大相关系数</td></tr><tr><td>L1</td><td>302</td><td>2338</td><td>0.435 8</td></tr><tr><td>L2</td><td>298</td><td>2337</td><td>0.435 6</td></tr><tr><td>L3</td><td>299</td><td>2 337</td><td>0.435 5</td></tr><tr><td>L4</td><td>299</td><td>2337</td><td>0. 434 7</td></tr><tr><td>L5</td><td>304</td><td>2330</td><td>0.431 4</td></tr><tr><td>L6</td><td>268</td><td>2 310</td><td>0.425 3</td></tr><tr><td>L7</td><td>293</td><td>2320</td><td>0.416 7</td></tr><tr><td>L8</td><td>285</td><td>2 348</td><td>0.414 0</td></tr></table></body></html>

以光谱反射率 $R$ 及其9种常规数学变换与SOM含量的相关系数通过显著性检验的最大相关系数以及所在波段位置进行统计，如表4所示。观察发现前4种数学变换敏感波段基本在 $2 ~ 3 0 0 ~ \textdegree$ $2 ~ 4 0 0 ~ \mathrm { n m }$ 之间，且最大相关系数在 $0 . 4 0 \sim 0 . 5 0$ 左右，后4种经过微分变换的敏感波段集中在 $2 ~ 1 0 0 \sim$ $2 \ 3 0 0 \ \mathrm { n m }$ 之间,且最大相关系数在 $0 . 4 5 \sim 0 . 7 0$ 之间。此外，由表4看出，在经过 $( 1 / \mathrm { L g } R )$ '数学变换,各敏感波段在此处均出现了较高的相关系数，其他微分处理均很好的提高了相关性，观察得出各分解层数经过微分变换后均极大提高了与SOM含量的相关性，同时最大相关系数集中在L4重构光谱范

Tab.4Maximum correlation and the location of its band between SOMand different mathematical transformation of reconstruction spectra   

<html><body><table><tr><td></td><td>R</td><td>LgR</td><td>1/R</td><td>Lg1/R</td><td>1/LgR</td><td>R'</td><td>(LgR)'</td><td>(1/R)'</td><td>(Lg1/R)'</td><td>(1/LgR)'</td><td>R'</td></tr><tr><td>L0</td><td>Band</td><td>2 337</td><td>2337</td><td>2337</td><td>2 337</td><td>2 339</td><td>2110</td><td>2304</td><td>844</td><td>2 304</td><td>2109</td></tr><tr><td rowspan="2"></td><td>R²</td><td>0.436</td><td>0.417</td><td>-0.398</td><td>-0.417</td><td>-0.484</td><td>0. 449</td><td>0. 445</td><td>-0.477</td><td>-0.446</td><td>-0.609</td></tr><tr><td>Band</td><td>2338</td><td>2338</td><td>2 338</td><td>2337</td><td>2338</td><td>2288</td><td>2288</td><td>843</td><td>2 288</td><td>2109</td></tr><tr><td rowspan="2">L1 L2</td><td>R²</td><td>0.436</td><td>0.417</td><td>-0.398</td><td>-0.417</td><td>-0.484</td><td>0.468</td><td>0.456</td><td>-0.465</td><td>-0.455</td><td>-0.620</td></tr><tr><td>Band</td><td>2 337</td><td>2 336</td><td>2 336</td><td>2 337</td><td>2 338</td><td>2283</td><td>2 283</td><td>2283</td><td>2283</td><td>2110</td></tr><tr><td rowspan="2">L3</td><td>R</td><td>0.436</td><td>0.417</td><td>-0.398</td><td>-0.417</td><td>-0.484</td><td>0.498</td><td>0.496</td><td>-0.489</td><td>-0.496</td><td>-0.596</td></tr><tr><td>Band</td><td>2 337</td><td>2 337</td><td>2336</td><td>2337</td><td>2339</td><td>2 280</td><td>2 283</td><td>2283</td><td>2283</td><td>2280</td></tr><tr><td rowspan="2">L4</td><td>R²</td><td>0.436</td><td>0.417</td><td>-0.398</td><td>-0.417</td><td>-0.484</td><td>0.547</td><td>0.526</td><td>-0.511</td><td>-0.527</td><td>-0.655</td></tr><tr><td>Band</td><td>2 337</td><td>2 335</td><td>2 334</td><td>2335</td><td>2 338</td><td>2281</td><td>2 281</td><td>2 281</td><td>2 281</td><td>2 281</td></tr><tr><td rowspan="2">L5</td><td>R²</td><td>0.435</td><td>0.416</td><td>-0.397</td><td>-0.416</td><td>-0.483</td><td>0.567</td><td>0.532</td><td>-0.505</td><td>-0.532</td><td>-0.688</td></tr><tr><td>Band</td><td>2330</td><td>2 328</td><td>2 327</td><td>2328</td><td>2 335</td><td>2 212</td><td>2 210</td><td>2210</td><td>2 210</td><td>2 276</td></tr><tr><td rowspan="2">L6</td><td>R²</td><td>0.431</td><td>0.413</td><td>-0.394</td><td>-0.413</td><td>-0.479</td><td>0.528</td><td>0.535</td><td>-0.524</td><td>-0.534</td><td>-0. 635</td></tr><tr><td>Band</td><td>2310</td><td>2309</td><td>2308</td><td>2309</td><td>2 325</td><td>2 273</td><td>2 216</td><td>2 216</td><td>2 216</td><td></td></tr><tr><td></td><td>R²</td><td>0.425</td><td>0.406</td><td>-0.388</td><td>-0.406</td><td>-0.475</td><td>0.461</td><td>0.479</td><td>-0.524</td><td>-0.478</td><td>2 273 -0.527</td></tr></table></body></html>

注：Band代表最大相关系数波段的所在位置， $R$ 代表最大相关系数，L0代表没有经过小波变换的原始光谱

围的 $2 \ 2 8 1 \ \mathrm { n m }$ 波段周围。

# 2.5SOM与重构光谱重要性分析

以SOM含量为因变量，在L0至L6小波分解光谱中,选择每一层及其9种数学变换中相关系数最大的波段的反射率共7种因子作为模型的自变量，建立随机森林分类预测模型，表5为 $R F$ 模型精度拟合结果。观察得,训练集的 $R ^ { 2 }$ 为 $0 . 6 8 , R M S E$ 为2.11,测试集 $R ^ { 2 }$ 为 $0 . 7 0 , R M S E$ 为2.45。

图4列出了7种因子对SOM含量的影响贡献度，即 L0-1/LgR、L1-1/LgR、L2-（1/LgR）'、L3-（204号 $\left( 1 / \mathrm { L g } R \right) ^ { \prime }$ 、L4-(1/LgR）'、L5-(1/LgR）'、L6-$( 1 / \mathrm { L g } R ) ^ { \prime }$ ，同时 Mean Decrease Accuracy 分别为$1 7 . 4 1 \ 、 1 2 . 9 7 \ 、 8 . 0 4 \ 、 6 . 8 2 \ 、 6 . 1 6 \ 、 2 . 8 7 \ 、 2 . 7 4$ ，并按照从高到低进行排序。由图4观察得，对 $s o M$ 含量影响较大的因子为 $L 3 \mathrm { - } ( 1 / \mathrm { L g } R ) ^ { \prime }$ ,其次为 $L 4 \mathrm { - } ( 1 / \mathrm { L g } R ) ^ { \prime }$ ）L6-（1/LgR）'、L5-（1/LgR）'、L2-（1/LgR）'、L0-$1 / \mathrm { L g } R \ 、 L 1 \ – 1 / \mathrm { L g } R $ 。小波分解光谱中频范围，即 $L 3$ 与 $L \boldsymbol { 4 }$ 层结合( $\mathrm { ( 1 / L g } R \mathrm { ) }$ '数学变换对SOM预测贡献度最大,高频与低频范围,即 $L 2 \_ L 5 \_ L 6$ 层结合( $1 / \mathrm { L g } R )$ 1数学变换对SOM含量影响较小， $\textstyle L 0 - 1 / \operatorname { L g } R$ 与L1-1/LgR因子对SOM含量预测贡献度最小。

表4SOM与重构光谱数学变换的最大相关性及其波段所处位置  
表5SOM含量随机森林模型模拟精度  
Tab.5Simulation accuracy of random organic forest model of soil organic matter content   

<html><body><table><tr><td></td><td>R²</td><td>RMSE</td></tr><tr><td>训练集</td><td>0.68</td><td>2.11</td></tr><tr><td>测试集</td><td>0.70</td><td>2.45</td></tr></table></body></html>

![](images/d10131104cc3cdfd839368b328de45470d6b0298e47ecb311790de53f415f0e4.jpg)  
图4土壤有机质含量在各小波分解特征光谱的变量重要性 Fig.4Importance of soil organic matter content in the spectral characteristics of each wavelet decomposition

利用灰色关联分析法对数学变换后的6层重构光谱与SOM含量进行分析，并对其结果进行排序，见表6。除了 $L 0$ 原始光谱以及不同数学变换与SOM含量的灰色关联度，其它重构光谱灰色关联度排序大概相似。根据 $\boldsymbol { L 1 }$ ,其排列顺序为 $R \ > \ 1 / \mathrm { L g } R$ $> 1 / R ~ > ~ ( 1 / \mathrm { L g } R ) ^ { \prime } > \mathrm { L g } 1 / R ~ > ~ \mathrm { L g } R ~ > ~ ( 1 / R ) ^ { \prime } >$ $( \mathrm { L g } R ) ^ { \prime } > ( \mathrm { L g } 1 / R ) ^ { \prime } > R ^ { \prime }$ 。通过对比灰色关联分析与随机森林建模分类，研究发现在灰色关联分析下，各层重构光谱关联度排序为原始光谱第一，其次是各数学变换重构光谱，并且无法区分各层重构光谱的纵向排序，相反随机森林分类方法，各因子在重要性排序过程中，纵向与横向排列中都能进行有效的区分。研究表明：机器学习分类方法相比较传统线性数学模型分类，具有较好的灵活性、实用性。

Fig.6Gray relational analysis of different mathematical transformation of reconstruction spectra of each level   

<html><body><table><tr><td></td><td></td><td>R</td><td>LgR</td><td>1/R</td><td>Lg1/R</td><td>1/LgR</td><td>R'</td><td>(LgR)'</td><td>(1/R)'</td><td>(Lg1/R)'</td><td>(1/LgR)'</td></tr><tr><td>L0</td><td>关联度(P=0.5)</td><td>0.5662</td><td>0.5449</td><td>0.56</td><td>0.5449</td><td>0.5542</td><td>0.5863</td><td>0.4341</td><td>0.4439</td><td>0.4335</td><td>0.5537</td></tr><tr><td>L1</td><td>排序 关联度(P=0.5)</td><td>2 0.9084</td><td>7 0.894</td><td>3</td><td>6 0.894</td><td>4</td><td>1 0.3336</td><td>9</td><td>8</td><td>10</td><td>5</td></tr><tr><td></td><td>排序</td><td>1</td><td>6</td><td>0.8993 3</td><td>5</td><td>0.9064 2</td><td>10</td><td>0.4006 8</td><td>0.8363 7</td><td>0.4003 9</td><td>0.8945 4</td></tr><tr><td>L2</td><td>关联度(P=0.5)</td><td>0.6673</td><td>0.6428</td><td>0.6562</td><td>0.6428</td><td>0.6579</td><td>0.4496</td><td>0. 4441</td><td>0.4301</td><td>0.444</td><td>0.6521</td></tr><tr><td></td><td>排序</td><td>1</td><td>5</td><td>3</td><td>6</td><td>2</td><td>7</td><td>8</td><td>10</td><td>9</td><td>4</td></tr><tr><td>L3</td><td>关联度(P=0.5)</td><td>0.7852</td><td>0.7619</td><td>0.772</td><td>0.7619</td><td>0.7794</td><td>0.4926</td><td>0.5708</td><td>0.5736</td><td>0.571</td><td>0.4699</td></tr><tr><td>L4</td><td>排序 关联度(P=0.5)</td><td>1</td><td>5</td><td>3</td><td>4</td><td>2</td><td>9</td><td>8</td><td>6</td><td>7</td><td>10</td></tr><tr><td></td><td>排序</td><td>0.8979 1</td><td>0.8825</td><td>0.8883</td><td>0.8825</td><td>0.8956</td><td>0.6016</td><td>0. 6255</td><td>0.6414</td><td>0.6253</td><td>0.5029</td></tr><tr><td>L5</td><td>关联度（P=0.5)</td><td>0.7215</td><td>4</td><td>3</td><td>5</td><td>2</td><td>9</td><td>7</td><td>6</td><td>8</td><td>10</td></tr><tr><td></td><td>排序</td><td>1</td><td>0.6972 4</td><td>0.7094 3</td><td>0.6972 5</td><td>0.7134</td><td>0.4622 9</td><td>0.6651</td><td>0.6468</td><td>0.6653</td><td>0.3757</td></tr><tr><td>L6</td><td>关联度(P=0.5)</td><td>0.7924</td><td></td><td></td><td></td><td>2</td><td></td><td>7</td><td>8</td><td>6</td><td>10</td></tr><tr><td></td><td>排序</td><td>1</td><td>0.7698 5</td><td>0.7803 3</td><td>0.7698 4</td><td>0.786 2</td><td>0.4012 10</td><td>0.7673 7</td><td>0.7581 8</td><td>0.7673 6</td><td>0.4795</td></tr></table></body></html>

注：关联度在灰色关联分析中代表灰色关联系数，排序在灰色关联分析中代表关联程度

# 2.6SOM含量建模验证与分析

选取原始光谱与重构光谱中与SOM相关性最大的波段为多元逐步回归模型的自变量， $s o M$ 含量为模型的因变量。并且参照SOM含量与重构光谱随机森林分类结果，即 $L 0 \mathrm { \ t { \ L g } } R \mathrm { \ t l { - } } 1 / \mathrm { L g } R \mathrm { \ t { \ L 2 - } } ( 1 /$ $\mathrm { L g } R ) ^ { \prime } , L 3 \mathrm { - } ( 1 / \mathrm { L g } R ) ^ { \prime } , L 4 \mathrm { - } ( 1 / \mathrm { L g } R ) ^ { \prime } , L 5 \mathrm { - } ( 1 / \mathrm { L g } R ) ^ { \prime } ,$ L6-(1/LgR)'一一对应的特征波段作为多元逐步回归建模自变量 $L \mathrm { - } M C , S O M$ 含量作为模型因变量，模型参数和精度参数如表7所示。根据表7所示的具体每一层重构光谱模型的精度参数进行分析发现，上述9个模型中，无论是建模集还是验证集， $R P D \geqslant$

1.4的模型达到8个。在 $L 0 \sim L 6$ 中，除了L6外，其它各层重构光谱均能很好的提升模型的精度，同时L-MC模型，精度最高， $R _ { c } ^ { 2 } = 0 . 7 3$ ，建模 $R P D$ 为1.94,$R _ { \mathrm { } _ { p } } ^ { 2 } = 0 . 7 4$ ,验证 $R P D$ 为1.96。同时发现基于 $L 4$ 与$L 3$ 重构光谱所构建的模型，预测精度较高，验证RPD达到1.80以上。说明经过小波变换后 $L 3 \ , L 4$ 层重构光谱可以一定程度增强光谱对SOM含量的敏感程度，这3种模型对于研究区的 $s o M$ 含量具有较好的定量反演能力。所以确定这3种模型为最优反演模型。

图5基于 $L 3 \ , L 4$ 和 $_ { L - M C }$ 模型中实测值与预测值的散点图。由图中可以看出 $L 3 \ , L 4$ 和 $_ { L - M C }$ 中样点基本分布于 $1 : 1$ 线附近。各拟合线中， $_ { L - M C }$ 的系数最小,其中 $\textstyle R ^ { 2 }$ 达到 $0 . 7 4 , R P D = 1 . 9 6$ 。

表6各层重构光谱与不同数学变换的灰色关联分析  
表7土壤有机质含量反演模型及精度验证  
Tab.7Inversion models of soil organic matter content and precision validation   

<html><body><table><tr><td rowspan="2">变量</td><td rowspan="2">模型</td><td colspan="2">建模集</td><td colspan="2">验证集</td></tr><tr><td>R</td><td>RPD</td><td>R</td><td>RPD</td></tr><tr><td>L0</td><td>Y=23.6-6965.58X2109J +54 553.28X2304G</td><td>0.68</td><td>1. 77</td><td>0.65</td><td>1. 60</td></tr><tr><td>L1</td><td>Y =14.67 -7 570.08X2109J</td><td>0.61</td><td>1.6</td><td>0.62</td><td>1.58</td></tr><tr><td>L2</td><td>Y=19.48-7371.65X211g + 55 148.13X2283F</td><td>0.66</td><td>1.72</td><td>0.66</td><td>1. 65</td></tr><tr><td>L3</td><td>Y=36.14-42583.03X280J-206784.62X2280F</td><td>0.64</td><td>1.68</td><td>0.72</td><td>1.81</td></tr><tr><td>L4</td><td>Y=33.18-34335.85X281 -146964.93X2281F</td><td>0.70</td><td>1.82</td><td>0.72</td><td>1.83</td></tr><tr><td>L5</td><td>Y=8.15-19945.83X226] +47740.17X12F +6450.H</td><td>0.76</td><td>2.06</td><td>0.63</td><td>1.60</td></tr><tr><td>L6</td><td>Y =34.67 -11. 62X2325E + 282 270.09X2216G</td><td>0.51</td><td>1.43</td><td>0.49</td><td>1.40</td></tr><tr><td>L-MC</td><td>Y=24.84 -13355.03X2281J(I4)-3962.40X2109J(ZO)</td><td>0.73</td><td>1. 94</td><td>0.74</td><td>1.96</td></tr></table></body></html>

注 $: J$ 代表（ $\mathrm { \Omega } _ { \mathrm { . 1 / L g } R _ { \mathrm { . } } }$ '， $G$ 代表 $\left( \mathrm { L g } R \right) ^ { \prime } , F$ 代表 $R ^ { \prime } , H$ 代表 $( 1 / R )$ 1

![](images/d5a1a347818375cbacdc7de44431165294622fedf66757b4b8a0091f3f96224b.jpg)  
Fig.5MeasuredvaluesofSOMinL3,L4andL-MC modelswere comparedwiththepredictedvalues

![](images/a09b54b316bd913c854f0bdcc25713323d0a639cbd0993259268edfa7af621d7.jpg)  
图5L3、L4与L-MC模型的SOM含量实测值与预测值比较

# 3讨论

本研究结果表明，通过小波变换分解光谱结合数学微分变换与随机森林重要性参数分类方法，优选有效的特征波段，将所得结果作为SOM含量多元线性模型预测的重要因子，可以有效的实现干旱区SOM含量的快速估测。

研究区为典型的内陆干旱区，绿洲边缘部分盐渍化与荒漠化现象明显，长年累月侵蚀内部农田，通过分析农田土壤、林地土壤与盐渍土壤、荒漠土壤在相同SOM含量下光谱曲线的差异，发现富含养分的土壤类型与贫瘠土壤类型的光谱曲线在水分波段吸收谷与整体波动存在很大差异，结合小波变换，凸显和简化了不同土壤类型光谱曲线的差异。根据SHI等[28]研究土壤光谱曲线反射率随着 SOM含量的升高总体呈下降的趋势，同时SOM含量与光谱反射率的相关系数较高峰值集中在 $4 0 0 \ \mathrm { n m } \ 、 8 0 0 \ \mathrm { n m } \ 、 1 \ 4 0 0$ $\mathbf { n m }$ 与 $2 \ 2 0 0 \ \mathrm { n m }$ 范围内。如图2、图3和表3所示，本研究中，不同SOM含量下与不同类型土壤的分解特征光谱符合 SHI等[28]研究,同时 SOM含量与各小波分解特征光谱的相关系数高值集中在 $2 2 0 0 \ \mathrm { n m }$ 范围内。高光谱遥感的本质是将待测物连续通道的电磁波谱信息转化为光信号，常用的光谱去噪声手段以微分处理、S-G平滑、多元散射校正与标准正态变换等方法为主，上述方法在光信号处理上较为适用，但是这些方法在对光谱数据去噪的同时难免会引入新的噪声，而小波变换凭借在时域和频域对于信号的局部化分析能力，通过伸缩平移对信号逐步进行多尺度细化，最终达到高频与低频处信号的细分，在保留原状信号的同时，尽可能的分离噪声，是一种较好的电信号噪声去除方法。结合相关性分析与分解光谱特征分析的结果，本文确定最佳SOM特征光谱的小波分解层数为6。陈红艳等[18]研究小波分解后的潮土光谱与SOM含量的关系，并将小波分解光谱层确定为9层;王延仓等[19研究了小波分解后的北方潮土光谱与SOM含量的关系，进一步将小波分解光谱层数确定为6;张锐等[17]研究了小波变换后的原状水稻土光谱与SOM含量的相关性，相关系数与敏感波段在第6层达到最高，以上研究表明，最优分解层不一定都相同，原因包括土壤类型、土壤质地、土壤水分等其他因素。

随机森林预测分类模型相较于传统的线性预测分类模型，比如灰色关联分析，具有显著的优越性。灰色关联分析已经广泛用于土壤光谱研究中，但只能对于土壤的某些特定属性与近红外光谱之间的理想线性关系进行模拟，然而土壤属性与相应近红外光谱之间的关系不仅仅是简单的线性关系，所以利用简单的线性预测分类，不能有效的反应土壤性质与特征光谱之间的真实关系。随机森林模型在描述两者之间的非线性关系，通常会取得理想的预测分类结果。在两类预测分类模型中，随机森林模型不仅在统计结果上优于灰色关联分析，也在预测能力上表现出更优的可靠性和稳定性。

小波分解将光谱分成了不同频率并重构，低频范围包含了更多高频范围，高频范围更多反映了土壤中全氮、全磷等信息的光谱细节。为了更进一步探讨各小波分解层结合数学变换对SOM含量光谱预测的影响，利用随机森林预测分类，获得各因子对于SOM含量预测的重要性，进一步验证了中频范围的小波分解结合（1/LgR）'数学变换不仅能有效去除光谱噪声，还能保持SOM的光谱细节，解决了土壤光谱有机质信息噪声去除与保留信息之间的矛盾。但是根据王延仓等[19研究，小波分解重构光谱在低频范围对SOM含量的估测能力优于高频范围，本实验中，高频范围分解光谱对SOM含量估测能力较弱，与其相符，但基于中频范围L3与 $L \boldsymbol { 4 }$ 层模型的估测能力最高，与其不符。可能是土壤类型的不同，导致实验结果不一致。

本文存在一定不足，土壤中其他属性必然会对SOM光谱预测产生影响，比如土壤水分，如何有效的减少该方面的影响仍需展开研究；随机森林预测分类模型需要更多参数大规模复杂训练，以及对生成树的数量( $B = \mathrm { n t r e e } )$ 和预测变量树( $\begin{array} { r } { d = \operatorname* { m t r y } , } \end{array}$ 参数进行反复设定，选择最优解。本文利用典型样点得到较好的预测精度，下一步研究中，将扩大样点数，对随机森林模型进行训练，获得更可靠的结果，同时将反射光谱与现有的多源遥感系统相结合，为干旱区土壤养分的研究提供科学依据。

# 4结论

本研究以小波变换对原始土壤光谱进行分解重构，分别分析了不同SOM含量与不同土壤类型的小波分解光谱差异。通过相关性分析和特征光谱分析结果，确定小波分解的最大尺度，对各分解光谱进行数学变换，结合随机森林建模分类与灰色关联分析，分析各因子对于SOM含量预测的重要性。主要结论如下：

（1）富含养分的土壤类型较贫瘠土壤类型的光谱曲线在水分波段吸收谷范围内整体波动更大，随着分解层数增加光谱曲线逐渐变得平滑，基本看不出显著差别。

（2）小波变换不同分解层，从低频到高频范围内与SOM含量的相关性呈现先减后增的趋势，第6层显著波段较多且相关性较高，同时光谱细节保持良好，确定第6层为最大分解层数。

（3）通过灰色关联分析与随机森林预测分类的结果比较，随机森林模型相比灰色关联分析对于各小波分解层因子的筛选符合预期，按照对 $s o M$ 含量影响从高到低排序为 $L 3 \mathrm { - } ( \mathrm { 1 / L g } R ) ^ { \prime } \mathrm { , } L 4 \mathrm { - } ( \mathrm { 1 / L g } R ) ^ { \prime } \mathrm { . }$ ，L6-（1/LgR）'、L5-（1/LgR）'、 $L 2$ -（1/LgR）'、 $L 0$ $1 / \mathrm { L g } R , { \cal L } 1 \mathrm { - 1 / L g } R _ { \odot }$

（4）小波分解的中频范围 $L 3$ 与 $L \boldsymbol { 4 }$ 模型，以及L-MC模型对干旱区SOM含量的反射光谱快速估算较为适用。

# 参考文献(References)

[1］张勇,庞学勇,包维楷,等.土壤有机质及其研究方法综述[J]. 世界科技研究与发展,2005.27（5）:72-78.[ZHANG Yong, PANG Xueyong,BAO Weikai,et al.A review of soil organic matter and its research methods[J].World Sci-Tech R&D,2005,27（5）：   
72-78.] [2]程朋根,吴剑,李大军,等.土壤有机质高光谱遥感和地统计定 量预测[J].农业工程学报,2009,25（3）：142-147.［CHENG Penggen,WU Jian,LI Dajun,et al. Quantitative prediction of soil organic matter content using hyper spectral remote sensing and geostatistics[J].Transactions of the Chinese Society of Agricultural Engineering,2009,25（3）:142-147.] [3]何挺,王静,林宗坚,等.土壤有机质光谱特征研究[J].武汉大 学学报（信息科学版）,2006,31（11）:975－979.［HE Ting, WANG Jing,LIN Zongjian,et al. Spectral features of soil organic matter[J].Geomatics and Information Science of Wuhan University（Information Science Edition）,2006,31（11） :975-979.] [4］刘磊,沈润平,丁国香.基于高光谱的土壤有机质含量估算研 究［J].光谱学与光谱分析,2011,31（3）：762-766.［LIULei, SHEN Ruiping,Ding Guoxiang.Studies on the estimation of soil organic mattr content based on hyper-spectrum[J].Spectroscopy and Spectral Analysis,2011,31(3):762-766.] [5］叶勤,姜雪芹,李西灿,等.基于高光谱数据的土壤有机质含量 反演模型比较[J].农业机械学报，2017，48(3）：164-172［YE Qin,JIANG Xueqin,LI Xican,et al. Comparison on inversion model of soil organic matter content based on hyperspectral data[J]. Transactions of the Chinese Society for Agricultural Machinery,   
2017,48(3) :164 -172.] [6]郑曼迪，熊黑钢,乔娟峰，等.基于宽波段与窄波段综合光谱指 数的土壤有机质遥感反演[J].激光与光电子学进展，2018,55 (7）.[ZHENG Mandi,XIONG Heigang,QIAO Juanfeng,et al. Remote sensing inversion of soil organic matter based on broad band and narrow band comprehensive spectral index[J].Laser & Optoelectronics Progress,2018,55（7）.]   
[7]郑曼迪,熊黑钢,乔娟峰,等.基于高光谱的不同人类干扰程度 下荒漠土壤有机质含量估算模型[J].干旱区地理,2018,41 (2）:167-175.[ZHENG Mandi,XIONG Heigang,QIAO Juanfeng,etal.Hyperspectral based estimation model about organic matter in desert soil at different levels of human disturbance[J]. Arid Land Geography,2018,41(2）:167 -175.]   
[8］彭杰,张杨珠,庞新安,等.新疆南部土壤有机质含量的高光谱 特征分析[J].干旱区地理,2010,33（5）：740-746.［PENG Jie,ZHANG Yangzhu,PANG Xinan,et al. Hyperspectral features of soil organic matter content in south Xingjiang[J].Arid Lad Geography,2010,33(5）:740-746.]   
[9］沈润平,丁国香,魏国栓,等.基于人工神经网络的土壤有机质 含量高光谱反演[J].土壤学报,2009,46（3）:391－397. [SHEN Ruiping,DING Guoxiang,WEI Guoshuan,et al. Retrieval of soil organic matter content from hyper-spectrum based on ANN [J].Acta Pedologoca Sinica,2009,46(3）:391-397.]   
[10］于雷,洪永胜,朱亚星,等.去除土壤水分对高光谱估算土壤有 机质含量的影响[J].光谱学与光谱分析,2017,37（7）：2146- 2151.[YU Lei,Hong Yongsheng,ZHU Yaxing,et al. Removing the effect of soil moisture content on hyperspectral reflectance for the estimation of soil organic mater content[J]. Spectroscopy and Spectral Analysis,2017,37(7) :2146 -2151.]   
[11]MORGAN C L S,WAISER T H,BROWN D J,et al. Simulated in situ characterization of soil organic and inorganic carbon with visible near-infrared diffuse reflectance spectroscopy[J]. Geoderma, 2009,151(3 -4):249 - 256.   
[12]RIENZI E A,MIJATOVIC B,MUELLER T G,et al.Prediction of soil organic carbon under varying moisture levels using reflectance spectroscopy[J].Soil Science Society of America Journal,2014,78 (3):958-967.   
[13]NOCITA M,STEVENS A,NOON C,et al.Prediction of soil organic carbon for different levels of soil moisture using Vis-NIR spectroscopy[J].Geoderma,2013,199:37 -42.   
[14]LIAO Q H,GU XH,LIC J,et al.Estimation of fluvo-aquic soil organic mater content from hyperspectral reflectance based on continuous wavelet transformation[J].Transactions of the Chinese Society of Agricultural Engineering,2012,28(23）:132-139.   
[15]YANG HF,QIAN YR,YANGF,et al. Using wavelet transform of hyperspectral reflectance data for extracting spectral featuresof soil organic carbonandnitrogen[J].Soil Science,2012,177（11）: 674 - 681.   
[16] LIN L,WANG Y,TENG JY,et al. Hyperspectral analysis of soil organic matter in coal mining regions using wavelets,correlations, and partial leastsquaresregressonJ].Environmental Monitoring & Assessment,2016,188(2) :97.   
[17］张锐,李兆富,潘剑君.小波包一局部最相关算法提高土壤有 机碳含量高光谱预测精度［J].农业工程学报,2017,33（1)： 175-181.[ ZHANG Rui,LI Zhaofu. PAN Jianjun. Coupling discrete wavelet packet transformation and local correlation maximization improving prediction accuracy of soil organic carbon based on hyperspectral reflectance[J].Transactions of the Chinese Society of Agricultural Engineering,2017,33（1）:175-181.]   
[18］陈红艳,赵庚星,李希灿,等.基于小波变换的土壤有机质含量 高光谱估测[J].应用生态学报,2011,22（11）：2935－2942 [CHEN Hongyan,ZHAO Gengxing,LI Xican,etal. Hyper-spectral estimation of soil organic matter content based on wavelet transformation[J]. Chinese Journal of Applied Ecology,2011,22（11）: 2935-2942.]   
[19］王延仓,杨贵军,朱金山,等.基于小波变换与偏最小二乘耦合 模型估测北方潮土有机质含量[J].光谱学与光谱分析,2014, 34（7）:1922-1926.[WANG Yancang,YANG Guijun,ZHU Jinshan,et al.Estimation of organic matter content of north fluvo-aquic soil based on the coupling model of wavelet transform and partial least squares[J]. Spectroscopy and Spectral Analysis,2014,34 (7):1922 - 1926.]   
[20］蔡亮红,丁建丽.基于高光谱多尺度分解的土壤含水量反演 [J].激光与光电子学进展,2018,55（1):013001[CAI Lianghong,DING Jianli.Inversion of soil moisturecontent based on hyperspectral multi-scale[J]. Laser& Optoelectronics Progress， 2018,55(1) :013001. ]   
[21］唐梦迎,丁建丽,夏楠,等.干旱区典型绿洲土壤有机质含量分 布特征及其影响因素[J].土壤学报,2017,54（3）:759－766. [TANG Mengying,DING Jianli,XIA Nan,et al.Distribution of soil organic matter content and its affecting factors in oases typical of arid region[J].Acta Pedologica Sinica,2017,54(3):759-766]   
[22］刘广崧,蒋能慧,张连第.土壤理化分析与剖面描述［M].北 京：中国标准出版社,1996:166－167.［LIU Guangsong,JIANG Nenghui,ZHANG Liandi.Soil physical and chemical analysis and profile description[M]. Beijing:Standrds Press of China,1996: 166 -167. ]   
[23］中国土壤学会农业化学专业委员会·土壤农业化学常规分析 方法［M].北京:科学出版社,1989.[Agricultural chemical specialized committee of china soil society[M].Conventional analytical method of soil agricultural chemistry[M].Beijing:Science Press,1989.]   
[24］陈至坤,张菡洁,王玉田,等.基于小波变换的矿物油荧光光谱 数据处理方法[J].激光杂志,2016,37（10）：78-81.［CHEN Zhikun,ZHANG Hanjie,WANG Yutian,et al.Fluorescence spectral date of mineral oil processing based on wavelet transform[J]. Laser Journal,2016,37（10) :78 -81.]   
[25］刘燕德,欧阳爱国,应义斌.小波分析用于光谱信号处理及其 在Matlab 中的实现[J].传感技术学报,2006,19（3）：821- 823.［LIU Yande,OUYANG Aiguo,YING Yibin.Application of wavelet analysis in signal process using Matlab[J].Chinese Journal of Sensors and Actuators,2006,19(3）:821 -823.]   
[26］沈润平,郭佳,张婧娴,等.基于随机森林的遥感干旱监测模型的 构建[J].地球信息科学学报,2017,19(1）：125-133.[SHEN Ruiping,Guo Jia,ZHANG Jingxian,et al.Construction of a drought monitoring model using the random forest based remote sensing[J]. Journal of Geo-information Science,2017,19(1）:125-133.]   
[27] VAUDOUR E,GILIOT JM,BEL L,et al. Regional prediction of soil organic carbon content over temperate croplands using visible near-infrared airborne hyperspectral imagery and synchronous field spectral[J]. International Journal of Applied Earth Observation & Geoinformation,2016,49:24 -3.   
[28]SHI Z,WANG Q L,PENG J,et al.Development of a national VNIR soil-spectral library for soil clasification and prediction of organic matter concentrations[J].Science China Earth Sciences, 2014,57(7) :1671-1680.   
[29］高志海,白黎娜,王捧瑜,等.荒漠化土地土壤有机质含量的实 测光谱估测[J].林业科学,2011,47(6）：9-16.［GAO Zhihai,

BAILina,WANG Bingyu,et al.Estimation of soil organic matter content in desertified lands using measured soil spectral data[J]. Scientia Silvae Sinicae,2011,47(6):9-16.] [30］李洪.官厅水库消落带土壤有机质分布特征及其高光谱反演 研究［D].北京：首都师范大学，2014：40-60.［LIHong.Distribution characteristics of soil organic matter and its hyperspectral retrieval in the water-level-fluctuating zone of guanting reservoir [D].Beijing:Capital Normal University,2014:40-60.]

# Hyperspectral detection of soil organic matter content based on random forest algorithm

BAO Qing-ling12，DING Jian-li1²，WANG Jing-zhe1.2，CAI Liang-hong1,2 (1KeyLaboratoryofWisdomCityandEnvironmental Modeling DepartmentofEducationXinjiang UniversityUrumqi830046, Xinjiang,China；2KeyLaboratory ofOasis Ecology,Xinjiang University,Urumqi 83o046,Xinjiang,China)

Abstract：In orderto explore how to retain the spectral information and accuratelydetectthe soil organic matter content,this paper investigated the posibilityof using spectral processing techniques such as wavelet decomposition and random forest method to estimate thesoil organic mattercontent and analyze the spectral curves of diffrent wavelet decomposition reconstructionspectra in diferent soil typesusing spectroscopy data.This study took he soil samplesas the study objects which were collcted in Weigan River Oasis of Kuqa County,atypical arid area oasis at north-centralof the Tarim Basin in Xinjiang,China.The soil organic mattercontent of these samples was determined.The ASD Field Spec FR was used to measure the soil samples'spectrum,and the spectral data were preprocessed by waveletdecomposition and mathematical transformation.Discrete wavelet transform（DWT）hasthe functionof multi-scale analysis,whichcan transform multi-scale wavelet decomposition of soil near infrared spectroscopy data to analyze the spectral curves of different wavelet decomposition reconstruction spectra in diffrent organic matter content and different soil types.The correlation analysis was used to determine the maximum wavelet decomposition layer and filtersensitive bands.Finally,amulti-variant linear prediction modelabout soil organic matercontent was established based on the optimal characteristic spectrum producedby combining grey correlation analysis,randomforest method to analyze the significance of diferent wavelet decomposition characteristic spectra.The results showed as follows:（1）The spectral reflectance of each wavelet decomposed is decreased with the increase of organic mater content.At the same time,the spectral curve of cultivated soil and forest soil shows a more gradual change than that of the saline soil and desert soil.（2）The correlation between the decomposition spectrum of the wavelettransform and the soil organic mater content is decreased firstand then increased with the increase of the decomposition layer.Inthe sixth layer,the characteristic spectral curveandthe number of sensitive bands tend to be stable,which helps to determine this layer as the largest decomposition layer of wavelet transform.（3）Compared withthegraycorelationanalysis,therandom forest modelis inline withtheexpectation for screening thefactorsof wavelet decompositionat each layer,and itcomesalistof descending orderaccording tothe impactonsoilorganic matter content as follows:L3-(1/LgR)',L4-(1/LgR)',L6-(1/LgR)',L5-(1/LgR)',L2-(1/LgR)', $L 0 { - } 1 / \mathrm { L g } R , L 1$ 1 1/LgR.（4）Combining all $s o M$ estimation models for statistical analysis,the model based on L-MC has the highest accuracy.The research shows that the monitoring of soil spectral organic mater content based on machine learning clasification method combined with wavelet decomposition can efectively reduce noise band interference and improvethe clasification prediction accuracy of feature bands.The random forest prediction clasification model has significant advantages over the traditional linear prediction classfication model,such asgraycorrelation analysis. Therandom forest model not only outperforms the grey correlation analysis in statistical results,but also shows better reliabilityand stability in predicting ability.Theresults could provide scientificreference and support for the study of soil nutrients in the arid zone and local precision agriculture.

Key words:hyperspectral； soil organic matter content；wavelet transform；random forest