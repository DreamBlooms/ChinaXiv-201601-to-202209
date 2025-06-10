# 面向中文敏感词变形体的识别方法研究

付聪1，余敦辉1,2†，张灵莉1

(1．湖北大学 计算机与信息工程学院，武汉 430062;2.湖北省教育信息化工程技术中心，武汉 430062)

摘要：为净化网络环境，需要对网络信息进行审查。针对网络信息中所包含的敏感词，尤其是中文敏感词变形体的识别成为了一个迫切需要解决的问题。通过分析汉字的结构和读音等特征提出了一种中文敏感词变形体的识别方法。该方法针对词的拼音、词的简称和词的拆分三种敏感词变形体分别设计了基于易混拼音分组的敏感词的识别算法(SPGR）、字符串的简称识别算法（SNR）和基于KMP的汉字拆分识别算法（WS-KMP)，有效提高了敏感词审查的准确率和效率。实验结果表明，该方法在识别中文敏感词变形体的时候有较高的查全率和查准率。

关键词：变形体；敏感词识别；编辑距离；KMP算法 中图分类号：TP391.1 doi:10.3969/j.issn.1001-3695.2017.11.0996

# Study on identification method for change form of Chinese sensitive words

Fu Cong], Yu Dunhui1, 2†, Zhang Lingli1 (1.SchoolofComputerScience&InformationEngineeringHubeiUniversityWuhan43o62,China;2.HubeiProvincialCenter forEducation Information Technology Studies,Wuhan 43oo62,China)

Abstract: Topurify thenetwork environment,thenetworkinformationneeds tobereviewed.Recognizing thesensitive words inthe network information,especiallthechange form of Chinese sensitive words,is an urgent problemto be solved.By analyzing thestructureand pronunciationofChinesecharacters,this paperproposesamethodofrecognitionofthechange form of Chinesesensitive words.This method has designed sensitive wordrecognition algorithm based on the grouping ofconfusing pinyin,Stringabbreviationrecognitionalgorithmandrecognitionalgorithm basedonKMP'scharactersplitrecognition algorithmforthepinyinof word,theabbreviationof wordandthe splitof word,andimprovetheaccuracyand effciencyof the review.The experimentalresultsshow thattheproposed methodhashigherrecalland precision whenrecognizingthechange form of Chinese sensitive words.

Key Words: change form; sensitive word recognition; edit distance; KMP algorithm

# 0 引言

随着互联网的高速发展，各种各样的信息资源呈指数级增长，非法言论（如黄赌毒、恐怖、暴力血腥信息）经常充斥其中[1-2]，这些不良信息通常带有一些敏感词汇，从而很可能引起不良的连锁反映，对国家安全、社会稳定和网络环境的健康形成严重威胁，造成巨大的负面影响。因此，对于敏感词的识别已经成为一个迫切需要解决的研究课题。

当前，对敏感词的识别研究较为成熟，一般是基于敏感词表进行。基本思想是对待检测的文本进行检索，若其中含有敏感词，则系统会判定该文本为需要审查的文本。这种方法实现起来比较简单，但查找的效率不高。对此，文献[3]提出一种 ST-DFA 算法,通过敏感词拼音的第一个字母来构建敏感信息决策树，其优点是不依赖敏感信息语料库，能够提高敏感信息的检测效率。缺点是对敏感词变形体无处理能力。

