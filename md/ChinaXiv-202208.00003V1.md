# 纵向关系的探究：基于交叉滞后结构的追踪模型

方俊燕1 温忠麟\*\*² 黄国敏(华南师范大学心理学院，广州，510631)(华南师范大学心理应用研究中心/心理学院，广州，510631)(华南师范大学心理学院，广州，510631)

摘 要基于交叉滞后结构的追踪模型对于揭示变量间纵向关系具有重要作用，也为因果关系的验证奠定了基础。交叉滞后面板模型在一定条件下可转换为其他形式的模型，如何选择适当的模型是重要的议题。本文对各模型进行概述，并从模型结构、预设轨迹、时间点要求等方面进行比较，最后通过一个实例说明如何选择适当的模型。结果表明，不同模型在变量关系的判断上可能给出很不同的结果，实际运用中应当有模型选择和模型比较的意识。

关键词 纵向关系 交叉滞后 追踪模型 模型选择

# 1引言

追踪设计的广泛使用推动了心理学等社会科学领域对变量之间因果关系的讨论，有学者认为基于追踪数据建立的时序关系本质上是相关性的，不足以支撑可靠的因果推论（Usamietal.,2019)，因果推论还是需要有理论、文献或经验常识的支持（温忠麟,2017)。因此，研究者们在使用追踪数据探究变量间关系时更多使用纵向关系（longitudinalrelation）或相互关系（reciprocalrelation）而非因果关系（causality）的表述（Usami etal.,2019;Wiedermann &von Eye,2020)。纵向相互关系是一种双向的效应，在实证研究中其往往表现为一个变量的早期取值会影响另一个变量的后期取值（或变化量)，反之亦然（Curranetal.,2014;Wiedermann&von Eye,2020)。这种相互作用在心理学研究中很常见，例如发展心理学的理论通常认为个体特征变量与环境变量之间是相互影响的（Curran etal.,2014)。探究变量间的纵向相互关系对于理解生命历程中的个体发展非常重要，也能为因果推论的验证奠定基础

（Mund&Nestler,2019）。

交叉滞后面板模型（Cross-Lagged PanelModel,CLPM）是公认的探究变量之间动态关系的强有力的方法。与传统的分析重复测量数据的方法相比，CLPM具有高度的灵活性，能够处理时变协变量、多变量分析以及多组分析等，且可以提供多种模型拟合指数和修正指数（Curran etal.,2010)。CLPM通过交叉滞后路径反映变量间的历时性作用，即构建一个变量的先前水平对该变量当前水平的作用路径（称为自回归效应）以及其对另一变量当前水平的作用路径（称为交叉滞后效应)。交叉滞后结构的一个突出优点是能够控制结果变量的先前水平，即控制了一种潜在的“第三变量”（third variable）的影响（Cole&Maxwell,2003）。在纵向研究中，结果变量的先前水平往往同时和结果变量当前取值以及预测变量相关，因此需控制其影响。

基于交叉滞后结构出现了一系列追踪模型，如随机截距交叉滞后面板模型（RandomIntercept Cross-Lagged Panel Model,RI-CLPM）、结构化残差潜在曲线模型(Latent Curve Modelwith Structured Residuals,LCM-SR）和潜在变化分数模型（Latent Change Score Model,LCS）等，这些模型被广泛地运用于变量间纵向关系的探究。不同模型各有所长，所适用的数据结构也不同，没有任何一个模型是万能的（Curran et al.,2014; Mund&Nestler,2019)。然而，许多研究者并不了解各模型之间的差异，在实际运用中也缺乏模型选择和模型比较的意识。本文对基于交叉滞后结构的追踪模型进行分析和比较，首先对上述模型进行概述，然后厘清各个模型之间的差异和关联，并明确不同模型所适用的研究情境，最后通过一个实例说明如何选择适当的模型。

# 2 模型概述

# 2.1交叉滞后面板模型（CLPM)

Joreskog（1970）将时间序列分析中的向量自回归模型纳入结构方程建模框架，从而获得了CLPM，其假设变量的观测值围绕组均值上下波动。

对于变量 $x$ 和 $y$ ，被试 $i ~ \left( i { = } 1 , \cdots , N \right)$ 在时间点 $t ~ \left( t { = } 1 , \cdots , T \right)$ 的观测值分别为 $x _ { i t }$ 和 $y _ { i t }$

$$
\begin{array} { l } { { x _ { i t } = \mu _ { x t } + x _ { i t } ^ { * } } } \\ { { \nonumber } } \\ { { y _ { i t } = \mu _ { y t } + y _ { i t } ^ { * } } } \end{array}
$$

其中， $\mu _ { x t } , \ \mu _ { y t }$ 表示组均值， $x _ { i t } ^ { * } , \ y _ { i t } ^ { * }$ 表示时间特定的偏移量。首先进行中心化处理，提取出时间特定的偏移量，以表示每个被试在变量上随时间的变动，

$$
\begin{array} { c } { { x _ { i t } ^ { \ast } = x _ { i t } - \mu _ { x t } } } \\ { { { } } } \\ { { y _ { i t } ^ { \ast } = y _ { i t } - \mu _ { y t } } } \end{array}
$$

然后构建交叉滞后方程：

$$
\begin{array} { r } { x _ { i t } ^ { * } = \beta _ { x t } x _ { i ( t - 1 ) } ^ { * } + \gamma _ { x t } y _ { i ( t - 1 ) } ^ { * } + d _ { x i t } } \\ { y _ { i t } ^ { * } = \beta _ { y t } y _ { i ( t - 1 ) } ^ { * } + \gamma _ { y t } x _ { i ( t - 1 ) } ^ { * } + d _ { y i t } } \end{array}
$$

其中， $\beta _ { x t } , \ \beta _ { y t }$ 为自回归系数， $\gamma _ { x t } , \ \gamma _ { y t }$ 为交叉滞后系数， $d _ { x i t }$ 、 $d _ { y i t }$ 为回归残差。一般所称的交叉滞后结构默认同时包含自回归路径和交叉滞后路径。

