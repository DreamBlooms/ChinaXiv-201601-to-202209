# 基于传播能力差异的IWSR垃圾信息传播模型‘

冉茂洁，刘超，黄贤英，刘小洋，曹琼(重庆理工大学 计算机科学与工程学院，重庆 400054)

摘要：为研究用户传播能力差异性对垃圾信息传播的影响，根据仓室建模思想,将传播网络中的人群划分为I(ignorant)，W(weakly spreader)，S(strongly spreader)，R(removal)四个仓室并提出状态转换规则，运用微分动力系统理论建立一个具有传播能力差异的IWSR垃圾信息传播模型。通过计算模型的基本再生数，利用 Hurwitz判据、Lyapunov 稳定性定理和 LaSalle不变性原理，得出垃圾信息传播平衡点的局部稳定和全局稳定条件。最后通过数值仿真与新浪微博真实数据集的对比实验证明所得结论的合理、有效性。

关键词：数学模型；全局稳定性；基本再生数；垃圾信息传播；传播能力差异中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.01.0102

# IWSR spam propagation model based on disparity of propagation

Ran Maojie, Liu Chao†, Huang Xianying, Liu Xiaoyang, Cao Qiong (School ofComputer Science&Engineering,Chongqing Universityof Technology,Chongqing 40o054,China)

Abstract: In order to study the impact of diferences in user communication capabilities on the spread of spam.This paper divided the population inthecommunication network into fourcompartments I(Ignorant),W(Weakly spreader),S(Strongly spreader),R(Removal)andestablishedstate transitionrulesaccordingtothetheoryofcompartmentmodeling.Usingdiferential dynamical system theory,this paperdeveloped an IWSR spampropagationmodel with diferentcommunicationcapabilities. Bycalculating the basicreproductionnumberof the modeland using the Hurwitzcriterion,Lyapunov stabilitytheoremand LaSale invarianceprinciple,this paperobtainedtheconditions forlocalstabilityand global stabilityofthe spaminformation propagation equilibrium points.Finaly,thecomparison experiment between the numerical simulation and the Sina Weibo dataset proves that the conclusion is reasonable and effective.

Key words: mathematical model; global stability; basic reproduction number; spam propagation; propagation diversity.

# 0 引言

互联网的快速发展给人们信息的交流带来巨大便利，但也造成垃圾信息泛滥的困扰，各类垃圾信息如虚假新闻、垃圾邮件、虚假广告等通过互联网肆意传播，不仅扰乱网络空间秩序，更使网络用户和网络平台遭受巨大经济损失[I'2]。因而，对垃圾信息进行深入研究已成为计算机领域的研究热点。目前针对垃圾信息的研究主要致力于对垃圾信息进行检测和过滤，即从微观层面研究垃圾信息，从而研发垃圾信息检测过滤算法和防火墙软件等。如Carlos等人[3提出的基于异常检测的垃圾邮件过滤算法，可有效减少垃圾邮件过滤工作量。林英等人[4提出基于贝叶斯分类的多层次垃圾短信过滤算法，使垃圾短信分类准确率更高。孙大鹏等人[5提出基于Hadoop云平台的短信过滤模型，将云计算技术运用到垃圾短信过滤中，解决了现有垃圾短信过滤技术中存在的复杂度过高、信息网络易阻塞等问题。还有学者针对图像垃圾邮件[6]、短消息垃圾邮件[7进行了研究，并提出相应的过滤算法。相对之前的研究结果，现有垃圾信息检测过滤技术准确率已有很大提高，但垃圾信息传播者不断提升垃圾信息的防检测与防过滤能力，使得过滤软件的过滤效果不断降低，而且，任何一种垃圾信息过滤技术的过滤准确率不可能达到 $100 \%$ 。此外，垃圾信息检测过滤算法的出现总是滞后于新型垃圾信息推送技术的产生。因此，垃圾信息检测过滤技术不能完全抑制垃圾信息的扩散。所以有必要从宏观层面分析垃圾信息传播行为。

借鉴生物传染病传播建模思想如仓室建模法建立传播模型[8:9]是研究互联网传播问题的有效方法，已广泛应用在谣言传播、病毒传播等领域。近年来，研究者开始通过建立传播模型分析互联网信息传播行为。如Xu等人[10]考虑信息本身包含的价值对信息传播的影响，建立了社交网络上信息传播的SEIR传播模型，并通过理论分析及数值仿真证明了该模型能很好模拟信息在社交网络上的传播过程。Hai 等人[12]考虑了信息传播过程中用户行为的影响，建立了信息传播的SIR模型，分析了用户行为对模型基本再生数及信息最终传播范围的影响。这些信息传播模型虽能很好揭示信息传播规律，然而与普通信息相比，垃圾信息传播存在许多鲜明特征，如病毒式推广、引诱转发、运用僵尸网络传播等。因此这些普通信息传播模型不能反应垃圾信息传播行为。因而一些研究者建立了适用于垃圾信息传播的动力学模型。如魏德志等人[13针对微博上虚假信息传播问题，根据博弈论提出虚假信息传播模型并进行了仿真分析。申志伟等人[14]对互联网中有害信息的传播进行了研究，提出SI传播模型，最后通过分析得出互联网拓扑结构决定有害信息传播机制的结论。然而，垃圾信息传播建模尚处于起步阶段，相关研究成果依然较少，许多影响传播行为的关键因素如传播能力差异性等未被考虑。

鉴于此，本文在考虑网络用户对垃圾信息传播能力差异性的基础上，建立了IWSR垃圾信息传播模型。运用微分动力系统理论，建立了模型稳定的基本条件，通过数值仿真验证了所得结论的正确性，并以新浪微博八卦信息传播数据集进行对比实验证明了模型的有效性。

# 1 IWSR模型

# 1.1模型的描述

传播力实质就是实现有效传播的能力[15]，而传播主体的认知、影响力等与传播主体的传播能力密切相关，因而网络用户的传播能力存在差异性。本文考虑网络用户传播能力差异性，建立IWSR垃圾信息传播模型。在IWSR模型中，人群被划分为4个仓室(如图1所示)：无知者(ignorant，即未接受到垃圾信息的用户)，弱传播者(weakly-spread people，即垃圾信息的弱传播用户)、强传播者(strongly-spread people，即垃圾信息的强传播用户)、移出者(removal,即已接收但不传播垃圾信息的用户)。I(t)， $S ( t )$ ， $W ( t )$ ， $R ( t )$ 分别表示 $t$ 时刻四类人群的比例。模型中假设 $I ( t )$ ， $S ( t )$ ， $W ( t )$ ， $R ( t )$ 是关于 $\mathbf { \Psi } _ { t }$ 的连续且可微函数，若无特殊说明，用 $I , \ S , \ W , \ R$ 分别指代 $I ( t )$ ， $S ( t )$ ， $W ( t )$ ， $R ( t )$ 。由图1 可知，强传播者和弱传播者以不同的速率感染未知者，并且以一定的速率转为移出者。针对某垃圾信息，每个节点的状态一定会在无知者、强传播者、弱传播者以及移出者之间进行转换，其转换规则描述如下：

a)个体以概率 $\delta$ 进入传播网络；传播网络中的每一类个体由于个人兴趣等原因以相同概率移出传播网络。

b)进入传播网络的个体均为未知者。

