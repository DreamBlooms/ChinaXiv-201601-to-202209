# 一种基于LLVM中间表示的数据依赖并行计算方法

朱燕，衷璐洁

(首都师范大学 信息工程学院，北京 100048)

摘要：底层虚拟机LLVM是一个广泛使用的编译框架,其中间表示IR中包含有丰富的程序分析信息，众多以LLVM为平台的相关工作均以IR为基础开展。数据依赖关系在错误检测、定位及程序调试等领域有着重要应用。基于IR的数据依赖关系计算多采用串行迭代方式，但在应对较大规模IR文件时可扩展性不够理想。对此，进行了数据依赖关系计算中指令读写的可并行性挖掘，结合图形处理器并行计算优势，提出一种基于LLVMIR 的数据依赖关系并行计算方法 DRPC。该方法以IR为输入，采用CPU-GPU双端协同方式实现程序数据依赖关系的高效计算。实验结果表明，针对基准程序集 SPEC，DRPC分别在直接及传递数据依赖关系计算上最高获得了 $3 . 4 8 \mathrm { x }$ 和 $4 . 9 1 \mathrm { x }$ 的加速比。

关键词：底层虚拟机；中间表示；数据依赖；图形处理器；可扩展性中图分类号：TP301.4 doi:10.19734/j.issn.1001-3695.2018.08.0536

Approach of parallel data dependence relation computation based on LLVM IR

Zhu Yan, Zhong Lujie (College of Information Engineering,Capital Normal University,Beijing 1Ooo48,China)

Abstract:The low level virtual machine isawidelyused compiler framework.Its intermediaterepresentation contains abundant program analysis information,and manyrelated work basedon programanalysis takes a basis of IR.Data dependece plays an importantrolein faultdetection,fault location,and program debuging.IR-based data-dependence computing oftenadopts serial iterative approaches,such approaches usuallysufer scalability issues whendealing with larger-scale IRcontents.Toaddressabove isses,the paralelism miningof instructionsreading and writing in data dependece calculation is carried out.Combined with the paralel computing advantages of graphics processing unit,a paralel computing method DRPC based on LLVMIR is proposed,which accepts IRas inputs,and achieves efficient program data dependence computation through a CPU-GPU cooperation way.The experimental results show that DRPC's highest speedup is $3 . 4 8 \mathrm { x }$ and $4 . 9 \mathrm { x }$ respectively in the direct and transitive data dependence computation with benchmark SPEC.

Key words: LLVM; intermediate representation; data dependence; graphics processing unit; scalability

# 0 引言

LLVM（lowlevelvirtualmachine，底层虚拟机）是一个开源的编译框架，它提供一种基于SSA（static singleassignment）的中间表示（intermediate representation，IR），并以该表示作为后续优化及其他相关工作的基础[I]。IR中包含有丰富的程序分析信息。数据依赖分析是一种重要的程序分析技术，在程序优化、维护及调试等众多方面有着广泛的应用[2-4]。如：以指令间的依赖关系为指导进行的指令调度及以程序实体间的依赖关系为依据实施的更精准错误定位等[5]。基于 LLVMIR 的数据依赖分析一般采用串行迭代的方式，这样的方式在运用于较大规模程序的数据依赖关系计算时可扩展性表现不够理想。

# 1 问题背景

# 1.1数据依赖

数据依赖是一类典型的依赖分析方法，主要反映程序语句间需要遵守的读写依赖关系。根据语句间是否存在多个连续的数据依赖关系，可将数据依赖分为直接数据依赖及传递数据依赖两个类别。与数据依赖相关的定义如下：

定义1已知有 $n$ 条有序执行的语句构成的语句序列$S _ { I } , S _ { 2 , \cdots , S _ { n } }$ （ $n { \geq } 2 \rangle$ ），其中， $S _ { I }$ 称为起点语句， $S _ { n }$ 称为终点语句，其余称为中间语句。相邻语句间的依赖关系 $D _ { i } \left( 1 \leq i \leq n - 1 \right) .$ ）形成的依赖序列 $D / = \ ( D / , D / , . . . , D _ { n - l } )$ 称为依赖链[6]。

将语句 $S _ { i }$ 的内存读操作变量集记做read $( S _ { i } )$ ，语句 $S _ { i }$ 的内存写操作变量集记做write(Si)。

直接数据依赖（依赖链长度为2，即 $\scriptstyle n = 2$ ）的相关定义如下[7]：

定义2流依赖（flowdependence，FD）。若write(Si)∩read $( S _ { i + l } ) \neq \phi$ ， $\scriptstyle i = 1 , 2 , \ldots , n - 1$ ，则称 $S _ { i }$ 和 $S _ { i + I }$ 间存在流依赖，记做 $S _ { i } F D S _ { i + I }$ 。

定义3反依赖（antidependence，AD）。若 read(Si)Nwrite $( S _ { i + l } ) \neq \boldsymbol { \phi }$ ， $\scriptstyle i = 1 , 2 , \ldots , n - 1$ ，则称 $S _ { i }$ 和 $S _ { i + I }$ 间存在反依赖，记作： $S _ { i } A D S _ { i + I }$ 。

定义4输出依赖（outputdependence，OD）。若write(Si)Nwrite $( S _ { i + l } ) \neq \boldsymbol { \phi }$ ， $\scriptstyle i = 1 , 2 , \ldots , n - 1$ ，则称 $S _ { i }$ 和 $S _ { i + I }$ 间存在输出依赖，记做 $S i O D S _ { i + I }$ 。

特别地，当 $n { > } 2$ 时，若起点语句和终点语句间存在多个连续的、具有传递特征的数据依赖关系，则称这样的关系为传递依赖。

