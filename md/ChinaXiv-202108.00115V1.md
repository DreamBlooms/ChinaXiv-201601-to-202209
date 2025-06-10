# 国内中介效应的方法学研究回顾

温忠麟」方 杰² 谢晋艳」欧阳劲樱1(1华南师范大学心理学院/心理应用研究中心，广州510631)(²广东财经大学应用心理学系，广州510320)

摘要 中介效应可以分析自变量对因变量的影响过程和作用机制，已成为分析多个变量之间关系的一种重要统计方法。最近20年，中介效应成了研究方法的一个热点。从中介效应的检验方法、效应量、类别变量的中介效应检验、纵向数据的中介效应检验和模型拓展（包括多重中介、多层中介、有调节的中介和有中介的调节模型）五个方面系统总结了国内中介效应的方法学研究的发展历程。最后对中介效应的国外方法学研究进展和中介效应的未来研究方向做了讨论和拓展。

关键词中介效应，检验方法，效应量，模型拓展，类别变量，纵向数据分类号B841

揭示变量间的关系是量化研究的一个重要目标。中介（mediation）效应分析能解释自变量 $X$ 对因变量Y的影响是如何通过中介变量（mediator） $M$ 实现的，已成为多变量研究的重要统计方法（杜岸政等,2014;甘怡群,2014;温忠麟，叶宝娟,2014a)。

中介变量在社会科学研究中已有近百年的历史。例如，Woodworth（1928）在“刺激-反应”（S-R）理论的基础上提出了“刺激-机体-反应”（S-O-R）模型，说明了刺激对于反应的作用是通过有机体内部的转化过程而发生的，“机体”就是一个中介变量。但是直到20 世纪80年代，中介变量才受到重视，有了分析简单中介效应模型（即一个自变量、一个中介变量、一个因变量的简单中介模型）的逐步法（Baron&Kenny,1986;Judd&Kenny,1981)。在国内，温忠麟等（2004）率先介绍中介效应模型的分析方法，提出了一个包含依次检验和 Sobel检验的中介效应检验程序，引领和推动了国内中介效应的方法研究和应用。此后，中介效应分析成了国内心理统计的一个研究热点（温忠麟等,2021)。

中介效应的方法研究在国内的发展历程如表1所示，包括中介效应的检验方法、中介效应的效应量、类别变量的中介效应检验、纵向数据的中介效应检验和中介效应模型的拓展5个方面。中介效应模型的拓展包括多重中介效应模型、多层中介效应模型、有调节的中介模型和有中介的调节模型。表1分类列出了中介效应研究的由远及近的代表性文献，其中第一篇文献为相应类别在国内的首个研究。本文首先介绍简单中介模型，然后对与中介有关的概念进行辨析，接着系统地梳理国内中介效应的方法学研究的发展历程，最后对中介效应的国外方法学研究成果和中介效应的未来研究方向进行讨论。

表1国内中介效应的方法学研究文献一览  

<html><body><table><tr><td colspan="2">类别</td><td>文献</td></tr><tr><td colspan="2">检验方法</td><td>温忠麟等(2004)；温忠麟等(2005)；方杰等(2011)；方杰，张敏强(2012；2013)；温忠麟，叶宝娟 (2014a)；杨春艳等(2017)；方杰，温忠麟(2018a)</td></tr><tr><td colspan="2">效应量</td><td>方杰等(2012)；温忠麟等(2016)</td></tr><tr><td colspan="2">类别变量的中介效应</td><td>刘红云等(2013)；方杰等(2017)；王阳，温忠麟(2018)</td></tr><tr><td colspan="2">纵向数据的中介效应</td><td>刘国芳等(2018)；方杰等(印刷中)</td></tr><tr><td rowspan="4">模型拓展</td><td>多重中介</td><td>柳士顺，凌文轻(2009)；方杰，温忠麟，张敏强，孙配贞(2014)</td></tr><tr><td>多层中介</td><td>方杰等(2010)；刘红云等(2011)；方杰，温忠麟，张敏强，任皓(2014)；方杰，温忠麟(2018a)</td></tr><tr><td>有调节的中介</td><td>温忠麟等(2006)；温忠麟，叶宝娟(2014b)；方杰，张敏强等(2014)；方杰，温忠麟(2018b；印刷中)</td></tr><tr><td>有中介的调节</td><td>温忠麟等(2006)；刘东等(2012)；叶宝娟，温忠麟(2013)；温忠麟，刘红云(2020)；刘红云等(2021)</td></tr></table></body></html>

# 1简单中介效应模型

为了方便起见，假设变量都是连续并且已经标准化（回归方程中没有截距项)，则简单中介效应模型的分析就是执行如下线性回归方程

$$
Y = c X + \varepsilon _ { 1 }
$$

其中方程（1）的回归系数 $\mathbf { \Psi } _ { c }$ 为自变量 $X$ 对因变量 $Y$ 的效应；方程（2）的回归系数 $\mathbf { \Delta } _ { a }$ 为自变量 $X$ 对中介变量 $M$ 的效应；方程（3）的回归系数 $b$ 是在控制了 $X$ 的影响后 $M$ 对 $Y$ 的效应；系数 $c ^ { \prime }$ 是在控制了 $M$ 的影响后 $X$ 对 $Y$ 的效应； $\varepsilon _ { 1 }$ 、 $ { \varepsilon } _ { 2 }$ 和 $\varepsilon _ { 3 }$ 表示残差，假设残差服从正态分布且相互独立。将（2）代入（3)，整理得

$$
Y = ( c ^ { \prime } + a b ) X + \varepsilon _ { 2 } b + \varepsilon _ { 3 }
$$

方程（4）中的 $a b$ 为自变量 $X$ 对因变量 $Y$ 的中介效应（mediation effect）， $c ^ { \prime }$ 为 $X$ 对 $Y$ 的直

接效应（direct effect）， $c ^ { \prime } + a b$ 为 $X$ 对 $Y$ 的总效应（totaleffect)，在显变量情形， $c = c ^ { \prime } + a b$ 。

# 2概念辨析

中介效应也称为间接效应（indirect effect)，但两者并不完全相同。一般地说，中介效应都是间接效应，但间接效应不一定是中介效应。具体地，在只有一个中介变量的模型中，中介效应和间接效应是同义词；但当中介效应不止一个时，间接效应既可以指经过某个特定中介变量的间接效应（即中介效应)，也可以指部分或所有中介效应的和（卢谢峰，韩立敏,2007；温忠麟等,2004；温忠麟，刘红云,2020）。

