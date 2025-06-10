# 攻防博弈驱动下的无线传感器网络病毒传播模型

周海平1，沈士根1，黄龙军1，刘妮²

(1．绍兴文理学院 计算机科学与工程系，浙江 绍兴 312000;2.贵阳学院 数学与信息科学学院，贵阳 550005)

摘要：传统的无线传感器网络（wireless sensor networks，WSN）病毒传播模型直接给定感染概率和恢复概率，没有对其取值的原因进行分析。从博弈论的角度对WSN中病毒传播的微观机理进行分析，建立了WSN的攻防博弈模型，求出了博弈模型的混合纳什均衡解，并根据博弈双方的混合纳什均衡策略确定节点的感染概率和治愈概率，从而建立了WSN的病毒传播模型。此外，还进一步使用元胞自动机的方法对WSN的病毒传播过程进行模拟，理论分析及计算机模拟揭示了病毒传播结果与博弈参数之间的关系，研究结果对制定抑制病毒传播的措施具有一定的指导意义。

关键词：无线传感器网络；病毒传播；攻防博弈；元胞自动机模拟 中图分类号：TP393 doi:10.19734/j.issn.1001-3695.2018.08.0650

Virus propagation model for wireless sensor networks driven by attack-defense game

Zhou Haiping1, Shen Shigen1,Huang Longjun1, Liu $\mathbf { N } \mathbf { i } ^ { 2 }$ (1.Dept.of Computer Science& Engineering，Shaoxing University，Shaoxing Zhejiang 312O00,China;2.Dept.of Mathematic & Information Science, Guiyang College,Guiyang 550oo5,China)

Abstract: In traditional viruspropagation models on Wireless Sensor Networks (WSN),the infection probability and recovery probabilityaregiven directly,andare lackof analysisofthereasons forits value.Fromtheperspectiveofthe game theory,this paper analyzed the microscopic mechanism of virus propagation in WSN.By building and analyzing the atack-defense game model,itobtained the mixed Nash equilibrium solutionof the model.With the solution,itdeduced the infection probabilityandcureprobabilityandthenestablishedthe theoretical model for virus propagation in WSN. Meanwhile,this paper simulated viruses’propagation process with cellular automata method.The theoretical analysis and simulationresults revealed therelationship between the propagation speed and thegameparameters.Theresultsof this study are of significance for people to formulate measures to suppress the propagation of viruses.

Key words: wireless sensor networks; propagation of virus; atack-defense game; celllar automaton

# 0 引言

随着物联网技术的技术的发展，WSN已经成功地应用于交通运输、环境监测、军事侦查等多个领域[1,2]。然而，由于无线传感器节点的存储和计算能力十分有限，很容易受到恶意程序的攻击[3.4]。常见的攻击方式有信道干扰、身份欺骗、病毒传播等多种形式[5.6]。其中恶意病毒传播是一种更为严重的攻击方式，因为一旦某个节点被病毒感染，该节点又会进一步向其他节点传播，导致网络迅速崩溃[7.8]。

至今为止，人们已经分别对WSN的攻防检测及恶意程序传播问题进行了大量研究。WSN的攻防研究方面，张可径等人从博弈论的角度分析了恶意节点与防御系统之间的攻防策略，然后利用演化动力学方法得到了攻防双方的博弈均衡解，对WSN的防御过程有一定的指导价值9。刘怡等人针对工业WSN的能耗攻击问题提出了基于演化博弈的攻防模型，得到了博弈双方的进化稳定策略，为能耗攻击的防御策略提供了可行策略[10]。文献[11]使用数据挖掘技术对DoS攻击进行特征识别，并采用特征选择算法进一步提炼关键特征，该方法在降低时间复杂度的同时提高了DoS攻击的识别率。在病毒传播研究方面，郑榕俊等人利用传染病动力学理论对

WSN 中多种蠕虫病毒传播的行为进行了研究[12]，得到了多种病毒交互作用时的网络传播特性。文献[13]将传统的传染病传播理论应用于WSN中的恶意程序传播过程，作者将恶意程序和入侵检测系统（intrusion detection system,IDS）当作两种相互对抗的智能体，建立了二者之间的微分博弈模型，通过对博弈模型的分析和求解，得到了二者之间的均衡策略，该策略可以在抑制恶意程序的传播的同时降低检测代价。文献[14]提出了一个含个体差异的病毒传播模型，该模型中不同的节点具有不同的抗攻击能力，研究结果显示节点抵抗能力的异质性对病毒传播效果有显著影响。文献[15]对WSN中的移动代理被攻击时病毒的传播过程进行了研究，发现在移动代理被攻击的情况下病毒更容易扩散。

