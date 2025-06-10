# 多体多自由度量子隐形传态的张量表示\*

征夏明’21（安徽大学 物质科学与信息技术研究院，安徽 230039）2（中国科学院固体物理研究所，安徽 230031)

# 摘要:

[目的」找到一种最普遍情况下量子隐形传态的一般表示及代数结构。  
[方法]归纳推理与演绎推理，利用多项式相乘与张量积之间的等价性发现一般规律。[结果］将多体单自由度或单体多自由度的量子隐形传态推广至多体多自由度，以及混合态。  
[局限］无法推广至连续谱量子态。  
[结论］预言多体多自由度单次量子隐形传态的存在，并包含了已被实验证实的所有特殊情况。  
关键词：量子隐形传态 贝尔基 幺正变换

分类号：0413

# Quantum Teleportation of Many-body System with Multiple

# Degrees of Freedom

Xm Zheng12 1(Institute of Physical Science and Information Technology， Anhui University, Anhui，230039，China) 2 (Institute of Solid State Physics, Chinese Academy of Sciences, Anhui 230031，China)

Abstract:

[Objective] Finding a scheme and algebra structure of general quantum teleportation.

[Methods] Inductive reasoning and deductive reasoning. The equivalence between polynomial multiplication and tensor product.

[Results] Many-body or multi-degrees of freedom cases are generalized in multiple particles system with higher degrees of freedom, even mixed states.

[Limitations]It is not valid about continues quantum states.

[Conclusions] Predicting the existence of quantum teleportation of multiple particles system with higher degrees of freedom. And special cases which is proven by experiment are included.

Keywords: Quantum Teleportation， Bell State， Unitary Transform

# 1引言

量子隐形传态是十分有趣且充满潜力的量子力学效应，其首次在1993年由Charles Bennett[1]等人提出，两个粒子（包含纠缠态）的量子隐形传态由李大创和曹卓良提出[2．而在2015年，潘建伟、陆朝阳等人引入并成功完成了单光子多属性的量子传送3．本文中，我将利用多粒子各个属性之间的张量积和贝尔基(Bell states)与标准正交基之间的幺正变换得出较为普适的量子传送表示法。

# 2 单量子比特情形

首先，先简略介绍最为简单的情况。Alice 和Bob 需一人持有纠缠态中的一个粒子： $\begin{array} { r } { | \varphi _ { \mathrm { A B } } \rangle = \frac { 1 } { \sqrt { 2 } } ( | 0 \rangle _ { \mathrm { A } } | 0 \rangle _ { \mathrm { B } } + | 1 \rangle _ { \mathrm { A } } | 1 \rangle _ { \mathrm { B } } ) } \end{array}$ ．同时，Alice 有待传送的粒子 $\mathrm { \Delta } \mathrm { X }$ ，$| \psi _ { \mathrm { X } } \rangle = \alpha | 0 \rangle _ { \mathrm { X } } + \beta | 1 \rangle _ { \mathrm { X } }$ ，其中 $\alpha$ ， $\beta \in \mathbb { C }$ ， $\mathbb { C }$ 是复数域，且 $| \alpha | ^ { 2 } + | \beta | ^ { 2 } = 1$

现在做X态与AB态的张量积：

$$
\begin{array} { r } { | \varPsi \rangle = | \psi _ { \mathrm { X } } \rangle \otimes | \varphi _ { \mathrm { A B } } \rangle = \frac { 1 } { \sqrt { 2 } } ( \alpha | 0 \rangle _ { \mathrm { X } } | 0 \rangle _ { \mathrm { A } } | 0 \rangle _ { \mathrm { B } } + \alpha | 0 \rangle _ { \mathrm { X } } | 1 \rangle _ { \mathrm { A } } | 1 \rangle _ { \mathrm { B } } + \beta | 1 \rangle _ { \mathrm { X } } | 0 \rangle _ { \mathrm { A } } | 0 \rangle _ { \mathrm { B } } + \beta | 1 \rangle _ { \mathrm { B } } | 1 \rangle _ { \mathrm { B } } , } \end{array}
$$

我们有 4 个贝尔基(Bell states):

$$
\begin{array} { l } { { | \phi ^ { + } \rangle = \frac { 1 } { \sqrt { 2 } } \left( | 0 0 \rangle + | 1 1 \rangle \right) , ~ | \phi ^ { - } \rangle = \frac { 1 } { \sqrt { 2 } } \left( | 0 0 \rangle - | 1 1 \rangle \right) , ~ | \psi ^ { + } \rangle = \frac { 1 } { \sqrt { 2 } } \left( | 0 1 \rangle + | 1 0 \rangle \right) , } } \\ { { | \psi ^ { - } \rangle = \frac { 1 } { \sqrt { 2 } } \left( | 0 1 \rangle - | 1 0 \rangle \right) } } \end{array}
$$

显然，贝尔基所展开的线性空间和二维的二阶张量下的线形空间同构，即与标准正交基[00)，[01)，[10)，[11)等价．从而有：

$$
\begin{array} { r l } & { | 0 0 \rangle = \frac { 1 } { \sqrt { 2 } } ( | \phi ^ { + } \rangle + | \phi ^ { - } \rangle ) , \ | 1 1 \rangle = \frac { 1 } { \sqrt { 2 } } ( | \phi ^ { + } \rangle - | \phi ^ { - } \rangle ) , \ | 0 1 \rangle = \frac { 1 } { \sqrt { 2 } } ( | \psi ^ { + } \rangle + | \psi ^ { - } \rangle ) , } \\ & { | 1 1 \rangle = \frac { 1 } { \sqrt { 2 } } ( | \psi ^ { + } \rangle - | \psi ^ { - } \rangle ) \qquad ( 2 . 3 ) } \end{array}
$$

代入 $| \psi \rangle$ ，有：

$\begin{array} { r } { | \varPsi \rangle = \frac { 1 } { 2 } ( | \phi ^ { + } \rangle _ { \mathrm { X A } } ( \alpha | 0 \rangle _ { \mathrm { B } } + \beta | 1 \rangle _ { \mathrm { B } } ) + | \phi ^ { - } \rangle _ { \mathrm { X A } } ( \alpha | 0 \rangle _ { \mathrm { B } } - \beta | 1 \rangle _ { \mathrm { B } } ) + | \psi ^ { + } \rangle _ { \mathrm { X A } } ( \alpha | 1 \rangle _ { \mathrm { B } } + | 1 \rangle _ { \mathrm { B } } ) = 0 } \end{array}$ $\beta | 0 \rangle _ { \mathrm { B } } ) + | \psi ^ { - } \rangle _ { \mathrm { X A } } ( \alpha | 1 \rangle _ { \mathrm { B } } - \beta | 0 \rangle _ { \mathrm { B } } ) )$ （204号 (2.4)  
Bob 需要准备4个幺正变换： $U _ { 0 0 } = { \binom { 1 } { 0 } } , \ U _ { 0 1 } = { \binom { 0 } { 1 } } , \ U _ { 1 0 } = { \binom { 1 } { 0 } } , \ U _ { 1 } = { \binom { 0 } { 1 } } , \quad$ $U _ { 1 1 } = \Big ( \begin{array} { l l } { { 0 } } & { { 1 } } \\ { { - 1 } } & { { 0 } } \end{array} \Big )$ .A 先对粒子X和A 做贝尔基测量(Bell state Measurement)，各有 $\frac { \cdot 1 } { 4 }$ 的概率得到 $| \phi ^ { + } \rangle _ { \mathrm { X A } } , ~ | \psi ^ { + } \rangle _ { \mathrm { X A } } , ~ | \phi ^ { - } \rangle _ { \mathrm { X A } }$ ，和 $| \psi ^ { - } \rangle _ { \mathrm { X A } }$ ，分别对应二元数组00,01,10,11.A将测得的结果以经典信息发送给 $\mathbf { B }$ ，B 将他所持有的粒子被数组所对应的幺正变换作用，将得到与初始状态 $| \psi _ { \mathrm { { X } } } \rangle$ 相同的态 $| \psi _ { \mathrm { { B } } } \rangle ^ { \prime } ~ = \alpha | 0 \rangle _ { \mathrm { { B } } } + \beta | 1 \rangle _ { \mathrm { { B } } }$ ，即完成传送.

下面全部用张量的语言描述． $| \psi _ { \mathrm { X } } \rangle = ( \alpha , \beta ) { \binom { | 0 \rangle _ { \mathrm { X } } } { | 1 \rangle _ { \mathrm { X } } } } = K _ { i } | i \rangle _ { \mathrm { X } } { } ^ { ( 1 ) }$ $\begin{array} { r l } { | \varphi _ { \mathrm { A B } } \rangle = \frac { 1 } { \sqrt { 2 } } \binom { 1 } { 0 } \begin{array} { c c } { 0 } \\ { 1 } \end{array} ! \Big \langle \frac { | 0 0 \rangle _ { \mathrm { A B } } } { | 1 0 \rangle _ { \mathrm { A B } } } } & { \big | 0 1 \big \rangle _ { \mathrm { A B } } \Big ) = \frac { 1 } { \sqrt { 2 } } \delta _ { i j } \big | i j \big \rangle _ { \mathrm { A B } } , \ \cdot \cdot \big | \psi \big \rangle = \frac { 1 } { \sqrt { 2 } } K _ { i } \delta _ { j k } \big | i j k \big \rangle _ { \mathrm { X A B } } . } \end{array}$

$$
\begin{array} { r l } & { ( | \phi _ { 0 0 } \rangle , | \phi _ { 0 1 } \rangle , | \phi _ { 1 0 } \rangle , | \phi _ { 1 1 } \rangle ) = \frac { 1 } { \sqrt { 2 } } ( | 0 0 \rangle , | 0 1 \rangle , | 1 0 \rangle , | 1 1 \rangle ) \left( \begin{array} { c c c c } { 1 } & { 0 } & { 1 } & { 0 } \\ { 0 } & { 1 } & { 0 } & { - 1 } \\ { 0 } & { 1 } & { 0 } & { 1 } \\ { 1 } & { 0 } & { - 1 } & { 0 } \end{array} \right) } \end{array}
$$

式中的变换矩阵记作 $\pmb { U }$ ，其实体表示为：$U = e _ { 0 0 } e _ { 0 0 } + e _ { 0 0 } e _ { 1 0 } + e _ { 0 1 } e _ { 0 1 } - e _ { 0 1 } e _ { 1 1 } + e _ { 1 0 } e _ { 0 1 } + e _ { 1 0 } e _ { 1 1 } + e _ { 1 1 } e _ { 0 0 } - e _ { 1 1 } e _ { 1 0 } .$ 分量表示为： $U _ { i j , l m }$ ．前两个分量是矩阵表示中的行指标，后两个分量是矩阵表示下的列指标．容易发现， $\pmb { U }$ 关于指标 $i j$ 是么正的(目前都是实数，也可以说是对称矩阵)，例如当 $l { = } 0$ $\scriptstyle m = 0$ 时，$U = e _ { 0 0 } e _ { 0 0 } + e _ { 1 1 } e _ { 0 0 } = ( e _ { 0 0 } + e _ { 1 1 } ) e _ { 0 0 } = { \binom { 1 } { 0 } } e _ { 0 0 }$ ，另一方面， $\pmb { U }$ 关于指标 $i j$ 与lm 也是幺正的，即在基(|00),|01),[10),[11))和 $( | \phi _ { 0 0 } \rangle , | \phi _ { 0 1 } \rangle , | \phi _ { 1 0 } \rangle , | \phi _ { 1 1 } \rangle )$ 之间的变换矩阵显然幺正.

$$
{ \begin{array} { c } { { \frac { 1 } { \sqrt { 2 } } } \cdot { \frac { 1 } { \sqrt { 2 } } } { \left( \begin{array} { l l l l } { 1 } & { 0 } & { 1 } & { 0 } \\ { 0 } & { 1 } & { 0 } & { - 1 } \\ { 0 } & { 1 } & { 0 } & { 1 } \\ { 1 } & { 0 } & { - 1 } & { 0 } \end{array} \right) } { \left( \begin{array} { l l l l } { 1 } & { 0 } & { 0 } & { 1 } \\ { 0 } & { 1 } & { 1 } & { 0 } \\ { 1 } & { 0 } & { 0 } & { - 1 } \\ { 0 } & { - 1 } & { 1 } & { 0 } \end{array} \right) } = { \left( \begin{array} { l l l l } { 1 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { 1 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 1 } & { 0 } \\ { 0 } & { 0 } & { 0 } & { 1 } \end{array} \right) } . } \end{array} }
$$

是， $\pmb { U }$ 关于指标 $l m$ 并不幺正.

我们将(2.5)写成分量式： $\begin{array} { r } { | \phi _ { l m } \rangle = \frac { 1 } { \sqrt { 2 } } U _ { i j , l m } | i j \rangle } \end{array}$ (2.5').等式两端取逆，有： $\begin{array} { r } { | i j \rangle = \frac { 1 } { \sqrt { 2 } } U _ { l m , i j } ^ { * } | \phi _ { l m } \rangle ^ { ( 2 ) } } \end{array}$ （204号 (2.6), 等价于

$$
\begin{array} { r } { ( | 0 0 \rangle , | 0 1 \rangle , | 1 0 \rangle , | 1 1 \rangle ) = \frac { 1 } { \sqrt { 2 } } ( | \phi _ { 0 0 } \rangle , | \phi _ { 0 1 } \rangle , | \phi _ { 1 0 } \rangle , | \phi _ { 1 1 } \rangle ) \left( \begin{array} { c c c c } { 1 } & { 0 } & { 0 } & { 1 } \\ { 0 } & { 1 } & { 1 } & { 0 } \\ { 1 } & { 0 } & { 0 } & { - 1 } \\ { 0 } & { - 1 } & { 1 } & { 0 } \end{array} \right) . } \end{array}
$$

将(2.6)代入 $| \psi \rangle$ ，得：

$\begin{array} { r } { \vert \psi \rangle = \frac { 1 } { 2 } K _ { i } \delta _ { j k } U _ { l m , i j } ^ { * } \vert \phi _ { l m } \rangle _ { \mathrm { X A } } \vert k \rangle _ { \mathrm { B } } = \frac { 1 } { 2 } K _ { i } U _ { l m , i k } ^ { * } \vert \phi _ { l m } \rangle _ { \mathrm { X A } } \vert k \rangle _ { \mathrm { B } } , } \end{array}$ 此时，对应于前文的描述，Alice对 $\mathrm { \Delta } \mathrm { X }$ 粒子和A粒子做贝尔基测量，便会知道 $l m$ 的值，将 $l m$ 发送给Bob，Bob 对B粒子做幺正变换 $U _ { l m , i j }$ ，这里的 $l m$ 正是他收到的 $l m$

（204号 $\begin{array} { r } { { \pmb U } _ { l m } | \psi \rangle = \frac { 1 } { 2 } K _ { i } U _ { l m , i k } ^ { * } U _ { l m , r k } | \phi _ { l m } \rangle _ { \mathrm { { X A } } } | k \rangle _ { \mathrm { { B } } } } \end{array}$ ，利用 $\pmb { U }$ 的幺正性得：$\begin{array} { r } { \frac 1 2 K _ { i } \delta _ { i r } | \phi _ { l m } \rangle _ { \mathrm { X A } } | r \rangle _ { \mathrm { B } } = \frac 1 2 K _ { n } | \phi _ { l m } \rangle _ { \mathrm { X A } } | r \rangle _ { \mathrm { B } } } \end{array}$ ，从而 $| \varphi _ { B } ^ { \prime } \rangle = K _ { r } | r \rangle _ { \mathrm { B } }$ ，完成传送.

# 3多粒子，单属性

我们进一步推广，分析一次性传送多粒子的情形，这里假定每个粒子只传送一个属性，每个属性所在希尔伯特空间的维数是D.

![](images/62519c6eecae6974bbc9d4f56c1f5dea3a95773ca84e0f12faf585e34693b0b0.jpg)  
图1多粒子单属性结构示意图

待传送的量子态 $| \psi _ { \mathrm { { X } } } \rangle$ 可表示为：

$$
| \psi _ { \mathrm { X } } \rangle = K _ { i _ { 1 } i _ { 2 . . } i _ { n } } | i _ { 1 } \rangle _ { \mathrm { X } _ { 1 } } \otimes | i _ { 2 } \rangle _ { \mathrm { X } _ { 2 } } \otimes . . . \otimes | i _ { n } \rangle _ { \mathrm { X } _ { n } } = K _ { i _ { 1 } i _ { 2 . . } i _ { n } } | i _ { 1 } i _ { 2 . . . } i _ { n } \rangle _ { \mathrm { X } }
$$

这样的 $| \psi _ { \mathrm { { X } } } \rangle$ 包含了所有可能的态，无论是直积态、纠缠态还是部分纠缠态．如图1所示，A与B之间的每一个粒子需要两两配对形成纠缠态．定义第 $i$ 对粒子 $\mathtt { A } _ { i } \mathtt { B } _ { i }$ 之间的最大纠缠态： $\begin{array} { r } { | \phi _ { i } \rangle _ { \mathrm { A B } } = \frac { 1 } { \sqrt { D } } \delta _ { A _ { i } B _ { i } } | A _ { i } B _ { i } \rangle _ { \mathrm { A B } } } \end{array}$ 其中 $A _ { i } B _ { i }$ 是指标)，那么Alice 和 Bob之间所持有的超纠缠态(hyper-entangled Bell states[³)为:  
$| \varphi _ { \mathrm { A B } } \rangle = | \phi _ { 1 } \rangle _ { \mathrm { A B } } \otimes | \phi _ { 2 } \rangle _ { \mathrm { A B } } \otimes . . . \otimes | \phi _ { n } \rangle _ { \mathrm { A B } }$   
$\begin{array} { r l r } { \mathrm { ~ } } & { { } } & { = \left( \frac { 1 } { \sqrt { D } } \right) ^ { n } \delta _ { A _ { 1 } B _ { 1 } } \delta _ { A _ { 2 } B _ { 2 } } \dots \delta _ { A _ { n } B _ { n } } | A _ { 1 } B _ { 1 } A _ { 2 } B _ { 2 } \dots A _ { n } B _ { n } \rangle _ { \mathrm { A B } } } \end{array}$ (3.2).  
因此，有关于XAB 的总量子态  
$\begin{array} { r } { | \varPsi \rangle = | \psi _ { \mathrm { X } } \rangle \otimes | \varphi _ { \mathrm { A B } } \rangle = \left( \frac { 1 } { \sqrt { D } } \right) ^ { n } K _ { i _ { 1 } i _ { 2 } . . . i _ { n } } \delta _ { A _ { 1 } B _ { 1 } } \delta _ { A _ { 2 } B _ { 2 } } \dots \delta _ { A _ { n } B _ { n } } | i _ { 1 } i _ { 2 } . . . i _ { n } A _ { 1 } B _ { 1 } A _ { 2 } B _ { 2 } \dots A _ { n } B _ { n } \rangle } \end{array}$ (3.3)  
文献[1]给出了关于 ${ \bf D } \geqslant 2$ 时的一组贝尔基和相关的幺正变换：

$$
\begin{array} { r } { | \phi _ { l m } \rangle = \frac { 1 } { \sqrt { D } } \sum _ { j = 0 } ^ { D - 1 } e ^ { 2 \pi \mathbf { i } j l / D } | j \rangle \otimes | ( j + m ) m o d D \rangle } \end{array}
$$

$$
\begin{array} { r } { U _ { l m } = \sum _ { k = 0 } ^ { D - 1 } e ^ { 2 \pi \mathbf { i } k l / D } | k \rangle \langle ( k + m ) m o d D | } \end{array}
$$

(3.5)式的幺正性显而易见，我们想得到他们的分量表示，用 $\left. a \right| \otimes \left. b \right|$ 乘以(3.4)两端，得到(a|(blΦm)=δajδb(j+m)moaDe²D²=δb,(a+m)modDeD$\begin{array} { r } { \therefore | \phi _ { l m } \rangle = \frac { 1 } { \sqrt { D } } \delta _ { b , ( a + m ) \mathrm { m o d } D } e ^ { \frac { 2 \pi \mathrm { i } a l } { D } } | a b \rangle , \ U _ { n m , a b } = \delta _ { b , ( a + m ) \mathrm { m o d } D } e ^ { \frac { 2 \pi \mathrm { i } a l } { D } } } \end{array}$ (3.6)类比(2.5)式， $\pmb { U } _ { l m }$ 也是基 $| \phi _ { l m } \rangle$ 和基 $\left| a b \right.$ 之间的幺正变换：  
为了便于指标运算，先将(3.6)简化，由于指标 $a$ 和 $\mathbf { \nabla } _ { m }$ 都是在0到 $\mathbf { D } { - } 1$ 之间取值，因此 $\textstyle { a + m }$ 的取值范围在0到 $2 \mathrm { D } { - } 2$ 之间，那么 $\textstyle { a + m }$ 最多比 $\mathrm { ~ D ~ }$ 大 ${ \bf D } { - } 2$ ，从而 $\delta _ { b , ( a + m ) \mathrm { m o d } D } = \delta _ { b , a + m } + \delta _ { b , a + m - D } .$ （204  
$\begin{array} { r } { \frac { 1 } { \sqrt { D } } U _ { i j , l m } ^ { * } | \phi _ { l m } \rangle = \frac { 1 } { \sqrt { D } } \big ( \delta _ { j , i + m } + \delta _ { j , i + m - D } \big ) e ^ { - \frac { 2 \pi i l l } { D } } \frac { 1 } { \sqrt { D } } \big ( \delta _ { b , a + m } + \delta _ { b , a + m - D } \big ) e ^ { \frac { 2 \pi \mathrm { i } a l } { D } } | a b \rangle } \end{array}$ （204号$\begin{array} { r l } & { = \frac { 1 } { D } ( \delta _ { j , i + m } \delta _ { b , a + m } + \delta _ { j , i + m } \delta _ { b , a + m - D } + \delta _ { j , i + m - D } \delta _ { b , a + m } + \delta _ { j , i + m - D } \delta _ { b , a + m - D } ) e ^ { - \frac { 2 \pi i i i } { D } } e ^ { \frac { 2 \pi i a l } { D } } | a b \rangle . } \end{array}$ （204括号中第一项 $\delta _ { j , i + m } \delta _ { b , a + m } = \delta _ { m , j - i } \delta _ { m , b - a } = \delta _ { j - i , b - a } ,$ （  
最后一项 $\delta _ { j , i + m - D } \delta _ { b , a + m - D } = \delta _ { m , j - i - D } \delta _ { m , b - a - D } = \delta _ { j - i , b - a } ,$ （204号  
中间两项显然为0，同时 $\begin{array} { r } { \sum _ { l } e ^ { - \frac { 2 { \pi } \mathbf { i } i l } { D } } e ^ { \frac { 2 { \pi } \mathbf { i } a l } { D } } = D \delta _ { a i } { ^ { [ 4 ] } } } \end{array}$ ：  
因此 $\begin{array} { r } { \frac { 1 } { \sqrt { D } } U _ { l m , i j } ^ { * } | \phi _ { l m } \rangle = \frac { 1 } { D } \delta _ { j - i , b - a } D \delta _ { a i } | a b \rangle = | i j \rangle . } \end{array}$ （20  
（204号 $\begin{array} { r } { \therefore | i j \rangle = \frac { 1 } { \sqrt { D } } U _ { l m , i j } ^ { * } | \phi _ { l m } \rangle } \end{array}$ （20 (3.7)，对于(3.3)式，有 $\begin{array} { r } { | i A \rangle = \frac { 1 } { \sqrt { D } } U _ { l m , i A } ^ { * } | \phi _ { l m } \rangle . } \end{array}$ （20 $\begin{array} { r } { | \Psi \rangle = \frac { 1 } { D ^ { n } } K _ { i _ { 1 } i _ { 2 } , . . . , i _ { n } } \delta _ { A _ { 1 } B _ { 1 } } \delta _ { A _ { 2 } B _ { 2 } } \dots \delta _ { A _ { n } B _ { n } } U _ { l _ { 1 } m _ { 1 } , i _ { 1 } A _ { 1 } } ^ { \dagger } U _ { l _ { 2 } m _ { 2 } , i _ { 2 } A _ { 2 } } ^ { \dagger } \dots U _ { l _ { n } m _ { n } , i _ { n } A _ { n } } ^ { \dagger } \vert \phi _ { l _ { 1 } m _ { 1 } } \rangle \vert \phi _ { l _ { 2 } m _ { 2 } } \rangle \dots \vert \phi _ { l _ { n } m _ { n } } \rangle \vert B _ { 1 } B _ { 2 } \dots B _ { n } \rangle } \end{array}$ （204同样地，Alice 对粒子对 $\cdot X _ { 1 } A _ { 1 } , X _ { 2 } A _ { 2 } . . . X _ { n } A _ { n }$ 分别作超贝尔基测量(hyper-entangledBell state measurements, $\mathrm { h - B S M } ^ { [ 3 ] }$ )，将所得态对应的二元数组依次记作记作 $l _ { 1 } m _ { 1 }$ （204号 $l _ { 2 } m _ { 2 } . . . l _ { n } m _ { n }$ 并发送给Bob，Bob 则对他持有的一组粒子按对应的编号分别作一系列幺正变换：  
$\begin{array} { r l } & { U _ { l _ { 1 } m _ { 1 } } \ldots U _ { l _ { n } m _ { n } } | \psi \rangle = } \\ & { \frac { 1 } { D ^ { n } } K _ { i _ { 1 } i _ { 2 } \ldots i _ { n } } \delta _ { A _ { 1 } B _ { 1 } } \ldots \delta _ { A _ { n } B _ { n } } U _ { l _ { 1 } m _ { 1 } , i _ { 1 } A _ { 1 } } ^ { * } U _ { l _ { 1 } m _ { 1 } , B _ { 1 } ^ { \prime } B _ { 1 } } \ldots U _ { l _ { n } m _ { n } , i _ { n } A _ { n } } ^ { * } U _ { l _ { n } m _ { n } , B _ { n } ^ { \prime } B _ { n } } | \phi _ { l _ { 1 } m _ { 1 } } \rangle \ldots | \phi _ { l _ { n } m _ { n } } \rangle | B _ { 1 } \ldots B _ { n } \rangle = } \\ & { \frac { 1 } { D ^ { n } } K _ { i _ { 1 } i _ { 2 } \ldots i _ { n } } U _ { l _ { 1 } m _ { 1 } , i _ { 1 } B _ { 1 } } ^ { * } U _ { l _ { 1 } m _ { 1 } , B _ { 1 } ^ { \prime } B _ { 1 } } \ldots U _ { l _ { n } m _ { n } , i _ { n } B _ { n } } ^ { * } U _ { l _ { n } m _ { n } , B _ { n } ^ { \prime } B _ { n } } | \phi _ { l _ { 1 } m _ { n } } \rangle \ldots | \phi _ { l _ { n } m _ { n } } \rangle | B _ { 1 } \ldots B _ { n } \rangle = } \\ & { \frac { 1 } { D ^ { n } } K _ { i _ { 1 } i _ { 2 } \ldots i _ { n } } \delta _ { i _ { 1 } B _ { 1 } ^ { \prime } } \ldots \delta _ { i _ { n } B _ { n } ^ { \prime } } | \phi _ { l _ { 1 } m _ { 1 } } \rangle \ldots | \phi _ { l _ { n } m _ { n } } \rangle | B _ { 1 } ^ { \prime } \ldots B _ { n } ^ { \prime } \rangle = \frac { 1 } { D ^ { n } } K _ { B _ { 1 } ^ { \prime } \ldots B _ { n } ^ { \prime } } | \phi _ { l _ { 1 } m _ { 1 } } \rangle \ldots | \phi _ { l _ { n } m _ { n } } \rangle | B _ { 1 } ^ { \prime } \ldots B _ { n } ^ { \prime } \rangle \quad \quad \mathrm { ~ ( ~ R ' ~ R ' ~ R ' ~ ) } } \end{array}$ (3.8).（20 $\begin{array} { r } { | \varphi _ { B } ^ { \prime } \rangle = \frac { 1 } { D ^ { n } } K _ { B _ { 1 } ^ { \prime } \ldots B _ { n } ^ { \prime } } | B _ { 1 } ^ { \prime } \ldots B _ { n } ^ { \prime } \rangle } \end{array}$ ，即完成了传送.  
值得一提的是， (3.4)与(3.5)的贝尔基和么正变换并非唯一的，只需满足一定的条件，便可完成传送，文献[5]中的定理1对此进行了说明.  
利用[6]中的符号，可以将张量的多个（标量）指标看做一个矢量指标，从而上

述公式简写为：

$\begin{array} { r } { | \psi _ { \mathrm { X } } \rangle = \sum _ { \vec { i } } K _ { \vec { i } } | \vec { i } \rangle \qquad ( 3 . 1 ^ { \prime } ) , ~ | \varphi _ { \mathrm { A B } } \rangle = \sum _ { \vec { A } , \vec { B } } \left( \frac { 1 } { \sqrt { D } } \right) ^ { n } \delta _ { \vec { A } \vec { B } } | \vec { A } \vec { B } \rangle } \end{array}$ (3.2'),$\begin{array} { r } { \vert \psi \rangle = \sum _ { \vec { i } , \vec { A } , \vec { B } } \frac { 1 } { D ^ { n } } K _ { \vec { i } } \delta _ { \vec { A } \vec { B } } U _ { \vec { l } \vec { m } , \vec { i } \vec { A } } ^ { * } \vert \phi _ { \vec { l } \vec { m } } \rangle \vert \vec { B } \rangle } \end{array}$ .其中 $\delta _ { \vec { A } \vec { B } } = \delta _ { A _ { 1 } B _ { 1 } } \ldots \delta _ { A _ { n } B _ { n } }$ ， $| \phi _ { \vec { l } \vec { m } } \rangle =$ （20$| \phi _ { l _ { 1 } m _ { 1 } } \rangle | \phi _ { l _ { 2 } m _ { 2 } } \rangle \ldots | \phi _ { l _ { n } m _ { n } } \rangle , \stackrel { \vec { l } } { i } = ( i _ { 1 } , i _ { 2 } \ldots i _ { n } ) ^ { T } , \stackrel { \vec { n } } { n } = ( n _ { 1 } , n _ { 2 } \ldots n _ { n } ) ^ { T } , \stackrel { \vec { i } } { i } \in [ 0 , D - 1 ] ^ { n } \cap \{ 1 , \ldots , N \} ,$ $\mathbb { N } ^ { n }$ （N是自然数集）．其余的同理．后文中将省略求和符号，将矢量作为哑指标求和的含义是对矢量所有可能的取值代入式中最后相加，

# 4多粒子，多属性

待传送的量子态

$$
\left| \psi _ { X } \right. = K _ { \tilde { X } } \left| \vec { X } \right. = K _ { X _ { I } ^ { 1 } X _ { I } ^ { 2 } \ldots X _ { I } ^ { n _ { I } } X _ { I I } ^ { 1 } X _ { I I } ^ { 2 } \ldots X _ { I I } ^ { n _ { I } } \ldots X _ { N } ^ { 1 } X _ { N } ^ { 2 } \ldots X _ { N } ^ { n _ { N } } } \left| X _ { I } ^ { 1 } X _ { I } ^ { 2 } \ldots X _ { I } ^ { n _ { I } } X _ { I I } ^ { 1 } X _ { I I } ^ { 2 } \ldots X _ { I I } ^ { n _ { I I } } \ldots X _ { N } ^ { 1 } X _ { N } ^ { 2 } \ldots X _ { N } ^ { n _ { N } } \right. ^ { ( 4 ) } .
$$

这个张量的指标 $\overleftrightarrow { X }$ 也是张量，为了区分，用大写字母和罗马数字的组合表示X的指标，指标的下标表示第几行的粒子，指标的上标表示第几个性质．其结构如图所示：

![](images/a7d9468480253a5830d2ee600d677291e1f95897d2d53d557a97ffb618c44f96.jpg)  
图2多粒子多属性结构示意图

例如 $\mathrm { P _ { I I } ^ { 1 } }$ 代表二号粒子的第一个性质，其所在希尔伯特空间的维数是 $D _ { I I } ^ { 1 }$ 其余同理.可以看出 $\overleftrightarrow { X } \in \left( [ 0 , D _ { I } ^ { 1 } - 1 ] \times \ldots \left[ 0 , D _ { I } ^ { n _ { I } } - 1 \right] \right) \times \ldots \left( [ 0 , D _ { N } ^ { 1 } - 1 ] \times \ldots \left[ 0 , D _ { N } ^ { n _ { N } } - 1 \right] \right) .$ 1 $\lfloor \rceil ) \cap \mathbb { N } ^ { n _ { I } + n _ { I I } \ldots + n _ { N } }$ 后文中其他的张量指标也是同理．图中所示结构可以用一句话说明：“异地的粒子相互纠缠，相同的属性相互纠缠”．

$$
\begin{array} { l } { { | \psi \rangle = \mathcal { N } K _ { \vec { X } } \delta _ { \vec { A } , \vec { B } } | \vec { X } \vec { A } \vec { B } \rangle = \frac { 1 } { \sqrt { D _ { I } ^ { 1 } } } \cdots \frac { 1 } { \sqrt { D _ { I } ^ { n _ { I } } } } \frac { 1 } { \sqrt { D _ { I } ^ { 1 } } } \cdots \frac { 1 } { \sqrt { D _ { I I } ^ { n _ { I } } } } \cdots \cdots \frac { 1 } { \sqrt { D _ { N } ^ { n _ { 1 } } } } \cdots \cdots \frac { 1 } { \sqrt { D _ { N } ^ { n _ { 1 } } } } K _ { X _ { I } ^ { 1 } X _ { I } ^ { 2 } , \cdots , X _ { I } ^ { n _ { I } } X _ { I I } ^ { 1 } X _ { I I } ^ { 2 } \cdots X _ { I I } ^ { n _ { I I } } \cdots X _ { N } ^ { 1 } X _ { N } ^ { 2 } \cdots X _ { N } ^ { n _ { N } } } } } \\ { { \delta _ { A _ { I } ^ { 1 } , B _ { I } ^ { 1 } } \delta _ { A _ { I } ^ { 2 } , B _ { I } ^ { 2 } } \cdots \delta _ { A _ { I } ^ { n _ { I } } , B _ { I } ^ { n _ { I } } } \cdots \delta _ { A _ { N } ^ { 1 } , B _ { N } ^ { 1 } } \cdots \delta _ { A _ { N } ^ { n _ { N } } , B _ { N } ^ { n _ { N } } } } } \\  { | X _ { I } ^ { 1 } X _ { I } ^ { 2 } \cdots X _ { I } ^ { n _ { I } } X _ { I I } ^ { 1 } X _ { I I } ^ { 2 } \cdots X _ { I I } ^ { n _ { I I } } \underbrace { \cdots X _ { N } ^ { 1 } X _ { N } ^ { 2 } } _ { \cdots } X _ { N } ^ { 1 } X _ { N } ^ { 2 } \cdots \tilde { X } _ { N } ^ { n _ { N } } A _ { I } ^ { 1 } B _ { I } ^ { 1 } \underbrace { \cdots \tilde { 1 } _ { N } } _ { \cdots } A _ { N } ^ { 1 } B _ { N } ^ { 1 } \underbrace { \cdots } _ { \mathrm { N } } \cdots \underbrace { \tilde { 1 } _ { N } ^ { n _ { N } } } _ { \mathrm { N } } \delta _ { X _ { I } ^ { 1 } X _ { I } ^ { 2 } \cdots \tilde { A } _ { N } ^ { n _ { N } } B _ { N } ^ { n _ { N } } } \rangle \qquad ( 4 . 1 ) . } \end{array}
$$

其中 $\pmb { \mathcal { N } }$ 是归一化系数

同样地，将(3.7)式代入，我们得到：

$$
| \psi \rangle = \mathcal { N } K _ { \underset { \Vec { X } } {  } } \delta _ { \Vec { A } , \vec { B } } \big | \overleftrightarrow { X } \overleftrightarrow { A } \big \rangle = \mathcal { N } ^ { \prime } K _ { \underset { \Vec { X } } {  } } \delta _ { \underset { A , \vec { B } } {  } } U _ { \underset { \Vec { l m } , \underset { \Vec { X } } {  } } { * }  | \phi _ { \Vec { l m } } } \rangle \big | \overleftrightarrow { B } \rangle
$$

$$
\begin{array} { r } { | \Psi \rangle = \frac { 1 } { \sqrt { D _ { I } ^ { 1 } } } \cdots \frac { 1 } { \sqrt { D _ { I } ^ { n _ { I } } } } \frac { 1 } { \sqrt { D _ { I I } ^ { 1 } } } \cdots \frac { 1 } { \sqrt { D _ { I I } ^ { n _ { I I } } } } \cdots \frac { 1 } { \sqrt { D _ { N } ^ { 1 } } } \cdots \frac { 1 } { \sqrt { D _ { N } ^ { n _ { N } } } } K _ { X _ { I } ^ { 1 } X _ { I } ^ { 2 } . . . X _ { I } ^ { n _ { I } } X _ { I I } ^ { 1 } X _ { I I } ^ { 2 } . . . X _ { I I } ^ { n _ { I I } } \cdots X _ { N } ^ { 1 } X _ { N } ^ { 2 } . . . X _ { N } ^ { n _ { N } } } } \end{array}
$$

$$
\begin{array} { r l } & { \delta _ { A _ { I } ^ { 1 } , B _ { I } ^ { 1 } } \delta _ { A _ { I } ^ { 2 } , B _ { I } ^ { 2 } } \dots \delta _ { A _ { I } ^ { n _ { I } } , B _ { I } ^ { n _ { I } } } \dots \delta _ { A _ { N } ^ { 1 } , B _ { N } ^ { 1 } } \dots \delta _ { A _ { N } ^ { n _ { N } } , B _ { N } ^ { n _ { N } } } } \\ & { U _ { l _ { I } ^ { 1 } m _ { I } ^ { 1 } , X _ { I } ^ { 1 } A _ { I } ^ { 1 } } ^ { * } \dots U _ { l _ { I } ^ { n _ { I } } m _ { I } ^ { n _ { I } } , X _ { I } ^ { n _ { I } } A _ { I } ^ { n _ { I } } } ^ { * } \dots U _ { l _ { I } ^ { 1 } m _ { I I } ^ { 1 } , X _ { I I } ^ { 1 } A _ { I I } ^ { 1 } } ^ { * } \dots U _ { l _ { N } ^ { 1 } m _ { N } ^ { 1 } , X _ { N } ^ { 1 } A _ { N } ^ { 1 } } ^ { * } \dots U _ { l _ { N } ^ { n _ { N } } m _ { N } ^ { n _ { N } } , X _ { N } ^ { n _ { N } } A _ { N } ^ { n _ { N } } } ^ { * } } \\ & { | \phi _ { l _ { I } ^ { 1 } m _ { I } ^ { 1 } } \rangle \dots | \phi _ { l _ { I } ^ { n _ { I } } m _ { I } ^ { n _ { I } } } \rangle | \phi _ { l _ { I I } ^ { 1 } m _ { I I } ^ { 1 } } \rangle \dots | \phi _ { l _ { N } ^ { 1 } m _ { N } ^ { 1 } } \rangle | \phi _ { l _ { N } ^ { n _ { N } } m _ { N } ^ { n _ { N } } } \rangle | B _ { I } ^ { 1 } B _ { I } ^ { 2 } \dots B _ { I } ^ { n _ { I } } B _ { I I } ^ { 1 } B _ { I I } ^ { 2 } \dots B _ { I I } ^ { n _ { I } } \dots B _ { N } ^ { 1 } B _ { N } ^ { 2 } \dots B _ { N } ^ { n _ { N } } \rangle } \end{array}
$$

下面Alice 需要对X组粒子和A组粒子按一定的关系分别作超贝尔基测量，与图2中的下图一致： $X _ { I } ^ { 1 } A _ { I } ^ { 1 }$ ， $X _ { I } ^ { n _ { I } } A _ { I } ^ { n _ { I } } . . . X _ { I I } ^ { 1 } A _ { I I } ^ { 1 } . . . X _ { N } ^ { 1 } A _ { N } ^ { 1 } . . . X _ { N } ^ { n _ { N } } A _ { N } ^ { n _ { N } }$ ．会依次得到共 $n _ { I } \cdot n _ { I I } \dots n _ { N }$ 组整数对： $l _ { I } ^ { 1 } m _ { I } ^ { 1 } . . . l _ { I } ^ { n _ { I } } m _ { I } ^ { n _ { I } } , l _ { I I } ^ { 1 } m _ { I I } ^ { 1 } . . . l _ { I I } ^ { n _ { I I } } m _ { I I } ^ { n _ { I I } } . . . l _ { N } ^ { 1 } m _ { N } ^ { 1 } . . . l _ { N } ^ { n _ { N } } m _ { N } ^ { n _ { N } }$ .与前文相同，Alice 将这些有序数对，也就是将两个张量 $\overleftarrow { l }$ 和㎡以经典的形式发送给Bob，Bob对他所持有的各粒子做一系列幺正变换：  
$U _ { \vec { l } \vec { m } } | \psi \rangle = \mathcal { N } ^ { \prime } K _ { \vec { X } } \delta _ { \vec { A } , \vec { B } } U _ { \vec { l } \vec { m } , \vec { B } ^ { \prime } \vec { B } } U _ { \vec { l } \vec { m } , \vec { X } \vec { A } } ^ { * } | \phi _ { \vec { l } \vec { m } } \rangle | \vec { B } \rangle = \mathcal { N } ^ { \prime } K _ { \vec { X } } U _ { \vec { l } \vec { m } , \vec { B } ^ { \prime } \vec { B } } U _ { \vec { l } \vec { m } , \vec { X } \vec { B } } ^ { * } | \phi _ { \vec { l } \vec { m } } \rangle | \vec { B } \rangle = \delta ^ { \prime } \mathcal { N } ^ { \prime } K _ { \vec { X } } \delta _ { \vec { X } } \delta _ { \vec { B } ^ { \prime } \vec { B } } ^ { * } | \phi _ { \vec { l } \vec { m } , \vec { X } \vec { B } } ^ { * } | \phi _ { \vec { l } \vec { m } } \rangle | \vec { B } \rangle = \delta ^ { \prime } \mathcal { N } ^ { \prime } \langle \vec { l } _ { \vec { m } } , \vec { B } ^ { \prime } | \phi _ { \vec { X } } \rangle ,$ （20$\mathcal { N } ^ { \prime } K _ { \underset { X } {  } } \delta _ { \underset { X , B ^ { \prime } } {  } } | \phi \rangle \big | \overset {  } { B } ^ { \prime } \big \rangle = \mathcal { N } ^ { \prime } K _ { \underset { B ^ { \prime } } {  } } | \phi _ { \underset { l m } } \rangle \big | \overset {  } { B } ^ { \prime } \big \rangle$ ，至此， $\mathrm { \Delta } _ { X }$ 组粒子的所有属性，已被按照一定的顺序依次传给了B组粒子．张量的分量展开式为：  
$\begin{array} { r l } &  U _ { i _ { 1 } ^ { \prime } m _ { 1 } ^ { \prime } } : = U _ { i _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } m _ { 1 } ^ { \prime } } ^ { \prime } \ldots U _ { i _ { 1 } ^ { \prime } m _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } } \ldots U _ { i _ { 1 } ^ { \prime } m _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } m _ { 1 } ^ { \prime } } \ldots U _ { i _ { 1 } ^ { \prime } ^ { \prime } n _ { 1 } ^ { \prime } m _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } } \ldots U _ { i _ { 1 } ^ { \prime } ^ { \prime } n _ { 1 } ^ { \prime } m _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } } \ldots U _ { i _ { 1 } ^ { \prime } ^ { \prime } n _ { 1 } ^ { \prime } } \delta ( \delta _ { i _ { 1 } ^ { \prime } ^ { \prime } } \ldots \delta _ { i _ { 1 } ^ { \prime } ^ { \prime } n _ { 1 } ^ { \prime } } \delta _ { i _ { 1 } ^ { \prime } ^ { \prime } } \ldots \delta _ { i _ { 1 } ^ { \prime } ^ { \prime } n _ { 1 } ^ { \prime } } \ldots \delta _ { i _ { 1 } ^ { \prime } ^ { \prime } n _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } } \ldots \delta _ { i _ { 1 } ^ { \prime } ^ { \prime } n _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } } \ldots \delta _ { i _ { 1 } ^ { \prime } ^ { \prime } n _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } } \ldots \delta _ { i _ { 1 } ^ { \prime } ^ { \prime } n _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } } \ldots \delta _ { i _ { 1 } ^ { \prime } ^ { \prime } n _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } } \ldots \delta _ { i _ { 1 } ^ { \prime } ^ { \prime } n _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } } \ldots \delta _ { i _ { 1 } ^ { \prime } ^ { \prime } n _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } } \ldots \delta _ { i _ { 1 } ^ { \prime } ^ { \prime } n _ { 1 } ^ { \prime } } \delta ( \delta _ { i _ { 1 } ^ { \prime } } \ldots \delta _ { i _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } } \ldots \delta _  i _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } m _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } n _ { 1 } ^ { \prime } \ldots \delta _  i  \end{array}$

