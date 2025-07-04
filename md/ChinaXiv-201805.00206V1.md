# 差分隐私模型的启发式隐私参数设置策略

欧阳佳1，肖政宏」，刘少鹏1，印鉴²，林丕源(1．广东技术师范学院 计算机科学学院，广州 510665;2.中山大学 数据科学与计算机学院，广州 510275;3．华南农业大学 数学与信息学院，广州 510642)

摘要：差分隐私模型是一种强隐私模型，用隐私参数ε度量隐私保护程度及噪声量，近年来成为隐私保护领域的研究热点。但是隐私参数ε的设置只能依赖于实验或专业人士经验，限制了差分隐私模型的使用与推广。针对这个问题，基于(pl，p2)-隐私模型提出一种启发式的隐私参数ε设置策略(limit privacy breaches in differential privacy，LPBDP)，分析隐私参数ε与(pl，p2)的内在联系，实现噪声量的添加由(pl，p2)决定。LPBDP通过如下启发式原则设置隐私参数ε：如果攻击者关于目标受害者的先验概率小于阈值pl，攻击者得到差分隐私查询策略返回的加噪结果后，关于目标受害者的后验概率必须小于阈值p2。实验表明LPBDP能够更直观地设置隐私参数ε以满足差分隐私约束。

关键词：隐私保护；差分隐私；隐私参数；隐私泄露 中图分类号：TP309.2 doi:10.3969/j.issn.1001-3695.2017.06.0649

# Heuristic privacy parameter setting strategy for differential privacy model

Ouyang Jia1, Xiao Zhenghongl,Liu Shaoeng1,Yin Jian²,Lin Piyuan³ (1.College ofComputerScienceGuangdongPolytechnicNormalUniversityGuangzhou510665,China;2.SholofData& Computer Science,Sun Yat-sen University,Guangzhou510275,China;3.ColegeofMathematics&Informatics,South China Agricultural University,Guangzhou 510642,China)

Abstract: The diferential privacy modelisakindofstrong privacy model,which uses the privacyparameterε to measure the degree ofprivacy protection and theamount of noise.In recent years,the privacy model has become a hotspot in the field of privacyprotection.However,the seting of the privacy parameterεcan only dependon the experience of the lab or the profesional experience,limitingtheadoptionand popularizeofthe differential privacy model.Aimingat this problem,akind ofheuristic privacyparameterεsetingstrategy（limitprivacybreaches indiferential privacy,LPBDP）is proposed basedon the(p1,p2)-privacymodel.The intrinsicrelationshipbetweentheprivacyparameterεand(pl,p2)isanalyed,andtheaddition ofthe noisequantityis determined bythe parameters (pl,p2).LPBDPsets the privacy parameterεbythe following heuristic principle:Iftheatacker'sprior probabilityofthetargetvictim islessthanthethresholdpl,then,theatacker'sposterior probabilityofthe victimofthe target mustbelessthan threshold p2.Experiments showthatLPBDPcan more visually set the privacy parameter ε to meet the differential privacy constraints.

Key Words: privacy-preserving; differential privacy; privacy parameter; privacy breaches

# 0 引言

由于对原始数据的访问是数据挖掘的前提，但原始数据中往往包含个人的隐私信息，因此随之而来的是个人对隐私保护越来越关注。目前，数据挖掘领域中一个重要的研究方向是准确得到知识的同时保证数据与个人隐私的安全。

随着计算机科学、网络以及存储技术的发展，人类社会收集、存储的数据已经达到了前所未有的程度，数据的爆炸式增长又促进了数据挖掘的巨大发展，数据挖掘技术已经成功应用于社会的各行各业，如：医疗、社交网络、在线搜索等领域。

隐私保护数据挖掘的出现就是为了解决上述数据挖掘所带来的隐私担忧问题。隐私保护数据挖掘的目的是能成功构建各种有效的数据挖掘模型而不会泄露输入的原始数据[I\~4]。具体来说，隐私保护数据挖掘需要解决如下两个关键问题：a)如何在数据挖掘的过程中保护个人隐私；b）如何确保数据或结果的效用性。目前，隐私保护数据挖掘主要集中于隐私准则的设计以及同时满足上述两个关键点的算法。

ε-差分隐私模型[5\~8]不对攻击者的背景知识作任何假设，是一种隐私保护力度非常强的隐私模型，它的基本思想是发布对敏感数据的分析结果之前，添加少量噪声以满足差分隐私要求，噪声量由分析函数或分析过程的敏感度以及隐私参数ε共同决定，与具体的数据库类型及其大小无关。

