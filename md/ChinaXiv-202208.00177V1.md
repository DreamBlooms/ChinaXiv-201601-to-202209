# 周期光学系统中的连续域束缚态

姚建钰\*，李继涛，张雅婷，李杰，岳震，徐航，杨帆（天津大学 激光与光电子研究所，天津 300072）通信作者邮箱：\*iqyao@tju.edu.cn

摘 要：周期光学系统，如光子晶体和光学超材料，可以在亚波长尺度局域高密度的电磁场能量，并获得极小的模式体积，在光操控领域具有巨大的应用潜力。近年来，周期光学系统中一种光与物质的强相互作用被发现，称之为连续域束缚态，它是一类频率位于辐射连续域内但被完全局域的特殊电磁本征态，具有诸多有趣的物理特性和丰富的应用场景。本文系统性综述了周期光学系统中连续域束缚态的分类及其理论体系，并总结了其基本物理特性和最新应用发展。周期光学系统中的连续域束缚态正在为集成光学、信息光学、生物光学、拓扑光学以及非线性光学等领域注入新的发展动力。

关键词：周期光学系统，连续域束缚态，理论体系，物理特性，应用发展

# Bound states in continuum in periodic optical systems

YAO Jian-quan\*, LI Ji-tao, ZHANG Ya-ting, LI Jie, YUE Zhen, XU Hang, YANG Fan (Institute of Laser & Opto-electronics, Tianjin University, Tianjin, 3Ooo72, China) Corresponding authors, E-mails: \*jqyao@tju.edu.cn

Abstract: Periodic optical systems,such asphotonic crystals andoptical metamaterials,can localize high-density electromagnetic fieldenergyatsubwavelengthsalesandobtainextremelysmallodevlumes,soteyhavegreatapicationpotentialintefieldof lightmanipulation.Inrecent years,astrong interactionbetween lightand matter inperiodicopticalsystemshas beendiscovered, whichiscalled boundstates incontinuum(BIC).OpticsBICsare special electromagneticeigenstates thosefrequencieslieinthe radiationcontiuumbutarecompletelylocalized,andhaveshowninterestingphysicsandrichaplicationscenarios.Thispaper systematicallyreviewstheclasificationandtheoryof BICsinperiodicopticalsystems，and summarizestheirbasic physical propertiesandthe latest application development.BICsin periodicopticalsystemsare injectingnewimpetus intothe fieldsof integrated optics,information optics, bio-optics,topological optics,and nonlinear optics.

KeyWords:Periodicoptical systems；Boundstates in continuum;Theoretical system；Physical properties；Application development

# 1引言

经典力学的观点认为电子若具有足够的动能便会从其原子系统中逃逸出去，所述能量位于系统的散射连续谱中。然而，事实上有些电子虽然具有足够的能量却仍然被束缚在系统中，并未从周围系统的引力范围中解放出来；这一看似矛盾但真实存在的现象可以在量子力学中得到解释，由物理学界的两位先贤冯诺依曼（JohnvonNeumann）和尤金维格纳（EugenePaulWigner）于1929 年阐明[1]，这些电子所处的状态被称为“连续域束缚态”或“连续体束缚态”（英文为bound states incontinuum，一般缩写为BIC)。基于这一概念的类似现象相当普遍，在电磁波[2]、水波[3-5]、声波[6-8]和固体中的弹性波中都被发现[9,10]。进入二十世纪，光学BIC 现象在光波导、光纤、光子晶体和光学超材料等广泛的介质体系中进行了研究[11-32]。常规的观点认为，在辐射连续域中的电磁本征态是具有辐射的，能完全被介质捕获的束缚态应该位于辐射连续域以下；而BIC的出现打破了这种常规认知，在辐射连续域中，BIC是一类并不具有辐射的电磁本征态，尽管其频率和动量可能与真空模式匹配，但它仍被完全束缚在共振系统中（详见第二节)。更通俗地讲，光学BIC即是共振系统中一些直觉上“本该”辐射但实际并不辐射的特殊电磁共振状态一一这一描述并不严格准确，但有助于直观的理解光学BIC这一深晦的概念。

光子晶体和光学超材料是典型的周期光学系统，其在亚波长尺度与光发生相互作用，可以在极小空间内局域高密度的电磁能量，其中光学超材料还展现出强大的光场操控能力，可以对光的频率、相位、偏振、幅度、轨道角动量和自旋角动量等属性实施定制化操作[33-45]。周期光学系统中的BIC 是一种光与物质的强相互作用，但严格来讲，光学BIC是一个理想的状态，因为不可能存在无限大的周期系统，实际上，主要是运用其辐射泄露模式一一准BIC [46-53]。通过调整系统构型、尺寸、周期边界或激发波矢等参数，可使得BIC与远场弱耦合，从而小部分泄露到周围环境中，这种状态便称之为准BIC。基于BIC的系统的辐射损耗可以通过调整组成谐振模式的干扰来精确控制，从而获得不同泄露程度的准BIC[54-60]。虽然准BIC 模式容易获取，但在光学上获取真实BIC相当艰难，因为BIC模式与自由空间辐射没有耦合，根本不被远场激发。直到最近，这一困境才被打破，JoelK.W.Yang 等提出一种在纳米空间精确表征真实光学BIC的技术与装置，该实验在扫描透射电子显微镜中结合了阴极发光和单色电子能量损失谱，用纳米尺寸的聚焦电子束激发近场中的光学模式，在这些辐射和非辐射激发中传递的能量用单色电子能量损失谱测量，而在远场中仅用阴极发光测量辐射损耗，通过对单色电子能量损失谱和阴极发光谱的比较，区分了真实BIC 和准BIC光学模式[61]。需要强调的是，通过引入宇称-时间（parity-time）对称性扰动，远场也可能激发真实BIC，其中可能蕴藏更丰富的物理内涵，这一现象近期在光子晶体光纤中被发现[62]，但这种现象并未被普遍证实，因此本文只考虑常规意义上的远场不可激发的BIC。

周期光学系统中BIC的应用涵盖集成光学、信息光学、生物光学、拓扑光学以及非线性光学等多个领域，主要依赖于两个基础物理特性：可调谐的高品质（Q）因子和其特殊的动量空间偏振分布[63-69]，具体内容将在第三节阐述，如图1。高Q因子且器件小型化是对准BIC基本特性的追求之一，这有利于在极小空间范围内获得高强度的光与物质相互作用，以满足更多应用；最近的进展表明，支持准BIC的周期系统面积可以小到 $4 \lambda ^ { 2 }$ （入为工作波长）[70]。基于高Q因子属性，BIC可以用于窄带滤波[71]、高灵敏度传感[72]、分子光谱编码成像和图像边缘检测等领域[73,74]，也可用于非线性光倍频[75]、微激光[76]、微纳天线等领域[77]。此外，基于BIC在动量空间中特殊的偏振分布，使得它可用于动量空间中的涡旋光产生[78,79]；进一步，结合高Q因子属性和动量空间中的偏振属性，BIC也可能产生更多有趣的应用，例如，窄带不对称传输[80]。我们将在第四节来具体阐述光学BIC的这些应用与原理。

![](images/1dffb2cbd1107e8a5b22c68311049a9c20325a3c4ca447733b8ca5dffd58d0cb.jpg)  
图1周期光学系统中BIC的基础物理特性及其应用 Fig.1Fundamental Physical Properties and Applications of BICs in Periodic Optical Systems

# 2 BIC的理论体系

# 2.1BIC的概念与分类

考虑真空中的一个周期平板介质，如图2a，辐射电磁波的波矢 $\mathbf { k }$ 可被分解成垂直分量 $k _ { \perp }$ 和水平分量 $k _ { / / }$ ，从几何关系可知，任意辐射电磁波的频率$\scriptstyle { \omega = \mathbf { c } \left| \mathbf { k } \right| }$ 总是大于 $\mathrm { c } { \lvert k _ { \ / I I } \rvert }$ 的。此外，对于任一给定的水平波矢分量 $k _ { / / }$ ，垂直分量 $k _ { \perp }$ 可以是任意取值，因此辐射电磁波的频率是连续的。在频率-波矢 $( \omega - k _ { / / } )$ （202谱中，辐射电磁波的频率占据了 $\omega \mathrm { { > c | } } k _ { / / } \vert$ 的区域（也称为光锥)，即辐射连续域。在辐射连续域以下是常规束缚态占据的区域，麦克斯韦方程的本征解决定了介质中束缚态的电磁波频率是离散的。传统观点认为，在辐射连续域内，共振模都是具有辐射泄露的，但BIC背离了这一原则；BIC是一些频率位于辐射连续域内但又被完全束缚、无任何能量泄露的特殊共振模[81]。

![](images/e3412c72ee8d05754c0db7c26f889079832c2f5ea294a6f38292013c7c27e2e0.jpg)  
图2BIC的概念与分类。(a)周期光学系统的带结构中辐射共振模、BIC 与普通束缚态的带位置示意图，此处以对称保护型 BIC 为例，它位于波矢空间的高对称点（T点)；(b)周期系统中光学BIC 分类、与远场去偶方式及其基础理论图表 Fig.2.Theconceptandclasificationof BICs.(a)Schematicdiagram forthepositions of radiationresonance modes,BICsand ordinaryboundstates intheband structureofperiodicopticalsystems Here,thesymmetry-protectedBICistakenasanexample, which islocatedatthehighsymmetrypoint(point)ofthewavevectorspace; (b)thediagramfortheclasification,far-field decoupling approaches and fundamentals of optics BICs in periodic systems

BIC虽然位于辐射连续域内，但与远场辐射连续域完全解耦，从解耦方式上看主要有两种类型。如图2b，第一种BIC由结构对称性失配造成：具有$\mathbf { C } _ { 2 }$ 对称的微结构可约束辐射连续域中电磁场具有偶对称的共振模，这类共振模与奇对称的辐射模完全正交，从而与远场辐射去耦，即形成BIC，这类BIC称为对称保护型BIC；一旦结构的 $\mathbf { C } _ { 2 }$ 对称性破坏，BIC将与不同对称性的辐射模耦合，产生辐射泄露从而形成准BIC。第二种BIC来源于干涉相消：结构中不同电磁模式的干涉相消，或者同一种电磁模式的不同波的干涉相消，间接地实现与远场辐射的解耦，前者可分为Fabry-Pérot 型BIC和Friedrich-Wintgen型BIC，后者一般为单共振型BIC；调节结构参数可以调节辐射相消的程度，当辐射不能完全相消时，即形成辐射泄露的准BIC;这些BIC与准BIC通过调节结构参数来实现，并且很难准确预测BIC出现的参数条件，因此也被称为调参BIC或偶发BIC。

对于不同类型的BIC，其理论解释也不一样，主流的有对称性理论、时域耦合模理论以及耦合波理论，它们分别适用于解释不同BIC的来源，其中时域耦合模理论还适合分析所有类型BIC的散射问题。此外，还诞生了电磁多极理论，它研究多极子辐射从而识别对称保护型BIC和偶发BIC，但也缺乏对偶发BIC更进一步的分析能力，例如甄别偶发BIC的具体类型。总之，目前还没有一个理论可以对所有类型BIC的来源进行统一描述，针对不同类型的BIC需要单独分析。

# 2.2对称保护型 BIC

