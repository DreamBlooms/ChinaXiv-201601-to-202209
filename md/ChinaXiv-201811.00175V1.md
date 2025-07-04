# 面向云端FPGA的卷积神经网络加速器的设计及其调度

蔡瑞初1，余洋1，钟椿荣1，卢 冶²，陈瑶1,3†(1．广东工业大学 计算机学院，广州 510006;2.南开大学 计算机与控制工程学院，天津 300350;3．新加坡高等数字科学中心，新加坡 新加坡 138602)

摘要：卷积神经网络的高计算复杂性阻碍其广泛用于实时和低功耗应用，现有软件实现方案难以满足卷积神经网络对运算性能与功耗的要求，传统面向FPGA的卷积神经网络构造方式具有流程复杂、周期较长和优化空间较小等问题。针对该问题，根据卷积神经网络计算模式的特点，提出一种面向云端FPGA的卷积神经网络加速器的设计及其调度机制。通过借鉴基于HLS 技术、引入循环切割参数和对卷积层循环重排的设计，采用模块化方式构造网络，并进行参数拓展以进一步优化加速器处理过程；通过分析系统任务和资源的特性总结调度方案，且从控制流和数据流两方面对其进行优化设计。与其他已有工作相比，所提出的设计提供了一种同时具有灵活性，低能耗、高能效和高性能的解决方案，并且探讨了加速器的高效通用调度方案。实验结果表明，与CPU实现相比，该设计实现AlexNet达到8.48倍的加速，而实现Cifar的功耗仅为其 $2 4 . 9 6 \%$ ；相较于CPU+GPU实现对Cifar6.90倍的加速比，虽然实现较大规模网络的性能不及GPU，但功耗最小仅为其 $1 4 . 9 8 \%$ ；与已有研究成果相比，最大达到6.29 倍的加速比。其中与大平台生成的加速器相比，即使仅达到相当的性能，但具有更低的时钟频率。

关键词：卷积神经网络；现场可编程门阵列；高层次综合；加速器；调度 中图分类号：TP183 doi:10.19734/j.issn.1001-3695.2018.05.0507

# Design and scheduling of convolutional neural network accelerator for cloud FPGAs

Cai Ruichu1, Yu Yang1, Zhong Chunrong1, Lu $\mathrm { Y e } ^ { 2 }$ , Chen Yao1, 3† (1.CollegeofComputerScience Guangdong UniversityofTechnology,Guangzhou 51oo06,China;2.CollgeofComputer& ControlEngineering,NankaiUniversity,Tianjin30050,hna;3.AdvancedDigitalciencesCenter,Singapore38602, Singapore)

Abstract:Convolutionalneuralnetwork'shighcomputationalcomplexityoftenobstructsits widespreadadhibitioninreal-time andlow-powerapplications.The existingsoftware implementationsolutioncannotmeet thedemandsoftheconvolutionaleural network for computing performance and powerconsumption.The traditional FPGA-oriented convolutional neural network construction method has problems such as complicated process,long cycleand smalloptimization space.For these problems, according tothecharacteristicsofconvolutionalneural networkcalculationpatern,thispaperproposedadesignandscheduling mechanism ofconvolutional neural network acelerator forcloud FPGAs.Byusing forreference the design which based HLS technology,mportedthecycliccutigparametersandrearrangedtheconvolutionlayercirularly.Thenconstrutedteetwork inamodular way,and extended parameters tofurtheroptimize theacelerator procesing processSummarized thescheduling scheme byanalyzingthecharacteristicsofsystemtasksandresources,andoptimizedits design fromtwoaspectsofcontroland data flow.Incomparison with other existing work,the proposed design provided asolution with flexibility，low energy consumption,high energyeficiencyand performance.The design alsodiscussd the eficient universalscheduling schemeof the accelerator.Experimentalresults showthatcompared withtheCPUimplementation,this designachieves 8.84timesspeedup of AlexNet,while the power consumption of Cifar implementation is only $2 4 . 9 6 \%$ of it.Compared with the $\mathbf { C P U + G P U }$ to achieve 6.90times speedupofCifar,althoughthe performanceoflarge-scalenetwork isinferiortotheGPU,butthe minimum power consumption is only $1 4 . 9 8 \%$ .This design achieves the maximum acceleration of 6.29 times in comparison with the existingresearchresults.Compared to theacelerators generatedforlarge platforms,evenifitonlyhascomparable performance but with a lower clock frequency.

Key words: convolutional neural network; field programmable gate aray; high-level synthesis;accelerator; scheduling

# 0 引言

近年来，深度学习（deeplearning）的发展令人瞩目，引起了各个领域的巨大变革。以卷积神经网络（convolutionalneuralnetwork，CNN）为代表的方法在图像处理领域占据统治地位[12]。CNN广泛应用于计算机视觉（computer vision）[3-4]中，已经成为图像识别和分类任务中最有效的方法。有研究表明，CNN正在取代许多传统用于视觉任务的组合算法[5]。相关的应用包括人脸识别[]，交通标志检测等。现在，CNN已经成为众多科学领域的必备工具之一，在计算机视觉、模式识别（patternrecognition）[8]、自然语言处理（natural language processing）[9]等领域得到越来越广泛的应用。

