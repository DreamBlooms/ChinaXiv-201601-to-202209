# DOI: 10.5846/stxb201605010828

梁慧玲,王文辉,郭福涛,林芳芳,林玉蕊.比较逻辑斯蒂与地理加权逻辑斯蒂回归模型在福建林火发生的适用性.生态学报,2017,37（12)：4128-4141.  
LiangHL，Wgllforest fire forecasting.Acta Ecologica Sinica,2017,37(12）:4128-4141.

# 比较逻辑斯蒂与地理加权逻辑斯蒂回归模型在福建林火发生的适用性

梁慧玲1,2,3，王文辉²，郭福涛²，林芳芳¹，林玉蕊1，\*

1福建农林大学计算机与信息学院，福州350002  
2福建农林大学林学院，福州350002  
3漳州理工职业学院，漳州363000

摘要;林火预测预报是科学有效进行林火管理的前提，是林业管理部门和科研工作者的广泛关注的领域。逻辑斯蒂回归（Logistic Regresson，LR)是目前国内外广泛应用于森林火灾预测的模型方法,然而近年来有学者发现该方法没有充分考虑林火影响因子的空间相关性和异质性,从而导致模型拟合结果偏差。地理加权逻辑斯蒂回归（Geographically weighted logisticregresion，GWR)模型考虑到了模型变量之间的空间相关性,有效提高的模型的拟合能力。为探讨GWLR 模型在福建林火预测上的适用性,本研究应用LR和GWLR两种方法分别建立福建省森林火灾与气象因子的预测模型,通过模型拟合能力对比，判断在GWLR 的适用性。研究以2000—2005年福建地区森林火灾卫星火点数据和每日气象因子为基础,将全样本分为 $6 0 \%$ 的建模数据和 $4 0 \%$ 的校验数据,并重复5次,建立5个样本组。选择在5个样本组中3个及以上表现显著的变量进入最终模型。研究结果表明GWLR在模型拟合度、模型残差、空间自相关性以及预测准确率等方面均优于LR模型,说明充分考虑模型变量的空间异质性有助于提高模型的预测精度,同时也验证了GWLR 在福建地区林火预测上的适应性。此外,模型参数结果显示，“日最高地表气温”“日最低地表气温”“日平均风速”“24小时降水量”“日最高本站气压”“日照时数”、“日最高气温”和“日最小相对湿度"8个因子对福建省林火发生有显著影响,研究结论为福建地区林火预测预报提供了新的方法。

关键词：林火预测;空间异质性；逻辑斯蒂回归；地理加权逻辑斯蒂回归

# Comparing the application of logistic and geographically weighted logistic regression models for Fujian forest fire forecasting

LIANG Huiling1,2,3，WANG Wenhui²， GUO Futao²，LIN Fangfang¹,LIN Yurui1,\* 1CollegeofComputerandInformationScience,FujianAgricultureandForestry University，Fuzhou35oo02,China 2College of Forestry，Fujian Agriculture and Forestry University，Fuzhou 35ooO2，China 3 Zhangzhou Institute Of Science & Engineering，Zhangzhou 36300o，China

Abstract:Forest fire forecasting isa keycomponent of efective and science-based forest management and has been comprehensivelyaddressed inthescientific literature.The logisticregresion（LR）technique has beenused in forest fire prediction models.However，some scholars have recentlyreported thatthe technique does notadequatelyconsider the spatialcorelationandheterogeneityoffire impactfactors，whichresultsinporlyfiting models.Incontrast，geograpically weighted logisticregression（GWR）modelsconsider the spatial corelationof model variables，which improves the model's goodnessoffit.Inorder toexploretheapplicabilityof theGWLRmodelinFujianforestfireforecasting，thepresentstudy used both theLRand GWLRmethods toestablishforecastmodelforforestfiresand meteorologicalfactorsinFujian Province，andthe modelfiting abilityof two models werecompared.Basedon the forest fireand meteorological data for Fujian from 2OOO to 2Oo5，the original dataset was randomly divided into training （ $60 \%$ ）and validation ( $40 \%$ ）samples, with five replications and five sample groups，and predictors that were significant ( $a = 0 . 0 5$ ）for at least three of the five sample groups were included inthefinalmodels.Thegoodnessoffit，residual eror,spatialautocorrelation，,andprediction accuracyof theGWLRmodel were allbeterthan thoseof theLR model，andtheGWLRcomprehensivelyexplained the spatialheterogeneityofmodel variablesandhelpedtoimprove thepredictionaccuracyof themodel.Thestudyalsoverified thesuitabilityof theGWLRmodelontheforestfireforecasting inFujianarea.Inadition,theresultsalsoindicatedthatthe occurence ofFujian forest fires issignificantlyafected byeight parameters，including minimumand maximum surface temperature，daily average wind speed，daily precipitation，highest station presure，hoursof sunshine，daily maximum temperature，and daily minimum relative humidity.Therefore，the GWLR model mayprovideanew technique for the prediction of forest fires in Fujian Province.

KeyWords:forestfireforecast；spatialheterogeneity；logisticregression；geographicallyweightedlogisticregression (GWLR)

林火是是森林生态系统的重要影响因子,对森林资源与环境造成破坏也会威胁人类生命财产安全[1-3]判定林火发生的影响因子,建立准确的林火预测预报模型对林火管理工作至关重要。目前,国内外有关林火发生的预测模型和影响因子分析已大量开展,主要模型方法为人工神经网络[4]、最大熵算法[5.6]、分类树[7]、泊松回归、负二项回归、零膨胀泊松、零膨胀负二项以及逻辑斯蒂回归模型[-]等,其中逻辑斯蒂模型应用最为广泛。然而以上所有模型均假设因变量与自变量之间的关系是空间平稳的,即模型参数在整个研究区域上是一个不变的常数,通常建模的结果是一套模型参数应用于整个研究区域,也称之为全局模型。然而,随着研究的深入,很多学者发现区域的空间异质性是不容忽略的。林火与影响因子之间的关系在空间上是非平稳的,具有很强的异质性[12-14],因此,以往的全局模型在林火预测预报上可能会产生较大误差。

