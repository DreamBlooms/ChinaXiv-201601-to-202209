# 基于蚁群优化与独立特征集的遥感图像实时分类算法

赵芳¹，索岩²，彭子然³

(1．新乡学院 计算机与信息工程学院，河南 新乡 453003;2.河南师范大学 新联学院，河南新乡 453000;3．中南大学信息科学与工程学院，长沙 410083)

摘要：为了提高遥感图像的实时分类准确率与效率，提出了一种基于蚁群优化算法与独立特征集的遥感图像集实时分类算法。首先，提取遥感图像的小波域特征与颜色特征，并且组成特征向量；然后，采用蚁群优化算法对特征空间进行优化，独立地选出每个分类的显著特征集，从而降低每个子特征空间的维度；最终，每个分类独立地训练一个极限学习机分类器，从而实现对遥感图像集的分类。基于公开的遥感图像数据集进行了仿真实验，结果显示本算法实现了较高的分类准确率，并且实现了较高的计算效率。

关键词：人工智能；特征提取；遥感图像；时间效率；蚁群优化算法；极限学习机 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.06.0574

Real-time classification algorithm of remote sensing images based on ant colony optimization algorithm and independent feature sets

Zhao Fang1, Suo Yan²,Peng Ziran3 (1.InstituteofComputer& Information Engineeing,Xinxiang University，Xinxiang Henan 453003,China;2.Xinlian College,Henan Normal University, Xinxiang Henan 453003,China; 3.School of Information Science& Engineering, Central South University, Changsha 410083, China)

Abstract: Inorder to improve the accuracy and eficiencyofreal time clasification ofremote sensing images,areal time classificationalgorithmof remote sensing images basedontheantcolonyoptimizationalgorithmand independent feature set is proposed.Firstly, wavelet features andcolor features ofremote sensing images are Abstract:d,andthe features form thefeaturevectors;then,theantcolonyoptimizationisadoptedtooptimize the feature space,andthe significantfeature set of each class are selected independently to reduce the dimension of each feature sub-space; lastly,an independent extreme learning machine is trained foreach classto realize theremote sensing images classification.Simulation experimental results based on the public remote sensing image dataset showthat the proposed algorithm realizes a good clasification accuracy and computational efficiency.

Key words:artificial inteligence；feature abstraction；remote sensing image；computational efficiency；antcolony optimization algorithm; extreame learning machine

# 0 引言