当物理结构具有 $\pi$ 旋转对称性（ $\mathbf { C } _ { 2 }$ 对称）时错误！未找到引用源。，由于对称性保护，可以发现某些具有特定对称类型的束缚模与其他对称类型的连续模之间的耦合被完全禁止。如图3a，最常见的结构是在正方格子中刻蚀圆孔，并以此为元胞在二维方向上周期性排列成光子晶体平板[81]。在二维周期结构中，电磁模式可以由平行于平板的波矢量$k _ { / / } { = } ( k _ { x } , k _ { y } )$ 来表示。对称性保护的体现在于：当围绕$z$ 轴（光子晶体平板的法向）以 $\pi$ 角度旋转结构时，有一类电磁模式的平行波矢总是不变的，为确保这一特点，这类电磁模式的平行波矢通常位于波矢空间中的I点，此时这些模式的波矢没有水平分量，即 $k _ { I / = } ( 0 , 0 )$ ；在I点，偶对称的电磁模式与奇对称的电磁模式完全解耦，由于结构具有 $\mathbf { C } _ { 2 }$ 对称性，偶对称的电磁模式将被完全约束在结构中，形成对称保护型BIC，而奇对称的电磁模式将脱离结构辐射出去；当辐射频率低于衍射限时（衍射限定义为$\scriptstyle { \omega = 2 \pi \mathbf { c } / \mathbf { n } \mathbf { a } }$ ，这里c为真空中光速， $\mathbf { n }$ 为环境介质的折射率，a表示周期常数)，辐射方向仅有平板法向。离开I点后，电磁模式的水平波矢分量 $k _ { x }$ 和 $k _ { y }$ 中至少有一个量不再为零， $\pi$ 旋转操作不再确保水平波矢的不变性；由于失去对称保护性，BIC将与辐射模耦合形成泄露的准BIC。

从对称保护BIC中获得准BIC的核心思想都是破坏结构的 $\mathbf { C } _ { 2 }$ 对称性，这种破坏可以发生在波矢空间中（上述在波矢空间中操控电磁模式的水平波矢离开I点便属于此)，也可以发生在实空间中。在实空间中破坏结构 $\mathbf { C } _ { 2 }$ 对称性以获得准BIC的报道非常普遍，如图3b，常见的结构有：开口大小或位置变化的分裂圆环或矩形环[82,83]，一对长度不同的不对称矩形条[84,85]，一对以八字形倾斜的椭圆条[86,87]，添加或削减一小部分的不对称矩形或圆形块[8-90]，具有孔洞且孔洞位置偏离中心的圆盘[91]，以及中心位置偏移的不对称十字架等[92,93]。结构微扰理论通常被用来描述对称保护型准BIC的辐射特性；在结构微扰理论中，任何对结构 $\mathbf { C } _ { 2 }$ 对称性破坏的操作都被视为对原结构的微扰，这导致了BIC与辐射连续体的耦合；准BIC被看作是封闭共振腔与辐射连续体相互作用后的本征共振态，其辐射电场可表示为 $\scriptstyle \mathbf { E } ( \mathrm { r } ) = \mathbf { E } ^ { ( 0 ) } ( \mathrm { r } ) + \varphi \mathbf { E } ^ { \prime } ( \mathrm { r } )$ ，这里 $\mathbf { E } ^ { ( 0 ) } ( \mathbf { r } )$ 是考虑完美磁边界条件求解的麦克斯韦方程的结果，完美磁边界条件描述为 $\mathbf { \boldsymbol { s } } \mathbf { \boldsymbol { \times } } \nabla \mathbf { \times } \mathbf { E } ^ { ( 0 ) }$ ， $\textbf { s }$ 表示边界法向矢量，$\varphi \mathbf { E } ^ { \prime } ( \mathrm { { r } } )$ 描述了结构微扰作用[94]。

描述准BIC共振强度的一个重要物理量是品质因子Q，定义为 $scriptstyle { Q = \omega _ { 0 } / 2 \gamma }$ ，这里 $\omega _ { 0 }$ 是共振频率，γ表示共振阻尼率。真实BIC没有共振阻尼，Q无穷大，由于它不能与远场辐射耦合，因此也无法被远场平面波激发，无法在光谱上表现出来；但准BIC是一个与远场辐射相互作用的结果，因此可以在光谱上表现出来；准BIC具有共振阻尼，将在光谱上展现出非零的共振线宽。对称保护型准BIC的品质因子与结构 $\mathbf { C } _ { 2 }$ 对称性的破坏程度密切相关；YuriKivshar等人研究发现这种相关性可表示为$\scriptstyle { \mathrm { Q } = \mathrm { Q } _ { 0 } \mathrm { a } ^ { - 2 } }$ ，这里 $\mathrm { \Delta Q _ { 0 } }$ 是一个由结构决定的常数， $\mathrm { ~ \bf ~ \underline { ~ } { ~ a ~ } ~ }$ 表示不对称系数，它是一个衡量结构 $\mathbf { C } _ { 2 }$ 对称性破坏程度的参数（图3c）[94]；容易发现，品质因子随着不对称程度的增强而减小，当不对称性增强到一定程度后，准BIC共振将退化成普通共振。

![](images/7363d6147123988e997ab0887b26ed584ea8c143585ab39a816558d35eb49cd2.jpg)  
图3对称保护型 BIC。(a)圆孔光子晶体板约束频率低于衍射限下的偶对称电磁模，而辐射奇对称电磁模[811；(b)常见的因$\mathbf { C } _ { 2 }$ 对称性破坏而支持准 BIC 的的结构；(c)品质因子随着结构不对称程度增强而降低，具有 $\scriptstyle { \mathrm { Q } = \mathrm { Q } _ { 0 } \mathrm { a } ^ { - 2 } }$ 的关系[94]

Fig.3.Symmetry-protected BICs.(a)Thecircular-hole photoniccrystal plateconfines even-symmetric modeswith frequencies belowthedifractionlimit，whileodd-symmetricmodesradiateoutthecircular-hole photoniccrystalplate[81;(b）thecommon structures that support quasi-BIC due to $\mathbf { C } _ { 2 }$ symmetry breaking; (c)the quality factor decreases with increasing structural asymmetry, showing the relationship $\scriptstyle \mathrm { Q = Q _ { 0 } } \alpha ^ { - 2 \ [ 9 4 ] }$ ：

![](images/057f5adfc43a186e6c4ad9fb767b8f9e9472f6e2dc2d93a72185ca4c896f9120.jpg)  
图4共振耦合型 BIC。(a)两个完全相同的高反射光子晶体板支持的，(b)其示意的共振机制：调节两个平板共振器距离 $d$ 形成驻波[81]；(c-d)(c)单独一个周期结构器件中两个模式耦合示意图，(d)两个模式耦合成一个高Q模的辐射谱；(e)调频率调谐谱，调节结构参数，两个本征频率移动并交叉，在交叉点附近，一个频率的共振阻尼将完全消失形成Friedrich-Wintgen BIC，(f)在透射光谱上该点表现为平滑的谱线[96]

Fig.4.Resonance-coupled BICs.(a)Fabry-PerotBICsupportedbytwoidentical highlyreflectivephotoniccrystal plates,andits mechanism in (b): adjust the distance $d$ of the two plate resonators to form a standing wavel81; (c)schematic diagram of the coupling of two modes inaperiodicstructuredevice,(d)theradiationspectrumofthecouplingof tetwomodes intoahigh-Qmode;(e)the frequencytuning spectrum,adjusting thestructuralparameters,thetwoeigenfrequenciesmoveandcross,andtheresonancedamping of onefrequencywilldisappearcompletelyformingtheFriedrich-WintgenBICnear thecrosoverpoint,(f)teBICpoitppearsas a smooth line on the transmission spectrum.[96]

# 2.3共振耦合型BIC

周期几何结构导致光子带结构，这类似于固体中的周期电势产生电子带结构。周期平板支持频率位于自由空间中辐射模式的连续域内的导共振，这些共振通常具有有限的寿命，因为它们可以耦合到自由空间模式。虽然这些共振是辐射的，但不同共振模式耦合导致远场辐射相消也可以形成BIC，超表面中共振耦合型BIC可分为Fabry-PérotBIC和Friedrich-WintgenBIC。通过导共振效应构造具有单一辐射通道的高反射率二维周期结构，如光子晶体平板（图4a-b)，利用这样两个完全相同的结构组成一对镜面，当调节两个结构之间的谐振频率或间距 $d$ ，使往返电磁波的相移和为 $2 \pi$ 的整数倍时，就会形成BIC；这种结构相当于在两个谐振反射器之间形成法布里-珀罗（Fabry-Pérot）腔，腔体内往返电磁波的相移和为 $2 \pi$ 的整数倍即是构成腔内驻波的条件，从而实现对电磁波的捕获，这类BIC因此被称为Fabry-Pérot BIC[81,95]；进一步，细微地调节两个结构的间距则可以实现从BIC到准BIC的精细操控。若将支持Fabry-PérotBIC 的两个二维周期结构之间的距离调节到零，即相当于变成一个二维周期结构，在同一位置的两个共振的辐射也可能通过干涉相消形成BIC，这类BIC被称为Friedrich-Wintgen BIC[96]，如图4c-f。

时域耦合模理论（Temporal coupled-modetheory）是一个解释共振耦合型BIC现象的有效工具。在时域耦合模理论中，决定Fabry-PérotBIC 频率与阻尼率的关键数学量是一个Hamiltonian矩阵（其详细推演见2.4章节)，表示为：

$$
{ \bf H } = \left( \begin{array} { c c } { { \omega } } & { { k } } \\ { { k } } & { { \omega } } \end{array} \right) - i \left( \begin{array} { c c } { { \gamma } } & { { \gamma e ^ { i \varphi } } } \\ { { \gamma e ^ { i \varphi } } } & { { \gamma } } \end{array} \right) ,
$$

其中 $\kappa$ 是两个频率为 $\omega$ 的共振之间的近场耦合作用，y是单个共振的阻尼率， $\varphi$ 是波在两个谐振器间的传播相移。公式(1)的 $H$ 矩阵有两个本征值：

$$
\omega _ { \pm } = \omega \pm k - i \gamma ( 1 \pm e ^ { i \varphi } ) ,
$$

当往返电磁波的相移和为 $2 \pi$ 的整数倍时， $\varphi$ 恰好是 $\pi$ 的整数倍，上式两个本征值中的 $\scriptstyle \omega = \omega - k - i 2 \gamma$ 是一个复数，表示一个频率为 $\omega \mathbf { - } k$ ，阻尼率为 $2 \gamma$ 的本征模,另一个本征值则变成一个纯实数 $\scriptstyle { \omega _ { + } = \omega + k }$ ，这表示一个无阻尼的（ $\scriptstyle \cdot \gamma = 0 .$ ，频率为 $\omega { + } k$ 的BIC。若两个谐振器间的距离变为零（两个周期结构变成一个周期结构），将可能支持Friedrich-Wintgen BIC。此时，公式(1)中 $\scriptstyle \varphi = 0$ ，且两个相互耦合的共振不再是往返电磁波，因此不能确保具有相同的共振频率和阻尼率，这时Hamiltonian 矩阵变为：

$$
{ \bf H } = \left( \begin{array} { c c } { \omega _ { 1 } } & { k } \\ { k } & { \omega _ { 2 } } \end{array} \right) - i \left( \begin{array} { c c } { \gamma _ { 1 } } & { \sqrt { \gamma _ { 1 } \gamma _ { 2 } } } \\ { \sqrt { \gamma _ { 1 } \gamma _ { 2 } } } & { \gamma _ { 2 } } \end{array} \right) ,
$$

公式(3)的 $H$ 矩阵的频率本征值为：

$$
\omega _ { \pm } = \frac { ( \omega _ { 1 } + \omega _ { 2 } ) - i ( \gamma _ { 1 } + \gamma _ { 2 } ) \pm \sqrt { [ ( \omega _ { 1 } - \omega _ { 2 } ) - i ( \gamma _ { 1 } - \gamma _ { 2 } ) ] ^ { 2 } + 4 ( k - i \sqrt { \gamma _ { 1 } \gamma _ { 2 } } ) ^ { 2 } } } { 2 } ,
$$

公式(4)所表示的本征频率具有获得纯实数的条件，写作:

$$
k ( \gamma _ { 1 } - \gamma _ { 2 } ) { = } \sqrt { \gamma _ { 1 } \gamma _ { 2 } } ( \omega _ { 1 } - \omega _ { 2 } ) ,
$$

将公式(5)代入公式(4)可发现 $\omega .$ 将变为纯实数，此时$\scriptstyle \omega = ( \omega _ { 1 } + \omega _ { 2 } ) / 2 - ( \gamma _ { 1 } + \gamma _ { 2 } ) ( \omega _ { 1 } - \omega _ { 2 } ) / ( \gamma _ { 1 } - \gamma _ { 2 } )$ ，这意味着获得一个无阻尼的（ $\scriptstyle \cdot \gamma = 0 \ ,$ ，频率为 $\omega .$ 的 BIC；特别地，当$k { = } 0$ 或者 $\gamma _ { 1 } = \gamma _ { 2 }$ ，在 $\omega _ { 1 } = \omega _ { 2 }$ 处将获得BIC；该条件由Friedrich和Wintgen两位物理学家最先推导出[97],因此这类BIC被称为Friedrich-WintgenBIC。在物理上，共振耦合型BIC并不依赖于结构的对称性，其获取方式通常是调节有限个结构参数，当连续调节结构参数至一特定值时，结构将支持BIC，品质因子将变得无穷大，而在该结构参数的两端，品质因子递减，BIC变为准BIC。

# 2.4单共振型BIC

多个共振模的干涉相消可形成共振耦合型BIC，单个共振模中多组波的干涉相消也可形成BIC，这类BIC称为单共振型BIC，它较为少见，但确实存在。如图5a-b，2013年，ChiaWeiHsu等人在带有方形圆柱孔阵列的周期平板中发现了一种新型BIC的存在[98]；该结构具有时间反演对称性、$\mathbf { C } _ { 2 }$ 对称性以及上下镜像对称性，除了在一条带上的T点获得零泄露的BIC外，在同一条带上偏离I点的某处，再次获得了共振寿命趋于无穷大的BIC，在这个过程，品质因子呈现从极大到极小再到极大的变化趋势；由于这种BIC在离开I点后再次出现，不受结构对称兼容性限制，因此不属于对称保护型BIC，此外，它在单一TM共振模中被发现，不依赖于多个共振模干涉相消，因此也不属于共振耦合型BIC，这种新型的BIC随后被定义为单共振型BIC。一个直观而简单的理论可用来理解单共振型BIC：周期结构的本征电磁模式为布洛赫共振态，波函数可表达为平面波的傅里叶级数；在结构平板之外的近场区，这些波以指数衰减的倏逝波形式存在，随后在远场区以平面波形式传播；传播波的功率与 $( | \mathbf { C s } | ^ { 2 } \substack { + } | \mathbf { C p } | ^ { 2 } ) \mathrm { c o s } \theta ,$ 成正比，这里θ意味着传播角度，Cs和 $\mathrm { C p }$ 分别表示平面波的s和p分量在 x-y面内的平均幅度。当频率低于衍射限时，Cs 和 Cp是零阶傅里叶幅度；一般情况下，Cs和Cp为复数，傅里叶幅度有两个以上的自由度，因此仅调整波矢空间中 $k _ { x }$ 和 $k _ { y }$ 两个参数无法获得零输出的传播功率。然而，当结构具有时间反演对称性、 $\mathbf { C } _ { 2 }$ 对称性以及上下镜像对称性时， $\mathrm { C s }$ 和 $\mathrm { C p }$ 将为纯属实或纯虚数，傅里叶幅度的自由度降低为两个，此时仅调整 $k _ { x }$ 和 $k _ { y }$ 两个参数就可能使Cs和 $\mathrm { C p }$ 均为零（图5c)，从而获得零输出的传播功率。

