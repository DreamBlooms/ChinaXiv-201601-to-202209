# 一种用于Android应用的反控制混淆系统

曹宏盛，焦健，李登辉(北京信息科技大学 计算机学院，北京 100101)

摘要：Android 恶意软件中的控制混淆技术，可以增加传统 Android应用软件执行路径检测的难度，是目前代码静态分析的主要困难之一。针对该问题进行了研究，并设计系统DOCFDroid用于解决此问题。该系统在预处理阶段获取CFG关系矩阵，使用深度优先查找待分析路径集合；依据用户给定的源点集合和终节点集合，得到粗糙路径；然后采用权重筛选的算法，可以有效的获取目标路径集合。在实验阶段以DroidBench 1.2为基础构建测试样本集，验证该方法的有效性。实验结果表明，该方法能有效抵抗控制流混淆带来的干扰，目标路径识别率可达 $9 5 . 3 1 \%$ 。

关键词：反控制混淆；Android；控制混淆；路径查找 中图分类号：TP309.1 doi:10.3969/j.issn.1001-3695.2017.12.0759

# Deobfuscation system for Android applications

Cao Hongsheng, Jiao Jian,Li Denghui (Computer School ofBeijing Information Science&Technology University,Beijing 10o101,China)

Abstract: Controlobfuscation can greatlyincreasethe dificultyondetecting implementationpathof Android application,nd also is theoneofthemain diffculties oncurrentcode static analysis.Thisarticlehadcarriedontheresearchtothisquestion anddesignedasystemDOCFDroidusedto solvethis problem.The systemobtained the CFGrelation matrix inthe pretreatment stage,andusedthedepth-fistalgorithmtofidthesetofthepath.Acordingtothesetofsourepointsandthesetofendpoints, thecoarsepath wasobtained.Thealgorithmof weightscreening could efectivelyobtainthe targetpathset.Basedonthesample setDroidBenchl.2,thetestsampleset was furtherconstructedtoverifythevalidityofthis method.Theexperimentalresults showthatthesystemcanefectivelyresisttheinterferencecausedbycontrolobfuscation,andtherecognitionrateoftargetpath can reach $9 5 . 3 1 \%$ ：

Key Words:control flow deobfuscation; android; control flow obfuscation; path detection

# 0 引言

混淆技术的出现可以帮助隐藏代码内部的真实信息，最早应用于软件反分析和防盗版领域，但随着近年来恶意代码的泛滥，越来越多的黑客都会采用代码混淆技术来“躲避”检测工具。由于目前针对恶意代码的检测方法主要基于特征码的方式，混淆技术的大量使用可以有效隐藏自身的特征，躲避防病毒工具的查杀，加剧了分析过程的时空复杂性，造成特征码的数量日益庞大，使代码检测的时效性和准确都受到了严重的影响。

在通用的混淆技术中，目前比较常用且难以防范的是控制流混淆，其目的[1]是改变或复杂化程序的控制流，使程序更难以破译。控制混淆通过改变控制流图(CFG)的结构，达到混淆目的。按照其实方式控制混淆又可分为重打包、字节码控制和插入冗余分支等多种实现技术。文献[2,3]将控制混淆方法分为三类，分别是：计算混淆、排序混淆和聚合混淆，如表1所示。

表1控制混淆分类  

<html><body><table><tr><td></td><td>内联法</td></tr><tr><td>计算混淆</td><td>全局声明 克隆法</td></tr><tr><td rowspan="4">排序混淆</td><td>循环展开</td></tr><tr><td>声明重排序</td></tr><tr><td>循环重排序</td></tr><tr><td>表达式重排序</td></tr><tr><td rowspan="2">聚合混淆</td><td>循环条件扩展</td></tr><tr><td>转变成不可还原流程图表解析</td></tr></table></body></html>

由于控制混淆的多样性和易于实现的特点。越来越多的恶意代码普遍采用控制混淆技术逃避安全分析和检测，针对恶意代码的反混淆技术已经成为代码安全的关注热点。

