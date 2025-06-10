# 区域微电网集群技术研究新进展

万庆祝 薛潺

(北方工业大学电气与控制工程学院北京100144)

![](images/9dbb904cc5999390c738d2de6012dbc255d3f885bc8ec6986f4e028097019e66.jpg)

万庆祝男1975年生，博士，副教授，研究方向为分布式发电。

摘要：高渗透率分布式电源接入配电网后，传统配电网调度系统不满足对微电网的监控要求，使得大量分布式电源处于不可控状态，为了使分布式电源协调可控，微电网集群技术的研究很有必要性。本文首先描述了微电网集群的概念、结构及组成，研究了高渗透率接入情况下区域微电网集群运行特性与划分方法，设计了基于时空分布的微电网集群控制框架。

关键词：高渗透率 微电网集群 控制框架 系统结构时空分布中图分类号：TM73

# The New Progress on Technology of Regional Micro-Grids Cluster

Wan QingzhuXue Chan (Institute of Electrical and Control Engineering North China University of TechnologyBeijing 100144 China)

![](images/9d698252bfed7bc1c4b2f259647e861a58b4080ed7f5fd96f28aad89b7ebebd8.jpg)

薛潺女1993年生，硕士研究生，研究方向为分布式发电。

Abstract: Distribution network with high permeability of distributed power plant will cause many problems, plenty of distributed power plant under the status which cannot be control, traditional network cannot achieve the goal which control the distributed power plant,in order to make the microgrids controllable and coordinate,it’ s necessary to have research on the technology of microgrids cluster. These paper firstly briefly describe the conception, structure and constitution of microgrids cluster, discuss the synthetical operating characteristic access method and output characteristic of different kinds of clusters,have a design about the cluster control frame of microgrids which base on spatial and temporal distribution.

Keywords: High permeability,micro-grids cluster, frame on control, system structure,space-time distribution

# 1 引言

由于分布式电源（Distributed Generation，DG）[1]具有不同属性，并且数量多而分散，如果没有一套相应的调度体系就无法保证调度指令能够快速、有效、准确地传达并且执行，因此在配电网中，直接调度和管理大量分布式电源的有效解决办法就是将分布式电源进行集群化，形成微电网集群（micro-gridscluster)。配电系统中有大量微电网集群存在会改变电力系统配电网的结构与运行方式，虽然会产生一些技术层面的困难需要克服，但是可以实现分布式电源和配网系统的有效集成[2]。

本文研究的区域微电网集群建立在高渗透率分布式电源接入配电网的基础上，突破传统的微电网控制模式，讨论了一种新型的微电网发展模式。通过对微电网进行控制框架和系统结构的研究分析，在对微电网进行集群化后，按照微电网的时空分布，实现对微电网的有效管理，降低分布式电源个体对配电系统安全性的影响。

# 2 微电网集群的概念、结构及组成

# 2.1基于聚类分析的微电网集群概念

电力系统遵循一定的运行模式，按照机组组合、超前调度、在线调度及实时控制等不同的时间级进行模式叠加，最终实现电力系统的自动控制[3-4]。电力系统的自动控制来源于电源的可靠性和负荷在大范围、大时间区域内的可被预测来进行的。由此看来，风电、光伏发电等间歇性新能源在可靠性和可预测性方面均达不到电网标准。因此，随着新型能源的渗透率不断提高，探索先进的、可用于分布式电源的运行模式和控制策略显得尤为必要。

