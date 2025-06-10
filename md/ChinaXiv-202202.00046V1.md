# 项目反应理论观察分数核等值的影响因素

王少杰 张敏强\* 黄菲菲 黄丽芳 袁琪婷（华南师范大学心理学院，广州，510631)

摘要 探究带宽选择方法、样本量、题目数量、等值设计、数据模拟方式对项目反应理论观察分数核等值的影响。通过两种数据模拟方式，获得研究数据，并计算局部与全域评价指标。研究发现，在随机组设计中，带宽选择方法表现相似；考生样本量和题目数量影响甚微。在非等组设计中，惩罚法与 Silverman 经验准则表现优异；增加题目量可降低百分相对误差和随机误差；增加样本量导致百分相对误差变大，随机误差减小。数据模拟方式可影响等值评价。未来应重点关注等值系统评估。

关键词IRT观察分数核等值；带宽选择方法；等值设计；数据模拟方式

# 1问题提出

核等值（KermelEquating，KE）是一种测验等值方法体系，它基于近似传统等百分位等值（Equipercentile Equating，EE），并将线性等值作为特例（von Davier et al.,2004）。研究流程共包含五步：（1）预平滑，即采用对数线性模型拟合观察分数。（2）估计分数概率，即通过设计函数，将拟合的样本分数概率转化为总体分数概率。（3）连续化，即将离散累积分布连续化。（4）等值，即采用EE 计算结果。（5）计算等值标准误等指标，即评估等值结果（罗莲,2008)。KE采用预平滑和连续化，可降低因样本量较少造成的随机误差（Jiang et al.,2012;von Davier&Chen,2013)。从等值设计到等值评价，均在一系列特有且相互联系的框架中完成；同时可对各环节单独分析，调整参数，得到与其他方法相似的结果，极具包容与扩展性（王少杰等，2020）。综上，KE 相较于经典测量理论（Classical Test Theory，CTT）等值更为精确、稳定，具有较大发展和应用前景。

但由于其采用EE计算结果，不能从更微观角度，将考生与题目参数同时建模，而这恰为项目反应理论（Item Response Theory，IRT）等值擅长之处。在分数层面，IRT 等值方法包含观察分数等值（IRT Observed Score Equating，IRTOSE）与真分数等值（IRT True ScoreEquating，IRTTSE)。在将参数置于同一量尺后，前者通过IRT 模型计算待等两测验正确作答分数分布，最后采用EE 获得分数对应关系；而后者认为两测验中相同能力对应的真分数即为等值分数（Kolen&Brennan,2014)。KE与IRT等值方法各有优劣，在特定条件下，前者优于后者（De Ayala et al.,2018;Leóncio&Wiberg,2017; Wang et al.,2020）。那么，是否可将 KE与IRT等值方法结合，使新方法既有前者的连续化思想，又包含后者的优异特性呢?

# 2IRT观察分数核等值及其相关概念

# 2.1IRT观察分数核等值

Andersson 等（2013）最早将KE与IRTOSE 结合，在专门开展KE 分析的kequate 软件包中提出 IRT 观察分数核等值（IRTobserved score Kernel Equating，IRTKE）的概念。因非等组锚测验设计（Non-Equivalent groups with Anchor Test design，NEAT）较为常用，且本研究亦基于此，故仅介绍 NEAT下的 IRTKE。其他设计可参考 Andersson 和Wiberg（2017）和Sansivieri 等（2017）。

假设有测验X、Y与锚测验A，用 $r _ { j } , s _ { k } , t _ { P , l } , t _ { Q , l }$ 分别代表来自群体 $P$ 和 $\varrho$ 的考生分别取得分数 $x _ { j } , ~ y _ { k }$ 和 $a _ { l }$ 的概率。首先，采用 IRT 模型（本研究为二参数逻辑斯蒂克模型，2-Parameter Logistic Model，2PLM）拟合数据，得到考生和题目参数。第二步，依据 $r _ { j } \approx$ $\begin{array} { r } { \sum _ { r = 1 } ^ { R } r _ { j } ( t _ { r } ) W ( t _ { r } ) } \end{array}$ 计算得分概率， $t _ { r }$ 为第 $\boldsymbol { r }$ 个积分节点的能力水平， $r _ { j } ( t _ { r } )$ 为根据 Lord 和Wingersky（1984）迭代算法求出的分数概率， $W ( t _ { r } )$ 为积分节点 $t _ { r }$ 的权重。 $s _ { k } , \ t _ { P , l }$ 与 $t _ { Q , l }$ 算法类似。第三步，连续化。将离散变量 $X$ 连续化后，可得到 $\vert \pmb { X } ( h _ { X } )$ 的累积分布函数 $F _ { h _ { X } } ( x ) =$ $\begin{array} { r l } { \sum _ { j } r _ { j } \Phi \left( R _ { j X } ( { \boldsymbol { x } } ) \right) } & { { } } \end{array}$ ，其中 $\phi ( z )$ 为标准正态分布的累积分布函数， $\begin{array} { r } { R _ { j X } ( x ) = \frac { x - a _ { X } x _ { j } - ( 1 - a _ { X } ) \mu _ { X } } { a _ { X } h _ { X } } } \end{array}$ ， $h _ { X }$ （20为带宽。 $\boldsymbol { { \mathbf { \mathit { Y } } } }$ 与 $\textbf {  { A } }$ 的连续化与之类似。第四步，等值。依据EE， ${ \hat { e } } _ { Y ( C E ) } ( x ) =$ $\hat { G } _ { Q h _ { Y Q } } ^ { - 1 } ( \widehat { H } _ { Q h _ { A Q } } ( \widehat { H } _ { P h _ { A P } } ^ { - 1 } ( \hat { F } _ { P h _ { X P } } ( x ) ) ) )$ ，其中， $\begin{array} { r l } { \widehat { G } _ { Q h _ { Y Q } } ^ { - 1 } ( \cdot ) \widehat { \textbf { \textit { H } } } _ { Q h _ { A Q } } ( \cdot ) \cdot \widehat { H } _ { P h _ { A P } } ^ { - 1 } ( \cdot ) \cdot \widehat { F } _ { P h _ { X P } } ( \cdot ) } & { { } } \end{array}$ 分别为测验Y和A在 $\varrho$ 上的分数分布，以及测验A和X在 $P$ 上的分数分布。第五步，计算等值标准误（Standard Error ofEquating，SEE）和等值差异标准误（Standard Error ofEquating Difference,SEED)。