地理加权回归模型(GWR)考虑了地理空间因素的影响,该模型将一个大的数据集分成了若干小区域,减少了各个模型间的差异性,有助于提高模型精度,可以用来解决空间的平稳性问题。目前,地理加权回归模型主要应用在生态学、经济学和社会科学等领域[15-19]。近年来,国外已有少数学者将该模型的拓展模型即地理加权逻辑斯蒂模型(GWLR)应用于森林火灾的预测预报及林火影响因子的空间分析上,并且表现出较好的拟合效果[12-14]。由于该模型强调自变量与因变量关系的空间异质性,因此模型在不同区域的适用性可能有较大差异。为了探讨GWLR模型对我国亚热带地区林火预测预报的适用性,且由于2000—2005 年福建省的林火发生既不是太多,也不是很少,比较有代表性,因此本文以福建省 2000—2005年卫星火点数据为基础,选取每日气象数据为自变量因子,对模型的拟合能力进行分析,并与传统全局逻辑斯蒂回归模型进行对比,探讨地理加权回归模型在林火预测预报上的适用性。

# 1材料和方法

# 1.1研究区域概况

福建省位于我国东南沿海地区,介于北纬 $2 3 ^ { \circ } 3 3 ^ { \prime } - 2 8 ^ { \circ } 2 0 ^ { \prime }$ 、东经 $1 1 5 ^ { \circ } 5 0 ^ { \prime } { - } 1 2 0 ^ { \circ } 4 0 ^ { \prime }$ 之间(图1)。根据第八次全国森林资源清查结果显示，福建省林业用地面积926.82万 $\mathrm { { h m } } ^ { 2 }$ ，森林面积801.27万 $\mathrm { { h m } } ^ { 2 }$ ,人工林面积377.69万 $\mathrm { { h m } } ^ { 2 }$ ,森林覆盖率 $6 5 . 9 5 \%$ ,森林蓄积量 60796.15万 $\mathbf { m } ^ { 3 [ 2 0 ] }$ ,是我国南方重点林区的省份之一。但是,也是我国森林火灾的高发区。1951—1987年,全省共发生6.2万次的森林火灾,受害山林面积有 150 万 $\mathrm { { h m } } ^ { 2 }$ ，平均每年森林火灾0.1万次,受害山林面积4万 $\mathrm { { h m } } ^ { 2 }$ ,占全省年平均造林面积的 $2 5 \% - 3 3 . 3 \% ^ { [ 2 1 ] }$ ;1998—2007年间，福建省共发生森林火灾4504起，火场面积累计达 $7 9 , 5 7 2 \mathrm { h m } ^ { 2 }$ ,受害森林面积累计达 $5 5 4 8 5 . 6 \ \mathrm { h m } ^ { 2 }$ ,共损失了97万 $\mathbf { m } ^ { 3 }$ 的林木蓄积量，其中2004年发生了1164次火灾，1998 年林火发生次数最少，为156次;仅10年就发生了40 次重大火灾[22]。福建省森林火灾问题尤为严峻。

# 1.2 数据来源与处理

# 1.2.1 数据来源

福建省2000一2005年的林火发生数据（包括起火时间、起火原因、起火地理坐标等)来源于林业科学数据中心（http://www.cfsdc.org/indexAction.action?classId $= 1$ )提供的卫星火点解译数据;历史气象数据来源于中国气象数据共享网络( $\mathrm { \hbar h t t p : / / c d c . c m a . g o v . c n / \hbar }$ ，为2000—2005年福建省内22个国家级气象站的每日气象数据，一共包22个气象因子。由于仪器设备和气象站点变化等原因，造成部分数据缺失，且无法修补。因此，本研究对气象数据进行预处理，剔除部分缺失数据,剩下的气象因子包括日平均地表气温( $^ \circ \mathrm { C } )$ ,日最高地表气温 $( \mathrm { ~ \mathcal { C } ~ } )$ ，日最低地表气温( $^ \circ \mathrm { C } )$ ，日平均风速( $\mathbf { \Sigma } _ { \mathbf { m } } / \mathbf { \Sigma }$ s），日最大风速( $\mathbf { \dot { \Omega } } _ { \mathrm { m / s } } \mathbf { \dot { \Omega } } $ ）,24小时降水量( $\mathbf { \dot { m } } \mathbf { m } _ { \cdot } ^ { \cdot }$ ），日平均本站气压( $\cdot \ \mathrm { h } \mathrm { P a } )$ ,日最高本站气压 $\left( \mathrm { { h P a } } \right)$ ,日最低本站气压 $\left( \mathrm { { h P a } } \right)$ ,日照时数（hour），日平均气温( $\mathcal { C }$ ),日最高气温 $^ { \circ } \mathcal { C } \mathcal { A }$ ，日最低气温( $^ \circ \mathrm { C } )$ ,日平均相对湿度 $( \% )$ ,日最小相对湿度 $( \% )$ 共15个气象因子。

![](images/19854866b3c50ce51698644c1afd72d75f1c330c455e8cd5d8ba3e25fde130c0.jpg)  
图1研究区域示意图Fig.1The study area

# 1.2.2 数据处理

本文以 2000—2005 年的卫星火点数据为基础，从中随机选取 $6 0 \%$ 的训练样本(5210 个林火数据)来构建模型,剩下 $4 0 \%$ 的测试样本(3473个林火数据)用来检验模型。同时,为了避免样本分布对试验结果的影响，本文重复5次试验,即重复5次训练样本和测试样本的随机划分,选择5次试验中出现3次或以上的显著变量进入全样本数据拟合。 人

本文分别应用 SPSS 19.0 和GWR4 软件对逻辑斯蒂回归模型和地理加权逻辑斯蒂回归模型进行拟合,并应用Rookcase软件对模型残差进行空间自相关分析。

# 1.3 研究方法

# 1.3.1二项逻辑斯蒂回归模型

(1)多重共线性(Multicollinearity)是指在线性回归模型中,自变量之间存在精确的相关关系或者高度相关关系的现象。

本文运用方差膨胀因子（the variance inflation factor,VIF)诊断法对林火发生的驱动因子进行方差膨胀因子最早是由 Marquardt于1960 年引入的,第 $i$ 个变量的方差膨胀系数的表达式为

$$
\mathrm { V I F } _ { i } = \frac { 1 } { 1 - R _ { i } ^ { 2 } } \qquad ( i = 1 , 2 , \ldots , n )
$$

式中， $R _ { i }$ 为自变量 $x _ { i }$ 对其余 $\left( n - 1 \right)$ 自变量做线性回归分析的复相关系数。 ${ \mathrm { V I F } } _ { i }$ 的值越大, $R _ { i } ^ { 2 }$ 越接近于1,说明第 $\hat { i }$ 个自变量与其他 $\left( n - 1 \right)$ 个自变量之间存在越强的共线性现象[73,76-77]。当 $0 { < } \mathrm { V I F } { < } 1 0$ 时,说明自变量之间不存在多重共线性现象；当 $1 0 { < } \mathrm { V I F } { < } 1 0 0$ 时，说明自变量之间存在较强的多重共线性现象；当 $\mathrm { V I F } { > } 1 0 0$ 时，说明自变量之间存在严重的多重共线性现象。

