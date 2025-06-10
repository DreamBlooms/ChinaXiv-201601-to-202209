# 基于合作网络的学者动态学术影响力模式识别研究

范如霞」曾建勋」高亚瑞玺²1(中国科学技术信息研究所北京 100038)2(中国国防科技信息中心 北京 100142)

摘要：【目的】利用高合作学者识别算法和学者影响力模式识别算法识别出团队的高合作学者以及其动态学术影响力模式，为团队中人才成长提供参考。【方法】根据学者的合作人数情况，区分出团队中的高合作学者；利用高合作学者的发文量和度数中心度指标测度学者的个人影响力和在团队的影响力，识别学者的动态学术影响力模式。【结果】不同团队中的高合作学者数量不一，为零至多个。高合作学者的动态学术影响力模式不同，识别为稳步增长或成熟波动模式。【局限】仅利用两个指标来测度学者影响力，对于较复杂情况的学者需引入更多的指标识别其动态学术影响力模式。【结论】高合作学者识别算法和学者影响力模式识别算法能够较合理地识别出团队中的高合作学者及其动态学术影响力模式。

关键词:学术影响力社会网络分析动态模式分类号：G35

# 1引言

科研学者的学术影响力变化规律与价值评估研究，对于科研管理、人才培养具有重要意义。科研论文作为重要的科研产出对象，基于科研论文对学者进行学术影响力监控与评估是通常采用的方法。传统上，对学者科研论文的学术评估方法主要有同行评议、发文数量(总发文数量、平均发文数量)、引用数量(总引文数量、平均引文数量、影响因子)、基于发文和引文的评价指标(H指数、G指数等)[1-3]。此外，近年来社会网络分析方法也越来越多地被用于学者评价研究[4]。这些方法主要是通过测评学者之间的合作情况,根据学者在合作网络关系中的地位对其进行测度。

