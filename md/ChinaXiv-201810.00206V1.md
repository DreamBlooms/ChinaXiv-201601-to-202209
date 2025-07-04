# 栏目：VR虚拟现实技术/AR增强现实技术

# VR、AR在建筑工程信息化领域的应用

刘勇

（万间科技（深圳）有限公司，深圳518000）

【摘要】虚拟现实、增强现实、混合现实是新兴的多维可视化沟通技术，在各个领域都有广泛的应用，他们与建筑工程领域的BIM技术的结合应用，能发挥出两者的优势，相辅相成。他们在建筑全生命期都有极大的价值空间可供挖掘。本文从基础理论开始，深入探讨了BIMVR/AR这一创新融合技术在建筑规划与设计阶段、工程施工阶段、项目营销阶段、运维管理阶段等全生命期的应用需求、落地应用模式、应用现状以及未来发展方向和潜力。最后本文分析了技术进一步发展所面临的障碍及突破口。

【关键词】BIM；虚拟现实；增强现实；BIMVR；BIMAR【作者简介】刘勇（1991-），男，硕士研究生，万间科技（深圳）有限公司总经理，BIM产品经理，从事BIM与VR/AR结合的软件开发和技术研究工作。

# 1BIMVR/AR理论基础

BIMVR（Building InformationModeling inVirtualReality）是将BIM（建筑信息模型）和VR（虚拟现实）结合起来的一种技术手段[1]。

BIM工程师已经可以在工程施工前就做出来非常真实的BIM模型了，但是目前这种可视化的三维模型有很大的局限性。将BIM与VR技术相结合，可以让使用者不仅可以看到这个模型，还可以深入其中，身临其境，真实的感受身处模型之中。无论是对于设计方还是施工方，都能够得到充足的指导，避免很多很可能发生的事故、问题，让工程实施变得更加合理。AR、MR 亦如是[2]。

BIM是建筑工程管理领域新的信息沟通载体，基于BIM的大量工具软件和平台应用如雨后春笋，在逐渐替代传统基于CAD图纸的沟通方式。

VR/AR/MR，本质上是新的沟通技术，与之相关的软硬件成为新的沟通工具；它们也是继电脑、手机等信息处理和沟通工具之后的新一代沟通与通信平台。

BIM+VR/AR/MR所具备的价值潜力，对建筑业来讲，将不单单是一个信息载体和工具的升级，其整个信息沟通范式都会随着技术的深入发展而产生变革。图1介绍了BIM与VR/AR/MR的关系。BIMVR/AR/MR有望成为建筑工程产业新的沟通范式（Communication Paradigm）[3],形成新的技术门类和跨界学科。

![](images/407a7f209f70ac6790dde1c270bd0e123b70ff1398730c68aad0fe91462e5727.jpg)  
图1BIM与VR/AR/MR的关系

建筑业的生产效率及信息化水平，一直远远低于其他产业，本质源于其工程管理及沟通范式太陈旧落后，急需有更新的、更高效的沟通范式来对这一庞大产业进行革新，甚至颠覆。那么，BIMVR/AR/MR在建筑全生命期中具体有哪些应用呢？后面分别介绍。

# 2VR/AR在建筑全生命期的应用

# 2.1建筑规划与设计阶段

（1） $_ { \mathrm { B I M + V R } }$ 应用

BIMVR在建筑规划与设计阶段最基本的应用是设计方案评审。将设计师、评审人员带入VR场景中，基于VR的特性，便可实现常规看纸质图纸和透过屏幕看BIM模型所达不到的效果。特别是对于决策层以及一些非设计专业人士，VR的沉浸性让他们也能参与进来，发表评价。

体验者通过多种视角对项目进行全方位审视。比如通过飞行漫游视角，在VR场景中查看渲染过后1:1的BIM模型场景，让人们对未来区域的建筑规划方案有更宏观的感知和判断。体验者在漫游途中，还可通过丰富的VR交互手法，对方案进行全方位查看以及局部的修改调整。当有多套建筑规划设计方案供参考时，可通过VR体验，直观的进行方案的评审和比选。

目前针对建筑规划设计阶段，已经有大量的BIMVR软件供选择。比如IrisVR、Enscape、Mars、TwinMotion、Lumion 等。

