# 基于 $\mathsf { A R M + F P G A }$ 平台的二值神经网络加速方法研究

孙孝辉'，宋庆增1，金光浩1+，姜文超²(1．天津工业大学 计算机科学与软件学院，天津 300387;2.广东工业大学 计算机学院，广州 510006)

摘要：目前，现有的卷积神经网络由于其结构复杂且依赖的数据集庞大，难以满足某些实际应用或者计算平台对运算性能的要求和能耗的限制。针对这些应用或计算平台，对基于ARM+FPGA平台的二值化算法进行了研究，并设计了二值神经网络，该网络减少了数据对存储单元的需求量，也降低了运算的复杂度。在 $\mathbf { A R M + F P G A }$ 平台内部实现时，通过将卷积的乘累加运算转换为 XNOR 逻辑运算和popcount 等操作，提高了整体的运算效率，降低了对能源和资源的消耗。同时，根据二值神经网络中数据存储的特点，提出了新的行处理改进算法，提高了网络的吞吐量。总之，该实现方式在GOPS、能源和资源效率方面均优于现有的FPGA神经网络加速方法。

关键词：二值神经网络；现场可编程门阵列；异或运算；行处理算法 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2018.08.0614

Research of binary neural network acceleration method based on ARM $+$ FPGAplatform

Sun Xioahui1, Song Qingzeng1, Jin Guanghao1+, Jiang Wenchao² (1.SchoolofComputerScience&SoftwareEngineering,njinPolytechnicUniversityanjin3o387,China;2.ool of Computers,Guangdong University of Technology, Guangzhou 51ooo6, China)

Abstract:At present,theexistingconvolutional neural network has complicated structureand bases on huge dataset.So it has difficulties in meeting the requirement ofcomputing performance and limitationof energy consumption requested by some practical applications or computing platforms.This papaer studied the binary algorithm based on $\mathbf { A R M + }$ FPGA platformand designeda binary neural network aiming at these appications or platforms.This work reduces the demand for data storage units and simplifies the computational complexity.When implemented in the $\mathbf { A R M + }$ FPGA platform,the convolution multiply-accumulate operation is converted into XNOR logic and popcount operation，which improves the overalloperation eficiency and declines theconsumption of energy and resources.At the same time,based on the characteristicsof datastorage in binary neural network,a new row processing algorithm is proposed to improve the throughputof the network.Inaword,This implementation is superior totheexistingFPGAneural network acceleration methods in terms of GOPS,energy and resource effciency.

Key words: binary neural network; ARM+FPGA; XNOR; row-processing algorithm

# 0 引言

卷积神经网络(convolutional neural networks,CNN)是当前最为重要的深度学习算法之一，被广泛应用于计算机视觉[1]、机器翻译[2]、语音识别[3]、人脸检测[4]等领域，都取得了非常好的效果。随着CNN及其改进算法的进一步发展，对运算平台的存储容量和计算能力也提出了较高的要求，这就限制了CNN 等算法在功耗和性能受限的嵌入式平台上的发展。因此，很多研究人员开始提出各种模型压缩算法和技术[5\~7]，即在容忍一定的精度下降的代价下，降低CNN 的运算强度和模型参数的容量。其中，最重要的模型压缩方法之一是用低精度的定点数代替高精度的浮点数，比如8bit定点数代替32bit的浮点数，这种方法能将参数的存储需求降低到原来的四分之一。极端的情况是将32bit浮点数压缩为二值的定点数（1bit)，即所谓的二值神经网络（binaryneuralnetwork,BNN）[6]。相对于传统CNN，BNN这些方法不仅极大地减少了对内存容量的需求，也改变了传统卷积的计算方

式，降低了运算的复杂度。

