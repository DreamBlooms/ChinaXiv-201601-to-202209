# 情景感知的物联网服务推荐方法研究

刘志中，郭思慧，张振兴(河南理工大学 计算机科学与技术学院，河南 焦作 454000)

摘要：随着服务计算与物联网技术的快速发展与成熟，网络上出现了大量的物联网服务，如何根据用户实时的情景高效地为其推荐最为合适的物联网服务，已经成为当前服务计算与物联网领域亟需解决的关键问题之一。针对这一问题，提出了一种基于情景感知的物联网服务推荐方法。首先基于改进的FolkRank 算法生成当前用户可用的物联网服务列表；之后，依据用户当前关键的情景构建用户情景信息模型，根据用户的情景模型从服务列表中筛选出最能满足用户当前情景的物联网服务。实验结果表明，所提出的情景感知的物联网服务推荐方法是可行的与有效的。

关键词：物联网；物联网服务；情景感知；服务推荐 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.09.0637

# Research on context-aware IoT services recommendation

Liu Zhizhong, Guo Sihui, Zhang Zhenxing (College ofComputer Science&Technology,Henan Polytechnic University,Jiaozuo Henan 4540oo,China)

Abstract:Withtherapid developmentof servicecomputing and Internetof Things (IoT)technology,alarge numberof IoT services have appeared onthe network.To recommend the most suitable IoTservices for target user,some approaches has proposed inthe fieldof service recommendation.However,with the increase of services data,existing methods may not guaranteethatbeerrecommendationperformancecanbeachieved,which ignore real-timecontextinformationofusers.To solve the problem,a method basedon context-aware IoT service recommendation is proposed.The method,basedon improvedFolkRankalgorithm,firstlygeneratesalistofIoTservices whichareavailable tothecurrentuser.Thentheuser context information model isconstructed according tothecurrent criticalcontextof user.Finally,teIoTservices thatbest matchthecurrent context are filteredoutfromservice listaccording touser context informationmodel.The experimental results show that the proposed context-aware IoT service recommendation method is feasible and effective.

Key words: Internet of things; IoT service; context-aware; service recommendation

# 0 引言

