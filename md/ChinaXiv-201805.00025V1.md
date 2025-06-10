# 基于DBSCAN-GRNN-LSSVR 算法的WLAN 异构终端定位方法\*

张勇，范恒，王昱洁(合肥工业大学计算机与信息学院，合肥 230009)

摘要：针对 WLAN 室内定位系统中异构终端(指纹库终端和测试终端)引起的定位偏差过大的问题，提出一种基于DBSCAN-GRNN-LSSVR 算法的解决方案。该文使用最小二乘支持向量回归机(LSSVR)构建指纹库终端接收信号强度(RSS)和物理坐标位置的映射关系模型；列出校准点处异构终端采集的RSS值，得到散点图；用基于密度聚类方法剔除边界点和噪声点；用广义回归神经网络构建异构终端RSS 的映射函数；通过LSSVR模型定位测试点的位置。实验结果表明，与只用LSSVR算法相比，测试终端定位精度提高 $1 8 - 4 0 \%$ ，有效解决了定位偏差过大的问题。关键词：WLAN室内定位；异构终端；最小二乘支持向量回归机；具有噪声的基于密度聚类；广义回归神经网络中图分类号：TN915.05doi:10.3969/j.issn.1001-3695.2017.10.1007

# WLAN heterogeneous terminal location method based on DBSCAN-GRNN-LSSVR algorithm

Zhang Yong, Fan Heng, Wang Yujie (School ofComputer&Information,Hefei UniversityofTechnology,Hefei23ooo9,China)

Abstract:Aiming attheexcessive location errorcaused byheterogeneous terminal (fingerprint database terminal and test terminal) in WLAN indoor localization system,a solution based on DBSCAN-GRNN-LSSVR algorithm is proposed.In this paper,the least square support vector regression (LSSVR)algorithm is employed to build the mapping relationship model betwen thereceived signal trength(RSS)ofngerprintdatabaseterminaland physicalcoordinate locations.Thescaterplot isobtainedthroughlistingtheRSSvaluescollctedbythefingerprintdatabaseterminalandthetestterminalatthecalibration point.The boundary pointsand noise points are eliminated bydensity-based spatial clustering.Generalized regresion neural network(GRNN) is usedto constructthe heterogeneous terminal mapping functionof the RSS.The LSSVR model is used to determine the locationofthe testpoint.Provedbyexperiment,compared withLSSVRalgorithm,usingthe proposed DBSCANGRNN-LSSVR algorithm to calibrate the heterogeneous terminal,test terminal positioning accuracy increased by $1 8 - 4 0 \%$ ， which effectively solves the problem of excessve localization deviation caused by heterogeneous terminals.

Key Words:WLAN indoor localization; heterogeneous terminal; LSSVR; DBSCAN; GRNN

# 0 引言

近年来，随着机场、仓库、展厅、商场、矿井、医院等对位置服务需求的增加，促进了定位技术的发展。在室内由于建筑物遮挡信号，全球定位系统（global position system，GPS）不能满足人们对于室内定位精度的要求。目前室内定位技术有：红外线室内定位、RFID室内定位、ZigBee室内定位、超声波室内定位、超宽带室内定位、蓝牙室内定位、WLAN室内定位等。相比而言，WLAN室内定位I因其成本低、定位速度快、无须额外硬件设备、适用范围广、总体精度高等特点得到了广泛的关注。

WLAN室内定位主要方法有近似感知法、几何测量法、场景分析法等。场景分析法包括位置指纹法和信号传播模型法。

位置指纹法由于算法灵活、定位相对准确，成为研究的热门方向。

但是，基于WLAN的室内定位在实际应用中由于异构终端的问题，在同一点不同的终端接收到各个接入点(access point,AP)的接收信号强度(received signal strength，RSS)有差异，导致定位偏差过大。因此针对 WLAN 室内定位异构终端导致的定位偏差过大的问题已展开了很多研究工作。

