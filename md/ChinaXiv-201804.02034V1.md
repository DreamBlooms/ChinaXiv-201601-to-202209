# 基于特征选择的虚拟化系统语义鸿沟桥接研究

娄睿1，蒋烈辉1,2

(1．信息工程大学 四院，郑州 450002;2.数学工程与先进计算国家重点实验室，郑州 450002)

摘要：虚拟化系统的强隔离性质在为安全机制部署提供可靠环境的同时，也引入了语义鸿沟问题。针对现有研究普遍依赖的软件体系结构信息、数据结构和控制流容易被窜改，采用的检测算法在客户机状态识别方面效率较低等问题，设计了特征构造和窗口标记的方法对虚拟机数据进行预处理，以满足实施数据挖掘的必要条件，建立了基于特征选择的虚拟化系统语义鸿沟桥接模型,能够仅依赖硬件体系结构数据构建虚拟机执行模式并进行安全检测。实验结果表明，所设计的系统模型能够筛选出关键的虚拟机特征，并有效地识别出客户机异常行为，提高语义鸿沟的桥接效率，为处理语义鸿沟问题提供了一种可行方案。

关键词：虚拟化安全；语义鸿沟；机器学习；特征构造；特征选择；异常检测 中图分类号：TP309 doi: 10.3969/j.issn.1001-3695.2017.12.0761

# Research on bridging semantic gap in virtualization system based on feature selection

Lou Rui1, Jiang Liehui1, 2 (1.Fourth Department，Information Engineering University Zhengzhou 45002，China;2. State Key Laboratoryof Mathematical Engineering & Advanced Computing, Zhengzhou 450o02, China)

Abstract:Thestrong isolationpropertyofthevirtualizationsysteintroduces thesemanticgapproblemwhile providingareliable environment for the deploying the security mechanism.Currnt research generally relies on the information of software architecturewhichisnotreliable,forthedatastructuresandcontrolfowsareeasytobeilegallymanipulated.Andthedetection algorithmemployedinrelatedresearchhas theloweficiency in identificationof guest state.Forthese problems,this paper designed thefeature construction and window mark to preprocess the captured data so as to meet the necessary conditions of carrying out data mining,and then established the semantic gap bridging modelof virtualization system basedon feature selection,whichcan build the execution modeof virtual machineand carryoutthe securitydetectiononlyrelyingon the hardware architecture data.Testresults show that proposed model can screen out the key features of virtual machine and effectivelyidentify theabnormal behaviorof guestsystem,which lead tothe eficiency improvementofbridgingsemantic gap. This scheme provides a feasible solution for dealing with the problem of semantic gap.

Key Words:virtualization security;semanticgap; machine learning; feature construction;feature selection;anomalydetection

# 0 引言

随着信息技术的发展计算系统日趋复杂并暴露出更多的攻击面，恶意程序在攻击方式上呈现多样化的同时也逐步向更高特权级渗透，给系统安全防护带了巨大挑战。虚拟化技术凭借其底层控制、域间隔离、域外监控的特性，在安全领域得到了广泛应用。虚拟化系统的强隔离性质在为安全部件提供可靠环境的同时，也导致虚拟机管理器(virtual machine monitor,VMM)视图和客户机视图之间存在语义鸿沟，使安全部件难以准确获取客户机内部状态，制约了安全机制的有效发挥。语义鸿沟问题已成为目前虚拟化安全研究的一个热点。

