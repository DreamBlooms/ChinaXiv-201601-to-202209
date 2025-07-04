# 基于蒙特卡罗仿真的湖库水质预测及富营养化风险评估方法

王小艺，周宇琴，赵峙尧，王立，许继平，于家斌(北京工商大学 计算机与信息工程学院，北京 100048)

摘要：湖库水质预测及富营养化分析是水污染防控的重要技术手段。然而，已有的水质预测研究通常是单值预测，并以此为依据分析富营养化状态，具有一定的偶然性和不确定性。结合水质动力学模型，提出了一种基于蒙特卡罗仿真的湖库水质预测及富营养化风险评估方法。在已知水质动力学模型水质指标和模型参数的先验分布基础上，利用蒙特卡罗仿真预测水质指标的演化过程，获得未来时刻水质指标取值的概率分布，实现水质预测。进一步，构造综合营养状态指数，结合水质指标预测结果，计算综合营养状态指数的概率分布和处于不同营养程度的概率，实现富营养化风险评估。仿真结果表明，该方法能够有效实现水质预测和富营养化分析，且考虑更加全面、准确，克服了单值预测结果带来的偶然性。

关键词：水质动力学模型；蒙特卡罗仿真；水质预测；富营养化；风险评估 中图分类号：TP391.9 doi:10.19734/j.issn.1001-3695.2018.08.0655

# Monte-carlo simulation based water quality prediction and eutrophication risk assessment method oflakes

Wang Xiaoyi, Zhou Yuqin,Zhao Zhiyao,WangLi,Xu Jiping,Yu Jiabin (SchoolofComputer&InformationEngineering,BeijingTechnology&BusinessUniversityeijingl48,China)

Abstract: Waterquality prediction and eutrophication analysis of lakes are importanttechnical meansof water pollution prevention and control.However,theexisting waterquality prediction research is usualy inaform of single-valued prediction,and analyze eutrophication status onthis basis，which hasacertain degree of haphazardanduncertainty. Combining with the waterqualitykinetic model,proposed a water quality prediction and eutrophicationriskasessment method based on Monte-Carlo simulation.Basedon the prior distribution of waterqualityindex and model parameters of waterquality kinetic model,used MonteCarlosimulation to predicttheevolutionof waterqualityindex toobtain the probabilitydistributionof waterquality indicators in future timeandachieve waterqualityprediction.Further,constructed an integrated eutrophication status index.Combining with thepredicted resultsof waterquality indexes,calculated the probabilitydistributionofcomprehensive nutritionalstatus indexandthe probabilityofdiferentnutritional statustoasess the eutrophication risk.The simulation results show that the proposed methodcan effectively predictthe waterqualityand analyzeeutrophicationstatus，with morecomprehensiveconsideration and accuracy.Meanwhile,it overcomes the haphazard brought by single-valued prediction result.

Key words: water quality kinetic model, monte Carlo simulation, water quality prediction,eutrophication,riskasessment

# 0 引言

随着现代社会的飞速发展，水体富营养化已成为一个全球性的重大水环境问题。目前，在世界范围内，受富营养化影响的沿海地区有500多个。此外，许多世界淡水湖泊、溪流和水库正在遭受富营养化。相关研究表明，我国当前已有$8 0 \%$ 的湖泊出现富营养化现象。在我国除一些人烟稀少的淡水湖区域以及还保持着原始状态的湖泊之外，其他湖泊营养盐水平的浓度已经超过了湖泊富营养化的标准浓度。尤其是我国的几大淡水湖的营养盐浓度都已经超过了磷、氮富营养化的发生浓度，总氮浓度甚至超过10倍之上。当下，我国的太湖以及巢湖都已经完全变为富营养化状态[I-4]。因此，水环境问题已迫不容缓。水质预测能有效的掌握水质情况，预防大规模水污染事件的发生，对水污染防治具有现实意义。所以实现合理有效的水质预测，并在此基础上评估富营养化风险是解决水环境问题的重要思路。

已有的水质预测方法主要分为两类：

a)基于机理的水质预测方法。这类方法主要是通过分析水体内部的机理演化过程来建立水质模型，再基于该水质模型对水质指标进行预测。常用的机理模型包括：QUAL2E、WASP和EFDC等。QUAL2E是一个一维水质模型，适用于模拟完全混合的枝状河流水质；它假定存在主流输送机理，即假定平流与扩散混合都是沿着河流的主流向，而在河流的横向与垂向上水质组分是完全均匀混合的，允许河流沿程有多个污染源、取水口以及支流汇入；其基本方程是一维平流—扩散质量迁移方程[5\~8]。WASP(waterquality analysissimulationprogram)是美国环保局 (EPA)开发并推荐使用的用于各类水体水质模拟与分析的软件；它可用于模拟水动力学、河流一维不稳定流、湖泊和河口三维不稳定流、常规污染物和有毒污染物在水中的迁移和转换规律；其基本原理是平移—扩散方程[9-13]。EFDC(environmental fluid dynamicscode)模型是涵盖一维到三维地表水水质的数学模型；它可实现河流、湖泊、水库、湿地系统、河口和海洋等水体的水动力学、水质模拟、污染物迁移和泥沙输移等，是一个多参数有限差分模型[14-16]。

b)数据驱动的水质预测方法。这类方法利用数据分析模型和工具对水质指标的实测数据进行建模，再通过此模型对水质指标进行预测。常用的数据驱动模型包括：人工神经网络、时间序列模型和支持向量机等，该类模型均是利用不同时刻的水质指标观测数据建立表征水质演化过程的数据驱动模型，并在此基础上实现水质过程预测[17-25]。两类方法各具有一定优势，然而已有方法大都得到的是水质指标的取值变化预测（单值预测)，其结果通常具有一定的偶然性，精确度和可信度难以令人信服，在此基础上的富营养化评价也会存在偶然性和不确定性。

