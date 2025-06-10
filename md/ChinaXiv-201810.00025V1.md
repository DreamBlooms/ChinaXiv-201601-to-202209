# 改进迭代限幅滤波TDCS峰均比抑制算法

李夏昭，任清华，孟庆微(空军工程大学 信息与导航学院，西安 710077)

摘要：针对现有变换域通信系统存在较高峰均比及传统迭代限幅滤波算法峰均比收敛缓慢的问题，提出了改进迭代限幅滤波变换域通信信号峰均比抑制算法。该算法通过引入限幅噪声，对其进行滤波，减少峰均比回升的同时有效消除带外频谱扩撒，并在迭代过程中获得更好的峰均比抑制效果。仿真结果表明，该算法一方面能获得更好的峰均比抑制效果，一次迭代较传统算法获得约ldB的性能增益，三次迭代效果优于传统算法四次迭代；另一方面改善带外频谱性能，加入滤波后降低带外频谱功率约5dB。误码率的对比结果表明，改进算法所损失的系统传输性能非常低。

关键词：变换域通信系统；峰均比；改进迭代限幅滤波；

中图分类号：TN911.4 doi:10.3969/j.issn.1001-3695.2018.07.0412

# Improved iterative clipping and filtering method for TDCS PAPR reduction

Li Xiazhao,Ren Qinghua, Meng Qingwei (Information&Navigation College,Air Force Engineering University,Xi'an71oo77,China)

Abstract:For the problem of high peak-to-average powerratio (PAPR)oftransform domain communicationsystem (TDCS) andthe slowconvergenceof thePAPRof the traditional iterative clippingand filtering method,thispaper proposed an improved iterative clippingand filteringmethodforTDCS signal PAPRreduction.Byfilteringtheclipping noise introduced, this methodreduced the PAPR regrowth and efectivelyeliminatedout-of-band spectrum spread,and gotbetter PAPR suppression effectin iteration.Thesimulationresults show thaton theone hand,thismethod can obtain better PAPR suppression efect,thefirst teration canobtainabout1dB performancegain compared with the traditional method and the thirditeration hasbeter effctthanthe fourth iterationof traditional method.Ontheother hand,itcanimprovethe out-of-band spectrum performance,after filtering,theout-of-band spectrum power reduces byabout 5dB.Thecomparisonof BER shows that the performance of system lost by the improved method is very low.

Key words: transform domaincommunication system; peak-to-average power ratio;improved iterativeclippingand filtering

# 0 引言

变换域通信系统(transform domain communication system,TDCS）是通过频谱感知从而主动规避干扰的认知无线电系统[1-4]。TDCS 信号在频域与干扰正交，时域具有类噪声性，这些特性使得TDCS信号具有较强的抗干扰能力和抗截获特性[5]。然而TDCS作为多载波系统，其发射端信号时域波形是多个载波的叠加，导致其具有较高的峰均比[。当传输信号的峰值超过功率放大器的线性范围时，就会导致严重的带内幅度畸变和带外噪声，影响整个系统的误码率，而且信号幅度峰值过高使得该点分配功率过多，造成系统能量浪费。因此，抑制TDCS信号的峰均比对变换域通信系统的实际应用有很大的意义。

限幅法是多载波系统峰均比抑制的常用方案，但限幅会导致带内幅度畸变和带外频谱扩散[7-10]，需要加入滤波提升带外性能，但滤波会导致峰均比回升，所以需要多次迭代处理才能将峰均比控制在理想值[10-12]。但传统迭代限幅滤波算法峰均比收敛速度较慢，计算复杂度高。为此，本文提出了改进TDCS系统的迭代限幅滤波算法，通过引入TDCS信号限幅噪声，对限幅噪声进行滤波，信号频域合成，实现峰均比抑制效果的提升，同时有效控制带外频谱扩散。本文阐述了限幅滤波的基本方法以及改进算法的原理和步骤，并对其进行了理论分析。最后仿真对比了改进算法的峰均比抑制性能和误码率性能，验证了算法的有效性。

# 1 TDCS系统

TDCS通信系统由发射机和接收机构成。图1给出了采用CCSK(cyclic code shift keying)调制的 TDCS 发射机结构原理图。

![](images/51f95afa659a6ec01003dd2cf374580c28f8137485cdd8fd4d08d7c748e007d7.jpg)  
图1TDCS发射机框图

发射端通过谱估计技术，对环境电磁频谱进行采样，判定干扰所在位置，得到谱估计结果 $A ( K )$ 。将 $A ( K )$ 与预先设定的干扰门限进行对比，大于门限的干扰频段置0，可用频段置1，得到幅度谱向量 $A ^ { \prime } ( K )$ 。利用循环移位寄存器产生伪随机序列，后经相位映射产生随机相位 $e ^ { j \theta _ { k } }$ ，将其与幅度谱向量相乘得到基函数的频域表达式。将经过能量调整后的基函数通过IDFT变换到时域，发送数据通过时域基函数的调制，发送到发射端。

采用CCSK调制TDCS发射信号可表示为

$$
s ( n ) = { \frac { 1 } { \sqrt { N N _ { 1 } } } } \sum _ { k = 0 } ^ { N - 1 } A ^ { \prime } ( k ) e ^ { j \theta _ { k } } e ^ { - j 2 \pi m _ { i } k / M } e ^ { j 2 \pi k n / N }
$$

其中： $N$ 为基函数的采样点数， $N _ { 1 }$ 为基函数频谱可用点数。 $m _ { i }$   
为第 $i$ 个发送数据， $M$ 代表CCSK的调制阶数。

TDCS接收机结构如图2所示。接收机通过对本地环境频谱感知，生成本地基函数，取共轭后与接收信号进行相关处理，解调出发送数据。

![](images/65445aa7c43046ada8a37e612c61674b5a3cd5bd83dafd695495ac9c43796c0c.jpg)  
图2TDCS 接收机框图

# 2 TDCS 峰均比

由 TDCS信号的表达式可知，频域上其由多个不同频段的子载波构成。当子载波数 $N \to \infty$ 时，由中心极限定理知TDCS信号包络将服从瑞丽分布[13]。一般使用信号峰值功率与平均功率的比值(peak-to-average power ratio,PAPR）来表示信号幅值的变化程度。TDCS 信号峰均比PAPR 定义为[14]

$$
P A P R = \frac { \operatorname* { m a x } _ { n \in [ 1 , N ] } \left| s _ { i } ( n ) \right| ^ { 2 } } { E \left\{ \left| s _ { i } ( n ) \right| ^ { 2 } \right\} }
$$

其中： $i$ 代表第 $i$ 个TDCS 调制信号。TDCS 信号的峰均比随着基函数幅度和随机相位而变化。本文中，TDCS信号峰均比的抑制效果采用(complementary cumulative distribution function,CCDF)来描述，其代表的是PAPR超过某一预定值的概率[15]:

$$
C C D F = \mathrm { P r } \left\{ P A P R > P A P R 0 \right\}
$$

其中：PAPRO代表PAPR的常数值。根据中心极限定理，TDCS信号的实部和虚部服从均值为0，方差为 $\sigma ^ { 2 }$ 的高斯分布，其瞬时功率服从 $\chi ^ { 2 }$ 分布：

$$
\operatorname* { P r } ( \left| s _ { i } ( n ) \right| ^ { 2 } ) = { \frac { 1 } { 2 { \sigma } ^ { 2 } } } \exp ( - { \frac { \left| s _ { i } ( n ) \right| ^ { 2 } } { 2 { \sigma } ^ { 2 } } } ) \qquad ( 0 \leq n \leq N )
$$

则 $C C D F$ 可以表示为

$$
\operatorname* { P r } ( \operatorname* { m a x } \left| s _ { i } ( n ) \right| ^ { 2 } \leq P A P R 0 ) = ( 1 - e ^ { \frac { P A P R 0 } { 2 \sigma ^ { 2 } } } ) ^ { N _ { 1 } }
$$

$$
\operatorname* { P r } ( P A P R \geq P A P R 0 ) = 1 - ( 1 - \mathrm { e } ^ { - P A P R 0 } ) ^ { N _ { 1 } }
$$

# 3 改进迭代限幅滤波算法

限幅法通过预置门限，对信号幅值超过门限的部分保留其相位信息，将幅值替换为门限值。经过限幅后的TDCS发射信号可以表示为[16]

$$
\widetilde { s } _ { i } ( n ) = \{ { s } _ { i } ( n ) \qquad \stackrel { \scriptscriptstyle \triangleq \underline { { \mathbb { U } } } } | { s } _ { i } ( n ) | \le \gamma
$$

其中： $\gamma$ 表示预定的限幅门限， $s _ { i } ( n )$ 表示 TDCS 发送信号，$\left| s _ { i } ( n ) \right|$ ， $e ^ { j \theta }$ 分别表示发送信号的幅度和相位。为了对不同信号进行限幅处理，一般使用限幅比例(clippingratio,CR)进行限幅门限的计算：

$$
C R = \frac { \gamma } { \sqrt { E \left\{ \left| s _ { i } ( n ) \right| ^ { 2 } \right\} } }
$$

所以经过限幅后的TDCS信号峰均比理论值可以表示为CR的函数： $P A P R = 1 0 \log C R ^ { 2 } ( \mathrm { d B } )$ 。

但限幅是一个非线性过程，时域剔除会导致频域产生带内失真和带外频谱扩散，在降低峰均比的同时会影响TDCS基函数抗干扰性能，特别是限幅门限设计过低，系统性能会明显恶化。

针对限幅法引起的带外频谱扩散，需要采用滤波来消除。滤波分为时域和频域滤波，由于TDCS采用傅里叶变换域，所以使用频域滤波。TDCS信号限幅滤波的步骤为：

a)对第 $i$ 个TDCS调制信号 $s _ { n , i }$ 进行 $N$ 点FFT变换得到其频域形式 $\boldsymbol { S } _ { k , i } = [ S _ { 1 } , S _ { 2 , } , . . . , S _ { N } ]$ ，然后对其进行插零处理：

$$
S _ { k , i } ^ { \prime } = [ S _ { 1 } , . . . , S _ { { N } / { 2 } - 1 } , \underbrace { 0 , 0 , . . . , 0 } _ { ( J - 1 ) N } , S _ { { N } / { 2 } - 1 , } , . . . , S _ { N } ]
$$

b)对插零信号 $S _ { k , i } ^ { \prime }$ 进行 $J N$ 点IFFT变换得到时域信号：

$$
s _ { n , i } ^ { \prime } = J \sqrt { N } \cdot \mathrm { I F F T } _ { \mathcal { I N } } \left\{ S _ { k , i } ^ { \prime } \right\}
$$

c)对时域信号 $s _ { n , i } ^ { \prime }$ 进行限幅处理，将限幅后的时域信号 $\tilde { s } _ { n , i } ^ { \prime }$ 再进行 $J N$ 点FFT变换到频域：

$$
\tilde { S } _ { k , i } ^ { \prime } = \frac { 1 } { \sqrt { J N } } \cdot \mathrm { F F T } _ { J N } \left\{ \tilde { s } _ { n , i } ^ { \prime } \right\}
$$

d)对频域信号 $\tilde { S } _ { k , i } ^ { \prime } = [ \tilde { S } _ { 1 } , \tilde { S } _ { 2 , } , . . . , \tilde { S } _ { _ { J N } } ]$ 进行滤波，其方法是直接将除前后 $N / 2$ 个点的数据置零：

$$
\hat { S } _ { k , i } ^ { \prime } = [ \tilde { S } _ { 1 } , . . . , \tilde { S } _ { N / 2 - 1 , } , \underbrace { 0 , 0 , . . . , 0 } _ { ( J - 1 ) N } , \tilde { S } _ { J N - N / 2 , } . . . , \tilde { S } _ { J N } ]
$$

e)删除置零数据，对频域信号再进行一次 $N$ 点的IFFT变换，得到处理后的TDCS调制信号。

