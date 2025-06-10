# 同步发电机励磁系统状态在线测辨技术研究综述

乔冠伦」　李福兴² 李梧桐 沈小军1（1.同济大学电气工程系上海2018042.国家电网上海市电力公司电力科学研究院上海200437）

![](images/bbeac0187f7052e5137b15708b2004cfb0561b9340bbf44ba113738e05dd871b.jpg)

乔冠伦男 1992年生，硕士研究生，研究方向为励磁系统状态评估技术。

摘要：本文将励磁系统参数在线测辨分为信息实时获取、参数在线辨识和性能在线评估三个环节，分析了上述各环节的特征，探讨了励磁系统参数在线测辨技术的发展方向。结果表明，励磁系统信息实时获取环节在测量时间同步性和空间广泛性等方面均有大幅提升，以智能组件为代表的新型在线监测技术及其应用基础理论有待进一步研究；基于电网扰动的系统参数辨识具有较强的非线性环节参数辨识和噪声抑制能力，虽可满足当前系统参数在线辨识需求，若需进一步提升在线辨识的精度还需开展新的辨识算法和分类辨识策略研究；现有的励磁系统性能评估理论体系主要侧重于合格化对标，支持系统性能分级评估的应用基础理论研究有待开展。

关键词：同步发电机 励磁系统 在线测辨 性能评估 中图分类号：TM341

![](images/ba0f67ef5978496c46a3d38b10a597d9568a3881a085d179c2efa7ffe23190d1.jpg)

# Overview on On-Line Status Identification Technology of Synchronous Generator Excitation System

Qiao Guanlun'Li Fuxing² Li Wutong1Shen Xiaojun' (1.Department of Electrical Engineering Tongji UniversityShanghai201804 China 2.State Grid Shanghai Electric Power Research InstituteShanghai200437 China）

李福兴男 1963年生，高级工程师，从事网源协调、设备评价、诊断技术方面的研究。

Abstract: In the paper, on-line measurement and identification of excitation system parameter is divided into three sections: real-time information acquisition,on-line parameter identification and on-line performance evaluation. The research situationis reviewed,and the related theories and key technologies of on-line measurement and identification of excitation system parameter are discussed and analyzed.The results show that the real-time information acquisition section has great improvement on measurement time synchronization and spatial extensibility, new on-line monitoring technology such as intelligent electronic device and the basic theory of its application needs further study. For on-line parameter identification of the excitation system,the parameter identification based on disturbance of the grid has strong nonlinear parameter identification and noise suppression capability and meets the current system on-line identification needs, it is necessary to carry out research on new identification algorithm and classification identification strategy to be further enhanced. The existing theoretical system of excitation system performance evaluation mainly focuses on the qualitative benchmarking,and research on excitation system performance classification evaluation needs to be developed.

Keywords: Synchronous generator, excitation system,on-line measurement and dentification, performance evaluation

# 1 引言

励磁系统模型参数设置的精确性直接关系到电力系统稳定计算的准确性与可信度[1]。当前，电网调度部门采用的励磁系统模型参数一般通过励磁系统离线测试确定。理论分析发现，离线测辨因试验条件与实际工况存在差异，无法真实反映系统元件之间的相互响应和发电机实际运行状况，存在等效性和时效性较低等问题[2]，而在线测辨可直接计及发电机运行工况及所处环境等因素的综合作用，参数辨识值更接近励磁系统的实际参数值，便于电网调度部门及时掌握励磁系统的运行状态，是当前该领域研究的热点和难点[3]

同步发电机励磁系统模型参数在线测辨可划分为三个环节[4-6]：首先是励磁系统实时信息获取环节，主要实现励磁系统状态表征数据的在线监测；其次是对各励磁系统参数进行在线辨识，该环节将在线测量的励磁系统数据输入系统模型进行参数辨识；最后是励磁系统性能在线评估环节，即通过动态仿真模型和实际励磁系统的行为特征对比分析，实现励磁系统性能的综合评估。本文回顾上述三个环节的研究现状，并对未来的研究方向进行了分析讨论。

# 2 励磁系统信息实时获取环节研究现状

# 2.1传统在线监测技术

目前在我国大量应用的电力系统监测手段主要包括对系统稳态运行监视控制的能量管理系统（Supervisory Control and Data Acquisition/EnergyMeasurementSystem，SCADA/EMS）和记录系统暂态过程的各种故障录波仪（DigitalFaultRecorder,DFR)。

