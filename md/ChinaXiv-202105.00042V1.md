# 随机截距潜在转变分析(RI-LTA) 个案自我转变与个案间差异的分离

温聪聪 朱红

(厦门大学国际学院，厦门361102） (北京大学教育学院，北京 100871)

摘要传统的潜在转变分析属于单水平分析，但其同样也可以看作二水平分析。Muthen 和Asparouhov 就以二水平分析的视角在单水平分析框架内提出了随机截距潜在转变分析(RILTA)，其中跨时间点产生的自我转变可以看作在水平1进行分析，跨时间点不变的个案间差异可以看作在水平2进行分析，使个案的自我转变和个案间的初始差异分离，避免了高估保留在初始类别的概率。某精英研究型大学 2016级本科生的追踪调查数据被用于演示使用随机截距潜在转变分析的过程。该方法的最大优势是通过引入随机截距避免了高估保留在本组别的转变概率。未来研究可以运用蒙特卡洛模拟研究探究随机截距潜在转变分析模型的适用性，也可以以多水平分析的思路为灵感，探究多水平随机截距潜在转变分析在统计软件中的实现。

关键词潜在转变分析，随机截距潜在转变分析，单水平分析，多水平分析，蒙特卡洛模拟研究

# 一、研究背景

传统的分组研究方法大多数都聚焦于已知变量，如性别、专业、年龄等。近年来，聚焦于个案的混合模型越来越受到研究者的青睐(Collins&Lanza,2009)。聚焦于变量的研究方法是为了通过已知分组变量确定可观测子样板之间的差异，那么聚焦于个案的潜在类别分析则是为了确定不可观测子样板之间的差异(Wang&Wang,2019)。

潜变量混合模型的鼻祖是潜在类别分析(latent class analysis,LCA)，在 1950 年由Lazarsfeld 提出，并由Lazarsfeld、Henry、Goodman 等人进一步发展推广。聚焦于个案的聚类研究方法不仅限于潜在类别分析，传统的K均值聚类(K-means clustering)法一度被认为是对数据样本中个案分类的较好方法，至今仍有许多国内外学者在使用此方法进行研究。不过，Magidson 和Vermunt 运用模拟数据对两种研究方法进行了比较，认为潜在类别分析法明显优于聚类分析法(Magidson& Vermunt,2002)。而当所研究数据样本为纵贯数据，存在多个时间点时，那么就需要使用潜在类别分析的衍生模型——潜在转变分析(latent transition analysis,LTA)。自上世纪90 年代开始，潜在转变分析方法逐渐进入国外研究者的视野(Collins &Wugalter,1992)，被应用于许多社会科学与行为科学研究(Dominic et al.,2017; Jagenow et al.

2015; Pan et al.,2017; Ryoo et al.,2018)，医学与公共卫生研究(Cochran et al.,2015; Cosden etal.,2015; Kenzik et al.,2015),和教育研究中(Liu et al.,2016;Ryoo et al.,2015)。我国研究者使用潜在转变分析始于 2011年，吴鹏和刘华山(2011）在中国心理学会成立90 周年纪念大会暨第十四届全国心理学学术会议上首次引入了潜在转变分析，介绍该方法如何应用于初中生攻击行为研究。2014年，吴鹏等人(2014)在《心理科学》期刊发表了几乎同名研究，探究了湖北省某中学276 名初二升初三中学生存在的三种攻击模式。随后，潜在转变分析也被应用于研究香港中学生的自我伤害行为(胡俊，张敏强,2013；王碧瑶等,2014；王碧瑶等,2015)，山东省济南市初中生受同伴侵害的状况(杨晓霞等,2020)，青少年的网络成瘾发展趋势(谢晋艳等,2018)，研究湖北地区大学生的自杀风险(刘爱楼，欧贤才,2018)，研究美国 50 岁以上老年人的孤独感及其影响因素(吴国婷等,2017；吴国婷等,2018)，以及我国 25 省成年人存在抑郁症的状况和发展趋势(廖友国，连榕,2020)。潜在转变分析已经成为国内外心理学、社会学研究领域一种较为常用的研究方法。但由于潜在转变分析的使用流程存在争议，缺乏一致的使用标准，导致在使用该方法的过程中会受研究者主观影响。目前存在较多争议的方面是使用该方法应该遵循的流程，应当报告哪些估计结果和统计量结果，如何解释最终解的有效性。

潜在转变分析模型可以用下式来表示(Nylund,2007; Wang& Wang,2019)。其中,Tct|c(t-1)表示个案在归属时间点t-1时的类别 $c _ { ( t - 1 ) } = k$ 的前提下，在时间点t转变到类别 $c _ { t } = m$ 的概率。C为 $c _ { t }$ 和 $c _ { ( t - 1 ) }$ 的类别数，二者一般相等。为了使 $c _ { t }$ 在 $c _ { ( t - 1 ) }$ 上做回归， $c _ { t }$ 的最后一个类别被默认设为参照组。由于 $c _ { ( t - 1 ) }$ 在模型中也是一个多分类自变量，需要使用多分类logistic回归，所以需要创造C-1个虚拟变量 $\mathbf { d } _ { 1 } , \mathbf { d } _ { 2 } , \ldots . . \mathbf { d } _ { \mathrm { { c } - 1 } }$ 作为logits的指标，此时 $d _ { c }$ 也为0，被设为参照组。 $\alpha _ { m }$ 为转变到时间点t的类别m时的截距， $\beta _ { m k } d _ { k }$ 为个案在时间点t相对于参照组 $c _ { t } \mathrm { = C }$ ，属于类别m的概率与在时间点t-1相对于参照组 $c _ { ( t - 1 ) } { = } \mathrm { C }$ ，属于类别k的概率的比数比再取对数。对于每个时间点 $\mathrm { t } { = } 1 , 2 , { \ldots } \mathrm { t } .$ ，分别有C-1个 $\alpha$ 和C-1个 $\beta$ 参数需要估计。如果模型中还需要引入分类协变量(covariate)，那么就需要再加入 $\cdot \gamma _ { m } x$ 项和 $\gamma _ { c t } x$ ，协变量的最后一个类别也是被设为参照组。

$$
\begin{array} { r } { \tau _ { c t | c ( t - 1 ) } = P \big ( c _ { t } = m \big | c _ { ( t - 1 ) } = k \big ) = \frac { \exp { ( \alpha _ { m } + \beta _ { m k } d _ { k } + \gamma _ { m } x ) } } { c - 1 } } \\ { \frac { 1 + \sum \exp ( \alpha _ { c t } + \beta _ { c t k } d _ { k } + \gamma _ { c t } x ) } { c _ { t } = 1 } } \end{array}
$$

潜在转变分析可以被看作是单水平(single-level)分析，探究的是样本在不同时间点上的分组情况和各类别的转变情况。模型暗含一个假设，即观测指标变量跨时间点的相关性被潜在类别变量间的相关性完全解释。同时，潜在转变分析也可以被看作是二水平(two-level)分析，其中跨时间点产生的自我转变在水平1进行分析，跨时间点不变的个案间差异在水平2进行分析(Muthen&Asparouhov,2020)。二水平分析可以得到更为准确的转变概率，因为它把个案的自我转变和个案间的初始差异进行分离，使潜在类别变量间的相关性只解释跨时间点产生的自我转变。这一想法曾在多篇文献中被提出，例如有关潜在特质因子-潜在类别建模(latent trait-state modeling)的文章(Kenny & Zautra,1995; Cole et al.,2005; Eid et al.,2017)把不变的个案间差异看作由一个连续潜变量表示的潜在特质因子；Hamaker等人以交叉滞后面板建模(cross-lagged panelmodeling)为例，提倡把不变的个案间差异（随机截距）分离，使所有前测时间点只影响各自相邻下一个后测时间点的交叉滞后关系不受个案间差异的影响(Hamaker etal.,2015)。Kenny 和 Zautra(1995)最早提出了要将潜在特质因子和潜在类别分离。在他们提出的模型中，观测指标是潜在特质因子、潜在类别和代表着测量误差的残差的加和，最重要的特点是潜在特质因子直接影响观测指标，不直接影响潜在类别。如此设定后，潜在类别不受潜在特质因子影响，意味着潜在类别间的关系不受跨时间点不变的个案间差异的影响。Kenny 和 Zautra 以及Hamaker 等人的研究的共同点是观测指标是连续变量。而当观测指标和潜在变量都是分类变量时，Eid 和Langeheine (1999;2003)研究了潜在特质因子-潜在类别建模，由属于不同时间点的潜在类别变量和潜在类别变量特质因子一同影响分类观测指标。这一模型本质是随机截距潜在转变分析，但在当时并没有使用这一名称。总之，由于普通潜在转变分析没有分离出跨时间点不变的个案间差异，可能导致得出有偏误的模型参数估计结果，尤其是较大偏误的潜在类别转变概率结果。直到 2020 年，Muthen 和 Asparouhov 正式提出了随机截距潜在转变分析模型，在单水平分析中利用二水平分析的思想实现了个案自我转变与个案间差异的分离，这一模型的提出标志着潜在转变分析进入了一个新的发展阶段。

本文首先希望简要介绍随机截距潜在转变分析模型，让国内的研究者对这一新方法有所了解和认识。其次，一方面运用某精英研究型大学2016级本科生的追踪调查数据演示使用随机截距潜在转变分析的过程，通过这一实例探究普通潜在转变分析究竟如何高估了转变概率，让读者了解随机截距潜在转变分析相对传统方法的优势。国内目前尚未有研究运用随机截距潜在转变分析模型来拟合数据样本。另一方面，运用蒙特卡洛模拟原模型的方式验证本例中随机截距潜在转变分析模型估计参数的效果，演示如何检验随机截距潜在转变分析在特定情境中的有效性，而目前国内外尚未有研究运用蒙特卡洛模拟实际数据的方法检验随机截距潜在转变分析。最后，通过引入入学方式协变量，演示如何在随机截距潜在转变分析模型框架中进行多群组分析和交互效应分析，为随机截距潜在转变分析模型的应用和拓展提供参考。总之，本研究希望在国内首次引入随机截距潜在转变分析模型，让更多的研究者了解这一方法，帮助他们使用这一方法进行分析和应用。本文运用某精英研究型大学 2016 级本科生学习动机的追踪调查数据实例演示如何使用随机截距潜在转变分析，在文末列出相应的Mplus 语法示例，也正是希望达到这一目的。

# 二、研究模型介绍

在此部分，将对随机截距潜在转变分析模型进行简要介绍，希望能让国内研究者对这一新方法有所了解和认识。

图1展示了时间点数量为2时的随机截距潜在转变分析模型路径图。其中 $f$ 代表随机截距，yll,y12..,ylp代表时间点t 上的p 个观测指标，y21,y22.,y2p代表时间点t上的p 个观测指标，ci代表时间点ti的潜在类别变量，c2代表时间点tz的潜在类别变量。随机截距f既可以是数个连续的潜在因子，也可以是一个多分类潜变量，但根据 Muthen和 Asparouhov 文章中情绪案例和约会案例的研究结果，随机截距 $f$ 为连续的潜在因子时的模型拟合指标优于随机截距f为多分类潜变量时的模型拟合指标，使用连续的潜在因子作为随机截距是更好的选择(Muthen&Asparouhov,2020)。为了简化模型分析，减少不必要的运算时间，随机截距潜在因子的数量被设定为1。另外，模型中一些隐含的假设也需要进行说明，例如模型假设个案间初始差异不随时间改变，时间点ti 的p个观测指标的因子载荷λi,λ2...λp被设定和时间点tz的p个因子载荷两两对应完全相等;为了简化分析，对于不同的潜在类别，对应的因子载荷也被设为同指标完全相等；随机截距 $f$ 直接影响各时间点上的各观测指标，不会直接影响潜在类别变量 $\mathbf { c } _ { 1 }$ ， $\mathbf { c } _ { 2 }$ ，但却会解释一部分跨时间点的相关性，也就是个案间差异，从而影响转变概率；在随机截距潜在转变分析中，如果存在 $\mathfrak { n }$ 个时间点，那么 $\mathbf { c } _ { \mathrm { n } }$ 有可能影响 $\mathbf { c } _ { \mathrm { n } } .$ （201，也有可能影响 $\mathbf { c } _ { \mathrm { n } - 2 }$ ， $\mathbf { c } _ { \mathrm { n } - 3 }$ ，但为了简化分析，模型仅假设 $\mathbf { c } _ { \mathrm { n } }$ 影响 $\mathbf { c } _ { \mathrm { n - 1 } }$ ；潜在转变分析的指标可以是连续变量或是虚拟变量，多分类变量，定序多分类变量，计数变量等，但当观测指标的数量与每个观测指标的填答类型较多时，总的填答类型情况会过多导致有的填答情况没有或只有极少数人填答，影响潜在转变分析模型的识别，所以应当尽量使用填答类型较少的虚拟变量作为观测指标。

![](images/e126b1ce32f8b12a360325c8431f04a8581d64b89865e166e46847eb7c1451f1.jpg)  
图1时间点数量为2时的随机截距潜在转变分析模型路径图

随机截距潜在转变分析中的随机截距 $f$ 是关键。如果观测指标在随机截距上的因子载荷较大，说明观测指标概率较大，个案在该观测指标上的初始差异较大。从这一角度来看，随机截距可以看作是吸收了模型中的测量不等性(measurement noninvariance)。正因为观测指标上的差异较大，各类别之间的区分度较高，这部分差异被随机截距吸收并且不影响潜在类别变量，所以潜在类别间转变概率矩阵的非对角线转变概率会较高。而在普通的潜在转变分析中，各类别之间的高区分度没有被随机截距吸收，直接影响了潜在类别的转变概率，所以各类别间转变概率矩阵的非对角线转变概率会较低，对角线转变概率（保留在初始类别概率)较高。根据 Muthen 和 Asparouhov 文章中的实例和蒙特卡洛模拟研究，随机截距潜在转变分析模型的模型拟合指标总是优于普通潜在转变分析，所以可以认为普通潜在转变分析高估了不同类别保留在初始类别的概率(Muthén＆ Asparouhov,2020)。

如果用数学公式来表示随机截距潜在转变分析模型，那么应用下式表示：

$$
\begin{array} { r } { { l o g i t } [ P ( U _ { p i t } { = } 1 ) \mid C _ { i t } { = } j , f _ { i } ] = \alpha _ { p j } + \lambda _ { p } f _ { i } } \end{array}
$$

其中 $U _ { p i t }$ 为属于个案 $i$ ，时间点 $\mathbf { \chi } _ { t }$ 的第 $p$ 个虚拟变量观测指标， $\boldsymbol { C } _ { i t } { = } j$ 表示属于个案 $i$ ，时间点 $t$ 的第 $j$ 个潜在类别， $\alpha _ { p j }$ 代表在潜在类别变量观测指标上的模型参数， $\lambda _ { p }$ 表示第 $p$ 个观测指标的因子载荷， $f _ { i }$ 表示属于个案 $i$ 的因子得分，因子的分布为 $N ( 0 , 1 )$ 。在普通潜在转变分析中，模型要分析观测指标以类别 $j$ 为前提条件的条件概率 $\operatorname { P } ( U _ { p i t } { = } 1 \mid C _ { i t } { = } j )$ ，而在随机截距潜在转变分析模型中，观测指标的条件概率不仅要以类别 $j$ 为前提条件，还要以 $f _ { i }$ 为前提条件。在观测指标为虚拟变量时， $f _ { i }$ 的正因子得分越高，代表回答 $U _ { p i t } { = } 1$ 的概率越高; $f _ { i }$ 的负因子得分越高，代表回答 $U _ { p i t } { = } 0$ 的概率越高。所以，绝对值大的正负因子得分意味着不同类别间差异较大，不会轻易转变类别。这也说明如果数据是基于随机截距潜在转变分析生成的，普通潜在转变分析会倾向于高估保留在初始类别的概率。

# 三、研究步骤

随机截距潜在转变分析目前仅可以在Mplus 软件中执行，需要使用最新的Mplus8.5 版本，模型估计方法默认采用最大似然估计法(maximum likelihood)，可以分析纵贯跨时序数据或是进行蒙特卡洛模拟研究。在 Mplus 软件中进行随机截距潜在转变分析的步骤可以归纳为以下四步：

1、针对不同的时间点分别进行潜在类别分析(LCA)，探究每个时间点上的样本包含的类别数。2、进行普通潜在转变分析和随机截距潜在转变分析，探究逐渐引入不同时间点潜在类别变量、随机截距后样本包含的类别数以及转变概率。将所得的模型拟合指数结果作比较，得出最优模型。3、利用上一步骤所得最优模型保存下来的参数估计结果进行蒙特卡洛模拟研究，验证特定情境下待分析模型估计各项参数的有效性。4、根据已有的理论假设或是实际的研究需要，可以引入背景协变量(covariate)，远端结果变量(distal outcome)进行分析，或是做多群组分析(multiple-group analysis)、马尔科夫链变动-保留分析(mover-stayer analysis)、多水平随机截距潜在转变分析、跨时序因子分析(longitudinal factoranalysis)，对数据样本进行更深层次的探究。

研究者在进行数据分析时不一定要完全参照以上四个步骤。如果需要进行随机截距潜在转变分析，步骤一和步骤二必须要进行，步骤三和步骤四可以选择是否进行。文章的下一部分将以某精英研究型大学本科生的学习动机数据为例进行随机截距潜在转变分析的演示。

# 四、研究实例

本研究使用了某精英研究型大学2016级本科生的追踪调查数据，填写时间分别在 2016年（入学前暑假至入学后一个月）和 2018 年（大三下学期)。其中填答无缺失值的个案有 634人，本研究将使用这634人的填答作为总样本，样本分布情况如表1所示。

