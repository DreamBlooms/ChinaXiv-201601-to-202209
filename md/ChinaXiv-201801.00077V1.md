编号： 161258

# 离子影响水蒸气核化的分子动力学研究

宋粉红1，徐洪帆1，刘朝²，范晶1，陈奇成1，李勇1(1.东北电力大学能源与动力工程学院，吉林 132012；2．重庆大学动力工程学院，低品位能利用技术及系统教育部重点实验室，重庆 400030)

摘要：本文采用分子动力学模拟方法研究离子的存在对水蒸气核化过程的影响。模拟系综初始温度为 $6 0 0 ~ \mathrm { K }$ ，达到平衡后撤去水蒸气热浴，将载气温度标定至 $2 0 0 ~ \mathrm { K }$ ，与水蒸气进行热量交换，带走水蒸气核化释放的核化潜热。研究结果表明，离子的存在能够促使核化的发生，但离子的浓度对系综内最大团簇的生长影响较小。根据团簇分析统计系综内含 20个 $\mathrm { { N a ^ { + } / C l } }$ 时，核化率约为 $1 . 0 1 { \times } 1 0 ^ { 2 8 } / ( \mathrm { c m } ^ { 3 } { \cdot } \mathrm { s } )$ ，与经典核化理论计算值 $4 . 8 9 { \times } 1 0 ^ { 2 8 } / ( \mathrm { c m } ^ { 3 } { \cdot } \mathrm { s } )$ 在同一个数量级。

关键词：离子；异质核化；团簇；分子动力学中图分类号：TK123文献标识码：A

# Molecular Dynamic Study of the Effect of Ions on Water Vapor Nucleation

Song Fen-Hong1,Xu Hong-Fan1, Liu Chao², Fan Jing1, Chen Qi-Cheng1,Li Yongl

Collge ofEnergyandPowerEngineering,NortheastDianliUniversityJilin,32l2,China；ColegeofPowerEngiin

Chongqing University,KeyLaboratoryofLow-grade Energy UtilizationTechnologies and Systems ofMinistryofEducation,

Chongqing 400030, China))

Abstract: Molecular dynamics simulation was employed to explore the mechanism of heterogeneous nucleation of water vapor underthe efect of ions. After the system reached to the equilibrium state at initial temperature $6 0 0 ~ \mathrm { K }$ the temperature of carrier gas was rescale at $2 0 0 \mathrm { ~ K ~ }$ ，which worked as the heat resource for the water vapor nucleation.The nucleation heat was removed by carrer gases during the nucleation process.The results show that, ions promote the nucleation progress on the initial stage,and the concentration of ions has less effect on the growth of the largest cluster in the system. The nucleation rate obtained from the cluster analysis was $1 . 0 1 { \times } 1 0 ^ { 2 8 } / ( \mathrm { c m } ^ { 3 } { \cdot } \mathrm { s } )$ in the system with $2 0 \ \mathrm { N a ^ { + } }$ and $2 0 ~ \mathrm { C l ^ { - } }$ ions,which is in the same order of magnitude with the value $4 . 8 9 { \times } 1 0 ^ { 2 8 } / ( \mathrm { c m } ^ { 3 } { \cdot } \mathrm { s } )$ predicted by classic nucleation theory analysis.

Keywords: Ions; Heterogeneous nucleation; Cluster; Molecular Dynamics.

# 1前言

相变是自然界广泛存在的一种物理现象，在能源利用、强化传热等领域起着重要作用[1-2]。在大气层中，当水蒸气的相对饱和度达到过饱和或大气中有足够多的灰尘粒子时，就会发生水蒸气凝结过程而形成云雾。随着经济的发展、科技水平的提高，气溶胶颗粒物污染越来越引起人们的注意，大气气溶胶严重的影响了空气质量、危害了人类健康。大气中悬浮的离子又分为小离子与大离子两种，小离子是几个中性分子团聚在一个带电离子周围形成的粒子，小粒子吸附在较大的中性气溶胶粒子上形成大离子。同一符号的大小离子的浓度在海洋乡村城市不尽相同，海洋上空小离子较多，城市上空大离子较多，并且大小离子浓度变化趋势相反。海陆上空的正负离子浓度相差不大，但正离子稍多[3]。

Winkler等[4]实验研究有机蒸气在大小为1-24nm 的小团簇和纳米颗粒上的异质核化过程并与经

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