物联网(Internetof things，IoT)是继计算机、互联网之后，信息产业出现的第三次浪潮[1]，而本次将在前两次技术成果积累的基础上，进一步将信息获取的触角延伸至感知层，实现更广阔的互联互通。物联网能够自主地与物理世界进行交互并作出反应，以完成指定的任务。随着物联网的蓬勃发展，各种跨行业、跨领域的感知设备和终端能够快速接入网络并汇聚在一起，越来越多的智能设备[2被连接起来，并为用户提供各种各样的智能服务。

物联网服务继承和发展了传统Web服务，是传统Web服务通过传感器向物理世界的延伸。物联网服务是指建立在实现特定应用的联网的智能设备上的服务。物联网服务推荐就是在物联网的环境下，服务器提取智能设备产生的大量数据，通过对数据进行整理、分析，在服务集中找到满足用户需求的服务并推送给用户的过程。随着无线网络、移动计算与智能设备的发展与普及，物联网服务已广泛应用于不同的领域，如智慧养老、智慧城市、智慧农业等，越来越多的用户依赖于物联网服务来完成其工作与生活事务。

以养老领域为例，为了帮助患有疾病的老人处理日常生活事务，传统的方法是让子女陪护在老人身边。然而，由于年轻人工作生活事务繁忙，无法长时间地陪伴老人，使得多数老人独居，不能获取及时必要的医疗、保健与生活服务，严重影响了老人的生活质量。当前，物联网及物联网服务的出现，为居家智慧养老提供了很好的技术基础，从而可通过智能设备及时地捕获老人的各种数据信息，通过推理发现老人的需求，从而及时准确地为老人推荐最能满足其需求的物联网服务。因此，使用智能设备提供的各种物联网服务来提高居家养老的质量已成为可能。

然而，随着物联网服务数量的激增，网络上会出现大规模跨领域可用的物联网服务，而不同的用户拥有不同的智能设备，致使用户、物联网服务和智能设备之间的关联关系复杂，让缺乏领域知识的用户(尤其是行动不便的老人)人为地发现并选择物联网服务，是一个极其困难的工作，这将会大大影响物联网服务的效果与利用率。因此，如何根据用户当前的情景信息，高效地为用户推荐最为合适的物联网服务，成为当前服务计算与物联网领域亟需解决的关键问题之一。

目前，物联网服务推荐研究还处于起步阶段。魏强等人[3]针对物联网服务的大规模性、异构性和移动性等特点，提出了一种基于概率主题模型的物联网服务发现方法。Mashal等人[4通过物联网服务推荐的形式化模型，引入物联网服务推荐系统的概念，提出了一种物联网架构下基于图的推荐系统。Forestiero等人[5]利用分散自组织策略，提出了一种物联网环境下多Agent分布式推荐算法。Mashal等人[提出了一个适用于物联网环境下服务推荐的超图模型，其中每个超边连接用户、服务和智能设备。之后，Mashal等人深入地研究了传统的推荐方法及其混合方法在物联网服务推荐中的有用性。Saleem等人[7认为可通过使用各种物联网应用程序生成的数据，并借助社会物联网(SIoT)来实现物联网服务的推荐。基于此，该研究工作提出了一种通过示例应用场景的帮助，深入利用SIoT来实现多种物联网应用之间服务推荐的概念。Wang等人[8基于用户属性相似度，以及用户与设备服务之间的属性相关性，对物联网中的服务推荐策略开展研究。该研究工作还采用张量线性回归模型来解决服务推荐的冷启动问题。何秀青等人[9针对WoT设备资源受限的特点，研究了基于QoS属性向量动态更新选择最优服务的问题，给出了基于QoS动态更新的服务评价选择架构，提出了一种物联网服务动态评价选择方法。

上述研究工作在物联网服务的发现与推荐方面取得了一定的成果，推动了物联网服务应用的发展。而这些研究主要集中在物联网服务基于功能与性能的选择或推荐方法上，对于物联网服务推荐中用户情景信息对物联网服务推荐的影响缺乏深入的研究。事实上，物联网服务的运行依赖于一定的物理环境，比如用户的位置、用户的网络、用户的智能设备等。因此在为用户推荐物联网服务时，很有必要考虑用户实时的情景信息，依据用户所处的情景为其推荐最为合适的物联网服务，从而提高服务推荐的成功率。针对当前研究工作存在的不足，本文提出了一种情景感知的物联网服务推荐方法，该方法首先基于FolkRank算法生成当前用户可用的物联网服务列表；之后，依据用户当前关键的情景构建用户情景信息模型，根据用户的情景模型，从服务列表中筛选出最能满足用户当前情景的物联网服务。实验结果表明，情景信息的引入能够提高物联网服务推荐的成功率。

# 1物联网服务推荐问题建模

与传统Web服务相比，物联网服务不仅包含用户域和服务域，且还包含智能设备域。因此，物联网服务推荐是一个涉及用户领域、物联网服务领域以及智能设备领域的三元问题[10]。所以物联网服务推荐问题建模是将此三元问题转换为三个空间及其关系的数学问题。

目前，物联网环境下存在着大量可用的物联网服务、智能设备以及大规模个性化的用户，构成了物联网服务推荐中的服务空间、智能设备空间及用户空间。这三个空间的对象之间具有复杂的关联关系，比如，用户对智能设备具有一定的所属关系，物联网服务与用户之间是否存在订阅的关系，物联网服务与智能设备之间存在能否匹配运行的关系等；同时，由于三个空间内的对象数量巨大，导致三个空间的对象之间存在大量的信息孤岛。因此，三个空间的对象之间复杂的关联关系以及大量的信息孤岛，导致用户难以快速准确地发现满足其需求的物联网服务。为了实现物联网服务的快速发现，本文首先采用三元无向图来描述用户、服务和智能设备以及它们三者之间的关系；之后，将物联网服务推荐问题形式化为基于图的链接预测问题。

以智慧养老服务领域为例(如图1所示)，设某一社区养老中心有用户 $u _ { 1 }$ 、用户 $u _ { 2 }$ 和用户 $u _ { 3 }$ ，部署的物联网服务有医疗服务 $\mathbf { s } _ { 1 }$ 、定位服务 $\mathbf { s } _ { 2 }$ 和报警服务 $\mathbf { s } _ { 3 }$ ，存在的智能设备包括智能手表 $\mathbf { o } _ { 1 }$ 、智能床垫 $\mathbf { 0 } _ { 2 }$ 和烟感报警器 $\mathbf { 0 } _ { 3 }$ 。用户 $u _ { 1 }$ 使用智能手表的医疗服务和定位服务，以及智能床垫的医疗服务和报警服务；用户 $u _ { 2 }$ 使用智能手表的定位服务、智能床垫的医疗服务和烟感报警器的报警服务；用户 $u _ { 3 }$ 使用智能手表的医疗服务，以及智能床垫的医疗服务和报警服务。服务器通过三个空间对象之间存在的关系，推理出用户的需求，及时准确地给用户推送服务。用户、物联网服务以及智能设备之间的关系如图1所示。

![](images/632e1c4a2330dce8f7c00b22def27357b8e7d04efdeafb77eab67a67538fbde6.jpg)  
图1物联网服务实例Fig.1IoT service instance

对于物联网服务推荐问题，设 $U { = } \{ u 1 , u 2 , { \ldots } , u _ { m } \}$ 表示由 $m$ 个用户组成的用户集； $S { = } \{ s 1 , s 2 , { \ldots } , s _ { p } \}$ 表示由 $p$ 个服务组成的物联网服务集； $O { = } \{ o _ { 1 } , o _ { 2 } { , } . . . , o _ { n } \}$ 表示由 $n$ 个智能设备组成的智能设备集。以上述三个空间的对象作为顶点，以用户 $u _ { m }$ 、服务 $s _ { p }$ 以及智能设备 $o _ { n }$ 之间的关系作为边，构建三个空间对象之间的三元关系图。

本文定义物联网服务推荐模型为一个四元组：$F \mathrm { = } ( U , S , O , Y )$ ，其中， $Y \subseteq \{ u { \times } s { \times } o ; u \in U , s \in S , o \in O \}$ 表示 $U$ ， $s$ 和 $o$ 空间内对象之间存在的三元关系。物联网服务推荐模型中的三元关系可通过用户-智能设备矩阵 $M ( U , O )$ 、用户-服务矩阵 $M ( U , S )$ 和服务-智能设备矩阵 $M ( S , O )$ 来表示。基于这三个二维矩阵，可以将物联网服务实例图转换成一个三元无向图，继而建立三元无向图的邻接矩阵。下面给出构造三元无向图的主要步骤：

a)构建用户一智能设备矩阵 $M ( U , O )$ 。用户与智能设备之间的关系由 $m { \times } n$ 二维矩阵表示。其中，矩阵的行表示用户，矩阵的列表示智能设备，单元格 $M _ { u , o }$ 的值表示用户 $u$ 是否使用过智能设备 $\mathbf { \sigma } _ { o }$ 提供的服务；若 $\boldsymbol { M _ { u , o } { = } 1 }$ ，表示该用户拥有该智能设备，若 $\scriptstyle M _ { u , o } = 0$ ，则表示该用户对该智能设备不具有所属关系。根据图1所构建的 $M ( U , O )$ 如式(1)所示。

$$
M ( U , O ) { = } { \left[ \begin{array} { l l l } { 1 } & { 1 } & { 0 } \\ { 1 } & { 1 } & { 1 } \\ { 1 } & { 1 } & { 0 } \end{array} \right] }
$$

b)构建用户一服务矩阵 $M ( U , S )$ 。用户与服务之间的关系由 $m \times p$ 二维矩阵表示。其中，矩阵的行表示用户，矩阵的列表示服务，单元格 $M _ { u , s }$ 的值表示用户 $u$ 使用服务 $s$ 的次数。根据图1所构建的 $M ( U , S )$ 如式(2)所示。

$$
M ( U , S ) = { \left[ \begin{array} { l l l } { 2 } & { 1 } & { 1 } \\ { 1 } & { 1 } & { 1 } \\ { 2 } & { 0 } & { 1 } \end{array} \right] }
$$

c)构建服务一智能设备矩阵 $M ( S , O )$ 。服务和智能设备之间的关系由 $p { \times } n$ 二维矩阵表示。其中，矩阵的行表示服务，矩阵的列表示智能设备，单元格 $M _ { s , o }$ 的值表示智能设备 $\mathbf { \sigma } _ { o }$ 使用某个服务 $s$ 的用户数量。根据图1所构建的 $M ( S , O )$ 如式(3)所示。

$$
M ( S , O ) { = } { \left[ \begin{array} { l l l } { 2 } & { 3 } & { 0 } \\ { 2 } & { 0 } & { 0 } \\ { 0 } & { 2 } & { 1 } \end{array} \right] }
$$

d)建物联网服务推荐问题的三元无向图。基于上面构建的三个二维矩阵，合并两两关系不为0的边，并用一条边进行表示，边的权重为三个矩阵中所对应的值。通过对三个二元矩阵的合并处理，得到物联网服务推荐的三元无向图$G = ( V , E )$ ，其中，图 $G$ 的顶点集 $V$ 由用户空间、物联网服务空间和智能设备空间内的对象构成，即 $V { = } U \cup S \cup O$ 。图 $G$ 中边的集合 $E$ 由表示用户-智能设备、用户-服务和服务-智能设备之间关系的边构成，即 $E { = } \{ \{ u , o \} , \{ u , s \} , \{ s , o \} \big | ( u , s , o ) \in Y \}$ 。以图1为例，所构建的三元无向图如图2所示。

![](images/b2deef1379404a4f7ca6192655a656fbdd59b05628ac10f3577c4aff72f89701.jpg)  
图2 三元无向图 $G$

Fig.2Undirected tripartite graph $G$

三元无向图 $G$ 对应的邻接矩阵 $A$ 如(4)式所示。邻接矩阵$A$ 具有较强的稀疏性， $\partial _ { U U } , O _ { S S }$ 和 $\scriptstyle O o o$ 三个局部矩阵全是0,Muo、Mus、Mso分别与Mou、Msu、Mos互为转置，因此，在描述一个三元无向图 $G$ 时只需要对 $M _ { U O }$ 、 $M _ { U S }$ 和 $M _ { S O }$ 这三个矩阵进行存储。

$$
A = \left[ \begin{array} { l l l } { \boxed { O _ { U U } } } & { \boxed { M _ { U S } } } & { \boxed { M _ { U O } } } \\ { \boxed { M _ { S U } } } & { \boxed { O _ { S S } } } & { \boxed { M _ { S O } } } \\ { \boxed { M _ { O U } } } & { \boxed { M _ { O S } } } & { \boxed { O _ { O O } } } \end{array} \right]
$$

物联网服务推荐问题就是在物联网环境下，基于三元无向图 $G$ 所描述的用户、物联网服务以及智能设备之间的关联关系，根据用户的需求，从物联网服务集合中筛选出能够满足用户需求，并且具备运行环境(智能设备)的物联网服务，并将其推荐给用户。为了实现物联网服务的快速筛选，本文将描述物联网服务推荐的三元无向图 $G$ 转换成邻接矩阵，通过FolkRank算法完成物联网服务的快速筛选，生成推荐列表；之后，依据情景后过滤方法，实现用户情景感知的物联网服务推荐。

# 2 情景感知的物联网服务推荐方法

物联网是一个高度异构的网络，其中包括大量不同类型的智能设备，涉及到大规模的物联网服务以及大量具有个性化需求的用户。物联网服务推荐涉及到三个空间，三个空间的对象之间存在着复杂的关联关系。传统的推荐方法大多集中在二元空间内的推荐，不能有效地解决情景感知的物联网服务推荐问题。

目前，FolkRank[11,12]算法作为一种性能较好的快速排序算法，通常被用来处理包括用户、标签与资源的社会标签系统里的推荐问题。本文经过深入分析发现，FolkRank算法能够迅速捕获物联网服务推荐问题中用户、物联网服务以及智能设备之间的关联关系，并且能够有效地缓解稀疏性问题，比较适用于物联网服务推荐问题。

此外，国内外大量研究表明，情景信息能够反映用户在某一情景下的兴趣偏好，融入情景信息能够为用户提供更加准确和符合其意向的服务。物联网服务推荐问题涉及到很多关键的情景信息，比如时间、位置、天气等，利用这些情景信息能够有效地提高物联网服务推荐的效果，而传统的

FolkRank算法没有考虑问题求解时的情景信息，不能很好地满足物联网服务推荐问题的求解。为了提高物联网服务推荐的效率与效果，本文首先利用FolkRank算法生成候选物联网服务列表；之后，构建用户的情景信息模型，基于情景匹配结果为用户推荐最为合适的物联网服务。

情景感知的物联网服务推荐方法的主要计算过程如图3所示。首先，使用FolkRank算法为每个用户生成服务推荐列表；然后，根据用户实时的情景信息对推荐列表进行调整；最后，将最能满足用户情景的物联网服务推荐给当前用户。

![](images/126b5fd347f3f9a95dfb319538ac7d3f2e65614d1334ab050c4fd697a4f75648.jpg)  
图3情景后过滤  
Fig.3Contextual post-filtering

# 2.1 FolkRank 算法

FolkRank算法通常应用于由用户、标签和资源构成的社会标签系统。FolkRank算法的主要计算流程为：首先，根据收集到的数据，初始化邻接矩阵、偏好向量以及权重向量；之后，通过不断迭代和差别化的方法得到最终的权重向量；最后，选取推荐列表的Top-N项推荐给用户。在应用FolkRank算法求解物联网服务推荐问题时，需要将物联网服务看做该系统中的标签，将智能设备看做系统中的资源。FolkRank算法在计算排名时采用了PageRank 算法的随机冲浪模型。FolkRank算法的权重向量 $w$ 的迭代计算公式如式(5)所示。

$$
\boldsymbol { w } ^ { i + 1 } = d \boldsymbol { A } \boldsymbol { w } ^ { i } + \big ( \boldsymbol { 1 } - d \big ) \boldsymbol { \nu }
$$

其中： $w ^ { i }$ 是第 $i$ 次迭代时节点的权重值， $A$ 是邻接矩阵， $\nu$ 是偏好向量， $d$ 是常数（ $\begin{array} { r } { d \in [ 0 , 1 ] , } \end{array}$ ， $d$ 决定 $\nu$ 的影响程度。

FolkRank算法在计算权重向量 $w$ 时分两种情况，一种是不考虑偏好向量 $\nu$ ，即 $d { = } 1$ ，得到 $w _ { 0 } ^ { i + 1 } = A w _ { 0 } ^ { i }$ ；另一种是考虑偏好向量 $\nu$ ，即 $d { < } 1$ ，得到 $w _ { 1 } ^ { i + 1 } = d A w _ { 1 } ^ { i } + \bigl ( 1 - d \bigr ) \nu$ 。若FolkRank算法仅考虑 $d { < } 1$ 的情况，无向图的整体结构会削弱偏好向量的影响，因此利用一种差别化的方法，设置最终的权重向量为$w = w _ { 1 } - w _ { 0 }$ ，从而可以将排名合理地集中在偏好向量定义的主题周围。

# 2.2用户情景模型

在许多应用场景下，仅依靠用户、服务和智能设备之间的关联关系，并不能有效地实现物联网服务的准确推荐。事实上，同一个用户，当其所处的情景不同时，其所需要的物联网服务也会不同。若不考虑用户所处的情景信息，物联网服务的推荐精确度将受到较大的影响。因此，在进行物联网服务推荐时，将情景感知融入到推荐方法中是很有必要的。在进行物联网服务推荐时，用户所处的情景信息主要包括用户的位置、生活方式、社会关系、环境情况（温度、湿度、交通状况等）、设备能力等。本文将这些信息称为用户情景信息。

在构建用户情景信息模型时，首先对情景信息进行归类，将属于同一领域类型的情景信息归为一类。形式化地，将用户情景模型定义为由z种不同情景类型组成的z元组：$U C { = } \{ C _ { 1 } , C _ { 2 } , . . . . . . , C _ { z } \}$ ，其中 ${ C _ { i } } ( i \in { 1 . . . z } )$ 表示一种情景类型（如时间、位置或温度)。本方法主要目标是分析用户、服务和智能设备之间交互的信息以及事件发生的情景信息；依据情景信息的匹配程度对服务进行排序，依据情景匹配度为当前用户 $\boldsymbol { u }$ 选择最能满足其当前所处情景与当前的情景UC的物联网服务 $s$ 。

目前常用的情景后过滤方法主要是由Panniello 等人[13]提出的线性加权法和直接过滤法。鉴于物联网服务推荐问题的特性，本文采用线性加权的情景后过滤方法，将服务与用户实时的情景信息关联的概率和已生成的列表进行线性加权，调整候选物联网服务列表的排序。之后，将排在前面的物联网服务推荐给当前的用户。情景感知的物联网服务推荐方法的描述如算法1所示。

算法1 Context-aware IoT services recommendation algorithm

Input:Quadruple dataset，A given user $\boldsymbol { u }$ ，A given context c.

Output:the set of recommended services Rating $_ { \ast } ( u , o , s )$ Initializes the adjacency matrix $A$ ，randomly chosen vector $w _ { 0 }$ and vector $w _ { 1 }$ Compute the preference vector $\nu$ whilei<num $\begin{array} { c } { { w _ { 0 } ^ { i + 1 } = A w _ { 0 } ^ { i } } } \\ { { } } \\ { { w _ { 1 } ^ { i + 1 } = d A w _ { 1 } ^ { i } + \left( 1 - d \right) \nu } } \\ { { } } \\ { { i = i + 1 } } \end{array}$ end Compute the final weight vector $w = w _ { 1 } - w _ { 0 }$ （20 ComputeRating $_ { ( u , o , s ) }$ according to $w$ Compute $P _ { k } ( i , j )$ according to formula (6) $R a t i n g _ { k } \left( u , o , s \right) = R a t i n g \left( u , o , s \right) \times P _ { k } \left( i , j \right)$

其中： $P _ { k } ( i , j )$ 是给定用户在给定情景中的情景概率，其计算公式如式(6)所示。

$$
P _ { k } \left( i , j \right) { = } \frac { \mathrm { n e i g h b o r \_ m i n } } { \mathrm { n e i g h b o r \_ m a x } }
$$

第 $i$ 个用户在情景 $k$ 中使用第 $j$ 个服务，neighbor_max是基于用户相似度信息得到的用户 $i$ 的所有近邻总数，neighbor_min是根据特定情景 $k$ 得到的用户 $i$ 使用相同服务 $j$ 的近邻用户数。

neighbor_max的计算分三步来进行：

a)对用户一服务矩阵 $M ( U , S )$ 进行预处理。矩阵 $M ( U , S )$ 的数据取值相差较大，因此需要进行归一化处理，以保证数据取值在[0.1]中，方便进行后续的计算。

