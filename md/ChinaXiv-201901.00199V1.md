# 基于变迁图编辑距离的流程相似性算法

段瑞，方欢，方贤文，詹悦(安徽理工大学 数学与大数据学院，安徽 淮南 232001)

摘要：为了提高从企业模型库中查询检索模型的效率，提出一种基于变迁图编辑距离的流程相似性算法。首先，给出变迁图的概念及其生成方法；其次，提出边的长度概念，删除和插入边的代价由该边的长度决定，基于此定义图编辑操作及其代价，并用节点匹配算法计算最小图编辑距离；然后，给出两个过程模型的相似性概念和计算方法；最后，通过实验验证了算法的正确性且满足七条相似性性质，并验证了变迁图编辑距离满足四条距离性质。

关键词：Petri网；相似性度量；变迁图；图编辑距离中图分类号：TP301 doi:10.19734/j.issn.1001-3695.2018.10.0729

Process similarity algorithm based on editing distance of transition graph

Duan Rui, FangHuan,Fang Xianwen, Zhan Yue (SchoolofMathematics&Big Data,Anhui Universityof Science&Technology,Huainan Anhui 232001,China)

Abstract:Inorder to improvetheeficiencyofqueryingandretrieving models from the enterprise modellibrary,aprocess similarityalgorithmbasedontheeditdistanceof transition graph is proposed.Firstly,theconceptof thetransitiongraph and its generation methodare given.Secondly,theconceptof the length of theedge is proposed.Thecostof deletingand inserting theedgeisdeterminedbythelengthoftheedge.Basedonthis,thegraphediting operationanditscostaredefined, andthe node matching algorithm is used tocalculate the minimum graph editing distance.Then,the similarityconcept and calculation methodof te two process modelsare given.Finally,the corectnessofthe algorithm is verifiedand the seven similaritypropertiesaresatisfied,and theediting distanceof thetransitiongraph isverified tosatisfythefourdistance properties.

Key words:Petri nets; similarity measure; transition graph; graph editing distance

# 0引言

业务流程作为企业的三要素之一，流程模型的相似性度量一直是工作流研究中的一个重要方向。对于数以万计的模型库，高效且精准的模型检索方法成为业务过程管理的关键，这就要求高效的流程相似性算法[2。

目前已有的流程相似性算法主要基于以下三个方面展开[3]：a)最直观的相似性度量方法，关注任务标签、事件或其他建模元素；b)从模型的拓扑结构出发，关注模型的元素集合及元素之间的行为关系；c基于行为语义的相似性算法。为了验证算法的性能，流程相似性领域学者和专家提出了七条基本的相似性性质[4：顺序结构漂移不变性、并发结构漂移不变性、循环结构漂移不变性、互斥结构漂移不变性、跨度负相关性、非替代无关递减性和循环序列长度负相关性。

Zha 等人提出了一种基于变迁紧邻关系的相似性算法，称为TAR算法，该算法通过考察流程变迁的两两紧邻关系来表征流程模型的相似性。殷明等人[5提出了一种TAR算法的改进算法 $T A R + +$ 算法，创造性的为TAR增加了重要性系数，有效地满足了一些TAR算法不能满足的相似性性质。但$T A R + +$ 算法用深度优先搜索方法为紧邻变迁关系分配重要性，算法的最坏时间复杂度为 $O ( V + E + N ! )$ ，是一个阶乘级的复杂度，且 $T A R + +$ 相似性有一个不高的上界。

Weidlich等人(8提出了基于行为轮廓(BP)的相似度度量方法，该方法定义了弱序，并基于弱序关系提出一系列关系，统称为行为轮廓，该方法用行为轮廓扩展紧邻变迁关系，有效地满足了一些TAR算法不能满足的相似性性质，但仍不能满足所有性质。通过构造任务最短跟随距离矩阵度量流程相似性的SSDT算法[4能够满足所有相似性性质，但是SSDT算法每次计算流程相似性时，需要根据矩阵的秩进行对应的扩展确保两个矩阵的秩相等，使得算法性能不够优良。

图匹配和图编辑距离一直是模型相似性度量的重要手段，Dijkman等人描述了四种图匹配算法，分别是贪心算法、带剪枝的穷举算法、流程启发式算法及 $A ^ { * }$ 算法，并通过实验评估表明：贪心算法所耗时间远低于其他算法， $A ^ { * }$ 算法的精确度最高，带剪枝的穷举算法所耗时间远高于其他算法。图编辑距离是指一个图转换成另一个图需要的操作代价[]，计算流程相似性需要的是最小图编辑距离，图匹配算法即通过在模型比较时建立节点之间一一对应关系，从而找到最小图编辑距离。

针对相似性度量算法仍存在的一些问题，如不能满足相似性性质、时间复杂度较高、空间爆炸、灵活性较低、计算值与预期值不符等，本文提出一种新的基于变迁图编辑距离的流程相似性算法TGED，主要贡献为：a)通过库所映射，把Petri网模型转换成变迁图，即把Petri网模型中的库所映射成变迁图中的边；b)首次提出边的长度概念，编辑不同长度的边所需代价不同；c取一个变迁图到另一个变迁图所需操作的最小代价为编辑距离，并基于此计算相似性；d)TGED算法有一个较大的上界，且时间复杂度较低。

# 1预备知识

本文以Petri网作为形式化的建模和分析工具，在介绍TGED算法之前，先介绍关于Petri网的预备知识。

定义1标签Petri网。满足下列条件的一个五元组$\boldsymbol { L } \boldsymbol { N } = ( P , T , F , \Sigma , \ell )$ 称做标签Petri网，其中： $P$ 是库所； $T$ 是变迁； $F$ 是流关系； $\Sigma$ 是表示变迁的标签集合。

$$
P \cup T \neq \varphi \ ;
$$

$$
P \cap T = \varphi ;
$$

$$
F \subseteq ( P \times T ) \cup ( T \times P ) \ ;
$$

其中： $\ell : T \to \Sigma \cup \{ \varepsilon \}$ 是标签函数。

记 $X = P \cup T$ ，对于 $x \in X$ ， $x$ 的前集记为$\bullet x = \{ y \in X \mid ( y , x ) \in F \}$ （204号 $x$ 的后集记为$x \bullet = \left\{ y \in X \middle | ( x , y ) \in F \right\} , \bullet ( x \bullet ) = \left\{ z \in X \right.$

$\mid y \in X \land ( x , y ) \in F \land ( z , y ) \in F \ \circ \quad x \in$ $x \in X$ 称为 Petri 网的一个节点， $f \in F$ 称为Petri网的一个边，与 $x$ 相邻的边称为 $x$ 的边，包括入边和出边。为标签Petri 网添加一个初始标志 $M _ { 0 }$ 得$L N = ( P , T , F , M _ { 0 } , \Sigma , \ell )$ 称为标签Petri 网系统， $M _ { 0 } : P  N ^ { + }$ ， $N ^ { + }$ 为非负整数集。

定义2工作流网。满足下列条件的三元组 $W F N = ( N , i , o )$ 称做工作流网，其中： $N = ( P , T , F , M _ { 0 } , \Sigma , \ell )$ 是标签Petri网系统;$i \in P$ 是开始库所； $o \in { \cal P }$ 是结束库所。

a) $i , o$ 是唯一的;  
b) $\bullet i = \varphi$ ， $o \bullet = \varphi$ ， $i \neq o$ ：  
c) $\forall x \in P \cup T$ ，存在一条从 $i$ 到 $\vert o \vert$ 的路径包含 $x$ 。

