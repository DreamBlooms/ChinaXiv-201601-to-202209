# 移动互联网用户终端换机预测的研究与实现

符静，张治中，陈粵龙(重庆邮电大学 通信网与测试技术重点实验室，重庆 400065)

摘要：为解决预测潜在换机用户的低效率与实际应用问题，设计并搭建基于大数据平台的换机预测系统。该系统首先采集通信网络各接口的数据并收集外部数据；再通过解析处理平台对网络接口数据进行分发、解码、合成、关联等处理，对外部数据进行ETL处理，然后将处理后的数据存入HDFS中；进一步，在大数据平台上应用 Spark组件建立基于逻辑回归的换机预测模型，输出潜在换机用户；最后，选取了某西部城市部分用户数据进行系统测试，所得结果表明，该换机预测系统的预测准确率为 $71 \%$ ，可以较好地识别出潜在换机用户，为运营商及手机制造商的精准营销提供可靠支撑。

关键词：移动互联网；换机预测；逻辑回归；大数据 中图分类号：TN929.5 doi:10.3969/j.issn.1001-3695.2017.12.0781

# Research and implementation of users terminal replacement prediction in mobile internet

Fu Jing, Zhang Zhizhong, Chen Yuelong (Communication Networks Testing Engineering Research Center，Chongqing Universityof Posts&Telecommunications, Chongqing 400065, China)

Abstract: Inordertosolve theloweficiencyandpracticalaplcationofpredicting thepotentialphonereplacementuser,this paper designed and built a phone replacement prediction system basedon big data platform.This system firstly captured signalingdata from multiplenetwork interfaceand collected external data.Through the parseplatform,thedatafromnetwork interfacewoudbstributed,ecoed,sthesedadcoelatedndteexteraldatouldbeprocesdyElsd then storing processd datainto HDFS.Further,the paper establishedaphonereplacement prediction model,whichbasedon logistic regression,using sparkcomponents inthebigdataplatforandoutputthe potential phonereplacementusers.Finally thepaperchosepartofthe westerncity'suserdataforsystem testing.Theresultshows thatthepredictionaccuracyofthephone replacement prediction system is up to $71 \%$ . It can preferably recognize potential phone replacement users,and provide reliable support for the precise marketing of operators and mobile phone manufacturers.

Key Words:mobile internet; replacement prediction; logistic regression; big data

# 0 引言

移动互联网用户在使用手机的过程中产生大量的信息，运营商积累了这些用户的相关信息，如手机机龄、流量使用情况、异常开关机次数等，但在海量信息中，运营商和用户都很难及时交互双方所需要的信息。对于运营商而言，无法知道哪些用户有潜在的换机需求、需求的手机类型及可接受的价位等信息，从而做针对性的销售，即精准化营销[1-2]。对于用户而言，虽然市场上手机种类繁多，但是不知道有哪些手机更适合自己，而且性价比更高。运营商与手机用户之间缺乏有效沟通，因此运营商有必要对用户业务和流量等信息进行全面系统的研究分析以此挖掘出潜在换机用户，这不仅有利于运营商扩大用户市场，增加经济效益，还有利于用户获得更好的体验。

用户终端换机预测是针对运营商数据以及用户上网数据、网络接口采集数据等各类数据，通过数据挖掘方法进行分析，寻找数据间的隐藏关系，从大量终端用户中识别出有换机趋势的用户，便于向潜在换机用户进行精准营销。现有的换机预测研究较少，刘力凯，王国胤，邓维斌[3]利用基于优势关系粗糙集方法对有换机意向的用户进行分类选择；刘畅4基于Cox回归模型研究发现影响终端换机的因素，其结果表明影响用户换机行为的因素包括年龄、性别、终端品牌等；熊冰妍，王国胤，邓维斌5对决策树算法进行改进，并提出了一种基于分级式决策树的换机预测方法；Yang等人l从手机用户使用APP的数据入手，应用生存分析模型预测用户是否换机。

