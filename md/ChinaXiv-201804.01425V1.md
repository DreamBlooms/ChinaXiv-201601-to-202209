# 基于ROS的ICP-SLAM在嵌入式移动机器人上的实现与优化

郑富瑜，何苗，张辉，赵韦人，熊德平，梁安辉，王成民，王润，周海亮

(广东工业大学 物理与光电工程学院，广州 510006)

摘要：基于激光雷达的ICP-SLAM在机器人操作系统中无法直接运行，且通过PC实现算法时，没有高效运载计算机资源，产生资源浪费，同时降低了移动机器人系统的灵活性。通过在嵌入式系统中搭建机器人操作系统，在系统中移植 MRPT函数库中的ICP-SLAM算法，对算法进行优化，调整算法运行的CPU占用率，使用基于激光雷达的移动机器人进行建图。结果表明机器人操作系统生成的栅格地图可以满足机器人自主导航的需求，SLAM效果更为直观，系统更加灵活，成本和硬件配置要求大大降低。证明优化后的算法更贴近实际的使用需求。

关键词：ICP-SLAM；ROS；移动机器人；嵌入式系统 中图分类号：TP242 doi:10.3969/j.issn.1001-3695.2017.12.0820

# Implementation and optimization of ROS based ICP-SLAM embedded robot

Zheng Fuyu, He Miao†, Zhang Hui, Zhao Weiren, Xiong Deping, Liang Anhui, Wang Chengmin, Wang Run, Zhou Hailiang (School ofPhysics&OptoelectronicEngineering Guangdong UniversityofTchnology,Guangzhou 510o06,China)

Abstract:Laser-based ICP-SLAMcannotrundirectly in therobot operating system,andthere is no eficientcarryingof computerresources when implementing the algorithmonPC,resulting in waste ofresources,while reducing the flexibilityof mobile robot system.Build robot operating systemon the embedded system,transplant the ICP-SLAMalgorithmofthe MRPT library ntothe system,optimizeandfixthe CPUoccupancyrateofthealgorithm,testhe functionofSLAMbythe mobilerobot based on the LIDAR.The results showthatthe grid map thatrobot operating system generated have met the requirements of robotautonomous navigation,andtheffectofSLAMis more intuitive,besides,thesystemis more flexible,greatlyreducecost and hardware configuration requirements.Proved that the optimized algorithm is closer to the practical requirements.

Keywords:ICP-SLAM; ROS; mobile robot; embedded system

# 0 引言

即时定位与构建地图（SLAM）技术是移动机器人实现自主导航的关键，在未知环境中，通过传感器对周围进行探测，构建出环境地图，对机器人进行定位，从而结合传感器生成的实时地图进行导航。在SLAM的研究过程中，使用视觉传感器的方式容易受到环境光的干扰，生成的数据量巨大，限制了传感器的应用环境，同时提高了数据处理的成本[1]。移动机器人进行SLAM时，通过传感器收集到的数据还原环境分布，使用算法求解机器人的位姿[2]。ICP 算法由Besl和 McKay 于1992 年提出，是一个快速且精确的算法，在图像和点集的配准中得到广泛的应用[3]。由于初值不佳或者在扫描匹配过程中出现误差，

