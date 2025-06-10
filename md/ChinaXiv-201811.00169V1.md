# 一种基于GLRGMM的间歇过程在线监控策略\*

赵小强a,b,c，周文伟a,b

(兰州理工大学a.电气工程与信息工程学院；b.甘肃省工业过程先进控制重点实验室;c.国家级电气与控制工程实验教学中心，兰州 730050)

摘要：针对间歇过程的非线性和动态性，提出了全局一局部正则化高斯混合模型 (GLRGMM)算法。首先引入邻域保持嵌入算法提取局部流形结构，通过寻求一种低维投影对非线性过程进行全局结构保持，同时最大限度地保留局部流形特征；然后通过对高斯混合模型引入正则项来在线监控更新高斯模型，获取非线性数据流形结构，解决数据动态性问题；最后集成全局一局部监控指标实现在线监控。通过青霉素发酵过程进行了验证，结果表明所提算法比 DPCA、GLNPE具有更好的在线监控效果。

关键词：间歇过程；在线监控；动态特性；邻域保持嵌入算法；高斯混合模型 中图分类号：TP277 doi:10.19734/j.issn.1001-3695.2018.04.0441

# Online monitoring strategy for batch process based on GLRGMM

Zhao Xiaoqianga, b,c, Zhou Wenweia, b (a.CollegeofElectrical&InformationEngineering,b.KeyLaboratoryofGansuAdvancedControlforIndustrialProcesses, c.NationalExperimentalTeachingCenterofElectrical&ontrolEngineering,Lanzhou Universityofechnology,Lanzhou 730050, China)

Abstract:Aimingatnonlinearanddynamiccharacteristicsofbatch proces,thispaperproposedaglobal-localregularization Gausian mixture model (GLRGMM)algorithm.At first,this algorithm introduced Neighborhood Preserving Embedding algorithm to extract the local manifold structure.Itpreserved global structure of nonlinear process by seekinga low-dimensional projectionwhile preserved local manifold features to the maximum extent atthe same time.Then it introduced theregularization term intoGMM toonline monitorand update Gaussian model.Itobtained the manifoldstructure of nonlinear dataand solved thedata dynamiccharacteristicproblem simultaneously.Finaly,itusedthe integrationof global-localmonitoringindicators toeffectivelyachieveoninemonitoring.Theresults verifiedbythepenicilin fermentation process show that the proposed algorithm has better online monitoring effect than DPCA and GLNPE algorithms.

Key words: batch process; online monitoring; dynamic characteristic;NPE; GMM

# 0 引言

间歇过程由于其操作性强和灵活度高等优点成为一种重要的工业生产方式，特别是在精细化工、生物制药和食品饮料等小批量、高附加值产品的生产和制备当中得到广泛应用[1,2]。强非线性、动态性是间歇过程的固有特征，是实际生产过程和在线监控中面临的问题，而寻求一种有效的解决途径对降低经济损失和避免人员伤亡具有重要意义[3]。

