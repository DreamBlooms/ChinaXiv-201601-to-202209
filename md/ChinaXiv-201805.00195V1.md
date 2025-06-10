# 极化码串行抵消译码算法延迟性的改进

张宇国，周健

(南京邮电大学 通信与信息工程学院，南京 210003)

摘要：由Arikan提出的极化码，因其简单的编译码结构引起广泛关注。极化码作为一种高性能的信道编码，编码长度超过 $2 ^ { 1 0 }$ 会产生优异的性能。在串行抵消（successivecancelation，SC）译码算法结构基础上，其译码延迟随码长增加而加剧。通过分析SC译码算法，提出一种基于冻结比特的改善SC译码算法方案，有效地降低了传统SC译码算法的延迟性。算法改进后相比原来可以降低 $50 \%$ 的译码延迟，并引入串行抵消单比特翻转译码算法作为译码补偿，进一步提高译码算法的纠错能力。

关键词：极化码；SC译码算法；冻结比特；译码延迟 中图分类号：TN911.2 doi: 10.3969/j.issn.1001-3695.2017.07.0671

# Improvement of latency in successive cancellation decoder for polar codes

Zhang Yuguo, Zhou Jian (CollegeofElectronic Science&dEngineeing,Nanjing UniversityofPosts &Telecommunications,Nanjing210o,China)

Abstract:Abstruct: The polar codes proposed by Arikancaused much atention due to their simple structure.As a highperformance channel encoding,polar codes will achieve good performances once the code length $\mathrm { \Delta N }$ is greater than 210.On thebasisofthe SuccessiveCancelation (SC)decodingalgorithm,thedecodinglatencyincreases with theincreaseofcodelength. Byanalysis ofthe position of frozen bitsand the SCdecoder architecture,this paper proposed an improved SCdecoding algorithm,which effectivelyreduces thelatencyofthe traditionalSCdecoderalgorithm.Thealgorithmimproves thedecoding delay by $50 \%$ compared to the original. What'smore,it further improves the error correction capability ofthe decoding algorithm by using the Succession Cancellation Single-Bit-Flipping.

Key Words: polar code, SC decoder algorithm, frozen bit, decoder latency

# 0 引言

1984年，Shannon指出在不可靠的信道上实现可靠通信，可以用信道编码技术实现在干扰噪声中有效且可靠的传输信息[1。构造可达到信道容量或者逼近信道容量的信道编码具体方法以及寻求可行的相应译码算法是信道编码领域核心研究方向。

近20 年以来，以Turbo码、LDPC码为代表的信道编码技术，是能够逼近香农信道容量的。虽然这些编码技术在实际应用中有着不错的性能，但相应的编译码理论基础尚不完善，理论上很难证明这些码的最优传输特性。2009年，Arikan基于信道极化理论提出极化码，理论界掀起了研究热潮。基于串行抵消译码算法，极化码是能够被严格证明达到信道容量的信道编码方法[2.3]。相比于Turbo 码、LDPC 码，极化码可由简单的编码器和译码器来实现，译码算法无须复杂的迭代计算，编译码时间复杂度仅为 $o ( n \log n )$ ，随着码长的增加，复杂度对数增长。虽然极化码编码方案有着很好的抗干扰性能，但是随着编码位数增加，SC 译码系统的延迟问题随之突显[4-5]。针对这一编码不足，下面简要阐述极化码构造原理，并着重分析SC译码算法结构，对译码延迟作出改进。

# 1 极化码

极化码是通过信道极化概念来构建的。信道极化分为两个阶段，分别是信道联合和信道分裂。ErdalArikan证明了通过这一线性操作，分裂后的各个子信道的对称容量将呈现两极分化现象。随着信道联合数N（即编码的码长位数）的增加，部分信道的对称容量趋于1，而其余子信道的对称容量趋于0。利用这一信道极化现象构造极化码，在对称容量趋于1的子信道上传输K个信息比特，在其余子信道上传输冻结比特。冻结比特是收发双方已知的固定比特，默认设置为零，本文所提出的SC算法改进正是基于冻结比特这一特性。根据此极化信道提出的编码方案即为极化码，码率为K/N。

# 1.1编码步骤

Arikan 论文中是基于二进制输入离散无记忆信道（binary-discrete memoryless channel，B-DMC）[]中展开讨论极化码的编码方案，B-DMC 可表示为 $W ( X \to Y )$ 。基于信道极化现象构建的编码步骤如下：

a）极化信道的可靠性估计。

对于B-DMC 信道 $W$ ，用巴氏参数 Z(W)来衡量信道的可靠性。巴氏参数值的大小与信道可靠性呈负相关关系，即巴氏参数越小，说明该信道可靠性越大，反之说明该信道可靠性越小。根据Arikan给出的巴氏参数计算公式（针对二进制删除信道（Binary Erasure Channel，BEC)）:

