# 基于多蚁群同步优化的多真值发现算法

冯钦」，曹建军²，郑奇斌」，张磊」，翁年凤²，李红梅‘(1．陆军工程大学 指挥控制工程学院，南京 210007;2.国防科技大学 第六十三研究所，南京 210007)

摘要：为提高在多真值场景下真值发现的准确性，提出一种多蚁群同步优化的多真值发现算法（multi-ant coloniessynchronization optimization based multi-truth discoveryalgorithm，MAC-SO-MTD）。以最大化各数据源提供的观测值集合与该对象真值集合之间相似度的加权和为目标，将多真值发现问题建模为求解子集问题，在此基础上设计蚁群算法进行求解：根据对象个数设置相应的蚁群，构造子集问题的有向图，利用路径概率转移公式进行同步搜索真值；将信息素更新分为本次迭代最优更新和本次迭代不更新，提高了算法的收敛速度。最后，通过算法复杂度分析和在真实数据集上的实验验证了该算法的优越性。

关键词：数据清洗；数据冲突；多真值发现；子集问题；蚁群优化中图分类号：TP311 doi: 10.19734/j.issn.1001-3695.2018.05.0453

# Multi-ant colonies synchronization optimization based multi-truth discovery algorithm

Feng Qin', Cao Jianjun², Zheng Qibin1, Zhang Lei1, Weng Nianfeng²,Li Hongmei1 (1.Command&ControlEngineeringCollge,ArmyEngineering University,Nanjingo07,China;2.he63rdResearch Institute,National University ofDefense Technology,Nanjing21oo07,China)

Abstract: Inorderto improve theaccuracyof truth discovery in multi-truth scene,this paper proposedamulti-ant colonies synchronization optimization based multi-truth discovery(MAC-SO-MTD)algorithm.It modeled the multi-truth discovery problemas the subset problem,which goal was maximizing the weighted sum ofsimilarity betwen the setof observations provided byeachdata sourceandthesetof truevaluesof teobject.Onthisbasis,thendesignedantcolonyalgorithmto solve the problem.Itsetantcolonies acording to thenumberofobjects.Basedon thesubset problem's structure graph,this paper usedroutes’probability transition equations tosearchfortruthssynchronicaly.Afteronecycle,thebestrouteof this cycle updating and no updating were two instances ofupdating pheromone,which improved theconvergence speed.Finaly,the analysis of algorithmcomplexityand contrast experimentontherealdata setvalidated the superiorityofthe algorithm.

Key words: data cleaning; data conflict; multi-truth discovery; subset problem; ant colony optimization

# 0 引言

随着大数据时代的到来，互联网的高速发展和产业的数字化导致各种数据量急剧增长，同时也带来各种数据质量问题。由于互联网的开放性和多源特性，不同互联网平台提供的数据参差不齐，所以网络上的数据不一定都是真实的，错误、过时、不完整等数据的存在会导致多个数据源对同一实体的描述存在着冲突[1。例如，不同天气网站针对某一地方提供不同的天气情况；不同购物网站为同一商品提供了不一致的产品信息等。根据“垃圾进，垃圾出（garbage in,garbage out）"的原理可知,低质量的冲突数据可能导致错误的分析决策和预测，对于相关信息产业的影响十分巨大[2]。因此，解决数据冲突问题格外关键且迫在眉睫。

Yin 等人[3]针对冲突处理问题首先定义了真值发现问题，即给定多个数据源提供的对于多个真实对象的大量冲突描述信息，研究如何从这些冲突信息中为每一个真实对象找出最准确的描述。有些对象在不同数据源中只对应一种描述，即只有一个真值，如一个人只有一个身份证号，这类单值属性对应的真值发现问题为单真值发现问题；有些对象在不同数据源中对应多种描述，即存在多个真值，如一本书可以有多个作者、一个人可以有多个头衔等，这类多值属性对应的真值发现问题为多真值发现问题。

多真值发现问题的求解与单真值发现问题不同。文献 $[ 3 - 9 ]$ 针对单真值问题，提出"对象真值唯一"的假设，并选取对象属性中得分最高或概率最大的值作为真值。而多真值发现问题不但要找到正确的值，还要尽可能地将所有的真值都找到。文献[10\~12]提出的方法可以解决多真值发现问题。但文献[10]需要设置阈值来选择真值集合，文献［11］不适用于各数据源均仅提供了部分实体真值的情况，文献［12］需考虑数据源中对象的领域信息。

马如霞等人[13]提出了MTruths 算法，能处理各数据源均仅提供了部分实体真值的情况，可以直接返回对象的真值集合，避免了阈值的选择问题，且其准确性优于已有多真值算法。但当对象真值集合基数较大时，MTruths算法中基于贪心策略的方法容易陷入局部最优，降低多真值发现的准确性。本文针对这一问题，通过将多真值发现过程转换为求解子集问题，并设计蚁群算法同步进行多真值发现，在对象真值集合基数较大时能较好地进行多真值发现。

本文的主要贡献如下:

a)将多真值发现过程转换为求解子集问题，通过最大化各数据源提供的观测值集合与对象真值集合之间相似度的加权和，在给定的对象值集中选出合适的真值集合，避免了通过设置阈值来选择真值;b）设计蚁群算法求解问题，根据对象数量设置相应的蚁群同步进行多真值发现，能在合理时间内找到较优解;c）通过真实数据集上的实验验证了本文提出的算法的优越性。

# 1 相关工作

针对单真值问题，研究者们进行了大量的研究。文献[3]首先提出了真值发现的概念，并根据链路分析的思想提出了TruthFinder算法。文献[4]基于概率投票的迭代计算方式提出了IVote 算法，并在此基础上考虑数据源的权威性，即数据源的投票比重提出了IRVote 算法。文献 $[ 5 \sim 7 ]$ 针对具有不同数据类型的多源数据，考虑了异构数据的真值发现问题。文献[8]考虑数据源复制和数据的复制关系，通过一个多层概率模型提高了Web数据的可用性。文献[9]针对数据源间可能存在的数据复制问题，将特定于每条事实的联合召回率和联合假真率融入真值概率计算。

