# 基于异常值识别卡尔曼滤波器的短期交通流预测\*

白伟华1，张传斌1，张瓌旖²，周腾²

(1．肇庆学院 计算机科学与软件学院、大数据学院，广东 肇庆 526061;2.汕头大学计算机系，广东 汕头 515063)

摘要：针对智慧交通的需求，提出了一种新颖有效的短时交通流预测方法，通过异常值识别扩展了卡尔曼滤波，使其能对噪声进行识别和过滤——异常值识别卡尔曼滤波器。利用卡尔曼滤波能有效地过滤导致系统不确定性的交通流波动，但这可能会使指示交通流突变的细微线索丢失。为了提升预测精度，应用离散小波变换对原始信号进行识别处理，在去掉异常值的同时保留原有对预测有效的信号源信息，此外还使用了历史参考值对预测值进行修正。最后，在四个基准数据集上的大量实验表明，与常用及最新的预测模型相比，其结果 MAPE 平均降低了 $2 . 9 1 9 \%$ ，RMSE平均降低了79.582。

关键词：卡尔曼滤波；有源噪声控制；短时交通流预测；状态向量 中图分类号：TP393.09 doi:10.19734/j.issn.1001-3695.2020.03.0070

Outlier-identified Kalman filter for short-term traffic flow forecasting

Bai Weihual, Zhang Chuanbin', Zhang Shuangyi², Zhou Teng² (1.SchoolofComputerScience&Software、SchoolofBigData,ZhaoQingUniversity,Zhaoqing Guangdong526061,Chind; 2.Dept.of Computer Science, Shantou University,Shantou Guangdong 515063, China)

Abstract:Anovel and efective technique forshort-term traffcflow forecasting is presented.The main contribution is an extensioofKalman filter,suchthat itbecomestobeabletoidentifytheoutlierandthenflteroutit;thepresenttechnique is namedasOutlier-identified Kalman filter.Thefluctuationsof the traficflow,whichleadsthesystemuncertaintyisoften filteredutbytheclasic Kalmanfilter,and thesubtleclues indicating thesudenchangeofthetraffcflowmaylose inthis operation.Toachievebetter forecasting acuracydiscrete wavelet transformisused toprocesstheoriginal signaland the useful signalsare preserved whilede-noising.Inaddition,historical referencevaluesare apliedtocorrectpredicted values. Extensive experiments on four benchmark datasets demonstrate an average improvement of $2 . 9 1 9 \%$ in MAPE and 79.58 in RMSE.

Key words: Kalman filter; active noise control; short-term trafic flow forecasting; state vector

# 0 引言

结合物联网、车辆网和智慧交通的应用，准确及时的交通流信息对智能交通系统(intelligent transport system,ITS)的成功部署至关重要，它能为物流部门、商业机构、旅游服务机构和政府管理机构提供可靠的交通流信息：优化路线规划、提高效率且节约时间；缓解交通拥堵，降低交通运输成本；减少汽车尾气排放污染、节省能源；减少交通事故，并提高交通运营效率。

为提升交通运输体系的智能化水平，应用大数据、移动互联网等技术与交通运输深度融合，交通流量是判别道路交通状态的一个关键因素。短期交通流预测是微观意义上的，与中观和宏观意义上以小时、天、甚至是年计算的基于交通规划的战略预测有本质区别：其主要内容是基于当前和过去的交通数据，采用适当的方法去滚动预测未来几秒到半小时的交通状况。然而，由于交通流内在的随机性和外部噪声[l\~3]的存在，比如意外事故或人工交通管制[4,5]，找到既稳健又准确的预测算法是一项具有挑战性的任务。

针对交通流预测研究，各国学者已提出了300多种短时交通流预测模型和方法，主要包括线性理论模型、非线性理论模型、动态分配模型及基于知识发现的模型四大类。卡尔曼滤波器(Kalman filter,KF)及其变体由于具有计算效率高，所需内存少，适用于静态、非平稳数据分析，可使用实时数据动态更新其状态变量，并能更好地适应交通流量的变化等特性，是交通流预测任务中广泛使用的强大工具之一[6-8]。为了解决交通流中存在的高度不确定性(气候、交通事故、突发事件等)、简单的噪声过滤预处理对指示交通流突变的失真问题，本文提出了一种能够准确区分有效信号和噪声的卡尔曼滤波器，命名为异常值识别卡尔曼滤波器(outlier-identifiedKalmanfilter,OiKF)。本文将OiKF应用于短期交通流预测，并在四个基准数据集上对其进行了实验评估，然后与经典的卡尔曼滤波器以及其他常用的参数和非参数技术进行性能比较，经大量实验证明，该技术提高了预测的精确度和准确性，证明了异常值识别卡尔曼滤波器在短期交通流预测方面的优越性。

# 1 相关研究

传统的卡尔曼滤波及其变体为分析和解决一大类估计问题提供了清晰强大的基本工具，被广泛应用于许多工程领域，

收稿日期：2020-03-25;修回日期:2020-05-08基金项目：国家自然科学基金资助项目(61902232);广东省自然科学基金资助项目(2018A030313291)、广东省教育科学规划项目(2018GXJK048)；广东省普通高校特色创新项目（自然科学，2019KTSCX19)；广东大学生科技创新培育专项资金资助项目(pdjh2020b0222)；肇庆学院校级科研项目(2019012612)

