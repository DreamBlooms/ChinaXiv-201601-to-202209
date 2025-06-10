# 嵌入式Forth操作系统实时调度算法研究

黄忠建，代红兵，王蕾

(云南大学 信息学院 云南省高校数字媒体技术重点实验室，昆明 650223)

摘要：针对目前嵌入式Forth操作系统中缺乏实时调度机制的问题，对基于Forth虚拟机架构的嵌入式操作系统中多任务调度的关键技术进行了研究。采用 Forth虚拟机技术，新定义了一种中断任务类型来处理实时突发事件，并给出了一种新的任务调度算法来调度 Forth系统中终端任务、后台任务以及中断任务顺利运行。实验结果表明，改进后的Forth 系统能够通过实时调度处理突发事件，并且实时响应度高，尤其适合应用于对实时性有要求的嵌入式环境中，以满足日趋复杂的嵌入式环境对高效操作系统和 Forth 技术的应用需求。

关键词：Forth系统；多任务；实时调度 中图分类号：TP316 doi:10.3969/j.issn.1001-3695.2018.03.0237

# Research on real-time scheduling algorithm for embedded Forth operating system

Huang Zhongjian, Dai Hongbing†,Wang Lei (Digital MediaTechnologyKeyLaboratoryofUniversitiesinYunnan,SchoolofInformationScience&EngineeingYunnan University,Kunming 650223,China)

Abstract:Forthe problemof lackingreal-time scheduling mechanismintheembeddedForthoperating system at present,this paper investigated thekeytechnologiesof multitask-schedulingofembeddedoperating systembasedonForth virtualmachine architecture.On the basisofForthvirtual machine technology，this paper definedanew interupttask type to deal with real-timeemergenciesand proposedanew schedulingalgorithm,which enabledthe schedulingof terminaltasks,background tasks and interupttasksinForthsystem tobe successfullyexecuted.The experimentalresultsdemonstrate thattheimproved Forth systemcan handle emergencies through real-time schedulingand hasa high degree of real-time responseand is especiallysuitablefortheembedded environment which isrequired forreal-time performance,soas to meetthe increasingly complex application requirements of embedded system for efficient operating system and Forth technology.

Key words:Forth system; multitask; real-time scheduling

# 0 引言

