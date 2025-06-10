# 考虑零件功能性削减的多目标拆卸方案决策

王伏林，廖显羲，冯显东，张程栋，冷细元(湖南大学 机械与运载工程学院，长沙 410082)

摘要：为解决零件价值高低界限模糊、废旧产品拆卸深度不合理的问题，提出一种考虑零件功能性削减的产品多目标拆卸方案决策方法。分析零件具体损伤对拆卸工具、方向、约束状态的影响，建立损伤情况下的拆卸信息模型；结合各损伤形式对零件接触面功能性的削减作用，提出一种考量零件在产品中综合重要性的剩余价值排序方法，并由此建立一种动态的拆卸目标件选取模型；面向拆卸过程的经济性，建立包含“价值构成”和“成本构成”的目标函数，采用自适应遗传算法进行序列规划求解，并反向决策零件的回收去向；以受损的减速器为例，获得产品的最佳拆卸深度和各零件的回收去向，充分挖掘零件的利用价值，验证所提方法的经济性与科学性。

关键词：再制造；拆卸深度；回收去向；目标件选取；剩余价值；功能削减 中图分类号：TH165;TP18 doi:10.19734/j.issn.1001-3695.2022.03.0107

Decision-making method for multi-targets disassembly scheme considering functional reduction of parts

Wang Fulin, Liao Xianxi, Feng Xiandong, Zhang Chengdong,Leng Xiyuan (School ofMechanical &Vehicle Engineering,Hunan University,Changsha 41oo82,China)

Abstract:To solve the problems ofblurrd valueboundaryofparts and unreasonable disassembly depth ofte used product. This paper proposed adecision-making methodfor multi-targets disasembly scheme considering the functionalreductionof parts.It established a disassembly information model through analyzing the effect of specificdamageonremoval tools, directions,andrestrainttates.Then,it proposedaresidual valueranking methodbasedonthecomprehensive importanceof parts in the product combined with various damage forms tothe functional reduction of the contact surface of parts,and established a dynamic target parts selectionmodel.Itestablishedanobjective function including "value composition"and "costcomposition"fortheeconomyofthedisassmblyprocess.Then,itusedtheadaptive geneticalgorithmfordisassembly sequence planing,and reverselydetermined therecycling directionof the parts.Finaly,a damaged reducer was studiedas instances toobtainthe optimal disassemblydepthoftheproductandtherecycling directionofeachpart,itfully exploitedthe utilization value of the parts,and verified the economics and scientificity of the proposed method.

Keywords:remanufacturing；disassembly depth；recycling direction；target partsselection;residual value；functional reduction

# 0 引言

机电产品服役过程产生的损伤形式主要包括磨损、腐蚀、变形和断裂，随服役时间持续累积，影响产品的服役寿命。再制造可延长产品的总服役时间，而拆卸可为再制造提供高价值毛坏[1]。纵观废旧产品的增值过程，如图1，拆卸可同时满足再制造和二手市场的零件需求。损伤在一定程度上削减了废旧零件价值，造成拆卸成本的波动；科学高效的拆卸方案可促进高价值零件的提取，有助于产品的再制造。