随着工业过程控制系统的发展，大量过程数据被获取并得到有效利用，其中以PCA、ICA、PLS为主要代表的基于多元统计过程监控(multivariate statistical process monitoring,MSPM)方法在工业生产过程中得到了迅速发展和广泛应用。为了解决间歇过程中的非线性和动态性问题，KPCA[4]、DPCA和DPLS[5]应运而生并得到了成功应用。Lee等人[提出了多向核主成分分析算法(multi-waykernelPCA,MKPCA);Peng 等人[7]在T-PLS的基础之上提出了全影核偏最小二乘(total kernel partial leastsquares，T-KPLS)算法。这些算法在一定程度上能有效解决过程变量之间的非线性特性，但仍存在计算量大和核参数选择盲目性问题，并且忽略了时序相关性，没有考虑动态性问题，难以保证过程监控的准确性。Fan 等人[8提出了基于核函数的动态独立元分析KDICA算法；Lu等人[提出了双向动态主成分分析方法。这些方法都是通过历史数据扩展当前数据来消除时序相关性，并不能很好地消除过程数据的动态性。为了同时解决过程数据中的非线性和动态性，Wang 等人[10提出了双向动态核主成分分析法(dynamic kernel PCA,DKPCA)；Zhang 等人[11]提出了递归核PCA方法；Jia等人[12]提出了基于批动态核PCA方法。这些方法虽然能够同时监测过程数据非线性和动态特性，但没有考虑过程数据的全局和局部结构信息，仍存在主元个数多、故障误报率较高等问题。

近年来，流形算法由于其优越的局部流形结构特征提取和高维数据处理能力而越来越多地应用于过程监控领域。Hu等人应用局部保持投影算法(locality preserving projection,LPP)[13]和邻域保持嵌入算法(neighborhood preserving embedding,NPE)[14]对间歇过程进行了有效监控；Zhang等人[15]提出了一种基于全局一局部结构分析(global-local structure analysis,GLSA)算法，保持了全局结构信息的同时获取了局部流形结构； $\mathrm { Y u } ^ { [ 1 6 ] }$ 根据GLSA 提出了局部一全局PCA (local and global PCA,LGPCA)算法；Tong等人[17]提出了多流形投影(multi-manifoldprojection,MMP)算法，结合了全局和局部方差信息用于过程监控。这些算法虽然提取了数据的全局和局部信息，但并没有有效解决数据的非线性和动态性问题。由于高斯混合模型(Gaussianmixturemodel,GMM)可以更好地处理复杂过程数据而被用于估计复杂数据分布，并成功应用于非线性、动态特性的工业过程中[18\~20]。

为了解决间歇过程的非线性和动态特性，并且有效提取过程数据的全局一局部信息，本文提出了全局一局部正则化高斯混合模型(global-local regularization Gaussian mixture model,GLRGMM)算法。由于NPE 可以更好地获取高维数据的局部流形特征，通过对NPE进行改进求取一个新的低维投影，获取高维空间全局-局部流形结构，实现非线性过程数据降维和特征提取；然后对GMM进行动态流形正则化，自动更新获取当前数据；最后通过NLLP (negative log likelihood probability)和MD(mahalanobisdistance)统计全局、局部概率生成综合监控指标GLP(globallocal probability)，实现对间歇过程的在线监控。

# 1全局一局部邻域保持嵌入算法

# 1.1邻域保持嵌入算法(NPE)

NPE算法能够挖掘出高维空间中隐藏的低维流形结构，能保持原始空间的局部流形结构。其目的是将 $R ^ { D }$ 空间的高维数据映射到一个相对低维的特征空间 $Y = \left\{ y _ { 1 } , y _ { 2 } , \cdots , y _ { d } \right\}$ ，$\Bigl \{ y _ { i } \left| y _ { i } \in R ^ { d } \right. \Bigr \} \bigl ( d < D \bigr )$ ，同时求出相应的变换矩阵$A = \left\{ \mathbf { a } _ { 1 } , \mathbf { a } _ { 2 } \cdots , \mathbf { a } _ { d } \right\} \circ$ （204号

首先根据 $k$ 近邻法确定样本点 $x _ { i }$ 的 $k$ 个近邻点并组成局部邻域 $M \left( x _ { i } \right)$ ，再通过近邻点来计算权重系数矩阵 $W$ ，权重系数矩阵可通过求解式（1）的最优解得到。

$$
\operatorname* { m i n } \sum _ { i } \Biggl \| x _ { i } - \sum _ { j } w _ { i j } x _ { j } \Biggr \| , ~ \sum _ { j } w _ { i j } = 1 , j = 1 , 2 , \cdots , N
$$

映射变换矩阵 $A$ 通过式（2）最优解得到。

$$
A = \arg \operatorname* { m i n } \left[ \sum _ { i } \left\| y _ { i } - \sum _ { j } w _ { i j } y _ { j } \right\| ^ { 2 } \right] = \arg \operatorname* { m i n } t r \big ( A ^ { \mathrm { T } } X M X ^ { T } A \big )
$$

NPE 虽然能很好地保持局部流形结构，并能揭示隐藏在高维数据中的非线性，但忽略了全局结构，并不能更好地保持数据结构信息。因此，本文首先提出了全局-局部邻域保持嵌入(global-local neighborhood preserving embedding,GLNPE） 算法。

# 1.2全局一局部邻域保持嵌入(GLNPE)算法

# 1.2.1全局结构保持

对于 $R ^ { D }$ 空间样本集 $X = \left[ x _ { I } , x _ { 2 } , \cdots , x _ { n } \right]$ ，寻找投影矩阵$A$ ，通过投影映射 $Y = A ^ { \mathrm { { T } } } X$ 将其投影到低维特征空间，根据方差最大方向来最大程度地保留原始数据全局结构信息，其目标函数如式（3）所示。

$$
J _ { _ { g l o b a l } } \left( A \right) = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } A ^ { \top } \left( x _ { i } - \overline { { x } } \right) \left( x _ { i } - \overline { { x } } \right) ^ { \mathrm { T } } A = A ^ { \top } C A
$$

其中： ${ \overline { { x } } } = { \frac { 1 } { n } } \sum x _ { i }$ ； $C = { \frac { 1 } { n } } \sum _ { i = 1 } ^ { n } { \big ( } x _ { i } - { \overline { { x } } } { \big ) } { \big ( } x _ { i } - { \overline { { x } } } { \big ) } ^ { \mathrm { T } }$ 。

# 1.2.2局部结构保持

局部结构保持是通过每个数据点及其近邻点进行重构来挖掘出数据局部结构信息，其保留局部结构的目标函数如式（4)所示。

$$
\begin{array} { r l r } {  { \boldsymbol { J } _ { l o c a l } ( \boldsymbol { A } ) = \operatorname* { m i n } \sum \| \boldsymbol { y } _ { i } - \sum _ { j = 1 } ^ { k } \boldsymbol { w } _ { i j } \boldsymbol { y } _ { i } \| ^ { 2 } = \operatorname* { m i n } \boldsymbol { Y } ^ { \top } ( I - \boldsymbol { W } ) ^ { \top } ( I - \boldsymbol { W } ) \boldsymbol { Y } } } \\ & { } & { = \operatorname* { m i n } \boldsymbol { A } ^ { \top } \boldsymbol { X } ( I - \boldsymbol { W } ) ^ { \top } ( I - \boldsymbol { W } ) \boldsymbol { X } ^ { \top } \boldsymbol { A } = \operatorname* { m i n } \boldsymbol { A } ^ { \top } \boldsymbol { X } \boldsymbol { M } \boldsymbol { X } ^ { \top } \boldsymbol { A } } \end{array}
$$

其中：W 为权重矩阵； $M = \left( I - W \right) ^ { \operatorname { T } } \left( I - W \right)$ 0

# 1.2.3全局一局部邻域保持嵌入算法(GLNPE)

为了更加充分地提取过程数据特征，需要找到一种投影使得在低维空间同时保留全局和局部信息，即在式（3）最大的同时能保证式（4）最小。为了解决这个复杂优化问题，本文提出了新的目标函数：

$$
\begin{array} { r l } & { J \left( A \right) = \operatorname* { m i n } \frac { J _ { { l o c a l } } \left( A \right) } { \eta J _ { { g l o b a l } } \left( A \right) + \left( 1 - \eta \right) J _ { { l o c a l } } \left( A \right) } } \\ & { \qquad = \operatorname* { m i n } \frac { A ^ { \scriptscriptstyle \mathrm { T } } X M X ^ { \scriptscriptstyle \mathrm { T } } A } { \eta A ^ { \scriptscriptstyle \mathrm { T } } C A + \left( 1 - \eta \right) A ^ { \scriptscriptstyle \mathrm { T } } X M X ^ { \scriptscriptstyle \mathrm { T } } A } } \end{array}
$$

其中： $0 < \eta < 1$ 为可调平衡参数，本文取 $\eta = 0 . 8 5$ 。式（5）最小化问题可以通过拉普拉斯方法求得投影矩阵 $A$ ：

$$
\left( \eta C + \left( 1 - \eta \right) M \right) A = \lambda A ^ { \mathrm { T } } X M X ^ { \mathrm { T } } A
$$

由此可得低维特征空间数据：

$$
Y = A ^ { \mathrm { T } } X
$$

通过投影映射 $A$ 将高维数据投影到低维特征空间的同时最大程度地保留了全局一局部结构信息，更有助于对非线性数据特征的提取。

# 2 全局一局部正则化高斯混合模型(GLRGMM)算法

假设原始变量空间数据为 $D = \left\{ X _ { i } \middle | i = 1 , 2 , \cdots , n \right\}$ ，其中 $n$ 为变量个数，每个变量的维数为 $m$ ，则样本的高斯混合模型可表示为

$$
p \left( \boldsymbol { X } \right) = \sum _ { k = 1 } ^ { K } \omega _ { k } g \left( \boldsymbol { X } \left| \mu _ { k } , \boldsymbol { \Sigma } _ { k } \right. \right)
$$

其中： $K , \omega _ { k } , \mu _ { k } , \Sigma _ { k }$ 分别表示高斯成分数，第 $k$ 个高斯成分的权重、均值和方差，其目标函数可以写成

$$
J ( \theta ) = \operatorname* { m a x } [ \log p ( \boldsymbol { X } ) ] = \operatorname* { m a x } \Biggl [ \log \prod _ { i = 1 } ^ { n } p ( x _ { i } | \theta ) \Biggr ]
$$

通过 GLNPE 提取特征空间中的两个数据点 $X _ { i }$ 和 $X _ { j }$ ，其余弦相似性矩阵 $S _ { i j } = \cos \angle \left( X _ { i } , X _ { j } \right)$ 0

定义正则项 $R _ { k }$ ：

$$
\begin{array} { l } { { \displaystyle R _ { k } = \frac { 1 } { 2 } \sum _ { i , j = 1 } ^ { n } ( p ( C _ { k } | X _ { i }  ) - p ( C _ { k } | X _ { j } ) ) ^ { 2 } S _ { i j } } \ ~ } \\ { { \displaystyle ~ = \sum _ { i = 1 } ^ { n } p ( C _ { k } | X _ { i }  ) ^ { 2 } I _ { i i } - \sum _ { i , j = 1 } ^ { n } p ( C _ { k } | X _ { i }  ) p ( C _ { k } | X _ { j }  ) S _ { i j } } \ ~ } \\ { { \displaystyle ~ = f _ { C _ { k } } ^ { \top } I _ { i i } f _ { C _ { k } } - f _ { C _ { k } } ^ { \top } S f _ { C _ { k } } } \ ~ } \\ { { \displaystyle ~ = f _ { C _ { k } } ^ { \top } L f _ { C _ { k } } } \ ~ } \end{array}
$$

其中： $I _ { i i }$ 为单位矩阵； $L = I - S$ ； $p { \left( C _ { k } \left| X _ { i } \right. \right) }$ 为 $X _ { i }$ 属于第 $k$ 个高斯成分的后验概率，且

$$
f _ { k } = \left. p \Big ( C _ { k } \left. X _ { 1 } \right) , \cdots , p \Big ( C _ { k } \left. X _ { m } \right) \right. ^ { \mathrm { T } }
$$

通过最小化 $R _ { k }$ 确定后验概率，使得不同高斯成分之间平滑过渡，去掉后验概率最小的高斯成分，更新当前高斯成分，实现动态过程平滑过渡和数据实时更新。引入一个包含正则项 $R _ { k }$ 的新目标函数：

$$
J _ { _ { n e w } } \left( \theta \right) = \sum _ { i = 1 } ^ { n } \sum _ { k = 1 } ^ { K } p \left( C _ { k } \left| X _ { i } \right. \right) \log \left( \omega _ { k } g \left( X _ { i } \left| \mu _ { k } , \Sigma _ { k } \right. \right) \right) - \lambda R _ { k }
$$

其中： $\lambda$ 为正则化参数。采用 $\mathbf { K }$ -means 算法得到初始参数$K _ { \mathrm { 0 } } , \omega _ { \mathrm { 0 } } , \mu _ { \mathrm { 0 } } , \Sigma _ { \mathrm { 0 } }$ 通过 EM 迭代自动更新确定高斯成分参数$\theta \big ( K , \omega , \mu , \Sigma \big ) \ _ { \circ }$ （20

E-step:

通过最小化 $R _ { k }$ 确定后验概率：

$$
p ^ { ( s ) } \left( C _ { k } \left| X _ { i } \right. \right) = p ^ { ( s - 1 ) } \left( C _ { k } \left| X _ { i } \right. \right) - \frac { \displaystyle \sum _ { j = 1 } ^ { n } S _ { i j } p \left( C _ { k } \left| X _ { j } \right. \right) } { \displaystyle \sum _ { j = 1 } ^ { n } S _ { i j } }
$$

M-step:

$$
\omega _ { k } ^ { ( s + 1 ) } { = } \frac { \displaystyle \sum _ { i = 1 } ^ { n } p ^ { ( s ) } \left( C _ { k } \left| X _ { i } \right. \right) } { n }
$$

$$
\mu _ { k } ^ { ( s + 1 ) } = \frac { \displaystyle \sum _ { i = 1 } ^ { n } x _ { i } p ^ { ( s ) } \big ( { C } _ { k } \big | X _ { i } \big ) } { \displaystyle \sum _ { i = 1 } ^ { n } p ^ { ( s ) } \big ( { C } _ { k } \big | X _ { i } \big ) }
$$

$$
{ \underset { i = 1 } { \sum _ { k } ^ { \left( s + 1 \right) } } } = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } p ^ { \left( s \right) } \left( C _ { k } \left| X _ { i } \right. \right) \left( X _ { i } - \mu _ { k } ^ { \left( s + 1 \right) } \right) \left( X _ { i } - \mu _ { k } ^ { \left( s + 1 \right) } \right) ^ { \mathrm { T } } } { \displaystyle \sum _ { i = 1 } ^ { n } p ^ { \left( s \right) } \left( C _ { k } \left| X _ { i } \right. \right) } }
$$

