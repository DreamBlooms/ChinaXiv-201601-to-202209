# 动作识别中基于深度神经网络和GA合并算法的分类决策方法‘

赵雪章1，席运江²，黄雄波1

(1．佛山职业技术学院，广东 佛山 528137;2．华南理工大学，广州 510 510641)

摘要：针对人体动作识别中传统方法在分类决策方面存在问题和缺陷，提出了一种新颖的基于深度神经网络(DNN)和遗传算法(GA)合并算法的非线性分类决策方法。首先，提出的合并算法在整个训练集合上对特征提取器进行组合，进而组合成不同的两个独立网络；再利用DNN对两个独立网络进行初始化，进一步利用GA 对两个网络进行合并。然后将网络的偏差和权重表示为每层网络间的一个矩阵；最后，利用 DNN 对网络的偏差和权重进行训练，并在合并过程中将矩阵中的每一行当作一个染色体。实验采用了标准 MNIST 数据集对提出算法的性能进行评估。评估结果显示实验过程中的交叉和突变操作增加了神经元节点，提高了识别性能，并且弱化了不相关和相关神经元节点。因此，提出算法的错误率更低，网络性能更优异。

关键词：动作识别；分类决策；重新训练；遗传算法；深度神经网络 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2018.01.0120

# Classification decision method based on depth neural network and GA merging algorithm in motion recognition

Zhao Xuezhang1, Xi Yunjiang², Huang Xiongbol (1.FoshanPolytechnic,FoshanGuangdong528137,China;2.SouthChina UniversityofTechnology,Guangzhou510510641, China)

Abstract:Aiming atthe problems and shortcomings of traditional methods in human motion recognition in clasification decision,a novel nonlinear clasification decision method basedondeepneural network(DNN)and genetic algorithm (GA) mergealgorithmis proposed.First,the proposed merging algorithmcombines the feature extractors overthe entire training set andcombines them into twodifferent independent networks.ThenuseDNNto initializetwo independentnetworksandfurther use GAto merge the twonetworks.Then thedeviationand weightofthe network are expressedas a matrix between eachlayer ofthe network.Finally,use DNN totrain thebias and weight of the network,and each row in the matrix istreated as a chromosome during the merge process.The experimentuses the standard MNISTdata set to evaluate the performanceof the proposedalgorithm.The evaluationresultsshowed thatthecrossver and mutation operations during the experiment increased the neuronnodes,improvedtherecognition performance,and weakenedthe irelevantandrelated neuronal nodes.Therefore, the proposed algorithm has a lower error rate and better network performance.

Key words: motion recognition; classification decision; retraining; genetic algorithm; depth neural network

# 0 引言

模式识别研究是机器智能研究领域的一个重要组成部分，是一项基本的智能活动。机器智能研究有两个主要的起点，一个是通过人类或其他生物的自然智能建立数学模型，其次是使用各种数学工具来建立电脑模型。深度神经网络已经在语音识别，图像识别等领域取得了空前的成功[1]。神经网络系统是由大量的神经细胞（神经元）复杂的系统组成的，人们通过网络建立数学模型和算法，试图使其能够实现诸如基于数据的模式识别、函数映射等智能功能。反向传播是一种典型的用于深度神经网络(deep neural network，DNN)的学习方法，通常情况下将这种算法与一种优化算法进行结合使用，比如梯度下降算法[2]。

当前的人体动作识别主要依赖于传感器[3]，通过在人体各个部位放置多个传感器，如利用智能手环等传感器。传统的机器学习方法，如支持向量机（supportvectormachine，SVM）、贝叶斯网络、时域频域分析等机器学习方法也是研究的重点。文献[4]用到了卷积神经网络，但依然需要人为的提取动作特征。