上述这些方法都是基于真值唯一的假设，通过选择对象属性中得分最高或概率最大的值作为真值。对于多真值的情况，大部分算法模型并不适用。

针对多真值发现问题，文献[10]首先提出了可以处理多值属性真值发现的方法（latenttruthmodel,LTM），但该方法假设数据源的查全率和查准率服从Beta分布，如果真实数据集不满足假设的分布，则会对效果造成很大影响。文献[11]借鉴HITS（hypertext-induced topic search）算法思想，提出了多真值迭代发现算法，将数据源为实体提供的描述集看做实体在数据源上的视图，定义视图链接关系图，依据视图与描述相互迭代影响计算，但该算法并不适用各数据源均仅提供了部分实体真值的情况。文献［12］考虑数据源中不同领域对象的多真值发现问题，提出了一种集成贝叶斯的方法来考虑数据源内各领域对象描述的可信度，能够不需要任何监督来进行多真值发现，但该算法要求对象需具备其对应的领域信息。文献［13］提出了MTruths 算法，将多真值发现问题转换为一个最优化问题，并在真值计算过程中采用了基于枚举的方法和基于贪心策略的方法。该算法可以直接得到对象的真值集合，避免通过阈值的设置选择对象真值。但当对象真值集合基数较大时，MTruths算法的准确性较低，而本文提出的方法能较好地处理对象真值集合基数较大时的多真值发现问题。

# 2 问题描述

多真值发现问题假设对象的真值是一个集合。表1列举了提供《Distributed Systems:Concepts and Design》一书的五个网站及其提供的作者信息。

表1Distributed systems:concepts and design 作者信息

Table 1Author information of discreted systems:concepts and design   

<html><body><table><tr><td>网站</td><td>作者</td></tr><tr><td>happybook</td><td>Coulouris George F;Dollimore Jean; Kindberg</td></tr><tr><td></td><td>Tim</td></tr><tr><td>EnjoyStudy Sunmark Store</td><td>Coulouris;Dollimore Jean; Kindberg Tim</td></tr><tr><td>The Book Depository</td><td>Coulouris</td></tr><tr><td>Books2Anywhere.com</td><td>George Coulouris Coulouris George F;Dollimore Jean; K</td></tr></table></body></html>

由表1可知，每个网站提供的作者信息都不一样且难以判断真假，当想要收集这些信息时就存在一定困难。多真值发现就是要从这些多源冲突数据中发现真值集合。

给定对象集合 $O { = } \{ o 1 , o 2 , . . . , o _ { k } , . . . , o _ { n } \}$ ，其中 $n$ 是对象总数， $o _ { k }$ 表示第 $k$ 个对象。数据源集合 $S { = } \{ s 1 , s 2 , . . . , s h , . . . , s m \} $ 数据源提供对象描述信息， $s _ { h }$ 表示第 $h$ 个数据源，其中 $\mathbf { \nabla } _ { m }$ 是数据源总数。对象 $o _ { k }$ 可以有多个真值，数据源 $s _ { h }$ 可以为其提供观测值的集合。对象 $o _ { k }$ 的观测值集 $V _ { * , k } = \{ \nu _ { 1 } , \ \nu _ { 2 } , \ . . . , \ \nu _ { L k } \}$ ，表示所有数据源对对象 $o _ { k }$ 提供的观测值的集合，其中 $L _ { k }$ 是对象 $o _ { k }$ 观测值集的基数。对象 $o _ { k }$ 根据算法求解得到的真值集合可表示为$V _ { * , k } ^ { ' }$ ， $V _ { * , k } ^ { ' }$ 是观测值集 $V _ { \ast , k }$ 的子集。

本文研究的问题为：给定数据源集合 S={s1,S2,,Sh，$\vert s _ { m } \}$ ，对其描述的对象集合 $O { = } \{ o 1 , o 2 , . . . , o { k } , . . . , o { n } \}$ ，根据每个对象 $o _ { k }$ 的观测值集 $V _ { \ast , k }$ 找出其所有真值集合 $T _ { \boldsymbol { k } }$ □

# 3 多真值发现模型

本章首先介绍多真值发现算法的模型，然后对该模型进行分析。

# 3.1模型概述

根据两个假设：a)对象的真值情况应该尽可能与各数据源

提供的观测值接近；b)数据源的质量越高则其提供的对象属性集合与真值集合越相似[13]。因此可将多真值发现问题建模如式(1)\~(3)所示。

$$
\operatorname* { m a x } \Phi ^ { ' } = \sum _ { k = 1 } ^ { n } \sum _ { h = 1 } ^ { m } w _ { h } \times f ( \boldsymbol { V } _ { h , k } , \boldsymbol { V } _ { * , k } ^ { ' } )
$$

$$
s . t . \sum _ { h = 1 } ^ { m } w _ { h } = 1 \mathrm { H } . w _ { h } \in [ 0 , 1 ]
$$