基于耦合波理论（coupled-wave theory）[99,100],单共振型BIC的物理机制被进一步解释。在耦合波理论中，单共振型BIC来源于所有通道（包括面内封闭通道和面外辐射通道）中所有波的耦合作用，且耦合到开放通道中的所有波干涉相消 (图5d)。在I点时，由于结构几何对称性，所有参数都对称，耦合到开放通道中的面内不同波间的权重和相位都达到干涉相消条件，从而实现零辐射；调节波矢参数至离开I点后，新的对称性可能被创建，耦合到开放通道中的面内不同波间的权重和相位可以再次满足干涉相消条件，导致在开放通道中总体辐射被抑制到接近零。当然，如果结构的某些对称性不被保证，傅里叶幅度的自由度可能增加，此时则需要引入更多的参数来调节；此外，调整波矢参数也并不是获得单共振型BIC的唯一方法，例如，在一个基于开口介质矩形块的超表面中，通过调节开口位置，在某些TM模中也发现单共振型BIC的存在。

![](images/7cf5bde2b91125a19866dd42cbae52703f3dba75d8b79d847fd06d62558eaa6a.jpg)  
图5单共振型 BIC。(a)调节入射波矢可以再次进入BIC，其Q因子变化如(b)，当结构具有时间反演对称性、 $\mathbf { C } _ { 2 }$ 对称性以 及上下镜像对称性时，(c)调整 $k _ { x }$ 和 $k _ { y }$ 两个参数可能使s、p分量幅度（Cs、Cp）均为零，从而获得零输出的传播功率[98]；(d) 耦合波理论对单共振型 BIC来源解释的示意图，认为其来源于耦合到开放通道中的所有波干涉相消[100] Fig.5.Single-resonance BICs.(a)Adjust theincident wave vector toentertheBICagain,nditsQfactorchangesasshow n (b). When the structure has time-reversal symmetry, $\mathbf { C } _ { 2 }$ symmetry, and up-down mirror symmetry, (c) adjusting the two parameters of $k _ { x }$ and $k _ { y }$ is posible to make both the sandpcomponentamplitudes (Cs,Cp)zero,soas toobtain the propagating powerof zero output [98l;(d)the shematic diagramofthecoupled-wavetheory explaining thesourceofthesingle-resonanceBIC,which isconsideredto be derived from the destructive interference of all waves coupled into the open channel [100]

# 2.5时域耦合模理论

准BIC是BIC与远场辐射的弱耦合结果，时域耦合模理论已被广泛用于为弱耦合到输入和输出端口的光学谐振对象提供简单的解析描述[101-104]。该理论在弱耦合区工作良好；在实践中，当 $\mathrm { Q } { > } 3 0$ 时，该理论推导出的解析结果几乎是精确的，这符合准BIC 所考虑的情形，因此，时域耦合模理论成为解释 BIC 现象的一个基本数学理论之一[105]。该理论的强大之处表现在多个方面，例如，通过有限步骤的数学推导很成功的预测了共振耦合型BIC的存在，甚至预测了BIC独特的波矢空间偏振特性；更重要的是，该理论是一种用于描述共振结果的唯象理论，它完全可以不考虑共振的来源，无论BIC 是什么类型，辐射都会随着准BIC的形成而发生，此时，一个基本元素是谐振器和端口之间的耦合，因此，该理论普遍适用于描述任意准BIC的散射特性。

时域耦合模理论的重要性不言而喻。接下来，我们演示它如何预测出共振耦合型BIC的存在，其中重要一个参量是表示共振频率与共振衰减率（阻尼率）的Hamiltonian矩阵。一个共振器的共振模是一个时空动态场，数学上能分离出 $\mathbf { e } ^ { \mathrm { i } \mathrm { \omega t } }$ 独立项来表示时间特性；设该动态场幅度为 $\mathbf { a }$ ，它的大小由储存在模式中的能量来决定；首先假定该系统是无端口且能量守恒的封闭系统，对时间求导得到其共振幅度的动态关系，写作：

$$
\frac { d \mathbf { a } } { d t } = i \pmb { \Omega } \mathbf { a } \ ,
$$

这里 $\Omega$ 是一个频率矩阵。时域耦合模理论预测BIC存在的一个重要前提是，系统中存在两种以上的共振，因此 $\Omega$ 至少是一个二阶矩阵，并可以表示为：

$$
\Omega { = } \left[ \begin{array} { c c } { \omega _ { 0 1 } } & { k } \\ { k } & { \omega _ { 0 2 } } \end{array} \right] ,
$$

这里 $\omega _ { 0 1 }$ 和 $\omega _ { 0 2 }$ 表示两个模式的共振频率， $k$ 代表模式间的耦合率，这种耦合属于近场耦合。将两个端口引入这样一个共振系统时候，来自端口的入射波【与共振器耦合，且共振器内部共振将向端口衰减，衰减率为I，此时系统的动态关系可表达为：

$$
\frac { d { \bf a } } { d t } = [ i { \pmb \Omega } - { \Gamma } ] { \bf a } + { \bf D } ^ { \mathrm { T } } { \bf I } \ : ,
$$

这里 $\mathbf { D }$ 代表共振耦合到端口的耦合系数矩阵，它与端口耦合到共振器的系数矩阵互为转置， $\Gamma$ 与 $\Omega$ 一样均为2阶矩阵，可以表示为：

$$
\Gamma = \left[ \begin{array} { c c } { { \gamma _ { _ 1 } } } & { { \gamma _ { _ { 1 2 } } } } \\ { { \gamma _ { _ { 2 1 } } } } & { { \gamma _ { _ { 2 } } } } \end{array} \right] ,
$$

这里如果不考虑系统的损耗，衰减率完全有辐射损失决定，则 $\gamma _ { 1 }$ 和 $\gamma _ { 2 }$ 分别代表两个模式的辐射损失；y2与yi互为共轭数，表示两个模式的远场辐射耦合作用。此时，系统的Hamiltonian矩阵表示为：

$$
{ \bf H } { = } i \Omega - \Gamma = \left[ \begin{array} { c c } { { i \omega _ { 0 1 } { - } \gamma _ { 1 } } } & { { i k { - } \gamma _ { 1 2 } } } \\ { { i k { - } \gamma _ { 2 1 } } } & { { i \omega _ { 0 2 } { - } \gamma _ { 2 } } } \end{array} \right] ,
$$

求解Hamiltonian 矩阵的本征值即可得到本征频率与衰减率。值得注意的是，由于对准BIC频率与衰减的描述为复数 $\omega { - } i \gamma ,$ 其中心频率 $\omega$ 是实数，因此一般将公式(10)的频率项化为实数，取Hamiltonian为$\scriptstyle \mathbf { H } = \Omega + i \Gamma$ ；另一方面，由于对共振的时间特性在数学上也可描述为 $\mathrm { { e ^ { - i \infty t } } }$ ，系统Hamiltonian矩阵将变为$\scriptstyle \mathbf { H = } \Omega - i \Gamma$ ，这恰好到对应到2.2章节中所提出的Hamiltonian矩阵形式，按照公式(1-5)，可进一步得到衰减率为零的BIC形成条件，这里不再赘述。无论Hamiltonian矩阵的形式如何，本征频率和衰减率的值并不会因其表达形式的改变而改变。

以上提到，时域耦合模理论是一种用于描述共振结果的唯象理论，该理论虽然不能解释除共振耦合型BIC之外的其他类型BIC的来源，但适用于描述任意准BIC的散射特性。设有一个任意类型的准BIC 共振模，复频率为 $\omega _ { 0 }  – i \gamma ;$ ，公式(6-8)中的频率项$\Omega$ 和衰减率项r都将是一个单独的值而不是矩阵，公式(8)重新写作：

$$
\frac { d { \bf a } } { d t } = [ i \omega _ { 0 } - \gamma ] { \bf a } + { \bf D } ^ { \mathrm { T } } { \bf I } \quad ,
$$

对于散射波O，它来自于两个方面的贡献，一是输入波I与输出波直接耦合产生的背景散射，背散射矩阵表示为C；二是BIC共振与端口耦合的输出波，它是共振耦合到端口的耦合系数与共振幅度的乘积，表示为 ${ \bf D _ { a } }$ ；因此，完整的散射波可表达为：

$$
\mathrm { \bf O } = { \bf C I } + { \bf D a } = { \bf S I } \ ,
$$

这里S表示考虑上述两方面贡献后的总散射矩阵。对于一个符合时间反演对称性的散射系统，背散射系数中的反射与透射系数具有 $\mathit { \Pi } _ { \pi / 2 }$ 的相位差，反射系数表示为 $\boldsymbol { r }$ ，透射系数则表示为 $i t$ ，且系统无能量损耗时，有 $| r | ^ { 2 } + | t | ^ { 2 } { = } 1$ 。进一步，可以将共振器与端口合并为一个整体，当成一个新的封闭共振系统，由于能量守恒，这个新的封闭共振系统也具有幅度a，则公式(11)可写作：

$$
\frac { d { \bf a } } { d t } = [ i \omega _ { 0 } - \gamma ] { \bf a } + { \bf D } ^ { \mathrm { T } } { \bf I } = i \omega { \bf a } \quad ,
$$

由此可以推导出BIC共振与端口耦合对输出波的贡献为：

$$
{ \bf D } { \bf a } = \frac { { \bf D } { \bf D } ^ { \mathrm { T } } { \bf I } } { i ( \omega - \omega _ { 0 } ) + \gamma } \quad ,
$$

因此，我们得到总散射矩阵为：

$$
{ \bf S } = { \bf C } + \frac { { \bf D } { \bf D } ^ { \mathrm { T } } } { i ( \omega - \omega _ { 0 } ) + \gamma } \quad ,
$$

此外，由于整体的能量守恒， $\mathbf { D }$ 、C和r不是独立的它们之间的约束关系为：

$$
\mathbf { D } ^ { + } \mathbf { D } { = } 2 \Gamma ,
$$

$$
\mathbf { C D } ^ { * } \mathbf { = } \mathbf { - } \mathbf { D } ,
$$

这里 $\mathbf { D } ^ { * }$ 和 $\mathbf { D } ^ { + }$ 分别为 $\mathbf { D }$ 的共轭和厄米共轭阵。考虑系统物理特征，并通过公式(15-16)的关系来确定矩阵D，带入公式(14)之后则可给出总散射矩阵S的解析表达式。

# 2.6电磁多极理论

理解BIC性质的理论仍在进一步发展，代表性的还有电磁多极理论[106]。在过去几年中，电磁多极理论作为处理系统基本共振的研究工具受到了纳米光子学领域的广泛关注。多极分解技术是电磁多极理论具体表现，该技术将任意场分布表示为一组多极子创建的场的叠加，在数学上是把任意场用级数展开，不同多极子的贡献体现在多极展开的数学结果之中。多极展开已被广泛用于确定单粒子及其团簇（包括等离子体和电介质）散射场的偏振和方向图，适用于各种领域，例如偏振控制、电介质纳米天线和光解复用。多极分解方法解释了许多新的光学现象，如anapole效应、光机械效应和克尔克效应[107-109]。

V.Savinov等人总结了不同多极子的特征及其远场辐射的物理图像[110],这使得我们更容易从电磁多极的角度理解BIC的形成。多极子主要分为三大系列，分别为电多极子、磁多极子和环形多极子，每一个系列又可分为偶极子、四极子和八极子，它们被直观的表示在图6a。电偶极子和磁偶极子是我们熟知的，也是电磁领域最早提出的两类最基本的多极子；电偶极子由一个正负电荷对组成，电荷沿着极距方向运动；磁偶极子是一个振荡的环形电流，磁距位于电流环中心，且垂直于电流环所在平面。环形偶极子的概念在 2010 才被确立[I]，它由振荡的角向电流产生，角向电流沿着圆柱环的子午线流动，直观上可以看成是无数磁偶极子首尾相连，环偶极距位于圆柱环中心，且垂直于圆柱环所在平面。一直以来研究者将环形偶极子称为独立于电偶极子和磁偶极子之外的第三个电磁场源，因为在做多极展开的时候，取近似的处理方法导致最后得到独立的这一项，但近期研究发现环形偶极子包含在电偶极子的表达式中，实际是电偶极子的高阶项[112,113]。这三类偶极子是构成该系列下一级成员的基础，例如，四极子是由两对反向对齐的偶极子创建，八极子由反向对齐的四极子创建。所有多极子在其极距方向没有电磁辐射场，电磁场往极距以外的方向辐射。

明确不同多极子的辐射图像使得在直觉上理解BIC的形成变得容易。如图6b，在亚波长结构阵列中，每个多极子都对远场有贡献，可能存在一个方向，其中没有任何多极子对远场有贡献，或者不同项的非零贡献最终可能为零。具体而言（图6c)，位于I点的对称保护BIC在沿 $z$ 轴方向上没有远场辐射，每个元胞内的每一种多极子的场在 $\textbf { z }$ 方向上都没有辐射，因此总辐射为零。非Γ点上，对于特定的方向 $k$ ，虽然每一个多极子都可能具有辐射，但所有多极子的辐射相加可能为零，此时形成干涉相消型BIC（也叫调参BIC或偶发BIC）。

