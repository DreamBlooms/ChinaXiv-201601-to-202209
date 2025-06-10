中图分类号：作者填 文献标志码：A 文章编号：编辑部填

# 基于可解释网络的电力负荷预测

黄飞虎1,2，王金策11.四川大学计算机学院，四川 成都 610065；2.四川中电启明星信息技术有限公司，四川 成都 610000;摘要：负荷预测能有效助力负荷供需的动态平衡，保障电力系统稳定运行。基于统计模型和基于深度学习是目前构建预测方法的两种思路，但是少有从可解释的角度构建负荷预测方法。本文利用深度神经网络的非线性拟合能力，以及指数平滑模型的可解释特性，提出了深度平滑因子模型（DeepES）。从实际负荷序列数据中的预测结果来看，DeepES模型实现了最优的预测效果，而且相比于传统单一因子作为网络输入的RNNs网络具有更精确、可解释性更好的负荷预测模型。

关键词：负荷预测；深度神经网络；可解释网络；指数平滑模型;

# Power load forecasting based on interpretable networks

HUANG Fei-hul,2,Wang Jin-ce² (1. College of Computer Science, Sichuan University, Chengdu 61Oo65, Sichuan Province, China 2.Aostar Information Technologies Co.,Ltd., Chengdu 61Oooo, Sichuan Province, China）

Abstract:Load forecastingcanefectively balance the load at both ends ofsupplyand demand.Statistical model and deep learning are two common ways of constructing forecasting methods,but few load forecasting methods are constructed from the perspective of explanation. In this paper,a deep smoothing factor model, termed as DeepES,is proposed based on the nonlinear fiting ability of deep neural network and the explicable property of exponential smoothing model. According to the experimental results using actual load series data,the DeepES model achieves the best prediction. Moreover,compared with the traditional RNNs network with a single factor as the network nput, DeepES has a more accurate and better explanatory for load prediction.

Key words: Load forecasting; Deep neural network; Interpretable network; Exponential smoothing model;

# 0 引言

由于电能的特点是即发即用，因此提前对负荷进行预测可以有效地进行能源管理，实现负荷供需的动态平衡，保障电力系统的稳定运行[I]。双碳背景下，新能源入网的比例逐渐提供，电动汽车的数量日益增加，这些因素增加了电网负荷的波动性，也给准确预测用电负荷带来了挑战[2][4]。

从模型可解释的角度来看，现有的负荷预测方法可以分为两大类。一是基于统计模型的负荷预测方法，这类方法基于数学、统计理论构建，具有很好的可解释性。常见的有自回归移动平均(AutoRegressionMovingAverage,ARMA)、自回归(Auto Regression,AR)等时间序列模型[4],[5][6]。此外，也有基于卡尔曼滤波的预测方法[6][7]，基于指数平滑度预测方法[8]。另一类就是基于神经网络的预测方法，这是目前主流的预测方法[9][10]。其中以长短期记忆网络 LSTM（Long Short-TermMemory,LSTM)和门控循环单元(GateRecurrent

Unit,GRU）为主的循环神经网络（RecurrentNeuralNetwork,RNN）在负荷预测中有广泛应用[1][12][13]。比如，文献[14]基于长短期记忆网络提出了一种针对区域级负荷的深度超短期预测方法。也有很多学者将循环神经网络与其他方法相结合实现负荷预测。此外，Transformer模型仅两年在预测任务中得到了很广泛的应用[15]。比如，文献[16]基于Transformer设计了一种适应于长期时间序列预测(LSTF）的高效的结构，可以实现负荷数据的长时预测。

总的来说，基于统计模型的预测方法，其特点是可解释性强，但是效果没有基于神经网络的好。相反，由于神经网络本身是一个黑盒，在网络中，很难厘清模型对负荷序列特征的提取过程[17][18]。但是，神经网络模型具有很强的非线性映射能力，能够实现效果不错的负荷预测。模型可解释性是神经网络的主要缺点，构建具有可解释性的且预测效果好的模型受到了学者们的关注。在负荷预测中，构建具有可解释性的预测模型，能够让用户理解模型的推理过程，有助于增加对模型的可信度。

因此，本文综合神经网络模型和统计模型的优点，以指数平滑模型为基础创新地设计了具有可解释性的循环神经网络DeepES（Deep Exponential Smoothing）。指数平滑模型[19]，能够通过特定参数明确地描述输入序列的周期性、趋势性和平滑性。描述负荷序列的特征，但是如何以此为基础构建循环神经网络需要解决一下问题：(1)指数平滑模型中的因子(即平滑因子、趋势因子和季节因子）是迭代计算的，因此如何设计神经网络实现这些因子的迭代计算是必须解决的问题；（2)这些因子之间也有相关性，在神经网络中如何表达因子之间的关系；（3）在首次迭代计算时，如何初始化这些因子。针对问题1，本文涉及了一种循环神经网络，解决迭代计算问题。针对问题2，在每个子单元中，通过多层感知机网络实现因子之间的关系表达。同时，也设计了初始化网络实现因子的初始化。在实验中，通过对真实负荷数据的预测，验证了本文模型预测效果，而且比原始的指数平滑模型效果更好。

# 1指数平滑

指数平滑(Exponential Smoothing，简称 ES)起源于RobertG.Brown在二战期间为美国海军写的工作报告文章[19]。CharlesC.Holt 独立于RobertG.Brown,开发了一种类似的方法来平滑加性趋势的指数，以及一种完全不同的方法来平滑季节数据。Winters 在1960年用经验数据测试了Holt的方法，这些方法被称为Holt-Winters预测系统。现有的指数平滑方法均是对这三位学者提出方法的扩展。表1给出了常用的几种三次指数平滑。预测原理是平滑因子、趋势因子、季节因子三种因子的线性组合。

表1常用指数平滑方法  
Tab.1 Common exponential smoothing methods   

<html><body><table><tr><td>趋势,季节</td><td>公式</td><td></td></tr><tr><td>A,A</td><td>(Ii=α(xi-Si-k)+(1-α)(Ii-1+Ti-1) Ti=β(Ii-Ii-1)+(1-β)Ti-1 Si=γ(xi-1i)+(1-γ)Si-k （ Xi+h=Ii+hTi+Si-k+h</td><td>(1)</td></tr><tr><td>A,M</td><td>(Ii=α(xi/Si-k)+(1-α)(Ii-1+Ti-1) Ti=β(Ii-Li-1)+(1-β)Ti-1 Si=γ(xi/Ii)+(1-γ)Si-k Xi+h=(I+hTi)Si-+h</td><td>(2)</td></tr><tr><td>M,A</td><td>(Ii=α(xi-Si-k)+(1-α)Ii-1Ti-1 Ti=β(I/Ii-1)+(1-β)Ti-1 Si=γ(xi-I;)+(1-γ)Si-k Xi+h=ITh+Si-k+h</td><td>(3)</td></tr><tr><td>M,M</td><td>(Ii=α(xi/Si-k)+(1-α)Ii-Ti-1 Ti=β(Ii/Ii-1)+(1-β)Ti-1 Si=γ(xi/Ii)+(1-γ)Si-k Xi+h=ITʰSi-k+h</td><td>(4)</td></tr><tr><td></td><td>A表示加法;M表示乘法;I表示平滑因子; T表示趋势因子；S表示季节因子</td><td></td></tr></table></body></html>

# 2 DeepES 模型

三次指数平滑通过平滑因子、趋势因子、季节因子的组合实现预测。如表1所示，这些公式中三种因子的组合均是通过不同的运算方式实现。本文认为，这些指数平滑模型具有很强的可解释性，可以通过三种因子对数据的特征有直观认识。然而，每个因子的计算公式均有权重系数（比如， $\alpha , \beta , \gamma )$ 。在使用时，每种公式均需人工设置权重实现预测效率，所以灵活性差、泛化能力不强。此外，因子之间的运算关系，通过加法或乘法难以表达其复杂的非线性关系。因此，本文通过引入神经网络实现因子之间复杂非线性关系的表达，提出了一种新的神经网络计算模型，称为DeepES模型。模型的总体框架如图1所示。模型由初始化模块，DeepES单元和预测模块这三部分组成。下面对每个模块作详细介绍。

![](images/471755f549372e9246fdf726a1986e1974727cf19b46a66eaa1a1677410894e8.jpg)  
图1模型的总体框架

![](images/d5de4989333e571f99fb59b3ff90aba3250673295287675fe9316ec4e6b955fe.jpg)  
Fig.1Framework of model

# 2.1初始化模块

对于因子初始化方法，本文的设计思路为：记输入序列为 $\{ X _ { 1 } , X _ { 2 } , . . . , X _ { \mathrm { n } } \}$ ，其长度为 $n$ 。取输入序列的前$k$ 个值，记为 $\{ X _ { 1 } , X _ { 2 } , . . . , X _ { \mathrm { k } } \}$ ，计算该序列的均值、方差和水平比率，三个指标的计算公式如下：

$$
\begin{array} { r } { \mathrm { { X } _ { m e a n } = \frac { 1 } { k } \sum _ { i = 1 } ^ { k } \mathrm { { X } _ { i } } } } \end{array}
$$

$$
\scriptstyle \mathrm { X _ { v a r } = \frac { 1 } { k } \sum _ { i = 1 } ^ { k } \left( X _ { i } – X _ { m e a n } \right) ^ { 2 } }
$$

$$
\mathrm { { X } _ { b } \mathrm { { = } \frac { n \cdot X _ { m e a n } } { \sum _ { i = 1 } ^ { n } X _ { i } } } }
$$

得到 $\Chi _ { m e a n }$ ， $\mathrm { X } _ { v a r }$ ， $\mathrm { X } _ { b }$ 三个指标之后，通过初始化网络InitNet 得到初始化因子的取值 ${ { X } _ { i n i t } }$ 。InitNet 网络的设计如图2所示。得到 ${ { X } _ { i n i t } }$ 之后，则初始化三个因子：

$$
\begin{array} { c } { { \mathrm S _ { \mathrm { 0 } } { = } \mathrm { \left[ X _ { \mathrm { i n i t } } ^ { 1 } , . . . , X _ { \mathrm { i n i t } } ^ { p } \right] } } } \\ { { \mathrm T _ { \mathrm { 0 } } { = } \mathrm { X _ { \mathrm { i n i t } } ^ { p + 1 } } } } \\ { { \mathrm I _ { \mathrm { 0 } } { = } \mathrm { X _ { \mathrm { i n i t } } ^ { p + 2 } } } } \end{array}
$$

其中， $\mathrm { \Delta S _ { 0 } }$ 取 $X _ { i n i t }$ 的前 $\mathsf { p }$ 个值进行初始化， $T _ { 0 }$ 取 ${ X } _ { i n i t }$ 的第 $\mathsf { p } { + } \mathsf { 1 }$ 个值进行初始化， $I _ { 0 }$ 取 ${ { X } _ { i n i t } }$ 的第 $\mathsf { p } { + } 2$ 个值初始化。

# 2.2DeepES单元

每个迭代步骤的执行单元是DeepES单元（如图3所示），下面详细介绍DeepES单元中的执行流程，记当前执行步为t：

$\textcircled{1}$ 计算 $\mathbf { t } { + } 1$ 时刻的平滑因子 $I _ { \mathrm { t + 1 } }$ ，公式如下：

$$
\mathrm { I _ { p l } ^ { t } { = } T e m p N e t ( c o n c a t ( X _ { t } , S _ { t } ) ) }
$$

$$
{ \mathrm { I } } _ { { \mathrm { p } } 2 } ^ { \mathrm { t } } { = } \mathrm { T e m p N e t } ( \mathrm { c o n c a t } ( { \mathrm { I } } _ { \mathrm { t } } , { \mathrm { T } } _ { \mathrm { t } } ) )
$$

$$
\mathrm { I } _ { { \mathrm { t } } + 1 } { = } \mathrm { I } _ { \mathrm { p } 1 } ^ { \mathrm { t } } { + } \mathrm { I } _ { \mathrm { p } 2 } ^ { \mathrm { t } }
$$

其中，concat(·)表示两个向量的拼接操作，TempNet为其中的计算网络，网络设计如图4所示。

![](images/e650948cc73063856a723c6443df10740efa87e2dbbac99f0fd7d22781ddc338.jpg)  
图2InitNet网络结构  
图3DeepES单元网络结构

![](images/e74bcb0a0ba99f8fd04a526c123b652acfb72a646449309f675f1188633e42cb.jpg)  
Fig.2 Structure of InitNet   
Fig.3 Structure ofDeepES cell   
图4TempNet网络结构  
Fig.4 Structure of TempNet

$\textcircled{2}$ 计算 $_ { \mathrm { t + l } }$ 时刻的趋势因子 $T _ { \mathrm { t + 1 } }$ ，公式如下：

$$
\mathrm { T _ { p l } ^ { t } { = } T e m p N e t ( c o n c a t ( I _ { t } , I _ { t + 1 } ) ) }
$$

$$
\mathrm { T _ { t + 1 } { = } T _ { p 1 } ^ { t } + T _ { t } }
$$

其中，concat(·)表示两个向量的拼接操作，TempNet为其中的计算网络，网络设计与平滑因子 $I _ { \mathrm { t + 1 } }$ 中的计算

网络一致;

$\textcircled{3}$ 计算 $^ { \mathrm { t } + 1 }$ 时刻的趋势因子 $S _ { \mathrm { t + 1 } }$ ，公式如下：

$$
\mathrm S _ { \mathrm { p } 1 } ^ { \mathrm { t } } \mathrm { = T e m p N e t ( c o n c a t ( X _ { t } , I _ { t + 1 } ) ) }
$$

$$
\mathrm { S } _ { \mathrm { t } + 1 } { = } \mathrm { S } _ { \mathrm { p } 1 } ^ { \mathrm { t } } { + } \mathrm { S } _ { \mathrm { t } }
$$

其中，concat(·)表示两个向量的拼接操作，TempNet为其中的计算网络，网络设计与平滑因子 $\boldsymbol { I } _ { \mathrm { t + 1 } }$ 中的计算网络一致;

# 2.3 预测模块

基于最后一个DeepES单元输出的三个因子，即$S _ { \mathrm { l a s t } }$ 、 $T _ { \mathrm { l a s t } }$ 、 $I _ { \mathrm { l a s t } }$ ，计算预测值Y，计算公式为：

$$
\mathrm { Y { = } P r e N e t ( c o n c a t ( S _ { t + 1 } , T _ { t + 1 } , I _ { t + 1 } ) ) }
$$

其中，concat()表示两个向量的拼接操作，PreNet为其中的预测网络，如图5所示.

# 3实验

![](images/482b3a53f5b6b3f4b4ccac26ef6b02bb57ece1edcece3ce03a0bae49fead6ea0.jpg)  
实验数据：文章利用美国能源信息署的公开数据

Tab.3 Trend comparison   

<html><body><table><tr><td colspan="2">True</td><td colspan="2">ES</td><td colspan="2">DeepES</td></tr><tr><td>1-15</td><td>下降</td><td>1-8</td><td>下降</td><td>1-5</td><td>下降</td></tr><tr><td>15-31</td><td>上升</td><td>8-23</td><td>上升</td><td>5-21</td><td>上升</td></tr><tr><td>31-40</td><td>下降</td><td>23-37</td><td>下降</td><td>21-39</td><td>下降</td></tr><tr><td>40-45</td><td>上升</td><td>37-42</td><td>上升</td><td>39-44</td><td>上升</td></tr><tr><td>45-50</td><td>下降</td><td>42-45</td><td>下降</td><td>44-47</td><td>下降</td></tr><tr><td>50-61</td><td>上升</td><td>45-57</td><td>上升</td><td>47-51</td><td>上升</td></tr><tr><td></td><td></td><td>57-61</td><td>下降</td><td>51-61</td><td>下降</td></tr></table></body></html>

(4）GBRT，即渐进梯度回归树（GradientBoostRegressionTree），可处理不同类型的数据，具有很强的预测能力。该方法也是时序数据预测经常采用的对比方法。实验中，利用sklearn提供的对模型实证分析。为了验证DeepES的有效性，从预测精度、可解释性和深度非线性拟合预测有效性等三个方面对DeepES进行了分析论证。

对比算法:为验证DeepES的预测性能，本文选取的对比模型如下：

（1）ARIMA，该方法是经典的时间序列方法，在负荷预测任务中也常作为对比算法。实验中，采用模型参数为(0,0,1)。  
(2) LSTM，即长短期记忆网络，是循环神经网络的经典网络，能够挖掘序列数据的非线性时间依赖关系。实验中，采用2层LSTM，输出维度为64。  
(3）BP，即反向传播(BackPropagation)神经网络，是经典的神经网络，在时序预测和负荷预测任务中有广泛应用。实验中，隐藏层维度为32，输出维度64。

![](images/3bf931dc6e59a8f1e92c891e8bdd870ea4a901293df02560d24912ce395565a7.jpg)  
Fig.5Structure of PreNet.表3趋势对比表  
图6原始均值序列

![](images/b2e070b56f738c2015492d2c0b0f1709f5b0afaece1b5d50b010916b79343d47.jpg)  
图5PreNet网络结构图  
Fig.6 Original mean sequence.   
图7DeepES预测序列  
Fig.7Forecast sequence of DeepES

函数实现，主要参数为估计器数量500，最大深度3。

(5）Transformer，该模型最近很多学者将其运用到了序列数据预测、目标检测等领域，均取得了不错的效果。实验中，利用pytorch 提供的transformer函数实现，主要参数为编码层和解码层的输入维度为64，隐藏层维度64，层数为1。

(6）OneES，简单指数平滑，近期序列对当前数据影响较大，各期数据的权重根据时间间隔增大指数衰减[19]。

(7）TwoES，Holt两参数指数平滑，对含有线性趋势 的序列设置固定的线性趋势，进行修正预测[19]。

为说明深度非线性因子的有效性，实验进行非线性因子的合理性分析。为更具有说服性，实验选取长度为60的归一化负荷序列，如图6。分别利用ES和DeepES计算平滑因子、季节因子、趋势因子，图7为 DeepES 预测序列。

在图8中，给出了本文DeepES 模型与指数平滑模型（ES）之间的因子对比。可以看出，趋势因子与DeepES趋势因子整体趋势一致，趋势对比如表2，不同的是，DeepES 利用非线性拟合趋势特征，更具有超(8）ThreeES，简单指数平滑、线性指数平滑与季节指数三者结合的三次指数平滑方法，针对有季节性表现的时间序列预测[19]。

对比指标：本文采用RMSE与MAPE评估模型的预测性能，计算方法如下：

$$
\left\{ \begin{array} { l l } { \mathrm { M A P E { = } \frac { 1 0 0 \% } { n } \sum _ { i = 1 } ^ { n } \left| X _ { i } - \widehat { X _ { i } } \right| } } \\ { \mathrm { R M S E { = } \sqrt { \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \left( x _ { i } - \widehat { X _ { i } } \right) ^ { 2 } } } } \end{array} \right.
$$

前性、预测性，例如原始负荷1-15下降，15-31上升，ES 表现1-8下降，8-23上升，DeepES表现为1-5下降，5-21上升。趋势预测对未来数值拟合有重要作用，因此预测效果较好。

# 3.1负荷预测精度对比

为验证DeepES对负荷预测的先进性，选取现阶段性能较优的序列预测算法作为对比算法，如表2所示。从对比结果来看，本文模型的预测效果最优。

![](images/7fae795f380f933e053608dc5584d2f5e79521fd541391b5fdb9d90c0a1233fb.jpg)  
图8因子对比  
Fig.8 Comparison of factors

# 3.2非线性因子分析

ES 平滑因子与真实序列趋势和数据点值域，而DeepES平滑因子与ES存在较大差异，由于DeepES利用线性变化和非线性激活函数捕捉序列前后数据之间的非线性关系。ES季节因子有明显周期性，且周期固定，DeepES季节因子周期与幅值不断变化，对不同序列的季节因子拟合能力更强。

因为DeepES利用神经网络的非线性拟合能力分别拟合平滑、季节、趋势三种因子，进一步利用多层网络对三个因子非线性组合参数自适应学习，进而实现负荷序列预测，因子预测效果优于ES。如图9所示，两种模型的每一步预测绝对误差对比。

# 3.3 可解释性验证

利用DeepES中利用多层感知机对各种因子进行非线性组合，自适应学习组合参数。相对于RNNs与MLP等网络，DeepES更具可解释性，实验分别将各种因子及组合利用DeepES网络进行负荷预测，结果如图-10所示。I代表季节因子，S代表平滑因子，T代表趋势因子，TS代表趋势因子与平滑因子组合，IS代表季节因子与平滑因子组合、IT代表季节因子与趋势因子在组合、ITS代表三种因子组合，结果显示利用ITS预测效果最好，说明了深度指数平滑网络模型DeepES预测效果优越的可解释性。图11中表示60步预测的RMSE与MAPE，ITS预测性能最优，同时各个因子输入DeepES预测效果均比传统ES更有，显示出了利用理论因子与神经网络结合兼具效果与可解释性。

# 4结论

文章利用神经网络的非线性拟合能力，并与基于分解的指数平滑预测方法结合，提出了深度平滑因子模型DeepES，在实际负荷序列数据中验证了优越的预测性能，说明了DeepES依据经典指数平滑时间序列预测理论构建的神经网络是相比于传统RNNs网络单一因子作为网络输入的更精确、理论更完备的、可解释的负荷预测模型。

![](images/a33b6c84d845aceea3c230006615f42cde8106794c1fca263772ab14afdd2a24.jpg)

![](images/89a8a035cf6066f2e146981f918f471efb074334bc3d85a6880f7c7dc777993e.jpg)  
图9DeepES与ES预测绝对误差对比Fig.9 Comparison of absolute error  
图10因子预测效果对比

![](images/bba9332831ae3e7653aefec1fc89feaa8355b705dbe90753d53790dc64947ed4.jpg)  
Fig.10 Comparison results using three factors   
图11三种因子预测绝对误差对比  
Fig.11 Comparison of absolute error three factors

# 参考文献

[1]王栋.电力系统负荷预测综述[J].电气开关,2020,58(01):6-8+20.  
[2]廖启术,胡维昊,曹迪,黄琦,陈哲.新能源电力系统中的分布式光伏净负荷预测[J].上海交通大学学报,2021,55(12):1520-1531.  
[3]杨智宇,刘俊勇,刘友波,等．基于自适应深度信念网络的变电站负荷预测[J].中国电机工程学报,2019,39(14):4049-4061.  
[4] ChenJF,Wang Weimi,Huang Chaoming.Analysisof an adaptive time-series autoregressive moving-average(ARMA） model forshort-term loadforecasting[J].Electric Power Systems Research,1995，34(3): 187-196.  
[5]Hagan MT，Behr SM.The time series approach toshort term load forecasting[J]. IEEE Transactions onPower Systems，1987，2(3): 785-791  
[6] 陈培垠，方彦军．基于卡尔曼滤波预测节假日逐点增长率的电力系统短期负荷预测[J]．武汉大学学报,2020,53(2): 139-144.  
[7]赵峰，孙波，张承慧．基于多变量相空间重构和卡尔曼滤波的冷热电联供系统负荷预测方法[J].中国电机工程学报，2016,36(2):399-406.  
[8]Rendon-Sanchez JF, De Menezes L M. Structuralcombination of seasonal exponential smoothingforecasts applied to load forecasting [J]. EuropeanJournal of Operational Research,2019,275(3): 916-924.  
[9] 朱俊丞,杨之乐,郭媛君,等．深度学习在电力负荷预测中的应用综述[J].郑州大学学报(工学版),2019,40(05):13-22.  
[10]史凯钰,张东霞,韩肖清,解治军.基于LSTM与迁移学习的光伏发电功率预测数字孪生模型[J].电网技术,2022,46(04):1363-1372.  
[11] 梁志峰,董存,吴骥,崔方,陈卫东.组合辐射衰减因子预报与 RBF 神经网络的光伏短期功率预测方法[J].电网技术,2020,44(11):4114-4120.  
[12]陈志宝,丁杰,周海,程序,朱想.地基云图结合径向基函数人工神经网络的光伏功率超短期预测模型[J].中国电机工程学报,2015,35(03):561-567.  
[13] Frank R J,Davey N,Hunt S P. Time SeriesPrediction and Neural Networks[J]. Journal ofIntelligent and Robotic Systems,2001,31(1):91-103.  
[14] 张宇帆，艾芊，林琳，等．基于深度长短时记忆网络的区域级超短期负荷预测方法[J]．电网技术,2019,43(6): 1884-1892.  
[15] Feihu Huang,Peiyu Yi, Jince Wang,Mengshi Li,Jian Peng, Xi Xiong, A dynamical spatial-temporalgraph neural network for traffic demand prediction[J],Information Sciences,2022,594,286-304.  
[16] Zhou H, Zhang S, Peng J,et al. Informer: Beyondefficient transformer for long sequence time-seriesforecasting[C]. AAAI Conference on ArtificialIntelligence, 2021: 11106-11115.  
[17]衣玉林.基于深度网络的时间序列预测及其可解释性研究[D].北京邮电大学,2021.  
[18] Salinas D,Flunkert V,Gasthaus J,et al. DeepAR:Probabilisticforecastingwithautoregressive

recurrent networks[J]. International Journalof Forecasting,2020,36(3):1181-1191. [19] Gardner E S.Exponential smoothing:The state of theart—Part II[J]. International Journalof Forecasting,2006,22(4):637-666.