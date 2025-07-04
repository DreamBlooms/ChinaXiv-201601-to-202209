# 一种面向多类不平衡协议流量的改进AdaBoost.M2算法

张仁斌，张 杰，吴佩(合肥工业大学 计算机与信息学院，合肥 230009)

摘要：针对 AdaBoost。M2算法在解决多类不平衡协议流量的分类问题时存在不足，提出一种适用于因特网协议流量多类不平衡分类的集成学习算法RBWS-ADAM2，本算法在 AdaB0ost。M2 每次迭代过程中，设计了基于权重的随机平衡重采样策略对训练数据进行预处理，该策略利用随机设置采样平衡点的重采样方式来更改多数类和少数类的样本数目占比，以构建多个具有差异性的训练集，并将样本权重作为样本筛选的依据，尽可能保留高权重样本，以加强对此类样本的学习。在国际公开的协议流量数据集上将RBWS-ADAM2算法与其他类似算法进行实验比较表明，相比于其他算法，该算法不仅对部分少数类的F-measure 有较大提升，更有效提高了集成分类器的总体G-mean 和总体平均F-measure，明显增强了集成分类器的整体性能。

关键词：流量分类；集成学习算法；多类不平衡；泛化性能 中图分类号：TP393.04 doi:10.3969/j.issn.1001-3695.2018.01.0010

# Improved AdaBoost.M2 algorithm for multiclass imbalanced protocol traffic

Zhang Renbin, Zhang Jie†, Wu Pei (School ofComputer&Information,Hefei UniversityofTechnology,Hefei 23ooo9,China)

Abstract: The existing AdaBoost.M2 algorithmare insuficient in protocol taffc multiclass imbalanceto solve the problem. So,this thesis proposes an ensemble algorithom called RBWS-ADAM2 for the clasification of multiclass interet traffic. During ach iterationof AdaBoost.M2,this algorithm preprocesed thetraining dataset byrandomlybalancedresampling,this strategychangedthe numberof majoritiesand minorities byrandomly setting the sampling balance point to build multiple differentrainingdatasets.Moreover,thisstrategytokesample weightasthebasis forsamplescreningtostrengthentheearing of this kind of sample.The experimental comparison of RBWS-ADAM2 algorithmand other similar algorithms on the internationallypublished protocol trafic datasets shows that，compared to other algorithms,the proposed RBWS-ADAM2 algorithm notonlyimproves theF-Measureof most minorities,but increases theoverallG-mean and theoverallaverage Fmeasure effectively,and obviously enhances the overall performance of the ensemble classifier.

Key words: traffic classification; ensemble algorithm; multiclass imbalance; generalization performance

# 0 引言

当前因特网协议流量中存在严重的多类不平衡问题[1]，某些类别的流样本数远多于其他类别。这种情况下，分类器虽然可以取得较高的总体分类精度，但往往偏向于对总体分类精度贡献较大的多数类样本，对少数类样本的分类精度则较低。目前处理数据类别不平衡的方法主要分为两类。一类是在分类器训练之前对训练集进行重采样的方法，其基本思想是通过改变训练集的类别分布来消除或降低数据集不平衡程度，典型的有SMOTE[2]算法/SBC算法[3]，SCUT 算法[4]等。以上的重采样算法大都是针对两类不平衡问题进行研究，而文献[5,6]表明针对两类不平衡问题的重采样算法无法有效解决多类不平衡问题甚至可能会带来负面影响，并且部分针对两类不平衡问题的重采样算法无法直接用于解决多类不平衡问题，如前述SBC算法，此外对于类似SMOTE 算法的过采样或欠采样算法，采样比例是影响分类器最终性能的关键因素，但是对于不同数据集，最合适的采样比例可能不同也不容易确定。

另一类是对学习算法改进使之适用于不平衡数据分类，其中最常见的方法是基于Bagging的方法和基于Boosting的方法，例如将 SMOTE 重采样与Bagging 集成学习相结合的SMOTEBagging算法[7]。还有将重采样方法与AdaBoost.M2相结合进行改进的集成学习算法也被相继提出，AdaBoost.M2[8]作为多类集成学习算法，虽然具有相对较优的整体性能，但是其毕竟没有考虑到样本多类不平衡的影响，因此文献[9]提出了

SMOTEBoost算法，该算法在基分类器学习之前运用SMOTE算法为少数类构建新样本，以提高训练集中少数类的比重，但是该算法的最优过采样比例很难确定，若设置过小则无法达到预期效果，若设置过大则可能导致分类器过拟合，并且过度利用SMOTE过采样进行样本扩充，可能带来严重的样本重叠和噪声问题[10]。文献[11]提出了RUSBoost 算法，该算法在基分类器学习之前运用随机欠采样删除部分多数类样本，该策略可以降低数据的不平衡程度，却可能由于其随机性而误删有用的多数类样本，影响到分类器对多数类的分类效果。还有部分算法不依赖任何重采样算法来平衡数据集，例如文献[12]提出了基于数据分区的集成学习算法，该算法将多数类样本分为若干份，每次训练基分类器时取其中一份与少数类合并作为新训练集，虽然其避免了使用重采样算法，但是每次基分类器只能学习到多数类中的部分样本，可能会降低集成分类器对多数类的分类精度，并且其分区策略只适用于二类不平衡的情况，因此无法很好解决多类不平衡问题。

