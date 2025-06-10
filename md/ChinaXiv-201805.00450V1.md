# 基于压缩感知和循环谱理论的信号载频估计方法

谢瑶1，李思敏²，唐智灵1\*

(1.桂林电子科技大学 电子工程与自动化学院，广西 桂林 541004;2.广西科技大学 电气与信息工程学院，广西 柳州545006)

摘要：为实现在低信噪比的情况下对载频进行参数估计，提出了一种算法。首先，根据循环谱理论计算出信号的循环谱；然后，采用压缩感知的方法重新构造信号的循环谱切面；最后，根据信号循环谱切面中的离散谱线位置与信号的载频的关系采用平均法来计算载波频率。数值仿真显示在信号稀疏度较高的情况下，对载波频率的估计精度能控制在 $1 0 ^ { 3 } \mathrm { H z }$ 以下。在低信噪比的情况下，该算法能够有效地实现对信号载频的估计，在工程上具有一定的实用价值。

关键词：循环平稳；参数估计；压缩感知；信号重构中图分类号：TN911.7 doi:10.3969/j.issn.1001-3695.2018.01.0174

Signal carrier frequency estimation based on compressed sensing and cyclic spectrum theory

Xie Yao1, Li Simin², Tang Zhiling (GuilinUniversityofElectronicTechnology)ofInsituteofElectricalEngineering&AutomationGuilinUniversityoflectronic Technology，GuilinGuangxi5410o4,China;（Guangxi UniversityofScience&Technology）ofInstituteofElectrical& Information Engineering Guangxi University of Science & Technology,Liuzhou Guangxi 545o06,China)

Abstract:Parameters esimationofthemodulatedignal,suchscaierfrequencysmbolrate,etc.,istheprecondiionfor signal modulation recognition.Thispaper propose thealgorithm torealize the parameter estimationoftecarrerfrequency under theconditionoflow SNR.Firstly,the algorithmcalculates thecyclic spectrumofthe signal based on thecyclic spectrum theory.Then,itrebuildsthecyclicspectrumofthesignalbythecompressdsensingmethod.Finall,itcalculatesthecarier frequencyusingtheaverage methodaccordingtotherelationshipbetween thepositionofthediscrete spectralineinthesignal cyclespectrum and the carrier frequencyofthe signal.The simulationresults showthattheestimation accuracyof carrier frequency can be controlled below $1 0 ^ { 3 } \mathrm { H z }$ under the condition ofhigh signal sparsity. In the low SNR environment,the algorithm can effectively estimate the carier frequency of the signal, which has certain practical value in engineering.

Key Words: cyclostationarity; parameter estimation; Compressed Sensing; signal reconstruction

# 0 引言

近几十年，随着现代通信技术的高速发展，调制方式识别和信号参数的估计在民用或者军事领域都扮演着非常重要的角色，例如防御灾害、地质、海洋的探查、电子对抗，情报侦察等领域等。而信号调制参数的估计，如调制识别，是成功识别信号调制方式的重要前提，通常情况下，信号调制参数包括：载波频率、码元速率，信号带宽等。

