# 基于字簇的多模型中文分词方法研究

李对红，王裴岩，张桂平，张少阳(沈阳航空航天大学 人机智能研究中心，沈阳 110136)

摘要：字标注分词方法是当前中文分词领域中一种较为有效的分词方法。但由于中文汉字本身带有语义信息，不同字在不同语境中其含义与作用不同，导致每个字的构词规律存在差异。针对这一问题，提出了一种基于字簇的多模型中文分词方法。该方法首先对每个字进行建模，然后对学习出的模型参数进行聚类分析形成字簇，最后基于字簇重新训练模型参数。实验结果表明，该方法能够有效地发现具有相同或相近构词规律的字簇，很好地区别了同类特征对不同字的作用程度。

关键词：中文分词；构词规律；模型参数；聚类 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2018.08.0540

Multi-model Chinese word segmentation method based on character clusters

Li Duihong, Wang Peiyan†, Zhang Guiping, Zhang Shaoyang (Human-Computer Inteligence Research Center,Shenyang Aerospace University,Shenyang l1Ol36,China)

Abstract: Character-based tagging method is currentlyan effective method in Chinese word segmentation.However,the Chinese characters had theirownsemantic information,different characters had diferent meaningsand functions in diferentcontexts,which leadtodiffrentcorrelations withcontext,resulting inthediferenceof word-formationrules for each word.To solvethis problem,this paper proposeda multi-model method based oncharactercluster.Firstly,the method separately constructed amodelfor each word,then clustered the model parameters to form character clusters，and finaly retrainedthe model parameters basedonthecharacter clusters.Experimental results show that this methodcaneffectively find character clusterswith the sameorsimilar word-formation rules,and distinguish the effectof similar features for different characters.

Key words: Chinese word segmentation; word-formation rules; model parameters; clustering

# 0 引言

词是能够独立运用的最小语言单元。与英语和其他西方语言有所不同，中文以字为基本书写单位，词语之间没有明显的分界符加以区分，如果不进行分词，计算机就无法得知中文词的确切边界，从而很难理解文本中所包含的语义信息[1]。因此，中文分词是自然语言处理中的一项基础性工作,其在命名实体识别、文本自动分类、机器翻译等领域都有着举足轻重的地位，其性能的好坏直接影响后续的自然语言处理任务。

中文分词方法中，有指导的字标注分词方法[2具有较好的分词效果。该方法将分词过程抽象为序列标注任务，采用适合于序列标注的机器学习模型进行建模。其中，应用比较广泛的序列标注模型主要有最大熵马尔可夫模型(maximumentropyMarkov model，MEMM)[3]、隐马尔可夫模型(hiddenMarkov model，HMM)[4]和条件随机场(conditional randomfield，CRF)模型[5-7]。然而，这些模型分词效果的好坏很大程度上受制于特征的选择和提取。近年来，随着深度学习的蓬勃发展，循环神经网络(recurrent neural networks，RNN)、长短期记忆(long-shorttermmemory，LSTM)神经网络以及它们的变体等适用于序列标注任务的神经网络模型被广泛地应用

于分词任务[8\~11]。

无论是传统的机器学习模型还是神经网络模型，它们都是着眼于句子中的每一个字(或是符号)，根据当前待标注字的上下文环境判断其词位信息，以此作为分词的标记。该类方法基于训练语料建立单一模型参数，考虑的是上下文环境对所有字的全局综合作用，即假设相同上下文环境对不同待标注字的影响相同，学习出字构词的一般性规律。然而，由于中文汉字本身带有语义信息，造成了每个字的构词规律存在差异，即使相同的字作为待标注字的上下文特征时其含义与作用也存在较大的差异[12,13]，造成与待标注字的结合紧密程度发生变化。以如下例子进行说明：

a）建立/稳定/和睦/的/两岸/关系/。/b）营造/了/民主/和谐/的/气氛/。/c）党中央/坚持/领导/和/党/的/十五大/精神/。/

上述的三个例句，当前待标注字分别为"睦”“谐”“党”时，前一个特征都为“和”，然而，相同的特征对待标注字的影响却不同，即与待标注字的结合紧密程度不同。从例子中可以看出，一、二句中的“和”与待标注字“睦”、“谐”的结合紧密程度相同，而第三句中的“和”与待标注字“党”的结合紧密程度与前两例句不同。因此，假设上下文环境对待标注字的影响相同显然存在问题。针对这一问题，文献[14]提出了基于字的多模型中文分词方法，该方法最大的特点是对每个字建立单独的模型参数，有效地区分了相同特征对不同待标注字的影响，学习出了字构词的特殊性规律。然而，该方法也存在不足，尽管针对每个字训练得到的模型参数可以很好地反映该字的构词规律，但是，存在某些字的构词规律相同或相近，势必造成模型参数的冗余。并且部分字的训练样本较少，也会造成未登录词召回率的降低。

本文对基于字的多模型中文分词方法[14]进行改进，提出了一种基于字簇的多模型分词方法。该方法对基于字的多模型分词方法学习出的模型参数进行聚类分析，将具有相同或相近构词规律的字聚合形成字簇，并基于此字簇训练模型参数。该方法与单模型方法相比，有效地提高了词表词召回率，与多模型方法相比，有效地提高了未登录词召回率，并在PKU语料与MSR语料上得到了验证。

# 1基于字簇的多模型分词方法

# 1.1模型训练流程

本文提出了一种基于字簇的多模型分词方法，该方法首先基于字的多模型分词方法训练得到每个字的模型参数。字的模型参数代表了该字的构词规律。接下来对上述的模型参数进行聚类分析，发现模型参数之间内在的分布结构，将具有相同或相近构词规律的字聚合形成字的类簇。最后，基于上述的类簇重新训练得到模型参数。其具体训练流程包括三个部分：字模型参数获取、字构词规律分布结构发现、模型再训练。如图1所示。

![](images/43d5ec30300c4ea5b4ae86a496708c2b3d778a2156abaeba63bcf92ff5225d70.jpg)  
图1基于字簇的多模型分词方法模型训练流程  
Fig.1The training process of multi-model segmentation methoc based on character clusters

1)字模型参数获取

