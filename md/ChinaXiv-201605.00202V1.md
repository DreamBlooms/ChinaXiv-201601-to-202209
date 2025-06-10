# 无缝坏块处理与流水编程的NAND型内存控制器设计与实现

闫梦婷1²安军社²(1．中国科学院 空间科学与应用研究中心,北京100190；2.中国科学院大学 北京100190)

摘要:为满足航天大容量存储系统对高速存储及数据完整的需求,实现了一个基于NAND 型内存的高性能控制器提出了一种实现于NAND型内存芯片内部的流水编程机制,以及一种可以保证数据无缝连接的坏块处理机制。介绍了存储控制器的各个模块设计，并分析了不同情况编程机制所需的时间计算方法建立仿真模型利用蒙特卡洛方法仿真并讨论了流水编程机制的性能优化效果。在实际硬件平台验证了流水编程机制和坏块处理机制,结果表明该大容量存储系统的存储速率可达100MB/s,读取数据与存入数据保持一致数据无乱序无丢失。

关键词:NAND型内存控制器;固态存储器;坏块处理机制;流水存储机制 中图分类号：TP333 文献标志码：A 文章编号:1001-2486(2015)01-053-06

# Design and implement of a NAND Flash controller with pipelining program and non-missing invalid block handle method

YAN Mengting'² ,AN Junshe² (1.Center for Space Science and Applied Research,Chinese Academy of Science,Beijing 10o190,China; 2.University of Chinese Academy Sciences,Beijing 1Oo190,China)

Abstract:Aimingatrequirementofhighspeedandcompleteofdatainspacestoragesystem,thedesignofahighperformanceNADFlash controlerisresntIcocudapipeliingprgamingisideofFashipndaonissngivaldocetodetoage implementationispresntecalulatioofoagtieinierentitatioisisusedesiulatioodulesepresetndtepactf pipeliningprgisadeCalractltrogad invalid block method.The operation frequency of storage system achieves to $1 0 0 \mathrm { M B / s }$ ,ensuring accuracy ,completeness and continuity of data.

Key Words:NAND Flash controller;solid storage recorder; invalid block method;pipelining program method

近年来随着航天领域对大容量存储器研制工作的不断发展，与非型闪速存储器（no-andflashNANDFlash)作为一种新兴的半导体存储介质以其高密度、大容量、高数据存储速率以及可多次擦除等特点得到了大量的使用逐步成为航天电子系统存储介质的主流选择[1-2]。文献[3]基于NANDFlash设计了一种高速海量存储模块，为提高存储带宽引入了并行技术，同时在时间和空间上对存储架构进行了优化；文献[4]设计了一种高速多通道并行存储架构，在文献[3]的基础上对闪存转换层算法进行了优化最大存储速度达到73MB/s。高速系统的设计[3-8]基本通过扩展位宽或使用多片Flash芯片进行流水线操作来提高存储系统的存储速率，但Flash芯片内部流水操作的设计尚未提出，并且存储速率会因系统的时钟频率的不同而改变。本设计利用了NANDFlash多片叠装结构、复用自主固化时间，实现了Flash芯片内流水编程机制的设计，最大存储速度达到100MB/s，并分析了编程时间的理论值对流水编程机制的性能优化程度进行了建模仿真分析了流水编程机制在不同时钟频率下对系统性能的影响。

