# 基于最大互相关熵UKF的传感网目标状态和系统偏差联合估计算法

赵季红1²，谢志勇1，曲桦²，王明欣¹，刘熙²(1．西安邮电大学 通信与信息工程学院，西安 710121;2.西安交通大学 电子与信息工程学院，西安 710049)

摘要：针对空天地一体化传感网络中传感器观测目标时观测噪声具有重尾或突变性质的问题以及系统偏差对目标状态估计的影响，提出一种基于最大互相关熵无迹卡尔曼滤波（MCUKF）的目标状态和系统偏差联合估计（ASMCUKF)算法。MCUKF算法首先通过无迹变换(UT)获得预测状态估计值和协方差矩阵，然后使用基于最大互相关熵准则(MCC)的非线性回归方法重新构建观测信息，增强了UKF对重尾噪声的鲁棒性。ASMCUKF 算法通过目标状态向量扩维的方法建立状态方程和带有系统误差的非线性观测方程，根据估计的系统偏差进行偏差配准，改善了系统偏差对目标状态估计的影响。仿真结果表明，ASMCUKF在重尾非高斯观测噪声的环境下对通信目标状态和系统偏差的估计效果比传统方法更好。

关键词：空天地一体化；传感网络；无迹卡尔曼滤波；最大互相关熵准则；系统偏差中图分类号：TN92 doi: 10.3969/j.issn.1001-3695.2017.08.0884

# Augmented target state estimation algorithm with systematic errors based on maximum correntropy unscented Kalman filter in sensor networks

Zhao Jihong1, ²,Xie Zhiyong1, Qu Hua²,Wang Mingxin1,Liu $\mathrm { X i } ^ { 2 }$ (1.SchoolofTelecommunication&InformationEngineering,Xi'an UniversityofPosts&Tlecommunications,Xi'a7011, China; 2.Schoolof Electronic & Information Engineering,Xi'an Jiaotong University, Xi'an 710049,China)

Abstract: This letter proposeamethodthatcombines targettate and system errorbasedonte maximumcorrentropycriterion unscented Kalman filter(MCUKF),namely ASMCUKF,which can solve the problems thathe observation noiseof sensor is heavy-tailedor has some sudden change in Space-Air-Ground integratedsensor network..Firstly,MCUKFusesunscented transformation(UT)toobtainthe predictedstate estimationandcovariance matrix,andthenanon-linearregressionmodelbased on MCC is used to reconstruct the observed informationand strengthen therobustness of UKF in heavy-tailed noise.The ASMCUKF algorithm establishes the state equationandthe nonlinearobservationequation with systematic erors through the expansion of target state vector,and makes the error registration according to the estimated system errors to improve the influence ofthe system erors on the target state estimation.The simulation results show that the ASMCUKF has abetter performanceforthestate estimationofthecommunicationtargethanthe traditional methodin theenvironmentofheavy-tailed non- Gaussian noise.

KeyWords:space-air-groundintegrated;sensornetwork;unscentedKalman filter; maximumcorrentropy criterion;systematic errors

# 0 引言

络。其具有快速展开、鲁棒性强、容错性高等特点，可实现对通信目标的数据采集、处理和传输，在国防军事、卫星通信、飞机通信、车载网、工业控制、环境监测、健康护理等领域有广泛的应用前景[1,2]。

空天地一体化传感网络是由遥感卫星、无人机、飞艇、气球、地面传感器等传感资源和地面数据处理中心组成的新型网