(2)逻辑斯蒂回归模型属于广义线性回归模型,对于只有两种分类结果的分类因变量,可以应用二元逻辑斯蒂回归模型进行建模分析,其预测值为在[0,1]之间的预测概率。逻辑斯蒂模型是目前国内外应用最广的用于预测林火发生概率的模型。设有林火发生( $\scriptstyle \gamma = 1$ )的概率为 $P$ ,则无林火发生( $Y = 0$ )的概率为 $( 1 - P )$ ，

则有林火发生的概率

$$
P ( Y = 1 ) = \frac { e ^ { z } } { 1 + e ^ { z } } = \frac { 1 } { 1 + e ^ { - z } }
$$

式中， $z$ 为解释变量 $x _ { 1 } , x _ { 2 } , \ldots , x _ { n }$ 的线性函数,

$$
z = \alpha _ { 0 } + \alpha _ { 1 } x _ { 1 } + \alpha _ { 2 } x _ { 2 } + \ldots + \alpha _ { n } x _ { n }
$$

式中， $\alpha _ { 0 } , \alpha _ { 1 } , \alpha _ { 2 } , \ldots , \alpha _ { n }$ 为各个解释变量的回归系数。

对 $P$ 进行Logit变换，即将 $P$ 变换为 $\ln [ P / ( 1 { - } P ) ]$ ，则有

$$
\ln { \frac { P } { 1 - P } } = z = \alpha _ { 0 } + \alpha _ { 1 } x _ { 1 } + \alpha _ { 2 } x _ { 2 } + . . . + \alpha _ { n } x _ { n }
$$

最后,运用极大似然估计法可求得模型的参数估计系数 $\alpha _ { 0 } , \alpha _ { 1 } , \alpha _ { 2 } , \ldots , \alpha _ { n }$ [23-25]。

# 1.3.2地理加权逻辑斯蒂回归模型

由于地理位置的不同而引起变量之间的关系或者结构发生变化的现象称为空间非平稳性（spatialnonstationarity）。地理加权逻辑斯蒂回归模型是传统逻辑斯蒂回归模型的扩展,考虑了空间位置因素,利用加权最小二乘法对每一个坐标点进行参数估计,对参数的估计是局部而非全局的,每一个位置均有相应的参数估计系数[26-27]。地理加权逻辑斯蒂回归模型(GWLR)的表达式为:与逻辑斯蒂模型相同,位置 $i$ 有林火发生（20 $( Y = 1 )$ 的概率为 $P$ ，则无林火发生( $Y = 0 \mathrm { \dot { \Omega } }$ )的概率为 $( 1 { - } P )$ ,则位置 $i$ 有林火发生概率

