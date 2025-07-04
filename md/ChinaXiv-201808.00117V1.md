# 基于MF-R和AWS密钥管理机制的物联网健康监测大数据分析系统

臧艳辉」，赵雪章‘，席运江²(1．佛山职业技术学院，广东 佛山 528137;2．华南理工大学，广州 510000)

摘要：带有传感器的可穿戴式医疗设备不断生成大量数据，由于数据的复杂性，难以通过处理和分析大数据来找到有价值的决策信息。为了解决这个问题，提出了一种新的物联网体系结构，用于存储和处理医疗应用的可扩展传感器数据（大数据)。所提出的架构主要由两个子架构组成：MetaFog重定向（MF-R）架构和AWS密钥管理机制。MF-R架构使用Apache Pig和 Apache HBase 等大数据技术来收集和存储不同传感器设备生成的传感器数据，并利用卡尔曼滤波消除噪声。AWS 密钥管理机制使用密钥管理方案，目的是保护云中的数据，防止未经授权的访问。当数据存储在云中时，所提出的系统能够使用随机梯度下降算法和逻辑回归来开发心脏病的预测模型。仿真实验表明，与其他几种算法相比，提出的算法具有更小的误差，且在吞吐量、准确度等方面具有一定的优越性。

关键词：无线传感器网络；物联网；大数据；卡尔曼滤波；云计算；AWS密钥管理机制中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.05.0275

# IoT health monitoring big data analysis system based on MF-R and AWS key management mechanism

Zang Yanhui1, Zhao Xuezhangl,Xi Yunjiang² (1.FoshanPolytechnic,Foshan Guangdong 528137,China;2.SouthChina UniversityofTechnology,Guangzhou510641, China)

Abstract:Wearable medical devices with sensorcontinuouslygenerate enormous data,due tothecomplexityof thedata,itis diicult to processandanalyze thebigdata for finding valuable information thatcanbeuseful in decision-making.Inorderto overcome this issue,this paper proposedanew architecture forthe implementationofIoTto storeand processcalable sensor data(big data)for healthcare applications.The proposed architectureconsistedof two main sub architectures,namely,Meta Fog-Redirection (MF-R)andAWS keymanagement mechanism.MF-Rarchitecture usedbigdatatechnologies suchas Apache Pig and Apache HBase for collection and storageofthe sensordata generated from diferentsensordevices and it also used kalman filter for removal of noise.AWS key management mechanismused a key management scheme to protect data in the cloud and preventunauthorized access.When data wasstored inthe cloud,theproposed systemcoulduse stochastic gradient descent algorithmsand logistic regresion to develop a predictive modelof heart disease.Simulation experiments show that compared withother algorithms,the proposed algorithmhassmaller erorandithascertain advantages in termsofthroughput and accuracy.

Key words:Wirelessensor network; Internetof Things;Big data; Kalman filter; Cloud computing;AWS key management mechanism

# 0 引言

物联网（Internetofthings，IOT）[1]是物理对象与用于收集和交换数据的网络连接而成的，物联网的发展使得传感器的应用越来越广泛[2]。例如，使用可穿戴式传感器装置，对患者进行周期性的连续生理监测，可以给出生理运动和饮食习惯建议。在此期间，可穿戴式传感器将持续获取患者的健康数据，并将其存储[3]，这有助于医生诊断患者的健康状况。在基于IOT的医疗健康应用中，“大数据”起着至关重要的作用[4]。现代医疗保健系统通常采用临床数据以增加在线可用的临床记录。此外，在IOT大数据分析中，通常借助于云计算5和雾计算以提高效率，并减少需要从物理设备传输到云端的数据量[7,8]。科研人员针对IOT医疗系统做出了许多改进，Jee和Kim描述了基于大数据分析的医疗系统改进方式，以改善医疗系统，选择适当的治疗方式[9,10]。弗吉尼亚大学开发了Alarm-Net架构，用于监控患者健康状况[1I]。该框架有三层架构，第一层使用 BP传感器和ECG（心电图）传感器监测患者的生理状况。第二层架构用于观察环境参数，如灰尘、热量、运动和光线等。第三层通过使用无线通信协议和网络架构将原始观测信号传输到目的地[12]。本文提出了一种新的物联网体系结构来存储和处理医疗应用的传感器数据。提出的架构包括MetaFog重定向（MF-R)架构和AWS密钥管理机制两部分。其中，MF-R架构主要用于收集和存储传感器数据，并利用卡尔曼滤波消除噪声。AWS 密钥管理机制使用密钥管理方案以保护云中的数据，防止未经授权的访问。

