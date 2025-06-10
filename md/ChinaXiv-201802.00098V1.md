# 窗口材料光学常数的双厚度反演方法

李栋¹，夏新林²，艾青²

（1．东北石油大学土木建筑工程学院，黑龙江大庆163318；2．哈尔滨工业大学能源科学与工程学院，黑龙江 哈尔滨 150001)

摘要：建立了求解单层和双层窗口光谱透射比的正问题模型，提出了一种基于两块相同厚度窗口透射光谱反演其光学常数（吸收指数 $k$ 、折射率 $n$ ）的方法，研究其与现有方法的区别，分析了三种反演方法的适用范围。将已知文献中硒化物玻璃的光学常数作为“真实值”，通过正问题模型求解窗口的光谱透射比作为“实验测量值”，利用反演方法计算 $n$ 和 $k$ ，并分析实验偏差对计算的影响。研究结果表明：（1）新的反演方法与现有的双厚度方法精度基本相同；（2）三种反演方法均受窗口材料的光学常数影响，但在其适用范围内计算精度较高；（3）“实验测量值”存在偏差时，三种反演方法的求解精度差距较大。

关键词：窗口材料；光学常数；反演方法中图分类号：TK314 文献标识码：A

# Double-thickness Inversion Methods of Optical Constants of Window Materials

LI Dong XIA Xin-Lin² AI Qing (1. School of Architecture and Civil Engineering,Northeast Petroleum University,Daqing,150o01, China; 2. School of Energy Science and Engineering,Harbin Institute of Technology, Harbin 150o01,China)

Abstract: The direct calculation models of spectral transmittance of single and double window were developed,and a novel inversion method of optical constants( $k$ is extinction coefficient and $n$ is refractive index) of materials was proposed based on transmittnce spectrograms of double window. Differences between the new method and two others currently used methods were studied, and application ranges of methods were also investigated. Optical constants of selenide glass atained in references were selected as true values, and spectral transmittances of glass simulated based on direct calculation model were regarded as experimental values. Optical constants of selenide glass were achieved by inverse models. Influences of measurement error on inverse results were also determined. The results show that,(1） the inversed calculation precision of the new method is similar as two others methods.(2) Effects of optical constants on three inversion methods are urgent larger,but inversed calculation precision are higher in most application ranges. (3) Influences of measurement errors existed in experimental datum on the inverse precision of three methods are urgent distinctness.

Key words:window material; optical constants; inversion methods

# 0引言

窗口材料的光学常数在航空航天、建筑环境、太阳能利用、液体光学测量等领域具有重要的应用背景[1-3]。目前，测量窗口材料光学常数的方法主要包括：基于反射和透射光谱的干涉法[4-5]，椭偏法[6],结合色散关系式的单厚度透射法[7]和反射法[8]，双厚度透射法[9,10]。干涉法获取反射光谱时采用近垂直入射方式，而透射光谱却是垂直入射方式，导致获取光谱条件的不一致性。椭偏法测量弱吸收窗口材料的光学常数时容易受窗口折射率的影响。单厚度透射法和反射法需联立Kramers-Kronig（K-K)色散关系式求解窗口的光学常数，但构造K-K关系式过程已经引入理论偏差。双厚度透射法原理简单，不需要采用 $K { - } K$ 关系式，但目前的研究仅限适用于利用不同厚度窗口的透射光谱反演光学常数[9,10]。

本文分析了单层和双层窗口材料的透射特性，给出了求解其透射比的正问题模型，提出了一种新的基于两块相同厚度窗口透射光谱反演其光学常数的方法，然后分析其与现有两种双厚度透射法的区别，并分析了三种方法的适用范围，利用文献中已有的实验数据进行了模型验证，最后分析了实验偏差对反演计算的影响。

# 1数理模型

# 1.1正问题模型

设单层窗口材料厚度为 $L _ { i }$ ，吸收指数为 $k$ ，折 射率为 $n$ 。窗口上、下界面的反射率均为 $\rho$ 。假定光 线在窗口表面处的反射和折射过程遵循Fresnel定 律和Snell定律，且不考虑窗口上下界面反射光线 之间的干涉效应，则单层窗口的法向反射比 $R _ { i }$ 和法 向透射比 $T _ { i }$ 满足[10]

$$
R _ { i } = \rho + \rho T _ { i } \mathrm { e } ^ { - \frac { 4 \pi k L _ { i } } { \lambda } }
$$

$$
T _ { i } = \frac { ( 1 - \rho ) ^ { 2 } \mathrm { e } ^ { - \frac { 4 \pi k L _ { i } } { \lambda } } } { 1 - \rho ^ { 2 } \mathrm { e } ^ { - \frac { 8 \pi k L _ { i } } { \lambda } } }
$$

其中，界面反射率p满足[10]