# （2）BIM+AR/MR应用

与VR不一样，AR/MR的体验场景，不再局限于室内体验区，而是去到了任何地方，比如项目实地现场。从BIM软件中导出模型数据，在项目现场，可通过AR手持设备和MR眼镜等，将模型、图纸等1:1加载在现场。拥有现场临场感的AR/MR体验，对方案沟通效果更好。

如图2所示，在项目现场定位点扫描BIM模型，然后加载模型，设计及评审人员，即可拿着iPad设备，实现AR漫游体验。去到任何一个位置，探查未来完工后的状态。通过MR 眼镜也是同理，只是交互方式从触屏改为手势和语音交互。

![](images/9b2ebf7e9c1b70b5351ce154b2d81fdf9eff651d4c7c428d10136013632c691c.jpg)  
图2项目规划现场加载BIM模型的AR场景截图  
图3当前BIMAR应用开发模式

鉴于ARKit和ARCore发布的时间并不长，且目前可用的AR和MR眼镜设备也很少，针对建筑规划与设计阶段，目前很少见有通用的BIMAR/MR软件。_

Trimble公司基于微软HoloLens推出的 SketchupViewer是一个例子，可以通过

HoloLens浏览操作Sketchup创建的模型。不过大部分BIMAR的应用，在交互体验上还比较鸡肋，多数为定制开发的项目展示性质的定制型项目体验软件。

对于定制开发，目前可用的开发工具及软硬件平台如图3所示。

软件平台 software 开发接口sDK 适配硬件 HardwareUWP(Visual Windows Mixed- • HoloLensStudio) Reality APlsUnity iPhone/iPadiOS ARKitUnreal Android手机Android ARC6reAndroid Other AR GlassesStudio VuforiaXcode

# 2.2工程施工阶段

工程管理的过程，是对管理人员经验和技术的发挥过程，传统工程管理人员依据的工程管理信息媒介是纸质图纸，如今正在逐渐转向电子化、三维模型化，甚至更进一步实现VR、AR化。

工程管理的过程就是多个项目参与方不断沟通的过程。所以，BIMVR/AR/MR作为优秀的沟通工具，大有其用武之地。BIMAR/MR天然适合于施工现场的几乎所有沟通场景。相信再过不久，一系列的基于BIM和AR/MR的应用工具和平台软件将被开发出来，覆盖工程现场管理的方方面面。

# 2.2.1 BIM+VR 应用

VR最早的工程领域应用，侧重在VR沉浸式体验上。通过VR的沉浸感、交互性来发挥其工程教育培训的价值。随着教育培训的不断普及，单纯的VR体验已经不再能满足工程需求，更多深入挖掘BIM和VR价值的应用会不断推向工程现场。常见的BIMVR应用架构如图4所示。

目前 ${ \mathrm { B I M + V R } }$ 在工程施工阶段的应用主要集中在安全管理、质量控制、进度控制及组织协调方面。

![](images/1cd46a224d126274432cd7d9af43a254998fd95c699b0d94ae6a7ce3d0f6505f.jpg)  
图4基于UE4开源引擎的BIMVR软件开发框架  
图5SafetyVR体验使用流程

# （1）安全管理领域

VR安全管理及教育是工程施工阶段最早的落地应用。相比于传统安全培训，VR安全培训的优势不言而喻。将工人置身于施工场景中，依次去体验各类安全事故及应急抢险的流程，在VR中发生伤害、死亡等事故，通过视觉、听觉、触觉反馈，形成心理的震慑作用。

在VR工程安全教育上，国内市场需求更甚于国外，市场空间也更大。或许VR安全教育培训将成为工程现场的标配。部分研发型企业，深入工程管理，不再是停留在面子工程，做出的软件成果对一线工人来讲，有较大的实用价值。以万间SafetyVR为例，SafetyVR的体验流程详见图5。

管理员 工人刷 导出记安全答 VR安  
登录系 身份证 录和成题考核 全体验统 登录 绩

SafetyVR除了常规的安全体验项目，为了让培训效果更具可见性，做了几项技术的集成创新：刷身份证的实名制管理系统、眼球及视线追踪技术精确记录考核分数、成绩管理及分数导出用于备案（图6）、多项目场景及事故抢险类别全覆盖。