典核化理论及Kelvin关系对比，结果发现，异质核越小越能激发核化。Inci等[5]通过引入与核化蒸气分子大小相同的粒子作为异质核来研究异质核化，并改变异质核与蒸气分子的相互作用力来讨论其对核化的影响。研究结果表明，异质核化与蒸气分子相互作用力较小的时候，异质核对小团簇胚核的形成功影响很小；随着相互作用力的增加，团簇形成自由能降低。张超等[6采用团簇分析法分析大于不同阈值的团簇数随时间的变化情况，通过最小二乘法分别拟合获取3种模拟工况下的核化速率，对比不同带电量离子对核化过程的影响。结果表明正二价离子比正一价离子周围产生的电场力大，对核化过程影响大。因此离子的存在对水蒸气核化有着重要的影响，而正负离子及离子浓度对水蒸气核化的微观机理还有待于进一步的研究，本文建立分子动力学模拟模型，研究离子影响水蒸气核化的微观机理及核化的微观物理过程。

# 2 模拟模型与计算细节

采用 $\mathrm { { N a ^ { + } } }$ 、CI离子代表正负粒子研究其对水蒸气核化的影响。图1为带电离子存在下的水蒸气核化模拟系统图，5000个SPC/E模型的水蒸气分子均匀分布在模拟盒 $2 9 \times 2 9 \times 2 9$ $\mathrm { n m } ^ { 3 }$ 内，5000个氩蒸气分子作为载气（未画出)，系统平衡后控制载气温度，载气可带走水蒸气核化释放的显热和潜热。为使图示清晰，水分子用点表示， $\mathrm { \Delta N a ^ { + } }$ 、CI-离子用放大球体表示。

![](images/b8081239511aedf7f730d7cd36665a9f1db73dd6c07ae294845b1353de4c6fbf.jpg)  
图1存在带电离子的水蒸气核化模型  
Fig.1 Schematic plot of water nucleation system with ions

氩分子间相互作用采用经典的L-J (12-6)势函数。水分子选用SPC/E模型，作用势函数为，

$$
\phi ( r _ { i j } ) = 4 \varepsilon _ { o o } [ ( \frac { \sigma _ { o o } } { r _ { o o } } ) ^ { 1 2 } - ( \frac { \sigma _ { o o } } { r _ { o o } } ) ^ { 6 } ] + \frac { 1 } { 4 \pi \varepsilon _ { 0 } } \sum _ { i = 1 } ^ { 3 } \sum _ { j = 1 } ^ { 3 } \frac { q _ { i } q _ { j } } { r _ { i j } }
$$

由于氢原子质量较小，方程(1)中第一项L-J势函数只用来计算氧原子间的相互作用力。 $\sigma _ { \mathrm { { o o } } }$ 和 $\varepsilon _ { \mathrm { { o o } } }$ 分别为氧原子间作用的尺度参数和势阱深度。后一项计算各个带电荷原子间的静电力， $q _ { i }$ 与 $q _ { j }$ 分别为原子 $i$ 与 $j$ 的电荷， $r _ { i j }$ 为原子 $i$ 与 $j$ 间的距离。 $\scriptstyle { \varepsilon _ { 0 } }$ 为真空介电常数。水分子与氩原子间的相互作用力由修正的L-J势函数计算，水分子与 $\mathrm { { N a ^ { + } } }$ 、CI离子的作用势函数取自文献[7]，根据Lorentz-Berthelot混合法则计算其与水分子上的氧原子作用的能量参数与尺度参数。表1给出势函数中各原子作用参数及电荷。时间步长3fs，截断半径 $1 . 5 \ \mathrm { n m }$ ，采用PPPM方法对长程静电力进行修正。采用周期性边界条件，VelocityVerlet 算法求解分子动力学方程。首先，采用 Nose-Hoover 热浴，模拟300 ps 使得系统在600K温度下达到平衡，撤去热浴将载气温度标定至200K。再模拟2000ps统计参数分析核化过程。

# 表1．势函数中各原子作用参数及电荷

Table 1Parameters and charges of atoms for potential   

