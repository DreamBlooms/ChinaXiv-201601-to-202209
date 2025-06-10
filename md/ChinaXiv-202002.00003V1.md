# 基于极限学习机的极移中长期预报

赵丹宁，雷雨

(1.宝鸡文理学院 电子电气工程学院，陕西 宝鸡 7210162.西安邮电大学 计算机学院，陕西 西安 710121)

摘要：传统的极移预报多是基于最小二乘外推和自回归等线性模型，但极移包含了复杂的非线性成分，线性模型的预报效果往往不甚理想。将一种新型神经网络一极限学习机（extremelearning machine，ELM）用于极移中长期预报。首先利用最小二乘外推模型对极移序列进行拟合，获得趋势项外推值，然后采用ELM对最小二乘拟合残差进行预报，最终的极移预报值为趋势项外推值与残差预报值之和。将ELM的预报结果同反向传播（back propagation，BP）神经网络与地球定向参数预报比较活动（Earth Orientation Parameters Prediction ComparisonCampaign，EOPPCC）的预报结果进行对比，结果表明：ELM用于极移中长期预报是高效可行的。

关键词：极移；预报；极限学习机；神经网络；预报模型中图分类号：P227 文献标识码：A 文章编号：

# 0引言

地球极移表示地球瞬时自转轴相对于地球表面或者历元平极的运行，是表征地球自转变化的一个重要参量，简称极移动。极移的两个分量 $x _ { \mathfrak { p } } \cdot \ y _ { \mathfrak { p } }$ 、UT1-UTC与岁差、章动统称为地球定向参数（Earth orientation parameters，EOP），EOP是天球参考系和地球参考系相互转换的必需参数。甚长基线干涉（VeryLong Baseline Interferometry，VLBI）和全球导航卫星系统（GlobalNavigation Satelite Systems，GNSS）等空间大地测量技术的极移测定精度可达0.05mas[]。但由于复杂的资料处理过程，由空间大地测量技术获取的极移结果存在一定的延迟，而深空探测和卫星精密定轨等领域对极移的实时测量值具有重要需求，所以对极移进行短期预报就显得尤为必要，此外，极移中长期预报值在卫星自主导航和天文地球动力学研究中亦有重要应用，故极移的中长期预报也具有重要的科学及现实意义。

