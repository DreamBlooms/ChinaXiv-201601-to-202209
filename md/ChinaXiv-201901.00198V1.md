# 基于持续增量模型的低速端口扫描检测算法

沈晶，薛少勃，刘海波(哈尔滨工程大学 计算机科学与技术学院，哈尔滨 150001)

摘要：端口扫描是一种常见的有效入侵技术，用于搜索易受攻击的 Intermet 主机和端口。快速端口扫描的检测技术已经成熟，但是隐蔽的低速端口扫描检测效果有待提升。针对低速端口扫描进行了研究，根据低速扫描的时间持续性和特征分散性，提出了一种基于持续增量模型的低速端口扫描检测算法，结合条件熵对特征分布的评估达到检测目的。实验结果表明算法的检测率能达到 $9 9 . 7 8 \%$ ，且误报率为 $7 \%$ 。算法适用于多种复杂网络环境，且不需要网络先验知识，检测率对阈值的精确性要求低，能够有效检测到低速端口扫描行为。

关键词：低速端口扫描；持续增量模型；信息熵；异常检测 中图分类号：TP393.08 doi:10.19734/j.issn.1001-3695.2018.10.0730

Low-speed port scan detection algorithm based on continuous incremental model

Shen Jing, Xue Shaobo,Liu Haibo† (SchoolofComputer Science&Technology,HarbinEngineering University,Harbin15oo1,China

Abstract: Port scanning is acommon and efective intrusion techniquefor searching vulnerable Internet hosts and ports. Thedetection technologyoffastportscanninghas matured,butthehiddenlow-speed portscanningdetectionefectneeds to be improved.This paper studies low-speed port scaning. According to the time persistence and feature dispersion of low-speed scanning,alow-speed port scanning detection algorithmbasedoncontinuous incremental modelis proposed.The conditional entropyisusedto evaluate thefeature distribution.Theexperimentalresults showthatthedetectionrateof the algorithm can reach $9 9 . 7 8 \%$ ,and the false positive rate is $7 \%$ .The algorithm is applicable to a variety of complex network environments,anddoes notrequire network prior knowledge.Thedetectionrate has lowaccuracyon thethreshold,andcan effectively detect low-speed port scanning behavior.

Key words: low-speed port scanning; continuous incremental model; information entropy; anomaly detection

# 0 引言

端口扫描是网络入侵的重要组成部分，端口的开放状态意味着通信渠道是否顺畅，攻击者通过发送试探性报文来发现目标系统存在的漏洞，并利用这些漏洞对目标主机进行攻击[1]。因此，有效的端口扫描行为检测可以将部分入侵行为扼杀在萌芽状态，从而达到防患于未然的效果，减少恶意攻击行为所带来的损失。

现在有众多的安全工具可以实现扫描一个范围的端口和IP 地址。不过，一个入侵监测系统(IDS)一般将能够捕获这种明显的扫描行为，然后可以通过阻挡源IP地址来实现关闭这个扫描，或者自动向安全管理员告警。但是多数认真的攻击者一般不会通过执行这种扫描来暴露自己的意图；相反，他们会放慢速度，使用半连接(half-connection)尝试来找出你的可用资源[2]。尽管这种低速的攻击方法很耗时，它实现起来却不困难，更重要的是很难防范它。

对于快速的端口扫描多采用基于阈值的检测算法，snort等大多数的入侵检测系统根据所配置的阈值信息（一定的时间段内允许某源地址所访问目的主机数和端口数的最大值),实时统计网络主机所访问的主机数和端口数，如果超过所设定的阈值则为扫描行为。但是阈值容易受到环境影响，文献[3]提出了改进的状态阈值随机游走算法，利用网络服务的主动映射来考虑连接尝试失败的良性原因，能有效应对环境变化的干扰，显著降低误报率。文献[4]开发了一个基于规则的网络入侵检测系统，可在 snort 平台上使用。文献[5]提出了一种虚拟网络功能架构,用于在网络功能虚拟化云开放平台中检测端口扫描行为，对分布式端口扫描行为具有良好的检测效果。以上方法对于速度快的扫描行为可以实现很好的检测，但是难以检测低速的端口扫描行为。文献[6]采用模糊技术方法进行异常检测，具有一定的效果，但存在参数敏感问题。邵国林等人在文献[7]中提出一种基于Dempster-Shafer证据理论的检测方法，不需要训练精确的阈值，且能够检测不同速度的端口扫描攻击。文献[8]提出一种协调扫描检测算法，可对分布式扫描攻击作出有效检测。文献[9]用主成分分析方法量化端口扫描的风险指数，来检测低速端口扫描攻击。随机阈值算法是用于检测扫描仪的高效且广泛引用的方法，但是可以通过将探测尝试与已知活动主机的访问混合来规避它们。文献[10]提出一种与随机阈值互补的方法应对规避策略，通过目的主机的入度情况对源主机建立风险评估，结合源主机的出度评判攻击的可能性。但是该方法建立在目的主机存在活跃度差异的基础上，对于活跃性均衡的网络环境无法适应。

