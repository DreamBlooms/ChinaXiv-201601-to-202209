# 碳纤维结构对其辐射光谱性质的影响研究

杨柳谢鸣艾青（哈尔滨工业大学能源科学与工程学院，哈尔滨，150001)

摘要：为了研究碳纤维类高温防隔热复合材料中热辐射传输特性及对其传热性能的影响，采用数值模拟的方法，针对2维(2-D)，2.5维(2.5-D)编织的碳纤维复合材料的光谱辐射特性进行了研究。通过对比时域有限差分法（FDTD）和Mie 氏理论计算的微米级尺度下单根无限长圆柱的散射强度分布，验证FDTD计算碳纤维热辐射特性可靠性的基础上。采用FDTD 分析了编织方式、纤维特征尺寸、纵向层数、纤维间隔及基质折射率对其辐射性质的影响。研究发现，均质块材与实际编织结构的块材光谱辐射特性差异明显，散射强度分布差异可达2个量级。

关键词：碳纤维；时域有限差分；辐射光谱特性中图分类号：TK124 文献标识码：A

# The Research of Structural Influences on Carbon Fibrous Composite Material Radiative Spectral Properties

YANG Liu XIE Ming AI Qing

(School of Energy Science and Engineering,Harbin Institute of Technology，Harbin 150001， China)