国内外学者已对拆卸处理过程有了一定深度的研究。在零件价值方面，使用模糊分类的方法将回收的损伤零件分为重用、再制造、材料回收和废弃[2]，或仅根据材料价格定义拆卸收益[3]，体现回收价值；或根据统计的历史数据计算零件失效概率、可再制造加工性、可拆洗性和再制造经济性等因素，以对零件进行价值评价[4,5]；曾艳清等[引入零件价值率的概念，表达零件质量不确定性对拆卸利润的影响；YixiongFeng等[7]将待拆卸模块进行供需满足度和再制造重用程度加权排序，从而决定零件的拆卸价值，一定程度上考虑了需求之外的潜在价值。

![](images/1e9a37ddbe1e466c9d8e3484aea77b0034d0c4453bdd1ea4c93cec85062115e3.jpg)  
图1废旧产品增值过程  
Fig.1The value-added process of used products

多数学者考虑了重用和再制造需求零件的增值，把其他零件均作材料回收利用，对零件本身价值高低的界定缺乏较为严谨的方法，容易造成资源浪费；少数学者利用经验统计的方式估算各零件的折旧价值，具备一定的合理性，但没有针对具体损伤部位进行判断，不能较合理地反映各零件的实际价值差异。高价值零件是产品拆卸的重点，凭经验对零件价值进行人工判定效率较低，主观性较强；需要提升零件价值评定的准确性和效率，确保最大程度地拆卸所有高价值零件。零件价值受其在产品中的重要性影响，零件的几何属性和其在产品中的影响力是评判零件重要性的关键要素[8]。若零件的拓扑结构或几何形状发生变化，则会在一定程度上影响相邻零件的配合面积、尺寸、配合关系和装配精度等[9]，削减零件价值。故本文在此基础上，考虑损伤的影响来量化废旧产品零件的价值。

在拆卸成本方面，已有文献主要对拆卸工具成本和时间成本进行研究。如根据模糊推测、寿命和可靠性评估、连接类型等方式划分零件类别，确定是否使用高成本的破坏性拆卸工具[2,10\~12]；HongyuLiu 等[13]引入零件的拆卸成功率，考虑实际拆卸过程与序列规划产生出入的情况，从而影响拆卸成本；而根据不同连接方式的损坏状况，利用实验获取大量数据，建立拆卸时间的修正模型，具备一定的准确性[14\~16]。

对于拆卸成本的变动，大多数学者仅研究部分因素受损伤影响产生的变化。未全面而详细地考虑零件损伤对拆卸过程的影响，难以确定合适的拆卸深度。考虑接触关系、优先关系、拆卸工具、拆卸方向和拆卸时间，研究损伤对拆卸造成的全面性影响十分必要[17]。考虑到拆卸元素的变动与否只与损伤程度的下限阈值相对应(最轻能导致拆卸元素变动的损伤程度)，随着检测手段的进步和生命周期数据库的逐步完善[1,18\~20]，通过长期的回收拆解数据，可提前预知产品零部件的具体损伤，并在一定的反馈机制上逐步确定使拆卸元素变动的损伤阈值。

对于废旧产品拆卸方案的设计，多数学者研究了随机选定目标件情况下的序列规划方法，并将零件的回收决策作为回收收益的依据，计算拆卸方案的利润[2,21,22]。但受损零部件的几何精度、表面质量和潜在缺陷等难以在拆卸之前预知，无法准确判断零件回收之后的增值收益，故仅需评定受损零件的当前价值。由于拆卸深度一般与目标件数量成正比，部分学者研究了单一回收方式类产品的拆卸方案利润和拆卸深度的关系[23,24]；但对于拥有多种类零部件、多回收处理方式的大型机电产品，为增强企业拆卸效益的可预见性，目标件种类的选取方式更为重要。需建立目标件的选取模型，使拆卸方案利润最大化。此外，据调研可知，现阶段大多数大型机电产品拆解企业的自动化程度不高，企业更注重求解运算结果的切实性，而非运算效率；由于当前大多数序列规划算法均可在一定时间内获得可行的结果[3,25,26]，本文直接选取经典的自适应遗传算法进行序列规划求解，仅为证明拆卸方案制定方法的可行性。

本文基于零件的具体损伤状况和使拆卸元素变动的损伤阈值，构建损伤拆卸信息模型；从零件本身剩余价值出发，考虑待拆配合面属性和零件功能性两方面，量化废旧产品各零件的重要程度并进行排序；考虑零件的现实需求和价值排序，建立一种目标件动态选取模型；以拆卸处理过程的经济性为优化目标，通过自适应遗传算法寻找最佳目标件数量，在确定拆卸深度和拆卸序列的同时获得零件的回收处理方式。最大程度挖掘所有高价值零部件，减少资源浪费。

# 1 损伤拆卸信息模型

# 1.1参数定义

废旧产品的常见损伤形式包括磨损、腐蚀、变形和断裂。损伤到某种程度能显著影响拆卸难度。拆卸难度可看做连接类型的分离难度。过盈连接的拆卸难度受损伤影响主要体现为实际过盈量的减少；其余连接方式中，只要配合面周围介质变化或配合面间结合力变化，均会影响拆卸难度。损伤对拆卸难度的影响方式见表1。

Tab.1Impact of mating surface damage on disassembly   

<html><body><table><tr><td></td><td>损伤形式字母标识fm</td><td>在拆卸中的体现</td></tr><tr><td>磨损</td><td>fi</td><td>过盈配合面间的结合力减小，拆卸难度下降。</td></tr><tr><td>腐蚀</td><td>f</td><td>配合表面及周围介质发生变化，影响连接部位 的分离难度。如截面厚度变薄和局部锈蚀。</td></tr><tr><td>变形</td><td>f</td><td>拉伸变形或弯曲变形，随变形量增大，配合面</td></tr><tr><td>断裂</td><td>f4</td><td>间的结合力减小或增大，拆卸难度变化。 配合直接失效，拆卸难度下降。</td></tr></table></body></html>

结合文献[17]将拆卸元素分为四类，进一步根据拆卸难度可分为若干种变动情况，见表2。由于拆卸时间受拆卸工具和约束状态的影响较复杂，且工人熟练程度对拆卸时间影响差异明显，不能简单进行分类，故本文不将拆卸时间纳入拆卸元素中。

表1配合面损伤对拆卸的影响  
表2拆卸元素的变动情况  
Tab.2Changes of disassembly elements   

<html><body><table><tr><td>名称</td><td>字母标识</td><td>变动值</td><td>变动类型</td></tr><tr><td rowspan="3">拆卸工具</td><td rowspan="3">e1</td><td>0</td><td>需使用破坏性拆卸工具</td></tr><tr><td>1</td><td>可使用人工手动拆卸</td></tr><tr><td>2</td><td>可使用默认拆卸工具</td></tr><tr><td rowspan="3">拆卸方向</td><td rowspan="3">e2</td><td>0</td><td>拆卸方向改变</td></tr><tr><td>1</td><td>若干拆卸方向受限</td></tr><tr><td>2</td><td>拆卸方向不变</td></tr><tr><td rowspan="2">接触约束</td><td rowspan="2">Aij</td><td>0</td><td>不存在功能性接触约束</td></tr><tr><td>1</td><td>存在功能性接触约束</td></tr><tr><td rowspan="2">优先约束</td><td rowspan="2">Bij</td><td>0</td><td>不存在接触优先约束</td></tr><tr><td>1</td><td>存在接触优先约束</td></tr></table></body></html>

# 1.2拆卸元素的变动类型

根据各种损伤类型的单独作用结果，判定是否达到使拆卸元素变动的阈值，建立拆卸工具/方向的损伤关联判断矩阵$\pmb { Q } _ { i }$ ，表达四类损伤 $f _ { m }$ 分别单独作用于零件 $i$ 的相关配合面，使拆卸工具 $\scriptstyle { e _ { 1 } }$ 和拆卸方向 $e _ { 2 }$ 的变动值 $\pmb { g } _ { i }$ 产生变化，如式(1)。每个零件需要选定最合适的拆卸工具和拆卸方向。由于最严重的损伤决定了拆卸元素的变动结果，由表2可知，变动值越小代表损伤越严重。定义零件 $i$ 的拆卸工具/方向变动矩阵${ \bf { \sigma } } _ { G _ { i } }$ ，获取损伤耦合结果，如式(2)，式中 $i$ 代表零件号， $m$ 代表损伤形式。

$$
{ \begin{array} { r l } { f _ { 1 } \ } & { f _ { 2 } \ } \\ { \mathbf { { \boldsymbol { Q } } } _ { i } = { \left[ \begin{array} { l l l l } { g _ { i , 1 1 } } & { g _ { i , 1 2 } } & { g _ { i , 1 3 } } & { g _ { i , 1 4 } } \\ { g _ { i , 2 1 } } & { g _ { i , 2 2 } } & { g _ { i , 2 3 } } & { g _ { i , 2 4 } } \end{array} \right] } \ e _ { 1 } } \end{array} }
$$

$\begin{array} { r } { { \bf { g } } _ { i } = \left\{ \begin{array} { l l } { 1 \dag \array} { \mathbb { E } \dag 0 , } \\ { 2 , } \end{array} \right. } \end{array}$ 拆卸元素e受到损伤 $f _ { m }$ 影响 拆卸元素e不受损伤 $f _ { m }$ 影响

$$
\pmb { G } _ { i } = \left[ \operatorname* { m i n } _ { \operatorname* { m i n } } \pmb { g } _ { i , 1 m } \right] \mathbf { \Pi } _ { e _ { 1 } } ^ { e _ { 1 } }
$$

结合表2，假设已知各损伤程度的下限阈值，分析各拆卸元素的具体变动方式如下。

1)拆卸工具

零件i的拆卸工具 $\scriptstyle { e _ { 1 } }$ 受损伤 $f _ { m }$ 影响产生的变动值 $\scriptstyle { \pmb { g } } _ { i , 1 m } = [ 0$ 1，2]， $m { = } 1$ ，2，3，4。此处 $^ { \cdot } 0 ^ { \cdot }$ 代表严重损伤导致的拆卸难度提高，“1"代表严重损伤导致的拆卸难度降低。如 $\pmb { g } _ { i , 1 m }$ 经$f _ { 2 } ($ (局部锈蚀)或f(弯曲变形)的阈值从"2"转为 $\cdot _ { 0 } \cdot \cdot \$ ， $\pmb { g } _ { i , 1 m }$ 经 $f _ { 1 }$ 、$f _ { 2 }$ (厚度变薄)、 $f _ { 3 }$ (拉伸变形)或 $f _ { 4 }$ 的阈值从"2"转为"1”。

2)拆卸方向

零件 $i$ 的拆卸方向 $e _ { 2 }$ 受损伤 $f _ { m }$ 影响产生的变动值 $\mathbf { \Delta } _ { g _ { i , 2 m } = \lbrack 0 }$ 1，2]， $m { = } 1$ ，2，3，4。假设破坏性拆卸方式不会改变零件的拆卸方向。此处 $" 0 "$ 表示严重损伤导致的装配关系变化，如$\pmb { g } _ { i , 2 m }$ 经 $f _ { 4 }$ 的阈值从"2"转为 $^ { \ \mathrm { {  } } } 0 ^ { \mathrm { { \Rightarrow } } }$ ；“1"表示局部损伤导致的部分拆卸方向受阻，如 $\pmb { g } _ { i , 2 m }$ 经 $f _ { 2 }$ 或 $f _ { 3 }$ 的阈值从"2"转为"1”。