本文所讨论的模型都是基于Petri网的安全工作流网，称所有库所都是有界且界为1的Petri网为安全的，称库所最多含有一个标志为有界且界为1的，其中初始标志为整个系统模型的触发条件，初始标志状态下，开始库所中含有一个标志，其他库所不含标志。为了方便计算相似性，提出一种不含库所只由变迁和边组成的图，称为变迁图。

定义3图编辑距离。给定两个图 $G _ { 1 } = ( V _ { 1 } , E _ { 1 } )$ 和$G _ { 2 } = ( V _ { 2 } , E _ { 2 } )$ ，由 $G _ { 1 }$ 转换成 $G _ { 2 }$ 所需操作的最小代价称为图 $G _ { 1 }$ 和$G _ { 2 }$ 的编辑距离，记为 $e d i s ( G _ { 1 } , G _ { 2 } )$ 。

为了确定图编辑距离，需要定义合理的图编辑操作及其代价，本文总结已有的图编辑操作，并给出一个新的概念：边长度，删除和插入边由边的长度决定。

定义4图编辑操作。给定图 $G = ( V , E )$ ，定义编辑图 $G$ 的基本操作为：节点的删除、插入、替换及边的删除、插入。$( u \to \varepsilon )$ 表示删除节点 $u$ ， $( \varepsilon \to \nu )$ 表示插入节点 $ { \boldsymbol \nu }$ ， $( u \to \nu )$ 表示用节点 $\nu$ 替换节点 $u$ ，同理表示边的删除和插入。

如图1所示，从图1(a)到(b)为删除边 $( a , f )$ 和 $( f , c )$ ，从(b)到(c)为用节点 $g$ 替换节点 $f$ ，即 $( g \to f )$ ，从(c)到(d)为插入边 $( g , b )$ 、 $( g , d )$ 和 $( g , e )$ ，经过一系列基本的图编辑操作，图1(a)转换成(d)。

# 2基于变迁图的相似性计算

为了计算两个流程模型的相似性，首先需要依据它们的Petri网模型生成变迁图，其次为变迁图定义合理的基本图编辑操作及其代价，最后求得最小代价即为图编辑距离。

# 2.1变迁图的生成

定义5变迁图。给定工作流网 $W F N = ( N , i , o )$ ，其中

$N = ( P , T , F , M _ { 0 } , \Sigma , \ell )$ 是标签Petri网系统； $G = ( V , E )$ 是WFN的变迁图， $\boldsymbol { V }$ 是节点集合且 $\cup V = T$ ， $E \subseteq V \times V$ 是边集合。 $\boldsymbol { \mathbf { \mathit { E } } }$ 的产生方式为： $E = \{ ( \bullet p , p \bullet ) | \forall p \in P \}$ ，记边 $( \bullet p , p \bullet )$ 的前端节点为 $\bullet _ { } { p }$ ，后端节点为 $p \bullet$ 。特殊地，若 $\exists p \in P [ | \bullet p | > 1 ]$ ， $p$ 映射成的边的前端节点由前面边的后端节点确定， $p$ 或作为互斥结构的收尾，对应 $| \bullet \boldsymbol { p } |$ 条边，或引发一个循环结构；若 $\exists p \in P [ | p \bullet | > 1 ]$ ，$p$ 引发一些互斥分支，若 $p _ { 1 } , p _ { 2 } , . . . , p _ { j } \in p \bullet \cdot p _ { 1 } \bullet \bullet \neq$ $p _ { 2 } \bullet \bullet \neq \ldots \neq p _ { j } \bullet \bullet$ ，则 $p$ 对应边的后端节点将引出 $j$ 条边，且每条边由一个该节点中的变迁控制，该变迁称为控制变迁。

