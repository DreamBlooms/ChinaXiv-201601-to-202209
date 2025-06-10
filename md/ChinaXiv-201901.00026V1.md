# 基于深度序列加权核极限学习的入侵检测算法

汪‧洋，伍忠东，朱婧(兰州交通大学，电子与信息工程学院，兰州 730070)

摘要：针对海量多源异构且数据分布不平衡的网络入侵检测问题以及传统深度学习算法无法根据实时入侵情况在线更新其输出权重的问题，提出了一种基于深度序列加权核极限学习的入侵检测算法(DBN-WOS-KELM算法)。该算法先使用深度信念网络DBN 对历史数据进行学习，完成对原始数据的特征提取和数据降维，再利用加权序列核极限学习机进行监督学习完成入侵识别，结合了深度信念网络提取抽象特征的能力以及核极限学习机的快速学习能力。最后在KDD99部分数据集上进行了仿真实验，实验结果表明 DBN-WOS-KELM算法提高了对小样本攻击的识别率，并且能够根据实际情况在线更新输出权重，训练效率更高。

关键词：深度信念网络；序列学习；核极限学习；样本加权；入侵检测 中图分类号：TP393.08 doi:10.19734/j.issn.1001-3695.2018.08.0653

Intrusion detection algorithm based on depth sequence weighted kernel extreme learning

Wang Yang, Wu Zhongdong, Zhu Jing (School ofElectronic &Information Engineering,Lanzhou Jiaotong University,Lanzhou 73o07o,China)

Abstract:This paper proposed a intrusion detection algorithm based on deep sequence weighting kernel limit learning (DBN-WOS-KELM)to solve the problem of massive multi-source heterogeneous network intrusion detection with unbalanceddata distributionand the problem that thetraditional dep learning algorithmcannot update itsoutput weight online accordingtothereal-time intrusion situation.Thealgorithm firstusesthe deep belief network DBN to studythe historicaldatathen extracts thefeaturesof theoriginaldataandreduces the dimensionofthe data,and thenuses the weightedsequence kernel extreme learning machine forsupervised learning to complete the intrusion detection.Itcombines the abilityof extracting Abstractfeatures from the dep belief network andthe fastlearningabilityofthe kernel extreme learning machine.Finaly,the simulation experiments on KDD99 dataset show that DBN-WOS-KELM algorithm improves therecognitionrateofsmallsampleattacks,andcanupdate theoutput weights online according totereal-time situation,so that the training efficiency is much higher.

Key words: deep belief network;sequence learning; kernel extreme learning;sample weighting; intrusion detection

# 0 引言

入侵检测技术是信息网络领域不可缺少的部分，随着人工智能技术的不断深入，深度学习算法相对于传统的机器学习入侵检测算法具有识别率高，误报率低的优势，在入侵检测领域应用广泛。高妮等人[提出了深度信念网络的入侵检测算法,Ambusaidi等人[2]提出了基于DBN-SVM的混合入侵检测算法，逯玉婧、杨昆朋[3,4提出了基于深度学习的混合入侵检测模型，得到的实验结果在准确率和误报率上均优于传统的机器学习入侵检测算法。但是现阶段学习算法未考虑到参与训练的网络历史入侵数据分布的不平衡性，只强调了高检测率和低误报率，导致了小样本攻击类别大部分被识别为大样本攻击类别，对小样本攻击类别的检测准确率不高。针对此类不平衡数据的学习分类问题，Zong等人[5提出了加权极限学习算法处理不平衡数据。Mirza在研究了序列学习的优势，提出了加权在线极限学习机的不平衡数据学习算法以及加权的序列核极限学习算法[67],实验结果表明小样本数据识别大幅度增加。本文针对网络入侵数据的多源异构以及各攻击类别的分布不平衡特性以及传统深度学习算法无法根据实时入侵数据在线更新其输出权重的问题，对深度信念网络和序列核极限学习机进行了深入研究，提出了基于DBN-WOS-KELM的入侵检测算法，该算法充分利用了DBN提取数据特征的能力和序列核极限学习机的泛化能力。最后通过KDD99部分数据集进行有效评估，实验结果表明，本文算法不仅提高了对小样本攻击的检测率，还能根据实际情况在线更新分类器参数，进一步提高了训练效率。

# 1 DBN-WOS-KELM入侵检测模型

# 1.1方法总体架构

本文提出了DBN-WOS-KELM的入侵检测算法，总体框架如图1所示，具体步骤如下：

a)数据预处理。将网络数据中的字符特征转换成对应的二进制数据，再均值化到[0,1]。

b)DBN抽象特征提取。分为RBM的无监督预训练以及BP微调全局，对网络数据进行降维。

c)WOS-KELM分类器识别入侵。将降维后的数据打上数据标签作为可靠数据并进行样本加权，通过KELM的序列学习，学习完成后取代BP作为分类器。