由于其制造工艺和航天器的特殊使用环境等因素NANDFlash可能在任意地址存在坏块，并在使用过程中产生新的坏块[9-10],对坏块的处理是NANDFlash实际应用中必须要解决的问题。大量的Flash 使用实例[3-8]中已出现常见的坏块处理方法主要是在使用前建立坏块信息表，以此来检索有效块，屏蔽坏块。根据坏块信息表建立方式可以分为两类[3]：1)直接存储，即只存储有效块的地址剔除无效块地址;2)间接映射，即在块信息表空间相应的地址进行标记，以此来判断对应块的性质。根据坏块存储区域可以分为：控制器内部存储以及Flash页内存储，后者可以节约控制器资源但访问块信息表的时间过长，不适合于高速系统。另外，还有基于文件分配表(FileAllocationTableFAT)文件系统处理坏块方法软件操作却存在一定难度[9]。上述已实现的坏块处理方法能屏蔽已知坏块，但在新坏块产生后会丢弃整个坏块并未涉及对坏块内已存数据的恢复处理，一旦在编程操作中出现坏块就会丢失数据最坏情况是丢失一个块容量的数据。本文设计了一种数据无缝连接的坏块处理机制，在使用过程中产生新的坏块时能够使数据恢复，保证数据完整性。结合流水编程机制和坏块处理机制，本设计实现的大容量存储系统提高了整体性能，满足实际航天电子系统对高速存储、数据完整无丢失的要求[11-13]。

# 1NANDFlash控制器整体设计

本设计中的NANDFlash控制器内部分为初始化、擦除、编程、读取、标记以及主控制器六个模块。如图1所示，系统上电后自动进入初始化模块初始化模块的任务是读取所有的Flash块的坏块标记字节以及Spare区域的用户使用信息，生成形成完备的块信息表，后续存储系统的全部工作都将根据块信息表来执行。本设计为达到存储系统对高速率的要求必须减少读取块信息表所需的时钟周期，因此选择在控制器内部建立RAM区用来存放坏块信息表。对Flash的基本操作有编程、读取和擦除，三种操作各自为一个模块。另外标记模块就是根据擦除模块和编程模块提供的坏块地址对坏块进行标记，主控制器模块则控制协调所有子模块的工作。

编程和读取操作的基本单位为页，每次编程读取操作存储、读取一页容量的数据以及使用信息。编程操作模块中，为了提高存储系统的整体编程速率利用了流水操作的方法在片内实现了流水编程操作，并且嵌入了完备的坏块处理机制用于处理编程操作中产生坏块的数据丢失问题，编程模块将在下文详述。读取模块会在接收到读取指令后，按照顺序从Flash相应页地址中将数据读出发送给接收器件。Flash存储单元在执行数据写入之前需要进行擦除操作擦除模块完成

读出数据写入数据  
读取模块 读操作完成 写操作完成 流水编程读操作控制 写操作控制 模块块信息表 主控制器 坏块处初始化 坏块所在地址模块 初始化完成擦除控制初始化控制标记完成 擦除完成 擦除模块  
标记模块 坏块所在地址标记控制

以块为单位的擦除操作，擦除操作可能导致新的坏块产生此时需要启用标记模块对坏块进行标记。擦除操作实际上是将把整块Flash的全部字节单元恢复为“FF”，即把所有的位全部恢复为“1”。编程操作则是将字节单元中相应的位从“1"置为“0”以此将每个字节编程为相应的十六进制数[10]。而坏块的常见情况是无法将字节单元里的“1”值置为“0”或者无法将“0”的位恢复为“1”,对坏块进行编程操作将导致存入数据与实际编程成功的数据不一致，读出错误数据故而对Flash的使用要避免使用坏块。

# 2流水编程机制的设计

# 2.1 NANDFlash叠装芯片的结构特点

NANDFlash芯片内部架构为多片Flash晶片叠装本设计选用8片叠装式的Flash芯片，每单片Flash包含4096个块，1块(block)包含64页（page）1页包含2048字节数据区以及64字节Spare区其中每页的数据区用于存放数据Spare区则是提供给用户存放使用信息[11-12]。SamsungElectronics的型号为K9K8GO8U1A的Flash芯片的架构图如图2所示。8个单片Flash共用的信号有：指令锁存使能信号(CLE)、地址锁存使能信号(ALE)和一组8位的I/O接口。其他控制信号包括CE、RE、WE、R/B则是8片Flash各有一组。片选信号CE用于激活8片Flash晶片中的某一片使得共用信号与其连接，流水操作就是利用片选信号依次激活内部分立叠装的Flash晶片，将自主固化时间得以复用来提高存储系统的整体编程效率。