现有换机预测研究多是从理论算法上进行的，且其模型分析的数据仅来源于运营商；而本文提出了基于Hadoop平台的换机预测系统，在Spark组件上应用逻辑回归算法建立换机预测模型,挖掘潜在换机用户。此外，换机预测模型的数据源不仅有运营商的数据，还包括从2/3/4G各网络接口采集的数据。

# 1 换机预测系统设计

为了能够更好的解决用户需求并拓展运营商业务，本文设计并搭建了基于Hadoop平台的换机预测系统。换机预测系统包括数据采集、数据处理、数据挖掘、应用展示等功能模块。基于Hadoop平台的换机预测系统框架如图1所示。

![](images/b850a85208aeedc1ddb6a8e8008f8aa41d2be544a9a8e07146d3a73ebaf70450.jpg)  
图1换机预测系统框架

# 1.1数据采集处理

换机预测的原始数据通过数据采集层获取，主要包括外部数据与信令数据两部分。外部数据包括Boss系统、CRM系统以及经分系统的数据，主要通过ETL进行处理，将外部数据加载到Hadoop 数据仓库中去。信令数据由采集卡等设备实时采集获得，包括Gb、Gn、Iups、S1、Uu等网络接口的数据，再通过解析处理平台对其进行处理，处理后所得数据传送到Hadoop平台。解析处理平台包括数据分发解码、合成CDR、DPI识别、关联出表四个模块，其流程如图2所示。

网络各接 分发 合成 信令面数据 关联 Hadoop  
□数据 解码 CDR 出表 平台业务面 A数据 DPI识别爬虫信息

# 1.1.1数据分发解码

该模块主要完成对所采集网络接口数据的解码功能。首先识别数据类型，判断数据是信令面还是业务面的数据；再根据数据类型的不同分发到相应的解码系统；最后通过解码系统对网络接口数据进行解码，包括关键字段的提取与详细比特内容

的"翻译”。

解码系统根据接口协议栈进行解码，协议栈解码都是从底层依次向上层进行的，识别协议栈的每层协议后，调用相应的解码函数进行解码。下面以S1-U接口数据的解码为例，说明数据解码流程。首先，对于S1-U接口数据，判断数据是否为空，如果不为空，才进行解码；再识别协议栈的最底层协议（IP协议），调用相应解码函数（IP_decodeO）进行解码，IP解码函数如下。

