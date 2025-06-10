# 多焦距微透镜阵列光场成像火焰三维温度场测量

孙俊许传龙张彪刘煜东王式民(能源热转换及其过程测控教育部重点实验室，东南大学，能源与环境学院，南京210096)摘要：多焦距微透镜阵列可提高聚焦光场相机的深度分辨率。为了研究多焦距微透镜阵列对光场成像火焰三维温度场测量的影响，本文在火焰辐射光场成像模型的基础上，分析了单焦距微透镜阵列和多焦距微透镜阵列的火焰辐射光场成像特征，计算了两种不同微透镜阵列下的火焰辐射图像，根据火焰光场图像重建了火焰的三维温度场。开展了多焦距微透镜阵列聚焦光场相机火焰三维温度场重建的实验研究，并对数值计算和实验结果进行了分析。

关键词：聚焦光场相机，多焦距微透镜阵列，辐射传输方程，反演，温度中图分类号： TK311 文献标识码：A

# Three-dimensional Temperature Measurement of the Flame Using the Light Field Camera with a Multiple Focus Microlens Array

SUN Jun XU Chuan-long\* ZHANG Biao LIU Yu-dong WANG Shi-min （KeyLaboratoryofEnergyealConversionandControlofMinistryofEducation,ShoolofEnergyandEnviroment,othast University, Nanjing,210096,PR China)

Abstract:Multiple focus microlens array (MFMA)can improve thedepth resolution ofthe focused light field camera. This paper investigates the efect of MFMAonthe three-dimensional(3-D)temperature measurement of the flame. On the basis of light field imaging model of the flame,the lightfield imaging characters offlame radiation were analyzed forthe MFMA and single focus microlens array (SFMA).For the two diferent types of microlens array(MFMA and SFMA),the light field images ofthe flame were numerically calculated.According to the light field images,the 3-D temperature field of the flame was also reconstructed.Experiments were carried out on the 3-D temperature measurement of the flame using the light field camera with a MFMA.The simulation and experimental results were analyzed in detail.

Key words: focused lightfieldcamera; multiple focus microlens array; radiative transfer equation; inverse;temperature

# 0前言

燃烧火焰广泛存在于工业生产过程，如燃气轮机、电站锅炉和航空发动机等[1,2]。燃烧过程是一个复杂的剧烈的多相反应过程，伴随着连续进行的传热、传质，并生成多种燃烧产物，释放出大量热量。由于温度是表征燃烧情况的重要特征参数，为了提高燃烧效率和燃烧过程的稳定性，控制燃烧产物特别是污染性气体，必须进行有效的燃烧火焰温度场测量。

现有的火焰温度场测量技术主要分为基于激光光谱的测量技术[3-4]和基于火焰图像的测量技术[5-7]。基于激光光谱的测量技术，不仅能测量火焰温度场，还能测量燃烧过程中间组分的分布。例如，Ma等使用高光谱探测器，接收激光穿过火焰后的吸收光谱，再利用层析反演算法重建火焰温度场及吸收性组分的浓度[4]。然而，激光测温技术存在系统复杂，价格昂贵，操作要求高等缺陷，主要用于实验室火焰诊断研究。基于火焰图像的测温方法，不外加激光光源，仅使用传统成像探测器（相机）拍摄火焰自发辐射图像，再结合反演算法重建火焰温度场[5-8],使得测量系统的复杂性降低，更易于安装操作，对于受测量条件等限制而无法适用激光测温技术的工业火焰的温度场测量，具有一定优势。Hossain等使用传统相机拍摄火焰图像，利用层析重建技术，如滤波反投影重建（FBP）算法得到火焰内部各层的截面图像，再根据双色法计算火焰各层的截面温度分布，目前已有应用于工业火焰的监测的实例。Li等同样在传统相机的火焰辐射成像过程基础上，建立关联火焰辐射与图像灰度的辐射传输模型，再通过反演算法，如吉洪诺夫（Tikhonov）正则化法重建火焰温度场，该方法也有用于工业大型火焰(如电站锅炉燃烧火焰）温度场测量的实例。然而，由于传统相机无法分辨火焰辐射的方向，图像测温技术需要使用多台传统相机，才能采集火焰多视角的辐射信息，实现非轴对称火焰三维温度场的重建，这对相机之间的耦合及同步要求较高。

光场相机作为火焰辐射采样装置，在探测面与主镜头之间加装微透镜阵列，相比于传统相机，不仅能够在单次曝光条件下以更高的精确度记录火焰辐射的强度信息，还能分辨火焰辐射的方向，结合反演算法，如基于QR分解的最小二乘（LSQR）算法能够实现单光场相机的火焰三维温度场重建910]，更大程度地降低了测量装置的复杂性。在传统光场相机的基础上，Lumsdaine提出了聚焦光场相机的设计，成像探测器位于微透镜阵列的离焦面上，减少了光线方向维度的采样，用较低的方向分辨率换取更高的空间分辨率，有效提高了重聚焦计算的图像分辨率[II]。在此基础上，Perwass 等使用三焦距微透镜阵列，其中三种不同焦距的微透镜均匀布置，能够将不同深度的空间点重聚焦在同一图像上，进一步提高了光场相机的深度分辨率[10]，然而对于三焦距微透镜阵列聚焦光场相机火焰温度场重建，目前还没有相关研究。

