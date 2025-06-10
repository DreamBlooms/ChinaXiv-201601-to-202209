# 一个有效的动态网络节点影响力模型

韩忠明ab，毛锐a，郑晨烨a，赵振东a，段大高a(北京工商大学 a.计算机与信息工程学院 计算机系;b.食品安全大数据技术北京市重点实验室，北京 100048)

摘要：网络节点影响力度量对社会网络研究具有重要的价值，静态网络的影响力度量是目前研究的主要问题。实质上，社会网络属于动态网络。静态网络节点影响力度量模型虽然可以对动态网络不同时间点上的快照进行度量，但这种机制很难刻画动态网络节点影响力的变化过程。将动态网络建模为不同时间点网络的叠加快照，然后构建了动态网络边权重衰减和节点影响力衰减机制，基于衰减机制提出了动态网络节点影响力模型，模型可以应用于加权或无权动态网络节点影响力度量。为了客观衡量本文模型的性能，在一个模拟网络和三个真实网络进行了不同实验。实验结果表明本文模型不仅可以较好的刻画动态网络节点影响力的变化过程，还可以准确度量动态网络节点影响力。

关键词：动态网络；节点影响力；权重衰减 中图分类号：TP393 doi:10.3969/j.issn.1001-3695.2017.11.0847

# Effective model for measuring node influence on temporal network

Han Zhongminga,b, Mao Ruia, Zheng Chenyea, Zhao Zhendonga, Duan Dagaoa (a.Dept.ofComputerScience & Information Engineering,b.Beijing KeyLaboratoryof Big Data Technology forFood Safety, Beijing Technology&Business University,Beijing l0oo48,China)

Abstract: Measuring node influenceonnetworkisanimportant questionofonlinesocialnetworkanalysis.Currently,themain relatedresearch focus oninfluenceofstatic networks.Essentially,socialnetworksaredynamic networks.Althoughmodels for measuringnodeinfluenceonstatic networks canbeused to measure node influence indifferentsnapshotsofatemporaletwork, it is difcult to describethedynamic process ofnode influence.In this paper,a dynamic network is viewed as aseriesof snapshots at different time points.The mechanismsofedge weightatenuationand node influence attenuationare constructed. Basedon the atenuation mechanism,this paper propose amodel formeasuring node influence on dynamic networks,which can be applied toweighted or unweighted dynamic networks.In order to evaluate the performance of proposed model, comprehensive experiments areconductedonasimulated network andthreereal networks.The experimental results show that proposed modelcannotonlydescribethe influence dynamic processfor diferent nodes,but also efectively measure the node influence in dynamic networks.

Key words: dynamic network; node influence;weight attenuation

# 0 引言