# 1融合MF-R 和AWS 密钥管理机制的大数据分析系统

本文提出一种新的架构系统，用于存储和处理医疗保健应用中可扩展的传感器数据（大数据)。在图1中，描绘了各种设备物体之间的连接通信。

![](images/a85099d056504b9f750e6a36bceb085d58bd431813ba45b4fcd8f1d9c6878c87.jpg)  
图1医疗物联网中物与物之间的通信

# 1.1 MF-R架构

所提出的架构由三个不同阶段组成：数据收集阶段、数据处理传输阶段和大数据存储阶段。

a）数据收集阶段，用于持续监测患者的健康状况。因此，当呼吸频率、心率、血压、体温和血糖超过正常值时，设备通过雾计算使用无线网络向医生发送具有临床数据的警报消息。在数据收集阶段，通过雾计算收集的传感器数据与云连接，以便传输并存储到数据库中。

b）在数据处理传输阶段，所提出的架构使用"s3cmdutility”方法将临床数据移入AmazonS3。医疗机构使用亚马逊云中的EC2来存储患者的传感器数据（生理数据)。但是，此传感器数据集在AmazonEMR中不可用，因为传感器数据仅存储在运行EC2 实例的本地磁盘上。因此，必须把它转移到 EMR。AmazonEMR 在云中提供Hadoop 服务来处理大数据[13]。

c）通常情况下，在Amazon S3 中存储大量数据是不可能的[14]。为了解决这个问题，所提出的架构在数据存储阶段使用ApachePig将大量的传感器数据（临床数据）从AmazonS3传输到ApacheHBase，如图2所示。

![](images/6c33aa52e3ad57ca1892026a99f3b161b2053e0db772dada6f8b8b08a376cd2b.jpg)  
图2物联网大数据生态系统架构

# 1.1.1数据收集阶段和处理传输阶段

将从雾计算中收集的传感器数据传输并存储到数据库中。所提出的架构将数据移入AmazonS3，通过AmazonEMR访问。

本文通过应用数据过滤来提高数据处理效率，卡尔曼滤波器(Kalmanfilter，KF)用于在提出的框架中执行数据过滤[15]。KF是一个最优估计器，它可以从感测数据中去除噪声。算法表示如下所示。它最初假定当前状态 $f _ { k }$ 是从先前状态 $f _ { k - 1 }$ 发展而来的。当前状态观察由 $h _ { \boldsymbol { k } }$ 表示。 $\hat { f } _ { k | k - 1 }$ 表示时间 $k$ 处的 $f$ 的估计，而估计精度由 $G _ { k | k - 1 }$ 表示。KF 有助于以最小的内存消耗进行处理。

<html><body><table><tr><td>KF原理</td></tr><tr><td>1 初始化</td></tr><tr><td>Tk-状态转换模型(应用到上一状态f-1)</td></tr><tr><td>Ok-观察模型</td></tr><tr><td>Qk-过程噪音的协方差</td></tr><tr><td>Rk-观察噪音的协方差</td></tr><tr><td>Tk-控制输入模型(应用到控制向量Vk)</td></tr><tr><td>Wk ~(0,Qk)</td></tr></table></body></html>

2 使用上一状态 $f _ { k - 1 }$ 计算新的状态 $f _ { k }$

$$
\begin{array} { l } { f _ { k } = T _ { k } f _ { k - 1 } + C _ { k } \nu _ { k } + w _ { k } } \\ { h _ { k } = o _ { k } f _ { k } + u _ { k } } \\ { u _ { k } \sim \left( 0 , R _ { k } \right) } \end{array}
$$

3 从上一状态得到的当前状态评估评估的状态

$$
\hat { f } _ { k | k - 1 } = T _ { k } \hat { f } _ { k - 1 | k - 1 } + c _ { k } \nu _ { k }
$$

预测的协方差

$$
G _ { k | k - 1 } = T _ { k } G _ { k - 1 | k - 1 } T _ { k } ^ { T } + Q _ { k }
$$

4 联合当前预测和当前观测方程

当前观测方程

$$
\tilde { x } _ { k } = h _ { k } - O _ { k } \hat { f } _ { k | k - 1 }
$$

观测协方差方程

$$
S _ { k } = O _ { k } G _ { k | k - 1 } O _ { k } ^ { T } + R _ { k }
$$

最佳增益

