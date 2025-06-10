# 一种基于动态加权PPI网络的关键蛋白质识别算法

杨书新，鲁纪华，汤达荣(江西理工大学信息工程学院，江西 赣州 341000)

摘要：与静态PPI网络相比，动态PPI网络更能体现蛋白质之间相互作用的真实情况，并有效降低PPI网络中的假阴性。现有的关键蛋白质预测方法主要应用在静态PPI网络，忽视了PPI网络的动态特性。为有效预测关键蛋白质，利用基因表达数据提取蛋白质的动态信息，再结合静态PPI网络构建动态PPI网络，然后引入GO 术语对网络加权，并基于动态加权PPI 网络提出一种新的预测方法-DWE。该方法以蛋白质在动态网络中的动态加权边之和与蛋白质在动态网络中出现的次数的比值衡量蛋白质在网络中的关键性。实验结果表明动态加权PPI网络有助于提高关键蛋白质的预测精度，且DWE方法优于其他几种关键蛋白质预测方法。

关键词：动态网络；关键蛋白质；GO术语；动态加权PPI网络 中图分类号：TP301 doi: 10.3969/j.issn.1001-3695.2017.08.0707

# Novel algorithm prediction of essential proteins based on dynamic weighted PPI network

Yang Shuxin, Lu Jihua, Tang Darong (school ofinformation engineering Jiangxi University ofScience and Technology,Ganzhou 3410o0,China)

Abstract: Compared with static PPI network,the dynamic PPInetworkcan reflect thereal situation of interactions among proteins andeffectivelyreducethe falsenegation inPPInetwork.Mostof he existing methodsarebasedonstaticPPInetwork, which neglectthe inherentdynamicsofPPInetwork.Toeffectivelypredicttheessentialproteins,thedynamicinformationof proteins is extracted from gene expression dataand integrate with staticPPInetwork toconstruct dynamicPPI,then weighting theinteraction between proteins based on GO term similarityand introduce anew method named DWE.This method ssesses theimportant ofoneprotein through theratioofthesumofthedynamic weighted edgeconnecting this proteinand thenumber of temporal networks thatcontain this protein Theresult shows that dynamic weighted PPInetwork helpto improve the prediction accuracy of essential proteins and DWE outperforms other methods.

Key Words: dynamic network; essential proteins; GO terms; dynamic weighted PPI network

# 0 引言

