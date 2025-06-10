# 基于动态平衡策划下的集装箱堆场箱位分配方案研究

倪敏敏，甚道方

(上海海事大学 物流科学与工程研究院，上海 201306)

摘要：针对集装箱在码头堆存时存在的箱位分配问题，在研究原有多场桥同时作业方案的基础上，提出了多场桥分区域动态平衡策划方案，弥补了原方案中因保证场桥间的安全距离而带来的缺陷。以合理利用堆存空间，提高场桥作业效率为目标，建立数学模型，结合遗传算法对所提方案进行验证。结果表明，分区域动态平衡策划方案能有效减少场桥的无效作业时间，提高场桥的工作效率，并能充分地利用堆场贝位，更好地利用堆场空间。

关键词：箱位分配；分区域动态平衡；遗传算法；场桥调度 中图分类号：U691.3 doi:10.3969/j.issn.1001-3695.2018.01.0069

# Storage space allocation based on dynamic Strategy in container terminal yard

Ni Minmin, Chang Daofang (InstituteofLogistics Science&engineering,Shanghai Maritime University,Shanghai 2Ol306,China)

Abstract:Forthe problemofcontainerallcationstoredincontaineryard,this paper developedadynamicsub-regionbalance planning scheme of multiple yard cranes based on the original multiple yard sub-regional balanced strategy scheme,which madeuptheshortcomingsoftheoriginalschemebecauseoftheconsiderationofthesafedistancewithouteefectiveutilization of the relevant space.With the goal ofusing storage space rationally,and improving working eficiencyof yard cranes,this paperestablishedamathematical model,anditused geneticalgorithm toverify theproposed program.Theresultsshowthat thesubregional dynamicbalance planning schemecaneffectivelyreduce the ineffective working timeof theyardcranes and improve the work efficiency.In addition,it can make full use of the yard belt and make better use of yard space.

Key words: storage space alocation; dynamic balance of yard cranes; genetic algorithm; yard cranes scheduling

# 0 引言

传统的集装箱堆场采用在同一区域存放同类箱组，当采用多场桥协同工作时作业效率低下，已不满足当前大型船舶的作业需求。因此，研究同一箱区多场桥工作时存在的堆存分配问题，对提高堆存作业效率，有着重要的现实意义。