学者的学术影响力是一个动态变化的过程，只有从动态的角度对其进行研究，才能充分挖掘人才成长规律，预测人才发展方向，进而为制定人才培养计划以及选拔人才提供条件。当前，已有的学者影响力研究大都侧重于从静态角度展开[5-6]，较少进行动态分析[7，且大都从时间维度介绍学者的引文情况以反映趋势[8]。关于学者在团队中的影响力变化研究较少，尤其是在现实中团队有多位高影响力学者时，测度他们的动态学术表现能够更好地认识其成长情况，发现高影响力学者中团队影响力增长较快的学者，以便对其进行重点资助，为人才的发展和培养提供参考。本文针对上述考虑，基于作者合作网络，根据高合作学者识别算法识别团队中的高合作学者，并利用学者影响力模式算法发现其学术影响力的变化情况，从而发现团队中学术影响力增长较快的高合作学者，为人才选拔提供参考意义。

# 2 研究现状

利用作者合作网络来测评学者影响力已经得到应用。如汤森路透根据学者间的合著关系识别团队，为中国学者颁发"科研团队奖"9]。利用合作网络测评学者在团队中影响力的过程中，团队的识别是关键步骤。在合作团队的识别上，通常对合作网络进行派系分析[10以及2-派系分析[11]等。采用派系分析以及2-派系分析已经成为识别合作关系紧密团体的常用方法。但也有学者为了识别较为稳定且完整的团队，首先利用2-派系识别小团队，并以小团队中的作者为顶点，采用滚雪球方法使其在整体网络中向下层逐级滚动，以确定科研团队[12-13]。而此方法识别出的科研团队包括2-派系、3-派系、4-派系等其他派系，虽识别的科研团队规模较大，但利用此方法识别出的团队中的作者间关系较为稀疏也并不稳定。而本文是在较完整且稳定的团队识别基础上，再发现其高合作学者，可以弥补先行确定学者再确定团队方法中存在的不足。

在识别团队高影响力学者的方法上，Yan等指出通过科研合作网络中的中心性可以作为确定一个学者在其研究领域影响性的指标[14]。Abbasi等探讨了图书情报学学者合作网络的相关指标(包括度数中心度、接近中心度、中介中心度、特征向量中心度、平均连接强度和效率)与其引用影响力指标(H指数、G指数)之间的关系，并指出合作网络特征可用来预测科学家未来的学术表现[15-16]。王菲菲利用作者合作网分析学者的知识交流影响力，通过度数中心度、中介中心度和接近中心度指标发现其高影响力作者[17]。朱天等根据作者的合作数量以及合作范围对重要作者进行排名，以便识别重要作者[18]。但是这些对于学者影响力的研究大都侧重于从整体的学者合作状态来研究其影响力，是一种“快照式"的测评，缺乏从时间维度开展对学者学术影响力的变化规律研究，难以形成人才成长过程的全面认识。

也有学者通过引入时间维度，进行学者动态学术影响力研究，并采用个人影响因子、 $\mathrm { h r ( y ) }$ 指数和其他方法[19]。这些方法中，个人影响因子继承了影响因子指标，所以也无法避免影响因子采用近年的平均引文测评学者的较为不全面做法[20]。而 $\operatorname { h r } ( \mathrm { y } )$ 指数继承H指数，故也无法摆脱H指数固有的缺点，即对科研成绩一般的工作者区分度不高[21]。目前，除上述外，关于学者动态学术影响力的指标探讨相对较少。在人才评估中，众多高校采用发文量作为学者评定职称的常用指标，如浙江大学评选教授会对其成果进行统计和评测[22]。度数中心度也经常被用来测度学者在网络中的地位，以测量学者在学术关系中的影响力[23]。本文结合发文量和度数中心度两个指标分别测度学者在不同时间维度下的个人影响力和在团队的影响力，以补充学者的动态学术影响力测评。

# 3 研究思路

本文主要以团队的视角，根据团队中各学者所在子网中合作人数的多少识别出团队中的高合作学者。在此基础上，对团队中的高合作学者动态学术影响力进行研究，以期发现团队中学术影响力增长较快的高合作学者。因此，利用合作团队中学者在网络中的度数中心度代表学者在团队的影响力，发文量代表学者的个人影响力，根据学者在团队的影响力和个人影响力的时间变化以测度高合作学者的动态学术影响力为稳步增长模式或成熟波动模式。

# 3.1定义

n-派系：即任何两点之间在整体合作网络图中的距离(即捷径距离)最大不超过n，据此识别合作关系子网。

合作关系子网：在整体合作网络中，具有较为稳定合作关系的子网。本文特指合作两次以上的学者所形成的合作关系网络。

学者合作人数：论文合作关系网络中，点表示作者，边表示作者的合作关系，某个点直接关联的边数即定义为该点的合作人数。

归一化度数中心度：论文合作关系网络中，利用min-max标准化方法对学者的度数中心度进行归一化。

# 3.2算法

(1）高合作学者识别算法

首先通过 $\mathbf { n }$ -派系对整体合作网络划分合作关系子网。其次，根据学者的合作人数规模识别合作关系子网中的高合作学者。不同团队中高合作学者人数数量并不完全相同，有的团队仅有一位高合作学者，有的团队中有两位以上高合作学者(包括两位)，而有的团队无高合作学者。通过图1算法可识别团队中的高合作学者以及其数量特征。算法步骤如下：

$\textcircled{1}$ 通过 $n$ -派系分析，划分合作关系子网。本文旨在对较为稳定且完整的团队进行分析。因此 $n$ 的选择采取试探法，

首先 $n$ 从2开始：若进行 $n$ -派系分析时，划分为 $\mathbf { \nabla } _ { m }$ 个子群网;  
$( n { + } 1 )$ -派系分析时，划分为 $w$ 个子群网。

$m$ 个子网中至少有 $50 \%$ 的子网与 $w$ 中对应子网中的成员保持稳定不变，则采用 $n \cdot$ -派系分析。若不满足该条件，则$n$ 逐次加1。

$\textcircled{2}$ 根据子网中的作者构建非0-1合作矩阵 ${ M } ( a _ { i , j } )$ $a _ { i , j }$ 表示作者 $i$ 与作者 $j$ 之间的合作次数，且 $i$ 和 $j$ 的合作次数大于2。

$\textcircled{3}$ 对 $M$ 中的任意一个节点 $i .$ ，按以下方式计算合作人数向量 $C$ ，其中的元素 $C _ { i }$ 计算步骤为：

$C _ { i }$ 初始化为0，对 $\forall a _ { i , j } ( j$ 为 $M$ 所有列值),

If $( \forall a _ { i , j } > 0 )$ ）Then $C _ { i } { = } C _ { i } { + } 1$ 。

$\textcircled{4}$ 对 $\forall C _ { i }$ ， $\exists : C _ { i } : C _ { i } / Z \geqslant 5 0 \%$ ，其中 $Z$ 为学者网络总人数。则该合作网络中仅有一位高合作学者，且高合作学者为$i _ { \circ }$ 即仅存在一位学者与该团队一半以上的学者存在稳定的合作关系。

$\textcircled{5}$ 对于节点 $i , j , k$ 来说，节点的个数需为团队中总人数的 $20 \%$ 以内。再分别计算节点 $i , j , k$ 的合作人数向量，如果$C _ { i } { > } C _ { j } { > } C _ { k } ,$ 满足 $( C _ { i } { + } C _ { j } { + } C _ { k } ) / Z { \geqslant } 8 0 \%$ (据节点的合作人数向量多少依次相加，若 $j$ 与 $k$ 的合作人数相同，则合作频次多者优先相加)，则该合作网络中有多位高合作学者，且 $i , j , k$ 为其中的高合作学者。即高合作学者满足二八定律。

其中 $C _ { i \setminus }$ $C _ { j }$ 、 $C _ { k }$ 为首次相加超过团队总人数 $80 \%$ ，且$C _ { i }$ 、 $C _ { j }$ 、 $C _ { k }$ 相加时的合作学者必须唯一，即：若学者 $\mathbf { \Delta } _ { a }$ 与学者 $i , j , k$ 都有合作，则 $a$ 只计算一次。

$\textcircled{6}$ 若合作网络中，都不满足上述计算，说明该合作网络中学者间的合作较为均衡，则无高合作学者。

![](images/f18e8587f0bf0f68688feb3ec287eb9915bf98c72d8f2b99eb4d004e37d55af8.jpg)  
图1　高合作学者识别算法框图

(2）学者影响力模式识别算法

采用图1的算法识别出合作网络中的高合作学者后，采用学者影响力模式识别算法识别合作关系子网中高合作学者的动态学术影响力情况。图2算法利用每年学者的发文量衡量学者的个人学术影响力，用每年的论文合作网络中的度数中心度测评学者在团队中的学术影响力。此外，由于每年学者的论文合作网络成员会有变化，因而对度数中心度进行归一化处理后，以便对学者在各年间合作网络的重要程度进行比较。

![](images/72570cbc5db54e6eee217621c5149b497b8c35c911eb3a7c9d8d6980a3327c64.jpg)  
图2学者影响力模式识别算法框图(注：“无法识别"即此算法无法判断的学者影响力模式情况。)

学者影响力模式识别算法步骤如下：

$\textcircled{1}$ 对通过图1识别出的高合作学者，按时间跨度分别构建其合作网络。例如：识别高合作学者从 $m$ 年到 $n$ 年的动态影响力，则分别构建从 $m$ 年到 $n$ 年的 $m { - } n { + } 1$ 个合作网络。由于学者在论文中的作者顺序并不一致，需考虑作者权重，设第一作者、第二作者权重分别为 $w _ { 1 } , w _ { 2 }$ ，以此类推。

$\textcircled{2}$ 计算每个合作网络的 $m { - } n { + } 1$ 年的平均归一化度数中$\therefore$ 度与学者的最近 $( m { - } n ) / 2$ （若 $m { - } n$ 为偶数)或 $( m { - } n { + } 1 ) / 2$ （若$m { - } n$ 为奇数)年的平均归一化度数中心度，以下以 $m { - } n$ 为偶数说明其算法。

其中度数中 $\therefore$ 度计算需考虑其权重，若学者与 $A$ 学者以第一作者合作 $\scriptstyle A _ { 1 }$ 次，以第二作者合作 $\mathbf { \nabla } _ { A _ { 2 } }$ 次，以第三作者合作 $\mathbf { \nabla } \mathcal { A } _ { 3 }$ 次，以此类推，则学者与 $A$ 学者的合作次数为 $A _ { 1 } { \times } w _ { 1 } { + }$ $A _ { 2 } { \times } w _ { 2 } { + } A _ { 3 } { \times } w _ { 3 } { + } \cdots { + } \cdots$ ，若学者与 $B$ 学者以第一作者合作 $B _ { 1 }$ 次，以第二作者合作 $B _ { 2 }$ 次，以第三作者合作 $B _ { 3 }$ 次，以此类推，则学者与 $B$ 学者的合作次数为 $B _ { 1 } { \times } w _ { 1 } { + } B _ { 2 } { \times } w _ { 2 } { + } B _ { 3 } { \times } w _ { 3 } { + } { \cdots } { + } \qquad $ 那么该学者的度数中 $\therefore$ 度 $C _ { i }$ 为该学者与所有与其有合作关系学者的合作次数之和。即 $C _ { i } = { A _ { 1 } } \times w _ { 1 } + { A _ { 2 } } \times w _ { 2 } + { A _ { 3 } } \times w _ { 3 } + \cdots + \cdots + { B _ { 1 } }$

$\times _ { \boldsymbol { W } _ { 1 } + \boldsymbol { B } _ { 2 } \times \boldsymbol { w } _ { 2 } + \boldsymbol { B } _ { 3 } \times \boldsymbol { w } _ { 3 } + \cdots . } .$

$\textcircled{3}$ 计算学者 $\ m { - } n { + } 1$ 年的平均发文量与学者的最近$( m { - } n ) / 2$ （若 $m { - } n$ 为偶数)或 $( m { - } n { + } 1 ) / 2 \$ 若 $m { - } n$ 为奇数)年的平均发文量，以下以 $m { - } n$ 为偶数说明其算法。

