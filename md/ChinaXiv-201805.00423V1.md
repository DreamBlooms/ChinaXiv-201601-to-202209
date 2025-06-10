# 基于PAT的PCV2VLPs生产过程优化与控制研究

化磊召 易小萍\* 储炬 庄英萍 张嗣良(华东理工大学生物反应器工程国家重点实验室 上海 200237)

摘要：昆虫细胞-杆状病毒载体表达系统（Baculovirus expression vector system,BEVS）是病毒样颗粒亚单位疫苗（Virus like particles,VLPs）的理想生产平台。动物细胞培养过程分析技术（Process analytical technology,PAT）研究的重点在于更多地获取与细胞生理状态相关的过程参数，以及实现过程敏感参数的在线表征和过程控制关键时间节点的在线判定，从而指导过程优化和控制。本研究通过昆虫 Sf9 细胞的分批和补料悬浮培养，发现细胞代谢活性与在线特征频率（f）之间存在相关性。以f作为细胞代谢活性的在线指征，在细胞代谢活性下降之前补料，使得 Sf9 细胞在代谢活性明显增强的基础上，最高活细胞密度提高1.75倍。通过分批培养与补料分批培养过程细胞生理特性参数的相关性分析，发现比电容增长速率（ ${ \bf { \bar { \rho } } } _ { \mu _ { \varepsilon } }$ ）与培养体系S-期细胞比例之间存在相关性， $\mu _ { \varepsilon }$ 作为细胞增殖活性状态的在线指征参数，可以作为最佳接毒时间的判定依据。此外，研究还发现在线检测参数电容（ε）与最高疫苗产量之间存在相关性，可以作为疫苗最佳收获时间的在线表征参数。以在线f值作为补料时间指征，以在线 $\mu _ { \varepsilon }$ 值作为病毒感染时间指征，以在线ε值作为病毒收获时间指征，实现了猪圆环病毒2型（PCV2）VLPs 的高效生产。相比于批培养，基于PAT的生产工艺疫苗单位体积产量提高$76 \%$ ，生产周期缩短了 $2 4 \mathrm { h }$ 。本研究为PCV2病毒样颗粒亚单位疫苗大规模生产提供了一种新的高效生产模式。

关键词：VLPs，昆虫细胞-杆状病毒载体表达系统，PAT

# Process Control and Optimization of PCV2 Production of VLPs Based on PAT

HUA Lei-zhao; YI Xiao-Ping\*; CHU Ju; ZHUANG Ying-Ping; ZHANG Si-Liang.

(EastChina UniversityofScienceandTechnology，StateKeyLaboratoryofBioreactor Engineering，Shanghai2Oo237，China)

Abstract:Baculovirus expression vector system (BEVS) is the ideal platform for Virus-Like Particles (VLPs) production. The key points of the Process Analytical Technology (PAT) in animal cell culture include obtaining cell physiological characteristic parameters, and monitoring process sensitive parameters, and controlling critical time points. These parameters in turn can promote process optimization and process control. A close correlation between cell metabolic status and on-line parameter critical frequency $( f _ { \mathrm { c } } )$ was found in Sf 9 cell batch culture. Using the $f _ { \mathrm { c } }$ as on-line indictor of cell metabolic status and feeding the culture,a 1.7 time increase of Peak Viable Cell Density (PVCD) was obtained. Besides, the metabolic status was also improved. A close correlation was found between the

proportion of S-phase cells and specific capacitance growth rate $( \mu _ { \varepsilon } )$ . It turned out that $\mu _ { \varepsilon }$ can indicate the optimized infection time point. Additionally, a high correlation was found between ε and the maximum VLPs productivity. The parameter of ε can act as an on-line indicator. Overall, an effective product mode was established by using $f _ { \mathrm { c } }$ as on-line feeding indicator, $\mu _ { \varepsilon }$ as on-line infecting indicator,ε as on-line harvesting indicator. Compared with traditional process, the volume productivity was increased by $76 \%$ .And the culture duration was reduced by $2 4 \mathrm { h }$ 、A new VLPs production mode has been established successfully.

Key words: VLPs,BVES, PAT