1969 年美国的Chuck Moore 发明了Forth[1]。Forth 是一种操作系统、一套开发工具、一种高级程序设计语言、一种汇编语言以及一种软件设计准则的集合体[2]。近年来，国内外对Forth的研究主要集中于Forth系统构建和Forth处理器。自Forth诞生以来，经过不断的扩展和补充，已经有了多个Forth版本，比如AmForth、SwiftX、PunyForth 等，其中 SwiftX[3]是目前最具代表性的版本。就Forth处理器而言，Edvin等人[4]介绍了一种基于堆栈的32位Forth微处理器的设计，详细阐述了这种微处理器的架构以及指令设计等方面的内容。Hanna 等人[5提出了一种称为rForth的32位Forth内核体系架构，其包括一个浮点运算单元、一个中断控制器和一个可访问的扩展内存。Ting等人[6\~I1]对在FPGA上用VHDL 设计Forth 处理器进行了描述。

此外,ChuckMoore 创办的GreenArrays公司目前已在其生产的GA144 芯片上集成了144个Forth 处理器[12]。

正如多任务调度是其他操作系统的核心功能一样，Forth系统的核心功能也包括多任务调度。最早的Forth操作系统调度采用的是与传统操作系统相同的方式，即基于CPU方式的调度，这种方式任务切换需要保存和恢复CPU现场和Forth状态，例如早期的Forth11和Forth88[13]。基于CPU方式的多任务调度存在的问题是开销太大，针对这个问题，基于虚拟机的Forth多任务操作系统（下文简称Forth系统）开始出现，其特点是简洁高效、对硬件层抽象、可重构、可扩展、可移植以及可交互，多任务基于堆栈调度，并且采用协作式轮循的调度方式，典型的有ColorForth、AmForth、PunnyForth、SwiftX 等。这种基于虚拟机的Forth操作系统由于具备了诸多的优势开始成为研究热点，并逐渐成为主流。基于虚拟机的Forth多任务调度成功解决了在任务切换时开销大的问题，但同时也带来了另一个问题：多任务调度是非实时的。

Forth系统主要应用于嵌入式领域，对于一个应用于嵌入式领域的操作系统而言，能够及时处理各种突发事件的意义不言而喻。纵览目前国内外对Forth的研究，在基于虚拟机的实时调度方面依然是空白。因此，通过对目前基于虚拟机的Forth系统中多任务调度机制相关关键问题进行研究，本文给出了一种提升Forth系统多任务调度实时性的实现方法。

# 1 现有Forth系统协作式多任务调度机制

目前主流的Forth系统普遍支持协作式多任务机制，任务调度方式为轮询调度。Forth系统提供终端任务和后台任务两种不同类型的任务，并且在数量上只有一个终端任务和允许用户建立多个后台任务。不管终端任务还是后台任务，均只有就绪和休眠两种状态，只有在就绪状态下的任务才能在任务调度时获得CPU的控制权。在单任务模式下，终端任务得到CPU的控制权。在多任务模式下，终端任务与后台任务通过协作式轮询的方式交替得到CPU的控制权。终端任务与后台任务是通过循环链表的方式组织起来的，如图1所示。

![](images/8d9325b201717128b9a4132fe60380aad23e6a44d25afc51583c56cf9b409cd9.jpg)  
图1Forth系统中终端任务与后台任务的组织方式

Sys-task代表终端任务，也即系统任务，用于与用户交互。Bg-taski\~Bg-taskn-1代表后台任务，用于在后台处理其他事情。

在Forth系统多任务调度中，pause 是任务调度原语，它的功能在于：首先保存当前正在运行的任务的执行断点，然后去任务链里寻找下一个就绪的任务，最后把CPU控制权转交给已找到的就绪的任务，之后就绪的任务开始运行。如图1所示的任务链，假设终端任务正在运行，Forth系统中协作式多任务的轮询调度的原理为：

a)终端任务正在运行，在运行的过程中遇到了任务调度原语 pause，终端任务去执行pause。在pause 中，终端任务首先保存其执行断点，然后去任务链里寻找下一个就绪的后台任务Bg-taski（1≤in-1)，最后把CPU的控制权交给Bg-taski，随后Bg-taski开始运行。

b)Bg-taski正在运行，在运行的过程中遇到了任务调度原语pause，Bg-taski去执行 pause。在 pause 中，Bg-taski首先保存其执行断点，然后去任务链里寻找下一个就绪的后台任务Bg-taskj ( $\mathrm { i } <$ j≤n-1)，最后把CPU的控制权交给Bg-taskj，随后Bg-taskj开始运行。

c)后台任务Bg-taskj正在运行，在运行的过程中遇到了任务调度原语pause，倘若在Bg-taskj与后台任务Bg-taskn-1之间已经没有就绪的任务，由于任务链是通过循环链表的方式组织起来的，那么Bg-taskj在执行pause 的过程中寻找下一个就绪任务的时候，会把CPU的控制权交给终端任务，终端任务继续从上次发生调度的断点开始往下执行。

d)终端任务在运行的过程中，通过执行pause 的方式将CPU的控制权交给Bg-taski，Bg-taski从上一次发生调度的断点继续往下执行；Bg-taski在运行的过程中，通过执行pause 的方式将CPU的控制权交给Bg-taskj，Bg-taskj从上一次发生调度的断点继续往下执行。如此不断循环，直到Bg-taski与Bg-taskj的执行体均执行完，之后系统进入单任务模式，终端任务获得CPU的控制权。

在Forth系统中，任务是竞争系统资源的最小运行单元。目前Forth系统只有终端任务和后台任务这两种不同类型的任务，在终端任务和后台任务（Bg-taski\~Bg-taskn-1）的执行期间，倘若外部有一个实时突发事件请求处理，现有Forth系统并没有实时调度机制去实时处理突发事件，这显然严重影响了Forth系统的实时性，同时也局限了Forth在对实时性有要求的嵌入式环境中的应用范围。