![](images/52f436ba4ef9ddff69fa9be8d8ad524687e8f47329e466e1b9b3c20c890c4775.jpg)  
图6BIC的电磁多极理论。(a)电磁多极子构造及其辐射图像[11l;:(b)周期结构中多极子辐射示意图，以及(c)对称保护型 BIC和偶发BIC 的多极子作用机制[106]

Fig.6.ElectromagneticultipoletoryofICs.(a)Electromagneticultiolestructureanditsdiatioimageol; (b)sematic diagramof multipoleradiation in periodic structure,and(c）multipole interaction mechanismof symmetry-protected BICand accidental BIC [106]

# 3BIC应用所依赖的基础特性

动量空间中复杂偏振分布与高品质因子是BIC的两大基础物理特征，它们奠定了光学BIC的一系

列应用。

# 3.1动量空间中的辐射偏振特性

偏振是电磁波最基本的特性之一。偏振控制在三维成像、光通信和量子光学等许多领域都非常重要。作为光偏振调制元件，传统的波片和偏振器显得笨重且功能单一，近年来，人们越来越关注使用紧凑的亚波长周期结构器件来调制光的偏振，它们更适用于片上器件。光子晶体板在偏振调制中的应用引起了人们的兴趣，具有制作简单、能带结构可设计以及动量空间中与BIC拓扑连接的复杂偏振特征[63]，这有利于偏振调制。对于二维光子晶体平板，存在一系列具有不同频率和波矢的布洛赫共振模式形成光子带。这些模式在任意频带上的辐射偏振态可以投影到结构平面并映射到布里渊区，这定义了动量空间中的偏振场。这些布洛赫模式大多是辐射模式，除非干涉相消或对称性失配使其成为非辐射模式，即BIC。BIC在该场中表现为漩涡奇点（V点）[63]，偏振态无法确定，而布里渊区中围绕BIC的偏振态则是线性的，且表现出涡旋变化（图7a)，这种偏振特性可能在拓扑光子学中产生新的物理现象。

为了表征系统的偏振特性，可以将布洛赫模式的极化状态映射到庞加莱球面上，其坐标由斯托克斯参数 ${ \bf { S } } _ { 0 }$ 、 $\mathbf { S } _ { 1 }$ 、 $\mathbf { S } _ { 2 }$ 和 ${ \bf S } _ { 3 }$ 指定。庞加莱曲线的覆盖率表征了系统的偏振特性。基于BIC的光子晶体板仅支持偏振几乎为线性的共振态，从布里渊区投影到归一化庞加莱球上的相应偏振图是赤道附近的一条带加上一个奇点。BIC光子晶体板的动量空间偏振态仅覆盖庞加莱球面上的一小部分区域，没有两极（圆极化状态）的覆盖，表明其在全斯托克斯偏振调制中的能力有限，这将限制光子晶体板的应用。复旦大学资剑教授团队通过打破光子晶体板面内$\mathbf { C } _ { 2 }$ 对称性(图 7b)，消除了光子带上的涡旋偏振奇点（V点）[114]。当奇点被破坏时，偏振态主轴的缠绕被保留，导致在I点附近产生成对的圆极化态（C点）。利用围绕原始BIC位置的线偏振态线（L线），C点的生成甚至可以实现庞加莱球面上的全覆盖(图7c)，这种现象为调制偏振提供了一种新的自由度，C点可以在光与物质相互作用中找到应用。

![](images/938bf12a0d5d7fadd8509d5ea27aaacc91d9ea798a63a55f21d3464b144471e8.jpg)  
图7BIC 与准 BIC 在动量空间中的辐射偏振特性[14]。(a)以对称保护型 BIC 为例的动量空间中的辐射偏振态；(b)打破 $C _ { 2 }$ 对称性后，动量空间辐射偏振态变化示意图；(c)准BIC的动量空间辐射偏振态可覆盖整个庞加莱球面 Fig.7.RadiationpolarizationcharacteristicsofBICsandquasi-ICs inmomentumspace4l.(a)Teradiationpolarzationstates in themomentum space with thesymmetry-protected BICasanexample;(b)theschematicdiagramforthechangeof theradiation polarization states in momentum space after breaking the $\mathbf { C } _ { 2 }$ symmetry; (c) radiation polarization states in momentum space of the quasi-BIC can cover the entire Poincaré sphere

# 3.2高品质因子与动态BIC

实验中，支持准BIC的周期结构的Q因子很容易达到 $1 0 ^ { 2 } – 1 0 ^ { 4 }$ 量级，但仍然还有进步空间。限制准BIC的Q因子的部分原因有材料吸收、有限的样品尺寸以及样品加工缺陷所引起的散射损耗，这是许多高Q值片上谐振器的常见问题。2019年，北京大学彭超课题组通过将动量空间中多个BIC向一个BIC 整合，极大提高了准 BIC的Q因子[115]，他们考虑圆形孔洞方形格子的光子晶体板，在横电模中发现动量空间中九个BIC，每个BIC在动量空间偏振场中表现为拓扑缺陷（漩涡)，拓扑荷数为 $\pm 1$ 。在这九个漩涡中，一个由于对称性固定在布里渊区的中心，而其余八个漩涡的位置可以通过不同的系统参数来控制（图 8a)。当增加孔洞尺寸时，八个偏心BIC向中心移动，直到所有九个BIC合并为一个BIC（图 8b)；进一步增加孔洞尺寸，这种BIC持续存在。BIC的拓扑配置控制所有附近共振的辐射损耗，孤立BIC的Q因子随着动量空间中 $k$ 的变化呈二次衰减 $( { \bf Q } \propto 1 / { \bf k } ^ { 2 } )$ ，然而，在所有九个BIC合并的过程中，辐射损耗被抑制，这种比例变化为$\textstyle \operatorname { Q } \propto 1 / \operatorname { k } ^ { 6 }$ ；合并BIC的Q值始终比 $k$ 空间中所有方向上的孤立BIC的Q值高几个数量级（图8c)，实验中这种合并BIC的Q因子可达到 $1 0 ^ { 5 }$ 量级。2022年，在BIC合并设计的基础上，一种通过进一步阻止横向泄露而提高Q因子的方法被提出，这种结构用光子带隙镜封装微型BIC，使用横向异质结构，以防止横向泄漏，实验中的Q因子被提高到 $1 0 ^ { 6 }$ 量级[116]。

![](images/0d4cbdb79f783d439cda37a53f4bc5799cf06ffea5fb379202bf2948b27b718e.jpg)  
图8高品质因子准 BIC 与动态 BIC构建。(a)支持九个BIC 的光子晶体平板，(b)调节周期尺寸，九个BIC 逐渐合并成一个 BIC；(c)合并前后准 BIC的Q因子变化图，合并的准 BIC 的Q因子始终大于孤立准 BIC 的Q因子[I5]；(d-e)基于光掺杂矩 形硅和圆柱硅的动态 BIC 结构和功能示意图[11,119]；(f)图形化石墨烯-金属超表面器件图，该器件通过调节石墨烯费米能级 实现 BIC与准BIC动态切换[120]

Fig.8.Construction forquasi-BICswith highQfactoranddynamic BICs.(a)Photonic crystal slab supporting nine BICs,(b) adjustingthe periodsize,thenineBICsaregraduallymerged intoone BIC;(c)theQfactorchange diagramof thequasi-BICbefore andafterthe merger,wheretheQfactorof the mergedquasi-BICisalways greaterthan thatof isolatedquasi-BICll;(d-e) schematicdiagramsforthestructureandfunctionofdyamicBICsbasedophoto-dopedrectangularandcylindricalsilicon9]; (f)animagesofapattemedgraphene-metalmetasurfacedevicebytuning thegrapheneFermi-energylevelrealizes dynamic