谱相关理论由Gardner等人[1-3深入研究并发展，其优点主要表现在分辨率高、抗干扰能力强、双频率域信息丰富且易于提取等，适用于循环平稳信号的分析。在通信、雷达、遥测、水声、电子对抗等领域中，由于某些人为的或无意的调制，而使大量信号呈现出循环平稳性，因此谱相关理论在信号检测、参数估计、系统辨识、调制识别等现代信号处理诸多领域中得到了越来越深入的研究。其中，载波频率和符号速率在解调中起着重要作用。在军事侦察、住宅无线电管制和软件接收机等非合作通信环境中，这两个参数是解码信号的必要条件。因此，在过去几十年的研究中，越来越受到人们的重视。

估计载波频率的方法有很多，在基于频域分析方面，文献[2]的周期图法和文献[3]的频率居中算法适用于具有很强的载波功率和对称的功率谱密度信号。在基于时域分析方面，文献[3]过零点算法，文献[4]带状谱估计算法（SSCA）计算简单、计算量小，但是对噪声敏感。在基于小波方面，文献[5]和文献[6]介绍了关于小波变换以及基于负熵最大化的算法，去噪性能好，但计算复杂，计算量大。文献[7]提出了计算循环谱截面进行降维处理，使得计算量大大降低，但是适应性差。在改善循环谱算法方面，文献[8，9]通过分析循环谱矩阵，一方面改善循环谱矩阵的计算方法，更方便的提取特征值，另一方面对循环谱进行降维处理，使得循环谱计算量大大降低。文献[10\~12]提出对信号采样值进行数据分段，而且每段数据与前段数据重叠一部分，得到每段信号的循环谱，再进行平均处理，得到信号的循环谱，使得噪声影响降低，提高了信噪比门限。对于在有限数据情况下，改善了算法的有效性。但是其分段次数需人为操纵，使得算法稳定性不高，且增大了算法的计算量。文献[13，14]提出了基于高阶累积量与循环谱相结合对载频进行精确估计的方法，该方法利用了高阶累积量在抗噪声干扰方面的优势，提取信号的特征量。算法精确度高，抗噪强。但计算量较大。由于循环谱在频域上表现出稀疏性，文献[15]提出了采用压缩感知的方法对循环谱进行重构，消除循环谱中的冗余信息，提取信号中的有效信息。但是需要较多的测量次数，且重建精度相对较低。

针对现有算法存在的这些问题，本文提出了一种基于分段正交匹配追踪(StagewiseOMP)的算法。在算法的迭代过程中，每次可以选择多个元素，大大减少了信号重构的时间。此外，算法采用门限值的方式来确定元素，少了元素个数的限定，避免导致元素信息的冗余和缺失；本算法不依赖于信号的稀疏度，对信号的重构有着独到的优势。

# 1 循环谱的计算方法

循环谱是信号平稳分析的常用方法，利用不同的信号循环谱的差异可以对参数不同的信号进行识别。由于平稳噪声不具有循环平稳特性，因此循环谱分析可以在很大程度上将信号与噪声区分开，在信号分析中具有很大的优越性[67]。

设 $\mathbf { x } ( \mathrm { t } )$ 的一阶统计特性均值和二阶统计特性自相关函数具有某些周期 $\mathrm { \Delta T }$ 的特性，则称之为广义周期平稳过程。均值及自相关函数分别为[：

$$
m _ { x } ( t ) = m _ { x } ( t + T )
$$

$$
R _ { x } ( t + \tau / 2 , t - \tau / 2 ) = R _ { x } ( t + T + \tau / 2 , t + T - \tau / 2 )
$$

其中： $\mathrm { T } = { K } / { \alpha }$ ， $\mathrm { ~ K ~ }$ 为整数， $\alpha$ 为周期频率。将周期函数$R _ { x } ( t , \tau )$ 展开傅里叶序列表达式为

$$
R _ { x } ( t , \tau ) = \sum _ { a \in \Phi } R _ { x } ^ { \alpha } ( \tau ) e ^ { i 2 \pi \alpha t }
$$

其中： $R _ { x } ^ { \alpha } ( \tau )$ 为循环自相关函数，是循环频率 $\alpha$ 和时间延迟 $\boldsymbol { \tau }$ 的函数。其表达式为

$$
R _ { x } ^ { \alpha } ( \tau ) = \operatorname * { l i m } _ { t  \infty } \frac { 1 } { T } \int _ { - T / 2 } ^ { T / 2 } R _ { x } ( t + \tau / 2 , t - \tau / 2 ) e ^ { - i 2 \pi \alpha t } d t ( 4 )
$$

若 $\scriptstyle \alpha = 0$ ，则 $R _ { x } ^ { \alpha } ( \tau )$ 为平稳信号的自相关函数。循环相关函数$R _ { x } ^ { \alpha } ( \tau )$ 的傅里叶变换表达式为

$$
S _ { x } ^ { \alpha } ( f ) { = } R _ { x } ^ { \alpha } ( \tau ) e ^ { - i 2 \pi f \tau } d \tau
$$

其中， $S _ { x } ^ { \alpha } ( f )$ 被称为循环谱密度函数。

# 2 压缩感知

奈奎斯特采样定理作为模拟信号和数字信号的桥梁，一直在信号处理起到中流砥柱的作用。信号的采用处理是实现数字信号调制分类识别的前提，随着奈奎斯特信号采样要求的采样率越来越高，并且信号离散后会生成大量的离散数据，给数据存储、传输产生巨大的压力。Candes，Donoho 和 Tao 等人[17,18]提出压缩感知理论（compressed sensing,CS)，为这一问题的解决提供了新的思路，即在信号具有稀疏性的情况下，可以通过优化算法将信号进行精确重构，打破了奈奎斯特定理的限制，有效的降低了采样速率。

对于超宽带信号而言，可以通过寻找其稀疏域，利用少量的压缩数据实现对信号无失真的重构恢复，解除了信号对前端采样设备的依赖[17]。当信号在某一域是稀疏的或者其本身就是稀疏的，则可以通过一个满足一定条件的测量矩阵使得投影后的信号具有稀疏性，而且投影后的信号包含了原信号足够多的信息，可以通过算法重构恢复出原信号。因此，压缩感知理论中的采样频率与信号的采样频率是不相关的，也和原始信号的最高频率不相关，只是与信号本身的性质相关。此外，信号的离散化处理可以不通过奈奎斯特定理来采样信号，而是通过矩阵把信号投影到一个低维空间中[18]。

# 2.1信号的稀疏表示

信号的稀疏性也可称为信号的可压缩性，是指信号在某一组变换基下，其表示的系数只有少数不为零，或者是多数系数都接近零。信号的稀疏分析方法是在一定的先验条件的基础上，利用预先构造出的基函数来有效地表示数据。对于信号来说，首先就是要找到信号的稀疏域。对于信号 $\mathbf { x } \in R ^ { N }$ ，可以由一组正交基的线性组合来表示，即

$$
\begin{array} { r } { x = \sum _ { i = 1 } ^ { N } \theta _ { i } \varphi _ { \mathrm { } _ { i } } = \Psi \Theta } \end{array}
$$

其中： $\Psi = [ \varphi _ { 1 } , \varphi _ { 2 } , \cdots , \varphi _ { N } ]$ 为正交基矩阵，列向量 $\varphi _ { i }$ 为基函数，$\Theta = [ \theta _ { 1 } , \theta _ { 2 } , \cdots , \theta _ { N } ] ^ { T }$ ，是系数向量。如果0只有K个系数较大，则 $\mathbf { x }$ 是可压缩的。信号的稀疏性决定了信号压缩的最佳效果，对于信号 $\mathbf { x }$ ，在压缩处理中只需要保留前K个最大的系数，也不会导致信号的质量出现严重下降。

# 2.2观测矩阵

对于信号 $\mathbf { x } \in R ^ { N }$ ，如果存在正交矩阵 $\Psi$ 使得 $\textbf { x }$ 是K-稀疏，用观测矩阵 $\Phi \in R ^ { M \times N }$ 对信号 $\mathbf { x }$ 进行观测，得到yE $R ^ { M }$ $K { < } \mathbf { M } { < } \mathbf { N }$ 。其表达式为

$$
y = \Phi x
$$

压缩感知中的信号在观测过程中都是非自适应性的，测量矩阵性质的高低，与成功压缩信号和精确恢复重构信号息息相关。设计测量矩阵 $\Phi$ 需要满足一定的条件才能实现信号的重构，2006年Candes、Romberg 和Tao 等人提出了著名的约束等距性（Restricted Isometry Property，RIP)理论，RIP 准则限定了观测矩阵的设计，成为压缩感知奠基性理论，为压缩感知理论的准确性提供了保障。即假定信号 $\textbf { x }$ 的投影稀疏向量0的长度为N，稀疏度为 $\mathrm { ~ K ~ }$ ，对感知矩阵 $\mathsf { A } = \Phi \Psi \in R ^ { M \times N }$ ，若存在常数 $\delta \in$ (0,1)，满足以下不等式：

