# BERT模型的数学形式

何沧平 许涛cangping@staff.weibo.com xutao@sugon.com微博 曙光信息产业（北京）有限公司

# 摘要

最近流行的自然语言处理技术之一是BERT模型，本文给出该模型的数学形式。

关键词：BERT、自然语言处理

# Mathematical Principles of BERT Model\*

He Cangping cangping@staff.weibo.com WEIBO.COM

Xu Tao   
xutao@sugon.com   
SUGON.COM

# Abstract

BERT is the most popular natural language processing(NLP) model In the recent 3 years. This paper presents its mathematic formulas in detail.

Keywords: BERT, natural language processing

# 1引言

在自然语言处理领域，BERT[1]模型是最近两三年的流行技术。它为后续一大批模型带来灵感，例如ALBERT[2]、XLNET[3]、RoBERTa[4]。

BERT 原论文没有详细描述模型细节。BERT模型的主体来自于自注意力编码器[5]，然而论文[5]也是用自然语言大致描述，没有给出具体细节。BERT作者提供的 TensorFlow 代码1中的实现方式，与原论文[1]中的描述也有差异。

为了迅速应用于业务、严谨地理论研究，本文给出BERT模型的数学形式，将程序代码改写为数字公式。程序代码与原论文不一致的地方，以程序代码为准。

![](images/e61558ba4c0de2ea96797fc5ed31c2dd7f215bc9000e0b3434009953280fd177.jpg)  
图1：激活函数gelu

# 2函数定义

作为准备，本节定义几个函数。目前 BERT代码中数组的组织方式是行优先，因此本文中的向量、矩阵也按行优先来定义。

任意给定正整数 $m$ 和 $n$ ，行向量用黑体小写字母表示，形式为 $\pmb { x } = ( x _ { 1 } , x _ { 2 } , \dots , x _ { n } )$ 。矩阵用大写字母表示，形式为

$$
X = { \left[ \begin{array} { l l l l } { x _ { 1 1 } } & { x _ { 1 2 } } & { \dots } & { x _ { 1 n } } \\ { x _ { 2 1 } } & { x _ { 2 2 } } & { \dots } & { x _ { 2 n } } \\ { \vdots } & { \vdots } & & { \vdots } \\ { x _ { m 1 } } & { x _ { m 2 } } & { \dots } & { x _ { m n } } \end{array} \right] } .
$$

软大函数(softmax)定义为

$$
\begin{array} { r c l } { \operatorname { s m a x } ( \pmb { x } ) } & { = } & { \displaystyle \frac { 1 } { \sum _ { i = 1 } ^ { i = n } e ^ { x _ { i } } } ( e ^ { x _ { 1 } } , e ^ { x _ { 2 } } , \dots , e ^ { x _ { n } } ) , } \\ { \operatorname { s m a x } ( \pmb { X } ) } & { = } & { \displaystyle \left[ \begin{array} { l } { \operatorname { s m a x } ( x _ { 1 : } ) } \\ { \operatorname { s m a x } ( x _ { 2 : } ) } \\ { \vdots } \\ { \operatorname { s m a x } ( x _ { m : } ) } \end{array} \right] = ( \operatorname { s m a x } ( x _ { 1 : } ) ; \operatorname { s m a x } ( x _ { 2 : } ) ; \dots ; \operatorname { s m a x } ( x _ { m : } ) ) , } \end{array}
$$

这里的 $x _ { i : } = ( x _ { i 1 } , x _ { i 2 } , \ldots , x _ { i n } )$ ，圆括号里的分号表示换行。

对向量或矩阵求对数时，对数作用到它们的每一个元素上，即

$$
\begin{array} { r c l } { \log ( { \pmb x } ) } & { = } & { ( \log ( x _ { 1 } ) , \log ( x _ { 2 } ) , \dots , \log ( x _ { n } ) ) , } \\ { \log ( { \pmb x } ) } & { = } & { \left[ \begin{array} { c c c c } { \log ( x _ { 1 1 } ) } & { \log ( x _ { 1 2 } ) } & { \cdots } & { \log ( x _ { 1 n } ) } \\ { \log ( x _ { 2 1 } ) } & { \log ( x _ { 2 2 } ) } & { \cdots } & { \log ( x _ { 2 n } ) } \\ { \vdots } & { \vdots } & { \vdots } \\ { \log ( x _ { m 1 } ) } & { \log ( x _ { m 2 } ) } & { \cdots } & { \log ( x _ { m n } ) } \end{array} \right] . } \end{array}
$$

对实数 $x$ ，激活函数

$$
\operatorname { g e l u } ( x ) = 0 . 5 x ( 1 + \operatorname { t a n h } [ { \sqrt { 0 . 5 \pi } } ( x + 0 . 0 4 4 7 1 5 x ^ { 3 } ) ] ) ,
$$

gelu的图像见图1.

函数gelu作用到的向量和矩阵上时，它作用到每一个元素上。

