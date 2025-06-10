# 生产过程中人的极限工作时间研究

崔铁军1,²，李莎莎1

(1.安全科学与工程学院，辽宁工程技术大学，辽宁 阜新 123000;2 大连交通大学 辽宁省隧道与地下结构工程技术研究中心，辽宁 大连 116028)

摘要：操作工人在长时间的工作过程中，由于精神和身体的疲劳会产生失误，人的可靠性降低，导致生产残次品，甚至危及人身安全。为了了解在保证可靠性的前提下，操作者最长可持续的工作时间(极限工作时间)，提出了一种结合统计过程控制图(statistical process control chart，SPCC)和差分自回归移动平均模型(autoregressive integrated movingaverage model，ARIMA)的方法来进行确定。用连续时间中单位时间间隔内的次品率衡量人的可靠度，并形成次品率时序序列(defectiveratetime series,DRTS)。一方面使用该数列基于ARIMA 构建 SPCC，并确定样本的上控制线(up controlline,UCL)、下控制线(lowcontrolline,LCL)和极限时间范围;另一方面使用ARIMA和支持向量机(support vector machine,SVM)配合实时跟踪算法(realtime tracing algorithm，RTA)对需要确定极限工作时间(limit working time，LWT)的某一操作者的 DRTS 进行预测。最后将预测曲线置于SPCC中来确定该操作者LWT的范围。通过对 10个操作者8小时，每隔10分钟采样得到的DRTS 分析，表明该类工作参数的范围为UCL=[3.89，4.66]、LCL=[-4.98，-3.90]、LWT=[393，450]min。确定了一个新操作者的LWT为[435，452]min，即 $4 3 5 \mathrm { m i n }$ 时该操作者就应该停止工作进行休息。

关键词：人的可靠性；差分自回归移动平均模型；统计过程控制图；极限工作时间中图分类号：X913.4 doi:10.3969/j.issn.1001-3695.2017.12.0852

# Study on determine limit working time of human in production process

Cui Tiejun1,2, Li Shashal (1 College of Safety Science& Engineering Liaoning Technical University，Fuxin Liaoning1230o China;2Tunnel& Underground Structure Engineering Center ofLiaoning,Dalian Jiaotong University,Dalian Liaoning l16028 China)

Abstract: In the process of long work hours,operators can produce erors due to mentaland physical exhaustion,human reliabilityisreduced,anditleadstoproductioof incompleteandevenendangershumanal safety.Inordertounderstand operator'slongestsustainable working timeonthe premise of givenreliability,amethodofcombining SPCCandARIMA is put forward.Withunit time interval defectrateinthecontinuous time to measure threliabilityofhuman,andformadefectiverate time series.Ontheonehand,the SPCCis built using DRTS basedon ARIMAto determine the sampleofUCL,LCLnd LWT range.On the other hand,the DRTSofan operator is predicted using ARIMAand SVM with RTA.Finally the prediction curve is put into the SPCC to determine theLWTrange.Basedon 8 hours,10operators DRTSanalysis of sampling for every10 minutes,indicates that the scope of this kind of working parameters for the $\mathrm { U C L } = [ 3 . 8 9 , 4 . 6 6 ] , \mathrm { L C L } = [ 4 . 9 8 , 3 . 9 0 ] , \mathrm { L W T } =$ [393450].Identified anewoperatorLWTis [435452] minutes,435 minutes when the operator should stop working to havea rest.

Key words: reliability of the human; ARIMA; SPCC; limit Working time

# 0 引言

我国是一个劳动力大国，在高度机械化和自动化的今天，仍有大量的劳动者从事着以人为主要动力来源的劳动。人与机器相比有着丰富的创造能力，但同时人在长时间的劳动过程中会在生理和心里方面产生疲劳。在疲劳状态下工作的操作人员，心情烦躁，注意力难以集中，不但工作效率低下，而且会生产较多残次品。这样会加重操作人员的心里压力，使人的行为更加不可靠，甚至会由于操作不当造成人身伤亡。所以，确定一个适当的工作时间，不仅能提高操作者的效率，而且能提高产品的合格率。一方面保护了劳动者，另一方面也增加了企业的经济效益。即在保证操作人员操作可靠性不小于某个特定值的前提下，确定操作者可以工作的最长时间，即极限工作时间(LWT)。