BIC是光与物质的一种强相互作用，除了固定的提高准BIC的Q因子，人们也希望可以掌握这种相互作用的程度。SongHan 等人基于全硅介质设计了支持准BIC的超表面，使用光子能量大于硅带隙的短脉冲光泵在材料中产生可调的自由载流子，光生载流子的复合动力学可以在超快时间尺度上定制，实现对准BIC品质因子的超快动态控制(图8d)[117]。这种技术的基本机制是通过光掺杂或等效的复折射率来修改复本征频率，增加非辐射损耗率并降低Q[118]。Kebin Fan 等人也使用此原理，基于一个支持高Q准BIC的全硅浮空圆柱周期薄板，通过光掺杂对硅载流子密度进行修改，从而实现对Q因子的控制，Q因子动态变化超过两个数量级（图8e）[119]。除了光掺杂调制技术外，电掺杂调制技术也被提出，通过将图形化的石墨烯引入支持BIC或准BIC的金属超表面中，石墨烯位于金属结构层下，衬底使用硅，在硅衬底和金属间施加电压，使硅中的载流子注入到金属结构与衬底之间的石墨烯中，实现石墨烯电导率在类半导体和类金属相之间动态切换（图8f）[120]；当石墨烯费米能级较低时，石墨烯作用可以忽略，等于没有石墨烯，但当石墨烯费米能级升高时，石墨烯载流子数量增大到可以与金属类比，此时图形化的石墨烯就等同一个同样图案的金属；石墨烯费米能级从小到大调节时，等效于金属结构从缺损变换到完整，可以实现整个超表面在BIC与准BIC状态之间状态切换。

# 4BIC的应用及原理

# 4.1窄带滤波与高灵敏度传感器应用

在一段光谱范围内存在一个尖锐的准BIC共振峰，这一直观特点很容易使人联想到空间光通讯中的滤波器应用。2014年，J.M.Foley等人报道了基于绝缘体上硅制成的悬浮硅光栅窄带透射滤波器，该平台在长波红外光谱下工作。该工作原理涉及将入射光耦合到频率重叠且具有不同耦合强度的两个光栅模式。强耦合模式产生宽谱反射共振，这提供了低的背景透射率，而作为弱耦合模式的对称保护型准BIC则在背景内产生窄透射峰，因此实现窄带透射滤波（图9a）[71]。利用准BIC的高Q特性也容易实现高灵敏度传感，且检测极限低[121-123]；环境折射率变化使得准BIC的谐振峰位移，各种生物和化学分子，如蛋白质、细胞、甘油等都可以引起环境折射率变化，比如通过集成微流道实现实时、快速的液体折射率检测[72]，在生物化学领域检测细胞、蛋白质及葡萄糖浓度等（图9b-c）[124,125]。

![](images/7b301582d88f394610e8dafb58ca82e327483b8ee5b19111a33da73b93b50538.jpg)  
图9BIC 在窄带滤波与传感方面的应用。(a)支持准 BIC的光子晶体光栅，准BIC在低透射率背景下出现窄透射峰，实现空 间窄带滤波功能[71]；(b)基于八字椭圆条的准 BIC高灵敏分子传感器[124]；(c)基于月牙形的准 BIC高灵敏度折射率传感器[125] Fig.9.AppicationsofBICsinnarrowbandfilteringandsensing.(a)Photoniccrystal gratingsupportingquasi-BIC,quasi-BIChas

narrowtransmissonpeaks inthelowbackgroundtransmtance,andrealizes thefunctionofspatialnarrow-bandfiltering;(b) high-sensitivemolecularsensorbasedoapairof inclinedelipticalbarssupportingquasi-BIC24l; (c)high-sensitivityrefractive index sensor based on crescent shape supporting quasi-BIC [125]

![](images/e28ac27a057633e6e22681d327de2bd2faeb4fc603c0dcd3c821d119e5b5939a.jpg)  
图10BIC 像基应用。(a)准 BIC 分子光谱编码像素阵列，(b)所有像素的工作频率覆盖的光谱范围，(c)不同分子编码图像结 果示意图[73]；(d)准 BIC边缘检测超表面，(e)在准BIC频率附近一个频率下的调制传递函数，(f)边缘成像效果图[74] Fig.10.Imaging-basedapplicationsofBICs.(a）Themolecularspectral encodedpixel arrybasedoninclined elipticalbars supportingquasi-BIC,(b)thespectralrangecoveredbytheoperatingfrequenciesofallpixels,(c)theschematicresultsofdierent molecularlyencodedimages 3l; (d)edgedetectionbasedonmetasurfacesupportingthequasi-BIC,(e)modulationtransferfunction at a frequency near the quasi-BIC frequency, and (f) edge imaging results [74]

# 4.2光谱编码与边缘检测等像基应用

将BIC工作频率设计到生物分子的振动频率，并通过特殊几何设计获得覆盖一个宽波段的所有谐振频率。最终组成一个多像素阵列，每一个像素都包含多个相同的单元，每一个像素都对应一个特定的工作频率。生物分子被涂覆于超表面上，当生物分子振动频率与超表面BIC工作频率一致时，反射频谱中对应位置将实现剧烈增强，从而识别出不同生物样本，并为不同生物样本标记出特定的光谱条码。这一思想由Andreas Tittl等人于2018年提出[73],使用支持对称保护准BIC的全介质八字形椭圆条，通过缩放元胞来使准BIC频率移动，有限个相同的元胞组成一个像素，多个像素集成到同一个平面，不同像素之间的元胞缩放比例不同，因此对应到不同工作频率，最终组成了一个离散化的光谱范围覆盖 $1 3 5 0 \mathrm { c m } ^ { - 1 }$ 到 $1 7 5 0 \mathrm { c m } ^ { - 1 }$ 的多像素阵列(图10a-b)。

这样的光谱范围包含碳氢化合物和氨基酸中发现的特征性分子拉伸和弯曲振动，适用于检测和区分生物分子、环境污染物和聚合物等物质的吸收特征，涵盖生物传感和环境监测等应用。由于光谱频率变化紧凑，这使得该器件可以在多个光谱点读取分子吸收特征，然后将所得信息转换为类似条形码的空间吸收图进行成像（图10c)，此项技术可以在不需要光谱分析、频率扫描或移动机械部件的情况下解析物质的吸收指纹，在灵敏和多功能的微型中红外光谱设备领域充满潜力。进一步地，AleksandrsLeitis等人在2019年提出使用同样的八字形椭圆条[65]，利用光谱角度复用方法，区分各种生物分子的吸收光谱。通过中红外光的入射角度控制光谱的位置，利用单片超表面提供不同频点的共振，通过将每个入射角的反射率信号与相应共振频率的分子吸收强度匹配，可以实现对不同表面吸附分子的中红外吸收指纹特征的检测。这种方法可以通过使用一个宽带光源和探测器实现，无需光谱仪，降低了研究成本，为高灵敏、无标记生物传感开辟了新道路。

改变入射波矢，对称保护型BIC泄露成准BIC，泄露率伴随波矢单调变化，这为图像边缘增强提供了应用基础。基于边缘增强的图像处理对于数据压缩、物体检测、显微镜和通用计算机视觉特别有用，在生物成像、三维重建和自动驾驶汽车领域具有潜在应用价值。边缘增强使用空间差分实现，空间差分可以基于电子或光学架构。光学模拟计算具有直接使用光学信号处理信息的能力，它可以最小的功耗执行大规模实时数据处理。传统光学基于透镜和滤波器系统的傅里叶方法模拟图像差分，这运用到多个常规透镜(如4f傅里叶滤波中的透镜)，由此导致较大的形状因子，与紧凑型集成系统不兼容。采用周期光学结构，如超表面和光子晶体，用于光学图像处理可以显著减小光学系统尺寸。为了有效识别图像边缘的高阶衍射分量，要求周期结构对围绕垂直方向的一个小波矢方向范围内的入射光具有梯度增强的响应，这种响应在数学上表示为调制传递函数。对称保护型BIC对入射波矢具有敏锐的响应，基于这一特点，YouZhou等人证明了在超表面器件所支持的BIC频率附近可以找到一个特别的频率，在这个特别的频率下，容易构建满足要求的调制传递函数，该函数虽然不直接依赖于BIC频率，但确实受到BIC效应的诱导（图10d-f）[74]。

![](images/10d5797ce99d83d3f7452b309e1c3384607897953cd1f76a7d0a3448e2e1fadd.jpg)  
图11BIC 在非线性领域的应用。(a)用于产生倍频光的T字准 BIC 器件，(b-c)分别表示三次谐波和二次谐波强度与普通器件的效果对比[126]；(d)用于产生微激光的准 BIC超表面，(e)泵浦功率对光发射波长和功率的影响，(f)泵浦功率与激光输出功率的关系[76]；(g)基于准 BIC 的光馈天线样品图，及其(h)光发射方向示意图[127]

Fig.11ApplicationsofBICsin nonlinear field.(a)AT-shapedquasi-BICdeviceforgenerating frequencydoublinglight,(b-c) respectivelyshow thecomparisonof thethird harmonicandsecond harmonic intensitieswiththoseofordinarydevices[26]; (d) quasi-BIC metasurfaceusedto generate microlaser,(e)theefectof pumppoweronlight emission wavelengthandpower,(f)the relationship betweenpumppowerandlaseroutput power 76]; （g)sample diagramofoptical feed antenna basedonquasiBICand its (h) schematic diagram of light emission direction [127]

# 4.3非线性光变频、微激光及微纳天线应用

光对物质的极化作用除了一阶线性效应还有高阶的非线性效应。一般情况下，光与物质的相互作用较弱，主要表现为一阶线性极化。然而，BIC是一种光与物质的强相互作用，这种作用效果对二阶甚至三阶非线性极化都十分突出。2018 年，LucaCarletti等人理论上提出了采用BIC概念来大幅提高微尺度非线性响应的策略，通过构建支持BIC的AIGaAs纳米天线，其倍频转换效率与传统技术相比可以提高至少两个数量级，且器件体积更小，该项工作为光学高效变频技术奠定了新的理论基础[75]。2019 年，中山大学刘进教授实验上提出一种超高Q的对称保护型准BIC超表面，该超表面器件基于硅薄膜，单元结构设计为T字形矩形块(图11a-c)[126]，用频率与准 BIC 频率一样的光作为泵浦源，成功激发材料的非线性效应，由此产生强的二倍频和三倍频光，与常规激发无结构的硅薄膜相比，激发准BIC硅超表面能够产生强度高达几个数量级的倍频光。

腔在从量子力学到电磁学的波动现象中起着基础作用，并决定着激光的时空物理。一般来说，它是通过关闭所有可以逃逸波的通道来构建的。理想的激光腔只预留了唯一的光逃逸通道，这一通道作为光能量在腔体内共振增强到某一阈值时的输出通道，输出的光是具有高品质因子的激光。周期光学结构所支持的BIC就是一个微型共振腔，它将光模式约束在结构中，因而具有极高的品质因子，当频率低于衍射限时，只有唯一的垂直于结构表面的零阶辐射通道，这些属性表明BIC超表面具有产生激光的潜力。2017年，AshokKodigala 等人基于InGaAsP量子阱材料[76]，设计了一个支持BIC的二维周期浮空平板（图11d-f)，该平板是有限大的，因此实际上支持有限Q因子的准BIC，准BIC频率位于InGaAsP材料的光致发光频率中。用 $1 0 6 4 ~ \mathrm { { n m } }$ 的纳秒激光器泵浦，随着泵浦功率增高，器件发生从自发辐射到高Q受激辐射的转变，形成波长1.55$\mu \mathrm { m }$ 激光，且设计Q因子越大，泵浦阈值越小。