为了研究聚焦光场相机中，三焦距微透镜阵列的采用能否提高基于光场成像的火焰三维温度的测量精确度，本文在火焰图像测温方法的基础上，利用聚焦光场相机作为火焰辐射探测装置，开展基于光场成像技术的火焰三维温度场测量方法研究。分别对单焦距微透镜阵列和三焦距微透镜阵列聚焦光场相机采集的辐射光线的分布进行了分析，研究了两种微透镜阵列对火焰三维温度场重建结果的影响。最后利用三焦距微透镜阵列聚焦光场相机开展了乙烯扩散火焰三维温度场重建实验研究。

# 1火焰辐射光场成像模型

光场相机在成像探测面和主透镜之间安装了微透镜阵列。传统光场相机的探测面位于微透镜阵列的焦平面上，而聚焦光场相机的探测器面偏离微透镜阵列的焦平面，减少了光线方向维度的采样，提高了空间维度的采样，从而克服了传统光场相机方向维度采样冗余的缺陷。本文采用聚焦光场相机作为火焰温度场测量装置，如图1（a）所示。定义相机探测面关于成像系统的物方共轭面为虚拟物面，其中相机探测面与虚拟像面关于微透镜共轭，虚拟像面与虚拟物面关于主透镜共轭。虚拟物面上的点称为虚拟光源点，虚拟像面上的点称为虚拟像点。当微透镜阵列上的微透镜有三种焦距时，则相应地存在多三个虚拟像面和三个虚拟物面，如图1（c)所示。

相机探测面上各像素接收到的火焰辐射，可认为是来自虚拟光源点的一束辐射成像光线。如图1（a）所示，在聚焦光场相机中，以微透镜阵列与探测面的距离小于微透镜的焦距的情况为例，虚拟像面和探测面处于微透镜阵列的同一侧，相同虚拟光源点发出的火焰辐射成像光束，在被主透镜会聚到虚拟像点之前，被微透镜分成若干束，每束光线经过相应微透镜的会聚作用，投射到探测面不同像素上，每个像素对应的光束方向可由像素及其对应的微透镜位置确定，火焰辐射光线的强度和方向同时被记录下来。对于探测面的每个像素，由于其接收到的一束辐射成像光线的孔径角较小[10,13]，基于针孔成像模型，使用通过微透镜光心的主光线表征这束辐射成像光线，主光线的强度和方向为该像素探测的火焰辐射的强度和方向，将主光线称为该像素的采样光线，探测面所有像素的采样光线在空间中的分布方式能够表征光场相机的火焰辐射采样方式，因而可以通过研究单焦距微透镜阵列和三焦距微透镜阵列聚焦光场相机采样光线的分布，来分析比较两种微透镜阵列聚焦光场相机的火焰辐射采样方式。

对于单焦距微透镜阵列聚焦光场相机，微透镜阵列上各微透镜焦距相同，探测面上像素的采样光线的分布如图1（b）所示。对于三焦距微透镜阵列聚焦光场相机，微透镜阵列上各微透镜有三种焦距，三种焦距的微透镜均匀排列，任意两个相同焦距的微透镜互不相邻。同一种焦距的微透镜能够对物空间某一深度的物点聚焦成像，三种焦距的微透镜则有利于空间不同深度的物点同时在探测面上聚焦成像，提高了相机的深度分辨率[12]。三焦距微透镜阵列聚焦光场相机探测面上像素的采样光线分布如图1（c）所示。

