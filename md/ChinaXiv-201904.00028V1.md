# 基于异质移动网络的破坏性病毒传播模型

刘超，黄诗雯，黄贤英，刘小洋，杨宏雨(重庆理工大学 计算机科学与工程学院，重庆 400054)

摘要：针对现有研究没有考虑移动网络节点异质性与没有构建破坏性病毒传播模型的问题，提出一个基于异质移动网络的破坏性病毒传播模型。通过考虑移动网络节点的异质性，进一步将易感染状态划分为新系统状态和旧系统状态，并结合破坏性病毒的潜伏与爆发特性将感染状态划分为潜伏状态和爆发状态。计算了模型的平衡点与传播阈值，并指出当传播阈值大于1时，模型在正平衡点处不稳定；当传播阈值小于1时，模型在正平衡点处局部渐近稳定。在NW小世界网络和BA无标度网络上进行仿真对比实验，仿真结果表明，两个网络的病毒传播速度不同，NW网络存在病毒完全消除的情况，而BA网络中的病毒不会被完全清除。

关键词：异质移动网络；破坏性病毒；传播模型中图分类号：TP393.08 doi:10.19734/j.issn.1001-3695.2018.10.0831

Destructive virus propagation model based on heterogeneous mobile networks

Liu Chao, Huang Shiwen†, Huang Xianying, Liu Xiaoyang, Yang Hongyu (College of Computer Science & Engineering,Chongqing University ofTechnology,Chongqing 400054, China)

Abstract: Aiming at the problem that theexisting networkdoes notconsider theheterogeneityof mobile network nodes and the failure to construct adestructivevirus propagationmodel,this paper proposed a destructive virus propagationmodel basedonheterogeneous mobile networks.Byconsidering the heterogeneity of mobile network nodes,this paper further dividedthe uninfected state intoanew system state and an old system state,and combined with the latent and explosive characteristicsof thedestructive virus,divided the infection state intoalatent stateand an explosive state.This paper calculated theequilibrium pointand propagation thresholdof the model,and pointedoutthat when the propagation thresholdis greater than1,the model is unstableatthepositiveequilibrium point; whenthe propagation threshold is less than1,the model is locallyasymptotically stable atthe positiveequilibrium point.This papercariedoutthe simulation experiments on the NW smallworld network and the BAscale-free network.The simulation results showed thatthe virus propagation speeds ofthe two networks are different,andthe NW network has acomplete eliminationofthe virusbutBA does not have this situation.

Key words: Heterogeneous mobile network; destructive virus; propagation model

# 0 引言

随着移动智能设备的普及，病毒开始将移动终端和移动互联网络作为新的攻击对象。恶意扣费、破坏系统、数据窃取、资费消耗等各类攻击行为不断出现，给移动网络用户造成巨大损失[I\~4]。移动病毒的不断涌现引起了社会各界对移动病毒的关注，为网络病毒传播的研究提供了新的研究方向。

国内外研究者对移动病毒传播建模已经开展了大量研究工作并取得了丰硕的研究成果。如Zhang等人[5]研究了无线传感器网络中具有蠕虫传播的SEIRS—V模型的Hopf分岔问题。Xiao等人[提出了在Wi-Fi环境中的蠕虫病毒传播模型SEIQR，其中受感染的节点可以通过Wi-Fi基站隔离，达到阻止蠕虫病毒扩散的目的。Nallusamy等人[提出了一种基于节点能量的蓝牙病毒传播模型NBV，研究模拟并比较了病毒传播与节点能量和网络流量的关系。

尽管上述的病毒传播模型能够较好地刻画移动网络中的病毒传播过程，但这些病毒传播模型大都是基于均质移动网络的，而有研究表明，现实的移动网络具有异质特性[8]。近年来，一些学者研究了与异质移动网络相关的病毒传播模型。如Zhai等人[9考虑了通过下载文件相互感染的传播方式，提出一种新模型分析HY 蠕虫传播。Guo 等人[10]考虑了异构网络的连接概率、开放概率、主机防御和CRC等因素，提出了一种H蠕虫仿真模型。黄芳等人[1考虑了蓝牙网络的连接特性、异质性、抗病毒策略、人类行为等影响病毒传播的因素，提出了一种包含人类行为影响的蓝牙通信网络病毒传播模型。

然而上述异质移动网络中的病毒研究仍然存在不足：

a)没有考虑节点的异质性。实际上，现实移动网络中的

收稿日期：2018-10-29；修回日期：2018-12-25基金项目：国家自然科学基金资助项目（61503052，61872051)；重庆市教育委员会科学技术研究项目（KJQN201801120，KJQN20180104)；重庆理工大学两江国际学院预研基金项目；重庆市科委民生与社会保障项目（cstc2018jscx-msybX0049)；重庆市教育委员会人文社会科学研究项目(18SKSZ028,18SKGH10017SKG151,17SKG144);国家教育部人文社科研究项目(16JDSZ2019,16YJC870018，16YJC860010,15YJC790061)；重庆市社会科学规划青年项目（2016QNCB28)；重庆理工大学两江国际学院预研基金项目

作者简介：刘超（1983-)，男，四川广安人，副教授，博士，主要研究方向为网络空间安全动力学；黄诗雯（195-），女（通信作者），重庆丰都人，硕士研究生，主要研究方向为网络空间安全动力学（dayupnie@foxmail.com)；黄贤英（1967-），女，重庆万州人，教授，硕导，主要研究方向为网络空间安全动力学；刘小洋（1980-），男，安徽安庆人，副教授，博士，硕导，主要研究方向为网络空间安全动力学；杨宏雨（197-)），女，河南安阳人，副教授，硕士，主要研究方向为网络空间安全动力学.

