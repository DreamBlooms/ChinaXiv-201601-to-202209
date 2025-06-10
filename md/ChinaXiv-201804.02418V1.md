# 基于LDA主题模型的用户电信轨迹恢复算法

徐广根1，杨璐1,²，严建峰1,2，徐彩旭1，石鸿斌1(1．苏州大学 计算机科学与技术学院，江苏 苏州 215006;2.香港城市大学 创意媒体学院，香港 中国)

摘要：随着移动通信技术的发展和移动设备的普及，关于人们日常移动行为的轨迹数据记录愈发的丰富起来。海量的轨迹数据背后隐藏着关于人及人类社会的有价值的知识模式。为了使基于轨迹数据产生的知识模式更精准有效服务用户，能够准确、可靠地恢复缺失电信轨迹显得尤为重要。目前大多数方法主要针对GPS 轨迹等连续轨迹进行建模，而缺乏对移动通信场景中产生的电信轨迹恢复的研究。因此，针对电信轨迹缺失恢复问题，将电信轨迹恢复问题转化为矩阵补全问题，提出了一种基于LDA主题模型的恢复算法。实验中，与传统矩阵补全算法进行综合比较，并观察了不同参数对轨迹恢复效果的影响。实验结果表明，与传统矩阵补全算法相比，运用LDA主题模型能够显著提高缺失电信轨迹的恢复精度。

关键词：电信轨迹；轨迹恢复；LDA主题模型 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2018.01.0066

# User telco trajectory recovery algorithm based on LDA topic model

Xu Guanggen1, yang Lul,2, Yan Jianfeng1,2†, Xu Caixu1, Shi Hongbin1 (1.SchoolofComputerSience&TechnologySoochow University,uzhouJiangsu5o6,China;2.holofCreativeedia, City University of Hong Kong China)

Abstract: With thedevelopmentofmobilecommunicationtechnologyandthe popularizationofmobiledevices,thedailytrack record data becomerich.Massive track data hides valuable kowledgeabout personand human society.Inorder to make the knowledgemodel generatedbasedonthetrajectorydatamoreaccurateandefectivetoservetheusers,itisparticularlyportant to beable torecover the missing telco trajectories auratelyand reliably.Currently,mostofthe methods mainly focus on modelingcontinuous trajectoriessuchas GPStrajectories,butlackofresearchesontherestorationoftelcotrajectories geerated in mobile communication scenarios.Therefore,ithave transformedthe problemof telecommunicationtrajectoryrecovery into a matrix completion problem,andproposedarecoveryalgorithm basedontheLDA topic model.In the experiment,itmake a comprehensivecomparison with the traditional matrix completion algorithmand observe the effectof diferent parameters on trajectoryrecovery.Theexperimental results show thatcompared with the traditional matrix completion algorithm,theLDA topic model can significantly improve the recovery accuracy of missing telco tracks.

Key words:telco trajectory; trajectory recovery;LDA topic model

# 0 引言