为了处理工作流网首尾是特殊结构的情况，在生成变迁图之前，人工为工作流网增加开始库所 $p _ { s }$ 和变迁 $t _ { s }$ 、结束库所 $p _ { e }$ 和变迁 $t _ { e }$ ，并增加四条边分别为 $( p _ { s } , t _ { s } )$ 、 $( t _ { s } , j )$ 、 $( o , t _ { e } )$ 、$( t _ { e } , p _ { e } )$ 。

![](images/699abcc44493402499cb6fbdf482f39ef563a59456fce099a00d97c9e534727a.jpg)  
图1图编辑操作示例(a)\~(d)  
Fig.1Graph editing operation example (a)\~(d)

如图2所示，左边是4种典型的Petri网模型结构：顺序、互斥、循环和并发，右边是对应的变迁图。图2(a)左边是顺序结构，人工为其增加开始库所 $p _ { s }$ 和变迁 $t _ { s }$ 、结束库所 $p _ { e }$ 和变迁 $t _ { e }$ ，并增加4条边分别为： $( p _ { s } , t _ { s } )$ 、 $( t _ { s } , j )$ 、 $( o , t _ { e } )$ 、 $( t _ { e } , p _ { e } )$ ，新得到的模型除库所 $p _ { s }$ 和 $p _ { e }$ 外有4个库所，依据定义5对应4条边，得到如图2(a)的右边。图2(b)左边是内嵌有顺序结构的互斥结构，人工改造后：对于库所 $s _ { 1 }$ ， $s _ { 1 } \bullet = \{ t _ { 2 } , t _ { 3 } \}$ ，即$s _ { 1 } \in P [ | s _ { 1 } \bullet | > 1 ]$ ，且 $t _ { 2 } \bullet \bullet = \{ t _ { 4 } \}$ 、 $t _ { 3 } \bullet \bullet = \{ t _ { e } \}$ ，因此有 $t _ { 2 } \bullet \bullet \neq t _ { 3 } \bullet \bullet$ ，库所 $s _ { 1 }$ 对应边 $( \{ t _ { 1 } \} , \{ t _ { 2 } , t _ { 3 } \} )$ 的后端节点 $\{ t _ { 2 } , t _ { 3 } \}$ 将引出两条边，分别由 $t _ { 2 }$ 、 $t _ { 3 }$ 控制，如图2(b)右边。图2(c)左边是循环结构，对于库所 $s _ { 1 }$ $_ { 1 } , \bullet s _ { 1 } = \{ t _ { 1 } , t _ { 4 } \}$ ，则 $s _ { 1 }$ 对应的边的前端节点由库所i对应的边的后端节点决定，即 $\{ t _ { 1 } \}$ ，此时 $s _ { 1 }$ 引发一个循环结构。图2(d)左边是并发结构，在本文给出的变迁图定义中，顺序结构和并发结构是最易处理的结构，图2(d)右边是其对应的变迁图。

# 2.2变迁图的行为语义

变迁图作为Petri网模型的无库所简化，每个节点可能含有多个变迁，因为一个库所能够引发多个互斥分支。同理，变迁图中一个节点可能具有多条边：a)作为嵌有其他结构的互斥结构的收尾；b)引出的互斥分支具有循环结构；c)并发结构。本文称一条从人工添加变迁 $t _ { s }$ 到 $t _ { e }$ 的完整执行序列为一条语句，一个变迁图的所有语句组成变迁图的语言。对变迁图的行为保持解释如下：

a)变迁图的所有发生序列即为变迁图的行为语义。

变迁图中的边由变迁控制，边上的变迁决定了该边只能由控制变迁引发，如图2(b)中的变迁图的发生序列为：$< \{ t _ { s } \} , \{ t _ { 1 } \} , \{ t _ { 2 } , t _ { 3 } \} , \{ t _ { 4 } \} , \{ t _ { e } \} >$ 和 $< \{ t _ { s } \} , \{ t _ { 1 } \} , \{ t _ { 2 } , t _ { 3 } \} , \{ t _ { e } \} >$ ，若边上为空，则默认控制变迁为该边的前端节点元素；

变迁图中只含有一个变迁的节点引出的多条边并发，可以由上一条解释，即该节点引出的边默认由该节点元素控制，由于节点只含有一个变迁，当该变迁被引发之后，即可以引发所有从其引出的边，如图2(d)中变迁图的发生序列为：$< \{ t _ { s } \} , \{ t _ { 1 } \} , \{ t _ { 2 } \} , \{ t _ { 3 } \} , \{ t _ { 4 } \} , \{ t _ { e } \} >$ 和 $< \{ t _ { s } \} , \{ t _ { 1 } \} , \{ t _ { 3 } \} , \{ t _ { 2 } \} , \{ t _ { 4 } \} , \{ t _ { e } \} >$

