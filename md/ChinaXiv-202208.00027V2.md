# 考虑风功率预测条件误差和时空关联性的分布鲁棒机组组合模型及算法

郑晓东1,2\*，瞿凯平2.3\*，吕嘉庆4.5，李正茂，曾波6

1.南方电网科学研究院有限责任公司，广州510663  
2.华南理工大学电力学院，广州510640  
3.南洋理工大学电气与电子工程学院，新加坡639798  
4.克拉科夫AGH科技大学电气工程学院，波兰克拉科夫  
5.曼尼托巴大学电气与计算机工程学院，加拿大温尼伯  
6.匹兹堡大学工业工程系、电气与计算机工程系系，美国匹兹堡15260  
\* 通信作者.E-mail: eezhengxd@xjtu.edu.cn,13560361373@163.com

本文的英文版已于 2021年发表于期刊 IEEE Transactions on Sustainable Energy.引用本文，可直接采用英文版的引文格式：Zheng X,Qu K,Lv J,etal.Addressing theconditional andcorrelated wind power forecast errors inunit commitment by distributionally robust optimization[J].IEEE Transactions on Sustainable Energy, 2020,12(2): 944-954.

摘要本文研究含随机风电的机组组合问题，基于分布鲁棒优化提出了考虑风功率预测的条件误差和误差时空相关性的建模及优化方法．首先，为了量化计算风功率的预测误差，用Lasso（最小绝对值收敛和选择算子)训练得到鲁棒的条件误差估计器；为了获取风功率预测误差的时空关联信息，通过无偏估计从历史数据得到误差的协方差矩阵．用所得的条件误差和协方差矩阵构造了改进的风功率预测误差的概率分布模糊集．其次，在多面体支撑集上建立了风功率预测误差的随机量，构建了两阶段分布鲁棒机组组合模型，并提出了与该模型等效的混合整数半正定规划模型．再次，提出了从第二阶段半正定优化问题辨识极限分布的方法，并提出了利用极限分布求解两阶段分布鲁棒机组组合问题的高效割平面算法．最后，进行数值实验，验证了所提模型在应对风功率预测误差的时空关联性方面的能力和优势，验证了模型决策方案的经济性和鲁棒性.

关键词 列和约束生成，分布鲁棒优化，极限分布，时空关联性，风功率预测

# 1引言

