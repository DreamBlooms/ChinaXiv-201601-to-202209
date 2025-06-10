# 面向移动App流量的多特征集合集成聚类方法研究与应用

吴志敏1，刘珍1，王若愚2,，陈洁桐1

(1．广东药科大学 医药信息工程学院，广州 510006;2.华南理工大学 信息网络工程研究中心，广州 510041;3．广东省计算机网络重点实验室，广州510041)

摘要：针对移动互联网流量识别问题，基于多项性能评估指标，分析K-均值和谱聚类算法在不同特征集合或不同识别目标的流量数据集上的聚类性能；并提出基于多特征集合的集成聚类方法。比较分析实验表明，相同聚类方法在不同特征集合或不同识别目标数据集上性能有所不同，集成聚类方法能够有效提高利用单个特征集合的聚类方法的性能。进一步将集成聚类方法应用于App关联分析，分析结果可为移动App的划分和用户行为分析提供客观依据。

关键词：移动App流量；流量统计特征；集成聚类；流量识别 中图分类号：TP393 doi:10.3969/j.issn.1001-3695.2018.04.0250

# Research and Application of multi-feature sets based ensemble clustering method for mobile App traffic

Wu Zhimin1,Liu Zhen1†, Wang Ruoyu²,3, Chen Jietong1 (1.School of Medical Information Engineering Guangdong Pharmaceutical University，Guangzhou51oo06,China;2. Information&NetworkEnginering&Research Center,South China UniversityofTechnology,Guangzhou510041,China;3. Communication& Computer Network Lab ofGuangzhou 510041,China)

Abstract:To handle the mobile trafic identification problem,based on multipleperformanceevaluation metrics,this paper analyzed the performanceofK-Means and Spectral Clustering algorithmsonthedata sets characterizedbydiferent feature sets orlabeled with different classset,and proposed anensemble clustering method fromthe aspects of combining the clusteringresultson thedatasetswith diferentfeaturesets.Experimentalresultsshowthattheperformanceofthesame clustering algorithm is diferentonthe data sets with different feature sets ortraffcclassesandtheensembleclustering method isableto improve theoverallclustering performance.Further,this paperapplies the ensembleclusteringmethodon thecorrelation analysis of mobile apps，and theresultscan support the decision on groupingapps and analyzing user behaviors.

Key words: mobile app traffic; trafic statistics features; ensemble clustering; traffic identification

# 0 引言

近年来，随着移动互联网与智能终端设备的快速发展，用户可以随时随地访问互联网。成千上万的智能手机应用每天产生海量数据，移动互联网流量数据日益庞大。网络流量是记录和反映网络及其用户活动的重要载体。通过网络流量识别，可以间接地掌握互联网的使用情况，从而为网络运营、监控和测量方面提供辅助决策[1,2]。

基于机器学习的流量识别方法成为近年来的研究热点。早期，在传统互联网流量数据上，徐鹏等人[2的实验比较分析表明支持向量机比朴素贝叶斯的流量分类性能更加稳定；Soysal等人错误！未找到引用源。的比较实验结果表明决策树比贝叶斯网络和多层感知器在流量分类方面具有更高的准确性和有效性。后续多种互联网流量识别方法被提出，主要关注于在线流量分类问题错误！未找到引用源。、不平衡分类问题错误！未找到引用源。、分类鲁棒性[4.6.7]等。聚类方法的优点是无需有标记数据参与模型训练[8.9]。在互联网流量聚类方法研究方面，多种聚类方法被用于互联网流量识别，例如K均值、高斯混合模型和谱聚类[10,11]，DBSCAN 错误!未找到引用源。等。近期，鲁刚等人[12]利用前N（ $N { = } 1$ ，，10）个报文大小的特征建立基聚簇模型，然后利用基聚簇模型进行聚类，基于聚类概率作为新的特征建立新数据集，并利用有监督学习方法SVM 做最终决策，但是实验数据仍然是传统互联网流量。在移动互联网流量上，已有文献主要关注基于载荷的 App 识别错误!未找到引用源。和基于机器学习的App 行为识别错误!未找到引用源。，文献错误!未找到引用源。基于聚类方式识别移动互联网流量的P2P、WEB等服务类型，基于聚类方法的移动App 流量识别研究较为缺乏错误!未找到引用源。

已有互联网流量识别相关研究工作面临如下问题：a）各文献采用了不同的特征集合[18]，如单向流特征集合[2,19]、双向流特征集合[20.21;各实验数据集的识别目标也有所不同，例如 App级别（微信、QQ等）错误！未找到引用源。、用户行为级别（文本聊天、视频通话等）错误!未找到引用源。，各文献的实验结果不能直接进行比较;b）为管理大量的App，通常根据主观意识进行 App 类别划分，建立粗粒度识别目标，但是这种方式存在主观随意性，缺乏客观依据。

针对上述问题，本文主要贡献如下：

a）基于Mobilegt系统错误！未找到引用源。，采集移动互联网流量数据集，在数据集上提取四种不同的流量特征集合，开展App级别和上网行为（Behavior）级别的流量类别标记工作，为本文的聚类方法研究提供数据基础。b）利用多项性能评估指标，在不同特征集合、不同粒度类别标签的流量数据集上，比较分析各聚类方法、特征集合的性能等。c）为综合利用不同角度特征集合的优势，提出集成聚类方法，进一步提高单特征集合建立的聚类模型的流量识别性能；d）基于集成聚类方法，提出移动App 相似度评价指标，此相似度分析结果为App 归类（如社交类、视频类等）提供客观建议，并辅助用户上网行为分析。

# 1 集成聚类算法

将机器学习算法用于网络流量识别，需要首先对原始报文建立网络流，并提取流统计特征（如报文大小、流持续时间等统计特征)，然后建立特征向量描述的流样本集合，将其作为机器学习算法的输入，训练识别模型。已有研究表明，不同角度的流统计特征集合错误！未找到引用源。已被提出，并用于网络流量识别。聚类算法比较实验结果（详情见3.2小节）显示不同角度的特征集合可能有各自的优势，不分伯仲。受此启发，结合集成学习模型的特点，集成各特征集合描述的流量数据集上的聚类结果，可进一步提高聚类方法的性能。据此，本文提出基于多个特征集合的集成聚类算法（multi-feature sets basedensemble clustering,MFEC）。

# 1.1基本概念

为方便理解本文的网络流量识别工作，本小节首先给出相关的基本概念。

a)网络流量识别：将网络IP报文映射为流量类别（例如移动 App、用户行为等）。