二值神经网络非常适合在ARM $+$ FPGA的架构实现。当对参数和特征图进行二值化之后，乘累加操作可以被更简单的异或逻辑(XOR)和按位计数(popcount)所代替，对FPGA资源的消耗将大大降低。针对BNN，可以在FPGA上设计特殊的流水结构，进一步加速BNN网络的运算速度。与此同时，BNN网络中并不适合FPGA加速的部分可以在ARM上运行，保证了实现的灵活性。本文主要研究BNN如何在ARM+FPGA架构的设计与实现。主要工作如下：针对Cifar-100 数据集，在ARM+FPGA的硬件平台上设计和实现了BNN加速器；加速器采用HLS[8设计方法，具有更高的灵活性，同时也缩短了开发周期；分别在不同的开发板上进行了测试，并与其他平台在速度、精度和功耗做了对比，实验结果表明本文实现的加速器具备较大的优势。

# 1 相关工作

基于FPGA的卷积神经网络的加速优化措施中，可以通过将网络中的卷积运算转换为运算效率更高的矩阵乘矩阵操作，其中主要的转换算法包括GEMM变换[9和Winograd变换[10]，此外还可以通过快速傅里叶变换[1将时域的卷积转换为频域的乘积来进行优化。除了对网络中的运算进行优化之外，还可以通过阵列的收缩[12]、SIMD[13]、循环优化[14,15]和设计空间探索[16]等方法来优化网络中数据的传输路径，减小数据之间传输的延迟。

表1神经网络模型  
Table1Neural network model   

<html><body><table><tr><td>模型结构</td><td>Conv1</td><td>Conv2</td><td>Pool</td><td>Conv3</td><td>Conv4</td><td>Pool</td><td>Conv5</td><td>Conv6</td><td>Pool</td><td>FC1</td><td>FC2</td><td>FC3</td></tr><tr><td>输入特征图</td><td>3</td><td>128</td><td>128</td><td>128</td><td>256</td><td>256</td><td>256</td><td>512</td><td>512</td><td>8192</td><td>1024</td><td>1024</td></tr><tr><td>输出特征图</td><td>128</td><td>128</td><td>128</td><td>256</td><td>256</td><td>256</td><td>512</td><td>512</td><td>512</td><td>1024</td><td>1024</td><td>100</td></tr><tr><td>特征图维度</td><td>32</td><td>32</td><td>16</td><td>16</td><td>16</td><td>8</td><td>8</td><td>8</td><td>4</td><td>1</td><td>1</td><td>1</td></tr><tr><td>BN参数量</td><td>512</td><td>512</td><td></td><td>1024</td><td>1024</td><td></td><td>2048</td><td>2048</td><td></td><td>4096</td><td>4096</td><td>400</td></tr><tr><td>输出所占内存</td><td>128K</td><td>128K</td><td>32K</td><td>64K</td><td>64K</td><td>16K</td><td>32K</td><td>32K</td><td>8192</td><td>1024</td><td>1024</td><td>100</td></tr><tr><td>权重所占内存</td><td>3456</td><td>144K</td><td></td><td>288K</td><td>576K</td><td></td><td>1.1M</td><td>2.3M</td><td></td><td>8.0M</td><td>1.0M</td><td>100K</td></tr></table></body></html>

对卷积神经网络加速除了计算变换和数据路径优化外，还可以对网络的权重进行裁剪[17]，增加模型的稀疏性，减少网络的运算次数。同时网络中的卷积核可以通过低秩近似[18]的方法，来减少推断过程中乘法的数量，这些方法通过减少网络的运算量达到了优化的效果。

除了上述的优化方法外，在FPGA实现上还可以使用包括定点算法[19]、动态定点算法[20]、二值量化[5,21,22]、伪二值量化[23,24]以及随机计算[25]等近似计算的方法来减少数据的精度来加速网络的运算。这些方法不仅降低了网络中运算的复杂度，还能充分发挥FPGA定点计算的潜能。

# 2 二值神经网络

# 2.1网络结构

二值神经网络是一种对CNN 网络模型进行压缩的实现方法，即将网络中的权重参数和特征图进行了二值化。最初的想法是将权重参数二值化[5]，减少参数的存储量，而后[]进一步对网络中的特征图也作了压缩处理，在减少存储量的同时也降低了计算的复杂度，并对训练二值神经网络过程中的反向传播问题给出了解决方案。二值神经网络中的二值化是指将权重和激活函数二值化到 $+ 1$ 和-1 的实现。在文献[5]中提出了两种算法，分别是随机性和确定性二值化方法。尽管随机性二值化比确定性二值化更符合实际情况，但在量化时要生成随机位，不利于硬件化实现。因此本文使用了如下的确定性二值化方法：

$$
x ^ { b } = s i g n ( x ) = \bigl \{ { + 1 \atop - 1 } \quad \stackrel { i f \ x \geq 0 } { o t h e r w i s e }
$$

其中: $x ^ { b }$ 表示二值化之后的数据(权重/特征图)； $\textbf { \em x }$ 是原始值。

二值神经网络中为了减少在网络传输过程中由二值化运算带来的分布信息丢失问题，在网络结构中添加了一个新的层次结构，即批归一化(batch normalization,BN)[26]，其运算表达式为

$$
y = \frac { x - \mu } { \sqrt { \sigma ^ { 2 } + \varepsilon } } \gamma + \beta
$$

其中：x、y分别表示数据的输入和输出； $\mu$ 和o2是每个特征图的平均值和方差值； $\gamma$ 和β是网络训练得到的参数；E是一个很小的数值保证运算时分母不为零。批归一化层在保证原始数据分布信息稳定性的同时，也加速了网络的训练过程。在网络模型进行推断的过程中，所有的参数都是固定的，所以在实现的过程中，只需关心将式(2)应用到每一个输入的特征图的像素上，而且每个特征图都有唯一对应的批量归一化参数。

BNN与CNN的网络结构定义如图1所示。图1中CNN网络的层次顺序结构为卷积层、偏移层、池化层和激活函数层。其中输入和输出的数据都是实数类型；而BNN网络去掉了偏移层，在卷积层之后直接池化，而且为了减少特征图分布信息的丢失，在池化之后添加了BN层，除了第一层的输入数据外，每层经过二值激活函数之后输入和输出数据都是二值的。

![](images/2790ebe3338e048a8d831058f3945d81327cff1fb93ca89d96758ab7d8d6b395.jpg)  
图1CNN 与BNN的网络结构比较  
Fig.1 Comparison of CNN and BNN

# 2.2网络模型

本文设计的二值神经网络模型包括有六个卷积层和三个全连接层。每个卷积层和全连接层之后都有BN层和激活层，而池化层是每两个卷积层之后添加一个，也就是在第2层、第4层、第6层卷积之后有一个池化层。卷积层中卷积核的大小为 $3 \times 3$ ，池化层中设置采样器的大小为 $2 \times 2$ ，步长为2，对特征图数据取最大值。其中第一层卷积输入的数据为图片的原始数据是浮点类型，这与其余层的数据类型不一样，而每层的权重参数都是二值的。每层的详细参数设置如表1所示。其中Conv表示卷积层，FC(fullconnect)表示全连接层。表1中根据网络结构分别设置了每层特征图的输入和输出个数，并分别计算了每层的输出和权重所占内存大小，每个数据按照1bit存储来计算。BN层经过训练之后得到的参数都是浮点类型的数据，经过对卷积之后的数据处理之后得到了中间的浮点型数据，最后经过激活函数将中间的计算结果转换为输出的二值化数据。

# 2.3模型训练

本文使用Theano 和Lasagne 的深度学习框架[6]，实现表1定义的网络模型。模型中使用cifar- $1 0 0 ^ { [ 2 7 ] }$ 数据集进行训练和验证，数据集包括有6万张 $3 2 \times 3 2$ 大小的3通道RGB图像，其中包括真实世界中的鸟类、猫、飞机、汽车、青蛙等，每个照片的像素值由0\~255的整数表示。这些图片被分成了50000张训练数据和10000张测试数据，每个数据集都包括100个类别，这100个类别又被细分成了20个大类，每个图像都带有1个小类的标签和1个大类的标签。

二值神经网络模型中使用了指数衰减学习率，用ADAM方法来最小化铰链损失，数据的批大小设置为50，并使用批归一化来加速训练。实验使用训练集中最后的5000个样本作为验证集，训练了500个周期，最后的识别结果如表2所示。最终网络中总的权重大小为 $1 3 . 3 7 \mathrm { M }$ ，其中包括卷积层$4 . 3 6 \mathrm { M }$ ，全连接层 $9 . 0 1 \mathrm { ~ M ~ }$ 。

# 3 FPGA实现

# 3.1软硬件划分

基于ARM+FPGA架构的设计相较于传统的FPGA设计模式，不仅能够缩短开发的周期，而且在设计过程中也可以将性能、集成度和灵活性等因素考虑进来，这不仅降低了成本和功耗，还增强了特性和性能。

本文在针对ARM $^ +$ FPGA架构设计神经网络的前向推断过程时，由于主要的运算阶段在卷积和全连接两部分，为了让平台中各部分发挥出各自最佳的性能，在软硬件划分时，在FPGA内部实现主要的网络运算过程，在ARM处理器上对输入图片和每层参数进行预加载和分配，并对FPGA的初始阶段进行控制。系统的软硬件划分如图2所示。硬件逻辑部分主要由计算单元、片内存储器、DMA和有限状态机控制器组成，系统处理部分主要包括CPU、内存控制器等。

硬件逻辑部分DMA主要用来在运算阶段预加载权重数据到片内存储器中，并将最终的预测结果写回片外存储器。片内存储器主要用来存储计算单元运算之后的结果数据，并将DMA读取的数据保存下来。计算单元内部主要是将输入的数据和权重在运算时通过使用一些优化措施，加快网络的运算过程，并输出网络最终的预测结果。

![](images/4b89bcb4e6ca87a01fce2d05de227ca1650b675944e5e3e2ba2438889a2a43af.jpg)  
图2加速器系统架构

系统处理部分首先将片外存储器中存储的输入特征图和每层的参数数据读入内存之中，按照每层的超参量对参数进行分配，再将分配好的数据和控制信息传输到FPGA内部的存储器中。从表1可知，特征图和权重分别占据了不同的内存比重，在FPGA内部仅仅是保存这些参数，就会消耗很大一部分存储资源。为了最大化地利用存储资源，同时保证系统最佳的性能表现，对FPGA器内部计算过程中产生的中间数据的存储部分作了一些改进，详细的介绍将在4.2节给出。使用这种方法系统处理部分就可以按照网络层执行的顺序，依次将特征图和参数数据全部或者部分传输到FPGA的片内存储器上，保证数据的传输效率。

# 3.2硬件设计

根据软硬件划分的结果，针对网络处理的数据类型和运算量的不同，在计算单元内部分成了三个主要的模块来分别处理卷积和全连接，即定点卷积计算模块、二值卷积计算模块和全连接计算模块。每个模块按照网络的层次结构来处理相应的特征图数据，并产生最终的预测结果。

定点卷积计算模块主要用来处理第一层输入的原始图片数据，在该模块内部通过线性缓冲器来接收输入的3通道$3 2 \mathrm { x } 3 2$ 大小的图片，然后将对应的像素值转换成20位的定点数据。由于输入的权重是二值的，计算过程中使用符号的反转来代替卷积中的乘法。本文方法对这三个通道数据采取完全并行的处理方式，将输入的数据添加到三个缓冲区中，每个循环卷积核在缓冲区中流动，并计算一个3x3x3的卷积，其结果通过批归一化和二值化，每循环产生一个输出位。由于第一层卷积占用了很少的运行时间，所以并没有用过多的硬件资源来进行加速。

二值卷积计算模块是计算单元里最重要的组成部分，它用来处理其余的二值卷积层，占据了系统大部分的运行时间。因此该计算模块在处理不同尺寸的输入特征图时，也必须保持高吞吐量和高效的资源利用率。为了在模块内部更有效地进行卷积操作，需要对多行输入数据进行缓冲，以便同时进行访问。但标准的行缓冲器每个周期只能存储单行数据，且只能处理固定缓冲区长度的数据，当输入数据的宽度小于缓冲区的宽度时，就会造成缓冲区利用率不足，导致吞吐量损失。因此，为了能充分利用硬件资源，并解决行缓冲的问题，本文方法设计了可变宽度的行缓冲器，如图3所示。可变行缓冲器相较于普通的缓冲器解决了硬件资源利用率不足的问题，并且每个周期可以输出并缓存一行新的特征图数据。在二值卷积计算的过程中，首先从片上存储器读取输入特征图，根据特征图的宽度将数据进行重新组织排序；然后加载到行缓冲器中，卷积模块通过在行缓冲器上滑动产生运算结果，并将它们的累加和输出到缓冲区中，作为下次卷积的输入。

全连接模块执行最后的全连接计算并返回预测的结果，该模块在执行时通过循环展开将特征图数据与权重数据按位执行 XNOR 运算，然后使用 popcount 对结果位求和。与二值计算模块对中间数据处理的方式类似，都是在缓冲区对卷积结果求累加和，并在处理完所有的输入后应用二值化，输出最终的结果。

硬件逻辑部分的片内存储器，由于要同时保存上、下两层之间的输出特征图，本文在设计时根据表1中每层的最大参数量，实现了两个内存大小为 $1 2 8 \mathrm { ~ K ~ }$ 的缓冲器来保存中的运算结果，并对缓存里的数据采取轮转访问的形式，充分利用内存资源，减少片内外数据的传输。

![](images/b5216b66899f6ca0a4e4063bfff7bfc546c347fb23c14d5c65aa3d04c2e1a88a.jpg)  
Fig.2Architectural diagrams of accelerator   
图3宽度可调行缓冲器  
Fig.3 Variable-widthline buffer

# 3.3软硬件接口

本文使用XilinxSDSoC作为BNN应用的主要设计工具，在BNN加速器的软硬件划分中，软件部分主要来控制整个程序的运行和读取片外存储器里的数据到内存中，在硬件部分主要进行大量的并行计算任务。由于权重和特征图在硬件部分存放和读取的方式不同，在接口实现时采用了折中的方案。

首先，为了减少运算过程中软硬件之间频繁的数据访问，将系统处理部分的数据通过值传递的方式传输到硬件存储器内部，相较于址传递的访问形式，虽然占用了一些内存空间，但节省了交互的时间开销。

为了保证数据传输的高效性，权重数据需要保存在一段连续的物理内存空间里，并通过FIFO 流来接收数据。这种数据接收方式更符合权重数据每层依次读取的特性。将对应接口的数据传输方式确定之后，SDSoC会生成组件单元，组件的两端分别对应PS和加速器，中间的控制器就是设定的数据移动方式。

最终通过调用SDSoC将软件程序中标记为硬件实现的$\mathrm { C / C } { + } { + }$ 代码部分综合成硬件的RTL实现，并通过指定的接口指令生成PS与PL内存之间的数据传输模块和所需的DMA模块。同时在程序中确保产生的中间数据存放在片内存储器上，并且通过连续排列神经网络的数据和权重，保证网络的吞吐量，而片外数据的传输只在第一次和最后一次调用计算单元和加载权重时产生。

# 4 实验

实验选择在ZedBoard和ZCU102上评估本文的设计，其中ZedBoard代表了一个低成本的XilinxZynq ${ \cdot } 7 0 0 0 \mathrm { \ : { S o C } }$ 包含7Z020 型号的FPGA以及双核ARMCorteX-A9嵌入式处理器，ZCU102 作为一个高端的 Zynq UltraScale+ MPSoC 包含ZU9EG型号的FPGA以及四核ARMCortex-A53、双核ARMCortex-R5和图形处理单元的嵌入式处理器。

本文使用XilinxSDSoC2017.4作为主要的设计工具，利用Vivado HLS和Vivado 将 $\mathrm { C / C } { + + }$ 的代码，编译成FPGA运行的格式。图2中的系统结构中的CPU分别对应于ZedBoard和ZCU102器件中的Cortex-A9嵌入式处理器和Cortex-A53处理器，硬件逻辑中的计算单元主要是基于FPGA内部的LUT进行实现，并在每个计算单元内部分别调用了不同的可配置逻辑块和输入输出单元，而片内存储器分别对应于BRAM、FIFO、RAM等缓冲存储资源。

本文在实现过程中，将计算单元中的三个卷积计算函数分别进行了封装，对应网络整体的推断过程，根据每层所处的运算关系，调用相应的函数，函数处理之后的数据之间的传输是在片内存储器上进行的，存储器上存储着每层运算的特征图结果，整体网络的运算逻辑通过SDSOC进行综合实现之后，生成对应的FPGA上的硬件逻辑结构。

本文将实现的设计还与两个服务器级的计算平台和一个嵌入式平台进行了比较：一个IntelXeonE5-2640多核处理器(CPU)，一个NVIDIA Tesla K80 (GPU)和嵌入式NVIDIAJetsonTX2(mGPU)。CPU和GPU的基准线根中提供的代码进行调整，在运算过程中分别调用各自的优化库来进行运算加速。

在运行BNN时，器件的功率是通过功率监视器获得的，ZedBoard和ZCU102上的空闲功率分别为 $\phantom { - } 4 . 4 \ : \mathrm { W }$ 、23.4W，系统运行时的最大功率分别为4.7W、23.6W，这表明FPGA在运行过程中的动态功耗还是非常低的。其中吞吐量(giga-opera-tions-per-second,GOPS)计算总的加法与乘运算量，在 BNN中将每个二进制的异或、翻转和加法分别作为一个运算操作。

# 4.1精度分析

二值神经网络模型中的一个复杂因素是二值化数据参与卷积运算时与边缘填充之间的相互作用。二值神经网络将每个激活值二值化为-1或 $+ 1$ ，但每个输入特征图都用零填充边缘，这意味着卷积可以看到最多三个值：-1、0、 $^ { + 1 }$ 。而

Ternary- $\cdot \mathrm { N N } ^ { [ 2 4 ] }$ 网络就是考虑了这种情况，将激活函数的值分成了三部分，相较于二值数据，就不再考虑边缘填充带来的影响。而二值神经网络针对三个值在存储时可能就需要两个数据位来保存运算符。本文使用 $+ 1$ 的填充方式来重新训练网络，消除了零点并建立了一个真正的二值化CNN。这个 $^ { + 1 }$ 填充的BNN在训练时实现了 $5 8 . 7 4 \%$ 的准确率，在 $\mathrm { C / C } { + } { + }$ 的FPGA中实现了 $5 7 . 2 4 \%$ 的准确率，仅比原来的稍差。对于FPGA实现，使用 $+ 1$ 填充更符合本文的网络设计，考虑到硬件资源的节约，还是采取0填充的方式。表2比较了对相同的测试数据集Cifar-100，网络模型的测试结果。

# 4.2性能分析

本文的实验将加速器整体的性能与表3中的各种基准线进行了比较，由于原始吞吐量在很大程度上受限于设备尺寸，还比较了功耗和每瓦吞吐量。与mGPU相比两款FPGA的运行时间性能分别提升了8.和29.5倍，每瓦的吞吐量比mGPU分别高了14.1和9.4倍。与 $\mathbf { x } 8 6$ 处理器上相比也分别取得了2倍和6.7倍的加速效果。而与GPU相比，两款设计在性能上分别相差了18.6和5.5倍。但正如预期的一样，它们的功耗要低得多，每瓦的吞吐量也要高很多。其中Conv1表示第一层的卷积，Conv2-5表示的二值卷积层，FC1-3是最后的全连接层，最后一行显示了各平台每瓦的效率。

Table 2Network model test results in Cifar-100   

<html><body><table><tr><td></td><td>模型结构</td><td>边缘填充</td><td>识别准确度</td></tr><tr><td>Ternary-NN[24]</td><td>6Conv+2FC+SVM</td><td>0</td><td>51.6%</td></tr><tr><td>BNN (python)</td><td>6Conv+2FC+Softmax</td><td>0</td><td>60%</td></tr><tr><td>BNN (python)</td><td>-</td><td>+1</td><td>58.74%</td></tr><tr><td>BNN(C++/FPGA)</td><td></td><td>0</td><td>57.24%</td></tr></table></body></html>

表3计算平台性能比较

表2网络模型在Cifar-100 测试的结果  
Table 3Performance comparison of computing platforms   

<html><body><table><tr><td colspan="3">mGPU[6]CPU[6] GPU[6]</td><td rowspan="2">ZedBoard (this papaer)</td><td rowspan="2">ZCU102 (this papaer)</td></tr><tr><td></td><td></td><td></td></tr><tr><td>Conv1</td><td></td><td>0.63 0.002</td><td>0.088</td><td>0.026</td></tr><tr><td>Conv2-5</td><td></td><td>13.6 0.38</td><td>3.63</td><td>1.54</td></tr><tr><td>FC1-3</td><td>-</td><td>0.99 0.015</td><td>2.3</td><td>0.679</td></tr><tr><td>总运行时间</td><td>65</td><td>14.8 0.397</td><td>7.36</td><td>2.2</td></tr><tr><td>时间加速比</td><td>1.0x</td><td>4.4x 163.7x</td><td>8.8x</td><td>29.5x</td></tr><tr><td>功耗</td><td>7.5</td><td>95* 300</td><td>4.7</td><td>23.6</td></tr><tr><td>每瓦吞吐量</td><td>2.05</td><td>0.71 8.4</td><td>28.91</td><td>19.26</td></tr><tr><td>每瓦吞吐量</td><td>2.05</td><td>0.71 8.4</td><td>28.91</td><td>19.26</td></tr></table></body></html>

# 4.3功耗分析

由于BNN的相对新颖性，目前选定数据集Cifar-100，设计对应的加速网络，衡量消耗每个资源的吞吐量和每瓦特的吞吐量作为了比较的基准线。

表4比较了本文的实现与文献中发现的最前沿的FPGA加速器实现方案，表中的对应数字都是从对应的论文中检索得到。其中对比的平台有两个是相同的设备都为ZedBoard型号，另一个对比较大容量的FPGA。本文的BNN加速器在吞吐量方面超越了目前最好的FPGA加速器，并且也更加节省资源和能源。最终的数据结果也证明BNN在算法实现上比CNN更适合在FPGA上实现，它能更加有效地利用硬件资源。

# 5 结束语

本文设计了一种基于ARM $+$ FPGA的二值神经网络的加速器，完整地实现了针对Cifar-100数据集的网络前向传播过程。BNN网络对存储需求的减少和二值运算的特性，使其实现方式非常适合FPGA的组织结构，通过设计新的加速器架构，使得加速器在单位面积吞吐量和每瓦特的吞吐量方面都优于现有的全精度网络，大幅提升了运算效率。最近低精度的CNN的研究也一直在取得进展，并在ImageNet的数据集上取得了近乎最好的识别效果[7,24]。对未来低精度CNN的实现，仍需进一步探索缩小模型的算法并设计更大更复杂的加速器，以满足未来大计算量和实时性的需求。

表4神经网络FPGA加速器比较  
Table 4Comparison of FPGA based neural network accelerators   

<html><body><table><tr><td>平台</td><td>查找表容量</td><td>查找表</td><td>时钟</td><td>功耗</td><td>数据精度</td><td>GOPS</td><td>GOPS/kLUT</td><td>GOPS/Watt</td></tr><tr><td>Stratix-V-GSD8[28]</td><td>695</td><td>120</td><td>120</td><td>19.1</td><td>8-16b</td><td>117.8</td><td>0.98</td><td>6.17</td></tr><tr><td>Zynq-7Z045[29]</td><td>218.6</td><td>182.6</td><td>150</td><td>9.6</td><td>16b</td><td>137.0</td><td>0.75</td><td>14.3</td></tr><tr><td>Zynq-7Z020[30]</td><td>53.2</td><td>43.2</td><td>100</td><td></td><td></td><td>12.73</td><td>0.29</td><td>7.27</td></tr><tr><td>ZedBoard (this papaer)</td><td>53.2</td><td>38.71</td><td>143</td><td>4.7</td><td>1b</td><td>167.7</td><td>4.43</td><td>35.68</td></tr><tr><td>ZCU102 (this papaer)</td><td>274.08</td><td>132.95</td><td>300</td><td>23.6</td><td>1b</td><td>561.0</td><td>4.22</td><td>23.77</td></tr></table></body></html>

# 参考文献：

[1]Farabet C,Poulet C,Han J,et al.CNP:an FPGA-based processor for convolutional networks [C]// Proc of International Conference on Filed Programmable Logic and Application. Piscataway,NJ:IEEE Press, 2009: 32-37.   
[2]Devlin J, Zbib R,Huang Zhongqiang,et al.Fast and robust neural network joint models for statistical machine translation [C]// Proc of ACL Conference.2014:1370-1380.   
[3]Geoffrey H,Li Deng,Dong Yu,et al. Deep neural networks for acoustic modeling in speech recognition [J]. IEEE Signal Processing Magazine, 2012,29 (6): 82-97.   
[4]Garcia C,Delakis M. Convolutional face finder: a neural architecture for fast and robust face detection [J].IEEE Trans on Pattern Analysis and Machine Intelligence,2004,26 (11): 1408-1423.   
[5]Courbariaux M,Bengio Y,David JP. BinaryConnect: training deep neural networks with binary weights during propagations [C].Proc of the 28th International Conference on Neural Information Processing Systems.Cambridge,MA: MIT Press,2015: 3123-3131.   
[6]Courbariaux M,Bengio Y.Binarized neural networks: training deep neural networks with weights and activations constrained $^ { \mathrm { t o + 1 } }$ or-1 [J]. arXiv: 1602.02830v1,2016.   
[7]Hubara I, Courbariaux M, Bengio Y,et al. Quantized neural networks: training neural networks with low precision weights and activeations [J]. arXiv preprint arXiv: 1609.07061,2016.   
[8]Cong J,Bin Liu,Neuendorffer S,et al. High-level synthesis for fpgas: from prototyping to deployment [J]. IEEE Trans on Computer Aided Design of Integrated Circuits and Systems,2011,30 (4): 473-491.   
[9]Bottleson J,Sungye K,Andrews J,et al.ClCaffe:OpenCL accelerated caffe for convolutional neural networks [C]//Proc of IEEE International Parallel and Distributed Processing Symposium Workshops.2016: 50-57.   
[10] Andrew L,Gray S.Fast algorithms for convolutional neural networks [J].arXiv e-print,arXiv: 1509.09308.   
[11] JongHK,Mudassar B,Taesik N,et al.Design of an energyefficient accelerator for training of convolutional neural networks using frequency-domain computation [Cl// Proc of the 54th Annual Conference on Design Automation.2017.   
[12] Chakradhar S，Sankaradas M,Jakkula V,etal.A dynamically configurable coprocessor for convolutional neural networks [J].ACM SIGARCH Computer Architecture News,2010,38 (3):247-257.   
[13] Li Huimin,Fan Xitian,Jiao Li,et al.A high performance FPGA-based accelerator for large-scale convolutional nenral networks [Cl// Proc nf the 26th International Conference on Field Programmable Logic and Applications. 2016: 1-9.   
[14] Wei Xuechao,Yu C H, Zhang Peng,et al. Auto-mated systolic array architecture synthesis for high throughput CNN inference on FPGAs [C]// Proc of Annual Conference on Design Automation.2017:1-6.   
[15] Derrien S,Rajopadhye S.Loop tiling for reconfigurable accelerators [C]// Proc of International Conference on Field Programmable Logic and Applications. 2001: 398-408.   
[16] Williams S,Waterman A,Patterson D.Roof line: an insightful visual performance model for multicore architectures [J]. Communicat ions of the ACM,2009,52 (4): 65-76.   
[17] Han S,Pool J,Tran J,et al.Learning both weights and connections for efficient neural network [C]// Advances in Neural Information Processing Systems.2015: 1135-1143.   
[18] Sironi A,Tekin B,Rigamonti R,et al.Learning separable filters [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,2O15,37(1): 94-106.   
[19] Farabet C,Poulet C,LeCun Y,etal. CNP:an FPGA-based processor for convolutional networks [C]// Proc of International Conference on Field Programmable Logic and Applications.2009: 1689-1699.   
[20] Williamson D.Dynamically scaled fixed point arithmetic [C]// Proc of IEEE Pacific Rim Conference on Communications,Computers and Signal Processing Conference.1991: 315-318.   
[21] Rastegari M,Ordonez V,Redmon J,et al. XNOR-net:imagenet classification using binary convolutional neural networks [C]// Proc of European Conference on Computer Vision. 2016: 525-542.   
[22] Umuroglu Y,Nicholas JF,Gambardella G,et al.FINN: a framework for fast scalable binarized neural network inference [C]// Proc of ACM/SIGDA International Symposium on Fi eld Programmable Gate Arrays. 2017: 65-74.   
[23] Hubara I, Courbariaux M,Bengio Y. Binarized neural networks [C]// Advances in Neural Information Processing System.2016: 4107-4115.   
[24] Li Fengfu, Zhang Bo,Liu Bin.Ternary weight networks [J].arXiv e-print,arXiv: 1605. 04711,2016.   
[25] Ren Ao,Li, Zhe,Ding Caiwen,et al. SC-DCNN: highly-scalable deep convolutional neural network using stochastic computing [C]// Proc of International Conference on Architectural Support for Program ming Languages and Operating Systems. 2017: 405-418.   
[26] Ioffeand S, Szegedy C. Batch normalization: accelerating deep network training by reducing internal covariate shift [J].arXiv eprint,arXiv: 1502. 03167, 2015.   
[27] Krizhevsky,Hinton G. Learning multiple layers of features from tiny images [Dl. [S.1.]: University of Toronto,2009.   
[28] Suda N,Chandra V,Dasika G, et al. Throughput-optimal OpenCL based FPGA accelerator for large-scale convolutional neural networks [C]// Proc of ACM/SIGDA ISFPGA.2016:16-25.   
[29] QiuJiantao,Wang Jie,Yao Song,et al.Going deeper with embedded FPGA platform for convolutional neural network [C]// Procof

ACM/SIGDA International Symposium on Field-Programmable Gate Array. 2016:26-35. [30] Venieris S I,Bouganis C S. fpgaConvNet: a framework for mapping convolutional neural networks on FPGAs [C]// Proc of IEEE FCCM. 2016: 40-47.