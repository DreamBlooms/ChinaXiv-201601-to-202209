# 基于社交平台谣言抑制策略的传播模型及仿真研究\*

杨仁彪¹，尹春晓

(1.西南大学计算机与信息科学学院，重庆 400715；2.西南大学教育学部，重庆400715)

摘要：【目的/意义】社交媒体环境下网络谣言传播速度快、范围广，严重扰乱社会秩序，因此如何治理网络谣言成为网络社会管理中亟待解决的难题。本文从社交平台谣言抑制策略的视角探究网络谣言治理的方法，为人们科学有效地控制谣言传播提供参考建议。【方法/过程】本文基于社交平台谣言抑制策略（警告和封号)，提出了改进的 $S _ { Ḋ } \mathrm { I C _ { 1 - 2 } R } Ḍ$ 传播模型，然后分析了模型中的谣言平衡点并加以证明。最后利用matlab2021a进行仿真实验研究。【结果/结论】结果表明，新模型存在四个谣言传播平衡点（无谣言平衡点 $\mathrm { E } _ { 0 }$ 、封号前平衡点 $\mathrm { E } _ { 1 }$ 、解封前平衡点$\mathbf { E } _ { 2 }$ 以及解封后平衡点 $\mathrm { E } _ { 3 }$ ）并通过仿真实验得到验证。同时，模型内部相关参数以及时间因素均对谣言传播过程产生重要影响。【创新/局限】创新之处有两点：

（1）基于社交平台的谣言抑制策略（警告和封号）改进了传统 SIR 传播模型;（2）分阶段（封号前、解封前及解封后）讨论了模型中谣言平衡点的稳定性。局限主要在于实验中所采用的数据均为模拟值，部分参数依据经验设定，而且仅从平台的角度探讨了网络谣言的治理策略，研究结论不够全面。关键词：谣言传播；社交平台；抑制策略；MATLAB仿真分类号：G206

# 1引言

谣言是“在特定的环境下，以公开或非公开渠道传播的对公众感兴趣的事物、事件或问题的未经证实的阐述或诠释”[I。网络谣言的大规模传播是多主体共同参与的结果，其中既包括躲在幕后推波助澜的网络推手，也包括数量庞大的普通传播者。网络谣言的传播会引发公众的恐慌与不安情绪、损害政府的公信力等，继而影响社会稳定，带来损失[2]。因此，网络谣言治理已经成为网络社会管理无法回避的重要议题之一。当前相关研究多从辟谣策略[3]、辟谣模式[4]、辟谣效果[5-7]等视角出发，辟谣主体主要局限于政府、媒体两个方面[8]，少有学者从社交平台谣言抑制策略的角度探讨网络谣言治理。因此，本文基于社交平台谣言抑制策略（警告和封号)，提出了改进的 $\mathrm { S I C } _ { 1 - 2 } \mathrm { R }$ 传播模型，并进行仿真研究。本研究理论上能够丰富现有谣言传播模型的研究视角，实践上可以为社交平台的网络谣言治理提供一定的参考与指导。

# 2 文献回顾

# 2.1谣言传播模型相关研究

网络谣言被称为“信息病毒”，其传播途径、传播方式与生物病毒十分相似，因此谣言传播的研究大多也是基于病毒传播模式[9]。这方面研究最早可以追溯到20 世纪60 年代提出的DK模型[10]以及后来的MK 模型[11]。此后多数研究在研究思路和研究方法上都借鉴和参考了上面两个模型。当前学者们主要从三个方面对经典传播模型进行延伸。

首先是扩展或者再细分模型中的节点状态类型。例如，廖圣清等在SIR 模型基础上加入辟谣者的角色，构建了SIAR传播模型[12]。顾亦然等在易感状态 S 和感染状态I之间加入了潜伏状态E，提出了 SEIR 谣言传播模型[13]。考虑到传谣者对谣言的信任程度有所不同，唐梁鸿绪等将传谣者进一步区分为潜在传谣者和铁杆传谣者[14]。

其次是考虑模型中节点的行为属性，这也是谣言传播区别于病毒传播的主要特征。例如，屈楠伟等在信息行为模型的基础上引入用户的质疑行为，发现用户质疑行为在一定范围内能够提高辟谣效果，但是过度的质疑也会起到相反的效果[15]。王祁月等在模型中考虑了抑制者的沉默概率，指出谣言的传播会随着沉默概率的增大而突然爆发[16]。Nekovee 等将用户遗忘机制作为影响变量纳入分析，结果表明谣言在无标度网络中传播的初始速率远远高于在均匀网络中的传播速率[17]。

最后是考虑外部环境变量的扰动，主要从政府和媒体两个角度进行研究。例如，王晰巍等在 SIR 模型的基础上提出具有逆转效应的 SCNDR 模型，分析了官方辟谣时间对谣言逆转效率的影响[18]。赵敏等考虑媒体报道效应（正面报道和负面报道）对谣言传播的影响，分别讨论了有谣言传播和无谣言传播两种情况下平衡点的存在性和稳定性[19]。

# 2.2社交平台谣言抑制策略研究

网络谣言传播过程中，如果社交平台不采取任何抑制措施，那么对于网络社区环境以及平台运行秩序都将产生严重干扰。当前社交平台常用的谣言抑制措施主要包括警告和封号两种方式。警告是指社交平台对参与传播谣言的用户贴上具有警示意味的词语（例如“异常”“危险”“小心”等）或者是将用户页面进行特殊化显示（例如以红色、黄色、橙色、绿色分别表示不同用户的风险等级），从而降低传谣者发布信息可信度以及人们的转发意愿。研究表明，警告标签将唤醒用户“危险”感知的潜意识或者促使用户对当前事物进行更加周密的思考，从而能够有效降低社交媒体中谣言的可信度[20]。

封号是一种更为严格的谣言抑制策略，主要针对的是多次违规且违规情形十分严重的谣言传播者，通过在一定期限内禁止其发言、评论、转发及点赞等各项权利以达到惩罚的目的。封号期限通常依据用户违规次数或者违规程度而定，比如15天或者30天，甚至永久封号。封号意味着用户在网络这个虚拟世界中生命的临时“终结”，容易唤起用户潜意识中对于死亡的本能恐惧[21]。因此，与警告相比，封号对于那些试图制造或者转发谣言的人能够起到更大的威慑作用。

实践中社交平台一般不会单独采取某一种谣言抑制策略，而是会根据实际情况将两种策略搭配运用，最大程度地遏制谣言传播。

# 2.3文献评述

现有的相关研究为本文提供了很好的借鉴，但仍然存在如下三点不足。

第一，现有关于谣言传播模型的文献主要关注政府、媒体以及用户等因素对谣言传播过程的影响，少有学者从社交平台角度进行研究。社交平台作为网络谣言产生与传播的主要渠道，对于网络谣言治理具有非常重要的作用，需要研究者的关注。

第二，目前对于社交平台谣言治理的研究主要集中于网络辟谣相关主题，比如辟谣策略、辟谣方式以及辟谣效果等，少有学者研究警告与封号策略对于遏制谣言传播的影响。

因此，本研究首先在传统 SIR 模型基础上，引入受限者C（即受到平台警告或者封号措施限制的用户）这一新的人群状态，提出 $\mathrm { S I C } _ { 1 - 2 } \mathrm { R }$ 模型，然后分阶段求解出谣言传播模型的平衡点并对其稳定性进行理论推导，最后利用matlab2021a进行仿真实验，验证了平衡点的稳定性。此外，本研究还分析了模型中各参数对谣言传播过程的影响并进一步对影响因素进行了归纳总结。研究结果能够丰富谣言传播相关研究，为今后类似研究提供参考借鉴，同时也能为社交平台高效开展谣言治理工作提供一定的理论指导。

# 3模型构建

# 3.1模型中的用户状态类型

本研究在传统谣言传播模型 SIR 基础上引入新的传播节点C（受限者），即表示受到社交平台谣言抑制措施限制的用户群体，并根据用户所受限制的不同，进一步将其细化为 $\mathrm { C } _ { 1 }$ 、 $\mathbf { C } _ { 2 }$ 。其中Ci表示受到警告惩罚的用户节点， $\mathrm { C } _ { 2 }$ 表示受到封号惩罚的用户节点。因此，本研究中的所有节点分为以下几种类型：

无知者（S)：网民群体中，没有了解过谣言内容，从未参与过谣言话题的讨论，但在接触到谣言信息后容易转变为谣言传播者的节点。

传播者（I)：接触到谣言信息后，主动将谣言信息传递给其他人的节点。

受限者（C)：由于出现违规行为而受到平台谣言抑制措施限制的用户节点，主要包括 $\mathrm { C } _ { 1 }$ 和 $\mathrm { C } _ { 2 }$ 。