本文为了弥补单值预测方法带来的不足，提出了一种基于蒙特卡罗仿真的水质预测及富营养化风险评估方法。蒙特卡罗仿真是指利用大量重复随机实验来获取问题数值解的一种仿真。本文基于湖库水质指标演化机理，利用非线性连续微分方程建立湖库水质动力学模型，进而给定水质指标和模型参数初值，利用蒙特卡罗方法对水质指标演化过程进行预测，获得未来时刻水质指标取值的概率分布，实现水质预测。进一步，结合水质指标预测结果，利用综合营养状态指数法进行评估，获得综合营养状态指数的概率分布和处于不同营养程度的概率，实现富营养化风险评估。

# 1水质指标演化机理及动力学模型

![](images/8bc90c030e9880d2739e14f264ffef2f76e8a6993d1048b99b90ba7995802cb4.jpg)  
Fig.1Water ecosystem evolution process   
图1水体生态系统演化过程

水体生态系统主要包含以下四个演化过程：溶解氧平衡过程、浮游植物动力学过程、磷循环和氮循环，可由八个水质指标描述：溶解氧 (DO)、浮游植物 (Phyt)、碳生化需氧量(BOD)、有机磷(OP)、正磷酸盐 $\mathrm { ( P O _ { 4 } ) }$ 、有机氮（ON)、氨氮 $( \mathrm { N H } _ { 3 } – \mathrm { N } )$ 和硝酸盐氮 $( \mathrm { N O } _ { 3 } – \mathrm { N } ) ^ { [ 2 6 ^ { , } ~ 2 7 ] }$ 。溶解氧平衡过程通过DO和BOD含量变化体现，过程包括复氧，碳质氧化，硝化，反硝化，沉积，植物生长，Phyt死亡，Phyt呼吸和沉积物需氧量。浮游植物动力学过程的主要研究对象是水体中浮游植物的含量（浮游植物是一个生态学概念，是指在水中营浮游生活的微小植物。通常浮游植物就是指浮游藻类)，通过Phyt含量变化体现，过程包含三个部分：浮游植物的生长、死亡和沉降。磷循环是磷的三种物质形态相互转换的过程，通过OP和 $\mathrm { P O } _ { 4 }$ 含量变化体现，过程包含四个部分：无机磷（正磷酸盐）转换为浮游植物磷，浮游植物磷转换为无机磷和有机磷，矿化作用，以及沉降吸附作用。氮循环是氮的四种物质形态相互转换的过程，通过ON、NH-N和 $\mathsf { N O } _ { 3 }$ -N含量变化体现，过程包含：无机氮转换为浮游植物氮，浮游植物氮转换为无机氮和有机氮，矿化作用，硝化和反硝化作用，以及沉降作用。水体生态系统演化过程[28-30]如图1所示。

基于上述水质指标演化机理，水质动力学模型如式(1)所示。

$$
\begin{array} { r l } & { \dot { C } _ { \mathrm { c o s } } = k _ { 1 } ( C _ { \mathrm { S G } , n } - C _ { \mathrm { c o s } } ) - 1 . 0 4 7 k _ { 2 } \frac { C _ { \mathrm { c o s } } } { 0 . 5 + C _ { \mathrm { c o s } } } \zeta _ { \mathrm { c o s } } } \\ & { \qquad \quad - 4 . 9 7 1 k _ { 2 } \frac { C _ { \mathrm { c o s } } } { 2 } \zeta _ { \mathrm { c o s } } \zeta _ { \mathrm { c o s } } - 0 . 0 5 5 4 k _ { 4 } } \\ & { \qquad \quad + 1 6 6 6 6 7 4 + 4 k _ { 1 } \zeta _ { \mathrm { c o s } } - 0 . 3 3 3 k _ { 4 } Z _ { \mathrm { c o s } } } \\ & { \dot { C } _ { \mathrm { c o s } } - [ 5 . - k _ { 3 } - 6 . 1 3 1 \zeta _ { \mathrm { c o s } } ] } \\ & { \qquad \quad + 1 . 0 4 7 k _ { 2 } \frac { C _ { \mathrm { c o s } } } { 2 } + 0 . 0 2 5 k _ { 4 } \frac { \left( 9 . 2 8 \right) } { \left( 1 . 2 5 \right) ^ { 2 } \zeta _ { \mathrm { c o s } } } } \\ & { \qquad \quad + 2 6 6 6 7 k _ { 2 } C _ { \mathrm { c o s } } - 3 . 1 8 5 7 k _ { 4 } \frac { \left( 9 . 1 \right) } { \left( 1 . 2 5 \right) ^ { 2 } \zeta _ { \mathrm { c o s } } } \zeta _ { \mathrm { c o s } } - k } \\ & { \qquad \quad \dot { C } _ { \mathrm { c o s } } = 0 . 0 1 2 5 ( 1 . 2 5 + k _ { 4 } ) C _ { \mathrm { c o s } } - 0 . 2 3 7 k _ { 4 } \frac { \left( \mathrm { c o s } \right) } { \left( 1 . 2 5 \right) ^ { 2 } \zeta _ { \mathrm { c o s } } } + \frac { k } { 2 } ( 1 - k _ { 1 } ) \zeta _ { \mathrm { c o s } } } \\ & { \qquad \quad \dot { C } _ { \mathrm { c o s } } - [ 0 . 0 1 2 5 ( 0 . 1 2 5 + k _ { 3 } ) - 0 . 0 2 5 k _ { 3 } \zeta _ { \mathrm { c o s } } + 0 . 2 3 7 k _ { 4 } \frac { \left( \mathrm { c o s } \right) } { \left( 1 . 2 5 \right) ^ { 2 } \zeta _ { \mathrm { c o s } } } \zeta _ { \mathrm { c o s } } } \\ & { \qquad \quad \dot { C } _ { \mathrm { c o s } } - [ 0 . 0 1 2 5 ( 0 . 1 2 5 + k _ { 3 } ) - 0 . 0 2 5 k _ { 4 } \zeta _ { \mathrm { c o s } } ] \xi _ { \mathrm { c o s } } \left( - \mathrm { c o s } \right) } \end{array}
$$

其中： $\{ C _ { D O } , C _ { P h y t } , C _ { B O D } , C _ { O P } , C _ { P O _ { 4 } } , C _ { O N } , C _ { N H _ { 3 } - N } , C _ { N O _ { 3 } - N } \}$ 分别表示水质指标 DO、Phyt、BOD、OP、 $\mathrm { P O } _ { 4 }$ 、ON、 $\mathrm { N H } _ { 3 ^ { - } } \mathrm { N }$ 和 $\mathsf { N O } _ { 3 }$ -N的浓度。Phyt的浓度以叶绿素 $\mathbf { \Delta } _ { a }$ (Chl_a)的浓度为准，参数$\{ k _ { 1 } , k _ { 2 } , \cdots , k _ { 1 3 } \}$ 为模型参数，其含义和单位如表1所示。

令 $\mathbf { \boldsymbol { x } } = ( C _ { D O } , C _ { P h y t } , C _ { B O D } , C _ { O P } , C _ { P O _ { 4 } } , C _ { O N } , C _ { N H _ { 3 } - N } , C _ { N O _ { 3 } - N } ) ^ { \mathrm { T } }$ $\pmb { \theta } = ( k _ { 1 } , k _ { 2 } , k _ { 3 } , k _ { 4 } , k _ { 5 } , k _ { 6 } , k _ { 7 } , k _ { 8 } , k _ { 9 } , k _ { 1 0 } , k _ { 1 1 } , k _ { 1 2 } , k _ { 1 3 } ) ^ { \mathrm { T } }$ ，且假设模型参数是慢变的，则式(1)可表示为

$$
\scriptstyle { \left[ \begin{array} { l } { { \dot { \boldsymbol { x } } } } \\ { { \dot { \boldsymbol { \theta } } } } \end{array} \right] } = { \left[ \begin{array} { l } { f ( \boldsymbol { x } , \boldsymbol { \theta } ) } \\ { \begin{array} { r } { \mathbf { 0 } } \end{array} } \end{array} \right] }
$$

其中， $f ( x , \theta )$ 是水质动力学模型函数。

需要注意的是，不同的湖泊、河口等水体内部环境有差别，水体特征也不一样，故不同水体的模型参数也不一样。为使水质模型更为精确、合理，针对不同水体环境时，模型参数 $\theta$ 的取值应结合实测数据（水质指标的实测数据）和相关参数率定方法[31-34]确定。

# 2 基于蒙特卡罗仿真的水质预测及富营养化风险 评估

# 2.1蒙特卡罗仿真

蒙特卡罗仿真 (MonteCarlosimulation)是指利用大量重复随机实验来获取问题数值解的一种仿真方法。基本原理是当问题或对象本身具有概率特征时，可以用计算机模拟的方法产生抽样结果，根据抽样计算统计量或者参数的值；随着模拟次数的增多，可以通过对各次统计量或参数的估计值求平均的方法得到稳定结论。该方法基于大数定律（事件 $A$ 发生的概率可以近似为在大量实验中事件 $A$ 发生的频率)，通常用于解决优化、积分、随机概率分布等数学问题中解析解无法精确给出的情景[3-40]。蒙特卡罗仿真方法的步骤如表 2所示。

