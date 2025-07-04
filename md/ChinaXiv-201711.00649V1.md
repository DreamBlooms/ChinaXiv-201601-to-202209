# 半透明介质场参数的非接触测量算法研究

牛春洋 齐宏 贾腾 阮立明 谈和平（哈尔滨工业大学能源科学与工程学院，哈尔滨150001)

摘要：本文在考虑半透明介质吸收、发射以及散射衰减作用的情况下采用视在光线法计算某探测方向上介质边界出射辐射强度分布作为逆问题的输入数据，采用LSQR方法在介质辐射特性参数已知情况下重建介质三维温度分布，重建结果显示，无论有无测量误差存在，利用 LSQR 方法都可以在已知辐射特性参数的条件下很好地重建出介质的三维温度场。在此基础上提出LSQR-SPSO混合算法，并应用于同时重建三维温度场及辐射特性参数（吸收系数、散射系数)。计算结果显示，无论有无测量误差存在，利用LSQR-SPSO混合算法都可以很好地同时重建出介质的吸收系数、散射系数及三维温度场，相比较而言，介质的温度场更容易被重建出来。

关键词：LSQR-SPSO；温度场；辐射特性参数；逆问题中图分类号：TK123 文献标识码：A

# Research on Non-Contact Measurement Algorithm of Retrieving the Parameters distribution of Semi-transparent Medium

NIU Chun-Yang QIHong JIA Teng RUAN Li-MingTAN He-Ping (School of Energy Science and Engineering,Harbin Institute of Technology, Harbin15ooo1, China)

