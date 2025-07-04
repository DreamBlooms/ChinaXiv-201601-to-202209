# 深空探测天文自主导航技术综述

薛喜平1,2,3，张洪波1,²，孔德庆1,2（1．中国科学院月球与深空探测重点实验室，北京 100012；2.中国科学院国家天文台，北京 100012；3．中国科学院大学，北京100049)

摘要：自主导航技术在提高深空探测器自主生存能力、减轻地面测控负担、完成探测任务特殊阶段导航等多方面具有明显的优势，已经成为世界各国研究的热点。我国火星探测工程已经启动，将来还有其他小行星、彗星和行星及其卫星的探测计划。详细阐述了发展天文自主导航技术的必要性，阐述天文导航技术的基本原理及优势，并对国内外深空天文自主导航技术以及应用情况进行概述，总结了发展天文自主导航的关键技术。根据分析提出我国发展深空探测自主导航技术的建议与思考。

关键词：天文导航；自主导航；深空探测

图分类号：P173.4 文献标识码：A 文章编号：1672-7673(2017)03-0382-10

随着人类探索太空能力的不断增强，深空探测已成为航天领域的热点。对小行星、彗星、行星及其卫星等天体的探测是人类认识地球、了解太阳系和宇宙起源的重要途径，也是发展空间科学、提高空间技术的必经之路。深空探测距离远，巨大的通信时延不利于突发情况以及探测器故障的处理，探测器的生存面临巨大风险。自主导航技术能够在地面通信中断时，继续完成轨道确定与姿态调整，提高探测器的空间生存能力。未来深空探测任务不断增多，探测周期长，单靠地面测控导航需要占用大量的地面测控资源，采用自主导航技术可以大大降低地面测控负担。此外，自主导航在深空探测任务的某些特殊阶段尤为重要，如伴飞、飞越、着陆和撞击阶段等，这些阶段需要精确知道探测器的位置、速度和姿态等信息，然后开展相应的导航和控制措施[1]，传统的地球测控方式时延太大，导航精度和时效性不能满足这些特殊任务阶段的需求。

综合分析，自主导航技术在提高探测器生存能力、节约地面测控资源和满足任务特殊阶段导航需求等多方面具有明显优势。所以，发展探测器自主导航是一项亟待解决的关键技术，世界各国在积极探索研究。天文自主导航具有全自主、高精度、误差不随时间积累、抗干扰能力强、可提供位置和姿态信息等优点，是目前广泛应用的自主导航方法[1-2]。本文对深空天文自主导航技术的原理、优势、国内外研究进展和应用情况进行了概述，分析发展天文自主导航的难点与关键技术，并提出我国发展深空探测自主导航技术的建议。

# 1天文导航技术原理及优势

广义天文导航的定义是以太阳、月球、行星和恒星等自然天体作为导航信标，以天体的地平坐标（方位或高度)作为观测量，确定测量点地理位置(或空间位置)及方位基准的技术和方法[2-3]。天文导航的基本原理是利用星上敏感器获取的测量信息，自主确定探测器的姿态和位置，为深空探测器自主运行提供参考标准，自主给出控制指令，完成探测器空间状态的改变[4]。

国外深空探测任务多采用星光导航技术，另一种是基于射电信号的自主导航，比如：X射线脉冲星。由于脉冲星数量较少，且测量精度无法保证，目前还处于研究探索中，距离实际应用还有一定距离[5-6]。天文星光导航设备大致可以分为3个模块：导航信息采集模块（主要由星敏感器完成）、导航信息处理模块和导航控制模块。其中导航信息采集模块接收测量信息采集指令，进行星体拍照等导航信息的采集，发送给导航信息处理模块。导航信息处理模块分析与提取可用观测数据，并结合探测器原有姿态与位置，自主计算探测器下一时刻的姿态与位置，并完成星历修正。根据更新后的导航信息和星历表进行下一时间段的轨道规划，并计算探测器进行轨道机动所需的动力及姿态指令，将其发送给导航控制模块。导航控制模块的功能是根据指令完成轨道机动与姿态调整。天文导航系统组成如图1。

![](images/e183fdd4555a9c0599f6151ca15e14728be99608101485b18d072ebd5e982208.jpg)  
图1天文导航系统组成  
Fig.1Composition of celestial navigation

