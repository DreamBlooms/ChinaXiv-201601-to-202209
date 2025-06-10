# 基于局部划分的匿名算法研究

王芳1，余敦辉1,2，张万山1,2

(1．湖北大学 计算机与信息工程学院，武汉 430062;2．湖北省教育信息化工程技术研究中心，武汉 430062)

摘要：针对泛化会造成数据信息损失量较大，且这缺陷会随数据维度变大而越明显的问题，提出一种基于局部划分的匿名算法。在确保 $\mathbf { k } \cdot$ 匿名和1-匿名的前提下，基于敏感属性栏值约束和记录间距离将数据表横向分成若干个桶，然后对每个桶基于属性间的关联纵向分成多栏，最后对同一桶中各栏中的数据进行随机重排。实验结果表明，在处理高维数据时，与LGAA-CP算法相比，信息损失量减少了 $47 \%$ 到 $1 8 3 \%$ ，关联关系保留率提高了 $2 4 \% { \sim } 1 1 8 \%$ 。与Slicing算法相比，信息损失量相差在 $1 . 5 \%$ 之内，关联关系保留率提高了 $8 . 9 \%$ 到 $2 2 . 8 \%$ 。通过分析，该算法在同时确保高维数据的隐私保护能力和数据可用性方面是有效的。

关键词：数据发布隐私保护；k-匿名；1-匿名；敏感属性栏值约束 中图分类号：TP309.2 doi:10.3969/j.issn.1001-3695.2018.05.0352

# Anonymous algorithm based on local partition

Wang Fang1, Yu Dunhui1,2†, Zhang Wanshan1, 2 (1.CollegeofComputer&InformationEngineeringHubei University,Wuhan43o62,China;2.HubeiEducationInfortio Engineering&Technology Center,Wuhan430062,China)

Abstract: Aimingatthe problem thatthe generalizationcausesalargeamountoflossofdatainformation,andthis defect would become more obvious as thedata dimension becomes larger,this paper proposed an anonymous algorithm based on local partitioning.Toensuringk-anonymityand-diversityasedonthevalueconstraintofsensitiveatributecolumnandthedistance betweenrecords,horzontalldivide thedatatableintoseveralbuckets.Andthenbasedontherelationshipbetweentheaributes, longitudinallydivide thebuckets into multiplecolumns.Finally,randomlyrearrange thecolumns in the same bucket.The experimental results show that when dealing with high dimensional data,compared with LGAA-CP algorithm,the loss of information is reduced by $47 \%$ to $1 8 3 \%$ .the retention rate of the relationship is increased by $24 \%$ to $1 1 8 \%$ . Compared with the Slicing algorithm, the loss of information between the two is within $1 . 5 \%$ . the retention rate of the association is increased by （204号 $8 . 9 \%$ to $2 2 . 8 \%$ .Theanalysis show thatthealgorithm is efective in ensuring both high-dimensional data privacy protection and data availability.

Key words:privacy-preserving data publishing; $\mathbf { k }$ -anonymity;l-diversity; sensitive attribute column value constraint

# 0 引言

伴随信息技术的广泛使用和大数据技术的日益普及，数据开放已经是大势所趋。由于政府、部门、企业所开放的数据中包含了大量的隐私信息，若将数据直接以原始形式发布出去，必然会造成隐私泄露[I]。在此背景下，数据发布隐私保护（privacy-preserving data publishing，PPDP）这一技术被提出。与利用数据加密和访问控制等技术防止未授权者获取数据的传统隐私保护方法不同，PPDP的目的是尽量保持发布数据的可用性，同时防止数据使用者识别出敏感信息所对应的个体，从

而实现隐私保护[2-3]。

作为该领域的研究热点，当前很多学者在这方面做了大量的研究，众多数据发布模型纷纷被提出，如 $k \mathrm { . }$ 匿名模型[4.5]、 $l -$ 匿名[6.7]和 $t \cdot$ -接近性[89]等。但是这些研究存在的问题之一是虽然较好地实现了隐私保护，但是信息损失量大，数据可用性低。针对这一问题，很多学者在实现隐私保护的同时，开始考虑数据可用性。2012年徐勇等人提出基于属性权重的 $k \mathrm { . }$ -匿名算法WAK-anonymity[lo]，解决了重要信息损失量大的问题，但加大了其他数据的信息损失量，而且各数据间关联关系损失量很大。2012年李珊珊等人提出基于聚类的数据敏感属性匿名保护算法[1]。2016年龚奇源针对高维数据提出基于半划分的数据匿名算法[12]。2017年廖军等人提出一种基于权重属性熵的分类匿名算法[13]。这些方法在一定程度上降低信息的损失程度，但效果不太显著。同年姜火文提出贪心聚类匿名方法[14]，实现了等价类均衡划分，进一步提高了数据可用性，但仍然无法避免高维数据信息损失量大这一问题。