b)网络流：在一定时间间隔内（如300s)，具有相同五元组{源IP、源端口、目的IP、目的端口、传输层协议}的IP报文组成。

c)流统计特征：在组成网络流的IP报文上，提取报文大小、报文到达时间间隔等统计值。

# 1.2基于多特征集合的集成聚类算法（MFEC)

假设有 $m$ 个特征集合，对网络流量数据 $s$ 特征化后，建立$m$ 个样本集合 $\{ S _ { I } , . . , S _ { m } \}$ ， $S _ { i } { = } \{ ( \mathbf { x } ^ { i } { _ { 1 } } , y _ { 1 } )$ ， $( \mathbf { x } ^ { i } { } _ { 2 } , y _ { 2 } )$ ，， $( { \bf x } ^ { i } { } _ { n } , y _ { n } )$ }， $\mathbf { x } _ { j } ^ { i }$ 表示利用第 $i$ 个特征向量描述第 $j$ 条网络流建立的流样本。集成聚类方法的伪代码如算法1。主要步骤包括：

a)在 $m$ 个样本集合上，利用基础聚类算法（例如 $\mathrm { ~  ~ K ~ }$ 均值),分别训练聚类模型 $\{ f _ { 1 } , f _ { 2 } , . . . , f _ { \mathrm { { m } } } \}$ 。b）为了处理集成聚类的不一致问题，利用每个聚类模型$f _ { i }$ ，建立一个流样本之间的关联矩阵 $\mathbf { M } , \ M [ i ] [ j ] [ k ]$ 记录了 $f _ { i }$ 是否将 $\mathbf { x } _ { j } ^ { i }$ 和 $\mathbf { x } _ { \hphantom { i } \hphantom { x } } ^ { i }$ 划分到一个聚簇中 (若相同，取值为1，否则为0)；c）各关联矩阵相乘，最后将两两关联的样本划分到同一个聚簇。

这意味着，仅当 $m$ 个聚类模型将某些样本划分到同一个聚簇时，它们最终才在同一个聚簇。例如有5个流样本，表示为X1,X2, X3,X4, ${ \bf x } _ { 5 }$ ，有2个聚类模型，分别开展聚簇后获得的样本关联矩阵为 ${ \bf { M } } _ { 1 }$ 和 ${ \bf M } _ { 2 }$ 基于 $\mathbf { M _ { 1 } }$ 可得 $\{ x 1 , x 2 , x 3 \}$ · $\{ x 4 , x 5 \}$ 两个簇;基于 $\mathbf { M } _ { 2 }$ 可得 $\{ x _ { 2 } , x _ { 3 } \}$ ： $\{ x _ { 1 } , x _ { 4 } , x _ { 5 } \}$ 两个簇。集成两个聚簇结果后的聚簇由 $\mathbf { M } { = } \mathbf { M } \mathrm { 1 } { \cdot } \mathbf { M } _ { 2 }$ 获得。集成后得到 $\{ x _ { 1 } \} ; \{ x _ { 2 } , \ x _ { 3 } \} ; \ \{ x _ { 4 } , \ x _ { 5 } \} .$ 三个簇。

