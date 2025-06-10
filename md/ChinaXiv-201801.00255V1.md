# 关于穿戴式人体传感器网络的研究思考 \*

![](images/b76522af7ff979109337904b614cfdefb8f925f4e7b55f993f915dc9e668088d.jpg)

韩世鹏 Olatunji Mumini Omisore 王 磊\*\*中国科学院深圳先进技术研究院深圳518055

摘要人体健康信息的监测、获取、处理是衡量个人健康状态最直接的方法，也是有效预防疾病威胁的重要手段。穿戴式人体传感器网络技术，可实现健康全过程的跟踪与智能服务，对人体信息的动态监测和疾病预防具有重大意义。文章在分析穿戴式人体传感器的前景和研究现状基础上，提出了解决穿戴式人体传感器网络核心技术的策略方法，并给出了基于人体传感器网络技术的穿戴式医疗设备中与“人-机-环境”有关的两个关键问题。

关键词人体健康，智能服务，穿戴式，人体传感器网络

DOI 10.16418/j.issn.1000-3045.2017.12.006

穿戴式人体传感器网络（wearable body sensor network，WBSN）是涉及可穿戴、微机电、生物医学电子等多学科的交叉技术。作为近年来移动互联网的热点发展方向之一，WBSN具有便携化、无线化、网络化、信息化等诸多优势。基于人体传感器网络的穿戴式医疗设备可实现健康全过程的跟踪与服务；采用医学智能技术对人体健康信息进行智能处理，对于预防人体疾病具有重要的意义。智慧医疗、移动医疗、远程医疗、家庭医疗、社区公益医疗都在催促着医疗市场快速发展，穿戴式人体传感器网络技术作为突破医疗健康检测设备和人体健康信息监测的攻坚技术，具有很大的研究价值和医疗需求。

\*资助项目：国家自然科学基金项目（U1505251），中科院重点部署项目（KFZD-SW-2 14)  
\*\*通讯作者  
修改稿收到日期：2017年11月30日

# 1前景分析

人体传感器网络及医疗健康服务应用是穿戴式设备的发展趋势之一，WBSN主要涉及生理参数检测、运动数据统计及健康状况改善等方面的设备和技术。据英国市场研究机构朱尼普研究公司（Juniper Research）最新报告，2014年全球大约有1900万个可穿戴设备在使用，预计到2018年，使用量将是2014年的3倍。据美国消费电子协会（CEA）和美国电子电气工程师协会（IEEE）报告，预计2022年，全球可穿戴设备的全年销售额将达到2800亿人民币，这主要得益于可穿戴医疗健康服务类产品的推动。据全球移动通信系统（GSM）对移动医疗行业的测算标准，预计2022年中国可穿戴设备市场销售额可达到600亿元人民币。针对可穿戴医疗健康服务的人体传感器网络技术服务呈现出3个特点。

（1）基础医疗电子产品市场竞争更加激烈。随着中国、印度、俄罗斯、巴西、墨西哥等新兴国家经济的起飞，医疗技术的发展使医疗电子设备的主要功能从诊断治疗转向保健，并逐渐向基层普及。这些新兴市场需要更加实用的医疗器械新产品一一从最普通的电子测步表、电子血压表、电子血糖仪、电子按摩仪、电子疼痛治疗仪到价格相对较高的家用制氧机等大众医疗电子产品[1]。随着国际医疗电子巨头在高端市场不断收紧并向相对低端的基础市场延伸，以及我国医疗电子设备研发技术水平的提升，在上述领域国内外企业的市场竞争将更加激烈。

（2）高端与低端医疗设备国产化进程继续加速推进。近年来，我国启动优秀国产设备产品的遴选工作,越来越多的医院开始使用国产医疗设备，这促进了我国医疗电子行业的发展。一批国内优秀的医疗电子企业，如迈瑞、上海联影、万东医疗、东软医疗、深圳理邦、深圳安科等迎来发展良机，在政府相关政策与财政支持下，必定会在未来几年将一批先进技术水平的医疗设备进行产业化。