天文星光导航根据星敏感器获取信息的对象不同，大致可以分为3类：第1类是基于恒星的自主导航；第2类是基于太阳和行星的自主导航；第3类是基于小行星或者行星卫星的自主导航。恒星的发射光很弱，星敏感器容易受杂散光的干扰，对成像质量影响很大，影响恒星敏感器观测的杂光大致有太阳光、月球反照光、地球反照光、本体反照光、空间垃圾反照光等。这些杂光不仅影响星像的信噪比，甚至可能使敏感器不能正常工作。行星亮度高，但是数量太少，探测器能够观测到的机会有限，并且导航精度随探测器与太阳、行星之间距离的增加而降低。行星卫星数量较多，但是都围绕行星运行，不适合用于导航。彗星的彗核被彗发包裹，从图像中提取彗核中心比较困难。小行星数量众多，而且与探测器距离较近，成像可近似为点光源，导航精度相对较高，是深空探测自主导航的理想观测天体。深空1号巡航段的自主导航是基于导航相机拍摄带有恒星背景的小行星图像完成的。在整个巡航过程中，自主导航的位置精度达到 $2 5 0 \mathrm { k m }$ ，速度精度达到 $0 . 5 ~ \mathrm { m / s }$ ，完全满足巡航段对精度的要求。文[7-10]开展了小行星自主导航的研究与仿真，利用统计的蒙特卡洛仿真方法计算，导航的位置误差为 $9 0 . 2 5 ~ \mathrm { k m }$ ，速度误差为 $0 . 1 6 ~ \mathrm { m / s }$ ，相比深空1号飞行试验的自主导航误差（位置 $2 5 0 ~ \mathrm { k m }$ 、速度 $0 . 2 \mathrm { m / s }$ )好得多。

天文导航以自然天体为导航信标，不需要地面无线电设备参与，安全性和隐蔽性强，可以同时提供导航位置和姿态信息。天体辐射覆盖了X射线、紫外线、可见光和红外线整个电磁波谱，天文导航具有极强的抗干扰能力，不仅适用于空间导航，也同样适用于陆地和海洋，应用空间广泛。导航误差不随时间积累，是自主导航的重要特点，仅利用探测器姿态敏感部件星敏感器和红外地平仪，而不需额外增加其他硬件设备，设备简单，造价低，导航精度高，便于推广应用。

# 2国内外天文自主导航技术发展现状与应用

天文导航技术具有悠久的历史，1875年法国航海家 Saint-Hillarie创立了高度差原理，标志着天文导航理论的诞生。当时采用高度差原理，以六分仪为观测仪器，用《航海天文历》查看天体视位置，《天体高度方位表》计算天体的高度和方位，利用天体对舰船实施导航的方法，作为一种基本的海上导航技术(天文航海技术)应用至今。

20世纪60年代，国外开始大规模组织科研人员研究探测器的自主导航技术与方案。天文导航技术在历次任务中通过不断验证和改进，在观测仪器、导航信息获取和处理、系统状态模型以及滤波方法上不断发展、成熟与完善。天文导航最初的作用是辅助地面测控完成探测器导航任务，近年来，实现了完全依靠天文导航实现探测器自主导航。表1总结了自主导航技术在几次典型探测任务中的应用情况。

表1深空探测任务中的自主导航技术应用  
Table 1 Applications of autonomous navigation technology in deep space exploration   

<html><body><table><tr><td>Time</td><td>Mission</td><td>PP Nation</td><td>Application description of astronomical navigation technology</td><td>Star sensor</td></tr><tr><td>1968/12</td><td>Appollo 8</td><td>USA</td><td>In the phase of the moon,the celestial navigation is only used as an auxiliary means to verify the correctness of the track[11].</td><td>Sextant</td></tr><tr><td>1971/5</td><td>Mariner 9</td><td>USA</td><td>With the help of celestial navigation，the probe successfully entered the orbit of Mars；it is proved that only through the celestial navigation can complete the navigation task[12].</td><td>Optical camera</td></tr><tr><td>1996/2</td><td>NEAR</td><td>USA</td><td>The detector independently calculates the position of the sun, the earth,the asteroid and the detector,and adjusts the attitude of the spacecraft[13]</td><td>Optical camera</td></tr><tr><td></td><td>1998/10Deep Space 1</td><td>USA</td><td>Deep Space 1 is the first successful implementation of autonomous navigation task in the cruise phase by dependent photo sequence planning，image extraction，observation and phase element from the image，and orbit analysis，determination and atitude maneuver and orbit correction [14-15].</td><td>Navigation camera</td></tr><tr><td>1999/2</td><td>Stardust</td><td>USA</td><td>To obtain the image processing center extraction technology using autonomous navigation system， get the center point of the object，combined with the detector atitude information and filtering techniques，to determine the orbit and atttude control system，through the interface，proactive atitude maneuver，in order to maintain the navigation camera locked nucleus [16].</td><td>Optical camera</td></tr><tr><td>2003/5</td><td>Hayabusa</td><td>Japan</td><td>Rendezvous and landing asteroid stage through the processing of navigation cameras,laser range finder and navigation signs and other measurement information to determine the orbit of the detector，and to complete the track control[17].</td><td>Navigation camera、Laser range finder</td></tr><tr><td>2004/3</td><td>Rosetta</td><td>Esa</td><td>The measurement information of the satellite borne camera and the ranging radar are processed to determine the trajectory of the detector[18]</td><td>Navigation camera、radar</td></tr><tr><td>2005/1</td><td>Deep Impact</td><td>USA</td><td>Based on the image and attude information of the target comet, the navigation sensor is used to realize the autonomous navigation and control before the collision[19]</td><td>Navigation camera</td></tr><tr><td>2005/8</td><td>Mar Surveyor</td><td>USA</td><td>In the process of navigation camera close to Mars，Mar Surveyor using the two satellite images and ephemeris information，to achieve autonomous navigation [20].</td><td>Navigation camera</td></tr></table></body></html>