虽然加入滤波抑制了带外频谱扩散，但会导致峰均比的回升，联合限幅和滤波，采用迭代的方式才能将峰均比降低到理想值的同时控制带外频谱扩散。根据TDCS调制方式的不同和CR的选定，最优迭代次数也会有所差别。

传统的迭代限幅滤波峰均比收敛于理论值速率较慢，需要多次迭代，且每次迭代要进行多次FFT和IFFT，计算复杂度较高[17]，为此，本文提出了改进迭代限幅滤波算法，用较少的迭代次数获得传统算法多次迭代的抑制效果。

传统滤波方法是对限幅后的信号直接滤波，造成峰均比较大回升，为此本文提出了一种改进迭代限幅滤波算法，通过引入第i个TDCS 调制信号限幅噪声 $d _ { n , i } = s _ { n , i } - \tilde { s } _ { n , i }$ ，对限幅噪声进行滤波处理，避免直接对信号进行滤波，减少峰均比的回升。改进算法TDCS系统框图如图3所示。

![](images/c746bee73425a793fe99ebc3fa1630ac4b752fbaa21fe768fb6d23d366b874ec.jpg)  
图3改进算法TDCS发射机

改进算法的基本步骤如下：

a)对 $s _ { n , i }$ 变换到频域进行插零处理得到 ${ \cal { S } } _ { k , i } ^ { \prime }$ 0