隐私参数ε是差分隐私模型的重要参数，用于决定噪声的添加量以及度量隐私保护的程度。从拉普拉斯机制与指数机制中可以看出，ε越大，添加的噪声越少，相反，ε越小，添加的噪声越多。但差分隐私模型在决定添加噪声量的多少时存在两个方面的问题：第一个问题是隐私参数ε仅仅限制了个体记录对结果的影响，而不是限制个人泄露了多少信息[9]，将导致攻击者在获得随机结果后很容易识别个人的敏感信息；第二个问题是隐私参数ε的设置只能依赖于实验或专业人士的经验，没有更加直观的启发式参数设置方法。

针对上述两个问题，本文的主要贡献如下：

a)为限制差分隐私模型中个人信息的泄露，基于 $( \rho _ { 1 } , \rho _ { 2 } )$ -隐私模型的思想，提出一种新的攻击模型；b）找出隐私参数ε与 $( \rho _ { 1 } , \rho _ { 2 } )$ 之间的关系，提出了一种启发式隐私参数设置策略。

# 1 相关工作

针对恶意攻击者的攻击手段，研究者已提出众多优秀的隐私模型，如针对链接攻击的 $k \mathrm { . }$ -匿名模型[II]；针对属性攻击的 $l -$ 多样化模型[12]。这些模型的基本思想都是基于数据的匿名分组，匿名过程将整个数据集划分为多个等价类，每个等价类中至少包含 $k$ 条记录，恶意攻击者识别个体的概率最多为 $1 / k$ 。

差分隐私(differentialprivacy)l是一种完全独立于攻击者背景知识和计算能力的强隐私概念，近年来已成为研究热点。它假设攻击者拥有任意的背景知识，无论特定个体记录是否在数据集中，对该数据集的任意计算分析或查询的结果在形式上不可区分。差分隐私随机算法对任意两个邻近数据集进行操作，得到的结果几乎是一致的。形式化来说，已知 $D$ 为任意数据集，设与 $D$ 只相差一条记录的近邻数据集为 $D ^ { \prime }$ ，差分隐私要求任意算法对 $D$ 与 $D ^ { \prime }$ 得到相同结果的概率的比值有一个常数上界。差分隐私模型体系中最基本的模型是 $\varepsilon$ -差分隐私模型，其定义如下：

$\varepsilon$ -差分隐私(differential privacy)[6]：随机算法 $\pi$ 满足 $\boldsymbol { \varepsilon }$ -差分隐私约束，如果任意的两个邻近数据集 $D$ 和 $D ^ { \prime }$ ， $\left| D \Delta D ^ { \prime } \right| = 1$ ，对于所有输出数据集 $\phantom { 0 } O$ ，下列不等式成立：

其中： $\left| D \Delta D ^ { \prime } \right| = 1$ 表示数据集 $D$ 和 $D ^ { \prime }$ 只有一条记录不同， $\varepsilon \cdot$ 差分隐私保证 $D$ 中任意一条记录的改变对算法 $\pi$ 输出的影响都不会过于明显。拉普拉斯机制与指数机制是满足差分隐私约束的两种标准方法，它们均依赖于函数的全局敏感度。

Lee等人[9]提出了一种 $\rho \cdot$ 差分可识别(differentialidentifiability)的概念， $\rho$ -差分可识别提供与 $\varepsilon \cdot$ 差分隐私模型一样的隐私保护力度，它的优点是参数 $\rho$ 限定了每个个体对分析结果贡献的概率估计。 $\rho$ -差分可识别通过限定攻击者对个体的后验概率将隐私参数 $\boldsymbol { \varepsilon }$ 与 $\rho$ 联系在一起，数据挖掘者或数据发布者可以基于 $\rho$ -差分可识别设置隐私参数 $\boldsymbol { \varepsilon }$ ，添加的噪声限定攻击者在获得分析结果后推断目标受害者敏感值的概率不高于$\rho$ 。隐私机制 $M$ 满足 $\rho$ -差分可识别约束，需要隐私参数 $\boldsymbol { \varepsilon }$ 与 $\rho$ 满足如下关系：

$$
\varepsilon = \ln { \frac { \left( m - 1 \right) \rho } { 1 - \rho } }
$$