目前，国内外学者对集装箱码头堆场箱位分配问题做了大量研究，Taleb-Ibrahimi12]提出了针对临时箱存储空间分配的策略。但是研究主要针对于分配给船舶的空间大小，并未给出到场箱的具体位置分配；Kim等人[3]基于考虑集装箱在场时间，采用滚动计划建立了混合整数规划（MIP）模型，并结合启发式算法对模型进行优化求解；Chen 等人[4重点研究并优化了集装箱装卸过程的移动距离和各箱区的工作量；刘婵娟等人[51以最小化集卡运输距离和取箱装船过程中贝位内翻箱数最小为目标，建立多目标优化模型，采用yalmip 软件求解；Preston 等人[6,7]优化了码头堆场出口箱位的分配策略，却没有考虑出口集装箱到场的随机性；陶莎等人[8]以最大化集装箱港口效率和顾客满意度为目标，根据出口箱的箱位分配准则，设计了出口箱堆场空间分配的研究模型；周鹏飞等人[9提出了分阶段的调度方法，以减少场桥作业时间，并采用启发式算法来对目标问题进行优化。但是以上模型和算法只解决了集装箱到场后的箱区分配问题，并未给出到场集装箱具体位置分配方法且堆存以单场桥作业为主。

Hu 和魏晨等人[10,I1]针对堆场同一箱区的两端作业(堆存或取出)，考虑双起重机时空同步约束条件，提出了双起重机调度的MIP数学模型来优化作业总完成时间；Luo等人[12]把堆存位置的选择和水平运输车辆协调作业结合起来，建立了MIP模型，以尽量减少船舶停港时间，并运用遗传算法来优化模型，但是其主要针对堆存的卸载过程；Homayouni 等人[13]提出用遗传算法来解决自动化导引小车和堆场装卸平台的综和调度问题，结果表明用遗传算法得出的解相比模拟退火算法更优。以上研究均以堆存位置已知为前提，但现实是场桥的调度和堆存位置

两者相互影响，密不可分。

范厚明等人[14]对堆场箱位分配问题作了研究，并提出了分区域策划方案，场桥作业效率较传统场地规划有所提高。但该方案缺点也较明显：首先，在种群初始化时就将相邻场桥间不满足安全距离的个体剔除，虽然保证了场桥作业时互不干扰，却损害了种群的多样性，进而无法保证其结果是否最优；其次，若初始数据中两侧的贝位已满，货物必须存放到中部贝位，场桥间无法满足静态安全距离，该策略将失去意义，而实际中该情况确实可能存在。

综上所述，现有的研究大多集中在单场桥作业，但对于非单场桥作业的研究则设定已知集装箱堆存位置，且各场桥独立作业，没有涉及场桥间的协同问题。本文将综合研究箱区分配和多场桥调度问题，把堆存位置分为安全区和影响区，安全区场桥直接移动，影响区场桥互相配合保证互不干扰。以获得最小场桥非作业时间为目标，设计分区域动态平衡策划方案，并用遗传算法进行优化求解。

# 1 问题描述

根据码头堆场堆存的既定要求，同一贝位上需要堆放重量、箱型、目的港一致的集装箱，有时同一船舶的集装箱还要求集中放到同一区域，进而提高作业效率。为了加快船舶的离港时间，有时需要配备两个场桥协同作业。而两个场桥一起作业，存在以下问题：a）任务分配不均，致使一个场桥一直工作，另一个场桥却长时间处于空闲状态；b）场桥间彼此干扰，相互影响，造成堆存效率低下；c）任务分配不合理，相邻两个任务距离间隔太远，造成长距离跑位，效率低下。

为了对箱区进行合理分配，均衡场桥间的作业，范厚明等人[14]提出了均衡分配方案。某时刻场桥的移动区间如图1所示。

![](images/68ac68c6e66aca81f2f9b5d58df175e59683867353897942f4f8420d24ca7d72.jpg)  
图1某时刻场桥移动区域

图中，N∈[1,32]保证任意时刻，场桥间互不干扰。但该方案对是否满足安全距离的判断在种群初始化时进行，看的是静态距离，没有考虑实际中两个场桥可以互相配合实现保持动态安全距离。例如种群初始化时，该方案把目标贝位为 $\mathbf { N } { + } \mathbf { l }$ 的货物k $( \mathbf { k } \in [ 1 , 4 9 ] )$ 给了场桥1，同时把目标贝位为 $_ { \mathrm { N + 8 } }$ 的货物$\mathbf { k } { + } \mathbf { l }$ 给场桥2，该方案将因不满足静态安全距离而被排除。但实际中，场桥2可以在 $\textstyle \mathbf { N + 9 }$ 处等待，场桥1作业结束时，场桥2往 $_ { \mathrm { N + 8 } }$ 处移动幷作业，同时场桥1往N处移动，在移动中保证了安全距离。

本文提出了动态平衡分配方案，在场桥移动过程中进行安全距离的判断，通过场桥间的相互配合来保证互不干扰。通过分析范厚明等人的实验结果可知，获得最优方案时两个场桥任务量方差为0，因此对区域进行了重新划分，将区域划分为安全区和影响区，具体方案如图2所示。

![](images/07cc75978f95665ea964925921d64db52fd0de21f1e8f9cf649c304f0470acad.jpg)  
图2动态平衡分配方案

同样，场桥在安全区可以独立作业，在影响区作业时，需要两个场桥间进行状态传递，以便两个场桥配合。通过读取相邻场桥的当前位置以及作业状态，判断是否存在干扰，进而调整场桥运行状态。

![](images/40974512dd69f60d5ae1d58a25ab23bc3adc91e2cb25fa9f43abdc6cff51c35c.jpg)  
图3所示为场桥1的运行流程。   
图3场桥1的运行流程

当场桥1的当前任务目标贝位 $B 1 ( 0 )$ 处于安全区时，场桥1直接跑位并作业；当 $B 1 ( 0 )$ 处于影响区时，通过读取场桥2的当前位置 $B 2 ( 0 )$ 判断是否满足安全距离，若 $B 2 ( 0 ) { - } B 1 ( 0 )$ 大于1（安全距离)，则场桥1直接跑位作业，否则计算出场桥2需要额外移动的距离Temp，当场桥1跑位至B1(O)-Temp 时，读取场桥2当前工作状态：若场桥2已经完成当前任务，场桥1继续跑位至 $B 1 ( 0 )$ 并作业；若场桥2正在作业，等待场桥2完成当前作业后，场桥1移动至 $B 1 ( 0 )$ 并作业，场桥2移动至 $B 2 ( 0 ) { + } T e m p$ （分区时，场桥2在右边工作）进行下一作业任务。

综合考虑堆场分配与场桥工作效率，以减少场桥工作时间为目标设计了MIP数学模型，采用遗传算法，对MIP模型进行分析计算，得到最佳方案。

# 2 模型建立

文中设计了分区域动态平衡策略方案，采用MIP模型进行分析求解，目标是协调场桥作业，减少场桥的无效工作时间。

# 2.1基本假设

模型建立的前提：a）堆场内有足够的集卡来进行集港卸

箱；b）已知集卡到达的时间，集装箱卸货港；c）相邻场桥留有安全距离；d）贝位内预留翻箱位；e）场桥作业的任务总量等于集装箱数。

<html><body><table><tr><td colspan="3">2.2 相关符号意义</td></tr><tr><td rowspan="12">输入 参数</td><td>字符表示</td><td>说明</td></tr><tr><td>B</td><td>贝位总数</td></tr><tr><td>b</td><td>b∈[1,B]，具体的箱区贝位号</td></tr><tr><td>D</td><td>目的港总数</td></tr><tr><td>d</td><td>d ∈[1,D]，具体的目的港号</td></tr><tr><td>N</td><td>任务总数</td></tr><tr><td>n</td><td>n ∈[1,N]，任务编号</td></tr><tr><td>e</td><td>e ∈[1,2]，作业场桥编号,</td></tr><tr><td>e</td><td>另一个作业场桥编号（模型设定为 两个场桥)</td></tr><tr><td>α</td><td>权重系数，使场桥均衡作业</td></tr><tr><td>Cb</td><td>贝位b的容量</td></tr><tr><td>Nb</td><td>贝位b的预留缓存箱位数</td></tr><tr><td>Cd</td><td>目的港d的集装箱在贝位b的初始箱</td></tr><tr><td>l</td><td>量 单位贝位长度</td></tr><tr><td>L</td><td>相邻两个场桥的安全距离</td></tr><tr><td>V</td><td>场桥移动速度</td></tr><tr><td>To</td><td>场桥完成单个装卸任务花费的时间</td></tr><tr><td rowspan="8"></td><td>Qe</td><td>作业场桥e的任务量</td></tr><tr><td>Q</td><td>作业场桥任务量的平均值</td></tr><tr><td>Hi</td><td>场桥e的第i个任务</td></tr><tr><td>Tempe(Hi)</td><td>场桥e进行任务H;的时候，基于场桥 间安全距离考虑，场桥e需要移动的</td></tr><tr><td></td><td>距离 场桥e进行任务Hi的目标位置与场桥 e现有位置不满足安全距离时，场桥</td></tr><tr><td>Te(Hi)</td><td>e从上一位置进入影响区的时间 场桥e进行任务Hi时，等待场桥e完</td></tr><tr><td>Toe(Hi) Tse(Hi)</td><td>成现有任务所用的时间 场桥e的第i个集装箱到达时间</td></tr><tr><td>TRe(Hi) TFe(Hi)</td><td>场桥e到达Hi任务位置的时间 场桥e完成Hi任务时的时间，其中</td></tr><tr><td rowspan="6"></td><td></td><td>TFe(Ho)=0</td></tr><tr><td>Twe(Hi)</td><td>场桥e完成任务Hi过程中，场桥e的 等待时间</td></tr><tr><td>Te(Hi-1 -Hi)</td><td>场桥e从上一个任务处移动到当前任 务处所需的时间</td></tr><tr><td>Be(Hi)</td><td>场桥e的任务Hi所在贝位</td></tr><tr><td>P</td><td>任意t时刻，场桥e所处的贝位</td></tr><tr><td>Xne</td><td>Xne=1 任务n分给场桥e</td></tr></table></body></html>

<html><body><table><tr><td rowspan="3">变量</td><td></td><td>Xne=0</td><td>任务n未分给场桥e</td></tr><tr><td rowspan="2">Yndb</td><td>Yndb = 1</td><td>目的港为d的任务n分给 贝位b</td></tr><tr><td>Yndb = 0</td><td>目的港为d的任务n未分 给贝位b</td></tr></table></body></html>

# 2.3MIP模型

目标函数

$$
\operatorname* { m i n } F { = }  { \hat { \sigma } } f _ { 1 } { + } ( 1 { - }  { \hat { \sigma } } ) f _ { 2 }
$$

$$
f _ { 1 } = \sum _ { e = 1 } ^ { 2 } ( Q _ { e } - \overline { { { Q } } } ) ^ { 2 }
$$

$$
f _ { 2 } = \sum _ { e = 1 } ^ { 2 } \sum _ { i = 1 } ^ { Q _ { e } } T _ { W e } ( H _ { i } ) + \sum _ { e = 1 } ^ { 2 } \sum _ { i = 1 } ^ { Q _ { e } } T _ { e } ( H _ { ( i - 1 ) } , H _ { i } )
$$

约束条件：

$$
\sum _ { e = 1 } ^ { 2 } X _ { n e } = 1
$$

$$
\sum _ { b = 1 } ^ { B } Y _ { n d b } = 1
$$

$$
\sum _ { n = 1 } ^ { N } \sum _ { d = 1 } ^ { D } Y _ { n d b } + N _ { b } + \sum _ { d = 1 } ^ { D } C _ { b d } ^ { 0 } \leq C _ { b }
$$

$$
\sum _ { n = 1 } ^ { N } \sum _ { e = 1 } ^ { 2 } X _ { n e } = \sum _ { n = 1 } ^ { N } \sum _ { d = 1 } ^ { D } \sum _ { b = 1 } ^ { B } Y _ { n d b }
$$

$$
Q _ { e } = \sum _ { n = 1 } ^ { N } X _ { n e }
$$

$$
\overline { { Q } } = \frac { \displaystyle \sum _ { e = 1 } ^ { 2 } Q _ { e } } { 2 }
$$

$$
T e m p _ { \overline { { e } } } ( H _ { i } ) = \operatorname* { m a x } \left\{ L _ { 0 } - ( B _ { \overline { { e } } } ( H _ { i } ) - B _ { e } ( H _ { i } ) ) , 0 \right\}
$$

$$
\begin{array} { r l } & { T _ { e } ( H _ { i } ) = T _ { F e } ( H _ { i - 1 } ) + T _ { e } ( H _ { i - 1 } , H _ { i } ) - \frac { T e m p _ { \bar { e } } ( H _ { i } ) \times l _ { 0 } } { V } } \\ & { T _ { o e } ( H _ { i } ) = \operatorname* { m a x } \{ T _ { F \bar { e } } ( H _ { i } ) - T _ { e } ( H _ { i } ) , 0 \} } \\ & { T _ { R e } ( H _ { i } ) = T _ { F e } ( H _ { i - 1 } ) + T _ { e } ( H _ { i - 1 } , H _ { i } ) + T _ { o e } ( H _ { i } ) } \end{array}
$$

$$
T _ { _ { F e } } ( H _ { i } ) = T _ { _ { 0 } } + \operatorname* { m a x } \left\{ T _ { _ { R e } } ( H _ { i } ) , T _ { _ { S e } } ( H _ { i } ) \right\}
$$

$$
\begin{array} { r } { T _ { _ { W e } } \left( H _ { i } \right) = \operatorname* { m a x } \left\{ T _ { _ { S e } } \left( H _ { i } \right) - T _ { _ { \mathrm { R e } } } \left( H _ { i } \right) , 0 \right\} } \\ { T _ { e } ( H _ { i - 1 } , H _ { i } ) = \frac { \left| B _ { e } \left( H _ { i } \right) - B _ { e } \left( H _ { ( i - 1 ) } \right) \right| \times l _ { 0 } } { V } } \end{array}
$$

$$
\mid P _ { e } ^ { t } - P _ { \overline { { e } } } ^ { t } \mid \geq L _ { 0 }
$$

目标函数中：F表示模型的适应度函数； $f 1$ 表示各场桥任务量的方差； $f 2$ 表示各场桥等待时间与跑位时间。

约束条件中：式（4）表示每个任务只能被执行一次；式（5）表示一个任务对应一个贝位；式（6）表示贝内可堆存的箱位数不能超过贝内容量；式（7）表示两个场桥作业箱量之和等于箱区增加的箱数；式(8)表示作业场桥 $e$ 的任务量；式（9)表示作业场桥任务量的平均值；式（10）表示当场桥e的目标位置与场桥e现有位置不满足安全距离时，场桥e完成作业后需要额外移动的距离；式（11）表示在式（10）的前提下，场桥e到达影响区的时间；式（12）表示在式（10）的前提下，当前场桥e在影响区边缘等待场桥 $\bar { e }$ 完成工作所用时间；式（13）表示场桥e到达任务 $H _ { i }$ 目标位置的时间；式（14）表示场桥 $e$ 完成任务 ${ \bf \nabla } \cdot { \cal H } _ { i }$ 需要的时间；式（15）表示场桥 $\boldsymbol { \mathscr { e } }$ 完成任务 $\cdot H _ { i }$ 时在目标贝位等待的时间；式（16）表示场桥 $e$ 从上一位置移动到当前任务位置所需的时间；式（17）表示任意时刻工作场桥必须满足安全距离。

