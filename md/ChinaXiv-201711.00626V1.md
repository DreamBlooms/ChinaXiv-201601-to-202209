# 无轴双吸式血液泵内部流动分析

庄保堂1，罗先武2，纪晶晶2，许洪元2

（北京控制工程研究所，北京，100190清华大学水沙科学与水利水电工程国家重点实验室，北京100084）(010-68379107，zbt07@mails.tsinghua.edu.cn)

摘要：基于带有叶轮转子的双吸叶轮的概念，设计了一种新型无轴双吸式血液泵。为了研究血液泵的水力性能和溶血性能，对设计工况下血液泵进行了三维非定常数值模拟，同时考虑作为人类心脏用时的搏动流工况，以此为边界条件计算分析了搏动流工况下的内部流场的速度、压力和壁面剪切应力分布以及对泵运行稳定性的影响。数值计算结果表明，搏动流工况下，实现泵流量与扬程的波动输出，与非搏动流相比，其压力稳定性较差。该结果为血液泵在人工心脏、人工透析等现代机械辅助系统的应用提供有益的参考。

关键词：血液泵；双吸；非定常；数值模拟

# Internal Flow Analysis of a Shaft-less Double-suction Blood Pump

ZHUANG Bao-Tang1, LUO Xian-Wu ², WEI Wei ², XU Hong-Yuan ²

(1.Beijing Institute of Control Engineering,Beijing 100190, China; 2.Beijing KeyLaboratory ofCO2 Utilizationand Reduction Technology,Tsinghua University,Beijing l0o084,China) Abstract: Based on theconceptof double-suction impeller combined with motor rotor,a novel shaft-lessblood pump has been designed. In order to investigate the hydraulic performance and the biocompatibilityof the pump,the unsteady numerical simulation for threedimensionalflows in entire pump passage near the designcondition is conducted. In the calculations,the pulsatileflowofanaturalartery isused as theboundarycondition at pump inlet soas toobserve the flow characteristicssuchas the velocity,pressureand wallshear stressinflowpassage,and theefecton theoperatingstability of the pump.Based on the results of numerical simulation,the internal flow will be further discussed.

Key words: blood pump; double-suction; unsteady; numerical

# 0前言