中介效应解释了自变量 $X$ 如何影响因变量Y的问题，但如果理论或经验认为自变量 $X$ 对因变量Y应当有影响，而方程（1）的回归系数 $\boldsymbol { \mathscr { c } }$ 却不显著（表明 $X$ 对 $Y$ 的影响不显著),此时，如果问“ $X$ 如何影响Y”就不合理了，合理的问题是“ $X$ 为何不影响Y，变量 $M$ 在其中起到了什么作用”，应该进行“遮掩效应”（suppression effects）分析，研究效应被什么变量遮掩了（温忠麟，叶宝娟，2014a)。更明确地说，如果直接效应 $c ^ { \prime }$ 的绝对值比总效应 $\scriptstyle { \boldsymbol { c } }$ 的绝对值还大（此时 $c ^ { \prime }$ 和 $a b$ 异号)，就是遮掩效应（温忠麟，刘红云,2020)。温忠麟和叶宝娟（2014a）更进一步指出，如果方程（1）的回归系数 $\mathbf { \Psi } _ { c }$ 显著，则进行中介效应分析，研究“ $\dot { X }$ 如何影响Y”的问题；如果 $\mathbf { \Psi } _ { c }$ 不显著，则考虑遮掩效应分析（更一般的是不一致中介)，研究“ $X$ 为什么不影响 $Y ^ { \prime \prime }$ 的问题。

对于检验结果显著的中介效应，如果方程（3）的回归系数 $c ^ { \prime }$ 不显著，则称完全中介效应，如果 $c ^ { \prime }$ 显著，则称部分中介效应。有时候区分完全中介和部分中介并不合适。首先，一个完全中介模型的中介作用不一定比部分中介模型的中介作用大；第二，完全中介效应的结论阻碍了研究者进一步寻找其他中介变量的动机，阻碍了中介研究的发展。合适的做法是直接报告中介效应和直接效应的显著性（方杰等，2012；温忠麟，刘红云，2020；温忠麟，叶宝娟,2014a)。

中介效应分析的目的是探究 $X$ 如何影响Y，但如果自变量 $X$ 与因变量Y的关系受到第三个变量 $U$ 的作用，此时 $U$ 是调节变量（moderator）。调节效应（moderation effect）分析的目的是探究 $X$ 何时影响 $Y$ 或何时影响较大。中介变量和调节变量的区别详见温忠麟等(2005)。

# 3中介效应的方法学研究进展

# 3.1中介效应检验方法

早期的中介效应检验方法可分为系数差异检验法和系数乘积检验法。系数差异检验法的原假设为 $H _ { 0 }$ ： $c - c ^ { \prime } = 0$ ，但由于I型错误率有时候可能很高，所以系数差异检验法很早就被淘汰了（温忠麟等,2004)。系数乘积检验法的原假设为 $H _ { 0 }$ ： $a b = 0$ 。系数乘积检验法又可以分成间接检验和直接检验两类（图1)。

![](images/a36ed94f0fd1e4caa1ff42ab5b0afac67714f6fae39ef02edf7dd14d1dfa31b9.jpg)  
图1中介效应检验方法

依次检验法，也有文献称为联合显著法（joint significance)，是间接检验系数乘积的方法。其做法是依次检验方程(2)的系数 $| a |$ （即检验 $H _ { 0 } : a = 0 _ { , } ^ { \setminus }$ 和方程(3)的系数 $b$ (即检验 $\textstyle H _ { 0 } : b =$ 0)，如果系数 $\mathbf { \Delta } _ { a }$ 和 $b$ 都显著 （ $\mathbf { \Phi } _ { a } \neq \mathbf { \Phi } _ { 0 }$ 且 $b \ne 0 .$ )，足以推出中介效应 $a b$ 显著（ $a b \neq 0$ 。其实，依次检验与通常所说的联合显著法还是有区别的，前者要检验的研究假设（即备择假设)是 $H _ { 1 }$ ： $a b \neq 0$ ，而后者要检验的研究假设是 $H _ { 1 }$ ： $\mathbf { \boldsymbol { a } } \neq \mathbf { \boldsymbol { 0 } }$ 且 $b \neq 0$ 。也就是说，虽然检验过程一样，但对于依次检验，拒绝 $H _ { 0 }$ 后的结论是“ $a b$ 显著不等于 $\mathbf { \boldsymbol { 0 } } ^ { \prime \prime }$ ；而对于联合显著法，拒绝 $H _ { 0 }$ 后的结论是 ${ ^ { 6 6 } a }$ 显著不等于0且 $b$ 显著不等于 $\mathbf { \boldsymbol { 0 } } ^ { \prime \prime }$ ，两者的I型错误率是很不一样的。当显著性水平 $\alpha$ 为0.05时,可以分三种情形证明依次检验的I型错误率不足0.05（MacKinnonet al.,2002；也见温忠麟等,2004)，而联合显著法的I型错误率为 $1 - 0 . 9 5 ^ { 2 } { = } 0 . 0 9 7 5$ 。这是国内外都罕有人注意到的地方，以为依次检验没有检验到中介效应，不少期刊甚至不接受依次检验的文章投稿（甘怡群,2014)。诚然，如果依次检验得出中介效应不显著，则不应当使用该方法，因为它在图1所示的各种检验方法中检验力（power）最低（即Ⅱ型错误率最高）。依次检验还有一个不足是没有给出ab的置信区间。

直接检验系数乘积的方法包括 Sobel检验、乘积分布法、Bootstrap 法和贝叶斯法等。

Sobel 检验基于正态假设，但就算每一个系数都是正态分布，其乘积通常也不是正态的，因此 Sobel 检验的局限性是很明显的，此法现在已经极少使用（方杰等,2012)。乘积分布法默认ab的分布是两个正态变量的乘积分布，根据乘积分布得到 $a b$ 的区间估计，如果区间估计不包含0，则中介效应显著。乘积分布法只需要提供 $\boldsymbol { a }$ 和 $b$ 的估计值及其标准误即可，不需要原始数据，这是乘积分布法的优势。更多乘积分布法的内容详见综述方杰等（2011)。

Bootstrap 法是应用最为广泛的直接检验系数乘积的方法（陈瑞等,2013；江程铭等,2015;张涵等，2016)。Bootstrap 法是一种重复抽样方法。根据重复抽样的对象不同，可分为参数Bootstrap 法和非参数 Bootstrap 法。如果重复抽样的对象是参数（如 $\boldsymbol { a }$ 和 $b$ )，则是参数Bootstrap 法，Monte Carlo 法（简称MC 法）就是一种参数 Bootstrap 法，MC 法不需要原始数据，只需要知道 $a$ 和 $b$ 的估计值及其标准误即可。更多MC 法的内容详见方杰和温忠麟（2018a)。如果重复抽样的对象是样本数据，则是非参数 Bootstrap 法。非参数 Bootstrap 方法只依赖样本数据,通过不断抽取 Bootstrap 样本并计算 $\mathbf { \Delta } _ { a }$ 和 $b$ 的估计值,得到ab 的 Bootstrap区间估计，如果区间估计不包含0，则中介效应显著。如果要得到更高的检验力，可以使用偏差校正的 Bootstrap 法（方杰等,2011)。但偏差校正的 Bootstrap 法在某些条件下的I型错误率可能会超过设定的显著性水平（如0.05)，因此越来越多的研究者认为，如果不是为了追求最高的检验力，则更推荐使用未校正的 Bootstrap 法进行中介分析（方杰，温忠麟，2018a)。