c)由于外部因素的干扰，弱传播者以概率 $\beta$ 转为强传播者。

d)当未知者 $I$ 接触到强传播者 $s$ 时，未知者以概率 $\alpha _ { 2 }$ 转为强传播者；当未知者 $I$ 接触到弱传播者W时，以概率 $\alpha _ { \mathfrak { l } }$ 转为弱传播者。并且有 $\alpha _ { 2 } > \alpha _ { 1 }$ 。

e)由于意识到垃圾信息的危害等原因，强传播者和弱传播者会停止传播垃圾信息，以概率 $\eta$ 转为移出者 $R$ 。

根据上述状态转换规则，得到网络中垃圾信息传播的节点状态转换图，如图2所示。

![](images/5be061a1c2fa8a02f8bb4e0e58f9841f82d6d7ba6aab4dce33b94cbc05c4a6ff.jpg)  
图1传播者以不同的速率传播垃圾信息

![](images/c2449d24287e7cd463623b665021d02f3f6ebc32da7a1cc017f98a125c0580de.jpg)  
图2无知者、强传播者、弱传播者和移出者的状态转换关系图

由图2所描述的节点状态转换过程，建立如下垃圾信息传播的微分动力模型：

$$
\begin{array} { l } { \displaystyle {  \frac { d I } { d t } = \delta - \alpha _ { 1 } W I - \alpha _ { 2 } S I - \delta I  } } \\ { \displaystyle {  \frac { d W } { d t } = \alpha _ { 1 } W I - \beta W - \eta R W - \delta W } } \\ { \displaystyle {  \frac { d S } { d t } = \alpha _ { 2 } S I + \beta W - \eta R S - \delta S  } } \\ { \displaystyle {  \frac { d R } { d t } = \alpha R W + \eta R S - \delta R }  } \end{array}
$$

根据传播学中基本再生数的定义，将垃圾信息传播的基本再生数定义为单个垃圾信息传播者在其生存周期内所传播的未知者个数，根据Driessche 和Watmough[16提出的方法可计算出该模型的基本再生数为

$$
\mathfrak { R } _ { 0 } = \operatorname* { m a x } \left\{ \frac { \alpha _ { 2 } } { \delta } , \frac { \alpha _ { 1 } } { \delta + \beta } \right\}
$$

由式(1)可知，传播网络的规模保持不变，所以假定$I ( t ) + S ( t ) + W ( t ) + R { \big ( } t { \big ) } \equiv 1$ ，则式(1)可转换为

$$
\left\{ \begin{array} { l l } { \displaystyle \frac { d I } { d t } = \delta - \alpha _ { 1 } W I - \alpha _ { 2 } S I - \delta I } \\ { \displaystyle \frac { d W } { d t } = \alpha _ { 1 } W I - \beta W - \eta \left( 1 - I - W - S \right) W - \delta W } \\ { \displaystyle \frac { d S } { d t } = \alpha _ { 2 } S I + \beta W - \eta \left( 1 - I - W - S \right) S - \delta S } \end{array} \right.
$$

其初始条件为 $I \geq 0$ ， $W \geq 0$ ， $S \geq 0$ ，正向不变集为$\Omega = \{ \left( I , W , S \right) : I \geq 0 , W \geq 0 , S \geq 0 , I + W + S \leq 1 \}$

# 1.2平衡点及其稳定性分析

当 $\Re _ { 0 } \leq 1$ 时，则式(1)存在垃圾信息消失的平衡点：

$$
E _ { 0 } \left( I _ { 0 } , W _ { 0 } , S _ { 0 } , R _ { 0 } \right) = \left( 1 , 0 , 0 , 0 \right)
$$

当 $\Re _ { 0 } > 1$ 时，除 $E _ { 0 }$ 外，还可能存在两个垃圾信息传播平衡点：

$$
E _ { 1 } \left( I _ { 1 } , W _ { 1 } , S _ { 1 } , R _ { 1 } \right) = \left( \frac { \delta } { \alpha _ { 2 } } , 0 , \frac { \alpha _ { 2 } - \delta } { \alpha _ { 2 } } , 0 \right)
$$

$$
E _ { 2 } \left( I _ { 2 } , W _ { 2 } , S _ { 2 } , R _ { 2 } \right) = \left( \frac { \eta } { \eta + \alpha _ { 2 } } , 0 , \frac { \delta } { \eta } , \frac { \alpha _ { 2 } \eta - \delta \left( \alpha _ { 2 } + \eta \right) } { \eta \left( \alpha _ { 2 } + \eta \right) } \right)
$$

令 $X = \alpha _ { 2 } \eta - \delta \bigl ( \alpha _ { 2 } + \eta \bigr )$ ，可得到如下结论：

定理1a)式(1)始终存在垃圾信息消失的平衡点 $E _ { 0 }$ 。

b)当 $\Re _ { 0 } > 1$ 时，则存在垃圾信息传播平衡点 $E _ { \mathrm { 1 } }$ 。  
c)当 $\Re _ { 0 } > 1$ 且 $X > 0$ 时，则存在垃圾信息传播平衡点 $E _ { 2 }$ 。

定理2a)当 $\Re _ { 0 } \leq 1$ 时，则 $\boldsymbol { E } _ { 0 }$ 在 $\Omega$ 内局部渐进稳定。

b)当 $\Re _ { 0 } > 1$ 且 $\frac { \alpha _ { 2 } \left( \beta + \delta \right) } { \alpha _ { 1 } \delta } > 1$ δ（α+n)>1时，则E在Ω内局部渐进稳定。

c)当 $\Re _ { 0 } > 1$ 且 $X > 0$ 时，则 $E _ { 2 }$ 在 $\Omega$ 内局部渐进稳定。

证明 系统式(3)的Jacobi矩阵为