对于 $x$ 和 $y$ 方向上周期尺寸相同的二维微型激光腔，它所支持的准BIC的泄露通道被限制到垂直结构面方向。若仔细调整其中一个周期以支持共振波长处的一个衍射级次，辐射泄漏通道将被打开；通过这种方式，可以控制激光发射的方向性，从而应用到微型发射天线领域。SonTungHa 等人在2018年报道了一种光馈发射天线，该天线是二维砷化镓纳米柱阵列，由石英基板支撑，纳米柱支持垂直和平面内偶极子共振。在其中一个方向上，晶格的周期对砷化镓光致发光带内的一个工作波长是亚衍射的，而在另一个方向上的周期对该工作波长是衍射的。该设计打开了一个辐射通道，将亚衍射情况下的BIC模式转变为具有有限Q因子的泄漏共振，并在发射平面中呈现与 $k$ 的交叉点（图11g-h）[127]。除了控制发射方向外，Remi Colom 等人利用介电纳米盘阵列构建高Q准BIC，准BIC频率与纳米盘结构的偶极子天线发射频率重叠，理论上证明了准BIC可以极大增强天线发射效率[77]。

# 4.4动量空间中涡旋束产生及偏振操控

正如3.1章节所提到的那样，T点BIC具有完全不辐射的性质，其在动量空间中是一个偏振涡旋奇点，具有非零偏振拓扑荷数 $\boldsymbol { q }$ ，而在Γ点周围，布洛赫共振模的辐射偏振态是线性的，且缠绕I点以涡旋形式变化。这种线偏振涡旋特征可分解为一束左旋圆偏振和一束右旋圆偏振波分别携带方向相反、大小为2q的相位拓扑荷数在动量空间中叠加，数学上可以通过时域耦合模式理论来解释[79]。因此，BIC超表面可以在动量空间中对输入圆偏振波进行波前涡旋变换，2020 年，哈尔滨工业大学宋青海教授团队和复旦大学资剑教授团队在实验上陆续演示了这项有趣的功能（图12a-b）[78,79]。此外，由于光子晶体相较传统产生涡旋电磁波的Q波片、涡旋板等结构更加简单、轻便；针对现今产生涡旋太赫兹光束的传统方法的不足，本课题组正利用二维光子晶体动量空间中的连续域束缚态，结合太赫兹圆极化天线，在 $2 2 0 \mathrm { G H z }$ 的太赫兹波段，制作了涡旋拓扑荷可调的太赫兹涡旋天线，使太赫兹波传输携带更丰富的物理信息，样品示意如图12(c)。

基于BIC的涡旋产生颠覆了人们对涡旋操控的认知。传统上，涡旋光产生主要针对实空间，实空间产生涡旋光的方法是用厚重的涡旋相位片；近年来，研究人员开发出体积小的相位超表面器件来操控实空间中的涡旋光产生，但这样的器件具有可见的涡旋式几何排列构型。BIC超表面作为在实空间的周期性结构，没有呈现可见的涡旋几何构型，直觉上并不能实现涡旋光束的产生，但其在动量空间中确实具备产生涡旋光的能力，这项特殊的能力可能使得BIC超表面比传统相位超表面在保密电磁通信领域更有优势。

虽然I点BIC在动量空间中是偏振奇点，但BIC一旦泄露成准BIC，奇点被破坏，其辐射偏振态在动量空间中的I点上将被确定。适当调整结构几何参数，准BIC的I点辐射偏振也可能具有明显的椭圆率，这意味左旋圆偏振和右旋圆偏振态解耦，手性特征产生。AdamOvervig等人基于空间紧密堆叠结构，构建了面内 $\mathbf { C } _ { 2 }$ 对称性破坏的准BIC，理论上证明了这种准BIC的I点辐射偏振态可以是任意椭圆，并提出手性准BIC的概念[128]。Maxim V.Gorkunov等人基于成对椭圆条，构建面外 $\mathbf { C } _ { 2 }$ 对称性破坏的手性准BIC，且结构具有面内 $\mathrm { C } _ { 4 }$ 对称性，致使在垂直光入射下产生的散射波理论上具有完美的窄带圆二色性，并基于时域耦合模理论得到了圆二色性的解析表达，证明了在准BIC 频率下将获得最大的圆二色性[80]。然而，上述两项工作所用的结构不具有上下镜像对称性（关于 $\textbf { z }$ 平面的镜像对称性)，因此很难在实际中制备出来。2022年，为了增强实际制备手性准BIC的可行性，暨南大学李向平课题组提出平坦手性准BIC，该手性准BIC在关于 $\textbf { z }$ 平面上下镜像对称的平坦结构中被设计，元胞是基于面内 $\mathbf { C } _ { 2 }$ 对称性破坏的介质柱，实验上成功验证了手性准BIC的窄带不对称传输能力（图13a-b)[129]。本课题组进一步提出了针对平坦结构中手性准BIC的构造方法及其散射矩阵解析式，通过同步打破矩形介质块的结构面内 $\mathbf { C } _ { 2 }$ 对称性和面内镜像对称性，准BIC的I点将获得椭圆辐射偏振态（图13c-d)，在这样的结构中，除了发现联系到面内 $\mathbf { C } _ { 2 }$ 对称性破坏的手性准BIC外，与干涉相消作用相联系的手性准BIC 也被发现[130]。手性准BIC表现出的超窄带不对称传输能力可能在手性分子传感领域得到应用。

![](images/2fd35c4725d3594793c175b16b20308ca38b7da3f79d97f95853b68ce6234e08.jpg)  
图12BIC在涡旋束产生领域的应用。(a)基于BIC光子晶体板的动量空间涡旋束产生示意图，(b)动量空间辐射偏振分布（左)和圆偏振入射时测试的电场相位和强度分布（右）[78.79]；(c)本课题组正将 BIC 光子晶体板与太赫兹圆极化天线结合以制作涡旋拓扑荷可调的太赫兹涡旋天线

