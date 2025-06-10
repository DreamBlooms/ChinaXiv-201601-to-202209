# 可验证第三方的量子秘密信息平等互换协议

邵婷婷，张仕斌，昌燕(成都信息工程大学 网络空间安全学院，成都610225)

摘要：为了实现通信双方的信息交换，提出一种可验证第三方的量子秘密信息平等互换协议。该协议中，由第三方制备GHZ态，将其中的两个粒子分别发送给通信的双方。通信双方分别对收到的粒子进行泡利操作，然后发送给第三方；第三方对新的GHZ 态进行测量并公布测量结果，通信双方根据公布的测量结果能够推测出对方的秘密信息。通过分析可知，该协议能够实现通信双方秘密信息的平等互换，可以对第三方的身份进行认证，第三方负责进行粒子的分发和测量，但不能获得秘密信息。该协议能够检测窃听，同时能够抵御截获重发攻击、中间人攻击和参与者攻击。

关键词：量子通信；秘密信息；GHZ态；平等互换；可验证第三方 中图分类号：TN915.08 doi:10.19734/j.issn.1001-3695.2018.07.0560

Third party verifiable quantum secret information equal exchange protocol

Shao Tingting, Zhang Shibin†, Chang Yan (School of Cybersecurity,Chengdu University of Information Technology University,Chengdu 6lO225,China)

Abstract: Inorder to realize the information exchange betweenthe two parties,the paper proposes averifiable third party quantum secret information equal exchange protocol.In this protocol,a third party prepares the GHZ state and sends the particles to each communicating parties respectively.The two parties of the communication respectivelyconduct the pauli operation on thereceived particles and then send them to a third party.Athird party measuresthe new GHZ state and publishes the results.Both partiescan deduce the other party's secret information according to the published measurement results.Throughanalysis,this protocolcanrealize theequal exchangeofsecret informationbetwenthetwoparties,ndcan verifytheidentityofthethird party.Thethirdparty isresponsible for thedistributionand measurementof particles but canotobtain secret information.Analysis shows thatthe protocolcan detect eavesdropping.At thesame time,the protocol can resist the interception and retransmission attack,man-in-the-middle attack and participant attack.

Key words: quantum communication; secret information; GHZ state; equal exchange; verifiable third party

# 0 引言