Baumann等人[4提设计了一个Anti-ProGuard的一个原型实现，使用软件相似度算法检测混淆之后的恶意软件。文献[5]提出了一套抗混淆的恶意应用变种识别系统，包括行为分析、特征提取和恶意应用识别三个主要部分。其方法通过实现高透明度监控，分析代码行为，提取关键行为逻辑和抗干扰处理，实现对恶意应用变种的识别，但该文采用的动态污点分析，对资源和时间要求较大。文献[6]提出了检测系统DroidChameleon，它能够对检测出重打包、字节码控制混淆技术的应用。文献[7]提出的检测工具ViewDroid同样也是针对Android平台重打包后的应用进行检测。文献[8]提出了一种抗混淆的Android应用相似性检测方法。其思路是提取Android应用内特定文件的内容特征计算应用相似性。文献[9]目的是检测恶意软件是否属于同一家族，使用API调用及数据依赖关系描述特征，结合语义和统计学习进行检测，降低了部分代码混淆技术干扰，但分析复杂度较高。文献[10]提出的检测工具AppFence 结合了MockDroid和TISSA，采用了与TaintDroid类似的针对污点分析方法，能够检测经过混淆、加密的信息泄露。这些文献对恶意应用的识别方面提出有效的方法，但并不能给出恶意软件混淆前后的功能实现路径，分析人员无法分析应用在混淆前后的行为和运行过程。文献[11]使用CFG（ControlFlowGraph:控制流图）表示行为特征，通过分析同构CFG对抗部分混淆，该文引用CFG来解决混淆问题，但还是没有给出恶意应用混淆前后的功能实现路径。

从目前的研究结果可知，基于特征识别的传统方法已经无法满足现有反混淆需求，需要以行为特征为主要的分析方法，通过识别恶意应用的实际行为，达到抵抗混淆技术干扰的目的。文献[2]给出混淆的定义特别指出代码混淆不改变原程序的功能，因此混淆前后总能有一条实现程序功能的路径。本文以此为基础开展相应的研究，引用了source-sink机制，利用敏感函数定位source 和sink，并构建了恶意应用的CFG，最后检测出目标路径(实现原功能)。

# 1 问题分析

控制流图由基本块和有向边两类元素组成。对于程序原有的某些特定功能，总存在能从起始节点到达终止节点的路径。因此，对混淆之后的应用，查找实现原有功能的执行路径是可行的。为了便于说明，构建了如图1所示的CFG控制混淆处理前后的示例，图中的圆形表示CFG中的基本块，有向边表示控制流，其中标志为S的基本块为起始基本块；标志为E的基本块为终结基本块。

图1的 normal 所示，可达路径有 path $\mathrm { _ { 1 } l } { = } \{ \mathrm { S } , 1 , 2 , 3 , \mathrm { E } \}$ ，path2 $: =$ {S,1,4,2,3,E}， $\mathrm { \ p a t h { 3 = } \{ S , 1 , 4 , 5 , E \} }$ 和p $\mathrm { a t h } 3 { = } \{ \mathrm { S } , 1 , 4 , 5 , \mathrm { E } \}$ ，则对应的路径集合为paths $\left. \vert = \right.$ {path1,path2,path3}，可知 paths 中皆为可达路径。假设该应用输入数据为in，执行结果为out，数据作用于paths的可达路径必能够得到执行结果out。

如图1的obfuscate所示为经过控制混淆后所得的CFG，产生了不可达路径path4 $\vDash$ {S,1,6,7}、path5 $\begin{array} { r } { \mathsf { j } = } \end{array}$ {S,1,2,7}、path $\mathrm { 6 = \{ S , 1 , 2 , 7 , 8 \} }$ 和 $\operatorname { p a t h 7 } \mathrm { = } \{ \mathrm { S } , 1 , 2 , 8 , 9 \}$ ，而path1变为path $\mathrm { 3 = \{ S , 1 , 2 , 8 , 3 , E \} }$ ，path2 变为 $\mathrm { p a t h 9 = \{ S , 1 , 4 , 2 , 8 , 3 , E \} }$ ，最终的路径集合为 paths'={path3,path4,path5,path6,path7，path8path9}。不可达路径集合pathinvalid={path4,path5,path6,path7}给逆向分析工作制造障碍。

![](images/7ab700ee0f7e2feefe354282b7f864a3fc5d8f7d15f5a889d69a73c9ade53e39.jpg)  
图1示例控制流图

其中paths 和paths'是同一个应用对应的两个不同的路径集合，paths'是根据混淆后代码的CFG求得的路径集合。根据source-sink 机制，其中 ${ \mathfrak { n } } _ { s }$ 表示该基本块包含源点，下标s属于源点集合Source， $ { \mathbf { n } } _ { d }$ 表示该基本块包含终节点，下标d属于终节点集合 Sink，因此，反混淆的本质问题是如何从paths'中尽可能地还原出paths。即表示从代码中找到从 ${ \mathfrak { n } } _ { s }$ 到 ${ \mathbf { n } } _ { d }$ 的可达路径pathsd构成的集合（记作Pathsource_sink）。

pathsd根据函数分为两类：一类 $n _ { s }$ 和 $n _ { d }$ 在同一个函数中；另外一类是 $n _ { s }$ 和 $n _ { d }$ 分别在不同函数中，具体可以分为两种情况：

a） $n _ { s }$ 和 $n _ { d }$ 中的变量，在本函数的其他基本块中也有操作处理，通过 $n _ { s }$ 和 $n _ { d }$ 中的变量，分别查找 $n _ { s }$ 和 $n _ { d }$ 所在函数中关于其变量的路径;

b） $n _ { s }$ 或 $n _ { d }$ 中的变量，在本函数的其他基本块中没有操作处理，输出 $n _ { s }$ 和 $n _ { d }$ 所在的函数名以及基本块序号。

# 2 系统设计

# 2.1 预处理阶段

基于CFG的Android应用反控制混淆方法的系统（如图2所示，在系统地第一阶段主要完成数据预处理，在1.1中，系统将指定的安装文件，通过反编译抽取出其中class.des 和mainfirst.xml文件，并根据这些文件，生成 SSA(Static Single-Assignment:静态单赋值）文件。1.2阶段使用SSA，并根据用户的需求，生成相应的CFG。

![](images/9c3b499cd2ccebd7149c774493666b26f106965bc2de7251e2ab30c4f81f8bff.jpg)  
图2系统结构图

CFG可以将其表示成矩阵形的形式，称为CFRM（ControlFlowRelationMatrix：控制流关系矩阵)，二者形式定义如下：

$C F G = { \big ( } E , N { \big ) }$ ，其中E为有向边集合， $\mathsf { N } { = } \{ \mathrm { M } , \mathrm { ~ V } , \mathrm { ~ t } \}$ 为基本块（图中的节点）集合，其中 $\mathbf { \delta M }$ 为方法/函数集合，V为变量集合，t为分支数，其中 $\mathrm { \Omega } ^ { \mathrm { t } \geq 0 }$ 。

$C F R M = { \big ( } R , N { \big ) }$ ， $\mathrm { ~ N ~ }$ 是CFG 中基本块集合；R是一个二维矩阵，即从NxN 到 $\left\{ 1 , \quad 0 \right\}$ 的映射，称为N上的二元关系；$\forall ( n _ { \ i } , n _ { \ i } ) \in N \times N$ 。

# 2.2 查找路径阶段

系统的第二阶段主要作用是根据预处理模块得到的CFG，检测出符合用户当下需求的路径(功能路径)。具体分为三个部分：

# 2.2.1查找敏感基本块

敏感基本块查找功能（如图2的2.1所示)。在查找敏感基本块之前，先在预处理得到的CFG的基础上，生成CFRM。