遥感技术是军事侦察、导弹预警、军事测绘、海洋监视与气象观测等领域的重要研究课题之一，其中通过遥感图像对地面进行探测与侦查具有巨大的研究价值[1。在矿产检测与石油勘探工程应用中，通过卫星遥感图像对地表进行初步勘探、分析地表结构已成为一个重要的技术手段[2]。此外，在机器人探索荒漠地区的工程应用中，采集遥感图像也是探测机器人的一个重要任务[3]。但是探测机器人与卫星的通信能力有限，如果将遥感图像集实时地发送至工作站，则会带来巨大的通信负担[4]。因此，在探测机器人或者卫星中实时地对遥感图像集进行预处理，不仅可以减轻通信负担，而且也有助于对地表的定位效果[5.6]。

遥感图像的细节信息丰富、特征维度高，一般采用传统的特征提取方案提取遥感图像的特征，获得的特征表达能力弱并且信息损失严重，对遥感图像后续的处理具有不利的影响[7]。文献[8]对预处理后的图像进行降维处理，提取像素的光谱维特征，并且使用卷积神经网络提取图像块的空间特征，然后将这两个提取的特征串行拼接，该方案使用使用支持向量机作为遥感图像集的分类器。该方案有效地提高了图像分类准确率，但是时间效率较低。文献[9]提出了一种基于显著特征和GVFSnake的高分辨率遥感图像道路提取方法，通过融合颜色对比度和空间统计特征计算显著性图，并以输出的显著图最大值作为GVFSnake的初始种子点。该方案同时提高了计算效率与检测精度，但是由于该方案采用了GVFsnake的种子生长算法，导致该方案仅对轮廓显著的目标具有效果。

小波特征能够提取遥感图像的细节信息[10]，本文则同时考虑了遥感图像的小波域特征与颜色特征。为了保证较低的遥感图像分类处理时间，有效地减少特征数量则是另一个重要的课题。目前，卓有成效的特征优化方案主要有蚁群优化算法[11]、粒子群优化算法[12]、遗传算法[13]等。其中蚁群优化算法取得了更好的效果，因此本文也采用蚁群优化算法对每个分类的特征集进行优化处理。分类器的时间效率也是决定遥感图像分类效率的一个重要因素，目前遥感图像分类领域中常用的分类器主要为支持向量机[14]，本文通过实验发现极限向量机的计算效率略优于支持向量机，因此本文采用极限向量机作为分类器。

综上所述，为了在遥感测量终端实现对遥感图像集的实时分类处理，应当在保证遥感图像分类准确率的情况下，有效地降低算法的计算时间。本文提出了一种基于蚁群优化算法与独立特征集的遥感图像集实时分类算法，该算法提取遥感图像的小波特征与颜色特征，采用蚁群优化算法对特征数量进行优化处理，为每个图像分类分别训练一个独立的极限学习机分类器。最终基于公开的遥感图像数据集进行了仿真实验，结果表明本算法在保证较高图像分类准确率的同时，有效地提高了分类处理的计算效率，有助于在遥感测量终端实现实时的图像预处理。

# 1 特征提取

特征提取从复杂的图像数据集中提取出一个特征向量，采用特征向量表征一个大规模的数据集，由此节约数据的存储成本与计算成本。在本文的特征提取实验中，从每个像素的窗口提取该像素的特征向量。地表遥感图像中的岩石特征采用小波变换中的纹理特征描述符表示，将小波域的统计参数作为像素的描述符。其他的地表特征则采用颜色特征描述符表示。本文的特征描述符共包括四种特征，分别为：小波域的系数特征、主颜色描述符(DCD)特征、局部颜色直方图特征与颜色统计特征。

# 1.1小波特征

首先，为输入图像的每个像素建立一个窗口，对窗口进行一级的二维小波分解处理。然后，将欧式范数分别放入LH、HL 元素各行、各列的小波系数中[15]。最终，分别计算欧式范数的平均值与方差，获得8个小波特征值。

# 1.2颜色特征

颜色特征属于低级别特征，颜色特征对于旋转、缩放等变化不敏感，遥感图像存在较多的噪声，并且许多图像存在旋转、缩放等变形，因此颜色特征可以解决这些问题。本文采用了三个颜色特征，分别为：主颜色描述符(dominantcolordescriptor.DCD)特征、局部颜色直方图与颜色统计特征。

# 1.2.1主色描述符

DCD是MPEG-7标准认可的一种颜色描述符。DCD将图像的颜色分为若干个分区，称为“粗分区”，假设同一个分区中的所有点均为相似点，分区中心是该分区中所有像素颜色的平均值，具体计算为下式：

$$
C _ { j } = \frac { \sum _ { p \in P _ { i } } p } { \sum _ { p \in P _ { i } } 1 }
$$

其中 ${ \bf \nabla } : { P } _ { i }$ 表示第 $i$ 个分区。本文在RGB颜色域提取DCD特征，假设每个像素均属于一个分区，然后将该像素的颜色值替换为其分区的中心值，由此量化了图像的颜色。对于每个像素，计算像素窗口的DCD值，将这些DCD值组成特征向量。图1所示是原图像及其RGB颜色空间中的DCD图像。

# 1.2.2局部颜色直方图的特征

直方图是图像的离散统计概率密度。遥感图像一般为RGB彩色图像格式，每个颜色通道的范围为[0,255]。如果考虑每个直方图的全部256个bin，那么计算复杂度较高。本文将每个通道的颜色bin量化为8个相等的bin，考虑每个像素的窗口，计算窗口的局部直方图。最终，图像的每个像素被映射为一个24维的向量。

# 1.2.3颜色统计的特征

每个像素窗口的第一、第二矩阵分别表示了平均值与标

准偏差。将像素每个RGB 通道的平均值与标准偏差考虑为颜色的统计特征。

![](images/6627f8ff1f5ede086a10ba8cac3c8f51c0df7c6708a90c02576eda1fa78e883d.jpg)

# 2 分类器的选择

# 2.1支持向量机(SVM)分类器

遥感图像存在较多的像素类别。将提取的特征输入分类器来训练模型的参数，对于每个像素类别，训练一个一对多的二值SVM(支持向量机)。假设主分类的像素为正样本，其他所有分类的像素为负样本，主分类的像素数量远低于其他分类的像素数量，因此会导致SVM模型不平衡，并且偏向负样本。为了解决该问题，从负样本集合中随机选择 $k$ 个样本作为SVM的负样本训练集，从而实现正负样本的平衡。图2所示是SVM分类器训练数据平衡后的数据实例。

![](images/b9e87ee4cd19ae894a75b45a8502eabaa59c9cf29759b40aca54033bd47ede35.jpg)  
Fig.1Original image and DCD image in RGB color space   
图2正负样本平衡的SVM训练方法  
Fig.2SVM training method for positive and negative sample balance 2.2极限学习机(ELM)分类器

ELM 原本是针对单隐层前向反馈神经网络(SLFN)而提出的分类器，对于广义的SLFN(单层前馈神经网络)，ELM的输出为

$$
f _ { L } ( x ) { = } \sum _ { i = 1 } ^ { L } \beta _ { i } h _ { i } ( x )
$$

其中：βi为第 $i$ 个隐层节点与输出节点之间的权重， $h _ { i } ( x )$ 为第 $i$ 个隐层节点的输出。隐层节点的输出函数 $h _ { i } ( x )$ 一般是一个非线性的分段连续函数，例如：Sigmoid函数、Hardlimit函数、高斯函数与多元函数。

前向反馈神经网络的目标是实现较小的训练误差，因此ELM同时考虑了较小的训练误差与较小的输出权重范数。权重范数越小，模型的泛化性能越好。ELM也可以表示为以下的优化问题形式：

$$
\operatorname* { m i n } : \left\| \beta \right\| _ { p } ^ { \sigma _ { 1 } } + C \left\| H \beta - T \right\| _ { q } ^ { \sigma _ { 2 } }
$$

其中 $: \sigma _ { 1 }$ 与 $\sigma _ { 2 }$ 均为正数， $p , q { = } 0 , 0 . 5 , 1 . 2 , . . . H$ 表示 $h$ 个方程的矩阵，称为隐层输出矩阵， $T$ 为训练数据的目标矩阵。本文采用ELM对像素特征向量集进行训练，然后对其他像素的特征向量进行分类处理。本文使用MATLAB中的ELM工具箱实现ELM分类器。

# 3 特性选择

特征选择是一个从 $n$ 个特征中选出 $m$ 个特征的离散优化

问题。使用下式计算出所有可用子集的数量：

$$
\sum _ { s = 0 } ^ { n } ( n / s ) = ( n / 0 ) + ( n / 1 ) + \ldots + ( n / n ) = 2 ^ { n }
$$

其中 $: n$ 表示特征向量的维度， $s$ 表示当前特征子集的规模。

# 3.1采用蚁群优化算法的特征选择

蚁群优化算法是一种基于迭代与概率的启发式算法。蚁群算法模拟了蚁群觅食的自然行为，蚁群在图中的节点之间游走，在经过的每条路径上释放信息素，根据信息素寻找最短的路径。路径上的信息素会随着时间而分解，蚂蚁则选择信息素浓度最高的路径，图中的最短路径也具有较多的信息素，使其被蚂蚁选择的概率也更高。将特征选择问题建模为选择图中最短距离的问题，图中的节点表示特征，边表示选择的下一个特征[16]。蚁群在图中游走之后，选出最优的特征子集。本文的信息素、启发值与节点(特征)关联，蚁群 $k$ 在时间 $t$ 选择特征 $i$ 的概率可计算为下式：

$$
P _ { i } ^ { k } ( t ) = \left\{ \begin{array} { l } { \displaystyle \frac { \left| \tau _ { i } ( t ) \right| ^ { \gamma } \left| \eta _ { i } \right| ^ { \delta } } { \sum _ { u \in J ^ { k } } \left| \tau _ { u } \left( t \right) \right| ^ { \gamma } \left| \eta _ { u } \right| ^ { \delta } } \mathrm { , ~ } i f \ i \in J ^ { k } } \\ { \displaystyle 0 \mathrm { , ~ } \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \end{array} \right.
$$

其中 $J ^ { k }$ 表示当前尚未被访问的特征集， $\tau _ { i } ( t )$ 与 $\eta _ { i }$ 分别为特征$i$ 关联的信息素值与启发值， $\gamma$ 与 $\delta$ 分别为信息素与启发信息的权重。时间 $t$ 时蚂蚁 $k$ 在特征 $i$ 释放的信息素计算为下式：

$$
\Delta \tau _ { i } ^ { k } \left( t \right) = \left\{ \begin{array} { l l } { \displaystyle \phi \cdot H ( S ^ { k } \left( t \right) ) + \frac { \Psi \cdot \left( F C - \left| S ^ { k } \left( t \right) \right| \right) } { F C } , } \\ { \quad \quad \quad \quad \quad \quad \quad \quad i f ( i \in S ^ { k } \left( t \right) ) } \\ { \quad \quad \quad \quad } \\ { \displaystyle 0 , \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \end{array} \right.
$$

其中 $F C$ 表示所有特征的数量， $S ^ { k } ( t )$ 与 $| S ^ { k } ( t ) |$ 分别为蚂蚁 $k$ 在迭代 $t$ 发现的特征子集与特征长度。 $H ( S ^ { k } ( t ) )$ 表示对子集 $S ^ { k } ( t )$ 分类器性能的评估结果， $\phi$ 与 $\psi$ 分别是平衡分类器性能与特征子集长度的权重，节点的信息素更新方法如下式：

$$
\tau _ { i } \left( t + 1 \right) = \left( 1 - \rho \right) \tau _ { i } ( t ) + \sum _ { k = 1 } ^ { m } \Delta \tau _ { i } ^ { k } \left( t \right) + \Delta \tau _ { i } ^ { g } \left( t \right)
$$

其中 $: m$ 为蚂蚁数量， $\rho$ 为信息素的挥发速率， $g$ 为当前的最优蚂蚁。(7)式说明了最优蚂蚁对节点的信息速度影响大于其他普通的蚂蚁，因此之后的迭代中蚁群会集中于最优解。基于ACO的特征选择方案如图3所示。

![](images/cae0eaa32297180ef5884e68651d2c7b5763bdf2adc7e8e2bc7622ecf79f4433.jpg)  
图3基于ACO 的特征选择方案  
Fig.3Feature selection scheme based on ACO

# 3.2本文的特征选择方案

筛选出相关性最高的特征，不仅能够降低特征向量的维度与分类器的计算成本，而且能够提高系统的分类准确率。本文的像素分类系统中，在特征提取阶段完成特征选择的处理。

# 3.2.1所有分类使用同一特征集(第一种特征选择方案)

基于ACO 的特征选择方案是一种基于封装的方案，传统的 ACO 特征选择算法中，每个蚂蚁基于每条路径的效率选出最优的特征。假设特征向量共有 $n$ 个特征，为每个蚂蚁随机分配一个初始化特征，第2个特征需要训练 $^ { n - 1 }$ 次的模型训练，第3个特征需要 $^ { n - 2 }$ 次的模型训练。最差的情况是每次迭代、每个蚂蚁需完成 $n ( n { - } 1 ) / 2$ 次的模型训练，因此计算成本极高。本文提出一种新的方案，在保持高分类性能的同时，降低计算成本。原始蚁群优化算法的每次迭代中，需要评估所有未访问的特征，该步骤的计算成本极高。从诸多文献的实验结果可看出，实际上无须所有的蚂蚁执行该步骤。为了解决该问题，本文将特征分为13个分组，如表1所示。表中LH_meanL 表示小波LH 频带L分量的范数均值，LH_meanH表示小波LH频带H分量的范数均值，HL_meanH表示小波HL频带 $\mathrm { ~ H ~ }$ 分量的范数均值，HL_meanL表示小波HL 频带 $\mathrm { ~ L ~ }$ 分量的范数均值，DCDRiR表示R颜色分量的主色，DCDRiG表示 $\mathbf { G }$ 颜色分量的主色，DCDRiB表示B颜色分量的主色， $R _ { m } \& R _ { s }$ 量表示R颜色分量的均值与标准偏差，$G _ { m } \& G _ { s }$ 量表示G颜色分量的均值与标准偏差， $B _ { m } \& B _ { s }$ 量表示B 颜色分量的均值与标准偏差， $R i$ 表示R颜色分量的直方图bin， $G _ { i }$ 表示G颜色分量的直方图bin， $B _ { i }$ 表示B颜色分量的直方图bin。

表1小波特征与颜色特征的分组  
Table 1Grouping of wavelet features and color features   

<html><body><table><tr><td>分组编号</td><td>特征意义</td><td>分组编号</td><td>特征意义</td></tr><tr><td>1</td><td>LH_meanL(小波特征)</td><td>8</td><td>Rm&R(颜色特征)</td></tr><tr><td>2</td><td>LH_meanH(小波特征)</td><td>9</td><td>Gm&G(颜色特征)</td></tr><tr><td>3</td><td>HL_meanH(小波特征)</td><td>10</td><td>Bm&B(颜色特征)</td></tr><tr><td>4</td><td>HL_meanL(小波特征)</td><td>11</td><td>Ri(颜色特征)</td></tr><tr><td>5</td><td>DCDRiR(颜色特征)</td><td>12</td><td>Gi(颜色特征)</td></tr><tr><td>6</td><td>DCDRiG(颜色特征)</td><td>13</td><td>Bi(颜色特征)</td></tr><tr><td>7</td><td>DCDRiB</td><td></td><td></td></tr></table></body></html>

特征分组的优点是每个蚂蚁仅需要评估每组的一个特征。因为每个分组内的特征对于分类准确率具有相似的效果，所以无须对每个分组的所有特征进行训练。例如：如果LH_meanL是在第 $k$ 次迭代从分组1中选择的特征，那么特征LH_stdL将是第 $k { + } 1$ 次迭代的一个候选解，说明该分组中的所有特征均有机会被选择。

第一个特征选择方案中，同时对所有的像素分类进行特征选择处理，特征选择方案通过最大化所有像素的分类准确率，提取出最优的特征。因此该方法中各个分类选择相同的特征子集。

第一个特征选择方法的步骤如下所示：

a)设置蚁群的规模。将每个特征与图中每个节点建立映射，为每个节点设置一个随机的信息素水平。设置最大迭代次数与结束条件。

b)将特征集分组。

c)每个蚂蚁创建一个解，每个蚂蚁从初始解(初始节点)开始游走，并且将该解标记为“已访问”。

d)每个蚂蚁从每个特征分组随机选择一个特征，并将该特征保存于队列 $\textbf { \em a }$ 。使用式(5)计算 $\mathbf {  { a } }$ 中所有特征的概率值，概率值最高的特征标记为“已访问”。

e)如果蚂蚁未能满足阈值条件(式(8))，那么返回步骤d)。