关键蛋白质是生命活动的必需蛋白质。识别关键蛋白质不仅有助于理解生命活动，而且对药物设计及疾病治疗[具有重要意义。生物研究者通过生物实验预测关键蛋白质，但花费高、效率低，且只适用于部分生物体。因此，研究人员提出一系列的计算方法识别关键蛋白质，以提高预测效率，降低成本。

现有的关键蛋白质预测方法依据PPI网络的不同可以分为基于静态PPI网络的关键蛋白质识别和基于动态PPI网络的关键蛋白质识别。基于静态PPI网络的预测方法主要有度中心性(Degree Centrality,DC)[2]、介数中心性(Betweenness Centrality,BC)[3]、接近度中心性(ClosenessCentrality,CC)[4]、子图中心性(SubgraghCentrality,SC)[5]、特征向量中心性(EigenvectorCentrality,EC)[6]、信息中心性(Information Centrality,IC)[7]、局部平均联通性(Local Average Connectivity,LAC)[8]和邻居中心性(NeighborCentrality,NC)[9]等基于拓扑特征的预测方法，及融合生物信息的关键蛋白质预测方法，如 $\mathrm { P e C } ^ { [ 1 0 ] }$ 、DWC[11]、UDoNC[12]等。同时，2016年，催鑫等[13]在已有的CPPK 模型中引入LDA 模型预测关键蛋白质。同年，杨莉萍等[14]结合边聚集系数和随机游走模型进行关键蛋白质识别。目前，对动态PPI网络的研究主要集中在蛋白质复合物和功能模块的挖掘，针对关键蛋白质检测方法的研究还不多。2015年，Xiao等[15]依据时间序列模型构建动态PPI网络，并将六种现有的关键蛋白质预测方法应用于动态PPI网络。与基于静态PPI网络的预测方法相比，该方法考虑了PPI网络的动态特性对预测结果的影响，但忽略了PPI网络中假阳性和假阴性的影响。为降低假阳性和假阴性的影响，本文在考虑PPI网络动态特性的基础上结合蛋白质功能相似性构建一种新的动态加权PPI网络（dynamicweightedPPI network,DWPPIN）,并依据DWPPIN提出一种新的关键蛋白质检测方法-DWE。

# 1基于动态加权PPI网络的关键蛋白质预测

基于动态加权PPI网络进行关键蛋白质预测的方法的具体流程：首先以静态PPI网络为框架，利用基因表达谱构建动态PPI 网络；其次对动态PPI网络中的每个瞬态网络，利用边聚集系数和蛋白质之间的功能相似性衡量边的可靠性；最后计算动态加权网络中蛋白质的得分，得到蛋白质的重要程度。

# 1.1 动态PPI网络构建

动态PPI网络可通过蛋白质的共表达特性构建。蛋白质的共表达是指两个蛋白质之间存在相互作用，且在同一时刻的都属于活性蛋白质。表达水平超过阈值的蛋白质被认为是活性蛋白质。由于不同的蛋白质具有不同的表达水平，因此蛋白质的活性状态不能采用统一的阈值判断[16]。本文采用蛋白质的平均表达水平作为各自的阈值，即当蛋白质在某一时刻的表达值高于其平均表达水平时，本文认为蛋白质处于活性状态。

![](images/f0f7fddea91860a32f73653f7efe6f5d66bdea43402d78ab92ee9d7bd017ebfc.jpg)  
图1动态网络构建过程

基因表达谱包含各个蛋白质3个代谢周期(每个周期12个时刻，共36个时刻）的表达水平数据。每个蛋白质的平均表达水平可表示为：

$$
\ \overline { { T } } _ { \nu } = \frac { \displaystyle \sum _ { i = 1 } ^ { 3 6 } t _ { \nu } ( i ) } { \displaystyle 3 6 }
$$

式（1）中， $t _ { \nu } ( i )$ 表达蛋白质 $\mathbf { \sigma } _ { \nu }$ 在 $i$ 时刻的表达值， $\overline { { T } } _ { \nu }$ 表示蛋白质 $\nu$ 的平均表达值。

计算出各个蛋白质的平均表达水平后，依据基因表达谱判断各个蛋白质在每个时刻的活性状态，以确定各时刻PPI网络中的相互作用是否存在。对于静态PPI网络中的相互作用$e ( \nu , u )$ ，如果 $\mathbf { \Delta } _ { \nu , u }$ 在 $i$ 时刻同时处于活性状态，那么 $\mathbf { \Delta } _ { \nu , u }$ 之间在$i$ 时刻出存在相互作用。可用公式表示为：

$$
e _ { i } ( \nu , u ) = \left\{ \begin{array} { c c } { 1 } & { t _ { \nu } ( i ) > \overline { { T } } _ { \nu } , t _ { u } ( i ) > \overline { { T } } _ { u } } \\ { 0 } & { o t h e r w i s e } \end{array} \right.
$$

式（2）中， $e _ { i } ( \nu , u ) = 1$ 表示相互作用 $e ( \nu , u )$ 在 $i$ 时刻存在。反之，则不存在。

上述方法构建的动态PPI网络包含36个不同的瞬态PPI网络，每个瞬态网络都包含不同的活性蛋白质和不同的相互作用。动态PPI网络可形式化定义如下：

定义1动态 PPI 网络 $D G = \{ \ G _ { 1 } , G _ { 2 } , \cdots , G _ { i } , \cdots , G _ { l } \}$ ， $\mathbf { \xi } _ { l }$ 表示时刻数， $G _ { i } = \{ \ V _ { i } , E _ { i } \}$ 是 $i$ 时刻的 PPI网络， $V _ { i } = \{ \nu _ { i 1 } , \nu _ { i 2 } , \cdots , \nu _ { i n } \}$ （20表示 $i$ 时刻处于活性状态的蛋白质集合， $E _ { i } = \{ e _ { i 1 } , e _ { i 2 } , \cdots , e _ { i m } \}$ 表示;时刻蛋白质相互作用的集合，m=|Eil。

以图1为例说明动态网络的构建过程。静态PPI网络中A、B 之间存在相互作用，且在1、3、4三个时刻同时处于活性状态。那么A、B之间的相互作用仅在1、3、4三个时刻出现。静态PPI网络中E、C之间存在相互作用，但在任一时刻，E、C 的活性状态都不相同。因此，在任一时刻，E、C之间的相互作用都不存在。尽管F、D在时刻7同时处于活性状态，然而在静态PPI网络中，它们之间不存在相互作用，因此F、D之间在该时刻不存在相互作用。

# 1.2 动态PPI网络加权

基于对关键蛋白质的分析，关键蛋白质倾向于成簇出现，且蛋白质的关键性与相互作用的可靠程度之间关系密切。本文同时考虑蛋白质拓扑特征和生物特征，采用GO语义相似性和边聚集系数衡量相互作用的可靠程度。

相互作用的可靠程度可通过蛋白质之间的功能相似性评价。两个蛋白质之间的功能相似性越高，其相互作用越可靠。GO术语是对基因的功能进行注释的结构化自然语言。研究证实，两个蛋白质之间的共有GO术语越多，它们的生物功能越相似。因此，蛋白质间相互作用的可靠性可通过它们在GO术语上的功能相似性进行评价。

令GO（v）表示蛋白质 $\nu$ 的GO注释信息组成的集合，GO_sim表示两个蛋白质的GO语义相似性。那么两个蛋白质 $\nu$ 和 $\boldsymbol { u }$ 之间的功能相似性计算公式如下：

$$
G O \_ s i m ( \nu , u ) = \frac { \left| G O ( \nu ) \cap G O ( u ) \right| } { \left| G O ( \nu ) \cup G O ( u ) \right| }
$$

式（3）中， $G O ( \nu ) \cap G O ( u )$ 表示 $\mathbf { \Phi } _ { \nu }$ 和 $\boldsymbol { u }$ 的共同 GO 术语集合。 $G O ( \nu ) \cup G O ( u )$ 表示存在于 $\nu$ 或 $u$ 的 GO 术语集合。

关键蛋白质不仅与相互作用的可靠性有关，而且往往成簇出现。边聚集系数作为PPI网络的一个重要拓扑特征，它不仅可以描述蛋白质之间相互作用的重要程度，还可评估蛋白质之间属于同一簇的概率，且能够较好的识别PPI网络中的关键蛋白质[17]。边聚集系数的计算公式如下：

$$
E C C ( \ \nu , u ) { = } \frac { \tan ( \nu , u ) } { \operatorname* { m i n } ( d ( \nu ) - 1 , d ( u ) - 1 ) }
$$

式（4）中， $\tan ( \nu , u )$ 表示 $\nu$ 和 $\boldsymbol { u }$ 共同参与构成的三角形个数， $d ( \nu )$ 和 $\boldsymbol { d } ( \boldsymbol { u } )$ 分别表示 $\nu$ 和 $\boldsymbol { u }$ 的邻居节点个数。

定义2动态加权PPI网络 $D W G { = } \{ G _ { 1 } , G _ { 2 } , \cdots , G _ { l } \}$ ， $\mathbf { \xi } _ { l }$ 表示时刻数， $G _ { i } = \{ V _ { i } , E _ { i } , W E _ { i } \}$ 是 $i$ 时刻的加权PPI 网络，

Vi={vil,vi2,,Vin}表示时刻处于活性状态的蛋白质集合，E={ei,ei,,eim}表示i时刻蛋白质相互作用集合，$W E _ { i } = \{ w e _ { i 1 } , w e _ { i 2 } , \cdots , w e _ { i m } \}$ 是相互作用权值的集合， $m = \left| E _ { i } \right|$ 。

动态PPI网络中个瞬态网络的相互作用权值计算公式如下：

$$
\scriptstyle W E ( \nu , u ) = G O \_ s i m ( \nu , u ) + E C C ( \nu , u )
$$

# 1.3关键蛋白质识别

蛋白质的关键性可根据蛋白质在2.2节构建的动态加权PPI网络中的评分判定。由于瞬态网络中的活性蛋白质都各不相同，所以在计算蛋白质的评分时会将其在动态加权PPI网络中出现的次数考虑在内。蛋白质的评分DWE为各个瞬态网络中该蛋白质与其邻居节点之间权值之和与其在动态网络中出现的次数之比。其计算公式为：

$$
D W E ( \nu ) = \frac { \displaystyle \sum _ { i = 1 } ^ { 3 6 } \sum _ { u \in N _ { i } ( \nu ) } W E _ { i } ( \nu , u ) } { f r e ( \nu ) }
$$

式(6)中， $N _ { i } ( \nu )$ 表示在 $i$ 时刻对应的瞬态网络中节点 $\mathbf { \Phi } _ { \nu }$ 的邻居节点集合； $W E _ { i } ( \nu , u )$ 表示在 $i$ 时刻对应的瞬态网络节点 $\nu$ （20和节点 $\boldsymbol { u }$ 之间边的权值； $f r e ( \nu )$ 表示动态网络中包含节点 $\mathbf { \Phi } _ { \nu }$ 的瞬态网络的个数，即节点 $\nu$ 在动态网络中出现的次数。

本文根据每个蛋白质的DWE值，将所有的蛋白质按照DWE值进行降序排列。DWE值越高的蛋白质，排名越靠前，越可能是关键蛋白质。将排序后的前K个蛋白质输出作为DWE方法识别出的候选关键蛋白质。K是动态加权PPI网络中包含关键蛋白质的个数。DWE方法的伪代码描述如下：

DWE算法：

Input:Static PPI network $G$ ，gene expression data GED，GO   
annotation GOA， $\boldsymbol { \kappa }$   
Output:the top $\boldsymbol { \kappa }$ Ranked proteins by DwE value in descent   
order   
Construct dynamic PPI network $\pmb { { \cal D } } G = \{ G _ { 1 } , G _ { 2 } , \cdots , G _ { l } \}$ based on GED   
according to the formula(1）and (2)   
For each $G _ { i } \in D G$ do For each $e _ { i j } ( \nu , u ) \in E _ { i }$ do compute ${ \mathsf { G } } 0 _ { - } { \mathsf { s i m } } ( \nu , u )$ （204号 compute ECC $( \nu , u )$ （204号 compute WE(v,u) end for for each $\nu _ { i j } \in V _ { i }$ do compute the sum of WE(vij,u) end for   
end for   
a）Compute the DwE of all nodes by formula（6)   
b）Return the top $\boldsymbol { \kappa }$ ranked proteins according to their DWE   
values

DWE算法第1）步根据蛋白质的基因表达数据和静态PPI网络构建动态PPI网络。第2）步实现动态PPI网络的加权，对于动态PPI网络中的任意瞬态网络 $\mathbf { G } _ { \mathrm { i } }$ ，算法循环的以式（5）计算每条边的权值，然后对瞬态网络 $\mathbf { G } _ { \mathrm { i } }$ 中任意节点 $\nu _ { i j }$ ，计算与节点 $\nu _ { i j }$ 相连边的权值之和。算法第3）步对 PPI网络中的所有蛋白质评估其在动态加权PPI网络中的DWE评分，并按照DWE 值将蛋白质进行降序排列。在4）步返回排序后的前 $K$ 个蛋白质作为DWE算法预测的 $K$ 个关键蛋白质。

# 2 实验结果与分析

# 2.1实验数据

由于酵母蛋白质相互作用网络和关键蛋白质数据都具有较高的完整性和可靠性，因此本文选择酵母蛋白质相关数据集验证本文方法的有效性。实验用到的相关数据描述如下：

（1）酵母蛋白质交互作用网络（Protein-ProteinInteraction,PPI）来自DIP数据库[18]。其中包含5093个蛋白质，24743个相互作用。

（2）标准关键蛋白质数据可通过整合MIPS[19]、 $\mathrm { S G D } ^ { [ 2 0 ] }$ 、DEG[21]、 $\mathrm { S G D P } ^ { [ 2 2 ] } 4$ 个数据库的数据得到，包含关键蛋白质1285个，其中出现在酵母PPI网络中的仅有1167个。

（3）酵母基因表达谱来源于NCBI 基因表达综合网站[23]编号为GSE3431的数据。它以一个 $m \times n$ 矩阵的形式存储，矩阵中的每一个值表示某个蛋白质在某个时刻的表达水平。基因表达谱包含6740个基因产物的表达水平数据。其中有4981个基因产物出现在酵母PPI网络中。

（4）酵母蛋白质GO 注释信息下载自基因本体数据库[24]（2016年12月24日的版本)，它主要包括三部分：生物过程、分子组件和分子功能。

# 2.2实验结果

为验证动态加权PPI网络的效果和评估DWE方法的识别效率，本文设计了两组实验进行对比分析。其中一组使用三种不同的PPI网络数据，包括静态PPI网络（StaticPPINetwork,SPPIN）、Xiao 等[13]构建的动态PPI网络（Active PPINetwork,APPIN）及本文构建的动态加权PPI 网络（Dynamic WeightedPPINetwork,DWPPIN)。并在每种PPI网络上，分别应用中心性方法预测关键蛋白质。另一组编程实现现有的七种经典的中心性检测方法、融合了生物信息的PeC、WDC和UDoNC方法然后与本文提出的DWE方法进行对比。并采用“排序-筛选”法、“刀切法”及敏感度、特异性等指标评估实验结果。

# 2.2.1PPI网络对检测效果的影响

由于DC、LAC、NC分别从邻居个数、邻居的重要性和边的重要性三个不同的角度衡量蛋白质在网络中的重要性，因此选择这三种方法作为关键蛋白质检测方法。图2给出了这三种方法在不同PPI网络中识别关键蛋白质的数量。从图2可看出，与静态PPI网络相比，动态加权网络的检测结果明显提高了很多。当选取前600个作为候选关键蛋白质时，动态加权PPI网络的正确率提高了 $20 \%$ 。尽管在候选关键蛋白质较少时，动态加权PPI网络和动态PPI网络的识别正确率非常接近，然而随着候选关键蛋白质的增加，动态加权PPI网络的识别正确率逐渐优于动态PPI网络。因此动态加权PPI网络能够提高关键蛋

白质的检测效果。

![](images/075acc09289885d9c56e87317a42278639aaf4cde446c7de21354a620f674da9.jpg)  
图2在三种不同的PPI网络中三种方法识别关键蛋白质的数量

# 2.2.2“排序-筛选"法分析

“排序-筛选”法的具体做法是：对所选的测度参数，计算蛋白质网络中每个蛋白质节点的相应测度值，并将蛋白质节点按照测度值由大到小进行排序，选取排序靠前的蛋白质作为预测的关键蛋白质，然后与已知的关键蛋白质数据集比对，从而得到该测度参数识别出的关键蛋白质数目。本实验中，分别选取排序在前 $1 \%$ 、 $5 \%$ 、 $10 \%$ 、 $1 5 \%$ ， $20 \%$ 、 $2 5 \%$ 的蛋白质作为候选关键蛋白质。

七种经典的中心性方法中的NC识别效果最好。与NC相比，DWE的识别正确率分别提高了 $2 8 . 1 2 \%$ 、 $1 5 . 7 2 \%$ 、 $1 5 . 9 0 \%$ 、$1 1 . 5 2 \% . 8 . 4 1 \% . 6 . 6 2 \%$ 。同时，与融合生物信息的识别方法PeC、WDC、UDoNC相比，当候选关键蛋白质不超过 $2 5 \%$ 时，DWE仍然有比较明显的优势。虽然随着候选关键蛋白质的增加，DWE的优势逐渐减弱，但当选取 $2 5 \%$ 的蛋白质为候选关键蛋白质时，DWE的识别正确率仍然有所提高。这时，DWE的识别正确率提高了 $8 . 2 1 \%$ 、 $2 . 4 7 \%$ 、 $1 . 2 2 \%$ 相比于PeC、WDC、UDoNC。

![](images/b39e29620a2bc95af7349cb1596c85080ad3f7f1dfafab1a93e8cc48e5836446.jpg)  
图3为11种方法的关键蛋白质识别结果。从图3可看出，  
图311种方法在不同样本容量中预测的关键蛋白质数目

# 2.2.3其他评估方法分析

为更细致的评估DWE方法的性能，本文引入“刀切法"对比分析DWE方法与其他十种中心性测度方法的预测结果。图

4通过刀切法列出了各方法关键蛋白质的预测结果。图4中，X轴表示累计候选关键蛋白质数量，Y轴表示累计真实关键蛋白质数量。刀切法曲线下方的面积用于对比各个方法的性能，面积越大说明识别率越高。从图4可看出，与DC、BC、EC、SC、IC、NC和CC相比，DWE具有最好的识别率。从图4（a)看出,DWE曲线明显位于PeC曲线的上方，这说明DWE的识别率优于PeC。同时从图4(b)看出，DWE的识别率高于WDC和UDoNC两种方法。