b)计算用户之间的相似度。首先，得到经用户 $\mathbf { \Delta } _ { a }$ 和用户$b$ 共同使用的服务集合用 $I _ { a b }$ 表示；之后，通过Pearson相关系数计算用户 $\mathbf { \Delta } _ { a }$ 和用户 $b$ 之间的相似性 $s i m ( a , b )$ ，其计算公式如式(7)所示。

$$
s i m ( a , b ) = \frac { \sum _ { c \in I _ { a b } } ( Q _ { a , c } - \overline { { Q } } _ { a } ) ( Q _ { b , c } - \overline { { Q } } _ { b } ) } { \sqrt { \sum _ { c \in I _ { a b } } ( Q _ { a , c } - \overline { { Q } } _ { a } ) ^ { 2 } } \sqrt { \sum _ { c \in I _ { a b } } ( Q _ { b , c } - \overline { { Q } } _ { b } ) ^ { 2 } } }
$$

其中： $Q _ { a , c }$ 是用户 $\boldsymbol { a }$ 使用服务 $\boldsymbol { \mathbf { \mathit { c } } }$ 的次数， $\overline { { { Q } } } _ { a }$ 和 $\overline { { \mathcal { Q } } } _ { b }$ 分别是用户 $\mathbf { \Omega } _ { a }$ 和用户 $b$ 对服务使用的平均次数。

