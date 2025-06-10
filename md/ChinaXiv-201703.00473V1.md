# 热辐射问题的迭代双向统计蒙特卡罗方法

朱言旦1,2 曾磊2 杜雁霞²桂业伟1,2(1．中国空气动力研究与发展中心空气动力学国家重点实验室，绵阳621000;2.中国空气动力研究与发展中心计算空气动力研究所，绵阳621000)

摘要为了进一步提高辐射传递因子的倒易性，本文提出了迭代双向统计蒙特卡罗方法。该方法将双向统计蒙特卡罗方法分解为归一化过程与双向统计过程，摆脱了传统迭代双向统计蒙特卡罗方法对等权抽样假设的依赖，进一步提高了辐射传递因子的倒易性。验证结果表明，迭代双向统计蒙特卡罗方法获得的辐射传递因子满足完整性，其倒易性误差的量级随双向统计迭代次数的增加而呈线性下降趋势。将该方法应用到含空腔结构的辐射/导热耦合边界平衡问题中，结果表明本文所建方法可以有效提高热辐射传输问题的求解精度，并且求解精度随着迭代次数的增加而提高。

关键词迭代；双向统计；蒙特卡罗；热辐射中图分类号：TK124 文献标识码：A 文章编号:0253-231X(2017)03-0635-05

# Iterative Bidirectional Statistics Monte Carlo Method in Thermal Radiation

ZHU Yan-Dan $^ { 1 , 2 }$ （204 ZENG Lei² DU Yan-Xia² GUI Ye-Wei $^ { 1 , 2 }$

1.State KeyLaboratoryofAerodynamics,ChinaAerodynamics ResearchandDevelopmentCenter，Mianyang 621o,China   
2.Computational Aerodynamics Institute,ChinaAerodynamics ResearchandDevelopment Center，Mianyang 621o,China)

AbstractAn iterative bidirectional statistical Monte Carlo method is proposed to improve the reciprocity of radiative transfer factor， which decomposes the bidirectional statistical Monte Carlo method into a normalized process and a bidirectional statistical process.This method can get rid of the assumption of equal weight sampling and further improve the reciprocity of radiative transfer factor. The results of the validation of the new method show that the magnitude of the error of the reciprocity is decreased linearly with the increase of the number of iterations,and the integrity is certifed. The method is applied into equilibrium radiation problem.The result shows that the method developed in this paper can improve the accuracy of the solution of radiation transfer, and the accuracy increase with the increase of the number of iterations.

Key wordsiterative; bidirectional statistics; monte carlo; thermal radiation

# 0引言

蒙特卡罗方法是一种概率统计方法，既能用于求解随机性问题，也能用于求解确定性问题。该方法最早由Howell和Perlmutter应用于热辐射换热计算[1,2]，因其具有物理模型简单清晰、应用灵活等优点，获得了广泛的应用[3-5]。但是，由于该方法是一种统计方法，需要进行大量的抽样模拟以提高其精度。一些学者结合实际问题，提出了一些可以改善其计算效率的处理方法[6-10]，其中就包括文献 [9]提出的双向统计蒙特卡罗方法。