其中发文量计算需考虑其权重，若学者以第一作者发文 $F _ { 1 }$ 篇，以第二作者发文 $F _ { 2 }$ 篇，以此类推，则该学者发文量Fi为F=F1×W1+F2XW2+F×W3+..…。

$\textcircled{4}$ 学者动态影响力模式计算方法：学者用 $i$ 定义， $m { - } n$ 年用 $Y _ { m } { - } Y _ { n }$ 表示，学者的度数中 $\therefore$ 度用 $C _ { i }$ 表示，归一化度数中心度用 $D _ { i }$ 表示，而发文量用 $F _ { i }$ 表示。

学者度数中心度归一化处理公式为 $D _ { i } { = } ( C _ { i } { - } C _ { m i n } ) /$ （204号 $( C _ { m a x }  – C _ { m i n } )$ 。其中学者最近 $( m { - } n ) / 2$ 年的平均 $F _ { i }$ 和平均 $D _ { i }$ 大于 $m { - } n { + } 1$ 年的平均 $F _ { i }$ 和平均 $D _ { i } ,$ 则为稳步增长模式；学者最近 $( m { - } n ) / 2$ 年的平均 $F _ { i }$ 和平均 $D _ { i }$ 小于 $m { - } n { + } 1$ 年的平均 $F _ { i }$ 和平均 $D _ { i } ,$ 则为成熟波动模式。