$$
( 1 - \delta ) \Big \| \Theta \Big \| _ { 2 } ^ { 2 } \leq \Big \| A \Theta \Big \| _ { 2 } ^ { 2 } \leq ( 1 + \delta ) \Big \| \Theta \Big \| _ { 2 } ^ { 2 }
$$

则称感知矩阵A满足K阶约束等距性准则[18，19]。

# 2.3信号重构

压缩采样的成功与否，关键在于能否成功重构原始信号。在压缩感知理论中，由于观测算法的数量小于未知数的数量，信号X的重构问题是一个欠定问题。即，输入为观测值y和感知矩阵 A，在 $\mathbf { y } { = } \mathbf { A } \Theta$ 的约束下求稀疏解或其逼近值，其方程解有无数个。表达式为：

$$
\widehat { \Theta } = \arg \operatorname* { m i n } _ { \Theta \in R ^ { N } } \lVert \Theta \rVert _ { 0 } s . t . \ y = \ A \Theta
$$

0-范数表示0中非零元素的个数，是一个非凸优化的问题，方程难以直接求解。为解决这一问题，通常利用松弛技术采用凸优化问题对其进行逼近。在压缩感知中，会把非凸的目标函数转化为凸函数。转化后的方程为：

$$
\widehat { \Theta } = \underset { \Theta \in \cal R ^ { N } } { \arg \operatorname* { m i n } } \| \Theta \| _ { 1 } s . t . \mathrm {  ~ y = \ A \Theta ~ }
$$