$$
Z ( W _ { N } ^ { ( i ) } ) = \sum _ { y _ { i } ^ { N } \in Y ^ { N } } \sum _ { u _ { 1 } ^ { i - 1 } \in X ^ { i - 1 } } \sqrt { W _ { N } ^ { ( i ) } ( y _ { i } ^ { N } , u _ { 1 } ^ { i - 1 } |  0 ) W _ { N } ^ { ( i ) } ( y _ { i } ^ { N } , u _ { 1 } ^ { i - 1 } | 1 ) }
$$

计算出各个信道的巴氏参数值，其中 $W _ { N } ^ { ( i ) } ( y _ { i } ^ { N } , u _ { 1 } ^ { i - 1 } | u _ { i } )$ 为序号 $i$ 的极化信道 $W _ { N } ^ { ( i ) }$ 的信道转移概率。

b）比特混合。

在第一步骤的工作基础上，根据巴氏参数与信道可靠性的关系选取前K个可靠性大的分裂子信道传输消息比特，在其余N-K个分裂子信道传输冻结比特。此时，可以构建出原始比特$u _ { 1 } ^ { N }$ 。

c）构造生成矩阵。

Arikan提出的生成矩阵的表达式为

$$
G _ { { \scriptscriptstyle N } } = B _ { { \scriptscriptstyle N } } F ^ { \otimes n }
$$

上述式中 $\boldsymbol { F } ^ { \otimes n }$ 表示对矩阵 $\begin{array}{c} F = { \binom { 1 } { 1 } } \quad 0 \\ { 1 } \quad 1 \end{array}$ 的 $\mathfrak { n }$ 次克洛内克积。$B _ { \scriptscriptstyle { N } }$ 是排序矩阵，用以完成比特反序重排操作。最后给出编码公式

$$
x _ { 1 } ^ { N } = u _ { 1 } ^ { N } G _ { N }
$$

$x _ { 1 } ^ { N }$ 即是编码后的比特序列,码长为 $N = 2 ^ { n }$ 。

# 1.2串行抵消译码

序号 $i$ 的极化信道 $W _ { N } ^ { ( i ) }$ 的输出不仅包括信道接收信号 $\mathbf { y } _ { 1 } ^ { N }$ ，还包括前 $i - 1$ 个极化信道的输入 $u _ { 1 } ^ { i - 1 }$ 两个部分，信道转移概率为

$$
W _ { N } ^ { ( i ) } ( \mathbf { y } _ { 1 } ^ { N } , u _ { 1 } ^ { i - 1 } \mid u _ { i } ) { = } \sum _ { u _ { i + 1 } ^ { N } \in X ^ { N - i } } \frac { 1 } { 2 ^ { N - 1 } } W _ { N } ( y _ { 1 } ^ { N } \mid u _ { 1 } ^ { N } )
$$

比特 $u _ { 1 } ^ { i }$ 的估计值 $\hat { u } _ { i }$ 根据接收信号 $\mathbf { y } _ { 1 } ^ { N }$ 和部分输出序列 $u _ { 1 } ^ { i - 1 }$ 来进行比特估计，比特估计函数为

