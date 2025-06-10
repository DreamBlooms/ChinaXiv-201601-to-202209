# 基于主动信息存储的驾驶员头动行为和驾驶方向平稳度的量化研究在VR驾驶中

王文傲' 彭喆 徐庆1,\*1（天津大学大学智能与计算学部 天津 300350）

摘要：主动信息存储是重要/\*逐渐流行\*/的信息论工具，其优点在于易于获取复杂在系统中的可解释的信息存储。驾驶员的头动行为对于其把控方向具有重要作用，然而这种作用没有得到量化的衡量与解释。在本文中，我们将主动信息存储应用在驾驶员头动研究上，研究其与驾驶方向平稳度的关系。具体而言，我们设计了/\*包含直道和转弯的\*/VR 驾驶实验，获取驾驶员头动主动信息存储序列和车辆偏转角序列，并研究二者的量化关系。我们证明了二者具有高度的时序相关性，并且用二者的联合熵作为驾驶表现的一种指标，最后我们用驾驶员的头动实时预测车辆偏转角，得到了 $8 8 . 5 6 \%$ 的准确率。该工作有望帮助监测驾驶员状态，提高驾驶安全性。

# Quantitative study of driver' s head movement behavior and driving direction stability based on active information

# storage is studied in VR driving

Wang Wenao' Peng Zhe1Xu Qing1, 1(College of Intelligence and Computing， Tianjin University， Tianjin 300350, China)

Abstract: Active information storage is an important /\*growing popularity\*/ information theoretic tool， which has the advantage of being an easily accessible and interpretable store of information that is complex in the system. Driver head movement behaviour plays an important role in their directional control, yet this role has not been measured and explained quantitatively. In this paper, we apply active information storage to the study of driver head movements to investigate their relationship with driving directional smoothness. Specifically, we design a $\ast / \mathrm { V R }$ driving experiment with /\*containing straight and turning directions， obtain a sequence of active driver head movement information storage and a sequence of vehicle deflection angles,and investigate the quantitative relationship between the two.We demonstrate a high temporal correlation between the two and use the joint entropy of the two as an indicator of driving performance. Finally，we use driver head movements to predict vehicle deflection angles in real time and obtain an accuracy of $8 8 . 5 6 \%$ .This work is expected to help monitor driver state and improve driving safety.

# 1．介绍

