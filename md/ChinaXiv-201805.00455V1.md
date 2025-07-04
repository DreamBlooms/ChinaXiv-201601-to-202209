# 网络攻击检测的门控记忆网络方法

王家宝，徐伟光，周振吉，李阳，苗壮(陆军工程大学，南京 210007)

摘要：针对互联网大规模网络攻击检测难题，结合词向量特征表示与循环神经网络，提出了一种门控记忆网络检测方法。该方法首先将网络请求数据转换为低维实值向量序列表示，然后利用门控循环神经网络的长时记忆能力提取请求数据的特征，最后采用逻辑斯特回归分类器实现了对网络攻击的自动检测。在CSIC2010 公开数据集上，达到了 $9 8 . 5 \%$ 的10折交叉验证F1分数。与传统方法相比，较大幅度地提高了网络攻击检测的准确率和召回率。所提方法可自动检测网络攻击，具有良好的检测效果。

关键词：网络攻击检测；低维实值向量表示；门控循环神经网络中图分类号：TP393.08 doi:10.3969/j.issn.1001-3695.2018.01.0169

# Gated memory network approach for Web attack detection

Wang Jiabao, Xu Weiguang, Zhou Zhenji, Li Yang, Miao Zhuang (Army Engineering University ofPLA,Nanjing21oo07,China)

Abstract: To solve theproblemoflarge-scale network atack detection,this paper proposedagated memory network method, basedonwordvectorfeaturerepresentationandrecurrentneuralnetwork.Firstly,theproposedmethodtansformedthenetwork requestdataintolow-dimensionreal-valuevectorsequencerepresentation.Andthen,itextractedthefeaturesofrequestdataby using the memoryabilityofgatedrecurent neural ntwork.Finally,itadopted the logisticregressonclasifier toachieve automatic detection of network attack. On the CSIC2010 public data set,this method achieves $9 8 . 5 \%$ 10-fold cross-validation F1-score.Comparing with traditional methods,itcanefectively improve the precisionandrecallrates fordetecting network attack. The proposed method can detect network attacks automatically and has good detection results.

KeyWords: network atack detection; low-dimensionreal-value vector representation; gated recurrent neural networks

# 0 引言

随着互联网规模的不断发展，网络攻击已成为各国安全部门和企业面临的重大问题。由于网络攻击手段多样、类型各异，且极易变种，导致对网络攻击的检测也面临着巨大困难。针对互联网大规模的网络通信行为，如果能够自动地判断通信行为的恶意性，则可以有效地避免网络攻击行为产生的破坏及其可能的次生灾害。目前，针对网络攻击行为的检测主要分为基于模式匹配的检测和基于模式分类的检测[1。前者是当前大多数网络安全软件的主要手段，即通过模式匹配或统计分析判断系统或网络日志中的不正常行为，如登录不期望的位置、访问未授权文件、网络流量异常、程序行为异常等[2]。该类检测方法通常是在攻击行为发生或事后进行的检测，无法在事前和事中进行预先检测判断。后者通常先可对通信内容提取特征[3]，再利用分类器直接进行检测。该类方法可直接针对网络通信流数据进行，对发现的异常通信数据直接处理或丢弃，避免攻击行为对主机造成影响。

基于模式分类的检测方法是本文研究的重点。目前该方法主要是借鉴文本分类技术，通过提取内容的描述特征，将网络攻击检测问题转换为模式分类问题进行处理。其中特征表示方法主要包括词袋（Bag-of-Words)表示[4]、TF-IDF表示[5]、n-gram表示[]；分类检测方法主要包括贝叶斯[7]、决策树[8]、支持向量机[9,10]、多层感知机[11,12]、K-近邻[13]等经典机器学习方法。

近年来，随着深度学习的发展，特征表示与分类识别研究内容均得到了新发展。在文本特征表示方面，谷歌研究组提出的word2vec 模型能够将传统高维的one-hot词向量表示转换为低维实值向量表示，改变了文本词的表达能力，使得词与词之间可以度量距离（相似度）[14,15]。该特征表示在情感分类方面得到了很好的应用[1]，但主要限于与文本词内容的相关研究。对于网络通信而言，基于网络协议的通信请求是由字符串组成的流序列，可以被转换为文本词序列以低维实值向量序列进行表示。同时，对于产生的序列数据，循环神经网络（recurrentneuralnetwork,RNN）和门控循环神经网络（gatedRNN）具有良好的建模能力，并在文本分类[17]、入侵检测[18]、机器翻译[19]等领域得到了广泛应用。

受低维实值词向量模型[14,15]和门控循环网络模型[19,20]的启发，本文提出了一种网络攻击检测的门控记忆网络方法。该方法中，基于HTTP网络通信的请求内容被表示为低维实值向量序列，增强了数据的特征表示能力；同时，具有长时记忆能力的门控循环神经网络模型被用于建模序列中长间隔的词间关系，有效提升了分类检测效果。与传统方法相比，在CSIC2010公开数据集上，所提门控记忆网络方法较大幅度地提高了网络攻击检测的准确率和召回率。

