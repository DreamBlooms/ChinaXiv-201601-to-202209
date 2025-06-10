# 多径CD3S信号的多滤波器联合估计解调

袁国刚，陈鹏，王永川，高喜俊，闫云斌(陆军工程大学 无人机工程系，石家庄 050003)

摘要：针对多径衰落信道下混沌直接序列扩频（CD3S）信号的解调问题，提出一种基于卡尔曼滤波（KF)、无损卡尔曼滤波（UKF）与最小均方误差(MMSE)滤波联合估计的多径CD3S 信号解调算法．算法根据混沌码同步、信道估计与信息码解调间的差异性与关联性，利用UKF估计混沌码、KF估计信道参数，并通过MMSE滤波重构信息码。三个滤波器均将彼此的估计结果作为系统参数，交替工作，通过联合估计实现信息码的解调。仿真结果表明，无论对时不变信道还是时变信道，算法均可以克服多径衰落与信道噪声的影响，实现了多径信道下CD3S信号的解调。

关键词：混沌直接序列扩频；解调算法；多径衰落信道；卡尔曼滤波；无损卡尔曼滤波；最小均方误差滤波 中图分类号：TN911.3 doi: 10.3969/j.issn.1001-3695.2018.05.0325

# Demodulation of CD3S signals in multipath channel through multiple filters joint estimation

Yuan Guogang,Chen Peng,Wang Yongchuan, Gao Xijun,Yan Yunbin (Dept.of UAV Engineering,Army Engineering University,Shijiazhuang O5ooO3,China)