随着时间的发展，经典的密码体制已经比较完善，并且被广泛的应用在各个生活领域，保护着人们的信息安全。但是，随着量子算法[1,2]和量子计算机研制[3]的提出，经典密码系统的安全性受到极大的挑战。1969年Wiesner首先提出用量子效应保护信息，他写了一篇《共轭编码》[4的论文。量子通信具有两个基本的特征：无条件安全性及对窃听的可检测性。无条件的安全性是指在攻击者拥有无限的计算资源前提下仍然不可以破译该密码系统。对窃听的可检测性是指通信中的用户之间信道受到干扰时，根据测不准原理可以检测出干扰的存在。近年来，量子通信取得了一系列可喜可贺的研究成果[5.6]，主要包括量子密钥分发(QKD)[7.8]，量子秘密共享(QSS)[9.10]，量子隐私查询(QPQ)[11,12]，量子安全直接通信(QSDC)[13,14]等。

现实生活中，如果两个用户各自拥有一条秘密信息，用户1想要获得用户2的秘密信息，同时用户2想要获得用户1的秘密信息，两个用户可以通过秘密信息的交换获得更多的信息。但是在信息交换的过程中，以往的通信协议通常是用户1首先发送秘密信息给用户2，用户2确认收到秘密信息之后，才将自己的秘密信息发送给用户1。这种秘密信息交换的方式存在风险，有可能用户2获得用户1的秘密信息，却欺骗用户1，发送假的秘密信息给用户1。用户1获得的是假的秘密信息，但是自己的秘密信息已经泄露给用户2。为了避免这种风险的存在，本文设计了一种新的可验证第三方的量子秘密信息平等互换协议。

本协议首先由第三方制备GHZ 态，将其中的两个粒子分别发送给通信双方。虽然协议中引入了第三方，但是可以对第三方的身份进行验证，减少对第三方的依赖。收到粒子后的通信双方利用泡利操作将秘密信息分别加载到粒子上，再返回给第三方，通信双方对新的GHZ态进行测量并公布测量结果。通信双方可以根据公布的测量结果推测出对方的秘密信息。该协议可以使通信的双方同时获得对方的秘密信息，实现秘密信息的平等互换，避免秘密信息交换过程中一方欺骗另一方的情况。通过分析可知，第三方的身份可以被验证，能够确保第三方是安全可信的，同时，该协议在实现过程中能够进行检测窃听，抵御截获重发攻击、中间人攻击和参与者攻击。

# 1 基本原理

四种泡利矩阵如下：

$$
\left. { \begin{array} { c c } { \sigma _ { _ { 0 0 } } = { \left[ \begin{array} { l l } { 1 } & { 0 } \\ { 0 } & { 1 } \end{array} \right] } , } & { \sigma _ { _ { 1 0 } } = { \left[ \begin{array} { l l } { 0 } & { - 1 } \\ { 1 } & { 0 } \end{array} \right] } } \\ { \sigma _ { _ { 0 1 } } = { \left[ \begin{array} { l l } { 0 } & { 1 } \\ { 1 } & { 0 } \end{array} \right] } , } & { \sigma _ { _ { 1 1 } } = { \left[ \begin{array} { l l } { 1 } & { 0 } \\ { 0 } & { - 1 } \end{array} \right] } } \end{array} } \right\}
$$

对 $| 0 \rangle$ 和1>执行四种泡利操作得到如下结果：

$$
\begin{array} { l l } { { \sigma _ { _ { 0 0 } } \left. 0 \right. = \left. 0 \right. , } } & { { \sigma _ { _ { 0 0 } } \left. 0 \right. = \left. 1 \right. } } \\ { { \sigma _ { _ { 0 1 } } \left. 0 \right. = \left. 1 \right. , } } & { { \sigma _ { _ { 0 1 } } \left. 0 \right. = \left. 0 \right. } } \\ { { \sigma _ { _ { 1 0 } } \left. 0 \right. = \left. 1 \right. , } } & { { \sigma _ { _ { 1 0 } } \left. 0 \right. = - \left. 0 \right. } } \\ { { \sigma _ { _ { 1 1 } } \left. 0 \right. = \left. 0 \right. , } } & { { \sigma _ { _ { 1 1 } } \left. 0 \right. = - \left. 1 \right. } } \end{array}
$$

8 种GHZ 态如下：

$$
\begin{array} { c c } { { | \Psi \rangle _ { a } = \displaystyle \frac { 1 } { \sqrt { 2 } } ( | 0 0 0 \rangle + | 1 1 1 \rangle ) _ { 1 2 3 } } } & { { | \Psi \rangle _ { b } = \displaystyle \frac { 1 } { \sqrt { 2 } } ( | 0 0 0 \rangle - | 1 1 1 \rangle ) _ { 1 2 3 } } } \\ { { | \Psi \rangle _ { c } = \displaystyle \frac { 1 } { \sqrt { 2 } } ( | 0 0 1 \rangle + | 1 1 0 \rangle ) _ { 1 2 3 } } } & { { | \Psi \rangle _ { d } = \displaystyle \frac { 1 } { \sqrt { 2 } } ( | 0 0 1 \rangle - | 1 1 0 \rangle ) _ { 1 2 3 } } } \\ { { | \Psi \rangle _ { e } = \displaystyle \frac { 1 } { \sqrt { 2 } } ( | 0 1 0 \rangle + | 1 0 1 \rangle ) _ { 1 2 3 } } } & { { | \Psi \rangle _ { f } = \displaystyle \frac { 1 } { \sqrt { 2 } } ( | 0 1 0 \rangle - | 1 0 1 \rangle ) _ { 1 2 3 } } } \\ { { | \Psi \rangle _ { s } = \displaystyle \frac { 1 } { \sqrt { 2 } } ( | 0 1 1 \rangle + | 1 0 0 \rangle ) _ { 1 2 3 } } } & { { | \Psi \rangle _ { b } = \displaystyle \frac { 1 } { \sqrt { 2 } } ( | 0 1 1 \rangle - | 1 0 0 \rangle ) _ { 1 2 3 } } } \end{array}
$$