免疫者（R)：熟悉了谣言内容，但是已经不受其影响并且不再传播谣言信息的节点。

# 3.2模型中的相关参数

传播模型中的参数如表1所示。

Table1 Parameter descriptions   

<html><body><table><tr><td>参数</td><td>参数说明</td></tr><tr><td>α1</td><td>谣言传播率</td></tr><tr><td>α2</td><td>受限传播率</td></tr><tr><td>β</td><td>平台警告率</td></tr><tr><td>X</td><td>平台封号率</td></tr><tr><td>8</td><td>限制升级率</td></tr><tr><td>m</td><td>用户复阳率</td></tr><tr><td>1</td><td>I的免疫率</td></tr><tr><td>2</td><td>C1的免疫率</td></tr><tr><td></td><td>C的免疫率</td></tr></table></body></html>

谣言传播率（ $\cdot \alpha _ { 1 }$ )：当无知者S接触到传播者I传递的谣言信息后转变为传播者的概率。

受限传播率（ $( \alpha _ { 2 }$ )：无知者S接触到受限者Ci传播的谣言信息后转变为传播者的概率。

平台警告率(β)：当社交平台发现用户违规传播谣言信息，但是违规程度相对较轻，因此对其采取警告措施的概率。

平台封号率 $( \chi )$ ：当平台发现用户涉嫌违规，且违规情形十分严重时，平台对其进行封号的概率。

限制升级率（8)：被警告的用户再次出现违规行为，且已经达到封号的程度，平台决定将警告升级为封号的概率。

用户复阳率(ε)：“复阳率”一词借鉴病毒传播学中的概念，但含义略有差别，病毒学中的“复阳率”是指患者达到康复标准或病毒检测结果为阴性之后，在没有接触传染源的情况下重新成为传播者的概率，而本文主要是指受到封号处理的用户在期限届满之后，重新变回谣言传播者的概率。

用户免疫率 $( \phi )$ ：由于多种原因对谣言内容失去兴趣，其他状态节点转化为谣言免疫者的概率。

# 3.3传播模型的演化规则及假定

在谣言传播节点分类以及参数设置的基础上，本文构建了 $\mathrm { S I C } _ { 1 - 2 } \mathrm { R }$ 谣言传播模型（见图1)。模型的演化规则与假定如下：

（1）当无知者S接触到传播者I以后，会以 $\alpha _ { 1 }$ 的概率传播谣言，成为谣言传播者；当无知者S接触的不是传播者I而是限制者 $\mathrm { C } _ { 1 }$ 时，由于受到平台的警告（例如警示标签)，无知者对其信任度较低，会以 $\alpha _ { 2 }$ 的概率传播谣言，成为谣言传播者（图中虚线表示无知者不会直接成为限制者 $\mathrm { C } _ { 1 }$ ，而是先变成传播者I)。

（2)传播者传播谣言以后，平台可能会对其进行惩罚。对于违规情形较轻者，给予警告处理；对于情形较重者，给予封号处理。当受到警告的用户再次违规时，平台将升级惩罚措施，给予封号处理。

（3）假定平台采取警告措施的时间从 $\mathrm { t } = 0$ 时刻开始，而采取封号措施的时间从 $t = t _ { 0 }$ 时刻开始，并且封号期限为T。在封号期限内，用户被禁止发言、评论、转发及点赞等各项权利，即丧失传播谣言的能力。当封号期限结束以后，用户可能会重新变回谣言传播者。

（4）谣言传播者I、受限者Ci以及受限者 $\mathrm { C } _ { 2 }$ 由于对谣言内容失去兴趣或者畏惧平台惩罚措施，不再传播谣言信息，从而变为免疫者

![](images/3a6b811ba6079ee215aa2b785766152060fba92f4b41ed6e176c8aa0d518a282.jpg)  
Figure $1 \mathrm { S I C } _ { 1 - 2 } \mathrm { R }$ propagation model   
图1SICi-2R传播模型

根据上述对所有群体的分类以及模型演化规则的描述，本文构建了如下传播模型的微分动力学方程。谣言刚开始传播，平台尚未采取封号措施，即封号之前的微分动力学方程，

$$
\begin{array} { l } { \displaystyle \frac { \mathrm { d } S } { \mathrm { d } t } = \lambda - \alpha _ { 1 } S ( t ) I ( t ) - \alpha _ { 2 } S ( t ) C _ { 1 } ( t ) - \mu S ( t ) } \\ { \displaystyle \frac { \mathrm { d } I } { \mathrm { d } t } = \alpha _ { 1 } S ( t ) I ( t ) + \alpha _ { 2 } S ( t ) C _ { 1 } ( t ) - ( \beta + \phi _ { 1 } ) I ( t ) } \\ { \displaystyle \frac { \mathrm { d } C _ { 1 } } { \mathrm { d } t } = \beta I ( t ) - \phi _ { 2 } C _ { 1 } ( t ) } \\ { \displaystyle \frac { \mathrm { d } R } { \mathrm { d } t } = \phi _ { 1 } I ( t ) + \phi _ { 2 } C _ { 1 } ( t ) } \end{array}
$$

谣言扩散之后，平台开始封号，但处于封号期限内的微分方程

$$
\begin{array} { l } { \displaystyle \frac { \mathrm { d } S } { \mathrm { d } t } = \lambda - \alpha _ { 1 } S ( t ) I ( t ) - \alpha _ { 2 } S ( t ) C _ { 1 } ( t ) - \mu S ( t ) } \\ { \displaystyle \frac { \mathrm { d } I } { \mathrm { d } t } = \alpha _ { 1 } S ( t ) I ( t ) + \alpha _ { 2 } S ( t ) C _ { 1 } ( t ) - ( \beta + \chi + \phi _ { 1 } ) I ( t ) } \\ { \displaystyle \frac { \mathrm { d } C _ { 1 } } { \mathrm { d } t } = \beta I ( t ) - ( \delta + \phi _ { 2 } ) C _ { 1 } ( t ) } \\ { \displaystyle \frac { \mathrm { d } C _ { 2 } } { \mathrm { d } t } = \chi I ( t ) + \delta C _ { 1 } ( t ) - \phi _ { 3 } C _ { 2 } ( t ) } \\ { \displaystyle \frac { \mathrm { d } R } { \mathrm { d } t } = \phi _ { 1 } I ( t ) + \phi _ { 2 } C _ { 1 } ( t ) + \phi _ { 3 } C _ { 2 } ( t ) } \end{array}
$$

封号期限结束以后的微分方程，

$$
\begin{array} { l } { \displaystyle \frac { \mathrm { d } S } { \mathrm { d } t } = \lambda - \alpha _ { 1 } S ( t ) I ( t ) - \alpha _ { 2 } S ( t ) C _ { 1 } ( t ) - \mu S ( t ) } \\ { \displaystyle \frac { \mathrm { d } I } { \mathrm { d } t } = \alpha _ { 1 } S ( t ) I ( t ) + \alpha _ { 2 } S ( t ) C _ { 1 } ( t ) + \varepsilon C _ { 2 } ( t ) - ( \beta + \chi + I _ { 2 } ) I ( t ) } \\ { \displaystyle \frac { \mathrm { d } C _ { 1 } } { \mathrm { d } t } = \beta I ( t ) - ( \delta + \phi _ { 2 } ) C _ { 1 } ( t ) } \\ { \displaystyle \frac { \mathrm { d } C _ { 2 } } { \mathrm { d } t } = \chi I ( t ) + \delta C _ { 1 } ( t ) - ( \varepsilon + \phi _ { 3 } ) C _ { 2 } ( t ) } \\ { \displaystyle \frac { \mathrm { d } R } { \mathrm { d } t } = \phi _ { 1 } I ( t ) + \phi _ { 2 } C _ { 1 } ( t ) + \phi _ { 3 } C _ { 2 } ( t ) } \end{array}
$$

上式中的 S(t)、I(t)、C1(t)、 $\mathbf { C } _ { 2 } ( \mathrm { t } )$ 、R(t)分别表示在t时刻无知者 S、传播者I、受限者 $\mathbf { C } _ { 1 }$ 、受限者 $\mathbf { C } _ { 2 }$ 以及免疫者R占总人数的比例，且$\mathrm { S ( t ) } + \mathrm { I ( t ) } + \mathrm { C } _ { 1 } ( \mathrm { t ) } + \mathrm { C } _ { 2 } ( \mathrm { t } ) + \mathrm { R ( t ) } = \lambda - \mu \mathrm { S ( t ) } \circ$

# 4传播模型的平衡点及稳定性分析

# 4.1模型的传播阈值与平衡点