# 5混合态

一个密度矩阵 $\begin{array} { r } { { \hat { \rho } } = \sum _ { i } | \psi _ { i } \rangle \langle \psi _ { i } | } \end{array}$ 在一个确定表象下的张量表示可以记作

$$
\hat { \rho } = \rho _ { i _ { 1 } i _ { 2 } \ldots i _ { n } , i _ { 1 } ^ { \prime } i _ { 2 } ^ { \prime } \ldots i _ { n } ^ { \prime } } | i _ { 1 } i _ { 2 } \ldots i _ { n } \rangle \langle i _ { 1 } ^ { \prime } i _ { 2 } ^ { \prime } \ldots i _ { n } ^ { \prime } | = \rho _ { \vec { i } , \vec { i } ^ { \prime } } | \vec { i } \rangle \langle \vec { i } ^ { \prime } |
$$

众所周知，一个密度矩阵必须满足一些性质：

i.厄米性，Pii.ini.in =Pi.ini.in;

ii. 迹等于1, $\begin{array} { r } { \sum _ { i } \rho _ { \underbrace { i i \dots i } _ { 2 n \wedge i } } = 1 \qquad } \end{array}$

ii.半正定性， $C _ { i _ { 1 } i _ { 2 } \ldots i _ { n } } ^ { * } \rho _ { i _ { 1 } i _ { 2 } \ldots i _ { n } , i _ { 1 } ^ { \prime } i _ { 2 } ^ { \prime } \ldots i _ { n } ^ { \prime } } C _ { i _ { 1 } i _ { 2 } \ldots i _ { n } } \geq 0 ,$ ，其中 $\forall C _ { i _ { 1 } i _ { 2 } \ldots i _ { n } } \in \mathbb { C }$

