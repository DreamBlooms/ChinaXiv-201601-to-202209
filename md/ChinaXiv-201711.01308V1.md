# CN 53-1189/P ISSN 1672-7673

# 基于多项式模型的射电天文中的移动干扰消除

朱世宇¹，王壮}，王梦南'，董亮²(1.国防科学技术大学电子信息与工程学院，湖南 长沙410073；2.中国科学院云南天文台，云南 昆明 650011)

摘要：射电天文观测数据受无线电的影响日益严重。因此，射频干扰(Radio FrequencyInterference，RFI)消除已经成为信号处理流程中不可或缺的一步。考虑了自适应阵列信号处理中的移动干扰源的消除问题，对于阵列天线望远镜而言，射频干扰消除可以通过采样协方差矩阵在空域实施处理。在很多应用场景中，可得到的零点深度受限于协方差矩阵的估计误差，进而影响干扰子空间的估计精度。方法应用了一种多项式模型以跟踪阵列协方差矩阵随时间的变化，消除干扰子空间的估计误差，提高干扰消除性能。最后通过仿真对比了传统的子空间投影（Subspace Projection，SP）算法和基于多项式模型的子空间投影（Polynomial-augmented Subspace Projection，PSP)算法，仿真结果证明了所提方法的有效性。

关键词：干扰消除；自适应波束形成；子空间投影；射电天文中图分类号：TN973 文献标识码：A 文章编号：1672-7673(2017)03-0297-07

射频干扰是射电天文中一个十分重要的问题。大部分的射电源信号属于微弱信号，需要长时间的积分才能够被接收机检测。由于低质量的滤波器泄露和邻近频带的互调干扰，射电天文观测数据总受到来自被国际电信联盟（International Telecommunication Union，ITU）保护的频带内的无线电信号的干扰。另一方面，根据可观测灵敏度与带宽之间的关系可知，最小灵敏度与带宽成反比，即采用更宽的输人带宽能够获得更微弱信号的探测能力。那么和目前日益增长的无线电频率使用必然形成矛盾，人工产生的比如卫星传输信号、雷达信号、无线通信信号和电视广播信号等大大强于射电天文信号（太阳射电爆发信号除外)，如果在观测频段内，会造成接收机饱和、假谱、交调干扰等一系列问题，影响天文观测的数据质量。

近几年来，一系列自适应波束形成算法已经成功应用于空间干扰消除[1-2]，但是仍然有很多应用场景和信号环境是目前的方法不能应对的。当干扰移动相对较快时，传统的自适应干扰消除方法性能下降。本文方法基于已被广泛应用的子空间投影算法[3-8]，主要考虑到它良好的零陷深度。子空间投影算法是通过阵列协方差矩阵的特征值分解得到干扰子空间的估计，继而将接收信号投影到干扰子空间的正交空间，以实现干扰消除。

虽然本文所提方法和原理通常适用于大范围的传感器阵列和自适应阵列的干扰消除，但在这里着重强调射电天文中的相控阵天线（Phased Array Feeds，PAFs）。这个应用对干扰移动相对于阵列协方差矩阵的估计时间间隔而言是相对快速的问题，是一个恰当的处理方法。采样时间间隔通常被称为短时积分窗（Short-term integration，STI）。

相控阵天线提供了一种有前途的新方法以利用干扰信号的空间结构跟踪和消除射频干扰而不会丢失任何有用数据[8]。对于空间干扰消除而言，上述方法甚至可以消除完全遮盖有用信号的频谱的干扰源的影响。

本文第1节给出了信号模型的数学表示；第2节介绍了子空间投影的波束形成的详细原理和由于干扰源的相对移动导致的估计误差是如何限制零陷深度的；第3节提出了一种适用于移动干扰源的基于矩阵多项式模型的时变阵列协方差矩阵，以改善传统的子空间投影算法；第4节给出了仿真性能分析，由结果可知本文方法的干扰消除性能优于传统的子空间投影方法。

