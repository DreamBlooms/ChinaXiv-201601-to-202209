# CN 53-1189/P ISSN 1672-7673

# 弱偏振器件Mueller矩阵测量的校准及应用

彭建国1,²，袁沭¹，金振宇1(1.中国科学院云南天文台，云南 昆明650011；2.中国科学院大学，北京100049)

摘要： $1 \mathrm { ~ m ~ }$ 新真空太阳望远镜(New Vacuum Solar Telescope，NVST)的高分辨磁像仪采用了同步重建技术，其中用到了分束镜。分束镜从设计上一般会进行偏振优化，尽量减小偏振效应，但还是不可避免地对太阳磁场的偏振测量造成影响，因此，对分束镜偏振特性的测量是 $1 \mathrm { ~ m ~ }$ 太阳望远镜进行太阳磁场偏振测量的必需步骤。运用空气Mueller矩阵校准法对Mueller矩阵测量结果进行了校准，测量了两块用于磁场偏振测量的分束镜样品，比较了不同分束镜方案的 Mueller矩阵及其对偏振测量的影响，并测量了平板玻璃的 Mueller矩阵随入射角变化的结果，比较测量结果与理论值之间的偏差，利用空气Mueller矩阵进行校准后测量系统达到 $5 \times { 1 0 } ^ { - 3 }$ 的 Mueller矩阵测量精度。

关键词：偏振光学；分束镜偏振特性；弱偏振器件 Mueller矩阵测量；空气Mueller矩阵定标中图分类号：0436.3 文献标识码：A文章编号：1672-7673(2018)01-0095-09

太阳磁场是主导太阳活动的主要因素[1]，而太阳磁场高分辨图像是分析太阳活动与磁场变化之间关系的基本依据。目前，国内外有不少研究机构致力于太阳磁场高分辨观测的研究。其中，瑞典

$1 \mathrm { m }$ 太阳望远镜(Swedish Solar Telescope，SST)[2],美国大熊湖观测站的新太阳望远镜（NewSolarTelescope，NST）[3]，德国的GREGOR太阳望远镜[4都在太阳磁场高分辨成像或者光谱观测方面取得了优秀的成果。在国内，国家天文台怀柔观测站的太阳磁场望远镜[5]以及云南天文台的太阳Stokes 光谱望远镜[6-7]在太阳磁场的偏振测量方面做出了重要贡献。云南天文台的 $1 \mathrm { ~ m ~ }$ 太阳望远镜以其口径和台址等优势，有望获得在太阳活动中磁场的小尺度结构信息[8]

目前，太阳磁场主要通过观测磁敏谱线的偏振分裂获得[9]。然而，太阳望远镜要进行磁场观测，对望远镜及相关仪器的偏振定标必不可少[10-12]。图1(a)是 $1 \mathrm { ~ m ~ }$ 太阳望远镜的光路示意图，文[10]已经建立相关模型对望远镜进行偏振定标。图1(b)是 $1 \mathrm { ~ m ~ }$ 太阳望远镜磁场测量终端示意图，该终端安装于图1(a)中望远镜光路系统的后端，图1(b)中场镜位于望远镜焦点 $F _ { 3 }$ 处。

![](images/1b300b759ecc13224bcfc918fd482730ab01a830250dffaabf0ea78ec8e7da9b.jpg)  
图1 (a) $1 \mathrm { m }$ 太阳望远镜光路示意图；（b）磁场测量终端 Fig.1（a）Optical path diagram of NVST; （b）magnetic field measuring equipment

由于文[10]中已经对 $F _ { 3 }$ 前的望远镜系统进行了相应的偏振定标，现在只需要对 $F _ { 3 }$ 到偏振分析器间的光学器件进行偏振特性的测量，特别是分束镜的偏振效应。

由于分束镜的偏振效应较弱(一般在百分之几)，对偏振特性(本文中用Mueller矩阵表示)的测量更容易受测量系统精度的影响。本文采用空气Mueller 矩阵校准法对双旋转波片Mueller矩阵测量系统[13-14]的测量结果进行了校准，提高了系统对 Mueller 矩阵的测量精度。

# 1双旋转波片测量系统及空气Mueller矩阵校准法

# 1.1双旋转波片Mueller矩阵测量系统的建立

双旋转波片Mueller矩阵测量系统原理如图2，图中 $P L _ { 1 }$ 和 $\boldsymbol { W P } _ { 1 }$ 组成偏振发生器，用于产生已知状态的偏振光， $\boldsymbol { W P } _ { 2 }$ 和 $P L _ { 2 }$ 组成偏振分析器，分析经过样品之后偏振光的状态。图中两个偏振片 $P L _ { 1 }$ 和$P L _ { 2 }$ 的透过轴方向相同且固定不动，测量过程中旋转波片 $\boldsymbol { W P } _ { 1 }$ 和 $\boldsymbol { W P } _ { 2 }$ 。Mueller矩阵测量系统从光源到探测器依次是：激光二极管光源，格兰-汤普森棱镜 $P L _ { 1 }$ ， $1 / 4$ 波片 $\boldsymbol { W P } _ { 1 }$ ，待测样品， $1 / 4$ 波片 $\boldsymbol { W P } _ { 2 }$ ，偏振片 $P L _ { 2 }$ ，滤光片，光功率计。其中， $\boldsymbol { W P } _ { 1 }$ 和 $\boldsymbol { W P } _ { 2 }$ 分别安装在两个电控精密转台上，对波片角度$( \boldsymbol { \theta } _ { 1 } , \boldsymbol { \theta } _ { 2 } )$ 调节。可通过软件控制，实现多组 $( \boldsymbol { \theta } _ { 1 } , \boldsymbol { \theta } _ { 2 } )$ 的连续控制及光强的同步采集。测量系统选取 $\theta _ { 1 }$ ，$\boldsymbol { \theta } _ { 2 }$ 分别调节至（0，22.5，45，…，157.5）8个位置，一次测量得到64个光强值。其中， $\theta _ { 1 }$ ， $\boldsymbol { \theta } _ { 2 }$ 的调节位置是依据 $Q$ ， $U$ 的调制频率及响应矩阵对角化得到的。

![](images/2e5828222d260867d729f4259ea9d3b9f78ebe1f17d08618804a256e37353ee6.jpg)  
图2双旋转波片测量系统原理图  
Fig.2Schematic diagram of dual-rotating-retarder Mueller matrix polarimeter

系统选取起偏棱镜 $P L _ { 1 }$ 的起偏方向为 $Q$ 方向，依次将 $P L _ { 2 }$ 的透过轴及 $\boldsymbol { W P } _ { 1 }$ ， $\boldsymbol { W P } _ { 2 }$ 的快轴对准至 $Q$ 方向，并对 $\boldsymbol { W P } _ { 1 }$ ， $\boldsymbol { W P } _ { 2 }$ 的延迟量进行拟合[15-16]，得出 $\delta _ { \scriptscriptstyle 1 }$ ， $\delta _ { \scriptscriptstyle 2 }$ 分别为 $8 7 . 6 ^ { \circ }$ 和 $8 8 . 4 ^ { \circ }$ 。

在建立图2的测量系统时，选择激光二极管光源，该光源稳定性好，且准直度高，光斑半径小。可以直接使光源发出的光经过偏振发生器、待测样品、偏振分析器和滤光片后直接进入光功率计，而不需要使用透镜，这样既缩短了光路，又避免了透镜的偏振特性对测量结果的影响。

1.2Mueller矩阵的计算过程测量系统光强与各个光学元件参数关系如下：

$$
I ( \theta _ { 1 } , \ : , \ : \delta _ { 1 } , \ : \theta _ { 2 } , \ : \ : \delta _ { 2 } ) = [ 1 , \ : 0 , \ : \ : 0 , \ : \ : 0 ] M _ { \mu _ { 2 } } M _ { \mu \nu _ { 2 } } ( \theta _ { 2 } , \ : \ : \delta _ { 2 } ) M _ { s } M _ { u \nu _ { 1 } } ( \theta _ { 1 } , \ : \ : \delta _ { 1 } ) M _ { \mu _ { 1 } } [ I _ { 0 } , \ : \ : 0 , \ : \ : 0 , \ : \ : 0 ] .
$$

定义 $S _ { i } = M _ { \scriptscriptstyle { w p _ { 1 } } } ( \theta _ { _ { 1 i } } , \ \delta _ { 1 } ) M _ { \scriptscriptstyle { p l _ { 1 } } } [ I _ { 0 } , \ 0 , \ 0 , \ 0 , \ 0 ] ,$ $S _ { i }$ 表示与 $\theta _ { 1 i }$ 对应的定标光斯托克斯（Stokes)参量；定义$P _ { j } = ~ [ 1 , ~ 0 , ~ 0 , ~ 0 ] ~ M _ { p l _ { 2 } } M _ { w p _ { 2 } } ( \theta _ { 2 j } , ~ \delta _ { 2 } )$ ， $P _ { j }$ 表示与 $\theta _ { 2 j }$ 对应的偏振分析器对光强的调制矩阵。