定义5传递依赖（transitive dependence，TD）。对于语句序列 $S _ { i }$ ， $S _ { i + I }$ ， $S _ { i + 2 } , . . . . , S _ { j }$ ，若语句 $S _ { i }$ 和 $S _ { j }$ 间满足如下条件：

writer $( \mathsf { S } _ { \mathrm { m } } )$ Nread $ { \mathrm { \ : \ : } } \mathbf { S } _ { \mathrm { m + 1 } }$ ） $\neq \Phi$ (i≤m≤j-1),

则称 $S _ { i }$ 和 $S _ { j }$ 间存在传递依赖关系，记做 ${ S i } ~ T D ~ S j$ 。值得注意的是，由于存在传递依赖关系的语句序列中相邻语句间均存在流依赖关系，因此该序列也将形成一条流依赖链。

以图1(a)所示程序片段为例，由于 $w r i t e ( S _ { \mathit { 2 } } ) ~ = ~ \{ a \}$ ，1 ${ \it e a d } ( S _ { 3 } ) = \{ a \}$ ， $\scriptstyle w r i t e ( S 3 ) = \{ b \}$ ， $r e a d ( S _ { \bar { S } } ) = \{ b \}$ ， $w r i t e ( S \boldsymbol { \varsigma } ) = \{ d \}$ 有 $W r i t e ( S _ { 2 } ) \cap R e a d ( S _ { 3 } ) \neq \varPhi$ 且 $w r i t e ( S _ { 3 } ) \cap r e a d ( S _ { 5 } ) \neq \emptyset$ ，因此，在$S _ { 2 }$ 与 $S _ { 5 }$ 间存在传递依赖关系。

; Function Attrs: nounwind uwtable -FD define i32 @func() #0{ 读内存 entry: 写内存   
intfunc() %retval $\mathbf { \Sigma } = \mathbf { \Sigma }$ alloca i32, align 4 %a = alloca i32,align 4   
1 $\% { \bf b } =$ alloca i32, align 4 $S _ { I }$ ：int $^ { \mathrm { a , b , c } }$ %c = alloca i32,align 4 $S _ { 2 }$ ， $\mathbf { a } = 1$ ： %d = alloca i32,align 4 ① storei321i32%aalign4 先写 $S _ { 3 }$ ：： ${ \mathsf b } = { \mathsf a } + 1$ ： %0=loadi32,i32\*%aalign4 后读 $S _ { 4 }$ ： ${ \mathrm { c } } = { \mathrm { a } } + 3$ %add=add ns w i32 %0,1 %a $S _ { 5 }$ ：int $\mathrm { d } = \mathbf { b } + \boldsymbol { 5 }$ storei32%add i32\*%balign4 $S _ { \delta }$ if $\mathrm { ( d > 1 0 ) }$ 1 %112n 1 $S _ { 7 }$ 1 return c;} 1 store i32 %add1,i32\*.%c,align 4 $S _ { 8 }$ else{ ②%2=loadi32,i32\*%b align4 $S _ { g }$ ： retum a; } 先写读 add $\mathbf { \Sigma } = \mathbf { \Sigma }$ ads,32 $\% 2$ lign4-- $\textcircled{3}$   
} %b %3=loadi32,i32%dalign 4- 后读 %cmp $\mathbf { \sigma } = \mathbf { \sigma }$ icmp sgt i32 %3,10 %d br il %cmp,label %if.then, label %if.else... } (a) (b)

# 1.2LLVM IR

图2给出了LLVM编译框架的构成示意，主要包含三个部分：前端、优化器及后端。LLVM自定义的中间表示IR是该框架的重要组成部分。IR不仅是LLVM优化及后端相关工作的基础，也是基于LLVM程序分析的各种应用的主要输入。IR一般有三种形式：可读汇编形式、二进制码形式及内存中间表示形式。

![](images/5dbc6e442e97f157143ea41e615abdcb8008b57e57062ffc0f2cac465329f68a.jpg)  
图1内存读写型数据依赖关系示例  
Fig.1Example of memory read and write data dependence computation based on LLVM IR   
图2LLVM编译框架  
Fig.2LLVMcompilation framework

LLVMIR内容文本通常以指令集形式提供包含函数声明、基本块、变量声明及函数调用等在内的各项程序分析信息。LLVM典型的指令集类别包括内存访问指令、终端指令、二进制指令、按位二进制指令以及其他指令等。在图1(b)中给出了图1(a)所示代码片段的IR文本内容示例。

# 1.3基于LLVMIR的数据依赖计算

在LLVMIR中，与数据依赖计算相关的内存读写指令包括alloca、store和load等。其中alloca指令表示变量声明，store指令表示变量的内存写操作，load指令表示变量的内存取操作，并且三种指令中的相关变量会以符号"%"进行标志。

通过对相关读写指令的特征追溯，可以提取出数据依赖关系计算所需的程序分析信息。例如可通过追溯IR中的store和load指令并实施分析，计算获得数据依赖关系计算所需的Write集和Read集，进而完成数据依赖关系的相关计算。