$$
P ( \mathbf { \xi } ( Y = 1 ) = \frac { \exp ( \alpha _ { 0 ( u _ { i } , v _ { i } ) } \ + \ \alpha _ { 1 ( u _ { i } , v _ { i } ) } x _ { i 1 } \ + \ \alpha _ { 2 ( u _ { i } , v _ { i } ) } x _ { i 2 } \ + . . . \ + \ \alpha _ { n ( u _ { i } , v _ { i } ) } x _ { i n } ) } { 1 \ + \ \exp ( \alpha _ { 0 ( u _ { i } , v _ { i } ) } \ + \ \alpha _ { 1 ( u _ { i } , v _ { i } ) } x _ { i 1 } \ + \ \alpha _ { 2 ( u _ { i } , v _ { i } ) } x _ { i 2 } \ + . . . \ + \ \alpha _ { n ( u _ { i } , v _ { i } ) } x _ { i n } ) } = \frac { e ^ { 2 } } { 1 \ + \ e ^ { 2 } }
$$

式中， $z = \alpha _ { _ { 0 ( u _ { i } , v _ { i } ) } } \ + \ \alpha _ { _ { 1 ( u _ { i } , v _ { i } ) } } x _ { i 1 } \ + \ \alpha _ { _ { 2 ( u _ { i } , v _ { i } ) } } x _ { i 2 } \ + . . . \ + \ \alpha _ { _ { n ( u _ { i } , v _ { i } ) } } x _ { i n } \ \circ$

经Logit 变换,有

$$
\log \mathrm { i t } ( P ) = \ln { \frac { P } { 1 - P } } = \alpha _ { 0 ( u _ { i } , v _ { i } ) } + \alpha _ { 1 ( u _ { i } , v _ { i } ) } x _ { i 1 } + \alpha _ { 2 ( u _ { i } , v _ { i } ) } x _ { i 2 } + \ldots + \alpha _ { n ( u _ { i } , v _ { i } ) } x _ { i n }
$$

最后，运用加权最小二乘法可求得位置 $\ddot { \iota }$ 的局部回归模型的参数估计系数，即

$$
\hat { \overset { \land } { \alpha } } ( u _ { i } , v _ { i } ) = ( X ^ { T } W ( u _ { i } , v _ { i } ) X ) ^ { - 1 } X ^ { T } \mathbb { W } ( u _ { i } , v _ { i } ) \log i t ( P )
$$

式中 $\left( { { u } _ { i } } , { { v } _ { i } } \right)$ 为位置 $i$ 的地理坐标， $Y _ { \left( u _ { i } , v _ { i } \right) }$ 为位置 $i$ 的因变量, $\eta$ 为误差项。 $\hat { \alpha } ( u _ { i } , v _ { i } )$ 为模型参数 $\alpha _ { 0 ( u _ { i } , v _ { i } ) }$ ，α1(ui),α2(ui)）,αn(u)）的估计值，W(ui,vi）为权重矩阵,X为解释变量矩阵。其中,生成权重矩阵W的做法为：对于给定的位置 $\mathbf { \chi } _ { i , \mathcal { N } _ { i } } ^ { * }$ 为中心画一个半径为 $\boldsymbol { r }$ 的圆,然后计算圆内每个观测点 $j$ 到圆心 $i$ 的距离 $d _ { i j }$ ，从而生成一个空间权重矩阵 $W ^ { [ 1 5 , 2 8 - 2 9 ] }$ 。本研究应用GWLR 模型对火点进行参数估计,并结合 ArcGIS 10.2的局部多项式插值法对整个研究区域进行系数插值估计[30]。

# 1.3.3模型预测准确率计算

本文根据 ROC 曲线分析法所计算出来的敏感性值和特异性值,可求得约登指数,即约登指数 $\mathbf { \Sigma } = \mathbf { \Sigma }$ 敏感性值+特异性值-1,进而计算出福建省林火发生的最佳临界值(cut-off值),如果林火发生的预测概率大于该临界值则认为有林火发生,小于该临界值则认为无林火发生,从而根据模型所计算出来的林火发生次数与实际值进行比较,进而计算出LR模型和GWLR模型模型对林火发生与否的正确判别率。

# 1.3.4 模型空间自相关检验Moran'sI

本文应用全局Moran'sI指数计算残差（残差 $\mathbf { \sigma } = \mathbf { \sigma }$ 观测值-预测值)的空间自相关来对模型进行评价，全局Moran'sI指数的值越小,说明残差的空间依赖程度越低,模型考虑了更多的空间结构问题,模型的效果越好。

全局Moran'sI指数的计算公式为：

http ://www.ecologica.cn

$$
I = \frac { n } { S } \times \left[ \frac { \displaystyle \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } \omega _ { i j } ( e _ { i } - \bar { e } ) \left( e _ { j } - \bar { e } \right) } { \displaystyle \sum _ { i = 1 } ^ { n } \left( e _ { i } - \bar { e } \right) ^ { 2 } } \right]
$$

式中， $n$ 为研究区域内空间单元的个数， $\boldsymbol { e } _ { i }$ 和 $e _ { j }$ 分别为空间单元 $i$ 和 $j$ 上残差值, $\bar { e }$ 为残差 $\boldsymbol { \mathbf { \rho } } _ { e }$ 的平均值,S为残差的标准差， $\omega _ { i j }$ 是空间权重矩阵 $W$ 中对应的元素,如果空间单元 $i$ 和 $j$ 相邻,则 $\omega _ { { i j } } = 1$ ;若不相邻,则 $\omega _ { i j } = 0 _ { \circ } ^ { \prime }$ Moran'sI指数的取值范围为[-1,1],Moran'sI指数的值大于0,说明研究区域的残差值呈空间正相关,小于0表示残差值呈空间负相关,等于0则表明残差不存在空间自相关性[15.31]。

# 2结果与分析

# 2.1模型拟合结果与分析

# 2.1.1多重共线性诊断结果

多重共线性诊断结果显示,变量“日平均地表气温”“日平均本站气压”、“日最低本站气压”、“日平均气温”“日最低气温"等5个变量均存在共线性关系,将这5个变量剔除之后,用剩下的10个自变量构建LR模型和GWLR 模型。

# 2.1.2LR 模型拟合结果

本文应用LR模型和“wald向前"原则对5个训练样本进行拟合计算,得到5个不同的特征变量子集，然后在5个特征变量子集中选择出现3次或3次以上的特征变量进入全样本数据的拟合计算（表1)。

表1LR模型特征变量选择结果  
Table1LR model characteristic variable selection results   

<html><body><table><tr><td>变量 Variable</td><td>样本1 Sample 1</td><td>样本2 Sample 2</td><td>样本3 Sample 3</td><td>样本4 Sample 4</td><td>样本5 Sample 5</td><td>最终样本 Final sample</td><td>样本显著个数 No.samples signif</td></tr><tr><td>日最高地表气温 The highest surface temperature</td><td>+</td><td></td><td>+</td><td>+</td><td>+</td><td>+</td><td>5</td></tr><tr><td>日最低地表气温</td><td></td><td></td><td></td><td>+</td><td>+</td><td>+</td><td>5</td></tr><tr><td>The minimum surface temperature</td><td></td><td></td><td></td><td></td><td></td><td></td><td>5</td></tr><tr><td>日平均风速 Daily average wind speed 日最大风速 Daily maxium wind speed</td><td></td><td>+</td><td>+</td><td>+ 一</td><td>+ 一</td><td>+ 一</td><td>0</td></tr><tr><td>24 小时降水量Daily precipitation</td><td>+</td><td>+</td><td>+</td><td>+</td><td>+</td><td>+</td><td>5</td></tr><tr><td>日最高本站气压</td><td></td><td></td><td></td><td>+</td><td></td><td></td><td>4</td></tr><tr><td>The highest station pressure</td><td>+</td><td>+</td><td>+</td><td></td><td></td><td>+</td><td></td></tr><tr><td>日照时数 Hours of sunshine 日最高气温 Daily maximum temperature</td><td>+ +</td><td>+ +</td><td>+ +</td><td>+ +</td><td>+ +</td><td>+</td><td>5 5</td></tr><tr><td>日平均相对湿度</td><td></td><td></td><td></td><td></td><td>+</td><td>+</td><td>1</td></tr><tr><td>Daily average relative humidity 日最小相对湿度</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

+表示变量在模型里面;-表示变量不在模型里面

由表1可知,“日最高地表气温”“日最低地表气温”“日平均风速”“日降水量”“日最高本站气压”、“日照时数”“日最高气温”和"日最小相对湿度"等8个变量进入了全样本数据的拟合阶段,且除了“日最高本站气压”和"日最小相对湿度"在5个中间模型特征变量选择结果中出现4次以外,其他6个变量均出现了5次。表2为8个显著变量的全样本数据拟合结果,结果显示各变量与林火发生具有显著相关性。其中“日最高地表气温”“日平均风速”“日最高本站气压”“日照时数”和“日最高气温”等5个气象因子与森林火灾呈正相关关系，“日最低地表气温”“日降水量”和“日最小相对湿度"3个气象因子与森林火灾呈负相关关系,且这8个气象因子对林火发生均有显著的影响。

http ://www.ecologica.cn

Table 2LR model parameter fitting results of final sample   

<html><body><table><tr><td>变量 Variable</td><td>系数 Coefficient</td><td>标准误差 standard error</td><td>显著性 Significant</td></tr><tr><td>日最高地表气温 The highest surface temperature</td><td>0.005084</td><td>0.000512</td><td><0.0001</td></tr><tr><td>日最低地表气温 The minimum surface temperature</td><td>-0.019823</td><td>0.000968</td><td><0.0001</td></tr><tr><td>日平均风速 Daily average wind speed</td><td>0.011462</td><td>0.001706</td><td><0.0001</td></tr><tr><td>24 小时降水量 Daily precipitation</td><td>-0.004977</td><td>0.000959</td><td><0.0001</td></tr><tr><td>日最高本站气压 The highest station pressure</td><td>0.000257</td><td>0.000068</td><td>0.000157</td></tr><tr><td>日照时数Hours of sunshine</td><td>0.012671</td><td>0.001224</td><td><0.0001</td></tr><tr><td>日最高气温 Daily maximum temperature</td><td>0.006379</td><td>0.001082</td><td><0.0001</td></tr><tr><td>日最小相对湿度 The minimum relative humidity</td><td>-0.007462</td><td>0.002545</td><td>0.003365</td></tr><tr><td>常量 Constant</td><td>-4.113521</td><td>0.701953</td><td><0.0001</td></tr></table></body></html>

# 2.1.3 GWLR模型拟合结果

首先假设模型的数据结构是空间非平稳的,对5个训练样本进行模型拟合,然后对因变量与解释变量之间的关系的空间非平稳性进行检验。如果“某解释变量的估计系数的四分位数范围大于LR模型中该解释变量的估计系数的 $\pm 1$ 标准差范围”[13.29],则认为该解释变量是显著空间非平稳变量（以样本1为例,LR 模型和GWLR模型系数估计结果见附表1)。最后在5个训练样本中选择出现3次或3次以上的非平稳变量进入全样本数据的拟合阶段,并作为全样本数据模型的非平稳项,而其他平稳变量则作为全样本数据模型的平稳项。检验结果显示除了“日最低相对湿度”在5个中间模型中有1次被检验为空间平稳变量之外,其他9个气象因子在5个中间模型中均被检验为空间非平稳变量(附表2)。全样本数据的GWLR模型参数拟合结果如表3所示。