为了减少信息损失量，提高数据可用性，一些新的方法被陆续提出。2012年，Li等人[15]提出了基于随机重排技术的Slicing 算法思想，就如何减少信息损失量，保留属性间有用的关联关系给出了解决思路。2013年Li等人[16提出了Slicing 算法，利用对数据表横向分桶、纵向分栏的方式，在隐私保护的前提下，一定程度上保持了属性间的关联关系。2014 年 Yang等人[17提出的重叠划分匿名算法，以Slicing 算法为基础，但允许一个属性被划分到多栏，其优点是关联关系能更好地得到保留，缺点是在数据维数很高时，隐私保护能力凸显不足。2015年 Rohilla 提出的LDS 算法[18]，在 Slicing 的基础上只解决了连续型数据离散化的问题。2018年Wang等人针对事务数据提出T-Closeness Slicing 算法[19]，该算法使发布数据满足更严格的匿名发布T-Closeness模型，提高了隐私保护能力，但数据可用性有所下降。2016年王良等人提出基于加权贝叶斯网络的隐私数据发布方法[20]，利用差分隐私保护技术提升了原始隐私发布数据集的数据精确性，但在处理高维数据时还存在一些不足。综上所述，这些方法很难同时确保具有较好的隐私保护能力和数据可用性。

为此，本文提出一种基于局部划分的 ASG-LS(associationsetgenerating-localslicing)匿名算法，首先基于泛化层次树转换形成的泛化层次格，找出敏感属性顶点集srset和不包含敏感属性的关系属性顶点集rset，然后根据 srset 将数据表 $T$ 进行横向划分成多个桶，再根据srset 与 $r s e t$ 将同一桶中不同属性进行纵向划分形成栏，最后把同一桶中各栏的数据进行重排。从而在实现隐私保护的同时，确保发布的数据能具有更高的可用性。

# 1 匿名算法理论基础

假设要发布的数据表 $T$ 已经舍去标识符属性，如姓名、身份证号等。数据表 $T$ 包含的属性 $A = \{ A _ { 1 } , A _ { 2 } , \cdots , A _ { i } , \cdots , A _ { n } , S \}$ ，其中 $A _ { i } ( 1 \leq i \leq n )$ 为准标识符属性， $s$ 为敏感属性。

定义1泛化层次树 $T S e t$ 。若一棵树中任意存在父子关系的节点均满足泛化关系，则称这棵树为泛化层次树。在属性 $A _ { i }$ 的泛化层次树中，第 $j$ 层中第 $k$ 个节点记做 $A _ { i j k }$ ，其值域为$D ( A _ { i j k } )$ ，“<”表示属性值域间的泛化关系。若树中节点 $A _ { i j k }$ 与$A _ { i l m } ( l = j + 1 )$ 存在父子关系，则 $D ( A _ { i l m } ) < D ( A _ { i j k } )$ 一定成立。另外，若泛指属性 $A _ { i }$ 泛化层次树中的某个节点时，记做 $n o d e _ { i }$ 。

定义2泛化格 $\mathbf { g } _ { i }$ 。若一个图中任意存在边的顶点均满足泛化关系，且顶点为不同属性泛化层次树的节点集合，则称这个图为泛化格。 $i$ 个不同属性的泛化层次树构成的泛化格被记做 $g _ { i }$ ， $g _ { i }$ 中的任意一个顶点 $\mathbf { \Phi } _ { \nu }$ 则是这 $i$ 个泛化层次树中的节点$n o d e _ { 1 } , n o d e _ { 2 } , \cdots , n o d e _ { i }$ 的组合。且图中的任意一条边 $\nu _ { { } _ { m } } \nu _ { { } _ { k } }$ 的起始顶点 $\nu _ { { } _ { m } }$ 与终止顶点 $\boldsymbol { \nu } _ { \boldsymbol { j } }$ 满足以下条件： $\nu _ { { } _ { m } } < \nu _ { { } _ { j } }$ ；有且仅有一个$n o d e _ { \mathrm { k } }$ ，使得 $\nu _ { \mathrm { m } } . n o d e _ { k } < \nu _ { j } . n o d e _ { k }$ ，而两个顶点中的其余节点相同

定义3敏感属性栏值约束.将数据表T划分为桶时所遵循的约束条件。具体包括：a）敏感属性栏应满足 $l .$ 匿名；b)敏感属性栏内的属性间可存在关联关系，但不能与该栏以外的其他属性有关联关系。

定义4桶 $B$ 。数据表 $T$ 基于敏感属性栏值约束和记录间距离所做的一个横向的划分。假设一张数据表 $T$ 被划分 $\mathbf { \Sigma } _ { n }$ 个桶$B _ { 1 } , B _ { 2 } , . . . B _ { n }$ ，则 $\textstyle \bigcup _ { i = 0 } ^ { \mathrm { n } } B _ { i } = T ,$ 且 $\forall k$ $j , B _ { k } \cap B _ { j } = \emptyset , ( 0 \leq \mathbf { k } , j \leq n ) \circ$ （204

定义5栏 $c$ 。数据表 $T$ 中的一个桶 $B$ 基于属性间的关联关系，可被划分为 $m$ 栏，则 $\textstyle \bigcup _ { i = 0 } ^ { m } C _ { i } = B$ ，且 $\forall j , k$ ， $C _ { j } \cap C _ { k } = \phi$ ，$( 1 \leq \mathrm { j } , k \leq m )$ 。

定义6顶点 $\mathbf { \Phi } _ { \nu }$ 约束。记录t中的属性在顶点 $\mathbf { \Lambda } _ { \nu }$ 中有对应的属性节点，那么该属性的取值在其对应的属性节点值域内， $\mathfrak { t } _ { \in }$ $T$ 。

表1符号标志  

<html><body><table><tr><td>符号</td><td>意义</td></tr><tr><td>A</td><td>准标志符属性</td></tr><tr><td>S</td><td>敏感属性</td></tr><tr><td>rset</td><td>非敏感属性关联关系顶点集合</td></tr><tr><td>srset</td><td>包含敏感属性关联关系顶点合</td></tr><tr><td>TSet</td><td>泛化层次树</td></tr><tr><td>FTSet</td><td>频繁泛化层次树，即所有节点支持度均大于支持度阈值的化</td></tr><tr><td>node;</td><td>层次树</td></tr><tr><td>gi</td><td>属性A泛化层次树中的节点</td></tr><tr><td>fgi</td><td>泛化格</td></tr><tr><td></td><td>频繁泛化格，即顶点的支持度均大于支持度阈值的泛化格</td></tr><tr><td>V</td><td>顶点,其中v ∈g;,由i个泛化层次树中的节点nodel，node</td></tr><tr><td>B</td><td>,L,node,组合</td></tr><tr><td>W</td><td>桶</td></tr><tr><td>SupTh</td><td>属性权重</td></tr><tr><td>mc</td><td>支持度阈值 栏中属性列数最大值</td></tr><tr><td>C</td><td>栏</td></tr><tr><td>t</td><td></td></tr><tr><td>tA</td><td>数据表记录 记录t的第i个分类型属性</td></tr><tr><td>tA"</td><td>记录t的第i个数值型属性</td></tr><tr><td>conTh</td><td>置信度阈值</td></tr></table></body></html>

# 2 基于局部划分的匿名算法ASG-LS

# 2.1算法总体概述

为确保在隐私信息不被泄露的情况下，提升所发布的数据间的关联关系保持率，从而提高数据的可用性，针对发布数据中存在属性间的关系随值域的变化而变化的情形，提出一种基于局部划分的ASG-LS匿名算法。该算法先后依次调用ASG算法和LS算法，其中ASG算法用于找出属性值域间的多维多层次关联关系，并按顶点重要度降序，将包含敏感属性的关系保存到含敏感属性关联顶点集合srset，不包含敏感属性的关系保存到非敏感属性关联顶点集合rset中;LS算法则用于实现对数据表的划分，及匿名处理，其基本思想是基于敏感属性值约束和记录间距离将数据表横向分成若干个桶，再对每个桶基于属性间的关联纵向分成多栏，然后对同一桶中各栏中的数据进行随机重排，最终使得发布的数据在隐私保护的同时，使数据具有更高的利用价值。

# 2.2属性关联关系集合生成算法ASG

ASG算法完成LS算法的预处理工作，基于Apriori和层次泛化树实现，目的是找到属性值域间的多维多层次关联关系，并按重要度降序保存包含关联关系的顶点，将包含敏感属性的顶点保存到敏感属性关联关系集合srset 中，而其他顶点保存到普通关联关系集合rset中。ASG 算法如2所示。

该算法的主要实现过程分为四步：

a)生成频繁泛化层次树。从叶子节点开始，基于广度搜索的思想，按照从左往右，从下往上的次序遍历泛化层次树。根据节点包含的属性值域在数据表中出现的概率，依次计算每个节点的支持度，若支持度≥支持度阈值SupTh，则保留该节点，并标记与之直接相连的节点，反之则删除该节点，继续遍历与之相连的节点。遍历过程中若节点已被标记，则直接保留节点。最终使得泛化层次树中的所有节点的支持度均 $\ge \ S u p T h$ ，即得到频繁泛化层次树。