作者简介：白伟华(1976-),男，广东高要人，副教授，博士，主要研究方向为任务序列分析、服务计算、大规模任务调度、多服务器控制(bandwer@163.com)；张传斌(190-)，男，广东肇庆人，实验员，硕士，主要研究方向为计算智能，大数据，系统建模与优化；张块旖(1996-），女，青海西宁人，硕士研究生，主要研究方向为城市计算、深度学习；周腾(1987-)，男，广东汕头人，讲师，博士，主要研究方向为集成学习、深度学习、智能交通系统和医学图像处理.

特别是对于离散时间系统状态估计，包括信号处理，最优控制，导航等。实际应用包括参数估计，系统识别，目标跟踪，同步定位等。这些问题的很多过程都可以用状态空间系统去描述，如果本文能对一个过程建立数学模型，本文就可以利用数学工具去控制这个过程，并获得关于该过程的信息。利用状态空间系统对短期交通流预测问题进行建模已有不少研究。Okutani 和 Stephanedes[9] 首先在城市交通量预测中引入状态空间模型来预测高速公路入口坡道区域的交通分流，并验证该模型优于二代城市交通控制系统(UTCS-2)中使用的交通量预测模型。Stathopoulos和Karlaftis[l0]也提出了一种基于最优状态估计理论的模型，并表明多变量状态空间模型的使用提高了ARIMA模型的预测精度。Hu等人[1I]提出了混合粒子群优化支持向量机回归模型(HybridPSO-SVR)，使用支持向量机回归模型进行短期交通流预测，并通过粒子群算法优化向量机回归模型的参数，减少模型学习时间。Guo等人[12]提出使用一阶灰色模型GM 进行短期城市道路交通流预测，该模型引入道路的负载和时延因素，与原始灰色模型相比，预测精度明显提高。最小平方提升模型(least squaresboosting,LSBOOST)是一个集成多个学习算法的框架[13]，在进行短期电力需求预测时，具有良好效果，可尝试用于其他领域的短期预测。然而，如前文所述，短期交通流数据经常被局部噪声破坏，这可能会显著影响短期交通流的预测准确性。在先前的研究中，只关注了卡尔曼滤波在短期交通流预测中过滤噪声的作用，忽视了过滤噪声有损信号质量，例如，Xie等人[14]研究了卡尔曼滤波器在离散小波分析中的应用,得出噪声污染会严重影响交通流预测性能的结论。Wang等人[15]使用了一种基于卡尔曼滤波器的自适应交通流预测算法,该算法同时考虑了状态和观测高斯噪声。为了进一步提高预测精确度，Zhou等人[7通过补偿初步预测的误差，提出了一种用于交通流预测的新型混合卡尔曼滤波器。然而随着过滤噪声的能力逐步地提升，预测精确度趋于平稳，甚至开始下降。主要原因是，在过滤噪声的同时，有用的信号，尤其是部分指示交通流突变的细微线索也被过滤掉了。

与已有工作不同的是，本文利用一个新的成本函数重新构造了卡尔曼滤波器，提出了一种新颖有效的噪声识别卡尔曼滤波器OiKF，该技术能够在实现高效噪声过滤的同时获得高质量有效信号，并将其应用于短期交通流预测，提出了一种鲁棒交通流预测算法。具体地，本文通过离散小波变换(discretewavelettransform,DWT)将原始交通流数据分解重构成近似部分和细节部分。与只抛弃细节部分的Zhou等人的工作相比，该方法能够考虑多级细节部分；本文将不同层次的细节部分作为影响预测性能的噪声或提高预测性能的线索与保持了原始交通流数据基础模式的近似部分一起作为模型的输入来求解下一时刻的最优解，同时还利用历史参考点对预测值进行修正，从而提高了预测的准确性。

# 2 OiKF短期交通预测理论模型及实现

在理论模型中，首先利用离散小波变换对异常值进行过滤处理，然后分析卡尔曼滤波器(KF)进行交通流预测的通用方法，最后提出基于异常值识别卡尔曼滤波器(OiKF)及其理论模型，并叙述利用该理论模型实现短时交通流预测的过程。

# 2.1离散小波变换对异常值的处理

小波变换(wavelettransform，WT)是通过伸缩和平移对信号进行细化分析的工具，能提供变化的"时间-频率"窗口[16]。设函数 $\psi ( t )$ 是一个平方可积的函数，即 $\psi ( t ) \in L ^ { 2 } \left( R \right)$ ，且该函数的傅里叶变换为

$$
\Psi ( \mathfrak { c } ) = \int _ { - \infty } ^ { \infty } \psi ( t ) e ^ { - j \omega t } d t
$$

满足容许条件(admissibilitycondition)即：

$$
C _ { \Psi } = \int _ { - \infty } ^ { \infty } \frac { \left| \Psi ( \omega ) \right| ^ { 2 } } { \left| \omega \right| } d \omega < + \infty
$$

则称函数 $\psi ( t )$ 为小波母函数，对其进行伸缩和平移变换得

$$
\psi _ { a , b } \left( t \right) = \frac { 1 } { \sqrt { a } } \psi \left( \frac { t - b } { a } \right) , \lambda > 0 , \emptyset \in R
$$

其中 $a$ 为尺度参数， $b$ 为平移参数，若信号 $f \left( t \right)$ 是一个平方可积函数，即 $f \left( t \right) \in L ^ { 2 } \left( R \right)$ ，则连续小波变换的定义如下：

$$
W _ { f } ^ { \psi } \left( a , b \right) = \intop _ { - \infty } ^ { \infty } f \left( t \right) \bar { \psi } _ { a , b } \left( t \right) d t , a > 0 , \emptyset \in { \cal R }
$$

其中， $\bar { \psi } _ { a , b } \left( t \right)$ 为 $\psi _ { a , b } \left( t \right)$ 的共轭。对尺度参数 $a$ 和平移参数 $b$ 进行离散化采样，并使两个参数满足 $a = a _ { 0 } ^ { \ j } \left( a _ { 0 } > 1 \right) , b = k a _ { 0 } ^ { \ j } b _ { 0 }$ ，可获得离散小波函数：

$$
\psi _ { j , k } \left( t \right) = a _ { 0 } ^ { - j / 2 } \psi \left( a _ { 0 } ^ { - j } t - k b _ { 0 } \right)
$$

再令 $b _ { 0 } = 1$ ，使 $\psi _ { j , k } \left( t \right) = a _ { 0 } ^ { - j / 2 } \psi \left( a _ { 0 } ^ { - j } t - k \right) , a _ { 0 } > 1 , \mathfrak { j } , k \in Z$ ，若信号$f \left( t \right) \in L ^ { 2 } \left( R \right)$ ，则 $f \left( t \right)$ 的离散小波变换为

$$
W _ { f } ^ { \psi } \left( j , k \right) = \intop _ { - \infty } ^ { \infty } f \left( t \right) a _ { 0 } ^ { - j / 2 } \bar { \psi } \left( a _ { 0 } ^ { - j } t - k \right) d t
$$

通常， $\psi _ { j , k } \left( t \right)$ 是一个 $L ^ { 2 } \left( R \right)$ 上的标准正交基，即

$$
\psi _ { j , k } , \psi _ { m , n } = \left\{ \begin{array} { c } { { 1 , \mathfrak { Y } = m \mathbb { H } k = n } } \\ { { 0 , ? \quad \sharp \sharp \ : } } \end{array} \right.
$$

则，信号 $f \left( t \right)$ 可通过以下方式重构：

$$
f \left( t \right) = \sum _ { j = - \infty } ^ { \infty } \sum _ { k = - \infty } ^ { \infty } W _ { f } ^ { \psi } \left( j , k \right) \psi _ { j , k } \left( t \right)
$$

另外针对离散时间信号的离散小波变换可通过若干次高通和低通滤波简单实现，其中高通滤波器获得高频信息，表示信号的细节，低通滤波器获得低频信息，表示信号的近似。低频信息和高频信息分别通过对应的合成滤波器，可以获得原始信号对应的低频部分和高频部分，再根据实际情况合成所需的部分，就可实现信号的分解和重构，如信号去噪、过滤异常值等。

# 2.2KF短期交通预测模型

已知 $H _ { \iota } = [ \nu o l _ { \iota - n } , \nu o l _ { \iota - n + 1 } , . . . , \nu o l _ { \iota - 1 } ]$ ：时刻 $t - n$ 到时刻 $t \mathrm { - } I$ 的一组交通流原始数据，在短期交通预测中，预测目标值为 $\mathbf { \nabla } _ { \nu o l _ { t } }$ ：即预测下一时刻 $t$ 的交通流量。在Zhou等人先前的工作中，将要预测的交通流量表示为过去交通流量和相应权重$\Theta _ { t } = \left[ \theta _ { t - n } , \theta _ { t - n + 1 } , . . . , \theta _ { t - 1 } ? \right] ^ { T }$ 的组合，即：

$$
\nu o l _ { t } = H _ { t } \Theta _ { t } + \nu _ { t }
$$

$$
\Theta _ { t } = F \Theta _ { t - 1 } + w _ { t }
$$

其中 $F \in R ^ { n \times n }$ 表示状态转移矩阵， $\nu _ { t } \in R ^ { m }$ 和 $w _ { t } \in R ^ { n }$ 为测量噪声和过程噪声，它们均为零均值、不相关的高斯白噪声，分别有已知的过程噪声协方差矩阵 $\varrho$ 和测量噪声协方差矩阵 $R$ 。一旦获得 $\mathbf { \sigma } _ { \nu o l _ { t } }$ ，所求下一时刻 $t { + } l$ 的交通流预测值 $\nu o l _ { t + 1 }$ 可表示为

$$
\nu o l _ { t + 1 } = H _ { t + 1 } \Theta _ { t }
$$

$\Theta _ { t }$ 是结合式(1)和(2)得到的时刻t最优估计值。Lan等人[17]、Xie 等人[14]和 Zhou 等人[7]的工作也做了相同的假设。

# 2.3OiKF短期交通预测模型

OiKF短期交通预测模型中，利用离散小波变换对交通流原始数据 $\nu o l _ { t } \in H _ { t }$ 进行分解重构，最终由两部分组成：近似部分 $\tilde { H } _ { t }$ （ $\tilde { H } _ { t } = \left[ \nu o l _ { t - n } , \nu o l _ { t - n + 1 } , \cdots , \nu o l _ { t - 1 } \right]$ ）和细节部分 $\Lambda _ { t }$ （204号 $\scriptstyle \left( \Lambda _ { t } = \left[ \lambda _ { t - n } , \lambda _ { t - n + 1 } , \cdots , \lambda _ { t - 1 } \right] \right)$ 。其基本原理为：由于异常值(存在高度不确定性：气候、交通事故、突发事件等因素在原始数据流中产生的异常值)的存在，原始交通流数据被局部存在的异常值/噪声严重破坏，为解决该问题，通过离散小波变换，以分解重构获得的低频近似部分 $\nu o l _ { t }$ 替代原始数据vl作为系统的部分输入用于交通流预测，实现在对原始数据过滤由不确定性产生的异常值，同时还保持了原始交通流的基础模式；为不丢失原始数据中指示交通流突变的细微线索，以另一部分一—高频细节部分 $\Lambda _ { t }$ 作为被异常值所破坏的控制输入变量，去捕获隐含在快速随机变化的交通情况中的细微线索。

在离散小波变换对交通流原始数据 $\nu o l _ { t } \in H _ { t }$ 进行分解重构的基础上，实现扩展卡尔曼滤波器，其动态线性系统可表示为

$$
\tilde { \Theta } _ { t } = F \tilde { \Theta } _ { t - 1 } + B \Lambda _ { t - 1 } + w _ { t }
$$

$$
\nu o l _ { t } ^ { * } = \tilde { H } _ { t } \tilde { \Theta } _ { t } + \nu _ { t }
$$

其中 $B \in R ^ { n \times n }$ 是控制矩阵，其作用与 $F$ 类似。为了区别于式(2)中交通流权重 $\Theta _ { t }$ ，将其重新表示为 $\tilde { \Theta } _ { t }$ 。细节部分 $\Lambda _ { t }$ 可被重新表示为

$$
\Lambda _ { t } = \Lambda _ { t - 1 } + \xi _ { t }
$$

其中 $\xi _ { t } \in R ^ { n }$ 表示协方差为 $\sigma ^ { 2 }$ 的高斯白噪声。通过扩展，该技术既继承了传统卡尔曼滤波过滤噪声的所有优点，又保证了原始数据的质量。

在预测模型中，其目标成本函数为

$$
\operatorname { E } \left( { \nu o l } _ { t } \right) = C o { \nu } { \left( e _ { t - n } ^ { 2 } + e _ { t - n + 1 } ^ { 2 } + . . . + e _ { t - 1 } ^ { 2 } \right) } - { \sigma } ^ { 2 } { K } _ { t } ^ { 2 }
$$

问题求解：利用公式(7)所示的成本函数去求解最优解。其中： $\mathrm { E } \left( \nu o l _ { t } \right)$ 表示时刻 $t$ 求解获得的优化目标， $C o \nu$ 运算表示每个时刻 $i$ 的估计误差的平方 $e _ { i } ^ { 2 }$ 组成的协方差矩阵， $\boldsymbol { K } _ { t } \in { R } ^ { n \times n }$ 是卡尔曼增益矩阵。由于篇幅问题，推导优化公式(7)的详细过程可参考 Zhang 等人[8], $\mathbf { M } \mathbf { a }$ 等人[18]的相关工作。本文给出了该算法的基本过程：

首先基于 $_ { t - l }$ 时刻的权重 $\tilde { \Theta } _ { t - 1 } ^ { + }$ 和误差协方差矩阵 $P _ { t - 1 } ^ { + }$ 得到一个先验的估计值 $\tilde { \Theta } _ { \iota } ^ { - }$ 以及相应的误差协方差矩阵 $P _ { t } ^ { - }$ 。然后用求得的卡尔曼增益矩阵 $K _ { t }$ 和测量值 $\nu o l _ { t }$ 去更新估计值 $\tilde { \Theta } _ { t - 1 } ^ { + }$ 和相应协方差矩阵，从而获得其后验估计 $\tilde { \Theta } _ { t } ^ { + }$ (所求的最优估计值)和相应协方差矩阵 $P _ { t } ^ { + }$ ，在得到最优估计值后，所求的交通流预测值 $\nu o l _ { t + 1 }$ 可通过公式(3)进行计算。最后 $\tilde { \Theta } _ { t } ^ { + }$ 和 $P _ { t } ^ { + }$ 下一时刻的输入(先验估计)用来计算下一次的最优估计，这是一个动态滚动的持续预测过程。

此外，通过对实际数据的波形图进行分析，可知交通流数据本质上具有一定的周期性。因此，历史数据具有很好的参考价值。在进行预测时，首先通过公式(3)获取时间t的预测值 $\mathbf { \nabla } _ { \nu o l _ { \mathit { t } } ^ { \prime } }$ ，然后通过历史参考值对预测值进行修正。在近似部分中，先选取时间 $t$ 之前一段时间共 $s$ 个时间点的数据作为当前序列 $S _ { t } = \left[ \nu o l _ { t - s } , \nu o l _ { t - s + 1 } , . . . , \nu o l _ { t - 1 } \right]$ ，再从已预测获得的历史数据序列中搜寻与当前实际交通流数据序列最为接近的历史序列$S _ { \mathrm { { h } } } = \left[ \nu o l _ { h - s } , \nu o l _ { h - s + 1 } , . . . , \nu o l _ { h - 1 } \right]$ ，选取时间 $h$ 观测值 $\nu o l _ { h }$ 作为参考值，预测值修正过程如图1所示。

![](images/ea4c12258f602af6ed468aa1bb9126fdcd8ce9dca8a2c427d9872154db32e097.jpg)  
图1卡尔曼滤波器的预测值进行修正处理过程

Fig.1The correction process of prediction value of Kalman filter$\nu o l _ { h }$ 与 $\mathbf { \nabla } _ { \nu o l _ { \mathit { t } } ^ { \prime } }$ 进行加权平均，得到最终的预测值 $\mathbf { \Delta } _ { \nu o l _ { t } }$ ，设参考值的权重为weight，其计算公式可定义为

$$
\nu o l _ { t } = w e i g h t \times \nu o l _ { h } + \left( 1 - w e i g h t \right) \times \nu o l _ { t } ^ { \prime }
$$

基于异常值识别卡尔曼滤波器短期交通预测基本过程为算法1基于异常值识别卡尔曼滤波器算法步骤

1．初始化阶段：

1.1设置状态转移矩阵 $F$ ，控制矩阵 $B$ ，过程噪声的协方差矩阵 $\boldsymbol { \mathcal { Q } }$ ，测量噪声的协方差矩阵 $R$ 和细节部分的噪声方差 $\sigma ^ { 2 }$ 。

1.2 初始化 $\tilde { H } _ { \iota _ { 0 } }$ 状态协方差矩阵 $P _ { t _ { 0 } }$ ，权重 $\tilde { \Theta } _ { t _ { 0 } }$ 和细节部分 $\Lambda _ { t _ { 0 } }$ 的值。

2．预测阶段：

$\tilde { \Theta } _ { t } ^ { - } = F \tilde { \Theta } _ { t } ^ { + } + B \Lambda _ { t - 1 }$ $P _ { t } ^ { - } = F P _ { t - 1 } ^ { + } F ^ { T } + \sigma ^ { 2 } B B ^ { T } + Q$

3．更新阶段：

$$
\begin{array} { r l } & { K _ { t } = P _ { t } ^ { - } \tilde { H } _ { t } ^ { T } \left( \tilde { H } _ { t } P _ { t } ^ { - } \tilde { H } _ { t } ^ { T } + R - \sigma ^ { 2 } \right) ^ { - 1 } } \\ & { \tilde { \Theta } _ { t } ^ { + } = \tilde { \Theta } _ { t } ^ { - } + K _ { t } \left( \nu o l _ { t } - \tilde { H } _ { t } \tilde { \Theta } _ { t } ^ { - } \right) } \\ & { P _ { t } ^ { + } = \left( I - K _ { t } \tilde { H } _ { t } \right) P _ { t } ^ { - } } \\ & { \nu o l _ { t } = \tilde { H } _ { t } \tilde { \Theta } _ { t } + R } \end{array}
$$

4．修正阶段：

搜寻最相似的历史序列，获得历史参考值 $\nu o l _ { h }$ ，根据公式(8)与第3阶段获得的预测值 $\nu o l _ { \mathit { t } } ^ { \prime }$ 进行加权平均，得到最终的预测值 $\mathbf { \Delta } _ { \nu o l _ { t } }$ 。

5．迭代：重复阶段2\~4直到预测完毕。

# 3 实验及结果对比分析

# 3.1实验数据说明

实验中采用了常被用作基准的测试数据一一荷兰阿姆斯特丹的四条高速公路的交通流量数据(分别表示为A1、A2、A4 和 A8)[4,5,7,8,15,19],对本文提出的 OiKF 进行验证性实验。这四条高速公路终止于阿姆斯特丹的环路，即A10高速公路，对应的分布如图2所示，其数据是通过分别位于距离环路融合点附近的一段距离内的MONICA传感器的四个检测点收集获得。数据序列为：从2010年5月20日至2010年6月24日，每分钟进行一次统计，统计该分钟内所经过的车辆数量，并折算成该分钟的每小时车流量。

![](images/ac666d1a96b74afedb7a43c08ee84c2176cf8c47912e8c862d34260eb48c483c.jpg)  
图2荷兰阿姆斯特丹的A1、A2等四条高速公路分布图  
Fig.2The map of the four highways in Amsterdam

这四条高速路具有一定的代表性，其中：a)A1为边境高速，是欧洲第一条高占有率 $^ { 3 + }$ 分离车道，车道占有率瞬时变化较大，预测难度高。b)A2为荷兰境内最繁忙的高速公路之一，其拥堵情况变化大，用以验证预测模型应对交通拥塞的预测有效性。c)A4高速公路是境内标准的国家公路，其车流情况比较缓和正常。d)A8高速公路是一段长约10公里左右的接驳性公路，以验证交通突发情况的预测有效性。