以图1(a)所示程序片段为例，在IR中识别变量 $\mathbf { \Delta } _ { a }$ 、b、 $d$ 相关的内存读写指令，用 $S _ { s t o r e I }$ 表示图1(b)中标志 $\textcircled{1}$ 相关的store指令， $S _ { l o a d l }$ 表示图1(b)中标志 $\textcircled{1}$ 相关的load指令。可知Read $( S _ { s t o r e l } ) { = } \{ 1 \}$ ， $W r i t e ( S _ { s t o r e I } ) { = } \{ \%  a \}$ ，Read$( S _ { l o a d l } ) { = } \{ \begin{array} { r l } { \mathrm { ~ \% ~ } a } \end{array} \}$ ，Write $( S _ { l o a d l } ) { = } \{ \begin{array} { c } { \mathrm { ~ \% ~ } \} } \end{array}$ ，由于 $W r i t e ( S _ { s t o r e I } )$ $\cap R e a d ( S _ { l o a d l } ) \neq \varPhi$ ，进而可计算出 $S l o a d I$ 和 $S _ { s t o r e I }$ 间的流依赖关系。其特征追溯路线参见图1(b)中的带箭头弧形虚线。

# 1.4基于IR的数据依赖关系计算并行性分析

直接数据依赖关系计算中的并行性．直接数据依赖关系的计算需要考虑起点指令和终点指令间的相关读写交集。一方面，可利用不同起点指令与终点指令间的非连续读写交集特征进行计算任务划分，另一方面，也可充分利用相关指令信息的读取及数据依赖关系更新的访存特性进一步获得数据并行性。

传递数据依赖关系计算中的并行性．传递数据依赖关系的计算虽然具有动态性，但仍然具备较好的数据并行特征，例如，可调度多个线程同时计算不同起点指令、终点指令与同一中间指令之间的读写交集。

本文提出一种基于LLVMIR的、以GPU为环境的数据依赖关系并行计算方法，通过CPU-GPU双端联合的方式实现数据依赖关系的高效计算，具体包括：

a)一种面向数据依赖关系计算的CPU-GPU数据映射方法，在有效隐藏数据映射延迟的同时，进一步保障可扩展性目标的实现。

b)基于多流协同的直接数据依赖关系计算方法及GPU访存敏感的双端协同传递数据依赖关系计算方法。在数据依赖关系计算的过程中，针对不同迭代间的耦合关系规避问题，在保障计算准确性的同时实现CPU端与GPU端之间的计算同步。

c)结合GPU存储介质特点及数据依赖关系计算任务访存特性考虑的数据分布策略，进一步提升访存效率。

# 2 基于LLVMIR的数据依赖并行计算框架

本文主要围绕三个影响数据依赖并行计算的可扩展性问题：非规则存取带来的带宽资源浪费问题；CPU-GPU双端的高效协同问题；线程不同步破坏传递数据依赖计算的动态性问题，提出基于LLVMIR的数据依赖关系并行计算框架(dataDependence RelationParallel Computationframework,DRPC)。如图3所示，主要由IR特征指令匹配及信息提取(Pre_Match_Extract)、数据适配存储映射（Info_Storage）、直接依赖关系计算(Direct_DepCal)、传递依赖关系计算(Trans_DepCal)和并行优化(Parallel_Opt)及数据依赖关系应用输出(DepOutput_forApp)几个部分组成。

其中，Pre_Match_Extract主要负责基于特征制导的关键指令匹配及相关程序分析信息的提取；Info_Storage主要负责根据直接依赖关系及传递依赖关系计算需要，实现CPU端及GPU端的数据信息映射；Pre_Match_Extract 和Info_Storage是DRPC的基础性组成。在适应性数据映射完成后，由Direct_DepCal和Trans_DepCal共同负责完成各类数据依赖关系的并行计算。其中，Direct_DepCal主要负责直接数据依赖关系的并行计算，Trans_DepCal负责在直接数据依赖关系计算完成的基础上继续完成传递数据依赖关系的并行计算。

在数据依赖关系的并行计算过程中，Parallel_Opt会负责实施进一步的性能优化。最后由DepOutput_forApp 根据后续应用需求对数据依赖关系进行组织和输出。

![](images/46b44adb71a414ca491c6cf3878e5f6f53a54043b150c5772f1764207b6d0ea7.jpg)  
图3基于Ilvmir的数据依赖关系并行计算框架

同时，本文使用CUDA作为 $D R P C$ 的GPU并行计算环境。CUDA的线程模型被划分为三个层次，分别为线程格（grid）、线程块（block）以及线程（thread）。每个线程格内包含一定数量的线程块，每个线程块内包含一定数量的线程，并且每个线程、线程块和线程格都拥有编号。相同线程块中的线程可访问同一个共享内存区域，所有线程都可以访问全局内存。在进行数据依赖关系计算时，DRPC 将待计算数据按线程数量划分，并利用线程编号进行数据索引，让多个线程同时进行数据依赖关系计算。

# 3 DRPC具体实现

# 3.1存储设计

# 1）指令集存储设计

三个向量var_arr、inst_read_arr 和 inst_write_arr分别负责指令alloca、store及load的Write 集和Read集内容存储。其中，var_arr负责存储IR中的变量信息，其向量下标对应变量编号。inst_read_arr 和inst_write_arr负责存储内存读写操作变量的信息，其下标对应指令索引。同一指令中的读写变量在向量 inst_read_arr 和inst_write_arr 中具有相同下标,特别地，指令的内存常量读取设置特殊值-1。图4给出了图1示例的指令信息存储示意。以图1的第一个store指令为例，变量%a在var_arr中的下标为0，则该下标也是 $\% \text{‰}$ 的变量编号。那么在向量inst_write_arr下标为0的位置中，存入%a的编号O。在向量inst_read_arr下标为O的位置中，则存入表示常量1的特殊值-1。

![](images/e1845cbc69b280fca6339897be5021044271a6b6b16b4c36a716593c74e5bc70.jpg)  
Fig. 3 DRPC framework   
图4特征指令集存储设计  
Fig.4Design of characteristic instructions set storage