# 3 模型求解

通过研究集装箱贝位的分配方案，就可以根据集装箱到达港口的时间以及场桥作业具体区域确定场桥调度方案。因此，本文利用遗传算法的定向收敛能力，对模型进行求解，获取最佳方案。

1）染色体编码根据约束条件，染色体编码为集装箱随机选择满足目的港位的贝位号。染色体采用实数编码，长度为集装箱数量，基因值为对应位置的贝位号。例如，把10个集装箱在40个贝位进行分配，采用本模型对应的编码如图4所示，其中场桥作业集装箱序号由各集装箱分配的贝位号决定。

集装箱序号 1 2 3 4 5 6 7 8 9 10  
分配贝位号 12 2 5 20 21 25 32 35 19 15  
场桥序号 1 1 1 1 2 2 2 2 1 1

2）种群初始化在式（4) $\sim$ （7）的约束下，随机生成初始种群。

3）适应度函数采用目标函数的倒数作为适应度函数值，进行后续的选择、交叉、变异操作。

4)选择操作采用轮盘赌进行个体的选取，构成新的种群。并采用优秀个体保留法，将最优秀的个体保留到新一代种群中。

5）交叉操作利用rand函数随机选择两个染色体，并取得交叉点的坐标，把两个交叉点之间的基因进行互换操作，生成新染色体。过程如图5所示。对新的个体进行约束条件检测，不满足约束条件的个体则利用种群初始化的方法产生新的个体进行替换。