文献[5]也用到了卷积神经网络，但是由于只使用了一层卷积层，学习深度不够，无法提取更高维度的特征。基于目前的研究，为了提取更高维度的特征来提升分类效果，本文根据遗传算法(geneticalgorithm，GA)的启发，提出了一种用于深度学习的合并算法。之前，在文献[6]中提出了一种结合GA的神经网络方法试图提高分类精度，将GA作为图像分割的一个后处理程序，利用神经网络对图像进行处理之后再利用GA进行图像分割。区别于文献[6]，本文提出的算法将GA作为神经网络中的一个特征提取器，利用这个特征提取器对初始权重进行最优化。

本文算法的主要思路是利用GA选取更多的显性特征，其由两个阶段构成。在第一阶段，将整个训练数据集合划分成两个训练数据集合，然后利用DNN对这些数据集合进行训练。在第二阶段，利用GA将两个训练所得的网络进行合并，提出的算法利用网络中已经存在的训练信息，即权重和偏差。因此，将训练数据或者类别添加到网络中，但是，初始版本的DNN 算法用于对整个数据进行预先训练，整个数据集合是由初始数据和附加数据构成。本文提出的算法仅通过预先训练附加数据并利用已经存在的网络信息构建新网络,对附加数据进行预先训练之后，利用GA将训练结果和已经存在的网络进行合并。也就是说，本文提出的算法将可以给出一种新的重新训练的方法。

# 提出算法的GA处理过程

本文提出的算法是一种基于GA的典型方法，这种新方法利用进化准则解决各种问题。GA为最优化问题生成了解决方案，GA的提出是受到自然进化方法的启发，包括遗传、变异和交叉三种算子[7,8]。图1中给出了一个GA过程的简单模型。

![](images/3c004f72be0be7548c9a73494d513912dc4452998e30cc018eafe838a662eb98.jpg)  
图1GA过程的简单模型

本文利用这个方法选取显性特征，具体步骤如下：

a)将网络中每层之间的权重矩阵和偏差向量作为染色体，遗传给下一代。

b)通过交叉和变异算子的结合获取新的下一代，初始父本、母本为父母。

c)在众多子代中，根据对网络的适应度，选取两个子代作为父本和母本作为父母 $_ 2$ ，然后重复执行整个过程;然后构建由神经网络中每层之间的权重和偏见组成的矩阵，这些矩阵的第一列为偏差向量，剩余列构成的矩阵为权重矩阵。过程如图2 所示,本文提出的算法将这个矩阵的每一行作为一个染色体。

![](images/91815c9d05eb7e5ec8b3131d5be5a4ff662e005b335b6b0db30b80b6bcfae1a4.jpg)  
图2GA过程的矩阵化模型

将从父母 $_ 1$ 和父母 $2$ 中随机选取的行进行复制，然后将其添加到随机矩阵中以完成交叉过程，随机矩阵的值依赖于交叉概率(交叉率)。在这个过程中，将父母 $_ 1$ 和父母 $_ 2$ 的复制比例定义为分数比。交叉步骤结束之后，按照变异概率 $p ( m )$ 进行变异操作。在本文提出的算法中，变异过程是通过将染色体的一部分设置为零而完成的。

为了确定下一代的父母，需要完成对后代的评估。为了达到评估的目的，本文准备了验证集合，验证集合是训练集合的一部分，利用验证集合可以获取每个后代的错误率，然后选取两个具有最低错误率的后代作为下一代的父母。在这个步骤中，利用目标函数寻找后代，寻找的后代可以最小化0-1损失函数。

重复执行一系列的GA过程直到预先确定的代数，最后在所有的代中或者最后一代中选取具有最低错误率的一个后代。GA过程的伪代码如算法1所述：

<html><body><table><tr><td>算法1GA过程伪代码</td></tr><tr><td>随机：利用十进小数生成器随机生成0到1之间的数 for 所有的代数do for 所有的后代数do for层1的所有个数do for所有后代的权重矩阵行do if 随机>交叉率 then</td></tr></table></body></html>