其中： $\omega _ { k } ^ { ( s + 1 ) } , \mu _ { k } ^ { ( s + 1 ) } , \Sigma _ { k } ^ { ( s + 1 ) }$ 分别表示第 $s { + } 1$ 步迭代中第 $k$ 个高斯成分的权重、均值和方差。

GLRGMM通过GLNPE对非线性数据的全局一局部结构特征进行了更加充分地提取，更符合实际间歇过程数据特性。其详细的算法流程如图1所示。

![](images/55a4fc2c463c35d21d348b0e8632fedf37346ff7ab11739b1b05ac6c72221620.jpg)  
图1GLRGMM算法流程  
Fig.1Flowchart of GLRGMMalgorithm

# 3 基于GLRGMM的监控策略

# 3.1间歇过程数据预处理

间歇过程实时监测得到的数据为三维数据：

$X \left( I \times J \times K \right)$ ，其中： $I$ 为批次个数； $J$ 为变量个数； $K$ 为采样时间。在实际的生产过程中，由于不同批次的采样时间不同等原因而不可能做到完全重复同批次的生产，这就不可避免地出现数据不等长问题。本文采用最短长度法[21，以最短的一个批次数据作为标准而将其余批次数据进行硬性截取，使得所有批次数据都具有相等长度。

对间歇过程的三维数据进行建模，需要把已处理成相等长度的数据展开成与连续过程相类似的二维数据。本文结合了批次展开可以去除非线性、变量展开可以消除数据预估问题的优点，展开方式如图2所示。

![](images/7eb6ce2a1d86aea381a775673585f34de4bcba07b7addd9192b3b9fdbd6bace4.jpg)  
图2间歇过程数据展开方式  
Fig.2Scheme of batch process data unfolding

首先，将三维数据 $X \left( I \times J \times K \right)$ 按批次方向展开成二维数据 $X \left( I \times J K \right)$ 并进行标准化处理：

$$
\overline { { \ v { x } } } _ { j , k } \ = \ \frac { 1 } { I } \sum _ { i = 1 } ^ { I } \ v { x } _ { i , j , k }
$$

$$
\delta _ { j , k } \ = \ \sqrt { \frac { 1 } { I \ - \ 1 } \sum _ { i = 1 } ^ { I } { ( x _ { i , j , k } \ - \ \overline { { x } } _ { j , k } ) ^ { 2 } } }
$$

$$
\overline { { \boldsymbol { x } } } _ { i , j , k } \ = \ \frac { \boldsymbol { x } _ { i , j , k } \ - \ \overline { { \boldsymbol { x } } } _ { j , k } } { \boldsymbol { \delta } _ { j , k } }
$$

得到的数据在一定程度上可以消除非线性和动态特性；然后将标准化的二维数据 $X \left( I \times J K \right)$ 重置为三维数据$X \left( I \times J \times K \right)$ ，再按变量方向展开成二维数据 $X \left( K I \times J \right)$ 并进行标准化。这种展开方式可以消除在线监控时的数据预估问题，提高了实时监控的精确率，降低了误报率。

# 3.2GLP(global local probability)监控指标

为了统计全局概率指标，首先引入负对数似然概率（negative log likelihood probability,NLLP）。

$$
N L L P { \big ( } X _ { i } { \big ) } = - \log p { \big ( } C _ { k } \left| X _ { i } \right. { \big ) }
$$

全局概率指标通过比较测试数据与训练数据的NLLP得到

$$
P _ { g } \left( X _ { t e s t } \right) = \operatorname* { P r } \left\{ N L L P \left( X _ { t e s t } \right) \leq N L L P \left( X _ { t r a i n } \right) \right\}
$$

引入服从 $\chi ^ { 2 }$ 分布的马氏距离（Mahalanobis distance,MD）：

$$
M D \big ( \boldsymbol { X } _ { i } \big ) = \big ( \boldsymbol { X } _ { i } - \boldsymbol { \mu } _ { k } \big ) \big ( \boldsymbol { \Sigma } _ { k } \big ) ^ { - 1 } \big ( \boldsymbol { X } _ { i } - \boldsymbol { \mu } _ { k } \big ) ^ { \mathrm { T } }
$$

定义局部概率指标：

$$
\begin{array} { r l } & { P _ { l } ^ { ( k ) } \left( X _ { t e s t } \right) = \operatorname* { P r } \Big \{ M D \big ( \big ( X _ { t r a i n } , C _ { k } \big ) \big | X _ { t r a i n } \in C _ { k } \Big ) } \\ & { \qquad \le M D \big ( \big ( X _ { t e s t } , C _ { k } \big ) \big | X _ { t e s t } \in C _ { k } \big ) \Big \} } \end{array}
$$

通过集成全局一局部概率生成GLP(global local probability)监控指标：

$$
G L P = \sum _ { k = 1 } ^ { K } P _ { g } \left( C _ { k } \left| X _ { t e s t } \right. \right) P _ { l } ^ { \left( k \right) } \left( X _ { t e s t } \right)
$$

# 3.3离线建模

a）在正常工况下采集若干批次数据 $X \left( I \times J \times K \right)$ 作为训  
练样本，采用3.1节的方法进行数据预处理，最终得到已标准  
化处理的二维数据 $X \left( K I \times J \right)$ b）通过GLNPE进行全局一局部信息保持，由式（6）（7）  
得到低维特征空间投影数据 $Y$ ：c）利用GLRGMM对数据 $Y$ 进行正则化，用EM算法确  
定参数 $\theta$ ：d)通过式(20)(22)分别计算 $N L L P \big ( X _ { t r a i n } \big ) \mathrm { ~ , ~ } M D \big ( X _ { t r a i n } \big )$ 。