当前，对中文敏感词变形体的识别方法的研究还处于起步阶段，相关研究成果并不是太多，文献[4针对变异的敏感词汇提出了一种方法。将某特殊字符转换成形状相似的字母，然后再进行检测。例如：将字符“ $@$ ”转换成字母“a”,遇到“@rse”词后，将这个词换成“arse”来处理。文献[5]采用机器学习的方法,通过采用bigram、词干等作为特征值来对文本信息做分类分析，以检测出变形体。文献[6]利用贝叶斯滤波技术对恶意内容进行检测,利用近似的字符串匹配技术来提高检测恶意内容的有效性。文献[7]提出了一种基于语音的字符串匹配算法，该算法用于解决发音相似的字符串的匹配。这些方法对英文字符有较好的处理效果，但没有将中文敏感词变形体考虑在内。

由此可见，寻找更有效的中文敏感词变形体识别算法是当务之急。本文结合英文字符串变形体的识别方法，提出了一种中文敏感词变形体识别方法。该方法结合了汉字的发音与结构特征，在识别的过程中加入拼音、简称、拆分三种变形体形式，能够有效的识别出中文敏感词及其相关的变形体。

# 1 相关算法

现有的字符串识别算法有基于相似度的匹配方法和精准匹配的模式匹配算法。基于编辑距离的相似度的匹配方法能够很好体现出一个字符串变为另一个字符串所需的"代价”，“代价”越小相似度越高。精确匹配常用的是KMP算法，相较与朴素的模式匹配算法减少了字符串匹配次数。

# 1.1基于编辑距离的相似度计算

1965年俄罗斯科学家VladimirLevenshtein提出了编辑距离（editdistance）概念[8],又称为Levenshtein 距离，是指两个字符串之间，由一个转成另一个所需的最少编辑操作次数。许可的编辑操作包括将一个字符替换成另一个字符，插入一个字符，删除一个字符。编辑距离被经常用于计算两个字符串之间的差异程度，编辑距离越小两个字符串的相似度越大[9-10]。本文利用编辑距离计算相似度、并利用归一化方法将其映射到[0,1]区间：

$$
\mathrm { S i m i l a r ( s , a ) } = 1 - \frac { \mathrm { e d i t ( l e n g t h ( s ) , l e n g t h ( a ) ) } } { \mathrm { m a x ( l e n g t h ( s ) , l e n g t h ( a ) ) } }
$$

其中：edit(length(s),length(a))表示字符串 $s$ 与 $\mathbf { \Phi } _ { t }$ 的编辑距离,length(s)表示字符串 $s$ 的长度，max(length(s),length(a))表示length(s)与length(a)中长度较大的部分。

# 1.2 KMP 算法

1969年Knuth、Morris和Pratt提出快速单模式匹配KMP算法[]。它的主要思想是：每当一次匹配过程中出现字符不匹配时，不需要回退指针，而是利用已经得到的“部分匹配”的结果将模式向右移动尽可能远的一段距离，继续匹配过程。

设目标串表示为 $S = S [ \mathrm { s } _ { 1 } , \mathrm { s } _ { 2 } , \cdots , \mathrm { s } _ { \mathrm { n } } ]$ ，长度为 $\mathfrak { n }$ ；模式串表示为 $A = A [ \mathbf { a } _ { 1 } , \mathbf { a } _ { 2 } , \cdots , \mathbf { a } _ { \mathrm { n } } ]$ ，长度为 $\mathrm { ~ m ~ }$ ；并且满足条件 ${ \boldsymbol { n } } > m$ 。如果存在i使得 $\mathrm { S [ i ] } = A [ 1 ] , \mathrm { S [ i + 1 ] } = A [ 2 ] , \cdots , \mathrm { S [ i + } m - 1 ] = A [ \mathrm { m } ]$ ，则匹配成功,模式串P就出现在目标串T的i处。若S[i]=A[j],则继续比较 $\mathbf { S } [ \mathrm { i } + 1 ] = A [ \mathrm { j } + 1 ]$ ；若 $\mathbf { S } [ \mathrm { i } ] \neq A [ \mathrm { j } ]$ ，则i值不变，j为$n e x t ( \mathrm j )$ ，再进行下一轮的匹配。其中 $n e x t ( \mathrm { j } )$ 的值表示$[ \mathbf { a } _ { 1 } , \mathbf { a } _ { 2 } , \cdots , \mathbf { a } _ { j - 1 } ]$ 中后缀等于相同字符序列的前缀的最长后缀的长度，对next数组的定义如下：

$$
N e x t ( \mathrm { j } ) = \left\{ \begin{array} { l l } { - 1 , \frac { { \mathrel { \cdot } } \xi } { \Longrightarrow { \textnormal { \ j } } \mathcal { I } = 1 \beta \mathrm { \neq } \mathrm { \emptyset } } } \\ { m a x \{ k | 0 < k < j , \mathcal { H } \mathrm { \# } \mathrm { \# } \mathrm { \# } \} } \\ { 0 , \frac { \mathrm { \# } \mathrm { \# } \mathrm { \# } \mathrm { \# } \mathrm { \# } \mathrm { \# } } { \vrule \mathrm { \# } \mathrm { \# } \mathrm { \# } \mathrm { \# } \mathrm { \# } } } \end{array} \right.
$$

在下一次匹配时只需确定i的位置即可，从而提高模式匹配的效率。

# 2 敏感词变形体

本文研究的敏感词变形体包括以下三个模式：一是词的拼音模式。在中文中，同一个汉语拼音可能对应多个不同的汉字。且由于不同省市地区方言的差异性，导致了一些带有地域性特点的汉语拼音容易被混淆，如某些地区很难分辨"T"和"n”。二个是词的简称模式。在人们的日常生活中，对于字数较多的词，经常会以简称的形式替代。据统计，在汉语新闻文章里，在 $20 \%$ 左右的句子可能含有缩略语[2]。第三个是词的拆分模式。由于现在各个网络平台对信息的审查越来越严格，网络上出现了通过拆字的方式来逃避审查，比如"林"可以拆成"木木"[13]。以词“贩卖毒品”为例，其变形体的具体结构如图1所示。

![](images/90126399740a6ebd8040188738b216f3d2b8b54964b88d2469433fd4547cde32.jpg)  
图1词变形体结构图

为了更好地识别出敏感词的变形体，本文基于已有的敏感词列表提出了敏感词变形体的识别算法（以下简称为DFR（deformationformrecognition）算法），对敏感词变形体进行识别。并且对不同的变形体形式给出了不同的处理方法，设计了一种基于易混拼音分组的敏感词识别算法（SPGR)，通过相似度的计算识别出敏感词的拼音变形体，构建了字符串的简称识别算法（SNR)，通过敏感词的首字母和缩写规则识别出敏感词的简称变形体，提出了一种基于KMP的汉字拆分识别算法（WS-KMP)，通过分析汉字的结构对拆分后的敏感词进行模式匹配实现敏感词拆分变形体的识别。

# 3 敏感词变形体整理及处理方法

# 3.1 词的拼音模式

目前，存在很多利用具有与敏感词中读音相似的汉字来替换敏感词中汉字的情况，例如“去死（qusi)”为敏感词，恶意用户为了避开网络平台的审查，多数情况下会使用“去屎（qushi)”一词来替代。这样，不仅表达了其含义，也不会被平台所追究。为了识别出敏感词拼音的变形体，本文将敏感词与疑似敏感词转换成音码并通过编辑距离计算其相似度，判断该词是否为敏感词。

