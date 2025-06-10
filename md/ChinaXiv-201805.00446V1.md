# 基于MD5-KNN的Wi-Fi室内定位算法研究

苗云龙¹，陆彦辉」，尹峰²，杨守义‘

(1．郑州大学 信息工程学院，郑州 450001;2.香港中文大学(深圳）深圳市大数据研究院，广东 深圳 518172)

摘要：为降低RSSI指纹数据库中指纹数据量和AP 数量对KNN 算法的运算效率的影响，提出一种基于MD5-KNN的Wi-Fi室内定位算法，对大型场所构建的RSSI指纹数据库进行优化。在离线阶段，将RSSI指纹数据库中的每条指纹转换成包含32位16进制表示的MD5序列。在线上阶段，该算法完成定位所需时间与AP数量无关，且不随指纹数量的增加而线性增加，降低了定位所需时间和运算量。同时，该算法自适应的匹配出合适的K值，有效解决了RSSI-KNN算法需手动设定K值的问题。实验结果表明，该算法有效提高了基于Wi-Fi的室内定位技术的定位精度以及定位效率。

关键词：无线信号；室内定位；接收信号强度；消息摘要算法；运算时间复杂度；K近邻算法 中图分类号：TN915.07 doi:10.3969/j.issn.1001-3695.2018.03.0178

# Research on Wi-Fi indoor location algorithm based on MD5-KNN

Miao Yunlong1,Lu Yanhui1,Yin Feng², Yang Shouyi1 (1.SchoolofInformationEngineering,ZhengzhuUniversityZhengzhou450ol,China;2.henzhnInstituteofigtathe Chinese University Hong Kong,Shenzhen Guangdong 518172, China)

Abstract: Inorder to reduce the influenceof fingerprintdataamount andAP number in theRSSIfingerprintdatabase on the computationalefficiencyoftheKNNalgorithm,this paperproposeda Wi-Fi indoorpositioningalgorithmbasedonMD5-KNN, whichoptimized the fingerprint databaseoflarge place.In theofline phase,the algorithmconverted each fingerprint intoa MD5 sequencethatincludeda32-bithexadecimalrepresentation.Intheolinephase,thetimeitookforthealgorithmtolocate Wwaslinear with the numberofAPsanddidnotincrease linearlywiththe numberoffingerprints,which reduced the time and calculationamountrequiredforpositioningefectively.Atthesamtime,thisalgorithmcalculatedtheappropriateKadaptively so as to effctively solvethe problem thatthe RSSI-KNN algorithm needs to manually setthe value ofK.Theexperimental results showthattheproposed algorithmcan effctively improve thepositioningaccuracyandlocation eficiencyofthe ndoor positioning technology based on Wi-Fi.

Keywords:Wi-Fi; indoor position; RSSI; MD5;CTC;KNN

# 0 引言

近年来，随着无线通信技术的发展以及移动终端设备性能不断增强，用户对基于位置服务（locationbased service，LBS）的需求越来越高。包括美国的GPS系统，俄罗斯GLONASS系统，中国北斗，欧洲伽利略在内的基于卫星信号的全球定位系统已经能够满足用户对室外定位的要求[1，并且定位精度还在进一步提高。然而由于室内环境错综复杂，且卫星信号不能穿透建筑物墙壁，尚缺少被广泛应用的较为成熟的、精度较高的室内定位技术。因此，对室内定位技术的研究成为目前研究的主要热点。现有的室内定位技术主要有蓝牙（bluetooth)技术、红外线（infrared)技术、超宽带（ultrawide band，UWB）技术、RFID 技术、Zig-Bee 技术、超声波技术以及Wi-Fi技术等[2' 3]。在上述室内定位技术中，蓝牙技术所需设备体积小，但它在复杂环境中稳定性差，且蓝牙信号传输距离短；红外线技术需要探测器之间和待定位目标之间可视，这在复杂的室内环境中是不可实现的；超宽带技术需要新加入盲节点且功耗较高；RFID技术定位精度高[4]，但其抗干扰能力较差。同时，除Wi-Fi技术以外，其余室内定位技术在现有的公共场所里没有较为完善的适合的基础设施，而建立这些基础设施也需要大量的时间和经济投入[5]。而随着网络通信技术的发展，以及人们对无线通信速度提升的需求，推动无线网络的普及，Wi-Fi接入点（AccessPoint,AP）也被广泛部署，Wi-Fi信号几乎可以在建筑物任意位置中使用。这使得基于Wi-Fi的室内定位技术的优势越来越显著，成为室内定位技术中的一项重要的研究领域。

基于Wi-Fi的室内定位算法主要分为基于接收信号强度（received signal strength，RSS）和基于测距模型两大类[。基于测距模型的定位算法需要预先对室内信道环境进行估计，建立信道模型[。而由于室内环境复杂多变的特性，基于测距模型的室内定位方法无法适用新环境。而基于RSSI的指纹室内定位算法因其能适应较复杂的室内环境而具有突出优势[8]。该算法涉及两个阶段：离线训练阶段（生成数据库）和线上定位阶段9]。离线阶段，在参考点位置接收来自周围AP的RSSI以及与RSSI对应的位置形成指纹信息，利用参考点的指纹信息构建RSSI指纹数据库。在线上定位阶段，测量待定位点接收到的来自周围AP的RSSI指纹信息。将该指纹与指纹数据库各指纹进行比较，获取指纹数据库中与测定RSSI相匹配的指纹信息，从而给用户当前的估计位置。基于指纹的定位算法主要包括： $K$ 最近邻法（K-nearestneighbor，KNN）和加权 $K$ 最近邻法（weightK-nearest neighbor，WKNN）[lo]。该算法相对于其他基于Wi-Fi的室内定会算法，计算复杂率较低，运行速度较快，易于实现。但由于Wi-Fi技术的普及，大型场所内的Wi-Fi热点逐渐增多，有时会达到成百上千的数量，定位参考点的数量也会增多。指纹数目和热点数目逐渐增大导致在离线阶段构造的RSSI指纹数据库越来越庞大，KNN和WKNN算法的定位效率会受到很大影响。同时，由于WKNN算法在定位阶段不能自适应的获取实时定位点的有效 $K$ 值，需要手动设置，无法保证定位精度[II]。因此，急需一种能够解决在Wi-Fi指纹数据库变得庞大时能够缩短定位时间、保证定位效率，以及自适应获取 $K$ 值，提升定位精度的解决方案。

针对上述存在的问题，本文提出一种基于MD5-KNN的Wi-Fi室内定位改进算法。该算法有效解决了当指纹数量以及热点数量增多时，指纹数据库变大而导致的定位效率降低的问题，降低了运算时间复杂度与指纹数据库指纹数量大小的关联性，提升了定位效率。同时能够自适应的确定 $K$ 值，有效提升了定位精度。

# 1 MD5-KNN室内定位算法

# 1.1基于RSSI的KNN室内定位算法

基于Wi-Fi指纹的室内定位过程包含两个阶段：离线训练阶段和线上定位阶段。基本原理图如图1所示。

![](images/6d827b4cfa250789703b545d87ad6a35678d69807dc8380f73e0a466a89aaa3a.jpg)  
图1RSSI-KNN算法原理框图

在离线训练阶段，通过各参考点的RSSI指纹信息构建指纹数据库，线上定位阶段通过KNN算法，估计出待定位点的位置。RSSI指纹数据库模型如表1所示：其中，参考点 $R P _ { j }$ 的指纹信息可以表示为： $[ ( x _ { j } , y _ { j } )$ ， $R S S I _ { j l }$ ，…， $R S S I _ { j i , \dots }$ ’ $R S S I _ { j M } ]$ ，$R S S I _ { j i }$ 表示在第 $j$ 个参考点接收到来自第 $i$ 个AP 的接收信号强度； $( x _ { j } , y _ { j } )$ 表示参考点 $R P _ { j }$ 的位置坐标。

表1RSSI指纹数据库模型  

<html><body><table><tr><td rowspan="2">参考点指纹信息</td><td colspan="5">指纹信息</td></tr><tr><td>AP1</td><td>AP2</td><td>AP3</td><td></td><td>APM</td></tr><tr><td>RP1 (x1,y1)</td><td>RSSI11</td><td></td><td>RSSI13</td><td>…</td><td>RSSIIM</td></tr><tr><td>RP2 (x2,y2)</td><td>RSSI21</td><td>RSSI22</td><td>RSSI23</td><td></td><td>RSSI2M</td></tr><tr><td colspan="6"></td></tr><tr><td>RPN</td><td>(xN,yN)</td><td>RSSIN1</td><td>RSSIN2</td><td>RSSIN3</td><td></td></tr></table></body></html>

假定待定位点 $P _ { i }$ ，坐标为 $( x _ { i } , y _ { i } )$ ，接收来自 $M$ 个AP点的RSSI指纹信息为 $[ R S S I _ { i l } ^ { \prime } , R S S I _ { i 2 } ^ { \prime }$ ，.， $R S S I _ { i M } ^ { ' } ] .$ 则该指纹与指纹数据库中的第 $j$ 条指纹的距离为：

$$
d i s t = \left( \sum _ { m = 1 } ^ { M } \Bigl | R S S I _ { { { m } _ { j } } } - R S S I _ { { { m } _ { i } } } \Bigr | ^ { u } \right) ^ { \frac { 1 } { u } } .
$$

其中： $M$ 表示指纹数据库中每条指纹信息的AP总数。 $\boldsymbol { u }$ 表示距离的类别：当 $\scriptstyle u = 1$ 时，dist表示曼哈顿距离；当 $\scriptstyle u = 2$ 时，dist 表示欧几里得距离。本文算法中采用的均为欧氏距离。

dist的值越小，表明第 $j$ 条指纹对应的位置和待定位点位置越相近。

KNN算法首先计算待定位点的指纹信息与指纹数据库的所有指纹信息的距离，按照dist的值从小到大选取 $K$ 个dist 对应的指纹坐标作为参考坐标。假设KNN算法计算得出的 $K$ 个匹配坐标为 $( x _ { k } , y _ { k } )$ ， $k { \in } [ 1 , K ]$ ，则KNN 算法中待定位点的估计坐标如式(2)所示。

$$
\left( x _ { i } ^ { ' } , y _ { i } ^ { ' } \right) { = } \frac { 1 } { K } { \sum _ { k = 1 } ^ { K } } \left( x _ { k } , y _ { k } \right) .
$$

WKNN算法中，待定位点的估计坐标如式(3)所示。

$$
\left( x _ { i } ^ { \cdot } , y _ { i } ^ { \cdot } \right) = \sum _ { k = 1 } ^ { K } W _ { k } \left( x _ { k } , y _ { k } \right) .
$$

$$
W _ { k } = \biggl ( \mathop { V } _ { d i s t _ { k } } \biggr ) \biggl / \biggl ( \sum _ { k = 1 } ^ { K } \mathop { V } _ { d i s t _ { k } } \biggr ) .
$$

其中：distk为第 $k$ 个参考点与待定位之间的欧氏距离； $W _ { k }$ 为WKNN算法的加权系数。待定位点的实际位置与估计位置之间的定位误差由式(5)所示。

$$
L o c \_ e r r = \sqrt { \left( x _ { i } - x _ { i } ^ { ' } \right) ^ { 2 } + \left( y _ { i } - y _ { i } ^ { ' } \right) ^ { 2 } } \ .
$$

在RSSI-KNN算法中，需要在定位过程之前手动设置 $K$ 值。由式（2）（5）可知，定位误差受 $K$ 值的影响，选取最佳的 $K$ 值对提升定位精度有重要意义。在每次的定位实现过程中，通过手动设置 $K$ 值很难获得最优 $K$ ，会造成定位精度的下降；同时，选择 $K$ 值的过程也会造成定位效率的下降。本文所提MD5-KNN算法能够有效避免上述问题，自适应的确定最佳 $K$ 值，其具体过程将在1.2节介绍。

# 1.2基于MD5-KNN的室内定位算法

由式(1)可知，在传统的KNN和WKNN算法中，当指纹数据库中的AP数量增大，即 $M$ 值增大时，计算dist的时间复杂度会随之增大，同时当指纹数据库增加时，即 $N$ 值增大时，为得到 $K$ 个匹配指纹的复杂度也会增加，从而造成定位效率下降。对此，本文对RSSI-KNN室内定位算法进行改进，改进后的原理图如图2所示。

![](images/a51a2ca7d225c600770e822ef5ae680b773a8aace2a1863ffb88ec640b964b8f.jpg)  
图2MD5-KNN定位算法原理图

从图2可以看出，改进后的算法是在原有算法的基础上，新增从RSSI指纹信息到MD5信息的转换部分。MD5算法（Message-DigestAlgorithm5）是计算机中广泛使用的哈希算法之一，该算法可以将任意长的数据压缩，生成128bit的MD5信息，而且该算法是不可逆的，无法通过MD5序列逆推用户的位置信息，有效保护了用户的隐私。指纹信息转换为MD5序列的伪代码如算法1所示。

<html><body><table><tr><td>算法1：基于MD5-KNN的室内定位算法:线下训练阶段</td></tr><tr><td>初始化：RSSI门限值：Thmax，Thmin</td></tr><tr><td>输入：参考点RSSI指纹</td></tr><tr><td>输出：基于MD5的指纹数据库</td></tr><tr><td>1：for指纹中的每个RSSI</td></tr></table></body></html>

<html><body><table><tr><td>2:</td><td>if RSSI 小于Thmax并且大于Thmin</td></tr><tr><td>3:</td><td>标记此RSSI为1</td></tr><tr><td>4:</td><td>else 标记此RSSI为0</td></tr><tr><td>5:</td><td>end for</td></tr><tr><td></td><td>6：for 转换过的01指纹序列</td></tr><tr><td>7:</td><td>执行 MD5 转换</td></tr><tr><td>8:</td><td>生成MD5 指纹</td></tr><tr><td>9:</td><td>end for</td></tr></table></body></html>

在算法1中， $T h _ { m a x }$ 为能够探测到的RSSI最大值， $T h _ { m i n }$ 为能够探测到的RSSI最小值， $\cdot _ { 0 } ,$ 表示对应的AP未被探测到或探测到的AP信号不稳定，‘1'表示对应的AP可以被探测到且AP信号稳定。将128bits信息生成了32位16进制的序列，即将指纹数据库中的每条指纹信息转换成32位16进制表示的MD5序列。构建的基于MD5的指纹库结构如表2所示。

表2MD5指纹数据库模型  

<html><body><table><tr><td rowspan="2">参考点信息</td><td colspan="5">指纹信息</td></tr><tr><td>AP1</td><td>AP2</td><td>AP3</td><td></td><td>APM</td></tr><tr><td>RP1</td><td>(x1,y1)</td><td></td><td>MD51</td><td></td><td></td></tr><tr><td>RP2</td><td>(x2,y2)</td><td></td><td></td><td>MD52</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>RPN</td><td>(xN,yN)</td><td></td><td></td><td>MD5N</td><td></td></tr></table></body></html>

在线上阶段，用户在定位过程中能够探测到的AP数量是有限的，为确保待定位的指纹信息与指纹数据库的指纹信息一致，对待定位点的指纹数据进行预处理：将指纹补全为 $M$ 长度，对未探测到的AP的RSSI值表示为NULL。线上定位阶段伪代码如算法2所示。

<html><body><table><tr><td>算法2：基于MD5-KNN的室内定位算法：线上定位阶段</td></tr><tr><td>初始化：K值为0</td></tr><tr><td>输入：待定位点Pi的MD5指纹信息</td></tr><tr><td>输出：待定位点的估计位置(xi,yi)</td></tr><tr><td>10：for MD5指纹数据库中的每条MD5指纹j</td></tr><tr><td>11:if 5=4</td></tr><tr><td>12: K=K+1; 13: end for</td></tr><tr><td>14：估计位置（xi,yi）=∑（x,yk）</td></tr></table></body></html>

由算法1和2可知，改进后的定位过程对传统基于指纹的定位算法的两个阶段进行优化。线下训练阶段：获取参考点的RSSI指纹信息后，将RSSI指纹信息转换成 $^ { \cdot } 0 1 ^ { \cdot }$ 表示的序列，通过四步运算（数据填充、记录信息长度、装入标准幻数、四轮循环运算)，生成MD5序列，构建基于MD5的指纹数据库。线上定位阶段：获取待定位点 $P _ { i }$ 的RSSI信息，构建 $P _ { i }$ 的MD5指纹信息，匹配出表2所示的MD5指纹库中与之相同的MD5指纹的个数，即为最佳 $K$ 值，从而利用式（2）估计出待定位点

的位置。

与1.1节中RSSI-KNN算法中需要手动设置 $K$ 值不同，根据"相近位置检测到的 AP 热点相近"的性质[12]，MD5-KNN 算法通过匹配MD5指纹库中与待定位点的MD5序列相同的MD5指纹的个数，获取最佳的 $K$ 值，从而避免RSSI-KNN算法中需要手动设置 $K$ 值产生的问题。

# 2 算法验证与实验分析

# 2.1定位误差结果分析

为评估本文提出的MD5-KNN算法的性能，本文选择郑州大学核心教学楼1层作为实验环境，获取RSSI指纹。面积接近 $2 0 0 0 m ^ { 2 }$ 的整个楼层有多间教室、水泥墙壁、及木质教室门，教学楼已经铺设有校园无线Wi-Fi，无需连接。测量过程中使用魅族MX6手机参与RSSI信息采集。为降低线下训练过程中信号不稳定带来的影响，本文在每个参考点位置采集20组数据，采用均值滤波，实测RSSI检测间隔为0.8秒。整个离线阶段构造的Wi-Fi指纹数据库共包含3000条指纹，每个指纹信息共包含来自200个AP点的RSSI信息。本文在定位区域另选取80个位置点作为待定位点，分别运用RSSI-KNN和MD5-KNN算法进行位置估计，获取定位误差，定位过程每隔1分钟进行一次，实验次数各30次。

所得的定位误差概率密度分布函数如图3所示。其中图3(a)为RSSI-KNN 算法的定位误差概率密度分布，图3(b)为MD5-KNN算法的定位误差概率密度分布：

![](images/0824de559b925dfa8bd2d4fece7a92a4616479700f1a3d56d2b251f575cb9fe9.jpg)  
图3定位误差概率密度分布

从图3可以看出，RSSI-KNN定位算法的误差分布较为分散，主要集中在 $1 { - } 8 \mathrm { m }$ 之间，而相对于RSSI-KNN 算法而言，本文提出的MD5-KNN定位算法的误差范围进一步收缩，定位精度进一步提高，主要集中在 $1 { - } 4 \mathrm { m }$ 之间。

RSSI-KNN算法与MD5-KNN算法定位误差累积分布函数（CumulativeDistributionFunction，CDF）如图4所示：

![](images/de9875d1fd15ae695f08dc2372eeb916777b7840c191f58469051da249145a1b.jpg)  
图4定位误差累积分布函数

从图4可以看出，RSSI-KNN算法的定位精度在误差为2.5$\mathbf { m }$ 的概率均接近 $80 \%$ ，而MD5-KNN算法的概率提升到了 $90 \%$ ，并且文章提出的优化算法的累积分布函数更快的接近1，表明MD5-KNN定位算法的定位效果要优于RSSI-KNN算法。

为进一步验证K值，即近邻个数对RSSI-KNN和MD5-KNN 两种算法在定位误差方面的影响，本文在某待定位点的定位过程中，通过改变K值，得到定位误差随 $K$ 值变化的情况，如图5所示。

![](images/4ac33d852fb8aa106a140606be9d2a0e056739e5b9505be7fbb740c43a56d4a1.jpg)  
图5定位误差随 $K$ 值的变化

从图5中可以看出，RSSI-KNN定位算法受 $K$ 值的影响较大， $K$ 值不同，得到的定位精度也不相同。当 $K { = } 5$ ，即近邻个数为5时，定位误差最小为 $3 . 1 \mathrm { ~ m ~ }$ ，此时 $K$ 值为最优 $K$ ；而由于MD5-KNN算法在定位过程中可以根据MD5序列值自动的确定最佳的近邻个数，即最优 $K$ ，可以获得最低定位误差。

# 2.2算法复杂度性能分析

RSSI-KNN定位算法的运算时间复杂度由式(6)表示。

$$
{ \cal O } _ { ( { \scriptscriptstyle M N } ) } = k _ { 1 } { ^ * M ^ { * } N } .
$$

本文提出的MD5-KNN定位算法的运算时间复杂度由式(7)表示。

$$
{ \cal O } _ { ( N ) } = k _ { \scriptscriptstyle 2 } { } ^ { \scriptscriptstyle * } 3 2 ^ { \scriptscriptstyle * } N .
$$

其中： $k _ { 1 } , k _ { 2 }$ 分别为RSSI-KNN和MD5-KNN的单次运算时间，且满足 $k _ { I } > k _ { 2 }$ ； $N$ 为指纹数据库的指纹数目； $M$ 为指纹库建立过程中能够探测到的所有AP的数量。在MD5-KNN定位算法中，将传统的RSSI指纹信息构建成长度为32位16进制序列表示的MD5序列，在进行MD5序列匹配的过程中，只需对比32 位长度的字符即可。因此 MD5-KNN 的运算时间复杂度（computationoftimecomplexity，CTC）只受数据库指纹条数影响，而RSSI-KNN定位算法不仅受数据库指纹条数的影响，还受AP数量的影响。

当AP热点数量一定时，RSSI-KNN法与MD5-KNN算法随指纹数量变化的运算时间复杂度如图6所示。其中图6(a)为定位区域内 AP数量高于32 的运算复杂度对比图，其中图6(b)为定位区域内AP数量低于32的运算复杂度对比图。

![](images/bd068d7418b1efd1b3f93ebdb3a0eb36682721f403b3d42cbaec8f0fa9e5c75d.jpg)  
图6运算时间复杂度随指纹数量的变化趋势

从图6可以看出，在指纹数量相同的条件下，当区域内的AP 数量大于32时，MD5-KNN定位算法定位所需要的时间明显小于RSSI-KNN 定位算法所需时间。而当 AP 数量小于 32时，MD5-KNN定位算法的定位效率要差于RSSI-KNN定位算法。这是由于MD5-KNN算法将每条RSSI指纹转换成了32字节长度固定的序列。

当指纹数据库指纹数量一定时，RSSI-KNN和MD5-KNN算法的运算时间复杂度随AP数量的变化如图7所示。

![](images/b7195718de39f9964ff0000280014d83d836ccf1ef83fbba9a9c63ef33e70c5d.jpg)  
图7运算时间复杂度随AP数量的变化趋势

从图7可以看出，由于MD5-KNN的运算复杂度与AP数量无关，而RSSI-KNN算法的运算复杂度与AP数量呈线性关系。而在大型场合如大型商场中，AP数量会远多于32个，这也就表明本文提出的MD5-KNN算法的可行性与实用性。

在仿真过程中，两种算法的实际定位效率如表3所示：

表3MD5-KNN与RSSI-KNN 定位效率  

<html><body><table><tr><td rowspan="2">定位算法</td><td colspan="2">定位过程消耗时间（s)</td></tr><tr><td>指纹数量为500</td><td>指纹数量为3000</td></tr><tr><td>MD5-KNN</td><td>0.12</td><td>0.4</td></tr><tr><td>RSSI-KNN</td><td>1.6</td><td>19.8</td></tr></table></body></html>

由表3可知，当指纹数量扩大6倍时，MD5-KNN的定位时间增加了2.3倍，而RSSI-KNN的定位时间增加了近13倍，而在大型商场的指纹库构建过程中，指纹数量会远远多于3000条，AP数量也会远多于32，因此本文提出的MD5-KNN定位算法的定位效率具有很大的优势。

# 3 结束语

本文在RSSI-KNN算法的基础上，提出基于MD5-KNN的室内定位算法。从仿真结果可以看出，相较于RSSI-KNN算法，本文所提的算法在定位精度和定位效率方面都有了明显的改善，定位稳定性方面也有了一定的提高。在大型场合如商场中，由于面积大，热点数目多，线下阶段构建指纹数据库的指纹条数以及AP数量都会逐渐增多，对定位精度和定位效率的要求也随之增大，更能体现出所提算法的优越性和实用性。此外，由于MD5算法的不可逆性，使得从MD5序列值无法逆推出用户的RSSI指纹信息，间接的保证了用户的位置隐私。

# 参考文献：

[1]Zhang Chong,Yu Hongyang.Indoor matching location algorithm based on WIFI signal strength [C]//Proc of the 1Oth International Conference on Communications,Circuits and Systems.Piscataway,NJ:IEEE Press,2013: 116-119.   
[2]Chen Zhenghua,Zhu Qinchang,Soh Y C.Smartphone Inertial Sensor-Based

IndoorLocalization and Tracking With iBeacon Corrections [J].IEEE Trans

on Industrial Informatics,2016,12 (4):1540-1549.   
[3]汪苑，林锦国．几种常用室内定位技术的探讨[J].中国仪器仪表,2011 (2): 54-57.(Wang Yuan,Lin Jinguo.Discussion on several common indoor positioning techniques [J]. China Instrumentation,2011 (2): 54-57.)   
[4]Gunawan M,Li Binghao,Gallagher T,et al.A new method to generate and maintain a Wi-Fi fingerprinting database automatically by using RFID [C]/ Proc of IPIN. Piscataway,NJ: IEEE Press,2013:1-6.   
[5]Hou Yuying,Sum Guoyue,Fan Binwen.The indoor wireless location technology research based on WiFi[C]//Proc of the 1Oth International Conference on Natural Computation.Piscataway,NJ: IEEE Press,2014: 1044-1049.   
[6]朱浩，顾宗海，苏金，等．一种基于交点质心求解的 RSSI 定位算法及 其优化[J].郑州大学学报：工学版,2010,31(6):43-46.(Zhu Hao,Gu Zonghai,Su Jin,et al.ARSSI location algorithm based on the centroid of point of intersection and its optimization [J].Journal of Zhengzhou University: Engineering Science,2010,31(6): 43-46.)   
[7]Zhao Linsheng,Wang Hongpeng,Li Pengpeng,et al.An improved Wi-Fi indoor localization method combining channel state information and received signal strength [C]//Proc of the 37th Chinese Control Conference. Piscataway,NJ:IEEE Press,2017: 8964-8969.   
[8]ZegeyeWK,Amsalu SB,AstatkeY,et al.Wi-FiRSS fingerprinting indoor localization for mobile devices [C]// Proc of the 7th Ubiquitous Computing, Electronics & Mobile Communication Conference.Piscataway,NJ: IEEE, 2016: 1-6.   
[9]Liu Hui, Darabi H,Banerjee P,et al. Survey of Wireless Indoor Positioning Techniques and Systems[J].IEEE Trans on Systems Man& Cybernetics Part C,2007,37(6):1067-1080.   
[10] Ge Xingbin,Qu Zhiyi.Optimization WIFI indoor positioning KNN algorithm location-based fingerprint [C]//Proc of the 7th IEEE International Conference on Software Engineering and Service Science.Piscataway, NJ: IEEE,2017: 135-137.   
[11]王磊，周慧，蒋国平，等.基于WiFi的自适应匹配预处理WKNN算法 [J]．信号处理,2015,31(9):1067-1074.(Wang Lei,Zhou Hui, Jiang Guoping.WiFi-based self-adaptive matching and preprocessing WKNN algorithm[J]. Signal Processing,2015,31(9): 1067-1074.)   
[12]姚志锋．基于WiFi和惯性传感器的多信息融合室内定位系统的设计与 实现[D].广州：华南理工大学，2016.(Yao Zhifeng.Design and implementation of indoor localization system based on multi-information fusion by using WiFi and inertial sensors [D].Guangzhou: South China University of Technology,2016.)