# 对不可压缩两相渗流在突变界面处连接条件的辨析与重建

彭小龙」朱苏阳」王超文」梁保升²邓鹏1,贾春生1(1.西南石油大学油气地质及开发工程国家重点实验室；610500；2.University of Texas at Austin;3.加拿大卡尔加里大学)

【摘要】真实油气藏几乎都有突变界面，建立相应的渗流数学模型，其关键是突变界面处的连接条件。已有的渗流理论已确定根据质量守恒定律，在突变界面处各相渗流速度和压力都连续（CPVCM）。但通过调研文献发现： $\textcircled{1}$ 根据CPVCM推断的突变界面两侧的流体饱和度分布存在实际的反例； $\textcircled{2}$ 在驱替前缘，CPVCM与Rankine-Hugoniot跃变条件矛盾； $\textcircled{3}$ 由它推导出的数值计算格式被油藏数值模拟证明会出现非物理结果而被弃用。继而回了文献根据质量守恒方程推导CPVCM的过程，发现这些推导过程最终都出现指代错位，即用界面上同一质点的流速代表了界面两侧不同质点的流速，实质上预置了渗流速度连续，属于自证。接着以不可压缩流体为例，同样根据质量守恒定律和两相流达西公式推导出各相流速和压力都不连续的界面条件（JPVCM），从而建议不可压缩两相渗流应将上游权函数和总流速相等作为突变界面处的连接条件。

关键词：突变界面；界面条件；两相流；多孔介质；质量守恒（国家面上自然科学基金51474179；国家油气重大专项2016ZX05015 国家油气重大专项2016ZX05066 国家油气重大专项2016ZX05053）

Analyzing and Rebuilding Sharp Interface Conditions for Incompressible Two-Phase Flow in Porous Media Peng,Xiaolongl;Zhu Shuyangl; Wang Chanwenl;Liang Baosheng²； Deng Pengl; Jia Chun-Shengl

(1. Southwest Petroleum University.State Key of Laboratory of Oil and Gas Reservoir Geology and exploration; 2. University of Texas at Austin, U.S. ；3. University of Calgary, Canada)

Almost all the oil or gas reservoirs have sharp interfaces.The key to establish the corresponding mathematical flow modelis to find the reasonable phase pressures and velocities connection conditions at the sharp interfaces.In the existingseepage mechanics theory,it is generally recognized that the velocity and pressre of each phase of fluid are continuous at the sharp interface (named CPVCM). However, we can find that CPVCM contradicts some other multiphase seepage phenomena or theories: (1） The saturation distribution of fluid in the real world does not always obey the fluids distribution rules that CPVCMrequired；(2) Near the flood front, CPVCMconflicts with RankineHugoniot Interface Conditions;（3）It has been proved thatthe formula of phase fluxes acrossthe sharp interface which are derived from CPVCM,harmonic average of transmissibility,possible give non-physical results in some cases,so that they have been replace by single points upstream weighting method(SPU)and other high order method, such as TVD,ENO,WENO et al..Therefore,we retraced the waythat how to derive the CPVCM based on the mass conservation law in the early lectures,and find that the two particles on both sides ofthe interface which mentioned in the interface condition has been misplaced on the same interface， therefore,the proof process is essentially equivalent to preset the continuity of velocity and pressures of each phase and prove they are continuous.Such proof is invalid self-proof.Then,taking the incompressible two-phase fluids flow in the porous media as an example,the interface condition with discontinuous velocity and pressure of each phase (JPVCM) is obtained according to the same laws of massconservation and two-phase Darcy'slaw.Finally,it is suggested that,as for the incompressible two-phase flow in porous media,the jumpconditions shouldbe(1) total velocity of the two phases are equal, (2)the velocity of each phase at the sharp interface adopt the upstream ones.

Keywords: Sharp Interface; Interface Conditions; Multiphase; Porous Media; Mass Conservation

# 1.研究背景(introduce)

油气藏突变界面是指岩石属性、流体分布或性质在某些空间曲面邻近的狭窄区域急剧变化，该空间曲面就是突变界面。突变界在在真实油气藏中广泛存在：储层界面、沉积相界面、断层、裂缝-基岩等跨介质类型跨介质尺度界面、压裂缝/井筒-储层界面；油气藏原始气-油-水界面、注水/气/聚合物/示踪剂的驱替前缘、边底水或气顶锥进界面、流体相变界面。总之，真实油气藏几乎都有突变界面，指导油气藏科学开发，油藏工程理论必须基于反映突变界面特征的渗流数学模型，而建立合理的突变界面条件是其中的关键。

在渗流力学领域自多相渗流力学建立不久[1]，突变界面条件就已建立[2-7]，即：各相流体的渗流速度和流体压力在突变界面处连续（CPVCM）[2,8,9]。数在学上，有突变界面的渗流问题属于典型的Neumann 问题[10]，按理只要建立CPVCM结合连续介质场的渗流理论就足以描述考虑了突变界面的渗流问题。但是，技术调研和文献调研发现CPVCM基本没有具体应用于解决突变界面相关的油藏工程问题，即使这类问题得到解决也与CPVCM没有密切关系，例如：构建油藏数值模拟差分格式、预测驱替前缘位置、计算裂缝-基质窜流量、解释渗吸机理等；并且CPVCM还与诸多渗流现象或理论相矛盾。这不禁令人担忧CPVCM的合理性，反思它的科学性。为此我们对其开展了调研工作，论文内容安排如下：首先在第2节从多个案例剖析CPVCM存在的问题；然后在第3节回溯传统渗流力学为什么由质量守恒定律推导出了CPVCM；第4节以不可压缩两相流为例，仍按质量守恒规律和达西公式，但得到了不同于CPVCM的突变界面条件（记为JPVCM)；最后探讨了多相渗流方程在不连续界面处本应该的连接条件。

# 2.现有突变界面条件存在的问题

突变界面作为油藏的内部界面将油藏分割为多个子区域。描述油藏渗流规律的数学模型包括两部分：（1）描述子区域渗流规律的数学微分方程，因子区域连续，所以它们就是常规连续场的渗流数学微分方程，（2）突变界面的连接条件是将相邻介质的热力学性质联系起来的界面条件，这种关系通常又被称为“跳跃条件"或"突变条件”（JumpConditions）[1]。

![](images/edd05646e00e18649961654042062d7f14fdb9f4f424708bfda5f85dbec43da6.jpg)  
图1突变界面将油藏分割为两个连续的子区域及渗流数学模型  
Fig.1 the sharp interface divides the reservoir into two continuous sub regions

（ $\Gamma$ 表示突变界面； $\Gamma ^ { - }$ 、 $\Gamma ^ { + }$ 无限靠近且平行 $\Gamma$ 的界面；E、F分别处于突变界面两侧的两点； $\Omega _ { \scriptscriptstyle 1 }$ 、 $\Omega _ { 2 }$ 指被突变界面分隔开的两个内部连续的子区域)

根据文献两种突变界面处有界面连续条件[3-7]：

$$
{ \Big [ } \rho _ { \ell } \left( \nu _ { \ell } - \mathbf { w } \right) { \Big ] } \cdot N = 0 \qquad \ell \in \{ n , w \}
$$

式中 $\rho$ 表示由根据微观尺度下流体分布计算得到的平均密度； $\boldsymbol { \nu } _ { \iota }$ 表示 $\ell$ 相流体的流速；w 表示间断界面的移动速度； $\mathrm { ~  ~ N ~ }$ 表示界面的单位法向矢量。下标 $\mathfrak { n }$ 表示非润湿相；w表示润湿相；对于不可压缩流体，密度为常数，公式（1）所示界面条件可化简：

$$
{ \Big [ } { \Big ( } \nu _ { \ell } - \mathbf { w } { \Big ) } { \Big ] } \cdot N = 0 \qquad \ell \in \{ n , w \}
$$

对于空间固定界面 $\scriptstyle \mathbf { W = } 0$ 所以有： $\begin{array} { r } { \left[ \nu _ { \ell } \right] \cdot N = 0 \quad \quad o r \quad \nu _ { \ell } ^ { - } = \nu _ { \ell } ^ { + } \quad \ell \in \left\{ n , w \right\} } \end{array}$

即：各相流体的渗流速度和流体压力在突变界面处连续，为方便表述将公式（1）-（4）记为CPVCM。由CPVCM和达西公式，考虑毛管力和重力作用，可得到压力和毛管力的连接条件[9,12-25]：

$$
\nu _ { \ell } ^ { - } = \nu _ { \ell } ^ { + } , p _ { \ell } ^ { - } = p _ { \ell } ^ { + } , p _ { c } ^ { - } = p _ { c } ^ { + } , \ell \in \{ n , w \}
$$

CPVCM被认为是根据质量守恒定律显然可得的结论，作为重要理论见诸于诸多权威论著，几乎贯穿多相渗流力学的发展历史[9,12-25]。但可发现CPVCM与一些渗流现象和其它的一些渗流理论存在不可调和的矛盾，导致我们对其质疑。

为了突出问题的核心，论文以不可压缩两相渗流为例进行说明，渗流运动方程服从达西定律，考虑重力和毛管力（见公式（5）)：

$$
\begin{array} { c c } { \boldsymbol { \nu } _ { \ell } = - K \boldsymbol { \lambda } _ { \ell } \left( \nabla p _ { \ell } - \rho _ { \ell } g \nabla D \right) } & { \ell \in \left\{ n , w \right\} } \end{array}
$$

