# 基于BIM的建筑运维技术与应用综述

丁梦莉」，杨启亮1\*，张万君²，邢建春1，谢立强¹，张晓冰（1.中国人民解放军陆军工程大学国防工程学院，南京210007；

2．91126部队营房科，大连116041;

3.32125部队，济南，250100)

【摘要】运维阶段占据了建筑生命周期 $90 \%$ 以上的时间和 $8 0 \%$ 以上的成本，因此，追求高效的运维管理方式具有重要的意义。本文论述了BIM在建筑运维中应用的优势，从技术和应用两个方面讨论分析了基于BIM的运维管理方法，并对当前面临的技术挑战进行了分析，展望了未来研究的发展趋势。

【关键词】建筑信息模型（BIM）；运维管理；应用现状与技术分析；研究趋势【中图分类号】TU17 【文献标识码】 【文章编号】

目前，传统的基于图纸和二维平台的管理具有交付时易丢失信息、管理效率低、可视化程度低等缺点，在实际应用中不仅浪费时间，而且还易出现错误。如何改变传统运维模式，寻求更加高效的运维管理方式已经得到了越来越多研究人员的重视。通过实践已证明使用BIM技术，可以使整个工程项目在设计、施工和运维阶段都能有效的实现节省能源、节约成本、降低污染和提高效率的目的，提高建筑管理的集成化程度[31]。BIM 技术已从建筑设计、施工阶段向运维阶段渗透应用[1]。

虽然国内外都曾有关于BIM运维管理应用的综述文章，国内的胡振中[2等也对 BIM在运维管理中的应用做了较为完备的总结，但缺少对应用的具体功能和技术问题的讨论，对运维平台的一些核心构造技术总结还不够完善。与上述综述文献不同，本文总结了BIM与运维管理相结合的优势，分析了BIM用于运维管理的技术难点，并结合既有的研究成果，对BIM在运维管理中的应用进行了总结分析，文章最后对将来的研究方向进行了展望。

# 1BIM在运维中应用的优势

将BIM技术应用于运维管理中，可以实现信息的集成共享和设备的可视化管理[3]。BIM的3D可视化模型可以实现建筑部件的精确几何表示和建筑构件的定位，形成易于修改的可视化组件，从而实现对空间的有效管理；可以快速生成运维管理数据库，实现更快更有效的信息共享，节约时间和成本；能够将模型用于建筑性能的模拟和调试，预测能耗绩效和计算生命周期的成本；可以将模型数据用于仿真工具，并将构建的信息用于建筑模型的优化与改造；还具备一些新型应用，比如有助于规划路线，用于维修人员的路径优化或者智能紧急撤离[24]。

![](images/e59deb95d6f0bb636a534d0c3bfb4c439815897fb470664875901f4ec6e7ab4b.jpg)  
图1各种管理方式比较

如图1所示，与基于传统纸质图纸的人工化管理方式相比，基于BIM的全局综合管理方式不仅提高了设计、施工和运维阶段的效率，而且降低了各阶段信息交付时的损失。BIM的3D模型可以包含更多的模型信息，帮助施工和管理人员更加透彻的理解建筑设计。与基于二维平台的半自动化管理方式相比，基于BIM的全局综合管理方式降低了从设计阶段到运维管理阶段模型转换所需要的时间，其3D 可视化的管理方式提高了运维管理的效率[22]

在BIM与运维管理融合的优点中，准确的空间管理、高效的数据库源以及使用BIM数据进行预防性维护是最重要的原因[24]。

作者简介：丁梦莉（1994-），女，硕士研究生，主要研究方向：BIM技术及应用

# 2基于BIM的建筑运维管理核心技术问题分析

基于BIM的运维管理是一种新型的三维管理方式，在以BIM为重要载体实现信息整合与展示的基础上，能够实现建筑信息的直观可视化显示和对设备运行的可视化控制，并有效提高运维管理效率和智能化管理水平。

我们将基于BIM的建筑运维管理核心技术归纳为三个方面：（1)面向运维管理的BIM模型；（2）信息物理系统融合集成技术；（3）平台开发方法。

