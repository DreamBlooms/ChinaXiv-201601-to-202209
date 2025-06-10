# 关于信息本质和容量的研究

许建峰

（人民法院信息技术服务中心北京100745）(E-mail: xjfcetc@163.com)

文章中文版在ChinaXiv:202205.00179预印版正式发布并及时更新

# 摘要：

[目的]分析基于信息六元组模型的信息容量定义和性质，提出信息与物质、能量和时间的关系公式，为信息科学研究和应用提供理论参照。

[方法]基于关于信息的四项基本公设，提出信息的六元组模型，通过公理化方法，研究了多种组合条件下的信息容量效应；结合量子信息理论，推导了信息容量与质量、能量和时间的关系。

[结果]证明了利用信息熵定义信息容量仅仅是客观信息论所定义信息容量的一种特例，估算了单个量子载体所能承载的信息容量，推导给出信息与物质、能量和时间的关系公式，并以此计算和分析了迄今为止宇宙可能承载的信息容量。

[局限]相关理论方法需要在物理学实证研究和复杂信息系统科学应用中得到验证。

[结论]客观信息论的信息容量内涵能够较为深刻和准确地揭示客观世界物质、能量和信息三大组成要素之间的相互关系，具有很好的普适意义和应用前景。

关键词：信息模型信息容量信息组合量子信息信息与物质、能量和时间的关系公式、宇宙的信息容量

分类号：

# An Investigation of the Essence and Volume of Information

Jianfeng Xu