# 1信号模型

假设 $x [ n ]$ 是 $P \times 1$ 阶的阵列天线的复采样序列，它可以表示为

$$
x [ n ] = a _ { s } s [ n ] + a _ { d } [ n ] d [ n ] + \eta [ n ] ,
$$

其中， $s [ n ]$ 为观测的射电天文信号； $\boldsymbol { a } _ { s }$ 为 $s [ n ]$ 阵列响应矢量； $d [ n ]$ 为干扰源信号； $a _ { d } [ n ]$ 为 $d [ n ]$ 阵列响应矢量。天线是固定跟踪观测源以保持射电源在视轴线上，因此 $\boldsymbol { a } _ { s }$ 是常量。随着干扰源的相对运动或者天线跟踪射电源， $a _ { d } [ n ]$ 随时间改变。噪声矢量 $\eta [ n ]$ 假设为空域白高斯噪声。信号 $s [ n ]$ 、 $d$ $\left[ n \right]$ 和 $\eta [ n ]$ 假设为广义宽平稳的高斯随机过程。那么，阵列协方差矩阵表示为

$$
R _ { x } [ n ] = E \{ x [ n ] x ^ { H } [ n ] \} \ = \sigma _ { s } ^ { 2 } a _ { s } a _ { s } ^ { H } + \sigma _ { d } ^ { 2 } a _ { d } [ n ] a _ { d } ^ { H } [ n ] \ + R _ { \eta } = R _ { s } + R _ { d } [ n ] \ + R _ { \eta } ,
$$

其中， $R _ { x } [ n ]$ 的时间依赖性来自由移动干扰源产生的阵列响应矢量的变化，因此在一个短时积分窗内，它只能近似看做是广义平稳的。这个假设在干扰源移动速率相对于短时积分窗宽度较快时会失效。其他的所有信号假设为广义平稳的。

虽然 ${ \cal R } _ { \it x } \left[ n \right]$ 随 $n$ 连续变化，它只有假设在第 $k$ 个短时积分间隔内是平稳的，因此可以得到它的 $L$ 长度采样的估计值：

$$
\hat { R _ { x , k } } = \frac { 1 } { L } \sum _ { n = k L } ^ { \left( k + 1 \right) } { x \left[ n \right] x ^ { H } \left[ n \right] } = \frac { 1 } { L } X _ { k } X _ { k } ^ { H } ,
$$

其中， $X _ { k } = \left[ x \left[ k L \right] , \cdots , x \left[ \left( k { + } 1 \right) L { - } 1 \right] \right]$ 为第 $k$ 个短时积分窗 $L$ 长度的采样数据。

# 2传统的干扰消除算法

# 2.1子空间投影干扰消除

在满足窄带的条件下，波束形成器的输出信号可以表示为

$$
y \left[ n \right] = w ^ { H } x \left[ n \right] ,
$$

其中， $w$ 为波束形成器的权矢量，以提供期望信号来向上的响应方向图。如果干扰信号相对于信号在阵列间的传播时间是时域宽带的，那么 $x [ n ]$ 可以被分解为多个子带，每一个有各自的波束形成权矢量。

在传统的自适应波束形成算法中有很多可以用来设计 $\mathbf { \sigma } _ { w }$ 以得到期望的方向图主瓣、控制方向图形状和在干扰信号的方向上获得零点[1-2]。

考虑到子空间投影算法可以得到更深的零陷深度，本文方法基于子空间投影算法实现[6-8]。当干扰信号的强度大到可以主导 ${ \cal R } _ { \mathrm { { x } } } [ n ]$ 中的噪声和有用信号时，波束形成权矢量可以用下面的方法计算：

