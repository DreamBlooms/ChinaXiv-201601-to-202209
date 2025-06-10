# 基于BiGRU-Attention神经网络的文本情感分类模型

王伟ab，孙玉霞ʰ，齐庆杰‘，孟祥福b(辽宁工程技术大学a.科学技术研究院;b.电子与信息工程学院;c．矿业学院，辽宁葫芦岛 125105）

摘要：针对双向长短时记忆神经(BiLSTM)模型训练时间长、不能充分学习文本上下文信息的问题，提出一种基于BiGRU-Attention的文本情感分类模型。首先，利用双向门控循环(BiGRU)神经网络层对文本深层次的信息进行特征提取；其次，利用注意力机制(attention)层对提取的文本深层次信息分配相应的权重；最后，将不同权重的文本特征信息放入 softmax 函数层进行文本情感极性分类。实验结果表明，所提的神经网络模型在 IMDB 数据集上的准确率是$9 0 . 5 4 \%$ ，损失率是0.2430，时间代价是1100 s，验证了BiGRU-Attention模型的有效性。

关键词：文本情感分类；注意力机制；双向门控循环神经网络中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.07.0413

# Text sentiment classification model based on BiGRU-Attention neural network

Wang Weia, b, Sun Yuxiab, Qi Qingjiec, Meng Xiangfub (a.College Instituteof Science &Technology,b.Colege of Electronic & Information Engineering，c.College of Mining Liaoning Technical University,Huludao Liaoning 125105,China)

Abstract:The BiLSTM neural network model has longtraining time andcan notfuly learn text context informations.In orderto solve theproblems,this work proposes atext emotion classification model basedon BiGRU-Atention neuraletwork. Firstly,the bidirectional Gated RecurrentUnity(BiGRU)neuralnetwork layer was usedtoextractthe featuresof thedeeptext information；secondly,theatention mechanism（Attention）layer wasused toallocate thecorresponding weightof the extracted text deepinformation.Finally,tetextfeature messagesof diferent weightsareput intothesoftmax functionlayer tocarryoutthetextsentiment clasifications.Theexperimentalresultsshowthattheaccuracyofthe proposedneuralnetwork model is $9 0 . 5 4 \%$ on the IMDB data set,the loss rate is 0.243O and the time cost is 110Os and the validity of the BiGRU-Attention model is verified.

Key Words:text sentiment classifications; attntion mechanism; bidirectional Gated Recurrent Unity (BiGRU)

# 0 引言

文本情感分类是NLP领域的一个重要任务，通常是对带有主观情感色彩的文本进行分类。文本情感分类能对文本层次特征进行提取，挖掘用户的情感倾向，被广泛应用在政策意见挖掘、民意调查、产品分析、电影推荐、搜索排名等领域。近年来，Web2.0的兴起掀起了用户主动创造信息的时代，用户可以随时通过移动终端发表自己意见和评论，因此用户评论数据呈指数型增长。研究人员最初使用的朴素贝叶斯等浅层次机器学习算法已不能满足与日俱增的数据处理的需要，因此神经网络应运而生并且成为近年来的研究热点。

CNN最初在图像领域得到广泛应用，并迅速扩展到其他领域。LeCun等人[1将CNN应用到文本情感分类，提高了文本分类的准确率。虽然采用CNN相比传统研究人员所采用的基于规则和机器学习[2算法准确率提高了，但仍不能充分学习文本上下文信息。随着研究的不断深入，Mikolov等人[3提出将RNN应用到文本分类任务，由于RNN当前节点的输出值由当前的输入和上一个节点的输出两部分共同决定，使得 RNN 能够充分学习文本前后上下之间的信息，因此RNN比CNN适合于文本分类；但RNN长期依赖学习的特征会容易出现梯度弥散的问题。为了解决梯度弥散问题，LSTM和GRU 等众多变体被提出并在情感分类领域广泛应用，但LSTM由于结构的复杂性，计算异常复杂，存储了多余的中间变量，因此需要大量的训练时间和内存空间且LSTM、GRU只能利用历史信息来对当前信息作出判断，无法利用未来信息，有时可能无法对当前信息进行准确的判断和充分地文本信息提取；目前广泛在文本领域应用的BiLSTM和attention机制结合的模型，仍无法摆脱复杂计算造成的训练时间过长的问题。

针对上述问题，本文提出了一种BiGRU-Attention模型，将文本的输入向量放入BiGRU层相比放入BiLSTM层，能进一步减少网络训练的时间；把BiGRU层的输出向量放入Attention层能进一步突出文本的关键信息，提高文本信息的提取质量。BiGRU-Attention 模型在IMDB数据集上进行对比实验，将准确率、损失率和时间代价作为评价指标，证明了BiGRU-Attention模型在文本分类方面的有效性。

# 1 相关研究

利用深度学习的方法研究文本情感分类近年如雨后春笋般的涌现。梁军等人[4采用递归神经网络的情感转移模型加强文本相关性的捕获；白静等人[5]提出使用BiLSTM-CNN-Attention的混合神经网络结构进行两种特征融合的分类；梁斌等人[采用attention机制和CNN结合的混合模型，解决平行化问题，降低模型训练时间；赵勤鲁等人[7提出LSTM-Attention模型充分提取了语义结构信息；杨东等人[8提出CNN、GRU和Attention机制的混合神经网络模型对文本进行特征提取；司念文等人9提出attention机制和LSTM混合模型更加有效地对中文词性进行标注；王业沛等人[10采用LSTM神经网络进行判断结果的倾向性任务分析，有效地提高了裁判文书中关键信息提取的准确性；朱星嘉等人[1]提出了改进的attention-basedLSTM的特征选择模型，解决了数据的维度灾难问题，有效地突出了文本的重点特征信息；李阳辉等人[12]将降噪自编码的深度学习方法应用在情感分析任务，提高了模型对原始数据的鲁棒性和信息特征的表达能力；刘洋[13]采用GRU神经网络对时间序列进行预测，提高了预测方案的准确性；李晓等人[14采用BiGRU网络对互联网信息输入序列快速准确地实现特定信息的提取；黄兆玮等人[15]采用GRU和attention机制结合的远程监督关系抽取的方法提高了准确率；张玉环等人[16利用LSTM及GRU搭建文本情感分类模型使模型在较短的时间内达到较高的准确率；田竹[17将RSGRU的混合神经网络应用在语句级情感分析任务，节约了人力，更加容易维护；Zhou 等人[18采用最小门控单元(MGU)对序列化的数据进行处理，加快了模型的训练速度；黄磊等人[19采用LSTM和GRU的混合神经网络模型对文本重点信息进行提取，召回率明显提高。

近年，attention机制在自然语言处理领域广泛应用，attention机制最早应用在计算机视觉图像领域。2014年googlemind团队[20]使用循环神经网络和attention机制的混合模型做图像分类，它的主要思想是当观察某一幅图片时，人们经常会把注意力集中到某一小块区域，并能根据之前的观察来预测未来的注意力应该集中图像的位置，根据当前的输入和前一状态去确定当前状态应该处理的注意力部分，处理的像素更少，问题任务更加简单化；随后Bahdanau 等人[21]将attention 机制应用在机器翻译任务，通过attention机制把源语言端每个词学到的表达和预测要翻译的词联系起来，这也是attention 机制在自然语言处理领域的首次应用；Luong等人[22]介绍了全局和局部两种注意力机制；Yin 等人[23]介绍了卷积和attention 机制结合的三种方式，可以在输入CNN之前加入attention 机制，可以在进行CNN 特征提取后，池化之前加入attention 机制；也可以把以上两种方式结合起来添加attention机制，这也是attention机制在CNN中的首次探索；在2014\~2015年attention机制在机器翻译上开始流行；2015年attention机制与RNN结合的神经网络模型在自然语言领域广泛应用；2015一2016年attention机制和CNN相结合的神经网络模型成为研究热点。随后，研究人员利用attention机制和神经网络模型进行文本情感分类层出不穷，并成为近年来的研究热点。

随着LSTM、CNN、attention 机制等混合神经网络模型在文本情感分类中的广泛应用，在LSTM与attention机制的结合的模型在文本方面取得的卓越成绩后，人们逐渐把目光投向attention机制与BiLSTM、Bi-GRU的研究。国内外近两三年此类研究也开始涌现。田生伟等人[24]利用Bi-LSTM和attention机制结合的混合神经网络对维吾尔语事件时序关系进行识别，这种神经网络混合的方式先把文本向量放入Bi-LSTM层，提取一些文本信息，然后放入attention 机制层进行深层文本特征提取，最后放入到 softmax 层进行文本情感分类；司念文等人[9]提出LSTM-BiLSTM-Attention网络模型更加有效地对中文词性进行标注，首先利用LSTM层进行文本特征提取，然后利用BiLSTM双方向的原理通过双向的词性来对目标词进行标注，最后利用Attention层进一步提取重点信息，增加词性标注的准确性；成璐[25]提出了基于attention 机制和BiLSTM的神经网络模型对中文商品评论进行情感分析，将分词后的词向量的形式放入Bi-LSTM进行文本特征提取，放入Attention层突出文本分类中的重点信息;Rozental等人[26提出使用BiGRU神经网络和卷积的最大池化进行多次操作的混合模型来提取文本特征信息，最后在softmax层进行文本分类，用英语和西班牙语来测试实验模型，取得第一和第三的好成绩；Chen 等人[27使用Bi-LSTM和位置Attention机制结合的混合神经进行文本分类，也取得不错的分类效果；Kumar等人[28]使用简单的BiLSTM和两层attention 机制简单混搭的模型,在BiLSTM层提取了文本特征信息后，分别顺序建立了词语级的attention机制和句子级的attention机制，将该实验模型在SemEval2017Task5上进行评测，在 sub-tracks1和2的评测结果比目前最好的系统分别提高1.7和3.7个百分点。

无论是对维吾尔族语事件时序关系的分析、中文词性的分析或者商品评论分析还是国外对BiLSTM或Bi-GRU的一些最新研究，本质上都是利用神经网络和attention机制结合的网络模型对文本进行相关处理，提取深层次文本信息；大部分采用的是BiLSTM或者BiGRU和attention机制结合的混合模型，且大部分模型都经历了将文本向量放入Bi-LSTM层特征提取、注意力机制层突出重点信息，softmax层文本分类三个阶段。这些研究都把很大的注意力放在了Bi-LSTM或BiGRU神经网络和attention结合的模型研究上，并且取得了不错的效果。本文的算法模型在以前研究成果基础上，提出了一种更加简单的模型，采用结构更加简练、计算更加简单和存储空间更小的BiGRU层、attention层、softmax 层和全连接层的简单混合神经结构来提取特征信息，进行文本分类。

# 2 相关技术及BiGRU-Attention模型

# 2.1相关技术

# 2.1.1长短期记忆神经

RNN是一种用来处理序列数据的特殊的神经网络，这种神经网络的功能与人的一些思考习惯类似。想象这样一个情景，当我们做英语四、六级选词填空时，确定空格要填的单词，我们不仅要阅读空格前面的单词还要阅读前面单词的前面单词如The sea water in the deep sea is very—，通过阅读 very 及之前的inthedeep sea可以知道此处应选deep。同样的RNN就是为了解决文本中当前输出与当前输入和前一时刻输出的关系而诞生的神经网络。RNN主要应用在语音识别、机器翻译、中文分词和词性标注等序列化数据的领域，并在该领域取得了良好的成果。随着研究活动的不断开展，RNN被广泛应用在文本处理方面；近年来，被用在情感分析领域的模型更是层出不穷。经典的RNN结构由输入层、隐含层和输出层组成。RNN可以学习文本上下文的语义信息，抽取到的特征信息可以作为其他神经网络或其他模型的输入，也可以放入softmax 函数层直接进行情感极性的分类。RNN在 $t$ 时刻展开图如图1所示。

![](images/6fa02ae8778fb304750b51c32c6c8d8261555c93a42e6c0ade84f5bf0d8b056d.jpg)  
图1t时刻RNN结构的展开图

RNN基本的算法思想是随时间反向传播算法，但在随时间反向传播过程中，跨时间步和长时间学习使后续节点的梯度往往不能按照初值传到最初的位置，容易出现梯度弥散问题。为了克服梯度弥散的缺点，RNN的众多变体被提出，其中LSTM就是RNN变体中一种广泛应用的经典变体。LSTM单个神经元的具体结构如图2所示。

![](images/83212bb5b0bc4dbf1aecee9966b56bdc5521acb87f912fd6fe71e5007bde6a7c.jpg)  
图2LSTM神经元结构图

LSTM的具体工作原理可以通过以下几个公式进行理解：

$$
f _ { t } = s i g m o i d \left( W _ { f } \cdot \left[ h _ { t - 1 } , x _ { t } \right] + b _ { f } \right)
$$

$$
i _ { t } = s i g m o i d \left( W _ { i } \cdot \left[ h _ { t - 1 } , x _ { t } \right] + b _ { i } \right)
$$

$$
C _ { t } = t a n h \big ( { W _ { c } \cdot \big [ h _ { t - 1 } , x _ { t } \big ] + b _ { c } } \big )
$$

$$
C _ { t } = f _ { t } * C _ { t - 1 } + i _ { t } * C _ { t }
$$

$$
o _ { t } = s i g m o i d \left( W _ { o } \cdot \left[ h _ { t - 1 } , x _ { t } \right] + b _ { o } \right)
$$

$$
h _ { t } = o _ { t } * t a n h ( C _ { t } )
$$

从图2和公式可以看出，LSTM由输入门、记忆单元、输出门和遗忘门四部分组成。其中， $x _ { t }$ 表示 $t$ 时刻的输入向量， $h _ { t - 1 }$ 表示上一个时刻的输出向量， $\big \{ W _ { f } , W _ { i } , W _ { c } , W _ { o } \big \}$ 表示各个相应部分的权重系数矩阵， $\{ b _ { { _ f } } , b _ { { _ i } } , b _ { { _ c } } , b _ { { _ o } } \}$ 表示各个相应部分的偏移向量，sigmoid表示激活函数，式(1)计算的是遗忘门的值，看有多少信息可以进行保留，由式(1)的形式可以看出 $\mathbf { \Psi } _ { t }$ 时刻遗忘门的值由 $x _ { t }$ 和 $h _ { { \scriptscriptstyle { t - 1 } } }$ 共同决定；式(2)计算的是用 sigmoid 函数去激活的$\left( W _ { i } \bullet \big [ h _ { t - 1 } , x _ { t } \big ] + b _ { i } \right)$ 细胞状态的值，式(3)计算的是由 $h _ { t - 1 }$ 和 $x _ { t }$ 决定的候选记忆单元的值;式(4)计算的是记忆状态单元通过 $C _ { t - 1 }$ 和 $C _ { t }$ 对$f _ { t }$ 和 $i _ { \iota }$ 的调节作用后的值；式(5)(6)计算的是 $t$ 时刻由 $h _ { { \scriptscriptstyle { t - 1 } } }$ 和 $x _ { t }$ 决定的经过内部循环和更新的LSTM最后的隐层状态的输出 $h _ { { \scriptscriptstyle t } }$ 。

# 2.1.2 GRU

随着LSTM在自然语言处理特别是文本分类任务的广泛应用，人们逐渐发现LSTM具有训练时间长、参数较多、内部计算复杂的缺点。Cho等人在2014年进一步提出了更加简单的、将LSTM的单元状态和隐层状态进行合并的、还有一些其他的变动的GRU模型。GRU模型是一种保持了LSTM效果、具有更加简单的结构、更少的参数、更好的收敛性的模型。GRU 模型由更新门和重置门两个门组成。前一个时刻的输出隐层对当前隐层的影响程度由更新门控制，更新门的值越大说明前一时刻的隐层输出对当前隐层的影响越大；前一时刻的隐层信息被忽略的程度由重置门控制，重置门的值越小说明忽略得越多。GRU结构更加精简，具体如图3所示。

![](images/50235d94cac3e22fcc3f92ac5ddaf6525ad3e956e02d69ca72f591cbaaf83780.jpg)  
图3GRU神经元结构图

GRU模型的更新方式如下：

$$
r _ { t } = \sigma \big ( W _ { r } \cdot \big [ h _ { t - 1 } , x _ { t } \big ] \big )
$$

$$
z _ { t } = \sigma \big ( W _ { \boldsymbol { z } } \cdot \big [ h _ { t - 1 } , x _ { t } \big ] \big )
$$

$$
h _ { t } = \operatorname { t a n h } ( W \cdot \left[ r _ { t } ^ { * } h _ { t - 1 } , x _ { t } \right]
$$

$$
h _ { t } = \left( 1 - z _ { t } \right) ^ { * } h _ { t - 1 } + z _ { t } ^ { \mathrm { ~ * ~ } } h _ { t }
$$

其中： $r _ { t }$ 表示 $t$ 时刻的重置门， $z _ { t }$ 表示 $t$ 时刻的更新门， $h _ { { t } }$ 表示 $t$ 时刻的候选激活状态， $h _ { { t } }$ 表示 $t$ 时刻的激活状态， $h _ { t - 1 }$ 表示 $\left( t { - } 1 \right)$

时刻的隐层状态。更新门z由当前状态需要被遗忘的历史信息和接受的新信息决定；重置门 $\boldsymbol { r }$ 由候选状态从历史信息中得到的信息决定。

# 2.1.3BiGRU

在单向的神经网络结构中，状态总是从前往后输出的。然而，在文本情感分类中，如果当前时刻的输出能与前一时刻的状态和后一时刻的状态都产生联系如对这样一个句子进行选词填空 The sea water in the deep sea is so that the sun doesnot shine.通过在 The sea water in the deep sea 和 the sun does notshine两部分内容，我们可以更加确信此处选填deep，这样更有利于文本深层次特征的提取，这就需要BiGRU来建立这种联系。BiGRU 是由单向的、方向相反的、输出由这两个GRU的状态共同决定的GRU组成的神经网络模型。在每一时刻，输入会同时提供两个方向相反的GRU，而输出则由这两个单向GRU共同决定。BiGRU的具体结构如图4所示。

![](images/8b823c2f6d0d6023c281b77090f4a08bf65d42c576a325261107c8daaada1fe5.jpg)  
图4双向GRU 结构模型图

从图4可以看出，BiGRU当前的隐层状态由当前的输入 $\mathbf { X } _ { \mathrm { t } }$ 、(t-1)时刻向前的隐层状态的输 $\widehat { h _ { t - 1 } }$ ，和反向的隐层状态的输出$\overleftarrow { h _ { t - 1 } }$ 三个部分共同决定。由于BiGRU可以看做两个单向的GRU,所以BiGRU在 $t$ 时刻的隐层状态通过前向隐层状态 $\overrightarrow { h _ { { \scriptscriptstyle t } - 1 } }$ 和反向隐层状态 $\overleftarrow { h _ { t - 1 } }$ 加权求和得到：

$$
\overrightarrow { h _ { t } } = G R U \left( x _ { t } , \overrightarrow { h _ { t - 1 } } \right)
$$

$$
\overleftarrow { h } _ { t } = G R U \left( x _ { t } , \overleftarrow { h _ { t - 1 } } \right)
$$

$$
h _ { t } = w _ { t } \overrightarrow { h _ { t } } + \nu _ { t } \overleftarrow { h _ { t } } + b _ { t }
$$

其中：GRU()函数表示对输入的词向量的非线性变换，把词向量编码成对应的GRU隐层状态。 $w _ { t }$ 、 $\nu _ { \tau }$ 分别表示 $\mathbf { \Phi } _ { t }$ 时刻双向GRU所对应的前向隐层状态 $\overrightarrow { h _ { t } }$ 和反向隐状态 $\overleftarrow { h } _ { \iota }$ 所对应的权重，$b _ { _ t }$ 表示 $t$ 时刻隐层状态所对应的偏置。

# 2.1.4 Attention model

Attention机制在语音识别、机器翻译和词性标注等序列化数据中表现非凡，attention机制可以单独使用，也可以在其他混合模型中作为其他混合模型的层使用，可以放在文本向量输入层之后也可以放在其他网络模型训练数据之后，通过对数据进行自动加权变换，把两个不同的部分联系起来，突出重点的词语，使整个系统表现出更好的性能。Attention机制类似人脑的观察某些事物的原理，如人们为了描述某些画的内容而去观察某幅画，首先会观察这幅画上的题的字，然后根据判断有目的地去观察这幅图中表现主题的那部分内容；当去描述这幅画时，往往会先描述与这幅画最相关的内容，然后再去描述其他方面的内容；attention 机制就是一种通过在关键信息上分配足够的关注、突出局部重要信息的机制。attention机制通常可以分为两类：时间attention机制和空间attention机制，本文用到的主要是时间注意力。attention机制是一种类似人脑的注意力资源分配机制，通过概率权重分配的方式，计算不同时刻词向量的概率权重，使一些词语能够得到更多的关注，从而提高该隐藏层特征提取的质量。Attentionmodel基本结构如图5所示。

![](images/60693a6f6f95914f4243c5b0a1f808b0e4e49a86720a77e59ca188ccaac88040.jpg)  
图5attention model基本结构

在attentionmodel中，初始隐层状态到新的隐层状态的向量 $s$ 是各个隐层状态在新的隐层状态所占的比重大小的权重系数 $\alpha _ { i }$ 与初始输入的各个隐层状态 $h _ { i }$ 乘积的累加和，计算公式如下：

$$
s = \sum _ { i = 1 } ^ { t } \alpha _ { i } h _ { i }
$$

$$
\alpha _ { \mathrm { i } } = \frac { e x p ( e _ { i } ) } { \displaystyle \sum _ { j = 1 } ^ { n } ( e _ { j } ) }
$$

$$
e _ { i } = \nu _ { i } t a n h { \left( w _ { i } h _ { i } + b _ { i } \right) }
$$

其中： $e _ { i }$ 表示第 $i$ 时刻隐层状态向量 $h _ { i }$ 所决定的能量值， $\nu _ { i }$ 和 $w _ { i }$ 表示第 $i$ 时刻的权重系数矩阵， $b _ { i }$ 表示第 $i$ 时刻相应的偏移量。通过式(9)可以实现从输入的初始状态到新的注意力状态的转换。

# 2.2 BiGRU-Attention 模型

BiGRU-Attention模型共分为三部分：文本向量化输入层、隐含层和输出层。其中，隐含层由BiGRU层、attention层和Dense层三层构成。BiGRU-Attention模型结构如图6所示。

![](images/74e1ae070fb9aa05ad3658fda5af3a355b427b6a538c623fd36648ca2e9e4e2e.jpg)  
图6 BiGRU-Attention 模型图

下面对这三层的功能分别进行介绍：

# 1)输入层

输入层即文本向量化输入层主要是对IMDB电影评论的25000条数据的预处理即把这些评论数据处理成BiGRU层能够直接接收并能处理的序列向量形式。 $m$ 个单词组成 $\mathbf { \xi } _ { l }$ 个句子的文本 $\mathbf { \Delta } _ { a }$ 即 $\mathbf { a } = \left\{ s _ { 1 } , s _ { 2 } , \cdots , s _ { l } \right\}$ ，样本中的第 $j$ 个句子表示为$s _ { j } = \left\{ w _ { j 1 } , w _ { j 2 } , \cdots , w _ { j m } \right\}$ ，进行文本向量操作，使 $w \in \boldsymbol { w } ^ { a }$ 。文本向量化具体操作步骤如下：

a)读取数据并进行数据清洗；

b)将数据向量化为规定长度1000的形式（句子长度小于规定值的，默认自动在后面填充特殊的符号；句子长度大于规定值的，默认保留前1000个，多余部分截去。）

c)随机初始化数据，按8:2划分训练集和测试集；

d)将数据向量化后，每一条电影评论都变成了统一长度的索引向量，每一个索引对应一个词向量。

经过上面的四步的操作之后，输入的IMDB 数据就变成根据索引对应词向量的形成词矩阵，即设处理后词向量的统一长度为1000，使用glove.6B.100d 的100 维向量的形式，在glove.6B.100d 中不能查找到的词向量随机初始化。设 $c _ { j i }$ 为第$j$ 个句子的第 $i$ 个词向量，则一条长度为1000的IMDB评论数据可以表示为：

$$
c _ { j 1 : j 1 0 0 0 } = c _ { j 1 } \oplus c _ { j 2 } \oplus \cdots \oplus c _ { j 1 0 0 0 }
$$

其中：表示词向量与词向量的连接操作符， $c _ { j \ 1 : j 1 0 0 0 }$ 表示为$c _ { j 1 } .$ Cj2，， $c _ { j 1 0 0 0 }$ 即为第 $j$ 个句子的词向量矩阵。把IMDB 每一条评论中的每一个词按照索引去对应glove.6B.100d中词向量，生成词向量矩阵。

# 2）隐含层

隐含层的计算主要分为两个步骤完成：

a)计算BiGRU层输出的词向量。文本词向量为BiGRU层的输入向量。BiGRU层的目的主要是对输入的文本向量进行文本深层次特征的提取。根据BiGRU神经网络模型图，可以把BiGRU模型看做由向前GRU和反向GRU两部分组成，在这里简化为式(11)。在第 $i$ 时刻输入的第 $j$ 个句子的第 $\mathbf { \Psi } _ { t }$ 个单词的词向量为 $c _ { i j t }$ ,通过BiGRU层特征提取后，可以更加充分地学习上下文之间的关系，进行语义编码，具体计算公式如式(11)所示。

$$
h _ { i j t } = B i G R U \big ( c _ { i j t } \big ) , t \in \big [ 1 , m \big ]
$$

b)计算每个词向量应分配的概率权重。这个步骤主要是为不同的词向量分配相应的概率权重，进一步提取文本特征，突出文本的关键信息。在文本中，不同的词对文本情感分类起着不同的作用。地点状语、时间状语对文本情感分类来说，重要程度极小；而具有情感色彩的形容词对文本情感分类却至关重要。为了突出不同词对整个文本情感分类的重要度，BiGRU-Attention模型中引入了attention机制层。Attention机制层的输入为上一层中经过BiGRU神经网络层激活处理的输出向量 $h _ { i j t }$ ，attention机制层的权重系数具体通过以下几个公式进行计算：

$$
u _ { i j t } = \operatorname { t a n h } \left( w _ { w } h _ { _ { i j t } } + b _ { w } \right)
$$

$$
\alpha _ { i j t } = \frac { e x p \left( u _ { i j t } ^ { T } u _ { w } \right) } { \displaystyle \sum _ { t } e x p \left( u _ { i j t } ^ { T } u _ { w } \right) }
$$

$$
s _ { i j t } = \sum _ { i = 1 } ^ { n } \alpha _ { i j t } h _ { i j t }
$$

其中: $h _ { i j t }$ 为上一层BiGRU神经网络层的输出向量， $w _ { _ { w } }$ 表示权重系数， $b _ { { } _ { w } }$ 表示偏置系数， $\boldsymbol { u } _ { \scriptscriptstyle w }$ 表示随机初始化的注意力矩阵。Attention机制矩阵由attention机制分配的不同概率权重与各个隐层状态的乘积的累加和，使用softmax函数做归一化操作得到。

3)输出层

输出层的输入为上一层attention机制层的输出。利用softmax函数对输出层的输入进行相应计算的方式从而进行文本分类，具体公式如下：

$$
y _ { j } = s o f t m a x { \left( w _ { 1 } s _ { i j t } + b _ { 1 } \right) }
$$

其中: $w _ { 1 }$ 表示attention机制层到输出层的待训练的权重系数矩阵， $b _ { \scriptscriptstyle 1 }$ 表示待训练相对应的偏置， ${ \boldsymbol { y } } _ { j }$ 为输出的预测标签。

# 2.3 BiGRU-Attention模型训练方法

本文BiGRU-Attention 模型以IMDB数据集、预设参数和迭代次数N为输入，经过文本向量化输入层把IMDB数据集处理词向量的形式，利用BiGRU-Attention模型对IMDB数据集进行分类。

算法BiGRU-Attention 神经网络的文本情感分类算法输入：IMDB数据集、预设参数、迭代次数N。

输出：IMDB数据集的情感分类。

在文本向量化输入层对数据进行清洗、划分为固定长度、随机初始化、划分训练集和测试集、转化成对应词向量。

IMDB数据集对应的词向量的形式，设文本中某个词对应的词向量为$\boldsymbol { x } _ { t ^ { \mathrm { ~ o ~ } } }$

对IMDB每一条电影评论的处理：

for hop=1 to h:

$$
\overrightarrow { h _ { \iota } } = G R U \left( x _ { \iota } , \overrightarrow { h _ { \iota - 1 } } \right)
$$

$$
\overleftarrow { h } _ { t } = G R U \left( x _ { t } , \overleftarrow { h _ { t - 1 } } \right)
$$

$$
\begin{array} { l } { \displaystyle h _ { t } = w _ { t } \overrightarrow { h _ { t } } + \nu _ { t } \overleftarrow { h _ { t } } + b _ { t } } \\ { \displaystyle u _ { i j t } = \mathrm { t a n h } \big ( w _ { w } h _ { i j t } + b _ { w } \big ) } \\ { \displaystyle \alpha _ { i j t } = \frac { e x p \big ( u _ { i j t } ^ { T } u _ { w } \big ) } { \sum _ { t } e x p \big ( u _ { i j t } ^ { T } u _ { w } \big ) } } \end{array}
$$

$$
s _ { i j t } = \sum _ { i = 1 } ^ { n } \alpha _ { i j t } h _ { i j t }
$$

end for

使用softmax函数计算分类的结果概率 $y _ { j } = s o f t m a x { \bigl ( } w _ { 1 } s _ { i j t } + b _ { 1 } { \bigr ) }$ 并与原始的标签进行对比，本文的目标函数为

$$
\mathrm { l o s s } = - { \sum _ { j } } \hat { y } ^ { ( j ) } l o g y ^ { ( j ) }
$$

从式(14)可知，通过上述的训练步骤，对从1到 $h$ 个单词分别进行特征提取，分配相应权重累加求和,Dense层进一步提取特征，最后在softmax输出层进行分类，然后对所分类的各个影评标签值和 $l o g y ^ { ( j ) }$ 相乘的累加和，累加和为负值，取相反，使损失最小，计算误差，使用rmsprop 作为训练器，使模型训练和收敛的更快，在沿随时间反向误差传播过程中根据误差不断调整并更新权重和偏置，直到达到迭代次数或小于某一个固定的精度为止。

# 3 实验

# 3.1实验设置

为了验证BiGRU-Attention模型的有效性，实验选用公开的IMDB作为数据集。训练集和测试集按8:2进行划分，分别用于模型训练和模型测试，具体划分情况如表1所示。

表1数据集  

<html><body><table><tr><td>数据集</td><td>数据集</td><td>语句/条</td><td>类别</td></tr><tr><td rowspan="2">IMDB</td><td>训练集</td><td>20000</td><td>2</td></tr><tr><td>测试集</td><td>5000</td><td>2</td></tr></table></body></html>

本实验采用准确率、损失率和迭代时间作为实验的评价标准。数据预处理是实验数据放入神经网络训练前最重要的一步。文本向量层已经对数据处理做了详细的论述，在这里不做陈述。本实验采用keras深度学习框架，底层为TensorFlow，使用Python 语言编程实现；实验运行环境为JetBrainsPyCharm 软件、Win10系统、内存8GB 等。本实验模型为文本向量输入层、隐藏层和文本分类层的三层网络结构。实验中有许多超参数需要设置和调整，超参数设置和调整都是在每一次迭代完成后，根据实验的准确率、损失率调整的。经过多次迭代，实验设置的超参数如表2。

表2模型参数设置  

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>BiGRU隐藏层节点数</td><td>100</td></tr><tr><td>Loss函数</td><td>Categorical_crossentropy</td></tr><tr><td>optimzer</td><td>rmsprop</td></tr><tr><td>Batch_size</td><td>50</td></tr><tr><td>词向量维度</td><td>100</td></tr></table></body></html>

# 3.2 实验评价标准

本文采用准确率、损失率和迭代时间作为实验的评价标准，设样本数总数为 $\mathbf { \delta M }$ ，被正确分类的样本数为 $m _ { \cdot }$ 则正确率(Accuracy)为

$$
\mathrm { A c c u r a c y } = { \frac { m } { M } }
$$

损失函数是在每一次随机批量训练的过程中，按照式(14)的批量样本的相乘累加和取反得到。

迭代时间是10次迭代过程每一次时间相加的和取均值得到的。

# 3.3实验步骤

BiGRU-Attention 模型的具体实验步骤如卜：a)进行数据清洗;b)统一为固定长度的索引向量的形式；c)划分训练集和测试集；d)每一个索引向量对应词向量;e)拼接词向量，组成词矩阵，形成BiGRU-Attention模型的  
输入；f)把文本输入矩阵放入BiGRU层，采用公式(11)进行模型  
训练，提取文本层次特征；g)放入Attention 模型给文本的向量分配相应的权重；h)采用IMDB测试集进行BiGRU-Attention模型性能评估。

# 3.4对比实验

BiGRU-Attention模型与以下常见的7模型进行对比。7模型的结构情况如下：

a)ASC。Rozental等人[26]提出的利用Bi-LSTM进行特征提取和降维、最大池化层突出重点信息、全连接层降维，采用四个不同维度处理的向量进行连接，进入全连接层，最后softmax分类的网络模型

b)DBLSTM-Attention。Chen 等人[27提出了BiLSTM和位置Attention机制结合的混合实验模型。

c)BiLSTM-Attentions。Kumar等人[28]提出的利用BiLSTM和两层Attention机制结合的混合实验模型。