其中： $U$ 为所有可能的值以及 $m = \left| { U } \right|$ ，在假设 $U$ 中所有的 $i$ 的先验概率 $\mathrm { P r } [ D = D ^ { \prime } \mathrm { Y } \{ i \} ]$ 都相等以及 $| U |$ 已知的情况下， $\rho$ -差分可识别与差分隐私之间存在一种联系，即：任意的 $\rho$ -差分可识别隐私机制都满足 $\ln \left( m - 1 \right) \rho / ( 1 - \rho )$ -差分隐私约束。从式(2)中得出， $\rho$ -差分可识别依赖于个体的先验分布，并假设预先知道所有可能的值 $U$ 以及 $1 0 \%$ 然而现实中，个体的先验分布一般都是不相等的，甚至根本无法预先获得先验分布，并且不一定完全知道 $U$ 的值。因此本文基于 $( \rho _ { 1 } , \rho _ { 2 } )$ -隐私模型提出一种独立于这种先验分布的隐私参数设置策略。

# 2 基于(p1,p2)-隐私模型的隐私参数设置

# 2.1隐私模型

文献[10]首次提出 $( \rho _ { 1 } , \rho _ { 2 } )$ -隐私模型的概念，它的定义为：当随机变量 $X$ 的值 $x$ 的先验概率 $\operatorname* { P r } \left[ X = x \right] \leq \rho _ { \mathrm { { } _ { l } } }$ 时，通过隐私策略 $M$ 得到扰乱结果 $R \in R a n g e ( M _ { \mathrm { \Gamma } } ( D ) )$ 后， $x$ 的后验概率更新为$\operatorname* { P r } [ X = x \mid M _ { _ { f } } \left( D \right) = R ] \leq \rho _ { _ { 2 } }$ ，则称 $x$ 满足 $( \rho _ { 1 } , \rho _ { 2 } )$ -隐私模型约束。其中， $0 < \rho _ { { } _ { 1 } } < \rho _ { { } _ { 2 } } < 1$ 并且 $\operatorname* { P r } [ M _ { \mathit { f } } \left( D \right) = R ] > 0$ 。从定义上看， $( \rho _ { 1 } ,$ $\rho _ { 2 } )$ -隐私模型并不依赖于先验概率，它意味着先验概率不超过 $\rho _ { 1 }$ 则后验概率必须小于 $\rho _ { 2 } , \rho _ { 1 }$ 与 $\rho _ { 2 }$ 可以自定义不依赖于任何背景知识。

# 2.2攻击模型

假设攻击者的背景知识包含所有可能的值 $U$ 以及数据库$D$ 中除了第 $n$ 个元组以外其他所有元组的信息，也就是 $D ^ { \prime }$ 。另外攻击者还知道隐私机制 $M$ 的所有细节以及添加噪声所服从的概率密度函数。攻击者为了推断第 $n$ 个元组的值，在得到隐私机制 $M$ 返回的结果前攻击者以相等的概率 $1 / U$ 猜测 $U$ 中所有的值都有可能为第 $n$ 个元组的值，用户提交查询 $f$ 给隐私机制 $M$ ，得到扰乱的结果为： $R { = } M _ { f } ( D )$ ，则攻击者猜测第 $n$ 个元组的值为 $i$ 的概率为

$$
\operatorname* { P r } \left[ \Pi { \big ( } D { \big ) } = O \right] \leq e ^ { \varepsilon } \operatorname* { P r } \left[ \Pi { \big ( } D ^ { \prime } { \big ) } = O \right]
$$

$$
\Gamma \left( i \right) = { \mathrm { P r } } \left[ w = D \big | M _ { { \mathrm { \Gamma } } _ { f } } \left( D \right) = R \right]
$$

如果 $\Gamma ( i ) > \rho _ { _ 2 }$ ，则隐私泄露了。

# 2.3攻击模型举例

下面通过一个例子描述上述攻击模型的过程，尽管查询机制 $M$ 满足差分隐私约束，但攻击者依然可以以很高的后验概率猜测个体的值。令 $f$ 为求平均值的查询函数，给定数据集$D = \{ 1 , 2 , 3 , 1 0 \}$ ， $D$ 中的值都来自 $U = \left\{ 1 , 2 , 3 , 5 , 1 0 \right\}$ ，假设攻击者已经知道 ${ \cal D } ^ { \prime } = \left\{ 1 , 2 , 3 \right\}$ ，想推断第4个值，由于第4个值可能为1,2,3,5,10，得知 $f$ 的敏感度为： $1 6 / 4 - 7 / 4 = 9 / 4$ 。设差分隐私参数 $\varepsilon = 2$ ，且攻击者提交一个求平均值的请求后得到的返回值为：$R = 5 . 0 4 1$ ，缺失的值为 $U$ 中的其中一个，攻击者计算后验概率$\operatorname* { P r } [ X = x \mid M _ { \mathit { \Pi } _ { f } } \left( D \right) = R ]$ ，如表1所示。