表1样本结构 $( N { = } 6 3 4 )$   

<html><body><table><tr><td colspan="2">变量</td><td>占总样本比率</td></tr><tr><td>性别</td><td>女</td><td>45.7%</td></tr></table></body></html>

<html><body><table><tr><td>男</td><td>54.3%</td></tr><tr><td>城市 户口类型 农村</td><td>80.4%</td></tr><tr><td>是</td><td>19.6%</td></tr><tr><td>是否独生子女 否</td><td>74.8% 25.2%</td></tr><tr><td>直辖市</td><td>16.1%</td></tr><tr><td>省会城市</td><td>16.1%</td></tr><tr><td>家庭所在地类型 地级市</td><td></td></tr><tr><td>县城或县级市</td><td>24.4%</td></tr><tr><td></td><td>26.8%</td></tr><tr><td>乡镇农村 初中或以下</td><td>16.6%</td></tr><tr><td></td><td>20.2%</td></tr><tr><td>高中或中专 父亲文化程度 大学或以上</td><td>17.2%</td></tr><tr><td></td><td>62.6%</td></tr><tr><td rowspan="3">母亲文化程度</td><td>初中或以下</td><td>22.9%</td></tr><tr><td>高中或中专</td><td>24.3%</td></tr><tr><td>大学或以上</td><td>52.8%</td></tr></table></body></html>