贝叶斯（Bayesian）法，又称为马尔科夫链蒙特卡罗法（Markov Chain Monte Carlo,MCMC)，它将参数看成是随机变量，将参数的先验分布和观测数据整合在一起，通过马尔科夫链蒙特卡洛方法得到参数的后验分布，根据参数的后验分布得到ab 的区间估计，如果区间估计不包含0，就表示中介效应显著。贝叶斯法的关键步骤就是为模型参数选择合适的先验分布。当样本量小或抽样方差大时，合适的先验信息能有效改善参数的估计。更多贝叶斯法的介绍详见方杰等（2011)。

依次检验法、乘积分布法、Bootstrap 法和贝叶斯法在中介效应检验中各有所长（方杰，温忠麟,2018a；方杰，张敏强,2012；方杰，张敏强,2013)，温忠麟和叶宝娟（2014a）建议先使用依次检验，如果系数 $a$ 和 $b$ 不是同时显著，则建议使用Bootstrap 法进行中介效应检验。如果要报告中介效应的置信区间，使用Bootstrap 法较好，但无论如何，还是应当了解 $a$ 和$b$ 是否显著。如果有合适的先验信息，亦可使用贝叶斯法（方杰等,2011)。

# 3.2中介效应的效应量

中介效应显著，只能说明中介效应不是零，那么中介效应到底有多大的效应呢？这还需要使用中介效应的效应量指标来衡量。方杰等（2012）述评了四种中介效应的效应量，即中介效应与总效应之比 $P _ { M }$ 、中介效应与直接效应之比 $R _ { M }$ 、中介效应与中介效应的最大可能值之比 $\kappa ^ { 2 }$ 、以及 $R _ { m e d } ^ { 2 }$ 。 $R _ { m e d } ^ { 2 }$ 的计算公式是 $R _ { { { m e d } } } ^ { 2 } = \gamma _ { { { M Y } } } ^ { 2 } - ( R _ { { { Y } , { M X } } } ^ { 2 } - \gamma _ { { { X Y } } } ^ { 2 } )$ ，其中 $\gamma _ { _ { M Y } }$ 是因变量Y和中介变量 $M$ 的相关系数， $\gamma _ { _ { X Y } }$ 是 $Y$ 和自变量 $X$ 的相关系数， $R _ { Y , M X } ^ { 2 }$ 是方程(3)的测定系数 $R ^ { 2 }$ $R _ { m e d } ^ { 2 }$ 表示 $Y$ 的方差只能被 $X$ 和 $M$ 共同解释而不能被 $X$ 或 $M$ 独立解释的部分（方杰等,2012;温忠麟等,2016)。此外，Lachowicz 等（2018）将 $R _ { m e d } ^ { 2 }$ 公式中的 $\gamma _ { _ { M Y } }$ 换成 $\gamma _ { _ { M Y } } - a c ^ { \prime }$ ，提出一个新中介效应量指标 $\upsilon$ ， $\upsilon$ 的计算公式是 $\upsilon = ( \gamma _ { _ { M Y } } - a c ^ { \prime } ) ^ { 2 } - ( R _ { _ { Y , M X } } ^ { 2 } - \gamma _ { _ { X Y } } ^ { 2 } ) = a ^ { 2 } b ^ { 2 }$ 。

温忠麟等（2016）明确指出， $R _ { m e d } ^ { 2 }$ 中介效应量没有单调性（即中介效应 $a b$ 上升时， $R _ { m e d } ^ { 2 }$ 中介效应量可能下降)，所以 $R _ { m e d } ^ { 2 }$ 不适合作为中介效应量。 $\kappa ^ { 2 }$ 不仅没有单调性，而且将ab的最大可能值作为 $\kappa ^ { 2 }$ 的计算公式的分母是错误的，因此 $\kappa ^ { 2 }$ 也不适合作为中介效应量（Wen& Fan，2015）。 $\upsilon$ 虽然具有单调性，但还不如直接使用标准化的中介效应ab 更容易解释。温忠麟等（2016）建议当 $a b$ 和 $\mathbf { \Psi } _ { c }$ 符号一致时，报告 $a b$ 的标准化估计值并使用 $P _ { M }$ 作为中介效应量。当ab 和 $\mathbf { \Psi } _ { c }$ 符号不一致时，并没有合适的效应量推荐。

# 3.3类别变量的中介效应检验

一般的中介效应模型几乎都假设 $X , M$ 和 $Y$ 是连续变量的情况，对于被试间设计（即中介变量和因变量只测量一次）的中介分析，如果自变量为二分类别变量，中介变量和因变量为连续变量的中介效应检验，只需将类别自变量编码为0和1，可利用方程（1）－（3）进行中介效应分析。如果自变量为 $k$ 个类别 $( k \geqslant 3 )$ ，中介变量和因变量为连续变量的中介效应检验，可使用相对中介效应（即相对参照水平的中介效应）分析，即将多类别自变量进行虚拟编码，考察 $k ^ { - 1 }$ 个相对中介效应是否显著（方杰等,2017)

对于两水平被试内设计（即中介变量和因变量各重复测量二次）、自变量是二分类别变量（实验组 $X _ { 1 }$ 和控制组 $X _ { 2 }$ ）、中介变量 $( M _ { 1 }$ 和 $M _ { 2 }$ ）和因变量（ $Y _ { 1 }$ 和 $Y _ { 2 }$ ）是连续变量的情形，先计算 $Y _ { \mathrm { d i f f } } = Y _ { 2 } - Y _ { 1 }$ 、 $M _ { \mathrm { d i f f } } = M _ { \mathrm { 2 } } \cdot M _ { \mathrm { 1 } }$ 和 $M _ { \mathrm { s u m } } = M _ { 1 } + M _ { 2 }$ 产生三个新变量 $Y _ { \mathrm { d i f f } } \ 、 M _ { d i f f }$ （ $M _ { d i f f }$ 的均值就是系数 $\mathbf { \Omega } _ { a }$ ）和 $M _ { s u m } \mathrm { ~  ~ { ~ ( ~ } ~ } M _ { s u m }$ 需要中心化)；然后，由回归方程$Y _ { \mathrm { d i f f } } = c ^ { \prime } + b M _ { \mathit { d i f f } } + d M _ { s u m } + \varepsilon _ { Y }$ 得到系数 $b$ ，如果 $a b$ 的bootstrap置信区间不包含0，就表示中介效应显著（王阳，温忠麟,2018)。