表1水质动力学模型参数  
Table1Water quality mechanism model's parameters   
表2蒙特卡罗仿真方法的步骤  
Table 2Steps of the Monte Carlo simulation method   

<html><body><table><tr><td>符号</td><td>含义</td><td>单位</td></tr><tr><td>k</td><td>20℃复氧速率</td><td>day-1</td></tr><tr><td>k</td><td>20℃还原速率</td><td>day-1</td></tr><tr><td>k</td><td>20℃硝化速率</td><td>day-1</td></tr><tr><td>k4</td><td>底泥需氧量</td><td>g/(m²·day)</td></tr><tr><td>k5</td><td>浮游植物生长速率</td><td>day-1</td></tr><tr><td>k6</td><td>浮游植物死亡速率</td><td>day-1</td></tr><tr><td>k</td><td>20℃反硝化速率</td><td>day-1</td></tr><tr><td>kg</td><td>有机物沉降速率</td><td>mlday</td></tr><tr><td>kg</td><td>溶解有机氮矿化速率</td><td>day-1</td></tr><tr><td>k10</td><td>有机磷溶解比例</td><td>None</td></tr><tr><td>k11</td><td>有机氮溶解比例</td><td>None</td></tr><tr><td>k12</td><td>浮游植物呼吸温度系数</td><td>None</td></tr><tr><td>k13</td><td>氨优先选择系数</td><td>None</td></tr></table></body></html>

步骤 内容构造随机模型1 1）根据问题和实测数据构造随机模型；2)问题的解对应该模型中随机变量的某些特征。产生随机数21）根据模型中各个随机变量的分布产生随机数。随机抽样3 1）根据随机变量的分布特性，设计和选取合适的抽样方法;2)对每个随机变量进行随机抽样。仿真实验41）按照所建立模型进行仿真实验、计算，求出问题的随机解。统计分析5 1）统计分析模拟实验结果，给出问题的概率解以及解的精度估计。

# 2.2基于蒙特卡罗仿真的水质指标演化预测

考虑到蒙特卡罗仿真的优势，本文基于蒙特卡罗仿真对水质指标演化进行预测。

首先，式(2)可写成离散化形式如下：

$$
\begin{array} { r } { \pmb { x } _ { k } = \pmb { x } _ { k - 1 } + \boldsymbol { h } \times \pmb { f } ( \pmb { x } _ { k - 1 } , \pmb { \theta } _ { k - 1 } ) + \boldsymbol { \omega } _ { \pmb { x } , k - 1 } } \\ { \pmb { \theta } _ { k } = \pmb { \theta } _ { k - 1 } + \boldsymbol { h } \times \pmb { f } ( \pmb { x } _ { k - 1 } , \pmb { \theta } _ { k - 1 } ) + \boldsymbol { \omega } _ { \pmb { \theta } , k - 1 } } \end{array}
$$

