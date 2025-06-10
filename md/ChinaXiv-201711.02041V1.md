# 基于K-核塌缩序列的社会化资源推荐中核心用户发现研究

武慧娟1,² Jia Tina $ { \mathbf { D } }  { \mathbf { u } } ^ { 2 }$ 孙鸿飞’ Jannatul Fardous²1(东北电力大学经济管理学院吉林 132012)2(南澳大利亚大学信息技术与数学科学学院阿德莱德 5001)

摘要：【目的】通过对社交网站平台用户行为的分析，发现社会化小众群体中的核心用户，为社会化资源推荐服务提供参考。【方法】收集豆瓣读书用户的1208个标签，对排名前100位的标签建立标签共现矩阵，分析用户的K-核网络结构，研究用户的K-核塌缩序列的波动情况。【结果】与度数中心度、最小K-核深度值等方法相比，基于K-核塌缩序列方法发现了新的社会化小众群体中的核心用户。【局限】样本数据规模较小且局限于某领域，排序问题不能得到很好的解决，需要进一步改进K-核分析方法。【结论】本研究有利于社交网站平台的管理者制定或改进新的资源推荐策略，从而促进社交网站平台更好地发展。

关键词:核心用户社会化资源推荐社会化网络分析K-核塌缩序列分类号：G250

# 1引言

目前，互联网大数据问题日益严重，互联网每天产生的数据可以刻满约1.68亿张DVD光盘，这些数据蕴含着用户的信息行为，即“标签”，它与另外两个要素：用户和资源，已经成为社会化推荐研究的主要对象[1-2]，如何深度挖掘通过标签建立的用户关系网络，为用户提供精准的符合其兴趣偏好的资源是信息学界和管理学界等关注的研究热点之一[3]，也是未来10 年中非常重要的信息服务方向及研究课题[4]。