![](images/1aef07474b94260f29511717c8cc7e85ec12923faea9ac24ff3d78927959338d.jpg)  
图1控制器模块组成示意图Fig.1Modules of controller  
图2NANDFlash8片叠装内部示意图Fig.28 slides inside of NAND Flash

# 2.2 流水编程机制设计

根据Flash的编程操作时序，控制某一片Flash某一页进行编程时需要对Flash芯片的操作如下:1)发送起始指令和地址;2)加载2048字节数据和Spare区的若干字节使用信息;3)发送结束指令[9]。每一片Flash 芯片内部都有一个数据缓存区，可以用于缓存一页最大容量的数据控制器向Flash加载的数据实际上是暂存在数据缓存区里当接收到结束指令后，Flash进入自主固化阶段将数据缓存区的数据按顺序固化到当前物理地址指向的页空间中。在Flash芯片的自主固化时间内，控制器无须对该片FIash进行控制操作连接该片Flash的所有信号处于闲置状态。根据Flash广家提供的数据显示，Flash固化时间的典型值约为 $3 0 0 ~ \mu \mathrm { s }$ ,最大值为 $7 0 0 ~ \mu \mathrm { s } ^ { [ 9 ] }$ 。如果不采用流水编程机制，对Flash的所有页空间进行普通编程，写入每一页数据都需要等待Flash自主固化完成使得存储系统的整体编程效率低，无法实现高速存储的自的。因此本设计引入流水操作概念在多片叠装式NANDFlash芯片内实现了流水编程机制，大幅度地提高存储系统的整体编程速率[13]。

本设计对8片叠装的Flash芯片采取流水方式进行编程操作，每次对8片Flash的同一逻辑块地址的同一页进行编程操作，并将此称为一个流水级。 $\mathrm { C E 0 } \sim \mathrm { C E 7 }$ 为8片Flash对应的片选使能信号为了叙述简便将8片Flash单片分别定义为 $\mathrm { C E 0 } \sim \mathrm { C E 7 }$ 。每个流水级的控制器操作包括两部分。1)控制编程操作部分：依次对CE0到CE7发送起始指令并加载数据使得8片Flash芯片依次进入自主固化阶段。2)编程完成情况检测部分：编程操作完成之后需要对编程完成的状态进行检测，依次对CE0到CE7已完成编程操作的芯片发送检测指令，根据芯片返回状态判断是否产生新的坏块。如果检测某一片Flash时该片仍处于自主固化阶段，则需要等待其固化完成后再进行状态检测。流水编程工作顺序如图3所示。当 $\mathrm { C E 0 } \sim \mathrm { C E 7 }$ 全部检测到编程成功，则一个流水级的编程工作完成[14]。

![](images/e60492d9d996325243953d3b7eefef204add43d467a83edefd8bb740952181a5.jpg)  
图3流水编程工作顺序示意图 Fig.3Pipelining-programming method

# 2.3系统编程所用时间的计算方法

为了从理论上验证流水编程机制对存储系统性能的改善分析了不同情况下编程时间的计算方法建立了模型对此进行了仿真并且讨论了存储系统时钟频率的不同、自主固化时间的不稳定，对流水编程机制的性能影响。

设固化前发送指令和数据的时间为 $\mathbf { \Omega } _ { a }$ 固化后发送检查指令和状态返回时间为 $b$ 自主固化时间为 $X$ ,则第 $i$ 片Flash固化时间可以表示为 $X _ { i }$ 。

若不采用流水编程机制则8次页编程完成的时间 $T _ { \scriptscriptstyle 1 }$ 可以表示为：

$$
T _ { 1 } \ = \ 8 \times a \ + \ \sum _ { i = 0 } ^ { 7 } X _ { i } \ + \ 8 \times b
$$