# 3.2 实验设置说明

在实验中，令状态转移矩阵 $F$ 的初始值设置为单位矩阵$I$ ，即 $F = I$ ；控制矩阵 $B$ 初始设置为 $1 0 ^ { - 5 } \cdot I$ 即 $B { = } 1 0 ^ { - 5 } \cdot I$ ；矩阵大小 $n$ 设置为8。测量异常值的协方差矩阵 $R$ 设置为零矩阵，初始状态协方差矩阵 $P _ { \mathrm { { t } } }$ 和过程异常值的协方差矩阵 $\varrho$ 设置为 $1 0 ^ { - 2 } \cdot I$ 。令初始权重 $\Theta _ { t }$ 设置为 $\left[ { \frac { 1 } { n } } , \cdots , { \frac { 1 } { n } } \right]$ 1,.,』]。另外在离散小波变换操作时，本文选择Daubechies1和Haar作为母波。在搜索历史参考值时，经过实验验证，按一天时间

0 $2 4 \times 6 0 m i n = 1 4 4 \times 1 0 m i n$ 进行切分的数据序列相关性最高，因此将序列的长度 $s$ 设置为144，历史参考点的权重weight的值设置为0.2。

# 3.3 实验评价准则

在实验中，拟定预测效果评估准则为[4,5,7,8,14,19\~23]：均方根误差(rootmean square error，RMSE)用于衡量一个模型的预测值和系统的测量值之间的平均误差；平均绝对百分比误差(mean absolute percentage error，MAPE)是这个平均误差的百分比表示。其定义为