未感染节点由于安全软件的影响而存在免疫能力的差异性[12,13]。如上述Guo 等人[10]的研究中只考虑了将互联网和移动通信互联网集合成异构网络，对网络结构的异质性进行分析，在模型中并未考虑节点的异质性，只将易受病毒感染的移动设备划分为一种状态，难以准确表示移动设备在病毒传播中的内在特征。

b)没有针对破坏性病毒的研究。事实上，破坏性病毒是一类破坏能力极强的病毒，与其他病毒相比，具有潜伏状态和爆发状态两个状态。其潜伏状态具有强大的传播能力可感染其他节点，而爆发状态则是实施破坏，破坏性病毒可在一夜之间感染成千上万台设备，严重影响网络安全[14,15]。但上述研究[9-1没有区分病毒的潜伏状态和爆发状态，往往忽略了病毒的潜伏状态，将感染潜伏状态病毒的移动设备简单划分为易感染节点，把感染爆发状态病毒的移动设备当做感染节点进行研究，因而现有传播模型不能反映破坏性病毒的传播行为，不能揭示病毒传播特性和内在规律。因此，有必要构建基于异质移动网络的破坏性病毒传播模型，揭示其传播特性与内在传播规律。

鉴于上述病毒传播模型的不足，本文利用传播动力学和复杂网络理论，考虑异质移动网络中移动设备免疫能力的差异性、破坏性病毒的潜伏性和爆发性，提出一种基于异质移动网络的破坏性病毒传播模型，计算模型的平衡点与传播阈值以及证明平衡点局部稳定性，并在NW小世界网络和BA无标度网络上进行仿真对比实验，提出抑制移动网络中病毒传播的防治策略。

# 1 模型建立

破坏性病毒利用系统软件或应用软件的漏洞进行传播和破坏，可通过使用安全软件病毒查杀技术达到保护移动设备安全的目的[16]。由于安全软件良莠不齐，对移动设备保护程度大相径庭，使得网络节点的免疫能力存在较大差异，即网络节点存在异质性。破坏性病毒的感染阶段可分为潜伏期和爆发期，潜伏期目的在于感染其他节点，爆发期则主要是实施破坏[14]。

根据上述分析，将移动网络节点划分为如下四个状态。

a)旧系统状态(old)。处于该状态的网络节点的免疫能力较低。旧系统状态节点记为 $o$ 节点。

b)新系统状态(new)。处于该状态的网络节点具有较高的免疫能力。新系统状态节点记为 $N$ 节点。

c)潜伏状态(latent)。指爆发之前的潜伏状态，目的是感染尽可能多的节点。处于该状态的节点记为 $\boldsymbol { L }$ 节点。

d)爆发状态(burst)。指爆发状态，目的是对节点实施破坏。处于该状态的节点记为 $B$ 节点。

与传统模型不同，ONLB模型考虑到节点的异质性，将易感染节点分为新系统节点和旧系统节点，以体现易感染节点免疫能力的差异性。同时考虑破坏性病毒的潜伏状态和爆发状态，将感染节点分为潜伏节点和爆发节点。

破坏性病毒模型状态转换示意图如图1所示，模型假设如下：

a)旧系统节点用户或潜伏节点用户会对系统进行漏洞修补或杀毒，则每个旧系统节点或潜伏节点以恒定概率 $\alpha$ 变成新系统节点。

b)随着系统版本的更新以及新漏洞的出现，若新系统节点未对系统进行漏洞修复，则每个新系统节点以恒定概率 $\beta$ 变成旧系统节点。

c)由于旧系统节点受到破坏性病毒的侵入，一个旧系统节点与一个潜伏节点接触后，该节点以恒定概率 $\gamma _ { 1 }$ 变成潜伏节点。

d)由于新系统节点受到破坏性病毒的侵入，一个新系统节点与一个潜伏节点接触后，该节点以恒定概率 $\gamma _ { 2 }$ 变成潜伏节点。

e)由于破坏性病毒存在潜伏期，每个潜伏节点以恒定概率 $\sigma$ 变成爆发节点。

f)由于爆发节点会显现出明显的中毒症状，则用户会对系统进行漏洞修复和杀毒，每个爆发节点以恒定概率 $\mu$ 变成新系统节点。

![](images/2b827786b8479c92d356d51aa5507469fdb2baf98a2bfec21eebc2e5512e7bcd.jpg)  
图1破坏性病毒状态转换示意图  
Fig.1Schematic diagram of destructive virus state transition

为了在复杂网络的ONLB模型中反映关于节点度的信息，需要将节点按照状态和度数进行联合分类。分别用 $O _ { k } \left( t \right)$ 、$N _ { k } \left( t \right)$ 、 $L _ { k } \left( t \right)$ 、 $B _ { k } \left( t \right)$ 表示 $k$ 度旧系统节点、 $k$ 度新系统节点、$k$ 度潜伏节点、 $k$ 度爆发节点在时刻 $t$ 的占比。考虑ONLB模型的微分动力学系统如下：