$$
J = \left( \begin{array} { c c c } { { J ^ { 1 1 } } } & { { - \alpha _ { 1 } I } } & { { - \alpha _ { 2 } I } } \\ { { \alpha _ { 1 } W + \eta W } } & { { J ^ { 2 2 } } } & { { \eta W } } \\ { { \alpha _ { 2 } S + \eta S } } & { { \beta + \eta S } } & { { J ^ { 3 3 } } } \end{array} \right)
$$

其中： $J ^ { 1 1 } = - \alpha _ { 1 } W - \alpha _ { 2 } S - \delta ~ J ^ { 2 2 } = \alpha _ { 1 } I - \beta - \eta \big ( 1 - I - W - S \big ) + \eta W - \delta$ （204$J ^ { 3 3 } = \alpha _ { 2 } I - \eta \big ( 1 - I - W - S \big ) + \eta S - \delta$ （204号

(a）式(7)在 $E _ { 0 }$ 处对应的矩阵

$$
J _ { 0 } = \left( \begin{array} { c c c c } { { - \delta } } & { { } } & { { - \alpha _ { 1 } } } & { { - \alpha _ { 2 } } } \\ { { 0 } } & { { } } & { { \alpha _ { 1 } - \beta - \delta } } & { { 0 } } \\ { { 0 } } & { { } } & { { \beta } } & { { \alpha _ { 2 } - \delta } } \end{array} \right)
$$

$$
M _ { 0 } = - J _ { 0 } = \left( \begin{array} { c c c } { { \delta } } & { { } } & { { \alpha _ { 1 } } } & { { \alpha _ { 2 } } } \\ { { 0 } } & { { } } & { { \beta + \delta - \alpha _ { 1 } } } & { { 0 } } \\ { { 0 } } & { { } } & { { - \beta } } & { { \delta - \alpha _ { 2 } } } \end{array} \right)
$$

而 $\Delta _ { i } \left( i = 1 , 2 , 3 \right)$ 为 $M _ { 0 }$ 的 $i$ 阶顺序主子式，则

$$
\Delta _ { 1 } = \rvert \delta \rvert = \delta > 0
$$

$$
\Delta _ { 2 } \equiv \left| \begin{array} { c c c } { { \delta } } & { { } } & { { \alpha _ { 1 } } } \\ { { 0 } } & { { \beta + \delta - \alpha _ { 1 } } } \end{array} \right| = \delta \left( \beta + \delta - \alpha _ { 1 } \right) > 0
$$

$$
\Delta _ { 3 } = \left| \begin{array} { c c c c } { { \delta } } & { { } } & { { \alpha _ { 1 } } } & { { } } & { { \alpha _ { 2 } } } \\ { { 0 } } & { { } } & { { \beta + \delta - \alpha _ { 1 } } } & { { } } & { { 0 } } \\ { { 0 } } & { { } } & { { - \beta } } & { { } } & { { \delta - \alpha _ { 2 } } } \end{array} \right|
$$

$$
\stackrel { } { = } \delta \left| \begin{array} { c c } { { \beta + \delta - \alpha _ { 1 } } } & { { 0 } } \\ { { - \beta } } & { { \delta - \alpha _ { 2 } } } \end{array} \right|
$$

$$
= \delta \big ( \beta + \delta - \alpha _ { 1 } \big ) \big ( \delta - \alpha _ { 2 } \big ) > 0
$$

当 $\Re _ { 0 } \leq 1$ 时，有 $\Delta _ { \imath } > 0$ ， $\Delta _ { _ 2 } > 0$ ， $\Delta _ { 3 } > 0$ ，则 $M _ { 0 }$ 为正定矩阵，由此可得 $J _ { 0 }$ 的特征值全为负，根据Hurwitz判据[17]，可知$E _ { 0 }$ 是局部渐进稳定的。

(b)式(7)在 $E _ { 1 }$ 处对应的矩阵

$$
\begin{array} { r } { J _ { 1 } = \left( \begin{array} { c c c } { - \alpha _ { 2 } } & { \displaystyle \frac { - \alpha _ { 1 } \delta } { \alpha _ { 2 } } } & { - \delta } \\ { 0 } & { J _ { 1 } ^ { 2 2 } } & { 0 } \\ { J _ { 1 } ^ { 3 1 } } & { J _ { 1 } ^ { 3 2 } } & { \displaystyle \frac { \eta \left( \alpha _ { 2 } - \delta \right) } { \alpha _ { 2 } } } \end{array} \right) } \end{array}
$$

$J _ { 1 } ^ { \ 2 2 } = \frac { \alpha _ { 1 } \delta - \alpha _ { 2 } \left( \beta + \delta \right) } { \alpha _ { 2 } }$ （202 $J _ { 1 } ^ { \ 3 1 } = { \frac { \big ( \alpha _ { 2 } + \eta \big ) \big ( \alpha _ { 2 } - \delta \big ) } { \alpha _ { 2 } } }$ $J _ { 1 } ^ { \ 3 2 } = \frac { \beta \alpha _ { 2 } + \eta \big ( \alpha _ { 2 } - \delta \big ) } { \alpha _ { 2 } }$

$$
M _ { 1 } = - J _ { 1 } = \left( \begin{array} { c c c } { { \alpha _ { 2 } } } & { { \frac { \alpha _ { 1 } \delta } { \alpha _ { 2 } } } } & { { \delta } } \\ { { 0 } } & { { - J _ { 1 } ^ { \ 2 2 } } } & { { 0 } } \\ { { - J _ { 1 } ^ { \ 3 1 } } } & { { - J _ { 1 } ^ { \ 3 2 } } } & { { \displaystyle \frac { \eta \left( \delta - \alpha _ { 2 } \right) } { \alpha _ { 2 } } } } \end{array} \right)
$$

而 $\Delta _ { i } \left( i = 1 , 2 , 3 \right)$ 为 $M _ { 1 }$ 的 $i$ 阶顺序主子式，则

$$
\Delta _ { 1 } { = } \big | \alpha _ { 2 } \big | { = } \alpha _ { 2 } > 0
$$

$$
{ \Delta } _ { 2 } \mathbf { = } \left| \begin{array} { r l } { \alpha _ { 2 } } & { { } \quad \underline { { \alpha _ { 1 } } } \delta } \\ { \alpha _ { 2 } } & { { } = \alpha _ { 2 } \left( \beta + \delta \right) - \alpha _ { 1 } \delta , } \\ { 0 } & { { } \quad \mathbf { - } d } \end{array} \right.
$$

$$
\begin{array} { r } { \Delta _ { 3 } = \left| \begin{array} { c c c c } { \alpha _ { 2 } } & { \displaystyle \frac { \alpha _ { 1 } \delta } { \alpha _ { 2 } } } & { \delta } \\ { 0 } & { - J _ { 1 } ^ { 2 } } & { 0 } \\ { - J _ { 1 } ^ { 3 1 } } & { - J _ { 1 } ^ { 3 2 } } & { \displaystyle \frac { \eta \left( \delta - \alpha _ { 2 } \right) } { \alpha _ { 2 } } } \end{array} \right| } \\ { = \left( - J _ { 1 } ^ { 2 2 } \right) \times \displaystyle \frac { \left( \delta - \alpha _ { 2 } \right) \left[ \alpha _ { 2 } \eta - \delta \left( \alpha _ { 2 } + \delta - \alpha _ { 2 } \right) \right] } { \alpha _ { 2 } } } \end{array}
$$

当>1且 $\frac { \alpha _ { 2 } \big ( \beta + \delta \big ) } { \alpha _ { 1 } \delta } > 1 , \frac { \delta \big ( \alpha _ { 2 } + \eta \big ) } { \alpha _ { 2 } \eta } > 1$ 时，有 $\Delta _ { \scriptscriptstyle 1 } > 0$ ， $\Delta _ { 2 } > 0$ ，$\Delta _ { 3 } > 0$ ，则 $M _ { 1 }$ 为正定矩阵，由此可得 $J _ { 1 }$ 的特征值全为负，根据Hurwitz判据，可知 $E _ { \mathrm { { l } } }$ 是局部渐进稳定的。

(c)式(7)在 $E _ { 2 }$ 处对应的矩阵

$$
J _ { 2 } = \left( \begin{array} { c c c c } { { J _ { 2 } ^ { \mathrm { \tiny ~ 1 1 } } } } & { { - \displaystyle \frac { \alpha _ { 1 } \eta } { \eta + \alpha _ { 2 } } } } & { { - \displaystyle \frac { \alpha _ { 2 } \eta } { \eta + \alpha _ { 2 } } } } \\ { { 0 } } & { { J _ { 2 } ^ { \mathrm { \tiny ~ 2 2 } } } } & { { 0 } } \\ { { J _ { 2 } ^ { \mathrm { \tiny ~ 3 1 } } } } & { { \beta + \delta } } & { { \delta } } \\ { { } } & { { } } & { { } } \end{array} \right)
$$

其中：,J=_aδ+n8 ${ J _ { 2 } } ^ { 2 2 } = \frac { \eta \left( \alpha _ { 1 } - \alpha _ { 2 } \right) } { \eta + \alpha _ { 2 } } - \beta$

$$
{ \cal J } _ { 2 } ^ { ~ 3 1 } = \frac { \delta \left( \eta + \alpha _ { 2 } \right) } { \eta }
$$

$$
\begin{array} { r } { M _ { 2 } = - J _ { 2 } = \left( \begin{array} { c c c } { - J _ { 2 } ^ { \ 1 1 } } & { \displaystyle \frac { \alpha _ { 1 } \eta } { \eta + \alpha _ { 2 } } } & { \displaystyle \frac { \alpha _ { 2 } \eta } { \eta + \alpha _ { 2 } } } \\ { 0 } & { - J _ { 2 } ^ { \ 2 2 } } & { 0 } \\ { - J _ { 2 } ^ { \ 3 1 } } & { - \beta - \delta } & { - \delta } \\ { } & { } & { } \end{array} \right) } \end{array}
$$

而 $\Delta _ { i } \left( i = 1 , 2 , 3 \right)$ 为 $M _ { 2 }$ 的 $i$ 阶顺序主子式，则

$$
\begin{array} { r l } & { \begin{array} { r l } { \lambda _ { 1 } - \frac { \rho \lambda _ { 2 } + \rho \lambda _ { 3 } } { \rho } , ~ } & { \psi _ { 1 } ^ { \lambda _ { 2 } } + \frac { \lambda _ { 3 } + \rho \lambda _ { 3 } } { \rho } , ~ } \\ { ~ } & { \psi _ { 2 } ^ { \lambda _ { 3 } } ~ } \\ { ~ } & { \psi _ { 3 } ^ { \lambda _ { 3 } } ~ } \\ { ~ } & { \psi _ { 4 } ^ { \lambda _ { 4 } } ~ } \\ { ~ } & { \psi _ { 5 } ^ { \lambda _ { 5 } } ~ } \\ { ~ } & { \psi _ { 6 } ^ { \lambda _ { 7 } } ~ } \\ { ~ } & { \psi _ { 7 } ^ { \lambda _ { 8 } } ~ } \\ { ~ } & { \psi _ { 8 } ^ { \lambda _ { 7 } } ~ } \\ { ~ } & { \psi _ { 8 } ^ { \lambda _ { 8 } } ~ } \\ { ~ } & { \psi _ { 8 } ^ { \lambda _ { 8 } } ~ } \\ { ~ } & { \psi _ { 8 } ^ { \lambda _ { 8 } } ~ } \end{array} \begin{array} { r l } { \psi _ { 1 } } & { \psi _ { 1 } } \\ { ~ } & { \psi _ { 1 } } \\ { ~ } & { \psi _ { 1 } } \\ { ~ } & { \psi _ { 1 } } \\ { ~ } & { \psi _ { 8 } ^ { \lambda _ { 8 } } } \end{array} } \\ { ~ } \\ & { \begin{array} { r l } { \psi _ { 1 } ^ { \lambda _ { 7 } } } & { \psi _ { 1 } ^ { \lambda _ { 8 } } } \\ { ~ } & { \psi _ { 1 } ^ { \lambda _ { 8 } } } \\ { ~ } & { \psi _ { 1 } ^ { \lambda _ { 8 } } } \\ { ~ } & { \psi _ { 1 } ^ { \lambda _ { 7 } } } \\ { ~ } & { \psi _ { 2 } ^ { \lambda _ { 8 } } } \end{array} \begin{array} { r l } { \psi _ { 1 } } & { \psi _ { 1 } } \\ { ~ } & { \psi _ { 2 } } \\ { ~ } & { \psi _ { 3 } } \\ { ~ } & { \psi _ { 4 } ^ { \lambda _ { 7 } } } \\ { ~ } & { \psi _ { 5 } ^ { \lambda _ { 8 } } } \end{array} } \\ { ~ } \\ &  \begin{array} { r l } { \psi _ { 1 } ^ { \lambda _ { 7 } } } & { \psi _ { 1 } ^ { \lambda _ { 7 } } } \\ { ~ } & { \psi _ { 5 } ^ { \lambda _ { 7 } } } \\ { ~ } & { \psi _ { 6 } ^ { \lambda _ { 7 } } } \\ { ~ } & { \psi _ { 7 } ^ { \lambda _ { 7 } } } \\ { ~ } & { \psi _ { 8 } ^ { \lambda _ { 7 } } } \end{array} \end{array}
$$

当 $\Re _ { 0 } > 1$ 时，有 $\Delta _ { \mathrm { 1 } } > 0$ ， $\Delta _ { 2 } > 0$ ， $\Delta _ { 3 } > 0$ ，则 $M _ { 2 }$ 为正定矩阵，可得 $J _ { \mathbf { \Phi } _ { 2 } }$ 的特征值全为负，根据Hurwitz判据，可知 $E _ { 2 }$ 是局部渐进稳定的。

定理3a）当 $\Re _ { 0 } \leq 1$ 时，则 $E _ { 0 }$ 在 $\Omega$ 内全局渐进稳定。b）当 $\Re _ { 0 } > 1$ 时，则 $E _ { 1 }$ 在 $\Omega ^ { \prime }$ 内全局渐进稳定，此处

$\Omega ^ { \underline { { { \sf \cdot } } } } = \{ \big ( I , W , S , R \big ) \colon I \leq \frac { \delta } { \alpha _ { 2 } } , W \geq 0 , S \geq 0 , R \geq 0 ,$ $I + W + S + R \leq 1 \}$

证明a)针对式(1)的垃圾信息消失平衡点 $E _ { 0 }$ ，考虑Lyapunov 函数