其中 $\boldsymbol { D } = \left( 0 , 0 , z \right) ^ { T }$ 。根据 $\mathfrak { n }$ ，w两相流体的质量守恒方程： $\phi \hat { \mathcal { { O } } } _ { t } \boldsymbol { S } _ { \boldsymbol { w } } + \boldsymbol { \nabla } \cdot \boldsymbol { \nu } _ { \boldsymbol { w } } = 0 , \phi \hat { \mathcal { O } } _ { t } \boldsymbol { S } _ { \boldsymbol { w } } + \boldsymbol { \nabla } \cdot \boldsymbol { \nu } _ { \boldsymbol { n } } = 0$ 得到：

$$
\nabla \cdot \left( \nu _ { _ n } + \nu _ { _ w } \right) = 0
$$

并定义：

$$
\begin{array} { c } { { \nu _ { _ t } = \nu _ { _ o } + \nu _ { _ w } , \lambda _ { \ell } = k _ { _ r \ell } / \mu _ { \ell } , \lambda _ { _ t } = \lambda _ { _ n } + \lambda _ { _ w } , f _ { _ w } = \lambda _ { _ w } / \lambda _ { t } , f _ { _ n } = 1 - f _ { _ w } } } \\ { { \Delta \rho = \rho _ { _ w } - \rho _ { _ n } , \overline { { { \rho } } } = f _ { _ w } \rho _ { _ w } + f _ { _ n } \rho _ { _ n } , \overline { { { \lambda } } } = 2 \lambda _ { _ n } \lambda _ { _ w } / \lambda _ { t } , \Delta D = D - D _ { _ { c w n } } } } \end{array}
$$

根据等式（6）可知 $\boldsymbol { \nu } _ { t }$ 在渗流空间为无散场，为连续场，则达西公式也可用 $\nu _ { { } _ { t } } - f _ { { } _ { w } }$ 公式改写为：

$$
\nu _ { { } _ { w } } = f _ { { } _ { w } } \nu _ { { } _ { t } } - G P _ { { } _ { c } } , \nu _ { { } _ { n } } = f _ { { } _ { n } } \nu _ { { } _ { t } } + G P _ { { } _ { c } }
$$

其中：

$$
G P _ { c } = 0 . 5 K \overline { { \lambda } } _ { \scriptscriptstyle w n } \left( \nabla p _ { \scriptscriptstyle c } + \Delta \rho g \nabla D \right)
$$

# 2.1质疑1：在均质储层中CPVCM条件与流体饱和度场的矛盾

不考虑毛管力的一维两相不可压缩流体渗流问题即为 Buckley-Leverete（B-L）模型[26]，该模型能够得到的饱和度和流速场的解析解，解析解显示在驱替前缘流体处含水饱和度和水相流速不连续，如图2所示，显然不符合CPVCM 对各相流速在任何界面处连续的要求。为了解释该矛盾，一些学者提出[15,27]：真实的多孔介质总有毛管力，如果考虑毛管力，驱替前缘出现两种流体的过渡带呈连续分布，B-L 模型只是理想化模型。我们认为通过否定B-L 模型来支持CPVCM的理由非常牵强。首先CPVCM的建模过程，对于是否考虑毛管力没有限定，得到CPVCM的结论与是否考虑毛管力无关，重复CPVCM的推理过程，即使不考虑毛管力同样得出CPVCM，所以B-L模型应当作为CPVCM的反例；其次，B-L模型和CPVCM基于相同的物理模型，基于相同的质量守恒方程、运动方程、状态方程以及定解条件，理应得到相同的数学解，但两者却得出截然不同的突变界面条件，因为B-L通过引入 $\boldsymbol { \nu } _ { { } _ { t } } = \boldsymbol { \nu } _ { { } _ { o } } + \boldsymbol { \nu } _ { { } _ { w } }$ ，将不连续场问题转换为连续场问题，所以B-L更有可信度。我们提供两个即使有毛管力，在也存在流体饱和度间断的直观的反例：

反例1.如图3所示，两块性质相同岩石两种流体按不同饱和度充满孔隙，且平衡分布，然后足够快速地将两块岩石上下叠置，在重力作用和毛管力作用下流体将重新分布建立新的平衡，但新平衡的建立过程需要时间，所以在两块岩石接触的瞬时，界面处流体饱和度的分布是不连续的。

![](images/c4950251dfa1805891b11ec6ce03578b206c401b7a3a5f0af70809b453d481ed.jpg)  
图2Buckley-Leverate模型水驱油前缘饱和度和水相流速示意图  
Fig. 3 Schematic diagram of instantaneous updown contact of two same type of rocks with different water saturation

![](images/66e1b98ca960d3cc40cdc590cce0598bc6ad1ea950c0af9d947733ff516248d4.jpg)  
图3两块含水饱和度不同的相同岩块瞬间上下接触示意图

反例2.如图4所示，我们设计了一个利用均匀球体结合重力制作流体饱和度的突变界面实验，其原理在于均球最小喉道半径相对孔腹半径较大，导致毛管力曲线出现较长水平段。在重力作用下油水界面下端和上端，分别取毛管力曲线水平段的最大值和最小值，油水界面就成为饱和度的突变界面。

![](images/2e517b170851001106071275cd86639666330a604638bc1f07dbc9e57312cdf2.jpg)  
Fig.2 Schematic diagram of water flooding front saturation and water phase velocity of Buckley leverate model   
图4一种制作流体饱和度呈间断分布的实验方法

Fig. 4 an experimental method for making discontinuous fluid saturation field.

第一步：在 $\scriptstyle { \mathrm { t } = 0 }$ 时刻让整个油水系统达到垂向平衡状态，根据公式（8）和（9）有：

$$
\begin{array} { r } { \{ - \overline { { \lambda } } _ { w n } ^ { u p } ( S _ { w } ^ { u p } ) \Big [ \widehat { \partial } _ { z } p _ { c } ( S _ { w } ^ { u p } ) + \Delta \rho g \Big ] = 0  } \\ {  - \overline { { \lambda } } _ { w n } ^ { d n } ( S _ { w } ^ { d n } ) \Big [ \widehat { \partial } _ { z } p _ { c } ( S _ { w } ^ { d n } ) + \Delta \rho g \Big ] = 0 } \end{array}
$$

第二步：在垂向方向给多孔介质区域施加压差，让流体自下往上流动，总的流速 $\nu _ { { } _ { t } } > 0$ ，在开始流动的瞬间，流体饱和度与 $\scriptstyle { t = 0 }$ 时刻相同，毛管力与重力作用仍然平衡，所以根据公式（8）和（9）有：

$$
\begin{array} { r l } & { \nu _ { w } ^ { - } = \nu _ { w } ^ { d n } = f _ { _ w } \left( S _ { _ w } ^ { d n } \right) \nu _ { t } - 0 . 5 K \overline { { \lambda } } _ { w n } \left( S _ { _ w } ^ { d n } \right) \left[ \widehat { \mathcal { O } } _ { z } p _ { c } \left( S _ { _ w } ^ { d n } \right) + \Delta \rho g \right] = f _ { _ w } \left( S _ { _ w } ^ { d n } \right) \nu _ { t } } \\ & { \nu _ { _ w } ^ { + } = \nu _ { w } ^ { u p } = f _ { _ w } \left( S _ { _ w } ^ { u p } \right) \nu _ { t } - 0 . 5 K \overline { { \lambda } } _ { w n } \left( S _ { _ w } ^ { u p } \right) \left[ \widehat { \mathcal { O } } _ { z } p _ { c } \left( S _ { _ w } ^ { u p } \right) + \Delta \rho g \right] = f _ { _ w } \left( S _ { _ w } ^ { u p } \right) \nu _ { t } } \end{array}
$$

由于 $S _ { \boldsymbol { w } } ^ { d n } \neq S _ { \boldsymbol { w } } ^ { u p }$ ，且 $f _ { \scriptscriptstyle w } \left( S _ { \scriptscriptstyle w } \right)$ 随 $S _ { w }$ 单调，所以有：

活塞式驱替按理也是CPVCM的反例。在孔隙尺度上，多相渗流按活塞式驱替的方式流动。为了维护CPVCM[15,27]，一些研究者提0饱和度流体的属于未定义流体，所以它们的压力和渗流速度不存在，所以活塞式驱替不能否定CPVCM。这种解释实际上忽视了常规的连续介质渗流理论采用了0饱和度、0流量的事实；

# 2.2质疑2：在均质储层中CPVCM条件与Rankine-Hugoniot条件的矛盾

两相驱替的渗流问题，属于流体力学的一类激波问题。Rankine-Hugoniot(跳跃)条件(公式(14)）[28]是研究流体力学激波问题的经典理论公式，不妨简称R-H条件。

$$
u _ { s } = \frac { u _ { w } ^ { - } - u _ { w } ^ { + } } { S _ { w } ^ { - } - S _ { w } ^ { + } }
$$

式中： $\boldsymbol { S } _ { \boldsymbol { w } }$ 表示含水体积比； $u _ { s }$ 表示前缘界面的移动速度； $\boldsymbol { u } _ { \iota }$ 表示流体 $\ell$ 真实流速，与渗流速有关系$u _ { \ell } = \nu _ { \ell } / \phi$ 。根据公式（8-9）得到公式（15）[2]。

$$
u _ { w } = \frac { 1 } { \phi } \Big [ f _ { \scriptscriptstyle w } \nu _ { \scriptscriptstyle t } - 0 . 5 K \overline { { \lambda } } _ { \scriptscriptstyle w n } \big ( \hat { \sigma } _ { z } p _ { c } + \Delta \rho g \big ) \Big ]
$$

而按照CPVCM给定的界面条件有： $\left[ { { u } _ { { { w } } } } - { { u } _ { s } } \right] \cdot N = 0$

即

$$
u _ { s } = \frac { u _ { w } ^ { - } + u _ { w } ^ { + } } { 2 }
$$

显然表达式(17)与(14)不一致，说明CPVCM与R-H条件不相符合。

与 CPVCM不同，R-H条件可以描述毛细管或孔隙尺度下的两相活塞式驱替界面的移动，在微观渗流模拟中广泛应用[16,17,19,24,29-35]。

# 2.3质疑3：两块毛管力不同的岩块中CPVCM条件与流体饱和度场的矛盾

岩石物性变化引起的突变界面属于固定界面，但因为毛管力曲线不同，在CPVCM条件限制下，$p _ { c } ^ { - } \left( S _ { w } ^ { - } \right) = p _ { c } ^ { + } \left( S _ { w } ^ { + } \right)$ ，所以流体饱和度必须间断分布。Duijn、Molenaar和Neef建立了两块岩石毛管力不同的突主界面条件[9,36]，以图5为例，有如下结论：（1）突变界面处各相流体的流量续，总流量连续；（2)湿相压力 $p _ { { } _ { w } }$ 连续；（3）在在两块岩块界面处，岩块的毛管力值满足如下关系：

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { p _ { c } ^ { + } \left( S _ { w } ^ { + } \right) = p _ { c } ^ { - } \left( S _ { w } ^ { - } \right) \quad } & { i f \left( S ^ { - } \geq S ^ { * } \right) } \\ { S _ { w } ^ { + } = 0 \quad } & { i f \left( S ^ { - } < S ^ { * } \right) } \end{array} \right. } \end{array}
$$

