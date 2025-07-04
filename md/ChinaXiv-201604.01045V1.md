# 测距数传一体化调制解调技术

石立国1,2，王竹刚²，熊蔚明²，候鸿杰1.2(1.中国科学院空间科学与应用研究中心北京100190；2.中国科学院大学北京100190)

摘要：实现小卫星编队飞行,在测定小卫星之间的距离的同时,还必须进行星间科学实验数据的交换。为了尽可能降低设备复杂度,本文研究了一种测距、数传一体化调制方式的调制解调原理,通过 Simulink仿真分析得到了 $\mathrm { G M S K } +$ PN信号在不同测距调制度条件下的数传误码率。经过分析 $\mathrm { G M S K + P N }$ 信号的特性，给出了 $\mathrm { G M S K + P N }$ 信号的信道估计方法和一种有效的测距、数传一体化解调算法。

关键词：高斯最小频移键控；伪码测距；信噪比；误码率

中图分类号： $\mathrm { T N } 9 2 7 { + } . 2$ 文献标识码：A 文章编号 :1674-6236(2016)04-0001-03

# Modem technology for integrated ranging and telecommunication system

SHI Li-guo1,2，WANG Zhu-gang², XIONG Wei-ming²,HOU Hong-jie1,2 (1.Center for Space Science and Applied Research of Chinese Academy of Sciences ， Beijing 100190, China; 2. University of Chinese Academy of Sciences，Beijing 100190,China)

Abstract:Forthesmallsatelltes formationflying，thedistancebetweensatelites mustbedeterminedandanadequate intersatelitescommunication mediummustbeused to transmit thesciencedata.Inordertominimizedevicecomplexity,this paper studiedasystem capableof simultaneously transmiting high rate telecommunication and ranging.through simulations by Simulink indiferentranging modulation index，obtainedthebiterrorrateof telecommunication data.Byanalyzing the characteristics of GMSK $+ .$ PN signal,an effective demodulation scheme for GMSK $+$ PN is developed by this paper.

Key Words: Gaussian minimum shift keying；pseudo-noise ranging；signal to noise ratio；bit error rate

DOI:10.14022/j.cnki.dzsjgc.2016.04.001

编队飞行的微小卫星具有体积小、功耗低、周期短等优点，而实现编队飞行需要有测量星间距离、姿态的测量系统和进行星间数据交换的通信系统2。为了减小微小卫星测控系统的体积和重量，使用一套设备完成测距和数传两大功能，是非常有必要的。

随着航天技术的飞速发展，人们对深空探测中通信链路的吞吐量、低信噪比条件下的测距精度有了更进一步的要求,常规的S频段统一测控系统(Unified S-Band System,USB)已不能够满足要求。伪码测距以其测量精度较高及捕获时间短、能够适应低信噪比情况下的测距要求和设备相对简单等优点，成为了航天测控领域研究的热点。2009年3月，CCSDS建议使用Tausworthe复合码作为伪码测距的伪随机码。Tausworthe复合码适合用于深空测距和近地测距，具有测距捕获时间短、硬件实现复杂度低、测距精度相对较高的特点，并且Tausworthe复合码与每个子码也具有良好的互相关和自相关特性，是深空测控系统数字应答机的主要研究和发展方向。

由于现在空间业务的增加，通信容量急剧增长，星载数据调制方式为了适应非线性功放的特性、降低信号解调门限，不宜选择高阶信号调制方式。同时，发射信号功率谱还必须符合空间频率协调组(SFCG）、国际电信联盟(ITU)等管理机构的规定。所以，要求星载设备采用的调制方式产生的信号频谱扩展最小化，使其具有恒包络及高频带效率的特性。高斯最小偏移键控（Gaussian Minimum ShiftKeying,GMSK)是连续相位调制方式，它采用高斯滤波器对输入的数据进行预滤波，平滑了相位轨迹，已调信号具有旁瓣衰减快、频谱紧凑、带宽效率高的特点，并且信号是恒包络的。

