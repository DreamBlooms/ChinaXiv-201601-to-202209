# 宽光谱太阳能电池减反表面光谱特性研究

张玉涛’，宣益民 1，2

（1.南京理工大学能源与动力工程学院，南京，2100942．南京航空航天大学能源与动力学院，南京，210016)

摘要：本文利用时域有限差分方法，计算了三种不同的渐变折射率的单晶硅太阳能电池减反表面的光谱特性，对三种表面的减反性能进行了对比。讨论了结构参数对结构表面减反特性的影响，研究发现，蛾眼结构的单晶硅太阳能电池在整个太阳辐射光谱范围内具有最低的反射率，随着微结构高度的增加和周期的减小，有效折射率的梯度降低，减反效果更加明显。

关键词：宽光谱;渐变折射率;太阳能电池

中图分类号：TK123 文献标识码：A

# Spectral Features of Broadband Anti-Reflection Structured Surface for Si Solar Cell

ZHANG Yu-Tao1， XUAN Yi-Min1,2

(1.SchoolofEnergyandPowerEnginering,Nanjing UniversityofScience and Technology,Nanjing,210094,China;

2. School of Energyand Power, Nanjing University of Aeronautics and Astronautics,Nanjing,210o16, China)

Abstract: This paper calculates the spectral features of three diferent structured surfaces with graded refractive index for the anti-reflection of Si solar cellwith FDTD method.The spectral features of three structured surface are compared.The efects ofthe structural parameters on the spectral reflection are discussed.It is found that the reflection of moth-eye structured surface is lowest in the fullsolar spectrum among three structured surfaces. With the increase of height and reduce of period of micro-structure,the gradient of the effective refractive index in $z$ -direction is reduced and the reflection is suppressed more effectively.

Key words: broadband anti-reflection; graded refractive index; solar cell

# 0引言

随着全球能源危机的日益加剧，新型能源的开发和应用是人类解决能源问题的必然趋势。太阳能由于取之不尽以及无污染等优点，成为人类开发新能源的主要方向之一。目前，太阳能的利用方式主要有太阳能电池、热光伏、光化学催化以及其他一些能量转换装置[1-3]。早在 20 世纪 50 年代，第一块硅太阳能电池的问世，就揭开了太阳能电池研究和发展的序幕[4]。近年来，随着科研工作者的广泛关注和深入研究，使得太阳能电池技术迅猛发展。一方面，硅电池的效率不断得到提高，另一方面，也出现了多种多样的太阳能电池，单晶硅、非晶硅、GaAs、CdTe、InP等半导体材料被应用于太阳能电池的研究[4]。目前，影响太阳能电池发展和应用的主要问题是太阳能电池的效率和成本。薄膜太阳能电池的研究，对降低太阳能电池的成本有很重要的意义。

地球表面接收到的太阳辐射集中在 $0 . 3 \substack { - 2 . 5 \mathrm { ~ \mu \mathrm { m } } }$ 硅太阳能电池的禁带在 $1 . 1 2 \ \mathrm { e V }$ ，只有波长小于$1 . 1 \mu \mathrm { m }$ 的太阳能吸收以后才能直接转化为电流，所以硅太阳能电池的工作波段在 $0 . 3 \mathrm { - } 1 . 1 ~ \mu \mathrm { m }$ 。对于光滑的硅表面，大约 $30 \%$ 的太阳能会被反射出去，造成能量浪费，因此，微结构被广泛应用于硅太阳能电池，减少界面反射，提高电池效率[5-7]。然而，目前太阳能电池大多仅考虑 $0 . 3 \mathrm { - } 1 . 1 ~ \mu \mathrm { m }$ 的太阳能的利用，这部分能量大约占太阳总辐射的 $80 \%$ ，对于占太阳辐射 $20 \%$ 的 $1 . 1 { - } 2 . 5 ~ \mu \mathrm { m }$ 波段的太阳辐射，并未

