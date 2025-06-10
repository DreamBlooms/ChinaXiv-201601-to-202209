# 基于工业物联网的汽车工业敏捷规划轻量级仿真模型

卢阳光1，闵庆飞1，王奕斌²

(1．大连理工大学 管理与经济学部，辽宁 大连 116024;2.欧特克(中国)软件研发有限公司，上海 200011)

摘要：针对改进汽车工业的规划和流程分析方法进行了研究。为解决传统工业工程分析方法和仿真工具在规划任务中实施周期长，投入代价大，不能快速有效地支撑规划项目的问题，提出了一种基于 DEVS（discrete event systemspecification）理论的EVA（efficiencyvalidate analysis）仿真框架模型，并结合工业物联网技术，组合建立了一种敏捷的生产线规划分析方法。通过在发动机平衡轴生产线升级规划任务中实践检验，与传统的规划工作方法进行了比较，实践结果证明了新方法能显著提高建模和仿真工作的效率，并更有效地支持汽车工业中的规划工作。同时为实现实体物理世界和虚拟信息世界的快速有效互动，推动物联网技术和数字化技术与工业生产更深度地结合，带来了有价值的启发。

关键词：汽车工业；规划方法；仿真；工业物联网；数字孪生 中图分类号：TP391.9 doi: 10.3969/j.issn.1001-3695.2018.04.0268

# Light simulation model of agile planning for automotive industry based on industrial IoT

Lu Yangguang1, Min Qingfei1,Wang Yibin² (1.DUTFacultyof Management &Economics,Dalian Liaoning 16024,China;2.Autodesk (China) Software Research& Development Co. Ltd, Shanghai 200011,China)