(Supreme People's Court Information Center of China,Bejing,100745,China) (E-mail: xjfcetc@163.com)

Abstract:

[Objective]This paper studies the relationship between information volume and mass,energy,and time, through analyses of definition and properties of information volume based on the information sextuple model, in order to provide a theoretical reference for research and applications of information science. [Methods] Based on 4 basic postulations with regard to information, we proposed the information sextuple model; through an axiomatic approach, we studied the information volume effect under a variety of combinatorial conditions； in accordance with quantum information theories,we derived the relationship

between information and matter, energy and, time through mathematical axiomatic methods.

[Results] We proved that the information capacity based on the information entropy is a special case of the definition of information volume in the Objective Information Theory. Furthermore, we estimated the information volume of a single quantum carrier,derived the relationship formula between information volume and mass,energy and,time.Based on this,we estimated and comparatively analyzed the information volume existed in the universe.

[Limitations] These theoretical results are in need of validation with empirical physical studies and applications of complex information systems science

[Conclusions] The connotation of information volume of the Objective Information Theory can profoundly and accurately,to a certain extent,reveal the relationship among the three basic elements of the objective world—that is,matter,energy and information, demonstrating a good universal significance and application prospect.

Keywords: Information model Information volume Information combination Quantum information Information volume in the universe

# 1 引言

尽管人类已经进入信息时代，但人们对信息的认识依然众说纷纭[1-14]，研究信息的本质和容量有助于澄清和统一人们对信息的认识，推动信息科学发展。[2]就是以信息熵作为信息量，奠定了现代信息论的基础。它假定离散事件的发生概率分别为已知的 $p _ { 1 } , p _ { 2 } , \ldots , p _ { n }$ 。由此得到信息熵公式 $H ( X ) =$ $\begin{array} { r } { H ( p _ { 1 } , p _ { 2 } , \cdots , p _ { n } ) = - k \sum _ { i = 1 } ^ { n } p _ { i } l o g p _ { i } } \end{array}$ ，同时强调其作为信息、选择和不确定性的度量，在信息论中扮演着核心角色。迄今为止绝大多数信息理论研究都将各种类型的信息熵作为计算信息量的基本公式，确实在信息科技发展中发挥了非常重要的作用。

但细致分析可知，信息熵作为信息度量的定义有很大局限性，难以适应日趋广泛的信息系统建设和应用需求。主要原因有：第一，正如其题目“通信中的数学理论”所示，其研究结论主要适用于通信过程的典型场景，而对于现代信息系统除通信之外，还包括信息的采集、处理、存储和作用等更多、更复杂的环节，所有这些环节难以全面适用通信过程的规律；第二，其假定离散事件的发生概率$p _ { 1 } , p _ { 2 } , \ldots , p _ { n }$ 均为已知，这在实际应用即使是通信过程中也只可能是很少的特定情形；第三，利用信息熵公式描述信息量隐含“只有变化才产生信息”的观念，但当今人们接触最为广泛的计算机、互联网和数据库中传输、存储和应用的各种文件信息，无论变化与否都是信息系统研发人员必须面对的客观存在，而信息熵公式几乎对此无能为力。所以立足于信息熵公式的信息度量不适应现代信息系统需要面对和解决的众多问题，由此更显现了学界对于信息缺乏普遍共识所引发的深层次问题。

有鉴于此，[15]提出了客观信息论的基本概念，建立了信息的定义和模型，分析了信息的基本性质，定义了信息的九类度量。[16]以空中交通管制系统为例检验了客观信息论的适用性和合理性。[17]引入可还原信息的条件，修改、扩充了信息的容量、延迟、广度、粒度、种类、时长、采样率、聚合度、遍及度、失真度、失配度等十一类度量，进一步分析了信息系统可能具有的十一类度量功效，构建了信息系统动力构型，形成了信息系统动力学的基本框架，为支持信息系统体系设计和集成提供了较为全面的指标牵引和模型支撑，并在中国智慧法院体系工程中得到应用和验证[18]。

本文立足于客观信息论的基本概念，运用简单实例形象说明了信息的具体内涵，提出了关于信息的二元主体、存在时间、状态表达和使能映射等四项基本公设，以此为据论证了信息六元组模型是定义信息的充分必要条件，证明了客观信息论定义的信息容量也能表达 Shannon 信息熵原理，利用信息熵定义信息容量仅仅是客观信息论所定义信息容量的一种特例。根据信息的组合和分解性质，说明了原子信息组合的容量可加性，进而基于Margolus-Levitin 定理证明了单个量子载体在一定时段所能承载的信息容量，根据 Einstein 质能转换公式证明了信息容量与质量、能量和时间的关系公式，并以此计算和分析了迄今为止宇宙可能承载的信息容量，表明此公式较为准确地揭示了信息、物质、能量和时间的相互关系，具有很好的普适性，进而也凸现了客观信息论的科学意义。

# 2 信息的模型和容量分析

对于信息的认识尽管千差万别，但当今计算机和互联网上采集、传输、处理、存储和应用的各种数据、文本、音频、视频和多媒体等文件都是最具典型和普遍意义的信息。[19]提出信息就是信息，不是物质也不是能量，这是将信息提升到与物质和能量相同层次的论断。[15]认为物质是本源的存在，能量是运动能力的存在，信息是客观世界和主观世界中事物及其运动状态的客观反映，物质、能量和信息是构成客观世界的三大要素。通过简单的实例分析，归纳一般规律成为简明公设，采用公理化方法研究信息的模型、定义和容量，进一步澄清信息及其容量的概念是合理、科学的研究方法。

# 2.1信息概念的简单实例

为便于理解信息概念并形成对信息模型的直观认识，可通过一个笔记本电脑中的企鹅图片文件加以说明。

图1展现了存放在一台笔记本电脑中企鹅的活动画面信息。其中的本体就是画面中蓝天白云之下的三只企鹅，或许还包括企鹅们可能不为人知的主观情感。假设画面拍摄于 $\mathbf { t } _ { 0 }$ 时刻，快门定时为 $1 \%$ 秒，则本体的状态发生时间就是[to，to $+ 0 . 0 1$ 秒]的时间区间。本体的状态集合就是图1左侧所示[to.to$+ 0 . 0 1$ 秒]时蓝天白云之下企鹅们憨态可掬的姿态。而右侧的笔记本电脑就是信息的载体。假设存储时间从 $\mathbf { t } _ { 1 }$ 至 $\mathbf { t } _ { 2 }$ 时刻，则在时间区间[ti， $\mathbf { t } _ { 2 } ]$ 内的任一时刻都可成为信息载体的反映时间，而此时存储在笔记本电脑中的图片格式文件，也就是一组二进制数码就是信息载体的反映集合。

由这个简单的实例可知，企鹅们的活动状态甚或是主观情感信息通过笔记本电脑得以定格存储在客观世界之中，其内容就是笔记本电脑中的二进制图片格式文件，服从客观的科技规律。这也是所有以现代信息系统为载体的信息都具有的不以人们主观意志为转移的普遍属性，因此我们将这种关于信息的认识论称为客观信息论。

![](images/86a523f7e323cfaaa394021e24ce8b1cd314e0601ad5bf71ce89f0e9ed6368a5.jpg)  
图1笔记本电脑中的企鹅活动信息模型示意图

另一方面，笔记本电脑通过对图片格式文件进行适当处理，就能在其显示屏幕上还原展现蓝天白云之下的三只企鹅形象，在数学上可以理解为对载体反映集合进行了逆映射处理，就还原了信息本体的状态集合。这样信息最为重要的还原性得以具体体现。假设这个图片格式文件在笔记本电脑中占用1M比特存储空间，则一般都公认其信息容量就是1M比特，既不用估算发生概率，也不用计算熵公式来求得其它的信息容量，并且不会因为人们已经熟悉这幅图片而改变1M比特的信息容量。

人们常常仅将笔记本电脑中的二进制图片格式文件视为信息，也就是仅将载体的反映集合视作信息，一般情况下不致引起严重问题，因为事实上对于载体中的“信息”人们心中已经隐含了对其本体的认识。但在严格科学意义上，仅将载体中的反映集合视作信息会大为限制我们对信息的透彻研究。就上述实例而言，若仅以笔记本电脑中的图片格式文件作为独立对象，就无法研究其真实性、延迟性和准确性等对于信息而言具有决定性意义的关键问题。所以，只有将本体和载体及它们的存在时间和状态纳入信息的完整模型一并研究，才能全面反映信息的各种特征，为破解信息科学技术发展中面临的很多深刻问题提供充分的理论工具。

# 2.2信息的模型和定义

基于信息与物质、能量并列的基本认识并结合上述实例，为尽可能达成关于信息的普遍共识，建立形式化的信息模型，首先提出关于信息概念的四项公设：

公设1（二元主体公设）信息有本体和载体两个主体，其中本体具有信息的本质内涵，载体呈现信息的客观形态。

信息与物质、能量的重要区别在于，物质能够独立存在，能量也能独立存在，而信息表象的背后总是存在另一个“影子”。所以，人们常问“这个信息是真还是假？”“这个信息的准确性如何？”其实都是将信息的“表象”与其背后的“影子”相比较，利用信息的根本意义也在于能够从其表面形态还原或运用背后的事实真相。这里特别强调“客观形态”，就是要求信息呈现的表面形态应该不以人们的主观意志为转移，这就要求载体必须是客观世界中的事物。在2.1的实例中，人们正是通过笔记本电脑这个客观载体欣赏到三只企鹅本体的生活状态。这是公设1的立论依据。

公设2（存在时间公设）信息的内涵和形态都有各自的存在时间。

与物质和能量一样，信息存在也有时间性，体现在无论是信息本体的本质内涵还是载体的客观形态，都既可以产生于某一时间，也能够消失于某一时间。同时本体和载体的存在时间对于整个信息都具有深刻意义。比如，信息的延迟就取决于本体和载体存在时间之间的相互关系。在2.1的实例中，对于时间区间[ti，t2]内的任一时刻t， $\mathbf { t } - ( \mathbf { t } _ { 0 } + 0 . 0 1 )$ 就是笔记本电脑中图片信息的延迟。信息延迟在灾害预报、军事情报、公文流转等信息的很多应用中几乎具有决定性影响。这是公设2的立论依据。

公设3（状态表达公设）信息的本体和载体都有各自的状态表达。

与物质和能量的另一个重要区别在于，物质内容的本质仍然是物质，能量内容的本质仍然是能量，而信息内容的本质则是事物的状态。同时由于信息主体的二元性，本体或载体的状态都不可偏废。在2.1的实例中，蓝天白云之下企鹅们憨态可掬的姿态是信息本体的状态，笔记本电脑中的二进制图片文件是信息载体的状态，分析信息的真实性和准确性就必须研究比对本体状态和载体状态之间的关系。这是公设3的立论依据。

公设4（使能映射公设）信息的本体状态使能映射到载体状态。使能映射的涵义是既要求在数学上能够建立本体状态向载体状态的满映射，也要求由于本体状态才使载体状态成为客观现实。

如果本体状态和载体状态相互之间没有任何联系，那也不会形成任何信息。只有当本体状态不仅在数学上建立了与载体状态之间的满映射关系，还在物理上形成了前者与后者之间的因果使能关系，才能成为信息。在 2.1的实例中，企鹅图片信息就是信息创建者们建立的企鹅本体状态到笔记本电脑图片文件的映射关系，并且正因为有企鹅的本体状态，才产生了载体中图片文件的客观现实。这是公设4的立论依据。

公设1一4运用公理化方法归纳了信息应有的要素和要素之间的关系，由此能够导出信息的六元组模型。

引理1满足公设1一4的充分必要条件是存在非空的信息本体集合 $o$ ，本体发生时间集合 $T _ { h }$ ，本体状态集合 $f ( o , T _ { h } )$ 以及客观载体集合 $c$ ，载体反映时间集合 $T _ { m }$ ，载体反映集合 $g ( c , T _ { m } )$ ，使 $f ( o , T _ { h } )$ 使能映射到 $g ( c , T _ { m } )$ ，记此映射为I，简记为 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ ，称之为信息的六元组模型。

证明：当满足公设1一4时，根据公设1存在非空的信息本体集合 $o$ 和客观载体集合 $c$ ，根据公设2存在非空的本体发生时间集合 $T _ { h }$ 和载体反映时间集合 $T _ { m }$ ，根据公设3存在既依赖于本体集合 $o$ 、也依赖于发生时间集合 $T _ { h }$ 的本体状态集合，记为 $f ( o , T _ { h } )$ ，同时存在既依赖于载体集合 $c$ 、也依赖于反映时间集合 $T _ { m }$ 的载体状态集合，记为 $g ( c , T _ { m } )$ ，根据公设 $4 f ( o , T _ { h } )$ 使能映射到 $g ( c , T _ { m } )$ ，当此映射记为I时，就得到六元组模型 $\mathrm { I } = \langle \mathrm { o , T _ { h } , f , c , T _ { m } , g } \rangle$ 。引理的必要性得证。

另一方面，若存在非空的信息本体集合 $o$ ，本体发生时间集合 $T _ { h }$ ，本体状态集合 $f ( o , T _ { h } )$ 以及客观载体集合 $c$ ，载体反映时间集合 $T _ { m }$ ，载体反映集合 $g ( c , T _ { m } )$ ，并且 $f ( o , T _ { h } )$ 使能映射到 $g ( c , T _ { m } )$ ，则六元组模型 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ 能够满足公设1—4，引理的充分性得证。

根据公设1一4和引理1，能够给出客观信息论对于信息的一般数学定义：

定义1（信息的数学定义）设 $o$ 表示客观世界集合， $s$ 表示主观世界集合， $T$ 为时间集合， $o$ 、 $s$ 和T中的元素可以根据论域的特定要求进行合适的具体划分。本体 $o \in 2 ^ { O \cup S }$ 、发生时间 $T _ { h } \in 2 ^ { T }$ 、 $\mathbf { \sigma } _ { o }$ 在 $T _ { h }$ 上的状态集合 $f ( o , T _ { h } )$ 、载体 $c \in 2 ^ { o }$ 、反映时间 $T _ { m } \in 2 ^ { T }$ 和 $c$ 在 $T _ { m }$ 上的反映集合 $g ( c , T _ { m } )$ 均为非空集，信息I便是 $f ( o , T _ { h } )$ 到 $g ( c , T _ { m } )$ 的使能映射，即： $I \colon f ( o , T _ { h } )  g ( c , T _ { m } )$ ，或 $I \big ( f ( o , T _ { h } ) \big ) = g ( c , T _ { m } )$ 。所有信息I的集合称为信息空间，记为 $\mathfrak { T }$ ，是客观世界的三大构成要素之一。

需要特别说明的是， $I$ 在数学上一定要严格满足 $f ( o , T _ { h } )$ 到 $g ( c , T _ { m } )$ 之间满映射的所有数学性质，但同时只有 $f ( o , T _ { h } )$ 自身激发或通过外部力量产生了客观世界中相应的 $g ( c , T _ { m } )$ ， $I$ 才能被称为信息。这是定义1引入所谓“使能映射”概念的根本原因。也就是即使在数学上存在 $f ( o , T _ { h } )$ 到 $g ( c , T _ { m } )$ 的满映射，但 $g ( c , T _ { m } )$ 的出现与 $f ( o , T _ { h } )$ 并无任何物理上的联系，则此种映射不能成为信息。简言之，满映射是信息的必要条件，但并不是充分条件。归根结底信息既是数学的，也是物理的[20]，这是信息的本质属性。

定义2（可还原信息）设信息 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ 还是 $f ( o , T _ { h } )$ 到 $g ( c , T _ { m } )$ 的单射，也就是对于任何（204 ${ \bf 0 } _ { \lambda } , { \bf 0 } _ { \mathtt { k } } \in \mathfrak { o } , \mathrm { T } _ { \mathtt { h } \lambda } , \mathrm { T } _ { \mathtt { h } \mathtt { k } } \in \mathrm { T } _ { \mathtt { h } } , \mathrm { f } _ { \lambda } , \mathrm { f } _ { \mathtt { k } } \in \mathtt { f } ,$ ，若 $\mathbf { f } _ { \lambda } ( \mathbf { o } _ { \lambda } , \mathsf { T } _ { \mathrm { h } \lambda } ) \neq \mathbf { f } _ { \mu } ( o _ { \mu } , T _ { h \mu } )$ ，必有 $I ( f _ { \lambda } ( o _ { \lambda } , T _ { h \lambda } ) ) \ne$ $I ( f _ { \mu } ( o _ { \mu } , T _ { h \mu } ) )$ ，此时 $I$ 就是可逆映射，即存在 $I$ 的逆映射 $I ^ { - 1 }$ ，使对任何一组 $c _ { \lambda } \in c , T _ { m \lambda } \in T _ { m } , g _ { \lambda } \in g$ ，都存在唯一一组 $o _ { \lambda } \in o , T _ { h \lambda } \in T _ { h } , f _ { \lambda } \in f$ ，使 $I ^ { - 1 } \big ( g _ { \lambda } ( c _ { \lambda } , T _ { m \lambda } ) \big ) = f _ { \lambda } ( o _ { \lambda } , T _ { h \lambda } )$ ，由此可得 $\begin{array} { r l } { { \cal { I } } ^ { - 1 } \big ( g ( c , T _ { m } ) \big ) } & { { } = } \end{array}$ $f ( o , T _ { h } )$ 。这时我们称信息 $I$ 可还原，也称 $f ( o , T _ { h } )$ 是信息I的还原态。

可见，根据 $g ( c , T _ { m } )$ 和 $I ^ { - 1 }$ 能够还原到 $o$ 在 $T _ { h }$ 上的状态 $f ( o , T _ { h } )$ ，这就是信息的还原性。现实世界中，人们通过信息寻找其还原态，正是信息最为重要的性质和意义所在。

# 2.3信息容量的定义和推论

丰富完善信息的度量体系，进而支持分析研究信息系统的功效，是客观信息论的初衷。而信息容量则是其中最受关注的一个度量。

定义3设 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ 为可还原信息，0表示客观世界集合，T表示时间集合， $g ( 0 \times \mathrm { T } )$ 是客观世界和时间域上包含 $g ( c , T _ { m } )$ 的状态集合， $( g ( 0 \times \mathrm { T } ) , 2 ^ { g ( 0 \times \mathrm { T } ) } , \sigma )$ 构成测度空间，则信息 $I$ 关于测度$\sigma$ 的容量 $\mathrm { v o l u m e } _ { \sigma } ( I )$ 就是 $g ( c , T _ { m } )$ 的测度 $\sigma ( g ( c , T _ { m } ) )$ ，即

$$
\begin{array} { r } { \mathrm { v o l u m e } _ { \sigma } ( I ) = \sigma ( g ( c , T _ { m } ) ) . } \end{array}
$$

为尽可能提高普适性，用测度表示信息的容量，包含有限元素条件下的求和形式和连续可积函数条件下的积分形式。同样，对于同一个对象集合，数学上可以根据关注点的不同而定义多种不同的测度，如Lebesgue 测度、Borel测度等[21]。所以，这里定义的信息容量并不唯一，而是可以依据不同的应用背景作出不同的定义。在信息系统中，信息的容量通常以比特为单位，是人们最易理解的信息度量。

推论1（随机事件信息的最小可还原容量）设事件X为从数集 $\mathbf { \boldsymbol { x } } _ { i }$ $( i = 1 , \ldots , n )$ ）中随机取值，取值$\mathbf { x } _ { i }$ 的概率为 $p _ { i }$ $( i = 1 , \ldots , n )$ ，不同取值之间相互独立且 $\begin{array} { r } { \sum _ { i = 1 } ^ { n } p _ { i } = 1 } \end{array}$ ，信息 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ 表示利用信道传送X取值的编码，此时称I是一个随机事件信息。其中，本体 $o$ 就是随机事件 $\mathtt { X }$ ，发生时间 $T _ { h }$ 就是事件X发生的时间，状态集合 $f ( o , T _ { h } )$ 就是事件X的取值 $\mathbf { \boldsymbol { x } } _ { i }$ ( $\mathbf { \Phi } _ { i } = 1 , \dots , n )$ ，载体 $c$ 就是传送X取值的信道，反映时间 $T _ { m }$ 就是信道 $c$ 传送X取值的时间，反映集合 $g ( c , T _ { m } )$ 就是信道 $c$ 传送X取值的具体编码。若测度 $\sigma$ 表示 $g ( c , T _ { m } )$ 的比特数，则 $I$ 为可还原信息的最小容量就是 ${ \begin{array} { r } { { \mathrm { v o l u m e } } _ { \sigma } ( I ) = - \sum _ { i = 1 } ^ { n } p _ { i } \log _ { 2 } p _ { i } { \mathrm { c } } } \end{array} }$ （204

证明：[2]设定通信的语义与工程问题无关。因此，为尽可能降低所需信道带宽，传送X取值的通信过程并不需要直接传送具体的数值 $\mathbf { x _ { i } }$ ，只需要使用不同的二进制编码表示X取值 $\mathbf { x _ { i } }$ 这一事件，传送相应的编码即可！ ${ \bf \Phi } ( { \bf i } = 1 , \dots , { \bf n } )$ 。也即只要选择 $\mathbf { g } ( \mathbf { c } , \mathrm { T _ { m } } )$ 的合适编码方式，就能降低所需信道带宽。

用反证法，若还存在 $g ( c , T _ { m } )$ 的某种编码方式，使 $\begin{array} { r } { H ^ { \prime } = \sigma ( g ( c , T _ { m } ) ) < - \sum _ { i = 1 } ^ { n } p _ { i } \log _ { 2 } p _ { i } = H } \end{array}$ ，并且仍然保持I为可还原信息（也就是信道能够完整传送信源信息)，其中 $H$ 就是事件X的信息熵。假设信道c的带宽为W,此时即有 $\mathrm { W / H ^ { \prime } } \ > \mathrm { W / H }$ ，即信道c能够以大于W/H的速率完整传送信源信息。这就矛盾于[2]定理9作出的信道传送速率W/H不可能被超越的结论。