考虑。

自然界中有很多生物组织结构具有很好的光学特性。研究发现，蛾眼结构具有渐变的折射率，可以很好的降低表面反射的作用，并且被应用于太阳能电池的研究。Song等将蛾眼结构应用于GaAs太阳能电池，使得0.3-2μm 的反射率得到显著降低[8]。因此，将这种结构应用于硅太阳能电池，实现0.3-2.5$\mu \mathrm { m }$ 的减反，可以有效提高太阳能的有效利用。

本文利用时域有限差分 (FDTD)方法，研究并对比了蛾眼、金字塔、圆锥三种渐变折射率的硅太阳能电池微结构表面在 $0 . 3 \mathrm { - } 2 . 5 ~ \mu \mathrm { m }$ 的光谱特性，讨论了结构参数对光谱特性的影响，并将三种结构表面的平均光谱特性以及随结构参数的变化进行对比，为提高太阳能的有效利用提供有力的理论指导。

# 1 计算模型

三种太阳能电池表面结构如图1所示，在半导体Si薄膜表面分别周期排列蛾眼、金字塔、圆锥结构，构成渐变折射率， $x$ 和 $y$ 方向的周期均为∧，蛾眼和圆锥结构的底面直径与周期相同，金字塔结构的地面边长和结构周期相同。蛾眼、金字塔、圆锥结构的高度均为 $h _ { 1 } , \mathrm { S i }$ 薄膜的厚度为 $h _ { 2 }$ ，在Si薄膜的下表面增加一层 $\mathrm { S i O } _ { 2 }$ 薄膜，在 Si薄膜和真空之间形成过渡层，构建缓变折射率，进而降低反射。Si和 $\mathrm { S i O } _ { 2 }$ 的光学参数从光学手册中选取[9]。初始的结构参数为： $\Lambda { = } 0 . 3 ~ \mu \mathrm { m }$ $h _ { 1 } { = } 0 . 6 ~ { \mu } \mathrm { m }$ $h _ { 2 } { = } 2 ~ { \mu } \mathrm { m }$ $h _ { 3 } { = } 0 . 1 5$ $\mu \mathrm { m }$ 。

图1三种宽光谱太阳能电池减反表面计算模型；(a)蛾眼(b)金字塔；(c)圆锥；(d)蛾眼结构截面及尺寸；(e)金字塔结构截面及尺寸； (f)圆锥结构截面及尺寸。

Fig.1Three broadbandanti-reflectionstructured surfaces fortheSi solarcel. (a)moth-eye,(b)pyramid,(c)cone,(d)-(f) cross-sections and geometric parameters of the structured surfaces.

从Maxwell方程出发，利用时域有限差分(FDTD)方法计算了三种宽光谱太阳能电池减反表面的光谱特性。根据Courant稳定性条件$c \Delta t = \delta / \sqrt { 3 }$ ,取时间步长 $\Delta { \sf t }$ 为0.009826 fs，最小空间步长d为 $0 . 0 0 0 2 5 \ \mathrm { m m }$ 来确保计算的收敛和精度。

为了描述微结构表面的整体性能，利用下式计算结构表面在特定波段内的平均反射率、透射率：

$$
R _ { _ { a \nu } } = \int _ { \lambda } R _ { _ { ( \lambda ) } } I _ { _ { ( \lambda ) } } \mathrm { d } \lambda \big / \int _ { \lambda } I _ { _ { ( \lambda ) } } \mathrm { d } \lambda
$$

$$
T _ { a \nu } = \int _ { \lambda } T _ { ( \lambda ) } I _ { ( \lambda ) } \mathrm { d } \lambda \big / \int _ { \lambda } I _ { ( \lambda ) } \mathrm { d } \lambda
$$

式中， $R _ { ( \lambda ) }$ 和 $T _ { ( \lambda ) }$ 分别为光谱反射率和吸收率， $I _ { ( \lambda ) }$ 为AM1.5的太阳辐射。