$$
\mathrm { R M S E } = \sqrt { \frac { 1 } { M } \sum _ { t = 1 } ^ { M } \Bigl ( \nu o l _ { t } - \nu o l _ { t } \Bigr ) ^ { 2 } }
$$

$$
\mathrm { M A P E } = \frac { 1 } { M } \sum _ { t = 1 } ^ { M } \left| \frac { \nu o l _ { t } - \nu o l _ { t } } { \nu o l _ { t } } \right| \times 1 0 0 \%
$$

其中 $M$ 表示数据集的大小， $\nu o l _ { t }$ 和 $\nu o l _ { t }$ 分别为时刻 $\mathbf { \chi } _ { t }$ 的预测值和真实值。

# 3.4 预测结果及分析

实验采用OiKF对数据集进行测试。图3(a)-(d)为针对A1，A2，A4，A8四条公路交通流量数据其中1000个点的预测结果。图中黑色实线为预测值，红色虚线为实际观测值。图4-7为对应A1，A2，A4，A8四条公路交通流量5000个点的预测值与实际观测值的相关误差频度及CDF图，由观测值与预测值的差值取绝对值并除以观测值获得。

实验数据集考虑了多种影响因素及环境下的交通流数据，如图3所示，预测曲线与实际观测值曲线的拟合度高，即使在数据突变的位置误差也比较小。由此可见本文提出的方法克服了传统卡尔曼滤波器的不足，有效地捕捉到指示交通流突变的细微线索，能准确地对短时交通流进行预测。