借鉴传染病学中基本再生数的定义，将其定义为单个传播者在传播周期内感染未知者的人数。参考现有文献[22]关于基本再生数的求解方法，本文计算得出谣言传播模型在开始封号之前的基本再生为：

$$
R _ { 0 } ^ { 1 } = \alpha _ { 1 } \lambda / \mu ( \beta + \phi _ { 1 } )
$$

而平台采取封号措施之后的基本再生数为：

$$
R _ { 0 } ^ { 2 } = \alpha _ { 1 } \lambda / \mu ( \beta + \chi + \phi _ { 1 } )
$$

考虑到模型的实际背景，将在有界区域 $D = \{ \textit { \textbf { ( S , I , C _ { 1 } , C _ { 2 } , R ) } } | S \geq 0 ,$ $I \geq$ 0， $C 1 \geq 0$ ， $C 2 \geq 0$ ， $R \geq 0 ]$ 寻找平衡点。

（1）无谣言传播平衡点。当 $R _ { 0 } ^ { 1 } < 1$ 时，模型的无谣言传播平衡点为 ${ { E } _ { 0 } } =$ $( \lambda / \mu , 0 , 0 )$

（2）内部平衡点。当 $R _ { 0 } ^ { 1 }$ 、 $R _ { 0 } ^ { 2 } > 1$ 时，分别令式（1）～（3）中所有等式左边为0可以求得系统的内部平衡点。

1）当 $\mathsf { C } _ { 1 } \neq 0$ ， $\mathsf C _ { 2 } \mathsf = 0$ 时，即平台开始封号之前，存在谣言平衡点 $E _ { 1 } =$ $( S _ { ( 1 ) } ^ { * } , I _ { ( 1 ) } ^ { * } , C 1 _ { ( 1 ) } ^ { * } ) ,$ （204

其中：

$$
\begin{array} { l } { \displaystyle { S _ { ( 1 ) } ^ { * } = \frac { \phi _ { 2 } ( \beta + \phi _ { 1 } ) } { \alpha _ { 1 } \phi _ { 2 } + \alpha _ { 2 } \beta } , } } \\ { \displaystyle { I _ { ( 1 ) } ^ { * } = \frac { \big ( \lambda - \mu S _ { ( 1 ) } ^ { * } \big ) \big ( S _ { ( 1 ) } ^ { * } + \phi _ { 2 } \big ) } { \alpha _ { 1 } \phi _ { 2 } S _ { ( 1 ) } ^ { * } + \alpha _ { 2 } \beta S _ { ( 1 ) } ^ { * } } , } } \end{array}
$$

$$
\begin{array} { r } { C 1 _ { ( 1 ) } ^ { * } = \frac { \beta I _ { ( 1 ) } ^ { * } } { \phi _ { 2 } } } \end{array}
$$

2）当 $\mathsf { C } 1 \neq \mathsf { 0 }$ ， $C _ { 2 } { \neq } 0$ 时，即平台已经采取了封号措施，此时存在两个谣言平衡点，分别为解封前谣言平衡点 $E _ { 2 }$ 和解封后的谣言平衡点 $E _ { 3 }$ 。

$$
E _ { 2 } = \bigl ( S _ { ( 2 ) } ^ { * } , I _ { ( 2 ) } ^ { * } , C 1 _ { ( 2 ) } ^ { * } , C 2 _ { ( 2 ) } ^ { * } \bigr ) , E _ { 3 } = \bigl ( S _ { ( 3 ) } ^ { * } , I _ { ( 3 ) } ^ { * } , C 1 _ { ( 3 ) } ^ { * } , C 2 _ { ( 3 ) } ^ { * } \bigr )
$$

其中,

$$
\begin{array} { l } { { S _ { ( 2 ) } ^ { * } = \displaystyle \frac { ( \beta + \chi + \phi _ { 1 } ) ( \delta + \phi _ { 2 } ) } { \alpha _ { 1 } ( \delta + \phi _ { 2 } ) + \alpha _ { 2 } \beta } \ } } \\ { { I _ { ( 2 ) } ^ { * } = \displaystyle \frac { \big ( \lambda - \mu S _ { ( 2 ) } ^ { * } \big ) \big ( S _ { ( 2 ) } ^ { * } + \phi _ { 2 } \big ) } { \alpha _ { 1 } \phi _ { 2 } S _ { ( 2 ) } ^ { * } + \alpha _ { 2 } \beta S _ { ( 2 ) } ^ { * } } } } \end{array}
$$

$$
, C 1 _ { ( 2 ) } ^ { * } = \frac { \beta I _ { ( 2 ) } ^ { * } } { ( \delta + \phi _ { 2 } ) }
$$

$$
C 2 _ { ( 2 ) } ^ { * } = ( \frac { \chi } { \phi _ { 3 } } + \frac { \beta } { \phi _ { 3 } ( \delta + \phi _ { 2 } ) } ) I _ { ( 2 ) } ^ { * }
$$

$$
\begin{array} { l } { { S _ { ( 3 ) } ^ { \prime } = \frac { ( \beta + \chi + \phi _ { 1 } ) ( \delta + \phi _ { 2 } ) } { \alpha _ { 1 } ( \delta + \phi _ { 2 } ) + \alpha _ { 2 } \beta } - \frac { \varepsilon \chi ( \delta + \phi _ { 2 } ) } { ( \alpha _ { 1 } ( \delta + \phi _ { 2 } ) + \alpha _ { 2 } \beta ) ( \varepsilon + \phi _ { 3 } ) } } } \\ { { \ \ } } \\ { { \qquad \quad \ \qquad - \frac { \beta \varepsilon \delta ( \delta + \phi _ { 2 } ) } { ( \alpha _ { 1 } ( \delta + \phi _ { 2 } ) + \alpha _ { 2 } \beta ) ( \delta + \phi _ { 2 } ) ( \varepsilon + \phi _ { 3 } ) } } } \\ { { \ \ } } \\ { { I _ { ( 3 ) } ^ { * } = \frac { ( \lambda - \mu S _ { ( 3 ) } ^ { * } ) \bigl ( S _ { ( 3 ) } ^ { * } + \phi _ { 2 } \bigr ) } { \alpha _ { 1 } \phi _ { 2 } S _ { ( 3 ) } ^ { * } + \alpha _ { 2 } \beta S _ { ( 3 ) } ^ { * } } } } \\ { { \ \ } } \\ { { \ \ } } \\  { { \therefore \ C _ { ( 3 ) } ^ { 1 } = \frac { \beta I _ { ( 3 ) } ^ { * } } { ( \delta + \phi _ { 2 } ) } \qquad \mathrm { ~ f o r ~ } \qquad \mathrm { ~ } } } \\ { { \ } } \\ { { C _ { ( 3 ) } ^ { 2 } = ( \frac { \chi } { \varepsilon + \phi _ { 3 } } + \frac { \beta \delta } { ( \delta + \phi _ { 2 } ) ( \varepsilon + \phi _ { 3 } ) } ) I _ { ( 3 ) } ^ { * } } } \end{array}
$$

# 4.2平衡点的稳定性分析

定理1 当 $\begin{array} { r } { R _ { 0 } ^ { 1 } < \frac { \alpha _ { 1 } \phi _ { 2 } } { \alpha _ { 1 } \phi _ { 2 } + \alpha _ { 2 } \beta } < 1 } \end{array}$ 时，无谣言平衡点 $E _ { 0 }$ 为系统局部渐近稳定点。证明

系统（1）在 $E _ { 0 }$ 处的Jacobi矩阵为

$$
{ \bf J } _ { 0 } = \left[ \begin{array} { c c c } { { - \mu } } & { { - \frac { \alpha _ { 1 } \lambda } { \mu } } } & { { - \frac { \alpha _ { 2 } \lambda } { \mu } } } \\ { { 0 } } & { { \frac { \alpha _ { 1 } \lambda } { \mu } - \left( \beta + \phi _ { 1 } \right) } } & { { \frac { \alpha _ { 2 } \lambda } { \mu } } } \\ { { 0 } } & { { \beta } } & { { - \phi _ { 2 } } } \end{array} \right]
$$

令其三个特征根分别为 $\sigma _ { 1 } = - \mu , \sigma _ { 2 } , \sigma _ { 3 }$ 其中 $\sigma _ { 2 } , \sigma _ { 3 }$ 必须满足

$$
\left| \sigma + ( \beta + \phi _ { 1 } ) - { \frac { \alpha _ { 1 } \lambda } { \mu } } \quad - { \frac { \alpha _ { 2 } \lambda } { \mu } } \right| = 0
$$

通过其特征方程系数p、q可以判断 $\sigma _ { 2 } , \sigma _ { 3 }$ 的符号，而