# 2计算结果与讨论

蛾眼结构、金字塔结构和圆锥结构三种不同宽光谱太阳能电池减反表面的光谱特性如图2所示。由于渐变折射率的形成，反射率显著降低，特别是在可见光波段，Si的消光系数比较大，吸收比较明显，能量被表面结构捕获之后，被Si有效吸收。对于 Si电池，其禁带为 $1 . 1 2 \mathrm { e V } , 0 . 3 \substack { - 1 . 1 \mu \mathrm { m } }$ 的光子被吸收后能有效转化成光电流输出，所以这个波段的吸收越高约好；而 $1 . 1 { - } 2 . 5 ~ \mu \mathrm { m }$ 的光子不能被直接转化成光电流，反而会生成热量，导致电池温度升高，降低电池的光电转换效率，因此，为了实现全光谱的太阳能利用， $1 . 1 - 2 . 5 \ \mu \mathrm { m }$ 的光子最好能透过太阳能电池，被热点模块吸收利用，从而提高太阳能利用的整体效率。将三种结构的光谱特性进行对比，可以发现，蛾眼结构在 $0 . 3 \mathrm { - } 1 . 1 ~ \mu \mathrm { m }$ 的低反射波段更宽，吸收更好。而在 $1 . 1 - 2 . 5 ~ { \mu \mathrm { m } }$ 内，蛾眼结构的反射率最低，透射最好。为了更好的对比三种结构表面的减反效果，利用式(1)计算了三种结构在0.3-1.1$\mu \mathrm { m }$ 和 $1 . 1 - 2 . 5 ~ { \mu \mathrm { m } }$ 内的反射率和透射率，如表1所示。虽然平均反射率和透射率的差异很小，但还是可以反映出来，在 $0 . 3 \mathrm { - } 1 . 1 ~ \mu \mathrm { m }$ 内，蛾眼结构具有最高的吸收率，在 $1 . 1 { - } 2 . 5 ~ \mu \mathrm { m }$ ，蛾眼结构具最低的反射率和有最高的透射率。综合考虑，蛾眼结构最适合用于宽光谱太阳能电池的减反表面。

图2三种不同宽光谱太阳能电池减反表面光谱特性； (a)反射率； (b)透射率； (c)吸收率

Fig.2Spectral featuresof threediferent broadbandanti-reflection structured surfaces forthe solarcell (a)reflection,(b) transmission,(c)absorption

表1三种不同宽光谱太阳能电池减反表面平均光谱特性  
Table1 The average spectral features of three different broadband anti-reflection structured surfaces for the solar cell   

<html><body><table><tr><td rowspan="2"></td><td colspan="3">R</td><td colspan="3">T</td><td colspan="3">α</td></tr><tr><td>蛾眼</td><td>金字塔</td><td>圆锥</td><td>蛾眼</td><td>金字塔</td><td>圆锥</td><td>蛾眼</td><td>金字塔</td><td>圆锥</td></tr><tr><td>0.3-1.1 μm</td><td>0.029</td><td>0.032</td><td>0.036</td><td>0.238</td><td>0.248</td><td>0.239</td><td>0. 733</td><td>0.72</td><td>0.725</td></tr><tr><td>1.1-2.5 μm</td><td>0.167</td><td>0.168</td><td>0.172</td><td>0.794</td><td>0.794</td><td>0.790</td><td>0.039</td><td>0.038</td><td>0.038</td></tr></table></body></html>