$$
\begin{array} { r l } & { \frac { \partial \hat { \theta } _ { ( , i ) } } { \partial t } = \beta \Lambda _ { ( , i ) } ( t ) - \sigma \delta ( t ) } \\ & { \qquad - \gamma _ { \mathrm { s } } \delta ( t ) \sum _ { n = 1 } ^ { \infty } ( \operatorname* { m a x } _ { p } ( \operatorname* { m i n } _ { t \in \mathcal { I } _ { n } } ) \delta ( t ) ) \hat { \lambda } _ { \infty } ( t ) } \\ & { \frac { \partial \hat { \theta } _ { ( , i ) } } { \partial t } = \alpha \delta _ { ( , i ) } ( t ) + \beta \kappa _ { ( , i ) } ( t ) - \beta \kappa _ { ( , i ) } ( t ) } \\ & { \qquad - \gamma _ { \mathrm { s } } \gamma _ { \mathrm { s } } ( t ) \sum _ { n = 1 } ^ { \infty } ( \operatorname* { m i n } _ { p } ( \operatorname* { m i n } _ { t \in \mathcal { I } _ { n } } ) \delta ( t ) ) } \\ & { \frac { \partial \hat { \theta } _ { ( , i ) } } { \partial t } = \gamma \delta ( t ) \sum _ { n = 1 } ^ { \infty } ( \operatorname* { m i n } _ { p } ( \operatorname* { m i n } _ { t \in \mathcal { I } _ { n } } ) \delta ( t ) ) } \\ & { \qquad + \gamma _ { \mathrm { s } } \hbar \kappa _ { ( , i ) } ( t ) \sum _ { n = 1 } ^ { \infty } ( \operatorname* { m i n } _ { p } ( \operatorname* { m i n } _ { t \in \mathcal { I } _ { n } } ) \delta ( t ) ) } \\ & { \qquad - \gamma _ { \mathrm { s } } \hbar \kappa _ { ( , i ) } ( t ) - \sigma \delta ( t ) } \\ & { \qquad - \alpha \kappa _ { ( , i ) } ( t ) - \sigma \delta ( t ) , } \\ & { \frac { \partial \hat { \theta } _ { ( , i ) } } { \partial t } = \alpha \delta _ { ( , i ) } ( t ) - \beta \kappa _ { ( , i ) } ( t ) . } \end{array}
$$

其中: $p ( m | k )$ 表示度为 $k$ 的节点与度为 $m$ 的节点连接的条件概率，在度不相关的网络中， $p ( \mathbf { m } | k ) { = } \mathbf { m } p ( m ) / \langle k \rangle$ ， $p ( m )$ 为度分布函数， $\left. k \right.$ 为网络节点平均度， $\phi ( m )$ 表示度为 $m$ 的潜伏节点在单位时间内总的有效接触时间，假设每次接触是等时的， $\phi ( m ) / m$ 是它与每条边接触时间。这里取 $\phi ( m ) = A$ 为常数，因此系统(1)变为

$$
\left\{ \begin{array} { l l } { \displaystyle \frac { d \partial \Omega _ { 0 } ( t ) } { d t } = \beta N _ { \mathrm { t } } ( t ) - \alpha \alpha _ { 0 } ( t ) } \\ { \qquad \quad - \frac { P _ { \mathrm { t } } ( A _ { 0 } , B _ { \ell } ( t ) ) } { ( k \zeta ) } \sum _ { \ell = 1 } ^ { p } ( m ) { L _ { \mathrm { s } } ( t ) } . } \\ { \displaystyle \frac { d N _ { \mathrm { t } } ( t ) } { d t } = \alpha L _ { \mathrm { s } } ( t ) + \beta L _ { \mathrm { s } } ( t ) - \beta N _ { \mathrm { t } } ( t ) } \\ { \qquad \quad - \frac { P _ { \mathrm { t } } ( A _ { \mathrm { s } } , B _ { \ell } ( t ) ) \sum _ { \ell = 1 } ^ { p } \left( m \right) L _ { \mathrm { s } } ( t ) } { \sqrt { A _ { \mathrm { t } } } } , } \\ { \displaystyle \frac { d D _ { 0 } ( t ) } { d t } = \beta _ { \mathrm { t } } ^ { - } L _ { \mathrm { s } } ^ { A } \delta _ { 0 } ( t ) \sum _ { \ell = 1 } ^ { p } ( m ) L _ { \mathrm { s } } ( t ) . } \\ { \quad \quad + \frac { P _ { \mathrm { t } } ^ { - } L _ { \mathrm { s } } ^ { A } } { \sqrt { A _ { \mathrm { t } } } } N _ { \mathrm { t } } ( t ) \sum _ { \ell = 1 } ^ { p } ( m ) L _ { \mathrm { s } } ( t ) } \\ { \quad \quad - \alpha L _ { \mathrm { s } } ( t ) - \alpha L _ { \mathrm { s } } ^ { A } ( t ) . } \\ { \displaystyle \frac { d D _ { 0 } ( t ) } { d t } - \alpha L _ { \mathrm { s } } ( t ) - \beta R _ { \mathrm { t } } ( t ) . } \end{array} \right.
$$

并且各类全局密度为

$$
\begin{array} { l } { \displaystyle \int ( I ) = \sum _ { m } p ( m ) O _ { m } ( t ) , } \\ { \displaystyle \int N ( t ) = \sum _ { m } p ( m ) N _ { m } ( t ) , } \\ { \displaystyle \left\{ L ( t ) = \sum _ { m } p ( m ) L _ { m } ( t ) , \right. } \\ { \displaystyle \left. B ( t ) = \sum _ { m } p ( m ) B _ { m } ( t ) . \right. } \end{array}
$$

其中： $O ( t )$ 、 $N ( t )$ 、 $L ( t )$ 、 $B ( t )$ 表示旧系统节点、新系统节点、潜伏节点、爆发节点在时刻 $\textit { t }$ 的平均占比。

为了方便，假设系统经过归一化，于是对于不同的节点度，各个度的节点状态满足如下归一化方程：

$$
O _ { k } \left( t \right) + N _ { k } \left( t \right) + L _ { k } \left( t \right) + B _ { k } \left( t \right) = 1
$$

于是系统(2)的初始状态为

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { O _ { k } \left( 0 \right) = 1 - N _ { k } ^ { 0 } - L _ { k } ^ { 0 } - B _ { k } ^ { 0 } \geq 0 , } \\ { N _ { k } \left( 0 \right) = N _ { k } ^ { 0 } \geq 0 , } \\ { L _ { k } \left( 0 \right) = L _ { k } ^ { 0 } \geq 0 , } \\ { B _ { k } \left( 0 \right) = B _ { k } ^ { 0 } \geq 0 . } \end{array} \right. } \end{array}
$$

其中： $O _ { k } \left( 0 \right)$ 、 $N _ { k } \left( 0 \right)$ 、 $L _ { k } \left( 0 \right)$ 、 $B _ { k } \left( 0 \right)$ 表示度为 $k$ 的旧系统节点、新系统节点、潜伏节点、爆发节点在时刻 $t$ 为0的平均占比。

# 2 模型分析

本节将对上述建立的模型进行理论分析，计算模型的传播阈值[17]、平衡点以及证明平衡点的稳定性[18]。下面由正平衡点的存在性给出系统(2)传播阈值的计算。

令系统式(2)的右边为零，则可得到平衡点 $\{ \mathbf { O } _ { k } , N _ { k } , L _ { k } , B _ { k } \}$ 满足如下方程：

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { \beta N _ { k } \left( t \right) - \alpha O _ { k } \left( t \right) } \\ { \quad - \frac { \gamma _ { \mathrm { t } } A } { \left. k \right. } k O _ { k } \left( t \right) L \left( t \right) = 0 , } \\ { \alpha L _ { k } \left( t \right) + \mu B _ { k } \left( t \right) - \beta N _ { k } \left( t \right) } \\ { \quad \quad - \frac { \gamma _ { \mathrm { t } } A } { \left. k \right. } k N _ { k } \left( t \right) L \left( t \right) = 0 , } \\ { \frac { \gamma _ { \mathrm { t } } A } { \left. k \right. } k O _ { k } \left( t \right) L \left( t \right) + \frac { \gamma _ { \mathrm { t } } A } { \left. k \right. } k N _ { k } \left( t \right) L \left( t \right) } \\ { \quad \quad - \alpha L _ { k } \left( t \right) - \sigma L _ { k } \left( t \right) = 0 , } \\ { \sigma L _ { k } \left( t \right) - \mu B _ { k } \left( t \right) = 0 . } \end{array} \right. } \end{array}
$$

