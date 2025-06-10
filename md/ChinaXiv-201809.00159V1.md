# 带逆耗散势的修正牛顿动力学方程

解释暗物质和暗能量的一种可能模型

胡锦文\*武汉大学物理系，湖北省武汉市武昌区，430072摘要：本文在牛顿动力学方程中引入了逆耗散势，并研究孤立引力系统中物体的运动方程，发现在大尺度下它可以推导出与 $\Lambda C D M$ 模型相似的宇宙膨胀动力学方程，以及推导出盘状星系的渐近平坦的旋转速度性质，与通常暗物质模型不同的是，这种渐近平坦的旋转速度性质是时间积累的结果，而不是力学直接作用的结果，以及讨论了Tully-Fisher关系，发现MOND 模型中的自然常数 $a _ { 0 }$ 以及函数 $\mu$ 的形式在本文的模型中有着明确对应的物理意义。

关键词：暗物质；暗能量；牛顿动力学方程；逆耗散势；MOND

# 1.引言

暗物质与暗能量是当今宇宙学中两大疑难[1-4]，这两种“看不见”的物质表现出了两种截然不同的效应，即暗物质产生引力，而暗能量产生反引力。为了能解释这两种现象，提出了各种各样的理论模型，这些理论模型以广义相对论为基础，主要包括为两方面，一是修改Einstein场方程的左边，即修改时空几何本身，这些理论有 $f ( R )$ 引力理论[5-6]、膜世界引力理论[7]、MOND[8-9]等。二是修改Einstein 场方程的右边，即在时空中加入场或物质，这类理论有∧CDM[10]、Quintessence[11]、phantom[12-13]等。但是目前各种理论仍然没有完美的解决所有问题。尤其是，关于暗物质粒子的寻找实验和暗能量的测量实验仍然一无所获[14-15]，这促使我们想到，也许修改引力方程是一个可以尝试的选择，一些学者也在这方面作了很多工作[16-21]。

在众多替代暗物质的模型中，由M.Milgrom 所提出MOND 模型属于较广泛讨论的一个。该模型提出了一个经验公式，其中引入了一个基本的自然常数 $a _ { 0 }$ ，能很好的解释星系尺度的一些观测现象[22-28]，比如解释Tully-Fisher关系等[24-25]。然而该模型仍然在解释其它观测数据和理论自身上存在一些问题，例如它不能解释星系团中的质量偏差[29]，以及违反了动量守恒这一基本的守恒定律[30]。总之，MOND理论自提出时并不完善，因而Bekenstein等人提出了相对论性的 MOND 理论，即 Tensor-Vector-Scalar Theory（TeVeS）[20,26]，T.G. Zlosnik等人提出了Einstein-Aether理论[31]，以及M.Milgrom后续又提出了BimetricMOND Theory[32-33]，这些扩展理论极大的丰富了MOND 的内容，但是也存在其他问题[34-35]。

然而MOND及其扩展理论仍然取得了部分成功，这似乎暗示着它源于一个更基本的理论体系。本文试图在非相对论牛顿动力学的基础上，采用修正惯性的理论方法[36]，即在牛顿动力学方程中引入耗散势，来讨论它在大尺度下对物体运动的影响，并试图揭示MOND理论中自然常数 $a _ { 0 }$ 的一些深层次根源。

# 2.带耗散势能的牛顿动力学方程

在非相对论情况下，牛顿动力学方程为：

$$
F = m \pmb { a }
$$

其中 $m$ 为物体的质量， $\textbf { \em a }$ 为运动加速度。

按照 MOND的思想，修改MOND 理论通常有两种途径：第一种是试图修改方程的右边，即建立修正的惯性理论，第二种是修改方程的左边，建立修正的引力理论。在相对论情况下，惯性理论和引力理论是同等的。本文考虑在非相对论情况下采用修正的惯性理论，将式(1)修改为如下方程：

$$
\pmb { F } = m ( \pmb { a } - \lambda \pmb { \nu } )
$$

其中λ为常数， $\mid \nu \mid$ 为物体运动速度。

