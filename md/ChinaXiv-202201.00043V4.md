# 新能源电力系统并网设备小扰动稳定分析(二):导出机理与稳定性分类探讨

宫泽旭1，艾力西尔·亚尔买买提1，辛焕海1\*，张欣‘，鞠平1，袁小明²，屠竟哲³，傅闯4(1．浙江大学电气工程学院，浙江省 杭州市 310027；2．华中科技大学电气与电子工程学院，湖北省 武汉市 430074；3．中国电力科学研究院有限公司，北京市 海淀区 100192；4．南方电网科学研究院有限责任公司，广东省广州市 510663)

# Small Signal Stability Analysis of Grid-connected Equipment in Power System (Part II): Discussion on Mechanism Derivation and Classification of Stability

GONG Zexu1, YAERMAIMAITI Ailixier1, XIN Huanhai1\*, ZHANG Xin1, JU Ping1, YUAN Xiaoming², TU Jingzhe³,FU Chuang4 (1. College of Electrical Engineering, Zhejiang University, Hangzhou 310027, Zhejiang Province, China; 2.College ofElectrical and Electronic Engineering,Huazhong Universityof Science and Technology,Wuhan 430074, Hubei Province,China; 3.China Electric Power Research Institute,Haidian District,Beijing 1Oo192, China; 4. China Southern Power Grid, Guangzhou 510663, Guangdong Province, China)