Andersson（2016）推导出多级计分IRTKE的渐近标准误，为等值评估提供可靠指标。Wiberg（2016a）提出局部线性IRTKE，用 IRT模型拟合数据，再利用作答反应概率求得线性等值中的总体参数进行等值。Wiberg（2016b）比较了传统方法与IRTKE的表现，但未得出明确结论。Andersson 和Wiberg（2017）系统介绍了基于IRTKE的链等值和后分层等值，发现其等值标准误和偏差均较小。Wang 等人（2020）模拟操纵了样本量、测验长度、数据模拟方式与参照等值，比较 EE、KE、IRTOSE与 IRTKE，发现在随机组设计（EquivalentGroups design，EG）下IRTKE 表现最优，而在NEAT下，IRTOSE 最优。但尚未有学者专门探讨IRTKE 的影响因素。

# 2.2连续化与带宽选择方法

连续化是 KE 的关键。将 $\boldsymbol { \cal X }$ 与连续变量 $\nu$ 加和，得到 ${ \pmb X } ( h _ { X } ) = a _ { X } ( { \pmb X } + h _ { X } { \pmb V } ) +$ $( 1 - a _ { X } ) \mu _ { X }$ $\begin{array} { r } { a _ { X } ^ { 2 } = \frac { \sigma _ { X } ^ { 2 } } { \sigma _ { X } ^ { 2 } + h _ { X } ^ { 2 } } } \end{array}$ $h _ { X }$ $\mu _ { X }$ $\sigma _ { X } ^ { 2 }$ $X$ ${ \pmb Y } ( h _ { Y } )$ 可见， $h _ { X }$ 控制着分数连续化程度。最常用的带宽选择方法为惩罚法（PenaltyMethod)，$\begin{array} { r } { P E N ( h _ { X } ) = \sum _ { j } \bigl ( r _ { j } - f _ { h _ { X } } ( x _ { j } ) \bigr ) ^ { 2 } + K \cdot \sum _ { j } A _ { j } ( 1 - B _ { j } ) } \end{array}$ ，其中 $\pmb { X } ( h _ { X } )$ 的概率密度函数 $f _ { h _ { X } } ( x ) =$ $\begin{array} { r } { \sum _ { j } r _ { j } \phi \big ( R _ { j X } ( x ) \big ) \frac { 1 } { a _ { X } h _ { X } } } \end{array}$ ， $\phi ( \cdot )$ 为标准正态分布的概率密度函数； $\mathrm { \sf ~ K }$ 为常数，当在 $x _ { j }$ 稍偏左位置$f _ { h _ { X } } ^ { \prime } ( x ) < 0$ 时， $A _ { j } = 1$ ，当在 $x _ { j }$ 稍偏右位置 $f _ { h _ { X } } ^ { \prime } ( x ) > 0$ 时， $B _ { j } = 0$ 。

Silverman 经验准则（Silverman'sRuleofThumb method）通过使渐近平均积分平方误差最小化从而求取带宽（Andersson&vonDavier,2014)。为减小异常值的影响，避免过度平滑;同时考虑 $a _ { X }$ ，得到 $\vert h _ { X } = \frac { 9 \sigma _ { X } } { \sqrt { 1 0 0 n _ { X } ^ { \frac { 2 } { 5 } } - 8 1 } } ,$ ，其中， $\sigma _ { X }$ 含义同上， $n _ { X }$ 为参加测验X的考生人数。

Häggstrom和Wiberg（2014）将重复平滑法（Double SmoothingMethod）应用于带宽选  
择。首先，以最小分数单位的一半进行连续化，得到 $\begin{array} { r } { f _ { g _ { X } } ( x ) = \sum _ { j = 1 } ^ { J } r _ { j } \phi \left( R _ { j g X } ( x ) \right) \frac { 1 } { a _ { g X } h _ { g X } } } \end{array}$ ，其  
中， $\begin{array} { r } { R _ { j g X } ( x ) = \frac { x - a _ { g X } x _ { j } - ( 1 - a _ { g X } ) \mu _ { X } } { a _ { g X } h _ { g X } } } \end{array}$ ， $\begin{array} { r } { a _ { g X } ^ { 2 } = \frac { \sigma _ { X } ^ { 2 } } { \sigma _ { X } ^ { 2 } + h _ { g X } ^ { 2 } } } \end{array}$ ，其余指标含义与上文一致或相似。其次，  
利用fx(x），再次连续化得到x(x）=Σfx（x）(Rx（x）。最后，求使重复平滑函  
数最小对应的带宽 $\begin{array} { r } { D S ( h _ { X } ) = \sum _ { l = 1 } ^ { 2 J - 1 } \left( \hat { r } _ { l } - f _ { h _ { X } } ( x _ { l } ) \right) ^ { 2 } } \end{array}$ ，其中 $\begin{array}{c} \begin{array} { r } { \hat { r } _ { l } = \left\{ { r } _ { \frac { l + 1 } { 2 } } , \atop { f _ { h _ { X } } ( x _ { l } . } \right.} \end{array}   \end{array}$ l为奇数) 为偶数

虽有研究表明，三种带宽选择方法均较为优异（Andersson& vonDavier,2014;Häggstrom&Wiberg,2014)，但还未有研究探讨其对IRTKE 的影响。

# 2.3数据模拟方式

在等值模拟研究中，一般借助蒙特卡洛方法，从特定的先验分布中抽取参数值，通过 IRT模型，计算被试作答反应矩阵。该方式便捷、易理解和接受。但研究结论可能偏向IRT等值方法（De Ayala et al.,2018；Norman Dvorak,2009)。如何降低数据模拟方式可能导致的偏差呢？构造伪测验及伪群组法（Pseudo-Test Forms and Pseudo-Groups）最早由 Petersen 等（1982）提出，通过抽取实测数据，构建虚拟测验与考生；尽量保证模拟的现实性而又不失结论的一般性。虽有不少学者将其应用于等值比较（例如，Hagge＆Kolen,2012;Kim&Lu,2018;Powers&Kolen,2012)，但均未涉及IRTKE。验证该方法的可靠性，可为相关研究提供新的切入点。

# 3研究设计

# 3.1研究目的

采用不同数据模拟方式和等值设计，探究带宽选择方法、样本量与题目数量对 IRTKE

的影响。

# 3.2纳入的影响因素

# 3.2.1带宽选择方法

惩罚法、Silverman 经验准则、重复平滑法为三种常用的带宽选择方法，对它们相互比较的同时，亦可提高结论外部效度。

# 3.2.2考生样本量

IRT 参数估计对样本量要求较高，一般取 500 以上（Hambleton&Jones,1993）。结合相关研究（De Ayala etal.,2018;Kim,2014;Liang& von Davier,2014)，共设定三个样本量水平：1000人（小样本）、2000人（中等样本）、5000人（大样本）\*。

