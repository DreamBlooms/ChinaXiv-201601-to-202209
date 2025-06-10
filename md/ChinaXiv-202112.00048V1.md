# 基于两水平回归模型的调节效应分析及其效应量

方杰温忠麟²(广东财经大学广东经济与社会发展研究院/应用心理学系，广州510320)(华南师范大学心理学院/心理应用研究中心，广州510631)

摘要使用多元回归法进行调节效应分析在社科领域已常有应用。简述了目前多元回归法的调节效应分析存在的不足，包括人为变换检验模型、自变量和调节变量区分不足、误差方差齐性的假设难以满足、调节效应量指标 $\varDelta R ^ { 2 }$ 没有直接测量调节变量对自变量与因变量关系的调节程度。比较好的方法是用两水平回归模型进行调节效应分析并使用相应的效应量指标。在介绍新方法和新效应量后，总结出一套调节效应的分析流程，通过一个例子来演示如何用Mplus软件进行两水平回归模型的调节效应及其效应量分析。最后讨论了两水平回归模型的调节效应分析的发展，包括稳健的调节效应分析、潜变量的调节效应分析、有调节的中介效应分析和有中介的调节效应分析等。

关键词 调节效应，两水平回归模型，多元回归法，效应量

# 1引言

调节变量（moderator）在心理、教育、社会和管理等研究中扮演着重要的角色。如果自变量 $X$ 与因变量Y的关系受到第三个变量Z的影响，则变量Z 就是调节变量。此时， $X$ 与 $Y$ 的关系是调节变量 $Z$ 的函数，三者的关系可以用图1(a)的调节效应模型来表示。目前调节效应分析常用多元回归法（温忠麟等，2005；方杰等，2015)，但多元回归法的调节效应分析及其效应量指标 $\varDelta R ^ { 2 }$ 仍存在不足之处。Yuan 等（2014）提出两水平回归模型（two-levelregressionmodel）进行调节效应分析并引入新的调节效应量指标。本文将深入讨论两水平回归模型的调节效应分析及其效应量。在简介多元回归法的调节效应分析及其效应量指标$R ^ { 2 }$ 后，讨论了多元回归法和效应量 $\varDelta R ^ { 2 }$ 的不足，接着详述了如何利用两水平回归模型进行调节效应分析并引入了与此模型相应的新效应量指标，然后总结出一套调节效应的分析流程。随后用示例演示如何用Mplus 软件进行两水平回归模型的调节效应及其效应量分析，最后讨论了两水平回归模型的调节效应分析的发展。

![](images/443bc1a01059b4381fb5fb074b3b713dc9cad5c17adcb1f1ffae3442f2839e33.jpg)  
图1调节效应模型图(改编自方杰等,2015)

# 2多元回归法的调节效应分析及其传统效应量

常见调节效应可以通过下面回归方程进行分析(图 $1 ( b )$ 是相应的路径图)，

$$
Y = \beta _ { \mathrm { 0 } } + \beta _ { \mathrm { 1 } } X + \beta _ { \mathrm { 2 } } Z + \beta _ { \mathrm { 3 } } X Z + e
$$

$\beta _ { \mathfrak { o } }$ 为截距项， $\beta _ { \mathfrak { r } }$ 为当 $\scriptstyle { Z = 0 }$ 时自变量 $X$ 对因变量 $Y$ 的效应， $\beta _ { { } _ { 2 } }$ 为当 $\scriptstyle { X = 0 }$ 时调节变量 $Z$ 对因变量Y的效应，假设误差项 $e$ 服从正态分布。如果系数 $\beta _ { 3 }$ 的估计值经统计检验显著，则表明调节变量 $Z$ 对自变量 $X$ 与因变量 $Y$ 的关系具有调节作用。调节效应量用 $\Delta R ^ { 2 } = R _ { 2 } ^ { 2 } - R _ { 1 } ^ { 2 }$ 估计，其中 $R _ { 2 } ^ { 2 }$ 表示回归方程（1）的测定系数， $R _ { 1 } ^ { 2 }$ 表示回归方程（1）去掉乘积项 $X Z$ 后的测定系数（温忠麟等，2005,2020；方杰等，2015）。

目前，多元回归法被广泛应用于调节效应分析。但该方法仍存在诸多不足（Yuan et al.,2014)。第一、多元回归法将图 $1 ( a )$ 的调节效应（moderation）模型人为的变换成 $1 ( b )$ 的交互效应（interaction）模型，并通过最小二乘法来估计此模型。这种做法其实是检验Z与X的交互效应是否显著，并没有直接对图1(a)的调节效应模型进行检验。第二、自变量和调节变量的作用在方程（1）中难以区分。使用多元回归法，调节作用具有对称性。也就是说，如果X对Y的效应受到Z的调节（此时X是自变量)，那么Z对Y的效应同样也受到X的调节（此时X是调节变量)，且两种调节效应的分析结果相同（Hayes&Montoya,2017)。第三、误差方差齐性的假设难以满足。多元回归法假设误差方差齐性（即当自变量X取不同的值 $x _ { i }$ 时，误差方差相等），回归系数显著性的检验也基于这一假设。然而，方程（1）很难满足误差方差齐性的前提假设。因为当自变量X取某值 $x _ { i }$ 时，方程（1）的误差方差为

$$
V a r ( e \mid X = x _ { i } ) = V a r ( Y ) - ( \beta _ { 2 } + \beta _ { 3 } x _ { i } ) ^ { 2 } V a r ( Z ) ,
$$

只有当 $\beta _ { 3 } ^ { \quad } = 0$ 时，误差的方差才相等（与 $x _ { i }$ 的取值无关）（刘红云等,2021）。Aguinis等（1999）发现，大约 $5 0 \%$ 的文章在使用多元回归分析时都明显不满足误差方差齐性的假设，此时会导致系数 $\beta _ { 3 }$ 的参数估计的标准误有偏差，从而导致调节效应分析的检验力（power）下降、效应量估计也出现偏差（刘红云等,2021）。第四、调节效应量指标 $\triangle R ^ { 2 }$ 存在不足。 $\triangle R ^ { 2 }$ 并没有直接测量调节变量Z对 $\cdot X ^ {  }$ Y关系的调节程度， $\triangle R ^ { 2 }$ 反映的是乘积项XZ对因变量Y的方差的额外解释力（Liu&Yuan,in press）。温忠麟和叶宝娟（2014）认为 $\triangle R ^ { 2 }$ 变化要超过 $2 \%$ （甚至 $3 \%$ )才有实质性意义，但 $\triangle R ^ { 2 }$ 的数值往往很小（Aguinis et al.,2005; Liu& Yuan, in press）。