在当前大数据时代，数据所带来的影响远远超出了企业领域，其不仅能带来商业价值，也能产生社会价值。随着信息通讯技术的发展，手机普及率越来越高，移动通信基站的覆盖率也越来越高。因此，研究手机定位技术获取的轨迹信息，不但可以为城市交通规划和出行方式的划分提供更有效决策[,2]，甚至可以利用节假日中用户的出行定位数据估计出可能会产生的客流高峰和区域，从而及时做好相应的交通管理。因此，如何精准地恢复用户轨迹的缺失部分，从而挖掘更丰富的知识模式，为用户提供人性化的服务具有极高的应用价值。移动对象轨迹缺失恢复研究引起了学术界的广泛关注。Lou 等人[3提出了一种对于行驶过程中采样率很低的稀疏轨迹进行直接匹配的算法研究。但局限是忽略了时间间隔较大的稀疏轨迹。在时间间隔较大的情况下，该算法不能把匹配的路段拼接起来形成完整轨迹。Bernstein等人4使用GPS轨迹数据统计得到车辆运行速度、方向拐角、车辆运行的连续性等特征，加上车辆前一段时段轨迹数据点匹配来分析采样率较低的轨迹数据点，根据车辆行驶的历史轨迹信息提高了稀疏轨迹点匹配的精度。Zheng等人根据车辆行驶的历史轨迹数据建立了一套路径推理系统，提高了路径推理的准确性。该算法可以快捷地匹配采样率低的稀疏轨迹，有效地恢复了采样率较低的稀疏轨迹缺失部分。罗宇等人[6.7]提出了一种基于隐马尔科夫模型的局部最优状态路径的轨迹恢复算法，利用最大后验概率构建轨迹的缺失状态。徐超等人提出了还原个人出行GPS轨迹缺失的算法，通过设置经验阈值分析轨迹中缺失的情况，然后定义了最优路径的概念来搜索GPS轨迹缺失处的轨道站点，最终选择最优路径来还原GPS轨迹中的缺失路段。上述所有方案都为本文的研究提供了指导性作用，但存在的局限都是基于全球定位系统(globalpositioning system,GPS)技术9产生的轨迹恢复缺失时段的位置，而且都需要使用获取成本较高的路网数据。基于GPS定位的轨迹精度高、实时性高，而电信基站定位产生的轨迹数据量大、覆盖面积广，但精度低、离散程度高。针对上述方案的不足，本文充分考虑电信轨迹缺失的问题，对上海某运营商产生的用户电信轨迹在时空上完成预处理。具体过程是：在时间上将一天划分成若干个时间段，空间上城市基于K-Means聚类算法划分，再构建时空单词矩阵，将轨迹缺失恢复问题转换为矩阵缺失补全问题，最后运用LDA主题模型恢复缺失电信轨迹。

# 1 潜在狄里克雷分配

# 1.1LDA 模型原理

LDA模型是Blei等人[10在2003年提出的一种对离散数据集（如文档集）建模的概率主题模型，是一种对文本数据的主题信息进行建模的方法，通过发现文档中抽象的主题，挖掘语义背后隐含的信息，从而有助于高效地处理大规模的文档集。LDA模型是一个包含单词、主题、文档的三层贝叶斯网络概率图模型[11]。基于这样一种前提假设：文档是由若干个隐含主题构成，这些主题是由文本中若干个特定有效词汇构成，忽略文档中的句法结构和单词出现的先后顺序[12]。LDA 模型文档-主题-单词拓扑结构如图1所示。

![](images/9fdbef332b4debbef0c019223ad4e2c96a2e46eb54b6d24f50e918c0025f85e9.jpg)  
图1LDA模型文档一主题一单词拓扑结构

图2是常用的LDA图模型的表示。在图2中圆圈表示变量；深色表示可观测变量；浅色表示超参数或隐含变量；方框表示重复循环；箭头表示依存关系。符号标签含义如表1所示。

表1符号标签含义  

<html><body><table><tr><td>1≤d≤D</td><td>文档索引</td></tr><tr><td>1≤n≤V</td><td>单词索引</td></tr><tr><td>1≤k≤K</td><td>主题索引</td></tr><tr><td></td><td>文档d的主题多项分布(K维向量)</td></tr><tr><td></td><td>主题k的单词多项分布(V维向量)</td></tr><tr><td>ODxK</td><td>文档-主题分布矩阵</td></tr><tr><td>Φxxv</td><td>主题-单词分布矩阵</td></tr><tr><td>Nd</td><td>文档d的长度</td></tr><tr><td>Zd，n</td><td>文档d中第n个单词的主题</td></tr><tr><td>Wd,n</td><td>文档d中第n个单词的词项</td></tr><tr><td>ZDxv ={zd,n}</td><td>单词的主题标签</td></tr><tr><td>W Dxv ={Wd,n}</td><td>文档-单词矩阵</td></tr><tr><td>a</td><td>文档-主题分布的超参数</td></tr><tr><td>β</td><td>主题-单词分布的超参数</td></tr></table></body></html>

![](images/4dd6da6767d84304c67337e93f4b3b31ec49b24490f6f3f5d366eebee06a03da.jpg)  
图2LDA贝叶斯图模型

算法1 LDA 概率主题模型生成文档集过程

# //主题

1. for所有的主题 $k \in [ 1 , K ]$ ：  
2. 采样 $\overrightarrow { \varphi _ { k } } \sim D i r i c h l e t ( \beta )$   
3. end for  
//文档  
4. for 所有的文档 $d \in [ 1 , D ]$ ：  
5. 采样 $N _ { d } \sim P o i s s o n ( \zeta )$   
6. 采样 $\overrightarrow { \mathbfit { S } _ { d } } \sim D i r i c h l e t ( \alpha )$   
7. for 对文档 $d$ 中所有的单词 $n \in [ 1 , N _ { d } ]$ ：  
8. 采样 $z _ { d , n } \sim M u l t i ( \overrightarrow { \mathcal { P } _ { d } } )$   
9. 采样 $w _ { d , n } \sim M u l t i ( \overrightarrow { { \varphi } _ { z _ { d , n } } } )$   
10. end for  
11. end for

根据生成文本过程，在给定先验参数 $\alpha$ 和 $\beta$ 的条件下，可以得到文档集的联合概率分布（包括所有可观测变量和隐含变量)：

$$
\begin{array} { r } { p ( \mathbf { w } , \mathbf { z } , \Theta , \Phi | \alpha , \beta ) = \displaystyle \prod _ { k = 1 } ^ { K } p ( \vec { \varphi } _ { k } | \beta ) \cdot \prod _ { d = 1 } ^ { D } p ( \overrightarrow { \mathcal { S } _ { d } } | \alpha ) } \\ { \cdot \prod _ { n = 1 } ^ { N _ { d } } p ( z _ { d , n } | \overrightarrow { \mathcal { S } _ { d } } ) p ( w _ { d , n } | \overrightarrow { \varphi _ { z _ { d , n } } } ) } \end{array}
$$

对于生成单词 $w _ { d , n } = t$ 的概率如下：

$$
\begin{array} { r } { p ( w _ { d , n } = t | \overrightarrow { \mathcal { G } _ { d } } , \Phi ) = \sum _ { k = 1 } ^ { K } p ( w _ { d , n } = t | \overrightarrow { \varphi _ { k } } ) p ( z _ { d , n } = k | \overrightarrow { \mathcal { G } _ { d } } ) } \end{array}
$$

给定文档集后，LDA模型的目标就是使得隐含变量 $Z$ 的后验概率最大化（maximumaposteriori,MAP)。根据上述文档集生成过程，可以得到包含隐含变量的后验概率分布是

$$
p ( \mathbf { z } , \Theta , \Phi | \mathbf { w } , \alpha , \beta ) { = } \frac { p ( \mathbf { w } , \mathbf { z } , \Theta , \Phi | \alpha , \beta ) } { p ( \mathbf { w } | \alpha , \beta ) }
$$

