# 基于链路预测的有向互动影响力和用户信任的推荐算法

魏映婷，倪静+(上海理工大学 管理学院，上海 200093)

摘要：针对传统推荐算法存在忽视社交网络结构紧密强度对用户信任传递的影响和缺乏社交心理解释等问题，提出基于链路预测的有向性互动影响力和用户信任的推荐算法。首先利用融合用户偏好行为和社交圈的综合相似度识别出目标用户的相似朋友圈；其次通过结合节点引力指数和有向性影响因子获得目标用户之间的有向性互动影响力，再利用由有向性互动影响力和用户评分信任而得的综合用户信任值在目标用户的相似朋友圈中寻找出值得信任的相似用户集合，这有效提高了推荐的精确性，最后产生推荐。结果表明，所提的推荐方法较之前的社会网络推荐算法在性能上具有显著提高。

关键词：社交网络；评分信任度；有向性互动影响力；链路预测 中图分类号：TP doi:10.19734/j.issn.1001-3695.2018.10.0801

Recommendation algorithm based on link prediction for directed interaction influence and user trust

Wei Yingting, Ni Jing+ (Business School,University of Shanghai for Science&Technology,Shanghai 20oo93,China)

Abstract:Aimingatthe problems thatthetraditionalrecommendationalgorithm ignores the influenceofthe tight structure ofsocial network structureonuser trust transmision and the lack of social psychological explanation,arecommendation algorithm basedonlink prediction for directed interactionand usertrust isproposed.Firstly,the similar user circleof the targetuseris identifiedbythe integrated similaritybetweentheuserpreferencebehaviorand thesocialcircle.Secondly,the directionalinteraction influencebetweenthetargetusers isobtainedbycombining thenodegravityindexandthedirected influence factor.The integrated user trustvalueofthe directional interaction influenceand the user score trust finds a trustworthysimilarusersetinthesimilarcircleoffriendsofthetargetuser,whicheffectivelyimprovestheaccuracyofthe recommendation and finally generates the recommendation.The results show that the proposed method has a significant improvement in performance compared to the previous social network recommendation algorithm.

Keywords:social network; score trust; directive interaction; link prediction

# 0 引言

目前，已有不少学者将信任引入电子商务推荐系统，从而缓解了推荐准确性、数据稀疏度等问题，李良等人[1提出将评分信任度和偏好信任度线性加权融合，改进信任度计算方法，提高了推荐的准确率。丁小焕等人[2提出了一种融合朋友关系和标签信息的张量分解推荐算法，该算法验证了结合朋友关系能够提高推荐的准确率。Zhu等人[3]根据原有信任关系网络，结合不同的信任传播方式，挖掘出未知的信任关系，但该方法只借助于用户已经记录的信任网络信息，而忽略了用户间的交互信息，Liben-Nowell等人[4将相似性指标分为基于节点和基于路径的指标，并分析了若干指标合作对社会网络中链接预测的效果。

推荐系统与社交网络的融合使得个性化推荐发展到一个新阶段。众所周知，人们一般比较容易接受朋友和专家的推荐。所以考虑将用户信任和互动影响力融入推荐算法中解释了用户社交心理对用户社交行为的影响。该推荐算法把融合有向互动影响力的用户信任作为影响推荐的重要因素：a）本文结合 RA 指数 (resource allocation index)[5]和 AA 指数(adamic-adarindex)[6]，提出了利用一种节点互动影响预测方法一有向性节点引力指数，有向性节点引力指数是在考虑被预测两个节点的共同邻居节点的节点度的基础上，同时考虑被预测节点与共同邻居组成的小型网络对预测用户互动影响力的影响,由于每个用户的兴趣点不同，愿意接受的其他用户对自身的影响也不同，所以本文还应考虑互动影响力的有向性[7]；b)另一方面，考虑整个推荐系统中用户信任度，从用户活跃度和用户评分客观度两个因素来计算用户信任度。本文的主要的推荐过程是首先根据融合偏好行为和社交圈的用户相似度找到目标用户的相似邻居集，然后在相似邻居集中选择推荐信任值较高的top $\mathbf { \nabla } \cdot \mathbf { k }$ 用户推荐给目标用户。

# 1 相关研究

# 1.1典型的链路预测方法

在复杂网络链路预测的研究中，网络链路的预测方法已经成为研究热点，链路预测是指如何通过已知的网络节点以及网络结构等信息，预测网络中尚未产生连边的两个节点之间产生连接的可能性[8]。典型的RA指数和AA指数计算节点相似度时将共同邻居节点度信息考虑进来，分别取得较好的预测效果。RA指数[5]：该算法从资源分配的角度出发，认为网络中每个节点都有一定的资源，并将资源平均分配给它的邻居。网络中没有直接相连的两个节点 $^ { \mathrm { ~ \tiny ~ { ~ x , y ~ } ~ } }$ 可以从节点 $\textbf { x }$ 传递一些资源到节点y，在此过程，节点 $\textbf { x }$ 和y的共同邻居成为传递媒介，则节点y接收到的资源数就定义为节点 x,y的相似度记为RA指数。AA指数[：该算法的思想是节点度小的共同邻居节点对于相似性的作用程度反而大于节点度大的共同邻居节点，基于该思想定义节点之间的节点相似性记为AA指数。

这两种指数只考虑被预测的两个节点共同邻居数目和共同邻居的节点度数，并未深入研究预测用户与它们的共同邻居之间所形成的小型网络结构紧密程度以及节点出入度的方向性对预测结果的影响。

# 1.2好友信任的度量

信任是通过收集和分析用户之间的互动行为获得的用于衡量好友关系密切程度的度量。之前的学者研究用户信任一般考虑用户评分认可度和用户评分准确度，用户评分认可度表示用户对项目的评分被大众认可的程度，用户评分准确度表示用户的评分和大众对某项目评分平均值的接近程度。他们都是简单的从这两个因素考量用户信任，这样的方法比较片面，使得推荐不够准确，没有挖掘出潜在的信任好友。

# 1.3协同过滤算法与相似度计算

传统的协同过滤推荐算法过程：a)根据用户一项目评分矩阵计算用户相似度；b)根据相似度选取近邻用户；c根据近邻用户给出预测分数；d)产生推荐。本文的相似度计算如下：