除上述已经发射的深空探测器外，许多深空探测计划也提出了应用自主导航与控制技术。比如,欧洲空间局曙光载人深空探测计划提出了自主导航技术[21]。欧洲空间局的撞击小行星计划（DonQuijote)拟在接近和撞击阶段实现自主导航与控制技术[22]。美国国家航空航天局的火星取样返回（Mars Sample Return，MSR)和火星遥控轨道器（Mars Telecom Obiter，MTO)计划执行深空接近和交会对接的自主导航与控制技术的演示验证[23]。

我国嫦娥三号探测器于2013年12月2日发射，经过5天的飞行，首次成功利用自主导航实现月球软着陆自主避障[24」。利用光学成像敏感器获取着陆区光学图像，根据着陆器对月面的高度和太阳光照条件，依据图像灰度进行月面二维形状恢复，识别大的障碍物，并据此寻找安全着陆点。

# 3天文自主导航关键技术

天文导航涉及的关键技术有：天体筛选与规划、高精度星敏感器技术、导航信息的获取与处理技术、导航滤波技术以及仿真验证技术。目前，我国的天文自主导航技术还处于研究阶段，要发展天文自主导航技术，应该对以下关键技术进行研究。

# 3.1 导航天体筛选与规划

实现自主导航，首先要识别并筛选适合的导航星体，文[25]提出的小行星筛选准则为小行星与探测器的距离、相对速度以及探测器-太阳-小行星相角；文「26]在筛选时考虑了小行星的视星等和小行星所在星空域的属性。文[7]在前人基础上提出了两颗导航小行星间的视线夹角的准则。根据深

空探测任务的需求和典型深空导航成像敏感器的性能等，文「7-8给出了导航天体的一般选取标准(见表2)。天文自主导航要完成轨道确定与定位，需要观测多颗小行星。选择观测不同的小行星组合，导航定位精度也不同。文[8]提出了基于滤波协方差的小行星组合分析方法，给出了一种可量化的选取最优小行星组合的方法。在设计自主天文导航方案时，根据小行星筛选标准及优化组合方式，选定一批导航小行星，建立导航星体数据库。星体数据库本质上是一份星历表，它含有一组选定的恒星或行星位置、运动和星图等信息，供探测器飞行过程中规划导航路线使用。

表2导航小行星筛选准则[7-8]  
Table 2Navigation asteroids selection criteria[7-8]   

<html><body><table><tr><td>Parameters</td><td>Range</td></tr><tr><td>Apparent magnitude</td><td><12</td></tr><tr><td>Solar angle/°</td><td>>135</td></tr><tr><td>Relative velocity of asteroid and detector(KM/s)</td><td><7</td></tr><tr><td>Distance of asteroid and detector/km</td><td><1000 000</td></tr><tr><td>The angle of view of the two navigation asteroids/°</td><td>>5</td></tr></table></body></html>

# 3.2高精度星敏感器技术

导航星敏感器是深空天文自主导航系统的关键部件，要求测量精度高、灵敏度高、动态范围大、体积小、重量轻。因此，星敏感器制造时在光学、结构、机构、热控和杂光消除等方面具有极其严格的要求。星敏感器大致分为两类：（1)基于CCD 图像传感器的星敏感器，自70 年代美国研制出CCD相机起，CCD 图像传感器一直作为主流的星敏感器应用，比如德国 Jena-Optronik 的 ASTRO 系列、法国的 SODERN 系列和美国 Lockheed Martin的 AST-301等。美国AST-301敏感器在没有任何先验信息的条件下，全天任何地方3s内成功获得姿态的概率为 $9 9 . 9 8 \%$ 。(2)基于互补金属氧化物半导体（Complementary Metal Oxide Semiconductor，CMOS）的先进摄影系统（Advance Photo System，APS）星敏感器，与CCD 星敏感器相比，APS 星敏感器具有较宽的视场，可获得更多较亮的导航星，星敏感器星等阈值可以降低，光学部分的重量减轻，导航星表的容量减少，逐渐成为国际上星敏感器供应商主要研究的技术。