本文基于字的多模型分词方法训练得到模型参数，各个模型参数之间相互独立，有效地学习出每个字的构词规律。图1显示了该方法训练得到的n个字的模型参数，每个模型参数由d维向量表示，代表了该字的构词规律。

# 2)字构词规律分布结构发现

本文所提方法的关键之处在于如何发现上述模型参数之间的相关性，学习多个字之间共有的构词规律。本文采用层次聚类算法对上述得到的模型参数进行聚类分析，形成字的类簇，其中每一类簇表示该类字具有相同或相似的构词规律。具体另见1.4小节。

# 3)模型再训练

该模块根据上述生成的字的类簇重新在训练语料中抽取训练样本，输入到模型结构中进行训练。具体模型结构另见1.2 小节。

# 1.2模型结构

中文分词过程通常被视为字符级别的序列标注问题，因此，可以将分词过程视为对字符串中的每个字符标注的机器学习过程。本文借鉴Ma Jianqiang 等人[15]的思想，将模型结构分为3个部分，分别为Look-up表、Concatenation函数、Sigmoid函数。与基于字的多模型分词方法有所不同，本文的分词方法基于字簇进行建模。分词时，根据对应的字簇模型参数进行决策。为了降低问题的复杂性，每个类簇模型采用相同的结构。具体模型结构如图2所示。

![](images/facfc5ca4d0580251dd9fddcc3c5b8a72b18cd812a4a16e24701952dee243062.jpg)  
图2模型结构  
Fig.2Model structure

a)Look-up表，记录了特征与实数向量之间的映射关系，又称为特征的Embedding。每个不同特征t的Embedding记$E m b e d ( t ) = \mathbb { R } ^ { N }$ ，其中 $N$ 表示实数向量的维度。特征是从训练语料中提取的。

b)Concatenation函数。为了预测待标注字符的标记状态，需要将其对应的特征Embedding连接成一个单一的向量，作为模型的输入，记为 $\boldsymbol { a } \in \mathbb { R } ^ { N \times K }$ ，其中 $K$ 是用于描述待标注字符的特征数量， $N$ 为特征Embedding 的维度。

c)Sigmoid函数。模型结构中采用的激活函数为Sigmoid函数，定义如式(1)所示。其中，a为输入的特征Embedding，w 为特征权重， $\langle a , w \rangle$ 表示两个向量的点积。

$$
h ( a ) = { \frac { 1 } { 1 + e ^ { - ( a , w ) } } }
$$

# 1.2.1输入

本文从宽度为5的上下文窗口中抽取特征。其中包括一元特征和二元特征，如表1所示。已有的研究表明，5字长的上下文窗口恰好大致表达了前后各一个词的上下文[16]，从这个意义来讲，5字宽的上下文窗口具备了字和词的双重含义，足以覆盖真实文本中绝大多数的构词情形。

表1一元/二元特征表  
Table1 Uni-and bi-gram feature template   

<html><body><table><tr><td>特征类型</td><td>特征</td></tr><tr><td>一元特征</td><td>Ci-2,Ci-1,Ci,Ci+1,Ci+2</td></tr><tr><td>二元特征</td><td>Ci-2Ci-1,Ci-1CiCiCi+1,Ci+1Ci+2</td></tr></table></body></html>

其中，下标代表了字与待标注字的相对位置。Ci表示当前待标注字， $\mathbf { C } _ { \mathrm { i } - 1 }$ 表示当前待标注字的前一个字， $\mathbf { C } _ { \mathrm { i + 1 } }$ 表示当前待标注字的后一个字，依此类推。本文以上例中的“睦”“谐”分别作为当前待标注字，则“睦"对应的一元特征分别为“定”“和”“睦”“的”“两”，对应的二元特征分别为“定和”“和睦”“睦的”“的两”；同理，“谐”对应的一元特征分别为“主”“和”“谐”“的”“气”，对应的二元特征分别为“主和”“和谐”“谐的”“的气”。

# 1.2.2输出

字符序列中的每一个字符都有确切的词位标注结果。本文使用“S”和“C”两种标签表示当前待标注字可能的标记状态。其中“S”(Separation)标签表示当前字与前一个字处于分离状态，即以当前字符开始一个新的词，而“C”(Combination)标签表示当前字与前一个字处于结合状态，即与前一个字组成一个词或词的一部分。以下面的句子为例，其正确标记序列如下。

建-S立-C稳-S定-C和-S睦-C的-S两-S岸-C关-S系-C。-S

本文采用的激活函数输出值分布在(0,1)内。本文以0.5作为阈值，若输出值大于0.5 则标记为"S",否则标记为"C”。

# 1.3模型训练