如果中介变量和（或）因变量为类别变量，应该用Logistic回归取代通常的线性回归进行中介效应检验（刘红云等,2013)。当用Logistic 回归进行中介效应检验时，需要特别注意回归系数的等尺度化（方杰等,2017；刘红云等,2013)。例如因变量是类别变量，中介变量和自变量是连续变量时，方程2的回归系数 $a$ (连续变量的量尺)和方程3的回归系数 $b$ (Logit量尺）不在同一量尺上，因此不能直接将回归系数 $\mathbf { \Delta } _ { a }$ 和 $b$ 相乘得到中介效应大小。应当将回归系数 $a$ 和 $b$ 转化为 $Z _ { \ a } = a / S E ( a )$ 和 $Z _ { b } = b / S E ( b )$ ，中介效应大小为 $\boldsymbol { Z } _ { a } \times \boldsymbol { Z } _ { b }$ ，中介效应的检验也就是检验 $\boldsymbol { Z } _ { a } \times \boldsymbol { Z } _ { b }$ 的显著性（方杰等,2017)。当因变量是类别数不少于5的定序变量时，可考虑使用通常的线性回归进行中介效应检验（刘红云等,2013)。

# 3.4纵向数据的中介效应检验

以前的中介分析多采用截面数据，但有的情形不适合进行因果推断，因而需要收集历时性的纵向数据，进行纵向数据的中介分析（温忠麟,2017)。刘国芳等（2018）介绍了基于交叉滞后面板模型（其实称为自回归滞后模型更容易理解)、潜变量增长模型和潜分数变化模型的纵向数据的中介效应检验。方杰等（印刷中）进一步梳理了基于交叉滞后面板模型、潜变量增长模型和多水平模型的纵向数据的中介分析的四个发展趋势：（1）考察随时间变化的中介效应，如连续时间模型、多层时变系数模型。（2）考察随个体变化的中介效应，如随机效应的交叉滞后面板模型和多层自回归中介模型。（3）中介模型的整合，如交叉滞后面板模型与多水平模型整合为多层自回归中介模型。（4）使用 Bootstrap 和贝叶斯法进行纵向数据的中介分析。

方杰等（印刷中）明确指出，多层线性模型和潜变量增长模型在建模过程中，没有考虑变量之间影响的先后顺序，基于纵向数据的中介分析本质上还是截面的中介分析，要得出因果推论还要有统计以外的理据（温忠麟,2017)。只有交叉滞后面板模型、多层自回归中介模型和连续时间模型才能进行历时性因果推论，因为这三个模型体现了历时性因果推测所必须的测量时间点先后关系，同时考虑了自回归效应。他们还提出一个纵向数据的中介分析流程：如果研究目的不是为了进行历时性因果推论，可使用多层线性模型或者潜变量增长模型；如果研究目的是为了进行历时性因果推论且需要考察时变效应，则使用连续时间模型，否则使用交叉滞后面板模型或多层自回归中介模型。

# 3.5中介效应模型的发展

# 3.5.1多重中介效应模型

对于比较复杂的情形，经常需要多个中介变量才能更清晰地解释自变量对因变量的效应，即需要多重中介（multiple mediation）模型（图2)。根据多个中介变量之间是否存在影响关系，多重中介模型可以分为并行多重中介模型（中介变量之间无影响关系，图2 去掉

$M _ { 1 } {  } M _ { 2 }$ 路径）和链式多重中介模型（中介变量之间有影响关系，见图2)。多重中介模型的中介效应可以分为三类。（1）特定路径的中介效应（specific mediation effect)，即某个感兴趣的特定路径的中介效应。一般的中介效应都是两个系数的乘积（如 $a _ { 1 } b _ { 1 }$ )，但是多重中介模型可以研究多个系数乘积的链式中介效应（如 $a _ { 1 } a _ { 3 } b _ { 2 }$ )，链式中介效应是多重中介模型特有的。（2）总的中介效应（total mediation effect)，即模型中所有中介效应的总和。（3）对比中介效应，即某两个路径的中介效应的差异（如 $a _ { 1 } b _ { 1 } - a _ { 2 } b _ { 2 } )$ 。需要说明的是，如果两个中介效应异号，则对比中介效应为两个路径的中介效应的绝对值的差异（如 $\mid a _ { 1 } b _ { 1 } \mid - \mid a _ { 2 } b _ { 2 } \mid$ （方杰，温忠麟，张敏强，孙配贞,2014；柳士顺，凌文轻,2009；温忠麟，刘红云,2020)。

![](images/bf5246d67d876db7b13384c364128ff6123889a7d3aa0c10029ba7a4a08fa7a3.jpg)  
图2一个多重中介模型

柳士顺和凌文轻（2009）率先将多重中介效应模型及其分析方法引入国内，用 Sobel法进行显变量的多重中介模型分析。方杰、温忠麟、张敏强和孙配贞（2014）建议通过增加辅助变量，利用 Bootstrap 法进行潜变量的多重中介模型分析。各种中介效应检验方法在多重中介模型中的比较可见方杰等（2011）的综述，多类别自变量情形可见方杰等（2017）的文章，两水平重复测量的多重中介模型可见王阳和温忠麟（2018）的文章。

# 3.5.2多层中介效应模型

多层（嵌套）数据在社会科学领域中经常出现，如学生嵌套于班级。这时多层数据之间不满足独立性条件，需要引入多水平模型（multilevelmodel）分析中介效应，以克服传统中介模型使用最小二乘回归的局限（方杰等,2010)。多层中介效应模型是多水平模型和中介效应模型的结合。常见的多层中介模型有2-2-1模型（这三个数字依次代表自变量、中介变量和因变量的层次）、2-1-1 模型和 1-1-1 模型三种。根据路径系数是固定还是随机的，2-1-1模型可分为2-1-1固定中介效应模型和 2-1-1随机中介效应模型；1-1-1模型可分为1-1-1固定中介效应模型和 1-1-1 随机中介效应模型。具体地说，2-1-1 随机中介效应模型存在随机效应 $b _ { j }$ ，下标 $j$ 表示第 $j$ 个层2水平（如班级)，表示控制 $X$ 条件下，层1变量 $M$ 对层1变量Y的预测效应在不同的层2水平（班级）间存在变异。用 $b$ 表示所有层2水平的 $b _ { j }$ 的平均值， $b _ { j }$ 和 $b$ 的关系可表示为 $b _ { j } = b + \varepsilon _ { j }$ 。1-1-1随机中介效应模型存在随机效应 $a _ { j } \mathrm { , \ } b _ { j \mathrm { \cdot } } \ c _ { j } ^ { \prime }$ ，以及随机中介效应 $a _ { j } b _ { j }$ （刘红云等,2011）。

方杰等（2010）率先将多层中介效应模型及其分析方法引入国内，讨论了如何进行显变量的多层中介效应模型分析。在 2-1-1和1-1-1中介效应模型分析时，对层1自变量按组均值中心化，同时将组均值置于层2截距方程式中，以实现组间和组内中介效应的有效分离。具体地说，2-1-1中介效应模型的组内中介效应为0，仅有组间中介效应。1-1-1中介效应模型则既有组间中介效应，又有组内中介效应。刘红云等（2011）注意到，当数据符合1-1-1随机中介效应模型时，使用1-1-1固定中介效应模型将错误估计中介效应及其标准误，得到不正确的统计检验结果。