其中： $p ( \mathbf { w } | \alpha , \beta )$ 是文档集联合概率$p ( \mathbf { w } , \mathbf { z } , \Theta , \Phi | \alpha , \beta )$ 在文档主题分布 $\Theta$ 和主题单词分布 $\Phi$ 上的积分，计算复杂度高，所以需要可接受的近似推理算法来计算该后验概率。

# 1.2 Gibbs采样

Gibbs采样通过对难以求解的隐含变量的后验概率进行采样，迭代更新来获得LDA主题模型最终的参数。Gibbs 采样[13]基础理论是马尔可夫链蒙特卡洛[14]（Markovchain Monte Carlo,MCMC)。马尔可夫链的数学定义为

$$
p ( X _ { t + 1 } = x \vert X _ { t } , X _ { t - 1 } , . . . ) = p ( X _ { t + 1 } = x \vert X _ { t } )
$$

Gibbs采样是相对简单的算法，经常用于近似推理高维度模型。LDA主题模型的Gibbs采样算法把主题看做隐含变量，通过对文档集的联合分布中 $\Theta$ 和 $\Phi$ 进行积分消除，因为它们可以通过已经观测的单词 $w _ { d , n }$ 和对应的主题标签 $z _ { d , n }$ 联合统计得到。每个单词的主题标签 $\boldsymbol { z } _ { d , n }$ 是马尔可夫链上的状态变量，然后利用MCMC采样算法进行推理。这种通过一些参数进行积分的模型推理算法被称为“塌陷”，通过积分得到主题的后验分布为 $p ( \mathbf { z } \mid \mathbf { w } )$ 。

$$
p ( \mathbf { z } \mid \mathbf { w } ) = { \frac { p ( \mathbf { z } , \mathbf { w } ) } { p ( \mathbf { w } ) } }
$$

从式(5)可以得到，使用Gibbs采样算法，则需要计算主题和单词的联合概率分布。在LDA中，主题和单词的联合概率分布可以分解为 $p ( \mathbf { z } , \mathbf { w } ) = p ( \mathbf { z } \mid \alpha ) \cdot p ( \mathbf { w } \mid \mathbf { z } , \beta )$ ，这两个因子分别对应着LDA生成文档集的两个过程：

a) $\alpha  \overrightarrow { \mathcal { S } _ { d } }  z _ { d , n }$ 表示生成文档中所有单词的主题。$\alpha  \overrightarrow { \mathcal { A } _ { d } }$ 是 Dirichlet 分布， $\overrightarrow { \mathcal { S } _ { d } }  z _ { d , n }$ 是多项分布，所以整个过程是Dirichlet-Multinomial共轭结构。

$$
\begin{array} { l } { { \displaystyle p ( { \bf z } \vert { \boldsymbol \alpha } ) = \int p ( { \bf z } \vert \boldsymbol \alpha ) p ( \boldsymbol \Theta \vert { \boldsymbol \alpha } ) d \Theta } \ ~ } \\ { { \displaystyle ~ = \int \prod _ { d = 1 } ^ { D } \frac { 1 } { \Delta ( \alpha ) } \prod _ { k = 1 } ^ { K } g _ { d , k } ^ { n _ { d } ^ { ( k ) } + \alpha _ { k } - 1 } d \overrightarrow { { \boldsymbol g } _ { d } ^ { - } } } \ ~ } \\ { { \displaystyle ~ = \prod _ { d = 1 } ^ { D } \frac { \Delta ( \stackrel { \longrightarrow } { \boldsymbol \alpha } + { \boldsymbol \alpha } ) } { \Delta ( \alpha ) } , ~ \stackrel { \longrightarrow } { n _ { d } } = \{ { \boldsymbol n } _ { d } ^ { ( k ) } \} _ { k = 1 } ^ { K } } } \end{array}
$$

其中：

$$
\Delta ( \alpha ) = { \frac { \prod _ { k = 1 } ^ { K } \Gamma ( \alpha _ { k } ) } { \Gamma ( \sum _ { k = 1 } ^ { K } \alpha _ { k } ) } }
$$

n𝑘）是文档d中主题k出现的次数。

1 ${ \mathfrak { p } } \beta \to { \overline { { \varphi _ { k } } } } \to \ w _ { d , n }$ 表示生成文档中所有单词。$\beta  \overrightarrow { \varphi _ { k } }$ 是 Dirichlet 分布， $\overrightarrow { \varphi _ { k } }  w _ { d , n }$ 是多项分布。用类似于a)的推导方法可以得到

$$
p ( \mathbf { w } \left| \mathbf { z } , \beta \right. = \prod _ { k = 1 } ^ { K } \frac { \Delta ( \overrightarrow { n _ { k } } + \beta ) } { \Delta ( \beta ) } , \overrightarrow { n _ { k } } = \{ n _ { k } ^ { \nu } \} _ { \nu = 1 } ^ { V }
$$

其中： $n _ { k } ^ { ( \nu ) }$ 是主题 $k$ 中单词 $\nu$ 出现的次数。

综合a)和b)，得到联合分布：

$$
p ( \mathbf { w } , \mathbf { z } | \alpha , \beta ) { = } \prod _ { d = 1 } ^ { D } \frac { \Delta ( \overrightarrow { n _ { d } } + \alpha ) } { \Delta ( \alpha ) } { \cdot } \prod _ { k = 1 } ^ { K } \frac { \Delta ( \overrightarrow { n _ { k } } + \beta ) } { \Delta ( \beta ) }
$$