传感网络中对目标相关状态估计的问题，是目前研究热点之一，主要通过实时的优化估计算法对通信目标的位置信息进行估计预测。对于位置估计常用的几种观测方法[3有：到达角（AOA）、到达时间（TOA）、到达时间差（DTOA）、接收的信号强度（RSSI），以及一些混合的方法。因为目标的观测通常是非线性函数，传统的状态估计方法主要利用卡尔曼相关方法对通信目标状态进行估计，并假设观测噪声为高斯噪声，如拓展卡尔曼滤波（EKF）[4]、无迹卡尔曼滤波（UKF）[5]，以及一些改进的滤波器：基于最大似然估计的卡尔曼滤波[6、基于UKF的无迹粒子滤波(UPF)[7]。而在传感网的实际应用中，重尾非高斯噪声比较常见，而 EKF 和UKF 都是基于最小均方差准则的，对重尾噪声表现出强敏感性，因此不能表现出良好的滤波性能[8]。为了解决这个问题，文献[9]提出了一种鲁棒的方法—一互相关熵（Correntropy），其不仅可以获得二阶统计量，还可以获得更高阶的统计量，基于它的准则被称为最大互相关熵准则（MCC），并且已在一些领域得到了广泛的应用[10-14]。针对观测噪声呈现重尾的非高斯状况，文献[15]提出了一种新颖的MCUKF算法，将MCC与UKF结合提高了UKF的鲁棒性。

针对单个传感器观测的不确定性和局限性，通常利用多传感器进行状态估计，但其没有考虑系统偏差带来的影响，容易导致估计性能差，甚至不如单个传感器估计效果明显等问题，文献[16]提出一种ASUKF的联合估计算法，对系统偏差和目标状态进行很好的联合估计。

本文将MCUKF算法引入到传感网中，并以距离和角度作为传感节点的观测量，提出一种基于MCUKF的目标状态和系统偏差联合估计算法（ASMCUKF）。在考虑系统偏差和重尾非高斯噪声的情况下，其利用MCC对非高斯噪声进行鲁棒性处理，并通过状态向量扩维的方法来估计系统偏差，提高了对目标状态估计的性能。根据核宽度取值不同，将ASMCUKF算法与几种典型的联合卡尔曼滤波算法进行性能对比，最后给出仿真结果和分析。

# 1 互相关熵

定义随机变量 $X$ 和 $Y$ 之间的互相关熵表示为

$$
V _ { \sigma } ( X , Y ) = E [ \kappa _ { \sigma } ( X - Y ) ]
$$

其中： $E$ 表示期望算子， $\kappa _ { \sigma } ( \cdot )$ 表示核函数， $\sigma > 0$ 为核宽度，通常选用的核函数为高斯核函数：

$$
\kappa _ { \sigma } ( x - y ) = G _ { \sigma } ( x - y ) = \frac { 1 } { \sqrt { 2 \pi } \sigma } \mathrm { e x p } ( - \frac { ( x - y ) ^ { 2 } } { 2 \sigma ^ { 2 } } )
$$

假设随机变量 $X$ 和 $Y$ 的联合分布函数表示为 $F _ { _ { X Y } } ( x , y )$ ，则互相关熵表示为

$$
V _ { \sigma } ( X , Y ) = \int G _ { \sigma } ( x - y ) d F _ { _ { X Y } } ( x , y )
$$

针对传感网络实际应用中得到的数据量有限，联合分布$F _ { X Y }$ 函数未知的情况，可通过有限样本平均估计量来估计互相

关熵：

$$
\hat { V _ { \sigma } } ( X , Y ) = \frac { 1 } { M } \sum _ { i = 1 } ^ { M } G _ { \sigma } ( e _ { i } )
$$

其中： $e _ { i } = x _ { i } - y _ { i } ~ , ~ \{ ( x _ { i } , y _ { i } ) \} _ { i = 1 } ^ { M }$ ，为联合分布函数 $F _ { X Y }$ 的 $M$ 个采样点。

# 2 MCUKF目标状态估计算法

MCUKF算法采用基于MCC的非线性回归方法重新构建观测信息，增强了UKF对重尾噪声的鲁棒性，文章将该算法应用于传感网对目标的状态估计中，从而解决了传感网中重尾非高斯噪声影响的问题。

# 2.1MCUKF 算法描述

定义非线性离散时间系统模型为

$$
\displaystyle x ( k + 1 ) = f ( k , x ( k ) ) + q ( k )
$$

$$
y ( k { + } 1 ) = h ( x ( k { + } 1 ) ) + r ( k { + } 1 )
$$

其中： $x ( k + 1 )$ 为目标的状态向量， $y ( k + 1 )$ 为传感网络的观测向量， $f ( \cdot )$ 和 $h ( \cdot )$ 分别表示系统和观测的非线性函数，并且假设它们是连续可微的， $\boldsymbol { q } ( \boldsymbol { k } )$ 为过程白噪声，其协方差矩阵为 $Q ( k )$ ，$r ( k + 1 )$ 为观测白噪声，其协方差矩阵为 $R ( k + 1 )$ □

MCUKF滤波器具体推导如下[15];

首先，根据UT变换获得一组sigma点集

$$
\begin{array} { l } { { \mathcal { X } ^ { 0 } ( k \mid k ) = \hat { x } ( k \mid k ) } } \\ { { \mathcal { X } ^ { i } ( k \mid k ) = \hat { x } ( k \mid k ) + \left( \sqrt { ( n + \lambda ) P ( k \mid k ) } \right) _ { i } , i = 1 \sim n } } \\ { { \mathcal { X } ^ { i } ( k \mid k ) = \hat { x } ( k \mid k ) - \left( \sqrt { ( n + \lambda ) P ( k \mid k ) } \right) _ { i - n } , i = n + 1 \sim 2 n } } \end{array}
$$

其中： $\left( { \sqrt { ( n + \lambda ) P ( k \mid k ) } } \right) _ { i }$ 表示矩阵方阵的第 $\mathbf { \chi } _ { i }$ 列，λ=α²(n+ε)-n，α是采样点的分布函数控制参数，一般为$1 0 ^ { - 4 } < \alpha \leq 1$ ， $\boldsymbol { \varepsilon }$ 为待选参数，通常设置为 $3 - n$ 。

然后根据系统方程形成 $2 n + 1$ 个 sigma点集

$$
\displaystyle \chi ^ { ( i ) } ( k + 1 | k ) = f { \Big ( } k , \chi ^ { i } ( k | k ) { \Big ) } , i = 0 \sim 2 n
$$

则系统状态量的一步预测及协方差矩阵为

$$
\hat { X } ( k + 1 | k ) = \sum _ { i = 0 } ^ { 2 n } \omega _ { m } ^ { i } \chi ^ { ( i ) } ( k + 1 | k )
$$

$$
\begin{array} { c } { { P ( k + 1 \vert k ) = \displaystyle \sum _ { i = 0 } ^ { 2 n } \{ \omega _ { c } ^ { i } [ \hat { X } ( k + 1 \vert k ) - \chi ^ { ( i ) } ( k + 1 \vert k ) ] \times } }  \\ { { \lbrack \hat { X } ( k + 1 \vert k ) - \chi ^ { ( i ) } ( k + 1 \vert k ) ] ^ { \mathrm { T } } \} + Q ( k ) } } \end{array}
$$

其中：采样点对应的权值为

$$
\begin{array} { l } { \omega _ { m } ^ { 0 } = \lambda / ( n + \lambda ) } \\ { \omega _ { c } ^ { 0 } = \lambda / ( n + \lambda ) + ( 1 + \alpha ^ { 2 } + \beta ) } \\ { \omega _ { m } ^ { i } = \omega _ { c } ^ { i } = \cfrac { 1 } { 2 ( n + \lambda ) } , i = 1 \sim 2 n } \end{array}
$$

$\beta$ 为非负的权系数,在高斯情况下, $\scriptstyle { \beta = 2 }$ 性能最优,然后根据上一步预测值,产生新的sigma点集

$$
\begin{array} { r l } & { \chi ^ { 0 } ( k { + } 1 \left. k \right) { = } \hat { x } ( k { + } 1 \left. k \right) } \\ & { \chi ^ { i } ( k { + } 1 \left. k \right) { = } \hat { x } ( k { + } 1 \left. k \right) { + } \left( \sqrt { \left( n { + } \lambda \right) P ( k { + } 1 \left. k \right) } \right) _ { i } { , } i { = } 1 { - } n } \\ & { \chi ^ { i } ( k { + } 1 \left. k \right) { = } \hat { x } ( k { + } 1 \left. k \right) { - } \left( \sqrt { \left( n { + } \lambda \right) P ( k { + } 1 \left. k \right) } \right) _ { i { - } n } { , } i { = } n { + } 1 { - } 2 n } \end{array}
$$

将预测的新 sigma 点集代入观测方程，得到相应的观测sigma点集

$$
Z ^ { i } ( k + 1 \vert k ) = h ( \chi ^ { i } ( k + 1 \vert k ) ) , i = 1 \sim 2 n
$$

将式(5)(6)等式结合式(9)(10)重新得到以下的非线性模型：

$$
{ \left[ \begin{array} { l } { { \hat { x } } ( k + 1 | k ) } \\ { y ( k + 1 ) } \end{array} \right] } = { \left[ \begin{array} { c } { x ( k + 1 ) } \\ { h ( k + 1 , x ( k + 1 ) ) } \end{array} \right] } + { \left[ \begin{array} { l } { \eta ( x ( k + 1 ) ) } \\ { r ( k + 1 ) } \end{array} \right] }
$$

对等式(10)对应的协方差矩阵 $P ( k + 1 | k )$ 和 $R ( k + 1 )$ 的联合矩阵 $\psi ( k + 1 )$ 进行Cholesky分解

$$
\scriptstyle \psi ( k + 1 ) = { \left[ \begin{array} { l l } { P ( k + 1 \mid k ) } & { 0 } \\ { 0 } & { R ( k + 1 ) } \end{array} \right] } = T ( k + 1 ) T ^ { T } ( k + 1 )
$$

对式(15)两边左乘 $T ^ { \cdot 1 } ( k + 1 )$ ，得到如下等式：

$$
D ( k + 1 ) = g ( x ( k + 1 ) ) + \pmb { \mathscr { e } } ( k + 1 )
$$

其中：

$$
\begin{array} { r l } & { D ( k + 1 ) = T ^ { - 1 } ( k + 1 ) \left[ \begin{array} { c } { \hat { x } ( k + 1 | k ) } \\ { y ( k + 1 ) } \end{array} \right] } \\ & { g ( x ( k + 1 ) ) = T ^ { - 1 } ( k + 1 ) \left[ \begin{array} { c } { x ( k + 1 ) } \\ { h ( x ( k + 1 ) ) } \end{array} \right] } \\ & { e ( k + 1 ) = T ^ { - 1 } ( k + 1 ) \left[ \begin{array} { c } { \eta ( x ( k + 1 ) ) } \\ { r ( k + 1 ) } \end{array} \right] } \end{array}
$$

$e ( k + 1 )$ 中第 $i$ 行的元素 $e _ { i } ( k + 1 )$ 为

$$
e _ { i } ( k + 1 ) = d _ { i } ( k + 1 ) - g _ { i } ( X ( k + 1 ) )
$$

定义基于互相关熵的开销函数为

$$
J ( k + 1 ) = \sum _ { i = 1 } ^ { n + m } G _ { \sigma } ( d _ { i } ( k + 1 ) - g _ { i } ( X ( k + 1 ) ) )
$$

其中： $\begin{array} { r l } { d _ { i } ( \cdot ) \cdot } & { { } g _ { i } ( \cdot ) } \end{array}$ 分别为向量 $D ( \cdot )$ 和 $g ( \cdot )$ 的第 $i$ 个元素， $m + n$ 表示向量 $D ( \cdot )$ 的维数。

基于互相关熵的性质，当函数 $J ( \cdot )$ 最大时可以得到状态的最优估计，得到修改后的协方差为

$$
\tilde { \psi } ( k + 1 ) = T ( k + 1 ) C ^ { - 1 } ( k + 1 ) T ^ { T } ( k + 1 ) { = } \mathrm { d i a g } ( \tilde { \psi } _ { x } ( k + 1 ) , \tilde { \psi } _ { y } ( k + 1 ) )
$$

其中：

$$
C ( k + 1 ) = d i a g ( G _ { \sigma } ( e _ { 1 } ( k + 1 ) , \cdots , G _ { \sigma } ( e _ { n + m } ( k + 1 ) ) ) )
$$

在实际中真实的状态是未知的，设 $\eta ( \cdot ) = 0$ ，即式(15)中X(k+1)=x(k+1|k)，则有

$$
\tilde { \psi } _ { x } ( k + 1 ) = P ( k + 1 | k )
$$

修改后的观测协方差为

$$
\tilde { R } ( k + 1 ) = \tilde { \psi } _ { _ { y } } ( k + 1 )
$$

则系统观测的先验均值和协方差为

$$
\hat { y } ( k { + } 1 | k ) = \sum _ { i = 0 } ^ { 2 n } \omega _ { m } ^ { i } Z ^ { i } ( k { + } 1 | k )
$$

$$
P _ { y _ { k + 1 } y _ { k + 1 } } = \sum _ { i = 0 } ^ { 2 n } \omega _ { c } ^ { i } \Big [ Z ^ { i } ( k + 1 | k ) - \hat { y } ( k + 1 | k ) \Big ] *
$$

$$
\left[ Z ^ { i } ( k + 1 \vert k ) - \hat { y } ( k + 1 \vert k ) \right] ^ { T } + \tilde { R } ( k + 1 )
$$

互协方差矩阵和卡尔曼增益矩阵为

$$
P _ { x _ { k + 1 } y _ { k + 1 } } =
$$

$$
{ \sum _ { i = 0 } ^ { 2 n } \omega _ { c } ^ { i } \Big [ \chi ^ { i } ( k + 1 | k ) - \hat { x } ( k + 1 | k ) \Big ] * \Big [ Z ^ { i } ( k + 1 | k ) - \hat { y } ( k + 1 | k ) \Big ] ^ { T } }
$$

$$
K ( k + 1 ) = P _ { x _ { k + 1 } y _ { k + 1 } } P _ { y _ { k + 1 } y _ { k + 1 } } ^ { - 1 }
$$

最后，计算状态更新和协方差更新

$$
{ \hat { x } } ( k + 1 \left| k + 1 \right) = { \hat { x } } ( k + 1 \left| k \right) + K ( k + 1 ) { \Big [ } y ( k + 1 ) - { \hat { y } } ( k + 1 \left| k \right) { \Big ] }
$$

$$
P ( k + 1 | k + 1 ) = P ( k + 1 | k ) - K ( k + 1 ) P _ { y _ { k + 1 } y _ { k + 1 } } K ^ { T } ( k + 1 )
$$

# 3 ASMCUKF目标状态估计算法

ASMCUKF算法将系统偏差作为状态向量中的分量，利用MCUKF滤波器实现目标状态和系统偏差的联合估计，在重尾非高斯观测噪声情况下，解决了多传感器系统偏差对通信目标状态估计性能影响的问题。

# 3.1系统描述

空天地一体化传感网络中，部署 $L$ 个传感器对目标状态进行估计，传感器的坐标为 $( x _ { 0 i } , y _ { 0 i } , z _ { 0 i } )$ 。假设移动通信目标第 $\mathbf { k }$ 时刻的位置和速度为 $( x ( k ) , y ( k ) , z ( k ) ) \setminus ( \dot { x } ( k ) , \dot { y } ( k ) , \dot { z } ( k ) )$ ，传感器的观测量为 $( d _ { i } ( k ) , \theta _ { i } ( k ) , \varphi _ { i } ( k ) ) \ , \ L$ 个传感器的距离偏差、水平偏向角偏差、俯仰角偏差为 $\boldsymbol { x } _ { \Delta } ( \boldsymbol { k } ) = ( \Delta d _ { i } , \Delta \theta _ { i } , \Delta \varphi _ { i } ) ^ { T }$ ，其中$i { = } I , 2 , . . . , L$ 。则定义 $k$ 时刻目标状态向量为

$$
\begin{array} { r } { \boldsymbol { x } _ { \scriptscriptstyle r } ( \boldsymbol { k } ) = ( \boldsymbol { x } ( \boldsymbol { k } ) , \dot { \boldsymbol { x } } ( \boldsymbol { k } ) , \boldsymbol { y } ( \boldsymbol { k } ) , \dot { \boldsymbol { y } } ( \boldsymbol { k } ) , z ( \boldsymbol { k } ) , \dot { z } ( \boldsymbol { k } ) ) ^ { T } } \end{array}
$$

假设目标做匀速直线运动，系统的状态将由目标状态和系统偏差的联合组成，则扩维后的状态方程为

$$
\pmb { \chi } ( \pmb { k } + 1 ) = \pmb { F } \cdot \pmb { \chi } ( \pmb { k } ) + \pmb { G } \cdot \pmb { w } ( \pmb { k } )
$$

其中：

$$
\pmb { X } ( k ) = [ \pmb { X } _ { r } ( k ) ^ { T } , \pmb { X } _ { \Delta } ( k ) ^ { T } ] ^ { T }
$$

$$
W ( k ) = [ q _ { 1 } , q _ { 2 } , q _ { 3 } ] ^ { T }
$$

$$
F = d i a g ( F _ { r } , I ) , G = d i a g ( G _ { r } , O )
$$

$$
F _ { r } = \left[ \begin{array} { l l l l l l } { 1 } & { T } & { 0 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { 1 } & { 0 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 1 } & { T } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 0 } & { 1 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 0 } & { 0 } & { 1 } & { T } \\ { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 1 } \end{array} \right] , \mathcal { Q } _ { r } = \left[ \begin{array} { l l l } { \frac { T ^ { 2 } } { 2 } } & { 0 } & { 0 } \\ { T } & { 0 } & { 0 } \\ { 0 } & { \frac { T ^ { 2 } } { 2 } } & { 0 } \\ { 0 } & { T } & { 0 } \\ { 0 } & { 0 } & { \frac { T ^ { 2 } } { 2 } } \\ { 0 } & { 0 } & { T } \end{array} \right]
$$

其中 $\boldsymbol { { \cal I } }$ 为单位阵。

系统的观测方程定义为

$$
Z ( k ) = h ( x ( k ) ) + \Delta e _ { i } ( k ) + \cal V ( k )
$$

其中：

$$
\begin{array} { r l } & { \qquad h ( x ( k ) ) { = } [ d _ { i } ( k ) , \theta _ { i } ( k ) , \varphi _ { i } ( k ) ] { = } } \\ & { \left[ \begin{array} { c } { \sqrt { \left( x ( k ) - x _ { 0 i } \right) ^ { 2 } + \left( y ( k ) - y _ { 0 i } \right) ^ { 2 } + \left( z ( k ) - z _ { 0 i } \right) ^ { 2 } } } \\ { \arctan \left( \displaystyle \frac { y ( k ) - y _ { 0 i } } { x ( k ) - x _ { 0 i } } \right) } \\ { \arctan \left( \displaystyle \frac { z ( k ) - z _ { 0 } } { \sqrt { \left( x ( k ) - x _ { 0 i } \right) ^ { 2 } + \left( y ( k ) - y _ { 0 i } \right) ^ { 2 } + \left( z ( k ) - z _ { 0 i } \right) ^ { 2 } } } \right) } \end{array} \right] } \end{array}
$$

其中 $\Delta e _ { i } ( k ) = ( \Delta d _ { i } , \Delta \theta _ { i } , \Delta \varphi _ { i } ) ^ { T }$ 表示第 $i$ 传感器 $k$ 时刻观测时对应的系统偏差。

# 3.2ASMCUKF算法描述

该算法是以MCUKF算法为基础，根据式(33)状态方程和式(37)观测方程来配准系统偏差，并改善重尾非高斯噪声对目标状态估计的影响。具体算法步骤如下：

a)选择合适的核宽度 $\sigma$ ，设置初始的状态值 ${ \hat { x } } ( 0 | 0 )$ 和协方差矩阵 $P ( 0 | 0 )$ ，时刻 $k = 1$ ：

