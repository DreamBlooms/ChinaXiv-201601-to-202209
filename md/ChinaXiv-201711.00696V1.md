编号：147015

# 微型摆式发动机间隙内部流动数值分析

孙萌1² 张震宇¹孔文俊‘

(中国科学院工程热物理研究所，北京 100190；²中国科学院大学，北京 100039)摘要本文采用离散速度方向模型对微型摆式发动机摆臂与腔体间隙内的微尺度气体流动开展了数值研究，分析了摆臂运动对间隙内压差驱动下气体流动阻力和流量的影响规律，并探究了气体稀薄性的影响。研究发现，当摆臂运动方向与压降方向相同时，稀薄气体效应导致的速度滑移相对于气体流动阻力对流量的变化起主导作用；当摆臂运动方向与压降方向相反时，由于微尺度下壁面作用的增强，在边界附近出现气体回流，且在气流进出口处出现涡结构。

关键词间隙流动；离散速度方向模型；稀薄效应中图分类号TK431文献标识码A

# On Clearance Gap Flow in a Micro Internal Combustion Swing Engine SUN Meng1,²ZHANG Zhen-Yu1KONG Wen-Jun1

(1.Institute of Engineering Thermophysics,Chinese Academy of Sciences,Beijing 100190,China;

2.University of Chinese Academy of Sciences,Beijing 10oo39, China)