表2全样本数据的LR模型参数拟合结果  
表3全样本数据的GWLR模型参数估计  
Table 3Final sample of GWLR model parameter estimation   

<html><body><table><tr><td>系数 Coefficient</td><td>最小值 Min</td><td>四分之一分位数 25%quartile</td><td>平均数 Mean</td><td>中位数 Median</td><td>四分之三分位数 75% quartile</td><td>最大值 Max</td></tr><tr><td>截距 Intercept</td><td>-41.9643</td><td>-13.2123</td><td>-9.5616</td><td>-6.8187</td><td>-2.1540</td><td>2.8362</td></tr><tr><td>日最高地表气温 The highest surface temperature</td><td>-0.0023</td><td>0.0029</td><td>0.0040</td><td>0.0036</td><td>0.0050</td><td>0.0103</td></tr><tr><td>日最低地表气温</td><td>-0.0340</td><td>-0.0264</td><td>-0.0232</td><td>-0.0234</td><td>-0.0200</td><td>-0.0146</td></tr><tr><td>The minimum surface temperature 日平均风速 Daily average wind speed</td><td>-0.0434</td><td>-0.0036</td><td>0.0091</td><td>0.0100</td><td>0.0235</td><td>0.0591</td></tr><tr><td>日最大风速 Daily maxium wind speed</td><td>-0.0261</td><td>-0.0106</td><td>0.0004</td><td>0.0008</td><td>0.0118</td><td>0.0274</td></tr><tr><td>24小时降水量 Daily precipitation</td><td>-0.0173</td><td>-0.0071</td><td>-0.0054</td><td>-0.0050</td><td>-0.0031</td><td>0.0009</td></tr><tr><td>日最高本站气压 The highest station pressure</td><td>-0.0003</td><td>0.0001</td><td>0.0008</td><td>0.0006</td><td>0.0010</td><td>0.0040</td></tr><tr><td>日照时数 Hours of sunshine</td><td>-0.0005</td><td>0.0081</td><td>0.0112</td><td>0.0120</td><td>0.0145</td><td>0.0214</td></tr><tr><td>日最高气温 Daily maximum temperature</td><td>-0.0014</td><td>0.0068</td><td>0.0119</td><td>0.0110</td><td>0.0159</td><td>0.0309</td></tr><tr><td>日平均相对湿度 Dailyaverage relative humidity</td><td>-0.0883</td><td>-0.0217</td><td>-0.0092</td><td>-0.0016</td><td>0.0092</td><td>0.0244</td></tr><tr><td>日最小相对湿度 The minimum relative humidity</td><td>-0.0263</td><td>-0.0095</td><td>-0.0006</td><td>-0.0021</td><td>0.0055</td><td>0.0496</td></tr></table></body></html>

注：系数的最大和最小值若符号相同表示该变量在整个研究区域上与林火的相关性一致,反之表示变量在整个区域上与林火的相关性具有正负差异

表3显示,除“日最低地表气温"在整个研究区域上均与林火发生呈负相关关系之外,其他9个气象因子在整个研究区域上均在正相关和负相关之间变化。为更好体现GWLR模型各变量系数的局部变化,本文运用ArcGIS10.2对各变量模型估计系数进行空间插值（图2)。图2表明GWLR模型的估计系数随空间位置变

![](images/99fdf59764f636b9e54d4e5e2f2854b6ce4b0ca38017c1e17e5a47187d83061a.jpg)  
http ://www.ecologica.cn

![](images/2ea45ff1d50418fde08c5f1c2828851bd25133a8c5439ad95cd9925a4b3b3ac8.jpg)  
图2（变量系数分布图  
Fig.2Variable coefficient distribution

此外,对各变量估计系数的t检验值进行空间插值,若估计系数 $\mathbf { \chi } _ { t }$ 检验值的绝对值小于1.96,则表示估计系数在研究区域上不显示，若 $\mathbf { \chi } _ { t }$ 检验值小于-1.96或大于1.96,说明估计系数显著。图3表明模型变量的估计系数的显著性也具有很强的空间异质性。

图2,图3综合显示“日最低地表气温"在整个研究区域上均与林火发生呈负相关关系,且该因子的估计系数在整个研究区域上均显著；“24小时降水量”与林火发生呈显著负相关系数；“日照时数”和“日最高气温”与林火发生呈显著正相关关系；“日最高本站气压”与林火发生存在正负两种相关性,但以正相关为主,主要分布在福建北部和南部地区；“日平均相对湿度”在南平市北部地区和龙岩市大部分地区与林火呈显著的负相关关系,仅在三明与南平市交界处存在小块正相关区域；“日最小相对湿度”在龙岩市西南地区存在显著正相关系数,在三明市和永安市交界处及厦门市和漳州市的小部分沿海地区存在显著的负相关系数；“日平均风速"在福建省西部和中部地区与林火发生呈显著正相关,而“日最大风速”在西部和中部地区与林火发生则呈显著负相关。