本文采用交叉熵作为损失函数，如式(2)所示。训练过程首先在当前参数下预测待标注字的标记，再根据语料中其正确标记来更新模型参数。

$$
J = - \sum _ { i = 1 } ^ { n } y _ { i } \log ( \mathsf { h } ( \hat { a } _ { i } ) ) + ( 1 - y _ { i } ) \log ( 1 - \mathsf { h } ( \hat { a } _ { i } ) )
$$

其中： $y _ { i }$ 表示正确标记状态， $\mathbf { h } ( \mathfrak { a } _ { i } )$ 为模型预测的结果。

为了防止过拟合导致模型的泛化能力降低，本文在损失函数中增加 $\boldsymbol { \mathscr { l } } _ { 2 }$ 正则项，如式(3)所示。其中 $\lambda$ 为正则项系数，用于控制正则化的强度。

$$
J = J + \frac { \lambda } { 2 } ( \left\| \pmb { a } \right\| ^ { 2 } + \left\| \pmb { w } \right\| ^ { 2 } )
$$

本文采用随机梯度下降法对目标函数进行优化，采用误差反向传播的方式分别求出目标函数对 $w$ 和a的梯度，更新$w$ 时保证a不变，反之亦然。更新公式如式(4）(5)所示。

$$
a = a - \eta \frac { \hat { \sigma } J } { \hat { \sigma } a }
$$

$$
\boldsymbol { w } = \boldsymbol { w } - \eta \frac { \partial J } { \partial \boldsymbol { w } }
$$

# 1.4基于聚类的构词规律分布结构发现

在无监督学习中聚类算法可以用于寻找数据内在的分布结构。本文以层次聚类[17]作为后期模型训练的前驱工作，用于发现基于字的多模型分词方法中模型参数所表示的构词规律分布结构。层次聚类首先将每个模型参数作为一个类别，然后根据距离不断合并这些原子类,形成一个具有树型的聚类结构，最后根据事先设定的簇间切分标准对聚类结构进行切分，形成最终的类簇。具体算法流程如下：

a)将每个模型参数看做一类，计算两两之间的距离；

b)将距离最小的两个类合并成一个新类；

c)重新计算新类与所有类之间的距离；

d)重复(2)(3)，生成一个具有树型的聚类结构；

e)根据簇间切分标准对聚类结构进行切分，形成最终的类簇。

聚类结束后，将得到字的类簇。字所处类簇相同，代表该类字的构词规律相同或相近;反之，则说明字的构词规律存在差异。

层次聚类算法中通常采用的距离度量方式为欧氏距离、余弦相似度，具体如式(6)(7)所示。

$$
d i s t _ { e d } = \sqrt { \sum _ { n = 1 } ^ { d } \lvert x _ { n } - x _ { n } ^ { \prime } \rvert } ^ { 2 }
$$

$$
d i s t _ { \mathrm { c o s } } = \frac { \displaystyle \sum _ { n = 1 } ^ { d } x _ { n } x _ { n } ^ { \prime } } { \sqrt { \displaystyle \sum _ { n = 1 } ^ { d } x _ { n } ^ { 2 } } \sqrt { \displaystyle \sum _ { n = 1 } ^ { d } x _ { n } ^ { \prime 2 } } }
$$

其中： $x , x ^ { \prime }$ 代表模型参数， $d$ 表示向量的维度， $d i s t _ { e d }$ 代表欧氏距离，值越小，表示两个模型参数之间距离越小，即两个模型参数越相近； $d i s t _ { \mathrm { c o s } }$ 代表余弦相似度，值越大，表示两个模型参数之间夹角越小，两个模型参数距离越小，即两个模型参数之间越相近。

算法执行过程中为了统一采用距离最小值作为类簇合并条件，在使用余弦相似度作为距离度量方式时实际采用$1 - d i s t _ { \mathrm { c o s } }$ ，当 $1 - d i s t _ { \mathrm { c o s } }$ 值越小，表示两个模型参数越相近。

簇间切分标准采用不一致系数，该系数反映了树型聚类结构中两个类簇合并时的距离与其下层深度为2的类簇合并时的距离不一致程度。当划分到有明显区别的类簇时，不一致系数较高，反之亦然。不一致系数计算公式如式(8)所示。

$$
i n c o n s i s t e n c y = \frac { h - a \nu g } { s t d }
$$

其中：inconsistency代表不一致系数， $h$ 代表合并的两个类簇的距离，avg表示下层深度为2的类簇合并时距离平均值，std表示下层深度为2的类簇合并时距离标准差。当两个类簇的不一致系数小于阈值时，将这两个类簇合并为一个新类簇，否则，将两个类簇进行切分。

# 1.5分词算法的性能分析

分词算法性能的优劣往往通过算法复杂度来衡量。其中包括时间复杂度和空间复杂度。机器学习中，由于分词训练过程为一次性行为，分词时并不需要重新训练模型，只需将已训练好的模型用于分词任务。因此，对模型训练所消耗的时间代价关注相对较低，在实际的分词过程中更多的关注分词速度，以及模型存储所占的存储空间。

本节中将重点分析分词过程的时间复杂度。分词过程需要查找模型训练时生成的Look-up表,以及模型参数w。已知需要进行分词的字数为 $\mathrm { ~ m ~ }$ ，Look-up表以及模型参数的数量为n。查找Look-up表和模型参数的时间复杂度均为O(1)。分词时每对一个字进行词位标注时均需要遍历整个Look-up表以及模型参数w。因此，本方法中分词过程的时间复杂度为O(mn)。

