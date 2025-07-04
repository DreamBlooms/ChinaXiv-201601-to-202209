# AzureOP:基于WindowsAzure云并行计算的期权定价SaaS

林溢星1,²，赵地3，迟学斌1,2,4，姜金荣1,4(1．中国科学院计算机网络信息中心 高性能计算部，北京 100190;2.中国科学院大学，北京 1049;3.中国科学院计算技术研究所，北京100190;4．中国科学院计算科学应用研究中心，北京100190)

摘要：计算速度对于期权交易者至关重要，关系到如何有效地制定价格并评估相应的风险，而云并行计算提供的随收随付制（pay-as-you-go）可以实现低成本运行。在微软云平台Windows Azure 的基础上，开发了基于云并行计算的期权定价试点云软件AzureOP，该软件以较低的费用提供了低风险和高速度，并给出了AzureOP对于美式期权价格的模拟结果，绘制了对应的期权价格定价曲线和定价曲面。最后，对云并行计算在金融应用上的优势和不足进行了总结和讨论，同时举例说明了试点云软件AzureOP的具体细节。

关键词：云计算；并行计算；SaaS开发；计算金融；期权定价 中图分类号：TP301.4 doi:10.3969/j.issn.1001-3695.2018.01.0016

# AzureOP: parallel computing based SaaS for option pricing on cloud

Lin Yixing1,2, Zhao $\mathrm { D i } ^ { 3 \dagger }$ , Chi Xuebin1,2,4, Jiang Jinrong1, 4 (1.Computer Network Information Center,ChineseAcademyof Sciences,Beijing100l90,China;2.Universityof Chinese AcademyofSciences,Beijing 0o49,China;3.nstituteofComputing Technology,Chinese AcademyofSciences,Beijing 100190,China; 4.Center of Scientific Computing Applications &Research,Chinese Academy of Siences,Beijing 00190, China)

Abstract:Thecomputationalspeedis importantforthecrucialforoptiontraders toeficientlydecidethe priceandevaluatethe corresponding risk,and cloud paralel computing providesalow-cost implementation byproviders’Pay-as-You-Go policy. Based on Microsoft'scloud platformWindowsAzure,developedaoptiopricing'spilotcloudsoftware-AzureOP,thissoftware provided lowrisk and high speed withalowercost,and presented simulationresultsofAzureOPfor AmericanPut,plotted the corresponding option pricingcurve and pricing surface.Finally,makes conclusions and discusses the advantage and the disadvantageofcomputational financeonthecloud,andillustrates thedetailsdevelopmentofpilotcloud software AzureOP. Key words: Cloud computing; parallel computing; SaaS development; computational finance; option pricing

# 0 引言

虽然云计算被定义为计算和存储交付，但作为基于互联网的计算[1-4]，云计算也可以被定义为金融公司和制造公司的基于计算的服务器：计算密集的部分在服务器（云）上完成，结果通过Web接口交付给用户。众所周知，云计算包含三种服务模式：基础架构即服务（IaaS)，平台即服务（PaaS）和软件即服务（SaaS）。当前的公开PaaS 包括MicrosoftWindows Azure,Amazon Web Services，Google App Engine 和 Sun Grid ComputeUtility[5]以及Open Cirrus[]等新兴实验平台。PaaS的一个例子如图1所示。此PaaS基于微软的数据中心（IaaS)，逻辑结构由WindowsAzure 的HPC调度程序和Azure 节点组成。选择好PaaS提供商后，SaaS得到开发，测试和交付，并且成功发布的 SaaS 包括生物信息学[7-16]，图像处理[17]，工程[18]，医学信息[19]，娱乐[20]，金融，社会科学等。

计算金融是一个跨学科的领域，将数理统计建模、分析和计算应用于定价、交易和对冲决策，并分析这些决策的风险。这个领域典型的数理统计技术包括随机分析，蒙特卡洛模拟，微分方程，多元分析，时间序列等。很多通用软件兼容了计算金融，例如MATLAB，Mathematica，Maple和R，另外还有专门用于计算金融的软件，例如Quantifi，StreamBase，Volera和SciFinance。

![](images/50d87147b16c4655345d41bf37cc7a1855da32fad042cea0a48b05512e6bc568.jpg)  
图1Windows Azure HPC 的逻辑结构  
图2AzureOP的界面

除台式电脑外，并行计算还被广泛应用于计算金融领域，例如集群和GPU等平台。云并行计算是云上的并行计算模式，如WindowsAzure 的HPC调度程序，它为金融公司和专业人员提供了可扩展和低成本的并行计算。

期权是一种能在未来某特定时间以特定价格买入或卖出一定数量的某种特定商品的权利。期权可以通过Black-Scholes方程或随机波动模型进行定价，并通过二项式树、蒙特卡洛模拟和有限差分法等数值方法求解。期权定价的计算速度是交易双方取得成功的关键因素之一，云并行计算为满足期权定价的速度需求提供了新的平台。本文在WindowsAzure 的基础上，利用Black-Scholes方程模拟期权定价，并且开发了基于有限差分软件的云并行计算AzureOP进行期权定价。

# 1 AzureOP方法

首先介绍如何在云上使用AzureOP进行期权定价。然后介绍如何设计AzureOP：包括三种Black-Scholes方程的数值求解方案，这三种方案的云并行实现，以及云上使用到的软件，并且在第一次运行之前，将软件部署到WindowsAzure。最后介绍AzureOP的计算结果。

# 1.1软件

由于AzureOP是基于云平台Azure的软件，安装过程由平台配置过程组成，具体细节将在后面讨论。在成功部署之后，除了超级计算和背后的大数据存储的功能，AzureOP的使用类似于任何桌面软件。

AzureOP的GUI如图2所示，AzureOP的界面由三部分组成：“选择选项”，“参数设置"和命令按钮。选项样式可以从“optionselection"部分中选择，参数可以从"parametersetting"部分进行设置。之后，按下"start"按钮启动AzureOP。AzureOP的中间结果存储在Azure blob中，按下"FetchResults"按钮可以将计算结果提取到AzureOP的输出帧。

# 1.2 模型

AzureOP通过求解Black-Scholes方程来做期权定价。Black-Scholes模型是一个二阶偏微分方程，它描述了期权定价从终止条件递归到价格为零的结束时期的过程。从原始文献[21]推导出Black-Scholes方程后，得到：

$$
\begin{array} { r } { \frac { \partial V } { \partial t } + \frac { 1 } { 2 } \delta ^ { 2 } S ^ { 2 } \frac { \partial ^ { 2 } V } { \partial S ^ { 2 } } + r S \frac { \partial V } { \partial S } - r V = 0 , } \end{array}
$$

其中： $V$ 是期权价格， $s$ 是股票价格， $t$ 是时间， $\delta$ 是股票收益

率的波动率， $\boldsymbol { r }$ 是利率。方程（1）可以进一步简化为更简单的形式，如热传导方程。美式期权的左边界条件为

$$
V _ { 0 } ^ { t } = K ,
$$

