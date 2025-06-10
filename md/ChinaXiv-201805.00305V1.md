# 基于Forth虚拟机的嵌入式多任务操作系统体系架构研究

代红兵，周永录，安红萍，梅浩(云南大学 信息学院，云南省高校数字媒体技术重点实验室，昆明 650223)

摘要：面对越来越复杂的嵌入式应用需求以及当今嵌入式操作系统研究领域亟待解决的重构、移植、维护、可信、多核、众核等诸多难题，采用Forth 虚拟机技术，对基于Forth 虚拟机架构的嵌入式操作系统关键技术进行探索，提出一种具有良好扩展和移植特性、高效精简的基于Forth 虚拟机的嵌入式多任务操作系统体系架构。该架构采用分类存储映射、Forth向量定义和用户变量分离，实现了代码共享和多任务管理。实验结果表明，基于Forth 虚拟机架构的嵌入式操作系统在发挥Forth系统固有特性的同时，减少了资源占用，提高了系统的灵活性及运行效率。

关键词：Forth虚拟机；多任务；嵌入式环境 中图分类号：TP316 doi:10.3969/j.issn.1001-3695.2017.08.0863

# Research on embedded multitask operating system architecture based on Forth virtual machine

Dai Hongbing, Zhou Yonglu†, An Hongping, Mei Hao (SchoolofInformationScience&EngineeringYunnan University,DigitalMediaTechnologyKeyLaboratoryofUniversitiesn Kunming 650223, China)

Abstract:Faced with moreand more complex embeddedapplicationrequirementsandurgent problemsoftecurent embedded operating systemresearchareas,suchasreconstruction,transplantation,maintenance,trusted,multi-ore,manycoread soon, this paper proposed an embedded multitask operating system architecture，which presents bettr scalability,transplantation, streamlinedand eficientby exploring the key technologies of embeddedoperatingsystem basedonForth virtual machine technology.The architecture implemented code sharing and multitask managing,byusing the methods ofclasification storage mapping,Forth vectordefinitionanduser variableseparation.The experimentresultsdemonstratethattheembeddedoperating system architecture basedonForth virtual machine takes advantageof the inherent characteristicsof the system,reduces the resources consumption, and improves system flexibility and operational efficiency.

Key Words:forth virtual machine;multitask;embedded environment

# 0 引言

在以往嵌入式系统研究过程中，不断碰到现场不间断运行维护的困扰。许多在线运行的嵌入式固件出现Bug或要升级时，往往都需要宕机后在现场进行更新与维护，甚至需要撤离现场带入实验室才能解决，将更新、维护好的固件重新烧录到系统中。在某些特殊的应用场合，就需要一种全新的可重构、可扩展并且能够在线交互的实时多任务操作系统。例如在不间断的远程空间观测应用中，就期望有这类操作系统的支持：可创建观测、控制、采集、处理、通信、监测等一系列并发任务，当某一任务的应用程序出现故障时，在系统不宕机和不影响其他任务执行的情况下，通过远程终端强制阻塞该任务，完成在线修改或下载更新后，重新让该任务进入就绪状态，启动运行。

进一步考虑，若以上系统是一个解释/编译的双状态系统，那么代码维护将变得更加直接而且迅捷；若应用程序是积木式的架构，那么代码修复只需要简单替换存在Bug的模块，而不需要重新加载整个程序。现时是否有满足以上嵌入式领域资源条件有限情况下复杂应用需求的操作系统呢？答案之一便是基于Forth虚拟机架构的嵌入式多任务操作系统(FVMOS,embeddedmulti-task operating system based on the Forth virtual machinearchitecture）。

Forth语言本身就是一种过程控制语言和一种快速开发环境，而不仅仅是一个单纯的编程工具，具有很强的交互性、构造性、移植性和自扩展能力，以及高效的生成代码，甚至可以快速构造出一个实时多任务操作系统[1]。Forth语言自发明以来，先后形成了FIG-Forth、Forth-79、Forth-83、ANSIX3.215-1994[2]、

ISO/IEC15145:1997、FORTH-2012[3]等标准。目前，Forth语言已越来越广泛地用于设计嵌入式软件和固件，例如FlashForth(PIC18Fxxxx);PicForth(PIC16F8xx);hForth(x86 StrongARM);QuartusForth（PalmPilot）、F68KANS（68K)；Forth for theTMS320C50 [4]、Mecrisp-Stellaris（ARM-Cortex）、PunyForth（ESP8266）、AmForth（ArduinoAVR8）等等系统，几乎涵盖了所有主流的嵌入式处理器。严格讲，以上这些都仅仅只是Forth语言编程环境，真正将Forth推向操作系统领域的是美国KittPeak天文台开发的StandAloneForth11[5],并一直成为Forth操作系统保持至今的标杆。