（3）移动医疗等成为未来新型医疗模式。智慧医疗、移动医疗、远程医疗、家庭医疗和社区公益医疗是未来医疗行业发展的大趋势，它们将改变传统就医保健的方式，同时节省医疗资源，有效解决我国医疗管理系统不完善、医疗成本高、覆盖面窄等问题[2]。医疗电子产品的使用已不再局限于传统的专业医疗机构，家庭护理方面的应用需求正在急速扩张，而应用场合的转移对医疗电子产品的小型化、便携化提出了更高的要求。随着全社会信息化程度的提高，医疗电子向网络化、远程化、无线化方向发展。未来移动医疗将逐渐渗人市民生活，市民就医从挂号到治疗都会实现网络互连，这可大幅降低患者和医院的时间成本，提高诊治效率，确保医疗服务资源的最优整合和协同效应。

# 2研究现状

# 2.1现阶段研究热点

近年来，医疗健康服务发展如火如荼，尤其以穿戴式人体传感器网络技术为核心的柔性穿戴式医疗设备创制是一个极具挑战性的研究领域[3]，涉及“核心部件—柔性集成一医学智能一创新应用”等方面的研究工作，现阶段的研究热点主要包括：（1）生物检测方面，研发半导体纳米材料的高性能微纳传感器、可穿戴活性传感器、碳纳米材料超薄膜和具有仿生功能的电子皮肤、电子织物等核心器件4；（2）生化传感器方面，研发高结晶度、高纵横比的纳米纤维素生物膜基底的表皮生化传感器[5]，以及采用聚酰亚胺和硬质玻璃作为衬底基板，金和氧化锌作为传感电极，设计灵活可穿戴的汗液传感器，用来监测酒精浓度；（3）柔性集成方面，基于仿生微纳加工、低功耗集成电路（IC）设计与高密度封装技术，开发高可靠性的硬件系统；（4）人体数据通信方面，研究人体近端信息交互原理及信息安全理论，实现高能效人体近端通信；（5）健康状态辨识方面，研究适用于穿戴式生命健康数据集的机器学习方法，以及与生物信息大数据的融合技术[8]；（6）系统供能方面，研究纳米发电机、柔性光能材料和基于温度梯度的能量搜集方法，开发原理样机；（7）医疗健康应用方面，探索穿戴式医疗设备与时尚、创新设计的融合，行业、团体标准及商业模式的设立，以及柔性可穿戴医疗康复机器人等新应用[]

# 2.2国内外研究进展

（1）生理和生化检测方面。Ryu等[1°]通过干纺方法制备了高度取向性的碳纳米管纤维弹性应力传感器。Yugandhar等[]对于压电微机电系统（Micro-Electro-Mechanical System，MEMS）建立了仿真模型。