所以不存在任何一种编码方式使得 $\sigma ( g ( c , T _ { m } ) ) < - \sum _ { i = 1 } ^ { n } p _ { i } \log _ { 2 } p _ { i }$ 的同时还能保持I为可还原信息。volume $\textstyle { \boldsymbol { \sigma } } ( I ) = - \sum _ { i = 1 } ^ { n } p _ { i } \log _ { 2 } { p _ { i } }$ 就是 $I$ 的最小可还原信息容量。

推论得证。

推论1表明（1）式定义的信息容量也能表达 Shannon信息熵原理，利用信息熵定义信息容量仅仅是（1）式的一种特例。因为（1）式定义的信息容量只要求 $I$ 是 $f ( o , T _ { h } )$ 到 $g ( c , T _ { m } )$ 上的一一满映射且$g ( c , T _ { m } )$ 是关于测度 $\sigma$ 的可测集，相比于信息熵具有更为宽泛的数学条件限制，因而必定具有更加普适的应用场景。

根据定义1，我们还能够从数学上严格定义信息的延迟、广度、粒度、种类、时长、采样率、聚合度、遍及度、失真度、失配度等另外十类度量，并且也像推论1一样，分别由各类信息度量导出一些与经典信息原理相符或具有实用意义的重要数学推论（表1）［17]。

表1：信息度量体系的相关推论  

<html><body><table><tr><td>信息度量</td><td>经典及常用原理</td><td>基本推论</td></tr><tr><td>容量</td><td>Shannon信息熵</td><td>随机事件信息的最小可还原容量就是其信息熵。</td></tr><tr><td>延迟</td><td>串行信息传递延迟</td><td>串行信息传递的整体延迟等于各环节的延迟之和。</td></tr><tr><td>广度</td><td>雷达方程</td><td>雷达最大探测距离正比于信息广度之四次开方</td></tr><tr><td>粒度</td><td>光学成像的瑞利准则</td><td>光学成像信息的粒度正比于光波长，反比于感光单元的阔 度。</td></tr><tr><td>种类</td><td>可还原信息种类不变性原理</td><td>可还原信息能够保持信息的种类不变。</td></tr><tr><td>时长</td><td>连续监视信息平均时长</td><td>连续监视信息的平均时长等于信息采集设备的平均无故障 时间。</td></tr><tr><td>采样率</td><td>奈奎斯特采样定理</td><td>周期性信息的最低可还原采样率等于本体状态的最高频率 之半。</td></tr><tr><td>聚合度</td><td>可还原信息聚合度不变性原理</td><td>可还原信息能够保持信息的聚合度不变。</td></tr><tr><td>遍及度</td><td>梅特卡夫定律</td><td>网络系统的价值等于其承载信息的最大广度与最大遍及度 之积。</td></tr><tr><td>失真度</td><td>卡尔曼滤波原理</td><td>卡尔曼滤波是离散线性随机系统的最小失真度估计方法。</td></tr><tr><td>失配度</td><td>搜索算法平均查找长度</td><td>有限信息集合中最小失配度信息的平均查找长度就是搜索 算法平均查找长度。</td></tr></table></body></html>

# 3 信息组合和分解的容量效应

六元组模型 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ 的表达方式没有强调信息的集合属性。但稍加分析就能体现信息的集合属性，即 $I = \{ \langle o _ { \lambda } , T _ { h \lambda } , f _ { \lambda } , c _ { \lambda } , T _ { m \lambda } , g _ { \lambda } \rangle \}$ ，其中 $o _ { \lambda } \in o , T _ { h \lambda } \in T _ { h } , f _ { \lambda } ( o _ { \lambda } , T _ { h \lambda } ) \in f ( o , T _ { h } ) , c _ { \lambda } \in$ $c , T _ { m \lambda } \in T _ { m } , g _ { \lambda } ( c _ { \lambda } , T _ { m \lambda } ) \in g ( c , T _ { m } )$ ， $\lambda \in { \cal { A } }$ 为指标集。可见信息 $I$ 实际上也是由一系列六元组元素组成的集合。信息具有集合属性。若干集合能够通过“并运算”组合成更大集合，一个集合也能表达为若干集合之并而分解为更小的集合，集合的组合或分解决定了信息具有组合和分解的基本性质。无疑，信息的组合和分解将直接影响包括容量在内的相关信息度量。因而研究信息组合和分解的具体概念和形式，对于更加深刻地认识和运用信息的容量度量具有重要意义。

# 3.1信息组合和分解的数学定义

信息的组合和分解源于子信息的基本概念。

