# 基于统计降尺度方法的陕西省月气温预测分析

魏娜

（陕西省气候中心，陕西 西安710015)

摘要：从短期气候预测的实际出发,针对月尺度的气温分县预测,使用逐步回归和主成分分析（即经验证交函数)的统计降尺度方法，利用地面测站的气温资料、美国国家环境预报中心和美国大气科学研究中心的大尺度气候变量（NCEP/NCAR)和国家气候中心月动力延伸预报模式资料(DERF),对1982—2015年陕西省96个县区的1月和7月气温进行预测,建立统计降尺度模型，并采用交叉检验方法检验模型的预测效果，表明基于经验证交函数和逐步回归的统计降尺度方法在陕西省1月和7月气温的预测中是合理可用的。全省96个县区1月份预测值与观测值距平符号一致率大于 $6 0 \%$ 达到了50个县区，7月份大于 $6 0 \%$ 达到了60个县区。预测值可以较好的预测出气温变化趋势，但预测值变化幅度明显小于实测值。

关键词：月气温；统计降尺度;气候变化；预报模型中图分类号：P457.3 文献标识码：A 文章编号

随着社会经济的不断发展，对气候服务的需求变得越来越迫切，气候服务无论从内容、时效还是预测准确率方面都遇到了新的挑战。短期气候预测一直是气候服务的主要内容之一，其预测范围的精细化和准确率一直是气候预测工作的难点和重点。近年来随着动力气候模式的不断发展，大气环流模式对大气环流特征量模拟效果得到了很大的改善，但大气环流模式输出空间分辨率低，缺少详细的区域气候信息。目前有两种方法可以弥补大气环流模式预测区域气候信息的不足，一是要发展高分辨率的区域气候模式，另一个方法就是降尺度方法。发展高分辨率模式需要计算量很大，模式构成复杂，所以降尺度是一种较为可行的方法。降尺度方法认为区域气候变化不仅受大尺度环流因子控制，也受到区域尺度因子影响，把大尺度、低分辨率的大气环流模式信息转化为区域尺度气候信息（如气温、降水），从而弥补大气环流模式对区域气候预测的局限[1-6]

降尺度方法一般有动力和统计降尺度两个方法，统计降尺度主要是建立大尺度气候要素（大气环流指数)和区域气候要素(气温、降水等)之间的统计关系，并用独立的观测资料检验这种关系，最后再把这种关系应用于模式输出的大尺度气候信息，预测区域气候要素的变化趋势

随着我国动力气候模式预测系统不断完善，月动力延伸集合预测系统(DERF)模式提供的月平均集合预报场具备较好的预报能力，为开展动力气候模式产品解释应用提供了必要条件。我国很多省份用统计降尺度方法对模式产品进行了解释应用，在实际预测中得到了较好的应用[7-I]。本文采用经验正交函数(EOF)和逐步回归为组合的统计降尺度方法，建立大尺度气候预报因子（月动力模式产品DERF)与陕西省1月和7月气温的统计关系，并用独立的观测资料来检验这种关系，对采用的降尺度方法的适用性和模式产品的质量进行评估和检验。

# 1资料与方法

# 1.1 资料简介

本文所采用的地面观测资料为陕西省96个县区1982—2015年最冷月（1月）和最热月（7月）平均气温，代表区域尺度的信息，也是预报对象；采用的模式资料为NCEP/NCAR再分析资料和国家气候中心月动力延伸预报模式资料，代表了大尺度信息，也是预报因子。应用于统计降尺度的预报因子非常多,大尺度气候因子中最常用的预报因子是海平面气压（SLP），这是因为 $S L P$ 的资料记录很长，在区域天气过程控制的区域 $S L P$ 是很适合的预报因子，而且研究发现 $S L P$ 与地面气候变量的关系是相对稳定的。其次位势高度场也是常用的预报因子，最通常应用的就是 $5 0 0 ~ \mathrm { { h P a } }$ 位势高度场，因为该层代表对流层中部的大气环流，以及等压面厚度场。海平面气压场反映的是大尺度环流因子， $7 0 0 \ \mathrm { { h P a } }$ 与$5 0 0 \ \mathrm { h P a }$ 的高度场本来反映的也是环流因子，但是二者的差值更能体现温度场因子变化特征[13-14]。因此将环流因子和温度因子结合起来，作为预报因子的变量场。预报因子包括：（1）国家气候中心T63月动力延伸预报模式资料，主要为1982—2015年1月和7月 $7 0 0 \ \mathrm { { h P a } } \ . 5 0 0 \ \mathrm { { h P a } }$ 高度场和海平面气压场。(2）NCEP/NCAR再分析资料1961—2015年700$\mathrm { { h P a } , 5 0 0 \ h P a }$ 高度场和海平面气压场。

# 1.2 统计降尺度方法介绍

本文采用 $E O F$ （经验正交函数)和逐步回归方法相结合的统计降尺度方法，利用地面观测资料建立大尺度气候预报因子与地面气温的统计关系。主要包括挑选预报因子、建立预报方程与预报性能检验三个主要步奏。