b)根据式(7)计算sigma点，并通过扩维后的状态转移矩阵$F$ 计算出sigma点集的一步预测;

$$
\scriptstyle \chi ^ { ( i ) } ( k + 1 | k ) = F \cdot \chi ^ { i } ( k | k ) , i = 0 \sim 2 n
$$

c)通过式(9)(10)得到扩维后状态向量的一步预测${ \hat { x } } ( k + 1 | k )$ 及协方差矩阵 $P ( k + 1 | k )$ ；

$$
P ( k + 1 | k ) = \sum _ { i = 0 } ^ { 2 n } \omega _ { c } ^ { i } \Big [ \hat { x } ( k + 1 | k ) - \chi ^ { ( i ) } ( k + 1 | k ) \Big ]
$$

$$
\ast \Big [ \hat { X } ( k + 1 \vert k ) - \chi ^ { ( i ) } ( k + 1 \vert k ) \Big ] ^ { T } + G \cdot Q ( k ) \cdot G ^ { T }
$$

d)利用式(13)(14)产生新的 sigma点集和对应的带有系统偏差的观测值；

e)通过式(15)\~(25)得到修改后的观测协方差矩阵R(k +1)，并用式(18)计算观测的先验均值y(k+1k)和协方差Pyy；

f)用式(30)(31)得到对系统偏差进行配准的状态估计和协方差；