![](images/03709b701903a9334703319dbd13dbf263161393c649e66a08861f64e659cecd.jpg)

b)变迁图中节点触发条件：以该节点为后端节点的边被引发。

![](images/1ea9422a51d0c1383900f9d7a8e779c778e6c5e4e157a027472ff88ce1026a34.jpg)

图2四种典型的Petri 网模型结构(a)\~(d)及对应的变迁图

Fig.2There are4 typical Petri net model structureson the left(a)\~(d),corresponding transition graph onthe right

# 2.3图编辑操作及其代价

前面提到，本文给出的图编辑基本操作有：节点的删除、插入、替换及边的删除、插入，本节主要为这些基本操作赋予合理的代价。本文认为节点的删除、插入为单位基本操作，包括控制变迁的插入、删除和替换，赋予代价1。下面详细介绍节点的替换和边的删除、插入。

# 2.3.1节点的替换

节点的替换涉及到节点中变迁标签的相似性，标签的单位字删除、插入和替换代价为1，通过一系列字符串操作把一个变迁标签转换成另一个变迁标签，所需操作的最小代价为两个变迁标签的编辑距离，与它们中模值最大的比值为节点的替换操作代价。若两个变迁标签完全不同，则替换操作代价为1。

如图3(a)中变迁标签"Lookingforfood"到图3(b)中变迁标签"Findfood"的转换所需最小操作代价为10，即替换4个单位字，删除6个单位字，整个节点的替换代价为 $\frac { 1 0 } { 1 4 } = 0 . 7 1 4$ 。

![](images/b782ae9ffa78260dd079125faf44c94f9d312d21dfb24683695c6136216c72f2.jpg)  
图3某美食app 部分系统模型对应的变迁图(a)\~(b)  
Fig.3Transition graph (a)\~(b) corresponding to the system model of gourmet app

2.3.2边的删除与插入

本文首先提出边的长度概念用以描述删除与插入该边的代价，库所i和 $\mid o \mid$ 对应的边长度为1，在人工变迁 $t _ { s }$ 与 $t _ { e }$ 之间选取一条最长简单路径为主干，主干上的边长度均设为1，主干的分支跨主干的长度为该分支的近似长度，节点长度为0。

如图3 所示，图3(a)转换到(b)除用"Find food"替换"Looking for food"之外，还需删除节点"Findfood”及两条边({"Lookingforfood"},{"Findfood"}) ，({"Findfood"},{"Addfood to the shipping basket"}）。当节点"Find food"和节点"Entera shop"无限接近时，取这两个边的长度近似值1，则删除代价为1。

# 2.4相似性计算

由定义3可知，一个图转换成另一个图所需操作的最小代价为它们的编辑距离，基于变迁图编辑距离的相似性度量方法的核心是求变迁图的最小编辑距离。

定义6TGED相似性。给定两个工作流网，它们对应的变迁图分别为 $G _ { 1 } = ( V _ { 1 } , E _ { 1 } )$ 和 $G _ { 2 } = ( V _ { 2 } , E _ { 2 } )$ ， $e d i s ( G _ { 1 } , G _ { 2 } )$ 为图 $G _ { 1 }$ 和$G _ { 2 }$ 的编辑距离， $\mid G \mid = \mid \mathrm { G . V } \mid + \mid \mathrm { G . E } \mid + \mid \mathrm { G . C T } \mid$ 表示图 $G$ 的模值，其中$\vert G . V \vert$ 表示图 $G$ 中的节点数， $\left| G . E \right|$ 表示图 $G$ 中所有边的近似长度之和， $\operatorname { | } G . C T \operatorname { | }$ 表示图 $\boldsymbol { G }$ 中控制变迁数，则相似性为$s i m ( G _ { 1 } , G _ { 2 } ) = 1 - \frac { e d i s ( G _ { 1 } , G _ { 2 } ) } { \operatorname* { m a x } ( \left| G _ { 1 } \right| , \left| G _ { 2 } \right| ) - 2 } \mathrm { ~ o ~ }$ （204号

对于定义6的相似性计算公式中分母减去2是因为要消除人工添加的变迁的影响，如图3所示， $e d i s ( a , b ) = 3 . 7 1 4$ ，则$\begin{array} { r l } { s i m ( a , b ) = { } } & { { } 1 - \displaystyle \frac { e d i s ( a , b ) } { \operatorname* { m a x } ( | a | , | b | ) } = 1 - \frac { 3 . 7 1 4 } { 1 6 - 2 } = 0 . 7 3 5 \ _ { \circ } } \end{array}$ （20

# 3TGED 算法

# 3.1算法设计

本节给出基于变迁图编辑距离的流程相似性算法TGED。由前面可知，算法的核心是生成变迁图及计算变迁图编辑距离，依据变迁图编辑距离可以轻松的计算出相似性。

分析TGED算法，算法第1行人工改造工作流网，第2\~16行为改造后的工作流网生成变迁图，其中2\~4行创建并初始化变迁图，5\~15依据定义5计算工作流网的变迁图，16 行计算另一个工作流网的变迁图，第17行计算两个变迁图的最小编辑距离，第18\~19行依据定义6计算相似性。