染色体1 12 2 5 20 21 25 32 35 19 15   
染色体2 10 3 7 17 33 22 26 14 37 29 交叉点1 交叉点2   
染色体1' 12 2 5 17 33 22 26 35 19 15   
染色体2' 10 3 7 20 21 25 32 14 37 29 ·

6）变异操作利用rand函数取得变异点坐标，如图6所示对该位置进行单点变异。对新的个体进行约束条件检测。若不满足约束条件，则利用种群初始化的方法产生新的个体进行替换。

变异前 10 3 7 17 33 22 26 14 37 29 变异点 变异后 10 3 7 17 33 19 26 14 37 29

7）结束条件当程序运行到1500代时结束。

# 4 算法实现A

初始条件：场桥数为两台（模型中e与 $\overline { { e } }$ 表示两个不同的场桥)；箱区的规模设为40（贝位） $\times 6$ （堆垛） $\times 4$ （堆层)；考虑到实际中的倒箱操作，每个贝位都预留3个缓存箱位，即每个贝位只有21个可用箱位。本次实例中，共有50个装卸任务，为了与均衡区域策略对比，任务详情如表1所示，各贝位信息如表2所示。

表1装卸任务情况  

<html><body><table><tr><td>任务</td><td>到达时刻/min</td><td>卸货港</td><td>任务</td><td>到达时刻/min</td><td>卸货港</td><td>任务</td><td>到达时刻/min</td><td>卸货港</td></tr><tr><td>1</td><td>1</td><td>2</td><td>18</td><td>20</td><td>1</td><td>35</td><td>53</td><td>3</td></tr><tr><td>2</td><td>2</td><td>1</td><td>19</td><td>26</td><td>1</td><td>36</td><td>58</td><td>1</td></tr><tr><td>3</td><td>3</td><td>1</td><td>20</td><td>27</td><td>2</td><td>37</td><td>59</td><td>3</td></tr><tr><td>4</td><td>6</td><td>2</td><td>21</td><td>28</td><td>3</td><td>38</td><td>60</td><td>3</td></tr><tr><td>5</td><td>7</td><td>1</td><td>22</td><td>30</td><td>3</td><td>39</td><td>62</td><td>2</td></tr><tr><td>6</td><td>7</td><td>2</td><td>23</td><td>32</td><td>1</td><td>40</td><td>64</td><td>2</td></tr><tr><td>7</td><td>9</td><td>3</td><td>24</td><td>35</td><td>2</td><td>41</td><td>65</td><td>1</td></tr><tr><td>8</td><td>10</td><td>1</td><td>25</td><td>42</td><td>2</td><td>42</td><td>66</td><td>3</td></tr><tr><td>9</td><td>10</td><td>3</td><td>26</td><td>43</td><td>2</td><td>43</td><td>68</td><td>1</td></tr><tr><td>10</td><td>12</td><td>1</td><td>27</td><td>45</td><td>1</td><td>44</td><td>69</td><td>2</td></tr><tr><td>11</td><td>12</td><td>2</td><td>28</td><td>47</td><td>1</td><td>45</td><td>71</td><td>3</td></tr><tr><td>12</td><td>13</td><td>1</td><td>29</td><td>47</td><td>2</td><td>46</td><td>74</td><td>3</td></tr><tr><td>13</td><td>13</td><td>1</td><td>30</td><td>47</td><td>1</td><td>47</td><td>75</td><td>2</td></tr><tr><td>14</td><td>15</td><td>1</td><td>31</td><td>51</td><td>1</td><td>1 48</td><td>76</td><td>1</td></tr></table></body></html>