Abstract: In this work,aim to study carbon fibrous composite insulation materials’radiative spectral properties and the influences on heat transfer, using numerical simulation to calculate 2-dimension(2-D) and 2.5-dimension(2.5-D) micro-structural influences on carbon fibrous composite material spectral attenuation properties. The reliability of the result obtained from FDTD is proven by comparing the results of the scattering intensity distribution of the single carbon fiber with the Mie Theory approximation. Based on FDTD,this paper analyzes the influence of diameters,longitudinal structural layers,interval in horizontal and vertical as wellas the back ground refractive index on the spectral atenuation properties of carbon fiber braided structure both in 2-Dimension (2-D） and 2.5-Dimension (2.5-D). We also discuss scattered diferences in stagger and aligned arrangements respectively. Finally ,it can be shown that different structures have their special radiative spectral properties,meanwhile, it is not accurate to regard the carbon fiber braided structure as the equivoluminal block,the maximum value of the different scattred intensity may up to two orders of magnitude.

Key words: carbon fiber; Finite Difference Time Domain; radiative spectral properties

# 0引言

碳纤维复合材料一种性能优异的隔热材料，常用于高温热防护。通常碳纤维材料由微米级的碳纤维编织而成，难以基于几何光学进行研究。目前，学者们通过使用米氏理论，变换波动方程形式等方法求解结构简单的无限长圆柱的散射性质[1-4]，对无限长圆柱的研究也更加细化，对放置在吸收性介质中的单根圆柱的散射性质进行研究[5，并提出了对光线入射单根多层介质的通用计算方法[7,8]。多根圆柱光谱性质的研究受到了越来越多的关注，圆柱的位置以及排列的形状都会影响入射光谱的散射方向与能量，LeeSiuchun等人对平行放置的圆柱提出了求解随机放置在吸收介质中的圆柱散射性质的方法[9-13]。但上述研究主要针对2维结构，而且没有考虑实际材料编织等结构形式的影响。本文通过使用时域有限差分法，直接对麦克斯韦方程进行离散与求解，研究了不同碳纤维编织结构的辐射光谱性质，分析了结构对复合材料热辐射传输的影响，为高温下复合材料设计提供了参考。

# 1数理模型

# 1.1物理模型

![](images/b5a992aaa37c4dff246d4bfe7e087a61aa561f21a8253f9324be0700928ff513.jpg)  
图12维碳纤维计算模型Fig.1 2-D carbon fibrous computational model

图1为2维尺度下碳纤维的物理计算模型，其中，圆形区域为碳纤维， $M$ 表示水平层数， $N$ 表示纵向层数。 $L$ 表示纤维间隔。光源为平面波，从左侧垂直入射。

# 1.2 基本方程

针对碳纤维粒子的辐射特性问题，本节介绍了时域有限差分的基本方法，选用了FDTD计算当中的PML 边界层作为几何边界的处理方法[14]。

麦克斯韦方程是一组用来表征和描述自然界宏观电磁现象的方程，其中微分形式基本可以表征大部分电磁学基本原理，形式如下：

$$
\nabla \cdot D = \rho
$$

$$
\nabla \cdot B = 0
$$

$$
\nabla \times \boldsymbol { E } = - \frac { \partial \boldsymbol { B } } { \partial t }
$$

$$
\nabla \times H = J + { \frac { \partial D } { \partial t } }
$$

在研究材料光谱特性时，散射因子与散射分布强度分布可以很好地表征它的光谱特性，本文选用这两个参数作为参量，研究不同情况下二者的变化规律，由FDTD算法可计算出节点处的入射，散射的波印廷矢量：

$$
\vec { S } _ { \mathrm { i n c } } = \mathrm { R e } ( \vec { E } _ { \mathrm { i n c } } ) \times \mathrm { R e } ( \vec { H } _ { \mathrm { i n c } } )
$$

$$
\vec { S } _ { \mathrm { s c a t } } = \mathrm { R e } ( \vec { E } _ { \mathrm { s c a t } } ) \times \mathrm { R e } ( \vec { H } _ { \mathrm { s c a t } } )
$$

由波印廷矢量辐射强度的关系，在一个周期 $T$ 中，节点处的平均辐射强度：

$$
I = \left| \frac { 1 } { T } \int _ { 0 } ^ { T } \vec { S } ( t ) d t \right|
$$

设定光源垂直于圆柱轴向入射，当基质介质为非吸收性材料时，投射到圆柱上的辐射强度不变，所以能量为：

$$
W _ { \mathrm { i n c } } = I _ { \mathrm { i n c } } \cdot A _ { 0 }
$$

$\scriptstyle A _ { 0 }$ 为圆柱的投影面积，散射能量为：

$$
W _ { \mathrm { s c a t } } = L \cdot \oint _ { C } I _ { \mathrm { s c a t } } ^ { c } d c
$$

$C$ 为结构区域的边长， $L$ 材料长度，上标 $\mathbf { \Psi } _ { c }$ 表示当前节点处的散射强度。散射因子的计算式为：

$$
\ Q _ { \mathrm { s c a t } } = { \frac { W _ { \mathrm { s c a t } } } { W _ { \mathrm { i n c } } } }
$$

# 1.3FDTD中完全匹配吸收边界（PML）条件

在计算域的边界设置完全匹配吸收边界来截断计算。事实上，PML是一个有厚度的介质层，介质层的波阻抗和模拟区域波阻抗完全匹配，即：

$$
\frac { \sigma _ { x } } { \varepsilon } = \frac { \sigma _ { m x } } { \mu }
$$

$$
\frac { \sigma _ { y } } { \varepsilon } = \frac { \sigma _ { m y } } { \mu }
$$

下标 $x , \ y$ ， $m x$ ，my分别表示二维坐标下不同方向的电导率和导磁率，则PML中的电场分量可表示速为：

$$
\begin{array} { r l } & { E = E _ { 0 } \exp \Biggl [ \mathrm { j } \omega \Biggl ( t - \frac { x \cos \varphi + y \sin \varphi } { c _ { 0 } G } \Biggr ) \Biggr ] . } \\ & { \quad \quad \quad \exp \Biggl ( - \frac { \sigma _ { _ x } \cos \varphi } { \varepsilon _ { _ 0 } c _ { 0 } G } x \Biggr ) \exp \Biggl ( - \frac { \sigma _ { _ y } \sin \varphi } { \varepsilon _ { _ 0 } c _ { 0 } G } y \Biggr ) } \end{array}
$$

其中，G可参阅文献[14], $c _ { 0 }$ 是光在真空中的传播速度，$\varphi$ 是入射方向和交界面的夹角，PML边界层不影响入射电磁波的吸收效果。在处理纤维边界时，为防止产生阶梯近似，使用了共形网格技术[15]。

# 2编织碳纤维辐射特性分析

为了验证本文采用FDTD法的可靠性，针对无限长圆柱体，对比了FDTD法与Mie理论的计算结果，如图2所示，结果显示二者吻合良好。

![](images/eb8504f69ff7f87d5544e421b58b5240b862f1e119be15352c329650a07a3416.jpg)  
图2Mie理论与FDTD计算的散射强度分布对比 Fig.2 Comparison of the scattered intensity distribution between Mie approximation theory and FDTD method

采用FDTD 法，针对复合材料2-D和2.5-D两种常见编织方式进行数值模拟，通过计算不同条件下材料的散射因子等参数来对比研究其各自的热辐射性能。

为了控制计算变量，假设碳纤维材料的电磁性质均匀且各项同性,查阅相关数据[1],得到波长在 $2 . 5 \mu \mathrm { m }$ 至 $1 0 \mu \mathrm { m }$ 时膨胀石墨的复折射率，并把它当做碳纤维的电磁参数使用。

# 2.12-D编织碳纤维辐射特性研究

选用波段在 $2 . 5 \mu \mathrm { m }$ 至 $1 0 \mu \mathrm { m }$ 的平行光作为光源，计算模型如图1，设碳纤维的截面半径为 $1 \mu \mathrm { m }$ ，且规定碳纤维圆柱的水平间隔 $( L _ { I } )$ ）和纵向间隔 $( L _ { 2 }$ ）在同一个计算模型中为定值。如果没有做特殊说明，则取间隔为 $0 \mu \mathrm { m }$ ，基质折射率为1，结构的体积尺寸为$2 4 \times 2 4 ~ \mu \mathrm { m } ^ { 2 }$ 。

![](images/c6fb8b6fa84570581eb52f66f6e39797670964e820e62bc139c8457625312ef3.jpg)  
图32-D不同横向间隔散射因子随波长的变化规律 Fig.32-D structure scattering factors of different horizontal intervals

图3表示横向粒子间隔 $L _ { I }$ 对2-D编织结构散射因子的影响，四条曲线的变化趋势基本一致，全部随着入射波长的增加，散射因子逐渐减小，下降速度逐渐减缓；相同波长下，间隔越大时，散射因子越小。纵向粒子间隔 $L _ { 2 }$ 对2-D编织结构散射因子的影响关系与横向间隔相似，散射的变化趋势也基本一致。不同的是纵向间隔在 $5 . 5 \mu \mathrm { m }$ 之后的波段内，曲线出现了交叉，表示在这个波段范围内，粒子间距已经不是影响散射因子的主要因素。

![](images/a73856dbcd0711f426098a1e267bf147d7f8b92348ea99ac28482c3a7e316373.jpg)  
图42-D不同纵向间隔散射因子随波长的变化规律 Fig.42-D structure scattering factors of different longitudinal intervals

基质折射率对2-D编织结构散射因子的影响关系在图5中给出，从图中可以得到，4条曲线全部随着入射波长的增加，散射因子逐渐减小。其中， $n _ { b } { = } 1 . 1$ 对应的散射因子变化区间最小， $n _ { b } { = } 1 . 3$ 对应的散射因子变化最大；另外，随着基质折射率的增大，散射因子先减小后增大。基质折射率对2-D编织结构散射因子的影响作用很大，特别是在高基质折射率中。

![](images/72fa92aa3aa234ae0b6adf07ca150e44c32186acfc7bae2dfbdcf4e66037d512.jpg)  
图52-D不同基质折射率散射因子随波长的变化规律 Fig.52-D structure scattering factors ofdifferent back ground refractive indexes

在原有结构尺寸下，通过加大它的纵向宽度来增加碳纤维层数。分别计算了 $N { = } 6$ 、8、10、12层碳纤维的散射性质，发现除了 $N { = } 1 2$ 对应曲线在短波段范围内会出现短暂增大。从整体来看，随着纵向层数的增加，散射因子逐渐变大。碳纤维半径对2D编织结构散射因子的影响关系可由变换的波长体现，本质上来说，在用电磁学的方法计算材料的辐射特性时，需要考虑的变量是纤维的特征长度[11]，由纤维的半径和入射波长共同决定，所以，改变入射波长的范围，可以同样当做是改变碳纤维半径的模拟计算。

# 2.22-D碳纤维错排排列方式对散射特性的影响

不同碳纤维排列方式也会改变材料的散射性质，本文建立了错排的计算模型。模型中纤维的纵向层数为三层，第一层与第三层纤维7根，中间层为6根，所有纤维均匀分布。碳纤维的截面半径设为 $3 . 5 \mu \mathrm { m }$ 纵向间隔为固定 $7 \mu \mathrm { m }$ ，横向间隔 $b$ 作为变量。

![](images/4f07c6c3b11bfae6548143f8fd8056fe877a742693e0574eba62297816457c4f.jpg)  
图6错排不同横向间隔散射因子随波长的变化规律 Fig.62-D structure scattering factors of different horizontal intervals in stagger arrangement

可以看出，不论是错排还是顺排，间隔的大小是否变化，散射因子都会随着波长的增大而减小，但一般情况下，相同的间隔和波长下，顺排的散射因子数值要大于插排，当将横向间隔继续增大至 $1 1 \mu \mathrm { m }$ 以上时，散射因子曲线几乎重合，可以认为此时间隔影响很小，排列结构方式成为主要影响因素。

# 2.32.5-D编织碳纤维辐射特性研究

告

2.5-D编织结构是一种常见的纤维结构，模型如图

7所示，2.5-D编织结构中的碳纤维可以分为纬纱和经纱，经纱缠绕纬纱，处于弯曲状态，但经纱的横截面依然看做圆形，纬纱和经纱之间互相紧密排布。边界条件以及光源的设定与2-D结构完全一致。其中，碳纤维半径 $1 \mu \mathrm { m }$ ，横向纬纱间隔 $L _ { I } { = } 2 ~ { \mu \mathrm { m } }$ ，纵向纬纱间隔 $L _ { 2 } { = } 0 \mu \mathrm { m }$ ，基质折射率 $n _ { b } { = } 1 . 0$ 。

与2D编织结构一样，横向纬纱间隔是影响2.5D编织结构孔隙率的因素之一，为了研究横向纬纱间隔对碳纤维红外辐射特性的影响，分别设定了不同横向纬纱间隔四种结构的2.5D编织碳纤维，横向纬纱根数为3，纵向纬纱层数为2。

![](images/63927133ff3e3fa2084bb14b21bf3d6a8bfc50661ed01f71f73b6eece899fa7d.jpg)  
图82.5-D不同横向纬纱间隔散射因子随波长的变化规律 Fig.8 2.5-D structure scattering factors of transverse weft intervals

从图8可以看出，散射因子曲线的变化趋势是随着波长的变化而快速降低，这与2-D模型的结果相似，值得注意的是在2.5-D结构时，散射因子随波长的变化幅度明显下降，所以，可以得出当纤维经过复杂编织后，其本身的辐射光谱特性有了改善，降低了不同波长对材料的影响。

![](images/b03f0201372658d05afb772dff051df854203cc4aae6f91a805500e59e6b5843.jpg)  
图 $8 2 . 5 { \cdot } \mathrm { D }$ 编织结构模型 Fig.72.5-D carbon fibrous computational model   
图92.5-D编织结构和等体积块材的散射强度分布Fig.9Thescattered intensityofbulkand2.5-Dwoven fiber

将实际编织结构的纤维材料与均质块材的散射强度分布进行对比，如图9，在整个散射角范围内，2.5-D结构纤维的散射强度分布与块材明显不同，某个角度上数值差在2个数量级之上，而且经过编织后，各个方向上的辐射强度要比均质块材更加均匀。

# 3结论

本文通过数值模拟分析了两种编织结构（2-D，2.5-D）碳纤维的光谱辐射特性，比较了编织方式、纤维特征尺寸、纵向层数、纤维间隔及基质折射率对其辐射性质的影响。研究发现，纤维顺排时，在固定的几何区域内增加碳纤维个数则会使材料的散射因子升高；基质的折射率与纤维折射率的数值差距越大，散射效应也越强。在相同的间隔和波长下，顺排的散射因子数值要大于错排，但不论是顺排还是错排，随着波长的增大，最后都趋于一个定值。通过比较块材2-D和2.5-D编织结构的散射强度分布，发现通过把多根碳纤维用复杂形式编织起来，能够很好的提升材料的光谱稳定性。

因此，不同的结构的碳纤维材料的辐射辐射光谱性质有其特殊性，在计算时，如果简化做块材处理，散射强度分布之间的差异可能达到2个数量级以上，得到的计算数据并不准确。

# 参考文献

[1] Olaofe G O.Scattering by an Arbitrary Configuration of Parallel Circular Cylinders[J]. Journal of the Optical Society of America,1970,60:1233-1236,.   
[2] Barabls M.Scattering of a Plane Wave by a Radially Stratified Tilted Cylinder[J]. Journal of the Optical Society of AmericaA,1987,4(12): 2240-2248   
[3] Felbacq D, Tayeb G,Maystre D. Scattering by a Random Set ofParallel Cylinders[J].Journal of the Optical Society of America A,1994,11(9): 2526-2538   
[4] Lee Siu Chun.Light Scattering by Closely Spaced Parallel CylindersEmbedded inaFinite Dielectric Slab[J].Journal of the Optical Society ofAmerica A,1999,16(6):1350-1361   
[5] RuppinR.Extinction bya Circular Cylinder in an Absorbing Medium[J], Optics Communications,2002,211: 335-340   
[6]SUN Wenbo,Loeb Norman $\mathrm { \Delta G }$ LIN Bing. Light Scattering by an Infinite Circular Cylinder Immersed in an Absorbing Medium[J].Applied Optics.2005,4(12): 2338-2342   
[7] Lee Siu Chun.Light Scattering by a Coated Infinite Cylinder in an Absorbing Medium[J],Journal of the Optical Society of America A,2011,28(6): 1067-1075   
[8] 姜会芬，韩香娥,李仁先．垂直入射无限长分层住电磁散 射的改进算法及应用[J]，光学学报,2007,27(2):365-371 Jiang Huifen,Han Xiang'e,Li Renxian. Improved Algorithm of Electromagnetic Scattering by a Multilayered Cylinder of Infinite Length for Normal Incidence and Its Application[J], Acta Optica Sinica, 2007,27(2): 365-371   
[9]Lee Siu Chun ，A Quasidependent Scattering Radiative Properties Model for High Density Fiber Composites[J], JournalofHeat Transfer,2010,132:1-8   
[10] Lee Siu Chun ．Scattering by Cosely Spaced Parallel Nonhomogeneous Cylinders in an Absorbing Medium[J], Journal of the Optical Society of America A,2011,28(9): 1182-1819   
[11]Lee Siu Chun,Wave Propagation Through a Dielectric Layer Containing Densely Packed Fibers[J], Journal of Quantitative Spectroscopy & Radiative Transfer, 2011,112: 143-150   
[12]Schafer J,Lee S C,Kienle A.Calculation of the Near Fields for the Scattering of Electromagnetic Waves by Multiple Infinite Cylinders at Perpendicular Incidence[J],Journal of Quantitative Spectroscopy & Radiative Transfer,2012,113, 2113-2123   
[13]Lee Siu Chun.Near Field Scattering by Multiple Infinite Cylinders in an Absorbing Medium at Oblique Incidence[J], Journal of Quantitative Spectroscopy & Radiative Transfer, 2013,114: 65-72   
[14] 葛德彪，闫玉波．电磁波时域有限差分方法[M].第三版. 西安电子科技大学出版社，2011 GEDebiao,Yan Yubo．Finite-Difference Time-Domain Method forElectromagneticWaves[M]. 3rd. Xidian University Publishing House,2011   
[15] 牛朴，侯新宇．任意三维物体FDTD共形网格生成算法[J], 计算机仿真,2009,26(7):236-239 Niu Pu,Hou Xinyu,A Conformal FDTD Grid Generation Algorithm for Arbitrary Three-Dimensional Geometric Object[J],Computer simulation,2009,26(7): 236-239   
[16]豆正伟，李晓霞，赵纪金．光谱法研究膨胀石墨红外波段 复折射率[J].兵工学报,2011,32(4):498-502 Dou Zhengwei, Li Xiaoxia, Zhao Jijin, Complex Refraction Indices of Expanded Graphite Deduced from Its Reflection Spectra in Infrared Band[J],Acta Armamentarii,2011,32(4): 498-502