定义4对信息 $I ^ { \prime } = \langle o ^ { \prime } , T _ { h } ^ { \prime } , f ^ { \prime } , c ^ { \prime } , T _ { m } ^ { \prime } , g ^ { \prime } \rangle$ 和 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ ，若集合 $I ^ { \prime } \subseteq I$ ，并且 $I ^ { \prime } \big ( f ^ { \prime } ( o ^ { \prime } , T _ { h } ^ { \prime } ) \big ) =$ $I \big ( f ^ { \prime } ( o ^ { \prime } , T _ { h } ^ { \prime } ) \big )$ ，则称 $I ^ { \prime }$ 为 $I$ 的子信息，记为 $I ^ { \prime } \subseteq I$ ，称作 $I ^ { \prime }$ 包含于 $I$ 。同时在 $I ^ { \prime }$ 为I的真子集时，称 $I ^ { \prime }$ 为i的真子信息，记为 $I ^ { \prime } \subset I$ ，称 $[ I ^ { \prime }$ 真包含于I。

图2直观展现了信息 $I$ 与其子信息 $I ^ { \prime }$ 的相互关系。

![](images/83d7f48afcc744b843c261e3bd482cbbefc52b60841008de88c09ca6ecfefc2f.jpg)  
图2子信息概念示意图

[17]中信息度量的定义全部针对可还原信息。因此研究信息组合和分解的度量效应，信息可还原的条件十分重要。

推论2（子信息的可还原性）设信息 $I ^ { \prime } = \langle o ^ { \prime } , T _ { h } ^ { \prime } , f ^ { \prime } , c ^ { \prime } , T _ { m } ^ { \prime } , g ^ { \prime } \rangle$ 是信息 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ 的子信息，若I为可还原信息，则 $I ^ { \prime }$ 也是可还原信息。

证明：证明信息 $I ^ { \prime } = \langle o ^ { \prime } , T _ { h } ^ { \prime } , f ^ { \prime } , c ^ { \prime } , T _ { m } ^ { \prime } , g ^ { \prime } \rangle$ 可还原，只需证明 $I ^ { \prime }$ 是 $f ^ { \prime } ( o ^ { \prime } , T _ { h } ^ { \prime } )$ 到 $g ^ { \prime } ( c ^ { \prime } , T _ { m } ^ { \prime } )$ 一一映射即可。事实上，若 $I ^ { \prime }$ 非一一映射，则存在两组不同的 $o _ { 1 } ^ { \prime } , o _ { 2 } ^ { \prime } \in o ^ { \prime } , T _ { h 1 } ^ { \prime } , T _ { \mathrm { h } 2 } ^ { \prime } \in T _ { h } ^ { \prime } , f _ { 1 } ^ { \prime } , f _ { 2 } ^ { \prime } \in f ^ { \prime }$ 和一组 $c _ { 1 } ^ { \prime } \in$ $c ^ { \prime } , T _ { \mathrm { m 1 } } ^ { \prime } \in T _ { m } ^ { \prime } , g _ { 1 } ^ { \prime } \in g ^ { \prime }$ ，使得 $\begin{array} { r } { { \cal I } ^ { \prime } \big ( f _ { 1 } ^ { \prime } ( o _ { 1 } ^ { \prime } , T _ { h 1 } ^ { \prime } ) \big ) = { \cal I } ^ { \prime } \big ( f _ { 2 } ^ { \prime } ( o _ { 2 } ^ { \prime } , T _ { h 2 } ^ { \prime } ) \big ) = g _ { 1 } ^ { \prime } ( c _ { 1 } ^ { \prime } , T _ { \operatorname* { m 1 } } ^ { \prime } ) } \end{array}$ 。但根据子信息的定义，此时有1 $\left( f _ { 1 } ^ { \prime } ( o _ { 1 } ^ { \prime } , T _ { h 1 } ^ { \prime } ) \right) = I ^ { \prime } \bigl ( f _ { 1 } ^ { \prime } ( o _ { 1 } ^ { \prime } , T _ { h 1 } ^ { \prime } ) \bigr ) = g _ { 1 } ^ { \prime } ( c _ { 1 } ^ { \prime } , T _ { \mathrm { m 1 } } ^ { \prime } ) = I ^ { \prime } \bigl ( f _ { 2 } ^ { \prime } ( o _ { 2 } ^ { \prime } , T _ { h 2 } ^ { \prime } ) \bigr ) = I \bigl ( f _ { 2 } ^ { \prime } ( o _ { 2 } ^ { \prime } , T _ { h 2 } ^ { \prime } ) \bigr )$ 。这与 $I$ 可还原矛盾。所以， $I ^ { \prime }$ 必是可还原信息。

推论得证。根据子信息概念即可引入信息的组合和分解概念。

定义5（信息的组合和分解）对信息 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ 及其两个真子信息$I ^ { \prime } = \langle o ^ { \prime } , T _ { h } ^ { \prime } , f ^ { \prime } , c ^ { \prime } , T _ { m } ^ { \prime } , g ^ { \prime } \rangle$ 和 $I ^ { \prime \prime } = \langle o ^ { \prime \prime } , T _ { h } ^ { \prime \prime } , f ^ { \prime \prime } , c ^ { \prime \prime } , T _ { m } ^ { \prime \prime } , g ^ { \prime \prime } \rangle$ ，若集合 $I = I ^ { \prime } \cup I ^ { \prime \prime }$ ，且对任何 $o _ { \lambda } \in o , T _ { h \lambda } \in T _ { h }$ ，有 $I \big ( f ( o _ { \lambda } , T _ { h \lambda } ) \big ) = I ^ { \prime } \big ( f ^ { \prime } ( o _ { \lambda } , T _ { h \lambda } ) \big )$ 或 $I ^ { \prime \prime } \big ( f ^ { \prime \prime } ( o _ { \lambda } , T _ { h \lambda } ) \big )$ ,则称 $I$ 是 $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 的组合，也称 $[ I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 是I的分解，记为$I = I ^ { \prime } \cup I ^ { \prime \prime }$ 。

可见，组合和分解是一对互逆的关系。图3直观展现了信息 $I$ 与其两个分解子信息的相互关系。

![](images/e610573b6578b4953fbdbdc8e5a5f83e4d4984774069c87fb2addec9dd4f19e2.jpg)  
图3信息组合和分解概念示意图

当信息I为可还原信息时，根据推论2， $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 也都是可还原信息，此时信息的所有度量定义都适合I、 $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 三个信息，故此我们可以没有任何障碍地研究信息组合和分解的容量效应。

定义6（重叠信息）设 $I ^ { \prime } = \langle o ^ { \prime } , T _ { h } ^ { \prime } , f ^ { \prime } , c ^ { \prime } , T _ { m } ^ { \prime } , g ^ { \prime } \rangle$ 和 $I ^ { \prime \prime } = \langle o ^ { \prime \prime } , T _ { h } ^ { \prime \prime } , f ^ { \prime \prime } , c ^ { \prime \prime } , T _ { m } ^ { \prime \prime } , g ^ { \prime \prime } \rangle$ 是两个信息，若集合$I ^ { \prime } \cap I ^ { \prime \prime }$ 非空，且对任何 $o _ { \lambda } \in o , T _ { h \lambda } \in T _ { h }$ ，都有 $I ^ { \prime } \bigl ( f ^ { \prime } ( o _ { \lambda } , T _ { h \lambda } ) \bigr ) = I ^ { \prime \prime } \bigl ( f ^ { \prime \prime } ( o _ { \lambda } , T _ { h \lambda } ) \bigr )$ ，也即存在 $c _ { \lambda } \in c = c ^ { \prime } \cap$ $c ^ { \prime \prime } , T _ { m \lambda } \in T _ { m } = T _ { m } ^ { \prime } \cap T _ { m } ^ { \prime \prime }$ ，使得 $I ^ { \prime } \big ( f ^ { \prime } ( o _ { \lambda } , T _ { h \lambda } ) \big ) = g ^ { \prime } ( c _ { \lambda } , T _ { m \lambda } ) = g ^ { \prime \prime } ( c _ { \lambda } , T _ { m \lambda } ) = I ^ { \prime \prime } \big ( f ^ { \prime \prime } ( o _ { \lambda } , T _ { h \lambda } ) \big )$ ，定义$g ( c _ { \lambda } , T _ { m \lambda } ) = I \bigl ( f ( o _ { \lambda } , T _ { h \lambda } ) \bigr ) = I ^ { \prime } \bigl ( f ^ { \prime } ( o _ { \lambda } , T _ { h \lambda } ) \bigr ) = I ^ { \prime \prime } \bigl ( f ^ { \prime \prime } ( o _ { \lambda } , T _ { h \lambda } ) \bigr ) ,$ 则 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ 也是信息，且既是 $I ^ { \prime }$ 的子信息，也是 $I ^ { \prime \prime }$ 的子信息，称其为 $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 的重叠信息，记为 $I = I ^ { \prime } \cap I ^ { \prime \prime }$ 。特别地，若集合$I ^ { \prime } \cap I ^ { \prime \prime } = \emptyset$ ，则称信息 $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 无重叠信息。

图4直观展现了信息 $I$ 是两个信息 $\boldsymbol { I } ^ { ' }$ 和 $\boldsymbol { I } ^ { ' }$ 的重叠信息的概念。根据子信息的定义，由推论2可以得到下面关于重叠信息可还原性的推论。

![](images/0d09d5f60f87cfb0248aff4a9f59d79f2e68017b4dd3983cd8f55e6d28569237.jpg)  
图4重叠信息概念示意图

推论3（重叠信息的可还原性）设信息I'和I"均为可还原信息， $I = I ^ { \prime } \cap I ^ { \prime \prime }$ 是重叠信息，则I也为可还原信息。

# 3.2信息组合的容量可加性

定义7（信息的无重叠组合和分解）对信息I、 $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ ，若I是 $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 的组合，且 $I ^ { \prime } \cap I ^ { \prime \prime } = \emptyset$ ，则称I是 $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 的无重叠组合，也称 $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 是I的无重叠分解。此时还称 $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 互为 $I$ 关于对方的补信息，记为$I ^ { \prime } = I / I ^ { \prime \prime }$ 和 $I ^ { \prime \prime } = I / I ^ { \prime }$ 。

图5直观展现了信息的无重叠组合和分解概念。无叠重组合和分解是信息组合和分解的特例，但在研究容量效应时，针对无叠重组合和分解能够使问题大为简化，同时也并不影响从中发现子信息有重叠组合和分解时的相关规律。

![](images/d8b56269c85f649a5d7285030a2397e24258c37f7b74435390ce101894aaaf7d.jpg)  
图5无重叠信息概念示意图

推论4（无重叠组合信息的容量可加性）对于信息 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ ， $I ^ { \prime } = \langle o ^ { \prime } , T _ { h } ^ { \prime } , f ^ { \prime } , c ^ { \prime } , T _ { m } ^ { \prime } , g ^ { \prime } \rangle$ 和 $I ^ { \prime \prime } = \langle o ^ { \prime \prime } , T _ { h } ^ { \prime \prime } , f ^ { \prime \prime } , c ^ { \prime \prime } , T _ { m } ^ { \prime \prime } , g ^ { \prime \prime } \rangle$ ，若 $I$ 是 ${ \boldsymbol { I } } ^ { \prime }$ 和 $I ^ { \prime \prime }$ 的无重叠组合，且 $g ^ { \prime } ( c ^ { \prime } , T _ { m } ^ { \prime } )$ 和 $g ^ { \prime \prime } ( c ^ { \prime \prime } , T _ { m } ^ { \prime \prime } )$ 均为关于测度 $\sigma$ 的可测集，则 $g ( c , T _ { m } )$ 关于测度 $\sigma$ 也可测，且信息I关于测度 $\sigma$ 的容量等于信息 $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 关于测度 $\sigma$ 的容量之和，即

$$
\mathrm { v o l u m e } _ { \sigma } ( I ) = \mathrm { v o l u m e } _ { \sigma } ( I ^ { \prime } ) + \mathrm { v o l u m e } _ { \sigma } ( I ^ { \prime \prime } ) .
$$

证明：因为 $I = I ^ { \prime } \cup I ^ { \prime \prime }$ ，所以 $g ( c , T _ { m } ) = g ^ { \prime } ( c ^ { \prime } , T _ { m } ^ { \prime } ) \cup g ^ { \prime \prime } ( c ^ { \prime \prime } , T _ { m } ^ { \prime \prime } )$ ，并且根据测度的性质，由$g ^ { \prime } ( c ^ { \prime } , T _ { m } ^ { \prime } )$ 和 $g ^ { \prime \prime } ( c ^ { \prime \prime } , T _ { m } ^ { \prime \prime } )$ 均关于 $\sigma$ 可测可推得 $g ( c , T _ { m } )$ 关于 $\sigma$ 也可测[21]。

下面用反证法证明 $g ^ { \prime } \cap g ^ { \prime \prime } = \emptyset$ 。若不然，则存在 $c _ { \lambda } \in c ^ { \prime } \cap c ^ { \prime \prime } , T _ { m \lambda } \in T _ { m } ^ { \prime } \cap T _ { m } ^ { \prime \prime }$ ，使得 $g ( c _ { \lambda } , T _ { m \lambda } ) =$ $g ^ { \prime } ( c _ { \lambda } , T _ { m \lambda } ) = g ^ { \prime \prime } ( c _ { \lambda } , T _ { m \lambda } ) \in g ^ { \prime } \cap g ^ { \prime \prime }$ ，由于 $I$ 是可还原信息，必定存在唯一一组 $o _ { \lambda } \in o , T _ { h \lambda } \in T _ { h }$ ，使$I \big ( f ( o _ { \lambda } , T _ { h \lambda } ) \big ) = g ( c _ { \lambda } , T _ { m \lambda } )$ 。同样由于 $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 也是可还原信息，并且 $I$ 是 $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 的组合，所以$I \big ( f ( o _ { \lambda } , T _ { h \lambda } ) \big ) = I ^ { \prime } \big ( f ^ { \prime } ( o _ { \lambda } , T _ { h \lambda } ) \big ) = I ^ { \prime \prime } \big ( f ^ { \prime \prime } ( o _ { \lambda } , T _ { h \lambda } ) \big )$ ，可见 $o _ { \lambda } \in o = o ^ { \prime } \cap o ^ { \prime \prime }$ ， $T _ { h \lambda } \in T _ { h } = T _ { h } ^ { \prime } \cap T _ { h } ^ { \prime \prime }$ ，（20 $f ( o _ { \lambda } , T _ { h \lambda } ) \in f = f ^ { \prime } \cap f ^ { \prime \prime } , o ^ { \prime } \cap o ^ { \prime \prime } , T _ { h } ^ { \prime } \cap T _ { h } ^ { \prime \prime } , f ^ { \prime } \cap f ^ { \prime }$ 均非空集，矛盾于 $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 无重叠的假设。因此，根据测度的可加性， $\begin{array} { r } { \operatorname { v o l u m e } _ { \sigma } ( I ) = \sigma \big ( g ( c , T _ { m } ) \big ) = \sigma \big ( g ^ { \prime } ( c ^ { \prime } , T _ { m } ^ { \prime } ) \big ) + \sigma \big ( g ^ { \prime \prime } ( c ^ { \prime \prime } , T _ { m } ^ { \prime \prime } ) \big ) = \operatorname { v o l u m e } _ { \sigma } ( I ^ { \prime } ) + \sigma \big ( g ^ { \prime \prime } ( c ^ { \prime \prime } , T _ { m } ^ { \prime \prime } ) \big ) . } \end{array}$ $\mathrm { v o l u m e } _ { \sigma } ( I ^ { \prime \prime } )$ 。

推论得证。

（2）式表明信息的容量与集合的测度一样，都具有可加性。这既与人们的认知常识相符，也为深入研究信息组合和分解的容量效应提供了重要基础。由此利用集合和测度的性质，能够得到以下关于有重叠组合信息的容量构成推论。

推论5（有重叠组合信息的容量构成）对于信息 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle , I ^ { \prime } = \langle o ^ { \prime } , T _ { h } ^ { \prime } , f ^ { \prime } , c ^ { \prime } , T _ { m } ^ { \prime } , g ^ { \prime } \rangle$ 和$I ^ { \prime \prime } = \langle o ^ { \prime \prime } , T _ { h } ^ { \prime \prime } , f ^ { \prime \prime } , c ^ { \prime \prime } , T _ { m } ^ { \prime \prime } , g ^ { \prime \prime } \rangle$ ，若I是 $I ^ { \prime }$ 和 $I ^ { \prime \prime }$ 的组合，且 $g ^ { \prime } ( c ^ { \prime } , T _ { m } ^ { \prime } )$ 和 $g ^ { \prime \prime } ( c ^ { \prime \prime } , T _ { m } ^ { \prime \prime } )$ 均为关于测度 $\sigma$ 的可测集，则 $g ^ { \prime } ( c ^ { \prime } , T _ { m } ^ { \prime } ) \cap g ^ { \prime \prime } ( c ^ { \prime \prime } , T _ { m } ^ { \prime \prime } )$ 也是关于测度 $\sigma$ 的可测集，且

$$
\operatorname { v o l u m e } _ { \sigma } ( I ) = \operatorname { v o l u m e } _ { \sigma } ( I ^ { \prime } ) + \operatorname { v o l u m e } _ { \sigma } ( I ^ { \prime \prime } ) - \operatorname { v o l u m e } _ { \sigma } ( I ^ { \prime } \cap I ^ { \prime \prime } ) .
$$

推论6（可数无重叠信息组合的容量可加性）设可还原信息 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ 是可数信息集合（204号 $\{ I _ { i } = \langle o _ { i } , T _ { h i } , f _ { i } , c _ { i } , T _ { m i } , g _ { i } \rangle | i = 1 , 2 , \dots \}$ 的无重叠组合，则信息I的关于测度 $\overleftarrow { \boldsymbol { \sigma } }$ 的容量就是所有 ${ { I } _ { i } }$ 关于测度 $\dot { \boldsymbol { \sigma } }$ 的容量之和，即

$$
\begin{array} { r } { \mathrm { v o l u m e } _ { \sigma } ( I ) = \sum _ { i = 1 } ^ { \infty } \mathrm { v o l u m e } _ { \sigma } ( I _ { i } ) . } \end{array}
$$

证明：因为可还原信息 $I$ 是可数信息集合 $\{ I _ { i } | i = 1 , 2 , \dots \}$ 的无重叠组合，即 $I = \textstyle \bigcup _ { i = 1 } ^ { \infty } I _ { i }$ ，且对于任两$i \neq j$ ， $I _ { i } \cap I _ { j } = \varnothing$ ,由推论4的证明可知，对任两 $i \neq j$ 都有 $g _ { i } ( c _ { i } , T _ { m i } ) \cap g _ { j } \bigl ( c _ { j } , T _ { m j } \bigr ) = \emptyset$ 。同时因为$g ( c , T _ { m } ) = \cup _ { i = 1 } ^ { \infty } g _ { i } ( c _ { i } , T _ { m i } )$ ，根据测度的可数可加性，即有volt $\begin{array} { r } { \mathrm { n e } _ { \sigma } ( I ) = \sigma \big ( g ( c , T _ { m } ) \big ) = \sum _ { i = 1 } ^ { \infty } \sigma ( g _ { i } ( c _ { i } , T _ { m i } ) ) = \sum _ { i = 1 } ^ { \infty } \mathrm { v o l u m e } _ { \sigma } ( I _ { i } ) \circ \sigma \big ( g _ { i } ( c _ { i } , T _ { m i } ) \big ) } \end{array}$ （204号

推论得证。

（4）式对于i上限为有限的情形当然也适用。这对于实际应用很重要，因为由网络和计算机构成的信息系统中的所有信息实际上都是有限的，都可以利用（4）式进行容量的和/差分析。

# 3.3原子信息及其组合的容量计算

与物质可以分解到不再可分的基本粒子，能量可以分解到不可再分的量子一样，任何信息也都可以分解到最为基础、不可再分的程度。这就引入了原子信息的概念。

定义8（原子信息）对可还原信息I和I'，若 $I ^ { \prime }$ 是I的真子信息，且不存在任何I的其它真子信息I"，使得 $I ^ { \prime \prime } \subset I ^ { \prime }$ ，则称 $I ^ { \prime }$ 为I的原子信息。

图6直观展现了原子信息的概念。原子信息并非特指以原子为本体或载体的信息。正如基本粒子是构成整个物质世界的最为细微和基础的成分一样，原子信息是构成整个信息空间最为细微和基础的成分，因而对于研究信息的构成和性质具有非常重要的作用。所有信息都可以看作其所有原子信息的组合，并且原子信息之间不会有重叠，因此由推论6可以得到：

![](images/119d9af1beb59ea8cf64ddfaaa24722483cb05eeb33408a2294f3d6b175bbd82.jpg)  
图6原子信息概念示意图

推论7（原子信息及其组合的容量）对可还原信息 $\mathrm { I } = \langle \mathrm { o , T _ { h } , f , c , T _ { m } , g } \rangle$ ，若其中所有原子信息$\mathrm { ~ I ~ } _ { \lambda } = \langle \mathbf { o } _ { \lambda } , \mathbf { T } _ { \mathrm { h } \lambda } , \mathbf { f } _ { \lambda } , \mathbf { c } _ { \lambda } , \mathbf { T } _ { \mathrm { m } \lambda } , \mathbf { g } _ { \lambda } \rangle$ 都有 ${ \bf g } _ { \lambda } ( { \bf c } _ { \lambda } , \mathrm { T } _ { \mathrm { m } \lambda } )$ 关于测度°可测（ $\lambda \in \Lambda$ ，^是指标集)。则当 $\Lambda$ 为可数集时，

$$
\begin{array} { r } { \mathrm { v o l u m e } _ { \sigma } ( I ) = \sum _ { \lambda = 1 } ^ { \infty } \mathrm { v o l u m e } _ { \sigma } ( I _ { \lambda } ) . } \end{array}
$$

当4为有限集时，只需将（5）式中求和的上标 $\infty$ 改为4的基数即可。但若A为非可数集，（5）式不能简单改为积分公式，因为一般情况下测度并不具有对非可数集合的可加性。

所以为简化问题，对于原子信息的研究应尽可能不推广到非可数连续集合的情形。具体而言，I的原子信息数量取决于反映集合 $g ( c , T _ { m } )$ 的构成和特性，进而又取决于载体 $c$ 和反映时间 $T _ { m }$ 的构成和特性。因此若能尽量将 $c , T _ { m }$ 和 $g$ 三个集合都简化为有限集或可数集，则能大为便利信息I的容量计算。幸运的是，尽管宇宙怅然辽阔，人们认为其基本粒子数目总是有限的，因此对任何信息 $I$ ，都可以认为载体 $c$ 由有限的基本粒子集合构成。但时间是连续变量，因而 $T _ { m }$ 就可能是一个非可数的连续集合，故此在研究中对其进行适当的离散化处理，将为计算信息的容量提供充分便利。下文研究信息容量与物质和能量的关系时将证明，信息载体受物理性质所限，只能在离散时间集合上承载不同信息，这便实际达成了数学要求与物理规则的统一。

# 4信息容量与质量、能量和时间的关系

信息的容量由其客观世界中的载体在反映时间所处状态的测度决定。而客观世界中的任何载体都以物质或能量的形式存在，所以物质和能量的状态决定了信息反映集合的状态。而物质和能量状态的变化都需要能量的支持[22]，所以信息的容量必定与其载体的状态及其所蕴涵或被施加的能量密切相关，同时也与载体的反映时间密切相关，这是数十年来人们一直关注的问题。

# 4.1单个量子载体所能承载的信息容量

量子信息理论是当代信息科技的重要前沿成果。一般认为，没有能量低于单个光量子的辐射[23]。单个量子如夸克、轻子等费米子和胶子、W玻色子、光子、引力子等玻色子[24]是在能量上不可再分的基本元素，因而也是承载原子信息效率最高的载体。

推论8（单个量子载体的信息容量）对于可还原信息 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ ，设载体 $c$ 是单个量子,就称I为单个量子载体信息。定义测度 $\sigma$ 就是 $c$ 可以区分的状态数量， $t = \mathrm { s u p } T _ { m } - \mathrm { i n f } T _ { m }$ 为信息I的反映时长，可得信息I关于测度 $\sigma$ 的容量上界估算为

$$
\begin{array} { r } { \mathrm { v o l u m e } _ { \sigma } ( I ) = \left\{ \begin{array} { l l } { 4 \Delta E t / h , } & { \frac { \mathrm { x } } { 2 } t \pm \frac { \mu } { \lambda } \sqrt { 3 } \mathcal { K } \mathcal { K } } \\ { 1 , } & { \frac { \mathrm { x } } { 2 } t \pm \frac { \mu \mathrm { x } } { \mp } \mp \frac { \mu } { \lambda } \sqrt { 3 } \mathcal { K } \mp 2 \mathrm { i } \sqrt { 4 } \mathcal { Z } \mp 0 } \end{array} \right. } \end{array}
$$

其中，volume $_ \sigma ( I )$ 的单位为量子位(qubit)， $\Delta E$ 为量子 $c$ 的平均能量， $h \approx 6 . 6 2 6 2 \times 1 0 ^ { - 3 4 }$ 焦耳秒，为普朗克常数。

证明：根据信息容量的定义，volume $_ \sigma ( I )$ 为单个量子载体 $c$ 在反映时间 $T _ { m }$ 上历经的可以区分的状态数量。量子的状态可以由其两个相互正交的基态 $\left| 0 \right.$ 和|1〉以及它们的相干叠加状态 $\begin{array} { r l } { { \mathfrak { a } } { \big | } 0 \rangle } & { { } + { \mathfrak { b } } { \big | } 1 \rangle } \end{array}$ 组成，其中a和b均为复数，满足 $| \mathbf { a } | ^ { 2 } + | \mathbf { b } | ^ { 2 } = 1 [ 2 5 ]$ 。而量子可以区分的状态一定相互正交[22]，由Margolus-Levitin 定理[26]，从一个状态转化为另一个正交状态的最短时延取决于其具有的平均能量$\Delta E$ ，转换时间不能短于 $\Delta t = h / 4 \Delta E$ 。因为单个量子每一个可以区分的状态恰好承载一个qubit 信息[27]。可见对于载体c，若其具有的平均能量为 $\Delta E$ ，则对于反映时长 $t$ ，当 $t < \Delta t$ ， $\mathbf { \Psi } _ { c }$ 只能呈现一种可以区分于其它状态的状态，此时 ${ \mathrm { v o l u m e } } _ { \sigma } ( I ) = 1 ( { \mathrm { q u b i t } } )$ ，也就是 $c$ 只承载一个qubit 信息，这就证明了等式的下半部分。

更为一般地，对于更长的反映时长 $t$ ，则有

$$
\mathrm { v o l u m e } _ { \mathrm { ~ o ~ } } ( \mathrm { I } ) = [ \mathrm { t } / \Delta \mathrm { t } ] + 1 = [ 4 \Delta \mathrm { E t } / \mathrm { h } ] + 1
$$

因为 $h \approx 6 . 6 2 6 2 \times 1 0 ^ { - 3 4 }$ ，上式中只要t足够大，如当 $\Delta E t \geq 1 0 ^ { - 3 0 }$ 时， $[ 4 \Delta E t / h ] + 1$ 与 $4 \Delta E t / h$ 之差将小于 $1 0 ^ { - 4 }$ 量级，可以忽略不计，此时即有volume $\dot { \sigma } ( I ) \approx 4 \Delta E t / h ( \mathrm { q u b i t } ) .$ 0

推论得证。

推论8表明量子载体受其蕴涵或施加于其上的能量限制，在任一时段只能承载有限个不同的信息，同时因为宇宙中的量子数量总为有限，并且量子载体信息已经是最为基础的信息组成部分，所以即使考虑时间朝向未来的无限性，在数学上也可以确认任何信息最多只能由可数的不同原子信息构成，无论何种情形信息组合的容量可加性总能得以保证。

单个量子具有不可分割性，因而其作为载体在任一时刻的状态都是一个原子信息的反映集合。最为直接的情形是，信息 $I = \cup _ { i = 1 } ^ { n } \{ I _ { i } = \langle c , T _ { m i } , g , c , T _ { m i } , g \rangle | i = 1 , 2 , \dots n \}$ ，其中 $n$ 是单个量子 $c$ 在时间序列$T _ { m i } ( i = 1 , 2 , \dots n )$ 历经的正交状态数量， $g ( c , T _ { m i } )$ 是 $\boldsymbol { \mathbf { \mathit { c } } }$ 在时刻 $T _ { m i }$ 的状态。可见每一个 $I _ { i }$ 都是原子信息，且都是 $f ( o , T _ { h i } )$ 到 $g ( c , T _ { m i } ) = f ( o , T _ { h i } )$ 的自映射，图7表示信息I实际上反映了客观世界中单个量子c自身的状态转换情况，其中 $\left| 0 \right.$ 和1>是量子 $\boldsymbol { \mathbf { \mathit { c } } }$ 的两个基态。此时根据（5）式，volume $\textstyle \sigma ( I ) = \sum _ { i = 1 } ^ { n }$ volumeg(li)= n(qubit)， $n$ 的上界由（6）式给定。

![](images/7a1a4387b7c90f2221ccb2f974d13efaa757d52d234dd676f0fe38669f0ab834.jpg)  
图7量子信息状态变换自映射示意图

更为一般的情形是，信息 $I = \cup _ { i = 1 } ^ { n } \{ I _ { i } = \langle o , T _ { h i } , f , c , T _ { m i } , g \rangle | i = 1 , 2 , \dots n \}$ ，其中 $n , c , T _ { m i } , g ( c , T _ { m i } ) ,$ i的定义都与前例相同，而 $f ( o , T _ { h i } ) ( i = 1 , 2 , \dots n )$ 则是主观或客观世界中的事物本体 $o$ 在发生时间序列 $T _ { h i }$ 历经的状态集合。显然每一个 $I _ { i }$ 也都是原子信息，它们的组合信息 $I$ 则将其它本体的状态使能映射到单个量子 $c$ 的状态之上（图8)，使人们能够利用量子信息技术高效处理主观或客观世界中的各种事物和现象。这里也有 ${ \mathrm {  ~ \ v o l u m e } } _ { \sigma } ( I ) = \sum _ { i = 1 } ^ { n } { \mathrm {  ~ \ v o l u m e } } _ { \sigma } ( I _ { i } ) = n ( { \mathrm { q u b i t } } ) { \mathrm {  ~ \Omega ~ } }$ ，其上界也由（6）式给定。

# 4.2一般载体所能承载的信息容量

![](images/c405328ef5d47a92916772da0c9334be9126623ef5684c44fdf7fc0e3da85ef5.jpg)  
图8一般量子信息状态变换示意图

[28]提出宇宙中的所有能量分别以辐射和物质形式存在。客观世界中任何物质和辐射都可以成为信息的载体，所能承载的信息容量取决于载体的物理特性和工艺水平[29]。目前信息系统中最为常用、承载信息容量最大的载体是硅芯片。按照现在最先进的工艺制造水平，一个硅芯片的质量约为1.6 克，其存储容量能够达到 $1 0 ^ { 1 2 }$ 比特，可见1千克硅芯片所能承载的信息容量为 $6 . 2 5 \times 1 0 ^ { 1 4 }$ 比特。

[30]根据热力学原理和质能转换公式，推算出存储一个比特所需要的最小物质质量为 $m _ { b i t } =$ $k _ { b } T \mathrm { l n } ( 2 ) / \mathrm { C } ^ { 2 }$ ，其中 $k _ { b } \approx 1 . 3 8 \times 1 0 ^ { - 2 3 }$ 焦耳/千克为玻尔兹曼常数， $T$ 为信息载体所处的绝对温度，$\mathrm { C } \approx 2 . 9 9 7 9 \times 1 0 ^ { 8 }$ 米/秒为真空中的光速。由此可知，设信息I的载体是质量为1千克的物质，则其在没有能量耗散的情况下所能承载的信息容量永远是 $\mathrm { v o l u m e } _ { \sigma } ( I ) = 1 / m _ { b i t } = \mathrm { C } ^ { 2 } / k _ { b } T \mathrm { l n } ( 2 )$ 比特，其中测度 $\sigma$ 是比特。当T处常温约为300开尔文时， $\mathrm { v o l u m e } _ { \sigma } ( I )$ 为 $1 0 ^ { 3 8 }$ 比特量级。由于这个公式源于经典热力学原理，因而仅适用于经典数字存储器的平衡状态，不能适用于电子、光子等量子载体情形。

对于以量子为载体的信息，（6）式给出了单个量子载体在特定时间内所能承载的信息容量。由于量子载体信息互不重叠，（5）式所示原子信息组合的容量可加性能够帮助我们估算量子载体所能承载的信息容量。

定理1（量子载体的信息容量）设可还原信息 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ 的载体 $c$ 由 $N$ 个量子组成，载体 $c$ 一部分以物质形式存在，一部分以辐射形式存在，分别具有质量 $m$ 和能量 $E _ { r }$ ， $E$ 为 $c$ 具有的总能量，测度 $\sigma$ 是 $c$ 在反映时间 $T _ { m }$ 上的状态数量， $\mathbf { \Psi } _ { t }$ 为信息的反映时长。则当 $t$ 足够大时， $\mathrm { v o l u m e } _ { \sigma } ( I ) = 4 E t / h =$ 4 $\mathbf { \nabla } \cdot \mathbf { \tau } ( m \mathbf { C } ^ { 2 } + E _ { r } ) t / h ( \mathrm { q u b i t } )$ ，当 $t$ 等于或趋近于0时，volume $\mathbf { \sigma } _ { \sigma } ( I ) = N$ 。特别地为简化表达，让I直接表示自身的信息容量，则可以得到非常简明的信息容量计算公式

$$
I = \left\{ { \begin{array} { c } { { 4 E t / h = 4 ( m C ^ { 2 } + E _ { r } ) t / h , \stackrel { { \scriptscriptstyle { \perp } } V } { = } t \llangle } } } \\ { { N , \stackrel { { \scriptscriptstyle { \perp } } V } { = } t \ddagger { \Rightarrow } \mp \varXi \overrightarrow { \chi } _ { \mathrm { { k } } \notin { \pm } } ^ { \pm \neq } ) \varSigma \mp 0 } } \end{array}  \right. \qquad 
$$

其中I的单位为qubit，C为光速， $h$ 为普朗克常数。

证明：对于可还原信息 $I = \langle o , T _ { h } , f , c , T _ { m } , g \rangle$ ， $E$ 为其载体 $c$ 具有的总能量。根据能量守恒的基本原理[24]， $\mid c \mid$ 在反映时间 $T _ { m }$ 内任何时刻的总能量均应为 $E$ 。另外，载体 $c$ 由 $N$ 个量子组成，若 $c$ 中单个量子的平均能量为 $\Delta E$ ，则 $c$ 在反映时间 $T _ { m }$ 内所含量子数量均为 $N = E / \Delta E$ ，不失一般性可设 $c = \cup _ { i = 1 } ^ { N } c _ { i }$ ，$c _ { i } ( i = 1 , , , N )$ 均为在反映时间 $T _ { m }$ 内一直存在并作为信息载体的单个量子。记信息 $I$ 中以 $c _ { i }$ 为载体的子信息为 $I _ { i }$ ，则每个 $I _ { i }$ 均为单个量子载体信息，并且 $t$ 既是信息 $I$ 的反映时长，也是每个子信息 $I _ { i }$ 的反映时长。根据（6）即有volume $\sigma ^ { ( I _ { i } ) } = 4 \Delta E t / h$ （当t足够大）或volume $_ \sigma ( I _ { i } ) = 1 { }$ （当 $t$ 等于或趋近于0），$( i = 1 , , , N )$ 。又因为 $\textstyle I = \bigcup _ { i = 1 } ^ { N } I _ { i }$ ，各个 $c _ { i }$ 均为不同量子，信息 $I$ 的各个子信息 $I _ { i }$ 互不重叠且 $I _ { i }$ 均由$[ 4 \Delta \mathrm { E t } / \mathrm { h } ] + 1$ 个原子信息组成，根据（4）和（5)，