$$
\begin{array} { r l } & { \begin{array} { l l l } { \rho = - \Bigl [ \frac { \alpha _ { 1 } \lambda } { \mu } - ( \beta + \phi _ { 1 } ) - \phi _ { 2 } \Bigr ] = ( \beta + \phi _ { 1 } ) - \frac { \alpha _ { 1 } \lambda } { \mu } + \phi _ { 2 } > 0 } \\ & { \qquad \quad \_ d = \left| \frac { \alpha _ { 1 } \lambda } { \mu } - ( \beta + \phi _ { 1 } ) \frac { \alpha _ { 2 } \lambda } { \mu } \right| } \\ & { \qquad \beta } \end{array} } \\ &  \begin{array} { r l } { \phi _ { 2 } \frac { \alpha _ { 1 } \lambda } { \mu } - \frac { \alpha _ { 2 } \lambda \beta } { \mu } } &  = \begin{array} { r l } { \phi _ { 2 } \Bigl [ ( \beta + \phi _ { 1 } ) - \frac { \alpha _ { 1 } \lambda } { \mu } \Bigr ] - \frac { \alpha _ { 2 } \lambda \beta } { \mu } \Bigr ) = \phi _ { 2 } ( \beta + \phi _ { 1 } ) - } & \\ { \phi _ { 2 } \frac { \alpha _ { 1 } \lambda } { \mu } - \frac { \alpha _ { 2 } \lambda \beta } { \mu } } & { = \begin{array} { r l } { ( \beta + \phi _ { 1 } ) - \frac { \lambda } { \mu } ( \alpha _ { 1 } \phi _ { 2 } + \alpha _ { 2 } \beta ) } & { = \qquad ( \beta + \phi _ { 1 } ) \Bigr [ \phi _ { 2 } - \frac { \alpha _ { 2 } \beta } { \mu } \Bigr ] } \\ { \frac { \alpha _ { 1 } \lambda } { \mu ( \beta + \phi _ { 1 } ) } \frac { \alpha _ { 1 } \phi _ { 2 } + \alpha _ { 2 } \beta } { \alpha _ { 1 } } \Bigr ] = ( \beta + \phi _ { 1 } ) \Bigl [ \phi _ { 2 } - R _ { 0 } ^ { 1 } \frac { \alpha _ { 1 } \phi _ { 2 } + \alpha _ { 2 } \beta } { \alpha _ { 1 } } \Bigr ] } & { } \end{array} } \\ &  \begin{array} { r l } { \frac { ( \alpha _ { 1 } \phi _ { 2 } ) ^ { 2 } } { \mu } \frac { \alpha _ { 1 } \phi _ { 2 } + \alpha _ { 2 } \beta \left( \beta + \phi _ { 1 } \right) } { \alpha _ { 1 } \phi _ { 2 } } ( \beta + \phi _ { 1 } ) ( \frac { \alpha _ { 1 } \phi _ { 2 } } { \alpha _ { 1 } \phi _ { 2 } + \alpha _ { 2 } \beta } - R _ { 0 } ^ { 1 } ) } & \end{array} \end{array} \end{array} \end{array}
$$

因此，当R< αΦ2时，q>0，根据特征方程系数与根之间的关系可以判$\sigma _ { 1 } < 0 , \sigma _ { 2 } < 0 , \sigma _ { 3 } < 0$ 。由Hurtwitz判据[23]可以判断Eo局部渐近稳定。

定理2 当 $R _ { 0 } ^ { 1 } > 1$ 时，封号前谣言平衡点E1为系统的局部渐近稳定点。证明

系统（1）在Ei处的Jacobi矩阵为

$$
\mathsf { J } _ { 1 } = \left[ \begin{array} { c c c } { - \alpha _ { 1 } I _ { ( 1 ) } ^ { * } - \alpha _ { 2 } C 1 _ { ( 1 ) } ^ { * } - \mu } & { - \alpha _ { 1 } S _ { ( 1 ) } ^ { * } } & { - \alpha _ { 2 } S _ { ( 1 ) } ^ { * } } \\ { \alpha _ { 1 } I _ { ( 1 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 1 ) } ^ { * } } & { \alpha _ { 1 } S _ { ( 1 ) } ^ { * } - ( \beta + \phi _ { 1 } ) } & { \alpha _ { 2 } S _ { ( 1 ) } ^ { * } } \\ { 0 } & { \beta } & { - \phi _ { 2 } } \end{array} \right]
$$

令 $\ M _ { 1 } = - J _ { 1 }$ ，则 $\mathsf { J } _ { 1 } = \left[ \begin{array} { c c c } { \alpha _ { 1 } I _ { ( 1 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 1 ) } ^ { * } + \mu } & { \alpha _ { 1 } S _ { ( 1 ) } ^ { * } } & { \alpha _ { 2 } S _ { ( 1 ) } ^ { * } } \\ { - \left( \alpha _ { 1 } I _ { ( 1 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 1 ) } ^ { * } \right) } & { - \alpha _ { 1 } S _ { ( 1 ) } ^ { * } + ( \beta + \phi _ { 1 } ) } & { - \alpha _ { 2 } S _ { ( 1 ) } ^ { * } } \\ { 0 } & { - \beta } & { \phi _ { 2 } } \end{array} \right]$

将 $\Delta _ { i }$ （ $i { = } 1 , 2 , 3$ ）定义为矩阵Mi的顺序主子式，则

$$
\Delta _ { 1 } \mathrm { = } | \alpha _ { 1 } I _ { ( 1 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 1 ) } ^ { * } + \mu | { > } 0
$$

$$
\begin{array} { r l } & { \Delta _ { 2 } = \left| \frac { \alpha _ { 1 } I _ { ( 1 ) } ^ { * } } { - \left( \alpha _ { 1 } I _ { ( 1 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 1 ) } ^ { * } + \mu \right. } \qquad \left. \alpha _ { 1 } S _ { ( 1 ) } ^ { * } \right. } \\ & { - \left( \alpha _ { 1 } I _ { ( 1 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 1 ) } ^ { * } \right) \quad - \alpha _ { 1 } S _ { ( 1 ) } ^ { * } + ( \beta + \phi _ { 1 } ) \right| = \left( ( \beta + \phi _ { 1 } ) - \alpha _ { 1 } S _ { ( 1 ) } ^ { * } \right) \left( \alpha _ { 1 } I _ { ( 1 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 1 ) } ^ { * } \right) } \\ & { \alpha _ { 2 } C 1 _ { ( 1 ) } ^ { * } + \mu ) + \alpha _ { 1 } S _ { ( 1 ) } ^ { * } \left( \alpha _ { 1 } I _ { ( 1 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 1 ) } ^ { * } \right) } \\ & { \phantom { \frac { \alpha _ { 1 } S _ { ( 1 ) } ^ { * } } { - \left( \alpha _ { 1 } I _ { ( 1 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 1 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 1 ) } ^ { * } + \alpha _ { 3 } \right) } } . } \end{array}
$$