# 3两水平回归模型的调节效应分析及其效应量

# 3.1两水平回归模型的调节效应分析

两水平回归模型的调节效应分析(图2)可表示为(Yuanetal.,2014):

水平1：Y=β+βX+ei

水平2:βi=Yoo+YoZ+εi0

$$
\beta _ { _ { i 1 } } = \gamma _ { _ { 1 0 } } + \gamma _ { _ { 1 1 } } Z _ { _ { i } } + \varepsilon _ { _ { i 1 } }
$$

其中 $\beta _ { i 0 }$ 和 $\beta _ { { } _ { i 1 } }$ 是随机系数，即系数大小随个体 $i$ 的变化而变化， $\gamma _ { _ { 0 0 } } \setminus \gamma _ { _ { 0 1 } } \setminus \gamma _ { _ { 1 0 } }$ 和 $\gamma _ { _ { 1 1 } }$ 为固定系数，即系数大小不随个体 $i$ 的变化而变化。 $e _ { i }$ 、 $\varepsilon _ { i 0 }$ 和 $\varepsilon _ { i 1 }$ 都服从均值为0的正态分布。具体地，e\~N(0,σ²), $\binom { \pmb { \varepsilon } _ { i 0 } } { \pmb { \varepsilon } _ { i 1 } } \sim N ( \pmb { 0 } , \left( \begin{array} { l l } { \sigma _ { 0 } ^ { 2 } } & { \sigma _ { 0 1 } ^ { 2 } } \\ { \sigma _ { 0 1 } ^ { 2 } } & { \sigma _ { 1 } ^ { 2 } } \end{array} \right) )$ ，水平1的误差 $e _ { i }$ 和水平2误差( $\cdot \varepsilon _ { i 0 }$ 和 $\varepsilon _ { i 1 }$ )相互独立，但 $\varepsilon _ { i 0 }$ 和 $\varepsilon _ { i 1 }$ 有可能相关(误差的协方差 $C o \nu ( \varepsilon _ { i 0 } , \varepsilon _ { i 1 } )$ 用 $\sigma _ { 0 1 } ^ { 2 }$ 表示)，自变量 $X _ { i }$ 和调节变量 $Z _ { i }$ 有可能相关(图2中用虚线表示)。将方程 $( 3 a )$ 和 $( 3 b )$ 带入方程(2)，得：

$$
Y _ { i } = \gamma _ { _ { 0 0 } } + \gamma _ { _ { 0 1 } } Z _ { i } + \gamma _ { _ { 1 0 } } X _ { i } + \gamma _ { _ { 1 1 } } Z _ { i } X _ { i } + \varepsilon _ { _ { i 1 } } X _ { i } + \varepsilon _ { _ { i 0 } } + e _ { _ { i } }
$$

如果乘积项 $Z _ { _ i } X _ { _ i }$ 的系数 $\gamma _ { 1 1 }$ 显著不为 $0$ ，表示 $Z _ { i }$ 对 $X _ { i }$ 和因变量 $Y _ { i }$ 关系的调节效应显著。需要说明的是，由于方程(2)-(4)都只有下标 $i$ ，因此两水平回归模型实际上是对单水平数据(个体水平)进行调节分析。也正因为实际数据不是嵌套的两水平数据，所以两水平回归模型分析无法从 $\ \varepsilon _ { i 0 }$ 中区分出 $e _ { i }$ ，也就无法区分 $\sigma _ { 0 } ^ { 2 }$ 和 $\sigma _ { e } ^ { 2 }$ ，因此令 $\sigma _ { 0 e } ^ { 2 } = \sigma _ { 0 } ^ { 2 } + \sigma _ { e } ^ { 2 }$ 。

![](images/b7cf02fc1113ec572859120f9868aaec049545b42525414080dff3078847f4cd.jpg)  
图2两水平回归模型的调节效应图(改编自Yang&Yuan,2016)

两水平回归模型用两水平的结构对单水平数据进行调节效应分析存在明显的优势。第一、两水平回归模型（方程(2)-(4)，图2）中，调节变量 $Z _ { i }$ 直接解释了自变量 $X _ { i }$ 和因变量 $Y _ { i }$ 的关系（即 $\beta _ { i 0 }$ 和 $\beta _ { i 1 }$ ），解决了多元线性回归的第一个不足。第二、两水平回归模型能清楚地区分自变量 $X _ { i }$ 和调节变量 $Z _ { i }$ 的作用，自变量 $X$ 在层1方程中，作用是解释因变量 $Y _ { i }$ 的方差；调节变量 $Z _ { i }$ 却只能在层2方程中，作用是解释层1截距 $\beta _ { i 0 }$ 和斜率 $\beta _ { i 1 }$ 的方差。自变量 $X _ { i }$ （204号和调节变量 $Z _ { i }$ 是不可互换的，它们各自承担着不同的作用。解决了多元线性回归的第二个不足。第三、两水平回归模型不需要误差方差齐性的假设，可以在误差方差是异方差的情况下进行调节效应分析。因为，两水平回归模型(方程(4))的误差方差

$$
\begin{array} { r } { V a r ( e _ { i } + \varepsilon _ { i 0 } + \varepsilon _ { i 1 } X _ { i } ) = X _ { i } ^ { 2 } \sigma _ { 1 } ^ { 2 } + 2 X _ { i } \sigma _ { 0 1 } + \sigma _ { 0 } ^ { 2 } + \sigma _ { e } ^ { 2 } = X _ { i } ^ { 2 } \sigma _ { 1 } ^ { 2 } + 2 X _ { i } \sigma _ { 0 1 } + \sigma _ { 0 e } ^ { 2 } } \end{array}
$$

会随自变量 $X _ { i }$ 的变化而变化，即两水平回归模型的误差方差本就是异方差的(Yuan et al,2014)。Yuan 等(2014)的模拟研究也发现，当误差方差齐性的假设不成立(即误差方差是异方差)时，相比多元回归法，两水平回归模型的调节效应分析可以提供更准确的参数估计。Yuan等(2014)的模拟研究还发现，当误差方差齐性的假设成立时，两水平回归模型与多元回归法的参数估计基本相同。这是因为当 $\varepsilon _ { i 1 } = 0$ 时，基于多元回归法的调节效应模型(方程(1))可看成是两水平回归模型(方程(4))的特例(Liu&Yuan,in press)。

# 3.2调节效应的效应量

# 3.2.1效应量指标： R

