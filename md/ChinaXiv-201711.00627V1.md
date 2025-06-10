# 几种仿生翼型气动性能及噪声特性研究

李典 刘小民

（西安交通大学能源与动力工程学院，陕西西安710049）

摘要：依据翼型理论分别提取四种鸟类翅膀沿展向 $40 \%$ 截面处的翼型，采用大涡模拟结合声类比的FW-H方程的方法对不同仿生翼型进行流场及声场的模拟。非定常流场的计算结果表明，在逆压梯度作用下，气流在叶片吸力面前缘开始分离；在叶片下游处产生了明显的涡结构，脱离叶片尾缘后涡结构发生破碎。在四种仿生翼型中，海鸥翼型的升阻比最大，鸮翼的升阻比最小，但鸮翼具有优异的降噪特性。声压级的方向性分布揭示了仿生翼型声源具有偶极子声源特性。

关键词：仿生翼型；大涡模拟；气动噪声；升阻比中图分类号：TB533,O355 文献标识码：A

# Numerical Study on Aerodynamic Performance and Noise Characteristic of Several Bionic Airfoils

LI Dian LIU Xiao-Min (School of Energy and Power Engineering,Xi'an Jiaotong University, Xi'an 71Oo49, China)

Abstract: The bionic airfoils were restructured by extracting cross-section configurations of four species of bird wings at the $40 \%$ position along the spanwise direction respectively based on the airfoil theory. The flow fields and the corresponding sound fields over the designed bionic airfoils were simulated numerically by using large-eddy simulation coupled with the acoustic analogy of Ffowcs-Wiliams and Hawkings equation. The results on unsteady flow simulations indicated that the airflow separated at the leading edge of the suction side under the effect of adverse pressure.The vortex structure was formed at the downstream of the blade,and it broke down after it was separated from the tailing edge of the blade. The lift-to-drag ratio of seagullairfoil was the maximum and the lift-to-drag ratio of owl airfoil was the minimum， however， the later possessed excellent noise-reduction characteristic. The directional distribution of SPL revealed the dipole characteristics of the acoustic source of four bionic airfoils.

Key Words: Bionic Airfoil; Large Eddy Simulation; Aerodynamic Noise; Lift-to-Drag Ratio

# 0引言