d)HDBN模型。Yan 等人[29]提出了主要利用DBM 降噪降维、DBN提取层次特征和softmax层文本分类的将DBM和DBN混合的HDBN的混合神经网络模型。

e)S-LSTM。Zhu等人[30]提出的利用树形结构的LSTM模型并通过记忆细胞来记住历史信息的混合模型。

f)BiLSTM-Attention 模 型。BiLSTM-Attention 模型与BiGRU-Attention模型属于同种类型的混合实验模型。BiLSTM-Attention 模型就是把 BiGRU-A-ttention 模型中的BiGRU层换成BiLSTM层，其他实验设置均相同。

g)LSTM-Attention 模 型。LSTM-Attention 模 型、Bi-LSTM-Attention 模型与 BiGRU-Attention 模型都属于同种类型的混合实验模型。LSTM-Attention模型就是把BiGRU-Attention 模型中的BiGRU层换成LSTM层，其他实验设置均相同。

以上所有的实验模型都基本分为文本向量输入层、隐藏层即文本信息提取功能层和文本分类层的三层网络结构，超参数相同，迭代次数均为10次。从以上分析可以看出，除了实验变量层即模型功能层外，四种模型其他条件均相同，保证了实验变量层的唯一性和实验结果的针对的比较性。

# 3.5 实验结果分析