g)当 $k$ 等于预先设定时间步长时，算法结束，否则 $k { = } k { + } l$ ，返回步骤b)。

# 4 仿真分析

# 4.1仿真环境

本仿真采用3.1节的系统来对目标的状态进行估计，并以RMSD以及TARMSD为基准进行性能比较，具体表述形式如下：

$$
\begin{array} { c } { { R M S D ( k ) = \{ \displaystyle \frac { 1 } { M } \sum _ { m = 1 } ^ { M } [ ( x ( k ) - \hat { x } ( k \mid k ) ) ^ { 2 } + } }  \\ { { ( y ( k ) - \hat { y } ( k \mid k ) ) ^ { 2 } + ( z ( k ) - \hat { z } ( k \mid k ) ) ^ { 2 } ] \} ^ { \frac { 1 } { 2 } } } } \\ { { k = 1 , . . . , K } } \end{array}
$$

$$
T A R M S D = \frac { 1 } { K } { \sum _ { k = 1 } ^ { K } } R M S D ( k )
$$

其中 $\scriptstyle : M = I O O$ 表示蒙特卡罗实验的总次数， $K = 5 0 0$ 为每次蒙特卡罗实验中的整个时间步长。

目标在传感区域内做匀速直线运动[17]，运动轨迹为

$$
\left\{ \begin{array} { l l } { x ( k ) = 6 0 0 0 + 5 0 k } \\ { y ( k ) = 5 0 0 0 0 - 1 0 k } \\ { z ( k ) = 1 0 0 0 + 8 k } \end{array} \right.
$$

在传感区域内部署四个传感器，其坐标和对应的系统偏差分别为（距离单位为 ${ \mathrm { m } } ,$ 角度单位为rad)