为了解决语义鸿沟问题，Garfinkel等人首次提出了虚拟机自省(VirtualMachine Introspection,VMI)的概念[1]。VMI是指在虚拟机外部，通常是从VMM或其他特权系统的有利角度监控、获取客户机原始数据，并借助特殊服务程序从中提取、还原客户机内部状态和事件的过程。Garfinkel等人设计了首个VMI原型系统Livewire，基于Linuxcrash分析工具建立了操作系统接□库，该接口库主要用于将VMM提供的虚拟机状态转换成操作系统级视图。InSight[2]主要依据内核源码与符号表获得VMM视图与客户机视图之间的映射关系进而还原出系统相应信息。KDD[3]对内核源码进行静态指向分析以消除指针关系的歧义性，从而构建出精确的内核数据定义，能够精确映射虚拟机物理内存并提取出运行时对象以桥接语义鸿沟。RTKDSM[4]专用于对客户机状态的实时监控和分析来处理语义鸿沟问题。ODinn[5]通过预先缓存重要信息，解析内核源码并扫描完整内存结构来还原目标系统状态。IVirt[通过地址转换和内容定位获得虚拟机所需的内存数据，进而验证客户应用程序的完整性以判断目标系统状态。VMST7通过自动识别和重定向自省数据到内核空间的方式重构高级操作视图。

虚拟化与机器学习结合是当前虚拟化研究的新方法，这类方法通常借助虚拟化提取客户机数据流，并采用数据挖掘、统计学、模式识别等方法建立目标系统的执行模式，在此基础上进行虚拟机性能评估、负载特征分析、虚拟机状态检测等。Anand等人在虚拟机网络入侵检测中采用了基因算法进行特征选择，并采用了模糊 SVM算法对审计数据进行分类[8]。Udaya等人采用了神经网络算法检测虚拟域中的网络包[9]。 $\mathrm { \Delta X u }$ 等人通过引入机器学习对虚拟内存访问模式进行监视和分类进行恶意程序检测[10]。Mishra等人对所收集的信息应用决策树进行行为学习并分类，进而检测恶意系统调用模式[1I]。

尽管上述方法在一定程度上修复了语义鸿沟，提升了操作系统安全性，但这些方法普遍依赖的软件体系结构信息存在数据结构和控制流容易被窜改的缺陷，同时所采用的检测算法在客户机状态识别方面效率较低。尽管硬件体系结构信息能够提供准确的系统状态，但现有方法并不能从中推导出必需的客户机状态，也无法有效识别出客户机中的恶意行为。

本文基于前期工作[12]进行拓展研究，作为一种基于虚拟化的防护系统，协作型虚拟化安全模型(cooperatingvirtualizationsecuritymodel,CVSM)具备良好的抗攻击性，但同时也在系统低级状态和系统行为之间引入了语义鸿沟，使VMM很难准确获取客户机内部状态。从CVSM的虚拟化层能够提取出丰富的硬件体系结构信息，基于这些信息可以构造出多样的虚拟机特征。本文针对CVSM进行适应性设计，使之满足进行数据挖掘的必要条件，建立了基于特征选择的语义鸿沟桥接模型，通过特征选择处理虚拟机数据，并以分类算法进行安全检测，用于提高客户机中异常行为的识别能力。

# 1 虚拟化层数据分析

根据硬件体系结构数据难以被窜改和旁绕的特性，以硬件体系结构层（或称虚拟化层）收集的信息作为数据源，在该层次能够访问和利用软件层无法观测到的接口，如段页保护、中断和异常处理、任务管理、cache 管理、虚拟机扩展等。在本文研究中，CVSM中使用的数据来源于以下几个方面： $\textcircled{1}$ 虚拟机状态，如CR3、IDTR、GDTR、LDTR、I/O 等； $\textcircled{2}$ 虚拟机扩展，如上下文切换陷入、特权指令陷入、VMCALL 指令陷入等； $\textcircled{3}$ 中断或异常，如页故障、通用保护异常等。

虚拟化系统中恶意行为高低级语义之间存在一定的对应关系[13]，表1列出了这种映射关系。借助高低级语义映射可以在更低层次提取与客户机安全相关的信息，并从中状态推导出客户机内部状态。

表1恶意行为的高低级语义映射  

<html><body><table><tr><td>高级语义</td><td>低级语义</td></tr><tr><td>中断钩子</td><td>IDTR 与系统调用MSR 操作，系统中断陷入，用户中断陷入，页故障异常，通用保护异常</td></tr><tr><td>进程隐藏</td><td>上下文切换陷入，CR3写操作</td></tr><tr><td>模块隐藏</td><td>用户中断陷入，页故障异常，通用保护异常</td></tr><tr><td>网络活动隐藏</td><td>虚拟I/O 读写</td></tr><tr><td>虚拟机Rootkit</td><td>虚拟机进入陷入</td></tr><tr><td>网络攻击</td><td>虚拟I/O读写</td></tr><tr><td>恶意进程</td><td>虚拟I/O读写，用户中断陷入，页故障异常，通用保护异常，无效操作码异常，调试异常</td></tr></table></body></html>

CVSM适用于两种场景： $\textcircled{1}$ 用于入侵检测，对正常的工作负载提供安全防护； $\textcircled{2}$ 用于安全测试或蜜罐诱捕，收集、分析恶意程序的攻击行为。无论是入侵检测还是安全测试CVSM都需要在虚拟化层收集大量数据，为达到数据收集目的系统会设置并产生频繁的虚拟机退出操作，每个数据集都可能包含上千个原始数据，这些数据通常具有高维、类不平衡、类基本平衡三个特点，不仅增加了计算时间也降低了检测精度，因此在实验过程中并不适合对这些数据进行直接处理。

# 2 CVSM中的语义鸿沟桥接

# 2.1语义鸿沟桥接模型

从虚拟化层收集的数据具有高维、冗余、包含噪声等特点，并不直接适用于学习算法。对原始数据进行预处理、为机器学习过程提供准确而简洁的高质量数据，是提高学习算法效率的重要环节。典型的机器学习过程如图1所示，其中学习环节包含在数据训练阶段。

![](images/e22e65e67f278f1aa40e3f4a0584b8de900ad29895f44333795bbbbb24c0608b.jpg)  
图1机器学习过程

由图1可知，学习算法通常并不直接对原始数据进行处理，为此需要对CVSM进行适应性设计，对所收集的数据进行预处理以实施特征选择，进而筛选出符合学习算法的有效输入。数据输入到学习算法之前的必要处理包括：

a）数据收集。CVSM必须能够持续收集数据，使学习算法能够从中提取充足的特征并建立虚拟机执行模式。所收集的数据中应该包含正常数据和异常数据，便于对学习算法进行训练和测试。

b）数据描述。CVSM应该对所收集的数据进行描述，将数据转换成可以度量与比较的数值（或特征）有助于学习算法识别离群点。数据包括属性描述（二元属性、数值属性等）和统计描述（距离、方差等)。

c）数据标记。CVSM应该具备数据标记能力，采用带标记的正常数据和异常数据对学习算法（监督式学习）进行训练。由于CVSM中存在语义鸿沟，实现数据标记并不容易。

d)在线和离线数据处理。学习算法训练阶段VMM往往需要统计某个时间段内的数据量与分布，要求CVSM提供离线缓存功能。检测阶段则要求CVSM能够及时处理数据，提高其响应能力并减少空间存储。因此CVSM应该同时具备在线和离线数据处理功能。

当前的入侵检测技术主要有误用检测和异常检测，CVSM的一个重要设计目标是能够对未知系统状态进行判断，因此本文采用了异常检测方法，构建了基于特征选择的CVSM语义鸿沟桥接模型（如图2所示)，包括客户机数据收集、客户机数据筛选、客户机状态检测三个阶段。

![](images/eab6a77f6cc3df10261549e9bfd768442abef12f263bb83b98421f306285f3a3.jpg)  
图2基于特征选择的语义鸿沟桥接模型

# 2.2数据处理流程

根据数据处理部件的位置差异，可以将机器学习在CVSM中的应用模型分为前端和后端，如图3所示。

![](images/927128425805d59623e5588cfce70e4e66adfd4bc34c26cdd1dd143aa2a55740.jpg)  
图3机器学习模型组成及数据流程

前端在VMM中，包括事件提取和特征构造两个部分：a)事件提取，VMM捕获硬件体系结构层产生的原始数据，如磁盘和网络I/O操作、页故障、TLB刷新等；b)特征构造,借助统计学方法将原始数据转换成相应的特征，用于后续的机器学习。后端在SPM中，包括特征选择、正常模式建立和异常检测三个部分：a)特征选择,从全部特征集合中筛选出少数高质量特征，降低时间复杂度并提高学习算法效率；b)正常模式建立：构造出虚拟机负载正常的执行模式；c)异常检测,识别偏离正常执行模式的异常行为。