<html><body><table><tr><td colspan="4">function</td></tr><tr><td>Atom</td><td>g/A</td><td>ε /kJ mol-1</td><td>qi/e</td></tr><tr><td>0</td><td>3.166</td><td>0.6502</td><td>-0.8476</td></tr><tr><td>H</td><td>0</td><td>0</td><td>0.4238</td></tr><tr><td>Ar</td><td>3.405</td><td>0.996</td><td>0.0</td></tr><tr><td>Na</td><td>2.583</td><td>0.4184</td><td>1.0</td></tr><tr><td>C1</td><td>4.400</td><td>0.4184</td><td>-1.0</td></tr></table></body></html>

# 3模拟结果及分析

# 3.1核化过程热力学参数

为讨论离子浓度对水蒸气核化的影响，系综内分别引入20、50、100、200个 $\mathrm { { N a ^ { + } / C l } }$ 离子对。图2给出了不同离子浓度系综内水蒸气的动能与势能随时间的变化关系。系综在模拟达到平衡后撤去热浴，将载气温度标定至200K，在载气热浴下，水蒸气温度降低至核化平衡温度。由图2(a)温度的分布图可以看出，在核化初期，离子浓度较低的系统，核化慢，释放潜热少，温度下降略快；离子浓度较高的系统，系综内水蒸气核化较剧烈，核化释放的潜热未能被及时带走，温度降低略慢。随着核化进行，温度均趋于平衡值，系综内离子浓度对平衡温度的影响较小，其对应的核化平衡温度为372\~375K。核化过程是势能降低的过程，由于离子的相互吸引使得分子间距离减小，使得离子浓度较大的系综对应的势能较低。

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

![](images/96ff911a2a21a62d133bbe55b5c802586a35b5d5ad95d300d4f4987fbe5d3c91.jpg)  
图2离子存在时水蒸气核化过程热力学参数随时间变化关系

# 3.2核化过程分析

$\mathrm { \Delta N a ^ { + } }$ 、CI与水分子间的短程范德华力相对较弱，其主要的相互作用力来之长程库伦力。图3为系综内包含 $1 0 0 \mathrm { { N a ^ { + } / C l } ^ { - } }$ 正负离子时水蒸气核化的动态过程。与之对应图4为系统内不同时刻点团簇大小的分布。系统模拟300ps 使其达到 $6 0 0 ~ \mathrm { K }$ 高温的平衡状态，此时水蒸气分子均匀地分布在系统内，无稳定团簇存在。然后撤去热浴，将载气温度标定至200K。随着载气与水蒸气进行热量交换，带走显热，水蒸气系统温度降低。核化为亚稳态过程，离子与水分子的较强作用力相当于一些扰动，促使核化发生，温度降低到核化点时，在离子周围的水分子以离子为核化中心核化。由于原子间的相互作用随着距离的增加而减弱，所以带电离子对其周围水分子核化的影响也随距离变化。如图3中 $\scriptstyle 1 = 5 0 0$ ps 时水蒸气分子核化形成团簇的情况，对应团簇大小分布见图4中 $\scriptstyle 1 = 5 0 0$ ps，这时系统内大量小团簇形成，不稳定的小团簇在分子相互作用下破裂，稳定的小团簇继续长大。当 $\scriptstyle 1 = 1 3 0 0$ ps，形成的小团簇开始在相互作用下聚并形成大团簇，最大团簇约由

500个水分子组成，此时仍有一些小的不稳定小团簇存在，不断地破裂又形成，系统内水蒸气饱和度降低。当 $\scriptstyle 1 = 2 0 0 0$ ps 时，系统内的核化基本达到一个动态平衡，几个较大的团簇稳定存在，最大团簇约包含 700 个水分子，水分子单体均匀分布在系统内。继续模拟到 $2 3 0 0 ~ \mathrm { p s }$ ，系统内的团簇大小分布变化较小，说明核化系统达到了核化与蒸发的动态平衡状态。

![](images/60d4e4b87c178ef2cd713705ff9f021e16b0bcb34165ee824926dd764517752b.jpg)  
图3系综内水蒸气核化的动态过程（ $1 0 0 \mathrm { { N a ^ { + } / C l } }$ 离子） Fig.3 The snapshots for dynamic process of water vapor nucleation with ${ 1 0 0 } \mathrm { { N a ^ { + } } }$ ions and $1 0 0 \mathrm { C l } ^ { - }$ ions

