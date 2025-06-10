编号：163443

# 过冷水滴凝固特性的计算与实验研究

肖光明，杜雁霞\*，李伟斌，王桥，易贤，桂业伟（中国空气动力研究与发展中心空气动力学国家重点实验室，绵阳621000）

摘要：针对飞机结冰的特殊凝固过程，基于Enthalpy-porosity模型，发展了改进的结冰特性预测模型及数值计算方法，并基于凝固实验开展了所建模型及预测方法的验证。研究表明，相对于传统Enthalpy-porosity方法，所发展的方法可有效表征非平衡凝固过程，因而对冷水滴凝固特性的表征具有较好的改进。基于所建方法，开展了水滴凝固特性的影响因素分析，获得了不同过冷条件下水滴凝固过程的温度分布及相界面变化特征。相关研究可为结冰热力学模型的改进，以及结冰特性的精细化预测提供重要参考。

关键词：过冷水滴；飞机结冰；凝固；相变中图分类号：V211.3 文献标识码：A

# Computational and Experimental Study on Freezing Characteristics of

Supercooled Water Droplet

XIAO Guang-Ming DU Yan-Xiao Li Wei-BinWANG Qiao YI Xian GUI Ye-Wei (State KeyLaboratoryofAerodynamics, China Aerodynamics Researchand Development Center,Mianyang 6210oo,China)

Abstract: Based on the Enthalpy-porosity model,an improved icing prediction model and numerical method are developed for the special freezing process of aircraft icing. The model and prediction method are validated by the related experiments.Compared with the traditional Enthalpy-porosity method,the results show that the new method can characterize the non-equilibrium freezing process of supercooled water droplet more effectively.Using the developed method,the influencing factors of the freezing characteristics of supercooled water droplet are analyzed,the temperature distribution and phase interface characteristics are obtained under different cooling conditions..The results can provide an important reference for the improvement of icing thermodynamic model and finer prediction of icing accretion.

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

Key words: supercooled water droplet; aircraft icing; freezing; phase change

# 0引言