设计算法CONSTRAINT_VALUE。该算法找出所有包含源点元素以及终节点元素的敏感基本块集合(起始基本块集合和终结基本块集合)，并取两者中的元素个数大的值作为路径条数约束值rconstraint

算法的输入分别是：CFRM，SETs源点元素集合以及 $S E T _ { d }$ 的终点元素集合，两者都为一些特征集，用于匹配查找敏感基本块；输出：约束值rconstraint o

以下是该算法的伪代码：

CONSTRAINT_VALUE(CFRM, SETs,SETd)

1 $s = 0$ （204号   
2 $d = 0$   
3 $N _ { d } = \mathcal { O }$   
4 $N _ { s } = \emptyset$

5 for each n $\ r \in \ r _ { \ r }$ CFRM.N//遍历CFG中的基本块

6 for each $\ l _ { \textsc { m } } \in \ l _ { \ n . \mathbf { M } }$ //遍历基本块中的表达式  
7 （20 $\mathbf { i f } \mathrm { m } \in \mathrm { ~ S E T _ { d } ~ }$ //表达式含有终点元素  
8 $\begin{array} { l } { { N _ { d } = N _ { d } \cup n } } \\ { { } } \\ { { s + = 1 } } \end{array}$   
9  
10 else if $\mathrm { ~ m ~ } \in \ \mathrm { S E T _ { s } }$ //表达式含有源点元素  
12 $\begin{array} { l } { N _ { s } = N _ { s } \cup n } \\ { \qquad } \\ { d \mathrm { + } = 1 } \end{array}$   
13  
14 store $\mathrm { N _ { s } }$   
15 store $\mathrm { N _ { d } }$ （204号  
16 return max(s,d)