600 600 ODWE O-DWE 0006 AIC √EC 年★ 8 ★ 500 中C —UDoNC 品 品 X PeC 0o 日日日日 集 \*WDC 女 本本女 中   
400 8 1 本本 日 □□ aesrest 品 X 欢 X ★ 长本   
300 中 300 8 又 长年 X ★★ X   
200 200   
100 中电书中 100 有 茶 0 0 0 200 400 600 800 1000 1200 0 200 400 600 800 1000 1200 the number of top ranked proteins the number of top ranked proteins (a) (b)

此外，本文采用敏感度（SN）、特异性（SP）、F测度（F-measure）、正确率（ACC）、阳性预测值（PPV）和阴性预测值（NPV）这六个评估指标对各个方法的性能进行评估。其计算公式如下：

$$
S N = { \frac { T P } { T P + F N } }
$$

$$
S P = { \frac { T N } { T N + F P } }
$$

$$
P P V = { \frac { T P } { T P + F P } }
$$

$$
N P V = \frac { T N } { T N + F N }
$$

$$
F = \frac { 2 \times S N \times P P V } { S N + P P V }
$$

$$
A C C = { \frac { T P + T N } { T P + T N + F P + F N } }
$$

式（7）-（12）中， $\scriptstyle { \overline { { T P } } }$ 表示被预测为关键蛋白质的关键蛋白质数量； $\mathbf { \Omega } _ { T N }$ 表示被预测非关键蛋白质的非关键蛋白质数量;$F P$ 表示被预测为关键蛋白质的非关键蛋白质数量； $F N$ 表示被预测非关键蛋白质的关键蛋白质数量。