$$
\mathbf { M } _ { 1 } = { \left[ \begin{array} { l l l l l } { 1 } & { 1 } & { 1 } & { 0 } & { 0 } \\ { 1 } & { 1 } & { 1 } & { 0 } & { 0 } \\ { 1 } & { 1 } & { 1 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 0 } & { 1 } & { 1 } \\ { 0 } & { 0 } & { 0 } & { 1 } & { 1 } \end{array} \right] } \qquad \mathbf { M } _ { 2 } = { \left[ \begin{array} { l l l l l } { 1 } & { 0 } & { 0 } & { 1 } & { 1 } \\ { 0 } & { 1 } & { 1 } & { 0 } & { 0 } \\ { 0 } & { 1 } & { 1 } & { 0 } & { 0 } \\ { 1 } & { 0 } & { 0 } & { 1 } & { 1 } \\ { 1 } & { 0 } & { 0 } & { 1 } & { 1 } \end{array} \right] } \qquad \mathbf { M } = \mathbf { M } _ { 1 } * \mathbf { M } _ { 2 } = { \left[ \begin{array} { l l l l l } { 1 } & { 0 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { 1 } & { 1 } & { 0 } & { 0 } \\ { 0 } & { 1 } & { 1 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 0 } & { 1 } & { 1 } \\ { 0 } & { 0 } & { 0 } & { 1 } & { 1 } \end{array} \right] }
$$

# 算法1MFEC集成聚类算法

输入 $S _ { 1 } , . . . , S _ { m }$   
输出 样本聚簇标签   
for $i = 1$ to $m$ （20   
$f _ { i } =$ BasicClustering(Si)//在每个数据集上训练一个聚类模型   
end   
for $i = 1$ to $m$ $\mathrm { f o r } j = 1 \mathrm { t o } n$ for $k = 1$ to $n$ $\operatorname { i f } f _ { i } ( \mathbf { x } _ { j } ) = = f _ { i } ( \mathbf { x } _ { k } )$ $M [ i ] [ j ] [ k ] = 1$ //构建关联矩阵 $\mathbf { M }$ end if end for end for   
end for   
for $i = 2$ to $n$ （204 $M [ 1 ] = M [ 1 ] { \cdot } M [ i ] ;$ （204号   
end for

# labels[] $\mathbf { \sigma } = \mathbf { \sigma }$ getCluster(M[1][I[);//基于关联矩阵M获得每个样本簇号

# 2 移动互联网流量数据采集与预处理

# 2.1流量数据采集

基于Mobilegt系统错误！未找到引用源。的实验数据采集环境部署如图1所示。Mobilegt包括客户端MgtClient应用，服务器端MgtServer程序。在移动终端设备上安装MgtClient，将MgtServer程序部署到服务器端。用户在移动终端开启MgtClient，并点击连接按钮，启动VPN服务和Socket数据采集程序；然后用户像往常一样使用其它应用，例如微信、微博、浏览网页等。移动端产生的流量会重路由到服务器端，在服务器端MgtServer程序采集客户端发出和接收的所有网络流量数据。MgtClient采集所有网络会话信息，即：五元组（源IP、源端口、目的IP、目的端口和传输层协议）与App 的映射关系，并记录到Socket 文件。当移动端结束数据采集，MgtClient 将Socket数据发送到服务器端，MgtServer程序接收Socket文件，并基于 Socket文件对采集的网络流量数据进行 App 标记工作。Socket文件记录了客户端网络流量的真实App信息。因此，MgtServer可以利用Socket文件对网络流量进行 $100 \%$ 准确率的类别标记工作。

![](images/62c5f6a9bfab5130da91cd5961b2172fffb7b8a883629fed5a9c7052f49ca497.jpg)  
图1数据采集环境

# 2.2 流量数据预处理

在采集的移动互联网流量报文数据上，首先组流并提取流统计特征，建立流样本集合。已有多种流统计特征被用于流量识别，最常用的是基于报文大小和报文到达时间间隔的统计计算。统计的网络流对象又分为双向流和单向流两种。相关定义如下：

假设某移动设备（ $\cdot  { \mathrm { I P } _ { 1 } }$ ， $\mathrm { P o r t _ { 1 } }$ ）与某服务器（ $\mathbf { I P } _ { 2 }$ ，Port2）利用传输层协议 $p r o$ 进行通信。在一定时间间隔内，它们之间通信的IP报文组成了网络流。

定义1单向流。由单个方向的IP 报文组成，OUT 方向的网络流表示为 $\{ P k t |$ （20 $\mathrm { s r c I P } ( P k t ) { = } \mathbf { I P } _ { 1 }$ & $\mathrm { d s t I P } ( P k t ) = { \mathrm { ~ \bf ~ I P } } _ { 2 }$ &$\mathrm { s r c P o r t } ( P k t ) = \mathrm { P o r t } _ { 1 } \& \mathrm { d s t P o r t } ( P k t ) = \mathrm { P o r t } _ { 2 } \nonumber$ &Protocol $( P k t ) = p r o { \mathrm { ~ } }$ ：IN 方向的网络流表示为 $\{ P k t | { \mathrm { ~ d s t I P } } ( P k t ) { = } { \mathrm { I P } } _ { 1 } \ E$ srcIF $\ { } ^ { \mathsf { P } } k t ) = \operatorname { I P } _ { 2 }$ &dstPort $( P k t ) ~ = ~ \mathrm { P o r t _ { 1 } }$ &srcPort(Pkt）= Port2 & Protocol $\left( P k t \right) =$ $p r o \}$ 。

定义2双向流。由两个方向的IP报文组成，表示为 $\{ P k t |$ 0 $\mathrm { s r c I P } ( P k t ) { = } \mathbf { I P } _ { 1 }$ & $\mathrm { d s t I P } ( P k t ) { = } ~ \mathrm { I P } _ { 2 } $ &srcPort(Pkt) $\mathbf { \sigma } = \mathbf { \sigma }$ Port1&dstPo $\mathrm { r t } ( P k t ) ~ = ~ \mathrm { P o r t } _ { 2 }$ ） $\parallel$ 1 $( \mathrm { d s t I P } ( P k t ) { = } \mathbf { I P } _ { 1 }$ & $\mathrm { s r c I P } ( P k t ) { = } \ \mathrm { I P } _ { 2 }$ &dstPor $\mathrm { t } ( P k t ) ~ =$ Porti& srcPort(Pkt) $\mathbf { \tau } = \mathbf { \tau }$ Port2）& Protocol(Pkt）=pro}。

基于以上定义，本文提取的四种流统计特征描述如下：

1）单向流统计特征（UniDirection）错误！未找到引用源。

IN 总报文数，IN字节数，IN报文大小(最小、最大、平均、标准差、峰度、偏度、标准误差)，IN报文到达时间间隔(最小、最大、平均、标准差)，IN流持续时间；OUT总报文数，OUT字节数，OUT报文大小(最小、最大、平均、标准差、峰度、偏度、标准误差)，OUT报文到达时间间隔(最小、最大、平均、标准差)，OUT流持续时间。

2）双向流统计特征（BiDirection）

总报文数，字节数，报文大小(最小、最大、平均、标准差、峰度、偏度、标准误差)，报文到达时间间隔(最小、最大、平均、标准差)，流持续时间。

3）前 $k$ 个报文大小分布（PS）[24]前 $k$ 各报文大小，分别表示为 $\{ p s _ { 1 } , p s _ { 2 } , . . . , p s _ { k } \} _ { }$ 0

4）前 $k$ 个报文大小分布-映射（PS-mapped）[24]

将前 $k$ 个报文的报文大小映射为4个数值{1,2,3,4}，新的特征表示为 $\{ \nu _ { 1 } , ~ \nu _ { 2 } , ~ . . . , ~ \nu _ { \mathrm { k } } \}$ 。IN 方向的报文大小的映射如式（1)，OUT方向的报文大小的映射如式（2）所示。

# 2.3实验数据

2.3.1 SAD（specific application data，特定应用数据）

为了验证不同特征集合在不同类别标签数据集上的性能，本文针对三种常用社交应用（QQ、微信、微博)，采集了SAD数据集。采集过程为：用户根据规定的App和上网行为（例如微信视频通话、微信文本通话等)，运行特定的 App 并执行相应的行为，每个应用持续时间大概 $2 0 ~ \mathrm { m i n }$ 。

表1App 类别标签数据集  

<html><body><table><tr><td>App类别</td><td>流数目</td><td>报文数目</td><td>字节数目/MB</td></tr><tr><td>QQ</td><td>206</td><td>1 633 031</td><td>1 127.587</td></tr><tr><td>WeChat</td><td>272</td><td>475 412</td><td>188.930</td></tr><tr><td>Weibo</td><td>336</td><td>122 287</td><td>96.889</td></tr><tr><td>总数目</td><td>814</td><td>2230730</td><td>1413.406</td></tr></table></body></html>

在运行过程中Mobilegt系统采集原始报文数据、组流、提取特征、并根据 Socket信息标记网络流样本的App 类别标签。根据用户在规定时间内运行特定App的上网行为记录，以人工标记方式标记流样本的Behavior类别标签。这意味着，上述采集的原始流量数据上赋予了两种类别标签（App类别标签和Behavior类别标签)，两种类别标签的流量数据在类间的分布如表1和表2所示。两个数据集的数据来源相同，只是流样本的标签类型不同，两个数据集的总体流数目、报文数目和字节数目相同。