d)DBN-WOS-KELM识别入侵。将网络历史入侵数据降 $W \longleftarrow W + \varepsilon ( p ( h _ { 1 } = 1 \vert \nu _ { 1 } ) \nu _ { 1 } ^ { T } - p ( h _ { 2 } = 1 \vert \nu _ { 2 } ) \nu _ { 2 } ^ { T } )$ 隹后进行样本加权后进行入侵检测，识别出其入侵类型。 $c  c + \varepsilon ( \nu _ { 1 } - \nu _ { 2 } )$ （20b← e+e（p(h-=1+v）-pth=1|v))步骤2)DBN数据降维 步骤3)WOS-KELM分类器2）权值微调(数据分块)TO…· 实际标签 为使整个DBN 网络达到全局最优,通过BP 网络利用少Y ： 1 期望标签 Error 量真实可靠的标数据微调各RBM参数，将预测值与实 确定样本的惩罚矩阵 将误差传播至每一层，具体步骤如算法2所示确定KELM始输出权重 1训练 算法2反向传播算法。。··。BP 输入：预训练后的DBN参数 $\theta = \{ W \} _ { 1 } ^ { ' } b , c \}$ ,训练样本 $< \nu _ { i } \ , t _ { i } >$ ，NSL-KDD数据集 W3Tc3 dW1dc1 RBM3算法 最大迭代次数T1 。 …。。 输出：微调的DBN参数 $\boldsymbol { \theta } \mathbf { \lambda } = \{ \boldsymbol { W } , \boldsymbol { \dot { b } } , \boldsymbol { c } \}$ 。步处理 W2c2 dW2dc2 RBM2 检测训练阶设：计DB的重构输出，反向传播误√ 。.·… 88 差；数据归一化 1 对每个输出单元计算吴差δkW1c1 dW3 dc3 RBM1 入侵类型识别V）(v-Vk）i↓ ·。。·· 0 对每个隐藏层单元计算误差6 1标准化数据集 L 预训练 微调权值 降维数据集N 正常 DOS U2R R2L ProbeS=v（l-） -0kh8kk∈outputs

图1 DBN-WOS-KELM总体框架

# 1.2DBN 特征降维

深度信念网络是一种由多层RBM和一层BP网络构成的生成性深度结构，最先由Hinton 提出[8]，如图1步骤b）所示，其训练过程可分解如下两步：

# 1)RBM预训练

RBM的结构如图2所示，分为输入层和隐藏层两层。其参数为 $\theta = \{ W , b , c \}$ □

![](images/44ed22aafb60a1efc5051da9df1413922cfd3f1c8f48eaf76f05d0b3d8c70bdd.jpg)  
Fig.1The overall framework of DBN-WOS-KELM   
图2RBM结构模型  
Fig.2The structural model of RBM

其中 $b$ 是输入层到隐藏层的偏置， $\mid c \mid$ 是隐藏层到输入层的偏置， $W$ 是可见层到隐藏层节点的连接权重矩阵， $\nu _ { i }$ 和 $h _ { j }$ 是分别表示两层神经元的状态。RBM的训练算法是Hinton提出的对比散度学习算法[9][0]，算法过程如下：

算法1对比散度学习算法

输入：训练样本 $x _ { 0 }$ ；隐藏层神经元个数 $m$ ；学习率 $\varepsilon$ ；最大迭代次数 $T$ 。

输出：RBM参数 $\theta = \{ W , b , c \}$ 。

训练阶段： $\nu _ { 0 } = x _ { 0 }$ ；随机初始化 $\theta$

对所有隐藏层单元：  
计算 $p ( h _ { 1 j } = 1 | \nu _ { 1 } ) = \sigma ( b _ { j } + \sum _ { i } \nu _ { 1 i } W _ { i j } )$   
从条件分布 $p ( h _ { 1 j } = 1 | \nu _ { 1 } )$ 中抽取 $h _ { 1 j } \in ( 0 , 1 )$   
对所有可见层单元：  
计算 $p ( \nu _ { 2 i } = 1 | h _ { 1 } ) = \sigma ( c _ { i } + \sum _ { i } W _ { i j } h _ { 1 j } )$   
从条件分布 $p ( \nu _ { 2 i } = 1 | h _ { 1 } )$ 中抽取 $\nu _ { 2 i } \in ( 0 , 1 )$   
对所有隐藏层单元：  
计算 $p ( h _ { 2 j } = 1 | \nu _ { 2 } ) = \sigma ( b _ { j } + \sum _ { i } \nu _ { 2 i } W _ { i j } )$   
更新参数：

更新参数：

$$
\theta _ { j i } = \theta _ { j i } + \Delta \theta _ { j i }
$$

其中 $\Delta \theta _ { j i } = \eta \delta _ { j } x _ { j }$ ， $\eta$ 为学习率。

# 1.3WOS-KELM分类器

加权序列和极限学习机(WOS-KELM)[7是加权序列学习算法与加权核极限学习机算法(WKELM)[5]的结合，由 ShuyaDing等人提出。与序列核极限学习机(OS-KELM)[1I类似，训练过程分成初始化阶段和序列学习阶段两个阶段。

# 1)初始化阶段

WOS-KELM的初始化阶段与WELM学习算法类似，首先选择初始训练数据 $n _ { 0 } = ( x _ { i } , t _ { i } ) i = 1 , . . . , N _ { 0 }$ 。确定隐藏层初始化输出矩阵为

$$
\beta ^ { ( 0 ) } = ( H _ { 0 } H _ { 0 } ^ { T } + \frac { W _ { 0 } ^ { - 1 } } { C } ) ^ { - 1 } T _ { 0 } = R _ { 0 } T _ { 0 }
$$

$$
R _ { 0 } = ( H _ { 0 } H _ { 0 } ^ { T } + \frac { W _ { 0 } ^ { - 1 } } { C } ) ^ { - 1 }
$$

$$
W _ { 1 } ^ { - 1 } = d i a g \left( \frac { 1 } { w _ { 1 } ^ { 1 } } \quad \frac { 1 } { w _ { 2 } ^ { 1 } } \quad \cdots \quad \frac { 1 } { w _ { N _ { 0 } } ^ { 1 } } \right)
$$

定义 $H _ { 0 } H _ { 0 } ^ { T } = \Omega _ { E L M }$ ， $\Omega _ { E L M i j } = K ( x _ { i } , x _ { j } )$ ， $K ( x , y )$ 为核函数， $T _ { 0 }$ 为样本标签矩阵， $c$ 为正则化系数， $W _ { 0 }$ 为第一批训练样本的权重矩阵，文献[7]给出了 $W$ 的计算方法

$$
W _ { k } = d i a g \left( w _ { k , 1 } \quad w _ { k , 2 } \quad \cdots \quad w _ { k , N _ { k } } \right)
$$

$$
\textit { w } _ { k , i } { = } 1 / m _ { i }
$$

式(4)中 ${ N } _ { k }$ 表示训练样本的数量， $x _ { k , i }$ 表示第 $k$ 条属于第 $i$ 类标签的训练样本， $m _ { i }$ 表示训练数据中第 $i$ 类标签的样本数目。

2)序列学习阶段

当第一批训练数据 $n _ { 1 } = ( x _ { i } ^ { 1 } , t _ { i } ^ { 1 } )$ ， $i = 1 , 2 , . . . , N _ { 1 }$ 参与训练时，更新核极限学习机的输出矩阵 $\beta ^ { \left( 0 \right) }$ 为

$$
\beta ^ { ( 1 ) } = \left[ \begin{array} { c c } { { H _ { 0 } H _ { 0 } ^ { T } + \displaystyle \frac { W _ { 0 } ^ { - 1 } } { C } } } & { { H _ { 0 } H _ { 1 } ^ { T } } } \\ { { H _ { 1 } H _ { 0 } ^ { T } } } & { { H _ { 1 } H _ { 1 } ^ { T } + \displaystyle \frac { W _ { 1 } ^ { - 1 } } { C } } } \end{array} \right] ^ { - 1 } \left[ \begin{array} { c } { { T _ { 0 } } } \\ { { T _ { 1 } } } \end{array} \right]
$$

$$
W _ { 1 } ^ { - 1 } = d i a g \left( \frac { 1 } { w _ { 1 } ^ { 1 } } \quad \frac { 1 } { w _ { 2 } ^ { 1 } } \quad \cdots \quad \frac { 1 } { w _ { N _ { 0 } } ^ { 1 } } \right)
$$

定义 $K _ { 0 } = H _ { 0 } H _ { 0 } ^ { T }$ ， $K _ { 0 } ^ { ' } = H _ { 0 } H _ { 1 } ^ { T }$ ， $K _ { 0 } ^ { * } = H _ { 1 } H _ { 1 } ^ { T }$ ，则

$$
\begin{array}{c} \begin{array} { l } { R _ { 1 } = [ \begin{array} { c c } { K _ { 0 } + \displaystyle \frac { W _ { 0 } ^ { - 1 } } { C } } & { K _ { 0 } ^ { ' } } \\ { \displaystyle ( K _ { 0 } ) ^ { T } } & { K _ { 0 } ^ { ' } + \displaystyle \frac { W _ { 1 } ^ { - 1 } } { C } } \end{array} ] } \\ { = [ \begin{array} { c c } { R _ { 0 } } & { \displaystyle { O _ { N _ { 0 } , N _ { 1 } } } } \\ { O _ { N _ { 1 } , N _ { 0 } } } & { O _ { N _ { 1 } , N _ { 1 } } } \end{array} ] + [ \begin{array} { c } { - R _ { 0 } K _ { 0 } ^ { ' } } \\ { I _ { N _ { 1 } } } \end{array} ] } \\ { \displaystyle \times ( K _ { 0 } ^ { ' } + \displaystyle \frac { W _ { 1 } ^ { - 1 } } { C } - ( K _ { 0 } ^ { ' } ) ^ { T } R _ { 0 } K _ { 0 } ^ { ' } ) [ ( - R _ { 0 } K _ { 0 } ^ { ' } ) ^ { T }  } \end{array}  ~ I _ { N _ { 1 } } ]  \end{array}
$$

式(8)中 $O _ { m , l }$ 表示 $m \times l$ 阶零矩阵， $I _ { { \scriptscriptstyle m } }$ 代表 $m \times m$ 阶单位矩阵。

当第 $k { + } 1$ 批训练数据参与训练时，

$$
\begin{array} { c } { { R _ { k + 1 } = \left[ O _ { N _ { k } } O _ { N _ { k } , N _ { k + 1 } } \right] + \left[ \begin{array} { c } { { - R _ { k } K _ { k } ^ { ^ { \prime } } } } \\ { { I _ { N _ { k + 1 } } } } \end{array} \right] \times } } \\ { { ( K ^ { ^ { \prime } } { _ k } + \displaystyle \frac { W _ { k + 1 } ^ { - 1 } } { C } - ( K _ { k } ^ { ^ { \prime } } ) ^ { T } R _ { k } K _ { k } ^ { ^ { \prime } } ) ^ { - 1 } \left[ ( - R _ { k } K _ { k } ^ { ^ { \prime } } ) ^ { T } I _ { N _ { k + 1 } } \right] } } \end{array}
$$

$$
R _ { k } = ( K _ { k } + \frac { W _ { k } ^ { - 1 } } { C } ) ^ { - 1 }
$$

为了表达简便，定义

$$
Q _ { k + 1 } = - R _ { k } K { ^ { \prime } } _ { k }
$$

$$
\mu _ { k + 1 } = ( K ^ { \cdot } { } _ { k } + { \frac { W _ { k + 1 } ^ { - 1 } } { C } } ) + ( K ^ { \cdot } { } _ { k } ) ^ { T } Q _ { k + 1 }
$$

将式(11)(12)代入式(9)中得到

$$
\begin{array}{c} \begin{array} { c } { { R _ { k + 1 } = \left[ \begin{array} { c c } { { R _ { k } } } & { { O _ { N _ { k } , N _ { k + 1 } } } } \\ { { O _ { N _ { k + 1 } , N _ { k } } } } & { { O _ { N _ { k + 1 } , N _ { k + 1 } } } } \end{array} \right] + \left[ \begin{array} { c } { { Q _ { k + 1 } } } \\ { { I _ { N _ { k + 1 } } } } \end{array} \right] } } \\ { { \times ( \mu _ { k + 1 } ) ^ { - 1 } \left[ Q _ { k + 1 } ^ { T } \right]} & { { I _ { N _ { k + 1 } } } } \end{array}  }  \end{array}
$$

最后得到第 $k { + } 1$ 批次输出矩阵的更新

$$
\beta ^ { ( k + 1 ) } = R _ { k + 1 } \left[ { \check { T } } _ { k } \right]
$$

$$
\breve { T _ { k } } = \left[ T _ { 0 } \quad \cdots \quad T _ { k } \right] ^ { T }
$$

将式(14)(15)代入式(13)中得到

$$
\beta ^ { ( k + 1 ) } = \left[ \begin{array} { c } { \beta ^ { ( k ) } + Q _ { k + 1 } ( \mu _ { k + 1 } ) ^ { - 1 } ( T _ { k + 1 } - ( K ^ { \ast } _ { k } ) ^ { T } \beta ^ { ( k ) } ) } \\ { ( \mu _ { k + 1 } ) ^ { - 1 } ( T _ { k + 1 } - ( K ^ { \ast } _ { k } ) ^ { T } \beta ^ { ( k ) } ) } \end{array} \right]
$$

# 2 实验

# 2.1数据集预处理

本次实验采用的数据集是KDD99 数据集[12]，数据集将异常类型分成了四大类，分别是DOS、R2L、U2R、Probe，含有39种攻击方式。训练集中包含了22种攻击方式，测试集中还包含了17种训练集中未出现的攻击方式（实验未使用)。

数据集有41维特征，其中包含了字符型和数字型，在训练和检测前先进行预处理，首先将字符数据转换成二进制向量。例如标签类型normal、DOS、R2L、U2R、Probe表示为[0,0,0,0,1]、[0,0,0,1,0]、[0,0,1,0,0]、[0,1,0,0,0]、[1,0,0,0,0]。字符数据映射完成之后进行数据均值化处理，将各维数据归一化到0到1之间，转换公式如下：

$$
y = { \frac { y - M I N } { M A X - M I N } }
$$

# 2.2 实验评价标准

传统的入侵检测算法通常强调整体高准确率，以及低误报率，忽略了小样本攻击的检测，本文实验除采用准确率AC以及误报率FA作为各类攻击检测评价标准以外，还采用几何平均数 $G _ { m e a n }$ [13]作为整体检测结果的评价标准，如式(18)\~(20)所示。

$$
A C = { \frac { T _ { p } + T _ { N } } { T _ { p } + T _ { N } + F _ { p } + F _ { N } } }
$$

$$
F A = \frac { F _ { p } } { T _ { N } + F _ { p } }
$$

$$
G _ { m e a n } = ( \prod _ { j = 1 } ^ { q } \frac { s _ { j j } } { s _ { j } } ) ^ { \frac { 1 } { q } }
$$

其中： $T _ { \scriptscriptstyle N }$ 表示正常样本正确分类的个数， $T _ { P }$ 表示攻击样本正确分类的个数， $\boldsymbol { F } _ { p }$ 表示正常样本误报为攻击的个数， $F _ { N }$ 表示攻击样本误报为正常的个数， $s _ { j }$ 表示第 $j$ 类攻击样本总数，$s _ { j j }$ 表示检测准确的 $j$ 类攻击数， $q$ 表示样本类别数,实验数据共5类，故 $q$ 取值为5。

# 2.3实验参数设置

本文所提出的模型中，DBN作为数据降维的部分，其网络层数的设定至关重要，因此实验前必须确定其深度。实验中预设了5种DBN结构(i表示网络的层数)，分类器使用BP网络，其节点参数如表1所示，从KDD99的训练集中抽取$20 \%$ ，测试集中抽取10000条数据，得到各类攻击样本检测情况，根据式(20)计算出各网络深度下的 $G _ { m e a n }$ ，根据 $G _ { m e a n }$ 最大原则选用 $D B N ^ { 4 }$ (如图3中虚线所示)，具体检测结果如图3。

KELM的参数 $( \gamma , C )$ 设定为 $( 2 ^ { 1 } , 2 e ^ { 6 } )$ ，核函数为高斯核函数，如式（21）所示。

$$
K ( x , x _ { i } ) = \exp ( - \gamma \| x - x _ { i } \| ^ { 2 } ) , \gamma > 0
$$

Table1 DBN parameter   

<html><body><table><tr><td>网络深度</td><td>节点参数</td></tr><tr><td>DBN1</td><td>122-30</td></tr><tr><td>DBN2</td><td>122-100-30</td></tr><tr><td>DBN3</td><td>122-100-70-30</td></tr><tr><td>DBN4</td><td>122-110-100-60-30</td></tr><tr><td>DBN5</td><td>122-110-100-70-50-30</td></tr><tr><td>DBN6</td><td>122-110-100-80-60-40-30</td></tr></table></body></html>

![](images/ab5555985dbc734ea47f9a46eedc465c571c7f882485579326c2d2a142e3f73d.jpg)  
图3不同DBN深度下的检测结果  
Fig.3Test results at different DBN depths

# 2.4实验结果

# 2.4.1DBN-WKELM实验

为验证不同训练集分布情况下的检测情况，本次实验从训练集中抽取了4组不同样本分布的训练子数据集，从测试集中抽取5000条，分别讨论了DBN，DBN-KELM，以及改进后DBN-WKELM三种算法对5种攻击的检测情况以及检测结果的 $G _ { m e a n }$ 。实验数据分布情况如表2所示。

表1 DBN参数  
表2训练数据分布  
Table 2Training data distribution   

<html><body><table><tr><td></td><td>Normal</td><td>DOS</td><td>U2R</td><td>R2L</td><td>Probe</td></tr><tr><td>数据集1</td><td>2650</td><td>2150</td><td>10</td><td>140</td><td>400</td></tr><tr><td>数据集2</td><td>3000</td><td>2500</td><td>11</td><td>200</td><td>350</td></tr><tr><td>数据集3</td><td>2000</td><td>3000</td><td>8</td><td>180</td><td>500</td></tr><tr><td>数据集4</td><td>1200</td><td>1200</td><td>11</td><td>200</td><td>1500</td></tr></table></body></html>

各攻击样本的检测情况如表3\~6所示，据式(20)计算出样本检测结果的 $G _ { m e a n }$ ，结果如图4所示。实验结果表明DBN-KELM算法比原始的DBN算法检测率高，对训练样本加权过后的算法DBN-WKELM算法在尽可能少的牺牲的大样本攻击类型的检测率，提高了对小样本类型攻击的检测率，在4个训练子数据集下检测结果的几何平均数 $G _ { m e a n }$ 均优于另外两种算法，弥补了传统入侵检测算法对大样本攻击类型识别率高而对小样本攻击识别率低的缺陷。

<html><body><table><tr><td colspan="6">Table 3 Test result of data set 1</td></tr><tr><td>算法</td><td>Normal</td><td>DOS</td><td>U2R</td><td>R2L</td><td>1% Probe</td></tr><tr><td>DBN</td><td>95.93</td><td>95.90</td><td>55.00</td><td>78.72</td><td>88.52</td></tr><tr><td>DBN-KELM</td><td>95.58</td><td>95.32</td><td>52.50</td><td>81.63</td><td>92.85</td></tr><tr><td>DBN-WKELM</td><td>95.54</td><td>95.43</td><td>64.00</td><td>88.31</td><td>93.76</td></tr><tr><td></td><td>表4</td><td>数据集2检测结果</td><td></td><td></td><td>%</td></tr><tr><td>算法</td><td>Table 4 Normal</td><td>DOS</td><td>Test result of data set 2 U2R</td><td>R2L</td><td>1% Probe</td></tr><tr><td>DBN</td><td>95.87</td><td>96.19</td><td>67.50</td><td>82.10</td><td>87.24</td></tr><tr><td>DBN-KELM</td><td>95.90</td><td>96.38</td><td>67.50</td><td>81.48</td><td>94.44</td></tr><tr><td>DBN-WKELM</td><td>95.44</td><td>95.82</td><td>83.50</td><td>90.52</td><td></td></tr><tr><td></td><td>表5</td><td>数据集3检测结果</td><td></td><td></td><td>90.62</td></tr><tr><td></td><td>Table 5</td><td>Test result of data set 3</td><td></td><td></td><td>1% 1%</td></tr><tr><td>算法</td><td>Normal</td><td>DOS</td><td>U2R</td><td>R2L</td><td>Probe</td></tr><tr><td>DBN</td><td>95.25</td><td>97.01</td><td>62.50</td><td>81.59</td><td>88.43</td></tr><tr><td>DBN-KELM</td><td>95.18</td><td>97.73</td><td>69.00</td><td>82.61</td><td>94.30</td></tr><tr><td>DBN-WKELM</td><td>93.95</td><td>95.88</td><td>74.50</td><td>93.28</td><td>95.00</td></tr><tr><td></td><td>表6</td><td>数据集4检测结果</td><td></td><td></td><td>1%</td></tr><tr><td></td><td>Table 6</td><td>Test result of data set 4</td><td></td><td></td><td>1%</td></tr><tr><td>算法</td><td>Normal</td><td>DOS</td><td>U2R</td><td>R2L</td><td>Probe</td></tr><tr><td>DBN</td><td>94.67</td><td>94.97</td><td>64.00</td><td>87.15</td><td>94.18</td></tr><tr><td>DBN-KELM</td><td>95.15</td><td>95.16</td><td>71.50</td><td>86.56</td><td>96.32</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>DBN-WKELM</td><td>93.94</td><td>94.85</td><td>85.00</td><td>90.49</td><td>94.88</td></tr></table></body></html>

表3数据集1检测结果  

<html><body><table><tr><td>攻击样本</td><td>Normal</td><td>DOS</td><td>U2R</td><td>R2L</td><td>Probe</td></tr><tr><td>数据含量</td><td>568</td><td>330</td><td>3</td><td>25</td><td>75</td></tr></table></body></html>

图4不同训练数据下的 $G _ { m e a n }$ 对比  
![](images/4a2e151a2991c84e9d956ce2f3fd74129768ed1b82f881273ffb0f04f2a29e83.jpg)  
Fig.4Comparison of $G _ { m e a n }$ under different training data

2.4.2DBN-WOS-KELM实验

本次实验中从KDD99的训练集抽取了8000条数据并分成8个数据块，从测试集中抽取了5000条数据（不含未知攻击形式)，训练过程中将各个数据块经过DBN 降维后送入序列核极限学习机(WOS-KELM)中训练，依次更新核极限学习机的输出权重 $\beta ^ { ( i ) }$ ，模拟现实入侵检测系统在线更新过程，各数据块的数据含量相同，具体分布情况如表7所示。训练集中U2R含量较少，采取自我复制的方法。

图5给出了随着训练批次增加各个攻击类型的检测变化情况，以及检测结果的 $G _ { m e a n }$ 的变化情况。实验结果表明随着训练批次的增加，各类攻击样本的检测率逐渐趋于稳定，检测结果的 $G _ { m e a n }$ 也依次增加，但增加的速率逐渐降低，分类器逐渐稳定。证明了本文所提出的DBN-WOS-KELM算法的有效性。

图6给出了DBN-WOS-KELM算法与DBN-WKELM算法在相同数据量下的训练时间曲线。实验结果表明在同等数据量的情况下DBN-WOS-KELM算法的训练效率明显优于DBN-WKELM算法。

![](images/ed05487fc3191e0a657939dc2f7f071e8bbc45080c78cf7eb1cca5344c751652.jpg)  
图5DBN-WOS-KELM检测情况

表7批量数据分布情况 $1 \%$ Table 7The distribution of batch data $1 \%$   
Fig.5Detection situation ofDBN-WOS-KELM   

<html><body><table><tr><td>第一作者</td><td>导师/通信作者</td></tr><tr><td>姓名：汪洋</td><td>姓名：伍忠东</td></tr><tr><td>手机：15775137823</td><td>手机：13893455533</td></tr><tr><td>邮箱:1176601898@qq.com</td><td>邮箱：WUZHD@mail.lzjtu.cn</td></tr><tr><td>详细通信地址</td><td>邮编</td></tr><tr><td>甘肃省兰州市安宁区安宁西路88号 兰州交通大学</td><td>730070</td></tr></table></body></html>

![](images/e564bb93ca05118c43f75cf0ec9558ffc297a1c21548ebbc68cd6b1313d2915c.jpg)  
图6DBN-WKELM与DBN-WOS-KELM训练时间Fig.6Training time of DBN-WKELMand DBN-WOS-KELM

# 3 结束语

本文针对海量多源异构且数据分布不平衡的网络入侵检测问题以及传统深度学习算法无法根据实时入侵数据在线更新其输出权重的问题，提出了一种深度序列加权核极限学习的入侵检测算法(DBN-WOS-KELM 算法)。该算法结合了

DBN特征提取和KELM快速学习的优势，不但通过样本加权解决了数据分布不均衡下的训练问题，在尽可能低地降低大样本攻击类别的识别率的前提下提高了对小样本攻击的识别率，而且能够在新的训练数据到来时在原输出权重的基础上在线更新其输出权重。最后在KDD99 部分数据集上进行了实验，实验结果表明DBN-WOS-KELM算法不仅对各类型的攻击达到了较高的识别率，还能根据实际情况在线更新其输出矩阵，在同等数据量大小的情况下，训练效率优于DBN-WKELM算法。但本文仅仅使用了KDD99 部分数据集验证了算法的可行性，下一步将考虑使用本文算法解决现实生活中的入侵检测问题。

# 参考文献：

[1]Gao Ni,Gao Ling,He yiyue,et al. Intrusion detection model based on deep belief network [J].Journal of Southeast University:English Edition, 2015,31(3):339-346.)   
[2]Ambusaidi M A,He Xiangjian,Nanda P,et al.Building an intrusion detection system using a filter-based feature selection algorithm [J]. IEEE Trans on Computers,2016,65(10):2986-2998.   
[3]杨昆朋，基于深度学习的入侵检测[D].北京:北京交通大学，2015. (Yang Kunpeng. Intrusion detection based on deep learning [D]. Beijing: Beijing JiaotongUniversity,2015.)   
[4]逐玉婧.基于深度信念网络的入侵检测算法研究[D].石家庄：河北 师范大学,2O16.(Lu Yujing.Research on intrusion detection algorithm based on deep belief network [D].Shijiazhuang:Hebei Normal University,2016.)   
[5]Zong Weiwei,Huang Guangbin,Chen Yiqiang.Weighted extreme learning machine for imbalance learning [J].Neurocomputing,2013, 101: 229-242.   
[6]Mirza B,Lin Zhiping,Toh K A.Weighted online sequential extreme learning machine for class imbalance learning [J].Neural processing letters,2013,38(3):465-486.   
[7]Ding Shuya,Mirza B,Lin Zhiping,et al.Kernel based online learning forimbalance multiclass classification [J].Neurocomputing,2O18,277: 139-148.   
[8]Hinton G E,Osindero S,Teh YW.A fast learning algorithm for deep belief nets [J].Neural computation,2006,18(7):1527-1554.   
[9]Hinton G E.Training products of experts by minimizing contrastive divergence [J].Neural computation,2002,14(8): 1771-1800.   
[10]Hinton G E.A practical guide to training restricted Boltzmann machines [M]//Neural networks: Tricks of the trade.Berlin:Springer,2012: 599-619.   
[11]Deng WanYu,OngY S,TanP S,et al.Online sequential reduced kernel extreme learning machine [J].Neurocomputing,2O16,174:72-84.   
[12] Dhanabal L,Shantharajah S P. A study on NSL-KDD dataset for intrusion detection system based on classification algorithms [J]. International Journal of Advanced Research in Computer and Communication Engineering,2015,4(6): 446-452.   
[13]Al Helal M,Haydar M S,Al Mostafa S M..Algorithms efficiency measurement on imbalanced data using geometric mean and cross validation [C]//Proc of International Workshop on Computational Intelligence.Piscataway,NJ: IEEE Press,2O16:110-114.