b)将频繁泛化层次树转为泛化格。频繁泛化层次树之间连接产生泛化格：选取两棵不同属性的频繁泛化层次树，两两连接生成泛化格 $g _ { 2 }$ ，其顶点为两棵树中的节点的组合；若其中某两个顶点包含的节点组合中只有一组对应的属性节点存在泛化关系，而其余节点相同时，则依据泛化关系生成一条有向边。

频繁泛化层次树与频繁泛化格 $f g _ { i - l }$ 连接产生泛化格 $g _ { i }$ ：若频繁泛化格 $f g _ { i - l }$ 没有包含该频繁泛化层次树，则进行连接，并采用上述方法生成泛化格 $g _ { i }$ 。否则不进行连接。

c)生成敏感及非敏感属性关联关系集合。从没有边指向的顶点开始，基于广度搜索的思想，按层次，从下往上的次序遍历计算泛化格 $g _ { \mathrm { i } }$ 中各顶点的支持度与置信度。若两者均大于等于设定阈值，则保存该顶点，并根据其是否包含敏感属性，分别保存到敏感属性关联关系集合srset或非敏感属性关联关系集合rset中，然后标记与之直接相连的顶点；反之则删除该顶点。遍历过程中若顶点已被标记，则直接保留顶点。最终关联关系集合中保存了泛化格中具有关联关系、顶点包含的节点层次相对最大和各顶点中对应节点值域相交为空的顶点；泛化格变成频繁泛化格。

d)实现顶点的重要度排序。为保留更多有用的关联关系，在本文后续LS算法中优先按包含重要关联关系的顶点进行划分，因此需要将关联关系集合srset 中各顶点按重要度降序排序。

顶点 $\mathbf { \Phi } _ { \nu }$ 的重要度 $\nu a l u e ( \nu )$ 是评价一个顶点中包含的属性间关联关系是否重要的指标。它由顶点中所包含的所有节点的层次和顶点的置信度共同决定，为此，首先利用式(1)计算节点nodei归一化后的层次值。其中， $l e \nu _ { n o d e _ { i } }$ 为节点 $n o d e _ { i }$ 在泛化层次树中的层次， $l e \nu _ { \mathrm { { m a x } } }$ 为泛化层次树的层次最大值。

$$
l e \nu ( n o d e _ { i } ) { = } \frac { l e \nu _ { n o d e _ { i } } \cdot l e \nu _ { r o o t } } { l e \nu _ { m a x } \cdot l e \nu _ { r o o t } }
$$

然后，再利用式(2)计算顶点 $\mathbf { \sigma } _ { \nu }$ 的重要度 $\nu a l u e ( \nu )$ 。其中，$w _ { \mathrm { i } }$ 表示数据表 $T$ 中属性 $A _ { i }$ 的权重， $n$ 为顶点 $\mathbf { \sigma } _ { \nu }$ 中包含节点的个数，conf(v)为顶点 $\nu$ 的置信度。

$$
\scriptstyle { \nu a l u e ( \nu ) = \sum _ { i = 1 } ^ { n } w _ { i } l e \nu ( n o d e _ { i } ) + c o n f ( \nu ) } ,
$$

算法1 ASG算法

输入：数据表 $T$ ，属性泛化层次树 $T S e t$ ，置信度阈值 $c o n f T h$ ，支持度阈值supTh，栏中属性列最大值 $m c$ ，属性权重 $w$ ：

输出：含敏感属性关联顶点集合 srset，非敏感属性关联顶点集合rset。