StandAloneForth11系统，其主体实际是一个具有快速I/O能力的多任务操作系统，其最显著的特点是利用了PDP-11 小型机的页地址映射实现了Forth字典的共享。除ROM内监控导引程序外，整个系统代码仅为40K。此后出现的StandAloneForth88[6]，由于缺少页地址映射机制，没有实现代码的复用，每个任务都是一个独立运行的虚拟机，占据64K内存。ChuckMoore在SEAforth系列单芯40核处理器、100 核处理器[7\~9]研究的基础上，推出了第一个精简的嵌入式Forth 操作系统一Colorforth，其内嵌一个多任务操作系统和基本I/O驱动，核心可重入代码仅2K，现已从最初的RISC处理器拓展到多个平台。Colorforth的测试结果表明，对同一个应用，Forth的代码量仅有C语言的 $1 \%$ ，而且K级的代码可以完成传统M级操作系统相同的操作[10]。在业界真正获得较大影响的是Forth 公司推出的SwiftX，其也内嵌了一个高效精简的Forth 多任务操作系统 SwiftOS[1I]，其特点除了具备良好的移植特性外，就是系统可重构。典型的例子就是如果不考虑终端任务，生成的目标系统中甚至可以不包含文本解释器。

与传统的操作系统架构不同，FVMOS并不直接运行在硬件处理器上，而是与用户任务程序一样共同运行在Forth虚拟机上。因此，FVMOS的体系架构实质就是多任务的布局，与多任务管理密不可分。虽然在前期研究工作中，依据Forth思维，初步提出了一个EFOS（Embedded Forth Operating System）系统框架[12]，但没有充分体现出基于FVM的设计思想，遗留了若干有待深入研究的问题。本文在主流FVMOS多任务操作系统体系架构研究的基础上，以可重构、可扩展、可移植、可交互的多任务组织管理为目标，提出一种满足复杂嵌入式应用需求的FVMOS体系架构以及相应的多任务管理算法。

# 1 FVMOS总体架构

# 1.1Forth 虚拟机

FVMOS的硬件平台既可是硬件的Forth堆栈处理器，也可是寄存器型处理器。由于操作系统是在Forth虚拟机上运行，这就决定了其实现存在着较大的独特性。

从Forth系统结构看，Forth是一个词典式结构系统。词典由若干字典组成，字典由Forth定义（包含NF名字场、LF链接场、CF代码场、PF 参数场）组成，每个Forth 定义对应系统中的一个具有独立功能的程序。所有Forth定义都以统一的数据结构（词典结构）组织链接在一起（LFA指向前一Forth字），Forth定义之间遵循严格的有序调用关系，即高层Forth定义只能调用低层Forth定义，Forth定义之间的层次关系完全隐含在Forth定义当中。字典最底层的Forth定义为堆栈处理器指令组成的代码或由汇编指令组成的Code定义，上层为冒号定义（高级定义）。

