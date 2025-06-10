# 天马 $1 3 \textbf { m }$ 射电望远镜高精度指向模型的建立

孙正雄¹，王锦清1²，虞林峰¹，蒋涌斌’赵融冰¹，苟伟¹,王广利1,3（1.中国科学院上海天文台，上海 200030;2.中国科学院射电天文重点实验室，南京210008;

# 3.中国科学院大学，北京100094）

摘要：天马 $1 3 \mathrm { ~ m ~ }$ 射电望远镜是新一代专为空间大地测量的VLBI天线，即所谓的VGOS系统。VGOS 观测将从调度、相关、观测策略到分析各个方面改变VLBI。与传统测地观测相比，VGOS观测将数据提高1-2个数量级。天马 $1 3 \mathrm { ~ m ~ }$ 天线安装有3～15Ghz宽频制冷接收机，一般要求天线指向偏差小于最高频率波束宽度的1/10。为了满足高精度指向要求，本文详细介绍了指向建立的方法和天线控制扫描策略，给出了系统误差修正模型的完全表达式，明确了指向修正模型中的参数意义。基于该天线指向扫描的实测数据，实测评估了该望远镜的指向精度。采用最小二乘法对覆盖全天区的数据样本进行拟合，得到天马 $1 3 \mathrm { m }$ 射电望远镜指向模型，并加载到天线伺服控制系统中进行验证，得到了好于10"的的盲指误差。

关键字：射电望远镜，数据分析，系统误差，指向改正模型中图分类号：P11

# 1．概述

射电望远镜的指向精度是天线的一个重要的性能指标，指向好坏直接决定了天线是否能接收到射电源的信号，以及接受到信号的信噪比。当天线指向偏离观测频率波束宽度的1/10时，天线效率将损失约 $2 . 7 \%$ ，若偏离波束宽度的1/5时，天线效率将损失约 $1 0 . 5 \% ^ { [ 1 ] }$ 。所以，一般对天线的指向要求是偏差小于1/10 测频率的波束宽度。对于天马 $1 3 \mathrm { m }$ 射电望远镜观测频率为15Ghz时，天线的指向偏差应该小于 $3 0 "$ 。然而，本文研究的指向建模结果要远远好于这个指标。当前射电望远镜普遍采用指向模型校准天线指向偏差：对全天区均匀分布的致密的强射电源进行扫描观测，求出观测目标源的位置与在理论上计算的指向附件扫描获得的最大接收功率值之间的偏差，利用天线指向模型修正公式，通过平差计算出模型参数，然后将模型参数带入天线伺服控制系统，便可在天线跟踪射电源时，实时修正指向偏向。天线指向修正是一个迭代的过程，尤其是对新建的天线[3,41]。一般先扫描角径比较大的射电源来修正比较大的误差项（编码器固有误差），然后对强的校准源进行观测扫基金项目：国家自然科学基金(11903068,11873015)资助.

作者简介：孙正雄，男，硕士.研究方向：VLBI 技术、天文技术与方法.Email: zxsun@shao.ac.cn描迭代模型验证，保证天线指向盲指精度满足观测要求。图1为建立指向模型流程框图。在测试指向偏差时，根据目标源在天区的分布以及天线在该时刻对准目标源的方位俯仰角度来定制指向纲要文件。天线伺服系统根据纲要文件对目标源进行扫描观测，同时记录下天线的状态信息。分析观测数据，建立指向模型，将模型参数带入天线伺服控制系统。

Antenna Receiver signa1 1F Powermeter/ Computer   
Antend point ing Powerlog file ynrngt1 NTP synchronization 业   
Antenna servo Antenna log Preprocessing   
controlsystem information pointingdata ↑ Pointingmodel paraneter Pointinglog file Point to Modeling Point Eo AnalysisSoftware outlinefile Customizedobservationpan

# 2.指向扫描策略