信号的重构算法主要分为优化类算法和贪婪算法。优化类算法包括基追踪法（BasicPursuit,BP）、凸优化算法等算法。贪婪算法包括正交匹配追踪算法（OMP）、正则化正交匹配追踪算法（ROMP）、分段正交匹配追踪算法（STOMP）等算法。信号的重构过程就是利用最优的查询方法找到带有有效频谱信息的频段及其所对应字典中的位置，从而实现信号的恢复。由于查询方法均具有较高的复杂度，具有较高精度的查询能力的方法计算非常复杂，需要考虑或者附加的条件很多，这就导致这些算法在理论上很占优势，应用到实际的工程的优势不大。在实际工程应用中更倾向于贪婪算法。贪婪算法计算复杂程度不高，但对硬件的要求较高。通过尽可能少的迭代次数，查询出最具代表性的向量对原始输入稀疏多频带做加权表示，然后利用加权表达式对信号进行重构[21]。

# 3 载频估计

由整形滤波器的特性， $Q _ { r c } ( f )$ 在 $\scriptstyle \mathbf { f } = 0$ 处取最大值。当 $\alpha = 0$ 时，载波频率可以在其频域被计算。首先计算信号的循环谱$\textstyle { \mathcal { S } } _ { x } ^ { \alpha } ( f )$ ，并求出 $\alpha = 0$ 截面。

以MPSK信号模型为例，假设接收到的信号为：

$$
\mathrm { X ( t ) } = \mathrm { S } ( t ) + \mathrm { n ( t ) }
$$

${ \mathbf { } } S ( t )$ 为MPSK信号， ${ \bf n } ( \mathbf t )$ 为均值为0方差为 $\sigma ^ { 2 }$ 的高斯白噪声。 ${ \mathbf { } } S ( t )$ 的数学表达式为：

$$
\mathsf { S } ( t ) = A e x p \{ j 2 \pi f _ { c } T t + \theta _ { 0 } + \phi ( T t ) \}
$$

其中， $\mathfrak { t } = 1 , 2 , \cdots , \mathtt { N }$ ， $\begin{array} { r } { \phi ( T t ) = \sum _ { i = 1 } ^ { N _ { s } } } \end{array}$ a $\Pi ( T t - i T _ { b } )$ ，αi∈$\left\{ \frac { 2 \pi } { M } l \right\} _ { i = 0 } ^ { M - 1 }$ $\mathrm { ~  ~ N ~ }$ $\mathrm { ~ T ~ }$ $N _ { s }$ 码元个数， $T _ { b }$ 为码元宽度，I（)为脉冲形成函数， $f _ { c }$ 为信号载波频率， $\theta _ { 0 }$ 为信号的初始相位。假设

$$
S _ { c } ^ { \alpha } ( f ) = Q _ { r c } ( f + \alpha / 2 ) Q _ { r c } ^ { * } ( f - \alpha / 2 )
$$