聚类分析（clusteranalysis），又称群分析，是根据“物以类聚”的道理，对样品或指标进行分类的一种多元统计分析方法，它们讨论的对象是大量的样品，要求能合理地按各自的特性来进行合理的分类[5-6。本文将分布式电源进行聚类划分，进而将它们集群化。例如将一个地区内所有的风力发电设备进行聚类，形成本地区风力微电网集群；所有的光伏发电设备聚类形成本地区的光伏微电网集群；同时风光、风储和风光储等混合能源微电网集群也参与其中。通过聚类使得各种分布式电源形成规模较大的、集群内部类型统一或互补的分布式电源模块，便于统一进行实时控制。进行聚类划分能够改善电能质量，配套适应配电网继电保护系统，提高

系统的安全性和可靠性，便于进行实时的监视、控制和调节，通过协调可以达到电网效益最大化。这样形成的微电网集群能够保证在故障状态和非正常运行状态中，不仅集群内部可以进行调整，集群之间经过通信也可以进行协调控制，使得整个微电网集群包括配电网的稳定性和安全性都得到极大提高。

# 2.2系统内部结构

微电网在形成规模化集群化后因其地域分布较广且具有统一的公共连接点集中并网，必然要进行分区分层控制。微电网集群引入多代理系统（multi-agent)，其基本单元是代理(agent)，系统由多个代理组成，代理可以与其所在环境进行互动[7-8]。微电网集群分层分区控制框架如图1所示。

![](images/15e9a659d2663387d20bafcebbbb1b48564d95e8336d6ab8c160e156e11335fc.jpg)  
图1微电网集群分层分区控制  
Fig.1 Hierarchical distributed control in micro-grids cluster control

由图1可以看出，区域控制中共有3层协调控制，每层控制中都有相应的代理模块，信息层层传递，保证每层的信息都能分别向上下级传达。从配电网侧看可发现，分布式电源集群分层分区控制将整个分布式电源集群形成的微电网当作一个整体的、可控可调度的稳定电源进行协调和控制。风电场、储能、光伏电站、风储系统、光储系统、风光系统和风光储系统设有监控设备，进行电压、频率和稳定性等各方面的协调；集群协调控制的执行站可通过标准接口反映给上级子站；调度中心处在“总代理”的地位，实现对下级所有数据交互、供需实时性需求和经济性的协调控制并连接用户，将历史数据和实时数据进行传递和交互。这样通过3层协调，使得整个集群可观测可控制。

# 2.3区域微电网集群系统结构

在微电网集群中，微电网需具有一些特性来保证微电网接入配网后配电网能够保证安全可靠运行。某风光储微电网集群系统简化结构图如图2所示。

![](images/bcd633a7479fb2414e7160312ae3139720425b6f82ce656cfab8ff64fd76ed2d.jpg)  
图2风光储微电网集群系统简化结构图 Fig.2Simplified structure in wind/light/battery of microgrids cluster system

从图2可以看出，微电网集群是一个大型的综合性的系统，集群内部紧密联系，集群之间也互相联系，相互协调进行控制。

微电网集群需有如下特性：