而随着CNN模型朝着更大更深的方向发展，以及数据量的进一步增加，所需的存储器容量和操作数量呈指数增长。同时CNN在推理过程中，其计算模式具有高度重复的流水线和并行性[10]。而通用处理器为冯诺依曼结构，其串行执行指令的特性并不适合用来挖掘CNN的并行性，基于软件方式的CNN在实时性和功耗方面都不能满足应用的需求，CNN的计算模式使其非常适合硬件加速。

基于这些原因，在基于ASIC，GPU和FPGA的文献中已经提出许多加速器[10\~12]。相比于传统的 CPU 平台，GPU 虽然可以为深度学习算法提供较高的处理性能，但较高的功耗导致其计算效能低下；ASIC 解决方案虽然可达到性能和功耗之间的最佳平衡，但其高设计和制造成本使之并不具有优势；而现场可编程逻辑门阵列（field programmable gate array,FPGA）计算资源丰富、能源效率高、开发周期短、重构能力强，能够应对CNN运算的要求，可以充分发挥CNN中的并行特性[13]，并在低功耗的限制条件下，实现CNN的运算加速，达到性能和功耗之间的适当平衡[14]。

与嵌入式平台相比，云端FPGA旨在提供大量的逻辑和内存资源，提供PCIe、DDR控制、时钟控制等通用服务逻辑。在云环境中使用FPGA可实现既快速又高效节能的CNN推理。对于大型加速器而言，相较于嵌入式平台，云端FPGA中存储器和逻辑资源（DSP除外）通常是足够的。然而，当前CNN算法涉及大量的权重数据，从而与输入数据计算产生大量的中间结果，FPGA平台的片上RAM资源通常不足以缓冲所有数据。该限制使得应用系统需要大量的片外存储器。

然而，FPGA设计存在较大挑战：目标硬件设计的学习难度大，开发周期长。FPGA的容量飞速增长，使采用传统设计工具的开发效率没有以与之相对应的比率增长，所以越高的工程应用复杂性意味着越长的开发周期。高层次综合[15]（high-level synthesis,HLS）是提高FPGA开发效率的一种有效技术，使采用高级编程语言（例如ANSI $\mathrm { C / C ^ { + + } }$ 或者LabVIEW）来自动生成优化后的算法执行代码对FPGA进行编程成为可能。

本文将介绍针对云端FPGA的卷积神经网络加速器的设计及其调度方案。本文的主要贡献如下：

a）构造支持HLS的可重用CNN加速器模板库函数，简化CNN加速器在云端FPGA上的设计及生成，充分发挥出FPGA的并行优势和云计算平台的应用优势；

b)提出通用加速器调度机制，充分利用硬件资源和片外数据传输带宽，最小化网络模型处理延迟。

# 1 相关工作

CNN 作为乘法累加(multiply-accumulate,MAC)密集型算法,其固有的并行性使其实现方式与并行计算紧密相关。神经网络应用对于性能和功耗的需求，使CNN如何在低功耗条件下发挥高能效的问题得到学者广泛关注和深入研究。GPU已经被证实可以达到足够的性能水平[2,.11,16];然而其高功耗和低能效使之不能满足应用的加速需求。而ASIC解决方案[I7需要高设计和制造成本，且灵活性较低。在这些用于硬件加速的不同类型的器件中，FPGA成为硬件加速的理想选择。

文献[13]中使用ZynqSoC实现了一种采用8路并行引擎的CNN加速器。但该加速器面向卷积核设计，当卷积核尺寸变化时，不能充分发挥并行计算性能，会造成大量的资源浪费；Antony等人[18]通过FPGA实现了多层感知器网络，并详细分析了定点数格式表示和浮点数格式表示以及串行实现和并行实现对硬件实现的神经网络的性能的影响。然而，该实现并未给出具体完整的CNN的FPGA设计方案。

通过使用循环优化技术[19]和良好的缓存设计[20]，CNN可以表现出确定性的数据访问模式，因此可以最大化数据重用并减少片外数据传输。在[12]的工作中，Zhang等人使用多面体方法评估这些采用循环嵌套优化的技术，使用roofline 模型[21]解决寻找上述优化的有效平衡的问题，以提高性能并减少FPGA面积。但是仅用其方法测试网络[2]的第1-5层，通过避免评估通信密集型的全连接层（第6-8层）而人为产生高CTC比率（计算通信比)。文献[22]中也展示了仅1-5层的类似测试，这意味着全连接层将由主机处理，而不是采用卷积层和全连接层通用的加速器设计。

Murugan等人[23]设计了使用FPGA中大量DPS单元和片外DDR存储器的CNN协处理器，为了实现复杂的运算模块控制，该设计仍然需要使用PC作为上位机。同时，上位机也参与部分运算。与上述前几个相关工作一样，对于系统复杂的逻辑和模块控制，并未考虑设计良好的调度方案。

# 2 HLS及卷积神经网络

# 2.1HLS技术的优势和限制

传统地采用寄存器传输级（register transferlevel，RTL）描述语言设计FPGA代码具有流程复杂、周期较长和优化空间较小等问题。借助HLS技术，可以从硬件和软件两个角度快速探索设计空间，给FPGA设计带来很大便利，在不影响性能的情况下大幅缩短FPGA研发周期，使其开发时间甚至低于DSP和GPU[24]。基于HLS的优化是通过使用诸如指定流水线，展开循环和处理数据传输之类的技术来提高总体设计效率的实用方式。HLS非常高效，允许使用C， $\mathrm { C } { + } { + }$ 和OpenCL等高级语言来设计FPGA硬件加速器。与 $\mathrm { C } { + } { + }$ 等高级编程语言相比，HLS要求在编译之前将内存需求和目标函数的接口声明为静态。某些$\mathrm { C / C ^ { + + } }$ 语法不能被综合，如一些依赖操作系统的函数、动态内存分配和标准模板库等。为了使设计高效可用，本文充分考虑了这些限制条件。