由图3可知，机器学习在CVSM上的数据流程包括训练阶段和测试阶段。

a)训练阶段。首先运行正常负载，在前端收集事件并构造出尽可能多的特征，然后将这些特征递交到后端进行处理，在筛选特征的基础上建立正常执行模式，之后同时运行包含正常和异常行为的负载，评估这些行为与正常行为的偏离程度并作为分类预测的依据。

b)测试阶段。在前端运行任意类型的负载并收集事件，然后仅构造经过筛选的高质量特征，后端的异常检测单元将特征与训练阶段建立的正常执行模式对比，确定事件中是否包含异常行为。

# 3 虚拟机特征构造

# 3.1事件提取

CVSM中事件是指从硬件体系结构层提取的原始数据和信息。VMM对涉及体系结构的事件进行捕获并重新解释以确保多个虚拟机的正常运行，是虚拟化中基本的"限权"原则。典型事件包括执行特权指令，访问共享资源（内存、外设等)。事件所含信息的丰富程度与CVSM的性能密切相关，为了能够更准确地还原出客户机内部状态，必须广泛收集各种类型的事件。事件主要包括两类：

a）虚拟机事件。与虚拟机中客户机相关的体系结构或系统级事件，如客户机修改控制寄存器、刷新TLB、写磁盘等。

b)VMM事件。从VMM提取的与其自身状态相关的事件。客户机的状态以及客户机与VMM之间的交互也会影响到VMM状态，例如客户机执行特权指令时会从虚拟机地址空间陷入VMM地址空间。

除了监控事件的产生外还需要提取出与之相关的信息，例如对于磁盘I/O事件需要给出目标扇区、字节大小和读写类型等具体内容。表2、3分别列出了所提取的虚拟机事件和VMM事件，所提取事件应该有助于预测客户机状态改变，因此同时给出了与这些事件相对应的客户机高级语义。

# 3.2事件流分割

TCP协议中采用了窗口机制进行流量控制，本文也采用了窗口概念对事件流进行分割，以提高后端学习算法的数据处理效率。基本方法为：首先将事件流分成等时间的连续片段，之后借助统计学方法将片段中的事件转换成特征值，最后将窗口（包含一个片段中所有的特征值）发送到后端分析。窗口如图4所示。

表2虚拟机事件以及客户机中可能的高级语义  

<html><body><table><tr><td>虚拟机事件</td><td>事件内容</td><td>高级语义</td></tr><tr><td>磁盘I/O</td><td>磁盘扇区，字节大小，读或写</td><td>磁盘读/写事件</td></tr><tr><td>网络IO</td><td>字节大小，发送或接收</td><td>网络发送/接收事件</td></tr><tr><td>读/写CR</td><td>寄存器号，数值，读或写</td><td>与具体寄存器相关，例如写CR3可能为进程切换</td></tr><tr><td>页故障</td><td>错误号，EIP数值</td><td>违反写保护或启动新进程</td></tr><tr><td>TLB刷新</td><td>全局标记，新CR3</td><td>上下文切换</td></tr><tr><td>页无效</td><td>页无效的线性地址</td><td>程序试图越界访问</td></tr><tr><td>加载段描述符</td><td>段寄存器，基地址等</td><td>程序启动</td></tr><tr><td>当前特权级</td><td>特权级</td><td>当前运行用户或内核代码</td></tr><tr><td>LDT，GDT，TSS 访问</td><td>CR2中的故障地址</td><td>程序启动或上下文切换</td></tr><tr><td>模式指定寄存器</td><td>寄存器，数值，读或写</td><td>内核设定CPU工作环境，标志CPU工作状态</td></tr><tr><td>快速系统调用</td><td>SYSENTER_CS_MSR</td><td>用户到内核的快速调用</td></tr></table></body></html>

表3VMM事件以及客户机中可能的高级语义  

<html><body><table><tr><td>VMM事件</td><td>事件内容</td><td>高级语义</td></tr><tr><td>设置或退出虚拟化模式</td><td></td><td>进入或退出支持客户机运行的模式</td></tr><tr><td>启动虚拟机</td><td>虚拟机控制结构地址</td><td>客户机开始或重新运行</td></tr><tr><td>读写虚拟机控制结构</td><td></td><td>虚拟机控制结构中相应的子结构地址获取客户机当前状态，设置或修改客户机的执行模式</td></tr><tr><td>虚拟机调用</td><td></td><td>客户机预知运行于虚拟机并向VMM发出退出请求</td></tr><tr><td>设置虚拟机退出处理程序</td><td>退出程序入口及内容</td><td>客户机对真实机的操作能力被限制、改变</td></tr></table></body></html>

![](images/b5f992cf0d0a26fe955dd050124eaef77df79932f96a13bb7ae5d0b2ca4548d4.jpg)  
图4基于时间的窗口

采用基于时间的窗口有两个优势： $\textcircled{1}$ 每个窗口代表了相等的执行时间，方便窗口之间进行比较； $\textcircled{2}$ 能够以窗口为单位进行属性判断(正常或异常)。窗口长度也会对系统性能造成影响：较长的窗口可以捕获更多行为，较短的窗口则可以缩短检测时间。实验发现窗口长度在2\~4s时可以取得较好的平衡，相应的窗口不仅包含了丰富的信息能够完成分类，也能在较短时间内识别出异常行为。

# 3.3 特征设计空间

CVSM中前端向后端提供的特征包括原始特征和处理特征。原始特征包含所有从事件中提取的未处理信息。原始特征之间可能非常相近而呈现冗余，例如CR3修改通常伴随TLB刷新操作，原始特征中可能只有部分信息与系统状态改变相关，如果采用原始特征作为输入，学习算法必须处理上述问题；处理特征是对事件进行过滤、聚合或变换得到的特征，并不包含从事件中提取的所有信息而是信息的组合模式。本文采用了处理特征作为学习算法的输入。