# 4实证分析

# 4.1 数据来源

考虑数据规模大小以及数据获取的便利性，通过构建图书情报领域学者合作网络，识别高合作学者及其动态学术影响力。数据范围为2011年-2015 年CSSCI收录的18 种图书情报学期刊刊载的24711篇论文，涉及17486位学者。

构建论文作者合作网络：若一篇文章由A、B、C三人合著，则合作网络中的合著关系为A-B、A-C、B-C。通过此种方式共得到9859个作者的26710条合著关系，并形成合作关系网络。由于本文研究的是具有稳定合作关系的子网，需限定合作次数大于2,得到1454位学者的1485条合著关系。

由于考虑学者在论文中的作者顺序并不一致，需对作者的论文贡献赋予一定的权重。但是由于作者权重赋值存在一定的主观性，且受学科差异性的影响，故赋值情况较为复杂[24]。而自然指数中的论文数指标以及ESI中的高被引论文数指标中作者权重均视为1,故本文作者权重也视为1。

# 4.2学者动态学术影响力模式分析

# (1）高合作学者识别

对具有稳定合作关系的网络进行 $n$ -派系分析来划分团队，通过尝试法确定 $n$ 为4，并划分为227个子网，其中有126个子网与 $n$ 为5时划分的对应子群成员保持固定不变。即 $n$ 为4时，识别整体网络中的团队较为稳定且规模较完整，因此对整体合作网络进行4-派

系分析。

分别对227个合作子网运行上述算法，识别出每个子网的高合作学者，如表1所示，从中挑选具有多位高合作学者的典型团队进行分析。

表1不同高合作学者数量的团队情况  

<html><body><table><tr><td>团队中的高合作学者数量</td><td>团队数</td></tr><tr><td>1</td><td>153</td></tr><tr><td>2</td><td>23</td></tr><tr><td>3</td><td>39</td></tr><tr><td>4</td><td>5</td></tr><tr><td>5</td><td>5</td></tr><tr><td>6</td><td>1</td></tr><tr><td>无</td><td>1</td></tr></table></body></html>

