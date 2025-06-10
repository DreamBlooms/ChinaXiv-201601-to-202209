# 一种改进的深度置信网络在交通流预测中的应用

赵庶旭，崔方

(兰州交通大学 电子与信息工程学院，兰州 730070)

摘要：针对现有交通流预测方法忽视对交通流数据自身特征的有效利用以及不能模拟更复杂的数学运算，提出了一种改进深度置信网络（dep belief network，DBN）的交通流预测方法。该方法结合深度置信网络模型与 Softmax 回归作为预测模型，利用连续受限玻尔兹曼机（continuous restricted Boltzmann machines，CRBM）处理输入特征向量，利用自适应学习步长（adaptivelearming step，ALS）减少RBM训练网络模型时重建误差所需的时间，用改进的深度置信网络模型进行交通流特征学习，在网络顶层连接 Softmax 回归模型进行流量预测。实验结果表明，在实际的交通流数据预测中，改进的DBN模型的预测准确率以及时间复杂度相比传统预测模型都得到了较好的改善。

关键词：交通流预测；深度置信网络；连续受限玻尔兹曼机；自适应学习步长中图分类号：TP181

# Application of improved deep belief network in traffic flow forecasting

Zhao Shuxu, Cui Fang† (Lanzhou Jiaotong University,School ofElectronic& Information Engineering,Lanzhou 73007o,China)

Abstract: In viewofthe factthat theexisting trafficflowprediction methods ignore the eficientuseof thetraic flowdata characteristicsand cannot simulate more complex mathematical operations,a traffic flow prediction method is proposed to improve the deep belief network (DBN).The proposed method combines deep belief network modeland Softmax regressionas predictionmodels,anduses thecontinuous restrictedboltzmann machine(CRBM)to processthe input eigenvectorsandreduces the adaptive learning step(ALS)RBMtrains the time needed toreconstruct the network model,and uses the improved dep belief network model tostudytetraffcflowcharacteristics.Softmaxregresion modelisconected totetopofthenetwork fortraffic prediction.The experimentalresultsshow that in theactualtrafficflowdataprediction,the improved prediction accuracy and time complexity of the improved DBN model are better than the traditional prediction model.

Key Words: traffc flow forecast; dep belief network; continuous restricted boltzmann machine; adaptive learning step

# 0 引言

交通流预测作为交通控制和交通诱导的基础和关键技术，是智能交通系统研究的核心问题。实时、准确、科学的交通流预测技术可以有效地提高交通的通行效率和安全性，最大限度地实现城市路网运载能力的合理利用，实现交通流诱导，从而缓解了交通拥挤，减少了环境污染。

现有的交通流预测模型主要有基于以往历史数据的时间序列模型、概率图模型、非参数统计预测模型和组合模型等。a)基于以往历史数据的时间序列模型，自回归滑动平均模型（ARMA)就是通过找到交通流随时间变化的模式，从而实现预测。但是这类模型在实际应用中需要依赖大量的历史数据，受随机干扰因素影响较大，预测成本较高;b）概率图模型：贝叶斯网络，马尔可夫链，马尔可夫随机场等,这些预测模型虽然提高了预测的精确性，但是没有考虑到在路网当中交通状况之间的时空相关性;c）非参数统计预测模型：神经网络（NN）、KNN 方法、支持向量机（SVM）等。由于这种方法能够很有效地模拟交通流不确定、复杂性和非线性等特点，所以它比其他方法取得的效果更好，但是神经网络、支持向量机等预测模型均属于浅层模型，在有限样本和计算单元条件下，不能模拟更复杂的数学运算，并且大量样本的数据特征都是根据特定领域的先验知识选择，忽视了对交通流数据自身特征的有效利用。