近年来，国内研究人员也在不断探索研究，在硬件研发、软件算法设计、参数标定和模拟仿真等方面做了很多工作[27]。目前，已经研制完成基于像素数为 $1 0 2 4 \times 1 0 2 4$ 的 APS 敏感芯片的分体式APS 星敏感器，在探月三期月地高速再入返回飞行器导航、制导与控制试验子系统中成功实现了首次在轨飞行实验，在轨姿态捕获时间小于1s[28]。

在世界各国的深空探测任务中，应用较典型的星敏感器主要是光学相机或者导航相机。表3汇总了国外一些典型应用的星敏感器参数指标。

# 表3典型应用的星敏感器参数指标[16-17,29-31]

Table 3The typical application of star sensor parameters[16-17,29-31]   

<html><body><table><tr><td>Missions</td><td>Star sensor</td><td>Focuse</td><td>Field of view</td><td>Resolution</td></tr><tr><td>Deep Space 1</td><td>Optical camera 1</td><td>677 mm</td><td>0.76°</td><td>1024 ×1024P</td></tr><tr><td rowspan="3">Rosetta</td><td>Optical camera 2</td><td>677 mm</td><td>0.26</td><td>256 × 256P</td></tr><tr><td>Camera with Narrow field of view</td><td>1</td><td>2.4°</td><td>2 048 ×2048P</td></tr><tr><td>Camera with Wide field of view</td><td>一</td><td>12°</td><td>2 048 ×2048P</td></tr><tr><td>Stardust</td><td>Optical camera</td><td>200 mm</td><td>3.5°</td><td>1024 ×1024P</td></tr><tr><td>Hayabusa</td><td>Optical camera 1</td><td>1</td><td>5.7°</td><td>1024 ×1024P</td></tr><tr><td rowspan="3">Deep Impact</td><td>Optical camera 2</td><td>一</td><td>60°</td><td>1024 ×1024P</td></tr><tr><td>MRI camera</td><td>2.1m</td><td>0.57°</td><td>1024×1024P</td></tr><tr><td>HRI camera</td><td>10.5 m</td><td>0.12°</td><td>1024 ×1024P</td></tr></table></body></html>

# 3.3导航信息的获取与处理技术

导航信息的自主获取与处理是实现自主导航与控制的前提。图像的获取与处理算法是核心，是提高导航精度以及导航效率的关键环节。目前，存在着星点提取时间长、内部星表存储量大等缺点。因此，快速捕获和星表压缩算法的改进成为首要的研究对象。美国喷气推进实验室“星尘”号[16]探测器的导航图像，经过去噪声处理，图像畸变分析与校正，根据中心点提取技术得到目标天体的中心质点，然后根据小天体中心的图像信息和探测器的当前姿态信息，利用滤波估计算法得到探测器在空间的位置与速度。该技术在旅行者号与飞越天王星和冥王星相遇时也得到了验证。文「30]提出了一种基于高斯曲面拟合的星体质心提取方法，经过半球物理仿真实验表明，这种方法的提取均值误差非常接近理论值。文[28]提出了一种星点聚类提取方法，该方法通过预处理逻辑提取有效像元，减少软件处理的像元数，并采用4个聚类判据将有效像元按星点不同划分，在完成星敏感器姿态捕获模式下星点提取的同时，减小了星图存储空间和星点提取时间，达到了星敏感器优化的目标。在探月三期月地高速再人返回飞行器GNC试验子系统中配置了APS 星敏感器，图像处理时应用星点聚类提取方法，在轨姿态捕获时间小于1s，星点提取所需时间约为传统方法的 $1 6 \%$ ，像元存储所需空间约为传统方法的 $1 \%$ ，大大减小了星敏感器星图存储空间和姿态捕获模式星点提取时间。

由星体匹配发展到区域星图匹配，能实现更高的天文导航测量精度。在星图匹配方面，目前较常用的算法有三角形匹配算法、多边形角距匹配算法、主星识别算法等。它们在星空覆盖、数据库配置大小、噪声稳定度和匹配速度上各有优劣[32]。文[33]针对3种算法匹配成功率低的问题，提出了在地球物理领域广泛使用的三角网络部分算法进行星图识别匹配，还提出一种基于豪斯多夫（Hausdorff [33]距离的星图识别法，以及改进Hausdorff 距离的星图识别法。