与此同时，我们有 $\begin{array} { r } { | \phi ^ { + } \rangle \langle \phi ^ { + } | = \frac { 1 } { \mathrm { D } } \delta _ { i j } \delta _ { i ^ { \prime } j ^ { \prime } } | i j \rangle \langle i ^ { \prime } j ^ { \prime } | } \end{array}$ ，做张量积得:

$$
\begin{array} { r } { \hat { P } = \frac { 1 } { D ^ { n } } \rho _ { i _ { 1 } i _ { 2 } . . . i _ { n } , i _ { 1 } ^ { \prime } i _ { 2 } ^ { \prime } . . . i _ { n } ^ { \prime } } \delta _ { j _ { 1 } k _ { 1 } } \delta _ { j _ { 1 } ^ { \prime } k _ { 1 } ^ { \prime } } \dots \delta _ { j _ { n } k _ { n } } \delta _ { j _ { n } ^ { \prime } k _ { n } ^ { \prime } } | i _ { 1 } i _ { 2 } \dots i _ { n } j _ { 1 } k _ { 1 } \dots j _ { n } k _ { n } \rangle \langle i _ { 1 } ^ { \prime } i _ { 2 } ^ { \prime } \dots i _ { n } ^ { \prime } j _ { 1 } ^ { \prime } k _ { 1 } ^ { \prime } \dots j _ { n } ^ { \prime } k _ { n } ^ { \prime } | } \end{array}
$$