# 3.4在线监控

a）将测试数据按3.1节的方法进行数据预处理。b）通过GLNPE算法而得到新的测试数据的投影数据 $Y$ 0c）通过GLRGMM对新的投影数据 $Y$ 进行正则化，用EM算法确定参数 $\theta$ 。d)通过式（20)（22)分别计算 $N L L P \big ( X _ { t e s t } \big )$ 、 $M D \big ( X _ { t e s t } \big )$ 。e）通过式（21）（23）分别计算全局、局部概率指标。f）通过式（24）计算GLP监控指标，若 $\mathrm { G L P > 0 . 9 9 }$ ，则出现故障；否则，重复步骤b）\~f）直到出现故障报警或生产过程结束。

# 4 案例研究

青霉素作为一种重要抗生素而被临床广泛应用，其生产制备过程是典型的间歇过程，具有强非线性、动态性等特性。本文基于美国Illinois州立理工学院开发的Pensim2.0标准青霉素仿真平台[22]产生出间歇过程数据，它可产生出不同初始条件和不同工况下青霉素发酵过程中各变量每个时刻的数据用于分析研究。

本文将每批次的反应时间设定为 $4 0 0 \mathrm { { h } }$ ，采样时间设为0.5h，在正常范围设置不同初始条件，不引入故障的情况下共产生35 个批次正常工况下数据，从产生的18个变量数据中选择其中 10个过程变量作为监控变量（表1)，构成三维数据$\mathrm { X } ( 3 5 { \times } 1 0 { \times } 8 0 0 )$ 作为训练样本。

