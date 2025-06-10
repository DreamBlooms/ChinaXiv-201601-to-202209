# 比较洛伦兹变换和推迟电磁场的独立实验

汤克云1,2

1中国科学院地质与地球物理研究所，北京，1000292 清华大学天体物理中心，北京，100084kytang@bao.ac.cn

# 摘要

洛伦兹变换的时间膨胀是真实的物理效应还仅是数学的等效关系？本文提出一种独立实验方案，可在实验室坐标系比较和鉴别狭义相对论与Lienard-Wiechert 推迟电磁场理论的物理真实性。令一个高速运动电荷先后穿越两个相邻的皆配置有电场仪的屏蔽室；一方面可根据两种时空观分别计算出‘运动电荷的位置随时间变化’的理论曲线；另一方面可根据电场仪记录准确判断‘电荷位于第一个屏蔽室或第二个屏蔽室的时段’。将关于电荷位置的两条理论曲线与电场仪记录的实验曲线比较，即可判定何种理论符合自然实际。

关键词：屏蔽室，电场仪，推迟电磁场，洛伦兹变换

# An Independent Test to Compare Lorentz Transformation and Retarded Electromagnetic Field

TANG, Keyun1, 2 1 (Institute of Geology and Geophysics, Chinese Academy of Sciences, Beijing，100029,China) 2 (The Center for Astrophysics，Tsinghua University，Beijing，100084，China)

# Abstract

Is the time dilation of Lorentz transformation an actual physical effect or only a mathematical equivalent relation? This paper has proposed an independent test scheme, which can directly compare and identify the realities of special theory of relativity and Lienard - Wiechert theory of retarded electromagnetic field in the laboratory coordinate system. Making a fast moving charge passes successively through two adjacent shielding rooms all equipped with electrometer. On the one hand, two theoretical curves of the position-time of the moving charge can be calculated, according to the two kinds of space-time relations respectively. On the other hand, the time durations， during which the moving charge is located in the first or second shielding rooms, can be accurately determined according to the records of electrometers. To compare the two theoretical curves of position-time with the experimental curve of electric field recorded by electrometers, we can determine that which theory is in line with the nature.

Key words:Shielding Room, Electrometer， Retarded Electromagnetic Field, Lorentz Transformation

# 1．为什么要检验洛伦兹变换的物理真实性

对于携有电量 $q$ ，以速度 $\vec { \nu }$ 作匀速直线运动的点电荷 $\boldsymbol { Q }$ ，众多教科书分别根据Lienard-Wiechert推迟电磁场或狭义相对论求解其电场分布，获得相同的表达式[1,2,3,4]

$$
\vec { E } ^ { ( \vec { r } , t ) = } \frac { q \gamma \vec { r } } { 4 \pi \varepsilon _ { 0 } ( r _ { \perp } ^ { 2 } + \gamma ^ { 2 } r _ { \parallel } ^ { 2 } ) ^ { 3 / 2 } }
$$

其中，洛伦兹膨胀因子

$$
\gamma \equiv \frac { 1 } { \sqrt { 1 - \nu ^ { 2 } / c ^ { 2 } } }
$$

为便于比较，我们只研究沿飞行路径 $E F$ 之场点的电场，（1.1）式简化为

$$
\vec { E } = \frac { q \gamma \vec { r } } { 4 \pi \varepsilon _ { 0 } ( \gamma ^ { 2 } r _ { \parallel } ^ { 2 } ) ^ { 3 / 2 } } = \frac { q \vec { r _ { \parallel } } } { 4 \pi \varepsilon _ { 0 } ( \gamma ^ { 2 } r _ { \parallel } ^ { 3 } ) } = \frac { q } { 4 \pi \varepsilon _ { 0 } ( \gamma ^ { 2 } r _ { \parallel } ^ { 2 } ) } \vec { e _ { \parallel } }
$$

主流教科书认为，相同的表达式表明两种理论是等价的，都是正确的。笔者曾注意到，相同表达式背后的物理表述是存在差别的。我曾指出，根据库仑定律，当电荷 $\boldsymbol { Q }$ 相对于观测点静止，其电势分布不随时间变化，仅与电荷的电量成正比，与电荷至场点的距离成反比

$$
\varphi = { \frac { q } { 4 \pi \varepsilon _ { 0 } r } }
$$

当电荷相对于观测点作匀速运动，库伦势变为Lienard-Wiechert推迟势，推迟标量势为

$$
\varphi ( \vec { r } , t ) = \frac { q } { 4 \pi \varepsilon _ { 0 } ( r _ { * } - \displaystyle \frac { \vec { r } _ { * } \cdot \vec { \nu } _ { * } } { c } ) } = \frac { q } { 4 \pi \varepsilon _ { 0 } r _ { * } ( 1 - \displaystyle \frac { \nu _ { \parallel } ^ { * } } { c } ) }
$$