c）使用KNN算法得到给定用户的邻居。neighbor_min的计算分两步来进行。首先，得到相似情景下的用户一服务矩阵 $C ( U , S )$ ；之后，选择与给定用户具有相同服务 $L$ 个以上的用户作为给定用户的邻居。

# 3 实验结果及分析

本文进行了大量的模拟实验来验证该研究工作所提方法的可行性和有效性。由于物联网服务在目前还处于初期的发展阶段，研究领域尚缺乏公开公认的数据集。为了验证本文研究方法的可行性与有效性，本文采用IJCAI-18阿里妈妈国际广告算法大赛的数据集来模拟物联网系统。该数据集分为训练集和测试集，两者都包含4类数据：用户信息、广告商品信息、店铺信息和上下文信息。此数据集中包含了关于用户、广告商品、店铺和上下文的诸多属性，本文只提取最基本的信息组成基础数据表，如表1所示。将此数据集应用在本文模拟实验时，需要做以下映射：将物联网服务信息看做广告商品信息，将智能设备信息看做店铺信息，将情景信息看做上下文信息。为了验证情景感知的物联网服务推荐方法的有效性，本文将训练集分成两类，一类是不包含情景信息的训练集，数据包括用户、服务和智能设备的编号；另一类是包含情景信息的训练集，数据包括用户、服务和智能设备的编号，以及使用服务的时间和地理位置。