个体与个体之间通过各种关系连接形成网络[1，现实中存在着大量网络，典型的如社交网络，微博[2]、Facebook[3,4]、twitter[5]、Digg[6]等、邮件网络（enronEmaildataset[7]）、论文网络(DBLP[8][3])、生物网络[9,10]等。网络节点影响力度量对理解网络中信息、疾病和谣言等传播和控制、新产品的市场推广营销等应用有着非常实用的价值[1]。

近年来，动态网络受到高度关注，对其研究也更加深入[12],大部分网络具有动态特性。随着时间的推移，新的节点和新的边加入到网络当中，网络的规模不断扩大，节点的影响力也必然随之发生改变。如图1所示，若使用静态网络节点影响力度量计算，节点1和4的影响力相等。但观察网络结构的变化，在t与t时刻，节点1与4影响力相同，在t时刻，节点4的影响力相较于节点1要高出很多，这表明静态网络影响力难以表达节点影响力的变化。

为了能有效地度量动态网络的节点影响力，更好发现网络演变过程中不同时刻下的关键节点，提出了一个动态网络节点影响力模型。模型可以对动态网络节点影响力的变化过程进行刻画，并且准确度量动态网络节点影响力。

# 1 相关工作

网络节点影响力度量是网络科学中的重要部分，也是数据挖掘领域的研究热点。为了度量网络节点影响力，研究者们提出一系列方法。直观分析，度中心性[13]可以在一定程度上表示节点的影响力大小，但是度中心性并不能充分利用到邻居节点。如果A、B节点的度值相同，而A、B节点邻居节点的影响力不同，A、B节点的影响力肯定也是不同的。研究者进一步考虑全局属性来度量节点影响力，如：介数中心性[14][15]、紧密中心性[16]等。

![](images/7631ec5d377020c4b5314986f730238e67c2649f23293cfa59f5578c2042eb01.jpg)  
图1动态网络与静态网络对比

Kitsak等人[7则认为介数高或度值大的节点并不绝对是影响力大的节点。考虑到节点与整个网络的关系，利用K核分解从边缘到核心对节点进行分层，来划分影响力大小，认为核数大的节点影响力大。但由于网络中会形成紧密的小团体，核数大的节点也未必是网络核心节点。研究人员也有利用Pagerank[18,19]、HITS[20]、LeaderRank[21]等随机游走算法对节点进行打分，并对结果进行排序，寻找影响力最大的节点。

韩忠明等人[1对影响力度量方法进行了改进，认为网络核心区域的三角结构较多，节点的影响力是由邻居节点共同决定的。根据K核分解和局部中心性的理念提出了基于三角结构的节点影响力度量指标(local triangle centrality,LTC)。

以上方法均针对静态网络，然而静态网络忽略掉了时间属性。真实的网络都有变化过程，所以动态网络的研究是网络科学的研究方向，并且很多研究者已经开始关注网络的动态性，并已做了相应的研究[2223]。

Aggarwal等人[24]认为流行病学网络、邮件网络、聊天网络等更适合建立动态模型。从动态的角度对分析节点影响力最大化问题，提出了一种时间敏感算法，在时间点t处找到一个种子集合，使得在时间点t+h处影响力最大化。在Aggarwal等人的研究基础上，Chen等人[25进一步进行深度探索，提出影响节点跟踪问题。影响节点跟踪问题旨在动态跟踪一组有影响力的节点，使得影响力的传播在任何时刻下最大化。Yi等人[26]则认为为大多数测量都基于网络拓扑结构的统计，提出一种基于节点信任值的度量社会网络节点动态影响的新方案，实现动态网络节点影响力最大化。影响力最大化的问题旨在寻找一组节点使得传播最大化，但不能度量全部节点的影响力大小。

大部分动态网络影响力的度量均以PageRank 为基础进行相应修改。文献[27]基于PageRank算法，引入了时间信息，提出了TimedPagerank 算法。TimedPR 算法以节点之间边出现的时间为依据，赋予新出现的节点以更高的权重。闫光辉[28]在此基础上进一步引入了趋势因子，利用历史话题链接计算得到趋势因子，用于表示影响力的变化趋势。但这种方法并不能够给较早期的节点相应的权重，并且没有对两个节点间出现重边的情况进行算法设计。

在TimedPagerank 的基础上，Bundit Manaskasemsak [29]等提出了一种TWPR算法。不仅考虑了时间的因素，还考虑了事件和趋势因素。鞠时光[30]等提出WTPR算法，引入时间连接分析，使用爬虫抓起页面时http协议反馈回来的修改时间作为页面和链接的时间，并综合考虑页面的出入链接个数和时间来计算页面的权重值。这两种方法均只针对网页页面进行打分评价。广义上的动态网络中，节点没有修改时间或者事件因素，限制了本算法的应用场景，仅限于网页影响力，在其他类型网络中算法便不可取。

近年来，在动态网络节点影响力度方面的研究相对较少，现有的方法也主要是针对网络动态变化过程中的影响力最大化研究或者基于Pagerank添加特定网络的外来属性作为指标。本文针对这一方向开展研究，有助于深入理解动态网络的演化，提出一种可应用在不同动态网络上的影响力模型。

# 2 动态网络节点影响力模型

对动态网络，一般建模为不同时间上的独立快照，用$\mathbf { g } _ { \mathrm { t } } ( \nu ^ { t } , e ^ { t } , w ^ { t } )$ 表示一个时间段独立网络的快照， $\nu ^ { t }$ 为 $t$ 时间段内存在的节点集合， $e ^ { \prime }$ 为 $t$ 时间段内存在的边集合，表示为$e ^ { t } = \{ e _ { u , \nu } ^ { t } | u , \nu \in \nu ^ { t } \}$ ， $\boldsymbol { w } ^ { t }$ 为 $t$ 时间段边权重集合，$\boldsymbol { w } ^ { t } = \{ w _ { u , \nu } ^ { t } | \boldsymbol { u } , \nu \in \nu ^ { t } \}$ 。这种独立网络快照表示动态网络方法简单，但难以表现不同时间段之间的联系，为进一步完善网络结构定义，本文提出叠加网络快照，定义如式(1)所示。

$$
G _ { t } ( V ^ { t } , E ^ { t } , W ^ { t } ) { = } \mathbf { g } _ { 0 } \bigcup \mathbf { g } _ { 1 } \bigcup \mathbf { g } _ { 2 } \bigcup { \ldots } \bigcup \mathbf { g } _ { t }
$$

![](images/c3eef35fba7afecdfcdfa091f758ac474e976e1308d622114cfc6fb86de07711.jpg)  
图2叠加网络快照

其中 $\boldsymbol { V } ^ { t }$ 为0时间段到 $t$ 时间段内存在的节点集合， $E ^ { t }$ 为0到 $t$ 时间段内存在的边集合， $E ^ { t } = \{ E _ { u , \nu } ^ { t } | u , \nu \in V ^ { t } \}$ ， $\boldsymbol { W } ^ { t }$ 为0到 $t$ 时间段边权重集合，表示为 $\boldsymbol { W } ^ { t } = \{ \boldsymbol { W } _ { u , \nu } ^ { t } | \boldsymbol { u } , \nu \in \boldsymbol { V } ^ { t } \}$ 。叠加网络快照可以应用在有权网络和无权网络上，无权网络新加入的边权重设置为1。

$G _ { \mathrm { t } }$ 为0到 $t$ 时间段的网络结构的叠加，可以把不同时间段的网络结构建立其联系。如图2所示， $G _ { \imath }$ 和 $g _ { \mathfrak { l } }$ 的网络结构相同，在 $t = 1$ 时刻， $G _ { \imath }$ 与 $g _ { 1 }$ 产生差异， $g _ { 1 }$ 中节点1与节点2之间没有边，但 $G _ { \imath }$ 中节点1与节点2之间有边，以此类推。

单纯叠加网络快照并不能完全刻画随时间衰减的过程，所以本文基于叠加网络快照提出动态网络节点影响力模型来刻画动态网络变化过程。

当两个节点间建立联系，形成一条边后，如果两个节点在一段时间没有再次发生联系，则这两个节点之间的边的强度不应该等同于初始时刻，应随着时间变化减弱，体现为边权重下降。由于这两个节点之间仍存在联系，在之后的网络变化过程中，如果这两个节点再次发生联系，边的强度得到提升，体现为边权重上升。本文使用边权重衰减机制来体现节点间关系强度变化过程。式(2)给出边权重衰减机制的定义。

$$
\begin{array} { l } { { W _ { u , \nu } ^ { t } = E d g e W e i g t h D e c l i n e ( \Delta t , w _ { u , \nu } ^ { t } } } \\ { { \displaystyle \left\{ \begin{array} { c c } { { w _ { u , \nu } ^ { t } } } & { { \Delta t = 0 } } \\ { { w _ { u , \nu } ^ { t } + \displaystyle \frac { 2 ^ { * } W _ { u , \nu } ^ { t } } { 1 + \exp ( \Delta t ) } } } & { { \Delta t > 0 } } \end{array} \right. } } \end{array}
$$

$\Delta t$ 为边 $( u , \nu )$ 从初始时刻到当前时刻的时间长，即边 $( u , \nu )$ 的存在时间。 $\Delta t = 0$ 时，即 $t$ 时刻为边 $( u , \nu )$ 的初始时刻， $W _ { e _ { t } }$ 与$\boldsymbol { w } _ { \boldsymbol { e } _ { t } }$ 相等。 $\Delta t { > } 0$ 时， $W _ { e _ { t } }$ 为 $t$ 时刻边 $( u , \nu )$ 的 ${ \boldsymbol w } _ { \boldsymbol e _ { t } }$ 与经过衰减的$W _ { e _ { t - 1 } }$ 的和。

当一个节点在某时间段的独立网络快照出现，在这个时间段称之为相对活跃状态。如后续若干时间段的独立网络快照中未出现，则进入衰减状态，节点的影响力不再如活跃状态时高，对此提出节点影响力衰减机制。式(3)给出节点影响力衰减机制的定义。

$$
\begin{array} { r } { I n f _ { u } ^ { t } = I n f l u e n c e D e c l i n e ( \Delta t , u ) = \phantom { x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x } } \\ { P a g e r a n k ( u ) \phantom { x x x x x x x x x x x x x x x x x x x x x x x x x x x x x x } } & { \Delta t = 0 } \\ { \left\{ \beta \ast P a g e r a n k ( u ) + ( 1 - \beta ) I n f _ { u } ^ { t - 1 } \ast \exp { ( - \Delta t ) } \right. \left. \Delta t > 0 \right. } \end{array}
$$

$I n f _ { u } ^ { t }$ 为 $t$ 时刻的节点 $u$ 的影响力， $\Delta t$ 为节点 $u$ 初始时刻到当前时刻的时间长度，即节点 $u$ 的存在时间。 $\Delta t = 0$ 时，即 $t$ 时刻为节点 $u$ 的初始时刻， $I n f _ { u } ^ { t }$ 为 $t$ 时刻的 PageRank值。 $\Delta t { > } 0$ 时， $I n f _ { u } ^ { t }$ 为 $t$ 时刻的PageRank 值与经过衰减的 $I n f _ { u } ^ { t - 1 }$ 按照一定比例求和。 $\beta$ 用来调节比例， $0 < \beta < 1$ ，当 $\beta$ 较高的时候，节点影响力随时间的变化大；当 $\beta$ 较低的时候，节点影响力随时间的变化较小。

下面给出了动态网络节点影响力的求解算法，算法输入为全部时刻的独立网络快照集合。遍历快照集合，将 $g$ 叠加得到每个时刻的叠加网络快照 $G$ 。每次更新 $G$ 后，利用式(2)更新获得新的边权重。得到更新后的权重后使用式(3)更新每个节点的影响力。遍历结束便可得到 $t$ 时刻节点的影响力。

input: $\{ \mathbf { g } _ { 0 } , \mathbf { g } _ { 1 } , \mathbf { g } _ { 2 } . . . \mathbf { g } _ { t } \}$ （204号   
output: The influence of nodes at $t$ （20   
input: $\{ \mathbf { g } _ { 0 } , \mathbf { g } _ { 1 } , \mathbf { g } _ { 2 } . . . \mathbf { g } _ { t } \}$ （20   
$G = \emptyset$   
for $g$ in $\{ \mathbf { g } _ { 0 } , \mathbf { g } _ { 1 } , \mathbf { g } _ { 2 } . . . \mathbf { g } _ { t } \}$ do:   
$G = G \cup g$   
update edges’weight of $G$ according to formula (1)   
update nodes’influence of $G$ according to formula (2)   
end for   
output: the influence of nodes at $t$ （204号

# 3 实验

为了客观衡量本文模型的效果，本文分别使用模拟和真实网络数据集进行实验，验证动态网络节点影响力模型的效果。所有实验在主频为 $3 . 3 ~ \mathrm { G H z }$ CPU和8GB内存的PC机上完成。采用Python实现了本文模型以及对比性方法。

# 3.1实验数据与实验设计

实验使用一个模拟网络和三个不同规模的真实网络，网络基本属性如表1所示。在模拟网络上，将结果与人工交叉标注的结果计算肯德尔系数。针对三个真实网络进行了不同角度的影响力效果分析。针对论文引用网络与Twitter网络进行了定量实验，使用历史数据对累计引用次数或累计交互次数进行预测。由于演员合作网络受外界因素影响较大，选取问卷形式对排名结果进行评估，并分析有代表性的演员。

表1网络基本属性  

<html><body><table><tr><td>网络</td><td>来源</td><td>节点</td><td>边</td><td>时间跨度</td><td>划分方式</td></tr><tr><td>模拟网络</td><td>人工生成</td><td>18</td><td>67</td><td>4个时间段</td><td></td></tr><tr><td>电影演员合作网络</td><td>中国票房网</td><td>14 421</td><td>363674</td><td>2000—2016年，共</td><td>按年划分</td></tr><tr><td rowspan="2">论文引用网络</td><td>Aminer Citation-</td><td></td><td></td><td>17年 1954—2009年，共</td><td></td></tr><tr><td>network V2</td><td>1397 2403 021 489</td><td></td><td>56年</td><td>按年划分</td></tr><tr><td rowspan="2">Twitter 网络</td><td>Stanford Network</td><td></td><td></td><td>2012年7月1日至</td><td></td></tr><tr><td>Analysis Project</td><td>304 691</td><td>563 069</td><td>2012年7月8日</td><td>按小时划分</td></tr></table></body></html>

# 3.2模拟网络

对模拟网络建立动态网络节点影响力模型，划分为4个时间段。选取不同的 $\beta$ 值进行实验，得到不同时间段的排名结果。然后使用静态PageRank的方法计算不同时间段的排名。选取动态网络与静态网络不同时刻前5位节点排名顺序，分别与人工交叉标注结果的排名顺序计算肯德尔系数。人工标准采用多人重复标注，标注内容交叉，然后投票选择结果。实验结果如图3所示，横轴为不同的 $\beta$ 取值，纵轴为实验结果与人工交叉标注结果的肯德尔系数。当 $\beta$ 值取0.8和0.9的时候，实验排名结果最好，动态网络节点影响力在4个时间段的排名结果与人工交叉标注结果的肯德尔系数都为1。相比之下，静态PageRank在4个时间段内的排名结果与人工交叉标注的肯德尔系数分别为1、0.4、0和1，表明静态PageRank的结果与人工交叉标注的结果相差较大。由此可见，动态网络节点影响力模型可以有效的刻画出影响力随时间变化的过程。

# 3.3电影演员合作网络

对电影演员合作网络建立动态网络节点影响力模型，划分为17个时间段，

从定量角度进行验证。按照不同的快照划分方式构建动态网络节点影响力模型。将结果和静态影像力模型计算所得影响力结果，基于线性回归模型分别对2016年电影进行预测，结果如表2所示。按照年份划分快照所计算的影响力的预测结果最佳，对数化平均绝对误差与对数化均方误差分别为4.05和8.47，明显好于其他快照划分方式所得影响力。时间划分粒度过小，节点的影响力衰减的过于迅速，导致预测不准确。时间划分粒度过大，网络快照更新缓慢，节点衰减过慢，导致预测不准确。根据真实数据计算，平均每位演员每年出演1.19部电影，所以按照年份划分时间段较为合理。静态影响力的预测结果的对数化平均绝对误差和对数化均方误差4.17与8.72。对于R-square指标，动态影响力的预测结果（按1年划分时间快照）为静态影响力的10倍。根据这几个指标可以看出动态网络节点影响力结果对于演员预测有更好的作用。

表2电影票房预测结果   

<html><body><table><tr><td rowspan="2">对比指标</td><td>动态影响力</td><td>动态影响力</td><td>动态影响力</td><td>动态影响力</td><td>动态影响力</td><td rowspan="2">静态影响力</td></tr><tr><td>（按2年划分快照）</td><td>(按1年划分快照）</td><td>(按6个月划分快照)</td><td>（按3个月划分快照）</td><td>(按1个月划分快照)</td></tr><tr><td>对数化平均绝对误差</td><td>4.11</td><td>4.05</td><td>4.15</td><td>4.16</td><td>4.17</td><td>4.17</td></tr><tr><td>对数化均方误差</td><td>8.60</td><td>8.47</td><td>8.55</td><td>8.67</td><td>8.71</td><td>8.72</td></tr><tr><td>R-square</td><td>0.27</td><td>0.47</td><td>0.35</td><td>0.19</td><td>0.05</td><td>0.04</td></tr></table></body></html>

![](images/b0be357c43e55b4ed5fad2c2936038781ad5eca67a4245a3a1a31fc796d5f433.jpg)  
图3动态网络在不同 $\beta$ 值下的肯德尔系数和静态网络的肯德尔系数

![](images/54e9ef7704f725c7c958daebad1910527e1debeb4214a19ed8c736d71bf964f1.jpg)  
图4受访者每年观影次数

由于时间跨度较小，并且为了使时间的影响更充分，选取2014、2015、2016这三年的结果进行评估。本文对这三年的前10名的影视演员排名结果进行调查问卷，随机选择普通观众和影视从业人员进行调查，与观影人心目中的结果进行对比，来说明排名的可靠性。分为5个级别：非常符合、比较符合、一般、比较不符合、完全不符合。受访者的观影情况如图4，问卷

结果如图5所示。

横坐标为5种符合程度，纵坐标为5种符合程度调查结果的百分比。通过对这三年的结果进行分析。2014年的不符合度最低，为 $5 . 8 8 \%$ ，2016年的不符合度最高，为 $1 5 . 6 8 \%$ 。总体来看，排名很符合观众心中的评价顺序。说明本排名与真是排名符合度较高，进一步说明本模型的有效性。

为了更好地体现动态网络节点影响力，本文选取了6名电影演员，分别观察静态影响力排名和动态影响力排名走势区别。如图6所示，横轴为年份，纵轴为当年演员影响力排名取对数所得数值，排名越高值越小。静态影响力会让演员每个时间段的变化变得很小，当一名电影演员参演年份越长，排名变化程度越小。但是演员都会有低谷时期和巅峰时期，静态影像力并不能很好的体现出来。如A、B、C、D四名演员，都有未参演电影或参演电影水平不高的时间段，如演员C和演员D，演员C 在2010年之后参演的电影中表演水平下降严重，演员D在

2013年后转型担任导演，作为演员的影响力明显下降，由于静态影响力没有刻画变化过程，所以不能很好体现影响力的变化。另一类是如演员E、和演员F，这两位演员是网剧热门演员转型参演电影的演员，静态影响力的排名会使其排名相对较差，排名要低于名气较高但现阶段不活跃的演员，但是动态影响力能够让他们在短时间达到较高状态，能较好的体现他们应有的影响力水平。

50.00% 45.00% 40.00%  
45.00m 35.00m 1 40.00% 30.00% 川 25.00% 35.00% 山25.00%  
25.00% 20.00%20.00%  
20.00% 15.00%  
15.0 1500m 10.00%  
5.00% 5.00% 5.00%  
0.00% 0.00% 0.00%非常符合 比较符合 一般 比较不符合完全不符合 非常符合 比较符合 一般 比较不符合完全不符合 非常符合 比较符合 一般比较不符合完全不符合(a)2014年 (b)2015年 (c)2016年

![](images/e8769603e36f8e36be2180f1c9082c3f7699c0e06dcd9ce958604ceb9fcc69e0.jpg)  
图52014、2015、2016年问卷调查结果  
图6六名演员动态网络与静态网络的影响力

# 3.4 论文引用网络

对论文引用网络建立动态网络节点影响力模型，按照年份划分为56个时间段，将 $\beta$ 设为0.2，加强影响力累计的效果。

本文选取1970年排名前30名的论文，分析这30 篇论文从首次被引用的年份到2009 年的影响力走势。将论文 $a$ 的 $x$ 年的排名记为 $r a n k _ { a }$ ， $x$ 年的论文总数记为 $s u m _ { { } _ { x } }$ ，按照式(4)进行处理，结果如图7所示。Rank值为0到1之间，Rank值越高表明论文排名越靠前，式(4)给出Rank 值的定义。

$$
R a n k = 1 - \ln ( r a n k _ { a } ) / \ln ( s u m _ { x } )
$$

论文的影响力在其早期处于波动上升，一个新理念的出现并不能很快的被其他研究人员所充分的认同或使用。随着时间，中期平稳上升至稳定，影响力达到顶峰。后期会有一个较快下降的趋势，论文的研究方向或论文中可进一步深入研究的内容已经饱和，影响力下降。

Barabasi在文献[31]对学术论文的被引进行了深入研究，如文献[31]Fig.1C所示，论文的被引概率与时间的关系，当一篇论文第一次被引用开始，论文的引用概率不断上升，达到峰值，随之下降到很低的位置。本文论文影响力趋势和Barabasi揭示的引用概率的趋势一致，而被引概率是论文影响力的体现，这验证了本文动态网络节点影力模型的可靠性。

从定量角度进行分析，选取2009年前十名的论文，将从论文首次被引用的年份到2008年的影响力数值进行归一化处理，结合论文出现的时间长度，使用局部加权线性回归对次年累计引用量拟合曲面，以ID272067的论文为例，拟合的曲面如图8所示。x轴为边存在的时间，y轴为归一化后的影响力，z轴为次年累计引用次数。

![](images/9c3ee7a6a5dba22f05fc301cf361da004d1b19b2e0b22165df0ee88ddb72d3a4.jpg)  
图71970年排名前30名论文影响力走势

使用拟合得到的曲面对2009年的累计引用量进行预测，结果如表3所示。可以明显看出，最高误差 $1 8 . 9 1 \%$ ，最低误差$1 . 7 6 \%$ ，平均误差为 $6 . 5 9 \%$ ，预测结果说明动态网络节点影响力模型能够体现论文被引的特征，进而说明本文模型能够有效刻画论文的影响力变化。

表32009年排名前十名论文预测结果  

<html><body><table><tr><td></td><td>predict</td><td>real</td><td>error</td></tr><tr><td>277067</td><td>3928.2</td><td>4022</td><td>2.33%</td></tr><tr><td>325631</td><td>1846.0</td><td>1950</td><td>5.33%</td></tr><tr><td>307821</td><td>907.7</td><td>892</td><td>1.76%</td></tr><tr><td>311269</td><td>2091.4</td><td>2042</td><td>2.42%</td></tr><tr><td>364965</td><td>2829.5</td><td>2947</td><td>3.99%</td></tr><tr><td>845435</td><td>1542.2</td><td>1636</td><td>5.73%</td></tr><tr><td>877040</td><td>1469.3</td><td>1812</td><td>18.91%</td></tr><tr><td>977736</td><td>767.8</td><td>912</td><td>15.81%</td></tr><tr><td>1298356</td><td>2144.3</td><td>2104</td><td>1.92%</td></tr><tr><td>1349660</td><td>1554.3</td><td>1684</td><td>7.70%</td></tr></table></body></html>

![](images/7c34378d8542beada3e4b0090213d984b60ae09137eed0d86bf68b7b499cf2e8.jpg)  
图8272067号论文拟合的曲面

# 3.5Twitter 网络

对Twitter网络建立动态网络影响力模型，分别按照12小时、6小时、3小时对网络进行划分。选取10名用户，将从开始时刻到倒数第二时刻的影响力数值进行归一化处理，与节点出现的时间长度结合，使用局部加权线性回归对次年累计交互量拟合曲面。使用拟合得到的曲面对最后时间段的累计交互次数进行预测，结果如表5所示。按照6小时划分的效果最好，最高误差 $2 . 7 9 7 4 \%$ ，最低误差 $0 . 0 0 1 9 \%$ ，平均误差为 $0 . 5 3 3 9 \%$ ，有效的验证了动态网络节点影响力模型的有效性。按照12小时划分会出现影响力变化不明显，节点影响力的衰减效果不明显。按照3小时划分会出现影响力变化过快，节点影响力的衰减过于迅速。这两种划分方式均导致预测效果明显下降。通过对数据集的计算，每六个小时，用户平均每人进行1.34次操作。因此，按照6小时换份时间快照较为合理。

表510名高影响力Twitter用户预测结果  

<html><body><table><tr><td>id</td><td>按12小时划分快照 按6小时划分快照</td><td>按3小时划分快照</td></tr><tr><td>4741</td><td>1.625%</td><td>0.0035% 7.421%</td></tr><tr><td>88</td><td>1.079%</td><td>0.0383% 4.127%</td></tr><tr><td>677</td><td>3.402%</td><td>0.2576% 6.281%</td></tr><tr><td>245</td><td>3.352%</td><td>0.0019% 2.164%</td></tr><tr><td>14201</td><td>4.698%</td><td>2.7974% 6.148%</td></tr><tr><td>14454</td><td>1.617%</td><td>0.0213% 0.573%</td></tr><tr><td>52087</td><td>1.374%</td><td>1.0797% 2.891%</td></tr><tr><td>7274</td><td>2.965%</td><td>0.1972% 3.648%</td></tr><tr><td>7533</td><td>6.476%</td><td>0.4637% 3.353%</td></tr><tr><td>14070</td><td>1.315</td><td>0.4786% 3.174%</td></tr></table></body></html>

# 3.6模型分析和实验结果总结

总结在不同数据集上的实验结果与分析，可以得出如下结论：

a)动态网络的节点影响力确实存在变化过程，基于静态网络节点影响力度量机制难以真实表现动态网络节点影响力;b)本文提出的动态网络节点影响力模型考虑了节点影响力随时间的衰减特性，能够较好的体现动态网络节点影响力的变化；c)本文提出的动态网络节点影响力的模型不仅可以体现节点在网络动态演化过程中的影响力变化，同时在局部时间点上也能准确衡量节点影响力，这对于研究网络演化具有重要的作用。

# 4 结束语

社会网络节点影响力度量对研究社会网络有着重要的作用，本文针对动态网络的节点影响力展开研究，提出了叠加网络快照的图结构，用于刻画网络的演变过程，使得不同时刻的网络之间建立联系。并以叠加网络快照的基础上，提出了动态网络节点影响力模型，将时间的变化作为节点影响力度量的重要属性之一，有效地对节点的影响力进行度量。基于模拟和真实网络，进行了大量实验，实验结果说明了本文模型的有效性和合理性。

随着社会网络的不断扩大和演化，在大规模动态网络上进行快速有效的计算是未来值得关注的研究方向。另外，动态网络节点影响力的评价机制以及节点影响力和网络演化的关系也是值得研究的方向。

# 参考文献：

[1]韩忠明，陈炎，刘雯，等.社会网络节点影响力分析研究[J].软件学 报,2017,28(1):84-104.   
[2] 刘红丽，黄雅丽，罗春海，等.基于用户行为的微博网络信息扩散模型 [J]．物理学报,2016,65(15):277-288.   
[3] 窦炳琳，李澎淞，张世永．基于结构的社会网络分析[J].计算机学报, 2012,35 (4): 741-753.   
[4]王与，高琳．基于社交圈的在线社交网络朋友推荐算法[J].计算机学 报,2014,37(4):801-808.   
[5]Galuba W,Aberer K,Chakraborty D,et al. Outtweeting the twitererspredicting information cascades in microblogs [C]//Proc of Workshop on Online Social Networks,2010:3-3.   
[6]Ghosh R,Lerman K.Predicting influential users in online social networks [J].arXiv:1005.4882,2015.   
[7]Ahmed N K,Rossi RA,Willke TL,et al.Revisiting role discovery in networks:from node to edge roles [J].arXiv preprint arXiv:1610.00844, 2016.   
[8]Ley M.DBLP:some lessons learned [J].Proceedings of the VLDB Endowment,2010,2(2):1493-1500. Genetics,2005,37(4):351-352.   
[10] Wilkins MR, Kummerfeld S K. Sticking together?Fallng apart?Exploring the dynamics of the interactome [J]. Trends in Biochemical Sciences,2008, 33 (5): 195-200.   
[11]韩忠明，陈炎，李梦琪，等．一种有效的基于三角结构的复杂网络节点 影响力度量模型[J].物理学报,2016,65(16):285-296   
[12]高琳，杨建业，覃桂敏.动态网络模式挖掘方法及其应用[J].软件学 报,2013,24(9): 2042-2061.   
[13] Bonacich P.Factoring and weighting approaches to status scores and clique identification[J].Journal ofMathematical Sociology,1972,2(1):113-120.   
[14] Freeman L C.A set of measures of centrality based on be-tweenness.[J] Sociometry,1977,40(1): 35-41.   
[15] Newman M E J.A measure of betweenness centrality based on random walks [J].Social Networks,2005,27(1): 39-54.   
[16] Sabidussi G.The Centrality Index of a Graph [J].Psy-chometrika,1966,31 (4): 581-603.   
[17] Kitsak M, Gallos LK,Havlin S,et al. Identification ofin-fluential spreaders in complex networks [J].Nature Physics,2010,6(11): 888-893.   
[18] Pavel B.ASurvey on PageRank Computing[J]. Internet Mathematics,2005, 2 (1): 73-120.   
[19] BryanK,Leise T.The \$25,Ooo,Ooo,Oo0 eigenvector:the linearalgebra behind Google[J]. SIAMReview,2006,48 (3): 569-581.   
[20] Kleinberg JM. Authoritative sources in a hyperlinked environment [J]. Journal of the ACM,1999,46 (5): 604-632.   
[21]LinyuanL,ZhangYC,HoYC,etal.Leadersinsocial networks,the Deliciouscase [J]. PLoS One,2011,6(6): e21202.   
[22] Tang J, Musolesi M,Mascolo C,et al. Analysing information flowsand key mediators through temporal centrality met-rics [C]// Proc of Workshop on Social Network Systems.2010: 1-6.   
[23] Kim H, Tang J,Anderson R,et al. Centrality prediction in dynamic human contact networks [J]. Computer Networks the International Journal of Computer& Telecommunications Networking,2012,56(3): 983-996.   
[24]Aggarwal C C,Lin S, YuPS.On influential node discovery in dynamic social networks [Cl//Proc of SIAM International Conference on Data Mining.Society for Industrial and Applied Mathematics.2012: 636-647.   
[25] Chen X,SongG,He X,et al. On Influential nodes tracking in dynamic social networks[C]// Proc of the 2015 SIAMInternational Conference on Data Mining. 2015: 613-621   
[26] Yin HJ, YuH, Zhu Z L,et al. Analysis of the dynamic influence of social network nodes [J].Scientific Programming,2017(1):1-6   
[27] Yu P S,Li X,LiuB.Adding the Temporal Dimension to Search"A Case Study in Publication Search [C]//Proc of IEEE//WIC//ACM International Conference on Web Intelligence.2005: 543-549.   
[28]闫光辉，赵红运，任亚缙，等．基于时间特性的微博热门话题检测算法 研究[J].计算机应用研究,2014,31(1):43-46.

[29]Manaskasemsak B，Rungsawang A，Yamana H.Time-weighted Web authoritative ranking [J]. Information Retrieval,2011,14(2): 133-157. [30]鞠时光，吕霞，王靖．基于时间链接分析的页面排序优化算法[J].计

算机应用研究,2009,26(7):2438-2441. [31] Wang D,BarabasiAL.Quantifying long-term scientific impact[J]. Science, 2013,342 (6154): 127-32