$$
V \big ( W , S \big ) = S + \mu W
$$

其中： $\mu$ 为正常数，且 $V \geq 0$ 恒成立，则

$$
\begin{array} { r l } & { \quad \displaystyle \frac { \mathrm { d } V } { \mathrm { d } t } \bigg \vert _ { ( 3 ) } = S ^ { \star } + \mu W ^ { \star } = } \\ & { \quad \displaystyle \left( \alpha _ { 2 } S I + \beta W - \eta R S - \delta S \right) + } \\ & { \quad \quad \mu \left( \alpha _ { 1 } W - \beta W - \eta R W - \delta W \right) = } \\ & { \quad \delta S I \left( \frac { \alpha _ { 2 } } { \delta } - \frac { 1 } { I } \right) + \mu \delta \frac { \alpha _ { 1 } } { \alpha _ { 2 } } W \left( \frac { \alpha _ { 2 } } { \delta } - \frac { 1 } { I } \right) + } \\ & { \quad \quad \displaystyle \left( \mu \delta \frac { \alpha _ { 1 } - \alpha _ { 2 } } { \alpha _ { 2 } } + \beta - \mu \beta \right) W - \mu \eta R \left( S + W \right) } \end{array}
$$

令μ= $\mu { = } \frac { \beta \alpha _ { 2 } } { \beta \alpha _ { 2 } { + } \big ( \alpha _ { 2 } { - } \alpha _ { 1 } \big ) \delta }$ βa+(a-a）s，则

$$
\begin{array} { r l } & { \frac { \displaystyle { \mathrm { d } } V } { \displaystyle { \mathrm { d } } t } \Big \vert _ { ( 3 ) } = \delta S I \bigg ( \frac { \alpha _ { _ 2 } } { \delta } - \frac { 1 } { I } \bigg ) + } \\ & { \frac { \beta \alpha _ { _ 1 } } { \beta \alpha _ { _ 2 } + \big ( \alpha _ { _ 2 } - \alpha _ { _ 1 } \big ) \delta } \delta W I \bigg ( \frac { \alpha _ { _ 2 } } { \delta } - \frac { 1 } { I } \bigg ) - } \\ & { \frac { \beta \alpha _ { _ 2 } } { \beta \alpha _ { _ 2 } + \big ( \alpha _ { _ 2 } - \alpha _ { _ 1 } \big ) \delta } \eta R \big ( S + W \big ) } \end{array}
$$

从而 $V ^ { \prime } { \le } 0$ 在 $\Omega$ 中恒成立，并且当且仅当 $W = 0$ ， $S = 0$ 时$V ^ { \prime } = 0$ 成立。根据LaSalle不变集原理[18]以及极限方程原理可知， $E _ { 0 }$ 在 $\Omega$ 是全局渐进稳定的。

b)针对式(1)的垃圾信息传播平衡点 $E _ { 1 }$ ，考虑Lyapunov 函数:

$$
V \left( I , S \right) = \frac { 1 } { 2 } { \left( I - I _ { 1 } \right) } ^ { 2 } + \frac { 1 } { 2 } \kappa { \left( S - S _ { 1 } \right) } ^ { 2 }
$$

其中 $\kappa$ 为正常数，且 $V \geq 0$ 恒成立，则

$$
\begin{array} { r l } & { \frac { \mathrm { d } Y } { \mathrm { d } t } | _ { \cdot \rangle \cdot \rangle \big { = } } ( I - L _ { \cdot } ) Y + \kappa ( S - S _ { \cdot } ) | S ^ { \prime } = } \\ & { ( I - I _ { \cdot } ) [ \delta - \omega _ { \cdot } W - \omega _ { \cdot } W - \delta I ] + } \\ & { \kappa ( S - S _ { \cdot } ) | \alpha _ { \cdot } \Omega _ { S } Y + \beta W - \delta S ^ { \prime } \rangle } \\ & { ( I - I _ { \cdot } ) [ \big ( \alpha _ { \cdot } W - \alpha _ { \cdot } S - \delta \big ) ( I - I _ { \cdot } ) ] = } \\ & { - \omega _ { \cdot } L _ { \cdot } \big ( S - S _ { \cdot } \big ) ] + \kappa ( S - S _ { \cdot } ) \big [ \big ( \alpha _ { \cdot } L ^ { \prime } - \eta R - \delta \big ) ( S - S _ { \cdot } ) } \\ & { + \omega _ { \cdot } \Delta _ { \cdot } \big ( I - I _ { \cdot } ) \big ] = ( - \omega _ { \cdot } W - \alpha _ { \cdot } S - \delta ) ( I - I _ { \cdot } ) ^ { 2 } - } \\ & { \omega _ { \cdot } L _ { \cdot } ( S - S _ { \cdot } ) _ { \cdot \vert \mathbf { r } \vert } ( I - I _ { \cdot } ) + \kappa ( \omega _ { \cdot } 2 - \eta R - \delta ) ( S - S _ { \vert \cdot } ) ^ { 2 } } \\ & { + \kappa \omega _ { \cdot } S _ { \cdot } \big ( I - I _ { \cdot } ) ( S - S _ { \cdot } ) = - ( \alpha _ { \cdot } W + \alpha _ { \cdot } S + \delta ) ( I - I _ { \cdot } ) ^ { 2 } + } \\ & { \kappa ( \alpha _ { \cdot } L ^ { \prime } - \eta R - \delta ) \big ( S - S _ { \cdot } \big ) ^ { 2 } + } \\ & { ( \kappa \omega _ { \cdot } S - \omega _ { \cdot } L ^ { 2 } ) ( S - S _ { \cdot } ) ( I - I _ { \cdot } ) } \\ & { ( \kappa \omega _ { \cdot } \Omega _ { \cdot } - \omega _ { \cdot } ) ( I - S _ { \cdot } ) \big ( I - I _ { \cdot } \big ) } \end{array}
$$