$$
\begin{array} { r } { \mathrm { v o l u m e } _ { \sigma } ( I ) = \sum _ { i = 1 } ^ { N } \mathrm { v o l u m e } _ { \sigma } ( I _ { i } ) \left\{ \approx \sum _ { i = 1 } ^ { E / \Delta E } 4 \Delta E t / h = 4 E t / h ( \mathrm { q u b i t } ) , \quad \frac { \mathrm { s r } } { = 1 } t \frac { \mathrm { s t } _ { i } ^ { \mathrm { s r } } \mathrm { s t } _ { i } ^ { \mathrm { s r } } } { \mathrm { s r } } \mathrm { s t } _ { i } ^ { \mathrm { s r } } \mathrm { s t } _ { i } ^ { \mathrm { s r } } \right\} } \\ { = \sum _ { i = 1 } ^ { N } 1 = N \mathrm { ( q u b i t ) } , \quad \frac { \mathrm { s r } } { = 1 } t \frac { \dot { x } _ { \mathrm { s r } } ^ { \mathrm { s r } } } { \mathrm { s r } } \mp \frac { \mathrm { s r } } { \mathrm { s r } } \mathrm { s t } _ { i } ^ { \mathrm { s r } } \mathrm { s t } _ { i } ^ { \mathrm { s r } } \mathrm { \Delta } } \end{array}
$$