Yuan 等（2014）提出，两水平回归模型的调节效应的效应量(effect size)指标为

$$
R _ { \beta _ { i 1 } } ^ { 2 } = \frac { \hat { V } a r ( \gamma _ { \mathrm { 1 0 } } + \gamma _ { \mathrm { 1 1 } } Z _ { i } ) } { \hat { V } a r ( \beta _ { i 1 } ) } = \frac { \hat { \gamma } _ { 1 1 } ^ { 2 } V a r ( Z _ { i } ) } { \hat { \gamma } _ { 1 1 } ^ { 2 } V a r ( Z _ { i } ) + \hat { \sigma } _ { 1 } ^ { 2 } } \ ,
$$

其中 $V a r ( Z _ { i } )$ 为调节变量 $Z _ { i }$ 的样本方差， $\hat { \gamma } _ { 1 1 }$ 和 $\hat { \sigma } _ { 1 } ^ { 2 }$ 为 $\gamma _ { 1 1 }$ 和 $\sigma _ { 1 } ^ { 2 }$ 的估计值。 $R _ { \beta _ { i 1 } } ^ { 2 }$ 的值即为 $\beta _ { i 1 }$ 的方差中可被调节变量 $Z _ { i }$ 解释的部分，而 $\beta _ { i 1 }$ 是因变量 $Y _ { i }$ 对自变量 $X _ { i }$ 的回归系数，所以 $R _ { \beta _ { i 1 } } ^ { 2 }$ 代表了调节变量 $Z _ { i }$ 对 $X _ { i }$ 与 $Y _ { i }$ 关系的调节程度。因此，用 $R _ { \beta _ { i 1 } } ^ { 2 }$ 作为调节效应的效应量指标更符合图 $1 ( a )$ 中调节效应的定义。大多数情况下， $R _ { \beta _ { i 1 } } ^ { 2 }$ 会比多元回归法得到的调节效应的效应量$\triangle R ^ { 2 }$ 大，因为 $R _ { \beta _ { i 1 } } ^ { 2 }$ 表示的是 $\beta _ { i 1 }$ 的方差被解释了多少，而 $\triangle R ^ { 2 }$ 表示的是因变量 $Y$ 的方差被解释了多少， $\beta _ { i 1 }$ 的方差一般都小于因变量 $Y$ 的方差（Liu&Yuan,in press）。此外， $R _ { \beta _ { i 1 } } ^ { 2 }$ 的取值范围是 $[ 0 , 1 ]$ 。具体地， $R _ { \beta _ { i 1 } } ^ { 2 } = 1$ 表示 $\beta _ { i 1 }$ 的变化完全是由 $Z _ { i }$ 的变化引起的，即完全调节；0< $R _ { \beta _ { i 1 } } ^ { 2 } ~ < 1$ ，表示 $\beta _ { i 1 }$ 的变化部分是由 $Z _ { i }$ 的变化引起的，即部分调节； $R _ { \beta _ { i 1 } } ^ { 2 } ~ = 0$ 表示变量 $Z _ { i }$ 没有任何调节作用（Yang＆Yuan，2016）。综上可知， $R _ { \beta _ { i 1 } } ^ { 2 }$ 作为调节效应量的指标相比 $\triangle R ^ { 2 }$ 更为合适，解决了多元回归法的第四个不足。

# 3.2.2效应量指标 $\Delta R _ { m o } ^ { 2 }$ 和 $\textstyle V R ^ { 2 }$ 系列

Liu 和 Yuan（in press）指出 $R _ { \beta _ { i 1 } } ^ { 2 }$ 仍然存在不足。 $R _ { \beta _ { i 1 } } ^ { 2 }$ 表示 $\beta _ { i 1 }$ 的方差中可被调节变量 $Z _ { i }$ 解释的部分，而不是 $Y$ 的方差被自变量 $X$ 解释的部分（ $V a r ( \beta _ { i 1 } X _ { i } )$ ）中可被调节变量 $Z _ { i }$ 解释的部分。为此，他们提出了几种新的调节效应量指标。

第一种是

$$
\Delta R _ { _ { m o } } ^ { 2 } = \frac { R _ { _ { 2 } } ^ { 2 } - R _ { _ { 1 } } ^ { 2 } } { R _ { _ { 2 } } ^ { 2 } - R _ { _ { 0 } } ^ { 2 } } \ ,
$$

其中 $R _ { 0 } ^ { 2 }$ 表示方程 $Y _ { i } = \gamma _ { 0 0 } + \gamma _ { 0 1 } Z _ { i } + \sigma _ { 0 e } ^ { 2 }$ 的测定系数，即 $Y _ { i }$ 的方差能被 $Z _ { i }$ 解释的比例。 $R _ { 1 } ^ { 2 }$ 表示方程 $Y _ { i } = \gamma _ { 0 0 } + \gamma _ { 0 1 } Z _ { i } + \gamma _ { 1 0 } X _ { i } + \varepsilon _ { i 1 } X _ { i } + \sigma _ { 0 e } ^ { 2 }$ 的测定系数，即 $Y _ { i }$ 的方差能被 $X _ { i }$ 和 $Z _ { i }$ 共同解释的比例。 $R _ { 2 } ^ { 2 }$ 表示方程（4）的测定系数，即 $Y _ { i }$ 的方差能被 $X _ { i }$ 、 $Z _ { i }$ 和 $Z _ { i } X _ { i }$ 共同解释的比例。 $\Delta R _ { m o } ^ { 2 }$ 表示 $Z _ { i } X _ { i }$ 独特解释的 $Y _ { i }$ 的方差（排除 $X _ { i }$ 和 $Z _ { i }$ 的影响)在 $X _ { i }$ 和 $Z _ { i } X _ { i }$ 共同解释的 $Y _ { i }$ 的方差（排除 $Z _ { i }$ 的影响）中所占的比例。 $\Delta R _ { m o } ^ { 2 }$ 的取值范围是[0,1]。

第二种是所谓的 $\textstyle V R ^ { 2 }$ 效应量指标，包括