与基于字的多模型分词方法相比，本文所提方法的模型数量远远小于基于字的多模型分词方法的模型数量，因此，在时间复杂度与空间复杂度方面均有优势。

# 2 实验及结果分析

# 2.1数据和预处理

本文实验所采用的语料为PKU语料和MSR语料，它们是由SIGHAN举办的第二届国际中文分词评测Bakeoff2005所提供的封闭语料。其中包括训练集、测试集、测试集的标准答案、词典以及评分脚本。其语料详细信息如表2所示。

表2PKU语料和MSR语料的详细信息  
Table 2Corpus details ofPKUand MSR   

<html><body><table><tr><td></td><td>PKU语料</td><td>MSR语料</td></tr><tr><td>词型</td><td>5.5×104</td><td>8.8×104</td></tr><tr><td>词例</td><td>1.1×106</td><td>2.4×106</td></tr><tr><td>字型</td><td>5×10³</td><td>5×10</td></tr><tr><td>字例</td><td>1.8×106</td><td>4.1×106</td></tr></table></body></html>

实验中，在当前待标注字窗口宽度为5的上下文环境中提取特征时，当待标注字为句子开头或结尾字符时，需要在字符的左边(或右边)添加两个诸如“start-1”“start-2”（或“end-1”“end-2”)的字符进行补充，且补充字符的标记状态均为“S”。

# 2.2评价方法

中文分词性能的评价指标通常采用准确率（P）、召回率（R）、F值（F)、未登录词召回率（Roov）、词表词召回率中 $\langle \mathbf { R } _ { \mathrm { I V } } \rangle$ 。具体定义如下：

$$
\mathrm { F } = \frac { 2 \times P \times R } { P + R }
$$

其中：F值作为分词性能评估的主要参考指标；未登录词召回率能够很好的反映模型的泛化能力。

# 2.3实验参数设置

神经网络模型中超参数的选取对分词性能起着显著的影响，模型中各项超参数设置如表3所示。

表3神经网络模型中超参数设置  

<html><body><table><tr><td>参数名称</td><td>值</td></tr><tr><td>学习率</td><td>eta = 0.01</td></tr><tr><td>迭代次数</td><td>iter=100</td></tr><tr><td>损失容忍度</td><td>tol= 0.001</td></tr><tr><td>（正则项系数</td><td>l=1</td></tr><tr><td>特征Embedding 维度</td><td>d= 50</td></tr></table></body></html>

文献[1]中通过大量实验证明，特征Embedding的维度设定为50维，既能保证模型的训练速度又可以保证分词性能。因此，本文实验中将特征Embedding设置成50维。此外，为了防止模型训练过程中因某一错误导致训练无法终止，本文设置两种结束条件，一种为迭代次数，另一种为损失容忍度。当模型训练过程中满足两种情况中的一种，训练过程将停止。

# 2.4实验结果及分析

为了验证本文所提方法的有效性，本文列举了如下几种分词方法进行对比。其中包括CRF分词方法、单模型分词方法、基于字的多模型分词方法以及神经网络分词方法。其中，单模型分词方法是指针对训练语料建立单一模型参数；基于字的多模型分词方法针对每个字建立单独的模型参数；CRF分词方法采用3种策略，分别为2标记和4标记并考虑标记二元转移特征，记为CRF2和CRF4,以及采用2标记方法但不考虑标记二元转移特征，记为CRF。其中，CRF分词实验均采用表1所示的特征模板；神经网络模型中特征Embedding均为随机初始化，进行了如下对比实验。

# 2.4.1聚类算法距离度量方式及阈值选择实验

对基于字的多模型分词方法训练得到的字模型进行层次聚类，目的是将具有相同或相近构词规律的字聚合为一类，形成字的类簇。因此，得到聚类结果的好坏直接影响后续模型的再训练。表4、5展示了使用不同距离度量方式得到的实验结果。

表4在PKU语料中使用不同距离度量方式的实验结果

Table 4Performances of using different distance metrics in PKU test set   
Table 5Performances of using different distance metrics in MSR test set   

<html><body><table><tr><td rowspan="2">距离度量方式</td><td colspan="5">PKU语料</td></tr><tr><td>P</td><td>R</td><td>F</td><td>Roov</td><td>Riv</td></tr><tr><td>欧式距离</td><td>93.8</td><td>92.6</td><td>93.2</td><td>65.8</td><td>94.2</td></tr><tr><td>余弦相似度</td><td>94</td><td>92.9</td><td>93.5</td><td>66.4</td><td>94.5</td></tr></table></body></html>

从表4、表5中可以看出，在两种语料中使用余弦相似度作为距离度量方式表现出最佳的分词结果。余弦相似度计算的为两个向量夹角的大小，反映两个向量之间的相似程度，而欧式距离则是度量两个向量之间位置的绝对距离。本文的聚类对象为模型参数，该向量反映了字的上下文特征对该字标注状态的作用程度，代表了该字的构词规律，使用余弦相似度作为距离度量方式更为合理。表6展示了使用余弦相似度作为距离度量方式下的聚类结果。

Table 3Setting of the hyper-parameters   
表5在MSR语料中使用不同距离度量方式的实验结果  