本文根据低速扫描的时间持续性和特征分散性，提出一种基于持续增量模型的低速端口扫描检测算法。算法选取两个有效特征组成一个二项集，通过观察二项集的持续性和多项集对应特征的增长情况细粒度的筛选出网络中的可疑流量。最后通过条件熵对特征分布的评估，检测低速端口扫描攻击。

# 1 网络流量特征选取

# 1.1低速端口扫描行为描述

端口扫描通常分为水平扫描、垂直扫描和块扫描三种情况[11]。水平扫描是对多个不同目的主机的同一个端口进行扫描，垂直扫描是对特定目的主机的多个端口进行扫描，块扫描是水平扫描和垂直扫描的结合，是对多个不同目的主机的多个端口进行扫描。

有很多端口扫描工具，用户可以根据自己的需要选择不同的模板，由Nmap 负责选择实际的时间值[12]。模板也会针对其他的优化控制选项进行速度微调。参数-T有[0,5]的可选值，本文的数据集中出现以下三种：

-T1：数据包的发送间隔是 $1 5 \mathrm { s }$ 。

-T 2：不增加太大的网络负载，串行每个探测，并使每个探测间隔 $0 . 4 \mathrm { ~ s ~ }$ 。

-T3：Nmap的默认选项，在不使网络过载或者主机/端□丢失的情况下尽可能快速地扫描。

参数-T3对应的扫描攻击为常见的快速扫描，-T1、-T2对应的攻击称为低速端口扫描。扫描的速度越小，攻击流量在单位时间内所占比重越低，检测的难度也就越大。本文的数据集中单位时间流量的数量平均值为3554条每分钟，参数为-T3时攻击数据所占比例高达 $9 5 \%$ 。若攻击按照间隔$0 . 4 \mathrm { ~ s ~ }$ 进行，则攻击出现的频率约为0.04，如果间隔为15s,频率将更低。因此低速扫描攻击的隐蔽性更强，检测难度更大。

# 1.2低速端口扫描特征分析

扫描攻击发生时源主机和目的主机的连接示例如图1所示。其中S表示源主机，D表示目的主机，C表示与该源主机建立连接的不同目的主机的数量。正常活动的源主机通常情况下符合S1和S2的行为模式，特点是这类源主机和不同目的主机间建立的连接数少；而攻击主机更符合S3的情况，其和不同的目的主机建立大量的连接。

![](images/b9e16191fb3bd635ea7fe1e1c1f982c75d1979a2784e8d0b141f13c438320a9a.jpg)  
图1端口扫描攻击连接示例  
Fig.1Port scan attack connection example   
图2特征dip信息熵折线图  
Fig.2Information entropy line graph of feature dip

当然不能仅从连接数的大小来区分攻击和非攻击。例如服务器要响应大量请求时就会反向对请求者发送报文，这时的服务器主机的C值会很大，但服务器并没有发动攻击，因此C值大的源主机不一定是攻击者。对攻击行为的判定需要有更多依据。

本文用sip表示源主机IP地址，dip表示目的主机IP地址，dpt表示目的端口。攻击发生时相同sip和dip的报文采用的协议和报文长度具有局部一致性，在一定时间内报文的协议类型通常相同，多为TCP，UDP和ICMP。由于端口扫描的主要用于侦测端口的开放状态，只需要少量的报头信息就能完成。为了减小网络开销攻击者，通常将报文的数据部分控制在较低范围，报文长度多在300Bytes以下。另外低速扫描行为还有两个明显的特性：

a)持续性。由于采用的是低速的隐蔽形式来扫描端口，这种攻击就要以时间为代价，所以攻击具有持续性，水平扫描的sip-dpt组合和垂直扫描的sip-dip组合持续时间通常超过 $1 0 ~ \mathrm { m i n }$ 。

b)分散性。水平扫描的sip-dpt 组合对应的dpt总量大， 整体上呈现松散分布，重复率低；垂直扫描的sip-dip 组合对 应的dip总量大，整体上呈现松散分布，重复率低。