$$
\begin{array} { r } { \boldsymbol { w } _ { \mathrm { S P } , k } = \boldsymbol { P } _ { d , k } ^ { \perp } \boldsymbol { w } } \\ { \boldsymbol { P } _ { d , k } ^ { \perp } = \boldsymbol { I } - \boldsymbol { U } _ { d , k } \boldsymbol { U } _ { d , k } ^ { H } } \end{array} ,
$$

其中， $k$ 为短时积分窗的索引值； $P _ { d , k } ^ { \perp }$ 为估计的干扰子空间的正交投影矩阵； $U _ { d , k }$ 包含了协方差矩阵分解中干扰信号对应的单位长度归一化的主特征向量：

$$
\hat { R } _ { x , k } [ U _ { d , k } \mid U _ { s , \eta , k } ] = [ U _ { d , k } \mid U _ { s , \eta , k } ] \Lambda .
$$

权值矢量 $w$ 用来建立无干扰情况下的静态天线方向图。投影算子 $P _ { d , k } ^ { \perp } w$ 可能扰乱或者损坏期望的静态方向图，因此需要保证干扰从天线方向图的旁瓣进入。另一方面， $U _ { d , k }$ 的秩必须小于天线个数 $P$ 或有充分的自由度形成远离空域零点的期望的静态方向图。

在移动干扰源的应用场景中， $w _ { \mathrm { S P } , k }$ 在每一个新的 $L$ 长度的采样中被重新计算以保持干扰消除零点在干扰来向上。在多干扰源的应用场景中，必须事先计算干扰个数 $\mathbf { \nabla } _ { m }$ ，而此时的干扰信号矩阵 $U _ { d , k }$ 的阶数为 $P \times m$ 。本文方法着重应用于单个干扰的情况，此时 $U _ { d , k }$ 是一个列矢量。

# 2.2影响干扰消除性能的因素

提高采样数可以减小协方差矩阵 $\hat { R } _ { x , k }$ 的采样估计误差，那么干扰子空间的估计精度和干扰消除算法的性能会随之提高。但当传统的子空间投影的波束形成抗干扰方法应用于移动干扰源的场景时，如果干扰移动速度过快而采样间隔过长，会引起阵列相应的不一致，造成阵列协方差矩阵的秩不等于干扰源数量即子空间扩散，那么自适应波束形成抗干扰算法将无法使用。因此分析采样估计误差和子空间扩散对传统自适应波束形成干扰消除算法的影响，为改进传统的自适应波束形成干扰消除算法做准备。

（1)采样估计误差：在平稳信号环境中Rx,是R[n]In=的一致估计，估计误差的方差减少了」[9]。为了减少估计误差，短时积分窗的长度应该尽可能长。

(2)子空间扩散： $\hat { R } _ { x , k }$ 包含了第 $k$ 个采样时间间隔的 $L$ 长采样的时变 ${ \cal R } _ { d } \left[ n \right]$ 的时间平均。尽管${ \cal R } _ { d } [ n ] = \sigma _ { d } ^ { 2 } a _ { d } [ n ] a _ { d } ^ { H } [ n ]$ 的秩为1，但采样间隔过长时，对移动干扰源做时间平均产生一个秩更高的矩阵，这就需要用更多的特征矢量去张成干扰子空间。只有当采样间隔的宽度相对于干扰移动速率较窄时，投影算子 $P$ 才能有效地投影这个秩数较高的干扰分量。这个有限窗口的估计带来的影响通常叫做“子空间扩散”。

通过子空间投影波束形成抗干扰算法仿真得到的在不同输人干噪比情况下单移动干扰消除的干扰抑制比（Interference Rejection Ratio，IRR)如图1。

从图1可以看到，对于一个给定长度的样本数，一个更高的输入干噪比会带来更高的干扰抑制比,因为此时 $\hat { R } _ { x , k }$ 的主特征向量更接近真实的干扰信号。同时，干扰抑制比随着样本数长度的增加而增加，直到子空间扩散开始影响干扰消除性能，这会产生一个干扰抑制比的最大值。随着样本数的继续增加，干扰消除性能开始急剧恶化，也就是说干扰源的移动限制了可得到的干扰抑制比的最大值。但是在较低输入干噪比的情况下，由于无法得到干扰子空间的准确估计，因此无法对干扰进行很好的消除，所以干扰抑制比并没有明显的变化。