<html><body><table><tr><td rowspan="2">距离度量方式</td><td colspan="5">MSR 语料</td></tr><tr><td>P</td><td>R</td><td>F</td><td>Roov</td><td>RIv</td></tr><tr><td>欧式距离</td><td>95.5</td><td>95.5</td><td>95.5</td><td>53.9</td><td>96.6</td></tr><tr><td>余弦相似度</td><td>95.6</td><td>95.6</td><td>95.6</td><td>55.9</td><td>96.6</td></tr><tr><td>表6 Table 6</td><td colspan="4">与“吴”“鸯”“扒”“蚣”相近的字 Characters similarto“吴""鸯""扒”“蚣”</td></tr><tr><td>字</td><td>距离度量方式</td><td></td><td>构词规律相近的字</td><td></td></tr><tr><td>吴 鸯</td><td></td><td></td><td>赵、彭、徐、卢、蔡 鸠、鹉、鹃、鹊、鸪</td><td></td></tr><tr><td></td><td>余弦相似度</td><td></td><td></td><td></td></tr><tr><td>扒</td><td></td><td></td><td>扔、扛、扭、抛、抢</td><td></td></tr><tr><td>蚣</td><td></td><td></td><td>蟀、蜓、蟾、蛾、螂</td><td></td></tr></table></body></html>

如表6所示，“吴”为姓氏，通过聚类得到与之相近的几个字中“赵”“彭”“徐”“卢”“蔡”也作为姓氏，具有相同的构词规律。同理，“鸯”、“扒”、“蚣”分别作为鸟类名称、动词、昆虫名称，分别得到与之对应的类别字组成的字簇。说明对基于字的多模型分词方法学习出的模型参数进行聚类分析可以有效地获得相同或相近构词规律的字簇。

与K-Means聚类方法有所不同，层次聚类无须事先指出具体的聚类个数，而是通过设定不一致系数阈值得到最优的类簇，因此，不一致系数阈值的设定对实验结果有一定的影响。图3展示了使用不同的不一致系数得到的实验结果。

![](images/7a5193332b4c096f586a09615d625f023f7f5c4124169c5e919352408f30871f.jpg)  
图3不一致系数阈值对分词性能影响  
Fig.3Performance of using different inconsistentcy

从图3中可以看出，在两种语料中，使用层次聚类算法对基于字的多模型分词方法训练得到的模型参数进行聚类分析，不一致系数阈值设定为1时，得到最优的聚类结果，分词效果最佳。因此，在接下来的分词实验中将继续使用不一致系数阈值为1的这一设置。

# 2.4.2模型对比实验

表7、8给出了本文所提出方法与单模型方法、基于字的多模型方法实验对比结果。从中可以看出，在两种语料上，本文所提出的方法表现出较优越的分词性能。其中，在PKU语料上，F值高于单模型1.2个百分点，高于多模型0.1个百分点；在MSR语料上，F值高于单模型4.4个百分点，高于多模型0.1个百分点，表现出足够的稳定性。单模型方法在未登录词识别方面表现出明显的优势，考虑上下文环境对所有字的全局综合作用，学习出字构词的一般性规律；而多模型针对每个字进行建模，学习出字构词的特殊性规律，因而在词表词召回率方面表现出强有力的优势。本文方法通过对模型参数聚类，将两种建模思想进行结合，即学习出一般性构词规律又学习出特殊性构词规律，则分词效果优于其他两种方法。

Table 7Comparison with performance on PKU corpus   

<html><body><table><tr><td rowspan="2">模型</td><td colspan="5">PKU 语料</td></tr><tr><td>P</td><td>R</td><td>F</td><td>Roov</td><td>Riv</td></tr><tr><td>单模型</td><td>93.3</td><td>91.7</td><td>92.3</td><td>71.2</td><td>93.0</td></tr><tr><td>多模型</td><td>93.9</td><td>92.8</td><td>93.4</td><td>65.6</td><td>94.5</td></tr><tr><td>this approach</td><td>94</td><td>92.9</td><td>93.5</td><td>66.4</td><td>94.5</td></tr></table></body></html>

表8在MSR语料上的实验结果对比

表7在PKU语料上的实验结果对比  

<html><body><table><tr><td rowspan="2">模型</td><td colspan="5">MSR 语料</td></tr><tr><td>P</td><td>R</td><td>F</td><td>Roov</td><td>RIv</td></tr><tr><td>单模型</td><td>91.8</td><td>90.6</td><td>91.2</td><td>60</td><td>91.4</td></tr><tr><td>多模型</td><td>95.4</td><td>95.5</td><td>95.5</td><td>53.8</td><td>96.6</td></tr><tr><td>this approach</td><td>95.6</td><td>95.6</td><td>95.6</td><td>55.9</td><td>96.6</td></tr></table></body></html>

与此同时，本文对比了上述三种分词方法的模型数量，结果展示在表9中。与多模型相比，在PKU语料上，模型数量由4686减少到1854，减少幅度近五分之三；在MSR语料上，模型数量由原来的5151减少到2299，减少幅度近二分之一。说明本文的实验方法在提高F值的同时，大幅度减少模型数量，节约了模型存储成本。

<html><body><table><tr><td rowspan="2">模型</td><td colspan="2">PKU 语料</td><td colspan="2">MSR语料</td></tr><tr><td>F值</td><td>模型数</td><td>F值</td><td>模型数</td></tr><tr><td>单模型</td><td>92.3</td><td>1</td><td>91.2</td><td>1</td></tr><tr><td>多模型</td><td>93.4</td><td>4686</td><td>95.5</td><td>5151</td></tr><tr><td>this approach</td><td>93.5</td><td>1854</td><td>95.6</td><td>2299</td></tr></table></body></html>