b)将插零后的频域信号变换到时域进行限幅处理得到 $\tilde { s } _ { n , i } ^ { \prime }$ ，计算限幅噪声：

$$
d _ { n , i } = s _ { n , i } ^ { \prime } - \tilde { s } _ { n , i } ^ { \prime }
$$

c)将限幅噪声 $d _ { n , i }$ 变换到频域得到 $D _ { k , i }$ ，对其进行滤波，将非数据子载波位置的符号置零，得到 $\hat { D } _ { k , i }$ 。

d)计算 $\hat { S } _ { k , i } ^ { \prime } = S _ { k , i } - \hat { D } _ { k , i }$

e)将 $\hat { S } _ { k , i } ^ { \prime }$ 变换到时域得到处理后的TDCS 调制信号。

重复步骤 $\mathrm { { \bar { a } } ) \mathrm { { \tilde { \Sigma } } ^ { \mathrm { { \bar { d } } } } } }$ ，对信号进行迭代处理，并对处理后的信号峰均比进行检测，达到理想值则停止迭代，未达到则进行下一次迭代。

下面对改进算法进行理论证明。

TDCS信号包络服从瑞丽分布，当子载波数 $N$ 很大时，假 设在1秒内信号峰值超过门限值／的预期数值为 $p _ { t h }$ ，则