原始事件能够用于特征构造的特征维包含多个方面：a)事件类型,基于单一事件构造的特征可以从特定角度表达系统行为，基于多个事件构造的特征则能够从不同角度表达系统行为；b)事件信息,既可以根据事件是否发生构造特征(如产生CR3写操作)，也可以根据事件所附带的信息构造特征（如CR3写操作的具体数值)；c)时间,包括客户机所感知的虚拟时间和VMM所感知的真实时间，可以在有限时间内构造出包含特征的窗口，基于时间信息可以生成一系列连续的窗口，时间也可以用于统计截止到某个时间点的事件累积状态；d)事件语义,不同抽象级所代表的语义能够从不同角度表达系统行为，因此也可以从语义角度构造特征。虚拟机特征反映了客户机行为，可以构造出基于系统和进程的特征；VMM特征既可以反映VMM行为，也能间接反映客户机行为。

根据上述几种特征维，本文采用了统计学方法将事件转换成特征选择算法易于处理的特征向量，构造了两类虚拟机特征：速率特征和关系特征。

# 3.3.1速率特征构造

速率特征描述了一个窗口内特定事件的产生频率，通过存储该窗口长度内的事件流并统计其中每类事件发生的次数实现，图5表示了从事件流中构造出速率特征的实例。所构造的速率特征包括页故障、控制寄存器修改、磁盘和网络的I/O操作等，这些特征为预测系统行为提供了丰富信息。

表4列出了所构造的部分速率特征，其中以RATE-VM开头的表示虚拟机事件，以RATE-VMM开头的表示VMM事件。

![](images/e299172f470cb4667985683df6152f438bcc6296d5b814d43ef6a4effe1908a6.jpg)  
图5速率特征构造

表4部分速率特征实例  

<html><body><table><tr><td>特征名称</td><td rowspan="3"></td></tr><tr><td>RATE-VM-PAGE-FAULT-P-0</td></tr><tr><td>RATE-VM-TLB-FLUSH</td></tr><tr><td>RATE-VM-GDT-WRITE</td><td rowspan="3"></td></tr><tr><td>RATE-VM-TSS-WRITE</td></tr><tr><td>RATE-VM-CPL-SET</td></tr><tr><td>RATE-VM-CR0-WRITE</td><td rowspan="3"></td></tr><tr><td>RATE-VM-CR3-WRITE</td></tr><tr><td></td></tr><tr><td>RATE-VM-TRAP-RATE</td><td rowspan="3"></td></tr><tr><td>RATE-VM-PAGE-FAULT</td></tr><tr><td>RATE-VMM-SET-GUEST-EXIT-HANDLER RATE-VMM-RESUME-VM-EXECUTION</td></tr></table></body></html>

# 3.3.2关系特征构造

不同窗口中某些事件可能具有相同的速率但产生次序不同，由于速率特征只能反映单个特征的发生频率，并不能反映事件之间的关系，因此速率特征认为这些窗口相同。为解决上述问题，可以将事件的产生和事件的统计值相结合构造关系特征，图6表示了这类特征的构造方法，X轴表示事件A、B的产生次序，Y轴表示A、B产生次数的差异，如果事件A产生则Y值加1，如果事件B产生则Y值减1。

![](images/262b6b49f5f1c6378ec99fc0281766bb8855fea9916a5081a6393077f360d726.jpg)  
图6基于事件产生和统计值的关系特征

CVSM中所构造的关系特征包括以下数值：a)序列总数(total sequence),所有相同类型事件连续产生的总次数；b)最大差异(max discrepancy),事件A、B在Y轴方向上的最大差值；c)最大运行长度(maxrun length),相同事件连续产生次数的最大值；d)最小运行长度(min runlength),相同事件连续产生次数的最小值；e)平均运行长度(mean runlength),所有运行长度的平均值;f)曼-惠特尼U检验(Mann-WhitneyUtest),用于度量事件A、

B 交叉产生时的随机程度；g)曼-惠特尼U-P值(Mann-WhitneyU-Pvalue)：表示曼-惠特尼U值的规范化统计，目的是方便对特征值进行比较。

表5部分关系特征实例  

<html><body><table><tr><td>特征名称</td></tr><tr><td>REL-VM-GDT-WRITE-VS-CPL-SET-0[maxDiscrepancy]</td></tr><tr><td>REL-VM-DISKIO-READ-VS-DISKIO-WRITE[maxDiscrepancy]</td></tr><tr><td>REL-VM-DISKIO-READ-VS-NETWORKIO-</td></tr><tr><td>WRITE[Mann WhitneyU]</td></tr><tr><td>REL-VM-DISKIO-READ-VS-NETWORKIO-</td></tr><tr><td>WRITE[Mann WhitneyP]</td></tr><tr><td>REL-VMM-ENTER-VM-MODE-VS-EXIT-VM-</td></tr><tr><td>MODE[MannWhitneyP]</td></tr><tr><td>REL-VM-CR3-WRITE-VS-TSS-WRITE[meanRunValue]</td></tr><tr><td>REL-VM-TSS-WRITE-VS-TLB-FLUSH[maxDiscrepancy]</td></tr><tr><td>REL-VM-PAGE-FAULT-P-0-VS-PAGE-FAULT-P-1[MannWhitneyP]</td></tr><tr><td>REL-VM-PAGE-FAULT-ID-0-VS-PAGE-FAULT-ID-</td></tr><tr><td>1[maxDiscrepancy]</td></tr><tr><td></td></tr></table></body></html>

采用上述方法在CVSM中构造了关系特征，数据源包括：网络I/O，磁盘读写字节数，内存读写操作引发的页故障等。表5列出了所构造的部分关系特征实例，其中REL-VM开头的表示虚拟机事件之间的关系特征，REL-VMM-VM表示VMM和虚拟机事件之间的关系特征，REL-VMM表示VMM事件之间的关系特征。

# 4 窗口标记