# 3.2.3题目数量

根据De Ayala 等人（2018）、Kim（2014）、Liang 和von Davier（2014）及国内考试的试卷构成，并结合抽样数据源情况（见表1)，设定题目量水平：30与45，分别代表较短和中等长度测验。NEAT 锚题比例设定为 $30 \%$ ，即9题与14题。

# 3.2.4等值设计

EG与NEAT涵盖常用等值设计的处理思想，故在二者情况下探究IRTKE的表现。NEAT中具体采用的 EE 方法为链等值（Chained Equating）。

# 3.2.5数据模拟方式

构造法直接在真实数据中抽样以得到满足特定要求的测验与考生样本。IRT法需在特定的先验分布中抽取参数值，从而计算作答矩阵。综合考量二者结果，可提高结论的普适性。

# 3.3数据与工具

数据源为某大型语言测试Form1和Form2（同一批考生；Gonzalez&Wiberg,2017)，各包含80道题（二级计分)。两次测试间隔6个月，基础情况见表1。采用 2PLM拟合Form1数据，得到题目参数信息见表2。

表1语言测试  
表2Form1题目参数  

<html><body><table><tr><td></td><td>Form 1</td><td>Form 2</td><td></td><td>Form 1</td><td>Form 2</td></tr><tr><td>样本量</td><td>8000</td><td>8000</td><td>标准差</td><td>12.66</td><td>12.59</td></tr><tr><td>题目数量</td><td>80</td><td>80</td><td>偏度</td><td>0.12</td><td>0.04</td></tr><tr><td>最低分(理论值)</td><td>9(0)</td><td>11(0)</td><td>峰度</td><td>-0.65</td><td>-0.65</td></tr><tr><td>最高分 (理论值)</td><td>79 (80)</td><td>78(80)</td><td>信度</td><td>0.90</td><td>0.90</td></tr><tr><td>平均值</td><td>43.33</td><td>44.24</td><td>相关</td><td>0.86</td><td></td></tr></table></body></html>

<html><body><table><tr><td></td><td>平均数</td><td>标准差</td><td>最小值</td><td>最大值</td></tr><tr><td>区分度</td><td>0.78</td><td>0.28</td><td>0.15</td><td>1.47</td></tr><tr><td>难度</td><td>0.25</td><td>0.74</td><td>-1.56</td><td>2.13</td></tr></table></body></html>

所有分析采用R（RCore Team,2017）调用软件包kequate（Andersson etal.,2013）、mirt（Chalmers,2012）、equateIRT（Battauz,2015）完成。

# 3.4模拟流程

![](images/9418f5138f0a0d03afbffeac17981c7698bcaa174694df4637efd5a28540d4c1.jpg)  
图1模拟流程

以NEAT为例，详细介绍两种数据模拟方式的研究过程（EG较易，不赘述）。

# 3.4.1 构造法

（1)在Form1中随机抽取试题及全部考生对应作答结果，构造锚测验A、测验X与Y。（2）按Form2成绩是否高于平均分，将考生分成高、低分数组，分别随机抽取考生及其作答结果，构成具有能力差异的两样本。（3）采用不同带宽选择方法，计算IRTKE。（4）重复上述过程500 次，计算评价指标。

# 3.4.2 IRT 法

（1）采用2PLM拟合Form1数据，并计算题目与被试参数。（2）随机抽取试题及对应试题参数估计值，构造锚测验A、测验X与Y。（3）根据能力均值将考生划分成高、低能力组，分别随机抽取能力值，构成具有能力差异的两样本。（4）通过2PLM，计算考生正确作答概率，并将其与从U(0,1)抽取的随机数比较，获得作答矩阵。(5)采用不同带宽选择方法，计算IRTKE。（6）重复上述过程500次，计算评价指标。

# 3.5评价指标

# 3.5.1局部指标

局部指标有百分相对误差（PercentRelativeError，PRE）与 SEE，反映等值方法在单个分数点或原点矩的表现。

(1) PRE度量 $e _ { Y } ( { \pmb X } )$ 与Y的分布差异， $p$ 阶PRE为 $\begin{array} { r } { P R E ( p ) = 1 0 0 \times \frac { \mu _ { p } \left( e _ { Y } ( X ) \right) - \mu _ { p } ( Y ) } { \mu _ { p } ( Y ) } } \end{array}$ ，其中$\begin{array} { r } { \mu _ { p } ( { \boldsymbol { Y } } ) = \sum _ { k } ( y _ { k } ) ^ { p } s _ { k } , \mu _ { p } \bigl ( e _ { \boldsymbol { Y } } ( { \boldsymbol { X } } ) \bigr ) = \sum _ { k } \left( e _ { \boldsymbol { Y } } \bigl ( x _ { j } \bigr ) \right) ^ { p } r _ { j } \circ } \end{array}$

采用链等值可分别得到将测验X等值到A与将锚测验A等值到 $\mathrm { \Delta Y }$ 的 PRE。将二者取绝对值后加和，并求500次的平均值。

