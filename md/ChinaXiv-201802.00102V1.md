# 超声速膨胀器设计及其内部流动研究

钟兢军，黄振宇，杨凌，韩吉昂(大连海事大学 轮机工程学院，辽宁 大连 116026)

摘要 借鉴超声速喷管和传统涡轮结构与特性，设计了超声速膨胀器。对其内部三维流场的数值研究结果表明，超声速膨胀器能够实现气流膨胀加速，膨胀波的出现导致静压沿节距方向分布不均，流道出口附面层分离、回流、低能流体与主流掺混以及激波附面层相互作用是能量损失的主要来源。

关键词超声速膨胀器；膨胀波；三维流场；数值研究

中图分类号：V231.3 文献标识码：A

# Research on Design and Internal Flow of Supersonic Expander

ZHONG Jing-Jun, HUANG Zhen-Yu, YANG Ling, HAN Ji-Ang (Marine Engineering College,Dalian Maritime University,Dalian 116026, China)

Abstract According to the structure and characteristics of supersonic nozzle and traditional turbine, the structure of supersonic expander was designed. Numerical study of three-dimensional flow field shows that airflow could be expanded and accelerated in the expander,and existing of expansion waves leads to non-uniform distribution of static pressure in the pitch direction. The boundary layer separation, back flow, the low energy fluid mixing with the mainstream, shock waves and boundary layer interaction are the main sources of losses.

Key words supersonic expander; expansion waves; three-dimensional flow filed; numerical research

# 0前言