由1.1所述的测量过程，测得 $8 \times 8$ 光强矩阵：

$$
I _ { 8 , \mathrm { ~ 8 ~ } } = P _ { 8 , \mathrm { ~ 4 } } M _ { s } S _ { 4 , \mathrm { ~ 8 ~ } } ,
$$

其中， ${ S _ { 4 , 8 } = \mathrm {  ~ \left( ~ { \cal S } ~ \right)} _ { 1 } , \mathrm {  ~ \cdots ~ } , \mathrm {  ~ { \cal S } ~ } _ { i } , \mathrm {  ~ \cdots ~ } , \mathrm {  ~ { \cal ~ S } ~ } _ { 8 }  ; \mathrm {  ~ { \cal ~ P } ~ } _ { 8 , 4 } = \mathrm {  ~ \left( ~ { \cal ~ P } ~ \right)} _ { 1 } , \mathrm {  ~ \cdots ~ } , \mathrm {  ~ { \cal ~ P } ~ } _ { j } , \mathrm {  ~ \cdots ~ } , \mathrm {  ~ { \cal ~ P } ~ } _ { 8 }  } . \mathrm {  ~ \left( ~ { \cal ~ S } ~ \right)} _ { 1 } , \mathrm {  ~ \cdots ~ } , \mathrm {  ~ { \cal ~ S } ~ } _ { i } , \mathrm {  ~ \cdots ~ } , \mathrm {  ~ { \cal ~ P } ~ } _ { 8 }   . \mathrm {  ~ \left( ~ { \cal ~ S } ~ \right)} _ { 1 } , \mathrm {  ~ \cdots ~ } , \mathrm {  ~ { \cal ~ P } ~ } _ { j } , \mathrm {  ~ \cdots ~ } , \mathrm {  ~ { \cal ~ P } ~ } _ { 8 }  \mathrm {  ~ \left( ~ { \cal ~ P } ~ \right)} _ { 1 } , \mathrm {  ~ \cdots ~ } , \mathrm {  ~ { \cal ~ P } ~ } _ { j } , \mathrm {  ~ \cdots ~ } , \mathrm {  ~ { \cal ~ P } ~ } _ { 8 }  \mathrm {  ~ \left( ~ { \cal ~ P } ~ \right)} _ { 1 } , \mathrm {  ~ \cdots ~ } , \mathrm {  ~ { \cal ~ P } ~ } _ { j } , \mathrm {  ~ \cdots ~ } , \mathrm {  ~ { \cal ~ P } ~ } _ { 8 }  \mathrm {  ~ \left( ~ { \cal ~ P } ~ \right)} _ { 1 } , \mathrm {  ~ \cdots ~ } , \mathrm {  ~ { \cal ~ P } ~ } _ { j } , \mathrm {  ~ \cdots ~ } , \mathrm {  ~ { \cal ~ P } ~ } _ { 8 }  . $

