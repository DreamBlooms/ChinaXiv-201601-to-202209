# 用户步行导航过程中的情感变化研究

吴丹刘畅李翼(武汉大学信息管理学院武汉 430072)

摘要：【自的】优化用户体验，提高用户对导航系统的持续使用性。【方法】采用用户实验和基于情感词典的情感分析方法，使用程度副词系数量、中文情感词汇本体、极性短语的强度计算公式等对情感短语进行量化，分析影响情感的因素及其变化规律。结果】用户在步行导航过程中的情感变化主要受到系统因素和环境因素的影响，系统更新的不及时、定位不准、环境恶劣均会对用户的情感造成影响。【局限】情感是一个复杂而且涵盖广泛的概念，仅通过文本分析可能存在不足。【结论】通过改进系统本身和增添人性化的设置提高用户对导航系统的持续使用性，为系统未来的升级提供有效参考。

关键词:步行导航情感变化情感词汇本体极性短语 情感强度计算分类号：G250

# 1引言

手机地图导航是指在手机上利用手机或者手机网络提供商实现当前位置的定位，为用户提供了一种实时可见的掌上地图，并在必要时提示用户的行走方向和目的地的距离[1]。iiMedia Research(艾媒咨询)发布的《2016年第3季度中国手机地图(导航)市场研究报告》2显示,2016年第3季度，手机地图用户累计规模已经达到6.54亿人，超6成用户使用手机地图的导航功能。高德地图和百度地图分别以 $34 . 0 \%$ 和$2 9 . 7 \%$ 的市场份额位列前两位。比达咨询发布的《2016年第3季度中国手机地图(导航)市场研究报告》显示,截至2016年10月，手机地图(导航)活跃用户规模达3.01亿，相比于第一季度(2.86亿)4增长了 $5 \%$ ，说明手机地图系统被用户持续使用，且用户使用者呈增长态势。