表2Behavior类别标签数据集  

<html><body><table><tr><td>Behavior 类别</td><td>流数目</td><td>报文数目</td><td>字节数目/MB</td></tr><tr><td>audiochat</td><td>13</td><td>248 428</td><td>37.607</td></tr><tr><td>browse</td><td>361</td><td>107 828</td><td>85.090</td></tr><tr><td>chat</td><td>267</td><td>243 984</td><td>203.960</td></tr><tr><td>post</td><td>160</td><td>1 048 508</td><td>850.453</td></tr><tr><td>videochat</td><td>13</td><td>581 982</td><td>236.296</td></tr><tr><td>总数目</td><td>814</td><td>2230730</td><td>1413.406</td></tr></table></body></html>

2.3.2 MAD（more applications data，多应用数据）

SAD数据集涉及到人工标记，采集的数据有限。为了验证集成聚类方法在更多App 流量数据集上的性能。本文另外采集了MAD数据集，此数据集来自于多个用户，用户根据自己的意愿开启mobilegt终端应用，mobilegt服务器端自动采集和标记流量数据，采集时间为2017年1月，然后抽取流行的9个App 进行实验。MAD数据的类间分布情况如表3所示，相比SAD，其具有更多的不同App 标签。在这组数据上，主要用于验证集成聚类方法的性能，并分析集成聚类应用情况。

表3MAD数据集  

<html><body><table><tr><td>App类别</td><td>流数目</td><td>报文数目</td><td>字节数目/MB</td></tr><tr><td>Browser</td><td>4000</td><td>469 578</td><td>281.202</td></tr><tr><td>JdShop</td><td>1209</td><td>216 806</td><td>147.358</td></tr><tr><td>MgTV</td><td>4 000</td><td>3 153 559</td><td>2 208.004</td></tr><tr><td>Q</td><td>4206</td><td>3 874 852</td><td>2 774.752</td></tr><tr><td>VipShop</td><td>1745</td><td>433 065</td><td>253.586</td></tr><tr><td>WeChat</td><td>3684</td><td>1 037 697</td><td>651.094</td></tr><tr><td>Weibo</td><td>4 336</td><td>1 758 350</td><td>1 482.330</td></tr><tr><td>YahooMail</td><td>2 443</td><td>111 108</td><td>51.998</td></tr><tr><td>Youku</td><td>3054</td><td>14 63 226</td><td>1 078.451</td></tr></table></body></html>