3)接触约束

与前两种拆卸元素类似，接触约束同样受四种损伤形式的影响，定义零件 $i$ 和 $j$ 的接触约束 $A _ { i j }$ 受零件 $i$ 损伤 $f _ { m }$ 产生的变动值 $\scriptstyle A _ { i j , m } = [ 0$ ，1]， $m { = } 1$ ，2，3，4。此处 $\cdot _ { 0 } \cdot { }$ 包含本身不存在接触约束的情况和自身损伤导致的接触面功能性削减(约束解除)。如 $A _ { i j , m }$ 经任一 $f _ { m }$ 的阈值从"1"转为 $\cdot _ { 0 } \cdot \cdot \$ 。

为便于后续对零件价值的计算，建立单方面接触约束矩阵 $\pmb { M } _ { 1 }$ ，其第 $i$ 行代表零件 $i$ 自身的损伤导致与其他零件有无接触约束。与常规接触约束矩阵不同的是 $A _ { i j } { \neq } A _ { j i }$ ，并在损伤耦合情况下选最小的变动值，如式(3)。

$$
M _ { 1 } = { \left[ \begin{array} { l l l l } { A _ { 1 1 } } & { A _ { 1 2 } } & { \cdots } & { A _ { 1 n } } \\ { A _ { 2 1 } } & { A _ { 2 2 } } & { \cdots } & { A _ { 2 n } } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { A _ { n 1 } } & { A _ { n 2 } } & { \cdots } & { A _ { n n } } \end{array} \right] } ;
$$

$$
\ { \cal A } _ { i j } = \left[ \operatorname* { m i n } { \cal A } _ { i j , m } \right] ; i , j \in n
$$

其中， $i$ 和 $j$ 代表相接触的零件， $m$ 代表损伤形式， $n$ 代表零件总数。

4)优先约束

本文优先约束只考虑接触优先关系，定义零件 $i$ 和 $j$ 的优先约束 $\pmb { B } _ { \mathrm { i j } }$ 受四种损伤形式 $f _ { m }$ 的影响产生的变动值 $\pmb { B } _ { i j , m } = [ 0$ 1]， $m { = } 1$ ，2，3，4。“0"包含本身不存在优先约束的情况和损伤导致的功能性削减(约束解除)。可根据拆卸工具和拆卸方向的变动情况进行推断，如当 $g _ { i , 1 4 } { = } 1$ 或 $g _ { i , 2 4 } { = } 0$ 或 $g _ { j , 2 2 } { = } 1$ 或$g _ { j , 2 3 } = 1$ 时(前两种情况表示自身断裂导致的优先约束解除，后两种情况表示与其配合零件的弯曲或锈蚀导致其受限方向上的优先约束解除)， $B _ { i j , m }$ 由"1"转为" $\langle 0 ^ { \dag }$ 。

建立有效优先约束矩阵 $\pmb { M } _ { 2 }$ ，代表零件 $i$ 自身损伤或周围零件损伤导致与其他零件有无原先的优先约束。在损伤耦合情况下选最小的变动值，如式(4)。

$$
\pmb { M } _ { 2 } = ( \pmb { B } _ { i j } ) _ { n \times n } ;
$$

$$
\pmb { { B } } _ { i j } = \left[ \operatorname* { m i n } { \pmb { { B } } _ { i j , m } } \right]
$$

# 2 零件价值计算模型

零件价值体现在回收之后的最大利用程度，可由其在产品中的重要性表达。零件在产品中的重要性可通过属性层和拓扑层表示[8]。分析零件损伤对各指标的影响，量化零件功能重要性。

# 2.1拓扑层指标

1)"度中心性 $\ ' _ { D _ { d , i } }$

“度中心性"表达与零件具有面接触关系的零件总数[8]。零件 $i$ 的损伤可能导致与其具有面接触关系的零件数量减少，本文仅评估零件自身的影响力，默认 $j$ 零件的损伤无法导致i零件的面接触关系减少。由于面接触约束属于接触约束的一类，在此需判断矩阵 $\pmb { M } _ { 1 }$ 第 $i$ 行中的"1"是否是面接触关系，并将不是面接触关系的"1"换成 $\cdot _ { 0 } \cdot \cdot \$ ，建立各零件自身损伤影响下的面接触关系矩阵 $\pmb { M } _ { 3 }$ ，进而将 $\pmb { M } _ { 3 }$ 的第 $i$ 行元素累计，即为零件 $i$ 的"度中心性 $\ ' _ { D d , i }$ ，如式(5)。

$$
M _ { 3 } = \left( m _ { 3 , i j } \right) _ { n \times n } \quad \quad , m _ { 3 , i j } = 0 , 1 ;
$$

$$
D _ { d , i } = \sum _ { j = 1 } ^ { n } m _ { 3 , i j }
$$

2)"接近中心性 $\cdot _ { C _ { d , i } }$

“接近中心性"反映零件 $i$ 在产品中的辐射能力[8]。由于仅评估零件自身影响力的变化，只考虑零件 $i$ 损伤破坏了与其相邻零件 $j$ 的功能传递，导致其与相邻零件 $j$ 的距离变为无穷大，从而经过 $j$ 的所有最短路径需"绕行”，且不考虑路径中其他节点受损的影响。零件 $i$ 的"接近中心性"指标需要获得混合图各节点之间连接关系，以及零件 $i$ 导致的连接关系变动情况。根据矩阵 $M _ { 1 }$ 的约束情况，将第 $i$ 行元素置换到理想的接触约束矩阵中，假设各相邻节点对的距离为1，单节点本身距离为0，约束解除节点之间距离为无穷大，计算零件 $i$ 到各零件的最短距离 $d _ { i j }$ ，建立零件节点距离集合 $M _ { 4 }$ 。零件 $i$ 到其余零件的最短距离之和越小，其辐射能力越强，进而通过式(6)计算各零件的"接近中心性 $\because _ { C _ { d , i } }$ 。

$$
{ \cal M } _ { 4 } = \left\{ \sum _ { j = 1 } ^ { n } d _ { 1 j } , \sum _ { j = 1 } ^ { n } d _ { 2 j } , \cdots , \sum _ { j = 1 } ^ { n } d _ { n j } \right\} ;
$$

$$
C _ { d , i } = \frac { n - 1 } { \sum _ { j = 1 } ^ { n } d _ { i j } }
$$

# 2.2属性层指标

零件的属性层指标包括“接触面数”、“接触表面积”和“接触零件数”[8]。

1)"接触面数 $\boldsymbol { \ " } P _ { d n , i }$

损伤导致零件若干接触关系解除，在 $\pmb { M } _ { 3 }$ 的基础上，判断同一接触面上的接触零件减少量是否使接触面减少，明确存在功能性面接触关系的接触面数量。

2)"接触表面积' $P _ { d r ; i }$