# 2.2 CNN 模型功能层

典型的卷积神经网络由卷积层、池化层、全连接层以及激活层构成。如图1所示。

![](images/e1d0312de57c57612623c439b0b7d2de8b3522a859295b41989ba11608385a31.jpg)  
图1典型卷积神经网络模型  
Fig.1Typical convolution neural network model   
图2优化后的卷积计算  
Fig.2Optimized convolution calculation

卷积层输入特征图通过和卷积核局部连接进行卷积操作，将卷积结果累加并加一个偏置量后所得即为输出特征图。通过该过程从输入图像提取不同特征，并且通过堆叠多个卷积层来提取更高级特征。一般地，卷积层可以用以下表达式表示：

$$
\begin{array} { r } { \chi _ { j } ^ { \prime } = \sum / { \in } N _ { j } \chi _ { j } ^ { \prime - 1 } \ast W _ { i , j } ^ { } + B _ { j } ^ { \prime } } \end{array}
$$

其中: $\chi _ { j } ^ { \prime }$ 表示第1层卷积层的第 $\mathrm { ~ j ~ }$ 个卷积核对应的输出特征图，$N _ { j }$ 表示当前卷积对输入特征图的选择， $w _ { i , j }$ 表示第丨层的第j个卷积核的第i个加权系数， $B _ { j } ^ { \prime }$ 表示第1层卷积层的第j个卷积核对应的偏置系数。

池化层的工作原理类似于卷积层。池化层与卷积层相连，可起到二次特征提取的作用。通常采用最大值或均值采样进行池化操作来降低输入矩阵的规模。池化操作可有效减小特征映射的尺寸以节省大量的内存来存储中间结果；且其像素选择可确保将最相关的特征传播到下一层。

全连接层也称为线性层，是一种特殊的卷积层。全连接层可整合卷积层或池化层中区分类别的局部信息，通过对输入进行线性空间转换，从而得到向量形式输出，网络最后一个线性层的输出特征图数等于要识别的类别数。

激活层中激活函数的应用将像素值压缩至特定函数范围内，避免因卷积层中的乘法累加操作而导致值无限增加。且该函数通过添加非线性，将分类边界平滑化。常用的激活函数包括冲击响应（Sigmoid）、非线性（ReLU）、三角函数（Tanh）等。卷积层经过激活函数的非线性变换可表示为式 $( 2 ) , f$ 为激活函数。

$$
\chi _ { j } ^ { \prime } = / ( \Sigma i \in N _ { j } \chi _ { j } ^ { \prime - 1 } \ast w _ { i , j } + B _ { j } ^ { \prime } )
$$

# 3 基于HLS的模板函数库设计

本章主要针对CNN网络模型，对文献[12]中的设计方法进一步性能优化，通过模块化方式构造网络，提高计算的并行度和资源利用效率，增强加速器模板的通用性。

# 3.1性能优化

典型的卷积层由6级for-loops 组成[12]。本文借鉴[12]中的设计，即采取分块实现方式，为卷积层加速器引入循环切割参数，分别对输入输出维度的循环进行切割，通过对卷积层循环的重排，使得其可以借助HLS工具所提供的循环展开及流水线优化，进行硬件生成优化。最后采用缓存优化指令，使得卷积计算单元的执行与缓存单元获取数据并行执行，从而提高加速器内部的并行度。在此基础上，在卷积层加速器进行高层次综合前，将其数值确定为固化的加速器参数，并进行参数拓展，根据FPGA生成的加速器硬件地址映射特点设计offset参数来表示地址偏移量。使用地址偏移量可以提高FPGA片上资源利用效率，增加数据缓存大小、减少数据缓存次数，从而加快卷积计算的进程。优化后的卷积计算过程如图2所示。

