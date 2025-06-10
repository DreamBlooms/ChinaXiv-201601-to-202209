# 基于激光雷达的同时定位与地图构建方法综述

危双丰1,2,3,4，庞帆1†，刘振彬1，师现杰1(1．北京建筑大学测绘与城市空间信息学院，北京 102616;2.代表性建筑与古建筑数据库教育部工程中心，北京102616;3.现代城市测绘国家测绘地理信息局重点实验室，北京 102616;4.建筑遗产精细重构与健康监测北京市重点实验室，北京 102616)

摘要：与基于视觉的同时定位与地图构建（SLAM）技术相比，激光SLAM由于定位的稳健性成为国内外研究热点。目的是在未知环境中定位自身位姿并同时构建环境地图，广泛应用在无人驾驶、室内外机器人导航以及三维重建等领域。文中首先分解激光SLAM的基本框架，分别对前端扫描匹配、后端优化、闭环检测与验证、地图构建四个模块近年来的主流算法进行总结；然后对基于滤波器和基于图优化两种激光 SLAM框架下的代表性方案进行深入分析和比较；最后对激光SLAM的发展趋势进行展望。

关键词：激光雷达同时定位与建图；扫描匹配；后端优化；闭环检测与验证；地图构建 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2018.09.0674

# Survey of lidar-based SLAMalgorithms

Wei Shuangfeng1,2,3,4,Pang Fan1,Liu Zhenbin1, Shi Xianjiel (1.School of Geomatics & Urban Spatial Informatics，Beijing UniversityofCivil Enginering & Architecture,Beijing 102616,China;2.EngineeringResearch CenterofRepresentative Building&Architectural Heritagedatabase,Ministryof Education,Beijing 102616,China; 3.Key Laboratory for Urban Geomaticsof National Administration of Surveying, Mapping& Geoinformation，Beijing lO2616,China；4.Beijing Key Laboratory for Architectural Heritage Fine Reconstruction & Health Monitoring,Beijing 1O2616,China)

Abstract: Compared with visual based simultaneous localizationand mapping (SLAM) technique,due to the robustnessof localization,laser based SLAMbecome aresearchhotspot at home andabroad.Thepurpose is positioning itself pose in the unknown environment and build environment mapat the same time,there are many applications such as autopilot,indoor and outdoor robot navigation,and 3Dreconstruction.Inthis paper,firstlyitdecomposed the asic frameworkof SLAM based on laser and summarized the mainstream algorithms of four modules from the angle of front-end scan match, back-end optimization,the closed loop detectionand validation,and map generation; Then it analyzedand compared the representation scheme under two framework of SLAM,one is based on filterand the other is basedon graph optimization; Finally, the paper point out the development trend of laser based SLAM.

Key words: laser SLAM; scan matching; back-end optimization; closed loop detection and verification; mapping

# 0 引言

室内外导航、无人驾驶、增强现实等方面的应用需要实时定位搭载传感器的主体在环境中的位姿。定位技术虽然已有很多种，但多数的技术要么在实际应用中存在诸多局限，要么代价过高难以普及。如GPS无法在室内及严重遮挡的室外环境中使用，且定位精度较低；高精度的惯导系统成本过高；基于无线信号（WiFi、蓝牙、LED可见光）的定位方案需事先布置使用场景等[1。而基于激光雷达的同时定位与地图构建技术（simultaneous localization and mapping,SLAM)以其准确测量障碍点的角度与距离、无须预先布置场景、可融合多传感器、在光线较差环境工作、能够生成便于导航的环境地图等优势，成为目前定位方案中不可或缺的新技术。

激光SLAM任务是搭载激光雷达的主体于运动中估计自身的位姿，同时建立周围的环境地图。而准确的定位需要精确的地图，精确的地图则来自于准确的定位，定位侧重自身了解，建图侧重外在了解[2]。SLAM技术历经古典时代（1986-2004）、算法分析时代（2004-2015）、鲁棒性时代（2015-）[3]，出现了一些关于SLAM的综述，经典的例如CadenaC等人[3]撰写的文章，但是专门针对激光SLAM的系统总结则未能见到。本文专注于当前激光SLAM算法的总结，并对激光SLAM代表性方案进行分析和比较。

# 1激光SLAM关键模块算法

激光SLAM所需要的传感器一般有激光雷达（Lidar）、惯性测量单元（IMU）、里程计（Odometry)。通常室内采用二维激光雷达，室外采用三维激光雷达，里程计采用轮式里程计。由于IMU具有较高的角速度测量精度，相比IMU里程计具有较高的局部位置测量精度，一般用IMU计算角度信息，里程计计算位置信息，配合激光雷达进行SLAM过程。

当前，激光SLAM框架一般分为前端扫描匹配、后端优化、闭环检测、地图构建四个关键模块。前端扫描匹配是激光SLAM的核心步骤，工作内容是已知前一帧位姿并利用相邻帧之间的关系估计当前帧的位姿；前端扫描匹配能给出短时间内的位姿和地图，但由于不可避免的误差累积，后端优化正是当长时间增量式扫描匹配后优化里程计及地图信息；闭环检测负责通过检测闭环而减少全局地图的漂移现象，以便生成全局一致性地图；地图构建模块负责生成和维护全局地图。下面从算法的角度分别对四个模块进行总结。

# 1.1前端扫描匹配

目前在激光SLAM中主流的扫描匹配算法包括：迭代最临近点及变种、相关性扫描匹配、基于优化方法、正态分布变换、基于特征的匹配以及其他匹配算法。下面对上述6种算法进行总结，并介绍当无法获得较好初始条件时激光数据匹配问题的解决方案。

# 1.1.1迭代最临近点（IterativeClosestPoint）及变种

由ChenY等人[4提出的ICP算法，利用待匹配的两帧点云欧式距离最小化，恢复相对位姿变换信息。ICP方法分为已知对应点的求解和未知对应点的求解两种，其中已知对应点的情况能够直接计算出R和T的闭式解，而未知对应点的求解需要进行迭代计算，是EM算法的一个特例，算法流程(如图1)。CensiA 等人[5]提出ICP 变种算法(Point-to-Line ICPPL-ICP),算法流程如图2,适用于2D 激光SLAM。LowKL[6]提出ICP变种算法（Point-to-PlaneICP，PP-ICP)，适用于3D激光SLAM。ICP、PL-ICP与PP-ICP比较如表1所示。