图4\~7中， $\mathbf { x }$ 轴表示误差区间，左边y轴表示5000个预测点中误差 $\left| \frac { { \nu } o l _ { t } - { \nu } o l _ { t } } { { \nu } o l _ { t } } \right|$ 落入对应区间的数量(频度)，右边y轴表示误差累积，柱状图为频度，曲线为CDF。

![](images/50980687728a1f98414f1f7d9504e18820892243d85d0f64c30b528b1b7bdebd.jpg)  
(a)A1预测值与实际观测值拟合曲线

![](images/603895d49bdb73ef298ce3078631b02950aef6fc76f9d32800c717797daa490f.jpg)  
(b)A2预测值与实际观测值拟合曲线

![](images/38d7e62608845f377dc5307c6a5530e44c6d906987645320fca316e6b7beff08.jpg)  
图3四条高速公路交通流量预测值与实际观测值拟合曲线图Fig.3The curve of the predictions and actual values  
图5A2预测误差值频度及误差CDF

![](images/109056d3717a4197ffc685127085228d6655526e2ec1dbb077be938669139e12.jpg)  
图4A1预测误差值频度及误差CDF

![](images/96e897182fd079e154379019d76ff156febffec4ca8028ac5343d53a4f7e9d0b.jpg)  
Fig.4The prediction error frequency and error CDF ofA1

![](images/4e651e9f7eb7b28bac1b585e203091d3ecf03fd0897fdc93e467d6c47ca27dac.jpg)  
Fig.5The prediction error frequency and error CDF ofA2   
图6A4预测误差值频度及误差CDF

![](images/ef5b23ec2a93801af8db527d357087f712441e49224ba9b5e8de2dd48c7f210b.jpg)  
Fig.6The prediction error frequency and error CDF of A4   
图7A8预测误差值频度及误差CDF  
Fig.7The prediction error frequency and error CDF of A8