正常流量的分布情况与低速扫描行为在持续性和分散性上有明显的区别，合理利用这两个特征能够有效筛选出可疑流量，为异常检测的快速进行提供帮助。

# 2 异常流量检测算法

本文首先用单一特征信息熵方法，挖掘出明显的异常流量；然后重点针对低速扫描攻击作出检测。根据端口扫描特点的分析，将攻击分为水平扫描和垂直扫描，用持续增量模型过滤使检测范围缩减到最小，再用二项集组合的条件熵作最终的判定。

# 2.1信息熵检测方法

香农在1948年将热力学中熵的概念引入到信息论中，定义为信息熵[13]。信息熵用来解决信息度量的问题，公式如下：

$$
H ( X ) = - \sum _ { i = 1 } ^ { n } p ( x _ { i } ) \log p ( x _ { i } )
$$

其中： $H ( X )$ 代表了随机变量 $X$ 的信息熵； $p ( x _ { i } )$ 代表随机事件 $x _ { i }$ 出现的概率。网络流量数据由离散信息源组成，熵可以有效度量系统参数分布的变化情况，描述长时间的随机过程以及网络流量在某些维度上的分布状况。基于熵的异常检测系统的主要思想是：一旦有异常流量发生，总体流量的熵值会随之发生变化，通过熵值的变化检测出该异常。

定理1切比雪夫不等式：设随机变量 $\boldsymbol { \cal X }$ ， $E ( X ) = \mu$ ，$D ( X ) = \sigma ^ { 2 }$ ，则对任意的 $\varepsilon > 0$ ，必有

$$
P ( | X - \mu | \geq \varepsilon ) \leq \frac { \sigma ^ { 2 } } { \varepsilon ^ { 2 } }
$$

将流量的信息熵看做随机变量，根据切比雪夫不等式，令 $\scriptstyle { \varepsilon = 2 \sigma }$ ，则有 $P ( | X - \mu | \geq 2 \sigma ) \leq 1 / 4$ 。当攻击发生时，特征的熵值往往偏向（0,1）的两端。如果将阈值设置为 $\mu \pm 2 \sigma$ ，则异常流量落在这个区域的概率小于 $2 5 \%$ 。

0.8 Area 2 Area 3 0.7 WA 0.6 5 0.4 Area 1 0.3 dip 0.2 upper warning line lower warning line 500 600 700 800 Time

图2为特征dip的信息熵折线图。图中横坐标表示时间，单位为min;纵坐标表示特征dip在各个时间窗口内的熵值，经过归一化运算其范围在(0,1)之间。图中upperwarning line、lowerwaringline的纵坐标分别代表信息熵上、下两个阈值，落在两条线之间的坐标点被判定为正常点，两条线外的点为可疑点，阈值由各个时间窗口特征的信息熵根据式(2)计算得到。方框Area1圈中的坐标点熵值低于设定的阈值，被判定为异常流量。出现较大波动的原因可能是当前时间在午休范围内，网络波动大符合人们的行为规律，但也可能确实发生了攻击。通过频繁项集支持度计数的方法能够分辨出其中部分流量符合DOS攻击行为。Area2和Area3中的坐标点波动幅度与Area1相比，根据阈值信息将其判定为正常流量，但真实情况是这两个区域中存在水平扫描类型的低速扫描攻击由此可见单一特征的信息熵检测方法无法检测到低速扫描攻击，需要找到更精准的辨别方法。

# 2.2持续增量模型筛选方法

单纯用某些独立特征的信息熵来做检测，不考虑特征间的联系，只能检测到熵值变化很大的攻击。提升检测率的有效途径是挖掘流量中潜在的信息，特征间的关系就是一种重要的潜在信息。按照低速端口扫描的特征分析，本文从持续性和分散性入手建立关系模型。

对于水平扫描攻击，将数据集按时间顺序分为多个窗口，在每个窗口内选取 sip-dpt特征字段作为一个二项集组合，统计sip-dpt组合对应的dip特征字段的分布情况。低速水平扫描攻击的sip-dpt组合具有持续性，sip-dpt对应的dip 在数量上持续增长，直到完成一次扫描。而大部分正常流量的 sip-dpt组合连接时间小于 $1 ~ \mathrm { m i n }$ ，不具有持续性，且正常流量的sip-dpt组合对应的报文数量和报文长度分布无规则，在每个窗口中dip 的重复率高，dip 数量也很难持续增长。