问卷中的学习动机量表设置内部动机和外部动机两个维度，内部动机包括挑战性和热衷性的题项，外部动机包括依赖他人评价、关注人际竞争和追求回报等方面的题项。题项使用4点计分，让学生对每项表述从“很不符合"到"很符合"进行选择。在本例中，用于估计模型参数的列联表源于4个选项，10 个观测指标，2个时间点的原始数据，这样产生了1099511627776种不同情况。由于大量的不同情况以及个别题项中的选项出现无人选择的情况(emptycell)，导致潜在转变分析模型难以识别。另外，随机截距潜在转变分析限制测量不变性， $\mathbf { c } _ { 1 }$ 和 $\mathbf { c } _ { 2 }$ 中各潜在类别的得分限制相等，随机截距 $f$ 上的因子载荷也不随时间点改变，如果类别数不统一，会使模型无法运行，结果也会产生偏移。为了解决这些问题，本研究将4点计分观测指标转换为虚拟变量，“很不符合”和“比较不符合”赋分为0，“比较符合”和“很符合”赋分为1。将观测指标转换为二分虚拟变量后，列联表的不同情况降为1048576种，有效避免了模型识别问题。量表信效度良好，克朗巴赫系数为0.70，符合统计分析的标准。学习动机量表的内容构成如表2所示。