![](images/9e1e3a1db6bf58df289778bacc11913b29a419c0a51dbf36a5d67ee37184a947.jpg)  
图6SafetyVR成绩导出界面截图

BIMVR安全管理的进一步落地，将具备将BIM数据实时导入VR场景、安全措施自动规划布置、安全计算功能，VR 事故体验不再是必须的。VR场景BIM数据化，BIM场景VR化，BIM的数据价值将进一步挖掘并凸显。

VR应用于质量领域，首先也是用来做交底和培训考核。特别是对于大型工程的复杂施工部位，在现实场景中很难进行教育培训的。将BIM模型用来搭建VR场景，设置交互流程和考核标准后，即可用来进行培训。以万间SimVRFab为例，一般的制作开发流程如图7所示。

![](images/e246e1a8b133637db387df260661dca7e993770da19032f04f1412a85a39554e.jpg)  
（2）质量控制领域  
图7工艺质量BIMVR应用制作开发流程图

VR培训交底的深度，取决于BIM模型的精细程度，可以做出非常逼真的操作流程，甚至复制现实场景。一般配置的体验方式分为两种：教学模式、考核模式。

工程质量交底和培训是一项高粘性的工作。对于工程师和工人来说，每天都有这方面的需求。所以后面会出现大量信息交互流程更简单，一线BIM工程管理人员也能简单上手的BIMVR质量交底软件，提供给他们使用。除了输出VR体验成果，还可直接导出高清的流程动画视频、高清图（图8），用于方案存档和其他沟通场景。

![](images/8b7cf3a373ad9d6b2dede348761d626f76f355ca5c9866191e8dc6b6eb71a851.jpg)  
图8干挂石材工艺VR培训截图

# （3）进度控制领域

工程进度控制强调事前控制，VDC（Virtual Design and Construction）在国外已经是一个大的学科门类，在企业也是一个复合型的专业岗位。VDC工程师就是利用BIM模型和图纸，来进行施工进度的虚拟仿真、事前控制，排除所能察觉到的所有不合理项、问题点后，再去指导实际的现场施工，降低施工不确定性和返工的人力、资金、时间成本。

对于BIM工程师来说，他只需要将其搭建的BIM模型，导入VR场景，编排好施工进度顺序，做好和虚拟工期时间的精确挂接关系，即可在一个虚拟场景中，完整复现一个未来的施工场景了。管理人员不再仅仅依据自己的施工经验，而是依据BIM模型上精确的材料、成本、人员等数据，通过调节各类资源曲线，用线性规划的方式来寻找到最佳施工进度路线，让进度仿真达到优化施工方案，降低施工不确定性的目的。

![](images/7bc6c0bd57c5c4d12e85b061277cf81a642b485ad9342721811dd77d3e583024.jpg)  
图9进度模拟仿真BIMVR应用操作流程图

VR进度模拟仿真的操作流程，详见图9。

进度流程仿真模拟的精细度，与BIM模型的精细度有关。随着各类信息资源的进一步挂接，可以实现更精确的数据驱动进度流程。同时，在搭建好进度仿真流程后，工程师可以戴上眼镜，进入到VR场景，去对流程的细节进行评审，看虚拟施工方案是否具备可实施性，防止出现局部的流程冲突。随着BIM和VR的进一步融合，通用化的BIMVR软件，将成为现场的工长、材料员等与进度密切相关的管理岗位人员的生产工具。

另外，远程多人同时在线的VR体验，会更加普遍和实用。在VR场景中实现建设单位、施工承包单位、设计单位以及监理单位的远程多方协同沟通。不用去到同一个地方，在VR场景中完成会议或施工进度方案沟通，对工作效率提升、沟通成本节约的作用是极大的。

# 2.2.2 BIM+AR 应用

目前施工管理阶段的BIMAR/MR应用还不是很普遍，不过其与施工现场结合的场景优势，大有超越VR的趋势。BIMAR/MR应用，同样可以应用于工程现场管理的安全、质量、进度及组织协调领域。其沟通的对象不再是纯虚拟的BIM模型，而是BIM模型与现场环境的沟通，也不再是施工管理人员或者工人与模型的沟通，而是多方参与进来完成协调沟通。