纠缠态 $\left| \Psi \right. _ { \mathrm { a } } = \frac { 1 } { \sqrt { 2 } } \big ( \left| 0 0 0 \right. + \left| 1 1 1 \right. \big ) _ { 1 2 3 }$ 在 $\mathrm { \Delta } \mathrm { X }$ 基下的表示如下：

$$
\mid \Psi \rangle _ { a } = \frac { 1 } { \sqrt { 2 } } \left( \mid 0 0 0 \rangle + \mid 1 1 1 \rangle \right) _ { 1 2 3 } = \frac { 1 } { 2 } \left( \mid + + + \rangle + \mid + -- \rangle + \mid - + - \rangle + \mid -- + \rangle \right) _ { 1 2 3 }
$$

由式（4）可知，纠缠态 $\vert \Psi \rangle _ { a } = \frac { 1 } { \sqrt { 2 } } \left( \vert 0 0 0 \rangle + \vert 1 1 1 \rangle \right) _ { 1 2 3 }$ 中的三个粒子有如下关系：当第一个粒子为态 $| + \rangle$ 时，第二个和第三个粒子状态相同；当第一个粒子为 $| - \rangle$ 态时，第二个和第三个粒子状态相反。根据这个特性可以验证一个纠缠态是否是$\left| \Psi \right. _ { \mathrm { a } }$ 态。

# 2 协议描述

Alice拥有秘密信息 $X \left( \mathbf { x } _ { 1 } , \mathbf { x } _ { 2 } . . . . . . . \mathbf { x } _ { n } \right)$ ，Bob拥有秘密信息$Y ( y _ { 1 } , y _ { 2 } . . . . . . . . y _ { n } )$ ，其中每个 $\mathbf { x } _ { i }$ 与 $\mathbf { y } _ { i }$ 对应两位二进制比特。Alice和 Bob想要进行秘密信息的交换，协议如下：

a）Alice 和Bob告知第三方，由第三方制备 $\mathbf { m } { + } \mathbf { n }$ 对$\left| \Psi \right. _ { \mathrm { a } } = \frac { 1 } { \sqrt { 2 } } ( \left| 0 0 0 \right. + \left| 1 1 1 \right. ) _ { 1 2 3 }$ 态，将所有的1粒子组成序列 $S _ { 1 }$ ；所有的2粒子组成序列 $S _ { 2 }$ ；所有的3粒子组成序列 $S _ { 3 }$ 。第三方将序列 $S _ { \mathrm { 1 } }$ 自己保留，在序列 $S _ { 2 }$ 和序列 $S _ { 3 }$ 中随机插入诱骗粒子$| 0 \rangle$ 、1、 $\left| + \right.$ 、 $| - \rangle$ ，然后分别发送给Alice和Bob。

b)Alice和Bob收到第三方发送的粒子后进行窃听检测，第三方公布诱骗粒子的位置及对应的测量基，如果插入的是$| 0 \rangle$ 或1则公布Z基，如果插入的是 $\left| + \right.$ 或 $| - \rangle$ 则公布X基。Alice和Bob将对应位置的粒子提取出来用X基或Z基测量。若测量结果错误高于阈值，则放弃通信，否则进行c）步。