测试负载生成的正常窗口与恶意程序生成的异常窗口构成了窗口样本，本文首先采用了Boosting类算法完成窗口样本的特征选择，再借助分类算法识别异常窗口。训练Boosting类算法时需要对样本进行标记，因此CVSM需要提供窗口标记机制，用带标记的窗口训练特征选择算法。

对窗口进行标记存在两方面困难： $\textcircled{1}$ 关于“恶意行为"并无准确定义； $\textcircled{2}$ 即使可以借助客户机内部的安全软件识别出恶意行为，但语义鸿沟导致VMM很难判断原始数据中是否包含恶意行为。为桥接语义鸿沟，需要在客户机的高级操作和虚拟机数据之间建立关联。需要说明的是，事件流以窗口为单位递交给后端的学习算法，即使建立了高低级语义关联，学习算法对事件的识别粒度也只能精确到窗口级别。对窗口进行标记的关键在于使VMM能够确定恶意行为活动周期，并将活动周期内所生成的窗口标记为异常窗口。

由于系统行为的高低级语义之间存在映射关系，VMM可以根据低级事件的活动规律预测出客户机高级行为状态，从而直接对窗口进行标记。由于正常负载在运行期间不会或极少创建新的进程，如果在某个时间段内进程数量显著增加，则这些进程很可能是恶意程序。VMM需要区分并跟踪恶意程序产生的事件，将包含这些事件的窗口标记为异常窗口。

![](images/6c719b76038d7c51d1e180f3d8f9f36dd46427700d34dd53541e091e9c36419a.jpg)  
图7正常负载运行中的进程增长

进程具有不同的页目录基地址，该地址可以通过CR3获取，因此VMM通过收集、识别CR3可以区分客户机中的进程。图7反映了负载Database、Web和EMail运行过程中VMM所观测到的进程增长情况，从中可以看出在负载的主要运行区间内进程创建的数量并无显著增加。为比较注入恶意程序后客户机中的进程增长数量，在负载运行期间启动了四个恶意程序，相应的进程增长情况如图8所示，从中可以看出正常负载和恶意程序交替运行过程中存在明显的进程增长现象，新创建的进程与恶意程序有关。

![](images/f0fd2671519175f279a6405c7b6a855f71eb1b5894616bfcd0283920872d1454.jpg)  
图8正常负载与恶意程序混合运行中的进程增长  
图9窗口标记示意图

基于以上观测和分析，VMM窗口标记的步骤如下： $\textcircled{1}$ VMM缓存两个窗口并统计其中的CR3数值，将CR3数量显著变化区间内的CR3定义为异常CR3并作记录； $\textcircled{2}$ 检测所缓存的窗口中是否包含异常CR3，如果包含则说明该窗口含有恶意进程所产生的事件，将该窗口标记为异常窗口； $\textcircled{3}$ 两个窗口长度内会产生大量的CR3 操作，从一次异常CR3产生直至切换到正常CR3之间的所有事件都由同一进程产生，因此包含这些事件的连续窗口都是异常窗口。窗口标记的示意图如图9所示，其中灰色部分表示异常CR3。

CR3 Write Seg Load H CR3 Write InvPage CR4 Read Net IO 事件流→异常窗口

# 5 测试与分析

本文测试的主要目的是评估CVSM从硬件体系结构事件

中推导和识别客户机状态的能力，测试应该体现： $\textcircled{1}$ 对反映系统状态的关键虚拟机特征的筛选； $\textcircled{2}$ 恶意行为的检测效果； $\textcircled{3}$ 性能开销。

# 5.1 测试集

CVSM的一个主要优势在于方便部署，向其他平台移植时只需要修改与体系结构相关的事件收集方式，无须对客户机操作系统进行修改，因此可以支持多种类型的虚拟机。典型的服务器应用通常包括一个主进程和一个后台进程，这类负载所产生的系统行为相对稳定，因此本文针对虚拟服务器平台进行了测试。为产生多种类型的负载（CPU密集型、磁盘I/O型、网络I/O型)，反映多样的系统行为，采用了不同类型的服务器和虚拟应用。用于产生正常负载的三种测试集如表6所示。

表6产生正常负载的测试集  

<html><body><table><tr><td>数据集</td><td>服务器</td><td>虚拟应用</td><td>负载</td></tr><tr><td>Database</td><td>数据库管 理系统</td><td>MySQL Server</td><td>在线交易处理基准 (TPC-C)</td></tr><tr><td rowspan="2">Web</td><td>网络服务</td><td>Apache HTTP</td><td>Apache 带宽基准(ab)</td></tr><tr><td>器</td><td>Server</td><td></td></tr><tr><td rowspan="2">EMail</td><td>邮件服务</td><td>Exchange</td><td>Exchange 负载模拟器</td></tr><tr><td>器</td><td>Server</td><td>(LoadSim)</td></tr></table></body></html>

同时为在服务器上生成异常负载，从Malfease、OpenMalware、VXheavens、VXShare等库中收集了已知和未知的恶意软件。根据行为差异将这些软件分为四类：Trojan、Infostealer、Downloader和Backdoor，可以产生修改数据、安装程序、泄露信息、拒绝服务等恶意行为。

# 5.2 虚拟机特征筛选

虚拟机特征选择的目的是从VMM层所收集的事件中提取出对识别异常行为有价值的特征。特征选择算法采用AdaBoost-CR[14]，该算法采用贡献率(ContributionRate,CR)作为权重来衡量每个特征的重要程度，通过对特征权重排序可以对虚拟机特征进行有效分析。

# 5.2.1特征关联度

关系特征反映了不同事件之间的交互，在增强学习算法输入的同时也产生了冗余特征，冗余特征之间强相关且不包含太多额外信息。图10(a)表示了冗余特征"RATE-VM-CR3-WRITE"和"RATE-VM-TSS-WRITE"之间的分布。但相关并不一定意味着缺乏信息，存在噪声的情况下同时选择相关的特征有助于完成更好的分类及噪声消除，图10(b)表示大致冗余特征RATE-VM-CR0-WRITE"和"RATE-VM-CR4-WRITE"之间的分布。