常用检测和标定射电望远镜指向的方法为扫描河外射电源法和扫描人造卫星法。首先通过天文观测软件计算出给定时间目标校准源的引导值（如地平式的方位角、俯仰角），控制射电望远镜在目标源理论指向位置附近进行方位和俯仰扫描，对功率计接收到的辐射强度进行高斯函数拟合，确定辐射强度最大处的天线指向，进而得到引导指向和实测指向之间的差值，以此差值修正指向误差。人造卫星法测量指向偏差时候，信号的信噪比高，对于装备了制冷接收机天线很容易造成信号接收链路饱和，且天区覆盖差。因此，我们一般采用扫描河外射电源法实现射电望远镜指向在全天区的标定[5]。

典型的指向扫描方式为十字扫描，在早期天线扫描时的具体实施过程为：首先计算出目标源在当前时刻的方位角和俯仰角的位置值，并引导天线指向该位置0 $\mathrm { ~ \ : ~ } , \mathrm { ~ A ~ z ~ } _ { 0 } , \mathrm { ~ E ~ l ~ } _ { 0 }$ ）；然后在方位角偏开一个角度 $a$ ，引导天线方位角在 $\mathrm { A } z _ { \mathrm { 0 } } - \alpha$ 到 $\mathrm { A } \mathrm { Z } _ { 0 } + \alpha$ 范围内扫描，俯仰角以同样的方式进行扫描。由于地球自转的影响，该扫描方式的误差很大。目前天马 $1 3 \mathrm { m }$ 射电望远镜在做指向测试时，可以根据目标源的特点，软件设定单点扫描的时间和宽度。在发送引导指令时，软件实时计算目标源的位置值。比如方位扫描射电源3C144，一个单点扫描的宽度为0.8度，时间为60s，天线控制计算机与天线伺服控制单元的通讯频率为0.5s，即天线每间隔0.5s接收一次引导值驱动天线指向引导值。所以一个单点扫描驱动天线120次指向引导值。然而这120次引导值为：发送指令时刻目标源的方位角或俯仰角加上一个范围在-0.4至0.4，且长度为120的等比数列中的第i个元素，i表示第i次发送引导值，在方位方向发送指令需要除以目标源俯仰角的余弦函数[6]。

图2表示两种扫描策略中，天线指向目标源在一个单点扫描时天线俯仰角的实际值，假设天线系统没有延迟，且指向没有偏差，即引导值和实际值相等。图中横轴表示天线伺服控制单元发送指令的次数，纵轴表示天线俯仰角的实际值。其中“e1Obs”表示在这个单点扫描过程中目标源的俯仰角变化；“e1Ind1”表示上文所说的早期天线扫描时，一个单点扫描天线俯仰角的变化；“e1Ind2”表示目前普遍采用十字扫描法，一个单点扫描天线俯仰角的变化。一次60s的指向扫描，在第30s时（指令发送的第60次）天线可以指向目标射电源。然而早期的扫描在第40s时指向目标源，相当于台站控制系统与时间服务器相差了10s。显然这种指向扫描建模方式误差会很大。

在实际天线控制过程中，天线引导值指令发送给ACU驱动天线转动。在这之间是有系统延迟的，且电机驱动天线转动也有滞后。目前天马 $1 3 \mathrm { m }$ 射电望远镜指向建模采用的扫描方式为：引导天线分别以方位增加（ $\mathrm { A } \mathrm { z ^ { + } }$ ）、方位减少 $( \mathtt { A z ^ { - } } )$ 、俯仰增加 $\left( \operatorname { E } 1 + \right)$ 、俯仰减少 (E1-)共4个单点扫描作为对目标源的一次扫描，其中方位偏开扫描时俯仰实时跟踪，同理俯仰偏开扫描时方位实时跟踪。台站log文件记录扫描过程中的天线引导值、实际值和天线接收信号的测量功率值。图3是天马 $1 3 \mathrm { m }$ 天线在指向扫描过程中俯仰角的运动轨迹。其中‘ $\mathrm { \bf ~ \tilde { \tau } e l + I n d \Sigma ^ { \prime \prime } }$ 表示天线 $\operatorname { E } 1 +$ 扫描时天线俯仰角的实际值， $^ { 6 4 } \mathrm { e l } + 0 \mathrm { b s } ^ { \prime \prime }$ 表示天线 $\operatorname { E } 1 +$ 扫描时目标源的俯仰角的值；“e1-Ind”表示天线E1-扫描时天线俯仰角的实际值， $^ { 6 6 } \mathrm { e l - \ 0 b s ^ { \prime \prime } }$ 表示天线E1-扫描时目标源的俯仰角的值。假设天线是没有指向偏差的，从天线扫描轨迹上分析误差的来源，在一次60秒的指向 $\operatorname { E l } +$ 扫描过程中，在第30s时（指令发送的第60次）天线俯仰应该是指向目标源的，然而实际轨迹显示俯仰角偏小，EL-扫描时俯仰角偏大。在采用同样的方式对方位扫描时， $\mathrm { A z ^ { + } }$ 实际轨迹显示方位角偏小， $\mathrm { A z ^ { - } }$ 扫描时方位角偏大。这种误差是由于系统延迟造成的，所以在指向数据分析过程中，天马 $1 3 \mathrm { m }$ 射电望远镜在指向一个位置的偏差是取正反扫描的平均值。后文指向数据分析的实测数据也验证了这个问题。