基于 $G \mathrm { M S K + P N }$ 体制的测距与数传联合技术[3,兼有两者的特点，因此对GMSK联合Tausworthe测距码的研究是非常有意义的。在伪码测距系统中，伪码的直流分量对测距信号的功率以及对载波的捕获有着重要的影响。平衡码T4B（平衡4倍加权Tausworthe码)和T2B（平衡2倍加权Tausworthe码）的直流分量都非常的小。文中对GMSK联合Tausworthe码的调制解调方式进行了研究，并通过Simulink对这种同时传输高码率数传和测距信息的信号进行了仿真和特性分析。

# 1 GMSK+PN调制技术

基于 $G \mathrm { M S K + P N }$ 的调制体制、能够同时传输数传和测距遥测数据 预编码电平转换高斯滤波一积分器伪码数据电平转换 半正弦滤波调制度 PM调制

伪码数据经过电平转换和半正弦滤波后，乘以伪码调制度因数得到伪码测距信号相位；数传数据经过预编码、电平转换、高斯滤波和积分器后，得到GMSK相位；伪码相位和GMSK相位再经过相位调制，即可得到 $\mathrm { G M S K + P N }$ 调制信号4：

$$
s \left( t \right) = \sqrt { 2 P _ { t o t } } \cos \left( \omega _ { c } t + \varphi _ { G M S K } ( t ) + m _ { d } \varphi _ { P N } ( t ) \right)
$$

其中 $P _ { t o t }$ 为总功率， $\omega _ { c }$ 为载波角频率， $\varphi _ { G M S K } ( t )$ 为数传信号相位 ${ \varphi } _ { P N } ( t ) = D ( t ) \sin ( \frac { 1 } { 2 } \omega _ { P N } t )$ 为正弦波、 $D ( t )$ 为伪码序列， $m _ { d }$ 为测距码调制指数。

由GMSK调制原理可以得到：

$$
\varphi _ { G M S K } ( t ) = \pi \sum { a _ { n } \intop _ { - \infty } ^ { t - n T _ { b } } g ( \tau - n T _ { b } ) \mathrm { d } \tau }
$$

式(2)中， $a _ { n }$ 表示双极性非归零基带数据， $g ( t )$ 是高斯滤波冲击响应，其表达式为：