PCV2病毒属圆环病毒科、圆环病毒属的DNA病毒，是多种猪疾病的病原体，包括猪皮炎肾病综合征（PDNS）、坏死性肺炎（PNP）、断奶仔猪多系统衰竭综合征（PMWS）等[1-4]。感染死亡率在 $10 \% - 3 0 \%$ 之间，给全球养猪业带来巨大损失。目前主要预防方式为疫苗预防，VLPs是可针对该病原体的第三代疫苗并且已经成功上市。此类疫苗具有野生病毒的免疫原性，同时又不具备野生病毒的感染特性。其优势已经被广泛报道[5-7]。因此，其疫苗在产业界得到越来越多的关注。

BVES是VLPs的理想生产平台。该平台作为蛋白表达的真核系统具有翻译后修饰功能，如糖基化、二硫键修饰等[8]。目前已经用于治疗性蛋白的结构、功能研究，也用于动物、人用疫苗的生产[9-11]。

BVES培养系统可优化的参数包括：细胞接种密度、病毒感染复数（MOI)、病毒感染时间（TOI）、补料时间（TOF）、收获时间（TOH）、培养温度等过程参数，也包括分批培养[12]、分批补料培养[13]以及连续灌注培养[14-15]等培养方式的优化。传统优化方法主要是通过实验设计（DOE）寻找各个参数间的最佳组合。但存在实验次数多、周期长等问题。

随着质量源于设计（QbD）以及PAT理念的提出，对生产工艺的优化以及控制提出更高要求，而各种先进传感器的应用有力促进了QbD和PAT的发展。例如Zeiser[16等利用在线电容电极监测到了BVES系统中病毒对细胞的感染过程，借助红外 $\mathrm { C O } _ { 2 }$ 分析系统对培养系统 $\mathrm { C O } _ { 2 }$ 含量变化的分析，实现了BVES系统中病毒释放时间的在线监控[17]。Qiu J[18]等借助近红外光谱分析，实现了昆虫细胞培养系统中细胞密度的实时监测，同时能够监测培养系统中葡萄糖以及乳酸浓度，为培养过程控制提供控制依据。本文以PAT为指导，以活细胞传感器在线分析为基础，围绕昆虫Sf9细胞反应器生产PCV2VLPs亚单位疫苗过程进行相关研究，探索VLPs疫苗生产过程中各种生理代谢特性参数之间的相关性规律，发现最佳TOF、最佳TOI以及最佳TOH的在线表征参数,建立基于PAT的PCV2VLPs的高效生产工艺，为PCV2的反应器大规模生产奠定基础。

# 1材料与方法

# 1.1在线活细胞计数、离线活细胞计数，特征频率测定以及比电容增长速率计算

本研究采用血小球计数板测定离线活细胞密度及活性。将培养体系细胞与台盼蓝染色液1：1稀释，滴加到血小球计数板离线测定活细胞密度及活性，当细胞浓度过高时，适当稀释细胞。

在线活细胞仪型号为BM220，测定频率选定为608KHz,LowPass设定为30。比电容增长速率计算方法如下：

$$
\mu _ { \mathrm { { { \varepsilon } } } } = { \frac { \ln \varepsilon 1 - \ln \varepsilon 2 } { \mathrm { { t } } 1 - \mathrm { { t } } 2 } }
$$

# 1.2 离线 $\scriptstyle q _ { 0 2 }$ 测定

比耗氧速率采用OROBOROSOxygraph 2K 测定。每个测量室添加 $2 . 1 ~ \mathrm { m L }$ 新鲜培养基校准溶氧电极饱和点，培养的细胞用新鲜培养基稀释到 $1 . 0 \times 1 0 ^ { 6 }$ cells/mL，添加 $2 . 1 \mathrm { m L }$ 稀释的细胞培养液测定，绘制溶氧对时间的变化曲线。

# 1.3细胞线粒体膜电位去极化比例测定

取100万个培养的细胞， $1 0 0 0 ~ \mathrm { r / m i n }$ 离心 $5 \mathrm { m i n }$ 去除上清。沉淀细胞中加入${ 5 0 0 \mu \mathrm { L } }$ 冰浴预冷PBS 混匀细胞后，加入500μLJC-1染色工作液混匀， $3 7 ^ { \circ } \mathrm { C }$ 温育$2 0 \mathrm { m i n }$ 。期间配制JC-1染色缓冲液，并立即冰浴。离心温育的细胞并使用 JC-1染色缓冲液重悬，借助双波长荧光分光光度计检测细胞荧光强度。JC-1单体绿色荧光波长 $4 9 0 \mathrm { n m }$ ，发射波长 $5 3 0 \mathrm { n m }$ ，JC-1聚体红色荧光激发波长 $5 2 5 \mathrm { n m }$ ，发射波长 ${ 5 9 0 } \mathrm { n m }$ ，检测温度设定为 $2 7 \mathrm { ~ \textdegree C }$ 。

# 1.4 细胞周期测定

取50万个培养的昆虫细胞 $1 0 0 0 ~ \mathrm { r / m i n }$ 离心 $5 \mathrm { m i n }$ 后加入1mLPBS 重悬细胞,并重复一次。用 $1 \mathrm { m L 7 0 \% }$ 冰浴乙醇重悬，放置 $4 \mathrm { ~ } ^ { \circ } \mathrm { C }$ 冰箱过夜固定，之后弃去$70 \%$ 乙醇，放置 $- 2 0 \mathrm { ~ } ^ { \circ } \mathrm { C }$ 待检测。

当样品收集结束，加入1mLPBS 清洗细胞，然后加入 ${ 5 0 0 \mu \mathrm { L } }$ 染色工作液置于 $3 7 ^ { \circ } \mathrm { C }$ 培养箱温育 $3 0 \mathrm { m i n }$ 。借助流式细胞仪在激发波长 $4 8 8 ~ \mathrm { n m }$ 波长处检测红色荧光。

# 1.5 营养物的比消耗速率计算

取适量细胞培养液离心去除细胞，将离心后的细胞培养基根据预测的糖浓度稀释到 $1 \mathrm { g } / \mathrm { L }$ 附近，然后将稀释后的样品注入SBA60 检测糖浓度（Shandonginstituteoflife science)。比葡萄糖消耗速率依据以下公式计算：