为应对化石能源枯竭问题和环境污染问题，风电等清洁能源发电在近二十年来得到了快速应用和发展．风电在助力全球可持续发展的同时，也给电力系统的经济和可靠运行，如日前机组组合，带来了新的挑战 [Qin et al.(2016),Lowery and O'Malley(2012)].这一挑战的根源是风功率的预测精度较低，尤其是对于在地理上广泛分布的多个风电场．为了高效地消纳风电并规避风电的负面作用，机组组合问题需要精细化考虑风电的随机性，以更好的开停机计划来保证风功率随机扰动下的系统功率平衡和经济运行.

随机规划是决策问题中随机变量建模的经典方法，但其在电力系统机组组合问题的应用中显露出多方面的不足．一方面，风功率预测误差的概率分布实际上是无法准确估计的，因此随机规划是建立在一个有偏差的概率分布之上，其得到的决策方案自然是有一定误导性的 [Delage and Ye(2010)].另一方面，随机规划中的数学期望无法准确计算，需要借助蒙特卡洛模拟等技术来估算（或者称样本平均估计）[Dupacova et al.(2003)]，而场景采样过程必然损失精度．所以，随机规划得到的开停机方案可能是不可靠的，再调度中可能需要付出昂贵的代价．鲁棒优化是风功率不确定性建模的另一种方法 [Bertsimas et al.(2011),Zeng and Zhao(2013),Samani and Aminifar(2019). 通过考虑不确定集内最恶劣的场景，鲁棒优化可以得到可靠性极高的决策方案．基本上，鲁棒优化不考虑不确定量的概率分布和详细关联性信息 [Zhao and Zeng(2012),Bertsimas et al.(2013)]，而这些正是风电的关键信息．近年来，文献 [Lorca and Sun(2016)]提出了计及可再生能源发电时空关联性的动态不确定集，文献 [Roldan et al.(2019)]基于协方差矩阵提出了计及不确定量相关性的椭球型不确定集.然而，这些文献中的不确定集并不包含概率分布信息.

精细和严谨地考虑风电的随机性对于新型电力系统的运行是非常必要的．基于上面的讨论和分析，本文采用随机规划和鲁棒优化之外的另一种优化方法来对风电随机性进行建模，从而提升机组组合方案的经济性和可靠性．分布鲁棒优化在电气工程学科是一种非常新的范式[Zhao andGuan(2015),Wei et al.(2016),Duan et al.(2017),Xiong et al.(2017),Chen et al.(2018),Zhu et al.(2019),Babaei et al.(2019),Zheng et al.(2020)]，其建模思路是找到给定模糊集中最恶劣的概率分布，并依据该分布制定决策[Delage and Ye(2010)]．相比随机规划，分布鲁棒优化借助随机量的矩信息[Delageand Ye(2010),Bertsimas et al.(2010)] 或者一个训练数据集 [Esfahani and Kuhn(2018),Zheng andChen(2020)]来定义概率分布的集合．考虑最极端概率分布得到的决策相比随机规划的决策具有更高的可靠性．而相比鲁棒优化，分布鲁棒优化考虑了更多的概率和统计信息，即它的决策过程量化地考虑所有随机事件，而不是聚焦在极端场景上．所以，分布鲁棒优化得到的决策在期望的意义上通常具有更好的经济性.

当前，应用分布鲁棒优化处理机组组合问题的文献大多采用基于概率密度的模糊集[Zhao andGuan(2015),Duan et al.(2017)] 和基于概率分布距离的模糊集[Chen et al.(2018),Zhu et al.(2019),Zheng and Chen(2020)]．也有文献采用基于矩信息的模糊集，但基本上只考虑了一阶矩信息 [Xionget al.(2017)]，所以没有办法对风电场之间的时空关联性进行建模．尽管有文献考虑了部分的二阶矩信息（即方差）[Babaei et al.(2019)]，但方差并不包含随机量之间的协变性．实际上，协方差反映了多个风电场出力的时空关联性，其携带的信息有助于排除风功率不符合实际的快速波动和爬坡事件[Qin et al.(2016),C6rdova et al.(2018)]，而这些极端事件能够显著影响机组的开停机计划[Loweryand O'Malley(2012),Che et al.(2019).

关于定义模糊集的另一个问题是如何准确刻画风功率的矩特性．目前，统计学习方法已经在可再生能源发电概率预测方面广泛应用 [Cordova et al.(2018),Bessa et al.(2012),Agoua et al.(2019)].例如，文献 [Bessa etal.(2012)]提出了条件性概率密度估计器，实现具有时间适应性的风功率预测；文献[Agoua et al.(2019)]采用 Lasso 来实现时空预测模型的输入变量筛选．不过，目前已有的预测方法通常忽略了预测值和预测误差的关联性．实际上，由气象或物理方法给出一个日前预测值之后，该预测值的误差期望是有一定规律，并且可以进行统计推理的．所以，可以对条件预测误差进行量化分析，然后用于校正日前预测，从而构建更为精确的模糊集.

除了建模之外，两阶段分布鲁棒机组组合模型在求解方面也极具挑战性,尤其是考虑了二阶矩约束之后.已有的求解方法利用线性决策规则 [Xiong et al.(2017),Duan et al.(2017),Zhu et al.(2019),Babaei et al.(2019)]，Benders 分解法 [Zhao and Guan(2015),Chen et al.(2018)]，或者延迟约束生成法[Wei et al.(2016),Chen et al.(2016),Zheng et al.(2020)]．线性决策规则作为一种近似方法，会导致决策的次优性．Benders 分解方法和延迟约束生成法则存在计算效率低的问题，可能无法有效处理模糊集含有协方差矩阵的分布鲁棒机组组合问题[Zhenget al.(2020)].

在这一项研究中，我们使用精细的模糊集构建了基于矩模糊集的分布鲁棒机组组合模型，从而对风功率预测误差的相关性和条件误差进行了有效建模．此外，提出了高效的计算方法．本文的贡献可以总结为以下两点：

1.利用Lasso从训练数据集辨识风功率的条件误差与日前预测值的关系．使用风功率预测误差的条件期望和协方差构建模糊集，从而建立了含改进模糊集的分布鲁棒机组组合模型  
2．利用锥线性规划的对偶理论、单阶段鲁棒优化的重构方法、Schur补等，将含多面体支撑集的分布鲁棒机组组合模型的第二阶段问题精确地转化为半正定规划问题．证明半正定规划问题求解之后可以得到一个风功率的极限分布．基于极限分布，提出了基于原空间割平面的算法，该算法相比已有算法能够更加高效的求解两阶段分布鲁棒机组组合问题，

# 2 模型构造

# 2.1分布鲁棒机组组合模型

首先给出本文采用的机组组合模型．该模型考虑了可中断负荷、随机风电、弃风等要素，模型具体如下所示.

$$
\begin{array} { r l } & { \operatorname* { m i n } \displaystyle \sum _ { t \in { \mathcal T } } \displaystyle \sum _ { g \in { \mathcal G } } x _ { g , t } N L _ { g } + u _ { g , t } S U _ { g } + v _ { g , t } S D _ { g } + C _ { g } ( p _ { g , t } ) } \\ & { \qquad + \displaystyle \sum _ { t \in { \mathcal T } } \displaystyle \sum _ { d \in { \mathcal D } ^ { I } } C _ { d , t } ^ { I } ( \delta _ { d , t } ^ { I } ) + \displaystyle \sum _ { t \in { \mathcal T } } \displaystyle \sum _ { w \in { \mathcal W } } C _ { w } ^ { C } ( \delta _ { w , t } ^ { C } ) } \\ & { \qquad + \displaystyle \sum _ { t \in { \mathcal T } } C ^ { \mathrm { P e n } } \big ( \displaystyle \sum _ { g \in { \mathcal G } } ( s _ { g , t } ^ { G + } + s _ { g , t } ^ { G - } ) + \displaystyle \sum _ { d \in { \mathcal D } } s _ { d , t } ^ { D } \big ) } \end{array}
$$

$$
\begin{array} { r l } & { \qquad \displaystyle \sum _ { \tau = \operatorname* { m a x } \{ 1 , t - M U _ { g } + 1 \} } ^ { t } u _ { g , \tau } \leqslant x _ { g , t } \forall g \in \mathcal { G } , t \in \mathcal { T } } \\ & { \qquad \displaystyle \sum _ { \tau = \operatorname* { m a x } \{ 1 , t - M U _ { g } + 1 \} } ^ { t } v _ { g , \tau } \leqslant 1 - x _ { g , t } \forall g \in \mathcal { G } , t \in \mathcal { T } } \\ & { \qquad \displaystyle \sum _ { \tau = \operatorname* { m a x } \{ 1 , t - M D _ { g } + 1 \} } ^ { \operatorname* { m i n } } v _ { g , \tau } \leqslant 1 - x _ { g , t } \forall g \in \mathcal { G } , t \in \mathcal { T } } \\ & { \qquad \displaystyle P _ { g } ^ { \operatorname* { m i n } } x _ { g } \leqslant p _ { g , t } \leqslant P _ { g } ^ { \operatorname* { m a x } } x _ { g } \forall g \in \mathcal { G } , t \in \mathcal { T } } \end{array}
$$

$$
- R _ { g } ^ { - } \leqslant p _ { g , t } - p _ { g , t - 1 } \leqslant R _ { g } ^ { + } \forall g \in \mathcal { G } , t , t - 1 \in \mathcal { T }
$$

$$
0 \leqslant \delta _ { d , t } ^ { I } \leqslant D _ { d , t } ^ { \operatorname* { m a x } } \forall d \in \mathcal { D } ^ { I } , t \in \mathcal { T }
$$

$$
\begin{array} { r l } { \displaystyle \left. \begin{array} { l } { 0 \leqslant \delta _ { u , t } ^ { C } \leqslant \mathrm { W } _ { u , t } + \xi _ { u , t } \leqslant \mathrm { W } \leqslant \mathcal { W } , t \in \mathcal { T } } \\ { - F _ { i } \leqslant \mathrm { W } _ { u , t } ^ { C } ( \beta _ { y , t } + \delta _ { y , t } ^ { C } - \delta _ { y , t } ^ { C } ) + } \\ { \displaystyle \sum _ { d \in \mathbb { F } } \kappa _ { d , t } ^ { B } ( D _ { d , t } - s _ { i , t } ^ { ( 0 ) } ) - \displaystyle \sum _ { d \in \mathbb { F } ^ { \prime } } \kappa _ { d , t } ^ { B } \partial _ { d , t } ^ { i } + } \\ { \displaystyle \sum _ { m \in \mathbb { W } } \kappa _ { w , t } ^ { W } ( W _ { u , t } + \xi _ { m , t } - \delta _ { w , t } ^ { C } ) \leqslant F _ { i } \forall \ : \mathrm { W } \ : G , t \in \mathcal { T } } \end{array} \right. } \\ { \displaystyle \sum _ { y \in \mathcal { G } } \left( \beta _ { y , t } + s _ { g , t } ^ { ( + ) } - \delta _ { g , t } ^ { ( - ) } \right) + \displaystyle \sum _ { m \in \mathbb { W } } ( W _ { w , t } + \xi _ { m , t } - \delta _ { w , t } ^ { C } ) = } \\ { \displaystyle \sum _ { d \in \mathbb { F } } \sum _ { d , t } ( D _ { d , t } - s _ { i , t } ^ { W } ) - \displaystyle \sum _ { d \in \mathbb { F } } \delta _ { d , t } ^ { i } \forall \ : \mathrm { W } \in \mathcal { T } . } \end{array}
$$

·T：调度时段的集合.  
· $\mathcal { G }$ ：发电机组的集合.  
· $\mathcal { L }$ ：输电线路的集合.  
· $\mathcal { D }$ ：所有负荷节点的集合.  
· $\mathcal { D } ^ { I }$ ： $\mathcal { D }$ 的子集，代表可中断负荷的集合.  
· $\boldsymbol { \mathcal { W } }$ ：风电场的集合.  
· $N L _ { g }$ ：发电机组 $g$ 的空载成本.  
· $S U _ { g }$ ：机组 $g$ 的启动成本.  
· ${ \mathit { S D } } _ { { \mathit { g } } }$ ：机组 $g$ 的停机成本.  
· $C _ { g } ( \cdot )$ ：机组 $g$ 的可变发电成本.  
· $C _ { d , t } ^ { I } ( \cdot )$ ：负荷 $d$ 在时段 $\mathbf { \Psi } _ { t }$ 的负荷中断成本.  
· $C _ { w } ^ { C } ( \cdot )$ ：风电场 $w$ 的弃风成本.  
： $C ^ { \mathrm { P e n } } ( \cdot )$ ：松弛变量的惩罚费用.  
· $M U _ { g }$ ：机组 $g$ 的最小开机时间.  
· $M D _ { g }$ ：机组 $g$ 的最小停机时间.  
： $P _ { g } ^ { \mathrm { m i n } }$ ：机组 $g$ 的最小技术出力.  
， $P _ { g } ^ { \mathrm { m a x } }$ ：机组 $g$ 的最大发电能力.· $R _ { g } ^ { \pm }$ ：机组 $g$ 的上/下爬坡能力.  
： $D _ { d , t } ^ { \operatorname* { m a x } }$ ：负荷 $d$ 在时段 $\mathbf { \Psi } _ { t }$ 可中断量.  
· $F _ { l }$ ：输电线路 $l$ 的传输容量.  
· $\kappa _ { g , l } ^ { G }$ ：机组 $g$ 到线路 $l$ 的功率转移因子.  
$\kappa _ { d , l } ^ { D }$ ：负荷 $d$ 到线路 $\textit { l }$ 的功率转移因子.  
. $\kappa _ { w , l } ^ { W }$ ：风电场 $w$ 到线路 $l$ 的功率转移因子.  
· $D _ { d , t }$ ：负荷 $d$ 在时段 $\mathbf { \Psi } _ { t }$ 的需求水平.  
· $W _ { w , t }$ ：风电场 $w$ 在时段 $t$ 的日前发电功率预测值· $x _ { g , t }$ ：指示机组开机的0-1状态变量.  
· $\boldsymbol { u } _ { g , t }$ ：指示机组启动的0-1状态变量.  
· $\boldsymbol { v } _ { g , t }$ ：指示机组关停的0-1状态变量.  
· $p _ { g , t }$ ：机组 $g$ 在时段 $\mathbf { \Psi } _ { t }$ 的出力优化值.  
： $\delta _ { d , t } ^ { I }$ ：负荷 $d$ 在时段 $t$ 的负荷中断量.  
： $\delta _ { w , t } ^ { C }$ ：风电场 $w$ 在时段 $\mathbf { \Psi } _ { t }$ 的弃风量.  
， $s _ { g , t } ^ { G \pm }$ ：机组 $g$ 在时段 $t$ 松弛变量的正/负分量.  
· $s _ { d , t } ^ { D }$ ：负荷 $d$ 在时段 $\mathbf { \Psi } _ { t }$ 的非负松弛变量.  
· $\xi _ { w , t }$ ：风电场 $w$ 在时段 $\mathbf { \Psi } _ { t }$ 的预测误差，随机量.

目标函数(1)考虑了开停机成本、发电成本、负荷中断和弃风费用，以及松弛变量的惩罚费用等各项费用均采用线性的成本函数．式(2)-(4)为机组的状态转移方程和最小开停机时间约束．式(5)为机组的发电能力约束，该约束耦合了机组启停0-1变量和出力连续变量．式(6)为机组的爬坡约束.式(7)-(8)限定了负荷中断量和弃风量.式(9)为输电线路的潮流约束.式(10)为系统功率平衡约束.注意约束(9)-(10)包含松弛变量，用以保证问题的可行性.具体而言，每一台发电机组的每个时段均配置了自由变量，表征正的功率注入 $s _ { g , t } ^ { G + }$ 或者负的功率注入 $s _ { g , t } ^ { G - }$ ，而每个负荷阶段均配置了切负荷变量 $s _ { d , t } ^ { D }$ ．松弛变量取非零值意味系统在正常情况下无法维持线路潮流不越限，或者不能维持系统功率平衡，必须采取紧急措施才能保证安全运行．为了表示非正常运行情况下的风险代价，式(1)的最后一项对松弛变量进行惩罚，该惩罚系数取值较大，

在问题(1)-(10)中，机组启停变量是“此时此地”类型的决策变量，后续将其归类为第一阶段变量 $\scriptstyle { \mathbf {  { x } } }$ ．连续型的调度变量可以根据日内观察到的实际情况进行调整，因此归类为第二阶段变量$_ y$ [Bertsimas et al.(2013)]．随机变量记为向量 $\boldsymbol { \xi }$ ：基于变量的分组，可以得到问题(1)-(10)的紧凑形式，具体如下所示.

$$
\operatorname* { m i n } _ { { \boldsymbol { x } } , { \boldsymbol { y } } } { \boldsymbol { c } } _ { I } ^ { \top } { \boldsymbol { x } } + { \boldsymbol { c } } _ { C } ^ { \top } { \boldsymbol { y } }
$$

$$
\begin{array} { l } { G y \geqslant g } \\ { A x + B y \geqslant d } \\ { U y + V \xi = W w , } \end{array}
$$

其中， $\scriptstyle { c _ { I } }$ 和 $c _ { C }$ 是成本系数.式(11b)包含了(2)-(4).式(11c)是第二阶段变量 $\boldsymbol { y }$ 本身的相关约束，包含(6)-(7).式(11d)是耦合约束，对应(5).问题(1)-(10)中既包含第二阶段连续变量又包含随机量的约束由式(11e)表示.

问题(1)-(10)对应的两阶段分布鲁棒优化模型考虑模糊集中最极端的概率分布进行优化决策，其具体形式为

$$
\operatorname* { m i n } _ { { \pmb x } \in { \pmb X } } \operatorname* { m a x } _ { \mathbb { P } \in \mathcal { P } } { \pmb x } _ { I } ^ { \top } { \pmb x } + \mathbb { E } _ { \mathbb { P } } [ Q ( { \pmb x } , { \pmb \xi } ) ] ,
$$

其中 $\mathcal { X } = \{ x | F x \geqslant f \}$ 是第一阶段变量的可行域．式(12)的最优值函数 $Q ( { \pmb x } , { \pmb \xi } )$ 是根据第二阶段问题定义的，即

$$
Q ( \pmb { x } , \pmb { \xi } ) = \operatorname* { m i n } _ { \pmb { y } \in \mathscr { y } } \pmb { c } _ { C } ^ { \top } \pmb { y } ,
$$

其中 $\mathcal { Y } = \{ \pmb { y } | ( 1 1 \mathrm { c } ) - ( 1 1 \mathrm { e } ) \}$ 是第二阶段变量的可行域.模糊集 $\mathcal { P }$ 的定义如下，

$$
\mathcal { P } = \{ \mathbb { P } \in \mathcal { P } _ { 0 } ( \Xi ) | \mathbb { E } _ { \mathbb { P } } [ \Xi ] = \bar { \xi }   \qquad \\   \mathbb { E } _ { \mathbb { P } } [ ( \xi - \bar { \xi } ) ( \xi - \bar { \xi } ) ^ { \top } ] \preceq \Sigma  \} .
$$

式(14)中， $\mathcal { P } _ { 0 } ( \Xi )$ 表示有界支撑集的 $\sigma$ 代数上的所有概率分布，

$$
\Xi = \left\{ \xi \left| \xi ^ { \operatorname * { m i n } } \xi \xi \leqslant \xi ^ { \operatorname * { m a x } } \right. \right\} .
$$

式(14)的第二行表示风功率预测误差的期望值是 $\bar { \pmb { \xi } }$ ，式(14)的第三行将协方差限定在了两个半正定锥的交集之内，即 $\mathbf { 0 } \preceq \mathbb { E } _ { \mathbb { P } } [ ( \pmb { \xi } - \pmb { \bar { \xi } } ) ( \pmb { \xi } - \pmb { \bar { \xi } } ) ^ { \top } ] \preceq \Sigma$ ．直观地讲，风功率预测误差的方差和协方差不能比经验数值给定的程度更“严重”．

# 2.2 基于数据的矩估计

随机向量 $\boldsymbol { \xi }$ 的一阶和二阶矩对于模糊集(14)的构建十分关键．在这一小节，我们将介绍 $\bar { \pmb { \xi } }$ 和 $\pmb { \Sigma }$ 的估计方法.

通常，风功率日前预测采用气象或物理方法，由数值天气预报和风机功率曲线得到风功率预测值[Shokrzadeh etal.(2014)].在执行机组组合计算之前，系统运行机构已经掌握了风功率的预测值举个例子，在一个具有2个风电场的系统中，如果采用24小时的计划模型，则在机组组合建模时已经具备了维数为 $N = 4 8$ 的日前预测向量 $\hat { \omega }$ ．给定日前预测，预测误差的条件期望通常是非零值，甚至可能很大[Bessa et al.(2012)].我们将与向量 $\hat { \omega }$ 的第 $n$ 个元素相对于的预测误差条件期望标记为$\mathbb { E } [ \xi _ { n } | \hat { \omega } ]$ ．这里所描述的条件期望便是模糊集(14)所用到的期望，即 $\mathbb { E } [ \pmb { \xi } | \hat { \omega } ] = \bar { \pmb { \xi } }$ ，为了推断出 $\mathbb { E } [ \xi _ { n } | \hat { \omega } ]$ 的数值，假定我们具备一组历史的日前预测和实际误差的数据，这组数据的形式为

$$
D _ { n } = \{ ( \hat { \omega } _ { 1 } , \hat { \xi } _ { n , 1 } ) , ( \hat { \omega } _ { s } , \hat { \xi } _ { n , s } ) , . . . , ( \hat { \omega } _ { S } , \hat { \xi } _ { n , S } ) \}
$$

且 $( \hat { \xi } _ { n , s } , \hat { \omega } _ { s } )$ 具备如下线性结构

$$
\hat { \xi } _ { n , s } = \beta _ { n , 0 } + \sum _ { j } ^ { N } \beta _ { n , j } \hat { \omega } _ { n , s } + \varepsilon _ { n , s } s = 1 , . . . , S .
$$

式(16)中， $S$ 表示数据集的规模， $\varepsilon _ { n , s }$ 为噪声， $\{ \beta _ { n , 0 } , . . . , \beta _ { n , N } \}$ 是需要辨识的权重．上述线性模型可以写成矩阵的形式，

$$
\hat { \xi } _ { n } = \hat { \Omega } \beta _ { n } + \varepsilon _ { n } ,
$$

其中 $\hat { \pmb { \xi } } _ { n } = [ \hat { \xi } _ { n , 1 } , . . . , \hat { \xi } _ { n , S } ] ^ { \top }$ $\begin{array} { r } { \boldsymbol { \varepsilon } _ { n } = [ \varepsilon _ { n , 1 } , . . . , \varepsilon _ { n , S } ] ^ { \top } , \beta _ { n } = [ \beta _ { n , 0 } , . . . , \beta _ { n , N } ] ^ { \top } , \hat { \boldsymbol { \Omega } } ^ { \top } = [ \mathbf { 1 } ^ { \top } ; \hat { \omega } _ { 1 } ^ { \top } ; . . . , \hat { \omega } _ { S } ^ { \top } ] . } \end{array}$ 下一步的任务是找到一个能够最好程度拟合历史数据的向量 ${ \beta } _ { n } ^ { \star }$ ，基于该向量我们可以从新的样本 $\hat { \omega }$ 计算出 $\hat { \xi } _ { n }$ （即给定一个新的日前预测值，可以计算出相应的条件误差）：

式(17)中的向量 ${ \beta } _ { n } ^ { \star }$ 可以经由回归分析得到．在多种回归分析方法中，Lasso 相比经典的线性回归和岭回归有一定的优势，因此本文采用 Lasso 来求解线性系统(17).Lasso 是基于对拟合偏差平方和与 $L _ { 1 }$ 范数惩罚的最小化实现的，即

$$
\beta _ { n } ^ { \mathrm { L a s s o } } = \arg \operatorname* { m i n } _ { \beta _ { n } } \frac { 1 } { S } \| \hat { \pmb { \xi } } _ { n } - \hat { \pmb { \Omega } } \beta _ { n } \| _ { 2 } ^ { 2 } + \lambda \| \pmb { \beta } _ { n } \| _ { 1 } .
$$

$L _ { 1 }$ 范数使得Lasso 具备了自动特征筛选的功能，可以防止过拟合，实现更强的鲁棒性．参数 $\lambda$ 是正则化的权重稀疏，该参数可以由交叉检验来选取[Lv et al.(2013)]．本文的 Lasso 将由经典的坐标下降算法求解 [Friedman et al.(2007)].

根据式(17)-(18)，所有输入变量统一用于估计任意一个输出．所以，估计器计及了相邻时段和相邻风电场的特征．值得注意的是，在本文的框架内需要求解 $N$ 个Lasso 模型，通过这种方式反映每个 $\xi _ { n }$ 与 $\hat { \omega }$ 之间的不同映射关系[Bessa etal.(2012)]．最终，基于训练完成的 $N$ 个估计器，一阶矩可以在日前风功率预测值的基础上计算得到：

$$
\bar { \xi } _ { n } = [ 1 , \hat { \omega } ^ { \top } ] \beta _ { n } ^ { \mathrm { { L a s s o } } } n = 1 , . . . N .
$$

随机向量的二阶矩（协方差矩阵）由无偏估计器得到[Delage andYe(2010)]:

$$
\pmb { \Sigma } = \frac { 1 } { ( S - 1 ) } \sum _ { s = 1 } ^ { S } ( \hat { \pmb { \xi } } _ { s } - \frac { 1 } { S } \sum _ { t = 1 } ^ { S } \hat { \pmb { \xi } } _ { t } ) ( \hat { \pmb { \xi } } _ { s } - \frac { 1 } { S } \sum _ { t = 1 } ^ { S } \hat { \pmb { \xi } } _ { t } ) ^ { \top } .
$$

# 3 求解方法

# 3.1 求解第二阶段问题

分布鲁棒机组组合模型(12)的第二阶段最大化问题是一个无穷维锥线性问题，其详细模型为

$$
Z ( \pmb { x } ) = \operatorname* { m a x } _ { f _ { \pmb { \xi } } \geqslant 0 } \int _ { \Xi } Q ( \pmb { x } , \pmb { \xi } ) f _ { \pmb { \xi } } \mathrm { d } \pmb { \xi }
$$

$$
\begin{array} { r l } { \displaystyle \int _ { \Xi } f _ { \xi } \mathrm { d } \xi = 1 } & { : h _ { 0 } } \\ { \displaystyle } & { \int _ { \Xi } \xi f _ { \xi } \mathrm { d } \xi = \bar { \xi } \quad : h } \\ { \displaystyle } & { \int _ { \Xi } \xi \xi ^ { \top } f _ { \xi } \mathrm { d } \xi \preceq \Sigma + \bar { \xi } \bar { \xi } ^ { \top } \quad : H , } \end{array}
$$

其中 $f _ { \xi }$ 是决策变量，代表事件 $\pmb { \xi }$ 处的概率密度. $f _ { \xi }$ 是一个半正定矩阵, $\boldsymbol { h }$ 是自由向量, $h _ { 0 }$ 是自由变量．这三个变量是问题的约束的对偶变量．问题21的对偶问题为 [Bertsimas and Sethuraman(2000),Freund(2004)],

$$
Z ( \pmb { x } ) = \operatorname* { m i n } _ { \pmb { H } \succeq \mathbf { 0 } , h , h _ { 0 } } \mathrm { ~ t r } \left( \pmb { H } ^ { \top } \pmb { \Theta } \right) + \pmb { h } ^ { \top } \bar { \pmb { \xi } } + h _ { 0 }
$$

$$
\begin{array} { r } { \pmb { \xi } ^ { \top } \pmb { H } \pmb { \xi } + \pmb { h } ^ { \top } \pmb { \xi } + h _ { 0 } \geqslant Q ( \pmb { x } , \pmb { \xi } ) \quad \forall \pmb { \xi } \in \Xi , } \end{array}
$$

其中 $\begin{array} { r } { \Theta = \pmb { \Sigma } + \bar { \pmb { \xi } } \bar { \pmb { \xi } } ^ { \top } } \end{array}$ ， $\operatorname { t r } ( X )$ 代表矩阵 $\boldsymbol { x }$ 的迹．值得注意的是，问题(22)和问题(21)的强对偶性的充分条件是这两个问题都是可行的，且 $\pmb { \Sigma } \succ \mathbf { 0 }$ [Bertsimas and Sethuraman(200O), Wei et al.(2016)],而这两个条件是成立的．一方面，原问题(21)总是可行的，因为其目标函数中的值函数 $Q ( { \pmb x } , { \pmb \xi } )$ 总是可行和有界的（由第2.1节机组组合问题的定义可知)；另外，矩问题至少有一个可行解，该解是在期望 $\bar { \xi }$ 处取概率1的分布[Delage and Ye(2010)]．另一方面，协方差矩阵 $\pmb { \Sigma }$ 在实际中通常不会是0,因为风功率的日前预测不可能在整个24小时范围内都是准确的.

给约束(11c)-(11e)赋予对偶变量 $\lambda , \mu , \nu$ 之后，可以写出 $Q ( { \pmb x } , { \pmb \xi } )$ 的对偶问题

$$
Q ( x , \pmb { \xi } ) = \operatorname* { m a x } _ { \lambda , \mu , \nu } g ^ { \top } \lambda - \left( A x - d \right) ^ { \top } \pmb { \mu } - \left( V \pmb { \xi } - W w \right) ^ { \top } \pmb { \nu }
$$

$$
\mathfrak { s . t . } c _ { C } - ( G ^ { \top } \lambda + B ^ { \top } \mu + U ^ { \top } \nu ) = \mathbf { 0 } , \lambda \geqslant \mathbf { 0 } , \mu \geqslant \mathbf { 0 } ,
$$

基于 $\lambda , \mu , \nu$ 的对偶问题，问题(22)可以写成[Wei et al.(2016)],

$$
Z ( \pmb { x } ) = \operatorname* { m i n } _ { \pmb { H } \succeq \mathbf { 0 } , h , h _ { 0 } } \mathrm { ~ t r ~ } \big ( \pmb { H } ^ { \top } \pmb { \Theta } \big ) + \pmb { h } ^ { \top } \bar { \pmb { \xi } } + h _ { 0 }
$$

其中 $Q _ { i } ^ { - } ( { \pmb x } , { \pmb \xi } ) = { \pmb g } ^ { \top } \lambda _ { i } - { ( { \pmb A } { \pmb x } - { \pmb d } ) } ^ { \top } { \pmb \mu } _ { i } + { \pmb W } { \pmb w } ^ { \top } { \pmb \nu } _ { i }$ 是问题(23)的目标函数中独立于 $\pmb { \xi }$ 的部分, $\{ \lambda _ { i } , \mu _ { i } , \nu _ { i } \}$ 是问题(23)的可行域的顶点， $\boldsymbol { \mathcal { T } }$ 是顶点的指标集

问题(24)仍然是一个半无穷规划问题，该问题包含无穷多个以 $\boldsymbol { \xi }$ 为指标的约束，因此无法直接求解．在文献 [Wei et al.(2016),Zheng et al.(2020)]中，基于 $\Xi = \mathbb { R } ^ { | \pmb { \xi } | }$ 的假设，约束(24b)可以用一个半正定锥等效表征．然而，支撑集无穷大的假设要求系统能够应对大量非现实的风功率场景，进而可能导致最终的机组组合方案不合理.在文献 [Chen et al.(2016),Delage and Ye(2010)]中，基于支撑集为椭球的假设，约束(24b)可以用S引理等效转化成一个半正定约束．然而，该方法不能直接应用于约束(24b)，因为这里采用的是多面体支撑集．为此，本文提出一种新的方法来处理半无穷维约束(24b)．该方法的出发点是将问题(24)看成一个以 $\boldsymbol { \xi }$ 为不确定量的单阶段鲁棒优化问题．该方法具体如下所示.

尽管 $H$ 并不一定是整定矩阵，我们首先假设 ${ \pmb { H } } \succ { \pmb { 0 } }$ ．这一假设意味着(25)中的最小化问题是一个含仿射约束的凸二次规划．所以，根据强对偶性，约束(26)的第 $\mathbf { \chi } _ { i }$ 行（后续记为(25)）可以等效地写成下式,

$$
\begin{array} { r l } & { \underset { \xi \in \Xi } { \operatorname* { m i n } } \xi ^ { \top } H \xi + ( h ^ { \top } + \nu _ { i } ^ { \top } V ) \xi + h _ { 0 } - Q _ { i } ^ { - } ( { \pmb { x } } , { \pmb { \xi } } ) \geqslant 0 } \\ & { \qquad \quad \underset { \pmb { \xi } } { \underbrace { \mathrm { \normalfont ~ \ c u a l i z i n g } } }  } \\ & { \underset { \quad { \pmb { \operatorname* { m a x } } } _ { { \pmb { u } } _ { 1 } , { \pmb { u } } _ { 2 i } \geqslant { \pmb { 0 } } } } { \operatorname* { m a x } } - 1 / 4 h _ { i } ( { \pmb { u } } _ { i } ) ^ { \top } H ^ { - 1 } h _ { i } ( { \pmb { u } } _ { i } ) + h _ { 0 i } ( { \pmb { u } } _ { i } ) \geqslant 0 . } \end{array}
$$

式(26)中， ${ \mathbf { } } { \mathbf { } } { \mathbf { } } u _ { 2 i } , { \mathbf { } } { \mathbf { } } u _ { 1 i }$ 是 $\boldsymbol { \xi }$ 的边界约束对应的非负对偶变量，具体参照式(15)．向量 ${ \mathbf { } } h _ { i } ( { \mathbf { } } { \mathbf { } } u _ { i } )$ 表示 $h +$ $V ^ { \top } \pmb { \nu } _ { i } + \pmb { u } _ { 2 i } - \pmb { u } _ { 1 i }$ ，标量 $h _ { 0 i } ( { \pmb u } _ { i } )$ 表示 $h _ { 0 } - Q _ { i } ^ { - } ( { \pmb x } , { \pmb \xi } ) - { \pmb u } _ { 2 i } ^ { \top } { \pmb \xi } ^ { \operatorname* { m a x } } + { \pmb u } _ { 1 i } ^ { \top } { \pmb \xi } ^ { \operatorname* { m i n } }$ .注意到式(26)中的 max 算子可以移除，式(26)可以通过 Schur 补进一步写成

$$
\begin{array} { r } { \left[ \begin{array} { c c } { \pmb { H } } & { 1 / 2 \pmb { h } _ { i } ( \pmb { u } _ { i } ) } \\ { 1 / 2 \pmb { h } _ { i } ( \pmb { u } _ { i } ) ^ { \top } } & { \pmb { h } _ { 0 i } ( \pmb { u } _ { i } ) } \end{array} \right] \succeq \mathbf { 0 } , ~ \pmb { u } _ { 1 i } , \pmb { u } _ { 2 i } \geqslant \mathbf { 0 } . } \end{array}
$$

对于 $\pmb { H } = \mathbf { 0 }$ 的情况，式(26)将退化成线性如(28)所示的问题.同样地，根据强对偶性，式(28)可以等效写成(29)．而(29)同样可以由式(27)表示．因此，式(27)对于任意 $H$ 严格正定或者半正定的情况都是准确和适用的，

$$
\begin{array} { r l } & { \underset { \xi \in \Xi } { \operatorname* { m i n } } \left( h ^ { \top } + \nu _ { i } ^ { \top } V \right) \xi + h _ { 0 } - Q _ { i } ^ { - } \left( { \pmb x } , { \pmb \xi } \right) \geqslant 0 } \\ & { \qquad \quad \underset { \pmb { \xi } \operatorname { m a x } } { \operatorname* { d u a l i z i n g } } , } \\ & { \underset { \quad \quad h _ { i } \left( { \pmb u } _ { i } \right) = { \pmb 0 } , { \pmb u } _ { 1 i } , { \pmb u } _ { 2 i } \geqslant { \pmb 0 } } { h _ { 0 i } } ( { \pmb u } _ { i } ) \geqslant 0 . } \end{array}
$$

利用半正定约束(27)，问题(24)可以精确地转化成一个半正定规划：

$$
Z ( \pmb { x } ) = \operatorname* { m i n } _ { \pmb { H } \succeq \mathbf { 0 } , \boldsymbol { h } , \boldsymbol { h } _ { 0 } , \boldsymbol { u } _ { 1 i } , \boldsymbol { u } _ { 2 i } } \mathrm { t r } \left( \pmb { H } ^ { \top } \Theta \right) + \boldsymbol { h } ^ { \top } \bar { \boldsymbol { \xi } } + \boldsymbol { h } _ { 0 }
$$

可以看到问题(30)具有有限多个以问题(23)的可行域顶点为指标的约束．为了处理这个问题，我们采用延迟约束生成法来求解问题(30)，具体过程如下所述

首先，给定顶点的子集 $\{ \{ \lambda _ { i } , \pmb { \mu } _ { i } , \pmb { \nu } _ { i } \} | i = 1 , . . . , I \}$ ，其中 $I \leqslant | { \mathcal { I } } |$ ，求解问题(30)的松弛问题以得到一个待校验的解 $\{ H ^ { \star } , h ^ { \star } , h _ { 0 } ^ { \star } \}$ ．然后，通过求解如下的双凸问题来校验约束(22b)是否满足[Weietal.(2016)],

$$
R ( H ^ { \star } , h ^ { \star } , h _ { 0 } ^ { \star } ) = \operatorname* { m i n } _ { \xi , \lambda , \mu , \nu } \xi ^ { \top } H ^ { \star } \xi + h ^ { \star \top } \xi + h _ { 0 } ^ { \star }
$$

$$
- \left( \pmb { g } ^ { \top } \pmb { \lambda } - ( \pmb { A } \pmb { x } - \pmb { d } ) ^ { \top } \pmb { \mu } - ( \pmb { V } \pmb { \xi } - \pmb { W } \pmb { w } ) ^ { \top } \pmb { \nu } \right)
$$

$$
\lambda \geqslant \mathbf { 0 } , \mu \geqslant \mathbf { 0 } , \xi \in \Xi .
$$

如果 $R ( H ^ { \star } , h ^ { \star } , h _ { 0 } ^ { \star } ) \geqslant 0$ ,则约束(22b)是满足的,可以确定当前解是问题(22)的最优解．如果 $R ( H ^ { \star } , h ^ { \star } , h _ { 0 } ^ { \star } ) \geqslant$ 0 不成立，则存在一组对偶变量的解 $\{ \lambda ^ { \star } , \mu ^ { \star } , \nu ^ { \star } \}$ ，将其记为 $\{ \lambda _ { I + 1 } , \pmb { \mu } _ { I + 1 } , \pmb { \nu } _ { I + 1 } \}$ ，这个解是一个新的顶点，可以将其扩充到问题(30)中，再次求解松弛问题并重复上述过程.

# 3.2 概率分布生成法

用上文得到的半正定规划(30)替换(12)的第二阶段问题，可以得到如下的混合整数半正定规划，

$$
\operatorname* { m i n } _ { { \pmb x } \in { \mathcal X } } { \pmb c } _ { I } ^ { \top } { \pmb x } + { \cal Z } ( { \pmb x } ) .
$$

混合整数半正定规划问题(32)可以采用延迟约束生成法的框架，通过序贯求解多个大规模的混合整数半正定规划问题来求解．受限于现有混合整数半正定规划求解器的能力，延迟约束生成法实际上是不适用的 [Zheng et al.(2020)].

为了高效求解分布鲁棒机组组合问题，可以借鉴文献 [Zeng and Zhao(2013)]的作者提出的原割平面算法 (即列和约束生成法)，该算法可以非常有效地解决两阶段鲁棒优化问题.列和约束生成法的基本思想是对于迭代过程中每一个辨识到的极端场景，在原变量的决策空间不断地构造运行约束，使得第一阶段问题满足极端场景的运行要求．本文在列和约束生成法的框架下，提出一种原割平面算法来有效处理分布鲁棒机组组合问题．考虑到该算法是基于迭代过程中辨识到的极端概率分布而非极端场景，后续我们称其为概率分布生成法.

下文我们首先揭示一个重要的原理和结论，即求解半正定规划问题(30)之后可以得到特定的第一阶段决策 $\textbf { \em x }$ 相应的极端概率分布（极限分布），然后再介绍求解所提的分布鲁棒机组组合问题求解算法.

对问题(30)再次使用对偶方法，可以得到原问题(21)有限维形式的版本：

$$
Z ( \pmb { x } ) = \operatorname* { m a x } _ { \pmb { \sigma } _ { i } , \pmb { \pi } _ { i } , \rho _ { i } } \sum _ { i } \rho _ { i } Q _ { i } ^ { - } ( \pmb { x } , \pmb { \xi } _ { i } ) - ( \pmb { V } \pmb { \pi } _ { i } ) ^ { \top } \pmb { \nu } _ { i }
$$

$$
\cdot \sum _ { i \in \mathcal { I } } \rho _ { i } = 1
$$

$$
\left[ \begin{array} { l } { \pmb { \sigma } _ { i } ~ \pmb { \pi } _ { i } } \\ { \pi _ { i } ^ { \top } ~ \rho _ { i } } \end{array} \right] \succeq \mathbf { 0 } ~ \forall i \in \mathcal { T }
$$

$$
\rho _ { i } \pmb { \xi } ^ { \operatorname* { m i n } } \leqslant \pi _ { i } \leqslant \rho _ { i } \pmb { \xi } ^ { \operatorname* { m a x } } \quad \forall i \in \mathcal { I } ,
$$

其中变量 $\pmb { \sigma } _ { i }$ ， ${ \boldsymbol { \pi } } _ { i }$ ， $\rho _ { i }$ 是如算法1的第1行所示的对偶变量．不失一般性，这里假设 $\rho _ { i }$ 的取值均为非零值．从约束(33b)-(33c)可以看出，变量的组合表达式 ${ \pi _ { i } / \rho _ { i } }$ （后文记为 $\pmb { \xi } _ { i }$ ）是与随机向量紧密相关的．具体地，第 $\mathbf { \chi } _ { i }$ 个标量 $\rho _ { i }$ 表示事件 $\pmb { \xi } _ { i }$ 的概率质量．约束(33e)等效表征两个约束，即 $\rho _ { i } \geqslant 0$ 和 $\pi _ { i } \pi _ { i } ^ { \top } / \rho _ { i } = \rho _ { i } \xi _ { i } \pmb { \xi } _ { i } ^ { \top } \preceq \pmb { \sigma } _ { i }$ ．因此，约束(33b)-(33e)表明问题(30)的对偶变量构成了一个离散分布$\{ ( \pmb { \xi } _ { i } , \rho _ { i } ) | i \in \mathcal { I } \}$ ，该分布的期望和协方差分别等于 $\bar { \xi }$ 和小于 $\pmb { \Sigma }$ ．进一步地，约束(33f)还表明该离散分布的支撑集是集合 三．根据上述分析可知，离散分布属于模糊集(14)．基于强对偶性，对偶变量的最优值使得问题(33)取得最大值以及问题(30)的最小值，所以所构建的概率分布是使问题(21)在给定第一阶段方案 $\scriptstyle { \mathbf {  { x } } }$ 之下取得最大值的极限分布.

半正定规划问题隐含的极限分布可以在搜索第一阶段问题最优解方面发挥关键作用．与标准的列和约束生成法类似，可将每一步迭代辨识到的极限分布扩充到第一阶段问题，对第一阶段问题的可行域形成附加的约束，从而得到更接近原问题要求而的解，循环直至得到原问题的最优解.

总体的求解方法如算法1所示．第1行到第1行是主循环，该部分迭代求解混合整数线性规划主问题和半正定规划子问题．第1行所示的主问题采用极限分布和 $Q ( { \pmb x } , { \pmb \xi } )$ 的原问题形式来生成原割平面．每个主循环中，需要求解多个半正定规划子问题，直到约束(22b)满足，即 $R ( H ^ { \star } , h ^ { \star } , h _ { 0 } ^ { \star } ) \geqslant 0$ 需要注意半正定规划中的 $h _ { 0 i } ( { \pmb u } _ { i } )$ 采用了当前第一阶段问题的最优解 $\scriptstyle \mathbf { { \mathit { x } } } _ { K }$ ．在第1行，调用了交替优化算法来求解双凸问题(31)，该算法轮流地固定 $\{ \lambda , \mu , \nu \}$ 来求解二次规划问题，以及固定 $\pmb { \xi }$ 来求解线性规划问题 [Wei et al.(2016),Zheng et al.(2020)]．交替优化算法是求解双凸规划问题的局部最优算法，本文采用多个初始解来保证算法所得解的质量．我们仔细校验了交替优化算法的性能，该算法求解本文的双凸规划问题得到的解的最优性与内点法求解器 IPOPT 相比是具有竞争力的，而在计算效率方面则显著优于IPOPT.尽管算法1包含了启发式过程（即交替优化算法)，在算例测试中算法1的收敛性仍然是非常优良的，且其最终可以得到高质量的开停机方案，

# 算法1分布鲁棒机组组合问题的总体求解方法

0：选择收敛容差 $\epsilon$ ；记变量 $x$ 的最优值为 $x$ as $x ^ { \star }$ ；令 $U B = \infty$ ， $L B = - \infty$ ；令 $ I = 1 , \ K = 0$ ：令 $\{ \lambda _ { 1 } , \mu _ { 1 } , \nu _ { 1 } \}$ 为初始顶点.

0:while $U B - L B > \epsilon$ do

0: 利用已有的割平面，求解如下主问题以获得 $\underline { { \boldsymbol { \vartheta } } }$ ， $\{ { \mathrm { M I L P } } \}$

$$
\underline { { \vartheta } } = \operatorname* { m i n } _ { \substack { { \boldsymbol { x } } \in \mathcal { X } , \theta \geqslant - \infty } } { \boldsymbol { c } } _ { I } ^ { \top } \pmb { x } + \theta
$$

$$
\theta \geqslant \sum _ { i = 1 } ^ { I _ { k } } \rho _ { k , i } Q ( { \pmb x } , { \pmb \pi _ { k , i } } / { \rho _ { k , i } } ) k = 1 , . . . , K .
$$

0: repeat

0: 给定 $\scriptstyle { \pmb { x } } _ { K }$ ，求解如下子问题以获得 $\overline { { \vartheta } }$ ， $\{ \mathrm { S D P } \}$

$$
\begin{array} { l } { \displaystyle \overline { { \vartheta } } = c _ { I } ^ { \top } { \boldsymbol x } _ { K } + \operatorname* { m i n } _ { H \succeq 0 , h , h _ { 0 } , u _ { 1 i } , u _ { 2 i } } \mathrm { t r } \left( H ^ { \top } \Theta \right) + h ^ { \top } \bar { \boldsymbol \xi } + h _ { 0 } } \\ { \mathrm { s . t . } \left[ \begin{array} { c } { H } { 1 / 2 h _ { i } ( { \boldsymbol u } _ { i } ) } \\ { 1 / 2 h _ { i } ( { \boldsymbol u } _ { i } ) ^ { \top } \quad h _ { 0 i } ( { \boldsymbol u } _ { i } ) } \end{array} \right] \succeq \mathbf { 0 } : \left[ \begin{array} { c } { { \boldsymbol \sigma } _ { i } \ \boldsymbol { \pi } _ { i } } \\ { \boldsymbol \pi _ { i } ^ { \top } \ \boldsymbol { \rho } _ { i } } \end{array} \right] } \\ { \displaystyle u _ { 1 i } , u _ { 2 i } \geqslant \mathbf { 0 } \quad i = 1 , . . . I _ { K } . } \end{array}
$$

0: if $R ( H ^ { \star } , h ^ { \star } , h _ { 0 } ^ { \star } ) < 0$ then $\{ \mathrm { Q P }$ 和LP迭代}   
0: （204号 $I _ { K } \gets I _ { K } + 1$ ， $\{ \lambda _ { I _ { K } } , \pmb { \mu } _ { I _ { K } } , \pmb { \nu } _ { I _ { K } } \}  \{ \pmb { \lambda } ^ { \star } , \pmb { \mu } ^ { \star } , \pmb { \nu } ^ { \star } \}$   
0: end if   
0: until $R ( H ^ { \star } , h ^ { \star } , h _ { 0 } ^ { \star } ) \geqslant 0$   
0: $( \pi _ { K , i } , \rho _ { K , i } ) \gets ( \pi _ { i } ^ { \star } , \rho _ { i } ^ { \star } ) \ : i = 1 , . . . I _ { K } , \ : U B \gets \overline { { \vartheta } } .$   
0:end while   
0:返回 $\scriptstyle { \pmb { x } } _ { K } . \ = 0$

# 4算例研究

本节开展数值实验来验证风功率预测的条件误差估计器的有效性，以及证明所提出的分布鲁棒机组组合模型及其求解方法的有效性．实验采用了4个修改的 IEEE 标准测试系统．如表1所示，测试系统的节点数量小至6个节点，大至300个节点，其中300节点系统有8个风电场．每个系统的最大风功率占比均达到 $1 5 \%$ ．本文采用的机组组合模型，以及测试系统的完整数据均可以在线获取[Zheng(2020)].

实验中的 MILPs、LPs 和QPs均采用GUROBI8.1求解，SDPs 采用 MOSEK9.1求解．求解器经YALMIP调用．除非特殊说明，混合整数的相对收敛间隙默认设置为 $1 0 ^ { - 4 }$ ，连续优化问题的收敛容差都采用YALMIP的默认值.算法1的 $\epsilon$ 值设置为．所有计算均在一台运行频率为 $3 . 0 0 \mathrm { G H z }$ 、内存为8GB、CPU为Inteli5-8250U的个人计算机上完成.

# 4.1基于Lasso 的估计器的有效性

实验的风功率数据来源于泛加拿大风电并网研究的网站开源数据,https://canwea.ca/wind-integration-study/wind-data/．实验利用了3年的日前预测和实时数据．整个数据集的前一半用于统计，后一半用于

表1测试系统的配置  

<html><body><table><tr><td>系统</td><td>6节点系统</td><td>39节点系统</td><td>118节点系统</td><td>300节点系统</td></tr><tr><td>发电机数量</td><td>4</td><td>10</td><td>54</td><td>69</td></tr><tr><td>风电场数量</td><td>1</td><td>2</td><td>3</td><td>8</td></tr><tr><td>总装机容量（MW）</td><td>630</td><td>7367</td><td>7220</td><td>32678</td></tr><tr><td>风电场装机容量（MW）</td><td>110</td><td>1300</td><td>1274</td><td>5767</td></tr></table></body></html>

![](images/a53e8c3656790a2f56a366eb059aa06362d3ff02fa760e14463169fac859a849.jpg)  
图1风功率预测误差均方根的对比

仿真测试.

我们将本文提出的基于Lasso 的条件误差估计器的实际效果与无偏矩估计器的效果进行对比，后者对风功率预测误差的估计值是历史误差的平均值，即 $\begin{array} { r } { \bar { \pmb { \xi } } = \frac { 1 } { S } \sum _ { s = 1 } ^ { S } \hat { \pmb { \xi } } _ { s } } \end{array}$ ．图1给出了各项预测结果的均方根（RMS）指标，包括日前预测值（记为“原曲线")、经由基于Lasso 的条件误差估计校正后的预测曲线（记为“Lasso”)、经由无偏矩估计校正后的预测曲线（记为“无偏估计”）.

在这个案例中，39节点系统包含了两个650MW的风电场，因此随机向量 $\pmb { \xi }$ 的维度是48.将条件误差的估计值叠加到日前预测值后，实际预测误差的均方根有所降低．均方根最大降低了15.94MW（即功率序列上的第 25个值）．如图1所示，无偏估计器的误差估计值准确的不高，对日前预测起不到精度提升的作用.

由于在计算日前机组组合问题的时候，前一天的日前预测值和实际值大部分是已知的，可以将前一天的日前预测值和实际值作为Lasso 的附加输入．将考虑了附加输入的模型记为Lasso\*．实际测试表明采用Lasso\*之后RMS 会进一步降低．然而，当系统存在多个风电场时，Lasso\*模型的训练会变得比较耗时．例如，在含有8个风电场的案例中，训练数据集 $\hat { \Omega }$ 的规模为 $5 4 8 \times 5 7 6$ （数据集含548个样本，每个样本的维度是 $2 4 \times 8 \times 3$ ）．如果在100个候选的正则化参数 $\lambda$ 中通过2层的交叉检验来选择最佳参数，并将坐标下降算法的迭代数上限设置为 $1 0 ^ { 5 }$ ，则在192个Lasso 模型需要耗费超过2小时来训练每个模型．为了节省训练时间，对于含8个风电场的案例，我们将 $\lambda$ 参数候选值的数量减少到10个，将迭代数的上限降低为 $1 0 ^ { 4 }$ ．通过这一措施，该案例的所有Lasso 模型的训练时间降低到了10个小时，即每个模型耗费大约3分钟，

表2不同方法应用在不同风电场集合上所取得的风功率均方根误差  

<html><body><table><tr><td>风电场数量</td><td>Lasso* Lasso</td><td>无偏估计</td><td>原曲线</td></tr><tr><td>RMS (MW) 1 改进程度</td><td>17.79 18.93 7.56% 1.63%</td><td>19.31 -0.32%</td><td>19.25 1</td></tr><tr><td>RMS (MW) 2 改进程度</td><td>17.91 8.10%</td><td>18.78 19.57 3.62% -0.41%</td><td>19.49 1</td></tr><tr><td>3</td><td>RMS (MW) 18.02 改进程度 8.03%</td><td>18.90 3.54%</td><td>19.67 19.59 -0.40% 1</td></tr><tr><td>RMS (MW) 8 改进</td><td>17.35 17.90 5.89% 2.93%</td><td>18.29 0.81%</td><td>18.44</td></tr></table></body></html>

表2给出了经由Lasso\*、Lasso、无偏矩估计器等模型校正后和原预测值相对应的风功率预测误差的均方根．所有风电场的容量均归算成了100MW.可以看出原预测值的均方根误差约为 $2 0 \%$ 使用基于Lasso 的条件误差估计器进行校正之后，风功率的预测精度最大可以提升 $8 \%$ （Lasso\*），进而可以进一步得到更准确的模糊集．从表2还可以看出，在含8个风电场的案例中Lasso 降低均方根误差的幅度较小，即为了提升训练效率会牺牲校正精度．实际上，Lasso 模型可以离线进行并行训练，所以可以采用更精细的训练方式以获得更高的校正精度.

我们用相对Frobenius 距离来评估协方差矩阵的估计精度.将估计的协方差矩阵记为 $\pmb { \Sigma }$ ,从样本外数据计算得到的协方差矩阵记为 $\pmb { \Sigma } _ { 0 }$ ,则相对 Frobenius 距离的表达式为 $\sqrt { \mathrm { t r } ( ( \boldsymbol { \Sigma } - \boldsymbol { \Sigma } _ { 0 } ) ( \boldsymbol { \Sigma } - \boldsymbol { \Sigma } _ { 0 } ) ^ { \top } ) } / \sqrt { \mathrm { t r } ( \boldsymbol { \Sigma } _ { 0 } \boldsymbol { \Sigma } _ { 0 } ^ { \top } ) } .$ 在 4个案例中，相对 Frobenius 距离的值分别是 $2 9 . 5 2 \%$ 、 $2 8 . 8 1 \%$ 、 $2 9 . 5 2 \%$ 和 $3 1 . 6 6 \%$

# 4.2开停机计划的经济性和鲁棒性

如图2所示，得到一阶矩和二阶矩的估计器之后，对后一半数据集进行仿真模拟．为了更准确模拟两阶段的运行模式（即日前机组组合、日内经济调度），逐日进行仿真．对于数据集中的每一天，基于日前功率预测计算预测误差的条件期望，得到的条件期望和协方差矩阵用于构造模糊集．基于模糊集可以求解分布鲁棒机组组合问题，获取开停机方案．最后，利用当天的实际风功率数据，计算给定开停机方案所对应的真实运行费用.

本文采用了线性的费用函数.弃风和负荷中断的价格分别设置为 $2 0 0 \ S / \mathrm { M W }$ 和1,000\$/MW[Weiet al.(2016)]．为了计及系统调节能力不足带来的高额惩罚费用，将模型的松弛变量的惩罚系数设置为 $5 , 0 0 0 \mathbb { \ S } / \mathrm { M W }$ [Bertsimas et al.(2013)].在实际实验结果中，松弛变量的优化值均为0.

我们将从本文所提的分布鲁棒优化模型（后续记为模型1）得到的运行费用与其他三个模型的费用进行对比，包括：不考虑风功率预测的条件误差和误差相关性的模型2，即模糊集(14)的第二行期望 $\bar { \xi }$ 取0，第三行不考虑；基于数据驱动的随机规划的模型3，该模型使用[Dupacovaet al.(2003)]提出的基于距离的场景缩减算法来从训练数据集（含 548个场景）生成 50个场景1)；文献[Vellosoet al.(2019)]提出的基于数据驱动的鲁棒优化的，该模型的不确定集由历史发电时序数据集的凸包构成，因此不需要整定不确定集参数（如不确定性预算[Bertsimas et al.(2013),Wei et al.(2016),Zhenget al.(2020)]）．这四个模型均为数据驱动的模型4，可以使得对比更加公平．此外，模型运行费用的对比采取了图2所示的逐日仿真框架