# 2 Forth系统实时任务调度

# 2.1Forth系统实时任务调度机制

1)Forth系统处理实时突发事件

在Forth系统协作式多任务轮询调度的基础上，结合中断技术，本文定义了一种新的任务类型---中断任务类型来处理外部实时突发事件。终端任务、后台任务以及中断任务是通过循环链表的方式组织起来的，加入了中断任务的新任务链表如下图2所示：

![](images/6c111388f358b6627f3cfb796c651da34122a4b7bbc807d8599d007035837d0c.jpg)  
图2终端任务、后台任务以及中断任务的任务链组织方式

Int-taski\~Int-taskn代表中断任务。终端任务、后台任务以及中断任务的任务状态只有两种：就绪和休眠。中断任务处理突发事件的过程为：a)外部实时突发事件产生中断请求，当前正在执行的任务转去执行中断服务程序，在中断服务程序里就绪对应的中断任务；b)调度中断任务执行。

2)中断任务的调度

Forth 系统原有的任务调度原语pause 并不能调度中断任务。按照图2所示的任务链组织方式，在原始任务调度原语pause的基础上，本文定义了一个新的任务调度原语INT-PAUSE来调度终端任务、后台任务以及中断任务，INT-PAUSE调度的基本思想是：

a)引入临界资源intTask和readyTask[]。intTask初值为0，用于记录当前中断任务链里已经就绪的中断任务的数量。readyTask[O]存储终端任务的TCB或者后台任务的TCB，目的是当中断任务执行完的时候能够返回发生中断时的终端任务或者后台任务，使终端-后台任务的任务链里下一个就绪的任务运行。每当有中断请求就绪了中断任务，intTask就加1，且readyTask[1]\~readyTask[intTask]里存储着在中断服务程序里就

绪的中断任务的TCB 地址。

b)若终端任务或者后台任务正在运行的时候来了一个中断： (a)把当前正在运行的终端任务或者后台任务的 TCB 地址存储在 readyTask[O]里；(b)intTask 加1,且readyTask[intTask]里存储就绪的中断任务的TCB地址。若中断任务正在运行的时候来个一个中断：intTask加1,且readyTask[intTask]里存储就绪的中断任务的TCB 地址。

c)当前正在运行的任务每次执行INT-PAUSE 进行任务调度的时候,若intTask大于O，调度readyTask[intTask]里存储的就绪的中断任务的TCB 运行，然后intTask 减1；若intTask 等于0并且readyTask[O]等于0，调度在终端-后台任务的任务链里下一个已经就绪的任务运行；若intTask等于0并且readyTask[O]不等于O，从readyTask[O]里存储的终端任务的TCB或者后台任务的TCB开始，调度在终端-后台任务的任务链里下一个就绪的任务运行，然后将readyTask[O]赋值为0。

按照图2所示的任务链组织方式，某个就绪的中断任务Int-taskk从就绪到运行需要等待的时间为

$$
T _ { _ { k - w a i t } } = T _ { i } + \sum _ { m = k + 1 } ^ { m = i n t T a s k } T _ { _ { m - e x e c } } + ( i n t T a s k - k + 1 ) ^ { * } T _ { _ { I N T - P A U S E } }
$$

其中:1≤k≤n，0≤i≤n-1，当 $\mathrm { i } { = } 0$ 时， $\mathrm { T _ { i } }$ 表示终端任务从发生中断的地方执行到任务调度原语INT-PAUSE的时间，当 $\mathrm { i } { \neq } 0$ 时，$\mathrm { { T } _ { i } }$ 表示后台任务从发生中断的地方执行到任务调度原语INT-PAUSE的时间。 $\mathrm { T } _ { \mathrm { m - e x e c } }$ 为中断任务Int-taskm一次执行完其执行体的时间，且 $\mathbf { k } { + } \mathbf { l }$ ≤intTasK。TINT-PAUSE为任务调度原语INT-PAUSE的执行时间。

