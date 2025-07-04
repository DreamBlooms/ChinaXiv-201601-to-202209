# 一种基于模式匹配度的用户移动规则挖掘及位置预测方法研究

张海涛a，蒋继飞ʰ，周欢b

(南京邮电大学a.地理与生物信息学院;b.通信与信息工程学院，南京 210003)

摘要：移动用户的位置预测可以有效地用于系统资源的时空分配，提高移动通信系统的资源利用率。传统的位置预测方法由于模式支持度计算方式不合理，存在预测精度偏低的问题。为此，提出了一种基于模式匹配度的用户移动规则挖掘及位置预测方法，并将其用于移动通信系统中，以基台覆盖范围网格为单元的用户位置预测。具体包括三个步骤：通过图的遍历挖掘用户移动模式、基于用户移动模式生成用户移动规则和依据用户移动规则进行位置预测。实验分析使用10个批次轨迹数据进行用户移动规则挖掘，结果表明，该方法挖掘出的用户移动规则数少、支持度高和置信度高，具有高精度的优点。

关键词：移动用户；位置预测；模式匹配度；用户移动规则中图分类号：TP311 doi: 10.3969/j.issn.1001-3695.2018.04.0280

Method of mining user mobile rule based on pattern matching degree and location prediction.

Zhang Haitaoa, Jiang Jifeib, Zhou Huanb (a.Collegeof Geographic& Biologic Information,b.Colegeof Communication& Information Technology，Nanjing University ofPosts&Telecommunications,Nanjing 21ooo3,China)

Abstract: The location predictionof mobileuseris effective forthe temporaland spatialallocationof systemresources,and it can improve theresource utilizationof the mobilecommunication system.The traditional location prediction method hasa problemof low prediction acuracydue to unreasonable calculation of support.Toovercome these challenges,this paper presented a method called mining user mobile rule basedon pattern matching degreeand location prediction.Itcan predict location withthebase coverage mesh as theunit for mobile users in mobilecommunication systems.The detailed procedure contained three phases: a) mining user mobile patters from graph traversal; b)generating user mobile rules fromuser mobile paters;c）predicting based onuser mobilerules.Finally，the conducted experiments on10 batches of trajectorydata demonstrate thatthis methodhas thecharacteristicsoffewerrules,highsupport,andhighconfidence than traditionalethods, and highly predict accuracy.

Key words: mobile user; location prediction; pattern matching degree; user mobile rule

# 0 引言

随着计算机技术和通信技术的发展，移动通信系统日益普及[12]。移动计算为人们在任何时间地点访问任何数据的需求提供了实现手段。它被视为计算机的热点领域[34]。移动计算具有移动性、网络多样性等特点[5\~7]。目前，以3G、4G为主的移动通信系统，具有服务用户庞大及数据服务类型多样性（如视频、声音、图像等）的特点。为保障服务的质量，需要对移动通信系统中的移动用户信息进行更加有效的管理。移动性位置管理也即移动用户的位置信息存储、更新和预测是移动通信系统管理的主要内容[8-II]。其中，移动用户的位置预测可以有效地用于系统资源的时空分配，以提高移动通信系统的资源利用率，并降低移动用户在基台覆盖范围网格（mesh）之间切换（handover）时产生的系统延迟及掉线[12\~14]，最终能够明显的提高移动通信网络的服务质量。