根据联合分布，求解下标 $\boldsymbol { i } = ( d , n )$ ，即第 $d$ 篇文档中第 $n$ 个单词的条件概率。令 $\stackrel { \longrightarrow } { w } = \{ w _ { i } = t , \stackrel { \longrightarrow } { w } _ { - i } \} , \stackrel {  } { z } = \{ z _ { i } = k , \stackrel { \longrightarrow } { z _ { - i } } \} \ ,$

则

$$
\begin{array} { r l } { p ( z _ { i } = k | \vec { z } _ { - , i } , \vec { w } ) = \frac { p ( \vec { w } , \vec { z } _ { - } ) } { p ( \vec { w } , \vec { z } _ { - } ) } } \\ & { = \frac { p ( \vec { w } , \vec { z } _ { - } ) } { p ( \vec { w } , \vec { z } _ { - } | \vec { z } _ { - , i } ) p ( w _ { i } ) } \cdot \frac { p ( \vec { z } ) } { p ( \vec { z } _ { - } ) } } \\ & { \approx \frac { \Delta ( \vec { n } _ { i } + \vec { p } ) } { \Delta ( \vec { n } _ { i } - \vec { n } _ { i } + \vec { p } ) } \cdot \frac { \Delta ( \vec { n } _ { i } + \vec { n } _ { i } ) } { \Delta ( \vec { n } _ { i } - \vec { n } _ { i } + \vec { n } _ { i } ) } } \\ & { = \frac { \vec { n } _ { i } \cdot \vec { \mu _ { - } } + \vec { \beta } _ { i } } { \sum _ { t = } ^ { n } n _ { t _ { i } - i } ^ { ( t _ { i } ) } + \vec { \beta } _ { t } } \cdot \frac { \vec { n } _ { i - t _ { i } } ^ { ( t _ { i } ) } + \vec { \alpha } _ { t } } { ( \sum _ { t = } ^ { n } n _ { t _ { i } } ^ { ( t _ { i } ) } + \vec { \alpha } _ { t } ) - 1 } } \\ & { \propto \frac { \vec { n } _ { i } \cdot \vec { \mu _ { - } } + \vec { \beta } _ { t } } { \sum _ { t = } ^ { n } n _ { t _ { i } - i } ^ { ( t _ { i } ) } + \vec { \beta } _ { t } } ( n _ { i , t _ { i - \infty } } ^ { ( t _ { i } ) } + \alpha _ { t } ) \qquad \mathrm { ( . ~ } } \end{array}
$$

其中： $\vec { n } _ { d }$ 是文档 $d$ 的主题数向量； $\vec { n } _ { k }$ 是主题 $k$ 的单词数向量。因此，可以得到

$$
\mathcal { S } _ { d , k } = \frac { \pmb { n } _ { d } ^ { ( k ) } + \alpha _ { k } } { \sum _ { k = 1 } ^ { K } \pmb { n } _ { d } ^ { ( k ) } + \alpha _ { k } }
$$

$$
\varphi _ { k , t } = \frac { n _ { k } ^ { ( t ) } + \beta _ { t } } { \sum _ { t = 1 } ^ { V } n _ { k } ^ { ( t ) } + \beta _ { t } }
$$

最终，Gibbs采样算法完整训练流程如下：

<html><body><table><tr><td>算法2LDA主题模型Gibbs 采样算法训练过程</td><td></td></tr><tr><td>输入：文档集W，超参α和β，主题数K。</td><td rowspan="3"></td></tr><tr><td></td></tr><tr><td>输出：Θ,Φ。</td></tr></table></body></html>

1．随机为每篇文档的每个单词分配主题，根据这些主题初始化 $n _ { d } ^ { ( k ) }$ 和 $n _ { k } ^ { ( t ) }$ ， $n _ { d }$ 和 $n _ { k }$ （20号

2.Repeat:

3. for所有文档 $d \in [ 1 , D ]$ ：  
4. for文档 $d$ 中的所有单词 $n \in [ 1 , N _ { d } ]$ ：

<html><body><table><tr><td colspan="2">//删除该单词的主题计数</td></tr><tr><td>5.</td><td>nd)-=1;nd-=1;n)-=1;n-=1;</td></tr><tr><td></td><td>//根据式(10)采样得到该单词的新主题</td></tr><tr><td rowspan="2">6.</td><td>k~p(zi|z-i,W)</td></tr><tr><td>//增加该单词的主题计数</td></tr><tr><td>7.</td><td>nk）+=1;nd+=1;n)+=1;nk+=1;</td></tr><tr><td>8.</td><td>end for</td></tr><tr><td>9.</td><td>end for</td></tr><tr><td>10.</td><td>Until收敛或者达到设定的迭代次数</td></tr><tr><td>11.</td><td>根据式(11)和(12)计算得到,</td></tr></table></body></html>

# 2 电信轨迹缺失恢复过程

与基于GPS定位的轨迹相比，更为丰富的电信轨迹来自于电信基站定位数据，定位精度较低。因此，恢复电信轨迹在某个具体时刻缺失的精确位置相对比较困难。为了简化恢复电信轨迹缺失的问题，本文将恢复电信轨迹在缺失时段所经过的某个区域。

# 2.1构造时空单词矩阵

基于电信基站的定位任意用户每天的电信轨迹表示为$T r j = \{ ( t _ { 1 } , T o w e r _ { 1 } ) , ( t _ { 2 } , T o w e r _ { 2 } ) , . . . , ( t _ { n } , T o w e r _ { n } ) \}$ ，其中： $t _ { i }$ 表示用户接听通话、发送/接受短信、流量上网连接通信基站的时刻；Toweri表示用户的移动设备在 $t _ { i }$ 时刻连接的基站位置，即Tow $e r _ { i } = ( l o n _ { i } , l a t _ { i } )$ ；lon 和lat 分别表示该基站的经纬度。

a)时间分段：将一天 $2 4 \mathrm { h }$ 均匀划分成 $T$ 个时段。若 $T = 2 4$ ，则0:00与1:00之间的任意时刻都属于同一时段，以此类推。