$$
\begin{array} { l } { { \displaystyle \left[ g ( t ) = \frac { 1 } { 2 T _ { b } } [ Q ( \frac { 2 \pi B T _ { b } } { \sqrt { \ln 2 } } ( \frac { t } { T _ { b } } - 1 ) ) - Q ( \frac { 2 \pi B T _ { b } } { \sqrt { \ln 2 } } ( \frac { t } { T _ { b } } ) ) ] \right. } } \\ { { \displaystyle \left. Q ( x ) = \int _ { \mathrm { \small ~ x ~ } } ^ { \infty } \frac { 1 } { \sqrt { 2 \pi } } \exp ( - \frac { y ^ { 2 } } { 2 } ) \mathrm { d } y \right.}  }  \end{array}
$$

式（3）中， $B$ 为高斯脉冲的 $3 ~ \mathrm { d B }$ 带宽， $B T _ { b }$ 为时间带宽乘积，一般取值为0.25(近地)或0.5（深空）。 $B T _ { b }$ 决定了GMSK调制的带宽效率。 $T _ { b }$ 为数传信号码元周期。

伪码测距信号表达式为：

$$
{ x _ { P N } } ( t ) \mathrm { { = } } \displaystyle \sum _ { n = - \infty } ^ { \infty } D _ { n } h _ { s q / \mathrm { { s i n } } } ( t { - } n T _ { c } )
$$

$$
h _ { s q / \mathrm { s i n } } ( t ) = \left\{ \begin{array} { c } { h _ { s q } ( t ) = 1 , t \in [ 0 , T _ { c } ] } \\ { h _ { \mathrm { s i n } } ( t ) = \sqrt { 2 \hslash } \sin \left( \pi t / T _ { c } \right) , t \in [ 0 , T _ { c } ] } \end{array} \right.
$$

其中 $D _ { n }$ 是测距伪码(T2B或T4B)。伪码成型脉冲 $h _ { s q / \mathrm { s i n } } ( t )$ 有方波和半正弦两种，在本文中，应用的是半正弦滤波的方式。其中伪码测距信号的调制度为 $m _ { d } { = } \displaystyle \frac { \sqrt { \ln 2 } \ \pi } { 2 } h , h$ 是测距信号的加权因子。数传信号功率和伪码测距信号的功率比由测距调制度决定，调制指数越大， $\mathrm { G M S K + P N }$ 信号中包含的伪码测距信号越多，测距信噪比越高，测距抖动误差越小。随着测距信号加权因子的增大，调制指数增大，数传数据误码率也会受到比较明显的影响。

# 2 $\mathbf { G M S K + P N }$ 解调技术

# 2.1 GMSK解调

一般地，空间通信系统的信道是加性高斯噪声信道。这种情况下，GMSK信号的相干解调比非相干解调有更好的误码性能。在GMSK的相干解调方案中，有基于Viterbi检测和基于劳伦分解两种方法。基于Viterbi检测的方法可以得到较好的误码性能，但是实现起来非常复杂。而基于劳伦分解近似的相干解调方法，复杂度比Viterbi检测小很多，容易实现，并且误码率不会有太大降低。因此本文拟采用基于劳伦分解近似的相干解调。

劳伦提出了一种用多个相移调幅脉冲(AMP)流叠加来表示CPM(连续相位调制)，可以把GMSK调制信号看成是多个振幅/相位调制脉冲流的叠加，如式(6)所示，其中 $C _ { k } ( t )$ 是第 $k$ 个AMP流的等效脉冲波形。对于 $B T _ { b } { = } 0 . 5$ 的GMSK信号（适用于深空），仅用第一个脉冲分量表示就可以达到足够的精度。对于 $B T _ { b } { = } 0 . 2 5$ 的情况(适用于近地)，只用第一个分量性能会稍差一些。这时可以在两个支路上分别加一个维纳均衡器，提高性能。

$$
s \left( t \right) = \sqrt { \frac { 2 E _ { b } } { T _ { b } } } \sum _ { K = 0 } ^ { 2 ^ { L - 1 } - 1 } \left[ \sum _ { n = - \infty } ^ { \infty } C _ { K } ( t - n T _ { b } ) \cos \left( 2 \pi f _ { c } + \frac { \pi } { 2 } A _ { K , n } \right) \right]
$$

GMSK的劳伦分解近似具有基带成形OQPSK的信号形式，这也就是为什么OQPSK解调器可以用于GMSK解调的原因。在正交的各信道上脉冲互相叠加，两路错开 $T _ { b }$ ，实际的符号速率 $\scriptstyle { T _ { s } = 2 T _ { b } }$ ,基于以上分析，可以得出GMSK基于劳伦分解近似的相干解调原理如图2所示，图中 $C _ { 0 } ( t )$ 的框图表示只与AMP第一分量匹配的滤波器7。图3给出了GMSK解调在不同测距调制度条件下的误码率曲线。可以看出随着测距调制度的增大，数传信号的误码率也会相应变大。

![](images/b43815912040457024102d51ca216c9f9b7121b5af3697c953f1889a37f0f89a.jpg)  
Fig.1Modulation system block diagram   
图2 GMSK解调框图

![](images/bf4f5188a16ef1bacb46d8de3036361eeb1edbf27290664d4b196cfa57811eac.jpg)  
图1系统调制框图  
Fig.2 GMSK demodulation block diagram   
图3 $\mathrm { G M S K + P N }$ 解调误码率曲线Fig.3 $\mathrm { G M S K + P N }$ demodulation BER curve

# 2.2 GMSK、PN信号分离

因为基带的GMSK数据信号（所代表的相位)和PN测距信号(所代表的相位)在时域上是相加的，所以，如果得到其中的任何一种信号，就可以由复合与某一种“再生”的信号复相关，即可得到另一种信号。因为按照常规，GMSK信号在复合信号中所占的能量比例很大。所以，可以直接在已调载波信号上解调，得到GMSK基带信号。再由GMSK信号的基带再调制得到的相位，与输入信号进行复相关，即可得到单独的PN伪码测距信号。

# 2.3PN信号捕获、跟踪

T2B码或T4B码是Tausworthe类型的复合伪码，可以采用特定的捕获方法来捕获这种复合结构伪码信号的相位，只需找到各个子码的相位，即可复现Tausworthe码。Tausworthe码的串行捕获由5个相关支路组成（其中C1码为码钟分量，直接通过锁相环路进行跟踪）。Tausworthe码的各个子码采用并行捕获的方案。

Tausworthe 码的跟踪拟采用CTL(Chip Tracking Loop）结构,这种结构是 DTTL(Data Transition Tracking Loop)同相/中相定时算法的一种变形形式。同相/中相算法是一种以闭环方式工作的同步算法，该环路同时利用同相与中相信道两者的信息来判断定时误差的大小和极性。码跟踪环是一种改进的同相/中相环路，将同相/中相积分环路输出的鉴相误差进行码片的累加，解决低信噪比下的信号跟踪问题。

# 3 $\mathbf { G M S K + P N }$ 信号信道估计

由于 $\mathrm { G M S K + P N }$ 信号既包括数传信号，又包括伪码测距信号，无法直接进行信噪比估计。而 $G \mathrm { M S K + P N }$ 信号的结构非常特殊，在数传信号的基础上，直接加入了伪码测距信号（作为数传信号的相位抖动存在），故可以采用逐层简化的方式，将 $G \mathrm { M S K + P N }$ 信号分解为若干层。本文采取反推的方法，先估计出PN信号中 $C 1$ 子码分量的信噪比，即可以通过PN信号与C1子码分量的功率分配，得到PN信号的信噪比。进而，通过 $\mathrm { G M S K + P N }$ 信号的能量分配，得到整个 $\mathrm { G M S K + P N }$ 信号的信噪比。这种新的信噪比估计算法，可以大大降低 $\mathrm { G M S K + P N }$ 信号的信噪比计算的复杂度。通过Simulink搭建仿真模型，取采样率为 $f _ { s } { = } 1 0 0 ~ \mathrm { M H z }$ ，伪码速率为 $f _ { c } { = } 2 ~ \mathrm { M H z }$ ，测距调制度$\scriptstyle m _ { d } = 0 . 2$ rad,再生伪码采用T4B，测得信噪比估计值如图4所示。经过仿真可以发现，信噪比估计值与实际值非常吻合，误差在 $0 . 5 { \mathrm { ~ d B } }$ 以下。参与计算的码片数在大于1000时，信噪比估计值基本稳定实际值附近。

# 4结论

文中研究了一种同时满足高码率数据传输和高精度测距要求的基于 $\mathrm { G M S K + P N }$ 体制的测距与数传技术，通过

![](images/1f52a57080bbc05f6e377a2c96c3daf385ade6eb786db45109975062c0de1686.jpg)  
图4信噪比估计值与估计码片数关系

Fig.4Relationship between estimated SNR and estimate chip numberSimulink对信号频谱与能量分配进行了仿真分析，推荐在捕获时间要求不高的系统中，优先选择T4B码，并给出了$\mathrm { G M S K + P N }$ 在不同参数条件下的数传信号误码率和加性高斯白噪声信道中基带 $\mathrm { G M S K + P N }$ 信号的信噪比估计算法。作为一种通信和测距一体化的调制技术， $\mathrm { G M S K + P N }$ 具有恒包络、频谱利用率高的优势。

# 参考文献：

[1]刘应刚,周依林.微小卫星测控数传一体化发射机数字基 带设计[J].遥测遥控,2010(2):40-46.   
[2]罗续成.编队飞行航天器测量通信一体化系统的交互链 路技术[J].遥测遥控,2007(11):102-107.   
[3] SesslerG,Vassallo E,CalzolariGP,etal.GMSK/PN for high rate telemetry and high accuracy ranging of Lagrange and Mars missions [C]. 13th AIAA International Conference on Space Operations，SpaceOps,2014.   
[4] Orr R S,Divsalar D.Combined GMSK modulation and PN ranging for communications and navigation [C]//Aerospace Conference，IEEE，2008:1-18.   
[5]Laurent P.Exact and approximate construction of digital phase modulations by superposition of amplitude modulated pulses(AMP)[J].Communications，IEEE Transactions on, 1986,34(2):150-160.   
[6]SimonMK.高带宽效率数字调制及其在深空通信中的应 用[M].北京：清华大学出版社，2006.   
[7]Sessler G，Abello R，James N，et al.GMSK demodulator implementation for ESA deep-space missions[J]. Proceedings of the IEEE,2007,95(11):2132-2141.

# 欢迎订阅 2016 年度《电子设计工程》 (半月刊)

国内邮发代号：52-142 国际发行代号：M2996 订价：15.00元/期360.00元/年