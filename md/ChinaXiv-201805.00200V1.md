# 基于自动机的Java信息流分析

吴泽智1²，陈性元1,²，杜学绘1，杨智1(1．解放军信息工程大学 密码工程学院，郑州 450001;2．密码科学技术国家重点实验室，北京 100094)

摘要：面向Java的信息流分析工作需要修改编译器或实时执行环境，对已有系统兼容性差，且缺乏形式化分析与安全性证明。首先，提出了基于有限状态自动机的Java信息流分析方法，将整个程序变量污点取值空间抽象为自动机状态空间，并将Java字节码指令看做自动机状态转换动作；然后，给出了自动机转换的信息流安全规则，并证明了在该规则下程序执行的无干扰安全性；最后，采用静态污点跟踪指令插入和动态污点跟踪与控制的方法实现了原型系统IF-JVM，既不需要获得Java应用程序源码，也不需要修改Java编译器和实时执行环境，更独立于客户操作系统。实验结果表明，原型系统能正确实现对Java的细粒度地信息流跟踪与控制，性能开销为 $5 3 . 1 \%$ 。

关键词：有限状态自动机；动态污点跟踪；信息流分析；无干扰；Java 中图分类号：TP309.1 doi: 10.3969/j.issn.1001-3695.2017.08.0705

# Automata-based information flow analysis for Java

Wu Zezhi1,², Chen Xingyuan1, ²,Du Xuehui1, Yang Zhi1 (1.Collge ofCryptogramEngineering,PLAInformationEngineeringUniversityZhengzhou 450o1,China;2StateKey Laboratory of Cryptology,Beijing 100094, China)

Abstract:Existing Java-oriented informationflowanalysis worksdo notcompatible with current systems duetothe modifying ofthe compilerorrun-time executionenvironment.Atthesame tie,theyalsolackofformalanalysisandsecurityproof.First, this paper proposed a formal Java-oriented information flowanalysis method basedon finitestate automata.Itabstracted the taintvalue spaceofentire programvariablesintothestate spaceofautomataand transferredtheJavabytecode instruction into thestatetransitionactionsofautomata.Then,it giventheinformationflowsecurityrulesofstate machineconversionandproved the noninterference security propertyunderthese rules.Finaly, it implemented theprototypesystem named IF-JVMbyusing the static tainttrack instruction insertinganddynamictaint tracking technologies.IF-JVMis independentof thecustomer operatingsystem.Neither needs to getthe sourcecodeofJava application,nor needs to modifytheJavacompilerorrun-time executionenvironment.The experimentalresults show that the IF-JVM is an accurate system that tracking and controling information flow for the Java with the $5 3 . 1 \%$ overhead on performance.

Key Words: finite state automata; dynamic taint tracking; information flow analysis; noninterference; Java

# 0 引言