如果数据来自 $J$ 个公司的 $I$ 个员工，其中， $J$ 个公司是从公司总体中随机抽样，员工是从样本公司全体员工中随机抽样，那么在多层中介效应模型分析中，将层1变量（如员工心理资本）按组均值中心化，并将组均值（ $\cdot I$ 个员工的心理资本的平均值）置于层2截距方程中，这就默认了 $I$ 个员工的心理资本的组均值就等于不可观测的公司平均员工心理资本，这种默认会导致抽样误差（sample error)，即由于抽样(从被试总体中抽取部分被试)而产生的参数估计偏差（方杰，温忠麟，张敏强，任皓，2014)。可以将组均值看成是无法直接观测的潜变量，使用多层结构方程模型(Multilevel Structural Equation Modeling,MSEM)进行多层中介效应模型分析，能较好控制的抽样误差。方杰等还给出了一个多层中介效应分析流程，建议先使用多层结构方程模型进行潜变量的多层中介效应分析，如果检验结果是多层中介效应不显著且因变量在层1，则建议使用多水平模型继续进行显变量的多层中介效应检验。

在多层中介效应分析中，非参数 Bootstrap 法的实现是比较困难的，用什么中介效应分析方法比较好呢？方杰和温忠麟（2018a）的研究建议，在多层中介分析中，当有合适的先验信息时，推荐使用贝叶斯法；当先验信息不可得时，推荐使用 MC 法。因为MC 法在中介效应分析中的表现不仅与其他方法相当，还无需使用原始数据（这是非参数 Bootstrap 和贝叶斯法都无法做到的)，因此运算速度更快。各种中介效应检验方法在多层中介效应模型中的比较亦可见方杰等（2011）综述。

# 3.5.3有调节的中介模型

有调节的中介是指中介过程（ $\cdot X {  } M {  } Y \backslash$ ）受到调节变量 $Z$ 的影响，即中介效应大小会随着调节变量 $Z$ 的不同取值而变化。温忠麟等（2006）讨论了如何用依次检验法进行中介过程的后半路径！ $( M {  } Y )$ 被调节的中介模型检验。温忠麟和叶宝娟（2014b）系统总结了6种有调节的中介模型（只调节中介效应的3种模型和同时调节中介效应和直接效应的3种模型)，并以同时调节中介效应的前半路径（ $\cdot X {  } M )$ 、后半路径（ $M {  } Y \backslash$ ）和直接效应（ $\langle X { \to } Y \rangle$ 的有调节的中介模型为例，评述了三种有调节的中介模型的分析方法：依次检验法、系数乘积的区间检验法和中介效应差异检验法，并给出了一个检验流程。温忠麟等人建议先使用依次检验进行有调节的中介模型检验；如果有调节的中介效应不显著，则换用系数乘积的区间检验法（非参数 Bootstrap 法)；如果有调节的中介效应仍不显著，则换用中介效应的差异检验（非参数 Bootstrap 法)。方杰、张敏强等（2014）阐述了如何用系数乘积的区间检验法（贝叶斯法）进行有调节的中介模型检验。刘红云等（Liu,Yuan et al.,in press）将有调节的中介模型与两水平回归的调节效应模型（Yuan et al.,2014）相结合，提出了基于两水平回归的有调节的中介效应模型，并给出了被调节的中介效应的效应量指标。

方杰和温忠麟（2018b）进一步阐述了如何使用潜调节结构方程方法进行潜变量的有调节的中介模型检验。潜调节结构方程方法（Klein& Moosbrugger,2000）的优势在于无需使用乘积指标，且可用结构方程软件 Mplus 方便执行，有望推广应用。方杰等人建议，如果基准模型（不含潜调节项的有调节的中介模型）可接受，则进行潜变量的有调节的中介模型检验；否则进行显变量的有调节的中介模型检验。

方杰和温忠麟（印刷中）将多层中介和多层调节整合在一起，形成了2（多层中介类型)$\times 2$ （调节变量的层次） $\times 3$ （调节的中介路径）共12种有调节的多层中介模型。他们阐述了如何进行显变量的12种有调节的多层中介模型检验；系统阐述了使用多层结构方程模型进行潜变量的有调节的多层中介模型检验方法，包括正交分割法，随机系数预测法，潜调节结构方程法和贝叶斯合理值法。这四类方法的核心议题在于如何处理潜调节项。当样本量足够大时，建议选择潜调节结构方程法；当样本量不足时，建议选择贝叶斯合理值法。

# 3.5.4有中介的调节模型

有中介的调节模型意味着自变量 $X$ 对因变量Y的效应受到调节变量Z的影响，而调节效应(至少部分地)通过中介变量 $M$ 对因变量 $Y$ 起作用(图3(a))，这是有中介的调节模型I（刘东等,2012；温忠麟等,2006)。温忠麟等（2006）讨论了如何用依次检验法进行有中介的调节模型I的检验。此时，有中介的调节模型的检验步骤和中介过程的前半路径（ $\cdot X {  } M )$ 受到调节的中介模型的检验步骤一致，两种模型的区别在于立论和解释不同（温忠麟，叶宝娟,2014a)。对于有中介的调节模型，重点在调节效应，其次考虑调节效应是否通过中介变量起作用；对于有调节的中介模型，重点在中介效应，其次考虑中介过程是否受到调节。

![](images/3f6bcab96aae762a2dd766854a1402ce831112d09bc60835060cf6908224d01c.jpg)  
图3有中介的调节模型

叶宝娟和温忠麟（2013）系统地评述了五种检验有中介的调节模型的方法，并给出了一个检验流程。先检验自变量 $X$ 对因变量Y的效应是否受到调节变量Z的调节；如果调节效应显著（且效应量 $\varDelta R ^ { 2 }$ 不小于 $2 \%$ )，则先使用依次检验进行有中介的调节模型检验；如果有中介的调节效应不显著，则换用系数乘积的区间检验法(非参数 Bootstrap 法或贝叶斯法)。

温忠麟和刘红云（2020）进一步将有调节的中介模型检验和有中介的调节模型检验流程整合起来，总结出一个综合检验流程。如果自变量 $X$ 对因变量Y的效应没有受到调节变量Z的调节，则只考虑建立有调节的中介模型。如果自变量 $X$ 对因变量Y的效应受到调节变量 $Z$ 的调节，则既可以考虑建立有中介的调节模型，也可以考虑建立有调节的中介模型，到底建立哪种模型取决于研究者的立论。

刘东等（2012）指出，当调节变量Z的调节作用可以通过中介变量 $M$ 传递时，这就是有中介的调节模型II（图3（b))。Kwan 和Chan（2018）指出，有中介的调节模型I与将 $Z$ 当成自变量、 $X$ 当成调节变量的后半路径受到调节的中介模型等价。刘红云等（2021）进一步将有中介的调节模型ⅡI与两水平回归的调节效应模型（Yuan et al.,2014）相结合，提出了基于两水平回归的有中介的调节效应模型，并给出了经过中介变量的间接调节效应量的新指标。