$$
q _ { \mathtt { G l u } } = \frac { 2 ( C _ { G l u 1 } - C _ { G l u 2 } ) } { X _ { 1 } + X _ { 2 } }
$$

# 1.6细胞复苏、传代、扩大培养以及发酵罐设定

取冻存的 SF9细胞 $2 7 ^ { \circ } \mathrm { C }$ 迅速解冻，离心换液后将细胞转移到SFⅡI新鲜培养基中 $2 7 ^ { \circ } \mathrm { C }$ 培养，当细胞生长到 $( 3 . 0 { - } 4 . 0 ) \times 1 0 ^ { 6 } \mathrm { c e l l s / m L }$ 时，以密度 $1 . 0 \times 1 0 ^ { 6 }$ cells/mL传代或者扩大培养。当细胞生长到一定密度，以同样密度接种发酵罐，培养条件如下：搅拌转速 $6 5 \mathrm { r p m }$ ，培养温度 $2 7 ^ { \circ } \mathrm { C }$ ， $\mathsf { p H }$ 监测但不控制，溶氧关联纯氧自动控制 $40 \%$ 。

# 1.7PCV2蛋白颗粒ELISA 定量测定

分别以浓度 $1 0 0 0 ~ \mathrm { { n g / m L } }$ 、 $5 0 0 ~ \mathrm { { n g / m L } }$ 、 $2 5 0 ~ \mathrm { { n g / m L } }$ 、 $1 2 5 \mathrm { n g / m L }$ 、 $6 2 . 5 ~ \mathrm { { n g / m L } }$ 、$3 1 . 5 \mathrm { n g / m L } ( 1 0 0 \mu \mathrm { L } )$ ）或者待测样品包被孔板。 $4 ^ { \circ } \mathrm { C }$ 静置过夜后，用PBST清洗孔板3次，之后用 $5 \%$ 脱脂牛奶 $3 7 ^ { \circ } \mathrm { C }$ 封闭 $^ { \textrm { 1 h } }$ （ $\mathrm { \Delta } 2 0 0 \mu 1 / \mathrm { w e l l } )$ ，后清洗3次。2000倍稀释鼠抗PCV2Cap单克隆抗体加入孔板，并置于 $3 7 ^ { \circ } \mathrm { C }$ 孵育 $^ { \textrm { 1 h } }$ 。2000倍稀释辣根氧化酶标记的羊抗鼠抗体，每孔加入 $1 0 0 \mu \mathrm { l } 3 7 ^ { \circ } \mathrm { C }$ 孵育 $\mathsf { 1 h } .$ 后清洗4次，每孔加入 $1 0 0 ~ \mu \mathrm { l / }$ well TMB 溶液。 $3 7 ^ { \circ } \mathrm { C }$ 孵育 $1 5 \mathrm { m i n }$ 。加入 $2 \mathrm { M }$ 硫酸溶液终止反应，酶标仪 $4 5 0 \mathrm { n m }$ 读取吸光值。