通过 $M _ { 3 }$ 获得与零件 $i$ 有功能性面接触关系的零件，经模型装配关系计算接触表面积。

3)"接触零件数 $\ " P _ { d p , i }$

零件 $i$ 的"接触零件数"可通过 $\pmb { M } _ { 1 }$ 的第 $i$ 行元素累计获得，如式(7)。

$$
P _ { d p , i } = \sum _ { j = 1 } ^ { n } m _ { 1 , i j }
$$

# 2.3 零件价值评价

受损零件经再利用后增值，为描述其拆卸后的价值，当计算零件 $i$ 的价值时，不考虑其余零件指标受损的影响，运用2.1节各指标的计算结果，形成“重要性”评价公式：

拓扑层"重要性"评价公式：

$$
W _ { f t , i } = \omega _ { t 1 } \frac { D _ { d , i } } { \sum _ { j = 1 } ^ { n } D _ { j } } + \omega _ { t 2 } \frac { C _ { d , i } } { \sum _ { j = 1 } ^ { n } C _ { j } }
$$

属性层"重要性"评价公式：

$$
W _ { f s , i } = \omega _ { s 1 } \frac { P _ { d n , i } } { \sum _ { j = 1 } ^ { n } P _ { n , j } } + \omega _ { s 2 } \frac { P _ { d r , i } } { \sum _ { j = 1 } ^ { n } P _ { r , j } } + \omega _ { s 3 } \frac { P _ { d p , i } } { \sum _ { j = 1 } ^ { n } P _ { p , j } }
$$

受损零件的综合“重要性"评价公式：

$$
W _ { f , i } = \omega _ { 1 } \frac { W _ { f s , i } } { \sum _ { j = 1 } ^ { n } W _ { s , j } } + \omega _ { 2 } \frac { W _ { f t , i } } { \sum _ { j = 1 } ^ { n } W _ { t , j } }
$$

其中， $D _ { j } , \ C _ { j }$ ， $P _ { n , j }$ 、 $P _ { r , j }$ 、 $P _ { p , j }$ 是不考虑损伤的指标， $j { = } i$ 时考虑损伤； $\{ \hat { W } _ { s , j }$ 和 $W _ { t , j }$ 是理想“重要性”， $j { = } i$ 时考虑损伤; $\omega _ { t 1 }$ 、$\omega _ { t 2 }$ 、 $\omega _ { s 1 }$ 、 $\omega _ { s 2 }$ 、 $\omega { } _ { s 3 }$ 、 $\omega _ { 1 }$ 、 $\omega _ { 2 }$ 是经证明有效的权重[8]。

零件折损率 $\boldsymbol { \delta } _ { i }$ 表示为受损情况的综合“重要性" $\cdot W _ { f , i }$ 与理想情况的综合“重要性” ${ { \bf { \dot { \rho } } } _ { W _ { i } } }$ (不考虑任何损伤)之比，如式(11)。

$$
\delta _ { i } = \frac { W _ { f , i } } { W _ { i } }
$$

由于零件本身的价值和其在产品中发挥功能所具备的价值不同，当拆卸件单独售卖时，考虑到市场的不完全竞争情况，较为关键或急需的零件单件价格会上涨，普通零件单件价格会下降。用折损率在原基础上的变化率来表示，假设变化率为 $\mu _ { p } { = } 2 0 \%$ ，区分零件是否溢价的因子为 $k _ { p } = \pm 1$ ，溢价为正，否则为负。零件剩余价值计算方法如式(12)：

$$
P _ { i } = P _ { n e w , i } \times \delta _ { i } \times \left( 1 + k _ { p } \mu _ { p } \right)
$$

其中， $P _ { n e w , i }$ 为新品价格。

# 3 拆卸深度的确定方法

# 3.1 目标函数

拆卸过程的经济性是评价拆卸方案的重要指标。设定拆卸处理过程的"价值构成"包括高价值零件价格和其他零件材料回收价格；“成本构成"包括拆卸成本、清洗成本、仓储成本、运输成本和废弃处理成本。清洗成本和运输成本随单个产品拆卸过程的变化较小，在此不考虑；故拆卸处理过程的目标函数定义为式(13)。

$$
\begin{array} { r c l } { { } } & { { } } & { { E _ { d i s } = \omega _ { e 1 } \left( \sum _ { i = 1 } ^ { n } P _ { a i m , i } + \sum _ { i = 1 } ^ { n } P _ { m , i } \right) - } } \\ { { } } & { { } } & { { \omega _ { e 2 } \left( \sum _ { i = 1 } ^ { n } C _ { d i s , i } + \sum _ { i = 1 } ^ { n } C _ { l , i } + k \cdot C _ { p u } \right) } } \end{array}
$$

其中， $P _ { a i m , i }$ 为高价值零件价格， $P _ { m , i }$ 为其他零件的材料回收价格； $C _ { d i s , i }$ 为拆卸成本， $C _ { l , i }$ 为废弃处理成本， $C _ { p u }$ 是关于仓储量的惩罚成本； $k$ 是调整系数，由实际仓储空间决定，用于调整“惩罚成本”； $\omega _ { e 1 }$ 和 $\omega _ { e 2 }$ 为“价值构成"和"成本构成"权重，由专家经验确定。

高价值零件价格由式(12)进行计算；材料回收价格包括已确定只能材料回收处理的零件价格和非目标件的材料回收处理价格，由零件重量和材料市场价决定；拆卸成本综合拆卸工具和拆卸方向的变化次数；目标件的仓储成本属于计划内成本，而由于零件之间的装配关系相互制约，受目标件影响必须拆下的其他零件是计划外成本，即“惩罚成本”，反映序列风险性的大小，由式(14)计算。

$$
C _ { p u } = 1 - { \frac { N _ { a i m s } } { N _ { a l l } } }
$$

其中， $N _ { a i m s }$ 是目标件数量， $N _ { a l l }$ 是所有拆下零件的数量。

# 3.2 序列规划及实例

为了确定最佳的拆卸深度，提出一种动态的目标件选取模型。危害零件必拆，并允许当前具备再制造需求、二手市场需求和其他急需情况的零件纳入原始目标件行列。进而将危害件、需求件以外的其余各零件通过第2章的计算方法进行"重要性"排序，技术和市场条件限制只能进行材料回收的零件除外；依次将排序的前 $m$ 个零件与原始目标件一同作为拆卸目标件，划分方法如图2。运用遗传算法进行多目标的串行拆卸序列规划，寻找使适应度值最大的拆卸深度。

1，2，3, ， $_ { x + 1 }$ ： $x + 2$ 0 x+m, n-2, n-1， n  
危害零件、需求件 将要增加的目标件 受技术和市场条（原始目标件） （价值高低排序） 件限制的零件L 1 /再制造、重用、 废弃处置 材料回收

1)算法基本操作

首先，将零件进行实数编码，运用轮盘赌的方式，以几何可拆卸性基本条件作为约束条件生成初始种群。其次，采用自适应单点交叉操作对亲代染色体进行交叉，以跳出局部最优解；采用考虑零件优先关系的自适应单点变异操作对亲代染色体进行变异，以提高运算速度。最后，若经交叉、变异后的子代优于亲代较差个体，则优胜劣汰形成新种群。如此反复迭代直至适应度达到最优。

