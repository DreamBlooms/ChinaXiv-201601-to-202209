# 基于磁流体力学模拟的太阳高能粒子物理模式研究进展

魏稳稳1,，沈芳1，左平兵1

(1.空间天气学国家重点实验室中国科学院空间科学与应用研究中心，北京 100190；2.中国科学院大学，北京100049)

摘要：太阳高能粒子(SEP)事件是一类重要的空间天气灾害性事件，其数值预报研究在空间天气预报研究中占有很重要的地位。SEP事件主要包括3种类型：与太阳耀斑爆发相关联的脉冲型事件，与日冕物质抛射驱动的激波相关联的缓变型事件，以及同时具有缓变型和脉冲型事件特征的混合型事件。其中，缓变型SEP事件持续时间较长并且高能粒子强度较大，对这类事件的模拟是当前研究的难点。目前针对缓变型 SEP事件的模拟工作业已发展了多个理论和数值模型。每个模型都对 SEP 加速和传播的复杂过程作了基本的假设，这些模型的模拟结果能够部分重现观测到的 SEP事件特征。而若要提高预报SEP事件的能力，则需要将描述三维日冕物质抛射驱动的激波模型与描述高能粒子在行星际空间中的加速和传输的模型耦合起来，建立基于接近真实的SEP加速和传播的三维太阳风背景模拟及以激波参数为输入的SEP模型。主要回顾了缓变型SEP 事件中粒子的加速和传输方面的研究进展，以及可用于获取CME 激波传播参数的磁流体力学太阳风模型研究现状；综述了缓变型 SEP 事件的激波-粒子模型 (shock-and-particle model);最后对未来工作进行了讨论和展望。

关键词：太阳高能粒子；激波；MHD太阳风模式；行星际输运中图分类号：P353 文献标识码：A

# 1引言

太阳高能粒子(简称 SEP)事件是能量粒子的通量突然增强的事件，一般可以由人造卫星和地面探测设备探测到。美国国家海洋和大气管理局(NOAA）将 SEP事件定义为能量大于l0MeV的粒子在连续 $1 5 ~ \mathrm { m i n }$ 以上的时间内数目超过10pfu $( \mathrm { c m } ^ { - 2 } \cdot \mathrm { s } ^ { - 1 } \cdot \mathrm { s r } ^ { - 1 } )$ 的爆发性事件[]。SEP 事件能够产生高通量的高能粒子分布，这不仅会影响航天器的正常运行，而且会对航天员的生命安全造成严重危害。在极端情况下，能量较高的 SEP甚至可到达地面，产生地面水平事件(简称GLE)，GLE 是一种极端 SEP 事件，和通常的 SEP 事件(粒子的能量范围通常在 $1 0 \sim 1 0 0 ~ \mathrm { M e V }$ 之间）相比，GLE 事件中粒子的能量甚至能达到 $1 \mathrm { G e V } ^ { \left[ { 3 } \right] }$ 。

SEP 事件可分为3类：缓变型 SEP 事件(Gradual SEP events)，脉冲型 SEP 事件(Impulsive SEP events)以及混合型 SEP 事件 (Mixed SEP events)。缓变型 SEP 事件持续时间较长，通常持续数天，能量粒子强度较大，质子含量相对丰富；绝大多数的缓变型SEP事件都伴随着日冕物质抛射(简称CME）所驱动的激波而发生。脉冲型 SEP事件持续时间比较短，通常只有数小时，强度较弱，并且电子含量相对丰富，一般认为与耀斑过程相关。另外，Kallenrode指出，有些 SEP事件中粒子的成分由脉冲型事件的特征演化为缓变型事件的特征；即一次 SEP 事件中，耀斑和CME 驱动的激波对高能粒子的加速过程可能都有贡献，导致所谓的混合型事件。

对 SEP 事件的实地观测内容包括粒子的组分、电荷态、能谱、强度分布和各向异性分布等57]。表1给出缓变型和脉冲型 SEP 事件各自的特点，从中可以看出，在脉冲型 SEP 事件中 $^ 3 \mathrm { H e } / ^ { 4 } \mathrm { H e }$ 丰度的比值约为1，而太阳风中的 $^ { 3 } \mathrm { H e } / { ^ { 4 } \mathrm { H e } }$ 丰度的比值虽然波动很大但是很少超过0.01，因此脉冲型 SEP 事件有时也称富氨3电子事件。另外，脉冲型 SEP事件的 Fe/O比例比正常日冕大气中 $\mathrm { F e / O }$ 的比例大10倍，这些特征显示耀斑起源粒子在脉冲型事件中占主导地位。缓变型 SEP事件中 $^ { 3 } \mathrm { H e } / ^ { 4 } \mathrm { H e }$ 以及Fe/O的比例都与日冕大气中的成分比例接近，关于两类 SEP 事件的特征和区别，Reames于1999 年给出了详细的论述。

表1 缓变型和脉冲型 SEP 事件的特点[8]  

<html><body><table><tr><td></td><td>缓变型</td><td>脉冲型</td></tr><tr><td>粒子</td><td>质子丰富</td><td>电子丰富</td></tr><tr><td>3He/4He</td><td><0.01</td><td>约1</td></tr><tr><td>[Fe/O]/[Fe/O]cornal</td><td>约1</td><td>约10</td></tr><tr><td>持续时间</td><td>天</td><td>小时</td></tr><tr><td>经度分布</td><td>约180°</td><td><30°</td></tr><tr><td>相关射电暴类型</td><td>II, IV</td><td>III, V</td></tr><tr><td>事件发生率 (太阳活动极大年)</td><td>约10次/年</td><td>约1000次/年</td></tr></table></body></html>

SEP事件会对卫星和进行航天作业的宇航员构成严重的威胁，如能准确预报SEP事件，人们便可以采取必要的防护措施，保障卫星和星载设备的安全；同时也可以为航天器的故障分析和航天员的安全防护提供科学依据；还可以为采取应变措施赢得宝贵时间，尽可能地降低经济损失。然而SEP事件产生和发展的物理机制非常复杂，目前还没有被完全解释清楚，预报 SEP事件的能力也不尽如人意。因此，正确理解和恰当的动力学描述这些机制，对推进和提高空间天气预报能力是非常重要的。相对于脉冲型 SEP事件，缓变型SEP事件由于其高强度和长持续时间等特征造成的危害可能更大，由CME驱动的激波加速引起的缓变型SEP事件可以造成近地空间持续数天的高达数十 $\mathrm { M e V / n }$ 甚至 $\mathrm { G e V } / \mathrm { n }$ 能量的灾害性粒子辐射扰动。所以对缓变型 SEP 事件预报具有重要的空间天气学意义，同时 SEP 事件也是每一个 11 a 太阳活动周期内空间高能粒子通量的主要来源[1]。

对于脉冲型 SEP事件的模拟，许多模型假设粒子的源项是固定的，通常假定源项分布在太阳表面或者接近于太阳表面，然后求解粒子在行星际空间的传输过程，得到观测者位置的通量剖面、各向异性分布等。不同于脉冲型 SEP 事件，缓变型 SEP 事件的粒子源是移动的行星际激波，导致缓变型事件的建模难度更大。缓变型SEP事件通常与快速的CME 相关，这些快速的CME 加速行星际激波，使其速度非常高，ACE（Advanced CompositionExplorer）卫星在2003年10月29日和30日探测到的实地太阳风速峰值高达 $1 8 5 0 \ \mathrm { k m \cdot s ^ { - 1 } }$ 和 $1 7 0 0 \ \mathrm { k m } \cdot \mathbf { s } ^ { - 1 }$ ，GOES（Geostationary Operational Environmental Satellite）卫星记录到行星际激波加速产生的一系列 SEP 事件，其中还有3次达到了GLE 水平[1]。快速的 CME驱动的行星际激波对加速粒子起着主导作用，所以提前几天或几小时预测大型缓变型 SEP事件的技术难点主要包括以下几点[12：(1)CME 在何时、何地发生；(2)详述CME 的特点，比如它能否驱动激波等；(3)确定CME 驱动的激波加速粒子到高能量的效率，同时被加速的粒子怎样被注入到行星际介质；(4)被加速的粒子和CME 驱动的激波在背景太阳风中是怎样传播的。

因此，缓变型SEP事件的模拟主要包括以下3个方面：

1)行星际激波位形和演化的描述；  
2)粒子加速和传输的模拟；  
3)随着激波向外传播，激波加速机制和能量粒子注入的连续检验。

总体来讲，SEP 事件的模拟流程可用图1表示。对于脉冲型 SEP 事件，只要将太阳高能粒子的注入率输入到粒子模型里即可进行有效模拟；而对于缓变型 SEP 事件的模拟，则需要首先运行磁流体力学（简称 MHD）模型，获取激波面沿磁力线的cobpoint1（Connectingwith theOBserverPOINT：连结太阳和观测者的磁力线通过激波面上的位置）的激波参数(比如速度、磁场)，作为粒子模型的输入参数，然后通过求解传输方程得到SEP的能谱、强度和各向异性分布。从图中可以看出，无论是模拟缓变型还是脉冲型SEP事件，给定比较准确的粒子注入率很关键。模拟脉冲型事件时，一般假设粒子源被固定在太阳附近；而缓变型事件粒子源是随太阳风一起运动的行星际激波，高能粒子在激波附近被加速时，可以逃离激波进入太阳风并沿着行星际磁场传播到地球附近，而且传输的空间和时间尺度比较大，意味着传输条件会有显著改变，因此粒子注入率与CME 所驱动的激波传播参数的准确获取有着密不可分的关系。若要建立更加真实精确的SEP 物理模式，则需要将描述三维日冕物质抛射驱动的激波MHD 模型与描述高能粒子在行星际空间中的加速和传输的粒子模型耦合起来。