在已有的针对WSN 恶意程序传播的研究中，人们在建立传播模型时通常直接给定节点的感染概率和治愈概率，而没有考虑其背后的微观机理。而对于一个真实的WSN网络来说，感染概率和治愈概率与攻击方和防御方所采取的策略有关，基于这个原因，本文从博弈论的角度分析攻防双方的策略，并基于该策略来确定感染概率和治愈概率，从而揭示博弈参数对传播效率的影响。论文结构安排如下：a）建立WSN中攻防双方的博弈模型，并求取模型的纳什均衡策略;b)基于攻防双方的博弈策略建立WSN的SIS病毒传播模型，通过求解传播模型得到病毒传播速度与博弈参数之间的关系;c）对理论模型进行数值模拟及仿真，并将仿真结果与理论模型的解析结果进行比较与分析。

# 1 WSN的攻防博弈模型

WSN中含有恶意节点与合法节点，其中恶意节点是指感染了病毒的节点，会向合法节点传播病毒，合法节点会利用IDS对接收的信息进行检测。合法节点利用IDS对信息进行检测需要消耗一定的能量，由于节点能量有限，合法节点若对接收的所有信息都进行检测则很快会因能量耗尽而无法工作，为了延长其使用寿命，合法节点会以一定的概率对接收的信息进行检测。对于恶意节点来说，如果其频繁地发起攻击，则很快会暴露自己的身份，因此恶意节点也会以一定的概率发起攻击，由此可见，合法节点与恶意节点之间的攻防过程其实是一种博弈，因此本文利用博弈理论分析它们之间的攻防策略。

定义1WSN中攻防双方的博弈模型可以表示为一个三元组 $\Xi = \left[ { \Nu , \{ { \bf { S } } _ { \mathrm { { i } } } \} , \{ { \bf { u } } _ { \mathrm { { i } } } \} } \right]$ ，其中：

a)N为博弈的参与者集合，对于WSN来说，$N =$ {合法节点，恶意节点}。

b)Si为参与者的策略集合，当i为合法节点时，$S _ { \triangle \dot { \imath } \bar { 2 } \cdot \bar { 1 } \bar { 3 } \bar { 4 } } = \{$ 检测，不检测}，当i为恶意节点时，$S _ { \stackrel { \triangledown } { x \cdot \vec { s } } , \vec { \mathbb { g } } ( \vec { \uparrow } ) , \vec { \mathbb { H } } , \vec { \mathbb { H } } } = \left\{ \begin{array} { l l } { \begin{array} { r l r } \end{array} } \end{array} \right.$ 攻击，不攻击}，需要特别指出的是，此处的不攻击策略不是指恶意节点不发送任何信息，而是指其发送正常信息。

$\mathbf { c } ) u _ { i }$ 为参与者 $i$ 在博弈过程中获得的收益， $u _ { i }$ 的值由博弈双方所采取的策略决定。表1给出了本文用到的一些符号的定义，表2给出了博弈双方的收益矩阵。

Table1Symbolic definition   
表2合法节点与恶意节点的博弈收益表  

<html><body><table><tr><td>符号</td><td>含义</td></tr><tr><td>a</td><td>合法节点检测到病毒获得的收益，恶意节点被识别造成的损失。</td></tr><tr><td>b</td><td>恶意节点攻击成功带来的收益，合法节点感染病毒造成的损失。</td></tr><tr><td>es</td><td>合法节点对收到的信息进行检测所需的能量代价。</td></tr><tr><td>e</td><td>恶意节点发送病毒或正常信息所消耗的能量代价。</td></tr><tr><td>X</td><td>恶意节点发起攻击的概率。</td></tr><tr><td>y</td><td>合法节点进行检测的概率。</td></tr><tr><td>Eus</td><td>合法节点在攻防博弈中的期望收益。</td></tr><tr><td>Eu1</td><td>恶意节点在攻防博弈中的期望收益。</td></tr></table></body></html>