ABSTRACT: From the perspective of stability equivalence, nominal performance and robustness,the qualitative principles and quantitative evaluation index of stability criterion adaptation are proposed in Part I.In addition, the adaptation of the existing stability criteria and the physical interpretation of instability corresponding to the suitable stability criterion are analyzed for the typical equipment in power system, such as synchronous machines,doubly-fed induction generators (DFIG） and converters in Part II.Thereby the stability classification of the renewable power system is discussed based on dominant output variable.Firstly,aiming at low-frequency and sub-synchronous oscillation/resonance (SSO/SSR）of synchronous machine,the rationality of the existing stability analysis methods and physical interpretation is verified by using the proposed evaluation index.Secondly, the proposed evaluation index is used to analyze the oscillation of converters and DFIG,and the suitable stability criterion,derivation mechanism and dominant output variable are further discussed. Finally,a novel idea of equipment stability classification based on physical mechanism and dominant output variables are proposed,which classifies equipment stability from the vector perspectiveintothreecategories:phase-dominated synchronous stability,amplitude-dominated voltage stability, and electrical resonance formed by their special combination. Issues such as the concept of wide-band oscillation， the distinction between equipment stability and system stability, and the extensibility of their classification are further explored.

KEYWORDS:synchronous machine;converter; doubly-fedinduction generator; stability mechanism; stability classification摘要：该文第一部分从稳定性等价、标称性和鲁棒性3个角度，提出稳定分析方法/判据适应性的定性原则和量化评估指标。第二部分将进一步针对同步机、变流器和双馈机组等典型设备，分析现有稳定判据的适用性及判据对应的失稳物理解释是否合理，并从主导输出变量角度探讨稳定问题的分类方法。首先，利用所提评估指标，验证现有同步机低频振荡和次同步振荡/谐振的稳定分析方法和物理解释的合理性；其次，利用所提评估指标分析变流器和双馈机组振荡问题，探讨其适用的稳定判据、导出机理及主导输出变量；最后，提出基于物理机理及主导输出变量的设备稳定性分类新思路，从矢量角度将设备稳定性分为相角主导的同步稳定、幅值主导的电压稳定和它们特殊组合而成的电气谐振3类。同时还探讨宽频带振荡概念、设备稳定和系统稳定间的联系及稳定性分类的可拓展性等问题。

关键词：同步机；变流器；双馈机组；稳定机理；稳定性分 类

# 0 引言

新能源电力系统出现了一系列新形态的失稳问题[1-3]，且具有时间尺度跨度大[1-4]和稳定机理复杂[2-3]等特征，认知稳定机理是保障新能源电力系统安全稳定运行的关键所在。

本文第一部分的研究表明，不同稳定判据选取的物理视角不同，对稳定问题的适用性也不同。虽然多个判据都可以正确判断系统是否稳定，但只有选择合适的视角/判据时才可以厘清稳定机理并确定决定系统稳定的关键环节，从而有针对性的提出控制措施。根据对物理机理的深入认识，传统电力系统的稳定问题被分为三大类：功角、电压和频率稳定问题[5]。例如，同步机转子摇摆问题属于功角稳定，根据其物理机理发现了阻尼转矩法是适用分析和解决该问题的有效方法[6]。

然而，新能源电力系统中出现的多类新型稳定问题，学术界对其机理认识尚不存在统一的、公认的结论，现有分类往往基于时域形态或时间尺度。稳定机理认识的差异也导致了现有控制措施的多样性，以变流器振荡问题为例：文献[7]基于等效阻抗判据，提出增加虚拟正电阻的振荡抑制方案；文献[8]基于序阻抗判据，提出增加导纳的失稳治理方法；但文献[9]发现增加变流器导纳实部有时反而会恶化系统的稳定性，进而提出基于模态功率的导纳“整形”方法。因为文献[7-9]中采用的各类判据的系统观察视角是不同的，所以发现的引起系统失稳的关键环节和物理机理也不同，从而导致提出的失稳/振荡控制措施的有效性和适用性各不相同。实际上，只有正确识别出主导系统稳定问题的关键变量和失稳机理，才可能找到有效的控制方案[10]。

为此，本文第二部分将稳定判据/机理模型及其导出机理的评估方法应用到同步机、变流器和双馈机组等典型设备的单设备无穷大系统中。针对各个设备特定的稳定问题，探讨其适合的稳定判据及其物理解释。此外，将传统电力系统以相量为基础的模型拓展为以矢量为基础的模型，探索了新能源电力系统中同步机、变流器和双馈机组等设备的失稳共性特征和导出机理，并从主导输出变量和导出机理角度探讨了矢量稳定的分类方法。

具体组织内容如下：首先，基于第一部分所提评估方法，明确设备稳定机理的导出方法。其次，验证针对同步机若干经典方法在低频振荡和次同步振荡问题中的适用性和合理性。然后，针对变流器和双馈机组，分析现有稳定分析方法和判据的适用性，并基于机理判据给出对应的失稳物理解释(即导出机理)。最后，归纳适用各种稳定问题的稳定判据，探讨基于主导输出变量的新能源电力系统设备稳定性分类方法。

# 1设备稳定判据选取及机理导出流程

本文第一部分提出了基于环路增益灵敏度的稳定判据适应性量化评估指标，本节进一步根据该指标评估判据的适用性并导出设备失稳机理。主要分为2个步骤：确定稳定判据集合和稳定判据的适用性分析及机理导出。

# 1.1 确定稳定判据集合

形成判据集合的流程分为两步：

1）建立设备的数学模型，根据设备物理和控制特性，对设备主要物理环节或控制环节进行划分；2）将每个物理或控制部分都分别作为主导环节，消去其他无关变量，形成对应判据。

图1举例介绍了根据物理意义选择稳定判据的思路。设备是一个 $n$ 输入 $n$ 输出的系统，其包含输入 $u _ { 1 }$ 到输出 $y _ { 1 }$ 的回路1、..输入 $u _ { i }$ 到输出 $y _ { i }$ 的回路i、...输入 $u _ { n }$ 到输出 $y _ { n }$ 的回路 $n$ 。其中，如果回路 $i$ 的物理含义明确，则保留 $u _ { i } / y _ { i }$ 形成的稳定判据可以作为判据集合的一个备选判据。

![](images/b463abff04a18541807ea2701ae8b7011ed21a6d325b4c115c7f8134e8211146.jpg)  
图1设备稳定判据的生成思路  
Fig.1 Generation method of stability criterion

需要指出的是，相似物理意义的判据适用范围和对应机理本质是相似的。例如，针对变流器的同步问题，有聚焦锁相环输出状态 $\theta _ { \mathrm { p l l } }$ 的同步回路判据[11]，聚焦端口电压/电流相角的广义阻抗判据[9],聚焦电气惯量的广义转矩系数判据[12]等，它们反映的物理机理是一致的，区别在于某些判据选择的输出是状态变量而其他选择的是相关输出变量，本文不对物理本质相似的判据进行进一步区分。

# 1.2稳定判据的适用性分析及机理导出

聚焦单设备无穷大系统，此时稳定问题和稳定机理由单一设备的动态特性所主导，为表述方便，本文简称其为设备稳定问题，并在第6节探讨设备稳定与系统稳定的区别和联系。

由于不同稳定判据的提出是基于不同机理认识的,失稳机理解释与判据可以一一对应,如图 2(a)所示。如果所选择的稳定判据和分析方法是合适的，形成判据的机理认识也应当是合理的，基于该判据推导出的主导输出变量、导出机理和失稳主要影响因素等也是合理的。因此，基于判据适用性分析，可以反过来溯源或验证对于失稳机理的认识是否合理，也可以进一步导出失稳的关键环节、主导输出变量等，便于稳定治理和分类。

机理认识1u1 yi + 判据1主导变量 y1u2 2 机理认识2 + 判据2专 u2 →y机理认识n+ 判据nun yn Y uy →yn稳定机理 稳定判据机理科学性 判据适用性(a）设备稳定判据与机理的对应关系  
根据设备特性 形成稳定 稳定判据的 稳定机理导出  
划分物理环节 判据集合 适应性分析 及稳定分类步骤1 步骤2 步骤3 步骤4(b）设备稳定判据选取及机理导出及分类的流程

图2设备稳定判据与稳定机理的关系和机理导出流程 Fig.2Relationship between equipment stability criterion and mechanism and the process of mechanism derivation

设备稳定机理导出及分类的流程包括：

1）根据稳定判据集合中各判据是否满足稳定性等价原则、标称性和鲁棒性原则，来选择合适的稳定判据(本文第一部分已详细探讨);

2）得到决定失稳的主导输出变量，并结合设备物理特性，得到失稳的机理解释，即导出机理，并基于主导输出变量进行稳定性分类。

综上所述，图2(b)给出了设备稳定判据选取及机理导出的流程图。对于同步机等机理明晰的设备，通过上述流程可以验证传统稳定机理认知的合理性，而对于变流器等机理不明的设备，则可以导出设备的失稳机理解释。

# 2同步机的稳定判据及其导出机理

# 2.1同步机低频和次同步振荡的判据集合

# 2.1.1 同步机低频振荡的判据集合

同步机单机无穷大系统低频振荡的分析模型如图3所示，该系统有多个输入输出变量：△@、△δ、 $\Delta E _ { \mathrm { f } }$ 、 $\Delta E _ { q } ^ { \prime }$ 、 $\Delta P _ { \mathrm { e } }$ 和 $\Delta U _ { \mathrm { t } }$ 。在机电时间尺度下，主要包含转子和电磁(包括励磁)环节，前者主导同步机的相角特性，后者主导端口电压特性。

![](images/2ceb0823e0bd288e022e5e19ca7f3e011383caf77e64f58c03167a6dccae6255.jpg)  
图3同步机低频振荡传递函数模型 Fig.3Transfer function model for low frequency oscillation of synchronous machine

# 1）阻尼转矩法

同步机低频振荡的经典分析方法是提取转子动态的阻尼转矩法[6,13]。它通过保留 $\Delta \delta$ 和 $\Delta P _ { \mathrm { e } }$ 得到等效模型(图3中蓝色部分作为主导回路)[13]，本质是保留了相角同步特征。对应的特征方程为

$$
1 + L _ { \mathrm { D } } ( s ) = 0
$$

式中开环传递函数 $\scriptstyle L _ { \mathrm { D } } ( s ) = G _ { \mathrm { D } } ( s ) H _ { \mathrm { D } } ( s )$ ，表达式为

$$
\left\{ \begin{array} { l l } { \displaystyle G _ { \mathrm { D } } ( s ) = \frac { 1 } { H s ^ { 2 } + D s } } \\ { \displaystyle H _ { \mathrm { D } } ( s ) = k _ { 1 } - \frac { k _ { 2 } G _ { 3 } ( s ) ( k _ { 4 } + k _ { 5 } G _ { \mathrm { E } } ( s ) ) } { 1 + k _ { 6 } G _ { 3 } ( s ) G _ { \mathrm { E } } ( s ) } } \end{array} \right.
$$

式中： $G _ { 3 } ( s ) { = } k _ { 3 } / ( k _ { 3 } T _ { \mathrm { d 0 } } ^ { \prime } s { + } 1 )$ ; $G _ { \mathrm { E } } ( s ) { = } k _ { \mathrm { E } } / ( T _ { \mathrm { E } } s { + } 1 )$ 为励磁传递函数，变量含义详见文献[13]。

值得一提的是，基于式(1)特征方程中开环传递函数应用奈奎斯特判据，得到等效系统的稳定判据，在弱阻尼下和阻尼转矩法的阻尼判据是一致的。

# 2）励磁环节主导的稳定判据

保留励磁输入/输出 $( \Delta U _ { \mathrm { t } } / \Delta E _ { \mathrm { f } } )$ 时，以图3中阴影部分作为主导环节时，对应的特征方程如下：

$1 + L _ { \mathrm { E } } ( s ) = 0$ (3)

式中开环传递函数 $\scriptstyle { L _ { \mathrm { E } } ( s ) = G _ { \mathrm { E } } ( s ) H _ { \mathrm { E } } ( s ) }$ ，表达式为

$$
\left\{ \begin{array} { l l } { \displaystyle G _ { \mathrm { E } } ( s ) = \frac { k _ { \mathrm { E } } } { 1 + T _ { \mathrm { E } } s } } \\ { \displaystyle H _ { \mathrm { E } } ( s ) = G _ { 3 } ( s ) ( k _ { 6 } - \frac { k _ { 2 } G _ { \mathrm { D } } ( s ) ( k _ { 5 } + k _ { 4 } / G _ { \mathrm { E } } ( s ) ) } { 1 + k _ { 1 } G _ { \mathrm { D } } ( s ) } ) } \end{array} \right.
$$

式(1)、(3)分别为转子动态主导和励磁环节主导的特征方程，形成同步机低频振荡的判据集合。

# 2.1.2同步机次同步振荡的判据集合

同步机次同步振荡(subsynchronous oscillation,SSO)通常根据其产生的场景分为次同步谐振(subsynchronousresonance，SSR)和装置引起的SSO两类，其中SSR通常包括3个表现[13]：感应发电机效应、扭振互作用和暂态力矩放大作用。

次同步振荡问题涉及到电磁暂态时间尺度下的发电机转子轴系和考虑串补后的电路动态等，状态变量为[13]：△𝜔、△δ、△Ef、△Φ、 $\Delta U _ { \mathrm { C } , d q }$ 。频域中的经典方法包括复转矩系数法和等值阻抗分析法[13]，分别对应聚焦同步机的轴系部分和电路等值模型所形成的稳定判据。为体现判据集合的完备性，本文补充一个励磁主导的判据，以供对比分析。

# 1）复转矩系数法

同步机轴系主导的次同步振荡，经典分析方法是复转矩系数法[13]。设第 $i$ 个扭振模式 $s _ { i }$ 为被激励的弱阻尼振荡模式。当同步机电气转子角 $\Delta \delta _ { k }$ 存在振荡模式 $\scriptstyle s _ { 0 } = \sigma _ { 0 } + { \mathrm { j } } \omega _ { 0 }$ ，且接近扭振模式 $s _ { i }$ 时，第 $i$ 个轴系回路主导动态特性，其特征方程为

$$
1 + L _ { \delta } ( s ) = 0
$$

式中 $L _ { \delta } ( s ) { = } G _ { \mathrm { e } } ( s ) G _ { \mathrm { m } } ( s )$ 为系统的开环传递函数，参考文献[14]。文献[14]进一步指出，复转矩系数法与基于奈奎斯特的判据是等价的。

上述等效模型描述了系统轴系的电压相角的动态特性，属于轴系主导的等效模型。

# 2）等值阻抗分析法

对于串补主导的次同步振荡，通常基于等值电路进行分析[13]，电路如图4(a)所示。根据文献[13],电网谐振的次同步谐振频率 $\omega _ { \mathrm { e r } }$ 低于转子频率 $\omega _ { 0 }$ 时，同步机产生感应发电机效应，呈“负电阻”特性进而导致持续振荡。根据系统的谐振阻抗条件：$Z _ { l } ( s ) \mathrm { + } Z _ { \mathrm { S G } } ( s ) \mathrm { = } 0$ 可得，系统的特征方程为

$$
1 + Z _ { 1 } ( s ) / Z _ { \mathrm { S G } } ( s ) = 0
$$

![](images/f516a5c7a9045824f289c80c19e715610f7697e7c69b6891b65979c13fcfdfa1.jpg)  
图4同步机次同步谐振的等效模型  
Fig.4Equivalent model for sub-synchronous resonance of synchronous machine

式中：

$$
\left\{ \begin{array} { l l } { \displaystyle Z _ { \mathrm { 1 } } ( s ) = R + s L + \frac { 1 } { s C } } \\ { \displaystyle Z _ { \mathrm { S G } } ( s ) = R _ { \mathrm { s } } + s X _ { \mathrm { s } } + ( s X _ { \mathrm { m } } ) \parallel ( \frac { R _ { \mathrm { r } } } { s ^ { \prime } } + s X _ { \mathrm { r } } ) } \end{array} \right.
$$

上述模型描述了同步机等值电路的阻抗谐振，等值电路模型的传递函数模型可用图4(b)表示。

# 3）励磁环节主导的稳定判据

以同步机电磁暂态模型为基础，保留励磁系统输入/输出 $( \Delta U _ { \mathrm { t } } / \Delta E _ { \mathrm { f } } )$ 时，也可得到基于电磁暂态，反映端口电压特性的等效模型，其特征方程为

$$
1 + L _ { \mathrm { E E } } ( s ) = 0
$$

式中 $L _ { \mathrm { E E } } ( s )$ 为开环传递函数，推导见附录A。

式(5)、(6)和(8)分别为转子轴系、等值电路和励磁作为主导环节的特征方程，共同组成判据集合。

# 2.2同步机的判据适用性分析及机理导出

2.2.1同步机低频振荡判据适用性分析及机理导出根据附录表B1中的单机无穷大系统参数，对2.1.1节同步机低频振荡的阻尼转矩法和励磁主导判据进行比较和评估，结果如表1所示。

表1同步机低频振荡稳定判据的适用性分析  
Tab.1Adaptation analysis of two stability criteria   

<html><body><table><tr><td>适用性评价</td><td>阻尼转矩法</td><td>励磁判据</td></tr><tr><td>环路增益灵敏度</td><td>4.503∠124.2°</td><td>14038.9∠134.7°</td></tr><tr><td>稳定性等价原则</td><td>满足</td><td>满足</td></tr><tr><td>标称性原则</td><td>满足</td><td>满足</td></tr><tr><td>鲁棒性原则</td><td>鲁棒性较好</td><td>鲁棒性较差</td></tr></table></body></html>

根据表1可知，两种判据均满足稳定性等价和标称性原则，但阻尼转矩法的环路增益灵敏度模值更小，其鲁棒性更好，故认为更能解释低频振荡的机理。阻尼转矩法提取转矩-功角的动态关系，描述了功角同步特性，故低频振荡的主导输出变量为功角(也可看成是内电势相角)。该结论与传统对低频振荡机理的认识一致，也从侧面佐证了本文所提适用性分析及机理导出方法的合理性。

# 2.2.2 同步机次同步振荡判据适用性及机理导出

根据附录B表B2中的参数，对同步机SSO/SSR分析方法：复转矩系数法、等值电路法和励磁主导判据，进行适用性对比分析，结果如表2所示。

表2同步机次同步振荡稳定判据的适用性分析  
Tab.2Adaptation analysis of three stabilitycriteria   

<html><body><table><tr><td>振荡模式so</td><td>适用性评价</td><td>复转矩系数</td><td>等值阻抗</td><td>励磁判据</td></tr><tr><td rowspan="5">-0.05±j65.76 (轴系主导)</td><td>环路增益灵敏度</td><td>1.93 ∠150.8°</td><td>3.64 ∠115.0°</td><td>70.69 ∠173.1°</td></tr><tr><td>稳定性等价原则</td><td>满足</td><td>满足</td><td>满足</td></tr><tr><td>标称性原则</td><td>满足</td><td>满足</td><td>满足</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>鲁棒性原则</td><td>鲁棒性较好 10.26</td><td>鲁棒性适中</td><td>鲁棒性较差</td></tr><tr><td rowspan="5">-0.03±j107.59 (串补主导)</td><td>环路增益灵敏度</td><td>∠137.8°</td><td>4.90 ∠167.4°</td><td>308.34 ∠178.5°</td></tr><tr><td>稳定性等价原则</td><td>满足</td><td>满足</td><td>满足</td></tr><tr><td>标称性原则</td><td>满足</td><td>满足</td><td>满足</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>鲁棒性原则</td><td>鲁棒性适中</td><td>鲁棒性较好</td><td>鲁棒性较差</td></tr></table></body></html>

根据表2可以发现，针对轴系导的振荡，3种判据均满足稳定性等价和标称性原则，但基于复转矩系数法的环路增益灵敏度模值更小，判据的鲁棒性更好，故更适合用于分析和解释此类振荡。该判据通过保留轴系转子角变量，描述了发电机轴系动态，其导出机理为：轴系各质量块的相角摇摆和扭振，引起发电机端口电压相角振荡，与系统的同步特性变差，其主导输出变量为电压相角，该机理也与传统机理认识相符。

针对串补引起的振荡，3种判据均满足稳定性等价和标称性原则，但等值电路法的环路增益灵敏度模值更小、鲁棒性更好，更适合该模式的分析。根据等值阻抗法的分析和物理意义，导出失稳机理可以用电路阻抗谐振来解释，即：同步机在次同步频段下的等值电阻为负，引起系统非工频谐振/振荡，其主导输出变量为电压矢量整体 $\Delta ( U { \mathrm { e } } ^ { { \mathrm { j } } \delta } )$ 。该振荡机理也与串补主导的SSR 传统认知一致[14-15]，即等效电路在次同步频段下同步机感应发电机效应导致的“负电阻”引起了系统失稳。

综上，同步机SSO/SSR适用判据和导出机理可用表4总结，其对应振荡形态详见5.1节。值得一提的是，由其他设备引起的轴系主导SSO等，已有研究表明复转矩系数法也是适用的，其机理与轴系扭振类似，本文方法也能说明这点，限于篇幅不再赘述。另外，同步机SSR的机理与串补度相关，串补度较低时一般由轴系主导，而串补度较高或外电路在扭振互补频率附近呈现明显的电容效应时，则会出现电压相角和幅值共同主导的稳定问题。

# 3变流器的稳定判据及其导出机理

# 3.1变流器多时间尺度振荡的判据集合

光伏、直驱风机等新能源并网系统及柔性直流输电等，可以视为变流器并网模型，其具有多时间尺度特性，其失稳现象呈现宽频特征[3.4]。按变流器控制系统划分，可以分为外环主导、锁相环主导和内环/前馈主导的3类回路，生成3类判据。

1）直流电压稳定判据(外环主导)。

以外环为主导环节的分析手段包括：保留直流电压动态的分析方法[16]；建立内电势与功率之间关系的惯量和阻尼判据[17]等。本文将类似判据统称为直流电压稳定判据。

# 2）相角稳定判据(锁相环主导)。

以锁相环为主导环节的判据主要包括：提取锁相环主导回路的稳定判据[11]；提取相角阻抗的广义阻抗判据；提取电气惯性的广义转矩系数判据[12]等。本文将类似判据统称为相角稳定判据。

# 3）序阻抗判据(内环/前馈主导)。

由于变流器内环/前馈的负阻效应，以其为主导环节的判据主要指，将网络物理特性作为切入点的序阻抗[18]或修正序阻抗判据[19]。

上述3类稳定判据的详细推导及表达式见本文第一部分，这里不再赘述。

# 3.2变流器的判据适用性分析及机理导出

根据本文第一部分适用性分析算例，变流器可以划分为3类稳定问题：

# 1）外环主导的失稳

一般集中在外环带宽下的中低频段或零频段，包括弱阻尼低频振荡和电压崩溃2种失稳形式[16]。适用判据直流电压稳定判据输出变量为 $\Delta U _ { \mathrm { d c } }$ ，结合设备特性，其导出机理为：变流器直流电压振荡或单调失稳，引起输出功率/交流电流幅值失稳，进而导致电压失稳[2,16]。其主导变量为状态变量直流电压，或从系统侧输出变量看，为交流电流幅值。

此外，常规直流电压失稳的内部状态变量为直流电流，对外表现为系统交流电压失稳；异步机堵转引起内部状态变量滑差失稳，等效阻抗急剧减小，进而引起电压/电流幅值失稳[20]。两者与变流器外环主导失稳的失稳特性类似，本文不再赘述。

# 2）锁相环主导的振荡

该失稳问题表现为锁相环带宽下的次/超同步振荡，常发生于接入低短路比弱电网场景[16.21]。相角稳定判据在上述频率段内具有适用性，其导出机理为：变流器和电网的相角阻抗发生谐振，其主导输出变量为电流相角。因此，通过提高电网强度或相角阻尼，可以抑制锁相环失稳[1]，而增加导纳实部则不一定有效[9]。另外，因为功率同步环或虚拟同步控制也是同步控制环节，其失稳特性与锁相环类似，也属于广义的同步稳定问题[21-22]。文献[21]、[23]将该类稳定问题称为“虚拟功角”稳定。

# 3）内环/前馈主导的振荡

内环、前馈或数字/采样延时环节等为变流器的快动态环节，其失稳问题集中于锁相环带宽以外的中高频段，序阻抗判据适合这类问题。其导出机理为：变流器等效序阻抗与电网序阻抗不匹配，内环或前馈等在中高频段下的等效阻抗呈现“负电阻”特性而引起电路谐振，其主导输出变量为电流矢量。该结论也与现有研究相符，即数字/采样延时等“负电阻”效应引起了变流器中高频振荡，可以通过在谐振频段增加电路等效正电阻来抑制[24,25]。

# 4双馈机组的稳定判据及其导出机理

# 4.1双馈机组次同步振荡的判据集合

双馈机组包含机侧和网侧变流器，本节着重考虑机侧变流器主导的次/超同步振荡现象[26]，而网侧变流器主导的稳定性，与上一节变流器并网稳定相似。根据双馈机组次/超同步频段的物理和控制特性，可以分为锁相环和内环主导的2类稳定判据：

# 1）相角稳定判据(锁相环主导)

锁相环主导的稳定判据主要包括：聚焦锁相环的广义阻抗判据和复转矩系数法[27]，这里统称为相角稳定判据。该判据根据相角动态建立阻抗模型，保留锁相环主导的相角回路动态，其特征方程为

$$
1 + L _ { \mathrm { \tiny { P L L } } } ( s ) = 0
$$

式中 $L _ { \mathrm { P L L } }$ 为相角开环传递函数，详见文献[27]。

# 2）序阻抗稳定判据(内环主导)

内环主导的稳定判据主要指聚焦电机与外部电路谐振，考虑正负序耦合，建立双馈风机的序阻抗判据[26]，其特征方程为

$$
1 + L _ { { \boldsymbol { p p } } / n n } ( s ) = 0
$$

式中 $L _ { p p / m }$ 为正/负序阻抗判据，详见文献[26]。

# 4.2双馈机组的判据适用性分析及机理导出

双馈机组在次/超同步振荡频段主要有2种振荡模式：1）锁相环参与度高的振荡；2）线路串补电容与机组等效电感耦合的振荡(串补主导)。

根据附录表B3中的所示的双馈机组并网模型系统参数，针对两种振荡模式，对4.1节的2种判据进行了比较和评估，结果如表3所示。

表3双馈机组两种稳定判据的适用性分析  
Tab.3Adaptation analysis of two stability criteria   

<html><body><table><tr><td>振荡模式so</td><td>适用性评价</td><td>相角判据</td><td>序电路</td></tr><tr><td rowspan="4">-13.17±j54.07 (锁相环)</td><td>环路增益灵敏度</td><td>0.101∠174.9°</td><td>1.382∠126.0°</td></tr><tr><td>稳定性等价原则</td><td>满足</td><td>满足</td></tr><tr><td>标称性原则</td><td>满足</td><td>满足</td></tr><tr><td>鲁棒性原则</td><td>鲁棒性较好</td><td>鲁棒性较差</td></tr><tr><td rowspan="3">-2.57±j251.80 (串补1)</td><td>环路增益灵敏度1</td><td>0.313∠131.6</td><td>0.037∠104.3°</td></tr><tr><td>0 环路增益灵敏度2</td><td>0.138∠147.7°</td><td>0.037∠121.2°</td></tr><tr><td>稳定性等价原则</td><td>满足</td><td>满足</td></tr><tr><td rowspan="2">8.57±j375.17 (串补2)</td><td>标称性原则</td><td>满足</td><td>满足</td></tr><tr><td>鲁棒性原则</td><td>鲁棒性较差</td><td>鲁棒性较好</td></tr></table></body></html>

锁相环参与度较高的振荡一般表现为次/超同步振荡。此时，两个判据均满足稳定性等价和标称性原则，但相角判据的环路增益灵敏度模值更小，鲁棒性更好。因此，广义阻抗判据或复转矩系数法[27]等对锁相环引起的振荡更具有适用性。两种判据均通过保留相角动态得到，其导出机理为：双馈机组的相角阻尼不足，与系统失去同步，其主导输出变量为电流相角。

对于串补主导的振荡，其接入串补电容引起的振荡与电容电压和转子或定子磁链高度相关，一般表现为次同步振荡。此时，2个判据均满足稳定性等价和标称性原则，但序阻抗判据的环路增益灵敏度模值更小，鲁棒性更好。根据序阻抗判据分析及其物理意义，双馈机组在次同步频段内的失稳机理为：双馈机组等效序电路中电阻为负引起失稳[26],其主导输出变量为电流矢量序分量，可引入虚拟等效电阻抑制振荡。

值得一提的是，在充分认识设备的稳定机理后，设备的稳定建模、分析和控制可以流程化和规范化，包括：1）提取稳定的关键变量建立机理模型；2）基于机理模型得到适用判据；3）针对关键环节和主导变量设计稳定控制方法。例如，针对同步机低频振荡分析，首先建立转子转矩-功角关系的海佛容-菲利普斯模型；其次，形成阻尼转矩法；最后，提出安装电力系统稳定器(power systemstabilizer，PSS)的控制策略。电力系统设备对应的稳定现象、机理解释、主导输出变量、推荐判据等总结如表4所示。

表4电力系统设备稳定的现象、机理、判据  
Tab.4Stability phenomenon,mechanism and criterion for power system equipme   

<html><body><table><tr><td>稳定场景</td><td>稳定现象</td><td>导出机理</td><td>主导输出变量</td><td>推荐判据</td><td>稳定类型</td></tr><tr><td rowspan="2">同步机</td><td>低频振荡</td><td>阻尼转矩不足 导致发电机功角相对系统摇摆</td><td>电压相角</td><td>阻尼转矩法</td><td>相角稳定</td></tr><tr><td>次同步振荡</td><td>轴系各质量块的扭振 导致内电势相角的振荡</td><td>电压相角</td><td>复转矩系数法</td><td>相角稳定</td></tr><tr><td>同步机+串补</td><td>次同步振荡</td><td>电机次同步频段 等效负电阻导致的电路谐振</td><td>电压矢量</td><td>等值阻抗分析法</td><td>电气谐振</td></tr><tr><td>异步机</td><td>电压振荡 或电压单调失稳</td><td>内状态滑差振荡或失稳 导致交流电压振荡或单调失稳</td><td>电压幅值</td><td></td><td>幅值稳定</td></tr><tr><td>常规直流</td><td>电压振荡 或电压单调失稳 电压振荡</td><td>内状态直流电流失稳 导致交流电流振荡或单调失稳 内状态直流电压失稳</td><td>电流幅值</td><td></td><td>幅值稳定</td></tr><tr><td rowspan="2">变流器</td><td>次/超同步振荡</td><td>相角等效阻尼不足 导致电流相角振荡或失去同步</td><td>电流相角</td><td>相角稳定判据 (广义阻抗判据等)</td><td>相角稳定</td></tr><tr><td>中高频振荡</td><td>内环/前馈/延时中高频段 等效负电阻导致的电路谐振</td><td>电流矢量</td><td>修正序阻抗判据</td><td>电气谐振</td></tr><tr><td>双馈机+串补</td><td>次/超同步振荡</td><td>电机次同步频段 等效负电阻导致的电路谐振</td><td>电流矢量</td><td>修正序阻抗判据</td><td>电气谐振</td></tr><tr><td>双馈机组</td><td>次/超同步振荡</td><td>相角等效阻尼不足 导致电流相角振荡或失去同步</td><td>电流相角</td><td>相角稳定判据 (广义阻抗判据等)</td><td>相角稳定</td></tr></table></body></html>

# 5基于导出机理的设备矢量稳定性分类

本节尝试对表4讨论的设备稳定性进行总结分类。观察该表可以发现，同步机、变流器和双馈机组等典型设备的稳定机理差异很大，找到他们的共性存在困难：1）设备导出机理中涉及到的变量，有的是相量，有的是矢量，难以从设备电气量角度找到共性特征；2）设备失稳问题的主导环节等要素差异较大，难以找到设备物理环节上的共性特征。因此，目前IEEE等组织是将新能源设备引起的稳定问题看成单独一类，如后文图6(a)所示[I]。

为解决上述问题，本文从单设备稳定机理认知出发，尝试将这些设备的稳定问题进行融合，分为2 个主要步骤：1）针对问题1，将设备模型从相量扩展为矢量进行描述，从而将同步机和新能源稳定问题统一融合为设备的矢量稳定问题，奠定稳定性分类的数学和物理基础；2）针对问题2，借鉴传统电压稳定的分类思路，基于主导输出变量和导出机理，从物理上实现对不同稳定问题的分类。

# 5.1基于矢量的统一建模分析及分类思路

同步机和新能源的分析模型基础分别是相量模型和瞬时值矢量模型，因而对应的稳定问题无法纳入到统一的分类体系中。例如，同步机低频振荡的主导变量功角，是基于正弦量的相量；新能源锁相环引起振荡的主导变量电流相角，是基于瞬时值的电气矢量。虽然两者都是电气量的相角，但物理意义存在差异。

为解决该问题，借鉴电机学中空间矢量思路，将传统电力系统中利用相量的建模对象也扩展为基于矢量的动态模型，且基于矢量的分析结果也可以兼容基于相量的分析结果[28]。由于相量和矢量的幅值/相角在数学上都可以用向量的幅值/角度表示，因此，在表4中同步机和新能源设备模型/稳定问题可以统一为瞬时值矢量模型/稳定问题。此时，电气量的幅值和相角对应的物理意义和数学意义都一致，从而为传统电力系统稳定问题和新能源电力系统稳定问题的融合奠定了模型基础。

基于矢量模型和分析方法，各设备的动态特性都可以通过电气矢量进行描述，其表达式为

$$
Y ( t ) = y ( t ) \mathrm { e } ^ { \mathrm { j } [ \omega ( t ) t + \varphi ( t ) ] }
$$

电气矢量统一建模和分析方法克服了不同设备主导变量物理含义不一致、难以融合的障碍。基于此，同步机和新能源等设备的稳定性问题都能从电气矢量的角度进行分析，可以认为表4中的主导输出变量都是电气矢量。

再结合表4，发现同步机、双馈机组、变流器和常规直流等常见设备的主导输出变量和导出机理，在同步旋转坐标系下，都能从极坐标中按照幅值主导、相角主导以及矢量整体主导这几个维度去描述，即，出现的稳定问题可分为三类，后文分别称之为电压(幅值)稳定、同步(相角)稳定和电气谐振，其中电压稳定、同步稳定和电气谐振仍然借鉴IEEE最新分类中的术语，具体论述见5.2节。由于这些稳定问题是基于电气矢量进行描述的，故可称之为矢量稳定。

![](images/9ad64131a6eb9b1faf1d7d2c42b33bafd100cd8c39ebc76c348112cf7437edeb.jpg)  
图5主导输出变量的极坐标示意图  
Fig.5Schematic diagram of dominant output variable in polar coordinates

上述三种稳定，也分别对应了极坐标中电气矢量 $Y ( t )$ 的3个典型的方向：1)幅值方向(极轴方向);2）相角方向(极角方向)；3）矢量整体变化方向，如图5所示。为直观说明这几类矢量稳定的特征，表5从小扰动角度给出了相角振荡、幅值振荡和电气谐振的特征。其中，幅值振荡和相位振荡可以理解为电气矢量的幅值和相位中存在“周期性波动”；电气谐振较为特殊，可理解为幅值和相位同时存在“周期性波动”，且这两个波动幅值相等、相位相差 $\pi / 2$ ，证明详见附录C。本文第一部分附录C也从时域仿真中给出这3种振荡的典型特征。

表5极坐标下电气量振荡的矢量特征  
Tab.5Vector characteristics of electrical quantity oscillation in polar coordinate   

<html><body><table><tr><td>相角振荡 幅值振荡 电气谐振</td></tr><tr><td>矢量表达式 Ym=yo[1+yRe-a sin(@Rt+φR)]ej(@t+） Yp =yeilt++ye"sn(@+）</td></tr></table></body></html>

# 5.2基于主导输出变量的矢量稳定性分类方法

同步机和新能源设备的稳定机理差别很大，很难从机理上说明将这些稳定问题的物理共性。为此，本文借鉴传统电力系统电压稳定的形成思路，从主导输出变量和导出机理角度实现多种稳定机理的统一。具体的思路介绍如下：

在传统电力系统分类中，电压稳定可以看成是从主导输出变量角度进行稳定性定义和分类的结果，将不同失稳机理的问题统一归类为电压稳定。例如，常规直流的电压失稳是由内部主导状态变量直流电流引起，而对外表现为主导输出变量交流电压的失稳；异步机导致的电压稳定则是由内部滑差状态失稳引起的交流电压失稳[20]。其中，它们的主导输出变量都可以归结为交流电压/电流幅值，而失稳机理也可以用电压-无功的动态关系进行解释。这么做的优势在于，可以将机理不同的设备稳定问题归类在一起，并且提升这类稳定性的手段也具有共性。

受此启发，将此思想在同步机和新能源设备等的稳定性分类中推广，即基于主导输出变量将各种失稳机理从物理上进行重新梳理和归纳。基于此，失稳可以解释为：设备主导状态失稳引起的主导输出变量失稳。例如，变流器直流电容电压状态变量失稳导致的交流电流幅值失稳，与异步机等内状态引起的电压幅值失稳，它们的主导输出变量都是电气量的幅值维度，故可以统一归结为幅值稳定问题；变流器锁相环引发的稳定问题，与同步机同步失稳的主导输出变量都是电气量的相角维度，故可统一归结为相角稳定问题；电路谐振引发的稳定问题，其主导输出变量是非工频的矢量整体，且其机理可用等效电路解释。

此外，为了和传统电力系统稳定性分类术语一致，将主导输出变量为电气矢量幅值和相角的稳定问题，也分别称之为电压稳定和同步稳定；将矢量整体主导的稳定问题，称之为电气谐振。

# 5.3设备矢量稳定性分类结果

根据上述基于导出机理和主导输出变量的分类思想，将表4中同步机、双馈机组和变流器等设备的稳定问题进行归类，得到的设备矢量稳定性分类结果如图6(b)所示，并在第6节扩展为图6(c)所示的系统稳定，主要包括：

# 1）同步稳定(相角稳定)

指电气量相角分量的稳定性，反映了设备与系统的同步性能。此时主导输出变量也是主导状态变量，如同步机功角、虚拟同步机的虚拟功角等，故有时也是状态同步稳定。此外，同步机轴系主导的SSO/SSR、变流器锁相环失稳等则是由于内部状态如轴系转子角、锁相角等失稳，进而激发输出电压/电流相角的失稳。同步稳定在矢量稳定图谱内属于电气量相角主导的稳定，包含的问题如图6(d)所示。

# 2）电压稳定(幅值稳定)

指电气矢量幅值分量的稳定性，反映了维持母线电压的能力。其失稳原因一般是内部状态量失稳引起的输出电压/电流幅值失稳[2.20]，其中交流电流幅值失稳最终也表现为电压幅值的失稳，因此它们也可被认为是电压稳定。例如，异步机滑差、变流器外环、常规直流外环等环节主导的稳定问题，都能找到对应的失稳内状态，进而导致端口输出电压/电流幅值失稳。电压稳定在矢量稳定图谱内属于电气量幅值主导的稳定，包含的问题如图6(d)所示。

# 3）电气谐振

指电气矢量整体的稳定性，反映了等效电路谐振特性。其失稳原因是由设备(也包含网络元件)的状态变量引起的输出电压/电流矢量整体主导的稳定。在矢量稳定图谱下属于电气量矢量整体主导的稳定，包含的问题如图6(d)所示。

需要特别指出的是，在IEEE在2020年的新稳定性分类中，串补电容与感应发电机效应的等效电路谐振问题被归为谐振稳定性下的“电气谐振”[]。本文借鉴电气谐振这一术语，来指代电气矢量整体主导的稳定问题，原因为：电气谐振包含的电机加串补引起的稳定问题，与本文所讨论的这类稳定问题一致，其失稳机理都是等效电路存在负电阻，且主导输出变量都是矢量整体。在此基础上，本文扩展了该稳定问题的内涵，并进一步指出其特点：电气矢量的幅值和相位存在强耦合，在极坐标下观察时，剔除稳态分量后，它在幅值和相位上同时存在一个振幅相等但相位相差 $\pi / 2$ 的振荡分量；这不是一类新的稳定问题，传统电力系统中也存在该问题，如串补引起的同步机次同步振荡、电气网络的LC谐振等，只是在新能源电力系统中更具有不可忽视的地位。

基于上述讨论，对比图6中图(a)和图(b)可以发现，本文保留了IEEE 稳定性分类中部分术语，并将其含义进一步梳理和扩展，使得之前难以融合的稳定问题，如变流器驱动的稳定问题等，可以较好地融合到这几个稳定类型中。在进一步考虑频率稳定问题后，可以形成本文推荐的新能源电力系统稳定性分类，如图6(c)所示，这部分扩展内容将在第6 节中详细讨论。

![](images/dae0c3feb92d903bde50d7ad1ea705494056cea304f358b977a295251f1a4040.jpg)  
图6新能源电力系统的稳定性分类  
Fig.6Stabilityclassification of renewable power system

# 6进一步探讨

1）探讨1：根据机理对宽频振荡进行分类

通过时域波形或振荡频率等特性区分稳定性，一般难以反映机理。即使在同一个频段内，多样化设备可能发生同步失稳、电压失稳和电气谐振失稳等不同类型的失稳问题。例如，变流器锁相环主导的振荡，和双馈机组加串补引起的振荡，振荡频率接近，但本质分别属于同步稳定和电气谐振。

本文分析了常见设备的多时间尺度振荡，发现虽然他们的振荡频率覆盖很宽，但仍可以按各自导出机理/主导输出变量进行归类。此外，工业界或学术界针对电力电子设备的振荡频率分布很宽这一现象，常常称之为宽频振荡并认为是一种新稳定问题的说法值得商榷，不利于深入理解和解决该问题。

2）探讨2：基于主导输出变量的稳定性分类

本文的稳定性分类是基于主导输出变量进行划分的，而电力系统设备的失稳一般是由设备的状态变量失稳所引起，本质是由某一主导状态变量所决定的。但是由于状态变量的失稳一般也能反映到对应的输出变量中[21]，进而可以从主导输出变量角度对稳定性进行划分。

在传统电力系统稳定性分类中，功角/同步稳定是从状态同步的角度进行归纳，电压稳定则是从主导输出变量角度归纳。基于主导输出变量的电压稳定可以囊括多种失稳机理下的稳定问题，例如，异步机和常规直流诱发的交流电压崩溃分别是不同状态变量失稳引起的，但最终均由幅值主导，从而统一归纳为电压稳定。为了更好地梳理和兼容现有和未来电力系统的稳定性分类，本文将这种思想推广，将同步稳定和电气谐振也从主导输出变量角度进行定义和归类，从而可以统一归纳多样化设备的稳定问题。

# 3）探讨3：小扰动稳定与大扰动稳定

小扰动稳定由线性化模型导出，但大扰动和在小扰动下的轨迹在双曲平衡点附近拓扑结构同胚，故一个小扰动失稳一般会对应一个大扰动失稳。因此，按照同步、电压和电气谐振的划分方法并不局限于周期性振荡失稳，可以扩展到非周期单调失稳，如变流器外环主导的电压崩溃仍可归为幅值稳定。此外，考虑非线性后，至少应该包括与幅值/相角这些物理变量相关的大扰动失稳机理，这些都需要未来进一步研究和探讨。

# 4）探讨4：设备稳定与系统稳定

本文虽然聚焦单设备并网系统的稳定特性，但研究结果对多设备系统的稳定机理及分类具有重要的参考价值。例如，基于广义短路比的推导思路，同构多机系统的稳定模式可以近似看成由多个等效单机稳定模式的并集[29]，从而单机与多机的稳定问题和机理一一对应。此时，该多机系统的稳定问题也可以参照设备稳定问题进行分类。

其次，系统稳定和设备稳定有时候要根据影响来区分。单设备或设备群的失稳虽然是设备与电网相互作用的结果，但当设备容量较小或对系统影响较小时，该问题仍被认为是设备稳定问题。例如，小容量异步机堵转使得母线电压轻微波动的问题，被排除在系统电压稳定之外。这也是本文采用“设备稳定”这一术语的原因。相反，当单设备失稳对系统影响较大时，尽管失稳主要由设备特性决定，但该问题也被归结为系统稳定。例如，大容量常规直流引起的稳定问题既可看成是设备稳定问题，也是受关注的系统稳定问题。

此外，设备稳定性是基于单设备无穷大系统模型导出，忽略了电网频率变化。但在分析多设备构成的电力系统同步问题时，同步后会达到一个共模分量，即反映系统频率特性[30]。因此，当考虑系统存在功率不平衡时还会引起频率越限或失稳的问题，故系统稳定性中还包含了频率稳定性。

综上，前文探讨的设备稳定性分类结果在系统中也应该存在，系统的稳定性至少包含图6(c)所示的同步稳定、电压稳定、电气谐振和频率稳定4类。设备稳定是系统稳定的子集，将设备稳定性分类拓展到系统稳定完整的分类，还需进一步研究。

# 6 结论

利用本文第一部分所提的稳定判据适用性分析方法，基于典型参数分析了同步机、变流器和双馈机组等设备多时间尺度稳定问题的判据合理性、导出机理和主导输出变量，发现这些设备的稳定问题可以从电气矢量的相角、幅值及矢量整体3个维度进行归类。其中，同步机的低频振荡、轴系主导的次同步振荡、变流器和双馈风机锁相环引起的振荡可以归结为相角主导的同步稳定；变流器外环、常规直流外环等引起的失稳则可以归为幅值主导的电压稳定；LC电路谐振、同步机或双馈机组经串补引起的次同步振荡、变流器内环/前馈引起的中高频振荡则可以归为电气谐振。所提出的矢量稳定性分类，融合了新能源宽频带/多时间尺度振荡问题和传统电力系统稳定问题，为分析和解决高比例新能源电力系统的稳定问题提供一定的理论基础。每类稳定问题的基本模型、分析和控制方法未来还需深入研究。

# 致谢

业内专家和匿名审稿专家在文章修改过程中提出了极具建设性的意见和建议，作者对此致以诚挚的敬意和衷心的感谢！

# 参考文献

[1]HATZIARGYRIOUN，MILANOVICJ，RAHMANNC, et al．Definition and classification of power system stability-revisited& extended[J].IEEE Transactions on Power Systems，2021，36(4):3271-3281.   
[2]杨鹏，刘锋，姜齐荣，等．“双高"电力系统大扰动稳定 性：问题、挑战与展望[J].清华大学学报：自然科学版, 2021，61(5): 403-414. YANG Peng， LIUFeng， JIANG Qirong，et al.Large-disturbance stability of power systems with high penetration of renewables and inverters:phenomena, challenges，and perspectives[J]．Journal of Tsinghua University: Science and Technology，2021，61(5): 403-414(in Chinese).   
[3]谢小荣，贺静波，毛航银，等．“双高"电力系统稳定性 的新问题及分类探讨[J]．中国电机工程学报，2021, 41(2): 461-475. XIE Xiaorong，HE Jingbo，MAO Hangyin，et al．New issues and classification of power system stability with high shares of renewables and power electronics[J]．Proceedings of the CSEE，2021，41(2): 461-475(in Chinese).   
[4]袁小明，程时杰，胡家兵．电力电子化电力系统多尺度 电压功角动态稳定问题[J]．中国电机工程学报，2016, 36(19): 5145-5154. YUANXiaoming，CHENGShijie，HU Jiabing. Multi-time scale voltage and power angle dynamics in power electronics dominated large power systems[J]．Proceedings of the CSEE，2016，36(19): 5145-5154(in Chinese).   
[5] KUNDUR P，PASERBA J，AJJARAPU V，et al.Definition and classification of power system stability detinitions[J]． IEEE Transactions on Power Systems, 2004，19(3):1387-1401.   
[6] KUNDUR P.Power system stability and control[M]. New York:McGraw-Hill，1994.   
[7]HE Jinwei,LI Yunwei,BOSNJAK D,et al. Investigation and active damping of multiple resonances in a parallelinverter-based microgrid[J]． IEEE Transactions on Power Electronics，2013，28(1): 234-246.   
[8]李光辉，王伟胜，刘纯，等．直驱风电场接入弱电网宽 频带振荡机理与抑制方法(二)：基于阻抗重塑的宽频带 振荡抑制方法[J]．中国电机工程学报，2019，39(23)： 6908-6920. LI Guanghui ，WANG Weisheng，LIU Chun，et al． Mechanism analysis and suppression method of wideband oscillation of PMSG wind farms connected to weak grid(Part II): suppression method of wideband Oscillation based on impedance reshaping[J]．Proceedings of the CSEE，2019，39(23): 6908-6920(in Chinese).   
[9] 董炜，杨超然，辛焕海，等．变流器并网系统复电路模 态功率分析[J]．中国电机工程学报，2019，39(7)： 1919-1932. DONG Wei，YANG Chaoran，XIN Huanhai，et al . Complex circuit modalpoweranalysisof grid-connected converters[J]. Proceedings of the CSEE, 2019，39(7): 1919-1932(in Chinese).   
[10]吴为，汤涌，孙华东，等．电力系统暂态功角失稳与暂 态电压失稳的主导性识别[J].中国电机工程学报,2014, 34(31): 5610-5617. WU Wei， TANG Yong，SUN Huadong，et al．The recognition of principal mode between rotor angle instability and transient voltage instability[J]. Proceedings of the CSEE，2014，34(31): 5610-5617(in Chinese).   
[11] HUANG Linbin ， XIN Huanhai，LI Zhiyi，et al．Grid-synchronization stability analysis and loop shaping for PLL-based power converters with different reactive power control[J]. IEEE Transactions on Smart Grid，2020，11(1):501-516.   
[12] LI Yitong,GU Yunjie,GREEN T C.Mapping of dynamics between mechanical and electrical ports in SG-IBR composite grids[Z]． arxiv:2105.06583，2021.   
[13]倪以信，陈寿孙，张宝霖．动态电力系统的理论和分析 [M]．北京：清华大学出版社，2002. NI Yixin，CHEN Shousun，ZHANG Baolin．Theory and analysis of dynamic power system[M].Beijing:Tsinghua University Press， 2002(in Chinese).   
[14]HARNEFORS L．Proofandapplication ofthe positive-net-dampingstabilitycriterion[J].IEEE Transactions on Power Systems， 2011，26(1):481-482.   
[15]文劲宇，孙海顺，程时杰．电力系统的次同步振荡问题 [J]．电力系统保护与控制，2008，36(12)：1-4，7. WENJinyu，SUNHaishun, CHENG Shijie．Subsynchronous oscillation in electric power systems[J]. Power System Protection and Control，2008, 36(12):1-4， 7(in Chinese).   
[16]邢光正，吴琛，陈磊，等．电压源变换器接入电网的小 扰动稳定机理分析[J]．电力自动化设备，2020，40(9)： 42-49，162. XING Guangzheng, WU Chen,CHEN Lei, et al. Analysis of small disturbance stability mechanism forgridconnected voltage source converter[J]．Electric Power Automation Equipment，2020，40(9)：42-49，162(in Chinese).   
[17] HUANG Yunhui， ZHAI Xuebing，HU Jiabing，et al.Modeling and stability analysis of VSC internal voltage in DC-link voltage control timescale[J]． IEEE Journal of Emerging and Selected Topics in Power Electronics, 2018, 6(1): 16-28.   
[18] CESPEDES M，SUN Jian． Impedance modeling and analysis of grid-connected voltage-source converters[J]． IEEE Transactions on Power Electronics, 2014，29(3): 1254-1261.   
[19] RYGG A,MOLINAS M, ZHANG Chen,et al.A modified sequence-domainimpedancedefinitionandits equivalence to the Dq-domain impedance definition for thestabilityanalysisofACpowerelectronic systems[J].IEEE Journal of Emerging and Selected Topics in Power Electronics，2016，4(4):1383-1396.   
[20]汤涌．电力系统电压稳定性分析[M]．北京：科学出版 社，2011：10. TANG Yong． Voltage stabilityanalysisofpower system[M].Beijing: Science Press,2011:10(in Chinese).   
[21]黄林彬，辛焕海，鞠平，等．电力电子并网装备的同步 稳定分析与统一同步控制结构[J]．电力自动化设备， 2020，40(9):10-25. HUANG Linbin，XIN Huanhai， JU Ping，et al ．Synchronization stabilityanalysisandunified synchronization control structure of grid-connected power electronicdevices[J]. Electric PowerAutomation Equipment，2020，40(9):10-25(in Chinese).   
[22]徐政.电力系统广义同步稳定性的物理机理与研究途径 [J]．电力自动化设备，2020，40(9)：3-9. XU Zheng. Physical mechanism and research approach of generalized synchronous stabilityfor power systems[J]. Electric Power Automation Equipment,2020, 40(9): 3-9(in Chinese).   
[23] XIN Huanhai，HUANG Linbin， ZHANG Leiqi，et al .SynchronousinstabilitymechanismofP-f

current saturation[J]．IEEE Transactions on Power Systems，2016，31(6):5206-5207. [24] WANG Xiongfei, BLAABJERG F. Harmonic Stability in powerelectronic-basedpowersystems ：concept , modeling，and analysis[J]．IEEE Transactions on Smart Grid，2019，10(3):2858-2870.

[25]徐政，王世佳，邢法财，等．电力网络的谐振稳定性分析方法研究[J]．电力建设，2017，38(11)：1-8.XU Zheng，WANG Shijia, XING Facai, et al. Qualitativeanalysismethodofelectricnetworkresonancestability[J]. Electric Power Construction，2017，38(11):1-8(in Chinese).  
[26]张学广，邱望明，方冉，等．双馈风电机组静止坐标系下阻抗建模及次同步谐振抑制策略[J]．电力系统自动化，2019，43(6):41-48，106.ZHANG Xueguang，QIU Wangming，FANG Ran，etal．Impedance modeling and sub-synchronous resonancemitigation strategy of DFIG based wind turbine in staticreference frame[J]· Automation of Electric PowerSystems，2019，43(6):41-48，106(in Chinese).  
[27] 刘巨，姚伟，文劲宇．考虑 PLL 和接入电网强度影响的双馈风机小干扰稳定性分析与控制[J].中国电机工程学报，2017，37(11):3162-3173.LIU Ju，YAO Wei，WEN Jinyu． Small signal stabilityanalysis and control of double-fed induction generatorconsideringinfluenceofPLLandpowergridstrength[J]． Proceedings of the CSEE，2017，37(11):3162-3173(in Chinese).  
[28] BELIKOV J， LEVRON Y. Comparison of time-varyingphasor and dqO dynamic models for large transmissionnetworks[J]． International Journal of Electrical Power &Energy Systems，2017，93:65-74.  
[29]辛焕海，甘德强，鞠平．多馈入电力系统广义短路比：多样化新能源场景[J]．中国电机工程学报，2020，40(17): 5516-5527.XIN Huanhai, GAN Deqiang,JU Ping. Generalized shortcircuit ratio of power systems with multiple powerelectronic devices: analysis for various renewable powergenerations [J]. Proceedings of the CSEE，2020，40(17):5516-5527(in Chinese).  
[30] 高晖胜，辛焕海，黄林彬，等．新能源电力系统的共模频率分析及其特征量化[J]．中国电机工程学报，2021,41(3): 890-899.GAO Huisheng，XIN Huanhai，HUANG Linbin，et

al. Characteristic analysis and quantification of common mode frequency in power systems with high penetration of renewable resources[J].Proceedings of the CSEE，2021, 41(3): 890-899(in Chinese).

# 附录A

同步机次同步振荡的励磁传递函数模型推导。根据文献[13]同步机的电磁模型，线性化可得

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { \Delta U _ { d } = G _ { q } ( s ) \Delta I _ { q } - R _ { a } \Delta I _ { d } } \\ { \Delta U _ { q } = G _ { \mathrm { f } } ( s ) \Delta E _ { \mathrm { f } } - G _ { d } ( s ) \Delta I _ { d } - R _ { a } \Delta I _ { q } } \end{array} \right. } \end{array}
$$

其励磁系统传递函数为 $G _ { \mathrm { E E } } ( s )$ ，则励磁模型为

$$
\Delta E _ { \mathrm { f } } = G _ { \mathrm { E E } } ( s ) \Delta U _ { \mathrm { \ell } } = \frac { G _ { \mathrm { E E } } ( s ) } { U _ { \mathrm { \ell 0 } } } ( U _ { \mathrm { \ell 0 } } \Delta U _ { \mathrm { \ell } } + U _ { \mathrm { \ell 0 } } \Delta U _ { \mathrm { \ell } } )
$$

发电机采用六质量块弹性轴系模型为

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { H s \Delta \omega + D \Delta \omega + K \Delta \delta = - \Delta T _ { \mathrm { e } } } \\ { s \Delta \delta = \omega _ { \mathrm { 0 } } \Delta \omega } \end{array} \right. \Rightarrow \Delta \delta _ { \mathrm { s } } = G _ { \delta } ( s ) \Delta T _ { \mathrm { e } } } \end{array}
$$

网侧考虑串补电容、电感、电阻的模型为

$$
\begin{array}{c} \begin{array} { r } { \left\{ \underbrace { \left[ \begin{array} { l l } { R + s L } & { - \omega _ { 0 } L } \\ { \omega _ { 0 } L } & { R + s L } \end{array} \right] } _ { Z _ { l } ( s ) } \left[ \begin{array} { l } { \Delta { \cal I } _ { x } } \\ { \Delta { \cal I } _ { y } } \end{array} \right] = \left[ \begin{array} { l } { \Delta { \cal U } _ { x } } \\ { \Delta { \cal U } _ { y } } \end{array} \right] - \left[ \begin{array} { l } { \Delta { \cal E } _ { x } } \\ { \Delta { \cal E } _ { y } } \end{array} \right] - \left[ \begin{array} { l } { \Delta { \cal U } _ { c x } } \\ { \Delta { \cal U } _ { c y } } \end{array} \right] \right.} \\ { \left[ \begin{array} { l l } { s C } & { - \omega _ { 0 } C } \\ { \underbrace { \omega _ { 0 } C } _ { Z _ { c } ( s ) } } & \end{array} \right] \left[ \Delta { \cal U } _ { c x } \right] = \left[ \begin{array} { l } { \Delta { \cal I } _ { x } } \\ { \Delta { \cal I } _ { y } } \end{array} \right] } \end{array}   \end{array}
$$

通过 $x y - d q$ 坐标变换，将式(A4)转化到同步坐标系下，结合(A3)可得

$$
\begin{array} { r l } & { \quad \quad \quad \left\lfloor \stackrel { \ldots } { \Delta } I _ { q } \right\rfloor = Y _ { \mathrm { n e t } } \left\lfloor \stackrel { \ldots } { \Delta } I _ { q } \right\rfloor } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad Y _ { \mathrm { n e t } } = \left( \mathbf { Z } _ { 1 } + \mathbf { Z } _ { \mathrm { C } } + G _ { \mathcal { S } } \left[ I _ { d } \cos \delta _ { 0 } \quad I _ { q } \sin \delta _ { 0 } \right] \right) ^ { - 1 } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \left( I - G _ { \delta } \left[ U _ { d } \sin \delta _ { 0 } \quad U _ { q } \sin \delta _ { 0 } \right] \right) } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \end{array}
$$

结合式(A1)、(A2)、(A3)可得同步机以励磁系统为主导回路的传递函数模型，特征方程如式(9)所示，其中反馈传递函数 $H _ { \mathrm { E E } } ( s )$ 表达式为

$$
H _ { \mathrm { E E } } = \left[ \frac { U _ { d 0 } } { U _ { t 0 } } \begin{array} { c c } { \frac { U _ { q 0 } } { U _ { t 0 } } } \end{array} \right] \left( 1 + \left[ \begin{array} { c c } { R _ { a } } & { - G _ { q } } \\ { G _ { d } } & { R _ { a } } \end{array} \right] Y _ { \mathrm { n e t } } \right) ^ { - 1 } \left[ \begin{array} { c } { 0 } \\ { G _ { \mathrm { f } } } \end{array} \right]
$$

式中 $L _ { \mathrm { E E } } ( s ) { = } G _ { \mathrm { E E } } ( s ) H _ { \mathrm { E E } } ( s )$ ，符号说明见文献[13]。

# 附录B

算例模型参数。

# 表B1同步机低频振荡模型参数

Tab.B1Parameters for low frequency oscillation of synchronous machine   

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>转子惯性H,阻尼D</td><td>8,0.8pu</td></tr><tr><td>同步电抗Xd, Xq</td><td>1.2,0.9pu</td></tr><tr><td>d轴暂态电抗Xd</td><td>0.2pu</td></tr><tr><td>d 轴开路暂态时间常数Tdo</td><td>8s</td></tr><tr><td>线路电抗Xline</td><td>0.35pu</td></tr><tr><td>励磁系统传递函数GE(s)</td><td>100/(1+0.1s)</td></tr></table></body></html>

# 表B2同步机次同步振荡模型参数

Tab.B2Parameters for sub-synchronous oscillation of synchronous machine   
表B3双馈风机并网系统参数  

<html><body><table><tr><td rowspan="2">参数</td><td colspan="2">数值</td></tr><tr><td>工况1</td><td>工况2</td></tr><tr><td>轴系惯性H1,2.4.5,6/pu</td><td>(2.08,2.08,2.08, 2.08,1.38,0.05)</td><td>(2.08,2.08,2.08, 2.08,1.38,0.05)</td></tr><tr><td>轴系阻尼D1,2.3.4,5.6/pu</td><td>(0.05,0.12,0.12, 0.12,0.12.0.12)</td><td>(0.05,0.15,0.15, 0.15,0.15,0.15)</td></tr><tr><td>轴系弹性系数K12.23.34,45.56/pu</td><td>(10.5,18.9,26.3, 57.8,5.2)</td><td>(10.5,18.9,26.3, 57.8,5.2)</td></tr><tr><td>同步机等效内阻 Ra/pu</td><td>0.05</td><td>0.05p.u.</td></tr><tr><td>同步电抗 Xd, Xq/pu</td><td>2.07,1.97</td><td>1.75,1.35</td></tr><tr><td>暂态电抗Xd,X/pu</td><td>0.49,1.2</td><td>0.32.0.85</td></tr><tr><td>次暂态电抗Xd, X/pu</td><td>0.35,0.35</td><td>0.25.0.25</td></tr><tr><td>开路暂态时间常数Tdo,Tqo/s</td><td>6.5,1.5</td><td>6.5,1.5</td></tr><tr><td>开路次暂态时间常数 Tdo, Tqo/s</td><td>0.05,0.03</td><td>0.05.0.03</td></tr><tr><td>机械力矩Tm/pu</td><td>0.85</td><td>0.85</td></tr><tr><td>线路参数R,L,C/pu</td><td>0.12.0.6,5.6</td><td>0.05,0.25,5.71</td></tr><tr><td>电压调节器传递函数</td><td>200/(1+0.15s)</td><td>200/(1+0.15s)</td></tr><tr><td>GAVR(s) 励磁系统传递函数GE(s)</td><td>1/(1+0.8s)</td><td>1/(1+0.8s)</td></tr><tr><td>励磁电压反馈传递函数 GF(s)</td><td>0.02s/(1+0.5s)</td><td>0.02s/(1+0.5s)</td></tr></table></body></html>

Tab.B3Parameters of grid-connected DFIG   

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>基准容量Sb,电压Ub,直流电压Ubdc</td><td>1.5MVA,690V,1150</td></tr><tr><td>直流电容Cdc</td><td>V 0.038pu</td></tr><tr><td>线路电感Lg,电阻Rg,串补电容Cg</td><td>0.45,0.05,10pu</td></tr><tr><td>直流电压环传递函数Hdc(s)</td><td>0.8+6/s</td></tr><tr><td>功率外环传递函数 HPQ(s)</td><td>5+30/s</td></tr><tr><td>电流环传递函数Hi(s)</td><td>2+15/s</td></tr><tr><td>锁相环传递函数GPLL(s)</td><td></td></tr><tr><td>电压前馈低通滤波器GFF(s)</td><td>(30+3200/s)/s</td></tr><tr><td>电机互感Lm</td><td>1/(1+0.002/s) 1.9pu</td></tr></table></body></html>

# 附录C

在小扰动下，电气谐振与相位振荡和幅值振荡存在如下关系。

根据表5相角振荡的表达式，可得其一阶线性近似表达式为

$$
\begin{array} { r l } & { Y _ { \mathrm { p } } = y _ { 0 } \mathrm { e } ^ { \mathrm { j } ( \omega _ { 0 } t + \varphi _ { 0 } ) } \mathrm { e } ^ { \mathrm { j } [ \frac { 1 } { 2 \mathrm { j } } y _ { \mathrm { R } } \mathrm { e } ^ { - \alpha t } \mathrm { e } ^ { \mathrm { j } ( \omega _ { \mathrm { R } } t + \varphi _ { R } ) } - \frac { 1 } { 2 \mathrm { j } } y _ { \mathrm { R } } \mathrm { e } ^ { - \alpha t } \mathrm { e } ^ { - \mathrm { j } ( \omega _ { \mathrm { R } } t + \varphi _ { \mathrm { R } } ) } ] } \iff } \\ & { \tilde { Y } _ { \mathrm { p } } = y _ { 0 } \mathrm { e } ^ { \mathrm { j } ( \omega _ { 0 } t + \varphi _ { 0 } ) } y _ { \mathrm { R } } \mathrm { e } ^ { - \alpha t } \frac { \mathrm { e } ^ { 0 } } { 2 } [ \mathrm { e } ^ { \mathrm { j } ( \omega _ { \mathrm { R } } t + \varphi _ { \mathrm { R } } ) } - \mathrm { e } ^ { - \mathrm { j } ( \omega _ { \mathrm { R } } t + \varphi _ { \mathrm { R } } ) } - 0 ] = } \\ & { \qquad \frac { 1 } { 2 } y _ { 0 } y _ { \mathrm { R } } \mathrm { e } ^ { - \alpha t } \{ \mathrm { e } ^ { \mathrm { j } [ ( \omega _ { 0 } + \omega _ { \mathrm { R } } ) t + \varphi _ { 0 } + \varphi _ { \mathrm { R } } ] } - \mathrm { e } ^ { \mathrm { j } [ ( \omega _ { 0 } - \omega _ { \mathrm { R } } ) t + \varphi _ { 0 } - \varphi _ { \mathrm { R } } ] } \} } \end{array}
$$

式中 $\tilde { Y } _ { \mathfrak { p } }$ 为 $X _ { \mathfrak { p } }$ 的一阶线性近似表达式。根据式(C1)，相角振荡空间矢量的分解如图C1中相角振荡所示。

![](images/56282ce17d4ea14be428d53c1f13b755aec640e259fc263cf0c5d1eb3d47bbda.jpg)  
图C1 电气振荡的合成

取初相为 $\scriptstyle { \pi / 2 }$ 时，表5中幅值振荡对应的表达式可转化为式(C2)，如图C1中的幅值振荡所示。

$$
Y _ { \mathrm { m } } = y _ { 0 } \mathrm { e } ^ { \mathrm { i } ( \omega _ { 0 } t + \varphi _ { \mathrm { 0 } } ) } + \frac { 1 } { 2 } y _ { \mathrm { 0 } } y _ { \mathrm { R } } \mathrm { e } ^ { - \alpha t } \{ \mathrm { e } ^ { \mathrm { i } [ ( \omega _ { \mathrm { 0 } } + \omega _ { \mathrm { R } } ) t + \varphi _ { \mathrm { 0 } } + \varphi _ { \mathrm { R } } ] } + 
$$

$$
\mathbf { e } ^ { \mathrm { j } [ ( \omega _ { 0 } - \omega _ { \mathrm { R } } ) t + \varphi _ { 0 } - \varphi _ { \mathrm { R } } ] } \}
$$

将二者叠加，可得到电气谐振表达式，即：

$$
\begin{array} { r l } & { Y _ { \mathrm { c } } = y _ { 0 } \mathrm { e } ^ { \mathrm { j } ( \omega _ { 0 } t + \varphi _ { 0 } ) } + y _ { 0 } y _ { \mathrm { R } } \mathrm { e } ^ { - \alpha t } \mathrm { e } ^ { \mathrm { j } [ \left( \omega _ { 0 } + \omega _ { \mathrm { R } } \right) t + \varphi _ { 0 } + \varphi _ { \mathrm { R } } ] } = } \\ & { \qquad [ 1 + y _ { \mathrm { R } } \mathrm { e } ^ { - \alpha t } \mathrm { e } ^ { \mathrm { j } ( \omega _ { \mathrm { R } } t + \varphi _ { \mathrm { R } } ) } ] y _ { 0 } \mathrm { e } ^ { \mathrm { j } ( \omega _ { 0 } t + \varphi _ { 0 } ) } } \end{array}
$$

根据式(C3)可知，电气谐振有以下2个特征：

1）是电气矢量整体发生振荡，在极坐标下可以分解为幅值振荡和相位振荡的叠加，在静止坐标系下则为工频信号叠加幅值为 $y _ { 0 } y _ { \mathrm { { R } } } \mathbf { e } ^ { - \alpha t }$ ，频率为 $( \omega _ { \mathrm { 0 } } + \omega _ { \mathrm { R } } )$ 或 $( \omega _ { \mathrm { 0 } } - \omega _ { \mathrm { R } } )$ 的非工频分量形成的振荡；

2）按照极坐标分解为幅值和相角振荡时，幅值振荡分量超前相角振荡分量 $\pi / 2$ ，且二者振幅相等;

![](images/e2b076b727c274a1d9f1b5b1b568a1616f5ec411c471271fa292549560579cec.jpg)  
Fig.C1Synthesis of equal amplitude-phase vector oscillations   
宫泽旭

在线出版日期：2021-08-06。  
收稿日期：2022-02-07。

作者简介：

宫泽旭(1996)，男，博士研究生，研究方向为新能源电力系统稳定性分析和控制，gongzexu@zju.edu.cn;

艾力西尔·亚尔买买提(1996)，男，硕士研究生，研究方向为新能源电力系统稳定性分析和控制， $2 2 0 1 0 1 2 4 @$ zju.edu.cn ;

\*通信作者：辛焕海(1981)，男，教授，博士生导师，主要研究方向为新能源电力系统稳定性分析与控制、新能源并网和微电网技术等，xinhh@zju.edu.cn。

(责任编辑 乔宝榆 李新洁)