Fig.12.Applications ofBICs in thefieldof vortex beam generation. (a)Schematicdiagramfor vortex beamgenerationinmomentum spacebasedonphotoniccrystalplatesupportingBIC,(b)theradiationpolarzationdistribution inmomentumspace(leftandelectric field phaseandintensitydistributionundercircularlypolarized incidence (right)[78,79l;()Ourgroupiscombining BICphotonic crystal slab with THz circularly polarized antenna to makeTHz vortex antenna with adjustable vortex topologicalcharge

![](images/4bb6fdde0e329abc587d38228ff0021a8911cec0b0c841bd356d80b50afffcb8.jpg)  
图13BIC 在不对称传输领域的应用。(a)支持手性准 BIC 的平坦结构器件图，及其(b)圆偏振透射谱和圆二色性谱[129]；(c)基于面内 $\mathbf { C } _ { 2 }$ 对称性和面内镜像对称同步破坏的手性准 BIC器件示意图与动量空间偏振分布，及其(d)包含多个手性准 BIC 的圆二色性谱[130]

Fig.13.Applications ofBICs in thefieldof asymmetric transmision. (a)schematicdiagramoftheplanar structure devicesupporting thechiral quasi-BIC,andits(b）circularlypolarized transmissonspectrumand circulardichroismspectrum29];(c）schematic diagram for a metasurface supporting the chiral quasi-BIC,with in-plane $C _ { 2 }$ symmetry and in-plane mirror symmetry breaking simultaneously(eft),anditspolarzationdistributioninomentumsace(ight),and(d)itsiculardichroismspectruotaing multiple chiral quasi-BICs[130]

# 5结束语

本文系统性地总结了周期光学系统中出现的三大类型BIC，包括对称保护型BIC、共振耦合型BIC以及单共振型BIC，同时阐述其基于对称性理论、时域耦合模理论、耦合波理论以及电磁多极理论的物理数学解释；进一步，综述了周期系统中光学BIC的有趣的物理特性，例如，高Q因子特性和动量空间中的特殊偏振分布特性，基于这些特性，光学BIC带来了丰富的应用，包括窄带滤波、高灵敏度传感、分子光谱编码成像、图像边缘检测、非线性光倍频、微激光、微天线、动量空间中的涡旋光产生以及窄带不对称传输等。

高Q光学准BIC也存在一些缺陷，一方面，它对结构尺寸参数异常敏感，轻微的尺寸参数变化可能造成巨大的频点偏移，需要极高的加工精度。另一方面，介质材料的本征损耗会增强共振阻尼致使Q因子下降，因此一般基于金属材料的准BIC都很难获得两个数量级以上的Q因子，高折射率、低损耗的全介质材料是制备高Q因子准BIC的理想选择，Q因子可达三到四个数量级，但要维持四个数量级以上的超高Q因子，一般会选用极薄衬底，甚至抛弃衬底，选用介孔平板结构或者浮空结构；在太赫兹频率之上，无衬底结构厚度较薄，尤其是浮空结构，其横向尺寸极细，加工难度相当大，容易破损，成功率低(即便是选用极薄衬底也很难制备）。此外，超高Q因子光谱要求高精度的测试平台，这提高了测试成本，虽然在可见光到近红外波段也能够完成四个数量级及以上的Q因子测试，但在远红外到太赫兹甚至微波波段，受制于光源和光谱仪技术的发展，几乎不可能完成如此高Q因子的超高分辨率光谱测试，这限制了高Q准BIC的多波段应用。

可以期待的是，虽然BIC的诸多应用由于制备和测试的高难度、高成本问题仍被限制在实验室展示阶段，但伴随着光学BIC的持续研究，它将离工业化应用越来越近，未来可能涌现出更多奇异特性和新应用，为集成光学、信息光学、生物光学、拓扑光学以及非线性光学等领域的发展提供创新活力。

# 致谢

此项工作收到国家重点研发计划（Nos.2021YFB2800703,2017YFA0700202,2007CB310403）和国家自然科学基金 (61735010)的支持

# 参考文献：

[1] NEUMANNJV, WIGNER EP. Uber merkwurdige diskrete Eigenwerte[M]. Zhurnal Physik,1929.   
[2] VOO K-K. Trapped electromagnetic modes in forked transmisson lines[J]. Wave Motion,2008,45(6): 795-803.   
[3] CALLAN M,LINTONCM,EVANS D V. Trapped modes in two-dimensional waveguides[J].Journal of Fluid Mechanics, 1991, 229: 51-64.   
[4] COBELLIPJ,PAGNEUX V, MAUREL A,et al.Experimental observation of trapped modes in a water wave chanel[J]. Europhysics Letters,2009,88(2).   
[5] COBELLIPJ,PAGNEUX V,MAUREL A,et al.Experimental study on water-wave trapped modes[J]. Journal of Fluid Mechanics,2011,666: 445-476.   
[6] LINTON C M,MCIVERP.Embedded trapped modes in water waves and acoustics[J]. Wave Motion,2007,45(1-2):16-29.   
[7] HEIN S,KOCH W,NANNENL. Trapped modes andFano resonances in two-dimensional acoustical duct-cavitysystems[J]. Journal of Fluid Mechanics,2012, 692: 257-287.   
[8] LYAPINA A A, MAKSIMOV D N,PILIPCHUK A S,et al. Bound states in the continum in open acoustic resonators[J]. Journal of Fluid Mechanics,2015,780: 370-387.   
[9] ALSHITS V1, DARINSKII AN,SHUVALOVAL. Elastic waves in infinite and semi-infinite anisotropic media[J].Physica Scripta, 1992, T44: 85-93.   
[10] EVERYAG.Guided elastic waves ataperiodicarayof thincoplanar cavities inasolid[J].Physical ReviewB,2Oo8,78(17).   
[11]BULGAKOVEN,SADREEVAF.Bound states in thecontinuum in photonic waveguides inspired by defects[J].Physical Review B,2008,78(7).   
[12] MARINICADC,BORISOVAG,SHABANOV S V.Bound States in the continum in photonics[J]. Physical Review Letters, 2008,100(18):183902.   
[13]LONGHIS.Optical analogof populationtrappng inthecontinuum: Classicalandquantumiterference efects[J].Physical Review A,2009,79(2).   
[14]POTNIKY,PELEGODREISOWF,etal.Experimentalobservationof optical bound states inthecontinuum[J].Phsical Review Letters,2011,107(18): 183901.   
[15] LEE J,ZHENB,CHUASL,etal. Observationand differentiationofuique high-Qopticalresonances near zero wave ector in macroscopic photonic crystal slabs[J]. Physical Review Letters,2012,109(6): 067401.   
[16]WEIMANN S,XUY,KEILR,etal. Compactsurface Fano states embeddedin thecontinumof waveguidearys[J]. Physical Review Letters,2013,111(24): 240403.   
[17]BULGAKOVEN,SADREEVAFRobust bound state inthe continuum in a nonlinear microcavity embedded inaphotonic crystal waveguide[J]. Optics Letters,2014,39(17): 5212-5215.   
[18]YOONJW,SONG SH,MAGNUsSONR. Criticalfield enhancement of asymptoticoptical bound states inthecontium[J]. Scientific Reports,2015,5:18301.   
[19]ZHANG M,ZHANG X.Ultrasensitive optical absorption in graphenebasedonbound states inthecontinuum[J].Scientific Reports,2015,5: 8266.   
[20] BULGAKOVE N,SADREEVAF. Transferof spin angular momentum of an incident wave into orbital angular momentum of the bound states in the continuum in an array of dielectric spheres[J]. Physical Review A,2O16, 94(3).   
[21]LIL,YINH. Bound States in the Continuumin double layer structures[J]. Scientific Reports,2O16,6: 26988.   
[2]NIL,WANG Z,PENG C,etal.Tunableoptical boundstates inthecontinuumbeyond in-plane symmetry protection[J]. Physical Review B,2016,94(24).   
[23]GOMIS-BRESCO J,ARTIGAS D,TORNER L.Anisotropy-induced photonic bound states in thecontinuum[J].Nature Photonics,2017,11(4): 232-236.   
[24]SADREEV AF, PILIPCHUK A S,LYAPINA A A. Tuning of Fano resonances by rotation of continuum: Wavefaucet[J]. Europhysics Letters,2017,117(5).   
[25]SADRIEVA Z F,SINEVIS,KOSHELEV K L,et al. Transition from Optical Bound States in the Continuum to Leaky Resonances: Role of Substrate and Roughness[J]. ACS Photonics,2017,4(4): 723-727.   
[26]BULGAKOVEN, MAKSIMOVD N,SEMINA PN,et al. Propagating bound states in thecontinuum in dielectric gratings[J]. Journal of the Optical Society of America B,2018,35(6).   
[27]KOSHELEV K L，SYCHEV S K， SADRIEVA ZF,et al. Strong coupling between excitons in transition metal dichalcogenides and optical bound states in the continuum[J]. Physical Review B,2018,98(16).   
[28]LIUM,CHOIDYExtreme Huygens'Metasurfaces Basedon Quasi-Bound States inthe Continuum[J]. Nano Leters,2018, 18(12): 8062-8069.   
[29]MINKOVM, WILLIAMSONIAD, XIAOM,et al. Zero-Index Bound States in theContinuum[J]. Physical ReviewLeters, 2018,121(26): 263901.   
[30]LIS,ZHOUC,LIUT,etal.Symmetry-protectedboundstates intecontinuumsupportedbyal-ielectric metasfaces[J]. Physical Review A, 2019,100(6).   
[31]YUZ,SUNX.Acousto-optic modulationof photonic bundstate inthecontiuum[J].Light:Science &Applications220,9: 1.   
[32]YU Z,TONG Y,TSANG HK,etal. High-dimensional communicationonetchless ithium niobate platform withphotonic bound states in the continuum[J]. Nature Communications,2O2o,11(1): 2602.   
[33]LIZ,LIUW,GENGG,etal.MultiplexedNondifractingNonlinearMetasurfaces[J].AdvancedFunctionalMaterials,0, 30(23).   
[34]LIJ,IJZHENGC,etalBroadbandandtunable teraertzabsorptionviapotogeneratedcarrersiudopedsion[J]. Science China Physics,Mechanics & Astronomy,2021,65(1).   
[35]LIJ, ZHENG C,WANG G,et al. Circular dichroism-likeresponse of terahertz wavecaused by phase manipulation via all-silicon metasurface[J]. Photonics Research,2021,9(4).   
[36]YUE Z,LIUJ，LIJ，etal.Multifunctional terahertz metasurfacesforpolarizationtransformationand wavefront manipulation[J]. Nanoscale,2021,13(34): 14490-6.   
[37]柴若衡,刘文玮,程化,等．人工光学微纳结构中的连续体束缚态：原理、发展及应用［J]．光学学报，2021，41(4). CHAI R H,LIUWW,CHENH,et al.Bound States ofContinuum in Optical Artificial Micro-NanostructuresFundamentals Developments and Applicationsr[J]. Acta Optica Sinica,2021,41(4). (in Chinese)   
[38]LIJ，WANG G,YUEZ,et al.Dynamic phase assembled terahertz metalens forreversible conversionbetween linear polarization and arbitrary circular polarization[J]. Opto-Electronic Advances,2022,5(1): 210062.   
[39]LIJ,YUEZLIJ,etal.Wavefront-controllableal-sionterahertz met-polarer[J].cienceCinaaterials.   
[40]LIJ,YUEZ,LIJetal.iverseteraertzwavefrontmanipulations mpoweredbythespatiallyinterleaved metasufaces[J]. Science China Information Sciences,2022.   
[41]YUEZ,IJ,LIJ,etal.Terahertz metasurface zoneplates witharbitrarypolarzations toafixed polarizationconversion[J]. Opto-Electronic Science,2022,1(3): 210014.   
[42]YUE Z,LI J,LIUJ,et al. VersatilePolarization Conversion and Wavefront Shaping BasedonFullyPhase-Modulated Metasurface with Complex Amplitude Modulation[J]. Advanced Optical Materials,2022.   
[43]YUE Z,LIUJ,LIJ,etal. Vectorbeamgenerationbasedonspin-decoupling metasurfacezone plate[J].AppliedPhysics Letters,2022,120(19).   
[44]ZHENG C,LIJ,LIUJ,et al. Creating Longitudinally Varying Vector Vortex Beams withan Al-Dielectric Metasurface[J]. Laser & Photonics Reviews,2022.   
[45]ZHENG C,LI J,YUEZ,et al.Al-Dielectric Trifunctional Metasurface Capableof Independent Amplitude and Phase Modulation[J]. Laser & Photonics Reviews,2022,16(7).   
[46]KUPRIIANOVA S,XU Y,SAYANSKIYA,et al..Metasurface Engineering through Bound States in the Continuum[J].   
[47]ROMANO S,ZITOG,LARA YEPEZ SN,etal.Tuning the exponential sensitivityof abound-state-in-continumoptical sensor[J].Optics Express,2019,27(13): 18776-18786.   
[48]ABUJETAS DR, BARREDA A,MORENOF, et al.High-Q Transparency Band in Al-Dielectric Metasurfaces Induced bya Quasi Bound State in the Continuum[J]. Laser & Photonics Reviews,202o,15(1).   
[49]MURAI S,ABUJETAS DR,CASTELLANOS G W,et al.Bound States in the Continuum in the Visible Emerging from out-of-Plane Magnetic Dipoles[J].ACS Photonics,2020,7(8): 2204-2210.   
[50]OVERVIG A C, MALEK S C,CARTER MJ,et al. Selection rules for quasibound states in thecontiuum[J].Physical Review B,2020,102(3).   
[51]WANG X,DUANJ,CHEN W,etal.Controlinglight absorptionof grapheneat criticalcoupling through magneticdipole quasi-bound states in the continuum resonance[J]. Physical Review B,2O2O,102(15).   
[52]XIAOS,LIUT,WANG X,etal.Tailoring theabsorptionbandwidthofgraphene atcriticalcoupling[J]Physical ReviewB, 2020,102(8).   
[53]VAN HOOFNJJ,ABUJETAS DR,TER HUURNE SET,et al. Unveiling the SymmetryProtectionof Bound States inthe Continuum with Terahertz Near-Field Imaging[J]. ACS Photonics,2021, 8(10): 3010-3016.   
[54]ABUJETAS DR,VANHOOFN,TER HUURNE S,etal.Spectralandtemporal evidenceofrobust photonic bound states in the continuum on terahertz metasurfaces[J]. Optica,2019, 6(8).   
[55]BOGDANOVAA, KOSHELEVKL, KAPITANOVA PV,et al.Bound states in the continuum andFano resonances inthe strong mode coupling regime[J]. Advanced Photonics,2019,1(01).   
[56]CONGL，SINGHR.Symmetry-ProtectedDual Bound States inthe Continuum in Metamaterials[J].AdvancedOptical Materials, 2019.   
[57]KYAWC, YAHAOUIR,BURROWJA,et al. Polarization-selective modulationof supercavity resonances originating from bound states in the continuum[J]. Communications Physics,2020, 3(1).   
[58]LIANGY, KOSHELEVK,ZHANGF,etal.Bound Statesin theContinuuminAnisotropicPlasmonic Metasurfaces[J]. Nan Letters,2020,20(9): 6351-6356.   
[59]XIANGJ,XUY,CHEJ-D,etal.Tailoringthespatial localizationofbound stateinthecontinuuminplasmonic-dielectric hybrid system[J]. Nanophotonics,2020,9(1): 133-142.   
[60]NIUJ,ZHAI Y,HANQet al.Resonance-trappedbound statesithecontiuum inmetalic THz metasurfaces[J].Optics Letters,2021,46(2): 162-165.   
[61]DONG Z，MAHFOUD Z，PANIAGUA-DOMINGUEZ R， et al. Nanoscale mapping of optically inaccessble bound-states-in-the-continuum[J]. Light: Science & Applications,2022,11(1): 20.   
[62]SONGQJ,HUJS,DAIS W,etal. Coexistenceof anewtypeof bound state in the continuum andalasing threshold mode induced by PT symmetry[J]. Science Advcanced,2020, 6(34).   
[63]ZHENB,HSUCW,LUL,etal.Topological natureofoptical bound statesinthecontiuum[J].Physical ReviewLetters, 2014,113(25): 257401.   
[64]DOELEMAN HM, MONTICONEF,DEN HOLLANDER W,et al. Experimental observationof a polarization vortexat an optical bound state in the continuum[J]. Nature Photonics,2018,12(7): 397-401.   
[65]LEITISA,TITTLA,LIUMK,et al.Angle-multiplexedal-dielectric metasurfacesforbroaband molecularfingerprint retrieval[J]. Sci Adv,2019,5(5): eaaw2871.   
[6]KOSHELEVK,BOGDANOVA, KIVSHAR Y. Meta-optics and bound states in thecontinuum[J].Science Bulletin,2019, 64(12): 836-842.   
[67]KOSHELEVK,TANG Y,LI K,et al.Nonlinear Metasurfaces Governedby Bound States in the Continum[J].ACS Photonics,2019, 6(7): 1639-1644.   
[68]WANGY,HANZ,DUY,etal.Utrasensitive terahertzsensingwithhigh-Qtoroidal dipoleresonancegovernedbybound states in the continuum in all-dielectric metasurface[J]. Nanophotonics,2021,10(4): 1295-1307.   
[69]KANG M,ZHANG Z,WUT,etal.Coherent fullpolarizationcontrol basedonbound states in thecontinuum[J].Nature Communications,2022, 13(1): 4536.   
[70]KuHNERLORTNOL,BERTeR,etalRadialboundstatesinthecontinuumforpolarization-invariant nanophotoics[J], 2022.   
[71]FOLEYJM,YOUNG S M,PHILLIPS JD.Symmetry-protected mode coupling near normal incidence for narrow-band transmission filtering in a dielectric grating[J]. Physical Review B,2014,89(16).   
[72]ROMANO S,ZIO G,TORINO S,et al.Label-freesensing of ultralow-weight molecules with al-ielectric metasurfaces supporting bound states in the continum[J]. Photonics Research,2018, 6(7).   
[73]TITA,LESA,LIUK,etal.Imaging-basedmolecularbarcodingwithpixelateddielectric metasurfaces[J].ience, 2018,360(6393): 1105.   
[74]ZHOUY,ZHENG H,KRAVCHENKOII,etal.Flatoptics forimage diferentiation[J].Nature hotonics,20204(5): 316-323.   
[75]CARLETTIL, KOSHELEV K,DE ANGELIS C,et al.Giant Nonlinear Response atthe Nanoscale Driven by Bound States in the Continuum[J].Physical Review Letters,2018,121(3): 033903.   
[76]KODIGALA A,LEPETITT,GUQ，et al.Lasing action from photonicbound states in contiuum[J]. Nature,2017, 541(7636): 196-199.   
[77]COLOMR,BINKOWsKIFETZF,etal.Enhanced Purcellfactorforanoantennas supportinginterfering resonances[J]. Physical Review Research,2022,4(2).   
[78]HUANGC,ZHANG C, XIAO S M,et al. Ultrafast controlof vortex microlasers[J]. Science,2020,367(6481):1018.   
[79]WANGB,LIU W, ZHAO M,etal.Generatingoptical vortex beams by momentum-space polarization vorticescentredat bound states in the continuum[J]. Nature Photonics,2020,14(10): 623-628.   
[80]GORKUNOVM V,ANTONOVA A, KIVSHARY S. Metasurfaces with Maximum Chirality Empowered by Bound State in the Continuum[J]. Physical Review Letters,2020,125(9): 093903.   
[81]HSU C W,ZHEN B,STONE AD,et al. Bound states in the continuum[J]. Nature Reviews Materials,2016,1(9).   
[82]FEDOTOV VA,ROSE M,PROSVIRNI SL,et al. Sharp trapped-mode resonances in planar metamaterials with a broken structural symmetry[J]. Physical Review Letters,2007, 99(14): 147401.   
[83]MANJAPPA M, SOLANKI A, KUMAR A,et al.Solution-Processed Lead Iodide for Ultrafast Al-Optical Switchingof Terahertz Photonic Devices[J].Advanced Materials,2019,31(32): e1901455.   
[84]EVLYUKHINAB,BOZHEVOLNYIS I,PORS A,et al. Detuned electrical dipoles for plasmonic sensing[J]. NanoLettes, 2010,10(11): 4571-4577.   
[85]ZHANG J,MACDONALD K F, ZHELUDEV NI. Near-infrared trapped mode magnetic resonance in an al-dielectric metamaterial[J]. Optics Express,2013,21(22): 26721.   
[86]TIANJ,LIQ,BELOVPA,et al. High-QAll-ielectric Metasurface: Super and Suppessd Optical Absorption[J]. ACS Photonics,2020,7(6): 1436-1443.   
[87]LIJ,LIJ,ZHENG C,etal.Spectral amplitude modulationand dynamicnear-fielddisplayingof al-siliconterahertz metasurfaces supporting bound states in the continuum[J]. Applied Physics Leters, 2O21,119(24).   
[88]VABISHCHEVICH PP,LIU S,SINCLAIR M B,et al. Enhanced Second-Harmonic Generation Using Broken Symmetry III-V SemiconductorFano Metasurfaces[J]. ACS Photonics,2018,5(5): 1685-1690.   
[89]FANGC,YANGQ,YUANQetal. High-Qresonancesgovernedby the quasi-boundstates in thecontinumina-dielectric metasurfaces[J]. Opto-Electronic Advances,2021,4(6): 200030.   
[90]MUHAMMADN, CHENY,QIUCW,etal.Optical Bound States in Continuumin MoS2-Based MetasurfaceforDirectional Light Emission[J]. Nano Letters,2021,21(2): 967-972.   
[91]TUZ VR, KHARDIKOV V V, KUPRIANOVA S,et al.High-quality trapped modes in all-dielectric metamaterials[J]. Optics Express,2018,26(3): 2905-2916.   
[92]HAN S,PITCHAPPA P,WANG W,et al. Extended Bound States in the Continum with Symmetry-Broken Terahertz Dielectric Metasurfaces[J]. Advanced Optical Materials,2021,9(7).   
[93]KIM KH,KIMJR.High-QChiropticalResonances byQuasi-Bound States inthe ContinuminDielectric Metasurfaces with Simultaneously Broken In-Plane Inversion and Mirror Symmetries[J].Advanced Optical Materials,2021,9(22).   
[94]KOSHELEVK,LEPESHOVS,LIUM,etal.Asymmetric Metasurfaces with High-QResonances GovernedbyBound States in the Continuum[J]. Physical Review Letters,2018,121(19): 193903.   
[95]SUH W,YANIK MF, SOLGAARDO,etal.Displacement-senstive photonic crystal structures basedonguided resonance in photonic crystal slabs[J]. Applied Physics Letters,2003,82(13): 199-2001.   
[96]ZHAO X,CHEN C,KAJ K,et al. Terahertz investigationofbound states inthecontiuumof metallc metasurfaces[J]. Optica,2020,7(11).   
[97]FRIEDRICHH,WINTGEN D.Interfering resonances and bound states in the continuum[J].Phys Rev A Gen Phys,1985, 32(6): 3231-3242.   
[98]HSUCW,ZHENB,LEEJ,etal.Observationof traped light within theradiationcontinuum[J].Nature,2013,499(7457): 188-191.   
[99]LIANG Y,PENGCSAKAI K,etal.Thre-dimensionalcoupled-wavemodel forsquare-latice photoniccrystallasers with transverse electric polarization: A general approach[J]. Physical Review B,2011, 84(19).   
[100]YANG Y,PENG C,LIANG Y,et al.Analytical perspectivefor bund states inthcontinuum inphotoniccrystal slabs[J]. Physical Review Letters,2014,113(3): 037401.   
[101]FAN S H,SUH W,JOANNOPOULOS JD.Temporalcoupled-mode theory for theFanoresonance inopticalresonators[J]. J Opt Soc Am A,2003,20(3): 569-572.   
[102]WONJOO S,ZHENG W,SHANHUIF.Temporalcoupled-mode theoryandthe presence of non-orthogonal modes inlosles multimode cavities[J]. IEEE Journal of Quantum Electronics,2004,40(10): 1511-1518.   
[103]RUAN Z,FAN S.Temporal coupled-mode theory forlight scatering byan arbitrarilyshaped object supporting a single resonance[J]. Physical Review A,2012,85(4).   
[104]KIKKAWAR,NSHDAM,KADOYAY.Polarzation-basedbranchselectionofbound states inthecontinumindielectric waveguide modes anti-crossed by a metal grating[J]. New Journal of Physics,2O19,21(11).   
[105] HSU CW,ZHENB,CHUA S-L,etal.Bloch surfaceeigenstates within theradiationcontinuum[J].Light:Science& Applications,2013,2(7): e84-e.   
[106] SADRIEVAZ,FRIZYUK K,PETROVM,etal.Multipolaroriginof boundstates inthecontinuum[J].Physical ReviewB, 2019,100(11).   
[107] WUPC,LIAO C Y, SAVINOV V, et al. Optical Anapole Metamaterial[J]. ACS Nano,2018,12(2): 1920-1927.   
[108] POSHAKINSKIY A V,PODDUBNY AN. Optomechanical Kerker Effect[J]. Physical Review X,2019,9(1).   
[109] SHAMKHI H K,BARYSHNIKOVA K V,SAYANSKIYA,et al.Transverse Scatering and Generalized Kerker Efects in All-Dielectric Mie-Resonant Metaoptics[J]. Physical Review Letters,2019,122(19): 193905.   
[110] SAVINOV V,FEDOTOVVA,ZHELUDEVNI.Toroidaldipolar excitationand macroscopic electromagneticpropertiesof metamaterials[J]. Physical Review B,2014,89(20).   
[11] KAELBERERT,FEDOTVVA,PAPASIMAKIS N,et al.ToroidalDipolar Response ina Metamaterial[J].Science,2010, 330(6010): 1510-1512.   
[112]FERNANDEZ-CORBATONI,NANZ S,ROCKSTUHLC.Onthe dynamic toroidal multipolesfrom localizedelectric current distributions[J]. Scientific Reports,2017,7(1): 7527.   
[113]MUNJ,SOS,JANGJ,etal.DescribingMeta-Atoms UsingtheExact Higher-OrderPolarizabilityTensors[J].ACSPhotonics. 2020, 7(5): 1153-62.   
[14]LIU W,WANGB,ZHANGY,etal.CircularlyPolarized States Spawning fromBound States in theContinuum[J].Physical Review Letters,2019,123(11): 116104.   
[15]JINJ,IX,NLetalTopologicallyabledultraghQguedresoancesobsttutof-lanscateringJ].ature, 2019, 574(7779): 501-504.   
[116] CHENZ,YINX,JJ,etal.Observationof miniaturizedboundstatesitheontium ithultra-highqualityfactors[J]. Science Bulletin,2022,67(4): 359-366.   
[117] HAN S,CONG L,SRIVASTAVAYK,et al.Al-Dielectric Active Terahertz Photonics Driven by Bound States inthe Continuum[J].Advanced Materials,2019,31(37): e1901921.   
[118]YUEZ,LIJ,ZHENGC,etalResoance-trappedboundstatesinthecontinuumviaal-siliconterahertzmetasurace[J] Optics Communications,2022,516.   
[119] FAN K, SHADRIVOVI V,PADILLA WJ. Dynamic bound states in the continuum[J]. Optica,2019, 6(2).   
[120]LIJ,LIJ,ZHENG C,etal.Free switch between bound states inthe continuum (BIC)and quasi-BIC supported by graphene-metal terahertz metasurfaces[J]. Carbon,2021,182: 506-515.   
[121] CAMBIAsSO J,KoNIG M,CORTeS E，etal. Surface-Enhanced Spectroscopies of a Molecular Monolayer inan All-Dielectric Nanoantenna[J].ACS Photonics,2018,5(4): 1546-1557.   
[122]ROMANO S,ZITOG,MANAGo S,etal.Surface-EnhancedRamanandFluorescence SpectroscopywithanAl-ielectric Metasurface[J]. The Journal of Physical Chemistry C,2018,122(34): 19738-19745.   
[123]NDAOA,HSUL,CAI W,et al.Differentiating andquantifying exosomesecretionfroma singlecell usingquasi-bound states in the continuum[J]. Nanophotonics,2020, 9(5): 1081-1086.   
[124]YESILKOYF,ARVELOER,JAHANIY,etal.Ultrasensitivehyperspectral imagingandbiodetectioenabledbdielectic metasurfaces[J].Nature Photonics,2019,13(6):390-396.   
[125] WANGJ,KuHNEJ,KARAMANOS T,etal.Al-Dielectric Crescent Metasurface SensorDrivenbyBound Statesinthe Continuum[J].Advanced Functional Materials,2021,31(46).   
[126]LIUZ,XUY,LIY,etal.HighQQuasibound States intheContinuumforNonlinearMetasurfaces[J].PhysicalReview Letters,2019,123(25): 253901.   
[127]HA ST,FUYH,EMANINK,etal.Directional lasinginresonantsemiconductornanoantennaarrys[J].Nature Nanotechnology,2018,13(11): 1042-1047.   
[128]OVERVIGA,YUN,ALUA.ChiralQuasi-BoundStates intheContinuum[J].hysical ReviewLetters,16(7):3001.   
[129]SHIT,DENG ZL,GENGG,et al.Planarchiral metasurfaces with maximal and tunablechiropticalresponsedriven by bound states in the continuum[J]. Nature Communications,2022,13(1): 4111.   
[130]LIJ,YUZ,IJ,etal.Ultra-narrowband teraertzcirculardichroismdrivenbyplanarmetasurfacesupportingchiralquasi bound states in continuum[J].arXiv220602486,2022.