3.5.1与 HDBN、S-LSTM、ASC、DBLSTM-Attention、BiLSTM-Attentions模型的对比实验本实验选用在10次迭代过程中，在测试集上最高的准确率作为该模型的准确率，对应的测试集最高准确率的损失率即为该模型的损失率，对应的迭代时间即为该模型的迭代时间记为time，具体如表3所示。

表3不同模型的分类结果  

<html><body><table><tr><td>模型</td><td>准确率</td><td>损失率</td><td>time</td></tr><tr><td>BiGRU-Attention</td><td>90.54%</td><td>0.2430</td><td>1100s</td></tr><tr><td>ASC</td><td>89.96%</td><td>0.2445</td><td>985s</td></tr><tr><td>BiLSTM-Attentions</td><td>90.34%</td><td>0.2438</td><td>1417s</td></tr><tr><td>DBLSTM-Attention</td><td>88.85%</td><td>0..2650</td><td>1345s</td></tr><tr><td>S-LSTM</td><td>88.74%</td><td>0.2847</td><td>1205s</td></tr><tr><td>HDBN</td><td>86.94%</td><td>0.3947</td><td>1115s</td></tr></table></body></html>

从表3可以看出，本文所提出的BiGRU-Attention 模型在准确率、损失率方面的表现性能均优于其他五种实验模型，时间代价高于ASC实验模型但低于其他四种模型。从总体上看，这六种实验模型的准确率、损失率、时间代价比较接近，准确率、损失率、时间代价总是随着模型复杂度有所变化、上下波动。表格从上往下进行依次对比，可以看出 BiGRU-Attention模型准确率和损失率性能优于ASC模型，两模型都利用了BiGRU神经网络层，来提取文本的重点信息；两模型的区别在于一个是在BiGRU层的基础上加了Attention层，利用Attention层分配相应的权重来突出文本的重点特征，而另一个则是在BiGRU层的基础上增加了最大池化层，利用最大池化的突出重要信息，遗忘次要信息的特征。由两者的比较可以看出，Attention层在突出重要信息方面的表现性能要优于卷积的最大池化层，表现在实验评价指标性能方面就是提高准确率，降低损失率，但因为Attention层突出信息的功能是通过不断加权计算进行的，相比于单纯的最大池化，时间代价增加；BiGRU-Attention模型在实验的评价指标方面优于DBLSTM-Attention，这两个实验模型均存在attention层，attention层的主要功能基本相同，模型结构也基本相同；不同在于实验模型的第一层一个是BiGRU层，而另一个是BiLSTM层，通过本实验这两个实验模型的评价指标观察分析，可以看出 BiGRU神经网络在提取文本重点信息、减少计算量方面相比BiLSTM 神经网络表现更优。BiLSTM-Attentions 模型与DBLSTM-Attention模型进行比较，两者的区别在于BiLSTM-Attentions 模型要比 DBLSTM-Attention 模型多一个Attention层，通过对实验评价指标的分析，我们可以清楚的看出Attention层突出文本信息的重要作用。