Van Duijn 等人还讨论了多种类型的毛管力曲线组合（如图6)，在此我们将这组突变条件命名为 Duijn-Molenaar-Nef 突变界面条件，简称 DMN 界面条件。这些组合的区别点在上述（3）点不同[9,36-38]。DMN界面条件在流体平衡状态下可以通过实验室得到验证，也适用更多的毛管曲线组合类型(如图7)，但是包括我们的一些研究者发现它们不适用于描述流体在非平稳状态下的分布[21,39]。当通过技术手段控制流体出现短暂的非平衡分布。方式（1)：首先让两种岩心隔离放置，任意配置每块岩石让流体饱和度$S _ { w } ^ { - } , S _ { w } ^ { + } \in [ S _ { w i } , 1 - S _ { o r } ]$ ( $\boldsymbol { S } _ { w i }$ 束缚水； $S _ { o r }$ 残余油)，但确保 $p _ { \mathrm { c } } ^ { - } \left( S _ { w } ^ { - } \right) \neq p _ { \mathrm { c } } ^ { + } \left( S _ { w } ^ { + } \right)$ ；然后足够迅速地将两块岩心接触，就能突破 DMN 界面条件对流体分布模式的限定；方式(2)利用一些流体的表面张力受磁场影响的性质，利用磁场瞬间完成毛管力曲线的改变，从而让流体由平衡状态瞬间转入非平衡状态。

![](images/672ec11e42904746bac41ce82f2017554bb9c5391b0ffbf24ca1a5cb51a0693b.jpg)  
图5两种不同岩石的5种毛管力曲线组合类型

Fig. 6 Four types of capillary pressure curve compose of two different rocks studied by Van Dujn et al

在 Van Duijn 等人（1995年）的工作之后，所建立的界面条件就被用于油藏数值模拟技术，包括有限体积法和混合有限元法，以提高毛细管压力曲线不同条件下两种岩石界面处的流量精度。研究发现通过引入 DWN 界面条件，执行毛细管平衡，用一个局部非线性系统实现了跨界面流量的计算[40-45]，提高了油藏数值模拟在精度[46-48]和非线性收敛方面的表现[49-51]。表面上这些进步当归功于 DMN[52-54]，似乎可以证明DWN和CPVCM的合理性，但真相并非如此，我们调查文献发现引入总速度-分数流公式 $( \nu _ { t } \ – f _ { w } )$ ，将不连续界面问题转换为连续界面问题才是真正原因[39]。

# 2.4质疑4：CPVCM条件不能用于跨突变界面的流量计算

油藏工程有很多问题需要计算跨突变界面的流量，因为界面突变，需要采用数值方法近似计算。比如油藏数值模拟构建网格界面处的数值流量、动态法测试相渗曲线、示踪剂、多重介质孔隙窜流量计算等等

![](images/328375a61439bcf4af63cace17a19d984da56a66cbfd3f696bd98c730137c761.jpg)  
图6突变界面两侧的微元及它们的主要参数

Fig. 9 Infinitesimal elements on both sides of the mutation interface and their main parameters 以图9为例，并根据CPVCM界面条件（见公式（4)）跨突变界面处 $x _ { \Gamma }$ 的水流量为：

$$
q _ { w } ^ { \Gamma } = q _ { w } ^ { + } = q _ { w } ^ { - } = \frac { p _ { w i } - p _ { w i + 1 } } { \displaystyle \frac { \left( x _ { i + 1 } - x _ { \Gamma } \right) } { A _ { i + 1 } K _ { i + 1 } } + \frac { \left( x _ { \Gamma } - x _ { i } \right) } { A _ { i } K _ { i } \lambda _ { w i } } }
$$

当微元 $i { + } 1$ 中水相饱和度 $S _ { w i + 1 }$ 低于可动水需要的临界饱和度 $S _ { \nu \mathrm { c } }$ ，有 $k _ { r w } ^ { i + 1 } = 0$ ，将其代入公式（19）有$q _ { \scriptscriptstyle { w } } ^ { \Gamma } = 0$ ，说明水无法越过位置 $x _ { \Gamma }$ ，这与驱替过程的物理规律不相符合。CPVCM推导出的数值流量格式本质上是传导率系数的调和平均，在油藏数值拟中被证明是一种失效的方法[55]，所以被单点上游权（SPU)取代，SPU 是目前商业油藏数值模拟软件采用的主要方法。SPU 虽然比CPVCM更合理，但在模拟突变界面渗流问题时，产生很强的数值弥散，误差能够超过 $30 \%$ 以上[56-59]，为此人们又研究了高阶精度方法，包括两点上游加权法[60]、Godunov[61]、TVD，ENO，WENO[62,63]等，虽有改进但改进有限，并非计算突变界面流量的理想方法。因为它们并非针对间断界面条件的严格推导，而是不得已的选择[59]。

用 SPU 和高精度计算格式结合了总速度 $\nu _ { { } _ { t } }$ 公式-分数流 $f _ { \scriptscriptstyle { w } }$ 公式避开了间断界面问题[46-51]，成为当前油藏数值模拟技术发展的主流方法。这促使我们思考用总流速 $\nu _ { { } _ { t } }$ 连续代替CPVCM作为突变界面的处的连接条件。当然用 $\nu _ { _ { w } } - f _ { _ { w } }$ 公式改造从理论上只能用于仅限于不可压缩流体，因为对于不可压缩流体理论上尚未

确定在突变界面处的连续性。

# 3.传统突变界面条件的推理的回溯

质量守恒定律被认为是得出CPVCM的基础，调研文献发现渗流理论文献由质量守恒定律得到CPVCM有三种推理方式：

（1）方式1：根据质量守恒定律，在流动空间取任何包括有突变界面的微元（见图1所示)，有如下的质量守恒方程：

$$
m _ { \ell i n } - m _ { \ell o u t } = m _ { \ell c h g } + m _ { \ell s r c }
$$

式中 $m _ { \it { i n } } \cdot \ m _ { \it { i n } }$ 分别表示表示单位时间内流入和流出微元中流体 $\ell$ 的流量； $m _ { c h g }$ 表示单位时间内微元中的流体 $\ell$ 质量变化量； $m _ { \scriptscriptstyle { \ell s r c } }$ 表示单位时间内微元中由源汇项产生的流体 $\ell$ 质量。传统的渗流力学认为：当微元为面，并且不考虑源汇项，则公式（20）右侧得0，于是有：

$$
\begin{array} { r } { \begin{array} { r c l l } { m _ { \ell i n } = m _ { \ell o u t } } & { o r } & { \rho _ { \ell } q _ { \ell i n } = \rho _ { \ell } q _ { \ell o u t } } \end{array} } \end{array}
$$

对于不可压缩流体，密度不变，所以有：

$$
\begin{array} { r l } { q _ { \ell i n } = q _ { \ell o u t } \quad o r } & { { } \left( A _ { \Gamma } \nu _ { \ell i n } \cdot n _ { 1 } \right) + \left( A _ { \Gamma } \nu _ { \ell o u t } \cdot n _ { 2 } \right) = 0 } \end{array}
$$

所以有

$$
\left[ \nu _ { \ell } \right] = 0 o r \nu _ { \ell } ^ { - } = \nu _ { \ell } ^ { + }
$$