（2）SEE 代表随机误差， $\mathit { S E E } _ { Y } ( x ) = \parallel J _ { e _ { Y } } J _ { D F } \pmb { C } \parallel$ ，其中， $J _ { e _ { Y } }$ 为KE 函数关于 $\boldsymbol { r }$ 与 $s$ 的雅可比矩阵； $J _ { D F }$ 为设计函数关于 $\textbf { \textit { r } }$ 与 $s$ 的雅可比矩阵； $c$ 为估计分数概率阶段得到的特殊矩阵，且 $\Sigma _ { r , s } = C o v \left( \begin{array} { l } { r } \\ { s } \end{array} \right) = C C ^ { t }$ ； $\parallel \boldsymbol { v } \parallel = \sqrt { \sum _ { j } v _ { j } ^ { 2 } }$ 。最后，将 500 批 SEE求平均。

# 3.5.2全域标

全域指标刻画等值方法在分数区间或所有原点矩的表现，包含平均PRE（Averaged PRE，APRE）与平均 SEE（Averaged SEE，ASEE）。 $\begin{array} { r } { A P R E = \sum _ { p = 1 } ^ { 1 0 } P R E ( p ) } \end{array}$ ， $A S E E =$ $\begin{array} { r } { \sum _ { i } w _ { i } S E E _ { Y } ( x _ { i } ) } \end{array}$ ，其中， $\begin{array} { r } { w _ { i } = \frac { N _ { i } } { N _ { T } } } \end{array}$ ， $N _ { i }$ 为分数 $\cdot _ { x _ { i } }$ 的人数， ${ { N } _ { T } }$ 为总人数。

# 4结果

# 4.1抽样概况

分别计算各条件组合得到的500批测验X分数的描述统计量，详见表3和表4。

表3模拟分数情况 (EG)  

<html><body><table><tr><td>模拟方式</td><td>样本量-题目量</td><td>平均数</td><td>标准差</td><td>最小值</td><td>最大值</td><td>偏度</td><td>峰度</td></tr><tr><td rowspan="5">构造法</td><td>1000-30</td><td>16.29</td><td>5.18</td><td>0</td><td>30</td><td>0.06</td><td>-0.59</td></tr><tr><td>2000-30</td><td>16.28</td><td>5.19</td><td>0</td><td>30</td><td>0.06</td><td>-0.60</td></tr><tr><td>5000-30</td><td>16.28</td><td>5.19</td><td>0</td><td>30</td><td>0.06</td><td>-0.60</td></tr><tr><td>1000-45</td><td>24.43</td><td>7.45</td><td>1</td><td>45</td><td>0.08</td><td>-0.63</td></tr><tr><td>2000-45</td><td>24.42</td><td>7.45</td><td>1</td><td>45</td><td>0.08</td><td>-0.63</td></tr><tr><td rowspan="6">IRT 法</td><td>5000-45</td><td>24.42</td><td>7.44</td><td>1</td><td>45</td><td>0.08</td><td>-0.63</td></tr><tr><td>1000-30</td><td>13.35</td><td>5.58</td><td>0</td><td>30</td><td>0.45</td><td>-0.35</td></tr><tr><td>2000-30</td><td>13.36</td><td>5.58</td><td>0</td><td>30</td><td>0.45</td><td>-0.35</td></tr><tr><td>5000-30</td><td>13.35</td><td>5.57</td><td>0</td><td>30</td><td>0.45</td><td>-0.35</td></tr><tr><td>1000-45</td><td>20.04</td><td>8.06</td><td>0</td><td>45</td><td>0.49</td><td>-0.33</td></tr><tr><td>2000-45</td><td>20.05</td><td>8.06</td><td>0</td><td>45</td><td>0.49</td><td>-0.33</td></tr><tr><td></td><td>5000-45</td><td>20.05</td><td>8.06</td><td>0</td><td>45</td><td>0.49</td><td>-0.33</td></tr></table></body></html>

表4模拟分数情况 (NEAT)   

<html><body><table><tr><td>模拟方式</td><td>样本量-题目量</td><td>平均数</td><td>标准差</td><td>最小值</td><td>最大值</td><td>偏度</td><td>峰度</td></tr><tr><td rowspan="5">构造法</td><td>1000-30</td><td>19.78</td><td>4.04</td><td>0</td><td>30</td><td>-0.21</td><td>-0.11</td></tr><tr><td>2000-30</td><td>19.78</td><td>4.03</td><td>0</td><td>30</td><td>-0.21</td><td>-0.10</td></tr><tr><td>5000-30</td><td>19.78</td><td>4.03</td><td>0</td><td>30</td><td>-0.22</td><td>-0.11</td></tr><tr><td>1000-45</td><td>29.67</td><td>5.63</td><td>3</td><td>45</td><td>-0.19</td><td>-0.06</td></tr><tr><td>2000-45</td><td>29.67</td><td>5.63</td><td>2</td><td>45</td><td>-0.19</td><td>-0.07</td></tr></table></body></html>

<html><body><table><tr><td></td><td>5000-45</td><td>29.67</td><td>5.64</td><td>2</td><td>45</td><td>-0.19</td><td>-0.07</td></tr><tr><td rowspan="5">IRT法</td><td>1000-30</td><td>17.77</td><td>4.40</td><td>2</td><td>30</td><td>0.26</td><td>-0.40</td></tr><tr><td>2000-30</td><td>17.78</td><td>4.40</td><td>2</td><td>30</td><td>0.27</td><td>-0.39</td></tr><tr><td>5000-30</td><td>17.78</td><td>4.40</td><td>2</td><td>30</td><td>0.27</td><td>-0.39</td></tr><tr><td>1000-45</td><td>26.66</td><td>6.18</td><td>7</td><td>45</td><td>0.38</td><td>-0.36</td></tr><tr><td>2000-45</td><td>26.66</td><td>6.19</td><td>8</td><td>45</td><td>0.38</td><td>-0.36</td></tr><tr><td></td><td>5000-45</td><td>26.66</td><td>6.18</td><td>6</td><td>45</td><td>0.38</td><td>-0.36</td></tr></table></body></html>

# 4.2 EG

# 4.2.1局部表现