通过分析5000个数据点预测误差落入的区间频度和累积CDF曲线，a)由图4得到：对A1预测，误差在[0.0.2]累积达到 $9 0 . 3 6 \%$ ，误差 $< 0 . 3$ 累积达到 $9 6 . 3 9 \%$ ；b)对于A2，由图5可知：预测误差在[0,0.2]累积达到 $9 2 . 0 3 \%$ ，误差 $< 0 . 3$ 累积达到 $9 6 . 5 5 \%$ ；c)图6可知，对于A4的交通预测，[0,0.2]累积达到 $8 8 . 5 6 \%$ ，误差 $< 0 . 4$ 累积达到 $9 5 . 9 5 \%$ ；d)图7所示，[0,0.2]累积达到 $8 9 . 1 0 \%$ ，误差 $< 0 . 4$ 累积达到 $9 5 . 4 5 \%$ 。所有的预测中，误差 $< = 0 . 2$ 都超过了 $90 \%$ ，证明了OiKF能准确地对短时交通流进行预测。

# 3.5预测准确性对比分析

为验证OiKF模型在整体预测的有效性，以同一数据集(荷兰阿姆斯特丹的四条高速公路的交通流量数据)为输入，将本文提出的OiKF预测结果数据与传统的卡尔曼滤波模型[1] 以及当前一些新提出的交通流预测模型的实验结果按评价准则一一式(8)(9)的MAPE/RMSE进行准确性对比分析。主要具有代表性的对比算法有：

a）混合粒子群优化支持向量机回归模型算法(hybridparticle swarm optimization support vector regression method,SVR)[11];

b）灰色模型算法(grey model，GM)[12];

c）常用的标准基线对照模型算法[24]：随机游走模型(randomwalk method，RW)、历史平均模型(historical averagemodel,HA)、基于机器学习的最小平方提升模型(least squaresboosting，LSBOOST)，一个简单模型的集成框架[13]和指数平滑模型(exponential smoothingmodel，ES);

d)当前一些新的研究成果的模型算法：自动回归模型算法(autoregression，AR)[4]、混合式双卡尔曼滤波模型(hybriddual Kalman filtering model，KF)[25]、基于混合学习的模型(hybrid learningbased model，SVRGSA 以及 SVRPSO)[l9]。

各类算法的MAPE和RMSE实验结果数据分别如表1和2所示，最后本文还分析了OiKF对比各类算法在有效性上的提升率。

表1本方法和当前各类预测模型的MAPE实验结果对比

Tab.1The comparison ofMAPE with other models   

<html><body><table><tr><td>model</td><td>A1</td><td>A2</td><td>A4</td><td>A8</td></tr><tr><td>SVR</td><td>14.34</td><td>12.22</td><td>12.23</td><td>12.48</td></tr><tr><td>GM</td><td>12.55</td><td>10.88</td><td>13.28</td><td>12.92</td></tr><tr><td>RW</td><td>12.65</td><td>11.43</td><td>12.06</td><td>12.37</td></tr><tr><td>HA</td><td>16.87</td><td>15.53</td><td>16.72</td><td>16.24</td></tr><tr><td>LSBOOST</td><td>13.78</td><td>14.43</td><td>12.90</td><td>14.00</td></tr><tr><td>ES</td><td>11.94</td><td>10.75</td><td>11.97</td><td>12.00</td></tr><tr><td>AR</td><td>13.57</td><td>11.59</td><td>12.70</td><td>12.71</td></tr><tr><td>KF</td><td>12.46</td><td>10.72</td><td>12.62</td><td>12.63</td></tr><tr><td>SVRGSA</td><td>11.15</td><td>9.42</td><td>10.65</td><td>11.81</td></tr><tr><td>SVRPSO</td><td>11.63</td><td>10.08</td><td>10.99</td><td>12.20</td></tr><tr><td>OiKF</td><td>8.57</td><td>7.93</td><td>10.61</td><td>11.56</td></tr></table></body></html>

表2本方法和常用预测方法的RMSE实验结果对比

Tab.2The comparison ofRMSE with other models   

<html><body><table><tr><td>model</td><td>A1</td><td>A2</td><td>A4</td><td>A8</td></tr><tr><td>SVR</td><td>329.09</td><td>259.74</td><td>253.66</td><td>190.30</td></tr><tr><td>GM</td><td>348.38</td><td>255.86</td><td>274.48</td><td>188.97</td></tr><tr><td>RW</td><td>312.92</td><td>223.82</td><td>230.01</td><td>174.14</td></tr><tr><td>HA</td><td>404.84</td><td>348.96</td><td>357.85</td><td>218.72</td></tr><tr><td>LSBOOST</td><td>306.33</td><td>233.88</td><td>229.78</td><td>177.52</td></tr><tr><td>ES</td><td>315.82</td><td>226.40</td><td>237.76</td><td>174.67</td></tr><tr><td>AR</td><td>301.44</td><td>214.22</td><td>226.12</td><td>166.71</td></tr><tr><td>KF</td><td>332.03</td><td>239.87</td><td>250.51</td><td>187.48</td></tr><tr><td>SVRGSA</td><td>284.97</td><td>192.68</td><td>213.69</td><td>161.07</td></tr><tr><td>SVRPSO</td><td>300.97</td><td>205.94</td><td>224.63</td><td>163.95</td></tr><tr><td>OiKF</td><td>203.34</td><td>154.98</td><td>184.96</td><td>132.41</td></tr></table></body></html>

从表1和2可以得出，本文提出的方法在四个基准数据集上，比其他的对照方法更准确，OiKF在MAPE和RMSE的实验结果中都取得了最佳效果，与其他各个模型算法预测结果在MAPE和RMSE上的效果提升情况如图8和9所示。

![](images/7880177be18d79e3ecba993bcd23e281681c067a11e65c35be7dee6588726ae0.jpg)  
图8与其他模型在MAPE上的误差降低对比  
Fig.8The comparison of MAPE improving with others model

由图8可知，OiKF模型在A1、A2、A4和A8四条高速公路的测量点的预测值所获得的MAPE是最好的。图8 中Impvoe-Avg项统计出OiKF模型在各条高速路上对比其他预测模型的MAPE的平均降低百分率，故由图8可知，本文所提出的预测模型比其他最新研究提出的预测模型(如AR，SVRGSA，SVRPSO等)，其误差在四条高速路的预测值误差平均分别降低了达到： $4 . 5 2 4 \%$ ， $3 . 7 7 5 \%$ ， $2 . 0 0 2 \%$ 和 $1 . 3 7 6 \%$ 。