$$
p _ { t h } = \frac { \dot { \sigma } } { \sqrt { 2 \pi } } \frac { \gamma } { \sigma ^ { 2 } } \exp ( - \frac { \gamma ^ { 2 } } { 2 \sigma ^ { 2 } } )
$$

其中: $\dot { \sigma }$ 为信号平均功率的导数，由于信号功率谱密度在数据子载波频段内是连续的，那么

$$
\frac { \dot { \sigma } } { \sigma ^ { 2 } } { = } \frac { ( \pi N ) ^ { 2 } } { 3 T }
$$

其中 $T$ 为采样时间。设单个超门限峰值持续时间为 $\tau$ ，则在1s内TDCS信号峰值的变化情况可由图4表示。

![](images/710107edd1864b2a6b8e00cb7b1ff8f3b8414a5c15dde925483b3fd1d7fb110a.jpg)  
图4TDCS信号峰值分析图

在图4所示的情况中，超过门限的峰值个数为 $p _ { t h } = 3$ ， $\tau$ 的均值 $\overline { { \tau } } = ( \tau _ { { 1 } } + \tau _ { { 2 } } + \tau _ { { 3 } } ) / 3$ ，则

$$
\operatorname* { P r } \left\{ \left| s _ { n , \mathrm { i } } \right| > \gamma \right\} = p _ { t h } \overline { { \tau } } = \tau _ { 1 } + \tau _ { 2 } + \tau _ { 3 }
$$

那么 $\overline { { \tau } }$ 可以表示为

$$
\overline { { \tau } } = \operatorname* { P r } \left\{ \left| s _ { n , \mathrm { i } } \right| > \gamma \right\} / \ p _ { t h } = \frac { \sigma ^ { 2 } \sqrt { 2 \pi } } { \dot { \sigma } \cdot \gamma } = \sqrt { \frac { 6 } { \pi } } \frac { T \cdot \sigma } { N \cdot \gamma }
$$