自回归系数和交叉滞后系数都反映了被试内效应（Curran etal.,2014)，其中，自回归系数 $( \beta _ { x t } , \beta _ { y t } )$ 体现了变量的等级稳定性（rank-order stability)，即被试们在给定变量上的高低顺序不随时间变化的性质；交叉滞后系数 $( \gamma _ { x t } , \gamma _ { y t } )$ 表示在控制了上一时刻的结果变量（如 $y _ { i ( t - 1 ) } ^ { * } )$ 对自身的影响后，预测变量（如 $x _ { i ( t - 1 ) } ^ { * } )$ ）对结果变量（如 $y _ { i t } ^ { * }$ ）的历时性影响，交叉滞后系数通常被认为是推断变量间纵向关系的关键所在。

CLPM假设不存在稳定的被试间差异，参数中同时混合了被试内效应和被试间效应，这可能导致错误的结论（Mund&Nestler,2019）。

# 2.2随机截距交叉滞后面板模型 (RI-CLPM)

Hamaker 等人（2015）在CLPM中引入了随机截距这一潜变量，得到RI-CLPM。该模型假设变量的观测值围绕自身的特质性水平上下波动。

$$
\begin{array} { c } { { x _ { i t } = \mu _ { x t } + I _ { x i } + x _ { i t } ^ { * } } } \\ { { \nonumber } } \\ { { y _ { i t } = \mu _ { y t } + I _ { y i } + y _ { i t } ^ { * } } } \end{array}
$$

与公式（1）相比，公式（4）增加了特质因子 ${ { I } _ { x i } } \setminus I _ { y i }$ ，表示稳定的特质性因素，取值随个体变化。特质因子的所有负荷都固定为1，也称为随机截距项（Hamaker etal.,2015)。在分离出组均值和稳定特质因子之后，RI-CLPM同样采用时间特定的偏移量 $( x _ { i t } ^ { * } , ~ y _ { i t } ^ { * } )$ 来构建交叉滞后模型（同公式3)。相比于CLPM,RI-CLPM更能准确地反映变量的被试内变化过程。

# 2.3结构化残差潜在曲线模型（LCM-SR）

# 2.3.1潜在曲线模型(LCM)

结构化残差潜在曲线模型（LCM-SR）是以潜在曲线模型（Latent CurveModel,LCM)为基础建构的。LCM也称为潜在增长模型（Latent Growth Model,LGM）和潜在增长曲线模型（Latent Growth Curve Model,LGCM)。该模型由 Meredith 和 Tisak（1990）提出，其使用特定时间点的观测变量来推断变量的潜在增长趋势。

$$
\begin{array} { c } { { x _ { i t } = I _ { x i } + \lambda _ { t } S _ { x i } + x _ { i t } ^ { * } } } \\ { { { } } } \\ { { y _ { i t } = I _ { y i } + \lambda _ { t } S _ { y i } + y _ { i t } ^ { * } } } \end{array}
$$

$$
\begin{array} { l } { I _ { x i } = \mu _ { x I } + \zeta _ { x I i } } \\ { I _ { y i } = \mu _ { y I } + \zeta _ { y I i } } \\ { S _ { x i } = \mu _ { x S } + \zeta _ { x S i } } \\ { S _ { y i } = \mu _ { y S } + \zeta _ { y S i } } \end{array}
$$

其中， $I _ { x i } \setminus I _ { y i }$ 表示 $x , y$ 的初值(截距)， $\textit { S } _ { x i } \setminus \textit { S } _ { y i }$ 表示变化率， $\lambda _ { t }$ 表示时间的函数值（例如对于线性增长模型， $\lambda _ { t } = t - 1$ ， $t \geq 2 ^ { \cdot }$ ； $x _ { i t } ^ { * } , \ y _ { i t } ^ { * }$ 表示残差，同一个变量的各个时间点的残差相互独立，不同变量的残差在同一时间点有相关； $\mu _ { x I } \mathrm { ~ , ~ } \ \mu _ { y I }$ 表示所有被试的初值的均值；$\mu _ { x S } \mathrm { , ~ } \mu _ { y S }$ 表示所有被试的变化率的均值， $\zeta _ { x I i } \setminus \zeta _ { y I i } \setminus \zeta _ { x S i } \setminus \zeta _ { y S i }$ 表示误差。

LCM 的主要目的在于获得变量发展轨迹的特征，初值和变化率可统称为增长因子（growth factors)，然而增长因子无法反映两个变量随时间协同发展这一被试内过程，因此这里只考虑结构化残差潜在曲线模型(LCM-SR)。

# 2.3.2结构化残差潜在曲线模型（LCM-SR）

Curran 等人（2014）提出的LCM-SR，是在LCM基础上引入交叉滞后结构，使用分离出增长因子后的残差来建立交叉滞后方程。LCM-SR假设变量 $x$ 和 $y$ 具有系统的随时间变化的趋势，并通过增长因子 $( I _ { x i } , I _ { y i } ; S _ { x i } , S _ { y i } )$ 反映。首先将公式（5）中的残差移到方程左侧：

$$
\begin{array} { r } { x _ { i t } ^ { * } = x _ { i t } - I _ { x i } - \lambda _ { t } S _ { x i } } \\ { \phantom { x _ { i t } ^ { * } = } y _ { i t } ^ { * } - I _ { y i } - \lambda _ { t } S _ { y i } } \end{array}
$$

然后再构建交叉滞后方程，从而实现残差的结构化，

$$
\begin{array} { r } { x _ { i t } ^ { * } = \beta _ { x t } x _ { i ( t - 1 ) } ^ { * } + \gamma _ { x t } y _ { i ( t - 1 ) } ^ { * } + d _ { x i t } } \\ { y _ { i t } ^ { * } = \beta _ { y t } y _ { i ( t - 1 ) } ^ { * } + \gamma _ { y t } x _ { i ( t - 1 ) } ^ { * } + d _ { y i t } } \end{array}
$$

在LCM-SR中，描述变量发展轨迹特征的增长因子并不参与交叉滞后方程，后者中的关键参数仅仅是针对具体时间点的，这样就清晰地分离了被试间差异和被试内效应（Curranet al.,2014)。然而，有学者认为LCM-SR在构建纵向关系方程之前对变量进行了去趋势处理，排除了增长因子的作用，因此除非有足够理由认为变量的发展轨迹主要是由时变的遗漏变量导致的，否则使用该模型可能造成估计偏差（Usamietal.,2019）。

# 2.4潜在变化分数模型（LCS）