表1符号定义  
Table 2Game payoff for legitimate node and malicious nodt   

<html><body><table><tr><td rowspan="2">合法节点</td><td colspan="2">恶意节点</td></tr><tr><td>攻击</td><td>不攻击</td></tr><tr><td>检测</td><td>a-es，-a-el</td><td>-es，-e</td></tr><tr><td>不检测</td><td>-b， b-e</td><td>0，-e</td></tr></table></body></html>

为了使博弈有意义，模型须满足 $a \geq e _ { S }$ 及 $b \geq e _ { I }$ 这两个条件，因此，当恶意节点发起攻击时合法节点的最佳策略就是进行检测，反之就不进行检测；对于恶意节点来说，当合法节点进行检测时，其最佳策略就是不进行攻击，反之就进行攻击。由于攻防双方互不知道对方会采取何种行动，上述博弈模型不存在纯策略纳什均衡解，下面从混合均衡策略的角度分析博弈双方的攻防行为。

定理1 WSN 中的攻防博弈模型存在混合纳什均衡策略。

证明假设恶意节点以概率 $x$ 进行攻击(传播病毒)，以概率 $_ { 1 - x }$ 不进行攻击（传播正常信息)，合法节点以概率 $y$ 进行检测，以概率 $_ { 1 - y }$ 不进行检测，则根据收益矩阵，合法节点的期望收益 $E u _ { s }$ 为

$$
E u _ { s } = x y ( a - e _ { s } ) + ( 1 - x ) y ( - e _ { s } ) + x ( 1 - y ) ( - b )
$$

恶意节点的期望收益 $E u _ { I }$ 为

$$
\begin{array} { l } { E u _ { I } = x y ( - a - e _ { I } ) + ( 1 - x ) y ( - e _ { I } ) } \\ { \qquad + x ( 1 - y ) ( b - e _ { I } ) + ( 1 - x ) ( 1 - y ) ( - e _ { I } ) } \end{array}
$$

令 Eus=0，得

$$
x ( a - e _ { s } ) + ( 1 - x ) ( - e _ { s } ) - x ( - b ) = 0
$$

整理上式得

$$
x = \frac { e _ { s } } { a + b }
$$

当 $x = \frac { e _ { s } } { a + b }$ 时， Eus =0，合法节点进行检测的期望收益等于不进行检测的期望收益;

当 $x > \frac { e _ { s } } { a + b }$ 时， dEus >0，合法节点进行检测的期望收益大于不进行检测的期望收益;

当 $x < \frac { e _ { s } } { a + b }$ 时， dEus<0，合法进行检测的期望收益低于不进行检测的期望收益。

同理， 令 $\frac { \partial E u _ { I } } { \partial x } = 0$ Eu=0，得

$$
\begin{array} { l } { { y ( - a - e _ { I } ) - y ( - e _ { I } ) + } } \\ { { ( 1 - y ) ( b - e _ { I } ) - ( 1 - y ) ( - e _ { I } ) = 0 } } \end{array}
$$

整理上式得

$$
y = \frac { b } { a + b }
$$

当 $y = \frac { b } { a + b }$ 时， Eu=0，恶意节点发起攻击的期望收益等于不攻击的期望收益；

当 $y > \frac { b } { a + b }$ 时， Eu<0，恶意节点发起攻击的期望收益低于不攻击的期望收益；

当 $y < \frac { b } { a + b }$ 时， Eu>0，恶意节点发起攻击的期望收益高于不攻击的期望收益。

由以上分析可知，合法节点会根据恶意节点的攻击概率决定是否进行检测，而恶意节点也应该根据合法节点进行检测的概率决定是否发起攻击，（x=-s ${ \Bigg ( } x ^ { * } = { \frac { e _ { S } } { a + b } } , y ^ { * } = { \frac { b } { a + b } } { \Bigg ) }$ 便是恶意节点与合法节点进行攻防博弈的混合纳什均衡策略。证毕。

# 2 博弈驱动下的WSN病毒传播模型

