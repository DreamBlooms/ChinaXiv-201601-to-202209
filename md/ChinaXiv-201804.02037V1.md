# 基于 $d$ 维纠缠交换的 $( t , n )$ 门限量子秘密共享

宋秀丽，徐建坤，周道洋

(重庆邮电大学 网络信息安全技术重庆市重点工程实验室，重庆 400065)

摘要：以 $d$ 维纠缠交换为技术手段，提出了一个 $( t , n )$ 门限量子秘密共享方案。该方案执行t次 $d$ 维纠缠交换，秘密影子聚合于重建者的 $\boldsymbol { V _ { 1 } }$ 粒子中。重建者测量该粒子，可重建出共享的秘密。安全性分析可知，提出的方案，能抵抗截获-重发攻击、纠缠-测量攻击、合谋攻击和伪造攻击。性能比较分析表明，相比较于其他现有类似量子秘密共享方案，提出的方案具有更好的灵活性、实用性和普适性。而且总的计算和测量所花费的开销是最低的。

关键词： $d$ 维Hilbert空间； $( t , n )$ 门限；纠缠交换；量子秘密共享；投影测量 中图分类号：TP309.2 doi:10.3969/j.issn.1001-3695.2017.12.0758

# $( t , n )$ threshold quantum secret sharing based on $d$ -dimensional entanglement swapping

Song Xiuli†, Xu Jiankun, Zhou Daoyang (ChongqingKeyLaboratoryofNetworkInformationSecurityTechnology,Chongqing UniversityofPosts&Telecommunications, Chongqing 400065, China)

Abstract: This paper proposed a $( t , n )$ threshold quantum secret sharing scheme by means of $d$ -dimensional entanglement swapping. The proposed scheme has executed $t$ times of $d$ -dimensional entanglement swapping，which aggregates secret shadows into $V _ { 1 }$ particle of the reconstructor.Finally, the reconstructor measures this particle to reconstruct the original secret. Securityanalysissows thatthe proposedschemecanresistintercept-resend,entangle-measure,colusionandforgeryacks. Bycomparison withother similar schemes in performance,the proposed scheme is more flexible,practical and universal.In addition,its total overheadsofcomputationand measurement are lowest in currnt similarquantumsecret sharing schemes.

Key words: $d$ -dimensional Hilbert space; $( t , ~ n )$ threshold; entanglement swapping; quantum secret sharing; projection measurement

# 0 引言

在某些场合，为了让多人承担保护秘密消息的风险，或者加强对某个秘密消息的保密强度，需要多个参与者共同参与保护这个秘密消息。解决这个问题常用的技术是经典秘密共享。经典秘密共享将一个秘密消息拆分成若干个秘密份额，并将这些秘密份额分发给若干个参与者，由这些参与者共同管理，只有若干个参与者一起合作才能恢复出秘密消息。由于经典秘密共享很难克服秘密份额在经典公共信道传输过程中被窃听的问题，于是1999 年，Hillery 等人[1]将经典秘密共享扩展到量子世界中。在该方案中，秘密份额可在量子信道中分发给参与者，克服了经典秘密共享的安全缺陷。

此后，许多量子秘密共享方案 $[ 2 \sim 2 0 ]$ 被提出。在这些方案中，文献[2\~7,11,13\~16,19]是 $( n , n )$ 的量子秘密共享方案。它们必须$n$ 个参与者同时到场，一起合作才能恢复出秘密,现实生活中，有可能一个或多个参与者生病、出差等特殊情况不能到场，此时，共享的秘密无法恢复。文献[2\~5,8\~9,11\~12,14\~20]是2维量子秘密共享方案，它们制备的量子态都处在2维希尔伯特空间，如果将这些方案置于比2更高维的量子通信环境中，它们无法直接运行，需要进行维度的转换。文献[8\~9,12,17\~18,20]是 $( t , n )$ 的量子秘密共享方案，只需要 $t$ 个或大于 $t$ 个参与者就能恢复出秘密，但它们制备的量子态是处在2维希尔伯特空间。文献[6,7,13]是 $d$ 0 $( d > 2 )$ 维量子秘密共享方案，但它们是 $( n , n )$ 门限。文献[5,13]在秘密重构阶段应用纠缠交换实现隐形传输，份额没有量子信道中传输，但文献[5]是2维的(3,3)门限方案，文献[13]是 $d$ 维的 $( n , n )$ 门限方案。

为了突破Hilbert空间2维度的局限性，解决某些参与者无法到场重建共享秘密的问题，本文提出了一种 $d$ 维 $( t , n )$ 门限量子秘密共享方案，克服了上述方案的局限性。该方案将秘密影子加入到投影测量算子的相位中，当选择的 $\mathbf { \Phi } _ { t }$ 个参与者都执行完投影测量，复合系统发生 $\mathbf { \Phi } _ { t }$ 次 $d$ 维纠缠交换，秘密影子聚合于重建者 $B o b _ { 1 }$ 的 $V _ { 1 }$ 粒子中，测量该粒子，恢复出共享的秘密消息。与上述方案相比，提出的方案的主要贡献体现在：a)它制备的量子态处在 $d$ $( d > 2 )$ 维希尔伯特空间中，当量子环境是自由空间时，它比2 维量子秘密共享具有更好的普适性;b)它以 $\mathbf { \Psi } _ { t }$ $( t \leq n )$ 为门限值，与 $( n , n )$ 门限量子秘密共享相比，具有更好的灵活性和实用性;c)它在秘密重构阶段使用纠缠交换实现份额隐形传输，这些份额并没有在量子信道中传输，比那些将经典份额或量子份额在量子信道中传输的方案，具有更高的安全性。

# 1提出的 $d$ 维 $( t , n )$ 门限量子秘密共享方案

在提出的方案中，Alice是受信的秘密分发者，$B _ { n } = \{ B o b _ { 1 } , B o b _ { 2 } , \cdots , B o b _ { n } \}$ 是 $n$ 个参与者的集合，Alice 从其中选择 $B o b _ { 1 }$ 作为可信任的重建者。 $B o b _ { 1 }$ 的职责是从 $n$ 个参与者持有的份额中收集任意 $\mathbf { \Phi } _ { t }$ 个份额，然后重建出原始的秘密信息。提出的的 $d$ 维 $( t , n )$ 门限量子秘密共享方案由四个阶段组成：份额分发阶段，粒子制备阶段，纠缠交换阶段，秘密重建阶段。

# 1.1 份额分发阶段

本阶段，受信的秘密分发者Alice生成 $n$ 个秘密份额发送给 $n$ 个参与者，并将共享秘密的 hash 值发给重建者 $B o b _ { \scriptscriptstyle 1 }$ 。