潜在变化分数模型，也称为潜在差异分数模型（LatentDifference Score Model,LDSM)，由 McArdle 和Hamagami（2001）提出，LCS基于变化量（change）进行建模，其重点关注一个变量的先前水平对于另一个变量的变化量的影响。

和上述模型不同，LCS考虑了测量误差，

$$
\begin{array} { r } { x _ { i t } = f _ { x i t } + \varepsilon _ { x i t } } \\ { y _ { i t } = f _ { y i t } + \varepsilon _ { y i t } } \end{array}
$$

其中， $f _ { x i t } \setminus f _ { y i t }$ 表示潜在分数， $\begin{array} { r l } { \varepsilon _ { x i t } \backprime } & { { } \varepsilon _ { y i t } } \end{array}$ 表示测量误差。

可获得潜在变化分数，

$$
\begin{array} { c } { { \varDelta f _ { x i t } = f _ { x i t } - f _ { x i ( t - 1 ) } } } \\ { {  } } \\ { { \varDelta f _ { y i t } = f _ { y i t } - f _ { y i ( t - 1 ) } } } \end{array}
$$

其中， $\Delta f _ { x i t } , \ \Delta f _ { y i t }$ 表示潜在变化分数，即t－1时间点和 $t$ 时间点之间潜变量的变化量。最后基于潜在变化分数构建交叉滞后方程，

$$
\begin{array} { r } { \Delta f _ { x i t } = G _ { x i } + \beta _ { x t } f _ { x i ( t - 1 ) } + \gamma _ { x t } f _ { y i ( t - 1 ) } + d _ { x i t } } \\ { \Delta f _ { y i t } = G _ { y i } + \beta _ { y t } f _ { y i ( t - 1 ) } + \gamma _ { y t } f _ { x i ( t - 1 ) } + d _ { y i t } } \end{array}
$$

其中， $G _ { x i }$ 和 $G _ { y i }$ 描述了时间历程中变量的总体增长或减少，称为恒定变化（constant change)，而自回归和交叉滞后部分则为比例变化（proportional change)。LCS 模型可以同时探究变量长期性的变化和即时性的波动。

上述各个模型在参数估计过程中均默认要求测量间隔等距，以保证有意义的参数解释（Mund&Nestler,2019）。

# 3 模型比较

基于交叉滞后结构的各个追踪模型结构相似且存在一定关联（见图1)。

![](images/d45bd90f5ea16633cba4accfd8db0fb46bcfe0262c5794cda97a7bf4544aa9b8.jpg)  
图1各模型间关联

首先，对CLPM进行一定的变换，可获得其他形式的交叉滞后模型。以CLPM作为基准模型，若在方程中纳入取值随个体变化的特质因子 $( I _ { x i } , \ I _ { y i } )$ ）可得到 RI-CLPM；若采用LCM 模型的方式分离出增长因子 $( I _ { x i } , I _ { y i } ; S _ { x i } , S _ { y i } )$ ，再基于残差构建交叉滞后路径可得到

LCM-SR；若对观测值不进行中心化处理而是考虑测量误差（如公式9)，然后，采用潜在分数的差值构建交叉滞后路径，并加入取值随个体变化的恒定变化因子（ $\ ( \ G _ { x i } \setminus \ G _ { y i } )$ ，可得到LCS（Usami et al.,2015)。因此，可以认为，LCM-SR、RI-CLPM和LCS 都是CLPM在一定变化条件下的特殊形式。

上述模型之间存在数理关联。Usami等人（2019）归纳了一个统一的结构框架，该框架由三种通用方程构成，分别是测量方程、分解方程和动态方程。假设自回归系数和交叉滞后系数均不随时间变化，则三种方程分别为：

$$
x _ { i t } = f _ { x i t } + \varepsilon _ { x i t } , y _ { i t } = f _ { y i t } + \varepsilon _ { y i t }
$$

$$
f _ { x i t } = \mu _ { x t } + I _ { x i } + ( t - 1 ) S _ { x i } + f _ { x i t } ^ { * } , f _ { y i t } = \mu _ { y t } + I _ { y i } + ( t - 1 ) S _ { y i } + f _ { y i t } ^ { * }
$$

$$
f _ { x i t } ^ { * } = G _ { x i } + \beta _ { x } f _ { x i ( t - 1 ) } ^ { * } + \gamma _ { x } f _ { y i ( t - 1 ) } ^ { * } + d _ { x i t } , \ f _ { y i t } ^ { * } = G _ { y i } + \beta _ { y } f _ { y i ( t - 1 ) } ^ { * } + \gamma _ { y } f _ { x i ( t - 1 ) } ^ { * } + d _ { y i t }
$$

需要注意，为了能够全面地涵盖各个模型，在测量模型中考虑了测量误差，引入了潜在分数 $( f _ { x i t }$ )，因此，为了在随后的分解方程中保持左右两侧符号的一致性，采用 $f _ { x i t } ^ { * } , \ f _ { y i t } ^ { * }$ 来表示时间特定的偏移量或残差，对应于（1）那样的方程中的 $x _ { i t } ^ { * } , ~ y _ { i t } ^ { * }$ 。

通过在三种通用方程中删除和保留特定元素，可以获得不同的交叉滞后模型。例如，在测量方程中删除测量误差 $( \varepsilon _ { x i t } )$ ，在分解方程中删除截距和变化率因子 $( [ I _ { x i } + ( t - 1 ) S _ { x i } ] )$ ，同时在动态方程中仅保留交叉滞后结构与残差（ $[ \beta _ { x } f _ { x i ( t - 1 ) } ^ { * } + \gamma _ { x } f _ { y i ( t - 1 ) } ^ { * } + d _ { x i t } ] )$ ，可获得CLPM；基于CLPM，在分解方程中保留截距因子 $( I _ { x i } )$ ），可得到RI-CLPM；基于CLPM,在分解方程中删除均值 $( \mu _ { x t } )$ ，而保留截距因子和变化率因子 $( [ I _ { x i } + ( t - 1 ) S _ { x i } ] )$ ，可得到LCM-SR；基于CLPM，在测量方程中保留测量误差 $( \varepsilon _ { x i t } )$ ，在分解方程中删除均值、截距因子和变化率因子 $( [ \mu _ { x t } + I _ { x i } + ( t - 1 ) S _ { x i } ] )$ ，在分解方程中保留恒定变化因子 $( G _ { x i } )$ ，可得到LCS（由于LCS是基于差值的，其自回归系数应为 $\beta _ { x } ^ { \prime } = 1 + \beta _ { x } )$ 。