# 2.2模型评价

本文将全样本分成 $6 0 \%$ 的训练样本(用于建模)和 $4 0 \%$ 的测试样本（模型检验)。应用最小信息准则（AIC）、残差平方和（SSE)和ROC 曲线（ROC）下的面积AUC 值（AUC)等统计量和模型的预测准确率对 LR和GWLR 模型进行对比评价。

模型拟合统计结果表明,对比传统逻辑斯蒂回归模型,地理加权逻辑斯蒂回归模型具有更小的 AIC 和SSE 值,和更大的AUC 值以及更高的模型预测准确率（表4)。表4显示,LR 模型的预测准确率为 $7 4 . 2 \%$ 一$7 6 . 2 \%$ 小于GWLR模型 $( 7 7 . 1 \% - 7 8 . 6 \%$ 。

![](images/0b1452f4aaa370837e8e886cc1368ae769eb78c20bfb2b34e5caba7d3e908290.jpg)

![](images/03cadbeacad5921153d838bbaa531beb94489633dfc0098592dacfd684045183.jpg)  
图3变量系数显著性分布图  
Fig.3Significant distribution of variable coefficient正显著相关性用暖色调表示，负显著相关性用冷色调表示

# 表4模型拟合统计量

Table 4Model fit statistics   

<html><body><table><tr><td rowspan="2">样本ple</td><td rowspan="2">赤池信息准则</td><td rowspan="2"></td><td rowspan="2">残差平方和</td><td rowspan="2">ROC曲线</td><td colspan="3">预测正确率 Prediction accuracy/%</td></tr><tr><td>临界</td><td></td><td></td></tr><tr><td>样本1</td><td>LR</td><td>5256.368</td><td>872.679</td><td>0.822</td><td>0.501030</td><td>75.5</td><td>74.7</td></tr><tr><td>Sample 1</td><td>GWLR</td><td>4999.887</td><td>785.656</td><td>0.857</td><td>0.524587</td><td>78.6</td><td>76.8</td></tr><tr><td>? 样本2</td><td>LR</td><td>5307.347</td><td>883.882</td><td>0.822</td><td>0.501080</td><td>75.2</td><td>75.2</td></tr><tr><td>Sample 2</td><td>GWLR</td><td>5054.525</td><td>795.851</td><td>0.855</td><td>0.466608</td><td>78.5</td><td>76.9</td></tr><tr><td>样本3</td><td>LR</td><td>5304.786</td><td>883.694</td><td>0.819</td><td>0.479230</td><td>75.1</td><td>75.9</td></tr><tr><td>Sample 3</td><td>GWLR</td><td>5116.377</td><td>822.763</td><td>0.843</td><td>0.513953</td><td>77.6</td><td>77.3</td></tr><tr><td>样本4</td><td>LR</td><td>5342.380</td><td>891.813</td><td>0.815</td><td>0.503125</td><td>74.9</td><td>75.5</td></tr><tr><td>Sample 4</td><td>GWLR</td><td>5072.533</td><td>800.321</td><td>0.853</td><td>0.540291</td><td>77.8</td><td>77.1</td></tr><tr><td>样本5</td><td>LR</td><td>5401.440</td><td>905.102</td><td>0.810</td><td>0.501975</td><td>74.2</td><td>76.2</td></tr><tr><td>Sample 5</td><td>GWLR</td><td>5172.060</td><td>820.554</td><td>0.845</td><td>0.522827</td><td>77.6</td><td>79.0</td></tr><tr><td>全样本</td><td>LR</td><td>8792.525</td><td>1464.812</td><td>0.821</td><td>0.502310</td><td>75.1</td><td></td></tr><tr><td>Complete sample</td><td>GWLR</td><td>8323.496</td><td>1328.274</td><td>0.853</td><td>0.505205</td><td>78.4</td><td></td></tr></table></body></html>

# 2.3 残差分析

根据两个模型对5样本和全样本数据的拟合结果,分别绘制模型的残差图（图4)。图4表明GWLR模型

具有更小的残差。

![](images/469e9f742769a20bc8bf4871657d4a64b568353f402f1e587b9a960c6add160c.jpg)  
Fig.4Box figure the model residuals

全样本模型的残差空间自相关(图5)结果显示GWLR 模型的 Moran'sI值比LR 模型小,说明与LR 模型相比,GWLR模型在福建省林火发生与否的判别问题中考虑了更多的空间自相关问题,GWLR 模型对福建省林火发生的拟合效果较好。

# 3讨论

气候条件的变化对森林火灾的发生具有重要的影响，因此，本文基于气象因子应用传统的逻辑斯蒂回归模型和地理加权逻辑斯蒂回归模型对福建省2000—2005年的林火数据进行分析，对两种模型的预测能力以及对模型在森林火灾应用方面的适用性进行分析。模型变量选择结果显示，“日最高地表气温”、“日最低地表气温”“日平均风速”、“24小时降水量”“日最高本站气压”、“日照时数”、“日最高气温”和“日最低相对湿度"等8个变量均是LR模型和GWLR模型的全样本特征变量，说明这8个气象因子是福建省森林火灾的主要影响因子。气温的变化会使可燃物的湿度发生变化，改变火灾的气候条件，从而对森林火灾产生影响。我们的研究结果显示，“气温”对森林火灾的发生具有重要的影响,这与 $\mathrm { L i u } ^ { [ 3 2 ] }$ 和 $\mathrm { H u }$ 和 Zhou[33]的研究结果一致;相对湿度是反应林内可燃物含水量的一个重要指标,对林火发生有重要影响。我们的研究结果表明“相对湿度”对林火发生有重要的影响,与 Zhang[24]的研究结果一致。通常一个地区重特大火灾的发生,与最大风速是相关,但是,本文在对气象因子进行分析时,逻辑斯蒂回归模型却将"日最大风速"剔除,而地理加权逻辑斯蒂回归模型回归模型则显示“日最大风速”是一个空间非平稳变量,因此,模型变量的选择是否理想与模型的选择相关。此外,本研究并没有考虑地形、植被类型、人为活动等条件对森林火灾的影响,因此可能会对研究结果产生偏差。

![](images/476fd8cdb27f5a69f0791e832ca0823d7697ca955335a8351276ff886eaf6327.jpg)  
图4模型残差箱形图  
图5全样本模型的残差空间自相关  
Fig.5Final sample of residual spatial autocorrelation