# 1.8 重组杆状病毒培养

本实验室病毒由实验室自主开发，所需重组病毒颗粒来自同一生产批次，对

体系的感染复数（MOI）统一控制为0.5。

# 2结果与讨论

# 2.1分批培养细胞生理代谢变化研究以及最佳补料时间的确定

活细胞密度是细胞大规模培养中的重要状态变量，细胞生理状态的变化、操作变量的实施与变动，在很大程度上都与活细胞密度相关。本研究利用活细胞电极在线检测培养过程 Sf9 细胞的活细胞密度，发现在细胞生长的延滞期、对数生长期、稳定期，电极信号能够与活细胞密度成正相关（如图1所示)，线性拟合结果（如图2所示）显示，判定系数为 $\scriptstyle \mathrm { R } ^ { 2 } = 0 . 9 9$ ，能够很好地在细胞活性下降之前在线实时检测活细胞密度变化。

![](images/ea6b084c082a5b57d0bb75f3ee6a11712038574419a5a9786a4cc8d37247f68d.jpg)  
图1分批培养中细胞生长动力学研究 Fig.1The cell growth dynamics in batch culture

![](images/b3f73cb9e49cd3c857cce26179991c27e5d6df38710f132f22de6ce0b65f2441.jpg)  
图2分批培养中：与离线活细胞密度的线性拟合 Fig.2The liner fitting between ε and off-line measured viable cell count

细胞进入凋亡期之前，细胞膜特性以及细胞质电导率是对活细胞电容信号有显著影响的作用因子，能够保持相对恒定的状态。当细胞进入调亡期，细胞膜功能开始丧失，通透性增强，导致细胞内物质特别是带电离子的渗出。除此之外，细胞直径在凋亡期开始膨大，培养体系在活细胞密度恒定或下降的情况下生物量提高。此时电容信号增加而活细胞密度不变或者下降。即便如此，在培养的延滞期、对数生长期、平台期，在线电容信号与活细胞密度成正相关，能够在线表征培养体系活细胞密度。

细胞的代谢活性状态是细胞培养过程中的重要状态变量，对培养体系中细胞代谢活性状态进行精准的在线分析，可以帮助我们更精确地调控细胞培养过程。在实际生产应用中，为了提高设备利用率，会对培养体系进行补料操作，以此来提高细胞密度。适当的补料能够补充培养体系营养，提高细胞的VLPs生产能力，但补料同时改变培养体系渗透压等环境参数，给细胞生长形成冲击。因此补料时间是生产过程中关键的控制节点，需要在适当的时间发生。当细胞代谢活性最强时，对环境的适应能力最强，认为是最佳的补料时机。细胞线粒体是细胞能量代谢工厂，相对于细胞活性，其功能状态能够更真实地代表细胞的代谢活性，本研究在过程分析中引入了细胞线粒体膜电位去极化比例（mmp）的分析，对细胞的代谢活性状态进行分析，以便更深入准确把握培养过程中细胞生理代谢状态的变化规律。同时，细胞的比葡萄糖消耗速率（ $q _ { \mathrm { G l u } }$ ）和比氧消耗速率（qo2）是细胞生理代谢相关的重要参数。研究中利用以上两个细胞生理代谢参数，作为细胞代谢活性的离线判断标准，同时与在线的参数对比，寻求培养过程中细胞生理代谢活性性状态最佳点及其在线指征。

![](images/f49054fce6ae97944c075e6c9c5dbd2eed30616d5c79883545da374e55f73cb9.jpg)  
图3分批培养中Sf9细胞活性变化分析 Fig.3 the viability change in the batch culture