# 3.1.1音码编码 （soundcode SC)

音码即为汉字拼音的编码方式，能够用编码形象的表示出汉字的拼音特征，从而表示出汉字的读音特征。基于音码可将汉字的拼音转换成相应的字符序列，其结构如图2所示。

![](images/7f93b8a9d1f468d542cc8c91c966e679e4161ff46a6468af1ac4d732e89f93dc.jpg)  
图2音码结构图

本文采用三位音码的的形式，利用字母对其中每一位音码进行编码。三位音码中，设第一位为声母位，第二位为韵母位，第三位为声调位。根据1958年第一届全国人民代表大会第五次会议批准公布推行的《汉语拼音方案》[14]，其中包含声母 23个，韵母34个，为了方便编码，声调分为阴平、阳平、上声、去声和轻声。声母、韵母和声调的部分编码如表1、表2、表3所示。

表1声母编码表  

<html><body><table><tr><td>声母</td><td>b</td><td>p</td><td>m</td><td>f</td><td>d</td><td>t</td><td></td></tr><tr><td>编码</td><td>A</td><td>B</td><td>C</td><td>D</td><td>E</td><td>F</td><td>··</td></tr><tr><td></td><td></td><td>表2</td><td></td><td>韵母编码表</td><td></td><td></td><td></td></tr><tr><td>韵母</td><td>a</td><td>0</td><td>e</td><td>ai</td><td>ei</td><td>ao</td><td></td></tr><tr><td>编码</td><td>A</td><td>B</td><td>C</td><td>D</td><td>E</td><td>F</td><td></td></tr><tr><td></td><td></td><td>表3</td><td></td><td>声调编码表</td><td></td><td></td><td></td></tr><tr><td>声调</td><td>阴平</td><td>阳平</td><td></td><td>上声</td><td></td><td>去声</td><td>轻声</td></tr><tr><td>编码</td><td>A</td><td>B</td><td></td><td>C</td><td></td><td>D</td><td>E</td></tr></table></body></html>

通过以上编码，可将汉字转换成一系列的字符序列，以便进行下一步的计算和比较。以“海洛因”为例，基于以上编码表得到的音码为“KDCHXDPTA”。

# 3.1.2易混拼音分组

文献[15]提出了一种基于语音的字符串匹配算法，该算法用于解决英文发音相似的字符串之间的匹配问题。基于该算法，本文提出将中文易混拼音进行分组，并对所有分组赋予了一个相似性因子（该值区间为[0.1]，其值越低说明字符串的相似度就越高)。