当 $k { + } 1 >$ intTask时，即Int-taskk表示中断任务链里最后一个就绪的任务，Tk-wait =T+TINT-PAUSE

当中断任务链里只有一个任务Int-taski就绪时，$T _ { _ { 1 - w a i t } } = T _ { _ { i } } + T _ { _ { I N T - P A U S E } }$

当中断任务里 $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 个中断任务全部就绪时，$T _ { \scriptscriptstyle { \mathrm { n - w } a i t } } \leq T _ { \scriptscriptstyle { k - w a i t } } \leq T _ { \scriptscriptstyle { 1 - w a i t } } ( 1 \leq k \leq n )$ ，即

$$
T _ { i } + T _ { _ { I N T - P A U S E } } \leq T _ { _ { k - w a i t } } \leq T _ { i } + \sum _ { m = 2 } ^ { m = n } T _ { _ { m - e x e c } } + n ^ { * } T _ { _ { I N T - P A U S E } } \circ
$$

由于在终端任务或者后台任务的执行体中何处才开始调度是由程序员人为加入INT-PAUSE决定的，因此 $\mathrm { T _ { i } }$ 是不确定的，同时 $\mathrm { { T } _ { \mathrm { { m } } } }$ 也取决于中断任务执行体需要执行时间的长短。

# 2.2Forth系统实时调度算法

1)中断任务类型(1)中断任务的任务控制块

加上本文创建的中断任务类型，Forth系统目前能够提供三种类型的任务：终端任务、后台任务以及中断任务。其中，中断任务用于处理外部突发的事件。每个中断任务都拥有自己的任务控制块（TCB)。终端任务的TCB、所有后台任务的TCB和所有中断任务的TCB都位于用户区里，这些TCB是按照图2所示的循环链表方式组织起来，通过本文新定义的任务调度原语INT-PAUSE进行调度，如图3所示。

![](images/f0093182b435046eadead0e46d29e73359e72f7d12f9c0eb594a14748a95399e.jpg)  
图3Forth系统运行时的存储映像图

中断任务的TCB里定义了该任务运行时的信息，这些信息包括：任务的状态是就绪还是休眠；指向循环TCB链表中的下一个TCB；堆栈从哪里开始，目前有多少条目；一个用于识别该任务是中断任务的标志。结构如表1所示。

表1Forth系统中断任务的任务控制块结构  

<html><body><table><tr><td>地址偏移</td><td>用途</td></tr><tr><td>0</td><td> status</td></tr><tr><td>2</td><td>follower</td></tr><tr><td>4</td><td>rp0</td></tr><tr><td>6</td><td>sp0</td></tr><tr><td>8</td><td>sp</td></tr><tr><td>10</td><td>TaskType</td></tr></table></body></html>

其中：status 描述的是任务的状态，存储的是任务就绪词WAKE或任务休眠词PASS的执行地址；follower存储的是下一个中断任务的TCB 的地址；rp0描述的是当前中断任务的返回栈栈底指针；sp0描述的是当前中断任务的参数栈栈底指针；sp 描述的是当前中断任务的参数栈栈顶指针；TaskType 的值为1，描述的是该任务是中断任务，终端任务以及后台任务的TCB里也有这个标识，其值为0。

(2)中断任务的创建

通过INT-TASK:来创建一个中断任务。例如，用INT-TASK:来创建一个中断任务Int-taski：3232INT-TASK:Int-taski.第一个32代表Int-taski的返回栈空间有32个存储单元，第二个32代表Int-taski的参数栈空间有32个存储单元。

采用Forth2012 标准[14]，INT-TASK:的算法如下：

: INT-TASK: $\textcircled{1}$ <builds $\textcircled{2}$ （204号 here，

