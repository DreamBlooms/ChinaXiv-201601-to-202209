# 基于蚁群相似权算法的网络团购信用评价模型研究

张亚明 李娜赵培卿(燕山大学经济管理学院秦皇岛 066004)

摘要：【目的】帮助网络团购消费者快速找到优质商家，商家可以有效地提高自身信用水平。【方法】利用相似权测度法对指标体系分配权重，得出的综合指标变量作为蚁群算法参数，建立基于蚁群相似权的信用评价模型。【结果】实证研究表明，该模型能够快速有效地求出节约时间成本和货币成本的最短路径，找出优质商家。【局限】未考虑退款和刷单等特殊交易对网络团购信用评价的影响；对蚁群算法的其他参数未进行具体研究，直接采用前人研究结论。【结论】有助于商家提高信用、提升团体满意度，为进一步研究网络团购问题提供参考。

关键词：网络团购 信用评价相似权蚁群算法分类号：F713.36 G35

# 1引言

网络团购作为电子商务的衍生物发展十分迅猛，前景可观。然而，行业规范与自律的缺乏以及低准入门槛造成团购网站良莠不齐，加之相应的监管机制没有跟进使得诸如团购陷阱等损害消费者权益的事件屡屡发生，引起消费者的不满和投诉，一个个团购网站相继破产、被收购，网络团购的发展问题引人深思。据中国电子商务研究中心2015年3月13日发布的《2014年度中国电子商务用户体验与投诉监测报告》[1]显示，2014年网络团购类投诉占全部电子商务投诉$2 4 . 2 4 \%$ ，仅次于网络购物 $( 4 9 . 0 7 \% )$ 。报告通过对美团网、窝窝团、拉手网、大众点评团、携程、去哪儿、同程网、驴妈妈等团购电商进行全年监测，结果显示：质量问题、虚假团购和退款等问题是"2014年度中国网络团购十大热点投诉问题”，也是网络团购信用问题的具体体现。消费者为规避消费风险，必然要花费大量的时间和精力寻找值得信赖的商家，诚信问题亟待解决。因此，建立健全网络团购交易市场信用评价体系乃当务之急。

# 2国内外研究述评

# 2.1信用评价方法和模型