表2各贝位信息  

<html><body><table><tr><td></td><td></td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>15</td><td>17</td><td>1</td><td>32</td><td>51</td><td>3</td><td>49</td><td>77</td><td>2</td></tr><tr><td>16</td><td>17</td><td>1</td><td>33</td><td>52</td><td>2</td><td>50</td><td>80</td><td>3</td></tr><tr><td>17</td><td>18</td><td>1</td><td>34</td><td>52</td><td>3</td><td></td><td></td><td></td></tr></table></body></html>

<html><body><table><tr><td>贝位号</td><td>初始箱量</td><td>卸货港</td><td>贝位号</td><td>初始箱量</td><td>卸货港</td><td>贝位号</td><td>初始箱量</td><td>卸货港</td><td>贝位号</td><td>初始箱量</td><td>卸货港</td></tr><tr><td>1</td><td>7</td><td>1</td><td>11</td><td>5</td><td>2</td><td>21</td><td>3</td><td>1</td><td>31</td><td>15</td><td>2</td></tr><tr><td>2</td><td>12</td><td>1</td><td>12</td><td>10</td><td>2</td><td>22</td><td>8</td><td>1</td><td>32</td><td>8</td><td>2</td></tr><tr><td>3</td><td>9</td><td>1</td><td>13</td><td>9</td><td>2</td><td>23</td><td>5</td><td>1</td><td>33</td><td>7</td><td>2</td></tr><tr><td>4</td><td>13</td><td>1</td><td>14</td><td>15</td><td>2</td><td>24</td><td>6</td><td>1</td><td>34</td><td>3</td><td>2</td></tr><tr><td>5</td><td>16</td><td>1</td><td>15</td><td>9</td><td>2</td><td>25</td><td>11</td><td>1</td><td>35</td><td>16</td><td>2</td></tr><tr><td>6</td><td>16</td><td>1</td><td>16</td><td>7</td><td>3</td><td>26</td><td>3</td><td>1</td><td>36</td><td>7</td><td>3</td></tr><tr><td>7</td><td>9</td><td>1</td><td>17</td><td>9</td><td>3</td><td>27</td><td>5</td><td>1</td><td>37</td><td>14</td><td>3</td></tr><tr><td>8</td><td>16</td><td>1</td><td>18</td><td>12</td><td>3</td><td>28</td><td>4</td><td>1</td><td>38</td><td>10</td><td>3</td></tr><tr><td>9</td><td>2</td><td>1</td><td>19</td><td>6</td><td>3</td><td>29</td><td>4</td><td>1</td><td>39</td><td>7</td><td>3</td></tr><tr><td>10</td><td>9</td><td>2</td><td>20</td><td>13</td><td>3</td><td>30</td><td>6</td><td>2</td><td>40</td><td>15</td><td>3</td></tr></table></body></html>