in_buf [Tn][I_BUF][I_BUF];   
w_buf [Tn][Tm][W_BUF][W_BUF];   
out_buf [Tm][O_BUF][O_BUF];   
load weight();   
load bias();   
load input();   
for(i=0;i<K;i++){ for (j=0;j<K;j++){ for (tr =O; tr<Tr; tr++){ for (tc =O;tc<Tc; tc++){   
#pragma HLS PIPELINE for (tm =O; tm <Tm; tm++){   
#pragma HLS UNROLL for $\mathrm { ( } \mathrm { { t n } = 0 }$ tn<Tn;tn++){   
#pragma HLS UNROLL out_buf[tm][tr $^ +$ r_offset_o][tc $^ +$ c_offset_o] $\mathbf { \tau } = \mathbf { \tau }$ w_buf[tn][tm][i + W_r_offset][] $^ +$ W_c_offset] \* in_buf[tn][S $^ { * } \operatorname { t r } + \operatorname { i } +$ r_offset_i][S\*tc+j +c_offset_i];   
11111

由于卷积计算与池化计算均需大量的循环，且其数据获取及计算过程具有相似性，以上卷积加速器的优化方式同样适用于池化层加速器，但由于池化不改变输入特征维度，所以池化层加速器共用输入输出特征维度。

# 3.2模板化构造网络层功能

由于CNN前向传播过程中，层间运算具有独立性且相同类型的层运算模式相同，因此可通过设计针对不同类型层的通用的模板函数来实现CNN前向计算。而CNN前向传播是按照网络结构逐层顺序进行，即网络相邻层之间有数据依赖，不能并行处理。据此，基于上文的性能优化设计，通过设计足够通用的网络层模板，可以复用单层运算资源来节约硬件资源，让加速器以更高的计算能效来实现完整的CNN前向计算。

为了让不同规模的CNN均可复用硬件运算单元，需对硬件运算单元进行灵活性设计，并将配置参数化，使加速器模板具有可依据不同网络模型进行配置重构的能力。其中，加速器所采用数据类型、数据位宽、加速器缓存大小、数据处理并行度等，在编程实现时，均为加速器模板参数；同时数据获取方式、数据处理模块、数据输出模块等也进行参数化，可依据应用进行调整与重构。

a）卷积层。卷积层经过输入特征图和卷积核权重的三维乘法和累加得到输出，所处理的输入输出数据均为3维数据。基于卷积层的计算性质和分块实现方式，设计参数列表为输出、输入特征数，输出特征大小，内核大小，输入、输出特征偏移量，步长大小，填充大小和激活类型。根据FPGA生成的加速器硬件地址映射特点，设计offset参数来表示偏移量。卷积加速器模板如图3所示。

![](images/c1418e0de622990356a01e07dd5324a72bc9dde3040846af93fd7ed058798b96.jpg)  
图3卷积加速器模板

其中，Tn、Tm为输入、输出缓冲区特征数，I_BUF、O_BUF为输入、输出缓冲区大小，W_BUF为权重缓冲区大小。

b)池化层。池化层采取与卷积层类似的滑动窗口处理输入数据，并对每个滤波器的输入求最大值或平均值等。考虑到不同网络中卷积层和池化层的连接关系不同，将池化层以与卷积加速器相同的方式实例化为独立加速器，来增强加速器对不同模型的适用性与可重构性。采取与卷积层相同的加速器设计，由于池化层不改变输入特征维度，因此只有一个特征维度参数，其参数定义与卷积加速器相同，如图4所示。

![](images/e5b645cc6f3f6ebf49b9926cd1bb26c73fdbf2100f16abf1a6764f82d714d2b2.jpg)  
Fig.3 Convolution accelerator template   
Fig.4Pooling accelerator template

c）全连接层。通过分析CNN的特性得知，全连接层的计算相对于卷积层，区别仅在于减少了卷积核心内部的循环操作，可将全连接层视为卷积层的一种特殊形式。因此，采用卷积层加速器进行全连接层的计算，可通过复用卷积加速器来节约硬件资源，提高加速器的计算效能，达到对资源的高效利用。

d）数据存储体。为上述加速器分配相应的数据存储体，同样将其参数化。数据存储体用于存储3维输入和输出数据，以及相应的权重和偏置。采用多存储接口，设计输入、输出存储体的参数列表为输入、输出缓冲区特征数，输入、输出缓冲区大小；权重存储体的参数列表为输入、输出缓冲区特征数，权重缓冲区大小，其结构如图3中的3维数据存储体。

# 4 加速器的调度机制

本章主要介绍基于前文加速器模板设计的CNN加速器系统架构和相应通用加速器调度机制，即软硬件划分、系统构造流程、任务-资源调度模型和相应的调度优化方案。

# 4.1系统架构

# 4.1.1软-硬件划分

本文采用软硬件协同设计。结合HLS技术与云端FPGA平台所实现的“处理器 $^ { + }$ 加速器”架构，通过对任务在软硬件上的划分与协同设计，完成任务模型向硬件平台的映射。云端Host-CPU上的软件部分作为整个系统的控制端。CPU运行软件代码，并为硬件分配加速器任务。硬件端可根据不同加速任务，启动加速器来实现对计算的加速。CNN应用的执行过程主要分为三个阶段，即数据预处理、CNN推理、分类结果的整理和输出。其中，CNN推理中卷积、池化、全连接和激活函数等操作计算需求高，且数据吞吐率相对较高，将其划分为硬件加速器实现；而另外两个阶段与应用的前后端联系更为紧密，计算需求低，接口要求高，将其划分为Host-CPU执行。此外，加速器状态的控制、数据的转变和传输、CNN应用执行时间的测量和系统的调试也由Host-CPU管理。目标系统的软硬件划分如图5所示。

![](images/6f391c0d25fef659cd4f42b65bdb7879aff6ca376dca0ff3c95fffe7b544c829.jpg)  
图4池化加速器模板  
图5系统软硬件划分  
Fig.5System hardware and software partition

# 4.1.2系统构造流程

构建CNN应用首先需要掌握网络模型的配置和权重信息，通过构造CNN模型分析器，对使用Caffe 深度学习框架[25]训练所得网络模型描述文件进行分析，将其提取为网络配置参数和权重数据文件。其中，网络配置参数文件包括网络结构，所有层类型和输入、输出特征尺寸，卷积核大小，步长大小，填充大小等信息。然后根据系统软硬件划分，完成任务模型向软硬件端的映射。通过提取网络模型特征，结合CNN加速器模板，实现加速器的设计与生成。针对FPGA片上资源结构及特征，实现加速器缓冲区的构建及生成。最后，完成CPU和FPGA之间的任务分派及其任务-资源调度。系统构造流程如图6所示。

![](images/cd7f5665198bb536f5cb4d23cf809ad54e39a599fb8a5d9dae3766316b28184b.jpg)  
图6系统构造流程

# 4.2任务-资源调度模型

# 4.2.1任务调度

基于前文的软-硬件协同设计和CNN数据访问模式的特性建模分析得知，在FPGA上实现CNN各层的处理过程可分为三个操作阶段，即输入、计算和输出阶段。

a）输入阶段。将计算所需的输入数据从CPU片外DRAM移至FPGA片上BRAM。网络权重数据已在预处理阶段传输完成，不计入该输入阶段。通过将输入数据的一部分突发读入临时缓冲区，并移动到加速器生成的输入缓冲区中。

b)计算阶段。运算单元在启动时，从宿主端读取配置信息，根据配置信息，调用加速器启动命令执行计算。该阶段紧接于输入阶段处理所需的所有后续计算。在输入和权重之间执行元素乘法和累加计算，输出结果存储于加速器输出缓冲区。

c）输出阶段。将上阶段加速器输出缓冲区所得结果传回CPU片外存储器，并将其作为网络下层的输入数据。

由于采用分块实现方式，系统的逻辑和模块控制比较复杂，所以需对CNN各层的任务进行调度。系统中的Host-CPU负责加速器状态与运算过程的控制以及数据的传输，由主机控制代码完成。整个推理过程被封装为一个任务单元并分配给网络加速器。网络加速器被封装为PCIe设备，应用程序调用集不需要知道硬件的细节。根据以上分析，图7展示了执行卷积层的任务调度过程。

![](images/161a6f37ab1da11d9ef0cdbf2e64d5f167723d8de8434bc97e06d81b09f7c859.jpg)  
图7任务调度  
Fig.7Task scheduling;

# 4.2.2资源调度

虽然将模型参数和中间结果存储在片上BRAM中可以显著提高性能，但PFGA由于其计算资源、传输带宽的限制，往往无法满足高并行性所需的资源要求。因此，必须在片外动态存储器中分配数据缓冲区来存储中间结果和模型参数。将网络整体的资源划分为计算资源和缓存资源。加速器分配的层计算参数、权重、输入和输出缓冲区属于计算资源，缓存资源则用来存储模型参数和中间结果。资源调度的整体控制由通用处理器完成，当任务调度的输入阶段开始执行，从CPU片外存储器传输数据至加速器输入缓冲区，然后控制启动加速器进行计算。计算完成后，将加速器输出缓冲区的结果传输至CPU片外存储器。对应于任务调度三阶段中的输入和输出阶段，两种资源之间数据传输的方向分别映射为缓存资源 $$ 计算资源，计算资源$$ 缓存资源。根据以上描述，总结资源调度过程如图8所示。

![](images/8da28f8336176e1eb50297d0d7d71555e2244c15214a6c3ddb7be38770200432.jpg)  
Fig.6System construction process   
图8资源调度  
Fig.8Resource scheduling;

# 4.3 调度优化

# 4.3.1数据流

在卷积过程中，输入特征图上相同滤波器中不同位置之间的部分像素相互重叠，使得有必要在不同的迭代中存储一些输入像素。由此考虑在硬件资源和带宽允许的情况下，在每个卷积层的输入阶段向加速器输入缓冲区传输部分数据。而该阶段传输数据消耗的时间计入网络处理时间，需对其进行优化来减小网络处理的延迟。通过每次仅存储计算输出特征图的Tr行所需的一部分输入数据可以最小化输入阶段等待时间。设计为存储输入的行数为 $\mathrm { T r } \ ^ { * } \mathrm { S }$ ，并且列的数量为 $\mathrm { T c } ^ { \ast } \mathrm { T n }$ ，其中Tr和Tc 是加速器设置的输出特征大小，S和Tn分别是该层的步长大小和输入特征缓冲区的通道数量。图9说明了优化后的操作过程。在开始时，窗口的第一个 $\mathrm { T r } ^ { * } \mathrm { S }$ 行被填充以便有足够的数据来开始计算。当卷积核在该 $\mathrm { T r } ^ { * } \mathrm { S }$ 行上滑动完毕，新的一个 $\mathrm { T r } ^ { * } \mathrm { S }$ 行输入数据被加载到窗口中进行下一次迭代，并以相同方式继续计算，直到产生所有输出特征映射。

片上缓冲区的设计基于Double Buffering 的基本思想，来保证数据并行读取计算需求。其中双缓冲区采用ping-pong 操作，以便将数据传输时间与计算重叠，从而提高处理效率。将片上缓冲区分为两组，分别用于输入特征图和输出特征图。每个缓冲区集都包含多个独立的地址连续的缓冲区，每个输入缓冲区集和输出缓冲区集中的缓冲区组数量分别等于Tn和Tm。

![](images/1d5ffae10dd0c3922aea747b07c8c58a14d6061c2a621c37b8bd8dabd6825eae.jpg)  
图9卷积数据流调度优化  
Fig.9Scheduling optimization of convolution data stream scheduling

optimization

图10举例显示了几个计算和数据传输阶段的时序。对于输入特征映射，第一阶段，计算引擎正在处理input0，同时将下一个输入阶段所需的数据复制到input1,下一个输入阶段将执行相反的操作。对于输出特征映射，当计算和数据复制的[N/Tn]个阶段完成后，得到的输出特征映射存储于输出缓冲区集中。当outputO的空间被最大化利用后，则使用output1，并传输output0中存储的输出数据，下一个输出阶段同样执行相反的操作。

![](images/620412f85ed067d09753553792416d784403b7749591bbcd5e5084e485f367b0.jpg)  
图10基于Double Buffering 的数据流调度优化  
Fig.10Dataflow scheduling optimization based on Double Buffering

# 4.3.2控制流

在云端FPGA平台实现CNN推理的过程，包含软件和硬件实现两部分任务。在三个任务阶段中，输入和输出阶段由软件端控制实现，计算阶段则由软件端调用加速器启动命令来执行计算，即启动后的计算过程由硬件端控制实现。而软件和硬件执行部分的操作和资源都互相独立，且本文采用DoubleBuffering设计，这使得当前计算阶段与下个输入阶段及与上个输出阶段均可达到一定程度的并行化，从而减小整体网络延迟。对应于数据流优化，相应的控制流进行调度优化后的任务调度流程如图11所示。

# 5 评估

# 5.1实验设置

# 5.1.1软硬件环境

本文实验采用配备一个XilinxVU9PFPGA板卡的AWSF1EC2实例作为基于云的实验平台。该FPGA包含2585K逻辑单元和6800个DSP。此外，它拥有75.9Mb的BlockRAM和270

MbUltraRAM。网络模型的软件实现运行在8核英特尔i7-XeonCPUE5-2430（带15MB 缓存）和NVIDIAGPUTeslaK80上。5.1.2网络模型与测试数据集

选取Cifar、AlexNet、VGG-16等CNN模型及其量化版本作为实验对象，量化方法基于文献[26]，在本文的评估中，量化版本的输入数据和权重都被量化为16bit。将CiFar-10 数据集和 2012 年 ImageNet 大规模视觉识别挑战赛（ImageNet LargeScale Visual Recognition Challenge，ILSVRC）的验证集作为实验的测试数据集。

# 5.2性能评估

实验中对以下几方面进行评估。

a）评估属性。对设计生成的加速器进行评估，分析几种网络的处理性能、能耗和能效等。b）评估对象。展示生成的系统性能，并将其分别与软件实现和其他已有设计的各项性能进行比较分析。

# 5.3 结果与分析

a）首先评估针对这几个网络模型设计生成的加速器性能。

通过测量在云端FPGA平台实现中运行网络推理的处理时间来衡量整体性能。通过分析网络参数，表1中测量并报告了各网络模型的加速器参数设置和性能。

![](images/279e504d9064ffe34875f4e4f0f890251dd5dfff02b536de1f2f471a1067776f.jpg)  
图11控制流调度优化  
Fig.11Scheduling optimization of Control flow

Table 1Accelerator configuration and performance of network models   

<html><body><table><tr><td rowspan="2">网络模型</td><td rowspan="2">数据类型</td><td colspan="2">加速器配置</td></tr><tr><td>（Tm,Tn,Tr,Tc,I_BUF)</td><td>时间（ms/image）</td></tr><tr><td>Cifar</td><td>float</td><td>32,32,4,4,5</td><td>0.42</td></tr><tr><td>AlexNet</td><td>float</td><td>133,10,4,4,19</td><td>28.6</td></tr><tr><td>VGG-16</td><td>float</td><td>64,19,4,4,32</td><td>224.85</td></tr></table></body></html>

b)将本文实现的网络模型的性能与其纯软件版本进行比较。结果如表2所示。所有网络模型的加速都将CPU实现测得的延迟数据作为GPU和FPGA系统的基线来展示加速比。GPU和FPGA的能耗和能效也与CPU进行比较。