此外，有学者证明了单变量LCM与LCS存在一定的数理关联，并提供了不同形式下的参数转换公式，例如，对于满足线性增长假设的单变量LCM，其截距 $( I _ { x i }$ ）的均值和方差等于单变量恒定变化LCS 中 $\scriptstyle t = 1$ 时间点的潜在分数 $( f _ { x i ( t = 1 ) } )$ 的均值和方差,其变化率 $( S _ { x i }$ ）的均值和方差则对应LCS中的恒定变化因子（Gxi）的均值和方差，即：μix=μfx(t=1)，μsx =$\mu _ { G _ { x } } , \sigma _ { I x } ^ { 2 } = \sigma _ { f _ { x ( t = 1 ) } } ^ { 2 } , \sigma _ { S x } ^ { 2 } = \sigma _ { G _ { x } } ^ { 2 }$ （Serang et al., 2019）。

尽管各模型在结构上有相似之处，但不同模型之间存在明显差异，这些差异有可能导致分析结果及其解释的迥然不同。表1归纳了文中四种交叉滞后追踪模型的差异，分述如下。

第一，建模对象不同。CLPM是采用中心化变量，即分离出每个时间点的均值（在Mplus中是通过定义潜变量的方式，负荷都固定为1)，RI-CLPM是采用同时分离出均值和特质因子后的变量，LCM-SR 是采用去趋势的变量，即分离出截距因子和变化率因子；LCS 是基于不同时间点之间潜变量的变化值来构建交叉滞后结构。

第二，模型预设轨迹不同。LCM-SR主要用于分析具有线性或非线性发展轨迹的变量，能提供关于变量发展轨迹特征的信息；LCS 可分析满足指数型发展轨迹的变量（Mund&Nestler,2019)；其他两个模型则无法明确提供相关信息。

第三，模型对被试内和被试间效应的分解情况不同。截面设计只能获得被试间效应的数据，而追踪数据可以同时反映被试间差异和被试内过程，区分这两种效应对于理解变量间纵向关系的本质非常重要。CLPM和LCS 没有对被试间差异成分进行建模，也没有区分被试间差异和被试内过程（Curran et al.,2014;Mund& Nestler,2019)，而 RI-CLPM和LCM-SR则分别通过分离特质因子（如 $I _ { x i }$ ）和增长因子（如 $| I _ { x i }$ ， $S _ { x i }$ ）的影响，区分出了被试间差异。如果有足够理由认为在变量的协同发展过程中，被试间差异是不可忽视的，则研究者应选择能够区分被试内和被试间效应的模型，从而获得真实的变量间相互关系。

第四，模型对于追踪数据的时间点个数要求不同。Usami等人（2019）指出，在稳定性假设下（即自回归和交叉滞后系数不随时间变化)，CLPM需要至少两次重复测量，其他交叉滞后模型则需要至少三次。

第五，模型适用的研究情境不同。例如，若其中一个变量本身并不具备系统的变化趋势（如 $y$ 是阅读成绩， $x$ 是一个学年中的缺勤天数)，则不适合采用预设发展轨迹的LCM-SR。

可以看出，尽管不同模型存在一定关联，但各个模型的适用情境不同，所能提供的变量发展信息也有所不同（Parker etal.,2015)，因此，在实际运用中，如果没有明确的理论对模型进行预设，进行模型比较和模型选择是有必要的。

表1各交叉滞后追踪模型的比较  

<html><body><table><tr><td></td><td>建模对象 （特点）</td><td>考虑测量 误差</td><td>交叉滞后 结构</td><td>变量间 历时效应</td><td>预设发展 轨迹</td><td>被试间差异</td><td>被试内过程</td><td>时间点 个数</td><td>适用情境</td></tr><tr><td>CLPM</td><td>各时间点潜变量 （中心化）</td><td>×</td><td>√</td><td>√</td><td>无</td><td>×</td><td>自回归系数、 交叉滞后系数</td><td>≥2</td><td>不存在稳定的被试间差异</td></tr><tr><td>RI-CLPM</td><td>各时间点潜变量 （中心化、分离特质 因子）</td><td>×</td><td>√</td><td>√</td><td>无</td><td>特质因子</td><td>自回归系数、 交叉滞后系数</td><td>≥3</td><td>存在稳定的被试间差异</td></tr><tr><td>LCM-SR</td><td>各时间点潜变量 （去趋势）</td><td>×</td><td>√</td><td>√</td><td>线性 或非线性</td><td>增长因子</td><td>自回归系数、 交叉滞后系数</td><td>≥3</td><td>两个变量均存在系统的时间趋势</td></tr><tr><td>LCS</td><td>各时间点之间 潜变量的变化值 （考虑测量误差）</td><td>√</td><td>√</td><td>√</td><td>指数型</td><td>×</td><td>自回归系数、 交叉滞后系数</td><td>≥3</td><td>探究一个变量的先前水平对于另一个 变量之后的变化量的影响</td></tr></table></body></html>

注：此处特指双变量情况。“”表示存在， $^ { 6 6 } \times \vec { } ^ { , , }$ 表示不存在或无法体现。CLPM：交叉滞后面板模型；RI-CLPM：随机截距交叉滞后面板模型；LCM-SR：结构化残差潜在曲线模型；LCS：潜在变化分数模型，下同。

# 4 实证示例

下面用一个实例来说明不同的交叉滞后追踪模型运用于同一批数据时所得到的分析结果的差异。数据来源于中国家庭追踪调查（China Family Panel Studies,CFPS）的开放数据库。拟探究主观幸福感和身体质量指数（Body Mass Index,BMI）间的纵向关系，主观幸福感由一道问卷题目测量，其要求被试按照1（非常差）到5（非常好）的等级评价自己当前的生活；BMI由被试自我报告或他人代答的身高和体重数据计算：BMI $[ =$ 体重（千克）/身高（厘米）的平方。选取三个时间点（ $_ { \mathrm { T 1 } = 2 0 1 4 }$ ， $_ { \mathrm { T } 2 = 2 0 1 6 }$ ， $_ { \mathrm { T } 3 = 2 0 1 8 }$ )，删除异常值并保留那些在三个时间点都有记录的被试，最终获得来自1525名被试的有效数据，在初始时间点上被试平均年龄为20岁（范围为16-71岁）， $49 \%$ 为男性。