c）对第三方的身份进行认证，Alice和Bob随机指定m个粒子及对应粒子的位置，要求第三方用X基进行测量并用经典信道公布测量结果，Alice 和Bob收到测量结果之后也用X基测量对应位置的粒子。如果第三方正确制备了GHZ态，应该满足第三方公布 $\left| + \right.$ 态时，Alice和Bob的测量结果相同；第三方公布 $| - \rangle$ 态时，Alice 和Bob的测量结果相反。如果验证第三方准确制备了GHZ态，则进行d）步。

d）Alice根据自己的秘密信息 $X$ 对 $\mathfrak { n }$ 个粒子执行四种泡利操作，如果 $\mathbf { X } _ { i }$ 为00 则执行 $\sigma _ { 0 0 }$ 操作；如果 $\mathbf { X } _ { i }$ 为01则执行 $\sigma _ { \mathrm { 0 1 } }$ 操作；如果 $\mathbf { X } _ { i }$ 为10则执行 $\sigma _ { 1 0 }$ 操作；如果 $\mathbf { X } _ { i }$ 为11则执行 $\sigma _ { 1 1 }$ 操作。Alice执行泡利操作之后形成新的序列 $S _ { 2 } ^ { ' }$ ，同理，Bob根据自己的秘密信息Y执行泡利操作之后形成新的序列 $S _ { 3 } ^ { ' }$ 。Alice 在序列 $S _ { 2 } ^ { ' }$ 中随机插入诱骗粒子 $| 0 \rangle$ 、1>、 $\left| + \right.$ 、 $\left| - \right.$ ，然后发送给第三方，同理，Bob把随机插入诱骗粒子的 $S _ { 3 } ^ { ' }$ 也发送给第三方。

e）第三方收到Alice和Bob发来的粒子之后，Alice和Bob分别公布诱骗粒子的位置及测量基，同b）步第三方公布的方式相同。

f）第三方取出诱骗粒子之后得到 $S _ { 2 } ^ { ' }$ 和 $S _ { 3 } ^ { ' }$ ，然后与自己的序列 $S _ { \mathrm { { \ell } } }$ 联合测量，测量结果如表1所示，第三方公布测量的GHZ 态。

g）Alice 根据表1第三方公布的测量结果可以推测出信息 $Y ^ { ' }$ ，同理，Bob根据第三方公布的测量结果可以推测出信息 $X ^ { ' }$ 。Alice用经典信道公布 $\boldsymbol { Y ^ { \prime } }$ 异或 $\boldsymbol { \cal X }$ 的结果，Bob用经典信道公布 $X$ 异或 $Y$ 的结果，如果两者公布的内容相同，说明第三方没有存在欺骗，Alice 得到Bob的秘密信息 $Y$ ，Bob得到Alice的秘密信息 $X$ 。

表1泡利操作后GHZ态的测量结果  
Table1Measurement results of GHZ state after Pauli operatior   

<html><body><table><tr><td rowspan="2">Alice</td><td colspan="4">Bob</td></tr><tr><td>T00</td><td>01</td><td>010</td><td></td></tr><tr><td>00</td><td></td><td></td><td>|yd</td><td></td></tr><tr><td>01</td><td></td><td>14</td><td></td><td></td></tr><tr><td>010</td><td></td><td></td><td></td><td></td></tr><tr><td>011</td><td>14</td><td></td><td>14</td><td></td></tr></table></body></html>

# 3 协议分析

# 3.1协议的正确性分析

如果通信的双方Alice和Bob想要进行秘密信息的交换，由第三方制备GHZ 态 $| \Psi \rangle _ { \mathrm { a } } = \frac { 1 } { \sqrt { 2 } } \big ( \bigl | 0 0 0 \bigr \rangle + \bigl | 1 1 1 \bigr \rangle \bigr ) _ { 1 2 3 }$ ，将粒子2发送给Alice，将粒子3发送给Bob。Alice和Bob根据秘密信息对粒子进行泡利操作，然后发送给第三方，第三方将返回的粒子与自己手中的粒子进行测量并公布测量结果。如表1，Alice根据第三方公布的测量结果及自己的秘密信息能够推测出Bob的秘密信息，同理，Bob也能推测出Alice的秘密信息。协议的简化流程图如图1所示。