从Forth运行机制看，Forth是一个合并了解释程序和编译程序的双状态系统。Forth虚拟机直接运行堆栈处理器指令或由汇编指令组成的Code代码，所不同的是，对寄存器处理器来说，多了一个地址解释程序(或内层解释程序，机器原语)Next 控制Code代码的执行。在Next之外，还有一个控制整个系统的主控循环Quit，即解释编译程序。在Quit的控制之下，一个新输入/扫描的字符串若在字典中被找到，其CFA 将被编译进字典（编译态)；或转向Next立即执行（执行态)。若在字典中没有找到，就转换为数值，编译进字典(编译态)；或压入堆栈(执行态）。

# 1.2 FVMOS

在主流FVMOS体系架构研究的基础上，本文提出了FVMOS总体架构，如图1所示。架构在CPU之上的FVM实际就是Forth的地址解释程序NEXT，其运行时所用的堆栈是当前运行任务在各自用户变量区里的私有堆栈，系统上电时，使用的是Stask的堆栈。FVM作为一级抽象很好的屏蔽了系统的硬件细节，其指令指针存放在各自任务的返回栈里，只需要一个当前用户变量区指针UP 就能在任务间进行切换，因此没有传统上下文切换的额外开销。

![](images/b2e0c4eaedb5e86c52896711cf65d830f443213a701044a511c80067c27502f3.jpg)  
图1FVMOS 总体架构

按照以往的布局，需要分别建立FLASH和RAM两个字典，但这种方式不仅增加了字典管理的开销，而且在实际使用过程中一旦系统掉电，系统就会恢复到上电前的状态，RAM中动态加载的任务就会丢失。因此本架构将在FVM上运行的全部Forth可重入代码存放到Flash中。其中，FBS的底层是Code定义，上层是高级定义。在FBS之上是向下依赖由高级定义组成的FVMOS，再往上是由FVMOS创建的隶属Stask的若干用户任务。为精简目标系统，本架构设计了可裁减的FBS选项，若应用系统不考虑在线交互，生成的目标系统中可以不包含文本解释器 Interpreter。

RAM中有若干与用户任务相对应的由任务控制块TCB、返回栈RS、数据栈DS等组成的用户变量区，以及文本输入缓冲区TIB、其他用户变量区和普通变量区等存储项。逻辑上，FBS、FVMOS都可以进行RAM操作（虚框细箭头)，但物理上，系统的存取操作被封装在FBS的底层Code定义中，实际操作是透过这些分类存取指令完成的(粗箭头)。与抢占式StandAloneForth88不同，协同式FVMOS支持终端任务、后台任务和中断任务三种任务类型，虽然三种任务的TCB内容有差异，但都连接到多任务循环链表中（右虚线）。

在体系架构方面，FVMOS 架构应当在Forth 核心词典和主控循环Quit之上，这与直接在寄存器处理器上架构操作系统有着明显的差异。此外，其词典式生长结构，也与单体内核结构（模块法）、层次结构以及微内核结构等传统操作系统架构方法有着明显的不同。若仅考虑单核Forth 虚拟机，其可选的实时多任务操作系统实现方式为：利用Forth自身的特点，直接用汇编、C语言或多或Forth自生成器（可异构）生成一个包含Forth虚拟机的基本系统FBS（ForthBasic System)，也就是系统任务Stask（第一个终端任务)，之后在其上定义封装：任务管理、内存管理、设备管理、错误陷井等FVMOS原语构件。若存储在Flash中的FBS 和FVMOS是可重入的，那么新创建的用户任务Utask只在RAM用户变量区中建立任务数据空间（运行在同一个Forth 虚拟机之上，适合于多核SMP 模式)，否则就需要复制Stask到新的Flash和RAM工作区（运行在多个虚拟机之上，适合于多核AMP 模式或多核离散模型)同时，初始Utask的任务控制块TCB，并将新的TCB插入到系统的TCB链表中，进入多任务调度。

在抽象描述方面，与微内核的设计思路不同，由于是在经过一定抽象的堆栈虚拟机上运行，FVMOS本身就具有较强的跨平台移植性。从层次上看，FVMOS 并没有像传统操作系统那样直接对硬件进行封装，而是运行在虚拟机之上。理论上，排除效率问题，整个FVMOS可以不涉及任何汇编语言，其原语和任务体都能从FBS 的Forth 定义像搭积木一样构造出来。在异构平台的抽象化描述方面，与WindowsNT、Nanokernel、eCos 等基于硬件抽象层（HAL）设计的操作系统相比，FVMOS也有其独特的特点和优势。

# 2 FVMOS存储架构

# 2.1内存分配与管理

在前期研究的基础上，针对嵌入式的存储布局以及Forth主流的协同调度算法（Cooperative schedulingalgorithm，Round-