分析图9可知，与常用及当前最新研究的预测模型比较，在RMSE的 $^ { 4 ^ { * } 1 2 }$ 组的预测结果数据对比分析得到，OiKF所获得的效果也是最好的，从图9中Impove-Avg项数据可知，OiKF的RMSE值整体上比其他模型相应地平均分别降低了120.339，85.157，64.889和47.943。

![](images/8d056756bcc3ee83ddfc60a129ffb229f177e17bc0ba083c89ca92b9c93fd0d2.jpg)  
图9与其他模型RMSE 值降低值对比

OiKF在四条高速路上预测结果的MAPE和RMSE 整体提升情况(与其他模型对比，MAPE 降低值与RMSE 减少值的分布图)对应的箱图如图10和11所示。

![](images/380e16be847940132c2d4c5bf337e8b0b7264dd78508d7a724c2b4d6f9327635.jpg)  
Fig.9The comparison ofRMSE improving with others model   
图10各路线预测MAPE降低值分布情况

![](images/2b549dc7e569ad22ec8889a2551a2f39abd0b04820e31e4cf57cc93c65a6fc79.jpg)  
Fig.10The distributionofMAPE improving values   
图11各路线预测RMSE减少值分布情况  
Fig.11The distribution ofRMSE improving values

通过对实验结果的比较分析，实验数据呈现出本文提出的预测模型比其他常用模型的优越性，也充分证明了本文提出的方法在解决短期交通流预测问题中的有效性。

# 4 模型应用实例

在解决公交企业目前普遍存在的“分散调度”、“静态调度”、“经验调度”，引起的投入高、反应慢、效益差、客源流失严重的问题时，将基于异常值识别卡尔曼滤波器的短期交通流预测模型嵌入在公交智能调度系统中，对特殊路段进行短期交通流量预测，以动态调整公交调度的需求，提高公交运营调度管理的智能化，实现公交企业对人、车、线路等资源的高效利用。图12为系统中公交调度与GIS整合的场景，其中利用OiKF对地图中的多条主要路径进行交通流量预测，并反馈到公交的实时调度中。

本文提出的OiKF模型测试应用在2019年工业和信息化部新型信息消费示范项目“桂林出行网一一运输服务与旅游融合数字经济服务平台”的公交智能调度系统中，分别在桂林市的环城北一路、环城北二路、中山北路、东二环路和建干路五条干道(如图12所标注的五条城市干道)上设置了1000个预测点，以对OiKF进行有效性验证测试，并获得了良好的运营效果。将前期预测情况反馈给调度系统，以预案有效地指挥、控制和调节车辆运行，均匀合理的行车间隔，营运车辆跨线路营运，并可用于回顾总结分析，实现调度业务管理闭环。

山花山址量编号：1010 码C36223上监控D 时 广a 1.01 13 车 1010 1013 qC35223 万 上行 士时间 2015-50134518L 马目 江香江全百esa P山水·阳光城 22 a1 niti水园DS洗影Ea 严福小区 u 8. 皖x小区 mUuEMHE口B发笔8用全大临 上 东城隆用东城屋信2用 n H花园鑫彩区 滨江花园9- 中元站'BAB mARm优 8 桂花园 水线路 关江 总配车数：27辆 ：38个 运营车辆：23辆 上行车辆：11辆 下行车辆：9辆 上行速度：5Km/h 下行速度：14Km/h11路 8 2 8 联坛广场 R 四电日 公安西车场 二 西口 165路 0 N 国书团 铁西车场 江 汽车 口 +字街67路 881路 883路 上行在场车辆（6） ① 非营运车（0） ① □C3606 C31600 C3158 C31566 185路88路 C20580 楼C2088389路 ②91路 8 流水随次96路 上下行上行下行全部 特发鸡已发 软购 次K99路 8 请轮入林、车辆、工号、同机地300路 3 号 营运类型 路牌 次 状态 车辆 司机 开始站点 结束站点K307路1 营运计划 双11 1 完成 桂C31599 周鞍春 上行 联达广场 电子科大统计 日 1 营运计划 双11 2 发车 桂C31599 周教春 面 电子科大 联达广场线路 255条 2 营运计划 双21 1 完成 桂C31606 廖志明 上厅 联达广场 电子科大

# 5 结束语

本文提出了一种新的短时交通流预测方法，用于改善短期交通流预测的准确性。该方法改善了传统的卡尔曼滤波器，使其能对异常值进行识别和过滤。通过实验，与当前研究成果提出的模型的对比以及在公交智能调度系统中的测试应用，实验结果证明了该方法有效性和优越性，也说明在进行短期交通流预测时，过滤异常值的同时保证原始数据的质量是必要的。在四个基准数据集上的大量实验表明，与常用及最新的预测模型相比，其结果MAPE平均降低了 $2 . 9 1 9 \%$ ，RMSE平均降低了79.582。在今后的研究中，将进一步研究扩展到其他卡尔曼滤波器中，如扩展卡尔曼滤波器或无迹卡尔曼滤波器，并将其应用于其他预测任务中，如服务器任务序列的分析和预测，云计算中心各类资源利用率预测和分析，以及小粒度任务调度或任务量随时间变化预测等。结合神经网络的应用和一些新的交通流短期预测模型的成果[26\~28]，将进一步优化OiKF模型的参数设置，以提高预测模型的准确性。

# 参考文献：