表1攻击者的猜测值  

<html><body><table><tr><td rowspan="2">猜测值</td><td rowspan="2">猜测 数据集</td><td rowspan="2">真实 均值</td><td rowspan="2">添加 噪声</td><td rowspan="2">Pr[M(Di)]=5.401</td></tr><tr><td>后验 概率</td></tr><tr><td>1</td><td>1,2,3,1</td><td>7/4</td><td>3.291</td><td>0.0238</td><td>0.0751</td></tr><tr><td>2</td><td>1,2,3,2</td><td>8/4</td><td>3.401</td><td>0.0216</td><td>0.0682</td></tr><tr><td>3</td><td>1,2,3,3</td><td>9/4</td><td>2.791</td><td>0.0372</td><td>0.1174</td></tr><tr><td>5</td><td>1,2,3,5</td><td>11/4</td><td>2.291</td><td>0.0580</td><td>0.1831</td></tr><tr><td>10</td><td>1,2,3,10</td><td>16/4</td><td>1.041</td><td>0.1762</td><td>0.5562</td></tr></table></body></html>

以可能的值10为例给出后验概率的计算过程。

$$
\begin{array} { r l } & { \mathrm { P r } \Big [ X = 1 0 \Big | M _ { \mathrm { \prime } } \big ( D _ { i } \big ) = 5 . 4 0 1 \Big ] } \\ & { = \frac { \mathrm { P r } \big [ X = 1 0 \big ] \cdot \mathrm { P r } \big [ M _ { \mathrm { \prime } } \big ( D _ { i } \big ) = 5 . 4 0 1 \big | X = 1 0 \big ] } { \underset { i \neq U } { \sum } \mathrm { P r } \big [ X = i \big ] \cdot \mathrm { P r } \big [ M _ { \mathrm { \prime } } \big ( D _ { i } \big ) = 5 . 4 0 1 \big ] } } \\ & { = \frac { \mathrm { P r } \big [ X = 1 0 \big ] \cdot \mathrm { P r } \big [ M _ { \mathrm { \prime } } \big ( D _ { \mathrm { \scriptscriptstyle { 0 } } } \big ) = 5 . 4 0 1 \big ] } { \underset { i \neq U } { \sum } \mathrm { P r } \big [ X = i \big ] \cdot \mathrm { P r } \big [ M _ { \mathrm { \prime } } \big ( D _ { i } \big ) = 5 . 4 0 1 \big ] } } \end{array}
$$

其中： $D _ { i } = \left\{ D ^ { \prime } \cup i \right\}$ 。首先基于返回的值5.401，计算概率$\mathrm { P r } \big [ M _ { \mathrm { \Lambda ^ { \it f } } } \big ( D _ { \mathrm { \Lambda ^ { \mathrm { 1 0 } } } } \big ) = 5 . 4 0 1 \big ]$ ，因为 $m e a n \big ( D _ { \scriptscriptstyle { 1 0 } } \big ) = 4$ ，差分隐私机制 $M$ 给真实值添加的噪声量为： $R - m e a n \big ( D _ { _ { 1 0 } } \big ) = 1 . 0 4 1$ ，可以求出$\lambda = \frac { \Delta } { \varepsilon } = \frac { 9 } { 8 } = 1 . 1 2 5$ =1.125，则

$$
\begin{array} { l } { { \displaystyle \operatorname* { P r } \Bigl [ M _ { f } \left( D _ { _ { 1 0 } } \right) = 5 . 4 0 1 \Bigr ] } } \\ { { \displaystyle = \frac { 1 } { 2 \cdot 1 . 1 2 5 } \cdot e ^ { \frac { - \frac { \left| 1 . 0 4 1 \right| } { 1 . 1 2 5 } } { 1 . 1 2 5 } } } } \\ { { \displaystyle = 0 . 1 7 6 2 } } \end{array}
$$

假设 $U$ 中值的先验概率为 $\rho _ { { } _ { 1 } } = 0 . 2$ ，则

$$
\begin{array} { l } { { \displaystyle \operatorname* { P r } \Big [ X = 1 0 \Big | M _ { \rho } \left( D _ { i } \right) = 5 . 4 0 1 \Big ] } } \\ { { \displaystyle = \frac { \operatorname* { P r } \Big [ M _ { \rho } \left( D _ { \mathrm { { \scriptscriptstyle 0 } } } \right) = 5 . 4 0 1 \Big ] } { \sum _ { i \in U } \operatorname* { P r } \Big [ M _ { \rho } \left( D _ { i } \right) = 5 . 4 0 1 \Big ] } } } \\ { { \displaystyle = 0 . 5 5 6 2 } } \end{array}
$$