a）Alice 寻找一个合适素数 $d$ ，满足 $n \leq d \leq 2 n$ （因为需要$n$ 个不同的非零整数，再加上 $2 n$ 维空间的限制是对粒子制备的复杂度的限制)。并在 $G F ( d )$ 域上随机生成一个 $_ { t - 1 }$ 次多项式$f ( x ) = a _ { 0 } + a _ { 1 } x + a _ { 2 } x ^ { 2 } + \cdots + a _ { t - 1 } x ^ { t - 1 }$ ，其中 $\left( a _ { 0 } , a _ { 1 } , a _ { 2 } , \cdots , a _ { t - 1 } \right) \in Z _ { d } ^ { t }$ ，$a _ { 0 }$ 是秘密消息。Alice 再选择 $n$ 个互不相等且非零整数x(i=1,2,,n),并公布x。她以x为参数计算n个秘密份额$f ( x _ { i } )$ ，并通过安全的量子信道将它们发送给 $n$ 个参与者，每个参与者 $B o b _ { i }$ 手中持有一个秘密份额 $f ( x _ { i } )$ 。虽然每个秘密份额$f ( x _ { i } )$ 为参与者 $B o b _ { i }$ 本地所持有，但是其中任意 $\mathbf { \Phi } _ { t }$ 个秘密份额{f(x),f(x),,f(x)}在GF(d)域上满足下面关系

$$
a _ { 0 } = f ( 0 ) = \sum _ { r = 1 } ^ { t } f ( x _ { r } ) \prod _ { 1 \leq b \leq t , b \neq r } { \frac { x _ { b } } { x _ { b } - x _ { r } } } { \bmod { d } } \circ
$$

b)Alice 使用公开的hash 算法(如 SHA-256),计算 hash(ao），也通过安全的量子信道把它发送给参与者 Bob。

# 1.2粒子制备阶段

在 $n$ 个参与者中，假定临时到场的参与者集合为B={Bob,Bob,,Bob,}。其中，Bob既是粒子的制备者，也是可信的重建者。粒子制备阶段步骤如下：

a) $B o b _ { 1 }$ 制备 $\mathbf { \Phi } _ { t }$ 个 $d$ 维单粒子 $\{ \left| u _ { 1 } \right. _ { U _ { 1 } } , \left| u _ { 2 } \right. _ { U _ { 2 } } , \cdots , \left| u _ { t } \right. _ { U _ { t } } \}$ ，其中，$\boldsymbol { u } _ { r }$ 表示第 $\boldsymbol { r } \big ( r = 1 , 2 , \cdots , t \big )$ 粒子的取值， $U _ { \scriptscriptstyle r }$ 表示第 $\boldsymbol { r } \big ( r = 1 , 2 , \cdots , t \big )$ 个粒子的标签。

b） $B o b _ { 1 }$ 对 $U _ { 1 }$ 粒子 $\left| u _ { 1 } \right. _ { U _ { 1 } }$ 作 $d$ 维哈达门变换 $\boldsymbol { H } _ { d }$ ，则 $\mathbf { \Phi } _ { t }$ 个粒子 $\{ \left| u _ { 1 } \right. _ { U _ { 1 } } , \left| u _ { 2 } \right. _ { U _ { 2 } } , \cdots , \left| u _ { t } \right. _ { U _ { t } } \}$ 组成了一个的复合系统态 $\left| { { \varphi _ { \mathrm { { 1 } } } } } \right.$

$$
\begin{array} { c } { { \displaystyle { \left| \varphi _ { _ 1 } \right. = \left( H _ { _ d } \left| u _ { _ 1 } \right. _ { U _ { _ 1 } } \right) \left| u _ { _ 2 } \right. _ { U _ { _ 2 } } \left| u _ { 3 } \right. _ { U _ { 3 } } \cdots \left| u _ { t } \right. _ { U _ { t } } } } } \\ { { { } } } \\ { { = \displaystyle { \left( \frac { 1 } { \sqrt d } \sum _ { q = 0 } ^ { d - 1 } \zeta ^ { q u _ { _ 1 } } \left| q \right. _ { U _ { _ 1 } } \right) \left| u _ { 2 } \right. _ { U _ { _ { 2 } } } \left| u _ { 3 } \right. _ { U _ { 3 } } \cdots \left| u _ { t } \right. _ { U _ { t } } } ~ , } } \end{array}
$$

其中 $\scriptstyle \zeta = e ^ { 2 \pi i / d }$ ， $H _ { d } = \frac { 1 } { \sqrt { d } } \sum _ { q , u = 0 } ^ { d - 1 } \zeta ^ { q u } | q \rangle \langle u |$ 0

c） $B o b _ { 1 }$ 以 $( H _ { d } \big | u _ { 1 } ) _ { U _ { 1 } } )$ 作为控制粒子， $\left| u _ { j } \right. _ { U _ { j } } ( j = 2 , 3 , \cdots , t )$ 作为目标粒子来进行 $d$ 维CNOT门 $R _ { c }$ 运算。经过 $\left( t - 1 \right)$ 个 $R _ { c }$ 门运算后复合系统态 $\left| { { \varphi _ { 1 } } } \right.$ 演变为纠缠态 $\left| { \varphi _ { _ { 2 } } } \right.$ ，如图1所示[21]。

$$
\begin{array} { l } { { \displaystyle \left. \varphi _ { { } _ { 2 } } \right. = \left( \begin{array} { l } { { t } } \\ { { \otimes } } \\ { { j = 2 } } \end{array} { R _ { c } } \left( \boldsymbol { H } _ { d } \left. \boldsymbol { u } _ { 1 } \right. _ { U _ { 1 } } , \left. \boldsymbol { u } _ { j } \right. _ { U _ { j } } \right) \right) \left. \varphi _ { 1 } \right. } } \\ { { \displaystyle \qquad = \frac { 1 } { \sqrt { d } } \sum _ { q = 0 } ^ { d - 1 } \zeta ^ { q u _ { 1 } } \left. \boldsymbol { q } \right. _ { U _ { 1 } } \left. \boldsymbol { u } _ { 2 } + \boldsymbol { q } \right. _ { U _ { 2 } } \left. \boldsymbol { u } _ { 3 } + \boldsymbol { q } \right. _ { U _ { 3 } } \cdots \left. \boldsymbol { u } _ { t } + \boldsymbol { q } \right. _ { U _ { t } } } } \end{array}
$$

$$
\qquad = \left| \psi _ { \boldsymbol { \imath } } \left( u _ { \boldsymbol { \imath } } , u _ { \boldsymbol { \imath } _ { 2 } } , \cdots , u _ { t } \right) \right. _ { U _ { 1 } , U _ { 2 } , \cdots , U _ { t } } ,
$$

其中: $d$ 维 CNOT门 $R _ { c }$ 满足条件： $R _ { c } | u , q \rangle = | u , u + q \rangle$ 。