总之，通过对上面几个模型的对比分析可以得出这样的一个结论：在IMDB数据集上，BiGRU模型要优于BiLSTM，因为 BiGRU收敛速度更快，计算更简单，参数更少，在提高准确率降低损失率的同时降低模型的训练时间；attention层在突出重点信息方面要优于卷积的池化层。所以BiGRU-Attention模型在实验的指标方面均表现比较优异。

# 3.5.2迭代次数

本实验选用10次迭代实验来作为实验的评价指标分析。在

10 次迭代实验中，准确率、损失率和时间代价都不是一成不变的，都在动态变化着。为了深刻地反映这种动态变化，本文在所有的实验模型中，选取了最具典型、与本实验模型最相近、且最新提出的四种（BiGRU-Attention、ASC、BiLSTM-Attentions和DBLSTM-Attention）模型进行对比。

a）本文 将BiGRU-Attention 模 型 与ASC、BiLSTM-Attentions、DBLSTM-Attention 模型在训练集上进行训练，在测试集上进行对比实验，得到在测试集上的准确率与迭代次数之间的关系，具体如图7所示。

![](images/2c234415eeb311749f421604f3f1c69e4fe85cb504f48bde90892a171c9a6028.jpg)  
图7四种模型准确率变化情况

图7展示了四种模型随迭代次数准确率的变化情况，各个模型从下往上看，总体上准确率不断地提高，BiGRU-Attention模型的准确率始终高于其他三种模型，其中BiGRU-Attention模型的准确率高于ASC模型，突出Attention层相比最大池化更具快速凸显的重要信息、提取的文本深层次特征，快速收敛，快速提高准确性率的特征，在第三次迭代时就能达到最高准确率，并且在最初训练时的准确率就高于其他三种，训练效果较好；BiGRU-Attention模型总体上准确率平稳变化，但在某些迭代次数上可能会出现准确率较低的情况，但准确率始终高于其他三种模型；从总体上看，BiGRU-Attention、ASC和BiLSTM-Attentions这三种模型曲线比较接近，而DBLSTM曲线相对变化起伏比较大。可见，BiGRU模型在提取文本深层次特征方面表现更优且比较稳定；从迭代次数上看，并不是迭代次数越多，准确率越高，每一种模型都有其达到最高准确率的最佳的迭代次数如BiGRU-Attention模型在第四次迭代时准确率最高，而ASC模型在第六次迭代时准确率最高。从以上分析可以看出，BiGRU-Attention 模型能够在迭代次数最少的情况下有效地提高训练数据的准确率。