int Ipv4_FDecode(IN const void \* pData,IN const int32   
nBitLen, IN void \* pContext, IN void \* pDetail, OUT SDUINFO   
$^ { * * }$ ppSduInfo) { uint8 \*pDataHea ${ \mathrm { 1 d } } = ( { \mathrm { u i t } }$ nt8 \*)pData; int32 nLength $\ O =$ nBitLen; ...

在底层数据（IP协议数据）解码完成后判断是否存在上层数据(UDP协议数据），如果存在，再根据上层协议调用相应的解码函数（UDP_decodeO）进行解码，依次循环直至解完原始数据；再调用FilITreeBuf函数，构建树型结构，填充解码结果。

# 1.1.2合成CDR

CDR合成模块主要是对数据解码后的结果进行合成，并在内存中记录CDR和原始消息的对应关系，其具体流程如图3所示。

首先从解码结果消息中提取共有关键信息Key；其次，判断Key对应的CDR记录是否存在，如果存在，就从hash表中获取key对应的CDR，并更新CDR属性信息；如果不存在，就建立hash索引和新的CDR记录，并设置CDR属性信息。然后，判断当前消息是否为CDR结束消息，如果不是，后续消息将完善CDR内容；如果是，则移除Key并把完整的CDR传送到出表模块。

![](images/c363624561ca6da281a96f6a7c7e9612f6569bc94a4ef30d255f4fbe03418e92.jpg)  
图2解析处理平台  
图3CDR合成处理流程

# 1.1.3DPI识别与关联出表

DPI识别模块主要是识别用户访问互联网的数据，包括业务类型，如视频、购物、阅读等具体内容，此模块需要爬虫信息库的支持，爬虫信息库中存储爬虫程序爬取的一些信息，主要是各网站的业务关键信息，如视频名称、主演等信息。

该模块的输入是CDR合成文件数据，首先需要加载爬虫信息库，并读取CDR合成文件，再根据IP五元组信息，即源IP 地址，源端口，目的IP地址，目的端口和协议类型来查找业务类型；依次通过爬虫信息库、Host、URL与其他特征来识别业务，成功则填充识别统计表，失败则结束，关键代码如下。

switch(m_arr Level[i]) { case DPI_LEVEL_IP: { if(false $\scriptstyle = = { \mathrm { m } }$ _Check Stat[DPI_LEVEL_IP].Is OkO) { Search Ch Feature(dpi Info,Result Info ,context,DPIText,FEATURE_LEVEL5_IP); }}…. default:break; 3

关联出表主要是为了补充并完善CDR记录，对合成后的业务面CDR 记录中的空缺信息，通过信令面的相互关联信息进行交叉回填，回填后将完整的CDR合成结果以CSV文件格式存盘，实时保存CDR的合成记录，便于上层使用。

# 1.2数据挖掘与应用展示

数据挖掘模块是在Hadoop平台上完成数据导入、统计、分析、预测等功能，其核心是建立相应的数据挖掘模型。应用展示模块的主要功能是对大数据平台处理的数据结果进行展示，根据专题的不同，分为用户换机预测、用户行为分析和用户套餐推荐等。

数据挖掘包括数据准备、数据预处理与数据建模三个阶段，其具体设计如图4所示。

![](images/6c2d098c46a7e529cb74735c5e65619d3ef1bc27c34c8a6de3eac76ab51ed4fd.jpg)  
图4数据挖掘过程

数据准备阶段包括数据导入、宽表建立等工作。对于解析处理平台与ETL处理所得到的各类数据，导入到Hadoop平台的 HDFS中，HDFS 是分布式文件系统[7]，专用于存储各类文件。导入的数据是涵盖通信行为信息、网络行为信息、用户基本属性和用户消费信息等不同维度的数据。然后建立boss、信令等数据基础宽表。

数据预处理是对基础宽表数据进行处理，根据专家经验法提取特征字段，并对字段进行两两相关性分析，去除相关性较大的字段，形成模型的输入字段；进一步，对数据进行数据质量检查、变量转换等标准化处理，得到输入模型的数据宽表。

数据建模主要分为模型选择、模型建立与模型输出三阶段。第一阶段，根据业务目标选择合适的数据挖掘模型，业务目标是实现换机预测系统，因此换机预测模型选择为逻辑回归预测模型。第二阶段，通过数据挖掘算法进行建模，本文基于spark组件建立逻辑回归模型，对数据进行换机预测挖掘。第三阶段，输出换机预测模型结果，即输出潜在换机用户。

# 2 换机预测模型

换机预测模型主要是采用逻辑回归（LogisticRegression）算法[8-在 spark 组件上建立模型。逻辑回归是通过N 个影响因素预测变量发生的概率，多用于二分类情况。本文需要预测的是客户是否为潜在换机用户，是典型的二分类变量（1表示是，0表示否），因此基于逻辑回归算法建立换机预测模型。

逻辑回归算法

逻辑回归的思想也是基于线性回归，属于广义线性回归模型[12-13]。线性回归的公式如(1)所示。

$$
z = \beta _ { 0 } + \beta _ { 1 } x _ { 1 } + \cdots + \beta _ { n } x _ { n } = \boldsymbol { \mathbf { \mathbf { \mathbf { \mathbf { \mathbf { \mathbf { \mathbf \beta } } } } } } } \boldsymbol { \mathbf { \mathbf { \mathbf { \mathbf { \mathbf { \beta } } } } } }
$$

sigmoid函数公式如式(2)所示。

$$
\sigma ( x ) = \frac { 1 } { 1 + e ^ { - x } }
$$

逻辑回归是将线性函数的结果映射到了sigmoid函数中，如式(3)所示。

$$
h _ { \beta } ( x ) = \frac { 1 } { 1 + e ^ { - z } } = \frac { 1 } { 1 + e ^ { - \beta ^ { \operatorname { T } _ { x } } } }
$$

在换机预测应用中，假设给定 $\mathfrak { n }$ 个因素 $\mathbf { x } { = } ( \mathrm { x } 1 , \mathrm { x } 2 , \cdots , \mathrm { x n } )$ 设条件概率 $\scriptstyle \mathrm { P = P ( y = 1 | x ) }$ 为换机事件y相对于因素 $\mathbf { x }$ 发生的概率，用Logistic函数表示为

$$
\begin{array} { l } { P = h _ { \beta } ( x ) = \displaystyle \frac { 1 } { 1 + e ^ { - \beta ^ { \mathrm { T } _ { x } } } } } \\ { = \displaystyle \frac { 1 } { 1 + e ^ { - ( \beta _ { 0 } + \beta _ { 1 } x _ { 1 } + \beta _ { 2 } x _ { 2 } + \cdots + \beta _ { n } x _ { n } ) } } } \\ { = \displaystyle \frac { e ^ { \beta _ { 0 } + \beta _ { 1 } x _ { 1 } + \beta _ { 2 } x _ { 2 } + \cdots + \beta _ { n } x _ { n } } } { 1 + e ^ { \beta _ { 0 } + \beta _ { 1 } x _ { 1 } + \beta _ { 2 } x _ { 2 } + \cdots + \beta _ { n } x _ { n } } } } \end{array}
$$

根据式(4)，可建立换机预测模型。其中，P表示用户换机的概率，x1、x2、、xn 表示换机的影响因素如手机品牌，上网天数，平均流量等。

# 2.1逻辑回归模型工作流程

逻辑回归模型工作流程主要包括模型训练与模型预测两个阶段，具体流程如下。

1）模型训练流程

a)对选取的训练数据集进行数据预处理，包括对数据样本的去噪、剔重和筛选。

b)通过相关性分析得到对模型预测结果影响显著的变量，并将其作为模型最终的输入变量。

c)训练数据集利用逻辑回归的fit(方法生成逻辑回归模型。

2)模型预测流程

a)针对测试数据集进行数据预处理，并选取对预测结果影响显著的变量输入模型，该模型为经过训练数据集所生成的逻辑回归模型。

