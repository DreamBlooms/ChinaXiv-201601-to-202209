# 基于神经网络与领域知识的外交国际合作元素抽取

张子靖ab，万常选a,b，刘德喜ab，刘玉ab，刘喜平ab，江腾蛟ab(江西财经大学a.信息管理学院;b.数据与知识工程江西省高校重点实验室，南昌 330013)

摘要：为了能够实时了解国际双边合作中有价值的信息，高效地智能提取Web外交新闻中的国际合作元素就显得至关重要。将国际合作元素抽取抽象为类似命名实体识别的问题。首先，界定国际合作元素的内涵；其次，提取了蕴涵领域知识的规则；再次，结合神经网络与领域知识提出了面向外交新闻文本的国际合作元素抽取方法；最后，在相同语料库中与神经网络方法以及自身规则组合进行了比较，实验结果表明该方法具有更好的效果。

关键词：国际合作元素；神经网络；序列标注；命名实体识别；Web外交新闻中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.08.0626

# Extraction of diplomatic international cooperation elements based on neural networks and domain knowledge

Zhang Zijinga,b, Wan Changxuanab, Liu Dexiab, Liu $\mathrm { Y u ^ { a , b } }$ , Liu Xipinga,b, Jiang Tengjiaoa,b (a.SchoolofInformationTechnology,b.KeyLaboratoryofData&KnowledgeEngineeing,Jiangxi UniversityofFnance &Economics,Nanchang 330013,China)

Abstract:Inorder togetvaluable informationinbilateralcooperationinrealtime,itisofutmostimportance toeiciently extractinternationalcooperationelements in Webdiplomacynews.This paperabstracted internationalcooperationelement extraction intoaproblemsimilartonamedentityrecognition.Firstofall,itdefinedtheconnotationsof international coperation elements.Secondly,itextractedtherulesthatcontaineddomainknowledge.Then itproposedaframework for extracting intermational cooperation elements for diplomaticnews texts which combined with neural networks anddomain knowledge.Finally,the method was compared withthe neural network method and itsown rulecombination in the same corpus.The experimental results show that the proposed method has better results.

Keywords:international cooperationelements；neural networks；sequence labeling；named entityrecognition；Web diplomatic news

# 0 引言

国际合作元素抽取是自然语言处理(natural languageprocessing,NLP)研究的一个分支领域。抽取方法需要能够智能识别外交新闻文本中出现的国际合作元素，如“一带一路”、农产品深加工、达特卡—克明输变电工程、《中国加入世贸组织议定书》、斯图加特德中友好协会等。研究者可以在此基础上进一步深入挖掘中国国际合作的产业结构、共性产业、新兴产业、优势产业、特色产业、产业合作倾向、产业合作成效、产业迁移和产业合作短板等，从而实现中国国际合作情况的知识发现，为走出去企业提供实时的中国国际合作信息服务，避免中国企业走出去的盲目性。随着网络新闻的发展，以 Web 为载体的外交新闻(简称为 Web 外交新闻)具有真实性、权威性、广泛性、时效性特点。透过中国Web外交新闻这一窗口抽取国际合作元素，可以为中国国际合作情况的知识发现提供新的研究渠道和必要的技术支持。

本文把国际合作元素抽取问题抽象为类似于命名实体识别(named entity recognition,NER)任务。传统的 NER 任务的目标是识别出非结构化文本中的信息单元，包括人名、地名和机构名以及数值表达式(如时间、日期、金额和百分比)等。NER被看做是语言学中的序列标注任务，类似的任务有分词、词性标注以及机器翻译等。

大部分传统且表现较好的序列标注模型是线性统计模型，包括隐马尔可夫场(hiddenMarkovmodel,HMM)和条件随机场(conditional random field,CRF)[1.2]。它们的效果受到人工构建的特征和任务数据集本身特点的影响，如NER的效果会受到分词结果中词性特征的影响。然而，由于人工特征构建过程所需工作量和专业知识较大，使得对此类方法的改进出现了瓶颈。近年来，为了克服传统模型的局限性，随着词向量的出现，非线性的神经网络(neuralnetwork，NN)模型被广泛运用到NLP问题中，在NER任务的处理中已取得了与传统模型方法相媲美的结果[3\~5]。

通过对中国Web外交新闻的阅读和分析，本文提出了国际合作元素的概念，分析了国际合作元素的特点，提取了涵含领域知识的规则；并在此基础上提出了抽取国际合作元素的基本策略：首先，从Web中获取中国外交新闻文本，进行分词处理，并对分词序列进行人工标注；然后，基于Web外交新闻和中文维基百科组成的数据集，训练一个词向量模型;

再次，基于词向量模型通过BiLSTM-CNNs-CRF神经网络结构训练国际合作元素抽取模型，并完成初步抽取；最后，通过分析初步抽取结果，借助外部词典和已提取的规则等领域知识改进抽取结果。

# 1 相关研究

本节简要介绍NLP研究中与神经网络和序列标注任务相关的一些研究进展情况。

在NLP的研究中，卷积神经网络(convolutional neuralnetworks，CNN)、递归神经网络(recurrentneuralnetworks,RNN)和长短期记忆(longshort-termmemory,LSTM)网络的应用较为广泛。文献[5,6]的研究表明，CNN模型在英文文本中可以有效地从单词的字母中提取形态学信息(如单词的前缀或后缀)，并且把它编码为神经网络的表现形式。文献[7]已经证明，RNNs模型虽然在理论上能够获取长距离依存关系，但是实际上由于梯度消失和梯度爆炸的问题，在解决长距离依存问题上遇到了困难。