$$
A ( 0 , 4 0 0 0 0 , 0 ) , B ( 4 0 0 0 0 , 4 0 0 0 0 , 0 )
$$

$$
C ( 0 , 6 0 0 0 0 , 0 ) , D ( 4 0 0 0 0 , 6 0 0 0 0 , 0 )
$$

$$
\Delta d _ { \scriptscriptstyle 1 } = 2 0 0 0 , \Delta d _ { \scriptscriptstyle 2 } = 1 5 0 0 , \Delta d _ { \scriptscriptstyle 3 } = 1 5 0 0 , \Delta d _ { \scriptscriptstyle 4 } = 2 0 0 0
$$

$$
\Delta \theta _ { 1 } = 0 . 0 0 8 7 , \Delta \theta _ { 2 } = 0 . 0 0 2 5 , \Delta \theta _ { 3 } = 0 . 0 0 7 0 , \Delta \theta _ { 4 } = 0 . 0 0 7 8
$$

$$
\Delta \varphi _ { 1 } = 0 . 0 0 8 7 , \Delta \varphi _ { 2 } = 0 . 0 0 2 5 , \Delta \varphi _ { 3 } = 0 . 0 0 7 0 , \Delta \varphi _ { 4 } = 0 . 0 0 7 8
$$

观测精度均为