基于监视控制与数据采集的能量管理系统(SCADA/EMS）可采集电力系统在稳态或准稳态运行情况下的电压/电流有效值、有功功率/无功功率等运行量，并在局域网层次内上传到调度信息中心，主要包括系统状态估计、网络拓扑分析、静态安全分析等一系列功能[7。该监测手段成功解决了离线数据中稳态数据与实际系统存在差异的问题，并且保留了大部分的离线分析应用手段，被广大电力系统生产部门所接受。但SCADA/EMS系统数据刷新时间较长，且无法描述动态系统在扰动情况下响应的暂态数据。

故障录波仪（DFR）可在电力系统或机组发生故障、振荡时自动记录装置安装点的各种信息[8：安装在网络节点中的DFR，记录包括节点电压、电流、有功功率、无功功率及系统频率在系统波动期间的整体变化过程；安装在发电机节点处的DFR，记录包括机端电压、机端电流、有功功率、无功功率、机组转速、励磁电压和励磁电流等相关数据在系统波动及机组故障期间的整体变化过程。故障录波仪主要包括采集模块和管理分析模块：采集模块主要完成录波数据的采集、分析计算、录波启动判别等；管理分析模块主要完成数据的记录、分析和管理，故障类型分析、故障定位和故障再现等功能，装置结构框图如图1所示[9]。

![](images/cf1cb62be27de4be30bd44ab617557695bb1382d6f7c126d23eaebec8aec6d7a.jpg)  
图1故障录波仪结构图  
Fig.1The diagram of digital fault recorder structure

值得注意的是，虽然SCADA/EMS和DFR在系统实时监测方面发展已较为成熟，但目前二者具有一个共同的不足，即对不同地点之间的数据缺乏准确的时间坐标，记录的数据只在局部有效，难以适应逐步扩大的电力系统动态行为分析[10]

# 2.2相量测量单元技术

基于全球定位系统（GlobalPosition System,GPS）的相量测量单元（Phase MeasurementUnit,PMU）为发电机等电网元件的在线监测提供了一个全新的数据来源和技术平台[1]。当电网发生扰动时，GPS/PMU监测装置能够利用GPS的授时功能和工频带通滤波器输出的交流信号，实时跟踪系统各单元的频率信息。采样脉冲发生器将脉冲分成一系列的脉冲序列，该序列能够触发转换器进行模-数转换。微处理器根据傅里叶变换原理计算出各单元相量值，并以相量形式提供发电机系统的动态同步相量数据，包括机端电压/电流相量、有功功率/无功功率、励磁电压电流、内电动势功角等信息，其结构原理如图2所示[12]。

![](images/bff5c4caef6b73104c6a7df932af3bcafcabe93e4188eee02c17f42c0f24a252.jpg)  
Fig.2The diagram of phase measurement unit structure

GPS/PMU监测装置与传统远程终端(RemoteTerminalUnit，RTU）测量所不同的是各个PMU的测量值可以将时标统一至同一个时间坐标上，便于直接获得各个状态量的有效值以及各个状态量之间的相位关系，具有同步率高、测量精度高、数据更新快等特点[13]。

随着电力系统测量对时间同步和空间广域等要求的逐步提高，基于PMU的广域测量系统（WideAreaMeasurementSystem，WAMS）应运而生。PMU/WAMS主要由位于厂站端的PMU、通信系统和位于调度中心的控制系统组成，根据电网中关键变电站的实时动态测量数据在线监视电网的运行状态，在系统电压、相角、频率出现异常时进行越限（静态、动态）报警，对系统的异常运行状态、特征信号和故障类型进行观测、辨识和分析，通过观测分析为电力系统稳定控制策略的制定提供技术依据。PMU/WAMS技术在数据实时监测和测量范围方面均有大幅提升，为实现全网发电机功角的在线测量和广域电力系统的分析控制奠定了坚实基础[13-15]

# 3励磁系统参数在线辨识环节研究现状

# 3.1人为扰动励磁系统参数在线辨识法

人为扰动激励下的参数在线辨识试验要求外部激励信号不能影响发电机的正常运行，且研究多集中在激励信号的设计、数据预处理、辨识算法、非线性特性的处理等环节[16]。目前，人为扰动下的参数在线辨识主要分为在线频域辨识法和在线时域辩识法。

在线频域法是典型的人为扰动激励下的在线频域辨识法，该方法是在机组运行时施加外部扰动信号，利用动态拟合法求取参数，辨识过程如图3所示。

![](images/9f0dd95b51b934e7cb1623c1ae9887f35efce04879e20d7052fc0cfd6f38926b.jpg)  
图2PMU结构框图  
图3励磁系统参数在线频域辨识流程  
Fig.3Flow chart of on-line frequency response identification for excitation system parameter

在线频域法工作流程分为两部分[17-18]：首先利用实时采样和快速傅里叶变换(FastFourierTransformation，FFT）将系统输入/输出信号转换为频域信号，并根据维纳－霍甫方程得到系统的频率特性（幅频特性及相频特性）；然后利用动态拟合法（最小二乘法、改进的Levy法、卡尔曼滤波法、极大似然法）从频率响应曲线中求取模型参数。现场测试结果表明：各环节的实测相频、幅频特性与求得参数拟合后的曲线基本吻合，均方误差小于$5 \%$ ，满足参数误差要求，测试方法正确可信。该方法已成功运用于大型汽轮发电机组和水轮发电机组励磁系统参数的在线辨识。

在线时域辨识法首先对实际系统的输入/输出序列进行积分、滤波及正交变换等相关运算处理；然后建立差分方程，以具体参数为辨识对象，通过各类直接辨识法，如时域最小二乘法、状态滤波法、矩形脉冲函数（BPF）法、分段线性多项式函数（PLPF）法，得到具有物理意义的特性参数，再由输入的动态激励信号和差分方程得出辩识对象的输出响应，并比较系统实际输出响应与模型计算输出响应的差异，判断差分方程模型的优劣；最后将差分方程模型转换为系统需要的数学模型，如传递函数模型、状态空间模型，其参数辨识流程如图4所示[19]。电力系统的科研和工程技术人员习惯于在计算和分析中应用具有明确物理意义的参数，从辨识方法的操作过程看，参数在线时域辨识法更简便，在发电机励磁系统参数辨识中应用更为广泛。

![](images/b0594d4bcc137d34ed37475d08d1f179ec9d28c2d6cc7eb6c8921f356b453912.jpg)  
图4励磁系统参数在线时域辨识流程Fig.4Flow chart of on-line time domain identification ofexcitation system parameters

人为扰动下的参数在线频域辨识法和时域辨识法原理清晰，方便易行，在实际励磁系统参数在线辨识中得到了广泛运用。分析结果表明，在线频域辨识法是建立在FFT基础上，它的泄漏、混叠、栅栏效应易造成较大误差，而采用时域直接分析的辩识方法进行参数辩识建模，具有精度高、速度快等优点。二者的不足之处在于无法有效解决励磁系统高阶非线性环节参数辨识和噪声抑制等问题。

# 3.2电网扰动励磁系统参数在线辨识法

相较于人为施加激励的参数在线辨识，利用电网扰动激励下励磁系统的动态过程数据进行参数辨识无需任何试验，只需借助有效的测量设备记录励磁系统的动态过程即可[20-21]。因此，基于电网扰动激励的参数在线辨识具有较高的研究价值和工程应用价值，受到了广大学者的普遍关注。

先进智能的辨识算法是电网扰动励磁系统参数在线辨识的基础，基于电网扰动的励磁系统参数辨识算法主要有遗传算法（GeneticAlgorithm，GA）和神经网络观测法。其中，GA直接利用系统自然扰动进行参数辨识：首先建立励磁系统原模型和标准模型的传递函数与各非线性环节结构框图；然后给励磁系统标准模型中各待辨识参数进行编码，包括非线性环节参数的编码；再通过GA的不断优化，最终得到励磁系统标准模型的最优参数，其参数辨识流程如图5所 [22-23]

![](images/c48a1d5d98e7f93b41d94c3b64bc7937dcff8a4e4dbb2089f4f7a626a42b954c.jpg)  
图5基于遗传算法的励磁系统参数在线辨识流程 Fig.5On-line identification of excitation system parameters based on genetic algorithm

GA辨识法充分考虑了励磁系统的非线性特性，可以很好地解决励磁系统非线性环节的参数辨识问题。同时，GA是一种并行算法，能够对数据空间进行全局搜索，并能以很大的概率找到全局最优解，便于励磁系统参数辨识。

神经网络观测法不需要过多人为干预，直接针对发电机参数非线性特征，利用神经网络对复杂非线性参数的模拟，可以很好地追踪发电机参数的变化；并且神经网络具有自学习、自适应功能，能够不断地在励磁系统实际运行中得到训练，并在线观测同步发电机励磁系统动态特性[24-25]。

# 4励磁系统性能在线评估环节研究现状

相关研究表明，发电机励磁系统调节特性与电力系统的稳态特性和暂态特性直接相关。对于励磁调节系统，增大增益、减小时间常数可提高发电机电压调节精度、减小发电机组的动态过电压、增强电力系统的电压稳定和静态稳定；较高的强励倍数可提高电力系统的暂态稳定[26]。励磁系统调节性能的准确评估对于电力系统的安全运行具有重要意义。

励磁系统的调节性能指标可分为大干扰动态性能指标和小干扰动态性能指标。大干扰动态性能指标是指扰动信号大到使调节达到限定幅值时的性能指标，即励磁系统限制器的动态性能指标；小干扰动态性能指标是指扰动信号很小时励磁调节在线性区间的性能指标，包括低频振荡下的动态阻尼特性、负载阶跃响应特性和闭环特性等性能指标。其中，励磁系统限制器动态性能评估和励磁系统动态阻尼性能评估理论发展相对成熟，相关评估涵盖了励磁系统稳定性和快速性的主要性能指标[27]，具体如下：

(1）同步发电机励磁控制器作为电力系统中最重要的自动控制装置之一，主要由基本控制、辅助控制和限制系统三部分组成。限制系统主要在励磁控制器异常运行情况下，提供必要的励磁限制信号，并封锁基本控制信号和辅助控制信号以保证机组的稳定和安全运行，其工作性能直接影响到励磁系统和发电机的安全稳定运行。研究人员针对当前励磁限制系统中过励限制器参数配置合理性等问题，提出了一种基于电压影响因子的过励限制功能的分析方法[28]。该方法可以在系统发生短路故障之后，通过定量表征励磁系统的强励能力，准确分析定子过流限制器与励磁过流限制器的动作协调性，避免因励磁系统过励限制器的误动作抑制励磁系统的强励能力，提升了过励限制器参数整定与性能评估的准确性。

(2）同步发电机阻尼绕组是系统阻尼的一个重要组成部分，系统阻尼不足容易引发系统振荡，严重危及系统稳定，因此，励磁系统动态阻尼性能在线评估是励磁系统性能评估的重点研究内容。目前，相关研究基于实测数据对励磁电流振荡分量和机组转速（频率）振荡分量进行了相关性分析，提出了一种机组振荡过程中励磁系统 (主控制、附加控制)整体阻尼特性的计算方法[29]。该方法不依赖于励磁系统及其控制参数的准确性，能够检验励磁系统及其控制参数的合理性，并为负阻尼低频振荡源的定位分析和控制提供可靠参考。

某种意义上，励磁系统性能评估已涉及部件级评估。但该技术仍处于初期研究阶段，为准确评估各部件的调节性能，相关特性分析方法与性能指标的研究工作仍有待开展。

# 5 研究方向探讨

由上可知，国内外在励磁系统信息实时获取技术、励磁系统参数在线辨识方法和励磁系统各部件性能评估等环节均已开展了大量的研究工作，并取得了丰富的研究成果，为励磁系统性能的评价以及电网安全稳定运行发挥了巨大作用。随着波动性新能源的大量接入和电网规模的日益扩大，电力系统运行工况日益复杂，更精确地获取励磁系统性能参数及状态的需求日益迫切[30-31]，继续优化完善现有励磁系统状态在线测辨技术仍具有重要的工程价值和现实意义。同时，本文认为以下几个方面也应得到重视。

# 5.1励磁系统智能组件技术

所谓励磁系统智能组件是指一种基于GPS或北斗时间系统的智能电子设备（IntelligentElectronicDevice，IED)，可实时获取、记录并对外提供包括励磁变状态、发电机组状态、调节器状态、功率单元状态及发电机励磁系统状态的实时数据和历史数据，励磁系统智能组件架构如图6所示。

理论上，励磁系统智能组件技术可实时记录励磁系统各组成环节的动态信息数据，为系统各模块参数的精细化辨识与分析提供基础数据；可监测机组扰动及其励磁系统响应过程，为励磁系统动态和静态性能指标的计算与分析提供数据支持，实现励磁系统调节性能的准确评估。另外，励磁系统智能组件技术还可为机网协调优化提供全面的励磁系统动态基础数据，对电网运行方式稳定性分析、系统仿真模型校验等同样具有重要的价值[32-33]。

励磁系统信息实时获取环节中，励磁系统智能组件技术是一种新的思路，其应用基础理论和关键技术值得关注。

# 5.2励磁系统部件级特征参数在线辨识

电网扰动下的参数在线辨识有效地解决了高阶非线性环节参数辨识和噪声信号抑制等问题，具有方法简单、无需人为施加干扰信号的优点。但是，当前电网扰动励磁系统参数辨识研究成果侧重于励磁系统参数的整体辨识，通过在线获取机组扰动过程曲线及其励磁系统的动态响应曲线对励磁系统进行整体参数辨识。研究表明，励磁系统的整体特性较为复杂，利用该方法得到的参数辨识结果不确定性较强；另外，该方法以系统整体特性作为研究对象，无法为电网调度提供更多有关励磁系统内部运行的参数辨识结果，存在参数辨识结果不唯一、参数结果难以准确反映系统各部件性能等不足[34-35]

![](images/e4c7a54740d009ce3f5cd50b217e2febc19693b1506c5fe78ec222844158822f.jpg)  
图6励磁系统智能组件架构图  
Fig.6The diagram of excitation system intelligent electronic device structure

独立辨识励磁系统各模块参数可通过励磁系统分析与解耦，对各部件参数进行独立辨识。该方法基于各部件调节特性，利用不同的参数辨识算法有针对性地辨识系统参数，有利于提升参数辨识精度和辨识结果的唯一性，可为励磁系统各部件工作状态的实时、独立评估提供更加准确的数据支持。

当前，基于电网扰动的励磁系统各模块参数独立辨识的相关工作还鲜有开展。为实现系统各部件参数的独立辨识，首先需要提出新技术和新辨识算法对励磁系统进行解耦与参数筛选，以对励磁系统各模块参数进行快速、准确辨识[36]。另外，该辨识方法对信号获取技术也具有较高要求，相比于传统辨识方法在线监测发电机机端动态信息数据，该方法还需要在励磁系统内部设置多个测量点，通过在线获取励磁限制器、电压调节器和电力系统稳定器等部件的实时信息数据，准确辨识励磁系统各部件参数。

# 5.3励磁系统性能分级评估

励磁系统性能评估受到多方面因素影响，仅给出励磁系统等效动态性能是否合格已不能完全满足电力系统安全运行稳定运行和日益精准化的评估需求。以励磁系统动态阻尼性能评估为例，仅以阻尼系数是否达标无法具体判断励磁系统的阻尼性能，不同的达标参数值对于同一个励磁系统在稳定性和快速性等方面有不同的性能表现。因此，需要引入更多表征性能优劣的指标体系，为评价不同运行工况下的励磁系统调节性能提供更加准确的评估依据。另外，励磁系统各部件的调节性能对于系统整体调节具有不同程度的影响，然而，现有的励磁系统性能评价体系只适用于判断系统各部件参数是否在误差范围内，无法准确评估各部件的达标参数对于系统整体性能的优化程度[37-38]。

为适应日益复杂的电力系统运行工况和不同目标下的系统性能评估需求，研究者认为应建立励磁系统各部件的分级评价体系。首先以励磁系统各部件为研究对象，将各部件性能评估的关键因素分层排布，依据各因素在励磁系统性能中所起的作用和重要程度不同，确立各个因素的权重；然后根据评估需求将励磁系统各部件的性能分为多个等级，如优秀、良好、合格、不合格、差；再利用系统各部件的分级评价体系量化描述各部件的调节性能，得到各部件的准确评估结果；最后进行系统部件性能与系统整体性能的相关性分析，通过分析系统各部件调节性能对于系统整体性能的优化程度，确立系统整体的评估结果处于何种水平。

构建励磁系统各部件的性能分级评价体系可以更加准确评判励磁系统的工作状态，为指导励磁系统参数优化和电力系统运行方式的风险评估提供更加完善的依据。

# 6 结束语

同步发电机励磁系统参数在线测辨主要包括励磁系统的信息实时获取、参数在线辨识、性能在线评估三个环节。智能组件技术为励磁系统信息监测提供了新的思路，但该技术尚处于初级阶段，其应用基础理论和关键技术有待深入研究。基于电网扰动的参数在线辨识可有效解决非线性坏节参数辨识和噪声抑制等问题，但在系统功能部件解耦与参数筛选方面仍有待研究；另外，励磁系统性能在线评估研究应建立性能分级评估体系以适应日益复杂的电力系统运行工况和不同目标下的系统性能评估需求。

# 参考文献

[1] 刘取，刘宪林．21世纪电力系统的先进技术[J]. 电力自动化设备，2010，30(7)：1-14. Liu Qu,Liu Xianlin.Advanced technologies of power system in the 2lst century[J].Electric Power Automation Equipment, 2010,30(7):1-14.   
[2] 贺仁睦，沈峰，韩冬，等．发电机励磁系统建模 与参数辨识综述[J]．电网技术，2007，31(14)： 62-67. He Renmu, Shen Feng,Han Dong,et al. The study of generator excitation system modeling and parameters estimation[J].Power System Technology,2007, 31(14): 62-67.   
[3] 陆进军，戴则梅，张力，等．基于广域测量系统 的电网扰动在线监视和评估[J]．电力系统自动化, 2012，36(8): 82-86. Lu Jinjun,Dai Zemei,Zhang Li,et al. On-line power system disturbance monitoring and evaluation method based on WAMS[J].Automation of Electric Power Systems,2012,36(8): 82-86.   
[4] Karrari M,Malik O P.Identification of physical parameters of a synchronous generator from online measurements[J]. IEEE Transactions on Energy Conversion,2004,19(2): 407-415.   
[5] 郭磊，鞠平，王红印，等．电力系统多台发电 机参数的整体辨识[J]．电力系统自动化，2011, 35(17): 44-50. Guo Lei, Ju Ping,Wang Hongyin, et al. System wide parameter identification of multi-generators in power system[J].Automation of Electric Power Systems, 2011, 35(17): 44-50.   
[6] Wang Jianqiang,Zhang Hongyu. Multicriteria decision-making approach based on Atanassov's intuitionistic fuzzy sets with incomplete certain information on weights[J]. IEEE Transactions on Fuzzy Systems,2013,21(3): 510-515.   
[7] 陈屹东，程浩忠，栾伟杰，等．发电机组涉网参 数的在线评估方法[J]．华东电力，2013，41(4)： 789-793. Chen Yidong, Cheng Haozhong, Luan Weijie, et al. Online evaluation of generator grid-related parameters[J]. East China Electric Power, 2013, 41(4): 789-793.   
[8] 林济铿，张闻博，武乃虎，等．基于故障录波 器的机组参数辨识[J]．电力自动化设备，2012, 32(8): 27-34. Lin Jikeng,Zhang Wenbo,Wu Naihu,et al. Generation system parameter identification based on DFR[J]. Electric Power Automation Equipment, 2012,32(8): 27-34.   
[9] Ma Jin, Han Dong, He Renmu, et al. Reducing identified parameters of measurement-based composite load model[J]. IEEE Transactions on Power Systems,2008,23(1): 76-83.   
[10]Saavedra-Montes A J, Ramirez-Scarpetta J M, Malik O P. Methodology to estimate parameters of an excitation system based on experimental conditions[J]. Electric Power Systems Research, 2011, 81(1): 170-176.   
[11]程云峰，张欣然，陆超．广域测量技术在电力系 统中的应用研究进展[J]．电力系统保护与控制, 2014，42(4): 145-153. Cheng Yunfeng, Zhang Xinran,Lu Chao.Research progress of the application of wide area measurement technology in power system[J]. Power System Protection and Control,2014,42(4): 145-153.   
[12]薛禹胜，徐伟，万秋兰，等．关于广域测量系统 及广域控制保护系统的评述[J]．电力系统自动化, 2007， 31(15): 1-6. Xue Yusheng, Xu Wei, Wan Qiulan, et al. A review of wide area measurement system and wide area control system[J]. Automation of Electric Power Systems, 2007, 31(15): 1-6.   
[13]Bi T, Xue A, Xu G,et al. On-line parameter identification for excitation system based on PMU data[C]. IEEE Fourth International Conference on Critical Infrastructures,2009: 1-4.   
[14]许树楷，谢小荣，辛耀中．基于同步相量测量技 术的广域测量系统应用现状及发展前景[J]．电网 技术，2005，29(2)：44-49. Xu Shukai, Xie Xiaorong, Xin Yaozhong. Present application situation and development tendency of synchronous phasor measurement technology based wide area measurement system[J]. Power System Technology,2005,29(2): 44-49.   
[15]Defu N,Bing Y, Weimin Z,et al. A new algorithm for power system state estimation with PMU measurements[C]. 2011 International Conference on Mechatronic Science, Electric Engineering and Computer(MEC), Jilin, 2011: 114-117.   
[16]李志强，汤涌，何凤军，等．基于时频变换的同 步发电机参数辨识方法[J]．中国电机工程学报, 2014，34(19):3202-3209. Li Zhiqiang, Tang Yong, He Fengjun, et al. A timefrequency transform based identification method for synchronous generator parameters[J]. Proceedings of the CSEE,2014,34(19): 3202-3209.   
[17]鞠平，郭磊，高昌培，等．频域灵敏度及其在电 力系统参数辨识中的应用[J]．中国电机工程学报, 2010，30(28):19-24. Ju Ping,Guo Lei, Gao Changpei, et al. Frequencydomain sensitivities with application to power system modeling[J]. Proceedings of the CSEE,2010, 30(28): 19-24.   
[18]Belega D, Dallet D. Frequency estimation via weighted multipoint interpolated DFT[J]. IET Science, Measurement & Technology, 2008, 2(1): 1-8.   
[19] 曹浩军，张承学，单勇．基于连续时间方法的励 磁参数辨识[J]．电力系统自动化，2004，28(17): 49-54. Cao Haojun, Zhang Chengxue, Shan Yong. Identification of excitation system parameters based on continuous-time approaches[J]. Automation of Electric Power Systems,2004,28(17): 49-54.   
[20]沈峰，贺仁睦，谢永红．基于实测扰动的励磁 系统参数辨识可行性研究[J]．电网技术，2008, 32(10): 69-73. Shen Feng, He Renmu, Xie Yonghong. Study on feasibility of excitation system parameter identification based on actual measurement of disturbance[J]. Power System Technology, 2008, 32(10): 69-73.   
[21]Xue A,Cao Z, Bi T, et al. On-line excitation systems’ parameters identification based on inputoutput system and hybrid algorithm with PMU[C]. IPEC,2010 Conference Proceedings, IEEE, 2010: 544-548.   
[22]王兴贵，王言徐，智勇．遗传算法在发电机励磁 系统参数辨识中的应用[J]．电力系统及其自动化 学报，2010，22(1)：76-79. Wang Xinggui, Wang Yanxu, Zhi Yong. Application of genetic algorithm in generator excitation system parameters identification[J]. Proceedings of the CSUEPSA,2010,22(1): 76-79.   
[23]Dionysios C Aliprantis, Scott D Sudhoff, et al. Genetic algorithm-based parameter identification of a hysteretic brushless exciter model[J]. IEEE Transactions on Energy Conversion, 2006, 21(1): 148-154.   
[24]Pham D V. Online handwriting recognition using multi convolution neural networks,simulated evolution and learning[J]. Lecture Notes in Computer Science,2012,7673: 310-319.   
[25] Wu Shiqian,Er Meng Joo.Dynamic fuzzy neural networks-a novel approach to function approximation[J]. IEEE Transactions on Systems, Man,and Cybernetics,2000, 30(2): 358-364.   
[26]丁志东，刘国海．同步发电机励磁对稳定性影响 的研究[J]．大电机技术，2007，4(4)：60-64. Ding Zhidong,Liu Guohai. Research of influence of synchronous generator excitation on power system stability[J]. Generator Technology,2007,4(4): 60-64.   
[27]穆永铮，鲁宗相，乔颖，等．基于多算子层次分析 模糊评价的电网安全与效益综合评价指标体系[J]. 电网技术，2015，39(1)：23-28. Mu Yongzheng, Lu Zongxiang, Qiao Ying, et al. A comprehensive evaluation index system of power grid security and benefit based on multi-operator fuzzy hierarchy evaluation method[J]. Power System Technology,2015,39(1): 23-28.   
[28]竺士章，陈新琪．励磁系统的过励限制和过励保 护[J]．电力系统自动化，2010，34(5)：112-115. Zhu Shizhang,Chen Xinqi. Over-excitation limiter and protection of the excitation systems[J]. Automation of Electric Power Systems, 2010,34(5): 112-115.   
[29]王茂海，郭登峰，江长明，等．低频振荡过程中 励磁系统阻尼特性分析方法[J]．电力系统自动化, 2013，37(4): 47-68. Wang Maohai, Guo Dengfeng, Jiang Changming, et al. An analysis method to evaluate damping characteristics of excitation systems in low frequency Oscillation process[J]. Automation of Electric Power Systems,2013,37(4): 47-68.   
[30]汪海瑛，白晓民，马纲．并网光伏电站的发电可 靠性评估[J]．电网技术，2012，36(10)：1-5. Wang Haiying,Bai Xiaomin,Ma Gang.Reliability assessment of grid-integrated solar photovoltaic system[J]. Power System Technology, 2012,36(10): 1-5.   
[31]赵俊博，张葛祥，黄彦全．含新能源电力系统状态 估计研究现状和展望[J]．电力自动化设备，2014, 34(5): 7-20. Zhao Junbo, Zhang Gexiang, Huang Yanquan. Status and prospect of state estimation for power system containing renewable energy[J]. Electric Power Automation Equipment, 2014, 34(5): 7-20.   
[32]张斌，倪益民，马晓军，等．变电站综合智能组件 探讨[J]．电力系统自动化，2010，34(21)：91-94. Zhang Bin,Ni Yimin,Ma Xiaojun, et al.A study on integrated intelligent components for smart substation[J]. Automation of Electric Power Systems, 2013,34(21): 91-94.   
[33]刘有为，肖燕，许渊．智能高压设备技术策略分析 [J]．电网技术，2010，34(12)：11-16. Liu Youwei, Xiao Yan,Xu Yuan. Analysis on technical strategies for smart high voltage equipment[J]. Power System Technology, 2010, 34(12): 11-16.   
[34]张虹，徐滨，高健，等．基于最小方差基准的励 磁系统性能评估[J]．电力系统保护与控制，2014, 42(8): 135-140. Zhang Hong,Xu Bin,Gao Jian, et al. Performance assessment of excitation system based on minimum variance benchmark[J]. Power System Protection and Control, 2014, 42(8): 135-140.   
[35]王波，陆进军．基于同步相量测量技术的励磁系 统调节性能分析方法及其系统实现[J]．电力系统 保护与控制，2012，40(3)：54-58. Wang Bo,Lu Jinjun.A method for analyzing the regulating performance of excitation system based on synchronized phasor measurement technology and its system realization[J]. Power System Protection and Control,2012, 40(3): 54-58.   
[36]邱健，周孝信，于海承，等．基于电网动态特性 的发电机主导参数辨识方法[J]．中国电机工程学 报，2016，36(14):3699-3706. Qiu Jian,Zhou Xiaoxin, Yu Haicheng,et al.A methodology for generator dominant parameter identification based on dynamic characteristics of power grid[J]. Proceedings of the CSEE,2016, 36(14): 3699-3706.   
[37]Xu Zeshui. Intuitionistic fuzzy multi attribute decision making an interactive method[J]. IEEE Transactions on Fuzzy Systems,2012,20(3): 514- 525.   
[38]傅磊，卢力东，刘甲林，等．一种发电机励磁系 统性能的模糊综合评估算法[J]．电机与控制应用, 2016，43(2): 25-29. Fu Lei, Lu Lidong,Liu Jialin,et al.A kind of method based on fuzzy comprehensive evaluation algorithm for performance of generator excitation system[J]. Electric Machines & Control Application,2016, 43(2): 25-29.