1． 遍历 $T S e t$ ，计算树中各节点支持度，剪枝支持度小于支持度阈值supTh 的节点，找出频繁泛化层次树，并保存到频繁泛化层次树集合FTSet;  
2. FTSet中所有频繁泛化层次树，两两连接生成泛化格，并加入泛化格集合中;  
3. for (每一个 $\mathbf { g } _ { i } \in$ 泛化格集合)  
4. 所有没有边指向的顶点，按层次把顶点入队；  
5. while (队不为空)  
6. if 顶点没有被标记  
7. 计算泛化格 $g _ { i }$ 中各顶点的置信度conf 和支持度 support ；  
8. if support $\geq$ supTh且conf≥conTh  
9. 按该顶点是否包含敏感属性，分别保存到敏感属性关联关系集合srset 和非敏感属性关联关系集合rset；

# else

10. 删除该顶点，与之直接相连的顶点入队；

end if end if end while

11．泛化格 $g$ 加入频繁泛化格集合 fgset ；

# end for

12. fgset 中各泛化格 $\mathbf { g } _ { i }$ 与FTSet中各频繁泛化层次树连接，并加入新的泛化格集合中;  
13. 转步骤3迭代，直到泛化格中顶点包含的节点数 $\geq m c$ ；  
14. 基于顶点包含的各属性权重 $w$ ，计算各顶点重要度value(v)，并按顶点重要度降序排序 srset 中的各顶点;  
15. return srset,rset ;

# 2.3基于局部划分的LS算法

LS 算法基于Slicing思想和关联关系集合，采用局部划分数据表的匿名方法。其基本思想是先横向划分数据表，将整个数据表划分成多个桶，然后分别对每个桶进行纵向划分，将一个桶划分为多栏，其结果是同一属性在不同桶中不一定在同一栏。从而确保既减少信息损失量，又减少数据间关系的损失量。LS 算法如算法2所示。

该算法的主要实现过程分四步：

a）对数据表横向分桶

为减少数据的信息损失量，对数据表进行横向划分桶。划分时每次从srset 中取出一个重要度值最大的顶点 $\mathbf { \Phi } _ { \nu }$ ，然后从数据表 $T$ 中随机取出一条满足顶点 $\mathbf { \Phi } _ { \nu }$ 值约束的记录t，加入桶 $B$ ，进而从数据表 $T$ 中挑选 $k$ 条满足敏感属性栏值约束和距离最近约束的记录到桶B。