通过矩阵运算得出方程的最小二乘解，即

$$
M _ { s } = ( P _ { \ L _ { 8 , 4 } } P _ { \ L _ { 8 , 4 } } ) \ L ^ { - 1 } P _ { \ L _ { 8 , 4 } } I _ { \ L _ { 8 , 8 } } S _ { \ L _ { 4 , 8 } } ( S _ { \ L _ { 4 , 8 } } S _ { \ L _ { 4 , 8 } } ) \ L ^ { - 1 } .
$$

# 1.3空气Mueller 矩阵校准法

由于空气是各向同性的，无样品时进行测量根据（3)式计算的Mueller矩阵应该为单位矩阵，而实际测量中相对单位矩阵有偏离。这主要是由于对偏振片和波片参数测量的偏差以及偏振片和波片自身的不理想因素造成的。

本文不具体分析产生上述问题的原因，而是选择采用空气Mueller矩阵校准的方法实现对测量误差的处理和优化。下面分析如何使用空气Mueller矩阵 $M _ { \mathrm { c } }$ 对分束镜这类偏振效应相对较弱的样品进行校准的过程。

空气 Mueller 矩阵测量的结果 $M _ { \mathrm { { c } } }$ 可以看作单位矩阵 $E$ 与一个 $4 \times 4$ 矩阵 $m _ { 0 }$ 的和，即 $M _ { \mathrm { c } } = E + m _ { 0 }$ ，$m _ { 0 }$ 为一个小量。

由于 $m _ { 0 } { \neq } 0$ 是偏振发生器和偏振分析器与理想情形偏离造成的，所以针对空气的测量可以把（2)式展开有

$$
I _ { 8 , \mathrm { ~ 8 ~ } } = P _ { 8 , \mathrm { ~ 4 ~ } } ^ { 0 } ( E + \Delta p ) E ( E + \Delta s ) S _ { 4 , \mathrm { ~ 8 ~ } } ^ { 0 } ,
$$

其中， $( E + \Delta s )$ 和 $\left( E + \Delta p \right)$ 分别表示偏振发生器和偏振分析器相对理想情形的偏离程度， $\Delta p$ ， $\Delta s$ 为小量。无样品的测量结果 $M _ { \mathrm { { c } } } = \left( E + \Delta p \right) \left( E + \Delta s \right)$ 。

当待测样品的Mueller矩阵接近单位矩阵 $E$ ，即该样品为一个弱偏振原件时，样品实际 Mueller 矩阵 $M _ { \mathrm { s } } ^ { 0 } = \left( E + \Delta x \right)$ ， $\Delta x$ 为一个小量。对待测样品直接用（3)式计算出的结果 $M _ { \mathrm { s } }$ 与 $M _ { \mathrm { s } } ^ { 0 }$ 的关系如下：

$$
\begin{array} { r l } & { M _ { s } = \left( E + \Delta p \right) M _ { s } ^ { 0 } ( E + \Delta s ) } \\ & { \quad = \left( E + \Delta p \right) \left( E + \Delta x \right) \left( E + \Delta s \right) } \\ & { \quad = \left[ \left( E + \Delta x \right) \left( E + \Delta p \right) - \left( \Delta x \Delta p - \Delta p \Delta x \right) \right] \left( E + \Delta s \right) } \\ & { \quad = M _ { s } ^ { 0 } M _ { \mathrm { c } } - \left( \Delta x \Delta p - \Delta p \Delta x \right) \left( E + \Delta s \right) } \\ & { \quad \approx M _ { s } ^ { 0 } M _ { \mathrm { c } } } \\ & { \quad \qquad M _ { s } ^ { 0 } \approx M _ { s } { M _ { \mathrm { c } } } ^ { - 1 } . } \end{array}
$$

$M _ { \mathrm { s } } ^ { 0 }$ 即为使用空气Mueller矩阵 $M _ { \mathrm { { c } } }$ 进行校准后的结果，该式近似精度与 $\Delta p$ ， $\Delta x$ 趋近无穷小的程度有关。

使用空气Mueller矩阵进行校准后，实验测量系统的误差主要来源于公式的近似误差以及光强不稳定性。

# 2分束镜Mueller矩阵的测量

先用调试好的测量系统进行空气Mueller矩阵的测量，并将测量结果 $M _ { \mathrm { c } }$ 用于后续测量的校准；接着对一块标准的K9玻璃进行入射角从 ${ 0 } ^ { \circ }$ 到 ${ 5 0 } ^ { \circ }$ 的Mueller矩阵测量，比较测量结果和理论值的差别;然后用测量系统对待测分束镜样品进行测量；最后对测量系统的误差进行分析。

# 2.1无样品时的空气Mueller矩阵