国内外学者提出了多种极移预报方法，如最小二乘外推[2、自协方差模型[3]、模糊推理系统[4]、神经网络[5]、自回归模型[5-6]以及这些模型的不同组合。受大气和海洋等多种激发源的影响，极移呈现复杂的非线性、非平稳变化，因此采用神经网络等非线性方法对其进行预报在理论上更为合适，许多学者将神经网络应用于极移预报，取得了较好的预报效果[7-8]。国际EOP比较活动（EOP Prediction Comparison Campaign，EOP PCC）的结果也表明，神经网络是当前极移预报精度最高的方法之—[9]。

反向传播（back propagation，BP）神经网络是当前应用最为广泛的一种网络学习算法，在时间序列预测、图像处理和自动控制等领域均有应用，但BP神经网络存在易陷入局部极小值、学习速度慢和泛化能力弱等缺点。极限学习机（extreme learming machine，ELM）是近年发展起来的一种新型单隐含层前馈神经网络，其特点是隐含层神经元的权重可以随机给定，且不需要更新，网络学习过程仅计算输出权重，故在学习速度与泛化能力方面较传统BP神经网络具有一定优势[10-11]。正是基于此，本文将ELM神经网络应用于极移中长期预报，根据极移时间序列特征，建立了基于ELM神经网络的极移预报模型，试验结果验证了ELM神经网络应用于极移预报的有效性和实用性。

# 1极限学习机原理

给定 $N$ 个训练样本 $( \pmb { x } _ { i } , \pmb { y } _ { i } )$ ，其中输入向量 $\pmb { x } _ { i } = [ x _ { i 1 } , x _ { i 2 } , \cdots , x _ { i u } ] ^ { \operatorname { T } } \in \mathbb { R } ^ { u }$ ，输出向量$\pmb { y } _ { i } = [ y _ { i 1 } , y _ { i 2 } , \cdots , y _ { i \nu } ] ^ { \mathrm { T } } \in \mathbb { R } ^ { \nu }$ ， $u \cdot \nu$ 分别为输入向量维数与输出向量维数，则具有 $h$ 个隐含层

节点的单隐含层前馈神经网络能够以零误差来逼近这 $N$ 个样本，即有下式成立[10].

$$
\begin{array} { r } { \mathbf { y } _ { i } = \sum _ { j = 1 } ^ { h } \pmb { \beta } _ { j } g ( \pmb { w } _ { j } \cdot \pmb { x } _ { i } + b _ { j } ) , i = 1 , 2 , \cdots , N } \end{array}
$$

式中， $\pmb { w } _ { j } = [ w _ { j 1 } , w _ { j 2 } , \cdots , w _ { j u } ] ^ { \operatorname { T } }$ 为第 $j$ 个隐含层神经元与输入层神经元间的连接权重，$\boldsymbol { \beta } _ { j } = [ \beta _ { _ { j 1 } } , \beta _ { _ { j 2 } } , \iota \ , \beta _ { _ { j \nu } } ] ^ { \mathrm { { T } } }$ 为第 $j$ 个隐含层神经元与输出层神经元间的连接权重， $b _ { j }$ 为第 $j$ 个隐含层神经元的偏置， $g ( \pmb { x } )$ 为激活函数。式（1）可以表示为矩阵相乘的形式：

$$
Y = H \beta
$$

其中， $\pmb { H }$ 为隐含层输出矩阵：

$$
\begin{array} { r } { \pmb { H } = \left[ \begin{array} { c c c } { g ( \pmb { w } _ { 1 } \cdot \pmb { x } _ { 1 } + b _ { 1 } ) } & { \cdots } & { g ( \pmb { w } _ { h } \cdot \pmb { x } _ { 1 } + b _ { h } ) } \\ { \vdots } & { \cdots } & { \vdots } \\ { g ( \pmb { w } _ { 1 } \cdot \pmb { x } _ { N } + b _ { 1 } ) } & { \cdots } & { g ( \pmb { w } _ { h } \cdot \pmb { x } _ { N } + b _ { h } ) } \end{array} \right] _ { N \times h } } \end{array}
$$

$\beta$ 和 $Y$ 为

$$
\boldsymbol { \beta } = \left[ \begin{array} { l } { \boldsymbol { \beta } _ { 1 } ^ { \mathrm { ~ T ~ } } } \\ { \boldsymbol { \beta } _ { 2 } ^ { \mathrm { ~ T ~ } } } \\ { \vdots } \\ { \boldsymbol { \beta } _ { N } ^ { \mathrm { ~ T ~ } } } \end{array} \right] _ { N \times \nu } , ~ \boldsymbol { Y } = \left[ \begin{array} { l } { \boldsymbol { y } _ { 1 } ^ { \mathrm { ~ T ~ } } } \\ { \boldsymbol { y } _ { 2 } ^ { \mathrm { ~ T ~ } } } \\ { \vdots } \\ { \boldsymbol { y } _ { N } ^ { \mathrm { ~ T ~ } } } \end{array} \right] _ { N \times \nu }
$$

ELM神经网络的训练步骤如下[10]：1）随机选取输入层权重 ${ \pmb w } _ { j }$ 、偏置 $b _ { j }$ ， $j = 1 , 2 , \cdots , h ; 2 )$ （204号计算隐含层输出矩阵 $\pmb { H }$ ；3）计算输出层权值 $\pmb { \beta } = \pmb { H } ^ { \dagger } \pmb { Y }$ ，其中 $\pmb { H } ^ { \dagger }$ 为矩阵 $\pmb { H }$ 的Moore-Penrose广义逆。

# 2预报方法

# 2.1最小二乘外推

最小二乘外推模型包含3部分：线性趋势项、钱德勒项和周年项，其数学模型为

$$
f { = } a { + } { \gamma } t { + } \sum _ { i = 1 } ^ { 2 } [ c _ { i } \cos ( 2 \pi t / T _ { i } ) { + } d _ { i } \sin ( 2 \pi t / T _ { i } ) ]
$$

式中， $T _ { 1 }$ 、 $T _ { 2 }$ 分别为钱德勒项和周年项的振荡周期，取 $T _ { \mathrm { 1 } } { = } 4 3 2 . 0 8 \mathrm { d }$ 、 $T _ { 2 } = 3 6 5 . 2 4 \mathrm { d } , a \ 、 \gamma$ 为趋势项参数， $c _ { 1 }$ 、 $d _ { \mathrm { { \scriptscriptstyle 1 } } }$ 为钱德勒项参数， $c _ { 2 }$ 、 $d _ { 2 }$ 代表周年项参数，这些未知参数可以根据最小二乘法求解。

# 2.2神经网络模型构建

