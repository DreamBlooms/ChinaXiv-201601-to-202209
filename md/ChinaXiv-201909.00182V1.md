# SRM融雪径流模型在锡林河流域的应用

王飞，朱仲元，张鹏，王慧敏，张璐(内蒙古农业大学水利与土木建筑工程学院,内蒙古呼和浩特010018)

摘要：为了验证 SRM(snowmelt-runof model)融雪径流模型在寒旱区草原流域的适用性,在阐述模型结构、参数意义的基础上,结合锡林河流域上游 2014—2016 年融雪期(3—5月)的 MODIS 积雪覆盖数据及实测气象、水文资料，采用 $\mathrm { W i n S R M \ 1 . \ 1 0 }$ 版本对2014—2016 年锡林河上游年融雪期的径流进行模拟,结果发现：SRM模型可以较好地反映锡林河融雪期径流变化趋势，有效捕捉融雪径流洪峰到达日期及洪峰流量。对模型进行精度评价，得出3a模拟值的拟合优度确定系数 $\left( R ^ { 2 } \right)$ )与体积差( ${ \bf \nabla } ( D _ { \scriptscriptstyle V } )$ 均优于世界气象组织公布的模型模拟精度均值。所以,SRM融雪径流模型在锡林河流域上游具有较好的适用性,这对合理利用草原冰雪水资源具有重要意义。

关键词：SRM模型；融雪径流；模型变量；模型参数；模型适用性；锡林河流域；内蒙古

在水资源短缺的今天，缺水问题已经成为了国际社会共同讨论的话题。我国北方地区远离海洋，降水稀少气候干旱，水资源成为制约当地人们的生存与社会经济发展的关键环境因子。而季节性积雪融水作为干旱区重要淡水资源，是地表径流的主要补给来源之一(1-4]。所以,识别融雪产汇流规律、定量判别融雪径流量，预测未来气候条件下融雪径流变化过程，成为干旱区水文水资源研究的热点问题，而融雪径流模型是研究这类问题的重要方法和手段之-[5-6] O

目前，融雪径流模型发展日益成熟，多数模型可较为准确地估算和模拟径流量。这些模型主要分两类[6-9]：一种是基于度日因子的概念模型,如 SRM（snowmelt-runoffmodel)模型、HBV水文预报模型、PRMS 降水径流模型等。另一种是物理机制模型，如 SNTHERM、VIC、MILESHE等(10-13）。相对于概念模型，物理模型更注重融雪的物理机制变化，所以这类模型一般都需要输入较为精确的物理数据与参数，而在我国西北地区气象站、水文站相对较少，不能满足模型所需的数据输人要求，概念模型就成为西北地区的最佳选择[14-15]。概念融雪模型,以SRM融雪径流模型为代表，近些年来国内外学者对SRM模型的应用与改进有颇为丰硕的成果。Kustas等[1使用 SRM生成的径流的灵敏度分析,研究辐射与度日法等三种模式下，基于辐射等影响积雪消融的因子，对模型不同流域尺度下径流量预测值的影响,Martinec 等[17]分析了SRM模型的参数,综合考虑了SRM参数值可能对不同高程盆地的适应性。马虹等[18]对 SRM模型在天山西部巩乃斯河流域的适用性研究发现，该模型在研究区具有良好的应用前景。李宏毅等[14]以黑河流域为对象，研究表明，SRM模型在黑河流域上游具有较高的径流量模拟精度。赵军等[15使用SRM模型对疏勒河流域春季径流进行了模拟，得到了SRM模型可用于该流域春季融雪型洪水预测的结果。另外,陈心池等[19]刘文等[20]、怀保娟等[21]均利用 SRM 模型在我国北方典型干旱区河流流域开展了一系列研究，并取得了较好的成果。

目前，有关SRM模型研究成果颇丰，但模型在寒旱区草原流域应用极少。本文以寒旱区草原内陆河流域锡林河为例，运用SRM模型对流域融雪期的径流进行模拟，对SRM模型在寒旱区草原流域的适用性进行分析，以期为草原流域防汛减灾与水资源合理利用提供科学依据。

# 研究区概况与数据

# 1.1 研究区概况

锡林河发源于赤峰市克什克腾旗的敖仑诺尔和呼伦诺尔，纵贯锡林郭勒盟中部，经过锡林浩特市，最后流入查干诺尔沼泽，全长 $2 6 8 ~ \mathrm { k m }$ 。其东缘属于大兴安岭西麓低山丘陵区，海拔为 $1 5 0 0 \mathrm { ~ m ~ }$ 。锡林河有3条主要支流，好来吐郭勒河、好来郭勒河、胡斯特河（图1）。3条支流均在锡林河水库上游汇入，水库以下无支流汇入，所以导致整个流域水系呈不对称分布。全流域面积为 $1 0 \ 5 4 2 \ { \mathrm { k m } } ^ { 2 }$ ,地理位置为$4 3 ^ { \circ } 2 6 ^ { \prime } \sim 4 4 ^ { \circ } 3 9 ^ { \prime } \mathrm { N } , 1 1 5 ^ { \circ } 3 2 ^ { \prime } \sim 1 1 7 ^ { \circ } 1 2 ^ { \prime } \mathrm { E }$ 。近些年，由于锡林河流域干旱少雨，加之锡林河水库的截流蓄水，导致流域下游长期断流，故选择水库上游的锡林浩特水文站断面以上的锡林河上游流域，流域面积为 $3 \ 8 5 2 \ \mathrm { k m } ^ { 2 }$ 。锡林浩特水文站是锡林河流域唯一的控制水文站，地理位置 $4 3 ^ { \circ } 4 9 ^ { \prime } 2 4 . 8 ^ { \prime \prime } \mathrm { N }$ $1 1 6 ^ { \circ } 0 9 ^ { \prime } 3 8 . 5 ^ { \prime \prime } \mathrm { E }$ ,高程为 $9 9 6 \mathrm { ~ m ~ }$ 。根据中国地面气候资料日值数据集锡林浩特站1980—2016年逐日气象资料统计表明：研究区多年平均气温为 $2 . 7 1 \ \mathrm { { ^ { \circ } C } }$ ，其中积雪期（上年10月到翌年4月)多年平均气温为 $- 7 . 3 2 \mathrm { ~ } \mathrm { ^ { \circ } C }$ ,年平均降水量 $2 5 0 \sim 4 0 0 ~ \mathrm { m m }$ ,其中冬季降水占全年降水量的 $1 9 . 8 \%$ ，而融雪是春季径流的主要来源。根据锡林浩特水文站1963一2013 年50a径流资料的统计，按流域已有研究经验将春季融雪径流时间规定为3一5月，计算得到各年春季融雪径流占年总径流量比例如图2，锡林河流域1963—2013年春季融雪径流占全年总径流量的 $5 2 . 3 2 \%$ 。

![](images/1ec1e088aeec1be3aa57541124a75f5a6bf18829a365ab4e2506c9e8e34e8be4.jpg)  
图1锡林河上游流域位置及观测站点示意图

![](images/24a4b57046cea4d6a5043f3a3c0f9d55bf1cabf8ea3a398b6496af9fbc8522cd.jpg)  
Fig.1Location of upper reaches of the Xilin River Basin and distribution of the observation stations   
图21963—2013 年春季融雪径流量占比 Fig.2Proportion of spring snowmelt volume in the annual runoff volume during the period of 1963-2013

# 1.2数据

1.2.1积雪覆盖数据本文所用的积雪面积数据来源于美国冰雪数据中心（Nand Ice Data Center,NSIDC）。其积雪数据产品包括MOD10A1、MOD10A2、MOD10C1、MOD10C2、MOD10L2G等。本文采用的是经8d合成的空间分辨率为 $5 0 0 \mathrm { ~ m ~ }$ 的MOD10A2积雪产品数据。

1.2.2水文气象数据气象数据来源于中国气象数据共享服务网（http://cdc.cma.gov.cn）。模型输入的气象数据包括日均气温与日降水量，由于锡林河流域内仅有唯一的锡林浩特气象站，融雪期的日气象数据由该气象站提供,径流数据是锡林浩特水文站提供的融雪期日径流量资料。

# 2模型介绍及参变量的确定

# 2.1 SRM模型简述

SRM模型是1975年由瑞士科学家Martinec 主持开发的用于模拟和预报融雪径流的水文模型，按世界气象组织报告中提出的分类方法，SRM模型是确定性分布式的水文概念模型，同时也是为数不多的采用遥感数据作为模型输入变量的水文模型。模型所需输入的日气温、日降水和流域的积雪覆盖率3个基本变量，气温与降水是常规的气象数据,积雪覆盖率是遥感解译数据，都能很方便的得到。SRM模型是一种简单易用精度较高的水文模型，是国际气象组织推荐的融雪径流模拟模型，到目前为止SRM模型已在全球近200个流域得到广泛应用[16-18]  
O

# 2.2 SRM模型结构

SRM模型的原理是计算逐日的降水与融雪分别产生的水量，并与前日的退水流量相加得到的逐日径流量。其计算公式如下[17]：

$$
Q _ { n + 1 } = \left[ C _ { \mathrm { { S } } n } \cdot \alpha _ { n } ( T _ { n } + \Delta T _ { n } ) { \cal S } _ { n } + C _ { \mathrm { { R } } n } P _ { n } \right] \ .
$$

$$
\frac { A \cdot 1 0 ~ 0 0 0 } { 8 6 ~ 4 0 0 } ( 1 - K _ { n + 1 } ) + Q _ { n } K _ { n + 1 }
$$

式中： $Q$ 为日平均流量 $( \mathbf { m } ^ { 3 } \cdot \mathbf { s } ^ { - 1 } ) ; C _ { \mathrm { { R } } }$ 为降雨径流系数； $C _ { \mathrm { s } }$ 融雪径流系数； $\alpha$ 为度日因子( $\mathrm { c m } \cdot \mathrm { ^ q C } ^ { - 1 }$ ：$\textrm { d } ^ { - 1 }$ ),表示单位度日因子的雪融化深度; $T$ 是度日因子数； $\varDelta T$ 是高程度日因子修正值; $s$ 是积雪覆盖率;$P$ 为降雨量( $\mathbf { m } \mathbf { m }$ )；A为流域面积； $K$ 是流量衰退系数，表示在没有融雪或者降雨情况下径流衰减量; $n$ 为径流计算时间段的日数序列; $1 0 \ 0 0 0 / 8 6 \ 4 0 0$ 是径流深变换为径流量的转化系数。其中，降水、气温、积雪覆盖率是模型的驱动变量，而其余参数是根据研究区的条件确定的模型输人参数。

# 2.3模型参变量的确定

2.3.1流域特征参数锡林河流域平均海拔高度$9 8 8 . 5 \mathrm { ~ m ~ }$ ,流域最高处位于东南部嘆顺乌拉峰，海拔高于 $1 ~ 5 0 5 . 6 \mathrm { ~ m ~ }$ ,最低处位于锡林河下游，海拔低于$1 ~ 0 0 0 ~ \mathrm { m }$ ，高度差最大仅 $6 0 0 \mathrm { ~ m ~ }$ ,而下游常年断流，对于本文所研究的锡林河上游而言，高程差不足500$\mathbf { m }$ ,所以不对高程分带。将面积为 $3 \ 8 5 2 \ \mathrm { k m } ^ { 2 }$ ,平均海拔为 $1 ~ 2 0 6 ~ \mathrm { m }$ 的锡林河上游看作全流域的一个高程带进行模拟研究。

# 2.3.2 模型变量

（1）气温与度日数：模型中以度日数反映气温变化。气温是衡量积雪消融能量的一个重要的综合性指标，且气温数据易获取，也可根据研究通融的不同进行插值和预报。度日数一般采用气象站台的观测值进行计算[18]：

$$
T = \frac { T _ { \mathrm { m i n } } + T _ { \mathrm { m a x } } } { 2 }
$$

式中： $T$ 为日平均气温,即平均度日数; $T _ { \mathrm { m i n } }$ 与 $T _ { \mathrm { m a x } }$ 为逐日最低气温与最高气温。高程度日因子修正值$\Delta T$ 计算公式如下：

$$
\Delta T = \gamma ( h _ { \mathrm { { s t } } } - \overline { { h } } ) \times \frac { 1 } { 1 0 0 }
$$

式中： $\gamma$ 为气温直减率； $h _ { \mathrm { s t } }$ 气象站台的海拔高度; $\overset { - } { h }$   
在本文中为研究区平均海拔高度。

（2）积雪覆盖率：积雪覆盖率是SRM模型的核心输入变量，选用归一化积雪指数(NDSI)结合近红外通道的反射率判别方法，将MOD10A2时间尺度为8d积雪面积资料生成逐日积雪面积数据[2 -23] O积雪覆盖率是由流域研究区积雪面积比流域研究区总面积所得的比率，模拟期(2014—2016年融雪期)的积雪覆盖率变化见图3。如图3所示，积雪面积覆盖率与径流存在反向滞时的逆变化趋势，即积雪面积不断减少直至接近于0，径流开始有流量且不断增加，直至达到洪峰流量，融雪水补给径流达到最大量，径流流量开始逐渐减小，洪峰退去，可见，在融雪初期积雪融水是径流的最主要来源。观察2015年积雪覆盖率与径流流量的关系不难发现，从3月下旬开始流域上游出现了大面积的降雪，但径流流量并未产生较大的突变现象，只在4月20日左右有小幅度升高，整体变化仍按正常趋势。分析其原因，3月下旬气温回升土壤解冻，积雪融水直接进入土壤补给地下水，对地表水补给有限，所以，对锡林河径流并未产生较大影响。

# 2.3.3 模型参数

（1）径流系数：径流系数包括融雪径流系数$( C _ { \mathrm { s } } )$ 与降雨径流系数( $\boxed { C _ { \mathrm { R } } }$ ），其值介于0\~1之间。具体取值一般根据流域的地理气候特征选取，在锡林河流域融雪初期(3月），径流损耗较低，径流系数较高;融雪中期(4月)土地裸露，植物生长，融雪径流产生过程中损耗变大，径流系数也随之减小;融雪末期(5月），径流损耗有所降低，径流系数也会变大。所以，通过2007—2013年锡林浩特水文站融雪期径流量的变化，率定得到一组融雪径流系数与降雨径流系数，3月和5月径流系数值较高，4月较低，3月 $C _ { \mathrm { s } }$ 与 $C _ { \mathrm { R } }$ 分别为0.3、0.1,4月两个系数均为0.25，5月为0.3、0.15。

（2）度日因子：度日因子是SRM模型中计算每日融雪深度的一个核心参数，其定义为：每日气温上升 $1 \ \mathrm { { ^ { \circ } C } }$ 所产生的融雪深度。它和度日数与融雪水深的关系为：

$$
M = \alpha \cdot T
$$

式中： $M$ 为融雪水深; $\alpha$ 为度日因子； $T$ 为度日数。由于本研究区没有实测数据，度日因子采用SRM手册建议的经验公式获取[24]：

$$
\alpha = 1 . ~ 1 \times \frac { \rho _ { \mathrm { s } } } { \rho _ { \mathrm { w } } }
$$

式中： $\alpha$ 是度日因子； $\rho _ { \mathrm { s } }$ 是积雪的密度； $\rho _ { w }$ 为水的容重。本文使用的积雪密度参数是2011—2013年锡林河流域的积雪实验观测数据，并结合刘宝河[25]的积雪密度研究结果,综合率定积雪密度为 $0 . 1 4 2 \ { \mathrm { g } } \cdot { \mathrm { \Omega } }$ （2$\mathrm { c m } ^ { - 3 }$ ,最后确定度日因子为0.159。

(3）临界温度：临界温度是指流域在整个融雪期间，降水有降雨与降雪两种状态。采用临界温度区分降水的形态,大于临界温度为降雨，小于临界温度为降雪。模型模拟中临界温度一般为日平均温度，通常要大于 $0 \ \mathrm { { ^ circ C } }$ ,本文根据1969—1979年锡林浩特国家气象站台提供的融雪期日均气温及降水相态情况，率定临界温度取 $0 \sim 5 . 1 ~ \mathrm { { ‰ } }$ 。

![](images/0fdd638cf5726fd911b71827d5abbd354b35778b385cb0b1dd6bd7d0f7fe4d5f.jpg)  
图32014—2016 年锡林河流域上游积雪面积覆盖率及径流融雪期(3—5月)变化趋势 Fig.3Change trends of snow coverage and snow melt duration（from March to May）in upper reaches of the Xilin River Basin during the period of 2014-2016

(4）温度直减率：是指气温随海拔的升高而递减的速率，在模型运行中温度直减率可根据研究流域的地理情况确定，本文因研究的流域海拔变化范围较小，没有进行海拔分区，所以温度直减率对模拟结果影响较小,根据经验值确定海拔高度每增加$1 0 0 \mathrm { ~ m ~ }$ 气温下降 $0 . 6 5 ~ \mathrm { ^ { \circ } C }$ 。

(5）降雨贡献面积、流域滞时：融雪过程中，降雨的贡献面积在融雪期不同阶段率定不同的参数值。流域滞时是冲积雪融化开始至融水到达水文断面的时间，此参数可根据世界气象组织公布的结果，结合研究流域确定[25],对于锡林河流域采用 $^ { 1 2 \mathrm { ~ h ~ } }$ 的滞时值。

（6）退水系数：退水系数是SRM模型的一个重要参数，它是指在没有融雪或降雨的时间阶段径流的下降值，其能反映出融雪直接补给到径流量的部分。退水系数由以下计算公式得到：

$$
K _ { n + 1 } = { \frac { Q _ { n + 1 } } { Q _ { n } } }
$$

$$
K _ { n + 1 } = x Q _ { n } ^ { - y }
$$

式中： $K$ 是退水系数; $Q _ { n }$ 为第 $n$ 天的日径流量; $x , y$ 均为常量。本文选取2007—2013 年锡林河上游锡林浩特水文站3一5月的逐日径流量，作散点图（图4）,其趋势线可代表退水过程,根据趋势线确定 $x , y$ 值，从而得到退水系数的推导公式为：

$$
K _ { _ { n + 1 } } = 1 . 0 2 0 ~ 2 7 8 ~ \cdot ~ Q _ { _ n } ^ { - 0 . 0 0 8 ~ 7 }
$$

# 3融雪径流模拟结果精度分析

# 3.1 模拟结果

经参数率定，变量的输入及模型的检验后，运用

![](images/494f8e76e270e9b8daea5a1ea8018ec2022a5d52bd87106d6eda9385bb0abe2d.jpg)  
图42007—2013年锡林河流域融雪期退水过程散点图 Fig.4Scatter diagram of depletion process in snow melt period in the Xilin River Basin during the period of 2OO7-2013   
图52014—2016 年锡林河上游融雪期实际与模拟径流值 Fig.5Measured and simulated values of runoff volume in snow melt period in upper reaches of the Xilin River Basin during the period of 2014 -2016

-·)/鲁日 543210 一实测流量模拟流量  
10-00 80-£0 91-05 22-55 60-60 00-55 -4 61-50 94-40 00-00 01-90 21-50 5214 153-55日期／月-日  
（-S·u/鲁日 5  
43210  
10-00 80-0 1-05 20-00 60-00 00-55 1-10 61-50 94-45 00-90 01-10 1-90 52-00 153-55日期/月-日  
（-S·)/鲁日 5  
43210 1  
10-00 80-£0 01-55 22-0 62-55 00-55 71-50 6-0 94-54 00-90 01-50 11-50 2-00 53-55日期/月-日

SRM模型对锡林河流域上游2014—2016年3—5月进行融雪径流模拟，得到了连续3a融雪期日径流量的模拟值，将其与实测值进行对比分析，结果如图5所示。

从图5可以看出，SRM模型模拟产生的日径流量过程线与实测日径流量过程线变化趋势基本吻合，能够较好地反映出锡林河融雪期径流变化趋势，并可以较为准确地捕捉融雪径流洪峰到达日期及洪峰流量，但逐日径流模拟值并不十分准确，个别日期存在着较大的误差。融雪径流洪峰到达之前，模拟值与实测值之间的误差较大，而洪峰之后模拟值偏差较小。由图5还可以看出，在4月10日之前3a的模拟值均小于实测值，4月10日之后模拟值均大于实测值。

考虑其误差产生的原因，洪峰前误差较大，可能是因为锡林河上游流域在洪峰到达之前，气温变化不稳定，降雪与降水都有发生，积雪的融化速度随温度变化波动大，导致融雪水量模拟难度大，模拟效果不佳;而洪峰之后，气温稳定上升，降水单一，主要表现为降雨、积雪融水较之前阶段少，稳定的融雪过程是此阶段模拟值偏差较小的主要原因。4月10日前低估了实际流量，之后又高估了实际流量，其原因可能是没有考虑融雪过程中下垫面的水文条件，在4月10日之前气温较低蒸散发较小，且存在地下水及冻土层补给地表水的现象。4月10日之后温度上升，因下垫面条件变得更为复杂,牧草返青，土壤解冻，融雪水下渗水量增大，模型模拟并未考虑下渗过程，导致高估了实际径流量。

# 3.2 模拟结果的评价

为定量分析SRM融雪径流模型在锡林河流域上游的模拟精度，本文引入2个精度分析指标来评价模拟结果：无量纲的拟合优度确定系数Nash-Sut-cliffe系数 $R ^ { 2 }$ 和体积差 ${ \cal D } _ { \scriptscriptstyle V }$ 。

$$
R ^ { 2 } = 1 - \frac { \displaystyle \sum _ { i = 1 } ^ { n } ( \ : Q _ { i } - Q _ { i } ^ { ' } ) ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { n } ( \ : Q _ { i } - \overline { { { Q _ { i } } } } ) ^ { 2 } }
$$

式中： $Q _ { i }$ 为实测的日径流量； $Q _ { i } ^ { ' }$ 为模拟得到的日径流量； $\overline { { Q } }$ 为模拟得到的整个融雪期的平均径流量; $n$ 为融雪期的总天数。径流体积差如下

$$
D _ { _ { V } } = \frac { V _ { _ { R } } - V _ { _ { R } } ^ { ^ { ' } } } { V _ { _ { R } } } \times 1 0 0 \%
$$

式中： $\boldsymbol { V } _ { R }$ 为融雪期的实际径流体积； $V _ { R } ^ { ' }$ 是模拟得到的融雪期径流体积。 $R ^ { 2 }$ 的范围为0～1，越接近1，模拟精度越高。 $D _ { \scriptscriptstyle { V } }$ 的绝对值越小表明模拟效果越好。

将实测值与模拟结果带入式（9）和式（10），可得到融雪径流模拟结果的2个精度指标（表1）所示。根据世界气象组织对主要融雪径流模型的评价结果，SRM在融雪径流模拟中， $R ^ { 2 }$ 的平均值为$0 . 8 1 1 , D _ { \scriptscriptstyle V }$ 的均值为 $5 . 9 7 \%$ [24]。2014——2016年的模拟结果均满足模型模拟精度要求，说明SRM模型在

# 表12014—2016年融雪期径流模拟值拟合优度确定系数 $\scriptstyle ( R ^ { 2 }$ )和体积差 $( D _ { \nu } )$ （204号

Tab.1 Determination coefficients $\scriptstyle ( R ^ { 2 } )$ and volume differences $( D _ { \nu } )$ of fit goodness of simulated values of runoff volume in snow melt period from 2o14 to 2016   

<html><body><table><tr><td>年份</td><td>R²</td><td>Dv/%</td></tr><tr><td>2014</td><td>0.8487</td><td>5.545 2</td></tr><tr><td>2015</td><td>0.885 6</td><td>3.185 9</td></tr><tr><td>2016</td><td>0.816 5</td><td>1.707 0</td></tr></table></body></html>

锡林河流域上游的应用有较好的模拟效果。

# 4结语

本文利用SRM模型对锡林河流域上游的融雪径流进行模拟，发现SRM模型可以再现融雪期径流的变化趋势，能够较为准确地把握洪峰到达日期及洪峰流量，在模型模拟精度评价中,精度评价指标均优于模型模拟精度均值，表明SRM融雪径流模型在锡林河流域上游具有较好的适用性。这一研究结果对SRM模型在寒旱区草原流域的运用提供技术支持，并且对合理利用草原冰雪水资源及其草原流域春季防洪工作具有重要意义。

虽然模型模拟效果较好，但仍存在不合理的地方，如因其模型本身的局限性，忽略了融雪过程中水量的蒸发、下渗、截流等因素，而寒旱区草原的水文过程十分复杂，这些因素都会对融雪径流的产生造成影响。模拟过程中的误差除模型本身的局限性及系统误差，其输入模型的变量积雪覆盖率、气温、降水等数据的代表性有限，也是误差产生的主要原因。积雪覆盖率是经8d合成的空间分辨率为 $5 0 0 \mathrm { ~ m ~ }$ 的MOD10A2积雪产品数据所得，数据本身就存在误差。气温、降水数据来自锡林河上游唯一的气象站，站点代表性有限。在今后的研究过程中，应根据流域情况加密研究区气象站点分布，并选取精度更高的积雪覆盖数据，结合流域特点对模型加以改进，提高模拟精度，减小模拟误差。

# 参考文献（References）：

[1]夏自强，郭文献.河流健康研究进展与前瞻[J].长江流域资源 与环境,2008,17（2）:252.[Xia Ziqiang,Guo Wenxian.Progress and prospect of river health research[J].Journal of Yangtze River Resources and Environment,2008,17(2）:252.]   
[2]党素珍,刘昌明，王中根,等.黑河流域上游融雪径流时间变化 特征及成因分析[J].冰川冻土,2012,34(4）：920-926.[Dang Suzhen,Liu Changming，Wang Zhonggen,etal.Timevariation characteristics and genesis analysis of snowmelt runof in the upper reaches of Heihe River Basin[J]. Journal of Glaciology and Geocryology,2012,34(4) :920-926.]   
[3]王海娥,李生辰,张青梅,等.青海高原1961—2013 年积雪日 数变化特征分析[J].冰川冻土,2016,38（5）:1219-1 226. [Wang Hai'e,Li Shengchen,Zhang Qingmei,et al. Analysis of the variation characteristics of snow cover days in Qinghai Plateau from 1961 to 2013[J].Journal of Glaciology and Geocryology,2016,38 (5):1 219 -1 226.]   
[4]吕爱锋,贾绍凤,燕华云,等.三江源地区融雪径流时间变化特征 与趋势分析[J].资源科学,2009,31（10）:1 704-1 709.[Lu Aifeng,Jia Shaofeng,Yan Huayun,et al.Time-varying characteristics and trend analysis of snowmelt runoff in Sanjiangyuan area[J]. Journal of Resources Science,2009,31(10):1 704-1 709.]   
[5］陈华,杨阳,王伟.基于文献计量分析我国生态水文学研究现 状及热点[J].冰川冻土,2016,38（3）:769-775.[Chen Hua, Yang Yang,Wang Wei.The eco-hydrology in China analyzed based on bibliometric;Domestic research status and hot spots[J].Journal of Glaciologyand Geocryology,2016,38（3）:769-775.]   
[6]裴欢,房世峰,刘志辉,等.分布式融雪径流模型的设计及应用 [J].资源科学,2008,30（3）:454-459.[Pei Huan,Fang Shifeng,Liu Zhihui,etal.Design and application of distributed snowmelt runoff model[J]. Journal of Resource Science,2008,30 (3) :454-459.]   
[7]刘俊峰,杨建平,陈仁升,等.SRM融雪径流模型在长江源区冬 克玛底河流域的应用[J].地理学报,2006,61（11）：1149- 1 159.[Liu Junfeng,Yang Jianping,Chen Rensheng,etal.Aplication of SRM snowmelt runoff model in Dongkemadi River Basin of the Yangtze River source area[J]. Acta Geographica Sinica, 2006,61(11) :1 149 -1 159.]   
[8］王建,沈永平,鲁安新,等.气候变化对中国西北地区山区融雪 径流的影响[J].冰川冻土,2001,23（1）:28-33.[Wang Jian, Shen Yongping,Lu Anxin,et al. Impacts of climate change on snowmelt runof in mountainous areas of Northwest China[J]. Journal of Glaciology and Geocryology,2001,23（1）:28 -33.]   
[9]康尔泗,程国栋,蓝永超,等.概念性水文模型在出山径流预报 中的应用[J].地球科学进展,2002,17（1）:18-26.[Kang Ersi,Cheng Guodong,Lan Yongchao,et al.Application of conceptual hydrological model in mountain runoff forecast[J].Advances in Earth Science,2002,17(1） :18-26.]   
[10]Liang X,Letenmaier DP,Wood EF,et al.A simple hydrologically based model of land surface water and energy fluxes for general circulation models[J].Journal of Geophysical Research Atmospheres,1994,99(D7）:14 415 -14 428.   
[11］潘金梅.GLDAS 数据驱动积雪热力模型估算流域融雪量 [C]//中国地理学会.地理学核心问题与主线——中国地理学 会 2011年学术年会暨中国科学院新疆生态与地理研究所建 所五十年庆典论文摘要集.北京：中国地理学会,2011.〔Pan Jinmei.GLDAS data-driven snow thermal model to estimate the amount of snowmelt in the basin[C]//China Geography Society. The Core Issues and Main Line of Geography:2011 Annual Conference of the Chinese Geography Society and the Institute of Ecology and Geography of the Chinese Academy of Sciences Abstract Collection of Annual Celebration Papers.Beijing:Chinese Geographical Society,2011.]   
[12］何思为,南卓铜,张凌,等.用VIC 模型模拟黑河上游流域水分 和能量通量的时空分布[J].冰川冻土,2015,37（1)：211-   
225.[He Siwei,Nan Zhuotong,Zhang Ling,et al. Simulating the temporal and spatial distribution of water and energy flux in the upper reaches of the Heihe River using VIC model[J]. Journal of Glaciology and Geocryology,2015,37(1） :211-225.] [13］田开迪,沈冰,贾宪.MIKE SHE 模型在灞河径流模拟中的应用 研究[J].水资源与水工程学报,2016,27（1)：91-95.[Tian Kaidi,Shen Bing,Jia Xian.Application of MIKE SHE model in simulation of Weihe River runoff[J].Journal of Water Resources and Water Engineering,2016,27(1):91-95.] [14］李弘毅,王建.SRM融雪径流模型在黑河流域上游的模拟研究 [J].冰川冻土,2008,30(5）:769-775.[LiHongyi,Wang Jian. Simulation of SRM snowmelt runoff model in the upper reaches of Heihe River Basin[J]. Journal of Glaciologyand Geocryology,   
2008,30(5) :769 -775.] [15〕赵军,黄永生,宋阁庆,等.SRM融雪径流模型在疏勒河流域上 游的应用[J].水资源与水工程学报，2015（1）：72-76.［Zhao Jun,Huang Yongsheng,Song Geqing,et al.Application of SRM snowmelt runoff model in the upper reaches of Shule River Basin [J].Journal of Water Resources and Water Engineering,2015 (1):72-76.] [16]Kustas WP,Rango A,Uijlenhoet R.A simple energy budget algorithm for the snowmelt runoff model[J].Water Resources Research,1994,30(5):1 515-1 527. [17]Martinec J,Rango A.Parameter values for snowmelt runoff modelling[J].Journal of Hydrology,1986,84(3）:197 -219. [18］马虹，程国栋.SRM融雪径流模型在西天山巩乃斯河流域的应 用实验[J].科学通报,2003,48（19）:2088-2093.[Ma Hong， Cheng Guodong.Application experiment of SRM snowmelt runoff model in the Gongnaisi River Basin of the Western Tianshan Mountains[J].Chinese Science Bulletin,2003,48（19）:2 088 -   
2 093.] [19］陈心池，张利平，陈少丹，等.SRM融雪径流模型在奎屯河流域 洪水预报的应用[J].南水北调与水利科技，2018，16(1)：50- 56.[Chen Xinchi,Zhang Liping,Chen Shaodan,et al.Application of SRM snowmelt runoff model inflood forecasting in Kuitun River Basin[J].South-to-North Water Transfer and Water Science and Technology,2018,16（1）:50-56.]   
[20］刘文,李智录,李抗彬.SRM融雪径流模型在塔什库尔干河流 域的应用研究[J].水利技术监督，2007，15（3）：43-46.［Liu Wen,Li Zhilu,Li Kangbin.Application of SRM snowmelt runoff model in the Tashkurgan River Basin[J].Technical Supervision in Water Resources,2007,15(3）:43-46.]   
[21]怀保娟，李忠勤，孙美平，等.SRM融雪径流模型在乌鲁木齐河 源区的应用研究[J].干旱区地理,2013,36(1）：41-48.[Huai Baojuan,Li Zhongqin,Sun Meiping,et al.Application of SRM snowmelt runoff model in the source region of Urumqi River[J]. Arid Land Geography,2013,36(1） :41-48.]   
[22]穆振侠，姜卉芳，刘丰.2001—2008 年天山西部山区积雪覆盖 及NDVI的时空变化特性[J].冰川冻土,2010,32（5）：875- 882.[Mu Zhenxia,Jiang Huifang,Liu Feng.Temporal and spatial variation characteristics of snow cover and NDVI in the Western mountainous area of Tianshan from 2OO1 to 2Oo8[J].Journal of Glaciology and Geocryology,2010,32(5）:875-882.]   
[23］郝祥云,朱仲元,宋海清,等.锡林河流域积雪时空特征及其对 径流的影响[J].水土保持研究,2017,24(6)：360-365.[Hao Xiangyun,Zhu Zhongyuan,Song Haiqing,et al. Temporal and spatial characteristics of snow cover in Xilin River Basin and its influence on runof[J].Soil and Water Conservation Research,2017, 24(6):360 -365.]   
[24]Martinec J,Rango A,Roberts R.The Snowmelt Runoff Model (SRM）User's Manual（Updated Edition 1998,Version 4.0) [M].Berne:University of Berne,1998:7-30,45-57.   
[25］刘宝河.锡林郭勒典型草原区积雪过程与风雪流研究[D].呼 和浩特：内蒙古农业大学,2017.［Liu Baohe.Studyon Snow Accumulation Process and Wind and Snow Flow in Typical Steppe Area of Xilin Gol[D].Hohhot: Inner Mongolia Agricultural University,2017.]

# Application of A Snowmelt Runoff Model in the Xilin River Basin

WANG Fei， ZHU Zhong-yuan， ZHANG Peng， WANG Hui-min， ZHANG Lu(CollgeofWateresocdilEgig,rogaricalUesityt8roga)

Abstract：Inthis study,the MODIS snow cover dataand the measured meteorological and hydrological data in the upper reaches of the Xilin River Basin in snow melt period（from March to May）of 2014-2016 were simulated by WinSRM1.10.The purposes of the study were to verify the applicabilityof a snowmelt runoff model（SRM）in the drainage basins in arid and alpine steppe based on the description of the model structure and the meaning of the parameters,and to reveal the proportion of spring snowmelt volume inannual runoff volume in the upper reaches of the Xilin River Basin from 2O14 to 2016.The results showed that the SRMcould be used to ideally reflect the change trend of spring snowmelt volume in the study area,and to predictthe time offlood peak of spring snowmelt.The accuracy of the model was evaluated,and the fit goodness coefficient $( R ^ { 2 } )$ and volume difference $( D _ { \nu } )$ of the 3-year simulated values were obtained,which were superior to the mean values published by the World Meteorological Organization.Therefore,the SRM hasa good applicability in the upper reaches of the Xilin River Basin,and it is of great significance for the rational use of ice-snow resources in grasslands.

Key words:snowmelt runof model；snowmelt runoff；model variables；model parameters；model applicability; Xilin River Basin；Inner Mongolia