![](images/4c1bd937c23a48c5917e400954578b9e28465792a93ff6c02d0cc9ff19894d74.jpg)  
图4分批培养中Sf9细胞的代谢活性状态分析Fig.4Themetabolic statusanalysisinthebatchculture

研究发现（如图3所示)，在细胞培养的初始阶段，由于细胞对环境的适应，线粒体膜电位去极化比例相对比较高。随着细胞对环境的适应，细胞线粒体膜电位去极化比例逐渐降低，在细胞培养的第 $4 0 \mathrm { { h } }$ 细胞进入对数生长期，细胞代谢旺盛，线粒体膜电位去极化比例稳定在一个相对较低的比例。细胞在培养 $1 2 0 \mathrm { h }$ 后，细胞活性和细胞生长速率开始下降，进入减速区，此时线粒体膜电位去极化比例快速上升，细胞活性和线粒体膜电位去极化比例存在高度的相关性。

由于葡萄糖的彻底氧化分解发生在线粒体内，线粒体膜电位去极化比例的变化影响着葡萄糖和氧气的消耗。当细胞处于对数中期，细胞代谢旺盛，线粒体膜电位去极化比例相对较低，细胞的 $q _ { 0 2 }$ 和 $q _ { \mathrm { G l u } }$ 则相对比较高。当细胞生长进入减速期，线粒体膜电位去极化比例开始升高，预示着细胞代谢活性状态的下降。此时细胞的 $q _ { 0 2 }$ 值和 $q _ { \mathrm { G l u } }$ 值也显著降低，且 $q _ { 0 2 }$ 的快速下降早于 $q _ { \mathrm { G l u } }$ 。细胞代谢活性下降时间节点明显早于细胞活性下降时间节点，提示在实际细胞培养过程只检测细胞量和细胞活性以及葡萄糖代谢存在一定的滞后性，利用 $q _ { 0 2 }$ 的变化指示细胞的代谢活性状态变化更及时、更准确。

为了实现对培养过程细胞代谢活性状态的在线分析，本研究利用活细胞电极引入了Sf9 细胞培养过程的在线特征频率 $f _ { c }$ 值分析。从图4分析可发现，当 $f _ { c }$ 值降低到最低点附近时， $q _ { 0 2 }$ 快速上升，表明此时细胞处于最旺盛的代谢活性状态。当 $f _ { c }$ 值从最低值明显上升时， $q _ { 0 2 }$ 值的上升趋势开始减弱，并随着 $f _ { c }$ 值的快速上升，qo2值发生快速下降，qo2变化与在线 $f _ { c }$ 值变化之间存在高度的相关性，可以作为细胞代谢活性状态和补料操作的判断依据。由于病毒的繁殖依赖于宿主细胞的代谢活性，因此，在线参数 $f _ { c }$ 值也可以作为最佳病毒感染时间选择的辅助判断依据。

# 2.2分批与补料培养细胞生理代谢变化比较

![](images/b2173f7b1c9f8201793847238d3ee3a7e654e8341ce4640efe44c5a8023ed07f.jpg)  
图5昆虫Sf9细胞培养最佳补料时间的确定 (箭头代表补料操作)Fig.5 The identification of optimal feeding time for the Sf9 culture(fed at the arrow-labeled point)

细胞的比生长速率是表征细胞生长增殖状态的重要生理参数。由于在线电容值与细胞量之间存在高度的相关性，利用在线电容值ε计算的在线比电容值 $\mu _ { \varepsilon }$ 与细胞的比生长速率之间也存在高度相关性（数据未列出)。分批培养的研究结果表明，在线 $\mu _ { \varepsilon }$ 值与细胞的生长增殖状态存在高度的相关性，可以用来在线表征细胞生长增殖状态变化。结合在线分析的 $f _ { c }$ 和 $\mu _ { \varepsilon }$ ，确定了最佳补料操作时间的在线判定依据（如图5所示）。