a）基于偏好行为的用户相似度。

本文根据IF-IDF算法[9的思路计算项目标签对于用户爱好物体的权重 $\mathbf { w } \big ( u _ { i } , b _ { t _ { l } } \big )$ ，计算公式如式（1）所示。

$$
\mathrm { ~ w ~ } \big ( u _ { i } , b _ { t _ { l } } \big ) = T F _ { ( u _ { i } , b _ { t _ { l } } ) } \times I D F _ { b _ { t _ { l } } }
$$

其中： $T F _ { ( u _ { i } , b _ { t _ { l } } ) }$ 表示标签 $b _ { t _ { i } }$ 在用户评分项目中出现的频率； $I D F _ { b _ { \eta } }$ 表示该标签在所有用户的评分项目模型中的区别能力，它们的计算方法分别表示为

$$
T F _ { ( u _ { i } , b _ { \eta } ) } = \frac { n u m _ { ( u _ { i } , b _ { \eta } ) } } { n u m _ { ( u _ { i } ) } }
$$

其中： $n u m _ { ( u _ { i } , b _ { t l } ) }$ 表示用户 $u _ { i }$ 使用标签 $b _ { t _ { t } }$ 的次数； $n u m _ { ( u _ { i } ) }$ 表示用户 $u _ { i }$ 使用标签的总数。

$$
I D F _ { ( b _ { t } ) } = l o g \frac { n u m _ { u s e r } } { n u m _ { t _ { l } } }
$$

其中： $n u m _ { u s e r }$ 为推荐系统中的用户总数； $n u m _ { t _ { t _ { i } } }$ 为使用过标签 $t _ { l }$ 的用户的数量。综上所述，可得出基于标签系统的项目权重向量( $\mathbf { W } _ { \mathrm { i t e m _ { i } } }$ )为如式(4)所示。

$$
\mathbf { W } _ { \mathrm { i t c m _ { i } } } = \left( \mathrm { w } \left( u _ { i } , b _ { t _ { i } } \right) , \mathrm { w } \left( u _ { i } , b _ { t _ { 2 } } \right) , . . . , \mathrm { w } \left( u _ { i } , b _ { t _ { i } } \right) \right)
$$

其中：itemi代表用户i对项目item的偏好行为。综上，基于偏好行为的用户相似度( $\sin ^ { \mathrm { t a g } } _ { \left( \mathrm { u _ { i } , u _ { j } } \right) }$ )为

$$
\sin ^ { \mathrm { { u g } } } _ { ( \mathbf { u } _ { i } , \mathbf { u } _ { j } ) } = \cos \left( u _ { i } , u _ { j } \right) = \frac { \sum _ { i , j \epsilon ( I _ { u _ { i } } \cap I _ { u _ { j } } ) } \mathbf { W } _ { i t e m _ { i } } \cdot \mathbf { W } _ { i t e m _ { j } } } { \sqrt { \sum _ { i \in ( I _ { u _ { i } } \cap I _ { u _ { j } } ) } \mathbf { W } _ { i t e m _ { i } } } ^ { 2 } \sqrt { \sum _ { j \epsilon ( I _ { u _ { i } } \cap I _ { u _ { j } } ) } \mathbf { W } _ { i t e m _ { j } } } ^ { 2 } }
$$

其中： $I _ { u _ { i } } \cap I _ { u _ { j } }$ 表示用户 $u _ { i }$ 和 $\boldsymbol { u } _ { j }$ 的共同评分项目集合。

b）用户社交圈的相似度。

在社交网路中，如果两个用户拥有重叠程度很高的社交圈，那他们很可能会建立朋友关系。为了利用社交圈发现潜在朋友，首先需要识别社交圈，即实现对朋友的自动分组。如果两个用户之间“朋友圈”交集集合越大，这两用户之间兴趣爱好生活方式越相似。文中通过计算两个用户的共同朋友数目来确定用户社交圈的相似性( $s i m ^ { s o c i a l } ( u _ { i } , u _ { j } )$ )为

$$
s i m ^ { s o c i a l } _ { ( u _ { i } , u _ { j } ) } = \frac { \left| f r i e n d _ { u _ { i } } \cap f r i e n d _ { u _ { j } } \right| } { \left| f r i e n d _ { u _ { i } } \cup f r i e n d _ { u _ { j } } \right| }
$$

其中： $f r i e n d _ { u _ { i } }$ 和 $f r i e n d _ { u _ { j } }$ 表示用户 $u _ { i }$ 和 $\boldsymbol { u } _ { j }$ 的朋友集合。

# 2 基于链路预测的有向性互动影响力和用户信任的推荐算法

RUTI-CF算法分为两个具有递进性的推荐过程，首先以目标用户进行聚类分析形成以目标用户为中心的相似用户集合，再从相似用户集合中寻找值得信任的相似用户进行推荐。算法模型如图1所示。

用户偏好行 用户社交圈  
为的相似度 的相似度聚类分析处理相似朋友圈链路预测方法、评分信任分析  
用户有向性  
互动影响力 用户信任度↓值得信任的相似用户推荐

# 2.1融合偏好行为和社交圈的用户相似度

在现实生活中，人们往往会更愿意接受朋友圈中好友的推荐以及更爱和自己个性爱好相似的推荐。相似度计算的改进优化是推荐算法的关键所在。随着社交网络的不断发展，交互用户在扮演者越来越活跃的角色，本文在考量用户相似度的计算不限于平常的购买、评分和标签行为，还会考虑朋友圈中喜爱偏好相投的其他线上虚拟好友用户的偏好行为。用户的抉择在一定程度上会受到这些用户的影响。

基于上述原因，本节提出了一种结合用户偏好行为和社交圈的相似性度量。一方面由于用户一标签数据、项目一标签的稀疏性，决定了用户相似度也会出现稀疏性的缺陷；另一方面从基于用户社交圈的相似性分析考量同一个社交圈内的用户之间的联系更为紧密，在社交网络中，用户的偏好行为和社交圈对计算用户相似度的贡献都是不可小。综上相关研究，当基于用户偏好行为的相似值( $^ { * } s i m ^ { t a g } { } _ { ( u _ { i } , u _ { j } ) }$ )和基于社交圈的相似值( $s i m ^ { t a g } { } _ { ( u _ { i } , u _ { j } ) }$ )都存在时，本文则用调和平均值去融合两者；反之，则取两个相似值的最大值。这样有效地缓解了用户相似矩阵的数据稀疏性。融合计算如式(7)所示。

$$
\begin{array} { r } { \sin _ { ( u _ { i } , u _ { j } ) } = } \end{array}
$$

$$
\left\{ \begin{array} { c c } { \displaystyle \frac { 2 ^ { * } \sin ^ { \mathrm { t a g } } ( u _ { i } , u _ { j } ) ^ { * } \sin ^ { \mathrm { s o c i a l } } ( u _ { i } , u _ { j } ) } { \sin ^ { \mathrm { t a g } } ( u _ { i } , u _ { j } ) } } & { \displaystyle \sin _ { ( u _ { i } , u _ { j } ) } ^ { \mathrm { t a g } } > 0 \mathbb { E } \sin _ { ( u _ { i } , u _ { j } ) } ^ { \mathrm { s o c i a l } } > 0 } \\ { \displaystyle \operatorname* { m a x } \left\{ \sin ^ { \mathrm { t a g } } \left( u _ { i } , u _ { j } \right) , \sin ^ { \mathrm { s o c i a l } } \left( u _ { i } , u _ { j } \right) \right\} } & { \displaystyle \sharp \sharp \mathbb { H } \mathbb { H } ^ { * \pm } \mathbb { H } ^ { * } } \end{array} \right.
$$

基于以上的用户相似度计算方法本文可以得到社交网络中每个用户的以自我为中心的小型相似用户网络结构圈。下面本文将用综合用户评分行为的信任关系和用户节点影响力的推荐信任衡量这个圈中的每个相似用户的推荐信任值。

# 2.2综合有向性互动影响力和用户信任的推荐信任度

# 2.2.1用户信任度

1)用户活跃度

推荐系统中用户活跃度[10]存在较大的差异，用户活跃度可以用于隐性推断用户对未评分项目感兴趣的可能性。用户的活跃度越高，用户对未评价项目不感兴趣的可能性越大。所以本文引入用户活跃度可以作为衡量用户评分行为可信度的一个因子。本文提出的用户活跃度( $\mathrm { A c t i v i t y } _ { u , i t e m }$ )定义为

$$
\mathrm { A c t i v i t y } _ { u , i t e m } = { \frac { \sum { n _ { u , i t e m } } } { n _ { u , i t e m } } } \log { \frac { u s e r } { u s e r _ { i t e m } } }
$$

其中： $n _ { u , i t e m }$ 为用户 $\mathrm { ~  ~ u ~ }$ 评分某一项目item的次数；user表示用户总数； $u s e r _ { i t e m }$ 表示评分项目item的用户数目。所以，用户 $u$ 评分项目item的次数越多，表示他在这一领域的活跃度越高，权威性也会越大，同时若用户的好友评分项目次数越多，代表此用户在此项目的评论影响力越大，传播给其他好友的影响较大，同时说明用户对该项目所属领域越了解，评分的可信度越高;反之则评分可信度越低。

2)用户 $u$ 对项目item的评分客观度