算法通过遍历CFRM，根据SETs源点元素集合以及SETd的终点元素集合，将找到的敏感基本块分别保存，这些敏感基本块用于在后面粗糙路径查找中定位source-sink，通过定位source-sink，缩小了图查找的范围，有益于提高查找的效率。最后max(s,d函数来返回约束值，用于限定最后查找到的目标路径数量。

# 2.2.2查找粗糙路径

系统的2.2阶段主要实现查找粗糙路径。以图1中的CFG为例，混淆后的路径集合：

paths $\scriptstyle \prime = \left\{ \begin{array} { l l } { \begin{array} { r l r l } \end{array} } \end{array} \right.$ path3,path4,path5,path6,path7,path8,path9}。

根据 $n _ { s }$ 和 ${ \mathbf { n } } _ { d }$ 的元素组合，使用深度优先算法对paths集合进行裁剪，得到粗糙路径集合 $P a t h _ { c o a r s e }$ ，记作：

$$
\begin{array} { r l } & { P a t h _ { _ { c o a r s e } } \subseteq P a t h ^ { \prime } , \forall p _ { i } \in P a t h _ { _ { c o a r s e } } , } \\ & { \exists n _ { j } \in N _ { s } , n _ { k } \in N _ { d } , j \le k , } \end{array}
$$

算法的输入是：CFRM，起始基本块集合 $N _ { s }$ 以及终结基本块集合 $N _ { d }$ ；输出为：Pathcoarseo

算法伪代码如下：

GENERATE_COARSE_PATH_SET(CFRM, $\Nu _ { \mathrm { d } } , \Nu _ { \mathrm { s } } )$   
1 $P A T H _ { _ { t m p } } = \emptyset$   
2 $P a t h _ { _ { c o a r s e } } = \emptyset$   
3 for each $\ l _ { \textsc { n } } \in \ l _ { \textsc { N } _ { \mathrm { d } } }$ （204号  
//使用深度优先查找包含终结基本块的路径  
4 （20 $\mathrm { P A T H } _ { \mathrm { t m p } } { = } \mathrm { P A T H } _ { \mathrm { t m p } } \mid$ JGENERATE_DFS (CFRM.R,n)  
5 for each $\rho \in \mathrm { \ P A T H _ { \mathrm { t m p } } }$ （20  
//在 $\mathrm { P A T H _ { t m p } }$ 基础上查找包含起始基本块的路径  
6 for each m ∈ p  
7 $\mathbf { i f } \mathrm { m } \in \mathrm { \Delta N } _ { \mathrm { s } }$ （204  
8 $P a t h _ { _ { c o a r s e } } = P a t h _ { _ { c o a r s e } } \cup p$   
9 break  
10 return Pathcoarse

通过上一小节得到的敏感基本块，使用深度优先算法遍历CFRM.R二维矩阵得连通 source和 sink的路径,并存到Pathcoarse。Pathcoarse是整个CFG路径的子集，该算法进一步缩减了裁剪范围，获得更精确的目标路径。

以图1中的CFG为例，混淆后的路径集合：

paths $\scriptstyle \prime = \left\{ \begin{array} { l l } { \begin{array} { r l r l } \end{array} } \end{array} \right.$ path3,path4,path5,path6,path7,path8,path9}。

经过算法处理paths路径集合的CFG，得到粗糙路径集合Pathcoarse的CFG，如图3所示。

从图3可以看出，包含基本块6、7、9的路径，并没有同时包含起始基本块(S基本块)和终结基本块(E基本块)。通过对粗糙路径查找，将这些无关基本块剔除，得到粗糙路径集合，表现如图3的 $P a t h _ { c o a r s e }$ 的CFG所示。

# 2.2.3查找目标路径

系统2.3阶段主要功能,通过算法OPTIMIZE_PATH_SETO,计算各个粗糙路径的权重，然后根据权重筛选粗糙路径Pathcoarse得到目标路径Pathsource_sink 。

![](images/b28afc0d7b554bea4ce80b88ce3d46b783883b14b77f21c51ac9d74a001b5cb7.jpg)  
图3示例混淆路径集合paths剪枝

该算法主要分成三个步骤：

a)从粗糙路径集合中查找出每条路径的起始基本块以及终结基本块中的所有变量，伪代码中表示为FIND_RELATED_VAR(p)，然后为变量赋予权值1;

