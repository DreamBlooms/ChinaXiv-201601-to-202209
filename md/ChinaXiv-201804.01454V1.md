# 一种基于CUDA的截断重叠维特比译码算法

李晨杰，王志旭

(南京邮电大学 通信与信息工程学院，南京 210003)

摘要：为解决信道译码在高吞吐量通信系统中的瓶颈问题，通过对CUDA并行计算的了解和对维特比译码并行实现的探索，为卷积码提出了一种基于CUDA的截断重叠维特比译码器。算法通过截断式的子网格图相互重叠的方式，并行执行独立的正向度量计算和回溯过程。实验结果表明，在保证了译码算法误码率性能的同时，获得了良好的吞吐量提升表现，相比现有的实现方式有 $1 . 3 { \sim } 3 . 5$ 倍的提升，降低了硬件开销，能够有效运用于实际高吞吐量通信系统中。

关键词：卷积码；维特比译码；并行计算；CUDA 中图分类号：TP312 doi: 10.3969/j.issn.1001-3695.2017.12.0794

# Truncated overlap scheduling viterbi decoding algorithm based on CUDA

Li Chenjie, Wang Zhixu (College of Telecommunications& InformationEngineering,Nanjing UniversityofPosts&Telecommunications,Nanjing 210003, China)

Abstract: Inorder tosolvethebottleneckproblemofchanneldecodinginhigh-throughputcommunicationsystems,atruncated overlap ViterbidecoderbasedonCUDAisproposed forconvolutional codes tosolveitbyanalyzingofparallprocesingbased on Compute Unified Device Architecture(CUDA）and exploring of the parallel implementation of Viterbi decoding.The algorithm performs both independent forward metricscomputingand back-track procedure inparalel through the overlapping oftruncated sub-grid.The experimentshows that the method keeps low BER,achievesaperformance improvementof1.3-3.5 timesoftheexisting implementationandreduces hardwareconsumption.Itcanbeefectivelyused inpracticalhigh-throughput communication systems.

'ey words: convolutional codes;Viterbi decoder; parallel processing; CUDA

# 0 引言

随着现代移动通信技术的飞速发展，人们对通信业务速率的需求越来越高，给信道译码带来更高吞吐量的解决方案成为关注的重点之一。现如今，越来越多的人通过将FPGA、DSP、GPU等平台的优势与译码器特殊的结构相结合来达到高吞吐量的目的。文献[1,2]通过使用FPGA设计与实现了一种高通量的维特比译码器，文献[3]基于DSP实现了维特比译码算法。通过比较不难发现，DSP虽然具有良好的代码灵活性，但是却需要依靠高主频来解决计算能力，而FPGA提供了高计算能力，但是开发过程非常复杂，硬件成本也非常高[4。随着GPU的不断发展，它在拥有超高运算能力的同时还具有并行处理数据的能力，这给高吞吐量译码带来了更多的可能性。文献[5\~7]都使用GPU平台达到了各自的译码器对高吞吐量需求，这说明使用GPU 确实是一个实现高吞吐量译码器的有效途径。文献[8]提出了使用子译码级并行和共享内存技术两种方法，在GPU 平台对LTETurbo 译码器进行加速，在不损失误码率的情况下有效地提高了吞吐量。文献[9]提出了基于“分治法"的维特比译码算法，通过归并的方法来消除子网格之间的相关性，这种思想非常有利于维特比译码的并行实现。

本文提出了一种基于CUDA的并行截断重叠维特比译码算法（Parallel-TOVDA)，利用"分治法"的思想，结合子译码级并行方法和CUDA平台合并内存访问模式，达到了高吞吐量的要求。不同于文献[9]，本文提出的译码算法的网格图可以划分为截断式的子网格图，可以并行执行独立的正向度量计算和回溯过程。与文献[9]相比，本文提出的维特比译码器实现了1.2\~3.6倍的性能加速和良好的误码率(BER)性能。

# 1 并行维特比译码算法

# 1.1维特比译码算法

维特比译码过程可以表示为图1中描述的网格图。在网格图中，状态从左向右在多个时间阶段内反复变化，这里的时间阶段数等同于信息比特的长度。维特比算法的过程可以分为正向过程和回溯过程两个方向。回溯的目的是通过网格图来搜寻最大似然路径。路径度量（PM）用来测量网格图中每种可能的路径。在每个时间阶段，计算两个状态之间的分支度量(BM)，然后将它们相加来更新PM。然而只有具有最小PM的路径在下一次迭代中被保留并传递下去。对于网格图中的每个状态，执行加-比-选（ACS）操作来找到所有路径的幸存比特（SB)，最后得到幸存路径。ACS操作可以如下表示：