[s"/user"environment search-wordlist drop execute ] $\textcircled{3}$ literal $\textcircled{4}$ (rstacksize ）allot here , $\textcircled{5}$ （dstacksize）allot here, $\textcircled{6}$ does> ·

$\textcircled{1}$ <builds在词典里生成名称为Int-taski的名字域NFA词典条目，<builds与does>之间的词就是在创建中断任务Int-task1需要做的动作。名称Int-taski生成后，词典中下一个可用的存储单元就是Int-taski的参数域PFA的第一个字节的地址。以后执行Int-taski时，Int-taski的参数域的第一个字节的地址会被保留在参数栈的栈顶。

$\textcircled{2}$ here 将用户区中下一个可用存储单元的地址放到参数栈栈顶，词，将该地址存到词典里Int-taski的参数域中。

$\textcircled{3}$ literal在用户区里为Int-taski分配其TCB里地址偏移从0\~10 的地址空间。

$\textcircled{4}$ allot在用户区里为中断任务Int-taski分配32个存储单元来作为返回栈空间，然后词，将用户区里下一个可用的存储单元的地址存在词典里Int-taski的参数域中。

$\textcircled{5}$ allot在用户区里为中断任务Int-taski分配32个存储单元来作为参数栈空间，然后词，将用户区里下一个可用的存储单元的地址存在词典里Int-taski的参数域中。

Int-taski的存储映像图如下图4所示：

![](images/0f9d5cf8498327bbe271803465b677dabe7c1672cc7f033833354d640e8f9b13.jpg)  
图4Int-task1的存储映像图

(3)中断任务的运行

中断任务Int-taski建好后，还需要经过以下几个步骤才能得到运行：

a)初始化中断任务Int-taski的TCB。将中断任务的参数栈指针和返回栈指针指向正确的位置，将中断任务的执行体（突发事件要做的事情）地址放到中断任务的返回栈栈顶，以便Int-taski运行的时候去执行这部分代码。

b)若Int-taski是新建的第一个中断任务，那么构建一个循环的中断任务队列，即让Int-taski的TCB中follower自己指向自己；若Int-taski不是建里的第一个中断任务，将中断任务Int-taski的TCB加入到Forth系统中原先存在的中断任务的任务队列里，构成一个循环的中断任务队列。

c)外部的突发事件通过中断请求的方式请求CPU处理，而中断任务是专门用于处理外部突发事件的，因此在中断服务程序里还要使中断任务Int-taski就绪，即将词WAKE的执行地址存入到Int-taski的TCB里的status存储单元中，以便任务调度的时候Int-taski能够被调度到。

d)执行任务调度原语INT-PAUSE，使中断任务Int-taski得到CPU的控制权，处理突发事件。

2)任务调度原语INT-PAUSE

由上文的论述可知，任务调度原语INT-PAUSE用于调度终端任务、后台任务及中断任务的运行，采用Forth2012标准，INT-PAUSE算法如下：

$\textcircled{1}$ :INT-PAUSE ENTER_CRITICAL rp@ sp@ sp ! O intTask ${ \mathcal { Q } } >$ if branch1 else branch2 then EXIT_CRITICAL ;   
$\textcircled{2}$ : branch1 readyTask[intTask] $@$ tmpTCB ! 1 intTask -! tmpTCB $@$ dup $@$ i-cell+ >r ;   
$\textcircled{3}$ :branch2OreadyTask[O] $\boldsymbol { \ @ } =$ if branch3 else branch4 then ；   
$\textcircled{4}$ :branch3follower $@$ dup $@$ i-cell+ >r ;   
$\textcircled{5}$ :branch4 readyTask[0] $@$ tmpTCB ! O readyTask[O]! tmpTCB $@$ dup $@$ i-cell+ >r; :nonamecell+ $@$ dup $@$ i-cell+ >r ;constant PASS :noname up! $\operatorname { s p } @$ sp!rp!; constant WAKE