易混拼音主要分为三种：平舌音与翘舌音、边音与鼻音、前鼻音与后鼻音。表5是易混拼音分组的部分数据，该表的拼音分组以及相似性因子参考了文献[12]。每组相似性因子代表同组拼音被替换成同一组中的另一个拼音需要付出的“代价”，若两个拼音相同，则它们的“代价”就是0，若两个拼音不相同，并且也没有在同一个组里面，那么他们的“代价”是1。通过对汉语拼音的研究，部分分组情况如表4所示。

表4易混拼音分组  

<html><body><table><tr><td>易混拼音</td><td>z,zh</td><td>n,1</td><td>en,eng</td><td>：</td></tr><tr><td>音码</td><td>S,R</td><td>G,H</td><td>J,K</td><td></td></tr><tr><td>相似性因子</td><td>0.5</td><td>0.5</td><td>0.5</td><td></td></tr></table></body></html>

# 3.1.3基于易混拼音分组的敏感词识别算法

设有敏感词S和疑似敏感词A，通过建立unicode的编码与汉语拼音对应的集合把汉字转换成带有声调的拼音（Pinyin4j为汉字转拼音的java工具类)，然后根据音码表将其转换成音码s和a且length(s) $\mathrel { \mathop = } \mathrm { i } ( \mathrm { i } > 0 )$ ，

length(a) $) = \mathrm { j } ( \mathrm { j } > 0 )$ ,其编辑距为