(1）可与配电网并网或孤岛运行，充分发挥作  
为新型能源的区域集群优势和时空互补优势，既可  
以对配电网售购电，又可以支持配电网的安全运行。(2）微电网的动态特性可以反映到集群上，例  
如当需要全力支持某一微电网运行时，集群表现的  
是这一微电网的特性，集群中其他的微电网模块无  
需考虑经济性等因素。(3）集群中的任意一个微电网至少有另外一个  
微电网与之相连，这样才能集群化作业。（4）每个微电网集群中应有自己的资源控制系  
统，对自身的内部资源进行整合、优化和再组合。（5）集群拥有属于自己的经济运行策略，当需  
要在大区域内反映自己的集群特性时能够直接向集  
群反应自身特性。）

(6）集群需要拥有自己的安全系统，保证集群

能够安全稳定运行。

图2中，微电网1、微电网2、微电网3与微电网4都是相互独立的微电网集群模块，每一个微电网集群都至少与另外一个微电网集群相连，微电网集群1、2、3表现为微电网集群1的需求特性，微电网集群4单独运行，保证自己的供需平衡。微电网集群内部都包含着风光储等各种分布式电源，以微电网集群2为例，包含有风机、太阳能和储能分布式电源模块，也包括自己的经济运行策略 (软件)和安全保障系统。

# 3高渗透率接入情况下区域微电网集群划分方法与运行特性

根据分布式电源随机输出功率的特点，将不同的较多的机组组合成的微电网进行重新分组，建立风电、光伏、光储、风光、风储及风光储的微电网集群模型。

# 3.1风力微电网集群（ $\mathbf { 1 0 0 0 k W }$ 及以上)

随着风电能源的大规模开发，风电场数量急剧增加，而且风力发电区域性极强，往往沿着同一风带梯级能建设若干个风电场以便于风能的合理利用，且单机、单场容量也急剧上升，这样就形成了超大的风电场微网群[9。基于现有的以单个风电场为单位、各自独立调节的方式已无法满足地区电网的调压调频需求，因此需要将风电场群及其汇集站作为一个微电网，进行汇集站和集群中心站的协调控制，通过系统的优化，整体实行能量、电压、频率及成本各方面的管理[10]。图3为典型的风电场集群汇入系统拓扑图。

![](images/af2c5b9197b8209980684478ea4c30fc3bd6fd0d9105307d0cdf290ca688abe5.jpg)  
图3典型风电场集群汇入系统拓扑图 Fig.3A typical wind farm cluster topology into the power system

风力微电网集群的无功电压协调控制是风力发电重点需要解决的问题[11-18]。

# 3.2光伏微电网集群

大型光伏电厂因装配集中、设备容量较大，故中高压接入配电网，呈现集中大规模的特点。光伏发电的容量不同、并网方式不同及系统配置不同决定了光伏发电需要更高的要求以接入配电网。并网光伏发电系统主要由光伏阵列、逆变器及其他并网环节组成，光伏阵列由光伏电池电网串并联组成，逆变器和相应的滤波器将光伏电池板产生的电能输送到电网，在此过程中需要对逆变器和电能变换环节进行最大功率点追踪控制（MaximumPowerPointTracking，MPPT）和逆变控制[19]。大型并网光伏电站集群基本构架如图4所示。

![](images/2460b1cd9c4aa98672305aaa9144532c248346998382a08535db62ce4359fca3.jpg)  
图4大型并网光伏电站集群基本构架  
Fig.4Large grid photovoltaic power system station clustei

basic framework

大型光伏电站在光伏阵列、变换器及并网方面存在一系列问题，如组件性能差异，多台逆变器并联运行产生放大的环流谐波，本地电网产生电能质量、电压波动和孤岛等问题[20]。未来光伏发电集群化聚类化接入电网时对其负载特性、电网调度、电压无功和保护等诸多方面有影响，因此需要有与之相适应的、解决目前光伏并网一系列问题的措施和方案。

# 3.3风光、风储、光储与风光储微电网集群

现阶段集群研究较为广泛的还有风光、风储、光储与风光储微电网集群。当风电场容量为$1 ~ 0 0 0 \mathrm { k W }$ 以下 $1 0 \mathrm { k W }$ 以上时，风电场一般采取风光互补集群的方式进行并网。当风电场容量小于10kW时，风电场一般采用直流并储能集群的形式。风电场、光伏发电作为新型能源都具有间歇性和不确定性特征。大规模的风电场和光伏电站往往都建立在较为偏僻的地区，接入电网会对电力系统功率平衡造成不利影响。这时可以利用两种及以上不同的发电方式进行并网运行，既可以有效调整平衡不同分布式电源出力的不确定性，又可以通过集群控制，协调各部分出力的安全性和可靠性。以上4种微电网集群可以协调出力达到供电经济安全可靠的目的[22-24]

# 4基于时空分布的微电网集群控制

微电网集群是将地理上毗邻、特性上相关且共同拥有一个接入点的风电场、光伏电站等分布式电源进行一体化整合，形成微电网集群，集中进行协调控制，能够有效平抑单一小型分布式电源，例如风能可能出现的波动性、随机性和光伏发电出现的间歇性，因储能模块和风、光的互相调度补充，当分布式电源发电时储能模块充电，夜晚光伏发电不工作时，风力发电为主供电，当风光均达不到要求时由储能模块供电，尽量形成在规模和外部调控特性上都与常规电厂相近的电源，具备灵活响应电网调度与控制的能力，适应高渗透率分布式电源的发展现状，能够有效提高间歇式电源利用率。

微电网集群控制技术是微电网集群控制系统的核心部分。结合微电网集群的出力特性和当地电网的实际特点因地制宜使控制技术显得尤为重要。控制策略的公开公平公正涉及诸多业主的切身利益，因此，微电网集群间的协调调度不仅仅要考虑技术问题，还要考虑经济问题。这就需要建立完整的购馈电机制，以实现微电网集群间、集群与电网间电能交互的公平公正。因分布式电源本身具有一定层次性，在进行分层分区协调控制的同时，时间、空间指标都要进行深层考虑。因此各项功能均有协调上升的空间。

# 4.1时空分布

# 4.1.1时间尺度

根据实时控制（分钟级超短期预测数据）调整调度计划（小时级超短期预测数据)，根据短时间的实时控制和调度计划制定长周期（日级短期预测数据）大时间段的配置整定。而各时间周期又是相互影响的，三者相互制约，形成微电网集群的时间尺度规划模式，如图5所示。

不同类型的微电网集群因不确定性和间歇性，其功率预测和实时调度不可能百分之百正确。通过一次调频、自动电压控制及紧急有功功率控制等实时控制策略，可以在短时间从安全稳定的角度实现有功功率的平衡。从无功功率角度考虑，可以基于各无功电源特性对各无功源进行实时协调控制，以实现自动无压分配功能。

![](images/a6a2af620761c4f1192f30fe4d69b24a4f42e0c7109efb325dd80dcf14ef7bf9.jpg)  
图5集群时间调度协调控制示意图

# 4.1.2空间尺度

集群能够响应配电网命令，反应微电网的需求，控制各个场站及其设备，完成发电设备之间、微电网集群之间和配电网之间的协调。集群空间调度协调控制示意图如图6所示。

![](images/1db32f03bdee6dc6d70ab93fd50a2f8d7f55a21094e2e441a1ac2cc03df6a10f.jpg)  
Fig.5The time scheduling coordination control plan of cluster   
图6集群空间调度协调控制示意图  
Fig.6The space scheduling coordination control plan of cluster

集群空间尺度的确立便于微电网内部的不同发电设备之间的横向协调和微电网到集群再到电网之间的统筹纵向协调。横向协调体现设备与设备间的互补支援，完成电压的控制，纵向协调体现了空间的传递性，电网的指令可以通过纵向协调层层传递，信息传递精确到每一台发电设备。

# 4.2集群控制模式

基于时间和空间的集群控制的目标，就是将这些在时间和空间上具有相互联系的分散的微电网系统统一起来，形成大规模的集群系统。为了实现这一目标，首先要使得集群减少对电网的影响，其次要实现集群对电网的支持能力，即正常工作时配合运行，非正常状态下或故障状态下能够提供有效的功率或切除等支持。

(1）提供有功功率支持和频率调节。集群控制需要具备能够协调其有功功率和适应其变化率的能力。首先，根据集群的空间尺度和时间尺度，集群具备能够响应上下级的有功和频率的调节，计算其经济裕度和可靠性并主动参与削峰填谷。在调频不足时，集群应具备参与短时二次调频的功能，并且能够调整电网的频率偏差。

(2）提供无功控制和电压控制。集群大面积联网的空间尺度能够保证无功功率和功率因数的稳定并且支撑电压稳定，在故障发生时可快速使电压恢复，在未解除故障时防止大面积脱网。

(3）提供安全保障系统。集群能够根据其相应的时间尺度，实行实时监控和故障报警的在线调节功能、遇到紧急情况时的紧急投切功能和在故障无法排除时的最优解列点寻找功能，以保障整个集群系统的可靠运行。

(4）保证各个部分各取所需，配合运行。因微电网形成了集群，集群内部各个部分都能够通过代理获得信息，在必要时能够从集群内部获得支持和调节。

# 5 结论

微电网集群作为一个新兴的概念目前还没有得到广泛的应用，但其作为一个新兴的调度模型和调度手段，能够平抑单一分布式电源所带来的波动性和不确定性，提高微电网的稳定性。区域微电网集群配合新型的分层分区控制、系统控制结构和基于时空分布的集群控制，显示了集群化运作的优越性。在分布式电源渗透率越来越高的今天，微电网集群有待于进一步的研究和探讨。

# 参考文献

[1] 陈卫昀，严仰光．分布式电源[J]．电力电子技术，1999，33(2):82-85.Chen Weijun, Yan Yangguang. The distributed powersystem[J].Power Electronics,1999,33(2):82-85.  
[2] 蔡德华，贺兴，王利国，等．基于互联的微电网集群化运作整体设计与实现[J]．电器与能效管理技术，2015(9)：64-71.Cai Dehua,He Xing,Wang Liguo,et al.Design andrealization of cluster operation model for multi-microgrids in interconnection network[J]. Electrical& Energy Management Technology,2015(9): 64-71.  
[3] 高中文，周苏荃，刘有斌，等．电力系统运行模式的建立问题[J]．华中电力，1994(2)：9-15.Gao Zhongwen, Zhou Suquan, Liu Youbin. Theestablishment of electric power system operationmode[J]. Central China Electric Power, 1994(2):9-15.  
[4] 刘蔚．基于运行模式的配电网优化[D]．杭州：浙江大学，2006.  
[5] 方开泰．聚类分析[J]．数学的实践与认识,1978(1).Fang Kaitai. CLuster analysis[J]. Mathematics inPractice and Theory,1978(1).  
[6] 王成山，曹旌，陈光远．基于聚类分析的电力系统暂态稳定故障筛选[J]．电网技术，2005，29(15)：18-22.Wang Chengshan, Cao Sheng, Chen Yuanguang.Power system transient stability contingencyscreening based on clustering analysis[J]. PowerSystem Technology,2005,29(15): 18-22.  
[7] 章健，艾芊，王新刚．多代理系统在微电网中的应用[J]．电力系统自动化，2008，32(24)：80-82.Zhang Jian, Ai Qian, Wang Xingang. Application ofmulti agent system in a microgrid[J]. Automation ofElectric Power Systems,2008,32(24): 80-82.  
[8] 章健．Multi Agent 系统在微电网协调控制中的应用研究[D]．上海：上海交通大学，2009.  
[9] 范国英，史坤鹏，郑太一，等．风电场集群接入系统后的聚类分析[J]．电网技术，2011，35(11)：62-66.Fan Guoying, Shi Kunpeng, Zheng Taiyi. Clusteranalysis of grid-connected large scale wind farms[J].Power System Technology, 2011,35(11): 62-66.  
[10]穆永铮，鲁宗相，申洪．汇集站和集群中心站分级协调的风场群接入系统优化规划[J]．中国电机工程学报，2014(S1)：1-8.Mu Yongzheng, Lu Zongxiang, Shen Hong. Multiplewind farms integration grid optimal planningconsidering coordination of collecting stationsand cluster stations[J]. Proceedings of the CSEE,2014(S1): 1-8.  
[11]杨硕，王伟胜，刘纯，等．双馈风电场无功电压协调控制策略[J]．电力系统自动化，2013，37(12)：1-6.Yang Shuo, Wang Weisheng, Liu Chun, et al.Coordinative control strategy for reactive power andvoltage of wind farms with doubly-fed inductiongenerators[J]. Automation of Electric Power Systems,2013,37(12): 1-6.  
[12]陈宁，朱凌志，王伟．改善接入地区电压稳定性的风电场无功控制策略[J]．中国电机工程学报,2009，29(10):102-108.Chen Ning, Zhu Lingzhi,Wang Wei. Strategy forreactive power control of wind farm for improvingvoltage stability in wind power integrated region[J].Proceedings of the CSEE,2009,29(10): 102-108.  
[13] Moursi M E,Joos G,Abbey C.A secondaryvoltage control strategy for transmission levelinterconnection of wind generation[J]. IEEETransactions on Power Electronics,2008,23(3):1178-1190.  
[14]Pappala V S, Nakawiro W, Erlich I. Predictiveoptimal control of wind farm reactive sources[C].IEEE/PES Transmission and Distribution Conferenceand Exhibition,New Orleans,2010: 1-7.  
[15]Erlich I, Nakawiro W, Martinez M. Optimal dispatchof reactive sources in wind farms[C]. IEEE Powerand Energy Society General Meeting,Detroit, 2011:143-149.  
[16]陈慧粉，乔颖．风电场群的无功电压协调控制策略[J]．电力系统自动化，2010，34(18)：78-83．Chen Huifen, Qiao Ying. Study on reactive powerand voltage coordinated control strategy of windfarm group[J]. Automation of Electric Power System,2010, 34(18): 78-83.  
[17]张洋．风电场无功补偿容量及其控制方法的研究[D]．吉林：东北电力大学，2005.  
[18]杨硕，王伟胜．计及风电功率波动影响的风电场集群无功电压协调控制思路策略[J]．中国电机工程学报，2014，34(28)：4671-4679.Yang Suo, Wang Weisheng. Coordinative strategyfor reactive power and voltage control of windfarms cluster considering wind power fluctuation[J].Proceedings of the CSEE,2014, 34(28): 4671-4679.  
[19]刘东冉，陈树勇，马敏，等．光伏发电系统模型综述[J]．电网技术，2011，35(8)：47-52.Liu Dongran, Chen Shuyong,Ma Min.A review onmodel s for photovoltaic generation system[J].PowerSystem Technology,2011,35(8): 47-52.  
[20]赵争鸣，雷一，贺凡波．大容量并网光伏电站技术综述[J]．电力系统自动化，2011，35(12)：101-107.Zhao Zhengming,Lei Yi,He Fanbo.Overviewoflarge-scale grid-connected photovoltaic powerplants[J].Automation of Electric Power System,2011,35(12): 101-107.  
[21] 赵平，严玉廷．并网光伏发电系统对电网影响的研究[J]．电气技术，2009(3)：41-44.Zhao Ping,Yan Yuting. Research on effect of grid-connected photovoltaic system on power grid[J].Electrical Engineering,2009(3): 41-44.  
[22] 胡庆有，含大规模风光互补电力的电力系统动态经济调度研究[D]．成都：西南交通大学，2013.  
[23] 张宋彬．应用于改善风电并网特性的储能集群控制系统研究与设计[D]．杭州：浙江大学，2014.  
[24] 刘霞，江全元．风光储混合系统的协调优化控制[J].电力系统自动化，2012，36(14)：95-100.Liu Xia,Jiang Quanyuan.An optimal coordinationcontrol of hybrid wind/photovoltale/energy storagesystem[J]. Automation of Electric Power Systems,2012,36(14):95-100.

# （上接第52页）

Tian Liting,Shi Shuanglong,Jia Zhuo,et al.AStatistical model for charging power demand ofelectric vehicles[J].Power System Technology,2010,34(11):126-130.[10] 崔静．含分布式电源和电动汽车的电网无功电压协调控制[D]．广州：广东工业大学，2015.

[11] 邢志斌．含电动汽车充电站和风电的配电网无功 优化[J]．电气应用，2015(34)：88-92. Xing Zhibin.Reactive power optimization of distribution network with electric vehicle charging station and wind power[J].Electrotechnical Application,2015(34): 88-92.