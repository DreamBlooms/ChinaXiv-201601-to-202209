# 基于混合云架构的深度语义密文检索

李剑，矫健

(北京邮电大学 人工智能学院，北京 100876)

摘要：针对传统的云环境下密文检索方案基于统计学模型来生成文件向量和检索向量，并没有考虑文件和请求的深层次语义信息，提出一种基于混合云架构的深层次语义密文检索模型。通过私有云联邦学习神经网络模型构建向量生成模型，通过公有云存储密文数据。另外，提出密倒排索引表来存放文件向量，在公有云的检索过程中，保证检索信息不被泄露的情况下提高检索的效率。对真实数据集的分析和实验表明，提出的方案在安全性和搜索效率方面都优于目前同类型的密文检索方案。

关键词：密文检索；混合云；联邦学习；加密倒排索引表 中图分类号：TP309 doi:10.19734/j.issn.1001-3695.2022.02.0101

# Deep semantic ciphertext retrieval based on hybrid cloud architecture

Li Jian, Jiao Jian (SchoolofArtificial Intelligence,Beijing UniversityofPosts&Telecommunications,Beijing1Oo876,China)

Abstract: Aimingatthetraditional ciphertext retrieval scheme in cloud environment,which generates file vectorsand retrieval vectorsbasedonstatisticalmodel,anddoes notconsiderthe dep-seated semantic informationoffilesandrequests, this paper proposes a deep-seated semantic ciphertext retrieval model based on hybrid Cloud Architecture.The vector generationmodel isconstructedthrough the privatecloud federatedlearning neuralnetworkmodel,andtheciphertextdatais storedthroughthepubliccloud.Inadition,this paper proposesasecret inverted indextable to store file vectors,soas to improve the eficiencyofretrieval without ensuring thattheretrieval information isnot leaked intheretrieval processof publiccloud.Theanalysisandexperimentsonrealdatasets showthat thisscheme is betterthan thecurrentciphertextretrieval schemes of the same type in terms of security and search efficiency.

Key words: ciphertext retrieval; hybrid cloud; federal learning; encrypted inverted index table

# 0 引言

随着网络技术的发展和网络业务需求的扩大，以及云计算和大数据的发展。为了提高效率，越来越多的机构和公司将数据上传至公有云服务器。然而数据隐私一直是云计算应用发展的一个重大阻碍。虽然云服务提供商声称防火墙等机制可以增强用户数据的安全性，但公有云服务器完全控制外包数据，“诚实但好奇的”的云服务器可能会泄露数据所有者不愿透露的敏感数据。因此，数据所有者在将文档上传到半诚实的云之前对其进行加密，并将数据存储为密文以确保文档的安全性。另一方面，企业和政府为保证数据安全性构建私有云服务器，往往存在内部的大量有价值资源不可被使用，出现数据孤岛问题。因此提出一种在云环境下通过数据共享提升性能的高效密文检索方案具有重要意义。