b)计算每条粗糙路径p的每一个基本块的权重，将这些权重相加得到路径p的权重，并将路径p的权重添加到权值集合W中;

c)将W集合中的元素按照从大到小排序，按照约束值rconstraint选取出前t条权值大的路径作为目标路径。

根据算法2.1，由 $\mathbf { N } _ { S }$ （起始基本块集合）和 $N _ { d }$ （终结基本块集合）元素的个数，得到的约束值rconstraint取值为1，得到目标路径集合Pathsource_sink。如图4所示，对Pathcoarse做路径权重排序之后，再结合 $r _ { c o n s t r a i n t } { = } 1$ ，优先选择第一条权重大的路径作为目标路径，得到目标路径集合Path source_sink 。

![](images/48d2f0779f353952adddcc3af16c38a492285f23a0e34f8ef095cf3d835d152c.jpg)  
图4示例粗糙路径集合 $P a t h _ { c o a r s e }$ 剪枝

算法的输入分别是粗糙路径集合Pathcoarse，以及约束值Yconstraint；算法的输入出为目标路径Path source_sink 。 算法伪代码如下所示：

1 W=Ω  
2 PATHsource_sink =  
3 for each p $\ r \in \ r _ { \ r }$ Pathcoarse  
4 $w _ { p } = 0$ （20  
//获取路径中的敏感变量集合  
5 （ $\mathbf { v } = { }$ FIND_RELATED_VAR(p)  
6 for each n ∈ p  
//敏感变量在路径中出现的次数，计算路径权值  
7 $\begin{array} { r } { \mathrm { \Delta ~ w _ { p } + ~ = ~ T y p e ~ ( n ) * I s V a r E x i s t { \left( v , n \right) * _ { W _ { v } } } } } \end{array}$   
8 $W = W \cup \left. w _ { p } , p \right.$   
//权值排序  
9 $W ^ { ' } { = } \mathrm { D E S C E N D } { \_ } \mathrm { S O R T } ( W )$   
//由约束值获取前t个路径，作为目标路径  
$1 0 \ \mathrm { P a t h } _ { \mathrm { s o u r c e } _ { - } \mathrm { s i n k } } = \mathrm { P a t h } _ { \mathrm { o u r c e } _ { - } \mathrm { s i n k } } \cup \ \{ \mathrm { p } _ { \mathrm { i } } \ : | \ \langle _ { \mathrm { W } _ { \mathrm { p } } } , \mathrm { p } _ { \mathrm { i } } \rangle \in \mathbb { W } ^ { \prime } \ , \ \mathrm { i } \leqslant \mathrm { r } _ { \mathrm { c o n s t r a i n t } } \} \quad \}$   
11 return Pathsoure_sink

该算法从表达式和变量这两个层次去给得到的粗糙路径进行权重计算和优先级划分。通过敏感变量计算路径权重的方式，这一思路能够有效并快速地划分各个粗糙路径的优先级，从而得到目标路径。

# 3 实验验证

为验证算法在检测控制混淆后的Android应用路径的可行性与有效性，设计并实现了系统DOCFDroid，开发工具基于Eclipse4.5.2、JDK1.8、基础框架Soot。检测系统中识别source和 sink所采用的特征集来源于文献[12]。

# 3.1 DOCFDroid功能展示

本文实验采用的样本集为：混淆后的DroidBench1.2样本集[13]：在DroidBench1.2数据集的基础上，使用混淆技术进一步构建的样本集。DroidBench1.2的59个开源的Android应用共包含52个人工注入的信息泄露漏洞，包括数组与列表的下标混淆，ICC（Inter-componentCommunication：进程通信组件）、代码混淆、反射以及隐式泄露等，已知漏洞所分布的数量和位置，并且包含一些误报陷阱，用于评估检测系统的误报率。该数据集已成为Android信息泄露检测公认数据集，且围绕该数据集已进行了多项高水平研究。本文在DroidBench1.2数据集的基础上，进一步使用混淆技术构建本实验的测试样本数据集。

实验方法如下：使用多种控制混淆方法包括，循环条件扩展，插入冗余分支等，人为混淆样本集代码。样本集CFG混淆前后及路径查找对比如图5、图6和图7所示。

如图5所示。左边的图是由样本“PrivateDataLeakl.apk”中泄漏信息的函数源码生成的CFG，该CFG展示了该函数的所有基本块及其代码中间表示；图右边为未混淆的软件源代码，可以看到代码整体是一个if语句，并且if语句中只有一个for循环语句分支。该代码主要通过获取用户的日志数据和手机消息，并把这些数据发送至远程服务器，达到目标信息泄漏的目的。