![](images/a2785f60f3785c20e3a3838871a4aab7474de1d1b0d156beb7b6456f4a82d020.jpg)  
Fig.2Evolution of thermal properties in nucleation of water vapor with ions (a) temperature (b) potential energy   
图4系综内团簇大小随时间的分布（ $1 0 0 \mathrm { { N a ^ { + } / C l } } ^ { }$ 离子)Fig.4Evolutionofcluster size distribution in water nucleation

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

![](images/0098e74cfe9c662697993abe7037b72eff5faa925b07163bcdb1f134d47e9f14.jpg)  
图5系统内最大团簇的大小随时间的分布  
Fig.5 Evolution of the largest cluster size distribution in water nucleation process with ions

同时讨论了离子浓度对水蒸气核化的影响，分析不同离子浓度下，系统内最大团簇包含的分子数随核化时间的变化，如图5所示。在核化初期，离子的存在能够促使核化的发生，团簇生长较快，图中发生阶跃为小团簇聚并到大团簇，最大团簇急剧长大。随着核化进行，小团簇聚并长大，系统达到新的平衡状态，最大团簇包含约700水分子。不同离子浓度的系统，核化达到平衡时，最大团簇大小基本相同，离子浓度影响较小。

# 3.3核化率计算

核化率定义为单位时间单位体积内生产的活化核(即能够稳定存在并长大的分子团簇)。本文以包含 $2 0 \mathrm { { N a } ^ { + } / C l ^ { - } }$ 离子的核化系综为例，分别采用经典核化理论预测及团簇分布统计分析离子存在时水蒸气的核化率大小。核化系统内对应的饱和度约为2.9。离子存在时水蒸气核化达到动态平衡时对应的温度约为375K，此温度下对应的饱和气与饱和液的密度分别为 $6 . 2 7 \times 1 0 ^ { - 4 }$ $\mathrm { g } { \cdot } \mathrm { c m } ^ { - 3 }$ 和 $0 . 9 1 6 5 ~ \mathrm { g } { \cdot } \mathrm { c m } ^ { - 3 }$ ，参考表面张力 $3 6 . 9 4 ~ \mathrm { { \fontfamily { q p l } { N \cdot m ^ { - 1 } } } }$ 。由于本研究中的带电离子没有考虑大小，采用均质核化的核化率计算公式，

$$
J _ { { { \it c l } } } = \rho _ { l } ^ { - 1 } \sqrt { \frac { 2 \gamma } { \pi m } } \rho ^ { 2 } \exp ( - \frac { \Delta G _ { \mathrm { h o m } } ^ { * } } { k _ { B } T } )
$$

计算得出的核化率的大小为 $4 . 8 9 { \times } 1 0 ^ { 2 8 } / ( \mathrm { c m } ^ { 3 } { \cdot } \mathrm { s } )$ 。此外根据核化率定义，可从团簇分析方法求得核化率，图6给出了包含分子数大于一定阈值的团簇团簇数随时间的变化，阈值分别为10、20、30、40、50。当阈值为10时，系综内团簇数先迅速增加后降低，变化不稳定。当阈值大于20时，团簇数增加的斜率基本相同，从而可以根据其变化的斜率统计获得核化率。图中的虚线为团簇生长阶段的线性拟合，此时对应的系综内包含 $2 0 \mathrm { { N a } ^ { + } / C l }$ 离子时水蒸气核化的核化率约为 $1 . 0 1 { \times } 1 0 ^ { 2 8 } / ( \mathrm { c m } ^ { 3 } \ \mathrm { s } )$ ，与经典核化理论预测值在同一数量级，高于文献[8]计算得出的均质核化的核化率值 $2 . 8 \times 1 0 ^ { 2 7 }$ $/ ( \mathrm { c m } ^ { 3 } { \cdot } \mathrm { s } )$ ，说明离子的存在对水蒸气核化有促进作用。采用同样的方法根据团簇分析得出系综内包含50、100、200 $\mathrm { N a ^ { + } / C l ^ { - } }$ 离子时对应的核化率依次为， $1 . 5 4 \times 1 0 ^ { 2 8 } / ( \mathrm { c m } ^ { 3 }$ s)、$2 . 2 7 { \times } 1 0 ^ { 2 8 } / ( \mathrm { c m } ^ { 3 } \ \mathrm { s } )$ 、 $4 . 5 2 \times 1 0 ^ { 2 8 } / ( \mathrm { c m } ^ { 3 } \ \mathrm { s } )$ ，核化率随离子浓度的增加而非线性的增加。