在TGED算法第17行计算两个变迁图转换所需的最小操作代价不是一个简单的过程，文献[6]提出了基于 $A ^ { * }$ 搜索算法的节点匹配，在算法迭代过程中，不断利用当前生成的部分进行节点匹配，选择代价最小的(相似性最大)进行扩展，最终得到最优解，该算法定义了剩余节点的编辑距离下界估值，用以“剪枝”。文献[9]给出了4种匹配算法用以解决"诱导最大相似性的映射”，即最小图编辑距离，依据4种算法的平均精确度和运行时间，本文采用贪心算法和 $A ^ { * }$ 算法。

transition-graph-edit-distance-similarity-algorithm $( W _ { 1 } , W _ { 2 } )$   
1．artificial transformation workflow nets $W _ { 1 } , W _ { 2 }$ （204号   
2.create graph $G _ { 1 } = ( V _ { 1 } , E _ { 1 } )$ （204号   
3. $V _ { 1 } = \varphi$ （204   
4. $E _ { \mathrm { { l } } } = \varphi$ （204   
5.foreach in a certain order $s \in P _ { 1 }$ （20   
6. $\begin{array} { r l } { \boldsymbol { \mathsf { f } } } & { | \bullet s | = 1 } \\ & { V _ { 1 } = V _ { 1 } \cup \bullet s \cup s \bullet } \\ & { E _ { 1 } = E _ { 1 } \cup ( \bullet s , s \bullet ) } \\ { \boldsymbol { \mathsf { f } } } & { | \bullet s | > 1 } \end{array}$   
7.   
8.   
9.   
10. theplacein frontof $s$ determines   
11. $V _ { 1 } = V _ { 1 } \cup s \bullet$ （204号   
12. foreach $s ^ { \prime } \subseteq \bullet s \wedge$ Enode $s ^ { \prime \prime } \in V _ { 1 } [ ( s ^ { \prime \prime } , s ^ { \prime } ) \in E _ { 1 } ]$ （204号   
13. $E _ { 1 } = E _ { 1 } \cup ( s ^ { \prime } , s \bullet )$   
14. $i f \ \mid s \bullet \mid > 1 \land \exists s _ { 1 } , s _ { 2 } , . . . , s _ { j } \in s \bullet \land s _ { 1 } \bullet \bullet \neq s _ { 2 } \bullet \bullet \neq . . . \neq s _ { j } \bullet \bullet$   
15. incorporate the $j$ edgesof node $s \bullet$ into $E _ { 1 }$   
16.same as above,calculate transition graph $G _ { 2 }$ of $W _ { 2 }$   
17.calculate minimum operating cost,recorded as edi $\cdot ( G _ { 1 } , G _ { 2 } )$ （204号   
18.calculate the modulus of $G _ { \mathrm { 1 } }$ and $G _ { 2 }$ ,recorded separately $\big \vert G _ { 1 } \big \vert , \big \vert G _ { 2 } \big \vert$   
19.similaritybetweenWand W,sim(W,W)= $W _ { 2 } , s i m ( W _ { 1 } , W _ { 2 } ) = 1 - \frac { e d i s ( G _ { 1 } , G _ { 2 } ) } { \operatorname * { m a x } ( | G _ { 1 } | , | G _ { 2 } | ) }$

# 3.2算法时间复杂度分析

改造工作流网的方法为：人工添加两个变迁、两个库所及四条边，时间复杂度为常数量级；创建变迁图及初始化的时间复杂度同样为常数量级； $T G E D$ 算法第5\~16行生成变迁图的时间复杂度分别为 $O ( \left| V _ { 1 } \right| + \left| E _ { 1 } \right| )$ 和 $O ( \left| V _ { 2 } \right| + \left| E _ { 2 } \right| )$ ，用摊还分析即可得到该时间复杂度；用贪心算法计算最小图编辑距离的时间复杂度为 $O ( \operatorname* { m i n } ( \mid V _ { 1 } \mid , \mid V _ { 2 } \mid ) \times \mid V _ { 1 } \mid \times \mid V _ { 2 } \mid )$ ， $\cdot$ 算法计算最小图编辑距离的最坏情况下时间复杂度为 $O ( \operatorname* { m i n } ( \mid V _ { 1 } \mid ! , \mid V _ { 2 } \mid ! ) )$ ，最佳情况下时间复杂度为 $O ( \left| V _ { 1 } \right| \times \left| V _ { 2 } \right| )$ 。实际运行时，由于使用了估值函数， $A ^ { * }$ 算法的运行时间远低于最坏时间复杂度，接近最佳时间复杂度。

# 4实验与评估

本文的实验模型主要来自SAP模型库，从SAP模型库中随机获取230个模型作为实验对象。为了验证TGED算法相似性性质的满足情况，另人工编纂70个模型，一共300个流程模型作为实验数据。

# 4.1实验设计

本文的实验机器环境为:Intel(R)Core(TM)i5-7300HQ CPU$\textcircled { a } \ 2 . 5 0 \mathrm { G H z }$ ，安装内存(RAM)为 $8 . 0 0 \mathrm { G B }$ ，64位操作系统。以开放的业务过程模型管理框架BeehiveZ系统l.I2l为工具，BeehiveZ具有多种流程管理功能，本文主要用到查询功能，即检索功能。实验数据共分为两类：第一类是从SAP模型库中随机获取的230个模型，用以验证TGED算法的正确性和可行性；第二类是人工编纂的70个模型，用于验证TGED算法相似性性质的满足情况。