$$
K _ { k } = G _ { k | k - 1 } O _ { k } ^ { T } S _ { k } ^ { - 1 }
$$

通常，AmazonEMR 处理存储在Amazon S3或HDFS存储中的数据。有必要为存储数据的AmazonS3提供全球唯一的名称。每个Amazon S3 都有一个唯一的URL命名约束，来与其余AmazonS3交互。通常，有多种方法可将数据加载到AmazonS3 中。本文所提出的架构使用"s3cmdutility"方法将数据移入AmazonS3。S3cmd负责上传、检索和管理云存储服务提供商的数据，这是一个适用于S3批处理脚本和自动备份的命令执行程序。

# MetaFog重定向架构

处理审计日志文件，以检查登录用户的详细信息，比如他/她/AI机器的轨迹状态等。1 选择患者编号patient_id，密码password，地理位置geolocation，患者名字 patient_name，患者住址 patient_address，系统日期 sysdate;2 如果有任何恶意用户试图登录应用程序3 执行4 插入更新威胁值Threat_updated（patient_id，password,geolocation，patient_name，patient_address，sysdate）；5 返回-1;6否则7 列表1=从Meta数据存储云中选择数据存储供应商名字、数据范围，其中登录应用程序的客户 $\operatorname { I d } = ?$ ；8结束9 如果数据存储供应商名字 $\scriptstyle : =$ “Fog_Sever_1"并且数据范围 $= ^ { \mathfrak { c } }$ 临界")10 执行11 转到：Fog_Sever_DB_112 从Fog_Sever_DB_1中选择\*，其中登录应用程序的患者Id=？13 结束14 如果数据存储供应商名字 $\scriptstyle . =$ “Fog_Sever_2"并且数据范围=“敏感”15 执行16 转到：Fog_Sever_DB_217 从Fog_Sever_DB_2中选择\*，其中：登录应用程序的患者$\scriptstyle { \mathrm { I d } } = ?$ （2018 如果数据存储供应商名字 $\scriptstyle . = ^ { \prime }$ “Fog_Sever_3"并且数据范围 $\scriptstyle = ^ { \prime }$ “正常”19 执行20 转到：Fog_Sever_DB_321 从Fog_Sever_DB_3中选择\*，其中：登录应用程序的患者Id =？22结束

接下来使用mb选项创建一个名为clinical-emr的新存储，使用“s3cmdput"将传感器数据移入AmazonS3。

# 1.1.2大数据存储阶段

AmazonEMR提供了多种方法将大数据传送到集群中，可以将数据上传到AmazonS3，然后使用AmazonEMR的内置功能将数据加载到HBase 集群中。所提出的架构使用Apache Pig将传感器数据从Amazon S3传输到HBase，HBase 是一个可扩展的分布式数据库，可以以分布式方式存储大量行和列，并可供集群中的所有节点使用，HBase 遵循列式数据库存储。ApachePig是分析大量数据的一个平台，将数据表示为数据流。PigLatin是一种脚本语言，用于ETL（提取、转换和加载）过程以及对结构化、半结构化或非结构化数据的adhoc数据分析。所提出的架构使用ApachePig将新的增量临床数据与以前的数据结合到HBase中。

# 1.2基于AWS密钥管理机制的安全服务

为了保证雾计算和云计算之间的安全服务，在本文提出的框架中使用了AWS密钥管理机制和AWSCloudTrail。AWS密钥管理机制能够让用户安全、快捷的使用加密密钥。该机制在AmazonS3、EBS等AWS服务中已被广泛应用；此外，该机制还被应用在AWSCloudTrail中，以方便用户更好的使用密钥管理服务，同时将用户日志记录下来并将其传输到Amazon$\mathbf { S } 3 ^ { [ 1 6 ] }$ 。重定向体系结构如图3所示。所提出的安全框架，可防止在尝试登录到云应用程序时发生未经授权的访问。

![](images/9449a59602e146ef14e21ab6e51ecf531bd4c01f76bf4dd440f6bacf087ee591.jpg)  
图3重定向体系安全框架

# 1.2.1雾计算到云计算

科研人员把雾计算定义为云计算的延伸。使用雾计算改善的新兴网络范例，具有较少延迟和抖动。雾计算也被称为雾网络，用于分配云中计算资源和应用服务。雾计算的主要目标是提高可扩展性、效率并减少需要传输到云中进行数据分析、处理和存储的数据量。在雾计算环境中，数据处理总是在移动设备的数据中心或网关、智能路由器的网络边缘进行。