近年来，深度学习作为机器学习的新兴学科，一经提出便受到研究人员的高度关注。深度学习结构是一个包含多隐藏层的多层感知器，它可以通过学习一种深层的非线性网络结构，来实现复杂函数的逼近，也可以从大量输入数据中学习有效的特征表示。深度学习将较低层的输出作为更高层的输入，学习到的高阶特征表示中就包含输入数据的许多结构信息，是一种从数据中提取表示的好方法，能够用于分类、回归和信息检索等特定问题中。随着深度学习的深入研究，基于深度学习的交通流预测方法正在兴起，相比较以往浅层结构的预测方法，预测精度较高，但是目前应用深度学习来进行交通流预测的文章还比较少。在交通流预测方法中使用到的深度学习模型有自编码（AE）模型和深度置信网络（DBN）模型等。DBN模型是由多个受限玻尔兹曼机（RBM）组成的深层次网络[II。由于RBM只能接受二进制输入而导致数据丢失以及其在训练网络模型参数时收敛速度缓慢的问题，所以给交通流预测结果的准确性带来了挑战。

针对以上现有交通流预测方法的问题，本文提出了一种改进的DBN模型。该模型首先使用有高斯分布的连续受限玻尔兹曼机（CRBM）的DBN模型对交通流数据的输入向量进行特征学习，然后利用对比散度算法进行抽样以获取高层次的特征向量来达到对交通流状态的预测。在训练DBN网络模型参数过程中，使用自适应学习步长（ALS）来实现特征参数的快速收敛。实验结果表明，该方法在交通流预测中取得了不错的准确率，是一个可行、有效的交通流预测方法。

# 深度学习模型

深度学习由Hinton 等人在2006 年提出[2]。它通过发现数据的分布特征将低层组合成更加抽象的高层来表示属性类别或特征[]。深度网络是一种与浅层网络类似的多层次的网络，它能为复杂的非线性系统建模，通过为其提供更高层的抽象特征，来提高模型的表达能力。

# 1.1深度置信网络模型

深度置信网络可以解释为一个概率生成模型。它是通过若干个RBM堆积而成。Hinton 等人提出了一种可以快速的非监督逐层贪婪训练DBN的方法[4]。根据深度学习机制，采用输入样本训练第一层RBM单元，并利用其输出训练第二层RBM模型，将RBM模型进行堆栈通过增加层来改善模型性能。在无监督预训练过程中，DBN编码输入到顶层RBM后解码顶层的状态到最底层单元实现输入的重构。

# 1.2受限玻尔兹曼机模型

RBM即受限玻尔兹曼机，它是一个两层的无向图模型[5]，包含一个可视层和一个隐藏层，如图1所示。可视层用来表示数据信息，隐藏层用来增加学习数据的能力。

![](images/9b7304304f6c63df3baa3ec1c92de5485a01c8ee2cfa304f8dbf22219eb85fef.jpg)  
图1RBM 模型图

该模型可视层单元和隐藏层单元彼此互连（层内无连接，区别于玻尔兹曼机)，而且它们之间的分布可以表示为任意指数分布，在这里是假设所有可视层单元和隐藏层单元均为二值分布。

可视层单元（ $\nu$ ）对应于输入，隐藏层单元（）对应于特征探测，其隐藏层单元可以获取输入可视层单元的高阶相关性。它们的联合组态能量方程 $( \nu , h )$ 为

$$
E ( \nu , h ) = - \sum _ { i \in \nu } a _ { i } \nu _ { i } - \sum _ { j \in h } b _ { j } h _ { j } - \sum _ { i , j } \nu _ { i } h _ { j } w _ { i j }
$$

其中： $\nu _ { i }$ 和 $h _ { j }$ 是可视单元输入 $i$ 和隐藏单元特征 $j$ 的二进制状态；$a _ { i }$ 和 $b _ { j }$ 分别是它们的偏移量； $w _ { i j }$ 是它们之间的权重矩阵。因为隐藏节点之间是条件独立的(因为节点之间不存在连接)，即

$$
P ( h \vert \nu ) = \prod _ { j } P ( h _ { j } \vert \nu )
$$

在给定可视层 $\nu$ 或者隐藏层 $h$ 的基础上，可以计算出它们的条件概率分布：

$$
P ( \nu _ { i } = 1 | h ) = { \frac { 1 } { 1 + \exp ( - \sum _ { j } W _ { i j } h _ { j } - a _ { i } ) } }
$$

$$
P ( h _ { j } = 1 | \nu ) = \frac { 1 } { 1 + \exp ( - { \displaystyle \sum _ { i } } W _ { i j } \nu _ { i } - b _ { j } ) }
$$