其中 $\mathbf { \nabla } _ { \mathbf { \boldsymbol { X } } _ { } i }$ 表示第 $i$ 片Flash的固化时间 ${ \bf \nabla } , i = 0$ ：$1 \ , \cdots \ , 7 ; a \ b$ 分别表示固化前控制必需时间和固化后控制必需时间。

若采用流水编程机制，则8片Flash页编程完成的时间 $T _ { _ 2 }$ 可以表示为：

$$
T _ { 2 } = \left\{ \begin{array} { l l } { { 8 \times a + 8 \times b \ , \forall X _ { i } < Y _ { i } } } & { { } } \\ { { ( j + 1 ) \ \times a + X _ { j } + ( 8 - j ) \ \times b \ , \forall X _ { i } \geqslant Y _ { i } } } & { { } } \end{array} \right.
$$

其中 $, Y _ { i } = \left( { \mathit { \textsf { I } } } - i \right) \ \times a + \left( { \mathit { \ i } } + a \right) \ \times b , { \mathit { i } } = 0 \ , 1 \ \cdots \ 7 ;$ 令 $Z _ { j } = X _ { j } + \left( \ j + 1 \right) \ \times a \ , X _ { j }$ 为 $Z _ { j }$ 取得最大值时对应的 $X$ 值。

当 $X _ { i } < Y _ { i }$ 对于所有的 $X _ { i }$ 都成立时很明显看出 $T _ { _ 2 }$ 比 $T _ { _ 1 }$ 节省了所有的固化时间。当 $X _ { i } < Y _ { i }$ 不能全部 $X _ { i }$ 成立时 式(2)得出 $T _ { _ 2 }$ 的取值由 $X _ { j }$ 以及 $X _ { j }$ 处于流水级中的位置联合决定，为准确直观地表现流水编程机制的性能优化程度，根据上述理论分析建立了仿真模型，采用不同时钟频率以及不同自主固化时间进行了仿真测试，结果将在下文中进行讨论。

# 3无缝连接式坏块替代机制

# 3.1坏块产生对编程的影响

Flash在使用过程中会随机产生新的坏块，编程操作和擦除操作都会导致坏块产生[11-12]  其中擦除操作产生的坏块只需要对该坏块进行标记并及时更新块信息表将其屏蔽，但是编程操作产生的坏块涉及到数据的完整性以及数据读取的连续性需要提出一个处理机制来应对编程操作产生的坏块。固化完成后Flash接收状态读取指令，若状态显示为编程失败，表明当前页的数据没有正常写入称该页为编程失败页。编程失败页中的数据为无效数据，不能作为有效数据直接读取，加载到该页的数据将丢失。编程失败页所在的块为编程失败块即新出现的坏块若直接将编程失败块屏蔽不再使用将导致已正常编程页的数据全部丢失最坏情况会丢失整个块容量的数据将导致整个存储系统的数据丢失情况严重加剧。为了保证数据不丢失，本设计提出了一个无缝连接的坏块处理机制流水编程机制能够在高速编程过程中实现完备的坏块处理。

# 3.2 坏块处理机制的设计

在本设计中,如果8片Flash的页编程操作都成功，则称这一级流水编程成功;若有某一个Flash晶片的页编程操作失败则称该流水级编程失败，开始调用坏块替代机制。流水编程的替代机制具体流程如图4所示。

无缝连接坏块处理机制的具体设计涉及到数据备份和Flash编程操作地址。为了保证不丢失编程失败页中的数据需要进行数据备份在控制器内部例化出RAM空间分区后用于数据备份。当执行数据加载工作时，同时将数据写入到对应的RAM区里。发生页编程失败后，调用相应的RAM区里的数据再次写入到替代块的替代页中。只有在确保RAM区里的数据编程成功之后才能允许数据被覆盖。

Flash编程的地址指向即将执行编程操作的页单元，页地址在每次编程完成后加一指向下一页；当64页全部写满时提取新的块地址块地址需要检索初始化生成的块信息表得到。本设计提出逻辑块地址概念，对存有数据的物理块标记上逻辑块地址，作为有效块的顺序。发生页编程失败的坏块和该坏块的替代块拥有同一个逻辑块地址替代块的第一个编程的页地址为坏块中编程失败的页地址。使得坏块与替代块无缝连接后，相当于一个有效块在后续的数据读取工作中根据唯一的逻辑块地址可以顺序回放出存储的数据。

![](images/7955320bc5ebf6a1ec3e63e6cb21dfe246923e775752df3aee684cb9f9515769.jpg)  
图4流水编程替代机制流程图  
Fig.4Invalid block in pipelining programming method

# 3.3数据的读取顺序处理

数据的读取顺序将结合流水编程机制索引逻辑块地址得到。将每一页的数据看成一个包，设第 $n$ 包存放在第 $A$ 片第 $B ( \ b )$ 块的第 $C$ 页 $\mathbf { \delta } _ { , B }$ 表示物理块地址 ${ } , { b }$ 为逻辑块地址。第 $n$ 包数据的存放地址可表示为：

$$
n = { \left( \begin{array} { l } { A + 1 } \end{array} \right) } \ + 8 \times 6 4 \times { \left( \begin{array} { l } { B + 1 } \end{array} \right) } \ + 8 \times { \left( \begin{array} { l } { C + 1 } \end{array} \right) }
$$

如果不产生坏块，则 $B = b$ 物理块地址与逻辑块地址相同。一旦编程操作中产生了新的坏块检索出可用的块地址作为替代块对替代块标记当前使用的逻辑块地址。假设第 $n$ 包数据发生页编程失败则第 $n$ 包数据第一次编程存放的地址表达式为：

$$
n = { \left( \begin{array} { l } { A + 1 } \end{array} \right) } \ + 8 \times 6 4 \times { \left( \begin{array} { l } { B _ { i } + 1 } \end{array} \right) } \ + 8 \times { \left( \begin{array} { l } { C + 1 } \end{array} \right) }
$$

检测到该地址编程失败，调用替代块进行再次编程的地址表达式为：

$$
n = { \left( \ A + 1 \right) \ } + 8 \times 6 4 \times { \left( \ B _ { i + 1 } + 1 \right) \ } + 8 \times { \left( \ C + 1 \right) }
$$

其中 $B _ { i + 1 }$ 和 $B _ { i }$ 的逻辑块地址都为 $b _ { i }$ 。

如图5所示物理块地址 $B$ 之前都未发生页编程失败，直到物理块地址 $B$ 的CE3单片Flash的第 ${ \left( { \begin{array} { l } { n - 3 } \end{array} } \right) }$ /8页发生了页编程失败，于是将第 $n$ 包数据再次编程到替代块中，可见替代块的物理块地址为 $B + 1$ （假设该块为有效块）逻辑块地址仍为 $b$ 并且后续的编程操作将用替代块代替坏块继续进行，直到该逻辑块全部写满。图5中由$B$ 与 $B + 1$ 物理块组合而成的逻辑块 $b$ 无缝连接后实际上相当于一个正常块，根据逻辑块地址寻址读数，可以保证 $B$ 物理块中的已存数据不丢失也能保证流水编程操作顺序执行。

![](images/c577d40a3367bf09065bf446ce80fa052d3a8ee0f3ca5c5fb0df12aad66be7e8.jpg)  
图5坏块产生时存储顺序示意图

# 4测试结果与分析

# 4.1 时钟频率对流水编程机制性能的影响

选取 $4 \mathrm { M H z } \sim 6 4 \mathrm { M H z }$ 范围内的常用时钟频率并根据向Flash发送指令、地址以及加载数据所需周期计算出不同时钟频率下 ${ \textbf { \textit { a b } } }$ 的取值。

SamsungElectronics给出的NANDFlash芯片测试出的典型自主固化时间为 $3 0 0 \pm 1 0 0 ~ \mu \mathrm { s }$ ,超长自主固化时间最大值为 $7 0 0 ~ \mu \mathrm { s } ^ { [ 9 ] }$ 。首先讨论自主固化时间 $X _ { i }$ 不出现超长固化时间的情况下流水编程机制的编程速率。建立仿真模型并采用蒙特卡洛方法，该方法利用重复多次仿真数据的方差来代表被测对象的平均水平，令 $X _ { i }$ 在典型值$[ 2 0 0 ~ \mathsf { A 0 0 } ] ~ \mu \mathrm { s }$ 之间取随机值，多次测试结果如图6所示。从图中可以看出，在相同频率系统时钟下采用流水编程机制的系统比普通编程机制所需的编程时间明显减少；并且随着系统时钟频率的提高，普通编程机制所需时间趋于平衡但流水编程机制所需时间的性能仍有较大优化效果。

图6典型固化时间对比图  
![](images/b19031a930c995c2d7ffc1927cc44356504e09403ccd96dcb4a10ee9631344bb.jpg)  
Fig.6Typical storage time comparison

下面讨论编程中出现超长自主固化时间的情况。如图7所示在普通编程机制中出现超长自主固化时间将直接影响整体编程速率，系统所用的编程时间将随着出现超长固化时间的页编程个数线性增长。采用了流水编程机制后，根据式(2)和式(4），在一个流水级中，所用的编程时间与出现的超长固化时间的页编程个数无关，只与式(4)取得最大值的超长固化时间有关。得出结论在一个流水级中，当出现一个或多个超长固化时间，流水编程机制比普通编程机制所需编程时间明显减少。

![](images/fb3b5aeb35d693e3052df17a1125174d7c03dea427e6e2aaa85d9ef10c6b377e.jpg)  
Fig.5Storing order when invalid block occurs   
图7超长固化时间对比图Fig.7 Overtime storage time comparison

# 4.2坏块替代处理机制测试与仿真结果

本设计选用了Xilinx公司型号为Virtex5-$\mathrm { x c } 5 \mathrm { v l x } 8 5 \mathrm { F P G A }$ 硬件平台，将Flash控制器模块下载到可编程器件后所占用逻辑资源为 $7 . 5 \%$ [15]进行连接CPU、数据源和接收器等单元配合的板级测试利用数据源进行大容量数据存储测试遍历所有Flash存储单元、多次测试结果见表1：在频率为 $1 6 \mathrm { M H z }$ 的系统时钟下验证本设计的存储系统可以实现的平均存储速率可达 $1 0 0 \mathrm { M B / s }$ 以上。存取数据对比结果显示，本设计的大容量存储器能够检测出已知坏块并屏蔽已知坏块并在新坏块产生时调用坏块处理机制，保证无数据丢失实现数据的无缝连接。

表1平台测试统计数据Tab.1Data statistics in test bench  

<html><body><table><tr><td>遍历次数</td><td>坏块个数</td><td>平均存储速率(MB/s)</td></tr><tr><td>1~10</td><td>43</td><td>125</td></tr><tr><td>11~20</td><td>135</td><td>112</td></tr><tr><td>21~30</td><td>201</td><td>116</td></tr><tr><td>31~40</td><td>263</td><td>131</td></tr></table></body></html>

# 5结论

流水编程机制使得存储系统的整体编程速率大幅度提高,并且时钟频率越高性能优化程度越高；在出现较长固化的特殊情况时，仍然可以保证整体编程速度优于普通编程机制。提出了无缝连接式坏块处理机制，能够提供一个完备的方案实现突发坏块时对数据的无缝处理，改善了常用坏块处理机制无法恢复坏块数据的情况；并利用逻辑块地址索引进行读取操作，能够保证无丢失无乱序地存储读出数据，使得整个存储系统性能完好。

# 参考文献(References)

[1]王立峰 胡善清.基于闪存的高速海量存储模块设计[J]. 计算机工程 201137(7):255-257. WANG Lifeng,HU Shanqing.Design of high speed and large capacity storage module based on flash memory[J].Computer Engineering,2011,37(7) :255-257.(in Chinese)   
[2]彭军 黎福海.一种多通道并行固态存储系统的设计与实 现[J].计算机工程 201339(12):40-44. PENG Jun,LI Fuhai.Design and implementation of a multichannel parallel solid state storage system [J].Computer Engineering 2013,39(12):40-44.(in Chinese)   
[3]张胜勇高世杰．基于FPGA的NAND Flash坏块处理方法 [J].计算机工程 2010,36(6)：239-243. ZHANG Shengyong,GAO Shijie.Bad block handle method of NAND Flash memory based on FPGA [J].Computer Engineering,2010 ,36(6):239-243.(in Chinese)   
[4]贾源泉,肖侬.基于NANDFLASH的多路并行存储系统中 坏块策略的研究[J]．计算机研究与发展，2012 49(9)：68 -72. JIA Yuanquan,XIAO Nong.Research on bad block of the parallel storage system based on NAND FLASH[J] Journal of Computer Research and Development ,2012 49(9):68 -72. (in Chinese)   
[5] Samsung Electronics.512M $\times 8$ Bit/1G × 8 Bit NAND flash memory(Revision O.2) [R].2003.   
[6] Takeuchi K.Novel co-design of NAND flash memory and highspeed solid-state drives[J].VLSI circuit,2009,44(4):1224 -1227.   
[7] NAND Flash Applications Design Guide[EB/OL].（2004- 05-19)[2013-10 －21].http: $/ / \mathrm { { p d f } 1 }$ .alldatasheet.com/ datasheet-pdf/view/85039/SAMSUNG/K9W4G08U1M.html.   
[8] Shibata N,MaejimaH,IsobeK,et al. 70nm16Gb 16-evelcell NAND Flash memory [J].IEEE Journal of Solid-State Circuits 2008 43(4) :929 -937.   
[9]Takeuchi K. Novel co-design of NAND flash memory and highspeed solid-state drives [J].VLSI circuit,2009 ,44(4):1224 - 1227.   
[10]邢开宇 ,曹晓曼,方火能.基于FPGA 和 NANDFLASH的 存储器ECC 设计与实现[J]．电子科技,2012 25(10):69 -73. XING Kaiyu,CAO Xiaoman ,FANG Huoneng. ECC design based on FPGA and NAND flash memory [J].Electronic Science and Technology ,2012,25（10):69- 73.（in Chinese)   
[11]Virtex-5 FPGA configuration user guide.[EB/OL].（2012- 10-19)[2013－10－21].http://www.xilinx.com/ support/documentation/user_guides/ugl91.pdf.   
[12]潘立阳 ,朱钧.FLASH存储器技术与发展[J]．微电子学， 2002 32(1):1-6. PAN Liyang,ZHU Jun.FLASH memory technology and its development[J] Microelectronics,2002 32(1）:1-6.（in Chinese)   
[13]梁永刚 崔永俊 郁.基于NAND 型FLASH的双备份固 态存储系统[J]．科学技术与工程,2013,13(26):7676 -7681. LIANG Yonggang,CUI Yongjun ,HUAN Tao.Double backup solid-state storage system design based on the NAND-type flash[J].Science Technology and Engineering,2013, 13(26):7676 -7681(in Chinese)   
[14]Nguyen Q,Yuknis W,Pursley S,et al.A high performance command and data handling system for NASA's lunar reconnaissance orbiter[C]//Proceedings of AIAA Space 2008 Conference & Exposition ,Washington 2008.   
[15]Durna M,Urhan H,Turhan O,et al.A new generation onboard computer and solid state data recorder suitable for spacewire platforms [C]//Proceedings of 3rd International Conference on Recent Advances in Space Technologis RAST 2007.