在本文体系结构中，可穿戴传感器设备将健康数据传输到雾服务器。雾服务器采用近边缘技术，将智能医疗应用中的健康监测设备连接起来。边缘计算在雾计算的安全性、保密性和系统可靠性方面发挥着至关重要的作用。近边缘技术的主要目标是减少传输每一比特通过云通道所需的带宽量。雾计算遵循网络边缘技术，因此从可穿戴医疗设备收集数据需要花费的时间更少了。在本文中，MetaFog重定向结构根据数据分类（敏感、临界和正常)将健康数据重定向到不同的雾服务器。另外，该体系结构执行以下功能：安全性和日志文件处理，以防止来自恶意用户和未经授权用户的数据入侵。

# 1.2.2把雾计算安全集成到云计算

云计算安全由策略和基于控制的技术组成，旨在保护与云计算相关的数据、应用程序、信息和基础架构。在本文所提出的架构中，当把雾集成到云环境时，安全性是主要问题。所提出的安全架构使用安全术语作为公钥和私钥、加密和解密，加密身份访问管理和PKI证书授权来保护云中的数据和应用程序。

# 1.2.3逻辑回归随机梯度下降的MapReduce实现

所提出的物联网数据监测系统使用基于MapReduce的随机梯度下降与逻辑回归来开发预测模型。该预测模型使用ApacheHBase中提供的数据。该逻辑回归使用现有数据来开发预测模型。使用MapReduce 实现基于SGD 的逻辑回归，如下所示：

输入： $n$ 个临床记录集合 $V = \left\{ \left( a _ { i } \in R ^ { d } ; b _ { i } \in R \right) \right\} _ { i = 1 } ^ { n } ; \theta ^ { t } \in R ^ { d } \mathrm { ~ }$ （ 为 $t$ 时刻的权重; $n$ 是学习速率。

输出： $\boldsymbol { \theta } ^ { ( t + 1 ) } \in { \boldsymbol { R } } ^ { d }$ ，为 $\left( t + 1 \right)$ 时刻的权重。

# MAP 算法

# classMAPPER

method INITIALIZE   
double $\theta = 1$ ·   
double $n { = } 0 . 1$ ·   
#key $k$ ;value $\nu$ ·   
method MAP(string $k$ ;double $\nu$ ）； 执行 $\left( a _ { i } ; b _ { i } \right) = \left( k ; \nu \right)$ r=rand( #number of reducer EmithIntermediate $\left( r ; \left( a _ { i } ; b _ { i } \right) \right)$

结束

# Reduce 算法

# classREDUCE

#key $k$ ;value $\nu$ · method REDUCE (string k ; double v[1;2;.;r])

执行

$$
\begin{array} { c } { { k ^ { \theta ^ { \left( t + 1 \right) } } = \theta ^ { t } : } } \\ { { \ } } \\ { { \triangleq \left( a _ { i } ; b _ { i } \right) \in \nu \left[ 1 ; 2 ; \cdots ; r \right] \mathbb { H } ^ { } , } } \\ { { \ } } \\ { { k ^ { \theta ^ { \left( t + 1 \right) } } = k ^ { \theta ^ { \left( t + 1 \right) } } - n \nabla F \left( k ^ { \theta ^ { \left( t + 1 \right) } } \right) ; } } \end{array}
$$

结束

返回(string $k$ ; double $k ^ { \theta ^ { ( t + 1 ) } } )$ ：

结束

$n$ 个临床记录集合 $V = \left\{ \left( a _ { i } \in R ^ { d } ; b _ { i } \in R \right) \right\} _ { i = 1 } ^ { n }$ 每台机器接受 $M$ 个存储块。

其中： $M = { \frac { \left| V \right| } { m } }$ 在 MapReduce 框架中， $M$ 由映射器自

动分配[17]。最终权重 $\boldsymbol { \theta } ^ { ( t + 1 ) }$ 和权重 $\boldsymbol { \theta } ^ { ( t + 1 ) }$ 的平均值可以用$\theta ^ { ( t + 1 ) } { = } \frac { 1 } { M } \sum _ { k = 1 } ^ { M } k ^ { \theta ^ { ( t + 1 ) } }$ 来定义。

# 2 结果分析

把从各种传感器设备收集而来的数据分类为敏感数据、临界数据和正常数据，然后将分类结果存储在各种表格中（表1\~5)。假设患者的临床参数是临界数据，所有临界数据存储在表1中。表2描述了患者的个人数据，其中包括姓名、年龄、性别和地址；表3描绘了正常患者的数据，包括患者ID、性别和年龄;表4描述了数据中心的详细信息，包括数据中心名称、位置及其类别（临界、敏感、正常)；表5描述了日志文件，并