其中： $\pmb { x } \in \mathbb { R } ^ { 8 \times 1 }$ $\pmb \theta \in \mathbb { R } ^ { 1 3 \times 1 }$ $\pmb { f } : \mathbb { R } ^ { 8 \times 1 } \times \mathbb { R } ^ { 1 3 \times 1 }  \mathbb { R } ^ { 8 \times 1 }$ ；水质指标的过程噪声 $\omega _ { x } \sim \mathcal { N } ( \boldsymbol { O } , \boldsymbol { \Sigma } _ { x } )$ ，模型参数过程噪声 $\omega _ { \theta } \sim \mathcal { N } ( \theta , \Sigma _ { \theta } )$ ，其中 $\textstyle { \sum _ { x } }$ 、 $\Sigma _ { \theta }$ 为相应的噪声协方差阵； $h ( h \leq 1 d a y )$ 是预测步长。

在基于蒙特卡罗仿真的预测过程中，水质指标演化过程会被多次模拟。对每一次模拟，每一个水质指标在每一个预测时间点的数值均不相同，这些数值同时具有规律性和随机性。规律性体现在预测值是基于确定的水质动力学模型、水质指标和模型参数初值而产生的；随机性体现在每一个水质指标在每一个预测时间点受噪声影响而得到的预测值不尽相同。当模拟次数充分大时，结合概率统计规律，可以获得各水质指标在不同时间点上取值的概率分布。具体流程步骤为：

a)令水质指标的初值为 $\pmb { x } _ { 0 }$ ，模型参数的初值为 $\pmb { \theta } _ { 0 }$ ，蒙特 卡罗仿真粒子数为 $\mathbf { \Omega } _ { N }$ ，预测天数为 $T$ ，预测步长为 $h$ $( h \leq 1 d a y )$ ，初始时刻 $k = 0$ 。

b)根据水质指标和模型参数的初值 $( x _ { 0 } , \pmb { \theta } _ { 0 } )$ ，对 $N$ 个粒子赋初值，即 $\forall i \in [ 1 , N ]$ ，令

$$
\pmb { x } _ { 0 } ^ { ( i ) } = \pmb { x } _ { 0 } , \pmb { \theta } _ { 0 } ^ { ( i ) } = \pmb { \theta } _ { 0 }
$$

c)对于时刻 $k = h , 2 h , \cdots , T$ ,基于 $k { - } 1$ 时刻的水质指标和模型参数值 $\{ \pmb { x } _ { k - 1 } ^ { \quad ( i ) } , \pmb { \theta } _ { k - 1 } ^ { \quad ( i ) } \}$ ，利用式(3)进行单步预测，得到 $k$ 时刻的水质指标和模型参数预测值 $\{ \pmb { x } _ { k } ^ { ( i ) } , \pmb { \theta } _ { k } ^ { ( i ) } \}$ 。

d)若 $k < T$ ， $k \gets k + h$ ，转至c)，否则转至e)。

e)对 $\forall k \in [ h , T ]$ ，计算水质指标和模型参数的概率密度函数；

$$
\begin{array} { l } { \displaystyle P ( \pmb { x } _ { k } | ( \pmb { x } _ { 0 } , \pmb { \theta } _ { 0 } ) ) \approx \sum _ { i = 1 } ^ { N } ( 1 / N ) \delta ( \pmb { x } _ { k } - \pmb { x } _ { k } ^ { ( i ) } ) } \\ { \displaystyle P ( \pmb { \theta } _ { k } | ( \pmb { x } _ { 0 } , \pmb { \theta } _ { 0 } ) ) \approx \sum _ { i = 1 } ^ { N } ( 1 / N ) \delta ( \pmb { \theta } _ { k } - \pmb { \theta } _ { k } ^ { ( i ) } ) } \end{array}
$$

其中： $P ( \pmb { x } _ { k } | ( \pmb { x } _ { 0 } , \pmb { \theta } _ { 0 } ) )$ 为基于 $( x _ { 0 } , \pmb { \theta } _ { 0 } )$ 的水质指标概率密度函数，$P ( \pmb \theta _ { k } | ( \pmb x _ { 0 } , \pmb \theta _ { 0 } ) )$ 为基于 $( x _ { 0 } , \theta _ { 0 } )$ 的模型参数概率密度函数， $\delta$ 为狄拉克函数。

# 2.3富营养化风险评估

本节的富营养化风险评估方法，基于上述水质指标演化结果，构造综合营养状态指数 $T L I ( \Sigma )$ ，计算 $T L I ( \Sigma )$ 的概率分布，通过对 $T L I ( \Sigma )$ 的分级处理计算处于不同营养程度的概率。

选取Chl_a（即本文的Phyt）、总磷(TP)和总氮(TN)三个水质指标，计算三个水质指标的营养状态指数，通过权值归一化得出 $T L I ( \Sigma )$ ；对 $\pi I ( \Sigma )$ 做分级处理，并计算得出 $T L I ( \Sigma )$ 的概率分布和处于不同营养程度的概率[41-43]。具体流程步骤为：

a)对于时刻 $k = h , 2 h , \cdots , T$ ，粒子 $\mathbf { \boldsymbol { x } } ^ { ( i ) }$ ， $i \in [ 1 , N ]$ ：(a)对于 $\mathrm { C h l \_ a }$ ， $C _ { P h y t , k } \in \pmb { x } _ { k } { } ^ { ( i ) }$ ，有$T L I _ { k } ( C h l \_ a ) { = } 1 0 ( 2 . 5 0 0 { + } 1 . 0 8 6 \ln ( C _ { P h y t , k } ) )$ （204号对于TP， $C _ { o P , k }$ ， $C _ { P O _ { 4 } , k } \in \pmb { x } _ { k } { } ^ { ( i ) }$ ，有

$$
T L I _ { k } ( T P ) { = } 1 0 [ 9 . 4 3 6 { + } 1 . 6 2 4 ] \mathrm { l n } ( C _ { O P , k } + C _ { P O _ { 4 } , k } ) ]
$$