![](images/611b134070b29ec400f7b2e097e6e3562b546419775ab6949f4a9e6a70d7fd8f.jpg)  
图1纠缠态|y(uu.,u,uu

d） $B o b _ { \scriptscriptstyle 1 }$ 通过授权的安全量子信道将纠缠态|o(u,u..,u)u.U. 的第 $U _ { j } \left( j = 2 , 3 , \cdots , t \right)$ 个粒子分别发送给相应的参与者Bobj。

e)当 $B o b _ { j } \big ( j = 2 , 3 , \cdots , t \big )$ 收到从 $B o b _ { 1 }$ 发来的粒子后，集合 $B _ { t }$ （204号中每个参与者 $B o b _ { r } \big ( r = 1 , 2 , \cdots , t \big )$ 取出其持有的秘密份额 $f ( x _ { r } )$ ，计算秘密影子s,：

$$
s _ { r } = f ( x _ { r } ) \prod _ { 1 \leq b \leq t , b \neq r } \frac { x _ { b } } { x _ { b } - x _ { r } } \mathrm { m o d } d \circ
$$

f）每个参与者 $B o b _ { r } \left( r = 1 , 2 , \cdots , t \right)$ 制备一个 $d$ 维两粒子纠缠态 $\left| \psi \left( \nu _ { r } , \nu _ { r } ^ { \cdot } \right) \right. _ { V _ { 1 } , V _ { 2 } }$ ，如图2 所示。其中,

