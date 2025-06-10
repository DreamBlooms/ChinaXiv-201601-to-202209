# 基于扩展规则与统计特征的未登录词识别

曾浩1,²，詹恩奇1,²，郑建彬1,²，汪阳1,2†(1．武汉理工大学 信息工程学院，武汉 430070;2．光纤传感技术与信息处理教育部重点实验室，武汉 430070)

摘要：为提高各行业领域未登录词识别效果，提出一种基于扩展规则与统计特征的未登录词识别方法。分析行业领域未登录词构词特点，制定扩展规则，根据扩展规则对分词项进行扩展得到复合词，通过词频、互信息、邻接熵等统计特征判别复合词是否为未登录词，若为未登录词，则对其继续扩展和识别。6个行业领域和通用领域未登录词识别实验结果表明，提出方法取得了较好的未登录词识别效果，具有较好的移植性。

关键词：未登录词；扩展规则；词频；互信息；邻接熵 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.02.0140

# Unregistered word recognition based on expansion rules and statistical features

Zeng Haol,2, Zhan Enqi1,2, Zheng Jianbin1,²2, Wang Yang1, 2t (1.CollegeofInformationEngineering,Wuhan UniversityofchnlogyWuhan4o0,China;2.KeyLaboratoryofber Optic Sensing Technology &Information Processing ofMinistry of Education,Wuhan 430070, China)

Abstract: Inorder to improveunregistered wordrecognitioneffectinvarious fields,thispaperproposedanunregistered word recognition method basedon expansionrulesand statistical features.Itanalyzed word formation features ofunregistered words in various field,frmulated expansionrules,extended wordsegmentations togetcompound wordsaccordingtoexpansionrules, then determined whether compound words were unregistered words through statistical features such as word frequencymutual informationand branch entropy,if thecompound wordwasanunregisteredword,it wouldcontinuetobeexpandedand recognized.Theresultsofuregisteredwordrecognitionexperiments insix fieldsand generalfieldshowthatthe method based on expansionrules and statistical features achieves betterrecognitioneffect ofunregistered wordsandhas bettr portability.

Key Words: unregistered word; expansion rules; word frequency; mutual information; branch entropy

# 0 引言

在英语等西方语言书面表达中，句与句之间以标点符号为分隔符，词与词之间以空格为分隔符，计算机处理这些语言文本时，通过标点符号可以识别句子，通过空格可以识别词。在汉语书面表达中，虽然也以标点符号作为句子分隔符，但是词与词之间却无明显分隔符，字与字紧密相连，任何相邻的字都可能组成词，词的长度也没有限制。因此，计算机处理中文文本时，中文分词便成为了一项非常重要的基础工作。目前投入使用的各大分词器在通用领域取得了较高的分词准确率，但是其它行业领域分词效果并不理想。原因在于，各行业领域未登录词通常为长度更长语义更完整的复合词以及含有特殊字符的复合词，识别难度大。各行业领域未登录词识别准确率不高，就难以提高各行业领域文本分词准确率。因此，本文研究行业领域未登录词识别。

# 1 相关研究

未登录词指未被分词词典收录的词语以及随着时代发展而涌现出来的新词。其识别方法可分为基于规则的方法、基于统计的方法、规则与统计相结合的方法。

基于规则的方法通过构词模式、词性规则、成词概率等识别未登录词。郑家恒等人[1]研究汉语构词法，建立构词规则识别网络新词，取得了 $91 . 2 \%$ 的准确率。崔世起等人[2]通过语料库建立垃圾词典和词缀词典，结合词性规则和独立成词概率检测网络新词，也取得了较好的识别效果。基于规则的方法识别精度较高，但规则通常来源于特定领域，移植性较差，而且规则也不能概括所有的构词现象。