对于TN， $C _ { o N , k ^ { \star } } \ : \ : C _ { N H _ { 3 } - N , k } \setminus \ : C _ { N O _ { 3 } - N , k } \in { \pmb x } _ { k } ^ { \phantom { \dagger } ( i ) }$ ，有

$$
\begin{array} { c } { { T L I _ { k } ( T N ) { = } 1 0 [ 5 . 4 5 3 + 1 . 6 9 4 ] \mathrm { n } ( C _ { O N , k } } } \\ { { + C _ { N H _ { 3 } - N , k } + C _ { N O _ { 3 } - N , k } ) ] } } \end{array}
$$

(b)以Chl_a为基准参数，则Chl_a、TP、TN的权重分别为

$$
w _ { j } = { r _ { 1 j } } ^ { 2 } / { \sum _ { j = 1 } ^ { 3 } } { r _ { 1 j } } ^ { 2 }
$$

其中， $w _ { 1 }$ 、 $r _ { 1 1 }$ 分别是Chl_a的权重和与自身的相关系数， $w _ { 2 }$ 、$r _ { 1 2 }$ 分别是TP 的权重和与基准参数 $\mathrm { C h l \_ a }$ 的相关系数， $w _ { 3 } \ 、 r _ { 1 3 }$ 分别是TN的权重与基准参数 $\mathrm { C h l \_ a }$ 的相关系数。

结合各水质指标的营养状态指数和权重，计算 $T L I ( \Sigma )$ ：

$$
\begin{array} { r } { { T L I } _ { k } ( \Sigma ) = w _ { 1 } \cdot { T L I } _ { k } ( { C h l } \_ a ) + \qquad } \\ { w _ { 2 } \cdot { T L I } _ { k } ( { T P } ) + w _ { 3 } \cdot { T L I } _ { k } ( { T I } } \end{array}
$$

b)对 $\pi I ( \Sigma )$ 做分级处理。 $T L I ( \Sigma )$ 的值越大营养程度越重，以 $0 - 1 0 0$ 分级， $T L I ( \Sigma ) < 3 0$ 为贫营养(oligotrophic),$3 0 < T L I ( \Sigma ) < 5 0$ 为中营养(mesotrophic)， $T L I ( \Sigma ) > 5 0$ 为富营养(eutrophic)。

c)计算 $\pi I ( \Sigma )$ 的概率密度函数：

$$
P ( T L I _ { k } ( \Sigma ) ) \approx \sum _ { i = 1 } ^ { N } [ ( 1 / N ) \delta ( T L I _ { k } ( \Sigma ) - T L I _ { k } ( \Sigma ) ^ { ( i ) } ) ]
$$

d)根据综合营养状态指数 $T L I ( \Sigma )$ 的概率分布计算处于不同营养程度的概率 $p _ { E _ { m } } ( T L I ( \Sigma ) )$ 0

$$
p _ { E _ { m } } ( T L I _ { k } ( \Sigma ) ) = \frac { B [ E _ { m } , \ E _ { m + 1 } ] } { N }
$$

其中： $p _ { E _ { m } } ( T L I ( \Sigma ) )$ 为时刻 $k$ 预测结果的 $T L I _ { k } ( \Sigma )$ 属于区间$[ E _ { m } , E _ { m + 1 } ]$ 的概率， $B [ E _ { m } , \ \boldsymbol { E } _ { m + 1 } ]$ 为 $T L I _ { k } ( \Sigma )$ 属于区间 $[ E _ { m } , E _ { m + 1 } ]$ 的个数，区间 $[ E _ { m } , E _ { m + 1 } ]$ 为 $T L I ( \Sigma )$ 的分级区间。

# 3 案例验证

给定水质指标和模型参数初值，基于MATLAB验证水质预测及富营养化风险评估方法的有效性。

# 3.1仿真配置

本文仿真配置的水质指标初值