如果两个类的条件密度的协方差矩阵在第一主方向相同，但对类中心进行相同的移位，则这样的特征虽然相关但并不冗余，同时选择这些特征能够提供有利于分类的信息。图10(c)表示了类条件依赖特征“RATE-VM-TLB-FLUSH"和"RATE-VM-INVALIDATE-PAGE"之间的分布。尽管根据事件交互构造了关系特征，但并非所有事件交互都有意义，有可能产生噪声和无关特征。无关特征间具有相同的类条件概率密度函数，并不包含有价值的信息，实验表明与加载段描述符有关的事件之间产生的是无关特征，图10(d)表示了无关特征的分布。

![](images/7156df9781df6cbed32182a39a35e779492ca527b8c641be9d5e6e000eaca58a.jpg)  
图10虚拟机特征关联度与分布

# 5.2.2频繁特征

采用AdaBoost-CR算法进行虚拟机特征选择，可以为每一种负载选择出带CR权重的特征，表7(a)(b)(c)分别列出了Database、Web和EMail上选出的权重最高的5个虚拟机特征。可以看出， $\textcircled{1}$ 关系特征所占比重大于速率特征，三个测试负载中所有的速率特征比重小于 $20 \%$ ，而且关系特征中也包含了一部分速率特征所描述的信息，表明特征选择算法能够去除冗余特征。 $\textcircled{2}$ 不同负载上所选的特征具有相似性，三个测试负载中权重较高的特征分为五种类型：GDT特征、TLB刷新特征（包含CR3操作事件）、磁盘与网络I/O特征、页故障特征、VMM特征(包含模式切换和页故障)。

Databse负载上最好的特征为"REL-VM-PAGE-FAULT-P-0-VS-PAGE-FAULT-P-1[MannWhitneyP1]"，这是因为Database为磁盘密集型负载会产生大量的磁盘读写操作，数据在磁盘和内存之间频繁交换会导致大量的页故障事件。Web负载上最好的特征为"REL-VM-NETWORKIO-READ-VS-DISKIO-WRITE[MannWhitneyP1]”，是由网络I/O事件和磁盘I/O事件组成的关系特征，此类事件也与Web的负载类型一致。Email负载中最好的 特 征为“REL-VMM-VM-EXIT-VM-MODE-VS-PAGE-FAULT-US-0[MannWhitneyP1]"，该特征反映两种事件的关系：$\textcircled{1}$ 系统从虚拟机模式退出到VMM模式，由VMM对客户机敏感操作进行解释。 $\textcircled { 2 } \mathrm { V M M }$ 在解释客户机行为中产生了页故障。

表7负载上5个权重最高的特征  

<html><body><table><tr><td colspan="2">(a)Database负载</td></tr><tr><td>特征名称</td><td>CR权重</td></tr><tr><td>REL-VM-PAGE-FAULT-P-0-VS-PAGE-FAULT-P-1[MannWhitneyP1]</td><td>0.376832</td></tr><tr><td>REL-VM-NETWORKIO-READ -VS-DISKIO-WRITE [MannWhitneyP2]</td><td>0.120571</td></tr><tr><td>REL-VM-CR3-WRITE-VS-TSS-WRITE[meanRunLength]</td><td>0.111837</td></tr><tr><td>REL-VMM-VM-EXIT-VM-MODE-VS-PAGE-FAULT-US-0[MannWhitneyU1]</td><td>0.109041</td></tr><tr><td>REL-VM-GDT-WRITE-VS-CPL-SET-3[MannWhitneyU1]</td><td>0.099245</td></tr></table></body></html>

<html><body><table><tr><td colspan="2">(b)Web负载</td></tr><tr><td>特征名称</td><td>CR权重</td></tr><tr><td>REL-VM-NETWORKIO-READ-VS-DISKIO-WRITE [MannWhitneyP1]</td><td>0.456714</td></tr><tr><td>RATE-VM-DISKIO-READ</td><td>0.265052</td></tr><tr><td>REL-VM-CR3-WRITE-VS-CR4-WRITE[meanRunLength]</td><td>0.166301</td></tr><tr><td>REL-VM-CR3-WRITE-VS-CR0-WRITE[MannWhitneyP2]</td><td>0.105268</td></tr><tr><td>RATE-VM-PAGE-FAULT-WR-1</td><td>0.074971</td></tr></table></body></html>

<html><body><table><tr><td colspan="2">(c)EMail负载</td></tr><tr><td>特征名称</td><td>CR权重</td></tr><tr><td>REL-VMM-VM-EXIT-VM-MODE-VS-PAGE-FAULT-US-0[MannWhitneyP1]</td><td>0.334201</td></tr><tr><td>REL-VM-PAGE-FAULT-P-0-VS-PAGE-FAULT-P-1[MannWhitneyP1]</td><td>0.218797</td></tr><tr><td>RATE-VM-DISKIO-WRITE</td><td>0.144215</td></tr><tr><td>RATE-VM-NETIO-WRITE</td><td>0.112438</td></tr><tr><td>REL-VM-TSS-WRITE-VS-TLB-FLUSH[maxRunLength]</td><td>0.059907</td></tr></table></body></html>

对虚拟机的特征分析表明CVSM能够有效筛选出高质量特征，也说明并非所有的原始事件都能够产生有价值的特征，仅需要构造与高频度事件相应的特征，有利于提高CVSM检测

率和检测速度。

# 5.3 异常检测分析