据图2，随原点矩阶数升高，PRE均不同程度上扬，等值前后分数分布形态差异逐渐增大。除高阶原点矩和个别情况（图2左下中“sil-1000-30"）外，带宽参数选择方法对分数转换的影响基本无差异。扩大样本量与题目量对降低 PRE 指标有积极作用，其中后者尤为明显（对比图2左上与右上、左下与右下)。当采用 IRT法且30 道题时，各PRE 曲线较分散，数据模拟方式与题目数量间存在交互作用（对比图2左上与左下、右上与右下)。

从SEE 角度（图3)，与PRE 类似，带宽参数选择方法间 SEE 基本无差异，扩大样本量可减小随机误差。但题目量增加反而导致 SEE 稍有扩大。此外，采用构造法得到的 SEE“左高右低”，而IRT法却为“左低右高”。

# 4.2.2全域表现

据表5，在EG中，APRE 较小（除0.27外)，带宽参数选择方法间APRE 无明显差异。样本量与题目数量对其影响与前述一致。采用构造法的APRE较IRT 法小，但差异甚微。

各带宽选择方法间的ASEE/SD 相同，且随样本量增加和题目量减少，有降低趋势，但幅度较小。构造法与IRT 法所得ASEE 基本无差异。

表5全域指标APRE与ASEE (EG)  

<html><body><table><tr><td rowspan="2">样本量-题目量</td><td colspan="8">APRE</td><td colspan="4">ASEE/SD*</td></tr><tr><td colspan="3">构造法</td><td colspan="3">IRT 法</td><td colspan="3">构造法</td><td colspan="3">IRT 法</td></tr><tr><td></td><td>Pen</td><td>Sil</td><td>Dou</td><td>Pen</td><td>Sil</td><td>Dou</td><td>Pen</td><td>Sil</td><td>Dou</td><td>Pen</td><td>Sil</td><td>Dou</td></tr><tr><td>1000-30</td><td>0.04</td><td>0.04</td><td>0.04</td><td>0.06</td><td>0.27</td><td>0.06</td><td>0.03</td><td>0.03</td><td>0.03</td><td>0.03</td><td>0.03</td><td>0.03</td></tr><tr><td>2000-30</td><td>0.02</td><td>0.02</td><td>0.02</td><td>0.04</td><td>0.04</td><td>0.04</td><td>0.02</td><td>0.02</td><td>0.02</td><td>0.02</td><td>0.02</td><td>0.02</td></tr><tr><td>5000-30</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.02</td><td>0.02</td><td>0.02</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.01</td></tr><tr><td>1000-45</td><td>0.02</td><td>0.02</td><td>0.02</td><td>0.03</td><td>0.03</td><td>0.03</td><td>0.04</td><td>0.04</td><td>0.04</td><td>0.05</td><td>0.05</td><td>0.05</td></tr><tr><td>2000-45</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.02</td><td>0.02</td><td>0.02</td><td>0.03</td><td>0.03</td><td>0.03</td><td>0.03</td><td>0.03</td><td>0.03</td></tr><tr><td>5000-45</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.02</td><td>0.02</td><td>0.02</td><td>0.02</td><td>0.02</td><td>0.02</td></tr></table></body></html>

注：Pen、Sil与Dou分别代表惩罚法、Silverman 经验准则、重复平滑法。

# 4.3 NEAT

# 4.3.1局部表现

从PRE 角度，据图4，随原点矩阶数升高，PRE 呈现不同程度上扬。惩罚法与 Silverman经验准则结果重合，对分数转换影响较小；且当题目数量较少时，该优势较突出（对比图4左上与右上、左下与右下)。与EG 相似，题目量增加，PRE 减小；但样本量却几乎不影响PRE。采用 IRT法且题目量为30时，重复平滑法的PRE受考生人数影响较大。同时，基于构造法的PRE 值较IRT法对应值小。

从SEE 角度，据图5，采用构造法时，带宽参数选择方法表现基本一致，仅在高、低分处存在略微差异。采用 IRT法时，带宽参数选择方法仅在中间偏低分数处相似；在高、低分数附近，Silverman 经验准则逊于其他方法；而在中间偏高分数处，优于其他方法。扩大样本量和题目量可减小随机误差。同时，构造法的 SEE 在数值和形态波动上均较 IRT 法小。

# 4.3.2全域表现

参照表6,在NEAT 中，APRE 值较大（最大3.52)。与局部表现一致，惩罚法和 Silverman经验准则的 APRE 较重复平滑法小。样本量增加，APRE 变大，但增量不明显；而题目量增加对降低APRE有显著作用。构造法的APRE 较IRT 法对应值小。

ASEE 指标在带宽选择方法间不存在明显差异，且其随样本量与题目量的增加，均呈减小趋势。构造法的ASEE远小于IRT法对应值。

表6全域指标APRE与ASEE(NEAT)  

<html><body><table><tr><td rowspan="2">样本量-题目量</td><td colspan="6">APRE</td><td rowspan="2">ASEE/SD</td><td colspan="6"></td></tr><tr><td colspan="3">构造法</td><td colspan="3">IRT法</td><td colspan="3">构造法</td><td colspan="3">IRT法</td></tr><tr><td></td><td>Pen</td><td>Sil</td><td>Dou</td><td>Pen</td><td>Sil</td><td>Dou</td><td></td><td>Pen</td><td>Sil</td><td>Dou</td><td>Pen</td><td>Sil</td><td>Dou</td></tr><tr><td>1000-30</td><td>2.07</td><td>2.07</td><td>2.75</td><td>2.29</td><td>2.29</td><td>3.17</td><td></td><td>0.68</td><td>0.69</td><td>0.69</td><td>2.79</td><td>2.63</td><td>2.82</td></tr><tr><td>2000-30</td><td>2.09</td><td>2.09</td><td>2.72</td><td>2.31</td><td>2.31</td><td>3.52</td><td></td><td>0.38</td><td>0.38</td><td>0.38</td><td>0.94</td><td>0.88</td><td>0.96</td></tr><tr><td>5000-30</td><td>2.11</td><td>2.11</td><td>2.73</td><td>2.33</td><td>2.33</td><td>3.33</td><td></td><td>0.28</td><td>0.29</td><td>0.28</td><td>0.43</td><td>0.41</td><td>0.44</td></tr><tr><td>1000-45</td><td>0.96</td><td>0.96</td><td>1.22</td><td>1.19</td><td>1.19</td><td>1.62</td><td></td><td>0.13</td><td>0.13</td><td>0.13</td><td>2.69</td><td>2.56</td><td>2.71</td></tr><tr><td>2000-45</td><td>0.97</td><td>0.97</td><td>1.23</td><td>1.21</td><td>1.21</td><td>1.64</td><td></td><td>0.05</td><td>0.05</td><td>0.05</td><td>0.38</td><td>0.36</td><td>0.38</td></tr><tr><td>5000-45</td><td>0.98</td><td>0.98</td><td>1.24</td><td>1.22</td><td>1.22</td><td>1.66</td><td></td><td>0.03</td><td>0.03</td><td>0.03</td><td>0.04</td><td>0.04</td><td>0.04</td></tr></table></body></html>