针对位置预测国内外学者提出了很多解决方法。文献[15,16]提出了一种GMM和LMM相结合的方法，使用GMM与LMM分别建立用户在基台覆盖范围网格间和基台覆盖范围网格内的移动模型，并基于移动用户的运动轨迹与移动模型的匹配，对移动用户的位置进行预测。文献[17lJeungHoyoung 和QingLiu等人利用Apriori算法对用户移动轨迹进行处理，提取出用户移动模式以此来进行用户位置预测。文献[18.19]中，

Morzy利用Aprior算法进行改进后生成关联规则，后来又依据改进的PrefixSpan算法提取出用户移动的频繁模式，通过对用户的频繁模式进行处理生成预测位置的用户规则。

但是上述方法存在共性问题是在用于用户位置预测的模式或规则其支持度计算方法都是采用简单的计数方式，用户位置预测的精度较低。不能对用户位置预测的高精度问题进行有效处理。而高精度是保证移动通信系统为移动用户高效分配系统资源的关键技术问题。因此本文提出一种基于模式匹配度的用户移动规则挖掘及位置预测方法研究。

# 1 位置预测方法的基本原理

首先，给出相关方法涉及的定义。

定义1 $G = < V , E >$ 表示移动通信系统中所有基台覆盖范围形成的有方向性的，无权重的图结构。假设T=<CI,C,C3..C">表示用户在基台覆盖范围内的移动路径即移动序列，每个 $C _ { \kappa }$ 网格，且连续的网格之间空间邻近。序列数据库D为 $< s i d , T >$ 的元组集合，其中 sid 为当前移动序列的id，T表示移动序列。假设 $L _ { \kappa }$ 为根据序列数据库挖掘出长度为K的用户移动模式集合，对每一个长度为K的用户移动模式检查其最后一个网格是否在G中有空间临近点，若有，将其添加到该用户移动模式，最终形成长度为 $\mathbf { K } { + } \mathbf { l }$ 的候选模式集合$C _ { K + 1 }$ 。根据定义3定义的支持度计算方式，计算出序列数据库D 对候选模式集合Ck+ 的支持度。设定支持度阈值为 Sup min ，去掉候选模式集合 $C _ { K + 1 }$ 中支持度小于 $S u p _ { \mathrm { m i n } }$ 候选模式，生成长度为 $\mathbf { K } { + } \mathbf { l }$ 的用户移动模式集合 $L _ { \scriptscriptstyle { K + 1 } }$ 。由此逐层搜索得出所有用户移动模式集合L。

定义2如果 $\textbf { \em x }$ 和y都是单独的字符或者空格， $\mathcal { S } ( x , y )$ 表示匹配 $\textbf { \em x }$ 和 $\mathrm { \Delta y }$ 后的得分函数，公式定义为

$$
\delta ( x , y ) = { \left\{ \begin{array} { l l } { 0 , } & { \mathrm { ~ x = y ~ } } \\ { 1 , } & { \mathrel { \not \equiv } 1 \not \equiv 1 } \end{array} \right. }
$$

如果S是一字符串，IS表示S的长度， $s [ i ]$ 代表字符串 S中的第i个字符（第一个字符串是S[1]，而不是S[0])。假设A是一条移动用户在运动时产生的以基台覆盖范围网格（mesh)为单元的路径（user path based mesh,UPM）（简称用户移动路径)，UPMB 就是包含在A里的一个用户移动模式（usermobilepattern,UMP)。对齐匹配排列 $X$ 把A和B写成可能包含空格的字符串 $\mathbf { A } ^ { ' }$ 和 $\boldsymbol { B ^ { \prime } }$ 。其中： $\mathbf { \vert A ^ { ' } \vert = \vert B ^ { ' } \vert }$ ；分别从 $\mathbf { A } ^ { ' }$ 和 $\boldsymbol { B ^ { \prime } }$ 中去除空格后就剩下A和 $\mathbf { B }$ 。那么满足该特征的一个对齐匹配排列 $X ^ { ' }$ ，其对齐匹配得分函数的公式定义为δ(X)=∑"=δ(A[i],B[i])。其中 $\mathbf { k } , \mathrm { m }$ 分别是 $\boldsymbol { B ^ { \prime } }$ 中第一个和最后一个非空格字符的索引号。排列 $X$ 的对齐匹配得分值实际上就是 $\boldsymbol { B } ^ { ' }$ 中第一个和最后一个非空格字符之间错误匹配字符的个数。因此，最佳的对齐匹配排列 $X ^ { ' }$ 应具有最小的对齐匹配得分值即最小的模式匹配度，我们将该最小得分称为totDist。用户移动路径（UPM）A对用户移动模式（UMP）的增量支持度（suppInc）的定义公式为

$$
s u p p I n c ( A , B ) = \left\{ \frac { 1 } { 1 + t o t D i s t } \ , \ { \mathrm { U P M ~ A } } { \boxplus } \right. \widehat { \boxplus } \mathrm { U M P ~ B }
$$

定义3D是存储所有用户移动路径即移动序列的数据库，B 是数据库D中包含的一个用户移动模式(UMP)，则数据库D对B的支持度定义为

$$
\begin{array} { r } { s u p p ( B ) = \sum s u p p I n c ( \alpha , B ) , \alpha \in D } \end{array}
$$

定义4定义 $M = < m _ { 1 } , m _ { 2 } , . . . , m _ { k - 1 } , m _ { k } > , ~ \mathrm { k } > 1$ 表示长度为 $\mathbf { k }$ 的用户移动模式（UMR)，则定义用户移动规则（UMR）为$R _ { i } = < m _ { 1 } , m _ { 2 } , . . . , m _ { i } > < m _ { i + 1 } , m _ { i + 2 } , . . . , m _ { k } > ( 1 \leq i < k )$ ，那么根据用户移动模式推导出的用户移动规则有：

当i=1时，R =<m >-→<m,m,.,.mk >;

当i=2时，R=<m,m>-m,m4..,.m >;

：

当i=k-1时，Rk_ =<m,m.,m- >-<mk >;

其中:箭头 $(  )$ 前面为规则头部，后面为规则尾部，定义该用户移动规则的置信度为

$$
c o n f ( M ) = \frac { s u p p ( \ - m _ { 1 } , m _ { 2 } , . . . , m _ { k } > ) } { s u p p ( \ - m _ { 1 } , m _ { 2 } , . . . , m _ { i - 1 } > ) } \times 1 0 0 \%
$$

其中:supp(M)表示为用户移动模式支持度。设定置信度阈值为$c o n f _ { \mathrm { m i n } }$ 。在产生所有可能的用户移动规则和其对应的置信度时，对于 $c o n f ( M ) \ge c o n f _ { \mathrm { m i n } }$ 的用户移动规则保存用来预测用户位置。

定义5给定用户移动轨迹 $P { = } { < } m _ { 1 } , m _ { 2 } { , } { \ldots } , m _ { i { - } 1 } >$ ， $m _ { i }$ 为用户所在的网格。用户移动规则为（204号 $R _ { j } = < a _ { 1 } , a _ { 2 } , . . . , a _ { j } >  < a _ { j + 1 } , . . . , a _ { k } >$ 用户移动规则集合为R 则$R _ { j } \subset R$ 。若 $R _ { j }$ 的头部包含于 $\mathrm { ~ \bf ~ P ~ }$ 中，且头部最后一个元素 $a _ { j }$ 与P 的最后一个元素 $m _ { i - 1 }$ 重合。则定义该用户移动规则为匹配规则，并且计算该匹配规则的支持度与置信度的和。那么据此定义可以从用户移动规则集中筛选出匹配规则集，并且依据匹配规则的支持度与置信度和对匹配规则集进行降序。假定$R _ { j } = < a _ { 1 } , a _ { 2 } , . . . , a _ { j } >  < a _ { j + 1 } , . . . , a _ { k } >$ 为经过降序处理的匹配规则集中首个匹配规则，则 $a _ { j + 1 }$ 即为用户移动轨迹P的下一个预测位置网格。

# 2 基于用户移动规则的预测方法

位置预测包含三个阶段：基于图的遍历挖掘出用户移动模式、从用户移动模式生成用户移动规则、基于用户移动规则进行位置预测。

# 2.1从图的遍历中挖掘用户移动模式

该阶段包括三个步骤，具体过程如下：

a）将研究的移动通信系统中的所有基台覆盖范围网格（Mesh)，转换成以有方向性的、无权重的图（graph）结构$G = < V , E >$ 存储表达的数据;b）收集以基台覆盖范围网格