但我们认为，上述推理过程中在利用质量守恒定律推导界面条件的过程中，发生了对象的指代错位，如图10所示：界面条件需要确定界面两侧不同的两个质点 $M ^ { - } , M ^ { + }$ 的速度关系，而不是突变界面 $\Gamma$ 上相同的质点 $\mathbf { M }$ 的自已与自己比较速度；即不能将 $x ^ { - }  x _ { \Gamma }$ ， $x ^ { + }  x _ { \Gamma }$ 当作 $x ^ { - } = x _ { \Gamma } = x ^ { + }$ 或者 $M ^ { - } = M = M ^ { + }$ 不能由 $\nu _ { \scriptscriptstyle \Gamma } \cdot n _ { \scriptscriptstyle \Gamma } - \nu _ { \scriptscriptstyle \Gamma } n _ { \scriptscriptstyle \Gamma } = 0$ 得出 $\nu _ { \scriptscriptstyle w } ^ { - } n _ { \scriptscriptstyle \Gamma } - \nu _ { \scriptscriptstyle w } ^ { + } n _ { \scriptscriptstyle \Gamma } = 0$ （即 $\left[ \nu _ { _ w } \right] = 0$ )。在推理过程中需要始终保守所比较的是两个不同质点的参数，对于不能将有厚度的三维微元极限推理到二维，（或对有厚度的二维微元用极限降维到一维），否则就是预设了 $\boldsymbol { \nu } _ { \ell } ^ { - } = \boldsymbol { \nu } _ { \ell } ^ { \Gamma } , \boldsymbol { \nu } _ { \ell } ^ { + } = \boldsymbol { \nu } _ { \ell } ^ { \Gamma }$ ，再证明 $\nu _ { \ell }$ 在界面处连续就是自证。

![](images/bac482383ed839db72c7387a370d295245d5f4c15959d969a5f35752db17f70b.jpg)  
图7.突变界面两侧的两个不同质点与界面上的质点的区别[39,64];

Fig.10 The two particles on both sides of the sharp interface and the one at the sharp interface[39,64]

（2）方式2：当流体通过没有源汇项的突变界面从一个流动区域 $\Omega _ { \scriptscriptstyle 1 }$ 流向另一个区域 $\Omega _ { 2 }$ （如图1所示)，根据物质不灭原理，从 $\Omega _ { \scriptscriptstyle 1 }$ 流出的量总是等于流入区域 $\Omega _ { 2 }$ 中的流量，所以得出 $\left[ \rho _ { \ell } \nu _ { \ell } \right] = 0$ 或 $\left[ \nu _ { \ell } \right] = 0$ 。

我们认为方式（2）的推理过程同样发生了对象的指代错位：用 $\Omega _ { \scriptscriptstyle 1 }$ 区域在界面 $\Gamma$ 上的质点 $\mathbf { M }$ 的流速代替了 $M ^ { - }$ 的流速，同样用 $\Omega _ { 2 }$ 边界上 $\Gamma$ 的质点 M 的渗流速度代替了 $M ^ { + }$ 的流速。根据质量守恒定律，流体经过 $\Omega _ { \scriptscriptstyle 1 }$ 和 $\Omega _ { 2 }$ 的共同边界 $\Gamma$ 从 $\Omega _ { \scriptscriptstyle 1 }$ 流出的流量 $q _ { \ell \Omega _ { 1 } } ^ { \Gamma }$ 确实必须等于流入 $\Omega _ { 2 }$ 区域的流量 $q _ { \ell \Omega _ { 2 } } ^ { \Gamma }$ ，但这规律只要$\Gamma$ 上任意的流速 $ { \boldsymbol \nu } _ { \ell } ^ { \Gamma }$ 可实现，并不要求 $\nu _ { \ell } ^ { - } = \nu _ { \ell } ^ { \Gamma } = \nu _ { \ell } ^ { + }$ ，如果基于前者就得出后者，实质上同样预置了 $\nu _ { \ell }$ 在突变界面 $\Gamma$ 处连续，然后再自证 $\nu _ { \ell }$ 连续，也是自证。

![](images/a448bbec9a1d21b5280d6b708ad9a967067b1c8ec07e62520ac12b52f85e8244.jpg)  
图8.突变界面可视作每个子区域的外边界的示意图

Fig.8 The inner sharp interface can be regarded as the outer boundary of each sub reg

进一步以图8为例说明：突变界面 $\Gamma$ 既是 $\Omega _ { \scriptscriptstyle 1 }$ 的外边界也是区域 $\Omega _ { 2 }$ 的外边界。假设在 $\mathrm { \ t { < } } 5 \mathrm { { m i n } }$ 时边界按（20 $q _ { w \Omega _ { 2 } } ^ { \Gamma } { = } 6 0 \mathrm { c m } 3 / \mathrm { m i n } .$ $q _ { n \Omega 2 } ^ { \Gamma } { = } 4 0 \mathrm { c m } 3 / \mathrm { m i n }$ 供液让 $\Omega _ { 2 }$ 区域保持与边界相同的稳态流动，然后在 $\scriptstyle \mathrm { t = } 5 \operatorname* { m i n }$ 时，改变产量为 $q _ { w \Omega 2 } ^ { \Gamma } { = } 2 0 \mathrm { c m } 3 / \mathrm { m i n }$ $q _ { n \Omega 2 } ^ { \Gamma } { = } 8 0 ~ \mathrm { c m } 3 / \mathrm { m i n }$ ，注入条件的改变将在 $\Omega _ { 2 }$ 产生驱替前缘，前缘位置为时间的函数，用 $x _ { f } \left( t \right)$ 表示，可以证明对于任意的 $\varepsilon \to 0$ 且 $\varepsilon > 0$ ，总存在足够短时间 $\delta$ ，在 $t = 5 + \delta \big ( \mathrm { m i n } \big )$ 时刻，满足 $x _ { f } \left( t _ { 0 } + \delta \right) < x _ { \Gamma } + \varepsilon = x ^ { + }$ ，即能够确保 $\nu _ { \ell } ^ { \Gamma } \neq \nu _ { \ell } ^ { + }$ ；而另一端 $\Omega _ { \scriptscriptstyle 1 }$ 区域作为 $\Gamma$ 的上游，按 $\Gamma$ 供液的来源，只需令其按 $q _ { w \Omega 1 } ^ { \Gamma }$ 和 $q _ { n \Omega 2 } ^ { \Gamma }$ 相同的流量供液，根据上游权这一物理规律，有 $\boldsymbol \nu _ { \ell } ^ { \Gamma } = \boldsymbol \nu _ { \ell } ^ { - }$ ，所以 $\boldsymbol { \nu } _ { \ell } ^ { - } \neq \boldsymbol { \nu } _ { \ell } ^ { + }$ 。

（3）方式3：以Hassanizadeh和Gray为代表的理论证明方式

以Hassanizadeh和Gray等人的为代表的学者从理论的角度对CPVCM进行了证明，并受到广泛引用[23,24,65]。与方式（1-2）的推理方式不同，他们的推导过程中严格遵守了 $x ^ { - }$ 和 $x ^ { + }$ 指向不同的质点。但我们发现在其证明过程中没有考虑到微元厚度b改变（垂直于突变界面方向，如图1所示）将影响微元的平均饱和度 $S _ { \ell }$ ，即 $b S _ { \ell }$ 应为非0常数，所以不能得出：

$$
\operatorname * { l i m } _ { b  0 } \frac { \partial } { \partial t } \big ( b \langle \rho \rangle _ { _ { \ell } } \phi S _ { \ell } \big ) = 0
$$

进而不能得出 $\boldsymbol { \nu } _ { \ell } ^ { - } = \boldsymbol { \nu } _ { \ell } ^ { + }$ 。详细过程请参考原文献[5,6,11,12]，以及Peng 等人（2019）对其做的核对[39]。

总之通过文献追踪和分析，我们认为传统渗流力学在用质量守恒方程推导突变界面条件中将界面上的流速假设为界面两侧的流速，通过自证的方式建立了CPVCM，是不合理的。

# 4.突变界面条件的重新建立

本节我们仍然根据质量守恒定律和两相流达西公式建立突变界面条件。在前期我们针对一维问题开展了研究[39,64]，在此进一步扩展到三维。

# 4.1跨突变界面的总流量及各相流量计算