按照1.2节的介绍，将测得的光强矩阵 $I _ { 8 , 8 }$ 、波片的延迟量 $8 7 . 6 ^ { \circ }$ 和 $8 8 . 4 ^ { \circ }$ 及方位角（0,22.5，…,157.5)代入(3)式得出空气的Mueller矩阵：

$$
M _ { \mathrm { c } } = \left[ { \begin{array} { c c c c } { 1 } & { - 0 . 0 0 3 4 } & { 0 . 0 1 7 5 } & { 0 . 0 0 0 9 } \\ { - 0 . 0 0 1 8 } & { 1 . 0 0 4 3 } & { - 0 . 0 0 3 9 } & { - 0 . 0 0 2 9 } \\ { - 0 . 0 1 9 6 } & { 0 . 0 0 0 9 } & { 1 . 0 0 5 0 } & { - 0 . 0 0 0 5 } \\ { 0 . 0 0 0 7 } & { 0 . 0 0 3 5 } & { 0 . 0 0 0 7 } & { 1 . 0 0 0 8 } \end{array} } \right] ,
$$

测得的空气Mueller矩阵并不是一个具有实际物理意义的矩阵，而是测量系统不完美程度的表征。该矩阵反映了不进行校准的测量误差在 $2 \%$ 左右，极大地限制了对样品测量的精度。

在后续测量中使用空气矩阵的测量结果 $M _ { \mathrm { { c } } }$ 对样品Mueller矩阵的测量结果进行校准，以提高测量精度。

2.2测量平板玻璃Mueller矩阵随入射角变化的结果

测量K9 平板玻璃在入射角从 ${ 0 } ^ { \circ }$ 到 ${ 5 0 } ^ { \circ }$ 变化时的Mueller 矩阵，并比较测量结果与菲涅尔公式得出结果的差别，这样可以从实际测量角度得出Mueller矩阵测量系统的准确度。

设平板玻璃的偏振光 $P$ 分量和 $s$ 分量的透过强度比为 $\mathbf { \chi } _ { t }$ ，K9玻璃透射光的Mueller矩阵为

$$
M ( n , \ \alpha ) = \left[ \begin{array} { c c c c } { { 1 } } & { { { \frac { 1 - t } { 1 + t } } } } & { { 0 } } & { { 0 } } \\ { { } } & { { } } & { { } } & { { } } \\ { { { \frac { 1 - t } { 1 + t } } } } & { { 1 } } & { { 0 } } & { { 0 } } \\ { { } } & { { } } & { { } } & { { } } \\ { { 0 } } & { { 0 } } & { { { \frac { 2 \sqrt { t } } { 1 + t } } } } & { { 0 } } \\ { { } } & { { } } & { { } } & { { } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { { \frac { 2 \sqrt { t } } { 1 + t } } } } \end{array} \right] ,
$$

其中， $P$ ， $s$ 透过强度比 $\mathbf { \chi } _ { t }$ 为折射率 $n$ 和入射角 $\alpha$ 的函数。

图3为K9平板玻璃入射角 $\alpha$ 从 ${ 0 } ^ { \circ }$ 到 ${ 5 0 } ^ { \circ }$ 变化时的Mueller矩阵，该 $4 \times 4$ 图与(7)式中 $4 \times 4$ 的Mueler矩阵的各个阵元对应。从图3可以看出，（7)式中的0、1阵元的测量结果与理论值之间的偏差基本在 $5 \times { 1 0 } ^ { - 3 }$ 以内。

（20 $\times 1 0 ^ { - 3 }$ （204号 ×10-3  
1.005 501 -0.05 oprwrmm ee8-0.1 5 -5  
0.9950 10 20 30 40 50 0 10 20 30 40 50 0 10 20 3040 50 0 10 20 30 40 50×10-3 ×10-30 1.005 5  
-0.05 1 5 AWAM pe 5-10-0.1 0.995 -15 -50 10 20 30 40 50 0 10 20 30 40 50 0 10 20 3040 50 0 10 20 30 40 50X10 X103 X10-35 1.00510 a 5www mhy 0.995 wVWv-5 0.99 g-5 0.985 -50 10 20 30 40 50 0 10 20 30 40 50 0 10 20 3040 50 0 10 20 30 40 50X10-3 ×10-3 ×10-35 5 5 1.005e v 0.9950.99-5 -5 5 0.9850 10 20 30 40 50 0 10 20 30 40 50 0 10 20 3040 50 0 10 20 30 40 50

图4比较了阵元 $M _ { \scriptscriptstyle { 1 2 } }$ ， $M _ { 2 1 }$ ， $M _ { 3 3 }$ ， $M _ { 4 4 }$ 的测量值与理论值，可以看出(7)式中非0、1阵元的最大误差也在 $5 \times { 1 0 } ^ { - 3 }$ 内。

本节对标准样品K9玻璃的Mueller矩阵测量结果与理论值的比较，可得使用空气Mueller矩阵校准后的误差小于 $5 \times { 1 0 } ^ { - 3 }$ 。

![](images/a26f2df41c83336c6fdb6b319eb391d6686583c862c2570bfcf2e1d524411709.jpg)  
图4K9 玻璃 Mueller矩阵阵元 $M _ { 1 2 }$ ， $M _ { 2 1 }$ ， $M _ { 3 3 }$ ， $M _ { 4 4 }$ 的测量值与理论值的比较 Fig.4Compare the measured value of Mueller matrix $M _ { \scriptscriptstyle 1 2 }$ ， $M _ { 2 1 }$ ， $M _ { 3 3 }$ ， $M _ { 4 4 }$ with the theoretical value