关于人的可靠性及适合的工作时间的研究，目前有柴松等人[1,2]的基于CREAM和不确定推理的人因可靠性分析方法和海洋工程人因可靠性定量分析方法与应用；董学军等[3]的基于补偿和不可替代因素合成的人因可靠性分析方法；蒋建军等人[4.5]的基于隐马尔可夫的核电厂半数字化人-机界面事故诊断过程人因可靠性模型和考虑人因的核电厂主控室认知可靠性模型研究；倪蓉的煤矿职工疲劳度相关因素分析与控制研究。

笔者参考了文献[7\~9]，并根据自已的经验[10\~14]，提出了基于SPCC和ARIMA的人的LWT的确定方法。该方法主要分为两部分，一部分是构造 SPCC 并得到LCL、UCL、中心线(centerline，CL)和极限时间范围，这部分的数据来源是多个样本（操作者）的统计数据；另一部分使用ARIMA，配合SVM和RTA预测某一个新样本在工作时间不足的情况下后继时间序列的变化，进而形成该新样本的DRTS，结合得到的SPCC可预测该样本的LWT。

# 1 方法论

该方法涉及到的相关知识有SPCC、ARIMA，SVM和RTA。算法作用有两个，一是统计多个样本（操作者）确定某种操作的泛化LCL、UCL、CL 和LWT；二是基于这些统计结果预测某个个体（操作者）的LWT。SPCC对多个样本统计数据进行整理，得到数据的LCL、UCL、CL和LWT。可得数据变化趋势是否将超限，从而可根据统计数据的特征，预测同类型数据是否有超限的可能，形成SPCC图是衡量标尺。ARIMA是算法核心，SPCC处理时间序列。ARIMA在形成SPCC时适用于无相关性的时间序列数据。为了预测新操作者的LWT，需要对短时间内的新操作者的DRTS进行分析，并对未来的序列数据进行预测。但DRTS很可能是线性和非线性的序列数据叠加的，根据文献[9]可将线性数据使用ARIMA进行预测，非线性数据使用SVM预测。根据文献[8]可使用RTA对时序数据进行跟踪，以保证预测的精确性。经过上述处理的线性和非线性时序数据相叠加形成最终的该操作者的DRTS数据，放入SPCC图中，即可确定他的LWT。算法流程如图1所示。

![](images/cb4bca21bc9a3f466921042554a9c746eff28de8cb63ff7ccf46b49d796f881f.jpg)  
图1算法的流程图

从图1可知算法分为左右两部分用粗虚线分开。左边为时序数据的预测部分，右面为SPCC图构造部分。最右侧的ARIMA处理模块包括了三个部分，左右两部分都要用到所以独立开来。右侧形成SPCC图，是来源于多个样本的统计结果，是整个算法的基础。SPCC可得到LCL、UCL、CL和LWT，进而处理单个样本的LWT预测。左侧为预测单个样本DRTS数据，在SPCC中与LCL和UCL比较，最终确定LWT。

# 2 方法步骤及其解释

SPCC对实时数据进行监控和预测。SPCC基于ARIMA与传统的 SPCC 是不同的[15,16]。SPCC 构造过程分三步：相关性评价；ARIMA构建；控制图构建。自相关函数(autocorrelationcoefficientfunction，ACF)在第一步中，用来评价时间序列的自相关性。如果不相关直接执行第三步，用原始时间序列构建控制图。否则用ARIMA消除相关性，在第二步产生时间序列的非相关残差。第三步用时间序列残差构建控制图。

# 2.1相关性估计

使用ACF估计相关性。设滞后时间间隔为k，使用MATLAB中的autocorr 计算相关性。如果ACF图显示的数值绝对值总体趋势减小，则断定时间序列是相关[17]。

# 2.2 ARIMA 构建

如果数据是相关的，那么使用ARIMA消除来消除相关性。ARIMA 模型可表示为ARIMA(p,d,q)，其中 $\mathrm { p , d , q }$ 为大于等于0的整数，p为自回归项；d为时间序列成为平稳时所做的差分次数；q为移动平均项数。给定ARIMA(p,d,q)，原时间序列 $x _ { t }$ 可被拟合并转换为一个白噪声过程 $\boldsymbol { e } _ { t }$ ，之间的关系如式（1）所示[7]。