表1基础数据表  
Table1 Basic data table   

<html><body><table><tr><td>字段</td><td>解释</td></tr><tr><td>user_id</td><td>用户的编号</td></tr><tr><td>object_id</td><td>智能设备的编号</td></tr><tr><td>service_id</td><td>服务的编号</td></tr><tr><td>context_timestamp</td><td>使用服务的时间</td></tr><tr><td>context_location</td><td>使用服务的地理位置</td></tr></table></body></html>

为了评估算法的性能，本文采用经典的精确率(precision)和召回率(recall)作为评估指标。精确率是推荐结果的正确性度量，精确率等于正确推荐服务的数量除以推荐服务的数量，如式（8）所示。召回率是推荐结果的完整性度量，召回率等于正确推荐服务的数量除以相关服务的数量，如式（9)所示。其中， $S _ { u } ^ { t }$ 表示前 $t$ 个推荐的服务， $S _ { u }$ 是用户 $u \in U$ 的相关服务列表。

$$
P r e c i s i o n { = } \frac { 1 } { | U | } { \sum _ { u \in U } } { \left( \frac { | S _ { u } ^ { t } \cap S _ { u } | } { | S _ { u } ^ { t } | } \right) }
$$

$$
R e c a l l = \frac { 1 } { | U | } \sum _ { u \in U } \left( \frac { | S _ { u } ^ { t } \cap S _ { u } | } { | S _ { u } | } \right)
$$