x=[6.5,0.05019,3,0.07,0.06,0.35,0.36.0.1JT，水质指标过程噪声协方   
差阵 $\Sigma _ { x } = d i a g \{ 0 . 1 , 0 . 0 0 1 , 0 . 0 1 , 0 . 0 0 1 , 0 . 0 0 1 , 0 . 0 1 , 0 . 0 1 , 0 . 0 1 , 0 . 0 1 \}$ ，模型参数初 0=[1.208,0.01,0.01,0.15,0.13,0.0009,0.001，   
值 ，模型参数过程噪声协 0.025,0.075,0.9,0.35,1.02,1.3] ∑= diag{0.1,0.01,0.001,0.1,0.001,0.001,0.0001,   
方差阵 。中国湖泊(水 0.0001,0.0001,0.01,0.001,0.01,0.1}   
库)的基准参数Chl_a与其他参数之间的相关系数 $r _ { 1 j }$ 如下表3   
所示。预测步长 $h = 1 / 2 4 ($ 单位：day）、粒子数 $N = 1 0 0 0$ 和仿真时   
长 $T = 1 0 0 ( \$ 单位：day）。

表3Chl_a与TP、TN的相关关系  
Table 3Correlation coefficients between Chl_aand TP,TN   

<html><body><table><tr><td></td><td>Chl_a</td><td>TP</td><td>TN</td></tr><tr><td></td><td>1</td><td>0.84</td><td>0.82</td></tr><tr><td></td><td>1</td><td>0.7056</td><td>0.6724</td></tr><tr><td>Wj</td><td>0.4205</td><td>0.2967</td><td>0.2828</td></tr></table></body></html>

# 3.2 结果与分析

基于上一小节的仿真配置，利用3.2节中给出的水质指标演化预测算法，可得出 $N$ 个粒子的演化曲线，如图2所示，其中 $\mathrm { \Delta } \mathrm { X }$ 轴表示预测时间（预测天数100天，一天取24小时，则预测时间为2400小时)，Y轴表示水质指标的取值范围。为进一步清晰地表示结果，粒子形成的概率分布的概率密度函数如图3所示，其中X轴为预测时间（为使结果更清晰，选取预测天数100天中每隔10天的同一时刻为预测时间)，Y 轴为水质指标的取值范围，Z轴为水质指标的概率密度函数。

![](images/99e0a10b81482ac20d1355d7f6198e67165b8c78eee06eb9ab8f0e78bd118780.jpg)  
图2基于蒙特卡罗模拟的水质预测  
Fig.2Water quality prediction based on Monte Carlo simulation

![](images/dd862da955513f8ac468c752ccc35cdbff53682d9b50de10e27dce811908d51a.jpg)  
'ig.3Probability distribution functions of water quality indicators at specific time indexes

![](images/27cdd26b2e3ca225b8d4beeca4032eb77498e641cc6af2edb212345f162ddcb4.jpg)  
图3特定时间水质指标的概率分布函数  
图4 $T L I ( \Sigma )$ 在特定时间的概率分布函数

![](images/14637abad787e0ea1f6e995fe81c5d8f7c90d1ed8a26fbf4aa26780e22e8ec3a.jpg)  
Fig.4Probability distribution functions of $T L I ( \Sigma )$ at specific time indexes   
图5不同富营养化等级概率曲线  
Fig.5The probability curves of being in different eutrophication levels

由图2所示的8个水质指标预测值曲线可知，水质指标预测值的取值范围变化大，发散性强，水质预测具有随机性。其中，水质指标Phyt、BOD、ON、 $\mathrm { N H } _ { 3 - \mathrm { N } }$ 和 $\Delta O _ { 3 } – \Delta $ 的发散性强；水质指标OP和 $\mathrm { P O } _ { 4 }$ 的发散性较小；水质指标DO的水体含量首先呈现较快的下降趋势，再稳定在较小的取值范围内。这也体现在图3的水质指标预测值概率分布曲线中。随着预测时间的增加，8个水质指标的预测值概率分布由高窄形状逐渐变为矮宽形状，这体现了水质指标的具有随机性，并受噪声影响，对噪声敏感。其中，水质指标Phyt、BOD、ON、NH3-N和 $\Delta O _ { 3 - } \mathbf { N }$ 的随机性较强，受噪声影响大，对噪声敏感；水质指标OP和 $\mathrm { P O _ { 4 } }$ 的随机性较小，受噪声影响较小，对噪声敏感度较小；水质指标DO的随机性小，受噪声影响小，对噪声敏感度小。综合图2和3所示的8个水质指标预测值曲线和概率分布曲线可知，水体环境较为复杂，水质指标预测受噪声影响，具有随机性，但预测值稳定在一定范围内，具有确定性。无外界特殊因素影响时，此阶段水体变化速度较慢。

基于图3给出的水质指标概率分布，利用3.3节给出的富营养化风险评估方法，可得到综合营养状态指数TLI(∑)的概率分布，以及处于不同营养状态的概率，结果如图4、5所示。图4中，X轴表示预测时间（为使结果更清晰，选取预测天数100天中每隔10天的同一时刻为预测时间)，Y轴表示综合营养状态指数的取值范围，Z轴为综合营养状态指数的概率密度函数。图5中，X轴表示预测时间（预测天数100天，一天取24小时，则预测时间为2400小时)，Y轴表示不同营养状态的概率。

图4中，由水体富营养化概率密度函数可知富营养化风险评估具有随机性。随着预测时间的增加，富营养化风险评估概率分布的取值范围增大，由高窄形状逐渐变为矮宽形状，具有随机性和偶然性。这也体现在图5中，随着预测时间的增加，贫营养状态概率减小，中营养状态概率增加。据浮游植物特性可知，浮游植物的生长具有季节性，水体中的富营养程度一般也具有季节性。本文选取的水质指标和模型参数初值为水体贫营养状态，且水体营养物质含量为增长阶段。综上所述，基于水质预测的水体富营养化风险评估具有规律性和随机性。

综上所述，无论是水质指标预测值的概率分布，还是富营养化风险评估的概率分布可知，水体环境由多因素影响，具有复杂性，所以水质预测具有随机性。本文提出的基于水质动力学模型和蒙特卡罗仿真的水质机理预测方法是概率性预测，相较于单一取值的水质预测，精确度更高。

# 4 结束语

本文结合水质动力学模型，提出了一种基于蒙特卡罗仿真的湖库水质预测及富营养化风险评估方法。基于湖库水质指标演化机理，利用非线性连续微分方程建立湖库水质动力学模型。在已知水质动力学模型水质指标和模型参数的先验分布基础上，利用蒙特卡罗仿真预测8个水质指标的演化过程，获得8个水质指标取值的概率分布，实现水质预测；从仿真结果可知水质指标预测具有随机性，且不同水质指标对噪声的敏感程度不一。进一步，本文通过构造综合营养状态指数，结合水质指标预测结果，计算综合营养状态指数的概率分布，同时，对综合营养状态指数分级处理，获得处于不同营养程度的概率，实现富营养化风险评估；仿真结果可知，基于水质预测的富营养化风险评估也具有随机性。综上所述，本文所提出的基于蒙特卡罗仿真的湖库水质预测及富营养化风险评估方法考虑到水质预测的随机性，弥补了单一定值的水质预测和富营养化评价方法的不精确性，降低了预测的偶然性，提高了水体的富营养化风险评估的准确度。为进一步提高预测的精度，后期工作主要分为两个部分：采用参数率定方法，结合水质指标的实测数据，获得水质动力学模型的模型参数的估计值；采用一定的方法克服模型参数的慢变假设。

# 参考文献：