为了进一步验证本文所提方法的有用性，将本文所提分词方法与单模型分词方法、多模型分词方法在分词时间与模型存储所占空间方面进行对比。其中分词时间是指利用已训练好的模型进行分词时所消耗的时间；存储空间则是指模型存储所占空间的大小。实验结果展示在表10中。

表9在两种语料上模型数量对比结果  
表10两种语料上分词时间与模型存储空间比较  
Table 1O Comparison with word segmentation time and model storage   

<html><body><table><tr><td colspan="4">space on two corpora</td></tr><tr><td rowspan="2">模型</td><td colspan="2">PKU 语料</td><td>MSR 语料</td></tr><tr><td></td><td>F 分词时间(ms)存储空间 F</td><td>分词时间(ms)存储空间</td></tr><tr><td>单模型</td><td>92.3</td><td>536 4.3 KB</td><td>91.2 897 4.4 KB</td></tr><tr><td>多模型</td><td>93.4</td><td>1117 20 MB 95.5</td><td>1314 22MB</td></tr><tr><td>this approach 93.5</td><td></td><td>1084 7.9MB 95.6</td><td>1207 9.8 MB</td></tr></table></body></html>

从表10中可以看出，与多模型分词方法相比，本文所提方法在提高分词性能的同时，在分词时间与模型存储空间方面也具有一定的优势，尤其在模型存储空间方面，大幅度节约了存储成本，更有利于工程中实际的分词应用。分析原因，单模型基于训练语料建立单一模型参数，因此所占存储空间最少，分词速度最快；而基于字的多模型分词方法基于每个字进行建模，存在模型的冗余，模型所占存储空间较多；本文所提方法将具有相同或相近构词规律的字合并为字簇，进行模型训练，大大减少了模型数量，与多模型相比，提高分词性能的同时降低了模型存储所占空间。

表11、12比较了该方法与CRF分词方法的实验对比结果，可以看出，CRF采用4标记并加入标记转移特征的模型表现出较好的分词性能。与本文所提出的方法进行对比，在

PKU语料上，本文的方法在5种评价指标中皆高于CRF4方法，其中，F值提升0.4个百分点；但在MSR语料上，CRF4方法分词性能明显优于本文所提出的方法，F值高出0.8个百分点。从MSR语料实验结果中可以看出，CRF4方法与本文方法在词表词召回率方面相差不大，但在未登录词召回率上，CRF4方法明显高于本文方法，导致CRF4方法的最终结果优于本文方法。分析原因，相比PKU语料，MSR语料规模相对较大，CRF4方法训练得更充分，对未登录词识别能力更强。

Table 8Comparison with performance on MSR corpus   
表11在PKU 语料上与CRF实验对比结果  

<html><body><table><tr><td rowspan="2">模型</td><td colspan="5">PKU 语料</td></tr><tr><td>P</td><td>R</td><td>F</td><td>Roov</td><td>Riv</td></tr><tr><td>CRF</td><td>93.3</td><td>90.9</td><td>92.1</td><td>53.0</td><td>93.2</td></tr><tr><td>CRF2</td><td>93.1</td><td>91.2</td><td>92.1</td><td>55.6</td><td>93.3</td></tr><tr><td>CRF4</td><td>94.0</td><td>92.2</td><td>93.1</td><td>61.2</td><td>94.1</td></tr><tr><td>This approach</td><td>94.0</td><td>92.9</td><td>93.5</td><td>66.4</td><td>94.5</td></tr></table></body></html>

表12在MSR语料上与CRF实验对比结果

Table11Comparison with results used CRF on PKU corpus   
Table 12Comparison with results used CRF on MSR corpu:   

<html><body><table><tr><td rowspan="2">模型</td><td colspan="5">MSR语料</td></tr><tr><td>P</td><td>R</td><td>F</td><td>Roov</td><td>RIv</td></tr><tr><td>CRF</td><td>94.9</td><td>95.4</td><td>95.1</td><td>51.0</td><td>96.6</td></tr><tr><td>CRF2</td><td>95.4</td><td>95.1</td><td>95.3</td><td>63.6</td><td>95.9</td></tr><tr><td>CRF4</td><td>96.5</td><td>96.2</td><td>96.4</td><td>70.8</td><td>96.9</td></tr><tr><td>this approach</td><td>95.6</td><td>95.6</td><td>95.6</td><td>55.9</td><td>96.6</td></tr></table></body></html>

表13与前人工作进行对比

Table 9 Comparison with model numbers on two corpora   
Table 13Comparision with previous models   

<html><body><table><tr><td rowspan="2">模型</td><td colspan="3">PKU 语料</td><td colspan="3">MSR 语料</td></tr><tr><td>P</td><td>R</td><td>F</td><td>P</td><td>R</td><td>F</td></tr><tr><td>Zheng et al(2013)</td><td>92.8</td><td>92.0</td><td>92.4</td><td>92.9</td><td>93.6</td><td>93.3</td></tr><tr><td>Pei et al.(2014)</td><td>93.7</td><td>93.4</td><td>93.5</td><td>94.6</td><td>94.2</td><td>94.4</td></tr><tr><td>Chen et al.(2015)</td><td>95.8</td><td>95.5</td><td>95.7</td><td>96.7</td><td>96.2</td><td>96.4</td></tr><tr><td>Cai et al.(2016)</td><td>95.5</td><td>94.9</td><td>95.2</td><td>96.1</td><td>96.7</td><td>96.4</td></tr><tr><td>this approach</td><td>94.0</td><td>92.9</td><td>93.5</td><td>95.6</td><td>95.6</td><td>95.6</td></tr></table></body></html>