根据已知关键蛋白质的数量，本文选取排序后的前1167个蛋白质作为预测关键蛋白质，并根据已知的关键蛋白质计算各方法六项指标的值。表1为DWE与其他十种方法的六项指标的值。从表1可看出，DWE的任一指标都高于其他几种方法。

# 3 结束语

本文利用PPI网络的动态特性，结合蛋白质的生物特征构建动态加权PPI网络，并提出一种名为DWE的关键蛋白质识别方法。该方法降低了数据噪声对实验结果的影响，提高了PPI网络的可靠性。与其他方法相比，DWE方法提高了识别准确率，

能够识别出更多的关键蛋白质。

表1DWE和其他几种中心性测度的各个评价指标的比较  

<html><body><table><tr><td>Methods</td><td>SN</td><td>SP</td><td>PPV</td><td>NPV</td><td>F-measure</td><td>ACC</td></tr><tr><td>DC</td><td>0.4002</td><td>0.8217</td><td>0.4002</td><td>0.8217</td><td>0.4002</td><td>0.7251</td></tr><tr><td>IC</td><td>0.4002</td><td>0.8217</td><td>0.4002</td><td>0.8217</td><td>0.4002</td><td>0.7251</td></tr><tr><td>EC</td><td>0.3676</td><td>0.8120</td><td>0.3676</td><td>0.8120</td><td>0.3676</td><td>0.7102</td></tr><tr><td>SC</td><td>0.3676</td><td>0.8120</td><td>0.3676</td><td>0.8120</td><td>0.3676</td><td>0.7102</td></tr><tr><td>BC</td><td>0.3505</td><td></td><td>0.8069 0.3505 0.8069</td><td></td><td>0.3505</td><td>0.7023</td></tr><tr><td>CC</td><td></td><td></td><td>0.3548 0.8082 0.3548 0.8082</td><td></td><td>0.3548</td><td>0.7043</td></tr><tr><td>NC</td><td>0.4353</td><td></td><td>0.8321 0.4353</td><td>0.8321</td><td>0.4353</td><td>0.7412</td></tr><tr><td>PeC</td><td>0.4362</td><td>0.8324</td><td>0.4362</td><td>0.8324</td><td>0.4362</td><td>0.7416</td></tr><tr><td>WDC</td><td>0.4619</td><td>0.8400</td><td>0.4619</td><td>0.8400</td><td>0.4619</td><td>0.7534</td></tr><tr><td>UDoNC</td><td>0.4653</td><td>0.8411</td><td>0.4653</td><td>0.8411</td><td>0.4653</td><td>0.7550</td></tr><tr><td>DWE</td><td>0.4685</td><td>0.8441</td><td>0.4685</td><td>0.8441</td><td>0.4685</td><td>0.7594</td></tr></table></body></html>