BIMAR/MR平台软件开发的路线如图10所示。

![](images/362142c23c63d2fc5b5479a12ff6739345f7ec43cb0627cb659d321918ebe4bb.jpg)  
图10BIMAR应用平台软件开发路线

目前的BIMAR应用主要是基于苹果iOS系统之上ARKit接口开发的，适配苹果最新的手机和iPad系列设备。而基于Android系统之上ARCore的应用还很少，因为目前适配的机型还不多。不过相信过不久，就会有大量的手机和平板设备，都会支持流畅AR的功能，AR体验的成本会大大降低。

而目前的BIMMR应用主要是针对微软HoloLens眼镜而开发的，前不久新出的MagicLeapOne，其在性能和体验上均相对HoloLens有一定的提升，相信它在建筑工程上也会有一定的应用。

以万间Mr.BIM为例，BIMAR/MR在建筑工程施工管理阶段的应用点主要有以下几方面。

# （1）（1）定位漫游

：BIM模型二维码初始定位设置（图11），AR场景漫游及信息查看。（2）（2）虚拟测量放线

：施工图纸、模型分层增强显示，虚拟放线定位，AR量尺准确测量（图12）。

![](images/c1cb3f70050b9199bc13a92afb023e915f775ea7b63741c7e2e2d7e376a0a851.jpg)  
图11AR扫码定位加载BIM模型

![](images/b29625319fa59187edf6ee2f604b3ce60c5f5bc0aea150fe07878aaa34cb987f.jpg)  
图12加载AR图纸  
图13营销阶段BIMVR应用开发流程

（3）（3）现场施工指导

：施工安装流程指导，同步技术交底培训。

（4）（4）质量验收

：图纸、模型与实体结构位置校验，发现并记录质量偏差。

# 2.3项目营销阶段

VR/AR最早在建筑业的应用便是项目营销推广，特别是地产类的项目，VR样板间成为很多项目营销中心的标配。国内外均有大量的创业企业从事针对地产营销的VR内容定制开发服务。

VR/AR以其直观的沟通表达能力，能清楚的将项目特点、优势传达给非专业的客户群体，且让人耳目一新。对于还在施工前期但已开始销售的项目，将BIM模型导入VR/AR引擎，经过精细的渲染调节，辅以一定的交互程序，完整再现建筑工程在完工后的运行状态，精确传达给潜在客户、业主以及广大市民。

# 2.3.1BIM+VR 应用

VR应用主要是VR样板间、VR楼盘、VR展览展示等，将工程项目完工场景通过VR场景展示出来，传递给潜在客户或消费者。

一般的应用流程如图13。

营销需求分 BIM建模及深 VR场景设计 VR体验程序析 化设计 渲染 定制开发

以常见VR 样板间为例，一般整个VR项目营销展示系统包含区域规划VR展示、楼盘VR展示、户型VR交互展示、设计理念、精装场景、家装设计体验等VR展示模块，还与企业展示、平台概览、装修清单、主材介绍、交房标准、服务体系等常规营销内容结合。比如，通过在VR场景中再现未来建筑内的生活场景（如图14，体验智能冰箱的智能买菜功能的VR营销案例），来达到准确营销的目的。

![](images/72577d295c416f98a17e53f0489d3015721b68ac2b5b98692e2c4015f417a9d8.jpg)  
图14海尔智能冰箱VR场景式营销体验

# 2.3.2 BIM+AR 应用

AR/MR在项目营销中的应用与VR类似。AR体验一般是在手机移动应用中集成AR模型展示的功能，通过扫码，然后加载出模型和信息的方式。基于图像识别的AR体验，目前支持几乎所有Android和iOS移动设备。

而需要依赖SLAM实时定位的AR体验，可选方案目前则较少，且对硬件设备性能有要求。所以目前主流且简单的AR应用多为基于图像识别的模式。比如基于VuforiaSDK开发的卡片识别式的AR模型展示体验。