血液泵是以血液作为输运介质的一类医用血液泵，可代替人体器官的部分功能，用以辅助血液循环，是现代医学治疗急慢性器官功能衰竭的主要装置。目前，常用的血液泵多用机械轴承作为转轴支撑，机械轴承的摩擦损失大、易损坏，且运行时产生一定的热量，若用于血液循环系统，易产生凝血和溶血。因此，近年来越来越多的学者开始投入磁悬浮、液体动压为支撑的血液泵研究[1-4]。液体动压式血液泵具有噪音低、机械摩擦损失小及使用寿命长等优点。而相对于轴流泵，离心式血液泵具有转速低、溶血破坏小等优点。因此，有必要进行动压式血液泵的研究。2009年罗先武等人[5-8]设计一种叶轮外径为 $4 0 \mathrm { m m }$ 的无轴超小型泵，该泵的转子由动压支撑，这种无轴双吸血液泵不会造成大量血细胞破坏。针对血液泵内流场的研究，澳大利亚麦考瑞大学的QianYi教授较早开始了关于血液泵的研究工作[9,10]，并对液体压力悬浮式离心泵内部流动特性及液体压力支撑性能进行了数值仿真研究；Burgreen等人对带有永磁支撑转子的离心式HeartMateII左心辅助系统在设计条件下的动力学特性进行数值仿真和分析工作[11]，仿真计算与实验结果具有良好的一致性。Tsukamoto 等人[12开发了一种带有沟槽轴承的血液泵，该泵带有一种软性材料支撑液体动压轴承。

本文针对一种叶轮外径为 $2 4 \mathrm { m m }$ 的新型无轴双吸式血液泵在非搏动及搏动流工况下的内部流场进行了三维全流道非定常数值模拟，分析两种流动工况下血液泵的内部流动特性，探讨速度、压力及壁面剪切应力的非定常变化规律，为搏动流工况下血液泵的运行稳定性设计提供参考。

# 1血液泵的结构设计

血液泵的整体结构主要由两大部分组成：驱动部件和流动部件，如图1所示。驱动部件包括由电枢绕组、硅钢片及永磁体组成的电机和控制器；流动部件包括叶轮、泵壳及出口管等。

![](images/36148fa830e2b7319a6297a302de84c8b9eef000c7f62c6996eee54f140d19ac.jpg)  
图1血液泵的整体结构方案

1．泵壳2．泵端盖3．密封圈4．十字槽沉头螺钉5．密 封座6.转子磁体端盖7．叶轮转子8．永磁体9．电枢绕 组10．硅钢片

Fig.1 Schematic diagram of the miniature pump.

叶轮转子和压水室之间设有液膜间隙，当泵内流体流动时，该液膜间隙可以作为叶轮转子和泵壳之间的压力膜，对叶轮转子起支撑和润滑作用。液体经过叶轮后，叶轮出口压力高于叶轮进口压力，在压力差作用下，液体沿着间隙从叶轮出口流向叶轮进口，冲刷间隙流道，防止在流道中形成流动死区，并带走电流通过线圈及转子旋转所产生的热量。该方案可有效防止由于高温及血液长时间停滞和积淤而导致的凝血现象，而采用液体动压悬浮支撑，可避免由于机械轴承对红细胞破坏的溶血现象。

# 2数值计算方法

# 2.1计算模型与网格划分

全流道模型由进口管、叶轮、压水室、出口管四部分组成。以叶轮区域和旋转吸入段（进口管中间部位）作为旋转坐标系，而进口管、压水室、出口管区域作为静止坐标系处理。本文选用SST $k - \omega$ 湍流模型进行数值计算。

综合考虑数值计算精度和经济性，选用节点数量为86万的结构化网格。网格划分结果如图2所示。

为了更加精确地计算叶片表面的压力及剪切应力分布，对壁面网格进行局部细化，靠近壁面处的最小网格间距为 $3 0 \mu \mathrm { m }$

![](images/f482cd0be8b7475b51cbd39449dfa3d639a79d1ff560be07de1ace21e301f8d8.jpg)  
图2计算模型网格划分示意图Fig.2Mesh generation

# 2.2搏动流工况及模拟方法

根据人体搏动流流量变化曲线，取心脏搏动周期$T = 0 . 5 { \mathrm { s } }$ 。泵进口给定流量变化规律，图3为两个周期内泵的进口（单侧进口）质量流量随时间的变化规律。

![](images/1ed6d4db782776dd50c44a959899c2f48c6bfc6ea9ac44365ea917b64e72fdd6.jpg)  
图3泵入口质量流量随时间变化曲线Fig.3Variationofmassflowatpump inlet

一个搏动周期内质量流量随时间的变化关系曲线可用如下函数表示：

$$
\mathcal { Q } _ { \mathrm { m } } \left( t \right) = a _ { 0 } + \sum _ { n = 1 } ^ { 6 } \left( a _ { n } \cos ( n \omega t ) + b _ { n } \sin ( n \omega t ) \right)
$$

式中各参数值见表1。

Table 1: Coefficients in Equation (1).   

<html><body><table><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>ao</td><td>a1</td><td>a2</td><td>a3</td><td>a4</td><td>a5</td><td>a6</td></tr><tr><td>0.0160</td><td>0.0027</td><td>-0.018</td><td>-0.000</td><td>0.0018</td><td>0.0025</td><td>0.001</td></tr><tr><td>82</td><td>48</td><td>54</td><td>26</td><td>54</td><td>73</td><td>17</td></tr></table></body></html>

表1质量流量变化函数参数表  
续表1质量流量变化函数参数表  

<html><body><table><tr><td>b1</td><td>b</td><td>b</td><td>b4</td><td>b5</td><td>b6</td><td></td></tr><tr><td>0.0190</td><td>0.0026</td><td>-0.009</td><td>-0.002</td><td>-0.000</td><td>0.0009</td><td>12.5</td></tr><tr><td>64</td><td>14</td><td>36</td><td>11</td><td>76</td><td>36</td><td>7</td></tr></table></body></html>

# 3计算结果与分析

3.1非搏动流工况下血液泵的非定常流动模拟

在设计转速（ $5 0 0 0 \mathrm { r / m i n }$ ）下，对设计流量工况( $Q = Q _ { \mathrm { d } }$ ）下的血液泵内的流动进行非定常数值模拟，分析叶轮和压水室内部的速度、压力及壁面剪切应力分布。

定义如下无量纲的静压系数 $C _ { \mathfrak { p } }$ 和全压力系数

$C _ { \mathfrak { p t } }$

$$
C _ { \mathfrak { p } } = \frac { p - p _ { 0 } } { 0 . 5 \rho U _ { 2 } ^ { 2 } }
$$

$$
C _ { \mathrm { p t } } = \frac { p _ { \mathrm { t } } - p _ { 0 } } { 0 . 5 \rho U _ { 2 } ^ { 2 } }
$$

式中 $p$ 为静压（Pa）， $p _ { \mathrm { t } }$ 为全压（ $\mathbf { \rho } _ { \mathrm { P a } } )$ ， $\rho$ 为流体密度， $p _ { 0 }$ 为参考压力，这里取叶轮进口的平均静压。

为了观察叶片旋转对内部流态的影响，将一个周期分成5个叶片位置对应的时刻，图中黑色轮廓线表示同一个叶片。 $t = 0$ 与 $t = T$ 时刻对应叶片起始位置，及旋转一周后的位置。为了便于分析叶轮及压水室内部的流动情况，对叶轮叶片及压水室断面进行编号，如图4所示。

![](images/8ee7757b561bf74d99e0277897cb7f608f8f4efe2bbfe4ca305fc5823d04616f.jpg)  
图4叶轮与压水室相对位置示意图  
Fig. 4 The relative position of the blades and the casing

设计流量工况下，叶高中截面上叶轮区域的相对速度及压水室区域绝对速度，如图5、图6所示。

999 t=0 t=T/5 t=2T/5 569 t=3T/5 t= 4T/5 t=T

![](images/5221ad705446fb848bf971099525b9b7a96acfcc6b5d9c2e3b74a2823c0437d3.jpg)  
图5设计流量下叶轮内的相对速度及流线分布（单位： $\mathrm { m / s }$ ））Fig.5Distribution ofrelative velocity and streamlines inthe impeller passage (unit: $\mathrm { m / s } \mathrm { \dot { \Omega } }$ ）

由图5可以看出，随着流量的增加，叶轮内的相对速度增大，最大值为 $6 . 7 \mathrm { m / s }$ ，最大速度位置发生在靠近压水室隔舌附近沿叶轮旋转方向的叶片压力面出口处；不同时刻，随着叶片相对隔舌的位置改变，叶轮内的相对速度分布不同，在局部流道内相对流线偏折较小。

![](images/86d16a53249887453d783ac3b471c5e70511e39ad4086d13135a14935e34c524.jpg)  
图6设计流量下压水室内绝对速度及流线分布（单位： $\mathrm { m / s }$ ））Fig.6Distribution ofrelative velocity and streamlines incasing passage (unit: $\mathrm { m / s } \mathrm { \dot { } }$ ）

设计流量工况下，压水室内的绝对速度分布较均匀，最大绝对速度为 $3 . 7 \mathrm { m / s }$ ，没有出现较大的高速区，这主要是由于设计流量工况下叶片出口绝对速度与压水室的进口绝对速度比较接近，不会因出现较大的速度梯度而产生冲击；由于静止隔舌的影响，在第0至第II断面之间的压水室流道内出现低速区，在压水室出口位置出现较大的高速区。

ddd t=0 t=T/5 t=2T/5 ddd t=3T/5 t= 4T/5 t=T -20.3 -17.7 -15.0 -12.3 -9.6 -6.9 -4.3 -1.6 1.1 3.8 6.4

设计流量工况下，不同时刻叶轮及压水室流道内静压分布不同。整体上来看，压水室内及出口断面压力分布相对均匀，局部出现较大压力，是由于旋转叶片与静正隔舌的相互作用造成的。相对于小流量工况，其出口断面处的静压较低，仅为1.1kPa。

# 3.2搏动流工况下血液泵的非定常流动模拟

# 1．能量计算结果

两个脉动周期内血液泵的扬程随时间的变化关系见图8。

![](images/1723f92bf5ca9f89c95ca3cd5719999cb22c9636993b9defbe4c2bfaffb2a352.jpg)  
图7设计流量下叶轮及压水室内的静压分布（单位：kPa） Fig.7Distribution of relative velocity and streamlines in casing passage (unit:kPa)   
图8搏动流工况下泵的扬程随时间变化关系  
Fig.8Relation between the pump head and time

可以看出，随着入口流量的周期性变化，泵的扬程也随之出现周期性搏动，实现搏动流工况；扬程总体变化趋势与质量流量变化相反，流量较大的时刻，其扬程较低，扬程范围在 $1 . 3 7 { \sim } 2 . 5 8 \mathrm { m }$ 之间。

# 2．内流场模拟结果

一个搏动周期内泵输出流量随时间的变化曲线及典型流量工况测点如图9所示。 $t _ { \mathrm { 1 } } = 0 . 1 0 9 4 \mathrm { s }$ 为整个搏动周期的波峰时刻，此时流量接近设计流量; $t _ { 2 } = 0 . 1 9 \mathrm { s }$

为整个搏动周期内的平均质量流量时刻； $t _ { 3 } = 0 . 2 6 7 4 \mathrm { s }$   
为波谷时刻，此时质量流量接近零。

通过计算得到一个搏动周期内三个不同时刻$\mathit { \Omega } ( t = t _ { 1 } , \ t _ { 2 } , \ t _ { 3 } )$ ）的叶轮区域的相对速度分布，如图10所示。

![](images/ccbcddde68f84c9a9de8943b9ed3cc6c71868ed4c9f85e989c151f4eb56f517c.jpg)  
图9一个搏动周期内的质量流量变化及测点分布  
图10三个流量时刻叶轮区域的相对速度及流线分布 $\mathrm { { ( m / s } }$ ）Fig.1O Distribution of relative velocity at three differentmoments in impeller passage (unit: $\mathrm { m / s }$ ）  
图12叶轮及压水室内的静压分布（单位：kPa)

669   
t1 2 t3   
0.0 0.5 1.1 1.6 2.2 2.7 3.2 3.3 4.3 4.9 5.4

从三个不同时刻叶轮内的相对速度分布可以看出， $t _ { 1 }$ 时刻，即进口质量流量接近设计流量时，叶轮内流道内相对速度分布较均匀，流线相对光滑； $t _ { 2 }$ 时刻，流道内出现低速区，湍流现象明显，流线分布混乱，部分流道出现漩涡； $t _ { 3 }$ 时刻，流道内出现大面积低速区，每个流道内均有较大的漩涡，严重阻塞流道，势必带来较大损失。

图11为搏动流工况下三个不同时刻0 $\mathbf { \chi } _ { t } = t _ { 1 } , \ t _ { 2 } , \ t _ { 3 } \ \$ ，压水室内的绝对速度分布。

![](images/ac5c4e719701398a240552da326fd4ed1e88e8a624dfe363bc26f0e1ac1da931.jpg)  
Fig. 9 Flow rate and he monitoring points in a pulsating cycle   
图11压水室内的绝对速度及流线分布（单位： $\mathrm { m / s }$ ）  
Fig.11 Distribution of absolute velocity at three different moments in the casing (unit: $\mathrm { m / s }$ ）

$t _ { 1 }$ 时刻，即接近设计流量工况时刻，压水室内的绝对速度分布均匀，流动平稳，流线光滑，此时流动损失最小； $t _ { 2 }$ 时刻，隔舌附近速度分布不均匀，压水室进口位置局部速度较大，出口段出现低速区，流线也发生偏折； $t _ { 3 }$ 时刻，压水室内流速分布不均匀，出口有较大的低速区，流线偏折较大，并有较大的漩涡。

可以看出，搏动流工况时，血液泵的内部流动更加复杂、均匀性变差。在进行血液泵优化设计时，应重点改善小流量时刻叶轮内流态及压水室出口位置的流动滞留情况。

搏动流工况下，三个不同流量时刻（204号 $( \mathrm { \Delta } t = t _ { 1 } { \setminus } \mathrm { \Delta } t _ { 2 } { \setminus } \mathrm { \Delta } t _ { 3 } \mathrm { \Delta } )$ 叶轮及压水室内的静压分布如图12所示。图13给出了三个时刻叶轮及压水室表面的剪切应力分布情况；

叶轮及压水室的静压分布表明，不同时刻，叶轮及压水室内的静压分布差别较大。 $t _ { 1 }$ 时刻，叶轮内静压从进口到出口逐渐增加，压水室内静压分布均匀；$t _ { 2 }$ 时刻，叶轮出口位置压力分布不均匀，在压水室隔舌附近出现局部低压区； $t _ { 3 }$ 时刻，叶轮及压水室内压力分布非常不均，将严重影响泵的性能。

ydd t1 t2 13 -38.7 -34.6 -30.5 -26.4 -22.3 -18.2 -14.2 -10.1 -6.0 -1.9 2.2

![](images/c36dd7e044b529a7ea274a73f32ab9a03f427caf9f8101218f39f4925d6175f8.jpg)  
Fig.12 The distribution of the static pressure at three different moments (unit: kPa).

图14、图15分别为搏动流工况下一个脉动周期内，叶轮、盖板及压水室表面的最大壁面剪切应力$\tau _ { \mathrm { m a x } }$ 与平均壁面剪切应力 $\tau _ { \mathrm { a v g } }$ 随时间的变化曲线。

![](images/d7d72e0d8b4dcd391c492ff7f0b800821fb08feab9fa59a87216137e8da75eb4.jpg)  
图13叶轮及压水室表面的剪切应力分布（单位：Pa) Fig.13 Distribution of wall shear stress at three different moments (unit: Pa)

![](images/c3cb5117907fad4ddeed8c76a414ef111d2b14fb7f6aa8a37ce9f0ba59d4c847.jpg)  
图14一个脉动周期内叶轮及压水室的最大壁面剪切应力Fig.14 Distribution of maximum wall shear stress in apulsation period.  
图15一个脉动周期内叶轮及压水室的平均壁面剪切应力 Fig.15Distributionof averaged wall shear stress in a

pulsation period

通过计算得到 $t _ { 1 } \setminus \ t _ { 2 } \setminus t _ { 3 }$ 时刻的压水室内的最大壁面剪切应力分别为 $2 7 8 \mathrm { { P a } }$ 、 $3 7 7 \mathrm { { P a } }$ 、 $3 6 0 \mathrm { P a }$ ，同非搏动流工况类似，最大壁面剪切应力出现在隔舌和叶片进口及出口位置。压水室内的最大壁面剪切应力高于叶轮，而平均壁面剪切应力正好相反；平均壁面剪切应力与质量流量的变化趋势相同，大流量时刻，其平均壁面剪切应力亦较大；虽然压水室内的最大剪切应力较高，但平均壁面剪切应力较低，即整体上壁面剪切应力较小。在进行压水室优化时，可考虑降低压水室局部的最大壁面剪切应力值。

# 4结论

1）将人体心脏的搏动流工况运用于血液泵，分析搏动流动对无轴双吸式血液泵运行稳定性的影响，为血液泵在人工心脏、人工透析等现代机械辅助系统的应用提供有益的参考。2）搏动流工况下，可实现泵流量与扬程的波动输出。一个脉动周期内，各测点的压力变化趋势与泵送的质量流量有关，相对于压水室，叶轮内的压力波动较大。3）一个脉动周期内，压水室内的最大壁面剪切应力高于叶轮，但平均壁面剪切应力较低。在进行压水室优化时，可考虑降低压水室局部的最大壁面剪切应力值。

# 参考文献

[1]Michael P, Siegenthaler M P, Frazier O H,et al. Mechinical relicability of the Jarvik 2Ooo Heart[J]. Ann Thorac Surg, 2006,81:1752-1759.   
[2]Akamatsu T.Development of centrifugal blood pump with magnetically suspended impelle [J].   
Turbomachinery, 2001,29(1):7-16.   
[3] Kaneko M, Nakamura Y, Miyazaki K, et al.   
Multi-objective optimization of blood-pump with   
conical spiral groove bearings[C]// Proceeding of 4th International Symposium on Fluid Machinery and Fluid Engineering,Beijing, 2008   
[4] Hiltion E F,Allaire P R,Wei N,et al. Test controller design， implementation，and performance for a magnetic suspension continuous flow ventricular assist device[J]. Artif Organs,1999, 23(8): 792-6.   
[5] Zhuang B T, Luo X W, Zhang Y, et al. Design optimization for a shaft-less double suction mini turbo pump[C]. In: Proceeding of 25th IAHR Symposium on Hydraulic Machinery and Systems， Timisoara, 2010   
[6] Zhuang B T, Luo X W, Zhu L, et al. Cavitation in a shaft-lessdoublesuctioncentrifugal miniature pump[J]. J Eng Thermophys,2011, 32(S1):57-60   
[7] Luo X W, Zhu L, Zhuang B T, et al. A novel shaft-less double suction mini pump[J]. Sci China Tech Sci, 2010, 53:105-110   
[8] Luo X W, Ji B, Zhuang B T, et al. A miniature pump with a fluid dynamic bearing[J]. Sci China Tech Sci, 2012, 55: 795-810.   
[9] Qian Yi， Bertram C D. Computational fluid dynamics analysis of hydrodynamic bearings of the VentrAssist rotary blood pump[J]. Artificial Organs, 2000,24(6):488-491.   
[10] Bertram C D, Qian Yi, Reizes J A. Computation fluid dynamicsperformance prediction forthe hydrodynamic bearings of the VentrAssist rotary blood pump[J]. Artificial Organs, 2001, 25(5):248-357.   
[11] Burgreen G W. Computational Fluid Dynamics Analysis of a Maglev Centrifugal Left Ventricular AssistDevice[J].ArtificialOrgans, 2004, 28(10):874-880.   
[12] Kaneko M, Nakamura Y, Miyazaki K, et al. Multi-objective optimization of blood-pump with conical spiral groove bearings[C]. In: Proceeding of 4th International Symposium on Fluid Machinery and Fluid Engineering, Beijing, 2008.