Robin）的特点，重新优化了设计，放弃了源自 $\mathbf { x } 8 6$ 将Forth 内存划分为代码段（CS：）、数据段（DS：）、虚拟段（VS：）和堆栈段（SS：)等四个逻辑独立段的设计思路，建立Flash、RAM、EPROM等三组存取操作定义和相应的指针，分别用于存放代码、数据和参数。

Flash里存放着可重入的FBS和FVMOS，其分配由DP指针决定，存取操作定义包括：，、 $@ ^ { \phantom { \dagger } }$ 、IHERE 和IALLOT等。RAM里存放所有程序运行的数据，存取操作定义包括：！、 $@$ 、HERE和ALLOT等。其中，UP指针用于指示当前正在运行任务的用户变量区首址（TCB)。一般的嵌入式处理器缺乏页地址映射和内存保护机制，为实现代码保护，可以隐藏Flash的显式存取操作。

考虑到Forth在线交互过程中允许随时加载新代码的复杂性，在Forth系统中，Flash中的DP是严格按地址递增顺序进行分配的。与之对应的RAM里的UP既可以按实际需求进行简单的顺序分配，也可按动态分配回收算法、缓冲池等技术实现数据区的动态存储管理。

# 2.2 可重入与用户变量区

可重入代码要求除常量之外不能含有任何私有变量，上述存储管理模式可以支持统的可重入改造，只要稍作修改，整个Forth系统就能实现可重入。Forth系统的特点决定了系统运行的大多数参数及结果都可以存放在数据栈或返回栈中，要处理的字符串、变量、数组可以保存到系统分配给每个任务的RAM数据区中。

引入Forth用户变量是实现以上目标的关键。为保证可重入，可以定义一些公共例程去寻址RAM数据区里的变量，这些变量就是Forth用户变量。Forth用户变量实际就是地址变量，用户变量定义中PF里存储的是该变量在RAM中的地址。

用户变量区是RAM的一块特殊区域。每个任务都可以共享文本解释器、I/O驱动等代码，但每个任务都有独自的以用户变量定义的操作数据，这些私有数据存放在RAM数据区的不同区域，这个区域就是用户变量区。

# 2.3任务控制块

Forth操作系统多任务调度往往采用的是协同式调度策略，也就是说每个任务的启动时间都是预先确定好的。与其他多任务调度方式不同，FVMOS的协同式调度是基于虚拟机的，支持终端任务、后台任务和中断任务三种任务类型，在上述内存管理方式下，现场保护仅需要将当前返回栈指针RP压入数据栈，并将当前数据栈指针SP保存到该任务的用户变量区里。而恢复现场仅需要从该任务的用户变量区里恢复SP，并将栈顶值存入RP指针。FVMOS的任务控制块（TCB，TaskControlBlock）就是用户变量区里与多任务调度有关的一块特殊区域，其结构如表1所示。

TCB表中每一项都是通过用户变量USER定义的，其中基本表项（前六项）是每个任务的必备项，而附加表项是专门针对终端任务而设置的。附加表项（I/O驱动）存放的是该终端任务的I/O驱动向量，与该任务具体连接的终端设备有关。附加表项（解释器操作）存放的是该终端任务文本解释器与状态有关的操作向量。需要说明的是TCB没有保留返回栈指针，而是将当前返回栈指针放在数据栈栈顶。

表1TCB结构  