通过子空间投影波束形成抗干扰算法仿真得到在不同输入干噪比情况下单移动干扰消除残余干扰功率如图2。

从图2可以看到，对于一个给定长度的样本数，一个更高的输入干噪比带来更低的残余干扰，因为此时 $\hat { R } _ { x , k }$ 的主特征向量更接近真实的干扰信号。同时，残余干扰功率随着样本数长度的增加而减小，直到子空间扩散开始影响干扰消除性能，这会产生一个残余干扰功率的最小值。随着样本数的增加，干扰消除性能开始急剧恶化，也就是说干扰源的移动限制了可得到的残余干扰功率的最小值。但是在较低输入干噪比的情况下，由于无法得到干扰子空间的准确估计，因此无法对干扰进行很好的消除。不过由于输入的干噪比很低，所以此时的残余干扰功率也很低。

![](images/7eee93ed160d29dab0175b66c7edba53c9afec215092af2ba94f6987ae57d093.jpg)  
图1移动干扰源情况下不同样本数和输入干噪比下的干扰抑制比

![](images/50133c36a59189ad5ddcf04a05d2e409670d4a53a6b7561aabbf43e8d6dd950f.jpg)  
图2移动干扰源情况下不同样本数和干噪比下的残余干扰功率  
Fig.1IRR dependence on STI length and INR level for a moving interferer   
Fig.2Residual interference power dependence on STI length and INR level for a moving interferer

# 3基于多项式模型的子空间投影

由上述分析可知，传统的自适应波束形成抗干扰方法在样本数有限的情况下，由于协方差矩阵估计存在误差，导致干扰信号子空间估计精度受到限制，从而导致干扰消除性能下降。另一方面，如果增加样本数，由于干扰源运动导致干扰信号的子空间扩散，严重影响算法的干扰消除性能。在低干噪比情况下，由于干扰信号子空间不准确，传统方法的干扰抑制性能不能满足实际工作的需求。为了解决上述问题，本文通过将时变的 ${ \cal R } _ { d } [ n ]$ 与多项式模型合并，提出了一种子空间投影波束形成算法的扩展。这种新的基于多项式模型的子空间投影算法(Polynomial-based Subspace Projection，PSP)提高了干扰子空间的跟踪性能。

由于干扰源的移动和天线方向图结构导致从 $\boldsymbol { R } _ { \boldsymbol { x } , \boldsymbol { k } }$ 到 $R _ { x , k + 1 }$ 的变化是连续的，因此一个适当阶数的多项式拟合可行。假设忽略射电天文信号的影响，这个假设符合常见的射电天文的观测场景，因为射电天文信号的强度过于微弱，以至需要长时间的积分才可以检测到。

时间连续的协方差矩阵 $R _ { x } ( t )$ ，给出了它的采样形式 $R _ { x } [ n ]$ 。引人 $\widetilde { R } _ { d } ( t , C ) \approx R _ { d } ( t )$ 作为时变的干扰分量 $R _ { x } ( t )$ 的模型，并通过多项式系数矩阵 $C$ 使其参数化。单干扰信号 $R _ { a d } ( t ) = \sigma _ { a d } ^ { 2 } a _ { d } ( t ) a _ { a d } ^ { H } ( t )$ 的秩为1，因此可以用 $\boldsymbol { r }$ 阶的多项式矢量构建时间连续的 $\sigma _ { d } a _ { d } ( t )$ 。