$$
A _ { t } = \varphi * \exp ^ { - { \frac { F N } { N } } } + \varphi * \exp ^ { F _ { - } M e a s u r e }
$$

其中： $F N$ 是蚁群目前已选择特征的特征基数， $N$ 是特征的总数量， $\varphi$ 与 $\omega$ 分别是控制特征规模与F_measure效果的参数，$\scriptstyle { \varphi + \omega = 1 }$ 。最终，所有蚂蚁成功获得相应的特征子集。

考虑了三条信息素的更新规则：(a)每个蚂蚁在特征上释放一些信息素；(b)一些信息素随着时间而挥发；(c)最优的蚂蚁对信息素更新具有决定性效果，从而其他蚂蚁可以跟随优质蚂蚁的路径。

f)蚁群的所有蚂蚁执行步骤 $\mathrm { c ) \mathrm { \sim } e ) }$ L。

g)每个蚂蚁在其路径中的特征上释放信息素，并将该节点标记为“已访问”，信息素更新方法计算为下式：

$$
\begin{array} { c l l } { \Delta p h e r ( i , k ) = \propto . \big ( A c c \_ m o d e l ( k ) \big ) } & & { } \\ { + \beta . \left( \frac { F _ { \mathrm { ~ - ~ } } C - F _ { \mathrm { ~ - ~ } } C ( k ) } { F _ { \mathrm { ~ - ~ } } C } \right) } & { } \end{array}
$$