# 3 聚类方法比较实验

# 3.1实验设计

本文实验首先比较不同的聚类方法在不同特征集合和不同类别标签流量数据集上的聚类性能，然后再实验比较本文提出的MFEC集成聚类算法的性能。目前尚未查阅到相关文献比较分析不同流统计特征集合的性能。在 SAD数据集上，提取了2.2小节的4个特征集合，并且SAD标记了2种类别标签，从而可得到8个不同的数据集。在各数据集上，利用K均值和谱聚类方法开展聚类，然后讨论和分析在不同 $k$ 值条件下，多项聚类性能评估指标的变化情况。考虑到不同特征的量纲对聚类结果的影响，实验采用Min-Max方式对所有特征进行归一化处理。每个聚类方法在各数据集上独立重复执行20次，实验结果为20次的平均。为了从不同角度分析聚类方法的性能，本文采用了以下三种评估指标。

# 1）信息熵

本文利用信息熵评估每个聚簇的纯度。给定某个随机变量$X$ ，信息熵定义为式（3），信息熵评价随机变量取值的离散程度。为评估聚簇中App分布的离散程度，式（3）中的 $p _ { i }$ 表示第i个App 在聚簇中的百分比。信息熵取值越小，表示聚簇的纯度越高。

$$
E n t r o p y ( X ) = - \sum _ { i = 1 } ^ { n } p _ { i } \log _ { 2 } p _ { i }
$$

# 2）轮廓系数

轮廓系数结合了簇内紧密度和簇间分离度两种因素，如式（4）所示。其中， $\mathbf { \Delta } _ { a }$ 是该样本与同簇其它样本的平均距离， $b$ 是与其距离最近的它簇样本的平均距离。 $s \in [ - 1 , \ 1 ]$ ， $s$ 越接近于1，聚类效果越好。

$$
s = { \frac { b - a } { \operatorname* { m a x } ( a , b ) } }
$$

3）CH分数

CH分数与轮廓系数的区别在于，CH分数是通过计算聚簇内各点与其中心的距离平方和表示簇内紧密度，计算各聚簇中心点与数据集中心点的距离平方和表示簇间分离度，如式（5)所示。其中， $t r$ 表示矩阵的迹， $U _ { k }$ 为簇间分离度矩阵， $W _ { k }$ 为簇内紧密度矩阵。 $n$ 为样本数， $k$ 为聚簇数。CH分数越大代表聚簇自身越紧密，聚簇之间越分散。

$$
c = \frac { t r ( U _ { k } ) \cdot ( n - k ) } { t r ( W _ { k } ) \cdot ( k - 1 ) }
$$

# 3.2K-均值与谱聚类在不同数据集上的性能分析

本小节旨在分析K-均值和谱聚类算法在不同特征集合和不同类别标签的流量数据集上的性能，探究a）聚类算法在不同特征集合的流量数据集上的性能是否稳定；b）聚类算法在不同类别标签的流量数据集上的性能是否稳定；c)K-均值与谱聚类算法比较，哪种算法在流量数据上的性能更优；d）哪一类特征集合在流量数据上表现更优。

# 3.2.1在SAD(App 类别标签)数据集上的性能

K-均值和谱聚类算法在App类别标记数据集上的实验结果分别如图2和图3所示。a）信息熵，随着 $K$ 值增加，K-均值和谱聚类的信息熵都随之降低，K-均值表现相对稳定，波动次数更少,并且双向流特征集的信息熵最小;b)轮廓系数,谱聚类的效果劣于K-均值,对于表现较好的单向流与双向流特征集，谱聚类从 $K$ 取初值到逐渐增大的过程中，其轮廓系数基本维持在0.4以下，而K-均值却能够稳定在0.4以上;c）CH分数：对于4个特征集合表示的数据集，K-均值的CH分数最小值分别约为480、420、220、160，皆大于谱聚类的最大值分别约370、320、80、45；与轮廓系数类似，双向流特征和单向流特征获得更好的性能。

![](images/bb92cb10016f0282e21de00a8c5f59abda2d74b36fdfda4758ba828e6b5e278e.jpg)  
图2K-均值在SAD(App类别标签)数据集上的实验结果

![](images/f00a63fc3e2be046c3c316cbc3e9b6e6dd0d7ebe9cbdce7dc2d949dbc0ea7cc2.jpg)  
图3谱聚类在SAD(App类别标签)数据集上的实验结果

3.2.2在SAD(behavior类别标签)数据集上的性能

K-均值和谱聚类在Behavior类别数据集上的实验结果分别如图4、5所示。

a）信息熵。与App标签数据集上的实验结果相比，两种聚类算法在Behavior标签数据集上的性能更优，这是由于Behavior的标签比App的标签粒度更细，同个类别的数据的聚集程度更高，更易聚类；当 $K$ 值增加到最大20时4种特征集合的性能相差不多。

b）轮廓系数与CH分数：类似App数据的性能，K-均值比谱聚类性能更优；在特征集合方面，单向流特征和双向流特征集合性能更优。