![](images/25d26d07d7413005c9afe0fd484fe684c0e5b4a895ecbb89c9cb018a357f58c2.jpg)  
图2数值实验的框架.

为了节省仿真时间，39节点、118节点、300节点系统只考虑了关键输电线路的传输能力约束.尽管目前学术界已经有一些减轻输电线路安全约束带来的计算负担的精细方法，但不失一般性，我们采取了减少建模线路的数量的简单方法．具体地，首先求解一个确定性的安全约束机组组合问题实例，然后从中挑选传输功率最接近输电容量的10条线路，后续仅对这些线路建模．此外，从第 549天和第1096天的所有样本外数据中选出 $2 0 \%$ 的天数进行仿真．感兴趣的读者可以从[Zheng(2020)]了解测试系统配置和仿真实验的更多细节！

表3总结了运行费用．对于每个测试系统：定义了平均费用，表示所有仿真日的平均运行费用;定义了费用差异，表示该模型的每天的费用与4个模型当天平均费用的差异值．因此，平均差异反映了每个模型的费用节省程度、最小差异和最大差异分别反映了每个模型的最大费用节省量和最大费用多消耗量.

从表3可以看出，除了在6节点系统外（在这个系统是模型4具有最小的平均费用）模型1的平均费用是最低的.在118节点系统，模型1的平均费用节省量相比模型4的高达 $1 . 2 0 \%$ ．模型1的最大费用节省量总是最大的，可以高达平均费用的（如模型1在118 节点系统的“最小差异”行所示)；模型1的“最大差异”项也比较小，这意味着其开停机方案在费用方面的鲁棒性更强．总体而言，基于数据驱动的随机规划的模型3的性能是最为平均的，而基于数据驱动的鲁棒优化的模型4 的性能波动较大．所以，按照模型1的思路基于极限分布制定的开停机方案，可以比模型3和模型4更好地平衡运行的经济性和鲁棒性.