进一步地， $\boldsymbol { c }$ 的总能量 $E$ 应该是其物质形式和辐射形式分别具有的能量之和，根据质能转换公式[31,32]，物质形式具有的能量是 $m \mathsf { C } ^ { 2 }$ ，其中C为光速。此时 $E = m \mathsf C ^ { 2 } + E _ { r }$ ，这就有当 $t$ 足够大时，volume $\mathsf { \mathsf { z } } _ { \sigma } ( I ) = 4 ( m \mathsf { C } ^ { 2 } + E _ { r } ) t / h ( \mathrm { q u b i t } ) ,$

定理得证。

由于（7）式非常简明地涵盖了信息、物质、能量和时间的基本度量，因此我们简称其为信息、物质、能量和时间的关系公式。设想信息载体可以分解为[24]所列纯粹的量子，当其所含能量相当于质量为1千克的物质时，由（7）式可知，其1秒时间所能承载的信息容量为 $4 \mathrm { C } ^ { 2 } / \mathrm { h } \approx 5 . 3 8 5 3 \times$ $1 0 ^ { 5 0 } ( \mathrm { { q u b i t } ) }$ 。而在某一时刻，其所能承载的信息容量就是其所含量子的数量。假设这个载体全部由电子组成，因为单个电子质量约为 $9 . 1 \times 1 0 ^ { - 3 1 }$ 千克，即1千克载体约含 $1 0 ^ { 3 0 }$ 个电子，所以此时其所能承载的信息容量约为 $1 0 ^ { 3 0 }$ (qubit)。