$$
\begin{array} { r l } & { \widetilde { \boldsymbol { a } } ( t , \ C ) = \boldsymbol { C } t , } \\ & { \boldsymbol { t } = [ 1 , \ t , \ \cdots , \ t ^ { r } ] ^ { \ H } , } \\ & { \widetilde { \boldsymbol { R } } _ { d } ( t , \ C ) = \widetilde { \boldsymbol { a } } ( t , \ C ) \widetilde { \boldsymbol { a } } ^ { H } ( t , \ C ) = \boldsymbol { C } \boldsymbol { t } \boldsymbol { t } ^ { H } \boldsymbol { C } ^ { H } . } \end{array}
$$

多项式系数 $C$ 的估计值可以通过每一个单独短时积分窗的采样协方差矩阵的平方误差最小准则得到。

$$
\begin{array} { l } { \widehat { C } = \arg \operatorname* { m i n } _ { c } \displaystyle \sum _ { k = 0 } ^ { K - 1 } \| \widetilde { R } _ { x , \textit { k } } - \widetilde { R } _ { d } ( t _ { k } , \textit { C } ) \| _ { F } ^ { 2 } } \\ { t _ { k } = T \left( \frac { 2 k } { K - 1 } - 1 \right) } \end{array}
$$

其中， $t _ { k }$ 为第 $k$ 个短时积分采样窗口的对应于采样中值标准化的时间值。（8)式保证了对于 $0 \leqslant k \leqslant K - 1$ ，总有 $- T \leqslant t _ { k } \leqslant T$ ，在多项式拟合窗口中生成了 $K$ 个短时积分窗。多项式估计的时间尺度标准化是任意的，因为 $T$ 不代表任何实际的时间或以秒或采样数为刻度的窗口宽度。在估计(6)式时 $T$ 作为一个调节参数以限制时间范围，使得高阶的多项式模型不会主导曲线走向，并且在这时多个有界的变化值可以用拟合窗口表示。经过多次仿真分析发现，将 $T$ 设置为0.75 时得到较好的拟合性能。

利用一致性 $\parallel A \parallel _ { F } ^ { 2 } { = } t r \{ A ^ { H } A \}$ 将(7)式代入(8)式，并且扩展到矩阵形式得到：

$$
\hat { C } = \arg \operatorname* { m i n } _ { C } \sum _ { k = 1 } ^ { K } f _ { k } ,
$$

$$
{ \boldsymbol { f _ { k } } } = t r \{ \hat { R _ { k } ^ { H } } \hat { \boldsymbol { R _ { k } } } + C \boldsymbol { B _ { k } } C ^ { H } C \boldsymbol { B _ { k } } C ^ { H } - \hat { R _ { k } } C \boldsymbol { B _ { k } } C ^ { H } - C \boldsymbol { B _ { k } } C ^ { H } \hat { R _ { k } ^ { H } } \}
$$

其中， $B _ { k } = t _ { k } t _ { k } ^ { H }$ 。利用(8)式可以得到解析的梯度和全局最小解以明显减少计算空间，利用数据优化方法改善收敛时间。

有一系列广泛的优化代码可用来解决(9)式的问题。第4节的仿真结果通过MATLAB 的函数fminunc. $\mathbf { m }$ 得到，它是一种基于内部映射牛顿法的置信域方法。（9)式的梯度和全局最小解用来确定置信域问题并把这个区域限制在二维子空间。

梯度：虽然多项式的系数是复值，但在平常的优化代码中，它们必须作为独立的实部和虚部计算。在这种情况下，梯度需要改写为

$$
\nabla _ { C } f = \left[ \begin{array} { c c c c } { \mathrm { v e c } \left\{ \frac { \partial f } { \partial \operatorname { R e } \{ C \} } \right\} } \\ { \mathrm { v e c } \left\{ \frac { \partial f } { \partial \operatorname { I m } \{ C \} } \right\} } \end{array} \right] ,
$$

$$
\nabla _ { C } \Big ( \sum _ { k = 1 } ^ { K } f _ { k } \Big ) = 4 \sum _ { k = 1 } ^ { K } \left[ \mathrm { v e c } \{ \operatorname { R e } \{ \left( C B _ { k } C ^ { H } - \hat { R _ { k } } \right) C B _ { k } \} \} \right] ,
$$