Table1Process variables   

<html><body><table><tr><td>变量号</td><td>变量名称</td></tr><tr><td>1</td><td>通风速率 (L/h)</td></tr><tr><td>2</td><td>搅拌功率（w)</td></tr><tr><td>3</td><td>补料温度（K)</td></tr><tr><td>4</td><td>溶解氧浓度（mmol/L)</td></tr><tr><td>5</td><td>反应器体积（L)</td></tr><tr><td>6</td><td>排气二氧化碳浓度(mmol/L)</td></tr><tr><td>7</td><td>pH值</td></tr><tr><td>8</td><td>发酵罐浓度(K)</td></tr><tr><td>9</td><td>产生热（K)</td></tr><tr><td>10</td><td>冷水流加速率(L/h)</td></tr></table></body></html>

Pensim2.0提供了三种故障类型（通风速率、搅拌功率、底物流加速率)。本文引入故障类型1（即变量1通风速率）和故障类型2（即变量2搅拌功率)，在时间 $2 0 0 { \sim } 3 0 0 ~ \mathrm { h }$ 即采样点400\~600)加入 $1 5 \%$ 的阶跃信号作为故障信号，所产生的数据作为故障测试数据以供在线监控。通过GLRGMM对训练数据建模得到高斯成分如图3所示。分别用DPCA、GLNPE和GLRGMM算法进行监控，对于DPCA和GLNPE给出故障1的监控图，如图4\~7所示；其余详细监控结果见表2、3。GLRGMM对故障1和2的监控结果如图8、9所示。