最小二乘拟合残差含有剩余的短周期成分，也含有各种准周期和非线性成分，对于这些成分，利用神经网络的非线性拟合能力对其进行建模与预报。依据神经网络模型构建与极移预报的实际情况，采用如下方式确定网络的输入和输出：

$$
[ \pmb \varepsilon ( t - k - u + 1 ) , \pmb \varepsilon ( t - k - u + 2 ) , \cdots , \pmb \varepsilon ( t - k ) ]  \pmb \varepsilon ( t )
$$

其中， $\pmb \varepsilon ( t )$ 为最小二乘拟合残差， $t = 1 , 2 , \cdots , n$ ， $k$ 为预报跨度。为了提高数据利用率，采用滑动窗口方式构建训练样本：

$$
\begin{array} { r } { \left\{ \begin{array} { l } { [ \varepsilon ( 1 ) , \varepsilon ( 2 ) , \cdots , \varepsilon ( u ) ] \to \varepsilon ( u + k ) } \\ { [ \varepsilon ( 2 ) , \varepsilon ( 3 ) , \cdots , \varepsilon ( u + 1 ) ] \to \varepsilon ( u + k + 1 ) } \\ { \qquad \vdots } \\ { [ \varepsilon ( n - k - u + 1 ) , \varepsilon ( n - k - u + 2 ) , \cdots , \varepsilon ( n - k ) ] \to \varepsilon ( n ) } \end{array} \right. } \end{array}
$$

相应地，在预报阶段网络的输入和输出为

$$
[ \pmb \varepsilon ( n - u + 1 ) , \pmb \varepsilon ( n - u + 2 ) , \cdots , \pmb \varepsilon ( n ) ]  \hat { \pmb \varepsilon } ( n + k )
$$

其中， $\hat { \pmb { \varepsilon } } ( \boldsymbol { n } + \boldsymbol { k } )$ 为神经网络模型的第 $k$ 步预报值。

由于本文利用ELM神经网络实现从输入到输出的非线性映射，故需要事先确定激活函数类型和网络拓扑结构（输入层神经元数和隐含层神经元数），其中，激活函数选用Sigmoid函数，其表达式为

$$
g ( x ) = 1 / \left( 1 + e ^ { - x } \right)
$$

由于网络拓扑结构对网络性能起着至关重要的影响，为了确定较优的网络拓扑结构，本文通过观察网络训练误差随输入层神经元数和隐含层神经元数的变化情况来优化网络拓扑结构，即网络训练误差最小时所对应的输入层神经元数和隐含层神经元数为最优输入层和隐含层神经元数。以预报跨度30d为例，图1给出了网络训练均方根误差（root mean square error，RMSE）随输入层和隐含层神经元数的变化情况，从图1可以看到，当输入层神经元数为17、隐含层神经元数为47时，网络训练均方根误差最小。

![](images/e0aeae78914c7da46b33c1b7c29c4a5c88ba012cec62376c3c95f9fdf6ddca2f.jpg)  
图1网络训练均方根误差（RMSE）随输入层与输出层神经元数的变化情况 Fig.1 Changes of the network training RMSE with the neutron number of input and hidden la 3方法验证

为了评估ELM神经网络用于极移长期预报的性能，首先将本文的预报结果同Liao等的BP神经网络预报结果进行比较和分析，为了较为客观地对二者的结果进行对比，本文预报过程中采用与Liao等相同的预报策略和误差评价指标，其中，试验数据采用IERS发布的EOP05C04序列，基础数据长度为3yr，预报时段为2001年4月6日（MJD 52005）至2010年3月25日（MJD 55280），每隔91d预报一次，一共进行了37期的预报，预报误差评价指标选用平均绝对误差（meanabsoluteerror，MAE），其计算公式为

$$
\mathrm { M A E } _ { \boldsymbol { k } } = \frac { 1 } { l } \sum _ { j = 1 } ^ { l } \Bigl | P _ { j } ^ { \boldsymbol { k } } - O _ { j } ^ { \boldsymbol { k } } \Bigr |
$$

式中， $O _ { j }$ 、 $P _ { j }$ 分别表示 $j$ 点的观测值与预测值，1为预报期数。

图2给出了本文极移预报结果的误差曲线和Liao等预报结果的误差曲线，表1统计了二者1d、5d、10d、20d、30d、60d、90d、120d、180d、240d、300d和360d预报跨度的平均绝对误差。从图2和表1可以看出，对于 $x _ { _ { \vert } }$ 分量中长期预报，除了120d、180d和240d的ELM神经网络方法的预报精度稍逊于Liao等的BP神经网络方法，其余跨度的预报精度均优于Liao等的BP神经网络方法；对于 $x _ { . }$ 分量中长期预报，除了120d、180d和240d的ELM神经网络方法的预报精度稍逊于Liao等的BP神经网络方法，其余跨度的预报精度优于Liao等的BP神经网络方法或与之相当；对于 $y _ { \mathrm { { p } } }$ 分量中长期预报，除了120d的预报精度稍逊于Liao等的BP神经网络方法，其余跨度的预报精度优于Liao等的BP神经网络方法或与之相当。从图2还可以发现，ELM神经网络预报误差曲线变化比较平缓，预报误差呈现逐渐增大趋势，而BP神经网络预报误差曲线跳跃较为明显，预报误差不稳定。

表1ELM神经网络极移预报与Liao等预报结果的平均绝对误差统计（单位：mas）

![](images/1a0cab28076fe38c2768fd5dbcee8eeb49323534eb31d78905550abf222cce5c.jpg)  
图2ELM神经网络预报误差与Liao等预报误差的对比

Fig.2 Comparison of the prediction errors for pole coordinates obtained by the ELM and Liao为了进一步分析ELM神经网络方法的预报性能，本文也预报了2005年10月1日至2008年2月28日（与EOP PCC时段相同）不同预报跨度的极移值，并将本文预报结果的平均绝对误差与EOP PCC预报结果的平均绝对误差进行对比分析和分析9，如图 $3 \sim$ 图5所示，图中数字代表参与E0PPCC的不同团队的编号，不同颜色曲线表示不同团队预报结果的平均绝对误差，参与EOPPCC的团队详细情况详见文献[9]，其中，极移超短期（ $( 1 \sim 1 0 \mathrm { d } )$ 预报精度较高的团队是Kalarus（编号061，黑色实线）和IERSEOP产品中心（编号071，绿色实线）；短期（ $1 \mathrm { \sim } 3 0 \mathrm { { d } } \cdot$ ）预报精度较高的团队是Kalarus（编号061，黑色实线）、Zotov（编号091，浅蓝色实线）和Kosek（编号051，灰蓝色实线）；中长期（ $1 \mathrm { \sim } 5 0 0 \mathrm { d }$ ）预报精度较高的团队是Kalarus（编号061，黑色实线）和Kosek（编号051，灰蓝色实线）。

从图 $3 \sim$ 图5可以看到，对于 $1 \mathrm { \sim } 1 0 \mathrm { d }$ 的超短期预报，ELM神经网络方法的预报精度仅低于排在第一位的Kalarus团队的预报精度，优于其他团队的预报精度；对于 $1 { \sim } 3 0 \mathrm { d }$ 的短期预报，ELM神经网络方法的预报精度大体处于所有团队的居中位置；对于 $\cdot 1 \mathord { \sim } 5 0 0 \mathrm { d }$ 的中长期预报，ELM神经网络方法的预报精度低于排在第一位的Kalarus团队的预报精度，稍逊于排在第二位的Kosek团队的预报精度或与之相当，优于其他团队的预报精度。

![](images/e7424394f3ac06215ab93839cf62b1fcb1d89abc2f87bd70284cb66f18bf6af4.jpg)  
图3ELM神经网络超短期（ $1 \mathrm { \sim } 1 0 \mathrm { d }$ ）预报误差与EOPPCC的对比

![](images/1dcc79364a0f8764ef2280355f6cf937206384d2823721fd982d8c82234c2da3.jpg)  
图4ELM神经网络短期（ $1 \mathrm { \sim } 3 0 \mathrm { d }$ ）预报误差与EOPPCC的对比 Fig.4 Comparison of the short-term $( 1 \sim 3 0 \mathrm { d } )$ prediction errors obtained by the ELM and EOP PCC

![](images/f783b6cc3322f37ba226cdfbb3efcdccd20f39cae6e6d26689861dba12a8a4cd.jpg)  
图5ELM神经网络中长期（ $1 \mathrm { \sim } 5 0 0 \mathrm { d }$ ）预报误差与EOPPCC的对比 Fig.5 Comparison of the medium- and long-term ( $\left( 1 \sim 5 0 0 \mathrm { d } \right)$ ）prediction errors obtained by the ELM and EOP PCC 4结论

本文针对极移序列非线性、非平稳变化的特性，将一种新型ELM神经网络用于极移中长期预报。通过预报试验可以发现，ELM神经网络用于极移中长期预报可以获得较好的预报效果。与BP神经网络预报结果的对比表明，ELM神经网络的预报精度优于BP神经网络的预报精度；与EOP PCC预报结果的比较发现，ELM神经网络的中长期预报精度优于大部分参与EOP PCC团队的预报精度。

# 参考文献

1DillR,Dobslaw H.Short-termpolar motionforecasts fromearthsystem modelingdata[J].JournalofGeodesy,2O10,84(9): 529-536.   
2GuoJY,LiYB,DaiCL,etal.Atechnique toimprove theaccuracyofEarthorientationpredictionalgorithmsbasedonleast squares extrapolation [J].Journal of Geodynamics,2O13,70(1O): 36-48.   
3KosekW,McCarthyDD,LuzumBJ.PossibleimprovementofEarthorientation forecastusingautocovariance prediction procedures [J]. Journal of Geodesy,1998,72(4):189-199.   
4AkyilmazO,KutererH.PredictionofEarthrotationparametersbyfuzzyinferencesystems[J].JouralofGeodesy204, 78(1-2): 82-193.   
5SchuhH,UlrichM,EggerD,etal.PredictionofEarthorientationparametersbyartificialneuralnetworks[J].Journalof Geodesy,2002,76(5): 247-258.   
6许雪晴，周永宏.地球定向参数高精度预报方法研究[J].飞行器测控学报，2010，29（2)：70-76. Xu Xueqing,Zhou Yonghong.High precisionprediction methodofEarthorientationparameters[J].Journalof SpacecraftT& Technology,2010,29(2): 70-76.   
7LiaoDC,WangQJ,ZhouYH,etal.Long-termpredictionoftheEarthorientationparametersbytheartificialneuralnetwork technique[J]. Journal of Geodynamics,2012,62(8): 87-925.   
8赵丹宁，雷雨，蔡宏兵．利用经验模态分解提高极移预报精度[J].天文研究与技术，2018，15（2)：140-150. Zhao Danning,Lei Yu,Cai Hongbing,Enhancementof thepredictionaccuracyof polecoordinates with empirical mode decomposition [J].ASTRONOMICAL RESEARCH& TECHNOLOGY,2018,15(2):140-150.   
9Kalarus M,Schuh H,Kosek W,etal.AchievementsoftheEarthorientatioparameters predictioncomparisoncampaign[J]. Journal of Geodesy,2010,84(10): 587-596.   
l0Huang GB,Zhou QY,SiewCK.Extreme learning machine:theoryandaplications[J].Neurocomputing,2006,70(1-3): 489-501.   
[1赵丹宁，雷雨．利用端点延拓提高 LS $^ +$ NN 模型的UT1-UTC 预报精度［J].天文研究与技术，2019，16（3)：294-299. Zhao Danning,LeiYu.Improving the performanceof the LS+NN model for UT1-UTC forecast with the edge extension [J]．ASTRONOMICAL RESEARCH& TECHNOLOGY，2019，16(3)：294-299.