当给定一组训练样本集合 $S = \{ \nu ^ { 1 } , \nu ^ { 2 } , . . . , \nu ^ { n } \}$ 时，其目标就是最大化如下对数似然函数：

$$
L _ { S } = \sum _ { n = 1 } ^ { N } \log P (  { \boldsymbol \nu } ^ { n } )
$$

研究表明，对于RBM模型的训练，使用马尔科夫链（MCMC）方法获得对数似然概率的无偏差估计，并且只需要一定步数的吉布斯采样就能达到训练的要求[]。Hinton提出了一种名为对比散度的快速学习算法来训练受限玻尔兹曼机模型，该算法对RBM模型进行数据的训练和各个参数的更新，既能提高学习的计算速度，又能保证计算精度。

# 2 CRBM-DBN预测模型研究

# 2.1连续受限波尔兹曼机模型

在传统RBM模型中，可视层输入限制为二进制数(0或1)，对于模拟交通流这样的连续值来说是很不方便的，所以提出了一种连续受限玻尔兹曼机模型（CRBM)，该模型在线性单元中加入独立高斯分布的连续值来模拟真实的数据7]，使得传统受限玻尔兹曼机可以处理连续的输入向量，其能量函数改为

$$
E ( \nu , h ) = \sum _ { i } \frac { ( \nu _ { i } - a _ { i } ) ^ { 2 } } { 2 \sigma _ { i } ^ { 2 } } - \sum _ { j } b _ { j } h _ { j } - \sum _ { i } \sum _ { j } \frac { \nu _ { i } } { \sigma _ { i } ^ { 2 } } h _ { j } w _ { i j }
$$

其中： $\nu _ { i }$ 表示可视层第 $i$ 个真实值； $\sigma$ 是高斯函数的标准方差向量。通过方程就能让可视层的表达获得某个特定连续值的优先权，根据能量方程[8]，得到它们的条件概率分布为

$$
p ( \nu _ { i } \mid h ) = N ( b _ { i } + \sigma _ { i } \sum _ { j = 1 } ^ { n } h _ { j } w _ { i j } , \sigma _ { i } ^ { 2 } )
$$

$$
p ( h _ { j } \mid \nu ) = s i g m ( \sum _ { i = 1 } ^ { n } \nu _ { i } w _ { i j } + a _ { j } )
$$

CRBM训练以及更新参数的过程与传统RBM没有什么区别，都可以运用对比散度（CD）算法对其参数进行调整。

# 2.2 CRBM-DBN预测模型体系架构