由博弈模型可知，恶意节点和合法节点作为理性个体分别会以概率 $x ^ { * }$ 和概率 $y ^ { * }$ 进行攻击和检测，当恶意节点发起攻击而合法节点又没有进行检测时，合法节点就会被感染，而当恶意节点攻击时合法节点开启了检测，则恶意节点会被清除病毒并恢复为合法节点。因此，合法节点被感染的概率为$x ^ { * } ( 1 \mathrm { - y } ^ { * } )$ ，而恶意节点被治愈的概率为 $x ^ { * } y ^ { * }$ 。假设恶意节点占网络中总节点的比例为 $i$ ，合法节点占网络中总节点的比例为 $s$ ，则WSN中的病毒传播演化模型可以用方程组(7)描述。

$$
\left\{ \begin{array} { l l } { \displaystyle \frac { d i } { d t } = x ^ { * } ( 1 - y ^ { * } ) s i - x ^ { * } y ^ { * } s i } \\ { \displaystyle \frac { d s } { d t } = - x ^ { * } ( 1 - y ^ { * } ) s i + x ^ { * } y ^ { * } s i } \\ { \displaystyle i + s = 1 } \end{array} \right.
$$

于是有

$$
\frac { d i } { d t } = x ^ { * } ( 1 - 2 y ^ { * } ) i ( 1 - i )
$$

即

$$
\frac { d i } { i ( 1 - i ) } = x ^ { * } ( 1 - 2 y ^ { * } ) d t
$$

令 $t _ { 0 } = 0$ ，并假设初始时刻的感染比例为 $i _ { 0 }$ ，对方程(9)从 $t _ { 0 }$ 到 $t$ 进行积分得

$$
\ln \frac { i _ { t } } { 1 - i _ { t } } - \ln \frac { i _ { 0 } } { 1 - i _ { 0 } } = x ^ { * } ( 1 - 2 y ^ { * } ) t
$$

对方程(10)进一步求解可得

$$
i _ { t } = \frac { i _ { 0 } } { i _ { 0 } + ( 1 - i _ { 0 } ) e ^ { - x ^ { * } ( 1 - 2 y ^ { * } ) t } }
$$

$x ^ { * } = \frac { e _ { s } } { a + b } \ , \quad y ^ { * } = \frac { b } { a + b }$ 代入上式得

$$
i _ { t } = \frac { i _ { 0 } } { i _ { 0 } + ( 1 - i _ { 0 } ) e ^ { \frac { ( a - b ) e _ { s } } { ( a + b ) ^ { 2 } } t } }
$$

由式(12)可知，病毒的传播过程最终由博弈模型的收益参数决定。通过对式(12)进行数值模拟，得到博弈参数与网络节点感染比例之间的关系如图1\~3所示。当 $a { > } b$ 时(图1)，网络节点的感染比例会随时间的推移达到1，意味着网络中所有节点最终都会被病毒感染，并且此时病毒传播的速度随检测能耗 $e s$ 的增大而变快；当 $\scriptstyle a = b$ 时(图2)，感染比例维持初始值不变，并且不受检测能耗 $e s$ 的变化所影响；当 $a { < } b$ 时（图3)，网络节点的感染比例会随时间的推移达到0，意味着病毒将会在网络中彻底消失，并且此时病毒传播的速度随检测能耗 $e s$ 的增大而变慢。

![](images/2cc29b60f3ac4228aecd9ade78b46c80504037ef6252f41468c093de2ed29bc5.jpg)  
图1 $a { > } b$ 时感染节点比例随时间的变化趋势（ $a = 3 . 0 , b = 2 . 0$ ）Fig.1Trend of infection node ratio over time for $a { > } \mathbf { b }$ （ $\scriptstyle a = 3 . 0 , b = 2 . 0 )$ ：

![](images/78943d60a7a6180fea5e1fff254930873daa6b7078256d8a0f11809ac7c65a2c.jpg)

# 3 元胞自动机模拟

前面的理论模型虽然可以较好地描述WSN中恶意程序传播的过程，但仍然存在一些局限，例如，真实的传感器节点的通信半径是有限的，节点只能与其附近的节点通信，而理论模型没有考虑这个问题，另外对于有些传感器网络来说，节点可以移动，因此网络是动态变化的，现有的理论模型也无法处理这个问题。为了使研究结果与真实场景更接近，本节使用元胞自动机方法对WSN的病毒传播过程进行模拟。