由表2可见，对于小型网络，CPU可以实现与GPU相当的性能。但是，利用架构的灵活性，FPGA可以优于CPU 和GPU。与CPU实现相比，该设计实现AlexNet达到8.48倍的加速，而实现Cifar的功耗仅为其 $2 4 . 9 6 \%$ ；相较于CPU+GPU实现对Cifar6.90倍的加速，虽然实现较大规模网络的性能不及GPU，但功耗最小仅为其 $1 4 . 9 8 \%$ 。据此分析得知，相比于CPU实现，得益于FPGA较高的并行执行能力，生成的系统在性能和能效方面总是更佳；与GPU实现相比，即使本文设计生成的加速器系统性能达不到GPU的性能峰值，也仍然能利用FPGA的高计算密度优势提高能效，表现出较高的能耗优势。

c)将本文实现的网络模型的性能与已发表的研究成果进行比较。结果展示在表3中。

表1各网络模型的加速器配置和性能  
表2与其纯软件版本比较结果  
表3与已有工作比较结果  

<html><body><table><tr><td>平台</td><td colspan="3">CPU</td><td colspan="3">CPU+GPU</td><td colspan="3">本文（CPU+FPGA）</td></tr><tr><td>设备</td><td></td><td colspan="2">E5-2430</td><td colspan="3">E5-2609 +K80</td><td colspan="3">AWS F1</td></tr><tr><td>网络模型</td><td>Cifar</td><td>AlexNet</td><td>VGG-16</td><td>Cifar</td><td>AlexNet</td><td>VGG-16</td><td>Cifar</td><td>AlexNet</td><td>VGG-16</td></tr><tr><td>数据类型</td><td></td><td>float</td><td></td><td></td><td>float16</td><td></td><td></td><td>float</td><td></td></tr><tr><td>时钟（MHz)</td><td></td><td colspan="2">1.9GHz</td><td></td><td colspan="2">1GHz</td><td colspan="3">125MHz</td></tr><tr><td>能耗（Watt）</td><td></td><td>150</td><td></td><td></td><td>250</td><td></td><td>37.447</td><td>42.41</td><td>40.432</td></tr><tr><td>延迟/图（ms）</td><td>2.4065</td><td>242.562</td><td>794.238</td><td>2.8979</td><td>5.0486</td><td>25.7583</td><td>0.42</td><td>28.6</td><td>224.85</td></tr><tr><td>加速比（×）</td><td>1</td><td>1</td><td>1</td><td>0.83</td><td>48.05</td><td>30.83</td><td>5.73</td><td>8.48</td><td>3.61</td></tr><tr><td>能效</td><td>1</td><td>1</td><td>1</td><td>0.4034</td><td>28.203</td><td>16.95</td><td>17.292</td><td>28.6</td><td>12.11</td></tr></table></body></html>