挑选因子：首先采用EOF对大尺度环流因子进行滤波和降维处理，目的是提取环流因子的主要特征，滤去噪声。 $7 0 0 \ \mathrm { { h P a } }$ 与 $5 0 0 \ \mathrm { { h P a } }$ 高度差场、SLP的NCEP和DERF资料在时间序列上联合后进行EOF分解，把所得的第一模态和第二模态的时间序列（累计方差 $> 8 5 \%$ )作为预报因子。

这里用两个预报因子海平面气压 $( X _ { 1 } )$ 和500$\mathrm { { h P a } }$ 与 $7 0 0 ~ \mathrm { { h P a } }$ 的高度差 $( X _ { 2 } )$ ，对两个预报因子分别进行分解：

$$
\begin{array} { r l } & { X _ { 1 } = P C _ { 1 } \cdot E O F _ { 1 } + N _ { 1 } } \\ & { } \\ & { X _ { 2 } = P C _ { 2 } \cdot E O F _ { 2 } + N _ { 2 } } \\ & { } \\ & { Y = A _ { 1 } \cdot P C _ { 1 } + A _ { 2 } \cdot P C _ { 2 } } \end{array}
$$

式中： $X _ { 1 } , X _ { 2 }$ 为预报因子; $P C _ { 1 } \lnot P C _ { 2 }$ 分别 $X _ { 1 }$ 和 $X _ { 2 }$ 主成分； $E O F _ { \mathrm { 1 } }$ 和 $E O F _ { 2 }$ 分别为 $X _ { 1 }$ 和 $X _ { 2 }$ 的空间函数； $N _ { 1 }$ 和 $N _ { 2 }$ 为噪声矩阵; $Y$ 为预报量,这里指气温。 $A _ { 1 } \setminus A _ { 2 }$ 为系数矩阵。 $P C$ 时间序列为 $2 3 \mathrm { ~ a ~ }$ ,其中 $1 \sim 2 2$ a为NCEP资料，第 $2 3 \mathrm { ~ a ~ }$ 为 $D E R F$ 资料，也是预测和检测

年份。

建立预报方程：几个因子同时被纳入方程，有的因子对方程贡献大，有的因子贡献小，对那些贡献小的因子可以逐步剔出。因此，本文采用了逐步回归方法来选择“最优”因子建立预报方程，此方法最适合不同月份和不同站点的预报对象来选择预报因子[12]。以96个县区的观测1月和7月气温为预报对象，与SLP和高度差的几个主分量采用逐步回归方法建立预报方程。

检验：本文采用交叉检验方法对统计降尺度模型进行检验。交叉检验针对每个月份每个站点分别进行，具体做法为：比如建立西安站的1983年1月份预测模型方程，从1961—1982年为1月份的NCEP资料,1983年为1月份的DERF预测资料，建立预报方程后计算出1983年1月气温的预测值，然后与西安站1983年1月的观测值对比。1984年1月预测模拟方程为1962—1983年为NCEP资料，1984年为DERF模式预测资料，建立预报方程后计算出1984年气温的预测值。以此类推，西安站要完成32 次建模，算出西安站1982—2013年的预测值，然后把全省96个县区中的每个县都完成32次建模和计算。最后将全省96个测站从1982—2015年1月和7月的预测值和观测值进行分段对比检验，对月动力延伸预测产品效果和统计降尺度方法的性能进行检验分析。