注：Pen、Sil与Dou分别代表惩罚法、Silverman 经验准则、重复平滑法。

# 5讨论

# 5.1带宽选择方法与等值设计

带宽选择方法对等值的影响，因等值设计而异。在EG中，带宽选择方法间无较大差异（Häggstrom&Wiberg,2014)；但在NEAT中，惩罚法与 Silverman 经验准则的表现优于重注：上图与下图分别为构造法和IRT法；Pen、Sil与 $\mathrm { D o u }$ 分别代表惩罚法、Silverman 经验准则、重复平滑法；1000、2000、5000与30、35 分别代表样本量和题目量；除左下外，其他各图中三种带宽选择方法结果基本重合。

![](images/aa14e5ba5ab65da5734fc3c14f88998256d7eafdd239bf1b1706e685e33abe3d.jpg)  
图2 PRE(EG)

![](images/c0047e73fa682766dcda492b9efd06ae0a62729ae5cf2f8cf65139d74c7fcf74.jpg)  
图3 SEE (EG)

注：上图与下图分别为构造法和IRT法；Pen、Sil与Dou分别代表惩罚法、Silverman经验准则、重复平滑法；1000、2000、5000与30、35 分别代表样本量和题目量；除左下外，其他各图中三种带宽选择方法结果基本重合；纵轴将所有结果置于标准差单位量尺。

![](images/7384f58d8be57f139b5a31504c49a3a19a8de76c915754ed245f9bc64a336e6b.jpg)  
图4 PRE(NEAT)

注：上图与下图分别为构造法和IRT法；Pen、Sil与 $\mathrm { D o u }$ 分别代表惩罚法、Silverman 经验准则、重复平滑法；1000、2000、5000与30、45 分别代表考生样本量和题目量；除左下图外，其他三种带宽选择方法结果基本重合。

![](images/57b5135346a56346c02186d248c3125bed2cafb78ffbe0d4bd680d7e8a2497e1.jpg)  
图5SEE（NEAT)

注：上图与下图分别为构造法和IRT法；Pen、Sil与Dou分别代表惩罚法、Silverman经验准则、重复平滑法；1000、2000、5000与30、45 分别代表考生样本量和题目量；纵轴将所有结果置于标准差单位量尺。

复平滑法。区分EG与NEAT的关键因素之一是等值群体能力差异（Kolen&Brennan,2014）。为充分体现非等组，依据 Form2 成绩，构造高、低能力的考生群体，其平均分数差异为18.21分（满分80 分)。故而，考生能力水平差异使EG与 NEAT 结果有别，且在同等条件下，前者误差较后者小（Dorans et al.,2008; Sinharay& Holland,2010;Wang et al.,2008)，这在本研究两大类指标中均有所体现。综合两种等值设计，惩罚法与 Silverman 经验准则表现较优。保留两位小数，二者 PRE 值相同。这可能是Forml分数特征与标准正态分布相近，而 Silverman 经验准则正是基于正态分布的简单算法（Wallin et al.,2017）。Andersson 和von Davier（2014）也有相似发现，当分数分布较为平滑时，惩罚法第一部分表现优异；反之，Silverman 经验准则较好。Silverman 经验准则计算简单、直接；但当分数分布非正态时，误差可能较大。可见，各方法具有一定程度的稳健性。

# 5.2考生样本量与题目数量

其他条件不变，增大样本量可降低 SEE（Kolen&Brennan,2014)，这在 NEAT 中最明显。二者间存在边际递减关系——SEE 降低的幅度随样本量增大而逐渐变小。Godfrey（2007）发现，当样本量较小时，KE 与常用等值方法间存在明显差异；但随其增大，各方法趋于一致。Kim（2014)、Liang和vonDavier（2014）的结论类似。这是因为，等值系统误差主要来源于估计准确性、统计假设、等值设计与组间差异，受随样本量影响较小。而主要来源于抽样代表性的随机误差则会随样本量增大而减小（Kolen&Brennan,2014)。因此，适当增加样本量可提高等值准确性。受限于数据源的题目量，本研究未探讨测验题目量较大的情况。

不计其他因素，测验题目量与信度成正比，可为等值提供有利保障；但题目增多也使分数区间扩张，分配到各分数点的考生量减少，导致误差扩大（Wang etal.,2008)。在实际情况中，随题目数量增多，信度影响等值的增量变小，而各分数的频率却会急遽减小。EG 中的 SEE 指标也体现此点。例如，Norman Dvorak（2009）发现，当题目量从25道增加到75道时，测验信度不断增加，而KE的均方根差异等误差指标也在随之增大。

但在 NEAT中，锚测验题目增多可降低等值误差。锚测验是分离考生能力差异与试卷难度差异的关键因素，适当增加其长度，可更好地区分两种差异。例如，Andersson（2016）和 Kim（2014）发现，增加锚题比例可有效减小等值系统误差。锚测验长度对等值准确性的影响也受边际递减效应制约，比如APRE 和ASEE的表现。除此之外，在图5中，当采用 IRT 法且样本量为1000 时，在30 分左右，题目数量增加反而导致 SEE 变大，这与ASEE 结果不一致。对比两种条件的原始分数分布（未呈现)，题目数量为30时，分数集中于15左右；题目数量为45时，分数集中于25左右。SEE 与 ASEE 结果不一致主要由于后者为考虑分数分布的加权指标（整体表现)。而仅在相同分数位置比较（局部表现）时，题目数量增加可降低 SEE，这一结论在大多数情况下（除30分左右外）

