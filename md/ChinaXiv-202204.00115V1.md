# RFI抑制技术在射电天文中的应用

张海龙1,2,3,4\*，张亚州1²，王杰4，冶鑫晨1,4，王万琼’，李嘉，张萌1,²，杜旭1,2(1．中国科学院新疆天文台，新疆 乌鲁木齐，830011；2．中国科学院大学，北京，100049;3．中国科学院射电天文重点实验室，江苏南京210008；4.国家天文科学数据中心，北京，100101)

摘要：针对射电天文观测过程中的射频干扰(RFI)问题，详细分析了国内外台站 RFI抑制策略。根据各天文台站实际观测过程中遇到的RFI问题，分别从主动预防阶段、预相关阶段、后相关阶段、机器学习和深度学习等方面研究了RFI的预防策略和抑制方法。详细分析了主动预防阶段可采取的方法，预相关阶段的自适应滤波，和空间滤波方法；后相关阶段的VarThreshold,SumThreshold和奇异值分解等方法。探讨了基于机器学习的主成分分析、支持向量机、全卷积神经网络、卷积神经网络、U-Net等相关技术和方法在RFI信号处理方面的应用。

关键词：RFI；滤波；阈值法；机器学习；中图分类号：P161 文献标识码： 文章编号：

# 1引言

射电天文学中，RFI被定义为任何可能影响天文观测的有害信号，射电天文学发展过程中，抑制 RFI一直是天文学家研究的热点。随着信息技术飞速发展，人为造成的干扰信号导致天文台站周围电磁环境恶化，影响射电望远镜正常观测。

RFI的来源多种多样，包括外部来源和内部来源，外部来源主要由天文台址外设备产生，如人造卫星[ (北斗和GPS 导航卫星等)、飞机、台址附近的基站信号以及电视广播号等；内部来源主要由天文台址内使用的电子设备产生，如计算机、视频监控、网络交换设备、无线输入设备等[2]。天文信号通常为宽频带且在时间尺度上平滑变化，而 RFI在时域和频域的幅值强度高，绝大部分RFI与天文信号相比有明显差异[3]。RFI与热噪声不同，它通常由通信系统、人造雷达或电子设备产生的干扰构成，且通常具有复杂的时间和频率结构，常见通信信号的功率比天文信号高多个数量级并且会随时间变化，因此无法通过长时间积分（累积)来降低其强度，严重影响天文数据质量。天文学家针对上述问题已提出了多种 RFI 抑制方法，但仍受到以下因素制约：

（1）近年来，随着无线技术的飞速发展及人类活动范围的扩大，地面及空间产生的人为干扰逐年递增。

（2）随着制造技术和信息技术的飞速发展，射电望远镜向大口径或大规模阵列方向发展，随着多波束或PAF接收系统的投入使用，使得观测设备的灵敏度及数据收集能力显著提升，同时RFI抑制问题更加复杂。

在射电天文观测以及数据处理过程中需要针对不同阶段采取不同的 RFI应对策略，本文将 RFI抑制策略分为主动预防阶段、预相关阶段及后相关阶段，不同阶段针对RFI问题可采取不同抑制方法。主动预防阶段若能采取有效防护手段，能够杜绝通信基站，电视广播等大部分RFI进入系统;预相关阶段采取参考天线及空间滤波等方法可以应对特定RFI源;后相关阶段中可以采取阈值法处理幅值强度远大于天文信号RFI，或利用机器学习相关技术实现RFI数据标记。下面针对不同阶段可采取的RFI抑制策略进行详细分析：

# 2RFI主动预防阶段

# 2.1电磁波宁静区

射电望远镜观测的是来自宇宙遥远天体的微弱信号，对台址周边电磁干扰有较高要求，选择地理环境较好的台址及建立无线电宁静保护区是抑制 RFI 的重要一步，可以从根源上去除大部分干扰。 $5 0 0 \mathrm { m }$ 口径球面射电望远镜 (Five-hundred-meter Aperture Spherical radioTelescope，FAST)，是世界最大单口径、最灵敏的射电望远镜，位于贵州省黔南布依族苗族自治州平塘县克度镇大窝函，以FAST台址为中心，建立半径为 $3 0 \mathrm { k m }$ 的 FAST 电磁波宁静区，分为不同要求的3个区域。其中以台址为圆心，半径 5km 范围为保护核心区，$5 { \sim } 1 0 \mathrm { k m }$ 的环带为中间区， $1 0 { \sim } 3 0 \mathrm { k m }$ 的环带为边远区[4]，如图1所示，能够屏蔽绝大部分外来干扰源。

Haohua Zhangbu hong Guizhou Province Town Yashui Ln Datang Lushan Town Town Town Town Pingzhou Xiantang Yazhou Town Huishui CO Town 心 Tongzhou Duanshan Town   
Wangyou Town Town PingtangCo. Tangbiar Town Kedu Zhemi Jiacha Town Bianyang Town Town Town Luodian Co. Moyang Town   
Muyin Town Lowping GuangxiZhuang Autonomous Fengting Town Mowjing Region

新疆奇台110 米全向可动射电望远镜(Qi Tai Radio Telescope,QTT)[5]，位于新疆昌吉州奇台县，以QTT台址为中心，依据QTT地形特征及当地实际情况，规划了 $3 0 \mathrm { k m }$ 的无线电宁静区，该宁静区共分为三个区域，分别为核心区、限制区、协调区．其中核心区域为 2.5$\mathrm { k m } { \times } 4 \mathrm { k m }$ 的矩形区域；限制区域为 $1 0 \mathrm { k m } \times 1 5 \mathrm { k m }$ 的矩形区域[6-7]，如图2所示。

