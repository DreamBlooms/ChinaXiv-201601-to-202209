# 多层变耦合星型网络同步性研究

李晓霞ab†，李艳雨ab，冯志新ab，张启宇ab(河北工业大学a.省部共建电工装备可靠性与智能化国家重点实验室；b.河北省电磁场与电器可靠性重点实验室，天津 300130)

摘要：多层网络的同步性研究是网络科学研究中一个重要的课题，其中网络的层内耦合强度或为固定，或为可变。针对多层变耦合星型网络的同步性进行了研究：在层内耦合强度总值一定的前提下，令网络中部分耦合强度分别按照正比例函数、反比例函数、指数函数、对数函数以及三角函数等规律变化，然后严格推导多层变耦合星型网络的超拉普拉斯矩阵及其特征值谱，依据主稳定函数法，研究网络同步能力。数值仿真结果表明：当网络中部分耦合强度发生变化时，其余耦合强度随之以相反的趋势变化；在某些变化规律下，可能出现不同区间内网络同步能力的变化趋势不同的情况；另外，同步域有界时网络同步能力可能达到极大的值。综合分析可以得出结论：网络同步能力的变化趋势始终与较小的耦合强度的变化趋势相同；且同步域有界时更容易实现网络同步。

关键词：多层网络；同步能力；时变耦合 中图分类号：TP393.02 doi:10.19734/j.issn.1001-3695.2018.12.0837

Research on synchronizability of multilayer star network with time-varying coupling strength.

Li Xiaoxiaa,bt,Li Yanyu a,b, Feng Zhixin a.b, Zhang Qiyu a,b (a.StateKeyLaboratoryofReliability&IntelligenceofElectricalEquipment,b.KeyLaboratoryofElectromagneticField &Electrical Apparatus ReliabilityofHebei Province,Hebei UniversityofTechnology,Tianjin30ol30,China)

Abstract:This paper studied the multilayer star network synchronizationwith variablecoupling strength.First,from the premisethatthesumofthe intralayercoupling strength inthe network isconstant,partofthecoupling strength are made to varyrespectively according to theruleof different functions,then the Supra-Laplace matrix andits eigenvalue spectrumof multilayer star networkarestrictlyderived.Finaly,thenetwork synchronizabilityisresearchedonthe basisofthemain stability method.Theresults showthat whenpartofthecoupling strengthvary,the othercoupling strength willvary ina opposite trend.Besides,the network synchronizability may bevery large when the synchronous domain is bounded.The conclusionis that thetrendof thesynchronizabilityisalways thesame as thetrendof the smalercoupling strength in the multilayer star network,and it is easier forthe multilayer star network tobesynchronous when the synchronous domain is bounded.

Key words:multilayer network; synchronizability; variable coupling strength

# 0 引言

复杂网络是近年来较为热门的研究课题[1\~5]。多个网络之间可能存在相互联系、相互作用，从而形成多层复杂网络，更能精确、全面地描述现实社会中复杂系统的形态、作用和发展趋势。目前，多层网络已经在运输[6,7]、社交[8]、经济[9]等诸多方面广为应用。故而近年来对复杂网络的研究逐渐向多层网络拓展，已经在拓扑结构[10,II]、动态网络模型[12\~17]和鲁棒性[18\~20]等方面取得了较大研究成果。

同步是自然界中一种常见的现象，如萤火虫闪烁同步[21].掌声同步[22]、路由器同步[23]等。在现实生活中，同步有时是有益的，有时却是有害的[24]。为了利用有益的同步造福人类同时避免有害同步，需要不断对同步问题进行深入研究。随着多层网络研究的发展，对多层网络同步性的研究已取得了一定的成果。Alberto等人[25]探讨了层间连接模式对多层随机网络同步性能的影响，发现层间连接模式中某些对称性的存在往往会降低整个网络的同步能力。Li等人[26]研究了由两个链路相连的网络组成的双工网络的同步性，发现连接度高的节点更有利于实现双工网络同步。徐明明等人[27,28]采用主稳定函数法深入研究了两层网络的同步性问题，讨论了不同耦合方式和网络结构参数对网络同步能力的影响，并分析了网络的层内和层间耦合强度分别较弱时，如何使网络更好的实现同步的问题。孙娟等人[29]进一步研究了三层以及多层星型网络的特征值谱及同步性，讨论了网络耦合强度、层数、节点数等因素对网络同步能力的影响。