Abstract:This paperdeveloped methods ofautomobile industry planing and process analysis.Traditional industryengineering and simulation method takes long implementation time and high investmentcost,and cannot eficiently supportthe planning task inreal business.This research proposed anew simulation framework calledEVA (Eficiency Validate Analysis)model, which is basedon DEVS(Discrete Event System Specification）theory,and integrated it with industry internetof things technology,as an agile production line planing and analyzing method.Thenew method was implemented in an upgrading planing processof abalance shaft production line.Theresult approved that the new method can enhance the modeling and simulationeficiencyandsupporttheplanningtaskmoreeffectivelyintheautomobileindustryThis paperalsoprovides valuable implication,onrealizinganeficient andefectiveinteraction between physical worldand virtual information world,and promoting a deeper integration of IoT technology and digital technology in manufacturing industry. Key words: automobile industry; planning method; simulation; industrial internet of things; digital twin

# 0 引言

仿真分析是工业规划常用的技术手段，但是往往因为需要投入人力多，对人员素质要求高，耗时较长等原因导致中小型企业无法承担其成本；或因为实施周期长，不能满足企业发展节奏而不被采纳。现代汽车工业也面临着快速变化的市场环境，和企业不断升级，转型，调整产能和生产方式的需要，因此需要一种投资小且高效的工业规划分析方法。

工业工程的分析方法包括方法研究和作业测定，其中方法研究包括程序分析，作业分析，和动作分析，作业测定包括秒表测时，工作抽样，预定动作时间标准法等技术手段。其分析技术通常遵循 5W1H(whywhatwhere whenwho how）的提问技术，ECRS(eliminate combine rearrange simplify）的四大原则,以及检查分析表的基本技术。在实施的过程中，要考虑经济因素，技术因素，人因因素，获取相关部门领导的认可和批准，组织参与人员培训，进行现场研讨，进行实地试验运行，因此投入人力多，实施周期长[1-3]。伴随现代计算机性能和软件技术的发展，仿真分析软件越来越多地应用于工厂规划任务中，以提升工业工程分析和规划工作的效率。诸如PlantSimulation等仿真软件，都有所见即所得的图形化工作环境，层次化的模型结构，面向对象的方法过程，各种形式的报告输出等。但这些仿真软件都较为复杂，同时在实现生产系统动态仿真和信息分析的过程中，对各方面影响因素都有较高的要求，例如需要机床、产品、工艺、工时等数据采集和录入的准确性；需要领导支持、充足的人力、丰富的企业知识库等[4-6]。

为改善制造型企业的生产效率和提升绩效，相关学者已经提出了很多仿真方法，比如数字仿真，蒙特卡罗仿真模拟，以及基于精益系统的仿真[7.8]。可用来执行生产系统的仿真软件比如Quest、Flexsim以及支持整体解决方案的Delmia 和西门子的Tecnomatix。但是传统的仿真方法在工业规划类项目上的实施便利性和灵活性上存在限制[9-10]。

Gurumurthy等人基于已有的价值流图析（VSM）存在的缺点，从精益生产的角度设计精益制造系统，结合仿真技术和价值流图析显著改进车间的生产绩效[1]。然而，该研究并未解决在实践中可能会聚焦局部精益的问题，且未阐明市场动态变化的情形，对于临时项目的规划并未提出合理的方式。McDonald等人[12]提出，在生产改进分析工作中使用仿真软件有助于解决价值流图静态视角的局限性，并将其运用在按订单控制产品制造工厂中的专用产品线中，可以提高解决方案的质量和效率。但是，该研究提到的方法依赖一些具体的概念，比如工艺改进和 5S等，需要实施人员有比较系统的理论素养。Franc 等人[13]为不同的仿真模型提出了评估指南，集中研究了动态仿真模型的实验，并且指出多数仿真方法存在很多阻碍实施的限制条件。Zhou 等人[14]基于案例推理(case-based reasoning，CBR)提供了一种敏捷的工艺规划方法，有助于再制造生产线的规划人员够快速地检索和利用过去问题的解决方案，但是该研究也提到了CBR的工艺规划方法不能有效应对快速变化的环境。Zhou 等人[15]开发了集成仿真与可视化的方法，从而为过程优化、设计、扩展和故障排除提供一个成本效益高的工具，然而这种工具更适用于虚拟设计和虚拟培训的应用情境，而对于流程与节拍问题并没有提供充分的解决方法。从上述研究评述可以发现，为应对制造业工厂的临时性改造项目或者中小型企业的规划需求需要研究快捷有效的仿真手段，从而以比较低的仿真代价来满足规划需求。

本文因此提出一种新的敏捷工业规划分析方法，基于轻量级的仿真平台和物联网技术，快速地对当前生产线的实际情况和新规划方案进行分析，并提供一些关键指标的输出结果，以供企业进行高效的规划，快速做出战略部署或投资决策。这种新的敏捷工业规划分析方法也符合数字孪生工厂的概念，它提供了工厂在雏形的阶段，即概念设计阶段的信息世界和物理实体的简洁映射模型。

# 1汽车工业规划的轻量仿真系统

# 1.1DEVS及其基本概念模型

离散事件系统规范（discrete event system specification）即DEVS，是美国学者Zeigler提出的一种离散事件系统形式化描述体系。DEVS 提供了模块化、层次化的系统建模和仿真执行框架。每个子系统在DEVS框架中都被视为一个内部结构独立、IO接口明确的模块，而且这些模块可以由多个组合成具有一定的连接关系的耦合模型[16,17]。

DEVS形式的操作语义具简洁，有助于与真实系统构建简单对应关系，可以方便建立具有时间概念的仿真模型。DEVS的实验运行框架作被形式化为模型对象，同时模型和运行框架能够组合形成耦合模型并且具有其它耦合模型相同的性质。这种层次清晰的处理方式有利于模块化和结构化地描述仿真对象。

DEVS理论的通用型和有效性，带来了这种理论框架在各种行业背景下的应用，包括离散制造行业、流程制造行业、救灾和应急保障、军事、网络通信、电力等，但结合物联网对汽车工业的规划研究较少。

# 1.2汽车工业的轻量级仿真框架设计

在概念设计阶段的汽车工业规划中，仿真应用应当聚焦在有限的核心指标上。例如生产线的初期规划阶段关注的关键指标是综合节拍，而物流区域的初期规划阶段更关注单个运输对象的周转时间。

诸如Flexsim，Tecnomatix，DELMIA等大型仿真商业软件套件能够提供包括工艺协同分析，人体工程学分析，可视化分析，物流运输路线分析，设备投入产出分析，容器和设备的周转率分析，最优方案求解等等丰富信息，但是在汽车工业规划初期概念设计阶段，人们往往只关注时间，节拍，瓶颈等工作效率类的核心指标。

因此本文提出一种新的仿真框架思路，将研究对象简化，只将涉及到时间和节拍的相关要素提炼出来，基于DEVS的基本单元模型和仿真器运行框架理念，设计一个极简模型的仿真结构，称之为EVA（efficiencyvalidate analysis,效率验证分析）模型，其基本框架图解如图1所示。

![](images/953cc1bfb00d240726f5632524fd592f27a06e34dc77c05f9252eab897951269.jpg)  
图1EVA模型:基于DEVS形式的仿真框架

EVA仿真结构框架内的基本元素定义：   
Input 是仿真的输入接口。   
Output是仿真的输出接口。   
${ \mathsf { C A S E } } =$ <NAME，{STD},{END},{AGENT },{BUFFER𝑖}, $\{ \mathrm { \ L I N K _ { i } }$ }，{VIBRA𝑖 }，{GROUP}，{MAINVIB}> $S T D = \angle N A M E$ ， $\{ \mathrm { R A T E } _ { \mathrm { j } } \}$ ，PERFORM，PATTERN，QUANT>   
END $\ c =$ <NAME，QUANT>   
AGENT $\mathbf { \bar { \rho } } = \mathbf { \rho }$ <NAME,PERFORM,{TAKT},{PROCESS,},{RATE},   
PATTERN，LOT>   
BUFFER $\mathbf { \tau } = \mathbf { \tau }$ <NAME，PERFORM, $\{ \mathrm { R A T E _ { j } }$ }，QUANT>   
LINK $\ c =$ <NAME，UPPER，DOWNER， $\{ \mathrm { T I M E } _ { \mathrm { j } } \}$ ，LOT，QUANT>   
PERFORM= $\angle \cdot \angle$ MTBF，MTTR, $\{ \mathrm { \ V I B R A _ { i } \} }$ >   
RATE $\ c =$ <PRIOT，TAKT，VIBRA>   
PATTERN=<{SEQUE𝑗}，{TAKTj }，{QUANTj }>   
PROCESS $\mathbf { \sigma } _ { = }$ < NAME，TYPE，SEQUE，PRIOT，LOT>

参考制造系统面向对象的仿真技术建模方法和设计原则[18\~20]，EVA 模型中使用的变量和参数名词注释如表1 所示。EVA模型将仿真要素集中在时间，节拍，效率，负荷，产能等工业规划初期的核心指标上，只进行相对简洁的模型构建，需要采集和输入的信息也较少。其仿真结果的输出也聚焦在整条生产线和其中每个对象的产能、负荷、节拍、时间等效率类的关键信息。

表1EVA 模型中的变量和参数  

<html><body><table><tr><td>名称</td><td>说明</td><td>类型</td><td>注释</td></tr><tr><td>CASE</td><td>一个仿真案例</td><td>obj</td><td>仿真案例名称</td></tr><tr><td>NAME</td><td>子组件名字集</td><td>char</td><td>iENAME</td></tr><tr><td>{STD}</td><td>原料输入集</td><td>obj</td><td>原料投入的速度，规律，数量等属性</td></tr><tr><td>{END}</td><td>产品输出集</td><td>obj</td><td>仿真模型的流程终点</td></tr><tr><td>{ AGENT,}</td><td>中间处理器集</td><td>obj</td><td>中间处理环节，可以代表岗位，机床，业务窗口等</td></tr><tr><td>{BUFFER}</td><td>缓冲器集</td><td>obj</td><td>缓冲区，堆垛区</td></tr><tr><td>{LINK}</td><td>传送线集</td><td>obj</td><td>包括两点之间的运输能力，速率，组态等信息</td></tr><tr><td>{VIBRA}</td><td>振幅值集</td><td>%</td><td>所有实际值非恒定的量化参数的振幅</td></tr><tr><td>{GROUP }</td><td>组合方式集</td><td>obj</td><td>{GROUPi}U{AGENT;}×U{BUFFERi}×U{LINKi}×U{VIBRAi}</td></tr><tr><td>{MAINVIB,}</td><td>全局变量集</td><td>obj</td><td>影响整体仿真过程和输出结果的全局参数设定组合</td></tr><tr><td>{RATE,}</td><td>物料投送或转移的方式集</td><td>obj</td><td>包括速率，优先顺序，振幅值等</td></tr><tr><td>{TAKT; }</td><td>个体的节拍时间组合集</td><td>time</td><td>预备时间，装载时间，卸载时间按，执行时间，振幅值等</td></tr><tr><td>QUANT</td><td>数量值</td><td>int</td><td>上限容量，总投料量，总产量，运载能力等</td></tr><tr><td>PERFORM</td><td>性能值</td><td>float</td><td>单个对象的性能预测，或者基于历史统计数据的性能评估</td></tr><tr><td>PATTERN</td><td>序列控制机制</td><td>obj</td><td>由顺序，时间间隔，数量等信息组成的序列表</td></tr><tr><td>MTBF</td><td>平均故障间隔</td><td>time</td><td>工序单次不停机检修可连续工作的时间长度</td></tr><tr><td>MTTR</td><td>平均故障恢复</td><td>time</td><td>工序单次停机检修或维护的时间长度</td></tr><tr><td>LOT</td><td>单次数量要求</td><td>int</td><td>一次性处理的任务要求包含的产品个体数量</td></tr><tr><td>UPPER</td><td>上游对象</td><td>obj</td><td>UPPERE{STD }U{AGENT}U{BUFFER }</td></tr><tr><td>DOWNER</td><td>下游对象</td><td>obj</td><td>DOWNERE{AGENT,}U{BUFFER,}U{END }</td></tr><tr><td>{ PROCESS, }</td><td>工艺组合集</td><td>obj</td><td>一个AGENT中可以包含单个或多个PROCESS</td></tr><tr><td>TYPE</td><td>工艺形式</td><td>bool</td><td>组合或分解等工艺形式</td></tr><tr><td>SEQUE</td><td>工艺关系</td><td>bool</td><td>并行或串行等工艺间关系</td></tr><tr><td>PRIOT</td><td>优先等级</td><td>int</td><td>有争用的情况下优先级高的任务先执行</td></tr></table></body></html>

# 2 基于EVA仿真和物联网技术的工业规划分析方法

# 2.1汽车生产线工业物联网和应用

目前汽车工业生产线多数为联网控制的数控系统，其机械加工生产线和装配生产线基本都已部署了工业网络，包含随产品制造过程流动的RFID芯片，以及控制生产机床的PLC和CNC控制单元等等，这些技术基础都为实时获取丰富的工业大数据用于分析创造了条件。

在数控机床的控制柜内，PLC和CNC模块一般都预留了用于外接数据采集的空闲以太网口，以及电源接口。只需要外接一个廉价的工业控制盒（boxPC)，即可进行数据采集，在生产线安全级别要求不高的情况下，甚至可以直接将工业网口和服务器的网络进行连接。以CNC数控机床为例，汽车生产线工业数据采集方式的逻辑示意如图2所示。

![](images/3a0b5d0150137d4987aff58d092f5de14f8459a7b85a800c3136afc3de54a1e7.jpg)  
图2面向CNC数控机床的数据采集连接方式图

在汽车工业生产线通过物联网获取的机床工控数据，是做各种数据分析快捷有效的来源。从生产线获取工业数据，以及将相关数据对外数据传递的网络拓扑如图3所示。

通过工业物联网技术采集数据有如下好处：a)数据实时在线传输，提高了数据获取的及时性;b)避免了人为干预导致的错漏删改，保障了数据的准确性;c)借助边缘计算技术，可以在数据获取端就对大数据进行初步的清洗，筛选和整理，提升了数据的有效性。