实验的运行环境是笔记本电脑，具体配置如下：OS为Windows 7；CPU为 Intel(R) CoreTM i3， $2 . 3 0 ~ \mathrm { G H z }$ ； Memory为 $4 . 0 0 \mathrm { G B }$ 。所有算法采用的编程语言是Python3.5。为了验证本文方法的可行性和有效性，本文与FolkRank算法、基于项目的协同过滤算法进行了对比实验，结果如图4所示，其中，横坐标表示算法的召回率，纵坐标表示算法的精确率。

![](images/4f5f943a1b7fce2b214fbe94f7a810909c08393493eb06511aa7d1c4ba349403.jpg)  
图4不同算法的PR 对比Fig.4PR comparison of different algorithms

从图4可以看出，本文算法在精确率和召回率的表现均优于FolkRank算法和基于项目的协同过滤算法。这说明物联网的特点和用户的情景信息对推荐算法的性能有很大的影响，本文算法更适用于物联网服务推荐，提高了物联网服务推荐系统的推荐精确度和用户满意度。

本文还针对候选物联网服务的规模对算法精确率与召回率的影响，开展了模拟实验。在该实验中，设置不同数量的候选服务，计算出相应的精确率与召回率。实验结果如图5、6所示。

![](images/59ac1a4675d71058180c18288e0aa178273dcc0ebc94c84f23b56f996b2c6c00.jpg)  
图5精确率与候选服务数量的关系