$$
\begin{array} { l c l } { { V R _ { \mathrm { 1 } } ^ { 2 } = \displaystyle \frac { V \mathrm { a r } ( \gamma _ { \mathrm { _ 1 I } } Z _ { i } X _ { i } ) } { V a r ( \beta _ { i 1 } X _ { i } ) } { = } \displaystyle \frac { \gamma _ { \mathrm { _ 1 I } } ^ { 2 } V a r ( Z _ { i } X _ { i } ) } { V a r [ ( \gamma _ { \mathrm { _ 1 0 } } + \gamma _ { \mathrm { _ 1 I } } Z _ { i } + \varepsilon _ { \mathrm { _ i 1 } } ) X _ { i } ] } } } \\ { { V R _ { \mathrm { 2 } } ^ { 2 } { = } \displaystyle \frac { \gamma _ { \mathrm { _ 1 I } } ^ { 2 } V a r ( Z _ { i } X _ { i } ) } { V a r [ ( \gamma _ { \mathrm { _ 1 0 } } + \gamma _ { \mathrm { _ 1 I } } Z _ { i } ) X _ { i } ] } } } \end{array}
$$

这三个指标的分子都一样，表示 $Z _ { i } X _ { i }$ 解释的 $Y _ { i }$ 的方差，但分母不同。 $V R _ { 2 } ^ { 2 }$ 和 $V R _ { 3 } ^ { 2 }$ 的分母是 $V R _ { 1 } ^ { 2 }$ 的分母的一部分，所以 $V R _ { 2 } ^ { 2 }$ 和 $V R _ { 3 } ^ { 2 }$ 的值都大于 $V R _ { 1 } ^ { 2 }$ 。 $V R _ { 1 } ^ { 2 }$ 表示 $Z _ { i } X _ { i }$ 解释的 $Y$ 的方差在与 $X _ { i }$ 有关的 $Y$ 的方差中所占的比例。 $V R _ { 2 } ^ { 2 }$ 表示 $Z _ { i } X _ { i }$ 解释的 $Y _ { i }$ 的方差在 $X _ { i }$ 能解释的 $Y _ { i }$ 的方差中所占的比例。 $V R _ { 3 } ^ { 2 }$ 表示 $Z _ { i } X _ { i }$ 解释的 $Y _ { i }$ 的方差在 $Z _ { i } X _ { i }$ 解释的 $Y$ 的方差和 $X _ { i }$ 不能解释的 $Y _ { i }$ 的方差之和中所占的比例， $V R _ { 3 } ^ { 2 }$ 类似于方差分析的效应量 $\eta _ { p } ^ { 2 }$ 。 $V R _ { 3 } ^ { 2 }$ 的取值范围是[0,1]，但 $V R _ { 1 } ^ { 2 }$ 和 $V R _ { 2 } ^ { 2 }$ 有可能大于1，此时建议更换其他效应量指标或者将自变量 $X$ 和调节变量 $Z$ 都中心化后再进行调节效应检验和效应量计算。

# 3.2.3效应量的讨论

效应量应具有与测量单位无关、不受样本容量影响和单调性的性质，多元回归法的调节效应量指标 $\triangle R ^ { 2 }$ 就同时具有上述三个性质（温忠麟等,2016）。 $\Delta R _ { m o } ^ { 2 }$ 具有与测量单位无关和不受样本容量影响的性质，但 $\Delta R _ { m o } ^ { 2 }$ 是以分母 $R _ { 2 } ^ { 2 } - R _ { 0 } ^ { 2 }$ 为条件的系数 $\gamma _ { _ { 1 1 } }$ 的单调函数（Liu &Yuan,in press）。当自变量 $X$ 和调节变量 $Z$ 都中心化后， $V R _ { 1 } ^ { 2 }$ 、 $V R _ { 2 } ^ { 2 }$ 和 $V R _ { 3 } ^ { 2 }$ 才具有与测量单位无关和不受样本容量影响的性质，但Liu 和Yuan 并没有讨论 $V R _ { 1 } ^ { 2 }$ 、 $V R _ { 2 } ^ { 2 }$ 和 $V R _ { 3 } ^ { 2 }$ 是否具有单调性。因为保持 $\mathbf { \Delta } _ { a }$ 和 $b$ 不变， $a ^ { 2 } x ^ { 2 } / ( a ^ { 2 } x ^ { 2 } + b ^ { 2 } )$ 是 $x ^ { 2 }$ 的单调函数，所以 $V R _ { 1 } ^ { 2 }$ 、 $V R _ { 2 } ^ { 2 }$ 和 $V R _ { 3 } ^ { 2 }$ 都有单调性。Liu 和 Yuan 指出，在三个 $\textstyle V R ^ { 2 }$ 效应量指标中， $V R _ { 1 } ^ { 2 }$ 最符合调节效应的定义。因此，我们建议先将自变量 $X$ 和调节变量 $Z$ 都中心化，再计算 $\textstyle V R ^ { 2 }$ 效应量；在计算 $\textstyle V R ^ { 2 }$ 效应量时，建议先计算 $V R _ { 1 } ^ { 2 }$ ，并报告分母的方差 $V a r ( \beta _ { i 1 } X _ { i } )$ 大小，便于理解 $V R _ { 1 } ^ { 2 }$ 的实际意义。然后再根据研究者的具体需要，报告 $V R _ { 2 } ^ { 2 }$ 和 $V R _ { 3 } ^ { 2 }$ 。

# 4分析流程

面对一个调节效应分析任务，研究者应当如何进行呢？根据前面的讨论，我们总结出一套调节效应的分析流程（见图3)：

1.利用两水平回归模型进行调节效应分析。

2.判断 $\varepsilon _ { i 1 }$ （见方程（3b)）的方差 $\sigma _ { 1 } ^ { 2 }$ 是否显著。如果是，则误差方差一定是异方差的，报告两水平回归模型的调节效应分析结果和调节效应量；如果否，则表示不能推翻 $\sigma _ { _ { 1 } } ^ { 2 } { = } 0$ 的原假设，还无法得出误差方差齐性(即 $\sigma _ { 1 } ^ { 2 } { = } 0 _ { , } ^ { \cdot }$ 的结论，因此进入步骤3。

3．利用多元回归法进行调节效应分析，判断两水平回归模型的BIC 是否小于多元回归法的BIC(Bayesian Information Criterion)。如果是,则两水平回归模型和数据拟合的更好(Yuanet al.,2014)，报告两水平回归模型的调节效应分析结果和调节效应量；如果否，则报告多元回归法的分析结果和效应量 $\varDelta R ^ { 2 }$ 。

![](images/bf91024791cfac3eee1a044ba9865e23eb5df87bba1f4248b8c268b6b91c61bf.jpg)  
图3调节分析流程

# 5示例

接下来用一个实际例子演示如何进行两水平回归模型的调节效应分析。本例要研究的是冷酷无情特质(Z)在儿童期虐待 $( X )$ 与青少年的网络欺负行为 $( Y )$ 之间的调节作用，变量及其数据(940人)均来自方杰等(2020)的研究。所有数据在分析前都已经标准化。采用 Mplus8.2 进行两水平回归模型的调节效应分析（Mplus 程序见附录)。需要说明的是，第一，通过设置每个层2组只有一个层1被试（Mplus语句为CLUSTER $\mathbf { \tau } = \mathbf { I D } \mathbf { \tau }$ )，让Mplus 软件将单水平数据当成是两水平数据，从而进行两水平回归模型的调节效应分析（Liuetal.,2020)。第二，Mplus 软件默认采用稳健标准误的极大似然估计法（maximum likelihood estimation withrobust standard errors)进行参数估计,Liu等(2020)建议使用贝叶斯法进行参数估计（Mplus8.3及其以上版本才能实现)。第三，Mplus 软件默认误差 $\sigma _ { 0 1 }$ 为0。因为误差不相关( $\sigma _ { 0 1 } = 0 )$ 时，能得到更准确的 $\sigma _ { 1 } ^ { 2 }$ 和 $\sigma _ { 0 e } ^ { 2 }$ 值(Yuan et al., 2014; Liu et al., 202O, in press; Liu & Yuan, in press)。