而欧氏期权则为

$$
V _ { 0 } ^ { t } = K e ^ { - ( T - t ) } ,
$$

其中 $K$ 是常数，看涨期权的左边界条件为

$$
V _ { 0 } ^ { t } = 0 ,
$$

并且期权的右边界条件为

$$
V _ { S } ^ { t } = 0 ,
$$

期权价格预测的最终条件为

$$
V _ { S } ^ { T } = m a x ( K - S , 0 ) ,
$$

其中 $T$ 是时间的步长总数。Black-Scholes方程的关键思想是一方可以用方程式中的“正确"价格来对冲资产以避免所有的风险，所以定价的计算速度很重要。Black-Scholes方程的求解有两种方法：分析方法和数值方法。文献[21]中，Martin等人开发了近似解析解，而Black-Scholes方程的数值解法包括有限差分法[22,23]、蒙特卡洛模拟[24-26]、路径积分[27]、机器学习[28]等。本文用有限差分法求解Black-Scholes方程。

AzureOP 口 X Option option style sell or buy 04404304204153765 American -Put 034033032031030290.28027026025 024023022021020190.18017016015 Parameter 0.140.130.120.110.10.090.080070.06005 004003002001000000000000000 totaltime to 0.01 000000000000 000000000 000000000000 t 1.00 VAN □ r(interests rate) 0.01 000000000000000000000000 000000000000 K (strike price) 0.50 curranttimestep179:0.50.490.480.470.460.45 0.440.430.420.410.40.390.380.370.360.35 time step 250 0.340.330.320.310.30.290.280.270.260.25 grid step 100 5 scheme explicit 004003002001000000000000000 000000000000000000000000 000000000000 start Fetch Results curnttmestp178:0.50.490.480.470.460.45 0.440.430.420.410.40.390.380.370.360.35 Close About 04023022187605 Adanced Computing Co.Ltd 2012

# 1.3 显式方案

AzureOP由三个方案组成，用于数值求解Black-Scholes方程：显式方案、隐式方案和Crank-Nicolson方案。通过显式方案离散Black-Scholes方程，本文定义下面的算子：

$$
\begin{array} { r } { \frac { \partial V } { \partial t } = \frac { V _ { i } ^ { n + 1 } - V _ { i } ^ { n } } { \Delta t } , } \end{array}
$$

$$
\begin{array} { r } { \frac { \partial ^ { 2 } V } { \partial S ^ { 2 } } = \frac { V _ { i + 1 } ^ { n + 1 } - 2 V _ { i } ^ { n + 1 } + V _ { i - 1 } ^ { n + 1 } } { ( \Delta S ) ^ { 2 } } , } \end{array}
$$

$$
\begin{array} { r } { \frac { \partial V } { \partial S } = \frac { V _ { i + 1 } ^ { n + 1 } - V _ { i - 1 } ^ { n + 1 } } { 2 \Delta S } , } \end{array}
$$

其中： $n$ 是时间步长的计数器， $i$ 是网格（股票价格）的计数器。将这些算子（5.1-5.3）代入方程（1）得到

$$
V _ { i } ^ { n } = A _ { i } V _ { i - 1 } ^ { n + 1 } + B _ { i } V _ { i } ^ { n + 1 } + C _ { i } V _ { i + 1 } ^ { n + 1 } ,
$$

其中，

$$
\begin{array} { r } { A _ { i } = \frac { 1 } { 1 + r \Delta t } \Big ( \frac { \delta ^ { 2 } S ^ { 2 } \Delta t } { 2 ( \Delta S ) ^ { 2 } } - \frac { r S \Delta t } { 2 \Delta S } \Big ) , } \end{array}
$$

$$
\begin{array} { r } { B _ { i } = \frac { 1 } { 1 + r \Delta t } \Big ( 1 - \frac { \delta ^ { 2 } S ^ { 2 } \Delta t } { ( \Delta S ) ^ { 2 } } \Big ) , } \end{array}
$$

$$
\begin{array} { r } { C _ { i } = \frac { 1 } { 1 + r \Delta t } \left( \frac { \delta ^ { 2 } S ^ { 2 } \Delta t } { 2 ( \Delta S ) ^ { 2 } } + \frac { r S \Delta t } { 2 \Delta S } \right) } \end{array}
$$

由方程（6.1）可以得到，期权价格从最终状态（4）向当前时间步长 $n$ 后向递归演变，每个网格（股票价格）的期权价格从1到 $_ { I - 1 }$ 进行逐一计算，其中 $I$ 是网格步长的总数。期权价格预测的左边界条件可以被离散化为：

$$
V _ { 0 } ^ { n } = K e ^ { - ( T - n \Delta t ) } ,
$$

或者

$$
V _ { 0 } ^ { n } = 0 ,
$$

期权价格方程（3.2）的右边界条件可以被离散化为：

$$
V _ { I } ^ { n } = 0
$$

其中V和V不需要计算，可以直接用边界条件代替。另外，为了保持显式方案的稳定性，应该满足条件△t≤。

# 1.4隐式方案

AzureOP还可以通过隐式方案离散Black-Scholes方程，算子定义如下：

$$
\begin{array} { r } { \frac { \partial ^ { 2 } V } { \partial S ^ { 2 } } = \frac { V _ { i + 1 } ^ { n } - 2 V _ { i } ^ { n } + V _ { i - 1 } ^ { n } } { ( \Delta S ) ^ { 2 } } , } \end{array}
$$

$$
V _ { i } ^ { n + 1 } = A _ { i } V _ { i - 1 } ^ { n } + B _ { i } V _ { i } ^ { n } + C _ { i } V _ { i + 1 } ^ { n }
$$

$$
\begin{array} { r } { V = \frac { \left( V _ { i } ^ { n + 1 } + V _ { i } ^ { n } \right) } { 2 } . } \end{array}
$$

将方程（5.1）（11.1）（11.2）和（11.3）代入Black-Scholes方程(1)，可以得到：

$$
A _ { i } V _ { i - 1 } ^ { n } + B _ { i } V _ { i } ^ { n } + C _ { i } V _ { i + 1 } ^ { n } = f _ { i } ,
$$

其中：

$$
\begin{array} { r } { \frac { \partial V } { \partial S } = \frac { \left( V _ { i + 1 } ^ { n + 1 } - V _ { i - 1 } ^ { n + 1 } \right) + \left( V _ { i + 1 } ^ { n } - V _ { i - 1 } ^ { n } \right) } { 4 \Delta S } , } \end{array}
$$