# Medium- and long-term prediction of polar motion using extreme learning machine

Zhao Danning，Lei Yu

(1 School ofElectrical&Electronic Engineering,Baoji UniversityofArts and Sciences,Baoji 721ol3,China 2 SchoolofComputer Science&Technology,Xi'an UniversityofPosts &Telecommunications,Xi'an71O121,China)

Abstract: Linear models such as least squares (LS） extrapolation and autoregressve (AR) models get used to prediction Earth's polar motion. However, polar motion predictions obtained by linear models are not fully satisfactory owing to the non-linear and non-stationary variations in polar motion. In this paper,the extreme learning machine (ELM),a new training algorithm for single hidden layer feedback neural network (SLFN), is employed to prediction medium- and long-term polar motion. The LS extrapolation model is first employed to separate a linear trend, Chandler and annual wobbles (CW and AW) from observed polar motion time-series. The extracted linear trend, CW and AW are then predicted by using the above-mentioned LS extrapolation model. Secondly,the ELM is used for modeling and forecasting the residual time-series obtained by subtracting the LS extrapolation curve from the original polar motion data. In ELM training some special issues such as generation of training paterns and topology of the network for enhanced medium- and long-term prediction of polar motion are taken into consideration.The subsequently forecasted residuals are then added to the LS extrapolation so as to obtain the predicted values of polar motion. In order to demonstrate the efectiveness of the presented method,the results of the predictions of polar motion are analyzed and compared with those obtained by the back propagation (BP) neural network and Earth Orientation Parameters Prediction Comparison Campaign (EOP PCC). The results show that the predictions are comparable with or better than those obtained by other existing prediction methods and techniques in terms of the mean absolute error (MAE).

Key words: Polar motion; Prediction; Extreme learning machine; Neural network; Prediction model