在社会化网络服务中，与大众化的信息需求相比，用户对资源的需求偏好分布呈长尾特征，趋向于小众化[5]，用户更需要个性化的信息。而传统的过滤式的社会化资源推荐主要集中于大众的流行的信息，很难发现小众社区中用户的需求。因此，一方面，用户需要获取深层次的个性化信息[；另一方面，用户作为偏好社区的一员，与社区中其他用户具有相同或相似的需求，因此用户与资源之间由于关联关系结构而形成和表现出小众化的结构特征，即小众社区[5]。在多维语义关系(如浏览、评论、转发等)的虚拟社交社区，社区内每个用户都有可能成为领域内的小众核心用户[7，如何利用社交平台资源，通过社会网络及复杂网络等分析方法分层识别出小众核心用户，是目前该领域内需要解决的重要问题。

# 2 相关工作

国内外与核心用户相关的研究主题主要有“意见领袖"与"小众专家”，如 Momtaz等8利用社会网络分析法综合考虑中心点、结构洞、点入度等辨别出意见领袖;Zhang等设计基于时间序列的社群抽取及意见领袖挖掘的聚类算法，并以天涯社区为例，通过实证证明该算法的可行性;Gnambs等[10对意见领袖的知识和特点建立了适度模型；王国华等[11]和顾品浩等[12]从突发性事件中对意见领袖的识别和挖掘进行分析；李纲等[13]以 MetaFilter 为样本数据来源，从中介中心性和聚类系数的角度细化小众专家，判别不同时期小众专家的用户特征及扮演的角色；陈福集等[4从意见领袖的引导作用研究其在舆情事件中的影响机制。

总体上，利用社会网络分析方法进行社会化资源推荐时，重点是如何识别关系网络中的核心用户，许多学者主要从传统的度中心性、介数中心性、近邻中心性等角度分析，部分学者从K-核值的角度分析，如He 等[15]利用K值越大，其传播能力就越强的特点，研究微博中个性化信息推荐；Kitsak 等[16认为社区中传播效率较高的用户一般存在于K-核分解中；周漩等[17]提出重要度评价矩阵识别网络中的最重要用户，分析了K-核值很小的用户的传播能力；任卓明等[18]利用邻居用户的K-核信息分析K-核值较小用户的传播能力。而很少学者从K-核塌缩序列的角度分析核心用户。本文主要利用K-核塌缩序列识别用户关系网络的总体分裂性，发现核心用户及其所在的小众社区，将其所掌握的资源推荐给其他用户。

# 3研究设计

# 3.1 基本思路

在社会化资源推荐过程中，按照核心用户的发现过程构建如图1所示的社会化资源推荐模型。首先构建用户关系网络，并对其进行K-核分解，构建用户的K-核塌缩序列，分析网络的总体分裂性，如果存在分裂，则能够发现其中的核心用户；然后进行高密度子群筛选，发现小众社区；最后将核心用户所掌握的信息推荐给小众社区的其他用户，完成社会化资源推荐。

![](images/18cd5b3f3cbb383cbb0a568ae6c5d3e1075a028f2e0d36e51f9189d8ee3400ac.jpg)  
图1基于K-核塌缩序列的社会化资源推荐模型

# 3.2 构建K-核网络结构

K-核是研究复杂网络的层次结构非常有效的方法，从中可以发现具有凝聚性的子群，它是以度数为基础的一种测量标准,Seidman[19]认为对成分结构的研究可以运用最小度标准，以便区分高、低凝聚力的领域。对一个图的"K-核"结构分析是对密度测度的一个重要补充，一个K-核是一个最大子图，其中的每个用户都至少与其他K个用户连接：每个用户的度数都至少为K。一个简单的成分就是一个"1-核”，其中所有用户都相连，因而其度数至少为1；“2-核"就是去掉所有度数为1的用户，考察剩余各个用户之间的关联结构，它是由度数为2的剩余关联用户组成的，其他的以此类推。

对于一个无向图 $\scriptstyle { \mathrm { G } = } ( \mathrm { V } , \mathrm { E } )$ ，V为用户,E为用户之间的标签共现集，在集合 $\mathsf { W } \subseteq \mathrm { V }$ 中最大的子图 $\mathrm { H } _ { \mathrm { k } } { = } ( \mathrm { W } ,$ （20E|W)就是 K-核，即对于任意的 $\mathrm { v } \in \mathrm { C }$ 度 $\mathbf { P } _ { \mathrm { H ( v ) } } { \geqslant } \mathbf { K }$ 此时网络中存在K-核[20]。K-核分解过程是层层分析网络结构，从外向内层延伸式扩展进行。它通过递归的方法逐渐移去网络中所有度值小于或等于K的用户，通过K-核的分解，能够描述网络的结构特性，揭示网络层次性质。那么，最小K-核用户为网络最外层的用户，图2是用户关系网络的K-核分解示意图。

![](images/a6dc4c513a0cbd69359ca3cc47a07ed19e5ffa445298477937405721ffae1a8f.jpg)  
图2K-核分解示意图

图2中,n位用户可以进行4种分区，其度数分别为2、3、5、6,其中6-核是最大的连通子图，包括的用户也处于核心-边缘图的核心区，其中的每个用户至少与图中的其他6个用户相连。从最大的6-核到5-核、3-核，最后是最小的2-核，大核都是小核的子图，在小核中可以完全找到大核中包含的用户。从小核到大核聚类的过程中，每级可能会产生剩余用户。

# 3.3分析K-核塌缩序列

K-核是在整个图中的一个凝聚力相对较高的区域，但它不一定是最大的凝聚子图，因为有可能存在一些相互之间联系松散，但却有很高凝聚力的区域，即网络存在总体分裂性。Seidman[19]用核塌缩序列来估计一个网络的总体分裂性，核塌缩序列主要针对的是网络中每次升级聚类产生的剩余用户，一个K-核中的点可以分为两个集合：在 $\textstyle \mathrm { K } + 1$ 中的点和不在该核中的点。Seidman[19将后一群体称为 K-剩余集合，每当K增加一个单位，从核中消失的点所占的比例可以排列为一个向量(即一行简单的数值)，可用该向量描述成分内部的局部密度结构，如果向量中的值持续增加到比较高的K值，说明网络的结构具有一致性，如果向量中的K值在较低的值出现以后持续出现了0值，说明网络中存在多个高密度区。

表1为K-核的塌缩示意图，随着K-核的逐渐塌缩，K值在从0到6增加的过程中产生了许多剩余用户，得到的核塌缩序列为:(0.05,0.10,0.15,0.00,0.10,0.15,0.45)，具体的序列变化如图3所示。

表1K-核塌缩示意图  

<html><body><table><tr><td>K值</td><td>剩余用户</td><td>剩余点 所占比例</td><td>颜色</td></tr><tr><td>0 U5</td><td></td><td>0.05</td><td>粉色</td></tr><tr><td>1</td><td>U11、U3</td><td>0.10</td><td>黑色</td></tr><tr><td>2</td><td>U2、U14、Un-2、Un</td><td>0.15</td><td>蓝色 □</td></tr><tr><td>3 0</td><td></td><td>0.00</td><td></td></tr><tr><td>4</td><td>U4、U15</td><td>0.10</td><td>灰色 □</td></tr><tr><td>5</td><td>U1、Un-1</td><td>0.15</td><td>红色 ■</td></tr><tr><td>6</td><td>U12、U13、U9、U10、U6、 U7、U8、U16、U17</td><td>0.45</td><td>浅绿色 □</td></tr></table></body></html>

![](images/4f586cb2bb59d71f843d003a7abfb0c04c5a7c6189cdccb14983a17e8cc65753.jpg)  
图3K-核塌缩序列示意图

在图3中，当K处于[0，2]时，向量值由0.05到

0.15；然后，当K为3时，向量值为0，塌缩序列有小幅变动，向量值整体上逐渐增大，所以K分别为4和5时会产生高密子群，即分别以用户(U4、U15、U1、Un-1)为中心，即子群(U4、U15、U6、U13)、(U1、U10、U12、U13、U17、Un-1)，它们是除了常见的6-核子群(U12、U13、U9、U10、U6、U7、U8、U16、U17)之外发现的小众社区。

对于第1个子群，可以将U4、U15的资源偏好推荐给小众社区中其他用户；同理，对于第2个子群，可以将U1、Un-1的资源偏好进行推荐。

# 4实验及结果分析

# 4.1 数据采集

通过豆瓣的“读书"页面对用户数据进行随机抓取，从每个用户关注的其他用户中随机选取样本，同时采用滚雪球的方式展开，共取得35位用户的资料，为方便统计，每个用户均赋予编号，同时每个用户的标签是去掉重复标注次数后得到的数量，35位用户的最终标签数是1208。

对35位用户的所有标签进行频次降序排序，截取其中排名前100位的标签，数据如表2所示，其中“文学"的频次最高，说明35位用户中喜好文学的较多。

表2豆瓣数据标签频次排序(部分)  

<html><body><table><tr><td>序号</td><td>标签</td><td>频次</td><td>序号</td><td>标签</td><td>频次</td><td>序号</td><td>标签</td><td>频次</td></tr><tr><td>1</td><td>文学</td><td>21</td><td>14</td><td>女性</td><td>6</td><td>27</td><td>香港</td><td>4</td></tr><tr><td>2</td><td>散文</td><td>12</td><td>15</td><td>社会</td><td>6</td><td>28</td><td>文化</td><td>4</td></tr><tr><td>3</td><td>历史</td><td>11</td><td>16</td><td>生活</td><td>5</td><td>29</td><td>张爱玲</td><td>3</td></tr><tr><td>4</td><td>日本</td><td>10</td><td>17</td><td>随笔</td><td>5</td><td>30</td><td>爱情</td><td>3</td></tr><tr><td>5</td><td>传记</td><td>8</td><td>18</td><td>设计</td><td>5</td><td>31</td><td>科普</td><td>3</td></tr><tr><td>6</td><td>短篇集</td><td>8</td><td>19</td><td>美国</td><td>5</td><td>32</td><td>故事</td><td>3</td></tr><tr><td>7</td><td>漫画</td><td>8</td><td>20</td><td>管理</td><td>5</td><td>33</td><td>音乐</td><td>3</td></tr><tr><td>8</td><td>外国</td><td>8</td><td>21</td><td>英国</td><td>5</td><td>34</td><td>梦想</td><td>2</td></tr><tr><td>9</td><td>小说</td><td>6</td><td>22</td><td>摄影</td><td>5</td><td>35</td><td>安妮宝贝</td><td>2</td></tr><tr><td>10</td><td>绘本</td><td>6</td><td>23</td><td>旅行</td><td>5</td><td>36</td><td>张大春</td><td>2</td></tr><tr><td>11</td><td>台湾</td><td>6</td><td>24</td><td>童话</td><td>4</td><td>37</td><td>思想史</td><td>2</td></tr><tr><td>12</td><td>电影</td><td>6</td><td>25</td><td>上海</td><td>4</td><td>38</td><td>动物</td><td>2</td></tr><tr><td>13</td><td>艺术</td><td>6</td><td>26</td><td>经济</td><td>4</td><td>39</td><td>时尚</td><td>2</td></tr></table></body></html>

将35位用户按相应的编号形成标签共现矩阵，首先按使用频次对标签集合排序，将排名前37位的标签截取成为样本数据；然后分析35位用户使用这37个标签的具体情况，按两位用户同时使用过的标签次数计算，如果有3次，则两位用户的标签共现值就为3,矩阵中对角线均设为某一值，如0，表示用户与自身之间的关系；最后形成标签共现矩阵。

# 4.2 结果分析

在Ucinet中对豆瓣数据进行K-核分析的结果如图4所示：

![](images/65e8ee1ab99329f7b50ec5cd75e44cd17f0612a749d0bce165d5bbac401c8f62.jpg)  
图4豆瓣数据的K-核分析

图4中,35位用户可以进行7种分区，其度数分别为3、4、5、7、8、9、10。10-核是最大的连通子图，包括的用户也处于核心-边缘图的核心区，其中的每个用户至少与图中的其他10个用户相连。从最大的10-核到9-核、8-核、7-核、5-核、4-核，最后是最小的3-核，大核都是小核的子图，在小核中可以完全找到大核中包含的用户。

从小核到大核聚类的过程中，每级可能会产生剩 余用户，表3为豆瓣数据中K-核的塌缩。从0到10 增加的过程中产生了许多剩余用户，得到的核塌缩序 列为：(0.06,0.09,0.00,0.11,0.11,0.14, 0.00,0.03,0.03, 0.03，0.40)，序列的变化如图5所示。

表3豆瓣数据中K-核的塌缩  

<html><body><table><tr><td>K值</td><td>剩余用户</td><td>所占比例</td></tr><tr><td>0</td><td>U29、U32</td><td>0.06</td></tr><tr><td>1</td><td>U11、U21、U23</td><td>0.09</td></tr><tr><td>2</td><td>0</td><td>0.00</td></tr><tr><td>3</td><td>U3、U5、U18、U31</td><td>0.11</td></tr><tr><td>4</td><td>U2、U20、U24、U27</td><td>0.11</td></tr><tr><td>5</td><td>U4、U14、U15、U33、U35</td><td>0.14</td></tr><tr><td>6</td><td>0</td><td>0.00</td></tr><tr><td>7</td><td>U25</td><td>0.03</td></tr><tr><td>8</td><td>U30</td><td>0.03</td></tr><tr><td>9</td><td>U1</td><td>0.03</td></tr><tr><td>10</td><td>U6、U7、U8、U9、U10、U12、U13、 U16、U17、U19、U22、U26、U28、U34</td><td>0.40</td></tr></table></body></html>

![](images/198cf4c8a5d39aab3eef295ffae185fcf02751f9c9e8991c8f3dab19f62491b0.jpg)  
图5豆瓣数据K-核塌缩序列

图5中，当K处于[0，5]区间时，向量值先从0.06下降到0，然后又上升到0.14，虽然塌缩序列有小幅变动，但向量值整体上是逐渐增大的，且增加的幅度比较小，所以此区间的塌缩序列变动可以不予考虑；但是当在K处于[5，10]区间时，向量值首先从0.14降到0，然后又增加到0.03，塌缩序列发生了一些变动，最后当K为10时，向量值突然增加到0.40，塌缩序列发生了非常大的变动。所以当K分别为7,8,9的时候，网络会产生三个高密子群，前两个高密子群均是小众社区，第一个小众社区(U30、U1、U26、U27、U2、U10)以 U30 和 U1 为核心，第二个小众社区(U25、U26、U34、U12、U16)以U25为核心，第三个高密子群(U6、U7、U8、U9、U10、U12、U13、U16、U17、U19、U22、U26、U28)以U26和U28为核心，核心用户可以将其所掌握的资源向其所在的小众社区用户推荐。

# (1）与度数中心度比较

在社会网络分析中，如果一个用户的中心度越高，就说明该用户处于网络的核心区，部分拥有较高度数中心度的用户，如表4所示：

表4豆瓣数据的度数中心度  

<html><body><table><tr><td>用户</td><td>度数中心度</td><td>用户</td><td>度数中心度</td></tr><tr><td>U26</td><td>82.353</td><td>U6</td><td>47.059</td></tr><tr><td>U28</td><td>58.824</td><td>U16</td><td>41.176</td></tr><tr><td>U10</td><td>58.824</td><td>U12</td><td>41.176</td></tr><tr><td>U13</td><td>58.824</td><td>U1</td><td>35.294</td></tr><tr><td>U9</td><td>55.882</td><td>U19</td><td>35.294</td></tr><tr><td>U22</td><td>52.941</td><td>U8</td><td>32.353</td></tr><tr><td>U17</td><td>50.000</td><td>U30</td><td>31.238</td></tr></table></body></html>

表4中，U26的度数中心度最高，说明该用户是网络中的核心用户，依次是U28、U10、U13等，此表中并没有发现U1、U30的核心地位；但是从K-核塌缩序列的角度，却发现U1、U25及U30均为小众社区的核

心用户。

(2）与最小K-核值深度比较

在社会网络分析中，存在大量的K-核值很小的用户，一般为边缘用户，从该类节点的邻居集中的最大K-核值即深度，可以发现核心用户，表5是豆瓣数据的最小K-核值(一般为0或1)的深度。

表5豆瓣数据的最小K-核值的深度  

<html><body><table><tr><td>用户</td><td>K-核值</td><td>深度</td></tr><tr><td>U29</td><td>0</td><td>0</td></tr><tr><td>U32</td><td>0</td><td>0</td></tr><tr><td>U11</td><td>1</td><td>3</td></tr><tr><td>U21</td><td>1</td><td>28</td></tr><tr><td>U23</td><td>1</td><td>4</td></tr></table></body></html>

表5中，由于U21的深度为28，即该节点的邻居集中的最大K-核值为28，结合图4，可以发现邻居U26为核心用户，但没有发现U1、U25、U28、U30的核心地位。

因此，利用社会网络分析方法在发现核心用户方面，与基于度数和最小K-核值深度方法相比，基于K-核塌缩序列的方法具有一定的优势。

# 5结语

本文在K-核的基础上提出利用K-核塌缩序列发现社会网络群体中的核心用户，对其所在的小众社区进行小众推荐，并利用豆瓣网中的读书社交平台提取样本数据，进行实证分析，结果证明基于K-核塌缩序列方法发现核心用户与度数、介数、最小K-核深度值等方法相比较具有可行性及优越性。但是，本文也存在一定的局限性，一方面仅考察了豆瓣读书用户，样本数据相对较小；另一方面由于在K-核值相同的情况下，无法对核心用户所在小众社区中其他用户进行排序。因此后期工作将不断扩大样本研究数据，进一步完善和改进K-核塌缩序列排序算法，为用户提供更好的社会化小众信息资源。

# 参考文献：

[1] Guy I, Zwerdling N,Ronen I, et al. Social Media Recommendation Based on People and Tags [C].In: Proceedings of the 33rd International ACM SIGIR Conference on Research and Development in Information

Retrieval. ACM,2010: 194-201.   
[2]Wang J,Clements M,Yang J,et al.Personalization of Tagging Systems [J]. Information Processing & Management, 2010,46(1): 58-70.   
[3]Guy I, Carmel D. Social Recommender Systems [C]. In: Proceedings of the 2Oth International Conference Companion on World Wide Web.ACM,2011:283-284.   
[4]Wortham J. Search Takes a Social Turn [EB/OL].[2016- 04-02]. http://premiumknowledge.typepad.com/files/_r1.pdf.   
[5]胡吉明，张蔓蒂．基于用户一资源关联的社会化小众推荐 模型研究[J]．情报理论与实践，2014,37(4):123-126,118. (Hu Jiming,Zhang Mandi. Research on the Social Minority RecommendationModelBasedonUser-Resources Association [J]. Information Studies: Theory & Application, 2014, 37(4): 123-126,118.)   
[6]让·梅松纳夫．群体动力学[M]．殷世才，孙兆通译．北京: 商务印书馆，1997.(Jean Maisonneuve.Group Dynamics [M].Translated by Yin Shicai,Sun Zhaotong.Beijing: The Commercial Press,1997.)   
[7]李纲，叶光辉．多源专家特征信息融合研究[J]．现代图书 情报技术,2014(4): 27-33.(Li Gang,Ye Guanghui.Research on Information Fusion for Multiple-sensor Expert Features [J].New Technology of Library and Information Service, 2014(4): 27-33.)   
[8]Momtaz N J,Aghaie A,Alizadeh S. Identifying Opinion Leaders for Marketing by Analyzing Online Social Networks [J]. International Journal of Virtual Communities and Social Netwoking,2011,3(3): 19-34.   
[9]Zhang W,He H,Cao B.Identifying and Evaluating the Internet Opinion Leader Community Based on K-clique Identifying and Evaluating the Internet Opinion Leader Community Based on K-clique Clustering [J]. Neural Computing & Applications,2014,25 (3): 595-602.   
[10] Gnambs T, Batinic B.The Roots of Interpersonal Influence: A Mediated Moderation Model for Knowledge and Traits as Predictors of Opinion Leadership [J]. Applied Psychology, 2013,62(4): 597-618.   
[11]王国华，张剑，毕帅辉．突发事件网络舆情演变中意见领 袖研究—以药家鑫事件为例[J]．情报杂志,2011,30(12): 1-5.(Wang Guohua, Zhang Jian, Bi Shuaiui. Study on Opinion Leaders of Emergenciesin Network Opinion Evolution: A Case Study of Yao Jiaxin Event [J]. Journal of Intelligence,2011,30(12): 1-5.)   
[12]顾品浩，蒋冠，突发性公共事件中的网络意见领袖分析 以"杨达才事件"为例[J]．情报杂志,2013,32(5):20-24. (Gu Pinhao,Jiang Guan．Analysis on Network Opinion Leaders in Public Emergencies——A Case Study of YANG Dacai Event [J]. Journal of Intelligence,2013,32 (5): 20-24.)   
[13]李纲，叶光辉，张岩．“小众专家"特征识别——基于 MetaFilter的实证分析[J].现代图书情报技术，2015(6): 71-77.(Li Gang，Ye Guanghui, Zhang Yan．Feature Recognition of Niche Expert—-Empirical Analysis Based on MetaFilter Dataset [J].New Technology of Library and Information Service,2015(6): 71-77.)   
[14]陈福集，陈婷．舆情突发事件演化探析——基于意见领袖 引导作用视角[J]．情报资料工作，2015(2):23-28.(Chen Fuji,Chen Ting.Research on Public Opinion Emergencies Evolution: Based on the Perspective of Opinion Leaders Guiding Role [J]. Information and Documentation Services, 2015(2): 23-28.)   
[15]He Y，Tan J. Study on SINA Micro-blog Personalized Recommendation Based on Semantic Network[J].Expert Systems with Applications,2015,42(10): 4797-4804.   
[16] Kitsak M,Gallos L K,Havlin S,et al. Identification of Influential Spreaders in Complex Networks [J].Nature Physics,2010,6(11): 888-893.   
[17]周漩，张凤鸣，李克武，等．利用重要度评价矩阵确定复 杂网络关键节点[J]．物理学报，2012,61(5):05020101- 05020107.(Zhou Xuan, Zhang Fengming,Li Kewu,et al. Finding Vital Node by Node Importance Evaluation Matrix in Complex Networks [J].Acta Physica Sinica,2012,61(5): 05020101-05020107.)   
[18]任卓明，刘建国，邵凤，等．复杂网络中最小K-核节点的 传播能力分析[J]．物理学报，2013，62(10):10890201- 10890206.(Ren Zhuoming,Liu Jianguo, Shao Feng,et al. Analysis of the Spreading Influence of the Nodes with Minimum K-shell Value in Complex Networks [J]. Acta Physica Sinica,2013,62(10):10890201-10890206.)   
[19] Seidman S B.Network Structure and Minimum Degree [J]. Social Networks,1983,5(3):269-287.   
[20]宗刚，赵晓东．基于K-核分析的中国啤酒品牌二分网络结构 研究[J]．北京工业大学学报，2013，39(6):936-940.(Zong Gang， Zhao Xiaodong. Construction of Boolean Bipartite Network for Chinese Beer Brands Based on K-Core Analysis [J]. Journal of Beijing University of Technology，2013,39(6): 936-940.)

# 作者贡献声明：

武慧娟：提出研究思路，方法设计与实现，撰写论文;  
JiaTinaDu：提出论文的修改建议;  
孙鸿飞：数据分析;  
JannatulFardous:数据收集。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail:413170720@qq.com。   
[1]武慧娟,Jia Tina Du,孙鸿飞,Jannatul Fardous.usercollection.   
xls.用户数据集合.   
[2]武慧娟,Jia Tina Du,孙鸿飞,Jannatul Fardous.tagmatrix.xls.   
标签共现矩阵.   
[3]武慧娟,Jia Tina Du,孙鸿飞,Jannatul Fardous.networkdensiny.   
doc.网络密度图.   
[4]武慧娟,Jia Tina Du,孙鸿飞,Jannatul Fardous.structure.doc．核 心边缘结构图.

收稿日期:2016-04-15   
收修改稿日期:2016-05-09

# Identifying Core Users in Social Resource Recommendation System with K-shell Collapse Sequences

Wu Huijuan1,²Jia Tina Du²Sun Hongfei'Jannatul Fardous² 1(School of Economics & Management, Northeast Dianli University, Jilin 132012, China) 2(Information Technology and Mathematical Sciences, Universityof South Australia,Adelaide 50o1,Australia)

Abstract:[Objective]This study aims to identifythecore users in social minority groupswith the helpof social network behavior analysis technique,and then improve the service of social resources recommendation.[Methods] First, wecollected1,208user tags from the websiteofDouban Reading,and built co-occurrence matrix for the top 100 tags.Second, we analyzed these users'K-shellnetwork structure and then investigated its collapse sequences volatility. [Results] We found new core users from the social minority group using the proposed method.[Limitations] The sample data size was relatively small and from only one specific field.The K-shell analysis method needed to be modifiedto improve the result ranking.[Conclusions]The proposed method could help the social media administrators develop new resources recommendation strategy, and promote the development of social networking systems.

Keywords: Core userSocial resource recommendationSocial network analysisK-shell collapse sequences

# Innovative推出KnowledgeBase1.0版，助力图书馆电子内容生命周期管理

全球领先的图书馆自动化软件提供商 Innovative Interfaces 于近日推出 Knowledge Base 1.0版，助力图书馆内容生命周期的综合管理和馆藏内容的精确视图。

Knowledge Base是基于Web 的应用程序，拥有一个直观的、现代化的用户界面，以及高度优化的索引，使得其图书馆用户受益于更高效的工作流和简化的内容生命周期管理。Knowledge Base 1.0版增强了馆藏管理的用户体验，提供电子订阅内容的实时发现和访问。通过整合整个图书馆系统的馆藏资源和内容资源，图书馆员工能够快速识别所有资源的覆盖情况。Knowledge Base 的独特之处在于其识别所有内容的能力，不论是来自哪家内容供应商的内容，都能通过预测搜索功能在一个集中的地方进行识别。现在，工作人员将能够通过输人关键词检索范围更广的数据库，查看图书馆已经订阅的或是没有订阅的条目。Knowledge Base为图书馆提供:

(1）电子资源管理(Electronic Resource Management,ERM):更加有效的馆藏馆理;  
(2)OpenURL链接解析器：全文实时访问;  
(3）发现功能：确保读者能够方便快捷地找到他们所需要的资源。

考虑到出版商添加或删除内容的频率,Knowledge Base 在更精确的条目覆盖度更新上投人了许多精力。Innovative已显著减少图书馆员工意识到条目名称修改的时间延迟，将行业标准时间延迟从一个月缩短到两周。与Innovative 所提供的其他产品一样,Knowledge Base 是建立在一个安全的、大规模的、可扩展的云平台基础上，这正是 Innovative致力于整合多源信息的使命的写照。Knowledge Base 1.0版现可供所有部署了Sierra 解决方案的图书馆使用。

(编译自：https://www.ii.com/news-events/pr/innovative-launches-knowledge-base-release-10-electronic-content-lifecycle management)

(本刊讯)