![](images/20ceabd618719f20cc2171a37eed7b9efad8f31386a7164697c594fd4d46c190.jpg)  
图3训练数据建模结果

![](images/742fd6adae3c11a015c8e319957ee0998aa0ae417da9426472dbe0909297e4e9.jpg)  
Fig.3Modeling results of training data   
图4DPCA对故障1的 $T ^ { 2 }$ 监控图  
Fig.4 $T ^ { 2 }$ monitoring diagram of DPCA for fault 1

![](images/f42e011e98b99d1aca6d08fe2d12bba3490808a3a8932db8b2efbb3fecdc0bbb.jpg)  
图5DPCA对故障1的 SPE 监控图

![](images/792d3355015ab985525ad286f6705b4c1b4ce19b52c006034d5b3abed3aefeba.jpg)  
Fig.5SPE monitoring diagram of DPCA for fault 1

![](images/2d78f1420766031d768bb3de4117ac2593cf7f959d6add3ec9b6b714340c2007.jpg)  
Fig.6 $\scriptstyle { \pmb { T } } ^ { 2 }$ monitoring diagram of GLNPE for fault 1   
图7GLNPE对故障1的 SPE 监控图  
Fig.7SPE monitoring diagram of GLNPE for fault1

表1过程变量  
表2不同方法对故障1的监控统计 $1 \%$ （204号  
Table 2Monitoring statistics of different methods for fault 1 $1 \%$ （204号   