![](images/c61b9123631dd1b0eb2880b3911ef2ee4cfc86ce8add7ce24f15e25f2e112380.jpg)  
Fig.5Relationship between precision and number of candidate services   
图6召回率与候选服务数量的关系  
Fig.6Relationship between recall and number of candidate services

图5表示精确率与候选服务数量之间的关系，从图5可以看出两种算法的精确率都会随着候选服务数量的增加而下降，本文算法相比于FolkRank算法精确率提高了 $7 \%$ 。图6表示召回率与候选服务数量之间的关系，从图6可以看出两种算法的召回率都会随着候选服务数量的增加而上升，本文算法相比于FolkRank算法召回率提高了 $13 \%$ 。这些进步表明本文算法在合理考虑情景信息的情况下，有更高的推荐质量。同时也证明了本文算法相对于FolkRank算法更具有可行性和有效性。

# 4 结束语

物联网将会加速信息膨胀，使用户无法快速选择符合自身需求的服务，而物联网推荐系统是目前解决此问题最有效的方法，对物联网的普及起着至关重要的作用。本文提出情景感知的物联网服务推荐方法，使用线性加权的情景后过滤方法，将情景信息融入到物联网服务推荐中。实验结果表明该方法在准确率和召回率方面都有所提升。在未来，每个实体都将被赋予一个IP地址，可获取的数据源更多。研究者可从更多维度去描述情景，为用户提供更好的服务体验，真正做到服务与情景相融合，从而提供更加高效准确的推荐。