其中，Qrc(f）=sin(πfTo）。 根据表达式 $( 3 ) _ { \sim } ( 5 )$ 可以算出BPSK信号的循环谱为[7]

$$
\begin{array} { r } { S _ { x } ^ { \alpha } ( f ) = \frac { 1 } { 4 T _ { b } } \big [ S _ { c } ^ { \alpha } ( f + f _ { c } ) + S _ { c } ^ { \alpha } ( f - f _ { c } ) + S _ { c } ^ { \alpha + 2 f _ { c } } ( f ) e ^ { - j 2 \theta _ { 0 } } + } \end{array}
$$

$$
S _ { c } ^ { \alpha - 2 f _ { c } } ( f ) e ^ { j 2 \theta _ { 0 } } ]
$$

其中 $\alpha = \pm 2 f _ { c } + k T _ { b }$ ， $\alpha = k T _ { b }$ ， $\mathbf { k }$ 是整数。对于平稳白噪声，其谱密度集中在 $\scriptstyle { \mathfrak { a } } = 0$ 区域。在 $\mathbf { \boldsymbol { a } } \mathbf { \neq } \mathbf { \boldsymbol { 0 } }$ 时，噪声的影响很小。结果表明，基于循环谱的参数估计方法可以有效地抑制噪声。

然后采用贪婪重构算法重新计算循环谱截面 $S _ { x } ^ { 0 } ( f )$ 。贪婪算法中最常用的算法正交匹配追踪算法(OMP)，其目的是通过在多次迭代中查询出最少列向量作为基向量对原始输入的稀疏多频带信号的频域信号进行表示，最终通过这些基向量的加权函数对信号进行重构。算法的过程是在每次迭代中查询所需要的信息和信息对应的位置，然后重新残差，一直满足迭代终止条件时才会停止迭代。在凸优化算法中虽然计算量大和计算复杂度高，但是其鲁棒性比较高，而OMP算法虽然在计算速度上相比凸优化算法有着很大的改善，但是其鲁棒性较低。所以在结合凸优化算法和OMP算法的优点后，提出了正则化正交匹配追踪算法（ROMP)。相比OMP算法，ROMP算法是在每次迭代中会任意选择出列向量，而非只选择一个列向量。因为在随意选择的列向量中可能会出现误选的情况，为了避免每次迭代中过多的误选，ROMP算法通过引入正则化的方法对待选的矩阵作约束，进而降低误选率、减少迭代和提高恢复精度[]。

与OMP算法一样，ROMP算法在信号重构中也需要知道信号的稀疏度来决定在迭代中需要的最大迭代次数。此外，ROMP算法也存在一定的缺陷：当感知输出矩阵中含有噪声的时候，会导致迭代无法停止。在遇见这种情况时，就需要先验的稀疏度来控制迭代的次数。

为了进一步提高迭代速率，分段正交匹配追踪算法（STOMP)是在正交匹配追踪算法的思想基础上加入了分段查询的思想，即在每次迭代时设置一个阀值，当字典中的列向量与残差的相关度大于该阈值的列向量均视为正确的频谱支撑区查询结果，根据算法残差的相关度的情况，阀值的选择一般在$2 { \sim } 3 ^ { [ 1 8 , 1 9 ] }$ 。STOMP 算法实现步骤如下：

a）初始化：稀疏解 $\scriptstyle \Theta = 0$ ，感知矩阵 $\mathbf { \nabla } \cdot \mathbf { A } = \Phi \Psi$ ，输出矩阵y，残差向量 $\scriptstyle \mathbf { e } = \mathbf { y }$ 。支撑集设置为空，即 $I _ { 0 } = \phi$ ，设置阈值TH。

b)残差的后向投影： $u _ { k } = A ^ { T } e _ { k - 1 } ,$ 根据字典的随机性假设，大多数计算得到的值都是均值为0的独立分布的高斯向量。通过比较 $u _ { k }$ 与阈值 TH的大小，得到相对应的A 的列序号集合

J。

c）支撑集：在迭代过程中，每次迭代都更新感知矩阵A，$A _ { t } = A _ { t - 1 } \cup a _ { t }$ ，和支撑集I， $I _ { t } = I _ { t - 1 } \cup J _ { t }$ 。

d）更新残差：用最小二乘法计算 $\widehat { \Theta _ { t } } = \arg \operatorname* { m i n } _ { \Theta } \| y -$ $A _ { t } \Theta _ { t } \| = ( A _ { t } ^ { T } A _ { t } ) ^ { - 1 } A _ { t } ^ { T } y$ 。得到更新后的 $\Theta _ { t }$ 后，利用 $e _ { t } = y - y -$ $A _ { t } \Theta _ { t } .$ 得到新的残差。

STOMP迭代次数要小于OMP的次数，相当于简化了算法，而且在每次迭代过程中会选择多个列向量，由阈值的大小来决定此次选择列向量的个数，每次迭代会选择出多个基向量，收敛速度更快。另外，因为采用分段的阈值来选择基向量，所以信号的重构误差也较小。

最后，搜索通过贪婪算法重构出的循环谱截面 $S _ { x } ^ { 0 } ( f )$ 里面的峰值，利用频率平均法估算载频。其频率平均法公式如下：

$$
\widehat { f _ { c } } \frac { \sum _ { i = 1 } ^ { N } f ( i ) } { N }
$$

综上所述，载频估计的完整算法流程如图1所示。

![](images/90e201cd9c36588ebb19fa1bc78523603fad04c8128bd721a5a1daa7bcfe6193.jpg)  
图1算法流程图

# 4 实验结果分析

# 4.1系数对算法的影响