AbstractNumerical simulations on clearance gap flows between the swing arm and the engine body were completed by using the Discrete Velocity Direction(DVD） model in a Micro Internal Combustion Swing Engine.The influences ofthe movement ofthe swing arm on the gas flow resistance and fluxes driven bythe differential pressure within the gap wereinvestigated,and the effects ofrarefication were discussed.The results show that when the swing arm moves in the same direction with the drop of presure,the velocity slip caused by rarefication plays a leading role in the variation of gas flow resistance and fluxes.When the swing arm moves in the opposite direction with the drop of presure,the recirculation flow and vortex occurred near the boundary and entrance respectivelybecause of the enhancement of the wall effects.

Key wordsclearance gap flow; Discrete Velocity Direction model; rarefication effect

# 0引言

随着科技的进步，电子和机械产品趋于微型化，对能量供给单元提出更高要求。微型摆式发动机由于结构简单、效率高成为最具潜力的一种微型能源动力系统。但系统尺度减小导致动静部件之间的摩擦和泄漏损失增加。当发动机正常运行时，间隙尺度控制在微米量级，此时间隙内气体Knudsen数在$0 . 0 1 \mathrm { \sim } 1$ 之间，处于滑移流甚至过渡流领域，稀薄气体效应显著。即使采用二阶或更高阶滑移边界条件，适用于连续介质模型的Navier-Stokes方程也仅能扩展到Kn<0.5的流动领域，且误差较大[1,2]。

已经有学者对微型摆式发动机微间隙内摩擦损失和泄漏开展了研究。Gu假设间隙内气体流动处于连续流领域，用Navier-Stokes方程估算了间隙泄漏量和摩擦阻力[3]；王文等假设间隙中气流为伯努利流，采用管道流动的计算方法估算阻力损失[4]；郭志平等对采用FLUENT软件模拟间隙内的气体流动[5]。分析此前的研究可以发现，对于微型摆式发动机微间隙内气体流动阻力和泄漏的研究大多采用求解Navier-Stokes方程方法进行粗略估算，很少考虑微尺度气体流动的稀薄效应，而速度滑移和压缩性增强等微观流动特性会对发动机的气动性能产生显著影响。

本文采用精度更高的动力学方法一离散速度方向模型[7研究微型摆式发动机间隙内的气动特性,考虑微尺度气体流动的稀薄效应，探究了摆臂运动及气体稀薄性对微间隙内气体流动阻力和流量的影响规律，为改进微型摆式发动机结构，提高气动效率提供参考。

# 1离散速度方向模型验证

# 1.1离散速度方向模型简介

离散速度方向(DVD)模型是一种简化Boltzmann方程的动力学方法，它通过降低Boltzmann方程的维数来减小方程数值求解的计算量。DVD 模型在保持分子速率连续的前提下，将分子运动方向离散，用离散方向上的分子速率代替Boltzmann方程中连续的速度分布空间，将六维的Boltzmann方程降低到三维，从而减小Boltzmann方程数值求解的计算量。

# 1.2DVD模型验证

摆式发动机摆臂与缸体间的气体流动可近似认为是Couette 流动和Poiseuille 流动的结合，现分别在两种流动中验证模型精度，并将数值计算结果与线性化Boltzmann 方程(LBE)方法对比。计算中分子离散速率个数均匀选取8个，离散速度方向选取$4 \times 8$ 个。用各速率区间的分子数 $n _ { k }$ 作为控制方程变量可得DVD 模型的控制方程为

$$
\begin{array} { l } { \displaystyle \frac { \hat { \partial } n _ { i , k } } { \hat { \partial } t } + \overline { { c } } _ { k } \vec { l } _ { i } \cdot \frac { \hat { \partial } n _ { i , k } } { \hat { \partial } \vec { r } } = \pi d _ { 0 } ^ { 2 } \displaystyle \sum _ { j = 1 ( j \neq i , j \neq m + 1 - i ) } ^ { m } \frac { 1 } { m - 2 } } \\ { \displaystyle \sum _ { s = 1 } ^ { l } ( \overline { { c } } _ { k } + \overline { { c } } _ { s } ) ( n _ { j , k } n _ { m + 1 - j , s } - n _ { i , k } n _ { m + 1 - i , s } ) } \end{array}
$$

# 1.2.1Couette流动

计算得到的无量纲剪切力与LBE方法计算结果[8]对比如图1所示。

![](images/abeead96c8ca5f6f07d18049b0f4e0615a33c7541a6cc9099bf29855c94d73d2.jpg)  
图1无量纲剪切力随Knudsen数变化

Fig.1Dimensionless shear stress variation with Knudsen number 1.2.2Poiseuille流动

计算得到的无量纲流量与LBE 方法计算结果[9]对比如图2所示。

![](images/7ccdab27fb5567032e442a2af9c2261d017d9bfa42ebac0b53a9ca3dd6245460.jpg)  
图2无量纲流量随Knudsen数变化

Fig.2Dimensionless mass flux variation with Knudsen number

由图1、2可知，从滑移流到过渡流领域DVD模型计算得到的无量纲剪切力和流量与LBE方法最大误差均不超过 $3 . 2 \%$ ，计算精度明显高于滑移边界条件的Navier-Stokes方程。

# 2微型摆式发动机间隙内的气体流动

在微型摆式发动机摆臂与缸体之间的间隙内，由于摆臂运动和压差同时存在，其中的气体流动属于Couette-Poiseuille流。腔体内高温燃气进入间隙内，若间隙尺寸为5μm，Knudsen数即可达0.1左右，若间隙尺寸进一步减小，则进入过渡流领域。现分别研究摆臂运动和气体稀薄性对流动阻力和流量的影响规律。以氩气为例进行计算，初始压力为标准大气压 $1 0 1 3 2 5 \mathrm { P a }$ ，温度为273.15K，压差$\frac { d p } { d x } = - 3 . 0 2 \times 1 0 ^ { 7 } P a / m _ { \circ }$

# 2.1摆臂运动对气体流动阻力和流量的影响

计算中改变摆臂运动方向和速度，得到间隙内气体质量流量和流动阻力的变化曲线如图3、4所示。

![](images/33604f9f829b7cd787acfc0b21c49a5ebcc50d654b05661ff7158f3dd151cd42.jpg)  
图3间隙内气体质量流量随摆臂运动速度的变化 Fig.3 Mass flux variationwith the swing arm movement

![](images/a45a0be49d86763531ff2d0aef82296ce328ee129b9a8480323ef462caaa4e3a.jpg)  
图4间隙内气体流动阻力随摆臂运动速度的变化

由图3、4可知，在同一Knudsen数情况下，无论摆臂正向或反向运动，间隙内气体流动阻力均随摆臂运动速度增大而增大，可见压差对流动阻力的影响较小；在摆臂运动速度相同情况下，随Knudsen数增大间隙内气体流动速度梯度增大导致流动阻力增大。当摆臂正向运动时，气体流量随摆臂运动速度增大而增大，当摆臂反向运动时，气体流量随摆臂运动速度增大先正向减小后反向增大。气体流量随摆臂运动变化的原因可由间隙内气体流线图看出。

![](images/ec191dd0410e35f4bfef8853bc39b7ada57fa18f6a0bf3117c21c2d6fb24cd0d.jpg)  
Fig.4Flow resistance variation with the swing arm movement

![](images/49c613e0831cc855161f72daae53a6aa6dea967e8b0b44bfdb41f0876d51b175.jpg)  
图 $5 \mathrm { K n } { = } 0 . 1 1 2 8$ 摆臂反向运动速度 $0 . 1 \mathrm { m / s }$ 的流线图Fig.5Streamlinewith $\mathrm { { \Delta v = } 0 . 1 m / s }$ ， $\mathrm { K n } { = } 0 . 1 1 2 8$   
图 $6 \mathrm { K n } { = } 0 . 1 1 2 8$ 摆臂反向运动速度 $0 . 1 5 \mathrm { m / s }$ 的流线图Fig.6 Streamline with $\scriptstyle \mathrm { v = 0 . 1 5 m / s }$ $\mathrm { K n } { = } 0 . 1 1 2 8$

![](images/5167c9f30ff570623251e0e49e0b7acf7b71859a1f257f7531dda8e3b733397e.jpg)  
图 $7 \mathrm { K n } { = } 0 . 3 3 8 5$ 摆臂反向运动速度 $0 . 1 \mathrm { m / s }$ 的流线图Fig.7 Streamline with $\mathrm { { \Delta v = } 0 . 1 m / s }$ $\mathrm { K n } { = } 0 . 3 3 8 5$

![](images/3ce36a13058c54cdbcb5329d46beefd0f10a5810d7618f195757b7a8adb71050.jpg)  
图 $8 ~ \mathrm { K n } { = } 0 . 3 3 8 5$ 摆臂反向运动速度 $0 . 1 5 \mathrm { m / s }$ 的流线图Fig.8 Streamline with $\scriptstyle \mathrm { v = 0 } . 1 5 \mathrm { m / s }$ $\mathrm { K n } { = } 0 . 3 3 8 5$

由图5-8可知，当摆臂反向运动时在近壁区气体出现回流。当Knudsen数相同时，随摆臂运动速度增大回流区逐渐扩大；当摆臂运动速度相同时，随Knudsen数增大回流区逐渐扩大。 $\mathrm { K n = 0 } . 1 1 2 8$ 时，回流区扩大至主流区域，且在气流的进出口处出现明显的涡结构，此时壁面运动与压差作用对气体流动的驱动作用几乎相同； $\mathrm { K n } { = } 0 . 3 3 8 5$ 时，气体全部反向流动，此时壁面作用的影响已扩大至全部流场区域，间隙泄漏量主要由摆臂运动速度决定。由此可知，对于微型摆式发动机微间隙内的气体流动，特征尺度决定了控制间隙泄漏流动方式的主要因素。

# 2.2稀薄性对气体无量纲流动阻力和流量的影响

计算中改变气体流动的Knudsen数，气体无量纲质量流量和流动阻力的变化曲线如图9、10所示。

由图9可知，当摆臂正向运动时，随气体稀薄性增强区域中心处气体速度迅速减小导致间隙内气体的无量纲质量流量减小。由图10可知，随气体稀薄性增强，无量纲流动阻力增大，摆臂运动速度和方向对流动阻力影响较小。

![](images/c4ebf33a4133d57ea0825785b704d50ef3a2c4dfa4bf78ef14d767c545b67943.jpg)  
图9无量纲流量随Knudsen数的变化

![](images/946889453db31ac388e1f111effe7e681503d673993c080aff44d7d27f742253.jpg)  
Fig.9Dimensionless mass flux variation withKnudsen number   
图10无量纲流动阻力随Knudsen数的变化 Fig.10 Dimensionless shear stress variation with Knudsen number

# 3结论

本文采用离散速度方向模型研究微型摆式发动机摆臂与缸体之间微间隙内的微尺度气体流动，探究了气体稀薄性和摆臂运动对间隙内压差驱动下的气体流动阻力和流量的影响。主要得出如下几点结论： (1)摆臂运动方向与压降方向相同时，随摆臂运动速度增大，气体质量流量增大； (2)摆臂运动方向与压降反向相反时，随摆臂运动速度增大，气体质量流量先减小后增大，近壁区及进出口处出现回流区和涡结构； (3)无论摆臂运动方向与压降方向是否相同，气体流动阻力均随摆臂运动速度增大而增大。对微型摆式发动机间隙内的稀薄气体流动而言，当摆臂运动方向与压降方向相同时，应尽量降低摆臂运动速度，以减小间隙气体泄漏量；而当摆臂运动方向与压降方向相反时，应综合考虑间隙内气体流动阻力和泄漏量对整机效率的影响，设计摆臂的最佳运动速度以提高系统的运行效率。

参考文献   
[1]谢,樊菁．Navier-Stokes 方程二阶速度滑移边界条件的检 验[J]．力学学报,2007,39(1):1-6 XIE Chong， FAN Jing. Assessment of Second-Order Velocity-Slip Boundary Conditions of the Navier-Stokes Equations[J].Cninese Journal of Theoretical and Applied Mechanics,2007,39(1): 1-6   
[2]Roohi E,Darbandi M. Extending the Navier-Stokes Solutions to Transition Regime in Two-Dimensional Micro-and NanochannelFlowsUsingInformationPreservation Scheme[J].PhysicsofFluids， 2009, 21(8): 082001-1-082001-12   
[3]Gu Yongxian. Gasdynamic Modeling and Parametric Study of Mesoscale Internal Combustion Swing Engine/Generator Systems[D]. United States: University of Michigan, 2006   
[4]王文，朱红海，乔显力，等．摩擦对微型摆式发动机工作 性能的影响模拟[J]．工程热物理学报,2006,27(6):926-928 WANG Wen, ZHU Honghai, QIAO Xianli, et al. Impact of Friction on Performance of Micro Swing Engine[J]. Journal of Engineering Thermophysics,2006,27(6): 926-928   
[5]郭志平，王燕飞，李冠孚，等．微型摆式内燃机密封结构的 设计及分析[J]．润滑与密封,2013,38(8):83-86 GUO Zhiping,WANG Yanfei, LI Guanfu, et al. Design and Analysis on Micro Free Swing Piston Engine Seal Structure[J]. Lubrication Engineering,2013,38(8): 83-86   
[6]ZHANG Zhenyu, XU Jianzhong, QI Zhiguo, et al. A Discrete Velocity Direction Model for the Boltzmann Equation and Applications to Micro Gas Flows[J]. Journal of Computational Physics,2008,227(10): 5256-5271   
[7]彭程，张震宇，徐建中．过渡领域气体流动中的离散速度 方向模型应用[J]．工程热物理学报,2013,34(6):1031-1035. PENG Cheng， ZHANG Zhenyu， XU Jianzhong.The Application of Discrete Velocity Direction Model in Gas Flows in Transition Regime[J]. Journal of Engineering Thermophysics,2013,34(6): 1031-1035   
[8]Sone Y, Takata S,and Ohwada T. Numerical Analysis of the Plane Couette Flow of a Rarefied Gas on the Basis of the Linearized Boltzmann Equation for Hard Sphere Molecules[J]. European Journal of Mechanics,1990,9(3): 273-288   
[9]Ohwada T, Sone Y,and Aoki K. Numerical Analysis of the Poiseuille and Thermal Transpiration Flows Between Two Parallel Plates on the Basis of the Boltzmann Equation for Hard-Sphere Molecules[J].Physics of Fluids,1989,1(12): 2042-2049