驾驶员头动在驾驶中发挥着巨大的作用。具体而言，驾驶员用眼睛观察外界环境，然而眼球运转的范围有一定的限制，超过某个角度时就需要头部运动的帮助，以扩大人的视野[8-9，16」。有研究证明，头眼运动的协调性可以作为驾驶表现的一种衡量[10」。最简单的例子就是车辆转弯，在转弯前司机总是要先转头，观察没有危险后再打方向盘转弯，这样才能确保安全。这样来看，头动对于驾驶员保持方向平稳度具有重要意义一一驾驶员很难在头乱动时保持直行，也很难在头不动时顺利转弯。而且，头动对于驾驶方向具有预测作用，头动模式也能反映出驾驶员的驾驶状态。如Doshi等人[4]提出，相比眼睛运动，头部转动可以更早地体现驾驶人的转向意图；J．McCal1等人[12]构建一种基于车辆横向位置、车辆运行参数和驾驶人头部运动的车道变换意图识别系统DIIS，LiuT等人[11]融合驾驶人眼动及头动特征，通过半监督学习方法训练了认知分心识别模型。另外，头动数据容易采集，已有多种基于视觉的方法计算头部姿态[13-15]，只需要摄像头即可实现，研究成果易于推广。

算法方面，不少研究者使用神经网络来进行预测（变道[12、17、19]、路口时行为[16][20]）或分类（驾驶员是否专心[11]、驾驶行为特征[18]）。神经网络的优点是准确率高，但其主要缺点是缺乏可解释性，很难揭示驾驶员认知、行为的本质特征。为了克服该缺点，一些研究者使用信息论的工具进行建模研究，使结果具有可解释性［24,25]。我们follow 这个思路，使用LAIS[2]进行头动数据建模及分析。其优点是，LAIS本身是可预测性的度量，将其用于头动，可以得到头动稳定性的度量，这与驾驶方向平稳性有着天然的对应关系，有利于挖掘二者的量化关系。并且，我们可以计算出每个时刻的LAIS取值，其具有直接的物理含义一一即当前头动状态是否稳定一一这大大提升了计算结果的可解释性。

目前对于驾驶的行为研究，主要集中于头眼协调性[26-27]，据我们所知，没有工作单独研究头动和驾驶方向平稳性间的量化关系，但这对于驾驶安全与舒适具有重要意义；目前对于LAIS的使用较为局限，仅仅将LAIS当做一种被分析事物的指标做分析适用，没有找到较好的应用方式。为了填补这些空白，本文基于LAIS研究驾驶中的头动行为，深入探索驾驶员头动与驾驶方向平稳度之间的量化关系，同时挖掘LAIS的更多应用出口。本文的核心贡献如下：

（1）提出了HM-LAIS。它由水平头动角算出，但比后者好在数据自适应性更强，不关心角度的具体取值而关心取值所代表的状态。  
(2） 证明了头动角和汽车偏转角具有相关性。  
(3） 提出了使用HM-LAIS与偏转角的联合熵量化驾驶的方向稳定性。  
（(4） 实现了用头动角实时预测汽车偏转角，准确率达 $8 8 . 5 6 \%$ 。

# 2.相关工作

香农在信息论领域提出了熵的概念，即与选择相关的平均信息或不确定性[1]。它被定义为：

$$
\begin{array} { r } { H ( X ) = - \sum _ { x \in \mathbb { X } } p ( x ) l o g p ( x ) } \end{array}
$$

这里,H(X）代表了熵的值,单位是 bits(当使用 log 的底为 2 时）或者nats(当时用自然对数时)，X 是包含随机变量X所有可能事件的集合，x是一个个体事件。p(x)是每一种事件发生的概率.

如果有两个随机变量X和Y，我们可以使用联合熵，它量化了它们联合分布的不确定性。计算方法如下：

$$
\begin{array} { r } { H ( X , Y ) = - \sum _ { x \in \mathbb { X } } \sum _ { y \in \mathbb { Y } } p ( x , y ) l o g p ( x , y ) } \end{array}
$$

如果一个随机变量依赖于另一个随机变量，那么我们使用条件熵来量化当已知x时，关于 $\mathrm { \Delta y }$ 的平均不确定性。它由下式定义：

$$
\begin{array} { r } { \mathrm { H } ( \mathrm { Y } | \mathrm { X } ) = - \sum _ { x \in X } \sum _ { y \in Y } p ( x , y ) l o g p ( y | x ) } \end{array}
$$

我们可能还想知道X和Y之间共享信息的量。那么我们可以使用互信息。它是对它们的统计依赖性的度量，由下式给出：

$$
\operatorname { I } ( \mathrm { X } ; \mathrm { Y } ) = \operatorname { H } ( \mathrm { X } ) + \operatorname { H } ( \mathrm { Y } ) - \operatorname { H } ( \mathrm { X } , \mathrm { Y } )
$$

我们还可以根据概率计算互信息，如下所示：

$$
\begin{array} { r } { \mathrm { I } ( \mathrm { X } { : } \mathrm { Y } ) = \sum _ { x \in \Omega _ { x } , y \in \Omega _ { y } } p ( x , y ) l o g _ { 2 } \frac { p ( x , y ) } { p ( x ) p ( y ) } } \end{array}
$$

现在我们可以引入主动信息存储（AIS）的概念［2]。它是一种特殊的互信息。对于一个时间序列，AIS 量化了下一时刻可以从其最近的过去获得多少信息，也可以看作是进程过去状态所包含的可预测性。AIS计算如下：

$$
\begin{array} { r l } { \mathrm { A I S } ( X _ { t } ) = \mathrm { I } ( X _ { t - 1 } ^ { - } ; X _ { t } ) } \\ { = \mathrm { H } ( X _ { t } ) - \mathrm { H } ( X _ { t } | X _ { t - 1 } ^ { - } ) = \mathrm { H } ( X _ { t - 1 } ^ { - } ) - \mathrm { H } ( X _ { t - 1 } ^ { - } | X _ { t } ) } \\ { = \mathrm { H } ( X _ { t } , X _ { t - 1 } ^ { - } ) - \mathrm { H } ( X _ { t } | X _ { t - 1 } ^ { - } ) - \mathrm { H } ( X _ { t - 1 } ^ { - } | X _ { t } ) } \\ { = \displaystyle \sum _ { x _ { t } , x _ { t - 1 } ^ { - } } p ( x _ { t } , \mathbf { x } _ { t - 1 } ^ { - } ) l o g \frac { p ( x _ { t } | \mathbf { x } _ { t - 1 } ^ { - } ) } { p ( x _ { t } ) } } \end{array}
$$

这里， $X _ { t - 1 } ^ { - }$ 是该过程中过去状态的抽象．具体来说，我们从过去的变量集中选择一些变量 $\left\{ \begin{array} { l } { { \boldsymbol { X } } _ { t - 1 } ^ { - } } \end{array} \right.$ 。．.， $X _ { t - t _ { 1 } } ^ { - }$ ；...； $X _ { t - l _ { m a x } } ^ { - } \}$ ，我们不会给出选择方法的细节，你可以在[2]中找到详细信息。Xt 是下一个变量。

然后可以推导出本地主动主动信息存储的概念。它是AIS 的本地变体，测量过去状态的特定实现，提供有关特定下一个状态的信息.：

$$
\begin{array} { r } { \mathrm { L A I S } ( x _ { t } , k ) = l o g _ { 2 } \frac { p ( x _ { t - 1 } ^ { ( k ) } , x _ { t } ) } { p ( x _ { t - 1 } ^ { ( k ) } ) p ( x _ { t } ) } } \end{array}
$$

这代表了长度为 $\mathrm { ~ k ~ }$ 的历史序列对 $\mathrm { \Omega } _ { \mathrm { t } }$ 时刻的本地主动信息存储。

# 3.实验

# 3.0任务

在本文中，我们设计了一个VR 驾驶实验．我们使用Unity[30]搭建了VR 驾驶场景。它像郊区公路。然后我们邀请志愿者参加我们的实验。实验的要求是： (1)驾驶员必须尽力使车速保持 $4 0 \mathrm { { k m / h } }$ ．（2）驾驶员必须尽力沿快车道平稳驾驶。

3.1参与者

我们邀请了30 名天津大学的学生参加我们的实验。其中包含16 男 14女，年龄均值21.91岁，标准差1.54岁；驾龄均值1.04年，标准差1.15年。他们均色觉正常，视力正常或矫正正常，拥有驾驶经验，不晕3D和VR，符合实验条件。所有参与者在参与实验前均给予口头知情同意，我们给予了参与者一定

的现金补贴。

3.2装置

我们使用了HTCVive头戴VR 显示器，来显示VR驾驶场景，其中搭载了惯性传感器，实时记录了头动数据（俯仰角和摇摆角）。LogitechG29 驾驶套件包含方向盘和脚踏板，我们用来实现仿真自动挡驾驶，驾驶员操作设备的数据（方向盘转向，油门刹车力度）将被实时记录并用以分析。以上所有时序信号将在滤波后使用。实验过程中使用桌面显示器观察被试的头动和驾驶行为。

# 3.3虚拟现实场景

我们使用Unity搭建了实验所需的驾驶环境。场景仿照郊区公路设计，具有道路、斑马线、树、路灯等基础交通元素。出于我们实验设计目的，场景不能过于复杂以增加视觉干扰，因此没有设置建筑物、行人、其他车辆等元素。道路为来往方向各两车道，共四车道，驾驶员被要求保持在前进方向的快车道上行驶。整个行驶路线共9条直道8个拐弯。

我们使用UnityCar 插件来仿真驾驶员驾驶的车辆。其具有左、右、后视镜，仪表盘上显示当前档位和车速。驾驶员可以通过方向盘和踏板直接控制车辆行驶。

# 3.4实验流程

(1）实验前谈话：告知参与者本实验的目的和要求。要求包括：（a）车速尽量保持 $\mathrm { 4 0 k m / h }$ 匀速行驶（b）尽量保持水平方向的平稳度，除拐弯外尽量沿直线行驶。

（2）练习阶段：这个阶段，参与者在场景中自由驾驶，我们不设置任何任务，目的是让参与者熟悉场景和设备，此阶段约5-8分钟时间，当参与者提出已熟练掌握后，即可结束该阶段。同时我们会在一旁观察，确保参与者熟练保持车速、平滑转弯。

（3）正式实验：驾驶员将按照指定路线完成驾驶，路线将由语音提示，类似于现实中的语音导航。从起点到终点是一轮实验，每位参与者要完成两轮实验，两轮间有一分钟闭眼休息。

（4）实验后访谈：询问参与者驾驶的主观感受，试图通过这种方式了解驾驶中的行为机制，如：“为什么有一个弯转的特别急，你是如何补救的？”。另外询问我们仿真实验的沉浸感和逼真度（得到了较高的评价，证明了实验的可行性和数据的可用性）。

图1展示了实际实验时的效果图。

![](images/224df9bb3cb07e0510e03b3a76deaf588f287fbb0f4e71c8dd8b53dd50b215d4.jpg)  
图1志愿者进行实验

# 4．结果

# 4.0水平头动特性

我们分别计算了30个驾驶员在直道和拐弯时的头水平转动角度的标准差，结果如图2所示。由该图可以直观看出，驾驶员在转弯时的头动标准差远大于在直道时的，该结论通过了ANOVA分析（F（1,58） $= 8 2 . 4 6 \$ ， $\mathbf { p } { \langle 0 . 0 1 }$ ）。证明了转弯时，司机需要较大幅度转动头以观察交通情况，然后进行转弯，这为我们量化研究水平头动角和汽车偏转角间的关系奠定了依据。

![](images/ace23950380728ca3bf6b398336e0f9703a3f3a4f68bf7d71b08d2f5b0b4ba47.jpg)  
图230位驾驶员在直行和路口转弯时的水平转动角折线图（左）及箱型图（右）

# 4.1HM-LAIS

头动角可以分为pitch、yaw 和roll。根据前人工作[12]及上小节的证明，只有 yaw 和驾驶员把控方向的相关性更强，这也符合常识，我们也将在4.2 章节中证明。对于式{7}，我们取 $\mathrm { k } { = } 1$ 。因此我们可以根据每次的yaw序列$\mathrm { x = \{ x 1 , x 2 , x 3 , \cdots , x n \} }$ 来计算每个时刻的 HM-LAIS。

具体而言，HM-LAIS被定义为下式：

$$
\begin{array} { r } { \mathrm { H M - L A I S ( t ) } = l o g _ { 2 } \frac { p ( y a w _ { t - 1 } , y a w _ { t } ) } { p ( y a w _ { t - 1 } ) p ( y a w _ { t } ) } } \end{array}
$$

其中， $y a w _ { t }$ 代表 $\mathrm { \Omega ^ { t } }$ 时刻驾驶员的水平头动转角。

另外，我们有汽车每个时刻朝向的序列 $\{ ( x _ { 1 } , y _ { 1 } )$ ， $( x _ { 2 } , y _ { 2 } )$ ， $( x _ { 3 }$ ，$y _ { 3 } ) \cdots$ ， $\left( x _ { n } , \ y _ { n } \right) \}$ ,我们可以计算出每个时刻的车辆偏转角（localvehiclesteeringangle，LVSA）一一与上个时刻的角度差,具体定义如下式：

$$
\begin{array} { r } { \mathrm { L V S A ( t ) } = \frac { \mathrm { x _ { t } x _ { t - 1 } + y _ { t } y _ { t - 1 } } } { \sqrt { \mathrm { x _ { t } ^ { 2 } + y _ { t } ^ { 2 } } } \ast \sqrt { \mathrm { x _ { t - 1 } ^ { 2 } + y _ { t - 1 } ^ { 2 } } } } } \end{array}
$$

图3是其中一位驾驶员一轮实验的例子。上方是HM-LAIS序列，下方是LVSA序列。高HLIAS意味着高的信息存储，即该时刻的司机头动行为（实际上是近乎不动）在全局中出现频率较高，意味着头动较为稳定。高LAIS经常出现在直道上，这也很好解释，即直道上驾驶员很少头动或只小幅转头，因此LAIS 较高；反之，低HM-LAIS 意味着低的信息存储，即该时刻的司机头动行为在全局中出现频率较少，意味着头动较为频繁。低LAIS经常出现在弯道上，说明弯道上司机会频繁调整头的转向。

![](images/c5b5ba975e1ff10c5140fe91e8dca4900814dadbe563baf376a1ea0fc6d33c15.jpg)  
图3某位驾驶员一轮实验的示意图。上方是HM-LAIS序列，下方是LVSA序列

# 4.2HM-LAIS与LVSA间的相关性

我们分别计算了 30 名驾驶员 HM-LAIS 和 LVSA 间的三个相关系数[6]：Pearson linear correlation coefficient (PLCC)， Spearman rank ordercorrelation coefficient (SRoCC) 和 Kendall rank order correlationcoefficient（KROCC)。为了说明仅使用yaw 计算HM-LAIS 的正确性，我们额外给出了使用三维头动角计算 HM-LAIS 的三个相关系数。60 次实验的三个相关系数的平均值如表1所示。

表1相关性分析结果  

<html><body><table><tr><td></td><td>PLCC,p-value</td><td>SROCC,p-value</td><td>KROCC, p-value</td></tr><tr><td>仅使用 yaw 计算 HM-LAIS</td><td>-0.533，p<0.01</td><td>-0.339,p<0.01</td><td>-0.473,p<0.01</td></tr><tr><td>使用三维头动角计算HM-LAIS</td><td>-0.483, p<0.01</td><td>-0.305, p<0.01</td><td>-0.421, p<0.01</td></tr></table></body></html>

从表1可以看出，相关系数均为负数，说明了它们是负相关，当HM-LAIS小时，LVSA大，反之亦然。仅使用yaw 时的相关系数的绝对值均大于使用三维头动角时的相关系数的绝对值，证明了仅使用yaw是更优的（因此本文中HM-LAIS仅以yaw 计算得出）。此时的相关性绝对值均大于0.3，证明了HM-LAIS与LVSA具有相关性。

另外，考虑到我们研究的是时序相关问题，我们额外使用了互相关系数作为相关性的度量，计算出值为-0.748,它代表了强烈的时序相关性。

# 4.3HM-LAIS与汽车LVSA的联合熵

联合熵定义为两个随机变量联合概率的自信息的数学期望，它可以衡量两个随机变量间的相关性。就我们的场景具体来说，若HM-LAIS和LVSA的联合熵较小，说明对于不同的车辆偏转角，驾驶员都分别采用了较为固定的头动偏转角来应对（举一个较为极端的例子，每当汽车偏转角为 $1 ^ { \circ }$ 时，驾驶员偏转角总为$1 ^ { \circ }$ ），体现出了较高的驾驶稳定性；反之，若HM-LAIS 和LVSA 的联合熵较大，说明驾驶员的头动很没有规律。举个例子，在4次右转弯事件中，可能驾驶员两次向右转头，一次直视前方，一次向左转头，从常理就可以推断出，这种行为模式代表着一种较差的驾驶水平。另外，熵这个概念本身就代表着事物的混乱程度。因此我们可以使用 HM-LAIS 与LVSA 的联合熵作为驾驶水平的一种量化指标,其计算方法如式（2）。我们分别计算了30个驾驶员的该指标，结果如图4。

![](images/bd8bf5f0e070d44c43dc14d7cb7c2b97d956440e36558edbd00f8c9eac207267.jpg)  
图4 驾驶员HM-LAIS与LVSA的联合熵

为了验证该指标的正确性，我们选取了驾驶员中的新手组（驾龄<1年，共8人）和经验丰富组（驾龄>2年，共9人），使用ANOVA计算两组间使用存在差异。计算结果 $\operatorname { F } \left( 1 , 1 5 \right) = 6 . 9 8$ ， $\mathrm { p } { < } 0 . 0 5$ ，箱形图如图{3}。可以证明两组间存在显著差异，由图可知，新手组的平均联合熵较大，说明头动模式较为混乱，经验丰富组平均联合熵较小，说明头动模式较为稳定，证明了该指标的可行性，我们认为该指标可以作为驾驶员方向平稳度的一种度量。

![](images/8e7b074d08cfda4596d5514b08b551f12cef273fcf1ecb07ee87301e63c2952b.jpg)  
图3新手和老手间联合熵的对比

# 4.4使用HM-LAIS预测LVSA

LAIS这个概念本来就代表着可预测性，我们希望可以根据司机每个时刻的头动，来预测下一个时刻的LVSA，以证明HM-LAIS的可信性和实用价值。我们的做法是，将每一轮实验前 $7 0 \%$ 的数据作为训练集，计算HM-LAIS，并依据［31]的方法计算 HM-LAIS 与 LVSA 之间的二维核密度估计（ $ { \mathrm { 2 D ^ { - } } }$ Kernel DensityEstimation,2D-KDE），该方法的优点是高效并且准确。我们将该2D-KDE 作为HM-LAIS 与 LVSA 之间的二维概率密度函数(2D-Probability DensityFunction,2D-PDF）并认为这个2D-PDF 是驾驶员应对不同偏转角时的头动模式，它具有很强的个体性和稳固性。然后将后 $3 0 \%$ 的数据作为测试集，输入每个时刻的头动，根据 2D-PDF 输出预测的下个时刻的LVSA，并与真实LVSA 做对比，计算准确率(定义为1-平均绝对百分比误差)和方根误差(Root Mean Square Error,RMSE)。求出60轮实验的平均预测准确率作为全局预测准确率。作为对比，我们不使用HM-LAIS，仅使用头水平转动角的原始数据，再次计算全局预测准确率。

另外，我们还使用了长短期记忆网络（Long Short-Term Memory，LSTM）作为对比。该网络包含一个具有 200个隐藏单元的LSTM层，然后是一个大小为50 的全连接层和一个丢弃概率为0.5 的丢弃层。训练方式为，以大小为 20 的小批量进行60 轮训练。指定学习率为0.01。为防止梯度爆炸，将梯度阈值设置为1。使用 $7 0 \%$ 的数据作为训练集， $3 0 \%$ 的数据作为测试集。

四次的结果如表2所示。分组对照可见，使用HM-LAIS比使用原始头动数据准确率高，使用 2D-KDE 比使用LSTM 准确率高，证明了HM-LAIS 和 2D-KDE 的价值，我们将在第5章详细讨论。

表2预测准确率结果  

<html><body><table><tr><td>accuracy</td><td>RMSE</td></tr><tr><td>Use HM-LAIS and 2D-KDE</td><td>88.56% 0.32</td></tr><tr><td>Use head yaw and 2D-KDE</td><td>86.34% 0.35</td></tr><tr><td>Use HM-LAIS and LSTM</td><td>87.43% 0.32</td></tr><tr><td>Use head yaw and LSTM</td><td>85.26% 0.36</td></tr></table></body></html>

# 5.讨论

驾驶员的头动行为对于其把握方向具有重要意义，驾驶员不可能在头乱动时平稳把握方向，也很难在头不动时安全转弯。从这个常识出发，我们深入研究了头动和LVSA之间的量化关系，使用的关键方法是LAIS。首先我们通过四种相关系数证明了HM-LAIS与LVSA之间的相关性，这从数学上证明了该常识的正确性。然后我们继续挖掘其内涵和应用。我们提出了用HM-LAIS与LVSA 的的联合熵作为驾驶平稳度的一种指标；提出用 HM-LAIS 与LVSA 的 2D-KDE 作为一种驾驶模式的表示。最后，我们基于HM-LAIS，实时预测下一时刻的LVSA，取得了较高的准确率，充分说明了本工作的完整性和实用价值。本工作的应用前景较广：可以使用本文的方法构建驾驶员监测系统（driver monitoringsystem，DMS),以有效监测司机的驾驶状态，防止出现酒驾、疲劳驾驶等情况[7]；另外，由于驾驶员头动早于汽车方向改变，如果可以将监测信息发送给周围车辆，将有利于突发行为（急刹车、急转弯等)及时预警。对目前火热的自动驾驶研究也具有参考意义，AI 司机若能接收周围人类司机的头动数据，就可以提前预测其驾驶行为，并采取措施。

LAIS 对于我们研究的课题具有重要价值。LAIS是单个时序序列中前一段时间对后一个时刻点的影响，它既体现了数据内部的连续性和存储性，又体现了外部环境改变，对该变量造成的影响。举个例子，正常情况下气温是不会发生剧烈变化的，每时刻的温度和上一时刻高度相关（很可能是基本不变），我们很容易使用过去一分钟的温度来预测下一秒的温度，这体现了“信息存储”的含义；但是当有下雨等突发气象状况时，温度可能骤变，而这种异常状况，很容易通过LAIS 的值的变化检测出来。因此，LAIS作为可预测性度量是普遍适用的，无论对于温度这种客观自然事物，还是对于股票价格等与人主观行为相关联的事物。总结来说，LAIS对于预测和异常检测具有重要作用。

之前关于LAIS应用的工作，主要是用LAIS当做是被研究对象某种内在属性的度量，使用LAIS在揭示该对象的某些规律。如Wang XR 等人［21]研究蜂群的运动，用LAIS 量化某时刻个体运动受周围邻居影响大还是受自己影响大；Wibral,M等人[22」在猫的18区电压敏感染料成像数据中，测量了在时间和空间上的局部尺度LAIS。他们表明，存储反映了神经属性，如刺激偏好和对意外刺激变化的惊讶．ChristianeB 等人［24]测量了驾驶员在变道前后 扫描路径的LAIS，用于量化动态任务中的扫描路径可预测性。上述研究喜欢把LAIS看做一种指标，它可以量化研究对象的某种属性，但较难说明系统更本质的特征。

我们研究的关键创新之处，便是把LAIS 看作是一个变量，研究其与其他变量（LVSA）间的关系，以研究驾驶过程中的认知模式。HM-LAIS首先代表着驾驶员的驾驶经验，有经验的驾驶员对于直道、弯道，以及直道和弯道间的切换，应该具有稳定的模式，而新手驾驶员可能会显得随心所欲，每次都采用较为随机的头动模式；HM-LAIS 还反映出环境变化，当HM-LAIS 值较低时，说明了驾驶员选择了较为少见的头动角，即发生了特殊情况（转弯）。因此，HM-LAIS体现了主观驾驶行为和客观驾驶环境的统一，充分量化了人-车-环境的协同程度。我们在建立数学模型时，没有仅使用LAIS自己，而是将LAIS与LVSA一起使用，也因此具有较大创新性并取得了更深入的成果。

我们创新性地使用LAIS做时间序列预测。为什么不使用原始头动角数据，而必须把它处理成为HM-LAIS？这是因为，头动角只是一个数字，而并不能说明此刻司机的头动状态，更没有包含任何和驾驶员驾驶模式相关的信息。举个例子，“驾驶员某个时刻头转角从向右17度转到了向右18度”，从这句话能推断出什么？司机是在无聊向右膘了一眼，还是因为转弯要转头观察情况？很难得出结论。首先，驾驶员习惯的头转幅度范围不同，有的驾驶员习惯大幅度头动（举个例子60 度），有的驾驶员即使转弯时也仅做小幅头动（举个例子20度），这种信息需要我们根据全局数据中分析出来。如果我们知道该驾驶员是后者，那么18 度的转动对他来说是很大幅度，可以谨慎地假设他是要大幅度转头以应对转弯等复杂情况。其次，我们不知道他上时刻的头动信息，不知道他是从18度转向了19度，还是从20度转向了19度。前者可能意味着驾驶员正在为一次即将到来的转弯做准备，而后者可能意味着驾驶员已经完成转弯正准备将头转回正前。接着，如果我们通过全局数据发现“驾驶员头从向右19 度转向向右20度10 次这种情况发生了50次，占比 $5 \%$ ”，那么我们就可以相信这种转移是稳定发生的，肯定是任务导向下驾驶员的应对模式，而很可能不是偶尔膘一眼。最后，如果我们又通过行车数据发现，司机恰好全程一共进行了50次右转弯，而且转弯时刻和18度->19度头转时刻恰好能对应上，那么我们就有了充足的基础实现头动到LVSA间的预测。

从这个例子我们可以得出，一个单独的数通常是毫无意义的，因为数据有很强的个体性，人与人之间的数据通常很难进行直接的比较，除非做特殊的归一化；

而数到数之间的转移是很有价值的，我们可以把它视为一个“事件”，它是人在任务中做认知、决策的最小单位。但更有价值的是事件在全局中发生的频率，这可以说明这个事件是偶然的还是稳定发生的。最后，我们可以做基于事件频率的时间序列预测。

因此，在预测中，LAIS的优点是实现了局部信和全局信息的统一。局部信息只有放在全局中，才能体现出特征，而这种特征对于数据分析具有重要意义。目前热门的神经网络是对大量数据进行大量计算来提取特征，但是其模型本身是个“黑盒子”，所提取的特征并不具有直接的语义，无法直接供人直接使用并进一步研究，因此可解释性是神经网络研究者的研究重点，目前已有大量工作[23]。而LAIS本身就是一个“白盒子”，所提取的信息简单并且有效，对于人来认知领域的研究尤其具有重要价值。

# 6．结论和工作展望

本文深入研究了头动和LVSA间的关系，提出了HM-LAIS的概念，提出了用 HM-LAIS与LVSA的的联合熵作为驾驶平稳度的一种指标；提出用 HM-LAIS与LVSA的 2D-KDE 作为一种驾驶模式的表示。最后，我们基于HM-LAIS，实时预测下一时刻的LVSA，取得了较高的准确率。

目前我们研究的驾驶场景较为简单，然而在现实的复杂交通环境下，引起头动的环境因素是多样的。目前研究的驾驶场景有很多，如变道、紧急状况等，我们期望能在这些场景中应用HM-LAIS。我们也有强烈的兴趣将现在的工作和无人驾驶研究结合起来，通过挖掘人类驾驶员的驾驶经验、模式，来指导AI驾驶员更安全地驾驶。

同时，我们采集了驾驶员操作方向盘、油门刹车等实时行为数据，在本次研究中暂未使用，未来我们期待研究这些数据间的关联性，使对驾驶行为的研究更具整体性。

# 参考文献:

[1] Shannon, C.E.,1948.A mathematical theory of communication. Bell Syst.Tech.J.6, 379-423.   
[2] Lizier JT, Prokopenko M, Zomaya AY.Local measures of information storage in complex distributed computation. Information Sciences. 2012; 208:39-54. https://doi.org/10.1016/j.ins.2012.04.016   
[3] Bossomaier T，Barnett L,Lizier JT.An introduction to transfer entropy: information flow in complex systems[M]. Springer Publishing Company, Incorporated, 2016.   
[4] Doshi A,Morris BT,Trivedi M M. On-Road Prediction of Driver's Intent with Multimodal Sensory Cues[J]. IEEE Pervasive Computing,2011,10(3):22-34.[5] C.J. Cellucci, A. M. Albano, and P.E. Rapp. Statistical validation of mutual information calculations: Comparison of alternative numerical algorithms. Physical Review E,71(6):66208,   
2005.   
[6] Bolboac Sorana-Daniela and Jntschi Lorentz，“Pearson versus spearman，kendall's tau correlation analysis on structure-activity relationships of biologic active compounds," Leonardo Journal of ences,vol.5,no.9,pp.179-200,2006.   
[7] Hayley A C, Shiferaw B，Aitken B ,et al. Driver monitoring systems (DMS): The future of impaired driving management?[J]. Traffic Injury Prevention.   
[8] Zhao Z X,Wei S M,Wang C .Eye-gaze tracking under unrestrained head movements[J]. Computer Engineering and Design,2009,30(1):247-250.   
[9] Zhu M, Chen W M,Song X K,et al. Research on Head Control of Humanoid Soccer Robot with Restricted View Field[J]. Computer Technology and Development, 2010.   
[10] Lv Z,Xu Q, Schoeffmann K,Parkinson S.Transfer Entropy Based Causality From Head Motion To Eye Movement. bioRxiv; 2021. DOl: 10.1101/2021.03.11.434910.   
[11] Liu T,Yang Y,Huang G B,et al.Driver distraction detection using semi-supervised machine learning[J].Electronic Imaging,2017,2017(10):20-26.   
[12] J.McCallet al., “Lane Change Intent Analysis Using Robust Operators and Sparse Bayesian Learning," to be published in IEEE Trans. Intelligent Transportation Systems,2006.   
[13]COOTES T， EDWARDS G， TAYLOR C.ActiveAppearance Models[J].IEEETrans PatternAnalysis and Machine Intelligence,2001,23 (6) :681.   
[14]MORENCYL P， DARRELL T.Stereo TrackingUsingICP andNormalFlow Constraint[C]//16th Intemational Conferenceon Pattem Recognition， Cambrige:Anant Agarwal, 2002,4(1) :40367.   
[15]ZHAO Gang-qiang.Research on Key Techniques of Vision-based Large Head Pose Tracking[D].Hangzhou:Zhejiang University， 2009. (in Chinese)   
[16]Rahman Md. Junaedur and Beauchemin Steven S.and Bauer Michael A. Predicting driver behaviour at intersections based on driver gaze and traffic light recognition[J]. IET Intelligent Transport Systems, 2020,14(14) : 2083-2091.   
[17]Dogan, U., Edelbrunner, H.,lossifidis,I: 'Towards a driver model: preliminary study of lane change behaviour'. Proc. of the 11th Int. IEEE Conf. on Inteligent Transportation Systems, Beijing,China,2008,pp.931- 937   
[18]Kraiss, K., Kuttelwesch, H.: ' Identification and application of neural operator models in car driving situation'.Proc.of the Fifth IFAC/IFIP/IFORS/IEA Symp.on Analysis，Design and Evaluation of Man-Machine-Systems,the Hague,Netherlands,1992, pp.121- 126   
[19]Leonhardt, V.,Wanielik, G:‘ Neural network for lane change prediction assessing driving situation，driver behavior and vehicle movement'. IEEE 2Oth Int. Conf.on Intelligent Transportation Systems (ITSC), Yokoharna, Japan, 2017, pp.1- 6   
[20]Ou, C., Karray,F:‘ Deep learning-based driving maneuver prediction system, IEEE Trans. Veh. Technol., 2020,69,(2), pp.1328- 1340   
[21]Wang XR, Miller JM, Lizier JT, Prokopenko M, Rossi LF. Quantifying and tracing information cascades in swarms. PLOS ONE. 2012; 7(7):e40084. https://doi.org/10.1371/journal.pone.0040084   
[22]Wibral，M.，Lizier， J.，Vogler， S.，Priesemann，V.，and Galuske，R. (2014). Local active information storage as a tool to understand distributed neural information processing. Front. Neuroinform. 8:1. doi: 10.3389/fninf.2014.00001   
[23]Zhang，Y.， Tino，P.， Leonardis，A.，and Tang，K.，“A Survey on Neural Network Interpretability",arXive-prints,2020.   
[24]Wiebel-Herboth CB, Kru"ger M,Wolstadt P (2021) Measuring inter- and intra-individual differences in visual scan patterns in a driving simulator experiment using active information storage. PLoS ONE 16(3): e0248166. https://doi. org/10.1371/journal.pone.0248166 [25]Wollstadt P, Hasenja"ger M,Wiebel-Herboth CB. Quantifying the predictability of visual scanpaths using active information storage.arXiv Preprint arXiv:201211447 [csCE]. 2020; [26]Edward G. Freedman，“Coordination of the eyes and head during visual orienting," Experimental Brain Research,vol.190,no.4,pp.369,2008.   
[27]A.Doshi and M.M.Trivedi,“Head and eye gaze dynamics during visual attention shifts in complex environments,” Journal of Vision,vol.12,no.2, pp.189-190,2012.   
[28] "Htc corporation," https://www.htcvive.com.   
[29]“Logitechg29,”https://www.logitechg.com/enus/products/driving/driving-forceracing-wheel.html.   
[30]"Unity" https://www.unity.com   
[31] Z.I. Botev. J.F. Grotowski. D.P. Kroese. "Kernel density estimation via diffusion." Ann. Statist. 38 (5) 2916 - 2957, October 2010. https://doi.0rg/10.1214/10-AOS799