信号的恢复是压缩感知的关键。信号在某一域表现的稀疏性越稀疏，信号被重构的概率越大。对于本文提到的STOMP算法，门限参数的选择和观察数量的个数对于算法重构的信号效果起着决定性的作用。在信号个数 $N = 2 5 6$ ，阀值取值与稀疏度，观测个数的关系如图2～4所示。

![](images/5867be8e045276308a3e42ae7ffe7e3f0c6ce66d51f4f51deb5a4b5516133fb8.jpg)  
图2 $\scriptstyle \mathrm { t } = 2$ 时重构概率图

![](images/3170e5a29117a6b1975fcc092f202f1c4bf66ff8ce53d37af0723ee265014478.jpg)  
图3 $\scriptstyle \mathrm { t = } 2 . 6$ 时重构概率图

![](images/b1d675020c185c06f0ab615d90a1c7cdc80697f43ce173c71078f8d87fcd543f.jpg)  
图 $4 \ t = 3$ 时重构概率图

从图2\~4可以看出，当信号在某一域的稀疏性越好，需要观测提取的个数越多，信号被重构出来的概率就越大；当算法的阀值取得越大，从原信号中得到的信息就会越少，若需要保证信号被重构出来的效果越好，则需要观测的数据也就越多，而当阀值取得小时，从原信号会提取到冗余的信息，为保证重构效果，需要的观测数量也就越多；当阀值为2.6时，重构效果略优于阈值为2和3的时候。当观测的数量达到一定的数量后，信号就可以被完整的重构出来。

# 4.2循环谱与重构结果

由于平稳噪声和干扰在 $\alpha \neq 0$ 处不呈现谱相关，因此在利用$\alpha \neq 0$ 处的谱相关函数对调制信号进行检测与估计时，可以完全摆脱背景噪声的影响，采用BPSK方式调制的有噪声背景下，在 $\scriptstyle \mathbf { f } = 0$ 的循环谱截面上可以很容易地检测到2倍载频，在背景噪声下检测到载频的存在就完成了信号的检测。本实验采用BPSK信号为例，其仿真参数为：采样频率 $f _ { s } { = } 1 6 0 0 \mathrm { k H z }$ 载波频率 $f _ { c } = 2 0 0 \mathrm { k H z }$ ，码速率 $f _ { b } = 1 0$ kbps，信噪比 $\operatorname { S N R } { = } { - 3 } \ \mathrm { d B }$ ，数据长度 $\scriptstyle \mathbf { N = 1 } 0 0 0$ 。使用MATLAB对BPSK信号进行了循环谱的仿真，并对循环谱 $\scriptstyle \mathrm { f = } 0$ 和 $\alpha = 0$ 的截面仿真。其仿真图形如图 $5 \sim$ 7所示。

![](images/a9bdf506c2e724843c008ea81bf87a3f9dd92a37353467ae4e4f7f8bf27c0c5e.jpg)  
图5BPSK的循环谱

![](images/a2518614050cca33d2b4ad3fbd23e9246d087892c9281e015700182ea70595bc.jpg)  
图6BPSK $\mathbf { f } = 0$ 循环谱截面

![](images/c82c4c24ff6297a48b4d3ca64ac217d5fde00ca2fb61f3c326edd6cf1b6dc7e4.jpg)  
图7BPSK $\alpha = 0$ 循环谱截面

对于 BPSK信号，只有在 $\alpha = \pm 2 f _ { c } + k T _ { b }$ ， $\alpha = k T _ { b }$ ，的截面才能出现循环谱信号。其中 $f _ { c }$ 为载波频率， $T _ { b }$ 为码元周期。对于实信号，在谱相关图中，由于循环谱算法具有对称性，只需要知道 $\alpha \in \left( 0 , \ , + \infty \right)$ 和 $\mathrm { ~ : ~ } \in \left( 0 , \mathrm { ~ . ~ } , + \infty \right)$ 的部分，就可以知道循环谱的图形。

对循环谱截面信号通过STOMP算法进行信号重构得到的

图形如图8所示

![](images/01f6e19d666f965db4d29f52c251c3b6549a3978803c1bbfd5062b440d2c9531.jpg)  
图8BPSK $\mathbf { f } = 0$ 重构图