手机导航系统可看作是功利型信息系统[5]，对于信息系统开发者来说，系统能否被用户持续使用是影响系统成功的重要因素[]。刘鲁川等[7指出以往信息系统持续使用理论相关研究忽略了用户情感的重要作用，Zhang[8的研究表明情感在用户行为中发挥着强有力甚至核心的作用，会影响用户的信念和态度，并引导其决策和行动。Agarwal等研究表明，乐趣、沉浸等情感变量能较好地捕捉用户信息系统使用的整体体验，是解释信息系统采纳行为的重要概念。由此可知，情感对信息系统的持续使用有极为重要的影响。通过分析用户在导航过程中的情感变化可以更好地了解用户对移动导航系统交互过程的感知情况。因此，从用户情感的视角关注手机导航交互信息系统的使用行为就显得较为必要。

# 2相关研究

# 2.1情感计算相关研究

情感词[10]又称极性词、评价词语，特指带有情感倾向性的词语。情感词的判别是句子级和篇章级情感分析的基础。情感词的分类按照词汇级的倾向可分为正向(积极)和负向(消极)情感[11]，也有学者提出应包括中性词[12]。此外，徐琳宏等[13]在国外比较有影响的Ekman的6大类情感的基础上，将现有的情感资源分为乐、好、怒、袁、惧、恶、惊7大类，并在每个大类内按照情感强度和复杂度的区别细化情感大类，具体细分为21小类，构建情感词汇本体。

情感计算是以情感词的分类为基础，Jiang等[14]用7元情感的时间序列的聚类描述社会网络用户情感行为，包括表达强度和情绪维度的测量，指出情感计算的本质是人类情感表达的测量和计算，其中大多数是基于情感词汇的统计，并从文本中获得积极或消极的情感分数。情感计算的最终目的是进行文本的情感分析，Sudhakaran 等[12]指出情感分析能够推断人们对文本的看法和意见。情感分析可用于从评论中提取有价值的信息，最终使消费者和制造商受益。按照文本的颗粒度，文本情感分析可以划分为针对文本中的词、句子、篇章三个级别的识别与分析。其中，句子的情感分析是文本情感分析的核心，这是由于它是在情感词分析结果的基础上给出整句的情感分析结果[10]。张成功等[15]将极性词与修饰词组合成极性短语作为极性计算的基本单元，提出一种基于极性词典的情感分析方法。这些研究成果是本文用户情感极性和强度计算的基础。

# 2.2信息系统交互的情感研究

在信息系统交互方面，基于用户情感的研究主要集中在情感与信息系统交互的时间关系、模型构建和影响因素研究。

(1）研究用户与系统交互过程中，情感随时间的变化规律、影响因素和模型构建:Bollen 等[16]对4个月内Twitter用户播出的所有公众推文进行情感分析，提取情感的6个维度(紧张，抑郁，愤怒，活力，疲劳，混乱)，并将结果与重大公众事件(如美国总统选举等)进行比较，发现大众文化中的重大事件对公共情感有重要的和直接的影响。Jiang等[14]研究了社会网络环境中用户的多变量情感行为随时间序列的变化，提出一种结合PCA 相似性和距离相似性的新度量测量多变量情感时间序列的相似性，从而发现在社交网络中具有不同情感的用户群。杨亮等[17提出情感分布模型，分析相邻时段间情感分布语言模型间的差异，可以实现对微博热点事件的发现。

(2）研究用户在与系统交互中具体的情感体验及其影响研究，包括情感与系统满意度的关系和任务复杂度的影响等：刘鲁川等7从信息系统持续使用理论出发，研究发现用户使用微博中体验到的、频率最高的9种正向情感和7种负向情感，正向情感与用户满意度之间存在显著的正向影响关系，微博用户使用经验对正向情感与用户满意度之间的关系有正向调节作用。Nabi[18]的研究表明恐惧和愤怒会显著影响信息的获得。姜婷婷等[19]研究搜索任务复杂度对用户情感的影响，发现参与者对搜索任务的主观感知评价与其客观复杂度基本一致，任务复杂度对情感体验的影响主要体现在情感强度和情感持续时长两个方面。因此，在用户与系统交互过程中，存在正向情感和负向情感且正向情感要大于负向情感[20]

综上可知，用户的情感会受到系统本身，即内部因素的影响，具体表现为用户对系统的满意度以及持续使用；也会受情境、任务等外部因素的影响，表现为在社交系统中，用户情感受公众事件的影响，而搜索系统中则任务对用户情感及强度有明显的影响。但是，这些信息系统交互研究的场景主要是室内，主要考虑系统本身、任务设置和用户自身等影响因素下的情感变化，而关于室外场景的移动交互中的用户情感变化较少涉及。

# 3研究设计

本研究采用用户实验法，一共招募了30名大学生(包括研究生)参加步行导航实验，其中17名女生,13名男生，来自经济学、管理学、教育学、法学和工学专业，年龄为19-24岁之间。根据前期问卷的调查结果，被试者在手机地图和导航的使用经验上并无显著性差异。实验总共分为4部分，填写前测问卷、进行步行导航任务(共三个)、填写后测问卷、进行用户访谈。

经过初步统计，“从武汉销品茂商场出发步行导航到附近一家评分最高鄂菜餐馆"这一任务中，涉及到的情感词汇量较大，故仅选取此任务进行分析。为保证样本量，选取所有的30名用户为实验对象。

实验要求用户使用手机百度地图从销品茂出发步行导航到附近一家评分最高鄂菜餐馆。实验过程中，用户需采用出声思考法，对着手机录屏软件(录屏大师APP或录屏专家APP)说出自己的操作、心情等，并在任务结束后回忆实验过程；每个任务结束后填写一份问卷并勾选符合自己任务过程的情感词汇，此情感词汇是以《知网》[21]中的正负向词语为基础并综合刘鲁川等7研究中出现频度较高的情感词语，选出70个情感词汇供用户勾选。本研究的数据采集由人工提取用户的实验音频，并转录成文本。

# 3.1 研究问题

与桌面信息系统的固定性不同，移动导航系统最突出的一个特点是使用场景是移动的、动态的且需要用户的即时交互，且设备具有屏幕小巧，输人和输出能力有限[22]，在系统交互中需要用户的高度注意力，此外，用户使用导航系统时，个人处于移动环境中，也会受到外部因素的影响。因此，用户在与导航系统交互过程中，情感的变化应更为直接和明显。为了了解用户与导航信息系统交互的情感变化，本文提出以下研究问题。

(1）用户在步行导航过程中主要产生了哪些情感？这些情感是怎样变化的？(2）用户的客观情感与自评的主观情感是否一致？如不一致，有哪些差异？

# 3.2 数据分析方法

基于用户在实验过程中的实时表述文本以及实验回忆文本，分阶段进行文本分析，统计正负向短语、7大类情感短语的词频、强度值，并作出情感变化图，分析步行导航过程中用户情感的变化。

# (1）文本预处理

使用中国科学院计算技术研究所开发的汉语词法分析系统ICTCLAS①对用户的实验音频文本进行中文分词，输入用户自定义词语，手动添加口头语言、网络词汇等以提高分词结果精确度，并进一步人工调整。根据停用词表删除停用词、标点符号，根据大连理工大学信息检索研究室整理和标注的中文情感词汇本体库[13]对整理后的词汇文本进行情感词汇摘取，人工检查剩余未被摘取的部分并选取带有情感色彩的词汇，使用同义词词林扩展版[23]检测同义词，与中文情感词汇本体库中的情感词汇进行匹配，并替换。文本篇章的情感由文本中所含句子的情感决定，而每个句子的情感可以由句子中所含词或短语的情感决定[24]。因此保留情感词汇前后的程度副词和否定词，将情感词汇转换成情感短语。

# (2)强度值计算

使用葡璜等[25]的程度副词分类表及程度副词系数量L(DA)(见表1)，中文情感词汇本体库中设定的情感词汇的强度 E(PW)，结合张成功等[15]提出的极性短语的强度计算公式(见表2)，将否定词"不"的系数 E(NA)定为-0.8，对公式进行调整，计算情感短语的强度绝对值。

表1程度副词分类表  

<html><body><table><tr><td>量级</td><td>相对程度副词</td><td>绝对程度副词</td><td>系数量</td></tr><tr><td>极量</td><td>最</td><td>太、完全、爆炸、超级</td><td>1</td></tr><tr><td>高量</td><td>更、越</td><td>很、非常、特别、十分、好、 蛮、真、挺</td><td>0.75</td></tr><tr><td rowspan="2">中量</td><td>较、比较、</td><td>不大、不太、不很、没有太、 还、没有…没怎么、不是非常、没有非常、0.5</td><td></td></tr><tr><td>想象的</td><td>不是特别、不是那么、没那么</td><td></td></tr><tr><td>低量</td><td>一些 稍、略、…</td><td>有点、有些、一点、一点点</td><td>0.25</td></tr></table></body></html>

表2极性短语的极性计算  

<html><body><table><tr><td>极性短语</td><td>强度计算公式</td><td>例句</td><td>强度</td></tr><tr><td>S=PW</td><td>E(PW)</td><td>天气凉快</td><td>3</td></tr><tr><td>S=NA+PW</td><td>E(PW)XE(NA)</td><td>天气不凉快</td><td>-2.4</td></tr><tr><td></td><td>S=NA+NA+PW E(PW)XE(NA)XE(NA)</td><td>天气不是不凉快</td><td>1.92</td></tr><tr><td rowspan="2">S=DA+PW</td><td>E(PW)+[(1-E(PW))×L(DA) 若PW是正面的</td><td>天气比较凉快</td><td>2</td></tr><tr><td>E(PW)+[-1-E(PW)]×L(DA) 若PW是负面的</td><td>路上很堵</td><td>-2</td></tr></table></body></html>

将否定词"不"的系数定为-0.8而不是-1，是因为否定副词修饰中心词时不但对极性词极性置反，还会在强度上削弱，例如"不热"和"凉快"并不是等价关系[15]。对于张成功等[15]提出的极性短语的强度计算公式，本文仅使用实验中出现过的短语种类公式，因葡璜等[25]已将否定词 $\mathrm { N A ^ { + } }$ 程度副词DA设为一类程度副词，故将原公式中极性短语格式为 $\scriptstyle \mathrm { S = N A + D A + P W }$ 的公式归为 $\scriptstyle \mathbf { S } = \mathbf { D } \mathbf { A } + \mathbf { P } \mathbf { W }$ 类，不再单独计算。

# 4结果分析

# 4.1 情感短语分类

(1）情感短语的极性和强度值

词汇的情感极性是文本情感极性判断的基础。词汇、程度副词、否定词三者构成了短语。在实验过程中，30名用户共表述了261个含情感词汇的短语。根据中文情感词汇本体库中对情感词汇进行正向、负向、中性的分类，统计出在整个步行导航过程中的极性短语的频次、频率及强度值，如表3所示。正向情感短语出现了52次，负向情感短语出现了95次，负向情感短语出现的频次是正向情感短语的近两倍，正向情感短语的强度总值为140，负向情感短语的强度总值为323.5，负向情感短语的强度总值是正向情感短语的两倍多。这说明负向情感短语的平均强度值要大于正向情感短语。

表3短语极性的统计  

<html><body><table><tr><td>短语极性</td><td>频次</td><td>频率</td><td>强度值</td></tr><tr><td>正向</td><td>52</td><td>19.92%</td><td>140</td></tr><tr><td>负向</td><td>95</td><td>36.40%</td><td>323.5</td></tr><tr><td>中性</td><td>114</td><td>43.68%</td><td>311.15</td></tr><tr><td>合计</td><td>261</td><td>100.00%</td><td>774.65</td></tr></table></body></html>

(2)情感短语所属情感大类和强度值

大连理工大学信息检索研究室构建的中文情感词汇本体的情感分类体系以Ekman的6大类情感分类体系为基础，进行了更为细致的划分，将情感分为7大类 21小类。7大类情感分别是"乐”“好”“怒”、“哀”“惧”、“恶”、“惊”，如表4所示。

本实验的步行导航过程主要涉及到"乐”、“好”“哀”、“恶”4大类情感,“怒"和"惊"基本未出现。其中“恶"情感大类的短语频次最高，接近总数的一半，其次是"好”，频次接近总数的四分之一。如表4所示,“恶"情感大类的强度值也为最高，等于总强度值的$50 \%$ ，其次依然是"好”，占总强度值之比为 $2 5 \%$ 。由表3和表4得出，各情感大类的强度值占总强度值之比与其出现的频率非常接近。

表4情感类短语的统计  

<html><body><table><tr><td>情感大类</td><td>情感类</td><td>例词</td><td>频次</td><td>频次合计</td><td>频率</td><td>强度值</td><td>强度值合计</td><td>占总强度值之比</td></tr><tr><td rowspan="3">乐</td><td>快乐</td><td>高兴、愉悦、顺利、轻松</td><td>18</td><td rowspan="3">21</td><td rowspan="3">8%</td><td>53.5 5.5</td><td rowspan="3">59</td><td rowspan="3">8%</td></tr><tr><td>安心</td><td>平静</td><td>3</td><td></td></tr><tr><td>尊敬</td><td></td><td></td><td></td></tr><tr><td rowspan="5">好</td><td>赞扬</td><td>准确、及时、良好、快速</td><td>58</td><td></td><td></td><td>149</td><td></td><td></td></tr><tr><td>相信</td><td>确定</td><td></td><td>63</td><td>24%</td><td>45</td><td>194</td><td>25%</td></tr><tr><td>喜爱</td><td></td><td>5</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>祝愿</td><td>一</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>愤怒</td><td>投诉</td><td></td><td>1</td><td>0%</td><td>7</td><td></td><td>1%</td></tr><tr><td></td><td>悲伤</td><td>漫长、风吹日晒、饥肠</td><td>1 35</td><td></td><td></td><td>98.8</td><td>7</td><td></td></tr><tr><td rowspan="4">哀 惧</td><td>失望</td><td>绝望、无语、招架不住</td><td>3</td><td>38</td><td>15%</td><td>8</td><td></td><td>14%</td></tr><tr><td>疚</td><td></td><td></td><td></td><td></td><td></td><td>106.8</td><td></td></tr><tr><td>思</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>慌</td><td>急躁</td><td>4</td><td></td><td></td><td>12.6</td><td></td><td></td></tr><tr><td rowspan="4">恶</td><td>恐惧</td><td>惊吓、困难</td><td>4</td><td>8</td><td>3%</td><td>6</td><td>18.6</td><td>2%</td></tr><tr><td>羞</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>烦闷 憎恶</td><td>烦躁、心烦、疲劳、闷郁</td><td>21</td><td></td><td></td><td>65.5</td><td></td><td></td></tr><tr><td></td><td>讨厌、麻烦、不快</td><td>7</td><td></td><td></td><td>16.25</td><td></td><td></td></tr><tr><td rowspan="4">惊</td><td>贬责</td><td>炎热、阻塞、绕圈子、偏差</td><td>98</td><td>129</td><td>49%</td><td>280.25</td><td>387</td><td>50%</td></tr><tr><td>妒忌</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>怀疑</td><td></td><td></td><td></td><td></td><td>25</td><td></td><td></td></tr><tr><td>惊奇</td><td>怀疑 奇特</td><td>3</td><td>1</td><td>0%</td><td>2.25</td><td>2.25</td><td>0%</td></tr></table></body></html>

# 4.2 情感变化分析

本文将步行导航总过程分为6个阶段以描述情感的变化。第一阶段为搜索阶段，在这一阶段，用户在导航软件上使用周边服务功能查询所需目的地并选择导航指示路线；最后一阶段为到达阶段，表示用户从看到目的餐厅到最终到达的时段；中间阶段均为步行导航阶段，因导航阶段时间最长，将其按时间平均分为4个阶段：导航阶段1、导航阶段2、导航阶段3、导航阶段4。

(1)正负向情感变化由图1可知，用户的正负向情感均呈波动性变化。

正向情感在到达阶段最强，而负向情感短语与之相反，在到达阶段最弱，在导航阶段4最强。

![](images/69d36240636916a3c19603f9817168324905e6f793310e0bc4d9e31e9af76968.jpg)  
图1正负向情感的变化

从搜索阶段到整个导航阶段结束，负向情感均大于正向情感。通过计算每个阶段正负强度值的差值得出，负向情感与正向情感的差距逐渐加大，由20.35升高至65.5。而在到达阶段发生反转，正向情感大于负向情感，差值为23。

# (2)情感类短语频次及频率

由图2可知，情感类"乐"的频次在搜索阶段和整个导航阶段有轻微波动，总体稳定；情感类“好"的频次呈波动上升趋势，从导航阶段4至到达阶段上升明显；情感类“哀"和“惧"相对稳定；情感类“恶"的频次随着实验的进行呈波动上升，在到达阶段有所下降。

从搜索阶段至导航阶段结束，情感类“恶"的频次均高于其他情感类，由上文可知，实验过程中情感类“恶"和"好"的强度总值最高，计算情感类"恶"和"好”在各阶段频次的差值发现，差值从搜索阶段(4)至导航阶段4(25)逐渐增加，而在到达阶段，情感类"好"的频次达到最高。

![](images/f06e107f31f74a976436abc26888e7ea0162281e29d3c6aefff1ccf49934f094.jpg)  
图27大类情感短语频次

(3)7大类情感的变化

通过6个阶段中每个情感大类强度值之和，作出情感变化图，如图3所示。

由图3可知，在搜索阶段，除了“惧"情感类，其他的情感类强度均小于所有阶段的均值，从实验过程中的实时表述文本可以发现，在搜索查询目的地时，用户多在观察地图路线，体现的情感较少。

在整个步行导航过程中，情感类“恶"的强度值均处于较高状态，由用户的实时表述和实验回忆文本可知，这由多种因素引起。30名用户中有13名用户对GPS 定位不准确表达了不满，如用户N22在搜索阶段表述：“我决定不用它给我定位的位置，而是采取自己输入位置的形式定位，因为它给我的定位非常不准确。”13名用户表示步行路程远，对心情造成了很差的影响。12人提到天气状况不佳。7名用户遇到道路施工，因此路况恶劣，如用户N23在导航阶段1表述:“我觉得这个地图有一点不好，就是它这附近明明在修路，走路很不方便，它也不给行人提醒一下，这块走路很不方便，而且看样子这块儿已经修路很长时间了，地图也没有标出来。”2名用户表示系统给出的并非最佳路线，有绕路情况，如用户N20在导航阶段2表述：“这个百度地图也真是的，让我绕了一个圈，从那边绕过来，这边明显有个人行道。”此外，还有3名用户认为导航系统对步行时长的估算不准确;2名用户出现信号差、网速慢的情况;2名用户开启导航时默认为驾车模式，而在实验中期才发现，造成不便；2名用户因细小岔路口未给予提示导致了步行路线的偏离。因此，GPS定位不准确、步行路程远、天气状况不佳、路况恶劣等因素都会对用户的情绪造成较差的影响。

![](images/33ba2b5c5f7f1b7a6a14c76802a33b65ceddb05821e035229cb90c1a6c8cd656.jpg)  
图37大类情感的变化

从搜索阶段至导航阶段结束，情感类“恶"的强度均高于其他情感类，且“恶"与"好"的强度总值差距越来越明显，从18.3升高至63.8，情感类"好"的强度从导航阶段3至到达阶段大幅升高(97)，在到达阶段，“好"的强度超过了“恶”，达到100，成为到达阶段强度值最高的情感类。

在到达阶段，30名用户中有3人认为实验过程顺利，如用户N30评价：“挺顺畅的，旁边的路标非常明显。”3人表示心情平和,1人称实验过程很轻松，还有1人夸赞导航比较准确。因此情感类"好"大幅升高，情感类"乐"有小幅升高。但情感类“恶"的强度仍较其他情感类高，情感类“哀"的强度也达到6个阶段最高，这说明仍存在消极情绪，分析文本可知当7名用户达到目的地时，目标餐厅已经倒闭或被拆除，如用户N10表述：“这家店已经搬走了又没有牌子，找了半天也没有找到，这个百度周边更新是不是太不及时了？人家都已经搬走了。现在我很不爽，发现了一栋废弃的楼。”可见系统信息更新的不及时会导致用户浪费时间和人力寻找已不存在的目的地，而最终无法到达，对用户的情绪产生消极影响。

# 4.3主观情感与客观情感的对比

步行导航结束后，对用户进行后测问卷调查，勾选符合自己实验过程的主观心情词汇，实验过程与上文对应，分为三个阶段：搜索阶段、步行阶段、到达阶段。每个阶段可勾选1-3个词汇。使用情感词汇本体库赋值词汇强度，计算主观情感阶段正负向强度值。客观情感阶段正负向强度值，如图4所示。

由图4可知，对于负向情感，用户的客观情感与主观情感总体走势趋同，但客观总体较主观弱。这说明对于消极情绪，用户的主观感受和客观感受相似。

对于正向情感，用户的主观情感先大幅降低，后大幅升高，但客观情感持续在情感较弱的区域保持相对稳定的状态，两者之间没有交叉。这说明在实验中，用户没有表达出全部的情感，进一步说，用户不会仅仅通过口头表述的方式表现自己全部的情感。在搜索阶段，主观情感强度很高(273)，根据后测问卷调查结果可知，此阶段正向主观情感词汇频次达57，其中被勾选频率最高的词汇是"心平气和”，共计11次。而客观情感的强度值低达26.5。从用户的实时表述文本和实验回忆文本中可以看出，在搜索阶段，用户均在对导航系统进行操作，以搜寻最佳路线，很少表达自身情感。在到达阶段，主观情感也高达229，问卷中被勾选频率最高的词汇为"愉悦"(5)、“心平气和"(5)、“心静"(5)，这可能是因为实验接近尾声，用户感到胜利在望，正向情感也就随之升高。

![](images/2a3924d78f63bf7c891b10df70b00873910c11cddf0022e448125605dfc23733.jpg)  
图4主客观正负向情感变化的对比

正向情感与负向情感一致的是，无论是总体强度还是阶段强度，用户的客观情感均低于主观情感，因此在导航过程中，并非所有的情感都会通过言语表露出来。这一点在正向情感中更加明显，说明在步行导航过程中，用户更倾向于表达自身的正面情绪。

# 4.4 实验结果讨论

(1）影响情感的因素$\textcircled{1}$ 内部因素

在步行导航过程中，影响用户情感的内部因素主要体现在导航系统本身。30名用户中13名提出GPS定位不准确，7名表示信息更新不及时，3名提到时长估算不准确，2名开始导航时默认为驾车模式，2名认为导航路线并非最佳，2名处于细小岔路口时未被提示。

GPS定位不准确给用户带来了偏离正确路线的可能性;系统信息更新不及时导致用户无法找到目的地，浪费了时间成本和人力物力；同时，系统对步行时长估算的不准确会给用户带来不便，研究结果表明，用户除了想了解需要步行的距离之外，还想知道需要用多长时间；在用户想要进行步行导航时，系统默认为驾车导航，对于很少使用导航系统的人群来说，无法准确判断导航模式，可能会跟随驾车路线步行，达不到良好的用户体验；对于导航路线的规划，系统有时给出的并非最佳路线，导致用户浪费不必要的人力；而对于导航路线的提示，在不易发觉的岔路口，系统通常不会给予提示，从而造成用户走入错误道路。这些均对用户的情绪产生了负面影响。

另外，系统对于路线的及时提醒，以及实时定位准确性高，会对用户的情绪产生正面影响。在使用移动地图时，用户对移动地图的需求之一是希望系统的定位信息更加实时准确[26]。而使用移动地图的典型情境包含了步行导航情境,这与本文的研究结果是一致的。

$\textcircled{2}$ 外部因素

影响情感的外部因素主要体现在环境上，13名用户表示路程遥远，12名用户不满于天气状况，11名用户行走的路况恶劣，7名用户到达时目的餐厅已被拆除，2名用户的信号差、网速慢。

步行路程远使用户感到疲劳；天气状况不佳会导致用户产生烦躁的情绪；路况恶劣如道路施工等给用户出行带来不便；目的地已不存在则辜负了用户的期待感；信号差、网速慢导致用户无法及时走到正确的道路，同时存在走错的风险。诸如此类的因素会给用户的情绪带来负面消极的影响，同时用户对系统的持续使用性也将降低。

在旅游时，影响情感变化的因素包括环境、天气、交通等[27]。这与日常步行导航情境相同，在导航过程中，用户表达了较多对环境因素的不满，这主要是由于用户的多行为状态和室外复杂的环境造成的，步行导航情境确实是受情境因素影响较大的典型情境[26]。

(2）情感变化的规律

$\textcircled{1}$ 除了到达阶段，“恶"情感大类的强度值总是最高。

在步行导航过程中，由于用户的功能需求存在很多不被满足的情况，同时环境体验不佳，导致“恶”类情感持续处于较高水平，这说明系统还有很大的改进空间。

$\textcircled{2}$ “恶"情感大类和“好"情感大类在不同阶段的波动程度较大，且在导航阶段，它们的情感走势相同。

这两类情感波动程度大说明在步行导航过程中，用户的贬责、赞扬、烦闷类情绪不太稳定，一边行走一边查看手机地图易受到干扰，除了系统本身的影响，还经常存在外界因素的刺激。游客旅游时的情感变化与步行导航行为中的情感变化也有相似之处，在不同月份，游客"好”、“乐"和“恶”的波动程度较大[28]而其他情感的波动很小。

在导航阶段，“恶"和"好"的情感走势共同上升或下降，说明“恶"和“好”虽然是两种截然不同的情感类型，但用户在表达自己时，即使是相反的情感，也会同时表达得更多或更少。

$\textcircled{3}$ 从搜索阶段至导航阶段结束，对于情感类的强度，负 向与正向之间、“恶"与“好"之间的差值逐渐增大，而到达阶 段突然反转，正向情感值大于负向情感值，“好"的强度总值 大于“恶"的总值。

差值逐渐增大说明情绪存在累积现象，在步行导航过程中，如果不断有刺激用户负面情绪增长的因素出现，随着时间的推进，虽然情绪存在波动，但负面情绪是相对增长的，若持续下去，导致负面情绪过多，会对用户体验造成不好的影响。但实验表明，在最终到达目的地时，消极情绪降低，转而积极情绪升至最高，这是由于用户到达目的地，焦虑、烦躁的情绪得以释放，这可能说明用户的消极情感最终是可以通过附加手段进行弥补的。

# (3）对手机地图导航软件的建议

$\textcircled{1}$ 提升系统的易用性，防止消极情感的出现

前文提到，由于用户的多行为状态和室外复杂的环境，步行导航情境受情境因素影响较大[26]，除此之外，在驾车导航等情境下，用户受到情境因素的影响同样很大，在复杂的环境下，繁琐的操作更易导致用户的消极情感滋生。而近年来系统的功能呈现出越来越丰富的趋势，因此，简化操作形式很有必要。智能化记录用户常用的选项，有选择性并按照一定规律放置在界面上，减少操作次数的同时可有效避免人们对复杂的操作产生的惧怕心理，这样人性化的设计体现了对用户的关怀度，防止消极情感的产生。

$\textcircled{2}$ 加入情感化设计

创造惊喜感细节。如果用户每次进行一项行为都能得到奖励，用户就会变得对它有所期待。而如果得到的奖励完全是随机的，就会对它上瘾[29]。根据本文研究，地图软件可利用周边服务功能，与商铺合作，实行步行奖励机制，当用户使用软件完成导航时，随机奖励商家优惠卡券，帮助提升用户的积极情感。除了给予奖励措施，还可在细节设计上打动用户，比如在ChromeiOS中，如果累计的标签数超过99条，那么计算页数的小标签就会变成一个笑脸，本来被99条未读信息带来的郁闷心情也会一扫而空[30]。这同样可以应用到导航系统中。当用户步行路程超过一公里、连续驾驶超过一小时，定位光标变为可爱的笑脸，给人惊喜感，当达到目的地，设置页面特效或音效以达到鼓励的效果，这样的设计可以使用户产生一种持续的内在动机，提升系统的持续使用性。

增设生理测量功能。手机导航系统多缺少对用户情感的探测，通过生理测量法，韩国某研究所开发了可以测量用户情绪的软件[31]。类似于这样的生理测量功能也可以利用到手机导航系统中，捕捉用户在使用软件时的情绪，可以更清晰地定义系统可用性与用户情感之间的相关性，为将来系统的改进做出有效参考。

# 5结语

本文研究了用户在步行导航过程中情感的变化，发现在用户与系统交互过程中，存在正向情感和负向情感，且负向情感大于正向情感。实验主要涉及到“乐”、“好”、“哀”、“恶”4大类情感，其中“恶"情感大类最强，其次是"好”。消极情绪占主导地位，这主要由系统和环境两方面因素引起，如GPS定位不准、路程远、天气状况不佳等。且随着导航的进程，消极情绪会逐渐积累，在到达目的地之前达到峰值，到达目的地后，因寻址成功，转而积极情绪升至最高。同时，在步行导航过程中，用户的客观情感要弱于主观情感，在正向情感上尤为明显。

而情感是一个复杂且涵盖广泛的概念，本文还存在一些局限性和不足。研究采取的主要方法为用户实验和文本分析，要求用户用音频记录下自己的行为和感受，但在记录过程中，若用户专注于口述操作行为，可能会与表达实时感受有所冲突，以致于客观情感不足以代表用户内心真正的情感。对于用户主观情感和客观情感的区别与联系，后续研究可以进一步分析，并结合监督学习法，对篇章进行情感分析，或加入面部表情识别，提升研究结果的准确度。

# 参考文献：

[1] 彭志林．基于动作识别的手机地图导航系统设计[D]．上 海：复旦大学，2013．(Peng Zhilin．Design of Action Recognition Based Mobile Map Navigation System [D]. Shanghai: Fudan University,2013.)   
[2] 艾媒咨询.2016年第3季度中国手机地图(导航)市场研究报 告[R/OL]. [2016-12-25]. http:/iimedia.baijia.baidu.com/article/ 658275.(iiMediaResearch.Market ResearchReportof the 3rd Quarter of China Mobile Map (Navigation） in 2016 [R/OL]. [2016-12-25].http://iimedia.baijia.baidu.com/article/658275.)   
[3] 比达网.2016年第3季度中国手机地图(导航)市场研究报告 [R/OL]. (2016-11-06).[2016-12-25].http://www.cnit-research. com/content/201611/11430.html. (Bigdata-Research.Research Report of the 3rd Quarter of 2016 China Mobile Map (Navigation) Market [R/OL]. (2016-11-06). [2016-12-25]. http://www.cnit-research.com/content/201611/11430.html.)   
[4]比达网.2016年第1季度中国手机地图(导航)市场研究报告 [R/OL]. (2016-04-29). [2016-12-28]. http://www.bigdataresearch.cn/content/201604/256.html. (Bigdata-Research. Research Report of the lst Quarter of 20l6 China Mobile Map (Navigation） Market [R/OL]. (2016-04-29). [2016- 12-28]. http://www.cnit-research.com/content/201604/256. html.）   
[5]Heijden H. User Acceptance of Hedonic Information Systems[J]. MIS Quarterly,2004,28(4): 695-704.   
[6]BhattacherjeeA，BarfarA． Information Technology Continuance Research: Current State and Future Directions [J].Asia Pacific Journal of Information Systems,2011,21(2): 1-18.   
[7]刘鲁川，孙凯．社会化媒体用户的情感体验与满意度关系 以微博为例[J]．中国图书馆学报，2015，41(1):76-91. (Liu Luchuan,Sun Kai. Analysis of the Relationship Between Microblogging Users’Affections and Users’Satisfaction[J]. Journal of Library Science in China,2015,41(1): 76-91.)   
[8]Zhang P. The Affective Response Model: A Theoretical Framework of Affective Concepts and Their Relationships in the ICT Context[J]. Social Science Electronic Publishing, 2013,37(1): 247-274.   
[9]Agarwal R,Karahanna E. Time Flies When You're Having Fun: Cognitive Absorption and Beliefs about Information Technology Usage [J]. MIS Quarterly,2000,24(4): 665-694.   
[10]杨立公，朱俭，汤世平．文本情感分析综述[J]．计算机应 用，2013,33(6):1574-1578.(Yang Ligong, Zhu Jian, Tang Shiping.A Review of Text Sentiment Analysis[J]. Journal of Computer Applications,2013,33(6): 1574-1578.)   
[11] Hatzivassiloglou V,Mckeown K R.Predicting the Semantic Orientation of Adjectives[C]// Proceedings of the 40th Annual Meeting of the Association for Computational Linguistics. 2002: 174-181.   
[12] Sudhakaran P,Hariharan S,Lu J.Classifying Product Reviews from Balanced Datasets for Sentiment Analysis and Opinion Mining[C]// Proceedings of the 6th International ConferenceonMultimedia， ComputerGraphicsand Broadcasting.IEEE,2014: 29-34.   
[13]徐琳宏，林鸿飞，潘宇，等．情感词汇本体的构造[J]．情报 学报,2008,27(2):180-185.(Xu Linhong,Lin Hongfei,Pan Yu,et al.The Construction of Emotion Word Ontology[J]. Journal of the China Society for Scientific and Technical Information,2008,27(2): 180-185.)   
[14] Jiang Z,Bai W,Bin W U. Social Network Users Clustering Based on Multivariate Time Series of Emotional Behavior[J]. Journal of China Universities of Posts & Telecommunications,2014,21(2): 21-31.   
[15] 张成功，刘培玉，朱振方,等．一种基于极性词典的情感分 析方法[J]．山东大学学报:理学版，2012，47(3):50-53. (Zhang Chenggong,Liu Peiyu, Zhu Zhenfang，et al．A Sentiment Analysis Method Based on a Polarity Lexicon[J]. Journal of Shandong University: Natural Science,2012, 47(3): 50-53.)   
[16] Bollen J,Pepe A,Mao H.Modeling Public Mood and Emotion: Twitter Sentiment and Socio-Economic Phenomena [J].Computer Science,2009,44(12): 2365-2370.   
[17] 杨亮，林原，林鸿飞．基于情感分布的微博热点事件发现 [J]．中文信息学报，2012,26(1):84-90.(Yang Liang,Lin Yuan,Lin Hongfei.Micro-Blog Hot Events Detection Based on Emotion Distribution[J].Journal of Chinese Information Processing,2012,26(1): 84-90.)   
[18] Nabi R L.Exploring the Framing Efects of EmotionDo Discrete EmotionsDifferentially Influence Information Accessibility,Information Seeking,and Policy Preference? [J].Communication Research,2003,30(2): 224-247.   
[19]姜婷婷，贺虹虹，张正楠．搜索任务复杂度对用户情感的 影响研究[J]．图书情报知识，2016(4):74-82.(Jiang Tingting,He Honghong, Zhang Zhengnan. Impacts of Search Task Complexity on Users’Emotions[J]. Documentation, Information & Knowledge,2016(4): 74-82.)   
[20] Shah C,Pickens J，Golovchinsky G. Role-based Results Redistribution for Collaborative Information Retrieval[J]. Information Processing & Management, 2010,46(6): 773-781.   
[21]董振东，董强，郝长伶．知网的理论发现[J].中文信息学 报，2007,21(4):3-9.(Dong Zhendong,Dong Qiang，Hao Changling.Theoretical Findings of HowNet[J].Journal of Chinese Information Processing,2007,21(4): 3-9.)   
[22] Lumsden J,Brewster S.A Paradigm Shift: Alternative Interaction Techniques for Use with Mobile & Wearable Devices[C]// Proceedings of the 2003 Conference of the Centre for Advanced Studies on Collaborative Research. 2003: 197-210.   
[23]梅家驹,竺一鸣，高蕴琦，等．同义词词林(第二版)[M]. 上海：上海辞书出版社,1996.(Mei Jiaju,Zhu Yiming,Gao Yunqi,et al. TongYiCi CiLin [M]. Shanghai: Shanghai Lexicographical Publishing House,1996.)   
[24]王磊，黄河笑，吴兵，等．基于主题与三支决策的文本情 感分析[J]．计算机科学，2015，42(6):93-96.(Wang Lei, Huang Hexiao,Wu Bing，et al.Emotion Analysisof Text Based on Topics and Three-way Decisions[J].Computer Science,2015,42(6): 93-96.)   
[25]葡璜，郭姝慧．程度副词的特点范围与分类[J]．山西大学 学报：哲学社会科学版，2003，26(2):71-74.(Lin Huang, Guo Shuhui.On the Characteristics,Range and Classification ofAdverbs of Degree[J].Journal of Shanxi University: Philosophy and Social Science,2003,26(2):71-74.)   
[26]刘芳静．基于情境体验的移动地图设计研究[D]．长沙：湖 南大学,2014.(Liu Fangjing.The Research of Mobile Map Design Based on Situational Experience [D]. Changsha: Hunan University,2014.)   
[27]于静.基于微博大数据的游客情感及时空变化研究[D]．西 安：陕西师范大学，2015.（Yu Jing．Research on the Emotional and Temporal and Spatial Change of Tourists Based on Microblogging Data[D].Xi'an: Shaanxi Normal University, 2015.)   
[28]程翠琼，徐健．面向网络游记时间特征的情感分析模型[J]. 数据分析与知识发现,2017,1(2):87-95.(Cheng Cuiqiong, Xu Jian.A Sentiment Analysis Model Based on Temporal Characteristicsof Travel Blogs [J].Data Analysisand Knowledge Discovery,2017,1(2): 87-95.)   
[29]谢传伟．情感化设计在用户体验中的运用[J]．设计， 2014(2):21-22.(Xie Chuanwei.Emotional Design Methods

in User Experience Design[J].Design,2014(2):21-22.)

[30]陈驰．移动互联网软件产品(APP)中导航的情感化设计研 究[D]．武汉：湖北美术学院,2015.(Chen Chi.Research on the Emotional Design of Navigation in Mobile Internet Software Products[D].Wuhan:Hubei Institute of Fine Arts, 2015.)   
[31]Jeong S H.Suggestion of Methods for Understanding User's Emotional Changes While Using a Product[A].// Human Interface and the Management of Information.Methods, Techniques and Tools in Information Design [M]. SpringerVerlag,2007.

# 作者贡献声明：

吴丹：提出研究思路和方案，论文修改及最终版本修订;  
刘畅：数据处理与分析，论文起草;  
李翼：进行实验，收集数据。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据见期刊网络版http://www.infotech.ac.cn。[1]吴丹，刘畅，李翼．sentiment phrases.xlsx．情感短语的强度计算.

收稿日期:2017-02-08   
收修改稿日期:2017-04-14

# Changing Sentiments of Pedestrian Navigation System Users

Wu Dan Liu Chang Li Yi (School of Information Management, Wuhan University,Wuhan 430072, China)

Abstract: [Objective] This paper aims to optimize user experience and keep them using the pedestrian navigation system.[Methods] First, we collcted data from an experiment with 30 participants.Then we conducted analysis with the helpofsentiment dictionaries.Finally,weobtained influencing factors and their changing patterns with the number of degre adverbs, Chinese sentiment vocabulary Ontology and degree-calculating formula of polar phrases.Results] Wefound that users’ sentiment changed due to the systematic and environmental factors. Untimely system updates, inaccurate locations and tough environment allposed negative efects to the user's sentiments.[Limitations]Text analysis could not study the sentiments comprehensively.[Conclusions] We could optimize user experience by improving system design and adding user-friendly features, which provides direction for future developments.

Keywords: Pedestrian NavigationSentiment ChangeSentiment Vocabulary OntologyPolar Phrase Emotional Intensity Calculation