仍成立。未来可详细探讨锚题比例（锚题数量）对IRTKE的影响。

# 5.3数据模拟方式

构造法的初衷是对数据模拟方式偏向性的质疑。结果表明，基于构造法的指标较 IRT法小，其中以NEAT 的ASEE 最为突出。构造法与IRT法的 SEE 形状存在较大差异，但二者与其他因素间不存在明显的交互作用。结合表3与表4推测，相较于IRT法，构造法获得的分数偏高且更为集中，故而低分段人数较少，从而导致SEE 偏大。von Davier等人（2004）详细描述并解释过KE 中这种常见的“两端高中间低”的情况。但该差异是否由数据模拟方式造成，能否影响分数解释，尚无定论。须慎重对待仅采用IRT法的研究结果，可选择较为中立的构造法开展研究，未来仍需深入探索二者间的差异与原因。

# 6结论

IRTKE 具备IRTOSE 和KE 的优异特性，本研究从不同等值设计和数据模拟方式角度，探讨带宽选择方法、样本量、题目数量对其的影响，主要得出以下结论：（1）在EG中，惩罚法、Silverman经验准则和重复平滑法表现相似。（2）在 NEAT 中，惩罚法与 Silverman 经验准则表现较佳。特别地，在极端分数附近，Silverman 经验准则略逊于其余两种方法；而在中间偏高分数处，表现较优。（3）在一般情况下，增大考生样本量和题目数量均可降低等值误差，该现象在NEAT 中最为明显。（4）数据模拟方式可干扰结果，在涉及方法比较的研究中，尤其是当待比较的方法与数据模拟方式共享某种理论时，应尽量避免其对结果的误导。

致谢：感谢华南师范大学心理学院研究生甄锋泉在模拟代码编写过程中提供的帮助！

# 参考文献

罗莲.(2008)．一种新的等值方法：核等值法．心理学探新,28(2),69-74.   
王少杰，张敏强，李拓宇，梁正妍.(2020).核等值：一种观察分数等值体系．心理科学进展,28(5),855-870.   
Andersson,B.(2016).Asymptotic standard erors of observed-score equating with polytomous IRT models.Journal of Educational Measurement, 53(4),459-477.   
Andersson,B.,Branberg,K.,& Wiberg,M.(2O13).Performingthe kernelmethodof testequating withthe package kequate. Journal of Statistical Software,55(6),1-25.   
Andersson,B.,&von Davier,A.A.(2O14). Improving the bandwidth selection in kermel equating.Journal ofEducational Measurement, 51(3),223-238.   
Andersson,B.,&Wiberg,M.(2017).temresponse theory observed-score kermel equating.Psychometrika,82(1),48-66.

Batauz,M.(2O15).equateIRT: AnR packagefor IRT test equating.Journal of Statistical Software,68(7),1-22.

Chalmers,R.P.(2012).mirt:Amultidimensional itemresponse theory package for theRenvironment.JournalofStatistical Software, 48(6),1-29.

De Ayala,R.J.,Smith,B.,& Norman Dvorak,R. (2018). Acomparative evaluationofkernel equating and testcharacteristic curve equating. Applied Psychological Measurement, 42(2),155-168.   
Dorans,N.J.,Liu,J. H.,& Hammond,S. (2o08). Anchor test type and population invariance: An exploration across subpopulations and test administrations.Applied Psychological Measurement,32(1),81-97.   
Godfrey，K.E. (2o07).A comparisonof kernelequatingand IRTtrue score equatingmethods (Unpublished doctorial dissertation). The University of North Carolina at Greensboro.   
Gonzalez, J.,& Wiberg, M. (2017). Applying test equating methods: Using R. Springer.   
Hagge,S.L.,& Kolen,M.J. (2012).Effcts of group diferences on equatingusing operational and pseudo-tests.In M. J. Kolen & W.Lee (Eds.),Mixed-format tests: Psychometric properties with a primary focus on equating (volume 2) (pp. 45-86). CASMA,The University of Iowa.   
Haggstrom,J.,&Wiberg,M.(2014).Optimalbandwidth selection inobserved-score kernelequating.JournalofEducational Measurement, 51(2),201-211.   
Hambleton,R. K.,&Jones,R.W. (1993).An NCME instructional module on: Comparisonof clasical test theoryand item responsetheoryand theirapplications totestdevelopment.Educational Measurement: Issues and Practice,12(3),38-47.   
Jiang,Y.L.,von Davier,A.A.,& Chen, H.W. (2Ol2).Evaluating equating results: Percent relativeerorforchained keel equating. Journal of Educational Measurement, 49(1),39-58.   
Kim,H.Y. (2O14).A comparison of smoothing methods forthecommon item nonequivalent groups design (Unpublished doctorial dissertation). University of Iowa.   
Kim,S.,&Lu,R. (2O18).The pseudo-equivalent groups approachas analternative tocommon-item equating.ETS Research Report Series,2018(1),1-13.   
Kolen,M.J.,&Brennan,R.L. (2014). Test equating,scaling, and linking: Methods and practices (3rd ed.).Springer.   
Leoncio,W.,& Wiberg,M. (2017).Evaluating equating transformations from different frameworks.In M. Wiberg,S. Culpepper, R. Janssen, J. Gonzalez,&D.Molenaar (Eds.), Quantitative psychology (pp.101-110). Springer.   
Liang,T.,&vonDavir,A.A.(2014).Cro-validation: Analterativebandwidt-slection methdinkerelequatingApplied Psychological Measurement, 38(4),281-295.   
Lord,F.M.,& Wingersky,M.S.(1984).ComparisonofITtrue-scoreandequipercentileobserved-score“equatings.Applied Psychological Measurement, 8(4), 453-461.   
Norman Dvorak,R.L.(209).Acomparisonofkernelequating to thetestcharacteristiccurve method (Unpublisheddoctorial dissertation). University of Nebraska.   
Petersen,N.S.,arco,G.L,&Stewart,E.E.(1982).Atestof theadequacyoflinearcoreequating models.InP.W.Holland & D.B. Rubin (Eds.), Test equating (pp.71-135). Academic Press Inc.   
Powers,S.J.,& Kolen,M.J. (2O12). Using matched samples equating methods to improve equating accuracy. In M.J.Kolen & W.Lee (Eds.),Mixed-format tests: Psychometric properties with a primary focus on equating (volume 2) (pp.87-114). CASMA, The University of Iowa.   
R Core Team. (20l7). R: A language and environment for statisticalcomputing. R Foundation forStatistical Computing.   
Sansivieri, V., Wiberg,M.,& Mateucci, M. (017). Areview of test equating methods with a special focuson IRT-based approaches. Statistica, 77(4),329-352.   
Sinharay,S.,&Holland,P.W. (2010).Anewapproach tocomparing several equating methods in thecontextof the NEAT design. Journal of Educational Measurement, 47(3),261-285.   
vonDavier,A.A.,&Chen, H. W. (20l3).The kernelLevine equipercentileobserved-score equatingfunction.ETS Research Report Series,2013(2), i-27.   
von Davier,A.A., Holland,P.W., & Thayer,D.T. (2004). The kernel method of test equating.Springer.   
Walin,G.,Haggstrom,J,&Wberg,M.(2017).Howtoelecttebandwidthinerelequatig-Anvalationofivediet methods.InM. Wiberg,S.Culpepper,R.Jansen,J.Gonzalez,&D.olenar (Eds.),Quantitative psychology (pp.91- 100). Springer.   
Wang,S.J., Zhang,M.Q.,& You,S. (2020). Acomparison of IRTobserved score kemel equating andseveral equating methods.Frontiers in Psychology,11,Article 308.https://doi.org/10.3389/fpsyg.2020.00308   
Wang,T.Y.,Lee,W.C.,Brennan,R.L.,&Kolen,M.J.(2Oo8).Acomparison of the frequency estimation andchained equipercentile methods under thecommon-item nonequivalent groups design.Applied Psychological Measurement,32(8), 632-651.   
Wiberg,M. (2016a). Alternative linear item response theory observed-score equating methods.Applied Psychological Measurement, 40(3),180-199.   
Wiberg,M.(2O16b).Ensuring testqualityover timeby monitoring the equating transformations.InL.A.van der Ark,M. Wiberg,S.A. Culpepper,J.A. Douglas,& W. C. Wang (Eds.), Quantitative psychology (pp. 239-251). Springer.