$$
\left| \psi \left( \nu _ { r } , \dot { \nu _ { r } } \right) \right. _ { V _ { r } , V _ { r } ^ { ' } } = \frac { 1 } { \sqrt { d } } \sum _ { q = 0 } ^ { d - 1 } \zeta ^ { q \nu _ { r } } \left| q \right. _ { V _ { r } } \left| q + \nu _ { r } ^ { ' } \right. _ { V _ { r } ^ { ' } } \ : \ : \bullet
$$

![](images/b3c54aadb095f474d82e3a1b405d8facf19eccfff6410e32a0ea2a22a315d25f.jpg)  
图2纠缠交换前的粒子分布图

# 1.3 纠缠交换阶段

参与者 $B o b _ { 1 }$ 使用投影算子对自己持有的粒子 $\left( U _ { 1 } , V _ { 1 } ^ { ' } \right)$ 进行投影测量，每个参与者 $B o b _ { j } \left( j = 2 , 3 , \cdots , t \right)$ 依次使用投影算子对自己持有的粒子 $\left( V _ { r } , U _ { r } \right)$ 进行投影测量。当所有参与者B,={Bob,Bob,,Bob}测量完毕，复合系统发生t次d维纠缠交换，秘密影子聚合于重建者 $B o b _ { 1 }$ 的 $V _ { \mathrm { 1 } }$ 粒子相位中。具体步骤如下：

a) $B o b _ { 1 }$ 使用投影算子 $\left| \psi \left( u _ { 1 } - s _ { 1 } , \dot { \nu _ { 1 } } \right) \right. \left. \psi \left( u _ { 1 } - s _ { 1 } , \dot { \nu _ { 1 } } \right) \right|$ 对持有的粒子 $\left( U _ { 1 } , V _ { 1 } ^ { ' } \right)$ 进行投影测量,测量的结果为 $\left| \psi \big ( u _ { 1 } - s _ { 1 } , \nu _ { 1 } ^ { ' } \big ) \right.$ 。另外的 $\mathbf { \chi } _ { t }$ 个粒子 $\left( V _ { 1 } , U _ { 2 } , \cdots , U _ { t } \right)$ 坍塌到 $\left| \psi _ { 1 } { \left( \nu _ { 1 } + s _ { 1 } , u _ { 2 } , \cdots , u _ { t } \right) } \right. _ { V _ { 1 } , U _ { 2 } , \cdots , U _ { t } }$ 为了描述方便，后续坍塌态都省略了前面的相位因子)。

这是因为由 $t \cdot$ 纠缠粒子 $\left( \boldsymbol { U } _ { 1 } , \boldsymbol { U } _ { 2 } , \cdots , \boldsymbol { U } _ { t } \right)$ 和2-纠缠粒子 $( V _ { 1 } , V _ { 1 } ^ { ' } )$ 组成的混合系统 $\left| \Psi _ { 1 } \right.$ 为

$$
\left| \Psi _ { 1 } \right. = \left| \psi { \left( u _ { 1 } , u _ { 2 } , \cdots , u _ { t } \right) } \right. _ { U _ { 1 } , U _ { 2 } , \cdots , U _ { t } } \otimes \left| \psi { \left( \nu _ { 1 } , \nu _ { 1 } ^ { ' } \right) } \right. _ { V _ { 1 } , V _ { 1 } ^ { ' } }
$$

$$
= \frac { 1 } { d } \sum _ { k _ { 1 } , l _ { 1 } = 0 } ^ { d - 1 } \zeta ^ { - l _ { 1 } k _ { 1 } } \left| \psi \left( \nu _ { 1 } + k _ { 1 } , u _ { 2 } - l _ { 1 } , { } ^ { . . . } , u _ { t } - l _ { 1 } \right) \right. _ { V _ { 1 } , U _ { 2 } , . . . , U _ { t } } \otimes
$$

$$
\left| \psi \left( u _ { 1 } - k _ { 1 } , \nu _ { 1 } ^ { ' } + l _ { 1 } \right) \right. _ { U _ { 1 } , V _ { 1 } ^ { ' } } .
$$

当 $B o b _ { 1 }$ 测量粒子 $( U _ { 1 } , V _ { 1 } ^ { ' } )$ 之后，混合系统 $\left| \Psi _ { 1 } \right.$ 发生纠缠交换，如下图3所示。在式(6)右边的所有叠加项中，存在k=s,=0那一项为：

$$
\frac { 1 } { d } \Bigl | \psi \Bigl ( \nu _ { 1 } + s _ { 1 } , u _ { 2 } , \cdots , u _ { t } \Bigr ) \Bigr \rangle _ { V _ { 1 } , U _ { 2 } , \cdots , U _ { t } } \otimes \Bigl | \psi \Bigl ( u _ { 1 } - s _ { 1 } , \nu _ { 1 } ^ { \cdot } \Bigr ) \Bigr \rangle _ { U _ { 1 } , V _ { 1 } ^ { \prime } } ,
$$

![](images/029522ebfa6db29127284e1e56d2eed700c2525949ccb5ac2d99740fec51b12b.jpg)  
图3在粒子 $( U _ { 1 } , V _ { 1 } ^ { ' } )$ 上投影测量之后的第一次纠缠交换

b） $B o b _ { 2 }$ 使用投影算子 $\left| \psi \left( \nu _ { 2 } - s _ { 2 } , u _ { 2 } \right) \right. \left. \psi \left( \nu _ { 2 } - s _ { 2 } , u _ { 2 } \right) \right|$ 对持有的粒子(V,Uz)进行投影测量，测量的结果为|γ(v-S,u2)v,U另外的 $t$ 个粒子 $( V _ { 1 } , V _ { 2 } ^ { ' } , U _ { 3 } , \cdots , U _ { t } )$ 坍塌到$\Big | | \psi _ { 1 } ( \nu _ { 1 } + s _ { 1 } + s _ { 2 } , \nu _ { 2 } ^ { ' } , u _ { 3 } , \cdots , u _ { t } ) \Big \rangle _ { V _ { 1 } , V _ { 2 } ^ { ' } , U _ { 3 } , \cdots , U _ { t } }$ 。由于有混合系统Y>：

$$
\left| \Psi _ { 2 } \right. = \left| \psi { \left( \nu _ { 1 } + s _ { 1 } , u _ { 2 } , \cdots , u _ { t } \right) } \right. _ { V _ { 1 } , U _ { 2 } , U _ { 3 } , \cdots , U _ { t } } \otimes \left| \psi { \left( \nu _ { 2 } , \nu _ { 2 } ^ { \cdot } \right) } \right. _ { V _ { 2 } , V _ { 2 } ^ { \prime } }
$$

$$
= \frac { 1 } { d } \sum _ { l _ { 2 } , k _ { 2 } = 0 } ^ { d - 1 } \zeta ^ { - l _ { 2 } k _ { 2 } } \left. \psi \left( \nu _ { 1 } + s _ { 1 } + k _ { 2 } , \dot { \nu _ { 2 } } + l _ { 2 } , u _ { 3 } , \cdots , u _ { t } \right) \right. _ { V _ { 1 } , V _ { 2 } ^ { ' } , U _ { 3 } , \cdots , U _ { t } } \otimes
$$

$$
\left| \psi \left( \nu _ { 2 } - k _ { 2 } , u _ { 2 } - l _ { 2 } \right) \right. _ { V _ { 2 } , U _ { 2 } } \circ
$$

当 $B o b _ { 2 }$ 测量粒子 $\left( V _ { 2 } , U _ { 2 } \right)$ 之后，混合系统 $\left| \Psi _ { 2 } \right.$ 发生纠缠交换。在式(7)右边的所有叠加项中，存在 $k _ { 2 } = s _ { 2 } , l _ { 2 } = 0$ 那一项为：

$$
\begin{array} { l } { \displaystyle \frac 1 d \Big | \psi \big ( \nu _ { 1 } + s _ { 1 } + s _ { 2 } , \dot { \nu _ { 2 } } , u _ { 3 } , \cdots , u _ { t } \big ) \Big \rangle _ { V _ { 1 } , V _ { 2 } ^ { ' } , U _ { 3 } , \cdots , U _ { t } } \otimes } \\ { \displaystyle \Big | \psi \big ( \nu _ { 2 } - s _ { 2 } , u _ { 2 } \big ) \Big \rangle _ { V _ { 2 } , U _ { 2 } } } \end{array}
$$

c）其他参与者 $B o b _ { j } \big ( j = 3 , \cdots , t \big )$ 依次使用投影算子$\left| \psi { \left( \nu _ { j } - \right)} s _ { j } , u _ { j }  \right. \left. \psi { \left( \nu _ { j } - \right)} s _ { j } , u _ { j }  \right|$ 对持有的粒子 $\left( V _ { j } , U _ { j } \right)$ 进行投影测量，测量的结果为 $\left| \psi \left( \nu _ { j } - s _ { j } , u _ { j } \right) \right. _ { V _ { j } , U _ { j } }$ 。另外的 $\mathbf { \chi } _ { t } ^ { }$ 个粒子$\left( V _ { 1 } , V _ { 2 } ^ { ' } , \cdots , V _ { j - 1 } ^ { ' } , V _ { j } , U _ { j + 1 } , \cdots , U _ { t } \right)$ 坍塌到

$$
\left| \psi \left( \nu _ { 1 } + \sum _ { r = 1 } ^ { j } s _ { r } , \nu _ { 2 } ^ { ' } , \cdots , \nu _ { j - 1 } ^ { ' } , \nu _ { j } ^ { ' } , u _ { j + 1 } , \cdots , u _ { t } \right) \right. _ { \qquad V _ { 1 } , V _ { 2 } ^ { ' } , \cdots , V _ { j - 1 } ^ { ' } , V _ { j } ^ { ' } , U _ { j + 1 } , \cdots , U _ { t } } \ : .
$$

此时的混合系统为 $\left| { \Psi _ { j } } \right.$

$$
\begin{array} { r l } & { \left| \Psi _ { j } \right. = \left| \psi \left( \kappa _ { 1 } + \sum _ { s } ^ { i - 1 } s _ { j } , \dot { v } _ { 2 } , \cdots , \dot { v } _ { j - 1 } ^ { i } , u _ { j } , \cdots , u _ { t } \right) \right. _ { \stackrel { \scriptstyle 0 } { \tau _ { 1 } , g _ { 2 } ^ { \prime } , \cdots , g _ { j + 1 } , U _ { j } , \cdots , U _ { t } } } \otimes } \\ & { \qquad \left| \psi \left( v _ { j } , v _ { j } \right) \right. _ { V _ { j } , v _ { j } } } \\ & { = \frac { 1 } { d } \frac { d ^ { - 1 } } { d } _ { j } \frac { d ^ { - 1 } } { v _ { j } , v _ { j } } \xi ^ { i , j } , } \\ & { \left| \psi \left( v _ { 1 } + \sum _ { s } ^ { i - 1 } s _ { j } , \dot { v } _ { 2 } , \cdots , \dot { v } _ { j - 1 } ^ { i } , \dot { v } _ { j } ^ { j } + I _ { j } , u _ { j + 1 } , \cdots , u _ { t } \right) \right. _ { \stackrel { \scriptstyle 0 } { \tau _ { 1 } , g _ { 2 } ^ { \prime } , \cdots , v _ { j + 1 } ^ { i } , v _ { j } , u _ { k } , \cdots , U _ { t } } } \otimes } \\ & { \qquad \left| \psi \left( v _ { j } - k _ { j } , u _ { j } - I _ { j } \right) \right. _ { V _ { j } , v _ { j } } , } \end{array}
$$

d）当最后一个参与者 $B o b _ { t }$ 使用投影算子lv(v,-s,u,)v(v,-s,u,)|对持有的粒子(V,U,)进行投影测量，测量的结果为 $\left| \psi \left( \nu _ { t } - s _ { t } , u _ { t } \right) \right. _ { V _ { t } , U _ { t } }$ 。另外的 $\mathbf { \chi } _ { t } ^ { }$ 个粒子$\left( V _ { 1 } , V _ { 2 } ^ { ' } , \cdots , V _ { t - 1 } ^ { ' } , V _ { t } ^ { ' } \right)$ 坍塌到 $\left| \psi \left( \nu _ { 1 } + \sum _ { r = 1 } ^ { t } s _ { r } , \dot { \nu _ { 2 } } , \cdots , \dot { \nu _ { t - 1 } } , \dot { \nu _ { t } } \right) \right. _ { V _ { 1 } , V _ { 2 } ^ { ' } , \cdots , V _ { t - 1 } ^ { ' } , V _ { t } ^ { ' } }$ 当所有参与者投影测量完成，复合系统产生的纠缠交换如图4所示。

![](images/5d31f0b7189a9d1a44efc5497a3fe1045314c662e48d541bff3ea9448deaf47d.jpg)  
图4粒子 $\left( V _ { t } , U _ { t } \right)$ 投影测量后的纠缠交换结果

# 1.4秘密重建阶段

在本阶段，重建者 $B o b _ { 1 }$ 持有的 $V _ { 1 }$ 粒子，恢复出共享的秘密，并进行hash值比对，判断是否存在不诚实的参与者。

a） $B o b _ { \scriptscriptstyle 1 }$ 对持有的粒子 $V _ { 1 }$ 使用测量基 $\{ | J _ { _ q }  | { q = 0 , 1 , \cdots , d - 1 } \}$   
进行测量，其中 $\left| J _ { q } \right. = { \frac { 1 } { \sqrt { d } } } \sum _ { p = 0 } ^ { d - 1 } \zeta ^ { p q } \left| p \right.$ 。测量结果应为 $\left| J _ { _ { q } } \right.$ ，其中，  
q =ν+∑'_,s,。这是因为，在第1.3章第d）步，当 Bob,对粒  
子 $\left( V _ { t } , U _ { t } \right)$ 测量之后，坍塌的 $t$ 个粒子 $\left( V _ { 1 } , V _ { 2 } ^ { ' } , \cdots , V _ { t - 1 } ^ { ' } , V _ { t } ^ { ' } \right)$ 可表示为$\begin{array} { c } { { \displaystyle \left| \psi \left( \nu _ { 1 } + \sum _ { r = 1 } ^ { t } s _ { r } , \nu _ { 2 } ^ { ' } , \cdots , \nu _ { t - 1 } ^ { ' } , \nu _ { t } ^ { ' } \right) \right. _ { V _ { 1 } , V _ { 2 } ^ { ' } , \cdots , V _ { t - 1 } ^ { ' } , V _ { t } ^ { ' } } } } \\ { { = \displaystyle \frac { 1 } { \sqrt { d } } \sum _ { q = 0 } ^ { d - 1 } \zeta ^ { \left( \nu _ { 1 } + \sum _ { r = 1 } ^ { t } s _ { r } \right) q } \left| q \right. _ { V 1 } \left| q + \nu _ { 2 } ^ { ' } \right. _ { V _ { 2 } ^ { ' } } \left| q + \nu _ { 3 } ^ { ' } \right. _ { V _ { 3 } ^ { ' } } \cdots \left| q + \nu _ { t } ^ { ' } \right. _ { V _ { t } ^ { ' } } } } \end{array}$ (9)

b）已知测量结果 $\left| J _ { _ { q } \cdot } \right.$ 和 $\nu _ { 1 }$ 的值， $B o b _ { \scriptscriptstyle 1 }$ 能计算出 $\sum _ { r = 1 } ^ { t } s _ { r }$ 的值。进一步， $B o b _ { 1 }$ 计算 $h a s h \Big ( \sum _ { r = 1 } ^ { t } s _ { r } \Big )$ ，并验证等式$h a s h \Big ( \sum _ { r = 1 } ^ { t } s _ { r } \Big ) = h a s h \big ( a _ { 0 } \big ) \ \mathrm { ~ c ~ }$ 。如果这个等式成立，他就和其他参与者共享这个秘密消息；否则，他认为至少存在一个不诚实的参与者，进而结束此次秘密重建过程，开始新一轮的重建过程。

# 2 正确性证明

$$
\begin{array} { r l } & { \left| \psi \left( u _ { 1 } , u _ { 2 } \right) \right. _ { 1 , 2 } \otimes \left| \psi \left( \nu _ { 1 } , \nu _ { 2 } \right) \right. _ { 3 , 4 } } \\ & { = \frac { 1 } { \sqrt { d } } \underset { q = 0 } { \overset { d - 1 } { \sum } } \zeta ^ { q u _ { 1 } } \left| q \right. _ { 1 } \left| q + u _ { 2 } \right. _ { 2 } \otimes \frac { 1 } { \sqrt { d } } \underset { q = 0 } { \overset { d - 1 } { \sum } } \zeta ^ { q \nu _ { 1 } } \left| q \right. _ { 3 } \left| q ^ { * } + \nu _ { 2 } \right. _ { 4 } } \\ & { = \frac { 1 } { d } \underset { q , q } { \overset { \sum } { \sum } } \zeta ^ { q u _ { 1 } + q \overset { * } { \nu _ { 1 } } } \left| q \right. _ { 1 } \left| q ^ { * } + \nu _ { 2 } \right. _ { 4 } \left| q \right. _ { 3 } \left| q + u _ { 2 } \right. _ { 2 } } \end{array}
$$

$$
= \frac 1 { d ^ { 2 } } \sum _ { q , \dot { q } , p , p } \zeta ^ { q u _ { 1 } + \dot { q } ^ { \dot { \nu } _ { 1 } } } \zeta ^ { - q p - \dot { q } \dot { p } ^ { \prime } } \left| \psi \left( p , \dot { q } ^ { \prime } + \nu _ { 2 } - q \right) \right. _ { 1 , 4 } \left| \psi \left( p ^ { ' } , q + u _ { 2 } - \dot { q } ^ { \prime } \right) \right. _ { 3 , 2 }
$$

$$
\begin{array} { l } { \displaystyle \left| \psi \big ( u _ { 1 } , u _ { 2 } , \cdots , u _ { t } \big ) \right. _ { 1 , 2 , \cdots , t } \otimes \left| \psi \big ( \nu , \nu ^ { * } \big ) \right. _ { V , V } } \\ { \displaystyle = \frac { 1 } { d } \sum _ { k , l } \zeta ^ { - k l } \left| \psi \big ( \nu + k , u _ { 2 } - l , u _ { 3 } - l , \cdots , u _ { t } - l \big ) \right. _ { V , 2 , 3 , \cdots , t } \otimes } \end{array}
$$

$$
\left| \psi \left( u _ { 1 } - k , \nu ^ { ' } + l \right) \right. _ { 1 , V ^ { ' } } ,
$$

$$
\begin{array} { l } { \displaystyle \Big | \psi \big ( u _ { 1 } , u _ { 2 } , \cdots , u _ { t } \big ) \Big \rangle _ { 1 , 2 , \cdots , t } \otimes \Big | \psi \big ( \nu , \nu ^ { * } \big ) \Big \rangle _ { \scriptscriptstyle V , V } } \\ { \displaystyle = \cfrac { 1 } { d } \sum _ { k , l } \zeta ^ { - k l } \Big | \psi \big ( u _ { 1 } + k , u _ { 2 } , u _ { 3 } , \cdots , \nu ^ { * } + l , \cdots , u _ { t } \big ) \Big \rangle _ { 1 , 2 , \cdots , V ^ { ' } , \cdots , t } \otimes } \end{array}
$$

$$
\big | \psi \big ( \nu - k , u _ { m } - l \big ) \big \rangle _ { \nu , m } ,
$$

式(6)由式(13)得出，式(7)(8)由式(14)得出。

# 3 安全性分析

# 3.1截获-重发攻击

假设Eve 是一个不诚实的内部参与者或者是外部窃听者，她截获第 1.2 章第d）步中从 $B o b _ { 1 }$ 发往 $B o b _ { j }$ 的任意一个粒子$u _ { j } \big ( j = 2 , 3 , . . . , t \big )$ ，然后使用测量基 $\big \{ \vert 0 \rangle , \vert 1 \rangle , . . . , \vert d - 1 \rangle \big \}$ 去测量这个粒子。她有 $\bigstar$ 的概率成功获得 $u _ { j } + q$ 的值，其中q∈{0.,1...d-1}。最后她制备一个一样的粒子重放给参与者$B o b _ { j }$ 。不过，她的测量结果 $u _ { j } + q$ 并没有关于份额 $f ( x _ { j } )$ 和影子$s _ { j }$ 的任何信息。因此，Eve 的截获-测量-重发攻击不能获得任何有用的信息。

# 3.2纠缠-测量攻击

假设 Eve 截获了第1.2章第d）步中从 $B o b _ { 1 }$ 发往 $B o b _ { j }$ 的所有 $t - 1$ 粒子 $\{ U _ { 2 } , U _ { 3 } , \cdots , U _ { t } \}$ ，然后她制备 $_ { t - 1 }$ 个辅助粒子$\{ | e _ { 2 } \rangle , | e _ { 3 } \rangle , \cdots , | e _ { t } \rangle \}$ 。对于 $2 t - 1$ 个粒子组成的复合系统，Eve以粒子 $U _ { j } \left( j = 2 , 3 , . . . , t \right)$ 为控制粒子，以辅助粒子 $\left| e _ { j } \right.$ 为目标粒子分别进行 $d$ 维 $R _ { c }$ 门操作，将得到

$$
\left| \varphi _ { 3 } \right. = { \frac { 1 } { \sqrt { d } } } \sum _ { q = 0 } ^ { d - 1 } \zeta ^ { q u _ { 1 } } \left| q \right. \left| u _ { 2 } + q \right. \left| u _ { 3 } + q \right. \cdots \left| u _ { t } + q \right.
$$

令 $\stackrel { \cdot } { q - q } = l$ ，根据 $\frac { 1 } { d } \sum _ { q = 0 } ^ { d - 1 } \zeta ^ { q m } = \delta ( m , 0 )$ ，式(10)可写为

$$
{ \big | } u _ { 2 } + q + e _ { 2 } { \big \rangle } { \big | } u _ { 3 } + q + e _ { 3 } { \big \rangle } \cdots { \big | } u _ { t } + q + e _ { t } { \big \rangle } \ \circ
$$

$$
\left| \psi \left( u _ { 1 } , u _ { 2 } \right) \right. _ { 1 , 2 } \otimes \left| \psi \left( \nu _ { 1 } , \nu _ { 2 } \right) \right. _ { 3 , 4 } =
$$

$$
\frac { 1 } { d } \sum _ { k , l } \zeta ^ { - k l } \left| \psi \left( u _ { 1 } + k , \nu _ { 2 } + l \right) \right. _ { 1 , 4 } \otimes \left| \psi \left( \nu _ { 1 } - k , u _ { 2 } - l \right) \right. _ { 3 , 2 }
$$

由于在粒子2到粒子 $\mathbf { \Phi } _ { t }$ 之间，多粒子纠缠态的粒子以及粒子的标签之间的交换是对应的，即

$$
\big | \psi \big ( u _ { 1 } , \cdots , u _ { k } , \cdots , u _ { l } , \cdots , u _ { t } \big ) \big \rangle _ { 1 , \cdots , k , \cdots , l , \cdots , t } =
$$

$$
\left| \psi ( u _ { 1 } , \cdots , u _ { l } , \cdots , u _ { k } , \cdots , u _ { t } ) \right. _ { 1 , \cdots , l , \cdots , k , \cdots , t } ,
$$

由式子(11)(12)可得

由 $\left| \varphi _ { 3 } \right.$ 可知，当 Eve 对 $\left| u _ { j } + q + e _ { j } \right.$ 进行测量之后，已知$\left| e _ { j } \right. \left( j = 2 , 3 , . . . , t \right)$ 的值，Eve能得到 $u _ { j } + q$ 的值，其中$q \in \{ 0 , 1 , . . . , d - 1 \}$ 。但是结果 $u _ { j } + q$ 中并没有关于秘密份额 $f ( x _ { j } )$ （204和秘密影子 $s _ { j }$ 的任何信息。因此，Eve 的纠缠-测量攻击也不能获得任何有用的信息。

# 3.3合谋攻击

在第1.4章的秘密重建过程中，假定在 $t$ 个参与者中，除了重建者 $B o b _ { \scriptscriptstyle 1 }$ 是诚实的，其他参与者 $\{ B o b _ { 2 } , B o b _ { 3 } , \cdots , B o b _ { t } \}$ 都不诚实。当这t-1个参与者一起合谋，他们拿出自己持有的秘密影

子计算出这些影子的总和 $\sum _ { j = 2 } ^ { t } s _ { j }$ ，但他们并不知道 $B o b _ { 1 }$ 的的秘密影子 $s _ { 1 }$ ，也不能计算出最终的结果 $\sum _ { j = 1 } ^ { t } s _ { j }$ 。所以 $t \mathrm { - } 1$ 个参与者 $\left\{ B o b _ { 2 } , B o b _ { 3 } , \cdots , B o b _ { t } \right\}$ 的合谋攻击失败。

# 3.4伪造攻击

在第1.3章中，每个参与者对持有的粒子执行投影测量，假设有一个不诚实的参与者 $B o b _ { f }$ ，他使用一个伪造的秘密影子$\boldsymbol { s } _ { f } ^ { * }$ 代替真实的秘密影子 $s _ { f }$ ，生成投影测量算子$\left| \psi \left( \nu _ { _ { f } } - s _ { _ { f } } ^ { * } , u _ { _ { f } } \right) \right. \left. \psi \left( \nu _ { _ { f } } - s _ { _ { f } } ^ { * } , u _ { _ { f } } \right) \right|$ ，其中， $\boldsymbol { s } _ { f } ^ { * } \neq \boldsymbol { s } _ { f }$ 。进一步，他使用该算子对持有的粒子 $\left( V _ { f } , U _ { f } \right)$ 执行投影测量。当所有参与者测量完毕，重建者 $B o b _ { 1 }$ 将得到 $\nu _ { 1 } + s _ { 1 } + \cdots + s _ { f } ^ { * } + \cdots + s _ { t }$ 。当重建者 $B o b _ { 1 }$ 验证等式 $h a s h \big ( s _ { 1 } + \cdots + s _ { f } ^ { * } + \cdots + s _ { t } \big ) = h a s h \big ( a _ { 0 } \big )$ 时，发现等式不成立，于是他认为在所有参与者中至少存在一个参与者拿出的是伪造的秘密份额或秘密影子。 $B o b _ { 1 }$ 取消本次重建过程，$B o b _ { f }$ 的伪造攻击失败。

# 4 性能比较

由于提出的方案和方案给出了秘密份额和影子的产生过程，而方案[和方案[13]并没有提及，为了更公平地比较，四个方案都不考虑秘密份额和影子的产生过程的开销。由于提出的方案用 $\boldsymbol { H } _ { d }$ 门和 $R _ { c }$ 来制备多粒子纠缠态，而方案[和方案[13]没有提及多粒子纠缠态的制备过程，方案[9也没有给出t对 EPR对的制备过程，所以4个方案比较时也不考虑制备纠缠态的开销。将提出的方案与其他3个文献的方案[69:13]从门限类型、空间维度、酉操作 $+ Q F T$ 的次数、测量的次数、hash 运算的次数、信息效率六个方面进行比较，如表1所示。

表14个方案的比较  

<html><body><table><tr><td>性能</td><td>方案[6]</td><td>方案[9]</td><td>方案[13]</td><td>提出的方案</td></tr><tr><td>门限类型</td><td>(n,n)</td><td>(t,n)</td><td>(n,n)</td><td></td></tr><tr><td>空间维度</td><td>d</td><td>2</td><td>d</td><td>(t,n) d</td></tr><tr><td>酉操作+QFT 的次数</td><td>nUα.0 +nQFT</td><td>t(2t -1)U α.β</td><td>NUo.B +(N-Ci)(n+1)Hd</td><td>0</td></tr><tr><td>测量的次数</td><td>n</td><td>t</td><td>N(n +1)</td><td>t+1</td></tr><tr><td>hash 运算的次数</td><td></td><td></td><td></td><td>2</td></tr><tr><td rowspan="2">信息效率</td><td></td><td></td><td></td><td></td></tr><tr><td>1-22</td><td>3k +2k+dgd]</td><td>2N(n+1)</td><td>1-3</td></tr></table></body></html>

从表1可以看出，在门限方面，提出的方案和方案都是$\left( t , n \right)$ 门限方案，另外两种方案是 $\left( n , n \right)$ 门限方案。在Hilbert 空间维度方面，方案是2维方案，其他方案都是 $d ( d > 2 )$ 维方案。在4个方案中，只有提出的方案是 $d$ 维 $\left( t , n \right)$ 门限方案。

在酉操作 ${ } ^ { + } Q F T$ 的次数方面，在方案中， $n$ 个参与者先分别使用傅里叶变换 $( Q F T )$ 对自己的粒子作变换，再分别使用$U _ { \alpha , 0 }$ 变换将自己的秘密份额加入到量子态中，该方案酉操作 $^ +$ QFT的次数为 $n U _ { \alpha , 0 } + n Q F T$ 。在方案[9]中，分发者先把 $Y ^ { \prime }$ 序列发给 $B o b _ { 1 }$ ，每一个参与者 $B o b _ { r }$ 对来自于上一个参与者 $B o b _ { r - 1 }$ 发给他的 $Y ^ { \prime }$ 序列执行酉操作 $U _ { \alpha , \beta }$ 。最后一个参与者 $B o b _ { t }$ 对从$B o b _ { t - 1 }$ 收到的 $Y ^ { \prime }$ 序列执行酉操作 $U = U _ { _ { B _ { 1 } } } U _ { _ { B _ { 2 } } } \cdots U _ { _ { B _ { t } } }$ ，没有执行QFT 操作。该方案酉操作 ${ } ^ { + } Q F T$ 的次数为 $t \big ( 2 t - 1 \big ) U _ { \alpha , \beta }$ 。在方案[13]中，Alice 制备了 $N$ 对 $\left( n + 1 \right)$ 粒子的纠缠对，并将每个纠缠对中的第一粒子进行了 $U _ { 0 , \beta }$ 操作，在选取 $C _ { 1 }$ 个纠缠对进行窃听检测后，对剩余 $N - C _ { \scriptscriptstyle 1 }$ 个纠缠对的每个粒子进行了哈达门变换 $\boldsymbol { H } _ { d }$ 。QFT另一种表示法是 $d$ 维哈达门变换 $\boldsymbol { H } _ { d }$ ，所以该方案酉操作 ${ } ^ { + } Q F T$ 的次数为 $N U _ { 0 , \beta } + \big ( N - C _ { 1 } \big ) \big ( n + 1 \big ) H _ { d }$ 。提出的方案没有执行酉操作和 $\boldsymbol { \mathcal { Q } } \boldsymbol { F } \boldsymbol { T }$ ，这两种操作的次数为零。

在测量的次数方面，方案[13]测量次数最多，为 $N { \big ( } n + 1 { \big ) }$ 次。由于 $t \leq n$ ，方案[和提出的方案的测量次数相当，且少于其他两种方案。在hash运算方面，提出的方案有2次，其他方案没有。与酉操作 ${ } ^ { + } Q F T$ ，测量操作相比，hash运算所花费的开销要小得多。

信息效率计算公式为 $\eta = c / { \left( q + b \right) }$ ，这里 $\mathbf { \Psi } _ { c }$ 为秘密消息的经典比特总数， $q$ 为制备粒子总数， $\textit { b }$ 为经典信道交换的经典比特总数。提出的方案和其他三个文献[6，9，13]的方案都恢复了一个 $d$ 维的秘密消息（ $\left\lceil \log _ { 2 } d \right\rceil$ bits），因此 $\mathbf { \Psi } _ { c }$ 的值都为[logzd]。提出的方案第一轮制备了3t个d维粒子，且没有用经典信道传输经典比特，所以提出的方案的第一轮的信息效率为 $\eta = { \frac { \left\lceil \log _ { 2 } d \right\rceil } { 3 t { \lceil \log _ { 2 } d \rceil } } } = { \frac { 1 } { 3 t } }$ [logd]=1。方案需要制备n个d维粒子，且需要（20  
利用经典信道公布 $n$ 个 $d$ 维粒子的测量结果，因此方案的信息效率为n=n[ogd+n[ogd2n 1；方案由于在秘密重构阶段，秘密份额的影子需要在量子信道中传输，为保证可抵抗窃听攻击，其使用了插入诱骗粒子进行窃听检测的方法，方案[9]制备了 $\mathbf { \Sigma } _ { m }$ 个 EPR粒子对，这里的 $2 m = \lceil \log _ { 2 } d \rceil$ ，并需要进行 $\big ( t + 1 \big )$ 窃听检测，制备的诱骗粒子总数为 $2 k + { \big ( } t - 2 { \big ) } k$ ，而且经典信道里需要交换诱骗粒子的位置信息和测量结果信息共$2 k { \big ( } t + 1 { \big ) }$ bits，因此方案[9]的信息效率为$\eta = { \frac { \left\lceil \log _ { 2 } { d } \right\rceil } { 2 k + { \big ( } t - 2 { \big ) } k + { \big \lceil } \log _ { 2 } { d } { \big \rceil } + 2 k { \big ( } t + 1 { \big ) } } } = { \frac { \left\lceil \log _ { 2 } { d } \right\rceil } { 3 t k + 2 k + { \big \lceil } \log _ { 2 } { d } { \big \rceil } } }$ ，这里$k \geq 1$ 。方案[13]需要制备 $N$ 对 $n + 1$ 粒子的 $d$ 维纠缠态，并且最终恢复秘密后，所有的粒子都被测量完了，而且测量结果都需要通过经典信道进行公布，所以需要交换 $N { \big ( } n + 1 { \big ) } { \Big [ } \log 2 ^ { d } { \Big ] }$ bits信息，因此方案[13]的信息效率为$\eta = { \frac { \left\lceil \log _ { 2 } { d } \right\rceil } { N \left( n + 1 \right) \left\lceil \log _ { 2 } { d } \right\rceil + N \left( n + 1 \right) \left\lceil \log _ { 2 } { d } \right\rceil } } = { \frac { 1 } { 2 N \left( n + 1 \right) } }$ 。而且，提出的方案每一轮秘密共享只消耗 $\mathbf { \Phi } _ { t }$ 个 $d$ 维粒子，秘密恢复后剩下的 $\mathbf { \Phi } _ { t }$ 对2粒子纠缠态可以在下一轮继续使用，并在以后每一轮都可以继续使用。因此，从第二轮开始，提出的方案的信息效率将变为 $\eta = { \frac { \left\lceil \log _ { 2 } d \right\rceil } { t { \lceil \log _ { 2 } d \rceil } } } = { \frac { 1 } { t } }$ [logd]_1。而方案[6·9.13]中制备的粒子无法继（204号  
续使用，全部被消耗了，下一轮需重新制备，因此方案 $[ 6 , 9 , 1 3 ]$ 的信息效率在第二轮后是不变的。很明显，提出的方案的信息效率较高。

# 5 结束语

提出的以 $d$ 维纠缠交换为技术手段，提出了一个 $\left( t , n \right)$ 门限量子秘密共享方案。安全性分析可知，提出的方案能抵抗截获-重发攻击、纠缠-测量攻击、合谋攻击和伪造攻击。它应用纠缠交换实现隐形传输，份额没有在量子信道中传输，比其他现有类似方案具有更强的安全性。性能比较分析表明，提出的方案是 $d$ 维 $\left( t , n \right)$ 门限方案，相比其他2 维或 $\left( n , n \right)$ 门限方案，提出的方案具有更好的灵活性、实用性和普适性。由于提出的方案没有执行酉操作和 $\boldsymbol { Q } \boldsymbol { F } \boldsymbol { T }$ ，总的计算和测量所花费的开销在现有类似方案中是最低的。后期的研究是探寻如何将提出的 $d$ 维(t,n)门限量子秘密共享应用于量子群通信环境中，设计量子门限签名，量子门限加密等方案。

# 参考文献：

[1]Hillery M, Buzek V, Berthiaume A.Quantum secret sharing [J].Physical Review A,1999,59 (3):1829-1834.   
[2]Wang wenhua, Cao Huaixin.An improved multiparty quantum secret sharing with bell states and Bell measurement [J]. International Journal of Theoretical Physics,2013,52(6):2099-2111.   
[3]Qin Huawang,Dai Yuewei. Effcient quantum secret sharing [J]. Quantum Information Processing,2016,15 (5): 2091-2100.   
[4]Tan Xiaoqing,Jiang Lianxia.Improved three-party quantum secret sharing based on Bell states [J].International Journal of Theoretical Physics,2013, 52 (10):3577-3585. on entanglement swapping [J]. Physical Review A,2005,72 (2)   
[6]Yang Wei, Huang Liusheng,Shi Runhua,et al. Secret sharing based on quantum Fourier transform [J]. Quantum Information Processing,2013,12 (7): 2465-2474.   
[7]Tavakoli A,Herbauts I, Zukowski M,et al. Secret sharing with a single dlevel quantum system [J].Physical Review A,2015,92 (3).   
[8]Yang Yuguang,Wen Qiaoyan.Circularthreshold quantum secret sharing[J]. Chinese Physics B,2008,17 (2): 419-423.   
[9]Li Baokui, Yang Yuguang, Wen Qiaoyan. Threshold quantum secret sharing of secure direct communication [J]. Chinese Physics Letters,20o9,26 (1): 21-24.   
[10] Cleve R,Gottesman D,Lo HK.How to share a quantum secret[J]. Physical Review Letters,1999,83 (3): 648-651.   
[11] Guo Ying,Huang Dazu, Zeng Guihua,et al. Multiparty quantum secret sharing of quantum states using entanglement states [J]. Chinese Physics Letters,2008,25 (1): 16-19.   
[12] Qin Huawang,Zhu Xiaohua,Dai Yuewei. (t,n) threshold quantum secret sharing using the phase shift operation[J]. Quantum Information Processing, 2015,14 (8): 1-8.   
[13] Xiao Heling,Gao Jingliang.Multi-party d-level quantum secret sharing scheme[J].International Journal ofTheoretical Physics,2013,52(6): 2075- 2082.   
[14] Huang Dazu, Chen Zhigang,Guo Ying. Multiparty quantum secret sharing using quantum fourier transform [J].Communications in Theoretical Physics,2009,51 (2): 51-221.   
[15] Qin Huawang,Dai Yuewei. Proactive quantum secret sharing [J]. Quantum Information Processing,2015,14(11): 4237-4244.   
[16] Song Tingting,Wen Qiaoyan,Qin Sujuan,et al. The general theory of threeparty quantum secret sharing protocols over phase-damping channels [J]. Quantum Information Processing,2013,12(10): 3291-3304.   
[17] Dehkordi M H,Fattahi E. Threshold quantum secret sharing between multiparty and multiparty using Greenberger-Hore-Zeilinger state [J]. Quantum Information Processing,2013,12 (2):1299-1306.   
[18]Yang Yuguang,Jia Xin, Wang Hongyang,et al. Verifiable quantum (k, n)- threshold secret sharing [J]. International Journal of Theoretical Physics, 2011,50 (3): 792-798.   
[19] Deng Fuguo,Li Xihan,Zhou Hongyu.Eficient high-capacity quantum secret sharing with two-photon entanglement[J].Physics Letters A,2006 372 (12): 1957-1962.   
[20] Song Xiuli, Liu Yanbing.Cryptanalysis and improvement of verifiable quantum (k,n) secret sharing [J]. Quantum Information Processing,2016, 15 (2): 851-868.   
[21] Karimipour V,BahraminasabA,Bagherinezhad S.Entanglement swapping of generalized cat states and secret sharing [J].Physical Review A,2001,65 (4): 579-579.