Abstract: For the semi-transparent media which only consider the absorption,emission and scattering attenuation characteristics,the outgoing radiative intensities at the boundary surface were simulated by the line-of-sight (LOS) method,which were served as input for the inverse analysis.The least-square QR decomposition (LSQR) algorithm was used to estimate the three dimensional temperature distributions of the semi-transparent media with known radiative properties.And the retrieval results show that the temperature distributions could be retrieved accurately even with noisy data.For the participating media with unknown radiative properties,a hybrid least-square QR decomposition (LSQR） - Stochastic Particle Swarm Optimization (LSQR-SPSO） algorithm was developed to estimate the 3-D temperature distributions and radiative properties (absorption coeffcients and scatering coefficients）simultaneously.And the retrieval results show that the absorption coeficients,scattring coeffcients and 3-D temperature distributions also could be retrieved accurately even with measurement errors. It was also found that the temperature field could be estimated more accurate than the radiative properties.

Key words: LSQR-SPSO; Temperature field; Radiative properties; Inverse problem

# 0引言

目前对于介质温度的测量主要分为接触式测量和非接触式测量两类。接触式测量主要是指使用各种不同类型热电偶、示温漆、热电阻等接触式物理探针进行测量，但这些经典的接触式测量方法不仅干扰流场，测量误差大，而且在很多场合无法使用，更为重要的是接触式测量方法很难实现温度分布测量。非接触式辐射成像测温技术通过对介质辐射图像处理进行温度测量，具有测量精度高、非插入式、实时连续测量等优点，且能够获得三维温度分布信息，无疑代表着一种非常有前景的技术研究趋势。但该技术不能通过CCD相机或热像仪测试技术直接获得介质内部温度分布，需要建立复杂的辐射逆问题计算模型，且通常需要已知介质的辐射物性参数。

对于非接触式辐射成像测温技术，其核心问题就是建立高效、准确、稳定的介质温度场及物性场重建算法，这也成为近年来国内外学者广泛关注的研究热点。刘林华、谈和平等[1提出了网络搜索与共轭梯度相结合同时反演一维半透明介质内辐射源项和壁面黑度的混合方法。齐宏和阮立明等[2,3]首次将智能微粒群引入辐射源项和辐射物性的逆问题研究中，发现该算法具有对不依赖初值且无需求解目标函数导数等优点。周怀春、郑楚光等4提出了联合反演一维介质温度和辐射物性的方法。娄春等5提出了一种解耦方法用于联合重建一维光学薄火焰或非散射性弥散介质的温度分布和辐射物性参数。刘冬等[6采用最小二乘QR分解法（LSQR）结合反向蒙特卡洛法对二维参与性介质温度场和辐射物性参数进行反演研究。Klose 等7基于有限差分离散坐标法和准牛顿法研究了稳态传输光学成像问题。综上所述，目前对于参与性介质的温度场重建研究，多为一维、二维温度场的检测，而且多数需要已知或者假定介质辐射特性参数，而对于三维温度分布和辐射特性参数多宗量同时重建研究较少。

参与性介质温度场重建问题是典型的不适定问题，传统求解方法包括Tikhonov正则化方法、截断奇异值分解（TSVD）方法及LSQR方法等。本文将针对考虑吸收、发射及散射衰减的半透明介质，在辐射特性参数已知条件下采用LSQR方法利用探测器在介质边界处接收到的辐射强度信息重建介质三维温度分布。当介质辐射特性参数未知时，提出随机微粒群（SPSO）算法与LSQR算法结合的LSQR-SPSO混合算法，对半透明介质三维温度场和辐射特性参数（吸收、散射系数）进行同时重建。

# 1辐射传输正问题

在仅考虑半透明介质的吸收、发射以及散射衰减作用时可采用视在光线法计算任一探测方向上的辐射强度，此时的辐射传输方程可表示成如下形式：

$$
\frac { \mathrm { d } I \left( \mathbf { r } , \tau \right) } { \mathrm { d } \tau } + I \left( \mathbf { r } , \tau \right) = \left( 1 - \omega \right) I _ { \mathrm { b } } \left( \tau \right)
$$

式中， $I \big ( \mathbf { r } , \tau \big )$ 为方向辐射强度； $\tau$ 为光学厚度，$\tau = \kappa _ { \mathrm { a } } \cdot s$ ； $\kappa _ { \mathrm { a } }$ 为吸收系数； $\omega$ 为反照率，${ \omega } { = } { \kappa _ { \mathrm { s } } \ } / \left( { \kappa _ { \mathrm { a } } + \kappa _ { \mathrm { s } } } \right)$ ； $\kappa _ { \mathrm { s } }$ 为散射系数。

$$
\mathbf { A I _ { b } } = \mathbf { I _ { n } }
$$

将 $\mathbf { r }$ 方向的探测平面划分为 $M$ 个单元，则可得到介质内任意单元温度与介质边界出射辐射强度之间的方程组，写成矩阵形式如下，

考虑如图1所示的圆柱形半透明介质模型，四周为透明边界条件，忽略环境辐射，则针对任意 $\mathbf { r }$ 方向的边界出射辐射强度表达式为，

式中，A为系数矩阵； $\mathbf { I _ { b } }$ 为黑体辐射强度向量； ${ \bf { I } } _ { \bf { n } }$ 为出射辐射强度向量，即探测器接收到辐射强度向量。

$$
+ \sum _ { i = 1 } ^ { n - 1 } \left( \exp { \left( - \sum _ { j = i + 1 } ^ { n } \tau _ { j } \right) } - \exp { \left( - \sum _ { j = i } ^ { n } \tau _ { j } \right) } \right) \left( 1 - \omega _ { i } \right) I _ { \mathrm { b } i }
$$

![](images/324f16c4199ed29aee6e15b4f61ce10a1f8f547c92f05375047679c8f847f991.jpg)  
Fig.1 The geometric model   
图1几何模型

# 2温度场及辐射特性参数重建方法

式中， $n$ 为 $\mathbf { r }$ 方向某一探测线所经过的网格单元数目； $\tau _ { j }$ 为探测线经过第 $j$ 个网格单元的光学厚度; $I _ { \mathsf { b } i }$ 为探测线经过第 $i$ 个网格单元的自身黑体辐射强度，

$$
I _ { n } \left( \mathbf { r } \right) = I _ { \mathsf { b } n } \left( 1 - \exp \left( - \tau _ { n } \right) \right)
$$

# 2.1基于LSQR方法重建三维温度场

在辐射特性参数已知条件下，方程组(3)为线性方程组，因此可直接采用LSQR 方法求解式(3)，由探测器接收到的辐射强度分布重建介质三维温度场。LSQR方法是Paige 和 Saunders[8于1982 年提出的一种特别适合求解系数矩阵为大型、稀疏矩阵线性方程组的方法。LSQR方法求解的思路是首先把任意系数矩阵方程化为系数矩阵为方阵的方程，然后利用Lanczos方法，求解方程的最小二乘解。

# 2.2基于LSQR-SPSO 混合算法同时重建三维温度场及辐射特性参数

$I _ { \mathrm { b } i } = \sigma T _ { i } ^ { 4 }$ ； $T _ { i }$ 为探测线经过第 $i$ 个网格单元的温度。

若介质辐射特性参数未知，则需根据探测器接收到的辐射强度分布同时重建介质温度场及辐射特性参数，此时方程组(3)为非线性方程组，不能采用LSQR方法直接求解。因此，本文引入SPSO 算法，并将其与LSQR方法结合同时重建介质的三维温度场及辐射特性参数。SPSO 算法最早是由 Zeng 等[9]提出的能够保证以概率1收敛于全局最优解的算法，广泛应用于各种优化问题的求解[10]。与基本PSO 算法相比，SPSO去掉了微粒先前的速度项，使得速度失去记忆性，从而减弱了全局搜索能力，但这样也使得在进化的每一代均至少有一个微粒由于处于微粒群的历史最好位置而停止进化，利用停止进化的微粒改善全局搜索能力是SPSO算法的基本思想。

对于温度场和辐射特性参数同时重建问题需要两个不同探测方向 $\psi _ { 1 }$ 和 $\psi _ { 2 }$ 的探测器接收到的辐射强度分布 ${ \bf { I } } _ { \bf { n } 1 }$ 和 ${ \bf { I } } _ { \mathbf { n } 2 }$ 作为已知条件，利用 SPSO 算法搜索吸收系数，采用LSQR方法根据 $\psi _ { 1 }$ 方向的辐射强度分布 ${ \bf { I } } _ { \bf { n } 1 }$ 计算假设的温度场 $\mathbf { T ^ { \prime } }$ ，然后根据假设的温度场 $\mathbf { T ^ { \prime } }$ 由正问题计算得到假设的 $\psi _ { 2 }$ 方向的辐射强度分布 ${ \bf { I } } _ { \mathbf { n } 2 } ^ { \prime }$ ，并与 $\psi _ { 2 }$ 方向探测器探测到的真实的辐射强度 ${ \bf { I } } _ { \mathbf { n } 2 }$ 构造目标函数，如式(4)所示，利用SPSO算法搜索吸收系数使目标函数极小化，进而同时重建出介质的吸收系数、散射系数以及三维温度分布。

$$
R \big ( \mathbf { T } , \kappa _ { \mathrm { a } } , \kappa _ { \mathrm { s } } \big ) = \frac { \big \| \mathbf { I } _ { \mathbf { n } 2 } ^ { \prime } - \mathbf { I } _ { \mathbf { n } 2 } \big \| } { \big \| \mathbf { I } _ { \mathbf { n } 2 } \big \| }
$$

# 3重建结果及分析

如图1所示的圆柱形几何模型，半径为$r = 0 . 5 \mathrm { m }$ ，轴向长度为 $L = 2 0 \mathrm { m }$ ，网格划分为$N \varphi \times N r \times N z = 1 \times 1 0 \times 2 0$ ，探测线数为 $M = 1 0 0 0 0$ ，按(5)式假设介质的真实温度场，$T \left( z , r \right) = - \frac { 2 6 0 0 } { 1 7 } \left( z - 2 0 . 0 \right) \times \left( 0 . 5 - 3 . 0 r ^ { 2 } + 2 . 0 r ^ { 3 } \right) + 8 0 0$ ⑤式中， $z$ 为圆柱体轴向坐标， $\boldsymbol { r }$ 为圆柱体径向坐标。

# 3.1基于LSQR方法的温度场重建结果分析

首先假设介质的辐射特性参数是已知的，假设吸收系数为 ${ \kappa _ { \mathrm { a } } } = 0 . 8$ ，散射系数为 $\kappa _ { s } = 1 . 8$ ，介质真实温度分布如式(5)所示，分别在无测量误差以及$1 \% . 3 \%$ 测量误差的条件下采用LSQR方法根据探测方向 $\theta = 9 0 ^ { \mathrm { o } }$ ， $\varphi = 4 5 ^ { \mathrm { { o } } }$ 上的探测器接收到的辐射强度分布重建介质三维温度分布，重建结果如图2所示。

![](images/3568bdaa24d29c2588c0046a494a2cf60f39369804ea3f294c3f898c00250afb.jpg)  
图2辐射特性参数已知时温度场重建结果  
Fig.2 The reconstruction results of temperature field with known radiative properties

从图2中可以看出，无论有无测量误差都可以得到很好地温度场重建结果，不同测量误差条件下的各网格单元重建误差分布如图3所示，从图中可以看出在无测量误差时温度场的重建误差分布在$1 0 ^ { - 1 1 } { \sim } 1 0 ^ { - 1 5 }$ 量级；随着测量误差的增大，重建误差也随之增大；但即使存在 $3 \%$ 的测量误差时其温度场重建误差最大值只有 $0 . 9 6 \%$ ，其重建误差平均值为$0 . 1 2 \%$ ，因此说明在辐射特性参数已知的情况下，使用LSQR方法可以很好地重建出介质的三维温度场，该方法具有较好的计算精度和计算稳定性。

![](images/e80f4b20dfa0444612b86ab19052ccc8421328f7873fba283f3ff6131c8d8d20.jpg)  
图3辐射特性参数已知时温度场重建误差分布 Fig.3 The reconstruction error distribution of temperature field with known radiative properties

# 3.2辐射特性参数和温度场同时重建结果分析

假设介质的辐射特性参数未知，设吸收系数真值为 $\kappa _ { \mathrm { a } } = 0 . 4 \mathrm { m } ^ { - 1 }$ ，搜索范围为 $[ 0 . 1 \mathrm { m } ^ { - 1 } { \sim } 1 . 0 \mathrm { m } ^ { - 1 } ]$ ，散射系数真值为 $\kappa _ { s } = 1 . 6 \mathrm { { m } ^ { - 1 } }$ ，搜索范围为 $[ 1 . 0 \mathrm { m } ^ { - 1 } { \sim } 2 . 0 \mathrm { m } ^ { - 1 } ]$ ，介质真实温度分布如式(5)所示，分别在假设无测量误差以及测量误差分别为 $1 \%$ 、 $3 \%$ 的条件下采用LSQR-SPSO 方法根据探测方向为 $\theta = 9 0 ^ { \mathrm { o } }$ ， $\varphi = 3 5 ^ { \mathrm { o } }$ 和 $\theta = 6 0 ^ { \mathrm { o } }$ ， $\varphi = 4 5 ^ { \mathrm { { o } } }$ 两个方向上的探测器接收到的辐射强度分布同时重建介质吸收系数、散射系数及三维温度分布。不同测量误差条件下的吸收系数和散射系数重建结果如表1所示。

对于辐射特性参数的反演结果，从表1中可以看出，在无测量误差的情况下，介质的吸收系数和散射系数可以被精确地反演出来；而存在测量误差时介质吸收系数和散射系数的重建误差随测量误差的增大而增大，但都在合理的范围内。因此无论是否存在测量误差，采用LSQR-SPSO混合算法都可以将介质的吸收系数和散射系数合理地重建出来。

对于温度场的反演结果，不同测量误差条件下的各网格单元重建误差分布如图4所示，从图中可以看出在无测量误差时温度场的重建误差分布在${ { 1 0 } ^ { - 5 } }$ 量级，随着测量误差的增大，重建误差也随之增大，即使存在 $3 \%$ 的测量误差的时其温度场重建误差最大值只有 $1 . 2 6 \%$ ，其重建误差平均值为 $0 . 7 0 \%$ 。由此可以看出采用LSQR-SPSO算法可以较好地同时重建出介质的辐射特性参数和三维温度场。

同时发现在对辐射特性参数和温度场同时重建时，温度场很容易被重建出来，并具有较高的精度，而辐射特性参数重建结果相对较差，较难重建出来，这可能是由于测量数据对辐射特性参数的敏感性较小或者是辐射特性参数存在多值性造成的。

Table 1 The reconstruction results of absorption coefficient and scattering coefficients   

<html><body><table><tr><td rowspan="2">Inverse parameter</td><td rowspan="2">True value</td><td colspan="2">7=0</td><td colspan="2">y=1%</td><td colspan="2">y=3%</td></tr><tr><td>Retrieval value</td><td>£re1%</td><td>Retrieval value</td><td>εre1%</td><td>Retrieval value</td><td>re1%</td></tr><tr><td>Ka[m1]</td><td>0.4</td><td>0.4001</td><td>0.0250</td><td>0.4046</td><td>1.1500</td><td>0.4279</td><td>6.9750</td></tr><tr><td>K[m]</td><td>1.6</td><td>1.5999</td><td>0.0063</td><td>1.6190</td><td>1.1875</td><td>1.6828</td><td>5.1750</td></tr></table></body></html>

![](images/caf0310cc9cfcdd79027ad96c96c655aa75bdf6bbdaa90aee3095254347866c3.jpg)  
图4辐射特性参数未知时温度场重建误差分布 Fig.4 The reconstruction error distribution of temperature field with unknown radiative properties

# 4结论

本文在仅考虑半透明介质吸收、发射以及散射衰减作用的情况下根据采用视在光线法计算得到的某探测方向上探测器接收辐射强度分布，采用LSQR方法在介质辐射特性参数已知情况下重建介质三维温度分布。并在此基础上提出LSQR-SPSO 混合算法，将其应用于同时重建三维温度场及辐射特性参数。结果表明，当已知辐射特性参数时，无论有无测量误差，LSQR方法都可较好地重建出介质的三维温度场；当辐射特性参数未知时，无论有无测量误差，采用LSQR-SPSO混合算法都可较好地同时重建出介质的吸收、散射系数及三维温度场，证明LSQR-SPSO混合算法具有较高的计算精度和较好的稳定性，可广泛应用于半透明介质辐射特性参数和温度场重建研究。另外，在同时重建过程中，介质的温度场比辐射特性参数更容易被重建得到。

# 参考文献

[1]Liu L H,Tan HP,Yu Q Z. Simultaneous Identification of Temperature Profile and Wall Emissivities in One-dimensional Semitransparent Medium by Inverse Radiation Analysis[J].NumericalHeat Transfer,PartA,1999,36:511-525   
[2]Qi H,Ruan L M,Zhang H C,et al. Inverse Radiation Analysis in a One-dimensional Participating Slab by the Stochastic Particle Swarm Optimizer Algorithm[J]. International Journal of Thermal Sciences,2007, 46(7): 649-661   
[3]Qi H, Ruan L M, Shi M, et al. Application of Multi-Phase Particle Swarm Optimization Techniqueto Inverse Radiation Problem[J]. Journal of Quantitative Spectroscopy and Radiative Transfer, 2008,109(3): 476-493   
[4]Zhou H C, Hou YB,Chen D L,et al. An Inverse Radiative Transfer Problem of Simultaneously Estimating Profiles of Temperature and Radiative Parameters from Boundary inTensity and Temperature Measurements[J]. Journal of Quan- titative Spectroscopy and Radiative Transfer, 2002, 74: 605-620   
[5]Lou C, Zhou H C. Decoupled Reconstruction Method for Simultaneous Estimation of Temperatures and Radiative Properties in a 1-D, Gray, Participating Medium[J]. Numer. Heat Transfer Part B-Fundamental,2007, 51(3): 275-292   
[6]Liu D, Yan JH, Wang F, et al. Inverse Radiation Analysis of Simultaneous Estimation of Temperature Field and Radiative Properties in a Two-dimensional Participating Medium[J]. International Journal of Heat and Mass Transfer, 2010, 53: 4474-4481   
[7]Klose A D，Hielscher A H,Beuthan J.Quasi-Newton Methods in Iterative Image Reconstruction for Optical Tomography[J].Proceedings of SPIE,2000,3979:1323-1330   
[8]Paige C C, Saunders M A. LSQR: Sparse Linear Equations and Leasts Quares Problems[J].AMC Transaetions.Math, 1982, 8(2): 195-209   
[9] Zeng J C,Cui Z H. A Guaranteed Global Convergence Particle Swarm Optimizer[J]. Journal of Computer Research and Development, 2004,41(8): 1333-1338   
[10] Qi H,Wang D L，Wang S G,et al. Inverse Transient Radiation Analysis in One-dimensional Non-homogeneous Participating Slabs Using Particle Swarm Optimization Algorithms[J]. Journal of Quantitative Spectroscopy and Radiative Transfer,2011,112(15): 2507-2519