# 4.3极限分布的特征及其对开停机计划的影响

在模型1的模糊集利用风功率预测误差的条件期望提升了预测精度，利用协方差矩阵来排除不实际的概率分布．对比模型1和模型2可以发现，分布鲁棒模型得到的优化方案的经济性取决于模

表3运行费用的对比 $\left( \mathrm { k } \Phi \right) ,$   

<html><body><table><tr><td>系统</td><td>费用</td><td>模型1</td><td>模型2</td><td>模型3</td><td>模型4</td></tr><tr><td>6节点系统</td><td>平均费用 平均差异 最小差异 最大差异</td><td>162.87 -0.02 -1.20 0.19</td><td>162.96 0.07 -0.76 0.45</td><td>162.91 0.02 -1.00</td><td>162.83 -0.06 -0.42</td></tr><tr><td>39节点系统</td><td>平均费用 平均差异 最小差异 最大差异</td><td>1,254.28 -5.47 -53.17 0.42</td><td>1,254.72 -5.03 -53.17 0.86</td><td>0.17 1,266.16 6.41 -48.62 14.56</td><td>2.97 1,263.83 4.08 -5.03 154.96</td></tr><tr><td>118节点系统</td><td>平均费用 平均差异 最小差异 最大差异</td><td>1,608.54 -6.97 -84.34 4.19</td><td>1,609.21 -6.30 -83.52 3.92</td><td>1,616.20 0.68 -77.38 9.48</td><td>1,628.11 12.59 -8.30 245.25</td></tr><tr><td>300节点系统</td><td>平均费用 平均差异 最小差异 最大差异</td><td>3,484.28 -9.90 -37.55 0.61</td><td>3,500.02 5.84 -8.43 23.34</td><td>3,496.85 2.68 -8.53 16.75</td><td>3,495.55 1.38 -18.51 24.94</td></tr></table></body></html>