传统的逻辑斯蒂回归模型假设空间变量都是平稳变量,忽略了模型变量的空间异质性,模型的拟合结果无法全面反映变量的空间关系,而本文的研究结果显示,影响福建省林火发生的气象因子具有明显的空间异质性,且模型评价结果显示与传统的逻辑斯蒂回归模型相比,地理加权逻辑斯蒂回归模型的拟合效果较好,这与 Saefuddin[31]、Koutsias[12] ${ { \mathbb { W } } _ { \mathbf { u } } }$ 和 Zhang[28]等前人的研究结果一致,表明在对具有空间结构的数据进行拟合分析时，应考虑空间地理位置变化对因变量结果的影响。

# 4结论

本文应用逻辑斯蒂回归模型和地理加权逻辑斯蒂回归模型对福建省森林火灾空间格局和气象影响因子进行分析,并对两种模型的拟合效果进行研究,结果表明：（1）“日最高地表气温”“日最低地表气温”“日平均风速”“24小时降水量”“日最高本站气压”“日照时数”“日最高气温”和“日最低相对湿度”等8个变量是3个模型的共同变量,是影响福建省林火发生的主要气象因子；(2)在福建省林火发生的分类判别中,与传统的逻辑斯蒂回归模型相比，地理加权逻辑斯蒂回归模型的拟合效果更好，更适合福建省森林火灾的数据结构。

# 参考文献（References）：

[1]GroganP，usTD，aiFSeectsoostetrognlingiCalifoanishineforest.ecolgia，o（）:537-544.  
[2]LiuHersoJ,dsaFngsinesurfaceeeudgeferfirerealosysteofteriasalperspective. Journal of Geophysical Research Atmospheres，2005,110(D13）：D13101.  
[3]Chas-AmilouzaJresteoPSpatialtributioofhman-usedforestfiresinGicia（NWpain）Ecologdteot,2010，137:247-258.  
4]sqseein Galicia using MODIS data.International Journal of Wildland Fire,2012,21(8）：1025-1029.  
[5]ParisienMA,esingerS，rgJAsonCR,hagel,boiS,MritSatialbilityilreliacross the western United States.International Journal of Wildland Fire,2012,21(4)：313-327.  
[6]Renardeisshaotaletblielfrof India.International Journal of Wildland Fire,2012,21(4）：368-379.  
[7］Lozano F J，Suárez-S ，KellyM，Luis E.A multi-scale approach for modeling fire occurrence probabilityusing satellitedata andclssificationtres；Acasestudyinamoutainous Mediteraneanregion.RemoteensingofEnvroment，008,11（3)：708-719.  
[8］郭福涛，苏漳文，马祥庆,宋禹辉，孙龙，胡海清，杨婷婷.大兴安岭塔河地区雷击火发生驱动因子综合分析.生态学报,2015,35(19)：6439- 6448.  
[9］郭福涛，胡海清，金森，马志海，张扬.基于负二项和零膨胀负二项回归模型的大兴安岭地区雷击火与气象因素的关系.植物生态学报，2010, 34(5) : 571-577.  
10]秦凯伦，郭福涛，邸雪颖，孙龙，宋禹辉，吴瑶，潘建峰.大兴安岭塔河地区林火发生的优势预测模型选择.应用生态学报，2014，25(3):731-737.  
[11] 郭福涛，胡海清，马志海，张扬.不同模型对拟合大兴安岭林火发生与气象因素关系的适用性.应用生态学报，2010,21（1)：159-164.  
[12] KoutsiasN,MartezJio，rdelindfieuciouthuoygeogacalldeoapproach//Procdingsofthe5thInteationalWorkshopoRemoteSesingandGSApplationstoForestFireManagement：FireEffectsAssessment. Spain：Universidad de Zaragoza,20o5：57-60.  
[13]MartieFJuE，KutsiaoelilicectosiSioialigeographically weighted regresson.Natural Hazards and Earth System Sciences，2013,13(2）：311-327.  
[14]Rodriges,DeLaivaJteiaSodelingtheialriatiofplaatoractosfmanaedfrsiSsinggeographically weighted logistic regression.Applied Geography，2014，48：52-63.  
[15]WangQ，JnJAplcaofgapallegeialyitiateprauctiofrtecosystems.Global Ecology and Biogeography，2005，14(4）：379-393.  
16]TuJSpatiallyrngelatiosseldudateualitycosbaaiogdteplodygallregression.Applied Geography，2011，31(1）：376-392.  
Prollopdata.International Journal of Applied Earth Observation and Geoinformation,2012,18：82-90.  
[18] FredmanR，RoySSSpatialpaterngofMantabirostrsinUnitedStatesastcoastofsorehabitat.AledGeogahy2（2)：652-659.  
[19] AguilarGD，FaorthtratsinuclndZealaddisoveingapcfoatiofoploatoyspatialasGeography，2012，34：230-238.  
[20] 国家林业局.第八次全国森林资源清查结果.林业资源管理，2014，（1)：1-2.  
[21] 李兆明，高兆蔚.福建森林火险天气等级预测预报方法.福建林学院学报，1989，9（2)：172-176.  
[22] 朱学平，何东进，丁福立，洪伟，游巍斌，纪志荣.基于突变级数法的福建省森林火灾评价分析.福建林学院学报，2011，31（4)：295-299.  
[23] GarciaCV,WoodardPitusSAdamowczWL,LeeBS.Algitodelrpredictingthedailcueneofumacausedffre.International Journal of Wildland Fire，1995,5(2)：101-111.  
24]ZangZXaHZoUsingalsdlteirictilhdJournal of Arid Environments，2010,74(3）：386-393.  
25]delHabeeggistcesoefoadiiistatalthtialaccuracy in fire occurrence data.European Journal of Forest Research，2O11，130（6) 983-996.  
[26] 郭含茹，张茂震，徐丽华，袁振花，陈田阁.基于地理加权回归的区域森林碳储量估计.浙江农林大学学报，2015，32（4)：497-508.  
[27] 肖燕婷，田铮，魏岳嵩.时空地理加权回归模型的时空非平稳性检验.系统工程理论与实践，2013，33(6)：1537-1542.  
[28] WuW,ZagfsialelsiRico.Applied Geography，2013,37：52-62.  
29ZangHoprovtgodelieallsteleaalJFire，2014,23(8)：1130-1146.  
[30]odrigvaJAsitoaritodeaadialelSoftware，2014，57：192-201.  
[31] Saefuddin A， Setiabudi N A，Fitrianto $\mathrm { \bf A }$ .On comparison between logistic regression and geographically weighted logistic regression：withapplication to Indonesian poverty data.World Applied Sciences Journal,2012，19(2）:205-210.  
[32]LiuZHgJagWesHeHatialedesoffreoeditsfuerdelateboreal forest of Northeast China.Global Change Biology，2012，18(6)：2041-2056.  
[33]HuTYouGDesfggadaausedfieesineGating'anoarestologdaag,329:49-58.

# 附表：

<html><body><table><tr><td colspan="10">Annexed table 1 LRmodel and GWLR model coefficient estimation（sample1)</td></tr><tr><td>模型统计量</td><td></td><td>截距项</td><td>最气地</td><td>最气</td><td></td><td>日最达</td><td>2小时</td><td>最气本</td><td>日照时数</td><td>日最高气温</td><td>相搜度</td><td>最小度</td></tr><tr><td>Model Statistics</td><td></td><td>Intercept</td><td>GST_max</td><td>GST_min</td><td>Wnd_avg</td><td>Wnd_max</td><td>Pre</td><td>Pres_max</td><td>SSD</td><td>Temp_max</td><td>RH_avg</td><td>RH_min</td></tr><tr><td>LR</td><td>估计系数</td><td>-3.979183</td><td>0.004932</td><td>-0.020798</td><td>0.011638</td><td>-0.000071</td><td>-0.004711</td><td>0.000243</td><td>0.012919</td><td>0.007426</td><td>-0.003009</td><td>-0.003736</td></tr><tr><td></td><td>标准误差</td><td>1.064268</td><td>0.000661</td><td>0.001352</td><td>0.004287</td><td>0.002749</td><td>0.001232</td><td>0.000096</td><td>0.001591</td><td>0.001519</td><td>0.005586</td><td>0.005317</td></tr><tr><td></td><td>估计系数-标准误差</td><td>-5.043451</td><td>0.004271</td><td>-0.02215</td><td>0.007351</td><td>-0.00282</td><td>-0.005943</td><td>0.000147</td><td>0.011328</td><td>0.005907</td><td>-0.008595</td><td>-0.009053</td></tr><tr><td></td><td>估计系数+标准误差</td><td>-2.914915</td><td>0.005593</td><td>-0.019446</td><td>0.015925</td><td>0.002678</td><td>-0.003479</td><td>0.000339</td><td>0.014510</td><td>0.008945</td><td>0.002577</td><td>0.001581</td></tr><tr><td>GWLR最小值</td><td></td><td>-54.198396</td><td>-0.002282</td><td>-0.033631</td><td>-0.065206</td><td>-0.022832</td><td>-0.017348</td><td>-0.000429</td><td>-0.001035</td><td>-0.00064</td><td>-0.070422</td><td>-0.037178</td></tr><tr><td></td><td>四分之一分位数</td><td>-11.951030</td><td>0.002654</td><td>-0.026593</td><td>-0.000398</td><td>-0.008862</td><td>-0.006708</td><td>0.000091</td><td>0.008001</td><td>0.006217-0.018073</td><td></td><td>-0.013137</td></tr><tr><td>平均数</td><td></td><td>-9.182290</td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.011935</td><td>0.011610</td><td>-0.003814</td><td>-0.004102</td></tr><tr><td>中位数</td><td></td><td>-6.484965</td><td>0.003929</td><td>-0.023161</td><td>0.008436</td><td>0.001044</td><td>-0.005226 -0.004936</td><td>0.000746</td><td>0.013266</td><td>0.010479</td><td></td><td></td></tr><tr><td>四分之三分位数</td><td></td><td></td><td>0.003700</td><td>-0.023076 -0.019046</td><td>0.012048</td><td>0.001753</td><td></td><td>0.000527</td><td>0.015655</td><td>0.015613</td><td>0.003381</td><td>-0.005216</td></tr><tr><td>最大值</td><td></td><td>-2.419304</td><td>0.004719</td><td></td><td>0.024120</td><td>0.010857</td><td>-0.003099</td><td>0.000921 0.005137</td><td>0.022256</td><td>0.031157</td><td>0.013657</td><td>0.003580</td></tr><tr><td></td><td></td><td>3.108987</td><td>0.010752</td><td>-0.015394</td><td>0.061361</td><td>0.027887</td><td>0.000520</td><td></td><td></td><td></td><td>0.029408</td><td>0.037951</td></tr><tr><td></td><td>四分位数范围</td><td>9.531726</td><td>0.002065</td><td>0.007547</td><td>0.024518</td><td>0.019719</td><td>0.003609</td><td>0.00083</td><td>0.007654</td><td>0.009396</td><td>0.03173</td><td>0.016717</td></tr></table></body></html>