b)调用训练后的逻辑回归模型的transform(方法对测试数据进行分析，输出潜在换机用户。

c)输出并保存预测结果。

# 3 换机预测的实现与应用

换机预测系统是基于Hadoop平台实现的，其数据预处理过程包括数据字段提取，标准化处理等，主要是在Hive上完成，而换机预测模型的建立、预测等工作主要是在Spark 组件上完成。

# 3.1数据准备阶段

原始数据集O包括外部数据和信令数据，涵盖通信行为信息、网络行为信息、用户终端信息、用户属性信息、用户消费信息、boss、经分信息等多维度数据，共146字段。表1展示了原始数据集O的字段信息，由于字段较多，只选取部分展示。

表1原始数据集字段信息  

<html><body><table><tr><td rowspan="2">用户终端信息</td><td>终端品牌</td><td>IMEI在网月数</td></tr><tr><td>终端网络类型</td><td></td></tr><tr><td rowspan="2">用户消费信息</td><td>当月消费</td><td>漫游通话费</td></tr><tr><td>最近三个月平均消费</td><td></td></tr><tr><td rowspan="2">通信行为信息</td><td>通话常驻区县</td><td>通话常驻区域</td></tr><tr><td>通话常驻片区 (分局)</td><td></td></tr><tr><td rowspan="2">网络行为信息</td><td>上网套餐</td><td>视频流量</td></tr><tr><td>上网叠加套餐</td><td></td></tr><tr><td></td><td></td><td></td></tr></table></body></html>