细胞培养进行到 $2 4 \mathrm { h }$ 时， $f _ { c }$ 趋于稳定，此时活细胞密度为 $1 2 \times 1 0 ^ { 6 }$ cells/ml在培养 $2 4 { - } 5 8 \mathrm { ~ h ~ }$ 之间， $f _ { c }$ 稳定于 $3 5 0 \mathrm { H z }$ 的最低位附近，且 $\mathcal { \mu } _ { \varepsilon }$ 处于较高位，在此区间细胞的生长增殖和代谢活性处于最佳状态，选择 $f _ { c }$ 上升和 $\mu _ { \varepsilon }$ 下降之前，即 $6 0 \mathrm { h }$ 左右对培养体系进行补料。与分批培养相比，补料后，细胞经过短暂的适应期后，即进入对数生长模式。补料后培养体系达到最大活细胞密度 $2 1 \times 1 0 ^ { 6 } \mathrm { c e l l s / m l }$ ，相对于分批培养，最大活细胞密度提高1.7倍(如图6a所示)。

![](images/437ca7815d8695a93321a043d3c330ec16ed3c26d283435360d31f07325599f6.jpg)  
图6a分批和补料培养体系的细胞生长对比 (箭头代表补料操作）

![](images/18cae6ea9d86b44e89d6ee3caf4606712c23f12d3cf6fc71a53a3127ed632e10.jpg)  
Fig. 6 a The peak viable cell count increased by feeding (fed at the right   
图6b分批和补料培养体系的细胞比生长速率对比 Fig. 6 b The specific cell growth rate increased by feeding

![](images/c6943bce6f4935a3be2df3be49f8d21e6dc4692b7506d0beab32533fbbdca941.jpg)  
图6c分批和补料培养体系细胞 S-期细胞比例分布对比 (箭头代表补料操作) Fig.6 c S-phase cells increased by feeding (fed at the right arrow)

最高活细胞密度的大幅度提升，与细胞增殖活性提高有关。对比分批培养与补料分批培养的细胞比生长速率分析发现：补料的添加，明显提高并维持了细胞培养后期的比生长速率（图6b)。补料后细胞比生长速率下降，也说明了补料对细胞本身冲击作用的存在。

进一步对比分析发现，活细胞密度的提升，细胞比生长速率的提高与维持，可能与培养体系 S-期细胞比例分布的上升有关（图6c)。补料中丰富的营养更能促进细胞的分裂增殖，使得 S-期细胞比例提高，从而培养体系具有更大的比生长速率与更高的活细胞密度。同时，S-期细胞物质合成活跃，具备病毒增殖复制的酶体系，对病毒的增殖复制更加有利。

![](images/55dae5a07c601934ae71309b2b352756200691561369474309dd0bdff5f96b84.jpg)  
图6d分批和补料培养体系细胞比葡萄糖消耗速率对比 (箭头代表补料操作) Fig. 6 d The $q _ { G l u }$ increased by feeding in the culture (fed at the right arrow)

![](images/ab77d7f2ebc5118292c69c93da9d7dfbd7e03d0967b83e9d3be0e7856d5ef32d.jpg)  
图6e分批和补料培养体系细胞比耗氧速率对比 (箭头代表补料操作)

Fig. 6 e The cell specific oxygen consumption increased by feeding (fed at the right arrow)

VLPs的生产过程中，病毒不仅要借助昆虫细胞的物质合成系统，同时需要依赖细胞的能量代谢系统。因此，VLPs的高效表达，不仅仅需要提高培养体系的活细胞密度，而且需要提高培养体系的能量代谢活性。

葡萄糖是培养体系的主要碳源，为细胞的生长增殖提供能量。细胞呼吸是细胞产生ATP 的主要途径，细胞 $q _ { 0 2 }$ 是与细胞代谢状态直接相关的细胞生理代谢参数。此外，病毒繁殖完全依赖于宿主细胞的能量，病毒繁殖与细胞的呼吸强度也高度相关。因此，我们以 $q _ { \mathrm { G l u } }$ 及 $q _ { 0 2 }$ 为主要考察指标，研究了细胞能量代谢活性的变化。在补料添加之前，分批培养与补料分批培养具有相似的 $q _ { \mathrm { G l u } }$ 变化趋势，不同的是分批培养中细胞 $q _ { \mathrm { G l u } }$ 变化更加剧烈，当达到顶点后随即快速下降，这种现象可能与分批培养中某一营养因子的迅速耗竭有关。而在分批的补料培养中，补料使得细胞 $q _ { \mathrm { G l u } }$ 略有降低，但此后细胞在较高 $q _ { \mathrm { G l u } }$ 水平维持至培养后期，说明补料操作，使得细胞代谢活性更加旺盛，且维持时间更长。与 $q _ { \mathrm { G l u } }$ 变化规律相似,补料的添加，明显促进了整个培养过程 $\mathrm { O } _ { 2 }$ 的消耗。表明补料操作显著促进了细胞的能量代谢活性，且使得培养体系在旺盛的代谢状态下能维持更长时间（图6d、图6e)。