# 参考文献：

[1]Chen E T. The Internet of things:opportunities,issues,and challenges [M]//The Internet of Things in the Modern Business Environment.2017: 167-187.   
[2]Han S N,Crespi N. Semantic service provisioning for smart objects: Integrating IoT applications into the Web[J]. Future Generation Computer Systems,2017,76:180-197.   
[3]魏强，金芝，许焱．基于概率主题模型的物联网服务发现[J]．软件 学报,2014,25(8):1640-1658.(Wei Qiang,Jin Zhi,Xu Yan,Service discovery for Internet of Things based on probabilistic topic model [J]. Journal of Software,2014,25(8): 1640-1658.)   
[4]Mashal I, Chung T Y,Alsaryrah O.Toward service recommendation in Internet of Things [C]//Proc of the 7th International Conference on Ubiquitous and Future Networks.New York: IEEE,2015:328-331.   
[5]Forestiero A.Multi-agent recommendation system in Internet of things [C]//Proc of the 17th IEEE/ACM International Symposium on Cluster, Cloud and Grid Computing. New York: IEEE,2017: 772-775.   
[6]Mashal I,Alsaryrah O,Chung T Y. Performance evaluation of recommendation algorithms on Internet of Things services [J].Physica A: Statistical Mechanics and its Applications,2016,451(6): 646-656.   
[7]Saleem Y,Crespi N,Rehmani MH,et al. Exploitation of social IoT for recommendation services [C]//Proc of the 3rd IEEE World Forum on Internet of Things.New York: IEEE,2016: 359-364.   
[8] Wang P, Luo H, Sun Y. IoT service recommendation strategy based on attribute relevance[C]//Proc of International Conference on Ubiquitous Computing and Ambient Intelligence.New York: Springer International Publishing,2017: 34-43.   
[9]何秀青，王映辉．物联网服务动态评价选择方法研究[J]．电子学报， 2013,41(1):117-122.(He Xiuqing,Wang Yinghui. Service selection algorithm based on dynamic assessment for Web of Things [J].Acta Electronica Sinica,2013,41(1):117-122.)   
[10]乔秀全，章洋，吴步丹，等．事件驱动、面向服务的物联网服务提供 方法[J]．中国科学：信息科学，2013，43(10):1219-1243.(Qiao Xiuquan,Zhang Yang，Wu Budan,et al.An EDSOA-based service provisioning approach for Internet of things [J]. Science China: Information Sciences,2013,43(10):1219-1243.)   
[11] Hotho A,Jäschke R, Schmitz C,et al.FolkRank: A ranking algorithm for folksonomies [C]//Proc of Workshop of the Special Interest Group Information Retrieval. 20o6:111-114.   
[12] Hotho A,Jäschke R,Schmitz C,et al. Information retrieval in folksonomies:search and ranking[Cl//Proc of European Semantic Web Conference.2006: 411-426.   
[13]Panniello U，Tuzhilin A，Gorgoglione M，etal.Experimental comparison of pre-vs.post-filtering approaches in context-aware recommender systems [Cl// Proc of the 3rd ACM Conference on Recommender Systems.New York: ACM Press, 2009: 265-268.