$\textcircled{1}$ INT-PAUSE执行期间，不允许CPU响应中断，ENTER_CRITICAL与EXIT_CRITICAL之间的代码是临界区。通过 $\operatorname { r p } @ \operatorname { s p } @$ sp！保存当前正在运行的任务的执行断点。若intTask大于0，说明已经有中断任务就绪，然后去分支branch1中调度中断任务运行。若intTask等于0，说明没有中断任务就绪，然后去分支branch2中寻找终端任务或者下一个就绪的后台任务运行。

$\textcircled{2}$ 在branch1中，首先将readyTask[intTask]中存储的就绪的中断任务的TCB地址赋值给tmpTCB，然后intTask减1，最后调度tmpTCB 里存储的TCB 运行，具体是当前正在运行的任务去执行存储在tmpTCB 指向的TCB 的 status 存储单元里的词WAKE（就绪)，在WAKE里将CPU的控制权交给就绪的中断任务。

$\textcircled{3}$ 在branch2中，若readyTask[O]等于0，说明当前是在终端任务或者后台任务的执行体中发生任务调度，那么branch3的功能在于在终端-后台任务的任务链里寻找下一个已经就绪的任务，找到之后将CPU的控制权交给它。若readyTask[0]不等于0，说明当前是在中断任务的执行体中发生任务调度，那么branch4的功能在于返回发生中断时的终端任务或者后台任务，使终端-后台任务的任务链下一个就绪的任务运行。

$\textcircled{4}$ 在branch3里，取出任务链里当前任务的下一个任务的TCB的 status存储单元里的内容，若里面存的是词PASS（休眠）的执行地址，则去执行PASS，在PASS里继续往下寻找，直到在任务链里找到某个status是WAKE的任务，然后去执行WAKE，在WAKE里将CPU的控制权交给找到的就绪的任务，之后恢复就绪任务的执行断点，最后就绪的任务开始执行。

$\textcircled{5}$ 在branch4里，首先将readyTask[O]中存储的就绪的终端任务或者后台任务的TCB地址赋值给tmpTCB，然后readyTask[O]赋值O，最后调度tmpTCB里存储的TCB运行。

与基于CPU调度相比，对于基于虚拟机的Forth实时操作系统而言，其任务调度时现场保护仅需要将当前返回栈指针 rp压入参数栈，并将当前参数栈指针sp保存到该任务的用户变量区里。而恢复现场仅需要从该任务的用户变量区里恢复sp，并将参数栈栈顶值存入rp指针。

# 3 实验验证与分析

本文中Forth系统实时任务调度机制的具体实现基于开源的AmForth。AmForth 是一个16位的Forth系统，其运行在ATmega328芯片上，ATmega328是一个高性能、低功耗的AVR8位微控制器，支持中断处理，时钟频率16MHz，并且有32KB的flash、2KB的 RAM以及1KB 的 EEPROM 存储空间。ATmega328P能够提供外部请求中断、引脚变化请求中断、定时器中断、串口中断等不同类型的中断。所有中断在中断向量表中都有一个单独的中断向量。这些中断具有与中断向量位置相同的优先级，中断向量地址越低，优先级越高。

由2.1节的分析可知，按照INT-PAUSE的调度方式，后台任务的数量并不会影响某个就绪的中断任务Int-taskk从就绪到运行需要等待的时间，中断任务Int-taskk从就绪到运行需要等待的时间与下列因素有关：a)终端任务或者后台任务从发生中断的地方执行到任务调度原语INT-PAUSE的时间；b)中断任务的数量以及中断任务一次执行完其执行体的时间；c)任务调度原语INT-PAUSE的执行时间。

在AmForth中新建一个后台任务Bg-taski，终端任务Sys-task 的执行体由程序段 $\textcircled{2} \textcircled{4} \textcircled{5}$ 组成，后台任务Bg-taski的执行体由程序段 $\textcircled{1} \textcircled{3}$ 组成。突发事件在程序段 $\textcircled{1}$ 中通过中断的方式先后就绪了中断任务Int-taski\~Int-task5，中断任务Int-taski\~Int-task5的执行体分别是程序段 $\textcircled{6}$ 美 $\textcircled{10}$ ，如图5所示。