图1（b）和（c）中，三种不同焦距的微透镜，分别用红、绿、蓝三种颜色表示。比较两幅图，可以看出，相比于三焦距微透镜阵列，单焦距微透镜阵列虚拟光源点分布更加均匀，采样光线在火焰内部空间的分布也更加均匀，各采样光线独立性较高，而多焦距微透镜阵列的火焰辐射采样光线在火焰内部空间的分布不均匀，重叠程度较高。在采样光线数相当的情况下，相比于三焦距微透镜阵列，单焦距微透镜阵列采样光线在火焰内部空间重叠程度低，采集到的有效的火焰辐射信息更多，因而更加有利于火焰三维温度场的重建。

![](images/7c4ff3f62468b8185e633e33a3c313f13ca90d629f77488915058e098c7d0259.jpg)  
（a）火焰辐射光场成像模型(a) The light field imaging model of flame

![](images/c05ba10bdb15005cd697f84d3298943663dfd6551be457cc2d7e02591bc8647a.jpg)  
图1聚焦光场相机辐射采样光线示意图Fig.1Schematic of sampling rays of flame radiatior

根据几何光学中的薄透镜公式（1）和（2）[14],对探测面各像素火焰辐射采样光线进行光线追迹，确定这些光线在物方（火焰）空间中的位置和方向。

$$
\frac { 1 } { s ^ { \prime } } + \frac { 1 } { s } = \frac { 1 } { F }
$$

$$
{ \frac { x ^ { \prime } } { x } } = - { \frac { s ^ { \prime } } { s } }
$$

式中， $s ^ { \prime }$ 和 $s$ 分别是透镜的物距和像距，当光线经过微透镜时， $s ^ { \prime }$ 是虚拟像面与微透镜阵列的距离， $s$ 是相机探测面与微透镜阵列的距离， $x '$ 是虚拟像点相对于微透镜中心的坐标， $x$ 是像素点相对于微透镜中心的坐标， $F$ 是微透镜的焦距；当光线经过主透镜时， $s ^ { ; }$ 是虚拟物面与主透镜的距离， $s$ 是虚拟像面与主透镜的距离。 $x '$ 是虚拟光源点相对于主透镜中心的坐标， $x$ 是虚拟像点相对于主透镜中心的坐标， $F$ 是主透镜的焦距。