全局最小解：用 $E _ { s t }$ 表示一个除了 $( s , t )$ 位置为1以外全0的初等矩阵，全局最小解可以表示为

$$
H _ { C } \Big ( \sum _ { k = 1 } ^ { K } f _ { k } \Big ) = 4 \sum _ { k = 1 } ^ { K } \left[ \begin{array} { l }  \mathrm { v e c } \{ \mathrm { R e } \{ M _ { 1 } \} \} \ \mathrm { v e c } \{ - \mathrm { I m } \{ M _ { 2 } \} \} \ \} \\ { \mathrm { v e c } \{ \mathrm { I m } \{ M _ { 1 } \} \} \ \ \mathrm { v e c } \{ \mathrm { R e } \{ M _ { 2 } \} \} \ } \end{array} \right] ,
$$

$$
\begin{array} { r l } & { M _ { 1 } = E _ { s t } B _ { k } C ^ { H } C B _ { k } + C B _ { k } E _ { s t } ^ { H } C B _ { k } + C B _ { k } C ^ { H } E _ { s t } B _ { k } - \hat { R _ { k } } E _ { s t } B _ { k } , } \\ & { M _ { 2 } = E _ { s t } B _ { k } C ^ { H } C B _ { k } - C B _ { k } E _ { s t } ^ { H } C B _ { k } + C B _ { k } C ^ { H } E _ { s t } B _ { k } - \hat { R _ { k } } E _ { s t } B _ { k } . } \end{array}
$$

此时，（9)式的直接最优解中包含一个相位模糊，这可能影响数值收敛，因为对任意的角度 $\phi$ ，有$( e ^ { j \varphi } \widetilde { \boldsymbol { a } } ( t _ { k } , C ) ) \ ( e ^ { j \varphi } \widetilde { \boldsymbol { a } } ( t _ { k } , C ) ) ^ { H } = \widetilde { \boldsymbol { a } } ( t _ { k } , C ) \widetilde { \boldsymbol { a } } ^ { H } ( t _ { k } , C )$ 。这可以应用到一个任意的时间点 $t _ { k }$ 上，而其它的所有 $t _ { l }$ ， $l \neq k$ 的相位都可以通过多项式的连续性求得。这个模糊可以通过迫使 $\angle \stackrel { \triangledown } { \{ \hat { C } \} } _ { 1 , 1 } = 0$ 解决，此时有 $\angle \left\{ \stackrel { \sim } { a } ( 0 , \hat { C } ) \right\} _ { 1 } = 0$ 。文[10]给出的一种参数约束的替代方案是使 $\sum _ { p = 0 } ^ { P - 1 } \angle \ \stackrel { \textstyle \bigwedge } { \mid } \ C \ \bigr \uparrow _ { p , 1 } = 0$ ，也就是说在元素 $\tilde { \mathbf { \Gamma } } _ { a ( 0 , \hat { C } ) } ^ { \sim }$ 上有一个0均值相位。这两种方法减少了绝对的相位估计误差方差，但是这两种方法在系统中产生的误差方差也一样，这些值仅仅依赖于相位的不同。这正是 $\tilde { \boldsymbol { a } } ( t , \hat { C } )$ 是如何代入（7）式中以得到 $\stackrel { \sim } { R } _ { d } ( t , \hat { C } )$ 的，因此由于它在优化代码中更易于实现，选择 $\angle \stackrel { \textstyle \langle \hat { C } \rangle } { \hat { C } } _ { 1 , 1 } = 0$ 。

理论上，子空间投影算法可以扩展到处理多个干扰源的情况。此时， $\widetilde { \boldsymbol { a } } _ { m } ( t , C _ { m } )$ 是 $\mathbf { \Omega } _ { m }$ 个干扰信号的时变阵列响应。（7)式改写为