图3为三种宽光谱太阳能电池减反表面的光谱特性随微结构高度好 $h _ { 1 }$ 的变化。从图中可以看出，随着 $h _ { 1 }$ 的增加，三种结构的反射率均明显降低，尤其在可见光波段，减反效果比较明显。在红外波段，$h _ { 1 }$ 越大，微结构的作用越明显，薄膜特性越弱，反射率的震荡越小。当 $h _ { 1 } { = } 0 . 3 ~ \mu \mathrm { m }$ 时，微结构表面在$0 . 3 \mathrm { - } 1 . 1 \ \mathrm { \textrm { \textmu m } }$ 的反射最强，所以透射最低。在$1 . 1 { - } 2 . 5 ~ { \mu \mathrm { m } }$ 的震荡最大。随着 $h _ { 1 }$ 的增加，三种微结构表面在 $0 . 3 \mathrm { - } 1 . 1 ~ \mu \mathrm { m }$ 的吸收均呈增大的趋势。表2列出了三种不同的宽光谱太阳能电池减反表面在不同的微结构高度 $h _ { 1 }$ 下的平均光谱特性。随着 $h _ { 1 }$ 的增加， $z$ 方向有效折射率的梯度逐渐减小，反射率得到有效降低；另一方面，蛾眼结构在 $0 . 3 \mathrm { - } 2 . 5 \mu \mathrm { m }$ 内的平均反射率是最低，有效的降低了反射能量损失。然而，随着微结构厚度的增加，在 $0 . 3 \mathrm { - } 1 . 1 ~ \mu \mathrm { m }$ 的透射明显增大，吸收降低，影响Si电池的光电效率。因此，微结构的厚度不宜太大，需要综合考虑，优化设计。

图4所示为结构周期对三种宽光谱太阳能电池减反表面光谱特性的影响。当周期从 $0 . 1 \mu \mathrm { m }$ 增加到 $0 . 3 \mu \mathrm { m }$ 时，三种结构的反射率和透射率均有所降低，但是变化并不是很大。当周期进一步从 $0 . 3 \mu \mathrm { m }$ 增加到 $| 0 . 5 \mu \mathrm { m }$ 时，反射率显著增加，这主要是由于周期变大，有效折射率梯度增加，导致反射加强。但是当周期较小时，在 $0 . 3 \mathrm { - } 1 . 1 ~ \mu \mathrm { m }$ 的透射比较大，导致吸收比较低，降低电池效率。

图3 微结构高度对三种不同宽光谱太阳能电池减反表面光谱特性的影响；(a)-(c)为蛾眼结构的反射率、透射率、吸收率；  
(d)-(e)为金字塔结构的反射率、透射率、吸收率； ${ \bf \Psi } ( \bf g ) - ( \mathrm { i } \epsilon )$ 为圆锥结构的反射率、透射率、吸收率。

Fig.3 The effect of height of $h _ { 1 }$ on the spectral features of the broadband anti-reflection structured surface for the solar cell. (a)-(c) spectralfeatures ofmoth-eye structure,(d)-(f)spectralfeaturesofpyramid structure,(g)-(i) spectralfeaturesofcone structure

# 表2不同微结构高度下三种宽光谱太阳能电池减反表面的平均光谱特性

Table 2 The effect of $h _ { \scriptscriptstyle 1 }$ average spectral features of three broadband anti-reflection structured surface for the solar cell

<html><body><table><tr><td></td><td></td><td colspan="3">R</td><td colspan="3">T</td><td colspan="3">a</td></tr><tr><td></td><td></td><td>蛾眼</td><td>金字塔</td><td>圆锥</td><td>蛾眼</td><td>金字塔</td><td>圆锥</td><td>蛾眼</td><td>金字塔</td><td>圆锥</td></tr><tr><td rowspan="3">0.3-1.1 μm</td><td>h1=0.3μm</td><td>0.077</td><td>0.087</td><td>0.090</td><td>0.166</td><td>0.139</td><td>0.148</td><td>0.757</td><td>0.774</td><td>0.762</td></tr><tr><td>h1=0.6μm</td><td>0.029</td><td>0.032</td><td>0.036</td><td>0.238</td><td>0.248</td><td>0.239</td><td>0. 733</td><td>0.72</td><td>0.725</td></tr><tr><td>h1=0.9μm</td><td>0.021</td><td>0.022</td><td>0.022</td><td>0.239</td><td>0.261</td><td>0.251</td><td>0.740</td><td>0. 717</td><td>0.727</td></tr><tr><td rowspan="3">1.1-2.5 μm</td><td>h1=0.3μm</td><td>0.182</td><td>0.224</td><td>0.225</td><td>0. 781</td><td>0.741</td><td>0.740</td><td>0.037</td><td>0.035</td><td>0.035</td></tr><tr><td>h1=0.6μm</td><td>0.167</td><td>0.168</td><td>0.172</td><td>0.794</td><td>0.794</td><td>0.790</td><td>0.039</td><td>0.038</td><td>0.038</td></tr><tr><td>h1=0.9μm</td><td>0.162</td><td>0.163</td><td>0.168</td><td>0.796</td><td>0.797</td><td>0.793</td><td>0.042</td><td>0.04</td><td>0.039</td></tr></table></body></html>