火焰中的炭黑颗粒是吸收性粒子而且粒径较小，由Mie理论可知，炭黑颗粒散射能力远远弱于吸收能力[15]，本文只考虑吸收，以简化火焰辐射传输过程，使用视在光线法[6，通过式（3）计算相机探测面各像素火焰辐射采样光线的强度，从而得到火焰辐射图像。

$$
I _ { { \scriptscriptstyle n } } = I _ { { \scriptscriptstyle b n } } ( 1 - \exp ( - \tau _ { { \scriptscriptstyle n } } ) ) +
$$

$$
\sum _ { i = 1 } ^ { n - 1 } ( \exp ( - \sum _ { j = i + 1 } ^ { n } \tau _ { j } ) - \exp ( - \sum _ { j = i } ^ { n } \tau _ { j } ) ) I _ { b i }
$$

式中， $I _ { n }$ 为探测面探测到的光线强度。 $I _ { b i }$ 和 $\tau _ { i }$ 分别为光线穿过的路径上第 $i$ 个控制体的黑体辐射强度和光程， $I _ { b n }$ 和 $\tau _ { n }$ 分别为光线穿过的路径上最后一个控制体的黑体辐射强度和光程。

# 2三维温度场重建

为了重建火焰三维温度场，根据式（3）得到关于探测面所有采样光线强度的线性方程组，

$$
A I _ { B } = I _ { c c d }
$$

式中， $I _ { c c d }$ 为相机成像探测面上各像素探测的火焰辐射强度组成的向量， $I _ { B }$ 为火焰所有控制体的黑体辐射强度组成的向量， $A$ 为对应的系数矩阵。系数矩阵 $A$ 是大型稀疏矩阵，基于QR分解的最小二乘法（LSQR）能够求解关于大型稀疏矩阵的最小二乘问题，其类似于共轭梯度法，但是当 $A$ 具有病态性时，算法具有更高的稳定性[17]。式（4）的求解即求解式（5）所示的最小二乘问题，

$$
\operatorname* { m i n } { \left\| \boldsymbol { A } \boldsymbol { x } - \boldsymbol { b } \right\| _ { 2 } }
$$

式中， $\boldsymbol { x }$ 等于 $I _ { B }$ ， $\textbf { \textit { b } }$ 等于 $I _ { c c d }$ 。假定已经进行了 $k$ 次双对角化过程，得到了 $m \times \left( k { + } 1 \right)$ 维正交矩阵 $U _ { k + 1 }$ $n { \times } k$ 维正交矩阵 $V _ { k }$ 和 $( k { + } 1 ) \times k$ 维双对角矩阵 ${ \pmb B } _ { k } ^ { [ 1 8 ] }$

$$
\left\{ \begin{array} { c } { \pmb { U } _ { k + l } = [ \pmb { u } _ { l } , \pmb { u } _ { 2 } , \pmb { \mathrm { L } } ~ \pmb { u } _ { k + l } ] , \pmb { u } _ { l } , \pmb { u } _ { 2 } , \pmb { \mathrm { L } } ~ , \pmb { u } _ { k + l } \in \pmb { R } ^ { \mathrm { m } } } \\ { \pmb { V } _ { k } = [ \pmb { \nu } _ { l } , \pmb { \nu } _ { 2 } , \pmb { \mathrm { L } } ~ \pmb { \nu } _ { k } ] , \pmb { \nu } _ { l } , \pmb { \nu } _ { 2 } , \pmb { \mathrm { L } } ~ , \pmb { \nu } _ { k } \in \pmb { R } ^ { \mathrm { n } } } \end{array} \right\}
$$

$$
B _ { k } = \left[ \begin{array} { c c c c c } { \alpha _ { I } } & { 0 } & { \ L } & { \ L } & { 0 } \\ { \beta _ { 2 } } & { \alpha _ { 2 } } & { 0 } & { \ L } & { 0 } \\ { \mathbf { M } } & { \beta _ { 3 } } & { 0 } & { 0 } & { \ \mathbf { M } } \\ { \mathbf { M } } & { \mathbf { M } } & { \mathbf { O } } & { \mathbf { O } } & { \mathbf { M } } \\ { \mathbf { M } } & { \mathbf { M } } & { \mathbf { O } } & { \mathbf { O } } & { \alpha _ { k } } \\ { \mathbf { O } } & { \mathbf { L } } & { \mathbf { L } } & { \ L } & { \ \beta _ { k + l } } \end{array} \right]
$$

式中 $a _ { I }$ ， $a _ { 2 }$ ，， ${ a } _ { k } \in \mathbf { R }$ ， $\beta _ { I }$ ， $\beta _ { 2 }$ ，， $\beta _ { k + I } \in \mathsf { R }$ 。双对角化过程

$$
\left\{ \begin{array} { c } { \beta _ { I } = \left\| b \right\| _ { 2 } } \\ { u _ { I } = b / \beta _ { I } } \\ { \alpha _ { I } \nu _ { I } = A ^ { \top } u _ { I } } \\ { U _ { k + I } ( \beta _ { I } e _ { I } ) = b } \\ { A V _ { k } = U _ { k + I } B _ { k } } \\ { A ^ { \top } U _ { k + I } = V _ { k } B _ { k } ^ { \top } + \alpha _ { k + I } \nu _ { k + I } e _ { k + I } ^ { \top } } \end{array} \right\}
$$

设：

$$
\left\{ \begin{array} { c } { \pmb { x } _ { k } = \pmb { V } _ { k } \pmb { y } _ { k } } \\ { \pmb { y } _ { k } \in \pmb { R } ^ { k } } \\ { \pmb { r } _ { k } = \pmb { b } - \pmb { A } \pmb { x } _ { k } } \end{array} \right\}
$$

根据式（8）和（9)，可得：

$$
r _ { k } = U _ { { k + l } } ( \beta _ { l } \pmb { e } _ { l } - \pmb { B } _ { k } \pmb { y } _ { k } )
$$

因为 $U _ { k + I }$ 是正交矩阵，正交变换不改变矩阵的范数，所以原问题变为

$$
\operatorname* { m i n } \left\| \pmb { r } _ { k } \right\| _ { 2 } = \operatorname* { m i n } \left\| \beta _ { l } \pmb { e } _ { l } - \pmb { B } _ { k } \pmb { y } _ { k } \right\| _ { 2 }
$$