动态信息流跟踪[I又可称为动态污点跟踪或动态数据流跟踪，指在程序执行过程中跟踪所感兴趣的数据流集合。信息流控制机制实现的核心思想是将标签(附着在数据上，标签随着数据在整个系统中传播(数据派生出的对象也将会继承原有数据标签)，并使用这些标签来限制程序间的数据流向。机密性标签可以保护敏感数据不被非法或恶意用户的读取；而完整性标签可以保护重要信息或存储单元免受不可信或恶意用户的破坏。其广泛应用于与计算机系统安全相关的各个领域。

已有的工作在硬件层[2]、虚拟机层、高级语言层、低级语言层[3]、操作系统层[4]、网络层和数据层[5]实现了不同粒度的信息流控制，与本文密切相关的是虚拟机层实现和高级语言层实现，在虚拟机层，TaintDroid[在Dalvik虚拟机层实现了全系统动态污点跟踪，Trishul[7基于kaffe 虚拟机实现了Java 动态污点跟踪，Laminar[8实现了首个基于虚拟机和操作系统相结合的信息流跟踪控制系统，其他相关工作[9-13]在JavaScript、Python、PHP和Java上实现了信息流跟踪，但上述工作缺乏相关安全性分析与证明，且实现需要修改相应Java虚拟机运行环境，兼容性较差。Jif[l4,15]基于编译器实现静态信息流分析与控制,并且实现了基于类型系统的无干扰安全性分析，但其实现需要修改编译器，且其大部分工作在静态完成，对动态信息流跟踪与控制支持不够。本文综合以上工作的优势，主要贡献如下：

a)提出了基于有限状态自动机的Java信息流分析方法，通过将整个程序变量污点取值空间抽象为状态空间，并Java字节码指令看做自动机状态转换动作，给出了自动机转换的信息流规则，为面向Java的信息流控制工作提供理论基础。

b)给出了基于高级输入和低级输出的无干扰安全的定义，证明了自动机状态转换的的无干扰安全性。

c)采用静态污点跟踪指令插入和动态污点跟踪与控制的方法实现了原型系统IF-JVM，既不需要获得Java应用程序源码，也不需要修改Java 编译器和解释器，更独立于客户操作系统。

# 1 自动机信息流分析

有限状态自动机(finitestateautomata)简称有限自动机，是具有离散输入输出系统的数学模型，广泛应用于程序语言的设计和实现中。同时，在安全模型形式化验证领域也有着重要的应用。它具有有限数量的状态，用此来记忆过去输入的有关信息，并根据当前的输入确定下一步的状态和行为。一个有限自动机可等价地看做一个系统行为(事件)驱动的状态转换图，系统的行为(事件)包括输入事件、输出事件和内部事件。因而信息流安全策略可以由系统状态转移规则来进行形式化描述。本文有限状态自动机具有两个功能，其一，用于记录系统所有实体及其安全标记的值和系统所有输入和输出动作的集合；其二，依据安全策略阻止信息流从高级实体向低级实体流动。本文自动机定义如下：

$P$ （204号 the name of a program   
$\nu$ the value ofavarible   
$s$ （204 the security context of a varible   
$V$ （204 all variables in the program   
a a set of actions   
$\Omega$ （204号 an execution or a sequence of actions   
I the programe counter of VM   
$\Xi$ （204 the stack and heap of VM   
$\boldsymbol { \mathcal { Q } }$ （204号 the set of states of automata   
（204号 $q _ { o }$ （204 the start states of automata   
$\chi$ （204号 a finite set of input   
（20 $\kappa ( \chi )$ （204号 the secret inputs   
$\Delta ( \nu )$ （20 the influenced varibles by the secret input   
$\psi$ （204号 a finite set of output   
（204号 $\kappa ( \psi )$ （204号 the secret outputs   
$T ( \nu )$ （20 the security context of output varible   
$\delta$ （204号 a transition function

$P$ 表示Java程序，程序由数据和指令组成。 $\nu$ 表示变量的取值。变量的类型包括 boolean、byte、character、integer、short、long、float、double、object 和 arrays。 $s$ 表示变量的安全标记值。为跟踪多源信息流，安全标记 $s$ 由不同种基本标记 $\wp$ 组成，安全标记构成偏序格( $\cdot \wp , \wedge , \bot , \mathrm { { T } ) }$ ，交汇运算入取集合并集U，对于任意安全标记 $x$ 和 $y$ ，有：（1） $\scriptstyle x \bigwedge \ x = x$ ，满足等幂性；（2）$x \wedge y { = } y \wedge x$ ，满足可交换性；（3） $x \wedge ( y \wedge z ) { = } ( x \wedge y ) \wedge z$ ，满足可结合性.其顶元素是空集 $\emptyset$ ，表示为T，对于 $\mathrm { ~ v ~ }$ 中的所有 $x$ ，有T> $\scriptstyle x = x ;$ 底元素是全集U，为」，对于 $\mathrm { \Delta V }$ 中所有 $x$ ，有 $\perp \wedge x = \perp$ 。$V ( \nu , s )$ 表示该程序内所有的变量及其安全标记值。

$a$ 表示系统动作，可引起自动机状态发生转变。系统动作由不同类型的指令组成。如图1所示，本文将系统动作主要分为九类，分别是算术操作类(math_op），初始化类(allocate_op），返回操作类(return_op），取数值类(load_op），存数值类(store_op)，常数操作类(const_op），跳转类(jump_op)，调用类(invoke_op）和栈操作类(stack_op）。对于算术操作类，其又包含14种子类型，以add指令 $a { = } a { + } b$ 为例，将程序中变量 $\mathbf { \Delta } _ { a }$ 和$b$ 数值 $\boldsymbol { \nu }$ 进行加法运算并将结果保存于 $\mathbf { \Delta } _ { a }$ 中，同时，将 $\mathbf { \Delta } _ { a }$ 与 $b$ 的安全标记进行交汇运算入，并更新 $\mathbf { \Delta } _ { a }$ 的安全标记。对于初始化类，其中又包含3种子类型，以newarray为例，创建给定长度的数组同时创建相应安全标记。对于返回操作类，以dreturn为例，返回栈顶数值和相应的安全标记。对于存取操作类，在存取操作数同时存取其安全标记。对于常数操作类，规定常数安全标记取值为0。对于后续操作类不再赘述。对于类似于无条件跳转goto和空值返回return等不改变自动机状态指令不列入系统动作。 $\Omega$ 表示动作序列，由一系列顺序执行的动作组成。ⅡI表示程序计数器的安全标记值。三表示虚拟机堆栈存储的数据的安全标记值。由此可定义自动机状态及其状态转换。自动机状态定义为 $\mathcal { Q } \left( V , s h , p c \right)$ ，自动机状态转换可描述为$Q \ ( V , s h , p c ) { \mathsf { u g u p } } Q ^ { \prime } \ ( V ^ { \prime } , s h ^ { \prime } , p c ^ { \prime } )$ 或者 $\textit { Q } ( V , s h , p c ) \underset { = } { \cup } \underset { = } { \otimes } \varphi ^ { \prime } ( V ^ { \prime } , s h ^ { \prime } , p c ^ { \prime } ) \ \circ q o$ 表示自动机初始状态。

a= math_op add|mul|div|rem|sub|and|or|shl |shr|ushr| xor|lcmp|dcmpl| dempg allocate_op anewarray|newarray|multianewarray return_op areturn |dreturn |ireturn |freturn |lreturn load_op aaload|baload|caload|daload |iaload |faload |laload|saload|dload|fload|iload |lload|getfield|getstatic store_op aastore|astore|bastore丨castore|dastore liastore|fastore |lastore|sastore |dstore|fstore |istore |lstore|putfield|putstatic const_op bipush丨sipush |iconst |lconst|dconst|fconst |lde |ldew |lde2_w|aconst_null jump_op if_acmpeq lif_acmpne |if_icmplt|if_icmpge if_icmple |if_icmpeq |if_icmpne |ifeq lifne ifgt|ifge|ifle|iflt |ifnennull|ifnull invoke_op invokespecial |invokevirtual | invokeinterface |invokestatic stack_op swap|pop| pop2

$\chi$ 表示程序输入集。程序输入包括用户键盘输入，读取文件，数据库或者网络接收数据等。 $\kappa ( \chi )$ 表示输入集中高级输入。例如用户输入的密码或程序读取的隐私文件等。 $\Delta ( \nu )$ 表示在程序执行过程中受到高级输入影响的变量集合。 $\psi$ 表示程序输出集。程序输出包括屏幕显示(例如printfO，写入文件，写入数据库或网络发送等。 $\kappa ( \psi )$ 表示输出集中高级输出，即输出内容中包含受高级输入影响的变量。 $T ( \nu )$ 表示输出变量的降密能力。例如，若变量 $\mathbf { v }$ 虽然受高级输入影响，但该高级输出为内部输出(如写入秘密文件)，为保证系统可用性与灵活性，该高级输出是安全的。 $\delta$ 表示自动机状态转换函数，表示为 $Q \times \chi \tt o s e a p Q ^ { \prime } \times \psi$ 。由此，自动机系统可完全描述为 $( \mathscr { Q } , a , \chi , \psi , q _ { 0 } )$ 。自动机状态转换规则如下：

(R-INIT) q I:(v:Φ; s:Φ; II:Φ;E:Φ) (R-INPUT-H) Qr:(v:vi; s: s6; II:△; E:m)- ${ \xrightarrow { \kappa ( \chi ) } } Q ^ { \prime }$ Γ :(v: x(x); $s : ( s _ { i } \land s _ { \kappa ( \chi ) } )$ ; II△; E:m) (R-MATH) Q Γ :(v : (v,vj); $s : ( s _ { i } , s _ { j } )$ ; II:△;E:n)mah→Q'T:(v:(vvj,vj); $s : ( s _ { i } \wedge s _ { j } )$ ; II:△; E:m) (R- ALLOCATE) $Q \ \Gamma : ( \nu : \phi ; \ s : \phi ; \ \Pi : \Delta ; \ \Xi : \eta ) { \xrightarrow { \ a l l o c a t e \ } } Q ^ { \prime } \ \Gamma : ( \nu : \nu _ { \phi } ; \ s : s _ { \phi } ; \ \Pi : \Delta ; \ \Xi : \eta )$ (R-RETURN) $\begin{array} { r } { \underline { { Q \ \Gamma : ( \nu : \nu _ { i } ; s : s _ { i } ; \Pi : \Delta ; \Xi : \eta ) \mathrm { - } \Sigma ^ { e u m m } } } \mathrm { ~ } \to Q ^ { \prime } \ \Gamma : ( \nu : ( \nu _ { i } \wedge \eta ) ; s : s _ { \phi } ; \ \Pi : \Delta ; \Xi ) \ } \end{array}$ :m) (R-LOAD) $Q \Gamma : ( \nu : \nu _ { i } ; s : s _ { i } ; \Pi : \Delta ; \Xi : \eta ) { \xrightarrow { \ l o a d \ } } Q ^ { \prime } \Gamma : ( \nu : \nu _ { i } ; s : s _ { i } ; \Pi : \Delta ; \Xi : ( \eta \wedge s _ { i } ) )$ (R-STORE) （204号 $\begin{array} { r }  \underline { { Q \Gamma : ( \nu : \nu _ { i } ; s : s _ { i } ; \Pi : \Delta ; \Xi : \eta ) \xrightarrow { s a n e } } Q ^ { \prime } \Gamma : ( \nu : \nu _ { i } ; s : \eta ; \Pi : \Delta ; \Xi : \eta ) } \end{array}$ (R-CONST) $\begin{array} { r } { Q \Gamma : ( \nu : \nu _ { i } ; s : s _ { i } ; \Pi : \Delta ; \Xi : \eta ) \xrightarrow { c o n s t } \ Q ^ { \prime } \Gamma : ( \nu : \nu _ { i } ; s : s _ { \phi } ; \Pi : \Delta ; \Xi : \eta ) } \end{array}$ (R-INVOKE) （20 $\begin{array} { r } { Q \Gamma : ( \nu : ( \nu _ { i } , s _ { \phi } ) ; s : ( s _ { i } , s _ { \phi } ) ; \Pi : \Delta ; \Xi : \eta ) \xrightarrow { i n v o l e } \ Q ^ { \prime } \Gamma : ( \nu : ( \nu _ { i } , \nu _ { i } ) ; s : ( s _ { i } , s _ { i } ) ; \Pi : \Delta ; \Xi : \eta ) } \end{array}$ (R-SWAP) Qr :(v:(v,sj); s:(ssj); I:△; m)- $\begin{array} { r l r } {  { \xrightarrow { i n \nu o k e } \sum Q ^ { \prime } \Gamma : ( \nu : ( \nu _ { i } , \nu _ { j } ) } } \end{array}$ $s : ( s _ { i } , s _ { j } )$ ; II:△; E:m) (R-JUMP) $Q \Gamma : ( \nu : \nu _ { i } ; s : s _ { i } ; \Pi : \Delta ; \Xi : \eta ) { \xrightarrow { j u m p } } Q ^ { \prime } \Gamma : ( \nu : \nu _ { i } ; s : \eta ; \Pi : \Delta ; \Xi : \eta ) \quad { \mathrm { ~ i f ~ } } \Delta = \phi \quad ( \nu : \nu _ { i } ; \Delta ) \times \quad 0 . 5 ( \nu _ { i } ; \Delta ) .$ (R-OUTPUT -L) Qr:(v:v; s:s\$; I:△; :m)- $\begin{array} { r } { \xrightarrow { \kappa ( \psi ) } Q ^ { \prime } \Gamma : ( \nu : \kappa ( \psi ) ; } \end{array}$ （20 $s : s _ { \kappa ( \psi ) }$ ; II:△; E:m)if $s _ { \kappa ( \psi ) } = \phi$ （20 (R-OUTPUT-H) Qr:(v:v\$; s: s\$; I:△; 三:n)- $\begin{array} { r } { \xrightarrow { \kappa ( \psi ) } Q ^ { \prime } \Gamma : ( \nu : \kappa ( \psi ) } \end{array}$ $s : s _ { \kappa ( \psi ) }$ ; II:△; E:m)if ${ \cal S } _ { \kappa ( \psi ) } \leq T ( \nu )$

为便于理解，给出如表1所示程序代码及其自动机状态转换示意。对于第一条程序语句，应用 $R - A L L O C A T E$ 和$R - I N P U T - H$ 规则，假设系统初始环境为空， $R - A L L O C A T E$ 规则将变量 $\mathbf { \Delta } _ { a }$ 及其安全标记添加到自动机状态中，$R - I N P U T - H$ 规则根据输入 $\kappa ( \chi )$ 设置变量 $a$ 的数值和安全标记值。同理，对于第二条程序语句执行相同的操作。对于第三条语句应用 $R - A L L O C A T E$ 和 $R - C O N S T$ 规则，$R - A L L O C A T E$ 规则将变量 $s t r$ 及其安全标记添加到自动机状态中， $R - C O N S T$ 规则设置常量的安全标记值为 $\phi$ 。对于第四条程序语句，应用 $R - I N V O K E$ 规则，将实参数值和安全标记值传递给形式参数及其安全标记值。对于第八条程序语句，应用 $R - M A T H$ 规则，将 $\mid c \mid$ 安全标记更新为 $\mathbf { \Psi } _ { c }$ 与 $d$ 的安全标记值交汇值。对于第九条程序语句，应用 $R - R E T U R N$ 规则，将变量 $\mathbf { \Delta } _ { a }$ 数值和安全标记设置为返回值和返回值的安全标记，并将该方法调用中使用的本地参数值及其安全标记从自动机状态中删除。对于第五条程序语句，应用 $R - O U T P U T - L$ 规则，变量$s t r$ 其安全标记为空，因而该输出是安全的。对于第六条程序语句，应用 $R - J U M P$ 规则，变量 $b$ 其安全标记不为空，故该跳转是不安全的，自动机将拒绝该条程序语句和状态转换，第七条语句不能执行。

# 2 安全性证明

安全性证明采用无干扰分析方法，是一种抽象出安全本质的分析方法。直观可理解为：若受保护的数据与不受保护的数据之间不存在相互干扰，则认为该系统是安全的。在本文情形下，无干扰表现为程序高级输入不影响程序公开输出，即阻止了信息流从高级输入流向公开输出。无干扰安全可形式化定义为 $\forall ( \kappa ( \chi _ { 1 } ) , \kappa ( \chi _ { 2 } ) )$ 1 $\psi [ \mathcal { \kappa } ( \chi _ { 1 } ) ] \mathop { \mathrm { E X E } } _ { = } \psi [ \mathcal { \kappa } ( \chi _ { 2 } ) ]$ 。即对于任意不同类型的高级输入，系统公开输出是等价的。为证明系统满足无干扰安全性，首先给出安全标记传播的单调性定义及其证明。

安全标记传播的单调性定义为： $\textcircled{1}$ 自动机状态一次转换由函数 $f$ 表示，对于安全标记格 $\wp$ 中的 $x$ 和 $y , f ( x \land y ) \leq f ( x ) \land f ( y ) ,$ （24单调性也可等价定义为： $\textcircled{2}$ 自动机状态一次转换由函数 $f$ 表示，对于安全标记格 $\wp$ 中的 $x$ 和 $y$ ， $x \leq y$ 蕴含 $f ( x ) \leq f ( y )$ 。现证明两种定义是等价的：

先证明单调性 $\textcircled{2}$ 可推导出单调性 $\textcircled{1}$ ：由于 $x \wedge y$ 是 $x$ 和 $y$ 的最大下界,则 $x \wedge y \leq x$ 且 $x \wedge y \leq y$ ，由单调性 $\textcircled{2}$ 可知 $f ( x \land y ) \leq f ( x )$ 且 $f ( x \land y ) \leq f ( y )$ ，同时 $f ( x \wedge y )$ 是 $f ( x )$ 和 $f ( y )$ 的最大下界，单调性$\textcircled{1}$ 得证。然后，证明单调性 $\textcircled{1}$ 可推导出单调性 $\textcircled{2}$ ：假设 $x \leq y$ 由单调性 $\textcircled{1}$ 可知 $f ( x \land y ) \leq f ( x ) \land f ( y )$ ，根据定义有 $x \wedge y { = } x$ 。因此有 $f ( x ) \leq f ( x ) \land f ( y )$ 。因为 $f ( x \wedge y )$ 是 $f ( x )$ 和 $f ( y )$ 的最大下界，得到$f ( x ) \wedge f ( y ) \leq f ( y )$ 。从而 $f ( x ) \leq f ( x ) \land f ( y ) \leq f ( y )$ ，即 $f ( x ) \leq f ( y )$ ，单调性 $\textcircled{2}$ 得证。

对于任意安全标记 $X$ 和安全标记 $^ { Y , X }$ 属于 $X \cup Y _ { \circ }$ 由此，可系统的无干扰安全性证明如下：

对于第一种情况：假设自动机初始状态$q _ { o } \Gamma : ( \nu : \phi ; s : \phi ; \Pi : \phi ; \Xi : \phi )$ ，一个状态转换序列 $\Omega$ 可分解为 $\mathfrak { n }$ 个动作 ${ \mathrm { a } } _ { 1 } , { \mathrm { a } } _ { 2 } , \ldots , { \mathrm { a } } _ { n \circ } { \mathrm { a } } _ { n }$ 为公开输出动作，由规则 $R - O U T P U T - L$ 可知该公开输出动作 $\kappa ( \psi )$ 为空。 $\mathbf { a } _ { 1 }$ 为某高级输入动作 $\kappa ( \chi _ { 1 } )$ ，执行后自动机状态转换为 $\boldsymbol { Q } \ : \Gamma : ( \nu : \nu _ { \kappa ( \chi _ { 1 } ) }$ · $s : s _ { \kappa ( \chi _ { 1 } ) }$ ; II:△; E:n) 。a2，..， $\mathbf { a } _ { n - I }$ 为任意输入输出或者其他动作。假设系统高级输入动作影响了系统公开输出动作，则有，执行动作 $\mathbf { a } _ { \mathrm { n } }$ 后，自动机状态由 $Q \Gamma \colon ( \nu : \nu _ { a _ { n - 1 } } ; s : s _ { a _ { n - 1 } } ; \Pi { : } \Delta ; \Xi { : } \mathfrak { n } )$ 转换为$Q \Gamma \colon ( \nu : \nu _ { a _ { n } } ; s : s _ { a _ { n } } ; \Pi { : } \Delta ; \Xi { : } \boldsymbol { \eta } )$ 。由单调性可知，有 $s _ { a _ { n - 1 } } \leq s _ { a _ { n } }$ ，由于公开输出动作 $\kappa ( \psi )$ 为空，即 $s _ { a _ { n } }$ 为空，故 $s _ { a _ { n - 1 } }$ 也为空。执行动作 ${ \bf a } _ { \mathrm { n - 1 } }$ 后，自动机状态由 $\ : Q \Gamma \colon ( \nu : \nu _ { a _ { n - 2 } } ; s : s _ { a _ { n - 2 } } $ $\Pi { : \Delta } ; \Xi { : \eta }$ 转换为 $Q \Gamma : ( \nu : \nu _ { a _ { n - 1 } }$ $s : s _ { a _ { n - 1 } }$ $\Pi { : \Delta } ; \Xi { : \boldsymbol { \eta } }$ 。由单调性可知，有 $s _ { a _ { n - 2 } } \leq s _ { a _ { n - 1 } }$ ，由于 $s _ { a _ { n - 1 } }$ 为空，故 $s _ { a _ { n - 2 } }$ 也为空。依次类推,可知 $s _ { a _ { 1 } }$ 为空，即 $S _ { \kappa ( \chi _ { 1 } ) }$ 为空，而显然 $s _ { \kappa ( \chi _ { 1 } ) }$ 不为空。与前提矛盾，故系统高级输入动作不影响系统公开输出动作。即对于任意不同类型的高级输入，系统公开输出的安全标记皆为空。

上述无干扰性只考虑了系统公开输出（一般保证了系统公开输出无干扰安全，则系统是安全的)，若该输出为系统内部输出，系统仍满足特定条件下的无干扰安全性：$\forall ( s _ { \kappa ( \chi _ { 1 } ) } \leq T ( \nu ) , s _ { \kappa ( \chi _ { 2 } ) } \leq T ( \nu ) ) \quad \psi [ \kappa ( \chi _ { 1 } ) ] { \underline { { \mathrm { E X E } } } } \psi [ \kappa ( \chi _ { 2 } ) ]$ 。即任意高级输入与降密能力满足偏序关系，系统内部输出是等价的。证明如下：

假设自动机初始状态 $q _ { o } \ \Gamma : ( \nu : \phi ; s : \phi ; \Pi : \phi ; \Xi : \phi )$ ，一个状态转换序列 $\Omega$ 可分解为 $n$ 个动作 a1，a2，.．．， ${ \bf a } _ { n }$ 。 ${ \bf a } _ { n }$ 为内部输出动作，由规则 $R - O U T P U T - H$ 可知该内部输出动作${ \cal S } _ { \kappa ( \psi ) } \leq T ( \nu )$ 。 $\mathbf { a } _ { 1 }$ 为某高级输入动作 $\kappa ( \chi )$ ，执行后自动机状态转换为 $Q \Gamma : ( \nu : \nu _ { \kappa ( \chi ) }$ ： $s : s _ { \kappa ( \chi ) }$ ; II:△; E:m) 。a2，..， $\mathbf { a } _ { n - I }$ 为任意输入输出或者其他动作。执行动作 $\mathbf { a } _ { \mathrm { n } }$ 后，自动机状态由$Q \Gamma \colon ( \nu : \nu _ { a _ { n - 1 } } ; s : s _ { a _ { n - 1 } } ; \Pi { : } \Delta ; \Xi { : } \mathfrak { N } )$ 转换为$Q \Gamma \colon ( \nu : \nu _ { a _ { n } } ; s : s _ { a _ { n } } ; \Pi { : } \Delta ; \Xi { : } \mathfrak { N } )$ 。由单调性可知，有 $s _ { a _ { n - 1 } } \leq s _ { a _ { n } }$ ，由于内部输出动作 $s _ { \kappa ( \psi ) } \leq T ( \nu )$ ，即 $s _ { a _ { n } } \leq T ( \nu )$ ，故 $s _ { a _ { n - 1 } } \leq T ( \nu )$ 。执行动作 $\mathbf { a } _ { \mathrm { n - 1 } }$ 后，自动机状态由 $Q \Gamma : ( \nu : \nu _ { a _ { n - 2 } }$ · $s : s _ { a _ { n - 2 } }$ ： $\Pi { : \Delta } ; \Xi { : \boldsymbol { \eta } }$ 转换为 $Q \Gamma \colon ( \nu : \nu _ { a _ { n - 1 } } ; s : s _ { a _ { n - 1 } } ; \Pi { : } \Delta ; \Xi { : } \mathfrak { N } )$ 。由单调性可知，有（204号 $s _ { a _ { n - 2 } } \leq s _ { a _ { n - 1 } }$ ，由 $s _ { a _ { n - 1 } } \leq T ( \nu )$ 可知 $s _ { a _ { n - 2 } } \leq T ( \nu )$ 。依次类推，可知（202 $s _ { a _ { i - 1 } } \leq s _ { a _ { i } }$ ， $s _ { a _ { i - 1 } } \leq T ( \nu )$ 。即有 $s _ { a _ { 1 } } \leq T ( \nu )$ ， $S _ { \kappa ( \chi ) } \leq T ( \nu )$ 。假设系统满足偏序关系的高级输入动作 $\kappa ( \chi _ { _ 1 } )$ 与 $\kappa ( \boldsymbol { \chi } _ { 2 } )$ 影响了系统内部输出动作，则必有， $( s _ { \kappa ( \chi _ { 1 } ) } \leq T ( \nu ) ) \land ( s _ { \kappa ( \chi _ { 2 } ) } \not \subset T ( \nu ) )$ 或者$( s _ { \kappa ( \chi _ { 1 } ) } \subset T ( \nu ) ) \land ( s _ { \kappa ( \chi _ { 2 } ) } \leq T ( \nu ) )$ 。而与已知条件$( s _ { \kappa ( \chi _ { 1 } ) } \leq T ( \nu ) ) \land ( s _ { \kappa ( \chi _ { 2 } ) } \leq T ( \nu ) )$ 矛盾。故满足偏序关系的高级输入动作 $\kappa ( \chi _ { _ 1 } )$ 与 $\kappa ( \boldsymbol { \chi } _ { 2 } )$ 不影响系统内部输出。

表1自动机状态变迁示例  

<html><body><table><tr><td>程序代码</td><td>自动机输入</td><td>自动机判断</td><td>自动机状态</td></tr><tr><td>public class example{ allocate(a)</td><td></td><td>OK</td><td>{a}:{}</td></tr><tr><td></td><td>1．int a=system.in();input(a)</td><td>OK</td><td>{a}:{s1}</td></tr><tr><td rowspan="3"></td><td>allocate(b)</td><td>OK</td><td>{a,b）:{s1,}</td></tr><tr><td>2．int b=system.in();input(b)</td><td>OK</td><td>{a,b}:{s1,s2}</td></tr><tr><td>allocate(str） OK</td><td></td><td>{a,b,str}:{ s1,s2,}</td></tr><tr><td></td><td>3．String str='hello'；const(str)</td><td>OK</td><td>{a,b,str}:{ s1,s2,Φ}</td></tr><tr><td>4．a=plus(a, b);</td><td>invoke(plus) OK</td><td></td><td>{a,b,str,c,d}:{s1,s2,Φ,s1,s2}</td></tr><tr><td>5.system.out(str);</td><td>output(str)</td><td>OK</td><td>{a,b,str}:{s1△s2,s2,}</td></tr><tr><td>6.if(b)</td><td>jump(b)</td><td>NO</td><td></td></tr><tr><td>7. system.out(str)；-</td><td></td><td></td><td></td></tr><tr><td>plus(int c, int d){</td><td></td><td></td><td></td></tr><tr><td>8.c=c+d;</td><td>math(add)</td><td>OK</td><td>{a,b,str,c,d}:{s1,s2,Φ,s1△s2,s2}</td></tr><tr><td>9.return c;}</td><td>return(c)</td><td></td><td>{a,b,str}{s1△s2,s,}</td></tr><tr><td>}</td><td></td><td></td><td></td></tr></table></body></html>

# 3 系统实现与测试

# 3.1系统实现

系统实现采用动态污点跟踪技术，结合静态污点跟踪指令插入和动态污点跟踪与控制的方法，实现了对Java虚拟机细粒度地信息流跟踪与控制。既不需要获得Java应用程序源码，也不需要修改Java解释器，更独立于客户操作系统。

为实现细粒度数据标记，需要为每个程序变量设置相应污点影子变量。为便于理解，给出源代码层次污点跟踪代码插入示例，如表2所示。污点变量类型为taint，可针对不同跟踪粒度和跟踪需求进行相应设置，本文定义taint为32位无符号整数。程序变量包括基本变量类型和引用类型,基本类型如 int $a$ double $b$ 为其设置污点a_tag与b_tag。引用类型包括对象和数组，对象包括实例化的类，为其设置污点class_tag；数组又包括基本类型数组和对象类型数组，基本类型数组byte[]array 为设置污点taint[]arrar_tag，每个数组值对应相应污点值，对象类型数组污点值保存于相应对象中。Java虚拟机栈包括两部分：操作栈和局部变量区，该两部分可看做一个方法帧，对于方法调用 $\operatorname { p l u s } ( c , d )$ ，需要创建一个新的方法帧，并传递参数及其污点 $\mathrm { p l u s } ( c , c \_ t a g , d , d \_ t a g ) ,$ 。当调用结束时，需要返回相应的数值及其污点标记。因而，在非空返回时，需要将数值及其污点存入容器内并返回 return taintint.valueof $\tilde { ( c , c \_ t a g ) }$ ，返回后销毁该帧。

表2污点跟踪代码插入示例  

<html><body><table><tr><td colspan="2">原始程序代码</td></tr><tr><td>public class example{</td><td>public class example{</td></tr><tr><td rowspan="3">int a;</td><td>taint class_tag;</td></tr><tr><td>int a;</td></tr><tr><td>taint a_tag;</td></tr><tr><td rowspan="2">double b;</td><td>double b;</td></tr><tr><td>taint b_tag;</td></tr><tr><td rowspan="2">byte[] array;</td><td>byte[] array;</td></tr><tr><td>taint[] arrar_tag;</td></tr><tr><td rowspan="2">array= new byte[5];</td><td>array= new byte[5];</td></tr><tr><td>array= new taint[5];</td></tr><tr><td>plus(int c,int d){</td><td>plus(int c,taint c_tag,int d,taint d_tag){</td></tr><tr><td rowspan="2">c=c+d;</td><td>c=c+d;</td></tr><tr><td>c_tag=c_tag|d_tag;</td></tr><tr><td>return c;}</td><td>return taintint.valueof(c,c_tag)}</td></tr><tr><td>}</td><td>}</td></tr></table></body></html>

为实现细粒度信息流跟踪，需要为每种可发生污点传播的指令进行污点传播。其具有代表性的指令如表3所示。

为实现细粒度信息流控制，需要在程序关键调用点进行数据污点标记和数据污点检测。用户可使用配置文件预定义某类方法返回值污点类型(如用户键盘输入)及方法参数的污点检测(如执行 SQL 语句)。同时，用户可使用 SetTaint(val,taint)和GetTaint(val)来设置和获取任意变量的污点标记。

表3指令级污点传播分析  

<html><body><table><tr><td>序号</td><td>指令类型</td><td>指令含义</td><td>污点传播操作</td></tr><tr><td>1</td><td>算术(add)</td><td>将栈顶两数相加</td><td>将栈顶两数污点标记交汇运算后更新 栈顶数污点标记</td></tr><tr><td>2</td><td>分配 (newarray)</td><td>创建指定长度的数组</td><td>将数组长度变量污点设置为空，并创 建相应长度的污点影子数组</td></tr><tr><td>3</td><td>取数 1(iload)</td><td>从本地变量取数入栈</td><td>将相应本地变量的污点影子变量取到 栈顶下</td></tr><tr><td>4</td><td>取数</td><td>从数组中取数入栈</td><td>将该数索引值污点设置为空，并将其 污点影子数组相应索引位置取入栈顶</td></tr><tr><td></td><td>2(iaload)</td><td></td><td>下</td></tr><tr><td>5</td><td>存数 1(istore)</td><td>将数据存入本地变量</td><td>将相应本地变量的污点影子变量存入</td></tr><tr><td>6</td><td>存数 2(iaload)</td><td>将数据存入数组</td><td>将该数索引值污点设置为空，并将其 污点存入相应索引位置污点影子数组</td></tr><tr><td>7</td><td>返回</td><td></td><td>将方法的返回值于栈顶将返回值及其污点值存入返回容器，</td></tr><tr><td></td><td>1(ireturn)</td><td>返回</td><td>执行areturn</td></tr><tr><td>8</td><td>返回 2(areturn)</td><td>将方法的引用对象于栈 顶返回</td><td>若该栈顶对象是基本类型数组，存入 其数值与污点</td></tr><tr><td>9</td><td>常数(iconst)</td><td>取常数入栈</td><td>将相应污点影子变量设置为空</td></tr><tr><td>10</td><td>跳转1(ifge)</td><td>比较栈顶整数并跳转</td><td>栈顶弹出相应的污点影子变量</td></tr><tr><td>11</td><td>跳转</td><td></td><td></td></tr><tr><td></td><td>2(if_icmpge)</td><td>比较栈顶两整数并跳转</td><td>栈顶弹出相应的两污点影子变量</td></tr><tr><td>12</td><td>交换(swap)</td><td>交换栈顶两数</td><td>交换两数相应的污点数值</td></tr><tr><td>13</td><td>弹出(pop)</td><td>栈顶弹出</td><td>若该数是基本类型或基本类型数组，</td></tr><tr><td></td><td></td><td></td><td>弹出其污点影子变量</td></tr><tr><td>14</td><td>调用</td><td>调用一个方法，弹出调</td><td>将该方法转换为含污点参数的调用方</td></tr><tr><td></td><td>(invoke)</td><td>用参数并压入返回值</td><td>法，若参数对象通过基本类型数组传</td></tr><tr><td></td><td></td><td></td><td>递，将其存入容器</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td>长度</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>计算数组长度</td><td></td></tr><tr><td>15</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>在栈顶返回值下存入数值‘0'</td></tr></table></body></html>

# 3.2 系统测试

系统测试环境为：os/Ubuntu-12.04,CPU/2.27GHz,RAM/4GB,使用虚拟机版本为OpenJDK“IcedTea”JVM1.8.0。选择测试工具 Scalabench。

第一，测试两系统的运行时间，每个子测试项目运行10次并记录平均值（子测试项目详细信息可参见：http://www.benchmarks.scalabench.org/modules/scala-benchmark-suite/)，其结果如图2所示。IF-JVM较JVM运行效率平均延迟$5 3 . 1 \%$ ，这是由于除了运行程序自身指令之外，还需要运行静态插入的污点传播指令。其中子测试项目scaladoc性能延迟最大，这是由于该测试程序中对于数组及字符串等对象处理指令过多，导致污点传播指令增多。

![](images/ce9b3ea4fe4e2993ba2e6f06f986756117f1df4d5a1dcab667e8cc03ee8cd8cd.jpg)  
图2两系统运行时间对比  
图3两系统堆空间占用对比

第二，测试两系统在运行时最大堆的内存占用，其结果如图3所示。IF-JVM较JVM平均多占用堆内存 $323 . 1 \%$ ，这是由于除了程序自身数据结构需要占用堆内存之外，静态插入的用于保存相应数据的污点数据结构也需要占用堆内存。

3000 JVM 2500 ■IF-JVM KB 1000 J.n 500 foy

# 4 结束语

针对当前面向Java的信息流分析工作需要修改编译器或实时执行环境，对已有系统兼容性差且缺乏形式化分析与安全性证明等不足，提出了基于有限状态自动机的Java信息流分析方法，并证明了程序执行的无干扰安全性。采用静态污点跟踪指令插入和动态污点跟踪与控制的方法实现了原型系统IF-JVM，实验结果表明原型系统能正确实现了对Java虚拟机细粒度地信息流跟踪与控制。后续可研究插桩系统性能优化，使得插入的污点指令更加精简高效。

# 参考文献：

[1]吴泽智，陈性元，杨智，等．信息流控制研究进展[J]．软件学报，2017, 28 (1):135-159.   
[2]Crandall JR,Chong F T.Minos:Control data attack prevention orthogonal to memory model [C]// Proc of the 37th Intetnational Symp．on Microarchitecture.LA:IEEE Press,2004:221-232.   
[3]KemerlisVP,Portokalidis G,Jee K,KeromytisAD.Libdft:Practical dynamic data flow tracking for commodity systems [J].ACM SIGPLAN Notices,2012,47(7):121-132.   
[4]Krohn M,YipA,Brodsky M, etal.Information flow control for standard OS abstractions [C]//Proc ofACM SIGOPS Operating Systems Review.New York:ACMPress,2007:321-334.   
[5]Schultz D,Liskov B.IFDB:decentralized information flow control for databases [C]//Proc of the 8th ACM European Conference on Computer Systems.New York:ACMPress,2013:43-56.   
[6]Enck W,Gilbert P, Chun BG,et al. TaintDroid: an information-flow tracking system for realtime privacy monitoring on smartphones [C]//Proc of OSDI. Berkeley:USENIX Association,2010:255-270.   
[7]Nair S K,Simpson P N D,Crispo B,et al.A virtual machine based information flow control system for policy enforcement [J].Electronic Notes in Theoretical Computer Science,2008,197(1):3-16.   
[8]Roy I,Porter D E,Bond MD,et al.Laminar:practical fine-grained decentralized information flow control[J].ACMSIGPLANNotices—PLDI, 2009,44(6): 63-74.   
[9]Haldar V,Chandra D,Franz M.Dynamic taint propagation for Java [C]// Proc of Computer Security Applications Conference.20o6:301-311.   
[10]MatejV,Binder W,Hauswirth M.ShadowData: shadowing heap objects in Java [C]//Proc ofACM Sigplan-Sigsoft Workshop on Program Analysis for Software TOOLS and Engineering.New York:ACMPress,2013:17-24.   
[11] Chandra D,Franz M.Fine-Grained information flow analysisand enforcement in a Java virtual machine $[ \mathrm { C } ] / \AA$ Proc of the 23rd Annual Computer Security Applications Conference.New York:IEEE Press,2007: 463-475.   
[12]Manivannan K,Wimmer C，Franz M.Decentralized information flow control on a bare-metal JVM[C]//Proc.of the 6th Annual Workshop on Cyber Security and Information Intelligence Research.New York:ACM Press,2010:64-74.   
[13] MyersAC,Liskov B.Protecting privacy using the decentralized label model [J].ACM Trans on Software Engineering and Methodology,2ooo,9(4): 410-442.   
[14]Myers A C.JFlow:practical mostly-static information flow control [C]// Proc of the 26th ACM SIGPLAN-SIGACT Symp.on Principles of Programming Languages.New York:ACMPress,1999:228-241.   
[15]Blackburn S M,GarnerR,Hoffmann C,et al.The dacapo benchmarks: Java benchmarking development and analysis [C]//Proc of OOPSLA.New York: ACMPress,2006:169-190.