![](images/51c40fa53f69e5d4fa262f4cef66d0413372d1f5df9fd161b1698537000b6ed1.jpg)  
图3考虑条件误差和误差相关性得到的极限分布，

糊集或者极限分布的质量，

如第3.2节所述，子问题对偶变量的最优值可以构造极限分布 $\{ ( \pmb { \xi } _ { i } , \rho _ { i } ) | i \in \mathcal { I } \}$ ，其中 $\pmb { \xi } _ { i }$ 代表第 $\mathbf { \chi } _ { i }$ 个事件， $\rho _ { i }$ 代表该事件的概率．显然，模型1和模型2得到的极限分布是不一样的．我们有必要将这些极限分布进行可视化，以便直观地分析极限分布的形态是如何影响开停机计划的．图3和图4给出了39节点系统某个实例中的极限分布.

![](images/ec76e4e0208eae7c832ff536b935a8b722dc8ee6a4c437e825cd6cb73dab8710.jpg)  
图4不考虑条件误差和误差相关性得到的极限分布.

为了使展示的结果更加简洁清晰，每个图以4个子图的形式给出分布中的概率较高的前8个事件．图中实线代表分布中的事件，线的粗细则表示了该事件概率的大小．图3和图4用带框标记的线画出了（校正后的）日前风功率预测曲线．可以看出模型1的极限分布排除了很多频繁和快速爬坡的风功率场景，因为这些场景会导致较大的协方差．尽管图4的事件是以期望值为中心，由于没有考虑时空关联性，其事件的时空波动过于剧烈．值得注意的是，方差参数是不足以用于对时空波动和关联性进行建模的 [Babaei et al.(2019)]，因此有必要在构建模糊集的时候考虑完整的协方差矩阵.