如果 $\rho _ { { } _ { 2 } } = 0 . 5$ ，则差分隐私机制 $M$ 不满足 $\left( \rho _ { _ 1 } , \rho _ { _ 2 } \right)$ -隐私约束。

# 2.4LPBDP 的设计与实现

本文基于 $\left( \rho _ { { } _ { 1 } } , \rho _ { { } _ { 2 } } \right)$ -隐私模型提出的隐私参数设置策略LPBDP(limit privacy breaches in differential privacy)的基本思想是设置隐私参数 $\boldsymbol { \varepsilon }$ 使得差分隐私机制满足 $\left( \rho _ { { } _ { 1 } } , \rho _ { { } _ { 2 } } \right)$ -隐私约束,找出差分隐私参数 $\boldsymbol { \varepsilon }$ 与 $\left( \rho _ { { } _ { 1 } } , \rho _ { { } _ { 2 } } \right)$ 之间的关系，使得 $\varepsilon$ 的设置不再依赖于经验或实验，而是可以根据 $\left( \rho _ { _ 1 } , \rho _ { _ 2 } \right)$ 进行启发式设置。

为满足 $\left( \rho _ { { } _ { 1 } } , \rho _ { { } _ { 2 } } \right)$ -隐私约束，文献[10]提出一种增幅(amplification)方法。该方法的定义如下：隐私机制 $M$ 对于所有的结果 $R \in M _ { \mathit { f } } \left( D \right)$ 最多是 $\gamma$ -增幅的，如果式(7)成立：

$$
\forall D _ { i } , D _ { j } : \frac { \mathrm { P r } \big [ D _ { i }  R \big ] } { \mathrm { P r } \big [ D _ { j }  R \big ] } \leq \gamma
$$

其中： $\gamma \geq 1$ ， $D _ { i } = \left\{ D ^ { \prime } \cup i { \left| i \in U \right. } \right\} , D _ { j } = \left\{ D ^ { \prime } \cup j { \left| j \in U \right. } \right\} \circ$