表2学习动机量表维度与具体内容  

<html><body><table><tr><td>维度设计</td><td>题号</td><td>题项内容</td></tr><tr><td rowspan="3"></td><td>Q1</td><td>对我而言成功意味着比别人做得更好</td></tr><tr><td>Q2</td><td>成绩是推动我去努力的主要动力</td></tr><tr><td>外部动机 Q3</td><td>我希望别人发现我在学业上很出色</td></tr><tr><td></td><td>Q4</td><td>他人的肯定和赞赏是推动我去努力的主要动力</td></tr><tr><td>学习动机</td><td>Q5</td><td>我很在乎别人对我的观点怎么反应</td></tr></table></body></html>

<html><body><table><tr><td rowspan="7"></td><td>Q6</td><td>我认为表现很好但无人知晓是没有意义的</td></tr><tr><td>Q7</td><td>我乐于尝试解决复杂的问题</td></tr><tr><td>内部动机 Q8</td><td>我喜欢独立思考解决疑难</td></tr><tr><td>Q9</td><td>我乐于钻研那些全新的问题</td></tr><tr><td>Q10</td><td>我希望大学学习能够提供我增加知识与技能的机会</td></tr></table></body></html>

# 4.1 潜在类别分析(LCA)

首先使用Mplus8.5 版本软件分别在2016年和 2018年两个时间点运行潜在类别分析1，得到表3所示的输出结果。对于群组数目不同的潜在类别分析模型，对数似然值越高，模型拟合越好。从贝叶斯指数BIC来看，信息指数越小模型拟合越好。为了使各类别具有分析意义，占总样本比率低于 $3 \%$ 的潜在类别被认为不具有代表性(Ryoo etal.,2018)。在本研究中，在 2016年时间点，随着群组数目逐渐升高，对数似然值越来越高，贝叶斯指数BIC 在类别数目为3时达到最小值，数目为4时出现升高，所以类别数为3的解为最优解。在2018年时间点，随着群组数目逐渐升高，对数似然值越来越高，贝叶斯指数BIC在类别数目为4时达到最小值，数目为5时出现升高，所以类别数为4的解为最优解。

表3在两个时间点依次增加类别数目的潜在类别分析结果 $( N { = } 6 3 4 )$ （20  

<html><body><table><tr><td>时间点</td><td>类别数</td><td>对数似然值</td><td>BIC</td><td>最小类别占总样本比率</td></tr><tr><td>2016,c1</td><td>2</td><td>-2795.37</td><td>5726.23</td><td>47.0%</td></tr><tr><td>2016,c1</td><td>3</td><td>-2709.70</td><td>5625.87</td><td>10.8%</td></tr><tr><td>2016,c1</td><td>4</td><td>-2686.64</td><td>5650.71</td><td>10.5%</td></tr><tr><td>2018,c2</td><td>2</td><td>-3268.72</td><td>6672.94</td><td>43.4%</td></tr><tr><td>2018,c2</td><td>3</td><td>-3157.45</td><td>6521.36</td><td>24.3%</td></tr><tr><td>2018,c2</td><td>4</td><td>-3101.55</td><td>6480.54</td><td>7.6%</td></tr><tr><td>2018,c2</td><td>5</td><td>-3080.31</td><td>6509.03</td><td>6.3%</td></tr></table></body></html>

4.2普通潜在转变分析(LTA)和随机截距潜在转变分析(RI-LTA)

其次，将分别属于2016年时间点和2018年时间点的潜在类别变量 $\mathbf { c } _ { 1 }$ 、 $\mathbf { c } _ { 2 }$ 同时引入潜在转变分析模型和随机截距潜在转变分析模型进行分析，得到表4所示的输出结果。随机截距潜在转变分析相比普通潜在转变分析的不同是需要额外引入随机截距 $f$ 影响所有时间点上的观测变量。此时，同一观测变量在不同时间点上的因子载荷被设置为相等。从整体来看，当分析同样的类别数时，随机截距潜在转变分析比普通潜在转变分析多估计模型拥有的观测指标数目的因子载荷参数（在本例中为10个)，对数似然值相对更大，贝叶斯指数 BIC 相对更小。这说明随机截距潜在转变分析模型拟合数据样本的效果普遍优于普通潜在转变分析，有必要引入随机截距。从对数似然值来看， $\mathbf { c } _ { 1 } { = } 3$ ， $\scriptstyle \mathbf { c } _ { 2 } = 4$ 时的随机截距潜在转变分析模型取得最大值。从贝叶斯指数 BIC 来看， $\mathrm { c } _ { 1 } { = } 3$ ， $\scriptstyle \mathbf { c } _ { 2 } = 3$ 时的随机截距潜在转变分析模型取得最小值。根据 Muthen 和 Asparouhov 文章中的做法(2020)，当对数似然值和贝叶斯指数 BIC 出现1本研究实例所涉及的所有 Mplus 语法文件已经上传至OSF 官方网站，项目链接为：htps:/osf.io/8529q不同结果时，需要以贝叶斯指数 BIC 为准(Muthen&Asparouhov,2020)。此外，从模型估计的参数数目来看， $\mathbf { c } _ { 1 } { = } 3$ ， $\scriptstyle \mathbf { c } _ { 2 } = 3$ 时的随机截距潜在转变分析模型仅估计48个参数，相比估计91个参数的 $\mathrm { c } _ { 1 } { = } 3$ ， $\scriptstyle \mathbf { c } _ { 2 } = 4$ 时的随机截距潜在转变分析模型更为简洁，这也进一步提示了如何选取最优模型。综上所述，应当选取 $\mathbf { c } _ { 1 } { = } 3$ ， $\scriptstyle \mathbf { c } _ { 2 } = 3$ 的随机截距潜在转变分析结果为最优解。

表4不同潜在转变分析模型的分析结果 $\scriptstyle ( N = 6 3 4 )$ 号  