$$
\begin{array} { r } { A _ { i } = \left( \frac { 1 } { 4 } \delta ^ { 2 } i ^ { 2 } - \frac { 1 } { 4 } r i \right) , \qquad ( 1 2 . 1 \times \frac { 1 } { 4 } ) } \\ { B _ { i } = \left( - \frac { 1 } { \Delta t } - \frac { 1 } { 2 } \delta ^ { 2 } i ^ { 2 } - \frac { 1 } { 2 } r \right) , \qquad ( 1 2 . 1 \times \frac { 1 } { 4 } ) } \\ { C _ { i } = \left( \frac { 1 } { 4 } \delta ^ { 2 } i ^ { 2 } + \frac { 1 } { 4 } r i \right) , \qquad ( 1 2 . 4 \times \frac { 1 } { 4 } ) } \\ { f _ { i } = \left( - \frac { 1 } { 4 } \delta ^ { 2 } i ^ { 2 } + \frac { 1 } { 4 } r i \right) V _ { i - 1 } ^ { n + 1 } + \left( - \frac { 1 } { \Delta t } + \frac { 1 } { 2 } \delta ^ { 2 } i ^ { 2 } + \frac { 1 } { 2 } r \right) V _ { i } ^ { n + 1 } + } \\ { \left( - \frac { 1 } { 4 } \delta ^ { 2 } i ^ { 2 } - \frac { 1 } { 4 } r i \right) V _ { i + 1 } ^ { n + 1 } \qquad ( 1 2 . 4 \times \frac { 1 } { 4 } ) } \end{array}
$$

将方程（12.1）转换成矩阵形式，可以得到：

$$
\left[ \begin{array} { c c c c c c c } { B _ { 1 } } & { C _ { 1 } } & { 0 } & { \cdots } & { 0 } & { 0 } & { 0 } \\ { A _ { 2 } } & { B _ { 2 } } & { C _ { 2 } } & { \cdots } & { 0 } & { 0 } & { 0 } \\ { \vdots } & { \vdots } & { \vdots } & { \ddots } & { \vdots } & { \vdots } & { \vdots } \\ { 0 } & { 0 } & { 0 } & { \cdots } & { A _ { l - 2 } } & { B _ { l - 2 } } & { C _ { l - 2 } } \\ { 0 } & { 0 } & { 0 } & { \cdots } & { 0 } & { A _ { l - 1 } } & { B _ { l - 1 } } \end{array} \right] \left[ \begin{array} { l } { V _ { 1 } ^ { n } } \\ { V _ { 2 } ^ { n } } \\ { \vdots } \\ { V _ { l - 2 } ^ { n } } \\ { V _ { l - 1 } ^ { n } } \end{array} \right] = \left[ \begin{array} { l } { f _ { 1 } ^ { n + 1 } - A _ { 1 } V _ { 0 } ^ { n } } \\ { f _ { 2 } ^ { n + 1 } } \\ { \vdots } \\ { f _ { l - 2 } ^ { n + 1 } } \\ { f _ { l - 1 } ^ { n + 1 } - C _ { l - 1 } V _ { l } ^ { n } } \end{array} \right] = \left[ \begin{array} { l } { F _ { 1 } } \\ { F _ { 2 } } \\ { \vdots } \\ { F _ { l - 2 } } \\ { F _ { l - 1 } } \end{array} \right] .
$$

$$
\begin{array} { r } { \frac { \partial V } { \partial S } = \frac { V _ { i + 1 } ^ { n } - V _ { i - 1 } ^ { n } } { 2 \Delta S } , } \end{array}
$$

将方程（5.1)，（8.1）和（8.2）代入Black-Scholes方程（1），可以得到：

其中：

$$
\begin{array} { r } { A _ { i } = \frac { \Delta t } { 2 } \Big ( - \frac { \delta ^ { 2 } S ^ { 2 } } { ( \Delta S ) ^ { 2 } } + \frac { r S } { \Delta S } \Big ) , } \end{array}
$$

$$
\begin{array} { r } { B _ { i } = 1 + \frac { \delta ^ { 2 } S ^ { 2 } \Delta t } { ( \Delta S ) ^ { 2 } } + r \Delta t , } \end{array}
$$

$$
\begin{array} { r } { C _ { i } = - \frac { \Delta t } { 2 } \Big ( \frac { \delta ^ { 2 } S ^ { 2 } } { ( \Delta S ) ^ { 2 } } + \frac { r S } { \Delta S } \Big ) . } \end{array}
$$

将方程（9.1）转换成矩阵形式，可以得到

$$
\left[ { \begin{array} { c c c c c c c } { B _ { 1 } } & { C _ { 1 } } & { 0 } & { \cdots } & { 0 } & { 0 } & { 0 } \\ { A _ { 2 } } & { B _ { 2 } } & { C _ { 2 } } & { \cdots } & { 0 } & { 0 } & { 0 } \\ { \vdots } & { \vdots } & { \vdots } & { \ddots } & { \vdots } & { \vdots } & { \vdots } \\ { 0 } & { 0 } & { 0 } & { \cdots } & { A _ { I - 2 } } & { B _ { I - 2 } } & { C _ { I - 2 } } \\ { 0 } & { 0 } & { 0 } & { \cdots } & { 0 } & { A _ { I - 1 } } & { B _ { I - 1 } } \end{array} } \right] \left[ { \begin{array} { c } { V _ { 1 } ^ { n } } \\ { V _ { 2 } ^ { n } } \\ { \vdots } \\ { V _ { I - 2 } ^ { n } } \\ { V _ { I - 1 } ^ { n } } \end{array} } \right] = \left[ { \begin{array} { c } { V _ { 1 } ^ { n + 1 } - A _ { 1 } V _ { 0 } ^ { n } } \\ { V _ { 2 } ^ { n + 1 } } \\ { \vdots } \\ { V _ { I - 2 } ^ { n + 1 } } \\ { V _ { I - 1 } ^ { n + 1 } - C _ { I - 1 } V _ { I } ^ { n } } \end{array} } \right] = \left[ { \begin{array} { c } { F _ { 1 } } \\ { F _ { 2 } } \\ { \vdots } \\ { F _ { I - 2 } } \\ { F _ { I - 1 } } \end{array} } \right] \left( { \begin{array} { c } { V _ { 1 } ^ { n } } \\ { E _ { 2 } ^ { n } } \\ { \vdots } \\ { E _ { I - 1 } ^ { n } } \end{array} } \right) = \left[ { \begin{array} { c } { V _ { 1 } ^ { n } } \\ { V _ { 2 } ^ { n } } \\ { \vdots } \\ { V _ { I - 1 } ^ { n } } \\ { V _ { I - 1 } ^ { n } } \end{array} } \right] \left[ { \begin{array} { c } { V _ { 1 } ^ { n } } \\ { V _ { 2 } ^ { n } } \\ { V _ { 2 } ^ { n } } \end{array} } \right] = \left[ { \begin{array} { c } { V _ { 1 } ^ { n } } \\ { V _ { 2 } ^ { n } } \\ { \vdots } \\ { V _ { I - 1 } ^ { n } } \end{array} } \right] \left[ { \begin{array} { c } { V _ { 1 } ^ { n } } \\ { V _ { 2 } ^ { n } } \end{array} } \right] .
$$

其中 $F _ { i }$ 是线性系统方程（10）的等式右侧部分。为了求解系统方程（10)，使用三对角矩阵算法（TDMA)。与显式方案相比，隐式方案在任何 $\Delta t$ 和 $\Delta { } _ { S }$ 情况下都更稳定。