# 1.1.2相关性扫描匹配（CorrelationScanMatch）

由OlsonEB等人[8提出的CSM算法，该算法匹配的似然场模型高度非凸，存在很多局部极值。由于进行暴力匹配，排除初值敏感的影响，这是与前面三种匹配方法的最大区别。CSM算法流程如图3所示，该方法是对环境分辨率细分的，精度会受限于分辨率。另外该种方法能够通过加速策略来降低计算量，例如分枝定界方法。

1.1.3基于优化方法（Optimization-basedMethod)

给定一个目标函数，把激光数据扫描匹配问题建模成非线性最小二乘优化问题，该方法帮助限制误差的累积。基于优化的方法最大问题是对初值敏感，若初值选择恰当，由于对地图进行插值，建图精度往往会比较高。典型代表是Hector-SLAM[9]中的匹配方法。

# 1.1.4正态分布变换（NormalDistribution Transformation）

BiberP等人[10]提出的NDT算法，最开始作为一种二维的匹配方法，由MagnussonM等人[11]将该算法应用到三维的匹配中，是把地图看成很多高斯分布的集合，不需要通过搜索，直接最小化目标函数便能得到转换关系，计算量小，速度较快。NDT方法在3D 激光SLAM与纯定位中使用较多。1.1.5基于特征的匹配 (Feature-basedMethod)

FernandoM等人[2]通过匹配从激光扫描提取的特征点来改善计算成本，类似于视觉SLAM中的基于特征匹配的方法。ZhangJ等人[13]在每次扫描中专注于边和平面特征并将它们保存在地图中以进行边线和平面与平面的匹配，该方法适用于3D 激光SLAM。

# 1.1.6其他匹配方法

DeschaudJE等人[14]基于特定的采样策略和扫描到模型（scan-to-model）的匹配方式提出一种纯3D激光SLAM算法。在结合深度学习方面，NicolaiA等人[15]利用VLP-16采集3D点云数据，将其投影到2D平面生成深度图像，利用CNN网络训练，得到端到端的匹配结果，其运行速度明显快于传统ICP匹配方法。