首先通过实验验证TGED算法的正确性，即TGED算法是否能在输入两个工作流网的情况下，输出一个[0,1]之间的数；其次需要验证图编辑距离性质，以三角不等式性质为主；最后验证TGED算法相似性性质满足情况。

# 4.2距离性质验证

对本文提出的图编辑距离进行距离性质验证，TGED相似性度量满足4个距离性质，分别为对称性、自反性、非负性、三角不等式性。

对称性：两个工作流网之间的相似性唯一，即$\forall W _ { 1 } , W _ { 2 } [ e d i s ( W _ { 1 } , W _ { 2 } ) = e d i s ( W _ { 2 } , W _ { 1 } ) ] \Longrightarrow \ s i m ( W _ { 1 } , W _ { 2 } ) = s i m ( W _ { 2 } , W _ { 1 } )$ ，图编辑操作都是对称的，所以两个模型之间的最小编辑操作代价是对称的，它们的TGED相似性满足对称性。

自反性：工作流网和自身的相似性为1，即$\forall W [ e d i s ( W , W ) = 0 ] \Rightarrow s i m ( W , W ) = 1 \quad$ ，两个完全相同的图不需要任何操作便能互相转换。

非负性：两个图的TGED相似性计算为：$s i m ( G _ { 1 } , G _ { 2 } ) = 1 - \frac { e d i s ( G _ { 1 } , G _ { 2 } ) } { \operatorname* { m a x } ( \left| G _ { 1 } \right| , \left| G _ { 2 } \right| ) - 2 }$ ， 其中$e d i s ( G _ { 1 } , G _ { 2 } ) \leq \operatorname* { m a x } ( \mid G _ { 1 } \mid , \mid G _ { 2 } \mid ) - 2$ 恒成立，即 $\forall W _ { 1 } , W _ { 2 } [ s i m ( W _ { 1 } , W _ { 2 } ) \geq 0 ]$ 。

三角不等式： $\forall W _ { 1 } , W _ { 2 } , W _ { 3 } [ e d i s ( W _ { 1 } , W _ { 2 } )$ $\left. \leq e d i s ( W _ { 1 } , W _ { 3 } ) + e d i s ( W _ { 3 } , W _ { 2 } ) \right]$ ，即给定任意3个模型及它们之间的3个距离，任意两个距离之和大于等于第三个距离，这是TGED相似性最重要的一条距离性质，也是需要实验验证的。

首先给出三角不等式满足率的定义，假设实验数据集中共有 $n$ 个模型，从这 $n$ 个模型中任取3个，共有 $C _ { n } ^ { 3 }$ 种组合，若共有 $n ^ { \prime }$ 种模型组合满足三角不等式，则三角不等式满足率为 $n ^ { \prime } / C _ { n } ^ { 3 }$ 。其次为了更好的对不同算法的三角不等式满足率进行评估，本文采取3次实验，得到3组三角不等式满足率，每次从模型数据集中随机抽取一定数量的模型作为实验数据集，3次实验抽取的模型数量分别为94、117和123，3次实验数据集分别记作数据集1、2和3。最后为了更好地体现TGED算法的优势，除引言部分提到的相似性算法外，本节额外加入两个算法作为实验对象，分别为：因果足迹算法$C F$ [10]和完整触发序列算法CFS[13]。

前面提到，插入和删除边的代价由该边的长度决定，为了精确验证三角不等式满足率，在计算图编辑距离时，插入和删除边的代价便不能取近似值。本文用 $" n +$ “表示比长度0 $" n "$ 大一点点的长度，即插入和删除他们的代价。

对 $T A R + +$ 、TAR、 $B P$ 、SSDT、 $C F$ 、CFS 算法和本文提出的TGED算法进行三角不等式满足率实验，表现如图4所示。在三角不等式满足率方面，SSDT、 $\boldsymbol { C } \boldsymbol { F }$ 和CFS算法表现得不如其他算法，TAR算法在数据集1上未达到 $100 \%$ 满足率，表现最好的是 $T A R + +$ 、 $B P$ 和 TGED 算法。

更全面的算法性能比较还包括算法运行时间的对比，如图5所示，TGED算法分为用贪心算法进行节点匹配的$T G E D ( G )$ 算法和用 $A ^ { * }$ 算法进行节点匹配的TGED(A)算法。在计算相似性花费时间方面，CFS算法明显高于其他算法，$T G E D ( G )$ 算法所需时间比其他算法都要少，但在准确率方面低于 $T G E D ( A )$ 算法。结合三角不等式满足率得出结论：TGED算法在整体性能表现上略优于其他算法。

在三角不等式满足率上贪心算法略差于穷举算法和 $\boldsymbol { A } ^ { * }$ 算法，但在运行时间上有一定的优势。因此，在对精确度要求很高的情况下，选择 $A ^ { * }$ 算法进行节点匹配，在对精确度要求不高的情况下，则选择贪心算法以节省时间。

![](images/09c5720b04f95228f91fb51273f3ca30b256261652cb3573a57e5fa56b68209f.jpg)  
图4三角不等式满足率对比

![](images/bc85676e16d0e5ec4253e0d85020323e91af70e9a62c7c8b147ae871f931f389.jpg)  
Fig.4Triangle inequality satisfaction rate

# 4.3相似性性质验证