另外，由于线性系统方程（10）的系数矩阵有三对角线（左对角线，中对角线和右对角线)，所以这些对角线的信息被压缩成三个矢量（左矢量，中矢量和右矢量)，并且忽略所有的零。因此，在一个 $I ^ { * } I$ 的系数矩阵中，左矢量的大小为I-1，中矢量的大小为 $I _ { \mathrm { : } }$ ，右矢量的大小为 $_ { I - 1 }$ 。

# 1.5Crank-Nicolson 方案

AzureOP求解Black-Scholes方程的第三种内置方案是Crank-Nicolson方案，算子定义如下：

$$
\begin{array} { r } { \frac { \partial ^ { 2 } V } { \partial S ^ { 2 } } = \frac { \left( V _ { i + 1 } ^ { n + 1 } - 2 V _ { i } ^ { n + 1 } + V _ { i - 1 } ^ { n + 1 } \right) + \left( V _ { i + 1 } ^ { n } - 2 V _ { i } ^ { n } + V _ { i - 1 } ^ { n } \right) } { 2 ( \Delta S ) ^ { 2 } } , } \end{array}
$$

其中 $F _ { i }$ 是线性系统方程(13)的等式右侧部分，并且采用TDMA来求解该系统。

# 1.6 云并行计算实现

AzureOP由上述三种有限差分方案的云并行计算实现组成，使用的集成开发环境是MSVisualStudio2011（MS-VS）。

为了在尽可能低的成本下实现快速收敛，使用MS-MPI库对Black-Scholes方程的三种有限差分方案进行并行化处理，并在微软的WindowsAzure上运行，以获得可扩展的实例数量及满足用户对速度的需求。

在MS-VS上开发并行代码，首先需要安装MPI库，本文选择的 MPI 库是 HPCPack 2008R2 MS-MPIRedistributablePackage。安装完成后，重复检查MS-VS以确保HPCPACK库被正确引用。然后，利用并行库MS-VS开发了并行显式方案、并行隐式方案和并行Crank-Nicolson方案。

在显式方案的方程（6.1）中，求解当前时间步长 $\mathbf { } V _ { i } ^ { n }$ 的期权价格需要后续三个时间步长的值： ${ V _ { i - 1 } } ^ { n + 1 }$ ， $V _ { i } ^ { n + 1 }$ 和 ${ { V } _ { i + 1 } } ^ { n + 1 }$ 。在求解当前时间的期权价格时，由于后续时间步长的期权价格的所有值都是可用的，所以这些值可以同时求解。因此本文设计了一个如图3和4所示的云并行显式方案。

图3描述了显式方案的云并行算法。如图3所示，每个时间步长中期权价格的值是同时求解的，而不是逐一求解，并且是在当前时间步长到下一个时间步长之间的时间间隔中进行求解。

图4描述了AzureOP显式方案中的实现。如图4所示，MS-MPI进程分为三类：主服务器（初始进程)，网格服务器和工作节点。主服务器（初始进程）负责存储和更新期权定价的所有值，网格服务器负责计算每个网格的期权定价，节点工作人员则负责计算方程（6.2）中的 $A _ { i }$ ，方程（6.3）中的 $B _ { i }$ 和方

程（6.4）中的 $C _ { i } ,$ 0

![](images/52bbae8bc2c42c5e4cbc2582533223afa1ca85ac0ab11ff3032266d6440cb7ee.jpg)  
图3显式方案的云并行算法(算法1)

![](images/d640efd080a6ea0b21174d79a9feda7eb7dacec754554682de4afa09f6cf5c26.jpg)  
图4AzureOP显式方案的实现

为了更加清晰地表达，图3和4中讨论的云并行显式方案也可以如算法1所述：

算法1基于云并行计算的显式方案。

a）发起方（主服务器）将终止条件（4）初始化为 $V i n { + } 1$   
b）主服务器将方程（7.1）和（7.2）的边界条件设置为 $V _ { i } ^ { n + 1 }$   
c）在每一个时间步长中：  
（a）网格服务器初始化 ${ V _ { i } } ^ { n }$   
（b）计算方程（6.2）-（6.4）中的 $A _ { i }$ ， $B _ { i }$ 和 $c _ { i }$ ，随后工作节点将这些值发送给对应的网格服务器；  
（c）网格服务器计算 ${ V _ { i } } ^ { n }$ ，并发送给主服务器；  
（d）主服务器将 ${ v _ { i } } ^ { n }$ 保存到Windows Azure Storage上的价格容器;（e）主服务器根据 ${ v _ { i } } ^ { n }$ 更新 $V _ { i } ^ { n + 1 }$

结束

![](images/5c511a8845791c0ff0c738fba7764f04d5b8d1dd6d8fbd5f2acef5d4b29e40aa.jpg)  
图5隐式方案的云并行算法 (算法2)

在开发了算法1的云并行显式方案后，本文开发了云并行隐式方案。在隐式方案的线性系统方程（10）中，通过求解系统可以同时得到期权价格 $\mathbf { } V _ { i } ^ { n }$ 的所有值。为了加速这一过程，在显式方案中开发的云并行实现策略的基础上，可以计算出工作节点中的系数矩阵，并解决主服务器中的线性系统问题。因此本文设计了一个如图5和6所示的云并行隐式方案。

图5描述了隐式方案的云并行算法。如图5所示，利用图6中列出的服务器，可以并行地计算和组装系数矩阵，当前时间步长的期权价格的所有值也可以由线性系统方程(10)求解，并且此过程一直持续。

![](images/c40a504f102b8c8ee33bf1e0ce85ad93ccaf939d435c668d2b212267bc301453.jpg)  
图6AzureOP 隐式方案的实现

图6描述了AzureOP隐式方案的实现。从图6可以看到，MS-MPI进程分为三类：主服务器（发起者），网格服务器和工作节点。主服务器负责存储和更新期权价格的值，组装方程（10)的系数矩阵和其右侧矢量 $F _ { i }$ ，并求解线性系统。网格服务器负责计算方程（10）的右侧矢量 $F _ { i }$ ，并收集方程（9.2）的 $A _ { i }$ ，方程（9.3）的 $B _ { i }$ 或方程（9.4）的 $C _ { i }$ 。节点工作人员则负责计算方程（9.2）的 $A _ { i }$ ，方程（9.3）的 $B _ { i }$ 或方程（9.4）的 $C _ { i }$ 的值。

云并行计算的隐式方案也可以如算法2所述：

算法2基于云并行计算的隐式方案。