本文改进的深度置信网络模型结构包括一个CRBM、两个RBM和一层BP神经网络节点。三个RBM采用无监督训练机制进行训练，BP网络采用有监督机制进行训练。整个训练过程都尽可能地做到减少原始输入数据的遗漏[。将期望输出和实际输出之间的误差进行反向传播，利用mini-batch梯度下降法调整了整个网络的参数，寻找网络的最优。通过之前的描述，建立出改进的DBN预测模型的深度体系架构，底层是由CRBM与RBM组成的DBN架构[10]，用于对输入的连续数据进行无监督的特征学习，顶层再加入一个Softmax回归层用来对交通流的状态进行预测。建立的预测模型体系架构如图2所示。

# 2.3 自适应学习步长

一般来说，训练DBNs是一个计算上比较复杂的过程，因为它涉及到独立的进行几个RBMs 的训练，并且可能需要相当长的时间。此外，选择适当学习速率参数也是训练过程的一个基本方面，所以提出了一种使用自适应学习步长（ALS）方法[来解决选择适当学习速率和加快训练收敛速度的问题。

![](images/0afaf6a32b1c6461bd8180ce79d66cfd8a7012def3a4d43a19033fbad4d5fe6d.jpg)  
图2CRBM-DBN预测模型体系架构

ALS方法是使用每个权重连接 $w _ { i j }$ 的个人学习率（步长）参数 $\eta _ { i j }$ 来代替整个网络的全局学习率。本文使用ALS方法来解决RBM在训练网络参数时收敛速度缓慢的问题。在每个CD-k的迭代中，步长根据符号变化进行调整:

$$
\eta _ { i j } = \left\{ \begin{array} { c c } { { u \eta _ { i j } ^ { o l d } } } & { { \left( \left. \nu _ { i } h _ { j } \right. _ { 0 } - \left. \nu _ { i } h _ { j } \right. _ { k } \right) \left( \left. \nu _ { i } h _ { j } \right. _ { 0 } ^ { o l d } - \left. \nu _ { i } h _ { j } \right. _ { k } ^ { o l d } \right) > 0 } } \\ { { d \eta _ { i j } ^ { o l d } } } & { { \left( \left. \nu _ { i } h _ { j } \right. _ { 0 } - \left. \nu _ { i } h _ { j } \right. _ { k } \right) \left( \left. \nu _ { i } h _ { j } \right. _ { 0 } ^ { o l d } - \left. \nu _ { i } h _ { j } \right. _ { k } ^ { o l d } \right) < 0 } } \end{array} \right.
$$

其中 $u > 1$ （向上）表示步长的增量因子， $d < 1$ （向下）表示步长的减量因子。如果两个连续的更新具有相同的方向，则该特定权重的步长增加。对于相反方向的更新，步长减小，从而避免学习过程中由于过多的学习速率而产生的振荡。该过程的基本思想是找到可以绕过错误表面峡谷上的近似的最佳步长。

$$
X _ { i } ^ { t } = \{ x _ { i } ^ { t _ { 1 } } , x _ { i } ^ { t _ { 2 } } , . . . , x _ { i } ^ { t _ { n } } \}
$$

其中： $i = 1 , 2 , \ldots , n$ ； $t = 1 , 2 , \dots , T$ 。那么交通流预测就是根据以往的交通流量序列对于某条道路的 $\{ T + \Delta t \}$ 时间段来进行后期交通流量的预测，其中 $\Delta t$ 可以进行调节[12]。

在CRBM-DBN模型中，将具有交通流状态时序的数据通过高斯分布处理并且进行特征学习，可以得到代表以往历史交通流时间序列的一个特征代表模型 $H$ 。经过特征的学习和训练后，以往的交通流时间序列 $X$ 可通过 $H$ 转换为另外的一个特征空间 $Y$ ，即 $H ( x )  Y$ ，然后给定一组特征空间 $Y$ 与目标任务 $z$ 的配对组合表示为 $\{ ( Y _ { 1 } , Z _ { 1 } ) , ( Y _ { 2 } , Z _ { 2 } ) , ~ . . . ~ , ( Y _ { n } , Z _ { n } ) \}$ 来学习预测模型$Z _ { n + 1 } = G ( Y )$ [13],通过最小化目标损耗函数 $L$ ，得到预测模型的适合的参数 $W$ ：

# 2.4 CRBM-DBN预测模型算法

给予一个给定的路段，设 $X _ { i } ^ { t }$ 表示第 $i$ 个交通道路在第 $t$ 时间的交通流量，那么给定一个观察得到的交通流量序列表示为

$$
L ( Z ; W ) = \left\| Z - G ( Y ) \right\| ^ { 2 }
$$

在训练整个预测网络模型参数的过程中，利用自适应学习步长策略，进一步加快训练参数的收敛速度，解决了其收敛速度缓慢的问题。

CRBM-DBN预测模型的训练包括预训练和微调两个部分，过程如下:

a）预训练阶段。使用CRBM-DBN预测模型算法对输入的交通流数据进行重构。输入原始时间序列数据为${ \boldsymbol { x } } ( t ) , t = 1 , 2 , \ldots , T$ ，其经过重构后为 $x ( t - \tau ) , x ( t - 2 \tau ) , \ \ldots \ , x ( t - n \tau )$ ，其中 $\tau$ 是一个正整数， $n$ 是输入空间的维数，并且 $t - n \tau \leq T$ 。但是如果 $t - \tau \leq 0$ ，则设置重构之后的数据表示为 $x ( t - \tau ) = x ( t )$ □

b）微调阶段。在网络模型顶层利用BP算法使用有标签的数据进行自上而下的参数微调[14]。由于模型预训练后的参数已经接近于训练好的值，那么再做BP算法时，只需要在已知的参数里进行一个局部搜索[15]即可。具体的CRBM-DBN 预测模型算法过程如图3所示。

![](images/1ab26a656be382691106fb1ae93d3ab37f1d6f8eb509d983aa71e93ed1dfc35e.jpg)  
图3CRBM-DBN预测模型算法流程图

通过训练出来的CRBM-DBN模型算法就可以作为交通流数据的预测模型，即当给定一组输入数据后，便会得到对应道路的预测输出。

# 3 实验结果及分析

# 3.1实验数据描述

模型的仿真和验证工作基于山东省淄博市的某局部区域监控数据开展。依据官方提供的该区域交通历史监控数据进行梳理得到实验的样本数据集。数据集包含有每隔 $1 5 \mathrm { m i n }$ 的交通平均路途消耗时间、速度与交通流量，并且数据覆盖了淄博市的城市主干道。在此选取淄博市临淄区和张店区之间的五条主要城市道路，分别是临淄大道，桓公路，宏达路，张皇路，古候路。根据预测模型的构建需求，需分别整理两类学习集，即特征学习集和分类学习集。选取其2015年8月份的数据，共有30天数据。其中前29天的数据用以训练模型，后1天的数据用以测试。

# 3.2性能指标

为了能够更好的分析预测效果，使用两个最常见的性能指标参数为绝对平均误差（MAE）和相对平均误差（MRE)，定义如下:

绝对平均误差（MAE）

$$
M A E = \frac { 1 } { N } \sum _ { t } Y _ { p r e d } ( t ) - Y _ { r e a l } ( t )
$$

相对平均误差（MRE)：

$$
M R E = \frac { 1 } { N } \sum _ { t } \frac { Y _ { p r e d } ( t ) - Y _ { r e a l } ( t ) } { Y _ { r e a l } ( t ) }
$$

$Y _ { p r e d }$ ：交通流量预测值, $Y _ { r e a l }$ ：实际的交通流数值。在这里选择了MAE 与 MRE作为衡量标准。

# 3.3实验结果

实验程序在Windows764位系统Intel-I7CPU、32GB内存的高配置计算机上进行，编码在pycharm-professional平台下完成。在深度体系架构中，需要决定DBN模型的输入层大小，隐藏层层数以及其每一层的节点个数，其中隐藏层层数和其每一层的节点个数需要大量的测试来选定。在此选取五条道路的前两个时间段的交通流量作为输入，即共10个输入，桓公路作为其预测输出。选定隐藏层为深层结构{10，12，10，8，6，4}，通过训练以后对桓公路第30天做预测的结果如图4所示。

![](images/9c266839c6fcb0f4bbbb81f81d9159a03f9a020bccaf9fa87a5d1e0c4688650f.jpg)  
图4预测值和实际值的对比结果

由图4可以看出，本文提出的预测模型的预测结果与实际交通流数据偏差很小，反映了交通流随时间变化的基本规律。

实验中对训练CRBM-DBN模型的微调阶段里BP过程的调优次数epochs做了调整测试，结果发现大于某个数量时，模型的预测结果对于迭代次数的调整并没有特别大的影响。这也印证了模型在预训练阶段时参数的调整已经近乎较优的判断。模型的预训练结果如图5所示。

![](images/e478557c7a921e313459b1aaaca6ad83567a62228df04c851bbd540a081eca4b.jpg)  
图5预训练结果显示

由图5可以看出，随着RBM层数增加，整体损失会逐渐减小，这可以说明预训练这一过程可以预先训练出较好的参数值。

# 3.4本文算法与其他算法比较

# 3.4.1预测准确率比较

为了进一步验证本文提出的预测模型的有效性，使用本文方法与传统RBM-DBN模型以及CRBM-DBN模型算法相比较。每种算法都使用相同的数据集进行实验。三种算法的性能指标对比如表1所示。

表1性能指标对比  

<html><body><table><tr><td>方法</td><td>MAE</td><td>MRE</td></tr><tr><td>RBM-DBN</td><td>20.98</td><td>0.758</td></tr><tr><td>CRBM-DBN</td><td>15.53</td><td>0.354</td></tr><tr><td>CRBM-DBN（ALS)</td><td>15.35</td><td>0.335</td></tr></table></body></html>