国内外关于信用评价方法和模型已做了大量研究工作。最早Steve2研究并提出信用评价的单变量模型,即运用单一变量用个别财务比率预测财务危机。Altman 等[3提出的二次判别分析模型(Zeta 模型)指出某些财务比率在不同企业存在显著不同，为评价对象提供预警。Ohlson[4]利用Logit分析建立预测模型，得出4项财务资料对评估破产概率有明显影响。以上模型大部分采用先选定财务因素，再采集样本进行实证推导的基本研究方法。目前，最常用的信用综合评价方法有综合指数评价法、组合指标评价法、多元统计评价法、模糊综合评判法以及近几年出现的DEA等方法[5]。如Yuan 等给出电商风险的层次结构，构建基于信任的电商信用风险管理模式。Adnanl运用神经网络进行信用评价，通过采用不同的学习机制对12组神经网络训练得出：情绪处理神经网络模型比传统模型在决策速度和准确性上占有明显优势。Ioannis[8使用DEA评估企业信用风险以支持贷出决策，并证实企业利润为导向的政策是其在行业成功的驱动因素。

从21世纪初开始，国内越来越多的学者开始关注信用评价问题。王春峰等[9]和张玉洁等[10]将蚁群算法分别应用于商业银行信用风险评估和电信客户初始评分问题。杨韵[1提出动态信用评价模型，该模型充分考虑C2C交易环节中的信任要素及其权重，并且引入信用值随时间推移的动态变化，对网络交易环境中信用评价的构建具有积极意义。为了解决由数据"突变"引起的评价结果失真问题，张洪祥等[12]提出一种基于多维时间序列的灰色模糊信用评价模型，先后运用灰色关联分析方法和模糊聚类法算出受评样本的信用等级；张发明[1]提出一种融合 SOM与K-means 算法的动态信用评价方法对评价对象进行聚类分析，并以实例验证算法的有效性。周国强等[14]对传统信用评价方法难以有效处理重大工程语言评价相关信息问题进行了深入研究，提出一种基于改进云模型的信用评价方法，引入时间衰减因子和信用云相似度的概念，使得评价结果更加可信。郭伟等[15]针对云制造模式下中小企业制造服务交易模式所表现的多主题、动态特点,引人粗糙集和层次分析混合评价方法，建立动/静态属性结构相结合的信用评价指标体系，实现对企业信用状况的全面实时监控。

# 2.2 网络团购及其所产生的信用问题

国内外专家学者对网络团购及其所存在的信用问题进行了广泛研究和探讨。早在1972年，就开始有学者在理论方面进行研究。Webster等[16]从政治学角度探讨，将团购视为一种联盟并给予相关定义。Lee[17提出一个创新型移动电子商务团购系统，由可信的第三方记录和管理密钥的一部分，以保护交易的安全和隐私;采用Bloom过滤器和XOR操作提高运算效率，以便应用于移动设备。Marcelo[18]研究如何降低网上购物时的感知风险，即无形性，产品知识，品牌熟悉度，以及隐私和安全问题之间如何相互作用并对感知风险的影响程度。

国内专家学者对团购信用问题也进行了研究。如罗晓娜等[19从博弈论的视角出发，研究团购供应链成员之间的信任协调机制，通过分析信任影响因素和运用KMRW声誉模型，设计第三方信用监管机构相应的约束机制和激励机制，以约束交易双方的机会主义行为，降低团购风险。管晓永等[20以传统信用理论为指导，基于公众可获得信息，从决定信用行为的两大方面因素—信用意识和信用能力，展开对团购网站信用行为的基本特性研究，为网络团购及其他电子商务信用管理创新提供理论基础。

综上所述，国内外针对信用评价模型和方法的研究大多集中于财务影响因素，而忽略了消费者成本影响因素，评述和表层应用较多，且国内外均较少涉及如何在网络交易中节约消费者成本的研究。同时，在梳理网络交易信用评价的文献过程中，发现涉及信用评价问题的蚁群算法研究较少，优化网络团购信用评价体系更为罕见。因此，本文以节约消费者成本，提升满意度为目标，构建网络团购信用评价体系模型，更好地维护消费者利益。

# 3基于蚁群相似权的网络团购信用评价模型构建

蚁群算法根据蚂蚁觅食时通过散发信息素进行正反馈寻找窝食间最短路径的特点，模仿蚂蚁的这种智能行为，从而实现系统寻优。与传统编程模式相比，蚁群算法是一种自我学习的过程，具有独特的优势。

模型的经济学意义在于：在网络团购中，买方评分和系统口碑为模型中影响路径寻优的信息素，在其他买方对商家信用评价的启发下，买方如何在最短的时间内为团体找到最合适的商家，从而使消费者节约搜索时间成本，获得最高收益，达到商品质量和无形服务的双重满意；从另一角度，模型最优解也能提示商家要关注哪些方面以提高自己的信用。

# 3.1构建信用评价综合指标体系

# (1）构建指标体系

科学选择信用评价对象是构建信用指标的关键环节并且在构建时应该遵循科学、客观、集约、实用、可拓展性原则。从消费者最关注的指标角度—网络团购过程中的众多利益相关者视角，参照相关电子商务国家标准[21]及张成等[22]提出的基于关系式交易的网络团购模式及其信用评价体系分析结果，提取核心评价指标，测评算法的可行性和稳定性，接着对团购商家的信用作出评价。具体内容如表1所示：

<html><body><table><tr><td></td><td>表1信用评价指标体系</td></tr><tr><td>评价指标</td><td>选项</td></tr><tr><td>t1：商品介绍</td><td>A非常详细，图文并茂 B比较详细，文字或图片不充分 C不太详细，介绍较少，难以抉择 D不详细，无介绍</td></tr><tr><td>t2：交易前与卖家的 沟通 (主要指咨询)</td><td>A非常顺畅 B较顺畅，回答较满意 C回答不能解决问题 D无法联系</td></tr><tr><td>t3：服务态度 (交易过程)</td><td>A态度很好，处理迅速 B态度较好，能够保证交易顺利进行 C态度较差，拖延了交易进程 D态度很差，交易失败</td></tr><tr><td>t4:性价比(商品 性能和价格比)</td><td>A性能很好，价格合理 B性能一般，价格合理 C性能很好，价格一般 D性能一般，价格一般</td></tr><tr><td>t5：发货速度</td><td>A满意，发货快 B一般，比承诺时间稍晚, 延期不超过3天 C不满意，超期3天以上 D很不满意，没发货</td></tr><tr><td>t6:货物包裹状况</td><td>A包装仔细，无损坏 B 比较仔细，稍有磨损 C一般，有磕碰 D包装粗糙，商品受损</td></tr><tr><td>t7：商品品质(货物 与描述的相符度)</td><td>A完全相符 B稍有偏差 C 描述稍夸大 D品质天壤之别</td></tr></table></body></html>

# (2）信用评价指标相关性分析

在对商家信用进行初评时，要消除指标体系信息冗余，通过对表1中的指标体系进行打分，将得到的结果数据运用SPSS19.0软件进行相关性分析，以优化指标体系，相关性结果如表2所示：

表2买方评价指标的相关性分析  

<html><body><table><tr><td></td><td>t1介绍</td><td>t2沟通</td><td></td><td>t3服务 t4性价比 t5速度t6包装t7品质</td><td></td><td></td><td></td></tr><tr><td>t1</td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>t2</td><td>-0.1770</td><td>1</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>t3</td><td>0.0091</td><td>0.5903</td><td>1</td><td></td><td></td><td></td><td></td></tr><tr><td>t4</td><td>-0.0784</td><td></td><td>0.4652-0.2028</td><td>1</td><td></td><td></td><td></td></tr><tr><td>t5</td><td>-0.3485</td><td></td><td>0.5644-0.0020</td><td>0.5398</td><td>1</td><td></td><td></td></tr><tr><td>t6</td><td>0.7732</td><td></td><td>0.2575 -0.0228</td><td>-0.1592</td><td>0.0028</td><td>1</td><td></td></tr><tr><td>t7</td><td>0.3412</td><td>0.3478 -0.0003</td><td></td><td>0.9436</td><td>0.0056</td><td>0.3875</td><td>1</td></tr></table></body></html>

按照表2数据的绝对值将指标按相关性进行分类。指标t3(服务)和t7(品质)近似接近于零相关(相关系数为-0.0003)，说明这两项指标评分设置合理，t3和t7作为两类，通过比较与这两个指标的相关性大小对其余指标进行分类。指标 t2 和 t3 相关性较大中 $0 . 5 9 0 3 { > } 0 . 3 4 7 8$ ，t1、t4、t6和t7相关性较大 $( 0 . 3 4 1 2 >$ 0.0091, $0 . 9 4 3 6 { > } 0 . 2 0 2 8$ ， $0 . 3 8 7 5 { > } 0 . 0 2 2 8$ ,t5与t3、t7的相关性均不高(0.0020，0.0056)，因此将其单独作为一类。综上所述，可以将系统口碑值指标(历史口碑值和最近三个月口碑值)和买方评分系统评价指标(服务、品质、发货速度)作为团购综合信用评价简化后的指标体系。

(3）相似数定义相似权，确定指标权重

一般情况下，当评价者不能对指标重要性很好地做出评判时就需要寻找一种客观评价方法。而相似数定义相似权不失为一种较为客观科学的评价方法，其过程如下:

$\textcircled{1}$ 选取 $\mathfrak { n }$ 个样本。样本需要有可以直观判断的评价等级，并且各级别样本商家的选取不少于两个。$\textcircled{2}$ 设 $\mathbf { w _ { j } }$ 表示第j个评价指标 $\mathrm { I _ { j } }$ 相对于其他指标的重要程度，取 $\mathbf { w } _ { \mathrm { j } } = \frac { 1 } { \mathrm { m } } ( \mathrm { j } = 1 , 2 , \cdots , \mathrm { m } ) \mathrm { ~ , ~ }$

$\textcircled{3}$ 计算综合测度评价矩阵。

$\textcircled{4}$ 由单指标测度评价矩阵及综合测度评价矩阵求出相似系数 $\mathbf { r _ { j } }$ ，再求出相似权 $\mathbf { w _ { j } }$ 。

$\textcircled{5}$ 以相似权向量 $\mathbf { w } = ( \mathbf { w } _ { 1 } , \mathbf { w } _ { 2 } , \cdots , \mathbf { w } _ { \mathrm { m } } )$ 作为指标权重向量。

# 3.2蚁群相似权算法信用评价模型

由于蚁群算法是一种自组织的算法，具有正反馈性及较强的鲁棒性，因此本文采用蚁群算法完成信用评价模型的构建。结合信用评价综合指标体系的建立过程，即构建指标后利用基于相似数定义相似权的指标权重测度法确定权重，利用蚁群算法，将相似权法得到的综合指标变量值作为城市点坐标，寻找最优商家。具体步骤如下：

(1）构建综合指标评价体系。(2）确定指标权重，并进行数据测试，将综合指标变量作为蚁群算法城市点坐标。(3）配置蚁群算法参数，并进行迭代测试。(4)运行该算法。算法中的t时刻蚂蚁k有i到j的状态转移概率 $\mathsf { p } _ { \mathrm { i j } } ^ { \mathrm { k } } ( \mathrm { t } )$ 为：

$$
\mathrm { p _ { i j } ^ { k } ( t ) = \left\{ \begin{array} { l l } { \displaystyle \frac { \tau _ { i j } ^ { \alpha } ( t ) \eta _ { i j } ^ { \beta } ( t ) } { \sum _ { s \in a l l o w e d _ { k } } \tau _ { i s } ^ { \alpha } ( t ) \eta _ { i s } ^ { \beta } ( t ) } } & { j \in a l l o w e d _ { k } } \\ { 0 } & { o t h e r w i s e } \end{array} \right. }
$$

其中，allowed $\mathbf { \nabla } \cdot \mathbf { k }$ 为禁忌表集合； $\tau _ { \mathrm { i j } } ( \mathrm { t } )$ 为t时刻i到j路径上的信息素浓度； $\eta _ { \mathrm { i j } } ( \mathrm { t } )$ 为 $\mathrm { ~  ~ t ~ }$ 时刻i到 $\mathrm { ~ j ~ }$ 的启发信息； $\eta _ { \mathrm { i j } } = 1 / \mathrm { d } _ { \mathrm { i j } }$ ， ${ \bf d } _ { \mathrm { i j } }$ 代表相邻两城市间的距离； $\mathbf { \alpha } _ { \mathrm { ~ \normalfont ~  ~ } } \mathrm { ~ a ~ }$ 和 $\beta$ （20分别代表信息启发式因子和期望启发式因子，其大小分别反映蚁群在路径选择中随机因素和确定性因素的强弱。

(5）更新信息素。每循环一次，信息素量根据公式(2)和公式(3)进行一次调整：

$$
\tau _ { \mathrm { i j } } ( \mathrm { t } + 1 ) = \mathsf { \rho } \cdot \tau _ { \mathrm { i j } } ( \mathrm { t } ) + \Delta \tau _ { \mathrm { i j } } ( \mathrm { t } , \mathrm { t } + 1 )
$$

$$
{ \Delta \tau _ { \mathrm { i j } } ( \mathrm { t , t + 1 } ) = \sum _ { \mathrm { k = 1 } } ^ { \mathrm { m } } \Delta \tau _ { \mathrm { i j } } ^ { \mathrm { k } } ( \mathrm { t , t + 1 } ) }
$$

其中， $\Delta \mathfrak { \tau } _ { \mathrm { i j } } ^ { \mathrm { k } } ( \mathfrak { t } , \mathfrak { t } + 1 )$ 表示蚂蚁 $\mathbf { k }$ 在 $\displaystyle ( \mathfrak { t } , \ \mathfrak { t } { + } 1 )$ 时刻存留在路径 $( \mathrm { i } , \mathrm { j } )$ 上的信息素量，它的值与蚂蚁的寻优程度相关，即路径越短，平分到每条路径上的信息素就越多； $\Delta \mathfrak { \tau } _ { \mathrm { i j } } ( \mathfrak { t } , \mathfrak { t } + 1 )$ 表示信息素增量；(1-p)为衰减系数,p( $\cdot \boldsymbol { \rho } < 1 \dot$ )是信息素残留系数。

(6)若算法收敛或达到最大循环次数，则运行结束。蚁群算法模型的构建如图1所示：

输入 基于ACO算法的网络团购信用评价系统  
信用评价指标值 指标权重测度 样本数据加权处理 算法的参数选择 样本数据的调用 。。 数据转换处理 系统输出 最优解评价算法 Y结束初始化 满足？t=t+1

# 4网络团购评价模型实证分析

# 4.1蚁群相似权算法应用

(1）样本数据获取

综合考虑商家的行业和周期的可比性以及样本的科学要求，通过网络调查方法获取同为装修行业的21位商家的实测数据作为样本，如表3所示。发货速度指标为新增指标，其数据来源于原指标体系中的性价比指标。

表3样本数据  

<html><body><table><tr><td>项目</td><td colspan="3">指标项评分项I</td><td colspan="2">口碑值C</td></tr><tr><td>商家</td><td>I服务</td><td>I品质</td><td>I发货速度</td><td>C1最近三个月口碑值</td><td>C历史口碑值</td></tr><tr><td>(1) 33611449</td><td>82</td><td>96</td><td>92</td><td>214</td><td>16 780</td></tr><tr><td>(2) 33414690</td><td>78</td><td>90</td><td>96</td><td>326</td><td>19 562</td></tr><tr><td>(3)33165371</td><td>80</td><td>88</td><td>88</td><td>420</td><td>22 310</td></tr><tr><td>(4)33363272</td><td>96</td><td>96</td><td>98</td><td>378</td><td>17 890</td></tr><tr><td>(5) 32091340</td><td>88</td><td>88</td><td>88</td><td>178</td><td>16 562</td></tr><tr><td>(6) 34355293</td><td>76</td><td>94</td><td>90</td><td>325</td><td>15 346</td></tr><tr><td>(7)33165389</td><td>96</td><td>89</td><td>92</td><td>430</td><td>15 342</td></tr><tr><td>(8)34802790</td><td>88</td><td>87</td><td>90</td><td>231</td><td>13 230</td></tr><tr><td>(9)34091268</td><td>82</td><td>88</td><td>93</td><td>570</td><td>22 345</td></tr><tr><td>(10) 34355245</td><td>87</td><td>93</td><td>95</td><td>198</td><td></td></tr><tr><td>(11) 33611449</td><td>98</td><td>92</td><td>96</td><td>214</td><td>17 373</td></tr><tr><td>(12) 34803642</td><td>90</td><td>90</td><td>94</td><td>256</td><td>20 131</td></tr><tr><td>(13) 33165371</td><td>96</td><td>96</td><td>89</td><td>320</td><td>13 326</td></tr><tr><td>(14)33363272</td><td>93</td><td>98</td><td>95</td><td>187</td><td>12 650</td></tr><tr><td>(15) 34094345</td><td>90</td><td>92</td><td>92</td><td>156</td><td>17 856</td></tr><tr><td>(16) 34355233</td><td>90</td><td>90</td><td>90</td><td>126</td><td>27 808</td></tr><tr><td>(17)33611449</td><td>76</td><td>95</td><td>96</td><td>334</td><td>10 230</td></tr><tr><td>(18) 33414690</td><td>82</td><td>96</td><td>98</td><td>230</td><td>19 802</td></tr><tr><td>(19) 34355233</td><td>78</td><td>90</td><td>96</td><td>228</td><td>28 901</td></tr><tr><td>(20)33363272</td><td>94</td><td>96</td><td>96</td><td>658</td><td>10 890</td></tr><tr><td>(21) 34094345</td><td>82</td><td>96</td><td>92</td><td>236</td><td>18 266</td></tr></table></body></html>

以上数据中，第(10)组数据没有历史口碑值，很可能是新开业商家，第(20)组数据历史口碑值较低而最近三个月口碑值远远高于其他组，存在恶意炒作的嫌疑，因此，需要踢除这两组数据以避免时间和恶意炒作的影响，即总共只有19组数据可用。

(2)计算指标权重

以齐家网①同行业商家为例，系统评价分为两部分：买家评分(品质、服务、发货速度)和系统自动评分(最近三个月和历史口碑值)，并且它们对商家信用等级均有影响。因此，本文将这两部分进行综合，依据相似数定义相似权的方法，按照表4的评价标准，分别求出两系统中的各评价指标权重，得到买家综合评分和系统综合评分，并将此作为蚁群算法中城市点坐标值。商家数据如表5所示。

表5齐家网5位装修行业商家评测数据  

<html><body><table><tr><td>评价等级Ck</td><td>极差</td><td>差</td><td>可</td><td>良</td><td>优</td></tr><tr><td>评价指标Ij</td><td>C1</td><td>C2</td><td>C3</td><td>C4</td><td>C5</td></tr><tr><td>Ij</td><td><60</td><td>61~75</td><td>76~85</td><td>86~95</td><td>96~100</td></tr></table></body></html>

表4信用评价标准[21]  

<html><body><table><tr><td>评价指标Ij</td><td>服务I1</td><td>品质I2</td><td>发货 速度I</td></tr><tr><td>商家xi X1</td><td>70</td><td>98</td><td>96</td></tr><tr><td>X2</td><td>68</td><td>94</td><td>84</td></tr><tr><td>X3</td><td>71</td><td>97</td><td>76</td></tr><tr><td>X4</td><td>91</td><td>78</td><td>79</td></tr><tr><td>X5</td><td>76</td><td>81</td><td>82</td></tr></table></body></html>

$$
\mu _ { \mathrm { i k } } = \frac { 1 } { 3 } \sum _ { \mathrm { j = 1 } } ^ { 3 } \mu _ { \mathrm { i j k } } \quad \mathrm { i } = 1 , 2 , \cdots , 5 ; \mathrm { k } = 1 , 2 , \cdots , 5
$$

根据公式(4)求得综合测度评价矩阵如下：

$$
\begin{array} { r l } { \Gamma _ { 1 } } & { \mathrm { C } _ { 2 } } & { \mathrm { C } _ { 3 } } & { \mathrm { C } _ { 4 } } & { \mathrm { C } _ { 5 } } \\ { \left[ \begin{array} { l l l l l } { \frac { 1 } { 9 } } & { \frac { 2 } { 9 } } & { 0 } & { \frac { 2 } { 5 } } & { \frac { 4 } { 1 5 } } \\ { \frac { 8 } { 4 5 } } & { \frac { 1 7 } { 9 0 } } & { \frac { 1 } { 3 } } & { \frac { 3 } { 1 0 } } & { 0 } \\ { \frac { 4 } { 4 5 } } & { \frac { 4 9 } { 9 0 } } & { \frac { 1 } { 3 } } & { \frac { 3 } { 1 0 } } & { 0 } \\ { 0 } & { \frac { 1 3 } { 3 0 } } & { \frac { 1 } { 3 0 } } & { \frac { 1 } { 5 } } & { 0 } \\ { \frac { 2 } { 1 5 } } & { \frac { 3 } { 5 } } & { \frac { 4 } { 1 5 } } & { 0 } & { 0 } \end{array} \right] } & { \mathrm { x } _ { 1 } } \\ { \mu = ( \mu _ { \mathrm { m } } ) _ { 5 } } & { \mathrm { ( ) } } \end{array}
$$

再由公式(5)计算可得 $\mathbf { r } _ { 1 }$ ：

$$
\mathrm { { r } _ { j } = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } ( \mu _ { i j l } , \mu _ { i j 2 } , \cdots , \mu _ { i j p } ) \times ( \mu _ { i l } , \mu _ { i 2 } , \cdots , \mu _ { i p } ) ^ { T } = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \sum _ { k = 1 } ^ { p } \mu _ { i j k } \times \mu _ { i k } }
$$

可得:

$$
\mathrm { \Delta } \mathrm { r } _ { \mathrm { { l } } } = \frac { 1 } { \mathrm { n } } \sum _ { \mathrm { i = 1 } } ^ { 5 } ( \mu _ { \mathrm { i } 1 1 } , \mu _ { \mathrm { i } 1 2 } , \mu _ { \mathrm { i } 1 3 } , \mu _ { \mathrm { i } 1 4 } , \mu _ { \mathrm { i } 1 5 } ) \left[ \mu _ { \mathrm { i } 3 } \atop \mu _ { \mathrm { i } 4 } \right] = 0 . 2 0 4 , \mathrm { n } = 5
$$

同理可得 ${ \bf r } _ { 2 } , { \bf r } _ { 3 }$ ，即： $( \mathrm { r } _ { 1 } , \mathrm { r } _ { 2 } , \mathrm { r } _ { 3 } ) = ( 0 . 2 0 4 , 0 . 3 2 1 , 0 . 3 9 8 )$ （204再由wj=rj/ $\mathbf { w } _ { \mathrm { j } } = \mathbf { r } _ { \mathrm { j } } { \Bigg / } \sum _ { \mathrm { j } = 1 } ^ { \mathrm { m } } \mathbf { r } _ { \mathrm { j } }$ ，可得： $\begin{array} { r } { ( \mathbf { w } _ { 1 } , \mathbf { w } _ { 2 } , \mathbf { w } _ { 3 } ) = ( 0 . 2 2 1 , } \end{array}$ 0.348,0.431)，分别代表服务、品质和发货速度的权重。同理, $( \mathrm { w } _ { 1 } ^ { \cdot } , \mathrm { w } _ { 2 } ^ { \cdot } ) = ( 0 . 4 3 3 , 0 . 5 6 7 )$ ，分别代表最近三个月和历史口碑值的权重。

此指标权重表明，买方除了会看重商家以往的信用程度外，还会注重近期上架的新品及其评价，因此对实测数据与指标权值进行加权处理，

# 4.2 运行结果及分析

以Java作为编程环境，由于在算法准备阶段已经对信用评价指标做了标准化和量化处理，因此将数据直接输入程序，对19个待评点进行评价，程序输出及评价结果如表6所示：

表6输出结果  

<html><body><table><tr><td>商家</td><td>最优解</td><td>得到最优解的迭代次数</td></tr><tr><td>(1)33611449</td><td>32 036</td><td>1</td></tr><tr><td>(2) 33414690</td><td>32 036</td><td>1</td></tr><tr><td>(3)33165371</td><td>32 916</td><td>0</td></tr><tr><td>(4)33363272</td><td>32 916</td><td>2</td></tr><tr><td>(5)32091340</td><td>32 036</td><td>2</td></tr><tr><td>(6)34355293</td><td>38848</td><td>2</td></tr><tr><td>(7)33165389</td><td>32 036</td><td>10</td></tr><tr><td>(8) 34802790</td><td>32 036</td><td>2</td></tr><tr><td>(9)34091268</td><td>38 948</td><td>11</td></tr><tr><td>(11)33611449</td><td>32 036</td><td>2</td></tr><tr><td>(12) 34803642</td><td>33002</td><td>4</td></tr><tr><td>(13) 33165371</td><td>34510</td><td>2</td></tr><tr><td>(14)33363272</td><td>35282</td><td>6</td></tr><tr><td>(15) 34094345</td><td>36208</td><td>2</td></tr><tr><td>(16) 34355233</td><td>32 222</td><td>18</td></tr><tr><td>(17) 33611449</td><td>38804</td><td>3</td></tr><tr><td>(18) 33414690</td><td>32 036</td><td>2</td></tr><tr><td>(19) 34355233</td><td>33398</td><td>10</td></tr><tr><td>(21)34094345</td><td>32 842</td><td>9</td></tr></table></body></html>

算法程序的演示结果图和收敛图如图2和图3所示：

![](images/1361e6db19737c523844057efba6050dbe8c147407844652c2743625970cc04c.jpg)  
图2蚁群算法程序演示结果图

![](images/1bfc482a1bbf4f7627cc13ce78336576fddaf401f6bc14e28a73933f8152cc98.jpg)  
图3蚁群算法结果收敛图

演示结果分析：通过与运行结果图3进行对比分析，可看出结果无限地收敛于32036，也就是说问题的最优解(最短路径)为32036。对比评价结果得到，达到最优解的有7个，其中商家(1)和商家(2)的迭代次数最少，说明寻找到他们的成本最低，即这两个商家的信用度最高。

为了保证结果的可比性，设计参数与本文相同的基本蚁群算法对比实验，分别运行50次，计算平均搜索次数、平均运行时间、与50次中的最优解相差小于50(由于结果值较大)的最优解出现概率(结果稳定性)。实验结果如表7所示，可知蚁群相似权模型搜索次数远小于蚁群算法模型，其收敛速度快、运算效率高，且稳定性较高，因此本文模型有效、可行且具有一定的优越性。

表7蚁群和蚁群相似权算法比较  

<html><body><table><tr><td>算法</td><td>搜索次数</td><td>运行时间/s</td><td>稳定性</td></tr><tr><td>蚁群算法</td><td>103</td><td>70</td><td>96.54%</td></tr><tr><td>蚁群相似权算法</td><td>12</td><td>25</td><td>97.18%</td></tr></table></body></html>

综上所述，算法的信息素代表团购的系统口碑和买方评分，算法最优解表示消费者在已知商家信用评分后，寻找到最优商家的最短时间及最低成本，以达到消费者对品质和服务的要求，提升团体满意度；从另一角度看，这一结果也能提示商家在提高商品质量的同时，更要注重无形服务的改善，才能有效提高自身信用。

# 5结语

科学合理的信用评价模型对规范网络团购交易行为具有至关重要的影响。本文引入相似权指标权重测度法，首次构建了蚁群相似权的网络团购信用评价模型，通过实例验证其有效性。在对"齐家网"某行业21位商家的实测数据进行相关性分析后，得出信用评价指标间的关联程度图。同时，对齐家团购网进行算法仿真得出的评价结果表明，收敛速度快的商家即为综合信用度较高的商家，反之则为信用度低的商家，收敛速度的快慢能够为网络团购交易中的消费者提供很好的购物借鉴，从而为消费者节约时间和货币成本，有效增加顾客感知价值，这对商家在激烈的市场竞争中赢得战略优势也具有重要的现实意义。

# 参考文献：

[1] 中国电子商务研究中心.2014年度中国电子商务用户体验 与投诉检测报告[R/OL].[2015-03-13].http://www.100ec. cn/detail--6237267.html.(China E-Business Research Center. The 2014 Report of China E-Business Market Data Monitoring [R/OL].[2015-03-13]. http://www.100ec.cn/ detail--6237267.html.)   
[2] Steve W.Retailer Credit Cards:A Competitive Threat [J]. International Journal of Bank Marketing,1990,8(4):3-9.   
[3] Altman E I, Saunders A.Credit Risk Measurement: Developments over the Last 20 Years [J]. Journal of Banking & Finance,1997,21(11-12):1721-1742.   
[4] OhlsonJA.FinancialRatios and the Probabilistic Prediction of Bankruptcy [J]. Journal of Accounting Research,1997, 18(1): 109-131.   
[5] 李梅，马国建．中小企业信用评价指标体系的构建[J].统 计与决策,2005(12):63-64.(Li Mei,Ma Guojian.Construction of the Credit Evaluation Index System for Minor Enterprise [J].Statistics & Decision,2005(12):63-64.)   
[6] YuanD,Lu T,Yang X,et al.A Theory Analysis and Model Research on E-Commerce Credit Risk Management[C].In: Proceedings of the 2O1o International Conferenceon E-Business and E-Government, Guangzhou,China.2010.   
[7]Adnan K.Credit Risk Evaluation Using Neural Networks: Emotional Versus Conventional[J]. Applied Soft Computing, 2011, 11(8): 5477-5484.   
[8]Ioannis E T.Firm Credit Risk Evaluation: A Series Two-stage DEA Modeling Framework [J]． Annalsof Operations Research,2014,233(1): 483-500.   
[9]王春峰，赵欣，韩冬．基于改进蚁群算法的商业银行信用 风险评估方法[J]．天津大学学报：社会科学版，2005，7(2): 81-85.(Wang Chunfeng,Zhao Xin,Han Dong.A Model on Modified Ants Algorithm for Credit Risk Assessment in Commercial Banks [J]. Journal of Tianjin University: Social Sciences,2005,7(2): 81-85.)   
[10]张玉洁，孟祥武．利用蚁群算法求解电信客户初始信用评 分问题[J]．北京邮电大学学报，2010，33(1):124-128. (Zhang Yujie, Meng Xiangwu. Initial Credit Scoring for Telecom Customers Using Ant Colony Algorithm [J]. Journal of Beijing University of Posts and Telecommunications, 2010,33(1): 124-128.)   
[11]杨韵.C2C交易中的动态信用评价模型[J]．情报科学,2010, 28(4):563-566.(Yang Yun.A Dynamic Trust Evaluation Model on C2C Marketplaces [J]. Information Science,2010, 28(4): 563-566.)   
[12] 张洪祥，毛志忠．基于多维时间序列的灰色模糊信用评价 研究[J]．管理科学学报，2011，14(1):28-37．(Zhang Hongxiang， Mao Zhizhong. Research of Multidimensional Time Series Credit Evaluation Based on Gray-fuzz Analysis Model [J]. Journal of Management Sciences in China,2011, 14(1): 28-37.)   
[13] 张发明．一种融合SOM与K-means算法的动态信用评价方 法及应用[J].运筹与管理，2014，23(6):186-192.(Zhang Faming.Research on a Dynamic Credit Evaluation Method Integrating SOM and K-means Clustering Algorithm [J]. Operations Research and Management Science,2014, 23(6): 186-192.)   
[14]周国强，王雪青，刘锐．一种基于改进云模型的信用评价 方法[J]．系统工程，2013,31(4):60-66.(Zhou Guoqiang, Wang Xueqing,Liu Rui.A Credit Evaluation Method Based on the Modified Cloud Model [J]. Systems Engineering, 2013,31(4): 60-66.)   
[15] 郭伟,仝克宁，邵宏宇，等．基于RS与AHP的中小企业云 制造模式下多服务主体信用评价体系构建[J].计算机集成 制造系统,2013,19(9):2340-2347.(Guo Wei,Tong Kening, Shao Hongyu,et al. Small and Medium-sized Enterprises Multi-service Agent Credit Rating System Construction Under Cloud Manufacturing Mode Based on RS and AHP [J]. Computer Integrated Manufacturing Systems，2013，19(9): 2340-2347.)   
[16] Webster F E,Wind Y.A General Model for Understanding Organizational Buying Behavior[J]. Journal of Marketing, 1972,36(2): 12-19.   
[17] Lee J S.An Innovative Electronic Group-buying System for Mobile Commerce [J].Electronic Commerce Research and Applications,2013,12(1):1-13.   
[18] Marcelo V N. How to Reduce Perceived Risk When Buying Online: The Interactions Between Intangibility，Product Knowledge，BrandFamiliarity，PrivacyandSecurity Concerns [J]. Journal of Retailing and Consumer Services, 2014,21(4): 619-629.   
[19]罗晓娜，史彦虎，朱先奇．基于博弈的网络团购供应链信 任协调机制研究[J]．数学的实践与认识，2014，44(22): 47-54.(Luo Xiaona, Shi Yanhu, Zhu Xianqi. Research on the Trust Coordination Mechanism in Supply Chain of Network Group Purchase Based on Game [J]. Mathematics in Practice and The0ry,2014,44(22):47-54.)   
[20] 管晓永，陈红，刘润然，等．基于公众可获得信息的团购 网信用特性研究[J].科研管理,2013,34(5):144-152.(Guan Xiaoyong，Chen Hong，Liu Runran，et al．The Credit Behavior Characteristics of Online Group Buying Business Based on the Information Available to the Public [J].Science Research Management,2013,34(5): 144-152.)   
[21]GB/T26842-2011，基于电子商务活动的交易主体企业信用 评价指标与等级表示规范[S].北京：中国标准出版社， 2011.(GB/T26842-2011，Transaction Subject Based upon ActivitiesofElectronicCommerce-Specificationfor Enterprise Credit Assessment Index and Credit Grade [S]. Beijing: China Standard Press,2011.)   
[22]张成，吴映梅，魏强．基于关系式交易的网络团购模式及 其信用评价体系分析[J]．商业时代，2012(20)：43-44. (Zhang Cheng，Wu Yingmei，Wei Qiang.Analysis of Online Shopping Pattern and Its Credit Evaluation System Based on E-Commerce Activities [J]. Commercial Time,2012(20): 43-44.)   
[23] 赵培卿.C2B 模式下网络团购信用评价研究[D].秦皇岛: 燕山大学，2010.(Zhao Peiqing．Research on the Credit Evaluation of Group Shopping Traders Based on C2B Model [D]. Qinhungdao: Yanshan University, 2010.)

# 作者贡献声明：

张亚明：提出研究思路，设计研究方案;  
李娜：分析数据，进行实验，起草论文;  
赵培卿：采集、筛选数据，论文最终版本修订。

收稿日期:2015-07-14   
收修改稿日期:2015-10-30

# Study on Credit Evaluation Model of Online Group-buying by Using ACO and Similarity Weight Algorithm

Zhang Yaming Li Na Zhao Peiqing (School of Economy and Management, Yanshan University, Qinhuangdao O66oo4, China)

Abstract: [Objective]To help online group-buying consumers find high quality merchants quickly and help merchants improve their credit efficiently.[Methods] Usesimilarity weight todistribute the weights of index system,consider the goten composite indicator variables as the parameters of ant colony algorithm,and establish the credit evaluation model based on ACOand Similarity Weight Algorithm.[Results] Empirical results show thatthe model can effectively find out the shortest path to save time and moneycost,obtain high quality merchant.[Limitations]Not considering the impact of special trade on online group-buying credit evaluation,such as refund and fictitious trading; directly using previous research conclusion of other parameters in ACO.[Conclusions] The results can help merchants improve credit, promote satisfaction of consumer group,and provide the references for further research on online group-buying problems.

Keywords: Online group-buying Credit evaluationSimilarity weightAnt Colony Optimization(ACO)

# 研究报告提出建立单一的数字图书馆来支持所有公共图书馆

近日,BiblioCommons发布了题为《英国公共图书馆的基本数字基础设施：面向未来的计划》的报告。该报告主要研究目前用户在图书馆的体验情况，并试图给出建立一个汇总性数字图书馆的方法。该报告由英国艺术委员会赞助，并且得到一系列合作伙伴的支持。报告中的主要观点包括：

(1）当前图书馆的信息架构大部分是在30年前设计的。(2）图书馆网站经常让用户感到沮丧，不能很好地服务于用户。(3）目前图书馆的"数字基础设施"让图书馆很难与一些国家级的非盈利性机构和政府部门进行在线的用户数据和资源的共享。(4）目前图书馆的"数字基础设施"阻碍了图书馆博采众长，抑制而不是鼓励创新。(5）图书馆一直试图发展成为全国性的大联盟，因为每个图书馆都有自己特有的软件集，采用不同的编程语言；而不是采用一个通用的数字基础设施，使用相同的编程语言。英国国家统计局办公室指出，图书信息以外的网络世界正迅猛发展，主要表现如下：(1）联通到互联网的家庭数在1998-2014年间，增长了10倍，从 $9 \%$ 增至 $84 \%$ 。(2)在能上网的家庭里，只有 $3 . 6 \%$ 的家庭访问公共网络会遇到一定的障碍(2014年)。(3）在2006-2014年间，每天习惯上网的成年人数比例从 $3 5 \%$ 增长到 $76 \%$ 。BiblioCommons的报告和研究工作是基于其相当长一段时间内对图书馆用户、图书馆以外的网络用户，以及其他利益相  
关群体的研究。报告全文和附录资源可从相应网站下载。更多的关于 OCLC/ALISE 图书馆和信息科学研究资助项目可以在 htp://www.oclc.org/research/grants.html 中找到。先前  
资助的名单也可以在http://www.oclc.org/research/grants/awarded.html 中查找到。(编译自tp:/co/eort-oateati-sg-radial-pretsuptpublc-rarhfutue/)

(本刊讯)