Yamada等[12]制备了定向排列的单壁碳纳米管薄膜，拉伸时碳纳米管破裂成岛-桥-间隙结构，其形变可以达到 $2 8 0 \%$ 。Tee 等和Lipomi[13,14]利用具有锥状微结构的压阻传感器制备了可以向大脑传递触觉信息的电子皮肤和在弹性基底上制备了电容型透明可拉伸的碳纳米管传感器，其对压力和拉力同时有响应。Chae 等[15]制备了可以高度拉伸的透明场效应晶体管，其结合了石墨烯/单壁碳纳米管电极和具有褶皱的无机介电层碳纳米管网格通道。Gong等开发了实用的高灵敏压阻传感器，在弹性基底上构筑了金纳米线薄层和电极阵列。Liao 等[7]研制了柔性可穿戴的葡萄糖传感器。Bae等[18研制了双层PDMS复合结构，增强了吸附力。

笔者团队依托中科院重点部署项目，针对下一代可穿戴医疗健康服务的共性与关键技术，利用酶电极、纳米技术和柔性微机电系统构建可穿戴式汗液传感器，检测汗液中葡萄糖、乳酸、尿酸、氨基酸和各种离子（如钠、钾、钙、氯离子）等多种健康状态辨识指标，建立与人体健康相关指标的联系。汗液传感器采用葡萄糖、乳酸、尿酸氧化酶的定向进化及纳米组装体设计，提高葡萄糖、乳酸、尿酸电化学检测的灵敏度和稳定性；发展基因密码子扩展方法，设计筛选对特定生化分子具有特异性的氧化还原酶，通过将氧化还原酶定点特异偶联到图案化高密度金和石墨电极，实现生化信号到电信号的高效转化，提高生物电化学传感系统的灵敏度和稳定性；葡萄糖、乳酸、氨基酸氧化酶及各种离子检测手段在可穿戴设备上的整合，建立阵列式微针酶电极的工艺流程，实现心血管及糖尿病健康管理示范；课题组研制的柔性电极，如图1所示。

（2）医疗设备集成与健康状态辨识方面。Kim等[19]分析了穿戴式低功耗心电图监测专用集成电路的设计。Kmon 和Grybos[20]研究了基于互补金属氧化物半导体（CMOS）工艺的低功耗低噪声多通道神经放大器。Muller等[21]研制了采用 $0 . 5 \mathrm { V }$ 低电压供电的生理信号采集IC。Lee等[22]设计了基于Gm-C结构的低截止频率滤波器结构，芯片在超低截止频率和电源噪声抑制方面有进一步的改善。Qian 等[23]分析了应用于癫痫病治疗的微功率低噪声神经信号检测记录前端电路。Chang等[24]致力于研究低功耗高性能数字滤波器的设计。Piwek等[25研究可穿戴衣物为患者提供个性化的健康数据，协助自我诊断和干预。Poon等[2分析了大数据应用背景下的可穿戴传感器技术的应用前景；McDonald等[2系统分析了数据与疾病、健康或行为的关联性；Chaussabel和Pulendran[28论述了基于穿戴式数据采集的信息应用于临床决策的相关案例；Rumsfeld等[2将相关的穿戴式数据集与智能分析方法应用于具体心血管疾病的临床分析；Eisenstein[30将基因生物数据与健康监护数据应用相结合，应用于社区

![](images/0697b757e7489a764dde9a97a8fa3768dfe1b58f282945d8cef6231c71a29068.jpg)  
图1柔性电极

人口的医疗与康复实证。

# 2.3当前研究领域存在的问题与制约

前述研究工作很大程度上提升了穿戴式人体传感器网络各单项技术的水平，但是纵观相关领域的科研工作，尚存在如下不足：（1）在生物检测与传感部分，对材料创新、可获取的体征参数的种类和新参数的研究较多，但是对柔性传感器的接口电路、符合人体生理学和工效学的传感器优化设计的研究较少，导致样机系统在动态连续检测时的效果变差，很多传感器不能实用。（2）上述研究对传感器、IC芯片、电子电路等所有模块的柔性集成的研究较少。因此，虽然传感器是高度可柔的，但整个系统的柔性较差或几乎没有柔性，使得以人体传感器网络为核心的柔性穿戴式医疗设备的称谓“名不符实”，也导致连续检测期间运动伪差的增大和穿戴舒适性的降低。（3）对柔性系统进行原理验证的探索研究比较多，但与具体医疗健康需求相结合的应用研究比较欠缺。

上述3个问题严重制约了以人体传感器网络为核心的柔性穿戴式医疗设备真正被作为今后基层医疗、移动医疗的技术手段面向大众的推广。如何克服和解决这些问题，是该领域内具有挑战性和重要性的一项前沿课题。

# 3研究策略建议

人体传感器网络技术是穿戴式医疗健康设备在健康管理、随身健康监护、远程医疗等健康医疗设备或解决方案等方面的重要技术基础[31]。未来的技术突破主要集中在人体传感器网络的关键技术、核心器件和解决方案，可从以下4个方面展开研究，进一步为实现可穿戴医疗健康应用提供相应的技术积累

# 3.1图形化、多模态MEMS柔性电极制备技术

（1）基于人体工效学原理，优化电极结构形状。开发在人体不同状态下仍保持良好电学性能和信号采集性能的传感器互联互通方案，为穿戴式传感器信号的采集、处理与分析提供安全舒适、稳定可靠的体表接口。

具体包括研究基于柔性衬底的MEMS设计方法，建立柔性电极结构设计和分析优化模型。基于MEMS柔性电极对电生理/化学/物理等多模态信号采集方法复杂度高、难度大，可以采用图形化高密度电极制备的方法。该方法使用聚合物材料聚二甲基硅氧烷（PDMS）和金属金（Au）作为主要结构材料，这种柔性聚合物作为衬底排布高密度微米级金电极阵列，辅以图形化导线网络，起到保护金属电路的作用，从而实现良好的柔性、化学稳定性和生物相容性，最终实现与人体表皮的最优接触。

（2）图形化、多模态MEMS柔性电极制备过程。准备柔性聚对苯二甲酸乙二酯（PET）基板，采用旋涂法在基板上覆盖光刻胶，通过光刻将需要镀金部位的光刻胶刻蚀掉；接下来，采用电子束蒸镀原理在基板上先后沉积铬和金（铬有利于增强金和PET基板的结合）；然后通过有机溶剂（如丙酮）溶解光刻胶，同时光刻胶上面的铬和金也随之剥离基板，只有需要镀金区域的铬和金保留下来；最后清洗基板。相比于传统柔性电极，基于MEMS的柔性电极可以保证电极长期安全稳定的工作要求、最大化满足可控图形化的需求，以及提高整体器件的拉伸、弯曲、折叠等机械性能，实现与人体皮肤紧密无创贴合，增加了信号稳定性和舒适度，从而可以在皮肤表面实现无不适感觉的长期佩戴测量，具备生物安全性，满足个性化设计的需求。同时，通过三维图形化设计，降低表面阻抗，增强电极与皮肤贴附性，进一步提升信号采集灵敏度。

(3）柔性电极的机械性能、电学性能和生物安全性测试。探究各种因素对柔性电极的影响，以及如何改善传统柔性电极力学性能和粘连性不足等缺点，以提高柔性电极在复杂环境下的贴合程度，提高图形化MEMS 电极的信息采集能力。

# 3.2高精度参数提取与设备柔性集成技术

（1）高精度多模态模拟前端生物检测IC芯片设计技术的研究。图形化、多模态的MEMS传感器，可以在体表测量电生理、力（触）觉、pH值、乳酸等多种参数[32]，对接口电路精度的要求更高，可以研究基于动态共模反馈的低噪声低失调运算放大器和基于电流模技术的高共模抑制比增益可调的仪表放大器设计技术，以及采用全CMOS结构设计高精度低功耗电压/电流基准源和全MOSFET结构的电源电压及温度补偿等技术，开发更高精度和更低功耗的柔性可穿戴医疗设备模拟前端芯片，如图2所示。

（2）高精度参数提取与全柔性微系统集成。首先，结合自主IC和其他功能部件的物理尺寸和空间布局的实际情况，研究高柔性基板/高精密布线的计算机辅助设计技术，研究根据柔性衬底和柔性基板的运动学分析进行优化布局布线的方法；同时，为降低电路系统中数字电路部分噪声和热噪声对模拟电路的干扰，研究减少噪声传播的布局布线多级隔离结构，将干扰尽可能降低。其次，探究柔性衬底和柔性基板的匹配设计，融合MEMS技术与电子技术，实现全柔性的微系统集成。最后，针对生理参数非平稳非线性的特点，采用非线性滤波方法，并加入信号质量评价，联合形态学分析和时序分析方法进行伪差检测，剔除污染严重的不可用信号段，达到准确可靠地提取多模态体表信号的目的。

# 3.3人体通信技术

（1）基于人体通信原理构建穿戴式通信系统。人体通信是以“人”为通信媒介，具有低功耗、安全性高和身体状态对信道影响小的优点。可以采用人体通信原理构建穿戴式通信系统，这与采用蓝牙、Wi-Fi等常规方法构建WBSN有极大不同[33]。利用人体自身在特定频率下出现的电容耦合现象，进行高能效和高保密性的近场无线数据传输，对提升穿戴式设备传输性能、完善WBSN理论体系有重要意义。

（2）基于人体生物特征获取人体信息。基于人体通信的人体生物特征信息传感技术是在多个实验对象的基础上，选取不同的实验部位，将人体通信收发器放置在实验部位，信号发生端产生不同频率、幅度、调制方式的波形，在接收端记录相应的衰减值。通过建立数值仿真模型，研究电介质变化对信号的影响；通过实验与仿真相结合，研究基于人体通信的人体生物特征信息传感技术，获取人体的“生物密码”。图3所示为人体通信网分层安全管理架构。

# 3.4穿戴式医学智能技术

基于医学智能的穿戴式医疗设备数据融合处理。在实现多种数据可靠采集及海量数据积累的基础上，开展基于机器学习的柔性可穿戴医疗设备数据的融合。对不同来源、不同尺度的多种复杂数据进行分析，避免信号中的噪声及错误相互叠加而降低预测准确率，实现精确的个性化预测。研究多数据流信息的特征工程与模式匹配、信息融合、一致性及异常检测，海量非标数据集的无监督学习方法，以及基于柔性穿戴式数据集的健康监护应用及评估体系，分析穿戴式数据集中的数据高维特性和冗余特性；研究基于降维及数据嵌入的机器学习方法，同时考虑穿戴式数据集应用中的电生理/物理/化学多模态传感数据的特性，以及应用于健康监护应用中的适应性；研究具备自适应特性的数据嵌入降维机器学习计算框架，探讨高维可穿戴数据集的数据分析方法与应用机制。

![](images/aed09af44d5f9c7ca7e2ffc35ae998721ae3aa6e9803ed8a26e0cdf08fbb5ec8.jpg)  
图2医疗设备模拟前端芯片

![](images/bf5411699d4df1321b94351bfef9f19c663760a3676e078dc14fa9f5f4864669.jpg)  
图3人体通信网分层安全管理架构

# 4对未来研究中关键问题的思考

基于人体传感器网络技术的穿戴式医疗设备，必须考虑“人-机-环境”三者之间的关系。

（1）如何充分考虑环境与人体的“变”与“动”来优化核心模块的可靠性是一个关键科学问题。穿戴设备所处的环境多变，人体自身也基本处于运动状态，确保柔性设备总体性能的稳定、核心模块的可靠，是非常重要的。此外，若是可以充分利用这种“变”与“动”，建立理论模型，进而研究自适应的可靠性提升策略，可为柔性可穿戴医疗设备的实际应用打下理论基础。

(2）如何在深入理解人体健康信息的基础上提高柔性可穿戴医疗设备的信号采集精度是另一个关键科学问题。柔性设备与人体的频繁接触不可避免，电极部分更是要受到人体穿戴部位的结构、机械性能的影响，信号互扰很严重[34]。如何结合人体生理学与工效学，增加柔性设备贴附性、增加信号提取的“效率”，至关重要。同时，人体是一个综合的整体，如何通过体表多参数提取的有效组合，弥补单个传感器的检测精度的不足，也具有重要的理论意义和实际应用价值。

# 参考文献

1Park Y T,Han D.Current status of electronic medical record systems in hospitals and clinics in Korea.Healthcare Informatics Research,2017,23(3):189.   
2周兵.基于蓝牙低功耗技术的可穿戴式健康监护系统研究.北 京：中国科学院大学，2014.   
3Chen L Y, Tee B C K,Chortos AL,et al.Continuous wireless pressure monitoring and mapping with ultra-small passive sensors for health monitoring and critical care. Nature Communications, 2014, 5: 5028.   
4Peng H,Dang W, Cao J, etal. Topological insulator nanostructures for near-infrared transparent flexible electrodes. Nature Chemistry, 2012, 4(4): 281-286.   
5 Jandhyala S, Walper S A, Cargill A A, et al. Integration of biochemical sensors into wearable biomaterial platforms. SPIE Commercial $^ +$ Scientific Sensing and Imaging. 2016, 9863: 1-6.   
6 Selvam A P, Muthukumar S,Kamakoti V, et al. A wearable biochemical sensor for monitoring alcohol consumption lifestyle through Ethyl glucuronide (EtG) detection in human sweat. Scientific Reports,2016, 6: 1-9.   
7Zheng Y L, Ding X R, Poon C C Y, et al. Unobtrusive sensing and wearable devices for health informatics.IEEE Transactions on Biomedical Engineering, 2014,61(5): 1538-1554.   
8 Raj P, Raman A, Nagaraj D, et al. High-Performance Big-Data Analytics.Switzerland: Springer International Publishing, 2015: 391: 424.   
9 Laschi C, Mazzolai B, Ciancheti M. Soft robotics: Technologies and systems pushing the boundaries of robot abilities. Science Robotics,2016,1(1): 1-11.   
10 Ryu S,Lee P, Chou JB,et al. Extremely elastic wearable carbon nanotube fiber strain sensor for monitoring of human motion. ACS Nano, 2015, 9(6): 5929.   
11 Yugandhar G, Rao G V, Rao K S. Modeling and simulation of piezoelectric MEMS sensor. Materials Today Proceedings,2015, 2(4-5): 1595-1602.   
12 Yamada T,Hayamizu Y,Yamamoto Y, et al.Astretchablearbon nanotube strain sensor for human-motion detection. Nature Nanotechnology,2011, 6(5): 296-301.   
13 Tee B C, Chortos A,Berndt A,et al. Askin-inspiredorganic digital mechanoreceptor. Science, 2015,350(6258): 313-316.   
14 Lipomi D J, Vosgueritchian M, Tee B C, et al. Skin-like pressure and strain sensors based on transparent elastic films of carbon nanotubes. Nature Nanotechnology. 2011, 6(12): 788-792.   
15 Chae S H, Yu W J, Bae JJ,et al. Transferred wrinkled $\mathrm { A l } _ { 2 } \mathrm { O } _ { 3 }$ for highly stretchable and transparent graphene-carbon nanotube transistors. Nature Materials,2013,12(5): 403-409.   
16 Gong S, Schwalb W, Wang Y, et al. A wearable and highly sensitive pressure sensor with ultrathin gold nanowires.Nature Communications,2014,5(2): 3132.   
17 Liao C, Mak C, Zhang M, et al. Flexible organic electrochemical transistors for highly selective enzyme biosensors and used for saliva testing. Advanced Materials,2015, 27(4): 676-681.   
18 Bae W G, Kim D, Kwak M K, et al. Enhanced skin adhesive patch with modulus-tunable composite micropillars.Advanced Healthcare Materials,2013,2(1): 109.   
19 Kim H, Yazicioglu R F, Kim S,et al. A configurable and low-power mixed signal SoC for portable ECG monitoring applications. Vlsi Circuits,2011, 8(2): 142-143.   
20 Kmon P, Grybos P. Energy efficient low-noise multichannel neural amplifier in submicron CMOS process.IEEE Transactions on Circuits & Systems IRegular Papers,2013,60(7): 1764-1775.   
21 Muller R,Gambini S,Rabaey J M.A $0 . 0 1 3 ~ \mathrm { m m } ^ { 2 } \ 5 ~ \mu \mathrm { W }$ DCcoupled neural signal acquisition IC with $0 . 5 { \mathrm { ~ V ~ } }$ supply.IEEE Jourmal of Solid-State Circuits,2012,47(1): 232-243.   
22 Lee Y C,Hsu W Y, Huang T T,et al. A compact Gm-C filter architecture with an ultra-low corner frequency and high groundnoise rejection. Biomedical Circuits and Systems Conference, 2013,12(4): 318-321.   
23 Qian C, Parramon J, Sanchez-Sinencio E.A micropower low-noise neural recording front-end circuit for epileptic seizure detection. IEEE Jourmal of Solid-State Circuits. 2011, 46(6): 1392-1405.   
24 Chang C H, Molahosseini A S, Zarandi AA E, et al. Residue number systems: A new paradigm to datapath optimization for low-power and high-performance digital signal processing applications. IEEE Circuits & Systems Magazine,2015,15(4): 26- 44.   
25 Piwek L, Ellis DA,Andrews S,et al. The rise of consumer health wearables: Promises and barriers. PLoS Medicine. 2016,13(2): 1-9.   
26 Poon C,Lo B,Yuce M,et al.Body sensor networks: in the era of big data and beyond. IEEE Reviews in Biomedical Engineering, 2015, 8: 4-16.   
27 McDonald D, Glusman G, Price N D. Personalized nutrition through big data. Nature Biotechnology,2016,34(2): 152-154.   
28 Chaussabel D, Pulendran B.A vision and a prescription for big data-enabled medicine. Nature Immunology,2015,16(5): 435- 439.   
29 Rumsfeld J S,Joynt K E,Maddox T M. Big data analytics to improve cardiovascular care: promise and challenges.Nature Reviews Cardiology,2016,13(6): 350.   
30 Eisenstein M. Big data: The power of petabytes. Nature, 2015, 527(7576): 2-4.   
31邱明林.基于人体传感网的穿戴式远程健康监护系统的设计 与实现.杭州:浙江大学,2013.   
32 宋轶琳，林楠森，姜红,等.纳米铂黑修饰微电极阵列在神经 电生理检测中的应用研究．东南大学学报（医学版），2011, 30(1): 29-32.   
33 冷腾飞，聂泽东，王磊.人体通信信道测试系统的研究与实现. 传感器与微系统,2012,31(11):17-19.   
34 许鹏俊.用于体表心电监测的纺织结构电极与皮肤之间机械 作用分析及动态噪音研究.上海：东华大学,2012.

# Wearable Body SensorNetwork

Han ShipengOlatunji Mumini OmisoreWang Lei （Shenzhen Institutes of Advanced Technology, Chinese Academy of Sciences,Shenzhen 518055, China）

AbstractAsideteactatitoringangdprocssgofealtfoatiointepromnttoesgalth status,ithasalsobenanimportantmeansforefectiveprevetionandtreatmentofdiseasesEmergenceofwearablebodysnsoretork (WBSN)isawaytoevehealth trackingprocssanditellgentservicesquiredfodyamiconitorigofmanifoationBasedon analysisofthepresentsituationandresearchstatusofwearablehumansensorthispaperpresentsasystematicreviewonthecoretechology of WBSNthat ouldbeofgreatimpactinealthdagosisanddiseasesprevention.Finallbasedonte wearablemedicaldeviceadesor networtechnologytwosietificquestiosregardig“ma-machie-environmentarepresented.Oeistestrategyorethodtosolvte core technology of WBSN and the other is WBSN based wearable medical device.

Keywordshuman health,intelligent services,wearable, body sensor networks韩世鹏中科院深圳先进技术院研究助理。主要从事柔性传感器和医用机器人等方面的研究。参与了国家自然科学基金、中科院重点部署等科研项目。发表论文4篇。E-mail:sp.han@siat.ac.cn

HanShipengResearchAsistantattheShenzenIstitutesofAdvancedTechnology,ChineseAcademyofSciences(CAS).Hissearch focuincludesfexiblesesorsandmedicaloots.HhasparticipatedinseralprojectssuporedbyatioalNaturalSeceoudatios ofChina,KeyDeploymentofCAS,andotherresearchprojects.Hehasauthored/oauthored4researchpapers.E-mail:span@siatac.cn

王 磊中科院深圳先进技术院医工所副所长、微创中心主任、院纪委委员，研究员。荣获中科院“百人计划”、中科院王宽诚率先人才计划、广东省科技创新领军人才、深圳市政府特殊津贴等多种荣誉。主要从事人体传感器网络(BSN）技术、可穿戴技术及医用机器人等方面的研究，主持和参与了国家自然科学基金、国家科技重大专项、国家“863”计划等重大科研项目。累计发表科研论文200 余篇，其中SCIEI/ISTP索引150余篇；出版专著和专著章节10部。E-mail: wang.lei@siat.ac.cn

WangLeiDeputyDirectoratIstitutesofiomedicalandHealthEngineringandDrectorofCenterfoMedicalRoboticsandMiialy InvasiveSurgicalDvicesthatenenIstitutesofdvancedTecholgyinseAcademyfSiences (CAS).Hisearchfocu includesbodysnsortwoks,edicalbots,andwearabletologies.Heaspresidedoeradartipatediajrsientificac projectschasthKeyatioalaturaienceFoudatioofina,ajortioalSiceadThologyProjetsndNatioal6 ProgramProject.Heasuthord/oauthodovertotalofsieificpapers,cdingmorethan5OCEindexedts monographs. E-mail: wang.lei@siat.ac.cn