目前缓变型 SEP 事件模拟的相关模型中，一般需要对激波的传播和SEP 加速与输运的复杂过程作出一些基本的简化和假设[13-18]：当模拟激波的传播时，假设激波面为平面或球面；把激波对粒子的加速过程当做黑匣子处理，人为给定一个激波加速源项；行星际磁场假设成Parker场等。这些模型能够得到一些与实际观测相吻合的结果，但是并不能全面准确地重现 SEP 事件的观测特征，预报的准确度较低。因此，融合接近真实的三维MHD 太阳风背景，考虑CME 驱动的激波的三维结构，以及包含更真实丰富的物理内容的激波加速模式，是缓变型SEP事件物理模式研究的方向。

![](images/df3ae6cd63ae5744352879895c3ded6f08c5efb0506173e56f965a5e05a2f0eb.jpg)  
图1 激波-粒子模型的基本模块[12]

本文第2章介绍 SEP事件中粒子的加速和传输方面的研究进展，第3章回顾可用于获取CME 激波传播参数的MHD 太阳风模型，第4章综述缓变型 SEP事件的激波-粒子模型，第5章对未来工作进行讨论和展望。

# 2 SEP事件粒子的加速和传输研究进展

# 2.1 缓变型SEP事件中粒子的加速模型

缓变型SEP事件的模拟需要考虑激波加速的影响，相关模型可以粗略地分为两类：(1)不考虑具体的激波加速机制[13-18]，即忽略激波对粒子的具体加速过程，在传输方程中加入一个激波加速源项来描述粒子被运动激波加速后在激波面附近的分布函数；然后求解传输方程，得到观测者处在不同位置时粒子的通量。通过将模拟结果与观测结果作对比，进而研究高能粒子注入效率函数随粒子能量、时间和空间的变化，以及粒子在行星际的传播过程。(2）发展激波加速理论，主要包括激波漂移加速[19]、扩散激波加速[20-22]、随机加速[22]等。这几种激波加速机制的相对贡献依赖于激波的性质，激波速度、压缩比、Alfven马赫数、上游磁场与激波法向的夹角 $\left( \theta _ { B n } \right)$ 以及激波附近存在的MHD 扰动都能改变粒子加速效率的相对贡献大小[16,24]。下面分别对这两类工作进行介绍。

# 2.1.1不考虑具体加速机制的模型

Heras 等人[13.14对缓变型 SEP 事件的空间演化进行了建模研究，在 Heras 的模型中首次采用聚焦传输方程，用其替代Parker 传输方程模拟SEP 在行星际空间的传播过程。这个模型的主要特点如下：(1）在聚焦传输方程中加入一个激波加速源项 $Q$ ，表征粒子被激波加速在cobpoint 位置的粒子注入率。运用此传输方程，可以很好地再现 SEP事件中大而持久的各向异性分布[25]。(2)对 cobpoint 概念的详细阐述与量化实现。cobpoint 随着激波前沿改变且沿着连结飞船与太阳的磁力线运动，通过追踪cobpoint 的运动轨迹、激波法向、激波上下游速度的变化规律，可以为不同位置的飞船提供激波加速粒子的注入强度-时间变化曲线，这在SEP事件研究中具有重要作用。模型假设激波上游的行星际磁场采用Parker螺旋场模型，粒子的注入发生在cobpoint，采用MHD模型描述激波从 $0 . 0 8 \sim 1$ AU(1AU是太阳到地球的平均距离，在2012年8月于中国北京举行的国际天文学大会上，该值被定义为$1 4 9 5 9 7 8 7 0 7 0 0 \ \mathrm { m } )$ 的传播过程，从而得到激波参数在cobpoint 处的演化规律。此外，沈芳等人[2通过模拟cobpoint 沿着连结 ACE 与太阳磁力线的运动来追踪 cobpoint 的演化，并且给出了三维运动图像（见图2)。由于粒子的注入发生在cobpoint 位置，未来可以提高获取cobpoint 位置的算法，以期在粒子模型中能够获取更加准确的粒子注入率，使模拟结果更加接近真实。

在 Heras 等人假设的基础上，Kallenrode 等人[15，18把激波模拟为半球形的，使其以恒定速度沿径向从太阳表面向外传播；而且激波注入效率函数随径向距离和方位角变化，用以体现激波加速效率的时空变化。他们仅仅改变聚焦尺度来修正粒子在激波下游的传播，但是他们没有考虑激波传播经过被扰动后的行星际磁场所带来的影响，这将会导致不同的结果；他们还考虑到粒子横越激波的传播，却没有考虑当粒子被反射后或者传播过程中能量的改变。

（204号 $\mathrm { N g }$ 等人[17.27给出一个高能离子和 Alfven 波相互耦合演化的模型，他们结合了磁聚焦效应、投掷角扩散效应、波的放大效应和一个运动的离子源。 $\mathrm { N g }$ 等人采用有限差分方法，求解耦合的聚焦传输方程和描述高能离子激发的等离子体波动的强度演化方程。该模型假设激波以恒定速度沿径向传播，参数化粒子注入效率随时间、粒子刚度和径向距离变化。该模型最大的优势是考虑了粒子在传输过程中激发的等离子体波动对粒子散射的影响。但是行星际磁场沿径向这一假设过于简单，不能解释 SEP事件的经度差异；并且激波以恒定速度传播，是缺乏物理依据的追踪 cobpoint 的方式[28]。

Lario 等人[16,29进一步优化了Heras 的模型，在传输方程中加入太阳风对流和绝热减速效应。通过模拟不同的 SEP 事件，给出了一个在cobpoint 位置激波加速质子的注入率 $Q$ 与径向速度比值VR的经验关系式： $\lg Q \propto V R$ （ $V R$ 来自MHD 模型的输出， $Q$ 作为粒子传输模型的参数输入)。模型成功地再现了一些SEP事件中低能段（小于 $2 0 \ \mathrm { M e V } )$ ）质子通量和各向异性剖面[13,16]。Lario 等人[]建立的 MHD 变量与粒子注入率的 $Q ( V R )$ 关系，虽然只是一个半经验关系，却为我们提供了激波-粒子混合模拟的范例，让我们思考怎样把粒子注入率与CME 驱动的激波的传播参数联系起来。但是，Lario 等人提出的 $Q ( V R )$ 关系式仅仅将注入率与cobpoint 激波的速度联系在一起；未来可以寻找更加真实的关系，将MHD 模型得到的参量与粒子注入率联系起来。

在以上研究的基础上，Aran 等人[12,30]建立了预报 SEP 的 SOLPENCO(SOLar ParticleENgineeringCOde）模型。图3给出了SOLPENCO 在欧洲空间天气门户网站的初始界面，这个操作工具包括两个界面：需要输入不同变量值（日心距离、初始脉冲速度、观测者角度位黑色为行星际磁场线，实心黄色圆圈为太阳的位置，实心紫色圆圈为ACE，实心红色圆圈为cobpoint，色标代表相对密度$( \rho - \rho _ { 0 } ) / \rho _ { 0 }$ 的等值面。(a） $t = 3 0 ~ \mathrm { m i n }$ ；(b) $t = 1 0 \mathrm { ~ h ~ }$ ；(c) $t = 2 0 \mathrm { ~ h ~ }$ ：(b) $t = 3 0 \mathrm { ~ h ~ }$ ；(b）t=40h。

![](images/839e551d1be5a5bead0d60e8f4b537a6929fc693a8504914a2b333424c32e754.jpg)  
图2 不同时间段的三维运动图像[26

置、平均自由程、是否存在高度湍动、粒子能量)的初始界面；根据输入的参量，产生某一给定事件的通量图像或者一组数值矩阵。此模型的空间天气应用详见参考文献[12]。

SOLPENCO |European Space Weather Portal-Microsoft Internet Explorer -X   
E FavsramentAyuds 1 2 Bucad Favoto /eu/ D   
CoogeC. E·Mrcaooreoeadsectt otogsTrauE Conuroon EuropeanSpaceWeatherPortal TheEuropeangatewaytoSpaceWeatherresources   
angels Home>Content angelsaran logout   
aran SOLPENCO Services view edit outline translation Model Heliocentric distance: 04AU Search .access Initial pulse velocity： 750km/s Search access Heliolongitudeofparentsolaractivity: E 中 Data Mean freepath： 02AU catalog Existence of high turbulence: yes Events SWENET Energy: 0125MeV ember2006 Outreach Run Mon Tue Wed Thu Fri Sat Sun Acronyms 1 2 3 4 5 Bibliography Drawings UV 8IMCLCRA 6 7 8 9 1011 12 Glossary B 13 14 15 16 1718 19 Industry Introduction Departamentd'AstronomiaiMeteorologia 20 21 22 23 2425 26 Public AnEngineering Model forSolar Energetic 27 28 29 30 Your Particles in Interplanetary Space language (SOLPENCO) Contacts Languages Topical · English Thecode provides proton fluxand cumulative Web fluenceprofilesat0.125，0.2500.5,1,2,4,8,16, Zmybptl ink   
国 3 nterret

上述模型都没有涉及粒子被运动激波加速的具体物理机制，也不考虑激波面的MHD 条件，如激波位形、激波强度和速度演化如何影响激波加速效率等问题。要对粒子加速和注入的复杂现象和机制进行描述，只做运动激波的假设显然不充分。Lario等人[1提出将激波加速粒子的注入率的演化与激波动力学性质联系起来的 $Q ( V R )$ 关系，这个关系能够量化注入率等参数，但是无法解释激波加速粒子的物理机制。

# 2.1.2考虑具体加速机制的模型

也有一些学者尝试研究较为真实的CME 驱动激波附近粒子注入加速过程。关于激波加速的模拟工作主要集中在扩散激波加速，扩散激波加速是一种一阶费米加速过程。当粒子多次来回穿越激波面后，会被加速到很高的能量，这种加速过程如图4所示。

下面简单介绍扩散激波加速的分析计算，主要内容见参考文献[32]。假设散射在激波上下游都起作用，引起粒子沿着磁力线以及垂直磁力线的方向扩散；等离子体分布范围从$x = - \infty$ 到 $x = + \infty$ ，无限薄的平面激波处于 $x = 0$ 处，粒子的速度远大于背景流体速度；那么描述粒子输运的稳态玻尔兹曼方程可以写成扩散对流方程的形式[19]：

$$
\frac { \partial } { \partial x } \left[ u f ( x , p ) - \kappa \frac { \partial f ( x , p ) } { \partial x } \right] = \frac { 1 } { 3 } \left( \frac { \partial u } { \partial x } \right) \frac { \partial } { \partial p } [ p f ( x , p ) ] ,
$$

![](images/57ba00655a2839946a5de19e18d08e6e9fa585b8b6e0f85e7653751de77d0dd7.jpg)  
图4扩散激波加速过程示意图[32]垂直阴影线为激波面，圆点表示散射元，带有箭头的实线表示加速粒子的路径。

其中， $f$ 是粒子的分布函数， $\kappa$ 是垂直于激波面的扩散系数， $\boldsymbol { u }$ 是流体速度， $\pmb { p }$ 是粒子的动量。由式（1）可以推出上游和下游无穷远边界处的分布函数 $f _ { 1 }$ 和 $f _ { 2 }$ 的关系表达式，为：

$$
f _ { 2 } ( p ) = b p ^ { - b } \int _ { 0 } ^ { p } \mathrm { d } p ^ { \prime } p ^ { \prime ( b - 1 ) } f _ { 1 } ( p ^ { \prime } ) ~ , ~ b = \frac { 3 u _ { 2 } } { u _ { 1 } - u _ { 2 } } ~ ,
$$

其中， $u _ { 1 }$ 和 $u _ { 2 }$ 分别代表上游和下游流体速度， $f _ { 2 }$ 是激波下游无穷远处的分布函数， $f _ { 1 }$ 是激波上游无穷远处的分布函数。这里不给出此公式的推导过程，详细的推导见参考文献[19]。

假设注入粒子能谱是单一能量的，即 $f _ { 1 } ( p ) \propto \delta ( p - p _ { 0 } )$ ，那么从式(2）可以得出，当$p > p _ { 0 }$ 时， $f _ { 2 } ( p ) \propto p ^ { - b }$ 是幂律谱。幂律指数 $b$ 由压缩比 $\gamma = u _ { 1 } / u _ { 2 }$ 决定，根据马赫数$M = u _ { 1 } / v _ { A 1 }$ C $\overset { \cdot } { \boldsymbol { v } _ { A 1 } }$ 为激波上游Alfven 速度)，可以得到：

$$
b = \frac { 3 r } { r - 1 } = \frac { 3 ( \Gamma + 1 ) M ^ { 2 } } { 2 ( M ^ { 2 } - 1 ) } , r = \frac { ( \Gamma + 1 ) M ^ { 2 } } { 2 + ( \Gamma - 1 ) M ^ { 2 } }
$$

其中， $\Gamma = 5 / 3$ 为气体的绝热指数。当 $M ^ { 2 } \to \infty$ ，强激波条件下压缩比 $r \to 4$ ，得到幂律指数$b = 4$ ，而观测到的宇宙线能谱为 $b = 4 . 7$ ，因此这种加速机制常被用于解释宇宙线的起源。

扩散激波加速理论基于Parker 扩散传输方程[3.341

$$
{ \frac { \partial f } { \partial t } } = \nabla \cdot ( { \boldsymbol { K } } \cdot \nabla { \boldsymbol { f } } ) - { \boldsymbol { U } } \cdot \nabla { \boldsymbol { f } } - { \boldsymbol { V } } _ { \mathrm { d } } \cdot \nabla { \boldsymbol { f } } + { \frac { 1 } { 3 } } p \nabla \cdot { \boldsymbol { U } } { \frac { \partial f } { \partial p } } + { \frac { 1 } { p ^ { 2 } } } { \frac { \partial } { \partial p } } \left( { \boldsymbol { D } } _ { \mathrm { p p } } p ^ { 2 } { \frac { \partial f } { \partial p } } \right)
$$

其中， $f$ 是粒子分布函数， $\pmb { U }$ 为背景流场的速度， $\pmb { K }$ 和 $D _ { \mathbf { p } \mathbf { p } }$ 分别为空间扩散系数张量和动量扩散系数， $V _ { \mathrm { d } }$ 是漂移速度。Parker传输方程能融合运动电场导致的漂移加速，粒子穿越激波在上下游介质连续散射的一阶费米加速，由等离子体湍动引起的随机激波加速等机制，可以成功解释CME驱动的激波加速产生的单幂律谱能谱特征以及其他观测现象，但前提必须假设粒子投掷角分布各向同性。

对于扩散激波加速的模拟工作主要有以下几点[35：(1)对于CME 驱动的激波，由于其加速粒子的时间和能量有限，因此粒子要获得加速，需要在激波附近停留足够长的时间[36,37]。(2）逃逸的高能粒子在激波上游可以激发并放大 Alfven 波，这些被放大的 Alfven波能够有效地把粒子保持在激波附近③。Lee[2提出了一个与磁流体力学波相关的扩散激波加速粒子的自洽理论，研究表明AIfven波的强度和加速粒子分布函数的各向异性程度相关，由此可以得出Alfven 波的放大过程和粒子的加速过程存在耦合。此外， $\mathrm { N g }$ 等人在模拟缓变型 SEP事件时建立了激波加速高能粒子与行星际Alfven波相耦合的理想模型，模拟结果表明粒子激发的 Alfven 波对它们的传输过程具有重要作用。(3)较为真实的CME 驱动的激波并不是简单的平面或球面激波，而是具有有限经度宽的复杂三维结构，其演化也受三维太阳风结构的影响。Sokolov 等人[3通过耦合一个三维的MHD 模型和粒子加速的场线平流模型(field line advection model for particle acceleration)，得到一个由较为真实的 CME 驱动的激波加速粒子的模型。该模型能得到一个较为真实的CME 和激波结构，并模拟粒子在距离太阳 $4 \sim 3 0 ~ R _ { \mathrm { s } }$ 范围内的加速过程，结果发现扩散加速能够将粒子加速到几百MeV。其模拟结果与1998年5月2日发生的SEP事件的一些观测结果吻合较好。

Zank 等人[3提出了一个“洋葱壳层”模型(Onion Shell Model)，发展了基于扩散激波加速的动力学时变模式。“洋葱壳层”模型是粒子加速和波激发过程的耦合，可近似为一个激波掠过的同心球层，而忽略星际介质可能带来的不对称性。该模型假设行星际磁场为Parker场，爆炸激波在球对称太阳风中传播，采用一维的 ZEUS MHD 模式模拟激波产生后在内日球层中的传播过程，激波参量如强度、马赫数等和太阳风的演化由流体力学数值模拟确定。在准平行激波条件下，粒子的加速和Alfven波的非线性增长耦合在一起，粒子在传播、演化的行星际激波处得以加速。模型还包括激波加速后的粒子逃逸到上游激发Alfven波的过程。模拟结果显示，行星际激波加速粒子能达到的最大能量由逐渐降低的激波速度、逐渐减弱的行星际磁场和激波传播时间共同决定。

Rice 等人[4进一步优化了Zank等人的模型，利用波增长方程的稳态解自洽地计算并得到加速粒子激发的上游波强度，这样空间扩散系数也可以通过自洽地计算获得，空间扩散系数与动量相关并且决定粒子的加速和随后的演化。该模型适用于任意强度的激波，明显地改进了Zank等人通常只适用于强激波的模型。

李刚等人[37.41]对 Zank 和 Rice 等人建立的模型做了较大改进，采用蒙特卡洛方法模拟粒子经激波加速后，在距激波较远处逃逸后在Paker螺旋行星际磁场的传播过程，该模型可以求得粒子往返穿越1AU的次数，继而可以较为准确地计算出事件中粒子的强度分布和能谱。此外，李刚等人还运用该方法研究了行星际湍流对粒子输运的影响，模型给出了不同平均自由程、不同能量粒子的强度曲线随时间的变化，并且理论模型可以很好地解释ACE 和WIND飞船的观测结果。在此模型的基础上，李刚等人\*计算了同时有耀斑和CME 驱动激波加速时的时间强度剖面，结果显示：时间强度剖面经历一段快速增长，即呈现出只有耀斑加速时的特征，然后趋于平稳状态，即呈现出只有激波加速时的特征。这与Cane 等人l4提出的一些大SEP事件中某些高能粒子的时间强度曲线会有两个峰值的观测结果对应。同时，模型还预测了处于不同经度的观测者所观测到的时间强度曲线(见图5)。

后来该模型发展成为一套较成熟的日球层粒子传输和加速模型，称为PATH(ParticleAcceleration and Transport in the Heliosphere）模型[445]。PATH模型采用的是基于 Parker传输理论(基于Parker传输方程)的扩散激波加速机制，该模型成功地模拟了几例大的缓变型 SEP事件的粒子相对强度的时间剖面和能谱，计算结果和观测数据吻合较好。PATH模型的成功之处是融合了准平行激波的一阶费米加速机制、激波传播过程中强度速度演化、太阳风湍流对激波加速效率的影响，包含更真实丰富的物理内容。

![](images/8ca2477c6d421b5f5ae451833b507929fe522810cff0f61047be31ef96519fdc.jpg)  
[42]图5模型预测的处于不同经度处的观测者观测到的时间强度曲线不同颜色的线型代表不同能量的粒子的时间强度。(b）表示观测者只与耀斑相连：(c）表示观测者只与CME 驱动的激波相连；(d）表示观测者与耀斑和CME 驱动的激波都相连。

李刚等人[4在PATH模型中加入任意的磁场上游与激波法向的夹角 $\theta _ { b n }$ ，用以研究斜激波上的粒子加速，并且考虑 $\theta _ { b n }$ 对注入能量和注入效率，平行扩散系数 $k _ { | | }$ 和垂直扩散系数$k _ { \bot }$ ，以及总的扩散系数 $k$ 的影响。李刚等人自洽地同时求解粒子和波的输运方程得到平行扩散系数 $k _ { \parallel }$ ，计算垂直扩散系数 $k _ { \perp }$ 时采用非线性引导理论。模拟结果显示，粒子注入效率随$\theta _ { b n }$ 的增加迅速下降，接近于太阳时！ $( r < 0 . 2 { \mathrm { ~ A U } } ) $ ；准平行激波比准垂直激波能加速粒子到更高的能量，原因在于质子流激发的AIfven波在粒子加速中发挥主要作用。准平行激波加速的粒子能得到的最大能量随着日心距离 $\boldsymbol { r }$ 比准垂直激波下降得更迅速，而且准平行激波上游波强度随着距离下降得更快；因此，随着日心距离的增加，准垂直激波能将粒子加速到更高的能量。

# 2.2 各向异性激波加速粒子模型

关于激波加速，早期人为给定激波加速源项的处理方式显然无法精确描述激波加速的高能粒子源分布，而现有的高能粒子在CME 驱动激波的加速模型采用的都是基于Parker 传输理论的扩散激波加速(比如PATH模型)。Parker传输方程可以成功解释某些缓变型或者混合型SEP事件的观测特征尤其是能谱特征。但是Parker传输理论是基于扩散框架下的，以一个基本假设为前提，即粒子投掷角分布是各向同性的；显然，Parker传输理论不能应用于各向异性粒子环境下的激波加速问题。而且最近的一些 SEP事件的观测结果与扩散激波加速理论不完全吻合。如Terasawa等人发现加速效率与Alfven马赫数相关，而Alfven 马赫数取决于上游磁场强度；在扩散激波加速理论下，特别是平行激波时，加速效率只取决于激波压缩比，而与上游参数无关。

为了研究磁聚焦效应、由湍动磁场导致的投掷角扩散传输效应以及绝热冷却效应对 SEP传输机制的影响，秦刚等人4运用复合磁湍流模型，用数值模拟的方法计算了带电粒子在Parker 场的运动轨迹，并将模拟结果与解析公式的计算结果进行比较。相对于各向同性理论，模拟结果与各向异性绝热冷却效应理论更加吻合，并且，模拟结果与磁场聚焦和投掷角散射理论得出的结果基本一致。

近年来，一些研究者49.50开始用聚焦传输方程来描述粒子在激波附近的传输和加速过程，聚焦传输方程的本质是Fokker-Plank方程，用于描述粒子分布函数 $f$ 在相空间的演化，其形式如下：

$$
\begin{array} { r l } & { \displaystyle \frac { \partial f } { \partial t } = \nabla \cdot \boldsymbol { k } _ { \perp } \cdot \nabla f - \big ( v \mu b + { \boldsymbol { V } } _ { \mathrm { s w } } \big ) \cdot \nabla f + \frac { \partial } { \partial \mu } D _ { \mu \mu } \frac { \partial f } { \partial \mu } + } \\ & { \displaystyle \left[ \frac { \big ( 1 - \mu ^ { 2 } \big ) v } { 2 L _ { B } } - \frac { \mu \big ( 1 - \mu ^ { 2 } \big ) } { 2 } ( \nabla \cdot { \boldsymbol { V } } _ { \mathrm { s w } } - 3 b b : \nabla { \boldsymbol { V } } _ { \mathrm { s w } } ) \right] \frac { \partial f } { \partial \mu } + } \\ & { \displaystyle \left[ \frac { 1 - \mu ^ { 2 } } { 2 } ( \nabla \cdot { \boldsymbol { V } } _ { \mathrm { s w } } - b b : \nabla { \boldsymbol { V } } _ { \mathrm { s w } } ) + \mu ^ { 2 } b b : \nabla { \boldsymbol { V } } _ { \mathrm { s w } } \right] p \frac { \partial f } { \partial p } ~ . } \end{array}
$$

其中， $\mu$ 为投掷角的余弦值， $k _ { \perp }$ 是垂直扩散系数， $D _ { \mu \mu }$ 为投掷角扩算系数， $L _ { B } = ( \pmb { b } \cdot \nabla \ln B ) ^ { - 1 }$ 为磁场聚焦尺度， $\pmb { b }$ 是沿着磁场方向的单位矢量， $\mathbf { \nabla } _ { v }$ 是粒子的速度， $V _ { \mathrm { s w } }$ 是太阳风的速度。聚焦传输方程唯一的假设是基于小扰动的准线性近似。相对于Parker传输方程，该方程不仅融合了费米加速、激波漂移加速、横越激波电场引起的加速等，而且保留了投掷角信息，不用假设粒子各向同性，所以基于聚焦传输方程的激波加速模式一般称为各向异性激波加速模式[1]。

左平兵等人[5采用前向随机微分方法的各向异性激波加速模式，在连续单一能量粒子注入条件下研究不同类型激波(平行激波、斜激波及准垂直激波）的加速能谱，比较了各向异性加速和基于Parker传输方程的各向同性加速的异同点。对于能量较高的粒子，能谱接近于单幂律，这与标准的扩散激波加速理论一致；对于斜激波或者准垂直激波，能谱的高能成分表现出双幂律分布。当粒子注入源项相同时，由聚焦传输方程得出的能谱强度不同于标准的扩散激波加速理论得出的能谱强度。图6(a)给出了基于各向异性激波加速模式下平行激波加速高能粒子下游的能谱，实线代表运用前向随机微分方法得出的模拟结果，点划线代表一维Paker 传输方程的解析解。从图6(a)中可以看出，较高能段模拟得到的幂律分布的强度小于标准的扩散激波加速理论的值，这意味着很少的粒子能被加速到较高的能量。此外，左平兵等人[5还用此模式研究了激波加速的高能粒子的空间分布和各向异性，模拟发现激波上游的高能粒子处于强各向异性，但是下游却接近于各向同性，并且激波附近出现强度尖峰结构。这些模拟结果可以很好地解释 Voyager1&2飞船在终止激波附近探测到的终止激波粒子(能量在几keV至 $2 0 ~ \mathrm { M e V }$ 之间的高能粒子）的异常观测特征[52]，包括：(1）在终止激波上游区域，终止激波粒子具有很强的投掷角各向异性，并且随时间粒子各向异性变化较快，而在终止激波下游，终止激波粒子则显示出稳定的投掷角各向同性分布；(2)在终止激波附近出现强各向异性强度尖峰结构；(3)在终止激波上下游都能观测到多幂律谱能谱分布，而不是经常观测到的宇宙线单幂律谱分布。

![](images/a455e997a3c8a21bec23757c79c922360edf0f46a6f68369c86df46f6f674675.jpg)  
图6(a）平行激波下游的能谱分布；(b)粒子动量与投掷角随注入粒子投掷角的变化[(a)实线代表运用前向随机微分方法得出的模拟结果，点划线代表一维Paker传输方程的解析解。

# 2.3 垂直扩散对SEP在行星际空间传播的影响

在行星际空间，存在着由太阳风的波动和湍流引起的随机小尺度不规则磁场，由于这些随机扰动，SEP在行星际空间传播时运动轨道发生散射，导致扩散运动。在前面提到的模拟SEP 传播的模型中，普遍假定粒子只沿着行星际磁力线方向扩散，而不考虑垂直于磁力线的扩散过程。在准线性理论[3中，垂直扩散是由于磁力线的随机行走引起，该理论分别求出平行扩散系数和垂直扩散系数的表达式，结果表明垂直扩散系数相对于平行扩散系数可以忽略不计。但是Dwyer4、张明等人[5通过分析卫星的观测数据，发现在一些 SEP 事件中垂直扩散系数和平行扩散系数的比值可以接近甚至超过1。Matthaeus提出非线性引导中心理论（NLGC）并用其描述粒子在磁场中的垂直扩散，这是首个和数值模拟吻合得较好的理论模型，对后来关于垂直扩散系数的研究具有重要的参考价值。

张明等人模拟了 SEP在三维行星际空间的传播过程，并且对比了不加入垂直扩散和加入垂直扩散后的模拟结果。他们发现，加入垂直扩散后，通量分布更加均匀，衰变相期间SEP 各方向的通量比值更加接近于1，这是因为垂直扩散能很大程度地抹掉行星际空间中SEP 通量分布的不均匀性。2001年9月24日在1AU 附近，Wind飞船观测到在 SEP 事件的初始时刻，粒子还处于各向异性分布时，朝向太阳运动的粒子异常增加的情况。秦刚等人[8从垂直扩散的角度解释了这一异常情况。

汪洋等人[35研究了垂直扩散对被CME 驱动的行星际激波加速的高能粒子的影响，以及高能粒子在三维Parker场中的传播过程；计算了当激波传向不同的经度和纬度方向时，位于1AU 的观测者测量到的粒子通量和各向异性剖面随时间变化的情况。模型假设CME 驱动的行星际激波是一个运动的SEP源，源的强度随时间和空间的变化过程由经验模型给定，不考虑粒子的加速过程。模拟结果显示，当加入垂直扩散后，通量的初始时间、峰值时间、峰值强度与事件的持续时间都会受到显著的影响；并且在考虑垂直扩散效应后，高能粒子能够横越磁力线传播。观测者能够在其磁力线与激波面连结起来之前观测到高能粒子；当观测者所在的磁力线与激波面断开以后，同样还有粒子不断地注入或者离开观测者所在的磁力线。图7给出有垂直扩散和没有垂直扩散的情况下，5MeV粒子的通量和各向异性随时间变化的曲线。对于事件W70，有垂直扩散的情况下，通量衰减得更慢一些；对于N40 事件，观测者的磁力线一直与激波面是断开的，所有的粒子只能通过垂直扩散才能到达观测者。

秦刚等人[用与汪洋等人[3]相似的模型 (模型不同之处在于投掷角扩散系数 $\mathcal { D } _ { \mu \mu }$ 和垂直扩散系数 $k _ { \perp }$ 的公式不一样，汪洋等人采用的是基于量纲分析的较简单的经验公式，而秦刚等人采用的是基于湍流理论的公式）研究了卫星处于不同经纬度和径向距离时，形成蓄水池现象（到了大型SEP事件的衰退期，分开较远的飞船观测到高能粒子的通量几乎一致，通量的差别在 $2 \sim 3$ 倍左右，并且通量随时间线性演化的现象）所需的垂直扩散系数的大小。模拟结果显示，当垂直扩散系数增加时，粒子通量在空间分布的不均匀性将会变小，蓄水池现象变得更加明显。然而，如果激波加速强度随径向距离 $r$ 减小得比 $r ^ { - 2 . 5 }$ 慢时，基于非线性引导理论对垂直扩散系数的限制，那么蓄水池现象可能会消失。因此，对缓变型SEP事件的蓄水池现象的观测可以被用来定性地检测粒子扩散和激波加速理论。

从上面汪洋等人的模拟工作中可以得出，即便垂直扩散比平行扩散弱得多，垂直扩散仍然在粒子的传播过程中起着不可忽视的作用。垂直扩散可以用于解释许多观测现象，特别是当观测者所在的位置没有通过行星际磁力线与源区直接相连时，垂直扩散是粒子到达观测点的最可能途径。

# 2.4 SEP传输方程的求解

研究高能粒子在行星际空间中的传输时需要求解聚焦传输方程。一些学者[29,60.61]采用有限差分方法对方程进行离散求解。Lario等人[2利用时间分步法将传输方程（见式（7)）分裂成4个一维方程 $( \mu _ { 1 } - , r - , p - , \mu _ { 2 } -$ 方程)， $\mu _ { 1 }$ 方程解释了一半的由 $\mu$ 产生的效应; $^ { r - }$ 和$p -$ 这两个方程分别解释 $\boldsymbol { r }$ 和 $\pmb { p }$ 的变化；最后 $\mu _ { 2 }$ 方程解释了由 $\mu$ 产生的另一半的效应。这4个一维方程在每 $1 / 4$ 的时间步用有限差分格式求解(根据每个方程的特点选择具体的差分格式)。对于维数较低的传输方程，利用有限差分方法可以得到较高精度的数值模拟结果；但当传输方程维数较高时，数值计算的效率就会很低。

近年来，随机微分方程方法被一些学者用来求解聚焦传输方程，因为聚焦传输方程的本质是Fokker-Plank方程，而在数学上也可以证明随机微分方程和Fokker-Planck方程是相互等价的62。使用这种方法，聚焦传输方程被分解成一个粒子的两项单粒子运动：一项是确定项，一项是随机项。随机项描述了粒子的一个扩散过程[6]。李刚等人[37.41利用把传输方程分解成一个高能粒子的两项单粒子运动，提出用蒙特卡洛方法来研究带电粒子在缓变型 SEP事件中的传播。模型中确定项的部分描述粒子在Parker螺旋磁场下的运动，随机部分描述了粒子和太阳风湍流相互作用的扩散过程。利用蒙特卡洛方法模拟高能粒子在行星际空间中传输过程的好处是程序相对比较简单，特别是在研究脉冲型SEP事件时，如果不需要考虑具体的加速过程，可以通过蒙特卡洛方法模拟得到在任意空间和时间的能谱3。张明等人[]开发了一种计算 SEP在三维日球层磁场的传播模式，该模式采用后向随机微分方程解聚焦传输方程。模拟结果显示了观测者处于行星际空间不同的经度、纬度以及径向距离时，SEP 通量和各向异性随时间的演化过程。该模式的优势是日球层磁场并不局限于Parker螺旋磁场，任意位形的三维日球层磁场都可以作为模式参量，而且容易扩展到高维，容易实现并行计算，数值误差小。图8比较了差分方法和随机微分方程方法的计算结果，模型中忽略了绝热冷却和垂直扩散，最后得到两者的计算差别在 $5 \%$ 以内，但是，随机微分方程方法数值模拟在计算时间上有明显的优势。

![](images/4790b0977c2a10aacace5c2c9bbbbedb3ffe962ac67d88435774c6ac941bd312.jpg)  
图7在有垂直扩散 (实线)与没有垂直扩散(虚线)的情况下，对比 $\mathsf { 5 ~ M e V }$ 质子的通量和各向异性 [35]虚垂线标示激波通过1AU的时刻：两个短垂线标示观测者所在的磁力线与激波面相连的时间段；不同格子里面的图对应于激波被指向不同的方向的情况；源的强度随着径向和角距衰减， $S \simeq ( r / r _ { c } ) ^ { - 2 } \exp ( - | \phi | / 1 5 ^ { \circ } )$ ：标示为“ $E ^ { \prime }$ 的曲线显示的是cobpoint效率随时间的变化。

# 3 MHD太阳风模型

SEP 事件中的高能粒子在不同的时间尺度内被耀斑过程或者CME 驱动的激波加速，并且在被扰动后的行星际磁场和太阳风中传输，这些过程都紧紧依赖于太阳风背景场。从图1中也可以看出，模拟缓变型SEP事件时，CME及其驱动激波的传播参数与粒子注入率有着密不可分的关系。因此，获取更加接近物理真实的背景场是模拟SEP事件不可或缺的部分。目前对背景场的模拟主要采用MHD模拟，下面简要介绍可用于获取CME 激波传播参数的MHD 太阳风模型的研究结果，以期将包含更真实丰富物理内容的太阳风背景加入到SEP 物理模式中。

![](images/a1c638eb7a9fa8b110a0720a6538e91632d71fd1dd2065e4a568d5af67ef78d8.jpg)  
图8差分方法和随机微分方程方法模拟高能粒子的全向通量和各向异性随时间变化的对比图 157

描述日冕/行星际激波传播的模型中，有较简单将激波模拟为半球形、并以恒定速度沿径向从太阳表面向外传播的模型(15.18，也有复杂的 MHD 模型。基于 MHD 的三维数值模拟的模型中，根据不同的太阳风速度、密度、温度等边界条件求解磁流体力学方程组而获得稳态的背景太阳风分布。在此基础上，以不同的方法加入CME或激波等扰动，对CME 和激波的传播过程等进行分析。冯学尚等人从物理、格式和计算方面对日冕行星际过程的三维数值模拟工作中要注意的问题进行了较完整的总结，下面对一些模型进行简单的介绍。

# 3.1 空间天气框架模型

空间天气框架模型（SWMF）由美国密西根大学牵头的空间环境建模中心（CSEM）及其他10 多家合作单位共同开发。SWMF包括日冕模型、太阳爆发事件模型、内日球层模型以及其他区域模型。各个模块可以独立运行，也可通过标准接口耦合起来。SWMF 的日冕模型、内日球层模型及其他区域模型均采用 Roe 迎风格式[67.6 (Block Adaptive TreeSolar-wind Roe-type Upwind Scheme:块自适应树型太阳风Roe 迎风格式，BATS-R-US),采用块自适应树型结构网格，可以根据解的物理性质对计算网格进行加密或放粗。Toth 等人全面介绍了SWMF的整体结构及其在各方面的最新发展。

Manchester 等人[70-72用 BATS-R-US 代码建立一个三维 MHD 数值模型来描述 CME从太阳日冕到1AU的演化过程；在边界条件的确定中，此模型固定底部开放场区的各物理量，然后求解MHD方程组存在间断的黎曼问题以得到计算区域内的质量、能量、动量等各种通量，从而利用差分格式求解。图9给出，当CME接近1AU时CME和扰动太阳风的性质。这个模型用来探究激波后的鞘区是如何形成的，因为粒子加速过程主要依赖于这个区域的拓扑结构的演化情况。他们分析了沿着磁力线的密度和磁场强度的跳跃变化，这些量反映了等离子体和磁场的压缩比，这对研究扩散加速、一阶费米加速、磁泵（magneticpumping）加速机制对粒子的加速效果具有重要意义。他们还认为随着激波后磁场强度的突然增加，在这些加速机制的作用下，粒子的能量能够达到 $\mathtt { G e V }$ 的量级。

![](images/5754b6198cf5e8dc886cc288ab3b8aac8f7d97edd6422fbb4faae30e3a7566e5.jpg)  
图9当激波波前到达地球时CME 和扰动太阳风的速度、密度、温度和磁场强度的参数值！ $\mathit { \Omega } _ { \left. x \right. = 2 1 4 \ R _ { \mathrm { s } } } ^ { }$ 2 =20 Rs)[72]

# 3.2 日冕-日球层模型

日冕-日球层模型（CORHEL）是美国集成空间天气建模中心(CISM)开发的，由日冕和日球层两个模型耦合而成。日冕模型包括三种选择：(1)用势场源表面(PFSS)模型获得日冕磁场的WSA（Wang-Sheey-Arge）模型；(2）能量方程中采用多方过程的MAS（the

MHD-Around- $\mathbf { a }$ -Spheremodel）模型；(3)能量方程中采用热动力学过程的MAS模型。为了计算 $2 0 ~ R _ { \mathrm { s } }$ ( $R _ { \mathrm { s } }$ ：太阳半径)或 $3 0 ~ R _ { \mathrm { s } }$ 至1AU处的日球层的MHD变量，日球层模型可以选择ENLIL 模型或者日球MAS模型。CORHEL 所包含的模型及其输入输出见图 $1 0 ^ { [ 7 4 ] }$ 。WSA模型以光球视向磁场观测为输入，用PFSS 模型获得日冕磁场，根据源表面处(通常为2.5$R _ { \mathrm { s } }$ ）的日冕磁场相对于对应的光球磁场的膨胀因子，以及磁力线在光球上的足点与开闭场边界的角距离，利用经验公式确定自某一点发出的太阳风经过加速之后的最终速度。MAS 是一个三维时变MHD有限差分日冕模型，其中磁感应方程用Maxwell方程组的两个旋度方程和欧姆定律代替，引入矢量势表示磁场。ENLIL 模型中用修正的TVDLF（Total VariationDiminishingLax-Friedrich）格式计算三维时变MHD方程。此模型详见文献 [65,74]。

GONG  
HMI 日冕模型 内日球模型 外日球模型  
KPVT MDI 势场源表面 MAS多方 2 MAS串行 MAS并行 3？  
MWO MAS热动力学 ENLIL模型  
SOLIS ？ ？  
WSOba 1+ 1AU或其他白光图像 地方的v,B,n,T? 冕洞边界 日球电流片辐射图像 全球CIR结构

红色框代表输入，蓝色框为相应模型，绿色框代表输出，未来潜在的发展内容用“？”表示。

# 3.3 太阳行星际守恒元模型

太阳行星际守恒元解元(SIP-CESE)模型由我国空间天气学国家重点实验室冯学尚等人[75-82开发，是从太阳表面出发直至行星际空间的三维数值模型。控制方程采用守恒形式的MHD 方程组，模式的特点是在数值格式中将时间和空间不加区别作为一个整体，并且对空间微分作为待解变量，物理量在解元(SE)内假定是光滑可微的，而在相邻的SE之间或者在守恒元(CE）内可以出现间断。该方法在实际计算中，能够有效避免日地空间模拟中所涉及的球壳计算区域通常产生的极区奇性和网格收敛性问题。SIP-CESE模式可以满足磁场散度为零的条件，无需特别处理，并引入了非奇异变换，使得自适应网格技术(AMR)容易实现，计算效率得以提高。目前该模式用于日冕行星际太阳风背景的研究[75-79,81-84]、太阳活动区磁场重构[80.85,88和扰动事件的模拟(87.88]，可用于预报和研究行星际背景参数和日冕物质抛射及其驱动激波传播参数。冯学尚等人用改进后的 SIP-CESEMHD 模型结合AMR 技术，研究了4个不同卡林顿自转周（CR）内（CR1967,CR2009,CR2060 和CR2094）的太阳风背景，并与SOHO 和OMNI的观测结果进行对比，图11是计算得到的1AU准稳态太阳风参数与OMNI数据的对比，所得到的太阳风密度、速度和磁场结构呈现出该时期背景太阳风结构的典型变化特征。

![](images/9b3155812e14a4382cbb9a0d705381dde9ab6fe8f5967bd62ab83fac31e27bf4.jpg)  
图11周期内的太阳风参数在1AU处的模拟结果与观测结果的对比[83](a)CR1967；(b)CR 2009；(c)CR 2060:(d)CR2094。红色线代表模拟的结果；绿色线代表OMNI 的观测数据。从上到下依次为太阳风速度 $V _ { \ r }$ 、等离子体密度 $\scriptstyle { n }$ 、温度 $\boldsymbol { \tau }$ 和径向磁场 $\scriptstyle B _ { \tau }$ 。

# 3.4 日冕行星际区域组合MHD（COIN-MHD）模型

日冕行星际区域组合(COIN)MHD模型，是冯学尚等人[开发的从太阳表面出发直至行星际空间的又一个三维数值模型，该模式将从日面到行星际空间的太阳风计算区域分为日冕区域(大约为 $1 \sim 2 2 ~ R _ { \mathrm { s } } ^ { \ \cdot }$ ）和行星际空间区域（ $1 8 \ R _ { \mathrm { s } } \sim 1$ AU）两部分。在日冕区域，先用TVDLF守恒差分格式计算出新时间步的值，再将磁场部分用MacCormackII型格式的计算结果替换掉；而在行星际空间区域用MacCormackI格式求解与时间无关的定态MHD方程组。

随后，沈芳等人[90,91]在 $2 . 5 ~ R _ { \mathrm { s } }$ 处构建了适合不同太阳活动时期的自洽源表面结构，为原来的COIN-MHD 模式提供了以观测为基础的自洽初边值条件。此外，他们还提出一种新的快捷高效的异步并行时间推进法，并应用到三维太阳风及CME传播的MHD数值模拟中；即针对日冕和行星际空间物理性质的不同，根据各自的网格采用不同的计算步长向前推进，得到了精度比较高的结果，且计算时间比单一步长缩短了 $8 0 \%$ 多，为建立快捷的太阳风模式提供了重要参考[92]。沈芳等人[9将改进后的模式应用到三维太阳风背景、CME 传播及相互作用等方面的研究中，以2001年3一4月CME 相互作用事件为例，比较了两个CME 在L1点 $( 2 1 3 \ R _ { s } )$ 的磁场和等离子体参数的模拟结果与ACE飞船的观测结果(见图12)，发现模拟结果可以再现和解释飞船观测到的多重磁云的一些基本特征。

上面列出的模型中，SWMF模型以强大的并行计算能力为基础，可以实现从太阳日冕到地球空间环境的集成研究，但是耗时长。CORHEL模型中对日冕区和日球层区分开处理，体现了模型灵活的特点。其中MAS可以实现底部边界电磁场条件的连续更新，因此该模型可以研究日冕结构的演化，进而为日球层模型提供接近实际的输入；而ENLIL 模型中采用维度分裂技术提高计算效率，应用区域分解法实现并行计算。SIP-CESE不仅在日冕和行星际空间采用统一的处理方法，而且在时间和空间也采用一致的处理方法，它区别于所有现有太阳风模型所使用的差分格式而充分体现时空守恒的理念。COIN模型针对日冕和行星际的不同特点，采用不同的数值格式，提高了计算效率[5]。上述模型所得到的结果在一定程度上能够反映观测事实，在模拟太阳风速度、密度、总磁场的变化上具有较好的准确性，对CME 或激波扰动的模拟结果能够定性地再现卫星实地观测到的某些物理量的变化趋势。因此，可以研究在有结构太阳风背景下SEP的传播，以期对SEP事件有更加深入的了解。

# 4缓变型SEP事件激波-粒子模型

Heras 等人[13.14首次开发了关于模拟缓变型 SEP 事件的激波-粒子传播模型（Shock-and-Particle Model)；Lario 等人[16,29进一步优化了Heras 的模型，并提出 MHD 变量与粒子注入率的 $Q ( V R )$ 关系。Rosa 在Lario 等人[12.16,29] 建立的激波-粒子模型的基础上进一步完善了模拟缓变型SEP事件的激波-粒子模型，这个模型的关键在于加入了观测者的纬度这一因素。他们利用Lario 等人[建立的MHD 变量与粒子注入率的 $Q ( V R )$ 关系，用三维MHD模拟行星际激波，首次研究了激波强度的演化、激波加速粒子注入率的影响、质子通量剖面的变化与观测者所在纬度的可能相关性。Rosa 等人i6将三维MHD 模型和粒子模型结合在一起，提出研究缓变型 SEP事件的三维激波-粒子混合模型，其显著优势是可以通过Lario等人提出的 $Q ( V R )$ 关系式，将粒子模型所需要的注入率用激波模型中的速度计算得到，从而实现了对粒子模型的无间断输入。下面简要总结他们的工作，本章主要参考Rosa及其中相关文献的内容。

# 4.1 激波模型

背景太阳风初始条件采用一维Parker流体力学解，磁场用偶极子场，以它们作为输入，采用时间松弛法达到稳定状态。初始的磁偶极子位形消失，开放和闭合磁力线区域形成。为了形成快慢太阳风，作者采用了Groth等人[9的半经验方法，即在能量方程中引入额外的加热项。轴对称的背景太阳风模型用三维球坐标 $( r , \theta , \varphi )$ 下的MHD方程模拟。此模型的详细介绍参看参考文献[96]。

在背景太阳风中叠加一个高密度高压的等离子体团来形成激波，激波的速度 $v _ { \mathrm { c m e } }$ 和方向 $\varphi _ { \mathrm { c m e } }$ 给定。扰动的速度和密度剖面计算公式如下：

![](images/4f91ec2fee0d92277409a951271028c29b6498a597031ab82824d68aa9236395.jpg)  
图122001年L1点 $( 2 1 3 ~ R _ { \mathrm { s } } )$ ）处磁场和等离子体参数的模拟结果与ACE飞船的观测结果对比(93](a）和(b）分别代表ACE 的测量参数和模拟结果，图中从上到下依次为：地心太阳黄道坐标系(GSE,ge0centric solarecliptic system）下的磁场强度 $| B | ( \mathbf { n T } )$ ， $B _ { z } ( \mathbf { n T } )$ 、质子数密度、质子温度、速度以及等离子体 $\beta$ 。其中，蓝色实线表示激波到达L1点的时间，2条红色虚线代表第一个磁云的开始与结束时间，绿色虚线表示第二个磁云的开始时间。

$$
\alpha = \frac { \alpha _ { \mathrm { c m e } } } { 2 } \left( 1 - \cos \pi \frac { d _ { \mathrm { c m e } } - d } { d _ { \mathrm { c m e } } } \right) ,
$$

其中，α 代表密度或者是径向速度，αcme是α的最大值，dcme为等离子体团的半径，d为球心距离。

激波强度用 $V R = [ V r ( d ) - V r ( u ) ] / V r ( u )$ 表示， $\boldsymbol { u }$ 和 $d$ 分别代表激波的上游和下游。此模型中，粒子的加速过程被忽略，激波被处理成一个源项。

# 4.2 高能粒子的传输模型

在研究太阳风中的高能粒子的传输时需要求解聚焦传输方程，Rosa 等人采用Ruffolo发展的聚焦-扩散方程(见方程(7))，其中t是时间，μ为投掷角的余弦值，r是日心距离，p是粒子的动量，u是粒子的速度，ψ是径向方向同当地磁场方向的夹角，L是磁场聚焦尺度，Dμu是扩散系数，Usw是太阳风径向速度。此方程建立在混合坐标系下$( r , \ t , \ v _ { \mathbf { s w } }$ 是固定参考系下的变量； ${ \boldsymbol { p } } , \ v , \ \mu$ 是太阳风参考下的变量)，包括粒子沿行星际磁场流动，投掷角扩散过程，绝热减速，太阳风对流和磁场聚焦过程。为了解释缓变型事件，需要在运动激波中假定一个连续的粒子的注入，在方程中的表现形式为 $G ( t , \mu , r , p )$ ，它与相空间中激波加速粒子的注入率 $\boldsymbol { Q }$ 的关系为 $G ( t , \mu , r , p ) = A ( r ) Q ( t , \mu , r , p )$ ， $A ( r )$ 为磁通量管的横截面，在cobpoint 位置上计算得到。 $Q$ 和 $G$ 与cobpoint的MHD参数相关。能量粒子的传输模型假定一个行星际磁场为Parker 螺线的稳定的太阳风条件，但这样的近似只有当上游太阳风没有大幅扰动的情况下才适用；而且假定粒子注入发生在cobpoint，粒子只沿着磁力线方向扩散，这也是该模型的不足之处。对于粒子的传输方程，Dalla等人用单粒子一阶绝热理论在Parker螺旋场中验证了粒子的漂移速度在SEP传播模拟中不能被忽视，而漂移在此传输方程中是被忽略的，漂移对部分电离的SEP重离子的影响相对于质子来说更强。因此，粒子的传输方程也需要进一步完善。

$$
\begin{array} { r l } & { \frac { F ( t , \mu , r , p ) } { \partial t } = - \cos \psi \frac { \partial } { \partial r } \times \left\{ \left[ \upsilon \mu + \left( 1 - \mu ^ { 2 } \frac { \partial ^ { 2 } } { c ^ { 2 } } \right) u _ { \omega } \sec \psi \right] F ( t , \mu , r , p ) \right\} - } \\ & { \qquad \frac { \partial } { \partial \mu } \left\{ \left[ \frac { \upsilon } { 2 L ( r ) } \left( 1 + \mu \frac { n _ { \infty } \ \kappa _ { \infty } } { \pi } \sec \psi - \mu \frac { v _ { \infty } \pi } { c ^ { 2 } } \operatorname { s e c } \psi \right) \right] ( 1 - \mu ^ { 2 } ) F ( t , \mu , r , p ) \right\} , } \\ & { \qquad \frac { \partial } { \partial \mu } \left\{ \left[ v _ { \infty } \left( \cos \psi \frac { \mathrm { d } } { \mathrm { d } r } \operatorname { s e c } \psi \right) \mu \right] ( 1 - \mu ^ { 2 } ) F ( t , \mu , r , p ) \right\} + } \\ & { \qquad \frac { \partial } { \partial \mu } \left\{ D _ { \mu \mu } \frac { \partial } { \partial \mu } \left[ \left( 1 - \mu \frac { v _ { \infty } \pi } { c ^ { 2 } } \operatorname { s e c } \psi \right) F ( t , \mu , r , p ) \right] \right\} + } \\ & { \qquad \frac { \partial } { \partial \mu } \left\{ p _ { \infty } \left[ \frac { \sec \psi } { 2 L ( r ) } ( 1 - \mu ^ { 2 } ) + \cos \psi \frac { \mathrm { d } } { \mathrm { d } r } \operatorname { ( s e c } \psi ) \mu ^ { 2 } \right] F ( t , \mu , r , p ) \right\} + } \\ & { \qquad \frac { \partial } { \partial r } \left\{ \left[ \upsilon , r , p \right] \ \right\} . } \end{array}
$$

# 4.3 主要结果

Rosa[ 分别在0.4AU和1.0AU处假定了9个虚拟的观测点，用3D MHD 模拟了两个行星际激波 (快激波和慢激波)，运用激波-粒子模型，合成假定事件的通量剖面。图13给出了快激波条件下由粒子传输方程模拟得出的质子通量剖面，图中每一列代表观测者的经度，不同的线型代表观测者的纬度。上面3组图是观测者处于0.4AU处的模拟结果，下面3组图是观测者处于1.0AU的模拟结果。模拟结果显示在同时考虑径向距离时，观测者纬度的变化可能导致高达一个量级的强度变化（比如处于西经 $4 5 ^ { \circ }$ 的观测者)，说明在缓变型事件的模拟中，纬度与峰值强度的相关性是不容忽视的因素；因此，缓变型SEP事件在纬度上的演化情况和经度方向上的演化情况一样也要得到研究者的重视。

# 5总结与展望

对基于MHD太阳风模拟的SEP 物理模式进行研究，关键是建立两种模型的联系，将描述三维日冕物质抛射驱动的激波演化模型与描述粒子在行星际空间中加速和传输的粒子模型耦合起来。在之前模拟激波的模型[1.16.18中，一般假定行星际磁场是Parker 场，假设激波面为平面或球面，而且不考虑粒子在下游的传输过程等。但是实际情况下，特别是在太阳爆发期间，行星际的磁场结构会受到剧烈地扰动，导致粒子在行星际传播时，加速和传播的过程复杂很多。因此，未来的研究工作中可以尝试加入真实的三维背景太阳风模型和三维CME 激波模型，并且考虑两个CME在很短的时间尺度上接连爆发时对激波加速粒子的影响，从而更加深入地研究粒子的加速和传播过程。

![](images/b01055f0ebf9a40561e7be2bf1692b3ec9cfc0df6929243ae671f5433168645d.jpg)  
图13能量为 $\mathrm { 1 ~ M e V 1 }$ （蓝色线）和能量为 $3 2 \mathrm { \ M e V }$ （红色线）的质子通量剖面 [98]的线型代表观测者的纬度。（a）观测者处于0.4AU处的模拟结果：（b）观测者处于1.0AU 的模拟

对于缓变型 SEP 事件的混合模拟，需要结合3个模块：(1)CME 及其驱动的激波的触发和传播模型；(2)CME 驱动的激波的粒子加速模型；(3)SEP在三维行星际空间中的传播模型。对于第一个模块，建立CME 驱动的三维激波从太阳附近（比如 $2 ~ R _ { \mathrm { s } } ^ { \prime }$ ）到行星际传播的演化模型，以此获取激波沿磁力线的cobpoint的参数，作为粒子加速模型的输入参数。对于第二个模块，建立基于聚焦传输方程的各向异性的一维激波加速模型，同时考虑沿磁力线的激波加速和存在垂直扩散时激波的加速过程。对于第三个模块，可以尝试加入实时变化的太阳风速度及接近物理真实的太阳风背景磁场，并且统计在不稳定的激波下游区域传播的粒子，以期得到更真实的粒子在三维行星际空间的传播物理过程。综上所述，建立三维CME驱动激波模型、激波加速粒子模型和SEP在三维行星际空间传播模型的耦合模型，通过针对具体 SEP事件的数值模拟，将观测数据分析工作与模型计算密切有机地结合，不断检验和改进所发展的SEP加速和传播模型，是未来研究SEP事件的具有挑战性的研究方向。

# 参考文献：

[1] Rodriguez-Gasén R.PhD thesis,Barcelona:Univ.de Barcelona,2011   
[2]Kallenrode M. Space physics:an introduction to plasmas and particles in the heliosphere and m   
spheres.Berlin: Springer,2004   
[3] LiG.Proceedings of the 32nd International Cosmic Ray Conference,2011,12:119   
[4] Kallenrode M. Journal of Physics G: Nuclear and Particle Physics,2003,29:965   
[5]Desai M,Mason G,Wiedenbeck M,et al.ApJ,2004,611:1156   
[6] Tylka A,Cohen C,Dietrich WF,et al.ApJ,2005,625:474   
[7] Cohen C MS,Mewaldt R A,Leske RA,et al.Space Sci.Rev.,2007,130:183   
[8] Reames D V.Spa.Sci.Rev.,1999,90:413   
[9] Kahler S W. Space Weather, Geophysical Monograph,vol. 125.Washington DC: American Geol   
Union,2001:109   
[10] Shea M A,Smart D F.Adv.Space Res.,1996,17:225   
[11] Feng X S,Xiang C Q,Zhong DK.Scientia Sinica Terrae,2013,43:912   
[12]Aran A.PhD thesis.Barcelona:Universitat de Barcelona,2007   
[13] Heras A M,Sanahuja B,Lario D,et al.ApJ,1995,445:497   
[14]HerasA M,Sanahuja B,Smith ZK,et al.ApJ,1992,391:359   
[15] Kallenrode M,Wibberenz G.ApJ,1997,102:22311   
[16] Lario D,Sanahuja B,HerasA M.ApJ,1998,509:415   
[17] Ng C,Reames D,Tylka A.Geophys.Res.Lett.,1999,26:2145   
[18]Kallenrode M.JGR,2001,106:24989   
[19]Jones F C,Ellison D C.Space Sci.Rev.,1991,58:259   
[20] Lee MA.ApJ,1983,88:6109   
[21]Gordon BE,Lee M A,et al.JGR,1999,104:28263   
[22] Lee MA.ApJ,2005,158:38   
[23] Vainio R,Schlickeiser R.A&A,1999,343:303   
[24] Sokolov IV,Roussev II,Fisk L A,et al.ApJ Lett.,2006b,642:L81   
[25] Heras A M,Sanahuja B,Sanderson T R,et al.JGR,1994,99:43   
[26] Shen F,Feng X S,Wu S T,et al.JGR,201la,116:A04102   
[27] $\mathtt { N g } \subset \mathtt { K }$ ,Reames D V,Tylka A J.International Cosmic Ray Conference,20o1,8:3140   
[28] Lario D.Adv.Space Res.,2005,36:2279   
[29] Lario D,Sanahuja B,Heras A M.Adv.Space Res.,1997,20:115   
[30] Aran A,Sanahuja B,Lario D.Adv.Space Res.,2006,37:1240   
[31] Fermi E.ApJ,1954,119:1   
[32] Melrose D B.Ap&SS,1997,242:209   
[33] Parker E N.Planet.Space Sci.,1965,13:9   
[34] Drury L.Oc.Rep.Prog.Phys.,1983,46:973   
[35]Wang Y,Qin G,Zhang M.ApJ,2012,752:37   
[36] Zank G,Rice W,Wu C. JGR,2000,105:25079   
[37] LiG, Zank G,Rice W. JGR,2003,108:1082   
[38] $\tt N g C$ ,Reames D,Tylka A.ApJ,2003,591:461   
[39] Sokolov I,Roussev I,Gombosi T,et al. ApJ,2004,616:L171   
[40] Rice W, Zank G,Li G.JGR,2003,108:1369   
[41] LiG,Zank G P,et al. JGR,2005,110: A06104   
[42]LiG,Zank G P,et al.Geophys.Res.Lett.,2005,32:L02101   
[43] Cane H V,et al. Geophys.Res.Lett.,2003,30(12):8017   
[44] Zank G P,Li G, Verkhoglyadova O. Space Sci. Rev.,2007,130: 255   
[45] Verkhoglyadova O P,G Li,et al.JGR,2010,115:A12103   
[46] Li G,Shalchi A,et al.Adv. Space Res.,2012,49:1067   
[47] Terasawa T,Oka M,Nakata K,et al. Adv.Space Res.,2006,37:1408   
[48] Qin G,Zhang M, Dwyer JR, Rassoul H K.ApJ,2004,609:1076   
[49] Isenberg P A. JGR,1997,102:4719   
[50] Florinski V,Decker RB,le Roux JA.JGR,2008a,113:A07103   
[51] Zuo P B,Zhang M,et al.ApJ,2011,738:168   
[52] Zuo PB,Feng X S.CHIN.PHYS.LETT.,2013,30:019601   
[53] Jokipii JR. ApJ,1966,146: 480   
[54] Dwyer JR,Mason G M,et al.ApJ,1997,490:L115   
[55] Zhang M,Jokipii JR,McKibben R B.ApJ,2003,595:493   
[56] Matthaeus W H,Qin G,Bieber J W,Zank G P.ApJ,2003,590:L53   
[57] Zhang M, Qin G,Rassoul H. ApJ,2009,692:109   
[58] Qin G,He H Q, Zhang M. ApJ,2011,738: 28   
[59] Qin G,Wang Y,et al. ApJ,2013,766:74   
[60] Earl JA. ApJ,1974,188:379   
[61] Ruffolo D. ApJ,1995,442: 861   
[62] Gardiner CW.Handbook of Stochastic Methods for Physics,Chemistry,and the Natural Sciences.Berlin:   
Springer,1983   
[63] Zhang M.ApJ,1999,513:409   
[64] Shi L W,Shen C L,et al. Progress in Astron.,2013,31:267   
[65] Feng X S,Xiang C Q,Zhong DK.Sci Sin-Terrae,2011,41:1   
[66] T6th G,Sokolov I V,Gombosi T I,et al. JGR,2005,110(A12):A12226   
[67] Powell KG,Philip L R,Timur JL,et al. JGR,1999,154:284   
[68] Ilie R, Liemohn M W,Kozyra J,et al. Proc.R. Soc.A., 2010,466:3279   
[69] Tóth G,van der Holst Bart,Sokolov I V,et al.J. Comput.Phys.,2012,231:870   
[70] Manchester W B,Gombosi T I,Roussev I,et al.JGR,2004a,109:1102   
[71] Manchester IV W,Gombosi T I,et al. ApJ,2005,622:1225   
[72] Manchester W B,Ridley A J,Gombosi TI,Dezeeuw DL.Advances in Space Research,2006,38: 253   
[73] Arge C N,Pizzo V J. JGR,2000,105:10465   
[74] Riley P, Linker JA, Lionello R,et al. J Atmos Sol-Terr Phys,2012, 83: 1   
[75] Feng XS,Zhou Y F,Wu S T.ApJ,2007,655:1110   
[76] Hu Y Q,Feng X S,Wu S T,Song WB.JGR, 2008,113:A03106   
[77] Feng X S,Yang L P,Xiang C Q,et al. ApJ,2010,723:300   
[78]Feng X S,ZhangSH,Xiang CQ,et al.ApJ,2011,734:50   
[79] Feng X S,Jiang C W,Xiang CQ,et al.ApJ,2012,758:62   
[80] Jiang CW,Feng XS,Wu S T,et al.ApJ,2013,771:L30   
[81] Feng X S,Zhong D K,Xiang $\textsc { c Q }$ ,et al.Science China: Earth Sciences,2013,56:1864   
[82] Feng X S,Xiang C Q,Zhong D K,et al. Computer Physics Communications,2014,185:1965   
[83]FengX S,YangLP,Xiang CQ,et al.Solar Phys.,2012,279:207   
[84] YangLP,FengX S,Xiang C Q,et al.JGR,2012,117:A08110   
[85]Jiang CW,FengX S,Fan YL,et al.ApJ,2011,727:101   
[86]JiangCW,FengX S,XiangCQ.ApJ,2012,755:62   
[87] Zhou Y F,Feng X S.Sci China Ser E-Tech Sci,2008,51:1   
[88] Zhou YF,FengXS,Wu S T,et al.JGR,2012,117:A01102   
[89]冯学尚，向长青，钟鼎坤，等.科学通报，2005，50:820   
[90] Shen F,Feng X S,Xiang C Q,et al.J Atmos Sol-Terr Phys,2010,72:1008   
[91] Shen F,Feng XS,Xiang C Q.J Atmos Sol-Terr Phys,2012,77:125   
[92] Shen F,Feng X S,SongW B.Sci China Ser E-Tech Sci,2009,52:2895   
[93] Shen F,Feng X S,Wang Y,et al.JGR,2011,116:A09103   
[94] Parker E N.ApJ,1958,128:664   
[95] Groth C P T,de Zeeuw D L,et al. Adv. Space Res.,2000,26: 793   
[96] Jacobs C.PhD thesis,Leuven:Katholieke Univ. 2007   
[97]Dalla S,Marsh MS,Kelly J,Laitinen T. JGR,2013,118:5979   
[98] Rodriguez-Gasén R,Aran A,et al. Solar Phys.,2014,289:1745

# Research Progress on the Solar Energetic Particle Model Based on Magnetohydrodynamic Simulation

WEI Wen-wen1,2， SHEN Fang1， ZUO Ping-bingl

(1.State Key Laboratory of Space Weather，Center for Space Science and Applied Research,Chinese Academy of Sciences，Beijing 100190, China; 2. University of Chinese Academy of Sciences, Beijing 100049,China)

Abstract: Solar energetic particle (SEP) can destroy the spacecraft,and has great influence on human activities.Thus,it is of importance to forecast SEP events. SEP events can be divided by three general categories: impulsive SEP events,gradual SEP events and mixed SEP events. Impulsive SEP events, with characteristics of low intensity, short duration,and enhanced He-3,are correlated to solar fares.Gradual SEP events which become the main simulation branch of current research are related to coronal mass ejections (CMEs) and they usually have high flux in protons and last longer. Mixed SEP events maintain complex features of the former two kinds of events.

Several theories and numerical models are applied to simulate gradual SEP events. Each model makes some assumptions to simplify the complex acceleration and transportation processes.No research to date has combined accurate shock evolution，particles injection and acceleration,with their interplanetary transport.In order to develop the physics-based SEP prediction model and improve the ability to forecast SEP events,it is necessary to selfconsistently combine the magnetohydrodynamic (MHD) model that describes CME-driven shock propagation with particle model that simulates the acceleration and transportation processes of particles.

In this paper， firstly，we review current models,which have been used to describe gradual SEP events and their applications. Generally，there are two major approaches to model gradual SEP events: some studies include the acceleration mechanisms of SEPs induced by CME-driven shocks,while others assume a fixed particle injecting source at the shock.In addition,some researchers also consider the effects of perpendicular diffusion on SEPs propagation in three-dimensional interplanetary magnetic fields. These models can partially reproduce the observed properties for SEP events. Then，we make a brief review of numerical MHD simulation models, such as Space Weather Modeling Frame (SWMF), CORonal and HELiospheric (CORHEL) model, Solar InterPlanetary-Conservative Element Solution Element (SIP-CESE） model, COronal INterplanetary (COIN） model. All these models can be used to workout the propagation parameters of CME and CME-driven shocks, which are expected to provide inputs to the particle model. Finally,some discussions of the future work about how to combine MHD and particle models are presented.

Key words: solar energetic particle; shock; MHD solar wind model; interplanetary transport