两水平回归模型的调节效应分析结果见表1。由于 $\sigma _ { 1 } ^ { 2 }$ 显著（ $\sigma _ { 1 } ^ { 2 } \ = . 2 9$ ， $Z = 3 . 4 6 { \mathrm { : } }$ ，因此报告两水平回归模型的调节分析结果。系数 $\gamma _ { 1 1 }$ 的估计值显著 $\stackrel { \prime } { \boldsymbol { \gamma } } _ { 1 1 } = . 1 1 , t = 2 . 8 9 , P = . 0 0 4 )$ ，调节效应显著不等于0。Mplus 软件得到的调节效应量 $R _ { \beta _ { i 1 } } ^ { 2 } = . 0 4$ ， $R _ { \beta _ { i 1 } } ^ { 2 }$ 的 $9 5 \%$ 置信区间[0,

0.085]，表明 $\beta _ { i 1 }$ 的方差中有 $4 \%$ 可被调节变量Z解释。效应量 $\Delta R _ { m o } ^ { 2 }$ 、 $V R _ { 1 } ^ { 2 }$ 、 $V R _ { 2 } ^ { 2 }$ 和 $V R _ { 3 } ^ { 2 }$ 采用R 软件计算（Liu&Yuan,in press）。结果表明， $\Delta R _ { m o } ^ { 2 } = . 6 4$ ，表示 $Z _ { i } X _ { i }$ 独特解释的 $Y _ { i }$ 的方差在 $X _ { i }$ 和 $Z _ { i } X _ { i }$ 共同解释的 $Y _ { i }$ 的方差中所占的比例为 $64 \%$ ； $V R _ { 1 } ^ { 2 } =$ .043，表示 $Z _ { i } X _ { i }$ 解释的 $Y$ 的方差在与 $X _ { i }$ 有关的 $Y$ 的方差（.355）中所占的比例为 $4 . 3 \%$ ; $V R _ { 2 } ^ { 2 } = . 2 2 9$ ，表示 $Z _ { i } X _ { i }$ 解释的 $Y _ { i }$ 的方差在 $X _ { i }$ 能解释的 $Y _ { i }$ 的方差（.067）中所占的比例为 $2 2 . 9 \%$ ; $V R _ { 3 } ^ { 2 } =$ .05，表示 $Z _ { i } X _ { i }$ 解释的 $Y _ { i }$ 的方差在 $Z _ { i } X _ { i }$ 解释的 $Y$ 的方差和 $X _ { i }$ 不能解释的 $Y _ { i }$ 的方差之和（.303）中所占的比例为（204号 $5 \%$ 。

表1Mplus软件的两水平回归模型的调节效应分析结果  

<html><body><table><tr><td></td><td>Y00</td><td>Y01</td><td>Y10</td><td>Y11</td><td>g</td><td></td><td>R</td></tr><tr><td></td><td>-.04</td><td>.14</td><td>.17</td><td>.11</td><td>.29</td><td>.44</td><td></td></tr><tr><td>SE</td><td>.03</td><td>.03</td><td>.03</td><td>.04</td><td>.08</td><td>.08</td><td>.04</td></tr><tr><td>Z</td><td>-1.69</td><td>4.13***</td><td>5.36***</td><td>2.89**</td><td>3.46**</td><td>5.73***</td><td></td></tr></table></body></html>

注：\*\*表示 $p < . 0 1$ ；\*\*\*表示 $p < . 0 0 1$ 。

# 6两水平回归模型的调节效应分析的拓展

# 6.1稳健的调节效应分析

当数据存在异常值或者粗尾（heavy tails）时，两水平回归模型的调节效应分析结果存在偏差（Yuan et al.,2014; Yang&Yuan,2016)。为了解决这个问题，Yang 和 Yuan (2016)提出了两种稳健（robust）的两水平回归模型的调节效应分析方法。一种是基于t分布权重的极大似然估计法，另一种是基于Huber 权重的M估计法，字母“M”表示极大似然估计。稳健方法的基本思想是，为每个数据分配适当的权重，远离数据中心的数据（如异常值)，会给予更小的权重，因此异常值对调节效应估计的影响就更小了，从而得到更准确的调节效应估计值。Yang 和Yuan (2016)的模拟研究表明，当误差是非正态(如粗尾)时，这两种稳健方法在调节效应分析中的表现都优于基于正态分布的极大似然估计法；当误差是正态分布时，这两种稳健方法在调节效应分析中的表现与极大似然估计法相当。

对示例进行稳健的两水平调节效应分析，结果显示，两种稳健方法的系数 $\gamma _ { 1 1 }$ 的估计值都显著（表2），表明调节效应都显著不等于0，但系数的估计值都小于稳健标准误的极大似然估计法的分析结果（ $\gamma _ { 1 1 } = . 1 1 \AA )$ 。

表2稳健的两水平回归模型的调节效应分析结果  