为了应对风功率的快速爬坡事件，需要多开灵活和昂贵的发电机组，且机组的计划会出现更加频繁的开停机切换．所以，排除这些不实际的极端事件对于降低开停机计划的保守性是尤其关键的在如上所示的39节点系统中，模型1和模型2所得的10台机组的开停机计划如图5所示．可以看出机组4（变量序号从73到96）和机组5（变量序号从97到120）基于模型2是被调用的，且机组5的启停更加频繁．尽管两个模型的开停机方案均不会引发实际运行中的切负荷和弃风，模型2的运行费用是显著高于模型1的（主要是因为额外的空载成本和启停成本）．所以，模型2的开停机方案是过于保守的．这进一步印证了条件误差和协方差信息对分布鲁棒机组组合模型决策质量的重要影响.

# 4.4 计算效率

表4给出了求解每个模型的耗时与迭代次数．对于118节点和 300节点系统，主问题的混合整数收敛间隙设置为 $1 0 ^ { - 3 }$ ．对于300 节点系统，如果运行时间超过2个小时则耗时数据是空的；对于其他系统，如果运行时间超过1个小时则耗时数据是空的．考虑到Lasso模型的训练是可以离线进行的，且不需要每天更新训练，耗时项并不包括训练时间.

对于除模型3之外（模型3是一个MILP 问题，可用求解器一次性求解）的所有模型，均记录了求解所需要的迭代次数，并在耗时数据的后方列出．模型4是容易求解的．使用列和约束生成法求解数据驱动的鲁棒优化模型，所需要的迭代次数均在7次以内，耗时均在3分钟之内．因为考虑了 50个场景，问题规模较大，求解模型3的计算负担稍微高于模型4.模型1和模型2的计算负担明显更大．在大系统的测试案例中，模型1比其他模型需要更多的计算时间．这有两方面的原因:i)半正定规划子问题的规模随着随机向量的维数升高而升高，而目前半正定规划求解器的能力仍比较有限;ˆ）混合整数线性规划主问题的规模随着极限分布不断添加而增大.