<html><body><table><tr><td>序号</td><td>偏移</td><td>名称</td><td>描述</td><td>类别</td></tr><tr><td>1</td><td>0</td><td>status</td><td>任务状态的xt，UP 指针</td><td></td></tr><tr><td>2</td><td>2</td><td>follower</td><td>下一个任务的 TCB 首址</td><td></td></tr><tr><td>3</td><td>4</td><td>rp0</td><td>返回栈栈底指针</td><td></td></tr><tr><td>4</td><td>6</td><td>sp0</td><td>数据栈栈底指针</td><td>基本表项</td></tr><tr><td></td><td></td><td></td><td>数据栈栈顶指针</td><td></td></tr><tr><td>5</td><td>8</td><td>sp</td><td>(TOS)</td><td></td></tr><tr><td>6</td><td>10</td><td>CATCHER</td><td>错误陷阱</td><td></td></tr><tr><td>7</td><td>12</td><td>BASE</td><td>数值转换</td><td></td></tr><tr><td>8</td><td>14</td><td>EMIT</td><td>输出字符</td><td></td></tr><tr><td>9</td><td>16</td><td>EMIT?</td><td>输出设备就绪</td><td></td></tr><tr><td>10</td><td>18</td><td>TYPE</td><td>输出字符串</td><td></td></tr><tr><td>11</td><td>20</td><td>CR</td><td>回车</td><td>附加表项（I/O驱</td></tr><tr><td>12</td><td>22</td><td>PAGE</td><td>换页</td><td>动）</td></tr><tr><td>13</td><td>24</td><td>AT-XY</td><td>移动光标</td><td>向量定义</td></tr><tr><td>14</td><td>26</td><td>KEY</td><td>输入字符</td><td></td></tr><tr><td>15</td><td>28</td><td>KEY?</td><td>输入字符就绪</td><td></td></tr><tr><td>16</td><td>30</td><td>ACCEPT</td><td>输入字符串</td><td></td></tr><tr><td>17</td><td>32</td><td>DEVICE</td><td>设备地址或信息</td><td></td></tr><tr><td>18</td><td>34</td><td>SOURCE</td><td>定位输入缓冲区</td><td>附加表项</td></tr><tr><td>19</td><td>36</td><td>）IN</td><td>输入流中当前偏移量</td><td>（解释器）</td></tr><tr><td>20</td><td>38</td><td>REFILL</td><td>填充输入缓冲区</td><td>向量定义</td></tr></table></body></html>

# 3 FVMOS多任务架构及组织管理

FVMOS的调度原语是PAUSE，并通过引入可随时置换的Forth向量定义PASS和WAKE，不用查找TCB表便能实现任务的快速切换。下面重点讨论与操作系统体系架构有关的任务管理算法，针对Forth语言和Forth系统的特点，本文中算法描述语言采用了Forth2012标准。

# 3.1Flash 任务定义

在Flash的Forth字典里创建一个特殊的任务定义，将分配给该任务的用户变量区首址保存到cfa代码场里，返回栈、数据栈栈底指针保存到pfa参数场里，定义的cfa和pfa共同组成了任务信息块（TIB，TaskInformationBlock)，Task定义算法如下：

1／ds rs us"name"--ds、rs、us 分别是数据栈、返回栈、追  
加的用户区大小  
2:TASK  
3 <BUILDS／在Flash Forth 字典里创建一个任务定义  
4HERE，／将HERE（RAM中TCB可用地址）存入FlaSh任务定义的

# cfa

5（us） $\& 1 2 ~ +$ ALLOT／在RAM中分配用户变量区（前6项）  
6（rs）ALLOTHERE，／分配返回栈，将rp0保存到Flash 该任  
务定义的pfa[0]  
7（ds）ALLOT HERE，／分配数据栈，将 sp0 保存到Flash 该任  
务定义的pfa[1]  
81ALLOT／分隔  
9 DOES>；／执行任务时，将cfa 压入数据栈

入口参数ds、rs、us分别是数据栈、返回栈、追加的用户区大小，通过<BUILDS 在 Flash 中创建一个任务头，随后将RAM用户变量区中的可用地址HERE（与之对应，Flash操作为IHERE）存入Flash任务定义的cfa（即TCB首地)，在RAM用户变量区中分配TCB（前6项是基本的)，分配返回栈，将rp0 保存到Flash该任务定义的pfa[O]，分配数据栈，将 sp0 保存到Flash 该任务定义的pfa[1]。当执行该任务时（ $\mathrm { \Delta D O E S > } )$ )，将cfa压入数据栈。

# 3.2 存储区互操作

位于Flash的TIB与位于RAM的TCB之间的互操作由下列定义实现：

1 :TIB>TCB / TIB 映射到tcb[status]  
2 @I； / TIB 映射到tcb[rp0]  
3 ：TIB >RP0  
4 I-CELL+ @I ;  
5 ：TIB >SP0／TIB映射到 tcb[sp0]  
6 I-CELL+ I-CELL+ @I ;  
7 ：TIB >SIZE ／TIB换算用户变量区尺寸SIZE  
8 DUP TIB >TCB SWAP TIB >SP0 $^ { 1 + }$ SWAP-;