零件 $i$ 的几何可拆卸性基本条件：与零件 $i$ 有接触关系的零件均不优先于零件 $i _ { \textup { c } }$ ，根据1.2节论述，表述成式(15)，作为种群生成的基本条件。

$$
\sum _ { j = 1 } ^ { n } { B _ { i j } } = 0
$$

2)实例验证

以文献[8]中的蜗轮蜗杆减速器为例进行分析，结构如图3。包含损伤的拆卸信息如表3。

为判断损伤导致的拆卸元素变动，利用式(1)获得各零件的拆卸工具/方向的损伤关联判断矩阵 $\pmb { Q } _ { i }$ ，进一步利用式(2)求得拆卸工具/方向变动矩阵 $\pmb { G } _ { i }$ ，反映损伤耦合的变动结果。以零件4和22为例，已知零件4的磨损情况未达到拆卸元素的变动阈值，断裂情况达到阈值；零件22的磨损情况达到拆卸工具的阈值。故求得 $\varrho _ { 4 }$ 和 $\varrho _ { 2 2 }$ ， ${ \cal G } _ { 4 }$ 和 $\pmb { G } _ { 2 2 }$

![](images/972b57e39e8b09a25ef4d5c4f95104c91c882a6557911307ac92d27fe33a72ef.jpg)  
图2零件的划分方法Fig.2Parts division method  
图3蜗轮蜗杆减速器模型 Fig.3Worm gear reducer

根据 ${ \pmb G } _ { 4 }$ 和 $\pmb { G } _ { 2 2 }$ 可知，零件4和零件22的拆卸工具由默认工具转为人工手动拆卸，零件4的拆卸方向改变。同理获得其他零件的变动情况如表4。

表3包含损伤的拆卸信息表  
Tab.3Disassembly information including damage   

<html><body><table><tr><td>名称</td><td></td><td>数量 拆卸工具 拆卸方向 材料</td><td></td><td></td><td>损伤及部位</td></tr><tr><td>螺钉I</td><td>4</td><td>扳手I</td><td>-X</td><td>Q235A</td><td>腐蚀、变形</td></tr><tr><td>闷盖I</td><td>1</td><td>人工</td><td>-X</td><td>HT200</td><td>腐蚀</td></tr><tr><td>调心滚子轴承I</td><td>2</td><td>手锤</td><td>-X</td><td></td><td>内圈磨损</td></tr><tr><td>挡油盘I</td><td>2</td><td>钳子</td><td>-X</td><td>45</td><td>磨损、断裂</td></tr><tr><td>闷盖</td><td>1</td><td>人工</td><td>+Z</td><td>HT150</td><td>/</td></tr><tr><td>箱盖</td><td>1</td><td>人工</td><td>+Z</td><td>45</td><td>/</td></tr><tr><td>视孔盖</td><td>1</td><td>人工</td><td>+Z</td><td>Q235A</td><td>/</td></tr><tr><td>通气器</td><td>1</td><td>人工</td><td>+Z</td><td></td><td>/</td></tr><tr><td>启盖螺钉</td><td>2</td><td>扳手I</td><td>+Z</td><td>Q235A</td><td>腐蚀、变形</td></tr><tr><td>螺钉Ⅱ</td><td>4</td><td>扳手I</td><td>+Z</td><td>Q235A</td><td>腐蚀、变形</td></tr><tr><td>螺栓I</td><td>6</td><td>扳手I</td><td>Z</td><td>Q235A</td><td>/</td></tr><tr><td>蜗轮</td><td>1</td><td>专用工具I</td><td>+X</td><td>45</td><td>轮齿磨损、断裂</td></tr><tr><td>键I</td><td>1</td><td>扳手Ⅱ</td><td>+Z</td><td>45</td><td>/</td></tr><tr><td>蜗轮轴</td><td>1</td><td>手锤</td><td>+x、-X</td><td>45</td><td>轴颈磨损</td></tr><tr><td>键I</td><td>1</td><td>扳手Ⅱ</td><td>+Z</td><td>45</td><td>/</td></tr><tr><td>套筒</td><td>1</td><td>人工</td><td>+x</td><td>45</td><td>端面磨损</td></tr><tr><td>毡圈I</td><td>1</td><td>专用工具ⅡI</td><td>+x</td><td>羊毛毡</td><td>/</td></tr><tr><td>透盖I</td><td>1</td><td>人工</td><td>+x</td><td>HT200</td><td>腐蚀</td></tr><tr><td>螺钉II</td><td>4</td><td>扳手I</td><td>+X</td><td>Q235A</td><td>腐蚀、变形</td></tr><tr><td>螺栓Ⅱ</td><td>6</td><td>扳手I</td><td>+y</td><td>Q235A</td><td></td></tr><tr><td>闷盖II</td><td>1</td><td>人工</td><td>+y</td><td>HT200</td><td>腐蚀</td></tr><tr><td>调心滚子轴承ⅡI</td><td>2</td><td>手锤</td><td>+y</td><td></td><td>内圈磨损</td></tr><tr><td>挡油盘ⅡI</td><td>2</td><td>钳子</td><td>+y</td><td>HT100</td><td>磨损、断裂</td></tr><tr><td>箱座</td><td>1</td><td>人工</td><td>+Z</td><td>HT200</td><td></td></tr><tr><td>螺母I</td><td>8</td><td>扳手I</td><td>-Z</td><td>Q235A</td><td>/</td></tr><tr><td>螺母Ⅱ</td><td>4</td><td>扳手I</td><td>-Z</td><td>Q235A</td><td>/</td></tr><tr><td>蜗杆</td><td>1</td><td>专用工具I</td><td>+y、-y</td><td>45</td><td>/</td></tr><tr><td>键ⅢI</td><td>1</td><td>扳手ⅡI</td><td>-y</td><td>45</td><td>/</td></tr><tr><td>毡圈ⅡI</td><td>1</td><td>专用工具ⅡI</td><td>-y</td><td>羊毛毡</td><td>/</td></tr><tr><td>套杯</td><td>1</td><td>人工</td><td>-y</td><td>45</td><td>/</td></tr><tr><td>透盖Ⅱ</td><td>1</td><td>人工</td><td>-y</td><td>45</td><td>腐蚀</td></tr><tr><td>螺栓II</td><td>6</td><td>扳手I</td><td>-y</td><td>Q235A</td><td>/</td></tr><tr><td>油塞</td><td>1</td><td>扳手Ⅱ</td><td></td><td>Q235A</td><td></td></tr></table></body></html>

# 表4拆卸工具/方向变动情况

Tab.4Changes in disassembly tool and disassembly direction   