![](images/47cd5725184157131c15fdad70505a0c655505efccb63d11af9ea7ee0d4a6f48.jpg)  
图4K-均值在SAD(Behavior类别标签)数据集上的实验结果

![](images/2fb135d5fdfc10afd342cf63ae95b18ff2655a43e02996f91ce47a7431e38086.jpg)  
图5谱聚类在SAD(Behavior类别标签)数据集上的实验结果

基于上述实验结果分析，得出以下结论：

a）在聚类方法比较方面，K-均值的聚类纯度（信息熵）接近谱聚类的性能情况下，其聚类结果的聚簇内更紧密，簇间距离更远。并且K-均值的计算开销低于谱聚类，K-均值更适用于移动互联网流量识别。

b)在4个特征集合比较方面，单向流特征和双向流特征集总是表现更优。这是由于这两类特征的信息量更丰富，对报文大小和报文到达时间间隔进行了不同角度的统计计算。但是，两者之一没有总是表现最优，各有不同的适应场景。本文提出的MFEC方法，可集成两种特征集合表征的数据集上的聚类结果，提高单个特征的聚类性能。

实验结果还表明，在App目标数据上比在Behavior目标数据上的聚类更难，这是由于 App 包括了多种行为，不同 App之间还存在相似的行为。第 3.3 小节将在较难识别的多个 App标记的数据集上验证MFEC的性能。

# 3.3MAD数据集上MFEC方法性能验证分析

根据第3.2小节实验结果，K-均值相对更适用于移动互联网流量识别，本小节将采用K-均值作为基础算法，单向流特征（UniDirection）和双向流特征（BiDirection）作为特征集合，在规模更大、App类别更多的MAD数据集上验证MFEC方法的性能。在性能评价指标方面，采用上述三项指标之外，SSE（sumof squarederrors)和App识别准确率也将作为评价指标。为了缓解类间样本不平衡对聚类实验性能的影响，每个应用抽样了4000条网络流，不足4000的则全部抽样。

# 3.3.1MFEC实验性能分析

MAD数据集上聚类评估结果如图6所示，其中，UniDirection和BiDirection表示采用相应特征集合的K-均值，MFEC表示本文的集成聚类方法。实验结果表明，随着 $K$ 值的增加，K-均值和集成聚类产生的SSE和信息熵呈现较为平稳的下降趋势；轮廓系数在整体上是上升的，而CH分数是下降的，且随着 $K$ 值的增加而渐渐趋向平稳。其原因可能是随着 $K$ 值增加，属于相同类别的流样本划分到多个聚簇，簇间的距离可能降低。总体上，集成聚类的性能总是保持最优，实验结果验证了MFEC方法可以进一步提高利用单个特征集合的K-均值的性能。

![](images/4e6967595fa5d5fafc0975ce98c3f08b8ee3e887bbeb456e2cd7cd1bb27aec07.jpg)  
图6MFEC与K-均值的四项指标性能比较

为验证各聚类方法在App识别准确率方面的性能，本文借鉴文献[9]的做法，对于每个聚簇可将样本数最多的App标签作为这个簇的所有样本的预测类别标签，从而计算识别准确率。识别准确率可定义为，对于给定的应用样本识别出的应用流数与总流数之比，定义如下：

$$
A c c u r a c y = { \frac { T P + T N } { T P + F P + T N + F N } }
$$

图7显示了K-均值与MFEC对App 的识别准确率。实验结果表明，当 $2 \leq K < 7$ 时，K均值在整体上比MFEC的识别准确率要高。随着 $K$ 值增大，样本得以更细的划分，因而各自的准确率也逐渐增加。其中MFEC的提升尤为明显，并明显地超过了K-均值。MFEC的结果表明，平均性能可达到 $70 \%$ 以上的App 识别准确率。

基于多特征集的MFEC的性能优于K-均值聚类。其主要原因可能是，集成聚类能够综合利用在不同特征集上建立的多个聚类模型所得结果，在一定程度上起到"集优"的效果。另外，采用集成聚类可以帮助提高App识别准确率。当 $K$ 取值更大时，集成聚类更能显出它的这一优势。

![](images/d1953fd54a71fa40875f92b8f8a0a9d390ce3fe39a3cc6b72c58c6f9daf0d50d.jpg)  
图7MFEC与K均值的识别准确率比较结果

3.3.2基于集成聚类的App相似度分析

目前,已有大量移动 App,而将机器学习算法用于大量 App分类的性能往往较差，这是由于比较相似的应用容易被相互错分所致，例如同属于社交应用的QQ和微信。某些文献错误！未找到引用源。采用粗粒度的互联网流量分类，将相似的应用归为一类，但现有的应用划分方式主要基于主观判断。本节将MFEC方法应用到MAD数据集，分析各应用之间的相似度，为应用划分和用户行为分析提供客观建议。

1）App 相似度评价指标

基于Jaccard 距离指标，本文提出 App 间相似度指标，其定义如下：

$$
\mathit { s i m i l a r i t y } ( A , B ) = \frac { \displaystyle \sum _ { i = 1 } ^ { n } \frac { m i n \{ a _ { i } , b _ { i } \} } { a _ { i } + b _ { i } } } { n }
$$