# 4.3迄今为止宇宙可能承载的信息容量

茫茫宇宙充满了各种信息，也被认为是一台巨大无比的量子计算机。数十年来很多人研究迄今为止整个宇宙究竟可能承载了多少信息[33-37]。根据定理1给出的信息、物质、能量和时间的关系公式以及能量守恒的基本原理[24]，便很容易回答这个问题。

标准暴胀理论预测了宇宙的空间平坦性，Einstein广义相对论确定这样的宇宙具有的总能量密度等于临界密度 $\rho _ { c } = 3 \mathrm { H } _ { 0 } { } ^ { 2 } / 8 \pi \mathrm { G } [ 3 8 ]$ ，其中 $\mathrm { H } _ { 0 } \approx 2 . 1 \times 1 0 ^ { - 1 8 } ,$ /秒为哈勃参数的当前值， $\mathrm { ~ G ~ } { \approx } 6 . 7 \times$ $1 0 ^ { - 1 1 }$ 米/千克秒²为引力常数，即 $\rho _ { c } \approx 7 . 9 \times 1 0 ^ { - 2 7 }$ 千克/米"。另一方面，可观测宇宙的半径大约为（20 $L = 4 . 5 6 \times 1 0 ^ { 1 0 }$ 光年[39]，由此可得整个宇宙的体积估算为 $| V \approx ( 4 / 3 ) \pi L ^ { 3 } \approx 3 . 3 5 \times 1 0 ^ { 8 0 }$ 米，从而可以估算宇宙的总质量为 $m = \rho _ { c } V \approx 2 . 6 \times 1 0 ^ { 5 4 }$ 千克。根据较为普遍的认识，宇宙的年龄大约是137亿年[40]，也即信息反映时长 $t \approx 4 . 3 \times 1 0 ^ { 1 7 }$ 秒，根据（7）式，可得宇宙迄今为止的信息容量为 $I =$ 4 $m \mathbb { C } ^ { 2 } t / h \approx 4 \times 2 . 6 \times 1 0 ^ { 5 4 } \times ( 3 . 0 \times 1 0 ^ { 8 } ) ^ { 2 } \times 4 . 3 \times 1 0 ^ { 1 7 } / ( 6 . 6 \times 1 0 ^ { - 3 4 } ) \approx 6 . 1 \times 1 0 ^ { 1 2 2 } ( \mathrm { q u b i t } ) \circ$ 这个估计与[34]估算宇宙的逻辑运算次数为 $1 0 ^ { 1 2 3 }$ 几近一致。根据客观信息论的观点，宇宙的任何一次逻辑操作必然产生特定状态，这些状态一定蕴涵客观存在的信息，所以可以认为宇宙在特定时间的逻辑操作次数就是其所具有的状态总数。另一方面，这个估计与[34]估算宇宙的信息容量为 $1 0 ^ { 9 0 }$ 比特不相同，这是由于它用熵[41]定义信息的容量，与定理1的信息容量定义有很大区别。两者相比，作者认为利用“载体在反映时间内所有状态的测度”定义信息容量更具普适性。更为重要地，定理1建立了客观世界物质、能量和信息三大要素以及时间之间的一般关系，对于任何信息载体，只要给定质量、能量和时间，都能代入（7）式求得信息容量的上界。