2）数据依赖关系存储

数据依赖信息以矩阵Matrix方式存储，Matrix的定义如式(1)所示。

$$
\begin{array} { c } { { M a t r i x [ i , j ] = \left\{ N D , F D , A D , O D , T D \right\} } } \\ { { \left( i , j = 0 , 1 , 2 , . . . , n - 1 \right) } } \end{array}
$$

其中：i, $j$ 表示指令Insti和Instj的指令索引。取值ND、FD、$A D , O D$ 和 $m$ 分别表示 $I n s t _ { i }$ 和 $I n s t _ { j }$ 间不存在数据依赖关系、存在流依赖关系、存在反依赖关系、存在输出依赖关系及存在传递依赖关系。

# 3.2特征制导的IR指令预处理

DRPC中的Pre_Match_Extract主要负责IR指令的分析预处理工作。首先，根据特征关键词alloca、store、load，从IR文本中筛选出待分析指令。之后根据指令的组织模式提取数据依赖计算所需的信息。同时，本文主要关注IR级别的指令间的数据依赖关系，对于循环结构，本文直接实施指令信息提取，并分析两两指令间的数据依赖关系。

表1待分析指令的简要组织模式及描述  
Tablel Brief organization mode and description of the instructions to be   

<html><body><table><tr><td colspan="2">analyzed</td></tr><tr><td>指令组织模式</td><td>描述</td></tr><tr><td>store OPType OP1, OPType OP2</td><td>读取OPi的值，并赋给OP2</td></tr><tr><td>OP2= load OPType, OPTypeOP1</td><td>OPi从内存中加载数据，并将该值赋给OP</td></tr><tr><td>OP1=alloca OPType</td><td>声明变量OPi，并在内存中为OPi开辟空间</td></tr></table></body></html>

表1归纳了三种待分析指令的组织模式，并给出了相应描述，其中 $O P _ { I }$ 与 $O P _ { 2 }$ 代表指令操作对象，OPType代表变量的数据类型。

Pre_Match_Extract主要工作过程的算法描述如算法1所示，其中 $M a t c h (  { x } ,  { y } )$ 表示对传入的原始IR指令 $x$ 进行关键指令匹配，并将匹配所得的指令类型返回给 $y$ 。算法1将逐行处理IR原始信息文本，通过调用Match（Inst,Inst_Type）完成IR中关键指令的匹配（行1-2）；若匹配为alloca指令，则将所提取的指令关键信息存入var_arr（行3-5）；若匹配为store或load指令，则存入inst_read_arr或inst_write_arr（行6-9）。

算法1 Pre_Match_Extract 输入：IR信息

输出：var_arr、inst_read_arr 以及 inst_write_ai

1.for each Inst in IR   
2.Match(Inst, Inst_Type );   
3.if Inst_Type $\scriptstyle = =$ alloca   
4. var_arr $$ alloca指令信息;   
5.end if   
6.if Inst_Type $\scriptstyle = =$ (store $\parallel$ load)   
7. inst_read_arr←读操作变量信息;   
8 inst_write_ari $$ 写操作变量信息;   
9.end if   
10.end for

# 3.3基于多流协同的基础数据依赖关系计算

在数据依赖关系计算部分， $D R P C$ 首先由Direct_DepCal完成直接的数据依赖关系计算，主要包括流依赖、反依赖和输出依赖等依赖关系的计算。Direct_DepCal采用多流协同的方式进行依赖关系的计算。图5给出了基于多流协同的直接数据依赖关系计算的工作机制示意。

![](images/df7b44dd06417efcebf23b780bf7c71bf6e33cbfd51ed1916c8f62401fdd215f.jpg)  
图5多流协同计算的工作机制  
Fig.5Multi-stream collaborative computing mechanism

两个流StreamO及Stream1以流水线方式分别执行数据复制、内核函数执行及计算结果的返回。例如，在StreamO完成数据映射工作后，将开始执行GPU_Direct_Kernel进行直接依赖关系的并行计算，与此同时Stream1调用Info_Storage进行 数 据 映射。当StreamO 结束GPU_Direct_Kernel执行后，会将直接数据依赖信息回传至CPU端，同时 Stream1 启动GPU_Direct_Kernel。其中，GPU_Direct_Kernel 通过计算inst_read_arr 和 inst_write_arr的交集来获得直接数据依赖关系，具体计算方法如式(2)所示。在式2)中，Insts和Inste分别代表起点指令和终点指令，s 和e分别对应这两条指令的索引。

