# 车载动基座下交流电机控制的研究及应用

李爱萍姜晓明李佳圣（上海航天设计研究院第八设计部上海210109）

![](images/af5948783a4516cc4337a2a1b628e7fb19a976b92f87180253473ac010672def.jpg)

李爱萍 女 1980年生，硕士研究生，高级工程师，主要从事发射装置的伺服系统设计工作。

摘要：车载动基座下车辆轮胎、悬架部分的弹性变形在快速伺服控制系统中会起到一定的扰动作用，本文通过分析车体扰动对电机控制系统的影响，确定了解决动基座电机伺服系统高精度要求的关键技术是测量载车底盘自身悬挂系统的固有振动频率、根据扰动数据结果设计低通滤波器和伺服控制策略，以某型安装在动基座上的电机伺服系统为例进行了伺服系统的仿真，并将以上研究成果在该系统中进行了应用。该伺服系统最终的试验结果表明，本文中载车底盘频率的测量结果、设计的滤波器和伺服控制策略有效地抑制了车体扰动对于交流伺服电机的影响，控制精度满足系统要求。

关键词：车载动基座 车体扰动 交流电机伺服控制系统中图分类号：TM383.4

# Servomotor's Control Research and Application on Vehicle-Mounted Moving Base

![](images/9938ceacd47d00c77611c14c780c35bf5467e085a2f8f17b01f432f3ab8928f8.jpg)