<html><body><table><tr><td rowspan="2">0</td><td colspan="3">Huber 权重</td><td colspan="3">t分布权重</td></tr><tr><td>0</td><td>SE</td><td>Z</td><td></td><td>SE</td><td>Z</td></tr><tr><td>Y00</td><td>-.12</td><td>.03</td><td>-4.64</td><td>-.22</td><td>.02</td><td>-9.81</td></tr><tr><td>Y01</td><td>.09</td><td>.02</td><td>3.70</td><td>.06</td><td>.02</td><td>2.76</td></tr><tr><td>Y10</td><td>.19</td><td>.04</td><td>5.53</td><td>.17</td><td>.03</td><td>6.25</td></tr><tr><td>11</td><td>.07</td><td>.03</td><td>2.72</td><td>.05</td><td>.02</td><td>2.14</td></tr><tr><td></td><td>.08</td><td>.04</td><td>1.98</td><td>.09</td><td>.05</td><td>1.86</td></tr><tr><td></td><td>.29</td><td>.04</td><td>4.25</td><td>.17</td><td>.03</td><td>4.87</td></tr><tr><td></td><td></td><td>.062</td><td></td><td></td><td>.025</td><td></td></tr></table></body></html>

# 6.2潜变量的调节效应分析

显变量的调节效应分析的一个不足是假设所有变量的测量都不存在测量误差，当测量误差较大的时候这会造成调节效应的低估，而建立结构方程模型（Structural Equation Model,SEM）进行调节效应分析的最大优势就在于设置潜变量，有效控制测量误差，能准确估计调节效应值，是比较好的方法。

具体地，假设潜变量 $\xi _ { x }$ 由 $p _ { { _ x } }$ 个指标 $x _ { 1 } , x _ { 2 } , \cdots , x _ { p _ { x } }$ 组成，潜变量 $\boldsymbol { \xi } _ { z }$ 由 $p _ { z }$ 个指标 $\mathfrak { z } _ { 1 } , \mathfrak { z } _ { 2 } , \cdots , \mathfrak { z } _ { p _ { z } }$ 组成，潜变量 $\eta _ { \mathrm { y } }$ 由 $p _ { y }$ 个指标 $y _ { 1 } , y _ { 2 } , \cdots , y _ { p _ { y } }$ 组成，Liu等（2020）指出，两水平回归模型的 SEM调节效应分析就是将方程（2）和（3）中的显变量 $Y , ~ X$ 和 $Z$ 分别改为潜变量 $\eta _ { _ { y i } }$ 、 $\xi _ { _ { X i } }$ 和 $\xi _ { \mathrm { z } i }$ ，同时将图2中的长方形框(表示显变量)换做椭圆形图框(表示潜变量)即可。调节效应量指标$R _ { \beta _ { i 1 } } ^ { 2 }$ 只需要将方程（8）的 $V a r ( Z _ { i } )$ 改为 $V a r ( \xi _ { z } )$ 即可。

Liu 等（2020）的模拟研究发现，当误差方差是异方差时，相比单水平的 SEM调节效应分析(包括乘积指标法和潜调节结构方程法)而言，两水平回归模型的 SEM 调节效应分析提供了更准确的调节效应估计、且可靠区间覆盖率和第I类错误率的表现都更优(覆盖率更接近 $9 5 \%$ ，第I类错误率更接近0.05)；当误差方差齐性时，两水平回归模型的 SEM调节效应分析和单水平的分析结果相当。Liu 等提供了Mplus 程序进行两水平回归模型的 SEM 调节效应分析。值得注意的是，目前还不清楚 $\Delta R _ { m o } ^ { 2 }$ 和 $\textstyle V R ^ { 2 }$ 系列指标是否适用于两水平回归模型的 SEM调节效应分析（Liu&Yuan,in press）。

# 6.3基于两水平回归模型的有调节的中介效应分析

当前，调节和中介的整合已经成为社科领域发展的趋势。Liu等（in press）提出了基于两水平回归模型的有调节的中介效应的分析方法。例如，基于两水平回归模型的后半中介路径（ $. M {  } Y \rangle$ ）被调节的中介效应分析可表示为如下方程：

水平2： $\beta _ { _ { Y i } } = \gamma _ { _ { 0 0 } } + \gamma _ { _ { 0 } } Z _ { _ i } + \varepsilon _ { _ { i 0 } }$ （204号

$$
b _ { i } = \gamma _ { _ { 1 0 } } + \gamma _ { _ { 1 1 } } Z _ { _ i } + \varepsilon _ { _ { i 1 } }
$$

水平1:M,=β𝑀+aX,+eMi

如果 $\gamma _ { _ { 1 1 } } a$ 显著不为0（即 $\gamma _ { 1 1 } a$ 的置信区间不包含0)，就表示中介效应被调节了。Liu等（inpress)将被调节的中介效应的效应量定义为中介效应 $a b _ { \scriptscriptstyle i } = a ( \gamma _ { \scriptscriptstyle 1 0 } + \gamma _ { \scriptscriptstyle 1 1 } Z _ { \scriptscriptstyle i } + \varepsilon _ { \scriptscriptstyle i 1 } )$ 的方差中，能被 $Z _ { _ i }$ 解释的比例，即 $[ \gamma _ { 1 1 } ^ { 2 } a ^ { 2 } V a r ( Z _ { i } ) ] / V a r ( a b _ { i } ) = [ \gamma _ { 1 1 } ^ { 2 } a ^ { 2 } V a r ( Z _ { i } ) ] / [ \gamma _ { 1 1 } ^ { 2 } a ^ { 2 } V a r ( Z _ { i } ) + a ^ { 2 } V a r ( \varepsilon _ { i 1 } ) ]$ 。同理，读者很容易得到，基于两水平回归模型的前半中介路径（ $\cdot X {  } M$ ）被调节的中介效应分析可表示为如下方程：

水平1:M,=βmi+aX+eMi水平2：βMi=Yoo+γoZ+ε0

$$
a _ { i } = \gamma _ { _ { 1 0 } } + \gamma _ { _ { 1 1 } } Z _ { _ i } + \varepsilon _ { _ { i 1 } }
$$

水平1： $Y _ { \scriptscriptstyle i } = \beta _ { \scriptscriptstyle Y } + b M _ { \scriptscriptstyle i } + c ^ { \prime } X _ { \scriptscriptstyle i } + e _ { \scriptscriptstyle Y i }$

如果 $\gamma _ { _ { 1 1 } } b$ 显著不为0（即 $\gamma _ { _ { 1 1 } } b$ 的置信区间不包含0)，就表示中介效应被调节了。被调节的中介效应的效应量定义为中介效应 $a _ { i } b = ( \gamma _ { _ { 1 0 } } + \gamma _ { _ { 1 1 } } Z _ { _ i } + \varepsilon _ { _ i 1 } ) b$ 的方差中，能被 $Z _ { _ i }$ 解释的比例，即$[ \gamma _ { 1 1 } ^ { 2 } b ^ { 2 } V a r ( Z _ { i } ) ] / V a r ( a _ { i } b ) = [ \gamma _ { 1 1 } ^ { 2 } b ^ { 2 } V a r ( Z _ { i } ) ] / [ \gamma _ { 1 1 } ^ { 2 } b ^ { 2 } V a r ( Z _ { i } ) + b ^ { 2 } V a r ( \varepsilon _ { i 1 } ) ] \circ [ 0 , 1 ] \varepsilon = 0 .$ Liu等提供了Mplus程序进行两水平回归模型的有调节的中介效应及其效应量分析。