如果隐私机制 $M$ 返回的结果是 $R$ ，那么任意一个数据集D={D'Uili∈U}都有可能返回R。因此，基于拉普拉斯机制得到如下等式：

$$
\begin{array} { l } { \displaystyle \frac { p \big [ D _ { i }  R \big ] } { p \big [ D _ { j }  R \big ] } = \frac { \displaystyle \frac { 1 } { 2 \lambda } \cdot e ^ { \frac { \big | R - f ( D _ { i } ) \big | } { \lambda } } } { \displaystyle \frac { 1 } { 2 \lambda } \cdot e ^ { \frac { \big | R - f ( D _ { j } ) \big | } { \lambda } } } } \\ { = e ^ { \frac { \big | R - f ( D _ { j } ) \big | - | R - f ( D _ { i } ) | } { \lambda } } } \end{array}
$$

因为 $\left| f \big ( D _ { i } \big ) - f \big ( D _ { j } \big ) \right| \leq \Delta$ ，应用三角不等式得到

$$
{ \frac { p \big [ { D _ { i } \to R } \big ] } { p \big [ { D _ { j } \to R } \big ] } } \leq e ^ { \frac { \big | f \left( { D _ { i } } \right) - f \left( { D _ { j } } \right) \big | } { \lambda } } \leq e ^ { \frac { \Delta } { \lambda } }
$$

下面的定理[10]给出了 $\gamma$ -增幅与 $\left( \rho _ { { } _ { 1 } } , \rho _ { { } _ { 2 } } \right)$ -隐私模型之间的关系。

定理1如果 $\varepsilon$ -差分隐私机制 $M$ 对于所有的响应值 $R$ 都满足 $\gamma$ -增幅，其中 $\gamma \leq \frac { \rho _ { _ 2 } } { \rho _ { _ 1 } } \cdot \frac { 1 - \rho _ { _ 1 } } { 1 - \rho _ { _ 2 } }$ 则 $M$ 必定满足 $\left( \rho _ { _ 1 } , \rho _ { _ 2 } \right)$ -隐私约束。

基于定理1，可以找出差分隐私参数 $\boldsymbol { \varepsilon }$ 与 $\left( \rho _ { { } _ { 1 } } , \rho _ { { } _ { 2 } } \right)$ 之间的关系。根据式(9)得到：

$$
\frac { p \big [ D _ { i }  R \big ] } { p \big [ D _ { j }  R \big ] } { \leq e ^ { \frac { \Delta } { \lambda } } \leq \gamma \leq \frac { \rho _ { _ { 2 } } } { \rho _ { _ { 1 } } } \cdot \frac { 1 - \rho _ { _ { 1 } } } { 1 - \rho _ { _ { 2 } } } }
$$

因为 $0 < \rho _ { { } _ { 1 } } < \rho _ { { } _ { 2 } } < 1$ ，两边同时取自然对数得到

$$
{ \frac { \Delta } { \lambda } } \leq \ln \left( { \frac { \rho _ { _ { 2 } } } { \rho _ { _ { 1 } } } } \cdot { \frac { 1 - \rho _ { _ { 1 } } } { 1 - \rho _ { _ { 2 } } } } \right)
$$

$$
\lambda \geq \frac { \Delta } { \ln \left( \displaystyle \frac { \rho _ { _ 2 } } { \rho _ { _ 1 } } \cdot \frac { 1 - \rho _ { _ 1 } } { 1 - \rho _ { _ 2 } } \right) }
$$

由此得到一个重要的结果，对于任意的攻击者，如果设置差分隐私参数 $\varepsilon = \ln \left( \frac { \rho _ { _ { 2 } } } { \rho _ { _ { 1 } } } \cdot \frac { 1 - \rho _ { _ { 1 } } } { 1 - \rho _ { _ { 2 } } } \right)$ ，则拉普拉斯分布的参数：

$$
\lambda = \Delta \Bigg / \ln \left( \frac { \rho _ { _ { 2 } } } { \rho _ { _ { 1 } } } \cdot \frac { 1 - \rho _ { _ { 1 } } } { 1 - \rho _ { _ { 2 } } } \right)
$$

那么差分隐私机制 $M$ 满足 $\left( \rho _ { _ 1 } , \rho _ { _ 2 } \right)$ -隐私约束。又由于拉普拉斯分布要求 $\lambda > 0$ ，则有

$$
\ln \left( \frac { \rho _ { _ 2 } } { \rho _ { _ 1 } } { \cdot } \frac { 1 - \rho _ { _ 1 } } { 1 - \rho _ { _ 2 } } \right) > 0
$$

$$
\frac { \rho _ { _ 2 } } { \rho _ { _ 1 } } \cdot \frac { 1 - \rho _ { _ 1 } } { 1 - \rho _ { _ 2 } } > 1
$$

最后得到： $\rho _ { 2 } > \rho _ { I }$ ，意味着保护数据库中个体的隐私的后验概率 $\rho _ { { } _ { 2 } }$ 必须超过它的先验概率 $\rho _ { _ { 1 } }$ ，否则没有任何意义。这个结论显然是符合实际的，如果对个体实施隐私保护的概率不能超过它的先验概率，那就失去了保护的意义。

注意到，如果设置 $\rho _ { _ 1 } = 1 / m$ ，其中 $m = \left| { U } \right|$ ，就能得到：

$$
\lambda \geq \Delta { \Bigg / } \ln \frac { { \big ( } m - 1 { \big ) } \rho _ { _ { 2 } } } { 1 - \rho _ { _ { 2 } } }
$$

意味着 $\rho$ -差分可识别只是本文提出方法LPBDP的一个特例。

# 3 实验结果与分析

本节首先对比LPBDP与 $\rho$ -差分可识别的区别与联系，如表2所示；其次通过实验分析了LPBDP的启发性和语义性。

一方面，从表2中可以看出，本文提出的LPBDP方法同样满足差分隐私要求，且比 $\rho$ -差分可识别在先验知识上更有优势，LPBDP基本上不需要假设任何先验知识，具有更好的适应性

表2LPBDP与 $\rho$ -差分可识别的区别与联系  

<html><body><table><tr><td rowspan="2"></td><td colspan="2">区别</td><td colspan="2">联系</td></tr><tr><td>攻击模型</td><td>先验知识</td><td>差分隐私</td><td>关联</td></tr><tr><td>LPBDP</td><td>先验概率大于pi 后验概率小于p2</td><td>p(根据实际需求自定义设置)</td><td>满足</td><td></td></tr><tr><td>p-差分 可识别</td><td>后验概率小于p</td><td>数据集U 中存在的每个值; 数据集U 的大小|U|; 每个值先验概率相等且都为随机猜测</td><td>满足</td><td>当ρ=1/m，其中m=U|时，p-差分可识别为LPBDP 的特例</td></tr></table></body></html>

另一方面，通过实验分析LPBDP 的实际应用，为了与 $\rho$ 1差分可识别进行比较，实验中采用同样的聚集查询函数，即求平均值：mean，实验数据为来自UCI的Adult 数据库，包含48.842条记录，共有14个属性，其中9个分类属性，5个数值型属性。在本文中只用到其中3个数值型属性。表3描述了Adult数据库的特点。

表3Adult 数据库  

<html><body><table><tr><td>属性</td><td>最大值</td><td>最小值</td><td>敏感度</td><td>随机猜测概率</td></tr><tr><td>age(AG)</td><td>90</td><td>17</td><td>0.0015</td><td>0.0137</td></tr><tr><td>education-num(EN)</td><td>16</td><td>1</td><td>0.0031</td><td>0.0101</td></tr><tr><td>hourse-per-week(HW)</td><td>99</td><td>1</td><td>0.0020</td><td>0.0625</td></tr></table></body></html>

为了决定所添加噪声的拉普拉斯分布函数，必须求平均值函数的敏感度： $\Delta f$ 。例如，假设攻击者知道数据库中除一条记录外其他所有记录的年龄，那么攻击猜测值的范围为 $1 { \sim } 9 9$ 。所以，函数的敏感度为

$$
\Delta f = \left| f \left( D _ { \mathrm { { \% } } } \right) - f \left( D _ { \mathrm { { \scriptscriptstyle 1 7 } } } \right) \right| = \frac { 9 0 - 1 7 } { 4 8 8 4 2 } = 0 . 0 0 1 5
$$

攻击者随机猜测的概率为 $1 / | U |$ ，如表3中RG（randomguess）所示。

LPBDP表明，噪声添加量不仅受先验概率影响，也受后验概率影响。本文首先通过实验验证了添加的噪声量受先验概率影响的情况，设置后验概率为： $\rho _ { { } _ { 2 } } = 5 0 \%$ 。要求差分隐私机制满足 $\left( \rho _ { _ 1 } , 0 . 5 \right)$ -隐私要求，其中 $\rho _ { _ 1 } { = } 1 \% \Lambda 1 0 \%$ 。如图1所示，噪声添加量 $( \lambda )$ 随着先验概率的增大而增大。意味着 $\rho _ { { } _ { 2 } } - \rho _ { { } _ { 1 } }$ 越小，所需的噪声量越多。 $\rho$ -差分可识别中将所有值的先验概率都设置为随机猜测概率 $1 / | U |$ ，对于有的先验概率大于随机猜测概率的值，所添加的噪声量不能满足 $\left( \rho _ { _ 1 } , \rho _ { _ 2 } \right)$ -隐私模型约束。

![](images/fe5447f3303188cd1689072b0a5e87976594ebc24a059c927def3ec284f3552c.jpg)  
图1先验概率对噪声添加量的影响

为了验证LPBDP的实用性，对4个属性分别提交了1000次求平均值的查询请求,图2\~4给出了 $\rho _ { { } _ { 1 } } , \rho _ { { } _ { 2 } }$ 对噪声率的影响，噪声率的计算为

$$
\mathrm { N o i s e r a t i o } \big ( \mathrm { N R } \big ) \ = \frac { R - f \big ( D \big ) } { U _ { \mathit { r a n g e } } }
$$

其中 $R$ 为扰乱后的查询结果， $U _ { _ { r a n g e } } = \operatorname* { m a x } - \operatorname* { m i n }$ 是每个属性域上值的区间。Q1为第一个四分位数，Q3为第3四分位数，Q3-Q1为分位数极差。图3\~4表明，所有的响应值都集中在真实值的附近。当固定 $\rho _ { _ { 1 } }$ 时，增大 $\rho _ { { } _ { 2 } }$ ，需要更多的噪声以满足 $\left( \rho _ { { } _ { 1 } } , \rho _ { { } _ { 2 } } \right)$ 1隐私约束，这与 $\rho$ -差分可识别是相同的。当固定 $\rho _ { { } _ { 2 } } = 0 . 2$ ，从图3、4中可以看出（从左至右)，当 $\rho _ { _ { 1 } }$ 增大时， $\lambda$ 随之变大，因此所需要的噪声也增多。