在特征选择环节后需要采用分类算法，根据所选特征子集对CVSM产生的窗口数据进行分类。K-NN[15]是一种经典的懒惰学习算法，通过计算新数据与训练数据特征值之间的距离区分近邻点以实施分类；LOF[1是基于密度的离群点检测方法中的代表性算法，能为数据集中的每个点计算一个离群因子LOF值以衡量该点是否异常。考虑到K-NN和LOF两种分类算法在数据处理方式上具有显著差异，并且在主要指标方面具有较强的互补性，因此选择了K-NN和LOF 两种算法对所选特征子集进行分类。表8和表9分别给出了特征选择算法与K-NN、LOF算法组合时三种负载的检测率、误报率以及AUC结果。

表8特征选择算法和K-NN算法组合时的测试结果   

<html><body><table><tr><td colspan="4">Database</td><td colspan="4">Web</td><td colspan="2">Email</td></tr><tr><td>恶意程序</td><td>FP(%)</td><td>TP(%)</td><td>AUC(%)</td><td>FP(%)</td><td>TP(%)</td><td>AUC(%)</td><td>FP(%)</td><td>TP(%)</td><td>AUC(%)</td></tr><tr><td>Downloader</td><td>9.00</td><td>95.0</td><td>86.0</td><td>4.00</td><td>97.0</td><td>93.0</td><td>3.00</td><td>96.0</td><td>93.0</td></tr><tr><td>Infostealer</td><td>6.00</td><td>98.0</td><td>92.0</td><td>5.00</td><td>98.0</td><td>93.0</td><td>6.00</td><td>98.0</td><td>92.0</td></tr><tr><td>Trojan</td><td>8.00</td><td>93.0</td><td>85.0</td><td>2.00</td><td>98.0</td><td>96.0</td><td>4.00</td><td>92.0</td><td>88.0</td></tr><tr><td>Backdoor</td><td>4.00</td><td>94.0</td><td>90.0</td><td>2.00</td><td>96.0</td><td>94.0</td><td>2.00</td><td>98.0</td><td>96.0</td></tr><tr><td>平均值</td><td>7.00</td><td>95.0</td><td>88.0</td><td>3.00</td><td>97.0</td><td>94.0</td><td>4.00</td><td>96.0</td><td>92.0</td></tr></table></body></html>

表9特征选择算法和LOF算法组合时的测试结果  

<html><body><table><tr><td colspan="4">Database</td><td colspan="4">Web</td><td colspan="2">Email</td></tr><tr><td>恶意程序</td><td>FP(%)</td><td>TP(%)</td><td>AUC(%)</td><td>FP(%)</td><td>TP(%)</td><td>AUC(%)</td><td>FP(%)</td><td>TP(%)</td><td>AUC(%)</td></tr><tr><td>Downloader</td><td>8.00</td><td>93.0</td><td>85.0</td><td>6.0</td><td>96.0</td><td>90.0</td><td>6.00</td><td>90.0</td><td>84.0</td></tr><tr><td>Infostealer</td><td>5.00</td><td>96.0</td><td>91.0</td><td>5.0</td><td>97.0</td><td>93.0</td><td>4.00</td><td>91.0</td><td>87.0</td></tr><tr><td>Trojan</td><td>7.00</td><td>93.0</td><td>86.0</td><td>3.00</td><td>98.0</td><td>95.0</td><td>8.00</td><td>89.0</td><td>81.0</td></tr><tr><td>Backdoor</td><td>8.00</td><td>95.0</td><td>87.0</td><td>3.70</td><td>94.0</td><td>91.0</td><td>8.00</td><td>92.0</td><td>84.0</td></tr><tr><td>平均值</td><td>7.00</td><td>94.0</td><td>87.0</td><td>4.30</td><td>96.0</td><td>92.0</td><td>7.00</td><td>91.0</td><td>84.0</td></tr></table></body></html>

为直观展示CVSM异常检测效果，图11展示了特征选择算法和LOF组合时在Downloader上的检测结果，其中Y轴表示分类结果的可信度。可以看出当Downloader运行后，相对于正常窗口，异常窗口具有更高的分类可信度，进而表现出更好离群性。

![](images/9b39a4e6afb4edf75de8d92bbe38678f2881b18bd56338492f95036a89471816.jpg)  
图11Downloader上的LOF 结果分布  
图12窗口大小与样本LOF值分布

# 5.4性能分析

检测延迟是指从攻击发生到CVSM检测到异常之间的时间，从该角度出发对系统性能进行分析。通过对延迟时间进行测试不仅可以评估算法性能，还能评估CVSM的实时性。

窗口大小的设定会对检测延迟产生影响，较长的窗口可以捕获到更多系统行为，为学习算法提供更充分的分类信息，但同时也产生了较大的计算量增加了检测延迟。设置不同窗口大小时正常行为和异常行为的LOF数值分布如图12所示，其中时钟周期为10毫秒。

窗口大小 $scriptstyle - 2 0$ 个时钟周期0.5 异常窗口×0.45 正常窗口。0 攻击开始X  
J01 0.250.20.15 x×0.1 □ 。 。 Q。 。 .O. 。 0 × X0.05 O O.. \*X·0 二 × i0 5 10 15 20 25窗口样本窗口大小=200个时钟周期05 异常窗口 10. 攻击开始  
1OT 0.5 XX X XxO. Q 0O X0.1 X0.05 发 X X X00 50 100 150 200 250窗口样本窗口大小=2000个时钟周期05 异常窗 XO =0.4 Fo 攻击开始  
101 0.3 @0.250.2 XOXD0.150.10.05 uCD...O....舞00 500 1000 1500 2000 2500窗口样本

由图12可以看出，当设置较小的窗口 (20 个时钟周期)时所含样本较少，难以形成有效的密度统计，即使在注入恶意程序之前也有可能随机出现LOF值偏高的正常样本，这些点可能会被误判为异常，导致整个窗口被误分为异常窗口；当设置较大的窗口（2000个时钟周期）时包含样本较多，样本间的相对密度较大，正常样本和异常样本的LOF值都偏高而难以识别出其中的异常点，容易导致整个窗口被误分为正常窗口。测试表明当设置窗口大小为200个时钟周期（2s）时可以取得较好的分类效果，该时间段内可以向后端提供充足的分类信息，也能够在数秒钟的延迟内检测出异常行为。

在确定窗口大小后测试了CVMS 的检测延迟，以Database负载为例的结果如图13所示，X轴表示从注入恶意程序到生成警报之间的时间延迟，Y轴表示时间延迟内的检测率。

![](images/619347ed114adc6105f984480e04b4cf5274a27449ba0222e46c88f740942971.jpg)  
图13LOF 算法在Database 负载上的检测延迟

检测率和检测时间之间存在一定关系：a)较长的检测时间可以对多个窗口进行持续观测，积累较多的事件特征值，有利于提高检测率。但如果等完全确认某操作存在威胁时才生成警报，则该操作可能已经对系统造成破坏;b)如果检测时间过短而提前生成警报，则可能产生较多的误报现象。因此必须在保持适度检测率和误报率的前提下及时生成警报。