$$
V _ { \ast , k } ^ { ' } \subseteq V _ { \ast , k }
$$

模型以各对象的真值集合和数据源提供的该对象观测值集合之间相似度的加权和达到最大为目标（式(1)）。式(1)中： $w _ { h }$ 为数据源 $s _ { h }$ 的数据质量权重； $V _ { h , k }$ 为数据源 $s _ { h }$ 为对象 $o _ { k }$ 提供的观测值集合； $V _ { * , k } ^ { ' }$ 为算法得到的对象 $o _ { k }$ 的真值集合，且是 $V _ { \ast , k }$ 的子集； $f ( V _ { h , k } , V _ { * , k } ^ { ' } )$ 定义为集合 $V _ { i , k }$ 与 $V _ { * , k } ^ { ' }$ 的Jaccard 相似度。

$$
f ( V _ { h , k } , V _ { * , k } ^ { ' } ) = \frac { \left| V _ { h , k } \bigcap V _ { * , k } ^ { ' } \right| } { \left| V _ { h , k } \bigcup V _ { * , k } ^ { ' } \right| }
$$

$w _ { h }$ 定义如下:

$$
w _ { h } = \frac { \displaystyle \sum _ { k = 1 } ^ { n } f ( V _ { h , k } , V _ { * , k } ^ { ' } ) } { \displaystyle \sum _ { h = 1 } ^ { m } \sum _ { k = 1 } ^ { n } f ( V _ { h , k } , V _ { * , k } ^ { ' } ) }
$$

式(5)中: $\sum _ { k = 1 } ^ { n } f ( V _ { h , k } , V _ { * , k } ^ { ' } )$ 为数据源 $s _ { h }$ 内所有对象的相似度之和； $\sum _ { h = 1 } ^ { m } \sum _ { k = 1 } ^ { n } f ( V _ { h , k } , V _ { * , k } ^ { ' } )$ 表示所有数据源内所有对象的相似度之和。

# 3.2模型分析

由于式(1)中每个项目中的真值相互独立，所以当每个对象的真值集合与对应的观测值集合相似性达到最大时，式(1)即可达到最大。因此，可得知该问题是要在对象 $o _ { k }$ 给定的观测值集中选出合适的真值集合以满足式(6)，且真值集合应尽可能大。

$$
\operatorname* { m a x } \Phi _ { k } ^ { ' } = \sum _ { h = 1 } ^ { m } w _ { h } \times f ( V _ { h , k } , V _ { * , k } ^ { ' } )
$$

式(6)为单个对象的多真值发现目标函数，表示最大化各数据源提供的观测值集合与该对象真值集合之间相似度的加权和，其中 $w _ { h }$ 为数据源 $s _ { h }$ 的数据质量权重。由式(5)可知，数据源质量权重由其内所有对象的相似度之和归一化所得，因此在求解真值集合过程中，可通过上次求解获得的数据源质量权重计算对象真值，然后通过本次求解获得的真值集合计算数据源质量权重。

综上可知，该多真值计算过程为典型的子集问题，即要在给定的对象值集中选出合适的真值集合以满足目标函数。因此可根据对象的数量将对象的多真值计算过程转换为同等数量的子集问题，即多子集问题。

# 4 MAC-SO-MTD 算法设计

由3.2节可知多真值计算过程是从对象观测值集中寻找到合适的真值集合，根据对象个数可转换成多子集问题。

求解子集问题是无序组合优化问题，但因子集问题的解为一个与元素次序无关的集合，与蚂蚁寻找最短觅食路径的自然行为不一致，给蚁群算法带来了挑战。文献［14］提出了基于图的蚂蚁系统，通过定义等效路径将问题本身的无序信息转换为等效路径上信息素量，并且采用基于等效路径增强的信息素更新策略对蚂蚁实施了有序影响，增加了问题求解的信息量，有效解决了蚂蚁构造解的有序性与解无序性之间的矛盾。

因此，本文在基于图的蚂蚁系统上设计蚁群算法进行求解多真值发现问题。

# 4.1多蚁群同步优化的多真值发现算法的流程描述

多真值发现问题中每个对象的多真值计算过程都可转换成子集问题，据此可以设置相应数量的蚁群同步进行多真值计算，因此MAC-SO-MTD算法流程如图1所示。

![](images/cbff9dc9e7d089fe404fb374042df9f3e665f5156bb8628b406448d742695cad.jpg)  
图1MAC-SO-MTD 算法流程  
Fig.1Flowchart of MAC-SO-MTDalgorithm

图1中，蚁群数量根据对象个数进行设置，每个蚁群都对应一个对象，所有蚁群同步进行搜索，每次迭代完成都输出对应对象真值集合。数据源质量权重根据式(5)进行计算。MAC-SO-MTD算法整个的计算过程是蚁群进行真值寻找和数据源质量权重计算的一个迭代过程。蚁群满足收敛条件即停止迭代，其对应对象的真值集合为历史最优解对应的真值结合。当所有蚁群停止迭代后，MAC-SO-MTD算法输出所有对象真值集合。

本文将蚁群收敛条件设置为其对应对象历史最优目标函数值未更新的次数。当未更新的次数等于 $H$ 时，蚁群不再进行搜索。MAC-SO-MTD算法伪代码算法1所示。

算法1 MAC-SO-MTD 算法输入：数据源集合 $s$ ，对象集合 $o$ 。

输出：所有对象真值集合 $\{ V _ { * , k } ^ { \cdot } | k { = } 1 , 2 , 3 , . . . , n \}$ 。

1. $V _ { * , k } ^ { ' } = V _ { * , k }$ ，根据式(5)计算 $\{ w _ { h } | h { = } 1 , 2 , 3 , . . . , m \}$   
2. 根据 $V _ { * , k } ^ { ' }$ 及 $w _ { h }$ ，通过式(1)计算目标函数值 $\boldsymbol { \Phi } ^ { \prime }$ ：  
3. $G = \boldsymbol \Phi ^ { ' }$ ， $O b j e c t _ { k } = V _ { * , k } ^ { ' }$ ， $S o u r c e _ { h } = w _ { h }$ ,Threshold 和 tem  
均为长度为 $n$ 的零向量;  
4. 生成 $n$ 群蚂蚁并放置于对应的 $\boldsymbol { U } _ { 1 } ^ { k }$ ，初始化蚁群算法  
数，蚁群收敛条件 $H$   
5. while(向量Threshold有不为 $H$ 的元素)  
6. for $k { = } 1$ to $n$   
7. 调用蚁群 $k$ 寻找对象 $o _ { k }$ 的真值集合  
$V _ { \ast , k } ^ { ' }$ ，最优函数值 $G _ { k }$ ；  
8. if Gk<temp[k] then  
9. Threshold[k]=Threshold[k]+1;  
10. else Threshold $\scriptstyle \cdot ] = 0$ ,temp $[ k ] = G _ { k }$ ;  
11. end if  
12. end for  
13. for $h { = } 1$ to $m$ （20  
14. 根据式(5)计算数据源 $s _ { h }$ 的质量权重 $w _ { h }$ ；  
15. end for  
16. 根据式(1)计算目标函数值 $\boldsymbol { \Phi } ^ { \prime }$ ：  
17. if $G < \boldsymbol \Phi ^ { \prime }$ then  
18. $G = \Phi ^ { ' } , O b j e c t _ { k } = V _ { * , k } ^ { ' } , S o u r c e _ { h } = w _ { h }$ ：  
19. 根据式(10)更新 $n$ 群蚂蚁的信息素；  
20. end if  
21. end while  
22. return $\{ V _ { * , k } ^ { \cdot } \mid k = 1 , 2 , 3 , . . . , n \}$

算法1中第1\~2行是在假设所有观测值集合均为真值的基础上进行数据源质量权重和目标函数值的计算；第5行判断向量Threshold里是否存在不为 $H$ 的元素，若存在则算法继续运行，否则返回所有对象的真值集合；第6\~12行为蚁群进行多真值寻找步骤，返回每次迭代蚁群找到的最优值 $G _ { \boldsymbol { k } }$ 及其对应的真值集合 $V _ { * , k } ^ { ' }$ ，同时记录历史最优值未更新次数；第13\~15 行进行数据源质量权重的计算；第16行根据当前得到的真值集合及数据源质量权重计算目标函数值 ${ \boldsymbol { \Phi } } ^ { \prime }$ ；第17\~20行将得到的目标函数值与目前保留的最大目标函数值进行比较，从而决定是否更新算法各参数和蚁群的信息素。当所有的蚁群满足收敛条件时，即向量Threshold里的元素均等于 $H$ 时，算法退出循环，并输出所有对象真值集合。

# 4.2蚁群算法设计

4.2.1蚁群算法组成

下面为对象 $o _ { k }$ 对应的第 $k$ 个蚁群算法的组成。首先构造子集问题的有向图，如图2所示。

![](images/77caaef6291fccd425a6ab982756747c4df1cd1afd49f500d415c8538450eb33.jpg)  
图2子集问题构造图的有向图  
Fig.2Directed graph of subset problem's structure graph

图2中 $L _ { k }$ 为子集问题解的个数，即对象的真值个数； $q$ 为蚂蚁所找解的最大可能基数； $e _ { i j } ^ { k }$ 表示第 $k$ 个蚁群第 $j$ 步选择第 $i$ 个元素。

在基于图的蚂蚁系统中使用的路径选择概率公式如式(7)所示。

$$
h _ { i j } ^ { k } \left( t \right) = \left\{ \begin{array} { c c } { \displaystyle \frac { \left( \tau _ { i j } ^ { k } \left( t - 1 \right) \right) ^ { \alpha } \left( \eta _ { i } ^ { k } \right) ^ { \beta } } { \displaystyle \sum _ { e _ { i j } ^ { k } \notin t a b u _ { g } ^ { k } } \left( \tau _ { i j } ^ { k } \left( t - 1 \right) \right) ^ { \alpha } \left( \eta _ { i } ^ { k } \right) ^ { \beta } } } & { e _ { i j } ^ { k } \notin t a b u _ { g } ^ { k } } \\ { 0 } & { \mathrm { ~ } \forall i \notin t \mathrm { i } } \end{array} \right.
$$

其中：禁忌表 $t a b u _ { g } ^ { k } ( g { = } 1 , 2 , . . . , N )$ 记录第 $k$ 个蚁群中第 $g$ 只蚂蚁走过的边； $\alpha$ 与 $\beta$ 表示信息素量和启发式因子的重要程度；$\tau _ { i j } ^ { k } ( t )$ 表示在 $t ( t { = } 0 , \ 1 , \ 2 , \ . . . )$ 时刻边 $e _ { i j } ^ { k }$ 上的信息素量；启发式因子 $\eta _ { i } ^ { k }$ 是外部信息，表示选择第 $k$ 个蚁群中第 $i$ 个元素的希望程度，其表达式如式(8)所示。

$$
\eta _ { i } ^ { k } = \frac { \displaystyle \sum _ { h = 1 } ^ { m } \mathbf { s u m } _ { i } ^ { k } [ h ] } { \displaystyle \sum _ { h = 1 } ^ { m } \big | V _ { h , k } \ \big | }
$$

其中： $\sum _ { h = 1 } ^ { m } \lvert V _ { h , k }$ 表示第 $k$ 个对象所有观测值出现的次数之和;$\sum _ { h = 1 } ^ { m } \mathbf { s u m } _ { i } ^ { k } [ h ]$ 表示第 $k$ 个对象的观测值集 $V _ { \ast , k }$ 中第 $i$ 个观测值出现的次数；向量 $\mathbf { s u m } _ { i } ^ { k } [ h ]$ 表达式如式(9)所示。

$$
\mathbf { s u m } _ { i } ^ { k } [ h ] = \left\{ \begin{array} { l l } { 1 , \quad \nu _ { i } \in V _ { h , k } } \\ { 0 , \quad \nu _ { i } \notin V _ { h , k } } \end{array} \right.
$$

其中： $\mathbf { s u m } _ { i } ^ { k } [ h ]$ 表示数据源 $s _ { h }$ 为对象 $o _ { k }$ 提供第 $i$ 观测值的情况，若数据源 $s _ { h }$ 为对象 $o _ { k }$ 提供了第 $i$ 观测值，则设置为1，否则设置为 $0$ 。

当所有蚁群一次迭代完成后，根据计算得到的目标函数值决定是否对等效路径上的信息素进行更新，信息素更新公式如式(10)所示。

$$
\tau _ { i j } ^ { k } ( t ) = \left\{ { p ( t ) + \frac { \Phi _ { k } ^ { ' } ( t a b u ^ { k } ( t ) ) } { Q _ { k } } } e _ { i j } ^ { k } \in \Gamma _ { k } ^ { } ( t a b u ^ { k } ( t ) ) \right.
$$

其中： $\frac { \Phi _ { k } ^ { ' } ( t a b u ^ { k } ( t ) ) } { Q _ { k } }$ 为信息素增量公式， $\Phi _ { k } ^ { ^ { \prime } } ( t a b u ^ { k } ( t ) )$ 为第 $k$ 个蚁群中要进行信息素更新的路径的目标函数值； $\Gamma _ { \boldsymbol { k } } ( t a b \boldsymbol { u } ^ { k } ( t ) )$ 表示第 $k$ 个蚁群中要进行信息素更新的等效路径[14]; $Q _ { k }$ 为常数，用来调整信息素增加的量； $p ( t )$ 表示挥发后的信息素矩阵，如式(11)所示。

$$
p ( t ) = ( 1 - \rho ) \times \tau _ { i j } ^ { k } ( t - 1 )
$$

其中： $\rho$ 为信息素挥发的系数， $0 < \rho < 1$ 。

为兼顾算法收敛速度和全局搜索能力，本文采用本次迭代最优更新和本次迭代不更新的信息素更新策略，即若本次迭代最优解好于当前全局最优解，则对本次迭代的最优路径 $t a b u ^ { k }$ 进行信息素矩阵更新；若本次迭代最优解等于或小于当前全局最优解，则本次迭代不更新，以强化同等信息素分布下的搜索

力度。

# 4.2.2蚁群算法的流程描述

为尽可能多地从对象观测值集中找出真值，可假设对象观测值集的元素均为真值，蚁群 $k$ 对其进行非真值的搜索。蚁群$k$ 一次迭代搜索多真值的具体流程如图3所示。

![](images/98bc90fbb561534161faefb02dea849edcadbf647cbcb1e547ca51d56a99c8a1.jpg)  
图3蚁群k一次迭代搜索多真值流程  
Fig.3Flow chart of one iterative search of multi-truth by ant colony $k$

图3中，每只蚂蚁每搜索一次就根据式(6)进行目标函数值计算，并与当前最优值进行比较，如小于当前最优值时则退出搜索。当所有蚂蚁都搜索完后，返回当前最优目标函数值对应的真值集合。当蚁群 $k$ 满足收敛条件后不再进行多真值寻找。蚁群算法进行多真值发现的伪代码如算法2所示。

算法2蚁群搜索多真值算法

输入：数据源集合S，对象集合 $o$ ，Threshold[k]，蚁群收敛 条件H，Objectko

输出：对象真值集合 $V _ { \ast , k } ^ { ' }$ ，本次迭代最优值 $G _ { \boldsymbol { k } }$ □

1. Objectk，根据式(6)计算目标函数值 $\left. \Phi _ { k } ^ { \dot { \mathbf { \alpha } } } \right.$ ， $G _ { k } = \Phi _ { k } ^ { ' }$ ;  
2. ifThreshold[k]不等于 $H$ then  
3. for $g { = } 1$ to $N$   
4. for $j { = } 1$ to q  
5. 第 $g$ 只蚂蚁根据式(7)在 $V _ { * , k }$ 中进行冲  
突值的选择；  
6. 根据式(6)计算目标函数值 $\left. \Phi _ { k } ^ { \prime } \right.$ ：  
7. if $\Phi _ { k } ^ { ' } > G _ { k }$ then  
8. $G _ { k } = \Phi _ { k } ^ { ' }$ ，并将该观测值加入禁忌表  
$t a b u _ { g } ^ { k }$   
9. else return  
10. end if  
11. end for  
12. end for

13. 根据 $G _ { k }$ 对应的禁忌表得到 $V _ { * , k } ^ { ' }$ ：

14. return $V _ { * , k } ^ { ' }$ ， $G _ { k }$

15. end if

算法2中第1行根据对象 $o _ { k }$ 的历史最优值对应的真值集合Objectk计算其目标函数值；第2行判断蚁群是否收敛，若不收敛则算法继续运行；第5\~6行表示第 $g$ 只蚂蚁在第 $j$ 步寻找一个冲突值，并计算目标函数值；第7\~10行将得到目标函数值与目前保留的最大目标函数值进行比较，以此判断第 $g$ 只蚂蚁是否继续寻找真值；第13行根据本次迭代最优值 $G _ { k }$ 对应的禁忌表计算真值集合 $V _ { * , k } ^ { ' }$ ；第14 行返回每次迭代的最优值 $G _ { \boldsymbol { k } }$ 及其对应的真值集合 $V _ { * , k } ^ { ' }$ 。

# 4.3算法复杂度分析

4.3.1时间复杂度

算法2各步骤的时间复杂度（最坏情况）如表2所示。

Table2Time complexity of each step of algorithm 2   

<html><body><table><tr><td>步骤</td><td>时间复杂度</td></tr><tr><td>蚂蚁禁忌表</td><td>O(N×Lk)</td></tr><tr><td>蚂蚁可搜索可行路径</td><td>O(N×Lk2)</td></tr><tr><td>解的评价更新</td><td>O(N)</td></tr></table></body></html>

算法2中蚁群只负责找出对象的真值集合， $N$ 为蚁群中蚂蚁数量，对问题规模没有影响，因此由表2可知算法2的时间复杂度为 $O ( L _ { k } 2 )$ 。

算法1各步骤的时间复杂度（最坏情况）如表3所示。

表2算法2各步骤时间复杂度  
表3算法1各步骤时间复杂度  

<html><body><table><tr><td>步骤</td><td>时间复杂度</td></tr><tr><td>初始化蚁群参数（τ(0)，n）</td><td>O(Lk²+Lk)</td></tr><tr><td>算法2</td><td>0(Hxn×Lk2)</td></tr><tr><td>数据源权重的计算</td><td>0(H×m)</td></tr><tr><td>信息素更新</td><td>0(Hxn×Lk2)</td></tr><tr><td>解的评价更新</td><td>0(H×N)</td></tr></table></body></html>

由表3可知，MAC-SO-MTD算法时间复杂度为 $O ( H \times n \times L _ { k } ^ { 2 } )$

# 4.3.2空间复杂度

算法2实际实现时，有向图的功能可以由信息素表兼任，并不占用存储空间。算法2各部分的空间复杂度如表4所示。

Table 3Time complexity of each step of algorithm 1   
表4算法2各部分空间复杂度  
Table 4Space complexity of each part of algorithm 2   

<html><body><table><tr><td>存储内容</td><td>空间复杂度</td></tr><tr><td>物品价值</td><td>O(Lk)</td></tr><tr><td>信息素表τ (0)</td><td>O(Lk²)</td></tr><tr><td>启发式因子n</td><td>O(Lk)</td></tr><tr><td>禁忌表</td><td>O(Lk)</td></tr><tr><td>数据源质量权重</td><td>0(m)</td></tr><tr><td>数据源集合</td><td>0(m)</td></tr><tr><td>对象集合</td><td>O(n)</td></tr><tr><td>对象观测值集合</td><td>O(mxLk)</td></tr><tr><td>对象真值集合</td><td>O(Lk)</td></tr></table></body></html>

算法2中蚁群只负责找出对象的真值集合，因此由表4可知算法2的空间复杂度为 $O ( L _ { k } 2 )$ 。

算法1各部分的空间复杂度如表5所示。

表5算法1各部分空间复杂度  
Table 5 Space complexity of each part of algorithm 1   

<html><body><table><tr><td>存储内容</td><td>空间复杂度</td></tr><tr><td>算法2</td><td>O(n×Lk2)</td></tr><tr><td>数据源质量权重</td><td>0(m)</td></tr><tr><td>信息素表τ (0)</td><td>O(nxLk)</td></tr><tr><td>向量Threshold</td><td>0(n)</td></tr><tr><td>向量temp</td><td>0(n)</td></tr><tr><td>数据源集合</td><td>0(m)</td></tr><tr><td>对象集合</td><td>0(n)</td></tr><tr><td>对象观测值集合</td><td>0(nxmxLk)</td></tr><tr><td>对象真值集合</td><td>O(nxLk)</td></tr></table></body></html>

由表5可知，MAC-SO-MTD算法空间复杂度为 $O ( n { \times } L _ { k } { ^ 2 } )$ 0

# 5 实验与分析

本章通过在真实数据集上进行对比实验，验证了多蚁群同步优化的多真值发现算法的有效性和准确性。

# 5.1实验数据及方法

本文所提算法解决的是多真值发现问题，因此实验采用的数据集应具有多值属性，如图书的作者属性、电影的导演属性等。本文采用两个真实数据集：a)Books-Authors数据集，包含多个网站提供的图书和作者的信息；b)Movies-Directors数据集，包含多个电影网站提供的电影和导演的信息。

a)Books-Authors数据集[3]。该数据集是真值发现算法常用的数据集，其中包括877个数据源、1263本书籍以及33971条记录，且其提供了100本书籍作者的真实信息。本文去掉原始数据集中的重复记录和无作者信息的记录，并对作者姓与名进行分割，经过处理后的数据集包含877个数据源、1263本书籍以及25604 条记录，其中作者可能值集大小为[1,54]，平均可能值集大小为7.7。该数据集的标准集为随机挑选出100 本图书并对其作者信息进行手工标注后的记录。

b)Movies-Directors 数据集[12]。一部电影的导演可以有多个，因此电影的导演属性是一个多真值属性。Movies-Directors数据集包含了15个国外电影网站的各种类电影468607部，共1134432条记录。本文根据电影上映年份，抽取2010一2017年间上映电影的记录，经去掉重复记录和无导演信息的记录，并对导演姓与名进行分割，最终得到的数据集包含15个数据源、36242部电影以及104591条记录。其中导演可能值集大小为[1,71]，平均可能值集大小为3.1。该数据集的标准集为随机挑选出188部电影并对其导演信息进行手工标注后的记录。

将本文所提方法分别与Voting算法和Mtruths_Greedy算法和遗传算法（genetic algorithm,GA）[i5]进行对比，设置如下：

方法1Voting-K。该算法采用投票机制计算真值，本文选择投票比重大于 $K$ 的作为真值。

方法2 Mtruths_Greedy。该算法是Mtruths算法提出的一种算法，在真值计算过程中采用贪心策略来判断真值集合。

方法3MGA-MTD。该方法框架与本文所提算法框架相同，其中多真值寻找过程采用经典遗传算法同步进行搜索，算法停止条件与MAC-SO-MTD 算法一致。其中Books-Authors 数据集中MGA-MTD算法参数设置：交叉率为0.5,变异率为0.01，染色体个数为30；Movies-Directors 数据集中MGA-MTD 算法参数设置：交叉率为0.6，变异率为0.01，染色体个数为50。

方法4本文第4章提出的MAC-SO-MTD算法。该算法采用多蚁群同步进行寻找真值集合，其中根据文献［14,16］和结合数据集特点，Books-Authors 数据集中MAC-SO-MTD 算法参数设置为：信息素初始化浓度 $\tau _ { i j } ( 0 ) = 1 0 0$ ，信息素重要程度 $\alpha$ （204号$\scriptstyle = 0 . 8$ ，启发式信息重要程度 $\beta = 0 . 6 5$ ，信息素挥发系数 $\rho { = } 0 . 1$ ，常数 $\scriptstyle { \mathrm { Q } = 2 0 }$ ，蚂蚁个数 $N { = } 1 5$ ；Movies-Directors数据集中MAC-SO-MTD算法参数设置为：信息素初始化浓度 $\tau _ { i j } ( 0 ) = 1 0 0$ ，信息素重要程度 $\alpha = 1$ ，启发式信息重要程度 $\beta = 0 . 6$ ，信息素挥发系数 $\rho { = } 0 . 1$ ，常数 $\scriptstyle { \mathrm { Q } = 4 0 0 }$ ，蚂蚁个数 $N { = } 2 0$ 。

本文实验采用MATLAB实现所有算法，软件开发环境为MATLAB $\mathrm { R } 2 0 1 7 \mathrm { a }$ 。实验的内存大小为 $1 6 \mathrm { G B }$ ，处理器为Intel(R)$\mathrm { C o r e ^ { ( T M ) } i 7 - 4 7 7 0 }$ ，采用Windows764位操作系统。

# 5.2评价指标

实验结果采用文献［13］中的衡量真值发现算法准确性的三个指标来衡量算法的优劣。

1）查准率（precision）表示算法得到对象的真值集合中正确真值所占的比例，计算公式如式(12)所示。

$$
P = \frac { \left| T _ { k } \bigcap { V _ { * , k } ^ { ' } } \right| } { \left| \begin{array} { l } { V _ { * , k } ^ { ' } } \end{array} \right| } \times 1 0 0 \%
$$

其中： $T _ { \boldsymbol { k } }$ 表示对象 $o _ { k }$ 所有的真值集合； $V _ { * , k } ^ { ' }$ 表示算法得到的对象 $o _ { k }$ 的真值集合； $T _ { k } \cap V _ { * , k } ^ { \cdot }$ 表示算法得到的真正为对象 $o _ { k }$ 真值的集合。

2）查全率（recall）表示算法得到的真值集合中正确真值占对应正确真值集的比例，计算公式如式(13)所示。

$$
R = \frac { \left| T _ { k } \bigcap V _ { * , k } ^ { ' } \right| } { \left| T _ { k } \right| } \times 1 0 0 \%
$$

3） $F 1$ 指标 表示查准率和查全率的调和平均数，计算公式如式(14)所示。

$$
F 1 = \frac { 2 \times P \times R } { P + R }
$$

# 5.3MAC-SO-MTD 算法参数敏感性分析

MAC-SO-MTD算法中采用目标函数值未更新次数 $H$ 作为蚁群收敛的条件，因此需要对 $H$ 值的敏感性进行分析。

在Books-Authors数据集与Movies-Directors数据集上对 $H$ 值取不同值，分别运行10次计算其对应 $P$ 、 $R$ 和 $F 1$ 的均值，实验结果如图4所示。

![](images/01f3103cb66e21ade332e832de2f248506ab017f8bdfa96736b0803b9a018142.jpg)  
Fig.4Influence of $H$ value on precision $P$ ,recall $R$ and $F 1$

由图4可看出，在Books-Authors数据集上，MAC-SO-MTD算法的查准率 $P$ 和 $F 1$ 指标随 $H$ 值的增大而增大，查全率 $R$ 随$H$ 值的增大而逐渐减小。当 $H$ 值大于等于11时，MAC-SO-MTD算法的 $F 1$ 指标趋于稳定，因此在Books-Authors数据集中蚁群的收敛条件可设置为对应目标函数值未更新11次。

而在Movies-Directors数据集上，MAC-SO-MTD算法的查准率 $P$ 、查全率 $R$ 和 $F 1$ 指标波动性较小。当 $H$ 值大于等于6时 $F 1$ 指标趋于稳定，因此在Movies-Directors数据集中蚁群的收敛条件可设置为对应目标函数值未更新6次。

# 5.4 对比结果分析

本文所提算法分别对比于Voting 算法和、Mtruths_Greedy算法和MGA-MTD 算法。其中Voting算法为真值发现的基准算法；Mtruths_Greedy 算法可以直接返回对象的真值集合，且在准确性方面优于现有多真值算法；MGA-MTD算法采用遗传算法进行多真值的寻找。

原始的Voting算法根据投票的多少给出观测值为真的可能性，不能直接返回真值集合，因此需要设置一个阈值 $K$ ，选择概率大于 $K$ 的观测值为真值。实验设置 $K$ 值分别为 $1 5 \% . 3 0 \%$ ，$45 \%$ 。

在两个数据集上分别用Voting- $\boldsymbol { \cdot } \boldsymbol { K }$ 、Mtruths_Greedy、MGA-MTD及MAC-SO-MTD算法进行实验，运行10次计算 $P , R$ 和$F 1$ 的均值和标准差，实验结果如表6、7所示。

表6不同方法在Books-Authors数据集上的真值发现实验结果

Table 6Results of different truth discovery methods on the Book  

<html><body><table><tr><td colspan="4">Authors data set</td></tr><tr><td>方法</td><td>P</td><td>R</td><td>F1</td></tr><tr><td>Voting-15%</td><td>98.57±0</td><td>62.64±0</td><td>76.60±0</td></tr><tr><td>Voting-30%</td><td>100±0</td><td>19.82±0</td><td>33.08±0</td></tr><tr><td>Voting-45%</td><td>100±0</td><td>5.47±0</td><td>10.37±0</td></tr><tr><td>Mtruths_Greedy</td><td>89.85±0</td><td>80.64±0</td><td>85.00±0</td></tr><tr><td>MGA-MTD</td><td>89.7±0.93</td><td>90.82±0.83</td><td>90.25±0.66</td></tr><tr><td>MAC-SO-MTD</td><td>89.58±1.66</td><td>91.41±0.80</td><td>90.47±0.68</td></tr></table></body></html>

表7不同方法在Movies-Directors 数据集上的真值发现实验结果

Table 7Results of different truth discovery methods on Movies-Directors data set   

<html><body><table><tr><td>方法</td><td>P</td><td>R</td><td>F1</td></tr><tr><td>Voting-15%</td><td>98.29±0</td><td>88.31±0</td><td>93.04±0</td></tr><tr><td>Voting-30%</td><td>99.07±0</td><td>60.92±0</td><td>75.45±0</td></tr><tr><td>Voting-45%</td><td>98.66±0</td><td>42.34±0</td><td>59.25±0</td></tr><tr><td>Mtruths_Greedy</td><td>95.78±0</td><td>91.19±0</td><td>93.43±0</td></tr><tr><td>MGA-MTD</td><td>90.54±0.3</td><td>97.17±0.16</td><td>93.74±0.15</td></tr><tr><td>MAC-SO-MTD</td><td>92.52±0.12</td><td>96.47±0.08</td><td>94.45±0.08</td></tr></table></body></html>

由表6与7可知,MAC-SO-MTD 算法的查全率 $R$ 与 $F 1$ 指标均优于Mtruths_Greedy算法，且 $F 1$ 指标优于Voting- $\mathbf { \nabla } \cdot K$ 算法与 MGA-MTD 算法；而Voting- $\cdot K$ 算法的查准率 $P$ 虽然稍高于其他对比算法，但由于其查全率 $R$ 较低，所以Voting- $\mathbf { \nabla } \cdot K$ 算法的$F 1$ 指标明显低于其他对比算法。在Books-Authors 数据集中，MGA-MTD 算法的查准率 $P$ 虽然稍高于 MAC-SO-MTD 算法，但其查全率 $R$ 与 $F 1$ 指标均低于MAC-SO-MTD 算法。而在Movies-Directors 数据集中，MAC-SO-MTD算法的 $F 1$ 指标显著高于其他三种算法。

通过在两个真实数据集上的实验可知，MAC-SO-MTD 算法的准确性比MGA-MTD 算法更高。而Voting- $\mathbf { \nabla } \cdot K$ 算法中由于占比越高的观测值越可能为真值，随着阈值 $K$ 的增大，查准率

$P$ 越大，但其查全率 $R$ 显著降低，因此无法返回对象完整的真值集合。Mtruths_Greedy算法是基于贪心策略进行多真值发现，将对象观测值集里的观测值按可能为真值的概率进行排列并挑选，当对象的真值较多且分布较均匀时易陷入局部最优，故其查全率 $R$ 和 $F 1$ 指标均低于MAC-SO-MTD算法。

# 6 结束语

数据在各行各业中发挥着越来越重要的作用，如何从冲突数据中挖掘出准确的数据具有重要的意义和研究价值。真值发现作为数据集成中冲突消解的有效手段，得到了广泛研究。然而，当前的研究工作更多地关注单真值发现问题。针对多真值发现问题，本文提出了一种基于多蚁群同步优化的多真值发现算法MAC-SO-MTD，将对象的多真值发现过程转换成子集问题，并设计多蚁群算法同步进行真值搜索，避免了阈值选择的问题，提高了多真值发现的准确性，在对象真值集合基数较大时能较好地进行多真值发现。同时，考虑了数据源权重对真值发现效果的影响，在计算过程中迭代地进行蚁群真值寻找和数据源质量权重计算。

# 参考文献：

[1]Bleiholder J,Naumann F.Data fusion [J].ACM Computing Surveys,2008, 41 (1): 1-41.   
[2]曹建军，刁兴春，汪挺，等．领域无关数据清洗研究综述[J].计算机 科学,2010,37(5): 26-29.(Cao Jianjun,Diao Xingchun,Wang Ting,et al. Research on domain-independent data cleaning: a survey [J]. Computer Science,2010,37(5):26-29.)   
[3]Yin Xiaoxin,Han Jiawei,Yu Philip S.Truth discovery with multiple conflicting information providers on the web[J].IEEE Trans on Knowledge and Data Engineering,2008,20 (6):796-808.   
[4] 考明军，张炜，高宏．冲突数据中的真值发现算法[J].计算机研究与 发展,2010,47 (z1):188-192.(Kao Mingjun,Zhang Wei,Gao Hong.Truth discovery methods in conflict data integration [J]. Journal of Computer Research and Development, 2010,47 (z1): 188-192.)   
[5]LiQi,Li Yaliang,Gao Jing,et al.Resolving conflicts in heterogeneous data by truth discovery and source reliability estimation [Cl//Proc of the 32nd ACM SIGMOD International Conference on Management of Data.New York:ACMPress,2014:1187-1198.   
[6]Li Qi,Li Yaliang,Gao Jing,et al.A confidence-aware approach for truth discovery on long-tail data[J].Proceedings ofthe VLDB Endowment,2014, 8 (4): 425-436.   
[7]Li Yaliang,LiQi,Gao Jing,et al.Conflicts to harmony: a framework for resolving conflicts in heterogeneous databy truth discovery[J].IEEE Trans on KnowledgeandData Engineering,2016,28(8):1986-1999.   
[8]Dong Xinluna,Gabrilovich E,Murphy K,et al. Knowledge-based trust: estimating the trustworthiness of web sources [J].Proceedings of the VLDB Endowment,2015,8 (9): 938-949.   
[9] 余东，申德荣，寇月，等．面向Web 数据集成的真值发现算法[J].小 型微型计算机系统,2016,37(8):1633-1638.(Yu Dong,Shen Derong,Kou Yue,et al.Web data integration oriented truth discovery algorithms [J]. Journal of Chinese Computer Systems,2016,37(8):1633-1638.)   
[10] Zhao Bo,Rubinstein BIP,Gemmell J,et al.A Bayesian approach to discovering truth from conflicting sources for data integration[J]. Proceedings of the VLDB Endowment, 2012,5 (6): 550-561.   
[11]王继奎，李少波．基于HITS的冲突Deep Web数据多真值发现算法[J]. 计算机工程,2016,42(9):158-162.(Wang Jikui,Li Shaobo.Multiple truth value discovery algorithm for conflicting Deep Web data based on HITS [J] Computer Engineering,2016,42 (9):158-162.)   
[12] Lin Xueling，Chen Lei. Domain-aware mutil-truth discovery from conflicting sources [J].Proceedings of the VLDB Endowment,2018,11 (5): 635-647.   
[13]马如霞，孟小峰，王璐，等.MTruths:Web信息多真值发现方法[J].计 算机研究与发展,2016,52 (12):2858-286.(Ma Ruxia,Meng Xiaofeng, Wang Lu, et al.MTruths: an approach of multiple truths finding from web information[J]. Journal of Computer Research and Development,2016, 52 (12): 2858-2866. )   
[14]曹建军，张培林，王艳霞，等．一种求解子集问题的基于图的蚂蚁系统 [J]．系统仿真学报,2008,20 (22): 6146-6150.(Cao Jianjun,Zhang Peilin, Wang Yanxia,et al. Graph-based ant system for subset problems [J]. Journal of System Simulation,2008,20 (2): 6146-6150.)   
[15]王小平，曹立明.遗传算法理论应用与软件实现[M].西安：西安交通 大学出版社,2002:18-50.(Wang Xiaoping,Cao Liming.Geneticalgorithm: theory,application and software implementation[M].Xi'an: Xi'an Jiaotong University Press,2002: 18-50. )   
[16] DorigoM,Stu tzle T.蚁群优化[M].张军，胡晓敏，罗旭耀，等译．北 京：清华大学出版社,2007:202-209.(Dorigo M,St u tzle T.Ant colony optimization [M]. Zhang Jun,Hu Xiaomin,Luo Xuyao,etal Translated. Beijing: Tsinghua University Press,2007: 202-209.)