数据加密方案对数据检索提出了巨大的挑战。近年来，研究学者提出了许多文本检索策略。在文献[1]中，Cao等人首先采用向量空间模型计算文档向量和查询向量的内积，并使用安全kNN算法(Sec-kNN)对其进行加密。基于内积运算的结果，提出了一种多关键字密文检索结果排序(MRSE)方案后来，研究者提出了许多拓展方法[2-5。这些方法都具有可证明的安全性，但在信息检索领域都采用了传统的TF-IDF 加权统计计算规则。使用关键词的规则无法有效捕获单词的上下文。此外，这些方案具有高向量维数、高存储要求和高时间复杂度。在信息检索中，当单词匹配失败时，潜在语义模型将查询映射到相关文档。该模型解决了文档和查询之间的语言差异。具体来说，即使查询关键词没有在文档中直接出现，它们也可能被构造为两个具有高相似度的低维语义向量。

语义搜索是明文数据和加密数据信息检索的一个重要研究方向[6\~II。语义分析消除了查询和文档之间的语言差异。Fu 等人[在语义本体的支持下建立了用户兴趣模型，实现了个性化的关键词精确搜索。在文献[13,14]中，使用互信息模型构建语义扩展方案。例如，Jadhav利用互信息模型扩展查询关键字，然后计算文档的相关性得分。文献[15]中提出了模糊关键词搜索技术，用于扩展关键词集合。Fu等人[I5开发了基于单纯形的分级多关键字模糊搜索方案，没有预定义的模糊集。Yang等人[提出在一个可验证的语义方案中利用EMD距离，该语义方案描述了查询和文档之间的单词传输问题，单词传输的最小成本称为查询和每个文档之间的相似性分数。

本文使用混合云架构，解决数据孤岛问题，利用联邦学习构建深度神经网络模型提取数据深层语义，并提出加密倒排索引表结构来缩短检索时间，该方案保证了数据的安全性，并有较高的检索准确性和效率。

# 1 问题描述

# 1.1系统模型

如图1所示，在本方案中，一共有五个实体，分别为数据拥有者、数据使用者、私有云服务器、公有云服务器、参数服务器。

1)数据拥有者数据拥有者拥有有价值的数据。对数据进行加密处理后

上传至公有云，同时将明文数据上传至私有云后进行模型训练。根据训练完成的神经网络模型，生成文件向量后，构建加密倒排索引表上传至公有云。

# 2)数据使用者

数据使用者将检索关键词、个人信息发送至所有数据拥有者进行授权认证、检索关键词映射字及密钥。将检索关键词发送至参数服务器接收到检索向量后，根据密钥生成加密陷门发送至公有云，并收到公有云返回的TOP-K相关文件结果。

# 3)私有云服务器

每个数据拥有者有一个私有云服务器。“诚实且可信”的私有云服务器收到明文数据、网络模型后单独训练，每轮训练结束后将参数结果与参数服务器进行联邦训练。训练好的神经网络模型回传至数据拥有者。

# 4)公有云服务器

公有云服务器为“诚实且不可信”的实体。存储数据拥有者的加密数据与加密倒排索引表。收到参数服务器发送的请求陷门后，通过计算找出相关加密文件发送至数据使用者。

# 5)参数服务器

参数服务器同样也是私有云服务器。是“诚实且可信”的，由所有数据拥有者共同维护。它是联邦学习模型训练的中央服务器。在收到数据使用者的检索关键字后生成检索向量发送至数据使用者。

![](images/88eeccd3d455dcb4484409c69059b9b4e9cb1a1e58835f6ba823a9762b0d08fb.jpg)  
图1系统模型

# 1.2威胁模型

在本文的方案中，本文假设参数服务器是可信的，公共云是一个“诚实但好奇”的服务器。基于半诚实公共云服务器已知的信息，本文研究了两种威胁模型。

已知密文威胁模型。公共云只知道加密文档、加密数据索引和安全查询陷门。在这种情况下，公共云服务器仅使用仅密文攻击模式进行攻击。

已知背景威胁模型。公共云服务器应该知道比已知密文模型中更多的信息。这些知识包括陷门的相关关系，以及与数据集相关的统计信息。公共服务器使用已知的陷门信息来分析查询关键字或陷门与文档的关系。

# 1.3符号

$\boldsymbol { \mathscr { Q } }$ :检索关键词集合， $Q = \{ q _ { 1 } , q _ { 2 } , . . . , q _ { k } \}$ 0

$D$ ：明文数据集合 $D = \{ D ^ { 1 } , D ^ { 2 } , . . . , D ^ { n } \}$ ，其中 $D ^ { i }$ 代表第 $i$ 个数据拥有者的明文数据集合。

$E$ :密文数据集合 $E = \{ E ^ { 1 } , E ^ { 2 } , . . . , E ^ { n } \}$ ，其中 $E ^ { i }$ 代表第 $i$ 个数据拥有者的密文数据集合 $i$ 。

$P$ :文件向量集合， $P = \{ P _ { 1 } ^ { 1 } , P _ { 2 } ^ { 1 } , . . . , P _ { j } ^ { n } \}$ ，其中 $P _ { t } ^ { i }$ 代表第 $i$ 个数据拥有者的第 $t$ 个明文数据对应的文件向量。

$I$ :加密文件向量集合， $I = \{ I _ { 1 } ^ { 1 } , I _ { 2 } ^ { 1 } , . . . , I _ { j } ^ { n } \}$ ，其中 $I _ { t } ^ { i }$ 代表第 $i$ 个数据拥有者的第 $t$ 个明文数据对应的加密文件向量。

$N$ ：检索关键词映射数字集合，$N = \{ N _ { 1 } ^ { 1 } , N _ { 2 } ^ { 1 } , . . . , N _ { k } ^ { n } \}$ ，其中 $N _ { t } ^ { i }$ 代表第 $t$ 个检索关键词在第 $i$ 个数据拥有者的映射数字表达。

$V$ :检索向量。

$T$ :加密检索向量。

# 1.4设计目标

为了在上述模型下有效地利用外包的云数据实现排序搜索，本文方案需要确保检索准确性和检索效率。

检索准确率：使用统计特征的经典加密检索模型无法捕获单词的上下文信息和文档的深层语义。本文的方案旨在研究文件深层次的语义，而不是基于统计学特征作为文件检索结果的依据。，本文的模型不是使用统计特征的方法，而是通过神经网络进行优化，检索准确率高于以前的方法。

效率：效率包括两个方面，搜索和存储。减小生成向量的维数可天然减小存储与计算资源消耗，同时设计合适的文档索引向量管理结构也可提高检索的效率。

# 2 模型

# 2.1私有云联邦学习模型

联邦学习是分布式机器学习架构的一种表现形式，联邦学习可分为训练服务器和中心参数服务器。所有服务器共享需要训练的机器学习模型，且共享各服务器每轮训练的参数，所有训练服务器将参数以密文形式传递给中心服务器后，中心服务器进行参数统一。联邦学习架构，在保证数据不被共享的前提下，对所有数据进行集中训练。解决了各个数据拥有者的敏感数据孤岛问题。

联邦学习由参数服务器与数据训练方两部分组成，所有训练者共享训练模型[7I。各数据训练者单独训练自己的数据共享训练参数。传统密文检索方案基于统计学模型，根据文件中关键词的词频与逆向文件频率来生成文件向量和检索请求向量。在此基础上提高检索准确性的方案为检索关键词的拓展，如用户兴趣模型、根据深度学习得出的相似关键词的拓展，或根据关键词的位置进行权重更新。由于数据安全性的问题，并没有通过深度神经网络训练明文数据，挖掘文章深层次语义。本文提出基于私有云架构下的联邦学习模型，可将文章向量与检索向量的生成方式由传动的统计学模型更新为深度学习模型。并且考虑所有数据训练者的计算性能有所不同，设计时间窗口管理模式，提高了通信与训练效率。如图2所示，为私有云联邦学习模型架构。

![](images/bd6ee2131df7998ff1c2581ef6b79bcb5cddc4dfef6f2c8e043cd998b90eb8ac.jpg)  
Fig.1System model   
图2私有云联邦学习模型  
Fig.2Private cloud federation learning model

一轮联邦学习网络模型更新的时间由数据拥有者的训练时间T1和参数传递及参数服务器更新时间T2组成。考虑到每个数据拥有者的数据量及计算能力不同，本文设计了时间窗口管理模型。联邦学习开始之间，整个系统测试通信时间，设定通信窗口T1及总体窗口时间T，数据拥有者训练时间$\scriptstyle \mathrm { T } 2 = \mathrm { T } - \mathrm { T } 1$ 。对数据拥有者1来说，第一次训练参数结果为W，后在T2时间内继续本地训练，本地训练的轮次根据数据拥有者的数据量大小、私有云的计算能力不同也会有所不同，在结束时的训练参数结果计为 $W _ { 1 }$ ，将结果发送至参数服务器该方案既保证了每轮模型统一时，所有用户数据拥有者都参与训练又考虑了计算能力强的数据拥有者可多次本地训练提升模型训练效果。

# 2.2神经网络向量生成模型

与传统的统计学生成的向量生成模型不同，本文利用私有云联邦学习模型训练神经网络向量生成模型。模型选择为DSSM[18]。文件向量、检索向量通过该模型映射到同维度的深层次语义空间。

DSSM模型的输入为N个文件与1个查询请求。神经网络架构为五层。第一层为维度为 $5 0 0 \mathrm { k }$ 的输入。经过Word-n-gram层将维度减小到 $3 0 \mathrm { k }$ 。后经过两层全连接深度神经网络层，维度为300、300，后输入为128维的向量。该模型的各层激活函数为tanh。

在训练过程中，通过该模型生成的 $\mathbf { N } { + } \mathbf { l }$ 个128位的向量对应了文件与查询请求。为简化密文检索的复杂度，本文在生成128维向量后，需对向量进行归一化处理：

$$
\mathbf { y } = { \frac { Y } { \left. Y \right. } } 
$$

相关性分数为查询向量与文件向量的点乘结果。模型目标是优化点击文档的可能性，损失函数如式(2)所示。

$$
\begin{array} { r } { \operatorname { L } ( \Lambda ) = - \log \prod _ { ( Q , \hat { D } ^ { + } ) } P ( \hat { D } ^ { + } | Q ) } \end{array}
$$

其中，通过softmax函数计算的正向文档与查询请求的相关性得分的后验概率， $\gamma$ 为以真实数据测试为背景得出的平滑系数， $\overline { { D } }$ 为所有文档，包括4个没有被点击的文档 $\overline { { D } } ^ { \prime }$ 和1个被点击的文档 $\overline { { D } } ^ { + }$ 。在本文的方案中，随机初始化参数，使用随机梯度算法使得每个私有云来分布式地训练。如式(3)所示，

$$
P ( \boldsymbol { \bar { D } } ^ { * } \left| \boldsymbol { \mathcal { Q } } \right. ) = \frac { \exp ( \Upsilon R ( \boldsymbol { \bar { D } } ^ { * } \left| \boldsymbol { \mathcal { Q } } \right. ) ) } { \sum _ { \boldsymbol { D } ^ { * } = \boldsymbol { D } } \exp ( \Upsilon R ( \boldsymbol { \bar { D } } ^ { * } \left| \boldsymbol { \mathcal { Q } } \right. ) ) }
$$

在本文中，每个数据拥有通过私有云服务器单独训练DSSM模型，数据为该拥有者自己的数据。通过参数服务器进行参数共享。

# 2.3加密倒排索引表

倒排索引表在信息检索领域中应用广泛，根据KEY-VALUE格式建表，其中KEY为文件关键词集合。VALUE值为文件的文件向量。在密文检索中，不可信的公有云存放检索表，避免公有云服务器对数据使用者的检索情况进行分析，所以不可将KEY值以明文关键字的形式直接存放于公有云服务器。本文利用离散对数难题将关键词映射为无规律的数字。并且在每轮检索过程中更新密文倒排索引表的KEY值。加密倒排索引表保证了数据和数据使用者的安全性，具体流程如图3所示。

数据使用者在检索的初始阶段需要向所有数据拥有者发送身份认证。认证通过后，数据使用者拥有 $n$ 个密钥集合$S = \{ P D _ { 1 } , q _ { 1 } , a _ { 1 } \} , \{ P D _ { 2 } , q _ { 2 } , a _ { 2 } \} , . . . , \{ P D _ { n } , q _ { n } , a _ { n } \}$ ,其中 $\{ P D _ { i } , q _ { i } , a _ { i } \}$ 代表第 $i$ 个数据拥有者与数据使用者共享的素数 $q$ 、整数 $a$ ，以及数据使用者 $i$ 的文件密钥。

数据使用者通过私钥 $X _ { u s e r }$ 生成公钥 $Y _ { u s e r }$ ，如式(4)所示。

$$
Y _ { u s e r } = a ^ { ( X _ { w e r } ) } { \bmod { q } }
$$

随后将 $Y _ { u s e r }$ 和检索关键词集合 $\boldsymbol { Q } = \{ q _ { 1 } , q _ { 2 } , . . . , q _ { k } \}$ 一同发送给数据拥有者 $U _ { i }$ 。数据使用者该轮请求有 $k$ 个关键字。对于数据拥有者 $U _ { i }$ ，根据 $k$ 个关键字，生成 $k$ 个私钥 $\{ \mathbf { X } _ { p c s } ^ { 1 } , . . . , \mathbf { X } _ { p c s } ^ { k } \}$ 和$k$ 个公钥 $\{ Y _ { p c s } ^ { 1 } , . . . , Y _ { p c s } ^ { k } \}$ 。并将公钥发送至数据使用者。

数据使用者通过式(5)计算出 $k$ 个关键字映射数字：

$$
\mathbf { N } ^ { K } = ( Y _ { p c s } ^ { k } ) ^ { \scriptscriptstyle { X _ { w e r } } } \bmod q
$$

数据拥有者通过式(6)计算出 $k$ 个关键字映射数字：

$$
\mathbb { N } ^ { \kappa } = ( Y _ { u s e r } ) ^ { X _ { p e s } ^ { k } } \bmod q
$$

在数据使用者与所有数据拥有者进行身份认证和关键字数字映射后，共有 $n { \times } k$ 个关键词映射数字生成，数据使用者将 $\scriptstyle n \times k$ 个映射数字与检索关键词发送至参数服务器。每个数据使用者跟据自己拥有的 $k$ 个映射数字更新加密倒排索引表对应KEY值，其余KEY值随机生成并发送至公有云。

# 3 本文方案

# 3.1具体方案

$$
k e y ( 1 ^ { l ( n ) } )  \{ S K , K , a , q \}
$$

数据所有者通过随机密钥生成算法输出密钥以加密文档和索引，并输入一个安全参数1。 $^ { S K }$ 是一个密钥集，包括一个 $( n + u + 1 )$ 位向量和两个 $( n + u + 1 ) \times ( n + u + 1 )$ 可逆矩阵,$S K = \{ M _ { 1 } , M _ { 2 } , S \}$ 。此外， $K$ 是对称密钥, $a$ 是 $q$ 的本源根。

$$
\{ a , q , X _ { u s e r } , Y _ { u s e r } \}  N
$$

身份认证后，数据使用者发送检索关键字给所有数据拥有者，每个数据拥有者与该数据使用者根据 $\boldsymbol { a }$ ， $q$ 和各自的密钥 $X _ { u s e r }$ ， $Y _ { u s e r }$ 来生成检索关键词的映射数字。具体流程如2.2所述。数据拥有者根据生成的关键字映射数字生成加密倒排索引表的KEY值。数据使用者拥有 $n { \times } k$ 个关键字映射数字。其中 $k$ 为数据使用者的关键字个数， $n$ 为数据拥有者的数量。

数据拥有者U𝑖 数据使用者数据拥有者和使用者共享 身份认证、密钥交换 数据拥有者和使用者共享密钥{PDi,qiai}，且 密钥{PD(，qi,a𝑖），且a(是ai是qi的本原根 qi的本原根数据使用者生成私钥XuserQ (<q)、公钥Yuser发送Yuser 检索关键词集合Q=k个关键字，生成k个私钥 {q1q2,...q){xpcs...,Xpcs)（<q)，和k个 公钥{Ypes...Ypes]） 发送{Ypcs..,.ypes）数据使用者算出k个检索关键字的映射数字Nk=(Ypcs） Xuser mod q数据拥有者算出k个检索关键字的映射数字Nk =(Yuser）xpesmod q

a)联邦学习深度神经网络模型

数据拥有者将数据信息传入私有云，共同训练预先规定好的神经网络模型。规定，在初始轮次神经网络的参数统一，在每轮训练结束、下一轮训练开始前，各私有云服务器从参数服务器下载最新参数，参数再次统一。在本文使用的神经网络模型为DSSM[18]，该模型结构如2.2所述。联邦学习训练模型方式根据2.1所述，考虑所有用户参与每轮训练，也同时保证算力大的用户多次训练来提升联邦学习训练效率。

$$
I n d e x ( S K , D )  \{ P , I \}
$$

通过私有云训练好的向量模型，所有数据拥有者根据该模型明文数据 $D$ 生成128 维的文件向量 $P$ ，并将其扩展为（20 $( 1 2 8 + u + 1 )$ 维度向量 $\scriptstyle { \vec { P } }$ ，其中扩展的最后一位设为1，其他设为随机数字 $\varepsilon ^ { ( j ) }$ 。经过密钥 $S K$ 加密文件向量 $P$ 生成加密文件向量 $I$ ，具体为利用 $s$ 将向量 $\vec { P }$ 分裂为 $P ^ { \prime }$ 和 $P ^ { * }$ ，分裂规则如式(7)所示。数据使用者构建倒排索引表并将加密文件向量 $I$ 放入表的VALUE位置。上传至公有云。

$$
\left\{ \begin{array} { l l } { \overrightarrow { P _ { l } ^ { \prime } } [ t ] = \overrightarrow { P _ { l } ^ { \prime } } [ t ] = \overrightarrow { P } [ t ] } & { ( S [ t ] = 0 ) } \\ { \overrightarrow { P _ { l } ^ { \prime } } [ t ] + \overrightarrow { P _ { l } ^ { \prime } } [ t ] = \overrightarrow { P } [ t ] } & { ( S [ t ] = 1 ) } \end{array} \right.
$$

$$
E n c ( D , K ) \to C
$$

数据使用者使用密钥 $K$ 加密数据集 $D$ 。

$$
T r a p d o o r ( Q , S K )  T
$$

数据使用者将检索关键词发送至参数服务器，参数服务器根据训练好的模型生成检索向量发送至数据使用者，数据使用者根据密钥 $\mathit { S K }$ 和接收到的128 维检索向量 $V$ ，并扩展为 $( 1 2 8 + u + 1 )$ 维度向量 $\vec { \nu }$ ，扩展的最后一位为随机数字 $t$ ，其余补充位置由0或者1补充，并利用 $s$ 将向量 $\vec { \nu }$ 分裂为 $V ^ { ' }$ 和$\boldsymbol { V } ^ { * }$ ，分裂规则如式(8)所示。再生成加密检索陷门 $T$ 后，数据使用者将陷门 $T$ 和关键词映射集合 $N$ 发送至公有云。

$$
\begin{array} { r } { \begin{array} { r l } { \overrightarrow { V ^ { * } } [ t ] = \overrightarrow { V ^ { * } } [ t ] = \overrightarrow { V } [ t ] } & { { } ( S [ t ] = 1 ) } \\ { \overrightarrow { V ^ { * } } [ t ] + \overrightarrow { V ^ { * } } [ t ] = \overrightarrow { V } [ t ] } & { { } ( S [ t ] = 0 ) } \end{array} } \end{array}
$$

$$
S e a r c h ( T , I , N , k _ { t o p } )  E _ { q }
$$

公有云收到数据使用者上传的加密检索陷门 $T$ 后，根据关键词映射集合 $\mathbf { \Omega } _ { N }$ 与加密倒排索引表比对，找出与关键词映射集合 $N$ 为 KEY值的对应所有VALUE中的加密文件向量$I$ ，通过式(9)计算出前 $k _ { t o p }$ 个文件 $E _ { q }$ ，并发送至数据使用者。

$$
\begin{array} { c } { { { \cal I } _ { i } \cdot { \cal T } = \{ M _ { 1 } ^ { T } \overrightarrow { \mathrm { P } _ { l } ^ { ' } } , M _ { 2 } ^ { T } \overrightarrow { \mathrm { P } _ { l } ^ { ' } } \} \cdot \{ M _ { 1 } ^ { - 1 } V ^ { \prime } , M _ { 2 } ^ { - 1 } V ^ { \prime } \} ~ = \overrightarrow { \mathrm { P } _ { l } ^ { ' } } \cdot V ^ { ' } + \overrightarrow { \mathrm { P } _ { l } ^ { ' } } \cdot V ^ { ' } ~ = } } \\ { { \overrightarrow { { \cal P } \cdot { \cal Q } } = r ( { \cal P } \cdot { \cal Q } + \sum \varepsilon ^ { ( j ) } ) + t } } \end{array}
$$

$$
D e c ( E _ { q } , K ) \to D _ { q }
$$

数据使用者根据收到结果文件集 $E _ { q }$ 后，根据密钥 $K$ 解密后得到结果文件明文信息。

# 3.2方案流程

本文提出的混合云架构的密文检索方案具体工作流程解耦为为两部分，非检索阶段和检索阶段，如图4所示。

非检索阶段包括构建向量生成模型，向量生成模型可生成检索向量和文件向量，通过章节2.1提出的混合云架构的联邦学习模型来训练2.2章节的神经网络模型，生成神经网络向量生成模型；每个数据拥有者拥有该模型输入明文数据得到文件向量，文件向量通过加密并利用2.3章节提出的加密倒排索引表来管理文件向量。

![](images/8f669abc9493c2b375736bf3d9dd784c145a3c835209ac86afc4dee3618d342a.jpg)  
图4方案流程 Fig.4Scheme process

检索阶段，数据使用者发送检索请求至拥有神经网络向量生成模型的参数服务器，参数服务器收到检索请求后生成检索向量并发送至数据使用者，数据使用者加密检索向量后发送至公有云，公有云通过加密倒排索引表检索出相关文件，并发送给数据使用者；数据使用者通过密钥解密出目标明文数据。

由于数据的更新，会让神经网络向量生成模型不断更新，检索阶段和非检索阶段会重复发生，但分别独立。

# 4 安全性分析

首先，在神经网络模型中生成陷门和文档索引，并对其进行降维。文档和查询的内容不能直接反映在向量中。此外，还引入了伪关键字、随机分裂和两个 $( n + u + 1 ) ^ { 2 }$ 加密矩阵。正如文献[19]中所证明的，对手无法构造足够的方程来完整地计算矩阵。因此，本文提出的方案很好地抵抗了已知的密文模型威胁模型。

本文将已知背景知识模型下的安全性归结为了解文档索引和检索陷门之间的内在关系。为了进一步防止好奇的公共云服务器根据已知的背景知识泄露和最小化文档信息，本文动态地改变了陷门的表达。本文使用 $s$ 分割密钥 $^ { S K }$ 中的向量。因此，即使用户多次检索同一查询，收到的搜索请求陷门也是不同的。同时，所有向量引入随机数$\varepsilon ^ { ( j ) }$ ，其值服从均值为 $\mu ^ { \prime }$ ，方差为 $\scriptstyle \sigma ^ { \prime } = c ^ { 2 } / 3$ 的均匀分布$U ( \mu ^ { \prime } { - } c , \mu ^ { \prime } { + } c )$ ，根据中心极限定理， $\varepsilon ^ { ( j ) }$ 服从 $N ( \mu , \sigma ^ { 2 } )$ ， $\sigma$ 值越高，安全性越高但其检索准确性降低，合适的 $\sigma$ 值，可有效地抵抗了统计分析的攻击。本文提出的方案对于已知的背景知识威胁模型也是安全的。

# 5 性能评估

本文使用PYTHON语言在IntelCore CPU为 $2 . 9 \mathrm { G H z }$ 、Windows10服务器、RAM为4GB的计算机上实现了该方案。本文提出的系统的性能与 MRSE方案[2]、PRSE方案[12]和FMRSM方案[20的性能进行了对比。在实验中，本文在一个真实的数据集上评估整体性能，该数据集以后称为评估数据集，并且利用DSSM[18]网络作为联邦学习网络模型。从一年的查询文档日志文件中随机选择20000个英语查询样本，模型训练时每次一个检索请求和对应的4个非相关文档和1个相关文档。本文从检索效率和文档检索精度方面进行了性能分析。每次模拟重复10次，并分析和给出平均模拟结果，系统的各个模块及具体实现方案如表1所示。

表1模块介绍与实现方法  
Tab.1Introduction and implementation method of each module   

<html><body><table><tr><td>实现模块</td><td>模块实现方法</td></tr><tr><td>私有云联邦学习模块</td><td>FedML联邦学习开源框架</td></tr><tr><td>联邦学习模型</td><td>DSSM[20]</td></tr><tr><td>加密倒排索引表模块</td><td>自定义算法</td></tr><tr><td>文件检索模块</td><td>自定义算法</td></tr><tr><td>文件加解密密模块</td><td>Crypt库</td></tr></table></body></html>

本文比较了本文的方案与上述方案(MRSE、FMRSM和PRSE)的文档检索效率。如图5所示，随着集合中文档数量的增加，所有四种方案的检索时间都会增加。MRSE的搜索时间随着文档集大小的线性增长而近似线性增长。考虑到公共云服务器需要在搜索阶段扫描所有文档索引，这是合理的。FMRSM和PRSE方案的性能更好，但本文的方案的性能优于上述所有方案。本文方案搜索过程基于加密倒排索引表，且向量维数较低。因此，当文档集具有更多文件时，本文的方案更有效。

无论关键字的数量如何，三个方案：MRSE、PRSE和FMRSM的搜索时间大致保持不变，如图6所示。但三种方案的检索时间都远高于本文方案。

![](images/74a4e52353595fba4f9d4269c978468165e8be61ff2435d1bcc1a225c0c278fb.jpg)  
图5文件个数对检索时间的影响

在本文中，本文通过相关文档在所有返回结果中所占的比例来衡量文档检索的准确性。从图7可以看出，与MRSE相比，无论文档数量如何，本文方案的搜索精度始终高于 $9 5 \%$ 相比之下，MRSE的搜索效率从近 $90 \%$ 逐渐下降到 $80 \%$ 。

![](images/cf877f814536809e2af2976e782afdb00fa23c560661fc931bb93fef7b44da5f.jpg)  
Fig.5The influence of the number of files on retrieval time   
图6检索关键字对检索时间的影响Fig.6The influence of search keywords on search time

![](images/5c78c62cecba884e690f5a3f63bf2b55b2f5a22277b65ce4e104246b12979c4b.jpg)  
图7检索准确率 Fig.7Retrieval accuracy

# 6 结束语

本文提出混合云架构下的深度语义密文检索方案，本文利用私有云进行联邦模型学习，解决了数据孤岛及安全性问题，可提取出文件更深层次语义信息，提高了检索的准确性。并利用加密倒排索引表结构，在保证数据使用者检索关键词不被公有云记录的前提下，提升了检索的效率分析和仿真结果表明，该方案为数据用户提供了安全、高效的加密文档搜索服务。

在本文未来的工作中，本文计划优化神经网络结构或使用更好的模型来挖掘加密检索中文档的深层次语义。同时，结合具体模型构建提升检索效率的向量存储模型。

# 参考文献：

[1]Cao Ning,Wang Cong,LiMing,et al.Privacy-Preserving multi-keyword ranked search over encrypted cloud data [J].IEEE Transactions on Parallel and Distributed Systems,2014,25 (2):222-233.   
[2]Xia, Zhihua, Chen Li,Sun Xingming,et al.A multi-keyword ranked search over encrypted cloud data supporting semantic extension [J]. International Journal of Multimedia and Ubiquitous Engineering,2016, 11.8:107-120.   
[3]Cai Chengjun,Weng Jian,Yuan Xingliang.et al.Enabling reliable keyword search in encrypted decentralized storage with fairness [J]. IEEE Transactions on Dependable and Secure,2021,18(1):131-144.   
[4]Li Feng,MaJianfeng,Miao Yinbin,et al.Verifiable and dynamic multikeyword search over encrypted cloud Data Using Bitmap [J].IEEE Transactions on Cloud Computing.2021:1-1.   
[5]Liu Lianggui and Chen Qiuxia.A novel feature matching fanked search mechanism over encrypted cloud data [J].IEEE Access,202o,8:114057- 114065.   
[6]Zhang Dong,Fan Qing,Qiao Hongyi,et al.Apublic-key encryption with multi-keyword search scheme for cloud-based smart grids [C]// 2021 IEEE Conference on Dependable and Secure Computing,2021:1-6.   
[7] 沈学利，崔海韵，陈鑫彤．一种支持撤销的位置分层属性加密研究 [J].计算机应用研究,2019,37(1):216-220.(Shen Xueli,Cui Haiyun,ChenXintong.Research on encryption of location hierarchical attribute ssuporting revocation [J].Application Research of Computers, 2019,37 (1): 216-220.)   
[8]Miao Yinbin,R.Deng,K.K.R.,et al. Threshold multi-keyword search for cloud-based group data sharing [J].IEEE Transactions on Cloud Computing,2020,99:1-1.   
[9]路宏琳，王利明．面向用户的支持用户掉线的联邦学习数据隐私保 护方法[J]．信息网络安全,2021,21(3):64-71.(LUHonglin,WANG Liming.User-oriented Data Privacy Preserving Method for Federated Learning that Supports User Disconnection [J].Netinfo Security,2021, 21 (3): 64-71.)   
[10]张佳乐，赵彦超，陈兵，等．边缘计算数据安全与隐私保护研究综述 [J].通信学报,2018,39(3):1-21.(ZHANGJL,ZHAOYC,CHEN B, et al.Survey on data security and privacy-preserving for the research of edge computing [J]. Journal on Communications,2018,39 (3): 1-21.)   
[11] Zhang ke, Long Jiahuan,Wang Xiaofen,et al. Lightweight searchable encryption protocol for industrial internet of things [J].IEEE Transactions on Industrial Informatics,2020,17(6): 4248-4259.   
[12] Fu Zhangjie,Ren Kui, Shu Jiangang,et al. Enabling personalized search over encrypted outsourced data with eficiency improvement [J]. IEEE Transactions on Parallel Distributed Systems,2016,27 (9): 2546-2559.   
[13] J.Nagesh,N. Jyoti,B. Sayli. Semantic search supporting similarity ranking over encrypted private cloud data [J].Int.J.Emerging Eng. Res. Technol,2014,2(7): 215-219.   
[14] Xia Zhihua,Zhu Yanling， Sun Xingming,et al. Secure semantic expansion based search over encrypted cloud data supporting similarity ranking [J]. Journal of Cloud Computing. 2014,3 (1): 1-11.   
[15]Fu Zhangjie,Wu Xinle,Guan Chaowen,et al. Toward efficient multikeyword fuzzy search over encrypted outsourced data with accuracy improvement [J].IEEE Transactions on Information Forensics and Security.2017,11(12): 2706-2716.   
[16] Yang Wenyuan, Zhu Yuesheng.A verifiable semantic searching scheme by optimal matching over encrypted data in public cloud [J].IEEE Transactions on Information Forensics and Security.2020,16:100-115.   
[17] Wu Wentai, He Ligang,Lin Weiwei,et al. SAFA: a semi-asynchronous protocol for fast federated learning with low overhead [J].IEEE Transactions on Computers.2020: 1-1.   
[18] Shen Yelong,He Xiaodong,Gao Jianfeng,et al.A latent semantic model with convolutional-pooling structure for information retrieval [C]// Proceedings of the 23rd ACM International Conference on Conference on Information and Knowledge Management. New York:ACM,2014: 101-110.   
[19] Chen Chi, Zhu Xiaojie,Shen Peisong,et al. An effcient privacypreserving ranked keyword search method [J]. IEEE Transactions on Parallel and Distributed Systems.2016,27(4): 951-963.   
[20] Wong Kit Wong,D.W. Cheung,B.Kao,et al.Mamoulis. Secure knn computation on encrypted databases [C]// Proc. ACM SIGMOD Int'1 Conf.Management of Data (SIGMOD) .2009:139-152.