![](images/b3bf657079815109b0d42339ebbce9e1d8404f3f36a86db670fd5af4b73ce56b.jpg)  
图6三种算法的准确率对比

从图6中可以看出，在迭代次数较小的时候，三种算法准确率差距并不是很大，但是随着迭代次数增加，本文方法预测准确率是随着迭代次数增加而逐渐上升，最终维持在 $8 5 \%$ 左右；而传统RBM-DBN模型和CRBM-DBN模型也是随着迭代次数的增加而预测准确率逐渐上升的，但传统RBM-DBN 模型准确率只维持在 $67 \%$ 左右，而CRBM-DBN模型准确率维持在了 $80 . 8 \%$ 左右。

由上述的实验结果分析可知，本文方法中的CRBM-DBN（ALS）模型以及CRBM-DBN 模型与传统RBM-DBN 模型相比，预测精度要有所提高。所以只将本文CRBM-DBN（ALS）模型以及CRBM-DBN模型与实际交通流量作比较，如图7所示。

![](images/fb6a896c7452d4701d6d3c3cc1620f82e71a5c790e2ee163a70e995aad26475b.jpg)  
图7两种预测模型与实际交通流量对比

从图7中可以看出，在对实际交通流量的预测结果中，本文的CRBM-DBN（ALS）模型要比CRBM-DBN模型更加接近实际的交通流量曲线。