<html><body><table><tr><td rowspan="2">零件序号</td><td colspan="2">拆卸工具</td><td colspan="2">拆卸方向</td></tr><tr><td>原值</td><td>变值</td><td>原值</td><td>变值</td></tr><tr><td>1</td><td>扳手I</td><td>破坏性</td><td>-X</td><td>/</td></tr><tr><td>3</td><td>手锤</td><td>人工</td><td>-X</td><td>/</td></tr><tr><td>4</td><td>钳子</td><td>人工</td><td>-X</td><td>+Z</td></tr><tr><td>9</td><td>扳手I</td><td>破坏性</td><td>+Z</td><td>/</td></tr><tr><td>10</td><td>扳手I</td><td>破坏性</td><td>+Z</td><td>/</td></tr><tr><td>19</td><td>扳手I</td><td>破坏性</td><td>+X</td><td>/</td></tr><tr><td>22</td><td>手锤</td><td>人工</td><td>+y</td><td>/</td></tr><tr><td>23</td><td>钳子</td><td>人工</td><td>+y</td><td>+Z</td></tr></table></body></html>

对于接触约束，零件4具有磨损和断裂两种损伤，其中断裂程度达到了改变与零件3、12、14、17的功能性接触约束阈值，其变动值 $\scriptstyle A _ { 4 3 , 4 } = 0$ 、 $\scriptstyle A _ { 4 } 1 2 , 4 = 0$ 、 $\scriptstyle A _ { 4 1 4 , 4 } = 0$ 、 $\scriptstyle A _ { 4 1 7 , 4 } = 0$ ；零件22的内圈磨损程度达到与零件27的功能性接触约束阈值，故 $A _ { 2 2 , 2 7 , 1 } = 0$ 。对于优先约束，由于变动矩阵 ${ \pmb G } _ { 4 }$ 中 $g _ { 4 , 1 4 } { = } 1$ ，故优先约束变动值 $B _ { 4 } { \mathrm { ~ } } _ { 3 , 4 } { = } 0$ 。其余零件的相关变动值同理可得，并根据式(3)和(4)转换为 $\pmb { M } _ { 1 }$ 和 $\pmb { M } _ { 2 }$ 矩阵元素的变动结果，见表5。

表5接触约束/优先约束变动结果  

<html><body><table><tr><td>接触约束</td><td>接触约束</td></tr><tr><td>A3 14=0</td><td>A163=0</td></tr><tr><td>A43=0</td><td>A22 27=0</td></tr><tr><td>A4 12=0</td><td>A2321=0</td></tr><tr><td>A4 14=0</td><td>A23 24=0</td></tr><tr><td>A4 17=0</td><td>A23 27=0</td></tr><tr><td>A143=0</td><td></td></tr><tr><td>优先约束</td><td>优先约束</td></tr><tr><td>B43=0</td><td>B23 22=0</td></tr></table></body></html>

由于减速器各零件之间的接触方式均为面接触，故面接触关系矩阵 $\pmb { M } _ { 3 }$ 与 $\pmb { M } _ { 1 }$ 相等，根据式(5)计算各零件的 $D _ { d , i }$ 。接触约束会影响零件之间的距离计算，根据 $M _ { 1 }$ 获取零件节点距离集合 $M _ { 4 }$ ，并运用式(6)计算各零件的 $C _ { d , i }$ 。拓扑层情况如表6。

表6拓扑层变动情况  
Tab.6Changes in the topology layer   

<html><body><table><tr><td rowspan="2">零件序号</td><td colspan="2">Ddi</td><td colspan="2">Cd.i</td></tr><tr><td>理想值</td><td>变动值</td><td>理想值</td><td>变动值</td></tr><tr><td>3</td><td>6</td><td>5</td><td>0.492</td><td>0.471</td></tr><tr><td>4</td><td>4</td><td>0</td><td>0.390</td><td>0.003</td></tr><tr><td>14</td><td>7</td><td>6</td><td>0.405</td><td>0.327</td></tr><tr><td>16</td><td>2</td><td>1</td><td>0.364</td><td>0.248</td></tr><tr><td>22</td><td>2</td><td>1</td><td>0.432</td><td>0.376</td></tr><tr><td>23</td><td>3</td><td>0</td><td>0.438</td><td>0.003</td></tr></table></body></html>

零件4与相邻零件的原接触面总数为3，由于其发生断裂损伤，根据表5可知其所有功能性接触约束均失效，推断其不存在具有功能性面接触关系的接触面，故其“接触面数 $\stackrel { , } { p _ { d n , 4 } = 0 }$ ，同时"接触表面积 $p _ { d r , 4 } { = } 0$ ，“接触零件数 $\stackrel { , } { p _ { d p , 4 } = 0 }$ 零件22与相邻零件的原接触面总数为2，由于其发生内圈磨损，“接触面数 $\stackrel { , } { p _ { d n , 2 2 } } = 1$ ，“接触表面积"由模型数据除去失效的接触约束面面积，“接触零件数"由式(7)计算。其余零件的判断方式类似，零件属性层的情况如表7。

由式(8)\~(12)计算零件综合重要性，并进行排序，受损零件的排序变化情况如表8，可见损伤导致零件在产品中的重要性降低。

# 表7属性层变动情况

Tab.7Changes in the attribute layer   

<html><body><table><tr><td rowspan="2">零件序号</td><td colspan="2">Pdn,i</td><td colspan="2">Pdri</td><td colspan="2">Pdp.i</td></tr><tr><td>原值</td><td>变动</td><td>原值</td><td>变动</td><td>原值</td><td>变动</td></tr><tr><td>3</td><td>2</td><td>1</td><td>43360</td><td>28907</td><td>6</td><td>5</td></tr><tr><td>4</td><td>3</td><td>0</td><td>30489</td><td>0</td><td>4</td><td>0</td></tr><tr><td>14</td><td>7</td><td>6</td><td>121541</td><td>107088</td><td>7</td><td>6</td></tr><tr><td>16</td><td>3</td><td>1</td><td>12639</td><td>10111</td><td>2</td><td>1</td></tr><tr><td>22</td><td>2</td><td>1</td><td>43360</td><td>28907</td><td>2</td><td>1</td></tr><tr><td>23</td><td>3</td><td>0</td><td>21667</td><td>0</td><td>3</td><td>0</td></tr></table></body></html>

表8损伤零件综合重要性排序变化

Tab.5Variation results for contact and priority constraints   
Tab.8Changes in comprehensive importance ranking of damaged parts   

<html><body><table><tr><td>零件序号</td><td>零件名称</td><td>原始排序编号</td><td>受损排序编号</td></tr><tr><td>14</td><td>蜗轮轴</td><td>4</td><td>4</td></tr><tr><td>3</td><td>调心滚子轴承I</td><td>5</td><td>7</td></tr><tr><td>22</td><td>调心滚子轴承ⅡI</td><td>12</td><td>23</td></tr><tr><td>16</td><td>套筒</td><td>25</td><td>28</td></tr><tr><td>4</td><td>挡油盘I</td><td>10</td><td>32</td></tr><tr><td>23</td><td>挡油盘ⅡI</td><td>12</td><td>33</td></tr></table></body></html>

根据表3\~表8的拆卸信息，建立多目标序列规划模型，寻找最佳拆卸深度。设定需求件(原始目标件)为27和30；由于技术条件(无法修复)和市场条件(价值太低)等限制，部分零件只作材料回收处理，故将难以修复的零件和连接件汇总：1、4、9、10、11、12、13、15、16、17、19、20、23、25、26、28、29、32不纳入目标件行列；减速器不含危害零件，废弃处理成本为0；根据运算过程设置调整系数k，使“惩罚成本”与拆卸成本的数量级相对应，体现“惩罚成本”的重要性。