a）发起方（主服务器）将终止条件（4）初始化为 $v i n + 1$   
b）主服务器将方程（7.1）和（7.2）的边界条件设置为 $V _ { i } { } ^ { n + 1 }$ ·  
c）在每一个时间步长中：  
（a）网格服务器初始化 ${ v _ { i } } ^ { n }$   
（b）计算方程 $( 9 . 2 ) \sim ( 9 . 4 )$ 中的 $A _ { i }$ ， $B _ { i }$ 和 $c _ { i }$ ，随后工作节点将这些值发送给对应的网格服务器；  
（c）网格服务器计算方程（10）中的 $F _ { i }$ 值，并发送给主服务器；(d)主服务器组装系数矩阵和右侧矢量 $\boldsymbol { F } _ { i }$ ，并求解线性系统方程（10)；（e）主服务器将 ${ \boldsymbol { V _ { i } } } ^ { n }$ 保存到Windows Azure Storage 上的价格容器;（f）主服务器根据 $\boldsymbol { V _ { i } } ^ { n }$ 更新 $V _ { i } ^ { n + 1 }$ ：

结束

云并行算法的Crank-Nicolson方案也可以类比图5的描述。如图5所示，与隐式方案类似，方程（13）中的系数矩阵被同时计算和组装，当前时间步长的所有期权价格的值由线性系统方程（13）进行求解，并且这个计算过程在所有时间步长中持

续。

图7描述了AzureOP的Crank-Nicolson方案的实现。主服务器负责存储和更新期权价格的值，组装系数矩阵和右侧矢量，并求解线性系统方程（13)。网格服务器负责计算右侧矢量的 $F _ { i }$ 值，并收集方程（12.2）的 $A _ { i }$ ，方程（12.3）的 $B _ { i }$ ，方程（12.4）的 $C _ { i }$ 或方程（12.5）的 $f _ { i }$ 的值。如图7所示，与图6中实现的隐式方案相同，图7中的工作节点负责计算方程（12.2）的 $A _ { i }$ 方程（12.3）的 $B _ { i }$ ，方程（12.4）的 $C _ { i }$ 或方程（12.5）的 $f _ { i }$ 的值。

![](images/af78d13e15cff3a93b4548a6ddefb3ba975bf9755f2c4614095cf17b29c4ab64.jpg)  
图7AzureOP 的Crank-Nicolson 方案的实现

云并行算法的Crank-Nicolson方案也可以如算法3所述：算法3 基于云并行计算的Crank-Nicolson 方案。

a）发起方（主服务器）将终止条件（4）初始化为 $v i n + 1$   
b）主服务器将方程（7.1）和（7.2）的边界条件设置为 $V _ { i } { } ^ { n + 1 }$   
c）在每一个时间步长中：  
（a）主服务器初始化 ${ V _ { i } } ^ { n }$ ：：  
（b）计算方程（12.2）-（12.5）中的 $A _ { i }$ ， $B _ { i }$ ， $c _ { i }$ 和fi，随后工作节点将这些值发送给对应的网格服务器；  
（c）网格服务器计算方程（13）中的 $f _ { i }$ 值，并发送给主服务器；(d)主服务器组装系数矩阵和右侧矢量 ${ \mathbf { \mathscr { f } } } _ { i }$ ，并求解线性系统方程（13)；（e）主服务器将 ${ V _ { i } } ^ { n }$ 保存到Windows Azure Storage上的价格容器;（f）主服务器根据 ${ v _ { i } } ^ { n }$ 更新 $V _ { i } ^ { n + 1 }$

结束

# 1.7Windows Azure 的安装

成功安装AzureOP，首先需要一个WindowsAzure帐户。之后，使用WindowsAzureHPC调度程序来提交、管理和获取三种方案的代码结果，其中调度程序包括工作节点（头节点，计算节点和前端节点）和数据存储（WindowsAzure Storage）。WindowsAzureHPC调度程序将WindowsAzure 转变为基于云的超级计算机。所有步骤都需要通过在AppConfigure 应用程序中进行配置并填写WindowsAzure帐户、管理员帐户以及头节点、计算节点、前端节点的数量等信息来完成的。运行命令hpcfwutil可以打开计算机节点间通信的防火墙配置。

WindowsAzureHPC调度程序准备就绪后，远程桌面连接即可访问计算节点实例。之后，开发的代码可以通过WindowsAzureWebRole的图形用户界面提交给WindowsAzure。第一次安装之后，后续AzureOP的使用都不需要涉及本节中的所有

步骤。

# 2 计算结果

本章将介绍使用AzureOP进行期权定价的计算结果，并将显式方案，隐式方案和Crank-Nicolson方案的结果一一列出。

在显式方案中，总时间为0.01，离散化为250、500或1000步，股价St为1，离散化为25、50或100。AzureOP的时间成本和费用如表1所示；时间步长 $= 2 5 0$ 、网格步长 $= 1 0 0$ （ $\mathbf { \nabla } \cdot \boldsymbol { I } =$ 100)时的定价曲面计算结果如图8所示；显式方案在 $t = 1 . 0 0$ ，时间步长 $= 2 5 0$ 和 $I = 1 0 0$ 时的定价曲线如图9所示；显式方案在 $\scriptstyle s = 0 . 4 9$ （s是股票价格的当前值)，时间步长 $= 2 5 0$ 和 $I =$ 100时的定价曲线如图10所示。

在隐式方案中，总时间为1，离散化为250、500或1000步，股票价格 St为1，离散化为25、50或100。AzureOP的时间成本和费用如表2所示；时间步长 $= 2 5 0$ 、网格步长 $= 1 0 0$ $\mathit { \Omega } _ { \left[ I \right] } ^ { \prime } = 1 0 0$ ）时的定价曲面计算结果如图11所示；隐式方案在 $t$ $= 1 . 0 0$ ，时间步长 $= 2 5 0$ 和 $I = 1 0 0$ 时的定价曲线如图12所示；隐式方案在 $\begin{array} { r } { s = 0 . 0 8 } \end{array}$ ，时间步长 $= 2 5 0$ 和 $I = 1 0 0$ 时的定价曲线如图13所示。

在Crank-Nicolson方案中，总时间为1，离散化为250、500或1000步，股价St为1，离散化为25、50或100。AzureOP的时间成本和费用如表3所示；时间步长 $= 2 5 0$ 、网格步长 $\mathbf { \Sigma } = \mathbf { \Sigma }$ 100（ $\boldsymbol { I } = 1 0 0$ ）时的定价曲面计算结果如图14所示；Crank-Nicolson方案在 $t = 1 . 0 0$ ，时间步长 $= 2 5 0$ 和 $I = 1 0 0$ 时的定价曲线如图15所示；Crank-Nicolson方案在 $s = 0 . 1 7$ ，时间步长$= 2 5 0$ 和 $\boldsymbol { I } = 1 0 0$ 时的定价曲线如图16所示。

本文选择的计算实例规模非常小，一共购买了25个实例，且共享CPU内核和 $7 6 8 ~ \mathrm { M B }$ 内存，每小时收费0.02美元。

表1是AzureOP选择显式方案的计算结果。从表1可以得到，显式方案的时间成本从几分钟到几小时不等，而计算的开销很低。因此在保证最低费用的情况下，可以选择一个最佳的参数时间步长和网格步长，以获得良好的模拟结果，表1的最优选择是时间步长 $: = 1 0 0 0$ 、 $I = 5 0$ 。