低速扫描通过降低攻击速度隐藏自己，攻击发生时单位时间内攻击流量所占比重多低于 $5 \%$ ，容易被正常流量稀释。如果能将攻击数据的比重放大，减小正常流量的影响，那么异常检测的难度能降低。由于正常流量和低速端口扫描性质上的差异，如果按照持续性和分散性的标准过滤数据，那么过滤后的数据中正常流量所占比重会迅速下降。

按照上述思想，本文提出基于持续增量模型的低速端口扫描检测算法，用于考察流量的持续性和分散性。考察 sip-dpt持续性的步骤如下：

a)以 $2 ~ \mathrm { m i n }$ 为窗口长度分割数据。

b)统计每个窗口中不同的 sip-dpt 组合，并将对应的dip组成一个集合。

c)筛选出累计窗口数超过5次的sip-dpt组合。

找出持续sip-dpt组合后就要检验其对应的dip 是否具有分散性。用增量过滤算法来考察分散性，对某个窗口数为 $N$ 的持续组合，记时间窗口i $( i < N )$ 内的dip 集合为 $d i p _ { \mathrm { i } }$ 。第 $i$ 个窗口之前的 dip 集合的并集记为 $u _ { - } d i p$ 。若当前窗口对应的dip 集合中不存在与 $u _ { - } d i p$ 不同的元素，则 $u _ { - } d i p$ 清空。具体步骤如下：

a)初始化窗口号 $i = 0$ ,记 $d i p _ { 0 }$ 为 $p r e _ { - } d i p$ ， $p r e _ { - } d i p$ 集合长度 记为 $\boldsymbol { l e n } _ { 0 }$ 0 b) $i$ 加1，令 $u _ { - } d i p$ 为 $p r e _ { - } d i p$ 与 $d i p _ { \mathrm { i } }$ 的并集。 c)求 $u _ { - } d i p$ 与 $p r e _ { - } d i p$ 长度的差值 $^ d$ ，若 $d = 0$ ，则 $p r e _ { - } d i p = d i p _ { i }$ ；否则 $p r e _ { - } d i p = u _ { - } d i p$ 。 d)令窗口 $i$ 对应的值 $\boldsymbol { l e n } _ { i }$ 为 $p r e _ { - } d i p$ 的长度。若 $i \mathrm { > } = N$ ，结束; 否则转到步骤b)。

增量过滤算法将持续 sip-dpt组合所对应的dip 数量递增的流量筛选出来。持续增量模型筛选的结果如图3所示。每个子图的标题是一个sip-dpt 组合。横坐标表示时间，纵坐标表示 sip-dpt组合对应的dip 的局部累加和 $\boldsymbol { l e n } _ { i }$ 。图中带有“\*”标志的折线代表的是持续增量模型筛选的结果。折线图呈现周期性增长的态势，这是由于扫描分为多个阶段进行，一次扫描完成时dip数量达到峰值不再增加，这时需要重新开始新的计数周期用以探测下一次扫描。如果一个周期内的窗口数小于5，那么这段窗口就不满足攻击的持续性，就可以排除掉，带有""标志的折线正是在原有折线图基础上剔除局部增长窗口数少于5的周期后得到的。

![](images/0bd2824c657d9df8bf17a4d333e66f84b08682a8037b4bcdd858988d6fbb5147.jpg)  
图3持续增量模型筛选结果  
Fig.3Screening results of continuous incremental model

符合持续增量模型的组合被标记为可疑流量。最后用条件熵对每个增长周期做判定。正常流量的 sip-dpt条件特征字段对应的dip分布集中，即使有小部分正常流量满足了持续增量模型，在局部增长区域内其dip的重复率通常也比低速端口扫描的高，因此熵值偏小。而水平扫描攻击针对的是指定端口的不同dip，分布松散。因此可以将dip 条件熵值的大小作为判断依据。候选组合的条件熵如表1所示。从表1中能够看到，攻击组合"192.168.220.15,80"对应的条件熵明显大于其他正常组合。当确定攻击源IP和受害者端口后，根据协议类型和报文长度很容易找到受害者IP地址。

表1候选组合的条件熵  
Table 1 Conditional entropy of candidate combinations   

<html><body><table><tr><td>sip-dpt组合</td><td>dip 熵值</td><td>sip-dpt 组合</td><td>dip 熵值</td></tr><tr><td>192.168.220.7,443</td><td>0.629369</td><td>192.168.220.15,80</td><td>0.920444</td></tr><tr><td>192.168.220.15,443</td><td>0.570306</td><td>192.168.210.5,443</td><td>0.600042</td></tr><tr><td>192.168.220.11,443</td><td>0.58866</td><td>192.168.220.13,443</td><td>0.635613</td></tr></table></body></html>