其中 ${ \bf \nabla } \cdot \Delta p h e r ( i , k )$ 是蚂蚁 $k$ 在特征 $i$ 上释放的信息素，Acc_model(表示蚂蚁 $k$ 提取特征所训练的模型分类准确率。$F _ { - } N$ 与 $F _ { - } N ( k )$ 分别是特征总数量与蚂蚁 $k$ 路径中的特征数量。最终， $\scriptstyle a$ 与 $\beta$ 分别控制分类准确率与特征子集长度，并且 $\alpha + \beta = 1$ 。

h)搜索 $\mathrm { F } .$ -measure值最高的蚂蚁。

i)更新信息素：

$$
p h e r ( t + 1 ) = ( 1 - \rho ) . p h e r ( t
$$

$$
+ \sum _ { k = 1 } ^ { m } \Delta p h e r ( i , k ) + \Delta p h e r ( i , A n t _ { o p t i m a l } )
$$

j)删除已有的蚂蚁，随机产生新蚂蚁。

$\mathbf { k } _ { \mathrm { , } }$ 如果满足结束条件，则执行步骤1)，否则跳至步骤c)。  
1)F-measure值最大的路径即为最优解。

![](images/40fb14e19c698b0542c444527040b6d1f6b80da547394e6533e180d86a112701.jpg)  
图4所示是第一种特征选择方案的流程框图。  
Fig.4Flow of the first feature selection scheme