$$
\begin{array} { c } { { \delta _ { d 1 } = \delta _ { d 2 } = \delta _ { d 3 } = \delta _ { d 4 } = 1 0 0 m , } } \\ { { \delta _ { \theta 1 } = \delta _ { \theta 2 } = \delta _ { \theta 3 } = \delta _ { \theta 4 } = 0 . 5 ^ { \circ } , } } \\ { { \delta _ { \varphi 1 } = \delta _ { \varphi 2 } = \delta _ { \varphi 3 } = \delta _ { \varphi 4 } = 0 . 5 ^ { \circ } } } \end{array}
$$

设实验中目标状态向量如式(34)所示，初始真实状态为(位置单位 $\mathrm { ~ m ~ }$ 速度单位 $\mathrm { m / s }$ ）

$$
\boldsymbol { x } ( 0 | 0 ) = ( 6 0 0 0 , 5 0 , 5 0 0 0 0 , - 1 0 , 1 0 0 0 , 8 , 0 , 0 , 0 ) ^ { T }
$$

初始状态估计值和协方差矩阵为

$$
\begin{array} { l } { { \hat { x } ( 0 | 0 ) = ( 6 2 5 0 , 5 0 , 5 0 5 0 0 , - 1 0 , 1 2 5 0 , 8 , 5 0 0 , 0 . 0 0 1 , 0 . 0 0 1 ) ^ { T } } } \\ { { P ( 0 | 0 ) = d i a g ( [ 1 0 0 , 2 , 1 0 0 , 2 , 1 0 0 , 2 , 1 0 ^ { 6 } , 6 \times 1 0 ^ { - 5 } , 6 \times 1 0 ^ { - 5 } ] , } } \end{array}
$$

过程噪声为

$$
q _ { 1 } \sim N ( 0 , 1 0 m ^ { 2 } ) \quad q _ { 2 } \sim N ( 0 , 1 0 m ^ { 2 } ) \quad q _ { 3 } \sim N ( 0 , 1 0 m ^ { 2 } )
$$

观测的非高斯噪声为

$$
\begin{array} { c } { \gamma _ { d } \sim 0 . 8 N ( 0 , ( 1 0 ^ { 2 } m ) ^ { 2 } ) + 0 . 2 N ( 0 , ( 1 0 ^ { 3 } m ) ^ { 2 } ) } \\ { \gamma _ { \theta } \sim 0 . 8 N ( 0 , ( ( 0 . 5 \pi / 1 8 0 ) r a d ) ^ { 2 } ) + 0 . 2 N ( 0 , ( ( 5 \pi / 1 8 0 ) r a d ) ^ { 2 } ) } \\ { \gamma _ { \varphi } \sim 0 . 8 N ( 0 , ( ( 0 . 5 \pi / 1 8 0 ) r a d ) ^ { 2 } ) + 0 . 2 N ( 0 , ( ( 5 \pi / 1 8 0 ) r a d ) ^ { 2 } ) } \end{array}
$$

# 4.2仿真结果

系统观测目标时，在受到重尾非高斯噪声的影响下，对本文算法ASMCUK与ASUKF[16和ASEKF[I7]性能进行了比较。

图1为通信目标在传感网中移动时各种滤波器的估计轨迹。在处理基于非线性方程的观测量时，ASUKF和ASMCUK显然要比ASEKF估计更加精确，在处理非高斯的观测噪声时，ASMCUK算法要比ASUKF具有更好的鲁棒性。显而易见，由于初始的估计与真实的状态具有一定的偏差，所以估计逐渐逼近真实值。

![](images/b0b4aedc50a8fe56af9727b6c37fcc974a8552f3d7ccbdde44b73e3742795213.jpg)  
图1各种滤波器对目标的轨迹估计

图2描述了传感网络中通信目标在不同滤波器下的RMSD。随着迭代次数的增加，各种滤波器的RMSD呈减小趋势，但由于观测受到重尾的非高斯噪声影响,所以RMSD曲线出现明显波动。在处理基于非线性方程的观测量时，由于ASUKF类型滤波器利用无迹变换（UT）在估计点附近确定采样点，用这些采样点表示的高斯密度去近似表示状态的概率密度函数，因此表现出比ASEKF 滤波器更好的性能。在处理非高斯的观测噪声时，由于互相关熵的强鲁棒性，ASMCUKF在所有的滤波器中RMSD最小，如表1所示，使用适中的核宽度时，ASMCUKF明显优于ASUKF。特别 $\scriptstyle \sigma = 2$ 时，ASMCUKF表现出最小的TARMSD，核宽度非常大时，ASMCUKF的性能与ASUKF基本相同。

![](images/d6552ef010e71d64b1cb17cf36d1249b3e609fadaa63c6bae77a0e75c00380ee.jpg)  
图2非高斯噪声情况下各种滤波器的RMSD

表1非高斯噪声下不同滤波器的TARMSD  

<html><body><table><tr><td>滤波器</td><td>TARMSD/m</td></tr><tr><td>ASEKF</td><td>379.3074</td></tr><tr><td>ASUKF</td><td>356.2390</td></tr><tr><td>ASMCUKF(σ=2)</td><td>316.1145</td></tr><tr><td>ASMCUKF(σ=3)</td><td>324.9229</td></tr><tr><td>ASMCUKF(σ=5)</td><td>339.7223</td></tr><tr><td>ASMCUKF(o=10)</td><td>351.1527</td></tr><tr><td>ASMCUKF(σ=20)</td><td>354.8902</td></tr></table></body></html>

图3描述了多传感器目标跟踪时传感器个数以及各种联合估计算法对目标状态估计的影响。由图3可以看出，当其他参数相同时，随着传感器数量增加，RMSD逐渐减小，各种联合算法均能有效减小系统偏差的影响，ASMCUKF比ASEKF和ASUKF具有更小RMSD，特别 $\scriptstyle \sigma = 2$ 时，ASMCUKF在多传感观测中，具有最好的估计性能。

# 5 结束语

文章主要解决传感网络中当观测噪声服从重尾的非高斯分布时，多传感器对通信目标的状态估计问题，以及对目标状态估计时，由于系统偏差的影响，估计效果差甚至不如单个传感器估计的问题，提出了一种基于MCUKF的目标状态和系统偏差联合估计算法（ASMCUKF）。ASMCUKF与ASEKF和

ASUKF进行相比，新算法表现出了对重尾非高斯噪声的强鲁棒性。仿真结果表明，在重尾的非高斯噪声的影响下，较大的核宽度（ $\scriptstyle \sigma = 2 0$ ）时，ASMCUKF将表现出与ASUKF类似的性能，较小的核宽度（ $\scriptstyle { \sigma = 2 }$ ）时，可以实现比ASEKF和ASUKF更好的性能;并且随着传感器的增多，估计性能也能得到有效的改善。

![](images/3f169a9338bc9325bcd3e83b3bfb4f4935551f271658d6530f043a0441a85e54.jpg)  
图3多传感器时目标估计误差

# 参考文献：

[1]Solanki S,Kohli J.Wireless sensor network: a survey[J].Far East Journal of Electronics & Communications,2016: 767-776.   
[2]Kumar M M,Udaya M D.A survey on sensor networks [J] IEEE Communications Magazine,2002,40 (8): 102-114.   
[3]Gante A D, Siller M.A survey of hybrid schemes for location estimation in wireless sensor networks ☆ [J].Procedia Technology,2013,7(4):377-383.   
[4]．Masazade E,Fardad M,Varshney P K.Sparsity-promoting extended kalman filtering for target tracking in wireless sensor networks [J].IEEE Signal Processing Letters,2012,19 (12): 845-848.   
[5]Guo J, Zhang H, Sun Y,et al. Square-root unscented Kalman filtering-based localization and tracking in the Internet ofThings [J].Personal& Ubiquitous Computing,2014,18 (4): 987-996.   
[6]Wang X,Fu M, Zhang H. Target tracking in wireless sensor networks based on the combination of KF and MLE using distance measurements [J]. IEEE Trans on Mobile Computing,2012,11 (4): 567-576.   
[7]Zhou T,Liang P,Cheng Y. The target tracking of wireless sensor network using an improved unscented particle filter [C]// Proc of International Conference on Mechatronics,Electronic,Industrial and Control Engineering. 2015.17-20.   
[8]Vukovi,Najdan,Miljkovi, et al.Robust sequential learning of feedforward neural networks in the presence of heavy-tailed noise [M].[S.1.] Elsevier Science Ltd.2015,63:31-47   
[9]Principe JC. Information theoretic learning:renyi's entropy and kernel perspectives [M].[S.1.] : Springer Publishing Company Incorporated,2010: 1385-1392   
[10]Liu W,Pokharel PP,Principe JC.Correntropy: properties and applications in non-gaussian signal processing [J]. IEEE Trans on Signal Processing, 2007,55(11): 5286-5298.   
[11] Luan Z,Qu H, Zhao J,etal. Correntropy induced joint power and admission control algorithm for dense small cell network [J].IET Communications, 2016,10 (16): 2154-2161.   
[12] Liu X,Qu H, Zhao J,et al. State space maximum correntropy filter [J]. Signal Processing,2016,130:152-158.   
[13] Peng S,Chen B, Sun L,et al. Constrained maximum correntropy adaptive filtering [J]. Signal Processing,2017,140:116-126.   
[14] Chen L,Qu H,Zhao J,et al. Eficient and robust deep learning with Correntropy-induced loss function [J]. Neural Computing and Applications, 2016,27(4):1019-1031.   
[15] Liu X,Qu H, Zhao J,et al.Maximum correntropy unscented Kalman filter for spacecraft relative state estimation [J]. Sensors,2016,16 (9): 1530.   
[16]宋强，何友，杨俭.基于UKF的目标状态与系统偏差的联合估计算法 [J]．弹箭与制导学报,2007,27(3):311-313.   
[17]宋强，何友，董云龙．一种目标状态与系统偏差的联合估计算法[J]. 弹箭与制导学报,2007,27(4):312-315.