鸟类由于其翅膀特殊的形态结构，具有滑翔飞行和静音飞行的特性，这表明基于鸟类翅膀的仿生设计具有节能降噪的潜力。Kondo[]等对提取的鸮翼进行模拟，结果表明在低雷诺数下，鸮翼的升阻比较 NACA0012翼型有所提高。Klan[2]等对仓鸮翅膀结构进行分析，结果表明仿仓鸮翼型吸力面的气流分离主要与雷诺数和气流攻角有关。Lilley[3]等通过对猫头鹰翅膀的特殊形态研究发现，前缘梳妆及尾缘齿状结构是其静音飞行的主要降噪元素。葛长江[4]等对二维仿生翼型进行数值模拟，得到的声场显示出仿生翼型的声源具有偶极子特性，从而揭示了仿生翼型的噪声机理。任露泉[5等研究了长耳鸮翼前缘非光滑形态对噪声的影响，研究表明非光滑模型气动噪声降低了 $5 { \sim } 1 0 ~ \mathrm { d B }$ 。

本文通过提取四种鸟类翅膀沿翼展方向 $40 \%$ 截面处的翼型，利用大涡模拟方法对四种仿生翼型进行三维非定常流场的数值模拟，通过基于Lighthill声类比的FW-H方程计算其声场分布，对比分析了不同仿生翼型的气动和噪声特性，研究结果对微型扑翼飞行器及新型翼型设计具有重要的参考价值。

# 1四种仿生翼型提取

Liu[等通过3D无接触激光扫描技术提取了四种鸟类翅膀信息，并采用拟合的方法重构了四种仿生翼型，其中仿生翼型的上表面和下表面分别通过中弧线分布及厚度分布相加减得到，中弧线和厚度分布采用Birnbaum-Glauert函数方程获得。

图1所示为四种鸟类翅膀沿翼展方向上 $40 \%$ 位置处的翼型，该截面处翼型厚度变化较大，轮廓比较明显，主要用来支撑自身的升力，受到的气流冲击也较大，是影响鸟翼气动性能的主要部位，因此作为本文研究对象。

![](images/0f0c9965ed46bcdf0bc1d7c9dd355fa8a3f41193460bf708f50df161f4108e17.jpg)  
图1沿翼展方向 $40 \%$ 截面处的翼型型线

# 2 翼型数值计算

# 2.1计算网格及边界条件

根据四种鸟类翅膀的典型尺寸，取弦长 $\mathbf { \Psi } _ { c }$ 为$0 . 1 3 \mathrm { ~ m ~ }$ 。图2为计算域形状，计算域的展向宽度取0.2倍的翼型弦长，两侧为平移周期性边界条件。气流进口速度取 $1 0 \ \mathrm { \ m / s }$ ，攻角为 $0 ^ { \circ }$ ，出口压力为$1 . 0 1 3 { \times } 1 0 ^ { 5 } \mathrm { P a }$ ，仿生模型壁面采用无滑移壁面边界条件，翼型弦长雷诺数为 $9 . 0 \times 1 0 ^ { 4 }$ 。

![](images/c93ffc7e026ecee2a666395094d1b384ffcddda603c35f43686ddadffce90e7e.jpg)  
Fig.1Airfoils at the $40 \%$ cross-section in the spanwise direction   
图2计算域示意图  
Fig.2 Schematic plot of the computational domain

翼型外流场网格为C 型结构化网格[7]，网格单元数为120万，展向网格为H型网格，以保证近壁面网格的正交性。图3为海鸥翼型的网格划分，对仿生翼型壁面附近区域采取加密处理，翼型表面法向第一层网格 $y ^ { ' } { < } 1$ ，为了验证计算结果的有效性，本文以海鸥翼型为例进行了网格无关性验证。

![](images/03926027c667bc7dde3063b33a077a2fe9f700a7e703c6d9cf152b057af0c15e.jpg)  
图3翼型网格划分  
Fig.3 The mesh of airfoil

# 2.2数值计算方法

本文选用S-A模型作为稳态计算的湍流模型，将稳态计算的结果作为非定常计算的初值。采用基于亚格子尺度模型的大涡模拟进行非定常计算[9]。数值方法是基于有限体积法的SIMPLE算法，离散格式均取二阶迎风格式[10]。计算的时间步长满足CFL条件[11]。在非定常计算稳定后，将计算结果加入FW-H方程进行声场计算，选取壁面为唯一噪声源。

# 3数值结果分析

# 3.1升阻力系数

表1是四种仿生翼型表面的升阻力系数及升阻比，由此表可得，海鸥和秋沙鸭翼型的升力系数比其他两种翼型明显要高，均达到0.9以上，这是由于翼型下表面较弯曲，翼型沿弦向厚度较大，上下表面压力差大。四种仿生翼型的升阻比都大于10，进一步验证了鸟类翅膀具有高升阻比的特性。

表1不同仿生翼型升阻力系数  
Table1Liftand drag coefficients ofdifferent bionic airfoils   

<html><body><table><tr><td>种类</td><td>升力系数</td><td>阻力系数</td><td>升阻比</td></tr><tr><td>海鸥</td><td>0.9637</td><td>0.0398</td><td>24.2136</td></tr><tr><td>水鸭</td><td>0.4621</td><td>0.0212</td><td>21.7972</td></tr><tr><td>秋沙鸭</td><td>1.1680</td><td>0.0488</td><td>23.9344</td></tr><tr><td>鸮</td><td>0.3649</td><td>0.0264</td><td>13.8220</td></tr></table></body></html>

# 3.2壁面压力分布

图4为壁面压力系数分布曲线，由图中可知，四种翼型的吸力面前缘压力系数均达到峰值。这是由于翼型前缘厚度较大，气流冲击大，产生的相对压力高。海鸥和秋沙鸭翼型压力面的压力系数较高，均值达到0.3以上。水鸭和秋沙鸭翼型压力面的压力系数在弦向分布较均匀，表明其下表面因弯度较小引起的压力分布均匀。海鸥翼型吸力面在大约$0 . 0 3 \mathrm { ~ m ~ }$ 处形成局部吸力峰，之后压力系数趋于平缓。水鸭翼型上下表面弯曲较平缓，压力系数分布平稳，只在前缘处有较大的峰值出现。秋沙鸭翼型在前缘和尾缘处均发生压力突变，在中间部位呈现一段平稳区间。鸮翼压力面在 $0 . 0 3 \mathrm { ~ m ~ }$ 及 $0 . 0 7 \mathrm { ~ m ~ }$ 处有明显弯曲，故在此处产生了局部的压力双峰。

![](images/7030575dd4d463b6ebfc9a6f3e6f9d4a8d44f2f44bb6b80062c1a8926846e203.jpg)  
图4压力系数分布

# 3.3速度分布

为进一步分析仿生翼型的气动性能，图6给出了 $0 ^ { \circ }$ 攻角下瞬态流场四种仿生模型中间截面的速度云图及流线图，通过流线可以观察到气流分离的位置。图(a)中气流分离主要出现在压力面 $20 \%$ 弦长处和吸力面 $80 \%$ 弦长处，海鸥翼型尾缘处的气流分离严重，分离气泡向下游迁移，在下游区域形成了较明显的涡街。海鸥和鸮翼型压力面前缘均有气流分离，这是由于前缘下表面弯度较大引起的，气流流过壁面时在凹面处产生了局部涡旋。水鸭和鸮翼型的尾缘分布平缓且曲率较小，这种特殊形态使气流难以附着在壁面上，减小了边界层的气泡分离。

![](images/b304bc5880fc3f992d47c88d3266a486dff5128ff056808baa8506c4179831cd.jpg)  
图5仿生翼型中间截面处速度云图  
Fig.5 The velocity contours of the bionic airfoils

# 3.4压力和涡旋分布

这里用目前最常用的Q判据[12]通过分析吸力面与压力面涡旋的运动状态来进行比较非稳态流场中绕翼型的流动状态对声压级的影响。如图6所示，灰色部分的等值面代表了涡的结构，在逆压梯度作用下，流过海鸥、水鸭和秋沙鸭翼型的气流在吸力面前缘处开始分离，在下游处产生了明显的涡结构，在脱离尾缘后涡结构发生破碎，转化成小尺度湍流。在鸮翼尾缘处涡结构较小，气流分离不明显。结合吸力面尾缘处的涡结构，得出气动噪声主要是由尾随涡引起，说明后缘散射噪声是最主要的噪声源。

![](images/853880e5ac47790e703c990e20e0b95fc9189766623132790e80eacc15a11cb1.jpg)  
Fig.4Distributions of pressure coefficient   
图6瞬态流场压力云图及尾迹涡区域  
Fig.6 The pressure contours of transient flow and the location of vortex shedding

# 3.5声压级的方向性分布

为了准确地得到噪声在传播方向上的分布，对距仿生翼型15倍弦长处沿周向均匀布置12个声音压强信号接收点，图7所示为获得的噪声总A声压级的方向性分布。从图中可以看出，声压级随方向变化明显，在上下两侧出现最高峰，在前后两侧出现最低峰，说明噪声的主要辐射区在上下两侧。四种仿生模型的声压级方向性分布在水平和竖直方向上均呈轴对称性，表明此处空气动力性噪声的声源为偶极子源。秋沙鸭翼型的噪声峰值为57.64dB。鸮翼型的噪声最小，峰值为 $2 5 . 2 0 \mathrm { d B }$ ，与其具有静音飞行的生物功能一致。

![](images/32b706d2024a6d3d77d72d259a950d28710a7d0f62fcd1cfd195088f5b78d8f1.jpg)  
图7声压级的方向性分布  
Fig.7 The directional distribution of sound pressure level

# 4结论

（1）四种仿生翼型均具有高升阻比特性，其中海鸥和秋沙鸭翼型具有较高的升力系数。

（2）四种仿生翼型的噪声特性产生机理及变化趋势基本一致，声压级的方向性分布揭示了仿生翼型声源为偶极子源，并优先向上下方传播，鸮翼的总A声压级最小，峰值为25.20dB。

# 参考文献

[1]Kondo K，Aono H,Nonomura T,et al.Large-Eddy Simulations of Owl-Like Wing under Low Reynolds Number Conditions[C]//ASME 2013 Fluids Engineering Division SummerMeeting. American Societyof Mechanical Engineers,2013:V01AT04A004.   
[2]Klän S,Bachmann T,Klaas M,et al.Experimental Analysis of the Flow Field over a Novel Owl Based Airfoil[J].Experiments in Fluids,2009,46(5): 975-989.   
[3]Lilley G M.A Study of the Silent Flight of the Owl[J]. AIAA paper, 1998,2340(1998): 1-6.   
[4]葛长江，葛美辰，梁平 等．基于鸮翼的仿生翼型噪声 机理研究[J]．农业机械学报,2013,44(S1):292-296. GE Changjiang，GE Meichen，LIANG Ping，et al. Investigation of Noise Mechanism Based on Owl Wing[J]. Transactions of the Chinese Society for Agricultural Machinery,2013,44(S1): 292-296.   
[5] 任露泉，孙少明，徐成宇．鸮翼前缘非光滑形态消声降 噪机理[J]．吉林大学学报(工学版)，2008,38(S1): 126-131. REN Luquan， SUN Shaoming，XU Chengyu. Noise Reduction Mechanism of Non-Smooth Leading Edge of Owl Wing[J]. Journal of Jilin University(Engineering and Technology Edition),2008,38(S1): 126-131.   
[6]LIU Tianshu, Kuykendoll K, Rhew R, et al. Avian Wing Geometry and Kinematics[J]. AIAA journal, 2006, 44(5): 954-963.   
[7]SHAN Hua, LI Jiang, LIU Chaoqun. Direct Numerical Simulation of Flow Separation Around a NACA 0012 Airfoil[J]. Computers & fluids,2005,34(9): 1096-1114.   
[8] 华欣．海鸥翅翼气动性能研究及其在风力机仿生叶片 设计中的应用[D].吉林大学,2013. HUA Xin. Research on the Aerodynamic Characteristics of Wings of the Seagull and the Bionic Blade of Wind Turbines Design Application[D].Jilin University, 2013.   
[9] 刘小民，汤虎，王星 等．苍鹰翼尾缘结构的单元仿生 叶片降噪机理研究[J]．西安交通大学学报，2012,46(1): 35-41. Liu Xiaomin, Tang Hu, Wang Xin, et al. Noise-Reduction Mechanism of Bionic Coupling Blade Based on the Trailing Edge of Goshawk Wing[J]. Journal of Xi'an Jiaotong University,2012,46(1): 36-41.   
[10] 石磊，张成春，王晶 等.NACA0018 翼型模型的仿生降 噪[J]．吉林大学学报(工学版),2011,41(6): 664-668. SHI Lei， ZHANG Chengchun，WANG Jing，et al. Reduction of Aerodynamic Noise from NACAo018 Airfoil Model Using BionicMethods[J]．Journal of Jilin University(Engineering and Technology Edition),2011, 41(6): 664-668.   
[11] Kim H J, Lee S, Fujisawa N. Computation of Unsteady Flow and Aerodynamic Noise of NACA0018 Airfoil Using Large-Eddy Simulation[J]. International Journal of Heat and Fluid flow,2006,27(2): 229-242.   
[12] Kim T, Jeon M, Lee S,et al. Numerical Simulation of Flatback Airfoil Aerodynamic Noise[J]. Renewable Energy, 2014, 65: 192-201.

# 联系方式

通讯作者：刘小民，西安交通大学咸宁西路 28号能动学院，邮编：710049，手机：13720615519，电话：029-82663777-308电子信箱：liuxm@mail.xjtu.edu.cn