$\kappa { = } \frac { \delta } { \alpha _ { 2 } - \delta }$ α-δ，则

$$
\begin{array} { l } { \displaystyle \frac { \mathrm { d } V } { \mathrm { d } t } \Big \vert _ { ( 3 ) } = - \big ( \alpha _ { 1 } W + \alpha _ { 2 } S + \delta \big ) \big ( I - I _ { 1 } \big ) ^ { 2 } + } \\ { \displaystyle \frac { \delta } { \alpha _ { 2 } - \delta } \big ( \alpha _ { 2 } I - \eta R - \delta \big ) \big ( S - S _ { 1 } \big ) ^ { 2 } } \end{array}
$$

从而 $V ^ { \prime } { \le } 0$ 在 $\Omega ^ { \prime }$ 中恒成立，且当且仅当 $I = \frac { \delta } { \alpha _ { 2 } }$ $S = \frac { \alpha _ { 2 } - \delta } { \alpha _ { 2 } }$ 时$V ^ { \prime } { = } 0$ 成立。根据LaSalle不变集原理， $E _ { \mathrm { 1 } }$ 是全局渐进稳定的。

# 2 数值仿真分析

# 2.1主要参数设置

如未特别指明，在实验中设置 $\boldsymbol { I } ^ { * } = 0 . 2 ~ , \boldsymbol { W } ^ { * } = 0 . 4 ~ , ~ \boldsymbol { S } ^ { * } = 0 . 2$ ，$\boldsymbol { R } ^ { * } = 0 . 2$ 。其中 $\boldsymbol { I } ^ { * }$ 指初始条件下的无知者人群， $\boldsymbol { W } ^ { * }$ 指初始条件

下的弱传播者人群， $s ^ { * }$ 指初始条件下的强传播者人群。 $\boldsymbol { R } ^ { * }$ 指初始条件下的移出者人群。

# 2.2数值仿真结果

为了验证所得结论的正确性，下面对本文建立的模型进行数值仿真分析。

a)当 $\scriptstyle \alpha _ { 1 } = 0 . 2$ ， $\alpha _ { 2 } { = } 0 . 3$ ， $\beta { = } 0 . 3$ ， $\scriptstyle \eta = 0 . 5$ ， $\scriptstyle { \delta = 0 . 4 }$ ， $\boldsymbol { I } ^ { * } = 0 . 2$ ，$\boldsymbol { W } ^ { * } = 0 . 4$ ， $\boldsymbol { S } ^ { * } = 0 . 2$ ， $\boldsymbol { R } ^ { * } = 0 . 2$ 时，通过简单计算可得$\mathfrak { R } _ { 0 } = \operatorname* { m a x } \left\{ 0 . 2 , 0 . 7 5 \right\} _ { \ } = 0 . 7 5 < 1$ 。根据定理3，得出垃圾信息消失的平衡点 $E _ { 0 } ( I _ { \mathrm { 0 } } , W _ { \mathrm { 0 } } , S _ { \mathrm { 0 } } , R _ { \mathrm { 0 } } ) = ( 1 , 0 , 0 , 0 )$ 是全局渐进稳定的。如图4所示，系统稳定在了平衡点 $E _ { 0 }$ ，垃圾信息最终消失。仿真结果与定理3的理论结果相一致。由图3可知 $I _ { \setminus }$ $W$ ， $s$ 在不同初始条件下的演变结果最终均收敛于 $E _ { 0 }$ 。

![](images/fe1d77e6e921e96757982b5a5b897949fdce265437f599954edf1140a24831d3.jpg)  
图3 $\Re _ { 0 } \leq 1$ 时，各 $I ( t )$ ， $W ( t ) { + } S ( t )$ (蓝色菱形)最终收敛于点$\left( I , W + S \right) = \left( 1 , 0 \right)$ (红色圆点)

![](images/aee4601cc61fa343f7c5bcbb876fcb5f4b23e44fcfd462a67d3c6d40f7db859c.jpg)  
图4 $\Re _ { 0 } \leq 1$ 时 $I ( t )$ ， $W ( t )$ ， $S ( t )$ 和 $W ( t ) { + } S ( t )$ 的时间响应曲线

b)当 $\scriptstyle \alpha _ { 1 } = 0 . 3$ ， $\alpha _ { 2 } { = } 0 . 4$ ， $\beta { = } 0 . 1$ ， $\scriptstyle \eta = 0 . 5$ ， $\delta \mathrm { = } 0 . 3$ 时，通过简单计算可得 $\mathfrak { R } _ { 0 } = \operatorname* { m a x } \left\{ 0 . 7 5 , 1 . 3 \right\} = 1 . 3 > 1$ ， $E _ { 1 } = \left( 0 . 7 5 , 0 , 0 . 2 5 , 0 \right)$ ，且$I < \delta / \alpha _ { 2 }$ 。根据定理3，垃圾信息传播平衡点 $E _ { \mathrm { 1 } }$ 是全局渐进稳定的，如图6所示垃圾信息将在网络中持续传播。根据图5可得， $\mid I _ { \setminus }$ W、 $s$ 在各初始条件下的演化结果最终均收敛于 $E _ { \mathrm { { l } } }$ 。

c)当 $\alpha _ { 1 } { = } 0 . 4$ ， $\alpha _ { 2 } { = } 0 . 6$ ， $\beta { = } 0 . 1$ ， $\scriptstyle \eta = 0 . 4$ ， $\delta \mathrm { = } 0 . 2$ 时，通过简单计算可得 $\mathfrak { R } _ { 0 } = \operatorname* { m a x } \left\{ 1 . 3 , 3 \right\}$ $^ { = 3 > 1 }$ $X = \alpha _ { 2 } \eta - \delta \left( \alpha _ { 2 } + \eta \right) = 0 . 0 4 > 0$ ，根据定理1，系统垃圾信息传播平衡点 $E _ { 2 }$ 存在，此时有 $E _ { \scriptscriptstyle 2 } = \left( 0 . 4 , 0 , 0 . 5 , 0 . 1 \right)$ 。根据定理2，垃圾信息传播平衡点 $E _ { 2 }$ 是局部渐进稳定的。从图8可以看出系统在 $E _ { 2 }$ 处稳定。仿真结果与定理2的理论结果相符。由图7得，I、W、 $s$ 在不同初始条件下的演变结果均收敛于 $E _ { 2 }$ 。