<html><body><table><tr><td colspan="4">存储了与入侵者或未经授权访问有关的信息。</td></tr><tr><td colspan="4">表1患者的临床参数 编号 患者临床参数</td></tr><tr><td>C101</td><td>体温</td><td colspan="2">波士顿</td></tr><tr><td>T202</td><td>心率</td><td colspan="2">亚特兰大</td></tr><tr><td>S301</td><td colspan="3">血糖</td></tr><tr><td colspan="4">新德里 表2患者的个人资料</td></tr><tr><td>编号</td><td>名字</td><td>性别 年龄</td><td>位置</td></tr><tr><td>A231</td><td>Albert</td><td>47</td><td>那格浦尔</td></tr><tr><td>D342</td><td>男 David</td><td>58</td><td>班加罗尔</td></tr><tr><td>C352</td><td>女 Hendry 女</td><td>39</td><td>纽约</td></tr><tr><td colspan="4">表3 正常患者的数据</td></tr><tr><td>编号</td><td>性别 年龄</td><td></td><td>位置</td></tr><tr><td>A231</td><td>男</td><td>45</td><td>澳大利亚</td></tr><tr><td>D342</td><td>女</td><td>60</td><td>加拿大</td></tr><tr><td>C352</td><td>女</td><td>39</td><td>韩国</td></tr><tr><td colspan="4">表4 数据中心</td></tr><tr><td>数据存储供应商</td><td>数据中心位置</td><td>数据范围</td><td>患者编号</td></tr><tr><td>亚马逊</td><td>波士顿</td><td>临界</td><td>C101</td></tr><tr><td>谷歌</td><td>纽约</td><td>敏感</td><td>C352</td></tr><tr><td>微软</td><td>加拿大</td><td>正常</td><td>D342</td></tr><tr><td colspan="4">表5有关入侵者的信息</td></tr><tr><td>编号</td><td>地理位置</td><td>IP地址</td><td>日期和时间</td></tr><tr><td>C101</td><td>美国 10.10.142.107</td><td></td><td>12-1-2015: 14:23:03</td></tr><tr><td>T202</td><td>亚特兰大</td><td>12.11.112.108</td><td>14-1-2015: 14:23:03</td></tr><tr><td>D342</td><td>澳大利亚</td><td>11.10.122.182</td><td>12-1-2015: 14:43:08</td></tr><tr><td>X112</td><td>英国</td><td>22.11.111.107</td><td>22-1-2015: 14:23:05</td></tr><tr><td>N843</td><td>印度</td><td>12.10.146.162</td><td>14-1-2015:15:23:07</td></tr></table></body></html>

根据不同临床参数值的CPU使用情况对所提出系统的性能进行分析。通过定量评估，获得从物联网传感器设备接收各种临床参数的时间间隔。图4表示从IoT传感器设备获得临床参数的不同数据集时，各种CPU的使用情况。图5表示使用MapReduce 实现逻辑回归的性能评估。

![](images/45dcb307684483b63e90541f85d316615dedecebb8ebeee58472eb6c26f876f5.jpg)  
图4在不同临床参数采样率下的CPU使用情况

![](images/973fe7917be7260891ddf9027ece06d230e90d06ef2bb04cd1ea393501c366ba.jpg)  
图5性能评估

# 3 性能评估

本文所提出的基于物联网的健康监测系统使用随机梯度下降算法和逻辑回归来开发心脏病的预测模型。从CHDD据库收集先前的临床记录和患者的传感器数据。在此过程中，健康监测系统通过云和大数据技术，使用由身体传感器设备获取的当前传感器数据。预测分类表如表6所示。所提出基于MapReduce的预测模型的性能分析如表7所示。所提出的心脏病预测模型能够对心脏病进行有效的分类，训练样本和验证样本的准确度分别为 $74 . 3 9 \%$ 和 $73 . 9 2 \%$ 。在灵敏度、特异度、精度、召回率和F均值这些指标的帮助下，评估预测模型的性能；这些指标的定义如下：