其中 $: a _ { i }$ 和 $b _ { i }$ 分别表示应用A和应用B在第 $i$ 个聚簇中的样本数，聚簇总数为 $n$ 。此指标的取值范围为[0,0.5]。当取值为0，表示A和B没有样本聚类到相同的簇，两者相似度最低；当取值为0.5，表示A和B之间相似度最高。

# 2）App 相似度的分析

MFEC聚类后的App相似度矩阵如表4所示，灰体表示自身的相似度，粗体表示其相似度高于相似度阈值（所有相似度的平均，即0.278)。其中，某些App（如Browser）与多个App相似，而某些App（YahooMail）则没有与之相似的App。为了更清晰的表明App的相似关系，本文建立了如图8所示的关联图。在图8中，每个节点表示矩阵中行和列的某个App，若两个App 相似度大于某个阈值，则建立一条边，并且边的权重为相似度。

表4MAD 数据集App 相似度矩阵  

<html><body><table><tr><td></td><td>Browser</td><td>JdShop</td><td>MgTV</td><td>QQ</td><td>VipShop</td><td>WeChat</td><td>Weibo</td><td>YahooMail</td><td>Youku</td></tr><tr><td>Browser</td><td>0.500</td><td>0.342</td><td>0.224</td><td>0.249</td><td>0.334</td><td>0.347</td><td>0.364</td><td>0.316</td><td>0.254</td></tr><tr><td>JdShop</td><td>0.342</td><td>0.500</td><td>0.186</td><td>0.306</td><td>0.349</td><td>0.318</td><td>0.307</td><td>0.209</td><td>0.274</td></tr><tr><td>MgTV</td><td>0.224</td><td>0.186</td><td>0.500</td><td>0.219</td><td>0.195</td><td>0.235</td><td>0.158</td><td>0.236</td><td>0.339</td></tr><tr><td>Q</td><td>0.249</td><td>0.306</td><td>0.219</td><td>0.500</td><td>0.318</td><td>0.400</td><td>0.247</td><td>0.304</td><td>0.257</td></tr><tr><td>VipShop</td><td>0.334</td><td>0.349</td><td>0.195</td><td>0.318</td><td>0.500</td><td>0.307</td><td>0.254</td><td>0.284</td><td>0.182</td></tr><tr><td>WeChat</td><td>0.347</td><td>0.318</td><td>0.235</td><td>0.400</td><td>0.307</td><td>0.500</td><td>0.324</td><td>0.290</td><td>0.307</td></tr><tr><td>Weibo</td><td>0.364</td><td>0.307</td><td>0.158</td><td>0.247</td><td>0.254</td><td>0.324</td><td>0.500</td><td>0.245</td><td>0.314</td></tr><tr><td>YahooMail</td><td>0.316</td><td>0.209</td><td>0.236</td><td>0.304</td><td>0.284</td><td>0.290</td><td>0.245</td><td>0.500</td><td>0.213</td></tr><tr><td>Youku</td><td>0.254</td><td>0.274</td><td>0.339</td><td>0.257</td><td>0.182</td><td>0.307</td><td>0.314</td><td>0.213</td><td>0.500</td></tr></table></body></html>

图8表明，与WeChat 相似的App 有7个，按相似度大小排列分别是QQ、Browser、Weibo、JdShop、Youku、Vipshop和 YahooMail。类似地，与Weibo 相似的有Browser、WeChat、JdShop和Youku。其中，形成多个全关联子图，例如：WeChat、Weibo、JdShop 和Browser等。全关联子图的App可划分为一类。若不断将相似阈值提高，则可以找出与某个App 最为相似的 App，帮助提高App 划分的准确率。例如当相似阈值提高到0.32时，仅有WeChat、Browser、Weibo 形成全关联子图，即表示这三个应用最为相似，可建议将它们划分为一个类别。这也意味着，在此实验数据集上，用户在使用WeChat和Weibo方面，更多的表现为浏览行为。

![](images/3a32e559ab873c45867fa6e4a3902f5042843c6ce0caa347846f6f0c88d66df7.jpg)  
图8MAD 数据集上App 相似关联图

# 4 结束语

本文基于多项评估指标，分析K-均值和谱聚类方法在不同特征集合或不同类别标签的移动互联网流量数据集上的聚类性能。实验结果表明，K-均值在App 流量识别方面的性能优于谱聚类，并且单向流特征和双向流特征更适用于App 流量识别。为了综合利用不同角度的特征集合，本文提出基于多个特征集合的集成聚类方法MFEC，提高聚类性能。实验结果表明，MFEC 能进一步提高K-均值的App识别准确率。最后，本文将MFEC方法运用于App相似度分析，分析结果可辅助于用户App上网行为的分析，并为繁杂的App归类提供客观的建议。本文主要对常用的特征集合进行了分析与比较，未来将结合MFEC方法，在移动互联网流量数据集上研究性能更优的特征集合。

# 参考文献：