Liu 等(in press)的模拟研究发现，当误差方差是异方差时，相比单水平的有调节的中介模型而言，两水平回归模型的有调节的中介效应分析能提供更准确的条件中介效应估计、且可靠区间覆盖率和第I类错误率的表现都更优(覆盖率更接近 $9 5 \%$ ，第I类错误率更接近0.05)；当误差方差齐性时，两水平回归模型的有调节的中介效应分析和单水平的分析结果相当。

# 6.4基于两水平回归模型的有中介的调节效应分析

除了基于两水平回归模型的有调节的中介效应分析，刘红云等（2021）还提出了基于两水平回归模型的有中介的调节效应（即调节变量 $Z$ 对 $X {  } Y$ 关系的调节作用通过中介变量M

来传递）的分析方法。基于两水平回归模型的有中介的调节效应分析（图4）可表示为如下方程：

水平1：Y=βn+c,X+ei

水平2:β=Yoo+γoM,+YZ+εi0

$$
c _ { i } = \gamma _ { _ { 1 0 } } + \gamma _ { _ { 1 1 } } M _ { _ i } + \gamma _ { _ { 1 2 } } Z _ { _ i } + \varepsilon _ { _ { i 1 } }
$$

水平2：M=βm+aZ+εMi

![](images/ae30405d10c5a8859f60534f46dbb59aab776a868464c515e98e5f8e95026750.jpg)  
图4两水平回归模型的有中介的调节分析(改编自刘红云等，2021)

与两水平回归模型的调节效应分析（方程（2）和（3)）相比，两水平回归模型的有中介的调节效应分析仅增加了方程（13)并且在方程（12)中增加了中介变量 $\boldsymbol { M } _ { \boldsymbol { i } }$ 而已。将方程(12a)和（ $1 2 b$ ）带入方程(11)，得：

$$
Y _ { i } = \gamma _ { _ { 0 0 } } + \gamma _ { _ { 0 1 } } M _ { _ { i } } + \gamma _ { _ { 0 2 } } Z _ { _ { i } } + \gamma _ { _ { 1 0 } } X _ { _ { i } } + \gamma _ { _ { 1 1 } } M _ { _ { i } } X _ { _ { i } } + \gamma _ { _ { 1 2 } } Z _ { _ { i } } X _ { _ { i } } + \varepsilon _ { _ { i 1 } } X _ { _ { i } } + \varepsilon _ { _ { \bar { \imath } } }
$$

其中， $\varepsilon _ { _ { Y i } } = \varepsilon _ { _ { i 0 } } + e _ { _ { i } }$ ，因为在单水平数据中(方程(14)中仅有下标 $i )$ ， $\varepsilon _ { i 0 }$ 和 $e _ { i }$ 无法区分开的。将方程（13）带入方程（14)，整理得

$$
Y _ { i } = \gamma _ { \scriptscriptstyle { 0 0 } } + \gamma _ { \scriptscriptstyle { 0 1 } } \beta _ { \scriptscriptstyle { M } } + ( \gamma _ { \scriptscriptstyle { 0 1 } } a + \gamma _ { \scriptscriptstyle { 0 2 } } ) Z _ { i } + [ ( \gamma _ { \scriptscriptstyle { 1 0 } } + \gamma _ { \scriptscriptstyle { 1 1 } } \beta _ { \scriptscriptstyle { M } } ) + ( \gamma _ { \scriptscriptstyle { 1 1 } } a + \gamma _ { \scriptscriptstyle { 1 2 } } ) Z _ { i } + ( \gamma _ { \scriptscriptstyle { 1 1 } } \varepsilon _ { \scriptscriptstyle { M } } + \varepsilon _ { \scriptscriptstyle { i 1 } } ) ] X _ { i } + \gamma _ { \scriptscriptstyle { 0 1 } } \varepsilon _ { \scriptscriptstyle { M } } + \varepsilon _ { \scriptscriptstyle { N } }
$$

其中， $\gamma _ { 1 1 } a + \gamma _ { 1 2 }$ 表示 $Z$ 对 $X {  } Y$ 关系的调节作用，其中 $\gamma _ { 1 2 }$ 是直接调节作用， $\gamma _ { 1 1 } a$ 是 $Z$ 通过$M$ 对 $X {  } Y$ 关系的调节效应，即有中介的调节作用。如果 $\gamma _ { 1 1 } a$ 显著不为0（即 $\gamma _ { 1 1 } a$ 的置信区间不包含0)，就表示 $Z$ 对 $X {  } Y$ 关系的调节作用被 $M$ 中介了。刘红云等（2021）将有中介的调节效应的效应量定义为自变量 $X$ 对因变量 $Y$ 的效应 $c _ { i }$ 的方差 $V a r ( c _ { i } )$ 中，能被有中介的调节效应 $\gamma _ { 1 1 } a$ 解释的比例，即 $[ \gamma _ { 1 1 } ^ { 2 } a ^ { 2 } V a r ( Z _ { i } ) ] / V a r ( c _ { i } )$ 。刘红云等提供了Mplus 程序进行两水平回归模型的有中介的调节效应及其效应量分析。