$$
\left( 1 - \sum _ { p = 1 } ^ { p } \varphi _ { p } B ^ { p } \right) ( 1 - B ) ^ { d } x _ { t } = ( 1 + \sum _ { q = 1 } ^ { q } \varphi _ { q } B ^ { q } ) e _ { t }
$$

其中： $\varphi _ { p }$ 和 $\varphi _ { _ q }$ 自回归系数和移动平均系数，B 延迟算子，$B ^ { j } x _ { t } = x _ { t - j }$ ， $j$ 为延迟次数。

ARIMA的构造分三个步骤，即识别规则，参数估计和模型检验[18]。

a)在识别规则中，使用逐次差分将时间序列转换为稳定数据，一次和二次差分公式分别如式(2)(3)所示[7]。

$$
( 1 - B ) x _ { t } = x _ { t } - x _ { t - 1 }
$$

$$
( 1 - B ) ^ { 2 } x _ { t } = ( 1 - 2 B + B ^ { 2 } ) x _ { t } = x _ { t } - 2 x _ { t - 1 } + x _ { t - 2 }
$$

ACF和偏自相关函数(partial autocorrelationcoefficientfunction，PACF)可绘制出各种差分时间序列的对应曲线。如果其他参数不变，差分次数d的变化对ACF和PACF形成的图形影响较小[19]。具体来说，ACF 图像拖尾和PACF 延迟 $\mathfrak { p }$ 后截尾时应使用ARIMA，具体方法见文献[19]。

b)使用最大化条件对数似然函数 $l _ { * } ( \varphi _ { p } , \theta _ { q } , \mathcal { S } _ { e _ { t } } ^ { 2 } )$ 进行估计，如式(4)所示[7]。

$$
l _ { * } ( \varphi _ { p } , \theta _ { q } , \mathcal { S } _ { e _ { t } } ^ { 2 } ) = - \frac { n } { 2 } \mathrm { l n } ( \delta _ { e _ { t } } ^ { 2 } ) - \frac { S _ { * } ( \varphi _ { p } , \theta _ { q } ) } { 2 \delta _ { e _ { t } } ^ { 2 } }
$$

其中： $\delta _ { e _ { t } } ^ { 2 }$ 是 $\boldsymbol { e } _ { t }$ 的方差； $S _ { * } ( \varphi _ { p } , \theta _ { q } )$ 通过式(5)进行估计。

$$
S _ { * } ( \varphi _ { p } , \theta _ { q } ) = \sum _ { T = 1 } ^ { n } e _ { t } ^ { 2 } ( \varphi _ { p } , \theta _ { q } \mid ( 1 - B ) x _ { t _ { * } } , e _ { t _ { * } } , ( 1 - B ) x _ { t } \ )
$$

如果，ARIMA(p,d,q)中 $p \neq 0 , q \neq 0$ ，通过最小艾卡信息量准则(lowest Akaike information criterion，AIC)进行定阶[20]，其具体表达式如式(6)所示。

$$
A I C ( t , j ) = \ln ( \delta _ { e _ { t , j } } ^ { 2 } ) + \frac { 2 ( t + j ) } { N }
$$

其中： $\delta _ { e _ { t , j } } ^ { 2 }$ 是 $\boldsymbol { e } _ { t }$ 的方差的估计值， $\mathrm { ~  ~ N ~ }$ 为样本数。

c)检验时间序列的相关性是否消除。使用 ACF 对白噪声 $\boldsymbol { e } _ { t }$ 进行分析可进行验证。当延迟 $j$ 大于10，且ACF的分析结果趋近于0时可认为相关性已被消除[2I]。否则重复进行ARIMA处理，直到满足上述条件。

d)利用RTA改进ARIMA[8]。在ARIMA基础上提出与实时跟踪算法 RTA 结合的改进模型。假设要对时间序列 $\{ x _ { i } | i = 1 \colon t \}$ 进行预测，假设步长为 $\mathrm { ~ m ~ }$ ，利用 $\{ x _ { i } | i = 1 \colon t \}$ 预测$\{ x _ { i } | i = t + 1 { : } t + m \}$ ，去掉 $\{ x _ { i } | i = 1 \colon t + m \}$ 的前 $m$ 个数据，形成{x|i=m+1:t+m}进行下一步的时序数列预测。