(注：其中"无"表示该团队学者较为均衡，无高合作学者。)

以朱庆华学者所在的合作关系子网为代表，如图3所示。通过学者合作人数向量分析，朱庆华所在团队中合作人数向量较多的为朱庆华和赵宇翔，其中朱庆华合作人数向量为15，赵宇翔合作人数向量为7，合作关系子网总人数为19人。因此朱庆华的合作人数向量超过总人数的一半以上，即该子网中的高合作学者只有一人，为朱庆华。

![](images/63eff7d50df7852480b72f129cefa6c823f5954fb4e0c3bb0d51df2dffb1b8aa.jpg)  
图3仅有一位高合作学者的合作团队(框内为高合作学者)

以黄水清学者所在的合作关系子网为代表，如图4所示。通过学者合作人数向量分析，该合作子网的总人数为15人，其中黄水清的合作人数向量最多，为7人。故无单独学者合作人数向量超过总人数的一半。而根据算法，将学者的合作人数向量从多到少排序并依次相加，前 $20 \%$ 以内的高合作学者的合作人数向量超过团队总人数的 $80 \%$ 。其中黄水清、何琳、王东波三位学者的合作人数向量相加为14人(若同一个学者与黄水清、何琳、王东波都有合作，则该学者只计算一次)，高合作学者人数为团队总人数的 $20 \%$ 以内，且 $1 4 / 1 5 { > } 8 0 \%$ 因此高合作学者满足二八定律。故该合作关系子网中有三位高合作学者，分别为：黄水清、何琳、王东波。

![](images/b0c9d4304026ca5a67510e8d4faf478a167106da1d3ee65b5541d366883a3be4.jpg)  
图4多位高合作学者的合作团队(框内为高合作学者)