$$
\rho = \frac { ( n - 1 ) ^ { 2 } + k ^ { 2 } } { ( n + 1 ) ^ { 2 } + k ^ { 2 } }
$$

当光线进入单块材料厚度为 $\boldsymbol { { \cal L } } _ { 1 }$ 和 $\lvert L _ { 2 }$ 的两层叠加窗口时，则两层窗口的总法向透射比 $T _ { 1 + 2 }$ 为

$$
T _ { 1 + 2 } = \frac { T _ { 2 } T _ { 1 } } { 1 - R _ { 1 } R _ { 2 } }
$$

其中， $R _ { 1 }$ 、 $T _ { 1 }$ 、 $R _ { 2 }$ 和 $T _ { 2 }$ 分别通过式（1）和式（2）计算得到。

# 1.2双厚度反演方法

传统的双厚度反演方法1和方法2需要已知不同厚度窗口的透射光谱，其推导和反演过程参见文献[10]，本文不再详述。在实际窗口光学常数测量中，经常遇到厚度均一的窗口材料。因此，由于窗□厚度相同，通过透射法测量仅能获取单一厚度窗口的透射光谱数据，导致无法采用方法1和方法2反演窗口材料的光学常数。为此，本文提出通过将两块窗口叠加在一起（中间留有一定的间隙)，然后测试两层窗口的透射光谱，就可以得到单层和双层窗口的两组透射光谱数据 $T _ { 1 }$ 和 $T _ { 1 + 2 }$ 。由这两组数据反演其光学常数，且通过式（2）和式（4）构造方程如下

$$
\rho = \frac { \sqrt { 1 - \frac { { T _ { 1 } } ^ { 2 } } { T _ { 1 + 2 } } } } { 1 + T _ { 1 } e ^ { - \frac { 4 \pi k L } { \lambda } } }
$$

$$
k = - \frac { \lambda } { 4 \pi L } \ln \frac { \sqrt { \left( 1 - \rho \right) ^ { 4 } + 4 T _ { 1 } ^ { 2 } \rho ^ { 2 } } - \left( 1 - \rho \right) ^ { 2 } } { 2 T _ { 1 } \rho ^ { 2 } }
$$

$$
n = \frac { ( 1 + \rho ) + \big [ ( 1 + \rho ) ^ { 2 } - ( 1 - \rho ) ^ { 2 } ( 1 + k ^ { 2 } ) \big ] ^ { \frac { 1 } { 2 } } } { 1 - \rho }
$$

反演计算过程：1）假定 $k$ 值；2)通过式(5)计算 $\rho$ ，通过式(6)计算新的 $k$ 值；3）利用式(7)计算 $n$ 值；4）将新的 $k$ 和 $n$ 值代入正问题模型计算窗口对应的两组法向透射比计算值，分析窗口透射比测量值和计算值的误差，若误差小于所需精度或计算次数超过要求，则计算结束，否则将计算的 $k$ 值替换假定 $k$ 值返回第2)步。

# 2计算结果与分析

# 2.1适用范围分析

窗口的透射比主要受其材料光学常数（折射率$n$ 、吸收指数 $k$ ）的影响。如表1所示，在 $n , \ k$ 范围内合理取值将其作为“真实值”，利用正问题模型计算当量厚度(当量厚度定义为窗口厚度和波长之比)1、当量厚度2以及双层当量厚度1对应的窗口透射比 $T _ { 1 }$ 、 $T _ { 2 }$ 、 $T _ { 1 + 2 }$ 作为"实验测量值”，并利用反问题模型计算 $n , \ k$ ，结合反演数据与“真实值”和“实验测量值"的相对误差，结果如图1和图2所示。其中，相对误差计算式为

$$
\varDelta = \left| \frac { D _ { \mathrm { c a l } } - D _ { \mathrm { e x p } } } { D _ { \mathrm { e x p } } } \right| \times 1 0 0 \%
$$

式中， $\varDelta$ 为相对误差; $D _ { \mathrm { c a l } } , D _ { \mathrm { e x p } }$ 分别为计算值和“真实值”。

表1不同吸收区域反演所用的当量厚度  
Table 1 Given thicknesses of different absorption area   

<html><body><table><tr><td colspan="2">区域分类 吸收指数</td><td>折射率</td><td>厚度1</td><td>厚度2</td></tr><tr><td>弱吸收</td><td>10-3</td><td>1~10</td><td>2</td><td>4</td></tr><tr><td>中吸收</td><td>10-2</td><td>1~10</td><td>0.2</td><td>0.4</td></tr><tr><td>高吸收</td><td>10-1</td><td>1~10</td><td>0.02</td><td>0.04</td></tr><tr><td>强吸收</td><td>1</td><td>1~10</td><td>0.002</td><td>0.004</td></tr></table></body></html>