[1]TeresaP.Impact of Data Loss for Prediction of Traffic Flow on an Urban Road Using Neural Networks [J].IEEE Transactions on Intelligent Transportation Systems,2018:1-10.   
[2]Zhan Hongyuan,Gomes G,Li X S,et al. Consensus ensemble system for trafficflowprediction[J].IEEETransactionsonIntelligent Transportation Systems,2018,19(12): 3903-3914.   
[3]Zheng Zibin,Yang Yatao,Liu Jiahao,et al. Deep and embedded learning approach for traffic flow prediction in urban informatics [J].IEEE Transactions on Intelligent Transportation Systems,2019,20(10): 3927- 3939.   
[4]Zhou Teng,Han Guoqiang,Xu Xuemiao,et al. δ-agree AdaBoost stacked autoencoder for short-term traffic flow forecasting [J].Neurocomputing, 2017,247:31-38.   
[5]Zhou Teng,Han Guoqiang，Xu Xuemiao,et al.A Learning-Based   
[6]Wang Yubin, Van Schuppen JH, Vrancken J.Prediction of trafic flow at the boundary of a motorway network [J]. IEEE Transactions on Intellgent Transportation Systems,2013,15 (1): 214-227.   
[7]Zhou Teng,Jiang Dazhi,Lin Zhizhe,et al. Hybrid dual Kalman filtering model for short-term traffic flow forecasting [J].IET Intelligent Transport Systems,2019,13 (6):1023-1032.   
[8]Cai Lingru,Zhang Zhanchang,Yang Junjie,et al.A noise-immune Kalman filter for short-term traffic flow forecasting [J].Physica A: Statistical Mechanics and its Applications,2019,536:122601.   
[9] Okutani I, Stephanedes Y J. Dynamic prediction of traffic volume through Kalman filtering theory [J].Transportation Research Part B: Methodological,1984,18(1): 1-11.   
[10] Stathopoulos A, Karlaftis M G. A multivariate state space approach for urban trafc flow modeling and prediction [J].Transportation Research Part C:Emerging Technologies,2003,11 (2): 121-135.   
[11] Hu Wenbin, Yan Liping,Liu Kaizeng,et al.A short-term trafic flow forecasting method based on the hybrid PSO-SVR[J]. Neural Processing Letters,2016,43(1): 155-172.   
[12] Guo Huan,Xiao Xinping,Jeffrey F. Urban road short-term traffic flow forecasting based on the delay and nonlinear grey model[J]. Journal of Transportation Systems Engineering and Information Technology,2013, 13 (6): 60-66.   
[13] Mayrink V, Hippert H S.Ahybrid method using Exponential Smoothing and Gradient Boostingforelectrical shortermload forecastingC// 2016 IEEE Latin American Conference on Computational Intelligence (LA-CCI) . IEEE,2016: 1-6.   
[14] Xie Yuanchang, Zhang Yunlong,Ye Zhirui. Short-Term Traffic Volume Forecasting Using Kalman Filter with Discrete Wavelet Decomposition [J]. Computer-Aided Civil and Infrastructure Engineering,20o7,22 (5): 326-334.   
[15] Wang Yubin,Van Schuppen JH,Vrancken J.Predictionof Trafic Flow at the Boundary of a Motorway Network [J]. IEEE Transactions on Intelligent Transportation Systems,2014,15 (1): 214-227.   
[16] Ingrid Daubechies.The wavelet transform,time-frequency localization and signal analysis [J].Journal ofRenewable& Sustainable Energy,1990, 36 (5): 961-1005.   
[17] Lin Weihua.A Gaussian maximum likelihood formulation for short-term forecasting oftraffic flow [C]/ Intelligent Transportation Systems. IEEE, 2001: 150-155.   
[18]Ma Wentao, Qiu Jinzhe,Liang Junli,et al. Linear Kalman Filtering Algorithm with Noisy Control Input Variable [J]. IEEE Transactions on Circuits and Systems II Express Briefs,2018: 1-1.   
[19] Cai Lingru,Chen Qian,Cai Weihong,et al. SVRGSA: a hybrid learning based model for short-term traffic flow forecasting [J]. IET Intelligent Transport Systems,2019,13 (9): 1348-1355.   
[20] Mackenzie J, Roddick JF, Zito R.An evaluation of HTMand LSTM for short-term arterial traffic flow prediction [J].IEEE Transactions on Intelligent Transportation Systems,2018,20(5): 1847-1857.   
[21] Yang Haofan,Dillon T S, Chang E,et al. Optimized configuration of exponential smoothing and extreme learning machine for traffic flow forecasting[J].IEEE Transactions on Industrial Informatics,2018,15 (1): 23-34.   
[22] Feng Xinxin,Ling Xianyao,Zheng Haifeng,et al. Adaptive multi-kernel SVM with spatial-temporal correlation for short-term traffc flow prediction [J].IEEE Transactions on Intelligent Transportation Systems, 2018,20 (6):2001-2013.   
[23] Zheng Chuanpan,Fan Xiaoliang,Wen Chenglu,et al. Deepstd: Mining spatio-temporal disturbances of multiple context factors for citywide trafficflowprediction[J].IEEE Transactionson Intelligent Transportation Systems,2019.   
[24] Lippi M,Bertini M,Frasconi P.Short-Term Traffc Flow Forecasting: An Experimental Comparison of Time-Series Analysis and Supervised Learning [J].IEEE Transactions on Intelligent Transportation Systems, 2013,14(2):871-882.   
[25] Zhou Teng,Jiang Dazhi,Lin Zhizhe,et al. Hybrid dual Kalman filtering model for short-term traffic flow forecasting [J].IET Intelligent Transport Systems,2019,13 (6):1023-1032.   
[26]王秋莉，李军．基于核学习方法的短时交通流量预测[J].计算机应 用研究,2019 (3): 696-700.(Wang Qiuli,LiJun.Short-term traffic flow forecasting based on kernel learning mathods [J].Application Rsearch of Computers,2019 (3):696-700.)

[27]曹墳，王成，王鑫，高悦尔．基于时空节点选择和深度学习的城市道 路短时交通流预测[J/OL].计算机应用：1-10.http://kns.cnki. net/kcms/detail/51.1307.TP.20191209.1313.008.html. (Cao Yu,Wang Cheng,Wang Xin,et al.Urban road short-term traffic flow prediction based on spatio-temporal node selection and deep learning [J/OL]. Journal of Computer Applications， pp1-1o.htp://kns.cnki. net/kcms/detail/51.1307.TP.20191209.1313.008.html.)

[28]林浩，李雷孝，王慧．支持向量机在智能交通系统中的研究应用综述[J/OL].计算机科学与探索：1-19.http://kns.cnki.net/kcms/detail/11.5602.tp.20200331.1857.004.html.(Lin Hao,LiLeixiao,Wang Hui.A Survey on research and application of supportvector machines in ITS[J/OL].Journal ofFrontiers ofComputer Scienceand Technology,pp 1-19.http://kns.cnki.net/kcms/detail/11. 5602.tp.20200331.1857.004. ht ml.)