e)ARIMA和SVM模型分别在处理线性和非线性数据结构的预测问题时有着各自的优势。可将ARIMA和SVM结合使用，以求达到增强预测模型对数据样本的适应能力，从而提高预测的效果[9]。

# 2.3 控制图构建

构建休哈特统计控制过程图(Shewhart statistical processcontrol chart,SSPCC),基于 Shewhart three sigma control theory[22]来确定中心线CL。历史数据可为无相关性的原时间序列 $x _ { t }$ 或

ARIMA 处理后的白噪声过程 $\boldsymbol { e } _ { t }$ 。 $\alpha _ { i }$ 为在时间点 $i$ 处的历史数据。控制上线UCL、控制下线LCL和中心线CL如式（7）所示。

$$
U C L / L C L = 2 C L = \bar { X } \pm 3 \sigma = \overline { { X } } \pm 3 \frac { \overline { { m r } } } { d _ { n } }
$$

其中： $\ { \bar { X } } = { \frac { \displaystyle \sum _ { i = 1 } ^ { T } \sigma _ { i } } { T } }$ ∑δ，T为时间序列长度的平均值。m表示平均移动范围， $\overline { { m r } } = \frac { \displaystyle \sum _ { i = 2 } ^ { T } m r _ { i } } { T - 1 }$ ∑mri，其中 mr =α -αi-1 °

SSPCC使用时间序列中两个连续值作为移动范围[22]，所以$n { = } 2$ $, d _ { 2 } = 1 . 1 2 8 \ ^ { [ 2 3 ] } \mathrm { { c } }$

# 3 实例计算

在流水线上的操作人员往往由于工作时间长而产生疲劳，导致生产的部件残次品增多，甚至可能由于操作不当对自身安全遭威胁。监测10个工人在8小时内的生产残次品比例（次品率）作为衡量操作人员操作可靠性指标。取样时间间隔为10 分钟，次品率为10分钟内生产的残次零件/全部零件。构成了有48 个数据点的10个样本时序序列数据。根据次品率统计，在8 小时内的10个工人的次品率在0\~0.2，曲线是起伏的，但总趋势递增。所以采用一阶差分对时序序列进行处理。由于一阶差分、ACF、PACF在MATLAB中已有工具包，这里不在说明。给出10个样本中第一个样本的数据处理过程的图示，如图2所示。

![](images/1430467e1117688eb76059f7cf83c8ca2fa35b4d40e415d51c1497b74f68af3c.jpg)  
图2第一个样本的数据处理过程图

图2中，(a)表示了该操作者(第一个样本)的DRTS数据，一共48个采样点，480分钟的工作时间。根据次品率定义，可知DRTS数据是起伏波动的，随时间增加总体增加的趋势。由图(c)和(f)可见，大部分数据的ACF和PACF值都超出允许范围，时间序列的平稳性不满足计算要求，需要进行差分计算。通过差分计算的一次差分序列、ACF和PACF分别如图(b)(d)和(e)可见一次差分序列值趋于稳定，ARIMA 模型中的系数 $d$ 定为1。然后利用AIC来确定ARIMA模型的阶数 $p$ 和 $q$ 。通过计算发现当 $\scriptstyle p = 4 , q = 4$ 时 AIC 值最小,故使用模型 ARIMA(4,1,4)。第一个操作工人的差分DRTS的 SPCC如图3所示。

![](images/d026c5e4f06b3c5bebcfad0d9f956fbe134c93dabea8998f96b04b224fe6df6c.jpg)  
图3第一个操作工人的差分次品率时序序列的SPCC

从图3可知第一个操作工人的 $\mathrm { C L = } 0$ 、 $\mathrm { U C L } { = } 4 . 1 7$ 、LCL=-4.17。差分DRTS曲线与UCL交于采样点43\~44，即在430\~440min 该操作人员达到限值，不适宜继续工作。则LWT范围就是$4 3 0 { \sim } 4 4 0 \operatorname * { m i n }$ （ $\mathrm { L W L } { = } 4 3 7 \mathrm { m i n }$ )。同理确定10个操作人员的LWT如表1所示。将表1中参数的值进行综合得到了该类工作的对应参数的范围，即 $\mathrm { U C L = } [ 3 . 8 9 , 4 . 6 6 ]$ 、LCL=[-4.98,-3.90]、LWT=[393,450] min。