Sys-task Bg-task1 Int-task1 Int-task2 就绪中断任务 ① Int-task \~Int-task5 ⑥ 1   
INT-PAUSE INT-PAUSE INT-PAUSE ② INT-PAUSE Int-task3 Int-task4 Int-tasks ③   
INT-PAUSE ? 9 ① ④ INT-PAUSE INT-PAUSE INT-PAUSE INT-PAUSE   
INT-PAUSE ⑤ Sys-task Bg-task1   
Int-task1 Int-task2 Int-task3 Int-task4 Int-task5

后台任务Bg-taski将程序段 $\textcircled{1}$ 执行完后，中断任务就绪表readyTask[]的存储情况如图6所示。

0 1 2 3 4 5 Bg-task1 Int-task1 Int-task2 Int-task3 Int-task4 Int-task5 readyTask: 的TCB地址 的TCB地址 的TCB地址 的TCB地址 的TCB地址 的TCB地址 intTask=5

表2给出了在INT-PAUSE调度方式下，中断任务Int-taski\~Int-tasks从就绪到运行需要等待的时间。

表2Int-task1\~Int-task5从就绪到运行等待的时间 /ms  

<html><body><table><tr><td>就绪的任务</td><td>从就绪到运行需要等待的时间</td></tr><tr><td>Int-task1</td><td>18</td></tr><tr><td>Int-task2</td><td>16</td></tr><tr><td>Int-task3</td><td>12</td></tr><tr><td>Int-task4</td><td>11</td></tr><tr><td>Int-task5</td><td>9</td></tr></table></body></html>

TINT-PAUSE表示任务调度原语INT-PAUSE的执行时间， $\mathrm { \Delta T _ { 1 } }$ 表示后台任务Bg-taski在程序段 $\textcircled{1}$ 中从发生中断的地方执行到INT-PAUSE所用的时间，由表2和INT-PAUSE的调度过程可以得出：

a)中断任务Int-tasks从就绪到运行需要等待的时间

$$
T _ { \scriptscriptstyle 5 - w a i t } = T _ { \scriptscriptstyle 1 } + T _ { \scriptscriptstyle { I N T - P A U S E } } = 9 \mathrm { m s }
$$

b)T5-exec表示中断任务Int-task5执行其执行体所用的时间，中断任务Int-task4从就绪到运行需要等待的时间

$$
\begin{array} { r l } & { T _ { 4 - w a i t } = T _ { 5 - w a i t } + T _ { 5 - e x e c } + T _ { { I N T - P A U S E } } } \\ & { \qquad = T _ { 1 } + T _ { 5 - e x e c } + 2 ^ { * } T _ { { I N T - P A U S E } } } \\ & { \qquad = 1 \operatorname* { l m s } } \end{array}
$$

$\mathrm { c ) T _ { 4 - e x e c } }$ 表示中断任务Int-task4执行其执行体所用的时间，中断任务Int-task3从就绪到运行需要等待的时间

$$
\begin{array} { l } { { \displaystyle T _ { 3 - w a i t } = T _ { 4 - w a i t } + T _ { 4 - e x e c } + T _ { I N T - P A U S E } } } \\ { { \displaystyle \quad \quad = T _ { 1 } + \sum _ { m = 4 } ^ { m = 5 } T _ { m - e x e c } + 3 ^ { * } T _ { I N T - P A U S E } } } \\ { { \displaystyle \quad \quad = 1 2 \mathrm { m s } } } \end{array}
$$

d)T3-exec表示中断任务Int-task3执行其执行体所用的时间，中断任务Int-task2从就绪到运行需要等待的时间

$$
\begin{array} { r l } {  { T _ { _ { 2 - w a i t } } = T _ { _ { 3 - w a i t } } + T _ { _ { 3 - e x e c } } + T _ { _ { I N T - P A U S E } } } } \\ & { = T _ { 1 } + \sum _ { m = 3 } ^ { m = 5 } T _ { _ { m - e x e c } } + 4 ^ { * } T _ { _ { I N T - P A U S E } } } \\ & { = 1 6 \mathrm { m s } } \end{array}
$$