![](images/7a9531934fddbbe0e52421a093b3c00a2d6f4e522fb96a2f029eb21c5ccdf4f7.jpg)  
图3汽车生产线数据采集和传递的网络拓扑

# 2.2基于工业物联网的仿真数据计算

在机床上直接采集的工业物联网数据，已包括设备的运行状态，能源消耗，加工过程指标，在线指令分析等一系列时序性信息，这些信息既可以直接用于生产线运行过程的实时监控，也可以进一步结合办公网的应用系统，进一步进行生产线指标分析，以及持续的管控和改进过程，如图4所示。

On/Off 1 1 1  
设备数据 三 --=- 生产现场目视管理 =-=-设备状态统计分析统计IPower 1consumption of: == --- === 持续改进管理  
能耗数据 Water 1 能源负载监控 1 1Cold watair 1 1 能源介质消耗统计 11. 1 ！ 1  
加工数据 OP20 1 === ！ ---产量数据共享！ fail) 1 1 追踪和追管理！ 二 - 质量管理！DimensionsRoundness 1 1  
测量数据 二 二= 生产测量目视管理 ---加工测量数据分析和管理1 1 1生产数据 监控 1 分析 管理/控制·

生产线数据通过工业控制盒传递到办公网络中，可以由办公电脑直接收集和计算，也可以通过服务器统一处理之后，再直接将计算过的可以直接用于仿真的数据，通过应用程序接口共享给办公电脑。

EVA仿真模型只关心涉及到时间和效率和核心指标，例如平均节拍时间，生产周期内平均性能，平均故障间隔时间，平均故障恢复时间，以及数据的上下波动区间振幅等数值等。通过PLC或CNC获取的工业大数据，推算主要的仿真数据的逻辑公式如公式（1） ${ \sim } ( 5 )$ 。

$$
T A K T _ { P R o C E S S _ { - } i } = \frac { \displaystyle { \sum _ { j } } ^ { k } ( o u t _ { - } t i m e _ { s } - i n _ { - } t i m e _ { s } ) } { k - j + 1 } ,
$$

$$
(  { [ j , k ] [ M T B F _ { - } } s t a r t _ { m } ,  { M T B F _ { - } } e n d _ { m } ] )
$$

$$
\mathit { P E R F O R M } _ { \mathit { A G E N T } _ { - } i } = \{ \frac { T } { \displaystyle \sum _ { \mathit { A G E N T } _ { i } } T A K T _ { \mathit { P R O C E S S } _ { - } l } } , \mathit { \ P f S E Q U E } _ { i } = s e r i a l \
$$

$$
( \mathbf { T } \in \{ 2 4 h o u r s , \mathcal { K } 0 m i n u t e s , \mathcal { K } 0 s e c o n d s \} ~ )
$$

$$
M T B F _ { _ { A G E N T _ { - } } i } = \frac { \sum _ { p } ^ { q } ( s t a r t \_ t i m e _ { s } - f a i l \_ t i m e _ { s } ) } { q - p + 1 } \ : ,
$$

$$
( \mathrm { s } \in \{ P L C \ 2 o g , 2 a b n o r m a l d u r a t i o n \} )
$$

$$
M T T R _ { _ { A G E N T \_ } i } = \frac { \sum _ { p } ^ { q } ( f a i l \_ t i m e _ { s } - s t a r t \_ t i m e _ { s } ) } { q - p + 1 } ,
$$

$$
( \mathrm { s } \in \{ P L C \ 2 o g , 2 a b n o r m a l d u r a t i o n \} )
$$

$$
V I B R A _ { x } = \frac { \sqrt { \displaystyle { \sum _ { j } ^ { k } ( V a l u e _ { s } - A V E R A G E _ { - } x ) ^ { 2 } } } } { k - j - 1 } \times 1 0 0 \%
$$

$$
( \mathbf { x } \in \{ T A K T ,  T E R F O R M , \mathbf { \mathcal { M T B F } } , \mathbf { \mathcal { M T T R } } \} )
$$

# 2.3物联网结合轻量级仿真平台的组合应用

结合物联网技术和极简的仿真EVA模型，设计如下工业规划分析方法框架：

a)由规划人员在EVA仿真平台上用较短时间完成一个简洁模型的搭建;

6)对于物联网可直接获取的仿真必要数据，例如设备运转和人流物流数据，包括时间，节拍，故障，振幅等数据信息，经过程序化自动处理之后，直接用于EVA仿真模型的数据输入;

c)通过EVA仿真模型的平台输出仿真后得到的关键数据信息，反馈用于现实中项目规划决策或供优化讨论。

由此针对汽车工业规划构建一种新型的敏捷分析方法，其过程逻辑示意图如图5所示。