另外，针对无法获得较好初始条件的激光雷达数据匹配问题，BosseM等人[16提出基于投影直方图和熵序列为迭代扫描匹配直接计算初始条件的新方法，将旋转和平移估计分解成一系列的相关性直方图。ChecchinP等人[17将该任务视为影像匹配问题，利用通过毫米波雷达采集深度数据，经过Fourier-Mellin变换，通过相关方法对相邻帧之间的刚体变换进行自动计算和全局估计。

![](images/03bc143e25820777e14f0394f0308fac2a7377e495fe704e0627c48dfd87b969.jpg)  
图2PL-ICP 算法流程 Fig.2PL-ICP algorithm flow

![](images/41527a3ce91e40c1f7f0ea68d85d2ca1d2674700ef8ea58feac94ed1d68f191f.jpg)  
图3CSM算法流程 Fig.3CSM algorithm flow

![](images/51e8d47b7f3a1dbfb950106586fd6acb6d3f99383f1beaad9bbe42cf4e9a16c8.jpg)  
图1ICP 算法流程 Fig.1ICP algorithm flow

与上述全局策略相反，一些国外的学者提出基于遗传算法的扫描匹配。MartinezJL等人[18]提出使用一种解空间的遗传搜索方法来获取初始条件，将ICP的误差度量作为适应度函数，然后评估并改变一组初始估计直到留下单个的主导变换。LenacK等人[19]介绍一种基于相关性度量的遗传搜索去寻找粗略的初始条件，通过ICP算法能够优化遗传搜索的结果。CorsoN等人[20提出了一种抗离群点的分段遗传扫描匹配（FGSM）算法，该算法能够在初始条件较差的情况下精确扫描匹配。首先使用PhillipsJM等人[21]提出的分段均方根距离度量来极大的排除离群点干扰。然后通过变换函数，遗传扫描匹配算法仅搜索目标函数的局部最小值，为了改善计算成本又提出了一种解空间离散化方法。

目前，在2D激光SLAM中，最流行的匹配方法是CSM与梯度优化结合使用，典型的开源方案是Cartographer[7]。在3D 激光SLAM中，最流行的匹配方法是基于特征的匹配，典型的开源方案是LOAM[13]。

# 1.2后端优化

在激光SLAM中，对于解决遗留的局部误差累积的两种普遍的做法是基于滤波器的后端和基于图优化的后端[22.23]。

表1ICP、PL-ICP、PP-ICP三种算法比较

Table1Comparison of three algorithms of ICP,PL-ICP and PP-ICP   

<html><body><table><tr><td>ICP种类</td><td>误差函数收敛速度</td><td></td><td>求解精度</td><td>不足</td></tr><tr><td rowspan="2">ICp[4]</td><td>点对点</td><td>一阶 收敛</td><td rowspan="2">较低</td><td>计算成本大；由于激光点的不连续 性，ICP会造成误匹配引入额外的</td></tr><tr><td>距离</td><td></td><td>误差，在退化环境中会迅速的累积 误差[7]，如长直的走廊。</td></tr><tr><td rowspan="2">Point-to-Line</td><td></td><td></td><td></td><td>较高，适用于PL-ICP相比ICP对初始值更敏感，</td></tr><tr><td>点到线</td><td>二阶 收敛</td><td>2D激光</td><td>容易陷入局部极值；对于大旋转情</td></tr><tr><td>ICP[5]</td><td>距离</td><td></td><td>SLAM</td><td>况下算法不够鲁棒。</td></tr><tr><td>Point-to-Plane</td><td>点到平</td><td></td><td></td><td>二阶高，适用于3D需要从大量的三维激光点中提取特</td></tr><tr><td>ICp [6]</td><td>面距离</td><td>收敛</td><td>激光SLAM</td><td>征点。</td></tr></table></body></html>

1.2.1基于滤波器

基于滤波器的激光SLAM是一个贝叶斯估计的过程。包括里程计预测、测量预测、进行测量、数据关联、状态更新以及地图更新。下面对几种滤波的形式进行总结（如表2)。

表2滤波形式  
Table 2 Filter form   

<html><body><table><tr><td>滤波器形式</td><td>描述</td></tr><tr><td>卡尔曼滤波(KF)</td><td>递归的线性高斯系统最优估计。 当非线性非高斯系统时，将在工作点附</td></tr><tr><td>扩展卡尔曼滤波 (EKF)</td><td>近近似为线性高斯进行处理。</td></tr><tr><td>迭代卡尔曼滤波(IEKF)</td><td>对工作点进行迭代。</td></tr><tr><td>无迹卡尔曼滤波(UKF)</td><td>没有线性化近似，而是把sigma 点进行 非线性变换后再用高斯分布近似。</td></tr><tr><td>粒子滤波 (PF)</td><td>去掉高斯假设，直接采用蒙特卡洛的方 式，以粒子作为采样点来描述分布[24]。</td></tr></table></body></html>

在基于滤波器的激光SLAM中常常采用粒子滤波（PF)作为数学优化的框架，当表达较小的尺寸环境时，TipaldiGD等人[25]提出不需要每个粒子的栅格地图，能够减少资源需求量，当需要更新栅格地图时，StromJ等人[26]建议计算子图，只在必要时更新，使得最终的图是所有子图的栅格化。

# 1.2.2基于图优化

利用图论的方式来表示机器人SLAM过程，将机器人的位姿用节点（Node）表示，将节点之间的空间约束关系用边（Edge）表示，机器人在建图的过程中会积累误差，通过非线性最小二乘方法来优化建图过程中累积的误差[27,28]，即优化的方式同时考虑所有帧间约束，迭代线性化求解。BosseM等人[16]介绍的基于图优化的方法、局部扫描到扫描的匹配以及基于子图特征的直方图的匹配应用在室外SLAM的系统。如图4，5分别为图优化前后的建图效果。激光SLAM目前最流行的后端优化方法是基于图优化的数学框架。

![](images/5c18d3e347eb8adbb727bc2f04d4611f1466850090728a522285fb2df51b38a7.jpg)  
图4图优化前  
Fig.4Before optimization   
Fig.5After optimization

![](images/069253239c6257dbb0d52882032c4262eac32671bc654403240b05287700c255.jpg)  
图5图优化后

# 1.3闭环检测与验证

# 1.3.1闭环检测

闭环问题是数据关联问题的重要一类，利用闭环这一约束条件来达成拓扑一致的轨迹地图，闭环检测的问题是激光数据扫描匹配结果相似性的问题。

1）帧与帧闭环检测（Scan-to-Scan）。

OlsonEB等人[8采用的相关性扫描匹配，通过旋转和平移判断两帧激光数据的相似性，达到闭环检测的效果。但由于单帧激光数据的信息量少，容易和其他相似度高的数据发生错误匹配，不适用2D激光SLAM。

2）帧与子图闭环检测（Scan-to-Map）。

谷歌的Cartographer通过帧与子图的闭环检测来消除建图过程中产生的累积误差[7]。由ZakhorA等人[29]提出分段遗传扫描匹配算法（FGSM）利用二维的激光数据在闭环约束之间自动的估计变换，基于遗传搜索方法以及特殊建模离群值的距离度量，即使在近似的初始条件未知的情况下也能提供鲁棒的变换估计。

# 3）子图与子图闭环检测（Map-to-Map）。

该种检测方法改善了激光数据信息量少的缺点，将当前的N帧激光数据整合成局部子图，与之前的子图进行匹配。在BosseM等人[16的工作中，对于全局匹配利用现有的直方图互相关技术，引入熵序列投影直方图和穷举相关方法在非结构化环境中实现可靠匹配，适用于大比例尺环境的地图构建。文国成等人[30提出采用子地图与子地图匹配的方法进行闭环检测，通过定位筛选和压缩表，对闭环检测匹配候选集优化，有效解决了在大尺度地图中匹配速度缓慢及误检的问题。KonoligeK等人[31]为了得到当前帧与前面观测值关系，将当前帧的局部子图与已有地图进行比较，利用基于传感器扫描与地图的相关性原理来实现闭环检测。

# 4）其他的闭环检测方法

OlsonE等人[32]提出的像素精确的扫描匹配方法，可进一步减少局部误差的累积。虽然计算成本更高，但该方法对于环路的闭合检测也很有用。在结合深度学习的方面，HimstedtM等人[33]采用基于直方图的匹配，NietoJI等人[34]利用检测扫描数据中的特征点，并结合深度学习方法进行匹配。

# 5）闭环检测的加速策略

谷歌的Cartographer方案提出的分枝定界算法，分枝定界（BranchandBound）算法是常用的树型搜索剪枝算法，这是一个对闭环检测加速的策略。最初由Land AH等人[35]在求解整数规划问题背景下提出的，ClausenJ等人[36]对分枝定界的原理和例子进行概述总结，把最优求解问题转换为树型搜索问题，对于搜索树中的每一个节点，确定以该节点为根节点的子树的上界进行搜索来达到减枝加速的目的。

# 1.3.2闭环验证

一般的闭环检测的局限性在于误报（falsepositives)，进而导致错误的闭环，降低建图系统的性能，造成恢复地图后拓扑不一致。所以近年来一些国外学者提出闭环验证算法。

在BosseM等人[37的工作中，将基于投影直方图和熵序列之间的最大相关性之和的验证度量用于估计闭环检测的正确性。在之后的BosseM，ZlotR等人[6的工作中正确率被提升。CallmerJ等人[38的工作中提出了一个基于变换后扫描的最后配准的验证标准。在非结构化的室外环境下测试，对于有闭环检测与闭环验证的系统正确率进一步提升

与之前的工作不同，Corso N等人[20]提出在室内环境中严格处理闭环验证。CorsoN等人认为闭环可以从很多数据源中被检测到，因此将闭环验证算法与闭环检测算法相分离。针对室内的退化环境，由于在激光数据中缺少明显的特征点，提出了两个既能表征场景复杂性又能表征几何对齐的验证度量，使用简单的阈值方案，能够自动防止错误的环路闭合而构建几何不一致的地图。经过端到端的测试，该方法能够应用于各种各样的基于2DLiDAR的闭环系统。

目前，激光SLAM最流行的闭环检测方法是帧与地图之间的匹配，利用分枝定界策略加速匹配速度以及结合延时决策（LazyDecision）保证匹配的准确性。

# 1.4地图构建

SLAM构建的地图是传感器周围环境的模型，是机器人进行定位和路径规划的前提。在SLAM领域，构建的地图主要分为三类：尺度地图、拓扑地图以及语义地图（如表3)。

为强调基于激光SLAM系统中建图的实时性，地图构建模块通常采用计算量较少的占据栅格建图算法，是基于贝叶斯估计的方式。

占据栅格地图[39把环境分解成一个个栅格，栅格是二元随机变量，有占据或空闲两种状态。占据栅格地图中的每一个栅格是独立的，估计环境的地图只需要对每一个独立的栅格进行估计，该算法对某一个栅格进行操作时，只有加法计算，因此具有非常高的更新速度，更新地图时，需要知道传感器的逆观测模型。占据栅格地图以周围环境是否被遮挡来鲜明区分可通行区域，适用于避障与导航路径规划。

目前，无论是2D激光SLAM还是3D激光SLAM，应用最广泛的地图种类是占据栅格地图。另外实际应用中在评定基于激光SLAM建图的精度指标时可以分别与全站仪、钢尺、地面式激光扫描仪进行比较，将标靶球中心的点位误差作为一个精度指标，将特征物体尺寸的中误差作为一个精度指标，将点云模型的配准误差作为一个精度指标[40]

表3三种地图种类   
Table3Three types of maps   

<html><body><table><tr><td colspan="2">地图种类</td></tr><tr><td>尺度地图</td><td>构建的地图与实际环境尺度保持一致，栅格地图 （如图6)、特征地图（如图7）、点云地图（如图</td></tr><tr><td></td><td>8）都属于尺度地图。</td></tr><tr><td>拓扑地图</td><td>表示连通关系，包括是否连通以及距离大小，适 用于大尺度环境下的路径规划。</td></tr><tr><td>语义地图</td><td>加标签的尺度地图，强调地图中对象与对象之间 的描述性（如图9)。</td></tr></table></body></html>

![](images/c97800bf3e8372f22a6ed8ff8580f927e43c6e5ca0898896f4f1989bce6eeedc.jpg)  
图6栅格地图

![](images/a5790351c65b9adc1ca60fc8fcc3a7e738474395076a5cda55af215caaed371b.jpg)  
Fig.6Raster map

![](images/40154ec24457d05caa04b5149bf60f60b600e63976f8a98f42df98a1fce4d8cb.jpg)  
Fig.7Feature map   
图8点云地图

![](images/b9da7f45e5ca594fd2c59557bfad15bad447a6816c8a9b0c5f517d46804407e6.jpg)  
图7特征地图  
Fig.8Point cloud map   
图9语义地图Fig.9Semantic map

# 2 激光SLAM方案对比

根据所采用的数学优化框架，激光SLAM可分为两大类：基于滤波器（Filter-based）和基于图优化（Graph-based)的激光SLAM。下面分别介绍两种框架下的激光SLAM方案。

# 2.1基于滤波器的激光SLAM方案

由SmithR等人提出的扩展卡尔曼滤波SLAM方案（EKF-SLAM）[41]，使用最大似然算法进行数据关联，该方案的缺点是计算量复杂，鲁棒性较差，构建的地图是特征地图而不是栅格地图，无法应用在导航避障上。

针对EKF-SLAM方案的不足，MontemerloM等人提出了FastSLAM方案[42]，该方案将SLAM问题分解成机器人定位问题和基于已知机器人位姿的构图问题，是最早能够实时输出栅格地图的激光SLAM方案。用粒子滤波来估计机器人位姿，将每个粒子用运动学模型进行传播，对于传播后的粒子用观测模型进行权重计算并根据估计的位姿构建地图。该方案存在两个问题，第一，由于每个粒子包含机器人的轨迹和对应的环境地图，对于大尺度环境，若里程计误差较大即预测分布与真实分布差异较大，则需要较多粒子来表示机器人位姿的后验概率分布，严重消耗内存；第二，由于重采样的随机性，随着重采样次数增多，粒子多样性散失，粒子耗散问题会严重影响地图的构建。

为了对FastSLAM方案进行优化，GrisettiG等人提出Gmapping方案[43]，以FastSLAM方案为基本原理，在较小的环境中能实现较好的建图效果，是目前使用最为广泛的2D激光SLAM方案，建图效果如图10所示。为了解决内存消耗严重问题，将粒子的数量保持在一个比较小的数值，对预测分布采样，然后基于优化扫描匹配来优化位姿。对于缓解粒子耗散问题，采用减少重采样次数，用一个度量表示预测分布与真实分布的差异性，当差异性很小时，不进行重采样，当差异性很大时，进行重采样。该方案不足是在里程计模型在传播时，对所有的粒子同等对待，优的粒子在传播时可能变成差的粒子，粒子退化问题严重。因此Gmapping 方案非常依赖于里程计信息，构建的地图也取决于里程计的精度。

针对Gmapping方案的不足，BlancoJL等人在2010 年提出了更加优化的OptimalRBPF方案[44]，其在里程计模型传播时，一个粒子每次传播会得到N个粒子，在N个粒子里面选择最优粒子，作为此次的真实传播，相当于每个粒子给了N次机会，大大减少最优粒子退化为噪声很大的粒子情况。

王

# 2.2基于图优化的激光SLAM方案

在激光雷达领域，LuF，MiliosE等人[45]首次提出利用图优化（graph-based optimization）的数学框架优化SLAM问题，通过非线性最小二乘方法来优化建图过程中累积的误差。其存在的问题在于没有认识到系统的稀疏性，离线处理SLAM问题。由GutmannJ等人[46]提出的图优化框架与当前的图优化框架相似，包括局部扫描匹配、全局优化、以及子图与子图的闭环检测，不足是同样没有认识到系统的稀疏性，并非实时SLAM。

为了进一步改善前面工作的不足，KonoligeK等人[22]提出首个基于图优化框架的开源方案KartoSLAM，该方案认识到了系统稀疏性，在一定程度上替代了基于滤波器的激光SLAM方案。该方案的不足是采用局部子图匹配之前都要构建子图，耗费时间较长；若采用全局匹配方法，则在搜索范围大的时候速度会变慢。

谷歌的Cartographer[7开源方案，是对Karto SLAM的优化方案，核心内容是融合多传感器数据的局部子图创建以及用于闭环检测的扫描匹配策略，建图效果如图11所示。该方案中前端扫描匹配算法是结合CSM与梯度优化来实现的。在生成一个子地图后，会进行一次局部的闭环检测；当全部子地图构建完成后，利用分枝定界和预先计算的网格的算法，进行全局闭环检测，从而保证闭环检测的速度。该方案的不足是没有对闭环检测结果进行验证，在几何对称的环境中，容易引起错误的闭环。

另外，KohlbrecherS等人提出了Hector-SLAM方案[9],该方案利用高斯牛顿方法解决前端扫描匹配问题，把每一帧采集到的激光雷达数据和地图进行匹配，该方案仅有前端扫描匹配的模块，无后端优化的过程。与Gmapping方案最大的区别在于不需要里程计数据，里程计信息通过激光雷达数据估算出来，所以对传感器的测量频率要求较高。在ROS仿真环境中运行Hector-SLAM方案，若机器人速度过快尤其是在强旋转的时候，Hector-SLAM方案会发生漂移现象，如图12所示。在真实环境中，由于周围特征点能够辅助机器人定位和建图，构建的栅格地图会比仿真环境中效果好，建图效果如图13所示。Hector-SLAM方案的缺点是对初值敏感，同时难以处理闭环问题。Hector-SLAM的整体建图精度高于Gmapping，但对参数配置要求较高。Hector-SLAM适用于对地图要求较高的场合，Gmapping易用性更好[47]。

![](images/6913621d4c0e81d04604fcaba8632f12360a2c5b5520d745b19c9298325d5872.jpg)  
图11Cartographer方案 Fig.11 Cartographer scheme

![](images/d26747e112761881690149b9e72ed27ebdc92fc4523e36365bcfcecec71892e2.jpg)  
图10 Gmapping方案 Fig.10 Gmapping scheme   
图12Hector-SLAM 漂移Fig.12Hector-SLAMdrift  
图13Hector-SLAM方案Fig.13Hector-SLAM scheme

下象 州

在 3D 激光 SLAM 领域中，由 ZhangJ等人[13]提出的LOAM方案，利用3D 激光雷达采集数据，进行基于特征点的扫描匹配，利用非线性优化方法进行运动估计，激光里程计的输出与地图进行匹配，包括直线匹配和平面匹配，无回环检测模块，点面特征还不够可靠。LOAM方案的框架如图14所示。

为了进一步改进LOAM方案的，ZhangJ等人[48]提出视觉结合3D激光雷达实时建图的V-LOAM方案（如图15）。利用视觉里程计以高频率估计位姿变换，激光里程计以低频率优化运动估计，并校准漂移。在公开的KITTI数据集上，V-LOAM算法精度排名第一，而且当传感器高速运动并受到明显的光照变化时，该方法的鲁棒性较好。

![](images/950e28e49a8a3e0710b5ca31640aa09f2c773439b90f5660177c615a2c240049.jpg)  
图14LOAM方案框架

![](images/e8fb852394e95fb2f4cd6e247c1bbf989002d1082910f80868601ea56c964a57.jpg)  
Fig.14 LOAM scheme framework   
图15V-LOAM方案框架

DanielLawrenceLu等人[49]提出增强视觉结合激光雷达的VELO新方案，通过紧耦合的稀疏视觉与激光数据进行前端扫描匹配，利用位姿图的稀疏性进一步优化位姿误差。VELO具有低漂移性同时当激光雷达或相机数据被遮挡时能够可靠运行。

DeschaudJE等人[14]基于特定的采样策略和扫描到模型（scan-to-model）的匹配方式提出一种纯3D 激光SLAM算法。

ZhangJ等人[50提出了一种用于自我运动估计和建图的数据处理方案LVIO（如图16)。该方案连接3D 激光扫描仪，相机和IMU，顺序多层运行三个模块以产生实时自我运动估计。粗到精数据处理产生高速率估计并在长距离中构建低漂移的地图。

![](images/b5369529ea69d77aa23e55f00323f60225a749562f85cc7116e5f0b6a570ed6b.jpg)  
Fig.15V-LOAM scheme framework   
图16LVIO 方案框架Fig.16LVIO scheme framework

下面对几种激光SLAM方案进行总结，如表4所示。

# 3 发展趋势

当前，激光SLAM发展趋势主要涵盖以下三个方面：

1）深度学习在激光SLAM的应用。例如NicolaiA等人[15]将前端扫描匹配与深度学习结合，利用CNN 网络训练,得到端到端的帧间估计结果，实现了高维传感器数据处理与融合。邹勤[51将闭环检测模块与深度学习结合，构建一种深度Hash网络对激光点云样本进行Hash编码并计算样本相似度，实现相似样本的快速检索。而SLAM中后端模块是状态估计问题，有明确的数学模型做支撑，因此，深度学习端到端的贯穿整个SLAM系统将会有极大的挑战。此外，融合多传感器，配合深度学习领域中物体检测、识别和解析算法，进行语义SLAM以及实时三维重建[52]是未来SLAM的重要方向。

表4几种激光 SLAM方案  
Table 4Several laser SLAMschemes   

<html><body><table><tr><td>年份</td><td>方案</td><td>传感器</td><td>优缺点</td></tr><tr><td>1988年</td><td>EKF-SLAM[41]</td><td>2D激光</td><td>构建特征地图，计算量复杂，鲁棒性较差。</td></tr><tr><td>2002年</td><td>FastSLAM[42]</td><td>2D激光</td><td>最早实时输出栅格地图；消耗内存，粒子耗 散严重。</td></tr><tr><td>2007年</td><td>Gmapping[43]</td><td>2D激光</td><td>缓解粒子耗散；非常依赖于里程计信息。</td></tr><tr><td>2010年</td><td>Optimal RBPF[44]</td><td>2D激光</td><td>进一步减少粒子退化问题。</td></tr><tr><td>2010年</td><td>Karto SLAM[22]</td><td>2D激光</td><td>首个基于图优化框架开源方案，认识到稀疏 性；耗费时间。</td></tr><tr><td>2011年</td><td>Hector-SLAM[9]</td><td>2D激光</td><td>不需要里程计数据；强旋转漂移，初值敏感，</td></tr><tr><td>2014年</td><td>LOAM[13]</td><td>3D激光</td><td>难处理闭环。 实时性好；匀速运动假设，无闭环检测。</td></tr><tr><td>2015年</td><td></td><td></td><td>3D 激光、视精度高，算法鲁棒性好；漂移匀速假设，无</td></tr><tr><td></td><td>V-LOAM[48]</td><td>觉</td><td>闭环检测。</td></tr><tr><td>2016年</td><td>Cartographer[7]</td><td>2D激光</td><td>CSM与梯度优化的前端，图优化的后端，加 速的闭环检测。</td></tr><tr><td>2016年</td><td>VELO[49]</td><td>3D激光、视 觉</td><td>有闭环检测模块，低漂移；无运动畸变假设。</td></tr><tr><td>2018年</td><td>IMLS[14]</td><td>3D激光</td><td>不依赖于GPS、IMU、相机等传感器，低漂 移。</td></tr><tr><td>2018年</td><td>LVIO[50]</td><td></td><td>3D 激光、视 低漂移，光照、旋转、结构退化环境下鲁棒</td></tr></table></body></html>

2）面对复杂的周围环境，多传感器融合的SLAM是必然趋势。视觉会提供高精度的里程计以及信息量丰富的地图信息，激光雷达为视觉特征提供准确的深度信息。例如BokY等人[53]以松耦合和图优化方式融合2D激光雷达，GPS与相机数据，用于文物保护的室外 SLAM系统。Shen S 等人[54]与LynenS等人[55]两者均提出紧耦合的EKF估计器，用于融合多传感器信息的MAV系统。

3）SLAM算法的鲁棒性与实时性有待进一步提高。在提高SLAM算法的鲁棒性方面，需要考虑里程计的标定、激光雷达的外参与时间戳标定、激光雷达运动畸变的去除等数据处理过程，同时针对退化环境、全局定位、动态环境定位等问题还有待完善。例如CorsoN等人[20设计背包SLAM系统时，提出激光雷达与惯性传感器之间直接在线进行外参标定和时间标定。石鹏等人[56]提出在动态环境下激光SLAM方法。ZhangJ等人[50提出用于自我运动估计并构建地图的数据处理方法，该方法对于各个传感器故障、剧烈光照变化和结构退化、以及高速旋转与平移运动有较好的鲁棒性。在提高SLAM算法的实时性方面，ZhangJ等人[57提出两种不同频率的模块并行运算，保证低计算复杂度的同时实现实时的低漂移里程计。ParkC等人[58]提出了一种稠密的以地图为中心的CT-SLAM新方法，用于多模块传感器融合，提高了系统的实时性和长期适用性。DroeschelD等人[59] 基于高效的局部地图和分层的优化后端，提出了分层、连续时间的3D激光SLAM方法，允许实时建图期间优化配准。

上述发展趋势将把激光SLAM方案从实验室引入工程实践中，使移动机器人更加智能化。

# 4 结束语

随着3D固态激光雷达技术的成熟与深度学习理论的深入发展，越来多低成本激光雷达被民用化，同时将会有更加鲁棒的激光SLAM算法随之产生，以激光SLAM为基础的技术会被广泛的应用在室内外导航、无人驾驶、以及实时二维里廷寸刀面。

参考文献：   
[1]刘浩敏，章国锋，鲍虎军．基于单目视觉的同时定位与地图构建方 法综述[J].计算机辅助设计与图形学学报，2016,28(6)：855-868. (Liu Haomin,Zhang Guofeng,Bao Hujun.A survey of monocular simultaneous localization and mapping [J]. Journal of Computer-Aided Design & Computer Graphics,2016,28(6): 855-868.)   
[2] 高翔，张涛，等．视觉 SLAM 十四讲 [M].北京：电子工业出版社, 2017.(Gao Xiang,Zhang Tao,et al. The fourteen lectures on visual SLAM [M]. Beijing: Publishing House of Electronics Industry,2017.）   
[3]Cadena C,Carlone L,Carrillo H,et al.Past,present,and future of simultaneous localization and mapping: toward the robust-perception age [J].IEEE Transactions on Robotics,2016,32(6):1309-1332.   
[4]Chen Y,Medioni G. Object modelling by registration of multiple range images [J].Image & Vision Computing,1992,10 (3):145-155.   
[5] Censi A.An ICP variant using a point-to-line metric [C]//Proc of IEEE International Conference on Robotics and Automation.Piscataway, NJ: IEEE Press,2008:19-25.   
[6]Low K L.Linear least-squares optimization for point-to-plane ICP surface registration,TRO4-0O4 [R]. North Carolina: University of North Carolina at Chapel Hill, 2004.   
[7]Hess W,Kohler D,Rapp H,et al.Real-time loop closure in 2D lidar SLAM [C]// Proc of IEEE International Conference on Robotics and Automation. Piscataway,NJ: IEEE Press,2016: 1271-1278.   
[8] Olson E B.Real-time correlative scan matching [C]// Proc of IEEE International Conference on Robotics and Automation. Piscataway, NJ: IEEE Press,2009: 4387-4393.   
[9]Kohlbrecher S,Stryk O V,MeyerJ,et al.A flexible and scalable SLAM system with full3D motion estimation [C]//Proc of IEEE International Symposium on Safety Security and Rescue Robotics.Piscataway, NJ: IEEE Press,2011: 155-160.   
[10] Biber P, Strasser W. The normal distributions transform:a new approach to laser scan matching [C]// Proc of IEEE//RSJ International Conference on Intelligent Robots and Systems.Piscataway,NJ:IEEE Press, 2003: 2743-2748.   
[11] MagnussonM.Thethree-dimensionalnormaldistributions transform-an efficient representation for registration,surface analysis, and loop detection [J].Renewable Energy,2009,28 (4): 655-663.   
[12] Fernando M，Rudolph T,Luis M,et al. Two diferent tools for three-dimensional mapping: de-based scan matching and feature-based loop detection [J].Robotica,2014,32 (1):19-41.   
[13] Zhang J,Singh S.LOAM: lidar odometry and mapping in real-time [C/OL]/ Proc of Robotics: Science and Systems. (2014-07-12) [2018-08-12]. http://www. roboticsproceedings.org/rss10/p07. pdf.   
[14] Deschaud JE.IMLS-SLAM: scan-to-model matching based on 3D data [C]//Proc of IEEE International Conference on Roboticsand Automation.Piscataway, NJ: IEEE Press,2018: 2480-2485.   
[15] Nicolai A,Skeele R,Eriksen C,et al.Deep learning for laser based odometryestimation[J/OL].(2016)[2018-10-16].http://juxi. net/workshop/deep-learning-rss-2016/papers/Nicolai%20-%20Deep%2 OLearning%20Lidar%20Odometry. pdf.   
[16] Bosse M,Zlot R. Map matching and data association for large-scale two-dimensional laserscan-based SLAM [J/OL]. (2008-06-01) [2018-08-12]. http://journals. sagepub. com/doi/abs/10. 1177/0278364908091366.   
[17] Checchin P, Gerossier F,Blanc C,et al. Radar scan matching SLAM using the fourier-mellin transform [J].Field and Service Robotics,2010, 62 (7): 151-161.   
[18] Martinez JL,Gonzalez J，Morales J，et al.Mobile robot motion estimation by 2D scan matching with genetic and iterative closest point algorithms [J].Journal of Field Robotics,2010,23(1): 21-34.   
[19] Lenac K,Mumolo E,Nolich M.Robust and accurate genetic scan matching algorithm for robotic navigation [M]// Intellgent Robotics and Applications.Berlin: Springer, 2011: 584-593.   
[20] Corso N.Sensor fusion and online calibration of an ambulatory backpack system for indoor mobile mapping, UCB//EECS-2016-81 [R]. California: Universityof California,Berkeley,2016.   
[21] Phillips JM,Liu R,Tomasi C. Outlier robust ICP for minimizing fractional RMSD [C]/ Proc of the 6th International Conference on 3-D Digital Imaging and Modeling.Piscataway,NJ: IEEE Press，2007: 427-434.   
[22] Konolige K,Grisetti G,Kummerle R,et al.Eficient sparse pose adjustment for 2D mapping [C// Proc of IEEE//RSJ International Conference on Intelligent Robots and Systems.Piscataway,NJ: IEEE Press,2010: 22-29.   
[23] Grisettiyz $\mathbf { G }$ Stachniss C, Burgard W. Improving grid-based SLAM with Rao-Blackwellized Particle Filters by adaptive proposals and selective resampling [Cl// Proc of IEEE International Conference on Robotics and Automation.． Piscataway，NJ: IEEE Press，2005: 2432-2437.   
[24] Barfoot TD. State estimation for robotics [M]. Cambridge: Cambridge University Press, 2017.   
[25] TipaldiG D,Braun M,Kai O A. Interest regions for 2D range data with applications to robot navigation [J]. Springer Tracts in Advanced Robotics,2014,79 (1): 695-710.   
[26] Strom J. Occupancy grid rasterization in large environments for teams of robots [C// Proc of IEEE/RSJ International Conference on Intelligent Robots and Systems.Piscataway,NJ:IEEE Press,2011: 4271-4276.   
[27] Kummerle R, Griseti G, Strasdat H, et al. G2o: a general framework for graph optimization [Cl// Proc of IEEE International Conference on Roboticsand Automation. Piscataway，NJ: IEEE Press，2011: 3607-3613.   
[28] Carlone L，Aragues R,Castellanos JA,et al.A fast and accurate approximation for planar pose graph optimization [J]. International Journal of Robotics Research,2014,33(7): 965-987.   
[29] Zakhor A.Loop closure transformation estimation and verification using 2D lidarscanners，UCB//EECS-2013-73[R]. California: University of California,Berkeley,2013.   
[30]文国成，曾碧，陈云华．一种适用于激光 SLAM 大尺度地图的闭环 检测方法[J].计算机应用研究，2018,35(6)：1724-1727.(Wen Guocheng, Zeng Bi, Chen Yunhua.Loop closure detection method for large scale map of laser SLAM[J]. Application Research of Computers, 2018,35 (6): 1724-1727.)   
[31] Konolige K, Chou K. Markov localization using correlation [C]/ Proc of the 16th International Joint Conference on Artificial Intelligence.San Francisco: Morgan Kaumann,1999: 1154-1159.   
[32] Olson E.M3RSM: many-to-many multi-resolution scan matching [C]// Proc of the IEEE International Conference on Robotics and Automation. Piscataway,NJ: IEEE Press,2015:5815-5821.   
[33] Himstedt M,Frost J,Hellbach S,et al.Large scale place recognition in 2D lidar scans using geometrical landmark relations [Cl// Proc of IEEE//RSJ International Conference on Intelligent Robots and Systems. Piscataway,NJ: IEEE Press,2014: 5030-5035.   
[34] Nieto JI,Ramos F T.Learning to close loops from range data [J]. International Journal of Robotics Research,2011,30 (14): 1728-1754.   
[35] Land A H,Doig A G.An automatic method of solving discrete programming problems [J]. Econometrica,1960,28 (3): 497-520.   
[36] Clausen J. Branch and bound algorithms-principles and examples [J]. Parallel Processing Letters,1999,22 (5): 658-663.   
[37] Bosse M,Roberts J. Histogram matching and global initialization for laser-only SLAM in large unstructured environments [Cl//Proc of IEEE International Conference on Robotics and Automation.Piscataway, NJ: IEEE Press,2007: 4820-4826.   
[38] Callmer J, Ramos F, Nieto J. Learning to detect loop closure from range data [Cl// Proc of IEEE International Conference on Robotics and Automation. Piscataway,NJ: IEEE Press,2009:1990-1997.   
[39] Thrun S,Burgard W,Fox D.Probabilistic robotics [M].Cambridge: MIT Press,2005: 213-232.   
[40]俞德崎，李广云，王力，等.激光 SLAM 测图精度评定[C/OL]/ 第 九届中国卫星导航学术年会．[2018-08-12].htp://cpfd.cnki.com. cn/Article/CPFDTOTAL-ZKBD201805009045．htm．（Yu Deqi，Li Guangyun, Wang Li, et al. Laser SLAM mapping precision assssment [C/OL]/ Proc of the 9th China Satellite Navigation Academic Annual Meeting. [2018-08-12]. http://epfd. cnki. com. cn/Article/CPFDTOTAL-ZKBD201805009045.htm.）   
[41] Smith R, Self M,Cheeseman P. Estimating uncertain spatial relationshipsinrobotics[J].MachineIntelligence& Pattern Recognition, 1988,5 (5): 435-461.   
[42] Montemerlo M,Thrun S,Koler D，et al.FastSLAM:a factored solution to the simultaneous localization and mapping problem [C]// Proc of the AAAI National Conference on Artificial Intelligence. California: AAAI press,2002: 593-598.   
[43] Grisetti G,Stachniss C,Burgard W. Improved techniques for grid mapping with Rao-Blackwellized Particle Filters [J].IEEE Trans on Robotics,2007,23 (1): 34-46.   
[44] Blanco JL. Optimal filtering for non-parametric observation models: applications to localization and SLAM [M]. Los Angeles: Sage Publications,Inc.2010.   
[45] Lu F,Milios E.Globally consistent range scan alignment for environment mapping [J]. Autonomous Robots,1997,4 (4): 333-349.   
[46] Gutmann J S,Konolige K.Incremental mapping of large cyclic environments[C]//Proc of IEEE International Symposium on Computational Intelligence in Robotics and Automation.Piscataway, NJ: IEEE Press,1999: 318-325.   
[47]高文研，平雪良，贝旭颖，等．两种基于激光雷达的 SLAM算法最优 参数分析[J]．传感器与微系统，2018,37(4):28-30.(Gao Wenyan, Ping Xueliang,Bei Xuying,et al. Optimal parameter analysis of two SLAM aIgorinms Dased on laser radar [Jj. Iransducer and Microsystem Technologies,2018,37(4): 28-30.）   
[48] Zhang J, Singh S. Visual-lidar odometry and mapping: low-drift,robust, and fast [C]//Proc of IEEE International Conference on Robotics and Automation.Piscataway,NJ: IEEE Press,2015: 2174-2181.   
[49] Daniel Lawrence LU. Vision-enhanced lidar odometry and mapping [D]. Pittsburgh: Carnegie Mellon University,2016.   
[50] Zhang J, Singh S. Laser-visual-inertial odometry and mapping with high robustnessand low drift [J/OL].(2018-07-09）[2018-10-20]. https://doi.org/10.1002/rob.21809.   
[51]邹勤．一种基于深度学习的激光 SLAM 闭环检测方法：中国， CN107403163A [P].2017-11-28.(Zhou Qin. Laser SLAM closed-loop detection method based on deep learning: China, CN107403163A [P]. 2017-11-28. )   
[52]高翔.深度相机 SLAM 的特征学习与语义地图构建算法研究 [D]. 北京：清华大学,2017.(Gao Xiang.Feature learning and semantic map reconstruction in RGB-D SLAM [D]. Beijing:Tsinghua University, 2017.)   
[53] Bok Y, Jeong Y,Choi DG, et al. Capturing village-level heritages with a hand-held camera-laser fusion sensor [J]. International Journal of Computer Vision,2011,94(1):36-53.   
[54] Shen S,Mulgaonkar Y,Michael N,et al.Multi-sensor fusion for robust autonomous flight in indoor and outdoor environments with a rotorcraft MAV[C]// Proc of IEEE International Conference on Robotics and Automation. Piscataway,NJ: IEEE Press,2014: 4974-4981.   
[55] Lynen S,Achtelik M W,Weiss S,et al.A robust and modular multi-sensor fusion approach applied to MAV navigation [C]/ Proc of IEEE/RSJ International Conference on Intelligent Robots and Systems. Piscataway,NJ:IEEE Press,2013:3923-3929.   
[56]石鹏，吕品，赖际舟，等．动态环境下基于激光雷达的 SLAM 方法： 中 国,CN107991680A[P].2018.05.04.(Shi Peng,Lv Pin,Lai Jizhou, et al.Lidar based SLAM method in dynamic environment: China, CN107991680A[P]. 2018.05.04.）)   
[57] Zhang J,Singh S.Low-drift and real-time lidar odometryand mapping [J].Autonomous Robots,2017,41 (2): 1-16.   
[58] Park C,Moghadam P,Kim S,et al.Elastic lidar fusion:dense map-centric continuous-time SLAM [Cl// Proc of IEEE International Conference on Robotics and Automation.Piscataway,NJ:IEEE Press, 2018: 1206-1213.   
[59] Droeschel D，Behnke S.Efficient continuous-time SLAM for 3D lidar-based online mapping [C]// Proc of IEEE International Conference on Robotics and Automation．Piscataway，NJ:IEEE Press,2018: 5000-5007.