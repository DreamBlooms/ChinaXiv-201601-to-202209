# 技术方法

# 贝叶斯期中分析与经典期中分析在成组序贯设计中的比较

原玲玲1，詹志颖²，谭旭辉²  
南方医科大学人文与管理学院，生物统计学系，广东广州510515

摘要：目的比较贝叶斯期中分析与经典方法的期中分析的差异。方法 以对照组(Control)和试验组(Treatment)的两样本均数比较为分析目的，即 $\lvert \boldsymbol { \theta } = \boldsymbol { \mu _ { T } } - \boldsymbol { \mu _ { C } } ^ { \prime } \rvert$ （0越大疗效越好)，建立 ${ \bf \nabla } \cdot { \cal H } _ { 0 } : \theta \leqslant 0 ; { \cal H } _ { 1 } : \theta > 0$ 的优效性假设检验(拒绝 $H _ { 0 }$ ,即支持处理组疗效)。按照成组序贯设计的数据要求，在每次期中分析时刻，计算各种先验分布的贝叶斯期中分析I类错误、功效、平均样本量、平均阶段数等指标。结果在Pocock和O'Brien&Fleming设计中,Skeptical先验和Handicap先验的I类错误ε均能控制在0.05左右。当O'Brien&Fleming和Pocock方法功效在 $80 \%$ 时,基于Handicap先验和Skeptical先验的贝叶斯功效相对来说明显较低,而基于Non-informative先验和Enthusiastic先验的贝叶斯功效则明显较高。结论 Skeptical先验和Handicap先验的贝叶斯期中分析能较好的控制I类错误ε,基于Skeptical先验和Handicap先验的贝叶斯期中分析相对于O'Brien&Fleming方法均能够明显增加试验提前终止的可能性,而对于Pocock方法则没有太大实际意义。

关键词：成组序贯设计;贝叶斯;期中分析；先验分布

# Comparison of Bayesian interim analysis and classical interim analysis in group sequential design

YUAN Lingling', ZHAN Zhiying², TAN Xuhui² 1ScholofHumantiesndaagementepartmentofostatistcsoutherndicalUnersityGuangzouin

Abstract: Objective To explore the diferences between the Bayesian interim analysisandtheclasical interimanalysis. Methods To compare the means of two independent samplesbetween control and treatment,superior hypothesis test was established.Ilinewiththedatarequirementsfor groupsequentialdesign,TypeIerorof Bayesian interimanalysisbasedon various priordistributions,Power,Average SampleSizeand Average Stage were estimated inthe interim analysis.Results In the Pocock and $\mathrm { \Omega } ^ { \mathrm { \prime } }$ Brien & Fleming designs, the Type I errors in the Bayesian interim analysis based on the skeptical prior distributionandthe handicap priordistribution werecontroledataroundO.05.When thepowersof thesetwoclassical designs were both $8 0 \%$ , Bayesian powers of the skeptical prior distribution and the handicap prior distribution were markedly lower.Thepowersofthenon-informativepriordistributionandtheenthusiastic priordistribution weredistinctlyhigher than $8 0 \%$ . Conclusion Inthe Bayesian interim analysis basedontheskeptical prior distribution and the handicap Prior distribution, the Type Ierors can be wellcontrolled. Bayesian interim analyses using these two priordistributions,compared withthe analysis adopting the $\mathrm { \Phi } ^ { \mathrm { { \sc ~ O } ^ { \prime } } }$ Brien & Fleming method,can markedly increase the possibility of ending the clinical trials ahead of time.The Bayesian interim analysesbased on these two distributions do not have practical value for group sequential design of the Pocock method.

Key words: group sequential design; Bayes; interim analysis; prior distribution