从图8可以看出，由式（15）可以得出，在 $\mathbf { f } = 0$ 的循环谱截面BPSK信号只在2倍频才有频谱信号。通过搜寻重构图内最大的两处峰值，求出相对应的频率值，就可以得到相应的载频。由上图可以得出测量的峰值为 $4 0 6 \mathrm { K H z }$ 与 $- 3 9 4 \mathrm { K H z } .$ 。与循环谱理论值存在 $6 \mathrm { K H z }$ 的误差。由式（16）得测得到的载波频率$f _ { C } = { \frac { { \frac { \left| { 4 0 6 } \right| } { 2 } } + { \frac { \left| { - 3 9 4 } \right| } { 2 } } } { 2 } } { = } 2 0 0 \mathrm { K H z }$ ，算得载频与实验结果一致。由实验结果分析，循环谱对载频的估计精度在 $1 0 ^ { 3 } \mathrm { H z }$ 。

# 5 结束语

循环平稳理论主要是利用信号的统计参量，如均值和相关函数来研究非平稳信号，被广泛地应用于信号检测算法中。本文分析了应用循环谱理论进行信号检测和信号参数提取的可行性，利用循环谱在频谱区域内具有稀疏性的特点，提出了利用压缩感知的思想对信号的循环谱截面进行信号重构研究。本文采用的分段正交匹配追踪算法（STOMP）是在正交匹配追踪算法的思想基础上加入了分段查询的思想，即在每次迭代时设置一个阀值，来筛选原子，保证了其能够更加精准地重构原始信号。仿真结果表明在选择阀值为2.6情况下，重构信号需要的观测值较少，可以降低算法计算量。在信噪比-3dB的情况下，信号的载频估计与实验提供载频一致，对载波频率的精度可以达到 $1 0 ^ { 3 } \mathrm { H z }$ 以下。该方法在工程上具有一定的实用价值。

# 参考文献：

[1]Gardner WA.Statistical spectral analysis: a non-probabilistic theory [M]. Englewood Cliffs,NJ: Prentice-Hall, 1988: 28-44.   
[2]Gardner WA.Exploitation of spectral redundancy in cyclostationary signals [J].IEEE SP MAG,1991,(4): 14-36.   
[3]Roberts R S,Brown WA,Loomis HH.Computionally efficient algorithms for cyclic spectral analysis [J].IEEE Signal Processing,1991,8 (2): 38-49.   
[4]张娟娟．α稳定分布噪声下数字调制信号的分数低阶循环谱分析[D]. 西安：西安理工大学,20l7.(Zhang Juanjuan.Fractional low-order rotation of digitally modulated signals withα -stable distribution noise ring spectrum analysis [D]. Xi'an: Xi'an University of Technology,2017.)   
[5]吴昊，曹俊纺．一种复杂脉内调制信号的识别算法[J].雷达与对抗, 2017,37(3):27-3o.(Wu Wei,Cao Junfang.Analgorithm for identification

of complex intra-pulse modulation signals [J].Radar& Confrontation,2017, 37 (3): 27-30.)

[6]李强．基于小波谱相关方法的相位编码信号参数估计[J].弹箭与制导 学报,2017,37 (2):135-138.(Li Qiang.Parameter estimation of phasecoded signal based on wavelet spectral correlation method [J].Journal of Projectiles Rockets Missiles and Guidance,2017,37(2):135-138.)

[7]杨伟超，杨新权.Alpha 稳定分布噪声下卫星双信号调制识别[J]．应用 科学学报,2017,35(3):309-316.(Yang Weichao,Yang Xinquan.Satellite dual signal modulation recognition under Alpha-stable distribution noise [J]. Journal of Applied Sciences,2017,35 (3):309-316.)

[8]孔磊，周坤.基于循环谱奇异分解的干扰识别算法[J].军事通信技术, 2013，34 (4):70-74.(Kong Lei,Zhou Kun.Interference recognition algorithm based on singular decomposition of cyclic spectrum[J].Military Communications Technology,2013,34(4): 70-74.)

[9]张洋，彭华．比特谱相关改进循环谱的单通道混合信号参数估计快速 算法[J].信号处理,2016,32(4):404-416.(Zhang Yang,Peng Hua.Fast algorithm for single channel mixed signal parameter estimation based on improved bit-spectral correlation cyclic spectrum [J]. Signal Processing, 2016,32 (4): 404-416.)

[10]徐文会，刘开华，王丽婷.使用改进Welch法估计心率变异功率谱分析 人体疲劳程度[J].生物医学工程学杂志,2016,33(1):67-71,77.(Xu Wenhui, Liu Kaihua, Wang Liting. Evaluation of human fatigue degree using heart rate variation power spectrum using improved welch method [J]. Journal of Biomedical Engineering,2016,33(1): 67-71,77.)