$$
\begin{array} { r } { = \frac { 1 } { D ^ { n } } \rho _ { \vec { i } , \vec { i } } \delta _ { \vec { j } \vec { k } } \delta _ { \vec { j } ^ { \prime } \vec { k } ^ { \prime } } | \vec { i } \vec { j } \vec { k } \rangle \langle \vec { i } ^ { \prime } \vec { j } ^ { \prime } \vec { k } ^ { \prime } | } \end{array}
$$

将(3.7)代入得 $\begin{array} { r } { \hat { P } = \frac { 1 } { D ^ { 3 n } } \rho _ { \vec { i } , \vec { i } } \delta _ { \vec { j } \vec { k } } \delta _ { \vec { j } ^ { \prime } \vec { k } ^ { \prime } } U _ { \vec { l } \vec { m } , \vec { i } \vec { j } } ^ { * } U _ { \vec { l } ^ { \prime } \vec { m } ^ { \prime } , \vec { i } ^ { \prime } \vec { j } ^ { \prime } } \left( \big ( | \phi _ { \vec { l } \vec { m } } \rangle \big \langle | \phi _ { \vec { l } ^ { \prime } \vec { m } ^ { \prime } } | \big ) \otimes \big | \vec { k } \rangle \big \langle \vec { k } ^ { \prime } \big | \right. } \end{array}$ 由厄 米性知

$\vec { l } = \vec { l } ^ { \prime } , \overrightarrow { m } = \overrightarrow { m } ^ { \prime }$ 所以

$$
\hat { P } = \frac { 1 } { D ^ { 3 n } } \rho _ { \vec { i } , \vec { i } } \delta _ { \vec { j } \vec { k } } \delta _ { \vec { j } ^ { \prime } \vec { k } ^ { \prime } } U _ { \vec { i } \vec { m } , \vec { i } \vec { j } } ^ { * } U _ { \vec { i } \vec { m } , \vec { i } ^ { \prime } \vec { j } ^ { \prime } } ( ( | \phi _ { \vec { i } \vec { m } } \rangle \langle \phi _ { \vec { i } \vec { m } } | ) \otimes | \vec { k } \rangle \langle \vec { k } ^ { \prime } |
$$

之后仍然是Alice对AB处的混合态按图1的顺序做超贝尔基测量，将所得 $\overrightarrow { l m }$ 发送给Bob，Bob对他所持系综按其对应的指标做幺正变换：

$$
\begin{array} { l } { { \displaystyle U _ { \mathit { i } \overrightarrow { m } } \hat { P } { \cal U } _ { \mathit { i } \overrightarrow { m } } ^ { \dagger } = \frac { 1 } { D ^ { 3 n } } \rho _ { \mathit { i } \overrightarrow { i } , { \bf i } } \delta _ { \mathit { j } \overrightarrow { k } } \delta _ { \ j ^ { \prime } \overrightarrow { k } } { \cal U } _ { \mathit { i } \overrightarrow { m } , { \vec { i } } \overrightarrow { r } } { \cal U } _ { \mathit { i } \overrightarrow { m } , { \vec { i } } \overrightarrow { r } } { \cal U } _ { \mathit { i } \overrightarrow { m } , { \vec { i } } { \vec { j } ^ { \prime } } } { \cal U } _ { \mathit { i } \overrightarrow { m } , { \vec { i } } { \vec { r } } ^ { * } } ^ { * } { \cal U } _ { \mathit { i } \overrightarrow { m } , { \vec { i } } { \vec { r } } ^ { * } } ^ { * } ( ( | \phi _ { \mathit { i } \overrightarrow { m } } \rangle \langle \phi _ { \mathit { i } \overrightarrow { m } } \rangle \langle \phi _ { \mathit { i } \overrightarrow { m } } \rangle    } }  \\  { \displaystyle   = \frac { 1 } { D ^ { 3 n } } \rho _ { \mathit { i } , { \vec { i } } } { \cal U } _ { \mathit { i } \overrightarrow { m } , { \vec { i } } { \vec { r } } } { \cal U } _ { \mathit { i } \overrightarrow { m } , { \vec { i } } { \vec { k } } } ^ { * } { \cal U } _ { \mathit { i } \overrightarrow { m } , { \vec { i } } { \vec { k } } } { \cal U } _ { \mathit { i } \overrightarrow { m } , { \vec { i } } { \vec { k } } ^ { * } } { \cal U } _ { \mathit { i } \overrightarrow { m } , { \vec { i } } { \vec { r } } ^ { * } } ^ { * } ( ( | \phi _ { \mathit { i } \overrightarrow { m } } \rangle  \phi _ { \mathit { i } \overrightarrow { m } } | ) \otimes | \vec { k } \rangle \langle \vec { k } ^ { * } |   } \\ { \displaystyle   = \frac { 1 } { D ^ { 3 n } } ( ( | \phi _ { \mathit { i } \overrightarrow { m } } \rangle \langle \phi _ { \mathit { i } \overrightarrow { m } } | ) \otimes ( \rho _ { \vec { r } , \vec { r } ^ { \prime } } | \vec { r } \rangle \langle \vec { r } ^ { \prime } | ) \qquad ( 6 . 3 )  } \end{array}
$$

$\hat { \rho } _ { B } ^ { \prime } = \rho _ { \vec { r } , \vec { r } ^ { \prime } } | \vec { r } \rangle \langle \vec { r } ^ { \prime } |$ ，这样整个混合态 $\hat { \rho }$ 便传给了Bob.

第5节已经说明了多粒子多属性和单粒子多属性以及多粒子单属性之间只是总态矢所在希尔伯特空间结构的区别。不失一般性地，这里使用矢量指标，相当于只考虑多粒子单属性的情况，若想推广只需将矢量指标替换为张量指标

# 参考文献：

[1] Bennett，C. H. et al. Teleporting an unknown quantum state via dual classic and Einstein-Podolsky-Rosen channels [J]．Phys. Rev. Lett，1993,70(13):1895-1899.   
[2] Li Da-Chuang et al. Teleportation of Two-Particle Entangled State via Cluster State [J]. Commun．Theor．Phys,2007,47(3):464-466.   
[3] Wang X L，Cai X D,Su Z E,et al. Quantum teleportation of multiple degrees of freedom of a single photon [J]. Nature,2015,518(7540):516-519.   
[4] Zwiebach Barton. Quantum Physics II [EB/OL]． (2013).   
https://ocw. mit. edu/courses/physics/8-05-quantum-physics-ii-fall-2013/.   
[5] Albeverio S et al. Quantum Teleportation: from Pure to Mixed States and Standard to Optimal[J].Gender Work & Organization,2003,12(6):551-571.   
[6] Harrow Aram. Quantum Physics III [EB/OL]． (2016).   
https://ocw. mit.edu/courses/physics/8-06-quantum-physics-iii-spring-2016/   
[7] Yu Chang-Shui et al. Teleportation of Mixed States and Multipartite Quantum States[J]. Commun．Theor.Phys,2007,47(6):1041-1044.