# 1 网络攻击检测的门控记忆网络方法

# 1.1门控记忆网络方法的流程框架

图1是所提出网络攻击检测的门控记忆网络方法的流程框架。其中，攻击用户通过Web协议发出攻击请求，该请求数据是网络攻击检测的原始数据。

![](images/05db38afea2c285f2fda7c8adb328c470f704aba87a840f0201641ffe92b3df9.jpg)  
图1网络攻击检测的门控记忆网络方法流程框架  
图2HTTP网络协议攻击数据的低维实值特征表示过程

该流程框架中，首先从网络交换机抓取并解析数据包；然后解析后数据，经过低维实值特征表示转变为门控记忆网络模型的输入数据；最后通过预先训练的门控记忆网络模型对未知类别的输入数据进行预测，判定是攻击请求或正常请求。门控记忆网络模型的参数是在训练数据上预先学习得到的。训练数据包含正常数据和攻击数据两类样本。经过低维实值特征表示输入模型进行训练。该流程框架的核心内容是低维实值特征表示和门控记忆网络模型。

# 1.2低维实值特征表示

网络攻击的实施依赖于网络通信，且多以异常的通信请求出现。通常，通信请求可以被看做是一个命令字符串，而异常的网络通信请求数据中通常包含特殊的命令字符串，如systemInfo、alert、SELECT等，因此可以通过对请求数据中包含的字符串进行分类来检测网络攻击。

图2是基于HTTP网络协议攻击数据的低维实值特征表示过程。该过程主要包括词切分、量化和降维三个步骤。

HTTP Header POST/xxx/xxx/tiendal/publim/antenticar.jsp  
Host: xxxxxxx.com  
Acoept: text/xml,application/xml  
c modo z, = Mx,  
HTTP Payload modo=entrar%27%3B+DROP+TABLE SELECT x 212  
+05+WHERE+SELECTLIKEFROM+d词切分 WHERE 量化→ X3 降维→ Z3  
1 &login=jeanes&pwd=d%F3712&rememb nombre · .  
•er=on&B1=Ent rar LIKE ·B1 XL ZLEntrar one-hot表示 低维特征表示

1)词切分对于通信请求字符串而言，其内容是根据网络协议的规则构造的，故其格式是具有一定规范的，也是能够被转换成由一系列"单词"或符号组成的文本。例如，针对网络服务器的访问很大一部分是基于HTTP协议的，而请求数据的载荷部分中所提交的参数字符串，可以视为由符号“&"分隔的若干段，每个段内存在键和值两部分，以"="连接。因此，可以将请求字符串分隔成若干“单词"或符号的序列，即使"单词"或符号是没有字面意义。在此基础上，借助现有的文本表示技术实现对请求数据的量化表示。

2)量化在词切分之后，传统文本分类的特征表示方法通常将每个词表示为一个one-hot向量。one-hot 向量是一个二进制向量，在词汇表中第 $i$ 个单词的第 $i$ 个元素被设置为1，其他元素都被设置为0，以此唯一地表示一个词。对于一个由 $\_ L$ 个词组成的序列而言，可以表示为一个长度为 $L$ 的 one-hot 序列$( X _ { 1 } , X _ { 2 } , . . . , X _ { L } )$ 。但是，one-hot 向量是一个稀疏高维二值向量，该特征表示在计算是耗时较大，且难以度量两个词之间的距离（相似度）关系，如两个词是语义相近的同义词。