# 3.4.2时间复杂度比较

RBM基于CD的快速学习算法中通常采用一个全局的学习步长来对网络进行训练。然而，学习步长若过大，将导致重构误差急剧增加，权重也会变得异常大；学习步长过小可避免上述情况出现，但收敛速度较慢，训练时间过长，为解决这一矛盾，在CRBM-DBN模型中引入了自适应学习步长，可以有效的减少模型训练的时间。在自适应学习步长的实验中，将自适应学习率与三种不同的固定学习率值（ $\eta = 0 . 1$ ， $\eta = 0 . 5$ 和 $\eta = 0 . 9$ ）进行比较。对于自适应步长来说，每个连接的初始学习率设置为0.1，增量 $u$ 和减数 $d$ 的值分别取为1.2和0.6。总共设置了十二种不同的取值测试（三种用于自适应步长，另外九种用于固定学习率)，每个测试都以不同的权重开始，但是为了公平起见，每个测试都会根据正在执行的测试使用相同的权重值。图8显示了不同学习速率 $\eta$ 的均方根误差（RMSE）的变化。可以看出，自适应学习率优于所有的固定学习率。对于固定学习率来说，设置$\eta = 0 . 5$ 的结果最好，而 $\eta = 0 . 9$ 的结果最差。

![](images/2c3b923c906dc6902b3bd3d53690fc6bff3fc656671888be106a3423b0f6fb45.jpg)  
图8不同学习率的RMSE

通过使用自适应步长，本文不再需要搜索合适的 $\eta$ 参数。此外，它可以很容易地从不良选择中恢复初始学习率，并且参数 $u$ 和 $d$ 容易调整。

表2给出了各个算法的时间复杂度。本文CRBM-DBN（ALS)方法的时间复杂度为18.15，比RBM-DBN方法快了7.72，比CRBM-DBN方法快了5.58。引入高斯分布的CRBM-DBN方法对传统的RBM-DBN方法来说，收敛速度影响不算很大，但是在CRBM-DBN方法基础上加入ALS方法就加快了收敛速度，大大提高了训练速度。

表2算法时间复杂度比较  

<html><body><table><tr><td>方法</td><td>时间复杂度(s)</td></tr><tr><td>RBM-DBN</td><td>25.87</td></tr><tr><td>CRBM-DBN</td><td>23.73</td></tr><tr><td>CRBM-DBN（ALS)</td><td>18.15</td></tr></table></body></html>

从以上实验结果综合分析可以得出，使用本文方法与传统RBM-DBN方法以及CRBM-DBN方法相比，预测准确率以及时间复杂度有较大幅度的改善。