![](images/49c501b046c244768b21f2f527f5ff9303e8ff1f77b5d58fee127fdcaef20a6f.jpg)  
图3 $a { < } b$ 时感染节点比例随时间的变化趋势（ $a { = } 2 . 0 , b { = } 3 . 0$ ）Fig.3Trend of infection node ratio over time for $a { < } { \boldsymbol { \mathbf { b } } }$ $( a = 2 . 0 , b = 3 . 0 )$ ·

# 3.1模拟步骤

a)生成一个如图4所示的 $1 0 0 \times 1 0 0$ 的网格，随机选择比例为 $p _ { w }$ 的格子布设传感器节点.

b)任意两个传感器节点之间的距离如果不超过 $\boldsymbol { r }$ 则产生连接关系，由此确定传感器网络的结构。

c)在初始时刻，随机设置比例为i0的节点为恶意节点。

d)每个恶意节点随机选择一个与其直接相连的节点发送信息，其中发送恶意信息的概率为 $x ^ { * }$ ，发送正常信息的概率为 $1 - x ^ { * }$ 。

e)当恶意节点向恶意节点发送信息时，信息会被丢弃，而当恶意节点向合法节点发送信息时，合法节点会以概率 $y ^ { * }$ 进行检测。当合法节点接收到的是病毒且正好没有进行检测时就会被感染，当合法节点对收到的病毒进行检测时，恶意节点会被识别，被识别的恶意节点会被修复，从而又转换为合法节点。

f)若 $\mathbf { \Psi } _ { t }$ 小于预设的模拟步数，则 $\mathbf { \Psi } _ { t }$ 的值增加1，并转入步骤d)继续执行，否则，结束运行。

# 3.2模拟结果

设定参数 $p _ { \mathrm { { w } } } \mathrm { { = } } 0 . 1$ ， $\scriptstyle { i o = 0 . 0 5 }$ ，执行上述模拟步骤，考查博弈参数对病毒传播结果的影响。模拟结果如图5\~7所示。从图中可以看出，当 $a { > } b$ 时，随着时间的推移，网络中恶意节点的比例不断增加，最终所有节点都被病毒感染，并且病毒的传播速度随检测能耗 $E s$ 的增大而加快；当 $\scriptstyle a = b$ 时，随时间的推移，网络中恶意节点的比例始终在初始感染比例附近上下波动；当 $a { < } b$ 时，随着时间的推移，网络中恶意节点的比例不断减少，最终所有节点都变为合法节点。该结论与上一节的理论研究结果一致。

另外，由于WSN中病毒的传播过程与通信半径有关，本文进一步研究了传感器节点的通信半径对病毒传播速度的影响，通过改变通信半径的值，得到了不同通信半径下病毒的传播曲线，从图8可以看出，在其他参数固定的情况下，病毒的传播速度随着通信半径的增加而增大。

![](images/a681414139f1641934637554b83a8973bcdcacb6ece6cfe8bb29e4be28df3241.jpg)  
图2 $\scriptstyle a = b$ 时感染节点比例随时间的变化趋势（ $a { = } 2 . 0 , b { = } 2 . 0$ ）Fig.2Trend of infection node ratio over time for $\scriptstyle a = { \boldsymbol { \mathsf { b } } }$ （ $a { = } 2 . 0 , b { = } 2 . 0 )$ ：  
图4无线传感器节点分布图(灰色为正常节点，黑色为恶意节点) Fig.4Distribution of wireless sensor nodes (gray presents normal node,blackpresents malicious node)

![](images/ee150ae36ab09274a0e996e5c5bea7b57d5566fb1962619163cb679fd1094c36.jpg)  
图5 $a { > } b$ 时感染节点比例随时间的变化趋势（ $a { = } 3 . 0 , b { = } 2 . 0 , r { = } 5 ^ { \cdot }$ ）

![](images/f028f24cf971e985ca563607ba970dae261582ae3e81e9ab7c831d45e42e3691.jpg)