<html><body><table><tr><td>后代权重矩阵行←父母权重矩阵行</td></tr><tr><td>end if</td></tr><tr><td>end if</td></tr><tr><td>for所有后代权重矩阵列do</td></tr><tr><td>if 随机<突变率 then</td></tr><tr><td>后代权重矩阵元素=0</td></tr><tr><td>end if</td></tr><tr><td>end for</td></tr><tr><td>end for</td></tr><tr><td>endfor</td></tr><tr><td>利用验证集合对每个后代进行正反馈神经网络测试</td></tr><tr><td>end for</td></tr><tr><td>下一代父母←选取两个具有最低错误率的后代</td></tr><tr><td>endfor</td></tr><tr><td>在所有的代或者最后一代中选取一个具有最低错误率的后代</td></tr></table></body></html>

# 2 深度神经网络

# 2.1 多层感知器模型

采用不同的数学模型就能得到不同的神经网络方法，其中最有影响力的模型就是多层感知器（multi-layer perceptron,MLP)模型。它具有从训练数据中学习任意复杂的非线性映射的能力。图3为一个简单的多层感知器模型。

![](images/eb20a8707b52f5497529cb1d18f69b217555ec3a23ca54bcbf8843e793b126a2.jpg)  
图3多层感知器模型

神经网络是一个网络结构，它由一个个神经元链接组成。每个神经元有一个激活函数，凭借该函数，能够将输入数据压缩到指定区间，并且让原本线性的特征组合通过激活函数表现出非线性的特征。

# 2.2深度神经网络模型

深度神经网络由输入层、隐藏层和输出层三部分构成。图3就是一个深度神经网络模型的例子。顾名思义，输入层(InputLayer)就是直接获取输入的数据，其中每个单元对应一个特征，这是一个可以用于训练的显性特征。中间部分是隐藏层(HiddenLayer)，收集来自上一层输入层的全部特征进行线性组合后作为输入，带入激活函数中，得到一个输出值。在深层神经网络中，隐藏层可以有多个。并且，每个隐藏层会以前一个隐藏层的输出为函数的输入，带入本层的激活函数中。图4模型是一个包含两个隐层的深度神经网络模型。

![](images/d23d24cdb1d448b20e7ec8d3fb39b9c8b55c1bb982df4f8f1792db4d83e666b5.jpg)  
图4包含两个隐层的深度神经网络模型

输出层(outputlayer)所做的工作其实和隐藏层很相似，把上一层的输出进行线性组合后，作为输入，带入输出层的激活函数单元，便可以得到这个神经元的输出。如图3中对应的都有3个输出单元，每个输出单元用于二分类，也就是预测0或1，代表一个预测值。

深度神经网络的另一个常见的应用是特征提取。他们的实现思路非常简单。例如可以用层叠的多个受限玻尔兹曼机(restrictedBoltzmannmachine，RBM)[9]组成深度网络结构来提取音乐的特征。深度神经网络的RBM层构成如图5所示。

![](images/7fabfc84046ab19d515bb909a4707e2ac9760ecc15be518c5a920c319ffe425c.jpg)  
图5深度神经网络的RBM层

最近，一些研究者对 DNN 进行了研究[10-14]。但是，大多数研究者提出的方法主要专注于提升单个完全训练集合的识别率。本文的研究目标是对一种新颖的合并算法进行评估，本文提出算法的目的是提高DNN 的识别性能并给出一种新的用于重新训练附加数据或者类别的方法[15\~17]。

# 3 合并算法

# 3.1合并算法的流程