b)空间分块：根据运营商在城市各个区域部署的全部基站位置信息，利用K-Means算法[15对基站位置进行聚类，从而将城市划分成 $C$ 块区域。

完成时间分段和空间分块两个步骤后，可以将用户原始电信轨迹转换为 $T r j ^ { ' } = \{ ( T _ { 1 } , R _ { 1 } ) , ( T _ { 2 } , R _ { 2 } ) , . . . , ( T _ { n } , R _ { n } ) \}$ ，从而最终生成时空单词矩阵X，如图3所示。

<html><body><table><tr><td></td><td>1 域 区 时</td><td>区 ‘武</td><td></td><td>区 时</td><td>城 区 时</td><td></td><td>C 城 区 时</td><td></td><td>C 城 区 时</td></tr><tr><td>用户1，dayl</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>用户1，day2</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>用户1，dayM</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>用户2，day1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>：</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>用户2，dayM</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>·</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>用户U，dayM</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

矩阵X的行表示所有用户在所有天生成的电信轨迹，行数等于用户数 $U$ 与天数 $M$ 的乘积；列表示所有时段所有区域构成的时空单词，列数等于时段数 $T$ 与区域数 $C$ 的乘积；值表示用户在指定时空单词上的访问次数，即用户在该时段内访问该区域内的所有电信基站次数。

# 2.2划分训练集和测试集

本文将用户电信轨迹看做是记录用户一天出行的完整轨迹，为了模拟缺失电信轨迹恢复，对每条轨迹都需要随机地挖去一个时段内经过所有区域。如图4所示，阴影部分表示每条电信轨迹挖去时段的所有区域，即需要恢复该时段内的轨迹信息，作为测试集记为TestX；剩余的白色部作为训练集，残缺矩阵记为TrainX。

<html><body><table><tr><td></td><td>区 ‘武</td><td>区 ‘</td><td></td><td>区 时</td><td>区 时</td><td>：</td><td>区 时</td><td>：</td><td>区 时</td></tr><tr><td>用户1，day1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>用户1，day2</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>用户1，dayM</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>用户2，dayl</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>·</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>用户2，dayM</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>用户U， dayM</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# 2.3基于LDA主题模型的电信轨迹恢复算法

基于LDA主题模型的电信轨迹恢复算法主要思路是：将2.2节中得到的残缺矩阵TrainX看做文档集，每条用户电信轨迹看做一篇文档，每个时段区域组合看做一个单词，用户在该时段区域组合内出现的次数作为该单词在对应文档中的词频，从而在该文档集上利用LDA主题模型算法得到文档一主题矩阵 $\Theta$ 和主题一单词矩阵 $\Phi$ 。然后每条用户电信轨迹中被挖去时段内 $C$ 块区域的权重可以通过 $\Theta$ 和 $\Phi$ 对应的行列权重向量相乘得到。最终选取权重最大的 $N$ 块区域作为该缺失时段内可能经过的区域。具体流程如下：

<html><body><table><tr><td>算法3 基于LDA主题模型的电信轨迹恢复方法</td><td>3.2节中得到的TrainX和TestX，主题数K，选取</td></tr><tr><td>输入： 输出：</td><td>权重最大的区域数量N。 每条用户电信轨迹恢复的N块区域。</td></tr><tr><td>1.</td><td>针对文档一单词矩阵TrainX使用LDA主题模型 算法得到文档一主题矩阵和主题-单词矩阵 Φ。</td></tr><tr><td>2.</td><td>利用和对应的行列权重向量相乘计算得到 TestX中每条电信轨迹被挖去时段内C块区域权</td></tr><tr><td>3.</td><td>重。 选取每条电信轨迹被挖去时段内权重最大的N块</td></tr></table></body></html>

# 3 实验结果和分析

为了分析基于LDA主题模型对电信轨迹恢复方法的准确性和时间效率，对此进行了实验。实验硬件环境配置是：3台HuaweiRH2288服务器组成的集群上，每台机器的配置都相同。CPU为IntelXeonCPUE5-2690v2@3.00 GHz，40 核，内存为$1 4 0 { \mathrm { ~ G B } }$ 。实验抽样采集上海市某运营商2016年7月12号到8月12号的10万用户CDR（calldetail records）[16]数据、短信和上网记录构成的电信轨迹。抽样条件是：将每天24个小时均匀划分成24个时段，用户每天至少有10个不同时段存在基站连接记录。

# 3.1评价标准

本文采用准确率(precision)、召回率(recall)和F1-score 来衡量电信轨迹恢复的效果。当 $N$ 越大，准确率会越低，召回率会越高。准确率定义为

$$
P r e c i s i o n @ N = \frac { \left| Y ^ { \prime } \cap Y \right| } { N }
$$

召回率定义为

$$
R e c a l l @ N = { \frac { \left| Y ^ { \prime } \cap Y \right| } { \left| Y \right| } }
$$

F1-score 综合权衡了准确率和召回率，计算公式为

$$
F l - s c o r e @ N = 2 \times \frac { R e c a l l @ N \times P r e c i s i o n @ N } { R e c a l l @ N + P r e c i s i o n @ N }
$$

其中：Y表示当前电信轨迹在被挖去时段真实经过的区域集合；  
$Y ^ { \prime }$ 表示预测的 TopN块区域集合。

# 3.2 不同方法比较

本文将电信轨迹恢复问题转换成矩阵缺失补全问题，本节将 LDA 主题模型算法和常见的传统矩阵补全算法非负矩阵分解(Non-negative Matrix Factorization,NMF)[1和概率矩阵分解(Probabilistic MatrixFactorization,PMF)[18从电信轨迹恢复精度和时间效率两个角度上完成对比分析。实验中设置时段数$T = 2 4$ ，区域数 $C = 3 0 0$ ，主题数 $K \in \{ 1 0 , 3 0 , 5 0 , 1 0 0 , 1 5 0 \}$ 实验结果如表 $2 { \sim } 6$ 和图5所示。

表2主题数 $K { = } 1 0$   

<html><body><table><tr><td colspan="2">N</td><td rowspan="2">@1</td><td rowspan="2">@2</td><td rowspan="2">@3</td><td rowspan="2">@4</td><td rowspan="2">@5</td></tr><tr><td colspan="2">评价指标</td></tr><tr><td rowspan="3">Precision</td><td>NMF</td><td>0.246</td><td>0.215</td><td>0.194</td><td>0.163</td><td>0.145</td></tr><tr><td>PMF</td><td>0.273</td><td>0.256</td><td>0.224</td><td>0.196</td><td>0.178</td></tr><tr><td>LDA</td><td>0.354</td><td>0.297</td><td>0.267</td><td>0.246</td><td>0.231</td></tr><tr><td rowspan="3">Recall</td><td>NMF</td><td>0.262</td><td>0.323</td><td>0.405</td><td>0.478</td><td>0.544</td></tr><tr><td>PMF</td><td>0.281</td><td>0.368</td><td>0.453</td><td>0.516</td><td>0.586</td></tr><tr><td>LDA</td><td>0.318</td><td>0.444</td><td>0.534</td><td>0.603</td><td>0.660</td></tr><tr><td rowspan="3">F1-score</td><td>NMF</td><td>0.254</td><td>0.258</td><td>0.262</td><td>0.243</td><td>0.229</td></tr><tr><td>PMF</td><td>0.277</td><td>0.302</td><td>0.300</td><td>0.284</td><td>0.273</td></tr><tr><td>LDA</td><td>0.335</td><td>0.356</td><td>0.356</td><td>0.350</td><td>0.342</td></tr></table></body></html>

表3主题数 $K { = } 3 0$   

<html><body><table><tr><td colspan="2">N</td><td rowspan="2">@1</td><td rowspan="2">@2</td><td rowspan="2">@3</td><td rowspan="2">@4</td><td rowspan="2">@5</td></tr><tr><td colspan="2">评价指标</td></tr><tr><td rowspan="3">Precision</td><td>NMF</td><td>0.252</td><td>0.223</td><td>0.208</td><td>0.185</td><td>0.157</td></tr><tr><td>PMF</td><td>0.291</td><td>0.274</td><td>0.255</td><td>0.224</td><td>0.207</td></tr><tr><td>LDA</td><td>0.383</td><td>0.319</td><td>0.281</td><td>0.254</td><td>0.236</td></tr><tr><td rowspan="3">Recall</td><td>NMF</td><td>0.271</td><td>0.335</td><td>0.413</td><td>0.493</td><td>0.562</td></tr><tr><td>PMF</td><td>0.293</td><td>0.381</td><td>0.463</td><td>0.529</td><td>0.625</td></tr><tr><td>LDA</td><td>0.355</td><td>0.483</td><td>0.571</td><td>0.632</td><td>0.682</td></tr><tr><td rowspan="3">F1-score</td><td>NMF</td><td>0.261</td><td>0.268</td><td>0.277</td><td>0.269</td><td>0.245</td></tr><tr><td>PMF</td><td>0.292</td><td>0.319</td><td>0.329</td><td>0.315</td><td>0.311</td></tr><tr><td>LDA</td><td>0.369</td><td>0.384</td><td>0.376</td><td>0.363</td><td>0.350</td></tr></table></body></html>

表4主题数 $K = 5 0$ （204号  

<html><body><table><tr><td colspan="2">N</td><td rowspan="2">@1</td><td rowspan="2">@2</td><td rowspan="2">@3</td><td rowspan="2">@4</td><td rowspan="2">@5</td></tr><tr><td colspan="2">评价指标</td></tr><tr><td rowspan="3">Precision</td><td>NMF</td><td>0.317</td><td>0.292</td><td>0.265</td><td>0.249</td><td>0.231</td></tr><tr><td>PMF</td><td>0.348</td><td>0.313</td><td>0.287</td><td>0.267</td><td>0.244</td></tr><tr><td>LDA</td><td>0.414</td><td>0.354</td><td>0.338</td><td>0.294</td><td>0.266</td></tr><tr><td rowspan="3">Recall</td><td>NMF</td><td>0.295</td><td>0.363</td><td>0.465</td><td>0.532</td><td>0.613</td></tr><tr><td>PMF</td><td>0.314</td><td>0.418</td><td>0.492</td><td>0.557</td><td>0.656</td></tr><tr><td>LDA</td><td>0.387</td><td>0.524</td><td>0.593</td><td>0.644</td><td>0.708</td></tr><tr><td rowspan="3">F1-score</td><td>NMF</td><td>0.306</td><td>0.324</td><td>0.338</td><td>0.339</td><td>0.336</td></tr><tr><td>PMF</td><td>0.330</td><td>0.358</td><td>0.363</td><td>0.361</td><td>0.356</td></tr><tr><td>LDA</td><td>0.400</td><td>0.423</td><td>0.430</td><td>0.404</td><td>0.387</td></tr></table></body></html>

表5主题数 $K = 1 0 0$   

<html><body><table><tr><td colspan="2">N</td><td rowspan="2">@1</td><td rowspan="2">@2</td><td rowspan="2">@3</td><td rowspan="2">@4</td><td rowspan="2">@5</td></tr><tr><td colspan="2">评价指标</td></tr><tr><td rowspan="3">Precision</td><td>NMF</td><td>0.357</td><td>0.324</td><td>0.303</td><td>0.296</td><td>0.275</td></tr><tr><td>PMF</td><td>0.379</td><td>0.358</td><td>0.329</td><td>0.317</td><td>0.298</td></tr><tr><td>LDA</td><td>0.513</td><td>0.447</td><td>0.382</td><td>0.316</td><td>0.283</td></tr><tr><td rowspan="3">Recall</td><td>NMF</td><td>0.336</td><td>0.391</td><td>0.477</td><td>0.549</td><td>0.633</td></tr><tr><td>PMF</td><td>0.353</td><td>0.439</td><td>0.518</td><td>0.604</td><td>0.636</td></tr><tr><td>LDA</td><td>0.452</td><td>0.648</td><td>0.753</td><td>0.815</td><td>0.847</td></tr><tr><td rowspan="3">F1-score</td><td>NMF</td><td>0.346</td><td>0.354</td><td>0.371</td><td>0.385</td><td>0.383</td></tr><tr><td>PMF</td><td>0.366</td><td>0.394</td><td>0.402</td><td>0.416</td><td>0.406</td></tr><tr><td>LDA</td><td>0.481</td><td>0.529</td><td>0.507</td><td>0.455</td><td>0.424</td></tr></table></body></html>

表6主题数 $K = 1 5 0$   

<html><body><table><tr><td colspan="2">N</td><td rowspan="2">@1</td><td rowspan="2">@2</td><td rowspan="2">@3</td><td rowspan="2">@4</td><td rowspan="2">@5</td></tr><tr><td colspan="2">评价指标</td></tr><tr><td rowspan="3">Precision</td><td>NMF</td><td>0.374</td><td>0.338</td><td>0.315</td><td>0.303</td><td>0.283</td></tr><tr><td>PMF</td><td>0.412</td><td>0.376</td><td>0.355</td><td>0.346</td><td>0.327</td></tr><tr><td>LDA</td><td>0.493</td><td>0.426</td><td>0.366</td><td>0.304</td><td>0.276</td></tr><tr><td rowspan="3">Recall</td><td>NMF</td><td>0.347</td><td>0.413</td><td>0.498</td><td>0.564</td><td>0.657</td></tr><tr><td>PMF</td><td>0.368</td><td>0.448</td><td>0.532</td><td>0.588</td><td>0.608</td></tr><tr><td>LDA</td><td>0.431</td><td>0.616</td><td>0.728</td><td>0.783</td><td>0.833</td></tr><tr><td rowspan="3">F1-score</td><td>NMF</td><td>0.360</td><td>0.372</td><td>0.386</td><td>0.394</td><td>0.396</td></tr><tr><td>PMF</td><td>0.389</td><td>0.409</td><td>0.426</td><td>0.436</td><td>0.425</td></tr><tr><td>LDA</td><td>0.460</td><td>0.504</td><td>0.487</td><td>0.438</td><td>0.415</td></tr></table></body></html>

![](images/180f0d692a254b9878e94cf80794b41925c35e23fdc6ba7f6e45eef042dd6e4b.jpg)  
图5各种算法运行时间对比

从表 $2 { \sim } 6$ 可以看出，随着主题数 $K$ 增加，NMF和PMF在precision、recall和F1-score 都会逐渐增加，PMF 轨迹恢复效果略优于NMF；随着主题数 $K$ 增加，LDA在 precision、recall和 F1-score 是先增加后有略微减小，当 $K = 1 0 0$ 时，precision、recall和F1-score 达到最高，且明显高于NMF和PMF。从图5中可以看出，当主题数 $K$ 较小时，LDA运行时间会略高于NMF和PMF；随着主题数 $K$ 增加，LDA运行时间逐渐少于NMF和PMF。主要原因是：NMF和PMF的时间复杂度是关于主题数$K$ 的多项式级别，而LDA的时间复杂度是关于主题数 $K$ 的线性级别。因此，可以得出结论：基于LDA主题模型的用户电信轨迹恢复精度和时间效率都优于NMF和PMF两种算法，充分表明将用户电信轨迹类比成文档可以有效地描述用户每天出行的行为模式。因此，相比传统矩阵缺失补全算法，使用LDA主题模型恢复时空矩阵中的缺失部分更具优势。

从上述实验结果中可以看出，选择LDA主题模型且设置主题数 $K = 1 0 0$ 在电信轨迹恢复的精度和时间效率上会取得最佳效果。在此基础上，根据实验结果可以计算比较一周内周一到周日和一天内各个不同时段的所有电信轨迹的平均恢复精度。为简化对比结果，只选取precision $@ 1$ 、recall $@ 1$ 、F1-score@1作为评价标准。实验结果分别如图6和7所示。

![](images/8ec5cd33d435836b27e7142348ba385feba476b837eefc493c3f7c2c40a456e4.jpg)  
图6一周内各天电信轨迹平均恢复精度对比

![](images/feda2455f8a57849df0f64b925243efb787977956f0b84d74f2ca7d64fbb25bd.jpg)  
图7一天内各个时段电信轨迹平均恢复精度对比

从图6中可以看出，电信轨迹恢复的精度在周一到周五高于周六和周日，周二到周四较稳定。实验设置时段数 $T = 2 4$ ，则每个时段长度是1h。从图7中可以看出，电信轨迹恢复的精度在凌晨和夜间高于白天，上午9点电信轨迹恢复精度最低。产生上述现象的主要原因是：用户工作日的出行轨迹相比较周末更有规律；用户在凌晨和夜晚大多数处于休息状态，在白天出行活动范围更大。因此，图6和7进一步验证了Song等人[19]提出的人类的行为有其潜在的规律性。

# 4 结束语

本文提出了一种基于LDA主题模型恢复用户电信轨迹的方法。在此过程中介绍了LDA主题模型原理和Gibbs采样推理算法；然后本文详细地阐述了利用LDA主题模型解决电信轨迹恢复问题方法和步骤；最终本文通过实验对比了NMF、PMF、LDA主题模型三种不同算法的恢复精度和时间效率，综合得出结论LDA主题模型可以有效地解决用户电信轨迹恢复问题。

本文中研究的不足之处是仅仅能恢复电信轨迹在某个时段属于某个区域，并不能恢复电信轨迹某个时刻的具体位置，所以电信轨迹恢复还需要进一步研究。在未来发展中，可以考虑把用户个人兴趣爱好、路况、天气等上下文信息加入到模型中，进一步提高恢复的精度。

# 参考文献：

[1]Zhang Zelun，Stefan P.A new post correction algorithm (PoCoA） for improved transportation mode recognition [C]//Proc of IEEE International Conference on Systems,Man,and Cybernetics.2013:1512-1518.   
[2]Sasank R,Mun MY,Burke J,et al. Using mobile phones to determine transportation modes [J].ACM Trans on Sensor Networks,2010,6(2):13.   
[3]Lou Yin,Zhang Chengyang,Zheng Yu,et al.Map-matching for lowsampling-rate GPS trajectories [C]//Proc of the 17th ACM SIGSPATIAL International Conference on Advances in Geographic Information systems. 2009:352-361.   
[4]Bernstein D,Kornhauser A.An introduction to map matching for personal navigation assistants [J].Geometric Distributions,1998,122 (7):1082- 1083.   
[5]Zheng Kai,Zheng Yu,Xie Xing,et al.Reducing uncertainty of lowsampling-rate trajectories [C]// Proc of the 28th IEEE International Conference on Data Engineering.2012:1144-1155.   
[6]罗宇，杜利民．基于隐马尔可夫模型局部最优状态路径的数据重建算 法[J].电子与信息学报,2004,26(5):722-726.(Luo Yu,DuLimin.HMM local optimal state path-based data imputation [J].Journal of Electronics & Information Technology,2004,26(5): 722-726.)   
[7]苏腾荣，吴及，王作英，等．利用空间相关性的改进HMM模型[J].计 算机工程与设计,2010,31(5):1023-1026.(Su Tengrong,Wu Ji,Wang Zuoying，et al. Improved HMM model using spatial correlation [J]. Computer Engineering and Design,2010,31(5):1023-1026.)   
[8]徐超，季民河．个人出行轨迹中轨道交通段GPS 信号缺失修补算法 [J].交通信息与安全,2012,30(4):6-10.(Xu Chao,JiMinhe.An algorithm for repairing missing trajectories ofGPS data in personal light-rail travel [J]. Computer and Communications,2012,30(4): 6-10.)   
[9]Hofmann-Wellenhof B,Lichtenegger H,Collins J.Global positioning system: theory and practice [M].[S.1.]: Springer Science& Business Media, 2012.   
[10] BleiD M,NgAY,Jordan MI.Latent dirichlet allocation [J].Journal of machine Learning research,2003,3(1): 993-1022.   
[11] NirF,Dan G,Moises G.Bayesian network classfiers [J].Machine Learning, 1997,29 (2-3):131-163.   
[12]姚全珠，宋志理，彭程．基于LDA 模型的文本分类研究[J].计算机 工程与应用，201,47(13):150-153.(Yao Quanzhu,Song Zhili,Peng Cheng.Research on text categorization based on LDA [J].Computer Engineering and Applications,201,47 (13): 150-153.)   
[13] Ludden TM,Mu Song.Markov chain Monte Carlo and gibbs sampling [Z]. 2004.   
[14] George EI,McCulloch R E.Variable selection via Gibbs sampling [J]. Journal of the American Statistical Association,1993,88 (423):881-889.   
[15] Burkardt J. K-means clustering [C]// Advanced Research Computing, Interdisciplinary Center for Applied Mathematics.2009.   
[16]Perkins IF C.System and method for processing call detail records: U. S. Patent 6,658,099 [P].2003-12-2.   
[17] Farial S,BerryM W,PaulPV,et al. Document clustering using nonnegative matrix factorization [J].Information Processing & Management,2006,42 (2):373-386.   
[18]Andriy M,Ruslan S.Probabilistic matrix factorization [C]//Advances in Neural Information Processing Systems.2008:1257-1264.   
[19] Song Chaoming,Qu Zehui,Blumm N,Albert-Laszló Barabasi.Limits of predictability in human mobility[J]. Science,2010,327(5968):1018-1021.