基于苹果ARKit和谷歌ARCore的移动AR应用解决方案是一个主流方向。且有希望做出通用型的AR应用。已经有不少企业在做这方面的尝试，宜家的AR应用IKEAPlace 就是一个典型。IKEAPlace有超过2_000个家具BIM模型（图15），可以让用户充分发挥想象力，在AR中设计自己的空间。

![](images/42ddcf3265dba8d085c1250d10940be5a48678ace4f73dee838a964013101a5e.jpg)  
图15IKEAPlace使用场景

# 2.4运维管理阶段

建筑运维管理指建筑在竣工验收完成并投入使用后，整合建筑内人员、设施及技术等关键资源，通过运营充分提高建筑的使用率，降低它的经营成本，增加投资收益，并通过维护尽可能延长建筑的使用周期而进行的综合管理。

竣工后的建筑或工程物进入长达几十甚至上百年的使用期，都涉及到运营、维护保修、更新等内容。特别是对于机房、工厂等设备密集型建筑，一旦建筑设施发生故障，就需要及时进行维护保修。但由于存在大量的隐蔽工程，且历史的图纸存档资料很难查找，这时候，基于建筑工程的BIM数据的VR/AR/MR应用价值就凸显出来了。

# 2.4.1 BIM+VR 应用

项目在竣工后，交付试运行阶段，可以通过BIMVR场景来进模拟仿真运行的场景，即试运行模拟（VRCommissioning）。以一个生产工厂为例，可以通过VR来精确模拟各类设备运行时的工况。试运行模拟仿真的内容包括：设备运行工况模拟、消防应急演练模拟、典型设备故障应急演练模拟等。

# (2） $\mathbf { V R + I o T }$ 远程操作

VR技术结合建筑工程设施的物联网硬件，可将设备运行的数据，实时在VR场景中可视化。还可以通过在VR场景中操作虚拟硬件设施，将指令传递给建筑中的实际硬件控制器，实现远程控制，如图16所示。对于一些操作危险性较高的设备区域，在VR场景中远程操作，除了提高安全性，还非常简单、直观、便捷。

![](images/9e66e8f3749a8061a2a65ec0a2f43886a893435a77b74b9fb3d638020b523fba.jpg)  
（1）试运行仿真培训  
图 $1 6 { \mathrm { V R } } { + } \mathrm { I o T }$ 应用流程示意图

图17是钢材工厂中通过VR远程操作机床设备的案例。体验者手持控制器，在VR场景中操作虚拟设备，实际控制的却是跟虚拟设备一致的实体建筑设备。且设施设备的实时运行数据，也能够在VR场景中查看，操作员只需要在控制室体验区，即可对整个建筑内所有联机的设备进行控制。

![](images/46c0d85e05fa9093e3c276edfb3ae268d29abda55e1ed9f490c2785368cd3103.jpg)  
图17某工厂通过VR远程控制车间设备

# 2.4.2 BIM+AR 应用

以一个典型案例来介绍AR/MR应用。全球知名电梯厂商 ThyssenKrupp 基于微软HoloLens开发了专门针对其企业的一个 $_ { \mathrm { B I M + M R } }$ 运维检修管理系统。将电梯运行的设备数据联网，并在MR眼镜显示出来，指导现场维修人员，提高工作效率，如图18 所示。

维修人员接收到维修通知，打开MR设备，查看待维修的电梯设备信息及故障状态。然后去到设备所在建筑进行维修操作。

![](images/887a15b743eb637201d2c0462eeb8b1ba7c89b083033775faccab22f9bb78c8c.jpg)  
图18 ThyssenKrupp 基于HoloLens 的 AR应用

在维修过程中，维修人员不需要带任何图纸，所有模型和文档数据信息，均通过MR眼镜增强显示在空间中，所有的隐蔽工程信息也增强显示出来。遇到不能判断的问题时，还可寻求远程协助，将头盔摄像头画面同步给其他人员。

维修完成后，设备运行的实时信息、工单信息都可通过MR眼镜实时查看，并同步到服务器端。整个过程，维修人员通过MR进行信息增强辅助，让传统基于图纸、检测设备和经验的检修流程大大缩短，极大提高工作效率。