$$
\begin{array} { r l } { l e t } & { t e m p _ { 0 } = P M _ { t - 1 , 2 j } + B M _ { 2 j , s } , t e m p _ { 1 } = P M _ { t - 1 , 2 j + 1 } + B M _ { 2 j + 1 , s } , } \\ & { s = ( 0 , 1 , . . . , 2 ^ { K - 1 } ) , j = s ^ { \mathcal { I } } \boldsymbol { \partial } 2 ^ { K - 2 } } \\ & { i f ( t e m p _ { 0 } > t e m p _ { 1 } ) P M _ { t , s } = t e m p _ { 1 } , S B _ { t , s } = 1 } \\ { e l s e } & { = t e m p _ { 0 } , S B _ { t , s } = 0 } \end{array}
$$

其中： $K$ 是卷积码的约束长度；分支度量BM等于信息比特和汉明距离的乘积。在正向过程创建整个网格图之后，回溯过程开始反向追踪以搜索出最大似然路径，该路径的所有 SB 即是最后译码得到的比特（DB)。本文以约束长度为7，码率1/2的卷积码为例进行并行译码的介绍。

# 1.2两种维特比译码算法的执行方式

通过对维特比解码算法的分析，可以发现在正向计算中，各状态之间的ACS 操作相互独立，因此这些操作可以并行处理。然而从时间轴上看可以发现， $P M _ { t , s }$ 是受 $P M _ { \scriptscriptstyle { t - 1 , s } }$ 影响，因此必须逐级执行每一个时间阶段。所幸在后向计算过程中，所有的幸存者路径都是在适当的回溯长度之后就可以合并在一个状态，这种归并的过程称之为回溯阶段。最后，可以从合并的状态回溯，获得译码序列，这个过程称为译码阶段。

如图1所示，维特比译码算法有三个阶段，分别是正向计算阶段(FCP)、回溯阶段(TP)和译码阶段(DP)。可以发现，其实待译码的序列中的任一部分都进行上述三个阶段。如果将序列截断成 $n$ 块，FCP在每个块中生成子网格图，TP得到了归并的状态，为DP提供起始状态，最后DP输出译码比特。图2介绍了该算法的两种执行方式：流水线式和并行同步式。文献[10]提出一种基于滑动窗口管道技术的流水线模式，箭头表示算法的执行方向。当第 $i$ 次FCP（记为 $F _ { i }$ ）完成，则第i-1次TP（记为 $T _ { i - 1 }$ )开始执行，结束之后再执行第i-2次DP（记为 $D _ { i - 2 }$ ）。虽然流水线模式在使用FPGA时可以达到非常高的译码吞吐量[10]，但是它并不适用于GPU。为了充分利用GPU上的算法单元多的特性，本文提出了基于截断重叠技术的并行同步模式。首先，输入序列被截断成 $\mathfrak { n }$ 块，每一个块尾部都有一部分长度与下一个块重叠。重叠的尾序列将用于执行TP来找到归并的状态。然后将所有块中的FCP并行执行，在每个块中对应的TP和 DP可以独立处理。

![](images/df92e4c9c9528cbf05a458ea3f9d26936dc083c6a8a1ebfba22b8c9a9dbb4cab.jpg)  
图1维特比译码网格图

![](images/fb0e279aa1de4dffe181c23b9aa2b0df96923b2d24da6e0ce6c763e2b45fdb7f.jpg)  
图2流水线式、并行同步式维特比译码

# 2 基于CUDA 的Parallel-TOVDA

# 2.1基于CUDA平台的并行方式

CUDA架构是一种由NVIDIA推出的通用并行计算架构，该架构使GPU 能够解决复杂的计算问题，而基于截断重叠技术的维特比译码算法的思想也包含了并行计算的思想，因此只需要在该译码算法的基础上，通过对网格图的时间轴进行划分，将每个子网格图可以分为两个阶段：FCP和回溯译码(TD)阶段，其中包括TP和DP。图3描述了在CUDA上实现的并行维特比译码算法。图中 $F _ { i }$ 表示第 $i$ 个截断子网格的FCP； $A C S _ { t , s }$ 表示在时间 $\mathbf { \chi } _ { t }$ 和状态 $s$ 下的加比选操作； $T D _ { i }$ 表示在第 $i$ 个截断的子网格中的回溯译码阶段。为了精准地译码， $F _ { i }$ 的截断长度可以设置为 $2 L _ { d } + 2 L _ { t }$ 。其中： $L _ { \imath }$ 是 TP 的回溯长度，而 $L _ { d }$ 是