![](images/e2f5bec2e7dbd98564a2dfb09272a3fdeb116125e80a8ab628c7b4b7c03bd8f5.jpg)  
图1协议的简化流程图  
Fig.1Protocol simplified flow chart

协议举例：假设Alice拥有秘密信息001011，Bob拥有秘密信息110011。Alice和Bob告知第三方，由第三方制备$\mathbf { m } { + } \mathbf { n }$ $\left| \Psi \right. _ { \mathrm { a } } = \frac { 1 } { \sqrt { 2 } } \big ( \left| 0 0 0 \right. + \left| 1 1 1 \right. \big ) _ { 1 2 3 }$ 骗粒子后发送给Alice，将所有的3粒子随机插入诱骗粒子后发送给Bob。Alice和Bob收到第三方发送的粒子后进行窃听检测，证明信道安全之后对第三方的身份进行验证。Alice和Bob随机指定粒子的位置，要求第三方用X基进行测量，当第三方公布的是 $\left| + \right.$ 态时，Alice和Bob用X基测量的测量结果相同。当第三方公布的是 $| - \rangle$ 态时，Alice 和Bob用X基测量的测量结果相反。验证第三方正确制备GHZ态之后，Alice和Bob分别将秘密信息加载到各自的粒子上。Alice对2粒子分别执行 $\sigma _ { 0 0 }$ 、 $\sigma _ { 1 0 }$ 、 $\sigma _ { \mathrm { 1 1 } }$ 操作;Bob 对3粒子分别执行 $\sigma _ { \mathrm { 1 1 } }$ 、$\sigma _ { 0 0 }$ 、 $\sigma _ { 1 1 }$ 操作。Alice和Bob 将执行泡利操作之后的粒子插入诱骗粒子之后发送给第三方。第三方收到粒子，检测窃听之后将诱骗粒子提取出来，联合所有的粒子1进行GHZ测量。公布测量结果 $\left| \Psi \right. _ { b } \left| \Psi \right. _ { d } \left| \Psi \right. _ { \mathrm { a } }$ ，根据表1泡利操作后GHZ态的测量结果，Alice 获得信息110011，Bob获得信息001011。Alice将得到的信息110011与自己的秘密信息001011异或得111000并用经典信道公布；Bob将得到的信息001011与自己的秘密信息110011异或得111000也用经典信道公布，Alice和Bob公布的信息相同，说明没有存在欺骗或者攻击，Alice和Bob实现秘密信息的平等互换。

# 3.2安全分析模型的建立

量子秘密信息平等互换协议实现的是两个用户安全的进行信息交换。如图2所示，在秘密信息的交换过程中，秘密信息交换面临的攻击者可能有第三方的攻击（包括制备错误的GHZ态和公布假的信号）、通信过程中的中间人攻击或截获重发攻击、参与者攻击。

![](images/f92e64b2bf9dc3d84be5285f457913c846960bc265d1b1bfaa9569a457786b01.jpg)  
图2存在攻击的协议流程图  
Fig.2Protocol flow chart of the attack process

3.2.1第三方攻击

本协议中，需要第三方做两件事，第一：正确制备GHZ态；第二：Alice和Bob执行泡利操作之后返回给第三方，第三方正确公布联合测量的GHZ态的结果。