e)T2-exec表示中断任务Int-task2执行其执行体所用的时间，中断任务Int-taski从就绪到运行需要等待的时间

$$
\begin{array} { l } { { \displaystyle T _ { _ { 1 - w a i t } } = T _ { _ { 2 - w a i t } } + T _ { _ { 2 - e x e c } } + T _ { _ { I N T - P A U S E } } } } \\ { { \displaystyle \quad \quad = T _ { _ 1 } + \sum _ { m = 2 } ^ { m = 5 } T _ { _ { m - e x e c } } + 5 ^ { * } T _ { _ { I N T - P A U S E } } } } \\ { { \displaystyle \quad = 1 8 \mathrm { m s } } } \end{array}
$$

# 4 结束语

本文通过对Forth系统中多任务调度机制的相关关键问题进行研究，针对Forth系统没有实时调度去处理实时突发事件的问题，结合中断技术，本文新建了一种中断任务类型INT-TASK:来处理突发事件。然后新定义了一个任务调度原语INT-PAUSE来实现Forth系统中终端任务、后台任务及中断任务的调度。从理论上提高了Forth系统对突发事件的实时响应性，并且在AmForth上通过实验验证了这一理论的正确性，推动了Forth系统多任务实时调度技术的发展，为基于虚拟机的嵌入式Forth系统大规模应用于对实时性有要求的嵌入式环境提供了一定的理论支撑和实现参考。

# 参考文献：

[1]Wikipedia.Charles H.Moore [EB/OL].(2018)[2018-01-01].http://en. wikipedia.org/wiki/Charles_H._Moore.   
[2]Leo B. Starting Forth [M].Hermosa Beach: FORTH Inc,1981:1-5.   
[3]FORTH Inc.SwiftForth IDE for Windows,Linux,and macOS [EB/OL]. (2018) [2018-1-12]. https://www.forth.com/embedded/.   
[4]Hjrtland E,Chen L.EP32-A 32 bit Forth micorproprocessor[C]// Proc of CCECD.New York:Institute of Electrical and Electronics Engineers Inc, 2007:518-521.   
[5]Hanna D M,Jones B,Lorenz L,et al.An embedded Forth core with floating point and branch prediction [C]// Proc of the 56th International Midwest Symposium on Circuits and Systems.New York:Institute of Electrical and Electronics Engineers Inc,2013:1055-1058.   
[6]Ting C H. VHDL Design of eP32 Microprocessor [EB/OL].(2010) [2018-2-5].http://www.forth.org/svfig/kk/08-2010-Ting. pdf.   
[7]James B.The J1 Forth CPU [EB/OL].(2018)[2018-1-10].http://www. excamera.com/sphinx/fpga-j1. html.   
[8]Don G. Forth Processor in VHDL [EB/OL]．(2018）[2018-1-15]. http://www.ultratechnology. com/4thvhdl. htm.   
[9]John R.Using Forth as a VHDL [EB/OL].(2018)[2018-1-15]. http:/testra. com/Forth/VHDL. htm.   
[10] John R.QSP16 [EB/OL].(2018）[2018-1-12].http://www.sandpipers. com/.   
[11] Pawel G,Wojciech M Z.Tethered Forth system for FPGA applications [C]//Proc of Photonics Applications in Astronomy,Communications, Industry,and High-Energy Physics Experiments 2013.   
[12] Chuck M.GreenArrays [EB/OL].(2018）[2018-1-15].http://www. greenarraychips.com/.   
[13]代红兵．高效微机实时多任务操作系统设计与实现[J].中国科学院研 究生院学报，1993,10(3):283-292.(Dai Hongbing.The design and realization of eficent microcomputer operating system of real-time multitask [J].Journal of the Graduate School of the Chines Academy of Sciences,1993,10 (3): 283-292.)   
[14] Forth200x committee.Forth 2012 Standard [EB/OL].(2018)[2018-3-12]. http://forth-standard. org/.