综上所述，为增强AdaBoost.M2算法在面对多类不平衡协议流量时的整体分类性能，缓解多类不平衡对少数类分类的影响，本文提出一种基于随机平衡重采样的改进AdaBoost.M2集成学习算法-RBWS（random balance sampling based on weighting-ADAM2（AdaBoost.M2)，本算法通过在AdaBoost.M2每次迭代前对训练集进行基于样本权重的随机平衡重采样来提升分类器对于少数类的分类能力，以缓解多类不平衡问题对分类器的影响。在数据预处理过程中，本算法首先随机确定各多数类和各少数类的样本占比，再根据样本占比对训练集进行重采样形成新训练集以增大训练集之间的差异性，有利于提升分类器的泛化性能。此外，在对训练集重采样时，本算法将过采样与欠采样策略相结合，避免了单一使用过采样或欠采样可能导致的不足，同时本算法将样本权重作为唯一的样本筛选标准，优先扩充或保留各类别中高权重样本，进而保证分类器对此类样本的充分学习。

# 1 RBWS-ADAM2算法

# 1.1基于样本权重的随机平衡重采样策略

为提升AdaBoost.M2算法在多类不平衡协议流量数据集上的整体表现，本节设计了针对AdaBoost.M2改进的重采样策略RBWS，该策略包括对所有少数类执行过采样和对所有多数类执行欠采样两个过程，首先通过计算所有类别样本数目的平均值来确定随机区间，并在随机区间内随机确定采样平衡点，再根据采样平衡点来确定多数类和少数类。在对少数类的过采样过程中，为加大对少数类中分类错误样本的关注，对于每个少数类，按照其所有样本的权重大小排序，取前一半样本进行SMOTE过采样以生成新样本。在对多数类的欠采样过程中，考虑到网络协议流量存在严重的类内子概念[13]问题，部分样本占比小的子概念可能会被过度采样，所以为保证欠采样后多数类样本的总体质量，本策略采取对各多数类进行基于权重的聚簇式欠采样方法，首先对单个多数类所有样本进行聚簇以得到所有子簇，并按照子簇样本数目占比分配该子簇的欠采样数目，在各子簇中按照样本权重排序进行欠采样，优先删除权重小的样本，以保证分类器对高权重样本的学习。RBWS重采样策略的伪代码描述如下。