图8是Azure显式方案的计算结果。从图8可以看到，随着时间步长的增加，期权价格几乎保持不变，出现这种情况的原因是，为了满足显式方案稳定性的要求，本文选择了一个非常小的 $\Delta t$ ，约等于 $1 0 ^ { - 5 }$ ，这导致了一个非常小的时间间隔 $T =$ 0.01，因此显式方案几乎没有进展。

表1AzureOP显式方案的时间花销和费用  

<html><body><table><tr><td rowspan="2">时间</td><td colspan="2">网格步长=25</td><td colspan="2">网格步长=50</td><td colspan="2">网格步长=100</td></tr><tr><td>步长 时间花销/s</td><td>费用/美元</td><td>时间花销/s</td><td>费用/美元</td><td>时间花销/s</td><td>费用/美元</td></tr><tr><td>250</td><td>55.60</td><td>0.10</td><td>202.44</td><td>0.10</td><td>1096.21</td><td>0.10</td></tr><tr><td>500</td><td>219.37</td><td>0.10</td><td>791.70</td><td>0.10</td><td>4339.11</td><td>0.20</td></tr><tr><td>1000</td><td>877.07</td><td>0.10</td><td>3145.75</td><td>0.10</td><td>17319.28</td><td>0.50</td></tr></table></body></html>

![](images/629d9c897f14cab127551594b7124647d1924335b679fc16e234ef68dccbfeee.jpg)  
图8时间步长 $= 2 5 0$ ，网格步长 $: = 1 0 0$ 0 $\scriptstyle \mathbf { \mathit { T } = 0 . 0 1 }$ ${ \cal S } _ { t } { = } 1 . 0 0$ $\scriptstyle \delta = 0 . 3 0$ $_ { r = 0 . 0 1 }$ $K { = } 0 . 5 0 \rangle$ 时，显式方案的定价曲面

为了比较不同时间步长的计算结果，本文绘制了 $t = 1 . 0 0$ 以及时间步长分别为250、500和1000时的期权价格数值结果，如图9所示。

![](images/59505d4e24a32d772cb2a1ab7ca2b8b183e49a9f3ab39aeaa709d23dcea7a66e.jpg)  
图9时间步长 $: = 2 5 0$ ，网格步长 $: = 1 0 0$ 0 $_ { t = 1 . 0 0 }$ ， $\scriptstyle { T = 0 . 0 1 }$ 5 ${ \cal S } _ { t } { = } 1 . 0 0$ $\scriptstyle \delta = 0 . 3 0$ $_ { r = 0 . 0 1 }$ $K { = } 0 . 5 0 \$ 时，显式方案的定价曲线

图9描绘了显式方案的期权价格数值结果。从图9中可以 看到，迭代次数等于250、500和1000的期权价格数值结果完 全一致。时间步长的选择不会影响期权价格预测数值结果的精 度，但会影响数值结果的解析度。

为了研究期权价格随时间进度产生的变化，本文绘制了 $s$ $= 0 . 4 9$ ，以及时间步长分别为250、500和1000时的期权价格数值结果，如图10所示。