3.2.2不同分类使用不同特征集 (第二种特征选择方案)第一种特征选择方案将选择的最优特征集作为7个像素类的最优特征子集。第一个方法的特征降维阶段，研究了像素分类的主要属性，并且提出了包含小波特征与颜色特征的特征向量。对7个分类分别使用不同的最优特征集，可提高分类的准确率，图5所示分别是像素分类7与像素分类4的图像，图中小波特征的水平、垂直频率是分类7的不相关特征，而是分类4的高度相关特征。

![](images/e1bb0ce6d049db53eb0e15f0040542839f177167cc825aeec25da193ba8292c9.jpg)  
图5像素分类7与像素分类4的图像  
Fig.5Pixel classification 7and pixel classification 4

第二种特征选择方法为每个像素分类分别提取了一个最优特征子集，虽然该方法的计算时间较长，但是该程序为线下程序，可以保证线上程序的实时性。图6所示是第二个特征选择方案的流程框图。

这种类型的特征选择方案为每个每个像素分类设置一个最优的特征子集，从而保证每个像素分类具有最相关的特征子集，以期提高总体的像素分类准确率。第二种特征选择方案的步骤如下所示：

a)每个像素类运行步骤b)\~d)。  
b)运行第一种特征选择方案。  
c)分别计算每个分类的最优特征子集。  
d)分别训练每个像素分类的分类器。