Table 2Compare results with its software version   
Table3Compare results with the existed methods   

<html><body><table><tr><td>设计来源</td><td>文献[27]</td><td>文献[28]</td><td>文献[28]</td><td>文献[29]</td><td>本文</td></tr><tr><td>平台</td><td>VX690T</td><td>Arria 10</td><td>Stratix V</td><td>Stratix V</td><td>VU118</td></tr><tr><td>网络模型</td><td>VGG-16</td><td>VGG-16</td><td>VGG-16</td><td>VGG-16</td><td>VGG-16</td></tr><tr><td>数据类型</td><td>fixed16</td><td>fixed16</td><td>fixed16</td><td>fixed8-16</td><td>fixed16</td></tr><tr><td>时钟（MHz)</td><td>150</td><td>200</td><td>150</td><td>120</td><td>125</td></tr><tr><td>DSP 利用率（%)</td><td>78.7</td><td>100</td><td>100</td><td>37</td><td>88.47</td></tr><tr><td>能耗（Watt）</td><td>26</td><td></td><td></td><td></td><td>42.241</td></tr><tr><td>延迟/图（ms）</td><td>65.13</td><td>65.13</td><td>87.87</td><td>262.9</td><td>59.9 (41.77)</td></tr></table></body></html>

本文设计生成的加速器系统，在每张图像处理延迟和能源效率方面与其他已有工作相当甚至更有优势。相较于已有工作，最大达到6.29倍的加速比。与在较小平台上设计的加速器相比[27]，本文设计生成的加速器系统充分利用片上资源实现了更好的性能。其中与大平台生成的加速器相比[28-29]，本文设计生成的系统具有相当或更佳的性能，即使仅达到相当的性能，但具有更低的时钟频率。