# 3.4导航滤波技术

导航滤波方法主要有两种：（1)基于轨道动力学方程的滤波方法；（2)纯天文的几何解析方法。前者利用天文量测信息结合轨道动力学方程，通过最优估计的方法得到深空探测器的导航信息；后者利用天文量测信息，根据深空探测器与天体间的几何关系，通过几何解析得到深空探测器的导航信息。常用的滤波算法有扩展卡尔曼滤波算法和无迹卡尔曼滤波算法。由于深空环境中滤波模型和各种环境干扰等不确定性较大，导航滤波算法可能出现发散现象，需要研究与不确定因素自适应的导航滤波算法[4]

# 3.5姿态测量技术

星敏感器通过其光学系统测量天球上不同位置的星体，得到观测星图，并与由星表数据库产生的导航星图进行特征匹配，实现对空间飞行器的三轴姿态的测量。三轴姿态测量是利用卫星上的姿态敏感器测量所得的信息，经过适当的处理，求得固连于卫星本体的坐标系相对空间某参考坐标系中的姿态。姿态确定的输入信息是姿态敏感器的测量数据，输出是卫星的三轴姿态参数。

文[34]提出了利用高精度陀螺为星敏感器提供连续的三轴姿态信息，再通过积分运算可以得到姿态角信息。利用陀螺的测量输出对星敏感器进行实时补偿，以确保姿态测量元件在轨工作精度。仿真结果表明，星体姿态角估计误差优于 $0 . 0 0 0 \ 5 \ \mathrm { r a d }$ 。文［35]提出了一种基于径向准直约束（RadialAlignment Constraint，RAC)的星敏感器在轨姿态测量方法。该方法不依赖外部姿态信息，通过建立基于径向准直约束的星敏感器成像模型，采用两步法从单帧星图解算外部参数和内部参数，并利用多帧星图整体优化的方式得到内部参数的整体最优解。仿真实验表明，该方法能准确解算内外参数，其残差在 $x$ 方向为0.063 像素，在y方向为0.053像素。

# 3.6 仿真验证技术

为了验证深空探测器自主姿态与轨道控制技术的有效性、可行性和实用性，必需针对探测任务建立完善的地面仿真试验验证系统。通过地面仿真和试验，对自主导航系统的功能、性能、导航精度和关键技术进行验证，检验方案设计和数学模型的正确性，是深空探测自主导航与控制技术能够转入工程实施的前提条件。

文[36]提出借助星场模拟器进行仿真测试，基本方法是用星场模拟器仿真无穷远的星空，星敏感器通过观测仿真的星空图像进行识别和姿态计算。该方法的缺点在于星场模拟器价格昂贵，且星场模拟器参数、视场和口径等不可调，很难与星敏感器参数完全匹配。文「37]提出了外场观星测试，即在实际星空下进行测试，该方法简单易行，但是受天气等因素影响较大，无法保证随时测试的需求，也无法模拟星敏感器的在轨状态。但是，以上两种方法均无法用于空间环境试验和整星联调阶段的功能测试。对此，文[37]提出基于仿真星图的星敏感器地面功能测试方法，该方法以全幅仿真星图作为测试信号源，可以实现对星敏感器星点定位、星图识别、姿态计算等功能的全面测试。

文「38-41]对月球软着陆制动段、接近段和着陆段的飞行动力学模型进行研究，提出了下降轨道参考系和月心赤道惯性系下的两种均匀球体模型，进行制导律优化设计以及飞行轨迹的计算分析，根据仿真和计算结果制定了嫦娥三号探测器月球软着陆全过程自主导航方案。嫦娥三号探测器月球软着陆的成功证实了仿真计算的必要性和有效性。

# 4结论与展望

天文自主导航技术在国外许多探测任务中已经得到成功应用，成为未来深空探测的必然趋势。由于地理及政治因素的影响，我国的测控资源及测控覆盖率非常有限，在未来深空探测发展规划中，与其他国家相比，发展自主导航技术显得尤为重要。因此，加强天文导航技术人才的培养，加快天文导航技术的研究能力，为我国未来深空探测活动做好技术储备。除了文中提到的关键技术外，还应着重开展以下两方面的研究。

# 4.1多维导航信息的融合技术