附表1 LR模型和GWLR模型的系数估计(样本1)   
附表2GWLR模型空间(非)平稳变量检验结果   
Annexed table 2GWLR model of space（nor）smooth variable inspection resu   

<html><body><table><tr><td>变量 Variable</td><td>样本1 样本2 Sample 1 Sample 2</td><td>样本3 Sample 3</td><td>样本4 Sample 4</td><td>样本5 Sample 5</td><td>最终样本 Final sample</td><td>样本显著个数 No.samples signif</td></tr><tr><td>日最高地表气温 The highest surface temperature</td><td></td><td>+</td><td>+</td><td>+</td><td>+</td><td>5</td></tr><tr><td>日最低地表气温 The minimum surface temperature</td><td></td><td></td><td>+</td><td>+</td><td>+</td><td>5</td></tr><tr><td>日平均风速 Daily average wind speed</td><td></td><td>+</td><td>+</td><td>+</td><td>+</td><td>5</td></tr><tr><td>Day大xiu wind sped</td><td></td><td>+</td><td>+</td><td>+</td><td>+</td><td>5</td></tr><tr><td>24小时降水量 Daily precipitation</td><td></td><td>+</td><td></td><td>+</td><td>+</td><td>5</td></tr><tr><td>日最高本站气压 The highest station pressure</td><td>+</td><td></td><td></td><td></td><td>+</td><td>5</td></tr><tr><td>日照时数 Hours of sunshine</td><td>+</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>日最高气温 Daily maximum temperature</td><td>+</td><td></td><td></td><td></td><td>+</td><td></td></tr><tr><td>日平均相对湿度 Daily average relative humidity</td><td>+</td><td></td><td></td><td></td><td>+</td><td>5</td></tr><tr><td>日最小相对湿度 The minimum relative humidity</td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

-表示该变量是空间非平稳变量；-表示该变量是空间平稳变量