Sr0 := @this \$r1 := @parameter() 5r2 = St0.user i Se2mm null gotolabe Ssesg puivi Sr4 = \* label3: String password = getPassword(); s5=\$sagcbgaa return String obfuscatedUsername =""; H frs label: if Si2 < Sil goto labe12 String message = "User: " + user.getUsername() + \* | Pwd: " + obfuscatedUsermame; latel2z SmsMagaDeae   
Sr=5s   
Ss6=Ssaeal| a message, null, null); //sink, leak   
\$r4 = Sr6.toString() 5r6= Se6 append(2_) ） s=s 1   
s goto label1 未混淆的源代码 void sendMessage(android.view.View) 未混淆源代码的CFG

![](images/081f69e2a91c25f4cd5af0985d7acf2024fa87c9a2f671c8aea4237d525b8321.jpg)  
图5未混淆的源代码及其CFG

![](images/48f7ec20a38852b05073730a65a23ec6dfd298636bb75c6aefaeba89e7c721c6.jpg)  
图6混淆后的源代码及其CFG  
图7路径查找

如图6所示。图右边为混淆后的软件源代码，在源代码，本文插入了一个冗余的switch语句分支和if语句分支，使函数原来实现功能的路径变得复杂，如椭圆标志部分所示。两个语句中用于做条件判定的函数func1(永远取值为3，因此程序还是执行原来的代码，函数功能未改变。但是，达到了混淆代码的目的，使得代码分析增加了难度。系统DOCFDroid 通过检测混淆后的应用，得到该应用源代码的CFG（图5左边)，与图5比对，可以看到图中多出一些分支，如图中椭圆标志部分所示。

系统DOCFDroid处理之后到的目标路径(图7椭圆圈出的基本块组成)，一样能够实现“PrivateDataLeak1.apk”通过获取用户的日志数据和手机消息，并把这些数据发送至远程服务器，达到目标信息泄露的目的。

经反控制混淆路径查找之后，找到了可以实现函数原本功能的基本块。这些基本块可能并不与原来的基本块数量完全一致，但是这些基本块组合而成的路径同样能够实现函数原本的功能。如图中椭圆标志部分所示，基本块 $\textcircled{1}$ 、 $\textcircled{2}$ 对应未混淆源代码的 for 循环语部分；基本块 $\textcircled{3}$ 为变量“message”的赋值；基本块 $\textcircled{4}$ 对应代码“Log.i("TEST","sendSMS");"，用于获取日志数据；基本块 $\textcircled{5}$ 为本文插入的 switch 语句；基本块 $\textcircled{6}$ 对应未混淆的源代码“smsmanager.sendTextMessage( $" \mathrm { + } 4 9 ~ 1 2 3 4 "$ ， null,message,null,null)；"，用于实现信息数据的发送，达到目标数据泄露的目的。

# 3.2性能比较

DroidBench1.2的实验结果如表2所示。从结果可以看出，未经过混淆的59个样本数据集总共有64条目标路径。实验对此59个混淆之后的APK文件进行路径检测实验，可识别出61条目标路径，识别率为 $9 5 . 3 1 \%$ ，其中Libraryl（只有 source）和LogNoLeak（只有sink）不符合本文的目标路径条件，看成无效样本数据。如表2所示，漏报率为 $4 . 6 9 \%$ ，路径漏报的样本数据集有ImplicitFlow2、ImplicitFlow3、ImplicitFlow4。分析原因为在计算路径权值时，未能找到对应变量，重复对首个路径变量赋值，导致路径筛选失败。实验的误报率为 $6 . 2 5 \%$ 路径误报的样本数据集有LocationLeak3、Button2和ImplicitFlow1。分析发现，使用的污点源识别库导致部分识别出来的起始基本块和终结基本块，多于样本集中标注的source 和sink，导致目标路径个数比原样本集数据中的路径更多。

# 4 结束语