使用 Mplus 8.0 软件分析（见附录)。此处主要目的在于模型比较，因此均采用默认变量间存在纵向相互关系的全模型，且将同一类型的自回归系数、交叉滞后系数设置为不随时间变化。此外，考虑到LCM-SR预设了变化轨迹，先分别对两个变量进行单变量LCM分析，结果表明两个变量都具备系统性的时间趋势： $I$ 主观幸福感=3.80( $_ { p < 0 . 0 0 1 }$ )，S主观幸福感 $_ { = 0 . 0 1 }$ （ $\scriptstyle { p < 0 . 0 5 }$ )，$I _ { \mathrm { B M I } } { = } 2 0 . 8 8$ （ $_ { p < 0 . 0 0 1 }$ )， $S _ { \mathrm { B M I } } { = } 0 . 0 8$ （ $_ { p < 0 . 0 0 1 }$ )，适合用于后续分析。

不同模型的拟合结果见表2。当拟合指数满足以下条件：RMSEA小于0.08，SRMR 小于0.08,CFI大于0.90,TLI大于0.90,可以认为模拟能够较好地拟合数据(温忠麟等,2004)。可以看出，LCM-SR拟合较差，其余模型的整体拟合结果均较好。

表2各交叉滞后追踪模型的拟合情况  

<html><body><table><tr><td></td><td>x</td><td>df</td><td>RMSEA</td><td>SRMR</td><td>CFI</td><td>TLI</td></tr><tr><td>CLPM</td><td>19.68</td><td>6號</td><td>0.04</td><td>0.03</td><td>0.99</td><td>0.99</td></tr><tr><td>LCM-SR</td><td>82.79</td><td>2</td><td>0.16</td><td>0.03</td><td>0.98</td><td>0.83</td></tr><tr><td>RI-CLPM</td><td>34.60</td><td>6號</td><td>0.06</td><td>0.06</td><td>0.99</td><td>0.98</td></tr><tr><td>LCS</td><td>20.79</td><td>7</td><td>0.04</td><td>0.03</td><td>0.99</td><td>0.99</td></tr></table></body></html>

注：RMSEA $\ c =$ Root-mean-square error of approximation； SRMR $\underline { { \underline { { \mathbf { \Pi } } } } } =$ Standard root mean-square residual; CFI= Comparative fit index; ${ \mathrm { T L I } } = ^ { \prime }$ Tucker-Lewis index.

不同模型的参数估计结果见表3。对于同一批追踪数据，各模型提供了不同类型的参数信息。首先，对于变量发展轨迹，LCM-SR的结果表明BMI有显著的线性增长趋势，其截距、变化率均显著，而主观幸福感的变化率因子不显著；其次，对于自回归效应，CLPM 和RI-CLPM都表明两个变量均存在一定的等级稳定性，但各模型所反映的稳定性程度都不同，而LCM-SR仅识别出BMI的等级稳定性，LCS 由于模型较为复杂，部分系数在标准化后出现了不恰当解（Usami etal.,2019)；最后，对于交叉滞后效应，CLPM、RI-CLPM和LCMSR 都识别出了变量间的历时性影响，但所得到的作用方向不同，CLPM的结果表明BMI对主观幸福感有显著的历时性影响，即先前的 BMI正向影响随后的主观幸福感，而RI-CLPM的结果表明先前的主观幸福感对随后的BMI有显著的负向影响，LCM-SR 的结果则表明先前的BMI负向影响随后的主观幸福感。

可以看出，在分析同一批数据时，不同模型所得出的参数结果有一定的差异，这是因为不同模型的构成不同、前提假设也有所差异。一方面，有些模型可能并不适合分析该批数据，例如 LCM-SR 的模型拟合较差，说明该模型可能无法准确反映数据背后的真实变量关系;另一方面，由于各模型的构成不同，参数所反映的效应可能是不同的，例如CLPM被认为混淆了被试间过程和被试内过程，因此其参数结果可能无法真实地反映变量间的相互关系，而 RI-CLPM通过提取出稳定的被试特质因子来分离被试间差异，其估计结果能够更准确地反映变量间的动态相互作用。

表3各交叉滞后追踪模型的参数估计结果  

<html><body><table><tr><td></td><td>CLPM RI-CLPM</td><td>LCM-SR</td><td>LCS</td></tr><tr><td>【主观幸福感</td><td>1</td><td>3.85**</td><td>3.88***</td></tr><tr><td>S主观幸福感</td><td>1</td><td>一 -0.02</td><td>一</td></tr><tr><td>IBMI</td><td>1</td><td>20.71***</td><td>20.71***</td></tr><tr><td>SBMI</td><td>1</td><td>1 0.43***</td><td></td></tr><tr><td>A主观幸福感</td><td></td><td>1</td><td>11.55***</td></tr><tr><td>ABMI</td><td>1</td><td>1 1</td><td>-0.40</td></tr><tr><td>主观幸福感(TI)→主观幸福感 (T2)</td><td>0.65***</td><td>0.15***</td><td>0.12 ×</td></tr><tr><td>主观幸福感 (T2)→主观幸福感(T3)</td><td>0.63*** 0.18***</td><td>0.15</td><td>×</td></tr><tr><td>BMI(T1)→BMI(T2)</td><td>0.88***</td><td>0.52***</td><td>0.68* -0.14</td></tr><tr><td>BMI(T2)→BMI(T3)</td><td>0.90***</td><td>0.60*** 0.61*</td><td>-0.16</td></tr><tr><td>BMI(TI)→主观幸福感 (T2)</td><td>0.08**</td><td>-0.05 -0.37***</td><td>×</td></tr><tr><td>BMI(T2)→主观幸福感(T3)</td><td>0.08**</td><td>-0.07 -0.34***</td><td>×</td></tr><tr><td>主观幸福感(T1)→BMI(T2)</td><td>-0.01</td><td>-0.05** -0.12</td><td>0.23</td></tr><tr><td>主观幸福感 (T2)→BMI(T3)</td><td>-0.01</td><td>-0.06**</td><td>-0.14 0.30</td></tr><tr><td>I主观幸福感←→IBMI</td><td></td><td>0.26**</td><td>1 丨</td></tr></table></body></html>