$$
M a t r i x [ s , e ] = \left\{ \begin{array} { l l } { F D , \mp \mp i n s t _ { - } w r i t e _ { - } a r r [ s ] = i n s t _ { - } r e a d _ { - } a r r [ e ] } \\ { A D , \mp \pm i n s t _ { - } r e a d _ { - } a r r [ s ] = i n s t _ { - } w r i t e _ { - } a r r [ e ] } \\ { O D , \mp \mp i n s t _ { - } w r i t e _ { - } a r r [ s ] = i n s t _ { - } w r i t e _ { - } a r r [ e ] } \end{array} \right.
$$

算法2给出了CPU_Direct_DepCal的算法描述，此算法主要负责 CPU 端的相关工作。其中，Info_Storage(x)表示由流x完成数据映射工作；GPU_Direct_Kernel $( \mathbf { x } )$ 表示由流 $\textbf { \em x }$ 执行 GPU 内核函数；Data_Return(x,y,z）表示由流 $\textbf { \em x }$ 将y回传至z。对于程序中的每一个函数f，CPU_Direct_DepCal首先调用Info_Storage(StreamO)，由 StreamO 进行所需的数据映射工作，为 inst_read_arr及inst_write_arr在GPU端开辟存储空间d_Read_Arr和d_Write_Arr，以及为直接数据依赖关系集Depdirect 开辟GPU端存储空间d_Matrix（行1-2）；随后调用GPU_Direct_Kernel(StreamO)进行直接数据依赖关系计算（行3）；并在计算完成后调用Data_Return(StreamO,d_matrix,Depdirect），由StreamO将d_Matrix回传至集合Depdirect，并同时启动Info_Storage(Stream1)进行所需的数据映射工作（行4）；之后调用 GPU_Direct_Kernel(Stream1） 及Data_Return(Streaml,d_matrix,Depdirect)，由 Stream1 调用核函数进行下一次计算及数据回传（行5-6）。

算法2 CPU_Direct_DepCal   
输入：inst_read_arr、inst_write_arr   
输出：直接数据依赖关系集Depdiect   
1. for each f do   
2.Info_Storage(StreamO);   
3.GPU_Direct_Kernel(StreamO);   
4.Data_Return(StreamO,d_Matrix,Depdirect)&& Info_Storage(Stream1); 5.GPU_Direct_Kernel(Stream1);   
6.Data_Return(Stream1,d_Matrix,Depdirect);   
7.end for

算法3 给出了GPU_Direct_Kernel的算法描述，其中Share_W和Share_R是为了减少访存延迟而设置的共享数组，用于存储d_Read_Arr、d_Write_Arr 中的数据，函数Init(Array,x,y)表示利用索引信息 $\textbf { \em x }$ 和y初始化数组Array。算法3首先通过线程号、线程块号计算起点指令Insts和终点指令Inste的指令索引s和e（行1），然后调用Init(Share_Ws,e)和Init(Share_R,s,e)将d_Write_Arr、d_Read_Arr中的数据映射至 Share_W以及 Share_R(行 2-3），随后根据式 2)计算直接数据依赖关系，最后存储至d_Matrix（行4-12）。

算法3GPU_Direct_Kernel

输入：d_Read_Arr、d_Write_Arr以及d_matrix  
输出：包含直接数据依赖信息的集合d_matrix  
1.根据线程号及线程块号获得指令索引s、e  
2.Init(Share_W, s.e);  
3.Init(Share_R,s.e);  
4. if Share_W[s] $\scriptstyle = =$ Share_R[e]  
5.d_Matrix[s,e]←FD;  
6.end if  
7. if Share_R[s] $\scriptstyle = =$ Share_W[e]  
8.d_Matrix[s, $_ \mathrm { e l  A D }$ ·  
9.end if  
10.if Share_W $[ \mathrm { s } ] \mathrm { = } \mathrm { = } \mathrm { S h a r e \_ W } [ \$ e]  
11. d_Matrix[s, $\mathsf { e l e } \mathsf { l e } \mathsf { m o D }$   
12.end if

# 3.4GPU访存敏感的双端协同传递数据依赖关系计算

在Direct_DepCal计算结果的基础上，DRPC将由Trans_DepCal完成传递数据依赖关系的计算。在该阶段，需要先进行流依赖链的寻找。对于有序执行的指令序列$I n s t _ { i } , I n s t _ { i + I } , . . . , I n s t _ { j } ( j > i )$ ，根据指令索引i， $j$ 判断 $I n s t _ { i }$ 与Instj之间是否存在流依赖链的方法如式3)所示。

$$
\begin{array} { c } { { M a t r i x [ i , i + 1 ] = - F D } } \\ { { \wedge M a t r i x [ i + 1 , i + 2 ] = F D } } \\ { { \wedge . . . \wedge M a t r i x [ j - 1 , j ] = F D } } \end{array}
$$

流依赖链的构建是一个动态的过程，其长度会随中间指令的不断加入而增长。算法4和5分别给出了CPU_Trans_DepCal及GPU_Trans_Kernel的算法描述。其中，函数Map_midNumber $\cdot ( x )$ 负责映射中间指令 $I n s t _ { x }$ 的指令索引$x$ ：GPU_Trans_Kernel(k)表示向核函数GPU_Trans_Kernel中传入参数 $k$ 。在算法4中，首先为Depdirect分配GPU 端存储空间d_Trans_Mat（行2）；依次处理中间指令集 $S _ { m i d i n s t }$ 中的各条指令 $I n s t _ { k }$ ，获得GPU端映射中间指令索引 $k$ ；然后调用GPU_Trans_Kernel(k)，构建并分析含有中间指令的依赖链（行3-6）。计算结束后将GPU 端的d_Trans_Mat 回传至Deptrans（行7）。

算法4 CPU_Trans_DepCal  
输入：直接数据依赖信息集Depdirect输出：传递数据依赖信息集Deptrans1. for each f do  
2.d_Trans_Mat $$ Depdirect;  
3. for each Instk in Smidinst do  
4. $\mathbf { k } $ Map_midNumber(Instk);5.GPU_Trans_Kernel(k);  
6. end for  
7.Deptrans←d_Trans_Mat;  
8.end for

在算法5中，首先获取线程索引threadId和线程块索引blockId（行1)；之后利用上述信息调用Init(Share_k,threadId,blockId)初始化共享数组Share_ $\mathbf { \Psi } _ { \cdot } k$ （行2）；并通过寻找以blockId为起点指令索引，threadId为终点指令索引的流依赖链来计算传递数据依赖关系（行3-5）。

算法5 GPU_Trans_Kernel  
输入：包含直接数据依赖关系的d_Trans_Mat及k输出：包含传递数据依赖关系的d_Trans_Mat  
1.获取线程索引threadId和线程块索引blockId  
2.Init(Share_k,threadId,blockId);  
3.if d_Trans_Mat[blockId,k] $\scriptstyle = =$ Share_k[k,threadId] then

4.d_Trans_Mat[blockId,threadId] $\mathrm {  T D }$

# 5. end if

# 3.5并行优化机制

在Trans_DepCal 阶段，Parallel_Opt会就异构计算同步及数据分布等问题进行有针对性的优化。1)在传递数据依赖关系计算时，会实施中间指令添加工作，即在起点指令和终点指令之间添加中间指令以完成依赖链的构建与分析。每对一个新的依赖链进行分析，都需要依靠其余依赖链的分析结果，所以新依赖链的构建必须在其余依赖链完成计算的基础上进行。为了保证新依赖链分析的准确性，双端协同会在GPU端的本次分析结束之后，再从CPU端传入构建新依赖链所需的数据，从而使线程同步，避免遗漏其余依赖链的计算结果。2）考虑到访存效率，数据依赖关系以matrix形式存储在全局内存中，并在数据划分时利用GPU全局内存的合并访问机制[8]，对matrix按条带状划分，并建立中间指令索引 $k$ 与起点指令索引之间的索引映射。在这样的方式下，一个线程束访问的全局内存地址范围如式4)所示：

$$
r a n g e = \{ k ^ { * } N + j \vert j \in \{ 0 . . . 3 1 \} \}
$$

其中， $N$ 代表Matrix宽度， $j$ 代表线程号，同时映射为终点指令索引。内存地址连续的range可充分利用全局内存的合并访问优势，减少对全局内存的访问次数。此外，由于中间指令与其他指令形成的数据依赖关系被访问的频率较高，故将此部分数据存储在共享内存中，以提高数据访问的局部性，进而提升访存效率。

# 3.6数据依赖关系应用输出

数据依赖关系计算完成之后，DRPC可根据后续应用的不同需求进行数据依赖关系的组织和输出。图6给出一种图1(b)的数据依赖图输出示例。

![](images/b602b2514aa217ad2489566f523fe2ea1c560175f181be357701466aa216775d.jpg)  
Fig.6Data dependence graph of Figure 1(b)

其中椭圆节点代表指令，并且指令以简单等式的形式组织，等式左边代表指令中进行写操作的变量，等式右边代表指令中进行读操作的变量；Entry为入口指令节点；带箭头弧形虚线代表指令间的流依赖关系。

# 4 实验结果及分析

# 4.1实验环境

本文实验环境配置为IntelCorei7CPU $\mathrm { { \dot { + } } }$ NVIDIAGeForceGTX1050Ti。实验基准程序为SPEC2000，所有实验均以LLVMIR文件为输入。

# 4.2实验结果

实验选取了 SPEC 2000 中的 254.gap、183.equake、186.crafty以及176.gcc程序作为实验用例。表2给出了上述实验用例中 store 指令和load指令数量的统计结果，二者在数据依赖相关指令总数中占比均超过 $8 1 \%$ 。同时，结合GPU端全局内存的合并访存机制以及同线程块内的数据共享，通过线程与指令的一一映射，实现了一个线程束同时访问连续32 条指令的支持，进一步提高了全局内存的访存效率。当指令数量较少时，线程数量较少，导致计算任务的并行度较低，此时线程对全局内存的访问无法友好地隐藏线程的数据依赖计算操作，合并访存效果不佳。当指令数量较大时，活跃线程较多，数据访问能够较好地隐藏访存延迟，线程能够获取的共享数据资源增多，任务并行度和资源并行度都表现较好。

# 4.2.1时间开销

表2给出了DRPC的数据依赖关系计算时间数据，其中SDIR和STRA分别表示未并行化（串行）的直接数据依赖和传递数据依赖关系计算的时间数据；PDIR和PTRA分别表示本文提出的直接数据依赖关系并行算法和传递数据依赖关系计算并行算法的运行时间数据，并且PDIR和PTRA包含CPU端向GPU端的数据传输时间；图7为直接数据依赖关系计算串并行时间比较。图8为传递数据依赖关系串并行时间比较。由于254.gap及183.equake的数据与186.crafty及 $I 7 6 . g c c$ 的数据存在数量级差异，故分别以(a)和(b)两部分给出。此外，图9还给出了直接数据依赖关系和传递数据依赖关系计算的加速比数据。在图9中，DIRS和TRAS分别对应直接数据依赖关系计算和传递数据依赖关系计算的加速比。

表2数据依赖计算时间数据  
Table 2 Data dependence computation experiment time data   

<html><body><table><tr><td rowspan="2">实验用例</td><td rowspan="2">IR 大小 (KB)</td><td rowspan="2">IR 行数 (LOC)</td><td rowspan="2">store及 load (LOC)</td><td rowspan="2"></td><td colspan="3">PDIR 流依赖反依赖 (LOC) (LOC)</td><td rowspan="2">输出 依赖 (LOC)</td><td rowspan="2">STRA (ms)</td><td rowspan="2">传递 PTRA 依赖 (ms) (LOC)</td></tr><tr><td>SDIR (ms)</td><td>(ms)</td></tr><tr><td>254.gap</td><td>201</td><td>4662</td><td>1600</td><td>7.05</td><td>2.43</td><td>1550</td><td>1255 584</td><td>1148.96</td><td>634</td><td>180</td></tr><tr><td>183.equake</td><td>347</td><td>6934</td><td>2688</td><td>21.97</td><td>9.6</td><td>3636</td><td>2951</td><td>944 19069.93</td><td>4197</td><td>249</td></tr><tr><td>186.crafty</td><td>547</td><td>10676</td><td>2816</td><td>33.26</td><td>12.37</td><td>7287</td><td>6038</td><td>5230</td><td>102517 22228</td><td>353</td></tr><tr><td>176.gcc-1</td><td>1,913</td><td>34663</td><td>10892</td><td>163.35 53.72</td><td></td><td>6150</td><td>3491 2697</td><td>186540.55</td><td>37964</td><td>1247</td></tr><tr><td>176.gcc-2</td><td>3,193</td><td>54772</td><td>16010</td><td>294.33</td><td>84.66</td><td>20732</td><td>13823</td><td>6324 15565.42</td><td>3481</td><td>8521</td></tr></table></body></html>

![](images/63fe2e060db5be858c0b6796bf3f5294b172c2acd1bcfb628293263f094374a9.jpg)  
图7直接数据依赖关系计算串并行时间比较Fig.7Serial time and parallel time comparison of direct datadependence computation

![](images/f6ffa9f8bd43798600a25de05e4ecfd08ae965df6b5a295b41092c0f692f5fca.jpg)  
图6图1(b)的数据依赖图  
图8传递数据依赖关系计算串并行时间比较Fig.8Serial time and parallel time comparison of transitive datadependence computation

分析图7可知，对所有实验程序，PDIR的在时间性能上均优于 $S D I R$ 。当IR信息文本规模较大时，PDIR相较于SDIR表现出了更为明显的时间优势。直接数据依赖关系计算的加速比由 $2 . 2 9 \mathrm { x }$ 升至 $3 . 4 8 \mathrm { x }$ 。这主要是由于活跃线程的数量增多，多流协同计算的策略有效地隐藏复制数据带来的延迟

所带来的性能提升。

在图8中，当实验数据规模较小时，图8(a)中STRA与PTRA时间差值较小，加速比仅为 $1 . 8 \mathrm { x }$ ，这主要是由于数据量较小，GPU端活跃线程数量较少，传递依赖关系计算未能很好地隐藏访存延迟。而当实验数据规模增大，在图8(b)中，由于合并访问机制及共享内存的合理使用，访存效率提高，同时活跃线程的增多较好地隐藏了访存延迟，令传递闭包并行计算的加速比提升至了 $4 . 9 1 \mathrm { x }$ 。

![](images/fc5b1b451eff7d808047b2514d5a86de3f1eb3248b218284f27c33c933e202ee.jpg)  
图9加速比数据  
Fig.9Speedup of data dependence calculation

4.2.2空间开销

如表3所示， $S D D C$ 与 $P D D C$ 分别代表了未并行化的数据依赖计算和本文提出的数据依赖并行计算的空间数据。其中， $S D D C$ 只涉及到CPU的内存使用，而 $P D D C$ 的CPU端空间数据包含了存储在页锁定内存的数据，该部分的数据用于直接数据依赖并行计算中多流协同机制的数据复制，所以PDDC在CPU端的空间开销上相较于 $S D D C$ 要多出约 $0 . 8 \%$ 。除此之外， $P D D C$ 还包括GPU端并行计算所需数据的内存开销，表3给出了GPU端的拷贝开销。由表可知GPU端的拷贝开销最高占 $P D D C$ 的 $4 . 9 \%$ ，这是由于多流协同机制使得GPU端只需要分配一个函数中的指令的所需空间，所以总体而言，SDDC的空间开销接近 $P D D C$ 0

表3数据依赖计算空间数据  
Table 3 Data dependence computation experiment space data   

<html><body><table><tr><td rowspan="2">DatadependeheeComputatronCxperhentspacedata 实验用例</td><td rowspan="2">SDDC(M)</td><td colspan="2">PDDC(M)</td></tr><tr><td>CPU</td><td>GPU</td></tr><tr><td>254.gap</td><td>10.08</td><td>10.16</td><td>0.25</td></tr><tr><td>183.equake</td><td>56.43</td><td>56.60</td><td>1.56</td></tr><tr><td>186.crafty</td><td>52.94</td><td>53.07</td><td>2.64</td></tr><tr><td>176.gcc-1</td><td>274.01</td><td>274.64</td><td>2.85</td></tr><tr><td>176.gcc-2</td><td>450.94</td><td>451.88</td><td>3.52</td></tr></table></body></html>

# 5 相关工作

数据依赖分析方法．Johnson等人[9提出了一种基于LLVM的协作依赖分析框架，该框架对于不同的依赖场景使用特定的依赖分析算法，同时获得了准确性与依赖分析方法的可组合性。高念书等人[10]提出一种实用的数据依赖分析方法，该方法根据数组下标的不同类型采用不同的依赖分析方法，解决循环正规化的一些限制问题。姜淑娟等人[11提出了一种基于异常传播分析的依赖分析方法，通过建立一种能够描述异常处理结构的系统依赖图来适应含有异常处理的 $^ { C + + }$ 程序的分析，解决了忽略异常处理而造成的分析不准确问题。Nikolaos等人[12]提出了一种递归并行任务之间的动态数据依赖的系统PARTEE，该系统通过分析内存踪迹确定任务间的依赖关系，实验表明PARTEE比Nanos $^ { + + }$ 能解决更多细粒度问题，且在任务依赖不规则的情况下，PARTEE比Cilk高出

$103 \%$ 。Litvak等人[13]提出了一种域敏感的传递依赖关系分析算法，解决了大型结构体变量之间传递依赖关系的分析问题，该算法在内存消耗上降低了 $31 \%$ 。

并行化的数据依赖分析.MinjangKim等人[14]提出了一种可扩展的动态数据依赖分析框架 $\mathrm { S D } ^ { 3 }$ ，该框架利用流水线和数据并行的混合并行模型进行数据依赖分析，减少了时间开销，实验表明在8核和32核处理器上分别获得了4.1x和$9 . 7 \mathrm { x }$ 的加速比。Yu等人[15]提出一种将分析任务划分为独立片的方法，该方法通过并行分析不同的片生成子图，最终由编译器自动将其组合成完整的数据依赖图。实验表明，对于多个知名的基准程序，该并行方案将分析时间缩短了几个数量级。Li等人[16提出了一种无锁的并行数据依赖分析方法，该方法为每个内存地址分配一个处理存储器访问的工作线程，同时线程并行执行分析算法，该方法相较于其未并行化的数据依赖分析方法获得了 $2 . 1 \mathrm { x } \mathrm { - } 2 . 4 \mathrm { x }$ 的加速比。

# 6 结束语

针对基于IR的数据依赖计算的可扩展性问题，本文提出了一种基于LLVM中间表示的数据依赖并行计算框架DRPC。该框架对传统迭代方式的并行性进行挖掘，并解决了基于IR的数据依赖计算在GPU端中的数据适配性问题与同步性问题，根据数据访问频率，合理分配数据，同时提高任务并行性，实验证明该方法能有效提高基于IR的数据依赖计算的可扩展性。

# 参考文献：

[1]Lattner C.The architecture of open source applications:LLVM [EB/OL]. (2012) [2018-8-1]. http://www.aosabook.org/en/llvm.html.   
[2]王涛，韩兰胜，付才，等．软件漏洞静态检测模型及检测框架[J]. 计算机科学,2016,43(5):80-86.(Wang Tao,Han Lansheng,Fu Cai,et al. Static detection model and framework for software vulnerability [J]. Computer Science,2016,43(5): 80-86.)   
[3]Bates S,Horwitz S. Incremental program testing using program dependence graphs [C]//Proc of the 2Oth ACM SIGPLAN-SIGACT Symposium on Principles of programming languages.New York:ACM Press,1993:384-396.   
[4]Binkley D.Using semantic differencing to reduce the cost of regression testing [C]/Proc of Conference on Software Maintenance.Piscataway, NJ:IEEE Press,1992:41-50.   
[5]王克朝，王甜甜，苏小红，等．软件错误自动定位关键科学问题及研 究进展[J].计算机学报，2015，38(11):2262-2278.(Wang Kechao, Wang Tiantian,Su Xiaohong,et al.Key scientific issue and state-art of automatic software fault localization [J]. Chinese Journal of Computers, 2015,38(11)，2262-2278.)   
[6]缪力，张大方．扩展有限状态机 EFSM的后向切片[J].软件学报, 2004，15(suppl):169-178．(Miao Li，Zhang Dafang.Computing backward slice of EFSMs [J].Journal of Software,2004,15(suppl): 169-178.)   
[7]吴忧．基于LLVM的C程序的动态数据依赖分析工具的设计与实现 [D]．长春：吉林大学,2016.(Wu You.The design and implementation of dynamic data dependence analysis tool for C program based on LLVM[D].Changchun: Jilin University,2016.)   
[8]NicholasW.CUDA专家手册：GPU 编程权威指南 [M].苏统华，马 培军，译．北京：机械工业出版社，2014:97-98.(NicholasW.CUDA handbook: a comprehensive guide to GPU programming [M]. Beijing: China Machine Press,2014: 97-98.) [9]Johnson N P,Fix J,Beard S R,et al.A collaborative dependence analysis framework[C]//Proc of IEEE/ACM International Symposium on Code Generation and Optimization. Piscataway,NJ:IEEE Press,   
2017:148-159. [10]高念书，张兆庆，乔如良．实用数据依赖分析方法[J].计算机学报,   
1995,18(4):258-265.(Gao Nianshu, Zhang Zhaoqing,Qiao Ruliang. Practical data dependence analysis [J].Chinese Journal of Computers,   
1995,18(4): 258-265.) [11]姜淑娟，徐宝文，史亮，等．一种基于异常传播分析的依赖性分析方 法[J]．软件学报，2007,18(4):832-841.(Jiang Shujuan,Xu Baowen, Shi Liang，et al.An approach to analyzing dependence based on exception propagation analysis [J]. Journal of Software,2Oo7,18(4):   
832-841. ) [12]Papakonstantinou N,Zakkak F S,Pratikakis P.Hierarchical parallel dynamic dependence analysis for recursively task-parallel programs [C]//Procof ParallelandDistributed ProcessingSymposium. Piscataway,NJ:IEEE Press,2016:933-942. [13] Litvak S,Dor N,Bodik R,et al.Field-sensitive program dependence analysis [C]//Proc of ACM SIGSOFT International Symposium on Foundations of Software Engineering.New York:ACM Press,2010:   
287-296. [14]Kim M,Kim H,Luk CK.SD3:A Scalable Approach to Dynamic Data-Dependence Profiling [C]//Proc of IEEE/ACM International Symposium on Microarchitecture.Piscataway,NJ:IEEE Press,2010:   
535-546. [15] Yu Hongtao,Li Zhiyuan.Multi-slicing:a compiler-supported parallel approach to data dependence profiling [C]//Proc of International Symposium on Software Testing and Analysis.New York:ACMPress,   
2012:23-33. [16]Li Zhen,Jannesari A,Wolf F.An Efficient Data-Dependence Profiler forSequential and Parallel Programs [C]//Proc of Parallel and Distributed Processing Symposium.Piscataway,NJ: IEEE Press,2015:   
484-493.