基于统计的方法认为词作为一个独立的整体，应具备稳定的内部结构和丰富的上下文环境，通常以词频、互信息、邻接熵等统计特征识别未登录词。韩艳等人[3以互信息提取二元组，以邻接熵判断二元组边界并对其不断扩展，识别长度更长语义更完整的未登录词。杨阳等人[4综合考虑词频、互信息、邻接熵等统计特征，提取长度不超过6的字符串，选取统计特征值均大于阈值的字符串为未登录词。李文坤等人[5]通过互信息从分词散串中筛选具有稳定结构的二元组，再对二元组进行扩展，以邻接熵判断词边界，识别长度为2-4的未登录词。天荣朋等人[以改进互信息获取具有稳定结构的2-gram和3-gram，通过计算2-gram 的邻接熵以及对3-gram 进行扩展识别未登录词。段宇锋等人[通过词频、文档频率、平均词频筛选一定范围内的候选项得到未登录词。Pang 等人[8]分析词在文档间、文档内、段落内的分布特征识别未登录词。Zhang 等人[9]以K-means 方法对微博聚类，从每一类微博中提取词频大于阈值的候选串，通过邻接度判别候选串的子串是否为未登录词。基于统计的方法不依赖于规则，移植性较好，但计算量大，且由于没有规则的约束，结果中含有大量非词字符串。

为克服规则方法和统计方法的缺点，学者们更倾向于采用规则与统计相结合的方法，提高未登录词识别效果。Liu等人[10]通过统计方法、领域词典、词性规则、前后缀规则等识别未登录词；霍帅等人[1结合词频和词法规则识别未登录词;周超等人[12]综合词频、词性规则和邻接变化数识别未登录词；杜丽萍等人[13]以改进互信息筛选二元组并对其扩展，通过词频规则和停用词规则过滤得到未登录词。

大多数研究以新闻、微博为语料，研究通用领域未登录词识别方法，识别对象主要是长度为2-4的中文未登录词，缺乏对长度更长语义更完整的复合词的识别研究。此外，对中文文本中含英文的特殊未登录词识别研究相对较少。

本文研究行业领域未登录词识别，提出一种基于扩展规则与统计特征的未登录词识别方法。以6个行业领域招聘职位为语料，分析行业领域未登录词构词特点，建立扩展规则，根据扩展规则对分词项扩展得到复合词，综合词频、互信息、邻接熵等统计特征判别复合词是否为未登录词，若为未登录词，则继续扩展和识别。

# 2 行业领域未登录词识别

通过网络爬虫从招聘网站爬取招聘职位，建立职位语料库，招聘职位如图1所示，职位语料库如表1所示。职位通常由两部分组成：结构化数据和非结构化数据。结构化数据包括职位月薪、工作地点、发布时间等字段及相应内容，这部分内容通常由若干字描述。非结构化数据包括岗位职责、任职要求、福利待遇等。职位信息主要集中在非结构化数据，因此在本文后续工作中，关于职位的处理指的是对其非结构化数据的处理。

从每个行业领域各提取50个职位，使用分词器HanLP进行分词。造成分词错误的主要因素是歧义和未登录词，因此，排除分词结果中由歧义造成的分词错误字段，剩下的分词错误字段便可认为是未登录词。6个行业领域未登录词统计如表 2所示。

职位月薪：6000-12000元/月 工作地点：北京-昌平区发布日期：2017-10-10 工作性质：全职工作经验：无经验 最低学历：本科招聘人数：10人 职位类别：算法工程师

# 岗位职责：

1.参与大数据或云架构或机器学习相关的开发；  
2.参与机器学习和人工智能的设计和开发实现；  
3.参与数学建模、数据挖掘、自然语言处理等相关模块研究；  
任职要求：  
1.统招本科及以上学历，数学、计算机科学、通信工程等相关专业  
2.熟悉C/ $\mathtt { C } + +$ /Java等开发语言，熟悉常用算法和数据结构；  
3.熟悉机器学习、深度学习，使用过相关开源框架者优先；  
福利待遇：  
1、基本工资+五险一金+餐补+法定假日+带薪年假+节日福利+生日福利+年度旅游。2、朝九晚五，五天八小时工作制，周末双休！  
工作地址：  
北京市昌平区北七家镇未来科技城南区中国电子信息安全技术研发基地B栋5层

<html><body><table><tr><td colspan="2">行业领域 职位个数</td></tr><tr><td>IT互联网</td><td>83753</td></tr><tr><td>财务/人力/行政</td><td>40189</td></tr><tr><td>销售/客服/市场</td><td>83401</td></tr><tr><td>项目/质量/管理</td><td>32788</td></tr><tr><td>房产/建筑/物业</td><td>35093</td></tr><tr><td>金融</td><td>39376</td></tr><tr><td colspan="2">表26个行业领域未登录词统计</td></tr><tr><td>行业领域</td><td>职位个数 未登录词个数</td></tr><tr><td>IT互联网</td><td>50 346</td></tr><tr><td>财务/人力/行政 50</td><td>319</td></tr><tr><td>销售/客服/市场 50</td><td>325</td></tr><tr><td>项目/质量/管理</td><td>50 275</td></tr><tr><td>房产/建筑/物业</td><td>50 302</td></tr><tr><td>金融</td><td>50 342</td></tr></table></body></html>

表2中未登录词可分为中文未登录词和英文未登录词。其中，中文未登录词约占 $90 \%$ ，主要为人名、地名、机构名、行业术语。英文未登录词约占 $10 \%$ ，主要为表示工作技能的行业术语，如“ $\mathrm { { ( c + + ) } }$ ”、“j2se”。对中文未登录词和英文未登录词的构词特点分析，如表3、4所示。

图1招聘职位表1职位语料库  
表3中文未登录词构词特点  

<html><body><table><tr><td>特点</td><td>实例</td><td>比例(%)</td></tr><tr><td>1+1</td><td>餐补，入职，电销，调优，直招</td><td>10.00</td></tr><tr><td>1+2</td><td>微商城，云产品，大数据，高并发</td><td>9.00</td></tr><tr><td>2+1</td><td>工龄奖，通讯费，招商部，季度奖</td><td>10.00</td></tr><tr><td>2+2</td><td>深度学习，淘宝客服，市场营销</td><td>35.00</td></tr><tr><td>2+3</td><td>通信运营商，注册会计师，办公自动化</td><td>15.00</td></tr><tr><td>3+2</td><td>新媒体运营，房地产开发，节假日福利</td><td>8.00</td></tr><tr><td>2+2+2</td><td>自然语言处理，语音信号处理</td><td>10.00</td></tr><tr><td>其它</td><td>计算机科学与技术，电子与通信工程</td><td>3.00</td></tr></table></body></html>

表4英文未登录词构词特点  

<html><body><table><tr><td>特点</td><td>实例</td><td>比例(%)</td></tr><tr><td>英文+中文</td><td>c 语言，ip协议</td><td>10.00</td></tr><tr><td>英文+数字</td><td>html5，spring3，stm32</td><td>50.00</td></tr></table></body></html>

<html><body><table><tr><td>英文+特殊字符</td><td>c++，c#，notepad++</td><td>5.00</td></tr><tr><td>英文+数字+英文</td><td>j2se，j2ee，p2p</td><td>10.00</td></tr><tr><td>英文+特殊字符+英文</td><td>asp.net，object-c，b/s</td><td>20.00</td></tr><tr><td>英文+特殊字符+数字</td><td>cet-4，cet-6</td><td>5.00</td></tr></table></body></html>

由表3可知，对于各行业领域中文未登录词，其一般是由2-3个中文词组成的复合词。由表4可知，英文未登录词通常也是由2-3部分组成的复合词，但它的构词特点比中文词更灵活。中文词通常只和中文词组成复合词，而英文词既可以与中文词组成复合词，如“c语言”，也可以和数字组成复合词，如“html5”，甚至还可以和特殊字符组成复合词，如“c#”。HanLP因未能识别这些未登录词，将它们错误切分为若干个分词项。例如，将“深度学习”错误切分为“深度/学习”，将“j2ee”错误切分为“j/2/ee”。因此，若能根据未登录词构词特点，将分词结果中的分词项按照一定规则进行重组，再通过某种策略过滤，便可识别各行业领域未登录词。

# 3 基于扩展规则与统计特征的未登录词识别

# 3.1扩展规则

在分析行业领域未登录词构词特点的基础上，提出基于扩展规则与统计特征的未登录词识别方法。方法中的扩展指：HanLP分词后，同一句分词结果中当前词与后一个词组成复合词。扩展规则具体如下：

Rule1当前词为停用词或者既不是中文词也不是英文词，则当前词不扩展。

Rule2当前词为中文词且不是停用词，如果后一个词也为中文词且不是停用词，则当前词扩展。

Rule3当前词为英文词且不是停用词，如果后一个词不是停用词，则当前词扩展。

Rule4扩展次数大于预设最大扩展次数，不再扩展。

上述扩展规则源于对行业领域未登录词构词特点的总结。中文词通常只和中文词组成复合词，而英文词则可以与中文词、数字、特殊字符等组成有意义的复合词。因此，上述扩展规则既可筛选符合行业领域未登录词构词特点的复合词，又可去除一些无意义的组合，提高未登录词识别效果。

扩展规则需要使用停用词词典，在自然语言处理中，停用词指只在语句中充当某种成分而对语义表达无任何贡献的字词，这些字词通常不与其它字词构成有意义的复合词，比如“了”、“的”、“不”。互联网上存在各种版本的停用词词典，这些停用词词典通常只收录通用领域的停用词。而本文研究涉及各行业领域，为提高各行业领域未登录词识别效果，对职位语料库进行分词并统计词频，从中选取词频大于1000且与其它词组成复合词概率低的词作为停用词，部分停用词及其词频如表5所示。再结合通用领域停用词词典，建立一部含1900个停用词的行业领域停用词词典。

表5停用词及其词频  

<html><body><table><tr><td>停用词</td><td>词频</td><td>停用词</td><td>词频</td><td>停用词</td><td>词频</td></tr></table></body></html>

<html><body><table><tr><td>相关</td><td>246481</td><td>熟练</td><td>80161</td><td>参与</td><td>57928</td></tr><tr><td>以上</td><td>207463</td><td>及时</td><td>74945</td><td>安排</td><td>54905</td></tr><tr><td>具有</td><td>189815</td><td>使用</td><td>72890</td><td>各项</td><td>54370</td></tr><tr><td>进行</td><td>185871</td><td>了解</td><td>70874</td><td>各种</td><td>54130</td></tr><tr><td>熟悉</td><td>176847</td><td>其他</td><td>69804</td><td>做好</td><td>52225</td></tr><tr><td>完成</td><td>168965</td><td>能够</td><td>68439</td><td>建立</td><td>45268</td></tr><tr><td>提供</td><td>142157</td><td>以及</td><td>63221</td><td>各类</td><td>43410</td></tr><tr><td>具备</td><td>126778</td><td>我们</td><td>61132</td><td>善于</td><td>35422</td></tr></table></body></html>

# 3.2统计特征

本文以词频、互信息、邻接熵作为未登录词识别的统计特征。如果扩展所得的复合词的统计特征值均大于阈值，则判定为未登录词，否则不是未登录词。

# 1）词频

未登录词作为词，首先应具备一定的出现次数。记 $f ( w )$ 表示复合词 $w$ 在语料库中出现的次数， $f ( \boldsymbol { w } )$ 越大，复合词 $w$ 成为未登录词的可能性越大。

# 2）互信息

未登录词作为词，应具备稳定的内部结构。信息论中，互信息(mutualinformation,MI)用于衡量两个信号的关联程度。因此，互信息也可衡量两个词结合的紧密程度。互信息越大，结合得越紧密，相邻词组成的复合词成为未登录词的概率越大。互信息计算公式如式（1）～（4）所示。

$$
M I ( w ) = \log ( \frac { p ( w ) } { p ( x ) p ( y ) } )
$$

$$
p ( w ) = { \frac { f ( w ) } { N } }
$$

$$
p ( x ) = { \frac { f ( x ) } { N } }
$$

$$
p ( y ) = { \frac { f ( y ) } { N } }
$$

其中： $w$ 表示由词 $x$ 和词 $y$ 组成的复合词， $M I ( \boldsymbol { w } )$ 表示 $w$ 的互信息， $p ( w )$ 、 $p ( x )$ 、 $p ( y )$ 分别表示 $w$ 、 $x$ 、 $y$ 在语料库中出现的概率， $f ( \boldsymbol { w } )$ 、 $f ( x )$ 、 $f ( y )$ 分别表示 $w$ 、 $x$ 、 $y$ 在语料库中的词频， $N$ 表示语料库中的总词数。

式(1)只适用于计算由两个词组成的复合词的互信息，为计算由多个词组成的复合词的互信息，对式(1)进行改进，改进后的互信息如式（5）所示。

$$
M M I ( w ) = \log ( \frac { p ( w ) } { A \nu g ( w _ { 1 } . . . w _ { n } ) } )
$$

$$
A \nu g ( w _ { 1 } . . . w _ { n } ) = \frac { 1 } { n - 1 } \sum _ { i = 1 } ^ { n - 1 } p ( w _ { 1 } . . . w _ { i } ) p ( w _ { i + 1 } . . . w _ { n } )
$$

其中： $w _ { 1 } \ , \ \ldots , w _ { i } \ , \ \ldots , w _ { n }$ 为组成复合词 $w$ 的 $n$ 个词，MMI(w)为改进后复合词 $w$ 的互信息， $A \nu g ( w _ { 1 } w _ { 2 } . . . w _ { n } )$ 为组成复合词 $w$ 的不同组合的平均概率。例如，对于由“自然”“语言”“处理”三个词组成的复合词“自然语言处理”，组成它的不同组合的平均概率为： $P _ { \ l }$ 自然） $P _ { \ l }$ 语言处理)和$P$ (自然语言P(处理)均值。

# 3）邻接熵

未登录词作为词，应具备丰富的上下文环境。邻接熵(branch entropy,BE)是衡量字符串成词概率的一个重要统计特征，利用信息熵(information entropy,IE)计算字符串上下文的不确定性[14]。信息论中，信息熵用于表示随机变量的不确定性均值，随机变量的信息熵越大，它的不确定性就越大。假设 $A$ 是一个离散型随机变量，取值空间为 $B$ ，当 $A$ 取值 $a \in B$ 时，概率分布为 $P ( a ) = P ( A = a )$ ，随机变量 $A$ 的信息熵如式（7）所示。

$$
I E ( A ) = - \sum _ { a \in B } p ( a ) { \log { p ( a ) } }
$$

邻接熵分为左邻接熵(left branch entropy,LBE)和右邻接熵(rightbranchentropy,RBE)。如果字符串的左邻接熵越大，其上文环境越丰富，那么它的左边界就可以确定；如果字符串的右邻接熵越大，其下文环境越丰富，那么它的右边界就可以确定；如果字符串的左邻接熵和右邻接熵均很大，其左右边界均可确定，那么它单独成词概率就越大。

本文中，复合词的左邻接指它的前一个词，右邻接指它的后一个词，所有左邻接构成左邻接集合，所有右邻接构成右邻接集合，所有不同的左邻接构成左邻接类别，所有不同的右邻接构成右邻接类别。假设复合词 $w$ 的左邻接类别为$\boldsymbol { L S } ( \boldsymbol { w } ) = \{ L _ { 1 } , L _ { 2 } , . . . , L _ { i } , . . . , L _ { n } \}$ ，右邻接类别为$R S ( w ) = \{ R _ { 1 } , R _ { 2 } , . . . , R _ { i } , . . . , R _ { m } \}$ ，其左邻接熵和右邻接熵分别如式（8）（9）所示。

$$
L B E ( w ) - \sum _ { i = 1 } ^ { n } \frac { n _ { i } } { n } \mathrm { l o g } \frac { n _ { i } } { n }
$$

$$
R B E ( w ) = - \sum _ { i = 1 } ^ { m } \frac { m _ { i } } { m } \mathrm { l o g } \frac { m _ { i } } { m }
$$

式(8)中， $L B E ( w )$ 表示 $w$ 的左邻接熵， $n$ 表示左邻接集合的大小， $n _ { i }$ 表示左邻接集合中左邻接 $L _ { i }$ 出现的次数。式(9)中，$R B E ( w )$ 表示 $w$ 的右邻接熵， $m$ 表示右邻接集合的大小， $m _ { i }$ 表示右邻接集合中右邻接 $R _ { i }$ 出现的次数。

# 3.3未登录词识别流程

基于扩展规则与统计特征的未登录词识别流程如图2所示。具体步骤如下：

a)设置最大扩展次数、词频阈值、互信息阈值、左邻接熵阈值、右邻接熵阈值。

b)将语料库按中文标点符号切分为短句。

c)使用HanLP对短句分词，遍历分词项，根据扩展规则判断当前词是否可扩展。如果当前词不可扩展，则跳过此当前词，并将后一个分词项作为当前词进行扩展和识别。如果当前词可扩展，计算扩展所得的复合词的统计特征值，若均大于阈值，则添加到未登录词集合，并对此复合词继续扩展和识别；否则，舍弃该复合词，并将后一个分词项作为当前词进行扩展和识别。

d)语料库中所有短句处理完毕，算法结束，输出未登录词集合。

![](images/6c5fa641dd3c8be131fdfd559708ca85195f8ca5b9c3fe393a8fe4049b41cc6c.jpg)  
图2基于扩展规则与统计特征的未登录词识别流程

# 4 实验及分析

# 4.1实验方法及评价标准

本文方法参数设置：最大扩展次数为2，即只识别由两个词和三个词组成的复合词。词频阈值为10；互信息阈值为3;左邻接熵阈值和右邻接熵阈值均为1。考虑到语料库中低频未登录词，本文方法将各统计特征阈值设置较低，尽可能识别出更多未登录词。

文献[4]提取长度为2\~6的字符串，若字符串的词频、互信息、左邻接熵、右邻接熵均大于阈值，则判定为未登录词。而本文方法是识别长度更长语义更完整的复合词，为了与本文方法对比，对文献[4]方法稍加修改，不再提取长度为2\~6的字符串，而是提取由相邻分词项组成的二元组和三元组，若二元组和三元组的词频、互信息、左邻接熵、右邻接熵均大于阈值，则判定为未登录词。此外，各参数值均与本文方法参数值相同。

文献[5]在分词的基础上从散串中提取互信息和词频均大于阈值的二字组合，然后通过左邻接熵和右邻接熵对二字组合进行扩展，主要识别长度为2-4的未登录词。而本文方法是识别长度更长语义更完整的复合词，为了与本文方法对比，对文献[5]方法稍加修改，不再从散串中提取二字组合，而是提取由相邻两个分词项组成的二元组，后续的扩展和识别保持和文献[5]一样。此外，各参数值均与本文方法参数值相同。

以准确率 $( P )$ 、召回率( $\mathbf { \partial } _ { R } ^ { \circ }$ 和F值（ $F$ )作为未登录词识别结果的评价标准，如式 $( 1 0 ) \sim ( 1 2 )$ 0

$$
P = \frac { \left| C \bigcap D \right| } { \left| C \right| } \times 1 0 0 \%
$$

$$
R = \frac { \left| C \bigcap D \right| } { \left| D \right| } \times 1 0 0 \%
$$

$$
F = \frac { 2 P R } { P + R }
$$

其中： $c$ 表示方法识别出的未登录词集合， $D$ 表示人工标注的未登录词集合。

# 4.2行业领域未登录词识别对比

运用文献[4,5、本文方法，识别表2中6个行业领域各50个职位中未登录词，实验结果如表6\~8所示。

表6行业领域未登录词识别准确率 $( \% )$ 对比  

<html><body><table><tr><td>行业领域</td><td>文献[4]</td><td>文献[5]</td><td>本文方法</td></tr><tr><td>IT互联网</td><td>57.14</td><td>54.38</td><td>60.26</td></tr><tr><td>财务/人力/行政</td><td>56.41</td><td>55.28</td><td>58.36</td></tr><tr><td>销售/客服/市场</td><td>54.55</td><td>51.92</td><td>60.66</td></tr><tr><td>项目/质量/管理</td><td>51.11</td><td>51.33</td><td>59.74</td></tr><tr><td>房产/建筑/物业</td><td>42.17</td><td>42.98</td><td>52.08</td></tr><tr><td>金融</td><td>53.14</td><td>53.50</td><td>54.91</td></tr></table></body></html>

表7行业领域未登录词识别召回率 $( \% )$ 对比  

<html><body><table><tr><td rowspan="2">行业领域</td><td>文献</td><td>文献[5]</td><td rowspan="2">本文方法</td></tr><tr><td>[4]</td><td></td></tr><tr><td>IT互联网</td><td>32.37</td><td>34.10</td><td>52.60</td></tr><tr><td>财务/人力/行政</td><td>27.59</td><td>27.90</td><td>51.41</td></tr><tr><td>销售/客服/市场</td><td>31.38</td><td>33.23</td><td>56.92</td></tr><tr><td>项目/质量/高级</td><td>25.10</td><td>28.00</td><td>51.27</td></tr><tr><td>房产/建筑/物业</td><td>32.12</td><td>34.44</td><td>53.97</td></tr><tr><td>金融</td><td>37.13</td><td>38.01</td><td>60.53</td></tr></table></body></html>

表8行业领域未登录词识别F值 $( \% )$ 对比  

<html><body><table><tr><td>行业领域</td><td>文献[4]</td><td>文献[5]</td><td>本文方法</td></tr><tr><td>IT互联网</td><td>41.33</td><td>42.00</td><td>56.17</td></tr><tr><td>财务/人力/行政</td><td>37.05</td><td>37.10</td><td>54.67</td></tr><tr><td>销售/客服/市场</td><td>39.84</td><td>41.00</td><td>58.73</td></tr><tr><td>项目/质量/高级</td><td>33.66</td><td>36.24</td><td>55.19</td></tr><tr><td>房产/建筑/物业</td><td>36.47</td><td>38.24</td><td>53.01</td></tr><tr><td>金融</td><td>43.72</td><td>44.45</td><td>57.58</td></tr></table></body></html>

实验结果表明，本文方法在识别行业领域未登录词中取得了较好效果，其准确率、召回率、 $F$ 值均高于另外两种方法。文献[4,5]均以微博为语料库，研究通用领域未登录词识别，虽然充分利用了词频、互信息、邻接熵等统计特征，但是缺少对规则的运用，未登录词识别结果中包含大量统计特征值大于阈值的非词字符串。例如，文献[4]方法在识别IT互联网行业未登录词中，识别结果包含“学习Java”，这是因为“学习”和“Java”在此行业语料中共现次数较高，导致“学习Java”具有较高的词频、互信息、邻接熵。本文方法不仅充分利用了词频、互信息、邻接熵等统计特征，同时还结合了扩展规则，扩展规则源于对各行业领域未登录词构词特点的总结，中文词通常只和中文词组合成复合词，而英文词可以和中文词、数字、特殊符号等组合成有意义的复合词。根据扩展规则，可以避免类似“学习Java”这样无意义组合的产生，在一定程度上提高了未登录词识别效果。

# 4.3通用领域未登录词识别对比

微博覆盖内容较广，属于通用领域数据。从COAE2014提供的数据中选取5000条微博作为实验数据，分别采用文献[4,5]本文方法识别其中的未登录词。由于难以标注微博中未登录词，故仅以准确率作为实验结果的评价标准，实验结果如表9所示。

表9通用领域未登录词识别准确率 $( \% )$ 对比  

<html><body><table><tr><td>方法</td><td>识别个数</td><td>正确个数</td><td>准确率</td></tr><tr><td>文献[4]</td><td>404</td><td>254</td><td>62.87</td></tr><tr><td>文献[5]</td><td>496</td><td>304</td><td>61.29</td></tr><tr><td>本文方法</td><td>469</td><td>336</td><td>71.64</td></tr></table></body></html>

实验结果表明，本文方法在识别微博未登录词中取得了较好效果，其准确率高于文献[4,5]方法。

# 5 结束语

本文对行业领域未登录词识别方法进行研究，通过网络爬虫技术爬取各行业领域招聘职位，在分析行业领域未登录词构词特点的基础上，制定扩展规则，根据扩展规则对分词项进行扩展得到复合词，再综合词频、互信息、邻接熵等统计特征判定复合词是否为未登录词。在6个行业领域以及通用领域进行未登录词识别实验，本文方法取得了较好的准确率、召回率和F 值，说明本文方法是有效的，具有较好的移植性。由于本文方法根据统计特征值是否均大于阈值来判断复合词是否为未登录词，判断条件过于苛刻，因此无法识别出部分统计特征值大于阈值的未登录词，例如，未能识别出词频、互信息和左邻接熵均大于阈值但右邻接熵低于阈值的未登录词。今后将针对这一问题进行改进，进一步提高未登录词识别效果。

# 参考文献：

[1]郑家恒，李文花．基于构词法的网络新词自动识别初探[J]．山西大学 学报：自然科学版,2002,25(2):115-119.(Zheng Jiaheng,Li Wenhua.A new approach to automatic recognition of web new words based on word formation [J]. Journal of Shanxi University: Natural Science Edition,2002, 25 (2): 115-119. )   
[2] 崔世起，刘群，孟遥，等．基于大规模语料库的新词检测[J]．计算机 研究与发展,2006,43 (5):927-932.(Cui Shiqi,Liu Qun,Meng Yao,etal. New word detection based on large-scale corpus [J].Journal of Computer Research and Development,2006,43(5): 927-932.)   
[3] 韩艳，林煜熙，姚建民．基于统计信息的未登录词的扩展识别方法[J]. 中文信息学报,2009,23(03):24-30,50.(Han Yan,Lin Yuxi,Yao Jianmin. Extended identification method for unregistered words based on statistical information [J]. Journal of Chinese Information Processing,20o9,23 (03): 24-30, 50.)   
[4]杨阳，刘龙飞，魏现辉．基于词向量的情感新词发现方法[J].山东大 学学报：理学版，2014,49(11):51-58.(Yang Yang,Liu Longfei,Wei Xianhui. Emotional new word discovery method based on word vector [J]. Journal of Shandong University: Science Edition,2014,49 (11): 51-58.)   
[5]李文坤,张仰森，陈若愚．基于词内部结合度和边界自由度的新词发现 [J].计算机应用研究,2015,32(8):2302-2304,2342.(LiWenkun,Zhang Yangsen, Chen Ruoyu.New word discovery based on internal conjunction degree and boundary freedom [J].Application Research of Computers,2015, 32 (8): 2302-2304,2342.)   
[6]天荣朋，许国艳，宋健．基于改进互信息和邻接熵的微博新词发现方法 [J]．计算机应用,2016,36(10):2772-2776.(Yao Rongpeng,Xu Guoyan, Song Jian.Microblog new word discovery method based on improved mutual information and adjacency entropy [J]. Journal of Computer Applications,2016,36 (10):2772-2776)   
[7]段宇锋，翰菲．基于 N-Gram 的专业领域中文新词识别研究[J].数据 分析与知识发现,2012,28(2):41-47.(Duan Yufeng,Ju Fei.Research on recognition of chinese new words in professional field based on N-Gram [J]. Data Analysis and Knowledge Discovery,2012,28 (2): 41-47.)   
[8]Pang Wenbo,Fan Xiaozhong,Gu Yijun,et al.Chinese unknown words extraction based on word-level characteristics [C]// Proc of International Conference on Hybrid Intelligent Systems.2009:361-366.   
[9] Zhang Shuai,Liu Qianren，Wang Lei.A Weibo-oriented method for unknown word extraction [C]//Proc of the 8th International Conference on Semantics, Knowledge and Grids.Washington DC: IEEE Computer Society, 2012:209-212.   
[10] Liu Qingtang,Wu Linjing, Yang Zongkai, etal.Domain phrase identification using atomic word formation in Chinese text[J].Knowledge-Based Systems, 2011,24(8): 1254-1260.   
[11]霍帅，张敏，刘奕群．基于微博内容的新词发现方法[J].模式识别与 人工智能,201427(02):141-145.(Huo Shuai, Zhang Min,Liu Yiqun. New word discovery method based on weibo content [J].Pattern Recognition and Artificial Intelligence,2014,27(2): 141-145.)   
[12]周超，严馨，余正涛．融合词频特性及邻接变化数的微博新词识别[J]. 山东大学学报：理学版,2015,50 (3):6-10.(Zhou Chao,Yan Xin,Yu Zhengtao.Micro-blog new word recognition based on word frequency feature and adjacency change number[J]. Journal of Shandong University: Science Edition,2015,50(3):6-10.)   
[13]杜丽萍，李晓戈，于根．基于互信息改进算法的新词发现对中文分词系 统改进[J]．北京大学学报：自然科学版,2016,52(1):35-40.(DuLiping, Li Xiaoge,Yu Gen. The improvement of chinese word segmentation based on new word discovery based on improved mutual information [J].Journal ofPeking University:Natural Science Edition,2016,52(1):35-40.)   
[14] Zhikov V,Takamura H,Okumura M.An efficient algorithm for unsupervised word segmentation with branching entropy and MDL [J]. Transactions ofthe Japanese Society for Artificial Intelligence,2O13,28 (3): 347-360.