![](images/08e3d5f91493e2b153685e7a5ccd6e1d505213c16ea78cc9541d765936c7f6b0.jpg)  
图4汽车生产线物联网获取的数据和应用过程  
图5基于EVA仿真模型和汽车工业物联网的敏捷规划方法示意图

# 3 实践应用案例

这次实验得到了欧特克（中国）软件研发有限公司的技术支持，提供了一个自研的仿真软件，这个软件的功能和界面基于EVA仿真结构框架的概念设计开发。

实验用到的工具包括纸和笔，网线，工业控制盒，和一台办公电脑，配置为Inteli3处理器3GHz，4GB内存，500GB硬盘。

# 3.1项目背景

某汽车发动机厂位于中国北方，是欧洲某大型汽车集团与中方的合资企业，随着中国汽车市场的蓬勃发展，该公司的发动机的产销量持续快速增长，因此对现有生产线不断提出提升产能和扩大规模的要求。

过去该公司的规划工作时间周期长，这样导致公司的新生产线从提出需求到实际投产的时间周期过长，影响了公司产能对市场变化的反应速度。公司的工业工程部门曾申请引入德国总部研发的工业工程分析系统AP，以提升工业规划效率，但因需要耗资几百万，实施周期长达一年半，实施后还需要增加2\~3个工程师岗位，此提议被公司高层否决。

在 2017年的平衡轴生产线扩产能的改造项目中，公司希望能有针对现有生产线的实际运行情况进行快速评估，并在短期内设计出把生产线提升到目标产能方案的规划方法。

# 3.2方案设计及实现过程

根据工厂的项目背景设计如下方案：

仿真的方式是以被加工的工件为考察对象，模拟从投料到下线的整体工艺节拍过程，评价在指定的生产运行周期（连续运行20个小时或连续生产1800个产品）内，生产线规划涉及的关键指标，包括整体生产能力，个体的节拍和负荷情况，运输线的繁忙程度等。

实验者为一个计算机专业背景的工程师，在此项目之前他未接触过仿真相关的工作或工业工程分析有关的培训。在经过几个小时的EVA软件平台功能培训后，他开始独立进行现场调研和构建模型。现场调研一天后，实验者首先根据当前已有的旧生产线的实际平面布局和工艺路线图，快速手绘了一个现场的简单模型如图6所示。

![](images/b6b0e76f02ca6631399b0cfede4293924b7e937f85d327b30ac63b6a0d902d21.jpg)  
图6现场调研后手绘的生产流程模型图

然后根据这个仿真实例的业务情况，实验者参考EVA模型中使用的变量和参数表，以及现有的工艺文档，构建了应对EVA模型的逻辑如表2所示。

表2平衡轴生产线的EVA模型对象  

<html><body><table><tr><td>名称</td><td>仿真对象说明</td></tr><tr><td>CASE</td><td>：某发动机厂平衡轴生产线仿真</td></tr></table></body></html>

<html><body><table><tr><td>{STDi}：平衡轴毛胚投料口</td></tr><tr><td>{ENDi}：平衡轴成品下线</td></tr><tr><td>{AGENT}：加工机床</td></tr><tr><td>{BUFFER}：料框和在线缓存区</td></tr><tr><td>{LINKi}：料道运输、机器臂运输、工人搬运等物料移动形式</td></tr><tr><td>{GROUPi}：机床、缓冲区、机械臂的组合方式，根据现场观察</td></tr><tr><td>{TAKTj}：节拍时间集，根据机床loT数据计算</td></tr><tr><td>PERFORM：性能，根据机床IoT历史数据计算</td></tr><tr><td>PATTERN：输入输出序列，根据工艺文件</td></tr><tr><td>MTBF ：平均故障间隔，根据机床IoT数据计算</td></tr><tr><td>MTTR ：平均故障恢复，根据机床IoT数据计算</td></tr><tr><td>{VIBRA}：数值的分布区间或振幅集，根据机床IoT数据计算</td></tr><tr><td></td></tr><tr><td>LOT ：单次加工或运输最小数量，根据工艺文件</td></tr><tr><td>{PROCESSi}：加工工艺集，根据现场观察</td></tr><tr><td>TYPE ：拆解、组装、或机加等工艺形式，根据工艺文件</td></tr><tr><td>：工艺之间的串行、并行、或混合等关系，根据工艺 SEQUE</td></tr><tr><td>文件</td></tr><tr><td>PRIOT ：工艺之间或排料之间的优先关系，根据工艺文件</td></tr></table></body></html>

在手绘模型和EVA模型与仿真实物对象参照表的基础上，实验者在 EVA 仿真软件平台上构建了一个简洁的平衡轴生产线模型，包括生产设备，运输线，缓冲区，毛胚供料，和成品下线，其示意图如图7所示。

![](images/f4f2758c1a4a7ec6acae9374d9fbf2c929f8d161010e7ec9bf1c262e614881a9.jpg)  
图7基于EVA的平衡轴生产线模型示意图

模型中的仿真数据有以下来源：现场的实际观察和计算，生产现场管理工作报表的数据统计，工艺文档中的数据。

诸如每台机床的平均节拍，平均故障间隔，平均故障恢复，以及在概率区间内的上下限分布等数据，传统的工业工程规划方法计量和分析的时间周期长，投入人力代价较高，而本实验是通过生产线工业互联网获取。

# 3.3基于工业物联网的仿真数据采集

实验者在既有的生产线控制柜上安装了工业控制盒，并连接到了预留的CNC外接网口上，通过生产线的工业网络和标准的西门子工业数据传递协议，收集到工业控制盒。如图8所示。

![](images/4d6c27c93f66bc240bb28fefd55e55d2cba510bd2098b9758e1d6dc67778811a.jpg)  
图8生产线的工业数据采集现场图  
图10基于EVA仿真输出结果的统计信息图

基于IoT数据采集可以和其他工作并行同步开展。因为涉及到平均值和概率区间内上下限的数据计算，实验者采集了一个星期的工业数据。

工业控制盒与办公电脑之间通过防火墙和办公网络连接，通过生产线获取到的工业数据，这些原始数据下载到办公电脑之后，再通过统计程序计算得到相应的仿真输入数据。

# 3.4仿真输出数据

EVA模型仿真输出的数据原型是一个时间序列表，以每个状态变化为一条带时间戳的单独记录的方式，按时间先后顺序记录了仿真模型中每一个原子要素发生的所有变化。时间序列表里面每一条记录包含了当前作业的原子模型对象，其触发的作业类型，持续时间，操作产品的个数，涉及的上下游和运输通道，时间戳，以及一些累积数量等信息。本实验中以1800 个终产量目标进行模拟，输出了582989条记录，部分示例如表3所示。为了便于展示，输出数据中非重要信息，如对象ID号和事件ID号等，不在表格中展示。