注：表中路径系数均为标准化后的值，由于模型中的等值限制是对非标准化路径施加的，因此标准化路径系数可能会有不相等的情况;LCS 的路径系数表示一个变量取值对另一个变量的变化量的影响;LCS 较复杂，部分路径系数在标准化后有不恰当解（用“ $\times ^ { , , , }$ 表示)，但整体模型拟合良好，因此仍报告其他可提供有用信息的参数;\*\*\*，\* $p { < } 0 . 0 0 1$ ；\*\*， $p { < } 0 . 0 1$ ；\*， $p { < } 0 . 0 5$ $^ { 6 6 }  ^ { 3 }$ 表示相关.

除了LCM-SR，其余模型拟合都较好，仅根据模拟拟合情况无法确定最终模型，还需要结合模型特点和相关理论背景进行判断。首先，有研究表明主观幸福感和 BMI均存在显著的被试间差异（Bieda et al.,2019; Pereira& Coelho,2013)，所以排除 CLPM；此外，LCM-SR 拟合较差，说明该模型不适合用来反映所论的变量关系；最后，本研究的重点不在于变化量，且LCS 过于复杂导致不恰当解，因此排除LCS。综上，最终选择RI-CLPM并得出结论：在被试间水平上，主观幸福感与 BMI存在显著正向相关 $\stackrel { \prime } { \cdot } r = 0 . 2 6 , p { < } 0 . 0 5 \$ ，即主观幸福感高的被试群体倾向于有较高的 BMI，正所谓心宽体胖；在被试内水平上，两个变量均表现出一定的等级稳定性，主观幸福感的等级稳定性较低（0.15\~0.18)，BMI的等级稳定性较高（2 $( 0 . 5 2 \sim 0 . 6 0 )$ ；两个变量间的历时性影响：先前的BMI负向影响随后的主观幸福感（yBMI-主观幸福感 $\scriptstyle : = - 0 . 0 5 \sim - 0 . 0 7$ ， $p { > } 0 . 0 5 \$ )，但不显著，先前的主观幸福感负向影响随后的 BMI（主观幸福$\Xi { \ s } \to \mathrm { B M I } ^ { = } - 0 . 0 5 \sim - 0 . 0 6$ ， $\scriptstyle { p < 0 . 0 5 } .$ )，但影响微小。

# 5讨论

新兴追踪模型多采用交叉滞后路径来探究变量间的历时性作用，因此各模型的结构相似，但其中的细微差异可能导致分析结果的不同，尤其是在对变量间影响关系的判断上可能给出在统计上很不同的结果，甚至可能得到完全相反的方向，因此必须要选择适当的模型。

研究者需要了解不同追踪模型的适用情境，树立模型比较和模型选择的意识，并逐渐建立追踪研究的流程规范。

首先，在研究设计阶段，要保证足够的被试量和时间点，并注意对测量时间间隔的控制，一般采用等间隔设计，以保证有意义的结果解释。

然后，在数据分析阶段，可根据数据特征（如时间点个数）考虑备选模型，多个模型有助于获得有关变量发展的丰富信息（Parkeretal.,2015）。

最后，通过模型比较作出选择，可从以下几点综合考虑：（1）研究目的，如果研究者的目的在于描述变量的发展轨迹特征，可以选择LCM或LCM-SR，如果目的在于分析变量之间的纵向相互作用机制，可以选择LCM-SR、CLPM、RI-CLPM或LCS；（2）理论背景或经验，如果有证据表明变量存在被试间差异，需要从被试间差异中分离出被试内过程，则LCMSR 或RI-CLPM是较适当的；（3）模型拟合情况，研究者可借助各拟合指数进行模型选择。

基于交叉滞后结构的追踪模型重点关注变量间的历时性作用，可以提供变量发展和变化的多种信息，对于揭示变量间纵向关系具有重要作用，能够为变量间因果关系的论证提供证据。根据实际背景、研究目的和统计结果进行模型比较，有助于建立合适的追踪模型。

本文仅针对双变量追踪模型的全模型形式进行示例，在实际分析中，研究者还可以对全模型进行删减得到单向模型或放宽稳定性假设的限制，也可以纳入时变或非时变的协变量做进一步深入分析。本文所述的几种模型都是在理论和实证研究中得到较多讨论和运用的，此外，还存在其他交叉滞后模型，如因子-交叉滞后面板模型（Factor-CrossLagged PanelModel,factor-CLPM）（McArdle,2009），稳定特质自回归特质状态模型（Stable Trait AutoregressiveTrait and State Model,STARTS）（Kenny& Zautra,2001)，以及多水平交叉滞后模型（Multi-levelCross LaggedModel）（Yuetal.,2015）等，未来可纳入其他交叉滞后模型进行更系统的比较。

#

奓兮乂默   
温忠麟，侯杰泰，马什赫伯特.(2004).结构方程模型检验：拟合指数与卡方准则．心理学报， 36(2),186-194.   
温忠麟.(2017).实证研究中的因果推理与分析．心理科学,40(1),200-208.   
Bieda,A.， Hirschfeld,G.， Schonfeld, P.，Brailovskaia, J.，Lin，M. Y.,& Margraf,J. (2019). Happiness, life satisfaction and positive mental health: Investigating reciprocal effects over four years in a Chinese student sample. Journal of Research in Personality, 78,198-209.   
Cole,D.A., & Maxwell, S. E. (2003). Testing mediational models with longitudinal data: Questions and tips in the use of structural equation modeling. Journal of Abnormal Psychology, 112(4), 558- 577.   
Curran, P. J., Howard,A. L.,Bainter, S. A.,Lane, S.T., & McGinley, J. S. (2014). The separation of between-person and within-person components of individual change over time: Alatent curve model with structured residuals. Journal of Consulting and Clinical Psychology, 82(5), 879-894. Curran, P. J., Obeidat, K., & Losardo, D. (2010). Twelve frequently asked questions about growth curve modeling. Journal of Cognition and Development, 11(2), 121-136.   
Hamaker, E. L., Kuiper, R. M.,& Grasman, R. P.P.P. (2015). A critique of the cross-lagged panel model. Psychological Methods, 20(1),102-116.   
Joreskog, K. G. (1970). A general method for analysis of covariance structures. Biometrika, 57(2), 239-251.   
Kenny, D.A., & Zautra,A. (2001). Trait-state models for longitudinal data. In L. M. Collins & A. G. Sayer (Eds.)， Decade of behavior: New methods for the analysis of change (pp. 243-263). American Psychological Association.   
McArdle, J. J. (2o09). Latent variable modeling of diffrences and changes with longitudinal data. Annual Review of Psychology, 60, 577-605.   
McArdle, J. J., & Hamagami, F. (2Oo1). Latent difference score structural models for linear dynamic analyses with incomplete longitudinal data. In L. M. Collins & A. G. Sayer (Eds.), New methods for the analysis of change (pp. 137-175). American Psychological Association.   
Meredith, W., & Tisak, J. (1990).Latent curve analysis. Psychometrika, 55(1), 107-122.   
Mund, M., & Nestler, S. (2019). Beyond the cros-lagged panel model: Next-generation statistical tools for analyzing interdependencies across the life course. Advances in Life Course Research, 41, 1