刘东等（2012）将多层中介和多层调节整合在一起，提出了三种有中介的多层调节模型I和两种有中介的多层调节模型Ⅱ。三种有中介的多层调节模型I为：层2变量 $X$ 和层2变量 $Z$ 的调节作用通过层1变量 $M$ 对层1变量Y产生作用或通过层2变量 $M$ 对层1变量Y产生作用、层1变量 $X$ 和层1变量 $Z$ 的调节作用通过层1变量 $M$ 对层1变量 $Y$ 产生作用。两种有中介的多层调节模型I为：层2变量 $Z$ 对层1变量 $X$ 和层1变量Y的调节作用通过层2中介变量 $M$ 传递或通过层1中介变量 $M$ 传递。

# 4讨论与拓展

本文从中介效应的检验方法、中介效应效应量、类别变量的中介效应检验、纵向数据的中介效应检验、中介效应模型拓展5个方面系统总结了国内中介效应的方法学研究的进程，可作为读者了解中介效应分析的文献导读。结合国外新近的中介效应的方法学研究，还有一些值得深入探讨和拓展的地方。

# 4.1基于实验设计的中介效应

实验设计的中介效应在国内的研究仅有两项。一是刘国芳（2018）介绍了三种基于实验的中介效应的设计，包括双随机设计、并发双随机设计和平行设计。二是王阳和温忠麟（2018)阐述了两水平被试内设计的中介效应检验方法（详见3.3节)。Miocevic 等（2018）指出，对于操纵自变量（如实验组和控制组)，然后再测量中介变量和因变量(中介变量和因变量各测量一次）的实验设计，可在潜在结果和反事实框架基础上，进行潜在结果中介分析。例如，利用词汇记忆实验设计研究记忆策略（实验组是联想记忆、控制组是重复记忆) $$ 学生对词语的联想程度 $$ 记忆单词数目的中介效应。当学生没有被随机分配到实验组或控制组之前，每个学生都会有两个可能的因变量，即使用联想记忆（ $\scriptstyle { \mathcal { X } } = 1$ ）而默写出的单词数据 Y(1)和使用重复记忆（ $\scriptstyle \cdot X = 0$ ）而默写出的单词数据 Y(O)，我们称Y(1)和 Y(O)为潜在结果(potentialoutcome)。如果学生被分配进入实验组（联想记忆)，则 Y(1)就是观测到的因变量；此时 Y(0)这个潜在结果就是不可能出现的，称为反事实结果（counterfactual outcome）。

# 4.2混淆变量在中介效应检验中的控制

在简单中介模型中，如果变量 $T$ 既是中介变量 $M$ 的原因（即 $T {  } M )$ ，又是因变量Y的原因（即 $T {  } Y )$ ，则称变量 $T$ 为 $M {  } Y$ 关系的混淆变量（confounder）。 $M {  } Y$ 关系的混淆变量又分为两种，即前处理混淆变量（pretreatment confounder）和后处理混淆变量（posttreatmentconfounder)。前处理混淆变量是指混淆变量发生在实验处理 $X$ 之前，因此可以假设前处理混淆变量不受 $X$ 的影响（图4)。后处理混淆变量是指混淆变量发生在实验处理 $X$ 之后，因此后处理混淆变量可能会受到 $X$ 的影响（在图4中增加 $X {  } T$ 的箭头)。例如，受教育程度$( \boldsymbol { \chi } )$ 通过不良的饮食习惯（ $. M )$ 影响血压（Y）的简单中介模型中，社会经济地位（T）就是一个后处理混淆变量，因为受教育程度 $( \boldsymbol { X } )$ 会影响社会经济地位 $( T )$ 。

![](images/65b949e1e812255f8a5824174264874c96702679026273c4b9fb9e68d044a308.jpg)  
图4包含混淆变量 $T$ 的简单中介模型(改编自Fritz等,2016)

Fritz等（2016）发现在简单中介效应分析中，遗漏的混淆变量 $T$ 会影响 $M {  } Y$ 之间的关系，导致中介效应被高估。Tofighi等（2013；2016）发现在1-1-1中介效应分析中，遗漏的层2混淆变量 $T$ 会影响 $M {  } Y$ 之间的关系，使得组内和组间中介效应估计都产生了偏差。Talloen 等（2016）发现在2-1-1中介效应分析中，遗漏的层2混淆变量 $T$ 也会影响 $M {  } Y$ 之间的关系，导致中介效应估计产生偏差。因此，在中介效应检验中，混淆变量必须加以控制。如果是前处理混淆变量 $T$ 的简单中介效应检验，则在方程（1）－（3）中，增加混淆变量 $T$ 作为控制变量。例如方程（2）变为 $M = a _ { _ T } X + f T + \varepsilon _ { 2 }$ ，方程（3）变为$Y = c _ { T } ^ { \prime } X + b _ { T } M + g T + \varepsilon _ { 3 }$ ，中介效应检验就是检验 $a _ { T } b _ { T }$ （Fritz et al.,2016)。Fritz等人还指出，后处理混淆变量应看成新的中介变量来处理，增加 $X {  } T {  } M$ ， $X {  } T {  } Y$ ， $X {  } T {  } M$ $ Y$ 三个新的中介效应。

# 4.3稳健中介分析

利用线性回归进行中介效应检验时，线性回归需要满足残差同质（homoscedastic）且正态的假设，但实际上往往难以满足。稳健方法（robust method）可以缓解线性回归的中介分析中由于假设违背而造成的中介估计偏差。稳健方法的优点就是对理想的统计假设存在一定的偏差不敏感性（Zu& Yuan,2010)。因此，基于稳健方法的中介分析又称为稳健中介分析(robust mediation analysis)。稳健中介效应的分析方法包括 Robust M估计法（Zu& Yuan,2010）、中数回归法（Yuan & MacKinnon,2014）和 Robust Bootstrap 法（Alfons et al., in press ）三种。

Robust M的字母“M”表示极大似然估计（maximum likelihood)。RobustM估计法是对基于正态分布假设的极大似然估计的近似。Robust M估计法的基本思想是，根据每个数据距离数据中心（如均值）的距离，为每个数据分配适当的权重。距离数据中心的距离越远的数据（如极端值)，会给予越小的权重，因此极端值对（中介）估计的影响就更小（Zu&

Yuan,2010）。

传统线性回归可以称为均值回归，但是均值容易受极端值影响，在数据的分布存在偏度和厚尾（方差大）时表现较差（Yuan& MacKinnon,2014)。中数不容易受极端值影响，因此Yuan 和MacKinnon 提出了中数回归法（median regression)。对于中数回归法而言，除了残差独立性假设必须满足外，残差同质性和正态分布假设都不再需要。中数回归法采用最小绝对值残差（the least absolute deviations,LAD）法进行估计。