根据EVA模型仿真输出的时间序列表，可以通过软件生成时间轴分区图，如图9所示。时间轴分区图的横坐标是从仿真开始到结束的完整时间段，而每个时间点对应的不同颜色代表该单元模块在当前时刻所处的状态，其中绿，蓝，灰，黄，红五种颜色分别代表生产，等料，准备，堵料，维修等五种不同的情形，以直观地观察该工序在整个仿真时间周期上的状态分布。（因印刷版为黑白色，彩图请读者参考电子版。)

# 3.5根据仿真结果的规划问题分析

把相邻的上下游工序的时间轴分区图放在一起的时候，就可以对其进行横向的比较，图9展示了将不同工序的时间轴分区图排列在一起并行展示的结果。

图9中显示AF220表面硬化工序在全时间段一直处于满负荷运转的状态，而其上游AF200 铣刀工序出现了大量的堵料的情况，下游AF240校直出现了大量等料的情况，这种现象往往意味着AF220是一个显著的瓶颈工位，需要考虑对其产能进行扩充。图中还可以发现，上下游工位AF30和AF40中间的缓冲模型Buffer30-40存在规律性的满负荷和空载的情况，这说明缓冲模型的设计容量不足，需要在重新设计的规划方案中提升其负荷能力。

根据EVA模型仿真输出的时间序列表，可以通过软件统计得到各个原子模型的摘要信息表，如表4所示。摘要信息表用量化的数据，准确地展现了发动机再制造工厂各个组成要素，包括：生产工位，运输线，缓冲等在整个模拟的生产周期中的综合表现，例如当前环节接收到的工件数量，当前环节完成并移交到下一个环节的工件数量，平均每个工件在当前环节的周转时间，当前工位的统计生产时间，预备时间，等料时间，堵料时间，维修时间等。从表4中的统计数据可以更准确地算出，AF220工位两台表面硬化设备分布在生产和维修的平均时间比例为 $91 . 9 6 \%$ 和 $6 . 8 7 \%$ ，而其上游AF200六台铣刀车床分布在生产和堵料的平均时间比例为 $42 . 6 \%$ 和 $51 . 2 4 \%$ ，同时其下游AF240两台校直机器分布在生产和等料的平均时间比例为$2 7 . 0 3 \%$ 和 $6 8 . 0 1 \%$ ，以上所有和AF220上下游相关的堵料和等料时间总和占整条生产线的 $3 8 . 2 4 \%$ ，这从量化的角度更准确地说明AF220是生产线产能提升的首要改造点。

将仿真结果输出的时间序列数据经过求和统计后通过图形的方式量化地展示，则可以更直观地观察上述有关时间分配比例的信息，如图10所示。

10098   
%70   
1 60   
50   
出   
20 -   
10 - 0 AF200-1 AF200-2 AF200-3 AF200-4 AF200-5 AF200-6 Wassermaschine1 AF220-2 AF220-1 Wassermaschine2 producing I setup Idle lockedooun   
100   
80 -   
%70   
60   
出   
20 - 10 - 7   
0 - AF240-1 AF240-2 AF10-4 AF10-5 AF10-6 AF10-1 AF10-2 AF10-3 Conveyor 2a Conveyor Robot2b PreducingI setupIdleslockedooun   
100   
80 -   
%70   
1 60   
6 50   
出30   
20 -   
10 - 12 0 - Conveyor 1a AF20-2 AF20-1 AF30-2 AF30-1 AF40-1 AF50-1

图10 中每一个工序，都根据时间序列表的数据，统计了其在生产、准备、等料、堵料、维修五种状态下的时间占比，分别以绿、灰、蓝、黄、红五种颜色表示，并展示为百分比柱状图的形式。（因印刷版为黑白色，彩图请读者参考电子版。)

# 3.6实验发现和方法比较

实验者在第二周提供了现场仿真报告，在第四周内和德国规划部门的人员进行了讨论，设计了5种不同的生产线扩产规划方案，并对这五种不同的方案分别输出了规划方案仿真报告。

仿真的输出结果包括整体的性能指标（全线综合产能)，也包括各个工位、缓存、运输线在模拟周期内的性能指标，以及五种不同工况的时间分布比例（生产、预备、检修、等料、堵料）以及全时间轴的波段展示。

通过其输出报表发现的问题和主要结论包括：

a)当前生产线的主要瓶颈在AF220表面硬化工序， $3 8 . 2 4 \%$ 的堵料和等料导致的闲置情况都发生在此工序的上下游环节，所以未来扩产的投资重点应当优先考虑此工序。

b)AF30工序和AF40测量工序之间的缓冲区经常周期性地出现满载和空载的情况，说明负荷能力与实际业务需求不匹配，进一步实验证明，在AF220工位的产能问题解决后，此处会成为一个新的瓶颈，并降低生产线整体效率 $8 . 7 \%$ 。经过多次仿真比对证明该缓冲区容量扩大 $50 \%$ 能达到最佳边际收益点。

c)实验者配合规划员针对5种不同的生产线扩建规划方案进行了仿真，并输出了量化的数据，以供规划部门评估。在达到产能提升目标的前提下，他们通过仿真结论的辅助，分别寻找了投资最低，设备占用空间最小，和工人编制最少的单项指标最优解。

德国总部和中国工厂的规划人员在此实验项目后进行了评估，对比新的分析方法和传统的工业规划分析方法。结论是和传统规划分析方法相比，这种结合物联网数据和轻量级仿真的规划分析方法极大地节约了参与分析过程的人力，而且对项目执行者的工业工程专业背景要求降低了，因此前期规划分析的工作成本有了显著的减少。而新方法的工作输出成果和传统的方法比较，同样都可以提供准确的数据用于管理层做出投资决策评估，有效地支持生产线规划的工作。

# 4 结束语

传统的工业工程分析方法和仿真工具在工业规划任务中实施周期长，不能快速有效地得到项目评估结果。基于DEVS 理论构建的量级仿真平台和物联网技术，本文提出了一种EVA 仿真框架模型，设计了一种敏捷工业规划分析方法，并且在平衡轴生产线的一个升级改造项目中进行了检验，证明了其适用性。本文的研究结果对于学界和工业界有重要意义。首先，伴随着信息物理系统和数字孪生概念的兴起，实体物理世界和虚拟信息世界的转换越来越受学者和企业的关注[21-22]，然而鲜有能实现虚拟模型和真实环境之间快速有效互动的方法。本文在工厂生命周期的初始阶段，即概念设计阶段，提供了一种可落地的实践方法，推动了物联网技术和数字化技术与工业生产更深度地结合。其次，相对于传统的仿真建模方法，本文提出的方法更有效和简单，因前序准备工作和仿真建模过程较易实现，因此大大降低了技术人员的实施门槛。因此在其他类似的工业环境中，例如对中小型企业或临时性的小型项目如何快捷有效地应用仿真技术和工业物联网，也带来了有价值的启发。

# 参考文献：

[1]Dekkers R,Chang CM,Kreutzfeldt J.The interface between"product design and engineering"and manufacturing:a review of the literature and empirical evidence [J].International Journal of Production Economics,2013,144(1): 316-333.