真正(TP)灵敏度=真正 $\left( T P \right) +$ 假负 $\overline { { \left( F N \right) } }$ 真负(TN)特异度=假正 $\left( F P \right) +$ 真负 $\overline { { \left( T N \right) } }$ 准确度 $= { \frac { \left( T P \right) + \left( T N \right) } { \left( T P \right) + e \left( F N \right) + \left( F P \right) + \left( T N \right) } }$ 精度 $= { \frac { { \underset { \mathrm {  ~ \scriptstyle { \box E } ~ } } {  } } { \mathrm {  ~ \scriptstyle { \mathbb { E } } ~ } } { \mathrm {  ~ \scriptstyle { \mathbb { E } } ~ } } } { \mathrm { \exists ~ } { \mathrm {  ~ \scriptstyle { \mathbb { E } } ~ } } ( T P ) + { \mathrm { \sf \sf { H E } } } { \mathrm {  ~ \scriptstyle { \mathbb { E } } ~ } } ( F P ) } }$ 真正 $( T P )$ 召回率=真正 $\left( T P \right) +$ 假负 $\overline { { \left( F N \right) } }$ 精度 $^ *$ 灵敏度$F$ 均值 $^ { - } _ { . = 2 * }$ 精度 $\vdots$ 灵敏度

表6训练数据和测试数据  

<html><body><table><tr><td colspan="3">训练样本</td><td colspan="4">验证样本</td></tr><tr><td></td><td>Yes (1)</td><td>No (0)</td><td>总计</td><td>Yes(1)</td><td>No (0)</td><td>总计</td></tr><tr><td>Yes (1)</td><td>89</td><td>33</td><td>122</td><td>Yes (1)</td><td>36</td><td>11</td><td>47</td></tr><tr><td>No (0)</td><td>25</td><td>64</td><td>89</td><td>No (0)</td><td>14</td><td>31</td><td>45</td></tr></table></body></html>

表7性能评估   

<html><body><table><tr><td colspan="5">训练样本</td></tr><tr><td>准确度</td><td>灵敏度</td><td>特异度</td><td>精度</td><td>召回率</td><td>F均值</td></tr><tr><td>74.39%</td><td>78.07%</td><td>66.13%</td><td>72.95%</td><td>79.22%</td><td>75.42%</td></tr></table></body></html>

验证样本  

<html><body><table><tr><td>准确度</td><td>灵敏度</td><td>特异度</td><td>精度</td><td>召回率</td><td>F均值</td></tr><tr><td>73.92%</td><td>71.82%</td><td>74.2%</td><td>76.59%</td><td>72.74%</td><td>72.92%</td></tr></table></body></html>

把本文算法的结果与文献[18\~20]的算法的结果进行比较分析，如表8所示。计算每个机器学习算法的均方误差(MSE）均方根误差（RMSE）、R平方、Q平方、误差平方和（SSE）、误差平方和总和（TSSE）、平均绝对误差（MAE）、平均绝对误差百分比（MAPE）和均方差（MSD)，部分结果如图6所示。可以看出，与其他算法相比，本文算法的性能更好。

MSE是估计值和测量值之间的差，其计算公式如下：

$$
M S E = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \left( y _ { i } - \hat { y } _ { i } \right) ^ { 2 }
$$

其中： $n$ 是观测次数， $y _ { i }$ 是观测值， $\hat { y } _ { i }$ 是预测值。

RMSE表示测量模型或估计器预测值与观测值之间的差，均方根误差（RMSE）是MSE的平方根：

$$
R M S E = \sqrt { M S E }
$$

$R ^ { 2 }$ 是数据与拟合回归线接近度的统计测量， $R ^ { 2 }$ 的定义如下：

$$
R ^ { 2 } = 1 - \frac { S S E } { T S S }
$$

其中， $S S E$ 是每个观测值与其组平均值的误差平方之和：

$$
S S E = \sum _ { i = 1 } ^ { n } { \left( y _ { i } - { \hat { y } } _ { i } \right) ^ { 2 } }
$$

$S S E$ 同样可以表示为

$$
S S E = n \times M S E
$$

TSS为所有观测数据中，每个观测值与总平均值的误差平方之总和。TSS 公式如下：

$$
T S S = \sum _ { i = 1 } ^ { n } { \left( y _ { i } - { \overline { { y } } } \right) ^ { 2 } }
$$

其中： $\overline { { y } } = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } y _ { i }$ （20因此， $R ^ { 2 }$ 也被定义为

$$
R ^ { 2 } = 1 - \frac { n \times M S E } { \displaystyle \sum _ { i = 1 } ^ { n } \left( y _ { i } - \overline { { y } } \right) ^ { 2 } }
$$