如图1所示，油藏被突变界面 $\Gamma$ 分割为两个连续子区域 $\Omega _ { \scriptscriptstyle 1 }$ 、 $\Omega _ { 2 }$ 。界面 $\Gamma ^ { - }$ 、 $\Gamma ^ { + }$ 在 $\Gamma$ 两侧并与 $\Gamma$ 平行而且无限靠近 $\Gamma$ 。在突变界面 $\Gamma$ 两侧取两点 $X ^ { \alpha } \left( x ^ { \alpha } , y ^ { \alpha } , z ^ { \alpha } \right)$ 和 $X ^ { \beta } \left( \boldsymbol { x } ^ { \beta } , \boldsymbol { y } ^ { \beta } , z ^ { \beta } \right)$ ，两点连线记为 $l _ { \alpha \beta }$ ，$X ^ { \Gamma } \left( x ^ { \Gamma } , y ^ { \Gamma } , z ^ { \Gamma } \right)$ 为 $l _ { \alpha \beta }$ 与突变界面 $\Gamma$ 的交点； $X ^ { - } \left( x ^ { - } , y ^ { - } , z ^ { - } \right)$ 为 $l _ { \alpha \beta }$ 与 $\Gamma ^ { - }$ 的交点， $X ^ { + } \left( x ^ { + } , y ^ { + } , z ^ { + } \right)$ 为 $l _ { \alpha \beta }$ 与 $\Gamma ^ { + }$ 的交点，显然有 $X ^ { - }  X ^ { \Gamma }$ ， $X ^ { + }  X ^ { \Gamma }$ 。要求 $X ^ { \alpha }$ 和 $X ^ { \beta }$ 满足条件：线段 $l _ { \alpha \beta }$ 与 $\Gamma$ 法线方向相同;线段 $l _ { \alpha \beta }$ 长度大于线段 $X ^ { - } X ^ { + }$ ； $X ^ { \alpha }$ 和 $X ^ { \beta }$ 不能与 $X ^ { \Gamma }$ 相隔太远，以确保线段 $E X ^ { - }$ 和 $F X ^ { + }$ 流速、饱和度、毛管力和压力梯度足够相近。根据(25-a)得到 $\nabla \cdot \boldsymbol { \nu } _ { t } = 0$ ，即 $\nu _ { { } _ { t } }$ 在整个渗流场为无散场或保守场。由公式（5）得到两相总流速运动方程：

$$
\nu _ { t } = \nu _ { n } + \nu _ { w } = - K \lambda _ { t } \left( \nabla p _ { n } - f _ { w } \nabla p _ { c } - \overline { { \rho } } g \nabla D \right)
$$

引入全拟压力（global pressure）的概念[66,67].

$$
\Phi = p _ { n } + \int _ { S _ { w } } ^ { 1 } f _ { w } \left( \varsigma \right) \frac { \hat { \upsilon } p _ { c } \left( \varsigma \right) } { \hat { \upsilon } \varsigma } d \varsigma
$$

将（26）代入等式（25）得并对等式两端做 $X ^ { \alpha } X ^ { \beta }$ 线积分：

$$
\int _ { X ^ { \alpha } } ^ { X ^ { \beta } } { \frac { \nu _ { t } } { - K \lambda _ { t } } } \cdot d l = \int _ { X ^ { \alpha } } ^ { X ^ { \beta } } { \bigl ( } \nabla \Phi - { \bar { \rho } } g \nabla D { \bigr ) } \cdot d l
$$

根据 $\boldsymbol { \nu } _ { t }$ 无散场的连续性质， $X ^ { \alpha }$ 和 $X ^ { \beta }$ 足够近的条件下， $l _ { \alpha \beta }$ 线段上 $\nu _ { { } _ { t } }$ 近似相等，所以等式（27）左侧 $\boldsymbol { \ V } _ { t }$ 可置于积分符号外，用 $n _ { \alpha \beta }$ 表示沿 $l _ { \alpha \beta }$ 的单位矢量。所以得到：

$$
\begin{array} { r } {  { ( \nu _ { t } \cdot n _ { \alpha \beta } ) = \frac { \Phi ^ { \beta } - \Phi ^ { \alpha } + \overline { { \rho } } g ( D ^ { \beta } - D ^ { \alpha } ) } { \int _ { X ^ { \alpha } } ^ { X ^ { \Gamma } } \displaystyle \frac { d l } { - K ^ { \alpha } \lambda _ { t } ^ { \alpha } } + \int _ { X ^ { \Gamma } } ^ { X ^ { \beta } } \displaystyle \frac { d l } { - K ^ { \beta } \lambda _ { t } ^ { \beta } } } } } \end{array}
$$

由于 $l _ { \alpha \beta }$ 和界面 $\Gamma$ 的法线方向一致，所以 $n _ { \alpha \beta } = n _ { \Gamma }$ 所以跨突变界面的总流量：

$$
q _ { t } ^ { \Gamma } = \nu _ { t } ^ { \alpha \beta } A _ { \Gamma } = \left( \nu _ { t } \cdot n _ { \Gamma } \right) A _ { \Gamma } = \frac { A _ { \Gamma } \Big [ \Phi ^ { \beta } - \Phi ^ { \alpha } + \overline { { \rho } } g \left( D ^ { \beta } - D ^ { \alpha } \right) \Big ] } { \displaystyle \int _ { X ^ { \alpha } } ^ { X ^ { \Gamma } } \frac { d l } { - K ^ { \alpha } \lambda _ { t } ^ { \alpha } } + \int _ { X ^ { \Gamma } } ^ { X ^ { \beta } } \frac { d l } { - K ^ { \beta } \lambda _ { t } ^ { \beta } } }
$$

由公式（28）可计算在 $X ^ { - }$ 和 $X ^ { + }$ 处各相渗流沿 $\Gamma$ 法线方向的渗流速度：