燃气轮机性能的优劣直接影响其经济性、稳定性和可靠性。涡轮作为燃气轮机核心部件之一，受高温、高应力以及高转速循环作用，工作环境恶劣、流场结构复杂，其性能的好坏对燃气轮机整机性能将产生重大影响。通过降低内部流动损失来提高涡轮性能始终是国内外学者研究课题之一，而基于叶型改进的结构优化是诸多措施中行之有效的方法。文献[1-3]就弯、扭、掠叶片对涡轮内流影响进行了研究，不同程度提高了涡轮性能。随燃气轮机转子转速及涡轮进口温度的不断提高，对涡轮叶片负荷提出了更高的要求，单靠叶型优化减小流动损失、提高涡轮效率难以完全达到预期目标。因此，一些新结构在涡轮设计中得以应用，如变几何涡轮[4]、对转涡轮[5]和两级对转超声速膨胀器[等。两级对转超声速膨胀器是Ramgen 动力系统公司在其ASCE燃气轮机中结合超声速膨胀喷管技术和常规轴流燃气轮机设计技术而提出的一种新型的膨胀做功系统。

在对ASCE结构、性能、技术难度和工作原理分析的基础上，本文设计了一种超声速膨胀器，并对其三维流场进行数值仿真，旨在了解其内部流动规律，获得该部件的主要性能参数，以期能为这种新型膨胀做功系统的设计开发工作提供一定的理论依据和数值仿真基础。

# 1超声速膨胀器三维流道设计

超声速膨胀器(如图1所示)是融合了二元超声速喷管和轴流及向心式涡轮设计技术的一种新型膨胀做功系统，其结构设计的优劣直接决定其膨胀做功性能的高低。出于对整体结构的考虑，同时借鉴喷管[7]、旋转冲压压缩转子[8]结构，本文所设计超声速膨胀器三维流道是在二维流道的基础上通过添加 $z$ 坐标来实现的。

![](images/165dfe4c0eb624c7c8a84399b6cb4e033a227527717da526c70234006a4412f6.jpg)  
图1超声速膨胀器结构图

直角坐标系下，超声速膨胀器二维流道型线如图2所示，由圆弧 $\mathbf { \nabla } _ { A B }$ 和三次曲线段 $B C$ 组成，其中圆弧 $_ { A B }$ 半径为 $R _ { \mathrm { D } }$ 。定义圆心角 $\alpha$ 为初始膨胀角，$E A$ 与 $E A$ 比值 $h _ { \mathrm { o } } / h$ 为进口高度比，圆弧 $\mathbf { \nabla } _ { A B }$ 半径与 $E A$ 比值 $R _ { \mathrm { D } } / h _ { \mathrm { o } }$ 为圆弧半径喉部高度比，出口 $F C$ 截面面积与进口 $E A$ 截面面积之比 $\smash { \mathcal { A } _ { 1 } / A _ { 0 } }$ 为出进口面积比， $\overset { \cdot } { A ^ { \mathrm { ~ C ~ } } }$ 与 $E A$ 之比 $\boldsymbol { e } / h _ { \mathrm { o } }$ 为流道长高比。

如图3所示，三维流道扩张型面母线 $\mathbf { \nabla } _ { A B }$ 、BC上点所对应半径以及 $z$ 坐标分别为：

$$
R _ { y } = y _ { D } + R _ { D } \cdot \cos ( \Delta \alpha )
$$

$$
R _ { q } = a \cdot R ^ { 3 } + b \cdot R ^ { 2 } + c \cdot R + d
$$

$$
R = x _ { _ B } + \beta \cdot l _ { _ { B ^ { \prime } C } }
$$

$$
z _ { y } = R _ { o } \cdot \tan \varphi \cdot \Delta \theta _ { 1 }
$$

$$
z _ { q } = R _ { o } \cdot \tan \varphi \cdot ( \theta _ { 1 } + \Delta \theta _ { 2 } )
$$

其中， $R _ { \mathrm { y } } , R _ { \mathrm { q } } , z _ { \mathrm { y } } ,$ $z _ { \mathrm { q } }$ 分别为母线 $A B , B C$ 上点的半径和 $z$ 坐标； $\varDelta a$ $a , \ \beta , \ \varphi , \ l _ { \mathrm { B ^ { \prime } C } } ,$ 分别为圆心角$\varDelta \theta _ { 1 }$ 对应弧线在直角坐标系下圆弧圆心角，圆心角$\varDelta \theta _ { 2 }$ 的角度系数，隔板在超声速膨胀器轮缘上的安装角度以及直角坐标系中线段 $B ^ { ' } C$ 长度。

![](images/a95e56972eb9a31f50f688e82fe47394a6490977b37b58ce18564af0c7b9517f.jpg)  
Fig.1 The structure of supersonic expander

![](images/b060719b077d0720f17a75c87420e9e5492bffd15575b799cf5f6025955e5105.jpg)  
图2直角坐标系下二维流道图3坐标变换后二维流道型下壁面型线 线  
Fig.2Lines of the bottom wal oftwo-dimensional channel

![](images/89eae1a4333bb8afe7edc350e549183cebc91ed4ac3f2fe45a0634bce8d7bc7b.jpg)  
Fig.3The three-dimensional flow dilated busbar design   
Fig.4 Representation method of three dimensional passage in the supersonic expander

通过以上公式获得三维流道扩张型面母线 $\mathbf { \nabla } _ { A B }$ 和母线BC，并采用UG软件设计出超声速膨胀器三维流道，如图4所示。此外，为便于对计算结果进行分析，参照常规叶轮机械流面的定义方法，本文将流道中相应截面定义为S1和 S2 流面，由吸力面到压力面方向定义为节距方向。

![](images/7e1a754898f8f278c6507bf01c075629d6bf6fd81c595b0c92cf930b9d8818ca.jpg)  
图4超声速膨胀器膨胀流道及表示方法  
图5计算域与边界条件  
Fig.5 Computational domain and boundary conditions

# 2计算模型与数值方法

# 2.1计算模型及边界条件

本文所设计超声速膨胀器三维流道初始膨胀角为 $2 4 ^ { \circ }$ ；隔板安装角 $3 3 ^ { \mathrm { { o } } }$ ；进口高度比0.17；圆弧半径喉部高度比0.5；出进口面积比6；流道长高比6。采用六面体/混合网格对设计的三维流道进行网格划分。为节省资源并提高计算速度，仅对一个三维流道进行数值计算，计算网格约 $7 . 6 \times 1 0 ^ { 5 }$ 。

如图5所示，对于进口边界条件，给定进口总压、静压和总温，出口给定静压。三维流道上壁面、进出口延伸段上壁面设定为绝对静止的绝热壁面，而三维流道下壁面、侧壁面(吸、压力面)和进出口延伸段下壁面都设置为与流体一起转动的绝热壁面。进出口延伸段与三维流道吸、压力面相接的侧壁面设置为周期性边界条件。

# 2.2数值方法

采用Fluent软件对超声速膨胀器三维流道流场进行数值计算。采用的控制方程为三维定常雷诺平均N-S方程，湍流模型为标准 $k \mathrm { - } \varepsilon$ 两方程模型。计算中选用隐式耦合求解算法，方程对流项采用二阶迎风格式离散。

设计的超声速膨胀器三维流道流场在设计和非设计工况下进行数值研究的出口条件均给定静压 $1 5 0 0 0 0 \mathrm { P a }$ 。设计工况下计算条件为：转速 $n _ { \mathrm { d } }$ ${ = } 3 0 0 0 0 \mathrm { { f / m i n } }$ ，进口总压 $p _ { \mathrm { { o } } } ^ { \ast } { = } 1 0 1 3 2 5 0 \mathrm { { P a } }$ ，进口静压$p _ { \mathrm { { o } } } \mathrm { { = } ~ 8 8 1 7 2 8 P a }$ ，进口总温 ${ T _ { \mathrm { { o } } } } ^ { * } { = } 1 2 0 0 \mathrm { { K } }$ 。非设计工况下主要考虑转速和进口总压改变对三维流道流场和性能的影响，分别在 $90 \%$ 和 $1 1 0 \%$ 设计转速以及进口总压为 $7 0 9 2 7 5 \mathrm { P a }$ 、 $8 1 0 6 0 0 \mathrm { P a }$ 、 $1 2 1 5 9 0 0 \mathrm { P a }$ 和$1 3 1 7 2 2 5 \mathrm { P a }$ 时进行了流场计算。

为便于对计算结果进行分析，采用三维流道膨胀比、等熵绝热效率和超声速膨胀器功率对其性能加以评定，相关计算公式如下：

$$
\pi _ { 1 } ^ { * } = { p _ { o } } ^ { * } / { p _ { 1 } ^ { * } }
$$

$$
\eta _ { T } ^ { * } = \frac { \pi _ { 1 } ^ { * ^ { \frac { k - 1 } { k } } } \cdot ( 1 - \frac { T _ { 1 } ^ { * } } { T _ { o } ^ { * } } ) } { \pi _ { 1 } ^ { * ^ { \frac { k - 1 } { k } } } - 1 }
$$

$$
{ \cal N } _ { _ T } = { \cal N } \cdot m g \cdot \delta _ { _ { s e } } \cdot ( \frac { { c _ { o } } ^ { 2 } - { c _ { 1 } } ^ { 2 } } { 2 } - \frac { { w _ { 1 } } ^ { 2 } - { w _ { o } } ^ { 2 } } { 2 } )
$$

其中 $p _ { \mathrm { o } } { ^ \ast } , p _ { \mathrm { l } } { ^ \ast } , T _ { \mathrm { o } } { ^ \ast } , T _ { \mathrm { l } } { ^ \ast } , c _ { \mathrm { o } } , c _ { \mathrm { l } } , w _ { \mathrm { o } } , w _ { \mathrm { l } } , k \ ,$ $N$ ，mg， $\delta _ { \mathrm { s e } }$ 分别为进口以及出口总压、总温、绝对速度和相对速度，绝热指数，膨胀流道总数，燃气流量，二次损失系数。

# 3计算结果与分析

# 3.1设计工况下膨胀器三维流道数值仿真

图6和图7为不同喉部高度S1流面相对马赫数和静压等值线分布图，可以看出，膨胀流道入口，来流相对速度是声速，这是因为垂直于气流方向的流通截面是收扩型的(首先S1流面收缩，之后 S2流面扩张)，膨胀流道入口截面是收缩与扩张流道的临界截面(即喉部)，而来流是亚声的，因此实现亚声气流减压增速并最终在该截面达到声速。进入膨胀流道后气流在顺压梯度作用下继续增速，沿节距方向，速度分布差异较大：气流在入口靠近吸力面出现速度激增区，来流相对马赫数突升，此后在较大范围内维持该速度流动，沿流向气流在局部区域内增速，而同一速度节距方向呈头尖尾宽的二分之一反“C”型分布，压力面附近区域沿流向气流增速则较为均匀，主要因为在膨胀流道入口吸力面处产生膨胀波，使压力沿节距方向分布不均，导致增速的差异性。随喉部高度增加，高速影响范围呈先扩大后缩小趋势，且高速区域基本位于膨胀流道横截面的下半平面，气流最大速度出现在膨胀流道出口近压力面处，并由此处产生一道斜激波，激波之后速度略有下降。

图8为不同喉部高度S1流面熵和流线分布图，可以看出沿气流方向膨胀流道下壁面熵增明显，影响范围扩大，损失逐渐增大。而沿节距方向熵增则呈减弱趋势，主要因为压差作用下，附面层从压力面向吸力面迁移，在近吸力面区域内逐渐堆积，最终导致该区域损失严重。膨胀流道上壁面没有明显熵增区，流动损失情况与主流趋于一致。比较而言，吸力面附近损失明显高于其他区域，吸力面近出口处出现明显熵增区，流动损失很大，主要是斜激波作用下附面层分离、回流、附面层低能气流与主流掺混以及激波附面层相互作用而导致的。膨胀波与激波之后气流均有相应折转，流线上可观察到相应细节。

![](images/9c1d9098904b8c27b36f1d1bacac7700fda0eee872970d35c293200154b49669.jpg)  
图6不同喉部高度S1流面 相对马赫数等值线 Fig.6Relative Mach number contour of S1 with different throat heights

![](images/a9d5d84e3a3fd5a0d1957794054c68dcc70d80ffd8344abc1ce0f72aaa6d118c.jpg)  
图7不同喉部高度S1流面静压等值线Fig.7 Static pressure of S1 withdifferent throat heights

图9和图10给出不同节距S2流面相对马赫数和静压等值线分布，可以看出，膨胀流道喉部出现明显的速度分界，分界线几乎与气流方向垂直，这是因为喉部为临界截面，亚声来流在该截面增至声速，而喉部之后流道下壁面外凸，因此产生膨胀波，且马赫角为 $9 0 ^ { \circ }$ 。沿节距方向，压力大小逐渐由无规则状态向有规律分布过渡，气流加速也逐渐趋于均匀。高速区域位于下壁面附近，这主要是因为膨胀流道入口的膨胀波导致了速度沿径向分布不均，下壁面附近气流速度高、近上壁面速度低。图11给出不同节距S2流面熵和流线分布。可以看出，沿气流方向附面层逐渐堆积，流动损失增加；沿节距方向下壁面附面层逐渐减薄，流动损失降低。这与S1流面看到的现象是一致的。

![](images/56fd8785e680127e8b39cf07e5954ad7c226edfaca579364ff04d4eb2cdc5520.jpg)  
图8不同喉部高度S1流面熵和流线分布图Fig.8 Entropy and streamlines of S1with different throat heights

![](images/5cd4c8f6e322afcab5dc4832c4cbb4787c105a67e4b4ed72d61ab4adaee00496.jpg)

![](images/bea036beba992d7fb9eea3c3e27261ae53c8411612cccb9ddabf13bb18792541.jpg)  
图9不同节距S2流面相对马赫数等值线Fig.9Relative Mach number contour of S2 with

G6G c 95%t b 50%t a5%t

设计工况下超声速膨胀器膨胀比2.13，绝热效率0.836，功率 $1 3 1 4 . 2 1 5 \mathrm { k W }$ ，出口绝对马赫数1.253。与先进亚/跨声轴流及径流式涡轮相比，其膨胀比和效率相对较低，但超声条件下，膨胀器性能则显优越，文献[9]对某级超声速涡轮进行研究，设计工况下，静叶进口马赫数$\scriptstyle M _ { 0 } = 0 . 1 2$ ，静压 $1 5 . 2 \mathrm { M P a }$ ，静温 $T _ { \mathrm { o } }$ 大约1232K，转子转速 $3 1 3 0 0 \mathrm { r p m }$ ，等熵效率0.608，涡轮动叶膨胀比1.492。此外，由于超声速膨胀器采用隔板结构替代传统涡轮叶片，因此结构更为简单紧凑，制造成本降低。

# 3.2转速对膨胀器三维流道性能的影响

$90 \%$ 及 $1 1 0 \%$ 设计转速计算结果如图12和图13，设计转速的计算结果如图6和图8。由图12可以看出，随转速增加，流道内沿流向速度梯度减小，气流增速逐渐均匀。这主要是因为，转速增加时膨胀器对外做功增加，而等熵绝热条件下气流总能不变，因此气流流速相应降低。在 $90 \%$ 设计转速时，维持转子旋转所需能量减小，流道中气流速度增加，特别是膨胀流道出口近压力面处高速区范围明显扩大，直接导致出口斜激波强度增加，激波后静压显著上升，流动损失加剧。而在 $1 1 0 \%$ 设计转速时，流道中气流增速均匀，高速影响范围缩减，节距方向速度梯度减小，出口斜激波强度降低。因此，随着转速增加，膨胀器膨胀能力相应增强，膨胀比增大，如图14。

![](images/38ff143b3ef83f912ffe6556bd589bda9fbe2b18d64f6c40eeb9cda09ab23f49.jpg)  
图10不同节距S2流面静压等值线Fig.10 Static pressure of S2 with different pitchs  
图12不同转速 $50 \%$ 喉部高度S1流面相对马赫数  
图13不同转速 $50 \%$ 喉部高度S1流面熵和流线分布

Fig.12Relative Mach number contour of S1 at $50 \%$ throat height with

Fig.13 Entropy and   
streamlines of S1 at $50 \%$   
throat height with   
different speed

![](images/34739ad09432b480e5f30374b9068eb78fa665c845673acb19c00d63f2ddfafd.jpg)  
图11不同节距S2流面熵和流线分布图Fig.11 Entropy and streamlines of S2 with differentpitchs  
图15绝热效率随相对转速的变化Fig.15 Efficiency withdifferent speed

![](images/1ee546a1e685ea7e133922764dafa1b9ab2b7e0a7a30311f2d6c8ab3791dd54a.jpg)  
图14膨胀比随相对转 速的变化 Fig.14 Expansion ratio with different speed

随转速增加，吸力面壁面附面层逐渐减薄(图13)，主要因为沿节距方向压差减小，气流向吸力面的迁移运动减弱。而膨胀流道出口斜激波强度降低，这样由出口激波导致的附面层分离、回流以及激波附面层相互作用所产生的损失降低，膨胀器效率上升(图15所示)。为了获得膨胀器三维流道良好的综合性能，需依实际情况选择膨胀比和效率。

# 3.3进口总压对膨胀器三维流道性能的影响

图16为不同进口总压条件下 $50 \%$ 喉部高度S1流面相对马赫数等值线分布图，可以看出随着进口总压的增加，斜激波逐渐向出口迁移，激波强度减弱，由激波引起的附面层分离损失降低，故膨胀器的效率上升(图17)。这主要是因为随着进口总压的增加，气流做功能力增强，在进口速度不变条件下，来流膨胀加速更为完善，出口速度增加，故膨胀比上升(图18)。

![](images/b9bf6ea071c9b39df8d267d46123ba50678bcca7c6e4da6219a194d42640bc87.jpg)  
图16不同进口总压 $50 \%$ 喉部高度S1流面相对马赫数等值线

Fig.16 Relative Mach number contour of S1 at $50 \%$ throat height with different inlet total pressure

![](images/b5493928f3d8b6ec4ccb689117ce86652236bcc937dd04ab802a690e7414e2e0.jpg)  
图17绝热效率随进口总压的变化  
Fig.17Adiabatic efficiency with different inlet total pressure

![](images/d44d72388f1572034158b8734fb2e064ffca53b4305774c781bc8fe7eab5e7b6.jpg)  
图18膨胀比随进口总压的变化  
Fig.18 Expansion ratio withdifferent inlet total pressure

# 4结论

1）本文所设计超声速膨胀器实现了  
膨胀加速功能，膨胀流道入口来流达到声  
速，膨胀波的出现导致了压力沿节距方向  
的非均匀分布，进而影响流道内速度分布。2）膨胀流道出口附面层分离、回流、  
低能流体与主流掺混、激波以及激波与附  
面层的相互作用是能量损失的主要来源。3）随转速增加，膨胀器膨胀能力相应  
增强，膨胀比和效率增加；随进口总压增  
加，斜激波逐渐向出口迁移，激波强度减

弱，由激波引起的附面层分离损失降低，效率提高。气流做功能力增强，在进口速度不变条件下，来流膨胀加速更为完善，膨胀比增加。

# 参考文献：

[1] Harrison S. The Influence of Blade Lean on Turbine Losses[R]. ASME Paper 90-GT-55, 1990.   
[2] WANG Zhongqi, XU Wenyuan, HAN Wanjin. AnExperimentalInvestigationintothe Influence of the Blade Leaning onthe Secondary Flow in an Annular Cascades with Small Diameter-Length Ratio[R].ASME Paper 85-WAM-1485, 1985.   
[3]岳国强，韩万金．掠叶片对涡轮叶栅气动性 能的影响[J]·推进技术,2004,25(6):512-516· YUE Guoqiang, HAN Wanjin. Effects of Swept Blade on the Aerodynamic Performance of Turbine Cascade[J]. Journal of Propulsion Technology,2004, 25(6):512-516.   
[4] Razinsky E H,Kuziak W R,Jr. Aero thermodynamic Performance of a Variable Nozzle Power Turbine Stage for an Automotive Gas Turbine[J]. ASME Journal of Engineering for Power,1997,99(2):587-592·   
[5] Haldeman C W, Dunn M G, Abhari R S,et al. Experimental and Computational Investigation of the Time-Resolved Pressure Loading on a Vaneless Counter-Rotating Turbine [R]. ASME 2000- GT -0445,2000.   
[6] Lawlor S P, Steele R C, Baldwin P. Advanced Supersonic Component Engine for Military Applications[R]. ASME Paper GT2007-27336, 2007.   
[7] Spaid F W, Keener E R. Experimental Results fora HypersonicNozzle/AfterbodyFlow Field[R]. AIAA 92-3915, 1992.   
[8] YANG Ling， ZHONG Jingjun,HAN Ji'ang. Numerical Research of the Ram-rotor with Different Geometric Parameters[R]. ASME Paper GT2011-46051,2011.   
[9] Dorney D J, Griffin L W, Huber F W. A Study of the Effects of Tip Clearance in a Supersonic Turbine [J].ASME 2000-GT-447,2000.