(2）学者影响力模式识别

通过上述识别出团队的高合作学者后，再对高合作学者进行动态学术影响力识别。以黄水清、何琳以及王东波三位高合作学者所在的团队为代表，构建团队2011年-2015年的5年平均网络图及2014年-2015年的两年平均网络图，其中利用团队中学者在2011年-2015年的平均合作次数作为团队学者间新的共现次数构造合作矩阵以及网络，如图5所示；对团队中学者在2014年-2015年的平均合作次数作为团队学者间新的共现次数构造合作矩阵以及网络，如图6所示。

![](images/d019441a0e70a24086dbaeb96daa8dad19ea59acef7a8a29b4c1088c73a180ba.jpg)  
图55年平均网络图(数字为平均合作次数)

据上述算法，计算学者这5年的平均发文量和这5年平均网络图中的平均归一化度数中心度，及近两年的平均发文量和近两年平均网络图中的平均归一化度数中心度，其中5年平均值反映学者在整个时间段较为平均的长期表现，而近两年平均值测度的是学者的近期学术表现。通过长期与近期的学术表现对比，测评学者学术影响力水平的变化。学者一般通过论文的形式发表其研究成果，因此发文量可以一定程度上代表学者的研究水平。在同一网络中，度数中心度是对学者在网络中位置的表征，度数中心度越大，表明学者在该网络中的地位越重要。而在不同网络中，学者合作团队规模不一，故归一化度数中心度采用归一化的思想，方便学者在不同网络中地位的比较，归一化度数中心度越大，则学者在网络中的地位越重要。通过图5和图6可知，黄水清在两个网络图中都起着较为重要的连接作用，因此在团队的位置较为重要。而在5年平均网络图中，王东波的度数中心度最大，位置较为显著。在两年平均网络图中，何琳的度数中心度最大，在团队的位置更加明显。

![](images/23b5ee1b5eb6559d5b2ca5cbc518a0d39562a70e3164b37fe9f22a0b1594f393.jpg)  
图6两年平均网络图(数字为平均合作次数)

# $\textcircled{1}$ 稳步增长模式

通过图5和图6，对学者的发文量和归一化度数中心度进行分析，如表2所示。何琳2014年-2015年平均发文量超过2011年-2015年的平均发文量，即近期发文增长量高于5年平均发文量，且2014年-2015年的平均归一化度数中心度也较5年的平均归一化度数中心度增长幅度大，表明何琳近两年在团队中的位置较5年平均网络图愈加突出。因此何琳的动态学术影响力模式为稳步增长模式。

表2稳步增长模式的学者情况  

<html><body><table><tr><td></td><td>平均值</td><td>2011年-2014年- 2011年-2015年2014年-2015年 学者 2015年发文 2015年发 平均归一化度平均归一化度 文平均值</td><td>数中心度</td><td>数中心度</td></tr><tr><td>何琳</td><td>5.8</td><td>7</td><td>0.82</td><td>1</td></tr></table></body></html>

$\textcircled{2}$ 成熟波动模式

通过对高合作学者的在不同年份的学术表现进行分析，有的学者个人影响力和在团队的影响力因较为成熟而出现波动现象。如表3所示，黄水清和王东波2014年-2015年平均发文量与2011年-2015年的平均发文量相比波动减少。且两年平均合作网络较5年平均合作网络比较，虽王东波近两年平均合作次数有所上升，但平均归一化度数中心度却在下降，反映王东波近期合作表现虽与其之前相比有所提升，但王东波在两年网络图中的平均重要程度却有所下降。而黄水清在2014年-2015年的平均合作次数和平均归一化度数中心度较5年平均合作次数和5年平均归一化度数中心度都略有下降，表明黄水清在两年平均网络图中的平均重要程度有所降低。因此黄水清和王东波的动态学术影响力模式为成熟波动模式。

表3成熟波动模式的学者情况  

<html><body><table><tr><td>学者</td><td>2011年- 2015年发 文平均值</td><td>2014年- 2015年发 文平均值</td><td>2011年-2015 年平均归一化 度数中心度</td><td>2014年-2015 年平均归一化 度数中心度</td></tr><tr><td>黄水清</td><td>4.6</td><td>3</td><td>0.88</td><td>0.38</td></tr><tr><td>王东波</td><td>5.8</td><td>5</td><td>1</td><td>0.69</td></tr></table></body></html>

根据表4中学者不同年份发文的总被引频次分析，可知上述结论较为合理。由于被引频次具有时滞性，存在2015年论文还未产生引用，被引频次为0的情况。而其他年份中，何琳在近两年的论文被引频次较其他年份增加较多，黄水清和王东波近两年发表论文的被引频次表现较为不佳。这种情况也进一步说明何琳近两年的动态学术影响力为稳步增长模式，而黄水清和王东波近两年的动态学术影响力为成熟波动模式。

表4学者不同年份发文总被引频次变化情况  

<html><body><table><tr><td>年份</td><td>何琳</td><td>黄水清</td><td>王东波</td></tr><tr><td>2011</td><td>2</td><td>11</td><td>2</td></tr><tr><td>2012</td><td>7</td><td>12</td><td>1</td></tr><tr><td>2013</td><td>5</td><td>10</td><td>10</td></tr><tr><td>2014</td><td>14</td><td>1</td><td>0</td></tr><tr><td>2015</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

# 5结语

测度学者当前和将来的学术影响力，以对团队中高合作学者的动态学术影响力模式进行识别，既可以更好地呈现人才学术表现变化过程，还可以激励团队中高合作学者的成长，促进资源向稳步增长模式学者倾斜，进而促进学者的成长。然而目前关于学者动态学术影响力研究较少，且大多从发文和引文的角度分析学者的动态趋势，本文从团队的视角，识别合作团队中的高合作学者，进而分析多位高合作学者在团队的影响力变化来反映其成长。

本文关于学者动态学术影响力的模式研究，采用发文量和度数中心度指标来识别学者为稳步增长模式或成熟波动模式，仅是对动态学术影响力研究的一次探讨，以期补充新角度研究高合作学者动态学术影响力模式，为团队中人才培养提供参考。后继关于学者动态学术影响力的研究，将引入更多的学者测度指标，以便更加全面地对学者动态学术影响力模式进行识别评估。

# 参考文献：

[1]Abramo G, D'Angelo C A,Viel F. Peer Review Research Assessment:A Sensitivity Analysis of Performance Ranks to the Share of Research Product Evaluated[J]. Scientometrics, 2010, 85(3): 705-720.   
[2]Svider PF,Choudhry Z A,Choudhry O J,et al. The Use of theH-index in AcademicOtolaryngology[J].The Laryngoscope,2013,123(1): 103-106.   
[3]Waltman L，Van Eck N J. The Inconsistency of the H-index[J]. Journal of the American Society for Information Science and Technology,2012,63(2): 406-415.   
[4]刘璇，段宇锋，朱庆华，等．基于合著网络的学术人才评 价方法研究[J]．情报杂志,2014,33(12):77-82.(Liu Xuan, Duan Yufeng，Zhu Qinghua，et al. Study on Scholars Evaluation Method Based on Co-author Network[J]. Journal of Intelligence,2014,33(12): 77-82.)   
[5]林润辉，范建红．中国管理学者论文合作网络属性及其对 合作绩效的影响研究[J]．研究与发展管理，2012，24(4): 81-92.(Lin Runhui，Fan Jianhong．A Study of the Characteristicsof Co-authorship Network of Chinese Scholars in Management and Their Impacts on Cooperative Performance[J].R& D Management,2012,24(4): 81-92.)   
[6]汤强，王亚民.基于领域贡献值的高合作著者评价和合作网 络研究[J]．情报理论与实践，2015，38(1):85-89.(Tang Qiang，Wang Yamin.Study High Collaboration Scholars Evaluation Value and Cooperation Network Based on the Contribution in the Field[J]. Information Studies: Theory & Application,2015,38(1): 85-89.)   
[7]宋晓红.中国学者国际管理学合作网络演化及学术贡献分 析[D]．哈尔滨：哈尔滨工业大学，2011.(Song Xiaohong. Research on Chinese Scholars'International CoauthorNetwork' Evolution in Management and Academic Contribution [D]. Harbin: Harbin Institute of Technology,2011.)   
[8]杨思洛，邱均平，丁敬达，等．网络环境下国内学者引证 行为变化与学科间差异——基于历时角度的分析[J].中国 图书馆学报,2016,42(2):18-31.(Yang Siluo,Qiu Junping, Ding Jingda,et al.Differences of Citing Behavior over Time and Across Fields in China: A Diachronous Analysis[J]. Journal ofLibrary Science in China,2016,42(2):18-31.)   
[9]Thomson Reuters.Thomson Reuters China Citation Laureates 2014 [EB/OL].[2016-12-09]. http://www.thomsonscientific. com.cn/chinacitationlaureates/2014/.   
[10]庞弘燊，方曙，杨波，等．科研团队合作紧密度的分析研 究——以大连理工大学 WISE 实验室为例[J]．图书情报工 作,2011,55(4): 28-32,99. (Pang Hongshen,Fang Shu, Yang Bo,et al.Research on the Close Degree of Cooperation in Research Team——An Empirical Study in WISE Laboratory inDalianUniversityofTechnology[J].Libraryand Information Service,2011,55(4): 28-32,99.)   
[11]高杨.基于社会网络的虚拟团队知识共享促进策略研究[D]. 秦皇岛：燕山大学,2012.(Gao Yang.Research on the Virtual Team Knowledge Sharing Promotion Strategy Base on the Social Networks[D]. Qinhuangdao: Yanshan University, 2012.)   
[12]刘璇，朱庆华，段宇锋，等．社会网络分析法运用于科研 团队发现和评价的实证研究[J].信息资源管理学报，2011, 1(3): 32-37, 52. (Liu Xuan, Zhu Qinghua,Duan Yufeng, et al. An Empirical Study on the Application of Social Network Analysis to the Discovery and Evaluation of Scientific Research Team [J]. Journal of Information Resources Management,2011,1(3): 32-37,52.)   
[13] 尚珊，孟琦.基于凝聚子群法的专家团队聚合[J]．图书馆理 论与实践，2014(8):12-16．(Shang Shan，Meng Qi. Aggregation of Expert Team Based on Cohesive Subgroup[J]. Library Theory and Practice,2014(8):12-16.)   
[14] Yan E J,Ding Y.Applying Centrality Measures to Impact Analysis: A Coauthorship Network Analysis[J]. Journal of the American Society for Information Science and Technology, 2009,60(10): 2107-2118.   
[15] Abbasi A,Altmann J, Hossain L.Identifying the Effects of Co-authorship Networks on the Performance of Scholars: A Correlation and RegressionAnalysisof Performance Measures and Social Network Analysis Measures[J]. Journal of Informetrics,2011,5(4): 594-607.   
[16] Abbasi A,Chung K S K,Hossain L. Egocentric Analysis of Co-authorship Network Structure,Position and Performance [J]. Information Processing & Management,2012,48(4): 671-679.   
[17]王菲菲．发文与引文融合视角下的科学计量学领域核心作 者影响力分析[J]．科学学与科学技术管理，2014(12): 45-55.(Wang Feifei.The Influence of the Core Authors in the Field of Metrology from the Perspective of the Integration of Document and Citation [J]. Science of Scienceand Management of S.& T.,2014(12): 45-55.)   
[18]朱天，吴斌，王柏，等．科研合作网络的重要作者发现[J]. 数字图书馆论坛,2010(8):29-35.(Zhu Tian,Wu Bin,Wang Bai,et al. Core Author Discovery in Science Collaboration Network[J].Digital Library Forum,2010(8): 29-35.)   
[19] 高志，张志强．个人学术影响力的动态评价方法研究综述 [J]．情报杂志,2015,34(11):40-43，78.(Gao Zhi,Zhang Zhiqiang.A Review of Dynamic Quantitative Evaluation Methods for Individual Academic Impact[J]. Journal of Intelligence,2015,34(11): 40-43,78.)   
[20]Gupta HM,Campanha JR,Pesce RAG. Power-Law Distributions for the Citation Index of Scientific Publicationsand Scientists[J].Brazilian Journal of Physics,2005,35(4a):981-986.   
[21]王梅英，刘雪立．h-指数及其扩展指标的研究进展[J].中国 科技期刊研究，2011，22(2):184-189.(Wang Meiying,Liu Xueli.Research Advances on h Index and Its Expanded Variants[J].Chinese Journal of Scientific and Technical Periodicals,2011,22(2): 184-189.)   
[22] 浙江大学化学系．2015 化学系教授职务任职基本条件 [EB/OL].[2017-02-18]. http://www.chem.zju.edu.cn/chinese/ redir.php?catalog_id=473&page ${ \boldsymbol { \cdot } } = 0$ .(Department of Chemistry, Zhejiang University. 2015 Basic Requirements for the Position of Chemistry Department Professor [EB/OL]. [2017-02-18]. htp://www.chem.zju.edu.cn/chinese/redir.php? catalog_id=473&page $_ { : = 0 }$ ）   
[23]左美云，温晓薇，华晓清．知识管理领域学者间合著网络 分析[J]．信息资源管理学报,2012,2(4):4-15.(Zuo Meiyun, Wen Xiaowei,Hua Xiaoqing.Analysis on Co-authorship Network of Scholars in Knowledge Management[J]. Journal of Information Resources Management,2012,2(4): 4-15.)   
[24] 张闪闪．国内外作者贡献声明的贡献要素与贡献权重算法 初探[J]．图书情报工作，2016,60(1):125-134.(Zhang Shanshan.An Exploration Study of Contribution Factors and Weight Algorithm of Author Contribution Statements in China and Abroad[J].Library and Information Service,2016, 60(1): 125-134.)

# 作者贡献声明：

范如霞：提出论文思路，数据采集与分析，论文撰写及最终版本修订;曾建勋：改进论文思路和研究方案，修改和完善论文内容;高亚瑞玺：编写算法程序，识别不同合作团队中的高合作学者。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

[1]范如霞.author.xlxs.论文作者统计表.   
[2]范如霞.team.xlxs.团队模式统计表.

收稿日期:2016-12-29   
收修改稿日期:2017-03-16

支撑数据由作者自存储,E-mail:fanrx2015@istic.ac.cn。

# Recognizing Dynamic Academic Impacts of Scholars Based on Cooperative Network

Fan RuxialZeng Jianxun1Gao Yaruixi² 1(Institute of Scientific and Technical Information of China, Beijing 1Ooo38, China) ²(China Defense Science and Technology Information Center, Beijing 100142, China)

Abstract: [Objective] This paper tries to identifythe high cooperative scholars and their dynamic academic impacts with the helpof high cooperative scholar recognitionalgorithm andthe scholar impact recognition algorithm.[Methods] First,we identified the highcooperation scholars based onthe numberofcolaborators.Then,we estimatedthe impacts of these scholars and their teams with the amount of publications and degree of centrality.[Results]The numberof highly cooperative scholars varied among the teams.The dynamic academic impacts of highly cooperative scholars were either growing steadily or fluctuating maturely.[Limitations] Only used two indicators to measure the impacts of scholars.More indicators were needed to analyze the complex cases.[Conclusions] The proposed method could effectively identify the highly cooperative scholars of the team and their dynamic academic impacts.

Keywords: Academic ImpactSocial Network AnalysisDynamic Pattern