$$
e d i t ( i , j ) = \left\{ \begin{array} { l l } { i , j = 0 } \\ { j , i = 0 } \\ { \qquad \left( e d i t \left( i , j - 1 \right) + 1 , \left( i > 0 , j > 0 \right) \right. } \\ { \qquad \left. \operatorname* { m i n } \left\{ e d i t \left( i - 1 , j \right) + 1 , \left( i > 0 , j > 0 \right) \right. } \\ { e d i t \left( i - 1 , j - 1 \right) + r \left( s , i , j \right) \ , \left( i > 0 , j > 0 \right) \right. } \end{array} \right.
$$

采用易混拼音分组之前，函数 $\mathbf { r } ( \mathbf { s } _ { \mathrm { _ i } } , \mathbf { a } _ { \mathrm { _ j } } )$ 定义如下：

$$
r ( s _ { i } , a _ { j } ) = \left\{ { O } \atop { I } \quad s _ { i } \neq a _ { j } \right.
$$

采用易混拼音分组之后，函数 $\mathbf { r } ( \mathbf { s } _ { \mathrm { _ i } } , \mathbf { a } _ { \mathrm { _ j } } )$ 定义如下：

$$
\begin{array} { r } { r ( s _ { i } , a _ { j } ) = \left\{ \begin{array} { l l } { \boldsymbol { \theta } } & { s _ { i } = a _ { j } } \\ { \boldsymbol { I } } & { s _ { i } , a _ { j } \vert \boldsymbol { \Xi } \vert \boldsymbol { \mathcal { Z } } \boldsymbol { \mathrm { H } } } \\ { \boldsymbol { I } } & { s _ { i } \neq a _ { j } \boldsymbol { \mathcal { H } } \boldsymbol { \mathcal { H } } \boldsymbol { \mathcal { H } } \boldsymbol { \left| \boldsymbol { \Xi } \right| } \boldsymbol { \mathcal { H } } } \end{array} \right. } \end{array}
$$

其中：a 是字符 $s _ { i }$ 和 $a _ { j }$ 所在组的相似性因子。相似度计算公式如下：

$$
\mathrm { S i m i l a r ( s , a ) } = 1 - \frac { \mathrm { e d i t ( l e n g t h ( s ) , l e n g t h ( a ) ) } } { \mathrm { m a x ( l e n g t h ( s ) , l e n g t h ( a ) ) } }
$$

为了识别出敏感词的拼音变形体，本文提出基于易混拼音分组的敏感词的识别算法（以下简称为SPGR（SimilarPinyinGroupingRecognition）算法）。算法具体的执行过程如算法1所示。

算法1.SPGRalgorithm输入：敏感词S，疑似敏感词变形体A输出：A是否为S的拼音变形体

1.若 S.equals(A)为 true，则S与A为同一字符串，end.

2.若 S.equal(A)为 false，则根据编码表获取S 与A 的音码s与a，且 $\mathrm { i } =$ length(s) ， ${ \mathrm { j } } =$ length(a) ;

3.通过方法 $e d i t ( i , j )$ 得到音码的编辑距离;

4.通过方法 $m a x \big ( i , j \big )$ 获取音码长度较大的部分；

5.计算相似度 Similar(s,a);

6.若 $\sin i l a r ( \mathrm { s } , \mathrm { a } ) > \theta$ （ $\theta$ 为阈值)，则字符串 A为字符串 S 的拼音变形体，end.

7.若 $\quad S i m i l a r ( { \mathrm { s } } , { \mathrm { a } } ) \leq \theta$ ，则字符串 A不为字符串 S 的拼音变 形体，算法结束，end.

以“海洛因”和“海诺因”为例，设 $\theta$ 为 $90 \%$ ，其拼音分别为“hailuoyin”和“hainuoyin”,转换成音码之后为“KDCHXDPTA”和“KDCGXDPTA"，采用易混拼音分组之前相似度为 $8 8 . 8 9 \%$ ，之后为 $9 4 . 4 4 \%$ ,相似度明显提高且大于 $90 \%$ 则“海诺因”为“海洛因”的拼音变形体。

# 3.2 词的简称模式

3.2.1词的简称

词的简称模式包括首字母缩写和词的缩写。其中首字母缩写如“法轮功”缩写为“flg”。

词的缩写的一般分为三种形式:压缩、节略和统括[16]，其中又以压缩和节略的组合生成模式最为常见。压缩，是指把全称分割为几个词语，然后从每个词语中抽取最能代表原义的汉字保留，例如“贩卖\毒品”的简称为“贩毒”;节略是指在全称中直接省去部分词语，留下另一部分词语作为简称，例如“复旦\大学”的简称为“复旦”。压缩和节略的基本思想都是从全称中选取部分汉字或者词语重组形成简称。在重组的过程中，字序一般不会发生改变。简称中的汉字全部包含于词的全称中，因此，找到词全称的子集就可以找到其简称。如：中文字符串S=sSSsn(n>1）是由n个汉字构成，存在另外一个由m个汉字构成的字符串 $\mathbf { A } = \mathbf { a } _ { \mathrm { { l } } } \mathbf { a } _ { 2 } \cdots \mathbf { a } _ { \mathrm { { m } } } ( 1 \leqslant \mathbf { m } < \mathbf { n } )$ ，对于任何一个字$a _ { i } \in A ( 1 \leq i \leq m )$ ，都有 $\mathbf { a } _ { \mathrm { i } } = \mathbf { s } _ { \mathrm { j } } ( 1 \leq \mathrm { i } \leq \mathbf { m } , \mathrm { i } \leq \mathrm { j } \leq \mathrm { n } )$ ，且随着i值的递增， $\mathrm { ~ j ~ }$ 也呈递增趋势，则称A 为S 的简称。

# 3.2.2敏感词的简称识别算法

为了准确识别出敏感词的简称，本文提出了敏感词的简称识别算法（以下简称为SNR（ShortNameRecognition）算法）。对于敏感词首字母缩写的识别，首先利用Pinyin4j获取敏感词与疑似敏感词的的首字母，然后再对首字母进行字符串的比对；对于敏感词缩写的识别，将疑似敏感词的每个字符在敏感词中按照顺序进行匹配。算法具体的执行过程如算法2所示。

算法2.SNRalgorithm输入：敏感词S，疑似敏感词变形体A输出：A是否为S的简称变形体

1.获取字符串的首字母S',若 $\mathrm { S ^ { \prime } { = } A . }$ 则字符串A为字符串S的简称， end.

2.根据字符串 S 和待判断字符串 A 的有序集合 ${ \cal S } = (  { \mathbf { s } } _ { 1 }  { \mathbf { s } } _ { 2 } \cdots  { \mathbf { s } } _ { m } )$ 和$A = ( \mathbf { a } _ { 1 } a _ { 2 } \cdots a _ { n } )$ 得到 $m = l e n g t h ( { \mathrm { S } } ) \ , n = l e n g t h ( { \mathrm { A } } )$ 3.若 $m > n$ ,设ij分别为S,A的下标，初始值都为0;4.若 $i < m$ && $j < n$ && $S _ { i } = A _ { j }$ ，,则 $i + + , \quad j + +$ ，继续执行步骤4;5.若 $i < m$ && $j < n$ && ${ \bf \nabla } . { \cal S } _ { i } \not = { \cal A } _ { j }$ ，则 $i + +$ ，跳到步骤4;6.若 $i \geq m \| \ j \geq n$ ，则跳出循环；7.若 $j = n$ ,则字符串 A为字符串 S 的简称，end.8.若 $j \neq n$ ，则字符串 A不为字符串 S 的简称，end.

以字符串“上海交通大学”，待判断字符串“交大”为例，可以得到 $\mathrm { \sf S } =$ （上海交通大学)， $\mathbf { A } { = }$ (交大)，开始 $S _ { 1 } \not = A _ { 1 }$ ,S下标向右移动一个单位，继续比对直到 $S _ { 3 } = A _ { 1 }$ ，此时 S和A下标同时向右移动一个单位， $S _ { 4 } \not = A _ { 2 }$ ,S 下标向右移动一个单位，继续比对直到 ${ \cal S } _ { 5 } = { \cal A } _ { 2 }$ ，此时A的下标等于 length(A)，算法结束,则“交大”为“上海交通大学”的简称。

# 3.3 词的拆分模式

# 3.3.1汉字拆分

根据汉字的构成单位可把汉字分为独体字、合体字两类。独体字（日、月等）由笔画构成，合体字（休、取等）则由偏旁构成。现代汉字的拆分，要充分认识汉字的组成规律，要根据符合中国人书写习惯的规则来拆分。汉字的空间上的关系有：相交、相离、相接[17]。汉字的方位上的关系有：上下、左右，内外、框架、独体。

为了使每个汉字有一个全国统一的代码，我国颁布了汉字编码的国家标准：《信息交换用汉字编码字符集》[18]。区位码是一个四位的十进制数，每个区位码都对应着一个唯一的汉字或符号[19]。根据以上汉字特征对敏感词列表中的汉字进行人工拆分并采用区位码进行编码形成汉字拆分表。如表5所示。

表5汉字拆分表  

<html><body><table><tr><td>汉字</td><td>区位码</td><td>拆分</td><td>区位码</td></tr><tr><td>法</td><td>2308</td><td>去</td><td>6763 4005</td></tr><tr><td>秃</td><td>4526</td><td>禾几</td><td>2644 2824</td></tr><tr><td>国</td><td>2590</td><td>□玉</td><td>3158 5181</td></tr></table></body></html>

# 3.3.2基于KMP的敏感词拆分识别算法

为了识别出敏感词拆分的变形体，本文提出了基于KMP的汉字拆分识别算法（以下简称为WS-KMP（Word SplitKMP）算法)，首先根据汉字拆分表把敏感词S与疑似敏感词变形体A进行拆分并转换成相应的区位码，然后采用模式匹配KMP算法进行匹配。算法具体的执行过程如算法3所示。算法3.WS-KMP algorithm输入：敏感词S，疑似敏感词变形体A输出：A是否为包含于S的拆分变形体1.按照汉字拆分表将字符串S和待判断字符串A进行拆分，得到其区位码 ${ \cal S } = (  { \mathbf { s } } _ { 1 }  { \mathbf { s } } _ { 2 } \cdots  { \mathbf { s } } _ { m } )$ 和 $A = ( \mathbf { a } _ { 1 } a _ { 2 } \cdots a _ { n } )$ ；（ $\mathrm { 2 } . m = l e n g t h ( { \mathrm S } ) \ , n = l e n g t h ( \mathrm { A } ) \ ;$ （2043.若 $m > n$ ，匹配不成功，end.4.若 $m \leq n$ ，则 ${ \cal S } = (  { \mathbf { s } } _ { 1 }  { \mathbf { s } } _ { 2 } \cdots  { \mathbf { s } } _ { m } )$ 为目标串， $A = ( \mathbf { a } _ { 1 } a _ { 2 } \cdots a _ { n } )$ 为模式串，采用KMP算法进行匹配；5.若存在 $\mathbf { s } _ { 1 } \mathbf { s } _ { 2 } \cdots \mathbf { s } _ { m } = a _ { i } a _ { i + 1 } \ldots a _ { m + i - 1 }$ ,匹配成功，end.6.若不存在 $\mathbf { s } _ { 1 } \mathbf { s } _ { 2 } \cdots \mathbf { s } _ { m } = a _ { i } a _ { i + 1 } \ldots a _ { m + i - 1 }$ ，匹配失败，end.

以敏感词“海洛因吗啡”和疑似敏感词“口马口非”为例，首先将两个词进行拆分，结果为“氵每氵各口大口马口非”和“口马口非”，获取相应的区位码 $\mathrm { \sf S } =$ （6763353167632487315820833158347731582339）， $\mathbf { A } { = }$ （3158347731582339)，采用模式匹配KMP算法进行匹配。首先 $S _ { 1 } \not = A _ { 1 }$ ，S 下标每次向右移动一位继续比对直到 $S _ { 4 } = A _ { 1 }$ ，然后S与A下标同时向右移动一位 ${ \cal S } _ { 5 } \not = { \cal A } _ { 2 }$ ，根据 $\begin{array} { r } { N e x t { \mathrm { ( j ) } } } \end{array}$ 函数确定每次A的下标，直到 $s _ { 2 5 } s _ { 2 6 } \cdots s _ { 4 0 } = a _ { 1 } a _ { 2 } \cdots a _ { 1 6 }$ ，则匹配成功，所以A是包含于S的拆分变形体。

# 4 实验与分析

本实验在具有2.4GHzInter(RCoreTMi5处理器8GB内存的机器上运行，操作系统为windows10，编程语言为Java。

# 4.1数据集

为了评估面向中文敏感词变形体的识别方法的效果,从搜狗实验室(http://www.sogou.com/labs/)的 SogouCA(版本：2012)全网新闻数据库中随机抽取了含有疑似敏感词的800 篇新闻文本(包含科技、体育、金融、社会、娱乐等题材)作为测试数据集。对数据集中的敏感词及其变形体进行人工的识别和分类，共发现67个敏感词及其变形体400个，涵盖了词的拼音、词的简称、词的拆分三种变形体情况，并将识别出的敏感词存入敏感词表中。在实验中，首先对以上67个敏感词进行人工拆分，再将敏感词变形体的数据集随机分成5组进行测试，第一组为80个，第二组为160个，第三组为240个，第四组为320个，第五组为400个。数据集中所抽取的敏感词变形体的部分举例如表6所示。

表6敏感词及其变形体举例  

<html><body><table><tr><td rowspan="2">敏感词</td><td colspan="3">变形体</td></tr><tr><td>词的拼音</td><td>词的简称</td><td>字的拆分</td></tr><tr><td>法轮功</td><td>falungong</td><td>flg</td><td>氵去车仑工力</td></tr><tr><td>兴奋剂</td><td> xingfenji</td><td>xfj</td><td>兴大田齐』</td></tr><tr><td>贩卖毒品</td><td>fanmaidupin</td><td>贩毒 fmdp</td><td>贝反卖毒口口口</td></tr><tr><td>袭警</td><td>xijing</td><td>xj</td><td>龙衣敬言</td></tr></table></body></html>

# 4.2实验分析

在实验中，通过算法的准确率、查全率和运行时间三个方面来验证敏感词变形体识别算法的有效性。设词的拼音模式中$\theta$ 为 $91 \%$ ，将识别结果分为四种情况：识别为真，实际为真（TP)；识别为假，实际为假（TN)；识别为真，实际为假（FP)；识别为假，实际为真（FN)。其中，查全率 $scriptstyle = \mathrm { T P } /$ ( $\mathrm { T P + F P }$ )，准确率$scriptstyle = \mathrm { T P } /$ （ $\mathrm { T P + F N } .$ )。实验结果如表7所示。