100249.

Parker, P.D., Marsh, H. W., Morin,A. J. S., Seaton, M.,& van Zanden, B. (2015). If one goes up the other must come down: Examining ipsative relationships between Math and English selfconcept trajectories across high school. British Journal ofEducational Psychology, 85(2),172-191. Pereira, M. C., & Coelho, F. (2013). Untangling the relationship between income and subjective well-being: The role of perceived income adequacy and borrowing constraints. Journal of Happiness Studies, 14(3), 985-1005.   
Serang, S., Grimm, K. J.,& Zhang, Z. Y. (2019). On the correspondence between the latent growth curve and latent change score models. Structural Equation Modeling: A Multidisciplinary Journal, 26(4), 623-635.   
Usami,S., Hayes,T.,& McArdle,J.J. (2015). On the mathematical relationship between latent change score and autoregressive cross-lagged factor approaches: Cautions for inferring causal relationship between variables.Multivariate Behavioral Research, 50(6), 676-687.   
Usami, S., Murayama, K., & Hamaker, E.L. (2019). A unified framework of longitudinal models to examine reciprocal relations. Psychological Methods,24(5), 637-657.   
Wiedermann, W., & von Eye,A. (2020). Reciprocal relations in categorical variables. Psychological Methods, 25(6), 708-725.   
Yu, G., Sessions, J. G., Fu, Y., & Wall, M. (2015). A multilevel cross-lagged structural equation analysis for reciprocal relationship between social capital and health. Social Science and Medicine, 142,1-8.

# 附录

Mplus 语句   
Data: FILE $\mathbf { \Sigma } =$ 1.dat;   
Variable:   
names $= \mathbf { x } 1 \mathbf { x } 2 \mathbf { x } 3$ yl y2 y3;   
Analysis:   
ESTIMATOR=ML;   
!CLPM   
model:   
！ define latent variables   
etax1 by x1@1;etax2 by $\mathbf { x } 2 @$ 1;etax3 by $\mathbf { x } 3 @ 1$ etay1 by yl $@$ 1;etay2 by $\mathrm { y } 2 @ 1$ ;etay3 by $\mathrm { y } 3 @ 1$ ， ! autoregressions   
etax2 on etax1 (al);etax3 on etax2 (a1);   
etay2 on etayl (a2); etay3 on etay2 (a2);   
! crosslagged paths   
etay2 on etax1 (c1);etay3 on etax2 (c1);   
etax2 on etayl (c2);etax3 on etay2 (c2);   
！variance structure   
etaxl;etayl;etaxl with etayl;   
etax2-etax3 (e1);etay2-etay3 (e2);   
etax2 with etay2 (cove);etax3 with etay3 (cove); x1-x3;y1-y3;   
! mean structure   
[etax1-etax3];[etay1-etay3];   
[x1-x3@0]; [y1-y3@0];

# !RI-CLPM

model:   
ix by $\mathbf { x } 1 @ 1 \mathbf { x } 2 @ 1 \mathbf { x } 3 @ 1$   
iy by y $1 \textcircled { \omega } 1 \ : \mathrm { y } 2 \textcircled { \omega } 1 \ : \mathrm { y } 3 \textcircled { \omega } 1$   
etax1 by x1 $@$ 1;etax2 by $\mathbf { x } 2 @ 1$ ;etax3 by $\mathbf { x } 3 \textcircled { a } 1$   
etay1 by yl $@$ 1;etay2 by $\mathrm { y } 2 @ 1$ ;etay3 by $\mathbf { y } 3 @ 1$ ： etax2 on etaxl (al);etax3 on etax2 (al);   
etay2 on etayl (a2);etay3 on etay2 (a2);   
etay2 on etaxl (c1);etay3 on etax2 (c1);   
etax2 on etayl (c2);etax3 on etay2 (c2);   
$\mathbf { x } 1 - \mathbf { x } 3 @ 0 ; \mathbf { y } 1 - \mathbf { y } 3 @ 0 ;$   
etax1-etax3;etay1-etay3;   
ix; iy; ix with iy;   
etax1 with ix $@ 0$ ; etayl with ix $@ 0$   
etax1 with iy $@ 0$ ; etayl with iy $@ 0$ ; etaxl with etayl etax2 with etay2 (e1); etax3 with etay3 (e2); $[ \mathbf { x } 1 - \mathbf { x } 3 @ 0 ]$ ; [y1-y3@0];   
[etax1-etax3 $@ 0 ]$ ; [etay1-etay3 $@ 0 ]$   
[ix iy]; !LCM   
Model:   
il s1 $| \times 1 @ 0 \times 2 @ 1 \times 3 @ 8 \$ · $\mathrm { i } 2 \mathrm { s } 2 | \mathrm { y } 1 @ 0 \mathrm { y } 2 @ 1 \mathrm { y } 3 @ 2$ s1 with i2; s2 with il;

# !LCM-SR