秦泗明[2提出一种基于BP神经网络的接收信号强度指示(Received Signal StrengthIndication,RSSI)校准方法，该方法建立BP神经网络模型，将测试终端的RSS值转换成指纹库终端的RSS值。Dong[3提出将指纹向量的分量进行成对相减的方法，实验结果表明此方法可以将基于最近邻(nearest neighbor，NN)的定位精度提升 $20 \%$ ，将基于贝叶斯推理(Bayesian inference,BI)

的定位精度提升 $12 \%$ 。Kim等人[4通过观察指纹库终端和测试终端RSS的差异，提出了使用RSS峰值的位置进行定位的方法，该方法认为指纹库终端和测试终端RSS最强的位置是同一位置，以此解决终端差异给RSS带来的影响。Kjaergaard[5等人提出一种双曲线校准法，该方法将RSS向量的分量进行成对相除，消除线性变换中斜率项的影响，实验表明该方法能够减小异构终端的影响。赵聪[提出一种余弦相似度法，该方法的关键思想是采用余弦相似度算法计算测试终端RSS和指纹库终端RSS的相似性，相似程度越大，两个参考点就越匹配，一定程度上减小了因异构终端导致的定位偏差过大。Hossain 等人[7]提出一种RSS差值的（SSD）方法，假设原先的RSS向量是N维的，该方法是将RSS其他分量减去锚点的分量，这样新的RSS 向量就只包含N-1个RSS 差异值。谷洋等人[8提出一种设备自适应的无线信号特征提取与定位方法（SSDR)，该方法是对RSS向量进行处理，消除斜率和截距的影响后再进行定位，相比于直接基于信号强度和欧氏距离计算准则的定位方法其定位精度提高 $10 \small { \sim } 2 0 \%$ 。但是以上异构终端定位方法的定位精度提高不显著。

为保证WLAN室内定位的精度，解决因为异构终端导致的定位偏差过大的问题，提出一种基于DBSCAN-GRNN-LSSVR算法的解决方案。在指纹点处用指纹库终端获取RSS值，用最小二乘回归向量机[9-1l](least square support vector regression,LSSVR)建立指纹库终端采集的RSS与其对应位置坐标的非线性关系，建立LSSVR映射关系模型；用测试终端采集校准点上的RSS值，得到指纹库终端和测试终端RSS的散点图，用具有噪声的基于密度聚类方法[12\~14](density-based spatialclusteringofapplicationwithnoise，DBSCAN)对数据点进行聚类分析，标记出核心点、边界点和噪声点，剔除边界点和噪声点；采用广义回归神经网络[15-16](generalized regression neuralnetwork，GRNN)拟合DBSCAN算法处理后的指纹库终端RSS和测试终端RSS，得到指纹库终端RSS和测试终端RSS的映射函数，将测试终端RSS转换成指纹库终端RSS；用LSSVR模型定位测试点的位置。实验结果表明，与只用LSSVR算法对比，提出的DBSCAN-GRNN-LSSVR 算法使OPPO手机、智器平板1、智器平板2定位效果分别提高 $40 \%$ ， $20 \%$ 、 $1 8 \%$ ，较好的解决了异构终端引起的定位偏差过大的问题。

# 1 DBSCAN-GRNN-LSSVR 算法

位置指纹法分两个阶段：离线阶段和在线阶段。离线阶段主要是指纹库终端采集指纹点的RSS，并建立RSS与指纹点位置的对应关系数据库；在线阶段，测试终端在场景中通过接收到的AP信号强度，采用算法进行处理，估计出该点位置坐标，从而完成在线定位。本文提出的DBSCAN-GRNN-LSSVR异构终端定位算法是基于位置指纹法的。

本文的DBSCAN-GRNN-LSSVR定位系统框图如图1所示。

离线阶段 定位特征数据库 LSSVR训练RSS测试终端采集校准构建LSSVR点处RSS模型√绘制测试测试终端 终端和指 DBSCAN GRNN剔除边界 已构建的采集测试 纹库终端 拟合散  
在线阶段 点RSS RSS的散 点、噪声 点图 LSSVR模型点图测试终端映射函数定位结果

离线阶段，在场景中选定指纹点，指纹库终端采集各个指纹点上的RSS值，将定位特征和相应的指纹点位置作为输入样本对，完成LSSVR 的学习训练过程，建立定位特征和物理位置的LSSVR 映射关系模型。在线阶段，测试终端采集校准点上的RSS 值，得到测试终端和指纹库终端RSS 的散点图，用DBSCAN剔除边界点和噪声点，用GRNN拟合DBSCAN算法处理后的指纹库终端RSS 和测试终端RSS，得到指纹库终端RSS 和测试终端RSS的映射函数，选定测试点，将测试点的测试终端RSS值转换成指纹库终端的RSS值，输入构建好的LSSVR模型中，估计出测试点的实际位置。

# 1.1具有噪声的基于密度聚类方法

DBSCAN是一种典型的基于密度聚类的方法，其核心思想是用一个点的邻域内的邻近点数衡量该点所在空间的密度。它可以找出形状不规则的簇，且聚类时不需事先知道簇的个数。DBSCAN主要定义如下：

假设数据集合 $X = \{ x _ { 1 } , x _ { 2 } , \cdots , x _ { n } \}$ ，将Eps(半径)和MinPts(给定的整数)分别记为 $\varepsilon$ 和 $\mathbf { \delta M }$ 。

定义1 Eps 邻域。设 $x \in X$ ，称

$$
N _ { \varepsilon } \left( x \right) = \left\{ y \in X | d \left( y , x \right) \leq \varepsilon \right\}
$$

为 $x$ 的 Eps 邻域。 ${ \boldsymbol { x } } \in N _ { \varepsilon } \left( { \boldsymbol { x } } \right)$ ， $d \left( y , x \right)$ 表示 $x$ 中的两个对象$y$ 和 $x$ 之间的距离。

定义2核心点、边界点和噪声点。设 $x \in X$ ，如果 $x$ 的Eps邻域内的对象数目满足 $\left. N _ { \varepsilon } \left( x \right) \right. \geq \mathbf { M }$ ，则称 $x$ 为 $x$ 的核心点。记由$x$ 中所有核心点构成的集合为 $X _ { c }$ ；不是核心点，但落在某个核心点的Eps邻域内的对象称为边界点；由任意一个核心点对象开始，从该对象密度可达的所有对象构成一个簇。不属于任何簇的对象为噪声点。

定义3直接密度可达。若满足 $x \in X _ { c } , y \in N _ { \varepsilon } \left( x \right)$ ， $x , y \in X$ ，则称 $y$ 是从 $x$ 直接密度可达的。

定义4密度可达。设 $P _ { 1 } , P _ { 2 } , \cdots , P _ { n } \in X$ 。若它们满足： $P _ { i + 1 }$ 是从$P _ { i }$ 直接密度可达的， $i = 1 , 2 , \cdots , m - 1$ ，其中 $m \geq 2$ ，则称 $\boldsymbol { P _ { m } }$ 是从 $P _ { 1 }$ 密度可达的。

定义5密度相连。设 $x , y , z \in X$ ，若 $y$ 和 $z$ 均是从 $x$ 密度可达的，则称 $y$ 和 $z$ 是密度相连的，密度相连具有对称性。

当 Eps 和MinPts 给定时，DBSCAN 聚类流程如下：

a）选定任意一个未处理的数据点，判断其是否为核心点；  
b)若是，找出所有从该点密度可达的数据点，形成一个簇；

若不是，则判断是噪声点或边界点并进行标记;

c）重复以上步骤，直至所有的数据点处理完毕，得到核心点、噪声点和边界点，剔除边界点和噪声点，将核心点组成新的样本集。

设指纹库终端在校准点处的样本集为$H _ { f } = \left\{ ( S _ { f 1 } , L _ { 1 } ) , ( S _ { f 2 } , L _ { 2 } ) , \cdots , ( S _ { f i } , L _ { i } ) \right\} , S _ { f i } = \left\{ S _ { f i 1 } , S _ { f i 2 } , \cdots , S _ { f i n } \right\}$ $S _ { f i n }$ 表示指纹库终端在校准点 $i$ 接收来自于第 $n$ 个AP的RSS信号强度值， $n$ 为AP 的个数， $\pmb { L } _ { i } = \left( x _ { i } , y _ { i } \right)$ 为校准点 $i$ 的物理位置坐标。测试终端在校准点处的样本集：$H _ { c } = \left\{ ( S _ { c 1 } , L _ { 1 } ) , ( S _ { c 2 } , L _ { 2 } ) , \cdots , ( S _ { c i } , L _ { i } ) \right\}$ ， ${ { S } _ { c i } } = \left\{ { { S } _ { c i 1 } } , { { S } _ { c i 2 } } , \cdots , { { S } _ { c i n } } \right\}$ ， $S _ { c i n }$ 表示测试终端在校准点 $i$ 接收来自于第 $n$ 个AP的信号强度值。

根据 $\pmb { H } _ { f }$ 和 $\pmb { H } _ { c }$ 得到指纹库终端和测试终端的RSS散点图，用DBSCAN算法处理数据点，剔除边界点、噪声点后，指纹库终端的样本集成为 $H _ { f } ^ { \prime } = \left\{ ( S _ { f 1 } ^ { \prime } , L _ { 1 } ^ { \prime } ) , ( S _ { f 2 } ^ { \prime } , L _ { 2 } ^ { \prime } ) , \cdots , ( S _ { f m } ^ { \prime } , L _ { m } ^ { \prime } ) \right\}$ ，测试终端的样本集成为 $\pmb { H } _ { c } ^ { \prime } = \left\{ ( S _ { c 1 } ^ { \prime } , L _ { 1 } ^ { \prime } ) , ( S _ { c 2 } ^ { \prime } , L _ { 2 } ^ { \prime } ) , \cdots , ( S _ { c m } ^ { \prime } , L _ { m } ^ { \prime } ) \right\}$ ，其中 $m \leq i$ 。

# 1.2广义回归神经网络

广义回归神经网络是径向基神经网络的一种。GRNN具有很强的非线性映射能力和柔性网络结构以及高度的容错性和鲁棒性。GRNN在结构上与RBF网络较为相似。它由四层构成，如图2所示，分别为输入层、模式层、求和层和输出层。对应网络输入为： $X = \left[ x _ { 1 } , x _ { 2 } , ^ { \cdots } , x _ { n } \right] ^ { \mathrm { T } }$ □

![](images/72a0ef2f638b36aa059def3f7fe85edfee6e7f8dd1d73dcc26ded6f60bbfa64e.jpg)  
图2广义回归神经网络结构图

其原理如下：设随机变量 $x$ 和 $y$ ， $\scriptstyle { \boldsymbol { X } }$ 为 $x$ 的测试样本值。则在输入为 $\scriptstyle { \boldsymbol { X } }$ 时，GRNN模型预测值 ${ \hat { Y } } ( X )$ 为：

$$
{ \tilde { Y } } ( X ) = { \frac { \displaystyle { \sum _ { i = 1 } ^ { n } Y _ { i } \exp \left[ - { \frac { \left( X - X _ { i } \right) ^ { \operatorname { T } } \left( X - X _ { i } \right) } { 2 \sigma ^ { 2 } } } \right] } } { \displaystyle { \sum _ { i = 1 } ^ { n } \exp \left[ - { \frac { \left( X - X _ { i } \right) ^ { \operatorname { T } } \left( X - X _ { i } \right) } { 2 \sigma ^ { 2 } } } \right] } } }
$$

其中： $X _ { i }$ 和 $\mathbf { \boldsymbol { Y } } _ { i }$ 分别是 $x$ 和 $y$ 的训练样本值； $n$ 为训练样本数；$\sigma$ 为高斯函数的宽度系数，在此称为光滑因子。预测值 ${ \hat { Y } } ( X )$ 为所有训练样本值 $\pmb { Y } _ { i }$ 的加权平均，每个训练样本值 $\pmb { Y } _ { i }$ 的权重因子为相应的 $X _ { i }$ 与测试样本值 $\scriptstyle { \mathbf { \boldsymbol { X } } }$ 之间欧式距离平方的指数。GRNN人为调节的参数少，只有一个 spread 值(径向基函数的扩展速度)。所以在建立GRNN 时，只需要选择一个合适的spread 值。spread 值的大小对于网络的逼近结果影响很大，spread 的值越小，神经网络对样本数据的逼近性就越好；spread的值越大，神经网络对样本数据的逼近过程就越光滑，但与此

同时网络输出误差会增大。

构建GRNN拟合函数时，输入为测试终端在校准点处的样本集： $\pmb { H } _ { c } ^ { \prime } = \left\{ ( \pmb { S } _ { c 1 } ^ { \prime } , \pmb { L } _ { 1 } ^ { \prime } ) , ( \pmb { S } _ { c 2 } ^ { \prime } , \pmb { L } _ { 2 } ^ { \prime } ) , \cdots , ( \pmb { S } _ { c m } ^ { \prime } , \pmb { L } _ { m } ^ { \prime } ) \right\}$ ，输出为指纹库终端在校准点处的样本集： $\pmb { H } _ { f } ^ { \prime } = \left\{ ( \pmb { S } _ { f 1 } ^ { \prime } , \pmb { L } _ { 1 } ^ { \prime } ) , ( \pmb { S } _ { f 2 } ^ { \prime } , \pmb { L } _ { 2 } ^ { \prime } ) , \cdots , ( \pmb { S } _ { f m } ^ { \prime } , \pmb { L } _ { m } ^ { \prime } ) \right\}$ ，其中 $m \leq i$ 。

# 1.3 LSSVR算法

设指纹库终端在指纹点处样本集为${ \cal H } = \left\{ ( S _ { 1 } , L _ { 1 } ) , ( S _ { 2 } , L _ { 2 } ) , \cdots , ( S _ { t } , L _ { t } ) \right\}$ ， $\pmb { S } _ { t } = \left\{ S _ { t 1 } , S _ { t 2 } , \cdots , S _ { t n } \right\}$ ， $\boldsymbol { S } _ { t } \in \boldsymbol { R } , \boldsymbol { L } _ { t } \in \boldsymbol { R } ^ { \prime }$ ， $S _ { t n }$ 表示指纹库终端在指纹点 $t$ 接收来自于第 $n$ 个AP的RSS信号强度值， $n$ 为 AP 的个数， $\pmb { L } _ { t } = \left( x _ { t } , y _ { t } \right)$ 为指纹点 $t$ 的二维位置坐标。

LSSVR 通过一个非线性映射 $\pmb { \phi } \big ( \boldsymbol { S } \big ) : \pmb { R }  \pmb { R } ^ { m }$ 将 $s$ 映射到高维特征空间 $\pmb { R } ^ { m }$ ，然后在 $\pmb { R } ^ { m }$ 中构建位置坐标 $y$ 与RSSI值的最优回归函数：

$$
y = \omega ^ { \mathrm { T } } \pmb { \phi } \big ( S \big ) + b
$$

其中： $\omega$ 为权重向量， $b$ 为偏置项。

LSSVR的优化问题如下：

$$
\operatorname* { m i n } I ( \pmb { \omega } , \varepsilon ) = \frac { 1 } { 2 } \big \| \pmb { \omega } \big \| ^ { 2 } + \frac { C } { 2 } \sum _ { i = 1 } ^ { t } \pmb { \varepsilon } _ { i } ^ { 2 }
$$

s. t.

$$
y _ { i } = \omega ^ { T } \pmb { \phi } \big ( \pmb { S } \big ) + b + \varepsilon _ { \mathrm { i } }
$$

其中： $i = 1 , 2 , \cdots , t$ ， $c$ 为惩罚参数， $\varepsilon _ { i }$ 为误差。

可采用拉格朗日函数求解式(4)(5):

$$
\begin{array} { l } { \displaystyle \boldsymbol { L } ( \omega , b , \varepsilon , \alpha ) = \frac { 1 } { 2 } \| \omega \| ^ { 2 } + \frac { C } { 2 } \underset { i = 1 } { \overset { t } { \sum } } \varepsilon _ { i } ^ { 2 } - } \\ { \displaystyle \underset { i = 1 } { \overset { t } { \sum } } \alpha _ { i } \left( \omega ^ { \mathrm { T } } \bullet \phi \big ( S \big ) + b + \varepsilon _ { i } - f _ { i } \right) } \end{array}
$$

其中： $\mathbf { \alpha } \mathbf { \alpha } \mathbf { \alpha } = \left[ \alpha _ { 1 } , \alpha _ { 2 } , \cdots , \alpha _ { t } \ \right] ^ { \mathrm { T } }$ ， $\alpha _ { i }$ 是拉格朗日乘子。

本论文选用LS-SVM工具箱求解优化问题，该工具箱是用最小二乘算法来求解SVR模型中的最优化问题中的解。LSSVR使用的是参数相对少、适应能力较强的高斯核函数：

$$
K \left( S _ { m } , S _ { n } \right) = \exp \left( - \frac 1 { 2 \delta ^ { 2 } } \big \| S _ { m } - S _ { n } \big \| ^ { 2 } \right)
$$

因此得出位置坐标和RSS值的回归函数分别为

$$
x = \sum _ { i = 1 } ^ { t } \alpha _ { i } K \big ( S , S _ { i } \big ) + b
$$

$$
y = \sum _ { i = 1 } ^ { t } \alpha _ { i } ^ { \prime } K \bigl ( S , S _ { i } \bigr ) + b ^ { \prime }
$$

其中： $\alpha _ { \mathrm { i } } ^ { \prime }$ 和 $b _ { \mathrm { i } } ^ { \prime }$ 为相应求得的拉格朗日乘子和偏置。

# 2 实验结果与分析

# 2.1实验条件

为验证本文提出的DBSCAN-GRNN-LSSVR算法的有效性，实验在合肥工业大学逸夫楼6楼进行。逸夫楼6楼局部平面图如图1所示，包括办公室和走廊，一共三个区域。办公室内有桌椅、书柜等办公用品。在整个定位区域内一共布置了6个型号为DWL-2414N的AP，均安装在距离地面 $2 . 4 \mathrm { ~ m ~ }$ 的支架上。

![](images/67658180b6efecf1b9756a123ee981deb19ddff246eacdf4331683b678bc4166.jpg)  
图3WLAN室内定位实验环境

本文使用的四个终端如表1所示。

表1终端参数表  

<html><body><table><tr><td>品牌</td><td>型号</td><td>主要硬件</td><td>软件版本</td><td>数量</td></tr><tr><td>魅族</td><td>魅蓝note3</td><td>Helio P10</td><td>Flyme5.1</td><td>1</td></tr><tr><td>OPPO</td><td>OPPO A37</td><td>MT6750</td><td>ColorOS 3.0</td><td>1</td></tr><tr><td>智器</td><td>智器T30</td><td>TI OMAP4470</td><td>Android4.2</td><td>2</td></tr></table></body></html>

本次实验选取了25个指纹点（同时作为校准点）、22个测试点，分布在上图中的区域一、区域二和区域三中。指纹点在区域一、区域二和区域三中成 $3 ^ { * } 3$ 来均匀分布，测试点的位置随机选取。采集信号时，手持终端在实验区域中采样点以0.1秒间隔对各AP扫描50次，每个测试点测250组数据，数据剔除最大值最小值取平均。

定义定位误差err和平均定位误差AverErr：

$$
e r r _ { i } = \sqrt { ( x _ { i } - x _ { i } ^ { ' } ) ^ { 2 } + ( y _ { i } - y _ { i } ^ { ' } ) ^ { 2 } }
$$

$$
A \nu e r E r r = \frac { 1 } { h } \sum _ { i = 1 } ^ { h } e r r _ { i }
$$

其中： $( x _ { i } , y _ { i } )$ 是第 $i$ 个测试点的实际坐标， $( x _ { i } ^ { \prime } , y _ { i } ^ { \prime } )$ 是第 $i$ 个测试点的估计坐标， $h$ 是测试点的总数目。

# 2.2结果分析

本文用魅蓝 note3作为指纹库终端，OPPO、智器平板1、智器平板2作为测试终端，DBSCAN 算法的参数采用常用数值：MinPts设置为5，Eps设置为7。对于GRNN算法，spread的值取[0,2]之间的数，通过对比逼近均方根误差来找出最佳的spread值。

图4(a)\~(c)分别为OPPO手机、智器平板1、智器平板2和魅蓝 note3手机在全部校准点采集RSS 值的散点图。图4(d)\~(f)分别为使用DBSCAN算法处理后的散点图。

-20 -20 -20+++ ++ + 车 丰 T + + ++ E ×x + +++ + + +-50 美 8 -50 + 会 E ++++-70 4 车 +++ L 发 中 + +蓝 丰+ ++ + ++-90+-90 -80 -70 -60 -50 −40 -30 -20 −80-70 -60 −50-40 -30-20 -90 -80 -70 -60 -50 -40 -30 -20 -100OPPO RSS值/dbm 智器平板1 RSS值/dbm 智器平板2 RSS值/dbm(a) (b) (c)-20 -20 -20  
E -30 + 。 00我 +++++ 4 里 + ·· 160 + 车 · \* 中  
0 + ++ S ++ + 1 + , + +++ 车 ++  
00 # ++ ++++ +核心点 + + +核心点++ + +核心点 题-80+++ +\*+ ○噪声点 魅-80 ++‡ + ○噪声点： ：边界点 +# · 边界点 +· ： 边界点90 -904 −90 + 梅-90 -80 −70 -60 -50 −40 -30 -20 -90 -80 -70 -60 -50 −40 -30 -20 -90 -80 -70 -60 -50 -40 -30 -20 -100OPPO RSS值/dbm 智器平板1 RSS值/dbm 智器平板2 RSS值/dbm(d) (e) (f)

剔除图4(d)\~(f)中边界点和噪声点后的数据用GRNN拟合得到异构终端之间RSS关系。以智器平板1作为测试终端，采用GRNN拟合指纹库终端RSS和测试终端RSS的关系，spread参数变化时，spread值和逼近均方根误差的关系如图5所示，spread值为0.9时逼近均方根误差最小，故在拟合智器平板1和魅蓝note3RSS值的关系时，spread 选择0.9，拟合曲线如图6 所示。用相同方法得出OPPO、智器平板2的最佳拟合 spread值和拟合曲线。

以智器平板1作为测试终端时，图7为校准点个数与平均定位误差的关系图。从图7可以看出，当校准点个数达到20时，定位误差明显减小。

![](images/5aa25eafd2eb6b8130d00f06e26fb733d80850195e99ff11c9f534b042bc85c8.jpg)  
图4异构终端的RSS 散点图  
图5spread值和逼近均方根误差的关系

![](images/ed9713d2d19e2956367fd23ae7f45e4997f7fac4d184529dd13bc5b58670e6d8.jpg)  
图6GRNN拟合效果

![](images/0c1de2328c9b8a9bc28ace80de128451aebf3685a64d1a3849a2dce02f268c94.jpg)  
图7校准点个数与平均定位误差的关系

表2为采用不同的算法时测试终端平均定位误差对比，对于DBSCAN-GRNN-LSSVR算法，先采用DBSCAN算法剔除噪声点和边界点，再用GRNN算法会拟合的更精确。本算法对比LSSVR算法：OPPO手机定位效果有 $40 \%$ 的提升，智器平板1定位效果有 $20 \%$ 的提升，智器平板2定位效果有 $18 \%$ 的提升；对比SSD-LSSVR校准算法，定位效果分别有 $10 \%$ 、 $9 \%$ 、 $9 \%$ 的提升；对比GRNN-LSSVR校准算法，定位效果分别有 $21 \%$ 、$1 1 \%$ 、 $1 1 \%$ 的提升，实验结果表明DBSCAN-GRNN-LSSVR 算法校准效果更好。

表2魅蓝note3作为指纹库终端，采用不同的算法时测试终端平均  

<html><body><table><tr><td colspan="4">定位误差（单位：m)</td></tr><tr><td></td><td>魅蓝note3 OPPO</td><td>智器平板1</td><td>智器平板2</td></tr><tr><td>LSSVR</td><td>2.53 5.20</td><td>3.34</td><td>3.45</td></tr><tr><td>GRNN-LSSVR</td><td>1 3.92</td><td>3.01</td><td>3.19</td></tr><tr><td>SSD-LSSVR</td><td>1 3.44</td><td>2.93</td><td>3.12</td></tr><tr><td>DBSCAN-GRNN-LSSVR</td><td>1 3.09</td><td>2.66</td><td>2.82</td></tr></table></body></html>

图8为智器平板1作为测试终端时几种算法的定位误差累计概率分布。当定位误差在 $3 \mathrm { m }$ 以下时，DBSCAN-GRNN-LSSVR算法累计概率是 $6 3 . 6 3 \%$ ,SSD-LSSVR,GRNN-LSSVR,LSSVR算法的累计概率分别是 $5 9 . 0 9 \%$ ， $50 \%$ ， $50 \%$ ，当累计概率为 $50 \%$ 时，DBSCAN-GRNN-LSSVR，SSD-LSSVR，GRNN-LSSVR,LSSVR算法定位误差值分别为 $2 . 4 3 \mathrm { m } , 2 . 6 2 \mathrm { m } , 2 . 7 7 \mathrm { m }$ $2 . 8 9 \mathrm { { m } _ { \circ } }$ 从图8可以看出相比于其他几种算法，DBSCAN-GRNN-

![](images/79be972e2c78faf352f926561ad4d5d35153838177c592fa153f3051646afa09.jpg)  
LSSVR算法有着更好的校准效果。  
图8几种定位算法平均定位误差累计概率分布

# 3 结束语

针对WLAN室内定位因异构终端引起的定位偏差过大的问题，本文提出了一种基于DBSCAN-GRNN-LSSVR 算法的解决方案。列出测试终端和指纹库终端的RSS值，得到散点图，用DBSCAN密度聚类算法剔除噪声点和边界点，用GRNN算法拟合剔除噪声点和边界点后的散点图，得到指纹库终端RSS和测试终端RSS 的映射关系，将测试终端RSS值转换为指纹库终端RSS值，通过LSSVR模型定位测试点；通过对比实验看出，本文提出的DBSCAN-GRNN-LSSVR能有效的解决因异构终端导致的定位偏差过大的问题，效果好于LSSVR算法、GRNN-LSSVR校准算法、SSD-LSSVR校准算法。但是由于需要的校准点个数较多，因此怎样减少校准点个数是将下一步研究的方向。

# 参考文献：

[1]张明华，张申生，曹健．无线局域网中基于信号强度的室内定位[J].计算机科学,2007,34(6):68-75.  
[2]秦泗明．基于位置指纹的Wi-Fi室内定位技术研究[D].成都：电子科技大学,2013.  
[3]Dong F,Chen Y,Liu J,et al.A calibration-free localization solution forhandling signal strength variance [C]//Proc of International Conference onMobile Entity Localization and Tracking in Gps-Less Environments.[S.1.] :Springer-Verlag,2009:79-90.  
[4]Kim Y, Shin H,Chon Y,et al. Smartphone-based Wi-Fi tracking systemexploiting the RSS peak to overcome the RSS variance problem [J].Pervasive & Mobile Computing,2013,9(3): 406-420.  
[5]Kjaergaard M B,Munk C V. Hyperbolic location fingerprinting:Acalibration-free solution for handling differences in signal strength [C]//Proc of the IEEE Int'l Conf. on Pervasive Computing.[S.1.] : IEEE Press,2008:110-116.  
[6]赵聪．基于位置指纹的 WLAN 室内定位算法研究[D].哈尔滨：哈尔滨工业大学,2014.  
[7]Hossain AK M M,Jin Y,Soh W S,et al.SSD:a robust RF locationfingerprint addressing mobile devices'heterogeneity [J].IEEE Trans onMobile Computing,2013,12 (1): 65-77.  
[8]谷洋，蒋鑫龙，刘军发，等．设备自适应的无线信号特征提取与定位方[J]．软件学报,2014,25(S2):12-20.  
[9]罗清旺，师奕兵，王志刚，等．铁磁性管道物理参数反演方法研究[J].仪器仪表学报,2016,37(1):9-14.  
[10]代亮，许宏科，陈婷，等．基于MapReduce 的最小二乘支持向量机回归模型[J].计算机应用研究,2015,32(4):1060-1064.  
[11] Suykens J,Van G T,De BP,et al.Least Square Support Vector Machines[M]. Singapore: World Scientific Publishing,20o2: 71-111.  
[12]田增山，王向勇，周牧，等．基于DBSCAN子空间匹配的蜂窝网室内指纹定位算法[J]．电子与信息学报,2017,39(5):1157-1163.  
[13]冯振华，钱雪忠，赵娜娜.Greedy DBSCAN:一种针对多密度聚类的DBSCAN改进算法[J].计算机应用研究,2016,33(9):2693-2700  
[14]郭保青，朱力强，史红梅．基于快速DBSCAN 聚类的铁路异物侵限检测算法[J].仪器仪表学报,2012,33(2):241-247.  
[15]吴常铖，宋爱国，曾洪，等.基于 sEMG 和GRNN的手部输出力估计[J].仪器仪表学报,2017,38(1):97-104.  
[16]葛柳飞，李克清，戴欢．基于自适应GRNN 的无线室内定位算法[J].计算机工程,2016,42(6):81-85,90.