由表1可知，原始数据集O涵盖了不同维度的字段信息，也是换机预测模型的数据源。在系统实现过程中，需要建立boss、信令等数据宽表，存储于HDFS中，作为模型输入的数据基础宽表。

# 3.2 数据预处理阶段

# 3.2.1特征字段提取

原始数据集O所含字段较多，其中有些字段与换机预测关联较小，因此需要对宽表数据进行特征字段提取，留下可能对换机产生影响的变量字段。根据经验法，从BOSS、信令等宽表中筛选出17个相关特征变量字段，包括手机号（usr_nbr）、手机品牌（phone_brand）、当月流量（gprs_flux）、三个月平均流量（flow_avg3）、4g流量（flow_4g）等字段。

# 3.2.2相关性分析

相关性分析即对提取字段进行两两间的相关性分析，本文借助了spass statistics工具，对所有字段做双变量相关性分析，采用 pearson 相关系数算法，所得相关性分析结果部分如表 2所示。

从表2中可以看出，gprs_flux与flow_avg3字段的相关系数为0.819，gprs_flux与flow_4g字段相关性系数为0.963，flow_4g与flow_avg3字段的相关系数为0.863，相关性较大，当两字段相关系数大于0.8时，选取其中一个作为模型的输入，因此模型输入字段去掉 gprs_flux与flow_avg3字段。

# 3.2.3数据标准化处理

数据标准化处理先把非数值型数据进行转换，再对数据进行归一化处理。本文对于模型各输入字段处理方法不同，如对于市场细分（segment_type），将城区的转换为1，其他的转换为0；上网天数（gprs_days）为空的转换为0；针对手机品牌（phone_brand）字段，取值范围为0至20，即苹果、欧珀、步步高、华为、MIUI、三星、联想、金立、诺基亚等手机终端品牌从20至1依次递减排序，当字段内容不属于top20的品牌，或手机品牌字段为空时都转换为0。

表2部分相关性分析结果  

<html><body><table><tr><td>相关性分析</td><td>usr_nbr</td><td>phone_brand</td><td>gprs_flux</td><td>flow_avg3</td><td>flow_2g</td><td>flow_3g</td><td>flow_4g</td></tr><tr><td>usr_nbr</td><td>1</td><td>0.327</td><td>0.197</td><td>0.028</td><td>0.108</td><td>0.282</td><td>0.239</td></tr><tr><td>phone_brand</td><td>0.327</td><td>1</td><td>0.206</td><td>-0.018</td><td>0.253</td><td>0.095</td><td>0.086</td></tr><tr><td>gprs_flux</td><td>0.197</td><td>0.206</td><td>1</td><td>0.819</td><td>0.157</td><td>0.036</td><td>0.963</td></tr><tr><td>flow_avg3</td><td>0.028</td><td>-0.018</td><td>0.819</td><td>1</td><td>0.568</td><td>0.264</td><td>0.863</td></tr><tr><td>flow_2g</td><td>0.108</td><td>0.253</td><td>0.157</td><td>0.568</td><td>1</td><td>0.237</td><td>0.197</td></tr><tr><td>flow_3g</td><td>0.282</td><td>0.095</td><td>0.036</td><td>0.264</td><td>0.237</td><td>1</td><td>0.149</td></tr><tr><td>flow_4g</td><td>0.239</td><td>0.086</td><td>0.963</td><td>0.863</td><td>0.197</td><td>0.149</td><td>1</td></tr><tr><td>innet_months</td><td>0.182</td><td>0.156</td><td>0.065</td><td>0.238</td><td>0.234</td><td>0.438</td><td>0.451</td></tr></table></body></html>