$Q ^ { 2 }$ 是 MSE与响应变量Y的方差之比。 $Q ^ { 2 }$ 公式如下：

$$
Q ^ { 2 } = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } \bigl ( y _ { i } - { \hat { y } } _ { i } \bigr ) ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { n } \bigl ( y _ { i } - { \overline { { y } } } \bigr ) ^ { 2 } } }
$$

$R ^ { 2 }$ 由下式定义：

$$
R ^ { 2 } \sim 1 - Q ^ { 2 }
$$

平均绝对误差（MAE）衡量测试样本中，预测与实际观测值间绝对差的平均值，其中所有个体差异具有相同的权重。MAE公式如下：

$$
M A E = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \left| y _ { i } - \hat { y } _ { i } \right|
$$

平均绝对误差百分比(MAPE)以百分比形式衡量误差的大小。MAPE 被定义为

$$
M A P E = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \left| \frac { y _ { i } - \hat { y } _ { i } } { y _ { i } } \right| \times 1 0 0 \
$$

使用均方差（MSD）测量拟合时间序列值的精度。MSD的计算方法为

$$
M S D = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \left| y _ { i } - \hat { y } _ { i } \right| ^ { 2 }
$$

10RMSEMAEMAPEMSD  
9  
8  
76  
54  
3  
2  
1  
0文献[18]算法 本文算法 文献[19]算法文献[20]算法

吞吐量是根据在给定时间段内，从物联网传感器设备发送到传感器服务器的数据量来计算的。例如，如果在10s内的数据传输量为16个字节，则物联网传感器设备的吞吐量为每秒1.6个字节。图7显示了使用四种算法测量得到的各种物联网健康监测设备的吞吐量，由图可知，本文算法的吞吐量相对于其余算法总是最大，其性能较好。

![](images/5993636c04f95194b101c9c6c4bbe65519b357956c1a0ea4b1bc46ecabb3ab27.jpg)  
图6性能比较  
图7吞吐量比较

表8性能分析  

<html><body><table><tr><td rowspan="2">不同算法</td><td colspan="9">性能指标</td></tr><tr><td>RMSE</td><td>MSE</td><td>SSE</td><td>TSS</td><td>R²</td><td>Q²</td><td>MAE</td><td>MAPE</td><td>MSD</td></tr><tr><td>文献[18]算法</td><td></td><td></td><td>10.764</td><td>13.864</td><td>0.307</td><td>0.892</td><td>0.503</td><td>5.395</td><td>8.742</td></tr><tr><td>本文算法</td><td>0.629 0.441</td><td>0.175 0.078</td><td>8.424</td><td>12.024</td><td>0.299</td><td>0.705</td><td>0.315</td><td>2.143</td><td>4.257</td></tr><tr><td>文献[19]算法</td><td>0.448</td><td>0.141</td><td>12.984</td><td>16.884</td><td>0.223</td><td>0.786</td><td>0.511</td><td>4.345</td><td>7.241</td></tr><tr><td>文献[20]算法</td><td>0.445</td><td>0.104</td><td>11.267</td><td>14.867</td><td>0.242</td><td>0.757</td><td>0.326</td><td>4.092</td><td>6.844</td></tr></table></body></html>

# 4 结束语

本文提出了一种新的物联网体系结构以处理医疗应用中的可扩展传感器数据。所提出的架构主要由两个子架构组成：MetaFog重定向（MF-R)架构和分组AWS密钥管理机制。MF-R 架构使用Apache Pig 和Apache HBase 等大数据技术来收集和存储不同传感器设备生成的传感器数据，并利用卡尔曼滤波消除噪声。AWS密钥管理机制用于确保雾计算与云计算的集成。该体系结构还使用密钥管理服务和数据分类函数来提供安全服务，并使用基于MapReduce 的预测模型来预测心脏病。本文通过计算吞吐量、灵敏度、准确度和F-measure 等性能评估参数证明了所提出的架构以及预测模型的有效性。

# 参考文献：