对于垂直扫描攻击的检测方法和水平扫描类似，只需要调整特征字段的组合为sip-dip，用持续增量模型筛选对应的dpt，最后用条件熵确定攻击流量。

# 3 实验结果及分析

# 3.1网络流量数据集

本文的数据来自 CIDDS(coburg intrusion detection datasets)[14]。CIDDS是为基于异常的网络入侵检测系统创建评估数据集。入侵检测系统的发展可以看做是攻击者企图和防御者触发调整之间不断演变的过程。从这个角度来看，用旧数据集测试当前的入侵检测系统是不合适的。因此，CIDDS的主要目标是生成可定制和最新的数据集。为了实现这一目标，CIDDS背后的基本思想是使用OpenStack在虚拟环境中创建标记的基于流的数据集。

CIDDS 数据集由模拟的一个小型的小型商业环境产生，网络拓扑结构如图4所示。此环境包括多个客户端和典型服务器，如电子邮件服务器或Web 服务器。Python 脚本用于模拟良好的用户行为，如浏览Web、发送和接收电子邮件以及交换文件等。为确保尽可能真实的用户行为，使用配置文件设置每个用户的特征。在网络中执行拒绝服务(DoS)，暴力攻击和端口扫描来生成恶意流量。本文针对低速端口扫描攻击进行检测。

![](images/32f00a44ea62b46c5473dfb745eed8047269b111360661d1ad6e6e31acdd902c.jpg)  
图4模拟环境拓扑图  
Fig.4Topology diagram of simulated environment

# 3.2 实验结果及分析

由于CIDDS数据集总量大，本文只选取第二周的第二天7:30开始到下午14:35的150万条数据，数据包含了参数为-T1、-T2的低速水平扫描和垂直扫描攻击及DOS攻击，其中低速扫描攻击15096条，占比约为 $1 \%$ 。本文采用检测率和误报率两个指标来评价模型的准确度。检测率是指检测到的端口扫描总数与实际端口扫描总数的比率；误报率是指将正常行为判断为端口扫描的总数与检测结果总数的比率。本文将基于持续增量模型的方法和基于端口比的方法进行了比较，实验结果如表2所示。

表2端口扫描检测方法对比  
Table 2Comparison of port scan detection methods   

<html><body><table><tr><td rowspan="2">检测方法</td><td colspan="5">阈值</td><td rowspan="2">0.85</td></tr><tr><td></td><td>0.65</td><td>0.70</td><td>0.75</td><td>0.80</td></tr><tr><td>持续增</td><td>检测率</td><td>0.9978</td><td>0.9978</td><td>0.9978</td><td>0.9492</td><td>0.8742</td></tr><tr><td>量模型</td><td>误报率</td><td>0.2074</td><td>0.1705</td><td>0.0700</td><td>0.0157</td><td>0.0109</td></tr><tr><td>端口比</td><td>检测率</td><td>0.9451</td><td>0.9431</td><td>0.9431</td><td>0.9418</td><td>0.8828</td></tr><tr><td>模型</td><td>误报率</td><td>0.3542</td><td>0.3163</td><td>0.2663</td><td>0.1980</td><td>0.1451</td></tr></table></body></html>

常见的基于端口比阈值的方法，通过一定的时间段内源地址所访问目的主机数和端口数的比值来判定是否是攻击。低速扫描虽然在攻击发生后总的扫描数量依然庞大，攻击数据的端口比通常高于0.65，但是由于低速攻击持续时间长，正常流量和攻击流量混杂在一起无法作出有效区分，这种粗糙的判定方式容易造成正常流量的误判。从表2中能够看出端口比方法的检测率最高达到 $94 \%$ 以上，对应的误报率大于$1 9 . 8 \%$ ，可见端口比方法对低速扫描攻击的检测效果不是很理想。

相较于端口比方法，持续增量模型的检测率提升了约 $5 \%$ 而误报率下降了约 $10 \%$ 。当阈值在[0.65,0.75]区间上时，持续增量模型的检测率一直维持在 $9 9 . 7 8 \%$ ，由此可见持续增量模型的检测率对阈值的精确度要求较低。在误报率方面，随着阈值的增加，误报率逐渐降低，在保持检测率为 $9 9 . 7 8 \%$ 的条件下误报率能降至 $7 \%$ 。