DP 的译码长度。这样，输入信号序列就被划分为长度为 $2 L _ { d }$ 子序列，在每个子序列尾部添加一个长度为 $2 L _ { t }$ 的尾序列，这个尾序列同时又是下一个子序列的一部分，用于执行回溯阶段。

![](images/c7e22e8ced8c9ea883e9465dc74c28033967b3f39276e944d7daccfda31b9381.jpg)  
图3基于CUDA的Parallel-TOVDA 线程安排

在FCP中，网格图中的一个时间阶段的每个ACS操作都被分配给每个线程，在其中计算BM、PM和SB值。每个线程块中总共有1024 个线程，一共可以进行 $p$ 路 $F _ { i }$ 并行计算， $p$ 等于1024除以2K-1。连续时间阶段的网络在每个线程块中的共享内存中执行。每个线程分别将PM和 SB 值写入共享内存和全局内存中的对应地址。SB值由在网格图中的所有路径组成，但这对于共享内存来说太大了。在此之后，线程间轻量级的同步可以确保所有线程在网格图的一个时间阶段中完成计算和写入操作，这并不影响性能。在同步之后，可以在共享内存中获取正确的输入PM值。然后在相同的情况下对各个时间阶段进行连续的计算。

在FCP完成后,第 $i$ 个截断子网格中的 TD 阶段开始在 $T D _ { i }$ 的第一个线程中执行。采用分治法找出 $F _ { i }$ 中的所有第 $L _ { d } + L _ { t }$ 个状态中最小的PM值，把它作为回溯状态。在回溯 $L _ { \mathrm { { } } _ { t } }$ 位后就可以得到归并的状态。最后，得到的 $L _ { d }$ 个比特是第 $i$ 个截断子网格的译码比特。这就是所谓的Parallel-TOVDA。下面给出了Parallel-TOVDA的伪代码。

算法：基于CUDA的Parallel-TOVDA

初始化：  
输入：输入比特 $c$ 、汉明距离hd。  
输出：译码比特 $D B .$ 0  
变量 $P M _ { h }$ ，nextPMk用于对 $\boldsymbol { h }$ 线程进行分配共享内存;  
$P M _ { k } = 0$ ；next $P M _ { k } = 0$ ； $\scriptstyle p = 1 6$ ； $\scriptstyle { i = 0 }$ ； $B M _ { 1 } { = } \Theta$ ； $B M _ { 2 } = \theta$ ； $\scriptstyle { \mathsf { S } } = { \mathsf { \theta } }$   
迭代：  
1:for thread-block $\textit { b } \boldsymbol { \Theta }$ to $\lfloor n / p \rfloor$ parallel do  
2: for thread in dimension- $\textbf { \cdot x } t x \textbf { \ --}$ to $p \texttt { - } 1$ parallel do3: $\dot { \textbf { \textit { 1 } } } = \textbf { \textit { b } } \times \textbf { \textit { p } } + \mathbf { \beta } t x ;$ （204号  
4: for thread in $\mathsf { y }$ dimension ty 0 to 63 parallel do5: $j = t y \% 2 ^ { K - 2 } ;$