![](images/2ad4671086660d5d156e8efa9ecb5490f97c15a835983b884f807ce778105bbe.jpg)  
图539节点系统案例的开停机方案对比.

在 300 节点系统的实例中，需要求解多个大规模的半正定规划问题：由于系统有8个风电场，随机向量的维度是 $1 9 2 \times 1$ ，半正定规划的决策变量由 $2 I$ 个 $1 9 2 \times 1$ 维向量和 $I$ 个 $1 9 3 \times 1 9 3$ 维矩阵组成，其中 $I$ 是当前子问题的序号．虽然理论上半正定规划可在多项式时间内求解，但是当前基于内点法的求解器仍然无法有效处理超大规模的半正定规划问题．因此，为了在合理与可控的时间内（如日前现货市场出清的4小时时间限制），我们将300节点系统的测试案例的子问题顶点数限制在5以内．通过这个设置，子问题将返回一个事件数量不超过5的可行概率分布（不一定是极限分布）．实际计算结果表明，返回的可行概率分布仍然是比较苛刻的分布，且算法1能够收敛到高质量的开停机方案（详见第4.2节的表3）：

这一节也将算法1与其他两个求解方法相对比，即延迟约束生成法和 Benders 方法．文献 [Zhenget al.(2020)]采用延迟约束生成法，在几分钟内成功求解了6节点系统的分布鲁棒机组组合问题，然而该模型的支撑集是无界的，与本文的模型不同．如果使用延迟约束生成法将问题(32)作为混合整数半正定规划直接求解，或者使用 Benders方法，则在6节点系统的案例中算法也无法于1小时内收敛．表格也给出了这两个求解方法在求解时间达到上限时典型的迭代次数．根据表4，算法1在求解两阶段分布鲁棒机组组合问题方面的能力是明显优于其他两个对比方法的，

表4不同模型或者方法的耗时和迭代次数(秒、次)  

<html><body><table><tr><td rowspan="2">系统</td><td colspan="3">模型1</td></tr><tr><td>Algorithm 1</td><td>MISDP</td><td>Benders</td></tr><tr><td>6节点系统</td><td>80.60 (1-5)</td><td>- (41)</td><td>- (40)</td></tr><tr><td>39节点系统</td><td>217.24 (2-5)</td><td>- (17)</td><td>- (7)</td></tr><tr><td>118节点系统</td><td>2348.21 (2-4)</td><td>- (7)</td><td>- (3)</td></tr><tr><td>300节点系统</td><td>5142.60 (2-3)</td><td>- (2)</td><td>- (2)</td></tr><tr><td>系统</td><td>模型2</td><td>模型3</td><td>模型4</td></tr><tr><td>6节点系统</td><td>13.33 (1-4)</td><td>3.34</td><td>8.48 (2-6)</td></tr><tr><td>39节点系统</td><td>44.29 (2-6)</td><td>12.29</td><td>12.96 (2-5)</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>118 节点系统</td><td>1091.62 (2-6)</td><td>163.43</td><td>59.34 (2-7)</td></tr><tr><td>300节点系统</td><td>2111.53 (2-6)</td><td>714.84</td><td>189.33 (2-7)</td></tr></table></body></html>

# 5 结论与讨论

基于Lasso 的条件误差估计器有效提升了风功率预测的精度．对风功率条件预测误差和误差相关性信息的利用，有效地排除了不符合实际情况的风功率概率分布，因此得到的分布鲁棒机组组合模型能够确定更经济和可靠的方案．本文给出的混合整数半正定规划模型是含二阶矩约束和多面体支撑集的分布鲁棒机组组合模型的等价模型，所提出的极限分布生成方法相比已有方法能够更加高效地求解两阶段分布鲁棒机组组合问题．下一步工作将致力于提升二阶矩估计的精度，提出其他类型两阶段分布鲁棒优化问题的求解算法，以及利用半正定规划的特殊结构提升算法效率等方面.