![](images/979977f15631aa019dd31e2656f89eb48182a16e0c6baff7c15b69e4d1ce8be6.jpg)  
图2.天线2种指向扫描方式的俯仰角变化 Fig.2 Variation of the elevation of the antenna in two pointing scanning modes.

![](images/f98e0cb696d615c28808dbaacdef7f78ea683fff9692ce2309ffe494016aa35a.jpg)  
图 $3 . \ { \mathsf { e l } } + { \mathsf { , e l } } -$ 指向扫描天线俯仰角转动范围. Fig.3 The range of antenna elevation rotation for $^ { \mathrm { E l + } }$ 、El- pointing scan.

# 3.指向数据分析

天马 $1 3 \mathrm { m }$ 射电望远镜在做指向测量时，会记录扫描过程中天线方位角和俯仰角的引导值，以及当前时刻天线方位角和俯仰角的实际值和天线接收信号的功率值。经过数据分析、得到各个指向位置实际指向和引导指向的差值，并对全天区收集指向样本解算出天线的指向模型，同时定标指向精度。

天线对河外射电源的辐射的响应为天线方向图和射电源亮温分布的卷积，实时测量的功率值为该卷积在空间的采样。理想情况下，一个单点扫描的实测功率值为高斯分布。但是因为天线控制、采样、重力变形等一些不确定性因素的影响，实际测量功率值曲线存在附件噪声和扭曲，这将对根据高斯拟合曲线的最大功率值求指向偏差带来测量误差。本文采用e指数函数叠加线性项进行功率数据拟合，原始数据采用公式(1)进行拟合。

$$
p ( x ) = b _ { 1 } \cdot \exp \left[ - 0 . 5 \cdot \left( { \frac { x - b _ { 2 } } { b _ { 3 } } } \right) ^ { 2 } \right] + b _ { 4 } \cdot x ^ { 3 } + b _ { 5 } \cdot x ^ { 2 } + b _ { 6 } \cdot x + b _ { 7 }
$$

上式中， $\mathfrak { p }$ 为测量的功率值； $\textbf { \em X }$ 功率值的索引数； $\mathfrak { b } _ { \mathrm { i } } ( \mathrm { i } { = } 1 , 2 \dots 7 )$ 为拟合参数。p的最大值对应的偏差，即为天线指向的方位或俯仰的偏差[12.13]。图4为天线俯仰扫描的功率曲线的拟合。在做这次俯仰扫描前，我们反复采用5点扫描法，将天线指向进行修正。实测数据分析表明 $\operatorname { E } 1 +$ 扫描的指向误差为17.28″，E1-扫描的指向误差为-12.96"，然而这次扫描前指向进行了多次修正，造成这种结果是因为天线控制系统的系统延迟和伺服系统响应滞后导致一个单点扫描( $\mathrm { ~ E 1 + }$ 或E1-)的测量误差。因此我们在一个指向点扫描时分别进行 $\mathrm { A z ^ { + } }$ 、Az-、 $\operatorname { E } 1 +$ 、E1-共4次扫描，并分别取$\mathrm { A z ^ { + } }$ 和 $\mathrm { A z ^ { - } }$ ， $\operatorname { E l } +$ 和E1-的平均值作为方位和俯仰上的指向偏差。