<html><body><table><tr><td>方法</td><td>DPCA</td><td>DPCA</td><td>GLNPE</td><td>GLNPE</td><td>GLRGMM</td></tr><tr><td>(统计量)</td><td>(T²）</td><td>(SPE)</td><td>(T²）</td><td>(SPE)</td><td>(GLP)</td></tr><tr><td>误报率</td><td>26.36</td><td>10.7</td><td>3.02</td><td>9.18</td><td>0.5</td></tr><tr><td>漏报率</td><td>19.4</td><td>16.92</td><td>3.98</td><td>11.44</td><td>0</td></tr><tr><td>检测率</td><td>80.6</td><td>83.08</td><td>96.02</td><td>88.56</td><td>100</td></tr></table></body></html>

![](images/1fda5065ab65cb2afa0350820b5e8fe570603e2d1167007755c256ddf884c534.jpg)  
图6GLNPE 对故障1的 $\scriptstyle { \pmb { T } } ^ { 2 }$ 监控图  
图8 GLRGMM对故障1的监控图  
Fig.8Monitoring diagram of GLRGMMfor fault 1

![](images/572a14681e7128791eee6b277511ef9f8d304f98f32937a090764b814ceee14b.jpg)  
图9 GLRGMM对故障2的监控图  
Fig.9Monitoring diagram of GLRGMMfor fault 2表3不同方法对故障2的监控统计 $1 \%$

Table 3Monitoring statistics of different methods for fault 2 $1 \%$   

<html><body><table><tr><td>方法</td><td>DPCA</td><td>DPCA</td><td>GLNPE</td><td>GLNPE</td><td>GLRGMM</td></tr><tr><td>(统计量）</td><td>(T²)</td><td>(SPE)</td><td>(T²)</td><td>(SPE)</td><td>(GLP)</td></tr><tr><td>误报率</td><td>16.48</td><td>8.16</td><td>14.85</td><td>6.36</td><td>0</td></tr><tr><td>漏报率</td><td>18.91</td><td>15.53</td><td>14.43</td><td>12.97</td><td>8.96</td></tr><tr><td>检测率</td><td>81.09</td><td>84.47</td><td>85.57</td><td>87.03</td><td>91.04</td></tr></table></body></html>

图4\~7为采用DPCA和GLNPE对故障1的监控，从图中可以明显看出DPCA和GLNPE 均有误报、漏报产生。虽然DPCA 在一定程度上可以解决动态性；但从表2可以看出GLNPE的误报率、漏报率较低、检测率高于DPCA，这是因为DPCA并不能很好地保持非线性数据过程中的全局、局部结构，只是对线性过程的动态特性处理。GLNPE不仅保持了全局结构信息，而且可以有效地提取隐藏在高维空间中的低维流形结构，虽然不是对非线性最有效地解决途径，但通过保持非线性数据的全局、局部信息，故障检测率明显优于传统直接忽略非线性的方法。表3为故障2的监控统计结果，从表3也可以看出GLNPE比DPCA具有更好的监控效果，进一步证实了保持全局-局部信息对非线性过程监控的有效性。

图8、9为GLRGMM对故障1和故障2的监控，可以看出GLRGMM的监控效果优于DPCA和GLNPE。GLRGMM可以检测出所有故障1的变量，没有漏报产生，误报率仅为 $0 . 5 \%$ ，检测速度快;对故障2虽有漏报，但没有误报，检测率为 $9 1 . 0 4 \%$ ，故障敏感性高。这是因为GLRGMM不仅最大程度地保持了非线性数据的全局、局部结构，而且考虑了数据的动态性，对非线性和动态特性过程具有明显的优越性。

# 5 结束语

强非线性、动态性是间歇过程的固有特性，本文提出的基于GLRGMM的监控策略，不仅通过改进NPE对非线性数据进行全局一局部结构保持，而且通过引入正则项对高斯模型进行在线更新，最后整合全局一局部概率指标进行在线监控。通过青霉素发酵过程的仿真实验结果表明该方法比DPCA、GLNPE有更好的监控效果，降低了误报率、漏报率，提高了故障监控的快速性和精确性。

# 参考文献：

[1]郭金玉，袁堂明，李元．一种不等长的多模态间歇过程故障检测方法 [J]．化工学报,2016,67(7):2916-2924.(Guo Jinyu,Yuan Tangming,Li Yuan.Fault detection methodfor uneven-length multimode batch processes [J].CIESC Journal,2016,67(7): 2916-2924.)

[2] 王普，李春蕾，高学金，等．基于角结构统计量的 MKECA 间歇过程故 障监测[J].仪器仪表学报,2017,38(1):174-180.(Wang Pu,LiChunlei, Gao Xuejin,et al. Research on batch process monitoring method based on multi-way kernel entropy component analysis and angular structure statistic [J]. Chinese Journal of Scientific Instrument,2O17,38 (1): 174-180. )   
[3]赵小强，王涛．基于 TGNPE 算法的间歇过程故障诊断[J].化工学报， 2016,67 (3):1055-1062. (Zhao Xiaoqiang, Wang Tao.Batch processfault diagnosis based on TGNPE algorithm [J].CIESC Journal,2016,67 (3): 1055-1062. )   
[4]Ben IK,Liama M,Weihs C.Variable window adaptive kernel principal component analysis for nonlinear nonstationary process monitoring [J]. Computers & Industrial Engineering,2011,61(3): 437-466.   
[5]Chen J,Liu K C.On-line batch process monitoring using dynamic PCA and dynamic PLS models [J]. Chemical Engineering Science,20o2,57 (1): 63-75.   
[6] Lee J M, Changkyoo Y, In-Beum L.Fault detection of batch processes using multi-way kernel principal component analysis [J]. Computers& Chemical Engineering,2004,28(9):1837-1847.   
[7]Peng Kaixiang,Zhang Kai,Li Gang，et al.Contribution rate plot for nonlinear quality related fault diagnosis with application to the hot strip mill process [J]. Control Engineering Practice,2013,21 (4): 360-369.   
[8]Fan Jicong,Wang Youqing.Fault detection and diagnosis of non-linear non-Gaussian dynamic processes using kernel dynamic independent component analysis [J]. Information Sciences,2014,259 (3): 369-379.   
[9]Lu Ningyun,Yao Yuan,Gao Furong,et al. Two-dimensional dynamic PCA for batch process monitoring [J].AIChE Journal: Chemical Engineering Research and Design,2005,51 (12): 3300-3304.   
[10] Wang Ting，Wang Xiaogang,Zhang Yingwei,et al. Fault detection of nonlinear dynamic processes using dynamic kernel principal component analysis [C]//Procof the7th World Congress on Intellgent Controland Automation.2008: 3009-3014.   
[11] Zhang Yingwei,Li Shuai, Teng Yongdong. Dynamic processes monitoring using recursive kernel principal component analysis [J].Chemical Engineering Science,2012,72(16):78-86.   
[12] Jia Mingxing,Chu Fei,Wang Fuli,et al.On-line batch processmonitoring usingbatchdynamickernelprincipal componentanalysis[J]. Chemometrics and Intelligent Laboratory Systems,2010,101 (2): 110-122.   
[13]Hu Kunlun,Yuan Jingqi.Multivariate statistical process control based on multiway locality preserving projections [J]. Journal of Process Control,

2008,18(7-8):797-807.

[14] Hu Kunlun,Yuan Jingqi. Statistical monitoring of fed-batch process using dynamic multiway neighborhood preserving embedding[J].Chemometrics &IntelligentLaboratory Systems.2008,90(2):195-203.   
[15] Zhang Muguang,Ge Zhiqiang,Song Zhihuan,et al. Global-local structure analysis model and its application for fault detection and identification [J]. Industrial & Engineering Chemistry Research,2011,50(11): 6837-6848.   
[16] Yu Jianbo.Local and global principal component analysis for process monitoring[J]. Journal of Process Control,2012,22(7):1358-1373.   
[17] Tong Chudong,Yan Xuefeng. Statistical process monitoring based on a multi-manifold projection algorithm [J]. Chemometrics & Intelligent Laboratory Systems,2014,130 (15): 20-28.   
[18] Yu Jie,Qin S J.Multimode process monitoring with Bayesian inference-based finite Gaussian mixture models [J].AIChE Journal,2008,

54(7):1811-1829.

[19] Chen Tao,Zhang Jie.On-line multivariate statistical monitoring of batch processes using Gaussian mixture model [J].Computers & Chemical Engineering,2010,34(4): 500-507.   
[20] Yu Jianbo. Semiconductor manufacturing process monitoring using Gaussian mixture model and Bayesian method with local and nonlocal information [J].IEEE Trans on Semiconduct,Manufact,2012,25 (3): 480-493.   
[21]Kourti T.Multivariate dynamic data modeling for analysis and statistical process control of batch processes,startups and grade transitions [J]. Journal of Chemometrics,2003,17(1): 93-109.   
[22] Birol G, Undey C,Cinar A.A modular simulation package for fed-batch fermentation: penicillin production [J].Computersand Chemical Engineering,2002,26(11):1553-1565.