# 2.3分批培养与分批补料培养中病毒感染时间的在线指征

![](images/9a6716a07be7aefae7ef4e546e516eadeeb00b46c47fccedc0bccedccf7d772b.jpg)  
图7分批培养中细胞增殖活性变化

![](images/00e1727fbbe73916bf14cd066425191440f3c0cc7d57dcbc036fc2ba71a09bb9.jpg)  
Fig.7The cell proliferation ablity in batch culture   
图8分批补料培养中细胞增殖活性变化(左箭头代表补料,右箭头代表感染) Fig.8The cell proliferation ability in fed-batch culture(infect at arrow) (fed at the left arrow, infected at the right arrow)

病毒在细胞中的增殖复制需要依赖细胞的酶体系，因此病毒对细胞的感染依赖细胞的分裂复制周期，处于S-期的细胞具备DNA复制的相关酶，是病毒早期蛋白表达的前提，当S-期细胞比例处于较高位，细胞被抑制在S-期时，病毒感染效率最高。研究中借助细胞周期的离线分析，寻求与之相关的在线参数。数据表明：在分批培养与补料的分批培养中，S-期细胞比例与在线 $\mu _ { \mathrm { { s } } }$ 值呈现较高的相关性，在培养过程中能够作为其在线表征参数(图7和图8)。由于病毒的繁殖依赖于宿主细胞的增殖和代谢活性，结合离线 S-期细胞比例与 $q _ { 0 2 }$ 值以及在线u和在线 $f _ { c }$ 值的相关性分析，以在线 $\mu _ { \mathrm { { s } } }$ 为主判定参数，在线 $f _ { c }$ 值为辅助判定参数，并考虑到S-期细胞比例变化早于在线 $\mu _ { \mathrm { { s } } }$ 值变化，确定分批培养和补料培养最佳接毒时间分别为 $3 6 \mathrm { h }$ 和 $9 6 \mathrm { h }$ 左右。

# 2.4分批培养与分批补料培养中病毒收获时间的在线指征

疫苗生产过程中，实现对关键过程参数—疫苗产量最高时间节点的在线监控，将会极大提高对疫苗生产过程的调控效率，实现最大产物收获。分批和补料培养数据表明(图9和图10)，疫苗产量最高的时间节点与在线电容信号最大值存在高度的相关性，能够作为分批培养疫苗产量最高点的在线指征参数。

![](images/a10f4ec2f39c6f7fa2c6f9170cc0e94547cb995e0fbdbf4d36d8636430c5bb13.jpg)  
图9分批培养中VLPs产量与ε变化情况

Fig.9 On-line parameterε and Max. volumetic VLPs production in fed-batch culture

![](images/ff06cdd37fba2906fdfcdbb41c5d353c6bc44860894c88769b21be69d4b3a62d.jpg)  
图10补料培养体系VLPs产量与在线电容ε变化情况 Fig.10 On-line parameterε and Max. volumetic VLPs production in fed-batch culture

在线活细胞电极产生的电容信号是多个变量相互作用的结果，其中最敏感、最关键的因素—细胞膜极性的强弱对电容信号影响最显著。在培养后期，细胞在病毒感染、营养耗竭等因素下诱发自身凋亡机制。在细胞转向死亡的过程中，细胞膜极性发生显著变化。在这一过程中细胞膜极性完全丧失，电容信号开始下降。之后死亡细胞发生裂解，释放各种水解酶类，导致疫苗产量的下降。因此，电容峰值能够作为疫苗产量最高这一关键时间节点的在线指征参数。

# 2.5基于PAT生产工艺与传统生产工艺的对比