（mesh）为单元的所有用户移动路径（UPM）数据，检查每条用户移动路径（UPM）中的连续网格元素（mesh）是否空间临近，并在序列数据库D中存储;c)设定挖掘用户移动模式(UMP)的支持度阈值 $( s u p p _ { \mathrm { m i n } } )$ ），使用算法UMPMining $( G , D , s u p p _ { \mathrm { m i n } } )$ 从序列数据库D中挖掘出长度逐级增加的用户移动模式 (UMP)集合。其中，使用增量支持度对候选模式进行支持度计数、使用支持度阈值从候选模式获取用户移动模式（UMP）、使用空间临近性搜索从长度为 $\mathbf { k }$ 的用户移动模式（UMP）得到长度为$( \mathbf { k } { + } 1 )$ 的候选模式（算法实现CandidateGeneration(）

算法1UMPMining()

输入：存储所有用户移动路径（UPM）的数据库D、有基台覆盖范围网格（mesh）对应的图结构， $\mathsf { v }$ 是G中所有节点集合，E是连接G中所有节点V的有向边的集合、挖掘用户移动模式（UMP）的支持度阈值 supP min 。输出：所有的用户移动模式（UMP）集合L。

1. $C _ { 1 } \gets$ 长度为1的候选模式

2． $\scriptstyle \mathbf { k } = 1$

3. $L = \mathcal { O }$ //用户移动模式（UMP）集合，初始值设置为空

4. While $\mathbf { C } _ { K } \neq \varnothing \cdot$

5．ForeachUPM $\alpha \in D ^ { \cdot }$ t

//c是长度为 $\boldsymbol { \mathsf { k } }$ 的候选模式，同时也是用户移动路径（UPM） $\alpha$ 的子序列

6. $C = \{ s \vert s \in C _ { K }$ && $s \subseteq \alpha \}$ （204号

7. Foreach $\mathbf { c } \in \mathbf { C } { \mathrm { : } }$ {c.count=c.count $^ { + }$ s.suppInc} $/ /$ 使 $\mathsf { \Omega } _ { \mathsf { c } }$ 的支持度递 增

8． $\} / /$ 得到长度为 $\boldsymbol { \mathsf { k } }$ 的用户移动模式（UMP）

9. $L _ { \kappa } = \{ c \vert c \in C _ { \kappa }$ &&c.cou $u t \geq s u p p _ { \operatorname* { m i n } } .$

10. $L = L \cup L _ { k }$ //把 $L _ { k }$ 添加到L中//生成长度为 $\mathbf { k } { + } \mathbf { 1 }$ 的候选模式

11. $c _ { k + 1 } \gets$ CandidateGeneration $\iota ( L _ { k } , G ) , \forall c \in C _ { k + 1 }$ $c . c o u n t = 0$

12. $\textbf { k } = \textbf { k } + \mathtt { 1 } \mathtt { j }$

13.return L

其中，算法UMPMining $( G , D , s u p p _ { \mathrm { m i n } } )$ 中第 5\~8行利用增量支持度，对候选模式进行支持度计数（对应定义2、定义3);第9、10行利用候选模式的支持度计数（c.count）与设定的支持度阈值 $( s u p p _ { \operatorname* { m i n } } ) ^ { \frac { \ d H } { \ d t } }$ )的比较，从候选模式集合中得到用户移动模式（UMP）集合；第11行内嵌的算法CandidateGeneration $( L _ { k } , G )$ ，该算法通过使用空间临近性搜索从长度为k的用户移动模式（UMP）得到长度为 $( \mathbf { k } { + } 1 )$ 的候选模式。