为了应付梯度消失的问题，LSTM作为RNNs的变体被提出，每个LSTM单元由三种门来保护和控制单元状态，其中，输入门控制输入的幅度，遗忘门控制之前记忆状态的输入幅度，输出门控制最终记忆的输出幅度。LSTM利用了过去的动态时序信息和当前时刻的输入信息预测当前时刻的输出标记。

为了充分利用时间序列信息，文献[8]提出了Bi-LSTM(Bi-directionalLSTM)。Bi-LSTM在处理很多同时需要利用到过去上下文信息和未来上下文信息的任务时，取得了不错的效果。Bi-LSTM的基本思想是将每个序列向前和向后呈现为两个单独的隐藏状态，以分别捕获过去和未来的信息，然后将两个隐藏状态连接起来形成最终输出。

序列标注问题是NLP中的研究热点问题。它的应用范围非常广泛，包括NER、词性(part-of-speech,POS)标注、浅层句法分析和机器翻译等。

文献[9]中提出了一种区别于传统HMM的iHMM(infiniteHMM)方法，并把它应用于词性标注领域；应用iHMM解决了在无监督Markov模型中选择隐藏状态数目的问题；在实验过程中实现了并行iHMM算法，在华尔街日报数据集上应用了两个非参数化(dirichletprocess和pitman-yorprocess)先验；在结果评估中采用聚类评估指标，获得了比之前的工作相同或更好的评估结果；并基于该结果，用评估无监督词性标注标记器的输出替代全监督的词性标注标记器的输出，应用于浅层句法分析任务，取得了比较好的实验结果。

文献[10]将CRF应用于浅层句法分析任务中，并取得了不错的效果；文中提到，基于现代优化算法的改进训练方法，对于实现这样的结果至关重要。在实验过程中对模型和训练方法进行了大范围的比较。

文献[11]提出了一种新的结合Bi-LSTM和CRF的神经网络架构，在没有利用特定语言知识和资源的前提下，在4种语言的NER任务中取得了良好的效果。在文献[11]的神经网络架构基础上，文献[12]添加了一个CNNs网络层，以有效地从单词的字母中提取形态学信息。

现有的机器翻译系统，无论是基于短语的还是基于神经网络的，都几乎完全依赖于具有明确分割的词级建模。文献[13]使用来自WMT15的平行语料库对4 种语言对(En-Cs,En-De，En-Ru 和En-Fi)上的词根级(subword-level)编码器和字符级(character-level)编码器进行评估；实验结果说明，字符级编码器比词根级编码器的效果更好或相当。

# 2 国际合作元素的内涵界定

# 2.1国际合作元素的定义

定义1国际合作元素是指在外交新闻文本中能够直接或间接表明双方或多方合作领域以及合作意向的最大连续字符序列。国际合作元素包含规划名称(简称为规划类)、产业领域名称(简称为产业类)、项目名称(简称为项目类)、协定/协议/合作备忘录等文件名称(简称为协定类)、合作平台名称(简称为平台类)五大类别。

各类别举例如下：

例1近年来，双方加快发展战略对接，不断推进“一带一路”框架下各领域务实合作，产能合作也取得新进展。

规划名称：“一带一路”。

例2中方愿意进口更多吉尔吉斯斯坦的水果、肉类、奶粉等优势农产品，丰富中国居民的餐桌。

产业领域名称：水果、肉类、奶粉、农产品。

例3达特卡—克明输变电工程结束了吉尔吉斯斯坦电力资源分布不均、输送不畅的历史，南北公路竣工后将实现吉尔吉斯斯坦人民天山变通途的梦想，奥什市医院建成后将为南部地区居民提供更加优质的医疗服务。

项目名称：达特卡一克明输变电工程、南北公路、奥什市医院。

例4德方高度赞赏中方支持欧洲一体化，愿进一步推动欧盟履行《中国加入世贸组织议定书》有关承诺，希望欧中投资协定谈判尽快完成。

协定/协议/合作备忘录等文件名称：《中国加入世贸组织议定书》。

例5我宣布，中方将设立中拉产能合作专项基金，为此提供300亿美元融资，支持中拉产能合作项目。

合作平台名称：中拉产能合作专项基金。

在外交新闻中并非所有句子都包含国际合作元素，将包含国际合作元素的句子称为外交合作句，反之则称为非外交合作句。根据以上定义，把从外交合作句中抽取国际合作元素的问题抽象为一个类似于序列标注任务，即在已经进行过分词处理的句子中找出最符合要求的标注序列。

# 2.2国际合作元素的特点

国际合作元素的抽取虽然与NER有相似之处，但国际合作元素本身具有很多一般命名实体不具备的特点。具体分析如下：

a)国际合作元素中可能包含标点或特殊符号，而这些标点和特殊符号经常会成为划分国际合作元素的边界标志。

例6为延续业已开展35年的合作，双方商定，在中国计量科学研究院与德国联邦物理技术研究院2014年4月签署的中德计量合作协议框架下，加强在质量、时间、温度法制计量标准领域的交流。

例7在此基础上，双方致力于深化工业、城镇化及农业等领域的创新合作，并在此框架下共同应对可持续发展和全球公共产品保护的任务及挑战。

例6中，“质量、时间、温度法制计量标准”联合起来被看做是国际合作元素中产业类别的1个实例，在这一实例中包括2个顿号。而例7中的工业、城镇化、农业被看做是国际合作元素中产业类别的3个实例，而这3个国际合作元素被顿号分割。

b)相同的国际合作元素在不同的语境下可能被划分为不同的类别。

例8在今年6月召开的中阿合作论坛第六届部长级会议上， 主席提出了中国同阿拉伯国家共建“丝绸之路经济带”和“21世纪海上丝绸之路”的宏伟构想。