model:   
ix by $\mathbf { x } 1 @ 1 \mathbf { x } 2 @ 1 \mathbf { x } 3 @ 1$ ; sx by $\times 1 \textcircled { \omega } 0 \times 2 \textcircled { \omega } 1 \times 3 \textcircled { \omega } 2$   
iyby yl $@ 1 \ : \mathrm { y } 2 @ 1$ y3 $@ 1$ ; sy by yl $\textcircled { a } 0 \ y 2 @ 1 \ y 3 \textcircled { a } 2$ ：   
etax1 by $\mathbf { x } 1 @ 1$ ; etax2 by $\mathbf { x } 2 @ 1$ ; etax3 by $\mathbf { x } 3 @ 1$ ：，   
etay1 by yl $@ 1$ ; etay2 by $\mathrm { y } 2 @ 1$ ; etay3 by $\mathrm { y } 3 @ 1$ ，   
etax2 on etaxl (a1); etax3 on etax2 (a1);   
etay2 on etayl (a2); etay3 on etay2 (a2);   
etay2 on etax1 (c1); etay3 on etax2(c1); etax2 on etayl (c2); etax3 on etay2 (c2); $\mathbf { x } 1 - \mathbf { x } 3 \textcircled { a } 0$ ;y1-y3 $@ 0$ ; etax1-etax3; etay1-etay3;   
etax1 with etayl;   
etax2 with etay2 (e1); etax3 with etay3 (e1);   
ix; iy; sx; sy;   
ix with sx iy sy; sx with iy sy; iy with sy;   
etax1 with ix $@ 0$ ; etax1 with sx $@ 0$ ; etax1 with iy $@$ ； etax1 with sy $@ 0$   
etay1 with ix $@ 0$ ; etayl with sx $@ 0$ ; etayl with iy $@$ ; etayl with sy $@ 0$   
$[ \mathbf { x } 1 - \mathbf { x } 3 @ 0 ]$ ；[y1-y3 $@ 0 ]$ ，   
[etax1-etax3 $@ 0 ]$ ; [etay1-etay3 $@ 0 ]$ ; [ix iy]; [sx sy];

# !LCS

model:   
etax1 by $\mathbf { x } 1 @ 1$ ; etax2 by $\mathbf { x } 2 @ 1$ ; etax3 by $\mathbf { x } 3 @ 1$   
etayl by yl $@ 1$ ; etay2 by $\mathrm { y } 2 @ 1$ ; etay3 by $\mathrm { y } 3 @ 1$ ·   
dx2 by etax2 $@ 1$ ; dx3 by etax3 $@ 1$ ; dy2 by etay2 $@ 1$ ; dy3 by etay3 $@ 1$ · gx by $\mathrm { d } \mathbf { x } 2 \mathbf { - } \mathrm { d } \mathbf { x } 3 @ 1$ ; gy by dy2-dy3 $@ 1$ ，   
etax2 on etaxl $@$ 1;etax3 on etax2 $@ 1$   
etay2 on etayl $@$ 1;etay3 on etay2 $@ 1$ ·   
dx2 on etax1 (p1); dx3 on etax2 (p1);   
dy2 on etayl (p2); dy3 on etay2 (p2);   
dy2 on etax1 (c1); dy3 on etax2 (c1);   
dx2 on etayl (c2); dx3 on etay2 (c2);   
x1-x3 (ux); yl-y3 (uy); etax2-etax3@0;etay2-etay3 $@ 0$   
dx2-dx3@0; dy2-dy3 $@ 0$   
etax1; etay1;   
gx;gy;   
etax1 with etayl;   
gx with etaxl; gx with etayl;   
gy with etaxl; gy with etayl;   
gx with gy;   
[x1-x3@0]; [y1-y3@0];   
[etax2-etax3 $@ 0 ]$ ; [etay2-etay3 $@ 0 ]$ [dx2-dx3@0]; [dy2-dy3 $@ 0 ]$   
[etax1 etay1];   
[gx gy];   
OUTPUT: STDYX;

# Exploring the longitudinal relations: Based on longitudinal models with cross-lagged structure

Fang Junyan ’,Wen Zhonglin ²,Huang Guomin 3 (l School of Psychology,South China Normal University, Guangzhou,510631) ( CenterforStudiesofPsychologicalAplication/SchoolofPsychology,South China Normal University,Guangzhou,50631) ( School of Psychology, South China Normal University, Guangzhou,510631)

AbstractAcross-lagged structureusuallyconsists of twokinds ofefcts,autoregressive effects of the priorlevel ofa variable on the current levelof itself and cros-lagged effects of the prior levelofone variableon the current level of another variable.Longitudinal models with the cross-lagged structure are well recognized as powerful techniques for revealing longitudinal relations between two variables and laying the foundation of diachronic causation.There existseveral cross-lagged longitudinal models,while practitioners know litleabout theassociation and difference among them, which makes it difficult to choose the most proper one.Although these models are similar in structure, they may difer in theresults of estimation.Thus,it is necessary to get a whole picture of these longitudinal models and learn how to compareand choose among them.The present study aims toanalyze diferent cross-lagged longitudinal models and compare them,soas to reveal the importance ofmodel comparison and model selection and provide strategies to select among models.

First,we introduce four popular longitudinal models with cross-lagged structure: Cross-Lagged Panel Model (CLPM), Random-Intercept Cross-Lagged Panel Model (RI-CLPM),Latent Curve Model with Structured Residuals (LCM-SR),and Latent Change Score Model (LCS).Then, we clarify the similarities and associations among them. Next,we discuss their diferences in various aspects.Finally,we conduct an empirical study to ilustrate the procedure of model selection.

Results show that: (1) these models are very similar in the model configuration because they all analyze diachronic relations by the cross-lagged structure; (2) CLPMcan transform into RI-CLPM,LCM-SR and LCS under certain conditions;(3）diferent models focus on different developmental characteristics and each of them can provide valuable information on the change process; (4) these models could give diferent estimation results when applied to the same data set,which may induce different conclusions.

We summarize several reference points for selecting a proper longitudinal model in practice: (l） research purpose.If researchers are interested in characterizing the development trajectories,then LCMor LCM-SR is preferred; (2)theoretical knowledge and empirical experience.Ifthere is sufficient evidence showing thatthe withinperson process should be separated from between-person difference，then LCM-SR and RI-CLPM could be considered; (3) the model fitting. Several model fit indices can be used.

In summary,longitudinal models with cross-lagged structure play an important role in revealing longitudinal relations between psychological constructs.These models are similarinconfiguration but vary in modeling basis, premises and data requirements, which may give rise to distinct estimation results and conclusions.Researchers should understandthe association and diffrencesamong them with considerable insight into modelcomparison and modelselection.Itis advisable to trydifferentreasonable models and choose the most properone fortheexploration of longitudinal relations.

eywordslongitudinal relation, cross-lagged,longitudinal model,model selectiol