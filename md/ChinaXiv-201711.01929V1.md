# 基于CRFs和词典信息的中古汉语自动分词

王晓玉 李斌

(南京师范大学文学院 南京 210097)

摘要：【目的】验证中古时期分词一致性和语料类别对CRFs分词效率的影响，在此基础上进一步提高分词效率，降低人工校对的工作量。【方法】以中古时期的史书、佛经、小说类语料为例，针对中古汉语的自动分词问题，优化分词原则，运用CRFs 模型和词典相结合的方法，消除中古汉语人工分词结果中易出现的分词不一致问题；同时在CRFs分词中引入字符分类、字典信息两种特征，并通过对比实验选取每种特征最合适的分词模板。【结果】实验结果显示，分词结果的总F值在封闭测试中达到 $9 9 \%$ 以上，开放测试的综合测试中也达到$89 \% - 9 5 \%$ 。【局限】分词不一致研究主要针对双字词，因此三字以上词语(多字词)的识别效果稍有欠缺。【结论】在有效提高分词一致性的前提下，字符分类、词典标记特征能够有效提高中古汉语CRFs 分词的精确度。同时本文提出的中古汉语分词系统可以服务于中古时期多类别的汉语语料。

关键词:CRFs 模型分词一致性中古汉语自动分词分类号：TP391

# 1引言

众所周知，汉语中词与短语之间的界限往往难以划分清楚，这一现象在中古汉语中更为突出。在汉语史上，中古是指东汉末年至隋朝这段时期，此时期汉语正处于质变期，由于汉语中的词汇在上古时期以单字词为主，在近代时期以双字词为主，而中古时期汉语正处于由单字词为主向双字词为主转变的过渡期，该过渡期中存在大量状态介于词和短语之间的字组,这些字组的情况各不相同，有的字组正处于词汇化的进程中，有的则是由多个汉字临时组合起来作为词使用。正是这些字组的存在，使得中古时期词和短语的边界更加不明确。在构建中古语料库的分词阶段，由于各人语感不同，再加上这些字组发生词汇化的时期、在具体文献中的词汇化程度难以完全量化，这必然会造成中古汉语分词上的困难，不仅直接导致了人工分词结果中出现的分词不一致现象，在以人工分词结果为训练语料的前提下，也严重制约着机器分词准确率和一致性的提高。而分词在汉语语料库建设中是一项基础性工作，它对后续标注、语义分析等起着至关重要的作用。