持续增量模型充分利用特征之间的内在联系，构造二项集与对应特征的关系模型，精准刻画出低速端口扫描的持续性和分散性。正常流量的连接时间通常比低速扫描短暂，且通信端口分布在一定的范围内，访问的目的IP也有限，只有极少数的正常流量符合持续增量模型，经过筛选大部分正常流量被过滤出去，因此检测的范围将迅速缩小，检测难度也极大的降低。实验中过滤掉的正常流量占比超过 $9 8 . 6 \%$ ，说明了持续增量模型的高效性。持续增量模型在遇到特征的数量不再增加时会开始新的周期，这个机制使得异常检测分阶段进行，利用条件熵对特征分布情况的计算，能够精确区分一个连接中的攻击部分和非攻击部分。这些性质使得持续增量模型的检测率和误报率均优于端口比方法。

# 4 结束语

本文首先用单特征信息熵做粗分类，挖掘出明显的异常流量；然后重点针对低速扫描攻击作出检测。根据端口扫描特点的分析，将攻击分为水平扫描和垂直扫描，用持续增量模型过滤使检测范围缩减到最小，再用二项集组合的条件熵作最终的判定，分类后的检测结果更细致。采用持续增量模型能从图像上直观地看出攻击发生时扫描的强度，检测过程不需要先验知识，且检测率不受阈值精确度影响。

# 参考文献：

[1]王龙业，罗杰．互联网端口扫描攻击的安全检测方法 [J].信息安全 与技术,2016,7(2): 44-45,64. (Wang Longye,Luo Jie.The overview of safety testing methods aimed at the internet port scanning attack [J]. Information Security and Technology,2016,7(2): 44-45,64.)   
[2]程巍，章磊，高传善．隐蔽端口扫描的原理及防御方法[J].计算机 应用与软件,2004(8): 97-99.(Cheng Wei, Zhang Lei,Gao Chuanshan. The principle and defense of stealthy port scanning [J].Computer Applications and Software,2004 (8): 97-99.)   
[3]Alsaleh M,Oorschot P C V.Revisiting network scanning detection using sequential hypothesis testing [J].Security & Communication Networks,2012,5 (12): 1337-1350.   
[4]Patel S K, Sonker A. Rule-based network intrusion detection system for port scanning with efficient port scan detection rules using snort [J]. Future Generation Communication and Networking,2016，9(6): 339-350.   
[5]Sanz I J, Lopez MA,Mattos D MF,et al.A cooperation-aware virtual network function for proactive detection of distributed port scanning [C]/Proc of Cyber Security in Networking Conference. Piscataway, NJ: IEEE Press,2017.   
[6]吉治钢，蔡利栋．一种基于端口扫描的模糊检测策略[J].计算机应 用，2003(10):87-88,92.(Ji Zhigang,Cai Lidong.A port-scanning detection method based on fuzzy set theory [J]. Computer Applications, 2003 (10): 87-88,92.)   
[7]Shao G,Chen X,Yin X,et al.A fuzzy detection approach toward different speed port scan attcks based on Dempster-Shafer evidence theory [J]. Security and Communication Networks,2016,9 (15): 2627-2640.   
[8]Lv Y,Li Y, Tu S,et al. Coordinated scan detection algorithm based on the global characteristics of time sequence [C]//Proc of International Conference on Broadband&Wireless Computing.Piscataway,NJ: IEEE Press,2018:199-206.   
[9]Park S,Kim J.A study on risk index to analyze the impact of port scan and to detect slow port scan in network intrusion detection [J] Advanced Science Letters,2017,23 (10): 10329-10336.   
[10] Harang R E,Mell P.Evasion-resistant network scan detection [J]. Security Informatics,2015,4(1): 1-10.   
[11] Bhuyan MH, Bhattacharyya D K, Kalita JK. Surveying port scans and their detection methodologies [J]. The Computer Journal,2011,54 (10): 1565-1581 .   
[12] Anandita S,Rosmansyah Y,Dabarsyah B,et al. Implementation of

dendritic cell algorithm as an anomaly detection method for port scanning attack[C]//Proc of International Conference on Information Technology Systems and Innovation.Piscataway,NJ:IEEE Press,2015. [13]Berezinski,Przemyslaw,Jasiul B,et al.An entropy-based network

anomaly detection method[J].Entropy,2015,17(4):2367-2408. [14]RingM,Wunderlich S,Gruedl D,et al.Creation of flow-based data sets for intrusion detection [J]. Journal of Information Warfare,2O17,16(4): 40-53.