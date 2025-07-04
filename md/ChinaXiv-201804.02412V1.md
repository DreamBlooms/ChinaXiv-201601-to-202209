# 空间故障网络及其与空间故障树的转换

崔铁军1,2,3∗，李莎莎1,2，朱宝艳」

(1.辽宁工程技术大学 安全科学与工程学院，辽宁 阜新 123000;2.矿山热动力灾害与防治教育部重点实验室，辽宁阜新 123000;3．大连交通大学 辽宁省隧道与地下结构工程技术研究中心，辽宁 大连116028)

摘要：空间故障树是一种研究系统可靠性与影响因素关系的理论体系，用树型结构描述元件与系统之间的可靠性关系。但实际故障发生过程是复杂的，难以表示成树型结构，而更为广泛的是网状结构。因此，尝试将空间故障树中的树型结构转换为网络结构，进而形成空间故障网络。给出空间故障网络的定义、性质及其与空间故障树的转换方法。目的是将空间故障网络转换为空间故障树，以利用空间故障树已有研究结果。给出一般结构和多向环结构的空间故障网络，及其转换为空间故障树的方法。为使用空间故障树理论研究一般网络结构故障发生过程提供方法。

关键词：安全系统工程；空间故障树；空间故障网络；转换方法中图分类号：X913.4 doi:10.3969/j.issn.1001-3695.2018.01.0072

# Construction space fault network and recognition network structure characteristic

Cui Tiejun1,2,3,Li Shashal,2, Zhu Baoyanl (1.CollegeofSafetyScienceAndEngineeringLiaoningTechnicalUniversityFuxinLiaoning23oo,China;2.KeyLbotoy of Mine ThermodynamicDisasters AndControlof Ministryof Education,Fuxin Liaoning1230，China;3.Tunnel& Underground Structure Engineering CenterofLiaoning,Dalian Jiaotong University,Dalian Liaoning l16O28,China)

Abstract: The space fault treeisatheoretical systemto study therelationship between thesystem reliabilityand influencing factors.Tetrestructureissedtoscbetationship.utteactualfultproessismplicated,itisdiultt thetree structure,andthe more general is thenetworkstructure.Therefore,thispaperattemptedtotransformthetr structure inthe spacefault tree intoanetwork structure,and then formaspacefault network.Tedefinitionand propertiesofthe space fault network andthe transformation method withthespacefaulttree are given.The purposeis totransformthe space fault network into spacefault tre,andto makeuseoftheexistingresearchresultsofthe space faulttree.The spacefault network has thegeneralstructure andthe multidirectionring structure,andthetransforming methodintoaspace faulttree is given.Inorder to use the space fault tree,a method for the fault process of general network structure is provided.

Key Words: safety system engineering; space fault tree; space fault network; transformation method

# 0 引言