中古时期的汉语语料相比现代来说不算多，但其规模也在数亿字以上，包含大量史书、佛经及民间文学、杂著类语料[1]。用计算机处理中古语料时不可避免地要进行中古汉语分词。然而，目前与古代汉语信息处理相关的研究成果本就不多，与中古汉语相关的分词研究更加少见。王嘉灵[2基于《汉书》进行自动分词研究，制定了《汉书》分词规范，并在加入字符分类、上古音韵特征的基础上，用CRFs模型进行分词实验，实验结果的F值达到 $9 4 . 4 \%$ ，但该研究仅以《汉书》为自动分词的实验语料，一本书难以代表中古时期的语料全貌，再加上中古时期语料类别有很多，各类别语料间差异比较大，不仅史书、佛经、杂著等类别间存在差异，各类别内部，如佛经语料内部的译经和僧传间也存在词汇上的差异，这也使得该研究成果的可扩展性大大降低。王晓玉等[从中古时期具有代表性的语料中抽样选取28万余字作为实验对象，统计这些语料人工分词结果中出现的切分错误、分词不一致、组合型歧义字串的数目及比例，着重研究分词不一致字串产生的原因和分类，并提出解决方案的设想，该研究覆盖了中古时期的佛经、史书、小说类语料，不仅呈现了中古汉语人工分词的大体概貌，并找出分词中具体存在的问题，为进一步研究奠定了基础。

在以上研究的基础上，本文从理论和实践两个层面来解决中古语料分词中出现的问题：首先针对中古汉语中易发生分词不一致的字串，制定并优化分词规范，基于此分词规范校准人工分词语料，尽可能减少人工分词中出现的切分错误和分词不一致情况；然后将整理后的语料作为CRFs训练语料，引人字符分类、词典标记两种特征，对两个特征分别设置多个特征模板，并进行对比实验，挑选其中分词效果最好的特征及模板；最后，基于已选定的特征及模板，设置两组分词对比实验，分别验证语料类别和分词一致性对中古汉语CRFs分词结果的影响。该实验结果可直接服务于中古汉语语料库的建设。

# 2分词说明及实验语料

# 2.1 分词原则

汉语中词与短语的界限往往难以划分清楚，但这并不妨碍人们对语言的理解。同样，在分词时也不必纠结于语言学领域中词与短语的划界，只要在保证系统适用性、语言单位颗粒度合适的情况下，计算机可以正确理解处理语言单位即可。这一理念在词典收词中亦有所体现，即在保证语义理解正确的前提下，并不强行区分词和短语。因此，绝大部分词典所收录词条的范围不仅仅包括词，也包括一些使用稳固的短语、习用语等。也正是基于此，自然语言处理领域中引入分词单位这一概念，用来指代自然语言处理中使用的、具有确定语义和语法功能的基本单位[4]。中古汉语的词汇单位中存在许多介于词和短语之间的字组，在中古汉语语料库构建过程中，这些字组成为产生分词不一致问题的根源之一，严重影响着语料库的构建质量，理清这些字组的分词边界是提高中古汉语

语料库构建质量的关键。

“中古汉语词库"[1(简称为"词库")是中古汉语语料库项目的重要成果之一，它主要涵盖了以下几本词典所收录的词条及义项：《汉语大词典》[5]、《魏晋南北朝词语例释》[6]、《中古虚词语法例释》[7]、《佛学大辞典》[8]、《佛经词语汇释》[9]。它收录了中古时期出现的绝大部分词语，收录总条目超过54万条。基于该“词库”，本文在识别分词界限不清的字组类分词单位时，由于存在词汇化时间、程度模糊难以确定的情况，为了综合照顾到分词单位的统一性、可参照性及语义完整性，总体上遵照以下三个原则:

(1）从宽原则，在不影响语义理解的情况下，对介于词和短语之间的字组，主张从合不从分。(2）词典原则，也即黄居仁所说的分词的信级[10],规定凡收录在"词库"中的语义单位，一律从合。(3）词义透明原则，本文规定，词义不透明包括以下4种情况：通过隐喻或转喻方式产生新义；意义发生转指；组成成分的意义有脱落现象；词性发生转变。凡满足词义不透明任一种情况的，一律从合。

基于以上三个原则对人工分词过程进行优化，得到的分词结果作为CRFs自动分词模型的训练语料。然而，由于训练语料是多人人工分词的结果，以上三个原则也不能完全避免分词不一致现象[3的产生。因此，本文对训练语料单独进行整理，尽量消除其中存在的分词不一致现象，并设置对比实验，将分词不一致整理前和整理后的语料分别作为训练语料，验证分词不一致对自动分词结果的影响。

# 2.2 实验语料说明

中古时期流传下来数量最多的文献种类为史书类和佛经类，除此之外，也有较少量民间文学(如小说)、杂著(如农书)等类别的文献。因此，本文主要选取史书、佛经两类语料作为实验语料，为使实验更具代表性，也加入少量小说类语料。分类抽取中古时期的文献语料作为实验语料，结果如表1所示。

表1中语料均已初步完成人工分词及标注。按照2.1节的分词原则，校对表1中语料的分词结果，尽量减少其中存在的分词不一致现象，这样就产生了分词一致性整理前后两批语料，将测试语料校对后的结果作为标准分词结果。对下文三个实验语料，分别说明如下。

表1语料情况说明表  

<html><body><table><tr><td rowspan="2">语料类别</td><td colspan="3">训练语料</td><td colspan="3">测试语料</td></tr><tr><td>语料来源</td><td>字数</td><td>总字数</td><td>语料来源</td><td>字数</td><td>总字数</td></tr><tr><td rowspan="3"></td><td>后汉书(卷1、34、74；卷2、75、38未完)</td><td>70 344</td><td></td><td>北齐书(卷1-4，开放测试)</td><td>27189</td><td></td></tr><tr><td>史书类 三国志(魏书卷1-3；卷4未完；吴书卷46、卷49)</td><td>62 093</td><td>145 292</td><td>三国志(魏书卷1-2，封闭测试)</td><td>17 790</td><td>44 979</td></tr><tr><td>陈书(卷1-16；卷 27-36)</td><td>12 855</td><td></td><td></td><td></td><td></td></tr><tr><td rowspan="2">佛经类 小说类</td><td>撰集百缘经 杂譬喻经二种</td><td>80588</td><td>99 157</td><td>百喻经(开放测试) 杂譬喻经-失译(封闭测试)</td><td>21 552</td><td>35209</td></tr><tr><td></td><td>18 569 36 718</td><td>36 718</td><td></td><td>13 657</td><td></td></tr><tr><td>总计</td><td>幽明录 281 167</td><td></td><td></td><td>80 188</td><td></td><td></td></tr></table></body></html>

(注："未完"表示实验时，《后汉书》卷38仅有部分完成了人工标注，但并不影响将已完成部分作为实验语料。下"卷4未完"同。）

(1）在选定特征模板实验环节，训练语料直接使用表1中所有训练语料的人工分词结果，从4本测试语料中各选取一千字，合起来作为总测试语料;

(2）在分词一致性对分词结果影响的对比实验中，分别将分词不一致现象消除前后的语料作为训练语料，测试语料同表1;

(3）在语料混杂度对分词结果影响的对比实验中，分别将史书、佛经、全部语料作为训练语料，测试语料同表1。

# 3模型及特征模板选取

基于统计的分词问题可视为文本序列的分类问题，其核心是在字组中区分出词的起始、中间和结束位置。在给定观察序列的条件下，分词模型可以统计出整个标注序列的单一联合概率分布[12]，并据此计算或预测出最可能的输出序列。与常用的几个主流模型相比，如：隐马尔科夫模型(HMM)、最大熵马尔科夫模型(MEMM)和条件随机场模型(CRFs)，其中 CRFs具有较为突出的性能，它不仅克服了HMM强独立性假设的局限，而且解决了MEMM 标记偏置问题[13]。因此，本文选择CRFs作为实验模型，在此基础上添加不同特征及特征模板，选择其中实验效果最好的特征模板，以提高分词效率。

# 3.1 特征选取

将CRFs模型应用于分词中，其核心思想是充分挖掘训练语料(输入序列)中构词所用汉字的位置知识[14],也即特征。特征是CRFs分词的核心，特征选取情况将对分词结果的准确率产生直接影响。但选取的特征并不是越多越好，选取的特征越多，CRFs模型提取特征或分词时所需要搜索的数据也越多，这不仅对机器性能是严峻考验，也容易使分词结果的准确性受到过度冗余数据的干扰。基于此，本文选取字符分类和词典标记作为CRFs分词特征，分别说明如下：

(1）字符分类。字符分类是对语料中字符的粗分类，这种粗分类无论在现代汉语[15]还是古代汉语[16]中，都能对分词结果准确率的提高起到较为明显的作用。本文所用字符类别标注集为： ${ \mathrm { T 1 } } { = } \{ \  { \mathrm { H Z } }$ ，Punc,SenPunc,CNum,CCNum,D,X}。对应关系为：汉字(HZ)、普通标点(Punc)、句末标点(SenPunc)、数字(CNum)、干支(CCNum)、“第"字(D)、未识别字符(X)。

由于古代汉语中数字用文字表示，且不可能完全枚举，也就不可能完全依靠统计方法实现自动分词，而数字的表示又有很强的规律性：多位数字由个位数字组合而成，个位数字又是封闭的小类，因此特别对数字、干支(与数字情况相类似)设置了字符类别。而且中古文献使用的为繁体字，也存在异体字、疑难字等，“未识别字符"统一用来表示程序未能识别出来的文字。字符分类及词典标记采用程序自动标记法。

(2）词典标记。本文词典标记是动态标记语料中汉字在词典中组词情况的信息。由于CRFs分词模型是基于统计学的模型，它主要依赖词频、上下文构词信息来识别分词单位的界限，其缺点是难以发现语料中频率较低的词，且对语料类别有较强依赖性。要克服这些缺点，有以下两种方法：

$\textcircled{1}$ 分词时结合规则、词典等信息。由字组词过程中，可供分词使用的字规则十分有限，而词典是能用于自动分词的不可忽视的资源，黄昌宁等[I1]主张在语料库标注过程中严格执行"词表驱动"原则，在没有歧义的情况下，词表词应当作为一个完整的切分单位，以保证分词结果的一致性。“统计 $+$ 词典"的方法不仅能有效利用统计类分词模型便于通过上下文排除歧义、发现新词等优点，也合理运用了已有的语言资源，一定程度上降低了完全基于统计方法需要大规模训练语料的要求，能很好提高自动分词的准确率和效率。

$\textcircled{2}$ 使用足够多同一类型的训练语料。统计学习方法在分词评测中效果更好[II]，但它需要大量同类型的训练语料，再加上未登录词、组合型歧义的存在，使得统计模型在现代汉语分词结果中的正确率局限于0.85 左右[17]。而中古语料数量相对较少，语料类型也不统一，再加上分词规范等资源的缺失，采用该种方法，中古汉语CRFs分词的正确率只会更低。

基于以上分析，本文在分词时引入词典动态标记语料，将"词库"作为词典标记的依据，引入词典标记标注集为: $\mathrm { T } 2 = \{ \mathrm { B , M , E , S , W , T , H , F } \}$ 。标注集中字符含义分别为：词首字(B)、词中字(M)、词尾字(E)、单字(S)、标点(W)、属于两个词的字(T)、属于三个词的字 $\mathrm { ( H ) }$ 、属于三个词以上的字(F)。

以《百喻经》首句语言片断"闻如是：一时佛住王舍城,"为例，动态标记词典信息的具体流程为：将该语言片断作任意切分，来匹配"词库"收录的词目，除了单字词外，可以匹配到"闻如是、如是、一时、王舍、王舍城"这5个词，依据匹配情况可以将语句片断中的汉字分类如下：

(1)“闻、一"两字分别仅出现在"闻如是、一时"的词首位置，因此"闻、一"两字标记为"B”。(2)"如、是"两字出现在"闻如是、如是"两个词中,“王、舍"两字出现在"王舍、王舍城"两个词中，因此“如、是、王、舍"四字标记为"T”

(3)"时、城"两字分别出现在"一时、王舍城"的词尾位置，因此"时、城"两字标记为"E”。

(4)“佛、住"两字均在词典中匹配为单字词，故标记为"S”。

此外，标点符号统一标记为"W”。最终，基于"字符分类”、“词典标记”，并将校对后人工分词结果作为标准答案，得到用于CRFs实验的语料标准形式如表2所示。

表2CRFs语料标记示例  

<html><body><table><tr><td>字符</td><td>字符类别</td><td>词典标记</td><td>标准答案</td></tr><tr><td>闻</td><td>HZ</td><td>B</td><td>S</td></tr><tr><td>如</td><td>HZ</td><td>T</td><td>B</td></tr><tr><td>是</td><td>HZ</td><td>T</td><td>E</td></tr><tr><td>：</td><td>Punc</td><td>W</td><td>W</td></tr><tr><td>一</td><td>CNum</td><td>B</td><td>B</td></tr><tr><td>时</td><td>HZ</td><td>E</td><td>E</td></tr><tr><td>佛</td><td>HZ</td><td>S</td><td>S</td></tr><tr><td>住</td><td>HZ</td><td>S</td><td>S</td></tr><tr><td>王</td><td>HZ</td><td>T</td><td>B</td></tr><tr><td>舍</td><td>HZ</td><td>T</td><td>M</td></tr><tr><td>城</td><td>HZ</td><td>E</td><td>E</td></tr><tr><td>，</td><td>SenPunc</td><td>W</td><td>W</td></tr></table></body></html>

# 3.2 特征模板对比实验

在CRFs分词模型中，特征模板是运用特征提取词语边界信息的有效工具。特征模板的设定直接决定能否高效提取到有用的分词信息，对分词结果的好坏也有直接影响。在训练、测试语料中先后加人字符分类、词典标记作为分词特征，并对这两种特征分别选取不同的特征模板，对比不同分词模板作用下训练语料的分词结果，实验结果如表3所示。

表3加入字符分类、词典标记特征后分词对比  

<html><body><table><tr><td rowspan="2">特征 统计结果</td><td colspan="4">仅字面信息</td><td colspan="4">字面(1W+2C)+字符分类</td><td colspan="4">字面(1W+2C)+词典</td><td rowspan="2">Template-all</td></tr><tr><td>1W</td><td>2W</td><td>1W+2C</td><td>2W+2C</td><td>0W</td><td>1W</td><td>2C</td><td>1W+2C</td><td>0W</td><td>1W</td><td>2C</td><td>1W+2C</td></tr><tr><td>单字词数</td><td>1710</td><td>568</td><td>1918</td><td>648</td><td>1300</td><td>1403</td><td>1814</td><td>1384</td><td>1532</td><td>1597</td><td>1866</td><td>1790</td><td>1747</td></tr><tr><td>双字词数</td><td>970</td><td>1541</td><td>866</td><td>1501</td><td>1094</td><td>1042</td><td>819</td><td>1 045</td><td>923</td><td>906</td><td>803</td><td>837</td><td>833</td></tr><tr><td>多字词数</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>4</td><td>4</td><td>16</td><td>16</td><td>20</td><td>20</td><td>22</td></tr><tr><td>正确分词数</td><td>1127</td><td>849</td><td>1 223</td><td>885</td><td>1120</td><td>1135</td><td>1354</td><td>1 147</td><td>1910</td><td>1975</td><td>2 033</td><td>2 164</td><td>2 229</td></tr><tr><td>总 P(%)</td><td>42.05%</td><td>40.26%</td><td>43.93%</td><td>41.18%</td><td>46.78%</td><td>46.42%</td><td>51.35%</td><td>47.14%</td><td>77.30%</td><td>78.40%</td><td>75.60%</td><td>81.75%</td><td>85.66%</td></tr><tr><td>总R(%)</td><td>43.02%</td><td>32.40%</td><td>46.68%</td><td>33.78%</td><td>42.75%</td><td>43.32%</td><td>51.68%</td><td>43.78%</td><td>72.90%</td><td>75.38%</td><td>77.60%</td><td>82.60%</td><td>85.08%</td></tr><tr><td>总F(%)</td><td>42.53%</td><td>35.91%</td><td>45.26%</td><td>37.11%</td><td>44.67%</td><td>44.82%</td><td>51.51%</td><td>45.40%</td><td>75.03%</td><td>76.86%</td><td>76.59%</td><td>82.17%</td><td>85.37%</td></tr><tr><td>双字词正确数</td><td>361</td><td>535</td><td>334</td><td>522</td><td>446</td><td>414</td><td>347</td><td>423</td><td>592</td><td>640</td><td>620</td><td>634</td><td>662</td></tr><tr><td>双字词P(%)</td><td>37.22%</td><td>34.72%</td><td>38.57%</td><td>34.78%</td><td>40.77%</td><td>39.73%</td><td>42.37%</td><td>40.48%</td><td>64.14%</td><td>70.64%</td><td>77.21%</td><td>75.75%</td><td>79.47%</td></tr><tr><td>双字词R(%)</td><td>47.81%</td><td>70.86%</td><td>44.24%</td><td>69.14%</td><td>59.07%</td><td>54.83%</td><td>45.96%</td><td>56.03%</td><td>78.41%</td><td>84.77%</td><td>82.12%</td><td>83.97%</td><td>87.68%</td></tr><tr><td>双字词F(%)</td><td>41.86%</td><td>46.60%</td><td>41.21%</td><td>46.28%</td><td>48.24%</td><td>46.08%</td><td>44.09%</td><td>47.00%</td><td>70.56%</td><td>77.06%</td><td>79.59%</td><td>79.65%</td><td>83.38%</td></tr></table></body></html>

(注：这里的W表示单字,C为共现字，数字表示个数，例如0W表示该特征的当前字, $1 \mathsf { W } + 2 \mathsf { C }$ 表示相邻字符窗口为 $\pm 1$ 、二字共现；列名中 $\mathrm { ~ \bf ~ P ~ }$ 表示正确率,R表示召回率,F表示F值。)

从表3可以看出，仅从字面信息提取分词特征时，分词结果中双字词的F值与总F值之间呈现出负相关关系。当模板为 $1 \mathrm { W } + 2 \mathrm { C }$ 时分词结果总F值最高，此时双字词F值虽然最低，但双字词P和总P、双字词R和总R间比例稳定，其他模板均切分出过多的双字词，同时提高了双字词的错误率和召回率，因此 $1 \mathrm { W } + 2 \mathrm { C }$ 为字面信息分词效果最好的模板。

字符分类信息能有效地将汉字、标点、数字信息区分开来，因此也就对数字、天干地支等同类别汉字组成的分词单位分词效果尤为明显。加入该特征后，总F值提高了约 $6 \%$ ，双字词的F值也有所提高，当分词模板为2C和 $1 \mathrm { W } + 2 \mathrm { C }$ 时，还正确切分出了三字及以上的数词。从表3可以看出，字符分类信息总体分词效果最好的模板为2C。

词典是收录词语的权威工具，加人词典标记特征后，分词结果的F值得到大幅提升，并且双字词的 F值与总F值间的关系变为正相关，分词效果最好的词典标记模板显然为 $1 \mathrm { W } + 2 \mathrm { C }$ ，在该模板的作用下，分词结果的总F值比仅为字面信息时提高了 $3 9 . 9 1 \%$ 。

综上所述，如表3中粗体所示，分别选取：字面信息、词典标记特征模板为 $1 \mathrm { W } + 2 \mathrm { C }$ ，也即相邻字符窗口为 $\pm 1$ 、二字共现；字符分类特征模板为2C，也即二字共现。选取该模板作为实验的总特征模板，表示如下。

Template-a $\begin{array} { r } { \mathrm { 1 l } = ( 2 \mathrm { C } ) _ { \mp \mathrm { f i f f } \sharp \sharp \sharp } + ( \mathrm { 1 W } + 2 \mathrm { C } ) _ { \mp \sharp \sharp \wedge \sharp \sharp \sharp } + ( \mathrm { 1 W } + 2 \mathrm { C } ) _ { \sharp \sharp \sharp \sharp \wedge \sharp } } \end{array}$

# 4实验设计与评价标准

# 4.1 实验设计

从理论上来说，CRFs分词模型中，所选取的实验语料类别越统一，越利于提取到有规律的分词信息。而中古时期的史书、佛经等语料间存在较大语言、词汇方面的差异，语料类别必然也会对CRFs分词结果产生一定影响。因此设置以下两组对照实验:

实验1分词一致性影响：对人工分词结果进行一致性整理，分别选取分词一致性整理前后的语料作为训练语料，以考察训练语料分词一致性对CRFs分词结果的影响。

实验2语料混杂度影响：选取分词一致性整理后的语料，分别将史书、佛经单独分词结果与综合起来的分词结果作为训练语料，以考察语料类别混杂度对

CRFs分词结果的影响。

# 4.2 评价标准

以校对后的人工分词结果为衡量标准，以准确率、召回率、F值为评价指标。准确率(Precision，简写为P)也叫查准率，本文中表示CRFs分词结果中的正确率；召回率(Recall，简写为 R)又叫查全率，本文中表示CRFs分词结果中正确分词数与标准分词结果的比率;F值是这两个指标的综合评价。三者的计算公式分别为：

$$
\mathrm { P } = \mathrm { R W } / \mathrm { A W }
$$

$$
\mathrm { R } = \mathrm { R W } / \mathrm { S W }
$$

$$
\mathrm { F } = \mathrm { P } { \times } \mathrm { R } { \times } 2 / \left( \mathrm { P } + \mathrm { R } \right)
$$

其中,RW表示CRFs分词结果中正确分词的词目，AW表示CRFs分词结果的总词数，SW表示人工分词结果中的总词数。

P、R的取值范围在0和1之间,F的取值范围在P和R之间，这三者数值越接近1，代表分词效果越好。P和R从不同方面评价了分词模型，F值则反映了两者的综合评价。

# 5 数据及分析

在CRFs工具中使用上文实验得出的模板Templateall，对训练语料进行训练，将训练得到的模型按照实验设计分别进行封闭测试和开放测试。

# 5.1 封闭测试

将训练语料进行分词一致性整理，分别用CRFs模型训练整理前后的训练语料，并对测试语料进行封闭测试，以验证分词一致性对CRFs自动分词结果的影响，实验结果如表4所示。

本实验中，F值是最重要的性能评价指标，因此在对比实验结果时，主要基于F值的变化情况来说明实验结果，如表4中粗体字部分，可以得出以下结论：

(1）对语料进行分词一致性整理后，可以通过上下文、字符分类、词典标记三个特征获取较为准确一致的分词边界信息，其词语的分合规律变得更加有迹可循，因此分词结果的总F值得到明显提升，其中史书类语料提升了 $1 5 . 7 0 \%$ ，佛经类语料提升了$12 . 3 8 \%$ 。

(2）分词单位的字数越多，分词一致性整理对其分词结果的影响越显著。经过一致性整理后，所有词、双字词、多字词，随着词字数的增加，分词结果的F值提升效果也越来越明显。这是因为产生分词不一致的均为双字词及多字词，而“词库"以双字词和多字词的收录为主，词典标记强化了双字词和多字词的特征提取。

表4分词一致性对CRFs分词结果影响(封闭测试)  

<html><body><table><tr><td rowspan="2">训练 语料</td><td rowspan="2">测试 语料</td><td colspan="12">分 词 结 果(CRFs分词结果的词数与 PRF 值)</td></tr><tr><td>单字 双字</td><td>多字</td><td></td><td>总P</td><td>总R</td><td>总F</td><td>F值 双字词</td><td></td><td>双字词</td><td>双字词</td><td>F值</td><td>多字词</td><td>多字词 多字词</td><td>F值</td></tr><tr><td>原语料</td><td></td><td>词</td><td>词</td><td>词</td><td>(%)</td><td>(%)</td><td>(%)</td><td>变化率 P(%)</td><td>R(%)</td><td></td><td>F(%)</td><td>变化率</td><td>P(%)</td><td>R(%) F(%)</td><td>变化率</td></tr><tr><td>一致后</td><td></td><td>史书7 764 3 263 7 058 3309</td><td>80</td><td>82.05%</td><td></td><td>85.62%</td><td>83.79% →</td><td></td><td>81.67% 80.86% 81.26%</td><td></td><td>→ 18.15%</td><td>70.00%</td><td></td><td>20.59% 31.82%</td><td>↑</td></tr><tr><td>原语料</td><td></td><td>5 333 2 690</td><td>270</td><td>99.53%</td><td>99.46%</td><td></td><td></td><td>99.50% 15.70% 99.21% 99.61% 9941%</td><td></td><td></td><td></td><td>98.89%</td><td></td><td></td><td>98.16% 98.52% 66.71%</td></tr><tr><td></td><td>佛经</td><td></td><td>70</td><td></td><td>88.08% 85.67%</td><td>86.86%</td><td>个</td><td></td><td>78.55% 89.95% 83.87%</td><td></td><td>→</td><td>50.00%</td><td></td><td>26.12% 34.31%</td><td>个</td></tr><tr><td>一致后</td><td></td><td>5823 2 355</td><td>136</td><td></td><td></td><td></td><td></td><td>99.28% 99.21% 99.24% 12.38% 99.07% 99.32% 99.19% 15.33%</td><td></td><td></td><td></td><td>91.91%</td><td></td><td></td><td>93.28% 92.59% 58.28%</td></tr></table></body></html>

(3）多字词的F值提升率高达 $58 \%$ 至 $67 \%$ ，远高于总F值和双字词F值的变化率，这是因为分词单位的字数越多，其在文献中出现的频率就越低，分词结果也就越容易受到分词不一致的干扰。

(4)分词一致性对佛经类语料影响稍弱于史书类 语料。这是由佛经语料的特异性造成的，佛经是翻译 过来的文献，语言变异现象较多，也更难提取到规律 性的分词边界信息。

选取分词一致性整理后的语料，分别将史书、佛经类语料与综合后的语料作为训练语料，来验证语料类别混杂度对CRFs分词结果的影响，实验结果如表5所示。

表5语料混杂度对CRFs分词结果影响(封闭测试)  

<html><body><table><tr><td>训练 测试</td><td></td><td colspan="16">分词结 果(CRFs分词结果的词数与PRF 值)</td></tr><tr><td>语料语料</td><td></td><td>单字 词</td><td>双字 词</td><td>多字 词</td><td>总P (%)</td><td>总R (%)</td><td>总F (%)</td><td>F值 变化率</td><td>双字词 P(%)</td><td>双字词 R(%)</td><td>双字词 F(%)</td><td></td><td>F值 变化率</td><td>多字词 P(%)</td><td>多字词 R(%)</td><td>多字词 F(%)</td><td>F值 变化率</td></tr><tr><td>史书</td><td></td><td></td><td>7 764 3 263</td><td>80</td><td></td><td></td><td>99.73% 99.71% 99.72%</td><td></td><td>←</td><td>99.61%</td><td>99.79%</td><td>99.70%</td><td>←</td><td>99.26%</td><td>98.90%</td><td>99.08%</td><td>←</td></tr><tr><td>综合</td><td>史书</td><td></td><td>7058 3309</td><td>270</td><td>99.53% 99.46%</td><td></td><td>99.50%</td><td>0.22%</td><td>99.21%</td><td>99.61%</td><td></td><td>99.41%</td><td>0.29%</td><td>98.89%</td><td>98.16%</td><td>98.52%</td><td>0.56%</td></tr><tr><td>佛经</td><td></td><td></td><td>5 333 2 690</td><td></td><td></td><td></td><td>7099.44% 99.45% 99.44%</td><td></td><td>99.53%</td><td></td><td>99.32%</td><td>99.42%</td><td></td><td>93.43%</td><td>95.52%</td><td>94.46%</td><td>←</td></tr><tr><td>综合</td><td>佛经</td><td></td><td>5 823 2 355</td><td>136</td><td>99.28% 99.21% 99.24%</td><td></td><td></td><td></td><td>0.20% 99.07%</td><td>99.32%</td><td></td><td>99.19%</td><td>0.23%</td><td>91.91%</td><td>93.28%</td><td>92.59%</td><td>1.87%</td></tr></table></body></html>

表5反映出，将不同类别语料混同起来用作训练语料时，分词结果F值总体呈下降趋势。具体而言，从表5可以看出：区分不同类别的语料(史书、佛经)后,总F值均提高了不到 $0 . 3 \%$ 。说明中古时期不同类别语料间虽然存在差异，这种差异对CRFs 分词结果也造成一定影响，但总体而言影响并不十分大，远远低于分词不一致对分词结果的影响。

# 5.2 开放测试

按照表1对语料进行开放测试，分别将分词一致性整理前后的人工分词语料作为训练语料，进一步验证开放测试中分词一致性对CRFs自动分词结果的影响，实验结果如表6所示。

表6分词一致性对CRFs分词结果影响(开放测试)  

<html><body><table><tr><td rowspan="2">训练 语料 语料</td><td rowspan="2">测试</td><td colspan="11">分词结 果(CRFs分词结果的词数与 PRF 值)</td><td colspan="4"></td></tr><tr><td>单字 词</td><td></td><td>双字 词</td><td>多字 总P 词</td><td>总R (%)</td><td>总F (%)</td><td>F值 变化率 P(%)</td><td>双字词 双字词双字词</td><td>R(%)</td><td>F(%)</td><td>F值 变化率</td><td>多字词 P(%)</td><td>多字词 R(%)</td><td>多字词 F(%)</td><td>F值 变化率</td></tr><tr><td>原语料</td><td></td><td>10 745</td><td>5520</td><td>230</td><td>(%)</td><td>80.24% 85.27% 82.67%</td><td></td><td>→</td><td>83.22% 84.51% 83.86%</td><td></td><td></td><td>→</td><td>62.17%</td><td>20.11%</td><td>30.39%</td><td>→</td></tr><tr><td>致后</td><td>史书</td><td>9 834</td><td>5503</td><td>513</td><td></td><td></td><td></td><td></td><td>88.73% 90.61% 89.66% 6.98% 89.71% 90.82% 90.26% 6.40%</td><td></td><td></td><td></td><td>71.73%</td><td>51.76%</td><td>60.13% 29.74%</td><td></td></tr><tr><td>原语料</td><td></td><td></td><td>8482 4203</td><td>76</td><td></td><td>92.30% 88.46% 90.34%</td><td></td><td>↑</td><td>81.51% 94.72% 87.62%</td><td></td><td></td><td>个</td><td>60.53%</td><td>52.87%</td><td>56.44%</td><td>→</td></tr><tr><td>致后</td><td>佛经</td><td></td><td>9 113 3875</td><td>84</td><td></td><td>95.35% 93.61% 94.47% 4.13% 89.91% 96.32% 93.01% 5.38% 65.48%</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>63.22%</td><td>64.33%</td><td>7.89%</td></tr></table></body></html>

表6中可得到的与封闭测试一致的结论不再赘言，与之不同的是：对训练语料进行一致性整理后，虽然没有封闭测试提升效果那么明显，但开放测试分词结果的总F值仍然得到明显提升，其中史书类语料提升了 $6 . 9 8 \%$ ，佛教类语料提升了$4 . 1 3 \%$ 。

选取分词一致性整理后的语料，分别将史书、佛经类语料与综合后的语料作为训练语料，以进一步验证开放测试中语料类别混杂度对CRFs分词结果的影响，实验结果如表7所示。

表7语料混杂度对CRFs分词结果影响(开放测试)  

<html><body><table><tr><td rowspan="2">训练测试</td><td colspan="16">分词结果(CRFs分词结果的词数与PRF 值)</td></tr><tr><td>语料语料单字</td><td>词</td><td>双字 词</td><td>多字 词</td><td>总P (%)</td><td>总R</td><td>总F F值 变化率</td><td>双字词</td><td>双字词</td><td></td><td></td><td>双字词 F值变化 多字词</td><td>多字词</td><td>多字词</td><td>F值变</td></tr><tr><td>史书</td><td></td><td>9 668 5562</td><td></td><td></td><td></td><td>(%) 526 88.61% 89.94% 89.27%</td><td>(%)</td><td>P(%) 88.76%</td><td>R(%) 90.82%</td><td>F(%) 89.78%</td><td>率</td><td>P(%) 68.82%</td><td>R(%) 50.91%</td><td>F(%) 58.53%</td><td>化率</td></tr><tr><td>综合</td><td>史书</td><td>98345503</td><td></td><td></td><td></td><td></td><td>→</td><td>513 88.73% 90.61% 89.66% 0.39% 89.71%</td><td>90.82%</td><td>90.26%</td><td>→ 0.48%</td><td>71.73%</td><td>51.76%</td><td>60.13%</td><td>→ 1.60%</td></tr><tr><td>佛经</td><td></td><td>9 085 3902</td><td></td><td></td><td></td><td>76 94.82% 93.02% 93.91%</td><td>个</td><td></td><td>89.06% 96.07%</td><td>92.43%</td><td>→</td><td>65.79%</td><td>57.47%</td><td>61.35%</td><td>→</td></tr><tr><td>综合</td><td>佛经</td><td>9 113 3 875</td><td></td><td></td><td></td><td></td><td></td><td>84 95.35% 93.61% 94.47% 0.56% 89.91% 96.32%</td><td></td><td>93.01%</td><td>0.57%</td><td>65.48%</td><td>63.22%</td><td>64.33%</td><td>2.98%</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

结合表5，从表7中可以得出以下两个结论：

(1）在不区分训练语料类别的情况下，开放测试中分词结果的F值有所上升。而封闭测试中，分词结果的F值却下降了，封闭实验和开放实验的结果呈相反趋势。

(2）与封闭测试相比，开放测试中总F值的变化较大且呈上升趋势，但无论上升还是下降，变化幅度均不超过 $1 \%$ ，与分词一致性对结果的影响相比，小得多且不稳定。

这两个结论说明，语料类别的差异会影响人们的语感，从而加剧分词不一致，因此对语料类别细分类会提高分词效果；在优化分词标准后，一定程度上消除了分词不一致现象，不同类别的语料间词汇差别并没有想象中那么大，对语料类别进行细分后，由于训练语料数量的减少，分词效果反而会打折扣。

综合以上实验，在CRFs分词中，按语料类别细分类对分词结果稍有贡献，但在语料总量有限，特别是各类别语料数量不均衡、数量不够大的情况下，由于细分语料就相当于减少了单个实验的训练语料，反而会降低分词效率。而分词是否一致是评测训练语料质量好坏的重要标准之一，在很大程度上影响着分词结果的整体质量。

# 6结语

本文针对中古这一特殊时期的多种语料，制定分词原则，优化了分词过程，然后通过人工校对，尽量减少语料中存在的分词不一致现象。引入字符分类及词典标记特征，通过CRFs对比实验选取分词效果最好的模板，实现词典与统计相结合的自动分词方法。

可以看出，字符分类、词典标记特征有效利用了汉字构词、已有的中古词库信息，加入字符分类和词典标记特征后，分词结果的总F值分别提高 $5 \%$ 和 $3 5 \%$ 以上，不仅节省了人力，也获得了更好的分词效果。本文实验证明：中古汉语分词一致性对自动分词结果的影响十分显著，对训练语料进行一致性整理后，封闭测试中分词结果的总F值均提高了 $10 \%$ 以上，开放测试中分词结果的总F值提高了 $3 \%$ 至 $7 \%$ ；区分不同语料对分词结果的影响较小，不足 $1 \%$ ，但由于中古语料数量有限，细分语料类别必然会造成单个实验训练语料的减少，反而可能会降低分词效率。因此在处理好分词一致性的前提下，中古汉语自动分词不必区分处理不同语料。

本文一致性规范的对象仅限于双字词，多字词的处理效果虽然提升显著，但在开放测试中仅有 $60 \%$ 左右，仍然不十分理想，在未来的工作中笔者将考虑:

(1）研究多字词的分词不一致情况，并制定相应的分词规范，进一步提高训练语料的分词一致性;(2)完善"词库”，增强其对中古语料中分词单位的覆盖面;(3）在词典标记特征中加入最长匹配标记，提高低频多字词的识别率。

# 参考文献：

[1] 化振红．深加工中古汉语语料库建设的若干问题[J]．西南大学学报：社会科学版，2014，40(3)：136-142.(HuaZhenhong.Some Problems in the Deep Processing of theMedieval Chinese Corpus Construction[J]. JournalofSouthwest University:Social Science Edition,2014,40(3):136-142.)

[2]王嘉灵．以《汉书》为例的中古汉语自动分词[D].南京：南 京师范大学，2014.（Wang Jialing.The Medieval Chinese Automatic Segmentation Using the“Han Shu”as an Example [D]. Nanjing: Nanjing Normal University, 2014.）   
[3]王晓玉，董志翘．中古汉语分词不一致原因探讨[J].汉语 史研究集刊,2015,19:20-33(Wang Xiaoyu,Dong Zhiqiao. TheInvestigation of Middle Ancient Chinese Word Segmentation's Inconsistency[J]. The Collected Papers of the Chinese History Study,2015,19:20-33.)   
[4]GB-T13715-1992．信息处理用现代汉语分词规范[S].北京： 中国标准出版社，1993.(GB-T13715-1992.Contemporary Chinese Language Word Segmentation Specification for Information Processing [S]. Beijing: China Standard Press, 1993.)   
[5]罗竹风,等．汉语大词典[M]．上海：上海辞书出版社,2011. (Luo Zhufeng,et al． The Great Chinese Dictionary [M]. Shanghai: Shanghai Lexicographical Publishing House, 2011.)   
[6]蔡镜浩．魏晋南北朝词语例释[M]．南京：江苏古籍出版 社，1990.(Cai Jinghao．Wei，Jin，Southern and Northern Dynasties Words and Expressions [M]. Nanjing: Jiangsu Ancient Books Publishing House,1990.)   
[7]董志翘，蔡镜浩．中古虚词语法例释[M].长春：吉林教育 出版社，1994.(Dong Zhiqiao,Cai Jinghao.Middle Ancient Function Words and Expressions [M]. Changchun: Jilin Education Publishing House,1994.)   
[8]丁福保．佛学大辞典[M].北京：中国书店出版社，2011. (Ding Fubao．Buddhist Dictionary [M].Beijing: China Bookstore Publishing House,2011.)   
[9]李维琦，蒋冀骋．佛经词语汇释[M].长沙：湖南师大出版 社，2004.(Li Weiqi，Jiang Jicheng.SutrasWords Explanations [M]. Changsha:Hunan Normal University Publishing House,2004.)   
[10]黄居仁，陈克健，陈凤仪,等．《资讯处理用中文分词规范》 设计理念及规范内容[J]．语言文字应用，1997(1):94-102. (Huang Juren，Chen Kejian，Chen Fengyi,et al．A Segmentation Standard for Chinese Information Processing: Design Criteria and Content [J].Journal of Applied Linguistics,1997(1): 94-102.)   
[11] 黄昌宁，赵海．中文分词十年回顾[J]．中文信息学报, 2007,21(3): 8-19.(Huang Changning, Zhao Hai. Chinese Word Segmentation: A Decade Review [J]. Journal of Chinese Information Processing,2007,21(3): 8-19.)   
[12]吴琼，黄德根．基于条件随机场与时间词库的中文时间表 达式识别[J]．中文信息学报，2014，28(6):169-174.(Wu Qiong,Huang Degen.Temporal Information Extraction Based on CRF and Time Thesaurus [J].Journal of Chinese Information Processing,2014,28(6):169-174.) [13]段宇锋，朱雯晶，陈巧，等．条件随机场与领域本体元素 集相结合的未登录词识别研究[J]．现代图书情报技术,   
2015(4): 41-49.(Duan Yufeng, Zhu Wenjing, Chen Qiao,et al. The Study on Out-of-Vocabulary Identification on a Model Based on the Combination of CRFs and Domain Ontology Elements Set[J].New Technology of Library and Information Service,2015(4): 41-49.) [14]修驰．适应于不同领域的中文分词方法研究与实现[D].北 京：北京工业大学，2013．(Xiu Chi．The Research and Implementation of Chinese Word Segmentation for Different Domains [D].Beijing:Beijing University of Technology,   
2013.) [15]宋彦，蔡东风，张桂平，等．一种基于字词联合解码的中 文分词方法[J]．软件学报，2009，20(9):2366-2375.(Song Yan，Cai Dongfeng，Zhang Guiping，et al.Approach to Chinese Word Segmentation Based on Character-Word Joint Decoding[J].Journal of Software,2009,20(9): 2366-2375.) [16]石民，李斌，陈小荷.基于CRF 的先秦汉语分词标注一体 化研究[J]．中文信息学报,2010,24(2):39-45.(Shi Min,Li Bin,Chen Xiaohe.CRF Based Research on a Unified Approach to Word Segmentation and POS Tagging for Pre-Qin Chinese[J]. Journal of ChineseInformation Processing,2010,24(2):39-45.) [17] Zhao H,Kit C Y.An Empirical Comparison of Goodness Measures for Unsupervised Chinese Word Segmentation with aUnified Framework[C]//Proceedings of IJCNLP 2008, Hyderabad,India.2008:9-16.

# 作者贡献声明：

李斌：提出研究思路，软件编程实现，修改论文质量;  
王晓玉：负责进行实验，获取并分析数据，论文起草和修改。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据见期刊网络版http://www.infotech.ac.cn。  
[1]王晓玉，李斌.结合词典的中古汉语CRFs分词测试数据.

收稿日期:2017-03-14  
收修改稿日期:2017-04-20

# Automatically Segmenting Middle Ancient Chinese Words with CRFs

Wang Xiaoyu Li Bin (School of Chinese Language and Literature, Nanjing Normal University, Nanjing 210o97, China)

Abstract: [Objective] The purpose of this paper is to explore the influence of the word segmentation consistency and the corpus types in Middle Ancient Chinese (MAC).It tries to improve the accuracyand eficiency of the automatic word segmentation,a basic procedure in processng ancient Chinese,based on the CRFs model.[Methods]First,we optimized the segmentation principles for MAC historical records,Buddhist scriptures and novels.Then,we combined the CRFs model with dictionary to reduce the segmentation inconsistency in the manual procedures.Finaly, we added two features tothe CRFs model (i.e.characterclassificationand dictionary information),and identifiedthebest word segmentation template by comparison experiments. [Results] The F-score was higher than $9 9 \%$ in the closed test, while it was from $89 \%$ to $9 5 \%$ in the open test. [Limitations] The segmentation consistency was improved on the words with two characters，and more studies were needed on the segmentation of words with more than three characters. [Conclusions] The proposed method could efectively improve the accuracy of automatic word segmentation for mediaeval Chinese corpus.

Keywords: Conditional Random Fields ModelSegmentation Consistency Middle Ancient Chinese Word Segmentation

# IMLS资助Educopia和UNCSILS研究以改进原生数字资源存档工作流的开放源码软件

Educopia(一个非营利性的组织，旨在促进文化、科学和学术机构之间的合作)和北卡罗莱大学信息和图书馆科学学院(UNC SILS)已从美国博物馆和图书馆服务研究所(Institute of Museum and Library Services,IMLS)获得价值超过68万美元的资助，用于支持OSSArcFlow项目，该项目旨在调研图书馆、档案馆和博物馆采用开源工具的情况并提供支持。研究团队将与 12 家合作机构进行合作，共同研究、设计和测试实施三大领先的开源软件(OSS)技术：BitCurator 环境，ArchivesSpace 和Archivematica。

通过与多种规模和类型的机构合作，该项目的调查人员将能够收集到重要的意见，这将使许多图书馆和档案馆受益。最终，所有项目成果包括陈述、工作流程、总结结果、培训模块和指南，都将得到广泛传播，以帮助其他机构成功地采用开源的数字化策略和保存工具。

北卡罗莱大学信息和图书馆科学学院教授，项目主要研究人员 Christopher Lee说:“我们的目标是使得图书馆、档案馆和博物馆实施数字化管理工具的艰巨任务变得更加容易。该项目将发现并支持更有效率、更有效的数字化保存工具，来促进图书馆和档案馆的努力，从而确保全人类对日益增长的原生数字化文化遗产的持续访问。”

该项目的合作机构包括杜克大学、麻省理工学院、纽约公立图书馆、纽约大学、莱斯大学和斯坦福大学等。

(编译自:https://sils.unc.edu/news/2017/OSSArcFlow)

(本刊讯)