# 参考文献

Qin etal.(2016）QinW,Martinez-AnidoCB,WuH,etal.QuantifyingtheEconomicandGridReliabilityImpactsofmproved Wind Power Forecasting[J].IEEE Transactions on Sustainable Energy, 2016,7(4):1525-1537.   
LoweryandO'Maley(20l2）LoweryC,O'MallyM.ImpactofWindForecast Eror Statistics Upon Unit Commitment[J].IEEE Transactions on Sustainable Energy, 2012,3(4):760-768.   
Delage ad Ye(20lo）DelageE,YeY.Distributionallyrobustoptimizationunder moment uncertainty with applicationtodatadriven problems[J]. Operations Research,2010,58(3):595-612.   
Dupacovaetal.(2003）DupacovaJ,Growe-KuskaN,omischW.Scenarioreductioninstochasticprogramming[J].Math.ro gram.,2003,95(3):493-511.   
Bertsimas etal.(20l1）BertsimasD,BrownDB,Caramanis C.Theoryandaplications ofrobustoptimization[J].SIAReview, 2011, 53(3):464-501.   
Zengand Zhao(20l3）Zeng B,ZhaoL.Solving two-stage robustoptimization problems using acolumn-and-constraint generation method[J]. Operations Research Letter, 2013,41(5):457-461.   
SamaniandAminifar(2019）Samani E,AminifarF.Tri-LevelRobust Investment Planningof DERs in Distribution Networks With AC Constraints[J]. IEEE Transactions on Power Systems, 2019,34(5):3749-3757.   
Zhao and Zeng(20l2）ZhaoL,ZengB.Robustunitcommitment problemwithdemand response and wind energy[M//.In:Proc. IEEE PES Gen.Meeting[C]. New Jersey:IEEE,2012,1-8.   
Bertsimasetal.(20l3)BertsimasD,LitvinovE,SunXA,etal.Adaptiverobustoptimizationforthesecurityconstrainedunit commitment problem[J].IEEE Transactions on Power Systems,2013,28(1):52-63.   
Lorcaad Sun(2016）LorcaA,SunXA.Multistagerobustunitcommitment withdynamicuncertaintysetsandenergystorage[J]. IEEE Transactions on Power Systems,2016,32(3):1678-1688.   
Roldan et al.(2019)Roldan C,Minguez R,Garcia-Bertrand R,et al.Robust transmision network expansion planningunder correlated uncertainty[J]. IEEE Transactions on Power Systems, 20l9,34(3):2071-2082.   
Zhao andGuan(2015）Zhao C,Guan Y.Data-driven stochastic unit commitment for integrating wind generation[J].IEEE Transactions on Power Systems, 2015,31(4):2587-2596.   
Weietal.(2016）WeiW,LiuF,MeiS.DistributionalyobustcooptimizatioofenergyandreservedispatchJ].IEEETrasactions on Sustainable Energy, 2016,7(1):289-300.   
Duanet al.(207）DuanC,JiangL,FangW,etal.Data-drivenafinelyadjustabledistributionallyrobustunitcommitent[J]. IEEE Transactions on Power Systems, 2017, 33(2):1385-1398.   
Xiongetal.(20l7）Xiong P,JrutitijaroenP,SinghC.Adistributionallobustoptimizationmodelfornitcommitmentosidering uncertain wind power generation[J].IEEE Transactions on Power Systems,20l7,32(1):39-49.   
Chenet al.(2018）ChenY,Guo Q,Sun H,etal.Adistributionallrobustoptimization modelforunitcommitment basedon Kullback-Leibler divergence[J]. IEEE Transactions on Power Systems,2018,33(5):5147-5160.   
Zhuet al.(2019）ZhuR,WeiH,BaiX.Wasserstein metricbased distributionallyrobustapproximateframework forunitcommitment[J]. IEEE Transactions on Power Systems,2019,34(4):2991-3001.   
Babaeietal.(20l9)BabaeiS,ZhaoC,FanL.AData-Driven Modelof Virtual Power PlantsinDay-Ahead Unit Commitment[J]. IEEE Transactions on Power Systems,2019, 34(6):5125-5135.   
Zheng et al(2020）Zheng X,Chen H,Xu Y,etal.A mixed-integer SDPsolutionapproach todistributionallyrobustunit commitment with secondorder moment constraints[J].CSEE JournalofPower and Energy Systems,2020,6(2):374-383.   
Bertsimas etal.(20l)Bertsimas D,Doan X V,NatarajanK,etal.Modelsforminimax stochasticlinearoptimizationproblems with risk aversion[J].Mathematics of Operations Research, 2010,35(3):580-602.   
EsfahaniandKuhn(20l8）EsfahaniPM,KuhnD.Data-drivendistributionallyobustoptimizationusing the Wassersteinetric: Performance guarantees and tractable reformulations[J]. Mathematical Programming, 2018,171(1-2):115-166.   
Zheng and Chen(2020）Zheng X,Chen H.Data-driven distributionally robustunitcommitment with Wasserstein metric: Tractable formulation and eficient solution method[J].IEEE Transactions on Power Systems,2020,35(6):4940-4943.   
C6rdovaetal.(2018)Crdova S,Rudnick H,LorcaA,etal.AnEfcientForecasting-Optimization Schemeforthe Intra-Day Unit Commitment Process Under Significant Wind and SolarPower[J].IEEE Transactions on Sustainable Energy,2018, 9(4):1899-1909.   
Cheet al.(2019）CheL,LiuX,ZhuX,etal.Intra-IntervalecurityAsessmentinPowerSystemsWithHigh WindPenetration[J]. IEEE Transactions on Sustainable Energy, 2019,10(4):1890-1903.   
Besa et al.(20l2）BessaRJ,Miranda V,BotterudA,etal.TimeAdaptiveConditional Kernel DensityEstimationfor Wind Power Forecasting[J]. IEEE Transactions on Sustainable Energy, 20l2,3(4):660-669.   
Agoua etal.(2019)Agoua XGGirardR,Kariniotakis G.Probabilistic Models forSpatio-Temporal PhotovoltaicPowerFore casting[J].IEEE Transactions on Sustainable Energy, 2019,10(2):780-789.   
Chenetal.(2016)ChenY,WeiW,LiuF,etal.Distributionallyobusthydro-thermal-windeconomicdispatch[J].ApldEnergy 2016, 173:511-519.   
Shokrzadeh etal.(2014)ShokrzadehS,Jafari Jozani M,BibeauE.WindTurbinePower Curve Modeling UsingAdvancedParametric and Nonparametric Methods[J].IEEE Transactions on Sustainable Energy,2014,5(4):1262-1269.   
Lvetal.(2013）LvJ,Pawlak M,AnnakkageUD.Predictionofthe TransientStabityBoundaryUsingtheLasoJ]IE Transactions on Power Systems,2013,28(1):281-288.   
Friedmanetal(0）FredmanJ,HstieT,HfingH,etal.Pathwsecoordinateptimzation[J].AnnalsofApledttistics, 2007,1(2):302-332.   
Bertsimas and Sethuraman(2oo)Bertsimas DSethuraman J.Moment problemsandsemidefiniteoptimization[M//.In:Handbook of semidefinite programming[C]. Berlin: Springer,20oo. 469-509.   
Freund(2004)FreundR M.Introductiontosemidefiniteprogramming (SDP)[J].Technical Report,Masschusets Instituteof Technology, 2004,8-11.   
Zheng(2020）Zheng X.Data fornumerical experiments[EB/OL].htps://figshare.com/articles/dataset/Test_data_for distributionally_robust__unit__commitment/12630566/1,2020.   
Velosoetal(0l9）VelosoA,treetA,PozoDetal.Twostagerobustunitommitmentforo-optimizedelectricityarkets: An adaptive data-driven approach for scenario-based uncertainty sets[J].

# Addressing the Conditional and Correlated Wind Power Forecast Errors in Unit Commitment by Distributionally Robust

# Optimization

Xiaodong ZHENG $^ { 1 , 2 }$ \*,Kaiping QU $^ { 2 , 3 }$ \*， Jiaqing LV $^ { 4 , 5 }$ , Zhengmao LI3 & Bo ZENG6

1. The Electric Power Research Institute of China Southern Power Grid Co.，Ltd. Guangzhou 510663，China; 2.The School of Electric Power Engineering,South China University of Technology， Guangzhou 510640, China; 3.The School of Electrical and Electronic Engineering,Nanyang Technological University,639798,Singapore; 4.The Departmentof Electrical Engineering，AGH University of Science&Technology,Krakow,Poland; 5.The Department of Electrical & Computer Engineering， University of Manitoba， Winnipeg, Canada; 6.The Department of Industrial Engineering，and the Department of Electrical and Computer Engineering, UniversityofPittsburgh,Pittsburgh15260，USA   
\* Corresponding author. E-mail: eezhengxd@xjtu.edu.cn,13560361373@163.com

AbstractIn this paper,a study ofthe day-ahead unit commitment problem with stochastic wind power generationis presented,which considersconditionaland correlated wind power forecast errors througha distributionally robust optimization approach.Firstly,to capture the characteristics of random wind power forecast errors,the least absolute shrinkage and selection operator(Lasso) is utilized to develop a robust conditional error estimator, whileanunbiased estimator is used to obtain the covariance matrix.The conditional error and the covariance matrix are then used to construct an enhanced ambiguity set. Secondly, we develop an equivalent mixed integer semidefinite programming (MISDP)formulation of the two-stage distributionally robust unit commitment model with a polyhedral support of random variables.Further,to effciently solve this problem,a novel cutting plane algorithm that makes use of the extremaldistributions identifed from the second-stage semidefinite programming (SDP) problems is introduced.Finally,numerical case studies show the advantage of the proposed model in capturing the spatiotemporal correlation in wind power generation,as wellas the economic effciencyand robustness of dispatch decisions.

KeywordsColumn-and-constraint generation,distributionally robust optimization,extremal distribution,spatiotemporal correlation,wind power forecast.