# 4.1算例描述

本算例中，参数作如下初始化： $l 0 { = } 8$ 贝位， $l { = } 7 \mathrm { m }$ ， $V { = } 1 0 0$ $\mathrm { { m } } / \mathrm { { m i n } }$ ， $T 0 { = } 3 \operatorname* { m i n }$ ， $B { = } 4 0$ ， $N { = } 5 0$ ， $B I ( 0 ) { = } 1$ ， $B 2 ( 0 ) { = } 4 0$ ， $\scriptstyle \alpha = 0 . 5$ 。

# 4.2结果分析与比较

在软件MATLABR2014b中完成代码的编写，通过多次实验，为了避免陷入局部最优，把种群规模设定为500，交叉概率设为0.85，变异率设为0.15，迭代次数设为1500，同时对每代中的最优个体进行保留，如图7所示。

![](images/467d322cf57245fba4e259fcffeb6fdef192a7e273f11c084e99975d71cf09e9.jpg)  
图7遗传算法收敛过程

图7中，迭代次数为1294代时，系统最优值为5.77，空闲时间为 $2 . 5 7 \ \mathrm { m i n }$ ，跑位时间为 $7 . 7 7 ~ \mathrm { { m i n } }$ ，本次任务完成时间为 $1 6 0 . 3 4 ~ \mathrm { m i n }$ 。针对该算例，若采用范厚明等人的分区域平衡分配法：在两个区域间空出8个贝位的安全距离，以保证多个场桥工作时互不干扰，在种群初始化时就剔除不满足安全距离的个体。场桥的非工作时间为 $1 7 . 5 2 \mathrm { m i n }$ ,其中等待时间 $6 . 7 4 \mathrm { m i n }$ ，移动时间 $1 0 . 7 8 \mathrm { m i n }$ ；该批任务总用时 $1 6 7 . 5 2 \mathrm { m i n }$ 。具体场桥调度方案如图8所示，场桥的实时行走路径如图9所示。