b)实验完成一次迭代所需要的时间是实验所需的时间代价。图8给出了四种模型在相同的实验条件下完成一次迭代所需要时间的变化趋势曲线。

![](images/77972d0dd10460fdb7c277c2c114d1ad9b5cf20fb185c1b69ed32fd3a093353a.jpg)  
图8四种模型的迭代时间图

如图8可以看出，各个模型的迭代时间总体上没有多大起伏，整体时间趋于平稳，一般都经过了最低的迭代时间之后，再次训练的时候，训练时间不会再有较大的起伏；ASC模型完成一次迭代训练的时间最短，这与卷积的最大池化层的训练迭代收敛速度是分不开的；BiGRU-Attention模型的迭代时间曲线位于DBLSTM-Attention迭代时间曲线和ASC曲线之间，总体时间性能居中，BiGRU-Attention 和DBLSTM-Attention这两个模型的区别基本上在于BiLSTM和BiGRU的不同所引起的，二者迭代时间的不同，说明：迭代速度不同，BiGRU比BiLSTM模型具有计算更快、参数更少的特性；BiLSTM-Attentions 模型的迭代时间曲线相对来说最高，是因为BiLSTM神经网络相对计算较复杂、增加了计算的时间并且Attention层在突出重点信息的同时也增加了加权计算时间的缘故。