<html><body><table><tr><td>所分析模型</td><td>类别数</td><td>估计参数数目</td><td>对数似然值</td><td>BIC</td></tr><tr><td>普通潜在转变分析</td><td>C1=3,c2=3</td><td>38</td><td>-5857.19</td><td>11959.56</td></tr><tr><td>普通潜在转变分析</td><td>C1=3,c2=4</td><td>81</td><td>-5747.69</td><td>12017.99</td></tr><tr><td>普通潜在转变分析</td><td>c1=4,c2=4</td><td>55</td><td>-5780.99</td><td>11916.84</td></tr><tr><td>普通潜在转变分析</td><td>C1=5,c2=5</td><td>74</td><td>-5718.64</td><td>11914.72</td></tr><tr><td>随机截距潜在转变分析</td><td>C1=3,c2=3</td><td>48</td><td>-5725.25</td><td>11760.20</td></tr><tr><td>随机截距潜在转变分析</td><td>C1=3,c2=4</td><td>91</td><td>-5664.63</td><td>11916.40</td></tr><tr><td>随机截距潜在转变分析</td><td>C1=4,c2=4</td><td>65</td><td>-5691.77</td><td>11802.92</td></tr><tr><td>随机截距潜在转变分析</td><td>C1=5,c2=5</td><td>84</td><td>-5657.61</td><td>11857.19</td></tr></table></body></html>

然后，需要根据Mplus 输出结果对潜在类别进行分类与命名。图2展示了3个潜在类别在各个题项上的填答概率。从图中可以看出，3个类别在题项10上认为重要的概率都很高，可以区分这3个类别学习动机情况的题项为题项1至题项9。由于学习动机量表的第1-6题为外部动机（依赖他人评价、关注人际竞争和追求回报)，第7-10题为内部动机（挑战性和热衷性)，可以对3个类别进行分类命名。类别1在题项1至题项9的填答概率都相对较低，可以命名为消极组；类别2在题项1至题项9的填答概率都很高，可以命名为积极组；类别3在题项1至题项6的填答概率较低，在题项7至题项9的填答概率较高，可以命名为重视内部动机组。

图2 随机截距潜在转变分析所得3个类别在各题项上的填答概率 $( N { = } 6 3 4 )$

![](images/d4a6ad6bdabdef677dff8aae536a024bb299dc4b62758a4f0fc17e16bb00a453.jpg)

进一步研究输出结果，可以得到3个类别在两个时间点上的转变概率，如表5所示。在类别1和类别3，保留在本类别的概率变化不大；但在类别2，普通潜在转变分析保留在本类别的概率高达 $6 8 . 9 \%$ ，而随机截距潜在转变分析保留在本类别的概率降至 $3 3 \%$ ，这说明随机截距吸收了个案间的初始差异，普通潜在转变分析高估了类别2保留在本类别的概率，使用随机截距潜在转变分析是更合理的。

表53个类别在两个时间点的转变情况 $( N { = } 6 3 4 )$ （204号  

<html><body><table><tr><td colspan="3">普通潜在转变分析</td><td colspan="2">随机截距潜在转变分析</td></tr><tr><td>类别转变情况</td><td>个案数</td><td>转变概率</td><td>个案数</td><td>转变概率</td></tr><tr><td>C1#1-→c2#1</td><td>49</td><td>74.1%</td><td>58</td><td>73.9%</td></tr><tr><td>c1#1-→c2#2</td><td>16</td><td>24.8%</td><td>11</td><td>14.7%</td></tr><tr><td>C1#1→c2#3</td><td>1</td><td>1.1%</td><td>9</td><td>11.4%</td></tr><tr><td>总计</td><td>66</td><td>100%</td><td>78</td><td>100%</td></tr><tr><td>C1#2→c2#1</td><td>62</td><td>24.4%</td><td>37</td><td>55.5%</td></tr><tr><td>C1#2→C2#2</td><td>173</td><td>68.9%</td><td>22</td><td>33.0%</td></tr><tr><td>C1#2→c2#3</td><td>17</td><td>6.7%</td><td>8</td><td>11.5%</td></tr><tr><td>总计</td><td>252</td><td>100%</td><td>67</td><td>100%</td></tr><tr><td></td><td>64</td><td>20.4%</td><td>109</td><td></td></tr><tr><td>C1#3-→c2#1</td><td></td><td></td><td></td><td>22.4%</td></tr><tr><td>C1#3→C2#2</td><td>101</td><td>31.8%</td><td>121</td><td>24.7%</td></tr><tr><td>C1#3-→C2#3</td><td>151</td><td>47.8%</td><td>259</td><td>52.9%</td></tr></table></body></html>

<html><body><table><tr><td>总计</td><td>316</td><td>100%</td><td>489</td><td>100%</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# 4.3蒙特卡洛模拟研究

在此部分，利用随机截距潜在转变分析保存下来的参数估计结果生成新的数据组，设定原模型为待分析模型进行蒙特卡洛模拟研究，验证该情境下随机截距潜在转变分析模型估计各参数的有效性。模型设定仍然是20个虚拟变量观测指标，ci和 $\mathbf { c } _ { 2 }$ 类别数均为3，总样本量仍为634，生成数据组数量为500 组，模型分析类型为混合模型。由于加入了随机截距，需要额外进行一次定积分计算，所以在Mplus分析指令中也需要进行相应设定。