结合图8的场桥调度图可以看出，两个场桥在各自的区域工作，整体没有出现交叉；除了第3、4号任务，两个场桥间的距离都满足安全工作的要求。

结合图9的场桥实时路径图可以看出，在两个场桥的第3、4任务的位置（20号贝位与27号贝位）

间的距离不满足安全工作要求时，两个场桥出现了自动配合：场桥2在完成3号任务后，为了给场桥1足够的工作空间，自动从27号贝位移动到28号贝位；场桥1在完成3号任务后，自动从20号贝位移动到19号贝位，以便场桥2进行27号贝位任务。全程保证了，两个场桥在实际工作过程中，没有出现场桥间的相互影响或者干扰，互相配合以满足安全距离。

![](images/946603175c2a5cbdd0e304c9d83250930561e416865f257331fdcfb3c53f69f6.jpg)  
图8场桥调度图

![](images/955d144dfa1ae2915e2af85bd2ba6ba68710d7d3d1eebfd28c47d8c986525d5c.jpg)  
图9场桥实时路径图

# 5 算法实现B

为了更进一步展现该策略中两个场桥间的配合在实际中的应用优势。该算例中，货物的到达时间及目标港仍然采用表1的数据，对表2中的初始箱量进行更改，以限制场桥的作业区域，具体如表3所示。

表3改后各贝位信息  

<html><body><table><tr><td>贝位号</td><td>初始箱量</td><td>卸货港</td><td>贝位号</td><td>初始箱量</td><td>卸货港</td><td>贝位号</td><td>初始箱量</td><td>卸货港</td><td>贝位号</td><td>初始箱量</td><td>卸货港</td></tr><tr><td>1</td><td>21</td><td>1</td><td>11</td><td>21</td><td>2</td><td>21</td><td>0</td><td>1</td><td>31</td><td>21</td><td>2</td></tr><tr><td>2</td><td>21</td><td>1</td><td>12</td><td>21</td><td>2</td><td>22</td><td>20</td><td>1</td><td>32</td><td>21</td><td>2</td></tr><tr><td>3</td><td>21</td><td>1</td><td>13</td><td>21</td><td>2</td><td>23</td><td>21</td><td>1</td><td>33</td><td>21</td><td>2</td></tr><tr><td>4</td><td>21</td><td>1</td><td>14</td><td>21</td><td>2</td><td>24</td><td>21</td><td>1</td><td>34</td><td>21</td><td>2</td></tr><tr><td>5</td><td>21</td><td>1</td><td>15</td><td>6</td><td>2</td><td>25</td><td>21</td><td>1</td><td>35</td><td>21</td><td>2</td></tr><tr><td>6</td><td>21</td><td>1</td><td>16</td><td>21</td><td>3</td><td>26</td><td>21</td><td>1</td><td>36</td><td>21</td><td>3</td></tr><tr><td>7</td><td>21</td><td>1</td><td>17</td><td>21</td><td>3</td><td>27</td><td>21</td><td>1</td><td>37</td><td>21</td><td>3</td></tr><tr><td>8</td><td>21</td><td>1</td><td>18</td><td>21</td><td>3</td><td>28</td><td>21</td><td>1</td><td>38</td><td>21</td><td>3</td></tr><tr><td>9</td><td>21</td><td>1</td><td>19</td><td>21</td><td>3</td><td>29</td><td>21</td><td>1</td><td>39</td><td>21</td><td>3</td></tr><tr><td>10</td><td>21</td><td>2</td><td>20</td><td>8</td><td>3</td><td>30</td><td>21</td><td>2</td><td>40</td><td>21</td><td>3</td></tr></table></body></html>