如图1所示，方法1仅在部分吸收区域反演结果误差较小，如吸收指数小于 ${ { 1 0 } ^ { - 2 } }$ 、折射率在

1.01-1.75区间 $k$ 的反演相对误差小于 $1 \%$ ，当折射率在1.01-2.82区间时其反演误差接近 $10 \%$ 。这是由于方法1忽略高阶反射项的影响，导致在部分区域反演误差较大，在高折射率区域和强吸收区域尤其明显。方法2和方法3在表1中所有吸收区域范围内其吸收指数反演结果均较好，且比方法1具有更广的适用范围。

由图2可见，除强吸收区域外，方法2和方法3反演窗口材料的折射率结果均较好，而在强吸收区域仅在高折射率区域反演结果误差较小，且其中在强吸收区域反演误差最大值超过 $140 \%$ 。如反演吸收指数精度相似，方法1仅在部分吸收区域反演结果误差较小。

0.01 0.1150- o—k=1 Q o—k=1 丨o—k=1|-k=0.1 k=0.1 —- k=0.1△k=0.01 △—k=0.01 △—k=0.01  
% 100 —k=0.001 8 3 ——k=0.001  
花 Y 0.00 花50- R DI0I01010101010101010101010101010101010I010101RQ 0-000000 -0.12 46 8 10 2 4 6 b 10 2 46 8 10n n n(a)方法1 (b)方法2 (c）方法3

![](images/9996a0949a51848e62e7b1e8f919b0f571f0ac5b2dd5863e5e5b6d3997dde54e.jpg)  
Fig.1Relative errors of extinction coefficients in inversion calculation   
图2三种反演方法求解的折射率误差  
Fig.2Relative errors of refractive indexes in inversion calculation

# 2.2 算例分析

采用文献[9]中硒化物玻璃的光学常数作为“真实值”，利用正问题模型计算厚度为 $0 . 6 \mathrm { m m }$ 、 $1 . 2 \mathrm { m m }$ 和两块叠加后的窗口透射比作为“实验值”，如图3。

![](images/e28ae565033f08b46bc552cf39a3c09c2c005602f7c88da33c92f51ef76f9b4c.jpg)  
图1三种反演方法求解的吸收指数误差  
图3材料的光谱透射比  
Fig.3 Spectral transmittance values of windows

采用三种反演方法，分别利用“实验值”计算窗口材料的 $n$ 、k，结果如图4所示。

由图4可知，如同反演方法使用范围的分析结果基本一致，方法2和方法3反演该窗口材料吸收指数的精度较高且基本一致，而方法1的反演误差接近 $6 \%$ ，从而进一步说明前面方法适用范围分析的可靠性。由图同时可见，方法2和方法3反演该窗口材料折射率的精度也较好且基本一致，其最大反演误差小于 ${ { 1 0 } ^ { - 7 } }$ ，而方法1的反演误差却为 $4 \%$ 这也说明本文提出的新双厚度方法反演窗口材料光学常数的精度同传统反演双厚度方法2差别较小，足以可见新方法反演计算窗口材料的光学常数在多数区域是可靠的。

![](images/d91d9eeee872ba9fb3a0bfb6a1a923e2980338a2971fb6c9b3f15217c390fcee.jpg)  
图4光学常数反演结果（左为吸收指数，右为折射率）

Fig.4 Inversion results of optical constants（Left is extinction coefficient, right is refractive index）

考虑实验偏差的影响时，采取将适用范围分析中的材料透射比实验数据分别加以 $\gamma { = } 0 . 0 1 \% . 0 . 1 \%$ ，$1 \%$ 的相对误差（正偏差)，并将该“实验值”作为反演的已知量，其余计算条件不变，反演计算光学常数n、k，并采用式（8）计算与“真实值”的相对误差，结果如图5和图6所示。

![](images/2a039a27fd569fa8c73ee61eaaabe35dbb580f30167085878b20d05490fe1b2a.jpg)  
Fig.5Relative errors of extinction coefficients in inversion calculation

![](images/a9ef136cbcdac1138444096bd8ee8a58e93b18355e441c279079815a473cd138.jpg)  
图5吸收指数反演误差  
图6折射率反演误差  
Fig.6Relative errorsof refractive indexes in inversioncalculation

通过图5和图6可看出，当实验数据存在偏差时，三种方法反演光学常数的计算精度发生较大变化。如图5(a)所示，在计算偏差范围内，实验偏差对方法1反演窗口材料的吸收指数影响较小，且其误差约为 $6 \%$ 。如图5(b)所示，反演吸收指数时，方法2在偏差小于 $0 . 0 1 \%$ 时，实验偏差对其反演计算影响很小，当实验偏差 $1 \%$ 时其最大误差发生在强吸收区域且仅为 $0 . 4 3 \%$ ，从而说明方法2反演吸收指数时具有明显的抗干扰性。如图5(c)所示，实验偏差对方法3的影响较大，且随着实验偏差增大其反演误差也不断增加。同时由图5(c)还可见，反演误差和偏差存在一定的线性关系。

