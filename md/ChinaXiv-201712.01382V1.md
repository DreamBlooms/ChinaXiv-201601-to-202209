# 基于多特征融合的金融领域科研合作推荐研究

余传明」龚雨田」赵晓莉」　安璐²(中南财经政法大学信息与安全工程学院武汉 430073)2(武汉大学信息管理学院 武汉 430072)

摘要：【目的】科研合作关系是一种重要的社会网络。为了促进科研合作，提高科研生产率，对金融领域的科研合作推荐模型进行研究。【方法】建立金融领域个人、机构和区域三个层面的科研合作网络，提出一种新的融合基于邻居节点和基于路径的网络特征的科研合作推荐模型，并从个人、机构和区域三个层面进行实证检验。【结果】通过对 2000年到2014年刊载的68905篇金融领域的文章进行分析并构建科研合作网络，在个人、机构和区域三个层面上，基于特征融合的链接预测方法的AUC值分别为 $8 4 . 2 5 \%$ 、 $8 7 . 3 4 \%$ 和 $91 . 8 4 \%$ ，均高于基于邻居节点的算法和基于路径的算法的 AUC值。【局限】在进行训练集和测试集选取的时候只按时间进行切分，有待使用更多的切分方式对实验结果进行优化。【结论】本文有助于金融科研领域的个人、机构和区域寻求合作对象，为进行科研网络的研究以及科研合作推荐的学者提供新的研究方法和思路。

关键词：链接预测 科研合作推荐科研合作网络多特征融合分类号：G350