$$
\begin{array} { r l } & { \begin{array} { r l } & { \psi _ { \pm } , \quad \psi ^ { \prime } , \quad \psi _ { 1 } , \quad \psi _ { 2 } \neq ( 1 ) , \quad \psi ^ { \prime } , \quad \psi ^ { \prime } \mid \psi , \quad \psi ^ { \prime } , \quad \psi _ { 1 } , \psi _ { 2 } , \alpha _ { 1 } \beta _ { \pm } , \alpha _ { 2 } \beta _ { \pm } ^ { \prime } , \psi ^ { \prime } , \quad \psi ^ { \prime } , \psi ^ { \prime } , \psi ^ { \prime } , \psi , \psi } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \alpha _ { 2 } S _ { 1 } ^ { \ell } } \\ & { \Delta _ { 3 } = \displaystyle \displaystyle \overline { { \Bigg | } } - ( \alpha _ { 2 } I _ { ( 0 ) } ^ { \ell } + \alpha _ { 2 } C \Lambda _ { ( 0 ) } ^ { \ell } + \mu \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \alpha _ { 3 } S _ { ( 1 ) } ^ { \ell } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \phi _ { 2 } \Lambda _ { 2 } + \beta \times A _ { 3 2 } } \end{array}  } \\ &  \Biggl & \begin{array} { r l } & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \phi _ { 2 } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \phi _ { 2 } } \\ & { = \phi _ { 2 } [ ( \alpha _ { 2 } I _ { ( 1 ) } ^ { \ell } + \alpha _ { 2 } C \Lambda _ { ( 1 ) } ^ { \ell } + \mu ) ( \beta + \phi _ { 2 } ) - \alpha _ { 1 } \mu S _ { ( 1 ) } ^ { \ell } ] - \alpha _ { 2 } \mu \beta S _ { ( 1 ) } ^ { \ell } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ &  = \phi _ { 2 } [ \ \end{array} \end{array}
$$

因此，当 $R _ { 0 } ^ { 1 } > 1$ 时， $\Delta _ { 1 } > 0$ ， $\Delta _ { 2 } > 0$ ， $\Delta _ { 3 } > 0$ ，此时 $M _ { 1 }$ 为正定矩阵，其所有特征值均为负数。根据 Hurtwitz判据[23]可以知道 $\mathsf { E } _ { 1 }$ 局部渐近稳定。

定理3当 $R _ { 0 } ^ { 2 } > 0$ 时，解封前谣言平衡点E2和解封后平衡点E3均为系统的局部渐近稳定点。

证明

系统（2）在E2处的Jacobi矩阵为

$$
\begin{array} { r l } & { \mathrm { J } _ { 2 } = [ \begin{array} { c c c c c } { - \alpha _ { 1 } I _ { ( 2 ) } ^ { * } - \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } - \mu } & { - \alpha _ { 1 } S _ { ( 2 ) } ^ { * } } & { - \alpha _ { 2 } S _ { ( 2 ) } ^ { * } } & { 0 } \\ { \alpha _ { 1 } I _ { ( 2 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } } & { \alpha _ { 1 } S _ { ( 2 ) } ^ { * } - ( \beta + \chi + \phi _ { 1 ) } } & { \alpha _ { 2 } S _ { ( 2 ) } ^ { * } } & { \varepsilon } \\ { 0 } & { \beta } & { - \delta - \phi _ { 2 } } & { 0 } \\ { 0 } & { \chi } & { \delta } & { - \delta - \phi _ { 3 } } \end{array} ] } \\ & { \qquad \quad \overset { \Longleftrightarrow } { \underset { \Longleftrightarrow } { \bigoplus } } [ \begin{array} { c c c c c } { \alpha _ { 1 } I _ { ( 2 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } + \mu } & { \alpha _ { 1 } S _ { ( 2 ) } ^ { * } } & { \alpha _ { 2 } S _ { ( 2 ) } ^ { * } } & { 0 } \\ { - \alpha _ { 1 } I _ { ( 2 ) } ^ { * } - \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } } & { - \alpha _ { 1 } S _ { ( 2 ) } ^ { * } + ( \beta + \chi + \phi _ { 1 ) } } & { - \alpha _ { 2 } S _ { ( 2 ) } ^ { * } } & { - \varepsilon } \\ { 0 } & { - \beta } & { \delta + \phi _ { 2 } } & { 0 } \\ { 0 } & { - \chi } & { - \delta } & { \delta + \phi _ { 3 } } \end{array} ] } \\ & { \qquad \quad \overset { \Longleftrightarrow } { \underset { \Longleftrightarrow } { \longrightarrow } } [ \begin{array} { c c c c } { \alpha _ { 1 } I _ { ( 2 ) } ^ { * } - \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } + \mu } & { - \beta } & { \alpha _ { 1 } S _ { ( 2 ) } ^ { * } } & { - \delta - \phi _ { 3 } } \end{array} ] } \\ &  \qquad \quad \overset { \Longleftrightarrow } { \underset { \Longleftrightarrow } { \longrightarrow } } [ \begin{array} { c c c c } { \alpha _ { 1 } I _ { ( 2 ) } ^ { * } - \alpha _ { 2 } I _ { ( 2 ) } ^ { * } - \alpha _ { 1 } S _ { ( 2 ) } ^ { * } + \beta } & { - \alpha _ { 2 } S _ { ( 2 ) } ^ { * } } & { 0 } \\  - \alpha _ { 1 } I _ { ( 2 ) } ^ { * } - \alpha  \end{array} \end{array}
$$

将 $\Delta _ { i }$ （ $\ i = 1 , 2 , 3 .$ ）定义为矩阵 $\mathsf { M } _ { 2 }$ 的顺序主子式，则

$$
\Delta _ { 1 } \mathrm { = } | \alpha _ { 1 } I _ { ( 2 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } + \mu | { > } 0
$$

（204 $\begin{array} { r l r l } { \Delta _ { 2 } } & { { } = } & { | { \alpha _ { 1 } I _ { ( 2 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } + \mu \qquad } { \alpha _ { 1 } S _ { ( 2 ) } ^ { * } } | } & { { = } } & { { \Big ( } { \big ( } \beta + \chi + \phi _ { 1 } { \big ) - ( } \beta + \chi + \phi _ { 1 } { \big ) - ( } \beta + \chi + \phi _ { 1 } { \big ) - \chi ^ { * } ) } | } \\ { \qquad } & { { } } & { { } } \\ { \alpha _ { 1 } S _ { ( 2 ) } ^ { * } \Big ) ( \alpha _ { 1 } I _ { ( 2 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } + \mu ) + \alpha _ { 1 } S _ { ( 2 ) } ^ { * } \Big ( \alpha _ { 1 } I _ { ( 2 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } \Big ) = } \\ { \qquad } & { { } } & { { } } \\ { \quad } { \quad } & { { } } & { { } } & { { } \int { - ( \alpha _ { 1 } \ J _ { ( 2 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } ) - \alpha _ { 1 } S _ { ( 2 ) } ^ { * } \operatorname { i n } ( \beta + \chi + \phi _ { 1 } ) ( \delta + \phi _ { 2 } ) } ) _ { - \ f \ d { \rho } \ d \cdot \ w , \ 1 } . } \end{array}$ （20  
其中， $\begin{array} { r } { \left( \left( \beta + \chi + \phi _ { 1 } \right) - \alpha _ { 1 } S _ { ( 2 ) } ^ { \ast } \right) = \left( \beta + \chi + \phi _ { 1 } \right) - \alpha _ { 1 } \left( \frac { \left( \beta + \chi + \phi _ { 1 } \right) \left( \delta + \phi _ { 2 } \right) } { \alpha _ { 1 } \left( \delta + \phi _ { 2 } \right) + \alpha _ { 2 } \beta } \right) = \left( \beta + \chi + \phi _ { 1 } \right) } \end{array}$ （$\begin{array} { r } { \phi _ { 1 } ) \Big ( 1 - \frac { \alpha _ { 1 } ( \delta + \phi _ { 2 } ) } { \alpha _ { 1 } ( \delta + \phi _ { 2 } ) + \alpha _ { 2 } \beta } \Big ) > 0 } \end{array}$   
（204 $\Delta _ { 3 } = \left| \begin{array} { c c c } { { \alpha _ { 1 } I _ { ( 2 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } + \mu } } & { { \alpha _ { 1 } S _ { ( 2 ) } ^ { * } } } & { { \alpha _ { 2 } S _ { ( 2 ) } ^ { * } } } \\ { { - \alpha _ { 1 } I _ { ( 2 ) } ^ { * } - \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } } } & { { - \alpha _ { 1 } S _ { ( 2 ) } ^ { * } + ( \beta + \chi + \phi _ { 1 } ) } } & { { - \alpha _ { 2 } S _ { ( 2 ) } ^ { * } } } \\ { { 0 } } & { { - \beta } } & { { \delta + \phi _ { 2 } } } \end{array} \right| = ( \delta + \phi _ { 2 } ) \times \Delta _ { 2 } + \Delta _ { 1 } .$ $\begin{array} { r l } & { \qquad = p \qquad \textnormal { o r } \psi _ { 2 } 1 } \\ & { \beta \times A _ { 3 2 } = ( \delta + \phi _ { 2 } ) \big [ \big ( \alpha _ { 1 } I _ { ( 2 ) } ^ { * } + \alpha _ { 2 } C \boldsymbol { 1 } _ { ( 2 ) } ^ { * } + \mu \big ) ( \beta + \chi + \phi _ { 1 } ) - \alpha _ { 1 } \mu S _ { ( 2 ) } ^ { * } \big ] - \alpha _ { 2 } \mu \beta S _ { ( 2 ) } ^ { * } } \\ & { = ( \delta + \phi _ { 2 } ) \big [ \big ( \alpha _ { 1 } I _ { ( 2 ) } ^ { * } + \alpha _ { 2 } C \boldsymbol { 1 } _ { ( 2 ) } ^ { * } + \mu \big ) ( \beta + \chi + \phi _ { 1 } ) \big ] - \mu S _ { ( 2 ) } ^ { * } \big [ \alpha _ { 1 } ( \delta + \phi _ { 2 } ) + \alpha _ { 2 } \beta \big ] } \\ & { \qquad \quad ( \delta + \phi _ { 2 } ) \big [ \big ( \alpha _ { 1 } I _ { ( 2 ) } ^ { * } + \alpha _ { 2 } C \boldsymbol { 1 } _ { ( 2 ) } ^ { * } + \mu \big ) ( \beta + \chi + \phi _ { 1 } ) \big ] - \mu [ \alpha _ { 1 } ( \delta + \phi _ { 2 } ) + \mu } \\ & { \alpha _ { 2 } \beta \big ] \big [ \frac { ( \beta + \chi + \delta _ { 1 } ) ( \delta + \phi _ { 2 } ) } { \alpha _ { 1 } ( \delta + \phi _ { 2 } ) + \alpha _ { 2 } \beta } \big ] } \\ & { = ( \delta + \phi _ { 2 } ) \big ( \alpha _ { 1 } I _ { ( 2 ) } ^ { * } + \alpha _ { 2 } C \boldsymbol { 1 } _ { ( 2 ) } ^ { * } \big ) > 0 } \end{array}$ （204号$\Delta _ { 4 } = \left| \begin{array} { c c c c c } { { \alpha _ { 1 } I _ { ( 2 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } + \mu } } & { { \alpha _ { 1 } S _ { ( 2 ) } ^ { * } } } & { { \alpha _ { 2 } S _ { ( 2 ) } ^ { * } } } & { { 0 } } \\ { { - \alpha _ { 1 } I _ { ( 2 ) } ^ { * } - \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } } } & { { - \alpha _ { 1 } S _ { ( 2 ) } ^ { * } + ( \beta + \chi + \phi _ { 1 } ) } } & { { - \alpha _ { 2 } S _ { ( 2 ) } ^ { * } } } & { { - \varepsilon } } \\ { { 0 } } & { { - \beta } } & { { \delta + \phi _ { 2 } } } & { { 0 } } \\ { { 0 } } & { { - \chi } } & { { - \delta } } & { { \delta + \phi _ { 3 } } } \end{array} \right|$   
$\begin{array} { r } { \mathbf { \sigma } = ( \delta + \phi _ { 3 } ) \times \Delta _ { 3 } + ( - \varepsilon ) \times A _ { 2 4 } } \end{array}$ （20  
其中， $( - \varepsilon ) \times A _ { 2 4 } = \varepsilon ( \alpha _ { 1 } I _ { ( 2 ) } ^ { * } + \alpha _ { 2 } C 1 _ { ( 2 ) } ^ { * } + \mu ) [ \delta ( \beta + \chi ) + \chi \phi _ { 2 } ] > 0$   
因此，当 $R _ { 0 } ^ { 2 } > 1$ 时， $\Delta _ { 1 } > 0$ ， $\Delta _ { 2 } > 0$ ， $\Delta _ { 3 } > 0$ ， $\Delta _ { 4 } > 0$ 此时 $M _ { 2 }$ 为正定矩阵，其所有特征值均为负数。根据Hurtwitz 判据[23]可以知道E2局部渐近稳定。  
最后，同理可证E3为局部渐近稳定。

# 5建模数值分析

# 3.1模型平衡点的稳定性

首先将模型中各状态人群在初始条件下所占比例依次设置为 $\mathsf { S } ( 0 ) { = } 0 . 7$ ，$1 ( 0 ) { = } 0 . 1$ ， $\mathsf { C } 1 ( 0 ) { = } 0 . 0 5$ ， ${ \mathsf { C } } 2 ( 0 ) { \mathsf { = } } 0 . 0 5$ ， $\mathsf { R } ( 0 ) { = } 0$ ，然后在此基础上进行仿真模拟实验。

1）当 $\alpha _ { 1 } { = } 0 . 3$ ， $\alpha _ { 2 } { = } 0 . 1$ ， $\beta = 0 . 1 5$ ， $\phi _ { 1 } = 0 . 1$ ， $\phi _ { 2 } = 0 . 1 5$ ， $\lambda = 0 . 1$ ， $\mu = 0 . 2 5$ 时，可以计算得出 $E _ { 0 } = ( \lambda / \mu , 0 , 0 ) = ( 0 . 4 , 0 , 0 )$ ，且 $\begin{array} { r } { R _ { 0 } ^ { 1 } = \frac { a _ { 1 } \lambda } { \mu ( \beta + \phi _ { 1 } ) } = 0 . 4 8 < } \end{array}$ $\begin{array} { r } { \frac { \alpha _ { 1 } \phi _ { 2 } } { \alpha _ { 1 } \phi _ { 2 } + \alpha _ { 2 } \beta } = 0 . 7 5 < 1 } \end{array}$ β = 0.75<1成立。根据定理1，E局部渐近稳定。如图2（a）所示，易感者人群比例由最高点0.7逐渐下降，最后在0.4处趋于稳定，传播者比例逐渐降低并最终趋于零，谣言传播终止。仿真结果与定理1的结论相符。为了验证 $E _ { 0 }$ 点的局部稳定性，选取10 组不同的S、I、Ci初始状态值进行实验。如图2（b）所示，所有i-s相轨迹曲线最终全都收敛于 $E _ { 0 }$ 。结果表明，在满足定理1的条件下，任意选取各人群比例的初始值，其最终演化结果都会收敛于平衡点 $E _ { 0 }$ 。

![](images/73717e3d3f6e99fe19f65dff4d68433472cefe74558abb0c05a25f39af196079.jpg)  
图2无谣言传播平衡点 $E _ { 0 }$ 稳定性分析

2）当 $\alpha _ { 1 } { = } 0 . 3$ ， $\scriptstyle \alpha _ { 2 } = 0 . 2$ ， $\beta = 0 . 1 5$ ， $\phi _ { 1 } = 0 . 1 5$ ， $\phi _ { 2 } = 0 . 1$ ， $\lambda = 0 . 2$ ， $\mu = 0 . 1 5$ 时，计算得到 $\begin{array} { r } { | E _ { 1 } = \left( S _ { ( 1 ) } ^ { * } , I _ { ( 1 ) } ^ { * } , C 1 _ { ( 1 ) } ^ { * } \right) = \left( 0 . 5 0 , 0 . 4 2 , 0 . 6 2 \right) , R _ { 0 } ^ { 1 } = \frac { a _ { 1 } \lambda } { \mu ( \beta + \phi _ { 1 } ) } = 1 . 3 3 > 1 . } \end{array}$ 0根据定理2, $E _ { 1 }$ 局部渐近稳定。如图3（a)所示，易感者人数占比先上升后下降，最后在0.50处达到稳定，传播者和受限者 ${ \mathsf { C } } _ { 1 }$ 比例逐渐上升最终趋于稳定，稳定值分别约为0.42和0.62。在保持参数设置不变的情况下，选取10不同初始值进行实验，结果如图3（b）所示。从图中可以看出，尽管各组实验初始值有所不同，但所有i-s相轨迹曲线最终都收敛于 $E _ { 1 }$ ，仿真结果与定理2的结论相符。

![](images/4a371c1aaa0266c88e5de8e602b1ce0795bb07a3c412b0f827688c437718ea18.jpg)  
图3封号前谣言传播平衡点 $E _ { 1 }$ 稳定性分析

3）当 $\alpha _ { 1 } { = } 0 . 5$ ， $\alpha _ { 2 } { = } 0 . 3$ ， $\beta = 0 . 1 5$ ， $\chi = 0 . 1$ ， $\delta = 0 . 2$ ， $\varepsilon = 0 . 0 5$ ， $\phi _ { 1 } = 0 . 1 5$ ，$\phi _ { 2 } = 0 . 2 , \phi _ { 3 } = 0 . 2 5 , \lambda = 0 . 2 , \mu = 0 . 1 5$ 时，通过计算可以得到 $E _ { 2 } =$ $\big ( S _ { ( 2 ) } ^ { * } , I _ { ( 2 ) } ^ { * } , C 1 _ { ( 2 ) } ^ { * } , C 2 _ { ( 2 ) } ^ { * } \big ) = ( 0 . 6 5 , 0 . 2 5 , 0 . 1 0 , 0 . 2 6 ) , R _ { 0 } ^ { 2 } = \alpha _ { 1 } \lambda / \mu ( \beta + \chi + \phi _ { 1 } ) = 1 . 6 6 > 1$ 成立。由定理3可知， $E _ { 2 }$ 为系统（2）的局部平衡点。如图4（a）所示，各人群比例先是逐渐上升，到达峰值后缓慢下降，最终在 $\scriptstyle { \mathrm { t } } = 3 0$ 时步趋于各自的稳定状态，即意味着此时谣言传播已经达到平衡状态。最后仍然选取10组不同的初始状态值验证 $E _ { 2 }$ 的稳定性。仿真结果如图4（b）所示，所有相轨迹曲线均收敛于$E _ { 2 }$ 。

与系统（2）类似，系统（3）在解封后平衡点 $E _ { 3 }$ 处各群体均达到稳定状态，并且所有i-s相轨迹曲线最终都收敛于 $E _ { 3 }$ ，如图5所示。仿真结果与定理3的结论相吻合。

![](images/9dd6aa6aa886b4a56e6c4061bca27b5869f121c6d20554bccc79492f2ca0eae1.jpg)

(a） $E _ { 2 }$ 处各群体传播情况 （b） $E _ { 2 }$ 处i-s相轨迹图

![](images/de5c196805dc2526ff9bbd6073fdc9235a54cfc244a6bf450e4810dc386ac8ee.jpg)  
图4解封前谣言传播平衡点 $E _ { 2 }$ 稳定性分析  
图5解封后谣言传播平衡点 $E _ { 3 }$ 稳定性分析

# 3.2谣言传播影响因素分析

为了模拟不同因素对谣言传播过程的影响，现将模型中的参数设置如表2所示

表2模型传播参数设置表  

<html><body><table><tr><td>参数</td><td>取值</td><td>参数</td><td>取值</td></tr><tr><td>S(0)</td><td>0.7</td><td>α1</td><td>0.5</td></tr><tr><td>1(0)</td><td>0.1</td><td>&2</td><td>0.4</td></tr><tr><td>C1(0) C2(0)</td><td>0.05</td><td>β</td><td>0.15</td></tr><tr><td>R(0)</td><td>0.05 0</td><td>X</td><td>0.1</td></tr><tr><td></td><td></td><td>8</td><td>0.15</td></tr><tr><td></td><td></td><td></td><td>0.05</td></tr><tr><td></td><td></td><td>Φ1</td><td>0.25</td></tr><tr><td></td><td></td><td>2</td><td>0.2</td></tr><tr><td></td><td></td><td>3</td><td>0.18</td></tr><tr><td></td><td></td><td>to</td><td>3</td></tr><tr><td></td><td></td><td>T</td><td>30</td></tr></table></body></html>

# 3.2.1模型内的直接影响因素

由基本再生数 $R _ { 0 } ^ { 1 }$ 、 $R _ { 0 } ^ { 2 }$ 计算公式可以看出， $\alpha _ { 1 } , \beta$ 、X、 $\phi _ { 1 }$ 、、 $\mu$ 等参数都对谣言传播产生直接影响。下面通过仿真实验进一步分析模型参数变化对谣言传播过程的影响机理。图6（a）～（e）分别为各参数变化对传播者人数占比的影响。从图（a）～（b）中可以看出，传播者 $\alpha _ { 1 }$ 、流入率λ与传播者人数比例成正比，即随着传播率的提高、流入率的增大，传播者人数峰值越来越大，达到峰值的时间也逐渐提前。这主要是因为传播率的提高意味着传播者感染能力的增强，同时流入速度的加快将导致易感者人群基数的迅速扩大，更多的未知网民面临被“感染”的风险。此外，从图（c）～（e）中可以看出，警告率β、封号率x以及流出率 $\mu$ 的增加将导致传播者人数占比峰值的逐渐降低以及最终稳定状态时谣言规模的减小。这是由于警告和封号是平台直接对谣言传播者本人施加的惩罚，能够对传播者产生较大的威慑作用。而流出率的增加意味着越来越多的人脱离谣言传播网络，从而避免成为谣言传播的助燃剂。

![](images/86abc15d4b92f763b87b594ec8532550d6d32a91fa6a4fa7e6f3c6fbc433f81c.jpg)  
（a）αi的影响

![](images/60af85ecf390906c94b52c1f76450d6ec5e508b82f494efeae5239a3c0f7cdbd.jpg)  
（b）λ的影响

![](images/46a319db91db65777669381e3bad9e1c15a422a9a69bf355a7623f2a79214685.jpg)

![](images/d9b1e61ddcac8a8d154c0442f80e9f0567ad855e32754f7114baa1af37fb2adc.jpg)

(c） $\beta$ 的影响 （d）x的影响

![](images/2eb90832ae4105e633ed7303e0a677537d861a43d1ecf82408da92683cd3df2c.jpg)  
图6模型内部参数的直接影响

# 3.2.2模型内的间接影响因素

不包含在基本再生数 $R _ { 0 } ^ { 1 }$ 、 $R _ { 0 } ^ { 2 }$ 计算公式中的模型参数均可以看作影响谣言传播的间接因素。本研究模型中的间接影响因素主要包括传播率 $\alpha _ { 2 }$ 、升级率8以及复阳率ε。传播率 $\alpha _ { 2 }$ 和升级率8主要通过受限者C1从而间接地影响传播者丨的人数变化，而复阳率ε主要通过受限者 ${ \mathsf C } _ { 2 }$ 从而间接地对传播者I的人数比例产生影响，各参数的影响如图7（a） $\sim$ （c）所示。从图（a）中可以看出，随着传播率 $\alpha _ { 2 }$ 的增加，传播者峰值逐渐提高，表明受限者Ci传播能力的提高将导致谣言扩散规模的增大，而平台更多地升级对传播者的惩罚措施却能够在一定程度上减小谣言传播的影响范围。此外，从图（c）中可以看出，复阳率的增加并未对谣言传播峰值产生显著影响，而对最终稳定状态影响较大。原因在于复阳率主要影响的是受限者 ${ \sf C } _ { 2 }$ 解封后的“反弹”强度，复阳率越大，反弹力度越强，重新转变为传播者的人数越多。因此，如何有效降低复阳率对于防止谣言传播“死灰复燃”以及由此可能引发的次生舆情至关重要。

![](images/a5214987b397c87b6959c4a9612bb99fa0e486bf2e3ee17a469af4f4db3d3689.jpg)

![](images/3518216396a1dcd23b34dbc1df2f4a4fe8f7a5a228224c7c135341c7b9b4a213.jpg)  
图7模型内部参数的间接影响

# 3.2.3模型外的时间影响因素

除了以上模型参数会对谣言传播产生直接或间接的影响，社交平台何时采取封号措施以及封号期限的长短同样会对谣言扩散规模和传播速度产生一定影响，如图所示。从图8（a）中可以看出，随着to变大即平台采取措施的时间越来越晚，传播者的峰值也越来越大，且增幅较为明显。换言之，社交平台采取措施的时间越早，则抑制效果越好。在谣言爆发初期，通常只有少数网民关注到谣言内容，主动参与传播的网民数量十分有限，并且这一时期谣言传播往往局限于某一个或某一类社交平台，尚未“出圈”，无疑是阻止其扩散的最佳时机。从图8（b）中可以看出，封号期限的越长，谣言传播峰值越小，但是谣言规模并非随着封号期限的增大而一直减小。当解封日期超过到达峰值时间时，封号期限的延长并不能进一步降低谣言传播规模。因此，对于社交平台而言，适当延长封号期限，使之处于谣言传播衰退阶段，将更有助于控制谣言传播规模。

![](images/1aec627b2e349c686738929fa012043a146f36d2f1fa422667596db61e9e04b8.jpg)  
图8模型外部时间参数的影响  
图9 SIC1-2R模型影响因素分析图

通过对模型内外相关影响因素的数值分析发现，以上所有影响因素可进一步归纳为三种类型：促进因素、抑制因素和时间因素。促进因素主要包括传播率、传播率、复阳率以及流入率等能够促进谣言传播扩散的模型参数。抑制因素主要包括警告率、封号率、升级率以及流出率等对谣言传播具有阻碍遏制作用的相关参数，而时间因素主要是指与社交平台采取抑制措施时间有关的因素，包括封号起始时间和封号期限。因此，基于上述两种不同的划分维度，本文对传播模型中所有影响因素进行了归纳总结，如图9所示。

<html><body><table><tr><td>直接因素</td><td>间接因素</td></tr><tr><td>抑制 (β、x、μ)</td><td>促进 (a2、ε)</td></tr><tr><td>促进 (a1、λ)</td><td>抑制 (ε)</td></tr><tr><td colspan="2">时间因素 (to、T)</td></tr></table></body></html>

# 6对策与总结

基于提出的 $\mathrm { S I C } _ { 1 - 2 } \mathrm { R }$ 模型及其仿真研究结果，为社交平台科学治理网络谣言传播提出如下对策。第一，成立专门的内容审核部门，加强对用户发布内容的事实核查，减少报道来源不明、真相存疑的消息，清理平台中的垃圾内容，营造风清气正、和谐有序的社区环境（减小 $\alpha _ { 1 }$ )。第二，加强社交平台的宣传引导作用，建立网络谣言监测体系，及时发布辟谣信息，降低公众转发谣言的兴趣和意愿（减小 $\alpha _ { 2 }$ )。第三，进一步完善平台自身对于网络谣言传播者的惩罚机制，比如适当增加警告或者封号的频率、延长封号时间等手段，从而提高传播者违规成本、威慑潜在传播者（增大 $\beta 、 \gamma , \delta )$ 。第四，强化平台科学知识普及、文化宣传教育功能，提高人们的科学文化素养和明辨是非的能力，使之能够正确认识谣言传播危害，自觉抵制网络谣言（降低ε)。第五，当突发事件发生后，平台应该及时采取导控措施并适当延长封号时间，将谣言传播扼杀在萌芽期，避免事态升级，引发舆情危机（减小 $t _ { 0 }$ ，增大T)。

