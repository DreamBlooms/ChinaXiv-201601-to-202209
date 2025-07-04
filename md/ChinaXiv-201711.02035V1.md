# 面向在线评论的比较观点挖掘研究综述

高　松」王洪伟¹冯　罡²王伟³(同济大学经济与管理学院上海 200092)2(上海通用汽车销售有限公司上海 201206)3(华侨大学工商管理学院泉州 362021)

摘要：【目的】对比较观点挖掘和相关研究的主流研究方法和步骤进行综述，为相关领域的未来研究提供指导。【文献范围】从 WoS,Google Scholar，CNKI 中以“比较观点(Comparative Opinion)”、“比较句识别(ComparativeSentence)”、“比较关系(Comparative Relation)"等为检索词筛选获得 55篇相关文献。【方法】基于文献调研，介绍比较范畴的划分、比较句识别、比较关系抽取和比较观点情感分析等研究进展。【结果】由于有限的序列规则，比较观点的识别难以进一步提高，对隐形比较观点的识别研究鲜有提及，并且现有的抽取技术难以很好地提取比较要素。此外，比较观点缺乏细粒度的情感分析。【局限】缺乏对现有比较观点识别方法的对比分析。【结论】本文提出的研究框架可以为未来进一步研究提供参考。此外，未来的工作重点应关注通过比较观点识别追踪潜在竞争对手，分析产品竞争力，以及提供不同商品的对比分析等。

关键词：比较观点在线评论情感分析分类号：G353

# 1引言

225人中有211人认为以下评论非常有用  
★★☆☆☆说几句大实话  
留高者王海涛前500名评论人于2014年3月24日  
款式机身|已确认购买  
入手70D我考虑了一个月。当然不是600快的花费而举棋不定，主要是在D7100、60D、70D之间做了大量的对比+  
我第一部数码机是A70，那个小破机器只有320万像素，背后的显示屏小的可怜（类似于一张135的腕片底版大小）。但用了十年了，现在我组夫偶尔还在用。第二部数码机是富士HS11，三年前推出的时候，30借长焦已经是做视市场的长焦皇了，当时佳能最高26借。在丰单反中，这款机器被很多人相中，因为”一镜是很多人的选择。  
125 of 144 people found the following review helpful  
★☆☆☆☆Fantastic!  
By J. mcdaniel on February 10, 2015  
Styic Nomc: Block | Itm Packago Quantity: 1|Vorified Purchase  
ILOVE mynew Nikon Colpix cameral!Mylastcamera was the Canon PowershotA495.Icould NOT believe the diference in qualityofthe pictures.This one takes noticeablyclearer shots.Thfeatures are easytounderstand.idn't evenneed toreadthe manual.Iaventhad to change the batteries yet, and with my old Canon,Iwould have had to by now. Sooo happylgot thisl

比较是人们认识事物的基本方法。将多个事物加以对照，可以发现其在某些方面的相似性或差异性[-3]。尤其在商业领域，常言“不怕不识货，就怕货比货”。消费者常借助于与其他同类产品的比较来进行购物决策[2-3]。对于商家而言，通过比较能够体现出产品的竞争优势和不足，为市场营销策略以及产品改进提供依据[,4]。

近年来，社会化媒体日益普及，为消费者发布自己对于产品的观点和体验提供了广阔的平台。在线评论作为承载消费者观点和建议的载体，蕴含着大量的比较信息[2-3.5-6]，如图1所示，并且主要以比较结构句式的形式展现[6-8]

作为常见的表达方式，比较句有助于评论者更加立场鲜明地陈述观点[7。购物前，消费者倾向于查询相关产品的在线评论，从不同角度对产品进行比较，从而形成自己的判断[2.5]。但是，由于信息过载等问题,导致大多数用户没有足够的时间和精力浏览全部信息，难以形成有效的、高质量的决策信息[6]。

因此，有效地识别在线评论的比较信息，可为观点要素抽取、词语倾向性分析提供数据基础，也可为消费者和商家做出科学决策提供技术支持[2-3.9]。面向在线评论的比较观点挖掘是综合语言学、机器学习与自然语言处理于一体的研究[2.6,10-11]，涉及文本分类、实体提取、观点挖掘、情感分析等领域[6]这些研究取得了一定进展，但鉴于在线评论比较信息识别与提取具有自身特殊性与复杂性，目前仍处于探索阶段。

比较句最朴素的定义为“含有比较结构和比较特征词的语句[8.11-13]”，指出比较句包含一定的结构，因此可以将这种类型的比较句通过模式来表达[14]。但是,对于复杂的在线文本，含有特定比较结构或比较词的语句不一定是严格意义上的比较句[5,13,15]。另外，还有更多的比较句不具有统一的结构或包含特定的比较词语[14-16]。本文研究的对象是在线评论，针对评论中的比较句采用如下概念：表达不同事物在属性或特征上差别的语句][2,9,14-16]

基于现有的比较观点挖掘，本文将相关研究归为4 部分：比较句式研究、比较句识别、比较关系提取、比较观点倾向性分析。研究框架如图2所示，这4部分既独立，又相互联系。

![](images/b6224e00f56c38419fae74d513b876cda96fdbb7eea3c9ed6246314fce9d5c1a.jpg)  
图2本文归纳的比较观点挖掘研究框架

其中，比较句式研究主要分析比较句的语法结构、语义、显性和隐性比较句的特点；比较句识别基于比较句式的研究成果，进行比较句的自动识别，这里涉及自然语言处理、机器学习等技术，确保准确率与召回率；比较关系提取是对已识别好的比较句，采取语义角色标注等技术进行比较关系抽取，获得比较主体、客体、属性、结果；比较观点倾向性分析是针对抽取的要素，挖掘比较主体和客体的比较观点，挖掘情感倾向性、情感强度，找出主客体的差别。最后将比较观点挖掘结果进行应用，更好地向消费者和企业展示。

# 2比较句式研究

# 2.1基于语义的比较句研究