其中，与RAM操作 $@$ 不同， $@ ^ { \phantom { \dagger } }$ 是从Flash里取数。系统保留了Forth的习惯，将常规的存取操作符视同为RAM操作。

# 3.3任务用户变量区初始化

任务创建后，TASK-INIT负责初始化该任务用户变量区里的TCB和堆栈区，设置缺省进制为十进制(Decimal)，在尚未链接任务体前，将该任务设置为PASS 睡眠状态。TASK-INIT定义算法如下：

1：TASK-INIT  
2 DUP TIB>TCB OVER TIB>SIZE0 FILL／初始化任务用户变量  
／区里的TCB和堆栈区  
3 DUP TIB >SP0 OVER TIB>TCB &6 + ！/ tcb[sp0]=tib[sp0]  
4 DUP TIB >SPO CELL- OVER TIB>TCB $8 8 + 1$ /tcb[TOS]  
5 DUP TIB >RPO OVER TIB>TCB $8 4 + !$ /tcb[rp0] $\mathbf { \sigma } = \mathbf { \sigma }$ tib[rp0]  
6 &10 OVER TIB>TCB $\& 1 2 ~ + ~ !$ （204号 / tcb[base]=10  
7 TIB>TCB TASK-SLEEP ; / tcb[0]=PASS

入口参数为任务头执行时DOES>弹出的TIB，通过互操作转换为TCB地址，然后对RAM用户变量区的TCB和堆栈区进行清除，将保存在Flash 任务头中的 sp0 存储到 tcb[sp0]，计算出栈顶，保存到tcb[TOS]，将保存在Flash任务头中的rp0存储到tcb[rp0]，设置缺省十进制，最后将初始任务状态设置为PASS。

多任务存储架构如图2所示。

图2多任务存储架构  
![](images/8a40ec498bf9d563c78d19f4d84551b2d72641f44f119a7211e2d68b4181fb39.jpg)  
10R>ISPAUSE；／恢复多任务

# 3.4TCB 循环链表

在完成上述创建、初始化、链接任务体之后，还需要初始化和构建多任务TCB 循环链表，ADD-FIRSTTASK初始化第一个终端任务，将其 tcb[status]设置为WAKE，并将FOLLOWER指向自身。ADD-FIRSTTASK定义算法如下：

1：ADD-FIRSTTASK  
2WAKE STATUS！／将当前任务的tcb[status]设置为WAKE  
3UP@FOLLOWER！；／将FOLLOWER指向自身

通过ACTIVATE原语激活，多任务启动后，允许随时追加新的任务，ADD-NEXTTASK将tcb所指的新任务TCB表插入到多任务循环链表中。ADD-NEXTTASK定义算法如下：

1 / tcb-  
2：ADD-NEXTTASK  
3[']PAUSE DEFER@ >R／将 PAUSE 里的×t（MULTITASK-SCHEDULE  
／或NOOP）保存到返回栈  
4SINGLE／停止多任务，PAUSE被设置为NOOP  
5FOLLOWER @／得到当前任务的下一个任务 tcb  
6 OVER  
7 FOLLOWER！／将tcb 作为当前任务的下一个任务  
8 SWAP CELL+  
9！ ／将tcb 任务的下一个任务指向当前任务之前的下一个任务

入口参数为新添加任务的TCB首址。考虑到TCB表的访问属临界资源，为支持动态任务添加，一开始就将任务调度向量保存到返回栈上。在关闭多任务调度之后，取出FOLLOWER指针（当前任务指向的下一个任务)，将新任务的tcb作为当前任务的下一个任务，将当前任务的下一个任务作为新任务的下一个任务。完成TCB 循环链表的直接插入之后，从返回栈恢复任务调度向量，并随即启动任务调度。由于不涉及到优先级调度，因此本算法的TCB循环链表维护就变得十分简洁，不需要插入排序操作，算法复杂度为O(1)。过程最后启动了多任务调度，新添加的任务将得到优先执行。

# 4 实验评估