# 参考文献：

[1]Jeong H, Oltvai ZN,Barabasi A-L.Prediction of protein essentiality based on genomic data[J].ComPlexUs,2002,1(1):19-28.   
[2]JeongH,Mason SP,Barabasi A-L,etal.Lethality and centrality in protein networks[J].Nature,2001,411 (6833):41-42.   
[3]Joy MP,Brock A,Ingber D E,et al. High-betweenness proteins in the yeast protein interaction network [J].BioMed Research International, 2oo5,2005 (2):96-103.   
[4]Wuchty S,Stadler P F.Centers of complex networks [J].Journal of Theoretical Biology,2003,223(1):45-53.   
[5]Estrada E,Rodriguez-Velazquez JA. Subgraph centrality in complex networks[J].Physical Review E,2005,71(5):056103.   
[6]Bonacich P.Power and centrality:A family of measures [J].American journal of sociology,1987:1170-1182.   
[7]Stephenson K, Zelen M.Rethinking centrality: Methods and examples [J]. Social Networks,1989,11(1): 1-37.   
[8]LiMin,Wang Jianxin,Chen Xiang,et al.Alocal average connectivity-based method for identifying essential proteins from the network level [J]. Computational Biology& Chemistry,2011,35 (3):143-50.   
[9]Wang Jian,Li Min,Wang Huan,et al.Identification of Essential Proteins Based on Edge Clustering Coefficient [J].IEEE//ACM Transactions on Computational Biology& Bioinformatics,2012,9(4):1070.   
[10]Li Min,Zhang Hanhui,Wang Jianxin,et al.A new essential protein discovery method based on the integration of protein-protein interaction and gene expression data [J].BMC Systems Biology,2012,6(1): : 15.   
[11] Tang Xiwei,Wang Jianxin,Zhong Jiancheng,et al.Predicting Essential Proteins Based on Weighted Degree Centrality [J].IEEE//ACM Trans Comput Biol Bioinform,2014,11 (2): 407-18.   
[12] Peng Wei,Wang Jianxin, Cheng Yingjiao,et al.UDoNC:An Algorithm for Identifying Essential Proteins Based on Protein Domains and ProteinProtein Interaction Networks[J].IEEE//ACM Trans Comput Biol Bioinform, 2015,12 (2): 276-88.   
[13] Xiao Qianghua,Wang Jianxin,Peng Xiaoqing,et al. Identifying essential proteins from active PPI networks constructed with dynamic gene expression [J].BMC Genomics,2015,16 (3):1.   
[14]崔鑫，邵明玉．结合主题特征和互作用网络拓扑特性的关键蛋白质识 别[J].计算机应用与软件,2016,33(08):283-288.   
[15]杨莉萍，路松峰，黄钰．一种基于随机游走模型的关键蛋白质预测方法 [J].华中农业大学学报,2016,35(6):86-91.   
[16] Wang Jianxin,Peng Xiaoqing,Li Min,et al. Construction and application of dynamic protein interaction network based on time course gene expression data [J].Proteomics,2013,13 (2):301-312.   
[17] Wang Huan,Li Min,Wang Jianxin,et al.A New Method for Identifying Essential Proteins Based on Edge Clustering Coefficient [J].Lecture Notes in Computer Science,2011,6674: 87-98.   
[18] Xenarios I, Salwinski L,Duan XJ,et al.DIP,the Database of Interacting Proteins:a research tool for studying cellular networks of protein interactions [J].Nucleic Acids Research,2002,30(1):303.   
[19] Hw M,D F,Kf M,et al. MIPS: analysis and annotation of proteins from whole genomes [J].Nucleic Acids Research,2006,34(2): 169-72.   
[20] Cherry JM,Adler C,Ball C,et al. SGD: Saccharomyces Genome Database [J].Nucleic Acids Research,1998,26(1): 73-9.   
[21] Zhang Ren,Lin Yan.DEG 5.0,a database of essential genes in both prokaryotes and eukaryotes [J].Nucleic Acids Research,2oo9,37(Database issue): D455-D458.   
[22] Saccharomyces Genome Deletion Project [EB/OL]. http://www-sequence. stanford.edu/group/yeast_deletion_project.   
[23] Tu BP,Kudlicki A,Rowicka M,et al. Logic of the yeast metabolic cycle: temporal compartmentalization of cellular processes [J]. Science,2005,310 (5751): 1152-1158.   
[24] Consortium TG O.Gene Ontology Consortium: going forward [J].Nucleic Acids Research,2015,43 (Database issue):1049-56.