![](images/feb2eca4c83d35c22a45511495f176dfc99f68dcc6cbd08ffd7c3bce460edfe6.jpg)  
图1FAST无线电宁静保护区(来源文献[25])  
Fig.1 FAST Radio Quiet Zone   
图2QTT无线电宁静保护区(来源文献[6])Fig.2QTTRadio Quiet Zone

# 2.2预留频段

国际电信联盟（ITU）通过划分频谱来协调8.3MHz-300GHz之间的无线电频谱，将其分为几个频带，仅允许指定服务运行'。在分配的所有频段之间，约有 70到80个频段对应于射电天文学（确切的数量取决于地区和当地法律）。针对射电天文频段，一种是射电天文专用频段（或与无源服务共享），严格禁止无线电发射；另一种是与有源业务共享的频段，只能部分施加保护。射电天文的波段选择通常与科学目标有关。例如，氢线（由于中性氢原子状态的改变而发射）位于1420 MHz 附近，因此1400-1427MHz频带保留给射电天文学²。

即使射电天文专用频段，由于有源元件的谐波和功率泄漏，仍然可能存在干扰。对于这些情况，ITU 在其ITU-RRA.769 建议报告中，将最大可接受的干扰定义为在测量功率中引入不超 $10 \%$ 的误差，这是天文学家普遍接受的阈值，该报告还为一些典型的天文波段提供了一份使用普通望远镜和观测参数的建议阈值清单。

# 2.3RFI主动预防策略的不足

RFI 主动预防策略中最直接的方法是为天文台选择远离干扰源的偏远位置。自然形态（例如山脉）可以有效地阻止外部干扰，但干扰源会因为多径传播产生反射和衍射，从而增加干扰抑制难度。一些观测站研究发现，在望远镜台址周围种植松树等针叶树可有效抑制RFI，树针中的水分可吸收1GHz 以上的信号4。部分天文台站建在高海拔地区以减少大气对观测的影响且远离人类活动范围，同时尽可能避免干扰源多径传播。面对内部干扰，通常的办法是在产生干扰的电子设备（计算机、微波和射频元件）上覆盖电磁屏蔽材料，比如导电箔，也可以将电子设备集中放入屏蔽室，将干扰控制在密闭空间，并不影响设备性能。

通常，主动预防是处理干扰的最有效方法，可作为RFI的第一层防护。但仍然存在不足：

