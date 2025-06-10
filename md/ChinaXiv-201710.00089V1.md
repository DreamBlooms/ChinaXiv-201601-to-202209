# ORC换热设备结构与操作参数多目标同步优化

郭贵奇　罗向龙　许俊俊　陈 颖(广东工业大学材料与能源学院，广州 510006)

摘要随着全球性的能源紧缺和环境问题日益严重，通过充分利用可再生能源和工业余热资源，从而提高能源利用效率是缓解能源和环境问题的重要方式。有机朗肯循环（ORC)是最有应用前景的低品位热能发电技术之一。本文针对 ORC系统建立了结构参数和系统操作参数同步优化的换热设备多目标优化模型，采用 R245fa为工质和板式换热器，以效率最大和比投资成本最小为目标函数。首先分析了单个变量(蒸发压力、冷凝压力、过热度、蒸发器板间距、冷凝器板间距）对系统性能的影响，然后选取了系统的运行参数(蒸发压蒸发压力、冷凝压力、过热度）和换热器的结构参数(蒸发器和冷凝器的板长、板宽、板间距)九个参数为决策变量，利用遗传算法进行ORC换热设备结构与操作参数多目标同步优化，获得多目标优化的 Pareto 最优前沿及对应的最优系统运行参数和最佳换热器结构参数组合。

关键词遗传算法；多目标优化；有机朗肯循环；热力学性能；经济评价中图分类号：TK121 文献标识码：A 文章编号:0253-231X(2017)08-1619-05

# Heat Exchange Equipment Structure and Operation Parameter Multi-Objective Optimization Simultaneously of ORC

GUO Gui-QiLUO Xiang-LongXU Jun-JunCHEN Ying (Guangdong University of Technology Institute of Materials and Energy，Guangzhou 510006,China)

Abstract The decrease in fossil energy reserves and the deterioration in environment have resulted in a strong interest in utilizing renewable heat sources or waste heat for power generation.The organic Rankine cycle (ORC) is a promising method of generating power that utilizes low-enthalpy renewable energy and industrial waste heat.In this paper a multi-objective model is formulated for the simultaneous optimization of component configurations and system operating parameters. The objective functions are the minimization of specific power generation cost and the maximization of the exergy efficiency. A waste heat driven ORC is investigated using the proposed model. R245fa is used as working fluid. The influences of some key parameters on the cycle performance are performed. Then a multi-objective optimization is performed to optimize evaporation pressure,condensation pressure,superheat degree, plate length, plate width and plate spacing. The exergy effciency optimal scheme, economic optimal scheme and the Pare to curve are achieved using genetic algorithm.

Key wordsgenetic algorithm; multi-objective optimization; organic rankine; thermodynamic performance； economic appraisal

# 0引言

随着社会的发展，能源需求量的增长，由资源的过度开发及不当使用造成的日益严重的能源环境问题，成为当今世界人类需要解决的重大课题。通过采用热集成、热回收等技术对中低温余热进行回收利用，可以提高能源综合利用效率，降低能源成本。其中，回收利用中低温余热资源对进一步提升能源利用效率有巨大的潜力[1,2]。有机朗肯循环(ORC）发电系统具有结构设备简单、可靠、余热回收效率较高等特点，是理想的中低温热能回收发电技术[3,4]。ORC系统运行优化和结构优化可以提高ORC的热力学性能和降低成本。ORC的热力学性能由系统运行参数和工质性质决定，而ORC的成本是由组成系统的设备结构和几何参数决定。因此，ORO系统的全局优化应该是系统操作参数和设备的结构、几何参数的综合优化。

由于热源温度较低，低温热源驱动的ORC系统中超过 $8 5 \%$ 以上热源释放的热量需要换热器承担，并且ORC中换热设备的损占总损的 $7 0 \% \sim 9 0 \%$ 左右[5.6]，且在ORC 的初始投资成本中换热设备投资占整个系统投资的 $4 0 \% \sim 9 0 \% ^ { [ 7 , 8 ] }$ 。在能够实现换热要求的情况下，对换热器结构参数进行优化，通过常规的强化传热方法，可以有效提高换热器的性能，减小换热器所需面积，从而降低换热器的成本[9,10]。然而单纯从换热器自身出发的传热过程强化和结构优化设计，得到的再设计工况并不能保证系统运行的综合性能最优。

因此，建立ORC系统操作参数和换热器的同步优化模型是十分重要的。ORC系统中的换热器运行工况受系统的运行参数、运行负荷、及冷热源条件的影响。ORC系统与换热设备集成优化需要考虑在变工况条件下ORC换热设备的优化，具有优化变量多的特点，采用常规的线性规划方法难以进行求解。利用遗传算法在解决非线性多目标优化方面的优势，利用多目标遗传算法给出了Pareto 非劣解前沿[11]。

本文采用了板式换热器的ORC系统，且以ORC系统效率作为热力学目标和比投资成本作为经济学目标，对ORC系统的运行参数（蒸发压力、冷凝压力、过热度）及板式换热器的结构参数 (蒸发器、冷凝器的板长、板宽、板间距)进行同步优化，以期求解最佳的运行参数和换热设备的结构参数。利用多目标遗传算法给出了Pareto非劣解前沿，在此基础上进行决策分析，提供换热器的参考设计工况，为ORC换热设备的优化设计提供参考。1系统描述图1为纯工质ORC系统的 $T \mathrm { - s }$ 图，整个ORC包括膨胀机、冷凝器、工质泵和蒸发器等。ORC工作过程如图1中所示的1-2-3-4-5-6-7-1过程，其中，1-2为工质在膨胀机中的膨胀做功过程；2-4为工质在冷凝器中的定压放热过程；4-5为泵对工质的加压过程；5-7为工质在热回收蒸汽发生器中的定压预热、蒸发和过热过程。

# 2ORC系统的多目标优化模型

# 2.1系统热力学模型

蒸发器中有机工质的理想状态是定压蒸发过程，按照温度的变化情况，采用分段方式进行计算。将蒸发器分为预热段、蒸发段和过热段分段方式见图1。

$$
Q _ { \mathrm { e v a } } = m ( h _ { 1 } - h _ { 5 } )
$$

冷凝器中理想状态下有机工质在冷凝器中是定压冷凝过程，按照温度的变化情况，采用分段方式进行计算。将冷凝器分为预冷段和冷凝段，分段方式见图1。将蒸发器分为预热段、蒸发段和过热段分

段方式见图1。

$$
Q _ { \mathrm { c o n } } = m ( h _ { 2 } - h _ { 4 } )
$$

膨胀机是ORC系统中的动力输出部件，其热力过程见图1。

$$
W _ { \mathrm { t u r } } = m \cdot ( h _ { 1 } - h _ { 2 } )
$$

工质泵是ORC系统中能量消耗部件，其热力过程见图1。

$$
W _ { \mathrm { p u m p } } = m \cdot ( h _ { 5 } - h _ { 4 } )
$$

一般地，就参数优化问题而言，优化模型一般包括三个要素：目标函数 $\operatorname* { m i n } { f ( x ) }$ 、等式约束 $l ( x )$ 和不等式约束 $g ( x )$ ，如式（5）所示：

$$
\left\{ \begin{array} { l } { \mathrm { m i n } \ f _ { 1 } ( ( x ) , f _ { 2 } ( x ) ) \ \mathrm { s . t } } \\ { \quad \ l \left( x \right) = 0 } \\ { \quad \quad g \left( x \right) < 0 } \end{array} \right.
$$

式中， $f _ { 1 } ( x )$ 和 $f _ { 2 } ( x )$ 分别为不同属性的目标函数。

![](images/54c2f5e080ee8cc6fe496639045cc75224eed106e0dbf2a7d59ff9363c5f19dd.jpg)  
图1ORC系统 $T - s$ （204号Fig.1 $T - s$ diagram of ORC system

# 2.1 目标函数

在ORC系统的优化研究中，评价指标是热力系统优化数学模型的目标函数，本文选取合适的评价指标作为目标函数是多目标优化的关键。

# 1)热力学目标

效率：通常的热量平衡和能量转换效率并不能反映出的利用程度，效率用来表示余热资源有效能的利用程度，效率定义为收益与支付的比值：

$$
\eta _ { \mathrm { e x } } = { \frac { W _ { \mathrm { t u r } } - W _ { \mathrm { p u m p } } } { Q _ { \mathrm { e v a } } \cdot \left( 1 - { \frac { T _ { \mathrm { H } } } { T _ { \mathrm { L } } } } \right) } }
$$

2)经济性目标

本文所研究的ORC中的换热设备均采用板式换热器。

比投资成本（Specific investment cost， $S I C$ ：比投资成本定义为建造该系统的总造价与净发电量的比值，表征系统单位发电量所需要的投资成本，表示为：

$$
S I C = \frac { C _ { \mathrm { c o m } } + C _ { \mathrm { l a b o r } } } { W _ { \mathrm { n e t } } }
$$

式中， $C _ { \mathrm { { c o m } } }$ 为总设备购置成本； $C _ { \mathrm { l a b o r } }$ 为人力成本,在缺少资料的时，一般取 $( 0 . 1 { \sim } 0 . 3 ) C _ { \mathrm { c o m } }$

总设备购置成本 $( C _ { \mathrm { c o m } } )$ ：ORC系统的总设备购置成本主要考虑换热设备 $( C _ { \mathrm { H E } } )$ 、工质泵 $( C _ { \mathrm { p u m p } } )$ 和膨胀机 $( C _ { \mathrm { t u r } } )$ 等主要部件的成本[12-13],可以表示为：

$$
C _ { \mathrm { c o m } } = C _ { \mathrm { H E } } + C _ { \mathrm { p u m p } } + C _ { \mathrm { t u r } }
$$

$$
C _ { \mathrm { H E } } = 1 0 , 0 0 0 + 3 2 4 A ^ { 0 . 9 1 }
$$

$$
C _ { \mathrm { p u m p } } = 4 2 2 W _ { \mathrm { p u m p } } ^ { 0 . 7 1 } \left[ 1 . 4 1 + 1 . 4 1 \left( \frac { 1 - . 8 } { 1 - \eta _ { \mathrm { p u p } } } \right) \right]
$$

$$
C _ { \mathrm { t u r } } = 6 0 0 0 W _ { \mathrm { t u r } } ^ { 0 . 7 }
$$

其中，换热设备换热器总换热面积由蒸发器和冷凝器两部分组成，根据热平衡方程计算面积，换热器的面积计算公式如下，

$$
A = \frac { Q _ { \mathrm { e v a } } } { U _ { \mathrm { e v a } } \mathrm { T _ { e v a } } } + \frac { Q _ { \mathrm { c o n } } } { U _ { \mathrm { c o n } } \mathrm { T _ { c o n } } }
$$

$$
U _ { \mathrm { e v a } } = \left( \frac { 1 } { h _ { \mathrm { h o t } } } + \frac { \delta } { \lambda } + \frac { 1 } { h _ { \mathrm { f l u i d } } } \right) ^ { - 1 }
$$

$$
U _ { \mathrm { c o n } } = \left( \frac { 1 } { h _ { \mathrm { c o l d } } } + \frac { \delta } { \lambda } + \frac { 1 } { h _ { \mathrm { f l u i d } } } \right) ^ { - 1 }
$$

# 2.2约束条件

该多目标优化模型中的约束条件包括不等式约束和等式约束。其中，各变量的变化范围界限、冷源流体温度匹配关系共同组成了该问题的不等式约束；模型中各种设备的质量、能量平衡方程以及工质的物性方程共同组成了该多目标优化问题的等式约束。

# 2.3决策变量

本文将ORC系统中板式换热器(蒸发器、冷凝器)的结构参数板长 $L$ 、板宽 $W$ 、通道间距 $b$ 和ORC系统操作参数系统蒸发压力 $P _ { \mathrm { { e v a } } }$ 、冷凝压力 $P _ { \mathrm { c o n } }$ 、循环过热度 $T _ { \mathrm { s u p } }$ 作为多目标优化的决策变量。其中，将蒸发器和冷凝器与热源和冷源的夹点做相等固定处理，减少优化变量，便于优化求解。

# 3案例分析

对以压力 $0 . 8 \ \mathrm { M P a }$ 、 $1 5 0 ^ { \circ } \mathrm { C }$ 热水为热源，温度$\mathrm { 1 5 ^ { \circ } C }$ 冷水为冷源，R245fa为工质的ORC系统的效率和比投资成本多目进行优化设计。首先，分别选取影响系统热力学性能的系统运行参数 (蒸发压力$P _ { \mathrm { { e v a } } }$ 、冷凝压力 $P _ { \mathrm { c o n } }$ 、过热度 $T _ { \mathrm { s u p } } \mathrm { \# . }$ ）和影响投资成本的板式换热器结构参数 (蒸发器板间距 $b _ { \mathrm { { e v a } } }$ 、冷凝器板间距 $b _ { \mathrm { c o n } } \overset { \cdot } { _ { } }$ ）为单独的决策变量，进行ORC系统的多目标优化，研究单独决策变量对系统性能的影响。然后，以系统的运行参数 $( P _ { \mathrm { e v a } } , P _ { \mathrm { c o n } \setminus T _ { \mathrm { s u p } } } )$ 和换热器结构参数 (蒸发器板宽 $W _ { \mathrm { e v a } }$ 、蒸发器板长 $L _ { \mathrm { e v a } }$ 、 $b _ { \mathrm { { e v a } } }$ 、冷凝器板宽 $W _ { \mathrm { c o n } }$ 、冷凝器板长 $L _ { \mathrm { c o n } }$ 、 $b _ { \mathrm { c o n } } \mathrm { , }$ )九个关键参数同时作为决策变量，进行ORC系统的多目标优化。

# 3.1单个决策变量对评价目标的影响

# 3.1.1系统运行参数对评价目标的影响

图 $2 { \sim } 4$ 分别给出了在其他参数固定的条件下，蒸发压力 $P _ { \mathrm { { e v a } } }$ 、冷凝压力 $P _ { \mathrm { c o n } }$ 、过热度 $T _ { \mathrm { s u p } }$ 对系统性能系统效率和系统比投资成本的影响关系。系统效率随着蒸发压力增大而增大 $1 6 \%$ (图2)，随着冷凝压力的增大而减小 $3 9 . 4 \%$ (图3)，受过热度影响不大增加 $0 . 5 \%$ (图4)。系统比投资成本随着蒸发压力和冷

![](images/d32fcda4bd2b55a5b3467caf4d6a70eb5334bce14eb15dd33f8c73d073c38c3a.jpg)  
图2蒸发压力对系统性能的影响  
Fig.2 The influence of evaporation pressure on cycle performance   
图3冷凝压力对系统性能的影响 Fig.3 The influence of condensation pressure on cycle performance

9000 42 Peva=1.5 Tsup=1 Weva=0.5 8500 Leva=0.15 beva=0.002 Wcon=0.5 40 38 8000 Lcon=0.15 bcon=0.002 36   
7500 34 -SIC 32%   
/CCS nex 30 xu 6500 28 6000 26 5500 24 22 0.20 0.25 0.30 0.35 0.40 0.45 0.50 Pcon/MPa

凝压力的增大而增大 $4 \% \sim 5 4 \%$ (图2、3)，随过热度增大而减小 $1 . 8 \%$ (图4)。

![](images/202876e8826743ea275f8331242d68fdb155a3f8ef3cd6d6fea91de8b1778687.jpg)  
图4过热度对系统性能的影响

![](images/ed4fd94dbbc317cbdba8296ad22b61e26f89ce0e610d256fa5873dfc9a4c8b70.jpg)  
Fig.4 The influence of superheat degree on cycle performance   
图5蒸发器换热板板片间距对系统性能的影响Fig.5 The influence of evaporator plate space on cycle

# 3.1.2换热器结构参数对评价目标的影响

由于换热器结构参数对ORC 系统的影响是通过压降和总传热系统这两个参数间接作用的，因此仅以换热器的板片间距为代表来分析换热设备结构参数对ORC系统性能的影响。图5，6分别给出了蒸发器和冷凝器换热板板片间距对系统性能的影响。板片间距对系统性能的影响分析表明，两器板间距增大系统比投资成本增加 $3 \% \sim 1 0 \%$ ，但对于循环热力性能改善极小，仅有 $0 . 2 6 \%$ 左右。

# 3.2多目标优化

使用MATLAB(2014b）自带的基于遗传算法的多目标求解工具箱（GaMultiObj）对该模型进行求解。根据问题的复杂程度和规模，多目标遗传算法计算参数确定如下表1，下表2给出了各决策变量的取值范围和多目标遗传算法进化参数。

![](images/34cf03180578d9a604ec2849d7caa17a86731f84f61d6949529c14fba6f0b78b.jpg)  
图6冷凝器换热板板片间距图对系统性能的影响Fig.6 The influence of condenser plate space on cycle

图7给出了ORC的多目标优化求解Pareto解。多目标求解得到的非劣解数目众多，决策者需要对系统效率和系统比投资成本的具体看重程度。显然，由于目标函数的相悖性，要想得到系统效率最大且系统比投资成本最小的解 (即图 7中 A 点)，是不可能的。此处，距离A点距离最小的Pareto非劣解 (即图7中B点)通过最小距离法求得。事实上，在缺乏具体的系统实施参数的情况下，B点一般是决策者经常选取的非劣解，它同时较好考虑了系统效率和系统比投资成本的大小，此时系统的比投资成本和系统效率分别为 $5 5 8 8 . 7 \ : \mathrm { \in / k W }$ 和 $4 2 . 9 5 \%$ 。另外，C点为系统效率最大 $4 3 . 7 9 \%$ ，D点的系统比投资成本最小 $5 4 6 3 . 6 \ : \mathrm { { ‰ } }$ 。可以看到，Pareto 前沿上的非劣解越向两端延伸，其距离理想点A的距离越大，其实也就是越单一目标的权重越来越重，不同属性指标的综合评价越来越弱。对应地，B、C、D 非劣解对应的决策变量的数值解如表3所示。表3给出了设计参数、系统效率最大、系统比投资成本最小和多目标优化条件下系统决策变量的取值。表3与图7相结合，很好地反映了单目标优化和多目标优化的区别与改进。多目标优化中，虽然效率较单目标优化是减小的，但是较系统比投资成本却有下降；

# 表1变量的取值范围

Table 1 TablelLower and upper boundsof variables   

<html><body><table><tr><td>变量</td><td>Peva/ MPa</td><td>Pcon/ MPa</td><td>Tsup/ ℃</td><td>Weva/ m</td><td>Leva/ m</td><td>beva/ m</td><td>Wcon/ m</td><td>Lcon/ m</td><td>bcon/ m</td></tr><tr><td>下限</td><td>1.5</td><td>0.2</td><td>1</td><td>0.5</td><td>0.15</td><td>0.002</td><td>0.5</td><td>0.15</td><td>0.002</td></tr><tr><td>上限</td><td>2.5</td><td>0.5</td><td>5</td><td>1</td><td>0.5</td><td>0.005</td><td>1</td><td>0.5</td><td>0.005</td></tr></table></body></html>

同理，多目标优化系统比投资成本较单目标优化是增大的，但较其效率却有提高。

表2 GA 基本参数Table2 BasicparametersofGA  

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>初始种群大小</td><td>100</td></tr><tr><td>最大进化代数</td><td>300</td></tr><tr><td>交叉概率</td><td>0.7</td></tr><tr><td>变异概率</td><td>0.001</td></tr><tr><td>最优前端个体系数</td><td>0.3</td></tr><tr><td>适应度函数偏差值</td><td>10-6</td></tr></table></body></html>

# 表3不同优化目标下的决策变量优化结果

Table 3 Table 3 Optimization results at different objective functions   

<html><body><table><tr><td>决策变量</td><td>SIC 最小 (图7D点)</td><td>m1最大 (图7C点)</td><td>多目标优化 (理想点图7B点)</td></tr><tr><td>Peva</td><td>1.6338</td><td>2.4999</td><td>2.3065</td></tr><tr><td>Pcon</td><td>0.2002</td><td>0.2</td><td>0.2001</td></tr><tr><td>Tsup</td><td>4.9485</td><td>4.8718</td><td>4.8884</td></tr><tr><td>Leva</td><td>0.8251</td><td>0.629</td><td>0.766</td></tr><tr><td>Weva</td><td>0.1941</td><td>0.3483</td><td>0.2615</td></tr><tr><td>beva</td><td>0.0022</td><td>0.0041</td><td>0.0026</td></tr><tr><td>Lcon</td><td>0.6104</td><td>0.5924</td><td>0.6</td></tr><tr><td>Wcon</td><td>0.3454</td><td>0.4389</td><td>0.4005</td></tr><tr><td>bcon</td><td>0.0022</td><td>0.005</td><td>0.0024</td></tr><tr><td>SIC /(€/kW)</td><td>5463.6</td><td>5859.9</td><td>5588.7</td></tr><tr><td>mex</td><td>38.74%</td><td>43.79%</td><td>42.95%</td></tr></table></body></html>

![](images/fd27a586eefc7d4b8ddd2942a9244617e87b23f7482235ed9ebd3c3c4ab75be1.jpg)  
图7ORC系统多目标优化Pareto最优解曲线Fig.7 Pareto curve of the ORC

# 4结论

ORC运行参数中蒸发压力和冷凝压力对系统热力性和经济性影响较大，循环过热度对系统性能的影响较小。板片间距对系统性能的影响分析表明，随着板间距的减小，系统比投资成本减小 $3 \% \sim 1 0 \%$ 。但对于使用R245fa为工质的ORC系统而言，循环效率改变极小仅有 $0 . 2 6 \%$ 。在给定条件下对于采用R245fa为工质的ORC系统优化最大效率是 $4 3 . 7 9 \%$ ，最小比投资成本是 $5 4 6 3 . 6 ~ \mathrm { { ‰} }$ 。通过多目标优化得到Pareto曲线，用理想点最小距离辅助方法给出决策者决策指导，最优点B点效率为 $4 2 . 9 5 \%$ ，比投资成本为 $5 5 8 8 . 7 \in / \mathrm { k W }$ 。

参考文献   
[1]许玮玮，唐晓东,李小红,等.低温余热回收升级利用技术综 述[J].广州化工,2011,39(23):34-36 XU Weiwei, TANG Xiaodong,LI Xiaohong, et al. Review of the Technology ofLow Temperature Waste Heat Recovery and Utilization Technology [J].Guangzhou Chemical Industry, 2011,39(23): 34-36   
[2] Ziviani D,Beyene A,Venturini M. Advances and Challenges in ORC systemsmodeling for Low Grade Thermal Energy Recovery [J].Appl Energy, 2014,121:79-95   
[3]王华,王辉涛.低温余热发电有机朗肯循环技术[M].科学出 版社,2010 WANG Hua, WANG Huitao. The ORC Technology [M]. Science Press, 2010   
[4]翁一武.低品位热能转换过程及利用[M].上海交大出版社, 2014 WENG Yiwu.Low Grade Thermal Energyconversion Process and the use of [M]. Shanghai Jiaotong University Press, 2014   
[5]罗向龙，徐乐,谭立锋,等.R245fa 有机朗肯循环余热发电 系统分析[J].节能技术，2012,30(2)：131-135 Luo Xiang Long, XU Yue, TAN Lifeng, et al. Analysing R245fa organic Rankine Cycle Waste Heatpower Generation System of Energy. Energy Conservation Technology, 2012,30(2): 131-135   
[6] Chen Q,Xu J,Chen H.A New Design Method for Organic Rankine Cycles with Constraint of Inlet and Outlet Heat Carrier Fluid Temperatures Coupling Withthe Heat Source [J]. Applied Energy, 2012,98(5): 562-573   
[7] Quoilin S,Declaye S,Tchanche B F,et al. Thermoeconomic Optimization of Waste Heat Recovery Organic Rankine Cycles [J].Applied ThermalEngineering，2011, 31(14-15): 2885-2893   
[8] Hettiarachchi H D M,Golubovic M,Worek W M,et al. Optimum Design Criteria for an Organic Rankine Cycle Using Low-Temperature Geothermal Heat Sources [J].Energy, 2007,32(9): 1698-1706   
[9] Pierobon L,Nguyen TV,Larsen U,et al. Multi-Objective Optimization of Organic Rankine Cycles for Waste Heat Recovery:Application in an Offshore Platform [J]. Energy,2013,58(3):538-549   
[10] Wang J, Yan Z,Man W,et al.Multi-Objective Optimization of an Organic Rankine Cycle(ORC) for Low Grade Waste Heat Recovery Using Evolutionary Algorithm [J]. Energy Conversion & Management,2013,71(3):146-158   
[11]周明.遗传算法原理及应用[M].国防工业出版社，1999 ZHOU Ming. Principle and Application of Genetic Algorithm [M]. National Defence Industry Press,1999   
[12] Hall S G,Ahmad S,Smith R.Capital Cost Targets for Heat Exchanger Networks Comprising Mixed Materials of Construction, Presure Ratings and Exchanger Types [J]. Computers & Chemical Engineering,1990,14(3):319-335   
[13] Arsalis A.Thermoeconomic Modeling and Parametric Study of Hybrid SOFC-Gas Turbine-Steam Turbine Power Plants Ranging From 1.5 tol0 MWe [J]. Journal of Power Sources,2008,181(2): 313-326