![](images/1078b476ac36d8484fa09356135f3211da224d0e794eee88ad3022bcaba7a1df.jpg)  
图4第一种特征选择方案的流程  
图6第二个特征选择方案的流程框图  
Fig.6Flow of the second feature selection scheme

# 4 实验环境与参数设置

采用Mars Exploration Rover Spirit 数 据集作为benchmark数据集，该数据集共有94257个图像，图像大小均为 $5 1 2 \times 5 1 2$ 。图7所示是该数据集的三个图像实例。文献[17]将该数据集分为7个分类，如图8所示，将文献[17]的分类结果作为先验知识。

![](images/54591ef8baa91a707f934d49654357e89f81b54acc0284f50b10241cecbc3b11.jpg)

![](images/faba3d22e78f140ce5bf81058f202d1d2ad635a88bf09cac9daad1092b805f72.jpg)  
Fig.7Examples of remote sensing images   
图8遥感图像的7个分类实例  
Fig.8classification examples of remote sensing images

本算法的编程环境为：IntelCPU，主频为 $2 . 2 6 \ : \mathrm { G H z }$ ，内存为6GB。每个像素的窗口规模为 $2 1 \times 2 1$ ，计算灰度图像每个窗口的小波分解，并且计算窗口中行、列的范数，最终每个像素的特征向量均值与标准偏差共有8个小波特征。颜色特征的主颜色量设为8，因此，R、G、B三色通道共有24个特征，R、G、B通道的均值与标准偏差组成6个颜色的统计特征。使用R、G、B三个直方图的4个bin，共计算出12个特征。最终，每个像素均有一个50维的特征向量。

本实验的7个分类共有7个ELM分类器，每个分类对应一种地表类型。在每个分类器的训练过程中，将对应的地表类型作为正样本，其他像素作为负样本。表2所示是实验中所有7个分类的正、负样本数量，每组数据集的 $60 \%$ 像素作为训练集，剩下的 $40 \%$ 作为测试集。

表2MarsExplorationRoverSpirit数据集7个分类的正负样本数量  
Table 27classifications in mars exploration rover spirit data set   

<html><body><table><tr><td>分类</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td></tr><tr><td>正样本</td><td>5651</td><td>5470</td><td>4941</td><td>10771</td><td>8682</td><td>4959</td><td>5475</td></tr><tr><td>负样本</td><td>5734</td><td>4365</td><td>5412</td><td>12544</td><td>9322</td><td>4566</td><td>7165</td></tr><tr><td>样本总量</td><td>11385</td><td>9835</td><td>10353</td><td>23515</td><td>18004</td><td>9525</td><td>11640</td></tr></table></body></html>

KNN、GA与本算法在不同的参数设置下分别进行了实验，测试不同参数下三个算法特征选择与像素分类的性能。分类器模型采用 SMO 算法(sequential minimal optimization)作为SVM的学习方法，最大迭代次数为20000，内核缓存约束为10oo。多层感知机(multi layer perceptron)的范围为[-0.01,0.01]，高斯核为线性核函数，并且 $\scriptstyle \sigma = 4$ 。