科研合作网络是一种重要的社会网络。在科研合作网络中，通常将科研合作对象(包括个人、机构和区域等)抽象成为一个节点，将科研对象之间的合作关系抽象成为一条边。链接预测(LinkPrediction)是社会网络分析的一个重要问题，其任务是根据已知的链接和节点的属性，来预测尚未连接的两个节点之间存在或产生链接的可能性[1-3]。链接预测既包括预测将来会产生的新链接(FutureLinks)，也包括预测已经存在但尚未发现的链接(ExistbutUnknownLinks)[4。基于链接预测技术进行科研合作推荐在国内外得到越来越多的关注，所采用的方法包括基于邻居节点的链接预测和基于路径的链路预测等。目前的研究存在以下问题：

(1）往往只考虑基于邻居节点或者基于路径的网络特征，很少有将两者融合在一起，而这两类算法在进行链接预测的时候往往各有优势;

(2）国内的研究大多局限于个人层面，在机构和区域层面少有涉及。

鉴于此，本文提出一种融合基于邻居节点和基于路径的网络特征的科研合作推荐模型，并从个人、机构和区域三个层面进行实证检验，以期为相关研究提供借鉴。

# 1文献回顾

在社会网络分析领域，链接预测算法通常分为三种类型，即相似度算法、最大似然模型和概率方法[5]。相似度算法通过计算节点所共有的特征来定义相似度。节点相似度越高，在推荐过程中拥有越高的优先权。最大似然模型通过最大限度地提高网络结构的可能性，根据获取的规则和参数来计算所有推荐链路的可能性。概率方法则是用一组参数组合的概率模型估计待推荐的链接概率。由于目前最大似然模型和概率方法在处理大型网络时效率仍然较低[3,6]，且本文研究的科研合作网络涉及到节点数量较多，因此采用相似度算法作为本文研究基础。

基于相似性的链接预测算法可以分为两类，即基于邻居节点的算法和基于路径的算法。基于邻居节点的链路预测方法包括共同邻居(Common Neighbors,CN)算法[7]、Admic/Adar(AA)算法[8]、Jaccard Coefficient(Jaccard)算法[9]和 Preferential Attachment(PA)算法[10]等。Chen 等较早地提出共同邻居算法，将共同邻居定义为两个节点间所共同拥有的连接节点数量[]。节点之间拥有越多的共同邻居，则越有可能建立新的链接。AA算法和Jaccard算法对CN算法进行了补充，对于稀有特征(RareFeatures)赋予更大的权重。其基本假设是，两个拥有共同稀有兴趣的人可能更易成为朋友，且其成为朋友的可能性往往正比于所共有兴趣的稀有性。与AA算法不同,PA算法则认为度数较高(即拥有更多邻居)的节点具有更高的可能性来建立新的链接,并且这种可能性与其度数的乘积成正比。基于路径的算法则包括 Shortest Path(SP)算法、Katz 算法[11]、FriendLink 算法[12]、Random Walk with Restart(RWR)算法[13]等。其中,SP算法计算节点对之间的最短路径,并认为具有较短路径的节点对之间更容易建立链接。与 SP算法仅仅考虑一条路径不同，其他算法则将多个路径综合加以考虑。例如，Katz算法将节点之间所有的路径进行累计求和；FriendLink算法则对不同长短的路径赋予不同的权重，认为那些具有独特路径(UniquePath)的节点之间更容易建立链接。

Yan等较早地将链接预测方法应用到科研合作推荐之中，将CN 算法、AA算法、Jaccard算法、PA算法和Katz算法等应用到图书馆学情报学领域的科研合作推荐之中[14]。张斌将上述多种方法应用到包括文学、历史学、法学和教育学等在内的多个学科的科研合作者推荐之中[15]。刘萍等利用LDA 主题模型进行科研合作推荐[1]。吕伟民等尝试将链接预测与机器学习结合，以提高科研合作推荐的精确度[17]。上述方法在多个领域的科研合作推荐之中取得了一定的成果，但多数研究是将基于邻居节点的算法和基于路径的算法孤立开来进行科研合作推荐。

# 2 研究方法

将4种基于邻居节点的预测方法(CN算法、Jaccard算法、AA算法和PA算法)和4种基于路径的预测方法(SP及改进最短路径算法、Katz 算法、RWR算法和FriendLink算法)作为基线方法，与本文提出的融合方法进行比较。

# 2.1基于改进最短路径的预测方法

最短路径算法作为几大经典算法之一，在计算机科学、运筹学等学科中一直是一个研究热点。之前的学者对该算法的研究解决了优化网络特征运行结构等一系列网络特征问题，推动最短路径算法越来越成熟。但是在对科研者进行合作推荐时需要考虑多个科研者的路径相似度问题，传统的最短路径算法并不能很好地解决这一问题，因此笔者考虑对最短路径算法进行改进，将科研者最短路径的相似性考虑进来，改进后的算法如公式(1)所示。

$$
P a t h \_ S i m ( i , j ) = \left[ \sum ( A , B ) \in s h o r t e s t p a t h i j \frac { 1 } { | P _ { A } \bigcap P _ { B } | } \right] - 1
$$

其中，Path_ $S i m ( i , j )$ 表示节点 $i$ 和节点 $j$ 之间的最短路径相似度， $( A , B )$ 表示合作节点对，该节点对是节点 $i$ 和节点 $j$ 的最短路径上的节点，假设节点 $i$ 到 $j$ 的一条路径为 $\{ V _ { 0 } = V _ { i } , V _ { 1 } , \cdots , V _ { l - 1 } , V _ { l } = V _ { j } \}$ ，则合作者对集合为$\{ ( V _ { i } , V _ { j } ) , ( V _ { 1 } , V _ { 2 } ) , \cdots , ( V _ { l - 2 } , V _ { l - 1 } ) , ( V _ { l - 1 } , V _ { l } ) , ( V _ { l } , V _ { j } ) \} \ \circ$ $P _ { A }$ 表示节点 $A$ 的论文集合， $| P _ { A } \cap P _ { B }$ 表示节点 $A$ 和节点$B$ 合著论文的数目。如果两个节点之间合作的次数越多，则该公式得出的结果值越大。

# 2.2基于多特征融合的预测方法

本文将多种特征得出的相似度结果进行融合，形成一致性的数据模型。由于每种特征的计算结果在数量级上可能有很大差别，直接进行融合会导致数量级较大的特征占主导地位，从而造成不准确的结果，因此在进行特征融合之前，首先将所有的相似度结果进行min-max归一化，如公式(2)所示。

$$
s c o r e _ { n o r m } = \frac { s c o r e - \operatorname* { m i n } ( s c o r e ) } { \operatorname* { m a x } ( s c o r e ) - \operatorname* { m i n } ( s c o r e ) }
$$

本文采用线性组合方法，针对各种特征的相似度

构造融合模型(Proposed Hybrid Method,PHM)，如公式(3)所示。

$$
\begin{array} { c } { { s c o r e _ { f u s e d } = \alpha \times \operatorname* { m a x } \{ r e l _ { i } ( s c o r e _ { n o r m } ) \} + ( 1 - \alpha ) \times } } \\ { { \mathrm { m a x } \{ r e l _ { j } ( s c o r e _ { n o r m } ) \} } } \end{array}
$$

其中， $s c o r e _ { f u s e d }$ 是最终的相似度，作为推荐合作的依据； $r e l _ { i } ( s c o r e _ { n o r m } )$ 表示基于路径的算法的计算结果， $\operatorname* { m a x } \{ r e l _ { i } ( s c o r e _ { n o r m } ) \}$ 表示基于路径算法中(SP及改进算法、Katz[11]算法、RWR[13]算法和FriendLink[12]算法)最优的计算结果； $r e l _ { j } ( s c o r e _ { n o r m } )$ 表示基于邻居节点的算法中(CN 算法、Jaccard 算法、AA算法和PA算法)的计算结果， $\operatorname* { m a x } \lbrace r e l _ { j } ( s c o r e _ { n o r m } ) \rbrace$ 表示基于邻居节点算法中最优的计算结果； $\alpha$ 值为基于路径算法的权重，其值在0.1和0.9之间采取步长为0.1进行动态调整。

# 3实验过程与结果分析

# 3.1 数据获取与预处理

选取中国知网期刊数据库金融类目CSSCI选项下所包含的68905篇论文(2000年-2014年)作为数据源，从个人、机构以及区域三个层次构建科研合作网络。假设有一篇论文发表于2014年，在该论文中有三个合著者authorl、author2、author3，则构建三个科研作者合作对，即<authorl,author $^ { 2 , 2 0 1 4 > }$ 、<authorl,author3,$2 0 1 4 >$ 和<author2,author3,2014>。同理，如果作者1和作者2属于机构institutionl，作者3属于机构institution2，则机构1和机构2之间形成一条科研机构合作对，形成机构对<institution1,institution2,2014>。区域层次的科研合作网络构建与此类似。

将数据集分成两部分，即训练集和测试集。其中，训练集是2000年-2013年的数据，测试集是2014年的数据。在区域合作层次，某些国外地区以及因为年代和信息不完全问题导致的无法判断所属地区的数据在实验中被剔除。所使用三个层面的数据集如表1所示。

# 3.2基于邻居节点和路径的预测方法

将科研对象(个人、机构、区域)A和B抽象为节点(下文同)，两者拥有共同的合作对象C，则A、B有可能建立新的合作。A、B 拥有的共同合作对象越多,则其建立新的合作关系的可能性越高。本文所使用的基于邻居节点的预测方法包括4种:CN算法[7];Jaccard算法[8];AA算法[9];PA算法[10]

表1实验数据集  

<html><body><table><tr><td></td><td>个人层面</td><td>机构层面</td><td>区域层面</td></tr><tr><td>总集合合作链接数：</td><td>作者数：4123 7096</td><td>机构数：3383 合作链接数： 12 336</td><td>区域数：46 合作链接数：411</td></tr><tr><td></td><td>作者数：4049 训练集合作链接数： 6119</td><td>机构数：3289 合作链接数： 11 241</td><td>区域数：46 合作链接数：400</td></tr><tr><td>测试集</td><td>作者数：1080 合作链接数：864</td><td>机构数：1109 合作链接数：1553</td><td>区域数：36 合作链接数：171</td></tr></table></body></html>

本文所采用的基于路径的预测方法包括4种：SP算法;Katz[1]算法;RWR[13]算法;FriendLink[12]算法。

# 3.3科研合作推荐模型的评价方法

采用三种评价指标验证算法的推荐性能，即平均正确率均值(Mean Average Precision，MAP)[18]和曲线下的面积(Area Under Curve,AUC)[19]。在合作者推荐的情景中，对于潜在的科研合作对象，根据推荐模型的推荐结果与现实情况进行比较，最终可能会出现4种结果，如表2所示。

表2推荐模型产生的结果矩阵  

<html><body><table><tr><td></td><td>推荐</td><td>不推荐</td></tr><tr><td>有合作</td><td>TP</td><td>FN</td></tr><tr><td>无合作</td><td>FP</td><td>TN</td></tr></table></body></html>

准确率的计算公式如公式(4)所示。

$$
P r e c i s i o n = \frac { \left| T P \right| } { \left| T P \right| + \left| F P \right| }
$$

MAP的计算公式如公式(5)所示。

$$
M A P = \frac { 1 } { n } \sum _ { u = 1 k = 1 } ^ { n } P r e c i s i o n _ { u } @ k
$$

其中, $u$ 是目标节点, $r _ { u }$ 表示与目标节点 $u$ 相关的节点，Precisionu $@ k$ 表示当向目标节点 $u$ 推荐 top $\mathbf { \nabla } \cdot \mathbf { k }$ 个节点时的准确率。MAP不仅可以说明推荐算法的准确率还能揭示推荐算法的排序能力，因此使用MAP可以更好地对推荐算法的整体性能进行评估。

此外，本文使用曲线下面积(AUC)作为评价指标。假设两个节点之间当前没有链接，但是将来会产生链接，这类链接被称为“缺失链接"；假设两个节点现在不存在链接，将来也不会产生链接，这类链接被称为“错误链接”。AUC实际上就是比较缺失链接的得分和错误链接的得分。在每次实验中分别选择一条缺失链接和一条错误链接进行分数比较，该实验独立进行 $n$ 次，假设其中有 $n ^ { \prime }$ 次缺失链接的得分大于错误链接的分数，有 $n ^ { \prime \prime }$ 次缺失链接的得分和错误链接的得分相等，则AUC值可以由公式(6)获得。AUC的取值越大，说明推荐效果越好。

$$
A U C = \frac { n ^ { \prime } + 0 . 5 \times n ^ { \prime \prime } } { n }
$$

# 3.4个人科研合作推荐的实验结果与讨论

(1）基于网络结构特征的个人科研合作推荐结果

在个人层次的科研合作推荐上，本文使用8种基于网络结构特征的链接预测算法，即基于邻居节点的算法(AA、CN、Jaccard 和PA)和基于路径的算法(FL、RWR、Katz和Path_Sim)。在Katz 算法中，设定 $\beta$ 为0.001。鉴于本文所构建的科研合作者网络最大直径为18，为了计算的可行性，设定 $k$ 等于10，即 $k { > } 1 0$ 的情况不予考虑。在FriendLink算法[12中，根据"六度分割”理论设定的1值在[2,5]，该论文最终的实验结果表明l取3时，算法能够获得最好的预测效果。鉴于此，本文设置1为3。

图1显示了4种基于邻居节点的算法结果，可以看出,AA算法在MAP和AUC上都获得了最高值;CN 算法和PA算法在AUC上的表现较为接近，CN算法的AUC值明显高于Jaccard算法；PA 算法的MAP值很低,AUC值相对要高一些。图2显示了4种基于路径的算法在各项评价指标上的表现结果,可以看出，在MAP值上RWR算法得分最高，其次是FriendLink算法,PathSim则得分最低；在AUC上RWR和PathSim的效果优于其他两个算法。

0.8   
0.6   
0.4   
0.2 0 AA CN Jaccard PA ■MAP ■AUC   
1.0   
0.8   
0.6   
0.4   
0.2 0 FL RWR Katz Path_Sim ■MAP ■AUC

(2）基于特征融合的个人科研合作推荐结果

综合各种算法在三个评价指标上的表现，最终选择AA作为基于邻居节点的算法代表，选择RWR作为基于路径的算法代表。

对融合参数 $\alpha$ 进行调整的折线图如图3所示。

![](images/a502be225c4987aef70726f2e286ab37942f8c2c5222ef0dfc9b1903dd1a21e7.jpg)  
图2基于路径特征的预测算法结果—作者层次  
图3融合参数 $\alpha$ 调整折线图—作者层次

由图3可以看出，当 $\alpha$ 取值为0.9时，融合模型的结果最好。因此取 $\alpha$ 为0.9，利用公式(3)将这两项特征融合，利用融合模型(PHM)得到最终的推荐结果，如图4所示。可以看出，无论是MAP还是AUC值，PHM模型均获得最佳性能，这验证了将多种特征融合在一起进行科研合作推荐能够获得更好效果的设想。

![](images/2178774655fadf2a0e7b943d1ebb7cb1ce91465e7a5c72e8dc21a7e648327da5.jpg)  
图1基于邻居节点的预测算法结果—作者层次  
图4各种链接预测算法的结果比较—作者层次

笔者利用从金融领域采集的2000年-2014年的论文，采用PHM模型推荐可能的合作者。表3显示了推荐的部分科研合作者。通过对科研作者的机构进行比对分析，发现许多作者对处于相同或地理上邻近的机构。例如，在第一对推荐结果中，阎庆民曾任职于中国银行业监督管理委员会(银监会)，谢平则受雇于中国投资公司(在地理位置上与银监会较为接近)。在第7对推荐结果中，胡浩和樊志刚都任职于中国工商银行。研究结果也进一步验证了Evans等关于机构和地理因素对科研合作的影响的论证[20]。后者的研究表明,受制于机构和地理位置等限制因素，科学家更倾向于建立内部机构的合作；对于作者机构以外的选择，更愿意寻求那些在地理上更为接近的机构来进行合作。模型推荐结果从机器学习的角度为科研合作往往是建立在同一个或地理上密切的机构之间的作者之上这一论点提供了新的依据。

表3PHM模型推荐的部分科研合作作者  

<html><body><table><tr><td>编号</td><td>作者1</td><td>作者2</td></tr><tr><td>1</td><td>阎庆民</td><td>谢平</td></tr><tr><td>2</td><td>陈卫东</td><td>姜波克</td></tr><tr><td>3</td><td>姜波克</td><td>张健华</td></tr><tr><td>4</td><td>阎庆民</td><td>陈卫东</td></tr><tr><td>5</td><td>阎庆民</td><td>张健华</td></tr><tr><td>6</td><td>温信祥</td><td>樊志刚</td></tr><tr><td>7</td><td>胡浩</td><td>樊志刚</td></tr><tr><td>8</td><td>王佳佳</td><td>樊志刚</td></tr><tr><td>9</td><td>张燕生</td><td>唐旭</td></tr><tr><td>10</td><td>胡浩</td><td>马素红</td></tr></table></body></html>

# 3.5机构科研合作推荐的结果与讨论

在机构层次使用8种基于网络结构特征的链接预测算法，即基于邻居节点的算法(AA、CN、Jaccard和PA)和基于路径的算法(FL、RWR、Katz 和SP)作为基线方法。各算法的参数设置与个人层次的参数设置相同。图5显示了基于邻居节点的链接预测算法对机构合作关系进行预测的结果，可以看出，综合考虑MAP和AUC值,CN算法在4种算法之中表现最好。如图6所示，在基于路径的算法中RWR算法的MAP值最高,综合表现最优；SP算法的MAP值也比较高，但是AUC值低于RWR算法；Katz算法和FriendLink算法的两项评价指标均较弱。

1.0   
0.8   
0.6 L   
0.4   
0.2 0 AA CN Jaccard PA ■MAP ■AUC   
1.0   
0.8 二三   
0.6   
0.4   
0.2 0 FL RWR Katz SP MAP ■AUC

根据上述各种算法的MAP指标比较，笔者选择RWR和CN两种算法进行融合，进行合作机构推荐。对区域层次 $\alpha$ 参数的调整如图7所示，选定 $\alpha$ 为0.7。图8显示了融合算法与其他算法进行比较的结果。可以看出，在机构层面，融合算法能够获得更好的推荐结果。

![](images/392b8b30c2193a814718e38c1186485e0dfde95e208d526716b4b396ab1a8ad7.jpg)  
图5基于邻居节点的链接预测算法结果比较-机构层次  
图6基于路径特征的预测算法结果比较-机构层次  
图7融合参数 $\alpha$ 调整折线图

利用从金融领域采集的2000 年-2014年的论文，采用PHM模型推荐可能的合作机构，部分预测的科研合作机构如表4所示。

1.0   
0.8   
0.6 H   
0.4 ■   
0.2 0 RWR CN PHM ■MAP ■AUC

从表4可以看出，PHM模型的推荐结果在一定程度上反映了科研机构在地理位置上的近邻性。例如，第3、5、6和8组的科研合作机构是隶属于同一所大学的不同学院；第7和9组则位于同一省份或者城市。除了地理因素，推荐结果还反映了研究机构之间的主题相似性。通过对研究机构的主题进行分析发现，第1、4和10组机构具有很高的主题相似性。

表4PHM模型推荐的部分科研合作机构  

<html><body><table><tr><td>编号</td><td>机构1</td><td>机构2</td></tr><tr><td>1</td><td>中国金融学会金融史专业委员会</td><td>上海市金融学会</td></tr><tr><td>2</td><td>烟台大学经管学院</td><td>东北财经大学公共管理学院</td></tr><tr><td>3</td><td>云南财经大学商学院</td><td>云南财经大学会计学院</td></tr><tr><td>4</td><td>云南大学国际关系研究院</td><td>南开大学日本研究院</td></tr><tr><td>5</td><td>复旦大学管理学院产业经济系</td><td>复旦大学管理学院财务金融系</td></tr><tr><td>6</td><td>东北财经大学应用金融学院</td><td>东北财经大学职业技术学院</td></tr><tr><td>7</td><td>西南大学地理科学学院</td><td>重庆大学建设管理与房地产学院</td></tr><tr><td>8</td><td>华东师范大学俄罗斯研究中心</td><td>华东师范大学国际关系与地区发展研究院</td></tr><tr><td>9</td><td>浙江大学理学院</td><td>浙江水利水电专科学校</td></tr><tr><td>10</td><td>中国科学技术大学公共事务学院</td><td>西南科技大学政治学院</td></tr></table></body></html>

# 3.6 区域科研合作推荐的结果与讨论

在区域层次，采用与机构合作层次相同的8种链接预测算法。在Katz算法中，设定 $\beta$ 为0.001，统计发现区域合作网络的直径为3，平均路径长度为1.5，为了计算的可行性，设定 $k$ 等于3；在FriendLink算法中,设定1等于2。

在区域层次上也使用相同的8种基于网络结构特征的链接预测算法，即基于邻居节点的算法(AA、CN、Jaccard和PA)和基于路径的算法(FL、RWR、Katz和SP)作为基线方法。

图9显示了基于邻居节点的链接预测算法对于机构合作关系预测的结果，可以看出，综合考虑MAP和AUC值,CN算法在4种算法之中表现最好,Jaccard算法和PA算法MAP值和AUC值相当,AA算法表现相对不好。如图10所示，在基于路径的算法中RWR 算法的 MAP值最高，在两个评估指标上综合表现最优;SP 算法的MAP值也比较高，但是AUC值低于RWR算法；Katz算法和FriendLink算法的两项评价指标相对较弱。

1.0   
0.8 IH   
0.6   
0.4   
0.2 0 AA CN Jaccard PA MAP ■AUC   
1.0   
0.8 I.   
0.6   
0.4   
0.2 0 FL RWR Katz SP ■MAP ■AUC

根据上述各种算法的MAP值比较，选择RWR和CN两种算法进行融合，进行合作区域推荐。融合参数$\alpha$ 的调整如图11所示，最终选定 $\alpha$ 为0.5。图12显示了融合算法与其他算法进行比较的结果。可以看出，在区域层面，融合算法能够获得更好的推荐结果。

![](images/ea24631acc230324e110a868923011d75ecf0078287fefc0c18f8601a063aa14.jpg)  
图11融合参数 $\alpha$ 调整折线图  
图12 链接预测算法比较—区域层次

1.0   
0.8 山   
0.6   
0.4   
0.2 0 RWR CN PHM ■MAP ■AUC

通过使用提出的融合方法，笔者尝试利用2000年-2014年的区域合作数据来预测的潜在的区域合作对，其结果如表5所示。

表5PHM模型推荐的部分科研合作区域  

<html><body><table><tr><td>编号</td><td>区域1</td><td>区域2</td></tr><tr><td>1</td><td>陕西</td><td>海南</td></tr><tr><td>2</td><td>河北</td><td>重庆</td></tr><tr><td>3</td><td>重庆</td><td>陕西</td></tr><tr><td>4</td><td>黑龙江</td><td>重庆</td></tr><tr><td>5</td><td>天津</td><td>广西</td></tr><tr><td>6</td><td>吉林</td><td>重庆</td></tr><tr><td>7</td><td>四川</td><td>辽宁</td></tr><tr><td>8</td><td>江苏</td><td>广西</td></tr><tr><td>9</td><td>贵州</td><td>天津</td></tr><tr><td>10</td><td>海南</td><td>江苏</td></tr></table></body></html>

从表5可以看出，在区域层面，模型的推荐结果对物理位置的近邻性的反映程度弱于作者和机构层面。通过对这些地区的GDP进行深入分析发现，模型的推荐结果更多地反映了区域之间经济状况的差异性。例如，在第1对推荐结果中，陕西的GDP为1兆7689亿9400万元人民币(2014年)，而海南则仅为3500亿7200万元人民币(2014年)。在第2对推荐结果中，河北的GDP为2兆9421亿4000万元人民币，而重庆则仅为1兆4265亿4000万元人民币。在区域层面，模型更倾向于推荐经济发展互补的区域进行合作。

# 3.7个人、机构与区域科研合作推荐的综合分析

对比4种基于邻居节点的算法(AA、CN、Jaccard和PA)和5种基于路径的算法(FL、RWR、Katz、SP和PathSim)在个人、机构以及区域层次的科研合作推荐结果，发现不同算法在各层次的科研合作网络中的推荐效果呈现多样性。例如，在基于路径的预测方法中，RWR算法在个人、机构和区域三个层次上的链接预测中均展现出最好的结果；在基于邻居节点的链接预测算法中,AA算法在区域层次表现最好,CN算法在区域和机构层次表现得最好。对比基于网络结构的方法(AA、CN、Jaccard、PA、FL、RWR、Katz、SP和Path_Sim)、融合方法(PHM)，发现无论是MAP还是AUC值，融合模型均获得最佳性能，这表明将多种特征融合在一起能够有效提升推荐效果。

本文以金融领域的科研合作网络作为实证研究对象，将科研合作对象(包括个人、机构和区域等)抽象成为一个节点，将科研对象之间的合作关系抽象成为一条边。由于网络拓扑结构在不同学科门类下的分布呈现较高的一致性[21]，与学科门类并无实质关联，所以本文提出的模型和方法理论上可以应用到其他学科。值得说明的是，个人、机构和区域三个层次的科研合作推荐研究并非各自孤立，而是彼此关联。研究个人层面的科研合作推荐有助于发现科研人员合作的现状，揭示影响合作的微观因素，例如研究主题的差异性、研究机构的同一性等；研究机构层次的科研合作推荐有助于发现科研团队合作的现状，揭示影响合作的中观因素，例如地理位置的远近等；研究区域层次的科研合作推荐则可以更多地发现影响合作产生的宏观因素，例如区域经济发展的差异性等。从推荐结果来看，在个人层面，算法倾向于推荐具有相同机构的作者进行合作；在机构层面，倾向于推荐地理位置较为靠近的机构进行合作；在区域层面，则倾向于推荐经济发展互补的区域进行合作。尽管算法推荐的结果并不能作为实际工作的指导，但上述工作对于科研人员、机构与区域选择恰当的合作对象、促进学术交流与提高科研产出仍然提供了新的思路，具有一定的启发与借鉴意义。

# 4结语

本文通过利用影响科研合作关系产生的因素网络结构特征(包括邻居节点和路径)，构建了多种特征融合的科研合作推荐方法，并对金融领域的个人、机构与区域层次的科研合作推荐进行了实证研究。在网络结构特征方面，检验了4种基于邻居节点的算法(AA、CN、Jaccard 和PA)和5种基于路径的算法(FL、RWR、Katz、SP和PathSim)对于个人、机构和区域层次的科研合作推荐的效果，发现不同算法适用于不同的网络，在各网络中的推荐效果呈现多样性。本文提出的将邻居节点特征、路径特征进行融合的推荐模型在MAP与AUC指标上都取得了比只考虑其中一项特征更好的效果，这表明融合多种特征的推荐算法优于仅仅考虑单一特征的推荐算法。对于机构和区域层次的科研合作推荐则发现对于机构合作来说，影响合作产生的主要因素是地理位置，而影响区域合作的主要因素是经济发展水平。其研究发现有助于科研人员、机构与区域选择恰当的合作对象，促进学术交流与合作。后续还将考虑更多的特征来丰富各层次实体的科研合作推荐理论与方法。

# 参考文献：

[1] DaiC,ChenL,LiB,etal.LinkPredictioninMulti-relational Networks Based on Relational Similarity[J].Information Sciences,2017,394-395:198-216.   
[2] Moradabadi B，Meybodi M R.Link Prediction Based on Temporal Similarity Metrics Using Continuous Action Set Learning Automata[J].Physica A:Statistical Mechanics & Its Applications,2016,460:361-373.   
[3] Yu C,Zhao X,AnL,etal.Similarity-basedLink Prediction in Social Networks:A Path and Node Combined Approach[J]. Journal of Information Science.DOI:10.1177/016555151666 4039.   
[4] 张斌，马费成．科学知识网络中的链路预测研究述评[J]. 中国图书馆学报，2015，41(3):30-47.(Zhang Bin，Ma Feicheng.A Review on Link Prediction of Scientific Knowledge Network[J]. Journal of Library Science in China, 2015, 41(3): 30-47.)   
[5]Lu L,Zhou T. Link Prediction in Complex Networks:A Survey[J].Physica A: Statistical Mechanicsand Its Applications, 2011,390(6): 1150-1170.   
[6]Papadimitriou A,Symeonidis P, Manolopoulos Y. Fast and Accurate Link Prediction in Social Networking Systems [J]. Journal of Systems and Software,2012, 8(5): 2119-2132.   
[7]Chen J, Geyer W, Dugan C,et al. Make New Friends,but Keep the Old:Recommending People on Social Networking Sites [C]//Proceedings of the 27th International Conference on Human Factors in Computing Systems (CHI).2009: 201-210.   
[8]Adamic L,Adar E.How to Search a Social Network [J]. Social Networks,2005,27(3): 187-203.   
[9]Tan PN, Steinbach M, Kumar V. Introduction to Data Mining [M]. The lst Edition. Boston: Addison Wesley,2005: 65-84.   
[10] Costa L da F,Rodrigues F A， Travieso G,et al. Characterization of Complex Networks: A Survey of Measurements[J].Advances in Physics,2007,56(1): 167-242.   
[11]Katz L.A New Status Index Derived from Scientometric Analysis[J].Psychometrika,1953,18(1):39-43.   
[12]Papadimitriou A,Symeonidis P,Manolopoulos Y. Fast and Accurate Link Prediction in Social Networking Systems [J]. Journal of Systems and Software,2012,8(5): 2119-2132.   
[13] Pan J, Yang H,Faloutsos C,et al.Automatic Multimedia Cross-modal Correlation Discovery [C]//Proceedings of the 10th ACM SIGKDD International Conference on Knowledge Discovery and Data Ming,Seatte,WA,USA.2004: 653-658.   
[14] YanE， GunsR. PredictingandRecommending Collaborations: An Author-,Institution-,and Coutry-level Analysis [J]. Journal of Informetrics,2014(8): 295-309.   
[15] 张斌．科研合作网络中的链路预测研究[D]．武汉：武汉大 学，2016.(Zhang Bin.Research on Link Prediction of Scientific Collaboration Network [D]. Wuhan:Wuhan University,2016.)   
[16] 刘萍，郑凯伦，邹德安．基于LDA 模型的科研合作推荐研 究[J]．情报理论与实践，2015，38(9):79-85.(Liu Ping, Zheng Kailun， Zou De'an. Research on Cooperative Recommendation Based on LDA Model[I]. Information Studies: Theory & Application,2015,38(9): 79-85.)   
[17]吕伟民，王小梅，韩涛．结合链路预测和 ET 机器学习的科 研合作推荐方法研究[J]．数据分析与知识发现,2017,1(4): 38-45.(LvWeiming， WangXiaomei， HanTao. Recommending Scientific Research Collaborators with Link Prediction and Extremely Randomized Trees Algorithm[J]. DataAnalysis and Knowledge Discovery,2017,1(4):38-45.)   
[18]Yue Y,Finley T,RadlinskiF,etal.A Support Vector Method for Optimizing Average Precision[C]//Proceedings of the 30th Annual International ACM SIGIR Conference on Research and Development in Information Retrieval,Amsterdam, Netherlands.New York:ACM,2006:271-278.   
[19]Zhou T,LvL,ZhangYC.Predicting MissingLinks viaLocal Information [J].European Physical Journal B - Condensed Matter and Complex Systems,2009,71(4):623-630.   
[20]Evans T S,Lambiotte K,Panzarasa P.Community Structure and Patterns of Scientific Collaboration in Business and Management[J].Scientometrics,2011,9(1):381-396.   
[21]巴志超，李纲，朱世伟．基于知识超网络的科研合作行为 实证研究和建模[J].情报学报，2016，35(6)：630-639.(Ba Zhichao,Li Gang,Zhu Shiwei. Empirical Study and Modeling of Scientific Cooperation Behavior Based on Knowledge Hypernetwork[J].Journal of the China Society for Scientific and Technical Information,2016,35(6):630-639.)

# 作者贡献声明：

余传明：设计并实施技术方案、技术路线，提出论文主要研究思路，优化研究方案及技术路线，论文修改；  
龚雨田，赵晓莉：实验操作，论文初稿撰写;  
安璐：提出研究思路，数据分析，论文修改。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail:yuchuanming $\displaystyle { \phantom { - } 2 0 0 3 \mathcal { Q } 1 2 6 . \mathsf { c o m } }$ □[1]余传明，龚雨田，赵晓莉，安璐.data.zip.个人、机构、区域三个层面的科研合作数据.

收稿日期:2017-05-31   
收修改稿日期:2017-07-18

# Collaboration Recommendation of Finance Research Based on Multi-feature Fusion

Yu Chuanming1Gong Yutian1Zhao Xiaoli1An Lu² (School of Information and Safety Engineering, Zhongnan University of Economics and Law, Wuhan 430073,China) 2(School of Information Management, Wuhan University, Wuhan 430072, China)

Abstract: [Objective] Research collaboration builds an important social network system.This paper proposes a new recommendation model for research collboration in finance,aiming to promote the scientific collboration and improve research productivity.[Methods]First,we established the scientificcollaboration networksat individuals, institutions and regions levels.Then, we established a recommendation modelbased onnetwork neighbors and paths. Finally,we conducted empirical studyto examine the model at three levels.[Results]A total of 68905articles published from 20o0 to 2014 on finance were analyzed to construct their research collaboration networks.The AUC values of the proposed model at individual, institutional and regional levels were $8 4 . 2 5 \%$ ， $8 7 . 3 4 \%$ ，and $91 . 8 4 \%$ respectively,which were higher than thoseofthe traditional algorithms.[Limitations]The training and testing sets were only classified by time.More segmentation methods were needed to optimize the new model.[Conclusions]This study helpsresearchers find collaboration opportunities，and provides new directions for studies on scientific collaboration networks.

Keywords: Link PredictionScientific Collaboration Recommendation Scientific Collaboration Network Multi-feature Fusion