即把原来复杂最小二乘问题转换为一个较为简单的最小二乘问题，采用标准QR分解方法对该最小二乘问题（11）进行求解。得到火焰第 $i$ 个控制体的黑体辐射强度 $I _ { b i }$ ，根据斯特藩一玻尔兹曼（Stefan-Boltzmann）定律式（12）进一步计算各控制体的火焰温度。

$$
T _ { i } = ( I _ { b i } \pi / \sigma ) ^ { \frac 1 4 }
$$

式中，斯特藩-玻尔兹曼（Stefan-Boltzmann）常数 $\overset { \cdot } { \boldsymbol { \sigma } }$ 是$5 . 6 7 0 3 7 3 { \times } 1 0 ^ { - 8 } \ \mathbf { W } { \cdot } \mathbf { m } ^ { - 2 } { \cdot } \mathbf { K } ^ { - 4 } .$

# 3结果及分析

# 3.1数值模拟

为了比较单焦距微透镜阵列和三焦距微透镜阵列聚焦光场相机火焰三维温度场重建的精确度，进行了数值模拟计算。根据商用聚焦光场相机RaytrixR29 的参数[10,12]设定各计算参数值，如表1所示。其中， $d _ { m }$ 和 $d _ { p }$ 分别为微透镜直径和各像素的边长，$N _ { m }$ 、 $N _ { s }$ 分别为各子图像（微透镜覆盖的一组像素）直径覆盖的像素个数和微透镜阵列上纵向(或横向）

的微透镜个数， $f _ { m } , f$ 分别为微透镜的焦距和主透镜的焦距， $L _ { i x } , \ L _ { u x }$ 和 $L _ { x p }$ 分别为微透镜阵列与虚拟像面、主透镜面、相机探测面之间的距离， $L _ { o u }$ 为主透镜面与虚拟物面之间的距离。

对于两种微透镜阵列，参数 $d _ { m } , d _ { p } , N _ { m } , N _ { s } , f .$ $L _ { u x }$ 和 $L _ { x p }$ 均相同，单焦距微透镜阵列微透镜焦距 $f _ { m }$ 为 $6 0 0 ~ { \mu \mathrm { m } }$ 。三焦距微透镜阵列，三种微透镜(A、B和C)的焦距 $f _ { m }$ 分别为 $6 5 0 \mu \mathrm { m }$ 、 $6 0 0 \mu \mathrm { m }$ 和 $5 5 0 \mu \mathrm { m }$ 均大于微透镜阵列与探测面的距离 $L _ { x p }$ （ $4 4 0 \mathrm { m m } )$ ，三种焦距微透镜在横向（或纵向）依次间隔排列，任意两个相同焦距的微透镜互不相邻。 $L _ { i x }$ 和 $L _ { o u }$ 根据第1节所描述的共轭关系计算得到。

火焰设置为圆柱体形状，半径 $L$ 为 $8 0 \mathrm { m m }$ ，高度 $H$ 为 $3 0 0 \mathrm { m m }$ ，火焰的吸收系数为 $8 ~ \mathrm { m ^ { - 1 } }$ ，将火焰按轴向、径向和周向划分为 $1 0 \times 1 0 \times 1$ 个控制体，火焰的温度设置为关于圆柱体中心轴呈对称分布，分布函数 $T \ ( r , \ z )$ 如下式。

$$
T = 1 8 0 0 \sin \left( \frac { r ^ { 2 } } { 2 ( L ^ { 2 } / H ) } + z \right) + 2 7 3 . 1 5 \ K \ ,
$$

式中， $\boldsymbol { r } , \boldsymbol { z }$ 分别为以火焰底面中心为坐标系原点，对应控制体中心位置的径向和轴向坐标，单位为mm。对于单焦距微透镜阵列，火焰中心面位于虚拟物面上，对于三焦距微透镜阵列，火焰中心面位于微透镜（B）对应的虚拟物面上。由于火焰半径为$8 0 ~ \mathrm { m m }$ ，三种焦距微透镜(A、B和C)对应的虚拟物面与主透镜面的距离 $L _ { o u }$ 为 $5 0 5 \mathrm { m m }$ 、 $4 8 2 \mathrm { m m }$ 和444mm，三种虚拟物面均处于火焰内部，确保火焰对于三种焦距的微透镜均未处于离焦位置。

表1数值模拟中的光场相机参数Table1 The parameters of the light field camera in the numerical simulations  