表10不同负载上的检测率与检测延迟  

<html><body><table><tr><td colspan="4">LOF</td><td colspan="3">KNN</td></tr><tr><td>负载</td><td>TP(%)</td><td>FP(%)</td><td>检测延迟</td><td>TP(%)</td><td>FP(%)</td><td>检测延迟</td></tr><tr><td>Database</td><td>98</td><td>6</td><td>11</td><td>98</td><td>6</td><td>9</td></tr><tr><td>Web</td><td>96</td><td>0</td><td>1</td><td>97</td><td>13</td><td>1</td></tr><tr><td>EMail</td><td>84</td><td>3</td><td>14</td><td>94</td><td>3</td><td>15</td></tr></table></body></html>

恶意程序注入到正常负载中后可能并不立即产生异常行为，则从注入到表现出异常之间存在潜伏期，这种情况会增加CVSM的实际检测延迟，因此考虑了多数（ $9 5 \%$ ）不含潜伏期恶意程序时的检测延迟。表10列出了不同负载上的检测率、误报率和对 $9 5 \%$ 样本的检测延迟。从结果中可以看出，LOF和K-NN 算法在Web负载上具有较高的检测率，同时也具有1个窗□的最短检测延迟（2s)，而两种算法在Email负载上的检测延迟最长（约30s)。总体上，CVSM可以在平均8.5秒的延迟内以较高的检测率和中等误报率识别出异常行为。

# 6 结束语

本文针对虚拟机语义鸿沟问题，根据硬件体系结构数据难以被窜改和旁绕的特性收集了VMM层捕获的数据，增强了数据源的可靠性。通过对CVSM的适应性设计，使之满足能够进行数据挖掘的必要条件，构造了速率特征和关系特征，为机器学习过程提供了准确而简洁的数据，建立了基于特征选择的语义鸿沟桥接模型。实验结果表明，CVSM仅利用VMM层收集的数据便能够完成异常检测，引入机器学习方法处理虚拟机数据能够有效减小虚拟机特征空间，建立起有效的虚拟机执行模式并识别出客户机的异常行为，提高了语义鸿沟桥接效率，为处理语义鸿沟问题提供了一种可行方案。

# 参考文献：

[1]Garfinkel T，Rosenblum M.A virtual machine introspection based architecture for intrusion detection [C]//Proc of the 1Oth Annual Network and Distributed System Security Symposium. California: CPlane Inc,2003: 191-206.   
[2]Schneider C,Pfoh J, Eckert C.A universal semantic bridge for virtual machine introspection [C]// Proc of the 7th International Conference on Information Systems Security. Berlin: Springer,2011: 370-373.   
[3]IbrahimA S,Hamlynharris J,Grundy J,et al. Supporting virtualization ware security solutions usingasystematic approach toovercome the semantic gap [C]// Proc of the 5th International Conference on Cloud Computing. Washington DC: IEEE Computer Society,2012: 836-843.   
[4]Hizver J, Chiueh TC.Real-time deep virtual machine introspection and its applications [C]//Proc of the 10th ACM SIGPLAN//SIGOPS International Conference on Virtual Execution Environments. New York: ACM Press, 2014: 3-14.   
[5]Harrison C.Odinn: an in-vivo hypervisor-based intrusion detection system for the cloud [J].IEEE Trans on Power Delivery,2014,12(1):354-363.   
[6] 林杰，刘川意，方滨兴.IVirt:基于虚拟机自省的运行环境完整性度量 机制[J].计算机学报,2015,38(1):191-203.   
[7]Fu Yangchun. Bridging the semantic gap in virtual machine introspection via binary code reuse [D].Dallas: The University of Texas,2016.   
[8]Kannan A, Maguire G Q, Sharma A,et al. Genetic algorithm based feature selection algorithm for effective intrusion detection in cloud networks [C]// Proc of the l2th International Conference on Data Mining Workshops. Washington DC: IEEE Computer Society,2012: 416-423.   
[9]Tupakula U,Varadharajan V,Dutta D. Intrusion detection techniques for virtual domains [C]// Proc of the 19th International Conference on High Performance Computing. Washington DC: IEEE Computer Society, 2013: 1-9.   
[10] Xu Zhixing,Ray S,Subramanyan P,et al. Malware detection using machine learning based analysis of virtual memory access patterns [C]// Proc of Design，Automation and Test in Europe Conference and Exhibition. Washington DC: IEEE Computer Society, 2017: 169-174.   
[11] Mishra P,Pilli E S,Varadharajan V,et al. Securing virtual machines from anomalies using program-behavior analysis in cloud environment[C]// Proc of the 18th International Conference on High Performance Computing and Communications.Washington DC:IEEE Computer Society,2016:991-998.   
[12]娄睿．虚拟多域环境的安全保护技术研究[D].郑州：信息工程大学, 2014.   
[13]More A,Tapaswi S.Virtual machine introspection: towards bridging the semantic gap [J].Journal of Cloud Computing,2014,3(1): 16-30.   
[14] Tsuchiya M,Fujiyoshi H.A method of feature selection using contribution ratio based on boosting[C]//Proc of the 19th International Conference on Pattern Recognition.Washington DC:IEEE Computer Society,2oo8:1-4.   
[15] Bijalwan V,Kumar V, Kumari P,et al. KNN based machine learning approach for text and document mining [J].International Journal of Database Theory and Application,2014,7(1):61-70.   
[16]Bhatt V,Dhakar M,Chaurasia BK.Filtered clustering based on local outlier factor in data mining [J].International Journal of Database Theory and Application,2016,9(5):275-282.