推迟矢量势为

$$
\vec { A } ( \vec { r } , t ) = \frac { \mu _ { 0 } q \vec { \nu } _ { * } } { 4 \pi ( r _ { * } - \displaystyle \frac { \vec { r } _ { * } \cdot \vec { \nu } _ { * } } { c } ) } = \frac { \mu _ { 0 } q \vec { \nu } _ { * } } { 4 \pi r _ { * } ( 1 - \displaystyle \frac { \nu _ { | | } ^ { * } } { c } ) }
$$

其中， $\vec { \nu } _ { * } , \vec { r } _ { * }$ 依次为电荷速度和由电荷指向观测点的矢径， $\nu _ { \parallel } ^ { * }$ 是电荷速度沿 $\vec { r } _ { * }$ 方向的分量， $( * )$ 号的量为推迟量。在推迟标势和矢势中，第一次出现了某种意义下的收缩因子

$$
k \equiv ( 1 - \frac { \nu _ { \parallel } ^ { * } } { c } )
$$

尤峻汉教授称其为影响因子，并将

$$
\widetilde q \equiv \frac { q } { k }
$$

称作有效电荷[5]。本文认为，尤峻汉教授定义的有效电荷或等效电荷，意义十分清楚，只是一种数学等效关系，电荷量并没有真的发生变化。仿效尤峻汉教授的定义，我们也可将

$$
\tilde { R } _ { * } \equiv r _ { * } ( 1 - \frac { \nu _ { | | } ^ { * } } { c } ) = k r _ { * }
$$

称作等效推迟距离，但电荷推迟位置到观测点的距离并没有真的发生变化！

下面，考虑到推迟时刻与现时刻的关系

$$
t _ { * } = t - \frac { r _ { * } } { c }
$$

和推迟位置与现位置的关系

$$
\vec { r } = \vec { r } _ { * } - \vec { \nu } _ { * } \frac { r _ { * } } { c }
$$

逐步计算推迟标势的梯度和推迟矢势的偏导数，最后可求出其电场

$$
\vec { E } ( \vec { r } , t ) = - \nabla \varphi - \frac { \partial \vec { A } } { \partial t } = \frac { q \gamma \vec { r } } { 4 \pi \varepsilon _ { 0 } ( r _ { \perp } ^ { 2 } + \gamma ^ { 2 } r _ { \parallel } ^ { 2 } ) ^ { 3 / 2 } }
$$

强调一下，在以上推导中，出现了收缩因子 $k$ 和洛伦兹因子 $\gamma$ ，是由于电荷的运动，电磁场与距离的物理关系发生了真实变化：从简单的库伦电场公式变为推迟电场公式。所有的推导，都是在牛顿绝对时空中进行的，刚尺和时钟并未变化[3]。