采用几个常用的分类器性能指标评估本算法的性能，分别为：精度、召回率、 $F$ -measure、准确率， $F$ -measure定义为

$$
\mathrm { F } { \mathrm { - m e a s u r e } } = 2 \times \left( \mathrm { P r e c i s i o n } \times \mathrm { R e c a l l } \right) \mathrm { P r e c i s i o n } + \mathrm { R e c a l l }
$$

其中precision为精度，recall表示召回率。

# 5 实验结果与分析

# 5.1第一个特征选择方案的实验结果

为了比较不同分类器的效果，对ELM，SVM与KNN3个分类器分别进行实验分析，ELM，SVM与KNN分别采用13、17、18个特征。图9所示三个分类器获得的分类性能，图中可看出，ELM分类器实现了最高的性能。

![](images/63196e5365e4ada77b71cd264700d3bfce290724ebc04896e50827f132bfc3c2.jpg)  
图7遥感图像的实例  
图9三个分类器的分类性能(第一个特征选择方案)Fig.9Classification performance of 3 classifiers（1st)

# 5.2第二个特征选择方案

第二个特征选择算法为每个分类器提取了一个优化的特征子集。对ELM于SVM两个分类器分别进行了实验，结果如图10所示。从结果可看出，极限学习机的特征数量略多于SVM分类器。

![](images/418b19ed0dba2b6d4a7bb5bc5b3e44b4fb8caf7fb70b90a2ca5d8e499c6d89ba.jpg)

![](images/2aa2024828d8dbf30c64b7c503bf84543255c68beba8e365955a508689ad7b5b.jpg)  
图10ELM与SVM两个分类器的特征数量Fig.10Numberof features of ELMand SVMclassifiers图11所示是ELM与SVM分类准确率的结果，图中可看出，ELM分类器的分类准确率优于SVM分类器。

# 5.3算法的时间效率

时间效率是实时遥感图像处理算法的一个重要性能。本文同时考虑了算法在训练阶段与测试阶段的时间效率，图12所示是三个分类器训练与测试时间的实验结果。KNN分类器无须训练处理，但是其分类准确率远低于SVM与ELM分类器，总体而言，采用线性核的ELM实现了最低的计算时间。

# 5.4遥感图像的分割结果

遥感图像的分类处理可实现对遥感图像的分割，图13所示是图像分割的实例。从图中可直观地看出，本算法对于遥感图像的分类具有较好的准确率。

# 6 结束语

遥感图像的细节信息丰富、特征维度高，一般采用传统的特征提取方案提取遥感图像的特征，获得的特征表达能力弱并且信息损失严重，对遥感图像后续的处理具有不利的影响。为了在遥感图像采集终端实现图像的分类处理，提出了基于蚁群优化算法与独立特征集的遥感图像集实时分类算法，该算法提取遥感图像的小波特征与颜色特征，采用蚁群优化算法对特征数量进行优化处理，为每个图像分类分别训练一个独立的极限学习机分类器。实验结果表明，本算法有效地保证了图像分类的准确率，并且有效地降低了较快的处理时间。

![](images/9fdca96adab2ada1748080527ba330888ea90de50e3ce350b87b78ce245ec828.jpg)  
图12遥感图像分类算法的计算时间

![](images/354fdd44c72a5e7cdb2e3c9d9e098f4f8569e2227957a13dfa2623a5e2cd2aae.jpg)  
图11ELM与SVM分类准确率的结果(第二个特征选择方案)Fig.11Results of classification accuracy of ELMand SVM  
Fig.12 Computing time of remote sensing image classification algorithm   
图13图像分割结果的实例  
Fig.13Examples of image segmentation results

# 参考文献：