目前的研究大多基于特征识别的传统方法，该方法已经无法满足现有反混淆需求，通过行为特征为主要的分析方法，识别恶意应用的实际行为，达到抵抗混淆技术干扰的目的。本文提出并实现了反控制混淆系统DOCFDroid，检测出混淆前后应用功能的实现路径。本文的主要研究工作集中在两点：第一、依据混淆的定义[2]以及控制混淆[1]目的，论述对控制混淆后的软件路径检测的可行性，将反控制混淆问题转变为控制流图(controlflowgraph)的路径查找问题，从图论的角度提出了反控制混淆的方法;第二，利用源点和终节点集合确定目标路径的起始节点和终止节点，简化并有效地提高粗糙路径的检测；使用权重筛选的算法进行路径优化，去除冗余粗糙路径，提高目标路径的识别率，实验表明，系统对目标路径的识别率达到$9 5 . 3 1 \%$ 。对检测控制混淆后的Android数据集时，能够有效识别出目标路径，有效降低误报与漏报。

下一的研究内容主要包括：a）完善路径权重计算算法，进

一步降低由路径变量查找失败导致的漏报率；b)筛选或者构建 更完善的source、sink识别库，进一步降低的误报率。

表2DroidBench1.2数据集实验结果  

<html><body><table><tr><td rowspan="2">样本名</td><td>原始目标</td><td>混淆后目标</td><td>处理后</td><td rowspan="2">准确识别</td><td rowspan="2">样本名</td><td>原始目标</td><td>混淆后目标</td><td>处理后</td><td>准确识</td></tr><tr><td>路径条数</td><td>路径条数 路径条数</td><td>路径条数</td><td>路径条数</td><td>路径条数</td><td>路径条数</td><td>路径条</td></tr><tr><td>DirectLeak*</td><td>1</td><td>48</td><td>1</td><td>1</td><td>ObjectSensitivity2</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>InactiveActivity</td><td>1</td><td>1331</td><td>1</td><td>1</td><td>Exceptions1</td><td>1</td><td>21</td><td>1</td><td>1</td></tr><tr><td>Library1</td><td>0</td><td>231</td><td>0</td><td>0</td><td>Exceptions2</td><td>1</td><td>21</td><td>1</td><td>1</td></tr><tr><td>Library2</td><td>1</td><td>231</td><td>1</td><td>1</td><td>Exceptions3</td><td>1</td><td>21</td><td>1</td><td>1</td></tr><tr><td>LogNoLeak</td><td>0</td><td>231</td><td>0</td><td>0</td><td>Exceptions4</td><td>1</td><td>21</td><td>1</td><td>1</td></tr><tr><td>Obfuscation1</td><td>1</td><td>231</td><td>1</td><td>1</td><td>Loop1</td><td>1</td><td>252</td><td>1</td><td>1</td></tr><tr><td>PrivateDataLeak1</td><td>1</td><td>2783</td><td>1</td><td>1</td><td>Loop2</td><td>1</td><td>234</td><td>1</td><td>1</td></tr><tr><td>PrivateDataLeak2</td><td>1</td><td>231</td><td>1</td><td>1</td><td>SourceCodeSpecifi c1</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>PrivateDataLeak3</td><td>2</td><td>231</td><td>2</td><td>2</td><td>StaticInitialization1</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>ArrayAccess1</td><td>1</td><td>231</td><td>1</td><td>1</td><td>UnreachableCode</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>ArrayAccess2</td><td>1</td><td>231</td><td>1</td><td>1</td><td>ImplicitFlow1</td><td>1</td><td>231</td><td>2</td><td>1</td></tr><tr><td>HashMapAccess1</td><td>1</td><td>231</td><td>1</td><td>1</td><td>ImplicitFlow2</td><td>2</td><td>231</td><td>1</td><td>1</td></tr><tr><td>ListAccess1</td><td>1</td><td>231</td><td>1</td><td>1</td><td>ImplicitFlow3</td><td>2</td><td>462</td><td>1</td><td>1</td></tr><tr><td>AnonymousClass1</td><td>1</td><td>231</td><td>1</td><td>1</td><td>ImplicitFlow4</td><td>2</td><td>2772</td><td>1</td><td>1</td></tr><tr><td>Button1</td><td>1</td><td>231</td><td>1</td><td>1</td><td>IntentSink1</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>Button2</td><td>1</td><td>231</td><td>3</td><td>1</td><td>IntentSink2</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>Button3</td><td>1</td><td>231</td><td>1</td><td>1</td><td>ActivityLife1</td><td>2</td><td>231</td><td>2</td><td>2</td></tr><tr><td>LocationLeak1</td><td>1</td><td>231</td><td>1</td><td>1</td><td>ActivityLife2</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>LocationLeak2</td><td>1</td><td>231</td><td>1</td><td>1</td><td>ActivityLife3</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>LocationLeak3</td><td>1</td><td>231</td><td>2</td><td>1</td><td>ActivityLife4</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>MethodOverride1</td><td>1</td><td>231</td><td>1</td><td>1</td><td>ApplicationLife1</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>MultiHandlers1</td><td>2</td><td>231</td><td>2</td><td>2</td><td>ApplicationLife2</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>Ordering1</td><td>1</td><td>231</td><td>1</td><td>1</td><td>ApplicationLife3</td><td>2</td><td>231</td><td>2</td><td>2</td></tr><tr><td>Unregisterl</td><td>1</td><td>231</td><td>1</td><td>1</td><td>BroadcastLifecycle 1</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>FieldSensitivity1</td><td>1</td><td>231</td><td>1</td><td>1</td><td>SeviceLifecycle1</td><td>1</td><td>21</td><td>1</td><td>1</td></tr><tr><td>FieldSensitivity2</td><td>1</td><td>231</td><td>1</td><td>1</td><td>Reflection1</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>FieldSensitivity3</td><td>1</td><td>231</td><td>1</td><td>1</td><td>Reflection2</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>FieldSensitivity4</td><td>1</td><td>231</td><td>1</td><td>1</td><td>Reflection3</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>InheritedObjects1</td><td>1</td><td>231</td><td>1</td><td>1</td><td>Reflection4</td><td>1</td><td>231</td><td>1</td><td>1</td></tr><tr><td>ObjectSensitivity1</td><td>1</td><td>231</td><td>1</td><td>1</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>总计</td><td>30</td><td>10399</td><td>33</td><td>30</td><td></td><td>34</td><td>8445</td><td>32</td><td>31</td></tr><tr><td>原始目标路径总数：64</td><td></td><td></td><td></td><td>处理后路径总数：65</td><td></td><td></td><td></td><td>准确识别路径总数：61</td><td></td></tr></table></body></html>