# 5 结语

本文立足于客观信息论的基本概念，提出了关于信息的四项公设并证明了信息六元组模型满足定义信息的充分必要条件，论述了利用信息熵定义信息容量仅仅是客观信息论所定义信息容量的一种特例，证明了单个量子载体在反映时间所能承载的信息容量上界，建立了信息、物质、能量和时间的关系公式，较为深刻、准确地揭示了客观世界组成要素之间的相互关系，表明客观信息论的理论体系具有很好的普适意义和应用前景。

客观信息论不仅定义了信息的容量度量，还分析了信息具有客观性、还原性、组合性、传递性和关联性等五种基本性质，建构了信息的延迟、广度、粒度等另外十种度量。本文仅针对信息的本质及其容量特性进行了初步研究，今后还能够进一步针对信息的其它基本性质和度量开展各自特性以及相互之间关系的深入研究，同时对照、检验与现有各类信息科学原理和技术工具的兼容关系，推动建立普适完整的信息科学理论和全面丰富的信息系统动力学体系，为信息科技发展和应用提供更加有力的理论工具。

# 致谢

中国科学院郭雷院士、王永良院士、崔铁军院士、浙江大学吴飞教授和湖南大学李肯立教授、廖驳副教授在与作者关于信息科学的多次讨论交流中给予了很多重要指导和启发；中国政法大学刘振宇教授、王雅实教授、北京理工大学王树良教授、郑涛教授、党迎旭先生和人民法院信息技术服务中心王赢飞博士在与作者共同研究客观信息论和信息系统动力学的过程中给予了有关研究思路和文献收集等方面不可或缺的帮助，人民法院出版社丁鼎先生帮助绘制了所有插图，在此一并致以感谢！

# 参考文献

[1] Hartley, R.V.L. Transmission of Information. Bell Syst. Techn. J. 1928,VII, 535-563.   
[2] Shannon, C.E.The mathematical theory of communication.The Bell System Technical Journal.27,379- 423, 623-656(1948).   
[3] Brillouin,L. Science and Information Theory, Academic Press Inc., New York, New York,1956.   
[4] MacKay, D. Information, Mechanism and Meaning; MIT Press: Cambridge, MA, USA,1969.   
[5] Campbell, J. Grammatical Man: Information, Entropy, Language,and Life; Simon and Schuster: New York, NY,USA, 1982; p. 32.   
[6] Landauer, R. Information is physical. Phys. Today 44, 23-29 (1991).   
[7]Fleissner P,Hofkirchner W.Emergent information: towards a unified information theory.BioSyst,1996, 38: 243-248.   
[8] Zhong,Y. X.Principles of Information Science.3rd ed.Beijing: Beijing University of Posts and 社,2002. 111 - 116].   
[9] Rao M, Chen Y, Vemuri B C,et al. Cumulative residual entropy: a new measure of information. IEEE Trans Inform Theory, 2004,50:1220-1228   
[10] Zaliwski A S. Information-is it subjective or objective? Triple C: communication,capitalism & critique. Open Access JGlobal Sust Inform Soc,2011, 9: 77-92   
[11] Yan, X. S.Information science: Its past, present and future[J]. Information,201, 2(3): 510-527.   
[12] Burgin M.Theory of Information: Fundamentality, Diversity and Unification. Singapore: World Scientific Publishing Co Pty Ltd.,2010.   
[13] Li X, Cheng YQ, Wang H Q,et al. Progress in theory and applications of information geometry.Sci Sin Inform,2013,43:707-732[黎湘,程永强,王宏强,等.信息几何理论与应用研究进展.中国科学：信息 科学,2013,43: 707 - 732]   
[14] Logan,R. K. What Is Information?:Why Is It Relativistic and What Is Its Relationship to Materiality, Meaning and Organization.Information.3,68-91(2012).[15]许建峰,汤俊,马雪峰,等.客观信息的模型 和度量研究.中国科学:信息科学,2015,45(3):336. Xu, J.F.& Tang, J. & Ma, X. F. et al. Research on The Model and Measurement of Objective Information. Science China: Information Science.45(3),336-353(2015).   
[16] Xu,J.F.& Wang, S.L.& Liu, Z. Y.& Wang, Y.F. Objective Information Theory Exemplified in Air Traffic Control System. Chinese Journal of Electronics. 30(4),743-751(2021)   
[17] Xu, J.F.et al.Foundations and applications of information systems dynamics.Arxiv,2022,Available at: https://arxiv.org/abs/2112.15505.   
[18]Xu,J. F. Sun,F. H. Chen, Q. W. Introduction to the Smart Court System-of-Systems Engineering Project of China. Singapore: Spinger, 2022.   
[19] Wiener,N. Cybernetics: Or Control and Communication in the Animal and the machine.(MIT Press,New York, 1961).   
[20] Landauer, R. The physical nature of information. Phys. Lett. A 217,188-193 (1996).   
[21]周民强.实变函数论（第二版）.(北京大学出版社,北京,2008).   
[22] Lloyd, S. Ultimate physical limits to computation. Nature 406,1047-1054 (2000).   
[23] Wiener,N. The Human Use of Human Beings: Cybernetics and Society(New Edition). (Da Capo Press, Cambridge,1988)   
[24] Taube,M. Evolution of Matter and Energy on a Cosmic and Planetary Scale. (Springer-Verlag, New York,1985).   
[25] Zizzi,P.Holography, Quantum Geometry,and Quantum Information Theory. Entropy 2,36-39 (2000).   
[26] Margolus, N.& Levitin, L. B.The maximum speed of dynamical evolution. Physica D 120,188-195 (1998).   
[27] Nielsen, M. A. & Chuang, I. L. Quantum Computation and Quantum Information. (Cambridge University Press,New York,2010).   
[28] Hubble,E. Proc.Natl. Acad. Sci. U.S.A. 15, 168(1929).   
[29]Landauer,R.Irreversibility and heat generation in the computing process[J]. IBM Journal of Research and

Development 5(3),183 - 191 (1961). [30] Vopson,M. M. The mass-energy-information equivalence principle[J]. AIP Advances 9,095206:1-4 (2019). [31]Einstein, A. On The Electrodynamics of Moving Bodies. Annalen der Physik.17(10),891-921 (1905). [32] Rohrlich,F. An elementray derivation of $\scriptstyle \operatorname { E = m c } ^ { 2 }$ [J]. Am. J. Phys. 58(4),348-349(1990). [33] Gleick, J. The Information: A History, a Theory,a Flood. (Vintage,New York,2011). [34] Lloyd,S.Computational Capacity of the Universe.Physical Review Letters,88(23),237901:1-4(2002). [35] Vopson,M.M.Estimation of the information contained in the visible mater of the universe.AIP Advances 11, 105317:1-5(2021). [36] Davies,P. C.W.“Whyis the physical world so comprehensible?” in Complexity,Entropyand the Physics of Information. (Addison-Wesley, Redwood City, 1990). [37] Treumann,R.A. Evolution ofthe information in the universe. Astrophys. Space Sci.201,135-147 (1993). [38] Bahcall,N.A.& Ostriker, J.P.& Perlmutter,S.& Steinhardt,P.J.The Cosmic Triangle: Revealing the State of the Universe. Gen. Science 284,1481-1488 (1999). [39] Got II,J.R.& Juri' c,M.& Schlegel, D.& Hoyle,F.& Vogeley,M.& Tegmark,M.& Bahcall,N.& Brinkmann, J.A map of the universe. Astrophys.J.624(2), 463-484(2005). [40] Bryson, B.A Short History of Nearly Everything. (Broadway Books,New York, 2003). [41] Reichl,L.E.A Modern Course in Statistical Physics.(University of Texas Press,1980).