为了解算出来的指向模型精度高，需要指向样本点全天区覆盖面广且有足够的有效样本数。目前天马 $1 3 \mathrm { m }$ 天线指向测量是将几个强的河外校准射电源添加到脚本库，循环交替的扫描各个射电源，直到射电源的轨迹覆盖全天区。一次指向测量后，有大量的数据需要分析处理，为了方便每个单点扫描数据拟合分析和模型参数拟合，我们开发了一套交互式的数据分析软件，如图5所示。

I1 人 人 [mt Baan A A

![](images/6236b724756c8c6c678e7ba580e63c9d902489e6cc12da11213cd8097257b5e5.jpg)  
图4俯仰扫描模式下的功率曲线拟合  
图5指向数据分析软件界面  
Fig. 4 Fittings of the power curve under elevation modes.   
Fig.5 Software interface for analysing point data analysis.

整个指向建模数据分析都可以由此软件完成，首先点击“SelectFile”按钮选择要分析处理的数据文件；然后“DataAnalysis”分析文件中有多少个指向样本数（一个指向样本包括对一个源扫描的 $\mathtt { A z + , ~ A z - , ~ E l + , ~ E l - } \mathtt { \Omega }$ ，并记录文件中相应行的索引号；“NextScan”逐条分析对一个点的4次扫描偏差；“Pre-Scan”回放前一个样本的数据；“Delete”删除不好的指向样本数据；软件左边框上显示每个指向样本数据的方位角、俯仰角、扫描的射电源、方位偏差和俯仰偏差；最后点击“SaveAl1Data”保存数据和“Mode1”输出模型参数文件。

# 4.指向修正模型拟合

影响射电望远镜指向误差的原因是多方面的：整个天线各零部件的机械误差，天线系统的装配误差，射电望远镜还受到重力、温度变化、大气折射等因素的影响。在射电望远镜指向误差源中，大部分具有重复性和规律性，我们可以通过相应的误差函数来修正。对于固有的和具有变化规律的误差称为系统误差，该误差都会导致天线在方位或俯仰上产生指向偏差。传统建立指向模型是由公式（2）全天区拟合指向偏差 $\Delta \mathrm { A z }$ 和 $\Delta \mathtt { E } 1$ 获得的8参数模型[7,8]。

$$
\left\{ \begin{array} { l } { \Delta \mathbf { A } z = \mathbf { p } \mathbf { l } + p \mathbf { 3 } \cdot \mathbf { t } \mathrm { ~ a ~ n } E { l } ) \mathrm { c ~ o ~ s } A { z } ) + p \mathbf { 4 } \cdot \mathbf { t } \mathrm { ~ a ~ n } E { l } ) \mathrm { s ~ i ~ n } \mathbf { A } { z } ) + p \mathbf { 5 } \cdot \mathbf { t } \mathrm { ~ a ~ n } E { l } ) - p 6 / \mathrm { c ~ o ~ s } E { l } ) } \\ { \Delta E { l } = \mathbf { p } 2 - p \mathbf { 3 } \cdot \mathbf { s } \mathrm { ~ i ~ n } E { l } ) + p \mathbf { 4 } \cdot \mathbf { c } \mathrm { ~ o ~ s } A { z } ) + p 7 \cdot \mathbf { c } \mathrm { ~ o ~ s } E { l } ) + p 8 / \mathrm { t ~ a ~ n } E { l } ) } \end{array} \right.
$$

上式中，p1表示方位编码器固定零点偏差;p2表示俯仰编码器固定零点偏差;p3、p4参数项表示天线方位轴和俯仰轴倾斜引起的误差项;p5表示天线方位轴和俯仰轴不正交垂直导致指向误差项；p6描述述天线电轴和俯仰轴不正交；p7为天线重力变形因子；p8为残余大气折射误差。 $\Delta$ Az、△E1分别表示天线每个指向的方位误差和俯仰误差。指向数据分析中统计天线方位指向误差用公式（3)计算方位角的均方根，俯仰指向误差用公式（4）计算俯仰角的均方根，总体指向误差用公式（5）计算天线指向误差均方根。