故障树是安全系统工程基础理论之一。在当今系统可靠性研究领域极为重要，也是学界研究的重点。许多学者对故障树理论在不同方面进行了应用，并提出了改进方法。例如在医学方面，故障树应用于手足口病的控制分析[11；利用故障树分析法处理硫化氢的实验室规模生物反应器的安全性[2]。在不确定性问题研究方面，使用事故树处理不确定性问题[3]；使用决策树基于概率和可能性来表示不确定性[4]；依赖基本事件的故障树模型的不确定性分析[5]；通过混合概率一可能性框架处理故障树分析中的不确定性[。在系统可靠性分析方面，基于事故树提出了实时的系统分析方法[；研究了非可修系统的优先级和与门动态故障树模型[8]。在系统的安全分析方面，使用扩展故障树分析了自治系统的安全[9]。在电气系统方面，利用多值Fisher 模糊决策树对模拟电路故障进行诊断[10]；使用概率故障树对辐射处理系统进行了分析[1]；应用事故树诊断燃料电池故障[12]；利用故障树分析了不间断电源系统可靠性[13]。在交通运输方面，基于时序故障树对铁路运输系统风险进行了评估[14];另外，提出了故障树分析中基本事件的一种排序方法[15]；基于二元决策图的有效排序启发式算法的故障树分析[16]；基于IRVPMand SBDD的高度耦合动态事故树的定量分析[17]；基于结构函数耦合和蒙特卡洛仿真的动态故障树定量分析[18]；提出了动态故障树分析中的一种有效的近似马尔可夫链方法[19]；基于结构函数的动态故障树定量分析[20]。

但这些研究难以分析多因素影响下的系统可靠性特征，不具备逻辑分析和大数据处理能力。因此笔者提出了空间故障树理论，详见第1章论述。但空间故障树的基础是经典故障树，是一种具有树型结构的故障因果关系表示方法。但实际故障发展过程往往不能表示成理想的故障树形式，更为一般的是网络结构的故障发生过程。即各种原因和结果相互交织，共同作用于最终故障。其不能表示成故障树形式，更无法使用空间故障树理论进行分析。

为解决该问题，同时利用空间故障树现有研究成果，提出空间故障网络概念。将一般的故障发生过程用网络拓扑形式表示，在通过一定的方式将其转换为空间故障树进行处理。本文主要给出了空间故障网络的定义、性质；图形化表示方法；空间故障网络与空间故障树的转换方法；故障网络性质及故障概率计算等。空间故障网络的提出是空间故障树理论解决实际故障过程的泛化，是进一步使用空间故障树理论研究故障一般规律的基础。

# 1 空间故障树

为了解系统工作环境因素对系统可靠性的影响，提出了一套空间故障树（space fault tree，SFT）理论[2I]。该理论认为系统工作于环境之中，由于组成系统的基本事件或物理元件的性质，决定了系统在不同条件下工作的故障发生概率不同。SFT产生了三个分支：连续型空间故障树（continuous space fault tree,CSFT）、离散型空间故障树（discrete space fault tree，DSFT）和系统结构反分析（inward analysisof structural systems，IASS）。CSFT是一种知道系统内部构造和元件性质，再研究系统在外界作用下响应行为的一种白盒方法。相对应，DSFT不需要了解系统内部构造和元件性质，研究基础是系统对外界环境变化所进行的响应特征，即黑盒方法。IASS在不清楚系统内部具体构造情况下，通过系统对外界环境因素变化的响应来剖析和窥探系统内部结构。

对于CSFT，首先提出了 SFT 基本思想和方法[22]，研究了SFT的径集域与割集域[23]、因素重要度分布等概念[24]。同时利用上述基本概念完成了一些研究，包括维持系统可靠性方法[25]、系统可靠性决策规则发掘方法[26]、系统可靠性评估方法[27]及其优化[28]等。

对于DSFT，首先给出了DSFT的定义和性质[29]，后研究了DSFT的建立及故障概率空间分布[30]和故障概率变化趋势[31]。提出使用因素投影拟合法得到特征函数[32]。使用模糊结构元理论得到模糊结构元化特征函数[33.34]。使用云模型理论得到云化特征函数[35]，进而完成了对离散故障数据的表示及处理方法。

对于IASS，主要研究了二值的01型SFT的表示和分析方法。分析方法为逐条分析法和分类推理法[36]，结构化表示方法为图法和表法[37]。

结合SFT与因素空间理论完成了一些研究，包括属性圆定义及其在对象分类中的应用[38]。考虑范围属性的系统安全分类决策规则研究[39]、煤矿安全情况区分方法研究[40]。这些研究证明了FS与SFT结合的可行性。同时也进行了一些系统可靠性分析研究[41]。

这些研究为空间故障树打下了坚实的理论基础。

# 2 基本定义

空间故障网络的处理需要借助SFT理论，所以空间故障网络的基本定义借鉴了SFT。

定义1空间故障网络（space fault network,SFN)。产生系统故障事件组成的拓扑结构。用 $W = ( { \boldsymbol { X } } , { \boldsymbol { L } } , R , B , \mathbf { B } )$ 表示，其中： $X$ 代表网络中的节点集合，即事件； $L$ 代表网络中的连接集合； $R$ 代表网络跨度集合； $B$ 代表网络宽度集合；B代表布尔代数系统。

定义2节点。SFN 中的节点代表故障发生过程的事件，故障网络中多个节点可以表示同一个事件，但不是同一次事件；一个事件的一次发生只对应一个节点。SFN 的节点按照故障的发展可分为三类。用 $\nu _ { i }$ 表示，节点集合 $V = \{ \nu _ { 1 } , \nu _ { 2 } , \cdots , \nu _ { I } \}$ 共有 $I$ 个节点。

第一类称为边缘事件，即导致故障的基本事件，是故障发生的源头，在故障网络中没有任何事件导致边缘事件发生。对应于故障树的基本事件。

第二类称为过程事件，即故障发生过程中，由于边缘事件或其他过程事件导致的事件，同时也导致其他过程事件或最终事件。对应于故障树中的中间事件。

第三类称为最终事件，即过程事件导致的事件，但在故障网络中不导致任何其他事件发生。

定义3事件的发生概率。事件的发生概率与 SFT中的定义相同，用特征函数 $p _ { i }$ 表示。

定义4连接。故障发生过程中事件之间的影响传递，连接存在于两个事件之间。连接是有向的，从原因事件指向结果事件。用 $l _ { j }$ 表示，连接集合 $L = \{ l _ { 1 } , l _ { 2 } , \cdots , l _ { J } \}$ ，共有 $J$ 个连接。原因事件可以是边缘事件和过程事件。结果事件可以是过程事件和最终事件。

定义5路径。从一个事件到另一个事件过程中的多个连接的组合。这些连接具有统一的方向。用 $E _ { f }$ 表示，路径集合$E { = } \{ e _ { 1 } , e _ { 2 } , { \cdots } , e _ { F } \}$ ，共有 $F$ 个路径。

定义6传递概率。原因事件可导致结果事件的传递概率，即原因事件发生后导致结果事件发生的概率。用 $p _ { j }$ 或 $p$ 原因事件→结果事件表示。

定义7SFN 的跨度。指两个事件之间经过的连接数量。用于衡量故障发生的过程复杂程度。一个事件与边缘事件的最大跨度称为该事件的模跨度。最终事件的模跨度是故障网络中的最大跨度。用 $r _ { o }$ 表示，跨度集合 $R = \{ r _ { 1 } , r _ { 2 } , \cdots , r _ { o } \}$ ，共有

$o$ 个跨度。

定义8SFN 的宽度。指故障网络中一个事件所涉及的所有边缘事件的所有节点的总数。用于衡量故障原因的复杂度。一个事件的最大宽度称为该事件的模宽度。最终事件的模宽度是故障网络中的最大宽度。用 $b _ { { } _ { m } }$ 表示，宽度集合$B = \{ b _ { 1 } , b _ { 2 } , \cdots , b _ { M } \}$ ，共有 $M$ 个跨度。

定义9事件之间的逻辑关系。过程事件和最终事件都包含了引起它们发生的所有事件的逻辑关系。这些逻辑关系包括“与”“或”、“非”，与故障树的逻辑关系相同。用（B， $\vee$ ，>，一）表示。

# 3 SFN的图形化表示

SFN转换为SFT的前提是对故障发生过程的图形化表示。两种最基本的SFN结构如图1所示。

![](images/8bc71d8c539c724b82b6d8b0c54d2d97e3c801dfadba063507140e8d9c2044b9.jpg)  
图1 两种SFN

图1（a）为一个最基本的SFN，网络由6个事件组成，分别为 $\nu _ { 1 - 6 \circ }$ 根据定义2，边缘事件为 $\vert \nu \boldsymbol { 5 } ^ { }$ ， $\mathbf { \Psi } _ { \nu 6 }$ ；过程事件为 $\mathbf { \sigma } _ { \nu 2 }$ ， $\nu _ { 3 }$ ，$\nu _ { 4 }$ ；最终事件 $\nu _ { 1 }$ 。定义4的连接是图中的有向箭头线段。定义7和8中的跨度和宽度需要借助SFT转换得到，下章进行介绍。定义9逻辑关系，“与或”关系至少是二元运算，即需要两个原因事件才能完成，如图中 $\nu _ { 1 } , \nu _ { 4 \circ } \nu _ { 1 + }$ 表示原因事件 $\nu _ { 2 } , \nu _ { 3 }$ 是“或”关系，造成 $\nu _ { 1 }$ 发生； $\nu _ { 4 }$ .表示原因事件 $\vert \nu _ { 5 }$ ， $\nu _ { 6 }$ 是“与”关系，造成 $\nu _ { 4 }$ 发生。如果原因事件和结果事件是一一对应的，且不是“非”关系，则不需要在结果事件中标注逻辑关系。

图1（a）是最简单的故障网络。其中连接方向是恒定的，不存在多向环结构。

图1（b）在（a）的基础上出现了多向环结构，如 $\nu _ { 3 } \to \nu _ { 1 }$ 及$\nu _ { 3 } \to \nu _ { 2 } \to \nu _ { 1 }$ 。这样会产生相同原因事件和结果事件之间的跨度不同的现象。即相同的原因事件经历不同过程导致相同的结果事件，这样在进行SFT转换过程中采取的措施是不同的。这过程中结果事件及原因事件的逻辑关系有关。

上述两种故障网络是基本形式，不同形式转换为SFT的形式和方法不同。下章给出SFN转换为SFT的具体形式和方法。

# 4 SFN与SFT的转换

SFN 是SFT的重要组成部分，是SFT理论应用于更广泛故障过程分析的基础。由于树型结构是网络结构的特殊形式，将故障过程表示为故障网络具有更为普遍的适用性。SFT是在树型拓扑中研究故障概率与因素的因果关系；SFN是在网状拓扑中研究因果关系，它们方法类似但拓扑结构不同。SFT理论已提出了一些定义和方法，那么SFN如何实现相应功能是研究重点。可通过两种方法实现，一是针对故障网络特点从新研究分析方法；二是将SFN转换为SFT，使用现有的SFT方法进行处理。这里给出SFN转换为SFT的方法。

如图1可知，SFN具有两种基本形式。这两种结构表示的故障过程不同，转换为SFT的方法也不同。

![](images/de91f96222d6a8d23ded99ba51019533b1df86ec6674d97150fd017e29bb8704.jpg)  
图2转换后的 SFT

图2给出了图1中SFN转换为SFT的结果。图2（a）和（b）分别对应图1（a）和（b)。SFT中只有事件，而SFN同时具有事件和连接的概念。

从图2（a）可知，从最终事件出发进行SFT构建。 $\nu _ { 1 }$ 的原因事件为 $\nu _ { 3 }$ 和 $\nu _ { 2 }$ ； $\mathbf { \sigma } _ { \nu 3 }$ 的原因事件是 $\mathbf { \sigma } _ { \nu 4 }$ ： $\nu _ { 2 }$ 的原因事件是 $\nu _ { 4 }$ . $\nu _ { 4 }$ 的原因事件为 $\mathbf { \sigma } _ { \nu 5 }$ 和 $\nu _ { 6 }$ 。从最终原因事件向边缘事件的逆序故障发生过程寻找，从而可绘制该SFT。

从图2（b）可知，存在 $\nu _ { 3 } \to \nu _ { 1 }$ 及 $\nu _ { 3 } \to \nu _ { 2 } \to \nu _ { 1 }$ 两个不同的发生过程，添加 $\nu _ { 2 }$ 的原因事件为 $\nu _ { 3 }$ 和 $\mathbf { \sigma } _ { \nu 4 }$ ，逻辑关系为“或”。与图2（a）相比增加了一个连接，即 $\nu _ { 3 } \to \nu _ { 2 }$ 。那么对于 $\nu _ { 2 }$ ，其原因事件与 $\nu _ { 1 }$ 的原因事件相同，则可将图2（a）中 $\nu _ { 3 }$ 的原因事件过程直接作为 $\nu _ { 2 }$ 原因事件过程的一个分支，从而形成图2(b)。

最终，SFN转换为SFT是从最终事件开始的，转换是故障发生过程的逆序。从最终故障开始，寻找结果事件对应的原因事件，即沿着连接反方向寻找。以结果事件形成树根，分支数量为连接指向本结果事件的数量，即导致本结果事件的原因事件。如果该原因事件被连接指向，那么将其作为结果事件，根据上述方法继续寻找其他的原因事件。直至寻找得到的原因事件均为边缘事件，转换停止。

# 5 结束语

本文在SFT基础上提出了SFN的概念，主要结论如下：

a）构建了SFN基础定义和方法。SFN是SFT的扩展，用于处理具有网络特征的故障发生过程。给出了相关定义，图形化表示方法。

b）给出了两种不同的SFN网络结构与SFT转换的方法，包括一般结构和多向环结构。SFN转换为SFT是从最终事件开始的，是故障发生过程的逆序。一般结构和多向环结构的转化方法相同，即逆序转换。

目前提出的SFN方法及其与 SFT的转换只能处理较为简单的网络故障发生过程，更为复杂的网络拓扑与树型结构的转换有待进一步研究。

参考文献：   
[1]Isoda N,Kadohira M, Sekiguchi S,et al.Review: evaluation of foot-andmouth disease control using fault tree analysis [J].Transboundary and Emerging Diseases,2013,62 (3): 233-244.   
[2]Zytoon MA,El-ShazlyAH,Noweir MH,et al. Quantitative safety analysis ofalaboratory-scale bioreactor for hydrogen sulfide biotreatment using fault tree analysis [J]. Process Safety Progress,2013,32 (4): 376-386.   
[3]Ferdous R,Khan F,Sadiq R,et al. Fault and event tree analyses for process systems risk analysis: uncertainty handling formulations [J]. Risk Analysis, 2011,31 (1): 86-107.   
[4]FlageR，Baraldi P,ZioE,etal.Probabilityandpossibility-based representations ofuncertainty in fault tre analysis [J]. Risk Analysis,2012, 33 (1): 121-133.   
[5]Pedroni N,Zio E.Uncertainty analysis in fault tree modelswith dependent basic events [J].Risk Analysis,2013,33 (6):1146-1173.   
[6]Wang Dong, Zhang Yan,Jia Xiang,et al. Handling uncertainties in fault tree analysis by a hybrid probabilistic-possbilistic framework [J]. Quality and Reliability EngineeringIntermational,5,2(3):117-148.   
[7] Remenyte-Prescott R,Andrews JD.An efficient real-time method of analysis for non-coherent fault trees [J]. Quality and Reliability Engineering International,2009,25 (2):129-150.   
[8]Ge Daochuan,Li Dong,Chou Qiang,et al. Quantification of highly coupled dynamic faultree using IRVPM and SBDD [J].Quality and Reliability Engineering International,2014,32(1):39-151.   
[9]ASlund J,BiteusJ,Frisk E,et al. Safetyanalysis ofautonomous systems by extended fault tree analysis [J]. International Journal of Adaptive Control and Signal Procesing,20,21 (2): 287-298.   
[10] Cui Yiqian, Shi Junyou, Wang Zili. Analog circuits fault diagnosis using multi-valued Fisher's fuzzy decision tree (MFFDT)[J]. International Journal of Circuit Theory and Applications,2015,44 (1): 240-260.   
[11] Ekaete E,Lee R C,Cooke DL,et al.Probabilistic fault tree analysis of a radiation treatmentsystem[J].Risk Analysis,2008,27(6):1395-1410.   
[12] Steiner NY,Hissel D,MootéguyP,et al. Application of fault tree analysis to fuel cell diagnosis [J].Fuel Cells,2012,12 (2):302-309.   
[13]Rahmat MK, Jovanovic S.Reliability modelling of uninterruptible power supply systems using fault tree analysis method [J]. European Transactions on Electrical Power,2009,19 (2): 814-826.   
[14] Peng Zhaoguang,Lu Yu,Miller A,et al.Risk assessment of railway transportation systems using timed fault trees [J].Quality and Reliability Engineering International,2016,32(1):181-194   
[15] Huang Hongzhong,Zhang Hua,Li Yanfeng.Anew ordering method ofbasic eventsinfault treeanalysis[J]. QualtyandReliabilityEngineeing International,2012,28 (3):297-305.   
[16]Mo Yuchang,Zhong Farong,Liu Huawen,et al.Eficient ordering heuristics inbinary decision diagram-based fault treeanalysis [J].Quality and ReliabilityEngineeringInternational,2013,29 (3):7-15.   
[17] Ge Daochuan,Yang Yanhua.Reliability analysisof non-repairable systems modeledby dynamic fault treeswith priority AND gates [J].Applied Stochastic Models in Business and Industry,2015,31(6): 809-822.   
[18]Merle G,Rousel JM,Lesage JJ,et al.Quantitative analysis of damic fault trees based on the coupling of structure functions and monte carlo simulation [J].Qualityand Reliability Engineering International,2014,32 (1): 7-18.   
[19] Yevkin O.An efficient approximate markov chain method in dynamic fault tree analysis[J]. QualityandReliabilityEngineeringInternational,2015,32 (4): 1509-1520.   
[20] Merle G,Roussel JM,Lesage JJ.Quantitativeanalysisof dynamic fault trees based on the structure function [J]. Qualityand Reliability Engineering International,2014,30(1):143-156.   
[21]崔铁军．空间故障树理论研究[D].阜新：辽宁工程技术大学,2015. (Cui Tiejun. Study theory of space fault tree [D].Fuxin: Liaoning Technical University,2015.)   
[22]崔铁军，马云东．多维空间故障树构建及应用研究[J].中国安全科学 学报,2013,23(4):32-37.(Cui Tiejun,Ma Yundong.Research on multi dimensional space fault tree construction and application [J]. China Safety Science Journal,2013,23 (4): 32-37.)   
[23]崔铁军，马云东．空间故障树的径集域与割集域的定义与认识[J]．中 国安全科学学报,2014,24(4):27-32.(Cui Teijun,Ma Yundong.Definition and understand on size set domain and cut set domain based on multi dimensionalspacefault tree[J].ChinaSafetyScienceJoural,214,24(4): 27-32.)   
[24]崔铁军，马云东．连续型空间故障树中因素重要度分布的定义与认知 [J].中国安全科学学报,2015,25(3):24-28.(Cui Tiejun,Ma Yundong. The definition and cognition of the factor importance distribution in Continuous SpaceFault Tree[J]. China Safety Science Journal,2015,25 (3): 24-28.)   
[25]崔铁军，马云东．基于多维空间事故树的维持系统可靠性方法研究[J]. 系统科学与数学，2014,34(6):682-692.(Cui Teijun,Ma Yundong. Research on the maintenance method of system reliability based on multi dimensional space fault tree [J].Journal of Systems Science and Mathematical Sciences,2014,34(6): 682-692. )   
[26]崔铁军，马云东．系统可靠性决策规则发掘方法研究[J]．系统工程理 论与实践,2015,35(12):3210-3216.(Cui Tiejun,Ma Yundong.The method research ondecisioncriterion discoveryof systemreliability[J].Systems Engineering-Theory&Practice,2015,35 (12): 3210-316.)

[27]李莎莎，崔铁军，马云东．基于空间故障树理论的系统可靠性评估方法 研究[J].中国安全生产科学技术,2015,11(6):68-72.(Li Shasha,Cui Tiejun,Ma Yundong. System reliability assessment method based on space fault tree [J]. Journal of Safety Science and Technology,2015,11 (6): 86- 92.)

[28]崔铁军，马云东．基于 SFT 理论的系统可靠性评估方法改造研究[J]. 模糊系统与数学，2015,29(5):173-182.(Cui Tiejun,Ma Yundong. Reliability assessment method based on space fault tree [J].Fuzzy System and Mathematics,2015,29(5): 173-182.)

[29]崔铁军，马云东．离散型空间故障树构建及其性质研究[J]．系统科学 与数学,2016,36(10):1753-1761.(Cui Tiejun,Ma Yundong.Discrete space fault tree construction and application research [J].Journal of Systems Science and Mathematical Sciences,2016,36 (10):1753-1761.)

[30]崔铁军，马云东.DSFT的建立及故障概率空间分布的确定[J]．系统工 程理论与实践，2016,36(4):1081-1088.(Cui Tiejun,Ma Yundong. Discrete space fault tree construction and failure probability space distribution determine [J]. Systems Engineering-Theory & Practice,2016, 36 (4):1081-1088.)

[31]崔铁军，李莎莎，马云东，等．基于ANN求导的 DSFT中故障概率变 化趋势研究[J].计算机应用研究,2017,34(2):449-452.(Cui Tiejun,Li Shasha,Ma Yundong,et al.Research on trend of failure probability inDSFT based on ANN derivation [J].Application Research of Computers,2017,34 (2): 449-452. )

[32]崔铁军，马云东.DSFT中因素投影拟合法的不精确原因分析[J]．系统 工程理论与实践，2016,36(5):1340-1345.(Cui Tiejun,Ma Yundong Inaccurate reason analysis of the factors projectionfitting method in DSFT. Systems Engineering-Theory& Practice,2016,36(5):1340-1345.)

[33]崔铁军，马云东.DSFT 下模糊结构元特征函数构建及结构元化的意义 [J].模糊系统与数学,2016,30 (2):144-152.(Cui Tiejun,Ma Yundong. The construction of fuzzy structured element characteristic function and the significance of structure elemented in DSFT [J].Fuzzy System and Mathematics,2016,30(2):144-152.)

[34]崔铁军，马云东．基于模糊结构元的 SFT 概念重构及其意义[J].计算 机应用研究，2016,33(7):1957-1960.(Cui Tiejun,Ma Yundong.SFT concept reconstruction and its significance based on Fuzzy structured element [J].Application Research of Computers,2016,33(7):1957-1960.)

[35]Li Shasha, Cui Tiejun,LIU Jian. Study on the construction and application of cloud space fault tree [J]. Cluster Computing,2017 (2):1-21.

[36]崔铁军，汪培庄，马云东.01SFT中的系统因素结构反分析方法研究[J]．系统工程理论与实践,2016,36(8):2152-2160.(Cui Tiejun,WangPeizhuang,Ma Yundong.Inward analysis of system factor structure in 01space fault tree [J]. Systems Engineering-Theory & Practice,2O16,36(8):2152-2160. )

[37] Cui Tiejun,Wang Peizhuang,Li Shasha.The function structure analysis theory based on the factor space and space fault tree [J].Cluster Computing, 2017,20 (2): 1387-1398.

[38]崔铁军，马云东．因素空间的属性圆定义及其在对象分类中的应用[J]. 计算机工程与科学,2015,37(11):2170-2174.(Cui Tiejun,Ma Yundong. Definition of the attribute circle in factors space and its application in object classification [J]. Computer Engineering & Science,2015,37(11): 2170- 2174.)

[39]崔铁军，马云东．考虑范围属性的系统安全分类决策规则研究[J]．中 国安全生产科学技术，2014,10(11):6-9.(Cui Tiejun,Ma Yundong System security classification decision rules considering the scope attribute [J].Journal of Safety Science and Technology,2014,10(11): 6-9.)

[40]崔铁军，马云东．基于因素空间的煤矿安全情况区分方法的研究[J]. 系统工程理论与实践,2015,35(11):2891-2897.(Cui Tiejun,Ma Yundong. Research on the classification method about coal mine safety situation based on the factor space [J].Systems Engineering-Theory& Practice,2015,35 (11): 2891-2897.)

[41] Cui Tiejun,Li Shasha.Study on the relationship between system reliability and influencing factors under big data and multi-factors [J].Cluster Computing,2017 (3):1-23.