3）降维为了克服one-hot向量表示的不足，本文将一个one-hot 向量 $X _ { i }$ 投影为一个低维空间中的实值向量 $\boldsymbol { Z } _ { i } \in \mathbb { R } ^ { d }$ (d为空间维度）。该投影过程可以通过对向量 $x _ { i }$ 左乘一个投影矩阵 $M \in \mathbb { R } ^ { d \times | V | }$ 实现（式（1）），其中 $\vert V \vert$ 是无重复词典中词的个数。

$$
Z _ { i } = M X _ { i }
$$

矩阵 $M$ 可以通过随机赋值得到或通过包含一个隐层的网络学习得到。实验表明，通过学习得到的矩阵 $M$ 具有更好的低维表示。矩阵 $M$ 学习的网络输入一个one-hot 词向量，输出与其相邻的下一个one-hot 向量词，以此来学习两个共现词之间的关系。网络训练完成后，其隐藏输出即为低维实值向量 $Z _ { i }$ 。降维表示将一个高维稀疏的one-hot序列 $( X _ { 1 } , X _ { 2 } , . . . , X _ { L } )$ 转换为一个低维实值向量序列(Z,Z,Z)。

# 1.3门控记忆网络模型

门控记忆网络模型由一个门控循环神经网络和一个逻辑斯特回归分类器组成。其中，门控循环神经网络对序列数据进行建模，抽取长时记忆特征表示；逻辑斯特回归分类器完成对请求数据的二类分类预测判定。

# 1.3.1门控循环神经网络

近年来，循环神经网络在语音识别领域取得了优越的成果，其结构主要由一个循环过程构成：

$$
\boldsymbol { h } _ { t } = \varphi ( W _ { h } \boldsymbol { Z } _ { t } + R _ { h } \boldsymbol { h } _ { t - 1 } + \boldsymbol { b } _ { h } )
$$

其中： $\mathbf { \Phi } _ { t }$ 时刻的激活 $h _ { { _ t } }$ 由 $\mathbf { \Phi } _ { t }$ 时刻的输入 $\boldsymbol { Z } _ { t }$ 和 $t - 1$ 时刻的激活 $h _ { { \scriptscriptstyle t } - 1 }$ 决定，如图3左侧所示。循环神经网络通过循环迭代计算$h _ { { \scriptscriptstyle t - 1 } } \to h _ { { \scriptscriptstyle t } }$ 使信息可以得到长时记忆，对于序列数据具有优秀的建模能力。但是经典的循环神经网络在训练模型时面临着梯度弥散问题[21]。为了克服该问题，长短期记忆（long short-termmemory,LSTM）单元结构[18.22]被引入循环神经网络。该结构由输入门、遗忘门、输出门等门控单元组成，以维持长时序列数据的信息记忆。由于网络由一系列门控单元组成，也被称为门控循环神经网络。

受门控循环神经网络[19,20]的启发，网络攻击检测的门控记忆网络单元结构如图3右侧所示。其中， $\boldsymbol { Z } _ { t }$ 为低维实值特征表示的输入向量； $h _ { { \scriptscriptstyle t } - 1 }$ 为网络 $t - 1$ 时刻的隐状态； $h _ { { _ t } }$ 为网络 $t$ 时刻输出的隐状态； $h _ { { _ t } }$ 不仅作为 $t + 1$ 时刻的输入，还作为计算最终输出结果的输入。虚线框中，箭头表示数据流向； $\mathbf { x } x$ 表示点乘操作； $^ { + + }$ 表示向量加操作；1-1-表示对输入 $\mathbf { x }$ 变量 $_ { 1 - { \bf X } }$ 操作；$\sigma$ 表示sigmoid 激活操作；tanh表示tanh 激活操作。低维实值向量序列 $( Z _ { 1 } , Z _ { 2 } , . . . , Z _ { L } )$ 进入门控记忆网络后会按序列展开进行计算，当最后一个向量 $\boldsymbol { z } _ { \scriptscriptstyle L }$ 进入网络经计算后，对应输出 $h _ { { _ L } }$ 即为门控记忆网络的输出。

![](images/6059a6a4076c72e42a69c304c607db12b9eb31b3da5f33d5909b62d32c8f1b19.jpg)  
图3循环神经网络(左)与门控记忆网络单元结构(右)

图3中门控记忆网络单元结构主要由重置门和更新门组成，形式化如下：

$$
r _ { t } = \sigma ( W _ { r } Z _ { t } + R _ { r } h _ { t - 1 } + b _ { r } )
$$

$$
\boldsymbol { U _ { t } } = \sigma ( \boldsymbol { W _ { u } } \boldsymbol { Z _ { t } } + \boldsymbol { R _ { u } } \boldsymbol { h _ { t - 1 } } + \boldsymbol { b _ { u } } )
$$

其中： $w _ { \scriptscriptstyle r } , w _ { \scriptscriptstyle u }$ 与 $R _ { \mathrm { } _ { r } } , R _ { \mathrm { } _ { u } }$ 分别为输入 $\boldsymbol { Z } _ { t }$ 和隐状态 $h _ { { \scriptscriptstyle t } - 1 }$ 的权重;$b _ { { } _ { r } } , b _ { { } _ { u } }$ 为对应的偏置； $\sigma ( \cdot )$ 为 sigmoid 函数。最终输出：

$$
\begin{array} { r } { \begin{array} { r } { h _ { t } = ( 1 - U _ { t } ) \odot h _ { t - 1 } + U _ { t } \odot \tilde { h } _ { t } , } \end{array} } \end{array}
$$

其中： $\tilde { h } _ { t } = \varphi ( W _ { h } z _ { t } + r _ { t } \odot ( R _ { h } h _ { t - 1 } ) + b _ { h } )$ ； $\varphi ( \cdot )$ 为tanh 函数； $\odot$ 为元素点乘； $W _ { \scriptscriptstyle h } \setminus \textsf { R } _ { \scriptscriptstyle h }$ 和 $b _ { \scriptscriptstyle h }$ 分别为输入和隐状态的权重，以及对应偏置。 $\tilde { h } _ { { } _ { t } }$ 的计算结果受重置门控制，若 $r _ { t } = 0$ ，则$r _ { t } \odot ( R _ { h } h _ { t - 1 } ) = 0$ ，即 $_ { t - 1 }$ 时刻的信息输入 $R _ { h } h _ { { _ { t - 1 } } }$ 不起作用，此时隐含信息 $\tilde { h } _ { { } _ { t } }$ 仅由 $\mathbf { \Phi } _ { t }$ 时刻输入信息 $\boldsymbol { Z } _ { t }$ 控制，即 $\tilde { h } _ { { } _ { t } }$ 遗忘了其历史信息 $h _ { { \scriptscriptstyle t } - 1 }$ ，被 $\mathbf { \Phi } _ { t }$ 时刻输入信息 $\boldsymbol { Z } _ { t }$ 重置。最终输出 $h _ { { _ t } }$ 是由 $\boldsymbol { u } _ { \ u { t } }$ 控制加权平均 $t - 1$ 时刻隐含信息 $h _ { { \scriptscriptstyle t } - 1 }$ 与 $\mathbf { \Phi } _ { t }$ 时刻隐含信息 $\tilde { h } _ { { } _ { t } }$ 得到。

与LSTM相比，门控记忆网络单元结构将输入门和遗忘门整合为更新门，以平衡 $t - 1$ 时刻的激活 $h _ { { \scriptscriptstyle t } - 1 }$ 和 $\mathbf { \Phi } _ { t }$ 时刻的更新激活$\tilde { h } _ { { } _ { t } }$ ，同时重置门通过元素点乘决定是否遗忘 $t - 1$ 时刻的激活$R _ { h } h _ { { \scriptscriptstyle t - 1 } }$ 。序列数据的最终输出为具有长时记忆特性的隐含状态$h _ { { } _ { L } }$ ，该向量作为分类器的输入。

# 1.3.2逻辑斯特回归分类器

对于网络攻击检测二类分类问题，输入为网络协议请求数据，经低维实值特征表示转换为长度为 $\mathbf { \Omega } _ { L }$ 的向量序列$( Z _ { 1 } , Z _ { 2 } , . . . , Z _ { L } )$ ；再经门控循环神经网络提取长时记忆特征 $h _ { { _ L } }$ ；最终通过一个二类分类器进行分类输出。

本文采用逻辑斯特回归分类器。训练时，给定一组二值标签样本 $\{ ( h _ { L } ^ { ( i ) } , y ^ { ( i ) } ) : i = 1 , . . . , N \}$ ，其中： $h _ { _ L } ^ { ( i ) }$ 为第 $i$ 个样本的特征向量； $y ^ { ( i ) } \in \{ 1 , 0 \}$ 为其对应的真实类别标签（1 表示攻击样本，0表示正常样本）； $N$ 为训练样本个数。根据最大似然估计原理，计算所有样本的似然如下：

$$
L = \prod _ { i } \big ( \mathcal { F } _ { \theta } ( h _ { L } ^ { ( i ) } ) \big ) ^ { y ( i ) } \big ( 1 - \mathcal { F } _ { \theta } ( h _ { L } ^ { ( i ) } ) \big ) ^ { 1 - y ( i ) }
$$

其中： $\mathcal { F } _ { \theta } ( v ) = 1 / \left( 1 + \exp ( - \theta ^ { T } v ) \right)$ 逻辑斯特函数，其值可表示对输入样本 $v$ 判定为攻击样本的概率； $\theta$ 为待学习参数向量。为了方便优化，将最大化 $L$ 转变为最小化负的对数似然：

$$
\begin{array} { r l } & { J = - \log L } \\ & { \quad = - \log \prod _ { i } ( \mathcal { F } _ { \theta } ( h _ { L } ^ { ( i ) } ) ) ^ { y ^ { ( i ) } } \left( 1 - \mathcal { F } _ { \theta } ( h _ { L } ^ { ( i ) } ) \right) ^ { 1 - y ^ { ( i ) } } } \\ & { \quad = - { \displaystyle \sum _ { i } \left( \log ( \mathcal { F } _ { \theta } ( h _ { L } ^ { ( i ) } ) ) ^ { y ^ { ( i ) } } + \log ( 1 - \mathcal { F } _ { \theta } ( h _ { L } ^ { ( i ) } ) ) ^ { 1 - y ^ { ( i ) } } \right) } } \\ & { \quad = - { \displaystyle \sum _ { i } \left( y ^ { ( i ) } \log ( \mathcal { F } _ { \theta } ( h _ { L } ^ { ( i ) } ) ) + ( 1 - y ^ { ( i ) } ) \log ( 1 - \mathcal { F } _ { \theta } ( h _ { L } ^ { ( i ) } ) ) \right) } } \end{array}
$$

对于一个训练样本而言，式（7）中求和的两项只有一项不为零（取决于标签 $y ^ { ( i ) }$ 是1或0）。当 ${ \boldsymbol y } ^ { ( i ) } = 1$ ，最小化优化目标$_ { J }$ 意味着需要使 $\mathcal { F } _ { \theta } ( h _ { \iota } ^ { ( i ) } )$ 变大；当 $\boldsymbol { y } ^ { ( i ) } = 0$ ，则需要使 $1 - \mathcal { F } _ { \theta } ( h _ { L } ^ { ( i ) } )$ 变大。

实际过程中，逻辑斯特回归分类器可与门控记忆网络连接起来共同训练，门控记忆网络输出隐状态 $h _ { \scriptscriptstyle L } ^ { ( i ) }$ 通过一个一个全连接层来计算输出 $\boldsymbol { q } = \boldsymbol { \theta } ^ { T } h _ { \boldsymbol { L } } ^ { ( i ) }$ ，再连接一个 sigmoid 层实现$o = 1 / \left( 1 + \exp ( - q ) \right)$ 的计算，最后损失层计算式（7）结果。优化时，采用随机梯度下降算法进行参数更新，从后向前先计算偏导数 $\hat { c } J / \hat { c } o$ ，再根据反向传播算法，依次计算各层的偏导数以实现网络参数的学习。

测试时，将损失函数替换为一个逻辑斯特函数 $\mathcal { F } _ { \theta } ( v )$ 。当需要预测判定一个新的样本是属于"1"还是属于"0"时，则可以通过比较 $\mathcal { F } _ { \theta } ( h _ { \iota } ^ { ( i ) } )$ 与 $1 - \mathcal { F } _ { \theta } ( h _ { L } ^ { ( i ) } )$ 的大小来进行判定。若F(h)>1-F(h)，则判为"1”，否则判为"0”。

# 1.4门控记忆网络方法的实现细节

对于CSIC2010 数据集，先从中提取的通信请求数据。对于GET请求直接提取URI信息，对于PUT和POST请求提取URI和负载数据并将两者拼接起来，作为低维实值特征表示的输入，经过低维实值特征表示转换为一个词向量序列。具体实现时，词向量序列由一个词索引序列和一个词索引到词向量的映射矩阵组成。词索引序列中每个索引对应一个预训练好的词向量，根据词索引可从词索引到词向量的映射矩阵中找到词向量，该表示可大大节省空间。词索引到词向量的查找由一个网络嵌入层（embeddinglayer）实现。值得注意的是，词向量序列会根据数据集的整体特征被统一截断或补齐为长度56的序列，目的是可以批量输入数据进行训练。

门控记忆网络方法采用了深度学习的架构体系，其具体框架如表1所示。

表1门控记忆网络方法框架  

<html><body><table><tr><td>网络层</td><td>描述</td></tr><tr><td>输入层</td><td>输入词索引序列，不做处理直接输出</td></tr><tr><td>嵌入层</td><td>输入词索引序列和词索引到词向量的映射矩阵，将词 索引转化为词向量输出</td></tr><tr><td>门控记忆层</td><td>输入词向量序列，门控记忆单元计算的最后一个隐状 态作为输出</td></tr><tr><td>Dropout 层</td><td>输入隐状态，以一定概率丢弃权值后输出</td></tr><tr><td>全连接层</td><td>通过全连接映射到两个值输出</td></tr><tr><td>Softmax层</td><td>输出两个数值，归一化为两个概率值输出</td></tr></table></body></html>

表中，输入层和嵌入层完成低维实值特征表示；Dropout层是深度学习中用于抑制过拟合的主要手段，使用该策略可以获得更好的测试精度；全连接层和Softmax层实现逻辑斯特回归，对应计算式（6）中的 $\mathcal { F } _ { \theta } ( h _ { \iota } ^ { { ( i ) } } ) = 1 / \left( 1 + \exp ( - \theta ^ { T } h _ { \iota } ^ { { ( i ) } } ) \right)$ ，全连接完成线性映射计算，Softmax对映射后的两个值归一化得到$\mathcal { F } _ { \theta } ( h _ { \mathrm { . } } ^ { ( i ) } )$ 和 $1 - \mathcal { F } _ { \theta } ( h _ { L } ^ { ( i ) } )$ 。训练时，网络计算损失并进行梯度回传和参数更新；测试时，网络计算 $\mathcal { F } _ { \theta } ( h _ { \iota } ^ { ( i ) } )$ 和 $1 - \mathcal { F } _ { \theta } ( h _ { L } ^ { ( i ) } )$ 大小，判定类别标签。

基于Windows7操作系统（ $3 . 5 \mathrm { G H z }$ 主频，8GB内存）和tensorflow平台，实现门控记忆网络方法，所有训练和测试均采用CPU完成。网络输入为 $d$ 维的向量序列，单层门控记忆单元的隐状态维度为128，其后网络接一个Dropout层，Dropout 率为0.9，然后将128维输出全连接映射到2维结果输出。训练网络时，将批处理大小设置为128，学习率设置为0.001。训练代数为10，使用Adam优化器训练。

# 2 实验结果与分析

实验以CSIC2010数据集作为测试数据集。该数据集包含上万条自动生成的HTTP协议请求，主要用于测试网络攻击防护系统，它是由西班牙研究委员会（CSIC）信息安全研究所制作的。该数据集针对的是一个电子商务Web应用程序，已发布的数据被分为训练（只有正常）和测试（异常和正常）集。在实验中，采用的是测试集中36000多个正常请求和25000多个异常请求。该数据集中的攻击请求包含多种网络攻击，如SQL注入、缓冲区溢出、信息收集、文件披露，CRLF注入、跨站脚本和参数窜改等。其中，针对隐藏（或不可用）资源的请求也被视为异常[1,14]。目前，由于个人隐私保护等原因，公开可用的Web攻击检测问题的数据集非常少，诸如DARPAKDD99攻击检测数据集中的攻击很多都已过时，且不包括许多新型的攻击类型。

对于原始的请求数据，实验主要提取GET、POST、PUT 请求数据来进行检测。请求数据提取后对数据进行分词，即字符串分割。分词依据HTTP请求特点进行，主要涉及URL中字符解码，参数项、键值对、特殊符号的分割，请求数据的分词可以为后续低维实值特征表示提供基础。

# 2.1方法对比

为了验证本文方法的有效性，分别与传统方法和深度学习方法进行对比分析。传统方法包括朴素贝叶斯（naive Bayes,NB）、线性支持向量机（linear support vector machine,LSVM）、神经网络（neural network,NN）、K-近邻（K-near neighbor,KNN）、决策树（decisiontree,DT）。深度学习方法包括LSTM。

在特征表示方面，传统方法统一采用 TF-IDF 特征向量。深层学习方法采用1.2节中描述的数据特征低维表示。在分类检测方面，传统方法的参数设置如下：NB恒定的参数为0.01。LSVM采用线性分类器。NN采用两个隐层，隐单元个数分别为50和10。KNN设置邻居参数为3。DT采用熵最小，且叶子中的最小样本数被设置为3。

所有方法采用10折交叉验证技术进行结果评估。数据集随机分为10份，其中一份用于测试，其余用于训练。10次运行的结果取平均得到整体性能。测试结果以准确率、召回率和F1分数作为评测指标。实验结果见表2。

表2实验训练和测试数据  

<html><body><table><tr><td>方法</td><td>准确率</td><td>召回率</td><td>F1分数</td></tr><tr><td>本文方法</td><td>0.984</td><td>0.985</td><td>0.985</td></tr><tr><td>LSTM</td><td>0.977</td><td>0.979</td><td>0.978</td></tr><tr><td>DT</td><td>0.925</td><td>0.917</td><td>0.920</td></tr><tr><td>KNN</td><td>0.907</td><td>0.911</td><td>0.908</td></tr><tr><td>NN</td><td>0.895</td><td>0.882</td><td>0.887</td></tr><tr><td>LSVM</td><td>0.887</td><td>0.867</td><td>0.875</td></tr><tr><td>NB</td><td>0.767</td><td>0.776</td><td>0.765</td></tr></table></body></html>

由表2可以发现，门控记忆网络方法明显优于其他方法，准确率和召回率分别达到了 $9 8 . 4 \%$ 和 $9 8 . 5 \%$ ，较LSTM超出 $0 . 7 \%$ 的准确率和 $0 . 6 \%$ 的召回率，且远超传统方法。该结果表明本文方法具有很好的攻击检测效果。

# 2.2隐变量参数分析

门控记忆网络中，隐状态维度是影响网络能力的关键参数因子。为了进一步分析该参数变化对性能的影响。本节中固定Dropout参数为0.9，低维实值词向量维度为40。测试不同维度条件下，模型检测方法的F1分数综合性能。为了进一步说明本文方法的有效性，同时对比不同参数条件下LSTM方法的F1分数，实验结果如图4所示。此外，不同参数条件下，模型训练耗时如表3所示。

表3模型训练耗时/min  

<html><body><table><tr><td>方法\隐变量维度</td><td>16</td><td>32</td><td>64</td><td>128</td><td>256</td><td>512</td></tr><tr><td>本文方法</td><td>17</td><td>24</td><td>40</td><td>58</td><td>132</td><td>416</td></tr><tr><td>LSTM</td><td>17</td><td>24</td><td>36</td><td>67</td><td>175</td><td>539</td></tr></table></body></html>

![](images/7a0c6e3e469f9feeda27ab4be56893a962347864900328661040595235a00c01.jpg)  
图4不同隐节点维度下的F1分数

![](images/4e752af493b224abd4586df060a4794ebefd986aeddd23a0cfb1499b0d91439a.jpg)  
图6低维实值词向量嵌入的分布

由图4和表3可以得到如下结论：

a）模型的性能随着参数维度的增加而不断增加，但增加的幅度越来越小;b）对比LSTM模型，可知本文方法在相同参数条件下较LSTM模型结果更好；c）模型计算耗时会随着维数的增加而增加，故实际应用需要在效果与性能之间进行折中。

# 2.3Dropout 策略分析

考虑到CSIC2010 数据集的规模中等，为了抑制学习的过拟合问题，在模型训练中，加入了Dropout 策略。该策略中Dropout率决定了模型的效果。故研究固定隐变量维度为128，低维实值词向量维度为40的条件下，不同Dropout率的影响。图5给出了不同方法的Dropout率的结果。

![](images/ecf21d13f7af6c2a34e50d6b099775c8eb9cf1cc218667934de09ad68b906588.jpg)  
图5不同Dropout率下的F1分数

图6给出了13个低维实值词向量的嵌入显示。其中select、like、script、alert、waitfor是SQL入侵攻击的关键词，这些词在嵌入空间中均聚集在一起，而正常词汇如login、password 等则呈现随机分布的特性，这种相似词聚集的特性更容易帮助分类器学习网络攻击行为的模式。

此外，不同的低维实值词向量维度也会对模型的精度产生影响。为了研究低维实值词向量维度对算法性能的影响，分别选取10、20、40、80、160、320，测量模型对攻击检测的效果和耗时。图7给出了对应的测试结果。

![](images/3b634fcfc442e83d162738c74fd8e6cbb8c9c60c2daded4a94574bedf2823be6.jpg)  
图7低维实值词向量不同维度下的F1分数和耗时

由图7可知：

由图5可以得到：

a）模型泛化性能随着Dropout率增加而不断增长，但增长幅度不断减小。b）Dropout 策略（较大的Dropout 率）具有很好的抑制过拟合的能力，并取得了较好的性能。Dropout率为0.9时，达到了 $9 8 . 4 0 \%$ 的F1分数。

# 2.4低维实值词向量分析

低维实值词向量具有很好的特征表示能力，可以度量不同词间的相似性关系。具有相似关系或相同属性的词汇在向量空间中距离更近，易聚集在一起。为了说明低维实值词向量的表示能力，本文选取部分低维实值词向量并通过t-SNE方法[23]嵌入二维平面显示词间的关系，如图6所示。

a）本文方法随着低维实值词向量维度的增加，检测效果也不断增加，在维度为160时，达到了 $9 9 . 1 0 \%$ 的F1分数；b)同时，本文方法的耗时会随低维实值词向量维度的增加不断增长，且基本保持线性增长速率；c）在实际应用中，可根据应用的差异选择一定的低维实值词向量维度以实现速度和效果的折中。