类似ThyssenKrupp的BIMMR创新应用可拓展到建筑工程运维管理的各个方面，让AR/MR技术辅助运维人员进行高效率的工作。运维阶段的建筑工程BIM数据是在实时更新的，它们是一套数字虚拟资产，VR/AR/MR 提供了管理人员、业主与数据资产沟通交互的媒介，让数据资产在运维管理全生命期发挥价值。

# 3BIMVR/AR的发展趋势分析

# 3.1 发展趋势

BIMVR/AR/MR在建筑全生命期都有非常重要的应用，在一些沟通密集领域，它们有机会成为替代性或者颠覆性的沟通管理技术。当然，BIMVR/AR/MR技术还不够成熟，技术的进一步落地，还需要大量的创新研发和探索。建筑业新的管理沟通范式的形成，也不是一蹴而就的。

BIMVR/AR/MR发展路线如图19所示。对于建筑业来讲，特别是工程施工阶段，AR/MR的应用场景，远远高于VR场景。但凡需要沟通的地方，几乎都可以用到AR/MR代替传统低效率的沟通方式。当前，BIMVR的发展已经具备一定的成熟度，BIMAR应用正在崛起，BIMMR应用则还才少量试点型应用。BIMMR是最方便便捷的应用方式，随着软件开发成本降低，MR硬件逐渐成熟和大众化，BIMMR应用或许将统治整个施工现场，MR穿戴设备或将跟安全帽一样，成为建筑业工程人员的标配。

![](images/66b83fc3da04925b73065f15ebd6b5f0fa14c706545f43e1d213583b022f2ffb.jpg)  
图19BIMVR/AR/MR发展路线

在AR/MR硬件成本降低、性能提升后，应用的分发也将更加简单。随着5G通信技术的普及，BIM模型数据的实时传输不再是问题，BIMAR/MR也从早期的单机软件应用，到后面不断云化，用户通过纯Web应用，即可完成现场的沟通体验流程，形成小前端（AR/MR设备端）、大后台（云端）的应用模式。

会有越来越多的工具级BIMVR/AR/MR软件及平台出现，覆盖到工程的各个细分领域，特别是这些与基于BIM模型的沟通密切相关的领域。

# 3.2障碍与突破点

VR/AR/MR在建筑业的发展障碍是多方面的，主要有以下几方面：

（1）行业从业群体素质较低，对新技术采纳缓慢；。

（2）BIM技术发展缓慢，BIMVR/AR/MR的普及应用，或多或少会受到 BIM落地缓慢的影响；。

（3）VR/AR/MR硬件技术及成本离普及应用尚有较大差距。

建筑业利润率普遍很低，如果新技术的引入，能给项目管理降费、提质、增效带来价值，整个行业都会欣然接受新技术。BIMVR/AR/MR的普及应用突破点有两个：

（1）VR/AR/MR硬件成本的降低和性能提升；

（2）刚需型、易用型BIMVR/AR/MR应用软件出现。

# 参考文献

[1]BIMVR-百度百科, https://baike.baidu.com/item/BIMVR

[2]BIMAR-百度百科，   
https://baike.baidu.com/item/BimAR/22415   
490?fr=aladdin

[3]范式-百度百科， https://baike.baidu.com/item/%E8%8C%83 %E5%BC%8F/22773?fr=aladdin

【作者简介】-刘勇（1991一），男，硕士研究生，万间科技（深圳）有限公司总经理，BIM产品经理，从事-BIM与VR/AR结合的软件开发和技术研究工作。

# Application of VR and AR in the field of construction informationization

Liu Yong

（， Shenzhen 518000,China）

Abstract: Virtual reality, augmented reality and mixed reality are emerging multi-dimensional visual communication technology, which has been widely used in various fields. The combination with BIM in construction industry can give full play to both of their advantages and complement each other. There is a great value space to explore during the entire life cycle of the building. Starting from the basic theory, this paper deeply discusses the application of BIMVR/AR technology in the stage of architectural planning and design, engineering construction, project marketing, operation and maintenance management, from application demand, landing application mode,application status quo, to the future development direction and potential.In the end, we analyze the obstacles and breakthroughs in the further development of this technology.

Keywords: BIM; Virtual Reality; Augmented Reality; BIMVR; BIMAR