![](images/b85da7e2487abdd3fb359c5173daa796c6ac72f0d439ea746524fe43acbadaf9.jpg)  
图6系综内团簇数随时间的变化（ $2 0 \mathrm { N a ^ { + } / C l ^ { - } }$ ） Fig.6 Evolution of clusters larger thana threshold size in the nucleation process with $2 0 \mathrm { N a } ^ { + }$ and $2 0 \mathrm { C l ^ { - } }$ ions

# 4结论

本文建立了 $\mathrm { { N a ^ { + } / C l } }$ 离子存在时水蒸气核化的分子动力学模型，模拟研究 $\mathrm { { N a ^ { + } / C l } }$ 离子及离子浓度对水蒸气核化的影响，分析核化过程温度、势能的变化，根据团簇分析及经典核化理论预测离子存在时水蒸气的核化率。结果发现，在核化初期，离子的存在能够促使核化发生，但随着核化进行至动态平衡时，离子浓度对系综内最大团簇大小影响较小。以含 $2 0 \mathrm { { N a } ^ { + } / C l ^ { + } }$ 离子系统为例，根据核化率定义由团簇分析统计得出核化率约为 $1 . 0 1 { \times } 1 0 ^ { 2 8 } / ( \mathrm { c m } ^ { 3 } \ \mathrm { s } )$ ，高于均质核化系统，且与经典核化理论计算值$4 . 8 9 { \times } 1 0 ^ { 2 8 } / ( \mathrm { c m } ^ { 3 } \mathrm { s } )$ 在同一个数量级。

# 参考文献

[1]孙斌，刘阳．纳米流体绕包裹泡沫金属圆管外流动换热 的数值模拟[J]．东北电力大学学报,2016,36(3):41-46 SUN Bin, LIU Yang.Numerical Simulation of Nanofluid Flow and Heat Transfer Around Solid Cylinder Wrapped with Metal Foam[J]. Journal ofNortheastDianli University, 2016,36(3): 41-46   
[2]刘炜．四元混合熔融盐热物性的理论预测与研究[J]．东 北电力大学学报,2016,36(2):45-50 LIUWei. Theoretical Prediction Andstudy on the Thermal Property of Quaternary Hybrid Molten Salts[J].Journal of Northeast Dianli University,2016,36(2): 45-50

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

[3] 杨军，陈宝君，银燕．云降水物理学[M]．北京：气象出 版社,2011 YANG Jun, CHEN Baojun,YIN Y an. Physics of Clouds and Precipition [M]. Beijing:China Meteorological Press, 2011   
[4] Winkler P M,Steiner G,Vrtala A,et al,Experimental Determination of Critical Cluster Sizes from Moleular Ion Clusters to Nanoparticles[J]. Science,2008,319:1374-1377   
[5]Inci L,Bowles R K,Heterogeneous Condensation of the Lennard-Jones Vapor onto a Nanoscale Seed Particle[J]. The Journal of Chemical Physics,2011,134:114505   
[6]张超，王跃社，李晨沛．离子诱导水蒸气核化过程的分 子动力学模拟[J]．中国科学院大学学报，2016，33(2): 228-233 ZHANG Chao,WANG Yueshe,LI Chenpei.Molecular dynamics simulation of water vapor nucleation induced by

ions [J].Journal of University of Chinese Academy of Sciences,2016,33(2):228-233 [7]周健，朱宇，汪文川等．超临界NaCl水溶液的分子动力 学模拟[J]．物理化学学报,2002,18(3):207-212 ZHOUJian,ZHUYu,WANGWenchuan etal.Molecular Dynamics Study of Supercritical Aqueous Sodium Chloride Solutions [J].Acta Phys.-Chim. Sin.2002,18(3): 207-212 [8]宋粉红，刘朝，刘娟芳等．水蒸气在固体颗粒上异质核 化的分子动力学研究[J]．工程热物理学报，2013，34(10): 1813-1817 SONG Fenhong,LIU Chao,LIU Juanfang etal.Molecular Dynamics Simulation ofHeterogenous Nucleation of Water Vapor on Nanosolid Particle[J]. Journal of Engineering Thermophysics,2013,34(10):1813-1817

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538