数据归一化处理是为了消除指不同量纲间对数据分析结果的影响，其处理方法为：新数据 $\ c =$ （原数据-均值）/标准差。以在网月数（innet_months）与市场细分（segment_type）为例，归一化处理的代码如下：

(nvl(a.innet_months,O)-b.avg_innet_months) /b.stddev_innet_months innet_months, (nvl(a.segment_type,0)-b.avg_segment_type) /b.stddev_segment_type segment_type ,

# 3.3 数据建模实现

数据建模是在Hadoop平台 spark 组件上实现的，其主要建模实现步骤如下：

a）加载训练数据traindata，其路径为"user/test/train201706.csv"，并设置分割符以及划分属性列和标识列。

b)建立逻辑回归对象val $\operatorname { l r } =$ newLogisticRegression()。

c)重新设置逻辑回归对象参数lr.setMaxIter(10).setRegParam(0.01)，最大迭代次数10，正则化参数0.01。

d)训练模型。根据设定的模型参数，调用逻辑回归的fit(方法拟合训练得到模型model2，可以通过模型model2预测用户是否换机。

e）加载测试数据testdata，其路径为"user/test/unchanges201707.csv”，并设置分割符以及划分属性列和标识列。

f)调用预测模型 model2 的 transform(方法，对测试数据testdata进行换机预测。

g)测试数据testdata通过预测模型后得到预测结果，输出保存至res.csv 文件中。

模型实现的关键代码如下：

valtraindata $\mathbf { \Sigma } =$ sc.textFile("/user/test/train201706.csv")