在临床试验领域，以往试验的先验信息没有被充分利用是一个普遍现象,而贝叶斯统计[-2是一种能充分利用先验信息的统计方法。在药物临床试验中，期中分析通常能够有效的降低试验所需的样本量并提前完成试验,从而为药物的上市节省大量的时间和资源。而结合了先验信息的贝叶斯期中分析在临床试验中相对于传统期中分析是否可行可靠、能否进一步提高效率等相关疑问亟待明确。

因此，为了了解贝叶斯期中分析与成组序贯设计[3-4的经典期中分析[5的差异,揭示两种方法在具体应用上的优劣势，定量评估贝叶斯结果的可靠性，本文将对贝叶斯期中分析与经典期中分析进行比较，重点对几种常见的先验分布的影响进行评估，为贝叶斯期中分析在临床试验领域的应用提供理论参考，也为今后药物临床试验的期中分析提供新的思路。

# 1方法与原理

# 1.1 成组序贯设计

成组序贯设计是一种在试验正式结束前，能提供多次期中分析的设计。成组序贯方法是由Pocock于1977年提出，在此基础上Kittelson和Emerson于1999年提出了Unified family方法[,其包括 Pocock、O'Brien-Fleming、Power family等方法。其中Powerfamily方法是由Wang和Tsiatis于1987提出[7],其通过参数Power值的改变来得到不同的临界值。从设计方案角度来说，成组序贯设计是将整个试验划分成 $K$ 个连续的时间段，每个时间段内每个处理组都有 $n$ 个受试者加入。当第k个阶段 $( k { = } 1 , 2 , \cdots , K )$ 结束后，把之前各个阶段试验结果累积起来进行一次统计分析。对于拒绝性的成组序贯设计，如果拒绝 $\mathrm { H } _ { \mathrm { 0 } }$ 则试验结束，否则继续下一阶段试验。当其处于最后一个试验阶段时，其结果不是接受$H _ { 0 }$ ,就是拒绝 $H _ { 0 \textmd { > } }$

# 1.2 贝叶斯统计

假设参数 $\wp$ ,其概率分布为 $\pi ( \theta )$ ，观察值 $y _ { 1 } , . . . , y _ { n }$ 来自概率密度函数为 $P \left( y | \theta \right)$ ，则：

$$
p \big ( \theta | y \big ) = p \big ( \theta , y \big ) \big / \thinspace p \big ( y \big ) = p \big ( y | \theta \big ) \pi ( \theta ) \Big / \int p \big ( y | \theta \big ) \pi ( \theta ) \mathrm { d } \theta
$$

设 $L ( \theta ) \propto p { \big ( } y | \theta { \big ) }$ ，则 $p \big ( \theta | y \big ) \propto L \big ( \theta \big ) \pi \big ( \theta \big )$

由以上过程也可发现，贝叶斯统计推断均是基于后验概率分布 $p \big ( \boldsymbol { \theta } | \boldsymbol { y } \big ) _ { \circ }$ 而贝叶斯统计与经典统计的主要区别就在于先验信息的使用。在贝叶斯统计中，先验一般都具有主观性，然而为了减少主观性对后验概率的影响,也提出了一些较"客观"的先验分布[8],例如广义先验分布、无信息先验分布、共轭先验分布以及有信息先验分布等。在一些较复杂的具体分析中，贝叶斯统计需要应用MCMC方法模拟产生基于后验分布的样本，并以此来估计特征统计量。

# 1.3 贝叶斯期中分析

贝叶斯期中分析是基于试验过程中所得到的后验概率分布，并在此基础上作出统计推断。在该过程中不需要事先指定终止标准以及所需样本量，仅仅应用后验$P$ 值来进行期中监测9。而经典的期中分析是建立在“Neyman-Pearson"理论上，其重点是在于控制I和Ⅱl类错误。

ICH-GCP将期中分析定义为：在一个临床试验正式完成之前的任何时间内，为了比较组间的有效性或安全性而进行的分析。依据后验概率 $P$ 的期中分析，如果小于设定的临界值 $\boldsymbol { \varepsilon }$ ，即 $p \big ( H _ { 0 } | d a t a \big ) \leqslant \varepsilon ^ { \prime }$ （为了与经典统计I类错误 $\alpha$ 区分，记为e)，则拒绝 $H _ { 0 \text{ { o } } }$ 因此,先验分布的选择对于贝叶斯期中分析是至关重要的。为了让试验支持者或试验怀疑者能够达成较一致的结论，先验分布的选择有如下两个原则[]：(1)如果是阳性结局(positive result)的试验,其 $P$ 值的计算应基于Skeptical先验;(2)如果是阴性结局(negative result)的试验，其 $P$ 值的计算应基于Enthusiastic先验。

在以上两原则的条件下，仍以较大的概率支持相应的结局，则可下支持相应结局的结论。

# 1.4期中分析之间的比较设计

在临床试验中,Pocock和O'Brien&Fleming[]期中分析方法是成组序贯设计中比较常见的两种方法。在对比研究中，我们以经典成组序贯为设计框架，按照频率学派的观点，在功效，I类错误以及实际所需样本量等方面,将贝叶斯期中分析与常见的两种经典期中分析方法进行比较。由于成组序贯设计在实施前需确定一些参数，如 $\mathsf { I a }$ 、 $\beta$ 、 $\delta$ 、以及期中分析次数等,我们事先定义期中分析次数为 $k$ ，总分析次数为 $K ($ 即 $K { = } k { + } 1$ 。以对照组和试验组的两样本均数比较为分析目的，即$\scriptstyle \theta = \mu _ { T } - \mu _ { C } ($ （0越大疗效越好），建立 ${ \cal H } _ { 0 } ; \theta { \leqslant } 0 ; { \cal H } _ { 1 } ; \theta > 0$ 的优效性假设检验。对于两组的试验模拟数据,可由样本量公式计算出第 $k$ 阶段每组所需样本量(假设两组样本量相等)。我们以 $\displaystyle { . N \big ( \mu _ { T } , \sigma _ { T } ^ { 2 } \big ) }$ 、 $N \big ( \mu _ { C } , \sigma _ { C } ^ { 2 } \big )$ 表示试验和对照组总体，从中随机模拟生成各个阶段所需的样本试验数据。为了简化设计,我们假设 $\cdot \sigma _ { T } = \sigma _ { C } , \mu _ { T } > \mu _ { C }$ ,即两处理组有共方差。在模拟比较中，较"客观"的先验分布选择Enthusiastic 先验、Skeptical先验、Handicap 先验和Non-informative先验（无信息先验）。Pocock和O'Brien&Fleming两种方法的参数设定如表1。

基于经典期中分析结果，提出了评价贝叶斯期中分析效果的两个指标，即贝叶斯阳性符合率和贝叶斯阴性符合率[12]。贝叶斯阳性符合率计算公式如公式(1)：

$$
C _ { p } = \frac { N _ { p } ^ { C B } } { N _ { p } ^ { C } }
$$

假设在有差异的两总体中,进行了 $N _ { \rho }$ 次成组序贯模拟; ${ N } _ { p } ^ { C }$ ：在 $N _ { p }$ 试验中,经典期中分析 ${ N } _ { p } ^ { C }$ 次拒绝 $H _ { 0 }$ ！${ N } _ { p } ^ { B }$ ：在 $N _ { p }$ 试验中,贝叶斯期中分析 ${ N } _ { p } ^ { B }$ 次拒绝 $H _ { 0 } \mathrm { ~ } ; N _ { p } ^ { C B }$ ：在经典期中分析 ${ N } _ { p } ^ { C }$ 次拒绝 $H _ { 0 }$ 的试验中,贝叶斯期中分析也拒绝 $H _ { 0 }$ 的次数。

从公式(1)，我们可推出，经典期中分析的功效$P o w e r _ { C } = N _ { p } ^ { C } \big / N _ { \phantom { } _ { l } }$ ；贝叶斯期中分析的功效$P o w e r _ { B } = N _ { p } ^ { B } \big / N _ { p }$

贝叶斯阴性符合率计算公式如公式(2)：

$$
C _ { n } = \frac { N _ { n } ^ { C B } } { N _ { n } ^ { C } }
$$

假设在无差异的两总体中，进行了 $N _ { n }$ 次成组序贯模拟; ${ N } _ { n } ^ { C }$ ：在 ${ \cal N } _ { n }$ 试验中,经典期中分析 $\boldsymbol { N } _ { n } ^ { C }$ 次不拒绝$H _ { 0 } \ ; \ N _ { n } ^ { B }$ ：在 ${ \cal N } _ { n }$ 试验中，贝叶斯期中分析 $\boldsymbol { N } _ { n } ^ { B }$ 次不拒绝$H _ { 0 } \mathrm { ~ } ; N _ { n } ^ { C B }$ ：在经典期中分析 ${ N } _ { n } ^ { C }$ 次不拒绝 $H _ { 0 }$ 的试验中,贝叶斯期中分析也不拒绝 $H _ { 0 }$ 的次数。

从公式(2)，我们可推出，经典期中分析的I类错误$\alpha = 1 - N _ { n } ^ { C } / N _ { n }$ ;按照频率学派观点，贝叶斯期中分析的I类错误 $\varepsilon = 1 - N _ { n } ^ { B } \big / N _ { \rho }$ 。与此同时,我们也可计算另外两个指标,即贝叶斯期中分析的平均样本量(AverageSample Size)记为 $A S S _ { p }$ 和平均终止阶段数(AverageStage),记为 ${ \bf \nabla } \cdot { \bf A } S _ { p ^ { \circ } }$

表1参数设定Tab.1Parameter setting  

<html><body><table><tr><td>Parameter</td><td colspan="2">Value(β=0.2)</td></tr><tr><td>a</td><td>0.05</td><td>0.05</td></tr><tr><td>OT=Oc=σ</td><td>10</td><td>18</td></tr><tr><td>0=μr -μc(δ)</td><td>2</td><td>3</td></tr></table></body></html>

# 2结果

# 2.1两总体均数相同

在两总体均数相同条件下，我们将成组序贯设计按以下参数进行设定(表2)。

在O_Set5_1和O_Set5_2（即O'Brien&Fleming方法)参数设置下，不同先验分布和贝叶斯期中分析阴性符合率以及I类错误如表3。在P_Set5_1和P_Set5_2(即Pocock方法)参数设置下，不同先验分布和贝叶斯期中分析阴性符合率以及I类错误如表4。

由以上结果，我们可以看出在Enthusiastic先验和Non-informative先验的条件下，贝叶斯期中分析的I类错误均明显大于0.05;其中在Non-informative先验条件下,5阶段在0.10以上。在Handicap先验和Skeptical先验条件下，I类错误均能控制在0.05左右。当总阶段数调整为3或者2时，贝叶斯期中分析阴性符合率和

表2O'Brien&Fleming和Pocock方法参数设定(两总体均数相等) Tab.2 Parameter seting in the O'Brien & Fleming method and the Pocock method (two equal population means)   

<html><body><table><tr><td rowspan="2"></td><td colspan="8">Condition</td></tr><tr><td>Iteration</td><td>β</td><td>0</td><td>Stage(K)</td><td>Stopping</td><td>μT</td><td>μc</td><td></td></tr><tr><td>O_Set5_1</td><td>300</td><td>0.20</td><td>10</td><td>5</td><td>Reject</td><td>6</td><td>6</td><td>2</td></tr><tr><td>O_Set5_2</td><td>300</td><td>0.20</td><td>18</td><td>5</td><td>Reject</td><td>6</td><td>6</td><td>3</td></tr><tr><td>P_Set5_1</td><td>300</td><td>0.20</td><td>10</td><td>5</td><td>Reject</td><td>6</td><td>6</td><td>2</td></tr><tr><td>P_Set5_2</td><td>300</td><td>0.20</td><td>18</td><td>5</td><td>Reject</td><td>6</td><td>6</td><td>3</td></tr></table></body></html>

表3O'Brien&Fleming方法下的贝叶斯阴性符合率、I类错误 Tab.3 Bayesian negative coincidence rate and Type Ierror in the O'Brien &Fleming method   

<html><body><table><tr><td rowspan="2">Method</td><td colspan="2">O_Set5_1</td><td colspan="2">O_Set5_2</td></tr><tr><td>Cn(%)</td><td>a/ε(%)</td><td>Cn(%)</td><td>α/ε(%)</td></tr><tr><td>Non-informative Prior</td><td>92.01</td><td>11.67</td><td>87.76</td><td>16.33</td></tr><tr><td>Skeptical Prior</td><td>99.65</td><td>3.33</td><td>99.30</td><td>4.00</td></tr><tr><td>Enthusiastic Prior</td><td>55.21</td><td>47.00</td><td>57.69</td><td>45.00</td></tr><tr><td>Handicap Prior</td><td>99.65</td><td>3.00</td><td>99.30</td><td>3.33</td></tr><tr><td>O'Brien & Fleming</td><td>-</td><td>4.00</td><td>-</td><td>4.67</td></tr></table></body></html>

表4Pocock方法下的贝叶斯阴性符合率、I类错误Tab.4 Bayesian negative coincidence rate and Type I error inthe Pocock method  

<html><body><table><tr><td rowspan="2">Method</td><td colspan="2">P_Set5_1</td><td colspan="2">P_Set5_2</td></tr><tr><td>Cn(%)</td><td>α/ε(%)</td><td>C，(%)</td><td>α/ε(%)</td></tr><tr><td>Non-informative Prior</td><td>93.15</td><td>9.33</td><td>89.31</td><td>13.67</td></tr><tr><td>Skeptical Prior</td><td>99.32</td><td>2.67</td><td>98.62</td><td>3.00</td></tr><tr><td>Enthusiastic Prior</td><td>61.99</td><td>39.67</td><td>57.93</td><td>44.00</td></tr><tr><td>Handicap Prior</td><td>99.32</td><td>2.67</td><td>98.97</td><td>2.67</td></tr><tr><td>Pocock</td><td>-</td><td>2.67</td><td>-</td><td>3.33</td></tr></table></body></html>

I类错误与5阶段条件下的结果相似。

# 2.2两总体均数不同

在两总体均数不同条件下，我们将成组序贯设计按以下参数进行设定(表5)。

在O_Set5_D1、O_Set5_D2、P_Set5_D1和P_Set5D2参数设置下，几种常见先验分布的贝叶斯期中分析平均阶段数、平均样本量、功效和阳性符合率(表6,7)。

通过以上5阶段的结果可以看出，当OBrien&Fleming功效在 $80 \%$ 左右时，基于Handicap先验和Skeptical先验的贝叶斯功效相对较低，而基于Enthusiastic先验和Non-informative先验的贝叶斯功效明显较高。此外，几种先验分布的贝叶斯期中分析所需的平均阶段数和平均样本量均比OBrien&Fleming方法要低,而基于Handicap先验和Skeptical先验的贝叶斯期中分析均能提前终止试验。当Pocock功效在 $80 \%$ 时,Skeptical和Handicap 两种先验分布的贝叶斯功效仍旧明显较低，而Enthusiastic先验和Non-informative先验的贝叶斯功效均比Pocock功效要高。与此同时，基于Handicap先验和Skeptical先验的贝叶斯期中分析相对于Pocock方法而言并不能明显的提前终止试验。

# 3讨论

# 3.1两总体均数相同情况

从实际模拟效果来看，在OBrien&Fleming 和Pocock期中分析方法下，使用Enthusiastic先验和Non-informative先验进行贝叶斯期中分析会增加I类错误的风险，而Handicap先验和Skeptical先验均可较好的控制I类错误，因此这两种先验是比较合适的先验选择。Skeptical先验、Handicap先验和Non-informative先验均比Enthusiastic先验显著的增加贝叶斯阴性符合率,这意味着在原假设成立的条件下，基于Enthusiastic先验的贝叶斯期中分析结果很可能会和其他3种先验所得的结论不一致。这种现象提示我们，在保证试验因素能够继续进行研究的前提下，如果贝叶斯期中分析在Non-informative先验和Enthusiastic先验之间出现不一致的结论,则该研究可能是一个阴性研究[12]。我们还发现基于Handicap先验和Skeptical先验的贝叶斯阴性符合率均接近 $100 \%$ ，从先验分布选择的角度来说，Skeptical先验是在阳性研究(Positive study)中建议使用的分布，这意味着其更倾向于“保守”，而Handicap先验的贝叶斯阴性符合率和I类错误均与Skeptical先验相近，因此可认为这两种先验的“保守"程度是比较接近的。此外，在大样本的条件下，不同先验分布的后验概率分布之间通常只有很微小的差异，因此大样本条件下基于各种先验的贝叶斯期中分析就等同于敏感度分析，其目的是评估试验数据支持结论的强度[12-13]。

表5O'Brien&Fleming和Pocock方法参数设定(两总体均数不等) Tab.5Parameter setting in the $\mathrm { \Phi } ^ { \mathrm { \prime } }$ Brien & Fleming method and the Pocock method (two unequal population means)   

<html><body><table><tr><td rowspan="2"></td><td colspan="7">Condition</td></tr><tr><td>Iteration</td><td>β</td><td>0</td><td>Stage(K)</td><td>Stopping</td><td>μT</td><td>μc 8</td></tr><tr><td>O_Set5_D1</td><td>300</td><td>0.20</td><td>10</td><td>5</td><td>Reject</td><td>8</td><td>6</td><td>2</td></tr><tr><td>O_Set5_D2</td><td>300</td><td>0.20</td><td>18</td><td>5</td><td>Reject</td><td>9</td><td>6</td><td>3</td></tr><tr><td>P_Set5_D1</td><td>300</td><td>0.20</td><td>10</td><td>5</td><td>Reject</td><td>8</td><td>6</td><td>2</td></tr><tr><td>P_Set5_D2</td><td>300</td><td>0.20</td><td>18</td><td>5</td><td>Reject</td><td>9</td><td>6</td><td>3</td></tr></table></body></html>

<html><body><table><tr><td rowspan="2">Method</td><td colspan="4">O_Set5_D1</td><td colspan="4">O_Set5_D2</td></tr><tr><td>ASSp</td><td>ASp</td><td>Cp(%)</td><td>Power (%)</td><td>ASSp</td><td>ASp</td><td>Cp(%)</td><td>Power (%)</td></tr><tr><td>Non-informative Prior</td><td>352.53</td><td>2.73</td><td>100.00</td><td>85.00</td><td>489.09</td><td>2.64</td><td>100.00</td><td>86.33</td></tr><tr><td>Skeptical Prior</td><td>469.91</td><td>3.65</td><td>89.18</td><td>69.67</td><td>663.69</td><td>3.58</td><td>92.05</td><td>73.67</td></tr><tr><td>Enthusiastic Prior</td><td>187.30</td><td>1.45</td><td>100.00</td><td>97.67</td><td>295.93</td><td>1.59</td><td>100.00</td><td>96.00</td></tr><tr><td>Handicap Prior</td><td>474.19</td><td>3.68</td><td>87.88</td><td>68.00</td><td>666.16</td><td>3.59</td><td>89.54</td><td>71.67</td></tr><tr><td>O'Brien &Fleming</td><td>498.21</td><td>3.87</td><td></td><td>77.00</td><td>703.74</td><td>3.79</td><td></td><td>79.67</td></tr></table></body></html>

表6O'Brien&Fleming方法下的贝叶斯平均样本量、平均阶段数、阳性符合率和功效 lab.6 Average sample size, average stage, Bayesian positive coincidence rate and power in the $\mathrm { ^ \circ } { }$ Brien& Fleming method   
表7Pocock方法下的贝叶斯平均样本量、平均阶段数、阳性符合率和功效Tab.7 Averagesample size,average stage,Bayesian positive coincidence rateand power in the Pocock method  

<html><body><table><tr><td rowspan="2">Method</td><td colspan="4">P_Set5_D1</td><td colspan="4">P_Set5_D2</td></tr><tr><td>ASSp</td><td>ASp</td><td>Cp(%)</td><td>Power (%)</td><td>ASSp</td><td>ASp</td><td>Cp(%)</td><td>Power (%)</td></tr><tr><td>Non-informative Prior</td><td>388.85</td><td>2.50</td><td>100.00</td><td>91.33</td><td>547.25</td><td>2.45</td><td>100.00</td><td>92.00</td></tr><tr><td>Skeptical Prior</td><td>472.02</td><td>3.04</td><td>78.15</td><td>66.33</td><td>672.29</td><td>3.01</td><td>77.96</td><td>66.67</td></tr><tr><td>Enthusiastic Prior</td><td>227.95</td><td>1.46</td><td>100.00</td><td>97.67</td><td>297.02</td><td>1.33</td><td>100.00</td><td>99.33</td></tr><tr><td>Handicap Prior</td><td>473.05</td><td>3.04</td><td>77.31</td><td>65.33</td><td>675.28</td><td>3.02</td><td>75.92</td><td>64.33</td></tr><tr><td>Pocock</td><td>478.21</td><td>3.08</td><td></td><td>79.33</td><td>681.25</td><td>3.05</td><td></td><td>81.67</td></tr></table></body></html>

# 3.2两总体均数不同情况

从5阶段成组序贯设计所得的各种先验分布的功效结果来看，当O'Brien&Fleming和Pocock功效在$80 \%$ 时,基于Handicap先验和Skeptical先验的贝叶斯期中分析的功效相比较而言明显偏低；当OBrien&Fleming功效逐渐增大时，以上两种先验分布的贝叶斯功效开始接近O'Brien&Fleming方法的功效。这是因为在参数相同条件下，如果先验方差较小，则基于该先验分布的贝叶斯期中分析更易得到较大的 $P$ 值，这也意味着基于该先验的贝叶斯期中分析更加的保守，其功效也会相应的较低;如果两种先验方差的比值逐渐增大，两者功效之间的差异则会逐渐增大。然而随着O'Brien&Fleming功效的逐渐提高，基于以上两种先验的贝叶斯功效也会逐渐接近OBrien&Fleming的功效。这点也充分说明，在大样本条件下，不同先验分布下的后验概率分布之间通常只有微小的差异。此外，在O'Brien&Fleming和Pocock的功效较低的条件下，基于Handicap先验和Skeptical先验的贝叶斯阳性符合率均较低，这就意味着一方面基于这两种先验的贝叶斯期中分析的功效相对于Pocock和O'Brien&Fleming功效而言均较低;另一方面从频率学派角度来说，基于这两种先验的分析结果的可靠性也较低。值得一提的是，当OBrien&Fleming功效在 $80 \%$ 的时候，基于Skeptical先验和Non-informative先验的贝叶斯阳性符合率之间有较大差异。这种差异对于阳性研究来说不但意味着需要进行证实性的试验研究，而且也可能提示着试验因素可能没有被完全理解[12]

对于OBrien&Fleming方法来说,早期是很难拒绝零假设的，这也使得贝叶斯期中分析能提前终止试验的特点显得非常突出。然而在Ⅲ期临床试验中，为了对药物作有效性评价，成组序贯设计又通常会选择应用O'Brien&Fleming方法[1415],因此在验证有效性的临床试验中，当OBrien&Fleming方法的功效越高，基于Handicap先验和Skeptical先验的贝叶斯期中分析的功效就会越接近O'Brien&Fleming方法的功效，在功效较高且相近的条件下,基于Handicap 先验和Skeptical先验的贝叶斯期中分析均能增加试验提前结束的可能性。另外,基于Handicap先验和Skeptical先验的贝叶斯期中分析方法相对于Pocock方法而言并不能明显提前终止试验。这是因为5阶段Pocock法允许试验早期以较小的临界值(相当于早期设置了较大的名义检验水平，即名义 $\begin{array} { r } { . a _ { 1 } = 0 . 0 1 6 9 , } \end{array}$ 来拒绝零假设，这也就意味着一些试验可能在早期(甚至在第1阶段)因为拒绝零假设而终正，正因为Pocock具有较早的拒绝 $H _ { 0 }$ 的特点，所以在提前终止试验方面贝叶斯期中分析相对于Pocock法而言并没有什么优势。

综上所述，当采用功效达到 $80 \%$ 以上且早期不易拒绝零假设的传统成组序贯设计时，基于Skeptical先验和

Handicap先验的贝叶斯期中分析既能使结果具有较强的可靠性，又能显著增加试验提前终止的可能性

# 参考文献：

[1]Lin R,Yin G. Bayes factor and posterior probability:complementary statistical evidence to p-value[J].Contemp Clin Trials,2015,44(1): 33-5.   
[2]Freedman L. Bayesian statistical methods[J]. BMJ,1996,313(757): 569-70.   
[3]Gao Z,Roy A,Tan M. Multistage adaptive biomarker-directed targeted design for randomized clinical trials [J].Contemp Clin Trials,2015,42(1): 119-31.   
[4]Lai TL,Liao OY, Kim DW. Group sequential designs for developing and testing biomarker-guided personalized therapies in comparative effectiveness research[J].Contemp Clin Trials,2013,36(2):651-63.   
[5] Stephens RJ,Langley RE,Mulvenna P,et al. Interim results in clinical trials:do we need to keep all interim randomised clinical trial results confidential[J].Lung Cancer, 2014,85(2): 116-8.   
[6]Kittelson JM, Emerson SS.A unifying family of group sequential test designs[J].Biometrics,1999,55(3): 874-82.   
[7]Wang SK, Tsiatis AA. Approximately optimal one-parameter boundaries for group sequential trials[J]. Biometrics,1987,43(1): 193-9.   
[8]Berger J. The case for objective bayesian analysis[J].Bayesian Anal,2006,1(3): 385-402.   
[9]Daimon T. Predictive checking for Bayesian interim analyses in clinical trials[J].Contemp Clin Trials,2008,29(5):740-50.   
[10] Spiegelhalter DJ,Abrams KR,Myles JP.Bayesian approaches to clinical trial and health-care evaluation [M].Chichester:John Wiley&Sons,2004.   
[11] Bartroff J,Lai TL, Shih MC.Sequential experimentation in clinical trials[M]. New York: Springer, 2013.   
[12]Wijeysundera DN,Austin PC,Hux JE,et al. Bayesian statistical inference enhances the interpretation of contemporary randomized controlled trials[J].JClin Epidemiol,2009,62(1): 13-21.e5.   
[13]Homs MY, Steyerberg EW,Eijkenboom WM,et al. Single-dose brachytherapy versus metal stent placement for the palliation of dysphagia from oesophageal Cancer: multicentre randomised trial [J].Lancet,2004,364(9444): 1497-504.   
[14] Skovlund E. Repeated significance tests on accumulating survival data[J].JClin Epidemiol,1999,52(11): 1083-8.   
[15] Choi SC.Interim analyses and early termination of clinical trials[J]. JBiopharm Stat,1997,7(4): 533-43.

(编辑：孙昌朋)