表110个操作人员的极限工作时间  

<html><body><table><tr><td>指标</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td><td>范围</td></tr><tr><td>UCL</td><td>4.17</td><td>4.08</td><td>3.89</td><td>5.11</td><td>4.66</td><td>4.54</td><td>3.90</td><td>4.43</td><td>3.68</td><td>3.99</td><td>[3.89,4.66]</td></tr><tr><td>LCL</td><td></td><td>-4.17 -4.08</td><td>-4.03</td><td>-4.98</td><td>-4.66</td><td></td><td>-4.34 -3.90 -4.33</td><td></td><td>-4.09</td><td>-4.18</td><td>[-4.98,-3.90]</td></tr><tr><td>CL</td><td>0</td><td>0</td><td></td><td>-0.07 0.065</td><td>0</td><td>0.1</td><td>0</td><td>0.05</td><td>-0.205 -0.095</td><td></td><td></td></tr><tr><td>LWT/分</td><td>437</td><td>404</td><td>401</td><td>450</td><td>422</td><td>430</td><td>393</td><td>425</td><td>397</td><td>406</td><td>[393,450]</td></tr></table></body></html>

注：范围确定是取10个样本对应值的最大和最小值,作为区间的两个端点。

上述过程完成了图1中右侧框图部分，即完成了SPCC的构建。下面是判断某一新样本（新操作者）的LWT。

对于一个新操作者（不在样本的10个操作者内)，利用以进行工作时间的DRTS的一次差分序列对该操作者进行LWT预测。利用文献[8.9]的方法进行时序序列的拟合和预测，得到了较好的预测结果。主要思想是将原始时序序列拆分为线性序列和非线性序列，线性序列由ARIMA处理并进行预测，处理过程与上述过程相近，见参考文献[8；非线性序列可由SVM处理并进行预测，见参考文献9。同时在处理过程中结合RTA方法进行数据跟踪，提高预测精度。最后将上述线性和非线性序列进行叠加，达到对原DRTS数据预测的效果。实际值与预测值的残差如图4所示。预测误差为 $2 . 4 5 9 \%$ 。该操作者的实际DRTS数据曲线和预测曲线如图5所示。

在图5中，底纹区域UCL和LCL是通过原始10个样本确定的。使用预测方法对该操作者的DRTS预测较为成功（误差为 $2 . 4 5 9 \%$ )。而且使用预测曲线结合以得到的UCL和LCL区域可确定该操作者的LWT。如图中的竖向底纹区域，该区域的水平方向区间宽度是由DRTS的预测曲线与UCL相交的区域宽度确定的。对于该操作者的LWT为[435,452]分钟，即435分钟时该操作者就应该停止工作进行休息。

![](images/cc328a349b651e31334e7d63d8dfa4f9fe0ccbdd2c6846b6e04bc0b8b823791d.jpg)  
图4次品率时序序列数据差分拟合的残差

![](images/95247679f0038dbd769e06697b40e3372cc7cf4a94b7c29ae94d48f7a218f0bb.jpg)  
图5该操作者的LWT分析图

# 4 结束语

a）提出了极限工作时间确定方法。分为两部分，一是构造SPCC并得到LCL、UCL、CL和极限时间范围，数据来源是多个样本（操作者）的统计；二是使用ARIMA，配合SVM和RTA预测某一个新样本在工作时间不足的情况下后继时间序列的变化，进而形成该新样本的DRTS。结合得到的SPCC可预测该样本的LWT。

b）基于10 个样本形成了 SPCC。使用模型 ARIMA(4,1,4)进行 SPCC 构建。得到了10 个样本（操作者）的UCL、LCL、CL 和LWT。综合得到了该类工作的对应参数范围，即UCL=[3.89,4.66]、LCL=[-4.98,-3.90]、LWT $\mathbf { \bar { \rho } } = \mathbf { \rho }$ [393,450] min。

