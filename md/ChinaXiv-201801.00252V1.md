# 欧盟碳排放权市场重大公告事件对碳价格的影响

![](images/bf75ddbe9ce5564822ba308b0634e8feca4ec2bb204977fa003dea51862e8249.jpg)

# 贾君君12 许金华2\*\*范英

1合肥工业大学经济学院合肥230601  
2中国科学院科技战略咨询研究院北京100190  
3 北京航空航天大学 经济管理学院北京 100191

摘要随着全球气候变化问题不断突出，建立碳排放权交易市场成为各国政府应对气候变化、控制温室气体排放的重要措施。作为新生市场，碳市场价格容易受到制度类重大公告事件的较大冲击。文章通过在传统AR-GARCH模型的均值方程和波动方程中加入双边修正虚拟变量，提出双边修正虚拟变量的事件研究方法；以欧盟碳市场国家配额分配计划（NAP）公告和核证排放量公告（VEA）事件为例，分析了重要公告的发布对碳价格的潜在影响。实证结果表明，双边修正虚拟变量方法可以有效捕捉公告事件对碳价收益率和波动性的事前、事后影响过程。国家配额分配计划公告对碳价收益产生了显著的正向影响，且表现出较长的事前影响。核证排放量公告在碳市场第一阶段对碳价收益产生了显著的事后负向影响，在第二和第三阶段对碳价收益产生了显著的事前和事后正向影响，且在两阶段对碳价波动性都没有显著影响。第一阶段的核证排放量信息为市场预期提供了准确参考，使第二和第三阶段的核证排放公告对碳市场的影响减弱。

关键词碳排放权交易机制，国家分配计划公告，核证排放量公告，双边修正虚拟变量法，碳价收益率和波动率

DOI 10.16418/j.issn.1000-3045.2017.12.009

\*资助项目：国家自然科学基金项目（71673266、71210005、71403263)  
\*\*通讯作者  
修改稿收到时间：2017年12月6日

为控制并减少温室气体的排放，国际社会先后达成《京都议定书》和《巴黎协定》，明确 2008—2020年各成员国的减排目标，为2020年之后全球应对气候变化行动做出安排。作为成本有效的减排政策工具，碳排放权交易机制被越来越多的国家和地区采用。欧盟碳市场是迄今为止全球最大的碳排放权交易市场，而其作为新生市场，各类制度类公告事件可能对碳价格产生重大冲击。2006年4月，关于捷克、荷兰等国核证排放量公告（Verified

EmissionsAnnouncement，VEA）发布导致碳价格出现结构性断点[1]。因此，分析碳市场重大公告事件对碳价格的冲击和影响，有助于提高人们对碳价形成机制的认识，加深对碳市场运行机制的理解。

在欧盟碳市场中，国家分配计划（NationalAllocationPlan，NAP）公告和VEA制度至关重要。NAP确定各阶段配额的分配总量及分配方式，各国NAP中的配额分配数量之和决定了第一阶段（2005一2007年）与第二阶段（2008一2012年）的配额供给总量；VEA每年定期公布上一年度的二氧化碳排放量，将随着能源价格、天气状况等因素随机变化的二氧化碳排放量确定化，该排放量反映了履约企业对配额的需求量。这两类公告事件的发生直接影响市场对配额供需的预期，可能会对碳价产生重大冲击。虽然美国在2017年6月宣布退出《巴黎协定》，但是我国承诺致力于推进协定的实施，实现2030年碳减排承诺目标。目前，我国正积极筹备建立全国统一碳市场，希望通过碳排放权交易机制以较低成本实现减排目标。但是，碳价的剧烈波动会对碳市场的稳定运行带来重大冲击。本文通过分析NAP和VEA两大制度对碳市场的影响过程，厘清公告事件对碳市场的影响机制，为市场监管层提供事件的事前事后影响评估，为交易者制定合理的交易策略提供参考。

# 1国内外研究现状

研究事件影响的常用方法包括事件学习法和虚拟变量法。事件学习法通过计算事件窗口期的异常收益刻画事件对市场的影响过程。虚拟变量法在回归方程中加入代表事件发生的变量，通过虚拟变量的回归系数定量考察事件的影响。当前，已有一些文献使用上述两类方法分析碳市场相关事件的影响。Miclaus等2使用自回归-广义自回归条件异方差模型（AutoRegressive(1)-GeneralizedAutoRegressive Conditional Heteroskedasticity(1,1)，AR(1)-GARCH(1,1)）模型估计碳价的正常收益。通过事件前后异常收益的分析发现，与NAP公告相比，2005年和2006年的VEA对碳市场的影响更明显。Hitzemann等[3]使用标准的事件学习法分析2005—2009年的VEA的影响，结果发现公告对碳价的影响逐年减弱并且没有发现信息泄露的证据。Mansanet-Bataller和 Pardo[4]、Lepone等[5]结合截断正常收益异常值的事件学习法与虚拟变量法，研究NAP公告与VEA。结果表明这两类公告对碳价的收益率有显著影响，但对碳价波动性的影响较弱。Deeney等发现当欧洲议会在市场情绪低落或者市场敏感度较低的情景下发布非“党派政治”决定时，碳价会下降并且碳价收益的波动会上升。Koch等研究欧盟碳市场碳排放上限调整对碳价的影响，结果表明，推迟拍卖的若干决定导致碳价下降，而2020年和2030年欧盟气候政策的发布则导致碳价上升。