$$
\widetilde { R } _ { d } ( t , \ C _ { 1 } , \ \cdots , \ C _ { M } ) = \sum _ { m = 1 } ^ { M } C _ { m } t t ^ { H } C _ { m } ^ { H } \ .
$$

在数值优化中将梯度和全局最小解扩展到相应的 $C _ { m }$ 中是一项繁重却很直接的工作。最大的困难在于为每一个 $C _ { m }$ 找到一个好的初始值。因此，后面的讨论限定干扰维度为1。

# 4仿真和分析

在仿真中尽量保证仿真环境的设置与物理实验平台相符合。详细的数值模型是利用一个10阵元双极化线性半波长宽带的加厚偶极子的相控阵馈源放置在地平面上形成的，其结构如图3。可用的天线带宽为 $3 0 0 ~ \mathrm { M H z }$ ，中心频点为1600$\mathrm { { M H z } }$ ，同时这也作为仿真生成的窄带信号的中心频率。数据的采样速率为1.25Msamp/s，带宽为 $4 5 0 \mathrm { k H z }$ 。

以调制 $\mathrm { C } / \mathrm { A }$ 码的北斗导航信号为干扰信号。短时积分窗序列中的每一个窗口都通过 $2 ^ { 7 } \sim 2 ^ { 1 4 }$ 个采样点计算，并且所有的短时积分窗使用采样估计校准的噪声协方差矩阵 $\hat { R _ { \eta } }$ 进行预白化。同

![](images/d2e7f862f8ba9313dbcda762e652ae43aef3368d0fbc54f793599ef4271859aa.jpg)  
图3仿真天线结构示意图  
Fig.3The Schematic diagram of simulation antenna structure

时每一个相位正确的特征矢量进行多项式拟合。利用(5)式得到的静态(无干扰)波束形成权矢量$\boldsymbol { w } = \boldsymbol { \hat { R _ { \eta } } ^ { - 1 } } \boldsymbol { a _ { s } }$ 是最大灵敏度的波束，此时有用信号保持在天线的视轴上。

图4给出了在每一个短时积分窗的协方差矩阵中使用多项式模型拟合与传统的子空间投影算法的性能分析对比。从图中可以看出，子空间投影算法对短时积分的窗口宽度有更高的敏感性，但是子空间投影算法在整个短时积分窗的采样窗口的性能优于子空间投影算法。在很短的短时积分窗采样窗口情况下，子空间投影算法的性能急剧恶化，这是因为此时的采样协方差矩阵有太多的估计误差，不能得到一个良好的特征向量。而子空间投影算法在较短的短时积分窗口宽度的情况下可以得到与较长的短时积分窗口宽度近似的干扰消除性能。图3和图1的仿真环境都是在相同干噪比和 $3 ^ { \circ } / \mathrm { s }$ 的干扰移动速率下进行。在图3中，PSP-8是指特征矢量是用一个8阶多项式拟合的，PSP-12是指特征矢量是用一个12 阶多项式拟合的。

![](images/8bfbcf0a3d89fb7f7bd3947753774a0b8f7d37191a051fa05986e3718d583b1c.jpg)  
图4不同的干噪比和干扰移动速率下的子空间投影算法和基于多项式的子空间投影算法的性能。(a) $I N R = - 1 2 { \mathrm { ~ d B } }$ ；(b) $I N R { = } 0 ~ \mathrm { d B }$ ；(c) $I N R { = } 1 2$ dB$\mathrm { S P }$   
Fig.4Performance of and PSP for various input INRs and motion rates

# 5结论

本文的研究要点在于：（1)详细分析了子空间投影算法的性能特点，并研究了限制干扰消除性能的因素，包括采样估计误差和子空间扩散；（2)提出了一种多项式拟合的方法以更好地构造由干扰移动引起的时变特性。虽然本文是使用射电天文的相控阵馈源仿真和分析算法的有效性，但对于其它的移动干扰环境下的自适应阵列干扰消除有广泛的适用性。