# 参考文献：

[1]王建民，余志伟，王朝坤，等.Java 程序混淆技术综述[J].计算机学报,2011,34(9): 1578-88.

[2] Collberg C，Thomborson C，Low D.A taxonomy of obfuscating transformations [R].Auckland: University of Auckland,1997.   
[3]Hoffmann J,Rytilahti T,Maiorca D,et al.Evaluating analysis tools for android apps: status quo and robustness against obfuscation [C]//Proc of the 6th ACM Conference on Data and Application Security and Privacy.New York:ACMPress,2016.   
[4]Baumann R,Protsenko M,Müller T.Anti-ProGuard: towards automated Deobfuscation of Android apps [C]//Proc of the 4th Workshop on Security in Highly Connected IT Systems.New York:ACMPress,2017.   
[5]王蕊，苏璞睿，杨轶，等．一种抗混淆的恶意代码变种识别系统[J]. 电子学报,39(10):2322-2330,2011.   
[6]Rastogi V, Chen Y,Jiang X. Droidchameleon:evaluating android antimalware against transformation attacks [C]//Proc of the 8th ACM SIGSAC Symposium on Information, Computer and Communications Security, New York:ACMPress,2013:329-334.   
[7]Zhang F,HuangH, Zhu S,et al.ViewDroid: towards obfuscation-resilient mobile application repackaging detection [C]//Proc of ACM Conference on Security and Privacy in Wireless& Mobile Networks.New York:ACM Press,2014:25-36.

[8]焦四辈，应凌云，杨轶，等．一种抗混淆的大规模Android 应用相似

性检测方法[J].计算机研究与发展，2015,51(7):1446-1457.   
[9]Christodorescu M, Jha S,Kruegel C.Mining specifications of malicious behavior[C]//Proc of the 1st India Software Engineering Conference.New York:ACMPress,2008:5-14.   
[10]Hornyack P,Han S,Jung J,etal. These aren't the droids you're looking for: retrofitting android to protect data from imperious applications [C]//Proc of the 18th ACM Conference on Computer and Communications Security.New York:ACMPress,2011:639-652.   
[11]Bonfante G,Kaczmarek M,Marion JY.Architecture of a morphological malware detector[J].Journal in Computer Virology,2009,5(3): 263-270.   
[12] Rasthofer S,Steven A,Bodden E.A machine-learning approach for classifying and categorizing android sources and sinks [C]//Proc ofNetwork and Distributed System Security Symposium.2014.   
[13] Fritz C,Arzt S,Rasthofer S.DroidBench [EB/OL].(2015）[2017]. https://github.com/secure-software-engineering/DroidBench.