# 2.3对分束镜样品Mueller矩阵的测量

对两块用于 $1 \mathrm { m }$ 太阳望远镜磁场测量的分束镜进行Mueller矩阵测量。一方面可以用准确测量的分束镜Mueller矩阵处理 $1 \mathrm { m }$ 太阳望远镜偏振测量的结果，剔除分束镜的偏振效应造成的起偏和串扰；另一方面，通过比较不同设计下的分束镜的偏振特性，选择起偏和串扰相对较小的方案，以避免起偏和串扰过大对斯托克斯参量 $Q$ ， $U$ ， $V$ 信噪比的减弱。

由于分束镜样品都进行镀膜，其Mueller 矩阵有参数 $P$ ， $s$ 透过比为 $\mathbf { \chi } _ { t }$ ， $P$ ， $s$ 相位延迟差为 $\delta$ ，分束镜透射光的Mueller矩阵为

$$
M ( \iota , \delta ) = \left[ \begin{array} { c c c c c } { 1 } & { \frac { 1 - \iota } { 1 + \iota } } & { 0 } & { 0 } \\ { 1 - \iota } & { 0 } & { 0 } \\ { 1 + \iota } & { 1 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { \frac { 2 \tilde { \iota } \tilde { \iota } } { 1 + \iota } \cos \delta } & { \frac { 2 \tilde { \iota } } { 1 + \iota } \sin \delta } \\ { 0 } & { 0 } & { - \frac { 2 \tilde { \iota } \tilde { \iota } } { 1 + \iota } \sin \delta } & { \frac { 2 \tilde { \iota } \tilde { \iota } } { 1 + \iota } \cos \delta } \end{array} \right] ,
$$

其中， $s$ 方向与斯托克斯参量的 $Q$ 方向平行。

当分束镜的 $s$ 方向与测试系统定义的 $Q$ 方向存在 $\theta$ 夹角时，分束镜Mueller矩阵为

$$
M ( t , \ \delta , \ \theta ) = m _ { \mathrm { r } } ( { \bf \theta } - \theta ) M ( t , \ \delta ) m _ { \mathrm { r } } ( { \bf \theta } \theta )
$$

$$
\begin{array} { r } { \mathbf { \Sigma } } \\ { \mathbf { \Sigma } = \left[ \begin{array} { c c c c c } { 1 } & { B \cos 2 \theta } & { B \sin 2 \theta } & { 0 } \\ { B \cos 2 \theta } & { \cos ^ { 2 } 2 \theta + C \sin ^ { 2 } 2 \theta } & { \frac { 1 - C } { 2 } \sin 4 \theta } & { - D \sin 2 \theta } \\ { B \sin 2 \theta } & { \frac { 1 - C } { 2 } \sin 4 \theta } & { \sin ^ { 2 } 2 \theta + C \cos ^ { 2 } 2 \theta } & { D \cos 2 \theta } \\ { 0 } & { D \sin 2 \theta } & { - D \cos 2 \theta } & { C } \end{array} \right] , } \end{array}
$$

其中, $= \frac { 1 - t } { 1 + t } ; C = \frac { 2 \sqrt { t } } { 1 + t } \cos { \delta } ; D = \frac { 2 \sqrt { t } } { 1 + t } \sin { \delta } ; m _ { \mathrm { r } } ( \theta ) = \frac { 1 } { 2 } \left[ \begin{array} { c c c c } { 1 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { \cos { 2 \theta } } & { \sin { 2 \theta } } & { 0 } \\ { 0 } & { - \sin { 2 \theta } } & { \cos { 2 \theta } } & { 0 } \\ { 0 } & { 0 } & { 0 } & { 1 } \end{array} \right]$ 为坐标旋转矩阵。

下面是对 $1 \mathrm { m }$ 太阳望远镜的一块 $1 : 9$ 的分束镜 $A$ 进行Mueller矩阵测量的结果。

$$
M _ { \mathrm { A } } = \left[ \begin{array} { c c c c c } { { 1 } } & { { - 0 . 0 7 2 9 } } & { { 0 . 0 0 1 2 } } & { { 0 . 0 0 1 7 } } \\ { { - 0 . 0 7 2 0 } } & { { 1 . 0 0 3 8 } } & { { 0 . 0 0 3 3 } } & { { - 0 . 0 0 2 7 } } \\ { { 0 . 0 0 3 7 } } & { { - 0 . 0 0 3 4 } } & { { 0 . 9 8 9 8 } } & { { - 0 . 1 2 7 2 } } \\ { { - 0 . 0 0 2 0 } } & { { 0 . 0 0 2 1 } } & { { 0 . 1 2 7 8 } } & { { 0 . 9 8 8 6 } } \end{array} \right]
$$

对应的 $P$ ， $s$ 透过比 $t = 1 . 1 5 6$ ; $P$ ， $s$ 相位延迟差 $\delta \mathrm { = } - 7 . 3 5 ^ { \circ }$ ; $s$ 方向与测试系统 $Q$ 轴的夹角 $\theta = - 0 . 6 4 ^ { \circ }$ 。经过进一步偏振优化设计后的分束镜 $B$ 的 Mueller 矩阵

$$
M _ { \mathrm { B } } = \left[ \begin{array} { c c c c } { { 1 } } & { { 0 . 0 0 1 5 } } & { { - 0 . 0 0 5 8 } } & { { - 0 . 0 0 0 9 } } \\ { { 0 . 0 0 1 8 } } & { { 0 . 9 9 9 3 } } & { { 0 . 0 0 8 1 } } & { { 0 . 0 1 5 1 } } \\ { { - 0 . 0 0 3 5 } } & { { - 0 . 0 1 0 2 } } & { { 0 . 9 9 0 4 } } & { { 0 . 1 3 2 5 } } \\ { { 0 . 0 0 1 2 } } & { { - 0 . 0 1 1 4 } } & { { - 0 . 1 3 2 9 } } & { { 0 . 9 9 1 5 } } \end{array} \right]
$$

对应的 $P$ ， $s$ 透过比 $t = 1 . 0 0 4$ ; $P$ ， $s$ 相位延迟差 $\delta \mathrm { = } - 7 . 6 7 ^ { \circ }$ ; $s$ 方向与测试系统 $Q$ 轴的夹角 $\theta { = } 2 . 8 7 ^ { \circ }$ 。

由于太阳偏振信号 $Q$ ， $U$ ， $V$ 相对光强 $I$ 比较弱，所以在对太阳进行偏振测量时首先要尽量避免仪器的起偏效应 $( I { \stackrel { } {  } } Q , \ U , \ V )$ ，其次避免仪器造成的 $Q$ ， $U$ ， $V$ 之间的串扰。比较分束镜 $A$ 和 $B$ 的Mueller矩阵测量结果，可以发现经过偏振优化后的分束镜对起偏效应有了很好抑制，将 $I$ 对 $Q$ ， $U$ 的起偏由原先的 $7 \%$ 左右降到 $0 . 5 \%$ 以下。

# 2.4测量系统的系统误差和随机误差

本文对误差的处理方式如1.3节中所述，分析用空气矩阵 $M _ { \mathrm { { c } } }$ 进行校准后的误差。用(5)式求解近似的误差如下：

$$
\begin{array} { r } { \Delta M _ { \mathrm { s } } = \left( \Delta x \Delta p - \Delta p \Delta x \right) \left( E + \Delta s \right) { M _ { \mathrm { c } } } ^ { - 1 } } \\ { = \left( \Delta x \Delta p - \Delta p \Delta x \right) \left( E + \Delta p \right) ^ { - 1 } , } \end{array}
$$

其中， $\Delta x$ 为测量样品的偏振程度，样品偏振特性越弱， $\Delta x$ 越接近0； $\Delta p$ 为偏振分析器相对理想情形的偏差，偏差越小， $\Delta p$ 越接近0。

由2.1节 $M _ { \mathrm { c } }$ 的测量结果可知，当 $\Delta s = 0$ 时， $\Delta p$ 取最大值为

$$
\Delta p _ { \mathrm { m a x } } = \left[ \begin{array} { c c c c c } { { 0 } } & { { - 0 . 0 0 3 4 } } & { { 0 . 0 1 7 5 } } & { { 0 . 0 0 0 9 } } \\ { { - 0 . 0 0 1 8 } } & { { 0 . 0 0 4 3 } } & { { - 0 . 0 0 3 9 } } & { { - 0 . 0 0 2 9 } } \\ { { - 0 . 0 1 9 6 } } & { { 0 . 0 0 0 9 } } & { { 0 . 0 0 5 0 } } & { { - 0 . 0 0 0 5 } } \\ { { 0 . 0 0 0 7 } } & { { 0 . 0 0 3 5 } } & { { 0 . 0 0 0 7 } } & { { 0 . 0 0 0 8 } } \end{array} \right] ,
$$

结合2.2和2.3中测量样品 $\Delta x$ 的最大值可以得出：

$$
\Delta M _ { \mathrm { s } } ~ < ~ ( \Delta x _ { \mathrm { m a x } } \Delta p _ { \mathrm { m a x } } - \Delta p _ { \mathrm { m a x } } \Delta x _ { \mathrm { m a x } } ) ( E + \Delta p _ { \mathrm { m a x } } ) ^ { - 1 } .
$$

上式近似的最大误差：

$$
\left[ { \begin{array} { c c c c } { - 0 . 0 0 0 3 } & { - 0 . 0 0 0 4 } & { 0 . 0 0 0 7 } & { 0 . 0 0 0 3 } \\ { 0 . 0 0 0 4 } & { 0 . 0 0 0 2 } & { - 0 . 0 0 2 0 } & { - 0 . 0 0 0 1 } \\ { 0 . 0 0 0 3 } & { - 0 . 0 0 2 2 } & { 0 . 0 0 0 1 } & { 0 } \\ { 0 . 0 0 0 4 } & { 0 } & { 0 } & { 0 } \end{array} } \right] .
$$

即针对2.2和2.3中的测量样品，使用(5)式求解的近似误差 $\Delta M _ { \mathrm { s } } { < } 2 \times 1 0 ^ { - 3 }$ （204号

测量系统测得的Mueller矩阵的随机误差可由光强的随机误差得到，图5为实验前对光强进行稳定性测量的结果，光强的均方根值为 $5 \times { 1 0 } ^ { - 4 }$ ，且光强稳定后，强度随时间变化小于 $3 \times 1 0 ^ { - 4 } / \mathrm { m i n }$ 。在一个测量周期( $2 ~ \mathrm { m i n } \dot { }$ )内，光强的随机误差 $\frac { \delta I } { I } = 6 \times 1 0 ^ { - 4 }$ 。

![](images/98e975041f4eb4d94a38ab7e7ec3c55ee50d6ba387dca58797e26b6aae5a7fe1.jpg)  
图5光强随时间的稳定性(a）和光强的随机起伏（b) Fig.5The stability of light intensity over time(a）and random fluctuation of light intensity（b)

由（3)式可得，测得Mueller的第 $( i , j )$ 个阵元可表示为

$$
M ( i , j ) = k _ { 1 1 } ( i , j ) I _ { 1 1 } + k _ { 1 2 } ( i , j ) I _ { 1 2 } + \cdots + k _ { 8 8 } ( i , j ) I _ { 8 8 } ,
$$

其中，i, $j = 1$ ，2，3，4; $k _ { 1 1 } ( i , j )$ ， $k _ { 1 2 } ( i , j )$ ，…， $k _ { 8 8 } ( i , j )$ 根据 $P _ { 8 , 4 }$ 和 $S _ { 4 , 8 }$ 计算得到； $I _ { 1 1 } , I _ { 1 2 } , \cdots , I _ { 8 8 }$ 为光强矩阵 $I _ { 8 , 8 }$ 的各个阵元。

根据随机误差传递公式可得

$$
\delta M ( i , j ) ^ { 2 } = \big [ k _ { \scriptscriptstyle { 1 1 } } ( i , j ) \delta I _ { \scriptscriptstyle { 1 1 } } \big ] ^ { \scriptscriptstyle 2 } + \big [ k _ { \scriptscriptstyle { 1 2 } } ( i , j ) \delta I _ { \scriptscriptstyle { 1 2 } } \big ] ^ { \scriptscriptstyle 2 } + \cdots + \big [ k _ { \scriptscriptstyle { 8 8 } } ( i , j ) \delta I _ { \scriptscriptstyle { 8 8 } } \big ] ^ { \scriptscriptstyle 2 } ,
$$

其中， $\delta { \cal I } _ { 1 1 }$ ， $\delta { { I } _ { 1 2 } }$ ，…， $\delta { { I } _ { 8 8 } }$ 为光强矩阵 $I _ { 8 , 8 }$ 的随机误差。

由(12)式及 $I _ { { \mathrm { 8 } } , 8 } , \ { \frac { \delta I } { I } }$ ， $P _ { 8 , 4 }$ 和 $S _ { 4 , 8 }$ 计算可得，光强的随机误差传递到 Mueller矩阵上的随机误差 $\delta M$ ：

$$
{ \delta { \cal M } } = \left[ \begin{array} { c c c c c } { { 0 . 0 0 0 5 } } & { { 0 . 0 0 0 3 } } & { { 0 . 0 0 0 3 } } & { { 0 . 0 0 0 6 } } \\ { { 0 . 0 0 0 3 } } & { { 0 . 0 0 0 2 } } & { { 0 . 0 0 0 2 } } & { { 0 . 0 0 0 4 } } \\ { { 0 . 0 0 0 3 } } & { { 0 . 0 0 0 2 } } & { { 0 . 0 0 0 2 } } & { { 0 . 0 0 0 4 } } \\ { { 0 . 0 0 0 6 } } & { { 0 . 0 0 0 4 } } & { { 0 . 0 0 0 4 } } & { { 0 . 0 0 0 8 } } \end{array} \right] .
$$

实验中对空气Mueller矩阵 $M _ { \mathrm { c } }$ 进行20组测量的标准差为

$$
M _ { \mathrm { s t d } } = \left[ \begin{array} { c c c c } { 0 } & { 0 . 0 0 0 2 } & { 0 . 0 0 0 2 } & { 0 . 0 0 0 2 } \\ { 0 . 0 0 0 1 } & { 0 . 0 0 0 2 } & { 0 . 0 0 0 3 } & { 0 . 0 0 0 7 } \\ { 0 . 0 0 0 3 } & { 0 . 0 0 0 5 } & { 0 . 0 0 0 6 } & { 0 . 0 0 0 4 } \\ { 0 . 0 0 0 2 } & { 0 . 0 0 0 3 } & { 0 . 0 0 0 3 } & { 0 . 0 0 0 1 } \end{array} \right] .
$$

由误差传递计算的结果及实验测得结果可得，随机误差对Mueller矩阵测量结果的影响小于 ${ { 1 0 } ^ { - 3 } }$ 。

Mueller矩阵系统使用空气矩阵 $M _ { \mathrm { { c } } }$ 校准后，系统误差 $\Delta M < 2 \times 1 0 ^ { - 3 }$ ，随机误差 $\delta M < { 1 0 } ^ { - 3 }$ 。在2.2节中，对K9平板玻璃的测量值与理论值的偏差在 $5 \times { 1 0 } ^ { - 3 }$ 以内。综合考虑，本套测量系统用于文中样品的测量误差小于 $5 \times { 1 0 } ^ { - 3 }$ 。

由于空气Mueller矩阵校准法用(5)式中的近似，因此，仅适用于对弱偏振器件的Mueller 矩阵测量，对起偏和延迟效应小于 $10 \%$ 的样品的测量能达到 $5 \times { 1 0 } ^ { - 3 }$ 以内的测量精度。

# 3总结

本文以测量 $1 \mathrm { ~ m ~ }$ 太阳望远镜分束镜的 Mueller矩阵为出发点，使用空气Mueller矩阵校准法对Mueller矩阵测量结果进行校准，将Mueller矩阵测量精度由 $2 \%$ 提高到 $5 \times { 1 0 } ^ { - 3 }$ 。比较了标准样品K9平板玻璃的Mueller矩阵测量结果与理论值间的差别，并运用该测量系统对 $1 \mathrm { ~ m ~ }$ 太阳望远镜偏振测量中的分束镜进行了准确测量，比较了经过偏振优化的分束镜与未经过偏振优化的分束镜之间的差别和影响，这对 $1 \mathrm { m }$ 太阳望远镜的偏振测量以及分束镜方案的优化是必不可少的。

使用空气Mueller矩阵校准法后，Mueller矩阵测量系统的测量精度初步满足对弱偏振器件的偏振特性的测量。如果需要进行更高精度的测量和定标，则需要在测量系统中使用更标准的偏振片和波片，并且提高光源的稳定性。

# 参考文献：

[1] 刘煜，张洪起，包曙东．太阳磁场观测研究［J]．天文学进展，2001，19(1）：34-44. Liu $\mathrm { Y } \mathbf { u }$ ，Zhang Hongqi，Bao Shudong. A research on observation of solar magnetic field[J]. Progress in Astronomy，2001，19(1）:34-44.   
[2] Van Noort M J,Rouppe van der Voort L H M. Stokes imaging polarimetry using image restoration at the Swedish 1-m Solar Telescope [J]. Astronomy& Astrophysics，2008,489(1）: 429-440.   
[3] Cao Wenda，Jing Ju，Ma Jun，et al. Diffraction-limited polarimetry from the Infrared Imaging Magnetograph at Big Bear Solar Observatory [J].Publications of the Astronomical Society of the Pacific，2006，118(844) : 838-844.   
[4] Lagg A，Solanki S K，Doerr HP，et al.Probing deep photospheric layers of the quiet Sun with high magnetic sensitivity [J]. Astronomy & Astrophysics，2016，596：1-13.   
[5] Bai X Y，Deng Y Y，Teng F，et al.Improved magnetogram calibration of Solar Magnetic Field Telescope and its comparison with the Helioseismic and Magnetic Imager [J]. Monthly Notices of the Royal Astronomical Society，2014，445(1） : 49-55.   
[6] Qu Z Q，Zhang X Y， Chen X K，et al. A solar Stokes spectrum telescope [J]. Solar Physics, 2001，201(2):241-251.   
[7] 梁红飞，苏同卫，赵海娟.太阳 Stokes 光谱望远镜的结构及其数据处理方法［J].天文研究 与技术——国家天文台台刊，2007，4(3)：249-257. Liang Hongfei，Su Tongwei， Zhao Haijuan. Structure and data processing of the solar Stokes spectral telescope［J].Astronomical Research & Technology—Publications of National Astronomical Observatories of China，2007，4(3）：249-257.   
[8] Liu Zhong，Xun Jun，Gu Bozhong，et al.New vacuum solar telescope and observations with high resolution [J]. Research in Astronomy and Astrophysics，2014，14(6）:705-718.   
[9] LandiDegl'Innocenti E.Generation and transfer of polarized radiation in the solar atmosphere : physical mechanisms and magnetic-field diagnostic [C]//NASA Conference Publication.1985: 279-299.   
[10] Yuan S.Polarization model for the New Vacuum Solar Telescope [C]// ASP Conference Series. 2014.   
[11] Skumanich A，Lites B W，Martinez P V，et al. The calibration of the Advanced Stokes Polarimeter［J].The Astrophysical Journal Supplement，2009，110(2）：357-380.   
[12] Beck C，Schlichenmaier R，Collados M，et al.A polarization model for the German Vacuum Tower Telescope from in situ and laboratory measurements [J].Astronomy & Astrophysics, 2005，443(3): 1047-1053.   
[13] Smith M H. Optimizing a dual-rotating-retarder Muellr matrix polarimeter [C]// International Symposium on Optical Science and Technology. 2002.   
[14] Ichimoto K，Shinoda K，Yamamoto T,et al.Photopolarimetric measurement system of Mueller matrix with dual rotating waveplates ［J].Publications of the National Astronomical Observatory of Japan，2006,9(1-2)：11-19.   
[15] 侯俊峰，王东光，邓元勇，等.基于最小二乘拟合的波片相位延迟测量［J]．光学学报， 2011,31(8):104-109. Hou Junfeng，Wang Dongguang，Deng Yuanyong，et al. Phase retardation measurement with least square fiting method [J].Acta Optica Sinica，2011，31(8）：104-109.   
[16] 侯俊峰.偏振分析器的高精度偏振定标方法研究及其应用［D]．北京：中国科学院大学， 2013.

# Calibration of Mueller Matrix Measurement of Weak Polarization Element and Its Application

Peng Jianguo $^ { 1 , 2 }$ ，Yuan Shu’， Jin Zhenyul (1.Yunnan Observatories，Chinese Academy of Sciences，Kunming 65ool1,China,Email；yuanshu@ynao.ac.cn; 2.University of Chinese Academy of Sciences，Beijing1OoO49，China）

Abstract：Synchronous reconstruction technology has been used in High-resolution magnetograph of New Vacuum Solar Telescope，which uses the beam splitter.The beam splitter is designed to reduce the polarization effct，but still inevitably affcts the polarization measurement of the solar magnetic field，therefore，the measurement of the polarization characteristics of the beam splitter is necessary for NVST's polarimeter.Inthis paper，Mueller matrix of air is used to calibrate the measured Mueller matrix result of samples，and two beam spliter samples are measured in this method.The Mueler matrix of diferent beam splitters and their influences on the polarization measurement are compared.The Mueler matrix of the flat glass is measured，which varies with the incident angle,and the deviation between the measured result and the theoretical value is compared. The accuracy of the Mueller matrix measurement system is $5 \times { 1 0 } ^ { - 3 }$ after the air Mueller matrix has been used for calibration.

Key words：Polarized optics；Polarization characteristics of beam spliter；Mueller matrix measurement of weak polarization element；Calibration using Mueller matrix of air