本文提出的算法由两个步骤构成，第一个步骤：利用两个网络各自的DNN对其进行初始化；第二个步骤：利用GA对这两个网络进行合并。将 DNN 的输入数据划分为两个数据集合：用于对网络进行训练的集合 $( S _ { \mathrm { i } \parallel \parallel \ddagger \hslash } )$ 以及测试集合 $( S _ { \mathrm { i \ " \ " } } )$ ：在测试阶段利用测试集合对网络的性能进行评估。十分关键的是不能利用 $S _ { \mathfrak { M } | \mathfrak { X } }$ 对网络进行训练。在本文提出的算法中，将$S _ { \mathrm { i } \parallel \parallel \ddagger \ddagger }$ 划分为两个子集合( $S _ { \mathrm { i } \parallel \parallel \ddag \hbar 1 }$ 和 $S _ { \mathrm { i \vert \vert \ddag 2 \vert \cdot 2 } }$ )。为了对后代的性能进行评估还需要一个验证集合( $S _ { \sharp _ { \mathbb { N } } \sharp _ { \mathbb { E } } } )$ 。两个数据集合之间的关系如下所述：

$$
\begin{array} { r l } & { S _ { \mathrm { i } \parallel | \mathcal { E } _ { \mathrm { j } } 1 } \cap S _ { \mathrm { i } \parallel | \mathcal { E } _ { \mathrm { k } } 2 } \neq \phi } \\ & { S _ { \mathrm { i } \parallel | \mathcal { E } _ { \mathrm { k } } 1 } \cap S _ { \mathrm { i } \parallel | \mathcal { E } _ { \mathrm { k } } 2 } = \phi } \\ & { S _ { \mathrm { i } \parallel | \mathcal { E } _ { \mathrm { k } } 1 } \cap S _ { \mathrm { i } \parallel | \mathcal { E } _ { \mathrm { k } } } = \phi , S _ { \mathrm { i } \parallel | \mathcal { E } _ { \mathrm { k } } 2 } \cap S _ { \mathrm { i } \parallel | \mathcal { E } } = \phi } \\ & { S _ { \mathrm { i } \underset { \mathrm { i } \neq i \mathrm { d } } { = } } \cap S _ { \mathrm { s i } \parallel | \mathcal { E } } = \phi } \end{array}
$$

其中，根据本文提出算法的目的利用公式(la)和公式(1b)对（20 $S _ { \mathrm { i } \parallel \parallel \ddag 1 }$ 和 $S _ { \mathrm { i } \parallel \parallel \ddag 2 }$ 之间的关系进行表示。公式(la)中的数据集合关系表示本文提出的算法可以用于增强 DNN 的精度，公式(1b)表示本文提出的算法可以用于向当前存在的网络中添加数据或者类别。

图6中给出了本文提出算法的流程图。首先，将 $S _ { \mathrm { i } \parallel \parallel \ddagger \hslash }$ 划分为两个子集合，此时，两个子集合中含有一些公用数据。然后，利用这两个子集合对应的DNN分别对这两个子集合进行训练。每个DNN都具有相同的网络结构，但是，网络的权重和偏差却不同，这是因为其采用了不同的训练数据集合进行训练。因此，本文将这些网络表示为网络 $\mathbf { \Sigma } _ { 1 } ^ { 0 }$ 和网络 $\mathbf { \Sigma } _ { 2 } ^ { 0 }$ ，其中下标用于对网络进行区分。在第二阶段，利用GA将两个训练所得的网络进行合并，提出的算法利用网络中已经存在的训练信息，即权重和偏差。

![](images/44c646623f1b8fada032900e950a91c487cd0dd7e1039477cf5b95be55d5653b.jpg)  
图6提出的合并算法的流程图

# 3.2 重新训练方法

本文提出的算法中也采用新的重新训练方法。在重新训练流程中，在 DNN 中将集合 $S _ { \mathrm { i } \parallel \parallel \ddag 1 }$ 训练成网络 $\mathbf { \Sigma } _ { 1 } ^ { 0 }$ ，其中含有权重矩阵和偏差向量。在合并阶段将这个网络信息作为染色体，不需要进行任何的修改。因此，在合并阶段之前需要完成的仅是利用DNN对一个附加数据进行训练。