双向统计蒙特卡罗方法(BSMC）采用等温等权抽样假设，利用热辐射传输时光路可逆原理，对热辐射传输的蒙特卡罗模拟进行双向统计，充分利用能束传播的路径信息，一定程度上提高了辐射传递因子的倒易性[9]。但该方法得到的辐射传递因子的倒易性有时候并不一定能满足实际需求。为了更进一步地利用能束传播路径信息，提高辐射传递因子的倒易性，本文提出了迭代双向统计蒙特卡罗方法(IBSMC).

# 1迭代双向统计蒙特卡罗方法

# 1.1现有双向统计蒙特卡罗方法

辐射传递因子 $R D _ { i j }$ 定义为在一个红外辐射传输系统中，单元 $\mathbf { \chi } _ { i }$ 的本身辐射能量经系统各单元一次或多次反射和散射后最终被单元 $j$ 吸收的份额。

以由 $M$ 个单元构成的辐射传输系统为例。假设

系统模拟能束总量为 $N$ ，单元 $\mathbf { \chi } _ { i }$ 模拟发射的能束量 为 $N _ { i }$ ，则

$$
\sum _ { i = 1 } ^ { i = M } N _ { i } = N
$$

传统蒙特卡罗方法得到辐射传递因子记为$R D _ { i j } ^ { 0 }$ ，则

$$
R D _ { i j } ^ { 0 } = \frac { N _ { i j } } { N _ { i } }
$$

其中, $N _ { i j }$ 为单元 $\mathbf { \chi } _ { i }$ 发射的能束最终被单元 $j$ 吸收的能束量。

双向统计蒙特卡罗方法得到的辐射传递因子记为 $R D _ { i j } ^ { * }$ ，则

$$
\mathit { R D } _ { i j } ^ { * } = \frac { N _ { i j } + N _ { j i } } { \mathit { N } _ { i } + \displaystyle \sum _ { k = 1 } ^ { k = 1 } N _ { k i } }
$$

其中， $N _ { i }$ 满足

$$
\frac { N _ { i } } { N _ { j } } = \frac { E _ { i } } { E _ { j } }
$$

对于面元

$$
E _ { i } = \varepsilon _ { i } A _ { i }
$$

对于体元

$$
E _ { i } = 4 \kappa _ { i } V _ { i }
$$

$\varepsilon _ { i }$ 为面元 $\mathbf { \chi } _ { i }$ 的平均发射率， $A _ { i }$ 为面元 $\mathbf { \chi } _ { i }$ 的面积， $\kappa _ { i }$ 为体元 $\mathbf { \chi } _ { i }$ 的平均发射率， $V _ { i }$ 为体元 $i$ 的面积。

式（4）为等权抽样假设的表述，即假设每束光束携带相同的能量。

# 1.2迭代双向统计蒙特卡罗方法

将双向统计蒙特卡罗方法分解为归一化过程与双向统计过程。归一化过程即传统蒙特卡罗方法过程，如式(2)所示。双向统计过程视为对传统蒙特卡罗方法得到的辐射传递因子的后处理过程，如式 (7)所示。

$$
R D _ { i j } ^ { * } = \frac { E _ { i } R D _ { i j } ^ { 0 } + E _ { j } R D _ { j i } ^ { 0 } } { k = M }
$$

由式(2)和式(7)可以看出，归一化过程和双向统计过程都不依赖于等权抽样假设，即将式(3）分解为归一化过程和双向统计过程后，使双向统计蒙特卡罗方法摆脱了等权抽样假设 (式4)的限制，增大了其适用范围。

双向统计过程利用了光路可逆原理，相当于将辐射换热系统内的抽样能束总数目增加一倍，相应地，每一能束的能量减半[9]，而蒙特卡罗方法的精度随着抽样能束的增加而提高。因此可以考虑利用迭代的方法进行多次双向统计过程，则第 $n$ 次双向统计得到的辐射传递因子表述为

$$
R D _ { i j } ^ { n } = \frac { E _ { i } R D _ { i j } ^ { n - 1 } + E _ { j } R D _ { j i } ^ { n - 1 } } { k = M }
$$

其中， $R D _ { i j } ^ { n }$ 为第 $n$ 次双向统计得到的辐射传递因子， $n = 1 , 2 , 3 , \cdots$ 。式(2)和式 (8)联合起来即为迭代双向统计蒙特卡罗方法，当 $n = 1$ 时，方法退化为文献[9]中的双向统计蒙特卡罗方法。

为验证迭代式（8）得到的辐射传递因子 $R D _ { i j } ^ { n }$ 的完整性，先假设 $R D _ { i j } ^ { n }$ 满足完整性，则对于 $i =$ $1 , 2 , 3 , \cdots , M ; n = 1 , 2 , 3 , \cdots$ ，有

$$
\begin{array} { c } { { \displaystyle \sum _ { k = 1 } ^ { i = M } R \tilde { D } _ { k } ^ { n - 1 } = \sum _ { i = 0 } ^ { i } \frac { E _ { k } R _ { k } D _ { k } ^ { n - 1 } + E _ { i } R \tilde { D } _ { k } ^ { n - 1 } } { \varepsilon _ { k } - \omega } = } } \\ { { \mathrm { } } } \\ { { \displaystyle \sum _ { k = 1 } ^ { i = M } \frac { t } { \varepsilon _ { k } ( M ) D _ { k } ^ { n - 1 } } + \sum _ { k = 1 } ^ { i } E _ { k } R \tilde { D } _ { k } ^ { n - 1 } } } \\ { { \mathrm { } } } \\ { { \displaystyle \sum _ { k = 1 } ^ { i = M } ( E _ { i } R \tilde { D } _ { k } ^ { n - 1 } + E _ { i } R \tilde { D } _ { k } ^ { n - 1 } ) } } \\ { { \displaystyle \sum _ { k = 1 } ^ { i = M } \frac { t } { \varepsilon _ { k } ( M ) D _ { k } ^ { n - 1 } } - 1 } } \\ { { \displaystyle E _ { i } + \sum _ { k = 1 } ^ { i } E _ { k } R \tilde { D } _ { k } ^ { n - 1 } } } \\ { { \displaystyle \sum _ { k = 1 } ^ { i = M } \frac { t } { \varepsilon _ { k } ( M ) D _ { k } ^ { n - 1 } } + \sum _ { k = 0 } ^ { i } E _ { i } R \tilde { D } _ { k } ^ { n - 1 } } } \\ { { \mathrm { } } } \\ { { \displaystyle E _ { i } + \sum _ { k = 1 } ^ { i = M } E _ { k } R \tilde { D } _ { k } ^ { n - 1 } } } \end{array} =  
$$

即

$$
\sum _ { l = 0 } ^ { l = M } R D _ { i l } ^ { n - 1 } = 1
$$

由式（9)、（10）可知 $R D _ { i j } ^ { n }$ 满足完整性的前提是$R D _ { i j } ^ { n - 1 }$ 满足完整性。已知传统蒙特卡罗方法得到辐射传递因子的初始值 $R D _ { i j } ^ { 0 }$ 满足完整性，由递推关系知， $R D _ { i j } ^ { n }$ 满足完整性。

# 2方法验证

选取如图1所示正方形空腔，空腔表面均为漫灰体表面，发射率为0.5，每个表面划分为一个网格单元，每个单元模拟光束量为 $1 \times 1 0 ^ { 3 }$ 。倒易性误差定义为

$$
\Delta _ { i j } = \Delta _ { j i } = \left| \frac { 2 \left( E _ { i } R D _ { i j } - E _ { j } R D _ { j i } \right) } { E _ { i } R D _ { i j } + E _ { j } R D _ { j i } } \times 1 0 0 \% \right|
$$

倒易性误差和完整性误差随迭代次数的变化分别如图2和图3所示，本文提出的IBSMC方法计算得到的辐射传递因子倒易性误差的量级随双向统计迭代次数的增加呈线性下降趋势，双向统计的迭代过程中辐射传递因子完整性保持非常好，证明了IBSMC方法的可靠性。

![](images/1c6b72fb4f34f3d279a9360dc4bc3a53361a53b20d65cc2aaff4f4f1ad97b5f8.jpg)  
图1 正方形空腔Fig.1 Square cavity

![](images/c0f2089e209ff5eeecbf2efa35bb1a2b87181ed1194a073f33e6f276ce0480e4.jpg)

利用传统的蒙特卡罗方法计算耗时 $7 . 4 \times 1 0 ^ { - 3 }$ s，采用本文所建IBSMC方法进行20次双向统计过程耗时增加 $1 . 0 \times 1 0 ^ { - 5 }$ s，仅占传统蒙特卡罗方法计算耗时的 $0 . 0 8 \%$ 。而传统蒙特卡罗方法要达到相同的倒易性误差精度和完整性精度需要的模拟光束量大约为每个单元 $1 \times 1 0 ^ { 1 0 }$ ，耗时为 $3 . 9 \times 1 0 ^ { 4 } ~ \mathrm { s }$ ，远多于IBSMC 方法。

为考核所建IBSMC方法在热辐射传输问题求解上的优势，选取如图4所示的模型进行计算，模型是由三个正方形表面组成的腔体结构，尺寸如图所示，材料密度为 $5 0 0 ~ \mathrm { k g / m ^ { 3 } }$ ，热传导系数为0.1$\mathrm { W / ( m { \cdot } K ) }$ ，比热容为 $1 0 0 \mathrm { ~ J / ( k g { \cdot } K ) }$ 。外部边界加载$5 0 0 \mathrm { ~ K ~ }$ 的恒温边界条件。辐射表面采用漫灰体假设，表面发射率为0.2，每个表面单元模拟光束量为$1 \times 1 0 ^ { 3 }$ 。网格划分如图5所示。

采用非定常求解方法求解该辐射平衡问题，时间方向采用Newton-GMRES隐式迭代推进求解，时间步长取0.01 s，计算 17000 个时间步。计算表明，16000个时间步之后温度场不再变化，说明问题达到了辐射平衡。

![](images/30dba78d4eca04db22798810d70df15414a797f91b083c2a0581eccc1ea77706.jpg)  
图3完整性误差Fig.3 Error of the integrity

![](images/b0e02d033121139b6780d1b504cf640e6729f2e7ac7d1cf2c71ac90c8e0bd3ef.jpg)  
图2倒易性误差 Fig.2 Error of the reciprocity   
图4热辐射问题计算模型

![](images/b304446c09105977e6e122f697fb9b5b5e2107acb5de427ca66aefa20e211562.jpg)  
Fig.4 Model for Radiative Heat Tansfer   
图5网格划分  
Fig.5 Mesh for Radiative Heat Tansfer

图6给出了辐射平衡温度分布随双向统计迭代步数的变化。(a)-(f）分别代表了双向统计迭代步数为0、1、5、10、15、20时的辐射平衡温度分布。理论辐射平衡温度分布为 $5 0 0 \mathrm { K }$ 的均匀分布。可以看出，双向统计蒙特卡罗方法 $\scriptstyle ( \mathrm { n = 1 } )$ ）虽然在求解精度上较传统蒙特卡罗方法有明显的提高，但其误差还是相对较大。而迭代双向统计蒙特卡罗方法的求解精度随迭代步数的增加而提高，当迭代步数大于15时，稳态温度分布已基本接近理论值。

0.004 0.0040.002 0.002T/K T/K  
m 500.2 500.2  
y 0 499.8 0 500 499.8499.6 499.6-0.002 499.4 0.002 499.4499.2 499.2499 499-0.004 498.8-0.004 498.8498.6 498.6-0.004-0.00200.0020.004 -0.004-0.00200.0020.004x/m x/m(a) (b)0.004 0.0040.002 口 0.002 口T/K T/K  
m 500.2 500.2  
以 0 49.8 0 499.8499.6 499.6-0.002 499.4 -0.002 4994499 499-0.004 498.8 -0.004 498.8-0.004-0.002 0.0020.004 -0.004-0.00200.0020.004x/m x/m(c) (d)0.004 0.0040.002 口 0.002 □T/K T/K  
u/A 0 002 0 0028499.6 499.6-0.002 499.4 -0.002 499.4499.2 499.2499 499-0.004 498.8 -0.004 498.8498.6 498.6-0.004-0.00200.0020.004 0.004-0.00200.0020.004x/m x/m(e) (f)

平衡温度场最小温度与理论温度之差、最大温度与理论温度之差和最大温度与最小温度之差随双向统计迭代步数的变化如图7所示，由图7可以看出，当双向统计迭代步数为1时，即双向统计蒙特卡罗方法，温度差虽有明显下降，但此时温度差仍然相对较高。随着双向统计迭代步数的增加，温度差急剧下降，当迭代次数大于15时，温度差趋于稳定，已基本接近于零，说明迭代双向统计蒙特卡罗方法可以有效提高热辐射传输问题的求解精度，且精度较双向统计蒙特卡罗方法有较大提高。

![](images/ad134b06b9a76e02e6a2373b7a59012e29d06b7ed8a268af15b31b179aa6d0a4.jpg)  
图6不同迭代次数时平衡温度场分布 Fig.6 Temperature distribution along the number of iterations   
图7不同迭代次数时温度误差 Fig.7 Temperature distribution along the number of iterations

# 3结论

本文将求解热辐射传输问题的双向统计蒙特卡罗方法分解为归一化过程和双向统计过程，基于迭代思想提出了迭代双向统计蒙特卡罗方法，分析表明本文所建方法可以进一步提高辐射传递因子的倒易性，从而以较小的耗时代价进一步提高热辐射计算精度。通过文中算例和分析可以得到以下结论：

1）本文所建迭代双向统计蒙特卡罗方法摆脱了传统双向统计蒙特卡罗方法对等权抽样假设的依赖，具有更广的适用性。2)迭代双向统计蒙特卡罗方法获得的辐射传递因子满足完整性，其倒易性误差的量级随双向统计迭代次数的增加而呈线性下降趋势。3)将迭代双向统计蒙特卡罗方法应用到含空腔结构的辐射/导热耦合边界问题，结果表明本文所建方法可以提高热辐射传输问题的求解精度，并且求解精度随着双向统计迭代次数的增加而提高。