![](images/5f061454b5f91415354729d275b6a4d70558adeebb9faa69bd2ca4f4eef01708.jpg)  
Fig.5Trend of infection node ratio over time for $a { > } \mathbf { b }$ $( a = 3 . 0 , b = 2 . 0 , r = 5 )$ 1   
Fig.6Trend of infection node ratio over time for $a = b$ （204 $( a = 2 . 0 , b = 2 . 0 , r = 5 )$ 0   
图7 $a { < } b$ 时感染节点比例随时间的变化趋势（ $\cdot a { = } 2 . 0 , b { = } 3 . 0 , r { = } 5$

![](images/3a9df04d99d7c9d169c183e1a392570aa1f9f6ec34d0070c56e90ba0084520f7.jpg)  
图6 $\scriptstyle a = b$ 时感染节点比例随时间的变化趋势（ $a { = } 2 . 0 , b { = } 2 . 0 , r { = } 5$ ）  
Fig.7The trend of infection node ratio over time for $a { < } \mathbf { b }$   
图8通信半径对病毒传播速度的影响（ $e s = 2 . 0 , a = 3 . 0 , b = 2 . 0 \$ ）Fig.8Influence of communication radius on virus propagation speed.（20 $( \ e _ { s } = 2 . 0 , a = 3 . 0 , b = 2 . 0 )$ 0

# 4 讨论

# 4.1理论结果与模拟结果的比较

从整体规律上看，前面的理论研究结果和元胞自动机模拟的结论是一致的，但是在细节上还是会有一些差异，例如：在a>b时，理论模型中病毒的传播速度要大于元胞自动机模拟的传播速度，其原因如下：a）理论模型中任意两节点之间是直接相连的，节点之间可以充分混合，而元胞自动机模型中只有距离相近的节点才能直接通信，当某个节点附近的节点都已经被感染时，就不能进一步传播病毒;b）在元胞自动机模型中，随着传播的进行，恶意节点之间会聚集成簇，这种聚集效应也会阻碍病毒迅速传播。

# 4.2博弈参数对病毒传播过程的影响

本文的研究揭示了博弈驱动下的WSN的病毒传播特点：当合法节点检出病毒的收益a大于其被病毒感染的损失b时，病毒传播的范围会不断扩张，直至所有节点都被感染，反之，病毒传播的范围会不断缩小，直至病毒消失。解释如下：由第2章的博弈模型可知，在攻防博弈中，恶意节点会以概率$x ^ { * }$ 传播病毒，而合法节点会以概率 $y ^ { * }$ 进行检测，因此，感染概率为 $x ^ { * } ( 1 - y ^ { * } ) = \frac { a e _ { s } } { \left( a + b \right) ^ { 2 } }$ ，治愈概率为 $x ^ { * } y ^ { * } = \frac { b e _ { s } } { \left( a + b \right) ^ { 2 } }$ ，当 $a { > } b$ 时，感染速度大于治愈速度，病毒会在网络中蔓延，反之，当 $a { < } b$ 时，感染速度小于治愈速度，网络感染节点的比例就会不断减小。值得指出的是，在判断某个博弈参数的变化对传播速度的影响时，不能只根据某一方可能采取的行动进行推断，而必须综合考虑双方的行动。例如，在 $a { > } b$ 的情况下，当检测能耗 $e s$ 增大时，合法节点为了节约能量理应降低检测的概率，但这会促使恶意节点提高攻击概率，从而造成合法节点更大的损失，由混合纳什均衡策略可知，双方最终的博弈结果是合法节点保持检测概率不变，而恶意节点提高了攻击概率，从而使病毒的传播速度变快。

# 5 结束语

本文从博弈论的角度对 WSN 中的病毒传播过程进行了研究，得到了以下结论：a）WSN中恶意节点与合法节点之间的攻防博弈模型存在混合纳什均衡解;b)WSN中病毒传播结果与攻防博弈的收益参数有关，当合法节点检出病毒的收益大于其被病毒感染的损失时，感染比例会持续增加，直至所有节点都被感染，反之，感染比例会持续减少，直至所有恶意节点消失，该结论对制定抑制WSN 病毒传播的措施具有一定的理论指导作用。

# 参考文献：