$$
\hat { u } _ { i } = \left\{ \begin{array} { l l } { h _ { i } ( y _ { 1 } ^ { N } , \hat { u } _ { 1 } ^ { i - 1 } ) , i \in A } \\ { u _ { i } , i \in A ^ { c } } \end{array} \right.
$$

记信息承载信道集合为 $A$ ，反之记为 $A ^ { c }$ 。其中，当 $i \in A ^ { c }$ 时，表明该比特是冻结比特，则可以根据收发双方事先约定直接判决为默认值，以避免在固定位的译码错误。当 $i \in A$ 时，表明该比特是信息承载，判决函数为

$$
h _ { i } ( y _ { 1 } ^ { N } , \hat { u } _ { 1 } ^ { i - 1 } ) = \left\{ \begin{array} { l l } { 0 , L _ { N } ^ { ( i ) } ( y _ { 1 } ^ { N } , \hat { u } _ { 1 } ^ { i - 1 } ) \geq 0 } \\ { 1 , L _ { N } ^ { ( i ) } ( y _ { 1 } ^ { N } , \hat { u } _ { 1 } ^ { i - 1 } ) < 0 } \end{array} \right.
$$

其中对数似然比计算公式为

$$
L _ { N } ^ { ( i ) } ( y _ { 1 } ^ { N } , \hat { u } _ { 1 } ^ { i - 1 } ) = \ln \Biggl ( \frac { W _ { N } ^ { ( i ) } ( y _ { 1 } ^ { N } , \hat { u } _ { 1 } ^ { i - 1 } | 0 ) } { W _ { N } ^ { ( i ) } ( y _ { 1 } ^ { N } , \hat { u } _ { 1 } ^ { i - 1 } | 1 ) } \Biggr )
$$

为了寻求信息位的译码输出，关键是计算对数似然比$L _ { N } ^ { ( i ) } ( y _ { 1 } ^ { N } , \hat { u } _ { 1 } ^ { i - 1 } )$ ，可以对其进行递归运算方法 $[ 7 \mathord { \sim } 9 ]$ 。接收端得到$L _ { 1 } ^ { ( 1 ) } ( y _ { i } ) = \ln \frac { W ( y _ { j } \mid 0 ) } { W ( y _ { j } \mid 1 ) }$ ，由接收端向接收端逐级递归，求出对数似然比 $L _ { N } ^ { ( i ) } ( y _ { 1 } ^ { N } , \hat { u } _ { 1 } ^ { i - 1 } )$ ，在进行后续译码判决。

上述 SC 译码过程，当前第 $i$ 比特的译码判决会依赖前 $i - 1$ 个极化信道的输入 $u _ { 1 } ^ { i - 1 }$ ，线性依赖特性决定了译码的顺序输出。假定前 $i$ 个极化信道的输入 $u _ { 1 } ^ { i }$ 皆是冻结比特，根据前 $i$ 个估计比特序列 $\hat { u } _ { 1 } ^ { i }$ 和 $W _ { N } ^ { ( i + 1 ) }$ 接收信号 $y _ { 1 } ^ { N }$ 对第 $i + 1$ 个比特 $\hat { u } _ { i + 1 }$ 进行译码判决，但是对 $\hat { u } _ { i + 1 }$ 译码可以直接利用冻结比特的默认值进行译码工作，而无须等待 $u _ { 1 } ^ { i }$ 的译码工作。此时， $u _ { 1 } ^ { i }$ 的译码工作为本文所需的信息比特造成了译码延迟，造成了不必要的译码开销。

# 2 改进的 SC 译码算法

针对 SC译码延迟的研究，现今已经有多种方案提出[10\~12]。在文献[10]中，提出关于输出F和G的归并计算单元（mergedprocessing elements,MPE)，并给出相关定义。图1显示文献[10]中提出的MPE计算原理图。尽管这些译码方案改善了译码延迟，但是硬件实现有着一定困难。

![](images/1834f1dd7fbc29c69baaac3edebd8cd6bdf5e0f6ef11d0443d7ee1b25cdc37d0.jpg)  
图1MPE 模块单元计算

![](images/8c4c8afa35f059003ead80cbadcc7697e9e0b3f457391b404ad80bc542cf8ef2.jpg)  
图28位SC译码算法结构

图2显示了 $_ { \mathrm { N = 8 } }$ 的传统 SC 译码算法结构[10]，表1显示了译码的具体计算单元。分析表1中的数据，对于N位的极化码，传统SC 译码算法需要N-1个时钟循环来译码。表2显示 $_ { \mathrm { N = 8 } }$ 时，极化码的具体译码输出情况。N位长的极化码需要的译码可以分为 $\mathbf { N } / 2$ 个译码输出步骤，每个步骤输出两个译码比特。对于阶段i需要 $2 i - 1$ 次运算和 $N / 2 i$ 个 MPE,故而 MPE 的计算

量如下定义：

$$
M P E _ { c a l c } \ = \ N / 2 \times 1 \ + \ N / 4 \times 2 \ + \ . . . + 1 \times 2 ^ { l o g _ { 2 } N - 1 } \ = \ N / 2 \times l o g _ { 2 } N
$$

表18位SC译码算法时钟   

<html><body><table><tr><td>时钟</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td></tr><tr><td>阶段1</td><td>MPE</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>阶段2</td><td></td><td>MPE</td><td></td><td></td><td>MPE</td><td></td><td></td></tr><tr><td>阶段3</td><td></td><td></td><td>MPE</td><td>MPE</td><td></td><td>MPE</td><td>MPE</td></tr><tr><td>输出</td><td></td><td></td><td>u1,u2</td><td>3,04</td><td></td><td>5,u6</td><td>7,8</td></tr></table></body></html>

表28位SC译码算法步骤  

<html><body><table><tr><td>阶段</td><td>1</td><td>2</td><td>3</td><td>译码比特位</td></tr><tr><td>MPEcalc</td><td>4</td><td>2</td><td>1</td><td>U2i-1,U2i</td></tr><tr><td>步骤1</td><td>√</td><td>√</td><td>√</td><td>1,u2</td></tr><tr><td>步骤2</td><td></td><td></td><td>√</td><td>3,4</td></tr><tr><td>步骤3</td><td></td><td>√</td><td>√</td><td>5,u6</td></tr><tr><td>步骤4</td><td></td><td></td><td>√</td><td>7,u8</td></tr></table></body></html>

对于极化码(8,4,{4,6,7,8},(0,0,0,0))，表达式解释为根据巴氏参数计算出各个子信道的可靠性，选取 $u _ { 4 } , u _ { 6 } , u _ { 7 } , u _ { 8 }$ 作为信息比特， $u _ { 1 } , u _ { 2 } , u _ { 3 } , u _ { 5 }$ 为冻结比特，构造 $_ { \mathrm { N } = 8 }$ 的混合比特。根据传统 SC译码的特性，对第 $i$ 位的译码不仅仅依赖于分裂后极化信道的转移概率，还依赖于前 $i - 1$ 位译码输出。从表1获知，为了获取信息比特位 $u _ { 4 }$ ，需要前三位译码输出，需要四个时钟循环的工作量。然而，前四位的译码输出，根据混合比特位信息可知，只有第4位是信息位，前三位是冻结比特。8位的译码输出需要计算12次MPE（ $8 / 2 \times l o g _ { 2 } 8 = 1 2 \$ 。由表2可知，当第四位译码输出时，需计算8次MPE，为了第四位的译码，付出大约一半的译码延迟代价。综上，在传统 SC 译码带来了译码延迟的提高，以及随之的译码复杂度的提升。

为了克服这一延迟特性，考虑以下编码方案。将原本的第4 位信息比特位作为冻结比特，第五位作为信息比特位。先前的混合比特位方案改为(8,3,{6,7,8},(0,0,0,0,0))。在这种选择方案下，前四位译码输出是冻结比特，对照表1，可知原先的1-4译码时钟循环计算量是冗余的。所以，译码延迟由原先的7个时钟循环降低到3个时钟循环。

根据上述方案，从表2中可以看出子过程1和子过程2是冗余的，MPE 的计算量由12下降到4。在SC 译码算法中，第一阶段中 MPE 的输出 $o u t _ { - } F$ 用于前半部分译码输出比特的后续计算，输出out $_ - G 0$ 和 $o u t \_ G 1$ 用于后半部份译码输出比特的后续计算。采改进后的混合比特方案， $u _ { 1 } , u _ { 2 } , u _ { 3 } , u _ { 4 }$ 是冻结比特,则输出 $o u t _ { - } F$ 的运算是冗余的。图2中的第一部分的四个MPE运算模块可由四个加法器取代，改进后的译码方案如图3所示。因此，针对8位的极化码，如果前四位作为冻结比特位传输，则可以采用如图3的译码方案，可以降低 $57 \%$ 的译码延迟和减少 $60 \%$ 的MPE计算量。

推广到N位的极化码，根据上述译码方案，译码延迟被有效地降低：

$$
L a t e n c y = \left( N - 1 \right) - N / 2 = N / 2 - 1
$$

图2所示的第一阶段的MPE运算模块被图3中加法器取代。分析图1中 MPE三个输出，得出加法器的输出计算量为MPE计算量的1/3。改进后的译码方案MPE运算量：

$$
N u m _ { _ { M P E } } = \left( N / 2 \right) \times 1 / 3 + \left( N / 2 - 1 \right) = 2 N / 3 - 1
$$

![](images/5676d07dbdba388c56a5c366b7c5d395e557bbc0a5c9d0c62224c6a4533492c3.jpg)  
图3改进后的SC译码算法结构

通过改进的编译码方案，SC译码算法的延迟性得到有效的改善。现在，给出改进后的极化码编译码方案：

a）信道可靠性估计，上文中提出的巴氏参数针对BEC信道可靠性估计，针对二进制对称信道（Binary Symmetric Channel,BSC）信道和加性高斯白噪声信道（AdditiveWhiteGaussianNoise，AWGN）则另选估计参数，三种信道选取参数如表3。b）将原先比特混合方案前N/2位中的信息位改变为冻结比特位。c）为了对上一步骤进行译码补偿，将原先比特混合方案后$\mathbf { N } / 2$ 中的冻结比特位改变为信息比特位。

表3不同二进制离散无记忆信道的信道估计参数  

<html><body><table><tr><td></td><td>BSC</td><td>BEC</td><td>AWGN</td></tr><tr><td>密度进化</td><td>√</td><td>√</td><td>√</td></tr><tr><td>巴氏参数</td><td></td><td>√</td><td></td></tr><tr><td>高斯近似</td><td></td><td></td><td>√</td></tr></table></body></html>

针对本文前面8位极化码示例(8,4,{4,6,7,8),(0,0,0,0))，可将原先的信息比特位 $u _ { 4 }$ 变为冻结比特位,再进行译码补偿,将原先的冻结比特位 $u _ { 5 }$ 变为信息比特，改进后的方案(8,4,{5,6,7,8},(0,0,0,0)) 。

表4列出了改进后的SC译码算法与传统SC译码算法的性能对比。在相同的编码长度下，算法改进后相比原来可以降低 $50 \%$ 的译码延迟，减少了 $3 3 \%$ 的MPE运算量。

# 3 译码补偿及仿真

在改进SC算法中，信道可靠性的估计显得尤为重要，会直接影响比特位转换的选择。本文在后半部分 $( u _ { N / 2 + 1 } \sim u _ { N } )$ 将冻结比特位转换为信息比特位，会給译码性能带来影响。作为译码补偿，引入循环冗余校验码[13]（Cyclic Redundancy Check,CRC）模块可作为算法进一步完善的方向。在编码前加入校验码（一般24位)之后，编码的冗余度虽略有增加，编码率由 $\mathbf { k } / \mathbf { N }$ 略下降为k-24/N，但随着码长增加越不明显。