由方程(5)及 $O _ { k } \left( t \right) + N _ { k } \left( t \right) + L _ { k } \left( t \right) + B _ { k } \left( t \right) = 1$ 计算可得 $L _ { k }$ 如式(6)所示。将式(6)代入到 $L ( t ) = \sum _ { m } p ( m ) L _ { m } ( t )$ 可得 $\textbf { \em L }$ ，如式(7)所示。显然 $\boldsymbol { L }$ 存在正解，下面给出存在唯一正解的条件，记 $F ( L )$ 如式(8)所示。

$$
\begin{array} { c } { { L _ { \mathrm { { s } } } = \frac { \mu ( \alpha  k ) + \gamma _ { \mathrm { { t } } } A k L ) ( \beta  k  + \gamma _ { \mathrm { { t } } } A k L ) } { \mu  k  ( \alpha + \sigma ) ( \alpha  k  + \gamma _ { \mathrm { { t } } } A k L ) + \beta  k  + \gamma } } } \\ { { \ \ } } \\ { { \displaystyle ( \alpha  k  + \gamma _ { \mathrm { { t } } } A k L ) ( \beta  k  + \gamma _ { \mathrm { { t } } } A k L ) ( \mu + \sigma ) } } \\ { { L = \sum _ { \mathrm { { s } } } p ( k ) \frac { \mu ( \alpha  k  + \gamma _ { \mathrm { { t } } } A k L ) ( \beta  k  + \gamma _ { \mathrm { { t } } } A k L ) } { \mu  k  ( \alpha + \sigma ) ( \alpha  k  + \gamma _ { \mathrm { { t } } } A k L + \beta  k  +  } } } \\ { { \  ( \alpha  k  + \gamma _ { \mathrm { { t } } } A k L ) ( \beta  k  + \gamma _ { \mathrm { { t } } } A k L ) ( \mu + \sigma )  } } \\ { { \   \mathrm { } ( \alpha  k  + \gamma _ { \mathrm { { t } } } A k L ) ( \beta  k  + \gamma _ { \mathrm { { t } } } A k L ) ( \beta  k ) + \gamma _ { \mathrm { { t } } } A k L )  } } \\  { \ \mathrm { { c } } ( L ) = L - \sum _ { \mathrm { { s } } } p ( k ) \frac { \mu ( \alpha  k  + \gamma _ { \mathrm { { t } } } A k L ) ( \beta  k  + \gamma _ { \mathrm { { t } } } A k L ) } { \mu  k  ( \alpha + \sigma ) ( \alpha  k  + \gamma _ { \mathrm { { t } } } A k L + \beta  k  +  } } \\ { {   ( \alpha  k  + \gamma _ { \mathrm { { t } } } A k L ) ( \beta  k  + \gamma _ { \mathrm { { t } } } A k L ) ( \mu + \sigma )  } } \end{array}
$$

经计算得 $d F ( L ) / d L < 0 , d ^ { 2 } F ( L ) / d L ^ { 2 } > 0 .$ 且 $F ( 0 ) < 0 , F ( 1 ) > 0$ 从而可得到有唯一正解的充分必要条件为

$$
\frac { ( \gamma _ { 1 } \beta + \gamma _ { 2 } \alpha ) A } { 2 ( \alpha + \sigma ) } > 1 .
$$

因此得到系统式(2)的传播阈值为

$$
\mathbb { R } _ { 0 } = \frac { ( \gamma _ { 1 } \beta + \gamma _ { 2 } \alpha ) A } { 2 ( \alpha + \sigma ) } .
$$

定理1 当传播阈值 $\mathbb { R } _ { 0 } = \left( \gamma _ { 1 } \beta + \gamma _ { 2 } \alpha \right) A / 2 ( \alpha + \sigma ) < 1$ 时，系统式(2）在 $E _ { 0 } \left\{ ( 0 , 1 , 0 , 0 ) \right\}$ 附近局部稳定，当$\mathbb { R } _ { 0 } = \left( \gamma _ { 1 } \beta + \gamma _ { 2 } \alpha \right) A / 2 ( \alpha + \sigma ) > 1$ 时，系统式(2)在 $E _ { 0 } \{ ( 0 , 1 , 0 , 0 ) \}$ 附近不稳定，即系统(2)的病毒是持续存在的，即 $\varepsilon > 0$ ，使得

$$
\operatorname* { l i m i n f } _ { t  \infty } \ L ( t ) = \operatorname* { l i m i n f } _ { t  \infty } \ \sum _ { k } p ( k ) L _ { k } ( t ) > \varepsilon .
$$

证明由系统式(2)得如下等价动力学方程：

$$
\{ \begin{array} { l l } { \displaystyle \frac { d O _ { s } ( t ) } { d t } = \beta \big ( 1 - O _ { \mathrm { t } } ( t ) - L _ { \mathrm { t } } ( t ) - B _ { \mathrm { i } } ( t ) \big ) } \\ { \displaystyle \qquad - \alpha O _ { \mathrm { t } } ( t ) - \frac { \gamma _ { \mathrm { t } } A } {  k  } A O _ { \mathrm { t } } ( t ) \sum _ { n } p ( m ) L _ { \mathrm { s } } ( t ) , } \\ { \displaystyle \frac { d L _ { \mathrm { x } } ( t ) } { d t } = \frac { \gamma _ { \mathrm { t } } A } {  k  } _ { \mathrm { ~ w ~ } } } \\ { \displaystyle \qquad + \frac { \gamma _ { \mathrm { t } } ^ { 2 } A } {  k  } _ { \mathrm { ~ w ~ } } ( t ) \sum _ { n } p ( m ) L _ { \mathrm { s } } ( t ) } \\ { \displaystyle \qquad - \alpha L _ { \mathrm { s } } ( t ) - \sigma L _ { \mathrm { t } } ( t ) , } \\ { \displaystyle ( \frac { d B _ { \mathrm { t } } ( t ) } { d t } = \sigma L _ { \mathrm { t } } ( t ) - \mu B _ { \mathrm { t } } ( t ) . } \end{array} 
$$

系统的Jacobian矩阵是 $3 K _ { \operatorname* { m a x } } \times 3 K _ { \operatorname* { m a x } }$ 矩阵，如下所示：

$$
J = \left[ { \begin{array} { c c c c c c } { \mathbf { A } _ { 1 } } & { \mathbf { B } _ { 1 2 } } & { \mathbf { B } _ { 1 3 } } & { \cdots } & { \mathbf { B } _ { 1 k _ { \mathrm { m a x } } } } \\ { \mathbf { B } _ { 2 1 } } & { \mathbf { A } _ { 2 } } & { \mathbf { B } _ { 2 3 } } & { \cdots } & { \mathbf { B } _ { 2 k _ { \mathrm { m a x } } } } \\ { \vdots } & & { \ddots } & & { \vdots } \\ { \mathbf { B } _ { k _ { \mathrm { m a x } } 1 } } & { \mathbf { B } _ { k _ { \mathrm { m a x } } 2 } } & { \mathbf { B } _ { k _ { \mathrm { m a x } } 3 } } & { \cdots } & { \mathbf { A } _ { k _ { \mathrm { m a x } } } } \end{array} } \right]
$$

$$
A _ { j } = \left[ \begin{array} { l l l l } { - \beta - \alpha } & { \quad - \beta } & { \quad - \beta } \\ { \quad } & { \quad \frac { \gamma _ { 2 } j p \left( j \right) } { \left. k \right. } - \alpha - \sigma } & { \quad 0 } \\ { \quad } & { \quad \sigma } & { \quad - \mu } \end{array} \right] ,
$$

$$
B _ { i j } = \left[ \begin{array} { c c c c c c } { 0 } & { } & { } & { } & { } & { 0 } \\ { } & { } & { } & { } & { } & { } \\ { 0 } & { } & { } & { \frac { \gamma _ { 2 } j p \left( j \right) } { \left. k \right. } } & { } & { } & { 0 } \\ { } & { } & { } & { \sigma } & { } & { } & { - \mu } \end{array} \right] .
$$

通过计算得矩阵的特征值为 $\lambda _ { 1 } = - \beta - \alpha$ ， $\lambda _ { 2 } = - \mu$ ，$\lambda _ { 3 } = \gamma _ { 2 } - \alpha - \sigma$ 。当 $\mathbb { R } _ { 0 } < 1$ ，特征值全为负，证明系统(2)的无病平衡点 $E _ { 0 } \left\{ ( 0 , 1 , 0 , 0 ) \right\}$ 局部稳定；当 $\mathbb { R } _ { 0 } > 1$ ，有正实部的根，证明无病平衡点 $E _ { 0 } \{ ( 0 , 1 , 0 , 0 ) \}$ 不稳定。

# 3 仿真分析

由于现实的移动网络可能同时具有小世界网络和无标度网络的特性[19]，本文利用相关算法生成了两个仿真网络用来模拟异质移动网络中破坏性病毒的传播，它们分别是NW小世界网络和BA无标度网络。各网络的相关拓扑特性参数如表1所示，各网络结构如图2所示，各网络度分布如图3所示。

表1各网络的相关特性参数  
  

<html><body><table><tr><td>Table1</td><td colspan="5">Relevantcharacteristic parameters of each network</td></tr><tr><td>网络名称</td><td></td><td></td><td>节点个数 边数 节点平均度 节点最大度数 聚类系数 度相关系数</td><td></td><td></td></tr><tr><td>NW小世界网络</td><td>5000</td><td>33460 6.6920</td><td>12</td><td>0.4949</td><td>0.1087</td></tr><tr><td>BA无标度网络</td><td>5000</td><td>49944 9.9888</td><td>226</td><td>0.0113</td><td>-0.0415</td></tr></table></body></html>

结合表1、图2和3可知，文中NW小世界网络聚类系数较高，服从泊松分布，度相关系数为正数，属于同配性均匀网络；BA无标度网络度分布服从幂律分布，聚类系数较低，度相关性为负数，属于异配性非均匀网络。

本节设置三个实验，实验1研究异质移动网络中各个节点密度随时间的演化关系，探寻其变化规律；实验2针对节点的异质性，研究节点免疫能力的差异性与网络中爆发节点变化情况的关系；实验3根据破坏性病毒潜伏状态和爆发状态，将两种状态结合，重点研究破坏性病毒对不同度的节点造成的影响程度。最后对实验结果进行分析讨论，提出可以抑制破坏性病毒在异质移动网络中传播的相关策略。在下列实验中均设置初始状态网络中的旧系统节点、新系统节点、潜伏节点和爆发节点分别为 $O ( 0 ) { = } 2 4 9 0$ ， $N ( 0 ) = 2 4 9 0$ ， $L ( 0 ) { = } 1 0$ ，$B ( 0 ) { = } 1 0$ 。迭代次数 ${ \cal T } = 2 0 0 0$ 。

![](images/59d4e2f6e64653a4da17ed3f8aa1712a58c9b11d4004393db40330ed5e0c0cae.jpg)

![](images/3de1950295a297ead1a8cbe274f1539f31b4b98d7bd0d01e79ff26bcc933c7d4.jpg)  
Fig.2Network structure diagrams   
图3各网络节点度分布图；  
Fig.3Distribution of network node degrees

实验1为研究异质移动网络中各节点密度随时间变化情况是否有一定规律，现研究旧系统节点、新系统节点、潜伏节点和爆发节点的密度随时间的演化情况。设置模型参数如下： $\scriptstyle \alpha = 0 . 1$ ， $\scriptstyle { \beta = 0 . 2 }$ ， $\gamma _ { 1 } { = } 0 . 5$ ， $\gamma _ { 2 } { = } 0 . 2$ ， $\scriptstyle \mu = 0 . 8$ ， $\sigma { = } 0 . 5$ 。

如图4所示，在给定初始状态后，网络中不同节点的密度在经过一定时间后都趋于稳定。旧系统节点密度在初期迅速上升到峰值便下降至稳定状态；新系统节点密度在初始阶段快速下降到底值后渐渐趋于稳定；潜伏节点密度和爆发节点密度均缓缓上升趋于稳定。虽然初始状态的旧系统节点和新系统节点数量相同，但在稳定状态存在较多的旧系统节点、较少的潜伏节点、少量的新系统节点和极少爆发节点。四类节点在两个网络拓扑中表现出部分相同的规律，但同时又存在一定区别。

![](images/b561f1519eddf5cd377a13e14d82b5f87cd0653e9a27a55216d38ca16a54a940.jpg)  
图4各网络的模型节点密度随时间的变化关系;  
Fig.4Relationship between node density of each network and time

$O ( t )$ 在到达峰值后，在NW小世界网络中是缓慢下降趋于稳态，趋于稳定的时间步出现在第60、70步；而在BA无标度网络中， $O ( t )$ 是先迅速下降至底值而后趋于稳态，趋于稳定的时间步出现在第10、20步。继续观察其他节点发现，潜伏节点密度和爆发节点密度均在NW网络的第40、50时间步才到达稳态值，而在BA网络的第5、10时间步便趋于稳态值。这说明ONLB模型中非均匀网络BA到达稳态值的时间少于均匀网络NW，可以认为非均匀网络传播速度快于均匀网络。

分别比较两个网络趋于稳定的 $O ( t )$ 和 $L ( t )$ 可以发现，NW小世界网络中的旧系统节点较多，潜伏节点较少，BA无标度网络中的潜伏节点较多，旧系统节点较少。这说明在NW网络中虽然存在较多免疫能力较低的移动智能设备，但只存在极少潜伏状态的病毒；反之在BA网络中虽然存在较少免疫能力较低的移动智能设备，但存在较NW网络多的潜伏状

态的病毒。

综上可知，NW小世界网络和BA无标度网络有部分相同的传播规律，但在病毒传播过程中的传播速度不同。在两个网络中，移动智能设备在经过修复、杀毒一系列操作后终会趋于稳定，且处于旧系统状态的移动智能设备居多，同时设备中可能仍然存在病毒。

实验 2由于 $\alpha$ 和 $\beta$ 的参数与是否更新杀毒相关，能改变节点的免疫能力，为了研究节点免疫能力的异质性与网络中爆发节点变化情况的关系，本文重点研究模型中 $\alpha$ 和 $\beta$ 对爆发节点 $B$ 的影响。设置模型参数如下： $\gamma _ { 1 } { = } 0 . 5$ ， $\gamma _ { 2 } { = } 0 . 2$ ，$\scriptstyle \mu = 0 . 8$ ， $\sigma { = } 0 . 5$ 。

由实验1可知，此时病毒传播已经达到平衡状态，各类节点所占百分比基本稳定。图5显示了 $B$ 在 $\alpha$ 取不同值的情况下随 $\beta$ 的变化关系，图6给出了它们的三维图。从图中可以看出，在NW小世界网络中存在 $B$ 节点为零的情况，但对于BA无标度网络，不论 $\alpha$ 和 $\beta$ 取何值，爆发节点 $B$ 都存在。这是源于小世界网络存在病毒传播临界阈值的特性，而无标度网络由于它的幂律型度分布使得具有不存在病毒传播临界阈值的性质。可以认为在BA无标度网络中的用户节点对移动智能设备采取的任何杀毒措施都无法完全消灭病毒。

现从图5和6可以进一步分析 $\alpha$ 和 $\beta$ 分别对 $B$ 的影响。在 $\beta$ 相同的情况下，两个网络中 $B$ 的最终密度随着 $\alpha$ 的增长而有所降低，这表明及时更新系统进行修复和杀毒达到及时提高节点免疫能力的目的，对爆发病毒的出现有较明显的抑制效果。

![](images/794450be94f2376f22e25ee48a9e4d39b870f5471b562a40ca19e9bb34c2c39a.jpg)  
图5各网络的爆发节点最终密度 $B$ 在 $\alpha$ 取不同值时随 $\beta$ 的变化关系  
Fig.5Relationship between the final density of the burst node $B$ of each network and $\beta$ when $\alpha$ takes different values

![](images/2d9f8a68b1d60e60a4a7e5ba3ec5d85c868b9b96e803df5b05aa9e050bc2273d.jpg)  
图6各网络的ONLB模型中不同 $\alpha$ ， $\beta$ 下 $B$ 变化的三维图 Fig.6Three-dimensional graphs of $B$ under different $\alpha$ ， $\beta$ and value changes in ONLB models of networks;

在 $\alpha$ 相同的情况下，对于NW小世界网络中的模型，初始 $B$ 较小，随着 $\beta$ 增加而缓慢上升直到 $\beta$ 处于0.6-0.7才趋于稳态；在BA无标度网络中，初始 $B$ 较大，随着 $\beta$ 增加而较快上升至 $\beta$ 居于0.3-0.4便趋于稳态。这表明NW网络中 $B$ 受$\beta$ 值影响较大，即若未更新系统状态，降低节点免疫能力，移动智能设备受病毒破坏的几率更大；而在BA网络中， $B$ 只有在 $\beta$ 值较小时随 $\beta$ 值不同变化程度大， $\beta$ 值较大时 $B$ 变化不大，即若新系统节点不及时更新杀毒，不及时提高免疫能力会导致移动智能设备出现较多爆发状态的病毒，但若长期不更新系统状态，不提高免疫能力，爆发状态病毒数量变化不大。

实验3由于破坏性病毒分为潜伏和爆发两种状态，分别对节点进行感染和破坏。为了研究不同度的节点受破坏性病毒的影响，本文将潜伏节点和爆发节点相结合，重点研究各个不同度的节点受移动设备破坏性病毒感染和破坏的平均时间分布。设置模型参数与实验1相同。

如图7所示，从整体来看，不同网络中的节点受病毒影响的平均时间均随着其节点度的增大而增大，而受病毒影响的平均时间越长，则表示受病毒感染和破坏的节点越多。即节点的度数越大，其受病毒感染的概率越大。这表明，若移动智能设备在网络中连接过多的软件应用程序，将会加大其受破坏性病毒感染的概率。因此，及时关闭移动智能设备不必要的后台应用程序可以有效防止其受破坏性病毒的感染和破坏。

进一步分析两个网络的差异，发现在NW小世界网络中，节点受病毒影响的时间随着其节点度的增加而增加，直到节点最大度；而在BA无标度网络中，当网络的节点度不足50，节点度越大，节点受移动设备破坏性病毒影响的平均时间越长；当节点度超过50，节点受破坏性病毒影响的平均时间趋于最大值并保持稳定。这表明，NW网络中不同度的节点受病毒影响时间差距较大，而BA网络超过50度的节点受病毒影响的时间差别不大。观察比较两个网络的节点度受病毒影响的平均时间大小，得知 NW网络的最大平均时间值小于BA网络的最小平均时间值，说明在BA无标度网络中的节点受病毒感染和破坏的程度比在NW小世界网络大。这体现了BA无标度网络的连通性，使得网络中的病毒传播速度随着节点度的增大而增大，而节点受病毒影响的时间也随之增长。这进一步印证，过多的软件应用连接会加大移动智能设备受破坏性病毒感染的概率，使其被病毒攻击破坏，严重威胁到设备的安全。

![](images/f049233ac88c2f86747bb28f4f149ebfd77ec838ccaa8c9b1d959bd3d794be4a.jpg)  
图7不同度的节点受移动设备破坏性病毒影响的平均时间分布；Fig.7Average time distribution of nodes with different degreesaffected bydestructive viruses of mobile devices

综合考虑上述三个实验的仿真结果，可以提出以下抑制破坏性病毒在异质移动网络中传播的防治策略： (1)为增强移动智能设备免疫能力，可对移动设备的系统软件和安全软件定期进行升级更新； (2)为确保移动智能设备安全，可利用安全软件对移动智能设备及时进行病毒查杀和漏洞修复； (3)为减少移动智能设备受破坏性病毒影响的时间，可关闭移动智能设备中暂时不使用的后台应用程序。

# 4 结束语

本文提出了一种基于异质移动网络的破坏性病毒传播模型。考虑异质网络节点的异质性，将系统中未受病毒感染的节点划分为新系统状态节点和旧系统状态节点；考虑破坏性病毒的潜伏性，将感染节点分为潜伏节点和爆发节点。理论分析表明，模型存在一个无毒平衡点并局部渐近稳定，且无毒平衡点的稳定性与传播阈值密切相关。在NW小世界网络和BA无标度网络分别对ONLB病毒传播模型进行了仿真模拟。仿真发现，两个网络的病毒传播速度不同，在NW小世界网络中存在无病毒存在的情况，这与理论分析一致，而BA网络中的病毒仍然存在。通过对移动智能设备采取系统更新、病毒查杀的措施可以有效抑制病毒的传播，并且，定期清理应用软件的连接可以有效防止其被病毒感染和破坏。本文工作有助于进一步了解异质移动网络中的破坏性病毒传播行为规律及网络拓扑结构对破坏性病毒传播的影响，如何在动态网络中对破坏性病毒传播行为进行建模和分析将成为今后的研究工作。

# 参考文献：

[1]王春新，李信，于然，等．电力移动智能终端安全技术研究[J]．信 息网络安全，2014(4):70-77.(Wang Chunxin,Li Xi,Yu Ran,et al. Research on security technology of power mobile intelligent terminal [J].Information Network Security,2014 (4): 70-77.)   
[2] 范红，杜大海，王冠．移动互联网安全测评关键技术研究[J].中兴 通讯技术，2015(3):38-40.(Fan Hong，Du Dahai，Wang Guan. Research on key technologies of mobile internet security assessment [J]. ZTE Communications Technology,2015 (3):38-40.)   
[3]林鑫．基于沙盒的 Android 恶意软件检测技术研究[J]．电子设计工 程,2016,24(12): 48-50.(Lin Xin. Research on sandbox-based android malware detection technology [J]. Electronic Design Engineering,2016, 24(12): 48-50.)   
[4] 刘彩霞，季新生，邬江兴．一种基于 MSISDN 虚拟化的移动通信用 户数据拟态防御机制[J]．计算机学报，2018，41(2):275-287.(Liu Caixia,Ji Xinsheng,Wu Jiangxing.A mobile communication user data mimetic defense mechanism based on MSISDN virtualization [J]. Journal of Computer Science,2018,41(2): 275-287.)   
[5] Zhang Zizhen,Wang Yougang. Bifurcation analysis for an SEIRS-V model with delays on the transmission of worms in a wireless sensor network [J].Mathematical Problems in Engineering，2017,2017: articleID 9898726,.   
[6] Xiao Xi,Fu Peng,Dou Changsheng,et al.Design and analysis of SEIQRwormpropagationmodelinmobileInternet[J]. Communications in Nonlinear Science and Numerical Simulation,2017, 43(2): 341-350.   
[7]Nallusamy T,Ravi T. Node energy based virus propagation model for Bluetooth [J]. Journal of Engineering and Applied Sciences,2O18,13(2): 394-397.   
[8]鲁延玲．基于人类行为的复杂网络病毒传播研究[D]．南京：南京邮 电大学,2015.(Lu Yanling. Research on the transmission of complex network viruses based on human behavior [D].Nanjing：Nanjing University of Posts and Telecommunications,2015.)   
[9] Zhai Lidong,Guo Wei, Jia Zhaopeng,et al. Worm propagation model for heterogeneous network [C]//Proc of International Conference on Cyber-Enabled Distributed Computing and Knowledge Discovery. Washington DC: IEEE Computer Society,2012: 151-154.   
[10] Guo Wei, Zhai Lidong,Ren Yunlong,et al. Intelligent heterogeneous network worms propagation modeling and analysis [C]//Computer Science and Its Applications.Dordrecht:Springer,2012: 515-524.   
[11] 黄芳，刘元君，陈波，等．一种包含人类行为影响的异质蓝牙网络病 毒传播模型[J].计算机应用研究，2014,31(7):2144-2147.(Huang Fang,Liu Yuanjun, Chen Bo,et al.A virus propagation model for heterogeneous bluetooth networks containing human behavior [J]. Computer Applied Research,2014,31(7): 2144-2147.)   
[12] Li Yong,Hui Pan,Jin Depeng,et al.Optimal distributed malware defense in mobile networks with heterogeneous devices [J]. IEEE Trans on Mobile Computing,2014,13(2): 377-391.   
[13] Yang Luxing，DRAIEF M,Yang Xiaofan．The optimal dynamic immunization under a controlled heterogeneous node-based SIRS model [J].Physica A:Statistical Mechanics & Its Applications,2016, 450(9): 403-415.   
[14]田畅，郑少仁．计算机病毒计算模型的研究[J]．计算机学报，2001, 24(2):158-163.(Tian Chang，Zheng Shaoren.Research on computer virus computing model [J]. Journal of Computer Science,2Oo1,24(2): 158-163. )   
[15] Yang Luxing,Yang Xiaofan,Zhu Qingyi,et al.A computer virus model with graded cure rates [J].Nonlinear Analysis Real World Applications, 2013,14(1): 414-422.   
[16]王雨晨．系统漏洞原理与常见攻击方法[J].计算机工程与应用，2001, 37(3):62-64.(Wang Yuchen.Principle of system vulnerability and common attacking methods [J].Computer Engineering and Application, 2001,37(3):62-64.)   
[17] Pastorsatorras R.Epidemic spreading in scale-free networks [J]. Physical Review Letters,2000,86(14):3200-3203.   
[18] Liu Junli,Zhang Tailei.Epidemic spreading of an SEIRS model in scale-free networks [J].Communications in Nonlinear Science & Numerical Simulation,2011,16(8):3375-3384.   
[19]杜海峰，李树茁，MarcusWF,等．小世界网络与无标度网络的社区 结构研究 [J].物理学报，2007,56(12):6886-6893.(Du Haifeng，Li Shuzhuo,Marcus WF,et al.Research on community structure of small World network and scale-free network [J].Journal of Physics,2007, 56(12):6886-6893.)