飞机结冰是过冷水滴撞击飞机机体表面并发生凝固的特殊液/固相变现象，也是影响飞行安全的重要隐患之一[1-3]。在飞机结冰过程中，过冷水滴的凝固通常分为两个典型阶段[4]。第一阶段由形核开始，是水滴从热力学非平衡态过渡到热力学平衡态的阶段，即枝晶形成阶段，也有研究者称其为部分凝固阶段[。第二阶段为完全凝固阶段，即液固相界面由液相相向固相推进直至凝固完成的过程[7]。在飞机结冰过程中，由于撞击引起的异相形核过程，使凝固的第一阶段显著快于第二阶段[5]。由于结冰物理过程的复杂性，因而目前大多关于过冷水滴结冰的研究把重点放在凝固第二阶段，即相界面的推进过程上[4,5]。鉴于此，大多研究者基于平衡凝固的相关理论与方法开展结冰特性的预测研究，如不少研究者[8，9]基于Enthalpy-porosity 法研究凝固过程的液固相变行为，但该方法主要针对平衡凝固过程，无法表征过冷水滴凝固的第一阶段即非平衡凝固过程的影响特征。

近年来，随着结冰预测精度要求的提高，结冰过程的过冷水滴的非平衡凝固效应引起了研究者越来越多的关注[10-13]。但由于凝固过程的复杂性，目前非平衡凝固特性预测手段的研究还较为缺乏，预测精度也有待于提高，因而过冷水滴凝固规律特征的相关研究也较为薄弱。本文正是针对飞机结冰过程过冷水滴凝固的非平衡效应，发展了过冷水滴凝固特性预测方法，并自行搭建了实验系统开展了所建方法的实验验证。相关研究可为结冰热力学模型的改进，以及结冰特性的精细化预测提供参考。

# 1 非平衡凝固模型

实验研究表明，过冷水滴的凝固过程由两个典型阶段构成。在第一阶段即枝晶形成阶段，过冷水滴温度由过冷态上升至凝固点，并伴随潜热的部分释放，是非平衡凝固阶段；第二阶段为由热扩散驱动的界面推进阶段，也是在等温下进行的平衡凝固过程。尽管研究表明凝固第一阶段相对于第二阶段的时间相对较短，但由于结冰条件的不同，使第一阶段结束时形成了第二阶段的不同初始条件，从而影响了凝固的后续特征。因此，过冷水滴整个凝固过程的有效预测应综合考虑第一阶段的非平衡凝固效应及第二阶段的平衡凝固效应。针对过冷水滴的凝固两个典型阶段的特点，如何在相界面推进过程的预测中考虑第一阶段的非平衡效应，是有效预测结冰全过程凝固特性需解决的重要问题。

![](images/f08926d2c823179a2a6791c8644ca41fbcac50ac5cc9adf9c241ec8bf7462a56.jpg)  
图1过冷水滴凝固的两个典型阶段  
Fig.1Two typical freezing stages of supercooled water droplet

考虑到凝固第一阶段完成并形成混合态的过程中，过冷水滴已经有了潜热的部分释放，因此，凝固第二阶段预测中应进行考虑凝固第一阶段特性参数的修正。将无量纲过冷度 $\varepsilon$ 表示为：

$$
\varepsilon = c _ { s } \Delta T / \mathrm { L }
$$

其中， $c _ { s }$ 为固相比热容，L为固/液相变潜热， $\Delta T$

的计算表达式为：

$$
\Delta T = T _ { f } - T _ { \mathrm { s u p } e r c o o l e d }
$$

其中， $T _ { f }$ 为液相凝固温度， Tsupercooled为过冷态温度。

凝固第一阶段结束时混合态中未发生相变的液相分数 $f _ { 1 }$ 可表示为[5];

$$
f _ { 1 } = \boldsymbol { 1 - } \frac { c _ { l } } { c _ { s } } \varepsilon
$$

其中， $c _ { \scriptscriptstyle l }$ 为固相比热容。

因此，混合态的液/固相变潜热 $\mathrm { L } _ { m i x }$ 可表示为：

$$
\mathrm { L } _ { \mathit { m i x } } = L \cdot f _ { 1 }
$$

混合态的有关物性参数 $P M _ { m i x }$ 可表示为：

$$
P M _ { m i x } = P M _ { l } f _ { 1 } + P M _ { s } ( 1 - f _ { 1 } )
$$

其中， $P M _ { \iota }$ 和 $P M _ { s }$ 分别表示对应的液相和固相物性参数。

当获得凝固第一阶段凝固过程的物性参数后，考虑过冷阶段非平衡凝固效应的相变问题即可转化为平衡凝固问题。为借鉴平衡凝固条件下液/固相变传热的预测方法，作以下几点假设：

(1）忽略水滴凝固过程水滴的变形;

(2）由于撞击形成的异相形核作用，凝固第一阶段时间显著小于第二阶段；

(3）凝固过程的液相区实质为已在凝固第一阶段发生了部分相变的混合态，因此凝固第二阶段计算过程液相区物性参数由混合态参数代替。

基于上述假设并借鉴Enthalpy-porosity 方法，则凝固过程的流动及传热控制方程可描述为：

$$
\frac { \hat { \sigma } u _ { i } } { \hat { \sigma } x _ { i } } = 0
$$

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

$$
\begin{array} { l } { \displaystyle { \rho \left( \frac { { \hat { \partial } } u _ { i } } { \partial t } + u _ { j } \frac { { \hat { \partial } } u _ { i } } { \partial x _ { j } } \right) = - \frac { { \hat { \partial } } p } { \partial x } + \mu \frac { { \hat { \partial } } } { \partial x _ { j } } \left( \frac { \hat { \partial } u _ { i } } { \partial x _ { j } } \right) } } \\ { \displaystyle { - \rho g _ { i } \beta \big ( T - T _ { 0 } \big ) + S _ { i } } } \end{array}
$$

$$
\rho \left( \frac { \partial h } { \partial t } + u _ { j } \frac { \partial T } { \partial x _ { j } } \right) = \frac { \partial } { \partial x _ { j } } \left( \lambda \frac { \partial T } { \partial x _ { j } } \right)
$$

其中， $u _ { i } , \ u _ { j }$ 和 $x _ { i } , \ x _ { j }$ 分别表示不同方向的速度和坐标（对于三维问题， $i , j = 1 , 2 , 3 \ \rangle$ 。 $p$ 和 $T$ 分别对应于压力和温度变量， $T _ { 0 }$ 为满足Boussinesq 近似下的参考温度， $h$ 为热焓。 $\rho , \mu , \beta$ 和 $\lambda$ 分别对应于密度、粘性系数、热膨胀系数和热导率等物性参数。 $g _ { i }$ 为不同方向的重力加速度， $S _ { i }$ 为凝固第二阶段两相区的源项，可描述为[9];

$$
\begin{array} { c } { { S _ { i } = - C \left( 1 - f _ { 2 } \right) u _ { i } } } \\ { { \ } } \\ { { ( 9 ) } } \end{array}
$$

其中， $C$ 为表征凝固过程两相区特征的参数， $f _ { 2 }$ 为结冰过程凝固第二阶段液相率的比例，可表示为：

$$
f _ { 2 } = \left\{ \frac { T - T _ { s } } { T _ { l } - T _ { s } } \quad T _ { s } \leq T \leq T _ { l } \right.
$$

其中， $T _ { l }$ 和 $T _ { s }$ 分别为液/固相变过程完全熔化和完全凝固时的温度。

采用有限体积法离散控制方程，非稳态项采用时间一阶精度格式，采用强隐式迭代法进行求解。基于固定网格技术，不直接追踪两相界面，通过温度与焓值的关系，反算不同时刻的相界面位置，避免直接追踪两相界面带来的困难。基于上述方法，对项目组前期自行编制的相变传热计算代码[14]进行了方法的改进并开展了典型工况的算例分析。

# 2 非平衡凝固模型

以直径为 $4 \mathrm { m m }$ 、高度为 $2 . 5 \mathrm { m m }$ 的过冷水滴为例，分析其凝固过程的温度分布及相区分布特性。其中，水滴底面为冷却面。计算中底部为等温边界，表面采用对流边界。计算物性参数如表1所示。

表1冰和水的材料物性参数[5]  
Table 1Physical properties of water and ice[5]   

<html><body><table><tr><td colspan="4">相态p/kg:m³c/J·kg-1·K-1λ/W·m-1K-1L/kJ·kg-1</td></tr><tr><td>水</td><td>1000</td><td>4187</td><td>0.6 334624</td></tr><tr><td>冰</td><td>920</td><td>2031</td><td>2.3</td></tr></table></body></html>

图2显示了过冷水滴凝固过程的温度分布特性；图3显示了过冷水滴凝固过程的相区分布特性。在凝固初始阶段，相界面与等温线与底部冷表面近似平行。随着凝固过程的推进，相界面与等温线逐步向水滴顶部弯曲。

![](images/535b8d97a9be721f05b8784f9a9a30cef2678933969982b609688a46066f369f.jpg)  
图2考虑过冷效应的水滴凝固过程温度分布特性

![](images/d0df2609c82a509c5f4d808674b27dcec81875b5900ec482dba706c3d38f61e3.jpg)  
Fig.2Temperature distributions of droplet freezing considering supercooling effect   
图3考虑过冷效应的水滴凝固过程相区分布特性 Fig.3Phase interface distributions of droplet freezing considering supercooling effect

图4显示了过冷度为 $\cdot 1 0 ^ { \circ } \mathrm { C }$ 条件下考虑与不考虑非平衡凝固效应的凝固速率比较；图5显示了水滴不同过冷度对凝固相界面变化速率的影响特征。可以看出，在考虑过冷期间非平衡凝固效应影响条件下，凝固速率较传统方法有所提高。这是由于所建

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

模型考虑了过冷阶段形核和枝晶生长过程中水滴潜热的部分释放现象，因而在界面推进阶段，液/固相变潜热的释放量相对减少，因而界面推进速度较传统方法有所提高。从图5可以看出，在相同条件下，水滴过冷度越大，相变的驱动力也相对越大，因而凝固速率也相对越高。

![](images/3bf3305475e0a6c60fcfed35aeb1769d6341af43bbb72c7ccd702fc6926cc68e.jpg)  
图4过冷效应对相界面变化速率的影响

![](images/6ff6f1a94a6acb44dbcd99b7d837d5f8279331aecf3224a2171941e586454f91.jpg)  
Fig.4Effect characteristics of supercooled effect on freezing   
图5过冷度对凝固相界面变化速率的影响

图6显示了水滴凝固过程不同位置的温度变化曲线。T01-T05为从底面到表面位置点。可以看出，越靠近冷却面，温度降低速率越高。这是由于凝固第二阶段主要是在相变温度下由热扩散驱动而发生的等温平衡凝固过程，导热是该过程的主导传热机制。因此，越靠近冷却面，导热热阻相对越小，温降速率也相对越大。

![](images/bd2a09ce334d713cc2cbd2bdaab133c2d521926b31f43695a2b90e63e08cfc3e.jpg)  
图6水滴不同高度位置的温度变化特性 Fig.6Temperature variations of droplet freezingat different heights

# 3非平衡凝固模型

# 3.1 实验系统设计

为了验证所发展模型及方法的有效性，本项目自行搭建了实验系统并开展了相应的实验研究。实验系统示意图如图7所示，由半导体制冷系统、Agilent34970A多点数据采集仪、ANVTF100PID温度监视器、温度控制器、MotionXtraHG-100K高速摄像机、FLIRE60红外相机、LED无影光源系统、工控机及调压电源组成。实验时由半导体制冷台提供结冰冷环境，由PID 温度控制系统将制冷台表面温度维持在实验所需的温度条件；基于界面追踪的方法，采用高速摄像机记录获得水滴凝固过程相界面随时间的变化特性；采用红外相机记录水滴凝固过程温度的实时变化特性。

![](images/6c0a6525300ae049571f55dbaa9785014118867f337bd7f9e27d716ca49f5218.jpg)  
Fig.5Effect characteristics of supercooling on freezing rate of phase interface   
图7水滴凝固特性实验系统示意图  
Fig.7Experimental setup for droplet freezing

# 3.2实验凝固特性与计算结果的比较

在水滴凝固实验中可以发现，在过冷期间的形核与枝晶生长阶段，水滴在过冷条件的驱动下逐步由透明态向模糊态过渡；当水滴达到平衡温度，固/液界面开始出现并由液相区向固相区移动。如果以

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

固液/界面出现的起始时刻作为凝固第二阶段的起点，采用高速相机记录相界面随时间的变化特征，并同时采用红外热像仪记录水滴不同时刻的温度分布规律。图8显示了过冷度为- $1 0 ^ { \circ } \mathrm { C }$ 条件下凝固第二阶段相界面随时间的变化过程；图9显示了相对条件下相界面推进过程水滴红外温度场随时间的变化特征。可以看出，在凝固第二阶段，在热扩散的作用下，相界面由液相区向固相区推进，而水滴的低温区也逐步由底部向顶部发展。

![](images/5176ed5ed3f031110f0a162df55f95537921d04ab9e553ff07764fc9916c76c9.jpg)  
图8水滴凝固过程相界面随时间的变化特征

![](images/12bfb705979fc3bfea2392c56a9503e7cb2afc342604d02a540a10f68caf3b74.jpg)  
Fig.8Experimental evolution characteristics of phase interface   
图9水滴凝固过程温度随时间的变化特征  
Fig.9Experimental temperature variations of droplet freezing

图10显示了的计算与实验相界面移动特性的比较；图11则显示了过冷度分别为 $\cdot 1 0 ^ { \circ } \mathrm { C }$ 和 $1 4 ^ { \circ } \mathrm { C }$ 条件下，水滴表面计算温度与实验红外温度变化特性的比较。从图10可以看出，在相同过冷度条件下，改进预测模型的计算结果与实验结果的吻合程度优于传统Enthalpy-porosity预测模型。比较而言，考虑过冷效应的改进模型预测凝固速率要高于传统模型。从计算与实验结果的比较可以看出，计算与实验相界面随时间的移动特性吻合较好；计算与实验温度变化历程虽存在一定偏差但变化趋势基本相似，表明所建模型的有效性。

![](images/6d789a19ff09a3270a94c936e86ff5fdc7afa959f6aacb8b2cbd6cf1063df91d.jpg)  
图10实验与计算凝固速率的比较

![](images/04198b849f6bc87355217f9e14bda687754bff00f6f474c06498561afa859982.jpg)  
Fig.10Comparison of experimental and simulated freezing   
图11水滴凝固过程实验与计算温度变化特性的比较 Fig.11Comparison of experimental and simulated temperature variations of droplet freezing

# 4结论

本文针对飞机结冰过程过冷水滴结冰的非平衡凝固效应，开展了过冷水滴结冰凝固特性的计算与实验研究。主要结论如下：

（1）基于Enthalpy-porosity 模型，发展了过冷水滴结冰特性预测模型及数值计算方法，并自行搭建了实验台，开展了数值方法的实验验证。相对于传统方法，所发展的过冷水滴结冰特性预测模型及数值方法能有效表征非平衡凝固效应，因而可用于过冷水滴凝固特性的预测;

（2）在结冰过程中，过冷度越大，水滴的凝固速率相对越高。但在考虑非平衡凝固效应的条件下，过冷水滴凝固速率要高于不考虑非平衡凝固效应的工况。因此，飞机结冰过程中过冷水滴的凝固

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

特性具有与平衡凝固过程不同的特征。有效表征结冰过程的非平衡凝固现象是改进结冰热力学模型，提高结冰特性的重要基础。

# 参考文献

[1] BLAKE J,THOMPSON D,RAPS D,et al. Simulating the freezing of supercooled water droplets impacting a cooled substrate[J].AIAAJournal,2015,53(7):1725-1739.   
[2]FUMOTO K，KAWANAMI T. Study on freezing characteristics of supercooled water droplets impacting on solid surfaces[J]. Journal of Adhesion Science and Technology,2012, 26(4-5): 463-472.   
[3]KING W D.Freezing rates of water droplets[J]. Journal of the Atmospheric Sciences,1975,32(2): 403-408.   
[4] TABAKOVA S, FEUILLEBOIS F, RADEV S. Freezing of a suspended supercooled droplet with a heat transfer mixed condition on its outer surface [C]//lst International Conference on Applications of Mathematics in Technical and Natural Sciences,AIP Publishing,2009,1186(1):240-247.   
[5] FEUILLEBOIS F，LASEK A，CREISMEAS P，et al. Freezing of a subcooled liquid droplet[J]. Journal of Colloid and Interface Science,1995,169(1):90-102.   
[6]BURTNETT E.Volume of fluid simulations for droplet impact on dry and wetted hydrophobic and superhydrophobic surfaces [D].Mississippi: Mississippi State University,2012. [7] JUNG S，DORRESTIJN M，RAPS D，et al. Are superhydrophobic surfaces best for icephobicity?[J]. Langmuir, 2011,27(6): 3059-3066.   
[8]Voller,V.and Prakash，C.A Fixed Grid Numerical ModellingMethodology for Convection-DiffusionMushy Region Phase-Change Problems[J]. International Journal of Heat and Mass Transfer,1987,30(8): 1709 -1719.   
[9] Crank,J.Free and Moving Boundary Problems[M].New York :Oxford University Press,1987.   
[10] Worster M G.Solidification of fluids[J].Perspectives in fluid dynamics,2000,742:393-446.   
[11] ELLENN, JACCO MH, EDWIN W, et al.Aircraft icing in flight:effects of impact of supercooled large droplets [C]//29th Congress of the Aeronautical Sci-ences St. Petersburg,Russia, September 7-12,2014.   
[12] Tabakova, S.,and Feuillebois,F.,On the Solidification of a Supercooled Liquid Droplet Lying on a Surface[J]. Journal of Colloid and Interface Science,2004,272(1): 225-234.   
[13] Szimmat J.Numerical simulation of solidification process in enclosures[J].Heat Mass Transfer 2002,38:279-293.   
[14] Du Yanxia, Xiao Guangming,Gui Yewei, et al. Study on Heat Transfer Characteristics of Phase-Change Energy Storage Unit for Thermal Management[J].International Journal of Thermophysics,2014,35(8): 1577-1589

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

# 附页

第一联系人姓名：杜雁霞 Email:yanxiadu $@ 1 6 3$ . com邮编：621000 座机：0816-2463188通信地址：四川省绵阳市二环南路6号13信箱05分箱手机：15882778775

第二联系人姓名：肖光明 Email:cardc_xzm@163.com邮编：621000 座机：0816-2463192通信地址：四川省绵阳市二环南路6号13信箱05分箱手机：18780526077

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538