本文将实验结果与相同数据集上的前人工作进行了对比。如2013年，Zheng等人[18]应用Collobert等人[19]的神经网络框架进行分词；2014年，Pei等人[20]通过利用标签嵌入和基于张量的转换，提出了MMTNN的神经网络进行分词；2015年，Chen等人[21为了解决中文分词中无法长期依赖信息的问题，提出了LSTM神经网络并用于分词；2016年，Cai等人[22]利用门控组合神经网络对字符进行分布式表示，并利用LSTM神经网络对预测结果进行打分。实验结果对比如表13所示。与Zheng 等人相比，本文所提方法在PKU语料上F值提高1.1个百分点，在MSR语料上F值提高2.3个百分点；与Pei等人相比，本文所提方法在PKU语料上F值达到了相一致，在MSR语料上F值高出1.2个百分点。与Chen等人和Cai等人实验结果相比，本文方法的分词性能略显不足。

将本文分词结果与Cai等人的分词结果作进一步对比分析，发现本文所提方法在切分诸如“入/军队”、“服/现役”“战/风雪”、“拟/任”、“求/发展”等单字动词时的切分效果优于Cai等人的分词方法。此外，对本实验中具体的分词结果进行分析发现如表14中所列的切分错误。

# 表14切分结果对比

Table 14Comparison with segmentation results   

<html><body><table><tr><td>正确切分方式</td><td>错误切分方式</td></tr><tr><td>就业/旺季</td><td>就业旺季</td></tr><tr><td>无/党派/人士</td><td>无党派人士</td></tr><tr><td>浙江/海盐县</td><td>浙江海盐县</td></tr><tr><td>世纪/交替</td><td>世纪交替</td></tr></table></body></html>

从上述例子中可以看出，切分结果出现多词粘连的情况。该种切分错误在文献[23]中均有谈到，该文献中通过实验验证了基于字的分词方法往往忽略词所包含的组合信息，指出应用字词联合解码进行分词效果更佳。通过分析本文切分错误结果，同样验证了上述结论，而本文所提出的分词方法，恰好缺少词信息进行分词指导学习，因此出现多词粘连的情况，影响了最终的分词性能。对比Cai等人的分词方法，通过门控组合神经网络对输入的字符序列进行候选词分布式表示，很好地引入了词信息，并用LSTM神经网络对所有切分结果进行打分，取打分最高的切分组合作为最终的分词结果，则最终的分词效果优于本文实验结果。在今后的实验中，本文将借鉴Cai等人的分词方法，引入词信息进行指导学习。

# 3 结束语

本文提出了一种基于字簇的多模型中文分词方法，该方法可以看做单模型与基于字的多模型建模思想的结合，很好地发挥了单模型分词方法发现未登录的作用以及基于字的多模型分词方法切分词表词的作用，学习出字构词的一般性与特殊性构词规律。实验结果表明，与基于字的多模型分词方法相比，该方法在小幅度提升分词性能的同时，有效减少了模型数量，降低了模型存储成本并且提升了分词速度。

通过实验部分分析，本文的分词方法并没有引入词的信息对分词过程进行指导学习，影响了最终的分词性能，有一定的局限性。今后的工作中，可以尝试加入词的信息，提高分词质量；另一方面，本文的方法是利用聚类发现字构词之间分布结构规律，聚类的好坏直接影响分词的效果，今后的工作中可以在算法层面做进一步的尝试，利用多任务学习算法进行分词实验[24-26]。

# 参考文献：

[1]来斯惟，徐立恒，陈玉博，等．基于表示学习的中文分词算法探索 [J]．中文信息学报,2013,27(5):8-14.(Lai Siwei,Xu Liheng,Chen Yubo,et al.Exploring Chinese word segmentation algorithm based on representation learning [J]. Journal of Chinese Information Processing,   
2013,27(5): 8-14.) [2]Xue Neiwen, Shen Libin. Chinese word segmentation as LMR tagging [C]//Proc of the 2nd SIGHAN Workshop on Chinese Language Processing.New York:ACMPress,2003:176-179. [3]McCallum A,Freitag D,Pereira F.Maximum entropy markov models for information extraction and segmentation [C]//Proc of International Conference on Machine Learning.New York:ACM Press，2000:   
591-598. [4]李月伦，常宝宝．基于最大间隔马尔可夫网模型的汉语分词方法 [J]．中文信息学报，2010，24(1):8-14.(Li Yuelun,Chang Baobao. Chinese word segmentation method based on maximum interval markov network model [J].Journal of Chinese Information Processing,   
2010,24 (1): 8-14.) [5]Tseng H,Chang P,Andrew G,et al.A conditional random field word segmenter for sighan bakeoff 2O05 [C]// Proc of the 4th SIGHAN 2005: 168-171.   
[6] Zhang Ruiqiang，Kikui G, Sumita E. Subword-based tagging by conditional random fields for Chinese word segmentation [Cl// Proc of Human Language Technology Conference of the North American Chapter of the ACL. Stroudsbury,PA: ACL,2006: 193-196.   
[7] Zhao Hai,Huang Changning，et al. Effective tag set selection in Chinese word segmentation via conditional random field modeling [C]// Proc of Pacific Asia Conference on Language,Information and Computation.New York: ACM press,2006: 87-94.   
[8] He Jia,Li Guanghong. Research of Chinese word segmentation based on neural network and particle swarm optimization [C]//Proc of the 3th International Conference on Apperceiving Computing and Intelligence Analysis.Piscataway,NJ: IEEE Press,201O: 56-59.   
[9]Zheng Xiaoqing,Chen Hanyang,Xu Tianyu. Deep learning for Chinese word segmentation and POS tagging [C]// Proc of the 18th Conference on Empirical Methods in Natural Language Processing. Stroudsbury, PA: ACL,2013:647-657   
[10] Chen Xinchi, Qiu Xipeng, Zhu Chenxi,et al. Gated recursive neural network for Chinese word segmentation [C]/ Proc of the 53rd Annual Meeting of the Association for Computational Linguistics and the 7th International Joint Conference on Natural Language Processing. Stroudsbury, PA: ACL,2015: 1744-1753   
[11] Cai Deng,Zhao Hai,Zhang Zhisong,et al. Fast and accurate neural word segmentation for Chinese [Cl// Proc of the 55th Annual Meeting of Association for Computational Linguistics. Stroudsbury,PA:ACL, 2017: 608-615.   
[12]韩冬煦，常宝宝．中文分词模型的领域适应性方法[J].计算机学报， 2015，38(2): 272-281．(Han Dongxu,Chang Baobao．Domain adaptation method of Chinese word segmentation model [J]. Chinese Journal of Computers,2015,38(2): 272-281.)   
[13] Qiu.Likun, Zhang Yue.Word segmentation for Chinese novels [C]// Proc of the 29th AAAI Conference on Artificial Intelligence.Menlo Park, CA: AAAI, 2015: 2440-2446.   
[14] 张少阳，王裴岩，蔡东风．一种基于字的多模型中文分词方法[J]. 沈阳航空航天大学学报,2017,34(1):70-75.(Zhang Shaoyang,Wang Peiyan, Cai Dongfeng.A multi-model of Chinese word segmentation based on character [J]. Journal of Shenyang Aerospace University,2017, 34 (1): 70-75. )   
[15] Ma Jianqiang，Hinrichs E.Accurate linear-time Chinese word segmentation via embedding matching [Cl// Proc of the 53rd Annual Meeting of the Association for Computational Linguistics and the 7th International Joint Conference on Natural Language Processing. Stroudsbury,PA: ACL,2015: 1733-1743   
[16]黄昌宁，赵海．中文分词十年回顾[J]．中文信息学报，2007，21(3): 8-19 (Hang Changning， Zhao Hai. Ten years of Chinese participle review [J]. Journal of Chinese Information Processing，20o7,21(3) 8-19.）   
[17]孙吉贵，刘杰，赵连宇．聚类算法研究[J]．软件学报，2008，19(1): 48-61.(Sun Jigui,Liu Jie, Zhao Lianyu. Clustering algorithm research [J]. Journal of Software,2008,19 (1): 48-61.)   
[18] Zheng Xiaoqing,Chen Hanyang,Xu Tianyu.Deep learning for Chinese word segmentation and POS tagging [C]// Proc of the 18th Conference on Empirical Methods in Natural Language Processing. Stroudsbury, PA: ACL,2013: 647-657   
[19] Collobert R,Weston J,Bottou L,et al.Natural language processing (almost) from scratch[J].Journal ofMachine LearningResearch,2011, 12 (1): 2493-2537   
[20] Pei Wenzhe,Ge Tao,Chang Baobao.Max-margin tensor neural network for Chinese word segmentation [C]// Proc of the 52th Annual Meeting of the Association for Computational Linguistics. Stroudsbury,PA: ACL,2014:293-303.   
[21] Chen Xinchi,Qiu Xipeng, Zhu Chenxi,et al. Long short-term memory neural networks for Chinese word segmentation [C]// Proc of the 20th Conference on Empirical Methods in Natural Language Processing. Stroudsbury,PA:ACL,2015:1197-1206.   
[22] Cai Deng,Zhao Hai.Neural word segmentation learning for Chinese [C]// Proc of the 54th Annual Meeting of the Association for Computational Linguistics. Stroudsbury,PA:ACL,2016: 409-420.   
[23]宋彦，蔡东风，张桂平，等．一种基于字词联合解码的中文分词方法 [J]．软件学报，2009,20(9):2366-2375.(Song Yan，Cai Dongfeng, Zhang Guiping,et al.A Chinese word segmentation method based on joint decoding of words [J].Journal of Software，2Oo9，20(9): 2366-2375.)   
[24]Liu Jun,Ji Shuwang，Ye Jieping.Multi-task feature learningvia efficient L2, $^ { 1 }$ -normminimization [C]//Procof Conferenceon Uncertainty in Artificial Intelligence.20o9:339-348.   
[25] Chen Xinchi,Shi Zhan,Qiu Xipeng，et al.Adversarial multi-criteria learning for Chinese word segmentation [C]//Proc of the 55th Annual Meeting of the Association for Computational Linguistics. Stroudsbury, PA:ACL,2017:1193-1203.   
[26] Liu Pengfei,Qiu Xipeng,Huang Xuanjing.Adversarial multi-task learning for textclassification [C]//Proc of the 55th AnnualMeeting of the Association for Computational Linguistics. Stroudsbury,PA:ACL, 2017: 1-10.