为挑选出满足距离最近约束的记录，必须计算数据表中任意一条记录与记录 $\mathbf { \Phi } _ { t }$ 的距离，其值采用两条记录的属性间的距离来度量。属性间的距离分为数值型属性间的距离与分类型属性间的距离，记录 $t _ { p }$ 的第 $i$ 个数值型属性与记录 $t _ { \boldsymbol { q } }$ 的第 $i$ 个数值型属性间的距离为 $d i s t ( t _ { p } A _ { i } ^ { n } , t _ { q } A _ { i } ^ { n } )$ ，记录 $t _ { { } _ { p } }$ 的第 $i$ 个分类型属性与记录t第i个分类型属性间的距离为dist(tpA,tA）。

数值型准标识符属性间的距离dist(t,A",tA")：

$$
d i s t ( t _ { p } A _ { i } ^ { n } , t _ { q } A _ { i } ^ { n } ) { = } \frac { \left| { \cal D } \left( t _ { P } A _ { i } ^ { n } \right) - { \cal D } \left( t _ { q } A _ { i } ^ { n } \right) \right| } { m a x \left( T A _ { i } ^ { n } \right) - \operatorname * { m i n } \left( T A _ { i } ^ { n } \right) } ,
$$

D(tpA")表示元组t的第i个数值型准标识符的取值，（20 $| D \big ( t _ { P } A _ { i } ^ { n } \big ) - D \big ( t _ { q } A _ { i } ^ { n } \big ) \big |$ 为取两个属性值之差的绝对值， $m a x \big ( T A _ { i } ^ { n } \big )$ 表示数据表 $T$ 第 $i$ 个数值型标识符的最大值， $\operatorname* { m i n } \left( T A _ { i } ^ { n } \right)$ 表示数据表 $T$ 第 $i$ 个数值型标准符的最小值。

分类型准标识符属性间的距离计算需要引入泛化层次树作为度量依据，参照泛化层次树首先计算元组 $t _ { p }$ 第 $i$ 个分类型属性 $t _ { p } A _ { i } ^ { c }$ 与元组 $t _ { \boldsymbol { q } }$ 第 $i$ 个分类型属性 $t _ { q } A _ { i } ^ { c }$ 到共同最小祖先节点的距离，记为 $l e n ( t _ { p } A _ { i } ^ { c } , ~ t _ { q } A _ { i } ^ { c } )$ ；然后计算 $t _ { p } A _ { i } ^ { c } \ , t _ { q } A _ { i } ^ { c }$ 各自到根节点的距离 $l e n ( t _ { p } A _ { i } ^ { c } , r o o t )$ ；最后计算分类型准标识符属性间的距离$d i s t ( t _ { p } A _ { i } ^ { c } , t _ { q } A _ { i } ^ { c } )$ ，公式如下。

$$
d i s t ( t _ { p } A _ { i } ^ { c } , t _ { q } A _ { i } ^ { c } ) = \frac { l e n ( t _ { p } A _ { i } ^ { c } , t _ { q } A _ { i } ^ { c } ) } { l e n ( t _ { p } A _ { i } ^ { c } , r o o t ) + l e n ( t _ { q } A _ { i } ^ { c } , r o o t ) } ,
$$

假设一个记录有 $d _ { \scriptscriptstyle 1 }$ 个数值型准标识符， $d _ { 2 }$ 个分类型准标识符，记录间的距离为dist(tp,tq）。

$$
d i s t ( t _ { p } , t _ { q } ) = \sum _ { i = 1 } ^ { d _ { 1 } } d i s t ( t _ { p } A _ { i } ^ { n } , t _ { q } A _ { i } ^ { n } ) + \sum _ { i = 1 } ^ { d _ { 2 } } d i s t ( t _ { p } A _ { i } ^ { c } , t _ { q } A _ { i } ^ { c } ) \ ,
$$

# b）栏划分

为减少数据间关系的损失量，将每个桶纵向划分成多个栏。其思想是针对每个桶，首先将包含敏感属性的顶点 $\nu$ 所包含的节点集对应的属性划分到一栏。再遍历非敏感属性关联关系集合rset中每一个顶点 $\nu _ { i }$ ，计算桶中满足顶点 $\nu _ { i }$ 约束的记录数。并按记录数降序排序 $r s e t$ 后，按照从前往后的次序依次取出顶点 $\nu _ { i }$ ，找出 $\nu _ { i }$ 中所包含的各节点所对应的桶中属性，并去除其中已经被分配的属性，若剩余属性数量大于或等于设定的栏中最小属性数量，则将其划分为一栏，否则放弃该划分。最后，若桶中剩余的未被纵向划分的属性列数大于栏中最大属性数量，则对属性进行均匀分栏，否则将剩余属性直接作为一栏。

# c）数据重排

假设桶中的属性共划分为 $\mathbf { \Psi } _ { c }$ 栏，则对桶中任意 $c - 1$ 栏进行随机重排；重排后，若有记录仍处于原来位置，则将其与桶中其他记录随机置换。因此同栏中高关联属性间的关联关系保持不变，破坏的是不同栏之间的关联关系，从而保持了高关联属性间的关联关系。

d）栏概化

为使数据表 $T$ 满足 $k \cdot$ .匿名性。检查桶中某属性值在数据表$T$ 中出现的概率，若低于阈值 $f$ ，则需对其所在的栏进行该属性列的概化；列概化后，计算栏中不重复的记录数等于k的栏数量，若栏数 $_ { < 2 }$ ，则对整个桶进行概化。

算法2 LS 算法

输入：数据表 $T$ ，srset ，rset， $k$ 匿名性参数 $k ^ { \mathbf { \alpha } } \cdot \mathbf { \beta } _ { l - 1 }$ 多样性参数l，栏中属性最大数量 $m c$ ，栏中最小属性数量 $n c$ （20

输出：匿名后的数据表T\*

1. while（srset不为空且 $T$ 中存在未处理的记录)  
2. 从 srset 中按从前往后的次序取出顶点 $\nu$ ：  
3. while (满足顶点 $\nu$ 约束的记录数 ${ > } 0$ ）  
4. 从数据表 $T$ 中随机取出一条满足顶点 $\nu$ 约束的记录 $\mathbf { \Phi } _ { t }$ ，加入桶 $B$ ：  
5. while (桶 $B$ 中的记录数 $\cdot < \boldsymbol { k }$ ）  
6. 取出与 $\mathbf { \Phi } _ { t }$ 距离最近且满足敏感属性栏值约束的记录，加入桶 $B$ 中；  
7. end while  
8. 将顶点 $\nu$ 包含的节点集对应的属性划为一 栏;  
9. for (每一个顶点 $\nu _ { i } \in r s e t$ ）  
10. 计算桶中满足顶点 $\nu _ { i }$ 约束的记录数 $n t$ ；  
11. end for  
12. 按记录数 $n t$ 降序排序 $r s e t$ 中各个顶点;  
13. for (按从前往后的次序从rset 中取出顶点 $\nu _ { i }$ ）  
14. 找出 $\nu _ { i }$ 包含的各节点在桶 $B$ 中对应的属性，并去除其中已经被分配  
到其他栏的属性;  
15. 若剩余属性列数 $> n c$ ，将其划分为一栏；否则放弃该划分；  
16. end for  
17. 若桶中剩余的未划分栏的属性列数 $> m c$ ，对属性进行均匀分栏；否  
则将剩余属性直接作为一栏；  
18. 若桶 $B$ 总共被划分 $n$ 栏，则对其中 $^ { n - 1 }$ 栏进行随机重排;  
19. 重排后，若存在记录仍处于原来位置，则将其与桶中其他记录随机置  
换；  
20. 检查桶中某属性值在数据表 $T$ 中出现的概率;  
21. 若低于阈值 $f$ ，则需对其所在的栏进行该属性列的概化;  
22. 列概化后，计算栏中不重复的记录数等于 $\mathbf { k }$ 的栏数量，若栏数 $^ { < 2 }$   
则对整个桶进行泛化。  
23. end while  
24. end while  
25. return $T ^ { * }$

# 2.4 时间复杂性分析

ASG-LS匿名算法由两个子算法ASG和LS组成，其中，ASG算法生成频繁泛化层次树，以及将频繁泛化层次树转为泛化格的时间复杂度均为 $O ( n ^ { 2 } )$ ；另外两个步骤时间复杂度均为$O ( n )$ ；所以子算法 ASG 的时间复杂度为 $O ( n ^ { 2 } )$ 。LS 算法的时间复杂度只与srset 中的顶点数、rset 中的顶点数、以及 $k$ 匿名性参数 $k$ 以及表 $T$ 中的记录数 $n$ 有关。顶点数与 $k$ 值远小于$n$ ，因此时间复杂度为 $O ( n ^ { 2 } )$ 。所以 ASG-LS 算法总的时间复杂度为 $O ( n ^ { 2 } )$ 。

# 3 算法比较与实验分析

# 3.1算法比较

将本文提出的 ASG-LS 算法与泛化和 Slicing 两类方法进行比较。根据某家医院的病人诊断记录原始表，如表4所示，泛化首先把距离较近的记录划分到同一个等价类，然后概括等价类中各属性所有列中的值，如表5所示。Slicing横向划分将距离较近的记录划分到同一个桶中，纵向全局划分将高关联关系的数据划分到同一栏中，最后随机重排同栏中的数据，如表6所示。

表4病人诊断记录原始表  

<html><body><table><tr><td>Name</td><td>Age</td><td>sex</td><td>District</td><td>Disease</td></tr><tr><td>Tom</td><td>22</td><td>M</td><td>Hawaii</td><td>bronchitis</td></tr><tr><td>Lily</td><td>27</td><td>F</td><td>California</td><td>breastcancer</td></tr><tr><td>Hebe</td><td>35</td><td>F</td><td>California</td><td>pnenmonia</td></tr><tr><td>John</td><td>49</td><td>M</td><td>Connecticut</td><td>flu</td></tr><tr><td>Ella</td><td>59</td><td>M</td><td>Connecticut</td><td>flu</td></tr><tr><td>Selina</td><td>60</td><td>F</td><td>Mississippi</td><td>breastcancer</td></tr><tr><td>Bob</td><td>65</td><td>M</td><td>Washington</td><td>gastritis</td></tr><tr><td>Lau</td><td>70</td><td>F</td><td>Alaska</td><td>breastcancer</td></tr></table></body></html>

对表4中数据进行泛化处理后，结果如表5所示，从表中可看出，该结果满足4-匿名性和3-多样性，使发布的数据表满足了一定程度的隐私保护要求，但数据过度泛化导致数据的信息损失量过大，数据可用性很低。

表5泛化后的病人诊断记录表  

<html><body><table><tr><td>age</td><td>sex</td><td>district</td><td>zipcode</td><td>disease</td></tr><tr><td>[21-27]</td><td>*</td><td>America</td><td>47*</td><td>flu</td></tr><tr><td>[21-27]</td><td>*</td><td>America</td><td>47*</td><td>endemictyphus</td></tr><tr><td>[21-27]</td><td>*</td><td>America</td><td>47*</td><td>flu</td></tr><tr><td>[21-27]</td><td>*</td><td>America</td><td>47*</td><td>dyspepsia</td></tr><tr><td>[35,50]</td><td>*</td><td>America</td><td>47*</td><td>pnenmonia</td></tr><tr><td>[35,50]</td><td>*</td><td>America</td><td>47*</td><td>bronchitis</td></tr><tr><td>[35,50]</td><td>*</td><td>America</td><td>47*</td><td>breastcancer</td></tr><tr><td>[35,50]</td><td>*</td><td>America</td><td>47*</td><td>breastcancer</td></tr></table></body></html>

采用Slicing算法处理后，结果如表6所示，从结果可看出，该算法将敏感属性和与其有关的属性划分为一栏，其他属性分为一栏，并通过栏中数据进行置换来实现隐私保护。其结果满足3-多样性和4-匿名性，达到了一定程度的隐私保护。和泛化方法相比，Slicing算法不仅进行横向划分，还进行了纵向划分，从而提高了数据可用性。但其缺点是属性间的关系随值域的变化而变化，会损失部分属性间的关联关系。

表6Slicing算法处理后病人记录诊断记录表  

<html><body><table><tr><td>age,sex</td><td>district,zipcode,disease</td></tr><tr><td>22,M</td><td>California,47905,endemictyphus</td></tr><tr><td>25,F</td><td>Connecticut,47302,flu</td></tr><tr><td>26,M</td><td>Bloomington, 47490,dyspepsia</td></tr><tr><td>27,F</td><td>Connecticut, 47302,flu</td></tr><tr><td>35,M</td><td>Alaska,47304,breastcancer</td></tr><tr><td>40,F</td><td>Washington,47301,pnenmonia</td></tr><tr><td>49,M</td><td>Mississippi,47904,breastcancer</td></tr><tr><td>50,F</td><td>Washington,47301,bronchitis</td></tr></table></body></html>

采用本文的ASG-LS算法处理后如表7所示。整个表被分为两个桶，每个桶各自被划分为两栏。从结果不难发现，其满足4-匿名性与3-多样性，能较好地满足隐私保护要求。与Slicing算法划分后同一属性在不同桶中必在同一栏不同，由ASG-LS算法纵向划分后，利用在不同桶中，同一属性被划分到不同栏的方法，更多地保留了属性之间的关联关系，从而大大提高了数据的可用性。

表7ASG-LS 算法处理后的病人记录诊断记录表  

<html><body><table><tr><td>Age,Sex</td><td>District,Zipcode,Disease</td></tr><tr><td>22, M</td><td>Bloomington,47490,dyspepsa</td></tr><tr><td>25,F</td><td>Connecticut,47302,flu</td></tr><tr><td>26,M</td><td>California,47905,endemictys</td></tr><tr><td>27,F</td><td>Connecticut, 47302,flu</td></tr><tr><td>Age,District,Zipcode</td><td>Sex, Disease</td></tr><tr><td>35,Washington,47490</td><td>F, breastcancer</td></tr><tr><td>40,Connecticut,47302</td><td>F, breastcancer</td></tr><tr><td>49,Alaska,47304</td><td>M, bronchitis</td></tr><tr><td>50,Mississippi,47904</td><td>M, pnenmonia</td></tr></table></body></html>

# 3.2实验分析

从信息损失量[13]和数据可用性两个方面对本文提出的ASG-LS 算法的性能进行验证。GAA-CP[14]是信息损失量较小的泛化处理算法，其具有一定优秀泛化算法的代表性。但GAA-CP只满足K-匿名，为使能更好的对比将其满足 $l .$ 匿名，记为LGAA-CP。Slicing[16算法中的 $k$ 值为桶中记录数的最小值。

实验数据集来源于隐私保护领域广泛使用的Adult 数据集。在去除该数据集中具有缺失属性值的记录后，最终实验基于一个包含30162个元组的数据集完成。实验环境为：Intel(PCoreTMi5-2450MCPU $@ 2 . 5 0 \mathrm { G H z }$ ；4.00 GB 内存；LITEONT9(256GB)主硬盘；Windows10专业版64位操作系统；MySQL数据库系统；IntelliJIDEA2017.2.5开发环境；jdk8运行环境。算法采用Java 语言实现。

# 3.2.1信息损失分析

为分析数据信息损失量随数据集维度 $\left. T _ { m } \right.$ 、匿名参数 $k$ 值改变而改变的规律，分别采用ASG-LS算法、LGAA-CP算法和Slicing 算法进行如下两组实验。

实验1当数据维度 $\left. T _ { m } \right.$ 分别为5、10、14时，验证三种算法中匿名参数 $k$ 值的变化对信息损失量大小的影响。结果如图1(a)(b)(c)所示。其中栏中属性最大数量 $m c = 4$ ，栏中最小属性数量 $n c = 2$ ，置信度阈值 $c o n f T h = 0 . 8$ ，支持度阈值 $s u p T h = 0 . 2$ ，l-多样性参数 $L ^ { = 3 }$ 。

![](images/093f557be5290c8516434d28210c12797db1d79eb18c5993365b373efdb2fd67.jpg)  
图1匿名参数 $k$ 值的变化对信息损失量影响

实验结果表明，当数据维度相同时，随者 $k$ 值的增大，三者的数据信息损失量都增大，但LGAA-CP的信息损失量显著增大。Slicing和ASG-LS的信息损失量增加很少，且两者基本一致，因为Slicing和ASG-LS都是进行的局部的泛化处理。

实验2当匿名参数 $k$ 分别为10、15、20时，验证三种算法中数据维度 $\left. T _ { m } \right.$ 的变化对信息损失量大小的影响。结果如图2(a)(b)(c)所示。其中：栏中属性最大数量 $m c = 3$ ，栏中最小属性数量 $n c = 2$ ，置信度阈值 $c o n f T h = 0 . 8$ ，支持度阈值 $s u p T h = 0 . 2$ ，$L -$ 多样性参数 $L ^ { = 3 }$ 。

![](images/6cda1265ddb935ef655ebc56935a8cfbab1758e1a8e42c2553897109a1822a98.jpg)  
图2数据维度 $\left. T _ { m } \right.$ 变化对信息损失量影响

实验结果表明，当匿名参数 $k$ 值相同时，随数据维度 $\left. T _ { m } \right.$ 的增大，三者的数据信息损失量都增大。但LGAA-CP 的信息损失量显著增大，其中当 $\left. T _ { m } \right.$ 取值在5到8之间时增长最快；而同样因为Slicing和ASG-LS进行的都是局部泛化处理，其信息损失量较小，且增速较慢。

# 3.2.2数据可用性分析

关联关系保持率AR是数据匿名处理后保留的关联规则数与原始数据关联规则数的比值，用于衡量匿名方法在保留属性间有用关联关系效果。本文采用WekaApriori挖掘关联规则。

为了分析匿名后数据的关联关系保持率随数据集维度 $\left| \mathrm { T } _ { \mathrm { m } } \right|$ ，$k \mathrm { . }$ 匿名对应 $k$ 值改变而改变的规律，分别采用ASG-LS算法、LGAA-CP和Slicing算法进行如下两组实验。

实验3当数据维度 $\left. { T _ { m } } \right.$ 分别为5、10、14时，验证三种算法中匿名参数 $k$ 值的变化对关联关系保持率的影响。结果如图3(a)\~(c)所示。其中：栏中属性最大数量 $m c = 4$ ，栏中最小属性数量 $n c = 2$ ，置信度阈值 $c o n f T h = 0 . 8$ ，支持度阈值 $s u p T h = 0 . 2$ ，l-多样性参数 $L ^ { = 3 }$ 。

![](images/ac44155a59354c15d280f09c43493f17b2ec1a259ac29071bb9e61022dcd2de0.jpg)  
图3匿名参数 $k$ 值的变化对关联关系保持率影响

实验结果表明，当数据维数 $\left. T _ { m } \right. = 5$ 时，三个算法的关联关系保持率是一样的，原因是当维度较小时，原始数据具有的关联规则比较少，且很多数据自身特性已满足 $\mathbf { k }$ -匿名性，所以对算法的依赖性不强。而当数据维度为10和14时，随 $k$ 值增加，LGAA-CP算法关联关系保持率大幅度减少，ASG-LS 算法和Slicing算法关联关系保持率略有下降，但ASG-LS始终保持在Slicing 之上。因为ASG-LS和 Slicing 都是进行的局部泛化处理，且ASG-LS是进行的是局部划分。

实验4当匿名参数 $k$ 分别为10、15、20时，验证三种算法中数据维度 $\left. T _ { m } \right.$ 的变化对关联关系保持率的影响。结果如图4(a)(b)(c)所示。其中：栏中属性最大数量 $m c = 3$ ，栏中最小属性数量 $n c = 2$ ，置信度阈值 $c o n f T h = 0 . 8$ ，支持度阈值 $s u p T h = 0 . 2$ ，$l .$ 多样性参数 $L ^ { = 3 }$ 。

![](images/16f22de12bdf449e842b3d5c6bb249f07f4aa458567cf6333be1bcbe96591154.jpg)  
图4数据维度 $\left. T _ { m } \right.$ 变化对关联关系保持率影响

实验结果表明,三种算法均在数据维度 $\left. { T _ { m } } \right.$ 取值在5到8之间时关联关系保持率急速下降，原因是数据维度从5增加到8时，原始数据中具有的关联关系数量显著增加。而当数据维度$\left. T _ { m } \right.$ 从8增加到14时，三种算法随数据维度增加，关联关系保持率平缓减少,但由于ASG-LS采取的是小局部的泛化处理和局部划分，最终导致ASG-LS的关联关系保持率大于Slicing 和LGAA-CP。

# 4 结束语

为了确保在隐私信息不被泄露的情况下，提高数据匿名后的可用性，本文提出了一种基于局部划分的匿名算法研究。该算法借助Slicing的思想，在确保K-匿名性和L-匿名的前提下，基于敏感属性栏值约束和记录间距离将数据表横向分成若干个桶，然后对每个桶基于属性间的关联纵向分成多栏，最后对同一桶中各栏中的数据进行随机重排。实验结果表明，该方法在减少信息损失量和提高关联关系保留率方面具有较高的合理性和有效性。

# 参考文献：

[1] 武毅，王丹，蒋宗礼．基于事务型 $\mathbf { k }$ anonymity 的动态集值属性数据重 发布隐私保护方法 [J].计算机研究与发展,2013,50(S1):248-256.(Wu Yi，Wang Dan, Jiang Zongli． Privacy preserving in re-publication of dynamic set-valued data based on transactional $\mathbf { k }$ -anonymity [J]. Journal of Computer Research and Development,2013,50 (s1): 248-256.)   
[2]冯登国，张敏，李昊．大数据安全与隐私保护[J].计算机学报,2014, 37(1): 246-258. (Feng Dengguo,Zhang Ming,Li Hao.Big data security and privacy protection [J]. Chinese Journal of Computers,2014,37 (1): 246- 258.）   
[3]刘雅辉，张铁赢，靳小龙，等．大数据时代的个人隐私保护[J].计算 机研究与发展,2015,52(1):229-247.(Liu Yahui,Zhnag Tieying,Jin Xiaolong.Personal privacy protection in the era of big data [J]. Journal of Computer Research and Development,2015,52(1): 229-247.)   
[4]Latanya S. k-anonymity: a model for protecting privacy [J]. International Journal on Uncertainty,Fuzzinessand Knowledge-Based Systems,2002,10 (5): 557-570.   
[5] 董芳菲．基于k-匿名的隐私保护算法研究[D].兰州：西北师范大学, 2015.(Dong Fangfei. Research on privacy protection algorithm based on kanonymity [D].Lanzhou: Northwest Normal University, 2015.)   
[6]Machanavajhala A,Kifer D,Gehrke J.l-diversity:privacy beyond $\mathbf { k }$ 1 anonymity [C]/ Proc of International Conference on Data Engineering. 2006: 24.   
[7] Yang Gaoming,Li Jingzhao, Zhang Shunxiang,et al. An enhanced ldiversity privacy preservation [C]//Proc of International Conference on Fuzzy Systems and Knowledge Discovery. 2014: 1115-1120.   
[8]Li Ninghui, Li Tiancheng,Venkatasubramanian S. t-closeness:privacy beyond $\mathbf { k }$ -anonymity and l-diversity[C]//Proc of International Conference on Data Engineering. IEEE,2007: 106-115.   
[9]张健沛，谢静，杨静，等．基于敏感属性值语义桶分组的t-closeness 隐 私模型[J].计算机研究与发展,2014,51(1):126-137.(Zhang Jianpei, Xie Jing, Yang Jing,et al.AT-Closeness privacy model based on sensitive attribute values semantics bucketization [J]. Journal of Computer Research and Development,2014,51 (1): 126-137. )   
[10]徐勇，秦小麟，杨一涛，等．一种考虑属性权重的隐私保护数据发布方 法[J].计算机研究与发展,2012,49(5):913-924.(Xu Yong,Qin Xiaolin, Yang Yitao,etal.A weight-aware approach to privacy preserving publishing data set [J]. Journal of Computer Research and Development,2012,49 (5): 913-924.)   
[11]李珊珊，朱玉全，陈耿．基于聚类的数据敏感属性匿名保护算法[J]. 计算机应用研究,2012,29(2): 469-471.(Li Shanshan,Zhu Yuquan,Chen Geng. Clustering-based algorithm for data sensitive attributes anonymous protection[J].Application Research of Computers,201,29 (2): 469-471.)   
[12]龚奇源．面向数据发布的数据匿名技术研究[D]．南京：东南大学， 2016.(Gong Qiyuan. Research on data anonymous technology for data publishing [D]. Nanjing: Southeast University,2016.）   
[13]廖军，蒋朝惠，郭春，等．一种基于权重属性熵的分类匿名算法[J]. 计算机科学,2017,44(7): 42-46.(Liao Jun,Jian Chaohui,Guo Chun,et al. Classification anonymity algorithm based on weight attributes entropy[J]. Computer Science,2017,44(7): 42-46. )   
[14]姜火文，曾国荪，马海英．面向表数据发布隐私保护的贪心聚类匿名方 法[J].软件学报,2017,28(2): 341-351.(Jiang Huowen, Zeng Guosun, Ma Haiying. Greedy Clustering-AnonymityMethod forPrivacy Preservation of Table Data-publing [J]. Journal of Software,20l7,28 (2): 341-351. )   
[15] Li Tiangcheng,Li Ninghui,Zhang Jian,et al. Slicing:A New Approach for Privacy Preserving Data Publishing[J]. IEEE Trans on Knowledge & Data Engineering,2012,24 (3): 561-574.   
[16] Li Tiangcheng,Li Ninghui, Zhang Jian,et al. Slicing: a new approach to privacy preserving data publishing [J]. International Journal of Computer Trends& Technology,2013,4(8): 64-78.   
[17] Yang Jing,Liu Ziyun,Yang Yue,et al.A data anonymous method based on overlapping slicing [C]// Proc of International Conference on Computer Supported Cooperative Work in Design. 2014:124-128.   
[18] Bhardwaj M,Rohilla S.Privacy preserving data publishing through slicing [J].American Journal ofNetworks and Communications,2015,4 (3-1): 45 53.   
[19] Wang Mingzheng,Jiang Zhengrui, Zhang Yu,et al. t-closeness slicing: a new privacy preserving approach for transactional data publishing [J]. Social Science Electronic Publishing,2018,29(7):50-63.   
[20]王良，王伟平，孟丹．基于加权贝叶斯网络的隐私数据发布方法[J]. 计算机研究与发展，2016,53（10):2343-2353.（Wang Liang，Wang

Weiping，Meng Dan.Privacy preserving data publishing via weighted bayessian networks [J]. Journal of Computer Research and Development, 2016,53 (10):2343-2353.)