例9 表示，中方建设21世纪海上丝绸之路的倡议同印尼发展战略有契合之处。

例8中，21世纪海上丝绸之路被看做是国际合作元素中平台类别的1个实例。而例9中，将21世纪海上丝绸之路分类为国际合作元素中规划类别的1个实例，则更符合语境。

c）内涵更大的国际合作元素中可能包含内涵更小的国际合作元素。

例 10不少非洲国家领导人都提出扩大中非高速公路合作、建设高速公路网的愿望，中方对此给予积极支持，愿与非方加强合作，促进非洲高速公路逐步连接成网。

例10中，高速公路、高速公路网能够被看做是国际合作元素中产业类别的两个实例，其中，高速公路的内涵更小，它包含于内涵更大的高速公路网中。

由于国际合作元素的以上特点，抽取结果中会出现以下部分情况：

a)本应对称出现的标点符号在抽取结果中未成对出现，例如：0、《》以及双引号，本文将此类现象称为“不规范抽取”问题；

b)抽取结果仅仅是真实结果中的子部分，同时抽取结果与真实结果在国际合作元素的分类上相同，本文将此现象称为“未完全抽取”问题；

c)在初步抽取过程中，真实结果中的1个国际合作元素的全部或部分可能被分割为2个或多个国际合作元素，同时分割产生的国际合作元素与真实结果的类别相同，本文将此现象称为“分割抽取”问题；

d)抽取的国际合作元素完全正确，但在分类时出现错误，即“分类错误”问题；

e)真实结果中的国际合作元素并未在抽取结果中出现，即“完全未抽取”问题；

f)与e)相反，抽取结果中出现的国际合作元素并不是真实的国际合作元素，即“完全抽取错误”问题。

# 3 领域知识的提取

针对2.2节中提到的国际合作元素本身的特点，本文发现并提取了以下涵含领域知识的规则：

规则1抽取结果中，0、《》以及双引号必须成对出现，如果抽取结果收到影响，必须对抽取结果作出相应调整。

规则2开始词和结束词为出现在国际合作元素边缘但在初步抽取中未被抽取的词语。如果满足规则1的抽取结果$\boldsymbol { r }$ 至少包含2个词，则在左边补充开始词(B)、右边补充结束词(E)。如果BrE， $\mathbf { B } r$ ，rE之一出现在原句子中，则把扩充后的结果作为新的抽取结果；如果出现不止1类，则取长度较长者作为结果。

规则3中间词为出现在较长的国际合作元素中但在初步抽取中“分割”了国际合作元素的词语。记 $R _ { i } = \{ r _ { i , j } | 1 { \leq } i { \leq } m$ $1 { \le } j { \le } n _ { i } , r _ { i , j }$ 是满足规则1并已经过规则2处理的第 $i$ 个句子中包含的第 $j$ 个国际合作元素， $\mathbf { \nabla } _ { m }$ 为句子个数， ${ { n } _ { i } }$ 为第 $i$ 个句子中包含的国际合作元素个数}，对于 $R _ { i }$ 中每个至少包含2个词的国际合作元素，按照出现位置把与其相邻的国际合作元素从左到右和其两两组合，并在其中插入中间词(M)，即$r _ { i , j } \mathbf { M } r _ { i , j + 1 }$ ，不考虑中间词(M)的情况下则为 $r _ { i , j } r _ { i , j + 1 }$ ，统一记为$r _ { i , j } ( \mathbf { M } ) r _ { i , j + 1 }$ 。如果 $r _ { i , j } ( \mathbf { M } ) r _ { i , j + 1 }$ 出现在原句中，则把 $r _ { i , j } ( \mathbf { M } ) r _ { i , j + 1 }$ 替代 $r _ { i , j } r _ { i , j + 1 }$ 作为新的抽取结果。

为了更好地表述规则4，先定义触发词和边界标志如下。

定义2触发词是与某类国际合作元素搭配出现或包含在国际合作元素内，并可用于判别国际合作元素类别的词语或词组。根据触发词出现的位置，可把触发词分为3类：出现在国际合作元素左侧的称为前触发词，出现在国际合作元素右侧的称为后触发词，出现在国际合作元素内部的称为内触发词。

定义3边界标志是用以决定前触发词、后触发词与国际合作元素共现窗口大小的符号或词语，多为标点符号，少数情况为长句中能缩小范围的词语。共现窗口是指边界标志首端到国际合作元素末端(前窗口)或国际合作元素首端到边界标志末端(后窗口)。

规则4对于每个抽取结果，在其前窗口查找前触发词，若找到，则改变抽取结果的类别；反之，则保留原结果。后窗口同理。内触发词则在国际合作元素中查找。三种触发词的优先级(即决定权)由高到低依次为内触发词、前触发词、后触发词。

对于以上四条规则，规则1是为了解决初步抽取结果中出现的“不规范抽取”问题，规则2、规则3和规则4则是利用领域知识、通过不同的处理方式分别解决初步抽取结果中出现的“未完全抽取”“分割抽取”“分类错误”3类问题。

最后，对于“完全未抽取”“完全抽取错误”2类问题，由于缺乏必要的线索，无法在初步抽取结果的基础上通过领域知识而解决，因此不属于本文研究的范畴。

# 4 国际合作元素的抽取方式