将每个子集合训练的权重和偏差作为 DNN 的输入数据，并在合并阶段作为染色体。此外，在这个阶段发生了交叉和变异。在交叉过程中将权重和偏差作为染色体，利用每层之间的一个矩阵进行表示。矩阵的第一列对应于偏差向量，其它列构成的矩阵对应权重矩阵，因此，较低层神经元和较高层神经元之间的偏差和权重用一个矩阵行表示。

在先前学者的研究中，矩阵元素对应于特定的染色体，然而，这种对应关系并不恰当。利用一个滤波器图像表示权重矩阵的一行，因此，每个矩阵行都应该当作一个染色体。网络中染色体的选取参考图7。确定完染色体的类型之后，需要进行交叉操作。在各种交叉方法中，本文采用均匀交叉算子，这是因为这种交叉算子适用于对复杂的染色体进行交叉。

![](images/4bee3deb1a6dfd13a24bac628f9bd68196a75f8d297d001c2dea588df308a299.jpg)  
图7网络中染色体的选取

在这种算法中，随机应用显性特性和隐性特性。在部分区域或者整个区域中可以执行一次或者多次交叉操作，在本文的研究中，交叉操作仅在每个后代上执行一次，通过手动调整交叉率。重新训练方法的流程图如图8所示。

![](images/af2a75213e895b82d018e72fe3245f72cd4f9b1b44eb2ce22d4f096ee6970523.jpg)  
图8重新训练方法的流程图

第二阶段结束之后，利用验证集合记录错误(0-1损失)的个数进而完成对每个后代性能的评估。如果$f : R ^ { D } \to \{ 1 , . . . , L \}$ 表示预测函数，那么这个损失可以表示为

$$
l _ { 0 , 1 } = \sum _ { i = 1 } ^ { | S _ { \vec { y } \wedge i \vec { \parallel } } | } I _ { f ( x _ { i } ) \neq y _ { i } }
$$

其中: $D$ 表示输入维度的个数， $L$ 表示标签的个数， $x _ { i } \in R ^ { D }$ 表示维度 $D$ 第 $i$ 个数据， $y _ { i } \in \{ 1 , . . . , L \}$ 表示分配给输入信息$x _ { i }$ 的第 $i$ 个标签。指标函数 $I$ 和 $f$ 可以定义为