Abstract: Inorder todemodulatechaoticdirect sequence spread spectrum (CD3S）signals in multipath fadingchannels,this paper proposed a demodulation algorithm based on Kalman Filter(KF),Unscented Kalman Filter(UKF)and minimum mean square error(MMSE）filtr joint estimation.According tothedifference and correlationamong the chaotic code synchronization，thechannel estimationandthe data demodulation,the algorithmestimates thechaoticcode by UKF, estimatesthechannel parameters byKF,andreconstructs thedatabyMMSEfiltering.Thethree fitersrespectivelyuseone another's estimation resultsas the system parametersand work alternately toaccomplish demodulation by joint estimation. Simulationresultsdemonstrate thatthealgorithmcanovercome theinfluenceofmultipath fadingandchannelnoise,no mater whether the channel is ime invariant or time-varying,and realize the demodulationofCD3S signals in multipath chanels.

Key words:chaotic direct sequence spread spectrum(CD3S)；demodulation algorithm;multipath fading channel; Kalman filter(KF); unscented Kalman filter(UKF); minimum mean square error(MMSE) filter

# 0 引言

混沌信号是一种类噪声，宽频谱，非周期信号。混沌直接序列扩频（CD3S）通信用实值混沌序列代替传统伪随机序列对信息码扩频，提高了保密性，降低了截获概率[I-3]。然而混沌信号的非周期性与初值敏感性使得同步混沌扩频码十分困难，解调CD3S信号也因此难以实现。目前关于CD3S信号解调的研究主要是针对理想信道假设，或者只考虑高斯白噪声[4-8]，对多径CD3S信号解调的研究相对较少。

针对受多径信道影响的混沌通信系统，文献[8]提出了一种基于扩展卡尔曼滤波（EKF）的盲均衡算法，把信道均衡问题转化为混沌码与信道参数混合估计问题。该研究只针对未调制信息的混沌信号，不能传输有效的信息。文献[10]在文献[8]的基础上，将CD3S通信系统中信息符号建立为慢变模型，利用EKF估计信息码，实现了信息的传输。在文献[10]的基础上，文献[11]考虑了EKF 线性化误差对解调性能的影响，提出一种基于无损卡尔曼滤波（UKF）的CD3S信号解调算法。文献[12]考虑了非高斯噪声对解调性能的影响，提出一种基于粒子滤波（PF）的CD3S信号解调算法。然而，上述研究将信息符号建立为慢变模型，忽略了信息码状态独立性对非线性滤波器性能的影响，使得扩频因子较小时解调性能下降[4]。此外，信道参数估计问题属于线性估计问题，使用非线性估计算法估计信道参数，增加了系统复杂度，却不能提高估计精度。

由于混沌码同步属于非线性估计问题，信道参数估计属于线性估计问题，本文利用KF估计信道参数，利用UKF估计混沌码。考虑到均衡与解调的本质均是重构信息信号，而MMSE均衡算法可以使估计的均方误差最小化，本文使用MMSE 算法估计信息码。由于实现混沌码估计、信道参数估计与信息码估计均需要其他两者的估计结果作为系统参数，本文将三者的估计交替进行，通过联合估计实现CD3S信号解调。

# 1多径信道下CD3S系统模型

图1给出了多径衰落信道下CD3S通信系统的模型结构。

![](images/24f3b15dfe15eae45b067d0426c004f574445c5d6e90d35043ae13ea8752be09.jpg)  
图1CD3S通信系统模型

在发射机端，用混沌序列中的 $N$ 个点$x ( n = 1 + ( k - 1 ) N , \cdots , k N )$ 对每一个比特的信息码 $b \big ( k \big ) \in \big \{ - 1 , 1 \big \}$ 进行扩频。 $\mathrm { C D 3 S }$ 信号 $s ( n )$ 为二进制信息码 $b { \big ( } n { \big ) }$ 与混沌序列 $x { \big ( } n { \big ) }$ 相乘得到，即

$$
s ( n ) \mathop { = } x ( n ) b ( n )
$$

其中混沌序列 $x ( n )$ 由如图2所示的混沌动力学系统生成，可由混沌映射方程 $x { \big ( } n + 1 { \big ) } = f { \Big [ } x { \big ( } n { \big ) } { \Big ] }$ 描述。

![](images/355ac1f59782f680d0637a57792e4f012b0553506a54cc9a24f4af4ef05957dc.jpg)  
图2混沌动力学系统示意图

CD3S信号 $s ( n )$ 通过多径衰落信道传输到接收端。多径信道有多条不同的路径，每条路径都有不同的延时与衰落，接收信号可表示发射信号 $s ( n )$ 的延时加权和，即

$$
r \big ( n \big ) = \sum _ { i = 0 } ^ { L - 1 } a _ { i } \big ( n \big ) s \big ( n - i \big ) + \nu \big ( n \big )
$$

其中： $\nu \big ( n \big ) \sim N ( 0 , R )$ 信道噪声， $L$ 为路径数，$\pmb { a } ( n ) \mathrm { = } [ a _ { 0 } ( n ) , a _ { 1 } ( n ) , \cdots , a _ { L - 1 } ( n ) ] ^ { \mathrm { T } }$ 为信道参数。

结合式（1）（2)，通过多径信道的CD3S信号可由如下方程描述：

$$
r \big ( n \big ) = \sum _ { i = 0 } ^ { L - 1 } a _ { i } \big ( n \big ) x \big ( n - i \big ) b \big ( n - i \big ) + \nu \big ( n \big )
$$

在式(3)中，若将 $a _ { i } \left( n \right) x \left( n - i \right)$ 整体视为信道参数，则可以将多径CD3S信号的解调问题考虑为传统的信道均衡问题。本文所提的解调算法，即是利用UKF估计混沌序列 $x { \big ( } n { \big ) }$ ，KF估计信道参数 $\pmb { a } ( n )$ ，然后通过MMSE 滤波估计信息码 $b { \big ( } n { \big ) }$ 。三个滤波器交替工作，均将其他两个滤波器的估计结果作为完成自身估计的系统参数，通过联合估计从带噪声的接收信号 $r ( n )$ 中解调出信息码 $\hat { b } _ { d } \left( k \right)$ 。

# 2 多滤波器联合估计解调算法

# 2.1 UKF估计混沌码

假设信道中有两条路径，混沌码估计问题的状态空间模型可由如下系统方程描述：

$$
\left\{ \begin{array} { l l } { { \hat { x } } { \displaystyle { \big ( n \big ) } = f \Big [ { \hat { x } } { \big ( n - 1 \big ) } \Big ] } } \\ { r { \big ( n \big ) } = \sum _ { i = 0 } ^ { 1 } { \hat { a } } _ { i } { \big ( n - 1 \big ) } { \hat { b } } { \big ( n - i \big ) } { \hat { x } } { \big ( n - i \big ) } + \nu { \big ( n \big ) } } \end{array} \right.
$$

其中 $\pmb { a } ( n { - } 1 )$ 与 $\hat { b } \big ( n \big )$ 为上一时刻的信道参数与信息码估计结果。

由式(4)描述的状态空间模型可知混沌码估计问题为非线性估计问题。现有的非线性估计算法主要有EKF、UKF与PF。其中EKF需要对系统进行线性化近似，存在线性化误差。UKF与 PF均不存在线性化误差，在高斯分布噪声干扰下，两种算法估计精度接近，UKF 算法运算量更小[13]。本文选择UKF 估计混沌码，针对式(4)描述的状态空间模型，UKF估计混沌码主要步骤如下[14,15];

（a）设置初值。

$$
\begin{array}{c}  \begin{array} { l } { \qquad \quad \hfill \{ \hat { x } \big ( 0 \big ) = \mathrm { E } \Big [ x \big ( 0 \big ) \Big ] } \\ { \qquad \quad \hfill \{ P \big ( 0 \big ) = \mathrm { E } \Big \{ \Big [ x \big ( 0 \big ) - \hat { x } \big ( 0 \big ) \Big ] \Big [ x \big ( 0 \big ) - \hat { x } \big ( 0 \big ) \Big ] ^ { \mathrm { T } } \Big \} } \end{array}   \end{array}
$$

（b）计算 sigma点。

$$
\left\{ \begin{array} { l l } { \chi _ { 0 } \left( n - 1 \right) = \hat { x } \left( n - 1 \right) } \\ { \chi _ { 1 } \left( n - 1 \right) = \hat { x } \left( n - 1 \right) + \left( \sqrt { \left( 1 + \lambda \right) } P \left( n - 1 \right) \right) } \\ { \chi _ { 2 } \left( n - 1 \right) = \hat { x } \left( n - 1 \right) - \left( \sqrt { \left( 1 + \lambda \right) } P \left( n - 1 \right) \right) } \end{array} \right.
$$

其中是 $\begin{array} { r } { \lambda = \alpha ^ { 2 } ( 1 + \kappa ) - 1 } \end{array}$ 一个尺度因子， $\alpha$ 决定 $\hat { \pmb { x } }$ 周围sigma点的分布，通常取一个很小的正值 $\scriptstyle ( 0 < \alpha \leq 1 )$ 。常量 $\kappa$ 取值一般为2。

（c）时间更新。

$$
\chi _ { n | n - 1 } = f ( \chi _ { n - 1 } )
$$

$$
\overline { { \hat { x } } } \left( n \right) = \sum _ { i = 0 } ^ { 2 } W _ { i } ^ { m } \chi _ { i , n | n - 1 }
$$

$$
\overline { { { P } } } \big ( n \big ) = \sum _ { i = 0 } ^ { 2 } { W _ { i } } ^ { p } \Big ( \chi _ { i , n | n - 1 } - \overline { { { \hat { x } } } } \big ( n \big ) \Big ) \Big ( \chi _ { i , n | n - 1 } - \overline { { { \hat { x } } } } \big ( n \big ) \Big ) ^ { \mathrm { T } }
$$

$$
\begin{array} { r } { \mathbf { y } _ { n | n - 1 } = \hat { a } _ { 0 } \big ( n - 1 \big ) \hat { b } \big ( n \big ) \chi _ { n | n - 1 } + \hat { a } _ { 1 } \big ( n - 1 \big ) \hat { b } \big ( n - 1 \big ) \chi _ { n - 1 } } \end{array}
$$

$$
\overline { { \hat { y } } } \left( n \right) = \sum _ { i = 0 } ^ { 2 } W _ { i } ^ { m } y _ { i , n | n - 1 }
$$

$$
\scriptstyle \chi _ { n - 1 } = \left[ \chi _ { 0 } ( n - 1 ) , \chi _ { 1 } \left( n - 1 \right) , \chi _ { 2 } \left( n - 1 \right) \right]
$$

$$
\begin{array} { l l l } { { \displaystyle \chi _ { n | n - 1 } = \left[ \chi _ { _ { 0 , n | n - 1 } } , \chi _ { _ { 1 , n | n - 1 } } , \chi _ { _ { 2 , n | n - 1 } } \right] \quad , \quad } } & { { \displaystyle \quad y _ { n | n - 1 } = \left[ y _ { _ { 0 , n | n - 1 } } , y _ { _ { 1 , n | n - 1 } } , y _ { _ { 2 , n | n - 1 } } \right] } } \\ { { \displaystyle W _ { 0 } ^ { m } = \frac { \lambda } { 1 + \lambda } \quad \quad } } & { { , \quad } } & { { \displaystyle W _ { 0 } ^ { p } = \frac { \lambda } { 1 + \lambda } + 1 - \alpha ^ { 2 } + \beta } } \end{array}
$$

（d）测量更新。

$$
P _ { \overline { { { y y } } } } = \sum _ { i = 0 } ^ { 2 } W _ { i } ^ { p } \bigg [ y _ { i , n | n - 1 } - \overline { { { \hat { y } } } } \left( n \right) \bigg ] \Big [ y _ { i , n | n - 1 } - \overline { { { \hat { y } } } } \left( n \right) \Big ] ^ { \mathrm { T } } + R
$$

$$
P _ { \overline { { { x y } } } } = \sum _ { i = 0 } ^ { 2 } W _ { i } ^ { p } \Big [ \chi _ { i , n | n - 1 } - \overline { { { \hat { x } } } } \big ( n \big ) \Big ] \Big [ y _ { i , n | n - 1 } - \overline { { { \hat { y } } } } \big ( n \big ) \Big ] ^ { \mathrm { T } }
$$

$$
K _ { x } ( n ) = P _ { \overline { { x } } } P _ { \overline { { y y } } } ^ { - 1 }
$$

$$
\hat { x } \big ( n \big ) = \overline { { \hat { x } } } \big ( n \big ) + K _ { x } \big ( n \big ) \Big [ r \big ( n \big ) - \overline { { \hat { y } } } \big ( n \big ) \Big ]
$$

$$
P ( n ) { = } \overline { { P } } ( n ) { - } K _ { x } \left( n \right) P _ { \overline { { y y } } } K _ { x } ^ { - 1 } \left( n \right)
$$

# 2.2KF估计信道参数

信道参数通常是缓慢变化的，信道参数估计问题可用如下状态空间模型描述：

$$
\left\{ \begin{array} { l l } { \displaystyle { \hat { a } \left( n \right) = I \hat { a } \left( n - 1 \right) + w \left( n \right) } } \\ { \displaystyle r \left( n \right) = \sum _ { i = 0 } ^ { 1 } \hat { x } \left( n - i \right) \hat { b } \left( n - i \right) \hat { a } _ { i } \left( n \right) + \nu \left( n \right) = H _ { , a } \hat { a } \left( n \right) + \nu \left( n \right) } \end{array} \right.
$$

其中： $\textbf {  { I } }$ 为单位矩阵， $w \big ( n \big ) \sim N ( 0 , Q )$ ， ${ \hat { x } } { \big ( } n { \big ) }$ 与 $\hat { b } \big ( n \big )$ 为已经获得的混沌码估计值与信息码估计值，${ \pmb H } _ { a } = \left[ \hat { b } \big ( n \big ) \hat { x } \big ( n \big ) , \hat { b } \big ( n - 1 \big ) \hat { x } \big ( n - 1 \big ) \right]$ 为观测矩阵。

式（17）描述的状态空间模型为线性系统状态空间模型，故可以选择最优线性估计方法 KF 估计信道参数。针对式(17)描述的状态空间模型，KF估计信道参数主要步骤如下：

a）时间更新。

$$
\hat { \pmb { a } } _ { n | n - 1 } = \hat { \pmb { a } } \big ( n - 1 \big )
$$

$$
\bar { P } _ { a } \left( n \right) = I P _ { a } \left( n - 1 \right) I + Q
$$

b）测量更新。

$$
{ \cal K } _ { a } = \overline { { { { \cal P } } } } _ { a } \left( n \right) { \cal H } _ { a } ^ { \mathrm { T } } \Big [ { \cal H } _ { a } \overline { { { { \cal P } } } } _ { a } \left( n \right) { \cal H } _ { a } ^ { \mathrm { T } } + { \cal R } \Big ] ^ { - 1 }
$$

$$
\hat { \mathbf { a } } \left( n \right) = \hat { \mathbf { a } } _ { n | n - 1 } + \mathbf { K } _ { a } \Big [ r ( n ) - { \pmb { H } } _ { a } \hat { \mathbf { a } } _ { n | n - 1 } \Big ]
$$

$$
P _ { a } \left( n \right) { = } ( { \cal I - { \cal K } } _ { a } { \cal H } _ { a } ) \overline { { { P } } } _ { a } \left( n \right)
$$

# 2.3 信息码估计

2.3.1MMSE算法与KF估计信息码的关系

针对均衡后的CD3S信号，文献[10\~12]根据扩频通信系统中信息码 $b { \big ( } n { \big ) }$ 慢变于混沌码 $x { \big ( } n { \big ) }$ ，建立了如下信息码估计的状态空间模型：

$$
\left\{ \begin{array} { l l } { { \hat { b } } { \big ( } n + 1 { \big ) } = { \hat { b } } { \big ( } n { \big ) } } \\ { { \hat { s } } { \big ( } n + 1 { \big ) } = f { \Big [ } { \hat { x } } { \big ( } n { \big ) } { \Big ] } { \hat { b } } { \big ( } n + 1 { \big ) } + \nu { \big ( } n { \big ) } } \end{array} \right.
$$

其中 $\hat { s } ( \boldsymbol n )$ 是CD3S 信号。针对式(23)描述的状态空间模型，文献[11\~13]分别利用了EKF、UKF、PF三种非线性滤波算法估计信息码。然而观察可发现式（23)为线性系统模型，使用EKF、UKF与PF估计信息码均等效为KF估计信息码。KF估计信息码的主要步骤如下：

（a）时间更新。

$$
\hat { b } _ { { } _ { n + 1 | n } } = \hat { b } { } ( n )
$$

$$
\overline { { P } } _ { b } \left( n + 1 \right) = P _ { b } \left( n \right)
$$

(b）测量更新。

$$
K _ { b } = \overline { { P } } _ { b } \left( n + 1 \right) H ^ { \mathrm { T } } \left[ H \overline { { P } } _ { b } \left( n + 1 \right) H ^ { \mathrm { T } } + R \right] ^ { - 1 }
$$

$$
\hat { b } \big ( n + 1 \big ) = \hat { b } _ { n + 1 | n } + K _ { b } \Big [ \hat { s } ( n + 1 ) - H \hat { b } _ { n + 1 | n } \Big ]
$$

$$
P _ { b } \left( n + 1 \right) = ( I - K _ { b } H ) \overline { { P } } _ { b } \left( n + 1 \right)
$$

其中 $\scriptstyle H = f \left[ { \widehat { x } } { \left( n \right) } \right]$ 。

上述KF算法适用于一个扩频周期内的信息码估计。在一个扩频周期外，信息码发生改变，不满足式(23)描述的状态空间模型，KF算法会出现较大误差。此外，KF属于递推滤波，信息码改变造成的估计误差会传递到后续的估计中，影响下一个扩频周期的精度。

由于信息码状态间是相互独立的，根据式（23）中状态方程得到的下一状态预测值 $\hat { b } _ { \scriptscriptstyle n + 1 | n }$ 并不可信。一种降低估计误差的方法是通过调整卡尔曼增益 $K _ { b }$ ，将式（27）中 $\hat { b } _ { \scriptscriptstyle n + 1 | n }$ 权值置为0,即 $\hat { b } _ { { } _ { n + 1 | n } } - K _ { b } { \hat { H { } } } \hat { b } _ { n + 1 | n } { = } 0$ 。此时可得卡尔曼增益 $\boldsymbol { K } _ { b } = \boldsymbol { H } ^ { - 1 }$ ，信息码估计值为

$$
\hat { b } \big ( n + 1 \big ) = H ^ { - 1 } \hat { s } ( n + 1 )
$$

观察可以发现式(29)与迫零均衡算法相同，由式(29)得到的估计值虽然无偏的，但是未考虑噪声的影响，估计的精度较低。

信息码状态间相互独立，则可以用信息码估计的期望值作为预测值，假设信息码为1与为-1的概率均为 $\%$ ，则信息码预测值

$$
\hat { b } _ { n + 1 | n } { = } 0
$$

结合验前误差方差定义 $\overline { { P } } _ { b } \left( n + 1 \right) = \mathrm { E } \left[ \tilde { b } _ { { n + 1 } | { n } } \tilde { b } _ { { n + 1 } | { n } } ^ { \mathrm { T } } \right]$ ，可得验前误差 方差

$$
\overline { { P } } _ { b } \left( n + 1 \right) = 1
$$

其中 $\tilde { b } _ { \scriptscriptstyle n + 1 | n } = b \big ( n \big ) - \hat { b } _ { \scriptscriptstyle n + 1 | n }$ 为预测误差。将式(31)代入式(26)可得卡尔曼增益

$$
\boldsymbol { K } _ { b } = \boldsymbol { H } ^ { \mathrm { T } } \left[ \boldsymbol { H } \boldsymbol { H } ^ { \mathrm { T } } + \boldsymbol { R } \right] ^ { - 1 }
$$

将式(32)(30)代入式(27)可得信息码估计值

$$
\hat { b } \big ( n + 1 \big ) = H ^ { \mathrm { T } } \Big [ H H ^ { \mathrm { T } } + R \Big ] ^ { - 1 } \hat { s } ( n + 1 )
$$

不难发现式(33)与MMSE滤波等效。KF是线性系统的最优估计算法，要求待估计状态具有马尔科夫性，当用于估计状态相互独立的信息码时，等效于MMSE 算法。式(33)得到的估计值虽然是有偏的，但是满足KF的最小均方误差准则，有利于将估计误差最小化。本文使用式(33)描述的MMSE 滤波估计信息码。

# 2.3.2MMSE滤波估计信息码

当信道中包含两条路径时，接收信号 $r ( n )$ 可表示为

$$
r \left( n \right) = \hat { a } _ { 0 } \left( n \right) \hat { x } \left( n \right) \hat { b } \left( n \right) + \hat { a } _ { 1 } \left( n \right) \hat { x } \left( n - 1 \right) \hat { b } \left( n - 1 \right) + \nu \left( n \right)
$$

对式（34）进行MMSE滤波可得解调输出

$$
\hat { b } _ { \mathrm { d } } \left( n \right) = H _ { \mathrm { d } } ^ { \mathrm { T } } \Big [ H _ { \mathrm { d } } H _ { \mathrm { d } } ^ { \mathrm { T } } + R \Big ] ^ { - 1 } \Big [ r ( n ) - \hat { a } _ { \mathrm { l } } \left( n \right) \hat { x } \big ( n - 1 \big ) \hat { b } \big ( n - 1 \big ) \Big ]
$$

其中 $H _ { \mathrm { d } } = \hat { a } _ { 0 } \big ( \boldsymbol n \big ) \hat { x } \big ( \boldsymbol n \big )$ 。

完成下一时刻混沌码与信道参数的估计还需要信息码估计值 ${ \hat { B } } { \big ( } n + 1 { \big ) }$ 作为系统参数。接收信号 $r { \big ( } n + 1 { \big ) }$ 可表示为

$$
r \left( n + 1 \right) = { \hat { a } } _ { 0 } \left( n \right) f { \bigl [ } { \hat { x } } ( n ) { \bigr ] } { \hat { b } } { \bigl ( } n + 1 { \bigr ) } + { \hat { a } } _ { 1 } \left( n \right) { \hat { x } } { \bigl ( } n { \bigr ) } { \hat { b } } { \bigl ( } n { \bigr ) } + \nu { \bigl ( } n + 1 { \bigr ) }
$$

对式（36）进行MMSE滤波可得下一时刻的信息码估计值

$\begin{array} { r } { \hat { b } \big ( n + 1 \big ) = \mathrm { s g n } \Big \{ H _ { \mathrm { b } } ^ { \mathrm { T } } \Big [ H _ { \mathrm { b } } H _ { \mathrm { b } } ^ { \mathrm { T } } + R \Big ] ^ { - 1 } \Big [ r ( n + 1 ) - \hat { a } _ { 1 } \big ( n \big ) \hat { x } \big ( n \big ) \hat { b } \big ( n \big ) \Big ] \Big \} } \end{array}$ 其中 $H _ { \mathrm { b } } = \hat { a } _ { 0 } \big ( n \big ) f \big [ \hat { x } \big ( n \big ) \big ]$

# 2.4解调算法完整描述

多径衰落信道下CD3S信号的多滤波器联合估计解调算法如图3所示：

![](images/3185167e27357f9be09695851240ecf68a70f7aa296eb948613e04f59c2fe110.jpg)  
图3多滤波器联合估计解调算法框图

算法完整描述如下：

先对各状态变量赋初值，包括混沌码 ${ \hat { x } } { \big ( } n { \big ) }$ ，信道参数$\hat { \pmb a } ( { \boldsymbol n } )$ ，信息码 $\hat { b } \big ( n \big )$ ，误差协方差矩阵 $P$ 与 $\pmb { P } _ { a }$ 。从 $\scriptstyle { \mathrm { n = } } 2$ 开始循环，每个循环分为四步：

a)将上一循环得到的 ${ \hat { b } } ( n )$ 与 $\hat { \pmb { a } } \big ( \ b { n } - \ b { 1 } \big )$ ，作为式（4）中观测方程的参数，并通过UKF估计 $n$ 时刻的混沌码状态得到 ${ \hat { x } } { \big ( } n { \big ) }$ 。

b)将上一循环得到的 ${ \hat { b } } ( n )$ 与本循环得到的 ${ \hat { x } } { \big ( } n { \big ) }$ ，作为式（17）中观测方程的参数，并通过KF估计 $n$ 时刻的信道参数得到 $\hat { \pmb a } ( { \boldsymbol n } )$ 。

c)以本循环得到的 ${ \hat { x } } { \big ( } n { \big ) }$ 与 $\hat { \pmb a } ( { \boldsymbol n } )$ ，及上一循环得到的${ \hat { x } } { \big ( } n - 1 { \big ) }$ 与 ${ \hat { b } } { \big ( } n - 1 { \big ) }$ 为参数，通过式（35）得到信息码的解调输出值 $\hat { b } _ { \mathrm { d } } ^ { \phantom { \dagger } } ( n )$ ，

d)以本循环得到的 ${ \hat { x } } { \big ( } n { \big ) }$ 与 $\hat { \pmb { a } } ( \pmb { n } )$ 为参数，通过式（37）得到进入下一循环的信息码估计值 $\hat { b } \big ( n { + } 1 \big )$ 。

在循环外，对一个扩频周期内的 $\hat { b } _ { d } \left( n \right)$ 判决得到 $\hat { b } _ { d } \left( k \right)$ 。

# 3 仿真分析

仿真使用改进型Logistics混沌序列对信息码进行扩频，改进型Logistics 序列映射方程为 $x { \big ( } n { \big ) } = 1 - 2 { \Big [ } x { \big ( } n - 1 { \big ) } { \Big ] } ^ { 2 }$ 。生成CD3S信号的扩频比为50。

假设多径信道中共包含三条路径。通常情况下，经过最短路径的信号功率最强,其它路径包含较微弱的接收信号功率。因此，定义最短路径参数为 $a _ { 0 } \left( n \right) { = } 1$ 。对于时不变信道，假设信道参数为

$$
\pmb { a } \left( n \right) = \left[ 1 , \ 0 . 3 5 , \ - 0 . 2 \right] ^ { \mathrm { T } }
$$

对于时变信道，假设信道参数为

$$
\begin{array} { l } { a _ { 0 } \left( n \right) = 1 + 0 . 1 \sin ( 0 . 0 1 n ) } \\ { a _ { 1 } \left( n \right) = 0 . 3 5 + 0 . 2 \sin ( 0 . 0 0 5 n ) } \\ { a _ { 2 } \left( n \right) = - 0 . 2 + 0 . 1 \cos ( 0 . 0 1 n ) } \end{array}
$$

图4给出了在信噪比为20dB时，对时不变信道与时变信道的信道参数估计结果。图5为信道参数估计均方误差随信噪比变化的曲线。如图5所示，低信噪比下算法对时变信道与时不变信道估计精度接近，在高信噪比下算法对时不变信道的估计精度更高。

![](images/e343c660634a47da652fbb721661df131fb58292cb49276e2aa301179c525690.jpg)  
图4信道参数估计结果

![](images/2b31f6a607870ac835189ab9d2c44c985bf289d276c456c685817ade4ac57899.jpg)  
图5信道参数估计均方误差随信噪比变化曲线

出现图5所示现象的原因是信道参数估计精度同时受信道噪声水平与信道参数估计问题建模准确程度两个因素影响。信噪比低时，信道噪声功率大，信道噪声是影响估计精度的主要因素，故在低信噪比条件下算法对时变信道与时不变信道的估计精度接近。在信噪比高时，信道噪声对估计精度的影响降低，此时状态空间模型的准确程度是影响估计精度的主要因素，式（17）建立的状态空间模型可以准确描述时不变信道，在描述时变信道时存在误差，故在高信噪比条件下算法对时不变信道的估计精度更高。由于KF属于递推估计，对于参数变化缓慢的信道环境，利用式（17）描述的状态空间模型估计信道参数依然具有工程实践意义。

图6给出了在式（38）描述信道条件下，信噪比为20dB时的混沌码同步波形。图7出了在时不变信道与时变信道下下，混沌码同步均方误差随信噪比变化的曲线。如图7所示，受算法信道参数估计性能的影响，在低信噪比时，算法在不同信道条件下的同步精度接近，在高信噪比时，算法在时不变信道表现出更高同步精度。

![](images/ae76a2eae5b2124390d5300b293c73a862e340bdecef467df9e7c481375a7548.jpg)  
图6混沌码同步波形

![](images/1fcc331f58f5f93f6ad4e5a226e105d64755a977246a72cb1f04a2b077b587ea.jpg)  
图7混沌码同步均方误差随信噪比变化曲线

图8给出了CD3S信号解调波形示意图。对MMSE滤波得到的信息码估计值 $\hat { b } _ { d } \left( n \right)$ 在一个扩频周期内进行积分判决，可以得到信息码解调值 $\hat { b } _ { d } \left( k \right)$ 。由图8（b）也可以看出CD3S信号具有良好的类噪声性与保密性。

图9给出了在信道参数为式（38）和式（39）的条件下，本文所提多滤波器解调与文献[10]所提的EKF解调的误码率性能对比曲线。如图9所示，当信道条件相同时，在低信噪比条件下多滤波器解调与EKF解调误码性能接近，在高信噪比条件下多滤波器解调误码率更低。这是因为在混沌码同步时，EKF需要对式（4）描述的状态空间模型进行局部线性化，存在线性化误差，而多滤波器解调使用的UKF不存在线性化误差。当信噪比较低时，信道噪声是影响混沌码同步精度的主要因素，线性化误差影响较小，两种算法误码性能接近，当信噪比升高时，信道噪声影响降低，线性化误差对解调性能的影响提升，多滤波器解调算法表现出更优的误码性能。

![](images/7e454a94bc53c057c2e0d843ad68303d14149854bd0af4263a8e109730fe9aeb.jpg)  
图8CD3S信号解调波形示意图

(a)原信息码，(b)CD3S信号，(c)MMSE估计得到的信息序列，(c)判决估计结果得到的信息码

# 4 结束语

本文针对受多径衰落信道影响的CD3S信号，提出了一种基于多滤波器联合估计的CD3S信号解调算法。考虑到混沌扩频码同步、信道参数估计与信息码解调间的差异性，本文分别利用UKF、KF与MMSE三种滤波器完成混沌码同步、信道参数估计与信息码解调。由于混沌码、信道参数、信息码的估计之间又相互关联，本文将三者的估计交替进行，通过联合估计完成混沌码同步与信道估计，并实现多径信道下CD3S信号的解调。仿真结果表明，本文所提出的多滤波器联合估计解调算法具有良好的误码性能。

![](images/d7ec8c21b9877569d90e8b04aeb996581aabd37bec7e841801d815ac9ee7e38d.jpg)  
图9误码率性能对比曲线

# 参考文献：

[1]Berber S M.Probability of error derivatives for binary and chaos-based CDMA Systems in wide-band channels [J].IEEE Trans on Wireless Communications,2014,13 (10): 5596-5606.   
[2]Tayebi A，Berber S,Swain A．Performance analysis of chaotic DSSS-CDMA synchronization under jamming attack [J]. Circuits Systems & Signal Processing,2016,35 (12): 1-22.   
[3] 于一丁，王永川，王长龙．基于实值混沌序列的 DSSS 系统性能分析 [J]．计算机应用研究，2017，34（11):3402-3404.（Yu Yiding，Wang Yongchuan，Wang Changlong.Performance analysisof DSSS system based on real chaotic sequences [J]. Application Research of Computers, 2017,34 (11): 3402-3404.)   
[4] 甘露，熊波.DM-UKF 混沌拟合破译混沌直接序列扩频通信[J].物理 学报,2012,61 (22): 210504.(Gan Lu,Xiong Bo.Breaking chaotic direct sequence spread spectrum communication by DM-UKF chaotic fitting [J]. Acta Physica Sinica,2012,61(21): 210504.)   
[5]郭静波，徐新智，史启航，等．混沌直接序列扩频信号盲解调的硬件电 路实现[J].物理学报，2013,62(11):110508.(Guo Jingbo,Xu Xinzhi, Shi Qihang，et al. Hardware implementation for blind demodulation method for chaotic direct sequence spread spectrum signals [J].Acta Physica Sinica,2013,62(11):110508.)   
[6]Yahia M,Radi D,Gardini L,et al. Use of Chebyshev polynomial Kalman filter for pseudo-blind demodulation of CD3S signals[J].International Journal of Control,Automation and Systems,2015,13 (5): 1-8.   
[7]Nosrati K,Rostami A S,Pariz,et al. A private secure communication schemeusing UKF-based chaossynchronization [J].Journal of Engineering Science and Technology Review.2015,8 (2): 96-15.   
[8]Li Ting,Zhao Dexin,Huang Zhiping,et al. Blind demodulation of chaotic direct sequence spread spectrum signals based on Particle Filters [J]. Entropy,2013,15 (9):3877-3891.

[9]Zhu Zhiwen，Leung H. Adaptive blind equalization for chaotic communication systems using Extended-Kalman Filter[J]. IEEE Trans on Circuits and Systems-I,2001,48 (8): 979-989.

[10]徐新智，郭静波．基于状态估计的混沌直扩信号联合均衡与解调[J]. 物理学报,2011,60 (29): 020510.(Xu Xinzhi,Guo Jingbo.A novel unified equalization and demodulation of chaotic direct sequence spread spectrum signal based on state estimation [J].Acta Physica Sinica,2O11,60 (2）, 020510.)

[11] Xu Xinzhi,Guo Jingbo.Combined equalization and demodulation of chaotic direct sequence spread spectrum signals for multipath channels [J]. Circuits,Systems & Signal Processing,2013,32(6): 2957-2969.

[12]Li Ting，Zhao Dexin，Huang Zhiping，et al.Breaking chaotic direct sequence spreading spectrum signals under the multipath fading channel [J]. Circuits, Systems & Signal Processing,2014,33(3): 973-986.

[13]蔚国强，杨建业，张合新．常用非线性滤波方法比较研究[J]．电光与 控制,2009,16 (12):48-52.(Yu Guoqiang,Yang Jianye,Zhang Hexin.A comparison of several widely used nonlinear filtering approaches [J]. Electronics Optics & Control,2009,16(12): 48-52.)

[14]胡志辉，冯久超．基于UKF的多用户混沌通信[J].物理学报,2011,60 (7):07o5O5.(Hu Zhihui,Feng Jiuchao.Chaotic communications with multiuser based on unscented kalman filter [J].Acta Physica Sinica,2011, 60 (7):070505.)

[15] Nosrati K,Rostami A S,Azemi A,et al.A private secure communication schemeusing UKF-based chaossynchronization [J].Journalof Engineering Science and Technology,2015,8(2):96-105.