串行抵消单比特翻转译码算法[14]在循环冗余校验码的基础上可以进一步提高译码性能的算法。在传统SC 译码中，信道噪声和译码输出的错误传播是导致译码判定出错的主要原因。错误传播在信源每一位的信号间发生，仅影响误比特率。通常信道噪声只引起1位错，并且随着信噪比或者码长的增加产生1位错的概率更大。因此，只要找到了这个错误位，就可以极大的提高 SC 译码的译码性能。该算法在译码输出结果不能通过循环冗余校验时，将判定序列中不可靠的信息位进行单比特翻转并重新执行SC译码。选取输出序列中信息位对数似然比对应值T个最小判定位，将对应的信息位索引值集合记为 $\mathbf { M } ^ { [ 1 4 ] }$ 。每次从集合M中取出一个值，将对应的判定比特位值翻转，重新进行SC译码输出，直至新的码字可以通过CRC。遍历集合M若未得到有效码字，则译码失败。

表4改进后的SC译码算法与传统译码算法比较（ $N { = } 1 0 2 4$ ）  

<html><body><table><tr><td></td><td>传统 SC 译码</td><td>改进译码算法</td></tr><tr><td>编码长度</td><td>N</td><td>N</td></tr><tr><td>信息比特位数</td><td>0.5N=512</td><td>0.4N=408</td></tr><tr><td>MPEcalc</td><td>N-1= 1023</td><td>2/3N-1=682</td></tr><tr><td>译码延迟系数</td><td>N-1= 1023</td><td>2/3N-1= 511</td></tr><tr><td>码长/延迟系数</td><td>1</td><td>2</td></tr></table></body></html>