$$
I _ { x } = \left\{ \begin{array} { c c } { 1 } & { \hphantom { | } \mathcal { U } \mathbb { H } \mathbb { \xrightarrow { H } } x \mathcal { I } \mathbb { H } \overline { { \Xi } } } \\ { 0 } & { \hphantom { + } \overline { { \Xi } } \mathbb { H } \mathbb { 1 } \overline { { \Xi } } } \end{array} , \right.
$$

$$
f ( x ) = \arg \operatorname* { m a x } _ { k } P ( Y = k \mid x , N e t )
$$

其中：Net表示一个神经网络中的所有参数，GA的主要目的是找到使得0-1损失函数最小的 $N e t _ { u } ^ { m }$ 。因此，GA的目标函数可以表示为

$$
g ( x ) = N e t _ { \ast } ^ { m } , u = \arg \operatorname* { m i n } _ { \nu } l _ { 0 , 1 } ^ { \nu }
$$

对后代评估结束之后，选取最适合的两个后代，即 $N e t _ { 1 } ^ { m }$ 和 $N e t _ { 2 } ^ { m }$ ，其中在验证测试中下标即为级别，在合并阶段利用两个网络构成下一代。

迭代M代之后，最后选取最适合的后代 $N e t _ { 1 } ^ { N } ( N \leq M )$ 号后代网络由偏差和权重矩阵构成，将偏差和权重矩阵作为显性特征提取器。但是，这些值都不是最优的，因此，需要根据BP对其进行微调，在微调过程中还需要利用 $S _ { \mathrm { i } \parallel \parallel \ddag }$ 数据集合。

# 4 实验和结果

本章将会介绍两个不同的实验过程。首先，将提出的算法和原始的DNN的识别精度进行了对比。根据隐藏层中的神经元个数以及隐藏层的个数对提出算法的性能进行研究。实验采用了标准MNIST数据集[18]，这个集合中含有60000幅训练图像和10.000幅测试图像。其中GA的参数设定如表1所示。

表1GA的参数设定  

<html><body><table><tr><td>后代个数</td><td>300</td></tr><tr><td>交叉率</td><td>0.7</td></tr><tr><td>突变概率</td><td>0.001</td></tr><tr><td>代数</td><td>1000</td></tr><tr><td>分数比实验1</td><td>0.5</td></tr><tr><td>分数比实验2</td><td>第一代为0.2，下一代为 0.5</td></tr></table></body></html>

# 4.1合并算法的识别精度

为了对提出的算法和初始DNN 算法的性能进行比较，利用混合(MNIST)数据库进行实验。为了训练初始的DDN，本文采用了所有的60000幅训练图像。但是，当采用本文提出的算法时，将所有的 MNIST训练图像划分为两个集合，即 $S _ { \mathrm { i } \parallel \parallel \ddag \mathrm { \frac { 4 } { \hbar } } 1 }$ 和（204号 $S _ { \mathrm { i \parallel \parallel \ddag 2 } }$ ，每个集合中含有 30000 幅不同的训练图像；然后，从每个训练集合中随机提取出10000幅训练图像，将提取的10000 幅训练图像添加到其他训练集合中，每个训练集合中含有40000 幅训练图像。为了对后代进行验证，需要使用S验证。因此，要从60000 幅训练图像中随机选取出6000幅图。

图9中给出了实验中DNN算法和本文提出算法的训练和测试曲线结果。

![](images/9f15637178aee3510fda094479eaf5d87d713d1d6bebf7b18b66ba7b2b19d0ee.jpg)  
图9DNN和本文提出的合并算法的训练和测试曲线结果

如图9所示，本文提出的算法降低的错误率要低于初始版本的DNN算法。提出的算法设置了比RBM算法更加适当的初始网络参数，这些参数可以用作特征提取器。换句话说，本文提出的算法提高了预先训练的性能。

# 4.2重新训练方法的性能

接下来提出算法给出的新的重新训练方法的性能进行了研究。假设MNIST是由零到七手写数字图像构成。当新的两个类别数据添加到初始网络中时，初始版本的DNN应该预先在所有训练数据的基础上训练RBM。

但是本文提出的算法在添加新类别时，没有在所有的训练数据上对RBM进行预先训练，这是因为本文提出的算法采用了网络的偏差和权重，这些信息已经经过训练。利用本文提出的算法添加新类别的过程如下文中所述。首先，保持初始网络的偏差和权重；然后，利用DNN对新类别的训练数据进行训练，通过交叉和变异操作将新网络进行合并。采用GA进行预先训练之后，利用BP算子[19,20]对初始化后的网络进行微调。

在合并阶段存在一个限制条件，这是因为两个网络的结构不相同。在实验过程中为了解决这个问题，本文将零嵌入到初始网络顶层的行向量中，作为添加类别的个数。迭代M代之后，执行剩余的步骤，如先前所述。

为了对提出的算法性能进行评估，本文根据训练图像的数字将 MNIST 数据库划分为两个部分。 $S _ { \mathrm { i } \parallel \parallel \ddag \frac { 4 \phi _ { \mathrm { i } } } { 8 } 1 }$ 是由零到七的训练图像集合构成， $S _ { \mathrm { i } \parallel \parallel \ddag 2 }$ 是由八和九两个训练图像集合构成。此外，为了说明本文提出的算法不依赖于类别的类型，执行实验3进行0和1的添加类别。利用相应的DNN对这两个数据集合进行训练，训练结束之后，提出的算法利用两个网络的偏差和权重构成新网络。DNN和提出的算法的所有参数的设定与实验1者能够相似，根据 $S _ { \mathrm { i } \parallel \parallel \ddag \frac { 4 \xi _ { \parallel } } { 8 } 1 }$ 和 $S _ { \mathrm { i } \parallel \parallel \ddag 2 }$ 之间的个数差异设定分数比比例。在实验2中，将第一代的分数比设定为0.2，剩余代的分数比设定为0.5。实验2中DNN和提出的合并算法进行重新训练实验的训练和测试曲线结果如图10所示。可以看到实验2中的结果与实验1中的结果类似。

![](images/8165fa599c9bcae3b568c76cc549c106dd000ce3f53fc8bfe552e1dead408d3d.jpg)  
图10DNN和本文提出的合并算法进行重新训练实验的训练和测试曲线结果

实验结果表明，本文提出算法的初始错误率要低于初始版本的DNN，随着代数的增加这种现象依然持续。因此，本文提出的算法与传统的DNN算法相比可以在不对当前数据库进行RBMs重新训练的情况下以较低错误率添加新类。

# 5 结束语

本文提出了一种新颖的用于深度学习的合并算法。该算法在整个训练集合上对特征提取器进行更加适当的组合，进而组合成不同的两个独立网络；再利用DNN对两个独立网络进行初始化，进一步利用GA对两个网络进行合并；然后将网络的偏差和权重表示为每层网络间的一个矩阵；最后，利用DNN对网络的偏差和权重进行训练，并在合并过程中将矩阵中的每一行当作一个染色体。为了对提出的算法进行评估，本文执行了两种类型的实验，通过实验发现提出的算法具有比DNN更低的错误率。

实验过程中的交叉和突变操作增加了神经元节点，这样可以提高了识别性能，并且弱化了不相关和相关神经元节点。因此，提出算法的错误率更低，网络性能更优异。

在本文的研究中，试图利用提出的算法降低初始错误率并提高网络性能。此外，提出的算法还给出一种新的重新训练附加输出类的方法。因此，本文提出的算法可以作为一个基础算法进行网络分配，即可以添加数据集合或者数据类别。

# 参考文献：

[1]刘海龙，李宝安，吕学强，等．基于深度卷积神经网络的图像检索算法 研究[J].计算机应用研究,2017,34(12):3816-3819.(Liu Hailong,Li Baoan,Lv Xueqiang,et al. Image retrieval based on deep convolutional neural network [J].Application Research of Computers,2017,34(12): 3816-3819.)   
[2]刘岚，兰小毅．基于MILP 模型和QPSO 算法的绿色物流调度方法[J]. 湘潭大学学报自然科版,2018,40(1):77\~81.(Liu Lan,Lan Xiaoyi.Green logistics scheduling method based on MILP model and QPSO algorithm [J]. Natural Science Journal of Xiangtan University,2018,40 (1): 77\~81.)   
[3]刘锦怡，张乐，胡海波，等．强鲁棒性的可穿戴传感器的人体动作识别 方法[J].计算机工程与应用,2017,53(4):176-183.(Liu Jinyi,Zhang Le Hu Haibo,et al. Strong robustness human activity recognition based on wearable sensors [J]. Computer Engineering and Applications,2017,53 (4):

#

1/0-183.)   
[4] Zhang L，Wu X,Luo D. Recognizing human activities from raw accelerometer data using deep neural networks [Cl//Proc of the 14th IEEE International Conference on Machine Learning and Applic.2015: 865-870.   
[5] Kwon Y,Kang K,Bae C.Analysis and evaluation of smartphone-based human activity recognition using a neural network approach [C]// Proc of International Joint Conference on Neural Networks.2015:1-5.   
[6]Awad M, Chehdi K, Nasri A. Multicomponent image segmentation using a genetic algorithm and artificial neural network [J]. IEEE Geosci. Remote Sens. Letter,2007,4(4): 571-575.   
[7] Morris G M,G D S, Hallday R S,et al. Automated docking using a Lamarckian genetic algorithm and an empirical binding free energy function [J]. Jourmal ofComputational Chemistry,2015,19(14):1639-1662.   
[8] 张赫男，张绍文．采用改进的混合遗传算法求解高校排课问题[J].计 算机工程与应用,2015,51(5):240-246.(Zhang Henan,Zhang Shaowen. Improved hybrid genetic algorithm for university timetabling problem [J] Computer Enginering & Applications,2015,51(5): 240-246. )   
[9]Hinton G E.A practical guide to training restricted boltzmann machines [M//Neural Networks: Tricks ofthe Trade.Berlin: Springer,2012: 599-619.   
[10]候志强，戴铂，胡丹，等．基于感知深度神经网络的视觉跟踪[J]．电 子与信息学报,2016,38(7):1616-1623.(Hou Zhibo,Dai Bo,Hu Dan,et al. Robust visual tracking via perceptive deep neural network [J]. Journal of Electronics & Information Technology,2016,38(7):1616-1623.)   
[11]王坚，张媛媛．基于深度神经网络的汉语语音合成的研究[J].计算机 科学,2015,42 (s1): 75-78.(Wang Jian, Zhang Yuanyuan. Research on deep neuralnetwork based chinese speech synthesis [J]. Computer Science,2015, 42 (s1): 75-78. )   
[12] NguyenA, Yosinski J,Clune J.Deep neural networks are easily fooled: High confidence predictions for unrecognizable images [C]// Computer Vision and Pattern Recognition. 2015: 427-436.   
[13]陈国平，杜姗姗．基于深度神经网络的动态人脸识别方法及应用[J]. 微型电脑应用，2015,31(9):39-41.(Chen Guoping，Du Shanshan. Dynamic face recognition method based on deep neural network and its application [J]. Microcomputer Applications,2015,31(9): 39-41.)   
[14]张涛涛，陈丽萍，蒋兵，等．采用深度神经网络的说话人特征提取方法 [J].小型微型计算机系统,2017,38(1):142-146.(Zhang Taotao,Chen Liping.Novel method for speaker feature extraction using deep neural network[J]. Journal ofChinese Computer Systems,2017,38 (1): 142-146.)   
[15] Courbariaux M,Bengio Y,David JP.Binary connect: training deep neural networkswith binary weights duringpropagations[C]//Procof International Conference on Neural Information Processing Systems. Cambridge: MIT Press,2015: 3123-3131.   
[16]刘琮，许维胜，吴启迪．时空域深度卷积神经网络及其在行为识别上的 应用[J].计算机科学,2015,42（7):245-249.(Liu Zong,Xu Weisheng, Wu Qidi. Spatiotemporal convolutional neural networks and its application in actionrecognition[J]. Computer Science,2015,42(7): 245-249.)

[17]杨海燕，蒋新华，聂作先．基于并行卷积神经网络的人脸关键点定位方 法研究[J].计算机应用研究，2015,32(8):2517-2519.(YangHaiyan, Jiang Xinhua,Nie Zuoxian. Facial key points location based on parallel convolutional neural network [J]. Application Research of Computers，, 2015,32 (8): 2517-2519.)

[18] Song JH,An H S,Lee Sangmin. Speech//music classification enhancement for 3gpp2 smv codec based on deep belief networks[J].IEICE Trans on Fundam. Electron. Commun. Comput. Sci, 2014,97(2): 661-664.

[19]王军，刘文，程勇．基于TEEN协议和BP神经网络的WSN数据融合 模型[J].计算机应用研究,2017,34(8):2486-2489.(WangJun,Liu Wen, Cheng Yong.WSN data aggregationmodel based on TEEN protocol and BP neural network [J].Application Research of Computers,2017,34(8): 2486- 2489.)

[20]Liu Q, ZhangF,Liu M,etal.A fault prediction method based on modified Genetic Algorithm using BP neural network algorithm [C]//Proc of IEEE International Conference on Systems,Man,and Cybernetics.2017:614-619.