6: for $\textit { t } \boldsymbol { \Theta }$ to $\boldsymbol { L } _ { d } + \boldsymbol { L } _ { t } - 1$ do   
7: Load $c _ { i + 2 t }$ and $c i + 2 t + 1$ from the global memory;   
8: Load $h d _ { 2 j }$ and $h d _ { 2 j + 1 }$ from the constant memory;   
9: $k \ = \ t x \ \times \ 6 4 \ + \ t y .$   
10: $\begin{array} { r c l } { { } } & { { } } & { { B M _ { 1 } ~ { = } c _ { i + 2 t } ~ \times h d _ { 2 j } , B M _ { 2 } ~ { = } c _ { i + 2 t + 1 } ~ \times h d _ { 2 j + 1 } ; } } \\ { { } } & { { } } & { { } } \\ { { } } & { { n e x t P M _ { k } ~ { = } ~ m i n \{ P M _ { 2 j } ~ + ~ B M _ { 1 } , ~ P M _ { 2 } ~ { \ l } _ { j + 1 } ~ + ~ B M _ { 2 } \} ; } } \\ { { } } & { { } } & { { S B _ { t , t ; y } ~ { = } ~ ( P M _ { 2 j } ~ + ~ B M _ { 1 } ~ > ~ P M _ { 2 j + 1 } ~ + ~ B M _ { 2 } ) ? 1 ~ { : } ~ \theta ; } } \end{array}$   
11:   
12: （20   
13: Store $\textit { s } \boldsymbol { B } _ { t , \ t y }$ in the global memory;   
14: Synchronize;   
15: $P M _ { R } \ = \ n e x t P M _ { R } ;$   
16: end for   
18: end for   
19: Reduce and Fetch the state with minimum PM Smin   
from $P M _ { 0 + L d + L , \theta }$ to $P M _ { 0 + L d + L + } , 6 3$ ;   
20: （20 $s \ = \ s _ { m i n } ;$   
21: for $\textit { t } \ L _ { d } \ + \ L _ { t } \ - \ 1$ to 0 do   
22: j = 5%2K-2,   
23: Load $s \ B _ { t , s }$ in the global memory;   
24: if $t < L _ { d }$ then   
25: $D B _ { t } ~ = ~ S B _ { t , s } ; $   
26: end if   
27: $S ~ = ~ ( ~ S B t , s ~ = ~ \theta ~ ) ~ ? ~ 2 j ~ : ~ 2 j + 1 ;$ （204号   
28: end for   
29: end for   
30:end for

# 2.2合并内存访问技术

在算法中，每个线程中的 ACS 操作需要在每次迭代中将SB 存储到全局内存中，从而产生大量的内存访问开销。但是通过合并内存访问模式，可以将内存访问的总时间减少16倍。在

CUDA中，half-warp作为调度单位，内部拥有16个线程，它可以启动一个统一的合并访问内存，而不是启动16个单独的内存访问。这种合并访问模式只在半经线的数据必须存储在连续的内存地址中的情况下才可以使用。因此，必须在全局内存中对SB组织进行调整，以执行合并的内存访问。在编译之前，SB 必须以一种连续的方式对一个线程进行处理，以便在64个存储在一起的状态中形成 SB。然后，在一个half-warp，即每16个线程一组，可以通过单一的连接内存访问，在全局内存中执行数据交换。对于这种CUDA特有的内存访问技术，这里不再赘述。

# 3 误码率性能及吞吐量

# 3.1性能分析模型

处理译码的GPU 频率为 $F$ ，流处理器数量为 $N _ { c U D A }$ 。算法中用 $N _ { s }$ 表示状态数， $n$ 是分块数，执行周期和内存访问延迟在 ACS 操作时分别为 $E _ { A C S }$ 和 $M _ { _ { A C S } }$ ，在回溯操作时分别为$E _ { _ { T D } }$ 和 $M _ { \scriptscriptstyle T D }$ 。因为 FCP 中合并内存访问，所以 $M _ { \scriptscriptstyle A C S }$ 需要除以16。由于在TP阶段加入了额外的长度为 $L _ { \mathrm { } _ { t } }$ 的比特，所以在回溯操作 $E _ { \scriptscriptstyle T D }$ 和 $M _ { \scriptscriptstyle T D }$ 中执行和内存访问循环包括 TP 和 DP 的部分。该算法的执行时间 $T _ { _ { p } }$ 为

$$
T _ { p } = \frac { n } { F \times N _ { c U D A } } \Bigg [ \Bigg ( E _ { A C S } + \frac { M _ { A C S } } { 1 6 } \Bigg ) \times N _ { s } + \left( E _ { T D } + M _ { T D } \right) \times \left( L _ { d } + L _ { t } \right) \Bigg ]
$$

# 3.2实验设置

为了验证基于CUDA的Parallel-TOVDA的实用性，本文给出的测试场景是：输入随机生成的二进制比特流，由卷积编码器编码，然后经过AWGN通道。在接收机中，数据传递到GPU的全局内存中，执行Viterbi解码过程。

在测试场景中，GPU为GTX1050，拥有640个CUDA核心，核心的基础频率是 $1 . 3 5 ~ \mathrm { G H z }$ ，可动态睿频至 $1 . 5 ~ \mathrm { G H z }$ 。其全局内存的大小是2GB。表1列举了本次实验的关键参数设置情况。

表1测试实验关键参数设置情况  