![](images/c4c80e13105c517caa119e1f3636e617f1885319dffa653ccc529c0f3c46be70.jpg)  
图10时间步长 $= 2 5 0$ 股票当前价格 $\scriptstyle \cdot = 0 . 4 9$ ，网格步长 $= 1 0 0 ( \mathrm { T } = 0 . 0 1$ $\mathrm { S t } { = } 1 . 0 0$ $\delta \mathrm { = } 0 . 3 0$ $\scriptstyle 1 = 0 . 0 1$ ， $\mathrm { K } { = } 0 . 5 0 \$ 时，显式方案的定价曲线

从图10可以看出，迭代次数等于250、500和1000的期权价格数值结果完全一致，说明时间步长的选择不影响期权价格的数值结果。然而，随着时间的推移，期权价格几乎没有发生变化，原因正如上文讨论的。

在分析显式方案的结果之后，看一下隐式方案的结果，如表2、图11\~13所示。表2是隐式方案的计算结果。从表2可以看出，虽然隐式方案的时间成本从几分钟到几小时不等，但时间步长和网格步长每个组合的开销都很低。参数的最佳选择是时间步长 $= 1 0 0 0$ ， $I = 5 0$ 和时间步长 $= 5 0 0$ ， $I = 1 0 0$ 。

表2AzureOP隐式方案的时间花销和费用  

<html><body><table><tr><td rowspan="2">时间</td><td colspan="2">网格步长=25</td><td colspan="2">网格步长=50</td><td colspan="2">网格步长=100</td></tr><tr><td>时间花销/s</td><td>费用/美元</td><td>时间花销/s</td><td>费用/美元</td><td>时间花销/s</td><td>费用/美元</td></tr><tr><td>250</td><td>50.21</td><td>0.10</td><td>168.20</td><td>0.10</td><td>655.56</td><td>0.10</td></tr><tr><td>500</td><td>199.07</td><td>0.10</td><td>660.41</td><td>0.10</td><td>2600.02</td><td>0.10</td></tr><tr><td>1000</td><td>786.28</td><td>0.10</td><td>2607.49</td><td>0.10</td><td>10282.66</td><td>0.30</td></tr></table></body></html>

比较表1和2可以得到，几乎每个时间步长和网格步长的组合中，隐式方案都比显式方案快。当期权到期时，期权价格无限趋近于0。

图11是隐式方案的计算结果。从图11可以看出， $T = 0 . 0 1$ 的时间间隔足够长，因此随着时间的推进，当期权到期时，期权价格接近零。比较图8和11可以得到，图11比图8更平滑，原因在于隐式方案选定的时间间隔 $T$ 远大于显式方案的时间间隔。

![](images/d25f93dbcec99c526626c8ffdf060b5a9df1ea2b11f32d42f2939f27a6256a7e.jpg)  
图11时间步长 $= 2 5 0$ ，网格步长 $= 1 0 0$ ( $\scriptstyle \mathbf { \mathit { T } = 0 . 0 1 }$ 5 ${ \cal S } _ { t } { = } 1 . 0 0$ 5 $\scriptstyle \delta = 0 . 3 0$ 5 $_ { r = 0 . 0 1 }$ $K { = } 0 . 5 0 \rangle$ 时，隐式方案的定价曲面

图12绘制了隐式方案的期权价格数值结果。从图12可以 看到，迭代次数等于250、500和1000的期权价格数值结果完 全一致。时间步长的选择不会影响期权价格预测数值结果的精 度，但会影响数值结果的解析度。

![](images/827f268804b5110e849c27100bdfd390edcccbd5fd845a66ab23ca4b574b26a1.jpg)  
图12时间步长 $= 2 5 0$ ，网格步长 $= 1 0 0 \ ( t { = } 1 . 0 0 , T { = } 1 . 0 0 , S _ { t } { = } 1 . 0 0 , \delta { = } 0 . 3 0 ,$ $_ { r = 0 . 0 1 }$ 5 $K { = } 0 . 5 0$ ）时，隐式方案的定价曲线

为了研究随时间变化的特定股票价格，本文绘制了隐式方案在 $\begin{array} { r } { s = 0 . 0 8 } \end{array}$ 时的期权价格曲线，如图13所示。从图13可以看出，迭代次数等于250、500和1000的期权价格数值结果完全一致。与显式方案相同，时间步长的选择不会影响期权价格预测数值结果的精度，但会影响数值结果的解析度。

![](images/4cb7d7ba3e85bde60de0a464df4cba5774c615356daaadfe7d0b2b30ff12c3dd.jpg)  
图13时间步长 $: = 2 5 0$ ，股票当前价格 $_ { - 0 . 0 8 }$ ，网格步长 $\scriptstyle : = 1 0 0$ 0 $\scriptstyle \overbrace { I = 1 0 . 0 0 }$ ${ \cal S } _ { t } { = } 1 . 0 0$ $\scriptstyle \delta = 0 . 3 0$ $_ { r = 0 . 0 1 }$ $K { = } 0 . 5 0 \$ 时，隐式方案的定价曲线

从图13还可以看出，迭代次数等于250、500和1000的期权价格数值结果完全一致，这意味着时间步长的选择不会影响期权价格预测数值结果的精度，但会影响数值结果的解析度。

最后，将计算结果绘制出来，如表3、图14\~16所示。表3是Crank-Nicolson方案的计算结果。从表3可以看到，Crank-Nicolson方案的时间成本从几分钟到几小时不等，费用也很低。时间步长和网格步长参数的最佳组合是时间步长 $: = 1 0 0 0$ ，网格步长 $: = 5 0$ 和时间步长 $= 5 0 0$ ，网格步长 $= 1 0 0$ 。

表3AzureOP的Crank-Nicolson方案的时间花销和费用  

<html><body><table><tr><td rowspan="2">时间</td><td colspan="2">网格步长 =25</td><td colspan="2">网格步长=50</td><td colspan="2">网格步长=100</td></tr><tr><td>时间花销/s</td><td>费用/美元</td><td>时间花销/s</td><td>费用/美元</td><td>时间花销/s</td><td>费用/美元</td></tr><tr><td>250</td><td>57.87</td><td>0.10</td><td>198.27</td><td>0.10</td><td>782.11</td><td>0.10</td></tr><tr><td>500</td><td>228.35</td><td>0.10</td><td>788.86</td><td>0.10</td><td>3112.62</td><td>0.10</td></tr><tr><td>1000</td><td>905.65</td><td>0.10</td><td>3125.20</td><td>0.10</td><td>12418.10</td><td>0.30</td></tr></table></body></html>

图14是具有特定参数的Crank-Nicolson方案的定价曲面，从图14可以看到，随着时间的推移，当期权到期时，期权价格无限趋近于零。

![](images/1b39f46d95eaa5c07358c0702808e57c95e2cdae2312e32a5f89acdc9daf9e66.jpg)  
图14时间步长 $\scriptstyle = 2 5 0$ ，网格步长 $= 1 0 0$ 0 $T { = } 1 . 0 0$ ${ \cal { S } } _ { t } = 1 . 0 0$ $\scriptstyle \delta = 0 . 3 0$ $_ { r = 0 . 0 1 }$ $K { = } 0 . 5 0 \rangle$ 时，Crank-Nicolson方案的定价曲面

图15绘制了 $t = 1 . 0 0$ 时Crank-Nicolson方案的期权价格曲线。从图15可以看到，迭代次数等于250、500和1000的期权价格数值结果完全一致，这意味着时间步长的选择不会影响期权价格预测数值结果的精度，但会影响数值结果的解析度。

图16绘制了当 $s = 0 . 1 7$ 时，Crank-Nicolson方案的期权价格曲线。从图16可以看到，迭代次数等于250、500和1000的期权价格数值结果完全一致，这意味着价格曲线对时间步长并不敏感。从图16还可以看到，随着时间的推进，期权价格趋近于零，这与先前的假设相吻合。

![](images/e5fb71339cb2e92c6ec2b1b3ab5025e30598f90fdc4360f0390d40c288c632d2.jpg)  
图15时间步长 $= 2 5 0$ ，网格步长 $: = 1 0 0$ （20 $( t - 1 . 0 0 , T - 1 . 0 0 , S _ { t } = 1 . 0 0 , \delta = 0 . 3 0 ,$ （20$_ { r = 0 . 0 1 }$ $K { = } 0 . 5 0 \$ 时，Crank-Nicolson方案的定价曲线

![](images/922a6f46def045930da67258e90c06d91065bc4badb80c6714eb820fe2e4456b.jpg)  
图16时间步长 $: = 2 5 0$ 股票当前价格 $_ { - 0 . 1 7 }$ 网格步长 $: = 1 0 0$ 0 $_ { t = 1 . 0 0 }$ $T { = } 1 . 0 0$ ${ \cal S } _ { t } { = } 1 . 0 0$ 5 $\scriptstyle \delta = 0 . 3 0$ $_ { r = 0 . 0 1 }$ $K { = } 0 . 5 0 \$ 时，Crank-Nicolson方案的定价曲线

# 3 结束语

本文利用WindowsAzure的HPC调度程序，开发了基于云并行计算的期权定价方案，该方案以较低的费用提供了低风险和高速度，并给出了两种方案的期权定价仿真结果。

正如上述2.3节中讨论的那样，主服务器（发起者）利用TDMA方法求解线性系统方程（10)。为了进一步加快求解线性系统的计算速度，TDMA可以通过并行计算来实现，而现有的并行TDMA研究包括集群和GPU。文献[29]中，Swarztrauber等人开发了一个通用三对角矩阵的并行算法；文献[30]中，Nathan 等人开发了一个求解三对角矩阵的并行算法；文献[31]中，Lin 等人则开发了一个基于图的三对角矩阵算法。

期权定价的研究中，美式期权的定价问题，通常采用各种偏微分方程数值方法来求解。针对此类计算量大、计算时间长的问题，并行计算提供了有效的方法[32.33]。计算速度固然重要，但现有的美式期权定价研究主要将重心集中在数学模型的改进和提高运算速度上[34-37]，很少可以兼顾数据存储成本、计算成本和硬件开销问题。而云计算基于互联网,将规模化的计算能力、存储空间、开发平台和软件服务提供给用户,用户只需要支付一定的费用，便可以随时随地通过互联网使用云计算提供的资源

[38,39]。

金融领域云并行计算的一个关键问题是应该选择哪种部署模式：公有云还是私有云？对于没有兴趣建设和维护数据中心的金融公司来说，公有云是一个合适的选择，因为金融公司只需要向IaaS和PaaS提供商支付账单。通常来说，公有云的成本比私有云低，因为公共数据中心的规模往往比私有云大得多。此外，由于公共PaaS的开发人员往往来自领先的IT公司，因此公共PaaS在技术上也比私有云更先进。WindowsAzure此类云上的并行计算模式，为金融公司和专业人员提供了可扩展和低成本的并行计算，也为满足美式期权定价的速度需求提供了新的平台。而本文提供已成型的试点云软件AzureOP，将计算和存储都进行了交付，大大提高了计算效率，缩短了执行时间，相对于自己购买各种资源来说，以较低的成本完成了复杂的、大量的计算任务，简单高效，且使用方法简便快捷。私有云则为金融公司的敏感数据提供了更多的安全保障，未来将在这一领域开展更多的项目。

# 参考文献：

[1] Armbrust M,Fox A,Griffith R,et al.A view of cloud computing [J]. Communications of the ACM,2010,53 (4): 50-58.   
[2]Buyya R, Yeo C S,Venugopal S,et al. Cloud computing and emerging IT platforms:Vision, hype,and reality for delivering computing as the 5th utility [J].Future Generation Computer Systems,2009,25 (6): 599-616.   
[3]Marston S,Li Z, Bandyopadhyay S,et al. Cloud computing: the business perspective [J].Decision Support Systems,2011,51(1):176-189.   
[4]Dillon T,Wu C,Chang E.Cloud Computing: Issues and Challenges [C]/ Proc of the 24th IEEE International Conference on Advanced Information Networking and Applications. 2010: 27-33.   
[5]Doan D.Adeveloper's survey on different cloud platforms [D]. San Diego: University of California,2009.   
[6] Avetisyan A I, Campbell R,Gupta I, et al. Open Cirrus: A Global Cloud Computing Testbed [J]. Computer,2010,43 (4): 35-43.   
[7]Gunarathne T,Wu TL,Choi J Y,et al. Cloud computing paradigms for pleasingly parallel biomedical applications [J]. Concurrency & Computation Practice & Experience,2011,23(17): 2338-2354.   
[8] Gunarathne T, Zhang B,Wu TL,et al.Portable parallel programming on cloud and HPC: scientific applications of Twister4Azure [C]//Proc of the4th IEEE International Conference on Utility and Cloud Computing. Washington DC: IEEE Computer Society,2012: 97-104.   
[9]Wei L,Jackson J,Barga R.AzureBlast: a case study of developing science applications on the cloud [C]//Proc of the lst Workshop on Scientific Cloud Computing. 2010: 413-420.   
[10] Qiu X,Ekanayake J, Beason S,et al. Cloud technologies for bioinformatics applications [Cl//Proc of the 2nd Workshop on Many-Task Computing on Grids and Supercomputers.20o9:1-10.   
[11] Pratt B,Howbert JJ,Tasman NI,et al.MR-Tandem: parallel X!Tandem 2012,28 (1): 136-137.   
[12] Waltz E.10o0 genomes onAmazon'scloud[J]. Nature Biotechnology,2012, 30: 376-376.   
[13] ZhangL,Gu S,Liu Y,et al. Gene set analysis in the cloud[J].Bioinformatics, 2012,28 (2): 294-295.   
[14] Jourdren L,Bernard M,Dilles MA,et al. Eoulsan: a cloud computingbased framework facilitating high throughput sequencing analyses [J]. Bioinformatics,2012,28 (11): 1542-3.   
[15] Langmead B,Salzberg S L. Fast gapped-read alignment with Bowtie 2[J]. Nature Methods,2012,9(4):357-359.   
[16]HongD,RhieA,Park SS,etal.FX: anRNA-Seq analysis tool on the cloud [J]. Bioinformatics,2012,28 (5): 721.   
[17] HumphreyM,HillZ,IngenC V,et al.Assessing the valueofcloudbursting: a case study of satellite image processing on Windows Azure [C]// Proc of the 7th IEEE International Conference on E-Science.20l1:126-133   
[18] Subramanian V,Wang L,Lee EJ,et al. Rapid processing of synthetic seismogramsusing Windows Azure cloud [C]// Proc of the 2nd IEEE International Conference on Cloud Computing Technology& Science.2011: 193-200.   
[19]Rodrigues JJ.Analysis of cloud-based solutions on ehrs systems in different scenarios [J].Journal of Medical Systems,2012,36 (6): 3777.   
[20]Lawton G. Cloud streaming brings video to mobile devices [J].Computer, 2012,45 (2): 14-16.   
[21] Bohner M, Zheng Y.On analytical solutions of the Black-Scholes equation [J].Applied Mathematics Lettrs,2009,22(3):309-313.   
[22]HullJC.Options,futures and other derivatives [M].[S.1.]: Pearson,2009]   
[23] Gerbessiotis A V.Parallel option price valuations with the explicit finite difference method[J]. International Journal ofParallel Programming,2010, 38 (2): 159-182.   
[24] Bollerslev T, Gibson M, Zhou H. Dynamic estimation of volatility risk premia and investor risk aversion from option-implied and realized volatilities [J].Journal ofEconometrics,2011,160(1):235-245.   
[25] Liu Q. Pricing American options bycanonical least-squares Monte Carlo [J]. Journal ofFutures Markets,2008,30 (2): 175-187.   
[26]JasraA,DelMoralPSequentialMonteCarlomethodsforoptionpricing[] Stochastic Analysis& Applications,2011,29(2):292-316.   
[27] DevreeseJPA,LemmensD,Tempere J.Path integral approach toAsian options in the Black-Scholes model[J].PhysicaA: Statistical Mechanics & its Applications,2010,389 (4): 780-788.   
[28] Kohler M,Krzyzak A,Todorovic N.Pricingof high-dimensional american options by neural networks [J].Mathematical Finance,2010,20 (3): 383- 410.   
[29] Swarztrauber PN.A parallel algorithm for solving general tridiagonal equations [J].MathematicsofComputation,1979,33 (145):185-199.   
[30] Mattor N,Williams TJ,Hewett D W.Algorithm for solving tridiagonal

matrix problems in parallel[J].Parallel Computing,1995,21(11):1769- 1782.

[31] Lin H X.A unifying graph model for designing parallel algorithms for tridiagonal systems [J].Parallel Computing,2001,27(7): 925-939.

[32]张帆.两类期权定价模型有限差分的并行计算[D].保定：华北电力大学,2014.

[33]郭瑶瑶．两类期权定价模型有限差分并行计算的新方法研究[D].保定：华北电力大学,2016.

[34]蒋晓蓝．用GPU实现基于LSM算法的美式期权定价[J].科技创新导报,2013,18:34-35.

[35]刘颖，江一鸣．带不对称跳的期权定价扩散模型的参数估计[J]．南开大学学报,2017,50(6).  
[36]陈潇．拟蒙特卡罗方法在期权定价中的应用[D].长春：吉林大学,2017.  
[37]代斌．基于GPU的倒向随机微分方程的期权定价的并行算法研究 [D].济南：山东大学,2012.  
[38]刘源，张金燕．云计算技术在美式期权定价中的应用[J].电子技术与软件工程,2016,15:205-205.  
[39]王德原．基于期权和拍卖机制的云计算定价模型的研究[D].北京：北京邮电大学,2013.