目前已提出的相似性性质主要有顺序结构漂移不变性、并发结构漂移不变性、互斥结构漂移不变性、循环结构漂移不变性、跨度负相关性、非替代无关递减性及循环序列长度负相关性。实验数据模型集为人工编纂的70个流程模型。

性质1顺序结构漂移不变性。无论在顺序结构中哪部分插入新变迁得到新的顺序结构模型，新模型与原模型的相似性均相等。

人工制造一个含有10个变迁的顺序结构模型作为原模型 $N$ ，如图6所示，限于篇幅中间略去部分变迁，在原模型的变迁之间插入新变迁，得到11个新模型，图略。把所有模型转换成变迁图，则每个新模型变迁图到原模型变迁图的编辑距离均为2，即所有新模型与原模型的相似性均为0.913。

性质2并发结构漂移不变性。对流程模型中的顺序结构进行改造，改造成的并发结构分支无论添加在顺序结构的哪部分上，得到的新模型与原模型的相似性均相等。

性质3互斥结构漂移不变性。对流程模型中的顺序结构进行改造，改造成的互斥结构分支无论添加在顺序结构的哪部分上，得到的新模型与原模型的相似性均相等

性质4循环结构漂移不变性。对流程模型中的顺序结构进行改造，改造成的循环结构分支无论添加在顺序结构的哪部分上，得到的新模型与原模型的相似性均相等

其实，前4条性质可以总结为1条性质，即结构漂移不变性，但是有的算法只能满足前4条性质中的一部分，为了加以区分，分开叙述前4条性质。图7中模型 $N _ { \mathrm { 1 } }$ 、 $N _ { 2 }$ 、 ${ \cal N } _ { 3 }$ 分别为按性质2、3、4改造原模型得到的新模型，抽取其中一个在图7中表示，其余不作赘述。对于性质2，无论并发结构分支添加在哪部分上，对应的变迁图编辑距离均为3；对于性质3，无论互斥结构分支添加在哪部分上，对应的变迁图编辑距离均为0.5；对于性质4，无论循环结构分支添加在哪部分上，对应的变迁图编辑距离均为3.5。其中，代价为0.5 的操作均是出自节点替换，即在含一个变迁的节点中插入另一个变迁所需代价。

N:→→⑤ C2 C9 to

![](images/2007b342eb0cca1406d22821e48cf95db69081457db8c1314d4e12766f842574.jpg)  
Fig.5Algorithm running time comparison   
图6人工编纂的原模型,共含有10个变迁其中略去一部分  
图7按性质2、3、4改造原模型得到的新模型

Fig.7New models obtained by modifying original model according to properties 2,3and4

![](images/f89f51e4d5ec21ba39b0046463bfe38ec1e66ff24dac39fbff6b4648496d6b1e.jpg)  
图5算法运行时间对比  
图8相比于 $N _ { 2 }$ 跨度更大的互斥结构

![](images/9dc0d5ae8a3961403e8aa6cc853ea253c7460f6f96d1c0bfd9b82fc771d3ad7e.jpg)  
Fig.6Manually complied original model,there are 1O transitions and skip part   
Fig.8Mutual exclusion structure larger than span of $N _ { 2 }$   
图9非替代无关递减性  
Fig.9Non-replacement-independent decline

性质5跨度负相关性。对模型中顺序结构添加互斥结构分支，该分支在原模型结构上跨度越大，得到的新模型与原模型的相似性越小。

如图8所示，对 $N$ 添加跨度为2的互斥结构得到模型 ${ { N } _ { 4 } }$ ，$s i m ( N _ { 4 } , N ) = 0 . 8 2 0$ ，由前面可知 $s i m ( N _ { 2 } , N ) = 0 . 9 7 6$ ，有 $s i m ( N _ { 4 } , N ) <$ $s i m ( N _ { 2 } , N )$ ，增加互斥结构的跨度，得到另外一系列模型，验证了跨度负相关性的正确性。

性质6非替代无关递减性。对模型中顺序结构添加互斥结构分支，添加的分支越多，得到的新模型与原模型的相似性越小。

性质7循环序列长度负相关性。对流程模型中的顺序结构进行添加循环结构改造，循环结构的跨度越大，得到的新模型与原模型的相似性越小。

如图9所示，模型 ${  { N _ { 5 } } }$ 为在 $N$ 上同一部分添加两个互斥分支，在 $\boldsymbol { N } _ { 2 }$ 上互斥结构部分再添加一个互斥分支，有$e d i s ( N _ { 5 } , N ) > e d i s ( N _ { 2 } , N )$ ，即 $s i m ( N _ { 5 } , N ) < s i m ( N _ { 2 } , N )$ 。性质7与性质5类似，实验验证TGED相似性满足所有7种相似性性质。

表1为各算法对7种相似性性质的满足情况，V表示满足， $\times$ 表示不满足。由表1可知， $T A R + +$ 、SSDT、CFS算法和TGED算法(本文算法)满足所有相似性性质，SSDT算法每次计算流程相似性的时候，需要根据矩阵的秩进行对应的扩展确保两个矩阵的秩相等； $C F S$ 算法会对并发任务导致的所有可能执行序列进行逐一枚举。因此，和CFS算法运行时间过长。

$T A R + +$ 算法运行时间稍长于TGED算法，但 $T A R + +$ 算法用深度优先搜索方法为紧邻变迁关系分配重要性，算法的最坏时间复杂度为 $O ( V + E + N ! )$ ，最坏情况往往会出现。结合各算法的三角不等式满足率和运行时间进一步得出结论：TGED算法略优于其他算法。