# Effects of Several Factors on IRT Observed Score Kernel Equating

Wang Shaojie, Zhang Minqiang, Huang Feifei, Huang Lifang, Yuan Qiting (School ofPsychology, South China Normal University, Guangzhou,510631)

# Abstract

Atributing to its advantages of pre-smoothing and continuization of score distributions, kernel equating has been testified and shown equivalent to or better than other equating methods,especially traditional ones, in the aspect of equating accuracy and stability. IRT observed score kernel equating is formed by integrating kernel equating and IRT observed score equating.Few researches have focused on evaluating its performance systematically. Therefore， bandwidth selection method， sample size, test length, equating design, and data simulation methods were investigated about their influence on it.

To ensure ecological validity, data from a large-scale assessment were used as the sampling pool. IRT data simulation method and pseudo tests and pseudo groups simulation method were used to avoid the simulation preference in random Equivalent Groups design (EG) and Non-Equivalent groups with Anchor Test design (NEAT).In detail, bandwidth selection methods included Penalty method,Silverman's rule of thumb method, and Double smoothing method.Levels of sample size were 1000,2000,and 5000. Meanwhile，test containing 30 items and 45 items were considered.Finally,local criteria and universal criteria were computed, the former of which were Percent Relative Error (PRE) and Standard Error of Equating (SEE),and the latter of which were Averaged Percent Relative Eror (APRE) and Averaged Standard Eror of Equating (ASEE).

It was found out that in EG,regarding local criteria,PRE increased as central moment became higher, which also meant that the distribution difference before and after equating was enlarged. Nonetheless, considering that PRE was formed by multiplying initial difference with 100,bandwidth selection methods performed alike. On the other hand,PRE was significantly reduced by increasing sample size and lengthening tests,especially by the later one.Similar to PRE,when it came to SEE,there was no diffrence between effect of bandwidth selection methods.Larger sample size rendered less random error, which was contrary to test length.Furthermore,curves of SEE were “high at left but low at right" for pseudo tests and pseudo groups method,and "low at left but high at right” for IRT simulation method.As foruniversal criteria, APRE among bandwidth selection methods were alike, which were all small. Efects of sample size and test length were same as observed in local criteria. There was no significant difference between ASEE for two data simulation methods.

In NEAT,regarding local criteria, PRE increased as central moment became higher. The results of Penalty method and Silverman's rule of thumb method coincided, which were superior to others.And this trend was more evident when test is shorter. PRE was significantly reduced by lengthening tests as in EG, but not by increasing sample size.To be mentioned was the results that PRE for Double smoothing method was most influenced by sample size when test included 30 items and IRT simulation method was used, which indicated some interactions among them. When it came to SEE,bandwidth selection methods performed alike, only showing discrepancies at extreme scores. Increasing sample size and lengthening test could reduce random error. Meanwhile,distribution of SEE for pseudo tests and pseudo groups method was more stable than that for IRT method.As for universal criteria,the trends for APRE and ASEE were same as those in local criteria.

To summarize, performances ofbandwidth selection methods were similar in EG, but Penalty method and Silverman's rule of thumb method prevailed in NEAT. Bandwidth selection,sample size,and test length affected IRT observed score equating together. Preference of data simulation methods was spotted, which suggested researchers that multiple simulation methods and designs should be conducted before final conclusions are drawn in the field of comparison of equating method. Further study should focus more on the systematic evaluation of equating.

Key words IRT observed score kernel equating; bandwidth selection methods; equating design; data simulation methods