500 组数据分析的部分参数估计结果如表6所示。选取的参数包括随机截距上的第一个和第十个因子载荷 $\lambda _ { 1 }$ 和 $\lambda _ { 1 0 }$ ，时间点ti的潜在类别变量 $\mathbf { c } _ { 1 }$ 中第一个类别的第二个截距ci#1V2，时间点 $\mathbf { t } _ { 1 }$ 的潜在类别变量 $\mathbf { c } _ { 1 }$ 中第二个类别的第十个截距 $\mathbf { c } _ { 1 } \# 2 \mathbf { v } _ { 1 0 }$ ，时间点 $\mathbf { t } _ { 1 }$ 的潜在类别变量ci中第三个类别的第四个截距 $\mathrm { c } _ { 1 } \# 3 \ \mathrm { v } _ { 4 }$ ，潜在类别变量 $\mathbf { c } _ { 1 }$ 中相对于参照类别（默认为最后一个类别）属于第二个类别的比数对数 $\mathbf { c } _ { 1 } \# 2$ ，潜在类别变量 $\mathbf { c } _ { 2 }$ 中相对于参照类别属于第二个类别的比数对数 $\mathbf { c } _ { 2 } \# 2$ 。从估计值和偏差来看，随机截距潜在转变分析能较为准确地估计该情境条件下的数据组，只有 $\lambda _ { 1 0 }$ 的偏差达到0.05，且该偏差占真值的比率不超过 $5 \%$ ，属于可以接受的范围。从均方误差来看，各参数的均方误差较小，只有 $\lambda _ { 1 0 }$ 的均方误差稍大，达到了0.2。从标准差和平均标准误的比值来看，比值在 $0 . 9 5 \sim 1 . 0 5$ 的范围内波动，属于可以接受的范围(Asparouhov& Muthén,2014)。从 $9 5 \%$ 置信区间真值覆盖率来看，绝大多数参数的覆盖率较好，只有 $\mathbf { c } _ { 1 } \# 2 \ \mathbf { v } _ { 1 0 }$ 的真值覆盖率为0。根据以上的结果可以看出，大部分参数都满足偏差、均方误差、标准差/平均标准误、 $9 5 \%$ 置信区间真值覆盖率的可接受标准，参数估计效果较好。不过 $\lambda _ { 1 0 }$ 和 $\mathbf { c } _ { 1 } \# 2 \ \mathbf { v } _ { 1 0 }$ 的估计效果较为不理想，说明观测指标 $\mathbf { y } _ { 1 0 }$ 和 $\mathbf { y } _ { 2 0 }$ 出现了问题。进一步检查输出结果发现，3个类别在题项10上的填答概率都很高，尤其是类别2和类别3达到了1，也就是说这两个类别中 $100 \%$ 的学生在题项10 回答“符合”。缺乏0的填答会产生天花板效应，最终导致相关参数的异常估计，这也就是出现了 $\mathbf { c } _ { 1 } \# 2 \mathbf { v } _ { 1 0 } - 9 9 6 . 3 4$ 的异常截距值和 $\lambda _ { 1 0 }$ 出现较大偏差的原因。再检查 $\mathbf { c } _ { 1 } \# 3 \ \mathbf { v } _ { 1 0 }$ 的估计结果，也是达到了-286.78的异常值。不过，这样的天花板效应只会影响相关观测指标参数的估计值，并不会对个案分组和转变概率造成影响。

表6基于实际研究数据的蒙特卡洛模拟研究的部分参数估计结果(N=634)  

<html><body><table><tr><td></td><td>21</td><td>210</td><td>C1#1 V2</td><td>C1#2 V10</td><td>C1#3 V4</td><td>C1#2</td><td>C2#2</td></tr><tr><td>真值</td><td>1.27</td><td>1.41</td><td>-0.04</td><td>-996.34</td><td>0.63</td><td>-2.00</td><td>-0.76</td></tr><tr><td>估计值</td><td>1.27</td><td>1.46</td><td>-0.03</td><td>-996.34</td><td>0.64</td><td>-2.04</td><td>-0.75</td></tr><tr><td>偏差</td><td>0</td><td>0.05</td><td>0.01</td><td>0</td><td>0.01</td><td>0.04</td><td>0.01</td></tr></table></body></html>

<html><body><table><tr><td>均方误差</td><td>0.02</td><td>0.20</td><td>0.04</td><td>0</td><td>0.02</td><td>0.09</td><td>0.03</td></tr><tr><td>标准差/平均标准误</td><td>0.96</td><td>1.05</td><td>0.96</td><td>-</td><td>0.97</td><td>0.89</td><td>0.98</td></tr><tr><td>95%置信区间真值覆盖率</td><td>93.8%</td><td>94.8%</td><td>95.2%</td><td>0</td><td>95.6%</td><td>96.8%</td><td>94.0%</td></tr></table></body></html>

# 4.4引入协变量进行多群组分析和交互效应分析

进行完蒙特卡洛模拟研究后，一些研究者不仅仅满足于得出分组结果和转变概率，可能还希望引入其他的背景变量进行多群组分析或是探究这些背景变量是否会影响转变概率。在这一部分，将引入入学方式协变量分别进行多群组分析和交互效应分析。入学方式协变量共有3个类型，分别为高考统招，自主招生，保送和特长生。为了能让模型更好地被识别，减轻运算负担，将协变量拆分为2个虚拟变量作为新的协变量dummy1和dummy2。dummyl中1为高考统招，0为其他方式；dummy2中1为自主招生，0为其他方式；如果两个新的协变量上都为0，那么就属于保送和特长生。

首先引入协变量进行多群组分析，模型可以分为测量不变和测量不等两种情况。在测量不变情况下，仅仅在随机截距潜在转变分析模型的基础上引入两个虚拟协变量，让它们影响 $\mathbf { c } _ { 1 }$ 和 $\mathbf { c } _ { 2 }$ ；而在测量不等情况下，不仅设定两个虚拟协变量影响潜在类别变量，还需要额外设定两个虚拟协变量直接影响各观测指标。运用两种模型设定进行分析，结果如表7所示。由于测量不变模型嵌套于测量不等模型，所以可以使用卡方变化检验分析。两模型的参数数目相差60，所以自由度变化值为60；依据对数似然值和修正缩放指数，依照 Satorra 等人的方法(Satorra& Bentler,2010)计算出卡方变化值 941，结合自由度变化值得出显著性$p { < } 0 . 0 0 1$ ，拒绝原假设，卡方变化检验指向测量不等模型为更优模型。但测量不变模型的贝叶斯指数BIC更小，且参数数目较少，模型更为简洁，所以后续检验交互效应时将使用此测量不变模型。检查输出结果后发现，绝大多数协变量与各潜在类别间的回归系数不显著，只有 $\mathbf { c } _ { 1 } \# 1$ 在dummy2上的回归系数显著，为-2.364。这说明通过自主招生项目进入该院校的学生属于消极组的比数对数比通过保送或特长进入该院校的学生低2.364，自主招生项目学生相对保送、特长生属于消极组的人数显著更少。

表7引入入学方式协变量后的多群组分析结果 $( N { = } 6 3 4 )$   

<html><body><table><tr><td>所分析模型</td><td>参数数目</td><td>对数似然值</td><td>BIC</td><td>卡方变化</td><td>自由度变化</td><td>p</td></tr><tr><td>随机截距潜在转变分析， 测量不变</td><td>56</td><td>-5716.87</td><td>11795.06</td><td></td><td></td><td></td></tr><tr><td>随机截距潜在转变分析， 测量不等</td><td>116</td><td>-5673.43</td><td>12095.30</td><td>941</td><td>60</td><td><.001</td></tr></table></body></html>