[1]Xia Feng,Yang Tianruo L,Wang Lizhe,et al. Internet of Things [J]. International Journal of Communication Systems,2012,25 (9): 1101-1102.   
[2]丁治明，高需．面向物联网海量传感器采样数据管理的数据库集群系 统框架[J].计算机学报,2012,35(6):1175-1191.(Ding Zhiming,Gao Xu. A database cluster system framework for managing massive sensor sampling data in the Internet of things [J].Chinese Journal of Computers,2012,35 (6):1175-1191.)   
[3]Lorincz K,Malan D,Fulford JT,et al. Sensor networks for emergency response: challenges and opportunities [J]. IEEE Pervasive Computing, 2005,3 (4): 16-23.   
[4]张引，陈敏，廖小飞．大数据应用的现状与展望[J].计算机研究与发 展,2013,50 (s2):216-233.(Zhang Yin,Chen Min,Liao Xiaofei.Big data applications: a survey[J]. Journal of Computer Research and Development, 2013,50 (s2): 216-233.)   
[5] 李慧芳，刘秀平．凸价格函数下基于堆栈执行的云计算资源调度方案 [J].计算机应用研究,2017,34(10):3129-3132.(LiHuifang,Liu Xiuping. Resource scheduling scheme based on stack process under convex price function in cloud computing [J].Application Research of Computers,2017, 34 (10): 3129-3132. )   
[6]Bonomi F,Milito R,Zhu Jiang,et al.Fog computing and its role in the Internet of things [C]// Proc of the 1st Edition of the MCC Workshop on Mobile Cloud Computing. New York: ACMPress,2012:13-16.   
[7]Li Shancang, Xu Lida, Wang Xinheng. Compressed sensing signal and data acquisition in wireless sensor networks and Internet of things [J]. IEEE Trans on Industrial Informatics,2013,9(4):2177-2186.   
[8]何秀丽，任智源，史晨华，等．面向医疗大数据的云雾网络及其分布式 计算方案[J]．西安交通大学学报,2016,50 (10):71-77.(He Xiuli,Ren Zhiyuan,Shi Chenhua,et al.A cloud and fog network architecture for medical big data and its distributed computing scheme [J].Journal of Xi'an Jiaotong University,2016,50 (10): 71-77.)   
[9]Jee K, Kim G H.Potentiality ofbig data in the medical sector: focus on how to reshape the healthcare system [J].Healthcare Informatics Research,2013, 19 (2): 79-85.   
[10] Chawla N V,Davis DA.Bringing big data to personalized healthcare: a patient-centered framework [J]. Journal of General Internal Medicine,2013, 28 (3): 660-665.   
[11] Masdari M,Ahmadzadeh S.Comprehensive analysis of the authentication methods in wireless body area networks [J]. Security & Communication Networks,2016,9 (17): 4777-4803.   
[12]龙昭华，龚俊，王波，等．无线传感器网络中分簇安全路由协议保密通 信方法的能效研究[J].电子与信息学报,2015,37(8):2000-2006.(Long Zhaohua, Gong Jun,Wang Bo,et al.Energy efficiency study of secret communication method on clustering secure routing in WSN[J]. Journal of Electronics & Information Technology,2015,37(8): 2000-2006.）   
[13] He Hui,Du Zhonghui,Zhang Weizhe,et al. Optimization strategy of Hadoop small file storage for big data in healthcare [J].Journal of Supercomputing,2016,72 (10): 3696-3707.   
[14] Santos MY, Martinho B,Costa C.Modeling and implementing big data warehouses for decision support [J].Journal ofManagement Analytics,2017, 4 (2): 111-129.   
[15]胡振涛，胡玉梅，刘先省．量测提升卡尔曼滤波[J].电子学报,2016, 44(5):1149-1155.(Hu Zhentao,Hu Yumei,Liu Xianxing.Kalman filter based on measurement lifting strategy[J]. Acta Electronica Sinica, 2016,44 (5): 1149-1155. )   
[16] Manogaran G, Thota C,Kumar V.Meta cloud data storage architecture for big data security in cloud computing[J]. Procedia Computer Science,2016, 87 (3): 128-133.   
[17] Kang D,Lim W S,Shin K,et al.Data//feature distributed stochastic coordinate descent for logistic regression [Cl//Proc of ACM International Conference on Conference on Information and Knowledge Management. 2014: 1269-1278.   
[18] Rehab MA,Boufares F. Scalable massively parallel learning of multiple linearregression algorithm with MapReduce [C]// Proc of IEEE Trustcom//BigDataSE/ISPA. Washington DC: IEEE Computer Society, 2015: 41-47.   
[19] Rejab FB,Nouira K,Trabelsi A.Real time SVM for health monitoring system [J].Brain Informatics and Health,2014,2014 (8609): 301-312.   
[20] Wang Limin, Chen Jiaxu,Fan Min,et al.Application of random forest data mining method to the feature selection for female sub-health state [C]// Proc of IEEE International Conference on Bioinformatics and Biomedicine Workshops.2011: 651-654.