图4 结构周期对三种不同宽光谱太阳能电池减反表面光谱特性的影响；(a)-(c)为蛾眼结构的反射率、透射率、吸收率； (d)-(e)为金字塔结构的反射率、透射率、吸收率； $( \mathrm { g } ) \mathrm { - ( i ) }$ 为圆锥结构的反射率、透射率、吸收率。 Fig.4Theeffctofperdonthespectralfaturesofthebroadbandanti-efltionstructuredsurfaceforthesarcell.(a)-(c)spectral features of moth-eye structure,(d)-(f) spectral featuresofpyramid structure,(g)-(i) spectral features ofcone structure

# 3结论

本文研究了三种不同结构的单晶硅太阳能电池表面在 $0 . 3 \mathrm { - } 1 . 1 \mu \mathrm { m }$ 和 $1 . 1 \mathrm { - } 2 . 5 \mu \mathrm { m }$ 内的光谱特性，研究发现，由于三种结构表面均具有渐变折射率的特性，因此，反射率得到有效的抑制，蛾眼结构的单晶硅太阳能电池由于有效折射率变化比较平缓，因此在整个太阳辐射光谱范围内具有最低的反射率，随着微结构高度的增加和周期的减小，有效折射率的梯度降低，减反效果更加明显，在 $1 . 1 { - } 2 . 5 ~ \mu \mathrm { m }$ 波段内的透射率得到增强。

# 参考文献

[1] Bermel P,Luo C,Zeng L，et al. Improvign thin-film crystalline silicon solar cell efficiencies with photonic crystals [J]. Optics Express.2007,15(25):16986-17000.   
[2] Mauk MG.,Andreev VM.GaSb-related materials for TPV cells [J].Semiconductor Science and Technology.2oo3,18(5): S191.   
[3] Duan H L,Xuan Y M.Enhanced optical absorption of the plasmonic nanoshell suspension based on the solar photocatalytic hydrogen production system [J].Applied Energy，2014,114: 22-29.   
[4] 杨德仁．太阳电池材料.北京：化学工业出版社,2007. [4] YANG Deren. Solar cell materials [M].Beijing: Chemical Industry Press,2007   
[5]Pillai S,Catchpole K R,Trupke T,et al.Surface plasmon enhanced silicon solar cells [J].Journal of Applied Physics.2007, 101: 093105.   
[6] Tsakalakos L,Balch J,Fronheiser J,et al. Silicon nanowire solar cells [J].Applied.Physics Lettrt,2007,91: 233117.   
[7]Jang SJ, Song YM,Park CI, etal.Antireflective property of thin a-Si solar cell structures with graded refractive index structure [J]. Optics Express,2011,19(S2):A108-A117.   
[8] Song Y M,Jang S J,Yu J S,et al. Bioinspired parabola subwavelength structures for improved broadband antireflection [J]. Small 2010,6(9), 984-987.   
[9] Palik E D.Handbook of optical constants of solids [M].New York:Academic PressInc,1985,350-357.