其次引入协变量进行交互效应分析。此处的交互效应是指协变量与潜在类别 $\mathbf { c } _ { 1 }$ 的交互效应影响潜在类别 $\mathbf { c } _ { 2 }$ 。如果结果支持交互效应，那就说明入学方式协变量还可以影响转变概率。模型可以分为三种情况：引入协变量直接影响随机截距f；引入协变量直接影响随机截距 $f$ 和 $\mathbf { c } _ { 1 } , \mathbf { c } _ { 2 }$ ；引入协变量不但直接影响随机截距 $f$ 和 $\mathbf { c } _ { 1 }$ 、 $\mathbf { c } _ { 2 }$ ，还额外考虑协变量与 $\mathbf { c } _ { 1 }$ 的交互效应影响 $\mathbf { c } _ { 2 }$ 。运用三种模型设定进行分析，结果如表8所示。由于三种模型互相嵌套，所以可以使用卡方变化检验分析模型。依照 Satorra 等人的方法进行计算(Satorra＆ Bentler,2010)，两组模型比较的显著性 $p { < } 0 . 0 0 1$ ，拒绝原假设，卡方变化检验指向交互效应模型为更优模型。但协变量影响 $f$ 模型的贝叶斯指数BIC明显更小，且参数数目较少，模型更为简洁，所以协变量影响 $f$ 模型为最优模型。检查输出结果后发现，随机截距 $f$ 在 dummyl 和dummy2上的回归系数均不显著，说明不同入学方式对 $f$ 的影响无显著差异。dummyl 和dummy2 通过 $\mathbf { c } _ { 1 }$ 影响 $\mathbf { c } _ { 2 }$ 的各项回归系数也都不显著，说明确实不需要引入交互效应。

表8引入入学方式协变量后的交互效应分析结果 $( N { = } 6 3 4 )$   

<html><body><table><tr><td>所分析模型</td><td>参数数目</td><td>对数似然值</td><td>BIC</td><td>卡方变化</td><td>自由度变化</td><td>p</td></tr><tr><td>协变量影响f</td><td>50</td><td>-5725.02</td><td>11772.65</td><td></td><td></td><td></td></tr><tr><td>协变量影响f和ci、c2</td><td>58</td><td>-5716.83</td><td>11807.87</td><td>29</td><td>8</td><td><.001</td></tr><tr><td>协变量影响f和cI、c2, 交互效应</td><td>70</td><td>-5713.66</td><td>11878.96</td><td>1237</td><td>12</td><td><.001</td></tr></table></body></html>

# 五、方法总结与展望

通过前文所述，随机截距潜在转变分析可以被认为是传统潜在转变分析的推进和发展，其最大贡献是通过引入随机截距 $f$ 吸收不随时间点变化而变化的个案间差异避免了高估转变概率矩阵对角线上潜在类别保留在初始类别的概率。相比普通潜在转变分析，随机截距潜在转变分析的模型拟合指数结果往往更好，这也说明多数数据样本中的个案间有显著的初始差异。为了验证随机截距潜在转变分析估计模型参数的有效性，需要保存参数估计结果，用于蒙特卡洛模拟研究。为了进行多群组比较或是研究特定背景变量的交互作用，可以引入协变量进行进一步研究。本研究中运用有关某精英研究型大学2016级本科生学习动机的追踪调查数据，演示了使用随机截距潜在转变分析的整个过程，文章附录也附上了本研究中各种待分析模型的Mplus语法，希望能为研究者们提供借鉴与参考。

同时，随机截距潜在转变分析作为2020 年提出的新方法，其衍生模型较多，应用于实证研究的效果尚待检验，也有许多领域需要进一步研究。例如，当卡方变化检验、对数似然值与贝叶斯指数 BIC 结果相悖时，模型如何选取有待进一步考证；模型中使用二分虚拟变量指标可以帮助模型的识别和快速运算，但可能造成天花板或地板效应，造成模型参数估计的异常，如何选取因变量类型是一个值得研究的问题；随机截距潜在转变分析模型假设同一观测指标在不同时间点随机截距f上的因子载荷完全相等，这会造成因子得分的增加对各个时间点的影响相同，但显然这一简洁的模型设定很可能不符合实际数据样本；根据 Muthén和Asparouhov 文章中的阅读熟练度实例，跨时序因子分析(longitudinal factor analysis)模型的各项模型拟合指数均要优于随机截距潜在转变分析模型，那么仍然选择随机截距潜在转变分析模型解释数据样本的依据需要思索(Muthen & Asparouhov,2019)；Muthen 和 Asparouhov 文章中的蒙特卡洛模拟研究只探究了有限的情况，未来研究仍可以针对随机截距潜在转变分析模型所需的样本量、适宜的时间点数目、适宜的观测指标数目、适宜的潜在类别数目进行探究。此外，随机截距潜在转变分析模型是以多水平分析的思路为灵感，实际进行的仍然是单水平分析，未来该模型必将被引入多水平分析。目前在 Mplus8.5 最新版本中仍然无法运行多水平随机截距潜在转变分析，这也是该软件今后更新发展的方向。

# 参考文献

胡俊，张敏强.(2013年11月).青少年自我伤害行为的潜在类别及其转变分析．心理学与创新能力提升—第十六届全国心理学学术会议论文集(pp.374-375)，江苏，南京.  
廖友国，连榕.(2020).成人抑郁症状的潜在转变分析：四年追踪研究．中国临床心理学杂志,03,518-522.doi:10.16128/j.cnki.1005-3611.2020.03.018.  
刘爱楼，欧贤才.(2018).大学生自杀风险的类别转变:潜在转变分析．西南大学学报(社会科学版),02,104-111+193.doi:10.13718/j.cnki.xdsk.2018.02.012.  
王碧瑶，张敏强，张洁婷，胡俊.(2014年10月).青少年问题行为的类型:基于潜在转变分析的结果．第十七届全国心理学学术会议论文摘要集(pp.742-745)，北京.  
王碧瑶，张敏强，张洁婷，胡俊，攸佳宁，梁耀坚.(2015).青少年自我伤害行为的潜在转变分析:一项纵向研究．心理科学,06,1368-1376.doi:10.16719/j.cnki.1671-6981.20150613.  
吴国婷，张敏强，倪雨菡，杨亚威，漆成明，吴健星.(2017年11月).老年人孤独感的转变及其影响因素：基于潜在转变分析．中国心理学会第二十届全国心理学学术会议--心理学与国民心理健康摘要集(pp.722-723)，重庆.  
吴国婷，张敏强，倪雨菡，杨亚威，漆成明，吴健星.(2018).老年人孤独感及其影响因素的潜在转变分析.心理学报,09,1061-1070.  
吴鹏，刘华山.(2011年10 月).攻击性初中生的类别及其转变:一个潜在类别模型的应用．增强心理学服务社会的意识和功能——中国心理学会成立90周年纪念大会暨第十四届全国心理学学术会议论文摘要集(pp.139)，陕西，西安.  
吴鹏，刘华山，陈京军，谢继红.(2014).攻击性初中生的类别转变:潜在转变分析．心理科学,05,1167-1173.doi:10.16719/j.cnki.1671-6981.2014.05.023.  
谢晋艳，黎光明，侯桂云，甄锋泉.(2018年11月).基于LPA的青少年网络成瘾:潜在转变分析．第二十一届全国心理学学术会议摘要集(pp.644-646)，北京.  
杨晓霞，陈亮，曹衍淼，毕馨文，陈光辉，张文新.(2020).青少年早期同伴侵害的亚类别及其稳定性:个体定向的分析．心理发展与教育,02,146-156.doi:10.16187/j.cnki.issn1001-4918.2020.02.03.  
Asparouhov,T.,& Muthen, B. (2014).Multiple-group factor analysis alignment. Structural Equation Modeling: AMultidisciplinary Journal,21(4),495-508.  
Cochran,G.,Field,C.,&Caetano,R.(Ol5).Changes inclassesofinjury-relatedrisksandconsequencesofrisk-level drinking: Alatent transition analysis.The journal of behavioral health services &research,42(3),355-