Robust Bootstrap 法是指在每个Bootstrap 样本上，首先利用加权最小二乘法（权重的取值范围是[0,1]，权重越小，表示数据越远离其他数据）计算参数估计值 $\hat { a }$ 和 $\hat { b }$ 。考虑到获得稳健的权重的其他不确定性，再对 $\hat { a }$ 和 $\hat { b }$ 进行线性校正（linear correction，Alfons et al.,inpress）。

# 4.4中介效应的检验力分析

中介效应的检验力分析可分为两种。一种是已知样本量、I型错误率 $\alpha$ 和中介效应量(a$b$ 和 $c ^ { \prime }$ 的标准化的样本估计值)，求中介效应效应的检验力，也称为事后检验力分析（post hocpower analysis)。但这类分析通常意义不大。另一种是设定期望的检验力（不低于0.8）、I型错误率 $\alpha$ 和预估的中介效应量（a、 $b$ 和 $c ^ { \prime }$ 的标准化的预测估计值来源于已有研究、导航研究、元分析、专家经验等)，求中介效应分析的样本量。Schoemann 等(2017)开发了一种网络工具可进行简单中介模型和多重中介模型的两类检验力分析。Liu 和Wang（2019）指出，Schoemann 的统计分析工具在输入预测的a、 $b$ 和 $c ^ { \prime }$ 值时，没有考虑预测的不确定性有多大。Liu和Wang 将预测的不确定性考虑到检验力的分析中，开发了新的检验力分析的网络工具。

当前，与新的统计技术相结合成为中介效应的方法学研究的新特点。例如，Serang 等（2017）利用Lasso 估计提出了正则化的探索性中介分析（exploratory mediation analysis viaregularization)，只有中介效应不为0的特定中介路径会保留在并行多重中介模型中。Serang和Jacobucci（2020）将探索性中介分析拓展到适用于结果变量是类别变量的情景中，包括中介变量是类别变量以及因变量是二分变量的情况。又如，Gonzalez等（2018）将双因子分析和中介分析相结合，提出了双因子中介分析方法。Gonzalez 等（2021）将中介变量 $M$ 设为双因子模型，考察了中介变量的测量（包括信度和测量误差）对中介分析的影响。再如，Hsiao 等（in press）将潜类别分析和中介分析相结合，提出了潜类别中介分析方法。还有研究者将社会网络分析和中介分析相结合，提出了社会网络中介分析方法(Che etal.,2021; Liu,

Jin et al.,in press)。方法的进步为研究者提供了深入理解和应用中介效应的可能，相信随着中介效应的方法学研究的深入，会不断增加对中介效应相关问题的理解。

# 参考文献

陈瑞，郑毓煌，刘文静.(2013).中介效应分析：原理、程序、Bootstrap 方法及其应用．营销科学学报,9(4),120-135.  
杜岸政，古纯文，丁桂凤.(2014).心理学研究中的中介效应分析意义及方法评述．中国心理卫生杂志,28(8),578-583.  
方杰，温忠麟.(2018a).三类多层中介效应分析方法比较．心理科学,41(4),962-967.  
方杰，温忠麟.(2018b).基于结构方程模型的有调节的中介效应．心理科学,41(2),453-458.  
方杰，温忠麟.(印刷中).有调节的多层中介效应效应分析．心理科学.  
方杰，温忠麟，邱皓政.(印刷中).纵向数据的中介效应分析．心理科学.  
方杰，温忠麟，张敏强.(2017).类别变量的中介效应分析．心理科学,40(2),471-477.  
方杰，温忠麟，张敏强，任皓.(2014).基于结构方程模型的多层中介效应分析．心理科学进展,22(3), 530-539.  
方杰，温忠麟，张敏强，孙配贞.(2014).基于结构方程模型的多重中介效应分析．心理科学,37(3), 735-741.  
方杰，张敏强.(2012).中介效应的点估计和区间估计：乘积分布法、非参数 Bootstrap 和MCMC 法．心理学报,44(10),1408-1420.  
方杰，张敏强.(2013).参数和非参数 Bootstrap 方法的简单中介效应分析比较．心理科学，36(3), 722-727.  
方杰，张敏强，顾红磊，梁东梅.(2014).基于不对称区间估计的有调节的中介模型检验．心理科学进展,22(10),1660-1668.  
方杰，张敏强，李晓鹏．(2011).中介效应的三种区间估计方法．心理科学进展，19(5),765-774.  
方杰，张敏强，邱皓政.(2010)．基于阶层线性理论的多层级中介效应．心理科学进展,18(8),1329-1338.  
方杰，张敏强，邱皓政.(2012).中介效应的检验方法和效果量测量：回顾与展望．心理发展与教育,28(1),105-111.

甘怡群.(2014).中介效应研究的新趋势—一研究设计和数据统计方法．中国心理卫生杂志,