c)测试数据集的损失率也是衡量模型性能的一个重要的标准，损失率越小说明模型的性能指标越好。从图9可以看出，各个模型在各次迭代过程中，有些模型损失率的起伏还是比较大的如BiGRU-Attention、DBLSTM-Attention和BiLSTM-Attentions模型损失率曲线起伏比较大，但ASC模型达到最低的损失率后，模型曲线没有多大变化，说明没有加入Attention层的模型的稳定性比较好；各个模型达到损失率最低的迭代次数也不尽相同，比如BiGRU-Attention模型在第四次迭代时达到最低损失率0.2430；而ASC模型在第六次迭代时达到最低的损失率0.2445；BiGRU-Attention模型最初迭代的时候损失率明显的低于其他模型，达到最小的损失率后随着迭代次数的增加，其损失率呈现逐渐上升的趋势;而ASC模型总体曲线变化相对比较平稳，总体呈下降趋势。

![](images/b08b59bb54f3b86ba8ae2a4a8e44ae87d011cf4a6b172434cdfc9bfc97b17388.jpg)  
图9训练集损失率变化曲线

结合图7\~9可以看出，虽然BiGRU-Attention模型相比ASC模型需要训练的时间代价要稍微地高一些，但其准确率更高，损失率更低，达到最佳准确率和损失率所需要的迭代次数更少，总体上需要的训练时间较少；BiGRU-Attention模型在训练集上无论准确率、损失率还是在迭代次数上都具有相比DBLSTM-Attention 和BiLSTM-Attentions 模型无法比拟的优势。综上，本实验证明了BiGRU-Attention的模型有效性。