366. Cole,D.A.,Martin,N.C.,& Steiger,J. H.. (2oo5).Empirical and conceptual problems with longitudinal traitstate models: Introducing a trait-state-occasion model. Psychological Methods,10(1), 3. Collins,L.M.,&Lanza,S.T.(20o9).Latentclassand latent transition analysis: With applications in the social, behavioral,and health sciences (Vol. 718). Hoboken,NJ: John Wiley & Sons. Collins,L. M., & Wugalter, S.E. (1992).Latent class models for stage-sequential dynamic latent variables. Multivariate Behavioral Research, 27(1),131-157. Cosden,M.,Larsen,J.L.,Donahue,M.T.,& Nylund-Gibson,K. (2015).Trauma symptoms for men and women in substance abuse treatment: A latent transition analysis. Journal ofsubstance abuse treatment, 50,18-25. Eid,M.,Holtmann,J.,Santangelo,P.,&Ebner-Priemer, U.(2o17).Onthe definitionoflatent-state-trait models with autoregressive effects. European Journal of Psychological Assessment. Eid,M.& Langeheine,R. (1999).The measurement of consistency and occasion specificity with latent class models: A new model and its applicaton to the measurement of affect. Psychological Methods,4,100-116. Eid,M.& Langeheine,R. (2O03). Separating stable from variable individuals in longitudinal studies by mixture distribution models.Measurement: Interdisciplinary Research and Perspectives,1,179-206. Hamaker,E.L. Kuiper,R. M.,& Grasman, R. P. (2015). A critique of the cross-lagged panel model. Psychological methods,20(1),102. Jagenow, D.,Raufelder,D.,& Eid,M. (2015).The development of socio-motivational dependency from early to middle adolescence.Frontiers in psychology, 6,194. Kenny,D.A. & Zautra,A.(1995).The trait-state-error model for multiwave data. Journal ofConsulting and Clinical Psychology, 63,52-59. Kenzik,K.M.,Martin,M.Y.,Fouad,M.N.,& Pisu,M.(2015).Health-related quality of life in lung cancer survivors: Latent class and latent transition analysis. Cancer; 121(9),1520-1528. Liu,Y.,Liu, H.,& Hau,K.T. (20l6). Reading ability development from Kindergarten to junior secondary: Latent transition analyses with growth mixture modeling. Frontiers in psychology, 7,1659. Magidson, J., & Vermunt, J. (2oo2). Latent class models for clustering: A comparison with K-means. Canadian Journal of Marketing Research,20(1),36-43. Muthén,B.&Asparouhov,T.(2019). What multilevel modeling can teach us about single-level modeling: Latent transition analysis with random intercepts (RI-LTA).Version 1. Retrieved October 9,2020,from http://www.statmodel.com/RI-LTA.shtml Muthen, B.& Asparouhov,T. (2O2O). Latent transition analysis with random intercepts (RI-LTA). Version 4. Accepted for publication in Psychological Methods.Retrieved October 9,2020, from http://www.statmodel.com/RI-LTA.shtml Nylund,K.(20o7).Latent transition analysis: Modeling extensions and an application to peer victimization (Unpublished doctoral dissertation). University of California,Los Angeles. Pan, Y.,Liu, H.,Lau,P.,& Luo,F.(20l7).A latent transition analysisof bulling and victimization in Chinese primary school students. PLoS one,12(8), e0182802. Ryoo,J. H.,Wang, C.,& Swearer,S.M. (2015).Examination of the change in latent statuses in bullying behaviors across time. School psychology quarterly, 30(1),105. Ryoo,J. H., Wang, C., Swearer, S.M., Hul,M., & Shi,D. (2018). Longitudinal model building using latent transition analysis: An example using school bullying data. Frontiers in psychology, 9, 675. Satorra,A. & Bentler, P.M. (2010).Ensuring positivenessofthe scaled difference chi-square test statistic. Psychometrika,75: 243.doi:10.1007/s11336-009-9135-y Wang, J.,& Wang, X. (2019). Structural equation modeling: Applications using Mplus. John Wiley & Sons.

# Random intercept latent transition analysis(RI-LTA)-—separating the between-subject variation from the within-subject variation

WEN Congcong, ZHU Hong

(International College,Xiamen University,Xiamen 361102,China) (Graduate School ofEducation,Peking University,Beijing1oo871,China)

Abstract: Traditional latent transition analysis (LTA） is usually done using single-level modeling, but can also be viewed as a two-level modeling from a multi-level perspective. In 2020, Muthen and Asparouhov proposed a so-called random intercept latent transition analysis (RI-LTA) model which separates between-subject variation from within-subject variation. If the factor loadings on the random intercept factor are large, this indicates that the item probabilities are large and thus the cases have large differences on these items. From this perspective,RI-LTA can be viewed as absorbing the measurement non-invariance of the model.

Performing RI-LTA in Mplus software can be done in three to four steps. First, implementing LCA across diferent time points; second, implementing traditional LTA and RI-LTA; third, saving the parameter estimates obtained in the second step and using them as population values to do a Monte Carlo simulation study; fourth, in the event of previous knowledge or existing applications, one may include covariates or distal outcomes in the model.

In the current study, a two-wave longitudinal data collection from undergraduates attending in the year 2016 at a research-oriented university was used to demonstrate how to implement RI-LTA in Mplus. We performed the RI-LTA analysis, a multiple-group analysis and investigated the interaction effects by including a “type of university enrolment” covariate. Results showed that RILTA avoided overestimation on the transition probabilities of students staying in the original class and allowed for clearer interpretation of the data.Future research could use Monte Carlo simulation studies to investigate the applicability of RI-LTA, for example by manipulating sample sizes, numbers of indicators,latent classes，and time points. Inspired by multi-level modeling， the implementation of multi-level RI-LTA in statistical software should also be explored further.

Key words:latent transition analysis, random intercept latent transition analysis, single-level analysis,multi-level analysis,Monte Carlo simulation study