通过与传统优化工艺进行对比分析，发现传统优化生产工艺存在以下的瓶颈：首先，以活细胞密度以及细胞活性作为过程调控的依据，不具备实时性，并且细胞计数等操作误差大，结果不可靠；其次，传统工艺很难降低批次间的差异性。由于细胞培养的自身特点，不同批次生产中细胞的扩增，接种密度以及初始培养体积，不可能达到完全一致。这就导致工艺控制标准无论是选取活细胞密度还是培养时间，都很难精准与实时的细胞代谢状态相关联。此外，传统工艺以在线的活细胞密度为工艺控制指标，缺乏实时性。首先离线活细胞密度不能连续获取，其次，通过血小球计数板法获得的活细胞密度受操作员操作习惯影响大，因此极易在批次间发生产品的产量和质量问题，很难确保批次产品的稳定性和重复性。

本研究借助先进的活细胞传感技术，对于PCV2VLPs生产的工艺进行了研究,建立了一套高效的基于PAT的PCV2VLPs生产工艺。基于PAT的PCV2VLPs疫苗生产，补料培养的最大细胞密度相比于批培养提高1.7倍（图11)，疫苗产量提高 $76 \%$ （如图12所示)，培养周期缩短了 $2 4 \mathrm { h }$ ，提高了设备利用效率。而且基于PAT的工艺优化方法较传统优化方法更高效，可大大节约工艺优化周期，且通过在线参数的表征来指导和控制生产过程，能更有效确保批次产品的稳定性和重复性。

![](images/7dd6c8f16b4b68dc306f77f1e60913f24ae9433c41cdeb5a579fd3525f318952.jpg)

![](images/cb44bbe7596f2ef1edc2c9260eea4339b2182c4c3a8880e8017ea89f7e9291cc.jpg)  
图11分批培养与补料分批培养中最高活细胞密度对比 Fig.11 Comparison of PVCD between batch culture and feed-batch cuture   
图12基于PAT的优化工艺与传统工艺产量对比 Fig.12 Comparison between traditional process and PAT process

# 3总结

本文围绕昆虫Sf9细胞生产PCV2VLPs疫苗进行了相关的研究，以发现疫苗生产过程中各种生理代谢特性参数之间的相关性规律，确定相关的在线表征参数作为最佳补料时间、最佳病毒感染时间以及最佳疫苗收获时间的判定依据。

通过对昆虫Sf9细胞分批培养的各种生理代谢参数相关性分析发现，在线ε值变化与活细胞密度存在相关性，可以用来表征活细胞密度。在线 $\mu _ { \varepsilon }$ 变化与细胞生长增殖速率变化存在一定相关性，可以用来表征细胞生长增殖速率。在线 $q _ { 0 2 }$ 和在线f变化与细胞的代谢活性状态变化存在一定的相关性，可以用来在线表征细胞的代谢活性状态变化。此外，在线‘变化和 $f _ { \mathrm { c } }$ 变化与细胞活性状态变化之间也存在一定相关性，可以用来在线表征细胞活性状态变化。

以分批培养的细胞生理特性参数相关性分析为依据，以f变化作为最佳补料操作时间的在线指征参数，确定了最佳补料操作时间，补料培养使得培养体系最高活细胞密度达到 $2 1 \times 1 0 ^ { 6 } \mathrm { c e l l s / m l }$ ，相对于分批培养的最高活细胞密度 $1 . 2 \times$ $1 0 ^ { 7 } \mathrm { c e l l s / m l }$ 提高1.7倍，实现了Sf9细胞的反应器高密度培养。通过分批培养和补料培养细胞生长增殖活性和代谢活性的对比分析发现，补料操作不仅大幅度提高了培养体系的活细胞密度，同时提高了培养体系的细胞增殖状态以及代谢活性状态。

以特征频率值 $f _ { \mathrm { c } }$ 的变化作为补料操作的在线指征参数，以比电容值 $\mu _ { \mathrm { { s } } }$ 作为病毒感染时间的在线指征参数，以及最大ε作为疫苗产物收获时间的在线指征参数，实现了PCV2VLPs的高效生产。基于PAT的PCV2VLPs疫苗生产，补料培养疫苗最高产量相比于批培养提高了 $76 \%$ ，生产周期缩短了 $2 4 \mathrm { h }$ ，明显提高了设备利用效率。而且基于PAT的工艺优化方法较传统优化工艺优化方法更高效，可大大节约工艺优化周期。同时，各种在线生理特性参数的获取，方便了生产操作，能够保证批次生产的稳定性和重复性，保证产品质量。