[1]Cheng Gong,Han Junwei, Lu Xiaoqiang.Remote sensing image scene classification: benchmark and state of the art [J].Proceedings of the IEEE,2017,105(10):1865-1883.   
[2] 赵泉华，刘冬，李晓丽，等．利用包含度和隶属度的遥感影像模糊分 割[J].中国图象图形学报,2017,22(7):988-995.(Zhao Quanhua,Liu Dong,Li Xiaoli,et al.Fuzzy segmentation algorithm for remote sensing images using inclusion degree and membership degree [J]. Journal of Image and Graphics,2017,22(7): 988-995.)   
[3]李俊麟，张黎明，司孝龙，等．光学遥感卫星杂散光扫描测试系统 [J]．红外与激光工程,2017,46(9):242-247.(Li Junlin, Zhang Liming, Si Xiaolong,et al. Scanning measuring system of stray light for optical remote sensing satellite [J]. Infrared and Laser Engineering,2O17,46(9): 242-247.)   
[4] 李德仁，沈欣，李迪龙，等．论军民融合的卫星通信、遥感、导航一体 天基信息实时服务系统[J].武汉大学学报：信息科学版，2017, 42(11):1501-1505.(Li Deren，Shen Xin，Li Dilong，et al.On civil-military integrated space-based real-time information service system [J].Geomatics and Information Science of Wuhan University, 2017,42(11): 1501-1505.)   
[5]Romero Adriana,Gatta Carlo,Camps-Valls Gustau. Unsupervised deep feature extraction for remote sensing image classification [J].IEEE Trans on Geoscience & Remote Sensing,2016,54 (3):1349-1362.   
[6]Liu Dawei,Han Ling,Han Xiaoyong.High spatial resolution remote sensing image classification based on deep learning [J].Acta Optica Sinica,2016,36 (4):0428001.   
[7]王利，杨征，李洋．特征聚合的遥感图像数据库检索技术[J].激光 杂志，2016,37(6):78-81.(Wang Li,Yang Zheng,Li Yang，et al. Retrieval technology of remote sensing image database based on feature aggregation [J].Laser Journal,2016,37(6): 78-81.)   
[8]曾锐，陈锻生．结合双深度学习特征的高光谱遥感图像分类[J].小 型微型计算机系统,2018,39(2):396-400.(Zeng Rui,Chen Duansheng. ConcatenatingTwodeeplearnedspectral-spatial featuresfor hyperspectral remote sensing imagery classification [J]. Journal of Chinese Computer Systems,2018,39(2):396-400.)   
[9]王峰萍，王卫星，薛柏玉，等.GVF Snake 与显著特征相结合的高分 辨率遥感图像道路提取[J]．测绘学报，2017，12(12):1978-1985. (WangFengping，Wang Weixing，Xue Baiyu,et al.Road Extraction from High-spatial-resolution Remote Sensing Image by Combining GVF Snake with Salient Features [J].Acta Geodaetica et Cartographica Sinica,2017,12(12):1978-1985.)   
[10]吴一全，陶飞翔，曹照清．基于Log-Gabor 小波和 Krawtchouk 矩的 遥感图像分类[J]．武汉大学学报:信息科学版,2016,41(7):861-867. (Wu Yiquan，Tao Feixiang，Cao Zhaoqing.Remote sensing image classification based on Log-Gabor wavelet and Krawtchouk moments [J]. Geomatics and Information Science of Wuhan University,2016,41 (7): 861-867.)   
[11] Kashef S,Nezamabadi-Pour H.An advanced ACO algorithm for feature subset selection [J].Neurocomputing,2015,147(1): 271-279.   
[12] Zhang Yong，Gong Dunwei,Zhang Wanqiu.Feature selection of unreliable data using an improved multi-objective PSO algorithm [J]. Neurocomputing,2015,171(C):1281-1290.   
[13]Alexandre E,Cuadra L,Salcedo-Sanz S,et al.Hybridizing extreme learning machines and genetic algorithms to select acoustic features in vehicle classification applications [J].Neurocomputing,2O15,152 (C): 58-68.   
[14]彭晏飞，李佳．基于遗传算法和 SVM 的遥感图像检索[J].小型微 型计算机系统,2016,37(4):875-880.(Peng Yanfei,Li Jia.Remote sensing image retrieval based on SVM and genetic algorithm [J]. Journal of Chinese Computer Systems,2016,37 (4): 875-880.)   
[15]张丹，王玉德，冯玮．一种基于小波特征贡献率的融合特征的检索 算法[J].激光杂志,2018,1(1):110-113.(Zhang Dan，Wang Yude, Feng Wei.A fusion feature retrieval algorithm based on wavelet feature contribution rate [J].Laser Journal,2018,1(1): 110-113.)   
[16]Forsati R,Moayedikia A，Jensen R,et al．Enriched ant colony optimization and its application in feature selection[J]. Neurocomputing, 2014,142(142):354-371.   
[17] Shang Changjing，Barnes D. Fuzzy-rough feature selection aided support vector machines for Mars image classification [J].Computer Vision & Image Understanding Cviu,2013,117(3):202-213.