与英文不同，中文比较句不具有比较级或最高级的形态。另外，普通词语、成语以及谚语等也可以表达多个事物间的比较，格式上灵活多变，这给比较句的识别带来了困难。早期的研究是从句子语义的角度出发，认为凡是含有比较和对比含义的句子都是比较句[14]。如吕叔湘[17认为"与其害民，宁我独死”、“越大越没规矩”、“云是白的，山也是白的"算是比较句；黎锦熙等[18把“与其写死文，不如说活话"看作是表示“审决"的比较句。这样一来，比较句的范围很宽泛，显得庞杂。事实上，从人类认知角度看，表示比较语义的语言手段是多样的，既可以通过词汇表示，如"更慢”、“难一些”，也可以通过句法手段来表示，如“他比我慢”，甚至通过上下文或语境，如"这道题不算难，那道题才难呢”。早期研究之所以在比较句的划分上有诸多差异，原因在于对比较的范畴不加区别，只从意义的角度同等对待[14,16,19]，这一阶段的比较句可以称为广义的比较句。

英文比较句带有鲜明的标志词，表达更直接。Sawada[13将比较结构定义为两个事物、事件或问题在统一尺度下进行的显性比较。这个定义不包含原级和最高级。而Jindal 等[7-8]认为原级和最高级是比较。Lerner 等[20将比较句定义为程度上的量化，说明某个事物或属性的优劣。Kennedy[21]基于逻辑的角度讨论了比较句的语义差别。Schwarzschild[22]和Rett[23]采用程度分析法研究了差比句的语义，强调了两个事物程度值的不等关系。

# 2.2语义与句法结合的比较句研究

这一阶段注重汉语比较句在句法结构上的特点，将语义与形式结合起来，考虑标志词与句法结构形式,这为比较句的自动识别提供了思路。

学者研究了比较的范畴，将复杂的汉语比较句进行分类，如表1所示。黎锦熙等[18]、吕叔湘[17]、刘焱[24]都研究了不同类型比较句的特点，对比较的范畴进行划分。对于英文比较句，Sawada[13],Kennedy[21]和Rett[23]根据词性分别描述了 Nominal Comparatives、Adjectival Comparatives 、 Adverbial Comparatives、Adjectival Superlatives、Adverbial Superlatives这些类型的比较句；Jindal 等[7-8]将比较句分为 4 种类型:Non-Equal Gradable、Equative、Superlative、Non-Gradable。

在比较句类别划分基础上，学者研究了比较句的结构问题，认为汉语比较基本形式 $\mathrm { \Delta X ^ { + } }$ 比较词 $+ \mathbf { Y } + \mathbf { \mu }$ 范围[15,17,24]。这一形式表明，采用汉语表达比较语义时，先陈述比较前项X作为主语或主题，比较词加上比较后项作为状语，比较点(或是隐性的)以及比较结果作为谓语，确定比较所依据的范围标准。基于这种形式，结合汉语特点，学者提出5种基本句式[25]：“和/跟…比(较)/相比(较)；“有"字句；“像"字句；“比"字句;“于"字句。前三种既表示等比，也可表示差比，后两种只能表示差比。语义上，等比表示被比较对象在性质、程度上相近或相等，差比表示相互间有差异，并不相同或相似。句法上，差比句的形式变化比等比句复杂。学者细分了比较句式，并研究了不同类型的句法标志[15,24-25]

表1比较句的分类  

<html><body><table><tr><td>作者</td><td>比较句类别划分</td></tr><tr><td>黎锦熙等[18]</td><td>平比句、差比句、审决句</td></tr><tr><td>吕叔湘[17]</td><td>类同、比拟、近似、高下、不及、胜过、 尤最、得失、不如、倚变</td></tr><tr><td>刘焱[24]</td><td>差比句和平比句</td></tr><tr><td>Jindal等[7-8]</td><td>Non-Equal Gradable、Equative、 Superlative、Non-Gradable</td></tr><tr><td></td><td>Nominal Comparatives、Adjectival</td></tr><tr><td>和Rett[23]</td><td>Sawada[13], Kennedy[21]Comparatives、Adverbial Comparatives、 Adjectival Superlatives、Adverbial</td></tr></table></body></html>

不同于中文比较句，英文比较句是通过形容词和副词的比较级或最高级来表达，即考虑含有比较语义的词汇来分析英文比较句的语法，并将英文比较句分为正式比较与非正式比较[21-22]。其中，同比结构包含:含有as 的同级比较；比较句的否定结构表达同级比较；含有一些词语短句，如"in the same way”、“beequalto”、“similarto”。差比的结构既可以通过词组“better than”、“superiorto”表达，也可以通过词汇“above”、“differsfrom"展现。极比结构表示某人或某物在特定范围内最突出，达到最高程度，用最高级来表示。研究发现[13.21-23]，部分英文比较句虽然含有比较指示词，语义上却无比较，最高级只是一种夸张手段，用于加强语气，常用来表示数量、时间、程度等含义。例如,“more than 350 persons”、“the greatest pleasure”、“would better”、“more or less”，其对比较句识别的干扰较大。

# 2.3比较句显隐性研究与特殊句式

基于上述研究成果，结合不同的比较词和句中的形容词、副词，学者研究比较的显性表达、隐性表达、否定形式、比较的程度等问题，并对特殊比较句句式进行剖析[10-11,19.23]，对比较句的准确识别提供了理论支持。

汉语是意合语言，词语没有形态变化，语法关系是通过词序和虚词体现，句子常常按照逻辑顺序排开,多为时间顺序。以 $^ { \mathrm { 6 6 } } \mathrm { X ^ { + } }$ 比 $+ \mathrm { Y + W ^ { \prime } }$ 结构为例，它体现出一种动态和顺接，描述比较的过程。即：比较前项 X与比较后项Y相比后，得到结果W。比较后项Y放在结论项W的前面，更加强调Y，表示跟Y相比，有结论W。英语是形合语言，词语有诸多形态变化，形式严谨，层次分明，以限定动词为中心，控制各成分间的关系。以“er-than"比较结构为例，它描述的是一种状态，表达比较时需要用形容词和副词的比较级等形式。如"he runs faster than her"核心是"run faster”,“thanher"是附加解释。“他跑得比她快"表达的是"跟她相比,他更快”，强调的是“比她”。

显性比较和隐性比较广泛存在于比较句中[13]。显性比较句含有明显的比较指示词，中文显性比较句常采用“比”“相比”“像”“一样”“更”“不如”“越…越…”等标记性词汇；英文显性比较句则含有“than”、“cheaper”、“bigger”、“best”、“same”、“as·as"等词汇以及含有形容词和副词的比较级、最高级等词汇。隐性比较句指的是未含有明显的标记词汇,但在语义上存在比较关系的句子[13]。中文隐性比较句如"桌子上的土有硬币厚”，在语义上形成了比较含义,但没有明显的标记；英文隐性比较句如"This book is24Yuan,andthatbookis55"叙述了两个比较对象的客观情况，并没有明显地将两个实体进行比较，但从语义上构成了比较含义。事实上，针对不同类型的句子,显性和隐性比较句的识别效果也不同。可以通过前后句中与比较有关联的词句得以识别[13]；Kennedy[21]对显性和隐性比较做了区分，显性比较是指在事物 $\textbf { \em x }$ 和y之间基于可分等级的性质 $\mathbf { g }$ 排序，规约含义为：x拥有g的程度超过y拥有g的程度。通常句中有专门的级数的形态变化，隐性比较是指在 $\textbf { \em x }$ 和y之间基于可分等级的g排序，采用 $\mathbf { g }$ 原型，通过语境或描述的作用，表达出 $\mathbf { x }$ 具有g，而y没有。例如他比你年龄大(显性)，他年龄大(隐性)。

一些特殊比较句句式，如"一M比一M”“X比N还N"，,“X连Y也都VP"也引起学者的兴趣，从认知的角度探究了这些句型的含义。另外，比较句中的否定词、形容词、副词也引起关注。例如，考虑了形容词在比较句中的位置、功能[26-27]；考虑程度副词(如“还”、“更")的影响[14-15,25,28]。通常，带"还"的句式具有比较功能和比拟功能,如"X比Y还W”、“X比Y还Y"，带“更"句式具有语义层级性特征，如“X比Y更W”。比较句中的否定句式有“不如"句、“没有"句、“不像"句、“不比"句、“没法比"句，否定是语言表达的重要手段[28]，否定比较句带有更强的主观性和不确定性,需要针对不同的句型进行分析；还有学者从形式语义学的角度论证了不同类型差比句的不同语义形式，提出用传统的程度分析法分析形容词差比句，动词差比句更适合于用一一对应分析法来分析[29]。

# 3比较句挖掘研究

# 3.1 比较句识别

尽管对比较句结构进行了剖析，并总结了常用句式，然而，这些句式尚没有以数字化的形式存储起来为计算机所处理；另一方面句式的完备性也有待完善。在线评论作为非结构化文本，比较句的形式更是复杂多变，常包含一些网络用语。因此，针对在线文本，寻找比较关系的识别方法并构建数字化形式的比较模式库，对于比较观点的挖掘具有现实意义。总体而言，在线文本的比较句识别涉及到的方法有基于类别序列规则的识别[7-8]、基于比较模式库的识别[30]和基于特征关键词的识别[11，如表2所示。

# (1）基于类别序列规则的识别

类别序列规则(Class Sequential Rules,CSR)是将类别序列模式应用到比较句的识别，形成识别规则，并寻找满足用户定义的最小支持度约束的模式，为比较句识别提供特征输入。Jindal 等[7-8]首先提出通过CSR自动识别比较句的研究课题。Huang 等[31加以改进，将该方法应用到中文评论中的比较句上，取消了滑动窗口策略，将句中每个分句作为一个序列来提取与匹配规则，也使得诸多非比较句满足了序列规则。如“苹果手机没有三星手机好用”、“苹果手机没有电池可拆卸”，序列规则都是"n…没有…n…v”。因此，有学者针对这一问题展开研究，发现比较主体和比较基准通常位于比较特征词和CSR序列规则的两侧。以特征词、类别序列规则和实体对象信息(主要是对象的位置和数量)作为特征，对比较句进行了有效识别[32]；另外,Liu等[33]也利用CSR方法，结合统计特征进行了在线评论比较句的识别研究；王洪伟等[也将类别序列规则与人工模式库相结合，识别中文在线评论中的比较句，获得了很高的准确率与召回率。

表2比较句识别方法  

<html><body><table><tr><td>作者</td><td>关键技术</td><td>数据来源</td><td>识别效果</td></tr><tr><td>Jindal 等[7-8]</td><td>CSR</td><td>评论，论坛，新闻</td><td>准确率 79%，召回率81%</td></tr><tr><td>Huang 等[31]</td><td>CSR，序列生成策略，模式长度，分类器为 SVM</td><td>ZOL 产品论坛中的笔记本评论</td><td>准确率91.4%，召回率79.6%, F-度量85.0%</td></tr><tr><td>黄高辉等[32]</td><td>CSR和特征词为特征,SVM为分类器</td><td>百度知道中的汽车领域和数码产品 领域</td><td>准确率96.6%，召回率88.6%, F-度量92.4%</td></tr><tr><td>Liu等[33]</td><td>CSR，比较词，统计特征词，分类器为 SVM</td><td>ZOL中的产品评论</td><td>准确率84.3%，召回率82.4%, F-度量83.3%</td></tr><tr><td>王洪伟等[6]</td><td>CSR与人工模式库结合</td><td>大众点评网数据</td><td>准确率99.8%，召回率97.6%, F-度量91.4%</td></tr><tr><td>白林楠等[15]</td><td>句法语义规则库</td><td>14本对外汉语教材和HSK考试语料</td><td>准确率95.6%，召回率85.4%, F-度量90.2%</td></tr><tr><td>宋锐等[30]</td><td>中文比较模式库</td><td>IT168产品评论网评论数据</td><td>准确率77.0%，召回率80.0%, F-度量78.56%</td></tr><tr><td>周红照等[34]</td><td>基于语义分类的规则库</td><td>COAE2012发布的汽车、电子领域 语料</td><td>准确率90.3%，召回率95.3%, F-度量92.7%</td></tr></table></body></html>

(2）基于比较模式库和规则库的识别

该方法依靠大规模的比较句语料库。语料库包含比较句的词、词性、位置、语义以及比较属性的领域知识等特征，并按照比较句分类体系将其划分为不同类别。比较句的比较模式以正则表达式存储在XML文档中，每个模式附一个比较类别标签。研究证实，中文比较模式库和规则库能够较好地实现中文比较句的自动识别[6,15.30]。但是，难以识别复杂的比较句，为此,学者考虑了比较句与比较要素之间的“共生关系”，构建比较特征词典系统，根据汉语比较句句义分类，构建比较句识别模式库[34]。比较模式库和规则库中包含丰富的专家知识，构建完备的比较模式库和规则库对比较句识别提供保障。为了保证识别的准确率，提取比较句的词性、位置、语义等特征将有助于识别效率的提高[。但是，目前比较模式库和规则库的规模还不够大，覆盖的内容还有待进一步扩充。

# (3）基于特征关键词的识别

该方法是提取句子中具有比较含义的词，将其作为识别比较句的依据，包括副词(更、最、极)、比较词(比、于、有)、比较实词(超过、一样、差不多)等。

Ganapathibhotla 等[11]、Park 等[35]考虑了英语中的特征词汇对于识别的影响。Huang 等[31]、黄高辉等[32]、Liu等[33]、He等[3研究了在线评论或论坛中比较句的特征关键词，将关键词应用到比较句的识别，显著提高了识别的准确率、召回率和F-度量。研究发现，很难依靠一个词语清楚表达比较，出现关键词的句子未必是比较句，而非比较指示词与其他词搭配后也能形成比较句式，为此需要借助于由若干词与词性所构成的模式来提高识别的准确度。因此学者大多将基于特征关键词的识别方法与其他技术相结合[11,15,19.32]。

在线评论中的比较句的识别还不能令人满意。特别是一些隐含的表达，普通词语、成语以及谚语都可以表达事物之间的比较，这给在线评论中的比较句识别带来困难。

# 3.2 比较关系抽取

识别比较句后，需对其中的比较主体、比较客体、比较内容和比较结果进行提取。比较关系形成的条件是比较实体在相同属性上形成高低优劣，并且是在某一标准上的比较，比较后要形成明确的结果，如表3所示。常用方法有标签序列规则(Label SequentialRules,LSR)[7]、条件随机场(Conditional Random Fields,CRF)[30]、语义角色标注(Semantic Role Labeling,SRL)[37]。

表3比较关系抽取方法  

<html><body><table><tr><td>作者</td><td>关键技术</td><td>数据来源</td><td>识别要素中能够达到的最好效果</td></tr><tr><td>Jindal等[7]</td><td>LSRs 和 keywords</td><td>评论，论坛，新闻</td><td>准确率86.1%，召回率62.1%, F-度量72.2%</td></tr><tr><td>宋锐等[30]</td><td>CRF，考虑词性，语义，位置等特征</td><td>IT168产品评论网评论数据</td><td>准确率90.4%，召回率85.6%, F-度量88.0%</td></tr><tr><td>黄高辉等[32] CRF 和领域词典</td><td></td><td>百度知道中汽车领域和数码领域数据</td><td>准确率80%，召回率92%,F-度量85%</td></tr><tr><td>李建军[28]</td><td>SRL</td><td>消费者评论网站抽取的1080个比较句</td><td>准确率78.0%，召回率80.0%</td></tr><tr><td>周红照[34]</td><td>抽取规则库</td><td>COAE2012发布的汽车、电子领域语料 测试数据集</td><td>准确率46.6%，召回率48.9%</td></tr><tr><td>Hou等[38]</td><td>SRL</td><td>含有2000个中文比较句的语料库</td><td>准确率93.0%，召回率90.0%, F-度量91.5%</td></tr><tr><td>Li等[39]</td><td>基于序列模式的弱监督方法</td><td>Yahoo!Answers中的问题题目</td><td>准确率91.6%，召回率76.0%, F-度量83.3%</td></tr><tr><td>He 等[36]</td><td>LSR，比较要素命名特点</td><td>360buy,ZOL,IT168 and Amazon 抽取的准确率 92.1%，召回率 89.3%, 手机评论数据</td><td>F-度量90.7%</td></tr></table></body></html>

# (1）基于标签序列规则的提取

Jindal等7采用比较关系表示比较句的核心语义，提出5元组的概念，即关系词、产品属性、实体1、实体2、比较类型，这5个元素识别是通过LSR匹配来实现。LSR对英文要素提取的效果较好，但在中文方面并不理想。

# (2）基于条件随机场的提取

CRF是基于最大熵和隐马尔科夫模型的一种判别式概率无向图学习模型，应用于分词、词性标注和实体识别等领域。

单独的比较句通常只含有两三种元素[30]，或缺少比较客体，或缺少比较主体，这种情况对于评论文本尤为常见。因此，选取比较主体、比较客体及其上下文的词、词性、位置、语义以及比较属性的领域知识等特征，利用CRF模型进行中文比较关系抽取，准确率显著提高[30]；还有学者考虑了比较基准[32]，在预定义规则的基础上，采用CRF算法抽取了比较主体和比较基准，不过对比较基准的抽取效果不理想。

# (3）基于语义角色标注的提取

语义角色标注SRL是将词语序列分组，并按照语义角色对其分类。SRL的目的就是找出给定句子中谓语词的对应语义成分，即核心语义角色(主语、宾语等)和附属角色(时间、地点等)。SRL只针对句子中的部分成分与谓语的关系进行标注，属于浅层语义分析。

Kessler 等[7运用SRL对英文比较句的元素进行标注与提取，效果优于之前的方法。但是，只使用SRL对中文比较关系提取效果较差，为此进行不同程度的改进。例如，构建混合比较模式的SRL模型，对汉语比较句进行两阶段标注[9]；将SRL与句法分析树相结合，提出语义角色分析树[28]，通过计算两棵子树之间的匹配相似度抽取比较关系；还有学者尝试将CRF应用到SRL 中[38]。上述研究取得了一定成果，但是采用 SRL进行中文标注的效果还有待提高，对涉及上下句的比较信息提取尚未能够有效解决。

此外，还有基于序列模式的弱监督方法[39]、基于中文比较句要素命名特点的抽取[36]、基于概念层次网络的中英文专利文本比较句提取[40-41]。综上所述，比较关系的提取尚未形成有效的方法，未来的研究可借鉴信息抽取领域的实体名称抽取和实体属性抽取技术。

# 4比较观点倾向性分析

比较观点倾向性分析的核心是：比较对象之间相同还是不同，若有差异，孰优孰劣，并且差异程度如何。因此，比较观点倾向性分析就是计算两个或多个产品的情感倾向性和强度，涉及到情感分析技术。

情感分析(Sentiment Analysis)是利用文本挖掘技术对在线评论进行语义分析，旨在识别用户的情感是“高兴"还是“伤悲”，或判断用户的观点是“赞同"还是“反对”。其涵盖多个研究任务，例如文本的主客观检测[42]；不同粒度的情感分析[43]；产品“特征-观点对"提取等[44]。近年来的研究围绕粗粒度分析和细粒度分析展开，粗粒度情感分析采用基于模型的方法、无监督方法和半监督方法；细粒度情感分析采用基于语义和机器学习的方法。研究表明，即使是极性相同的词汇，其所表达的情感强度也有可能不同，例如“好"和“优秀”，情感极性都是正面，但是后者比前者的强度大得多。此外，程度副词也可以改变被修饰词的情感强度[45]。

情感分析技术为比较观点倾向性研究提供了技术支持，但是二者存在一定区别。情感分析是针对某个产品表达消费者是否满意，而比较观点是针对两个以上产品的情感倾向分析。比较观点倾向分析是情感分析的进一步延伸，属于句子级的情感分析。在研究多个产品的情感倾向时，不仅需要考虑观点词语本身的倾向和强度，还需要考虑比较主体和比较客体的位置，以及比较词本身的情感方向等[因素。Ganapathibhotla等[11]将英文比较句分为有倾向和无倾向，对于比较词和特征词都无倾向时，采用PMI方法计算倾向值。有学者借鉴了基于情感词典的倾向性分析方法[46]，构建了基础情感词典、领域词典、属性词典、副词词典及一个比较句规则库，结合比较句的句式特征判断比较实体的情感倾向性，但是这种方法并不能在各领域普遍适用。

另外，在评论系统中，同一比较句会出现针对相同比较实体的多个属性的比较，并且比较结果不统—[3.6,46]。例如，“苹果6与三星 S6相比，系统占优,不过画面色彩略差点。”，比较主体是iPhone6，比较客体是GalaxyS6，比较属性有两个，分别是系统性能、屏幕色彩。可以看出，苹果的系统性能比三星好，但屏幕色彩不如三星。对于系统性能，iPhone6为正面,GalaxyS6为负面；对屏幕色彩而言，GalaxyS6为正面。为此，如何有效提取包含多个物体、多个特征的比较句中的观点，尚未获得有效的解决方法。

# 5比较观点挖掘的应用

上述研究主要是从在线评论的比较句中提取观点，但是，比较观点不仅仅体现在比较句中，不同文本中涉及同一个产品的讨论也隐含着比较信息。Liu等[47]开发了针对产品竞争分析的观点比较系统;Lerman 等[48]、Paul等[49]通过生成两个实体的比较概要信息，进行观点比较和差异性挖掘研究；Fang 等[50]在LDA基础上研究了比较观点的建模问题，提出Cross-PerspectiveTopic 模型，引人了“主题-观点"分布，模拟了在不同视角下的文档观点生成过程。

有学者从比较观点挖掘之外的角度探讨认知中的比较关系。通过Web搜索和比较两个对象的完整信息，揭示它们之间的关系[51；或者从论坛上抽取产品的比较信息，给消费者提供购物参考[52]；学者还尝试从评论中建立产品特征情感数据库，根据情感的倾向性构建产品比较和推荐系统[52]；还有学者研究了大量文档集之间的共性与差别，通过生成概率混合模型获得不同文档之间的主题比较信息[53]。

比较是抽象的概念，将比较结果可视化，有助于比较观点的明确表达。例如，网络分析技术把实体视为节点，将节点间的关系抽象成边，采用PageRank 和HITS 算法计算节点重要度，从而构成产品比较网络[54]。学者还发现，在线评论包含大量关于竞争对手的信息，于是提出图形模型提取竞争性产品的比较关系并将其可视化[，分析竞争者之间的相互依赖关系，帮助企业发现潜在的风险和设计新产品的营销策略[2.6.55]。

# 6研究评述与展望

# 6.1 研究评述

基于在线评论的比较观点挖掘涉及语言学、自然语言处理、机器学习等多个领域。识别比较句、提取比较关系要素、挖掘比较观点是相对独立但又相互联系的课题，研究成果可应用于产品竞争情报获取、商务智能挖掘、消费者偏好分析、产品缺陷分析、同类产品的竞争排名[2,39,52-53,55]

目前，针对在线评论的比较句识别，提出了基于序列规则、基于比较模式库、基于特征关键词的方法[6,8,11,0.33-35.46]；针对比较关系的抽取，采用了LSR、CRF、SRL 等技术[16.36,38.46]；针对比较观点的挖掘，采用了情感分析技术[6.11,49-50]。但是，相关研究面临诸多难题:

(1）在线评论中比较句识别的准确率有待提高

尽管许多研究关注在线评论中比较句的识别，但是对于非结构化的在线评论文本，已有方法的识别效果仍不理想。特别是相对于英文比较句，中文比较句句式类型多而杂，基于规则、模式库的手段尚未全面涵盖，亟待建立大型的比较模式库。因此，将比较的语言学研究成果引入比较观点挖掘研究工作中是十分有必要的。先区分在线评论中比较句的不同类别，再结合语言学成果，通过句式和关键词的匹配，构造不同类别的规则库。

# (2)隐性比较句的识别有待深入

已有研究对含有明显比较指示词的比较句识别效果较好。但是，在线评论是非结构化文本，一些评论语句不包含明显的指示词，但同样表达比较语义。对这些句子的识别尚未形成有效的解决方法。实际上，比较句拥有很多特点，比如同一个评论中出现两个以上产品名称，形容词或副词短语均能揭示出该评论包含比较关系。因此，将语义挖掘、关联规则的方法引入便于隐性比较关系的识别。

# (3）比较关系抽取效果有待改进

完整的比较句包括四元组<比较主体，比较客体，比较属性，比较结果 $\cdot > ^ { [ 9 , 3 1 ] }$ ，其中，比较主体、比较客体、比较属性可以归结为实体。就词性而言，比较主体、比较客体和比较属性多为名词和代词类型的实词；从语义而言，它们涉及上下文中有概念的实物及属性。然而，比较的主客体不易区分，代词不能有效匹配，属性特征杂乱。因此，将现有的实体抽取、特征挖掘等研究成果应用在比较关系抽取上可以获得更好的抽取效果。

(4）比较观点的情感倾向性及其强度有待深入研究

成熟的情感分析技术可应用于比较观点的情感倾向性分析。比较主体是基准，比较客体依附于比较属性，比较结果蕴含在比较句中。但是，有些比较结果需要根据语境才能得出。对于这类比较结果的倾向性分析，需要通过语义分析、句法依存等方法完成。此外，比较观点的情感强度应是未来的研究热点，不同产品之间的差距大小需要明确。进而可以对众多产品进行热度分析、竞争对手识别与竞争力分析。

(5）比较观点挖掘与可视化技术相结合

比较是一种抽象的概念，如果能结合定量的方法将其可视化、直观化，能清晰地表明观点，便于读者的理解。结合现有的一些技术，将比较关系定量化、可视化，能更好地将研究成果应用到实际当中。特别是构造产品特征比较网络，利用网络中的节点与连接，能够获取很多潜在的知识

# 6.2 研究展望

学者分别从字、词、句的角度对比较观点展开研究。英语形式严谨，层次分明，以限定动词为中心，很好地控制各词语成分间的关系。英文比较句注重词语的搭配，带有鲜明的标志词。例如，通过形容词和副词的比较级或最高级来表达比较含义。找出句子中的动词，以动词为核心分析句子的层次结构，或者挖掘句中的比较词汇，能够实现比较句的识别。

而汉语作为意合语言，句子通常按照逻辑顺序展开，词语无形态变化。中文比较句更多地注重结构上的变化，识别的难度较大。特别是，中文比较词过于繁多，依靠比较词或词语搭配识别中文比较句很难开展。由于句式灵活多变，也很难将其穷尽。因此，针对中文比较句的识别，首先要进行类别划分，每种类别中考虑词汇与句式特点进一步研究。

基于现有的框架(见图2)及其不足，未来可开展的研究方向如图3所示。

基于在线评论的比较观点挖掘分为三个子任务：比较句识别、比较关系提取、比较观点倾向性分析，它们是层层递进关系。对于比较句识别，进一步的研究工作应集中在不同类别比较句和隐形比较关系的识别上。借鉴已有的比较语言学研究成果，采用自然语言处理与机器学习技术，识别在线评论中的比较句并标记类别。这一工作尽管基础，但是对后续的研究是至关重要的。

而对于比较关系抽取，需要构建实体名称词典，结合实体抽取，语义与关联挖掘等技术对识别出的比较句进行要素提取。并且，在线评论是非结构化文本,需要分析评论语句的句法结构，才能准确抽取比较关系信息，这是一个难点。

比较观点倾向性分析是比较观点挖掘的核心，现有的情感分析研究已较为成熟，进一步的研究应关注比较观点的应用，如构建比较特征网络，挖掘潜在竞争对手，了解自身与竞争对手产品的优缺点，进而进行改善，提高竞争力。这一研究有助于消费者明晰不同产品的对比信息，辅助决策。并且能够促进生产厂商快速应对市场的变化，帮助销售商得到产品反馈信息，调整战略，增加销售利润。

![](images/94c209ab27132e3d9f6137b3b83f1cce46e31daf30c4c0fb13799846fdab01df.jpg)  
图3面向在线评论的比较观点挖掘研究路线

# 7结语

本文介绍了面向在线评论的比较观点挖掘研究进展。重点对比较句式、比较句识别、比较关系提取、比较观点倾向性分析及应用等方面的研究进行了总结。对比较句、比较句识别等概念进行界定；从比较句的语法结构、语义及显隐性角度进行比较句式研究概述；结合比较句式研究成果，分别基于类别序列规则、比较模式库、特征关键词等方法对比较句的自动识别进行概述；分别基于标签序列规则、条件随机场、语义角色标注等方法对比较关系提取研究进行概述;在比较要素抽取基础上，对比较观点倾向性的相关研究进行总结；介绍了比较观点挖掘研究的相关应用型研究。最后，对面向在线评论的比较观点挖掘研究进行评述，并提出一个框架供将来研究参考。

# 参考文献：

[1]Amarouche K,Benbrahim H,Kassou I. Product Opinion

Mining for Competitive Intelligence [J].Procedia Computer Science,2015,73:358-365.   
[2] XuK,Liao S S,Li J,et al.Mining Comparative Opinions from Customer Reviews for Competitive Intelligence[J]. Decision Support Systems,2011,50(4):743-754.   
[3] Kim Y,Jeong SR,DwivediR,etal.Competitive Intelligence in Social Media Twitter:iPhone 6 vs.Galaxy S5[J].Online Information Review,2016,40(1):42-61.   
[4] ShenJ,Li Y,Akula V,etal.Gaining Competitive Intelligence from Social Media Data[J].Industrial Management & Data Systems,2015,115(9):1622-1636.   
[5] Jin J,Ji P,Gu R.Identifying Comparative Customer Requirements from Product Online Reviews for Competitor Analysis[J].Engineering Applications of Artificial Intelligence, 2016,49:61-73.   
[6] 王洪伟，蒋文瑛，高松,等．面向竞争力分析的中文在线评 论的比较观点识别：以餐饮业为例[J].情报学报，2015, 34(12):1259-1264.(Wang Hongwei,Jiang Wenying，Gao Song,et al.Mining Comparison Opinions for Competitive Analysis by Sentiment Analysis: Evidence from Online Restaurant Reviews[J]. Journal of the China Society for Scientific and Technical Information， 2015, 34(12): 1259-1264. )   
[7]Jindal N，Liu B. Mining Comparative Sentencesand Relations[C]. In: Proceedings of the 2lst National Conference on Artificial Intelligence,Boston,Massachusetts,US.AAAI, 2006.   
[8]Jindal N,Liu B.Identifying Comparative Sentences in Text Documents[C]. In:Proceedingsofthe 29th Annual International ACM SIGIR Conference on Research and Development in Information Retrieval, Seattle,WA,USA. New York: ACM,2006.   
[9]Wang S,Li H, Song X.Automatic Semantic Role Labeling for Chinese Comparative Sentences Based on Hybrid Paterns[C]. In:Proceedings of the 2O1o International Conference on Artificial Intelligence and Computational Intelligence (AICI), Sanya, China.IEEE,2010: 378-382.   
[10]Liu B.Sentiment Analysis and Opinion Mining[J]. Synthesis Lectures on Human Language Technologies, 2012, 5(1): 1-167.   
[11] Ganapathibhotla M,Liu B.Mining Opinions in Comparative Sentences[C]. In: Proceedings of the 22nd International Conference on Computational Linguistics. Stroudsburg,PA, USA: ACL,2008: 241-248.   
[12] 王巍，赵铁军，徐冰，等．中文比较句的自动识别[J].智能 计算机与应用,2015,5(5):1-3.(Wang Wei,Zhao Tiejun,Xu Bing，et al. Automatic Identify Chinese Comparative Sentences [J]. Intelligent Computer and Applications,2015, 5(5): 1-3.)   
[13] Sawada O. Pragmatic Aspects of Implicit Comparison: An Economy-Based Approach[J]. Journal of Pragmatics,2009, 41(6):1079-1103.   
[14]尚平．比较句系统研究综述[J]．语言文字应用，2006(S2): 77-80.(Shang Ping.Literature Review of Systematic Research on Comparative Sentence[J]. Applied Linguistics, 2006(S2): 77-80.)   
[15]白林楠，胡韧奋，刘智颖．基于句法语义规则系统的比较 句自动识别[J]．北京大学学报：自然科学版，2015,51(2): 275-281.(Bai Linnan,Hu Renfen,Liu Zhiying. Recognition of Comparative Sentences Based on Syntactic and Semantic Rules-System[J].Acta Scientiarum Naturalium Universitatis Pekinensis,2015,51(2): 275-281.)   
[16]王素格，赵策力，刘慧慧．基于规则与序列模式的比较要 素缺省识别[J]．山西大学学报：自然科学版，2015,38(1): 85-92.(Wang Suge,Zhao Celi,Liu Huihui.Comparison Element Ellipsis Identification Based on Rules and Sequence Paterns[J]. Journal of Shanxi University: Natural Science Edition,2015,38(1): 85-92.)   
[17]吕叔湘．中国文法要略[M].北京：商务印书馆，1990.(Lv Shuxiang. Essentials of Chinese Grammar[M]. Beijing: The Commercial Press,1990.)   
[18]黎锦熙，周迟明．比较文法：词位与句式[M]．上海：上海 书店,1989.(Li Jinxi, Zhou Chiming. Comparative Grammar: Wordsand Sentence Patterns[M]. Shanghai: Shanghai Bookstore Publishing House,1989.)   
[19] 张辰，冯冲，刘全超,等．基于多特征融合的中文比较句识 别算法[J]．中文信息学报，2013，27(6):110-117.(Zhang Chen，Feng Chong，Liu Quanchao，et al． Chinese Comparative Sentence Identification Based on Multi-feature Fusion[J]. Journal of Chinese Information Processing,2013, 27(6): 110-117.)   
[20] LernerJ Y, PinkalM. Comparativesand Nested Quantification [C]. In: Proceedings of the 8th Amsterdam Colloquium. 1992.   
[21] Kennedy C.Comparatives,Semantics[A].// Encyclopedia of Philosophy of Language and Linguistics[M]. The 2nd Edition,Elsvier,2006.   
[22] Schwarzschild R.The Semantics of Comparatives and Other Degree Constructions[J]. Language and Linguistics Compass, 2008,2(2): 308-331.   
[23] Rett J. Degree Modification in Natural Language[M]. ProQuest, 2008.   
[24] 刘焱．“比”字句对比较项选择的语义认知基础[J]．上海财 经大学学报,2004,6(5):76-80.(Liu Yan.On Requirements of “Bi” Sentences for the Choice of Comparative Objects[J]. Journal of Shanghai University of Finance and Economics, 2004, 6(5): 76-80.)   
[25]何元建．现代汉语比较句式的句法结构[J]．汉语学习, 2010(5): 11-19.(He Yuanjian. Constituency and Grammatical Categories: The Case of Comparative Constructionsin Mandarin Chinese[J]. Chinese Language Learning, 2010(5): 11-19.)   
[26] Lin J. Chinese Comparativesand Their Implicational Parameters[J]. Natural Language Semantics,20o9,17(1): 1-27.   
[27] Xie Z. The Relevance of Gradability in Natural Language: Chinese and English[D]. Cornel University,2011.   
[28]李建军．比较句与比较关系识别研究及其应用[D]．重庆: 重庆大学,2011.(Li Jianjun.Research on the Identification of Comparative Sentences and Relations and Its Application [D]. Chongqing: Chongqing University,2011.)   
[29]Li X. Degreeless Comparatives: The Semanticsof Differential Verbal Comparatives in Mandarin Chinese[J]. Journal of Semantics,2013,32(1): 1-38.   
[30]宋锐，林鸿飞，常富洋．中文比较句识别及比较关系抽取 [J].中文信息学报，2009,23(2):102-107.(Song Rui,Lin Hongfei， Chang Fuyang. Chinese Comparative Sentences Identificationand Comparative RelationsExtraction[J]. Journal of Chinese Information Processing，20o9,23(2): 102-107.)   
[31] Huang X,Wan X,Yang J，et al. Learning to Identify Comparative Sentences in Chinese Text[C]. In: Proceedings of the 10th Pacific Rim International Conference on Artificial Intelligence,Hanoi, Vietnam. Springer, 2008.   
[32] 黄高辉，姚天昉，刘全升．基于CRF 算法的汉语比较句 识别和关系抽取[J]．计算机应用研究，2010，27(6): 2061-2064.(Huang Gaohui, Yao Tianfang,Liu Quansheng. Mining Chinese Comparative Sentences and Relations Based on CRF Algorithm[J]. Application Research of Computers, 2010,27(6): 2061-2064.)   
[33] Liu Q,Huang H, Zhang C,et al. Chinese Comparative Sentence Identification Based on the Combination of Rules and Statistics[C]. In: Proceedings of the 9th International Conference on Advanced Data Mining and Applications, Hangzhou, China. Springer, 2013.   
[34] 周红照，侯明午，侯敏,等．基于语义分类的比较句识别与 比较要素抽取研究[J]．中文信息学报，2014，28(3): 136-141.(Zhou Hongzhao,Hou Mingwu,Hou Min,et al. ChineseComparativeSentencesIdentificationand Comparative ElementsExtraction Based on Semantic Classification[J]. Journal of Chinese Information Processing, 2014,28(3): 136-141.)   
[35]Park D H,Blake C.Identifying Comparative Claim Sentences in Full-text Scientific Articles[C]. In: Proceedings of the Workshop on Detecting Structure in Scholarly Discourse. ACL, 2012.   
[36] He S, Yuan F, Wang Y. Extracting the Comparative Relations for Mobile Reviews[C]. In: Proceedings of the 2nd InternationalConferenceonConsumerElectronics, Communications and Networks, Yichang, China.IEEE,2012.   
[37]Kessler W,Kuhn J.Detection of Product Comparisons-How Far does an Out-of-the-Box Semantic Role Labeling System Take You?[C].In: Proceedings of the 2013 Conference on Empirical Methods on Natural Language Processing,Seattle, USA. ACL,2013.   
[38]Hou F,Li G H. Mining Chinese Comparative Sentences by Semantic Role Labeling[C]. In: Proceedings of the 2008 International ConferenceonMachineLearningand Cybernetics,Kunming,China.IEEE,2008.   
[39]Li S,Lin C Y,Song Y I,et al. Comparable Entity Mining from Comparative Questions[J]. IEEE Transactionson Knowledge and Data Engineering,2013,25(7): 1498-1509.   
[40] Shih M J,Liu D R,Hsu M L.Discovering Competitive Intelligence by Mining Changes in Patent Trends[J]. Expert Systems with Applications,2010,37(4): 2882-2890.   
[41]Zhang R, Jin Y. Identification and Transformation of Comparative Sentences in Patent Chinese-English Machine Translation[C]. In: Proceedings of the 2012 International Conference on Asian Language Processing, Hanoi, Vietnam. IEEE,2012.   
[42] BalahurA， Mihalcea R， Montoyo A． Computational Approaches to Subjectivity and Sentiment Analysis: Present and Envisaged Methods and Applications[J]. Computer Speech & Language, 2014, 28(1): 1-6.   
[43] Wang H, Yin P, Zheng L,et al. Sentiment Classification of Online Reviews: Using Sentence-based Language Model[J]. Journalof Experimental&Theoretical ArtificialIntellgence, 2014,26(1): 13-31.   
[44]Guo JL, Peng JE,Wang HC.An Opinion Feature Extraction Approach Based on A Multidimensional Sentence Analysis Model[J]. Cybernetics and Systems,2013,44(5): 379-401.   
[45]王洪伟，刘勰，尹裴,等．Web 文本情感分类研究综述[J]. 情报学报,2010,29(5):931-938.(Wang Hongwei,Liu Xie, Yin Pei,et al. Literature Review of Sentiment Clasification on Web Text[J]. Journal of the China Society for Scientific and Technical Information,2010,29(5): 931-938.)   
[46] 张朕，杜文韬，刘培玉,等．基于关联特征词表的中文比较 句识别[J]．计算机应用，2013，33(6):1591-1594.(Zhang Zhen,Du Wentao,Liu Peiyu,et al. Chinese Comparative SentencesRecognition Based on Associated Feature Vocabulary[J]. Journal of Computer Applications，2013, 33(6): 1591-1594.)   
[47] Liu B,Hu M,Cheng J. Opinion Observer: Analyzing and Comparing Opinions on the Web[C]. In: Proceedings of the 14th International Conference on World Wide Web,Chiba, Japan. ACM, 2005.   
[48] Lerman K,McDonald R.Contrastive Summarization: An Experiment with Consumer Reviews [C]. In: Proceedings of the 2009 Annual Conference of the North American Chapter of the Association for Computational Linguistics,Boulder, Colorado,USA.ACL,2009.   
[49]Paul M J,Zhai C,Girju R. Summarizing Contrastive Viewpoints in Opinionated Text[C].In:Proceedings of the 2010 Conference on Empirical Methods in Natural Language Processing,Massachusetts,USA.ACL,2010.   
[50]Fang Y,Si L,Somasundaram N,et al. Mining Contrastive Opinions on Political Texts Using Cross-perspective Topic Model [C]. In:Proceedings of the 5th ACM International Conference on Web Search and Data Mining， Seatle, Washington,USA.ACM,2012.   
[51]Sun JT,Wang X,Shen D,et al.CWS:A Comparative Web Search System[C].In:Proceedings of the 15th International Conference on World Wide Web,Edinburgh,Scotland UK. ACM,2006.   
[52]Luo G, Tang C,Tian Y.Answering Rqueries on the Web[C]. In:Proceedings of the l6th International Conference on World WideWeb,Banff,Alberta,Canada.ACM,2007.   
[53]ZhaiC,Velivelli A,Yu B.A Cross-collection Mixture Model for Comparative Text Mining[C].In:Proceedings of the 10th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining，Seattle,Washington，USA. ACM,2004.   
[54]Zhang Z,Guo C,Goes P.Product Comparison Networks for Competitive Analysis of Online Word-of-mouth[J].ACM Transactions on Management Information Systems (TMIS), 2013,3(4): 20-42.   
[55]Wang H,Wang W. Product Weakness Finder: An Opinion-aware System Through Sentiment Analysis[J]. Industrial Management & Data Systems， 2014,114(8): 1301-1320.

# 作者贡献声明：

高松：提出研究课题，阅读、整理文献，起草论文;  
王洪伟：提出研究课题，文献整理，论文最终版本修订;  
冯罡：论文最终版的梳理与文章内容的检查;  
王伟：表1-表3的修改和论文最终版本修订。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

收稿日期:2016-06-02  
收修改稿日期:2016-07-13

# Review of Comparative Opinions Mining Studies of Online Comments

Gao Song' Wang Hongwei Feng Gang² Wang Wei3   
1(School of Economics and Management, Tongji University, Shanghai 20oo92, China) ² (Saic General Motors Sales Co., LTD, Shanghai 201206, China)   
3 (College of Business Administration, Huaqiao University, Quanzhou 362021, China)

Abstract:[Objective] This paper reviews leading research methodologies and related studies on comparative opinion mining,and then provides useful guidance for future research.[Coverage] We retrieved 55 scholarly papers from the WoS，Google Scholar and CNKI. Using the keywords of “comparative opinion”，“comparative sentence” or "comparative relation”.[Methods] Based on the retrieved literature，we discussed the latest development in classification schemes,recognizing comparative sentences,extracting comparative relations and analyzing sentiments of the comparative opinion.[Results] Due to the finite sequence rules,it was dificult forus to further improve the performance ofcomparative opinion recognition techniques.Meanwhile,few studies focused on the latent comparative opinion,and the current technology could not extract the comparative elements effectively.More research was needed toconduct fine-grained sentiment analysis with comparative opinion.[Limitations] Wedid not examine dierent methods of comparative opinion mining.[Conclusions] This paper presents a framework for future studies. New research should focus on identifying and tracking potential competitors,analyzing competitive edges of products,as well as providing comparative reports for different products.

Keywords: Comparative opinionOnline reviews Sentiment analysis