$$
\left\{ \begin{array} { l l } { { \nu _ { w } ^ { - } = f _ { w } ^ { \alpha } \nu _ { t } - G P _ { c } ^ { a } } } & { { \nu _ { n } ^ { - } = f _ { n } ^ { \alpha } \nu _ { t } + G P _ { c } ^ { a } } } \\ { { \nu _ { w } ^ { + } = f _ { w } ^ { \beta } \nu _ { t } - G P _ { c } ^ { \beta } } } & { { \nu _ { n } ^ { + } = f _ { n } ^ { \beta } \nu _ { t } + G P _ { c } ^ { \beta } } } \end{array} \right.
$$

比较公式（30）中4项，可发现一般情况下突变界面两侧各相渗流速度并不相等：

$$
{ \nu _ { w } } ^ { - } \ne \nu _ { w } ^ { + } , { \nu _ { n } } ^ { - } \ne { \nu _ { n } ^ { + } }
$$

如何确定突变界面 $\Gamma$ 上各相渗流速度则根据流体力学的上游权法则，所以有：

$$
\nu _ { \ell } ^ { \Gamma } = u p s t r e a m \Big ( \nu _ { \ell } ^ { - } , \nu _ { \ell } ^ { + } \Big ) = i f \Big ( \widehat { \Phi } ^ { - } > \widehat { \Phi } ^ { + } ; \nu _ { \ell } ^ { - } ; \nu _ { \ell } ^ { + } \Big ) \quad \ell \in \Big \{ n , w \Big \}
$$

$$
\widehat { \Phi } = \Phi + \overline { { \rho } } g \Delta D = \int _ { S _ { w } } ^ { 1 } f _ { w } \left( \zeta \right) \frac { \widehat { \sigma } p _ { c } \left( \varsigma \right) } { \widehat { \sigma } \varsigma } d \varsigma + \left( f _ { w } \rho _ { w } + f _ { n } \rho _ { n } \right) g \Delta D
$$

所以跨突变界面的各相流量为：

$$
\begin{array} { r l } & { q _ { w } ^ { \Gamma } = \nu _ { w } ^ { \Gamma } \cdot n _ { \Gamma } A _ { \Gamma } = i f \left( \hat { \Phi } ^ { \alpha } > \hat { \Phi } ^ { \beta } ; f _ { w } ^ { \alpha } q _ { t } ^ { \Gamma } - A _ { \Gamma } \hat { \mathcal { O } } _ { l _ { a \beta } } G P _ { c } ^ { \alpha } ; f _ { w } ^ { \beta } q _ { t } ^ { \Gamma } - A _ { \Gamma } \hat { \mathcal { O } } _ { l _ { a \beta } } G P _ { c } ^ { \beta } \right) } \\ & { q _ { n } ^ { \Gamma } = \nu _ { n } ^ { \Gamma } \cdot n _ { \Gamma } A _ { \Gamma } = i f \left( \hat { \Phi } ^ { \alpha } > \hat { \Phi } ^ { \beta } ; f _ { n } ^ { \alpha } q _ { t } ^ { \Gamma } + A _ { \Gamma } \hat { \mathcal { O } } _ { l _ { a \beta } } G P _ { c } ^ { \alpha } ; f _ { n } ^ { \beta } q _ { t } ^ { \Gamma } + A _ { \Gamma } \hat { \mathcal { O } } _ { l _ { a \beta } } G P _ { c } ^ { \beta } \right) } \end{array}
$$

# 4.3跨突变界面的处压力的分布

根据等式(28)很容易证明全拟压力（globalpressure）在突界面处连续。即：

$$
\operatorname * { l i m } _ { X ^ { - }  X ^ { \Gamma } } \Phi ^ { - } = \Phi ^ { \Gamma } = \operatorname * { l i m } _ { X ^ { + }  X ^ { \Gamma } } \Phi ^ { + }
$$

说明由等式(26)所定义的全拟压力（globalpressure）在突界面处连续。

分别用用 $X ^ { \alpha }$ 和 $X ^ { \Gamma }$ 两点、 $X ^ { \beta }$ 与 $X ^ { \Gamma }$ 两点按(28)式计算总流速在线段 $l _ { \alpha \beta }$ 方向分量 $\left( \nu _ { t } \cdot n _ { \alpha \beta } \right)$ 并联立求解可 $\Gamma$ 处的全拟压力 $\Phi ^ { \Gamma }$ ：

$$
\Phi ^ { \Gamma } = \frac { \displaystyle \int _ { X ^ { \Gamma } } ^ { X ^ { \beta } } \frac { d l } { K ^ { \beta } \lambda _ { t } ^ { \beta } } } { \displaystyle \int _ { X ^ { \alpha } } ^ { X ^ { \Gamma } } \frac { d l } { K ^ { \alpha } \lambda _ { t } ^ { \alpha } } + \int _ { X ^ { \Gamma } } ^ { X ^ { \beta } } \frac { d l } { K ^ { \beta } \lambda _ { t } ^ { \beta } } } \Big ( \Phi ^ { \alpha } + \overline { { { \rho } } } g \left( D ^ { \alpha } - D ^ { \Gamma } \right) \Big )
$$

$$
+ \frac { \displaystyle { \int _ { X ^ { \alpha } } ^ { X ^ { \Gamma } } \frac { d l } { K ^ { \alpha } \lambda _ { t } ^ { \alpha } } } } { \displaystyle { \int _ { X ^ { \alpha } } ^ { X ^ { \Gamma } } \frac { d l } { K ^ { \alpha } \lambda _ { t } ^ { \alpha } } + \int _ { X ^ { \Gamma } } ^ { X ^ { \beta } } \frac { d l } { K ^ { \beta } \lambda _ { t } ^ { \beta } } } } \Big ( \Phi ^ { \beta } + \overline { { { \rho } } } g \left( D ^ { \beta } - D ^ { \Gamma } \right) \Big )
$$

根据（36）和全拟压力的定义公式[66-68]，可计算 $l _ { \alpha \beta }$ 线段上 $X ^ { - }$ 和 $X ^ { + }$ 处的各相压力。

$$
\left\{ \begin{array} { l l } { p _ { w } ^ { - } = \Phi ^ { \Gamma } - \displaystyle \int _ { 1 } ^ { S _ { w } ^ { \alpha } } f _ { w } ^ { \alpha } \left( \varsigma \right) \displaystyle \frac { \hat { c } p _ { c } ^ { \alpha } \left( \varsigma \right) } { \hat { \partial } \varsigma } d \varsigma } & { p _ { n } ^ { - } = \Phi ^ { \Gamma } + \displaystyle \int _ { 1 } ^ { S _ { w } ^ { \alpha } } f _ { n } ^ { \alpha } \left( \varsigma \right) \displaystyle \frac { \hat { c } p _ { c } ^ { \alpha } \left( \varsigma \right) } { \hat { \partial } \varsigma } d \varsigma } \\ { p _ { w } ^ { + } = \Phi ^ { \Gamma } - \displaystyle \int _ { 1 } ^ { S _ { w } ^ { \beta } } f _ { w } ^ { \alpha } \left( \varsigma \right) \displaystyle \frac { \hat { c } p _ { c } ^ { \beta } \left( \varsigma \right) } { \hat { \partial } \varsigma } d \varsigma } & { p _ { n } ^ { + } = \Phi ^ { \Gamma } + \displaystyle \int _ { 1 } ^ { S _ { w } ^ { \beta } } f _ { n } ^ { \beta } \left( \varsigma \right) \displaystyle \frac { \hat { c } p _ { c } ^ { \beta } \left( \varsigma \right) } { \hat { \partial } \varsigma } d \varsigma } \end{array} \right.
$$

根据(36)式可知，当突界面两侧 $\ b { f } _ { \scriptscriptstyle w }$ 、 $p _ { c }$ 等参数不同，得到的 $p _ { { } _ { w } }$ 和 $p _ { n }$ 在界突主面处不连续。 结合公式(29)和(36)形成的突变界面处各相压力和渗流速不连续，由此构成的界面条件不同于CPVCM，为示区别，将其称为JPVCM。

# 4.4突变界面及邻近区域渗流速度的计算

公式(28)只能给出总流体沿方向 $l _ { \alpha \beta }$ 方向的总流速分量。对于一维渗流问题，该分量即为总流速分量，但对于二维和三维渗流问题，还需要确定其它方向的总流速分量。不妨以 $X ^ { \alpha } \left( x ^ { a } , y ^ { \alpha } , z ^ { \alpha } \right)$ 作为局部坐标原点，在界面另一侧选一点 $X ^ { \xi } \left( x ^ { \xi } , y ^ { \xi } , z ^ { \xi } \right)$ ， $X ^ { a } X ^ { \xi }$ 与 $\Gamma$ 的法线同向，另外作两点 $X ^ { \eta } \left( x ^ { \eta } , y ^ { \eta } , z ^ { \eta } \right)$ ，$X ^ { \zeta } \left( x ^ { \zeta } , y ^ { \zeta } , z ^ { \zeta } \right)$ ，并且满足条件： $X ^ { \alpha } X ^ { \xi }$ （记为 $l _ { \alpha \xi }$ ）， $X ^ { \alpha } X ^ { \eta }$ （记为 $l _ { \alpha \eta }$ ）， $X ^ { \alpha } X ^ { \zeta }$ （记为 $l _ { \alpha \zeta }$ ）在空间相互垂直，如果他们与 $\Gamma$ 有交点，记为 $X _ { \alpha \beta } ^ { \Gamma } \left( \beta \in \{ \xi , \eta , \zeta \} \right)$ ，如果没有， $X ^ { \beta } \left( \beta \in \{ \xi , \eta , \zeta \} \right)$ 与 $X ^ { \alpha }$ 位于同一的子区域。

![](images/487af86ef198f71cea3b23baf4de322b0e4739ebd6e1ffd872747d1baae282e0.jpg)  
图9在三维渗流空间计算总流速张量的示意图

Fig.13 schematic diagram of calculating total velocity in three-dimensional porous me(用三次公式（38）计算三个方向的总流速的分量：

$$
\left( \boldsymbol { \nu } _ { t } \cdot \boldsymbol { n } _ { \alpha \beta } \right) = \frac { \Phi ^ { \alpha } - \Phi ^ { \beta } + \overline { { \rho } } g \left( D ^ { \alpha } - D ^ { \beta } \right) } { e \left( X _ { \alpha \beta } ^ { \Gamma } \right) \int _ { X ^ { \alpha } } ^ { X ^ { \Gamma } } \frac { 1 } { K ^ { \alpha } \lambda _ { t } ^ { \alpha } } + e \left( X _ { \alpha \beta } ^ { \Gamma } \right) \int _ { X ^ { \Gamma } } ^ { x ^ { \beta } } \frac { 1 } { K ^ { \beta } \lambda _ { t } ^ { \beta } } + \left( 1 - e \left( X _ { \alpha \beta } ^ { \Gamma } \right) \right) \int _ { X ^ { \alpha } } ^ { x ^ { \beta } } \frac { 1 } { K ^ { \beta } \lambda _ { t } ^ { \beta } } } , \beta \in \{ \boldsymbol { \xi } , \boldsymbol { \eta } , \boldsymbol { \zeta } \}
$$

其中 $e \Big ( X _ { \alpha \beta } ^ { \Gamma } \Big ) = i f \Big ( \exists X _ { \alpha \beta } ^ { \Gamma } ; 1 ; 0 \Big )$ 。再由三个分量组成总流速的张量矩阵（39）：

$$
\nu _ { t } = { \left( \begin{array} { l } { \nu _ { t } ^ { \alpha \xi } } \\ { \nu _ { t } ^ { \alpha \eta } } \\ { \nu _ { t } ^ { \alpha \zeta } } \end{array} \right) } = { \left( \begin{array} { l l l } { \nu _ { t x } ^ { \alpha \xi } } & { \nu _ { t y } ^ { \alpha \xi } } & { \nu _ { t z } ^ { \alpha \xi } } \\ { \nu _ { t x } ^ { \alpha \eta } } & { \nu _ { t y } ^ { \alpha \eta } } & { \nu _ { t z } ^ { \alpha \eta } } \\ { \nu _ { t x } ^ { \alpha \zeta } } & { \nu _ { t y } ^ { \alpha \zeta } } & { \nu _ { t z } ^ { \alpha \zeta } } \end{array} \right) } = { \left( \begin{array} { l l l } { \nu _ { t } ^ { \alpha \xi } n _ { x } ^ { \alpha \xi } } & { \nu _ { t } ^ { \alpha \xi } n _ { y } ^ { \alpha \xi } } & { \nu _ { t } ^ { \alpha \xi } n _ { z } ^ { \alpha \xi } } \\ { \nu _ { t } ^ { \alpha \eta } n _ { x } ^ { \alpha \eta } } & { \nu _ { t } ^ { \alpha \eta } n _ { y } ^ { \alpha \eta } } & { \nu _ { t } ^ { \alpha \eta } n _ { z } ^ { \alpha \eta } } \\ { \nu _ { t } ^ { \alpha \zeta } n _ { x } ^ { \alpha \zeta } } & { \nu _ { t } ^ { \alpha \zeta } n _ { y } ^ { \alpha \zeta } } & { \nu _ { t } ^ { \alpha \zeta } n _ { z } ^ { \alpha \zeta } } \end{array} \right) }
$$

$$
n _ { x } ^ { a \beta } = \frac { x ^ { \beta } - x ^ { a } } { \left| X ^ { a } X ^ { \beta } \right| } , n _ { y } ^ { a \beta } = \frac { y ^ { \beta } - y ^ { a } } { \left| X ^ { a } X ^ { \beta } \right| } , n _ { z } ^ { a \beta } = \frac { z ^ { \beta } - z ^ { a } } { \left| X ^ { a } X ^ { \beta } \right| } , \left( \beta \in \{ \xi , \eta , \zeta \} \right) ,
$$

进一步根据公式(8)可以计算 $X ^ { \alpha }$ 处各相流速。将(38)(38)代入公式(29)可得到界面两侧 $X ^ { - }$ 、 $X ^ { + }$ 各相流速。

# 4.5渗流方程中突变界面条件的重新建立

本节推导JPVCM采用了：(1)总流速连续 $\nabla \cdot \boldsymbol { \nu } _ { t } = 0$ ；（2）界面处的流速取上游权。综合考虑CPVCM存在的问题和 JPVCM的建立过程，我们在多相渗流方程中，连接两个连续子区域的突主界面采用如下的界面条件（见公式40）：

$$
\left\{ \begin{array} { l l } { { \nu _ { \ell } \big \vert _ { \Gamma } = i f \left( \hat { \Phi } ^ { - } \geq \hat { \Phi } ^ { + } ; \nu _ { \ell } ^ { - } ; \nu _ { \ell } ^ { + } \right) } } & { { \quad ( a ) \quad } } \\ { { \nu _ { w } ^ { - } + \nu _ { n } ^ { - } = \nu _ { w } ^ { + } + \nu _ { w } ^ { + } } } & { { \quad ( b ) } } \end{array} \right.
$$

理由如下：

（1）所列界面条件可以确定界面两侧流体压力和渗流速度等参数，实现对相邻子区域的渗流方程的连接；（2）这是两项被渗流力学认可的结论： $\nabla \cdot \boldsymbol { \nu } _ { t } = 0$ 根据质量守恒得到；上游权在流体力学中是一种自然规律的表达，在建立渗流数学模型前，它就应该列入物理模型，作为前提假设，在所建立的渗流数学模型中有对应的数学公式表达，而非作为一种可选的数值求解方法；（3）公式（40-a）根据 $\hat { \Phi }$ 确定上游权方向。相比一些文献采用 $\widehat { p } _ { \ell } = p _ { \ell } + \rho _ { \ell } g \Delta D$ 确定上游权，它更为合理，因为当两相流体对流时，利用 $\hat { p } _ { \ell }$ （ $\scriptstyle \left. 4 0 - a \right.$ ）判断上游得出的结果可能违背界面条件（40-b)；采用有限小时间间隔分析法，在间隔内 $t _ { 0 } \sim \operatorname* { l i m } _ { \Delta t \to 0 } \left( t _ { 0 } + \Delta t \right)$ 时间内，用 $\hat { \Phi }$ 判定的上游函数确定的 $ { \boldsymbol \nu } _ {  { \boldsymbol w } } ^ { \Gamma }$ ， $\nu _ { n } ^ { \Gamma }$ 变化平缓，但是由 $\hat { p } _ { \ell }$ 判定上游权结果会出现跳跃，如图2、图4、图9、图11所示。

# 5.结论

(1）传统渗流力学理论认为根据质量守恒定律在突变界面处各相渗流速度连续(CPVCM)，本文从三个方向进行了质疑：根据CPVCM 推断的突变界面两侧的流体饱和度分布存在实际的反例，包括均质介质和毛管力不同的两种多孔介质两类；对于驱替前缘问题 CPVCM与 Rankine-Hugoniot 跃变条件矛盾；CPVCM推导出的数值计算格式被油藏数值模拟证明会出现非物理结果而被弃用;

（2）论文回溯了文献根据质量守恒方程推导CPVCM的过程，发现这些推导过程出现用界面上同一质点的流速代替了界面两侧不同质点的流速，实质上预置了渗流速度连续，属于自证。

（3）本节根据质量守恒方程、达西公式、上游权性质，针对不可压缩流体，考虑两相流毛管力和重力作用，在三维空间建立了突变界面两侧各相流速，得出在突变界面两侧，各相渗流速度和各相压力一般都不连续，称为JPVCM。JPVCM能够解释CPVCM面临的上述所有质疑，不仅实用于有间断界面的渗流，也适用于连续场渗流，而且也适用于纯活塞式驱替；

（4）根据 JPVCM 突变界面处的变界面条件包括两项：其一、突变界面处总流速连续；其二、突变界面处的渗流速度由上游权函数确定。

当前关于多相渗流的突变界面的条件的研究仅限于不可压缩两相流，而考虑流体可压缩性、相间传质或相变、三相流、黑油模型、组分油藏模型等更复杂情况还有待研究。

实际油藏基本含有变变界面，油藏工程方法必须依赖考虑突变界面的渗流力学，所以突变界面条件完善作为油藏工程的基础理论，将影响油藏开发的各个环节，例如相对渗透率测量、试油试井、油藏数值模拟、生产动态分析、产量预测、开发方案优化、油气二次运移成藏、井筒计算、微观渗流等。除了油气层渗流，也将在其它多相渗流领域发挥作用。

# 参考文献

[1]MUSKATM, WICKOFFRD.The Flow ofHeterogeneous Fluids Through Porous Media[J]. The Journal of Geology, 1937, 46(2):   
[2]SHELDONJW,ZONDEK B,CARDWELL WT.One-Dimensional,Incompressible,Noncapillary,Two-Phase Fluid Flow in a Porous Medium [J]. Transactions of the AIME,1959,207(1): 136-43.   
[3]BACHMATYB,J.Mathematicalformulationoftransport phenomena inporous media; proceedings ofthe the Second Symposium on Fundamentals ofTransport Phenomena in Porous Media,IAHR,Guelph,Ont., Canada,F,1972 [C]. [4]BEAR J. Hydraulics of Groundwater [M]. New York: McGraw-Hill, 1979.   
[5]HASSANIZADEHM, GRAY W G. General conservation equations for multi-phase systems: 1.Averaging procedure [J].Advances in Water Resources,1979,3(1): 25-40.   
[6]HASSANIZADEH S M, GRAY W G. Derivation of conditions describing transport acros Zones ofreduced dynamics within multiphase systems [J]. Water Resources Research,1989,25(3): 529-39.   
[7]RAATS P.Theroleof inertia inthe hydrodynamics ofporous media[J].Archive for Rational Mechanics &Analysis, 1972, 44(4): 267-80.   
[8]BEAR J.Dynamics of Fluids in Porous Media [M]. Courier Corporation,1975.   
[9]VAN DUIJN CJ,MOLENAAR J,DE NEEF M J.The effect of capillary forces on immiscible two-phase flow in heterogeneous porous media [J]. Transport in porous media,1995,21(1): 71-93. [10] 刘绍学,朱元森.数学辞海[M].数学辞海,2002.   
[11] HASSANIZADEH S M, GRAY W G.Boundary and interface conditions in porous media [J]. Water Resources Research,1989,25(7): 1705-15.   
[12] HASSANIZADEH S M, GRAY W G. Mechanics and thermodynamics of multiphase flow in porous media including interphase boundaries [J].Advances in Water Resources,1990,13(4): 169-86.   
[13]JAFFRéJ. Numericalcalculation ofthe flux across an interface between two rock types of a porous medium fora two-phase flow [M]. Hyperbolic Problems Theory Numerics Applications.NY; Stony Brook.1996: 165-77.   
[14] LIU Z.Propagation and Evolution of Wave Fronts in Two-Phase Porous Media[J].199,34(1): 209-25.   
[15] FUCiK R, MIKYSKA J,BENES M,et al. Semianalytical Solution for Two-Phase Flow in Porous Media with a Discontinuity [J]. Vadose Zone Journal, 2008,7(3): 1001-7.   
[16]AL1,Q.,RAEINI,etal.Modelling two-phaseflowinporous mediaat the pore scale using the volume-of-fluid method [J]. Journal of Computational Physics,2012,231(17): 5653-68.   
[17] RAEINI A Q, BIJELJIC B, BLUNT M J. Generalized network modelling: capillry-dominated two-phase flowmodel description [J]. PHYSICAL REVIEW E,2017,97(2): 023308.   
[18]DEDé L,QUARTERONIA.Isogeometric Analysis ofaPhase Field Model forDarcyFlows with Discontinuous Data [J].数学年刊：B辑英文版,2018,39(3):26.   
[19] SHAMS M,RAEINI A Q,BLUNT M J,et al. A numerical model of two-phase flow at the micro-scale using the volume-of-fluid method [J]. Journal of Computational Physics,2018,357(159-82.   
[20] ALALI AH, HAMONFP,MALLISON B T,et al. Finite-volume simulationof capillry-dominated flow inmatrixfracture systems using interface conditions [J]. Computational Geosciences,2021,25(1): 17-33.   
[21] TRANLK,KIMJC,MATTHISK.Simulation oftwo-phas flow in porous media with sharp material discontinuities [J].Advances in Water Resources,2020,142(1): 103636.   
[22] DASHTBESH N, ENCHeRY G, NOETINGER B. A dynamic coarsening approach to immiscible multiphase flows in heterogeneous porous media[J]. Journal of Petroleum Science and Engineering, 2021,201(3):108396.   
[23] BOSMA S B,HAMONFP, MALLISONBT,et al. Smooth implicit hybrid upwinding for compositional multiphase flow in porous media [J]. Computer Methods in Applied Mechanics and Engineering, 2022,388(114288.   
[24] SHOKRI J,GODINEZ - BRIZUELA O E,ERFANI H, et al. Impact of displacement direction relative to heterogeneityonaveraged capilary pressure -saturation curves[J]. Water Resources Research,2022,e2021WR030748. [25] XINJ,SHIF,FANS,etal.Asharp interface multiphase flowmodelfor two-dimensional waterimpactofasymmetric and asymmetric wedge [J]. Applied Ocean Research, 2022, 119(102988-.   
[26] BUCKLEY SE,LEVERETTMC.Mechanism ofFluid Displacement in Sands[J].Transactions of the AIME,1942, 146(01): 107-16.   
[27] DOSTER F,HILFER R. Generalized Buckley-Leveret theory for two-phase flow in porous media[J]. New Joural of Physics,2011,13(12): 123030.   
[28]RANKINE W.On the thermodynamic theory of waves of finite longitudinal disturbance[J].Philosophical Transactions of the Royal Society of London,1870,160): 277-88.   
[29]JAFARI I，ROKHFOROUZ M R. Numerical modeling of water oil two-phase flow during counter-current spontaneous imbibition in porous media at pore-scale[J]. Petroleum Science and Technology,2020,38(24):1040-53. [30]WANGD,CHENGL,CAOR,etal.Pore-scale model oftwo phase flow in2D porous media: Influences ofinterfacial tension and heterogeneity efects on CO2 injection in the tight oil reservoir[Jj.IOPConference Series:Earth and Environmental Science, 2020, 467(1): 012061.   
[31] NOIRIEL C,SOULAINE C.Pore-Scale Imaging and Modeling of Reactive Flow in Evolving Porous Media: Tracking the Dynamics of the Fluid-Rock Interface [J].Transport in Porous Media,2021,140(1):181-213.   
[32] RAEINI Q,ALI. Modelling multiphase flow through micro-CT images of the pore space [D]; Imperial College London, 2013.   
[33] RAEINI A Q,BLUNT MJ,BIJELJIC B.Direct simulations oftwo-phase flow on micro-CT images of porous media and upscaling of pore-scale forces [J]. Advances in Water Resources,2014, 74(116-26.   
[34] MEHMANI Y,TCHELEPI HA.Multiscale Formulation of Two-Phase Flowat the Pore Scale [J].Journal of Computational Physics,2019,389(164-88.   
[35] SAHAR, BAKHSHIAN,SEYYED,et al. Pore-scale characteristics of multiphase flow in heterogeneous porous media using the latice Boltzmann method [J]. Scientific Reports,2019,9(1): 1-13.   
[36] NEEF M,MOLENAAR J.Analysis ofDNAPL infiltration ina medium witha low-permeable lens [J].Computational Geosciences,1997,1(2): 191-214. [37] DUIJN C, MOLENAAR J,NEEF M.The efect of capilary forces on immiscible two-phase flow in heterogeneous porous media [J]. Transport in Porous Media,1995,21(1): 71-93.   
[38] VAN DUIJN C J,DE NEEF M J.The Effct of Capillry Forces on Immiscible Two-phase Flow in Strongly Heterogeneous Porous Media [J]. 1994,   
[39] PENG X,MOF,LIANG B,et al.Critical Investigation Of Interface Conditions For Fluid Presures,Capilary Pressure,And Velocities At Jump Interface In Porous Media[J]. Journal of Porous Media,2019,22(6): 723-44. [40] AHMED R X Y, EDWARDS M G. A cel-centred CVD-MPFA finite volume method for two-phase fluid flow problems with capilary heterogeneity and discontinuity[J].Transport in Porous Media,2019,127(1): 35-52.   
[41] BRENNER K, CANCéS C,HILHORST D.Finite volume approximation for an immiscible two-phase flow in porous media with discontinuous capillary pressure [J]. Computational Geosciences,2013,17(3): 573-97.   
[42] CANCeS C.Finite volume scheme for two-phase flows in heterogeneous porous media involving capilary pressure discontinuities [J]. Esaim Mathematical Modelling & Numerical Analysis, 2009, 43(5): 973-1001.   
[43]ENCHeRY G, MICHEL R E. Numerical Approximation of a Two-phase Flow Problem in a Porous Medium with Discontinuous Capillary Forces [J]. Siam Journal on Numerical Analysis,2006, 43(6): 2402-22.   
[44]FRIS,H.A,EVJE,etal.Numerical treatmentoftwo-phase flowincapilary heterogeneous porous mediaby finitevolume approximations [J]. International journal of numerical analysis and modeling,2012, 9(3): 505-28.   
[45] HAMONF P,MALLISON B T,TCHELEPI HA. Implicit Hybrid Upwinding for two-phase flow in heterogeneous porous media withbuoyancyandcapilarity[J].ComputerMethods inAppliedMechanicsandEngineering,2018,331(701- 27.   
[46] ALALIA,HAMONF, MALLISON B,etal. Finite-Volume Simulation of Capilary-Dominated Flowin MatrixFracture Systems using Interface Conditions [J]. 2019,   
[47] BRENNERK,DRONIOUJ,ROLANDM,etal.Total-velocity-basedfinite volumediscretizationoftwo-phaseDarcy flowin highly heterogeneous media withdiscontinuous capilary pressure[J].IMAJournalof Numerical Analysis,2021, [48] BRENNER K, ROLAND M, QUENJEL E H. Vertex Approximate Gradient discretization preserving positivity for two-phase Darcy flows in heterogeneous porous media[J].Journal ofComputational Physics,202o,409(109357-. [49] BRENNER K, CHORFI N, MASSON R. Sequential implicit vertex approximate gradient discretization of incompressible two-phase Darcy flows with discontinuous capilary pressre[J].ComputationalGeosciences,2021,26(1): 147-69.   
[50] JIANG J,TCHELEPI HA.Nonlinear Acceleration of SequentialFully Implicit (SFI) Method for CoupledFlowand Transport in Porous Media [J]. 2019,352:246-75.   
[51] WATANABE S,LI Z,BRATVEDT K,et al.A Stable Multi-phase Nonlinear Transport Solver with Hybrid Upwind Discretizationin Multiscale Reservoir Simulator; proceedings of the Ecmor Xv-european Conference on the Mathematics of Oil Recovery,F, 2016 [C].   
[52] AGHILI J, BRENNER K,HENNICKER J,et al. Two-phase Discrete Fracture Matrix models with linear and nonlinear transmission conditions [J]. GEM-International Journal on Geomathematics,2018,10(1):1-35.   
[53] BRENNER K, GROZA M,JEANNINL,et al. Immiscible two-phase Darcy flow model accounting for vanishing and discontinuous capillary pressres: application to the flow in fractured porous media[J]. Computational Geoences,2016, 21(3): 1-20.   
[54]BRENNER K, HENNICKER J, MASSON R, et al. hybrid-dimensional modeling of two-phase flow through fractured porous media with enhanced matrix fracture transmision conditions fracture model multiphase hybriddimensional darcy flow model vertex approximate gradient scheme polyhedral meshes [J]. Journal of Computational Physics,2018,357(100-24.   
[55] AZIZ K, SETTARI A. Petroleum reservoir simulation [J]. Elsevier Applied Science Publishers, 1986,   
[56]BRENIERTY,JAFFRTTJ.upstreamdiferencing for multiphase flow inreservoir simulations[J].SIAMjournalon numerical analysis,1991, 28(3): 685-96.   
[57]TADMOR E.Numerical viscosity andthe entropy condition forconservative diference schemes[J].Mathematics of Computation,1984, 43(168): 369-81.   
[58] WARRICK A W. Numerical approximations of Darcian flow through unsaturated soil [J]. Water Resources Research, 1991, 27(6): 1215-22.   
[59]RAITHBY GD. Acritical evaluationofupstream diferencing applied to problems involvingfluidflow[J].Computer Methods in Applied Mechanics and Engineering, 1976, 9(1): 75-103.   
[60] TODDMR,APOS,DELLPM,etal. Methods for Increased Accuracyin Numerical Reservoir Simulators[J].Society of Petroleum Engineers Journal, 1972, spe-3516(06): 515-30.   
[61]DICKS EM.Higher Order Godunov Black-Oil Simulations for Compressble Flow[D]; UniversityofReading,1993. [62]BRANTSONET,JUB,WUD,et al.Stochastic porous media modeling and high-resolution schemes for numerical simulation of subsurface immiscible fluid flow transport [J]. Acta Geophysica, 2018, 66(3): 243-66.   
[63] ABOIYAR T, GEORGOULIS E H, ISKE A. Adaptive ADER Methods Using Kemel-Based Polyharmonic Spline WENO Reconstruction [J]. Siam Journal on Scientific Computing, 2010, 32(6): 3251-77.   
[64]PENG X,MOF,DU Z.Interfacecondition forthe Darcy velocityat the water-oilflood frontin the porous medium [J]. PLoS ONE,2016,12(5): e0177187.   
[65] BRENNER K， CHORFI N,MASSON R. Sequential implicit vertex approximate gradient discretization of incompressible two-phase Darcyflowswithdiscontinuous capilary pressre[J].ComputatioalGeosciences,222,26(1): 147-69.   
[66] ANTONCEV S N.The solvabilityof boundary value problems for degenerate equations of two-phase filtration [J]. Dinamika Splon Sredy,1972,28-53,246.   
[67] G CHAVENTJJ. Mathematical models and finite elements forreservoir simulation:single phase,multiphase,and multicomponent flows through porous media [M]. ELsevier, 1986.   
[68] CHEN Z.Degenerate Two-Phase Incompressible Flow: I. Existence, Uniqueness and Regularityofa Weak Solution [J]. Journal of Differential Equations,2001,171(2): 203-32.