国际合作元素的抽取与序列标注任务具有相似的特点；但是相比传统序列标注任务，国际合作元素抽取任务涉及的类别较多，且长度分布不均匀，这使得一般的序列标注方法抽取得到的结果仍然有改进的余地。从元素类别来说，国际合作元素的类别较多且类别的分类以“语义”为标准，相比传统的人名地名识别的分类更为困难；从元素长度而言，国际合作元素的长度(词语个数)分布不均匀，如例6中的“质量、时间、温度法制计量标准”不仅包含多个词语而且还包含标点符号。为了兼顾以上两点，本文的抽取策略是：首先，采用近期在序列标注任务上表现优异的神经网络模型对国际合作元素进行初步抽取；然后，将初步抽取的结果作为输入，借助已提取的领域知识规则对抽取结果进行优化，并把优化结果作为最后的输出结果。方法框架如图1所示，对应算法1和2。

算法1基于神经网络的国际合作元素抽取输入：已训练好的神经网络模型，已进行分句和分词处理的文件。

输出：初步抽取结果。

for 测试集中的一个批次(batch)的每一个句子(s){for 句子(s)中的每一个词语 $( x _ { t } )$ 1$/ { * }$ 在词向量文件(WV)中查找词语 $x _ { t }$ 所对应的词向量表示 $^ { * } I$ word_embedding $\cdot \gets \mathrm { W V } [ x _ { t } ]$ $/ *$ 使用w2c方法计算词语 $x _ { t }$ 的字符表示 \*/char_representation $\mathbf { \sigma } _ { : } \gets \mathbf { w } 2 \mathbf { c } ( x _ { t } )$ $/ { ^ { * } }$ 拼接word_embedding 和 char_representation 作为词语 $x _ { t }$ 的神经网络的输入\*/embedding $$ concat(word_embedding,char_representation);$/ { ^ { * } }$ 前向过程：决定什么信息应该被神经元遗忘 $^ { * } I$ $\mathbf { \mathit { f f } } _ { t }  \sigma \mathbf { ( \mathit { W } _ { \mathit { f f } } \cdot [ h _ { \mathit { t - 1 } } , x _ { t } ] + \mathbf { \mathit { b } _ { \mathit { f f } } } ) } ;$ $/ *$ Sigmod层决定要更新的数值\*/

$\pmb { \mathscr { f } } _ { t }  \sigma ( W _ { \hbar } \cdot [ h _ { t - 1 } , x _ { t } ] + b _ { \hbar } ) \ ;$ （204号  
$/ { * }$ tanh 层生成新的候选数值， $f C _ { t }$ 会被增加到神经元状态中 $^ { * } I$   
$f C _ { \iota } \gets \operatorname { t a n h } \left( W _ { f C } \cdot \left[ h _ { t - 1 } , x _ { \iota } \right] + b _ { f C } \right) ;$   
$/ { ^ * }$ 更新旧的神经元状态 $f C _ { { t - 1 } }$ 到新的神经元状态 $f C _ { t }$ \*/  
$\mathbf { \Delta } f C _ { t } \gets f f _ { t } \ast \mathbf { \Delta } f C _ { t - 1 } + \mathbf { \mathscr { f } } \bot \ast \mathbf { \Delta } f C _ { t } \ ;$   
$/ *$ 使用 sigmod 层决定哪一部分的神经元状态需要被输出\*/  
$f o _ { t } \gets \sigma \big ( W _ { f o } \cdot [ h _ { t - 1 } , x _ { t } ] + b _ { f o } \big ) ;$

$/ { ^ { * } }$ 让神经元状态 $f C _ { \iota }$ 经过tanh（使输出值变为-1\~1之间）层，并 /

乘以sigmod门限的输出 $f { \pmb { \theta } } _ { t }$ 后作为前向过程的最终结果\*/$\pmb { \mathscr { h } } _ { t } \gets \operatorname { t a n h } ( \pmb { \mathscr { f } } C _ { t } ) \pmb { \mathscr { f } } \pmb { \mathscr { o } } _ { t } \ ;$ （20$/ { ^ { * } }$ 后向过程：计算方法与前向过程相同，只是计算方向相反；此处只给出后向过程的最终结果 $^ { * } I$ $b h _ { t } \gets \operatorname { t a n h } ( b C _ { t } ) b o _ { t } ;$ （20$/ { ^ { * } }$ 拼接前向过程与后向过程的结果，再用模型中的权重矩阵W和偏置矩阵 $\textbf { \textit { b } }$ 计算出未解码的output $^ { * } I$ $o u t p u t \gets \mathrm { c o n c a t } ( \textit { f } \pmb { h } _ { t } , \textit { b } \pmb { h } _ { t } ) \boldsymbol { W } + \boldsymbol { b } ;$ （2041$/ *$ 使用条件随机场进行解码，trans_params 为模型中的转移矩阵，pre_tags为句子对应的标签序列\*/pre_tags $$ crf_decode(output,trans_params);

![](images/7d7f8a298eb9a98626ef435b0f82cbf2f9026247ace95d65dcf095387e0b473b.jpg)  
图1抽取国际合作元素的方法框架

Fig.1Methodological framework for extracting international cooperation elements

算法2基于领域知识的优化  
输入：一个句子的神经网络的抽取结果(词语-标记)，开始结束词集合，中间词集合，边界标志集合以及触发词集合。  
输出：最终抽取结果(词语-标记)。  
$/ { ^ * } 1 \}$ 规范化\*/  
while(句子sentence中找到了未匹配的“《》”，“("或双引号){$/ { ^ * }$ 查找句子sentence中未匹配的“《》”，“(”或双引号，并返回第一次出现的位置 \*/spot $$ symbolmatch(sentence);if(未匹配的符号被标记为“其他”）{删除该词语-标记对;1else if(未匹配的符号被标记为国际合作元素的“开始”）{找到对应元素的末尾，添加对应符号，并修改标记;1else {找到对应元素的开始，添加对应符号，并修改标记;1  
1  
$/ * 2 )$ 扩充元素 $^ { * } I$   
for 句子中的每一个国际合作元素{if(国际合作元素至少包含两个分词){if(国际合作元素的前一个词出现在开始词集合中，且后一个词出现在结束词集合中){$N E \gets B + r + E ;$ （2041else if(国际合作元素的前一个词出现在开始词集合中){$N E \gets B + r ;$ （204号

}else if(国际合作元素的后一个词出现在结束词集合中){$N E \gets r + E ;$ （20411}$/ \ast _ { 3 ) }$ 合并元素 $^ { * } I$ for 句子中的每一个国际合作元素{if(国际合作元素至少包含两个分词){if(该国际合作元素之后仍存在其他国际合作元素){$M \gets$ 该国际合作元素与下一个国际合作元素中间的部分；if( $M$ 出现在了中间词集合中){$N E \gets r _ { i } + M + r _ { i + 1 } ;$ 1111$/ { ^ * 4 } )$ 修正分类\*/找出句子中包含的所有边界标志;通过边界标志和国际合作元素的位置明确句子中的窗口位置和大在每个窗口中查找触发词;根据触发词的优先级更新国际合作元素的类别；

# 4.1神经网络层的训练

在神经网络层中，采用CNNs-BiLSTM-CRF[I2]结构获取初步的序列标注结果。其中，CNNs层是利用每个词中的每个字对应的字向量，通过CNNs结合后得到一个词的字符表示(charrepresentation)，其网络结构如图2所示；BiLSTM层的输入是每个词的词向量表示(word embedding)以及其对应的字符表示的连接，输出为每一个词对应的标注状态；对于序列标注任务，CRF层在考虑邻域中标签之间的相关性、并对给定输入句子的最佳标注链进行联合解码时的帮助很大。

![](images/62b094c367b111496a80eaf2d4e275c642b4c2cc9a6ee33472398528bf11f53a.jpg)  
图2得到词的字符表示的CNN网络结构  
Fig.2CNN network structure for character representation of words

在CNNs-BiLSTM-CRF模型的训练过程中，本文所使用的参数与文献[12]中略有不同。具体的参数选择情况如表1所示。其中，adam为学习率(learning rate)优化时所采用的一种利用一阶导数的优化算法，此类算法的选择会影响到batchsize 在数量级上的选择，在综合各类因素后batchsize最终取值为20；gradientclipping取值为-1(小于O)表示不使用gradient clipping。

Table 1Parameter selection of neural network layer training   

<html><body><table><tr><td>层</td><td>超参数</td><td>值</td></tr><tr><td rowspan="2">CNN</td><td>window size</td><td>3</td></tr><tr><td>number of filters</td><td>30</td></tr><tr><td rowspan="2">LSTM</td><td>state size</td><td>300</td></tr><tr><td>initial state</td><td>0</td></tr><tr><td rowspan="2">dropout</td><td>peepholes</td><td>No</td></tr><tr><td>dropout rate</td><td>0.5</td></tr><tr><td rowspan="4">Other parameter</td><td>batch size</td><td>20</td></tr><tr><td>initial learningrate</td><td>0.001</td></tr><tr><td>decay rate</td><td>0.9</td></tr><tr><td>gradient clipping</td><td>-1</td></tr><tr><td></td><td>learning rate method</td><td>Adam</td></tr></table></body></html>

# 4.2基于领域知识的优化

在分析了由神经网络层抽取到的初步结果后，本文发现初步抽取结果中仍然存在着2.2节中所提到的6类问题。其中，造成“不规范抽取”问题的原因有两个，一是数据集本身出现特殊符号未配对现象；二是抽取过程中丢失符号。此类问题是底层的抽取错误，可能会对后续优化过程产生影响，因此必须首先对初步抽取结果进行规范化处理。在规范化处理中，要保证抽取结果中特殊符号的出现必须与数据集中包含的特殊符号“同步”，即如果数据集中特殊符号配对出现，则抽取结果中特殊符号也必须配对出现；否则，抽取结果中不出现特殊符号。规范化处理对应于第3节中的规则1。

对于“未抽取完全”和“分割抽取”2类问题，虽然它们都已经抽取到了真实结果的组成部分，但是这样的结果并不完整，并不是真正的国际合作元素。然而，正因为它们抽取到了真实结果的组成部分，才提供了针对初步抽取结果进行“扩充”与“合并”来优化抽取结果的机会。“扩充”与“合并”的具体策略对应于第3节中规则2和规则3。

在优化了“未抽取完全”和“分割抽取”两类问题之后会产生新的国际合作元素，而在新国际合作元素和原国际合作元素中仍然会存在“分类错误”问题。为此本文提出了相应的优化策略，对应于第3节中的规则4。

# 5 实验结果与分析

# 5.1实验数据集和环境

实验部分使用到的第1部分数据是中国Web外交新闻数据集，它来源于中国外交部网站1提供的中国驻各国使馆新闻文本。首先，针对获取的中国Web外交新闻数据集，利用哈工大提供的LTP分词工具依次进行分句、分词处理；然后，根据任务需求对分词结果进行人工标注。本文选用3个人作为数据集的标注者，以少数服从多数决定正确答案；当出现无法决定的情形，则由3人讨论并经本文确认标注结果。3个人的组成为2位本科生和1位研究生，且都有财经基础课程学习经历。

依据句子中是否包含国际合作元素，可分为外交合作句和非外交合作句。中国Web外交新闻数据集中共有10030个外交合作句，可作为抽取国际合作元素的数据集，记为dataSeti。实验部分使用到的第2部分数据是中文维基百科的网页数据集，记为dataSet2。

在实验过程中，训练集、验证集和测试集的划分如下：将dataSeti中的8000个、1000个和1030个句子分别作为训练集、验证集和测试集。在训练集、验证集和测试集中，人工标注的5种类别国际合作元素的统计数据如表2所示。

# 表2数据集中不同类别国际合作元素的统计结果

表1神经网络层训练的参数选择  
Table 2Statistical results of different types of international cooperation elements in the dataset   

<html><body><table><tr><td rowspan="2">类别</td><td colspan="2">训练集</td><td colspan="2">验证集</td><td colspan="2">测试集</td><td colspan="2">合计</td></tr><tr><td>数量/个</td><td>占比/%</td><td>数量/个</td><td>占比/%</td><td>数量/个</td><td>占比/%</td><td>数量/个</td><td>占比/%</td></tr><tr><td>规划</td><td>516</td><td>3.36</td><td>62</td><td>3.11</td><td>132</td><td>3.28</td><td>710</td><td>3.32</td></tr><tr><td>产业</td><td>10087</td><td>65.63</td><td>1333</td><td>66.78</td><td>2690</td><td>66.89</td><td>14110</td><td>65.97</td></tr><tr><td>项目</td><td>1655</td><td>10.77</td><td>228</td><td>11.42</td><td>426</td><td>10.59</td><td>2309</td><td>10.80</td></tr><tr><td>协定</td><td>618</td><td>4.02</td><td>66</td><td>3.31</td><td>151</td><td>3.75</td><td>835</td><td>3.90</td></tr><tr><td>平台</td><td>2493</td><td>16.22</td><td>307</td><td>15.38</td><td>623</td><td>15.49</td><td>3423</td><td>16.01</td></tr><tr><td>合计</td><td>15369</td><td>100</td><td>1996</td><td>100</td><td>4022</td><td>100</td><td>21387</td><td>100</td></tr></table></body></html>

在第3节中提到的开始词、结束词、中间词、触发词以及边界标志均从人工构建的词典中获得。其中，开始词和结束词分别提取了46个和62个词语；中间词共提取了12个词语；触发词共提取了27个词语；边界标志共提取了4个标点符号和6个词语。

实验环境：HPZ840 图形工作站，采用Python 语言，并使用谷歌提供的TensorFlow深度学习框架。实现方案：参考了TensorFlow训练神经网络模型的标准机制，即网络结构设计与数据流独立；在神经网络初步抽取之后，根据提取的领域知识，逐个优化领域知识的实现。

# 5.2实验设计与实验结果分析

本节首先对第3节中提取出的领域知识在数据集中的影响范围进行分析；然后再针对本文方法与CNNs-BiLSTM-CRF[12]模型抽取国际合作元素的精确率 $P$ 、召回率 $R$ 以及 $F 1$ 值进行实验对比分析。

1)领域知识的提取效果

领域知识的提取效果如表3所示，分析结果是基于dataSeti进行的。其中，规则1用于规范化初步抽取结果，规则2和规则3用于弥补由“未抽取完全”和“分割抽取”问题带来的抽取错误，规则4则用于改进“分类错误”问题。

表3领域知识的提取效果分析

Table 3Analysis on extraction effect of domain knowledge   

<html><body><table><tr><td colspan="5">规则 问题数量/个 发现数量/个 纠正数量/个 发现率/% 纠正率/%</td></tr><tr><td>规则1</td><td>24</td><td>24</td><td>23</td><td>100 95.83</td></tr><tr><td>规则2</td><td>448</td><td>501</td><td>389 89.42</td><td>77.64</td></tr><tr><td>规则3</td><td>92</td><td>118</td><td>81 77.97</td><td>68.64</td></tr><tr><td>规则4</td><td>601</td><td>738</td><td>549 81.44</td><td>74.39</td></tr></table></body></html>

由于4条规则均是为优化神经网络层的抽取结果而提出的，前题是保证在不影响神经网络层已抽取正确结果的前提下，尽可能准确地弥补或改进错误，因此一般的规则评价标准并不适用于此类情况。于是本文提出用如下两个指标来评价领域知识的提取效果。

发现率 $\ L =$ 真实问题个数/发现问题个数 $* 1 0 0 \%$

纠正率 $\ c =$ 纠正问题个数/发现问题个数 $* 1 0 0 \%$ 其中，发现率用来评测规则是否能够尽可能多地发现错误结果，而不去影响正确结果；纠正率用来评价规则所发现的错误是否能够被尽可能多地纠正。

2)国际合作元素的抽取效果

具体的实验过程如下：首先，利用dataSeti和 dataSet2训练出一个300维的词向量；然后，将词向量、训练集和验证集作为输入，通过网络模型训练出一个国际合作元素的标注模型；最后，可以评估出测试集在标注模型上的表现，如表4所示。本文方法的实验结果如表5所示。

Table4Experimental Results of the CNNs-BiLSTM-CRF model   
表5本文方法的实验结果  

<html><body><table><tr><td>类别</td><td>P/%</td><td>R/%</td><td>F/%</td></tr><tr><td>规划</td><td>88.33</td><td>77.94</td><td>82.81</td></tr><tr><td>产业</td><td>88.75</td><td>90.06</td><td>89.40</td></tr><tr><td>项目</td><td>69.47</td><td>66.00</td><td>67.69</td></tr><tr><td>协定</td><td>72.83</td><td>79.76</td><td>76.14</td></tr><tr><td>平台</td><td>83.02</td><td>85.13</td><td>84.06</td></tr><tr><td>合计</td><td>85.32</td><td>86.08</td><td>85.70</td></tr></table></body></html>

表4CNNs-BiLSTM-CRF模型的实验结果  
Table 5Experimental results of the proposed model   

<html><body><table><tr><td>规则</td><td>类别</td><td>P/%</td><td>R/%</td><td>F1%</td></tr><tr><td rowspan="6">规则1</td><td>规划</td><td>90.00</td><td>79.41</td><td>84.38</td></tr><tr><td>产业</td><td>88.75</td><td>90.06</td><td>89.40</td></tr><tr><td>项目</td><td>69.47</td><td>66.00</td><td>67.69</td></tr><tr><td>协定</td><td>72.83</td><td>79.76</td><td>76.14</td></tr><tr><td>平台</td><td>83.18</td><td>86.08</td><td>84.60</td></tr><tr><td>合计</td><td>85.39</td><td>86.28</td><td>85.83</td></tr><tr><td rowspan="6">规则2 规则3</td><td>规划</td><td>90.16</td><td>80.88</td><td>85.27</td></tr><tr><td>产业</td><td>89.10</td><td>90.28</td><td>89.69</td></tr><tr><td>项目</td><td>72.73</td><td>72.00</td><td>72.36</td></tr><tr><td>协定</td><td>78.49</td><td>86.90</td><td>82.49</td></tr><tr><td>平台</td><td>85.54</td><td>87.97</td><td>86.74</td></tr><tr><td>合计</td><td>86.51</td><td>87.66</td><td>87.08</td></tr><tr><td rowspan="6">规则4</td><td>规划</td><td>88.52</td><td>79.41</td><td>83.72</td></tr><tr><td>产业</td><td>88.70</td><td>90.13</td><td>89.41</td></tr><tr><td>项目</td><td>69.79</td><td>67.00</td><td>68.37</td></tr><tr><td>协定</td><td>74.19</td><td>82.14</td><td>85.27</td></tr><tr><td>平台</td><td>84.47</td><td>86.08</td><td>84.06</td></tr><tr><td>合计</td><td>85.60</td><td>86.53</td><td>86.06</td></tr><tr><td rowspan="6">所有规则结合</td><td>规划</td><td>90.00</td><td>92.65</td><td>91.30</td></tr><tr><td>产业</td><td>89.27</td><td>90.65</td><td>89.95</td></tr><tr><td>项目</td><td>75.36</td><td>79.50</td><td>77.37</td></tr><tr><td>协定</td><td>80.21</td><td>91.67</td><td>85.56</td></tr><tr><td>平台</td><td>87.35</td><td>91.77</td><td>89.51</td></tr><tr><td>合计</td><td>87.16</td><td>89.83</td><td>88.48</td></tr></table></body></html>

为了综合并直观地对所有的实验结果进行对比分析，将本文方法与CNNs-BiLSTM-CRF模型的实验结果(考虑 $F 1$ 值)通过柱状图进行比较直观的比对分析，结果如图3所示。

从图3可以看出，本文采用基于领域知识的优化策略，对提高CNNs-BiLSTM-CRF模型的 $F 1$ 值有明显的效果。规划类别的 $F 1$ 值提高了8.49个百分点，提高率为 $1 0 . 2 5 \%$ ；产业类别的 $F 1$ 值提高了0.55个百分点，提高率为 $0 . 6 2 \%$ ；项目类别的 $F 1$ 值提高了9.68个百分点，提高率为 $1 4 . 3 0 \%$ ；协定类别的 $F 1$ 值提高了9.42个百分点，提高率为 $1 2 . 3 7 \%$ ；平台类别的 $F 1$ 值提高了5.45个百分点，提高率为 $6 . 4 8 \%$ 。

![](images/edb76a5369d33af8fecb2b42b49cf406a4f688450ee9e5f11c038aa3dd0f156f.jpg)  
图3采用基于领域知识的优化策略对提高CNNs-BiLSTM-CRF模型 $F 1$ 值的对比分析  
Fig.3Comparative analysis for improving $F 1$ of the cnns-bilstm-CRF model using the optimization strategy based on domain knowledge

从产业类别来看，领域知识对该类别的影响最小，使得领域知识在该类别上的优化效果很低，原因主要有3点：一是产业类别的国际合作元素的词长都较短，因此CNNs-BiLSTM-CRF模型对产业类别的国际合作元素的抽取效果较好(F1值为 $8 9 . 4 0 \%$ ；二是在数据集中产业类别的国际合作元素总量较多(占总量的 $6 5 . 9 7 \%$ )，CNNs-BiLSTM-CRF模型对于产业类别的国际合作元素的训练效果较好；三是"扩充”与“合并”规则主要是用于优化较长的国际合作元素(要求词长不小于2)的抽取效果。

对于项目类别，相比其他类别而言，尽管领域知识使得抽取结果的 $F 1$ 值得到了最大程度的优化( $F 1$ 值提高了$1 4 . 3 0 \%$ ，但由于CNNs-BiLSTM-CRF模型对项目类别抽取的 $F 1$ 值是最低的 $( F 1$ 值为 $6 7 . 6 9 \%$ ，导致优化之后对项目类别抽取的 $F 1$ 值仍然是最低的 $( F 1$ 值为 $7 7 . 3 7 \%$ )。本文认为主要原因有2点：一是CNNs-BiLSTM-CRF模型对项目类别的召回率明显偏低 $( R$ 值为 $6 6 . 0 0 \%$ ，而领域知识是基于对该模型召回的国际合作元素进行优化，尽管在优化过程中还会发现新的国际合作元素，一定程度上提高召回率，但优化之后对项目类别的召回率还是偏低， $( R$ 值为 $7 9 . 5 0 \%$ ；二是项目类别的国际合作元素相较于其他类别的构成更为复杂，导致该模型的抽取精度也明显偏低( $P$ 值为 $6 9 . 4 7 \%$ )，优化之后对项目类别的抽取精度还是偏低( $P$ 值为 $7 5 . 3 6 \%$ 。

对于平台类别，由于被分类未平台类别多为机构名称，而机构名称的抽取也是传统命名实体识别的任务之一，并且从表2中可以看出平台类别在所有元素类别中的占比排名第二 $( 1 6 . 0 1 \%$ 。因此，CNNs-BiLSTM-CRF模型对其抽取的精度和召回率都较为出色且平均 $( P _ { }$ 值为 $8 3 . 0 2 \%$ ， $R$ 值为$8 5 . 1 3 \%$ )。但是由于国际合作元素的长度分布不均匀，平台元素相比传统的机构名在抽取过程中会遇到更多的“未完全抽取”和“分割抽取”现象。

从规划和协定类别来看，由于这些类别的国际合作元素一般都较长，同时这两类元素在数据集中的占比很小(分别为$3 . 3 2 \%$ 和 $3 . 9 0 \%$ )，所以CNNs-BiLSTM-CRF模型在这4类国际合作元素的抽取结果上表现不佳，而领域知识则有效地提升了这两类国际合作元素提取的 $F 1$ 值。

# 6 结束语

本文首先利用分词工具对语料库中的Web外交新闻文本进行分词，再利用神经网络对文本中的国际合作元素进行初步抽取，最后结合人工提取的领域知识对初步抽取结果进行优化得到国际合作元素的最终抽取结果。在实验阶段，把本文方法与神经网络方法在相同语料库上进行了对比分析，验证了本文方法能取得更好的效果；同时对人工提取的领域知识在语料库上的效果进行了对比和分析。

从实验分析中可以发现，本文方法对于初步抽取结果有着较强的依赖性，所以如何提高初步抽取性能是未来工作的重点之一，尤其是对项目类别国际合作元素的抽取。其次，本文使用的语料库中五类国际合作元素的分布倾斜度较高，今后会考虑对数据集进行扩充并构建一个5类合作元素分布倾斜度较小的数据集，在新的数据集上对方法进行实验和改进。最后，利用从Web外交新闻中抽取到的国际合作元素继续开展知识发现方面的研究。

# 参考文献：

[1]Luo Gang,Huang Xiaojiang,Lin CY,et al. Joint entity recognition and disambiguation [C]//Proc of Conference on Empirical Methods in Natural Language Processing. Stroudsburg,PA:ACL,2O15:879-888.   
[2]Passos A,Kumar V,McCallum A.Lexicon infused phrase embeddings for named entity resolution [C]//Proc of the 18th SIGNLL Conference on Computational Natural Language Learning. Stroudsburg,PA:ACL, 2014:78-86.   
[3]Hu Zhiting,Ma Xuezhe,Liu Zhengzhong,et al.Harnessing deep neural networks with logic rules [C]//Proc of the 54th Annual Meeting of the Association for Computational Linguistics，Volume 1:Long Papers. Stroudsburg,PA:ACL,2016: 2410-2420.   
[4]Graves A,Mohamed A R,Hinton G. Speech recognition with deep recurrent neural networks [C]/Proc of IEEE International Conference on Acoustics,Speech and Signal Processing.Piscataway,NJ:IEEE Press,2013:6645-6649.   
[5] Zadrozny B． Santos C D,Zadrozny B.Learning character-level representations for part-of-speech tagging [C]// Proc of the 31st International Conference on Machine Learning. New York: ACM Press, 2014:1818-1826.   
[6]Chiu J,Nichols E.Named entity recognition with bidirectional LSTM-CNNs[J].Transactions of the Association of Computational Linguistics,2016,4(1): 357-370.   
[7]Pascanu R,Mikolov T,Bengio Y.On the dificulty of training recurrent neural networks [C]//Proc of International Conference on Machine Learning.New York:ACMPress,2013:1310-1318.   
[8]Dyer C,Ballesteros M,Ling Wang,et al. Transition-based dependency parsing with stack long short-term memory [C]//Proc of the 53rd Annual Meeting of the Association for Computational Linguistics and the7th International Joint Conference on Natural Language Processing ,Volume 1:Long Papers.Stroudsburg,PA:ACL，2015: 334-343.   
[9]Gael JV,Vlachos A，Ghahramani Z. The infinite HMM for unsupervised PoS tagging.[C]// Proc of Conference on Empirical Methods in Natural Language Processing. Stroudsburg,PA: ACL, 2009: 678-687.   
[10] Sha Fei,Pereira F. Shallow parsing with conditional random fields [C]// Proc of Conference of the North American Chapter of the Association for Computational Linguisticson Human Language Technology. Stroudsburg,PA: ACL,2003:134-141.   
[11] Lample G, Ballesteros M,Subramanian S,et al. Neural architectures for named entity recognition [C]//Proc of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies. Stroudsburg,PA: ACL,2016: 260-270.   
[12] Ma Xuezhe,Hovy E.End-to-end sequence labeling via bi-directional LSTM-CNNs-CRF [C]//Proc of the 54th Annual Meeting of the Association for Computational Linguistics,Volume 1: Long Papers. Stroudsburg,PA: ACL,2016:1064-1074.   
[13] Chung J,Cho K,Bengio Y.A character-level decoder without explicit segmentation for neural machine translation [C]// Proc of the 54th Annual Meeting of the Association for Computational Linguistics. Stroudsburg,PA: ACL,2016,Volume 1: Long Papers: 1693-1703.