![](images/69adde11788b9abfd7325d9c835ba206d107d95ed38677c32e8df8d884bb33fd.jpg)  
图5 $\Re _ { 0 } > 1$ 时，各 $I ( t )$ ， $W ( t ) { + } S ( t ) ($ 蓝色菱形)最终收敛于点$( I , W + S ) { = } ( 0 . 7 5 , 0 . 2 5 )$ (红色圆点)

![](images/75cac0f40f4bdb206e59104e526d19ea147bd8b5b421110f1d604cc478d629e9.jpg)  
图6 $\Re _ { 0 } > 1$ 时I(t)， $W ( t )$ ， $S ( t )$ 和 $W ( t ) { + } S ( t )$ 的时间响应曲线

![](images/668c80fce4c681856391feb97a780db7b88db4609ae791442333d15fc4801603.jpg)  
图7 $\Re _ { 0 } > 1$ 时，各 $I ( t )$ ， $W ( t ) { + } S ( t ) ($ 蓝色菱形)最终收敛于点$\left( I , W + S \right) = \left( 0 . 4 , 0 . 5 \right)$ (红色圆点)

d由 $\frac { \partial \mathfrak { R } _ { 0 } } { \partial \delta } = - \frac { \alpha _ { 1 } } { \left( \beta + \delta \right) ^ { 2 } } < 0$ 可知， $\mathfrak { R } _ { 0 }$ 与 $\delta$ 成反比例关系，即R随δ的增加而减小，如图9所示。由α $\frac { \partial \mathfrak { R } _ { _ 0 } } { \partial \alpha _ { 2 } } = \frac { 1 } { \delta } > 0$ 得， $\mathfrak { R } _ { 0 }$ 与$\alpha _ { 2 }$ 成正比例关系，即 $\Re _ { 0 }$ 随 $\alpha _ { 2 }$ 的减小而减小，如图10所示。

![](images/1a0bcd52e499b79f1c7c162f5311089606de1095ab6c28835c5626678f962ab4.jpg)  
图8 $\Re _ { 0 } > 1$ 时 $I ( t )$ ， $W ( t )$ ， $S ( t )$ 和 $W ( t ) { + } S ( t )$ 的时间响应曲线

![](images/b3b856c19d993fab1e03df20651c07825ce4dee5e82e41d15bf3867cc7a4581a.jpg)  
图9基本再生数 $\Re _ { 0 }$ 关于 $\delta$ 的函数

![](images/ba6cfed31b2f742583e5cafb0db75499bd220e1d464416c09d2efc323a7c81e4.jpg)  
图10基本再生数 $\mathfrak { R } _ { 0 }$ 关于 $\alpha _ { 2 }$ 的函数

e)在实验中令 $\alpha _ { 1 } { = } 0 . 4$ ， $\alpha _ { 2 } { = } 0 . 6$ ， $\beta { = } 0 . 1$ ， $\scriptstyle \eta = 0 . 4$ ， $\delta$ 的取值分别为0.2，0.4，0.5，0.7，实验结果如图11所示。从图11可以看出，随 $\delta$ 值的增加，垃圾信息传播者数量明显减少，当 $\delta$ 取值满足 $\Re _ { 0 } < 1$ 时，最后达到的状态是垃圾信息传播者比例趋近零。在实验中令 $\scriptstyle \alpha _ { 1 } = 0 . 2$ ， $\beta { = } 0 . 3$ ， $\delta \mathrm { = } 0 . 2$ ， $\eta { = } 0 . 4$ ， $I _ { 0 } = 0 . 2$ ，$W _ { 0 } = 0 . 4$ ， $S _ { \mathrm { 0 } } = 0 . 2$ ， $R _ { \mathrm { 0 } } = 0 . 2$ ， $\alpha _ { 2 }$ 的取值分别为0.2，0.3，0.5,0.6，实验结果如图12所示。从图12可以得到，随 $\alpha _ { 2 }$ 增加，垃圾信息传播者的数量明显增加，当 $\alpha _ { 2 }$ 的值满足 $\Re _ { 0 } > 1$ 时，传播者比例由零开始上升。

![](images/ebd7360c975d2db9074a49987d01c1b8e7341610f536f7a10a9e4ce60e44b058.jpg)  
图11不同 $\delta$ 值 $S ( t ) { + } W ( t )$ 的时间响应曲线

![](images/19ad15b0c7d18adc74043b33de1b6c661ff2c8090ba8909d30ffc6961b7f7e20.jpg)  
图12不同 $\alpha _ { 2 }$ 值 $S ( t ) { + } W ( t )$ 的时间响应曲线

![](images/4c589566060e1cf83cd0a3c0cf73825b7f849b4aa21bf466a7cac1776a2d1f36.jpg)  
图13信息传播者随时间 $t$ 的变化曲线

f)对2018年3月1日至3月9日期间，阐清子纪凌尘的八卦信息在新浪微博上的传播进行采集和挖掘，得到该信息传播的日活跃用户数量如表1所示。为进行对比实验，选取参数令$\scriptstyle \alpha _ { 1 } = 0 . 2$ ， $\alpha _ { 2 } { = } 0 . 6$ ， $\beta { = } 0 . 1$ ， $\scriptstyle \eta = 0 . 8$ ， $\delta { = } 0 . 5$ ，并根据3月1日的传播量设定初始未知者、弱传播者和强传播者数量分别为1170，3540，1170。由此可得初始值为 $\boldsymbol { I } ^ { * } = \boldsymbol { 0 . 2 }$ ， $\boldsymbol { W } ^ { * } = 0 . 4$ ，$\boldsymbol { S } ^ { * } = 0 . 2$ ， $\boldsymbol { R } ^ { * } = 0 . 2$ 。对比实验结果如图13所示，蓝色曲线是根据理论模型模拟的一段时间内强传播者和弱传播者数量之和的变化曲线，红色曲线是由表1数据所得的八卦信息传播活跃人数变化曲线。从图13可以看出，模拟曲线与实际传播曲线能够较好拟合，即该模型能大致反映此八卦信息的传播过程，因此本模型有一定的可靠性。而通过图13，发现模拟传播曲线与实际情况在细节上仍存在一定的误差，通过分析得出导致误差的原因包括：a)只考虑网络用户传播能力的差异性，所建立的理论模型未考虑实际传播过程中其他因素对垃圾信息传播的影响；b)互联网是具有无尺度与小世界双重特征的复杂网络，而本模型建立在均匀分布的网络结构基础之上，与实际情况存在一定差异。