刘红云等(2021)的模拟研究发现，当误差方差是异方差(即 $\varepsilon _ { i 1 } \neq 0 \rangle$ 时，相比单水平的有中介的调节模型(去掉方程(12)的 $\varepsilon _ { i 1 }$ )而言，两水平回归模型的有中介的调节效应分析能提供更准确的参数估计和效应量估计、第I类错误率更接近0.05，并且随着 $\boldsymbol { \varepsilon } _ { i 1 }$ 的增大，两水平回归模型的优势随之增加；当误差方差齐性(即 $\varepsilon _ { _ { i 1 } } = 0 \rangle$ 时，两水平回归模型的有中介的调节效应分析和单水平的分析结果相当。

# 7结语

针对多元回归法的调节效应分析及其效应量 $\varDelta R ^ { 2 }$ 的不足（Yuan et al.,2014; Liu & Yuan,in press)，较好的改进方法是使用两水平回归模型进行调节效应分析并使用与此模型相应的新效应量指标。我们总结出一个调节效应分析流程，并通过一个实例演示了如何进行两水平回归模型的调节效应分析并计算其效应量，随后还讨论了两水平回归模型的调节效应分析的发展。但本文仍然存在一些不足，尚需进一步深入讨论和拓展。例如，本文仅涉及一个自变量、一个调节变量和一个因变量的调节效应分析，实际上，本文介绍的方法同样适用于多个自变量、多个调节变量的情况。Yuan 等人(2014)用两水平回归模型分析了两个自变量、三个调节变量的调节效应。Liu 等(in press)用两水平回归模型分析了两个调节变量分别调节前、后路径的有调节的中介效应。方法的进步给研究者提供了一个深入理解和应用两水平回归模型进行调节效应分析的机会，相信随着研究的深入，会不断增加我们对两水平回归模型的调节效应分析问题的理解。

# 参考文献

方杰，赖馨，罗畏畏.(2020)．儿童期虐待对青少年网络欺负行为的影响：冷酷无情特质和性

别的调节作用．中国临床心理学杂志,28(5),991-994.   
方杰，温忠麟，梁东梅，李霓霓.(2015).基于多元回归的调节效应分析．心理科学，38(3), 715-720.   
刘红云，袁克海，甘凯宇．(2021)．有中介的调节模型的拓展及其效应量的测量．心理学报， 53(3), 322-338.   
温忠麟，范息涛，叶宝娟，陈宇帅.(2016)．从效应量应有的性质看中介效应量的合理性．心 理学报,48(4),435-443.   
温忠麟，侯杰泰，张雷．(2005)．调节效应与中介效应的比较和应用．心理学报，37(2), 268-274.   
温忠麟，刘红云.(2020)．中介效应和调节效应：方法及应用.北京：教育科学出版社.   
温忠麟，叶宝娟. (2014).有调节的中介模型检验方法：竞争还是替补？心理学报，46(5), 714-726.   
Aguinis,H., Petersen, S.A.，& Pierce,C.A.(1999). Appraisal of the homogeneity of error variance assumption and alternatives to multiple regression for estimating moderating effects of categorical variables. Organizational Research Methods, 2(4), 315-339.   
Aguinis, H., Beaty, J. C., Boik, R.J.,& Pierce, C. A. (2005). Effect size and power in assessing moderating effects of categorical variables using multiple regression: A 3O-year review. Journal of Applied Psychology, 90(1), 94-107.   
Hayes,A. F.,& Montoya,A. K. (2O17). A tutorial on testing, visualizing,and probing interaction involving a multicategorical variable in linear regression analysis. Communication Methods and Measures,11,1-30.   
Liu，H.，& Yuan，K-H. (in press). New measures of effect size in moderation analysis. Psychological Methods.   
Liu,H.,Yuan,K-H.,& Liu,F. (2O2O). A two-level moderated latent variable model with single level data. Multivariate Behavioral Research,55(6), 873-893.   
Liu, H., Yuan, K.-H., Wen. Z. (in press). Two-level moderated mediation models with single level data and new measures of effect sizes.Behavior Research Methods.   
Yang,M.，& Yuan,K.-H. (2016). Robust methods for moderation analysis with a two-level regression model. Multivariate Behavioral Research, 51(6),757-771.   
Yuan, K.-H., Cheng, Y.,& Maxwell S. (2O14). Moderation analysis using a two-level regression model. Psychometrika, 79(4), 701-732.

# Moderation Analysis and Its Effect Size Based on a Two-Level

# Regression Model

FANG Jie1， WEN Zhonglin²   
('Institute of Guangdong Economy and Social Development & Department of Applied Psychology, Guangdong University of Finance & Economics, Guangzhou, 510320)   
(²Center for Studies of Psychological Application & School of Psychology, South China Normal University, Guangzhou, 510631)

Abstract: In recent years, multiple regression has been widely used in social sciences to analyze the moderating effect. However, this practice was found to have at least four weaknesses. First, the concept of moderation is artificially treated as interaction. Second, the role of the predictor $X$ is confounded with that of the moderator $Z$ .Third,the assumption of homoscedasticity of error variances across different values of $X$ and $Z$ is often violated by data in social and behavioral sciences. Fourth, $\triangle R ^ { 2 }$ do not directly measure the effect of moderation as conceptually defined. Compared to multiple regression,the two-level regression model has many advantages in the analysis of moderating effect. After introducing the moderation analysis method based the two-level regression model and the corresponding effect size, we propose a procedure to analyze the moderating effect based on the two-level regression model. We exemplify how to conduct the proposed procedure by using Mplus. Directions for future study on two-level regression models are discussed at the end of the paper, including robust method of two-Level regression models; two-level moderated latent variable model, two-level moderated mediation model,and two-level mediated moderation model.

Key words: moderating effect, two-level regression model, multiple regression, effect size

附录：两水平回归模型的调节效应分析的Mplus程序  
DATA: $\mathrm { F I L E } = 2 . \mathrm { t }$ xt;  
VARIABLE:NAMESAREID x Zy；!2.txt的变量名USEVARIABLES= X z y Xz;CLUSTER ${ \bf \Lambda } = \mathrm { I D }$ ；!ID是被试号WITHIN ${ \bf \mu } = { \bf { x } }$ z y xz; !水平1的变量DEFINE: $\mathbf { X } \mathbf { Z } { = } \mathbf { X } ^ { * } \mathbf { Z }$ !产生调节项xz  
ANALYSIS:TYPEISTWOLEVELRANDOM;ALGORITHM $\mathbf { \Sigma } = \mathbf { \Sigma }$ INTEGRATION;  
MODEL:$\% \mathrm { W I T H I N \% }$ 1 $\ u _ { \mathrm { { 1 } Y O N X } }$ ！设置随机斜率YONZ !gam01值XZ(r11); !gam11值X with Z;X with Y;%BETWEEN%[b]; ！gam10值b(sig2_eil)；！sigmal的平方  
MODEL CONSTRAINT: NEW(var_z R2);var_ $\scriptstyle z = 1$ ；!Z由于标准化，方差为1R2=(r11\*r11\*var_z)/(r11\*r11\*var_z)+sig2_ei1)；!求效应量 $R _ { \beta _ { i 1 } } ^ { 2 }$   
OUTPUT: CINTERVAL;  
注：本程序默认使用MLR估计，如果使用贝叶斯估计，则需要将ANALYSIS命令改为:ESTIMATORISBAYES;POINT $\ c =$ MEAN；！后验均值作为参数的点估计值