在Arduino 嵌入式硬件平台上，借助开源的Forth虚拟机,实现了FVMOS基本框架和多任务管理算法。实验环境中，在系统上电初始化阶段，先设计了含有一个终端任务TASK1和一个后台任务TASK2 的实验程序如下：

1：MS（n--）PAUSE0 ?DO 1MS LOOP；/每隔n毫秒调用 PAUSE等待  
2VARIBLEM／TASK1中TASK2 使用的全局变量M  
3：INITM（--）OM！；  
4\$40\$400 BACKGROUND-TASK TASK2／建立后台任务TASK2，在FLASH  
／中创建任务头，分配用户变量区  
5：TASK2-BODY（--）BEGIN1M+！&10 MSAGAIN；/定义TASK2任务体  
6：STARTTASKER（--） ／初始化并启动多任务  
7TASK2 BACKGROUND-INIT／TASK2 初始化，在 RAM 中创建 TCB2  
8TASK2 TIB>TCB ACTIVATE TASK2-BODY／连接TASK2 任务体  
9 ADD-FIRSTTASK／建立TCB1循环链表  
10 TASK2 TIB>TCB ADD-NEXTTASK／将TCB2 加入循环链表  
11 MULTI； ／启动多任务  
12 ：TASK-TURNKEY（--）／上电启动向量  
13 APPLTURNKEY INITM STARTTASKER;

在系统上电启动运行后，通过终端任务TASK1，建立新的后台任务TASK3，通过命令行或文件方式动态载入以下程序，实验代码如下：

1VARIBLEN／TASK1中TASK3 使用的全局变量N  
2：INITN（--）ON！；  
3\$40\$400 INTERRUPT-TASK TASK3／建立中断任务TASK3，在FLASH  
／中创建任务头，分配用户变量区  
4：TASK3-BODY（--）BEGIN1N+！&10 MS AGAIN；／定义TASK3任务体  
5：STARTTASK3（--）／初始化并启动TASK3  
6TASK3 BACKGROUND-INIT／TASK3 初始化，在 RAM中创建 TCB3  
7 TASK3 TIB>TCB ACTIVATE TASK2-BODY/连接TASK3任务体  
8 INITN  
9 TASK3 TIB>TCB ADD-NEXTTASK； /将TCB3加入循环链表

在终端任务TASK1里定义后台任务TASK2，多任务启动后，TASK1在TASK2任务体每次调用MS时执行一次；TASK2在 TASK1每次等待键盘输入时执行（内嵌PAUSE 向量)。此后，若有动态重构多任务系统的需求，可以在并发运行的终端任务TASK1里定义新的后台任务TASK3，并通过任务初始化BACKGROUND-INIT、激活连接任务体ACTIVATE以及加入循环链表ADD-NEXTTASK等操作将TASK3加入多任务循环。第一个终端任务TASK1实际就是系统任务（Stask)，除包含了FBS和FVMOS两个部分外，还涵盖了系统上电前定义的所有任务以及系统运行后通过各终端任务动态加载的新任务，因此可以通过各终端任务对所有任务进行SLEEP、WAKE、STOP等有效控制。实验表明，系统运行稳定可靠，相关算法能够达到系统可重构、可扩展、可移植、可交互的多任务组织管理目标。

与文献[6]基于CPU调度的StandAloneForth88多任务系统相比，本文提出的FVMOS多任务体系架构有诸多的优点。在嵌入式有限存储空间利用方面，基于FVM的架构缩减了TCB的规模。任务切换仅仅只需保留或恢复SP指针就能实现，这样就可将TCB中数十项CPU映像存储压缩到只需6个单元。在重构、扩展、移植方面，整个多任务管理系统建构在系统的FBS 高级定义之上，做到与硬件无关。在系统简洁性方面，特殊的调度方式和精简的TCB结构，使得系统不需要新建和维护任务队列。与StandAloneForth88中创建任务的同一层次代码量（LOC）相比，至少压缩了10倍，整体压缩了16倍，如表2所示。在快捷性方面，除了将常规带优先级的时间片轮转调度算法复杂度从 $O ( n ^ { 2 } )$ 降低到 $O ( n )$ 之外，所有多任务管理算法的复杂度均为0(1)。

表2代码量（LOC）对比  