对于一个只有两个物体组成的孤立引力系统 $\Sigma$ ，其中质量为 $\mathbf { \nabla } _ { m }$ 的物体在质量为 $M$ 的准静止物体的引力场中作赤道平面上的运动 $( M > > m )$ ，则根据式(2),系统 $\Sigma$ 的拉格朗日方程为：

$$
{ \cal L } = E - U = { \frac { 1 } { 2 } } m [ ( { \dot { r } } ) ^ { 2 } + ( r { \dot { \theta } } ) ^ { 2 } ] + { \frac { G M m } { r } }
$$

其中 $( r , \theta )$ 为赤道平面圆坐标系。

在式(2)中引入了与速度相关的耗散函数，其对应的耗散势为：

$$
\Psi = - \frac { 1 } { 2 } m \lambda [ ( \dot { r } ) ^ { 2 } + ( r \dot { \theta } ) ^ { 2 } ]
$$

根据耗散系统的哈密顿原理，可得质量为 $m$ 的物体运动方程为：

$$
{ \begin{array} { r l } & { \left\{ { \frac { d } { d t } } ( r ^ { 2 } \ { \dot { \theta } } ) = \lambda r ^ { 2 } \ { \dot { \theta } } \right. } \\ & { \left. { \frac { } { r - r { \dot { \theta } } } } ^ { 2 } + { \frac { G M } { r ^ { 2 } } } = \lambda { \dot { r } } \right. } \end{array} }
$$

考虑当质量为 $m$ 的物体沿着坐标系的径向运动时，即 $\scriptstyle \theta = 0$ ，则由式(5)的第二式可得：

$$
\stackrel { \bullet } { r } = - { \frac { G M } { r ^ { 2 } } } + \lambda \stackrel { \bullet } { r }
$$

我们知道可以由牛顿力学给出宇宙学方程[37]。若取物理坐标 $r = a ( t ) R$ （ $R$ 为宇宙膨胀的随动坐标， $a ( t )$ 为宇宙膨胀因子），并取 $\rho = \rho _ { \mathrm { 0 } } a ^ { - 3 }$ ，以及$M = 4 \pi / 3 \rho r ^ { 3 }$ 为半径为 $r$ 的球体内物质的质量。则根据式(6)可得：

$$
\stackrel { \bullet } { a } = - \frac { 4 \pi G \rho _ { 0 } } { 3 a ^ { 2 } } + \lambda \stackrel { \bullet } { a }
$$

根据哈勃定律 $H = a / a$ ，则式(7)可化为

$$
\stackrel { \bullet } { a } = - \frac { 4 \pi G \rho _ { 0 } } { 3 a ^ { 2 } } + \lambda H a
$$

对比ΛCDM模型中场方程的时-时分量[10]，可得

$$
\frac { \Lambda } { 3 } \sim \lambda H
$$

式(9)反映出，带逆耗散势的牛顿动力学方程在大尺度上可以给出与膨胀宇宙学ACDM模型中相似的动力学方程。

现在考虑质量为 $m$ 的物体在初始条件下 $( t = 0 )$ 在质量为 $M$ 的准静止物体的

引力场中作圆周运动，即 $r _ { 0 } = 0$ ， $G M / r _ { 0 } ^ { 2 } = \dot { \theta _ { 0 } } ^ { 2 } r _ { 0 }$ 。在耗散系统中， $\boldsymbol { r }$ 、 $\theta$ 会随着时间而变化，设 $r = r _ { 0 } f ( t ) , \dot { \theta } = \dot { \theta _ { \scriptscriptstyle 0 } } g ( t )$ ，则式(5)中第二式可化为：

$$
\stackrel { \bullet } { r } - f g ^ { 2 } r _ { 0 } \stackrel { \bullet } { \theta _ { 0 } } ^ { 2 } + \frac { 1 } { f ^ { 2 } } \frac { G M } { r _ { 0 } ^ { 2 } } = \lambda \stackrel { \bullet } { r }
$$

$$
\overleftrightarrow { r } + { \frac { G M } { r _ { 0 } ^ { 2 } } } ( { \frac { 1 } { f ^ { 2 } } } - f g ^ { 2 } ) = \lambda \overleftarrow { r }
$$

考虑在初始条件下 $( t = 0 )$ ，引力场很弱时，即

$$
{ \frac { G M } { r _ { 0 } ^ { 2 } } } \sim 0
$$

将式(12)代入式(11)中，则有

$$
\begin{array} { l } { \displaystyle { \ddot { r } } \approx \dot { \lambda _ { r } } \dot { r } } \end{array}
$$

解方程(13)可得

$$
r = r _ { 0 } e ^ { \lambda t }
$$

根据式(5)中的第一式，则有：

$$
r ^ { 2 } \stackrel { \bullet } { \theta } = r _ { 0 } ^ { 2 } \stackrel { \bullet } { \theta _ { 0 } } e ^ { \lambda t }
$$

根据式(14)和式(15)，可得：

$$
V = V _ { 0 }
$$

其中 $V = { \dot { \theta } } r$ 为旋转线速度， $V _ { _ 0 } = \dot { \theta _ { 0 } } r _ { 0 }$ 为初始时旋转线速度。

由式(14)和式(16)可知，随着时间的推移，半径 $r$ 呈指数增大，然而质量为 $m$ 的物体旋转线速度却保持不变。这恰好和通常一些盘状星系所呈现的渐近平坦的旋转速度性质相一致[38-39]。

# 3.MOND模型

我们知道，在M.Milgrom 所提出的 MOND 理论中引入了一个自然常数 $a _ { 0 }$ ，它将牛顿力学中的实际加速度与牛顿加速度修改为如下关系[8-9]:

$$
a _ { \scriptscriptstyle N } = a \mu ( a / a _ { 0 } )
$$

其中当 $a / a _ { 0 } > > 1$ 时， $\mu ( a / a _ { 0 } ) \sim 1$ ，当 $a / a _ { 0 } < < 1$ 时， $\mu ( a / a _ { 0 } ) { \sim } a / a _ { 0 }$ 。

而从式(12)可知，当初始条件的引力场很弱时，随着时间的推移，质量为 $m$ 的物体运动线速度基本保持不变，而距离 $r$ 却可以仍然不断增大。设该弱引力场对应的强度为 $g _ { \mathrm { 0 } }$ ，则有：

$$
g _ { 0 } = { \frac { G M } { r _ { 0 } ^ { 2 } } }
$$

将式(18)代入式(16)中，则可得：

$$
V ^ { 4 } = V _ { 0 } ^ { 4 } = G M g _ { 0 }
$$

由式(19)可以给出：

$$
\lg ( L ) = 4 \lg ( V ) - \lg ( G g _ { 0 } < M / L > )
$$

其中 $M / L$ 为质光比。

式(20)正是 Tully-Fisher关系。对比式(19)和 MOND 理论，可以发现 $g _ { 0 } = a _ { 0 }$ 。

并且由式(14)可得物体运动的实际加速度为：

$$
a = { \frac { V ^ { 2 } } { r } } = { \frac { V _ { 0 } ^ { 2 } } { r _ { 0 } e ^ { \lambda t } } } = { \frac { g _ { 0 } } { e ^ { \lambda t } } } = { \frac { a _ { 0 } } { e ^ { \lambda t } } }
$$

而牛顿加速度为：

$$
a _ { _ { N } } = { \frac { G M } { r ^ { ^ 2 } } } = { \frac { G M } { r _ { _ 0 } ^ { 2 } e ^ { 2 \lambda t } } } = { \frac { g _ { _ 0 } } { e ^ { 2 \lambda t } } } = { \frac { a _ { _ 0 } } { e ^ { 2 \lambda t } } }
$$

则由式(21)和式(22)可得

$$
\frac { a _ { N } } { a } = \frac { 1 } { e ^ { \lambda t } } = \frac { a } { a _ { 0 } }
$$

对比式(17)和式(23)可见，本文的模型能够推导出 MOND 理论中引入的经验函数 $\mu$ 的形式。

# 4.结论

本文尝试在牛顿动力学方程中引入逆耗散势，并研究一个孤立的引力系统，发现该修正后的动力学方程可以同时给出与ACDM模型相似的宇宙膨胀动力学方程和盘状星系的近似平坦旋转速度性质，而这通常被认为是暗能量和暗物质，这说明，引入了逆耗散势后暗能量效应和暗物质效应是一个物理本质的两方面。

与通常暗物质模型不同的是，引入逆耗散势后盘状星系所呈现的渐近平坦的旋转速度性质是长久时间积累后形成的结果，而不是直接的力学作用结果。以及在其导出的宇宙膨胀动力学方程中，呈现的是一个等效的时变宇宙学常数，而这与Quintessence 模型和 phantom 模型相一致。

最后，与MOND模型一样，该修正后的牛顿动力学方程同样推导出了Tully-Fisher关系，并可以看到MOND模型中引入的自然常数 $a _ { 0 }$ 以及函数 $\mu$ 的形式在本文的模型中有一个明确对应的物理意义。但是，本文的讨论仍然不是一个相对论性的修正牛顿引力方程，这还需后续的进一步扩展研究。

# 参考文献

Universe and a Cosmologiacal Constant, Astron. J., 116,1009-1038 (1998).   
[2]P.A. R. Ade, et al., Planck 2013 results. XXI. All-sky Compton parameter power spectrum and high-order statistics, Astronomy and Astrophysics, 571, A16 (2013). [3]E. Komatsu et al, Seven-Year Wilkinson Microwave Anisotropy Probe (WMAP) Observations: Cosmological Interpretation, Astrophys. J. Suppl., 192,18 (2011). [4]Nolta M. R.，Dunkley J.， Hill R. S.，et al.， Five-year wilkinson microwave anisotropy probe (wmap) observations: angular power spectra, Astrophys. J. Suppl., 180,296 (2009).   
[5]Nojiri S,Odintsov S D， Introduction to Modified Gravity and Gravitational Alternative for Dark Energy, Int. J. Geom. Meth. Mod. Phys., 4,115 (2007).   
[6]Carroll S M, Duwuri V, Trodden M, et al.， Is cosmic speed-up due to new gravitational Physics? Phys. Rev. D, 70, 043528 (2004).   
[7] Roy Maartens, Brane-world gravity, Living Rev. Rel., 7,7 (2004).   
[8]Milgrom M.,A modification of the newtonian dynamics as a possible alternative to the hidden mass hypothesis,Astrophys.J., 270, 365 (1983).   
[9]M. Milgrom, A modification of the Newtonian dynamics: implications for galaxy systems,Astrophys. J., 270,371 (1983).   
[10]P. J. E. Peebles,B. Rhatra, The Cosmological Constant and Dark Energy, Rev. Mod. Phys., 75,559 (2003).   
[11]J.A. Frieman，C. T. Hill，A. Stebbins，et al.，Cosmology with Ultra-light Pseudo-Nambu-Goldstone Bosons,Phys. Rev. Lett.,75,2077 (1995).   
[12]P. Singh, M. Sami, N. Dadhich, Cosmological Dynamics of phantom Field, Phys. Rev. D, 68, 023522 (2003).   
[13] R.R. Caldwell， M. Kamionkowski，N. N. Weinberg,Phantom Energy and Cosmic Doomsday, Phys. Rev.Lett., 91, 071301 (2003).   
[14]Gianfranco Bertone, Particle Dark Matter, Cambridge University press (2010). [15]T.M. Davis, E. Mortsell, J. Sollerman, et al, Scrutinizing Exotic Cosmological Models Using Essence Supernova Data Combined with Other Cosmological Probes, Astrophys. J., 666,716 (2007).   
[16]Capozziello S， Francaviglia M， Extended theories of gravity and their cosmological and astrophysical applications, Gen. Relativ. Gravit., 40(2), 357 (2008). [17]De Felice A, Tsujikawa S, $f ( R )$ Theories, Living Rev. Relat., 13,3 (2010). [18]Ferraro R,Fiorini F, Modified teleparallel gravity: Inflation without an inflaton, Phys. Rev. D, 75, 084031 (2007).   
[19]Bengochea G R, Ferraro R, Dark torsion as the cosmic speed-up, Phys. Rev. D, 79,124019 (2009).   
[20]Bekenstein J. D., Relativistic gravitation theory for the MOND paradigm, Phys. Rev. D, 70, 083509 (2004).   
[21]T. G. Zlosnik, P. G. Ferreira, G. D. Starkman, Modifying gravity with the Aether: An alternative to Dark Matter, Phys.Rev. D, 75,044017 (2007).   
[22]M. Milgrom, Sanders R. H., MOND predictions of halo phenomenology in disc galaxies, Mon. Not. R. Astron. Soc., 357,45 (2005).   
[23]M. Milgrom， Sanders R. H.， MOND rotation curves of very low mass spiral galaxies, Astrophys. J., 658,L17 (2007).   
[24]McGaugh S. S., Schombert J. M., Bothun G. D., et al., The baryonic tully-fisher relation, Astrophys. J., 533, L99 (2000).   
[25]McGaugh S. S.， The baryonic tully-fisher relation of galaxies with extended rotation curves and the stellar mass of rotating galaxies,Astrophys. J.，632,859 (2005).   
[26]Skordis C.， The tensor-vector-scalar theory and its cosmology， Class. Quant. Grav., 26, 143001 (2009).   
[27]Cardone V.，Angus G.， Diaferio A.，et al.， The modified newtonian dynamics fundamental plane, MNRAS, 412,2617 (2011).   
[28]Famaey B. McGaugh S., Modified newtonian dynamics(MOND): Observational phenomenology and relativistic extensions,Living Reviews in Relativity，15,10 (2012).   
[29]G.Gentile，B. Famaey，W. J.G.de Blok，THINGS about MOND, arXiv: 1011.4148(2010).   
[30]J.Bekenstein，A Primer to Relativistic MOND theory, Contemporary Physics, 47,387 (2006).   
[31]T. G. Zlosnik, P.G. Ferreira, G. D. Starkman, Modifying gravity with the Aether: An alternative to Dark Matter, Phys. Rev.D, 75,044017 (2007).   
[32]M. Milgrom, Bimetric MOND gravity, Phys. Rev. D, 80, 123536 (2009).   
[33]M. Milgrom, Cosmological fluctuation growth in bimetric MOND, Phys. Rev. D, 82, 043523 (2010).   
[34]J. P. Bruneton, S. Liberati, L. Sindoni, et al., Reconciling MOND and dark matter? JCAP, 03, 021 (2009).   
[35]J. M. Romero, et al., Electrodynamics a la Horava, Mod. Phys. Lett. A, 25(29), 2501 (2010).   
[36]M. Milgrom, Dynamics with a non-standard inertia-acceleration relation: an alternative to dark matter, Ann. Phys., 229, 384 (1994).   
[37]Malcolm S.Longair, Galaxy Formation, Springer press, 2008.   
[38]Bertone G, Hooper D， Silk J.,， Particle dark matter: evidence， candidates and constraints,Phys. Rep., 405,279 (2005).   
[39]Begeman, K. G., Broeils,A. H., Sanders, R. H., Extended rotation curves of spiral galaxies: Dark haloes and modified dynamics. Monthly Notices of the Royal Astronomical Society, 249, 523 (1991).

# Modified Newtonian Dynamics with Inverse Dissipation Potential as an Alternative to Dark Matter and Dark Energy

Jinwen HU Department of Physics，Wuhan university，Wuhan， Hubei 430072，China

# Abstract:

In this paper， the inverse dissipation dispersity is introduced in the Newtonian Dynamics equation, and the equation of motion of the object in the isolated gravitational system is studied. It is found that at large scale it can derive the cosmic expansion dynamics equation similar to the ACDM model and derive the asymptotic flat rotational velocity property of spiral galaxies,which it is unlike the usual dark matter model that the asymptotic flat rotational velocity property is the result of time accumulation rather than the direct effect of mechanics,and the Tully-Fisher relationship is discussed and it is found the natural constants in the MOND model that $a _ { 0 }$ and the form of the $\mu$ function have a clear corresponding physical meaning in the model of this paper.

# Keywords:

Dark matter; dark energy; Newtonian dynamic equation; inverse dissipation potential; MOND