<html><body><table><tr><td>参数</td><td>dp/ mm</td><td>Nm</td><td>Ns</td><td>fm/ mm</td><td>dm/ mm</td><td>f/ mm</td><td>Lix/ mm</td><td>Lux/mm</td><td>Lxp /mm</td><td>Lou /mm</td></tr><tr><td>单焦距微 透镜阵列</td><td>0.080</td><td>12</td><td>60</td><td>0.60</td><td>0.095</td><td>50</td><td>-1.65</td><td>54.14</td><td>0.44</td><td>505</td></tr><tr><td>三焦距微 透镜阵列</td><td>0.080</td><td>12</td><td>60</td><td>A: 0.65 B: 0.60 C: 0.55</td><td>0.095</td><td>50</td><td>A: -1.36 B: -1.65 C: -2.20</td><td>54.14</td><td>0.44</td><td>A: 505 B: 482 C: 444</td></tr></table></body></html>

根据式（3）计算得到火焰辐射图像，如图2所示。图2（a）是单焦距微透镜阵列聚焦光场相机的火焰图像，图2（b）是三焦距微透镜阵列聚焦光场相机的火焰图像。从宏观上看两幅图像基本一致，火焰图像符合式（13）所示的温度分布特征，温度高的部分对应的图像区域亮，温度低的部分对应的图像区域暗。

比较火焰子图像可以发现，单焦距微透镜阵列聚焦光场相机各子图像大小一致，而三焦距微透镜阵列聚焦光场相机，虽然微透镜直径 $d _ { m }$ 大小相同，但是不同焦距的微透镜对应的子图像直径大小不同，微透镜焦距 $f _ { m }$ 越大（ $\mathrm { C } \mathrm { \to } \mathrm { B } \mathrm { \to } \mathrm { A } .$ )，对应的子图像直径越小，如图2（b）所示。这是由于成像探测面与微透镜阵列的距离 $L _ { x p }$ 不变，微透镜焦距 $f _ { m }$ 越大，光瞳在探测面上关于微透镜的成像离焦程度越大，其成像轮廓越模糊，子图像直径越小。

火焰图像叠加不同程度的高斯噪声模拟测量误差，信噪比分别为30dB和20dB，根据第2节中所提方法重建火焰三维温度场，得到各控制体温度重建相对误差，计算所有控制体（ $1 0 \times 1 0 \times 1$ ）相对误差的平均值，结果如图3所示。可以看出，噪声增大时，单焦距和三焦距微透镜阵列的温度重建相对误差均随之增大。而在其中任一中噪声水平（30 dB或20dB）下，单焦距微透镜阵列的温度重建相对误差均小于三焦距微透镜阵列的重建相对误差。这是由于相比于三焦距微透镜阵列聚焦光场相机，单焦距微透镜阵列聚焦光场相机的火焰辐射采样光线在火焰内部的分布具有更高的均匀性，因而火焰温度测量具有更高的精确度。

![](images/2057ed98fdcf6591e59ee09bc411bdba3fdb99668fd19be9e411769d1036de9e.jpg)  
图2两种微透镜阵列下聚焦光场相机的火焰辐射图像 Fig.2 The light field images of the flame based on the focused light field camera with two types of microlens array   
图3重建的温度相对误差 Fig.3 The relative error of the reconstructed temperature

# 3.2实验研究

进行三焦距微透镜阵列聚焦光场相机（RaytrixR29）乙烯扩散火焰温度测量实验，拍摄火焰光场图像，如图4（a）所示。火焰燃料流量为 $3 \mathrm { m L / s }$ 火焰半径和高度分别为 $1 0 \mathrm { m m }$ 和 $9 0 \mathrm { m m }$ 。利用该图像，根据所提方法，重建了该乙烯扩散火焰的三维温度场。沿火焰高度方向 ${ Z = } 5 \mathrm { m m }$ 至 ${ \cal Z } { = } 9 0 \mathrm { m m }$ 均匀选取6个横截面，如图4（a）所示，各截面温度分布重建结果如图4（b）所示。图中，火焰温度范围从 $7 0 0 \mathrm { K }$ 到 $1 4 0 0 \mathrm { K }$ ，由于扩散火焰中，燃料（乙烯)由内向外扩散，空气由外向内扩散，当燃料和空气混合比等于该燃料燃烧的化学当量比时，燃料完全燃烧，释放大量热量，形成高温区域，该区域火焰温度高于其它区域[20]，因而火焰各截面温度分布沿径向呈现由内向外各层温度先升高再降低的趋势，而火焰最高层（ $\mathrm { 9 0 ~ m m }$ ）截面，燃料与空气在中心处能够充分混合，沿径向由内向外各层温度逐渐降低，图4（b）所示的温度分布与该温度分布规律较吻合。