由式(17)可知， $\bar { \tau }$ 与子载波数成反比，与信号功率 $\sigma$ 成正比，传统限幅滤波是对频率插零后的信号进行限幅，然后将插零位置数据置零并删除，子载波数目 $N$ 相对滤波之前的限幅信号有所减少，导致 $\bar { \tau }$ 增加，引起峰均比回升，而本文的改进算法对功率相对较小的限幅噪声 $d _ { n , i }$ 进行滤波处理，在子载波减少相同数目的条件下，降低了 $\bar { \tau }$ ，从而获得更好的峰均比抑制效果。

# 4 仿真分析

为了验证本文改进算法有效性，选择对其峰均比抑制性能、滤波性能及系统误码率进行仿真实验。

仿真实验中，系统采样速率 $f _ { s } { = } 5 1 2 \ : \mathrm { M H z }$ ，基函数子载波数为 $N { = } 5 1 2$ ，采用CCSK调制，电磁频谱环境为 $10 \%$ 的窄带干扰，采用Burg 法进行功率谱估计，干信比为4dB，传输信道为高斯白噪声信道。限幅比例 $C R { = } 1 . 6$ ，对1000个TDCS调制信号的PAPR统计其概率分布。

![](images/584b921aa865171d719d6b46441fea784864d13931267644eceb9dcd8a1fe6a4.jpg)  
图5TDCS信号峰均比分布图

本文将改进迭代限幅滤波算法和传统算法的峰均比抑制效果进行了对比仿真，当 $C R { = } 1 . 6$ 时， $P A P R$ 理论值约为 $4 \ : \mathrm { d B }$ 。从图5可知，第一次迭代处理，在 $C C D F { = } 0 . 0 1$ 时，改进算法将峰均比控制在6dB左右，相比传统算法提升约1dB。在第三次迭代时改进算法可获得比传统算法第四次迭代更好的峰均比抑制效果。改进算法较传统算法峰均比更快收敛于4dB的理论值。

![](images/521328c53fbbefd35e1c737c76e689e17cd7eb4742515122b4f62740bedbc351.jpg)

![](images/4003b02e1d6051fc4c67658cae689bcbee6b9f868c07c136f78ef3ac93c14ccf.jpg)