表7实验结果  

<html><body><table><tr><td colspan="6">基于变形体的中文字符串识别算法</td></tr><tr><td>数据集大</td><td></td><td></td><td></td><td></td><td>运行时间 准确率</td></tr><tr><td>小</td><td>TP</td><td>FP</td><td>FN</td><td>查全率</td><td>(s）</td></tr><tr><td>80</td><td>71</td><td>6</td><td>9 88.75%</td><td>92.22%</td><td>0.95</td></tr><tr><td>160</td><td>135</td><td>11</td><td>25 84.38%</td><td>92.47%</td><td>1.11</td></tr><tr><td>240</td><td>211</td><td>19</td><td>29</td><td>87.91% 91.73%</td><td>1.87</td></tr><tr><td>320</td><td>285</td><td>21</td><td>35</td><td>89.06% 93.13%</td><td>2.53</td></tr><tr><td>400</td><td>357</td><td>24</td><td>43</td><td>89.25%</td><td>93.70% 3.46</td></tr></table></body></html>

通过上述实验结果可以计算出基于变形体的中文字符串识别算法的平均查全率和准确率分别为 $8 7 . 8 7 \%$ 、 $9 2 . 6 5 \%$ ，在查全率方面，五组数据集中最低查全率为 $8 4 . 3 8 \%$ ，导致该组结果偏低的原因可能是由于被识别的敏感词及其变形体实际情况比较复杂，本文所提出的识别规则还需进一步的改进和优化；随着数据量的增加查全率基本稳定在 $89 \%$ ；在准确率方面五组数据集均高于 $91 \%$ ，且最高准确率接近 $94 \%$ ；在运行时间方面，随着数据量的增加，运行时间也有相应的增加。综上所述，本文所提出算法在实验中均已得到了较为理想的效果。

# 4.3实验结论

通过对不同的数据集进行实验，根据上述实验结果可以发现：本文提出的算法在查全率、准确率和运行时间的指标上均有较稳定的体现，证明了所提出算法的可行性和有效性。

# 5 结束语

本文所提出的方法能够根据词的拼音、词的简称和词的拆分三种中文字符的变形体识别出其相关的敏感词，辅助提高了审查的准确率和效率。实验证明本文所提出的方法可较为准确的识别出中文字符串的各种变形形式，有效提高敏感词审查的准确度，其效果也更接近于人脑识别的结果。但是词的拆分需要人工进行操作，当敏感词较多的时候，工作量会比较大，所以汉字的自动拆分是非常重要的，这也是下一步的工作。

# 参考文献：

[1]李扬，潘泉，杨涛．基于短文本情感分析的敏感信息识别[J].西安交 通大学学报,2016,50(9):80-84.   
[2]叶蕾，邹国奇，肖健．模糊遗传算法在敏感词分类优化中的应用[J]. 计算机应用研究,2012,29(7):2549-255.   
[3] 薛朋强，努尔布力，吾守尔·斯拉木．基于网络文本信息的敏感信息过 滤算法[J].计算机工程与设计,2016,37(9):2447-2452.   
[4]Yoon Taijin,Park Sunyoung, Cho HG.A smart filtering system for newly coined profanities by using approximate string alignment [C]/ Proc of IEEE International Conference on Computer & InformationTechnology.2010: 643-650.   
[5]Sood S 0,Antin J, ChurchillEF. Using crowdsourcing to improve profanity detection [J]// Proc of AAAI Spring Symposium Series.2012: 69-74.   
[6]Ghauth K I, Sukhur M S.Text censoring system for filtering malicious content using approximate string matching and Bayesian filtering $[ \mathrm { C } ] / \AA$ Computational Intelligence in Information Systems. Springer International Publishing,2015: 331: 149-158   
[7]李少卿，吴承荣，曾剑平，等．不良文本变体关键词识别的词汇串相似 度计算[J].计算机应用与软件,2015(3):151-157.   
[8]Levenshtein VI. Binary codes capable of correcting deletions,insertions and reversals [J].SovietPhysics Doklady,1966,10(1): 707-710.   
[9]Liu Baoyan,Lin Hongfei, Zhao Jing. Chinese sentence similarity computing based on improved edit-distance and dependency grammar [J]. Computer Applications & Software,2008.   
[10]李圣文，凌微，龚君芳，等．一种基于熵的文本相似性计算方法[J]. 计算机应用研究,2016,33(3):665-668.   
[11] Knuth D,Morris J,Pratt V.Fast pattern matching in strings [J]. SIAM Journal on Computing,1977,6(2):323-350.   
[12] Chang Jingshin,Teng Weilun. Mining atomic Chinese abbreviation pairs: a probabilistic model for single character word recovery [J].Language Resources and Evaluation, 2007,40 (3//4): 367-374   
[13]李钝，曹元大，万月亮．信息安全中的变形关键词的识别[J].计算机 工程,2007,33 (21): 55-156.   
[14]中国文字改革委员会.汉语拼音方案[S].中国：中国文字改革委员会， 1967   
[15] Zobel J,Dart P.Phonetic string matching:Lessons from information retrieval[C]//Proc ofthe 19th Annual International ACM SIGIR Conference on Research and Development in Information Retrieval.1996:166-172   
[16]船志平构造缩略语的方法和原则[] 语言教学与研究1999(2):73-

[17]朱文轩.Blog文本内容敏感信息的自动提取技术[D].上海：上海交通大学,2008

[18]中国国家标准总局.信息交换用汉字编码字符集[S].中国：中国国家

标准总局,1980[19]杨超，谢剑刚．基于区位码字典对数控程序进行中文注释[J].中国科技信息,2015 (17):65-66