层归一化(layernormalization） 函数

$$
\mathrm { l n o r } ( X ) = \left[ \begin{array} { c c c c c } { \frac { \gamma _ { 1 } ( x _ { 1 1 - \mu _ { 1 } } ) } { \sigma _ { 1 } } + \beta _ { 1 } } & { \frac { \gamma _ { 2 } ( x _ { 1 2 - \mu _ { 2 } } ) } { \sigma _ { 1 } } + \beta _ { 2 } } & { \cdot \cdot } & { \frac { \gamma _ { n } ( x _ { 1 n - \mu _ { n } } ) } { \sigma _ { n } } + \beta _ { n } } \\ { \frac { \gamma _ { 1 } ( x _ { 2 1 - \mu _ { 1 } } ) } { \sigma _ { 1 } } + \beta _ { 1 } } & { \frac { \gamma _ { 2 } ( x _ { 2 2 - \mu _ { 2 } } ) } { \sigma _ { 1 } } + \beta _ { 2 } } & { \cdot \cdot } & { \frac { \gamma _ { n } ( x _ { 2 n - \mu _ { n } } ) } { \sigma _ { n } } + \beta _ { n } } \\ { \vdots } & { \vdots } & & { \vdots } \\ { \frac { \gamma _ { 1 } ( x _ { m 1 - \mu _ { 1 } } ) } { \sigma _ { 1 } } + \beta _ { 1 } } & { \frac { \gamma _ { 2 } ( x _ { m 2 - \mu _ { 2 } } ) } { \sigma _ { 1 } } + \beta _ { 2 } } & { \cdot \cdot } & { \frac { \gamma _ { n } ( x _ { m n - \mu _ { n } } ) } { \sigma _ { n } } + \beta _ { n } } \end{array} \right] ,
$$

这里的 $\begin{array} { r } { \mu _ { j } = \frac { 1 } { m } \sum _ { i = 1 } ^ { m } x _ { i j } , \sigma _ { j } = \sqrt { \frac { 1 } { m } \sum _ { i = 1 } ^ { m } ( x _ { i j } - \mu _ { j } ) ^ { 2 } } , j = 1 , 2 , \dots , n _ { \circ } \beta = ( \beta _ { 1 } , \beta _ { 2 } , \dots , \beta _ { n } ) , } \end{array}$ 和$\gamma = ( \gamma _ { 1 } , \gamma _ { 2 } , \dots , \gamma _ { n } )$ 是待定向量。

对任意实数 $x$ 和任意实数 $\alpha \in [ 0 , 1 )$ ，随机取舍(dropout)函数定义为

$$
\begin{array} { r } { \mathrm { d r p } ( x , \alpha ) = \{ \begin{array} { l l } { 0 , } & { \mathrm { b } \mathrm { , ~ } \forall \mathrm { ~ } \mathbb { H } \mathbb { E } \backslash \Xi \mathrm { \stackrel {  } { \alpha } ~ } \alpha \mathrm { ~ } \mathrm { H } \mathrm { X } \mathrm { I } \mathrm { E } \mathrm { I } \Xi , } \\ { \frac { x } { 1 - \alpha } , } & { \mathrm { b } \mathrm { , ~ } \forall \mathrm { ~ } \mathbb { H } \mathbb { E } \backslash \Xi \mathrm { \stackrel {  } { \alpha } ~ } 1 - \alpha \mathrm { ~ } \mathbb { H } \mathrm { X } \mathrm { I } \mathrm { E } \mathrm { I } \Xi . } \end{array}  } \end{array}
$$

drp 简称随取函数。对任意矩阵 $X$ 和任意实数 $\alpha \in [ 0 , 1 )$ ，随取函数作用到每个元素上

$$
\begin{array} { r l r } { \mathrm { d r p } ( X , \alpha ) } & { = } & { \left[ \begin{array} { c c c c } { \mathrm { d r p } ( x _ { 1 1 } , \alpha ) } & { \mathrm { d r p } ( x _ { 1 2 } , \alpha ) } & { \cdots } & { \mathrm { d r p } ( x _ { 1 n } , \alpha ) } \\ { \mathrm { d r p } ( x _ { 2 1 } , \alpha ) } & { \mathrm { d r p } ( x _ { 2 2 } , \alpha ) } & { \cdots } & { \mathrm { d r p } ( x _ { 2 n } , \alpha ) } \\ { \vdots } & { \vdots } & & { \vdots } \\ { \mathrm { d r p } ( x _ { m 1 } , \alpha ) } & { \mathrm { d r p } ( x _ { m 2 } , \alpha ) } & { \cdots } & { \mathrm { d r p } ( x _ { m n } , \alpha ) } \end{array} \right] . } \end{array}
$$

假设行向量 $\pmb { \hat { x } } = ( \hat { x } _ { 1 } , \hat { x } _ { 2 } , \dots , \hat { x } _ { n } )$ ，将行向量与矩阵相加定义为逐行相加，即

$$
X + \hat { \pmb x } = \left[ \begin{array} { c c c c } { x _ { 1 1 } + \hat { x } _ { 1 } } & { x _ { 1 2 } + \hat { x } _ { 2 } } & { \cdots } & { x _ { 1 n } + \hat { x } _ { n } } \\ { x _ { 2 1 } + \hat { x } _ { 1 } } & { x _ { 2 2 } + \hat { x } _ { 2 } } & { \cdots } & { x _ { 2 n } + \hat { x } _ { n } } \\ { \vdots } & { \vdots } & { \vdots } \\ { x _ { m 1 } + \hat { x } _ { 1 } } & { x _ { m 2 } + \hat { x } _ { 2 } } & { \cdots } & { x _ { m n } + \hat { x } _ { n } } \end{array} \right] .
$$

# 3BERT模型全貌

定义几个常数，并给出典型值。典型值是google预训练模型的一种参数配置，其它参数配置见BERT源码网站。 $n _ { 1 }$ 为词碎数量，典型值30522； $n _ { 2 }$ 为词碎嵌入宽度，典型值512； $n _ { 3 }$ 为词碎序列长度，典型值128； $n _ { 4 }$ 为被遮挡语碎数量，典型值20； $n _ { 5 }$ 为自注意力头数，典型值8;$n _ { 6 }$ 为单头宽度，等于 $\textstyle { \frac { n _ { 2 } } { n _ { 5 } } }$ ，典型值64； $n _ { 7 }$ 为全连接层宽数，典型值2048； $n _ { 8 }$ 为编码器层数，典型值8.

BERT模型的全貌见图2。BERT模型的输入是词碎序列，形式为$[ \mathrm { C L S } ] _ { \sqcup }$ 词碎 $2 _ { \sqcup }$ 词碎 $3 \cdots$ 词碎63[SEP]词碎 $6 5 _ { \scriptscriptstyle \perp }$ 词碎 66词碎127[SEP]□是显式空格，用来分隔词碎。第1个[SEP]（含）之前的词碎序列称为上句，第1个[SEP]（不含）之后的词碎序列称为下句。中间[SEP]的位置只是示意，不要求一定是第64个词碎。词碎序列中，一些随机位置上是[MASK]，它表示原来句中的词碎被“遮挡”了。例如：

$\mathrm { \small { [ C L S ] _ { \scriptscriptstyle \perp } } \ [ M A S K ] _ { \scriptscriptstyle \perp } \ [ M A S K ] _ { \scriptscriptstyle \perp } }$ 济南的雪 $\mathrm { _ { \perp } [ M A S K ] _ { \perp } }$ 下在了这[里，跑马岭位于济南南部山区 $\downarrow [ \mathrm { M A S K } ] _ { \downarrow }$ 海拔近 $\downarrow [ \mathbf { M A S K } ] _ { \downarrow }$ 米 $\begin{array} { r l } { \sqcup \circ } & { { } \sqcup \big [ \mathrm { S E P } \big ] _ { \sqcup } } \end{array}$ $[ \mathrm { M A S K } ] _ { \sqcup }$ 素裹的[MASK][MASK]云[雾[飘[渺，山中民 $[ \mathbf { M A S K } ] _ { \sqcup }$ 木屋格外精致，不用 $\downarrow [ \mathbf { M A S K } ] _ { \downarrow }$ 了 $\downarrow [ \mathbf { M A S K } ] _ { \perp }$ 计去砍树赚钱,□更不用与□熊大□熊二斗 $\downarrow [ \mathrm { M A S K } ] _ { \downarrow }$ 斗勇费心[劳 $\mathrm { \Omega _ { \perp } } \mathrm { [ M A S K ] _ { \perp } }$ ，□在□这[可 $\mathrm { \Delta [ M A S K ] _ { \perp } }$ 像光头[强一样惬意的蜗居一天，享受□ $[ \mathbf { M A S K } ] _ { \sqcup }$ 段美好的冰 $\downarrow [ \mathrm { M A S K } ] _ { \downarrow }$ 奇缘 $\downarrow [ \mathrm { M A S K } ] _ { \perp }$ #济南爆 $\downarrow [ \mathbf { M A S K } ] _ { \sqcup }$ ##忍[不住[想拍[的[SEP]

![](images/a65c60d8594c1ba538d39118a2ebad24d37818801ef5de4954e9ef4b527db4f0.jpg)  
图2：BERT模型全貌。词碎序列长度为128，编码器层数为8，这2个数字均可以按需调整。

这个例子中，上句是

$\mathrm { \Delta [ C L S ] _ { \perp } [ M A S K ] _ { \perp } [ M A S K ] _ { \perp } }$ 济南的雪 $\downarrow [ \mathbf { M A S K } ] _ { \perp }$ 下在了这里，跑马□岭位于济南南部山区 $[ \mathrm { M A S K } ] _ { \sqcup }$ 海拔近 $\downarrow [ \mathrm { M A S K } ] _ { \downarrow }$ 米。[SEP]

下句是

□[MASK]素裹的 $\ J [ \mathbf { M A S K } ] _ { \perp }$ [MASK]云[雾飘[渺，山中民 $\downarrow [ \mathrm { M A S K } ] _ { \downarrow }$ 木□屋格外精致，不用 $[ \mathbf { M A S K } ] _ { \sqcup }$ 了 $[ \mathrm { M A S K } ] _ { \sqcup }$ 计去砍树赚钱，更不用与熊大熊二斗 $\downarrow [ \mathrm { M A S K } ] _ { \downarrow }$ 斗勇费心劳 $\downarrow [ \mathbf { M A S K } ] _ { \downarrow }$ ，在这可 $\mathrm { _ { \perp } \ [ M A S K ] _ { \perp } }$ 像光头[强一样惬[意的蜗[居一天，享受 $\mathrm { \lrcorner [ M A S K ] _ { \scriptscriptstyle \perp } }$ 段美好的冰 $\downarrow [ \mathrm { M A S K } ] _ { \downarrow }$ 奇缘 $\downarrow [ \mathrm { M A S K } ] _ { \downarrow }$ #济南爆 $\downarrow [ \mathrm { M A S K } ] _ { \downarrow }$ ##忍[不[住[想[拍[的[[SEP]

上句和下句来自紧下方这条微博中的3句话，并将长度裁剪为128原来济南的雪都下在了这里，跑马岭位于济南南部山区，海拔近千米。

有幸亲临今冬初雪，银装素裹的山林云雾飘渺，山中民宿木屋格外精致，不用为了生计去砍树赚钱，更不用与熊大熊二斗智斗勇费心劳神，在这可以像光头强一样惬意的蜗居一天，享受这段美好的冰雪奇缘。

#济南爆料##忍不住想拍的冬日美景#@济南文旅发展集团

词碎进入BERT之后，立即被转化为向量。相应地，词碎序列转化为矩阵 $S$ ， $S$ 的每一个行向量对应一个词碎。接下来，矩阵 $S$ 被喂给第1个编码器，第1个编码器输出矩阵 $Z ^ { 1 }$ ，矩阵 $Z ^ { 1 }$ 随后被喂给第2个编码器。这样依次操作，第 $n _ { 8 }$ 个编码器的输出为 $Z ^ { n _ { 8 } }$ ，这也是BERT模型的输出。图2中的向量 $\phi$ 是 $Z ^ { n _ { 8 } }$ 的第1行。

为了得到BERT模型内部参数的最优值，需要2个任务来设定优化目标函数。上下句任务：判断词碎序列中的上句和下句是否为真实的承接关系。这要求制作一批正样本和一批负样本，正样本从相邻的句子中产生，负样从不同的文档中产生。遮挡任务：原论文称为“遮挡的语言模型”，猜测被遮挡的词。

# 4制作训练样本

训练语料通常来自多篇文章，每一篇文章都分割为多个句子。例如每条微博文本都可以视为一篇文章，话题、句号、问号均可以作为句子结束的标志。

从训练语料中生成一个词碎词典 $\mathcal { C } = \{ c _ { 1 } , c _ { 2 } , \ldots , c _ { n _ { 1 } } \}$ ，具体的生成方法有字对编码[6][7]（Byte Pair Encoding）、WordPiece和Unigram Language Model。词典中还要包含几个特殊的词碎：[CLS]、[SEP]、[MASK]、[PAD]、[UNK]。对中文来说，词碎是单个字、单个标点符号。对英文来说，词碎是组成单词的片段，例如un、##aff、##able，2个井号表示该词碎应该接在别的词碎后面。任何一个单词都可以分割成若干词碎，例如unaffable 能分割成un ##aff ##able。

将训练语料的中文句子和英文句子全部转化为词碎句子，此后提及的训练语料均指词碎形式的训练练语料。

词典的中每个词碎 $c _ { i }$ 都嵌入到一个行向量 $\mathbf { \Delta } d _ { i }$ ， $\mathbf { \delta } d _ { i }$ 的尺寸为 $1 \times n _ { 2 }$ ，尺寸典型值为 $1 \times 5 1 2$ 。将所有的行向量 $\mathbf { \delta } d _ { i }$ 按顺序排列起来，组成矩阵 $D = ( d _ { 1 } ; d _ { 2 } ; \ldots ; d _ { n _ { 1 } } )$ ，尺寸为 $n _ { 1 } \times n _ { 2 }$ ，尺寸典型值 $3 0 5 2 2 \times 5 1 2$ 。

训练样本分正样本和负样本，正样本词碎序列的上句和下句是真实的承接关系，负样本词碎序列的上句和下句之间没有承接关系。

从训练语料的同一篇文章中挑出2个相邻的句子适当裁剪，使2个句子的长度等于 $n _ { 3 } - 3$ ，典型值为125。按照形式“ $[ \mathrm { C L S } ] _ { \sqcup }$ 第1个句子 $\boldsymbol { \lrcorner } [ \boldsymbol { \mathrm { S E P } } ] _ { \sqcup }$ 第2个句子 $\boldsymbol { \lrcorner } [ \boldsymbol { \mathrm { S E P } } ]$ ”组成序列 $\tau$ ，记为

$$
\pmb { \tau } = \tau _ { 1 } \tau _ { 2 } \dots \tau _ { n _ { 3 } } ,
$$

这里的 $\tau _ { i } \in \mathcal { C } , i = 1 , 2 , \dotsc , n _ { 3 }$ 从 $\tau$ 随机挑出 $n _ { 4 }$ 个词碎，要求不能是[CLS]、[SEP]、[PAD]。这 $n _ { 4 }$ 个词碎在 $\tau$ 中的位置编号记为 $\pmb { \hat { t } } = ( \hat { t } _ { 1 } , \hat { t } _ { 2 } , \dots , \hat { t } _ { n _ { 4 } } )$ ，在词典 $\mathcal { C }$ 中的编号记为 $\tilde { \pmb { t } } = ( \tilde { t } _ { 1 } , \tilde { t } _ { 2 } , \dots , \tilde { t } _ { n _ { 4 } } )$ ，显然 $\hat { t } _ { i } \in \{ 1 , 2 , \dots , n _ { 3 } \}$ ， $\tilde { t } _ { i } \in \{ 1 , 2 , \ldots , n _ { 1 } \} \mathrm { ~ c ~ }$ （204号

对这 $n _ { 4 }$ 个位置 $( \hat { t } _ { 1 } , \hat { t } _ { 2 } , \dots , \hat { t } _ { n _ { 4 } } )$ ，随机挑出 $0 . 8 \times n _ { 4 }$ 个并将 $\tau$ 中的对应词碎替换为[MASK],随机挑出 $0 . 1 \times n _ { 4 }$ 个并将 $\tau$ 中的对应词碎并替换为 $\mathcal { C }$ 中的其它词碎；剩余 $0 . 1 \times n _ { 4 }$ 个位置， $\tau$ 中的对应词碎保持不变。将替换后的词碎序列记为 $\hat { \tau }$ ，即得到一个正样本。

如果从训练语料的不同文章中挑出2个句子，并用同样的方法制作成词碎序列 $\hat { \tau }$ ，就得到一个负样本。

第3节的语碎序列中，随机挑出来的遮挡的位置为

$$
\hat { t } = ( 2 , 3 , 8 , 2 6 , 3 0 , 3 4 , 3 8 , 3 9 , 4 8 , 5 7 , 6 0 , 7 7 , 8 3 , 8 8 , 1 0 5 , 1 1 1 , 1 1 4 , 1 1 6 , 1 1 9 ) ,
$$

对应的词碎为

原来都，千装山林宿为生智神以这雪。济料

这些词碎在词典 $\mathcal { C }$ 中的编号 $\tilde { t } =$ (1334,3342,6964,8025,1284,6164,2256,3361,2163,712,4496,3256,4869,810,6822,7435,512,3846,3161)。注意，词碎“济”保持不变。

# 5编码器

输入BERT模型的样本是词碎序列，不能直接进行矩阵、向量运算，需要先转换成矩阵形式。这个转换工作在第1个编码器前完成。

# 5.1 输人向量

给定训练样本 $\hat { \pmb { \tau } } = \hat { \tau } _ { 1 } \hat { \tau } _ { 2 } \dots \hat { \tau } _ { n _ { 3 } }$ 。对 $i = 1 , 2 , \dots , n _ { 3 }$ ，取出 $\hat { \tau } _ { i }$ 在矩阵 $D$ 中的对应行向量，记为 $\mathbf { \boldsymbol { s } } _ { i }$ 。将 $\mathbf { \boldsymbol { s } } _ { i }$ 按 $i$ 从小到大顺序排列起来，得到矩阵 $\boldsymbol { S } = ( s _ { 1 } ; s _ { 2 } ; \ldots ; s _ { n _ { 3 } } )$ ， $S$ 的尺寸为 $n _ { 3 } \times n _ { 2 }$ ，尺寸典型值 $1 2 8 \times 5 1 2$ 。

位置矩阵记为 $P$ ，尺寸为 $n _ { 3 } \times n _ { 2 }$ ，尺寸典型值 $1 2 8 \times 5 1 2$ 。 $P$ 的每一行对应词碎序列中的一个位置。称行向量 $f _ { 1 }$ 和 $f _ { 2 }$ 为句标向量，向量尺寸为 $1 \times n _ { 3 }$ ，尺寸典型值 $1 \times 5 1 2$ 。 $f _ { 1 }$ 对应词碎序列中的上句， $f _ { 2 }$ 对应词碎序列中的下句。记 $F = ( \pmb { f } _ { 1 } ; \pmb { f } _ { 1 } ; \dots ; \pmb { f } _ { 1 } ; \pmb { f } _ { 2 } ; \dots ; \pmb { f } _ { 2 } )$ ，尺寸为 $n _ { 3 } \times n _ { 2 }$ ，尺寸典型值 $1 2 8 \times 5 1 2$ 。对任意 $i = 1 , 2 , \dots , n _ { 3 }$ ，如果 $\hat { \tau } _ { i }$ 属于上句，那么 $F$ 的第 $\mathbf { \chi } _ { i }$ 行等于 $f _ { 1 }$ ；如果 $\hat { \tau } _ { i }$ 属于下句，那么 $F$ 的第 $i$ 行等于 $f _ { 2 }$ 。

令 $Z ^ { 0 } = S + P + F$ ，尺寸为 $n _ { 3 } \times n _ { 2 }$ ，尺寸典型值 $1 2 8 \times 5 1 2$ 。 $Z ^ { 0 }$ 是第1个编码器的输入矩阵。自注意力层的随取概率记为 $\alpha _ { 1 } \in [ 0 , 1 )$ ，全连接层的随取概率记为 $\alpha _ { 2 } \in [ 0 , 1 )$ 。在训练阶段,$\alpha _ { 1 }$ 和 $\alpha _ { 2 }$ 取值非零，官方代码中取值均为0.1；在预测阶段， $\alpha _ { 1 }$ 和 $\alpha _ { 2 }$ 均取值为0.

接下来的自注意力子层和全连接子层均指第1个编码器，不再每次说明。

# 5.2 自注意力子层

对 $i = 1 , 2 , \ldots , n _ { 5 }$ ，第 $i$ 头的“查”权重矩阵记为 $W ^ { 1 i 1 }$ ，尺寸 $n _ { \mathrm { 2 } } \times n _ { \mathrm { 6 } }$ ，尺寸典型值 $5 1 2 \times 6 4$ 第 $\mathbf { \chi } _ { i }$ 头的“查”偏置向量记为 $\pmb { b } ^ { 1 i 1 }$ ，尺寸 $1 \times n _ { 6 }$ ，尺寸典型值 $1 \times 6 4$ 。“查”矩阵

$$
Q ^ { 1 i } = Z ^ { 0 } W ^ { 1 i 1 } + b ^ { 1 i 1 } ,
$$

尺寸 $n _ { 3 } \times n _ { 6 }$ ，尺寸典型值 $1 2 8 \times 6 4$

对 $i = 1 , 2 , \ldots , n _ { 5 }$ ，第 $i$ 头的“键”权重矩阵记为 $W ^ { 1 i 2 }$ ，尺寸 $n _ { 2 } \times n _ { 6 }$ ，尺寸典型值 $5 1 2 \times 6 4$ 第 $\mathbf { \chi } _ { i }$ 头的“键”偏置向量记为 ${ \pmb b } ^ { 1 i 2 }$ ，尺寸 $1 \times n _ { 6 }$ ，尺寸典型值 $1 \times 6 4$ 。“键”矩阵

$$
K ^ { 1 i } = Z ^ { 0 } W ^ { 1 i 2 } + b ^ { 1 i 2 } ,
$$

尺寸 $n _ { 3 } \times n _ { 6 }$ ，尺寸典型值 $1 2 8 \times 6 4$

对 $i = 1 , 2 , \ldots , n _ { 5 }$ ，第 $i$ 头的“值”权重矩阵记为 $W ^ { 1 i 3 }$ ，尺寸 $n _ { 2 } \times n _ { 6 }$ ，尺寸典型值 $5 1 2 \times 6 4$ 第 $\mathbf { \chi } _ { i }$ 头的“值”偏置向量记为 $\pmb { b } ^ { 1 i 3 }$ ，尺寸 $1 \times n _ { 6 }$ ，尺寸典型值 $1 \times 6 4$ 。“值”矩阵

$$
V ^ { 1 i } = Z ^ { 0 } W ^ { 1 i 3 } + b ^ { 1 i 3 } ,
$$

尺寸 $n _ { 3 } \times n _ { 6 }$ ，尺寸典型值 $1 2 8 \times 6 4$

记

$$
R ^ { 1 i } = \mathrm { d r p } \left( \operatorname* { s m a x } \left( \frac { Q ^ { 1 i } ( K ^ { 1 i } ) ^ { T } } { \sqrt { n _ { 6 } } } \right) , \alpha _ { 1 } \right) .
$$

第 $\mathbf { \chi } _ { i }$ 头的归一化分值为

$$
U ^ { 1 i } = R ^ { 1 i } V ^ { 1 i } ,
$$

尺寸为 $n _ { 3 } \times n _ { 6 }$ ，尺寸典型值 $1 2 8 \times 6 4$ 。将所有头的归一化分值连接起来，就得到第1个编码器自注意力的分值

$$
\boldsymbol { U } ^ { 1 } = ( U ^ { 1 1 } , U ^ { 1 1 } , \dots , U ^ { 1 n _ { 5 } } ) ,
$$

尺寸 $n _ { 3 } \times n _ { 2 }$ ，尺寸典型值 $1 2 8 \times 5 1 2$

$W ^ { 1 \cdot 4 }$ 为权重矩阵，尺寸 $n _ { 2 } \times n _ { 2 }$ ，尺寸典型值 $5 1 2 \times 5 1 2 \textmd { o } b ^ { 1 \cdot 4 }$ 为第1个编码器偏置向量，尺寸 $1 \times n _ { 2 }$ ，尺寸典型值 $1 \times 5 1 2$ 。线性变换后施加随取操作，得

$$
Y ^ { 1 1 } = \mathrm { d r p } ( U ^ { 1 } W ^ { 1 \cdot 4 } + { \pmb b } ^ { 1 \cdot 4 } , \alpha _ { 2 } ) .
$$

做一个层归一化操作，得到自注意力子层的输出

$$
Y ^ { 1 2 } = \operatorname { l n o r } ( Y ^ { 1 1 } + Z ^ { 0 } ) ,
$$

尺寸 $n _ { 3 } \times n _ { 2 }$ ，尺寸典型值 $1 2 8 \times 5 1 2$

# 5.3 全连接子层

$W ^ { 1 \cdot 5 }$ 为全连接权重矩阵，尺寸 $n _ { 2 } \times n _ { 7 }$ ，尺寸典型值 $5 1 2 \times 2 0 4 8$ 。 $\pmb { b } ^ { 1 \cdot 5 }$ 为全连接偏置向量,尺寸 $1 \times n _ { 7 }$ ，尺寸典型值 $1 \times 2 0 4 8$ 。全连接层的输出为

$$
Y ^ { 1 3 } = \mathrm { g e l u } ( Y ^ { 1 2 } W ^ { 1 \cdot 5 } + b ^ { 1 \cdot 5 } ) ,
$$

尺寸 $n _ { 3 } \times n _ { 7 }$ ，典型尺寸 $1 2 8 \times 2 0 4 8$ =

$W ^ { 1 \cdot 6 }$ 为线性变换权重矩阵，尺寸 $n _ { \mathrm { { 7 } } } \times n _ { \mathrm { { 2 } } }$ ，尺寸典型值 $2 0 4 8 \times 5 1 2$ 。 ${ \pmb b } ^ { 1 \cdot 6 }$ 为线性变换偏置向量，尺寸 $1 \times n _ { 2 }$ ，尺寸典型值 $1 \times 5 1 2$ 。用线性变换将尺寸 $n _ { 3 } \times n _ { 7 }$ 变回 $n _ { 3 } \times n _ { 2 }$ ，然后作一下随取操作，即

$$
Y ^ { 1 4 } = \mathrm { d r p } ( Y ^ { 1 3 } W ^ { 1 \cdot 6 } + \pmb { b } ^ { 1 \cdot 6 } , \alpha _ { 2 } ) .
$$

施加一个层归一化操作，得到第1个编码器的输出

$$
Z ^ { 1 } = \mathrm { l n o r } ( Y ^ { 1 4 } + Y ^ { 1 2 } ) ,
$$

尺寸 $n _ { 3 } \times n _ { 2 }$ ，尺寸典型值 $1 2 8 \times 5 1 2$

# 5.4 编码器堆叠

第1个编码器的输入是矩阵是 $Z ^ { 0 }$ ，输出矩阵是 $Z ^ { 1 }$ 。每个编码器内部的计算过程都一样，第2个编码器的输入矩阵是 $Z ^ { 1 }$ ，输出矩阵是 $Z ^ { 2 }$ 。依次类推，第 $n _ { 8 }$ 个编码器的输入矩阵是 $Z ^ { n _ { 8 } - 1 }$ ，输出矩阵是 $Z ^ { n _ { 8 } }$ .对 $j = 1 , 2 , \dots , n _ { 8 }$ ，矩阵 $Z ^ { j }$ 的尺寸是 $n _ { 3 } \times n _ { 2 }$ ，尺寸典型值是 $1 2 8 \times 5 1 2$ 。

# 6训练任务

训练BERT模型时，使用2个任务：上下句匹配、词碎遮挡。

# 6.1 上下句匹配任务

记 $\phi = Z _ { 1 : } ^ { n _ { 8 } }$ ，即词碎[CLS]对应的向量。 $\phi$ 的尺寸为 $1 \times n _ { 2 }$ ，尺寸典型值 $1 \times 5 1 2$ 令 $E$ 是尺寸为 $2 \times n _ { 2 }$ 的矩阵，尺寸典型值为 $2 \times 5 1 2$ 。令 $\eta$ 是尺寸为 $1 \times 2$ 的向量。当输入序列 $\hat { \tau }$ 的上句和下句是真实的承接关系时， ${ \pmb \xi } = ( 0 , 1 )$ ，否则 ${ \boldsymbol { \xi } } = ( 1 , 0 )$ 。任务权重矩阵记为 $\hat { W } ^ { 1 }$ ，尺寸为$n _ { 2 } \times n _ { 2 }$ ，尺寸典型值 $5 1 2 \times 5 1 2$ 。任务偏置向量记为 $\hat { \pmb { b } } ^ { 1 }$ ，尺寸为 $1 \times n _ { 2 }$ ，尺寸典型值 $1 \times 5 1 2$ 。上下句匹配任务的目标函数为

$$
l _ { 1 } = - \log ( \operatorname { s m a x } ( \operatorname { t a n h } { ( \phi \hat { W } ^ { 1 } + \hat { b } ^ { 1 } ) E ^ { T } } + \eta ) ) \pmb { \xi } ^ { T } .
$$

# 6.2 词碎遮挡任务

从 $Z ^ { n _ { 8 } }$ 中取出行号为 $\hat { t } _ { 1 } , \hat { t } _ { 2 } , \dots , \hat { t } _ { n _ { 4 } }$ 的行向量,按顺序排列起来,组成矩阵 ${ \hat { Z } } ^ { 2 }$ ，尺寸为 $n _ { 4 } \times n _ { 2 }$ ，尺寸典型值 $2 0 \times 5 1 2$ 。任务权重矩阵记为 $\hat { W } ^ { 2 }$ ，尺寸为 $n _ { 2 } \times n _ { 2 }$ ，尺寸典型值 $5 1 2 \times 5 1 2$ ；任务偏置向量记为 $\hat { b } ^ { 2 }$ ，尺寸为 $1 \times n _ { 2 }$ ，尺寸典型值 $1 \times 5 1 2$ .词典 $c$ 的偏置向量记为 $\textbf { \textit { b } }$ ，尺寸为 $1 \times n _ { 1 }$ ，尺寸典型值 $1 \times 3 0 5 2 2$ .令

$$
H = - \log ( \operatorname { s m a x } ( \operatorname { g e l u } ( \hat { Z } ^ { 2 } \hat { W } ^ { 2 } + \hat { b } ^ { 2 } ) D ^ { T } + b ) ) ,
$$

$H$ 的尺寸为 $n _ { 4 } \times n _ { 1 }$ ，尺寸典型值 $2 0 \times 3 0 5 2 2$

根据编号向量 $\tilde { \pmb { t } } = ( \tilde { t } _ { 1 } , \tilde { t } _ { 2 } , \dots , \tilde { t } _ { n _ { 4 } } )$ ，从 $H$ 中取出元素求平均值，就得本任务的目标函数，即

$$
l _ { 2 } = \frac { 1 } { n _ { 4 } } \sum _ { i = 1 } ^ { n _ { 4 } } { h _ { i , \tilde { t } _ { i } } } ,
$$

这里的 $h _ { i , \tilde { t } _ { i } }$ 是矩阵 $H$ 的元素。

# 6.3 模型预训练

以 $l _ { 1 } + l _ { 2 }$ 为目标函数，以 $\hat { \tau }$ 为样本进行训练，即可得到所有的待定参数。

# 7待定参数的数量

第4节中,矩阵 $D$ 参数量为 $n _ { 1 } n _ { 2 }$ 。第5.1节中,矩阵 $P$ ，参数量为 $n _ { 3 } n _ { 2 }$ ；句标向量 $f _ { 1 }$ 和 $f _ { 2 }$ 的参数量为 $2 n _ { 2 }$ 。

第5.2节中,矩阵 $W ^ { 1 i 1 }$ 、 $W ^ { 1 i 2 }$ 和 $W ^ { 1 i 3 }$ 的参数量均为 $n _ { 2 } n _ { 6 }$ ，向量 $\pmb { b } ^ { 1 i 1 }$ 、 ${ \pmb b } ^ { 1 i 2 }$ 和 $\pmb { b } ^ { 1 i 3 }$ 的参数量均为 $n _ { 6 }$ ， $W ^ { 1 \cdot 4 }$ 的参数量为 $n _ { 2 } ^ { 2 }$ ，向量 ${ \pmb b } ^ { 1 \cdot 4 }$ 的参数量为 $n _ { 2 }$ ; $Y ^ { 1 2 }$ 对应的函数lnor 中隐含 $2 n _ { 2 }$ 个参数。第5.3节中，矩阵 $W ^ { 1 \cdot 5 }$ 的参数量为 $n _ { 2 } n _ { 7 }$ ，向量 $\boldsymbol { b } ^ { 1 \cdot 5 }$ 的参数量为 $n _ { 7 }$ ；矩阵 $W ^ { 1 \cdot 6 }$ 的参数量为$n _ { 7 } n _ { 2 }$ ，向量 ${ \pmb b } ^ { 1 \cdot 6 }$ 的参数量为 $n _ { 2 }$ ; $Z ^ { 1 }$ 对应的函数 lnor 中隐含 $2 n _ { 2 }$ 个参数。

第6.1节中，矩阵 $E$ 的参数量为 $2 n _ { 2 }$ ，矩阵 $\hat { W } ^ { 1 }$ 的参数量为 $n _ { 2 } ^ { 2 }$ ，向量 $\hat { \pmb { b } } ^ { 1 }$ 的参数量为 $n _ { 2 }$ 。第6.2节中，矩阵 $\hat { W } ^ { 2 }$ 的参数量为 $n _ { 2 } ^ { 2 }$ ，向量 $\hat { b } ^ { 2 }$ 的参数量为 $n _ { 2 }$ ，向量 $\hat { b }$ 的参数量为 $n _ { 1 }$ 。

将这些数量相加，即得BERT模型待定参数的数量

$$
\begin{array} { r } { n _ { 8 } ( n _ { 2 } ^ { 2 } + 3 n _ { 2 } n _ { 6 } + 2 n _ { 2 } n _ { 7 } + 4 n _ { 2 } + 3 n _ { 6 } + n _ { 7 } ) + n _ { 1 } n _ { 2 } + 2 n _ { 2 } ^ { 2 } + n _ { 2 } n _ { 3 } + 6 n _ { 2 } + n _ { 1 } . } \end{array}
$$

当 $n _ { 1 } \sim n _ { 8 }$ 的取值为第3节中的典型值时，待定参数的数量为35945786。

# 参考文献

[1]Jacob Devlin,Ming-Wei Chang,KentonLee,etal.BERT: Pre-trainingofDeep Bidirectional Transformers forLanguage Understanding.arXiv:1810.04805.2018.4   
[2]Zhenzhong Lan,Mingda Chen,Sebastian Goodman,etal.ALBERT:A Lite BERTfor Self-supervised Learning of Language Representations.arXiv:1909.11942.2019.11   
[3]Zhilin Yang,ZihangDai,Yiming Yang,etal. XLNet: Generalized Autoregressive Pretraining forLanguage Understanding. arXiv:1906.08237. 2019.6   
[4]Yinhan Liu，Myle Ott，Naman Goyal,et al.RoBERTa:A Robustly Optimized BERT Pretraining Approach. arXiv:1907.11692.2019.7   
[5] Ashish Vaswani,Noam Shazeer,NikiParmar, et al.Atention Is All You Need.arXiv:1706.03762.2017.3   
[6] Gage,Philip.A New Algorithm for Data Compression. The C User Journal. 1994   
[7] A New Algorithm for Data Compresson.Dr. Dobb's Journal.1 February 1994.Retrieved 10 August 2020