在碳价驱动因素的研究中，通过引入代表气候因素的虚拟变量，研究发现碳价不仅受到能源价格的影响，也受到天气状况的影响。具体地，Mansanet-Bataller等发现德国的极端气温对碳价收益产生了显著的正向影响;Rickels等发现欧洲的极热天气对碳价收益产生了显著的负向影响。Wilfried等[10证明2005—2006 年碳价收益并没有受到风速的显著影响，但陈晓红和王陟昀[]却发现2006年5月到2007年年底风速对碳价收益产生了显著的负向影响。Creti等[12]的研究表明降雨量等其他气候学因素未对碳价收益产生显著影响。Alberola和Chevallier[13]借助虚拟变量发现法国禁止将第一阶段多余的配额存储到第二阶段的公告打压了碳价。Conrad等[4在分整非对称幂广义自回归条件异方差模型中引入虚拟变量对高频碳价格进行分析，结果发现，与美国和德国经济运行指数的公告相比，第二阶段NAP相关的公告对碳价的影响更强、更持久。刘纪显和苏艺龙[15发现2009年开始的欧债危机对碳价产生了显著影响。

通过改进虚拟变量的建模方法，可以刻画事件的持续影响。Schmidbauer和Rosch[6通过在事件发生的一侧添加虚拟变量以刻画石油输出国组织公告对油价的影响;Jia 等[7在事件发生的两侧修正虚拟变量以捕捉事件的影响过程。本文使用双边修正虚拟变量的建模方法，克服了传统虚拟变量只能刻画事件单一影响的缺陷，完整地刻画 NAP公告和VEA制度对碳价的影响过程（影响的产生$$ 持续 $$ 消失过程），并且分析了两类公告事件在欧盟碳市场第一和第二阶段对碳价格收益率和波动性的影响。

# 2事件持续影响模型

在对碳价的收益与波动建模的基础上，本文分别在均值方程和波动方程中加入修正的虚拟变量，以刻画公告事件对碳价的影响过程。通过最小化赤池信息量（akaikeinformationcriterion，AIC）选择修正虚拟变量的最优参数，以及对碳价期望收益率和波动率建模的最优模型。

# 2.1 基本模型

本文使用AR-GARCH模型对碳价进行建模[18]，在均值方程和波动方程中加入双边修正的虚拟变量，刻画NAP公告和VEA对碳价期望收益率和波动率的影响过程：

$$
r _ { t } = { \bf c } + \sum _ { s \geq l } a _ { s } r _ { t - s } + b d _ { t } + \varepsilon _ { t } ,
$$

$$
\begin{array} { r c l } { { } } & { { } } & { { \varepsilon _ { t } = \nu _ { t } \sqrt { h _ { t } } , } } \\ { { } } & { { } } & { { } } \\ { { } } & { { } } & { { h _ { t } = \omega + \alpha \varepsilon _ { t - l } ^ { 2 } + \beta h _ { t - l } + \gamma d _ { t } , } } \end{array}
$$

$d _ { t } \mathrm { = } \big \{ \begin{array} { l } { 1 _ { } } \\ { 0 _ { } } \end{array} \big _ { 0 \mathrm { . } }$ ，在第 $t$ 天发生公告事件在第 $t$ 天没有发生公告事件其中，式（1）对碳价收益进行建模，c是常数项； $\boldsymbol { r } _ { t }$ 是第 $\mathbf { \chi } _ { t }$ 天的碳价对数差分的日序列数据，即碳价在第 $\mathbf { \chi } _ { t }$ 天的对数收益； $r _ { t - s }$ 是碳价对数收益滞后 $s$ 期的序列数据;$a _ { s }$ 是对应于 $r _ { t - s }$ 的待估系数。 $d _ { t }$ 是传统的虚拟变量，具体定义见式（4），在式（1）中用于刻画公告对碳价格期望收益率的影响， $b$ 是对应于 $d _ { t }$ 的待估系数。 $\boldsymbol { \varepsilon } _ { t }$ 是第 $t$ 天的残差。式（2）和（3）是GRACH(1,1)模型[19]，对碳价收益的条件方差进行建模。 $h _ { t }$ 是 $\boldsymbol { \varepsilon } _ { t }$ 在第 $t$ 天的条件方差;$\nu _ { t }$ 是高斯白噪声并且Var $( \nu _ { t } ) { = } 1$ 。在式（3）中， ${ \bf { \omega } } _ { \infty } \Leftrightarrow \Leftrightarrow \Leftrightarrow \infty \quad \scriptstyle { { \bf { \omega } } _ { \infty } } ( 0 ) = { \bf { \dot { \omega } } } _ { \infty } ( 0 )$ 是方差式中的常数项； $\boldsymbol { \varepsilon } _ { t - l }$ 是残差滞后1期的序列； $\scriptstyle a$ 是对应于 $\boldsymbol { \varepsilon } _ { t - l }$ 的待估系数； $h _ { t - I }$ 是滞后1期的条件方差序列； $\beta$ 是对应于 $h _ { t - I }$ 的待估系数； $d _ { t }$ 是传统的虚拟变量，用于刻画公告对碳价收益的波动率的影响；y是对应于 $d _ { t }$ 的待估系数。

# 2.2双边修正虚拟变量的影响过程建模

传统的虚拟变量建模方法只能通过设置0-1变量对事件的影响进行单一刻画（图1）。本文使用双边修正虚拟变量的方法，以刻画公告的影响过程，即公告的影响是何时开始的，持续多久，以及如何消失。

![](images/2eb5f144e1679dcb917b6035971dde20ecf05945ee8b8359d94309b15f1a6486.jpg)  
图1传统未经修正的虚拟变量t为公告事件发生的日期

给定虚拟变量序列$d ^ { ( 0 ) } = ( d _ { t } ) = ( 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 1 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 ) ,$ 。以下4步说明修正虚拟变量的过程：

(1）在 ${ d } ^ { ( 0 ) }$ 中1的位置后面设置 $s _ { 1 }$ 个1，得到 $\boldsymbol { d } ^ { ( 1 ) }$ （2）在 $\boldsymbol d ^ { ( 1 ) }$ 中的最后一个1后面，用以 $s _ { 2 }$ 为首项， $s _ { 2 }$ 为公比的等比数列取代原先的若干个0。其中 $\boldsymbol { s } _ { 2 } \in [ 0 , 1 )$ ，当等比数列的末项小于0.1时，将该位置及之后位置上的数字设为0，从而得到 $\boldsymbol { d } ^ { ( 2 ) }$

(3）在 $\boldsymbol d ^ { ( 2 ) }$ 中第一个1之前设置 $s _ { 2 }$ 个1，得到 $\boldsymbol { d } ^ { ( 3 ) }$

（4）在 $\textit { d } ^ { ( 3 ) }$ 中第一个1之前，以相反方向用以${ } _ { S _ { 4 } }$ 为首项，以 $s _ { 4 }$ 为公比的等比数列取代若干个0：其中 $\mathbf { \sigma } _ { S _ { 4 } \in \left[ 0 , \ 1 \right) }$ ，当等比数列的末项小于0.1时，将该位置及之前位置上的数字设为0，从而得到 $d ^ { ( 4 ) }$ 。

修正后的虚拟变量 $\boldsymbol { d } ^ { ( 4 ) }$ 由4个参数 $s _ { i } ( i { = } 1 , 2 , 3 , 4 )$ 决定，称 $( s _ { 1 } , s _ { 2 } , s _ { 3 } , s _ { 4 } )$ 为一个方案。其中， $s _ { 1 }$ 描绘恒定影响在公告发生后的持续天数； $s _ { 2 }$ 描绘了影响的消失速度； $s _ { 3 }$ 描绘了恒定影响在公告发生前的持续时间； $s _ { 4 }$ 描绘了影响的建立速度。虚拟变量 $d ^ { ( 4 ) }$ 经过方案 $( 5 , \frac { 1 } { 2 } , 3 , \frac { 2 } { 5 } )$ 修正后得到的结果如图2所示。当 $s _ { i } = 0 ( i \mathrm { = } 1 , 2 , 3 , 4 )$ 时，修正后的虚拟变量等同于对虚拟变量的传统定义，此时， $\boldsymbol { d } ^ { ( 4 ) } = \boldsymbol { d } ^ { ( 0 ) }$ 。

![](images/996b70916f22b59c58c5b6740565005576a95f0b19b1d7e6e493159ff5246a10.jpg)  
图2新改进后的虚拟变量

# 2.3最优模型的选择

在选择修正虚拟变量的最优方案时，首先，将经方案 $( s _ { 1 } , s _ { 2 } , s _ { 3 } , s _ { 4 } )$ 修正的虚拟变量依次带入式（1）进行拟合，选取AIC值最小的方案作为最优方案。找到适合式（1）的最优方案并且式（1）的残差 $\boldsymbol { \varepsilon } _ { t }$ 通过序列相关及异方差性检验之后，对式（2）和（3）进行拟合，重复式（1）中的选择过程，得到式（3）中修正虚拟变量的最优方案。通过筛选最优的虚拟变量修正方案，得到刻画碳价期望收益率和波动率的最优模型。上述算法的实现通过R语言编写程序完成。

# 3数据

本文使用每年12月份到期的碳配额期货价格日度数据，数据来自欧洲环境署（EuropeanEnvironmentAgency）和洲际交易所（Intercontinental Exchange），数据跨度为2005—2013年。由于欧盟碳市场第一阶段多余的配额不能在第二阶段使用，而第二、第三阶段的配额可以通用；因此，第一阶段公告事件的影响被单独研究，第二、第三阶段被合并到一起研究。

表1给出第一阶段与第二阶段发布NAP公告的日期，并对发布的NAP公告内容进行简要描述；表2给出第一阶段与第二阶段VEA公告的发布日期及数据描述。表3给出2005一2012年每年分配的配额量和核证排放量，以及两者的当年差额和累计差额。

根据AugmentedDickey-Fuller（ADF）单位根检验，所有价格序列都是一阶单整的，即 $I ( 1 )$ 。所以，所有价格序列均被转化为一阶对数差分的形式，以适应本文使用的模型。

表12005一2013年国家分配计划（NAP）公告与碳价格序列样本信息  

<html><body><table><tr><td>公告阶段</td><td>公告日</td><td>事件描述</td><td>期货合约</td><td>数据跨度</td><td>样本个数</td></tr><tr><td rowspan="2">NAP I</td><td>2005-03-08</td><td>批准波兰的NAPI</td><td>2007年12月</td><td>2005-01-03-2007-12-03</td><td>748</td></tr><tr><td>2005-04-12</td><td>批准捷克的NAPI 批准德国、希腊、爱尔兰、拉脱维亚、立陶宛、卢森堡、马耳他、斯洛伐克</td><td></td><td></td><td></td></tr><tr><td rowspan="4">NAP I</td><td>2006-11-29</td><td>和瑞典的NAP I</td><td></td><td></td><td></td></tr><tr><td>2007-08-31</td><td>批准丹麦的NAP I</td><td>2012年12月</td><td>2006-06-26—2012-12-31</td><td>1666</td></tr><tr><td>2009-02-27</td><td>批准挪威的NAP I</td><td></td><td></td><td></td></tr><tr><td>2009-12-11 2011-12-05</td><td>拒绝波兰及爱沙尼亚的NAPII 批准爱沙尼亚的NAPI</td><td></td><td></td><td></td></tr></table></body></html>

数据来源：http://ec.europa.eu/clima/index_en

表22005一2013年核证排放量公告（VEA）日期与碳价格序列样本信息  

<html><body><table><tr><td>公告阶段</td><td>公告日</td><td>数据跨度</td><td>样本个数</td></tr><tr><td rowspan="2">VEA I</td><td>2006-04-25</td><td>2006-01-09—2007-12-17</td><td rowspan="2">500</td></tr><tr><td>2007-04-02</td></tr><tr><td rowspan="5">VEA I</td><td>2009-04-01 2010-04-01</td><td rowspan="4">2008-01-02-2013-12-31</td><td rowspan="4">1532</td></tr><tr><td>2011-04-01</td></tr><tr><td>2012-04-02</td></tr><tr><td>2013-04-02</td></tr><tr><td></td><td></td><td></td></tr></table></body></html>

a数据来源：http://ec.europa.eu/clima/index_enb为了获得较长的碳价格序列以覆盖公告日，碳价在每年12月份期货合约到期月的第1天翻转到次年12月份到期的期货合约

表32005一2012年配额分配量及排放量的数量关系（单位：百万吨 $_ { \mathsf { C O } _ { 2 } ) }$   

<html><body><table><tr><td></td><td>年份</td><td>配额分配量</td><td>核证排放量a</td><td>差额</td><td>累计差额</td></tr><tr><td rowspan="3">第I阶段</td><td>2005</td><td>2089</td><td>1995</td><td>94</td><td>94</td></tr><tr><td>2006</td><td>2064</td><td>2005</td><td>59</td><td>153</td></tr><tr><td>2007</td><td>2145</td><td>2086</td><td>59</td><td>212</td></tr><tr><td rowspan="5">第Ⅱ阶段</td><td>2008</td><td>1959</td><td>2120</td><td>-161</td><td>-161</td></tr><tr><td>2009</td><td>1975</td><td>1880</td><td>95</td><td>-66</td></tr><tr><td>2010</td><td>1998</td><td>1939</td><td>59</td><td>-7</td></tr><tr><td>2011</td><td>2017</td><td>1904</td><td>113</td><td>106</td></tr><tr><td>2012b</td><td>2050</td><td>1788</td><td>262</td><td>368</td></tr></table></body></html>

a数据来源：根据EUTL网站（htp://ec.europa.eu/environment/ets/）上的原始数据计算得到b由于统计口径差异，2012年分配给航空业的配额及核证数据未统计在内

# 4实证结果与讨论

# 4.1 NAP公告的影响与讨论

表4给出经过筛选后的最优模型的实证结果，分别衡量了第一阶段与第二阶段NAP公告事件对碳价期望收益率和波动率的影响。各参数估计值对应式（1）到式（3）中的参数值。图3是均值方程和方差方程中经双边修正后的虚拟变量图示。

表4和图3表明NAPI公告对第一阶段的碳价期望收益产生了显著的正向影响，对碳价波动未产生显著影响；NAPI公告不仅对碳价期望收益产生了显著的正向影响，也显著增加了碳价的波动。具体地，NAPI公告对碳价期望收益的影响从公告发布之前的第33天开始便逐渐形成，在公告发布之前的第11天开始形成恒定的影响（表4），一直持续到公告发布后的第6天为止；但NAPI公告未对碳价波动产生显著影响。NAPⅡI公告对碳价期望收益的影响从公告发布之前的第7天开始一直持续到公告发布之后的第3天为止；此外，NAPII公告显著增加了碳价的波动性，影响从公告发布之前的第31天开始便逐渐形成，在公告发布之前的第10天开始形成恒定的影响（表4），一直持续到公告发布之后的第6天为止。

表4国家分配计划（NAP）公告对碳价期望收益与波动的影响过程的实证结果  

<html><body><table><tr><td rowspan="2"></td><td colspan="2">NAP公告阶段</td></tr><tr><td>第I阶段</td><td>第Ⅱ阶段</td></tr><tr><td>均值方程中的滞后阶数</td><td>1</td><td>1,2</td></tr><tr><td>最终的均值方程 C a</td><td>-0.008**</td><td>-0.001</td></tr><tr><td></td><td>0.108**</td><td>0.176**</td></tr><tr><td>a</td><td></td><td>-0.077**</td></tr><tr><td>b</td><td>0.035**</td><td>0.011**</td></tr><tr><td>均值方程中虚拟变量的修正方案a</td><td>(6,0,11,0.9)</td><td>(3,0,7,0)</td></tr><tr><td>最终的GARCH模型 @</td><td>0.0001**</td><td>0.000**</td></tr><tr><td>α</td><td>0.219**</td><td>0.116**</td></tr><tr><td>β</td><td>0.781**</td><td>0.872**</td></tr><tr><td></td><td>1</td><td>0.00003*</td></tr><tr><td>GARCH中虚拟变量的修正方案a</td><td>1</td><td>(6,0,10,0.9)</td></tr></table></body></html>

“四个参数 $( S _ { 1 } , S _ { 2 } , S _ { 3 } , S _ { 4 } )$ ）的含义： $S _ { 1 }$ 表示公告日之后不变影响持续的天数; $S _ { 2 }$ 表示影响消失的速度； $S _ { 3 }$ 表示公告日之前不变影响持续的天数； $S _ { 4 }$ 表示建立影响的速度。各参数的详细说明见本文2.2节

表中的空白表示在相应的回归方程中没有选择相应的阶数e“”表示不存在同时满足AIC减小，并在给定的显著性水平下显著的传统的或者经修正的虚拟变量，因此没有相应的最优修正方案\*和\*\*分别代表5%和1%的显著性水平

从影响方向上看，NAPI公告与NAPII公告均对碳价期望收益产生了显著的正向影响，这说明在NAP信息公开时，市场认为配额供给较紧，没有预见后来配额供给过量的情况。

从影响碳价期望收益的大小上看，与NAPI公告的影响（0.035）相比，NAPI公告的影响（0.011）明显减弱。这可能由两个原因导致：一方面，NAPI为NAPII的制定提供了宝贵的借鉴，使市场对NAPII中的条款内容有了较为准确的预期；另一方面，第二阶段（2008一2012年）的排放上限及各国的减排任务已在制定NAPII之前确定，使得市场对各国NAPII中的配额分配量有了

![](images/34a223405455aba23df53b265ec38c6b38632d5739df3013442aa886a1782f65.jpg)  
图3NAPI和NAPⅡ公告对碳价期望收益与波动的影响过程

(a）NAPI公告对碳价期望收益的影响过程；（b）NAPI公告对碳价波动的影响过程；（c）NAPII公告对碳价期望收益的影响过程；（dNAPⅡI公告对碳价波动的影响过程。其中，红色虚线代表公告发布日

较为准确的把握。

从图3可以看出，NAP公告的事前影响持续时间明显长于事后影响，这可能是由NAP制度的特点导致的。NAP的编制、提交、审核、修改与批准是一个长期且反复的过程，在被正式批准之前，市场可能已根据先前的信息对公告进行了预判，从而产生较长的事前影响。在公告发布之后，市场只需较短的时间便完成公告信息的吸收，表现为较短的事后影响。

# 4.2VEA的影响与讨论

表5给出了VEAI与VEAII对碳价期望收益和波动影响的实证结果，对应式（1）一（3）中的参数值。图4显示了VEAI和VEAⅡI在不同阶段的影响。

从表5和图4可以看出，VEAI对碳价期望收益产生了显著的负向影响，而VEAII对碳价期望收益产生了显著的正向影响。另外，两个阶段的VEA均未对碳价的波动产生显著影响。具体地，VEAI对碳价收益的影响开始于公告发布当天，一直持续到公告发布后的第3天，之后迅速消失。VEAII对碳价期望收益的影响开始于公告发布之前的第4天，持续到公告发布后的第3天，影响完全消失。

从影响方向上看，VEAI对碳价期望收益产生了显著的负向影响，VEAI对碳价期望收益产生了显著的正向影响。第一阶段每年配额供过于求的状态使得VEA的发布对碳价期望收益产生负向冲击；第二阶段前期配额供小于求，后期配额开始供过于求（表3）。这种配额供需力量的转变最终使得从平均意义上来说，VEAII对碳价期望收益产生了显著的正向影响。

从影响大小上看，与VEAI的影响（0.146）相比，VEAII对碳价期望收益的影响大小（0.012）明显减弱。第一阶段核证排放量数据为市场预期第二阶段的排放量提供了较为准确的参考，从而使得VEA的影响减弱。

从核证排放公告事件的影响模式来看，VEAI表现出事后影响。这说明公告事件的信息是在公告发布之后逐渐被碳价格吸收，表明排放信息没有提前泄漏。VEAII表现出对称性的事前与事后影响，这可能是由信息提前

表5核证排放量公告（VEA）对碳价期望收益与波动的影响过程的实证结果  

<html><body><table><tr><td rowspan="2"></td><td rowspan="2"></td><td colspan="2">VEA阶段</td></tr><tr><td>第阶段</td><td>第阶段</td></tr><tr><td colspan="2">均值方程中的滞后阶数</td><td>1,2</td><td>1,2</td></tr><tr><td rowspan="4">最终的均值方程</td><td>c</td><td>-0.018**</td><td>-0.001</td></tr><tr><td>a</td><td>-0.343**</td><td>0.175**</td></tr><tr><td>a</td><td>-0.196**</td><td>-0.129**</td></tr><tr><td>b</td><td>-0.146**</td><td>0.012**</td></tr><tr><td colspan="2">均值方程中虚拟变量的改进方案a</td><td>(3,0.3,0,0)</td><td>(3,0,4,0)</td></tr><tr><td rowspan="4">最终的GARCH模型</td><td>@</td><td>0.0001</td><td>0.000</td></tr><tr><td>a</td><td>0.198**</td><td>0.121**</td></tr><tr><td></td><td>0.801**</td><td>0.878**</td></tr><tr><td></td><td>1</td><td>1</td></tr><tr><td colspan="2">GARCH中虚拟变量的改变方案a</td><td>1</td><td>一</td></tr></table></body></html>

注释同表4

![](images/671c8431281d531c74d37f5726c0c5cfce89375b18908f5cd8b898f0877c9365.jpg)  
图4VEAI与VEAII对碳价期望收益与波动的影响过程

(a）VEAI对碳价期望收益的影响过程；（b）VEAI对碳价波动的影响过程；（c）VEAI对碳价期望收益的影响过程；（d）VEAII对碳价波动的影响过程。其中，红色虚线代表公告发布日

泄漏导致的。

碳市场中，NAP与VEA两大机制分别直接决定了配额的供给量与需求量。在设计碳市场时，设定适度的配额供给量既是难题也是关键。虽然配额供给过紧会加重企业的减排任务，对经济发展产生较大负面影响，但配额供给过松也会导致碳价持续低迷，抑制市场参与者对投资低碳技术的积极性。因此，市场设计者可考虑建立柔性的配额供给机制使碳价保持在合理区间。另外，欧盟碳市场的经验表明NAP公告与VEA有时会增加碳价收益的波动，提高碳资产的风险。市场设计者可考虑分批释放此类信息，以保证碳市场本身制度的设置不会对市场产生重大冲击。

# 4.3 Robustness 检验

除了使用碳期货价格数据之外，本文还使用来自欧洲能源交易所（European Energy Exchange）和纽约-泛欧证券交易集团Bluenext交易所的现货价格数据分析NAP公告或VEA对碳价的影响过程；而且，通过适当缩短或延长碳价格时间序列长度，以分析公告事件的影响。实证结果表现出高度一致性，证明了实证结果的稳健性。

# 5结论

本文采用双边修正虚拟变量的事件研究方法，对欧盟碳市场中NAP公告与VEA制度对碳价期望收益与波动的影响进行分析，以完整刻画事件的影响过程。研究结果表明，NAP公告与VEA公告均对碳价产生了显著影响，说明NAP公告揭示出的配额供给量信息和VEA公告揭示出的配额需求量信息促使市场参与者调整对碳价的预期，这两类公告的发布有促进价格发现的功能。NAPI公告只对碳价期望收益产生了显著的正向影响；NAPII公告对碳价期望收益产生了显著的正向影响，并显著增加了碳价波动；与NAPI公告相比，NAPⅡI公告对碳价期望收益的影响明显减弱，这可能是市场逐渐吸收了国家配额公告信息的结果。NAP公告的影响表现出较长的事前影响，这可能是由NAP反复而漫长的制定特点导致的。VEAI仅对碳价期望收益产生显著的事后负向影响，VEAII对碳价期望收益产生了显著的事前与事后正向影响；与VEAI相比，VEAII对碳价期望收益的影响大小明显减弱，这可能是由于第一阶段的排放量信息为第二阶段的市场预期提供了可靠参考。

为促进节能减排、应对气候变化，我国正积极规划全国统一的碳市场。作为碳市场的蓝本，欧盟碳市场的机制设计与实证经验对我国具有较强的借鉴意义。一方面，碳排放上限的设计是碳排放权交易机制设计的难点之一。欧盟碳市场第一阶段的经验表明如果排放上限（NAPI）设置过松，排放量信息的公布（VEAI）会对市场产生负向冲击，不利于保持企业投资低碳技术的积极性。建立柔性的排放上限机制以稳定碳价是一种应对方法。目前，欧盟碳市场为解决配额供给过剩的境况，从2014年开始实施了推迟拍卖部分配额的短期措施，并计划从2019年起建立市场稳定储备的长效机制。这两种做法对我国碳市场的设计有一定启示意义。另一方面，重大公告事件可能会增加碳价期望收益的波动，市场设计者应探索有效机制减小公告对市场的冲击，以维护市场的平稳运行。

# 参考文献

1Alberola E,ChevallierJ,Cheze B.Price drivers and structural breaks in European carbon prices 20o5-20o7.Energy Policy,2008, 36(2): 787-797.   
2Miclaus PG,Lupu R,Dumitrescu SA,et al. Testing the efficiency of the European carbon futures market using event-study methodology. International Journal of Energy and Environment, 2008,2(2):121-128.   
3Hitzemann S,Uhrig-homburg M,Ehrhart K M.The impact of the yearly emissions announcement on $\mathrm { C O } _ { 2 }$ prices: an event study. Information Management and Market Engineering,2010,2:77- 92.

4 Mansanet-bataller M, Pardo A.Impacts of regulatory announcements on $\mathrm { C O } _ { 2 }$ prices.The Journal of Energy Markets,2009, 2(2): 75-107.

5 Lepone A,Rahman R T, Yang JY. The impact of European Union Emissions Trading Scheme (EU ETS) National Allocation Plans (NAP) on carbon markets.Low Carbon Economy,2011,2(2): 71- 90.   
6Deeney P,Cummins M,Dowling M,et al.Influences from the European Parliament on EU emissions prices.Energy Policy, 2016,88: 561-572.   
7 Koch N, Grosjean G, Fuss S,et al. Politics maters: regulatory events as catalysts for price formation under cap-and-trade.Journal ofEnvironmental Economics and Management,2016,78:121- 139.   
8 Mansanet-bataller M, Tornero A,Mico E. $\mathrm { C O } _ { 2 }$ prices,energy and weather. The Energy Journal,2007,28(3): 73-92.   
9Rickels W, Gorlich D,Peterson S. Explaining European emission allowance price dynamics: evidence from phase II. German Economic Review,2015,16(2):181-202.   
10 Wilfried R,VickiD,Andreas K.The determinants of allowance prices in the European emissions trading scheme: can we expect an efficient allowance market 2oo8?Review of Environmental Economics and Policy,2007,1(1): 66-87.

11 陈晓红,王陟昀.碳排放权交易价格影响因素实证研究—以

欧盟排放交易体系(EUETS）为例．系统工程,2012,30(2): 53-60.   
12Creti A,JouvetPA,Mignon V.Carbon price drivers:Phase I versus Phase II equilibrium? Energy Economics,2012,34(1): 327- 334.   
13 Alberola E, Chevallier J. European carbon prices and banking restrictions: evidence from Phase I(2005-2007). The Energy Journal,2009,30(3): 51-80.   
14 Conrad C,Rittler D,Rotfub W. Modeling and explaining the dynamics of European Union Allowance prices at high-frequency. Energy Economics,2012,34(1): 316-326.   
15 刘纪显，苏艺龙.欧债危机对EUETS碳价的影响及其对我国 的启示.预测,2013,32(5):27-33.   
16 Schmidbauer H, Rosch A. OPEC news announcements: effects on oil price expectation and volatility. Energy Economics,2012, 34(5): 1656-1663.   
17 Jia JJ,Xu JH,Fan Y. The impact of verified emissions announcements on the European Union emissions trading scheme: a bilaterally modified dummy variable modelling analysis.Applied Energy,2016,173:567-577.   
18 Benz E, Truck S.Modeling the price dynamics of $\mathrm { C O } _ { 2 }$ emission allowances. Energy Economics,2009,31(1): 4-15.   
19 Bollerslev T. Generalized autoregressive conditional heteroscedasticity. Journal of Econometrics,1986,31(3): 307-327.

# Impact of Pivotal Announcement Event on Carbon Price in European Union Emission Trading Scheme

Jia Junjun1,²Xu Jinhua²Fan Ying³

(1School of Economics,Hefei University of Technology,Hefei 230601, China;

Institutes of Science and Development, Chinese Academy of Sciences,Beijing 10o190, Chin

3School of Economics and Management,Beihang University,Beijing loo191, China）

AbstractWiththeworseningof globalclimatechange,establishmentofcarbon tradingscheme hasbecomeanimportantoption for governments toaddresstheissueofclimatechange.Asnewlycreatedmarket,carbon marketisasilysubjectotheshocksfrominstitution modification,uleadjustment,andvital informationanoucement.Theresearch establishesaneventstudymethodthroughmodeling bilaterally modified dummyvariablesinAR-GARCHmodeltounveil the ex anteand ex post impact processandimpact pattrof the anouncementevent.Thesudytakes NationalAlocationPlans (NAPannouncementand VerfiedEmissonAnnouncement (VEA)eventin theEuropean Unionemisiontradingscheme(EUETS）asexamples.EmpiricalresultsshowthatbilaterallymodifeddummyVariablescan efficientlycapturetheexateandexostipactprocesofaouncementeventoexpctedcabonesdvolatiliteaoucent ofNAPIassignicatpositiveipactoarbnetusdasnognificantipactonarbonpriceolatityThaouncemtfA Ihas significantnegativeexostipactoncarbonretusandtheaouncementofEAIhassigificantpositiveexanteandexstipact oncarbonetus.Inaddition,theanouncementsofVEAIandVEAIhavenosignificantimpactoncarbonpricevolatityComparedwith theimpactofVEAaounceent,timpactofEAIaouceenthasreased,alyuetotfctatheerifideiofte first phase provides reliable data to calibrate expectations.

Keywordscarbontradingse,atioalallationlanouncementerifiedmissionouncement,blateralloidmy variable modeling,carbon expected returns and volatility

贾君君中国科学技术大学与中科院科技战略咨询院联合培养博士研究生。研究方向为碳排放权交易机制、居民能源消费等。E-mail: jiajunjunceep@163.com

JiaJunjunPh.D.candidateco-cultivatedbyUniversityofScienceandTechnologyofChinaandInstitutesofScienceandDevelopent Chinese Academyof Sciences (CAS).His research area includes carbon trading scheme and residential energy consumption. E-mail: jiajunjunceep@163.com

许金华男，中科院科技战略咨询院副研究员。研究方向为能源经济学、二氧化碳排放机制。主持国家自然基金委青年基金、面上基金、北京市自然基金面上项目等多项课题，发表中、英文论文30余篇。  
E-mail: xujinhual11@163.com, xjh@casipm.ac.cn

XuJinhuaMale,AsociateProfesorinIstutesofSencendevelopent,CinseAcademyofSienes(AS).Hiseahfels areenergyecoomics,low-arbontech-economicmodeling.HeistheleaderofmanyprojectssponsoredbytheNationalNaturalSience Foundation of China,and has already published more than 3O academic papers.E-mail: xujinhual11 $@$ 163.com, xjh@casipm.ac.cn