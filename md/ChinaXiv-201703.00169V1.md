# 集成电路中的时延可测性设计技术

# 裴颂伟 李华伟

摘要：随着集成电路制造工艺的特征尺寸不断减小，高性能集成电路产品的定时约束变得越来越严格。各种制造缺陷如阻性开路、阻性短路、通孔中形成空洞以及栅氧化层失效等现象的影响在当前先进的集成电路制造工艺下也变得越来越显著。为了确保芯片的出厂质量，通常需要对其进行有效的时延测试。对集成电路进行时延可测性设计不仅可以非常有效地检测芯片中的时延缺陷，而且可以为芯片在量产前进行有效的调试。在本文当中，我们首先介绍了集成电路中的时延缺陷对芯片性能和可靠性的影响，然后分别介绍了一些采用时延可测性设计技术来提高芯片时延测试故障覆盖率、精简时延测试向量集规模、检测芯片中小时延缺陷以及对芯片的时延故障进行在线检测的方法。

关键词：时延测试，可测性设计，小时延缺陷，故障覆盖率，时延测量

# 1 引言

，随着集成电路制造工艺的特征尺寸不断缩小，芯片的性能以及复杂度也不断提高[1]。在特征尺寸进入超深亚微米条件下，芯片在制造后包含阻性开路、阻性短路、通孔中形成空洞、以及栅氧化层失效等缺陷的现象越来越多，其影响也越来越显著，给芯片的性能和可靠性带来了严重的挑战[2。此外，集成电路中的沟道长度、氧化层厚度、金属线宽等工艺参数难以精确地控制到相应的期望值，而是分布一个范围之内。因而，器件之间的饱和电流、阈值电压、电阻电容等电学参数存在很大的偏差，并最终将导致芯片中的逻辑门和信号传播通路存在很大的时延偏差[3]。因此，在芯片的定时约束变得越来越严格的情况下，测试芯片在额定的工作频率下是否能够正确地工作成为确保芯片品质的一个不可或缺的步骤[4,5]。这就产生了对时延可测性设计的需求。

首先，使用功能向量对芯片进行时延测试不仅需要非常昂贵的外部测试仪来实速地施加这些功能向量，而且需要很大的代价来开发相应的功能向量集以达到满意的时延故障覆盖率[6]。

再有，在深亚微米工艺下，集成电路中的小时延缺陷（small delay defect，通常指引起的额外时延较小的制造缺陷）越来越普遍，传统的时延测试方法通常难以对其进行检测。而在芯片时延测试中没有检测到的小时延缺陷，当电路在正常功能操作模式下，如果影响了一条非常长的功能通路的信号传播时延，则芯片将可能发生定时失效（timing failure)。此外，即使芯片中包含的小时延缺陷不会影响电路的正常功能，也会给芯片在使用的过程中带来非常严重的可靠性挑战[2。例如，芯片内部某个通孔在制造过程时形成的小空洞带来的小延迟虽然暂时没有影响功能通路，但却可能会在日后的使用过程中随着电迁移失效而发生断路，并导致芯片的功能失效[,8]。为了检测小时延缺陷，很多基于自动测试程序生成（ATPG）的方法都是试图使生成的时延测试向量尽可能敏化时隙值（slack，指测试时钟周期与通路时延的差值）较小的长通路，然而这种方法的有效性将受到芯片内通路时延分布情况的影响。一方面，电路中存在某些结点，即使通过它的最长通路仍然具有很大的时隙；另一方面，与电路规模呈指数增长的通路数、时延偏差、复杂设计以及测试约束带来的很低的通路可测性[5.9]，导致很难选取足够的可测长通路来进行测试。超速测试为芯片中的小时延缺陷检测提供了一种更加有效的手段。然而，通过高速的外部测试仪来对芯片进行超速时延测试，其实现代价将非常昂贵。此外，测试时钟的频率也非常容易受到相应的寄生电阻、寄生电容、传输线阻抗等杂散参量的限制[10,11,12]。

此外，芯片在正常使用过程中也可能会发生由于软错误、串扰、电源噪声等而导致的瞬态时延故障。在芯片集成度越来越高的情况下，芯片在正常的使用过程中发生软错误的概率不断增高；芯片中互连线之间的耦合电容的增长也将导致更加严重的串扰效应；同时，电路时延对电压波动也越来越敏感。因此，对于可靠性要求高的应用来说，通常需要对电路中的功能失效进行在线检测[13,14]，而设计片上时延违例检测电路可以为芯片功能失效的在线检测提供一个重要手段。

综上所述，时至今日仅仅依赖于外部测试仪来对芯片进行时延测试，其有效性将会受到限制。因此近年来很多学者对芯片的时延可测性设计技术做了一些相应的研究，以有效地提高芯片时延故障覆盖率、精简时延测试向量集规模、检测芯片中小时延缺陷以及对芯片的时延故障进行在线检测等。下面本文将分别介绍一些近年来相关的时延可测性设计技术。

# 2 基于混合扫描的时延测试技术

基于扫描结构的时延测试方法通常作为芯片时延测试的一种非常有效的手段。一般来说，为了测试芯片中某一个结点是否存在跳变故障（transitionfault)，可以通过使用扫描链在被测电路上应用一组测试向量 ${ < } \mathrm { V } 1 , \mathrm { V } 2 { > }$ 来完成。其中时延测试的第一个测试向量，即初始化向量V1，用来把被测电路的内部逻辑初始化到一个确定的状态；第二个测试向量，即加载向量V2，用来在被测电路的输入上产生相应的跳变，并激发和传播目标结点的故障效应，从而通过在额定的时钟周期之后捕获电路的响应来检测电路中的时延故障。时延测试向量对中的初始化向量 V1一般是应用慢速的扫描测试时钟通过对扫描链进行移位得到。根据对时延测试向量对中加载向量V2的获取方式，可以把常见的时延测试方法大致分为捕获加载(launchoncapture，简称LOC)，移位加载(launchonshift，简称LOS）以及增强型扫描（enhancedscan）三种方法[5]。

![](images/cdefec8d45974e21d1b24712ab79436218dc0f6bf4d74d5d8c6cf302d11d1a1a.jpg)  
图1. 部分增强型扫描单元扫描链

![](images/6123c5c292883e64d15a309fdd4326b0127e917023765cc14471d2cbe20671a1.jpg)  
图2. 通用扫描触发器

在捕获加载方式中，加载向量V2 是通过在加载时钟周期阶段，电路捕获初始化向量V1的电路响应得到。这种时延测试方式的实现代价很小。然而在这种方法当中，由于在获取加载向量V2时将会受到电路结构的约束，从而导致很多跳变故障不可检测，即得不到一个相应的电路状态能够激励这些故障的故障效应并传播到芯片的可观测输出。因此，捕获加载时延测试方法的故障覆盖率相对较低。

在移位加载时延测试方式中，加载向量V2是通过初始化向量V1进行移位得到，然而这种方法需要一个实速的扫描使能信号，从而使得硬件实现相对比较困难，故通常不被大多数基于扫描设计的电路所采用。此外，加载向量V2与初始化向量V1之间存在移位依赖，

限制了被测芯片的跳变时延故障覆盖率。

增强型扫描时延测试方法由于扫描触发器中能同时保存两位数据，测试时初始化向量V1与加载向量V2之间可以不存在任何结构约束。因此，这种方法能达到非常满意的跳变时延故障覆盖率。但是，为了保存两位测试数据而不影响移位时的电路测试状态，需要非常大的硬件开销。由此有些学者通过把这种方法与捕获加载结合起来，通过采用部分增强型扫描时延测试方式，即把电路扫描链中比例非常小的通用扫描触发器置换为增强型扫描触发器单元，从而以可以接受的硬件开销来达到令人满意的跳变时延故障覆盖率，或者获得非常精简的时延测试向量集以减少测试成本。

图1所示为部分增强型扫描单元的扫描链结构的一种实现方案[15,16]。从图中可以看出，该扫描链中包含部分通用扫描触发器以及部分增强型扫描触发器。图2所示为一种常见的基于多路选择器的通用扫描触发器[5]

![](images/057362b38d1845740b132616e282cd5cd188fc0a094c85c2584b46dc890ca83e.jpg)  
图3. 增强型扫描触发器的两种实现方案

图 3(a)和图 3(b)分别是增强型扫描触发器的两种实现方案[15,16]。从图中可以看出，增强型扫描单元和通用的扫描触发器单元具有相同的外部引脚，因此可以方便地应用在标准的工业设计流程当中。显然，增强型扫描触发器中能同时保存两位数据，因此，加载向量V2 可以不依赖于初始化向量V1的电路响应。图3(a)和图3(b)中的增强型扫描触发器具有相似的电路功能。下面将通过描述图3(b)中增强型扫描触发器的功能来分析包含部分增强型扫描单元的电路扫描链的工作方式。

图4为图3(b)所示增强型扫描单元在工作情况下相关信号的时序图[1]。不失一般性，我们假设所有的触发器均为时钟上升边缘敏感触发。从图中可以看出，如果电路需要工作在正常电路功能的模式下，只需使扫描使能信号保持为低电平，在电路时钟初始化之

![](images/f1eb98ed5a1614f4617a698c1a76c48d227df75c078857bca734716d9ab91b55.jpg)  
图4. 增强型扫描触发器的时序图

后，多路控制（MUXControl）信号也将保持为低电平。显然，在这种情况下，增强型扫描单元的功能等效于通用的扫描触发器，组合逻辑信号可以通过DI端口保存到触发器当中。当扫描使能信号为逻辑高电平时，被测电路的扫描链将处于扫描移位状态，从而可以通过 SI端口，分别为增强型扫描触发器中的主、从触发器扫入相应的状态值。在这种情况下，当通过捕获加载来获取时延测试向量对中的加载向量V2时，由图3(b)可知，电路扫描链结构上的通用扫描触发器捕获的是其相应的组合逻辑的响应值，而增强型扫描触发器由于其内部多路控制信号仍保持为高电平，因此其主触发器捕获的是来自其从触发器的加载向量V2中的对应位，从而能够有效提高被测电路的跳变时延故障覆盖率[16]。

然而为了使被测电路的面积开销可以接受，必须通过一种有效的优化选择方法来将被测电路中部分关键的通用触发器替换为增强型扫描触发器。对这种方法的研究引起了学者的关注。

在文献[17]中，提出了采用部分增强型扫描时延测试方法来提高被测电路通路时延故障覆盖率。通过从电路全增强型扫描时延测试方式出发，在不降低通路时延故障覆盖率的前提下，依次将被测电路扫描链中相应的增强型扫描单元替换成通用单元。

在文献[16]中，通过对被测电路中每一个通用触发器进行可控性分析，即假设给被测电路的每一个原始输入和伪输入（即触发器的输出）施加一个取0和取1概率均为0.5的随机向量，通过蒙特卡罗模拟或者可控性分析得出随机向量在进行相应逻辑运算后每个触发器上置0或置1的概率，计算该概率值相对于0.5的偏移，把概率值具有较大偏移的触发器替换成增强型扫描单元。然而由于概率计算存在较大的误差，而且简单的基于概率的触发器可控性分析结果与跳变时延测试的故障覆盖率之间关联度相对较弱，因此为了达到高的跳变时延故障覆盖率仍需要在触发器的替换上进行大量的调整。

在文献[18]中，在基于捕获加载不可测而增强型扫描可测的跳变时延故障集合基础上，提出了把部分通用扫描触发器替换成增强型扫描触发器的选择算法，从而期望在面积开销较小的前提下，来尽可能提高被测电路的跳变时延故障覆盖率。然而在这种方法中，没有考虑跳变时延故障的敏化传播通路。

在文献[15]中，通过对电路中通用扫描触发器进行可控度和有用度的分析，提出了把部分通用扫描触发器替换成增强型扫描触发器来精简时延测试向量集规模的选择算法。此外，通过采用部分增强型扫描时延测试方法，被测电路的跳变时延故障覆盖率也会得到相应的提高。

通过研究触发器和故障检测之间的关系，我们也提出了两种触发器选择方法，分别用于有效地提高被测电路的跳变故障覆盖率[19]和精简测试向量集的规模[20]。在文献[19] 中，基于对捕获加载不可测而增强型扫描可测的跳变时延故障集合，提出了相应不可测的故障和通用扫描触发器之间相关度的计算方法。从而可以依据计算得到的相关度值，把部分关键的通用扫描触发器替换成增强型扫描触发器，以有效地提高跳变故障覆盖率。在文献[20]中，基于对被测电路冗余故障的分析，并通过对被测电路的跳变故障进行精简，分别定义了激活相关度和敏化相关度的概念。依据对通用扫描触发器的激活、敏化相关度以及可控度进行的计算，建立了一个选择函数来把部分关键的通用扫描触发器替换成增强型扫描触发器，从而可以有效地精简时延测试向量集的规模。

# 3 片内时延测量技术

通过在集成电路中应用可测性设计（DesignforTestability）技术对芯片进行片内通路时延测量，将不仅可以非常有效地检测芯片中的时延缺陷，而且还能方便地对芯片进行量产前的调试[21,22]。为了对芯片中某条特定通路的时延进行片内测量，可以首先为被测通路生成一组单通路可敏化的时延测试向量，通过对被测通路施加相应的测试向量把通路的起点和终点的跳变信号

![](images/e1548bead875899a225b26d7f1960307fa2dca18883bbef615ee5b06c9efa0dd.jpg)  
图5. 片内时延测量实现结构

分别引入到片内时延测量单元当中。如图5所示为片内时延测量技术的一种简单实现结构[25]，其中 BIDM(Built-In Delay Measurement）代表片内时延测量装置。将被测通路输入和输出端口的跳变信号分别通过多路选择器或者编解码器选择输入到BIDM单元当中来进行通路时延的测量。通路时延的测量结果值可以通过 BIDM 电路中的时延读出（DelayReadout）端口得到[21]。从图中可以看出，进行时延测量通路的输入和输出可以分别是电路中的原始输入、伪输入以及原始输出和伪输出（即触发器的输入)。此外，为了更加方便地对芯片的时延故障进行测试和调试，也可以选择把电路的内部结点作为输入或者输出的通路引入到片内 BIDM电路中进行时延测量[21]。下面介绍几种近年来采用数字方法实现的片内时延测量电路[23]。

# 3.1采用游标延迟线原理的实现方法

图6所示为基于游标延迟线原理进行片内时延测量的实现方法[24]。从图中可以看出，该方法包含两个平衡的缓冲器链。假设上面的缓冲器链（连接到y端口）中的缓冲器单元的延迟 $\mathrm { D } _ { \mathrm { y } }$ 相对较大，下面缓冲器链 (连接到x端口)中的缓冲器单元的时延值 $\mathrm { \Delta D _ { x } }$ 相对较小,被测时延通路的起点和和终点分别连接到图6所示的时延测量电路的y端口和 $\mathbf { x }$ 端口。如果在被测通路的起点施加了一个上升的跳变信号，在延迟这条被测通路的时延值之后，在这条通路的输出端口也形成一个同样的上升跳变信号。那么，如果这条被测通路输入和输出的两个上升跳变信号之间存在一个足够大的时延差，则图6所示的时延测量电路中离 $\mathbf { x }$ 和y输入端口最近的第一个触发器将会被锁存到逻辑高电平。

![](images/33d86ef8fd206ff5f301cebe11e109a91cae325d6d3992e55d6d1fce1fb062f3.jpg)  
图6. 改进的游标延迟线方法

容易发现，当进入时延测量电路中 $\mathbf { x }$ 和y端口的两个上升跳变沿着上下两个缓冲器链分别进行传播的时候，这两个跳变信号之间的时延差将会随着缓冲器级数的增加而逐渐减少。假如这个片内时延测量电路的量程足够大，那么最后将导致一些触发器由于其时钟信号满足不了其所要求的建立时间，而保存为初始化的逻辑低电平。因此可以通过锁存到逻辑高电平的触发器数目来得知这条被测通路的时延。从图6中可以看出在这种基于游标延迟线原理的方法的时延测量的分辨率 $T R$ 为：

$$
T R = D _ { y } - D _ { x }
$$

同单一缓冲器链进行时延测量的方法相此，这种基于游标延迟线的方法不会因为在特定工艺下，缓冲器本身带来的时延引起时延测量分辨率的降低。理论上，这种时延测量方法的精度可以满足任意时延大小通路的测量。

在参考文献[22]当中，如图7所示，通过在常规的扫描触发器基础上增加两个多路单元，改进成时延扫描触发器。当时延扫描链上的时延扫描信号delay scan为逻辑高电平时，分别连接被测通路输入和输出的端口y和x上的跳变信号将被送入到时延扫描触发器当中，开始进行时延测量。当delay_scan信号为低电平0时，时延扫描触发器的功能将等效于常规的扫描触发器。采用这种结构进行片内时延测量的基本原理仍然为基于游标延迟线技术。

![](images/c10ff78672238ef7ac714faa13692ace6c992079dafa38c57360964e184e6b70.jpg)  
图7. 时延扫描链

在参考文献[21]当中，如图8所示，基于改进的游标延迟线的方法，把测量的电路分为每级测量范围较大的粗粒度模块和每级测量范围较小的细粒度模块。被测通路的起点和终点处的跳变信号分别通过参考信号端口Ref 和数据端口Data 进入校准电路和可以减轻毛刺的施密特触发器电路，然后通过专门设计的动态逻辑门（dynamic-logic gate，DG）把Ref和Data端口送入的跳变信号转换成上升跳变信号送入到粗粒度的差分延迟线上，小于粗粒度分辨率的时延值进一步送入到细粒度的差分延迟线上进行测量。

![](images/9f277d1d936ca03d889b54fbd79ac80f46d4d7470fc0d9e56df308ac881761e9.jpg)  
图8. 粗细粒度结合片内时延测量电路

![](images/daed8c42cfd86aff4b36525ae7083f1e3536ff9a73bf4ff1f54614386541ec00.jpg)  
图9. 低开销的片内时延测量电路

为了降低时延测量的面积开销，我们提出了一种用于检测和调试时延故障的片上通路时延测量电路结构[25]，如图9所示。该电路使用多级时延测量单元来进行通路时延的测量，从连接到测量电路输出的最后一级测量单元到第一级，相应每级测量单元的时延测量分辨率成倍递增，依据存储在各时延级中触发器的值构成的二进制数可计算出两个跳变信号之间的时延差。与已有的基于游标延迟线的方法相比，该方法能够以较少的时延级测量较大的时延范围，显著减少测量时间和面积开销，同时在时延测量分辨率和测量精度上都有所改善。

# 3.2基于非对称反相器实现片内时延测量的技术

图10 所示为采用非对称反相器延迟线实现片内时延测量的方法[26]。图10(a)为脉冲产生器，其实质为一个异或门。图10(b）为两个非对称反相器电路。假设被测通路的起点和终点分别有一个上升跳变信号，且分别连接到图10(a)所示的 $\mathbf { x }$ 和y信号端，通过脉冲发生器后，将如图10(c)中所示完成脉冲整形。图10(c）为采用非对称反相器延迟线进行片内时延测量的结构。其中每一级脉冲整形电路如图10(b)所示。图10(b）中的非对称反相器单元设计了两个非对称的反相器，其中第一个非对称反相器的PMOS 管的宽度设计得较大，为相应反相器中NMOS管宽度的 $m$ 倍。第二个非对称反相器的NMOS管的宽度设计得较大，为相应反相器中PMOS管宽度的 $\mathbf { \nabla } _ { m }$ 倍。其工作原理如下：当一个下降跳变信号送入该非对称反相器延迟单元，由于第一个反相器的 PMOS 管的宽度较大，第一个反相器的输出电平被拉升得很快，同理由于第二个反相器的 NMOS 管的宽度较大，第二个反相器的输出电平同样被拉低得很快。这样，信号通过这种非对称反相器延迟线后的脉冲宽度逐级缩窄，当脉宽足够小的时候，将不足以把期望的逻辑值锁存到触发器中。因此，通过每一级非对称反相器减小的脉冲宽度以及测量电路中每一个触发器被锁存的电平值，就能够得知被测通路上的时延值大小。

![](images/f692a4e70fa4412ac092a42991df825de8a98ef674ba8889cd279da35ba78239.jpg)

图10. (a)脉冲产生器 (b)非对称反相器 (c）采用非对称反相器延迟线的时延测量电路

# 3.3采用环形振荡器原理进行片内时延测量的实现方法

图11所示为采用环形振荡器原理实现片内通路时延测量的方法[27]。图11(a)中的测量校准单元(measurement and calibration unit) MC可进行时延值大小调整。图11(a)中的校准加载触发器（calibration launch flip-flop）CLFF和校准捕获触发器（calibration capture flip-flop）CCFF分别如图11(b)和图11(c)所示。这两种触发器由改进常规触发器而得到，其目的是为了实现跳变信号能够在被测通路和CLFF到CCFF的通路之间产生环形振荡。这种时延测量方法的工作原理如下：首先为从CLFF触发器通过MC单元到CCFF的通路生成一个时延测试向量，利用MC单元中的控制扫描链，对MC的时延进行调整，通过判断测试向量通过和失效，把CLFF通过MC单元到CCFF的通路时延调整为刚好是一个时钟周期，并记为 $T _ { \mathrm { c m c } }$ 。结合图11(a)、图11(b）和图11(c)可以看出，当测量电路中的振荡激励信号OE有效时，跳变信号可以在被测时延通路和CLFF到CCFF的通路之间形成一个环形共振。在时间 $T$ 内，假设一个跳变信号经历这个环路 $2 N$ 次，则可以得知这条被测通路的时延 $T _ { \mathrm { p a t h } }$ 为：

$$
T _ { \mathrm { p a t h } } = T / 2 N - T _ { \mathrm { c m c } }
$$

![](images/c7968f38d38063f033008759a9395b2316ae1950aa22cfb6dc80b22980204e2c.jpg)  
图11. (a)片内时延测试结构 (b)通路终点的改进触发器 (c）通路起点的改进触发器

# 4 片内超速时延测试技术

片内超速测试通过在集成电路内部生成具有可调整频率的测试时钟，用比电路功能时钟频率更高的测试时钟对芯片进行测试，并以此来降低电路通路的时隙值，从而实现对芯片中的小时延缺陷进行有效的检测。

麦克劳伦等人（T.McLaurin and F.Fredrick）[28]提出了一种基于片内的锁相环来设计时钟控制电路，从而实现片内超速测试的方法。然而使用这种方法进行片内超速测试，需要在应用每一个测试向量之前对锁相环进行复位，实际使用非常麻烦。

泰德等人（R.Tayade andJ.A.Abraham）[12] 提出了一种如图12 所示的片内可编程捕获信号（CAPTURE）发生器，从而可以通过调整测试的时钟周期来进行通路时延测量。图12(a)为可编程捕获信号发生器。通过调整扫描触发器的时钟信号选择器值，可以使得测试触发器（test trigger）TT 处的跳变信号通过粗粒度和细粒度两级时延单元来控制捕获信号CAPTURE 和测试触发信号TT之间的时延值，即通过改变加载（Launch）时钟和捕获（Capture）时钟之间的时延差来调整测试时钟的频率。基于这个片内可编程捕获信号生成电路，实现了用于捕获加载、移位加载和增强型扫描时延测试三种不同的测试方法的硬件结构。图12(b)为采用增强型扫描时延测试方法相应的硬件实现结构，稍加修改就能适用到捕获加载和移位加载时延测试方法当中。图12(c）为时钟信号选择器。从图12(b)中可以看出，在电路的扫描链上增加了一个增强型扫描单元。因此可以通过应用测试向量，使得时延测试在发生加载（Launch）事件的同时，扫描链上增加的增强型扫描单元使得 TT 处产生一个上升跳变信号，从而TT 处的上升跳变信号将通过可编程的捕获信号生成器对测试时钟周期进行调整。从图12(c)中可以看出，当功能时钟停止信号FCLK_STOP 为逻辑高电平，扫描使能信号SE为逻辑低电平时，捕获信号CAPTURE送入到时钟CLK。因此通过可编程捕获信号发生器，调整CAPTURE和TT信号之间的时延值，即可改变测试时钟的周期，从而实现片内超速时延测试。

![](images/3a6ffa990e1db4c4eb0cfbb0f26182c7b2386bea4b934e6647258ebe725df57f.jpg)  
图12. (a)可编程CAPTURE信号发生器（PCG）(b）增强型扫描时延测试中的通路时延测量结构(c）时钟信号选择器

# 5 在线时延故障检测技术

芯片在出厂时，通常都需要对其进行有效的测试来确保其能正确地工作在额定的工作频率卜。然而芯片在使用过程当中可能由于发生了软错误、串扰、电源噪声等而导致芯片发生瞬态时延故障，并且电路的老化效应也会使芯片的时延增加，最终发生功能失效。因此，对于一些关键的应用来说，通常还需要芯片在正常操作模式进行功能失效的在线检测和预测。

图13(a)所示，为拉赫米法等人（KRaahemifar and M.Ahmadi）[29]提出的一种可用于对芯片在功能模式下进行在线时延故障检测的电路结构。假设 $\Phi 1$ 代表电路中的时钟信号，

S 代表电路的组合逻辑输出。图13(a)中电路结构对芯片中时延故障进行在线检测的基本原理是检测芯片中的组合逻辑输出的信号稳定性，即检测组合逻辑上的输出信号在时钟边缘到达之前是否已经进入了一个稳定的状态。假设电路中的触发器为时钟下降沿敏感触发，那么可以通过把图13(a)中的稳定性检测电路插入到芯片中组合逻辑的输出处来进行在线的时延故障检测。显然，当时钟信号为高电平时，图13(a)中的N2管将会处于导通状态，从而不管组合逻辑输出保持什么样的电平值，Out 和Od 将保持相同的逻辑电平值。当时钟下降边缘到达后，对于一个没有发生时延故障的芯片来说，所有的组合逻辑输出应该已经稳定到一个期望的终值。在时钟信号为低电平时，N2管将被关断，Out 和Od结点将保持为这之前的逻辑电平状态。然而，如果组合逻辑输出在时钟信号为低电平时发生了信号翻转，那么Out或者Od的状态值将会发生变化，因此通过把Out和Od信号进行异或运算，即可以根据异或门的输出来在线检测到芯片中的时延故障。显然，对于图13(b)的稳定性检测电路，其工作原理和图13(a)类似。

基于图13(c)所示电路结构的信号稳定性检测原理，[13,14]等文献分别提出了对芯片失效进行预测和检测的方法。假设电路中的触发器为时钟上升沿敏感触发。如图13(c)所示，假设CLK为电路的时钟信号，CO和COV分别代表组合逻辑的输出信号及其反相值。显然，当时钟信号为低电平时，M1和M2 管将处于导通状态，M5处于关闭状态。因此不管CO 以及COV的信号如何取值，S1和 S2将处于逻辑高电平。我们把S1和S2信号作为输入连接到一个输出为OUT的或非门，于是OUT信号将处于一个逻辑低电平。这个过程，被称为稳定性检查器的预充电阶段。在电路上升时钟边缘到达前，如果芯片没有时延故障，那么所有的组合逻辑输出应该已经稳定到一个期望的终值。显然，在这种情况下，OUT信号仍然将处于逻辑低电平。然而，如果组合逻辑输出在时钟信号为高电平时发生了信号翻转，那么 S1和 S2都将变为逻辑低电平，导致OUT信号变为高电平。由此可见，通过分析OUT信号的电平值，可以对芯片的时延故障进行在线检测。

![](images/cea9dc3491150d119de1978a12fe2f0d771fd6ab7d9c94b1673ec042ab9f743f.jpg)  
图13. 信号稳定性检查器

# 6总结

本文介绍了集成电路中时延可测性设计的一些技术，通过在芯片中采用时延可测性设计技术，可以用来有效地提高芯片的跳变时延故障覆盖率、精简时延测试向量集规模、检测芯片中小时延缺陷以及对芯片的时延故障进行在线检测等。总的来说，研究集成电路中时延可测试设计技术，一方面关注的是如何以更小的面积开销来使被测电路达到更满意的故障覆盖率和更理想的测试向量集规模，从而提高时延测试的质量并降低测试时间；另一方面关注的是如何在更合理的面积开销前提下，在片内设计高精度的时延测量电路或产生时延测试需要的高速检测信号，从而有效地实施小时延缺陷的检测，节省使用外部高性能测试仪的昂贵开销。时延测试的有效应用长期以来一直是困扰业界的难题，作为解决该难题的一个重要思路，时延可测性设计技术将持续受到关注。

# 参考文献：

[1] International Technology Roadmap for Semiconductors, http:/pulic.itrs.net.   
[2] Hawkins et al.,“A View from the Bottom: Nanometer Technology AC Parametric Failures-Why, Where,and How to Detect,” Proceedings of International Symposium on Defect and Fault Tolerance,2003, pp.267-276.   
[3] D.Blaauw,K.Chopra,A.Srivastava,L. Schefer,“Statistical Timing Analysis:From Basic Principles to State of the Art, IEEE Transactions Computer-Aided Design of Integrated Circuits and Systems,Vol.27,No.4, pp.589-607,Apr. 2008   
[4] T.Mak，A.Krstic, K.T.Cheng，and L.C.Wang,“New challenges in delay testing of nanometer, multigigahertz designs,” Proceedings of CASS, 2004, pp.241-247.   
[5] A.Krstic and K.T.Cheng,“Delay Fault Testing for VLSI Circuits,” Boston, MA: Kluwer, 1998.   
[6] Gefu Xu and A.D.Singh,“Delay Test Scan Flip-Flop: DFT for High Coverage Delay Testing,” proceedings of 20th international conference on VLSI Design, 2007, pp.763-768.   
[7] N.ahmed, M.Tehranipoor, and V.Jayaram,“A Novel Framework for Faster-than-at-Speed Delay Test Considering IR-drop Effects,” Proceedingsof IEEE/ACM International Conferenceon Computer-Aided Design, 2006, pp.198-203.   
[8] B.Kruseman，A.K.Majhi， GGronthoud, and S.Eichenberger,“On Hazard-free Paternsfor Fine-delay Fault testing,” Proceedings of International Test Conference,2O04,paper 9.1.   
[9] Wangqi Qiu, D.M.H.Walker,"An efficient algorithm for finding the k longest testable paths through each gate in a combinational circuit”, Proceedings of International Test Conference, 2003, pp. 592-601.   
[10] H. Yan and A. D. Singh,“Experiments in Detecting Delay Faults using Multiple Higher Frequency Clocks and Results from Neighboring Die,” Proceedings of International Test Conference ,2003,pp. 105-111.   
[11]B. N. Lee,L. C. Wang, and M. S. Abadir,“Reducing Pattern Delay Variations for Screening Frequency Dependent Defects,” Proceedings of VLSI Test Symposium, 2005, pp. 153-160.   
[12] R.Tayade and J.A.Abraham,“On-chip Programmable Capture for Accurate Path Delay Test and Characterization,”Proceedings of International Test Conference,2Oo8,paper 6.2.   
[13] M.Agarwal, B.C.Paul,M.Zhang,and S.Mitra,“Circuit Failure Prediction and Its Application to Transistor Aging,” Proceedings of IEEE VLSI Test Symposium, 2007, pp.277-286   
[14]Guihai Yan, Yinhe Han,and Xiaowei Li,“A Unified Online Fault Detection Scheme via Checking of Stability Violation”,IEEE Design,Automation & Test in Europe Conference & Exhibition, 2009, pp. 496-501.   
[15]Seongmoon Wang,Wenlong Wei,“Low Overhead Partial Enhanced Scan Technique for Compact and High Fault Coverage Transition Delay Test Patterns” Proceedings ofIEEE European Test Symposium, 2008,pp.125-130   
[16]Gefu Xu,A.D.Singh,“Flip-flop Selection to Maximize TDF Coverage with Partial Enhanced Scan”, Proceedings of Asian Test Symposium, 2007, pp. 335-340.   
[17]Kwang-Ting Cheng，S.Devadas,K.A.Keutzer,“Partial Enhanced-Scan Approach to Robust Delay-Fault Test Generation for Sequential Circuits”,Proceedings of International Test Conference, 1991, pp. 403-410.   
[18]N.Devtaprasanna, A.Gunda, P.Krishnamurthy,S.M.Reddy,I.Pomeranz,“Methods for improving transition delay fault coverage using broadside tests”, Proceedings of International Test Conference, 2005, pp. 255-265.   
[19] Songwei Pei, Huawei Li, and Xiaowei Li,“Improving Transition Delay Fault Coverage with Partial Enhanced Scan", Digest of papers of IEEE 10th Workshop on RTL and High Level Testing, 2009.   
[20] Songwei Pei, Huawei LI,and Xiaowei LI“Flip-flop selection for transition test pattern reduction using partial enhanced scan,”Proceedings of IEEE 15th Pacific Rim International Symposium on Dependable Computing,2009,pp.75-80.   
[21] Ming-Chien Tsai, Ching-HwaCheng, Chiou-Mao Yang,“An All-Digital High-Precision Built-In Delay Time Measurement Circuit”, Proceedings of 26th IEEE VLSI Test Symposium,2008, pp. 249-254.   
[22] R. Datta，A. Sebastine,J.A. Abraham,“Delay fault testing and silicon debug using scan chains”, Proceedings ofNinth IEEE European Test Symposium,2004,pp.46-51.   
[23] 裴颂伟，李华伟，李晓维，"集成电路中的片内时延测量技术"，第十三届全国容错计算学术 会议论文集，pp.505-510,2009.   
[24] R.Datta，A. Sebastine,A. Raghunathan and J.A.Abraham.“On-chip Delay Measurement for Silicon Debug",Proceedings of GLSVLSI,2004,pp.145-148.   
[25] Songwei Pei, Huawei Li,and Xiaowei Li,“A Low Overhead On-chip Path Delay Measurement Circuit ",Proceedings of IEEE 18th International Asia test symposium,2009,pp.145-150.   
[26] R.Datta, G.Carpenter, K.Nowka,J.A.Abraham,“A Scheme for On-chip Timing Characterization”, Proceedings of 24th IEEE VLSI Test Symposium,2006, pp.24-29.   
[27] Xiaoxiao Wang，M.Tehranipoor,R. Datta,“Path-RO: A novel on-chip critical path delay measurement under process variations”, Proceedings of IEEE/ACM International Conference on Computer-Aided Design,2008,pp. 640-646.   
[28] T.McLaurin and F.Fredrick,“The testability features of the mcf5407 containing the 4th generation coldfire microprocessor core,” Proceedings of International Test Conference, $2 0 0 0 , \mathsf { p p } 1 5 1 { \mathsf { - } } 1 5 9$   
[29] K.Raahemifar and M.Ahmadi，“Design-for-Testability techniques for detecting delay faults in CMOS/BiCMOS logic families”,IEEE transactions on circuits and systems- IIAnalog and digital signal processing, Vol.47, No.11, pp.1279-1290, Nov.2000.

作者简介：

裴颂伟： 中国科学院计算技术研究所系统结构重点实验室博士研究生李华伟： 中国科学院计算技术研究所系统结构重点实验室研究员，博士生导师，lihuawei@ict.ac.cn