其实，现实中许多复杂问题可以抽象、简化为多层网络问题。例如，为了统筹考虑线上社交网络和线下社交网络在舆情传播中的作用，沈乾等人[30首次提出了一种包含“媒体层一线上层一线下层”的多层同步网络模型，通过案例仿真分析线上网络与线下网络之间的相互影响及其对舆论传播的作用；李延龙等人[31将稀疏突触的复杂神经网络抽象为多层网络，进而研究其同步中耦合参数的临界特征。随着科学研究的日益深入，多层网络原理将会应用到越来越多的实际问题当中去。

众所周知，神经网络中神经元之间通过突触连接。最近，Jungenitz等人研究发现：在神经网络中，重复的电刺激可以通过扩大树突棘来加强突触，然而，这个过程中棘的整体大小和数量没有改变，也就是说，当刺激加强了一组突触，并且它们的树突棘扩大时，没有同时被刺激的另一组突触变弱，它们的树突棘收缩[32]。类似的情形如路由器分配宽带问题，当某些终端占用较多宽带时，其他终端占用的宽带就会随之减少。基于此，本文研究多层变耦合星型网络的同步性：在层内耦合强度总值一定的前提下，令网络中部分耦合强度分别按正比例函数、反比例函数、指数函数、对数函数以及余弦函数的规律变化（其余耦合强度随之改变），然后严格推导多层变耦合星型网络的超拉普拉斯矩阵及其特征值谱，依据主稳定函数法，研究网络同步能力。通过数值仿真结果，观察不同变化规律下网络同步能力的发展趋势，进而分析总结出一般性结论。

# 1 基础理论

$M$ 层网络中第 $K$ 层第 $i$ 个节点的动力学方程为

$$
\frac { d \mathbf { \Phi } _ { X _ { i } ^ { K } } ^ { K } } { d t } = f ( \mathbf { \Phi } _ { X _ { i } ^ { K } } ^ { K } ) + a ^ { K } \sum _ { i = 1 } ^ { N } w _ { i j } ^ { K } ( \mathbf { \Phi } _ { X _ { j } ^ { K } } - \mathbf { \Phi } _ { X _ { i } ^ { K } } ^ { K } ) \mathbf { \Phi } + \sum _ { H = 1 } ^ { M } d _ { i } ^ { K H } ( \mathbf { \Phi } _ { X _ { i } } ^ { H } - \mathbf { \Phi } _ { X _ { i } } ^ { K } )
$$

其中： $1 \leq i \leq N$ ， $1 \leq K \leq M$ ； $\boldsymbol { x } _ { i } ^ { K } \in \boldsymbol { R } ^ { N }$ 是第 $K$ 层第 $i$ 个节点的状态变量； $f ( \cdot )$ ： $R ^ { N } \to R ^ { N }$ 是一个动力学函数； $a ^ { \kappa }$ 为第 $K$ 层的层内耦合强度； $\boldsymbol { W } ^ { K } = ( \boldsymbol { w } _ { i j } ^ { K } ) \in \boldsymbol { R } ^ { N \times N }$ 为第 $K$ 层的耦合矩阵，若节点$i$ 与节点 $j ~ ( i \neq j )$ 相 $w _ { i j } ^ { K } = 1$ 连，则；反之 $w _ { i j } ^ { K } = 0$ ；且满足：w=-∑w；(x-x）表示第K层各节点状态变量的层内耦合函数； $\mathbf { \Delta } _ { d _ { i } } \mathbf { \Lambda } _ { } ^ { K H }$ 为第 $K$ 层与第 $H$ 层的第 $i$ 个节点的层间耦合强度； $( x _ { i } ^ { H } - x _ { i } ^ { K } )$ 表示第 $i$ 个节点状态变量的层间耦合函数。

需要指出，网络属于哪种类型是由网络上各节点的具体动力学行为 $f ( \cdot )$ 和节点间具体的耦合方式决定的。在分析网络同步能力的时候，可以将网络结构对同步的影响（即外耦合矩阵对同步的影响）和具体动力学行为及节点间具体耦合方式对同步的影响分离出来。也就是说，描述网络结构同步能力可以只考虑外耦合矩阵。外耦合矩阵可以采用多种不同的表达形式，本文选用拉普拉斯矩阵。

对于一个每层节点数都为 $N$ 的 $M$ 层星型网络模型：a)用 $\boldsymbol { W } ^ { K } \in \boldsymbol { R } ^ { N \times N }$ 表示第 $K$ 层的层内连接强度矩阵，用 $\boldsymbol { S } ^ { K } \in \boldsymbol { R } ^ { N \times N }$ 表示层内点强度矩阵（对角矩阵），则第 $K$ 层的层内拉普拉斯矩阵表示为 $\boldsymbol { L } ^ { K } = \boldsymbol { S } ^ { K } - \boldsymbol { W } ^ { K }$ ；b）假设每层网络的网络结构都相同，且只有层间对应节点相连。那么，用 $\boldsymbol { W } ^ { I } \in \boldsymbol { R } ^ { N \times N }$ 表示每两层网络的层间连接强度矩阵， $\boldsymbol { S } ^ { I } \in \boldsymbol { R } ^ { N \times N }$ 表示每两层网络的层间点强度矩阵（对角矩阵），则每两层网络的层间拉普拉斯矩阵为 $\boldsymbol { L } ^ { \prime } = \boldsymbol { S } ^ { I } - \boldsymbol { W } ^ { I }$ 。

整个网络的超拉普拉斯矩阵 $\Lambda = \Lambda ^ { L } + \Lambda ^ { I }$ ,其中 ${ \boldsymbol { \Lambda } } ^ { L }$ 为层内超拉普拉斯矩阵， ${ \boldsymbol { \Lambda } } ^ { I }$ 为层间超拉普拉斯矩阵；层内超拉普拉斯矩阵为

$$
\Lambda ^ { L } = \left( \begin{array} { l l l l } { L ^ { 1 } } & { 0 } & { \cdots } & { 0 } \\ { 0 } & { L ^ { 2 } } & { \cdots } & { 0 } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { 0 } & { 0 } & { \cdots } & { L ^ { M } } \end{array} \right) = \bigoplus _ { K = 1 } ^ { M } L ^ { K }
$$

层间超拉普拉斯矩阵为

$$
\Lambda ^ { I } = L ^ { I } \otimes I
$$

值谱。根据主稳定函数法，模型的同步能力可以用∧的最小非零特征值λ和最大特征值 $\lambda _ { \mathrm { m a x } }$ 来判断[28]-[30]：当同步区域无界时，越大，网络同步能力越强；当同步区域有界时，$\lambda _ { \operatorname* { m a x } } / \lambda _ { 2 }$ 的值越小，网络同步能力越强。

# 2 同步性研究

# 2.1 网络结构模型

构建 $M$ 层变耦合星型网络模型，每层网络共有 $N$ 个节点，且每层网络的网络结构和耦合方式都相同。图1（a）为网络层内耦合结构图，叶子节点向中心节点单向耦合，同一层内叶子节点间相互无耦合；假设初始时刻网络层内耦合强度为$a$ 且耦合强度总值一定，为 $( N - 1 ) a$ ，某时刻其中 $\mathbf { \nabla } _ { m }$ 个耦合强度变为 $\varepsilon a$ ，则其余 $N - m - 1$ 个耦合强度变为 为N-εm-la，为方便后续工作，将 $\frac { N - \varepsilon m - 1 } { N - m - 1 }$ 记作0。图1（b）为网络层间耦合结构图，每两层网络的对应节点耦合连接，耦合强度为 $d$ 不对应节点间无耦合。

其中： $\otimes$ 为Kronecker乘积, $I$ 是一个 $M \times N$ 的单位矩阵。

求解网络模型的超拉普拉斯矩阵（外耦合矩阵）的特征

(b)网络层间耦合结构,红色虚线表示中心节点的层间耦合,黑色虚线 表示对应叶子节点的层间耦合 (b)Inter-layer coupling structure,the red dotted lines represent the coupling strength between corresponded hub nodes,the black dotted   
lines represent the coupling strength between the corresponded leaf nodes

![](images/aaf18b168eeca91f52c9c7d3d437b860d12f448fc1136eea00c35d84aec3f306.jpg)  
图1网络模型耦合结构图

（红色节点为中心节点，黑色节点为叶子节点)

Fig.1Coupling structure of the network (the hub nodes are red and the leaf nodes are black)

# 2.2同步能力

根据前述理论知识，写出图1网络模型的层内拉普拉斯矩阵为

$$
\begin{array} { r } { \left( \begin{array} { c c c c c c c } { ( N - 1 ) a + ( M - 1 ) d } & { 0 } & { \ldots } & { L ^ { K } = } & { \ldots } & { \ldots } & { 0 } \\ { - \varepsilon a } & { \varepsilon a + ( M - 1 ) d } & { \ldots } & { \ldots } & { \ldots } & { \vdots } \\ { \vdots } & { \ddots } & { \ddots } & & & { \vdots } \\ { - \varepsilon a } & & & { \varepsilon a + ( M - 1 ) d } & & & { \vdots } \\ { - \theta a } & & & & { \theta a + ( M - 1 ) d } & { \vdots } \\ { \vdots } & & & & & { \ddots } & { 0 } \\ { - \theta a } & & & & { \ldots } & { \ldots } & { 0 } \end{array} \right) } \end{array}
$$

层间拉普拉斯矩阵为

$$
L ^ { I } = \left( \begin{array} { l l l l } { { - d } } & { { 0 } } & { { \cdots } } & { { 0 } } \\ { { 0 } } & { { \ddots } } & { { } } & { { \vdots } } \\ { { \vdots } } & { { } } & { { \ddots } } & { { 0 } } \\ { { 0 } } & { { \cdots } } & { { 0 } } & { { - d } } \end{array} \right)
$$

将式(4)(5)代入到式(2)(3)中，分别得到层内和层间超拉普拉斯矩阵，进而写出整个网络模型的超拉普拉斯矩阵并求其特征值。然后利用公式 ${ \left| \begin{array} { l l l l } { A } & { B } & { \cdots } & { B } \\ { B } & { A } & { \cdots } & { B } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { B } & { B } & { \cdots } & { A } \end{array} \right| } \quad = \left| A - B \right| ^ { M - 1 } \left| A + ( M - 1 ) B \right|$ 推导出矩阵的所有特征值分别为0,aεa， $\begin{array} { r } { , \underbrace { \varepsilon a \cdots \varepsilon a } _ { m } , \underbrace { \theta a \cdots \theta a } _ { N - m - 1 } , \underbrace { M d \cdots M d } _ { M - 1 } } \end{array}$ εa+Md-.ga+Md，0a+ Md.a+Md，假设 Md>εa，Md> 0a,则最小非零特征值 $\lambda _ { 2 } = \operatorname* { m i n } \{ \varepsilon a , \theta a \}$ ，最大特征值$\lambda _ { \mathrm { m a x } } = { \bf \mathrm { m a x } } \left( { \varepsilon { a } + { M d } , { \theta } { a } + { M d } } \right) , r = \frac { { \operatorname* { m a x } } \left( { \varepsilon { a } + { M d } , { \theta } { a } + { M d } } \right) } { { \operatorname* { m i n } } \left( { \varepsilon { a } , \theta { a } } \right) }$ 由此可得同步域有界和无界两种情况下网络的同步能力。

为研究网络时变耦合下的同步能力，令部分耦合强度分别按照正比例函数、反比例函数、指数函数、对数函数以及余弦函数的规律变化，这里取 $\scriptstyle { \varepsilon _ { 1 } = t }$ ， $\ \varepsilon _ { 2 } = \frac { 1 } { t }$ ， $\smash { \varepsilon _ { 3 } = 0 . 9 ^ { \prime } }$ ， $\varepsilon _ { 4 } = \log _ { 1 0 } t$ ，$\varepsilon _ { 5 } = \cos t + 1 . 5$ 0

# 2.3数值仿真

利用MATLAB进行数值仿真，取 $N = 2 0 0$ ， $M = 2 0$ ， $m = 7 0$ ，$\scriptstyle a = d = 1$ ，仿真结果如下：

取 $\varepsilon _ { 1 } = t$ ，对网络层内耦合强度及同步能力进行仿真如图2 所示。由图2(a)可以看出，在(0,2.84)时间段内， $\scriptstyle { \varepsilon _ { 1 } }$ 线性增大，而 $\theta _ { 1 }$ 则线性减小，即部分耦合强度增大，其余耦合强度减小。在(0,1)时间段内，ε1<θ，则=ε1，r=a+Md。 。由图2(b)(c)可知 $\lambda _ { 2 }$ 随时间增大， $\boldsymbol { r }$ 随时间减小，即网络同步能力随时间增强；在(1,2.84)时间段内， $\varepsilon _ { 1 } > \theta _ { 1 }$ ，则 $\lambda _ { 2 } = \theta _ { 1 }$ ，$r = \frac { \varepsilon _ { 1 } a + M d } { \theta _ { 1 } a }$ 。由图2(b)(c)可知 $\lambda _ { 2 }$ 随时间减小， $\boldsymbol { r }$ 随时间增大，即网络同步能力随时间减弱。

取 $\varepsilon _ { 2 } = \frac { 1 } { t }$ ，对网络层内耦合强度及同步能力进行仿真如图3所示。由图3(a)可以看出， $\scriptstyle { \varepsilon _ { 2 } }$ 非线性减小，而 $\theta _ { 2 }$ 则非线性增大，即部分耦合强度减小，其余耦合强度增大。在(0.35,1)时间段内，ε²>θ，则=，r=εα+Md。 。由图3(b)(c)可知$\lambda _ { 2 }$ 随时间增大， $\boldsymbol { r }$ 随时间减小，即网络同步能力随时间增强;在（1, $\infty$ ）时间段内， $\varepsilon _ { 2 } < \theta _ { 2 }$ ，则 $\lambda _ { 2 } = \varepsilon _ { 2 }$ ， $r = \frac { \theta _ { 2 } a + M d } { \varepsilon _ { 2 } a }$ 。由图3(b)(c)可知 $\lambda _ { 2 }$ 随时间减小， $\boldsymbol { r }$ 随时间增大，即网络同步能力随时间减弱。

![](images/6917a75c10f31d274ab20f5abb9fb0cddaece63d2eeac7e988ee46ce756d71f3.jpg)  
Fig.2Graph of the synchronizability when thecoupling strength vary according to therule ofproportional function

![](images/247b2d78026f134d9ce577ac35b7fcb1b33a18aa3097d08ed77e12e4727ede28.jpg)  
图2耦合强度按正比例函数变化时网络同步能力  
图3耦合强度按反比例函数变化时网络同步能力

Fig.3Graph of the synchronizability when the coupling strength vary according to the rule ofinverse function

取 $\mathbf { \varepsilon } _ { \mathcal { E } 3 } = 0 . 9 ^ { t }$ ，对网络层内耦合强度及同步能力进行仿真如图4所示。由图 4(a)可以看出， $\varepsilon _ { 3 }$ 非线性减小，而 $\theta _ { 3 }$ 则非线性增大，即部分耦合强度减小，其余耦合强度增大，始终都有ε3<0，则λ3=ε3，r=θa+Md 。由图4(b)(c)可知 $\lambda _ { 2 }$ 随时间减小， $\boldsymbol { r }$ 随时间增大，即网络同步能力随时间减弱。

取 $\varepsilon _ { 4 } = \log _ { 1 0 } t$ ，对网络层内耦合强度及同步能力进行仿真如图5所示。由图5（a）可以看出， $\scriptstyle { \varepsilon _ { 4 } }$ 线性增大，而 $\theta _ { 4 }$ 则线性减小，即部分耦合强度增大，其余耦合强度减小。在（1，10）时间段内， $\varepsilon _ { 4 } < \theta _ { 4 }$ ，则 $\lambda _ { 2 } = \varepsilon _ { 4 }$ ， $r = \frac { \theta _ { 4 } a + M d } { \varepsilon _ { 4 } a }$ 。由图5（b）（c）可知 $\lambda _ { 2 }$ 随时间增大， $\boldsymbol { r }$ 随时间减小，即网络同步能力随时间增强。在(10,）时间段内，ε4>θ4,则λ=04,r=εα+Md由图5(b)(c)可知 $\lambda _ { 2 }$ 随时间减小， $\boldsymbol { r }$ 随时间增大，即网络同步能力随时间减弱。

![](images/90e46fb9708c039b1b7c92aa8023dacda126c1fca9aa6272d3a9f8dc3ddce9dd.jpg)  
Fig.4Graphof the synchronizability whenthecoupling strengthvaryaccording to theruleofexponential function

![](images/f5ae02cde1e6826af5e37f2fa5514afe9255aeff53c14ea75f1496fbbb68e58e.jpg)  
图4耦合强度按指数函数变化时网络同步能力  
图5耦合强度按对数函数变化时网络同步能力  
Fig.5Graph of the synchronizability when thecoupling strength varyaccording to the ruleoflogarithmic function

取 $\varepsilon _ { 5 } = \cos t + 1 . 5$ ，在 $( 0 , 4 \pi )$ 时间段内对网络层内耦合强度及同步能力进行仿真如图6所示。以一个周期内的图像进行分析。在 $( 0 , \frac { 2 \pi } { 3 } )$ 时间段内，由图6(a)可以看出， $\scriptstyle { \varepsilon } _ { 5 }$ 减小而 $\theta _ { 5 }$ 增大，此时ε5>θs，则𝜆2=05，r=εa+Md ；由图6(b)(c)可知 $\lambda _ { 2 }$ 随时间增大， $\boldsymbol { r }$ 随时间减小，即网络同步能力随时间增强；在 $( { \frac { 2 \pi } { 3 } } , { \frac { 4 \pi } { 3 } } )$ 时间段内，由图6(a)可以看出， $\scriptstyle { \varepsilon _ { 5 } }$ 先减小后增大而θ5先增大减小，此时εs<θ5，则=εs，r=a+Md 。由图6(b)(c)可知 $\lambda _ { 2 }$ 随时间先减小后增大， $\boldsymbol { r }$ 随时间先增大后减小，即网络同步能力随时间先减弱后增强；在 $( { \frac { 4 \pi } { 3 } } , 2 \pi )$ 时间段内，εs增大而θ5减小，此时εs>0s，则=θs，r=εΩ+Md由图6(b)(c)可知 $\lambda _ { 2 }$ 随时间减小， $\boldsymbol { r }$ 随时间增大，即网络同步能力随时间减弱。

# 3 结束语

本文主要研究了多层变耦合星型网络的同步性。若每层网络层内耦合强度总值一定，当部分耦合强度分别按照正比例函数、反比例函数、指数函数、对数函数以及三角函数的规律变化时，依据主稳定函数法，研究网络同步能力的变化趋势。最后得出结论：当部分耦合强度变化时，其余耦合强度随之以相反的趋势变化；在某些变化规律下，可能出现耦合强度交替变小的情况，导致不同区间内网络同步能力的变化趋势不同；但综合分析发现，不论耦合强度以何种规律变化，不论同步域有界还是无界，网络同步能力的变化趋势始终与较小的耦合强度的变化趋势相同；然而，同步域无界时网络的同步能力普遍较小，同步域有界时网络同步能力在某些时候却可以达到极大的数值，由此可知，同步域有界时，

![](images/9d60b35e0858c34f6417d4ff10596fe6d0017c19cb0a81b6269f117cda4fcd38.jpg)  
图6耦合强度按三角函数变化时网络同步能力 ig.6Graph of the synchronizability when the coupling strength vary according to the rule of trigonometric function

# 参考文献：

[1]Cai Shuiming,Zhou Peipei,Liu Zengrong. Synchronization analysis of directed complex networks with time-delayed dynamical nodes and impulsive effects[J].Nonlinear Dynamics,2014,76(3):1677-1691.   
[2]Boccaletti S,Latora V,Moreno Y,et al.Complex networks: Structure and dynamics [J].Physics Reports,2006,424(4):175-308.   
[3]He Ping,Jing Chunguo,Fan Tao,et al.Robust decentralized adaptive synchronization of general complex networks with coupling delayed and uncertainties [J].Complexity,2014,19(3):10-26.   
[4]Zhang Qunjiao,Zhao Junchan．Projective and lag synchronization between general complex networks via impulsive control[J].Nonlinear

#

Dynamics,2012,67(4):253-264.   
[5]Lu L,Li C,Wang Wenjun,et al. Study on spatiotemporal chaos synchronization among complex networks with diverse structures [J]. Nonlinear Dynamics,2014,77(1-2): 1-7.   
[6] Cardillo A， Zanin M,Gómez-Gardeies J，et al.Modeling the multi-layer nature of the European Air Transport Network: Resilience and passengers re-scheduling under random failures[J]. European Physical Journal Special Topics,2013,215 (1): 23-33.   
[7] Kaluza P,Kolzsch A,Gastner M T,et al. The complex network of global cargo ship movements[J]. Journal of the Royal Society Interface, 2010,7(48): 1093-1103.   
[8] Szell M,Lambiotte R,Thurner S.Multirelational organization of large-scale social networks in an online world [J]. Proceedings of National Academy of Sciences of the United States of America,2010, 107 (31): 13636-13641.   
[9]Zhang Xin,Shao Shuai,Stanley H E,et al. Dynamic motifs in socio-economic networks [J].Europhysics Letters,2014,108(5):1-9.   
[10] Cardillo A, Zanin M,Romance M,et al. Emergence of network features from multiplexity[J]. Scientific Reports,2012,3(2):1-6.   
[11] Gao J,Buldyrev S V,Stanley H E,et al. Networks formed from interdependent networks [J].Nature Physics,2012,8(1): 40-48.   
[12] Dickison M,Havlin S,Stanley H E,Epidemics on interconnected networks [J]. Physical Review E,2012,85(6): 1-7.   
[13] Gómez-Gardenes J，Reinares I，Arenas A，et al.Evolution of cooperation in multiplex networks [J]. Scientific Reports,2012,620 (2): 1-6.   
[14] Santos M D,Dorogovtsev S N,Mendes JFF.Biased imitation in coupled evolutionary games in interdependent networks[J]. Scientific Reports,2014, 4(4): 1-12.   
[15] Wang Zhen, Wang Lin,Perc M. Degree mixing in multilayer networks impedes the evolution of cooperation [J].Physical Review E Statistical Nonlinear & Soft Matter Physics,2014,89(5):1-9.   
[16] Li Fangfei,Lu Xiwen. Complete synchronization of temporal Boolean networks [J]. Neural Networks,2013,44(8): 72-77.   
[17] Aguirre J, Sevilla-Escoboza R,Gutiérrez R,et al. Synchronization of interconnected networks:the role of connector nodes [J].Physical Review Letters,2014,112(24): 1-8.   
[18] Huang Xuqing,Gao Jianxi， Buldyrev S V,et al. Robustness of interdependent networks under targeted attack [J]. Physical Review E, 2011,83 (6): 1-6.   
[19] Hu Yanqing，Zhou Dong，Zhang Rui，et al.Percolation of interdependent networks with inter-similarity.[J].Physical Review E Statistical Nonlinear & Soft Matter Physics,2013,88 (5): 448-4498.   
[20] Hu Yanqing,Ksherim B,Cohen R,et al.Percolation in interdependent and interconnected networks: abrupt change from second to first order transition [J].Physical Review E,2011,84 (6): 1-11.   
[21] Buek J,Buek E.Mechanism of rhythmic synchronous flashing of fireflies [J]. Science,1968,159 (3821): 1319-1327.   
[22] Néda Z,Ravasz E,Brechet Y,et al. The sound of many hands clapping [J].Nature,2000,403 (6772): 849-850.   
[23] Floyd S,Jacobson V. The synchronization of periodic routing messages [J]. ACM Trans on Networking,1994,2 (2): 122-136.   
[24]任红卫，邓飞其．随机复杂网络同步控制研究进展综述[J].控制理 论与应用，2017,34(10):1261-1274.(Ren Hongwei,Deng Feiqi. Review on synchronization control in stochastic complex networks [J]. Control Theory& Applications,2017,34(10): 1261-1274.)   
[25]Alberto S.Symmetries and synchronization in multilayer random networks [J].Physical Review.E,2018,97(4):1-11.   
[26]Li Yang,Wu Xiaoqun,Lu Jun'an,et al.Synchronizability of duplex networks [J].IEEE Trans on Circuits and Systems,2016,63(2): 206-210.   
[27] Xu Mingming,Zhou Jin,Lu Jun'an,et al. Synchronizability of two-layer networks [J]. The European Physical Journal B,2015,88 (240): 1-6.   
[28]徐明明，陆君安，周进．两层星型网络的特征值谱及同步能力[J]. 物理学报，2016,65(2):1-13.(Xu Mingming,Lu Jun-an,Zhou Jin. Synchronizability and eigenvalues of two-layer star networks [J].Acta Phys.Sin,2016,65(2):1-13.)   
[29]孙娟，李晓霞，张金浩等．多层单向耦合星型网络的特征值谱及同 步能力分析[J].物理学报,2017,66(18):1-14.(Sun Juan,Li Xiaoxia, Zhang Jinhao,et al.Synchronizability and eigenvalues of multilayer star networks through unidirectionally coupling [J].Acta Phys. Sin,

# 2017,66(18): 1-14.)

[30]沈乾，刘怡君．多层同步网络在舆情仿真研究中的应用[J]．系统工 程理论与实践,2017,39(1):182-190.(Shen Qian,Liu Yijun.Public opinion simulation research based on multilayer synchronization network [J].Systems Engineering-Theory & Practice，2017,39(1):   
182-190.) [31]李延龙，马军，李鸿伯．具有稀疏突触的多层神经网络同步中的耦 合参数[C]//全国复杂系统研究论坛论文集（二），2005:764-768. (Li Yanlong,Ma Jun,Li Hongbo.Coupling Intensity in Synchronization ofMulti-layer Neural Networks with Diluted Synapses [C]//Proc of National Complex Systems Research Forum (2).2005:764-768.) [32]Jungenitz T,Beining M,Radic T,et al. Structural homo-and heterosynaptic plasticity in mature and adult newborn rat hippocampal granule cells [J].Proceedings of National Academy of Sciences,2018,   
155 (20):4670-4679.