28(8), 584-585.   
江程铭，李纾.(2015).中介分析和自举(Bootstrap）程序应用．心理学探新,35(5),458-463.   
刘东，张震，汪默.(2012).被调节的中介和被中介的调节：理论构建与模型检验(高中华 译)．见陈晓萍，徐淑英，樊景立 (编).组织与管理研究的实证方法(第二版，pp. 553-587)．北京：北京大学出版社.   
刘国芳，程亚华，辛自强．(2018)．作为因果关系的中介效应及其检验．心理技术与应用， 6(11), 665-676.   
刘红云，骆方，张玉，张丹慧.(2013)．因变量为等级变量的中介效应分析．心理学报,45(12), 1431-1442.   
刘红云，袁克海，甘凯宇.(2021).有中介的调节模型的拓展及其效应量的测量．心理学报, 53(3), 322-338.   
刘红云，张月，骆方，李美娟，李小山．(2011).多水平随机中介效应估计及其比较．心理学 报,43(6),696-709.   
柳士顺，凌文轻.(2009).多重中介模型及其应用．心理科学,32(2),433-435.   
卢谢峰，韩立敏.(2007)．中介变量、调节变量与协变量—一概念、统计检验及其比较．心理 科学,30(4),934-936.   
王阳，温忠麟．(2018).基于两水平被试内设计的中介效应分析方法．心理科学，41(5), 1233-1239.   
温忠麟.(2017).实证研究中的因果推理与分析．心理科学,40(1),200-208.   
温忠麟，范息涛，叶宝娟，陈宇帅.(2016)．从效应量应有的性质看中介效应量的合理性．心 理学报,48(4),435-443.   
温忠麟，方杰，沈嘉琦，谭倚天，李定欣，马益铭.(2021)．新世纪 20 年国内心理统计方法研 究回顾．心理科学进展,29(8),1331-1344.   
温忠麟，侯杰泰，张雷.(2005)．调节效应与中介效应的比较和应用．心理学报，37(2), 268-274.   
温忠麟，刘红云.(2020)．中介效应和调节效应：方法及应用．北京：教育科学出版社.   
温忠麟，叶宝娟.(2014a).中介效应分析：方法和模型发展．心理科学进展,22(5),731-745.   
温忠麟，叶宝娟.(2014b).有调节的中介模型检验方法：竞争还是替补？心理学报，46(5), 714-726.   
温忠麟，张雷，侯杰泰.(2006).有中介的调节变量和有调节的中介变量．心理学报,38(3), 448-452.   
温忠麟，张雷，侯杰泰，刘红云.(2004).中介效应检验程序及其应用．心理学报,36(5), 614-620.   
杨春艳，侯艳，李康.(2017)．中介分析方法及在其医学研究中的应用．中国卫生统计,34(1), 159-162.   
叶宝娟，温忠麟.(2013).有中介的调节模型检验方法：甄别和整合．心理学报，45(9), 1050-1060.   
张涵，康飞.(2016).基于bootstrap 的多重中介效应分析方法．统计与决策,(5),75-78.   
Alfons, A., Ates, N., & Groenen, P. J. F. (in press). A robust bootstrap test for mediation analysis. Organizational Research Methods.   
Baron,R. M.,& Kenny, D.A. (1986). The moderator-mediator variable distinction in social psychological research: Conceptual, strategic， and statistical considerations. Journal of Personality and Social Psychology, 51(6), 1173-1182.   
Che, C., Jin, I. H.,& Zhang, Z. (2021). Network mediation analysis using model-based eigenvalue decomposition. Structural Equation Modeling: A Multidisciplinary Journal, 28(1), 148-161.   
Fritz, M. S., Kenny, D.A.,& MacKinnon, D. P. (2016). The combined effects of measurement error and omiting confounders in the single mediator model. Multivariate Behavioral Research,51(5), 681-697.   
Gonzalez, O., & MacKinnon, D.P. (2018). A bifactor approach to model multifaceted constructs in statistical mediation analysis. Educational and Psychological Measurement, 78(1), 5-31.   
Gonzalez, O., & MacKinnon, D. P. (2021). The measurement of the mediator and its influence on statistical mediation conclusions. Psychological Methods, 26(1),1-17.   
Hsiao, Y-Y., Kruger, E. S., Horn, M., Tofighi, D., MacKinnon, D.P., & Witkiewitz, K. (in press). Latent class mediation: A comparison of six approaches. Multivariate Behavioral Research.   
Judd, C. M., Kenny, D.A. (1981). Process analysis: Estimating mediation in treatment evaluations. Evaluation Review, 5(5), 602-619.   
Klein,A. G.,& Moosbrugger, H. (20o0). Maximum likelihood estimation of latent interaction effects with the LMS method. Psychometrika, 65(4), 457-474.   
Kwan, J. L. Y., & Chan, W. (2018). Variable system: An alternative approach for the analysis of mediated moderation. Psychological Methods, 23(2),262-277.

Lachowicz, M. J., Preacher, K. J.，& Kelley, K. (2018). A novel measure of effect size for mediation analysis.Psychological Methods, 23(2), 244-261.

Liu, H., Jin, I. H., Zhang, Z.,& Yuan, Y. (in press). Social network mediation analysis: A latent space approach. Psychometrika.   
Liu,H., Yuan,K.-H., Wen, Z. (in press). Two-level moderated mediation models with single level data and new measures of effect sizes.Behavior Research Methods.   
Liu, X.,& Wang,L. (2019). Sample size planning for detecting mediation effects: A power analysis procedure considering uncertainty in effect size estimates. Multivariate Behavioral Research, 54(6), 822-839.   
MacKinnon,D. P.,Lockwood, C. M.，Hoffman, J. M.，West, S.G.，& Sheets， V. (2002)．A comparison of methods to test mediation and other intervening variable effects. Psychological Methods, 7(1), 83-104.   
Miocevic, M., Gonzalez, O., Valente, M. J.,& MacKinnon, D. P. (2018). A tutorial in Bayesian potential outcomes mediation analysis. Structural Equation Modeling: A Multidisciplinary Journal,25(1), 121-136.   
Schoemann, A. M., Boulton, A. J.,& Short, S. D. (2017). Determining power and sample size for simple and complex mediation models. Social Psychological and Personality Science, 8(4), 379-386.   
Serang,S.,& Jacobucci, R. (2020). Exploratory mediation analysis of dichotomous outcomes via regularization. Multivariate Behavioral Research, 55(1), 69-86.   
Serang, S., Jacobucci, R., Brimhall K. C., & Grimm, K. J. (2017). Exploratory mediation analysis via regularization. Structural Equation Modeling: A Multidisciplinary Journal, 24(5), 733-744.   
Talloen, W., Moerkerke, B., Loeys, T.,De Naeghel, J., Van Keer, H.,& Vansteelandt, S. (2016). Estimation of indirect effects in the presence of unmeasured confounding for the mediator-outcome relationship in a multilevel 2-1-1 mediation model. Journal of Educational & Behavioral Statistics, 41(4), 359-391.   
Tofighi,D.,& Kelley, K. (2016). Assessing omitted confounder bias in multilevel mediation models. Multivariate Behavioral Research, 51(1), 86-105.   
Tofighi, D., West, S. G.,& MacKinnon, D. P. (2013). Multilevel mediation analysis: The effects of

omitted variables in the 1-1-1 model. British Journal of Mathematical and Statistical

Psychology, 66(2),290-307.   
Wen,Z.，& Fan, X. (2015). Monotonicity of effect sizes: Questioning kappa-squared as mediation effect size measure.Psychological Methods, 20(2),193-203.   
Woodworth, R. S. (1928). Dynamic psychology. In C. Murchison (Ed. ), Psychologies of 1925. Worcester, MA: Clark University Press.   
Yuan, K.-H., Cheng, Y., & Maxwell, S. (2014). Moderation analysis using a two-level regression model. Psychometrika, 79(4), 701-732.   
Yuan,Y.,& MacKinnon, D. P. (2014).Robust mediation analysis based on median regression. Psychological Methods,19(1),1-20.   
Zu,J.,& Yuan, K.-H. (2o10). Local influence and robust procedures for mediation analysis. Multivariate Behavioral Research,45(1),1-44.

# A Review of the Methodological Research

# on the Mediation Effect in Chinese Mainland

WEN Zhonglin ’, FANG Jie ²,XIE Jinyan 1, OUYANG Jinying 1 (1 Center for Studies of Psychological Application & School of Psychology, South China Normal University, Guangzhou 510631, China) (² Department of Applied Psychology, Guangdong University of Finance & Economics, Guangzhou 510320, China)

Abstract: The mediation effect analysis is able to reveal the process and mechanism of the impact of independent variables on a dependent variable.As an important statistical method, the mediation effect analysis has become a hot topic in methodology research in the last twenty years. The development of domestic research on the methodology of mediation effect was systematically reviewed from the five aspects, including testing method, effect size, the mediation effect test of categorical variables and longitudinal data, and model expansion. Specifically, model expansions include multiple mediation models, multilevel mediation models, moderated mediation model and mediated moderation model. Finally, recent progresses of foreign methodological studies on mediation effect and the future research directions were discussed.

Key Word: mediation effect, test method, effect size,model expansion,categorical variable, longitudinal data