一个用户的信任程度比较高，只是表明这个用户值得信任，他的评分整体可信度较高而已，并不代表用户每次评分都那么可信和客观，这个问题反映在表现为用户关于单个项目评价的可信性。考虑到用户打分时的随意性也会影响评分的客观公正，所以用户 $\mathrm { ~  ~ u ~ }$ 的评分客观度( $\cdot O b j e c t i \nu i t y _ { u , i t e m }$ )定义如下：

$$
O b j e c t i \nu i t y _ { u , i t e m } = 1 - \frac { \left| r _ { u , i t e m } - \overline { { r _ { i t e m } } } \right| } { r _ { m a x , i t e m } - r _ { m i n , i t e m } }
$$

其中： $r _ { u , i t e m }$ 表示用户 $\mathrm { ~  ~ u ~ }$ 对项目item的评分值； $\overline { { r _ { i t e m } } }$ 则表示社交网络中所有的用户对此项目item 的评分平均值； $r _ { m a x , i t e m }$ 代表所有的用户对此项目评分数据中的最高评分值； $r _ { m i n , i t e m }$ 表示所有的用户对项目评分数据中的最低评分值。用户 $\mathrm { ~  ~ u ~ }$ 关于项目的评价越接近评分均值，则用户的评分客观度越接近1。$O b j e c t i v i t y _ { u , i t e m }$ 取值在0\~1之间。