算法2 CandidateGeneration (

输入:长度为 $\mathbf { k }$ 的用户移动模式（UMP) $L _ { \ l _ { k } }$ 、所有基台覆盖范围网格(Mesh)对应的图结构 $G = < V , E > , \mathrm { { V } }$ 是G 中所有节点集合,E是连接G中所有节点 $\mathrm { \Delta V }$ 的有向边的集合。

输出：长度为 $\mathbf { k } { + } \mathbf { l }$ 的候选模式集合candidates。

1．Candidates $= \varnothing$ V/候选模式集合，初始值设置为空

2.Foreach $L = < l _ { 1 } , l _ { 2 } , . . . , l _ { k } > , L \in L _ { k } \ \{$ （204号

/\*对每个长度为 $\mathbf { k }$ 用户移动模式（UMP）L，获取其成员 $l _ { k }$ 在G中的邻近覆盖区域网格\*/

$$
N ^ { + } ( l _ { k } ) = \{ \nu | \nu \in V , e \in E , \exists e ( l _ { k } , \nu ) \}
$$

$/ *$ 在G中查找所有的节点 $\textbf { v }$ ，其同 $l _ { k }$ 在 $\mathbf { G }$ 中的节点具有有向连接边e。因此， $N ^ { + } ( l _ { k } )$ 是用户从 $l _ { k }$ 出发可能到达邻近覆盖区域网格（Mesh）的集合\*/

4.Foreach $\nu \in N ^ { + } ( l _ { k } )$ I

/\*对满足条件的所有节点 $\textbf { v }$ ，将其添加为模式L最后一个元素，从而生成相应的候选模式 $^ { * } /$

5. $C ^ { ' } = < l _ { 1 } , l _ { 2 } , . . . , l _ { k } , V >$ //将 $c ^ { \prime }$ 添加到候选模式集合candidates 中

6. Candidates $\gets$ Candidates U C' H   
7．return candidates

# 2.2从用户移动模式生成用户移动规则

该阶段包括四个步骤，具体过程如下：

a）设定挖掘用户移动规则（UMR）的置信度阈值(confmin）;b）选择长度大于1的所有用户移动模式（UMP)，生成一系列的用户移动规则（UMR）;c）扫描序列数据库D中的用户移动路径（UPM）数据，对生成的系列用户移动规则(UMR)，进行置信度的统计计算;d）按照设定的置信度阈值（204号 $( c o n f _ { \mathrm { m i n } } )$ ，逐一比较生成用户移动规则（UMR）的置信度，从而得到满足条件的用户移动规则集合R。

# 2.3基于用户移动规则的位置预测

该阶段包括三个步骤，具体过程如下：

a）取用于预测移动用户位置的、当前的用户移动路径(UPM)P;b）设定预测移动用户下一步可能到达的基台覆盖范围网格（mesh）的数量 $( \mathrm { ~ \bf ~ m ~ } ) \mathrm { ~ \bf ~ ; ~ c ~ } )$ 利用算法MobilityPrediction $( P , R , m )$ 对移动用户的下一步位置进行预测。

算法3 MobilityPrediction(

输入：用户当前的移动轨迹 $P { = } { < } m _ { 1 } , m _ { 2 } { , } { \ldots } , m _ { i { - } 1 } >$ 、用户移动规则（UMR）集合R、预测用户下一步可能到基台覆盖范围网格（mesh）的数量m。

输出：预测到达的基台覆盖范围网格（Mesh）集合，PMeshs。

1． PMeshs $= \emptyset$ //初始结果设置为空

2． $\textbf { k } = \textbf { 1 }$ //检查R中的所有规则

3. ForeachUMR $r ; < a _ { 1 } , a _ { 2 } , . . . , a _ { j } >  < a _ { j + 1 } , . . . , a _ { k } > \in R$ {/\*找出匹配规则的集合：如果规则的头部（head）包含于P中，且规则的头部（head）的最后一个元素 $( a _ { j } )$ 与 P 的最后一个元素 $( m _ { i - 1 } )$ （即用户当前所在的网格）重合，则该规则为匹配规则 $*$ 1

4. $\scriptstyle I f < a _ { 1 } , a _ { 2 } , \dotsc , a _ { j } > \subset P$ && $a _ { j } = m _ { i - 1 } \mathopen { } \mathclose \bgroup \left\{ \begin{array} { r l r l } \end{array} \aftergroup \egroup \right.$ （204号/\*把匹配规则的尾部（tai1）的第一个元素，以及匹配规则的置信度与支持度的和（同时考虑度量规则有效性的两个指标：supp，conf）保存到数组变量中\*/

5．TupleArr $a y [ k ] = ( a _ { j + 1 } , r . c o n f + r . s u p p )$   
6． $k = k + 1 ^ { \alpha \beta }$ （204  
//按照置信度与支持度的和，对数组变量进行降序  
7. TupleArray $ s o r t ($ TupleArray)  
8.index $= 0$ （204号  
9. while $( i n d e x < m$ & &index $<$ TupleArray.length){  
//从数组变量中选择前 $\mathsf { m }$ 个元素  
10．PMeshs $$ PMeshs $\cup$ TupleArray[index]  
11. $i n d e x = i n d e x + 1 ~ .$ ÷  
12．Return PMeshs

其中，算法 MobilityPrediction $( P , R , m )$ 中第 3-6行利用用户移动路径（UPM）P与用户移动规则（UMR）的匹配运算获取系列的匹配规则；第8行按照匹配规则的支持度、置信度，这两个衡量规则有效型的指标进行规则排序；第9\~11行从排序后的匹配规则中选择前 $\mathrm { ~ m ~ }$ 个结果；第12行返回最终的规则结果集合PMeshs，其中包含的基台覆盖范围网格（Mesh）即为预测的结果。

# 2.4实例分析

下面结合一个例子，介绍算法执行的基本过程。将图1所示的9个基台覆盖范围网格转换成对应的图结构，并检查表1所示的所有的用户移动路径（UPM）数据，并确定每条用户移动路径（UPM）中的连续网格元素均是空间临近，并将表1的结果保存到数据库D中。

![](images/c7142ba44cd7b933f1861af33d4452229f7a3191d9ead07b868dd2b60e2ed664.jpg)  
图1所有基台覆盖范围网格及其对应的图结构

表1存储用户移动路径的数据库  

<html><body><table><tr><td>ID</td><td>UPM</td></tr><tr><td>1</td><td><7,6,5,0></td></tr><tr><td>2</td><td><2,3.0,1></td></tr><tr><td>3</td><td><1,2,3,4,5,7,0></td></tr><tr><td>4</td><td><5,0,7,0,1></td></tr></table></body></html>

设定挖掘用户移动模式（UMP）的支持度阈值$( \operatorname* { s u p } \mathrm { p } _ { \operatorname* { m i n } } = 2 )$ ，并使用算法UMPMining（从序列数据库D中挖掘出长度逐级增加的用户移动模式（UMP）集合。

结果如表2\~5所示，C表示候选模式集合，L表示用户移动模式集合，数字表示长度。

表2长度为1的候选模式集合和长度为1的用户移动模式集合  

<html><body><table><tr><td colspan="2">C1</td><td colspan="2">L1</td></tr><tr><td>CAND</td><td>SUPP</td><td>PATTERN</td><td>SUPP</td></tr><tr><td><0></td><td>4</td><td><0></td><td>4</td></tr><tr><td><1></td><td>3</td><td><1></td><td>3</td></tr><tr><td><2></td><td>2</td><td><2></td><td>2</td></tr><tr><td><3></td><td>2</td><td><3></td><td>2</td></tr><tr><td><4></td><td>1</td><td><5></td><td>5</td></tr><tr><td><5></td><td>5</td><td><7></td><td>3</td></tr><tr><td><6></td><td>1</td><td></td><td></td></tr><tr><td><7></td><td>3</td><td></td><td></td></tr><tr><td><8></td><td>0</td><td></td><td></td></tr></table></body></html>

表3长度为2的候选模式集合和长度为2的用户移动模式集合  

<html><body><table><tr><td colspan="6">C2 L2</td></tr><tr><td>CAND</td><td>SUPP CAND</td><td>SUPP</td><td>CAND SUPP</td><td>PATTERN</td><td>SUPP</td></tr><tr><td><0,1></td><td>2 <2,1></td><td>0.33</td><td><5.4> 0</td><td><0,1></td><td>2</td></tr><tr><td><0,2></td><td>0 <2.0></td><td>0.7</td><td><5,3> 0</td><td><0,7></td><td>2</td></tr><tr><td><0.3></td><td>0 <2.3></td><td>2</td><td><5.0> 2.5</td><td><2.3></td><td>2</td></tr><tr><td><0.5></td><td>0 <3,2></td><td>0</td><td><5,7> 2</td><td><5,0></td><td>2.5</td></tr><tr><td><0,7></td><td>2 <3.0></td><td>1.25</td><td><5,6></td><td>0 <5,7></td><td>2</td></tr><tr><td><0.8></td><td>0 <3.5></td><td>0.5</td><td><7,6></td><td>1 <7,0></td><td>2.33</td></tr><tr><td><1,2></td><td>1 <3.4></td><td>1</td><td><7,5></td><td>0.5</td><td></td></tr><tr><td><1,0></td><td>0.17</td><td></td><td><7,0></td><td>2.33</td><td></td></tr><tr><td><1,8></td><td>0</td><td></td><td><7.8></td><td>0</td><td></td></tr></table></body></html>

表4长度为3的候选模式集合和长度为3的用户移动模式集合  

<html><body><table><tr><td colspan="6">C3</td></tr><tr><td>CAND</td><td>SUPP</td><td>CAND</td><td>SUPP</td><td>CAND</td><td>L3 SUPPPATTERNSUPP</td></tr><tr><td><0,1,2></td><td>0</td><td><5,0,1></td><td>0</td><td><7,0,1></td><td>1 <5,0,7> 2</td></tr><tr><td><0,1,0></td><td>0</td><td><5,0,2></td><td>0</td><td><7,0,2> 0</td><td></td></tr><tr><td><0,1,8></td><td>0</td><td><5,0,3></td><td>0</td><td><7,0,3> 0</td><td></td></tr><tr><td><0,7,8></td><td>0</td><td><5,0,5></td><td>0</td><td><7,0,5> 0</td><td></td></tr><tr><td><0,7,0></td><td>0</td><td><5,0,7></td><td>2</td><td><7,0,8></td><td>0</td></tr><tr><td><0,7,5></td><td>0</td><td><5,0,8></td><td>0</td><td></td><td></td></tr><tr><td><0,7,6></td><td>0</td><td><5,7,8></td><td>0</td><td></td><td></td></tr><tr><td><2,3,2></td><td>0</td><td><5,7,0></td><td>1</td><td></td><td></td></tr><tr><td><2,3,0></td><td>1.25</td><td><5,7,5></td><td>0</td><td></td><td></td></tr><tr><td><2.3,5></td><td>0.5</td><td><5,7,6></td><td>0</td><td></td><td></td></tr><tr><td><2,3,4></td><td>1</td><td></td><td></td><td></td><td></td></tr></table></body></html>

表5长度为4的候选模式集合  

<html><body><table><tr><td colspan="2">C4</td></tr><tr><td>CAND</td><td>SUPP</td></tr><tr><td><5,0,7,8></td><td>0</td></tr><tr><td><5,0,7,0></td><td>0</td></tr><tr><td><5,0,7,5></td><td>0</td></tr><tr><td><5,0,7,6></td><td>0</td></tr></table></body></html>

根据表2\~5的结果最终得到长度分别为1，2，3的用户移

动模式（UMP）集合及对应的支持度，如表6所示。

表6所有用户移动模式(UMP)集合  

<html><body><table><tr><td colspan="4">L</td></tr><tr><td>CAND</td><td>SUPP</td><td>CAND</td><td>SUPP</td></tr><tr><td><0></td><td>4</td><td><0,1></td><td>2</td></tr><tr><td><1></td><td>3</td><td><0,7></td><td>2</td></tr><tr><td><2></td><td>2</td><td><2.3></td><td>2</td></tr><tr><td><3></td><td>2</td><td><5,0></td><td>2.5</td></tr><tr><td><5></td><td>5</td><td><5,7></td><td>2</td></tr><tr><td><7></td><td>3</td><td><7,0></td><td>2.33</td></tr><tr><td></td><td></td><td><5,0,7></td><td>2</td></tr></table></body></html>

设定挖掘用户移动规则（UMR）的置信度阈值(confmin =50)。从表6中选择长度大于1的用户移动模式（UMP)，生成一系列的用户移动规则（UMR)。扫描表1中的用户移动路径（UPM）数据，按照定义4对生成的系列用户移动规则（UMR)，进行置信度的统计计算。

所有可能的用户移动规则（UMR）及置信度的结果如表7所示。按照设定的置信度阈值 $( c o n f _ { \mathrm { m i n } } = 5 0 )$ ，得到最终的用户移动规则（UMR）如表8所示。

表7所有可能的用户移动规则(UMR)

<html><body><table><tr><td>Rule</td><td>Conf</td></tr><tr><td><0>→<1></td><td>50</td></tr><tr><td><0>→<7></td><td>50</td></tr><tr><td><2>→<3></td><td>100</td></tr><tr><td><5>→<0></td><td>5</td></tr><tr><td><5>→<7></td><td>40</td></tr><tr><td><7>→<0></td><td>77.67</td></tr><tr><td><5.0>→<7></td><td>80</td></tr><tr><td><5>→<0.7></td><td>40</td></tr><tr><td>表8 满足置信度阈值的用户移动规则(UMR)</td><td></td></tr><tr><td>Rule</td><td>Conf</td></tr><tr><td><0>→<1></td><td>50</td></tr><tr><td><0>→<7></td><td>50</td></tr><tr><td><2>→<3></td><td>100</td></tr><tr><td><5>→<0></td><td>50</td></tr><tr><td><7>→<0></td><td>77.67</td></tr><tr><td><5.0>→<7></td><td>80</td></tr></table></body></html>

获取用于预测移动用户位置的、当前的用户移动路径$( U P M ) P = < 3 , 5 , 7 , 0 > \ ,$ 。设定预测移动用户下一步可能到达的基台覆盖范围网格（Mesh）的数量（ $\mathrm { m } { = } 1$ ）。利用算法MobilityPrediction(P,R,m)对移动用户的位置进行预测。根据表9得出预测结果为7的覆盖区域网格。

表9用于预测的用户移动规则（UMR）  

<html><body><table><tr><td>Rule</td><td>Conf+ SUPP</td></tr><tr><td><5,0>→→<7></td><td>82</td></tr></table></body></html>

<html><body><table><tr><td><0>→<1></td><td>52</td></tr><tr><td><0>→<7></td><td>52</td></tr></table></body></html>

# 3 实验结果与分析

# 3.1实验数据

本文初始数据为电信数据中的请求位置数据，其通过60s采集一次，时间范围为 $2 4 \mathrm { h }$ 。一个用户的请求位置数据代表了该用户移动过程中经过的基台覆盖范围网格，通过空间离散化将用户移动的网格序列变为空间临近的连续网格序列。本文使用了10个批次轨迹数据基本信息如表10所示。

表1010个批次轨迹数据基本信息  

<html><body><table><tr><td>不同批次</td><td>用户数量</td><td>轨迹点总数量</td><td>轨迹点总数量去重</td><td>移动轨迹平均轨迹点数</td></tr><tr><td>1</td><td>200</td><td>231779</td><td>17838</td><td>1158</td></tr><tr><td>2</td><td>201</td><td>240375</td><td>17455</td><td>1195</td></tr><tr><td>3</td><td>200</td><td>236833</td><td>19522</td><td>1184</td></tr><tr><td>4</td><td>198</td><td>231857</td><td>19236</td><td>1170</td></tr><tr><td>5</td><td>202</td><td>237104</td><td>19021</td><td>1175</td></tr><tr><td>6</td><td>201</td><td>231732</td><td>20130</td><td>1153</td></tr><tr><td>7</td><td>200</td><td>237718</td><td>20460</td><td>1188</td></tr><tr><td>8</td><td>199</td><td>239059</td><td>21653</td><td>1201</td></tr><tr><td>9</td><td>203</td><td>236350</td><td>22474</td><td>1164</td></tr><tr><td>10</td><td>200</td><td>233262</td><td>19447</td><td>1166</td></tr></table></body></html>

# 3.2 性能对比实验

通过前面对传统预测方法研究发现，本文提出方法与传统方法存在的本质区别点在于支持度计算方式不一样，为了避免与传统方法逐一对比，同时使对比更具有公平性，我们采用本文设计方法的基本框架，设计与传统的方法一样支持度计算方式的挖掘预测方法。传统计算支持度方式，即采用0或1的度量方法：

$$
s u p p I n c ( A , B ) = \left\{ { \begin{array} { l l } { 1 , U P M A \ { \overleftrightarrow { \bigoplus } } \cdots U M P B } \\ { 0 , { \qquad \overleftrightarrow { \bigoplus } } { \hat { \mathcal { H } } } { \hat { \mathcal { H } } } } \end{array} } \right.
$$

实验设定挖掘算法的支持度阈值，置信度阈值分别为 $10 \%$ ，$5 0 \%$ 。

在后面的实验及结果分析中，我们简称基于模式匹配度计算支持度的方法为相似化方法，而采用0或1计算支持度的对比方法为非相似化方法。相似化方法和非相似化方法挖掘用户移动规则的基本性能指标如图2\~图4所示，从这10个批次可以发现本文设计的相似化方法挖掘的用户移动规则数量少，支持度高，置信度高的特点。数量少是因为本文方法重新定义了用户移动路径对用户移动模式支持度使得挖掘出的用户移动模式集合变少导致挖掘用户移动规则变少。支持度高是因为相似化方法挖掘出的用户移动规则数量少。置信度均值高是因为对比方法（非相似化）采用简单的0或1的度量方法计算支持度，导致产生了大量的虚假的强规则。

![](images/f6d8b65fde6c49eb89ce392002c169ddee2b37cf0c5d871f90530bee67a2075a.jpg)  
图2挖掘用户移动规则数量的对比

![](images/7674b27805ab0deb2eaf9f170b7297e4515a6e52dc217bc8ae7dd9fb20213e5c.jpg)  
图3挖掘用户移动规则支持度均值对比

![](images/9525ecc38d8aa8d52b824446b81d64d9df58eb4ed09d9b66c7d5fb3d939144de.jpg)  
图4挖掘用户移动规则置信度均值对比

相似化与非相似化方法挖掘用户移动规则预测指标对比如图5\~7所示。可以看出，相似化方法挖掘出的用户移动规则具有较高的准确率均值、召回率均值和F均值。准确率均值高说明通过相似化方法挖掘出的用户移动规则在用于测试数据预测时具有更高的预测精度。召回率均值高说明通过相似化方法挖掘出的用户移动规则在用于测试数据预测时具有更多匹配到的规则数量。F值均值是准确率和召回率加权（权值 $\mathbf { a } { = } 1$ ）调和平均，这能够反映出挖掘用户移动规则的预测性能。F值高说明采用本文设计的相似化方法挖掘用户移动规则能够有比较高的可用性。

![](images/dde0b8b691a57c24beb4802cce69532e04284373302c19101cc0779e807505f6.jpg)  
图5挖掘用户移动规则准确率均值对比

![](images/8f92e7fbde63930019c9073b0ab412e869e88d161b28a8ab8a695bb3cdd2da81.jpg)  
图6挖掘用户移动规则召回率均值对比

![](images/d6c89f202aecef57e13f4a3786701d89b86941230b8edc9ebdb4e436e6b554bd.jpg)  
图7挖掘用户移动规则F值均值对比

# 4 结束语

移动用户的位置预测，可以有效地用于系统资源的时空分配，成为移动通信系统中资源管理的重要内容之一。预测准确度是位置预测性能的重要指标。但是，传统的位置预测方法并不能有效应对此类问题。本文提出一种基于模式匹配度的用户移动规则挖掘及位置预测方法研究。该方法通过定义度量用户移动路径（UPM）与用户移动模式（UMP）匹配度得分值，获取用户移动路径（UPM）与用户移动模式（UMP）的最佳匹配方法，从而设计了一种更加合理的度量用户移动路径(UPM)对用户移动模式（UMP）支持程度的计算方法。通过实验结果表明：本文提出的方法挖掘出的用户移动规则具有规则数少、支持度高和置信度高的特点，在用于预测数据时能够具有更高的预测精度。

# 参考文献：

[1]Dinh HT,Lee C,Niyato D,et al.A survey of mobile cloud computing: architecture,applications,and approaches [J].Wireless Communications & Mobile Computing,2013,13 (18): 1587-1611.   
[2]Park YI, Jang SM.Understanding privacy knowledge and skill in mobile communication [J].Computers in Human Behavior,2014,38 (9):296-303.   
[3]胡海洋；刘润华；胡华．移动云计算环境下任务调度的多目标优化方法 [J]．计算机研究与发展，2017，54(9):1909-1919.(Hu Haiyang，Liu Runhua,Hu Hua. Multi-objective optimization for task scheduling in mobile cloud computing [J].Journal of Computer Researchand Development,2017,54 (9):1909-1919.)

[4]郎为民．移动云计算：架构、算法与应用[M].北京：人民邮电出版社.

2016.(Lang Weimin.Mobile Cloud Computing:Architectures,Algorithms and Applications [M].Beijing:Posts& Telecom Press,2016.)   
[5] KamalR.Mobile computing[M]. Oxford: Oxford University Press,2008   
[6]Meroufel B.,Belalem G.Lightweight coordinated checkpointing in cloud computing[J].Journal of High Speed Networks,2014,20 (3): 131-143   
[7]Zhang Wen,Wen Yin,Wu Du.Collaborative task execution in mobile cloud computing under a stochastic wireless channel [J].IEEE Trans on Wireless Communications,2015,14(1):81-93.   
[8]黄国盛．移动IP的切换与移动性管理研究[D]．长沙：中南大学,2010. (Huang Guosheng. Study of handoff and mobility management in mobile IP [D]. ChangSha: Central South University,2010.)   
[9]ZickuhrK.Location-based services [J].Pew Research,2O13:1-25.   
[10]Al-Molegi A, Jabreel M,Ghaleb B.STF-RNN: space time features-based recurrent neural network for predicting people next location [C]// Computational Intelligence.2016: 1-7.   
[11]Wu Fan,Fu Kun,Wang Yang,et al.A Spatial-temporal-semantic neural network algorithm for location prediction on moving objects[J]. Algorithms,2017,10 (2): 37.   
[12] Zheng Y, ZhangL,Ma Z,et al.Recommending friends and locations based on individual location history[J].ACM Trans on the Web,2011,5(1): 5.   
[13] Meetei, K.P.,George,A. handoff management in wireless networks using predictivemodelling[C]//ProcofNationalConference on Communications.2011:1-5.   
[14] Feng Zhenni, Zhu Yanmin.A survey on trajectory data mining: techniques and applications [J].IEEE Access,2017,4:2056-2067.   
[15] Liu T,Bahl P,Chlamtac I.Mobility modeling,location tracking,and trajectory prediction in wireless ATM networks [C]. IEEE J.Select.Area Commun,1998,16: 922-936.   
[16]薛丹．用户移动模式的挖掘与位置预测的研究[D].上海：东华大学， 2005.(Xue Dan.Research on ming the user mobility patterns and location prediction [D]. Shanghai: Donghua University,2005.)   
[17]JeungH,Liu Q,Shen HT.A hybrid prediction model for moving objects [C]// Proc of the 24th IEEE International Conference on Data Engineering. 2008: 70-79.   
[18] Morzy M.Prediction of moving object location based on frequent trajectories [M].Berlin: Springer Berlin Heidelberg,2OO6:583-592.   
[19] Morzy M.Mining frequent trajectories of moving objects for location prediction [M].Berlin: Springer, 2007: 667-680.