(c）加入滤波后限幅信号功率谱   
图6TDCS 信号功率谱

本文对滤波抑制带外频谱扩散的有效性进行了仿真验证，如图6所示。图中，(a)是在 $10 \%$ 窄带干扰下，未经任何处理的TDCS 调制信号功率谱；(b)是经过限幅处理后的TDCS信号功率谱，可以看出限幅使信号频谱在非传输频带上发生了扩散，这将影响TDCS系统的传输性能；(c)是对限幅噪声进行滤波处理后TDCS信号功率谱，当频率为 $1 8 0 \mathrm { M H z }$ 时，带外辐射功率比未加滤波限幅法降低约5dB。

本文对改进算法的 TDCS 系统误码率性能进行了仿真分析，码元数量为10000，如图7所示，通过对比可知，在$E b _ { - } n 0 < 4 d B$ 的情况下改进算法误码率与传统算法相近，在$E b _ { - } n 0 > 4 d B$ 的情况下略微有所增高。由于改进算法提升了峰均比抑制性能，引入了更多的限幅噪声，导致误码率上升，但其对TDCS传输性能损失非常低，因此改进算法能够适用于

TDCS 系统。

![](images/ef429b7a02b2141f305acb1e0446967b77613c78d75a26e820226667c91fd6d5.jpg)  
图7TDCS 系统误码率

# 5 结束语

针对TDCS信号存在较高的峰均比、限幅滤波所产生峰均比回升及传统限幅滤波算法计算复杂度高，峰均比抑制效果差的问题，提出了改进迭代限幅滤波的TDCS信号峰均比方案。仿真结果表明该方案能在提升峰均比抑制效果的同时有效降低带外频谱扩散，用较少的迭代次数获得更好的峰均比抑制效果，其对提升TDCS系统传输性能有实际意义。

参考文献：   
[1]Jin Chuanxue,Hu Su,Huang Yixuan，et al.On transform domain communication systems under spectrum sensing mismatch: a deterministic analysis [J]. Sensors,2017,17(7):1594.   
[2]王桂胜，任清华，姜志刚，等．基于信号特征空间的 TDCS干扰分类识 别[J]．系统工程与电子技术,2017,39(9):1950-1958.(Wang Guisheng, Ren Qinghua,Jiang Zhigang,et al. Jamming classification and recognition in transform domain communication system based on signal feature space [J].Systems Engineering and Electronics,2017,39 (9): 1950-1958.)   
[3]孙乐，张衡阳，魏军，等.FRFT-TDCS 应对多分量LFM干扰的最优阶 次选择算法[J].计算机应用研究，2017,34(10):3121-3124.(Sun Le, Zhang Hengyang,Wei Jun,et al. Optimal order selection algorithm for FRFT-TDCSwith multi-component LFM interferencesignal [J]. Application Research of Computers,2017,34 (10): 3121-3124.)   
[4] 徐兵政，任清华，孟庆微，等．小波变换域通信系统中连续均值剔除算 法研究[J].空军工程大学学报：自然科学版，2018,19(5):32-39.(Xu Bingzheng，Ren Qinghua,Meng Qingwei,et al. Research on consecutive mean excision algorithm in wavelet domain communication system [J]. Journal of Air Force Engineering University (Natural Science Edition）, 2018,19 (5): 32-39.)   
[5]梁源，达新宇，张喆，等．隐蔽通信中变换域通信系统双门限基函数设 计[J].华中科技大学学报：自然科学版，2017,45(11):11-16.(Liang Yuan,Da Xinyu, Zhang Zhe,et al. Design of double-threshold basic function in transform domain communicationsystem for covert communication [J]. Journal of Huazhong University of Science& Technology: Nature Science Edition,2017,45 (11):11-16.   
[6]Chang Cheng,Hao Huan,Guo Jianmin，et al.Complementary peak reducing signals for TDCS PAPR reduction [J]. IET Communications, 2017,11 (6): 961-967.   
[7]Ochiai H,Imai H.Performance analysis of deliberately clipped OFDM signals [J].IEEE Trans on Communications,20O2,50(1): 89-101.   
[8]杨超，王勇，葛建华．联合迭代滤波与压扩参数优化的 OFDM 信号峰 平比抑制[J].通信学报,2015,36(4):163-169.(Yang Chao,Wang Yong, Ge Jianhua. Companding transform technique combined with iterative filtering forreducingPAPR of OFDM signals[J].Journalon Communications,2015,36(4):163-169.)   
[9]Byung Moo Lee.Performance analysis of the clipping scheme with SLM technique for PAPR reduction of OFDM signals in fading channels [J]. Wireless Personal Communications,2012,63(2):331-344.   
[10] Singh S,Kumar A.Performance analysis of adaptive clipping technique for reductionof PAPR in alamouti coded MIMO-OFDM systems [J].Procedia Computer Science,2016,93:609-616.   
[11] Wang Luqing,Tellambura C.A simplified clipping and filtering technique forPAR reduction in OFDM systems [J]. IEEE Signal Processing Letters, 2005,12 (6): 453-456.   
[12]Li Xiaodong,Effect of clipping and filtering on the performance of OFDM [J].IEEE Communications Letters,1998,2(5): 131-133.   
[13]郭红．概率论与数理统计[M].北京：高等教育出版社，2010.(Guo Hong.Probability theory and mathematical statistics [M].Beijing:Higher Education Press,2010.   
[14] Zhi Xiaohuan,Hao Huan,Yu Xiao.Peak-to-average power ratio analysis and reduction in transform domain communication system [C]// Proc of IEEE,International Conference on Signal Processing.2O17: 1191-1195.   
[15] Yang Lin, Song Kun,Yun Ming Siu.Iterative clipping noise recovery of OFDM signals based on compressed sensing [J].IEEE Transon Broadcasting,2017,63 (4): 706-713.   
[16] Wang Y C,Luo ZQ. Optimized iterative clipping and filtering for PAPR reduction of OFDM signals [J].IEEE Trans on Communications,2011,59 (1): 33-37.