以重要则优先的原则逐次增加目标件个数，每增加一个目标件进行一次寻优。运用matlab软件计算，适应度和成本随目标件个数的变化趋势如图4。提取前六次的最优序列如表9，目标件数由原始目标件数和每次增加的目标件数组成。

由图4可知，最佳适应度与目标件数量不是简单的线性关系，当刚开始增加目标件时，随着拆卸深度的增加，“成本构成”提高较快，导致适应度稍有下降；当增加的目标件超过2个后，拆卸成本仅在一定范围内波动，在“惩罚成本”的作用下，“成本构成”缓慢降低，适应度值有逐步提升的趋势；根据适应度值的走势可知，增加任何目标零件的最优适应度均超过了只考虑需求件的情况。

![](images/7114185bd348eb79a8f3bb30ac4ee710c13909509e88ddc68c962771ed04ada6.jpg)  
4适应度和成本随目标件数目增加的变化趋势 Fig.4Variation trend of fitness and cost with increasing number of target parts

1)当目标件只包括需求件时，经济性不一定最高；随着目标件的增加，总成本和零件总价值均会有不同程度的变动。适应度值大于原始目标件数对应的适应度值，均为较优的拆卸方案。但考虑到成本波动，应从较优方案中选取可行的方案，企业需根据自身情况进行目标件的选择，同时可自动确定哪些零件仅作为材料回收处理。

2)受减速器装配结构影响，高价值零件在模型中辐射范围较大。由表9可知，当零件14被纳入目标件之后，最优序列的零件数量不再变化，规划结果符合实际情况。

3)由于后续拆卸深度不变，在成本和时间允许的前提下，可对此类产品进行完全拆卸。在实际生产过程中，变动的目标件属于潜在高价值零件，在确定最佳拆卸深度和各零件的回收去向后，企业需制定新增目标件的售卖计划，以保证资源利用的最大化。

表9目标件数量和最优序列的关系  
Tab.9Relationship between target number of parts and optimal sequence   

<html><body><table><tr><td>目标件数</td><td>最优序列</td></tr><tr><td>2</td><td>19-20-21-22-23-25-26-32-33-18-31-30-29-27</td></tr><tr><td>2+1</td><td>19-20-21-22-23-25-26-32-33-18-31-30-29-27-28-1-2-4- 7-8-9-10-11-5</td></tr><tr><td>2+2</td><td>19-20-21-22-23-25-26-32-33-18-31-30-29-27-28-11-7-8- 9-10-1-2-4-5-6-3-16-17-12-13-15-14</td></tr><tr><td>2+3</td><td>1-2-4-7-8-9-10-19-20-21-22-23-25-26-32-33-18-31-30- 29-27-28-6-11-5-3-16-17-12-13-15-14</td></tr><tr><td>2+4</td><td>19-20-21-22-23-25-26-32-33-31-18-30-29-27-28-4-7-8- 9-10-11-1-2-5-6-3-16-17-12-13-15-14</td></tr><tr><td>2+5</td><td>4-7-8-9-10-19-20-21-22-23-25-26-32-33-31-30-29-27- 28-11-1-2-18-5-6-3-16-17-12-13-15-14</td></tr></table></body></html>

# 4 结束语

针对成批废旧产品的拆卸过程变数大、拆卸深度和拆卸方案具有个性化的问题，本文提出了一种考虑零件功能性削减的多目标拆卸方案决策方法。

1)从零件的具体损伤形式出发，分析了拆卸工具、拆卸方向、接触约束和优先约束受不同损伤形式的影响方式，运用损伤关联判断矩阵来判定拆卸工具和方向的变动结果；进一步考虑了零件在产品中的功能性，建立了单方面接触约束矩阵和有效优先约束矩阵，有助于零件的价值计算和序列规划。

2)以零件拓扑层和属性层的综合评价方法，结合单方面接触约束矩阵，对受损零件的综合重要性进行量化，提出了一种考虑零件在产品中重要性的剩余价值排序方法，提升了零件价值评定的科学性。

3)结合零件价值排序提出了一种动态的目标件选取模型并建立了考虑零件价值、拆卸成本、废弃处理成本和仓储惩罚成本的综合评价模型，运用自适应遗传算法对受损的减速器进行实例验证，生成了随目标件数量变化的最佳适应度值，获取到一系列切合实际且节约资源的拆卸方案，同时对零件进行了回收决策。

本文的研究方法可为产品拆卸方案和零部件回收去向的决策提供指导与参考。由于本文研究对象的机械结构较为简单，易将拆卸工具和拆卸方向的变化次数转换为拆卸成本；对于结构较复杂的产品，需预估各零件的拆卸时间，因此后续会考虑研究损伤状态下拆卸时间的计算方式。

# 参考文献：

[1]郑汉东，陈意，李恩重，等．再制造产品服务系统生命周期评价建模 及应用[J]．中国机械工程，2018,29(18):2197-2203.(Zheng Handong,Chen Yi,Li Enzhong,et al.LCA modeling and applications forRPSS[J].China Mechanical Engineering,2018,29(18):2197-2203.)   
[2]郭磊，张秀芬．多重故障驱动的再制造并行拆卸序列规划方法[J]. 浙江大学学报（工学版）,2020,54(11):2233-2246.(Guo Lei, Zhang Xiufen.Remanufacturing parallel disassembly sequence planning

method driven by multiple failures [J]. Journal of Zhejiang University (Engineering Science),2020,54(11):2233-2246.)