val training $\mathbf { \Sigma } =$ sqlContext.createDataFrame(.....).toDF("label",   
"features") val $\operatorname { l r } =$ new LogisticRegression() lr.setMaxIter(10).setRegParam(0.01) val model2 $\ O =$ lr.fit(training, paramMapCombined) val testdata $\scriptstyle 1 = \sec$ .textFile("/user/test/unchanges201707.csv") val res=model2.transform(test).select("isdn","features",   
"myProbability","prediction") res.save(path $\scriptstyle 1 = 1$ '/user/test/res",source $\mathrel { \mathop : } =$ "json")

# 3.4结果分析

在换机预测模型完成之后，本文选取了某西部城市2017年7月部分用户数据进行系统测试，测试对象为200000名未换机用户，将该数据导入换机预测系统后得到结果如表3所示，其中， ${ } ^ { \cdot \cdot } 1 3 4 ^ { * * * * } 4 7 6 3 ^ { \cdot }$ ”是用户号码，“b"代表预测用户是潜在换机用户，“a"代表预测用户为非潜在换机用户。

表3换机预测模型结果  

<html><body><table><tr><td>134****4763</td><td>b</td></tr><tr><td>134****6829</td><td>b</td></tr><tr><td>134****0019</td><td>a</td></tr><tr><td></td><td></td></tr></table></body></html>

通过换机预测模型后，得到预测结果，进一步，利用大数

据平台统计潜在换机用户人数，关键代码如下： ---14002 select count(a.usr_nbr) from cyhcmc_temp.hj_jychange_test   
a,hj_change_201707 b where a.usr_nbr $\mathbf { \Sigma } =$ b.usr_nbr and $\mathbf { a } . \mathbf { f l a g } = \mathbf { \bar { b } ^ { \prime } }$ · ---19720 select count(a.usr_nbr) from cyhcmc_temp.hj_jychange_test a wherea $. \mathrm  { f l a g } = \{ b ^ { \prime }$ ·

从统计结果可以看出，待测试200000名用户中，预测所得潜在换机用户数为19720，其中有14002用户是与实际相匹配的，实际上7月份换机用户数为18216，预测准确率为$1 4 0 0 2 / 1 9 7 2 0 { = } 7 1 \%$ 。系统测试中，从开始数据处理到最终模型完成预测共花费时间约 $5 . 3 \mathrm { s } _ { \mathrm { { c } } }$ ，现有换机预测研究准确率多为 $6 8 \%$ $74 \%$ 左右，本文实现的换机预测系统准确率与现有研究相当，但相比于传统仿真或理论研究的实现方式，该换机预测系统性能有较高的提升，可及时预测出潜在换机用户。该西部城市运营商针对该换机预测系统测预测的潜在用户，进行了精准营销，成功营销人数达5248，成功营销率为 $5 2 4 8 / 1 9 4 5 7 { = } 2 7 . 0 \%$ ，相比于该西部城市运营商之前随机抽取用户 $4 \% \sim 5 \%$ 的营销成功率有了更大的提升。

由运营商实际成功营销数据表明，该换机预测系统可以预测出潜在的换机用户，运营商仅仅对潜在换机用户实施精准营销，从人力投入方面降低了营销成本，并且最终提高手机终端的营销成功率。此外，该换机预测系统还可以掌握用户终端使用的行为习惯、换机前后的消费变化，结合用户消费行为数据，为后续其他业务（如套餐推荐）提供参考。

# 4 结束语

本文从理论与实际结合的角度研究换机预测，并应用Hadoop平台上的Spark组件实现了换机预测系统，能较好的识别出潜在的换机用户。但换机预测模型仍然存在一些问题，例如选取特征字段的方法是借助专家经验法，可能会忽略一些影响换机预测的其他字段；模型的预测结果与实际结果仍存在一些误差，可能是用户是否换机会受到一些偶然因素的影响。在接下来的研究中，会尝试用聚类算法选取相关特征字段，进一步提高换机预测模型的准确率。

# 参考文献：

[1]Ma J,Zhao S,Ma J,et al.Research on precision marketing data source system based on big data [J].International Journal of Advanced Media& Communication,2017,7(2): 93.   
[2]You Z, Si Y W, Zhang D,et al.A decision-making framework for precision marketing[J].Expert Systems with Applications,2015,42(7): 3357-3367.   
[3]刘力凯，王国胤，邓维斌．优势关系粗糙集的移动用户换机预测方法 [J].小型微型计算机系统,2015,36(8):1789-1794.   
[4]刘畅．基于CoX 回归模型的用户终端换机研究[J].电子科学技术， 2016,3(4):418-421.   
[5] 熊冰妍，王国胤，邓维斌.分级式代价敏感决策树及其在手机换机预测 中的应用[J].山东大学学报：工学版,2015,45(5):36-42.   
[6]Yang D,Wu Z,Wang X,et al. Predicting replacement of smartphones with mobile app usage[C]//Proc of International Conference on Web Information Systems Engineering.[S.1.] : Springer International Publishing,2016: 343- 351.   
[7]Ghazi MR,Gangodkar D.Hadoop,MapReduce and HDFS:a developers perspective [J].Procedia Computer Science,2015,48: 45-50.   
[8]Edition S.Applied logistic regression analysis [J]. Technometrics,2017,38 (2):184-186.   
[9]Wallenstein S,Hodge S E,Weston A.Logistic regression model for analyzing extended haplotype data [J].Genetic Epidemiology,2015,15 (2): 173-181.   
[10] Zhang Z. Model building strategy for logistic regression: purposeful selection.[J].Annals of Translational Medicine,2016,4(6): 111.   
[11] Zhang S,Zhang L,Qiu K,et al.Variable selection in logistic regression model[J].Chinese Journal of Electronics,2015,24 (4): 813-817.   
[12] Olive DJ.Linear regression analysis [J]. Technometrics,2014,45 (4): 362- 363.   
[13] Abuella M, Chowdhury B.Solar power probabilistic forecasting by using multiple linear regression analysis [C]//Proc of Southeastcon.2O15:1-5.