随着深空技术的发展，未来单一的导航技术可能无法满足系统要求，将天文导航与其他方法相结合构成组合导航系统，实现优势互补，提高导航系统的精度。根据星图、测距、多普勒频移、脉冲星导航、惯性导航器件等传感参数，利用广义滤波、广义融合等算法，实现深空探测器位置及运动参数的准确解算。未来还可以通过建立太阳系内高精度引力场模型以及太阳风压模型，融合其他导航技术，进一步提高探测器的导航精度。

# 4.2通信与导航一体化技术

一体化信号采用伪码扩频体制，扩频伪码既用作扩频码，也用作测距码，再加入一些与定位有关的参数与信息，加上必要的时间刻度、卫星轨道以及传输途径中的时延误差计算有关参量，就能实现伪距测量。一体化的通信系统不仅具有通信能力，而且还有测量伪距和定位的能力，其信号结构主要由电文、扩频码和载波组成。导航与通信一体化后，信号频谱拓宽，功率谱密度大大降低。解扩后的中频信号带宽较窄，进入中频滤波器的干扰和噪声功率被降低，使解调器输入端的信噪比提高，提高了系统的抗干扰能力，对提高深空探测器远距离、长时延情况下的高精度测距和授时技术有极大帮助。

# 参考文献：

[1］王大轶，黄翔宇.深空探测自主导航与控制技术综述［J].空间控制技术与应用，2009，35(3):6-12.Wang Dayi，Huang Xiangyu. Survey of autonomous navigation and control for deep spaceexploration[J].Aerospace Control and Application，2009，35(3）:6-12.  
[2] 王安国.现代天文导航及其关键技术［J]．电子学报，2007，35(12)：2347-2353.Wang Anguo. Modern celestial navigation and key techniques [J]. Acta Electronica Sinica,2007，35(12): 2347-2353.  
[3] 崔平原，徐瑞，朱圣英，等.深空探测器自主技术发展现状与趋势［J]．航空学报，2014,35(1):13-28.Cui Pingyuan，Xu Rui， Zhu Shengying，et al. State of the art and development trends of on-board autonomy technology for deep space explorer [J]. Acta Aeronautica et Astronautica Sinica,2014，35(1) : 13-28.  
[4] 房建成，宁晓琳，田玉龙.航天器自主天文导航原理与方法［M].北京：国防工业出版，2006.Fang Jiancheng，Ning Xiaolin，Tian Yulong. Principle and method of autonomous celestialnavigation system ［M].Beijing：National Defense Industry Press，2006.  
[5] 郑伟，孙守明，汤国建.基于X射线脉冲星的深空探测自主导航方法［J].中国空间技术，2008(5): 1-6.Zheng Wei， Sun Shouming，Tang Guojian. Principle of deep space autonomous navigation basedon X-rays pulsars [J]. Chinese Space Science and Technology，2Oo8(5）:1-6 .  
[6] 唐云秋，孔德庆.基于深空探测器下行信号的太阳风观测及通信链路的影响综述［J］．天文研究与技术，2015，12(3)：355-363.Tang Yunqiu， Kong Deqing. A review of observations of solar winds and solar impact on dep-space telecommunications using downlink signals from space probes [J]. Astronomical Research& Technology，2015，12(3）：355-363.  
[7] 徐文明，崔祜涛，崔平远，等.深空自主光学导航小行星筛选与规划方法研究［J].航空学报，2007，28(4):891-896.Xu Wenming， Cui Kutao, Cui Pingyuan，et al. Selection and planning of asteroids for deep spaceautonomous optical navigation [J]. Acta Aeronautica et Astronautica Sinica，2O07,28(4） : 891-896.  
[8] 张晓文，王大轶，黄翔宇.深空自主光学导航观测小行星选取方法研究［J].宇航学报，2009，30(3) : 947-952.Zhang Xiaowen，Wang Dayi，Huang Xiangyu. Study on the selection of the beacon asteroid inautonomous optical navigation for interplanetary exploration ［J]. Journal of Astronautics，2009,30(3): 947-952.  
[9] 王大轶，黄翔宇.深空探测转移段光学成像测量自主导航及仿真验证技术［J].控制理论与应用，2014，31(12)：1714-1722.Wang Dayi, Huang Xiangyu. Autonomous optical navigation for deep space transfer phase and itssimulation verification[J]. Control Theory & Applications，2014，31(12）:1714-1722.  
[10］朱佳丽．尘埃三维蒙特卡洛辐射转移模型述评［J]．天文研究与技术，2016,13(4)：392-2n0

Astronomical Research & Technology，2016，13(4）: 392-399. [11] Battin R H.An introduction to the mathematics and methods of astrodynamics ［M].American Institute of Aeronautics and Astronautics，1999. [12] Duxbury T C，Born G H,Jerath N. Viewing photos and demos for navigation mariner 9[J]. Journal of Spacecraft and Rockets，1972，11(4) : 215-222. [13] Miller JK，Williams BG，Bollman W E.Navigation of the NEAR earth asteroid rendezvous mission [J]. Advances in the Astronautically Sciences，1995(89) : 243-265. [14] Bhaskaran S,Desai S D, Dumont P J,et al. Orbit determination performance evaluation of the deep space 1 autonomous navigation system [C]. Proceedings of the AAS/AIAA Space flight Mechanics Meeting，1998. [15] Bernard K，Jay M，Robert D. The deep space program science experiment mission（DSPSE) astrodynamics mission planning [C]. The 44th International Astronautically Federation Congress， 1993:16-22. [16] Bhaskaran S，Riedel JE，Synnott S P.Autonomous nucleus tracking for comet/asteroid encounters : the stardust example [C]. IEEE Aerospace Conference proceedings，1998,2(2）: 353-365. [17] Kubota T,Hashimoto T, Kawaguchi J,et al. Navigation guidance and control of asteroid sample return spacecraft: MUSES-C [C]// Schuirmann B. Proceedings of 4th ESA International Conference on Spacecraft Guidance. Navigation and Control Systems，2001，425(425） : 511. [18] Champetier C，Régnier P，Lafontaine JD.Advanced GNC concepts and techniques for an interplanetary misson [C].Proceedings of the Annual Rocky Mountain Guidance and Control Conference，1991:433-452. [19] Nikos M，Daniel G K，Stephen P S.Autonomous navigation for the deep impact mission encounter with comet temple 1 [J]. Space Science Reviews，2005，117(1） :95-121. [20] 马鹏斌，宝音贺西，沐俊山.利用火星卫星光学测量实现火星探测器自主导航［J]．光学 精密工程，2014，22(4)：863-869. Ma Pengbin，Baoyin Hexi，Mu Junshan. Autonomous navigation of Mars probe based on optical observation of Martian moon [J]. Optics and Precision Engineering，2014,22(4）: 863-869. [21] Marini A E,Racca G D,Foing B H. SMART-1 technology preparation for future planetary missions [J].Advances in Space Research，2002，30(8）: 1895-1900. [22] Misu T,Hashimto T,Ninomiya K. Optical guidance for autonomous landing of spacecraft [J]. IEEE Transactions on Aerospace and Electronic Systems，1999,35(2) : 459-473. [23] Johnson A E，Cheng Y，Mathies L H. Machine vision for autonomous small body navigation [C]. IEEE Aerospace Conference Proceedings，2000，7:661-671. [24] 张洪华，梁俊，黄翔宇，等.嫦娥三号自主避障软着陆控制技术［J]．中国科学：技术科 学，2014，44(6): 559-568. Zhang Honghua，Liang Jun，Huang Xiangyu，et al. Autonomous hazard avoidance control for Chang'E-3 soft landing [J]. Scientia Sinica Technologica， 2014，44(6): 559-568. [25] Delavault S,Berthier J,Foliard J. Optical navigation to a near Earth object [C]// Proceedings of the 18th International Symposium on Space Flight Dynamics，2004：467. [26] Chausson L，Elavault S. Optical navigation performance during interplanetary cruise [C].17th ISSFD，2003. [27] 刘鹏.CCD 星敏感器关键技术的研究［D].哈尔滨：哈尔滨工业大学，2012.

Liu Peng.Research on key technologies of CCD star sensor [D].Harbin：Harbin Institute ofTechnology，2012.  
[28] 王龙，杨孟飞，钟红军.星敏感器星点聚类提取方法［J].中国科学：技术科学,2015,45(3): 257-262.Wang Long，Yang Mengfei, Zhong Hongjun，et al. Star extraction based on clustering within astar tracker [J]. Scientia Sinica Technologica，2015，45(3）: 257-262.  
[29] Riedel JE，Bhaskaran S,Desai S，et al. Deep space 1 technology validation report-autonomousoptical navigation ［M]. JPL Publication，2000.  
[30] Thomas N，Keller H U，Arijs E，et al. OSIRIS-the optical spectroscopic and infrared remoteimaging system for Rosetta Orbiter [J]. Advances in Space Research，1998，21(11）: 1505-1515.  
[31] Owen W M,Mastrodemos Jr N,Rush B P,et al. Optical navigation for deep impact [C]. TheProceeding of the AAS/AIAA Space Flight Mechanics Meeting，2006.  
[32] 田玉龙，金伟，王广君.星图识别的剖分算法［J]．系统工程与电子技术，2004，26(11)：1675-1679.Tian Yulong，Jin Wei，Wang Guangjun. Star map identification algorithm based on cuttingalgorithm [J]. Systems Engineering and Electronics，2004，26(11）: 1675-1679.  
[33] 王广君，房建成．基于Hausdorff距离的星图识别方法研究［J]．北京航空航天大学学报，2005，31(5) : 508-511.Wang Guangjun，Fang Jiancheng. New star patern recognition approach based on Hausdorffdistance [J]. Journal of Beijing University of Aeronautics and Astronautics，2OO5，31(5） : 508-511.  
[34] 金伟，王广君，房建成．一种基于HD距离的改进星图识别算法［J]．北京航天航空大学学报，2006,32(1):8-12.Jin Wei，Wang Guangjun，Fang Jiancheng.Improved star map identification algorithm based onHaustorff distance [J]. Journal of Beijing University of Aeronautics and Astronautics，2006,32(1):8-12.  
[35] 钟红军，杨孟飞，卢欣．星敏感器标定方法研究［J]．光学学报，2010，30(5）：1343-1348.Zhong Hongjun，Yang Mengfei，Lu Xin. Calibration method of star sensor ［J].Aata OpticaSinica，2010，30(5):1343-1348.  
[36] 张延顺，王海，陈家斌，等.卫星三轴姿态确定系统的光纤陀螺/星敏感器组合技术研究[J]．中国惯性技术学报，2003，11(2)：1-4.Zhang Yansun，Wang Hai，Chen Jiabin，et al. FOG/Star-sensor combination tecnology forsatellite three-axis atitude determination ［J]. Journal of Chinese Inertial Technology，2003,11(2): 1-4.  
[37] 孙高飞，张国玉，郑茹，等.星敏感器标定方法的研究现状与发展趋势［J］．长春理工大学学报：自然科学版，2010,33(4)：8-14.Sun Gaofei, Zhang Guoyu，Zheng Ru，et al. Star sensor calibration research and development[J].Journal of Changchun University of Science and Technology: Natural Science Edition,2010,33(4) : 8-14.  
[38] Gong Yan，Hu Yining，Zhao Yang.Design of a mini star simulator based on digital opticalprocessing [J]. Optics and Precision Engineering，2007，15(11）: 1698-1703.  
[39] Hao Shengguo，Hao Zhihang. Star image simulation software of star-tracker [J]. Optics andPrecision Engineering，2000，8(3）：91-95.  
[40] 魏新国，张广军，樊巧云，等.利用仿真星图的星敏感器地面功能测试方法［J].红外与激光工程，2008，37(6)：1087-1091.Wei Xinguo，Zhang Guangjun，Fan Qiaoyun，et al. Ground function test method of star sensorusing simulated sky image [J]. Infrared and Laser Engineering，2008,37(6）：1087-1091.  
[41] 王鹏基，张熇，曲广吉．月球软着陆飞行动力学和制导控制建模与仿真［J].中国科学 技术科学，2009，39(3)：521-527.Wang Pengji，Zhang Hao，Qu Guangji. Modeling and simulation of flight dynamics andguidance control for lunar soft landing ［J]. Scientia Sinica Technologica，2OO9,39(3）：521-527.

# An Overview of Celestial Autonomous Navigation Technology for Deep Space Exploration

Xue Xiping $^ { 1 , 2 , 3 }$ ， Zhang Hongbo $^ { 1 , 2 }$ ， Kong Deqing $^ { 1 , 2 }$

Key Laboratory of Lunar and Deep Space Exploration，Chinese Academy of Sciences，Beijing 100012，Cl 2.National Astronomical Observatories，Chinese Academy of Sciences，Beijing 10oo12,China; 3.University of Chinese Academy of Sciences，Beijing 1Ooo49,China,Email；xuexp@bao.ac.cn)

Abstract：Autonomous navigation technology has obvious advantages in improving deep space detector survival ability，reducing the burden of the ground station and meeting the need of special task stage in navigation.It has become a hotspot of research in the world wide.Mars exploration project has been launched in China，there are other projects for asteroids，comets andplanets and their satelites.Under this background，this paper describes the necessity of the development of autonomous celestial navigation technology；describes the basic principle and advantages of celestial navigation technology；and gives an overview of domestic and foreign deep space autonomous celestial navigation technology and application; summarizes the key technologies of the development of autonomous celestial navigation technology.According to theanalysis in this text，the suggestions and considerations for the development of deep space exploration autonomous navigation technology in China are proposed.

Key words: Celestial navigation；Autonomous navigation；Deep space exploration