结合表1和3可以发现，目标港为1的货物将集中存放在21号贝位和22号贝位；目标港为2的货物将集中存放在15号贝位；目标港为3的货物将集中存放在20号贝位。根据式(17)可以知道，任意时刻工作场桥间必须满足8个贝位的安全距离，若用范厚明等人[14]的先判断安全距离再工作的策略，本次调度将无法采用两个场桥协同完成。采用文中所提方案运行结果如图10和11所示。

![](images/d276fdaeaef770ad91986fe279eecf1861b50a622711b6a542ed1b83720bcab3.jpg)  
图10场桥调度图

![](images/4e8f2a047f7f74afa564aa28945e6024501788a7b0649846dd9493514ce55993.jpg)  
图11场桥实时运行轨迹

从图10中可以看出，除了初始状态，场桥1和场桥2同一个时刻的目标港都不满足安全距离，无法直接进行作业。从图11可以看出，在场桥1作业时，场桥2会主动远离场桥1以保证互不影响；当场桥1完成作业后主动远离场桥2，同时场桥2到达目标港进行作业。场桥1和2通过相互配合的方式实现安全作业，进而完成本次调度任务。而范厚明等人[14]提出的分区域平衡法在初始化种群时就进行安全距离检测，除了初始状态，场桥1和2同一时刻的目标港都不满足安全距离，将这些解剔除出去后，将无法进行接下去的操作，场桥不会进行动态的调整以满足安全距离的要求，因此分区域平衡法将无法完成本次调度策略的制定。

# 6 结束语

针对多场桥下的集装箱堆场分配问题做了深入研究，考虑到多场桥作业时的安全距离，设计了分区域动态平衡策划方案：将堆场分为两个安全区和一个影响区，通过实时获取其相邻场桥的作业状态，计算最佳运行方式，时刻保证相邻场桥间满足安全距离。采用遗传算法对方案进行算例验证，结果表明，与分区域平衡策划方案相比，在同样的堆场空间中，文中所提方案作业效率更高；且文中所提方案能适应更加复杂的环境，解决多个场桥工作时的干扰问题。但文中还存在一些不足：默认各货物都能准时到达目标贝位，而在实际中到达时间是很难确定的，且未考虑翻箱问题，因此实际中的带有翻箱问题的箱位分配问题和多场桥联合作业调度问题将是未来的研究方向。

# 参考文献：

[1]Teleb-Ibrahimi D C M,Storage space vs.handling work in container terminals [J].Transportation Research B,1993,12(1):13-32.   
[2]Kim K H,Park K T.A note on a dynamic space-allocation method for outbound containers [J].European Journal of Operational Research,2003, 148 (1):92-101.   
[3]Chen Lu,Lu Zhiqiang.The storage location assignment problem for outbound containers in a maritime terminal [J].International Journal of Production Economics,2012,135(1):73-80.   
[4]刘婵娟，胡志华．基于滚动计划的堆场出口箱存储位置分配两阶段模 型[J].上海大学学报：自然科学版，2017，23(5):789-800.   
[5]Preston P,Kozan E.An approach to determinw storage locations of containers at seapor-t terminal[J].Computers &Operations Research,2001, 28 (10): 983-995.   
[6] Bazzazi M, Safaei N.A genetic algorithm to solve the storage space allocation problem in a containerterminal [J].Computers & Industrial Engineering,2009,56(1): 44-52.   
[7]陶莎，胡志华，集装箱堆场出口箱箱位分配的多策略集成优化[J]．大 连海事大学学报，2012(3):59-63.   
[8]周鹏飞，方波．动态环境下集装箱码头堆场出口箱箱位分配建模与算 法研究[J].控制与决策,2011,26(10):1571-1576.   
[9]Hu Zhihua, Sheu JB,Luo JX. Sequencing twin automated stacking cranes in a block at automated container terminal[J]. Transportation Research Part C:Emerging Technologies,2016,69:208-227.   
[10]魏晨，胡志华，高超锋，等．自动化集装箱码头堆场内双起重机调度模 型与算法[J].大连海事大学学报,2015(4):75-89.   
[11] Luo Jiabin,Wu Yue,Mendes AB.Modelling of integrated vehicle sche

duling and container storage problems in unloading process at an automated container terminal [J]. Computers & Industrial Engineering,2O16,94:32- 44.

[12]Homayouni S M,Tang Saihong,Motlagh O.A genetic algorithm for optimization of integrated scheduling of cranes,vehicles,and storage platforms at automated container terminals [J].Journal of Computational and Applied Mathematics,2014,270:545-556.

[13]范厚明，姚茜，马梦知．多场桥分区域平衡策划下的集装箱堆场箱位分配问题[J].控制与决策,2016,31(9):1603-1608.