# 6 结束语

本文根据卷积神经网络计算模式高度重复的流水线和并行性的特点，提出一种面向云端FPGA的卷积神经网络加速器的设计及其调度机制。实验结果表明，该加速器可在有效提高运算速度的同时减小功耗。对Cifar、AlexNet、VGG-16等网络模型采用本文设计系统实现的评估结果表现出与已有工作相当或更佳的性能，并且与CPU和GPU相比，在云端FPGA上的功耗及性能均表现出较大优势。

未来工作中，还将探索多种加速器之间拆分推理的设计可能性。本文已有的工作采用模块化设计，系统可拓展性较高，各种新型计算类型可轻松集成到设计中。未来将进一步扩展笔者的设计以支持新功能，并为CNN的FPGA映射提供更多的自适应解决方案。

# 参考文献：

[1]周飞燕，金林鹏，董军．卷积神经网络研究综述[J].计算机学报,2017, 40 (6):1229-1251.(Zhou Feiyan,Jin Linpeng,Dong Jun.Review of convolutional neural network[J].Chinese Journal of Computers,2017,40 (6): 1229-1251)   
[2]Krizhevsky A,Sutskever I,Hinton G E.Imagenet classification with deep convolutional neural networks [C]// Advances in Neural Information Processing Systems.New York:ACMPress,2012:1097-1105.   
[3]Saxena S,Verbeek J.Heterogeneous face recognition with CNNs [C]// Proc of the European Conference on Computer Vision. Berlin: Springer Press, 2016:483-491.   
[4]Ji Shuiwang,Xu Wei, Yang Ming,et al.3D convolutional neural networks for automatic human action recognition: USA, US8345984 [P/OL].(2010- 06-11) [2013-01-01].http://www.google.com/patents/US8345984.   
[5]Shao Hong,Chen Shuang,Zhao Jieyi,et al. Face recognition based on subset selection via metric learning on manifold[J].Frontiers of Information Technology& Electronic Engineering,2015,16(12):1046-1058.   
[6]Levi G,Hassncer T.Age and gender classification using convolutional neural networks [C]//Proc of Computer Vision and Pattern Recognition Workshops.Piscataway,NJ:IEEE Press,2015:34-42.   
[7]Peemen M,Mesman B,and Corporaal H. Speed sign detection and recognition by convolutional neural networks [C]// Proc of the 8th International Automotive Congress.2011:162-170.

[8]Lee W Y,Park S M,Jang IH,et al.CNN-based shoe-upper patern