[1]田旭．互联网流量识别技术研究[D]．北京：北京邮电大学,2012.(Tian Xu.Research on Internet traffic identification technology [D]. Beijing: Beijing University of Posts and Telecommunications,2012.)   
[2]林森，徐鹏，刘琼．基于支持向量机的Internet 流量分类研究[J].计算 机研究与发展,2009,46(3):407-414.(Lin Sen,Xu Peng,Liu Qiong. Trafic classification based on support vector machine [J]. Journal of Computer Research and Development,2009,46 (3): 407-414. )   
[3]Soysal M,Schmidt E G. Machine learning algorithms for accurate flow-based network traffic classification: evaluation and comparison [J]. Performance Evaluation,2010,67 (6):451-467.   
[4]Peng Lizhi, Yang Bo,Chen Yuehui. Effective packet number for early stage internet traffic identification [J]. Neurocomputing,2015,156 (C): 252-267.   
[5]Liu Zhen,Wang Ruoyu,Tao Ming,et al. Aclass-oriented feature selection approach for multi-class imbalanced trafc datasets based on local and global metrics fusion [J]. Neurocomputing,2015,168 (2015): 365-381.   
[6] Zhang Jun,Chen Xiao,Xiang Yang，et al.Robust network traffic classification [J]. IEEE//ACM Trans on Networking，2014，23 (4): 1257-1270.   
[7]Aceto G, Ciuonzo D,Montieri A,et al. Multi-classification approaches for classifying mobile App trafic [J].Journal of Network & Computer Applications,2017,103:131-145.   
[8]Park B,Hong JW,Won YJ. Toward fine-grained traffic clasification [J]. IEEE Communications Magazine,2011,49(7): 104-111.   
[9]Erman J，Arlitt M,Mahanti A.Traffic clasification using clustering algorithms [C]// Proc of ACM SIGCOMM Workshop On Mining Network Data.2006:281-286.   
[10] Bernaille L,Teixeira R,Salamatian K.Early application identification [C]/ Proc of ACM CoNEXT.New York:ACMPress,2006:1-6.   
[11]周文刚，陈雷霆，董仕．基于谱聚类的网络流量分类识别算法[J]．电 子测量与仪器学报，2013，27(12):1114-1119.(Zhou Wengang，Chen Leiting,Dong Shi.Network traffic classification algorithm based on spectral clustering [J]. Journal of Electronic Measurement and Instrument, 2013,27 (12): 1114-1119.)

[12]鲁刚，余翔湛，张宏莉，等．基于集成聚类的流量分类架构[J].软件 学报,2016,27(11): 2870-2883.(Lu Gang,Yu Xiangzhan,Zhang Hongli, et al.Traffic classification framework based on integrated clustering [J]. Journal of Software,2016,27(11):2870-2883.)

[13]何震凯，阳爱民，刘永定，等．一种使用DBSCAN聚类的网络流量分类方法[J].计算机应用研究,2009,26(9):3461-3464.(He Zhenkai,YangAimin,Liu Yongding,etal.Anetwork trafficclassfication methodusingDBSCAN clustering [J]. Application Research of Computers,2009,26 (09):3461-3464. )

[14]Tongaonkar A.A look at the Mobile App Identification Landscape [J]. IEEE Internet Computing,2016,20 (4): 9-15.   
[15]Fu Yanjie, Xiong Hui,Lu Xinjiang,et al. Service usage classification with encrypted internet traffic in mobile messaging Apps [J]. IEEE Trans on Mobile Computing,2016,15 (11): 2851-2864.   
[16]张馨予．基于社团结构的移动互联网流量分析与应用识别[D]．北京: 北京邮电大学,2014.(Zhang Xinyu.Mobile Internet trafic analysis and applicationidentification based on community structure [D].Beijing: Beijing University of Posts and Telecommunications,2014.)   
[17] Tongaonkar A, Keralapura R,Nucci A. Challenges in network application identification [C]// Proc of the 5th USENIX Conferenceon Large-Scale Exploits and Emergent Threats. 2012: 1-3.   
[18]刘珍，王若愚，蔡先发，等．互联网流量分类中流量特征研究[J].计 算机应用研究，2017,34(1):8-14,41.(Liu Zhen，Wang Ruoyu,Cai Xianfa,et al. Survey on traffic features in internet traffic classification [J]. Application Research of Computers,2017,34 (01): 8-14,41. )   
[19] Moore A,Zuev D,Crogan M L.Discriminators for use in flow-based classification [R]. Queen Mary and Westfield College,2005: 1-16.   
[20] Qin Tao,Wang Lei,Liu Zhaoli,et al.Robust application identification methods for P2P and VOIPtraffc classification in backbone networks [J]. Knowledge-Based Systems,2015,82(C): 152-162.   
[21] Dainotti A,Pescape A，Kim H C. Traffic classification through joint distributionsof packet-level statistics[C]//Procof IEEEGlobal Telecommunications. 2011: 1-6.   
[22]Mongkolluksamee S，VisoottivisethV,Fukuda K.Enhancingthe performance of mobile traffic identification with communication patterns [Cl// Proc of Computer Software and Applications Conference.2015: 336-345.   
[23] Liu Zhen,Wang Ruoyu.Mobilegt: A system to collct mobile trafc trace and build the ground truth [C]/ Proc of Telecommunication Networks and Applications Conference. 2017: 142-144.   
[24]王变琴，余顺争．未知网络应用流量的自动提取方法[J].通信学报, 2014，35(07):164-171.(Wang Bianqing，Yu Shunzheng.Unknown Network Application Trafic Automatic Extraction Method [J]. Journal on Communications,2014,35 (7): 164-171. )   
[25] Williams N, Zander S,Armitage G. A preliminary performance comparison offive machine learning algorithms forpractical IP traffic flow classification [J].ACM SIGCOMM Computer Communication Review, 2006, 36 (5): 5-16.