c）确定了新样本（新操作者）的极限工作时间。预测误差为 $2 . 4 5 9 \%$ ，确定了该操作者的LWT为[435,452]min，即435min 时该操作者就应该停止工作进行休息。

# 参考文献：

[1]柴松，余建星，马维林，等．基于CREAM和不确定推理的人因可靠 性分析方法 [J].天津大学学报,2012,45(11):958-962.   
[2]柴松，余建星，杜尊峰，等.海洋工程人因可靠性定量分析方法与应用 [J].天津大学学报,2011,44(10):914-919.   
[3]董学军，陈英武．基于补偿和不可替代因素合成的人因可靠性分析方 法[J]．系统工程理论与实践,2012,32(9):2087-2096.   
[4]蒋建军，张力，王以群，等．基于隐马尔可夫的核电厂半数字化人-机 界面事故诊断过程人因可靠性模型[J].核动力工程,2012,33(5):79- 82.   
[5] 蒋建军，张力，王以群，等.考虑人因的核电厂主控室认知可靠性模型 研究[J].核动力工程,2012,33(1):66-72.   
[6]倪蓉．煤矿职工疲劳度相关因素分析与控制研究[J].煤矿安全,2013, 44 (10): 230-233.   
[7]Hu Xinyao,Qu Xingda.An individual-specific fall detection model based on the statistical process control chart [J]. Safety Science 2014,64:13-21.   
[8]秦摇鹏，苏怀智，沈跃军．基于ARIMA-RTA 组合模型的海堤工程沉降 预测[J]．水利水运工程学报,2013,5:66-70.   
[9]黄彬彬，谷波，任能．基于 ARIMA-SVM 模型的翅片管蒸发器结霜性 能预测[J].上海交通大学学报,2009,43(10):1622-1631.   
[10]崔铁军，马云东．基于泛函网络的周期来压预测方法研究[J].计算机 科学,2013,40 (6A): 242-246.   
[11] Cui Tiejun,Li Shasha.Study on the relationship between system reliability and influencing factors under big data and multi-factors [J].Cluster Computing-The Journal of Networks Software Tools and Applications, https://doi.org/10.1007/s10586-017-1278-5.   
[12] Li Shasha,Cui Tiejun,Li Xingsen,et al. Construction of cloud space fault tree and its application of fault data uncertainty analysis [C]// Proc of International Conference on Machine Learning and Cybernetics.2O17:195- 201.   
[13]Li Shasha, Cui Tiejun,Liu Jian. Study on the construction and application of cloudization space fault tree [J].Cluster Computing: The Journal of NetworksSoftwareToolsandApplications, htps://doi.org/10. 1007/s10586-017-1398-y   
[14]崔铁军，马云东．多维空间故障树构建及应用研究[J].中国安全科学 学报，2013,23(4):32-37.   
[15] Alwan LC,Roberts H V.Time-series modeling for statistical process control [J]. Journal of Business and Economic Statistics,1988,6(1): 87-95.   
[16] Haridy S,Wu Z. Univariate and multivariate control charts for monitoring dynamic-behavior processes:a case study [J].Journal of Industrial Engineering and Management,2009,2(3): 464-498.   
[17]Mohammed MA,Worthington P,Woodall WH.Plotting basic control charts: tutorial notes for healthcare practitioners [J].Quality and Safety in HealthCare,2009,17(2):137-145.   
[18] Box G EP,Jenkins G M.1976.Time series analysis: forecasting and control [M].5th ed.Hoboken: Wiley,2015.   
[19] Montgomery D C,Jennings C L，Kulahci M. Introduction to time seriesanalysis and forecasting [M].2nd ed.Hoboken:Wiley-Interscience, 2015.   
[20]何林，欧进萍．基于ARMAX 模型及MA 参数修正的框架结构动态参 数识别[J].振动工程学报,2002,15(1):47-51.   
[21] Nau R. Introduction to ARIMA: non-seasonal models [EB/OL]. (2014-11- 29). https://people.duke.edu/\~rnau/Slides_on_ARIMA_models-Robert_ Nau.pdf.   
[22] Shewhart,W.A.，1931.Economic Control of Quality of Manufactured Product [M].D.VanNostrand Company Inc.,New York.   
[23]Montgomery D C.Introduction to statistical quality control [M]. 6th ed. Hoboken: Wiley,2009.