[2]李显君，高歌，孟东晖，等．工艺创新机制研究：来自中国汽车企业的 实证[J].科研管理,2016,37(12):37-45.(Li Xianjun,Gao Ge,Meng Donghui,et al.An empirical research on process innovation mechanism: The evidence from China's automobile industry [J].Science Research Management,2016,37(12): 37-45.)

[3]张力，张晓玲，蒋建军．基于ECRS和启发式算法的涡轮增压器装配线 平衡研究[J].机械,2016,43(4):1-5.(ZhangLi,Zhang Xiaoling,Jiang Jianjun.ECRS and heuristic algorithm-based balance study in turbochargers assembly line [J].Machinery,2016,43 (4):1-5.)   
[4]Sanchez R，Mahoney JT. Modularity，flexibility，and knowledge management in product and organization design[J]. Strategic Management Journal,2015,17 (S2): 63-76.   
[5]Thomson N.Simulation in manufacturing[J]. Journal of the Operational ResearchSociety,2002,75(3):110.   
[6]Kasperczyk M,Bötinger F,Michen M,et al.Applied knowledge management for complex and dynamic factory planning[J]. International Journal ofModernPhysicsA,2012,16 (12):2165-2173   
[7]张玺，刘明周，张铭鑫，等．基于改进模糊Petri网的制造车间重调度策 略优化研究[J].管理工程学报,2017,31(2):216-221.(Zhang Xi,Liu Mingzhou, Zhang Mingxin,et al.Research onrescheduling strategy optimization in manufacturing shop based on improved fuzzy petri net [J]. Journal of Industrial Engineering and Engineering Management, 2O17,31 (2): 216-221.)   
[8] Negahban A,Smith JS. Simulation for manufacturing system design and operation: literature review and analysis [J].Journal of Manufacturing Systems,2014,33(2):241-261.   
[9]尤后兴，林杰．基于公理设计理论的仿真软件评价方法研究[J].管理 科学,2012,25 (2): 78-86.(You Houxing,Lin Jie.Research on simulation software evaluation method based on axiomatic design theory[J]. Journal of Management Science,2012,25 (2): 78-86.)   
[10] Davis E, Marcus G. The scope and limits of simulation in automated reasoning [J].Artificial Inteligence,2016,233 (C): 60-72.   
[11] Gurumurthy A, Kodali R. Design of lean manufacturing systems using value stream mapping with simulation: a case study[J]. Journal of Manufacturing Technology Management,2011,22 (4): 444-473.   
[12]McDonaldT,VanAkenEM,RentesAF.Utilising simulation to enhance value stream mapping: a manufacturing case application [J]. International Joumal ofLogistics,2002,5 (2):13232.   
[13] De Franca BB N,Travassos G H.Experimentation with dynamic simulation models in software engineering:planning and reporting guidelines [J]. Empirical Software Engineering,2016,21(3):1302-1345.   
[14] Zhou Fan,Jiang Zhigang, Zhang Hua,et al.Acase-based reasoning method for remanufacturing process planning [J]. Discrete Dynamics in Nature and Society. 2014 (5): Article ID 168631.   
[15] Zhou Chenn, Wang Jichao, Tang Guangwu, et al. Integration of advanced simulation and visualization for manufacturing process optimization [J].

Journalof the Minerals,2016,68(5):1363-1369.

[16] Zeigler BP,Moon Y,Kim D,et al. The DEVS environment for highperformance modeling and simulation [J].IEEE Computational Science and Engineering,1997,4(3): 61-71.

[17]Foures D,FranceschiniR,BisgambigliaPA,et al.multiPDEVS:a parallel multicomponent system specification formalism [J].Complexity, 2018, 2018 (4): Article ID 3751917.

[18]侯扬，范秀敏，严隽琪，等．基于仿真的制造系统对象建模及其应用 [J].计算机集成制造系统,2001,7(5):42-46.(Hou Yang,Fan Xiumin,Yan Juanqi,et al. Simulation-based manufacturing system object modeling [J]. Computer Integrated Manufacturing Systems,2001,7(5): 42-46.)

[19]Ieee BE.IEEE standard for modeling and simulation(M&S) high level architecture (HLA): framework and rules [J].IEEE,201O:1-378.

[20]冯辉宁．用分层事件关系图实现系统仿真与分析[J].计算机应用研究，2010,27(7): 2572-2574.(Feng Huining. System simulation and analysisusing hierarchical event relationship graphs [J].Application Research ofComputers,2010,27(7):2572-2574.)

[21] Liu Qiang,Zhang Hao,Leng Jiewu,et al.Digital twin-driven rapid individualised designing of automated flow-shop manufacturing system [J].

International Journal of Production Research,2018,Online (101006).

[22] Tao Fei, Cheng Jiangfeng,Qi Qinglin,et al.Digital twin-driven product design,manufacturing and service with big data [J]. International Journal of Advanced Manufacturing Technology,2017,94(9-12): 3563-3576.

[23]Lin Yan,Chen Jian,Chen Yan.Backbone of technology evolution in the modern era automobile industry:Ananalysis by the patents citation network [J].Journal of Systems Science and Systems Engineering,2011,20(4):416- 442.

[24]牛占文，荆树伟，杨福东．基于精益管理的制造型企业管理创新驱动因 素分析—四家企业的案例研究[J].科学学与科学技术管理,2015(7): 116-126.(Niu Zhanwen,Jing Shuwei, Yang Fudong.An analysis of driving factors of the management innovation of manufacturing enterprises based on lean management: case studies of four enterprises [J]. Science of Science and Management of S.&.T.,2015(7):116-126.)

[25]陈海涛，张健，齐林，等．基于时间Petri网的循环物质流动态投入建模 与仿真优化[J]．系统工程理论与实践,2016,36(8):1993-2002.(Chen Haitao,Zhang Jian,Qi Lin,et al.Modeling and simulate optimization for dynamic input of circular material flow based on timed-Petri net[J].Systems Engineering: Theory & Practice,2016,36(8):1993-2002.)

表3EVA仿真输出的发动机平衡轴生产线模型时间序列表示例表  
/s   

<html><body><table><tr><td>ID</td><td>Object Type</td><td>Object Name</td><td>Action Type</td><td>Action Subtype</td><td>Elapsed Time</td><td>Quantity</td><td>Input Items</td><td>Output Items</td><td>Operation Object</td><td>Connection</td><td>Time stamp</td></tr><tr><td>393083</td><td>Processor</td><td>AF10-4</td><td>Processing</td><td>Stop</td><td>88.75</td><td>1</td><td>216</td><td>215</td><td>Schleifen</td><td></td><td>48994.09</td></tr><tr><td>393097</td><td>Processor</td><td>Conveyor 2a</td><td>Blocked</td><td>blocked Stop</td><td>70.72</td><td>1</td><td>635</td><td>634</td><td>Pick from buffer</td><td></td><td>48994.09</td></tr><tr><td>393220</td><td>Buffer</td><td>240-10 Auslass</td><td>Blocked</td><td>blocked Stop</td><td>8.93</td><td>2</td><td>639</td><td>637</td><td></td><td></td><td>49003.02</td></tr><tr><td>393253</td><td>Buffer</td><td>10-20 Auslass</td><td>Idle</td><td>available Stop</td><td>5.15</td><td>0</td><td>630</td><td>630</td><td></td><td></td><td>49004.68</td></tr><tr><td>393273</td><td>Processor</td><td>Conveyor 2a</td><td>Processing</td><td>Stop</td><td>9.00</td><td>1</td><td>637</td><td>636</td><td>Pick from buffer</td><td></td><td>49012.02</td></tr><tr><td>393355</td><td>Processor</td><td>Conveyor la</td><td>Idle</td><td>available Stop</td><td>501.60</td><td>1</td><td>639</td><td>639</td><td>Pick from buffer</td><td></td><td>49043.67</td></tr><tr><td>393377</td><td>Buffer</td><td>240-10 Auslass</td><td>Blocked</td><td>blocked Stop</td><td>42.78</td><td>1</td><td>639</td><td>638</td><td></td><td></td><td>49045.80</td></tr><tr><td>393378</td><td>Buffer</td><td>240-10 Auslass</td><td>Input Item</td><td>Received</td><td>0.00</td><td>1</td><td>640</td><td>638</td><td></td><td>Connection 10</td><td>49045.80</td></tr><tr><td>393379</td><td>Buffer</td><td>240-10 Auslass</td><td>Blocked</td><td>blocked Start</td><td>0.00</td><td>10</td><td>648</td><td>638</td><td></td><td></td><td>49045.80</td></tr><tr><td>393380</td><td>Processor</td><td>AF200-3</td><td>Processing</td><td>Stop</td><td>80.23</td><td>1</td><td>276</td><td>275</td><td>Fraesen Dehren</td><td></td><td>49048.52</td></tr><tr><td>393404</td><td>Connector</td><td>Connection 1</td><td>Idle</td><td>available Start</td><td>0.00</td><td>0</td><td>0</td><td>630</td><td></td><td>Entmagnet</td><td>49050.09</td></tr><tr><td>393405</td><td>Processor</td><td>Entmagnet</td><td>Idle</td><td>available Stop</td><td>1076.78</td><td>1</td><td>621</td><td>621</td><td>Entmagnetisierung</td><td></td><td>49050.09</td></tr><tr><td>393406</td><td>Processor</td><td>Entmagnet</td><td>Input Item</td><td>Received</td><td>0.00</td><td>1</td><td>622</td><td>621</td><td>Entmagnetisierung</td><td>Connection 1</td><td>49050.09</td></tr><tr><td>393479</td><td>Processor</td><td>Entmagnet</td><td>Processing</td><td>Start</td><td>0.00</td><td>1</td><td>626</td><td>625</td><td>Entmagnetisierung</td><td></td><td>49058.89</td></tr><tr><td>393480</td><td>Processor</td><td>AF20-2</td><td>Processing</td><td>Stop</td><td>28.56</td><td>1</td><td>631</td><td>630</td><td>Finischen</td><td></td><td>49060.65</td></tr><tr><td>393640</td><td>Processor</td><td>Conveyor 2a</td><td>Processing</td><td>Start</td><td>0.00</td><td>1</td><td>638</td><td>637</td><td>Pick from buffer</td><td></td><td>49079.31</td></tr><tr><td>393641</td><td>Buffer</td><td>240-10 Auslass</td><td>Blocked</td><td>blocked Stop</td><td>33.51</td><td>10</td><td>648</td><td>638</td><td></td><td></td><td>49079.31</td></tr><tr><td>394483</td><td>Processor</td><td>Conveyor Robot2b</td><td>Processing</td><td>Start</td><td>0.00</td><td>1</td><td>634</td><td>633</td><td>Pick from AF10</td><td></td><td>49167.98</td></tr><tr><td>394484</td><td>Processor</td><td>Wassermaschinel</td><td>Processing</td><td>Stop</td><td>6.96</td><td>1</td><td>1459</td><td>1458</td><td>wasschen</td><td></td><td>49169.73</td></tr><tr><td>394485</td><td>Processor</td><td>Wassermaschinel</td><td>Blocked</td><td>blocked Start</td><td>0.00</td><td>1</td><td>1459</td><td>1458</td><td>wasschen</td><td></td><td>49169.73</td></tr><tr><td>394486</td><td>Processor</td><td>Conveyor Robot2b</td><td>Processing</td><td>Stop</td><td>2.49</td><td>1</td><td>634</td><td>633</td><td>Pick from AF10</td><td></td><td>49170.46</td></tr><tr><td>394497</td><td>Buffer</td><td>10-20 Auslass</td><td>Idle</td><td>available Stop</td><td>78.98</td><td>0</td><td>633</td><td>633</td><td></td><td></td><td>49170.46</td></tr><tr><td>394498</td><td>Buffer</td><td>10-20 Auslass</td><td>Input Item</td><td>Received</td><td>0.00</td><td></td><td>634</td><td>633</td><td></td><td>Connection 64</td><td>49170.46</td></tr><tr><td>394519</td><td>Processor</td><td>AF20-2</td><td>Idle</td><td>available Stop</td><td>28.44</td><td>1</td><td>633</td><td>633</td><td>Finischen</td><td></td><td>49174.46</td></tr></table></body></html>

![](images/da6d7a952aa1f335bba8f724104fe593f7b379e44c3c33cf10965ffde3cbe22f.jpg)  
图9通过EVA仿真输出时间序列表模拟的平衡轴生产线时间轴分区对比图

表4基于EVA仿真输出时间序列表统计的摘要信息表(时间值单位为秒)  

<html><body><table><tr><td>ID</td><td>Name</td><td>Type</td><td>Received</td><td>Delivered</td><td>Average Output Time</td><td>Time Producing</td><td>Time Idle</td><td>Time Blocked</td><td>Time Setup</td><td>Time Down</td><td>Count MTBF</td></tr><tr><td>1</td><td>AF200-1</td><td>Processor</td><td>478</td><td>477</td><td>152.23</td><td>38361.27</td><td>2.01</td><td>29794.66</td><td>0</td><td>4454.05</td><td>5</td></tr><tr><td>2</td><td>AF200-2</td><td>Processor</td><td>388</td><td>387</td><td>187.63</td><td>31289</td><td>2.09</td><td>36798.81</td><td>0</td><td>4522.09</td><td>5</td></tr><tr><td>3</td><td>AF200-3</td><td>Processor</td><td>415</td><td>414</td><td>175.39</td><td>33282.52</td><td>2.03</td><td>34794.45</td><td>0</td><td>4532.99</td><td>5</td></tr><tr><td>4</td><td>AF200-4</td><td>Processor</td><td>298</td><td>297</td><td>244.48</td><td>23253.61</td><td>2.01</td><td>44849.64</td><td>0</td><td>4506.73</td><td>5</td></tr><tr><td>5</td><td>AF200-5</td><td>Processor</td><td>394</td><td>393</td><td>184.76</td><td>30078.89</td><td>2.27</td><td>38069.79</td><td>0</td><td>4461.04</td><td>5</td></tr><tr><td>6</td><td>AF200-6</td><td>Processor</td><td>379</td><td>378</td><td>192.1</td><td>29153.64</td><td>2.52</td><td>38933.9</td><td>0</td><td>4521.93</td><td>5</td></tr><tr><td>7</td><td>Wassermaschine1</td><td>Processor</td><td>2098</td><td>2097</td><td>34.63</td><td>14686.38</td><td>1901.63</td><td>56023.97</td><td>0</td><td>0</td><td>0</td></tr><tr><td>8</td><td>AF220-2</td><td>Processor</td><td>983</td><td>982</td><td>73.94</td><td>67061.91</td><td>851.76</td><td>0</td><td>0</td><td>4698.32</td><td>9</td></tr><tr><td>9</td><td>AF220-1</td><td>Processor</td><td>976</td><td>975</td><td>74.47</td><td>66490.47</td><td>844.77</td><td>0</td><td>0</td><td>5276.76</td><td>9</td></tr><tr><td>10</td><td>Wassermaschine2</td><td>Processor</td><td>1953</td><td>1953</td><td>37.18</td><td>13672.05</td><td>58939.94</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>11</td><td>AF240-1</td><td>Processor</td><td>970</td><td>969</td><td>74.93</td><td>19566.67</td><td>49442.63</td><td>0</td><td>0</td><td>3602.68</td><td>4</td></tr><tr><td>12</td><td>AF240-2</td><td>Processor</td><td>969</td><td>968</td><td>75.01</td><td>19680.55</td><td>49331.44</td><td>0</td><td>0</td><td>3600</td><td>4</td></tr><tr><td>13</td><td>AF10-4</td><td>Processor</td><td>329</td><td>329</td><td>220.71</td><td>28623.04</td><td>38016.54</td><td>0</td><td>0</td><td>5972.4</td><td>4</td></tr><tr><td>14</td><td>AF10-5</td><td>Processor</td><td>312</td><td>312</td><td>232.73</td><td>27000.42</td><td>39410.1</td><td>0</td><td>0</td><td>6201.47</td><td>4</td></tr><tr><td>15</td><td>AF10-6</td><td>Processor</td><td>322</td><td>322</td><td>225.5</td><td>28150.14</td><td>38494.37</td><td>0</td><td>0</td><td>5967.48</td><td>4</td></tr><tr><td>16</td><td>AF10-1</td><td>Processor</td><td>303</td><td>303</td><td>239.64</td><td>26383.51</td><td>39766.85</td><td>0</td><td>0</td><td>6461.63</td><td>4</td></tr><tr><td>17</td><td>AF10-2</td><td>Processor</td><td>310</td><td>310</td><td>234.23</td><td>26672.98</td><td>39704.13</td><td>0</td><td>0</td><td>6234.88</td><td>4</td></tr><tr><td>18</td><td>AF10-3</td><td>Processor</td><td>350</td><td>350</td><td>207.46</td><td>30370.04</td><td>36399.67</td><td>0</td><td>0</td><td>5842.28</td><td>4</td></tr><tr><td>19</td><td>AF20-2</td><td>Processor</td><td>963</td><td>963</td><td>75.4</td><td>27470.93</td><td>41542.37</td><td>0</td><td>0</td><td>3598.69</td><td>6</td></tr><tr><td>20</td><td>AF20-1</td><td>Processor</td><td>963</td><td>963</td><td>75.4</td><td>27603.99</td><td>41414.65</td><td>0</td><td>0</td><td>3593.34</td><td>6</td></tr><tr><td>21</td><td>AF30-2</td><td>Processor</td><td>936</td><td>936</td><td>77.58</td><td>25745.21</td><td>39655.22</td><td>0</td><td>0</td><td>7211.56</td><td>2</td></tr><tr><td>22</td><td>AF30-1</td><td>Processor</td><td>936</td><td>936</td><td>77.58</td><td>25727.15</td><td>38432.22</td><td>1217.94</td><td>0</td><td>7234.68</td><td>2</td></tr><tr><td>23</td><td>Entmagnet</td><td>Processor</td><td>954</td><td>954</td><td>76.11</td><td>2098.8</td><td>70343.69</td><td>0</td><td>0</td><td>169.49</td><td>1</td></tr><tr><td>24</td><td>Entmagnet</td><td>Processor</td><td>954</td><td>954</td><td>76.11</td><td>2098.8</td><td>69901.2</td><td>0</td><td>0</td><td>611.99</td><td>1</td></tr><tr><td>25</td><td>AF40-1</td><td>Processor</td><td>902</td><td>902</td><td>80.5</td><td>15109.76</td><td>37634.54</td><td>1733.36</td><td>0</td><td>18134.32</td><td>5</td></tr></table></body></html>

<html><body><table><tr><td>26</td><td>AF50-1</td><td>Processor</td><td>3604</td><td>900</td><td>80.68</td><td>20685.99</td><td>49430.7</td><td>0</td><td>0</td><td>2495.3</td><td>6</td></tr><tr><td>27</td><td>AF40-2</td><td>Processor</td><td>903</td><td>902</td><td>80.5</td><td>15378.63</td><td>36976.86</td><td>2016.25</td><td>0</td><td>18240.25</td><td>5</td></tr><tr><td>28</td><td>AF50-2</td><td>Processor</td><td>3604</td><td>900</td><td>80.68</td><td>20698.33</td><td>49394.96</td><td>0</td><td>0</td><td>2518.7</td><td>6</td></tr><tr><td>29</td><td>Auslass Rohteile</td><td>Source</td><td>n/a</td><td>1089</td><td>66.68</td><td>n/a</td><td>n/a</td><td>n/a</td><td>n/a</td><td>0</td><td>n/a</td></tr><tr><td>30</td><td>Einlass Rohteile</td><td>Source</td><td>n/a</td><td>1299</td><td>55.9</td><td>n/a</td><td>n/a</td><td>n/a</td><td>n/a</td><td>0</td><td>n/a</td></tr><tr><td>31</td><td>EndProduct1</td><td>End Product</td><td>900</td><td>n/a</td><td>n/a</td><td>n/a</td><td>n/a</td><td>n/a</td><td>n/a</td><td>0</td><td>n/a</td></tr><tr><td>32</td><td>EndProduct2</td><td>End Product</td><td>900</td><td>n/a</td><td>n/a</td><td>n/a</td><td>n/a</td><td>n/a</td><td>n/a</td><td>0</td><td>n/a</td></tr></table></body></html>