<html><body><table><tr><td colspan="2">误码率性能测试实验</td><td>吞吐量性能测试实验</td></tr><tr><td>总译码位数</td><td>16384</td><td>16384</td></tr><tr><td>L</td><td>0、14、28</td><td>14</td></tr><tr><td>Ld</td><td>64</td><td>32、64、128、256、512</td></tr><tr><td>Nb</td><td></td><td>1、2、4、8、16、32</td></tr></table></body></html>

# 3.3译码器误码性能

如前所述， $L _ { \mathrm { } _ { t } }$ 表示了TP的长度，它可以决定解码过程的初始状态并影响维特比译码器的误码率。为了评估译码器的BER 性能，将 $L _ { \phantom { } _ { t } }$ 长度分别设置为0、14、28，固定 $L _ { d }$ 长度为64。最终性能指标如图4所示。BER 随 $L _ { \mathrm { * } }$ 的增加而减小。当回溯长度越高，译码器的BER在MATLAB仿真中越接近理论BER的性能，这证明了本文的译码器是实用的。

![](images/f923523dea7b6486bee552a5c9a9934ed0843c8eec6ad8edf5cd2838ef6bd22e.jpg)  
图4AWGN 信道下译码器在不同 $L _ { \mathrm { * } }$ 情况的误码率性能

# 3.4译码器吞吐量

为了测量在CUDA上提出的维特比译码算法的处理时间，本文使用NVIDIA公司提供的Profiler。在实验中，总译码位数是16384,被分成 $n$ 个截断块,在GPU 的 $\boldsymbol { N } _ { b }$ 个线程块上执行，因此固定 $L _ { \mathrm { } _ { t } }$ 为14，改变不同的 $\boldsymbol { N } _ { b }$ 和 $L _ { d }$ 。如图7所示，发现开启线程块越多，执行的效率越高，吞吐量越大；当运行在相同的线程块情况下， $L _ { d }$ 设为64 可以获得更好的执行效率，吞吐量相对较高。纵观图5，当 $L _ { d }$ 为64并开启8个线程块并行执行时（白线交点)，CUDA核心的计算能力和线程块间共享内存的使用达到了平衡。

![](images/002890b3d1d6c2ee8b48f6762c4711e161df61b1fc5cb7cc742c3a7686e2b271.jpg)  
图5不同DP长度和线程块情况下的运算时间

# 3.5性能比较

为了突显Parallel-TOVDA的优点，本文将实验结果与文献[9,11]进行对比（表2)。文献[9]中的算法利用了将比特序列分割成多个块的方法，将这些块被分布到与本文相似的多个线程块中。然而在回溯阶段，多个线程块的所有路径都被合并，并且通过一个线程生成解码序列。本文提出的算法是一种完全并行的截断重叠维特比算法。整个网格图被分割成多个子网格图，每个子网格图的正向计算和回溯独立执行。性能比较如图8所示。该维特比译码算法的峰值吞吐量达到了88.1Mbps，总体相比文献[9]吞吐量提高了1.3\~3.5倍。文献[12\~14]通过提高CUDA核心的频率和数目，在原有实现方式的基础上获得了吞吐量的提升，甚至到 $\mathbf { G b } / \mathbf { s }$ 级别。

表2不同线程块 $N _ { b }$ 时译码器吞吐量比较/Mbps  

<html><body><table><tr><td>Nb</td><td>1</td><td>2</td><td>4</td><td>8</td><td>16</td><td>32</td></tr><tr><td>文献[11]</td><td>0.9</td><td>1.8</td><td>4.1</td><td>7.6</td><td>14.8</td><td>28.7</td></tr><tr><td>文献[9]</td><td>2.7</td><td>4.7</td><td>8.6</td><td>12.3</td><td>15.1</td><td>29.4</td></tr><tr><td>本文</td><td>3.5</td><td>7.1</td><td>13.4</td><td>28.3</td><td>52.9</td><td>88.1</td></tr></table></body></html>

图6更直观地显示了本文所设计的译码器在吞吐量上的巨大优势。性能优化情况如下：当线程块 $\boldsymbol { N } _ { b }$ 设置为16时,Parallel-TOVDA相比文献[9]所提出的译码器在吞吐量上提高了3.5倍，相比文献[11]提高了3.6倍；当达到88.1Mbps 峰值吞吐量时，相比文献[9]和[11]提高了3倍；当仅试用1个线程块（ $N _ { b } ^ { \mathbf { \alpha } } = 1$ ）时，相比文献[9]提升了1.3倍。这说明在该算法在保证纠错性能前提下，最大限度地将维特比译码的结构特性和CUDA平台的计算特性结合，提高了译码的吞吐量，这意味着该算法可以在同样的吞吐量要求下，节省更多的硬件开销。