表1各算法对相似性性质的满足情况

Table1Satisfaction of similarity properties of each algorithrr   

<html><body><table><tr><td colspan="6">性质1 性质2 性质3 性质4 性质5 性质6 性质7</td></tr><tr><td>TAR++[5]</td><td>√</td><td>√ √</td><td>√</td><td>√</td><td>√ √</td></tr><tr><td>TAR[7]</td><td>×</td><td>√ ×</td><td>√</td><td>×</td><td>√ ×</td></tr><tr><td>BP[8]</td><td>√ √</td><td>√</td><td>√</td><td>× √</td><td>√</td></tr><tr><td>SSDT[4]</td><td>√ √</td><td>√</td><td>√</td><td>√</td><td>√ √</td></tr><tr><td>CF[10]</td><td>√</td><td>√ ×</td><td>×</td><td>×</td><td>√ √</td></tr><tr><td>CFS[13]</td><td>√ √</td><td>√</td><td>√</td><td>√</td><td>√ √</td></tr><tr><td>TGED(本文 方法)</td><td>√</td><td>√ √</td><td>√</td><td>√</td><td>√ √</td></tr></table></body></html>

# 5结束语

为了提高从企业模型库中查询和检索模型的效率，解决已有流程相似性算法存在的一些问题，本文提出基于变迁图编辑距离的流程相似性算法。该算法通过把模型转换成简单的变迁图，计算最小变迁图编辑距离，得出相似性。另外，本文首次提出了边的长度概念，删除和插入边的代价由边的长度决定，基于此定义了图编辑操作代价，并用贪心算法和$A ^ { * }$ 算法计算最小图编辑距离。通过实验证明了本文算法整体性能上略优于其他算法。

未来，希望通过深入研究各种相似性度量方法，扩展相似性性质，优化TGED算法或提出新的更好的算法，使相似性更加贴近领域专家的评估结果。

# 参考文献：

[1]Lu Yahui,Yu Haofei,Ming Zhong,et al.A similarity measurement based on structure of business process [C]// Proc of IEEE International Conference on Computer Supported Cooperative Work in Design. 2016: 498-503.   
[2]Montani S,Leonardi $\mathbf { G }$ Quaglini S,et al.A knowledge-intensive approach to process similarity calculation [J]. Expert Systems with Applications,2015,42 (9): 4207-4215.   
[3]Wang Jianmin,Jin Tao,Wong R K,et al.Querying business process model repositories[J].World Wide Web-internet & Web Information Systems,2014,17 (3): 427-454.   
[4]汪抒浩，闻立杰，魏代森，等．基于任务最短跟随距离矩阵的流程模 型行为相似性算法[J].计算机集成制造系统，2013，19(8): 1822-1831.(Wang Shuhao，Wen Lijie,Wei Daiseng，et al．SSDT matrix-based behavior similarity algorithm for process model [J]. Computer integrated manufacturing system,2013,19 (8): 1822-1831. )   
[5]殷明，闻立杰，王建民，等．基于变迁紧邻关系重要性的流程相似性 算法[J].计算机集成制造系统，2015,21(2):344-358.(Yin Ming, Wen Lijie,Wang Jianmin,et al.Process similarity algorithm based on importance of transition adjacent relations [J]. Computer integrated manufactu-ring system,2015,21 (2): 344-358.)   
[6]王子璇，闻立杰，汪抒浩，等．基于变迁标签图编辑距离的过程模型 相似性度量[J].计算机集成制造系统,2016,22(2):343-352.(Wang Zixuan,Wen Lijie,Wang Shuhao,et al. Similarity measurement for process models based on transition-labeled graph edit distance [J]. Computer integrated manufacturing system,2016,22(2): 343-352.)   
[7]Zha Haiping,Wang Jianmin,Wen Lijie,et al.A workflow net similarity measure based on transition adjacency relations [J].Computers in Industry,2010,61 (5): 463-471.   
[8]Weidlich M,Elliger F,Weske M.Generalised computation of behavioural profiles based on Petri-net unfoldings [M]// Web Services and Formal Methods.Berlin: Springer,2010:101-115.   
[9]Dijkman R,Dumas M. Graph matching algorithms for business process model similarity search [C]// Proc of International Conference on Business Process Management.[S.l.]:Springer-Verlag,20o9: 48-63.   
[10]Dijkman R,Dumas M,Dongen BV,et al. Similarity of business process models: metrics and evaluation [J]. Information Systems,2011,36 (2): 498-516.   
[11]Jin Tao,Wang Jianmin,Wen Lijie.Efficiently querying business process models with beehiveZ[Cl//Proc of Demo Track of the 9th Conference on Business Process Management.2011.   
[12]武年华，金涛，查海平，等．BeehiveZ:一个开放的业务过程模型管 理框架[J].计算机研究与发展,2010,47(z1):450-454.(Wu Nianhua, Jin Tao,Cha Haiping,et al. BeehiveZ: an open business process model management framework.[J]. Computer Research and Development, 2010, 47 (z1): 450-454. )   
[13]Dong Zihe,Wen Llijie,Huang Haowei,et al.CFS:a behavioral similarity algorithm for process models based on complete firing sequences [J]. Journal of Software,2015: 202-219.