[3]朱卓悦，徐志刚，沈卫东，等．基于遗传蝙蝠算法的选择性拆卸序列 规划[J].浙江大学学报(工学版），2018,52(11):2120-2127+2135. (Zhu Zhuoyue,Xu Zhigang,Shen Weidong,et al.Selective-disassembly sequence planning based on genetic-bat algorithm [J]. Journal of Zhejiang University (Engineering Science），2018,52 (11):2120- 2127+2135.)

[4] 陈劭力．基于RFID 的机电产品回收信息语义建模及拆卸决策方法 的研究[D].上海：华东理工大学,2016.(Chen Shaoli.Researches on RFID based semantic modeling and decision-making method for electromechanical product disassembly and recovery [D]. Shanghai: East China University of Science and Technology,2016.)   
[5]Xia Xyuhui, Zhu Huixian,Zhang Zelin,et al.3D-based multiobjective cooperative disassembly sequence planning method for remanufacturing [J]. The International Journal of Advanced Manufacturing Technology, 2020,106:4611-4622.   
[6] 曾艳清，张则强，刘俊琦，等．部分破坏性拆卸线平衡问题建模与优 化[J].信息与控制,2020,49（03):365-376.(Zeng Yanqing,Zhang Zeqiang，Liu Junqi，et al.Modeling and optimization of partial destructive disassembly-line balancing problem [J]. Information and Control,2020,49 (03): 365-376.)   
[7] Feng Yixiong，Zhou Mengchu,Tian Guangdong，et al.Target disassembly sequencing and scheme evaluation for CNC machine tools using improved multiobjective ant colony algorithm and fuzzy integral [J]. IEEE Trans on Systems Man and Cybernetics: Systems,2019,49 (12): 2438-2451.   
[8]郝丽，莫蓉，魏斌斌，等．粗糙集理论在关键功能零件识别中的应用 [J]．哈尔滨工业大学学报,2021,53(02):61-70.(Hao Li,Mo Rong, Wei Binbin,et al.Application ofrough set theory in identification of key functional parts [J].Journal of Harbin Institute of Technology,2021,53 (02): 61-70.)   
[9]Han Zhoupeng,Mo Rong,Chang Zhiyong,et al. Key assembly structure identification in complex mechanical assembly based on multisource information [J].Assembly Automation,2017,37 (2): 208-218.   
[10]陈建，胡俊康，王建勇．基于多因素约束度函数的拆卸序列规划研 究[J]．机电工程,2018,35(11):1145-1151.(Chen Jian,Hu Junkang, Wang Jianyong. Disassembly sequence planning based on multi-factor constraint degree function [J]. Journal of Mechanical & Electrical Engineering,2018,35 (11): 1145-1151.)   
[11]魏伟杰，张华，江志刚，等．零件分类条件下废旧产品拆卸序列多目 标优化[J]．现代制造工程,2018(09):127-133.(WeiWeijie,Zhang Hua,Jiang Zhigang,et al. Multi-objective optimization method for disassembly sequence of used product under the condition of parts classification [J]. Modern Manufacturing Engineering,2018 (09):127- 133.)   
[12] 聂应军，江志刚，王鹏．基于分解矩阵的废旧产品拆卸模型研究[J]. 组合机床与自动化加工技术,2019(06):27-30.(NieYingjun,Jiang Zhigang, Wang Peng.A decomposition matrix based disassembly model for used product [J]. Modular Machine Tool & Automatic Manufacturing Technique,2019 (06): 27-30.)   
[13] Liu Hongyyu, Zhang Linsheng. Optimizing a Disassembly sequence planning with success rates of disassembly operations via a variable neighborhood search algorithm [J].IEEE Access,2021,9:157540- 157549.   
[14]邢宇飞，李景春，张景强．考虑作业空间约束的并行拆卸序列规划 算法[J].计算机辅助设计与图形学学报,2018,30(09):1755-1764. (Xing Yyufei,Li Jingchun，Zhang Jingqiang.Parallel Disassembly Sequence Planning Method Considering Operation Space Constraints [J]. Journal of Computer-Aided Design & Computer Graphics,2018,30 (09): 1755-1764.)   
[15]吴宏伟．基于扩展随机 Petri 网的废旧产品拆解序列优化[D]．吉林 大学,2019.(Wu Hongwei.Optimization of dismantling sequence of waste products based on extended stochastic petri netst [D]. Changchun: Jilin University,2019.)   
[16]朱慧贤．面向再制造的多目标件拆卸序列规划方法[D].武汉科技 大学，2020.(Zhu Huixian．Multi-objective cooperative disassembly sequence planning method for remanufacturingt [D].Wuhan: Wuhan University of Science and Technology,2020.)   
[17]杨得玉，徐志刚，朱建峰，等．考虑产品故障特征的目标选择性拆卸 序列规划[J].哈尔滨工业大学学报，2019,51(07):160-170.(Yang Deyyu,Xu Zhigang,Zhu Jianfeng,et al. Objective selective disassembly sequence planning considered product fault features [J]. Journal of Harbin Institute of Technology,2019,51 (07):160-170.)   
[18]宋守许，邱权，卜建，等．基于疲劳与磨损的曲轴主动再制造时机选 择[J].计算机集成制造系统,2020,26(02):279-287.(Song Shouxyu, Qiu Quan,Bu Jian,et al. Predecisional remanufacturing timing selection of crankshaft based on fatigue and wear [J].Computer Integrated Manufacturing Systems,2020,26 (02):279-287.)   
[19]宋守许，汪志全，蔚辰．基于在线监测的曲轴主动再制造时机识别 [J]．现代制造工程,2020,2020 (08): $7 - 1 2 + 1 9$ .(Song Shouxyu, Wang Zhiquan，Wei Chen.Timing recognition of crankshaft predecisional remanufacturing based on online monitoring [J]. Modern Manufacturing Engineering,2020,2020 (08): 7-12+19.)   
[20]宋小龙，李博，吕彬，等．废弃手机回收处理系统生命周期能耗与碳 足迹分析[J]．中国环境科学，2017,37(06):2393-2400.(Song Xiaolong,Li Bo,Lyu Bin,etal.Life cycle energy use and carbon footprint of waste mobile phone treatment system [J].China Environmental Science,2017,37(06): 2393-2400.)

[21]邓明星，王菊梅，唐秋华，等．基于蚁群算法的选择性拆卸序列规划

研究[J].武汉大学学报(工学版），2018,51(03): $2 5 7 - 2 6 1 + 2 6 7$ (Deng Mingxing,Wang Jumei,Tang Qiuhua,et al. Selective disassembly sequence planning based on ant colony algorithm [J].Engineering Journal of Wuhan University,2018,51 (03): 257-261+267.)   
[22]张秀芬，张树有，伊国栋，等．面向复杂机械产品的目标选择性拆卸 序列规划方法[J]．机械工程学报，2010,46(11):172-178.(Zhang Xiufen, Zhang Shuyou,Yi Guodong,et al. Object selective disassembly sequence planning for complex mechanical products [J].Journal of Mechanical Engineering,2010,46 (11):172-178.)   
[23]郭洪飞，陈志彬，任亚平，等．基于零件回收综合评价的废旧产品拆 解序列与拆解深度集成决策研究[J/OL].机械工程学报,2022:1-11. (2022-02-10)[2022-04-17].http://kns.cnki.net/kcms/detail/11.2187. TH.20220210.1109.028.html.(Guo Hongfei, Chen Zhibin,Ren Yaping, et al.Research on disass-embly sequence and disassembly length integrated decision of end-of-life products based on parts recovery comprehensive evaluation [J/OL]. Journal of Mechanical Enginering, 2022: 1-11．(2022-02-10)[2022-04-17]．http://kns． cnki. net/kcms/detail/11.2187.TH.20220210.1109.028.html.)   
[24] Ramirez FJ,Aledo JA,Gamez JA,et al. Economic modelling of robotic disassembly in end-of-life product recovery for remanufacturing [J]. Computers & Industrial Engineering,2020,142:106339.   
[25]王玉鑫，任帅．基于遗传-粒子群混合优化算法的拆卸序列规划方法 研究[J].机电工程,2021,38(03):337-342.(Wang Yyuxin,Ren Shuai. Disassembly sequence planning method based on hybrid genetic particle swarm optimization algorithm[J].Journal of Mechanical & Electrical Engineering,2021,38 (03): 337-342.)   
[26]尹凤福，杜泽瑞，李林，等．基于双种群遗传算法的废旧智能手机拆 卸序列规划[J]．机械工程学报,2021,57(17):226-235.(Yin Fengfu, Du Zerui,Li Lin,et al.Disassembly Sequence Planning of Used Smartphone Based on Dual-population Genetic Algorithm[J].Journal of Mechanical Engineering,2021,57(17): 226-235.)