![](images/966b09d75218a2ef42e1323168aeb044a8eafd4080bc18834d8510237e6f917e.jpg)  
图2Age 的噪声率

![](images/8f3ab56cb396e450bd85a9d8d4ed844dcc9376118bf4f7ce4215d4e5afb98b70.jpg)  
图3Hours-per-week 的噪声率

图5研究了隐私参数 $\boldsymbol { \varepsilon }$ 对差分隐私的影响。图5表明LPBDP能达到 $\boldsymbol { \varepsilon }$ -差分隐私一样的效果。但是对于 $\boldsymbol { \varepsilon }$ -差分隐私而言，如何设置 $\boldsymbol { \varepsilon }$ 是个大问题，大多通过经验或实验设置。而LPBDP 设置隐私参数具有更好的语义，必须满足 $\left( \rho _ { _ 1 } , \rho _ { _ 2 } \right)$ -隐私约束。

# 4 结束语

针对差分模型中的隐私参数设置问题，以往的设置方法主要基于实验或相关专家的经验，本文提出了一种启发式的差分隐私参数设置策略。 $\rho$ -差分可识别是另一种差分隐私参数的设置策略，然而该方法依赖于如下两个假设：(1）知道每个值的先验概率，并假设预先知道所有可能的值 $U$ 以及 $| U |$ ；(2）所有可能值的先验概率都是相等的。然而，部分应用场景无法满足上述两个假设条件，本文提出的方法弥补了这一缺陷，基于(p,p)-隐私模型提出一种新的隐私参数设置策略LPBDP，该策略的优势在于 $\left( \rho _ { { } _ { 1 } } , \rho _ { { } _ { 2 } } \right)$ -隐私模型并不依赖于先验概率且不需要知道 $| U |$ ，且LPBDP同样满足差分隐私约束。

![](images/fc88b18b5137f9fb82d76069da9a28da7767408046332899bbf642d596cb58dc.jpg)  
图4Education Number 的噪声率  
图5差分隐私的噪声率

0.0004   
0.0003   
O 0.0002 0.0001 米杀杀素 × XI   
-0.0001   
-0.0002 \*   
-0.0003   
-0.0004 10.135 9.503 4.669 2.582 1.325 0.502 0.0123 £ (a) Age   
0.0004   
0.0003   
0.0002   
G 杀杀   
-0.0002   
-0.0003   
-0.0004 8.213 7.615 4.669 2.582 1.325 0.902 0.0631 £ (b) Hours-per-week   
0.0004   
0.0003   
0.0002 杀杀   
-0.0002 ?   
-0.0003   
-0.0004 11.513 6.805 4.669 2.582 1.325 0.502 0.0123 ε (c)Education Number

# 参考文献：

[1]欧阳佳，印鉴，刘少鹏．一种有效的差分隐私事务数据发布策略[J].计算机研究与发展,2014,51(10):2195-2205.  
[2]欧阳佳，印鉴，刘少鹏．一种分布式事务数据的差分隐私发布策略[J].

软件学报,2015,26(6):1457-1472.

[3] Goethals B,Laur S,Lipmaa H,et al. On private scalar product computation for privacy-preserving data mining $[ \mathrm { C } ] / \hbar$ Proc of the 7th International Conference on Information Security and Cryptology.2004:104-120.   
[4]Aggarwal C C,Philip S Y.A general survey of privacy-preserving data mining models and algorithms [M].[S.1.] : Springer,2008.   
[5]Dwork C,McSherry F,Nissim K,et al. Calibrating noise to sensitivity in private data analysis [C]// Proc of the 3rd Conference on Theory of Cryptography Theory of Cryptography.2006: 265-284.   
[6]Dwork C.Differential privacy [C]// Proc of International Colloquium on Automata,Languages and Programming.20o6:1-12.   
[7]Dwork C.Diferential privacy in new setings [C]// Proc of the 21st Annual ACM-SIAM Symposium on Discrete Algorithms.Society for Industrial and Applied Mathematics.2010:174-183.   
[8]Dwork C.Differential privacy:a survey of results [C]// Proc of the 5th Conference on Theory and Applications of Models of Computation.2008: 1-19.   
[9]Lee J,Clifton C.Differential identifiability[C]// Proc of the 18th ACM SIGKDD International Conference on Knowledge Discovery and Data mining.[S.1.]:ACM Press,2012.1041-1049.   
[10] Evfimievski A, Gehrke J, Srikant R.Limiting privacy breaches in privacy preserving data mining [C]// Proc of the 22nd ACM SIGMOD-SIGACTSIGART Symposium on Principles of Database Systems.[S.l.] :ACM Press,2003: 211-222.   
[11] Sweeney L. k-anonymity: a model for protecting privacy [J]. International Journal of Uncertainty Fuzziness and Knowledge Based Systems.2002,10 (5): 557-570.   
[12][Machanavajjhala A,KiferD,Gehrke J,etal.l-diversity: Privacy beyond $\mathbf { k }$ 1 anonymity[J].ACM Trans on Knowledge Discovery from Data,2007,1(1): 1-12.