ICP算法在可能会收敛到局部最优点上，提高了算法对于传感器的要求[4]。ICP-SLAM 算法将新的测距扫描结果与上一次结果生成的点云图进行匹配，从而增量地构建地图[5]。点云图随着时间的推移计算量持续增大，增加了系统的负担[。ICP-SLAM需要比特征提取更多的计算量，在PCLinux 系统中使用ICP-SLAM，结合高分辨率的激光雷达可以较好的实现高精度的SLAM效果，但使用PC相当于提高硬件配置，且只占用PC很小一部分的功能，造成功能浪费和成本增加[]。但移动机器人的普通嵌入式开发板配置不够，无法实现高精度的地图构建和机器人实时定位。MRPT库中的ICP-SLAM没有在ROS中的节点，无法使用ROS评估工具进行仿真平台的验证。

针对以上ICP-SLAM无法在ROS中运行，硬件配置要求对于移动机器人普通嵌入式不适用的问题，本文将MRPT $\mathrm { C } { + } { + }$ 库中的ICP-SLAM移植在移动机器人嵌入式开发板上，保留算法的部分源码并作出修改，优化地图构建中的耗时与计算资源的部分，增加基于栅格地图实时轨迹显示部分等。移植后的ICP-SLAM大大降低了对硬件平台的要求，提高了系统的灵活性，显示效果更为直观，还添加了实时轨迹的显示，提升了SLAM的性能，精确反映了周围环境的布局。

# 1 算法优化与改进

# 1.1 总体流程设计

本文将PC 端的MRPT $\mathrm { C } { + } { + }$ 库中的ICP-SLAM进行移动机器人嵌入式ROS平台中的移植和优化，最终在显示终端显示基于ROS平台的包含运动轨迹的栅格地图，即地图的实时构建。算法可以分成以下几个步骤：完成选择控制点，扫描匹配，通过最小化匹配点误差方程求出旋转矩阵与平移矩阵，即时定位和地图构建。总体的系统设计流程如图1所示。选择控制点在激光雷达与里程计部分完成，扫描匹配之后，进行迭代求出旋转、平移矩阵，不断迭代，求解机器人的运动，完成即时定位和地图构建。

![](images/0d94ebaa5980d51721ec910cdf5a1b074dac5475709f612ed0b85e9fbe195cc2.jpg)  
图1总体设计流程

在上述系统设计流程中，本文通过修改ICP-SLAM算法源代码部分的 $C { + } { + }$ 代码，同时删去了与本文ICP-SLAM方法不同的源代码，包括 MRPT $\mathrm { C } { + } { + }$ 库中的 EKF、RBPF 和 Graph-slam方法；在地图的匹配方式与方法上进行改进，优化算法对于CPU 需求的计算量；在ROS的图形显示工具中进行 SLAM,并添加路径的显示。

# 1.2ICP-SLAM 源代码

ICP-SLAM算法的主要在src 和 include文件夹下实现，在mrpt_icp_slam_2d_wrapper.cpp 中使用栅格地图数据 occu_msg替换点云地图数据；对匹配点搜索使用的方法进行修改，将 icpslam-live.ini 文件中的匹配方法ICP_algorithm 改为 grid map,使用栅格图进行扫描匹配激光雷达得到的环境地图；在mrpt_icp_slam_2d_wrapper.cpp加入读取里程计的读数odom 的函数，再对里程计的读数进行四元数的转换，为扫描匹配初期ICP 算法提供初值姿态矩阵，ICP算法加入机器人里程计提供初始姿态矩阵，大大减少初始时刻全局搜索带来的时间消耗。在mrpt_icp_slam_2d_wrapper.cpp 中 删 去3D 显示窗口3DWindows，关闭同时定位与地图构建的实时显示，同时添加轨迹显示updatetrajectory，采用基于ROS 的图形工具RVIZ 进行界面和轨迹的显示。

# 1.3扫描匹配

进行扫描匹配时，最邻近点迭代（iterativeclosestpoint，ICP）算法通过最小化匹配误差求解旋转矩阵与平移矩阵，在MRPT$\mathrm { C } { + } { + }$ 库中有多种不同的方法。算法对扫描得到的数据帧进行匹配、更新局部区域地图、调整局部地图偏差，由于缺少初始姿态矩阵，达到收敛条件需要的迭代次数大量增加。考虑到耗时且使用里程计提供初始姿态矩阵对于扫描匹配的精度影响较小，同时迭代次数减少降低了对嵌入式开发板CPU计算量的载荷，为嵌入式的引入提供契机。

ICP算法在MRPT $C { + } { + }$ 库中有多种方法，主要包括经典点云匹配方法，经典ICP方法（ClassicICP）[8]，列文伯格-马夸尔特方法(Levenberg-Marquardt,LM)[9]、八叉树图方法(octomap)[10]和栅格地图方法（gridmatch）等[1]。本文将扫描匹配算法中点云匹配的方式调整为栅格地图匹配，避免了后期点云匹配长时间匹配产生的大量迭代计算，确保精确率的基础上降低对硬件的要求，更加适用于嵌入式开发板的配置。优化后的扫描匹配流程如图2所示。激光雷达采集到数据之后，通过对编码器为主要结构的里程计读数进行检测，机器人位移小于一定阈值时，不进行旋转平移匹配，沿用上一帧栅格图。

![](images/52ed40831c063e6ad3bb679d41832cf65023f9fc8696a9ecab479339f414862a.jpg)  
图2扫描匹配流程

# 1.4ROS 显示与观测

机器人操作系统(ROS)是一个机器人软件操作平台，前身由斯坦福大学人工智能研究所(Stanford Artificial IntelligenceLaboratory)所研发。ROS可以建立节点管理器，从命令行客户端查看特定主题不断发布的消息数据[12]。

为了能够借助ROS的评估工具和功能，在嵌入式开发板上安装Ubuntu并搭载ROS平台，订阅激光雷达采集数据后发布的Laserscan主题。在ROS中创建节点，移植ICP-SLAM算法，将源代码放置于src文件夹下，将ini可执行文件放置于tutorial文件夹中，创建launch文件同时驱动多个节点，包括订阅激光雷达发布的主题的节点、使用ICP-SLAM可执行文件进行建图的节点和使用ROS图像显示界面工具RVIZ进行实时显示建图过程。同时，在RVIZ的实时显示中添加机器人的运动轨迹。ROS中主题的发布与订阅如图3所示。通过订阅移动机器人里程计发布的主题odom和激光雷达发布的主题scan，ICP-SLAM算法会对采集到的数据进行处理。

![](images/028ad9de90bf6561f0ee770107e89c4e9f27d0f1dce91272623fecc1f5a0e9d5.jpg)  
图3ROS主题发布与订阅

# 2 算法的测试与结果解析

# 2.1测试硬件配置

测试的硬件配置为台式计算机、激光雷达和自制的移动机器人底盘，将使用台式计算机运行算法与机器人采用嵌入式开发板独立运行算法的对比。机器人采用的激光雷达采用二维激光雷达，移动机器人底盘模块主要由上位机和下位机组成，上位机主要由移动机器人普通嵌入式开发板树莓派三代和PC组成，树莓派负责激光雷达获取数据的处理、ROS软件上ICP-SLAM 算法的运行和机器人移动命令的发布，PC用于显示开发板处理之后的数据和图形界面，并未参与到算法的计算部分，仅发挥观测的作用。下位机主要由基于ArduinoUno的开发板、电机驱动板、集成磁电编码器的直流电机和电源组成，基于ArduinoUno的开发板主要负责机器人的移动功能实现，集成磁电编码器的直流电机负责产生里程计数据,机器人的上、下位机供电统一由电源提供。测试硬件配置实物图如图4所示，分别是机器人整体图、树莓派开发板与激光雷达。

![](images/47f76b9c339115de0896c99148de23f94c207e8c41053ee1e22d2e2effad2c59.jpg)  
图4硬件配置实物图

进行算法的测试时，个人电脑计算能力强，存储空间大，但运行ICP-SLAM时只用到小部分运算能力，对于移动机器人开发而言，个人电脑与机器人的捆绑开发不仅导致未使用的计算资源严重浪费，且提升了硬件配置成本和功耗，降低了系统的灵活性与集成性。嵌入式开发板以其低成本、低功耗、体积小和适当的CPU运算效率等优点，成为SLAM算法运行时个人电脑的替代品。表1所示为个人电脑与嵌入式开发板树莓派三代的硬件参数对比。除此之外，硬件的价格上，树莓派只需要40美元左右，价格约为PC的 $10 \%$ 。

表1硬件参数对比  

<html><body><table><tr><td></td><td>PC</td><td>Raspberry Pi</td></tr><tr><td rowspan="2">CPU</td><td>Intel(R) core(TM)i5-4660</td><td>Quad Core 1.2GHz Broadcom</td></tr><tr><td>CPU@3.20GHz</td><td>BCM2837 64bit CPU</td></tr><tr><td>Storage</td><td>777GB</td><td>Micro SD card 32GB</td></tr><tr><td>Memory</td><td>4GDDR31600MHz</td><td>1GB</td></tr></table></body></html>

# 2.2不同匹配算法仿真对比

使用不同的ICP匹配算法进行扫描匹配时，精确程度不尽相同，除了实时建图质量可以反映精度之外，还可以通过ICP-SLAM定位功能生成的轨迹来判断。不同算法产生的轨迹与真实值之间的误差不同，为了得到轨迹的真实值，使用MRPT $\mathrm { C } { + } { + }$ 库apps文件夹下的模拟器，通过运行模拟器中的模型机器人，在模拟的环境中进行运动，得到运行轨迹的真实值文件和数据包，通过选择不同ICP匹配算法运行同一数据包，得到对应的轨迹文件，使用MATLAB仿真对比轨迹真实值与MRPT $\mathrm { C } { + } { + }$ 库中几种不同的匹配算法产生的轨迹，包括气体映射方法（gas_mapping）、列文伯格-马夸尔特方法(Levenberg-Marquardt,LM）、八叉树图方法（octomap）和栅格地图方法（gridmatch）与真实值（GroundTruth）的轨迹，得到的轨迹图如图5所示。不同匹配方法与真实值的方差如表2所示。

![](images/dda87c6c9075f8314a2987c54e4adaaa70a48391de9e32aa9a0e6303aceea8bc.jpg)  
图5不同匹配方法轨迹图

表2不同匹配方法与真实值的方差  

<html><body><table><tr><td>MatchingAlgorithm</td><td>Gridmap</td><td>LM</td><td>Classic</td><td>Octomap</td></tr><tr><td>Variance</td><td>0.0042</td><td>0.0021</td><td>0.0155</td><td>0.049</td></tr></table></body></html>

根据表2，使用列文伯格-马夸尔特方法（LM）与真实值的方差最小，为0.0021，小于使用栅格地图方法的方差0.0042，但在嵌入式开发板运行过程中，使用LM方法的CPU的占用率远大于使用栅格地图，当CPU占用率过高时，算法的运行速度和数据处理速度会受到限制，即时建图容易产生漂移，导致地图的精度下降甚至无法建立完整的地图。表3所示为算法运行时嵌入式开发板运行的CPU占用率。由于嵌入式开发板的CPU计算资源十分宝贵，列文伯格-马夸尔特方法明显对CPU的消耗更大，当嵌入式开发板在移动机器人上使用时，复杂的环境会导致CPU的浮动更加明显，更低的CPU消耗让开发板的容错率更高，鲁棒性更好。

表3不同匹配方法嵌入式开发板的CPU占用率  

<html><body><table><tr><td>Algorithm</td><td>Max</td><td>Average</td><td>Min</td></tr><tr><td>Gridmap</td><td>40.35%</td><td>38.76%</td><td>36.84%</td></tr><tr><td>LM</td><td>56.82%</td><td>49.84%</td><td>48.34%</td></tr><tr><td>Classic</td><td>50.77%</td><td>47.68%</td><td>45.31%</td></tr><tr><td>Octomap</td><td>66.58%</td><td>63.49%</td><td>62.44%</td></tr></table></body></html>

# 2.3 优化后的算法测试

测试场地为 $7 . 8 \mathrm { m } \mathrm { x } 1 5 \mathrm { m }$ 大小的办公区域，使用基于二维激光雷达的移动机器人底盘进行即时定位和建图。图6所示为机器人底盘SLAM生成的地图，黑色部分是障碍物，白色为可通行区域，绿色实线为机器人底盘的运动轨迹。对比图7使用嵌入式开发板运行MRPT $\mathrm { C } { + } { + }$ 库中的ICP-SLAM生成的地图与图8使用PC作为运算单元运行MRPT $\mathrm { C } { + } { + }$ 库ICP-SLAM生成的地图，图6使用嵌入式开发板运行改进后的ICP-SLAM算法的方式生成的地图可以明确辨认出障碍物的位置、环境的布局、机器人运动的轨迹，验证了使用嵌入式开发板的可行性与实用性。图7由于嵌入式开发板在运行时内存耗尽，容易产生地图漂移，导致即时建图的准确率降低，而图8由于PC硬件配置较高，建图时清晰度与对比度较高，并在运行中添加机器人模型，但该图生成时，算法选择点云与栅格图同时生成，让边缘部分厚度增加，且没有路径显示，不能够直观反映机器人的实时定位。

![](images/967b322f40925c925fdf29973565ba43c414c6414b4b39c8a42527839214089a.jpg)  
图6ICP-SLAM构建地图

![](images/acc0b80e2426ef9d27714847def1a6bc84d7ae548f13c98a1808c5c1e9a1593b.jpg)  
图7MRPT $\mathrm { C } { + } { + }$ 库ICP-SLAM

![](images/b0e6b048b978996124053c4ae141f8cc42f9175929f6fa1ec0f39ed452385c1e.jpg)  
图8PC 运行ICP-SLAM

# 2.4 总体改进效果

将移植后的ICP-SLAM在嵌入式开发板上运行与在系统中运行MRPT $\mathrm { C } { + } { + }$ 库中的ICP-SLAM进行对比，同一个数据包，在嵌入式开发板系统中使用MRPT $\mathrm { C } { + } { + }$ 库中原始的ICP-SLAM运行时，迭代的总次数为27349次，运行时间为 $1 5 \mathrm { \ m i n } \ 3 7 \mathrm { \ s }$ 使用优化后ICP-SLAM算法迭代次数为2954次，运行时间为$5 \ \operatorname* { m i n } 2 9 \ \mathrm { s }$ ，CPU占用率上，使用MRPTC $^ { + + }$ 库中原始的ICP-SLAM平均值达到 $13 6 \%$ ，优化后降低到了 $3 8 . 7 6 \%$ 。移植后的算法提高了运算速率，同时降低了CPU占用率，确保了运行时算法的测量准确率不会因CPU资源耗尽而产生下滑。

将生成的地图通过ROS 节点map_server 保存下来，移动机器人使用自适应蒙特卡洛定位（adaptiveMonteCarlolocalization，AMCL）算法，结合激光雷达进行室内的导航，导航效果如图9所示。

![](images/02dba026dc88754623048a6d7620aa4b4e0a6d6d3f3276659f4f4742e402f5b9.jpg)  
图9保存地图进行导航

# 3 结束语

本文提出并实现了将ICP-SLAM进行改进和优化，移植到移动机器人嵌入式开发板树莓派三代中，最终实现了SLAM;同时算法的运行速度和CPU占用率两方面得到提升，大大降低了移动机器人实现SLAM硬件配置要求和设备的成本。针对嵌入式开发板运算速率有限导致MRPT $\mathrm { C } { + } { + }$ 库中ICP-SLAM不适用的问题，在保证精确率的基础上，通过修改原点云图匹配方式为栅格图匹配，去除ICP-SLAM实时显示界面，降低了算法对CPU计算量的需求，缩短了算法运行耗时。关于构建地图过程中显示不够直观的问题，采用在ROS平台上使用RVIZ图像显示界面，结合自带评估工具在PC终端中进行显示；同时添加了路径显示功能，既符合现在的机器人研究趋势，又更加直观地反映了实际环境的布局。通过对算法的改进，从而提高了移动机器人的集成度和灵活度，降低了移动机器人的硬件成本。随着嵌入式技术的不断发展，嵌入式机器人的功能将不断延伸，普及生活中的更多领域。

# 参考文献：

[1]KimJ,JeongJ, ShinY S,etal.LiDAR configuration comparison for urban mapping system [C]//Proc of the 14th IEEE International Conference on Ubiquitous Robots and Ambient Intelligence.2017: 854-857.   
[2]Mendez O,Hadfield S,Pugeault N,et al. SeDAR-semantic detection and ranging: humans can localise without LiDAR,can robots?[J].arXiv preprint arXiv: 1709.01500,2017.   
[3]BeslPJ,McKayND.Method for registration of3-D shapes[J].IEEE Trans on Pattern Analysis and Machine Intelligence,1992,1611 (2):239-256.   
[4]Tiar R, Ouadah N,Azouaoui O,et al. ICP-SLAM methods implementation

on a bi-steerable mobile robot [C]// Proc of the 1lth IEEE International Workshop of Electronics,Control，Measurement，Signalsand their Application to Mechatronics.2013:1-6. [5]Ghorpade VK, Borrmann D,Checchin P,et al. Time-of-flight depth datasets for indoor semantic SLAM[J/OL].[2017-12-01]. https://www.researchgate. net/publication/319464322_Time-offlight_depth_datasets_for_indoor_semantic_SLAM. [6]Georgiou C,Anderson S,Dodd T. Constructing informative Bayesian map priors: a multi-objective optimisation approach applied to indoor occupancy grid mapping[J]. The International Journal of Robotics Research,2017,36 (3): 274-291. [7]Mur-Artal R,Tardos JD.Probabilistic semi-dense mapping from highly accurate feature-based monocular SLAM [M]// Robotics:Science and Systems. 2015. [8]Thorpe M. Gas mapping LiDAR for large-area leak detection and emissions monitoring applications [M]// CLEO: Applications and Technology. Optical Society of America.2017. [9] Li Haoran,Zhang Qichao,Zhao Dongbin. Comparison of methods to efficient graph slam under general optimization framework [C]//Proc of the 32nd Youth Academic Annual Conference of Chinese Association of Automation.2017: 321-326. [10] Vlaminck M,Luong H,Philips W. Multi-resolution ICP for the efficient registration of point clouds based on octrees [Cl//Proc of the 15th IAPR International Conference on Machine Vision Applications.2017:334-337. [11] Sasongko DF, Miura J. An integrated exploration and observation planning for an efficient indoor 3D mapping [C]// Proc of IEEE International Conference on Mechatronics and Automation.2017:1924-1929. [12] Garage W. Robot operating system (ROS)[Z].2012.