$$
\delta _ { _ { A z } } = \sqrt { \frac { \sum _ { \scriptstyle i = 1 } ^ { n } [ \Delta A z _ { \scriptstyle i } \cdot \cos ( \textit { \textbf { E l } } _ { i } ) ] ^ { 2 } } { n } }
$$

$$
\delta _ { E 1 } = \sqrt { \frac { \sum _ { i = 1 } ^ { n } [ \Delta E l _ { i } ] ^ { 2 } } { n } }
$$

$$
\delta = \sqrt { \delta _ { A z } ^ { 2 } + \delta _ { E l } ^ { 2 } }
$$

采用8参数模型对指向偏差测量采集的数据进行解析，得到了拟合模型参数值。天线方位和俯仰拟合残差分布分别如图6和图7所示，从图中可以看出指向样本数据分布均匀且覆盖天区范围广。经过模型拟合后指向在方位分布的残差为7.69”，指向在俯仰分布的残差为8.99”。天线指向在方位和俯仰整体上的残差分布如图8所示，模型拟合后的残差为11.83”。图中符号“×”表示测量的指向样本数据，符号“·”表示模型拟合后的指向值。

![](images/4dc50bfffd008f78780f7858ced435d27454905bcc6a7401b9fd65585e92d742.jpg)  
图6指向数据方位拟合及残差分布

![](images/365edb875af5b325f9f702f38087681703cd14afa11f2023979c4d95471285d9.jpg)  
图7指向数据俯仰拟合及残差分布  
Fig.7 Distribution of the point fitting errors and theirresiduals in the elevation direction

![](images/0cce624b0f463dea67cfdea81df1f0af2006378c4d0e4333ea6c6e130a82a43e.jpg)  
Fig.6 Distribution of the point fitting errors and theirresidualsintheazimuthdirection   
图8方位俯仰整体残差分布

指向模型建立后，把模型参数配置文件加载到天线伺服控制计算中，天线每次发送的引导值会加上模型偏差值。为了验证模型的准确性，对射电源进行指向扫描，计算出指向偏差，根据公式（3）、公式（4）、公式（5）计算得到其中方位上的指向误差均方根为6.16”，俯仰上的指向误差均方根为8.09″，总体指向误差为10.17”。

Fig.8 Distribution of the overa11 residuals in the azimuth and elevation directions

# 5结论

本文详细介绍了天马 $1 3 \mathrm { m }$ 射电望远镜指向修正建模的方法。分析对比了不同扫描方式对指向误差测量的影响；描述了处理观测数据的算法软件，最后建立了8参

数指向模型，并将模型带入天线伺服控制系统，验证了模型的正确性。天线的盲指误差均方根可以达到10”。本文的研究可以为天线指向建模方法提供参考。

# 参考文献