# 2EOF分解

EOF分解降低了数据的维数获得了大尺度气候主要模态。本文分别以1月 $H G T$ 高度差和7月$S L P$ 来举例说明,高度场取值区域为( $1 0 5 ^ { \circ } \sim 1 2 0 ^ { \circ } \mathrm { E }$ $2 5 ^ { \circ } \sim 4 5 ^ { \circ } \mathrm { N }$ ）。图1为1987—2010年E0F空间分析场，1987—2009年为NCEP资料，2010年为DERF资料，二者在时间序列上进行联合，可以检验DERF资料和NCEP资料的耦合性，1月份高度差场的前2个主分量的累积方差为 $8 9 . 5 \%$ 。从图1a中看到1月份的高度差场在空间上有较好的一致性，除陕北北部外，陕西省整体表现为较好增温或者降温为模态，这与陕北北部冬季1月份的强冷空气活动次数明显多于关中、陕南地区。对应的PC时间序列变化从1990年代末期开始逐渐减弱，高度差降低，意味着大背景气温是具有增加的趋势；7月份SLP的前2个主分量的累积方差为 $9 1 . 0 \%$ ，略高于HGT高度差，SLP在空间上也有较好的一致性，但是分布形态与HGT高度差有明显的不同，空间中心明显偏西偏北。对应的PC时间序列变化有明显的周期振荡，在2000年开始有降低的趋势。从20世纪90 年代以来，我国北方地区冬季增温明显大于夏季，从EOF分解的特征量来看，几个预报因子的变化与气温有着较好的对应关系。

![](images/0714703bc5ac6f1007da2a5978c2e84eb06fcec5508d3fe26a2c85a4a9abcef2.jpg)  
图11987—2010 年 E0F第一特征向量的空间分布图

![](images/a0d896615795d049aa3f848cdf8d56264acd4fd94d84e2d03568521ec8f62029.jpg)  
Fig.1First PC pattern of the two predictions from 1987 to 2010   
图21987—2010年E0F第一模态时间序列  
Fig.2First PC time series of the two predictions from 1987 to 2010

# 3统计降尺度方程性能检验

利用逐步回归方法对1982—2015年陕西省96个县区的1月份和7月份分别建立了33个预报方程,计算出对应的预测值。图3为神木县1982—2015年1月份的预测值和观测值距平对比分析图，得出预测值较好的预测出气温升高的趋势，但预测值明显小于实测值，且年际变化幅度也较实测值小,尤其是气温异常偏高和异常偏低时期，预测值很难预测出异常信号。华县1982—2015年7月份气温变化趋势不明显，但在2005年和2008年之间，华县观测值7月份气温出现了几年负距平，预测值较好的预测了这一小段气温的波动。

图4为1月份和7月份全省96个县区1982—2015年预测值和观测值对比分析图，1月份全省96个县区预测值和观测值距平符号一致率大于 $6 0 \%$ 达到了50个县区，陕北北部、关中和陕南南部的县区距平符号一致率都达到了 $70 \%$ 左右，其中神木县达到了 $78 \%$ 。7月份全省96个县区的预测值和观测值距平符号一致率大于 $6 0 \%$ 达到了60个，关中西部和陕南南部的符号一致率达到了 $7 5 \%$ 左右，陕南的佛坪县达到了 $9 0 \%$ 。7月份模拟效果明显好于1月份，可能是暖月气温变率小，变化幅度小，而冬季气温变率大，多冷空气活动，预测难度加大。

![](images/99300f7c0ec7e1981eb5d6053320aa7958d1b7b38d90df122f145191adbbf27f.jpg)  
Fig.3Temperature simulation values and observation comparative analysis from 1982 to 2013

![](images/21a842cd97fd841fbe1976e633c07f137fe823c0dfff93b405f8904618bb683d.jpg)  
图31982—2015年气温预测值与观测值对比分析  
图4陕西省96县1982—2015年气温预测值与观测值对比分析  
Fig.4Temperature simulation valuesandobservationcomparativeanalysisof96countyin ShaanxiProvincefrom1982 to201:

# 4结论

本文通过1982—2015年的观测资料，采用EOF与逐步回归相结合的统计降尺度方法建立了陕西

96个县区1月和7月平均气温的统计降尺度模型。通过分析可知，EOF作为获取大尺度气候主要模态的方法是可行的，海平面气压和高度差场作为预报因子，用交叉检验方法进一步验证了预测效果。结果表明：

（1）1月份全省96个县区，预测值和观测值距平符号一致率大于 $6 0 \%$ 达到了50 个县区，其中陕北北部、关中大部和陕南南部的测站距平符号一致

率都达到了 $70 \%$ 左右。

（2）7月份全省96个县区预测值和观测值距平符号一致率大于 $60 \%$ 达到了60个县，其中关中西部和陕南南部的符号一致率达到了 $7 5 \%$ 左右。（3）DERF资料是国家气候中心研发的月动力延伸预报产品，在经过统计降尺度方法，计算出陕西省96个县区的气温预测值，具有一定的可行性和可靠性。在上述的分析中，预测值较好的预测出气温升高的趋势，但预测值明显小于实测值，且年际变化幅度也较实测值小，尤其是气温异常偏高和异常偏低时期，预测值很难预测出异常信号。7月份预测效果要好于1月份，估计是夏季气温变率小,变化幅度小，比较稳定，而冬季气温变率大，多冷空气活动，预测难度加大。

# 参考文献(References)

[1］李维京,陈丽娟.动力延伸预报产品释用方法的研究[J].气象学报,1999,57（3）:338-345.［LIWeijing,CHENLijuan.Re-search on reexplanation and reanalysis method of dynamical ex-tended rang forecast products[J].Acta Meteorologica Sinica,1999,57(3) :338-345.]  
[2]陈丽娟,李维京,张培群,等.降尺度技术在月降水预报中的应用[J].应用气象学报，2003，14（6）：648-655.［CHENLi-juan,LI Weijing,ZHANG Peiqun,et al. Jingui.Application of anew downscaling model to monthly precipitation forecast[J].Jour-nal of Applied Meteorological Science,2003,14(6）:648-655.]  
[3］李维京,张培群,李清泉.动力气候模式预测系统业务化及其应用[J].应用气象学报,2005,16（增刊):1-11.[LIWeijing，ZHANG Peiqun,LI Qingquan.Research and operational applica-tion of dynamical climate model prediction system[J].Journal ofApplied Meteorological Science,2005,16(Supplement）:1-11.]  
[4]范丽军,符淙斌,陈德亮.统计降尺度法对未来区域气候变化情景预估的研究进展[J].地球科学进展.2005，20：320～329.[FANLijun,FUCongbin,CHENDeliang.Reviewon creating fu-ture climate change scenarios by statistical downscaling techniques[J].Advance in Earth Sciences.2005,20:320\~329.]  
[5］陈丽娟,李维京.月动力延伸预报产品的评估和解释应用[J].应用气象学报，1999，10（4）：486-490.[CHENLijuan，LIWei-jing.The score skill and interpretation of monthly dynamic extend-

ed rang forecast[J].Journal of Applied Meteorological Science,

1999,10(4) :486 -490.] [6]王世玉,钱永甫. $\mathrm { P } 2 \sigma$ 九层区域气候模式对东亚区域气候季节 与年际变化的模拟[J].大气科学,2003,27（5）：798－810. [WANG Shiyu,QIAN Yongfu. Seasonal and interannual variation simulation of the regional climate of east Asia by a nine-level P-o regional climate model[J]. Chinese Journal of Atmospheric Sciences,2003,27(5) :798-810.] [7］林纾,陈丽娟,陈彦山,等.月动力延伸预报产品在西北地区月 降水预测中的释用[J].应用气象学报,2007,18（4）：555-   
560.[LIN Shu,CHEN Lijuan,Chen Yanshan,et al. Interpretation of monthly dynamical extended range forecast products in northwest China[J].Journal of Applied Meteorological Science,2007,18 (4) :555 -560.] [8］严小冬,古书鸿.IEOF 法在 MDERF产品对贵州5月气温预测 释用中的应用[J].贵州气象,2008,32（3）:7-9.[YAN Xiaodong,Gu Shuhong.IEOF method in MDERF product to Guizhou in May temperature prediction with application［J]. Journal of Guizhou,2008,32(3):7-9.] [9］栗瑶,王红丽,刘健,等.黄河上游地区近千年气候变化的模拟 重建[J].干旱区地理,2013,36(6）:1023－1029.[LI Yao, WANG Hongli,LIU Jian,et al.Reconstruction of climate change over upper reaches of Yellow River Basin during Last Millennium [J].Arid Land Geography,2013,36(6）:1023-1029.] [10］黄金龙,陶辉,苏布达,等.塔里木河流域极端气候事件模拟与 RCP4.5情景下的预估研究[J].干旱区地理,2014,37（3）：490 -498.[HUANG Jinlong,TAO Hui,SU Buda,et al. Simulation of climate extreme events in the Tarim River Basin and projection under the RCP4.5 scenario[J].Arid Land Geography,2014,37(3）:   
490 -498.] [11］吴晶,罗毅,李佳.CMIP5 模式对中国西北干旱区模拟能力评 价[J].干旱区地理,2014,37（3）:499-508.[WU Jing,LUO Yi,LI Jia,et al.Evaluation of CMIP5 modes's smulation ability in the northwest arid areas of China[J].Arid Land Geography,2014,   
37(3):499 -508.] [12]WILBY R L,WIGLEY T ML. Downscaling general circulation model output:A review of methodsand limitations[J].Progress in Physical Geography,1997,21:530 -548. [13]HUTH R.Statistical downscaling of daily temperature in central Europe[J].JClimate,2002,15:1731-1742. [14]MO R,STRAUS D M. Statistical dynamical seasonal prediction based on principal component regression of GCM ensemble integrations[J].Monthly Weather Rev,2002,130(9）:2167-2187.

# Predictive analysis of monthly temperature in Shaanxi Province based on statistical downscaling method

WEI Na

(Shaanxi ClimateCenter,Xi'an71Oo15,Shaanxi,China)

Abstract:At present,general circulation models （GCMs）can represent the main features of the global atmospheric circulationreasonablywell,but theircapability inreproducing regionalscale climaticdetails isratherlimited owing to theirlow-resolution.As aresult,there isaneed todevelop toolsof downscaling GCM predictionsof climate change to regional andlocal scales.Statistical downscaling arethe main tools fordownscaling.Statistical downscaling method is to build relation between large-scale climate elements（atmospheric circulation index）and regional climate（temperature,precipitation).Then,this relationshipis tested by independentobservationdata.Finaly,thisrelationisapplied inthe large-scale climate model tooutput informationand predictthe change trend of regional climate.The dynamic extended range forecast（DERF）has good prediction capability which provided the monthly average of ensemble forecast.Many studies have been made to statistically downscale large scale climatic information to regional level in East China byuse of DERF's data.This paper focuses on the research of statistical downscaling method and its application over Shaanxi Province,China.Statistical downscaling method based on stepwise linear regressions andcommon empirical orthogonal functions（EOF）is applied in this paper.It has two predictors in this research.One is the monthly temperaturedata obtained at 96 observation stations in Januaryand July from 1982 to 2015,which is provided by Shaanxi Meteorological Administration.The other is climatic predictors which are derived from the NCEP/NCAR reanalysis data in Januaryand Julyfrom 1961to 2O15,andthe dynamic extended range forecast（DERF）product from National Climate Centerof China wereapplied to predict temperature byusing the forecast model and compared withthe observed temperature.It is built prediction model between the large scale climate predictor and the observed temperature byuseof statistical downscaling.The main results of this research can be summarized inthe follwing items:EOFas forlarge scale climate main modal methodand sea level pressure and altitude difference fieldaspredictors are feasible;In January,theconsistent anomalysymbolrateof simulated values and observed values greater than $60 \%$ reached 5O counties of the province's 96 counties,and the rate of most of the northern Shanbei,Guanzhong and the southern Shannan has reached $70 \%$ or so.In July,the consistent anomaly symbol rate of simulated values and observed values greater than $60 \%$ reached 6O counties of the province's 96 counties,and the symbol rate of Western Guanzhong and the southern Shannan reached $7 5 \%$ or so.

Key words: monthly temperature；statistical downscaling；climate change；prediction model