[1]Meinikmann K,Hupfe Mr,Lewandowski J.Phosphorus in groundwater discharge:a potential source for lake eutrophication [J]. Journal of Hydrology,2015,524（5） :214-226.   
[2]Rast W, Thornton J. Trends in eutrophication research and control [J]. Hydrological Processes,2015,10 (2): 295-313.   
[3]Paerl H,Xu Hai,Hall,N S,et al. Nutrient limitation dynamics examined on a multi-annual scale in Lake Taihu,China:implications for controlling eutrophication and harmful algal blooms [J]. Journal of Freshwater Ecology,2015,30(1): 5-24.   
[4] 吴瑶洁，于霞，刘定富，等．我国湖泊富营养化问题及其控制措施研 究进展[J].绿色科技,2015,2015(6):189-191.(Wu Yaojie,Yu Xia, Liu Dingfu,et al. Research progress on eutrophication of lakes in China and its control measures [J]. Journal of Green Science and Technology, 2015,2015(6): 189-191.)   
[5]Woldegiorgis B T,Van Griensven A，Pereira F,et al．A new unconditionally stable and consistent quasi-analytical in-stream water quality solution scheme for CSTR-basedwater quality simulators [J]. Water Resources Research,2017,53 (6): 4668-4690.   
[6]朱文婷，钱新，钱玮，等．基于QUAL2K 模型的尾水生态净化方案 设计[J].环境化学，2018,37(3):600-608.(Zhu Wenting,Qian Xin, Qian Wei，et al.Application of QUAL2K model for ecological purification design of treated water [J]. Environmental Chemistry,2018, 37(3): 600-608.)   
[7]邱璃，卢诚，徐泽，等．湟水河流域水质时空变化特征及其污染源解 析[J].环境科学学报,2017,37(8):2829-2837.(Qiu Yu,Lu Cheng， Xu Zhe,et al. Spatio-temporal variation characteristics and water pollution sources in the Huangshui River Basin [J].Acta Scientiae Circumstantiae,2017,37(8): 2829-2837.)   
[8] Cho Jaepil，Her Younggu，Bosch D.Sensitivity of Simulated conservation practice effectiveness to representation of field and in-stream processes in the little river watershed [J].Environmental Modeling & Assessment,2016,22(2): 1159-173.   
[9]Kim T, Sheng YP. Estimation of water quality model parameters [J]. Ksce Journal of Civil Engineering,2010,14(3): 421-437.   
[10]朱文博，王洪秀，柳翠，等．河道曝气提升河流水质的WASP模型研 究[J]．环境科学，2015，36(4):1326-1331．(Zhu Wenbo，Wang Hongxiu,Liu Cui, et al. Improvement of river water qualitybyaeration: WASPmodel study[J].Environmental Science, 2015，36(4): 1326-1331. )   
[11] Wang Xiaoyi, JiaJie,Su Tingli,etal. Afusion water quality soft-sensing method based on WASP model and itsapplication in water eutrophication evaluation [J]. Journal of Chemistry,2018,2018:1-14.   
[12] Huang Jiacong, Gao Junfeng, Hormann G Hydrodynamic-phytoplankton model for short-term forecastsof phytoplankton in Lake Taihu,China[J].Limnologica-Ecology and Management of Inland Waters,2012,42(1):7-18.   
[13] Akomeah F Chun K P Karl-Frich Iindencchmidt Dvnamic quality modelling and uncertainty analysis of phytoplankton and nutrientcyclesforthe upperSouth Saskatchewan River[J]. Environmental Science and Polution Research，2015，,22(22): 18239-18251.   
[14]熊家庆，赖格英，彭小娟，等．基于 EFDC 模型对鄱阳湖湖面面积的 推算方法[J]．南京信息工程大学学报，2016,8(1):56-63.(Xiong Jiaqing,Lai Geying, Peng Xiaojuan,etal. Poyang Lake area estimation based on EFDC model[J]. Journal of Nanjing University of Information Science and Technology: Natural Science Edition,2016,8(1): 56-63.)   
[15] Arifin RR,James SC,De Alwis DA,et al. Simulating the thermal behavior in Lake Ontario using EFDC[J].Journal of Great Lakes Research,2016,42(3): 511-523.   
[16] Zhang Chunxue,You Xueyi. Application of EFDC model to grading the eutrophic state of reservoir: case study in Tianjin Erwangzhuang Reservoir, China [J]. Engineering Applications of Computational Fluid Mechanics,2017,11(1): 111-126.   
[17] Gani Y, Ustinova E,Ajakan H,etal. Domain-adversarial training of neural networks [J]. Journal of Machine Learning Research,2017,17 (1):2096-2030.   
[18]张颖，高倩倩．基于灰色模型和模糊神经网络的综合水质预测模型 研究[J].环境工程学报，2015，9(2):537-545.(Zhang Ying,Gao Qianqian.Comprehensive prediction model of water quality based on greymodel and fuzzy neural network[J].Chinese Journalof Environmental Engineering,2015,9(2): 537-545.)   
[19]马玲玲，周林飞，王铁良．基于BP 神经网络的大伙房水库水质综合 评价[J].沈阳农业大学学报，2014,45(5):637-640.Ma Lingling, Zhou Linfei, Wang Tieliang. Comprehensive evaluation of waterquality in Dahuofang reservoir based on BP neural network [J].Journal of Shenyang Agricultural University,2014,45(5): 637-640.   
[20] Yan Qiao,Ma Cong.Application of integrated ARIMA and RBF network for groundwater level forecasting[J].Environmental Earth Sciences,2016,75(5): 1-13.   
[21] GeblerD，WieglebG,SzoszkiewiczK.Integratingriver hydromorphology and water quality into ecological status modelling by artificial neural networks [J].Water Research,2018,139:395-405   
[22] Liu Binsheng,Wang Ying,Hu Xueping.A chaotic prediction method to timeseries data [J].Advanced Materials Research，2010,113-116 (1662-8985): 1367-1370.   
[23] Katimon A, Shahid S,Mohsenipour M. Modeling water quality and hydrological variables using ARIMA:a case study of Johor River, Malaysia [J]. Sustainable Water Resources Management, 2017,2017 (03): 1-8.   
[24] Faruk D O.A hybrid neural network and ARIMA model for water quality time series prediction [J]. Engineering Applications of Artificial Intelligence,2010,23 (4): 586-594.   
[25]张亚平，鲁县华，晋美．基于人工鱼群优化支持向量机水文预报系 统模型[J].计算机应用研究，2010，27(8)：2902-2905.(Zhang Ya-Ping,Lu Xian-Hua,Jin Mei. Hydrological forecasting systemmodel based on AFSVM[J]. Application Research of Computers,2010,27(8): 2902-2905.)   
[26] Defne Z,Spitz F J,De Paul V,et al.Toward a comprehensive water-quality modeling of barnegat bay: development of ROMS to WASP coupler [J]. Journal of Coastal Research,2017,78:34-45.   
[27] Jia Haifeng，Zhang Yansong，Guo Yu.The development ofa multi-species algal ecodynamic model for urban surface water systems and its application[J]. Ecological Modelling,2017,221(15):1831-1838.   
[28]湛青青.WASP水质模型和GIS 空间分析在水污染监测中的集成应 用[J].科技资讯,2015,13(34):12-14.(Zhan Qinqin.WASP water quality model and GIS spatial analysis integrated application in water pollution monitoring [J]. Science & Technology Information,2015, 13(34): 12-14.)   
[29]廖梦娜，于革，郭娅.300年来鄱阳湖营养盐演化重建与模拟[J].生 态学报，2016,36(8):2393-2402.(Liao Mengna,Yu Ge,Guo Ya. Reconstructions and simulations of nutrient evolution in Poyang Lake over the past 30O years [J]. Acta Ecologica Sinica,2016,36(8): 2393-2402.)   
[30] Gooddy D C, Lapworth D J, Bennett S A.,etal. A multi-stable isotope framework to understand eutrophication in aquatic ecosystems.[J]. Water Research,2016,88: 623-633.   
[31] Li Ranran,Zou Zhihong.Water environmental capacity analysis of taihu lake and parameter estimation based on the integration of the inverse method and Bayesian modeling [J]. International Journal of Environmental Research and Public Health,2015,12(10):12212-12224.   
[32] Shi Yuning, Davis K J, Zhang Fuqing,et al. Parameter estimation of a physically-based land surface hydrologic model using an ensemble Kalman filter: A multivariate real-data experiment [J].Advances in Water Resources,2015, 83: 421-427.   
[33]张永祥，王磊，姚伟涛，等.WASP 模型参数率定与敏感性分析[J]. 水资源与水工程学报，2009,20(5):28-30.(Zhang Yongxiang，Wang Lei，Yao Weitao,et al.Calbration and sensitive analysis on the parameters of the WASP model [J]. Journal of Water Resources &W ater Engineering,2009,20 (5): 28-30.）   
[34] Ala-Luhtala J,Whiteley N,Heine K,et al.An introduction to twisted particle filters and parameter estimation in non-linear state-space models [J]. IEEE Trans on Signal Processing,2015,64(18): 4875-4890.   
[35] He Wei,Williard N,Osterman M,etal.Prognostics of lithiumion bateries based on Dempster-Shafer theory and the Bayesian Monte Carlo method [J].Journal of Power Sources，2011，196(23): 10314-10321.   
[36]朱伦伦，熊九龙，谢金哲，等．基于蒙特卡罗仿真的校准结论风险分 析[J]．电子测量与仪器学报，2016,30(7)：1045-1051.(Zhu Lunlun, Xiong Jiulong,Xie Jinzhe,et al. Calibration conclusion risk analysis based on Monte Carlo simulation [J].Journal of Electronic Measurement and Instrument,2016,30(7):1045-1051.）   
[37] Fougere N,Altwegg K,Berthelier JJ,et al. Three-dimensional direct simulationMonte-Carlomodelingofthecomaofcomet 67P/Churyumov-Gerasimenko observed by the VIRTIS and ROSIA instruments on board Rosetta [J]. Astronomy and Astrophysics,2016, 588 (A&A): A134.   
[38]李君昌，樊重俊，杨云鹏，等．基于蒙特卡洛小波去噪的股票投资组 合风险优化研究[J]．计算机应用研究，2018，35(10): 2947-2951,3028.(Li Junchang,Fan Chongjun,Yang Yunpeng,et al. Stock portfolio risk optimization based on filtering method of wavelet using Monte Carlo simulation [J].Application Research of Computers, 2018,35 (10): 2947-2951,3028.)   
[39] Chen Bin, Siepmann JI. A novel Monte Carlo algorithm for simulating strongly associating fluids:applications to water,hydrogen fluoride, and acetic acid [J]. Journal of Physical Chemistry B,2O15,104 (36): 8725-8734.   
[40] Jorgensen WL, Jenson C. Temperature dependence of TIP3P, SPC,and TIP4P water from NPT Monte Carlo simulations: Seeking temperatures of maximum density [J]. Journal of Computational Chemistry,1998,

19(10):1179-1186.

[41]李镇镇，李晓东，李飞，等．基于动态聚类分析和盲数理论的综合营 养状态指数评价模型[J].环境工程学报，2015,9(4):2021-2026.(Li Zhenzhen,Li Xiaodong,Li Feil,etal. Improved assessment model for comprehensive trophic state index based on dynamic cluster analysis and blind theory [J].Chinese Journal of Environmental Engineering, 2015,9(4): 2021-2026.)

[42]郭成久，洪梅，闫滨．基于综合营养状态指数法的石佛寺水库水质富营养化评价[J].沈阳农业大学学报，2016,47(1)：119-123.(GUOCheng-jiu,HONGMei,YAN Bin.Eutrophication of Shifosi Reservoir

Based on Comprehensive Nutrition State Index [J]. Journal of Shenyang Agricultural University,2016,47(1):119-123.) [43]李林衡，郑飞，何春花，等．综合营养状态指数法评价鄞州区水库富 营养化程度[J]．中国给水排水，2016,32(13):75-78.(Li Linheng， ZhengFei,He Chunhua,etal.Evaluation of reservoir eutrophication in Yinzhou district based on comprehensive eutrophication state index method[J].ChinaWaterand Wastewater,2016,32(13):75-78.)