![](images/5cabe60ed349f13c4ed3b7ad6845e34a4c027f77cd5451d0439672d7c54a35ee.jpg)  
图4改进后SC译码算法仿真（ $N { = } 1 0 2 4$ ）

可将单比特翻转算法作为改进SC译码算法的译码补偿方案。图4的仿真结果表明，译码性能随比特位转换位数增大而趋于线性比例下降。通过单比特翻转算法的引入，译码性能的补偿允许了冻结比特位转换为信息比特位，使译码输出更加可靠。

# 4 结束语

基于分析极化码编码中的冻结比特位置，将其中的一些特定的信息位和冻结比特位进行位置交换，实现新的混合比特方案。根据传统SC译码算法结构，减少其中的译码冗余计算，降低译码延迟。算法改进的本质是通过牺牲较低的误码率性能来换取大幅度的减少译码延迟。串行抵消单比特翻转译码算法的引入，可以有效的进行译码补偿，降低误码率。现阶段寻求更好的译码补偿手段值得进一步展开深入研究。

# 参考文献：

[1]Shannon C E.A mathematical theory of communication [J]. Bell System Technical Journal,1948,27(3): 379-423.   
[2] Arikan E.Channel polarization: a method for constructing capacityachieving codes for symmetric binary-input memoryless channels [J]. IEEE Trans on Information Theory,2009,55(7): 3051-3073.   
[3]Arikan E.On the origin of polar coding [C]// Proc of IEEE Int. Symp. Inf. Theory.2015.   
[4]王实.5G 移动通信发展趋势与若干关键技术[J].信息通信,2015,12: 253-254.   
[5]ESLAMI, ALI, HOSSEIN P N. A practical approach to polar codes [C]// Proc of IEEE Inf. Theory Workshop.2011.   
[6]田宝玉．信息论基础[M].2版．北京：人民邮电出版社,2016:32-128.   
[7]陈凯．极化编码理论与实用方案研究[D].北京：北京邮电大学,2014.   
[8]Andersson M, Rathi V, Thobaben R. Nested polar codes for wiretap and relay channels [J].IEEE Communications Letters,2010,14(8): 752-754.   
[9]李超.PolarCodes 编译码算法研究及应用[D]．成都：电子科技大学, 2013   
[10] Zhang C, Parhi K K.Low-latency sequential and overlapped architectures for successive cancelltion polar decoder[J]. IEEE Trans on Signal Process, 2013,61 (10): 2429-2441.   
[11] Yuan B,Parhi K K.Low-latency successive-cancellation polar decoder architecture using 2-bit decoding [J]. IEEE Trans on Circuits and Systems, 2014,61 (4): 1241-1254.   
[12] Zhang C,Parhi K K. Latency analysis and architecture design of simplified SC polar decoders [J].IEEE Trans on Circuits Syst.II, Express Briefs,2014, 61 (2): 115-119.   
[13]牛凯．一种循环冗余校验辅助的极化码译码方法：中国,201210202279. 2 [P]. 2014-03-26.   
[14] Orion A,Balatsoukas-Stimming A,Andreas B.A low-complexity improved successive cancellation decoder for polar codes [Cl//Proc of the 48th IEEE Asilomar Conference on Signals,Systems and Computers.2014: 2116-2120.