由用户活跃度和用户评分客观度可以计算用户 $\mathrm { ~  ~ u ~ }$ 在某个领域的评分准确度，用户 $\mathbf { \Omega } _ { u }$ 在项目item的活跃度越大，评分越客观，那么他在项目item的评分价值性越高，他在这个领域越值得被其他用户信任。所以用户 $\boldsymbol { u }$ 在项目item上的评分可信度(Scored $\underline { { \mathbf { V } } } \mathrm { a l u e } _ { u , i t e m }$ )定义为

$$
\underline { { \phantom { 1 } } } _ { u } \mathrm { l } \mathrm { u } \mathrm { e } _ { u , i t e m } = \mathrm { A c t i v i t y } _ { u , i t e m } \mathrm { \phantom { \ast } } ^ { \ast } O b j e c t i \nu i t y _ { u , i t e m }
$$

得出被推荐用户 $\boldsymbol { u } _ { j }$ 对于目标用户 $u _ { i }$ 之间的信任度（2 $\left( \begin{array} { l } { T r u s t ^ { r a t i n g } \left( u _ { i } , u _ { j } \right) } \end{array} \right)$ )为

$$
T r u s t ^ { r a t i n g } \left( u _ { i } , u _ { j } \right) = \frac { \sum _ { \substack { i t e m \in \left( I _ { u _ { i } } \cap I _ { u _ { j } } \right) } } \mathrm { S c o r e d \Pi \_ V a l u e } _ { u _ { j } , i t e m } } { \left| I _ { u _ { i } } \cap I _ { u _ { j } } \right| }
$$

其中： ${ \cal I } _ { u _ { i } } \cap { \cal I } _ { u _ { j } }$ 表示用户 $u _ { i }$ 和 $\boldsymbol { u } _ { j }$ 的共同评分项目集合。

# 2.2.2基于链路预测的有向性用户互动影响力

在社交网络中，本文可以将有共同项目的用户认为是邻居节点，则两个邻居节点的度 $d _ { u _ { i } u _ { j } }$ 定义为