3.5.3与BiLSTM-Attention 模型、LSTM-Attention模型的对比 实验

虽然 BiGRU-Attention 模型与 HDBN、S-LSTM、ASC、DBLSTM-Attention、BiLSTM-Attentions模型的对比实验已经能充分的说明，BiGRU-Attention模型具有降低模型训练时间、高准确率和低损失率的特点。但是毕竟不属于同种类型混合实验模型的对比，缺少实验的说服力。因此，选择BiGRU-Attention模型与BiLSTM-Attention 模型、LSTM-Attention 模型的对比实验，具体情况如表4所示。

表4三种模型对比  

<html><body><table><tr><td>模型</td><td>准确率</td><td>损失率</td><td>time</td></tr><tr><td>BiGRU-Attention</td><td>90.54%</td><td>0.2430</td><td>1100s</td></tr><tr><td>BiLSTM-Attention</td><td>89.23%</td><td>0.2460</td><td>1352s</td></tr><tr><td>LSTM-Attention</td><td>87.63%</td><td>0.2520</td><td>1221s</td></tr></table></body></html>

通过三种模型的准确率、损失率和迭代时间的对比，可以看出BiGRU-Attention 模型在训练集和测试集比其他两种实验模型表现更优。

# 4 结束语

本文提出了一种新的基于BiGRU-Attention的神经网络模型，比起目前最广泛使用的BiLSTM神经网络和Attention的混合模型，能够在提高准确率的同时降低损失率，适当地降低了模型的训练时间。一方面说明BiGRU比BiLSTM更加的简单，训练时间要快一些；另一方面说明BiGRU与Attention模型结合的有效性；在与最新提出来的模型相比，总体上看来，BiGRU-Attention的神经网络模型略胜其他网络模型。虽然基于BiGRU-Attention的神经网络模型在IMDB数据集上的准确率较高，损失率较低，但随着数据量的增大，其准确率会有所下降；加入Attention机制模型需要进一步自动加和处理所有的对象并且要存储相应的权重信息，增加了系统的计算和系统开销。下一步将寻找能够在数据量巨大时，训练时间较短，准确率较高，损失率较低，计算量小，系统开销小，更适合文本情感分类的神经网络模型。

# 参考文献：

[1]Lecun Yann,Bottou Lenon,Bengio Yoshua,et al. Gradient-based learning applied to document recognition [J].Proceedings of the IEEE,1998,86 (11): 2278-2324.   
[2] 陈珂，梁斌，柯文德，等．基于多通道卷积神经网络的中文微博情感分 析 [J].计算机研究与发展,2018,55(5):945-957.(Chen Ke,Liang Bin, Ke Wende,et al. Chinese micro-blog emotional analysis based on multi-channel convolutional neural network [J]. Computer Research and Development, 2018,55 (05): 945-957.)   
[3]Mikolov T,Sutskever I,Chen Kai,et al.Distributed representations of words and phrases and their compositionality [J]. Neural Information Processing Systems,.2013: 3111-3119.   
[4]梁军，柴玉梅，原慧斌，等．基于深度学习的微博情感分析[J]．中文 信息学报,2014,28 (5):155-161.(Liang Jun,Chai Yumei,Yuan Huibin,et al.Micro-blog emotional analysis based on deep learning [J].Chinese Journal of information,2014,28 (5):155-161.)

[5]白静，李霏，姬东鸿．基于注意力的BiLSTM-CNN中文微博立场检测 模型[J].计算机应用与软件,2018,35(3):266-274.(Bai Jing,Li Fei,Ji Donghong.Attention based BiLSTM-CNN Chinese micro-blog stance detection model [J].Computer Application and Software,2O18,35(3): 266-274. )

[6]梁斌，刘全，徐进，等．基于多注意力卷积神经网络的特定目标情感分 析[J].计算机研究与发展，2017，54(8):1724-1735.(LiangBin，Liu Quan，Xu Jin，et al.Specific target emotion analysisbased on multi-attentions convolution neural network [J]. Computer Research and Development,2017,54 (8): 1724-1735.)