而狭义相对论认为,洛伦兹膨胀因子 $\gamma$ 的出现，是由于运动点电荷的时间膨胀，从固有时间 $( \tau _ { o } )$ 变为 $( \gamma \tau _ { o } )$ ，从而使电荷运动的距离不再等于固有距离 $d _ { o }$ ，而是真实地改变为 $( \gamma d _ { 0 } )$ 。例如，宇宙线中的 $\mu$ 介子[，固有寿命为（20 $\tau _ { o } = 2 . 2 \times 1 0 ^ { - 6 } s$ ，固有距离只应有 $d _ { o } = 6 6 0 m$ 却可以穿越 $d = 2 0 k m$ 的大气层，被认为是运动 $\mu$ 介子的真实寿命加长，真实运动距离从 $d _ { o } = 6 6 0 m$ 增加至$d = 2 0 k m$ 。

如何理解上述两种时空观之间的尖锐矛盾，电荷的运动距离是否发生了真实的膨胀？在上述宇宙线中的 $\mu$ 介子观测中，没有在地面坐标系直接测量 $\mu$ 介子的速度和飞行时间，只是一个间接测量[。还有若干‘支持’时间膨胀和距离膨胀的实验，都是不明晰的间接实验。最有说服力的判据是在地面实验室坐标系直接测量‘运动电荷的位置’。

# 2．实验方案

由于两种理论导出的电磁场表达式完全相同，似乎难以分辨，为此已纠结了100 多年。本文根据上述矛盾，提出一种实验方案，可在实验室坐标系直接比较和鉴别推迟势与狭义相对论的物理真实性：有两个相邻屏蔽室 $A$ 和 $B$ ，如图1，长度都是 $L$ ，屏蔽室 $A$ 的后壁、前壁留有小孔 $E$ 和 $F$ ，连线 $E F$ 垂直于前、后壁，电荷可由小孔 $E$ 进入屏蔽室 $A$ ，再经小孔 $F$ 进入屏蔽室 $B$ ，两室内分别配置有电场仪 $M _ { \scriptscriptstyle A }$ 的和 $\boldsymbol { M } _ { \scriptscriptstyle B }$ 。

![](images/b19842fb251d780cdd2b1ff81292febfbcf5078455d2089ef3161711633089e8.jpg)

图1由金属片网构成的屏蔽室 $A$ 和 $B$ 。在屏蔽室 $A$ 的前、后壁各留一小孔 $F$ 和 $E$ ，电荷可由小孔 $E$ 沿 $+ X$ 轴方向进入屏蔽室 $A$ ，再经小孔 $F$ 进入屏蔽室 $B$ ， $G$ 和 $\boldsymbol { G ^ { \prime } }$ 分别是位于屏蔽室 $A$ 和 $B$ 内的两个点， $G E = 0 . 6 L , G ^ { ' } E = 1 . 2 L$ ；屏蔽室 $A$ 和 $B$ 内分别安置有电场仪${ { M } _ { A } }$ 和 $\boldsymbol { M } _ { \scriptscriptstyle B }$ 。

为表述明确、简洁，我们不妨取

$$
\begin{array} { l } { \displaystyle \beta \equiv \frac { \nu } { c } = \frac { \sqrt { 3 } } { 2 } , } \\ { \displaystyle \gamma = \frac { 1 } { \sqrt { 1 - \beta ^ { 2 } } } = 2 } \end{array}
$$

先按照经典电动力学和Lienard-Wiechert推迟势，确定点电荷的位置和所在屏蔽室：

$$
\left\{ \begin{array} { l l } { { w h e n ~ 0 < t < \frac { L } { \nu } , ~ 0 < x < L , ~ i n ~ r o o m ~ A } } \\ { { w h e n ~ \frac { L } { \nu } < t < \frac { 2 L } { \nu } , L < x < 2 L , ~ i n ~ r o o m ~ B } } \end{array} \right.
$$

假如洛伦兹膨胀因子真实代表了飞行距离的增加，可按照狭义相对论计算点电荷的‘真实位置’和所在屏蔽室：

$$
\left\{ \begin{array} { l l } { w h e n ~ 0 \zeta t < \displaystyle \frac { 0 . 5 L } { \nu } , ~ 0 < ( \gamma x ) < L , ~ i n ~ r o o m ~ A } \\ { w h e n ~ \displaystyle \frac { 0 . 5 L } { \nu } \zeta t < \displaystyle \frac { L } { \nu } , L < ( \gamma x ) < 2 L , ~ i n ~ r o o m ~ B } \\ { w h e n ~ t > \displaystyle \frac { L } { \nu } , ( \gamma x ) > 2 L , ~ o u t ~ f r o m ~ r o o m ~ B } \end{array} \right.
$$

显然，上述两种‘电荷位置随时间变化’的情况存在巨大差别。例如，在屏蔽室 $A$ 内，在 $E F$ 连线上取一点 $G$ ， $G E = 0 . 6 L$ 。按照经典电动力学，当时间为 $t = 0 . 6 L / \nu$ ，电荷到达 $G$ 时，当然在屏蔽室 $A$ 内，电场仪 $M _ { \scriptscriptstyle A }$ 的读数不为零，$\boldsymbol { M } _ { \scriptscriptstyle B }$ 的读数应为零。而按照狭义相对论，当时间为 $t = 0 . 6 ~ / \imath$ ，$G ^ { \prime } E = 0 . 6 L \gamma = 1 . 2 L$ ，电荷已不在屏蔽室 $A$ 内，而应在屏蔽室 $B$ 内，电场仪 $M _ { \scriptscriptstyle A }$ 的读数应为零，而 $\boldsymbol { M } _ { \scriptscriptstyle B }$ 的读数应不为零。

在任何时刻，点电荷要么在屏蔽室 $A$ 内，要么在屏蔽室 $B$ 内，答案是唯一的，不可能两者都对！分别将根据两种时空观计算的‘电荷位置’与电场仪读数比较，即可确定何种时空观是真实、合理的。

鉴于上述计算和实验都是在实验室参考系实施的，是可以直接比较的！而且，一般加速器可使电荷速度达到0.5至0.99倍光速，对于速度为0.5至0.99倍光速的点电荷，穿越长度为1米量级的屏蔽室，穿越时间为 $1 0 ^ { - 8 } s$ 量级；现代实验技术，可确保时间测量精度不低于 ${ { 1 0 } ^ { - 1 2 } }$ 。因此，本文提出的实验方案是可行的。本文提出的实验方案对于比较和鉴别狭义相对论和推迟电磁理论，是一个严峻、可行的决定性实验，具有十分重要的物理意义。

# 3．讨论

1）经深入的研究，本文发现：由洛伦兹变换导出的公式（1.1）中的矢径r本应是由运动点电荷指向两坐标系（实验室坐标系和电荷随动坐标系）的共同初始原点之矢径；假若观测空间是均匀的，总可以将共同初始原点平移至观测点（场点)，这样，由运动电荷指向共同原点和指向观测点就成了一回事；但是，假若空间是不均匀的，例如，存在一些屏蔽材料，将观测空间分割为几个不均匀的子空间，我们必须在每个子空间分别计算运动点电荷指向观测点的矢径，这样，由运动电荷指向共同原点和指向观测点就不再等效，狭义相对论与Lienard-Wiechert推迟电磁场的矛盾就暴露出来了。

2）如何直接测量电荷相对于实验室的速度。让加速器加速电荷 $Q$ ，令其速度足够块；令其由小孔 $E$ 进入屏蔽室 $A$ ，再经小孔 $F$ 进入屏蔽室 $B$ ；当电荷由小孔 $E$ 进入屏蔽室 $A$ 的瞬间 $t _ { E }$ ，电场仪 $M _ { \scriptscriptstyle A }$ 的读数会从零突然增加，当电荷由小孔 $F$ 进入屏蔽室 $B$ 的瞬间 $t _ { F }$ ，电场仪 $\boldsymbol { M } _ { \scriptscriptstyle B }$ 的读数会从零突然增加，两时刻之差 $( t _ { F } - t _ { E } )$ 即为电荷 $\boldsymbol { Q }$ 从小孔 $E$ 运动至小孔 $F$ 所需的时间，所以电荷 $Q$ 的速度为

$$
\nu = \frac { L } { t _ { \scriptscriptstyle F } - t _ { \scriptscriptstyle E } }
$$

3)运动电荷的时间和距离是不是膨胀？迄今为止，只有间接的实验，例如，对宇宙线中 $\mu$ 介子飞行距离的观测，并没有独立、直接测量 $\mu$ 介子的飞行距离和对应的时间。最令人费解的一点是，Chamberlain等测量到 $\pi$ 介子的飞行距离为 40 英尺，也测量到介子的飞行时间 $3 8 \times { { 1 0 } ^ { - 9 } } { { s } }$ ，都是在地面参考系实施的；在计算介子速度时，自然应是直接将运动距离除以运动时间，得到 $\pi$ 介子速度;但Chamberlain等却舍近求远，弃简用繁，用介子动量和狭义相对论的动量公式求 $\pi$ 介子速度。这作法一隐含两个问题，第一，介子动量是在地面参考系测量的吗，准确到什么地步？第二，更要紧的一点，用狭义相对论的动量公式求 $\pi$ 介子速度，意味着测量是非独立的！现在，我们的目的是要检验‘狭义相对论所说的运动时间膨胀和运动距离膨胀是否正确’，你先用狭义相对论的动量公式求 $\pi$ 介子速度，意味着‘将待检验的东西用作论据’，这等于是让‘运动员兼裁判员’，让‘嫌疑人当法官’，存在‘逻辑循环’的根本失误，论证是不可信的。

一个独立、直接的明晰实验要胜过100个非独立、间接的非明晰实验；即使有1000个正面的实验结果，只要有1个反例，结论便不成立。所谓独立，就是所有的测量不依赖待检验的理论；所谓直接，在这里就是直接测量距离与时间。4）本文提出的实验方案，是用地面坐标系的米尺独立和直接地测量电荷的飞行距离，用地面坐标系的电场仪（含时钟）独立测量对应的时间。未用到任何人为的假设，更没有用到任何与‘待检验结论’有关的假设！‘运动电荷的运动距离是不是会膨胀’？先不作任何假设，等待实验结果的判断。

# 参考文献

[1]J.D. Jackson，Classical Electrodynamics, $2 ^ { \mathrm { n d } }$ edition，John Wiley& Sons，Inc.，New York,1975.  
[2］胡友秋，程福臻，电磁学与电动力学（下册），科学出版社，2008.1，北京.  
[3］汤克云，洛伦兹变换只是数学表象推迟作用才是物理本质（修改稿），中国国家科技图书文献中心预印本服务系统，(2014.6.12).  
[4］刘辽，费保俊，张允中，狭义相对论，科学出版社，2008.7，北京.  
[5]尤峻汉，天体物理中的辐射机制（第二版)，科学出版社，1998.8，北京.  
[6]张元仲，狭义相对论实验基础，科学出版社，1979.9，北京.