第三方制备 $\left| \Psi \right. _ { \mathrm { a } } = \frac { 1 } { \sqrt { 2 } } \big ( \left| 0 0 0 \right. + \left| 1 1 1 \right. \big ) _ { 1 2 3 }$ 态并将粒子2和粒子3分发给Alice和Bob，假如第三方试图制备假的GHZ态，破坏 Alice和Bob的秘密信息交换，将会在验证第三方身份的过程中被发现。在协议的实现过程，需要对第三方进行认证，Alice和Bob分别收到2粒子和3粒子之后随机选取部分粒子进行验证。要求第三方用X基进行测量并用经典信道公布测量结果，Alice和Bob收到测量结果之后也用X基测量对应位置的粒子，如果第三方公布 $\left| + \right.$ 态，Alice和Bob的测量结果相同；如果第三方公布 $| - \rangle$ 态，Alice 和Bob的测量结果相反。满足上述关系，则说明第三方正确制备了GHZ态，

否则第三方可能存在欺骗。

如果第三方想阻止Alice和Bob之间的秘密信息交换，采用假信号攻击，将 $S _ { 2 } ^ { ' }$ 和 $S _ { 3 } ^ { ' }$ 与自己的序列 $S _ { \mathrm { { \ell } } }$ 联合测量之后公布假的GHZ态，试图使Alice得到假的秘密信息 $\boldsymbol { Y } ^ { \prime }$ ，同理，Bob得到假的秘密信息 $X ^ { ' }$ 。Alice根据第三方公布的测量结果推测出信息 $\boldsymbol { Y ^ { \prime } }$ ，同理，Bob根据第三方公布的测量结果可以推测出信息 $X$ 。如果 $\boldsymbol { Y ^ { \prime } }$ 与 $Y$ 不相同， $X ^ { ' }$ 与 $\boldsymbol { \cal X }$ 不相同，Alice和Bob分别用经典信道公布 $\boldsymbol { Y } ^ { \prime }$ 异或 $\boldsymbol { \cal X }$ 的结果和 $X ^ { ' }$ 异或 $Y$ 的结果将会不同，Alice和Bob将会发现第三方可能公布了假信息，但是第三方不能准确获得Alice和Bob的消息。例如第三方得到表1中的 $\left| \Psi \right. _ { \mathrm { a } }$ 态，但是并不知道Alice和Bob的泡利操作是00还是11，二进制比特的数量越多，第三方获得正确消息的概率越小。

# 3.2.2中间人攻击或截获重发攻击

当信道不安全时，可能存在中间人攻击或截获重发攻击。Alice和Bob收到粒子之后，需要进行信道安全性检测，第三方公布诱骗粒子的位置。Alice和Bob将对应位置的粒子提取出来用X基或Z基测量并公布测量结果，攻击者一旦选错测量基，就会对粒子造成干扰，如果与第三方插入的诱骗粒子状态不同，则说明可能存在中间人攻击或截获重发攻击，第三方重新发送新的GHZ态。Alice和Bob执行泡利操作之后返回给第三方的过程同样需要窃听检测，Alice和Bob也可以通过公布的 $\boldsymbol { Y } ^ { \prime }$ 异或 $X$ 与 $X ^ { ' }$ 异或 $Y$ 的结果是否相同判断是否存在攻击者，如果存在攻击者，那么Alice 通过第三方公布的GHZ 态获得信息 $Y ^ { ' }$ 并不是Bob 的真正秘密信息Y，同理，Bob获得信息 $X ^ { ' }$ 不是Alice的真正秘密信息 $\boldsymbol { \cal X }$ ，因此 $\boldsymbol { Y ^ { \prime } }$ 异或 $\boldsymbol { \cal X }$ 与 $X ^ { ' }$ 异或Y的结果将会不同。分析可知，本协议可以有效的抵御中间人攻击或截获重发攻击。

# 3.2.3参与者攻击

假设通信过程中Bob试图欺骗Alice，Bob不按照正确的秘密信息 $Y$ 执行泡利操作。例如Alice的秘密信息是 $" 0 1 \ '$ ，Bob的秘密信息是“ $0 0 ^ { \prime \prime }$ ，但是Bob却对收到的粒子执行 $\sigma _ { 1 1 }$ 操作，试图骗取Alice的秘密信息。Alice和Bob将执行泡利操作之后的粒子返回给第三方，第三方测量之后公布 $\left| \Psi \right. _ { \mathrm { f } }$ （如果Bob正确执行泡利操作应该公布的是 $\left| \Psi \right. _ { \mathrm { c } }$ ),Bob 根据自己的秘密信息“00”和表1中对应的 $\left| \Psi \right. _ { \mathrm { f } }$ 得到‘ $^ { \bullet } 1 0 ^ { \prime \prime }$ ，而Alice的秘密信息是“ $0 1 ^ { \prime \prime }$ ，Bob并不能通过这种攻击方法获得Alice的秘密信息。

# 4 结束语

本文提出一种可验证第三方的量子秘密信息平等互换协议，可以实现通信双方平等的秘密信息交换。本协议可以防止一方欺骗一方获得秘密信息，通信的双方通过第三方公布的消息同时获得对方的秘密信息。本协议可以验证第三方，减少了对第三方的依赖，同时可以抵御中间人攻击或截获重发攻击以及参与者攻击，确保信息的安全平等互换。

# 参考文献：

[1]Shor P W.Algorithms for quantum computation:discrete logarithms and factoring [C]// Proc of the 35th Annual Symposium on the Foundations of Computer Science.Washington DC:IEEE Computer Society,1994:124-134.   
[2]Grover L K.A fast quantum mechanical algorithm for database search [C]/Proc of the 28th ACM Symposium on Theory of Computing.New York:ACMPress,1996:212-219.   
[3]Ladd T D,Jelezko F,Laflamme R,et al.Quantum computers [J]. Nature,2010,464(7285):45-53.   
[4]Wiesner S.Conjugate coding [J].ACM SIGACT News,1983,15(1): 78-88.   
[5]Gao Fei,Liu Bin,Wen Qiaoyan.Quantum position verification in bounded-attack-frequencymodel[J].Science China :Physics,Mechanics & Astronomy,2016,59(11):110311.   
[6]Song Xueke,Zhang Hao,Ai Qing，et al.Shortcuts to adiabatic holonomic quantum computation in decoherence-free subspace with transitionless quantum driving algorithm [J].New Journal of Physics, 2016,18(2): 569-577.   
[7]CurtyM,Xu Feihu，Cui Wei,et al.Finite-key analysisfor measurement-device-independent quantum key distribution [J]. Nature Communications,2014,5(4): 643-648.   
[8]Wang Chao，Wang Shuang，Yin Zhenqian，et al.Experimental measurement-device-independentquantum key distributionwith uncharacterized encoding [J]. Optics Letters,2016,41(23): 5596-5599.   
[9]Qin Huawang,Dai Yuewei.Verifiable $( t , n )$ threshold quantum secret sharing using $d$ -dimensional Bell state [J]. Information Processing Letters,2016,116(5):351-355.   
[10] Gao Gan. Secure multiparty quantum secret sharing with the collective eavesdropping-check character [J]. Quantum Information Processing, 2013,12(1): 55-68.   
[11] Gao Fei,Liu Bin,Huang Wei,et al.Postprocessing of the oblivious key in quantum private query [J].IEEE Journal of Selected Topics in Quantum Electronics,2014,21 (3): 98-108.   
[12] Wei Chunyan,Wang Tianyin,Gao Fei. Practical quantum private query with better performance in resisting joint-measurement attack [J]. Physical Review A,2016,93(4): 042318-042324.   
[13] Patwardhan S,Moulick S R,Panigrahi PK.Efficient controlled quantum secure direct communication protocols [J].  International Journal of Theoretical Physics,2016,55(7):3280-3288.   
[14] Cao Zhengwen,Song Dan,Peng Jinye,et al.High security quantum secure direct communication protocol based on three-particle GHZ states [C]//Proc of IEEE,International Conference on Nanotechnology. Piscataway,NJ:IEEE Press,2017:40-43.