# 2.1 面向运维管理的BIM模型

模型是构建运维管理系统的基础，如何构建模型、模型应该满足什么要求、如何自定义扩展模型，都是需要实际考虑的问题。构建系统时，对缺少的模型需要进行自定义和扩展，而目前对BIM模型的扩展主要有三种方式[4：基于IFC Proxy 实体的扩展、基于增加实体类型的扩展、基于属性集的扩展。

基于IFCProxy 实体的扩展方式是利用IFCProxy实体对原模型体系中未定义的信息进行扩展。周亮[5等将输变电工程中的GIS 设备根据IFC标准扩展为电气设备模型，可用于实现有效的信息交换和共享。YuK等介绍了设备管理类和计算机集成设施管理系统开发的框架。

基于实体类型的扩展方式是对模型本身定义的扩充和更新。余芳强等整理了自IFC2x发布以来，各版本IFC标准升级时核心模块的变化与发展。BuildingSMART对IFC标准做了新的扩展，制定了新的IFC4标准。

基于属性集的扩展方式是对具有信息描述功能属性的扩展。刘照球9等分别从几何信息模型、荷载信息模型、分析信息模型三个方面对IFC标准的结构产品模型的缺失信息进行了扩展，完善了IFC标准的结构信息模型基本框架。Rio J[等探讨了当前 IFC 模型的局限性，在传感器通用属性集对的基础上，提出了对各传感器的特殊属性集进行扩展的方法。

# 2.2虚拟BIM模型与建筑物理系统融合集成技术

目前主流的BIM技术只支持对几何数据、空间位置和关系等静态信息进行描述，已经不能满足日益复杂的运维管理需求，如何实现BIM的静态信息模型与建筑实体模型之间的动态交互成为亟待解决的问题。

信息物理融合系统CPS 是一个综合计算、网络和物理环境的多维复杂系统，通过3C(Computation、Communication、Control)技术的有机融合与深度协作，可实现大型工程系统的实时感知、动态控制和信息服务[I]。它将数字图形作为连接物理和几何属性的介质，实现了“数据附着于图形，图形蕴含数据"[12],能够把原来建筑中独立运行并现场操作的各设备，结合RFID等技术汇总到统一的管理平台上，在监视设备的实时运行状态的同时，可以进行远程管控。

# 2.3平台开发方法

运维平台的构建需要解决模型数据双向传递、三维模型的显示以及数据绑定等问题[13]。其中，平台的三维模型可视化功能需要将信息完整的转换为三维模型，并且对各构件的位置和关系信息实现可视化显示。目前，模型显示主要通过 Auto CAD、Open GL、Direct3D 等软件。

采用移动手持终端是平台信息交互的有效方式，目前已经在BIM施工阶段得到了应用，如广州地铁施工中使用的“派工单”，将施工信息通过手机APP等设备下发给工人，同时将施工进度反馈到系统中。运维阶段主要是应用于设备巡检中的漫游，对设备扫描显示设备的基本信息[4]，以及设备报修等方面[15]。

# 2.4 总结分析

![](images/4cb4199683db25556d53cfd261e785e6d894bd6479cbb519b69790aa79b91266.jpg)  
图3核心技术研究热度

1975年，“BIM之父”，乔治亚理工学院的ChuckEastman教授提出了BIM的概念，从那时起，BIM这一命题就对建筑业产生了巨大的影响。本文分析了构建基于BIM的运维管理系统需要解决的核心技术问题，总结了已有的研究成果。如图3所示，现有的研究主要集中在基于BIM的运维平台构建以及BIM模型的扩展上，对于如何实现BIM静态信息模型与建筑设备之间的动态信息交互这一问题研究甚少。

# 3BIM在建筑运维管理中的应用功能分析

# 3.1 应用功能分类与定义

BIM技术所具有的可视化和协调能力，可以将数据与3D模型相结合，不仅可以有效促进信息的交互操作，还能够提高建筑信息与运维系统的集成与兼容性。我们根据运维管理系统的功能将其划分为7类，其分类及功能与应用如表1所示：

表1功能和应用  

<html><body><table><tr><td>名称</td><td>技术分析</td><td>应用</td><td>作者</td></tr><tr><td>空间 管理</td><td>对空间和空间中的人员设备进行的管理。包 括人员管理，空间规划分配，设备位置管理。</td><td>（1）城市轨道交通建设 （2）曼彻斯特市政厅大楼</td><td>[3][16] [17][27][31]</td></tr><tr><td>信息 管理</td><td>对建筑所有信息以及运营产生的所有新信息 的管理。包括资产管理和设备信息管理。</td><td>（1）用于资产管理的BIM系统 （2）医院综合维修监控 （3）知识管理</td><td>[18][28]</td></tr><tr><td>设备 监管</td><td>对建筑中设备运行的监测和运行状态的控制 调整。包括设备信息监管和设备实时控制。</td><td>（4）电子文件管理系统（EDMS） （1）BIM应用于设备运行状态监管 （2）应用于设备实时控制</td><td>[9]</td></tr><tr><td>安全 管理</td><td>对建筑中的安全问题排查和紧急事故的反馈 管理。包括安保管理、火灾消防管理和隐蔽 工程管理。</td><td>（1）楼宇自动化系统（BAS）</td><td>[19][23]</td></tr><tr><td>能耗 管理</td><td>对建筑的能耗进行显示、分析、远程控制， 以达到节能目的的管理。</td><td>（1）悉尼歌剧院 （2）能源管理系统（EMS） （3）能源分析和可持续性</td><td>[20][21] [28][29]</td></tr><tr><td>引导 管理</td><td>根据实时信息，对变更时的人员、操作、设 备流量进行管理，以避免操作冲突。</td><td>（1）南加州大学建设项目 （2）泽维尔大学的建筑工程</td><td>[31]</td></tr><tr><td>协助 管理 功能</td><td>对建筑的其他功能需求提供建筑物的空间、 构造、数量信息的管理。</td><td>（1）自动化成本估算 （2）计算机维护管理系统（CMMS）</td><td>[30]</td></tr></table></body></html>

# 3.2 应用现状

基于BIM的可视化空间管理，可以对人员和空间实现系统化、信息化的管理。人员位置管理能够对建筑物中人员位置的变动进行实时监控。校园运维系统[模块可以通过视频监控实现对校园巡逻人员的位置跟踪，将信息实时显示在平台上。空间规划分配[3是对建筑中各功能模块、商户位置等的最优布局。设备位置管理能够实现对建筑物中电梯、车辆等移动设备的位置监控[17]。

信息管理主要包括资产管理和设备信息管理。通过在RFID的资产标签芯片中注入信息，结合三维虚拟BIM技术可以实现对建筑资产精确定位、快速查阅。设备信息管理是对设备的检修与清洁周期、废物处理与回收利用等信息的管理。轨道交通设备维修系统，改变了传统需要人工查看故障点，手动将信息录入数据库的报修方式。设计的报修平台分为巡检人员手持式移动设备报修和平台实时监控报修[18]两种方式，提高了效率，减少了中间环

节的错误。

设备监管包括设备信息监管和设备实时控制。设备信息监管能够实现对设备运行状态的监测，确保设备故障状态及时被发现。基于BIM技术的管理系统集成了对设备的搜素、查阅以及定位功能。基于BIM与AR等人机交互技术相结合的运维管理系统，可以在BIM模型上直观显示设备是否正常运行，并且通过BIM运维平台可对设备进行直观化的实时控制。

安保管理是对系统中一切人、物和环境状态的管理和控制，主要应用在军事基地、重要设备机房、银行、校园、主干道路等对监测要求比较高的场所。例如：基于BIM技术的火灾消防管理系统有效提高了运维效率，保证了所有消防设备的正常运行[23]；基于BIM技术的运维系统可以将原本主要由人工管理的隐蔽工程以三维可视化的形式直观的表示出来，将各种管线显示在三维模型中，通过点选模型可以实现对管线信息的查询。

能耗管理是对建筑物的智能化节能管理。电量监测系统通过安装具有传感功能的电表，可在管理系统中收集用电信息，并对能耗情况进行自动统计分析，从而及时发现异常。水量监测系统通过对水表的监测，可以在BIM运维平台上清楚显示建筑内水网位置信息，对水平衡进行有效判断[20] [21]。总的来看，建筑能耗管理系统是将BIM与物联网、传感器、控制器等技术相融合，对建筑用能进行监测和分析，并且可以控制用能设备的运行，降低了传统运营管理下由于建筑物能耗大引起的成本增加。

# 3.3总结

![](images/705d9a178cac050658ea84c15ff515246af359a0875fb7888f3f2f6bc1d640f7.jpg)  
图4应用比例

通过查阅并归纳各方面的文献资料可以看出，目前BIM技术在建筑工程运维管理中的应用主要是在设备监管方面（如图4所示），设备的有效管理可以给建筑业主带来了效益的优化。而如何在传统优势领域继续优化并在新兴领域扩展BIM的应用范围，是我们接下来的研究方向。

# 4基于BIM的运维技术瓶颈分析

BIM技术为运维管理提供了新的协作方法，但是也产生了一些问题。在建筑运维管理需求不断提高的情况下，如何实现更深层次信息的获取、交互以及可视化呈现等问题，是在未来需要关注的核心方面。

（1）运维平台信息处理与大数据分析。BIM可视化监测平台产生了关于建筑和设备运行的大量数据，因而对搭载平台的计算机提出了大容量存储、快速处理、精确分析的要求。云计算是能提供动态资源池、虚拟化和高可用性的计算平台，凭借其所拥有的计算和存储能力，有望在未来实现BIM运维平台的移动终端配置，此时，用户便可以通过移动终端直接从云平台调取所需的数据。

（2）平台与物理系统之间动态实时交互的问题。现有的运维平台功能主要是对建筑和设备的监测，是信息的单向传递，是一种无法与物理世界交互的“聋哑模型”，缺少控制方面的应用。如何实现系统的监测与控制一体化，实现信息的动态实时交互，是目前研究的难点[5][12]。目前，将 AR，AV，VR，MR,GIS等技术与BIM进行融合，并成功应用于施工现场，实现了将BIM技术的信息数据与现场实际环境进行实时交互的需要。将AR 等技术用于运维阶段，可以充分实现BIM信息的价值，实现信息的直观化、可视化[37]。

（3）缺乏实用可靠的运维管理平台。现有运维平台功能单一，一般只是针对单一功能，无法形成统一的协同合作系统，并且大部分平台只能用于建筑物的漫游和简单的信息查看，不能做到对设备的实时监控，而自主研发平台难度大，研发周期长，资金成本高，并且应用度较低[26]。未来对于运维管理平台的不断开发，将使其逐步形成一个整体的建筑协同平台，由本来只针对单一运维领域向功能完善的运维管理系统发展。

（4)基于BIM运维平台与现有系统的角色定位问题。传统的运维管理系统（如BA)已经较为成熟，并且应用广泛。而人们对新技术仍然有接受障碍，缺乏现实案例与投资回报的正面证明，新技术的实行需要对基础设施进行投资，比如人员培训和新的软件工具开发，投资回报周期较长。随着BIM系统不断完善发展，将在未来实现科研与实际工程项目相结合，在实践中达到检验软件功能、培养人才并优化施工运维技术的目的。

（5）设计阶段与运维管理阶段的矛盾。现有的BIM冲突检测软件，只能验证运维系统和设备之间在结构布局上的物理冲突，在运维阶段的设备实际安装运行与碰撞检查之间还存在问题。例如，可能在碰撞检查和实际安装时没有问题，但是由于设备之间出现运维信息相互干扰，导致某些信息在维护阶段不可访问，从而影响维护人员的检查和判断。设计阶段和运维阶段的矛盾将导致信息不匹配和成本的增加，未来运维阶段将更加考虑人的需求和两者之间的协调。

（6）目前，BIM技术仅用于单个建筑物的管理。随着人类社会的不断发展和城市建设的日益复杂，智慧城市的信息管理模式也开始受到关注。城市信息模型（CIA）[32]是城市空间的延伸，是一个综合的城市应用系统，而不是简单的城市元素系统的二维数字元素和三维模型的集合[25]，CIA 面临的挑战比孤立建筑的外部环境要求更为复杂。BIM技术作为未来发展方向，为未来整体化的城市建设与管理奠定了基础。

# 5结论

随着智能建筑的发展，人们逐渐认识到运维管理的重要性，开始探求更加高效的管理方式。BIM作为一种备受关注的模型管理方法，不仅可以建立三维几何模型，还可以提供与建筑物相关的各种建筑构件和系统信息。使用BIM作为建筑项目信息的中央存储库，彻底改变了传统的建筑运维管理方式。未来我国BIM技术的发展，不仅要重视运维平台的开发，还应该完善BIM技术标准，不断探索有效的应用模式，逐渐实现以人为本、人机交互和信息共享的智能化运维管理。

# 参考文献：

[1]Eastman C M,Teicholz P,Sacks R,et al.BIMHandbook:A Guide to Building InformationModeling For Owners[J].Australasian Journal ofConstruction Economics& Building， 2012,12(3):101-102.  
[2] 胡振中，彭阳，田佩龙．基于BIM的运维管理研究与应用综述[J].图学学报，2015,36(5):802-810.  
[3] Pezeshki Z,Ivari S A S.Applications of BIM:ABrief Review and Future Outline[J].Archives ofComputational Methods in Engineering，2018,25(2):273-312.  
[4] 王勇，张建平，胡振中．建筑施工IFC 数据描述标准的研究[J]．土木建筑工程信息技术,2011(4):9-15.  
[5] 周亮，吕征宇，邓雪原,等．一种基于IFC的输变电工程GIS 设备模型扩展方法:,CN105488306A[P]. 2016.  
[6] Yu K,Froese T,Grobler F. A developmentframework for data models forcomputer-ntegratedfacilitiesmanagement[J].Automation in Construction,2000, 9(2):145-167.  
[7] 余芳强，张建平，刘强．基于IFC的BIM子模型视图半自动生成[J].清华大学学报(自然科学版),2014(8):987-992.  
[8] BuildingSMART ， IFC4 documentationhttp://www.buildingsmart-tech.org/ifc/IFC4/Add2/html/  
[9] 刘照球，李云贵，吕西林．基于IFC 标准结构工程产品模型构造和扩展[J].土木建筑工程信息技术,2009,1(1):47-53.  
[10]Rio J,Ferreira B,Martins JPP.Expansion of IFCmodel with structural sensors[J].Informes De LaConstruccion,2013,65(530):219-228.  
[11]李 犁,邓雪原.基于BIM技术的建筑信息平台的构建[J]．土木建筑工程信息技术.2012.4（2）：25-29.  
[12]王喜文．图解工业4.0的核心技术—信息物理系统(CPS)[J].物联网技术,2017,7(4):4-5.  
[13] 魏振华，马智亮.基于免费组件的IFC数据三维图形交互模块研究[J].土木建筑工程信息技术,2011(4):1-4.  
[14] Terreno S,Anumba C J,Gannon E,et al．Thebenefitsof BIMintegrationwith facilitiesmanagement:A preliminary casestudy[J].Advances in Physics,2015,42(3):343-391.  
[15] 王廷魁，赵一洁，张睿奕,等．基于BIM与 RFID的建筑设备运行维护管理系统研究[J].建筑经济,2013(11):113-116.  
[16]陈晓．基于BIM 的校园运维管理系统研究[D].西南交通大学,2016.  
[17] 张建华．基于BIM与Web 的立体车库运维系统研究[J].北京信息科技大学学报(自然科学版),2017,32(2):70-72.  
[18] 孙钰杰，张社荣，潘飞．基于IFC 的水电设备运行维护管理系统设计及原型实现[J].工程管理学报,2017,31(1):17-22.  
[19] 任荣．基于 BIM 技术的建筑消防系统优化[D].郑州大学,2015.  
[20] 张赞．从建筑信息模型(BIM)的角度思考建筑全生命周期的能耗管理[C]国际绿色建筑与建筑节能大会.2013.1-8.  
[21] Dong B，Zheng O，Li Z.A BIM-enabledinformationinfrastructureforbuilding energyFault Detection and Diagnostics[J].Automation inConstruction,2014,44(2):197-211.  
[22] Volk R， Stengel J， Schultmann F. BuildingInformationModeling(BIM)forexistingbuildings —Literature review and future needs[J].Automation in Construction,2014,38(5):109-127.  
[23] 石志道.基于BIM 的建筑消防设施管理系统研究[D]．沈阳航空航天大学,2016.  
[24] Terreno S,Anumba C J,Gannon E,et al. ThebenefitsofBIM integrationwithfacilitiesmanagement:Apreliminarycasestudy[J].AdvancesinPhysics,2015,42(3):343-391.  
[25] Chen H M,Wang Y H. A 3-DimensionalVisualizedApproach forMaintenanceandManagement of Facilities[J]. Proceedings of Isarc,2009.468-475.  
[26] L Li,X Y Deng.Construction of BIM-BasedBuilding Information Platform[J]. CivilEngineeringInformation Technology. 2012,2:25-29.  
[27] Ding L Y, Zhou Y,Luo $_ { \mathrm { ~ H ~ B ~ } }$ ，et al.Using nDtechnology to develop an integrated constructionmanagement system for city rail transitconstruction[J].Automation in Construction,2012,21(7):64-73.  
[28]D Dong B，Zheng O，Li Z.A BIM-enabledinformation infrastructure for building energyFault Detection and Diagnostics[J].Automation inConstruction,2014,44(2):197-211.  
[29] CRC for Construction Innovation,“Adopting BIMfor facilities management: solutions for managingthe Sydney opera house," 2007,http://eprints.qut.edu.au/27582/1/27582.pdf.  
[30] Vanlande R,Nicolle C,Cruz C. IFC and buildinglifecycle management[J].Automation inConstruction,2009,18(1):70-78.  
[31]WongKWF. THE UTILISATION OFBUILDING INFORMATION MODELS IN nDMODELLING: A STUDY OF DATAINTERFACING AND ADOPTIONBARRIERS[J].Electronic Journal of Information Technology inConstruction,2005,10:85-110.  
[32] Jiao Y,Wang Y, Zhang S,et al.A cloud approachtounifiedlifecycledatamanagement inarchitecture,engineering，constructionandfacilities management: Integrating BIMsandSNS[J].Advanced Engineering Informatics,2013,27(2):173-188

# Review of BIM-Based operation and maintenance in technologies and applications

Ding Mengli',Yang Qiliang', Zhang Wanjun², Xing Jianchun1, Xie Liqiang1， Zhang Xiaobing (1.PLA Army Engineering University,Nanjing 210007; 2.Army 91126 Barracks department, Dalian 116041; 3.32125army,Jinan,250100)

Abstract：In the management of building life cycles,operation and maintenance occupies more than $90 \%$ of the time and $80 \%$ of the overallconstruction costs.Thus,the research on more efficient operation and maintenance is of great significance.This paper discusses the advantages of theapplication in operation and maintenance based on BIM.We discussand analyze the BIM-based operation and maintenance in the context of technology and application. Future work regarding the technical challenges and development trends of operation and maintenance is proposed.

Keywords:building information modeling；operation and maintenance；literature review；technical analysis; future