[1] 王锦清，虞林峰，赵融冰,等．大型射电望远镜高精度指向偏差检测方法[J].中国科学：物理学、力学、天文学,2017,47(12):10.[Wang JQ,Yu LF, Zhao RB,et al. High precision pointingerror detection method for large radio telescope (in Chinese). Sci Sin-Phys Mech Astron,2017, 47: 129504.]  
[2]魏善祥，王启明，孔德庆,等．大型双反射面天线指向误差评估算法[J].天文研究与技术,2020,17(4):513-521.[WEI S X,WANG Q M,KONG D Q, et al.Algorithm for EstimatingPointing Error of Large Dual-reflector Antenna[J].Astronomical Research & Technology, 2020,17(4):513-521.]  
[3]温浩兴，许谦，王娜.南山 26 米射电望远镜轨道高差测量及其对指向精度的影响[J].天文研究与技术,2019,16(2): 158-166.[WEN H X,XU Q,WANG N,Measurement of NSRT 26mAntenna Track Unevenness and Influence on Pointing Accuracy[J].Astronomical Research &Technology, 2019,16(2): 158-166.]  
[4]魏善祥，王启明，孔德庆,等．大型双反射面天线指向误差评估算法[J].天文研究与技术,2020,17(4):513-521.[WEI S X,WANG Q M, KONG D Q, et al.Algorithm for EstimatingPointing Error of Large Dual-reflector Antenna[J].Astronomical Research & Technology, 2020,17(4):513-521.]  
[5]李金岭，赵达新，柳聪,等．佘山 $1 3 \mathrm { ~ m ~ }$ 口径射电望远镜指向扫描数据解析[J]．武汉大学学报:信息科学版,2020,45(2):159-166.[LI J1,ZHAO D X,LIU C,et al.Analysis of Pointing ScanData of the Sheshan $1 3 \mathrm { ~ m ~ }$ Radio Telescope[J].Geomatics andInformation Science of WuhanUniversity,2020,45(2):159-166.]  
[6]虞林峰，王锦清，蒋甬斌，等．倾斜仪在提高 $\mathrm { T M } 6 5 \mathrm { ~ m ~ }$ 射电望远镜指向精度上的应用．中国科学：物理学力学天文学,2019,49:129502.[YuL F,Wang JQ,Jiang Y B,et al.Usinginclinometer to improve the pointing accuracy of TM65 m radio telescope (in Chinese). SciSin-Phys MechAstron,2019,49:129502]  
[7]马小辉，张志斌，孙中苗,等．射电天线指向改正模型中轴系误差的完全表达式[J]．天文学报,2021, 62(1):17-28.[MA X H,ZHANG Z B,SUN Z M,et al.The Complete Expression of theAxes Related Errors for the PointingCalibration Model of the Radio Telescope[J].ActaAstronomica Sinica,2021, 62(1):17-28.]  
[8]虞林峰，王锦清，赵融冰,等．TM65m 射电望远镜指向模型的建立[J].天文学报，2015,56(2):165-177.[YU L F， WANG JQ， ZHAO R B ，et al. Pointing Model Establishment ofTM65 m Radio Telescope[J]. Acta Astronomica Sinica, 2015, 56(2):165-177.]

# The high precision pointing Model Establishment of Tianma $1 3 \mathrm { m }$

# RadioTelescope

Sun Zheng-xiong1,Wang Jin-qing1.2,Yu Lin-feng1,Jiang Yong-bing' ,Zhao Rong-bing',Gou Wei',

Wang Guang-li1.3

（ $^ 1$ Shanghai Astronomical Observatory，Chinese Academy of Sciences，Shanghai 2Ooo3O，China; ²Key Laboratoryof Radio Astronomy, Chinese Academy of Sciences,Nanjing 2loo08,China; 3University of Chinese Academy of Sciences, Beijing l00094, China)

Abstract:The Tianma $1 3 \mathrm { ~ M ~ }$ radio Telescope is a new generation of VLBI antennas designed for space geodesy， the so-called VGOS system. VGOS observing will change all aspects of VLBI, from scheduling,to correlation，to observing strategy，to analysis. Compared to current observing，a typical VGOS session will have 1\~2 orders of magnitude more data. Tianma $1 3 \mathrm { m }$ antenna was equipped with a $3 \sim 1 5 \mathrm { G h z }$ broadband refrigeration receiver. The antenna pointing deviation is generally required to be less than 1/1O of the HPBW. In order to meet the requirement of high precision pointing, In this paper, the method of pointing establishment and antenna control scanning strategy are introduced in detail. The complete expression of the system error correction model was given,and the meaning of the parameters in the model was clarifiedand .Based on the measured data of the antenna pointing scan, the pointing accuracy of the telescope was evaluated. The least square method was used to fit the data samples covering the all-sky region, and the pointing model of the Tianma $1 3 \mathrm { m }$ radio telescope was obtained. The model was loaded into the antenna servo control system for verification,and the blind finger error of the tianma $1 3 \mathrm { m }$ radio telescope was better than 10 arc seconds.

Key words: Radio telescopes, data analysis, systematic error, pointing correction model