[11]刘锋，郑鹏，张鑫，等．一种改进的循环谱估计算法[J].电路与系统 学报,2013,18(1):397-402.(Liu Feng,Zheng Peng,Zhang Xin,et al.An improved cyclic spectrum estimation algorithm [J]. Journal of Circuits and Systems,2013,18(1):397-402.)

[12]陆亭宇．基于Welch谱估计的认知无线电频谱感知算法研究[D].北京: 北京邮电大学,2015.(Lu Tingyu.Research on cognitive radio spectrum sensing algorithm based on welch spectrum estimation [D]. Beijing: Beijing University of Posts and Telecommunications,2015.)

[13]张文启．基于特征提取的通信信号识别研究[D].兰州：兰州理工大学， 2016.(Zhang Wenqi.Research on identification of communication signals based on feature extraction [D].Lanzhou:Lanzhou University of Technology,2016.)

[14]赵雄文，郭春霞，李景春．基于高阶累积量和循环谱的信号调制方式混 合识别算法[J].电子与信息学报，2016,38(3):674-680.(Zhao Xiongwen, Guo Chunxia,Li Jingchun.A hybrid signal recognition method based on high order cumulant and cyclic spectrum [J].Journal ofElectronics &Information Technology,2016,38(3):674-680.)

[15]黄勋.基于压缩感知的PSK信号参数估计方法[D]．成都：电子科技大 学,2016.(Huang Xun.Parameter estimation method of PSK signal based on compressed sensing [D]. Chengdu: University of Electronic Science and Technology,2016.)

[16]韩小石．一种基于稀疏特性的循环谱估计方法研究[J].信息通信, 2016,161 (5):13-15.(Han Xiaoshi.A cyclic spectrum estimation method based on sparse characteristics [J].Information and Communications,2016, 161 (5): 13-15.)

[17]范虹．非平稳信号特征提取方法及其应用[M].北京：科学出版社， 2013:18-45.(Fan Hong.Non-stationary signal feature extraction method and application [M]. Beijing: Science Press,2013:18-45.)

[18]石光明，林杰，高大化，等．压缩感知理论的工程应用方法[M]．西安： 西安电子科技大学出版社，2017:1-55.(Shi Guangming,Lin Jie,Gao Dahua,et al. Engineering application method of compressed sensing theory [M].Xi'an: Xidian University Press,2017:1-55.)

[19]EladM.稀疏与冗余表示-理论及其在信号与图像处理中的应用[M]. 曹铁勇，杨吉斌，赵斐，等，译．北京：国防工业出版社，2015:7-20. (Elad M. Sparse and redundant representation-theory and its application in signal and image processing [M]. Cao Tieyong,Yang Jibin,Zhao Fei,et al. Beijing: National Defense Industry Press,2015:7-20.)

[20]王福驰．压缩感知的重构算法研究[D].青岛：青岛大学,2017.(Wang Fuchi.Research on reconstruction algorithm of compressed sensing [D]. Qingdao: Qingdao University,2017.)

[21]黄振．稀疏多频带信号的亚奈奎斯特采样与重构算法研究[D].昆明： 云南大学,2015.(Huang Zhen. Sub-Nyquist sampling and reconstruction algorithm for sparse multi-band signals [D]. Kunming: Yunnan University, 2015.)

[22]姚成勇，林云．一种改进的自适应压缩采样匹配追踪算法[J].现代电 信科技,2015,45(1):18-22,29.(Yao Chengyong,Lin Yun.An Improved Adaptive Compression Sampling Matching Tracking Algorithm [J].Modem Telecommunications Technology,2015,45(1):18-22,29.)

[23]倪加明，孙钦者，陆家明．一种改进的稀疏度自适应压缩采样匹配追踪 算法[J].通信技术,2016,49 (8): 992-996.(Ni Jiaming,Sun Qinzhe,Lu Jiaming.An improved sparsity adaptive compression sampling match pursuit algorithm [J]. Communications Technology,2016,49 (8): 992-996.)

[24]田金鹏，刘小娟，郑国莘．一种变步长稀疏度自适应子空间追踪算法 [J]．自动化学报,2016,42(10):1512-1519.(Tian Jinpeng,Liu Xiaojuan Zheng Guojun.A variable-step sparsity adaptive subspace tracking algorithm [J]. Journal of Automation,2016,42 (10):1512-1519.)