recognition and generation of adhesive point [J].Journal of Institute of Control Robotics & Systems,2017,23 (9): 725-731.   
[9]蔡慧苹，王丽丹，段书凯．基于word embedding 和CNN的情感分类模 型[J].计算机应用研究,2016,33(10):2902-2905.(Cai Huiping,Wang Lidan,Duan Shukai.Sentiment classification model based on word embedding and CNN[J].Application Research ofComputers,2016,33 (10): 2902-2905.)   
[10]SankaradasM,Jakkula V,Cadambi S,etal.Amassivelyparallelcoprocessor forconvolutional neural networks [C]//Proc of IEEE International Conference on Application-Specific Systems,Architecturesand Processors. Piscataway,NJ: IEEE Press,2009:53-60.   
[11]Potluri S,Fasih A, Vutukuru L K,et al. CNN based high performance computing for real time image processing on GPU[C]//Proc of Workshop on Nonlinear Dynamics & Synchronization& Intl Symposium on Theoretical Electrical Engineering. Berlin: Springer Press,2011:1-7.   
[12] Zhang Chen,Li Peng,Sun Guangyu,et al.Optimizing FPGA-based accelerator design for deep convolutional neural networks[C]//Proc of ACM/SIGDA International Symposium on Field-Programmable Gate Arrays. New York: ACMPress,2015:161-170.   
[13] Cadambi S,Majumdar A,Becchi M,et al.A programmable parallel acceleratorforlearningand classification [C]//Proc of International Conference on Parallel Architectures and Compilation Techniques.New York: ACM Press,2010: 273-284.   
[14] Wei Xuechao, Yu Codyhao, Zhang Peng,et al. Automated systolic array architecture synthesis for high throughput CNN inferenceon FPGAs [C]/ Proc ofDesign Automation Conference.ACM,New York:ACMPress,2017: 29.   
[15]Farrens M,Chong FT, Oskin M.HLS: combining statistical and symbolic simulation to guide microprocessor designs[C]//Proc of International Symposium on Computer Architecture. New York: ACMPress,2000: 71-82.   
[16]StriglD,KoflerK,Podlipnig S.Performanceand scalability ofGPU-based convolutional neural networks [C]// Proc of Euromicro International Conference on Parallel，Distributedand Network-Based Processing. Piscataway,NJ: IEEE Press,2010:317-324.   
[17]Ferry C.Hardware accelerated convolutionalneural networks for synthetic vision systems [C]/ Proc of IEEE International Symposium on Circuits and Systems.Piscataway,NJ: IEEE Press,2010:257-260   
[18]Savich A W, Mouss M,Areibi S.The impact of arithmetic representation on implementing MLP-BP on FPGAs: A study[J]. IEEE Trans on Neural Networks,2007,18(1):240-252.   
[19]Peemen M M, Mesman B B,Corporaal H H. Optimal iteration scheduling for intra-and inter-tile reuse in nested loop accelerators [D].Eindhoven: Eindhoven UniversityofTechnology,2013.   
[20]Peemen M, Setio AAA,Mesman B,et al. Memory-centric accelerator design for convolutional neural networks [C]// Proc of IEEE,International Conference on Computer Design. Piscataway,NJ: IEEE Press,2013:13-19.   
[21]Williams S,Waterman A,Patterson D.Roofline:An insightful visual performance model for floating-point programs and multicore architectures [J].Office of Scientific & Technical Information Technical Reports,2009, 52 (4): 65-76.   
[22]Motamedi M,GyselP,Akella V,et al.Design space explorationof FPGAbased deep convolutional neural networks [C]//Proc of Design Automation Conference.Piscataway,NJ:IEEE Press,2016:575-580.   
[23] Gokhale V,Jin Jonghoon,Dundar A,et al.A240 G-ops/s mobile coprocessor for deep neural networks [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition Workshops.Piscataway,NJ:IEEE Press,2014: 696-701.   
[24]Baklouti M,Ammar M,MarquetP,et al.A model-driven based framework forrapid parallel SoC FPGA prototyping.[J].Journal of Biological Chemistry,2011,272 (12): 7797-800.   
[25] Jia Yangqing，Shelhamer E,Donahue J,et al.Caffe:Convolutional architecture for fast feature embedding[C]//Proc of ACM International ConferenceonMultimedia.New York:ACMPress,2014:675-678.   
[26] Gysel P,Motamedi M,Ghiasi S.Hardware-oriented approximation of convolutional neural networks [J].arXiv preprint arXiv:1604.O3168,2016.   
[27] Zhang Chen，Fang Zhenman,Zhou Peipei,et al. Caffeine: towards uniformed representation and acceleration for deep convolutional neural networks [C]//Proc of International Conference on Computer-Aided Design. NewYork:ACMPress,2016:12.   
[28]Ma Yufei,Cao Yu,Vrudhula S,etal.An automatic RTL compiler for highthroughput FPGA implementation of diverse deep convolutional neural networks [C]// Proc of International Conference on Field Programmable Logic and Applications.Piscataway,NJ:IEEE Press,2O17:1-8.   
[29] Qiu Jiantao,Wang Jie,Yao Song,et al.Going deeper with embedded FPGA platform for convolutional neural network [C]// Proc of ACM//SIGDA International Symposium on Field-Programmable Gate Arrays.New York: ACMPress,2016:26-35