$$
d _ { u _ { i } u _ { j } } = { \left\{ \begin{array} { l l } { 1 \mathcal { I } _ { u _ { i } } \cap I _ { u _ { j } } \neq \emptyset } \\ { 0 \mathcal { I } _ { u _ { i } } \cap I _ { u _ { j } } = \emptyset } \end{array} \right. }
$$

其中： $I _ { u _ { i } }$ 和 $I _ { u _ { j } }$ 分别用户 $u _ { i } , u _ { j }$ 的项目集合，表示当 $I _ { u _ { i } } \cap I _ { u _ { j } } \neq \emptyset$ 表示用户 $u _ { i } , u _ { j }$ 有共同评分项目，那么会存在一条从节点 $u _ { i }$ 指向$\boldsymbol { u } _ { j }$ 的有向边时，它们之间的节点度 $d _ { u , u _ { j } } = 1$ ，反之两个节点的

节点度 $d _ { u _ { i } u _ { j } } = 0$ 。

用有向带权图 $\mathbf { G } \ = \ ( \mathrm { V } , \mathrm { E } , \mathrm { I } )$ 作为社会网络的抽象表述,其中： $\mathrm { ~ v ~ }$ 代表网络中的所有节点集合，用户之间的具体关系则用每节点之间的连边表示；E代表边的集合。在网络图形中，边权值 $I _ { i j }$ 表示节点i指向节点j的互动影响值。给定社交网络G，本文的目标是通过对社交网络中各好友之间互动影响力的分析来预测尚未建立信任关系的两个人之间建立信任关系的可能性。所以用户之间的互动影响关系如图2所示。

![](images/e8ed96324c07dd1e540d997483abf0f64425f156c326bc1aeb6654861e33a983.jpg)  
图2互动影响力图  
Fig.2Interactive influence diagram

如图2所示，本文可以得出节点a传播至节点b的互动影响力 $\boldsymbol { I } _ { a b }$ 与节点b传播至节点a的互动影响力 $I _ { b a }$ 是不平衡的，体现了互动影响力的有向性。同时，节点a对节点c产生了单向的互动影响力 $I _ { a c }$ ，由于互动影响力的传递性，本文可以得知节点b会对节点c产生一定的互动影响力 $I _ { b c }$ 。本文可以计算 $I _ { b c }$ 来预测节点b至c产生信任链接的可能性；节点间的互动影响力在会增强节点间的信任关系的建立。

本文把用户节点的评分项目类别看做它的兴趣偏好点，这样用户节点的共同评分项目类别可以当作用户之间的相同兴趣偏好点，目标用户可以通过相同兴趣偏好点开辟一条兴趣偏好路径进而影响与其可能产生信任关系的用户；所以本文可以计算共同评分项目个数所占比例来确定有向性影响因子，以表现用户之间相互影响的差异性。当目标用户与其可能产生信任关系的用户拥有越多的共同评分项目，而且共同评分项目占目标用户的评分项目总数目的比例越高，说明目标用户有多条兴趣偏好路径倾向于对此用户产生影响，反之产生的影响因子越低。有向性影响因子( $\stackrel { \triangledown } { \boldsymbol { \gamma } } _ { ( u _ { i } , u _ { j } ) }$ )的定义公式为

$$
\gamma _ { ( u _ { i } , u _ { j } ) } = \frac { \left| I _ { u _ { i } } \cap I _ { u _ { j } } \right| } { \left| I _ { u _ { i } } \right| }
$$

其中： $I _ { u _ { i } } \cap I _ { u _ { j } }$ 表示用户 $u _ { i }$ 和 $\boldsymbol { u } _ { j }$ 的共同评分项目集合。

本文提出的互动影响力考量节点b和c产生信任传递链接的可能性时不仅考虑被预测两个节点之间的共同邻居的节点度数，同时还要考虑了被预测节点与共同邻居组成的小型网络结构的紧密程度。所以本文利用节点引力指数( $S _ { ( u _ { i } , u _ { j } ) }$ )来预测节点 $u _ { i }$ 和 $u _ { j }$ 的互动影响力，它的公式定义为

$$
S _ { ( u _ { i } , u _ { j } ) } = \sum _ { a \epsilon \varphi ( u _ { i } ) \cap \varphi ( u _ { j } ) } e _ { a } \Bigg / _ { k _ { a } }
$$

$$
e _ { a } = \sum _ { u _ { i } \epsilon C } d _ { a u _ { i } }
$$

$$
k _ { a } = \sum _ { u _ { i } \epsilon D } d _ { a u _ { i } }
$$

其中： $e _ { a }$ 为节点a与其他共同邻居之间及与节点 $u _ { i }$ 和 $\boldsymbol { u } _ { j }$ 的链接数； $d _ { a u _ { i } }$ 为节点a至节点 $u _ { i }$ 的节点度； $k _ { a }$ 是节点 $u _ { i }$ 和 $\boldsymbol { u } _ { j }$ 的

共同邻居节点的节点度； $C$ 为节点 $u _ { i }$ 和 $\boldsymbol { u } _ { j }$ 以及它们之间的共同邻居组成的小型网络用户节点集合； $D$ 为整个社交网络中所有用户节点集合。

![](images/05db7bca729e8a9ae1e4f9759f46a24b4f8eea5e6403c9d103aa0c410684fbe2.jpg)  
图3有向性影响系数示意图点  
Fig.3Schematic point of directional influence coefficient

数。因为考虑到用户节点相互影响的差异性，本文对影响力度量方法进行修正，所以有向性的互动影响力( $I ^ { D i r } { } _ { ( u _ { i } , u _ { j } ) }$ ）定义如下：

$$
I ^ { D i r } { } _ { ( u _ { i } , u _ { j } ) } = \gamma _ { ( u _ { i } , u _ { j } ) } * S _ { ( u _ { i } , u _ { j } ) }
$$

其中： $S _ { ( u _ { i } , u _ { j } ) }$ 是节点 $u _ { i }$ 和 $\boldsymbol { u } _ { j }$ 之间的互动影响力； $\gamma _ { ( u _ { i } , u _ { j } ) }$ 是有向影响系数；两者的乘积得到有向性的互动影响力即社交网络G中的节点b对c产生的有向边权值 $I _ { b c }$ (虚线表示)。

如图2所示，在由节点 $\mathbf { \Omega } _ { a }$ 、 $b$ 、 $\boldsymbol { \mathbf { \mathit { c } } }$ 组成的小型社交网络 $A$ 和由节点c、d、e、f的小型社交网路 $B$ 中，本文用式(14)式计算节点 $b$ 对节点 $\boldsymbol { \mathbf { \mathit { c } } }$ 的产生信任链接的可能性大小为： $2 / 3 ( \mathrm { a } ) { = } 2 / 3$ ，同样的方法得到节点 $d$ 对节点 $\boldsymbol { \mathbf { \mathit { c } } }$ 的产生信任链接的可能性大小为 $: 3 / 4 ( \mathrm { f } ) + 2 / 3 ( \mathrm { e } ) = 1 7 / 1 2$ ，节点 $b$ 、c、 $d$ 的交互行为如图3所示。根据式(13)本文可以得到节点 $b$ 到节点 $\mid c \mid$ 的有向性影响因子为 $2 / 7$ ，节点 $d$ 到节点 $\boldsymbol { \mathscr { c } }$ 的有向性影响因子为 $3 / 7$ ，最后本文根据式(17)可得节点 $b$ 对节点 $\mathbf { \Psi } _ { c }$ 的有向性的互动影响力为： $2 / 3 \times 2 / 7 { = } 4 / 2 1$ ；同时得到节点 $d$ 到节点 $\mathbf { \Psi } _ { c }$ 的节点 $d$ 到节点 $\mathbf { \Psi } _ { c }$ 的： $1 7 / 1 2 \times 3 / 7 { = } 1 7 / 2 8$ 。所以当社交网络B中节点交互行为比社交网络A更为密切，从而社交网络B的结构比A更为紧密，节点 $d$ 对节点 $\mid c \mid$ 相比于节点 $b$ 对节点 $\boldsymbol { \mathscr { c } }$ 更容易建立信任关系。

# 2.2.3综合推荐信任度

综合前文研究，提出融合在线社交网络用户信任$\left( T r u s t ^ { r a t i n g } \left( u _ { i } , u _ { j } \right) \right.$ )和互动影响力( $I ^ { D i r } { } _ { ( u _ { i } , u _ { j } ) }$ )的推荐信任度( $t r u s t _ { ( u _ { i } , u _ { j } ) }$ ）计算方法如下：

$$
t r u s t _ { ( u _ { i } , u _ { j } ) } = \alpha T r u s t ^ { r a t i n g } \left( u _ { i } , u _ { j } \right) + ( 1 - \alpha ) I ^ { D i r } { } _ { ( u _ { i } , u _ { j } ) }
$$

其中： $0 \leq \alpha \leq 1$ ，用于权衡用户信任和互动影响力对推荐信任值的影响程度， $\mathfrak { a }$ 数值具有不确定性，将视社交网络的具体情况而定。

# 3 基于链路预测的有向性互动影响力和用户信任的推荐

本文按照融合偏好行为和社交圈的相似值计算方法求得用户相似值，利用用户相似值找出。用户的"朋友圈”，获取目标用户的近邻集合NB。采用如下方法产生推荐的结果：首先假设目标用户 $\mathrm { ~  ~ u ~ }$ 的"朋友圈"组成的集合为NB，对于任一 $\nu _ { i } \in N B$ ，计算目标用户 $\mathrm { ~  ~ u ~ }$ 与朋友圈内好友 $\nu _ { i }$ 之间融合有向性互动影响力和用户信任的综合推荐信任值，利用top-k 法获取目标用户的值得信任的近邻集合为： $\mathrm { T N B } = \{ u _ { 1 } , u _ { 2 } , . . . . , u _ { k } \}$ ，对于任一 $u _ { i } \in T N B$ ，获得其历史评价的项目集合 $I _ { i }$ $( \mathrm { i } { = } 1 , 2 , { \ldots } , \mathbf { k } )$

组成新的集合，将这个新的项目集合Recommend-Item推荐给用户。

# 4 实验结果及分析

# 4.1实验数据集

本实验采用的实验数据是Last.fm数据集。实验评估前，针对Last.fm数据集，要求每个用户至少给10个音乐家标注过标签。经过筛选最后保留881个用户及其所有的好友信息记录和标签行为记录。其次，将这两组数据都划分为训练集和测试集两部分。本文使用交叉验证法共进行五次实验，得到五组实验结果，然后求出平均值作为最后的结果。

# 4.2 实验评估指标

准确率(precision)、召回率(recall)和F1-measure 是推荐系统中常用的三个重要指标。准确率表征的是项目物体被成功推荐的比例,准确率的值越大，推荐模型越好;召回率则指的是推荐出的好友数量，占测试数据当中的好友数量的比例，召回率的值越大，模型效果越好；F1-measure 指标则是综合准确率和召回率这两个指标衡量，当两个指标都是越高越好，但是在一些情况下两者会有矛盾，此时就需要F1-measure 指标来进行衡量，当F1-measure指标具有较高的值时，说明此算法的推荐效果更优。计算公式如下：

$$
\mathrm { p r e c i s i o n } = \frac { n _ { l i k e } } { n _ { r e c o m m e n d } }
$$

$$
\mathrm { r e c a l l } = \frac { n _ { l i k e } } { n _ { t e s t } }
$$

$$
\mathrm { F l - m e a s u r e } = 2 ^ { \ast } \frac { \mathrm { p r e c i s i o n ^ { \ast } r e c a l l } } { \mathrm { p r e c i s i o n + r e c a l l } }
$$

其中： $n _ { r e c o m m e n d }$ 表示给推荐项目集合的元素个数； $n _ { t e s t }$ 表示测试集中物体的数量； $n _ { l i k e }$ 表示在推荐的项目中受该用户喜欢的项目总数。

# 4.3 实验结果分析

本实验需对 $\mathfrak { a }$ 和K的合理取值进行验证，然后在合理的$\mathfrak { a }$ 值使得实验结果最优的情况下，将本文提出的算法与其他推荐算法进行性能比较，得出结论。

1)权重值 $\alpha$ 对算法的影响

分别将 $\mathfrak { a }$ 的取值为0.00.10.2,...1.0进行实验。为了消除邻居用户数量对推荐结果的影响，实验过程中依次将邻居用户的数量设为2,3,4,...,10,进行9组实验。表1表示在Last.fm数据集上，不同的 $\mathfrak { a }$ 对RUTI-CF算法的准确率的影响。可以看出不同的 $\textbf { \em a }$ 值对本文基于链路预测的有向性互动影响力和用户信任的推荐算法(RUTI-CF 算法)准确率的影响。从表1中可以看出，当K一定时，随着 $\mathfrak { a }$ 从0.0开始不断增加，RUTI-CF算法准确率波动的趋势总体上是一致的，都是呈现先平缓上升，到达最高点，

表1不同 $\mathfrak { a }$ 对RUTI-CF算法的准确率的影响  
Table1Effect of different $\mathfrak { a }$ on accuracy ofRUTI-CF algorithm   

<html><body><table><tr><td></td><td>0</td><td>0.1</td><td>0.2</td><td>0.3</td><td>0.4</td><td>0.5</td><td>0.6</td><td>0.7</td><td>0.8</td><td>0.9</td><td>1.0</td></tr><tr><td>Top-2</td><td>0.1551</td><td>0.1604</td><td>0.1610</td><td>0.1622</td><td>0.1632</td><td>0.1698</td><td>0.1723</td><td>0.1621</td><td>0.1597</td><td>0.1504</td><td>0.1109</td></tr><tr><td>Top-3</td><td>0.2201</td><td>0.2291</td><td>0.2301</td><td>0.2434</td><td>0.2311</td><td>0.2506</td><td>0.2557</td><td>0.2272</td><td>0.2237</td><td>0.2117</td><td>0.1817</td></tr><tr><td>Top-4</td><td>0.3433</td><td>0.3512</td><td>0.3523</td><td>0.3567</td><td>0.3588</td><td>0.3599</td><td>0.3669</td><td>0.3315</td><td>0.3206</td><td>0.3008</td><td>0.1653</td></tr><tr><td>Top-5</td><td>0.4018</td><td>0.4122</td><td>0.4616</td><td>0.4656</td><td>0.4717</td><td>0.4837</td><td>0.5272</td><td>0.4589</td><td>0.4789</td><td>0.5537</td><td>0.2966</td></tr><tr><td>Top-6</td><td>0.4218</td><td>0.5796</td><td>0.6012</td><td>0.6082</td><td>0.6271</td><td>0.6376</td><td>0.6579</td><td>0.5989</td><td>0.6366</td><td>0.6366</td><td>0.4704</td></tr><tr><td>Top-7</td><td>0.5154</td><td>0.4276</td><td>0.4204</td><td>0.4213</td><td>0.4301</td><td>0.4321</td><td>0.4381</td><td>0.4112</td><td>0.4019</td><td></td><td>0.3904 0.2148</td></tr><tr><td>Top-8</td><td>0.3872</td><td>0.3889</td><td>0.3981</td><td>0.3915</td><td>0.3959</td><td>0.4008</td><td>0.4035</td><td>0.3779</td><td>0.3743</td><td>0.3717</td><td>0.2306</td></tr><tr><td>Top-9</td><td>0.3109</td><td>0.3111</td><td>0.3210</td><td>0.3219</td><td>0.3267</td><td>0.3317</td><td>0.3549</td><td>0.3093</td><td>0.2945</td><td>0.2857</td><td>0.1633</td></tr><tr><td>Top-10</td><td>0.2690</td><td>0.2696</td><td>0.2807</td><td>0.2817</td><td>0.2877</td><td>0.2899</td><td>0.3064</td><td>0.2754</td><td>0.2708</td><td></td><td>0.2655 0.1521</td></tr></table></body></html>

再平缓下降的趋势。当 $\mathfrak { a }$ 取值为0.6时，推荐模型的准确率的值是最好。即在本文的推荐算法中，用户信任和用户之间的互动影响力对最后的推荐结果的影响比例是3:2。说明用户在进行项目选择时，在相似用户集成的"朋友圈"中信任好友的评分对其的影响还是比用户之间的互动影响力的影响程度要大，当 $\mathfrak { a }$ 在 $0 . 8 { \sim } 1 . 0$ 内变化时，推荐准确率急剧下降。特别是当 $\mathfrak { a } = 1 . 0$ 时，即只考虑用户节点影响力时，与 $\mathfrak { a } = 0 . 9$ 时相比较，推荐推荐率下降 $10 \% { \sim } 2 0 \%$ ，这说明不考虑互动影响力，单独考虑用户信任时，推荐准确率将大大下降，这表明用户之间的互动影响力对于用户建立信任关系有很大的促进加强作用。

2)Top-K取值对算法的影响

根据本文产生推荐的方法，将K的取值设为 $2 , 3 , 4 , . . . , 1 0$ 实验观察推荐准确率随着K值不断变化的规律。同样从表1的实验结果数据得知，不管权重值 $\textbf { \em a }$ 的取值，随着K值的不断增加，RUTI-CF 算法准确率呈现先上升，等达到最高峰，再下降的趋势。

在本文实验环境下，当K的值在2\~5内变化时，算法准确率不断上升；当 $\mathrm { K } { = } 6$ 时，准确率值最高；当K的值在6\~10区间内变化时，推荐的准确率又开始下降。因此，实验说明邻居数量的大小能够推荐的质量，但不是邻居数量越多，推荐的质量越好。对于本实验的数据环境而言，当目标用户的近邻取值为6时，实验结果最好。

# 3)不同算法的推荐效果比较

为了验证本文提出推荐算法的有效性，将RUTI-CF算法与其他算法进行对比分析，分别是FT-CF 算法(hybridcollaborative filtering recommendation algorithm based onfriendshipsandtags,基于好友关系和标签的混合协同过滤算法）[1l]、FRSN-CF 算法(research on friend recommendationmethods in socialnetworks，社交网络中的好友推荐方法研究)[12]、Trust_CF 算法代表本文只考虑在线社交网络用户信任的算法、InfluenceCF算法代表本文只考虑用户之间互动影响力的推荐算法。通过实验，得到以上方法的准确率值和F1-measure指标值，分别如图4和5所示。

如图4和5所示，随着K值的不断增加，各种算法在指标上的变化规律趋于一致。对于准确率，随着K值得增加，其呈现先增后减的趋势，验证上文的 $\mathrm { K } { = } 6$ 时实验效果最好的结论；随着K值的增加，召回率呈现不断增长的趋势，但是增长的幅度由快到慢，逐渐趋于平缓。

本文的RUTI-CF 算法在准确率值和F1-measure 指标值上都要优于其他算法。一方面，与FT-CF算法对比，虽然FT-CF算法也从好友关系和标签两个角度综合考虑用户之间的相似度，但是该算法的准确率值和F1-measure指标值均低于RUTI-CF算法，说明本文使用融合用户信任和互动影响力考察用户朋友圈中综合推荐信任值更加精确；另一方面，与FT-CF算法对比，这个算法仅仅从用户挖掘的标签信息出发，衡量用户的兴趣偏好，且本文算法在找出自己相似用户即"朋友圈"时使用用户偏好模型计算用户基于标签行为的相似度；与 FRSN-CF算法对比，这种算法利用社交网络中用户的好友交互行为，为用户推荐潜在的好友。但是实验结果表明，本文的RUTI-CF 算法的准确率值和F1-measure 指标值都优于这两个算法，说明在社交网络的朋友圈中，仅仅考虑用户的信任关系具有一定的片面性，如果同时考虑用户之间的有向性互动影响力，那么推荐的效果将更为优越。

![](images/61542e0ad6eb7fc3169ec33e1e0b1bc7fe5a3b0e7f14d1fee25b0f61ee4d3c21.jpg)  
图4不同K值情况下各算法的准确率

![](images/97b11b7c8456b4cee90d44524e781d898640d94d5c2ea5141e54ed17c3676faf.jpg)  
Fig.4Accuracy of each algorithmunder differentKvalues   
图5不同K值情况下各算法的F1-measure 值Fig.5Fl-measure value of each algorithm under different K values

# 5 结束语

从实验结果看，RUTI-CF算法具有良好的推荐性能，说明在社交平台中，融合在线社交网络用户信任和用户影响力能够更加更加全面地考察用户之间的综合推荐信任度。且本文在衡量用户节点无向性互动影响力，将其与有向性影响系数结合，提出有向性互动影响力，得到的综合推荐信任更加精确。本文推荐模型一方面从直接角度出发考虑用户之间的社交评分信任，另一方面从间接角度通过衡量用户节点的互动影响力对用户节点产生信任关系的可能性的影响程度，使得本实验更符合社交逻辑。因此推荐的准确率和召回率更高。

本文主要讨论静态网络的协同过滤推荐算法，随着系统中用户、项目和标签的数量持续增多，数据稀疏问题等会导致推荐算法的性能降低。结合时序网络的特征，分析总结出在不同的时间窗上用户的相似性特点，从而提出在动态网络中有效的推荐算法模型是本文中进一步研究的重点。

# 参考文献：

[1]李良，董宇欣，赵春晖，等．融合用户信任的协同过滤推荐算法[J]. 小型微型计算机系统,2017,38(5):951-955.(LiLiang,Dong Yuxin, Zhao Chunhui,et al. Collaborative filtering recommendation algorithm based on user trust[J].Journal of Chinese Computer Systems,2O17,38 (5): 951-955. )   
[2]丁小焕，彭甫鎔，王琼，等．融合朋友关系和标签信息的张量分解推 荐算法[J].计算机应用，2015,35(7):1979-1983.(Ding Xiaohuan, Peng Wei,Wang Qiong,et al.A tensor decomposition recommendation algorithm combining friend relationship and label information [J]. Journal ofComputer Applications,2015,35(7):1979-1983.)   
[3]Zhu Xiaofeng,Zhang Shichao,Jin Zhi,et al.Missing value estimation for mixed-attribute data sets [J].IEEE Trans on Knowledge Data Engineering,2011,23(1):110-121.   
[4]Liben-Nowell D,Kleinberg J.The link prediction problem for social networks[Cl// Proc of the 12th International Conferenceon Information and Knowledge Management.New York:ACM Press,2003:   
556-559. [5]谢锐，郝志峰，刘波，等．非对称信息在链接预测中的应用[J].计 算机应用,2018,38(6):1698-1702,1708.(Xie Rui,Hao Zhifeng,Liu Bo,et al.Application of asymmetric information in link prediction [J]. Computer Applications,2018,38(6):1698-1702,1708.) [6]Schall D.Link prediction in directed social networks [J].Social Network Analysis& Mining,2014,4(1):157 [7]Butin E,Kaya M,Alhajj R.Extension of neighbor-based link prediction methods for directed,weighted and temporal social networks [J].Information Sciences,2018 (10):152-165. [8]东昱晓，柯庆，吴斌．基于节点相似性的链接预测[J].计算机科学,   
2011，38(7):162-164.(Dong Xiaoxiao,Ke Qing，Wu Bin.Link prediction based on node similarity [J]. Computer Science,2O11,38(7):   
162-164. )   
[9]Aizawa A.An information-theoretic perspective of tf-idf measures [C]// Proc ofInformation Processing& Management.2003.   
[10]曲朝阳，宋晨晨，任有学，等．结合用户活跃度的协同过滤推荐算法 [J]．东北电力大学学报，2017，37(5):74-79.(Qu Chaoyang，Song Chenchen,Ren Youxue et al.Collaborative filtering recommendation algorithm based on user activity degree [J].Journal of Northeast Electric Power University,2017,37(5):74-79.)   
[11]曾安，徐小强．基于好友关系和标签的混合协同过滤算法[J].计算 机科学，2017,44 (8):246-251.(Zeng An,Xu Xiaoqiang.Hybrid collaborative filtering algorithm based on friends relationship and label [J].Computer Science,2017,44(8): 246-251.)   
[12]吴昊，刘东苏．社交网络中的好友推荐方法研究[J].现代图书情报 技术,2015,31(1): 59-65.(Wu Hao,Liu Dongsu.Research on friend recommendation methods in social networks [J].Modern Library and Information Technology,2015,31(1):59-65.)