本文基于传统的SIR 模型，将社交平台谣言抑制策略（警告和封号）作为主要研究变量纳入分析，由此构建了 $\mathrm { S I C } _ { 1 - 2 } \mathrm { R }$ 模型。新模型存在四个谣言平衡点，依次为无谣言传播平衡点 $\mathrm { E } _ { 0 }$ 、封号前谣言传播平衡点 $\mathrm { E } _ { 1 }$ 、解封前谣言传播平衡点 $\mathrm { E } _ { 2 }$ 以及解封后谣言传播平衡点 $\mathrm { E } _ { 3 }$ ，并且均通过仿真实验得到了验证。同时，仿真实验还表明，传播率、复阳率以及流入率等因素能够促进谣言传播，而警告率、封号率、升级率以及流出率能够对谣言传播起到抑制作用。最后，封号起始时间以及封号期限也会对谣言传播过程产生一定影响。

本研究也存在一定的不足。首先，仿真实验中所采用的数据均为计算机模拟值，模型参数虽然参考了前人研究，但是部分是根据经验设定，下一步将选取真实案例数据进行实证分析。其次，网络谣言治理主体非常多元，主要包括政府、社交平台、大众媒体，甚至是普通民众，而本文仅仅选取了社交平台一个对象进行探讨，研究角度略显单一，无法得出具有综合性的研究结论，因此，基于多元主体共同治理的网络谣言传播模型也是本研究未来主要关注的研究方向。