利用热电偶（R型）测量火焰不同高度（ $\scriptstyle { Z = 3 0 }$ mm, ${ Z } { = } 6 0 \mathrm { m m }$ )截面径向上的不同位置点( $\scriptstyle \cdot R = 0 \mathrm { m m }$ $R { = } 5 \mathrm { m m }$ ， $R { = } 1 0 \mathrm { m m }$ ）的温度值。由于热电偶测量火焰温度时，与温度较低的周围环境进行辐射换热，导致辐射量的损失，根据文献[19]，对热电偶火焰温度测量结果进行修正。修正后的温度值与三焦距聚焦光场相机的温度重建值进行比较，结果如图5所示，这两种高度下温度分布趋势基本一致，随着半径的增加，火焰温度先增加再减小。在高度 $\scriptstyle { Z = 6 0 }$ mm 半径 $R { = } 5 \ \mathrm { m m }$ 处，二者的温度差值达到最高的$1 8 2 ~ \mathrm { K }$ ，其他各处温度差值均小于 $8 5 ~ \mathrm { K }$ ，温度差值最小为8K，相对火焰达 $1 4 0 0 \mathrm { K }$ 的高温而言，重建结果具有一定可靠性。

为了进一步提高火焰三维温度场重建的精确度，根据数值模拟的结果，可设计组装单焦距微透镜阵列聚焦光场相机来重建火焰的三维温度场。

16 单焦距 12 三焦距 8   
% 4   
/美 0 1   
误 -4 -8 -12 30 20 噪声／dB

![](images/90b4e8fdcc8ecc88db829040f823ac88ff4b99a90c335a1a9343f3ea318a775c.jpg)  
（a）乙烯扩散火焰光场图像(a) The light field image of the ethylene diffusion flame

![](images/1b6e9fe289501c55583a488d8caa349d2f16dcd27f4dd4b5d2d3a64e12265dc1.jpg)  
图4基于三焦距微透镜阵列聚焦光场相机的火焰图像及重建的温度场  
Fig.4 The light field image and reconstructed temperature field of the flame based on the light field camera with a multiple focus microlens array

![](images/f8cf4cf85d9a751cbd80e1494f84546bcb181afe6f3927eeec1712b251bb3499.jpg)  
图5火焰热电偶测温结果与温度场重建结果对比 Fig. 5 Comparison of the temperatures obtained using the thermocouple and the reconstructed for different cross-sections

# 4结论

本文分析了单焦距微透镜阵列和多（三）焦距微透镜阵列的光场成像特征，比较了两种微透镜阵列的火焰辐射采样光线的分布特性。利用视在光线法分别计算了两种不同微透镜阵列下的火焰辐射图像，并叠加了不同水平的噪声作为测量误差，在此基础上重建了火焰的三维温度场。最后利用多焦距微透镜阵列聚焦光场相机对乙烯扩散火焰进行了三维温度测量的实验研究。结果表明：对于三焦距聚焦光场相机，火焰光场图像中，子图像轮廓随着微透镜焦距的增大而减小。单焦距微透镜阵列火焰辐射采样光线在火焰内部空间分布较均匀，各采样光线独立性较高，单焦距微透镜阵列聚焦光场相机火焰温度场重建误差小于三焦距微透镜阵列。乙烯扩散火焰温度场重建实验结果与热电偶温度测量结果分布趋势基本一致，数值上吻合较好。下一步将研究设计单焦距微透镜阵列聚焦光场相机来重建火焰三维温度场，以提高火焰温度重建的精确度。

参考文献   
[1]Ballster J, Garcia-Armingol T. Diagnostic techniques for the monitoring and control of practical flames [J].Progress in Energy and Combustion Science,2010,36(4):375-411   
[2]王宁飞，苏万兴，李军伟等．固体火箭发动机中铝粉 燃烧研究概述 [J]．固体火箭技术，2011,34(1):61-66 WANG Ningfei, SU Wanxing,Li,LIJunwei, etal. A survey of study on aluminum combustion in solid rocket motors [J]. Journal of Solid Rocket Technology,2011,34(1):61-66   
[3]Yang HN, Yang B,CAI X S, Hecht C,Dreier T,and Schulz C,“Three-dimensional (3-D) temperature measurement in a low pressure flame reactor using multiplexed tunable diode laser absorption spectroscopy (TDLAS),” Laser. Eng. 31, 285-297 (2015).   
[4]Ma L, Cai W, CaswellA W,et al. Tomographic Imaging of Temperature and Chemical Species Based on Hyperspectral Absorption Spectroscopy [J]. Optics Express,2009,17(10): 8602-8613   
[5]娄春,孙亦鹏,周怀春.基于图像处理测量扩散火焰温度 和碳黑浓度[J].工程热物理学报,2010,(9):1595-1598 LOU Chun, SUN Yipeng, ZHOU Huaichun. Measurement of temperature and soot concentration in a diffusion flame by image processing[J]. Joumal of Engineering Thermophysics, 2010, 31(9): 1595-1598   
[6]Hossain M M,Lu G, Sun D,et al. Three-dimensional reconstructionofflametemperatureandemissivity distribution using optical tomographic and two-colour pyrometric techniques [J]. Measurement Scienceand Technology,2013,24(7):1-10   
[7]Li W,Lou C, Sun Y, et al. Estimation ofradiative properties and temperature distributions in coal-fired boiler furmaces by a portable image processing system [J]. Experimental Thermal and Fluid Science,2011,35(2):416-421   
[8]张婷,郭庆华,龚岩等.CH4/O2同轴射流扩散火焰辐射 发光特性[J].燃烧科学与技术,2012,18(4):353-358 ZHANG Ting，GUO Qinghua， GONG Yan，et al. Luminescent properties of CH4/O2 co-flowing jet diffsion flame [J]. Journal of Combustion Science and Technology, 2012, 18(4):353-358   
[9] $\Nu \tt { g } \mathrm { ~ R ~ }$ ,Levoy M, Bredif M,et al. Light field photography with a hand-held plenoptic camera [R], Computer Science Technical Report CSTR of Stanford University,2005,1-11   
[10]Sun J, Xu C,Zhang B,etal.Three-dimensional temperature field measurement of flame using a single light field camera   
[11] Georgiev T,Lumsdaine A. Focused plenoptic camera and rendering [J]．Jourmal of Electronic Imaging， 2010, 19(2):021106-1-021106-11   
[12] Perwass，Ulrich， Perwass C. Digital imaging system, plenoptic optical device and image data processing method [P]. U.S.Patent No. 8,619,177. 31 Dec. 2013   
[13] 孙俊,许传龙,张彪等.基于单光场相机的火焰三维温度 场测量[J].工程热物理学报,2016,37(3):527-532 SUN Jun， XU Chuanlong， ZHANG Biao，et al. Measurement of three-dimensional temperature field of flame based on a single light field camera [J].Journal of Engineering Thermophysics,2016,37(3):527-532   
[14]Fusiello A,Elements of geometric computer vision. [2016]. http://homepages.inf.ed.ac.uk/rbf/CVonline/LOCAL_COPI ES/FUSIELLO4/tutorial.html   
[15]Felske J, Tien C.Calculation of the emissivity of luminous flames[J]. Jounal of Combustion Science and Technology, 1973, 7(1), 25-31   
[16]Niu C, Qi H, Huang X et al. Simultaneous reconstruction of temperaturedistributionandradiativepropertiesin participating media using a hybrid LSQR-PSO algorithm [J]. Chinese Physics B,2015,24(11):285-295   
[17] Paige C C, Saunders M A. LSQR: An algorithm for sparse linearequationsand sparse least squares[J]. ACM Transactions on Mathematical Software (TOMS),1982, 8(1): 43-71   
[18]刘冬,王飞,黄群星等.三维炉膛温度场重建中病态矩阵 方程的求解研究[J.中国电机工程学报，2007， 27(26):72-77 LIU Dong, WANG Fei, HUANG Qunxing, et al. Study on Solving ill-posed matrix equation in reconstruction of three-dimensional temperature distribution infurmace [J]. Proceedings of the CSEE,2007,27(26):72-77   
[19] Hossain M M. Tomographic characterisation of bumer flames through digital imaging and image processng [D]. Ph.D. dissertation, University of Kent,1956   
[20]TurnsS R. An Introduction to Combustion[M]. McGraw-Hill Education,1996