[1]钱志鸿，王义君．面向物联网的无线传感器网络综述[J]．电子与信 息学报,2013,35(1):215-227.(Qian Zhihong,Wang Yijun.Internet of Things-oriented Wireless Sensor Networks Review [J].Journal of Electronics & Information Technology,2013,35(1):215-227.)   
[2]洪锋，褚红伟，金宗科，等．无线传感器网络应用系统最新进展综述 [J]．计算机研究与发展，2010,47(S2):81-87.(Hong Feng，Chu Hongwei,Jin Zongke,et al.Review of Recent Progress onWireless Sensor Network Applications [J]. Journal of Computer Research and Development,2010,47(S2): 81-87.)   
[3]张焕国,韩文报,来学嘉,等．网络空间安全综述[J]．中国科学：信息 科学,2016,46(2):125-164.(Zhang Huanguo,Han Wenbao,Lai Xuejia, et al.Review of Cyberspace Security[J].Scientia Sinica: Informationis, 2016,46(2):125-164.)   
[4]李化邓，李雷，施化吉，等．无线传感器网络的生存性评估[J].计算 机应用研究,2018,35(8):2450-2453.(Li Huadeng,LiLei,Shi Huaji, etal.Survivabilityevaluation inwirelesssensor network [J]. Application Research of Computers,,2018,35(8):2450-2453.)   
[5]沈士根，刘建华，曹奇英．博弈论与无线传感器网络安全[M]．北 京：清华大学出版社，2016.(Shen Shigen,Liu Jianhua,Cao Qiying. Gametheory and wireless sensor network security [M].Beijing: TsinghuaUniversityPress,2016.)   
[6]Abdalzaher M,Seddik K,Elsabrouty M,et al.Game theory meets wireless sensor networks security requirements and threats mitigation: A survey[J].Sensors.2016,16(7):1-27.   
[7]沈士根，周海平，黄龙军，等．基于最优反应均衡的传感网恶意程序 传播抑制方法[J].传感技术学报．2017，30(10):1589-1595.(Shen Shigen,Zhou Haiping,Huang Longjun，et al.Quantal Response Equilibrium-BasedMethod forPreventingWSNMalware Infection [J]. Chinese Journal of Sensors and Actuators,2017,30(10):1589-1595.)   
[8]Singh A,Awasthi A,Singh K,et al.Modeling and analysis of worm propagation in wirelesssensor networks[J].Wireless Personal Communications,2018,98(3),2535-2551.   
[9]张可径，曹奇英，沈士根．基于演化博弈的WSN攻防策略选择动力 学分析[J].计算机应用与软件，2017,34(9):132-137.(Zhang Kejing, Cao Qiying，Shen Shigen.Dynamic analysis of attack and defense strategy selection for WSN based on evolutionary game[J].Computer Applications and Software,2017,34(9):132-137.)   
[10]刘怡，林德钰．基于进化博弈论的工业无线传感网能耗攻防研究 [J]．测控技术,2018,37(4): 58-63.(Liu Yi,Lin Deyu.Defense against energy exhausting attack based on the evolutionary game theory for the industrial wireless sensor network[J].Measurement and Control ItuHuiugy,∠U1o,5/(+).Jo-u5.)   
[11] Sedjelmaci H, Senouci S,Ansari N.Intrusion detection and ejection framework against lethal attacks in UAV-aided networks:a bayesian game-theoreticmethodology[J].IEEETransonIntelligent Transportation Systems,2017,18(5):1143-1153.   
[12]郑榕俊，陈志德，马金花.无线传感器网络中n蠕虫传播模型[J].计 算机应用．2015，35(S2):62-64.(Zheng Rongjun，Chen Zhide，Ma Jinhua.N-worm propagation model in wireless sensor networks [J]. Journal of Computer Applications,2015,35(S2):62-64.)   
[13] Shen S,Li H,Han R,et al.Differential game-based strategies for preventing malware propagation in wireless sensor networks [J].IEEE Trans on Information Forensics and Security,2014,9(11):1962-1973.   
[14]周海平，蔡绍洪，龙艳．个体差异对病毒传播效率的影响[J]．计算 机应用研究,201,28(10):3797-3798.(Zhou Haiping Cai Shaohong, Long Yan.Effect of individual difference on virus'spreading efficiency [J].Application Research of computers,2011,28(10):3797-3798.)   
[15]Wang T,Wu Q,Wen S,et al.PropagationModeling andDefending of a Mobile Sensor Worm in Wireless Sensor and Actuator Networks [J]. Sensors,2017,17(12):139-155.