(1）只能为电磁频谱的小部分提供保护。  
(2) 对于高灵敏度的设备，电磁屏蔽材料并不能完全屏蔽干扰。  
(3) 卫星通信以及飞机等产生的干扰，由于相对位置限制，无法通过主动预防的方法避免。

# 3RFI预相关阶段

本文将观测获取的原始数据在未写入磁盘形成可供科学研究处理之前的 RFI 处理阶段定义为预相关阶段。对于单大线观测可利用参考大线通过自适应滤波方式去除特定干扰，对于阵列天线可采用空间滤波方法抑制RFI。

# 3.1自适应滤波

自适应滤波算法是由Barmbaum 和Bradley在1998 年首次引入射电天文领域用来解决RFI 问题[8，在2005 年，Kesteven 等人进行了现场试验，在RFI存在的情况下，自适应滤波方式能够极大改善脉冲星观测[9]。

![](images/5b136bbfc01b9f0ce518ff76c59b9ef4cc13258cb23b0dbe4a937f6da5ffc39f.jpg)  
图3自适应滤波器基本设计图  
Fig.3 Adaptive filter basic design diagram

参考天线接收的信号可表示为：

$$
R = R _ { n o i s e } + R _ { r f i } + R _ { a s t } \# ( 1 )
$$

其中 $R$ 表示参考天线接收的信号， $R _ { n o i s e }$ 表示参考天线的系统噪声， ${ R _ { r f i } }$ 表示参考天线接收的RFI， $R _ { a s t }$ 表示参考天线接收到的天文信号，天文信号通过参考天线的旁瓣接收，其强度微弱可忽略不计。同理，主望远镜接收的信号可表示为：

$$
M = M _ { n o i s e } + M _ { r f i } + M _ { a s t } \# ( 2 )
$$

主望远镜和参考天线接收的系统噪声不相关，而接收的 RFI具有相关性。为了消除主天线中的RFI，使其对准RFI源，并通过不断优化参考天线的指向及极化方向可提高参考天线中 RFI信噪比。

自适应滤波具体实现步骤：

(1）在自适应相关环路中确定复增益系数 $g$ （该系数是不断迭代优化的）与参考天线接收的信号 $R$ 相乘，逐步迭代 $g \cdot R _ { r f i }$ ，使其大小接近主天线的 RFI 信号，能最大程度消除主天线某一特定方向的 RFI。  
(2)当 $g$ 达到最优值时， $\boldsymbol { g } \cdot \boldsymbol { R _ { r f i } }$ 基本接近 $M _ { r f i }$ ，天文信号与参考信号的差值即为去除特定干扰后的天文信号。  
(3）图3为自适应滤波器基本设计图，将原始参考信号与滤波器输出相关，当相关系数为零时，达到最佳增益。

相关项计算如公式（3）所示，

$$
C ( g ) = ( M - g \cdot R ) \cdot R \# ( 3 )
$$

当 $C ( g ) = 0$ 时，可剔除主天线的RFI，即

$$
0 = M - g \cdot R \Rightarrow M = g \cdot R \Rightarrow g = { \frac { M } { R } } \# ( 4 )
$$

代入天线接收的各个分量得：

$$
\begin{array} { l } { { g = \frac { { { M _ { n o i s e } } + { M _ { r f i } } + { M _ { a s t r } } } } { { { R _ { n o i s e } } + { R _ { r f i } } + { R _ { a s t r } } } } } } \\ { { \mathrm { } } } \\ { { \displaystyle = \frac { { \left( { { M _ { n o i s e } } + { M _ { r f i } } + { M _ { a s t r } } } \right) \cdot \left( { { R _ { n o i s e } } + { R _ { r f i } } + { R _ { a s t r } } } \right) } } { { \left( { { R _ { n o i s e } } + { R _ { r f i } } + { R _ { a s t r } } } \right) \cdot \left( { { R _ { n o i s e } } + { R _ { r f i } } + { R _ { a s t r } } } \right) } } \# } } \end{array}
$$

因为两个天线的系统噪声、天文信号、其他信号均与RFI不相关，参考天线中的天文信号非常微弱，可以忽略不计，即 $R _ { a s t } = 0$ ，那么上式进一步简化得：

$$
g = \frac { M _ { r f i } \cdot R _ { r f i } } { R _ { n o i s e } ^ { 2 } + R _ { r f i } ^ { 2 } } \# ( 6 )
$$

令 ${ M _ { r f i } } = \xi { R _ { r f i } }$ ， $g$ 可以写为：

$$
\mathbf { g } = \frac { \xi } { 1 + 1 / I N R } \# ( 7 )
$$

其中 INR(Interference-to-Noise Ratio)是参考天线中的干扰噪声比，等于 $R _ { r f i } ^ { 2 } / R _ { n o i s e } ^ { 2 }$ ，可以明显看出，当INR越大， $g$ 值越小，自适应滤波器效果越好。输出信号中RFI的残留量为

$$
\begin{array} { r l } & { S _ { r f i } = M _ { r f i } - g \cdot R _ { r f i } } \\ & { \quad \quad = M _ { r f i } - \cfrac { \xi } { 1 + \cfrac { 1 } { I N R } } \cdot R _ { r f i } } \\ & { \quad \quad = \cfrac { M _ { r f i } + M _ { r f i } \cdot I N R - \xi I N R \cdot R _ { r f i } } { 1 + I N R } } \\ & { \quad \quad = \cfrac { M _ { r f i } + M _ { r f i } \cdot I N R - \cfrac { M _ { r f i } } { R _ { r f i } } \cdot I N R \cdot R _ { r f i } } { 1 + I N R } } \\ & { \quad \quad = \cfrac { M _ { r f i } + M _ { r f i } \cdot I N R - \cfrac { M _ { r f i } } { R _ { r f i } } \cdot I N R \cdot R _ { r f i } } { 1 + I N R } } \end{array}
$$

$$
= \frac { M _ { r f i } } { 1 + I N R } \# ( 8 )
$$

在天文观测中，主天线指向待观测的天体， $M _ { r f i }$ 在观测期间可以认为是恒定量， $\boldsymbol { S _ { r f i } }$ 与INR 成反比，即INR 越大， $\boldsymbol { S _ { r f i } }$ 越小，说明提高RFI在参考天线中信噪比能提高主天线RFI抑制能力。

影响自适应滤波性能的几个因素：

（1）混合RFI源

自适应滤波方法消除单源RFI效果较好，但是面对复杂的RFI环境，其抑制RFI的性能会大幅度下降。对于混合RFI，当两个干扰信号处于相同频域时，振幅大的干扰将被消减。对于天文台址附近 RFI来源复杂，且与天文信号相比具有较高的功率，在此类条件下自适应滤波方法 RFI抑制效果一般[10]。

（2）多路径传播影响

多径传播是指由于信号到达接收天线的路径不同，而存在同一信号的多个副本的现象，通常是由大型陆地物体(山脉、建筑物)、大型水体 (湖泊、泻湖）和电离层反射产生的。

![](images/81bb66eced96c3880ea10a582b4a0adb1bd6440c9952c9580dadf2840b32a8cd.jpg)  
图4RFI多径传播情况  
Fig.4 RFI multipath propagation situation

图4描述了多路径干扰信号传播场景。因为到达望远镜和参考天线的多个副本有不同的时间延迟。如果延迟足够大，那么添加的信号就可以被望远镜视为完全不相关。在这种情况下，多路径情况相当于多个RFI源，RFI信号种类繁多，难以获得滤波器多径传播的通用表达式。防止多径传播的最佳措施是将望远镜和参考天线放置在尽可能近的位置，以减小传播距离差异，并通过增加 FFT点数来提高系统的频率分辨率，或在FFT 点数不变的条件下减少系统带宽[10]。

（3）违反线性时不变(LTI)条件

假设干扰传播路径至少在滤波器收敛的时间内满足LTI条件。如果不满足LTI条件，则表示RFI路径在某些地方呈现非线性或时变的传播特性。然而，没有任何自然介质表现出足够强的非线性，或具有快速变化的传播特性，而影响滤波器的性能，特别是考虑到最终算法收敛时间是毫秒级的。当望远镜在跟踪天体移动时，捕获 RFI 的旁瓣随望远镜一起移动，被测 RFI 的路径特性会随时间逐渐变化。自适应滤波方法需具备相应计算能力，以使其不会因望远镜的缓慢移动而受到明显影响。

接收机前端的一些模拟元件是信号饱和的，如放大器和频率混频器。当一个分量达到饱和时，输入信号的幅值就会被削去，从而产生谐波失真，将会影响系统的LTI 条件。这种失真被视为附加的损坏信号，其频率是原始输入信号中心频率的几倍。此外，由于数字化后的混叠等原因，谐波信号往往会被混入基带从而破坏天文数据。主信道 RFI 谐波失真会严重破坏滤波器性能，附加的谐波信号不会出现在参考信道中，使得这类RFI更难被抑制[10]。

# 3.2空间滤波

空间滤波方法主要针对多通道射电天文观测中的 RFI 抑制问题[11-13]，该技术适用于干涉射电望远镜阵列，如荷兰的Westerbork 综合射电望远镜(WSRT)，美国的甚大阵列(VLA)，或配置了相控阵接收系统的单天线望远镜。图5显示了空间滤波技术在天线阵列系统中的应用。

![](images/ed22e81ea54ca94ae86947f59859b278d2506e67a31af79edb14dbf621160487.jpg)  
图5天线阵列系统在不同阶段抑制RFI  
Fig.5 Antenna array system suppresses RFI at different stages

射电望远镜接收的信号由三部分组成，射电源信号（拟观测目标）、系统噪声以及RFI。系统噪声由宇宙背景噪声、大气噪声、接收机噪声等噪声分量组成。根据中心极限定理，系统噪声是时间独立的且高斯分布的信号，在短时间间隔上是短时平稳的，且所有的射电源都

被假定在统计学上彼此独立[2]。

射电天文学中的RFI特征是各种各样的。选择中心窄带高斯平稳、二阶非周期和循环平稳信号三种不同的信号特性来建模RFI。

天线阵列共有 $M$ 个天线，其中 $x ( t ) = [ x _ { 1 } ( t ) \cdots x _ { M } ( t ) ] ^ { T }$ 表示的是 $M \times 1$ 个天线阵列的输出，其中第 $k$ 个天线在时间t时刻的输出为 $x _ { k } ( t )$ ，那么 $x ( t )$ 可以被写为

$$
\mathbf { \boldsymbol { x } } ( \mathbf { \boldsymbol { t } } ) = \mathbf { \boldsymbol { A } } _ { \mathbf { \boldsymbol { c } } } \cdot \mathbf { \boldsymbol { c } } ( \mathbf { \boldsymbol { t } } ) + \mathbf { \boldsymbol { A } } _ { \mathbf { \boldsymbol { r } } } \cdot \mathbf { \boldsymbol { r } } ( \mathbf { \boldsymbol { t } } ) + \mathbf { \boldsymbol { n } } ( \mathbf { \boldsymbol { t } } ) \# ( 9 )
$$

其中

(1) $\boldsymbol { c } ( t ) = \left[ c _ { 1 } ( t ) \cdots c _ { N _ { c } } ( t ) \right] ^ { T }$ 表示在 $t$ 时刻时，射电源的特征向量，大小为 ${ N _ { c } } \times 1$ 。

(2) $A _ { c } = \left[ c _ { 1 } ( t , \theta _ { c _ { 1 } } , \phi _ { c _ { 1 } } ) \cdots c _ { N _ { c } } \left( t , \theta _ { c _ { N _ { c } } } , \phi _ { c _ { N _ { c } } } \right) \right] .$ 是射电源的空间特征向量矩阵，大小为 $M \times N _ { c }$ 。其中 $c _ { n } \big ( t , \theta _ { c _ { n } } , \Phi _ { c _ { n } } \big ) = \big [ c _ { n , 1 } \big ( t , \theta _ { c _ { n } } , \Phi _ { c _ { n } } \big ) \cdots c _ { n , M } \big ( t , \theta _ { c _ { n } } , \Phi _ { c _ { n } } \big ) \big ] ^ { T }$ 是第 $\overset { \cdot } { n }$ 个射电源的空间特征向量。同理， $A _ { r }$ 和 $\boldsymbol { r } ( t )$ 分别代表着RFI的空间特征向量矩阵以及在 $t$ 时刻RFI的信号特征向量。

(3） $n ( t ) = [ n _ { 1 } ( t ) \cdots n _ { M } ( t ) ] ^ { T }$ 是系统噪声在 $t$ 时刻的向量，大小为 $M \times 1$ 。通过协方差矩阵描述射电源在时间维度上的相关性，即

$$
R ( t , \tau ) = E \{ x \left( t + { \frac { \tau } { 2 } } \right) \cdot x ^ { H } \left( t - { \frac { \tau } { 2 } } \right) \} \# ( \cdot
$$

其中 $R ( t , \tau )$ 描述在 $t$ 时刻t范围内射电源信号的相关性， $x ^ { H }$ 代表 $x$ 的共轭转置。假设RFI、射电源和系统噪声三者相互独立，即互不相关，那么

$$
\begin{array} { l } { { E \{ c _ { n } \left( t + \displaystyle \frac { \tau } { 2 } \right) r _ { m } ^ { * } \left( t - \displaystyle \frac { \tau } { 2 } \right) \} = 0 , \quad \forall \tau , n \in [ 1 \ldots N _ { c } ] , m \in [ 1 \ldots N _ { r } ] } } \\ { { \ } } \\ { { E \{ c _ { n } \left( t + \displaystyle \frac { \tau } { 2 } \right) n _ { m } ^ { * } \left( t - \displaystyle \frac { \tau } { 2 } \right) \} = 0 , \quad \forall \tau , n \in [ 1 \ldots N _ { c } ] , m \in [ 1 \ldots M ] } } \\ { { \ } } \\ { { E \{ r _ { n } \left( t + \displaystyle \frac { \tau } { 2 } \right) n _ { m } ^ { * } \left( t - \displaystyle \frac { \tau } { 2 } \right) \} = 0 , \quad \forall \tau , n \in [ 1 \ldots N _ { r } ] , m \in [ 1 \ldots M ] \# ( \log \left( 1 \ldots N _ { r } \right] ) } } \end{array}
$$

从线性代数的观点来看，相控天线阵列射电望远镜数据协方差矩阵可以看作是线性变换矩阵。这个矩阵生成一个数据向量空间，该向量空间由RFI子空间、射电源子空间和系统噪声子空间组成。图5展示了一个无噪声场景下的二维数据向量空间的示例。红色和黑色矢量分别代表与射电源和射频干扰源相关的向量。

![](images/1f381979b561847ab6d6e7fd7b464fe85e683eaca3e7518397997d0f9f7d9cff.jpg)  
图6二维数据向量空间的正交投影

Fig.6 Orthogonal projection of a two-dimensional data vector space

使用正交投影技术减少干扰，将数据向量空间投影到与RFI子空间正交的子空间上，投影的RFI子空间完全为零，由此产生的数据只包含射电源。

从图6上可以清楚地看出，在投影后，恢复的射电源能量取决于两个向量的夹角大小，即

$$
P _ { p r o j } ^ { 2 } = P ^ { 2 } \cdot s i n \left( \Theta _ { a _ { c } , a _ { r _ { n } } } \right) \#
$$

其中 $P ^ { 2 }$ 代表着射电源的功率， $\mathsf { \Pi } _ { \theta _ { a _ { c } , a _ { r _ { n } } } }$ 代表着RFI向量与射电源向量的夹角大小,在 $0 \sim 9 0 ^ { o }$ 范围内， $\theta _ { a _ { c } , a _ { r _ { n } } }$ 越大，最终投影得到的射电源功率越大。但是射电源子空间和干扰子空间之间的夹角难以测量，需要借助投影矩阵间接计算。

设投影矩阵为 $P$ ，它的特征值是0或1。特征值为0对应的特征向量生成投影核子空间，特征值为1对应的特征向量生成值域子空间。因此投影矩阵的秩等于它的值域子空间的维数。如果 $H$ 是投影范围子空间基， $K$ 是投影核子空间基，则有：

$$
\begin{array} { l } { \mathsf { P } \cdot \mathrm { H } = \mathrm { H } } \\ { \mathsf { P } \cdot \mathrm { K } = 0 \# ( 1 3 ) } \end{array}
$$

由基矩阵 $H$ 生成的投影矩阵定义为

$$
P = H ( H ^ { T } H ) ^ { - 1 } H ^ { T } \# ( 1 4 )
$$

其值域是正交于 $H$ 的子空间的正交投影为 $P ^ { \perp }$ ，定义为：

$$
P ^ { \perp } = I - H ( H ^ { T } H ) ^ { - 1 } H ^ { T } \# ( 1 5 )
$$

在多干扰的情况下，干扰子空间是多维的，这个子空间是由存储在矩阵 $A _ { r }$ 中的独立RFI向量集合生成的。因此，投影矩阵可表示为

$$
P _ { r } ^ { \perp } = I - A _ { r } ( A _ { r } ^ { T } A _ { r } ) ^ { - 1 } A _ { r } ^ { T } \# ( 1 6 )
$$

在预相关阶段，可用数据为天线阵列输出数据向量 $x ( t )$ ，将其投影到RFI子空间的正交空间上，修正后的数据向量 $x _ { c l e a n } ( t )$ 为

$$
x _ { c l e a n } ( t ) = P _ { r } { } ^ { \perp } x ( t ) \# ( 1 7 )
$$

从以上内容可知，空间滤波需要预先知道干扰源来源，以便确定投影矩阵，对于复杂的干扰环境，干扰源具体位置测定是非常困难的。

# 4RFI后相关阶段

由于RFI信号强度通常比天文信号大几个数量级，阈值法是一种有效抑制RFI的方法。阈值水平通常是根据统计量决定的，可以用一段数据的均值、均方根等作为阈值参考值，超出这个范围之外的值都标记为RFI。阈值法不足之处是会误将天文信号标记为RFI，在后相关阶段降低RFI检测的错误率是研究RFI抑制问题的一个重要方向。

# 4.1VarThreshold算法

在频域和时域上，RFI数据往往会影响相邻的数据，因为其强度比较低，往往不会被标记为RFI，增加了检测RFI的错误率。VarThreshold 是一种组合阈值算法，其思想是当组合样本的某一统计属性超过某个限制时，将标记样本的组合为 $\mathsf { R F I } ^ { [ 1 4 , 1 5 ] }$ 。假设A和B是相邻的样本采样点，常规阈值法是分别查看样本A和B是否超过设定的阈值水平线，如果超过，则标记为RFI。但对于组合阈值来说，只有样本A和 $B$ 都超过阈值，才可以将这一组合的样本都标记为RFI。如果样本A和 $B$ 没有被标记为RFI,它们将和下一个相邻的采样点 $C$ 进行组合，继续与阈值进行对比，迭代多次完成RFI标记，算法如公式(18)所示。

$$
\begin{array} { r } { f l a g \mathrm { { \bf ~ v } } _ { M } ( \mathrm { v } , t ) = \exists i \in \{ 0 , \dots M - 1 \} : \forall j \in \{ 0 , \dots M - 1 \} : \left| R \left( \mathrm { v } + a \Delta \mathrm { v } , t \right) \right| > \chi _ { M } \# \mathrm { { \bf ~ v } } _ { M } ( \mathrm { v } _ { M } , t ) . } \end{array}
$$

上式表达的是从 $t$ 时刻起， $M$ 个数的范围内，如果该范围内所有采样点的绝对值大于 $\cdot _ { \cdot \chi _ { M } }$ 那么将这 $M$ 个数都标记为RFI。

VarThreshold算法用一组严格递减的阈值序列 $\chi _ { i } ( i = 1 , \dots , N )$ 判定某个采样点是否应被标记为RFI，如公式（19）所示。

$$
\chi _ { i } = \frac { \chi _ { 1 } } { \rho ^ { l o g _ { 2 } i } } \# ( 1 \up9 .
$$

其中 $\chi _ { 1 }$ 是单采样点阈值，当 $\rho = 1 . 5$ 时效果最好， $\chi _ { 1 }$ 的取值是根据数据的统计水平量决定，即选取的阈值使RFI的假阳率最小。

# 4.2 SumThreshold算法

SumThreshold 算法也是一种组合阈值算法[14,15]，与 VarThreshold 算法求解阈值序列类似，只是p值不同，当 $\rho = 1 . 2$ 时效果最好，求出一组阈值 $T = \{ T _ { 1 } , T _ { 2 } , T _ { 4 } , \dots \}$ ，通过迭代的方式与样本进行比较，即 $T _ { 1 }$ 与单样本比较， $T _ { 2 }$ 与两个样本的均值比较， $T _ { m }$ 与 $m$ 个样本的均值比较，当样本均值大于阈值时，被标记为RFI，且不参与后续的迭代计算过程。以一维序列为例，设序列为{1,7,4,3,2,1,1,6,1,1,3,2,3,2}，x为 $\{ \chi _ { 1 } = 6 , \chi _ { 2 } = 3 , \chi _ { 4 } = 2 \}$ 。

![](images/88da1aba914fa512e3f743f6ef21a870029b96ad74f079e95c21fa8aed16c365.jpg)  
图7第一轮，阈值为 $\chi _ { 1 } = 6$ ，只有7被标记

Fig.7 In the first round,the threshold is $\chi _ { 1 } = 6$ and only 7 is marked

![](images/5a8c35bc272c5ea11b914d47d6fd915b6a19547a85f1dd47b583ebbd8ba3bc33.jpg)  
图8 第二轮，阈值为 $\chi _ { 2 } = 3$   
Fig.8 In the second round,the threshold value is $\chi _ { 2 } = 3$ （20

![](images/2c1a3431f43e1d16bb24789d3789515db34c21556275e4d838ff14744cb1331d.jpg)  
图9第三轮，阈值为 $\chi _ { 4 } = 2$   
Fig.9 In the third round,the threshold value is $\chi _ { 4 } = 2$

图7，图8和图9展示了SumThreshold 算法的过程。从算法角度考虑，该算法的时间复杂度为 $O ( n ^ { 2 } )$ 。为了减少计算速度，当阈值 $M$ 取1,2,4,8,16,32,64,128,256...时，时间复杂度降至0(nlogn)。

# 4.3奇异值分解

奇异值分解（SingularValue Decomposition，SVD）是线性代数中一种重要的矩阵分解，能够提取信息，简约数据，去除噪声等，可将数据映射到低维空间[16。SVD 可分解为

$$
\pmb { A } = \pmb { U } \pmb { \Sigma } \pmb { V } ^ { T } \# ( 2 0 )
$$

如公式(20)，SVD 将原始矩阵A分解为三个矩阵： $\pmb { U } , \pmb { \Sigma } , \pmb { V } ^ { T }$ ，其中 $\pmb { U } , \pmb { V }$ 是正交矩阵， $\pmb { \Sigma }$ 是对角矩阵，对角线上的元素为奇异值。绝大部分的RFI信号在时域或频域上的振幅较大。用A代表接受的天文信号，将其进行奇异值分解，即 $\pmb { A } = \pmb { U } \pmb { \Sigma } \pmb { V } ^ { T }$ ，将 $\pmb { \Sigma }$ 中最大特征值置为0,将其逆向恢复后，得到新的矩阵A，那么原矩阵A中幅值较大的信号（RFI）会被抑制。

当 RFI 信号足够强，且 $\sigma _ { R F I } \cdot \sigma _ { a s t r o } = 0$ 时，该算法效果最好，但该方法仅适用于宽带RFI信号，对于遵从高斯分布的RFI信号并不适用[14,15]。

# 5基于机器学习的RFI抑制方法

随着机器学习和深度学习等技术快速发展以及天文数据的急速增长，两者的结合已成必然趋势，通过对大量的数据进行学习和训练后，能有效地标记天文信号中的RFI，并进行特征提取。

# 5.1主成分分析法

主成分分析（PrincipalComponent Analysis，PCA）是一种用于数据特征降维的方法，常用于减少数据集的维数，同时保持数据集对方差贡献最大的特征。这样低阶成分往往能够保留数据的重要信息，方便特征提取和分类[17,18]。

文献[19]对生活中常见的九种瞬时RFI来源进行分类测试实验，在时域范围内分别使用标准 PCA 和核PCA进行测试。之后用一种聚类分离的方法比较了两种方法的聚类精度，如图10和图11，发现核PCA在区分来源方面比标准PCA更好，能有效区分瞬时RFI来源。

![](images/f9c95cff7bc8a12577dc12ad657e6357a85b46b808fc5519d6ff509aa7056185.jpg)  
Principal Components4,5and6   
Fig.10 Standard PCA

# Principal Components 4,5 and 6

![](images/92e6dafc1655a0718682622bc40f6028a4c8c8bd0e0bed800a9db59096d071bc.jpg)  
图10标准PCA（来源文献[18])  
图11核PCA（来源文献[18])  
Fig.11 Kernel PCA

# 5.2支持向量机

在机器学习中，支持向量机（SupportVectorMachine，SVM）是在分类与回归分析中分析数据的监督式学习模型与相关的学习算法[20]。

文献[21]选取时间长度为 $3 0 0 \mu s$ 非RFI和RFI信号训练，提取均方根、均值、方差、均值与方差之比、偏度、峰度、最大振幅、最小振幅和峰值个数等信息，导入SVM训练模型，之后对测试数据进行RFI和非RFI分类，流程如图12所示。结果表明即使在非常低 INR 和RFI占空比小的情况下，该方法仍能准确地检测出RFI，效果良好。

![](images/833150a627a8f110c8273e568b682288c1da94116081216d9dc5e8493c05a869.jpg)  
Fig.12 RFI suppression process based on SVM

# 5.3神经网络

神经网络的基本结构包含输入层、隐藏层和输出层，由大量的节点和之间相互连接构成，是一种非线性统计性数据建模工具，常用来对输入和输出间复杂的关系进行建模，或用来探索数据的模式[22]。

文献[23]提出了全卷积神经网络(Deep Full Convolutional Neural Network，DFCN，用于图像的分割，解决的核心问题是图像像素级别的分类。文献[24]利用DFCN，如图13， $H$ 和W分别对应输入的时间和频率可见性维数， $F$ 为滤波器层数，L对应输入和全卷积层之间的层数总和，以振幅和相位为特征，瀑布图进行特征提取，并标记出RFI。

![](images/f2078ac88183a0b77592d991bb36a8ae6d323bef8b12b9c2568d05211e632add.jpg)  
图12基于 SVM的RFI抑制过程  
图13DFCN架构(来源文献[23])

文献[25]提出的U-Net神经网络，是在卷积神经网络的基础上增加了上卷积的扩展路径，可以应对小样本的数据集进行较快、有效地图像分割，被用于医学细胞图像分割。文献[3]成功地应用了U-Net深度神经网络模型来识别单天线射电望远镜数据中的RFI，其结构如图14。

![](images/0387caea45a9a626ffa9e548930e7de8e68c1a68538d4142af25e5cecac52c6d.jpg)  
图14U-Net架构(来源文献[3])

文献[26]发现使用卷积神经网络(Convolutional Neural Networks,CNN)在对FAST数据进行标记RFI时，常常标记错误，需要进一步人工检查，带来了显著的额外工作量，为了克服这一问题，提出了一种称为RFI-Net 的神经网络模型如图15 所示,结果表明，RFI-Net 模型要优于 U-Net，KNN(K-nearest Neighbour)和 SumThreshold 算法。

循环神经网络(Recurrent Neural Network，RNN)是一类用于处理序列数据的神经网络，对处理上下文关联的语音[2数据有很好效果。天文信号也是一种时序数据，非常适和使用RNN 对其进行处理，Burd 等人利用RNN对射电望远镜干涉阵列数据进行RFI检测，根据巨米波射电望远镜(Giant Metrewave Radio Telescope,GMRT)的 610MHz 的 RFI振幅信息,区分RFI和非RFI数据[28]。

![](images/3bfa7e02319927c4aaf8dd26754430cdf3efd3283abd3553dcf67be482804405.jpg)  
Fig.14 U-Net architecture

# 6总结

本文系统阐述了射电天文中抑制和标记RFI 算法和技术，分析了在主动预防阶段、预相关阶段、后相关阶段RFI抑制方法的优势和不足。采用有效地屏蔽手段可以在主动预防阶段阻止大部分RFI进入系统；预相关阶段基于各个天线中的天文信号具有相关特性抑制RFI；在后相关阶段大部分算法基于阈值标记RFI。通过机器学习相关技术对RFI进行标记和识别是目前的研究热点，基于海量天文数据进行训练能够极大提高标记RFI的正确率，但不足是前期手动标记训练样本中RFI 和天文信号十分耗费时间，目前可用的训练样本有限。

RFI抑制问题需要在不同阶段采用多种方法协同解决，从射电望远镜台址周边的无线电环境保护到最终天文数据处理过程各个环节都需要考虑 RFI问题。各天文台站需要结合实际需求和所处环境的电磁干扰情况，合理选择RFI抑制方法。

致谢：感谢国家重点研发计划（2021YFC2203502）；国家自然科学基金（12173077,11873082,11803080,12003062）；新疆维吾尔自治区天山创新团队计划（2022D14020）；中国科学院青年创新促进会；国家重点研发计划(2018YFA0404704)；国家天文科学数据中心；中国科学院天文台站设备更新及重大仪器设备运行专项经费资助。本论文得到中国虚拟天文台、国家天文科学数据中心、中科院科学数据中心体系提供的数据资源和技术支持。

# 参考文献

[1]WangYu,ZagHa-YaHuoetal.atelitetigatiooATJ].eseahinstroodstropsis():

[2]Porko,Jukka-Pekka Goran.Radio frequency interference inradioastronomy[D],Aalto University,2011:77   
[3]J.Akeret,C.Chang,Aucchi,A.Refregie.Radiofrequencyinteferencetgationsingdeepovolutioaleraltoks[J]. Astronomy and Computing,2017(18):35-39.   
[4] 胡浩,张海燕,黄仕杰.FAST 电波环境保护措施[J].深空探测学报,2020,7(02):152-157. HU Hao，ZHANG Haiyan，HUANG Shijie.Protection Measuresof FAST Radio Environment[J].Jourmal of Deep Space Exploration,2020,7(02):152-157.   
[5] 王娜.新疆奇台110米射电望远镜[J].中国科学:物理学 力学 天学,2014,44(08):783-794. WANG Na. Xinjiang Qitai $1 1 0 \mathrm { ~ m ~ }$ radio telescope[J].SCIENTIA SINICA Physica,Mechanica & Astronomica,2O14,44(08): 783-794.   
[6]刘晔.QTT台站限制区域电磁干扰影响分析[C].中国天文学会 2018年学术年会. LIU Ye.Analysisof electromagnetic interferenceimpact intherestrictedareaofQTTstations[C].Chinese AstronomicalSociety 2018Annual Academic Conference.   
[7]刘晔,刘奇.大口径射电望远镜台址电磁干扰预测方法[J].中国科学:物理学 力学 天文学,2019,49(09):121-129. LIU Ye,LIU Qi.Apredictionmethodfor electromagnetic interferenceof large apertureradio telescope.[J].SCIENTIA INICA Physica,Mechanica & Astronomica,2019,49(09):121-129.   
[8]CeciliaBarbaumandRichardFBradleyANewApproachtoInterferenceExcisioninRadioAstronomy:Real-TimeAdaptive Cancellation [J].The Astronomical Journal,1998(116):2598-2614.   
[9]Kesteven,M.andHobbs,G.andlement,R.andDawson,BndManchester,R.andUppal,T.Adativefilersrevisited:dio frequency interference mitigation in pulsar observations[J]. Radio Science,2005(40).   
[10]Curottoolaodreaigplemtaticteriofdiucefereedita using a field-programmable gate array[D]. Universidad de Chile,2019.   
[1]RazaJostraAJVadVeAJSpatialileingofintefereeiastrooJ].IEEialroceige, 2002,9(2): 64-67.   
[12]Hellbourg G.RadioFrequencyInterference spatialprocesing for moderradio telescopes[D]. Universite dOrleans,2014.   
[13]KoczJ,BriggsFReyoldsJ.Spatialfilteringusingamultibeamreceiver[CProceedingsofRFMitigation Wrksopo (RFI2010) proceedings.2010,1: 32.   
[14]Ofringa,A.R,rA.G,iehl,.etl.ooeladrecitefreasicatietdsly Notices of the Royal Astronomical Society,2010(405):155-167.   
[15] Ofringa AR.Algorithms for radio interference detection and removal[D]. University of Groningen, 2012.   
[16]GuoQ,ZhangC,ZhangY,etal.AnefcientSD-basedmethodforimagedenoising[J].IEEtransactionsoCiruitsadSyte for Video Technology,2015,26(5): 868-880.   
[17]AbdiH,WiliamsLJ.Principalcomponentanalysis[J].Wileyinterdisciplinaryeviews:omputationalstatistics(4): 433-459.   
[18] KherifF,Latypova A.Principal component analysis[M]//MachineLearning. Academic Press,2O2o: 209-225.   
[19]CzechDaniel,ishaitumar,ggscael.medoaiasificatiooftrasientaiofreuecyteferee.16 IEEE Intermational Geoscience and Remote Sensing Symposium (IGARSS),2016:302-305.   
[20]Pisner DA,SchnyerDM.Support vector machine[M]/Machine Learming.Academic Press,2020:101-121.   
[21]NazarIM,AksoyM.RadioFrequencyInterference DetectioninMicrowaveRadiometryUsing Support VectorMachines[J].URSI GASS,2020.   
[22]Aggarwal CC.Neural networksand deep learning[J]. Springer,2018,10:978-3.   
[23]LongJ,hemerEaellTFullyvouioaeosfmaticmtaCroeingftheEEec computer vision and pattern recognition. 2015: 3431-3440.   
[24]KerriganJ,PantePL,KohnS,etal.OptimizingsparseRFpredictionusingdeepleaing[J].MonthlyNoticesoftheRoal Astronomical Society,2019,488(2): 2605-2615.   
[25]RonebererOscherProx.Uet:ConvolutioalwrksforiomedicalimagesgmetatioCteatioalCofece on Medical image computing and computer-assisted intervention. Springer, Cham,2015: 234-241.   
[26]Yang Z,YuC,XiaoJ,etal.DeepresidualdetectionofradiofrequenyinterferenceforFAS[J].onthlyoticsofteoyal Astronomical Society,2020,492(1):1421-1431.   
[27]Zaremba W,SutskeverI VinyalsO.Recurent neuralnetworkregularization[J].arXivpreprintarXiv:1409.2329,2014.   
[28]BurdPR,aK,MarT,etal.Detectingradiofreuecyitefereceindianteaaswitecurrtal network algorithm[J].Astronomische Nachrichten,2018,339(5): 358-362.

# Application of RFl Mitigation Technology in Radio

# Astronomy

Zhang Hailong1,234， Zhang Yazhou1²2，Wang Jie14， Ye Xinchen14， Wang Wanqiong'，Li Jia',Zhang Meng1², Du Xu1.2

(1Xinjiang AstronomicalObseratory,ChineseAcademyofSciences,Urumqi83ool1,China;2UniversityofChineseAcademyof

Sciences,BeijingOo49,China;3KeyLaboratoryofadioAstronomy,ChineseAcademyofSiences,NanjingCina;4

Abstract: Aiming at the problem of radio frequency interference (RFI) in the process of radio astronomy observation, the RFI mitigation strategies of domestic and foreign stations are analyzed in detail. According to the RFI problems encountered in the actual observation process of each observatory,the prevention strategies and mitigation methods of RFI were studied from the aspects of active prevention stage， pre-correlation stage， post-correlation stage， machine learning and deep learning. The methods that can be adopted in the active prevention stage, adaptive filtering in thepre-correlation stage， spatial filtering method, VarThreshold, SumThreshold and singular value decomposition in the post correlation stage are systematically analyzed. The applications of principal component analysis based on machine learning,support vector machine,full convolution neural network, convolution neural network,u-net and other related technologies and methods in RFI signal processing are discussed.

Key words: RFI; filtering; thresholding; machine learning

Aiming at the problem of radio frequency interference (RFI) in the process of radio astronomy observation, the RFI mitigation strategies of domestic and foreign stations are analyzed in detail. According to the RFI problems encountered in the actual observation process of each observatory， the prevention strategies and mitagation methods of RFI were studied from the aspects of active prevention stage, pre-correlation stage, post-correlation stage, machine learning and deep learning. The methods that can be adopted in the active prevention stage,adaptive filtering in the pre-correlation stage，spatial filtering method, VarThreshold, SumThreshold and singular value decomposition in the post correlation stage are systematically analyzed. The applications of principal component analysis based on machine learning, support vector machine, full convolution neural network,convolution neural network,u-net and other related technologies and methods in RFI signal processing are discussed.