# 参考文献

[1]Howell JR,Perlmutter M.Monte Carlo Solution of ThermalTransfertroughRadiantMedia betweenGrayWalls [J].Journal of Heat Transfer,1964,86(1):547-560   
[2]Howell JR.The Monte Carlo Method in Radiative Heat Tansfer[J].ASMEJ.Heat Tansfer,1998,120(4):547-560   
[3]景丽,王广飞，唐绍峰，等.金属蜂窝夹芯板辐射导热耦合问 题[J].哈尔滨工业大学学报，2010,42(5)：827-831 JINGLi,WANG Guangfei, TANG Shaofeng,et al. Radiation and Conduction Coupling Problems of Honeycomb Sandwich Panel [J].Journal of Harbin Institute of Technology,2010,42(5):827-831   
[4]方茜茜，方伟，王凯．蒙特卡罗法计算黑体空腔有效发射率 [J].中国光学，2012,5(2):167-173 FANG Qianqian，FANG Wei，WANG Kai.Calculation ofEffective Emissivity of Blackbody Cavities by MonteCarlo Method [J].Chinese Optics,2012,5(2):167-173   
[5]艾青，孙凤贤，夏新林.求解热辐射传递的移动区域蒙特卡 罗法[J].工程热物理学报,2012,33(10):1781-1784 AI Qing，SUN Fengxian，XIA Xinlin.Mobile-Region Monte Carlo Method for Thermal Radiative Transfer [J].Journal of Engineering Thermophysics,2012,33(10): 1781-1784   
[6]赵越，唐桂华,陶文钰.碳黑掺杂 $\mathrm { S i O _ { 2 } }$ 气凝胶热辐射特性的 蒙特卡罗计算[J].工程热物理学报，2015,36(3)：591-595 ZHAO Yue,TANG Guihua,TAOWenquan.Monte Carlo Study on Radiative Properties of Silica Aerogel Insulation Doped With Carbon[J].Journal of Engineering Thermophysics,2015,36(3):591-595   
[7]张伟清，宣益民，韩玉阁．单元表面间辐射传递系数的新型 计算方法[J].宇航学报,2005,26(1)：77-80 ZHANG Weiqing，XUAN Yimin，HAN Yuge.A New Method of Radiative Transfer Coefficient between Unit Surfaces [J]. Journal of Astronautics,2005,26(1): 77-80   
[8]李鹏，肖泽娟，程慧尔．蒙特卡洛模拟漫辐射时两种确定表 面发射方向方法的比较[J].计算物理，2006，23(4)：457- 460 LI Peng,XIAO Zejuan,CHENG Huier.Determination of Emimive Direction from a Difusing Surface in Monte Carlo Simulation [J].Chinese Journal of Computational Physics,2006,23(4):457-460   
[9]夏新林,任德鹏，郭亮,等.求解介质内热辐射传递的双向统 计蒙特卡罗法[J].工程热物理学报，2006,27(2)：21-24 XIA Xinlin,REN Depeng，GUO Liang.Bidirectionally StatisticalMonteCarloMethodforRadiativeHeat Transfer in Medium [J]. Journal of Engineering Thermophysics, 2006,27(2):21-24   
10]艾青，夏新林,李德富．热辐射传递求解的蒙特卡罗法新型 统计模式[J].科学技术与工程，2009,9(14)：4149-4151 AI Qing，XIA Xinlin，LI Defu.New Statistical Mode ofMonte Carlo Method for Radiative Heat Transfer in Medium [J].Science Technology and Engineering，2009, 9(14): 4149-4151