Input:dataset $\mathrm  S = \{ ( x _ { 1 } , y _ { 1 } ) , \} ~ , ~ ( x _ { m } , y _ { m } ) \} ~ , ~ y _ { i } \{ 1 , \uparrow ~ , k \} ~ , \mathrm { i \{ 1 , \uparrow ~ , m \} ~ } .$ //k  
为类别数， $\mathrm { ~ m ~ }$ 为样本总数  
Output: new training dataset $\boldsymbol { \mathrm { \Sigma } } ^ { s ^ { \prime } }$ ：  
$\mathbf { 0 1 : M = m / k }$ //计算所有类别样本数目的平均值M  
$\mathbf { 0 2 } { \cdot } \mathrm { d } { = } \mathrm { R a n d o m } ( \mathbf { \eta } _ { \mathrm { n _ { 1 } } } \mathrm { M } , \mathbf { \eta } _ { \mathrm { n _ { 2 } } } \mathrm { M } )$ //从随机区间为[ ${ \boldsymbol { \mathrm { n } } } _ { 1 } ^ { \mathrm { \Theta } } { \mathrm { M } } , { \boldsymbol { \mathrm { n } } } _ { 2 } ^ { \mathrm { \Theta } } { \mathrm { M } } ]$ 选取随机值  
d作为采样平衡点，其中 $0 < { \mathfrak { n } } _ { 1 } \leq 1$ ， $1 { < } \mathsf { n } _ { 2 } < [ \mathsf { M a x } / \mathsf { M } ]$ ，Max 为所有类别  
的最大样本数目  
03:for each $i \{ 1 , 2 \} \ , \mathbf { k } \}$ do:  
04: $\mathbf { i f } \mathrm { n } [ i ] > \mathrm { d }$ ： //类别 $i$ 样本数目 ${ \mathbf n } [ i ]$ 大于d  
05: add $i$ toC//将类别 $i$ 加入多数类集合C  
06: else: add $i$ toU//将类别 $i$ 加入少数类集合U  
07:end for  
08:for each $\mathrm { { C } _ { i } \mathrm { { C } } }$ do:  
09:num[ C,]=number[ $\mathrm { { C } _ { \mathrm { { i } } } }$ ]-d//获取多数类 $\mathbf { C } _ { \mathrm { i } }$ 的欠采样数目  
10: （20 $\mathrm { S U M \_ C = S U M \_ C + n u m [ \vec { C } _ { i } ] }$ //SUM_C为所有多数类欠采样  
的总数目  
11:clusters=Cluster( $\mathrm { \dot { \langle } C _ { i } }$ ）//对类别 $\mathbf { C _ { \mathrm { i } } }$ 的所有样本聚簇，得到簇集  
clusters  
12:for each clusterj clusters do:  
13: num[ cluster,]=number[ cluster]  
/number[ $\mathrm { C _ { i } \ l { \times } n u m [ C _ { i } ] }$ （204号  
//按样本数目占比确定各子簇的欠采样数目，样本数目越多的子簇需  
要欠采样的数目越多  
14: undersamplingcluster；byweight//在每个子簇中优先欠采  
样样本权重小的样本  
15:end for  
16:end for  
17:get C'after undersampling//C'为多数类欠采样后的样本集  
18:for each UiU do:  
19:num[ $\mathrm { U _ { i } \ l { = } S U M _ { - } C / q }$ //对所有少数类，过采样数目为 SUM_C  
除以所有少数类个数取整，q为少数类类别数  
20:get $\mathbf { U } _ { \mathrm { i } } ^ { \dagger }$ by weight／/对单个少数类所有样本按照权重大小进  
行降序排序，取排序后前一半样本 $\mathbf { U } _ { \mathrm { i } } ^ { \prime }$ （20  
21:SMOTE( $\mathbf { U } _ { \mathrm { i } } ^ { ' }$ ）//按照 num[U]对 $\mathbf { U } _ { \mathrm { i } } ^ { \prime }$ 执行 SMOTE 过采样  
22:end for  
23:get U'?after oversampling $/ / \mathrm { U } ^ { \prime }$ 为少数类过采样后的样本集  
24:return $\mathbf { S } ^ { \prime = } \mathbf { C } ^ { \prime + } \mathbf { U } ^ { \prime }$ //将 $\mathbf { C ^ { \prime } }$ 与 $\mathrm { ~ U ~ } ^ { \prime }$ 合并得到新训练集 $\boldsymbol { s } ^ { \prime }$

# 1.2RBWS-ADAM2集成学习算法

研究[14]表明增加训练数据的差异性对于提升集成学习算法的整体性能和解决集成学习算法面临的数据集不平衡问题起十分关键的作用。本节RBWS-ADAM2算法基本思想就是在

AdaBoost.M2每次迭代过程中运用前述RBWS重采样策略进行数据预处理，从而在缓解数据不平衡的同时增大训练集的差异性。AdaBoost.M2 算法有两种权重处理方式，分别是 Boostingby reweighting [15]和 Boosting by resampling[15]。Boosting byreweighting方式要求基分类器可以直接训练带权重的训练集，其优点是所有样本都会参与分类器训练，但是该方式并未考虑多类不平衡的影响，并且由于训练集所有样本都参与训练，每次迭代之间的训练集缺乏差异性，无法有效提升集成分类器的泛化性能。Boostingbyresampling方式的基本思想是每次迭代通过对训练集进行基于样本权重的有放回随机抽样来构造新训练集，该方式虽然对基分类器没有特殊要求，但是可能存在同一样本被重复选入的情况，若某类别中含有过多的困难样本，则采样后的新训练集中可能某一类别的样本数目过多，从而导致分类器过拟合。本算法是基于reweighting的方式对样本权重进行利用，首先对训练集进行RBWS重采样，在重采样后更新新训练集的样本权重D'时，设置新训练集S中属于原训练集 S的样本的权重不变，将新样本的权重设为统一值 $1 / \mathrm { m }$ ， $\mathrm { ~ m ~ }$ 为初始训练集s的样本总数。接下来利用 $\mathbf { S } _ { \mathrm { t } }$ 和 $\mathbf { D } _ { \mathrm { t } } ^ { \mathrm { ' } }$ 进行基分类器 $\mathbf { h } ,$ 的训练，最后计算基分类器 $\mathbf { h } _ { \mathfrak { t } }$ 的伪误差 $\mathbf { \varepsilon } _ { \mathbf { \varepsilon } _ { \mathrm { t } } }$ ，并对权重分布进行更新。经过T次迭代训练，得到最终的集成分类器 $\mathrm { ~ \textmu ~ } _ { \mathrm { { H } } }$ 。RBWS-ADAM2算法的伪代码描述如下。

Input:dataset $\mathrm { S = \{ ( x _ { 1 } , y _ { 1 } ) , \uparrow \ , ( x _ { m } , y _ { m } ) \} ~ , ~ y _ { i : } \{ 1 , \uparrow \ , k \} ~ , ~ i \{ 1 , \uparrow \ , m \} ~ . }$ $/ / \mathbf { k }$ 为类别数， $\mathrm { ~ m ~ }$ 为样本总数

Output: integrated classifier H.

01:for each $\mathrm { i } \{ 1 , ? \mathrm { ~ } , \mathrm { m } \}$ do:

02: $\mathrm { \bf D } _ { 1 } \left( \mathrm { i } \right) { = } 1 / \mathrm { m }$ //初始化样本分布权重

03: $\mathbf { W } _ { \mathrm { i , y } } ^ { 1 } { = } \mathbf { D } _ { 1 } \big ( \mathrm { i } \big ) / ( \mathbf { k } { - } 1 )$ //初始化权重向量，权重向量W 的上标1代表是第1次迭代， $\mathbf { i }$ 是样本的序号，y是样本的类别标签，不包括$\mathbf { y } _ { \mathrm { i } }$ ，即 $\mathbf { y } \neq \mathbf { y } _ { \mathrm { i } }$

# 04:end for

05:for each $\mathfrak { t } \{ 1 , ? \ , \mathrm { T } \}$ do:

06: for each $\mathrm { i } \{ 1 , ? \ , \mathrm { m } \}$ do:

)7: $\mathrm { W { = } W { + } ~ W _ { i } ^ { t } / / \vec { \ z } \vec { \ k } \vec { \mp } \vec { \mathbb { H } } ~ \sum _ { i = 1 } ^ { m } W _ { i } ^ { t } }$

08: end for

09: for each $\mathrm { i } \{ 1 , ? \mathrm { ~ } , \mathrm { m } \}$ do:

10: q.(i,y)=Wi,y/W//计算样本标签权重，其中$\mathbf { W } _ { \mathrm { i } } ^ { \mathrm { t } } { = } \sum _ { \mathrm { y } \neq \mathrm { y } _ { \mathrm { i } } } \mathbf { W } _ { \mathrm { i , y } } ^ { \mathrm { t } } \ , \ \ \ \ \mathbf { y } \neq \mathbf { y } _ { \mathrm { i } }$ 11: $\mathrm { { D } _ { \mathrm { { t } } } ( \mathrm { { i } ) = \mathrm { { W } _ { \mathrm { { i } } } ^ { \mathrm { { t } } } / W } } }$ //计算样本分布权重

12: end for

13: $\mathbf { S } _ { \mathrm { t } } { = } \mathbf { R } \mathbf { B } \mathbf { W } \mathbf { S } ( \mathbf { S } )$ //运用RBWS 重采样策略对训练集S进行预处理得到新训练集 $\mathbf { S } _ { \mathrm { t } }$

14: for each jS.?&&j $s$ do:

15: D,(j)=1/m//设置采样过程中产生的新样本权重为$1 / \mathrm { m }$ ，原有样本的权重保持不变

16: end for

17:get $\mathbf { D } _ { \mathrm { t } } ^ { \mathrm { ' } }$ //得到新训练集的样本权重分布 $\mathbf { D } _ { \mathrm { t } } ^ { ' }$

18: $ { \mathbf { h } } _ { \mathrm { t } } = \mathrm { T r a i n } (  { \mathbf { D } } _ { \mathrm { t } } ^ { \prime } ,  { \mathbf { S } } _ { \mathrm { t } } )$ ）//利用 $\mathbf { D } _ { \mathrm { t } } ^ { \mathrm { i } }$ 和 $\mathbf { S } _ { \mathrm { t } }$ 进行基分类器训练，得到基分类器 $\mathbf { h } _ { \mathrm { t } }$

19: for each $\mathrm { i } \{ 1 , ? \mathrm { ~ } , \mathrm { m } \}$ do:

20: $\varepsilon _ { \mathrm { t } } = \varepsilon _ { \mathrm { t } } + \mathrm { D } _ { \mathrm { t } } ( \mathrm { i } ) ( 1 - \mathrm { h } _ { \mathrm { t } } ( \mathrm x _ { \mathrm { i } } , \mathrm y _ { \mathrm { i } } ) + \sum _ { \mathrm { y } \neq \mathrm { y } _ { \mathrm { i } } } \mathrm { q } _ { \mathrm { t } } ( \mathrm { i } , \mathrm { y } ) \mathrm h _ { \mathrm { t } } ( \mathrm x _ { \mathrm { i } } , \mathrm { y } ) )$ //计算基分类器 $\mathbf { h } _ { \mathfrak { t } }$ 的伪误差 $\mathbf { \varepsilon } _ { \mathbf { E } _ { \mathrm { t } } }$

21: end for

22: $\boldsymbol { \mathfrak { E } } _ { \mathrm { t } } = \frac { 1 } { 2 } \boldsymbol { \mathfrak { E } } _ { \mathrm { t } }$ //得出伪误差 $\mathbf { \varepsilon } _ { \mathbf { \varepsilon } _ { \mathrm { { t } } } }$

23: $\beta _ { \mathrm { t } } { = } \varepsilon _ { \mathrm { t } } / ( 1 \nu \varepsilon _ { \mathrm { t } } )$ //计算 $\beta _ { \mathrm { t } }$

24. for each $\mathrm { i } \{ 1 , ? \mathrm { ~ } , \mathrm { m } \}$ do:

25: $\mathbf { W } _ { \mathrm { i , y } } ^ { \mathrm { t + 1 } } \mathrm { = } \mathbf { W } _ { \mathrm { i , y } } ^ { \mathrm { t } } \boldsymbol { \beta } _ { \mathrm { t } } ^ { ( \frac { 1 } { 2 } ) ( 1 + \mathbf { h } _ { \mathrm { t } } \left( \mathbf { x } _ { \mathrm { i , } } \mathbf { y } _ { \mathrm { i } } \right) - \mathbf { h } _ { \mathrm { t } } \left( \mathbf { x } _ { \mathrm { i } } , \mathbf { y } \right) ) }$ （204号 //更新权重

26: end for

# 27:end for

28:return $\mathrm { { H } ( x ) = \mathrm { { a r g m a x } } \sum _ { t = 1 } ^ { T } \mathrm { { g } \frac { 1 } { \beta _ { t } } h _ { t } ( x , y ) } }$ //T次循环结束后，输出最终的集成分类器H，并运用测试样本进行测试，通过投票的方式得到分类结果

# 2 实验与分析

# 2.1实验设置

本文实验采用的两个共享因特网流量数据集分别为Cambridge1[16]和 Cambridge2[17]。Cambridge1 和 Cambridge2 流量数据集均取自剑桥大学的研究网站，其中Cambridge1包括ENT1，ENT2，...，ENT10和ENT12共11个子数据集，Cambridge2包括dayl，day2，day3和siteb共四个子数据集，本文选取其中entl，ent2，day1和day2共四个数据集进行对比实验，数据集ent1中各类别样本数目如表1所示，可以看出各类别样本数目存在严重的不平衡。

表1数据集ENT1各类别样本数目  

<html><body><table><tr><td>类别</td><td>数目</td><td>类别</td><td>数目</td></tr><tr><td>WWW</td><td>18211</td><td>MAIL</td><td>4146</td></tr><tr><td>FTP-PASV</td><td>43</td><td>ATTACK</td><td>122</td></tr><tr><td>DATABASE</td><td>238</td><td>FTP-DATA</td><td>1319</td></tr><tr><td>SERVICES</td><td>206</td><td>MULTIMEDIA</td><td>87</td></tr><tr><td>FTP-CONTROL</td><td>149</td><td>P2P</td><td>339</td></tr></table></body></html>

实验中所有参与比较的算法分别为AdaBoost.M2-reweighting(简称 ADAM2-rewei),AdaBoost.M2-resampling(简称ADAM2-resam)，SMOTEBoost(简称 SB-采样比例 $100 \%$ ，SMOTEBoost(简称 SB-采样比例 $200 \%$ ),SMOTEBoost(简称 SB-采样比例 $50 0 \%$ ，RUSBoost(简称RB)和本文RBWS-ADAM2。

实验采用Python 实现，集成学习算法的迭代次数设置为

100，并选择最大深度为5的CART决策树作为所有集成学习算法的基分类器。实验结果通过十重交叉验证获得。实验评价分类器性能的指标包括总体分类精度，总体平均F-measure，总体G-mean 和单类F-measure，其中总体平均F-measure 是所有类别网络流分类F-measure的平均值，总体平均F-measure和总体G-mean都可以衡量分类器对多类不平衡数据集的分类性能。

# 2.2实验结果比较与分析

# 2.2.1 Kappa-error 图

Kappa-error图是衡量集成分类器多样性的重要表现形式，假设有一个样本数目为N的测试集和两个分类器C1和C2，表2表示的是测试集中被分类器C1和C2分类正确或错误的样本数，例如a为C1和C2都分类正确的样本数，b为C1分类正确C2分类错误的样本数，abcd四项的总和为 $\mathrm { ~ N ~ }$ 。

表2C1和C2分类情况示例  

<html><body><table><tr><td></td><td>C2 correct</td><td>C2 wrong</td></tr><tr><td>C1 correct</td><td>a</td><td>b</td></tr><tr><td>C1 wrong</td><td>C</td><td>d</td></tr></table></body></html>

两个分类器之间的差异可以通过 $\mathbf { k }$ 值衡量，计算公式如式(1)所示。

$$
\mathrm { k } { = } \frac { 2 ( \mathrm { a d } { \cdot } \mathrm { b c } ) } { \bigl ( \mathrm { a } { + } \mathrm { b } \bigr ) \bigl ( \mathrm { b } { + } \mathrm { d } \bigr ) { + } ( \mathrm { a } { + } \mathrm { c } ) ( \mathrm { c } { + } \mathrm { d } ) }
$$

$\mathbf { k }$ 值代表的是Kappa-error 图中 $\mathbf { x }$ 轴，值越小代表两个分类器之间差异性越大。此外，可以通过e值来衡量两个分类器的平均误差，计算公式如式(2)。平均误差 $\mathrm { ~ \bf ~ e ~ }$ 代表的是Kappa-error图中y轴error。

$$
\mathrm { e } { = } \frac { 1 } { 2 } \Bigg ( \frac { \mathrm { c } { + } \mathrm { d } } { \mathrm { N } } { + } \frac { \mathrm { b } { + } \mathrm { d } } { \mathrm { N } } \Bigg ) { = } \frac { \mathrm { b } { + } \mathrm { c } { + } 2 \mathrm { d } } { 2 \mathrm { N } }
$$

假设一个集成分类器有L个子分类器，则这L个子分类器就会在Kappa-error 图中产生L(L-1)/2个点，每个点对应一对子分类器。本文计算了200 个RBWS-ADAM2 和 200 个AdaBoost.M2中子分类器对应的Kappa-error点。图1中a图和b 图分别是RBWS-ADAM2和AdaBoosT.M2 对应的Kappa-error图，每个图中只包含200个数据点。

![](images/8eb44827d9e2691651763e0b4eb0176e53e90ccd1582b35ae740d378fa73fcc1.jpg)  
图1Kappa-error 图

如图1所示，在Kappa-error图1（b）中，RBWS-ADAM2的数据点分布相对于图1（a）的AdaBoost.M2在 $\mathbf { x }$ 轴和y轴方向的跨度都更大，表明RBWS-ADAM2的分类器产生了更大的多样性。此外，可以看出图1（b）中点集分布是倾斜的，在y轴跨度相对于图1(a)更大，表明在增加分类器多样性的同时，

分类误差也会略有增大。

# 2.2.2实验指标对比分析

表3\~6是各算法在各数据集上进行对比实验的结果。其中总体分类精度用ALL-PRE 表示，总体G-mean用ALL-GMN表示，总体平均F-measure用ALL-AVG-FM表示，训练时间用T表示。

表3ent1各算法对比结果  

<html><body><table><tr><td>算法</td><td>ALL-PRE</td><td>ALL-GMN</td><td>ALL-AVG-FM</td><td>T(s)</td></tr><tr><td>ADAM2-REW</td><td>0.9851</td><td>0.8077</td><td>0.8597</td><td>146.95</td></tr><tr><td>ADAM2-RES</td><td>0.9839</td><td>0.7651</td><td>0.8249</td><td>150.06</td></tr><tr><td>SB(100)</td><td>0.9840</td><td>0.7781</td><td>0.8444</td><td>232.70</td></tr><tr><td>SB(200)</td><td>0.9744</td><td>0.4973</td><td>0.7093</td><td>213.88</td></tr><tr><td>SB(500)</td><td>0.9786</td><td>0.6672</td><td>0.7801</td><td>270.97</td></tr><tr><td>RB</td><td>0.9721</td><td>0.8072</td><td>0.8267</td><td>164.05</td></tr><tr><td>本文算法</td><td>0.9530</td><td>0.8508</td><td>0.8997</td><td>608.85</td></tr></table></body></html>

表4ent2 各算法对比结果  

<html><body><table><tr><td>算法</td><td>ALL-PRE</td><td>ALL-GMN</td><td>ALL-AVG-FM</td><td>T(s)</td></tr><tr><td>ADAM2-REW</td><td>0.9901</td><td>0.7952</td><td>0.8363</td><td>171.17</td></tr><tr><td>ADAM2-RES</td><td>0.9897</td><td>0.8074</td><td>0.8543</td><td>142.97</td></tr><tr><td>SB(100)</td><td>0.9889</td><td>0.8614</td><td>0.9102</td><td>203.97</td></tr><tr><td>SB(200)</td><td>0.9875</td><td>0.7785</td><td>0.8696</td><td>188.23</td></tr><tr><td>SB(500)</td><td>0.9823</td><td>0.7075</td><td>0.8372</td><td>264.69</td></tr><tr><td>RB</td><td>0.9889</td><td>0.8964</td><td>0.9198</td><td>170.64</td></tr><tr><td>本文算法</td><td>0.9912</td><td>0.9072</td><td>0.9369</td><td>590.0</td></tr></table></body></html>

表5dayl各算法对比结果  

<html><body><table><tr><td>算法</td><td>ALL-PRE</td><td>ALL-GMN</td><td>ALL-AVG-FM</td><td>T(s)</td></tr><tr><td>ADAM2-REW</td><td>0.9861</td><td>0.8854</td><td>0.9001</td><td>2850.8</td></tr><tr><td>ADAM2-RES</td><td>0.9571</td><td>0.8989</td><td>0.9169</td><td>1224.3</td></tr><tr><td>SB(100)</td><td>0.9546</td><td>0.9002</td><td>0.8860</td><td>5741.2</td></tr><tr><td>SB(200)</td><td>0.9562</td><td>0.9084</td><td>0.9083</td><td>5023.3</td></tr><tr><td>SB(500)</td><td>0.9826</td><td>0.6667</td><td>0.8174</td><td>6374.4</td></tr><tr><td>RB</td><td>0.9809</td><td>0.9073</td><td>0.8817</td><td>2155.2</td></tr><tr><td>本文算法</td><td>0.9566</td><td>0.9345</td><td>0.9427</td><td>9798.3</td></tr></table></body></html>

表6day2 各算法对比结果  

<html><body><table><tr><td>算法</td><td>ALL-PRE</td><td>ALL-GMN</td><td>ALL-AVG-FM</td><td>T(s)</td></tr><tr><td>ADAM2-REW</td><td>0.9333</td><td>0.9431</td><td>0.9254</td><td>3526.3</td></tr><tr><td>ADAM2-RES</td><td>0.9338</td><td>0.9251</td><td>0.9114</td><td>2686.9</td></tr><tr><td>SB(100)</td><td>0.9031</td><td>0.9384</td><td>0.9069</td><td>5333.2</td></tr><tr><td>SB(200)</td><td>0.9201</td><td>0.9445</td><td>0.9190</td><td>6002.2</td></tr><tr><td>SB(500)</td><td>0.9047</td><td>0.9332</td><td>0.8564</td><td>7956.3</td></tr><tr><td>RB</td><td>0.9720</td><td>0.9588</td><td>0.9496</td><td>2598.8</td></tr><tr><td>本文算法</td><td>0.9060</td><td>0.9545</td><td>0.9316</td><td>9853.1</td></tr></table></body></html>

如表3\~6所示，在数据集ent1，ent2和day1上，相比其他算法，本文RBWS-ADAM2算法在总体G-mean和总体平均F-measure两个指标上均有较大程度的提升，说明本文算法对于解决集成学习面临的多类不平衡问题，提升AdaBoost.M2算法的整体分类性能起了很好的效果，特别是在数据集ent2上，本文算法的总体G-mean 和总体平均F-measure 比AdaBoost.M2-reweighting 提升高达 $10 \%$ 左右。对比总体分类精度，本文RBWS-ADAM2算法虽然在数据集ent2上最高，但是在其他数据集上均有所下降，与AdaBoost.M2-reweighting也基本保持在$0 . 0 1 { \sim } 0 . 0 4$ 的差距，这验证了图1的分析结论，本文算法对多类不平衡数据分类性能的提升是以损失一定的分类精度为代价的

对于RUSBoost算法，其在部分数据集上表现很好，但是在其他数据集上出现波动，比如在数据集DAY2上该算法的三项指标值都是最高，但是在数据集ent1上其总体G-mean和总体平均F-measure 两个指标均与最高值有较大差距。对于SMOTEBoost算法，采样比例是影响算法表现的重要因素，本文选取 $100 \%$ $200 \%$ 和 $500 \%$ 三个采样阈值进行对比实验的结果表明，不同数据集的最优采样比例可能不相同，例如在数据集ent2上，最优的采样比例为 $100 \%$ ，而在数据集day2上，最优的采样比例却为 $200 \%$ 。本文RBWS-ADAM2 算法在所有数据集上的表现都较为稳定，即使在部分数据集中没有取得最好的分类表现，却也保持在较高的水平。

此外，从训练时间的对比可以看出，本文算法的训练时间相比于其他算法较长，出现这种情况是因为本文算法的处理逻辑相比于其他算法更加复杂。为进一步分析本文算法对少数类分类的提升效果，图2展示了数据集ent1上各算法对各类别的F-measure 对比结果。

1 0.9 0.8 0.7 0.7 F 0.6 0.6 0.5 0.5 0.4 0.4 ADA ADA SB100SB200SB500 RB RBWS ADA ADASB100 SB200 SB500 RB RBWS -REWEI -RESAM -ADAM2 -REWEI-RESAM -ADAM2 (a)ATTACK (b)MULTIMEDIA 1 1 J.aaeeeee 0.9 0.8 0.7 0.7 0.6 0.6 ADA ADA SB100SB200SB500 RB RBWS ADA ADASB100 SB200 SB500RB RBWS -REWEI -RESAM −ADAM2 -REWEI-RESAM -ADAM2 (c) FTP-CONTROL (d) SERVICES   
T 山 0.6 0.6 ADA ADASB100 SB200 SB500 RB RBWS ADAADASB100 SB200 SB500RB RBWS -REWEI -RESAM -ADAM2 -REWEI-RESAM -ADAM2 (e) MAIL (f)FTP-DATA 1 1 MII 0.6 0 ADA ADASB100 SB200 SB500RB RBWS ADAADASB100 SB200 SB500RBRBWS -REWEI-RESAM −ADAM2 -REWEI-RESAM −ADAM2 (g)P2P (h) FTP-PASV   
E M ADA ADASB100 SB200 SB500RB RBWS ADA ADASB100 SB200 SB500RBRBWS -REWEI -RESAM -ADAM2 -REWEI-RESAM −ADAM2 (i)WWW (i)DB

由图2可得，本文RBWS-ADAM2算法对Attack，FTP-control，Multimedia和P2P这四类少数类协议的F-measure 较其他算法均有较为显著的提升，说明本文算法对部分少数类的分类能力相比于其他算法有明显提高，而对其他少数类或多数类，本文算法的F-measure 也与其他算法中表现最优的基本相近，例如就DatabasE 而言，SMOTEBoost(20O)的F-measure 最低，而 本 文 RBWS-ADAM2 算 法 的 F-measure与SMOTEBoost(100)同样处于较高的水平并且差距极小。

就RUSBoost而言，对于大部分少数类，其F-measure相对于AdaBoost-reweighting均有一定程度的提高，而对多数类WWW，RUSBoost对应的F-measure却略低于其他算法，出现这种情况可能是因为在对多数类随机欠采样时，误删了部分包含有用信息的样本，影响了分类器对多数类的学习，以上分析说明虽然利用随机欠采样来平衡数据集会在一定程度上提升对部分少数类的分类能力，但是很可能会降低对多数类的分类效果。另外从图2中SMOTEBoost三种不同阈值的实验对比结果可以看出，采样比例对SMOTEBoost的算法表现产生了明显的影响。其中对于FTP-control，Multimedia，Database 和P2P 四类，F-measure 随着采样阈值的增加不断降低，说明对于这四类，采样阈值不需要超过 $100 \%$ ，对于FTP-DATA，Mail和WWW三类，三种采样阈值下的算法表现相差不多，而Attack，FTP-PASV和Services三类的则分别在 $500 \%$ ， $200 \%$ 和 $500 \%$ 取得最高的F-measure。以上分析表明不仅对不同数据集SMOTEBoost算法的最优采样阈值不同，对不同类别的最优采样阈值也可能不同。

此外，从FTP-PASV的F-measure 对比可以发现，AdaBoost-resampling 算法对应的 F-measure 出现了远低于其他算法的情况。通过查看表1，可以发现在数据集ent1中，FTP-PASV的样本数目仅有43，远少于其他类别。由此可推断，出现这种情况是因为AdaBoost-resampling 中采用的有放回随机抽样策略导致数目较少的FTP-PASV样本在重采样过程中被忽略，进而造成分类器对该类样本学习不足。

前述实验中，集成学习算法的迭代次数设置为100，为探究迭代次数对集成分类器分类效果的影响，本文再次设置迭代次数为0到100，利用AdaBoost.M2和RBWS-ADAM2对数据集 ent1进行训练与测试，以观察集成分类器的总体平均F-measure随迭代次数变化情况，实验结果如图3所示。

![](images/7cc334525210c0e8c31ff143d6677294fb50ad2c5e335949e21193e1eeeed09f.jpg)  
图3总体平均F-measure 随迭代次数变化图

由图3可见两种集成分类器的总体平均F-measure 随着迭代次数增加而不断提升，当迭代次数增加到40之后，折线上升的幅度才逐渐变缓，并在数次波动后趋于平缓稳定，最终AdaBoost.M2对应的总体平均F-measure 稳定在0.85左右，而本文RBWS-ADAM2对应的总体平均F-measure 稳定0.90 左右。在折线上升过程中，可以发现当迭代次数约小于20时，RBWS-ADAM2的总体平均F-Measure总是低于AdaBoost.M2，但随着迭代次数增加，RBWS-ADAM2逐渐高于AdaBoost.M2并拉开差距直至最终趋于稳定。可以推断出现这种现象的原因是RBWS-ADAM2中构造的训练集具有较大差异性，当迭代次数较低时，其无法代表全部的原始训练集，并且其差异性学习没有发挥优势，还可能因为出现极端差异性而影响分类器的学习效果，导致集成分类器的分类性能甚至比不上AdaBoost.M2分类器，然而随着迭代次数增加到一定程度，各训练集在具备差异性的同时，也具备覆盖全部原始训练集的条件，从而保证集成分类器可以充分学习到全部原始训练数据，因此提升了算法的整体性能。

# 2.3算法复杂度分析

通过对本文RBWS重采样策略的伪代码进行时间复杂度分析，得出第03到07行的复杂度为 $\mathrm { O ( k ) }$ ，第11行的复杂度为 $\operatorname { O } ( \mathrm { k } _ { \mathfrak { n } ^ { 2 } } )$ ，第12行到15行的复杂度为 $\mathrm { O } ( \mathrm { k } _ { \mathrm { n } ^ { 2 } } )$ ，第18到22行的复杂度为 $\mathrm { \Gamma _ { } O ( k n ) }$ ，其他部分复杂度均为常数级。综上，得出RBWS 重采样策略的复杂度为 $\operatorname { O } ( { \mathfrak { n } } ^ { 2 } )$ ）

通过对本文RBWS-ADAM2算法的伪代码进行时间复杂度分析，得出第01到04行的复杂度为 $\mathrm { O ( n ) }$ ，第06到08行的复杂度为 $\mathrm { \Gamma _ { } O ( k n ) }$ ，第09到12行复杂度为 $\mathrm { \Gamma _ { } O ( k n ) }$ ，第13行中RBWS重采样过程的复杂度为 $\mathrm { O } ( \mathrm { k } _ { \mathfrak { n } ^ { 2 } } )$ ，第14 行到16行的复杂度为O(k)，第18行基分类器训练的复杂度为 $\mathrm { { O } ( k n ) }$ ，第19到21行的复杂度为 $\mathrm { { { O } ( k n ) } }$ ，第24行到26行的复杂度为 $\mathrm { { { O } ( k n ) } }$ ，其他部分复杂度均为常数级。最终得出，本文RBWS-ADAM2算法的时间复杂度为 $\operatorname { O } ( { \mathfrak { n } } ^ { 2 } )$ ）

本文算法和实验中各算法的时间复杂度对比结果如表7所示。

表7算法时间复杂度对比  

<html><body><table><tr><td>算法</td><td>复杂度</td><td>算法</td><td>复杂度</td></tr><tr><td>ADABOOST.M2</td><td>O(n)</td><td>RUSBOOST</td><td>O(n)</td></tr><tr><td>SMOTEBOOST</td><td>0(n)</td><td>本文算法</td><td>（n²）</td></tr></table></body></html>

由表7可见，本文算法的时间复杂度为 $\operatorname { O } ( { \mathfrak { n } } ^ { 2 } )$ ，较高于其他算法，这是因为本文算法的处理逻辑相对于对比的算法稍复杂，但从前述实验结果可以看出，本文算法取得了最优的分类效果。

# 3 结束语

本文主要针对网络流量中的多类不平衡问题，提出一种集成学习算法RBWS-ADAM2，该算法在ADABOOST.M2每次迭代时，设计了基于样本权重的随机平衡重采样策略来对训练集进行预处理，在解决数据多类不平衡问题的同时，增大训练集之间的差异性以提升集成分类器的泛化性能。在国际公开数据集Cambridge1和Cambridge2的部分数据集上进行对比实验的结果表明，本文提出的算法不仅可以有效提升集成分类器对于部分少数类的F-Measure，也有效提升了集成分类器的总体G-Mean和总体平均F-Measure，在缓解数据多类不平衡对少数类分类影响的同时，提高了集成学习算法的整体泛化性能，使得集成分类器在面临多类不平衡网络流量时具备更强的分类能力。后期工作主要是针对本文算法训练时间稍长的不足进行优化。

# 参考文献：

[1]Khater N,Overill R.Network traffic classification techniques and challenges [C]// Proc of the 1Oth International Conference on Digital Information Management. 2016: 43-48.   
[2]Chawla N,Bowyer K,HallL,et al. Smote: synthetic minority over-sampling technique [J]. Journal of Artificial Intelligence Research,20o2,16(1): 321- 357.   
[3]Yen S J,Lee Y S.Cluster based under-sampling approaches for imbalanced data distributions [J].Expert Systems with Applications,2009,36(3): 5718- 5727.   
[4]Agrawal A,Viktor H,Paquet E.SCUT:multi-class imbalanced data classification using smote and cluster-based undersampling [C]//Proc of International Joint Conference on Knowledge Discovery.2016: 226-234.   
[5]Blaszczynski j,Stefanowski j.Neighbourhood sampling in bagging for imbalanced data [J].Neuro Computing,2015,150 (52): 529-542.   
[6]Wang S,Yao X.Multi-class imbalance problems: analysis and potential solutions[J]. IEEE Trans on Systems,Man and Cybernetics,Part B,2012, 42 (4): 1119-1130.   
[7]Wang s,Yao x.Diversity analysis on imbalanced data sets by using ensemble models [C]//Proc ofIEEE Symposium Series on Computational Intelligence and Data Mining.2009: 324-331.   
[8]Freund Y,Schapire R.Experiments with a new boosting algorithm [C]//Proc of the 13th International Conference on Machine Learning.1996:148-156.   
[9]Chawla N, Lazarevic A,Hall L. SMOTEBoost: improving prediction of the minority class in boosting[C]//Proc of the 7th European Conference on Principles and Practice of Knowledge Discovery in Databases.[S.1.] : Springer,2003:107-119.   
[10] Barua S,Islam M,Yao X,et al.MWMOTE-Majority weighted minority oversampling technique for imbalanced data set learning [J]. IEEE Trans on Knowledge and Data Engineering,2014,26 (2): 405-425.   
[11] Seifert C,Khoshgoftaar T,Hulse JV,et al. Rusboost: a hybrid approach to alleviating class imbalance [J].IEEE Trans on Syst,Man Cybern,PartA: Syst. Hum,2010,40(1): 185-197.   
[12] Molinara M, Ricamato M, Tortorella F.Facing imbalanced classes through aggregation of classifiers [Cl//Proc of the 14th International Conference on Image Analysis and Processing. 2007: 43-48.   
[13] Stefanowski J. Overlapping,rare examples and class decomposition in learning classifiers from imbalanced data [M]// Emerging Paradigms in Machine Learning. Springer,2013: 277-306.   
[14] Wang S,Yao X.Relationships between diversity of classification ensembles and single-classperformance measures [J]. IEEE Trans on Knowl. Data Eng, 2013,25 (1): 206-219.   
[15] Seiffert C,Khoshgoftaar T,Hulse JV.Resampling or Reweighting:A Comparison of Boosting Implementations [C]// Proc of IEEE International Conference on Tools with Artifical Intelligence. 20o8,1: 445-451.   
[16] Moore A M, Zuev D,Crogan M.Discriminators for use in flowbased classification [R].2005:1-16.   
[17]LiW, Canini M,Moore A W,et al.Efficient application identification and the temporal and spatial stability of classification schema [J].Computer Networks,2009,53 (6): 790-809.