<html><body><table><tr><td>对比项目</td><td>Stand Alone Forth88</td><td>FVMOS</td></tr><tr><td>TASK</td><td>136</td><td>12</td></tr><tr><td>MULTITASKER</td><td>2500</td><td>155</td></tr></table></body></html>

# 5 结束语

从以上分析可以看出，FVMOS与传统方式有本质的不同，并不存在严格区分的模块、层次、微内核等传统结构。虽然系统天生具有可重构特性，甚至构件化特征，但与采用构件化操作系统也不尽相同。Forth特有的堆栈和字典式结构决定了其体系架构和运行机制的特殊性。一方面，Forth特殊的穿线编码（ThreadedCode)，使Forth堆栈机的词典式结构本身就是一个可动态、交互扩展的开放性程序库。除此之外，Forth虚拟机运行环境还为系统提供了难得的跨平台能力。但另一方面，也正是因为这些特性，给基于虚拟机的多任务组织管理带来了难题。例如，由于所有过程（包括任务调度）都必须在Quit控制之下，因此经典的多任务管理算法难以直接派上用场。虽然实时性还有待提高，但本文研究的FVMOS体系架构以及多任务管理算法具有一定的现实指导意义。

# 参考文献：

[1]代红兵．新型、高效微机Forth 语言的研制[J].中国科学院研究生院学报,1993,10(1):62-69.

[2]ANSI X3.215-1994 American National Standards for Information Systems Programming Languages Forth [S]. New York: American National Standards Institute,1994.   
[3]Forth-Standard-Committee.FORTH-2012 [S/OL].(2015）．https:/forthstandard. org/.   
[4]FORTH.Inc.Featured Forth Applications[J/OL].(2009).http://www.forth. com/resources/app Notes.   
[5]Thomas E.McGuire.Kit Peak Multi-Tasking FORTH-11[J]. The Journal of Forth Application and Reseach,1984,2 (2): 57-67   
[6]代红兵．高效微机实时多任务操作系统设计与实现[J].中国科学院研 究生院学报,1993,10(3):283-292.   
[7]James Rash． Space-related applications of forth [J/OL].(2006-09）. http://forth. gsfc. nasa. gov/.   
[8]Caffrey R T.Forth in space: interfacing SSBUV: a scientific instrument, to the space shutte [J]. ACM Sigforth Newsleter,1993,4 (3): 1-8.   
[9]IntellaSys,A TPL Group Enterprise.SEAforth 40C18 Scalable Embedded Array Processor [EB/OL].(2oo8）.http://www.intellasys.net/templates/ trial/content/SEK_40C18_DataSheet_1.1.pdf.   
[10] Mikiten B C，Mikiten S,OrrJL.A Forth-basedreal-time in-flight monitoring system [C]//Proc of the 2nd & 3rd Annual Workshops on Forth. New York: ACM Press,1991: 31-34.   
[11]Forth Inc. SwiftX Cross Compilers for Embedded Systems Applications [EB/OL].(2016).https://www. forth.com/embedded/.   
[12] 杨为民，代红兵，安红萍，等．一种新的嵌入式Forth 实时操作系统的 研究[J].云南大学学报：自然科学版,2013(S2):96-103.   
[13] Paul Frenger. Forth and AI Revisited: BRAIN.FORTH[J].ACM SIGPLAN Notices,2004,39 (12): 11-16.   
[14] Stephen Pelc.Programming Forth [M].[S.1.] : MicroProcessor Engineering Limited,2011: 97.   
[15]代红兵，杨为民，王丽清，等．多目标Forth自生成器的研究与实现[J]. 计算机应用研究,2014,31(4):1109-114.   
[16] The Forth Interest Group.Forth Compilers Page [EB/OL].(2009）. http://www.forth. org/compilers. html.   
[17] Frederic PMiller. Colorforth [M].Alphascript [S.1.],2010: 28.   
[18] Frenger P.Hard Java [J].Acm Sigplan Notices,2008,43 (5): 5-9.   
[19] Hanna D M, Jones B,Lorenz L,et al.An embedded Forth core with floating point and branch prediction [Cl// Proc of IEEE Intermational Midwest Symposium on Circuits and Systems. 2013: 1055-1058.