[7]赵勤鲁，蔡晓东，李波，等．基于LSTM-Attention 神经网络的文本特征 提取方法 [J].现代电子技术，2018,41(8):167-170.(Zhao Qinlu,Cai Xiaodong，Li Bo，et al.Text feature extraction method based on LSTM-Attention neural network [J].Modern Electronic Technology, 2018, 41 (8): 167-170.)

[8]杨东，王移芝．基于 Attention-based C-GRU 神经网络的文本分类[J]. 计算机与现代化，2018(2):96-100.(Yang Dong，Wang Yizhi.Text classification based on Attention-based C-GRU neural network [J]. Computer and Modernization,2018(2): 96-100.)

[9]司念文，王衡军，李伟，等．基于注意力长短时记忆网络的中文词性标 注模型[J].计算机科学，2018,45（4): $6 6 { - } 7 0 { + } 8 2$ .(Si Nianwen,Wang Hengjun,Li Wei,et al. Chinese POS tagging model based on attention time memory network [J].Computer Science,2018,45 (4): 66-70+82.)

[10]王业沛，宋梦姣，王鐶，等．基于深度学习的判决结果倾向性分析 [J/OL].计算机应用研究，2019,36(2）．[2018-06-23].http://kns.cnki. net/kcms/detail/51.1196.TP.20180208.1753.154.html.(Wang Yepei, Song Meijiao,WangPu,et al.Analysis of decision results propensity based on deep learning [J/OL].Computer Application Research,2019,36 (2）. [2018-06-23]. http://kns.cnki. net/kcms/detail/51.1196.TP. 20180208. 1753.154. html.)

[11]朱星嘉，李红莲，吕学强，等．一种改进的attention-basedLSTM特征选 择模型[J].北京信息科技大学学报：自然科学版，2018,33(2):54-59. (Zhu Xingjia,Li Honglian，Lu Xueqiang，etal.Animproved Attention-Based LSTM feature selection model [J]. Journal of Beijing University of Information Technology:Natural Science Edition,2018,33 (2): 54-59.)

[12]李阳辉，谢明，易阳．基于深度学习的社交网络平台细粒度情感分析[J].计算机应用研究,2017,34(3):743-747.(Li Yanghui,Xie Ming,YiYang.Fine-grained Emotional Analysis of Social Networking PlatformBased on Deep Learning [J]. Computer Applications，2017,34(3):743-747. )

[13]刘洋．基于GRU神经网络的时间序列预测研究[D].成都：成都理工 大学，2017.(Liu Yang.Time series prediction based on GRU neural network [D].Chengdu: Chengdu University of Technology,2017.)

[14]李骁，黄征．基于GRU网络的互联网信息挖掘[J].信息技术,2018(3):1-5,9.(Li Xiao,Shawn Huang.Internet Information Mining Based onGRU network [J].Information Technology,2018 (3): 1-5,9)

[15]黄兆玮，常亮，宾辰忠，等．基于GRU和注意力机制的远程监督关系 抽取[J/OL].计算机应用研究，2019,36(10).[2018-07-05].htp://kns. cnki.net/kcms/detail/51.1196.TP.20180619.1516.012. html.(Huang Zhaowei，Chang Liang，Bin Chenzhong，et al.Remote supervisory relationship extraction based on GRU and Attention mechanism [J/OL]. Computer Application Research,2019,36(10).[2018-07-05].http:/kns. cnki. net/kcms/detail/51.1196.TP.20180619.1516.012.html.)

[16]张玉环，钱江．基于两种LSTM 结构的文本情感分析[J].软件，2018,39(1):116-12O.(Zhang Yuhuan,Qian jiang.Text sentiment analysis basedon two kinds ofLSTMstructure[J].Software,2018,39(1):116-120.)

[17]田竹．基于深度特征提取的文本情感极性分类研究[D].济南：山东大 学,2017.(Tian Zhu. Text sentiment polarity classifications based on depth feature extraction [D]. Jinan: Shandong University,2017.)

[18] Zhou Guobing,Wu Jianxin,Zhang Chenlin,et al.Minimal gated unit for recurrent neural networks [J]. International Journal of Automation and Computing,2016,13(3):226-234.

[19]黄磊，杜昌顺.基于递归神经网络的文本分类研究[J].北京化工大学 学报：自然科学版，2017,44(1):98-104.(Huang Lei,Du Changshun. Text classfication based on recurrent neural network [J]. Journal of Beijing University of Chemical Technology:Natural Science Edition,2O17,44(1): 98-104.)

[20]Mnih Volodymyr,Heess Nicolas,Graves Alex,et al.Recurrent models of visual attention [J].Neural Information Processing Systems,2014: 2204-2212.

[21]Bahdanau D,Cho K,Bengio Y. Neural machine translation by jointly learning to align and translate [C]// Proc of International Conference on Learning Representations.2015:1-15.

[22] Luong T,Pham H,Manning C D.Effective approaches to attention-based neural machine translation [J].Empirical Methods in Natural Language Processing,2015:1412-1421

[23] Yin Wenpeng, Schutze H,Xiang Bing,et al.Attention-based convolutional netural network for modeling sentence pairs [J].Transactions of the Association for Computional Linguistics,2016,4: 259-272

[24]田生伟，胡伟，禹龙，等．结合注意力机制的Bi-LSTM维吾尔语事件时 序关系识别[J]．东南大学学报：自然科学版，2018，48(3)：393-399. (Tian Shengwei,Hu Wei,Yu Long,etal.Bi-LSTMUygur event sequence recognition combined with attention mechanism [J].Journal of Southeast University:Natural Science Edition,2018,48(3): 393-399.)

[25]成璐.基于注意力机制的双向LSTM 模型在中文商品评论情感分类中 的研究[J]．软件工程,2017,20(11):4-6,3.(Cheng lu.A bidirectional LSTM model based on attention mechanism for emotional classification of Chinese comments [J]. Software Engineering,2017,20 (11): 4-6,3)

[26]Rozental Alon,Fleischer Daniel.Amobee at SemEval-2O18 Task 1:GRU neural network with a CNN attention mechanism for sentiment classification [C]// North American Chapter of the Association for Computational Linguistics.2018:218-225.

[27] Chen Peng，Sun Zhongqian,Bing Lidong，et al.Recurrent Attention Network on Memory for Aspect Sentient Analysis [C]//Proc ofConference on Empirical Methods in Natural Language Processing.2O17: 452-461.   
[28] Kumar A，Kawahara D，Kurohashi S,et al.Knowledge-enriched two-layered attention for sentiment analysis [C]// North American Chapter of the Association for Computational Linguistics.2O18:253-258.   
[29] Yan Yan,Yin Xucheng,Li Sujiang,et al.Hybrid deep belief network [J]. Computational Intelligence and Neuroscience,2015 (5): 650527:1-650527:

# 9.

[30] Zhu Xiaodan,Sobhani P,Guo Hongyu.Learning document semantic representation with long short-term memory over recursive structures [C]// Proc of the 32nd International Conference on International Conference on Machince Learning.2015:1604-1612.