Li Aiping Jiang Xiaoming Li Jiasheng (The 8th Institute of Shanghai Academy of Spaceflight Technology Shanghai210109China ）

姜晓明男 1985年生，博士研究生，主要从事发射装置的伺服系统设计工作。

Abstract: On vehicle-mounted moving base, the vehicle tire and suspension's elastic deformation will play a role in disturbances in rapid servo control system. Through the analysis of the influence of vehicle disturbance for motor control system, this article determines the key technology of high precision servo system on the moving base is to measure the cars chassis suspension system natural vibration frequency, according to the result of the disturbance data to design low-pass filter and servo control strategy, and the simulation of the servo system is also carried out. In the end,as an example,the above research results are applied to a certain motor servo system installed on moving base. The final test results show that the servo system in this paper, the filter and effectively suppresses the bodywork disturbance servo control strategy for ac servo motor, the influence of control precision meet the system requirements.

Keywords: Vehicle-mounted moving base,disturbance of vehicle, servo-motor, servo-control system

# 1 引言

为有效应对精确打击和低空/超低空突防威胁，武器系统对快速反应能力和自我生存能力提出了更高的要求，以便在行进过程中及时把握战机，快速拦截来袭目标。为了满足上述要求，具备短停稳瞄能力乃至于具备行进间高精度控制能力就成了末端防空武器所必须具备的能力。

随着现代机械化水平的发展，目标的机动性达到了一个新的高度，对稳定跟踪设备的性能提出了更高的要求[1-4]。为了满足短停运行及行进间高精度控制的需求，车辆底盘无法安装调平系统，这就带来了一个问题：车辆轮胎、悬架部分的弹性变形在快速伺服控制中会起到一定的扰动作用。在船用电机伺服系统中同样面临相同的问题，但是由于波浪频率低，对波浪扰动的抑制相对容易，且国内已有多型成功案例。车体扰动由于高频成分较多，抑制车体扰动的难度更大。

传统的车载伺服系统由于精度要求低，在控制过程中没有考虑底盘的弹性变形对伺服精度产生的影响。目前国内有多家单位都在开展短停及行进间高精度电机控制系统的研究，但控制效果均不理想，大部分伺服系统的控制精度都在 $0 . 3 ^ { \circ }$ 以上。

某项目由于其系统的特殊性，对电机伺服系统的精度要求达到了 $0 . 1 5 ^ { \circ }$ 。该项目的伺服系统在调转过程中，底盘的姿态变化值可以达到 $0 . 2 ^ { \circ }$ ，如果不对底盘的弹性变形带来的扰动进行补偿，伺服精度无法满足系统要求，而且，如果没有在伺服控制中有效避开车体的固有频率，还有可能会出现伺服系统与车体的谐振现象。因此，对载车底盘自身悬挂系统刚度及阻尼下的模态振型和固有振动频率进行测试、采集伺服系统运转过程中的车体姿态数据并寻找合适的滤波方法、选择适当的伺服控制策略并对滤波之后的数据进行补偿就成了解决动基座伺服系统高精度要求的关键技术[5-11]

本文通过分析车体扰动对电机伺服系统的影响，确定需要首先测量出车体悬挂及轮胎的固有频率，以便在控制时避开车体的固有频带；根据车体的振动频率，选择了巴特沃斯滤波器作为该系统的低通滤波器，确定了融合经典控制理论中的前馈控制和模糊参数自整定的复合控制算法作为该系统的伺服控制策略，并对控制系统进行了仿真。最终，以上研究成果被应用到了某车载电机伺服控制系统中，系统的试验结果表明，车体扰动得到了有效的抑制，电机伺服系统运行平稳，静态误差及动态跟踪效果满足整体控制系统要求。

# 2 车体扰动及固有频率的研究分析

车载动基座的扰动会给伺服系统的控制带来一定的影响，因此，需要分析该扰动对伺服控制的影响，并重点研究车体固有频率在其中起到的作用。

# 2.1车体扰动对伺服系统的影响

电机伺服系统的控制原理是将目标指令和当前位置之间的误差作为输入，通过智能控制算法计算控制量，进而控制被控对象的运动。对于安装于车载动基座之上的伺服系统，目标指令都加入了车体姿态的变化值，具体的做法是：载车的底盘上安装有定位定向设备，实时采集车体在偏航、俯仰及横滚方面的信息，火控系统将以上三维信息转换为伺服系统高低及方位两个方向的信息加入到目标指令中发送给伺服系统。目标指令中的高频扰动部分对伺服系统的控制带来一定的影响。其影响具体表现为：

（1）装置起动和停止的瞬间，由于采用轮胎结构，底盘成为一个弹性底座，装置运转的动能难以迅速消减。安装在固定平台上的伺服系统，其动能的变化能够迅速通过固定的底座衰减掉，而由于车载基座的弹性特征，动能的变化势必引起轮胎和悬架的振动，需要较长时间才能将动能衰减到位。

(2）由于底盘本身存在固有频率，伺服系统的谐振频率会因底座动力学特性的变化而下降，这就使得伺服带宽降低，从而伺服系统对于高频扰动的控制力下降。

以上各影响均需要首先测量出车体悬挂及轮胎的固有频率并加以分析，以便在控制时避开车体的固有频带，进而获得较好的控制效果。

# 2.2车体固有频率测量及分析

在底盘大梁的前后设置了4个测试点，在测试点上分别安装加速度传感器，通过路障跌落的方式对车体的频率进行了测试，测试结果如图1所示。经分析得到：车体悬挂系统自身弹簧阻尼的一阶振动频率为 $2 . 4 1 \mathrm { H z }$ ，其余频率的振动为悬架结构和大梁结构的前六阶固有振动频率，分别为$6 . 7 8 \mathrm { H z }$ 、 $1 2 . 7 0 \mathrm { H z }$ 、 $3 8 . 8 4 \mathrm { H z }$ 、 ${ 5 4 . 4 2 } \mathrm { H z }$ 、 $7 7 . 6 4 \mathrm { H z }$ 以及 $1 0 8 . 5 \mathrm { H z }$ 。这些频率的测量结果可直接用于指导伺服系统控制带宽的设计。

![](images/45e699bd4b152481a530cc85fff496a906e14baa5d809494e4fb203cbdd613e9.jpg)  
图1车体固有频率测试结果图

# 3针对车体扰动数据的滤波算法研究

在获取了车体的固有频率之后即确定了伺服系统运转过程中车体姿态数据滤波的截止频率。接下来就要确定合适的滤波算法。

在低通滤波器算法的选择方面，卡尔曼滤波器、切比雪夫滤波器和巴特沃斯滤波器等常用的滤波器都可以作为软件滤波器进行使用。卡尔曼滤波器最初的形式为简单卡尔曼滤波器，现在已经改进，提出了施密特扩展滤波器、平方根滤波器等多种改进形式，这类滤波器利用线性系统状态方程，通过系统输入输出观测数据，对系统状态进行最优估计。但是卡尔曼滤波器计算量较大，适合在离线状态下分析系统状态并进行估计；切比雪夫滤波器在通带或阻带上频率响应幅度等波动信息，与理想滤波器的频率响应曲线之间的误差较小，但在仿真之后发现滞后明显；巴特沃斯滤波器的特点是通频带内的频率响应曲线最大限度平滑，没有起伏，而在阻频带则逐渐下降为零，比较适合本系统的情况，因此，最终选择巴特沃斯滤波器作为低通滤波器算法，以谐振频率 $2 \mathrm { { H z } }$ 作为分界点，对伺服软件接收到的目标数进行滤波，滤除车体姿态信息中的高频数据分量，仅对低频数据进行补偿控制，以避免谐振对系统的共振影响。

在本系统中设计了四阶巴特沃斯滤波器，采用如下的表达形式对数据进行了仿真

$$
G ( z ) = \frac { 0 . 0 0 2 2 3 5 ( z + 1 ) ^ { 4 } } { ( z ^ { 2 } - 1 . 2 1 3 z + 0 . 3 8 4 ) ( z ^ { 2 } - 1 . 4 8 z + 0 . 6 8 8 7 ) }
$$

高低及方位方向上的扰动滤波前后的效果如图2和图3所示，低通滤波效果明显。

以滤波后的数据作为伺服控制算法的输入指令，可以大大减少高频成分对伺服控制效果的影响，使得伺服系统仅对低频数据进行补偿控制，可以在一

![](images/2bfb91927ab14f394ba028a5c97b84891ec31820371186668fb350d2a053d66b.jpg)  
图2高低向扰动滤波前后的效果图

![](images/df6c58d0722d9427f5469fbbe181a9d73bfd4086bc864cdffafd4979950e91b8.jpg)  
Fig.1The measuring diagram for vehicle's fixed frequency   
Fig.2The effect picture on elevation before and after adopting filterarithmetic   
图3方位向扰动滤波前后的效果图  
Fig.3The effect picture on athemath before and after adopting filter azimuth

定程度上避免谐振对系统的共振影响。

# 4电机伺服控制策略的确定及仿真结果

根据对扰动数据精度要求的分析，采用了融合经典控制理论中的前馈控制和模糊参数自整定的复合控制算法作为系统的伺服控制策略，并在Matlab软件中选用交流电机模型建立了一套仿真模型结构，以滤波后的数据作为输入指令进行了仿真计算。具体基本仿真结构图如图4所示。

仿真结果如图5和图6所示（由于篇幅的原因，本文只列出方位仿真结果)，在正常跟踪后，正弦跟踪误差及等速跟踪误差仿真结果均在 $0 . 1 ^ { \circ }$ 以内。方位等速跟踪曲线如图7所示。

# 5 伺服系统具体设计

根据车体频率的测试结果、数据滤波及算法仿真效果，开展了某型伺服系统的具体设计。

伺服系统由PowerPC控制器、信号控制单元、电机、电机驱动器、位置采集传感器、装置安全机构及控制软件组成，控制对象为某发射装置，而装置安装在载车底盘上。载车底盘上安装有定位定向设备，可以实时地采集车体姿态信息。火控系统将雷达数据加入车体姿态信息后生成目标指令信息，PowerPC控制器通过CAN通信接口接收火控系统发送过来的指令信息后进行巴特沃斯滤波，同时接收电机伺服系统的位置信息，并根据指令及位置信息对控制量进行计算；方位及高低位置传感器通过CAN通信接口与控制器进行通信，传输伺服系统的位置信息；伺服控制软件中采用了智能控制算法，通过PowerPC控制器进行软件运行及控制量计算后，经由D-A转换板将控制信号转换成模拟量控制电机进行转动；信号检测单元用于对该装置的限位等安全信号进行采集，为控制软件的安全性设计提供数据来源。伺服系统总体框图如图8所示。

![](images/cc152df35ed316dd0e16f64448c3e966daf21d3d7a8b0c40b27a49d37b966ee9.jpg)  
图4Matlab搭建的电机伺服系统仿真结构图Fig.4Servo-control structure diagram in Matlab

![](images/bc7ae47e915d1b132b912fdd10b4057272b5f242ed023f3a98e57c6b3b428e7e.jpg)  
图5方位正弦跟踪曲线

![](images/45d2741258e8c6ae551003f2daed229e50bb8744d8d7515156eccaf26e4ba8d2.jpg)  
Fig.5Sine tracking simulation curve for elevation   
图6方位正弦跟踪误差  
Fig.6Sine tracking simulation curve for azimuth

![](images/ad5edd0041bc67507f1d4d7963b22a0dcb3220e039daf1fca9b8fd40f0ec2d2e.jpg)  
图7方位等速跟踪曲线  
Fig.7Constant speed tracking simulation curve for azimuth

在伺服控制软件中按照四阶巴特沃斯滤波器的表达形式对接收到的火控指令进行了滤波，滤波效果与仿真效果相近，起到了明显的高频扰动抑制作用。

同时，为了解决伺服系统动能的变化会引起轮胎和悬架的振动进而需要较长时间才能将动能衰减

信号检测 发射装置单元 安全信号↑ CAN通信方位位置传感器  
PowerPC CAN通信高低位置传感器  
控制器方位电源↑ 控制信号 电机 方位驱动器 电机D-A方位电源、  
转换板 控制信号 电机 高低驱动器 电机

到位的问题，将电流环及控制算法中的参数进行了优化，采取了加长电机的加减速时间、增大积分常数、将控制量进行平滑处理等措施来完善伺服系统的控制效果。

# 6 伺服系统试验验证效果

经过前期的调试，伺服系统的运行效果最终满足了系统的要求，其静态精度为 $0 . 0 5 ^ { \circ }$ ，动态跟踪精度达到了 $0 . 1 5 ^ { \circ }$ ，满足整体系统对于短停精确控制的要求。图9和图10是伺服系统在进行正弦运动及等速运动时的波形效果图。

![](images/acd467a283d9d25b5c15126eec62a706f102b98adf100d90729ffae680c10f76.jpg)  
Fig.8General diagram for servo-control system   
图9方位向正弦运行波形图

![](images/f61b8b197ebf3a8cde636503a1260d28e4ef7fc6fc1ee2cc0629ef2eabf6fecc.jpg)  
图8伺服系统总体框图  
Fig.9Sine tracking curve for elevation   
图10方位向等速运行波形图  
Fig.10 Constant speed tracking curve for azimuth

# 7 结论

本文通过分析车体扰动对电机伺服系统的影响，确定了解决车载动基座高精度电机控制系统的关键技术，即测量车体悬挂及轮胎的固有频率、设计滤波算法和伺服控制策略，针对以上3个关键要素开展了相关的测量、研究及试验，以上研究成果最终被应用到了某车载电机伺服控制系统中。该系统的试验结果表明，本文中的滤波器和伺服控制策略有效地抑制了车体扰动对电机系统带来的影响，电机伺服控制精度满足系统要求。本文的研究成果对于行进间高精度伺服系统的最终实现具有较强的借鉴意义。

# 参考文献

[1] 张运芳．交流永磁同步伺服系统研究[D]．镇江：江苏大学，2009．  
[2] 季晶晶．大惯量负载伺服系统动力学建模与控制研究[D]．南京：南京理工大学，2014.  
[3] 窦汝振．高性能永磁交流伺服系统及其新型控制策略的研究[D]．天津：天津大学，2002.  
[4] 陶永华．新型PID控制及其应用[M]．北京：机械工业出版社，2002.  
[5] 程国卿，胡金高．限速伺服系统的近似时间最优控制方案[J].西安电子科技大学学报：自然科学版，2015，42(1):180-186.Cheng Guoqing,Hu Jingao.Proximate time-optimal control scheme for speed-constrained servosystems[J]. Journal of Xidian University (NaturalScience),2015,42(1): 180-186.  
[6] 史朝晖，白明，盖东飞，等．基于专家系统的风电机组协调控制策略研究[J]．电气应用，2016,35(12): 58-61.  
[7] 焦鑫，江驹．非线性系统自适应鲁棒控制器设计[J].哈尔滨工程大学学报，2016，27(3)：402-407.Jiao Xin, Jiang Ju. Design of an adaptive robustcontroller for nonlinear system[J]. Journal of HarbinEngineering University,2016,27(3): 402-407.  
[8] Bahadur Prasad,Barjeev Tyagi. Optimal controlof nonlinear inverted pendulum system using PIDcontroller and LQR:performance analysis withoutand with disturbance Input[J]. International Journalof Automation & Computing,2014,11(6): 661-670.  
[9] Li Xiang,Chien Chern Cheah.Adaptive neuralnetwork control of robot based on a unified objectivebound[J]. IEEE Transactions on Control SystemsTechnology,2013,32(3):1032-1043.  
[10] Li Juan,Li Shihua,et al.Adaptive speed control ofa PMSM servo system using an RBFN disturbanceobserver[J].Transactions of the Institute ofMeasurement & Control,2012,34(5): 615-626.  
[11] Hu Hongjie.Hybrid adaptive compensation controlscheme for high-precision servo system[J].Transactions of Tianjin University,2013,19(3): 217-224.