更进一步的工作包括把算法应用到多干扰消除和处理由多径散射带来的秩的增加。本文的实验数据是以秒为单位进行观测的结果，但是实际的射电天文观测中可能需要以小时为单位进行观测。因此，实时处理需要考虑该方法是否可以在实际的天文观测中应用。实时处理的问题包括快速多项式参数估计和波束形成中的自动参数估计问题，因此需要根据不同的数据环境选择不同的多项式阶数。

# 参考文献：

[1] Veen B D V，Buckley K M.Beamforming：a versatile approach to spatial filtering[J]. IEEE Acoust Speech Signal Process，1988，5(2) : 4-24.   
[2] Tres H J V. Detection， estimation and modulation theory，Part IV: Optimum Array Processing [M].New York:Wiley，2002.   
[3] Palka T A，Tufts D W.Reverberation characterization and suppresson by means of principal components [J].Oceans，1998，3(5）：1501-1506.   
[4] Youn W S,Un C K. Robust adaptive beamforming based on theeigenstructure method [J]. IEEE Transactions on Signal Processing，1994，42(6) :1543-1547.   
[5] Friedlander B.A signal subspace method for adaptive interference cancelation [J].IEEE Transactions Acoustics，Speech and Signal Processing，1988，36(12） : 1835-1845.   
[6] Leshem AJ,Veen AJDV,Boonstra AJ. Multichannel interference mitigation mrthods in radio astronomy［J].The Astrophysical Journal Supplement，2000，131（1）：355-374.   
[7] Ellingson S W，Hampson G A. A subspace-tracking approach to interference nulling for phased arraybased radio telescopes [J]. IEEE Transactions on Antennas & Propagation，2002，50(1）：25-30.   
[8] Jeffs B D，Warnick K F，Landon J,et al. Signal processing for phased array feeds in radio astronomical telescopes ［J]. IEEE Journal of Selected Topics in Signal Processing，2008，2 (5) : 635-646.   
[9] Ulaby F T，Moore R K， Fung A K. Microwave remote sensing，active and passive: radar remote sensing and surface scatering and emission theory [M].Norwood，MA：Artech House，1982.   
[10] Wijnholds S J,A J van der Veen. Effcts of parametric constraintson the CRLB in gain and phase estimation problems [J].IEEE Signal Processing Letters，2006，13(10）:620-623.

# Model-Based Mitigation of the Moving RFI in Radio Astronomy

Zhu Shiyu'，Wang Zhuang'，Wang Mengnan'，Dong Liang² (1.ATRKeyLab,ScholofElectronic ScienceandEnginering，NatioalUniversityofDefenseTechnolog，Changsha4，China, Email：zsy_kd@163.com；2.Yunnan Observatories，Chinese Academy of Sciences，Kunming 650o11,China)

Abstract：Radio astronomical data are increasingly corrupted by human telecommunication activities. Therefore，Radio Frequency Interference（RFI）mitigation becomes an important step in the data processing flow.This paper considers the problem of adaptive arry processing for interference canceling to drive nulls in a moving interference environment.As to the telescopes based on antenna array，RFI mitigation can be conducted in spatial domain using the sampled covariance matrix.In many practical scenarios，the achievable null depth is limited bycovariance matrix estimation error whichleads to poor identification ofthe interference subspace.We pay attention to the particularly troublesome cases of relatively rapid interference motion.A polynomial-based model is incorporated in the proposed algorithm to track changes in the arraycovariance matrix over time，mitigate interference subspace estimation errors，and improve canceler performance. Performance for conventional subspace projection （SP）is compared with polynomial-augmented SP using simulation. The simulation results validate the effectiveness of the proposed algorithm.

Key words: Interface cancelation； Adaptive beamforming； Subspace projection （SP）；Radio astronomy