![](images/f0128536977c7df1d5006b4d3e3e184196414ad2a269a33d08f942d32d9c24e0.jpg)  
图9 17:40-17:45时间段结果显示

![](images/c86783d4dfd06bd28e93ac40bff5e2f45feb69269a6c74575f4356a9bd14ce03.jpg)  
图1018:25-18:30 时间段结果显示

为了使交通流预测的情况更为直观的显示，应用ArcGIS在每个时间段可视化出预测的热度图。其热度图的显示效果如图9以及图10所示。图中绿色较深的部分表示交通状态为畅通，绿色较浅的部分表示交通状态为基本畅通，随着颜色部分的变化情况，来说明交通流状态的五个状态，分别是畅通，基本畅通，轻度拥堵，中度拥堵，严重拥堵。

# 4 结束语

本文提出了一种基于CRBM-DBN模型的交通流预测方法。其中针对RBM只能接受二进制输入而导致数据丢失问题，提出了带有高斯分布的CRBM模型，以及其在训练网络模型参数时收敛速度缓慢问题，提出了一种自适应学习步长的解决方法，在每次迭代中，该方法寻求近似最佳步长来提高收敛速度。实验结果表明，用本文提出的预测方法预测出的值与真实值基本吻合，且预测精度较高，是一种有效的交通流预测方法。

由于本文CRBM-DBN（ALS）模型算法的复杂性，其时间复杂度的简化仍然是未来研究的重点。如果该模型能够并行训练，则会大大提高训练的速度。此外，本文只是对交通路段中单个断面的输出进行预测，多断面输出预测还需要进一步研究。

# 参考文献：

[1]江德浩．基于深度信念网络的短时交通流预测[D].长沙：湖南师范大 学,2016.   
[2]刘建伟，刘媛，罗雄麟．深度学习研究进展[J].计算机应用研究,2014, 31(7):1921-1930.   
[3]罗向龙，焦琴琴，牛力瑶，等．基于深度学习的短时交通流预测[J]. 计算机应用研究,2017,34(1):91-93.   
[4]Hinton G E,Osindero S,Teh YW.A fast learning algorithm for deep belief nets [J].Neural Computation,2006,18(7): 1527.   
[5]FischerA,Igel C.Training restricted Boltzmann machines:an introduction [J].Pattern Recognition,2014,47(1): 25-39.   
[6]Hinton G E.A Practical guide to training restricted Boltzmann machines [J]. Momentum,2012,9(1): 599-619.   
[7]Salakhutdinov R,Hinton G.Using deep belief nets to learn covariance kernels for Gaussian processes [C]// Proc of International Conference on Neural Information Processing Systems.[S.1.] :Curran Associates Inc. 2007: 1249-1256.   
[8] Chen H, Murray A F. Continuous restricted Boltzmann machine with an implementable training algorithm [J].IEE Proceedings:Vision, Image and Signal Processing,2003,150 (3):153-158.   
[9]柴瑞敏，侣称称．一种改进的深度置信网络及其在自然图像分类中的 应用[J].计算机应用与软件,2016,33(9):221-223.   
[10] Bengio Y,Lamblin P,Popovici D,et al. Greedy layer-wise training of deep networks [C]//Advances in Neural Information Processing Systems,2007: 153-160.   
[11] Silva FM,Almeida L B.Acceleration techniques for the backpropagation algorithm [C]// Proc of Eurasip Workshop on Neural Networks.[S.1.] : Springer-Verlag,1990:110-119.   
[12]刘思妍.城市道路交通流预测方法的研究[D].上海：上海交通大学, 2015.   
[13]尹邵龙，赵亚楠．深度学习在城市交通流预测中的实践研究[J].现代 电子技术,2015,38(15):158-162.   
[14]孙志军，薛磊，许阳明，等.深度学习研究综述[J].计算机应用研究, 2012,29 (8): 2806-2810.   
[15] Lv Y,Duan Y,Kang W,etal. Traffic flow prediction with big data: a deep learning approach [J].IEEE Trans on Inteligent Transportation Systems, 2015,16 (2): 865-873.