![](images/89829539d8b13a1c6288d9da706ec00cfca4f30d7dd493d0ec36d79270bbcd7e.jpg)  
图6不同线程块 $\boldsymbol { N } _ { b }$ 时译码器的吞吐量大小/Mbps

# 4 结束语

本文提出了一种基于CUDA的截断重叠并行维特比译码算法。将维特比译码器的输入比特序列划分为 $n$ 个重叠的截断块，分布在GPU上的多个进程块中，每个线程块可以对多个截断块进行并行处理。在每个截断块中，正向计算和回溯可以独立执行，从而最大限度地提高GPU的并行能力。实验表明，基于CUDA的截断重叠维特比译码器的吞吐量可以达到88.1Mbps，相对于文献[9]的实现有1.3\~3.5倍的性能改进。如果对吞吐量有更高的要求，可以使用CUDA核心数目更多、频率更高的GPU平台，线性地提高吞吐量，很轻易就可以达到Gb/s级别的吞吐量。结果表明，提出的维特比译码器完美匹配CUDA平台的架构特性，能够在保证纠错能力的同时很大程度上提高了译码吞吐量，可用于基站或移动基站的通信。

参考文献：   
[1]Kermani M M, Singh V,Azarderakhsh R.Reliable low-latency viterbi algorithm architectures benchmarked on ASIC and FPGA [J]. IEEE Trans on Circuits & Systems IRegular Papers,2017,PP(99): 1-9.   
[2]Li LF,Li HW,Li HL,et al.Research and implementation of Viterbi decoding in TD-LTEsystem [C]// Advanced Information Technology, Electronic and Automation Control Conference.2017: 890-894   
[3]罗友宝，李小文.LTE 系统的Viterbi译码算法仿真及DSP 实现[J]．光 通信研究,2010,2010 (3):67-70.   
[4]Stamoulias I, Georgoulakis K,Blionas S,et al.FPGA implementation of an MLSE equalizer in 10 Gbps optical links [C]//Proc of IEEE International Conference on Digital Signal Processing.2015:794-798.   
[5]Wu M,Wang G,Cavallaro JR.Implementation of a high throughput 3GPP turbo decoderon GPU[J]. Journal of Signal Processing Systems,2011,65 (2): 171-183.   
[6]Martinez-Zaldivar F J. Tridimensional block multiword LDPC decoding on GPUs [J]. Journal of Supercomputing,2011,58 (3): 314-322.   
[7]Wu M,Sun Y,Gupta S,et al. Implementation of a high throughput soft MIMO detector on GPU[J]. Journal of Signal Processing Systems,2011, 64 (1): 123-136.   
[8]Liu C,Bie Z, Chen C,et al. AparalelLTE turbo decoder on GPU [C]//Proc of IEEE International Conference on Communication Technology.2014: 609-614.   
[9]Lin CS,Liu WL,Yeh WT,etal.Atiling-scheme viterbi decoderinsoftware defined radio for GPUs [C]//Proc of International Conference on Wireless Communications,Networking and Mobile Computing.2011: 1-4.   
[10] Zhang D, Zhao R, Han L,et al.An implementation of viterbi algorithm on GPU[C]//Proc of International Conference on Information Science and Engineering. 2009:121-124.   
[11] Ahn C, Kim J,Ju J,et al. Implementation of an SDR platform using GPU and its application to a $2 \times 2$ MIMO WiMAX system [J]. Analog Integrated Circuits & Signal Processing,2011, 69 (2-3): 107-117.   
[12] LiR,Dou Y, Zou D.Efficient parallel implementation of three-point viterbi decoding algorithm on CPU，GPU，and FPGA [J].Concurrency& Computation Practice & Experience,2014,26 (3): 821-840.   
[13]PengH,LiuR,HouY,etal.AGb//sparallelblock-based Viterbi decoder for convolutional codes on GPU [Cl/ Proc of International Conference on Wireless Communications & Signal Processing.2016:1-6.   
[14]Xia KF,BinWU,XiongT,et al.Design ofa high-throughput sliding block viterbi decoder for IEEE 802.1lac WLAN systems [J]. Ieice Trans on Fundamentals of Electronics Communications & Computer Sciences, 2017, E100.A(8): 1606-1614.