表1明星分手信息日传播量  

<html><body><table><tr><td colspan="8">3月1日3月2日3月3日3月4日3月5日3月6日3月7日3月8日3月9日</td></tr><tr><td>5310</td><td>2265</td><td>1355</td><td>1202</td><td>942</td><td>1000</td><td>937 1017</td><td>1007</td></tr></table></body></html>

# 3 结束语

本文考虑到用户传播能力差异对垃圾信息传播的影响，建立了基于传播能力差异的垃圾信息传播模型。计算了模型的基本再生数，分析了模型的垃圾信息消失平衡点及其中一个垃圾信息传播平衡点的全局稳定性，同时对另一垃圾信息传播平衡点的局部稳定性进行了分析。模型的理论分析和计算机仿真结果表明，垃圾信息传播最终达到的状态取决于基本再生数 $\Re _ { 0 }$ ，当 $\Re _ { 0 } \leq 1$ 时，垃圾信息最终消失；当 $\Re _ { 0 } > 1$ 时，垃圾信息将在网络中持续传播。基于研究结论，提出如下垃圾信息防治建议：a)在一定条件下，政府应加大对大众的通识教育，提高大众辨识能力，以减少对垃圾信息的传播。即减少 $\alpha _ { 2 }$ 值，降低其影响力度；b)在一定条件下，政府等机构应加大对垃圾信息传播的监管力度，约束大众行为，使其不参与垃圾信息传播。即增大$\delta$ 值，增加其影响力度。

本文模型是建立在均匀分布的网络结构基础上，然而真实互联网是具有无尺度与小世界双重特性的复杂网络。此外，对微博八卦信息传播数据的采集过程中发现，周末垃圾信息的传播量会呈现较大波动，这表明垃圾信息传播具有时变特性，因此下一步工作将考虑垃圾信息传播的时变特性与互联网的无尺度与小世界特征，建立基于复杂网络的垃圾信息传播动力学模型，得出垃圾信息的网络传播规律。

参考文献：   
[1]路鹃．新媒体环境下垃圾邮件、短信的危害及法律规制探讨[J].新闻 界,2016,14: 42-46. (Lu Juan.The harm of spam and text messges in new media environment and legal regulations [J].Press Circles,2016,14: 42-46.)   
[2] 蒲建国．网络时代，垃圾信息霸屏的隐忧—一浅析自媒体信息传播的 乱象、危害及对策[J]．中国地市报人,2017,9:26-28.(PuJianguo.In the internet age,the concealment of spam and information barriers—analysis of the chaos,harms and countermeasures of self-media information dissemination [J]. China Prefecture and Town,2017,9: 26-28.）   
[3]Laorden C, Ugarte-Pedrero X, Santos I,et al. Study on the effectiveness of anomaly detection for spam filtering [J]. Information Sciences,2014,277 (9): 421-44.   
[4]林英，陈静怡，秦江龙．基于贝叶斯分类的垃圾短信过滤方法研究[J]. 计算机与数字工程,2016,44(9):1752-1756.(Lin Ying,Chen Jingyi, Qin Jianglong. Spam messages filtering methods based on bayes classification [J]. Computer & Digital Engineering,2016,44(9): 1752-1756.)   
[5]孙大鹏.云计算技术在垃圾短信过滤中的应用与实现[J].信息网络安 全，2015,7:13-19.(Sun Dapeng. Application and implementation of Hadoop cloud computing technology in junk message filtering [J]. Information Network Security,2015,7:13-19.)   
[6]Li Xiaomang,Jung HR, Youn HY,et al.An incremental learning based framework for image spam filtering [J]. International Journal of Computer Science,Engineering and Applications,2014,4(1): 25-40.   
[7]Chan PPK, Yang C,Yeung D S,et al. Spam filtering for short messages in adversarial environment [J]. Neurocomputing,2015,155 (C):167-176.   
[8]Mccluskey C C.Global stability for an SIR,epidemic model with delay and nonlinear incidence [J].Nonlinear Analysis Real World Applications,2010, 11 (4): 3106-3109.   
[9]Beretta E,Takeuchi Y. Global stability of an SIR epidemic model with time delays [J]. Journal of Mathematical Biology,1995,33 (3): 250.   
[10] Xu Ruzhi,Li Heli,Xing Changming. Research on information dissemination model for social networking services [J].International Journal of Computer Science and Application,2013,2 (1): 1-6.   
[11] Ananthaswamy V, Seethalakshmi B. Mathematical analysis of information dissemination model for social networking services [J].American Journal of Modeling andOptimization,2015,3(1): 26-34.   
[12] Zhang Haifeng,Xiong Fei,Liu Yun,et al.Modeling and analysis of information dissemination inonline social networks[J]. Journalof Interet

Technology,2015,16(1): 1-10.

[13]魏德志，陈福集，郑小雪．微博虚假信息传播模型的仿真研究[J].计 算机仿真,2015,32(12):158-163.(Wei Dezhi,Chen Fuji,Zheng Xiaoxue. Simulation research on propagation model of microblog false information [J].Computer Simulation,2015,32(12): 158-163.)

[14]申志伟，张彬，陈文基．基于有害信息传播模型的互联网治理研究[J]. 北京邮电大学学报,2010,12(5):32-37.(Sheng Zhiwei, Zhangbin,Chen Wenji.Research on Internet governance based on harmful information propagation model [J].Journal of Beijing University of Posts and Telecommunications,2010,12(5):32-37.)

[15]赖东威．网络信息传播力的构成维度[J].青年记者,2017,23:6-7.(Lai Dongwei.The constituent dimension of network information dissemination [J].Youth Journalist,2017,23: 6-7.)   
[16] Van d Driessche P,Watmough J.Reproduction numbers and sub-threshold endemic equilibria for compartmental models of disease transmission [J]. Mathematical Biosciences,2002,180 (1-2): 29-48.   
[17]Robinson R C.An introduction to dynamical systems: continuous and discrete [M].2nd ed.[S.1.]:American Mathematical Society,2012.   
[18]Lasalle JP. Invariance principle in the theory of stability [M].New York: Academic Press,1966:277-286.