# 3 结束语

针对网络攻击检测问题，本文提出了一个门控记忆网络方法，在CSIC2010 数据集上达到了 $9 8 . 4 0 \%$ 的F1分数，超越了传统方法和LSTM 等检测方法。该方法实现简单、效果显著。同时，算法在检测时速度可达到实时应用需要。但是，由于数据特征低维表示的学习通常需要一定规模的数据支撑，所以本文需要大量网络请求数据来进行学习。

此外，本文方法仅采用单层门控循环神经网络结构，下一步拟采用多层网络结构进一步提高检测精度。考虑到多层网络的时间耗费，可根据实际情况构造两层或三层网络结构，以折中检测精度和时间耗费。同时，为了进一步验证本文的效果，后续将在实际网络环境中进行测试，以检验方法的实际可用性。

# 参考文献：

[1]Elbachirelmoussaid N,Toumanari A.Web application attcks detection: a survey and classification [J]. International Journal ofComputer Applications, 2014,103 (12): 1-6.   
[2] 徐周波，张永超，古天龙，等．面向入侵检测系统的模式匹配算法研究 [J]．计算机科学,2017,44(9):125-130.(Xu Zhoubo,Zhang Yongchao,Gu Tianlong,et al. Research on pattern matching algorithm in intrusion detection system [J]. Computer Science,2017,44 (9): 125-130.)   
[3] 戴远飞，陈星，陈宏，等．基于特征选择的网络入侵检测方法[J].计 算机应用研究,2017,34(8):2429-2433.(Dai Yuanfei,Chen Xing,Chen Hong,et al. Feature selection based approach to network intrusion detection [J]. Application Research of Computers,2017,34(8): 2429-2433.)   
[4]马林进，万良，马绍菊，等．基于词袋模型的分布式拒绝服务攻击检测 [J].计算机应用,2017,37(6):1644-1649.(Ma Linjin,Wan Liang,Ma Shaoju,et al. Distributed denial of service attck recognition based on bag of words model[J]. Journal ofComputer Application,2017,37(6):1644- 1649.)   
[5]Mao Chinghao,Lee HM,Liu Ensi,et al.Web mimicry attacks detection using HTTP token causal correlation [J]. International Journal of Innovative Computing Information& Control,2011,7(7): 4347-4362.   
[6] Oza A,Ross K,Low R M,et al. HTTP atack detection using n-gram analysis [J]. Computers& Security,2014,45 (3): 242-254.   
[7]Singh K J, De T.An approach of DDOS attck detection using classifiers [M]// Emerging Research in Computing, Information, Communication and Applications. New Delhi: Springer, 2015: 429-437.   
[8]Garcia V H, Monroy R, Quintana M. Web attck detection using ID3 [M]// Professional Practice in Artificial Intelligence.Boston,MA: Springer,2006: 323-332.   
[9]Rawat R, Kumar Shrivastav S. SQL injection attack detection using SVM [J]. International Journal of Computer Applications,2012,42(13): 1-4.   
[10]吴少华，程书宝，胡勇．基于SVM的Web攻击检测技术[J].计算机科 学,2015,42 (6A): 362-364.(Wu Shaohua, Cheng Shubao,Hu Yong. Web attck detection method based on support vector machines [J]. Computer Science,2015,42 (6A): 362-364. )   
[11] Silva L D S,Santos AC F D,Silva JD SD,et al.A neural network application for attack detection in computer networks [C]//Proc of IEEE International Joint Conferenceon Neural Networks.Budapest,.Hungary: IEEE Press,2004: 1569-1574.   
[12]Li Jin,Liu Yong,Gu Lin.DDoS atack detection based on neural network [C]// Proc of IEEE International Symposium on Aware Computing.[S.1.]: IEEE Press,2010: 196-199.   
[13]肖甫，马俊青，黄洵松，等.SDN 环境下基于 KNN的 DDoS 攻击检测 方法[J].南京邮电大学学报：自然科学版,2015,35(1):84-88.(Xiao Fu, Ma Junqing, Huang Xunsong, et al. DDoS attck detection based on KNN in software defined networks [J]. Journal ofNanjing University of Posts and Telecommunications: Natural Science Edition,2015,35 (1): 84-88.）   
[14] Mikolov T,Chen K,Corrado G,et al.Efficient estimation of word representations in vector space [J/OL]. CoRR,2013,abs/1301. 3781. https://rxiv. org/abs/1301.3781.   
[15] Mikolov T, Sutskever I, Chen K,et al. Distributed representations of words and phrases and their compositionality[C]//Proc of 27th Annual Conference on Neural Information Processing Systems.Lake Tahoe, Nevada: Curran Associates,Inc,2013: 3111-3119.   
[16] Nowak J, Taspinar A, SchererR. LSTM recurrent neural networks for short text and sentiment classification [C]// Proc of International Conference on Artificial Intelligence and Soft Computing. Cham: Springer,2017: 553-562.   
[17]Liu Pengfei,Qiu Xipeng, Huang Xuanjing. Recurrent neural network for text classification with multi-task learning [C]//Proc of International Joint Conference on Artificial Intelligence. NewYork, NY: IJCAI//AAAPre, 2016: 2873-2879.   
[18] Kim J, Kim J, Thu HL T,et al. Long short term memory recurrent neural network classifier for intrusion detection [C]// Proc of IEEE International Conference on Platform Technology and Service.Jeju, SouthKorea: IEEE Press, 2016: 1-5.   
[19] Cho K,Merrienboer B V, Gulcehre C,et al. Learning phrase representations using RNN encoder-decoder for statistical machine translation [J/OL]. CoRR,2014,abs/1406.1078.htps://arxiv.org/abs/1406.1078.   
[20] Chung J,Gulcehre C,Cho KH,et al.Empirical evaluation of gated recurrent neural networks on sequence modeling [J/OL]. CoRR,2014,abs/1412.3555. https://arxiv. org/abs/1412. 3555   
[21] PascanuR,Mikolov T,Bengio Y.On the difficulty of trainingrecurrent neuraletworks[C//ProcofInterationalConferenceon MachineLeaing. Altanta, Georgia: PMLR,2013: 1310-1318.   
[22] Hochreiter S,Schmidhuber J.Long short-term memory [J].Neural Computation,1997,9(8): 1735-1780.   
[23] Maaten L V D,Hinton G. Visualizing data using t-SNE [J].Journal of

Machine Learning Research,2008,9 (2605): 2579-2605.