作者简介：杨仁彪（ $( 1 9 9 5 - )$ ，重庆奉节人，硕士研究生，主要从事网络辟谣、网络舆情研究；尹春晓（1984-)，重庆北碚人，副教授，博士研究生，主要从事信息传播、信息甄别等研究。

基金项目：本文系中央高校基本科研业务费专项资金资助（项目编号：SWU2209211）研究成果之一。

通讯作者：尹春晓（yincx $@$ swu.edu.cn )

# 作者贡献说明：

杨仁彪：理论构建、数据获取及分析、初稿撰写及修改尹春晓：理论指导及论文修改

# 英文摘要

Research on Propagation Model and Simulation based on rumor suppression strategy of social

platform

YANG Ren-biaol,YIN Chun-xiao² (1.School of Computer and Information Science,Southwest University,Chongqing 400715, China; 2.Faculty of Education,Southwest University,Chongqing 400715, China)

Abstract:【Purpose/Significance】 Under the environment of social media, Internet rumors spread fast and widely, which seriously disturb the social order. Therefore, how to deal with Internet rumors has become an urgent problem to be solved in the management of Internet society. This paper explores the methods of network rumor governance from the perspective of rumor suppression strategies on social platforms,and provides reference suggestions for people to control rumor propagation scientifically and effectively. 【Method/Process】 Based on the rumor suppression strategy (warning and blocking) of social platforms,this paper proposes an improved SIC1-2R propagation model,and then analyzes the equilibrium point of rumors in the model and proves it. Finally, matlab2O2la was used for simulation experiment. 【Result/Conclusion】 The results show that there are four equilibrium points of rumor propagation in the new model (no rumor equilibrium point $\mathrm { E } _ { 0 }$ ,equilibrium point $\mathrm { E } _ { 1 }$ before sealing, equilibrium point $ { \mathrm { E } } _ { 2 }$ before unsealing and equilibrium point $\mathrm { E } _ { 3 }$ after unsealing),which are verified by simulation experiments.At the same time,the internal parameters of the model and the time factor have an important influence on the rumor propagation process.【Innovation/limitation】 There are two innovations: (1) The rumor suppression strategy based on social platform (warning and blocking） improves the traditional SIR Communication model; (2) The stability of rumor equilibrium in the model was discussed in stages (before,before and after the number was sealed).Limitations mainly lie in the fact that the data used in the experiment are all simulated values,some parameters are set according to experience,and the governance strategy of Internet rumors is only discussed from the perspective of platform, so the research conclusions are not comprehensive enough.

Key words: Spread rumors; Social platforms; Inhibition strategy; MATLAB simulation

# 参考文献

[1]巢乃鹏,黄娴．网络传播中的“谣言”现象研究[J]．情报理论与实践,2004,(6):586-589,575.  
[2]王国华,汪娟,方付建．基于案例分析的网络谣言事件政府应对研究[J].情报杂志,2011,30(10): 72-76.  
[3]唐雪梅,赖胜强．突发事件中政府对网络谣言的辟谣策略研究——以太伏中学事件为例[J].情报杂志,2018,37(9):95-99.  
[4]肖珺,庞航宇．微博自净功能与辟谣模式选择研究[J].现代传播(中国传媒大学学报),2012,34(8): 138-139.  
[5]李宗敏,张琪,杜鑫雨.基于辟谣微博的互动及热门评论情感倾向的辟谣效果研究——以新冠疫情相关辟谣微博为例[J]．情报杂志,2020,39(11):90-95,110.  
[6]唐梦斐,王建成．突发事件中政务微博辟谣效果研究——基于“上海外滩踩踏事件”的案例分析[J].情报杂志,2015,34(8):98-103,36.  
[7]王晰巍,邱程程,贾若男．突发公共卫生事件网络谣言辟谣效果影响因素研究——以新冠疫情期间网络谣言为例[J].图书情报工作:1-10.  
[8]贾若男,王晰巍,孙玉姣．社交媒体中突发公共卫生事件网络辟谣信息主体研究[J]．图书情报工作,2021,65(19): 16-25.  
[9]Chuang Liu,Xiu-Xiu Zhan,Zi-Ke Zhang, et al. How events determine spreading patterns:information transmision via internal and external influences on social networks[J]. New Journalof Physics,2015,17(11): 113045.  
[10]Daryl J Daley,David G Kendal. Stochastic rumours[J]. Ima Journal of Applied Mathematics,1965, 1(1): 42-55.[11]Daniel P Maki,Daniel P Maki,DP Mali, et al. Mathematical models and applications: withemphasis on the social, life,and management sciences[M]: Prentice Hall,1973.  
[12]廖圣清,方圆．基于仿真模型的社交网络辟谣效果研究[J]．湖南师范大学社会科学学报,2021, 50(6): 138-148.  
[13]顾亦然,夏玲玲．在线社交网络中谣言的传播与抑制[J]．物理学报,2012,61(23):544-550.[14]唐梁鸿绪,王卫苹,王昊,等．新冠疫情下的 SEIRD 时滞性谣言传播模型及辟谣策略[J]．工程科学学报,2022,44(6):1080-1089.  
[15]屈楠伟,夏志杰,王诣铭．基于用户信息行为的社交媒体辟谣效果研究[J]．情报科学,2021,39(1): 111-119.  
[16]王祁月,刘润然,贾春晓．复杂网络上的意见动力学对谣言传播的影响[J]．物理学报,2021,70(6): 351-358.  
[17]Maziar Nekovee,Yamir Moreno,Ginestra Bianconi, et al. Theory of rumour spreading incomplex social networks[J]. Physica A: Statistical Mechanics and Its Applications,2OO7,374(1):457-470.  
[18]王晰巍,李玥琪,邱程程,等．突发公共卫生事件下网络谣言传播逆转模型及仿真研究[J].图书情报工作:1-12.  
[19]赵敏,陈文霞,宋乾坤．考虑媒体报道效应的谣言传播模型研究[J].应用数学和力学,2018,39(12): 1400-1409.  
[20]Patricia Moravec,Antino Kim,Alan Dennis. Flagging fake news: System 1 vs. System 2[J],2018.  
[21]Justin T Picket,Sean Patrick Roche,Greg Pogarsky. Toward a bifurcated theory of emotionaldeterrence[J]. Criminology, 2018, 56(1): 27-58.  
[22]Pauline Van den Driessche,James Watmough. Reproduction numbers and sub-thresholdendemic equilibria for compartmental models of disease transmission[J].Mathematical  
Biosciences,2002,180(1): 29-48.  
[23]Rex Clark Robinson. An introduction to dynamical systems: continuous and discrete[M]:American Mathematical Soc., 2012.