如图6(a)所示，在计算偏差范围内，实验偏差对方法1反演窗口材料折射率的影响较小，其大部分数据的反演误差约为 $4 \%$ ，但实验偏差为 $1 \%$ 时反演误差却减小至 $3 \%$ 。这是由于实验偏差恰恰补偿了忽略高阶反射项所带来的结果。如图 5(b)和 5(c)所示，实验偏差对方法2和方法3反演材料的折射率影响趋势一致，方法2在强吸收区域实验偏差造成的影响较明显且其最大误差约为 $1 . 4 \%$ ，而方法3在整个吸收区域的反演误差约为方法2的两倍。

# 3结论

本文开展了窗口材料光学常数的正、反问题模型研究，以其光谱吸收指数、折射指数的反演模型为研究对象，分析了三种反演方法的适用范围，得到如下结论：

（1）基于两块相同厚度窗口透射光谱反演其光学常数的方法，可以结合实验获取窗口材料的光学常数。

（2）反演方法受材料的光学常数影响较大，但在其适用范围内计算精度高。方法2和方法3反演吸收指数受其实际值影响较小，方法1仅在有限的吸收区域反演误差较小。在多数吸收区域反演折射率时，方法2和方法3精度较好，而方法1较差。

（3）实验数据存在偏差时，三种反演方法求解光学常数的精度差距较大。在计算偏差范围内，反演吸收指数时，实验偏差对方法1影响较小（误差约为 $6 \%$ )，对方法2影响更小，但对方法3影响较大；反演折射率时，实验偏差对方法1影响较小，对方法2和方法3的影响更小，但对方法3的影响约为方法2的两倍。

# 参考文献

[1]Siegel R. Transient Effects of Radiative Transfer in Semitransparent Materials [J]. International Journal of Engineering Science, 1998,36(12-14):1701-1739.   
[2]Guardoa A, Coussirat M,Valero C,et al. CFD Assessment of the Performance of Lateral Ventilation in Double Glazed Facades in Mediterranean Climates [J].Energy and Buildings,2011,43 (9): 2539-2547.   
[3]Porter JM,Jeffries JB,Hanson R K.Mid-infrared Absorption Measurements of Liquid Hydrocarbon Fuels near $3 . 4 \mu \mathrm { m }$ [J]. Journal of Quantitative Spectroscopy & Radiative Transfer, 2009,110(18):2135-2147.   
[4] Caricato A P, Fazzi A， Leggieri G. A Computer Program for Determination of Thin Films Thickness and Optical Constants [J]. Applied Surface Science，2005，248 (1-4):440-445.   
[5] HUANG Shuiping，Wang Zhanshan，Xu Jian, et al. Simulation of the Spectra and Determination of the Optical Constants of Online Low-emission Glass from Visible to Mid-infrared Region [J]. Thin Solid Films,2009,517 (9): 2963-2967.   
[6]Franta D,Ohlidal I, Petr K, et al. Influence of Overlayers on Determination of the Optical Constants of ZnSe Thin Films [J]. Journal of Applied Physics，2002，92(4): 1873-1879.   
[7]Joraid A A,Alamri S N, Solieman A,et al. Dielectric Modeling of the Transmittance Spectra of Thin $\mathrm { A s } _ { 2 0 } \mathrm { S } _ { 8 0 }$ （20 Films[J].Optics& Laser Technology，2011，43 (7):1243-1248.   
[8]Bridou F, Cuniot-Ponsard M, DesvignesJM. Experimental Determination of Optical Constants in the Vacuum Ultra Violet Wavelength Region between 80 and $1 4 0 \ \mathrm { n m }$ :a Reflectance Versus Thickness Method and its Application to ZnSe [J]. Optics Communications,2007, 271 (2): 353-360.   
[9] 苏星,李正芬，刘成赞，等.一种红外硒化物玻璃的光学 常数及其增透膜[J].红外技术,1996,18(5):15-18. Su Xing,Li Zhengfen,Liu Chengzan，et al. Optical Constants of a Selenide Glass and its AR Coatings [J]. Infrared Technology, 1996,18(5):15-18.   
[10] Li Dong，Ai Qing，Xia Xinlin. Determined Optical Constants of ZnSe Glass from 0.83 to $2 1 \mu \mathrm { m }$ by Transmittance Spectra: Methods and Measurements [J].

Japanese Journal ofApplied Physics,2013,52(4):046602.

李栋  
黑龙江大庆市东北石油大学土木建筑工程学院  
邮编163318  
电话：0459-6507763 15164563872  
电子信箱:lidonglvyan@126.com