# 可乐易拉罐柱壳在轴-侧-扭-内压联合作用下的屈曲地貌The buckling landscape of coke can cylindrical shell under the combined action ofaxial compression-torsion-lateral poking-internal pressure

宋广凯，孙博华†1 1西安建筑科技大学土木工程学院和力学技术研究院   
School of Civil Engineering E Institute of Mechanics and Technology,   
Xi'anUniversityofArchitecture and Technology，Xi'an 71oo55，China http://imt.xauat.edu.cn +通信作者：email:sunbohua@xauat.edu.cn (Dated: August 25,2020)

本文利用非线性有限元分析程序ABAQUS 研究了柱壳曲屈问题，并应用到了可乐易拉罐柱壳的曲屈分析。首先从数值模拟上验证了Virot 等学者的可乐易拉罐曲屈实验结果，然后为了获得曲屈的一些普适结果，进一步考察了柱壳的曲屈表现。对柱壳结构在不同荷载组合、不同几何参数作用下进行了细致的分析。为了讨论的直观，本文绘制了柱壳结构在受到侧压-轴压荷载作用下外力-曲屈荷载-位移三维曲屈地貌图(称为landscape)。结果表明：在侧压-轴压-扭转荷载作用下试件力-位移曲线出现了“clif”(断崖)现象；扭转荷载的施加不利于试件整体稳定性，并造成了试件对初始缺陷的敏感性；对于受到轴压-扭转试件，本文定义承载力为零的平面为“sea level”（海平面)来区分试件破坏模式；通过对不同边界条件的试件进行分析，发现试件两端固接可以有效地整加结构的承载能力，提高稳定性。对柱壳结构内部充气可以大幅度提升结构的承载能力和稳定性，减小对初始缺陷的敏感度。

The aim of this work is to investigate the buckling of the cylindrical shells based on the non-linear finite element analysis program ABAQUS and applied to the buckling analysis of cola cans.Buckling analysis of soda cans by means of comparing the numerical results with experimental data[34l.In order to obtain some qualitative results of buckling,the buckling behaviour of the cylindrical shells will be investigated.In this article,we focus on the effect of different load combinations and different geometric parameters of the cylindrical shels.The straightforward,simple analysis of the buckling of the cylindrical shells under the axially compressed-lateral perturbation load is presented. We show that the three-dimensional curve of external force-buckling load-displacement called landscape. The numerical results indicate that: the phenomenon of "cliff appears in the force-displacement curve of specimens under the action of lateral pressure-axially compressed-torsional load;It wil be appreciated that the torsional is not conducive to the stability of the specimen and makes the specimen sensitive to the initial imperfections；For specimen under axially compressed-torsional load,in this paper,the plane with zero bearing capacity is defined as "sea level" to distinguish failure modes of specimens; The results of specimens with different boundary conditions shows that the bearing capacity of the cylindrical shels can be improved with fixed boundaries.The internal pressure can greatly improve the bearing capacity and stability of the structure and reduce the imperfection-sensitivity.

Keywords:柱壳，曲屈，曲屈地貌，可乐易拉罐，有限元cylindrical shells,buckling,landscape,cola cans,numerical simulation

# I．前言

结构在一定荷载和边界条件下的失稳现象称为结构曲屈或者稳定问题。自从Euler（1744）[1，2，28自研究细弹性压杆（Euler称之为Elastica）的稳定问题以来，结构稳定性问题已经成为结构设计必须考虑的问题。人们在工程实际中发现细薄长结构在失去稳定时，其受力强度通常远低于材料的屈服应力，这种现象一开始比较困扰人们的传统思维，既以材料强度为设计原则的思维。后来人们注意到，在同样荷载条件下，不同的结构几何构形的稳定性可能完全不同，特别是对于细薄长的结构，结构稳定性问题尤其突出[6，13，14，16,17，23-28,41,42]。

随着新材料的开发，高强度强韧性超材料逐渐开始应用，从而可以使原来必须使用较大尺寸材料构造的结构，可以使用超材料在达到同样的承载能力的情况下构成结构的构件尺寸越来越细薄，从而使得结构稳定性问题的研究越来越重要。反过来，结构力学的研究也启发和促进了超材料胞元的设计，就是说按结构力学角度设计具有需要力学性能的胞元来获得材料整体性能的提升，使得在基体材料性能不变的情况下，通过设计微结构达到特别的整体材料性能。所以超材料也称为具有微结构的材料[45-50]。从这个意义上说，结构力学的研究促进了高性能材料的设计。

对于结构稳定性的认识，从早期的理论预测与实验相差甚远[3-7,39]，让人们开始注意稳定性理论研究的重要性。为此，人们提出了不同的稳定性理论来试探解释理论预测与实验的差距，比如Karman-Tsien(卡门-钱学森)非线性大挠度理论[3-5，7]，Stein的非线性前屈曲一致理论[39]和Koiter的考虑初始缺陷的后屈曲理论[6]。但遗憾的是，尽管人们已经绞尽脑汁考虑各种因素，目前的理论预测与实际仍然存在一定的差距。导致在工程实际中，还不敢完全以稳定性理论的预测来进行结构设计，不得不采用比较大的压溃系数，既KnockdownFactor，比如美国的国家航空航天局(NASA)就有专门研究结构Knockdown Factor 的研究计划[10，43，44]。对于柱壳的曲屈问题，1965年NASA根据实验拟合出来的KnockdownFactor经验公式是

$$
\kappa = 1 - 0 . 9 0 1 ( 1 - e ^ { - \frac { 1 } { 1 6 } \sqrt { \frac { R } { t } } } ) ,
$$

其中 $R / t$ 是柱壳半径与厚度的比。

![](images/31062d8244f0b025a62b55b95b4dad9d518b6661059a805c931671f432412fdf.jpg)  
图1：1965年美国NASA[10发布的压溃系数KnockdownFac-$\kappa = 1 - 0 . 9 0 1 ( 1 - e ^ { - \frac { 1 } { 1 6 } \sqrt { \frac { R } { t } } } )$

这个公式说明典型的结构一般在曲屈预测值的20$5 0 \%$ 就发生了曲屈，较低的情况只有预测的 $2 0 \%$ ，所以[44指出：NASA提出的屈曲荷载折减系数来计算含初始缺陷的柱壳结构的屈曲荷载偏保守。经过了半个世纪的发展，利用精巧实验和大量计算分析，虽然曲屈荷载有些改进，但目前仍然还采用这个经验公式[11]。可以看出任何使曲屈能力的提高的方法都将具有重大的工程实际意义。

柱壳结构由于其质量轻、承载力高，多用于航天、建筑等领域，所以获得特别多的研究[6,8，9,12-16，16-22,29,30，36-41，51。在结构曲屈理论发展历史上，一个里程碑式的进展式，Koiter[6揭示了结构的初始几何缺陷对于结构曲屈有非常大的影响，或者说结构对于初始缺陷是十分敏感的，结构表面微小的凹陷便会导致结构承载力大幅度下降，Koiter[6]以此创建了结构稳定的后曲屈理论。为了验证初始几何缺陷对于曲屈的影响，人们假设了不同形式的几何缺陷，甚至提出了随机缺陷的问题。

由于柱壳结构的应用广泛，对其曲屈稳定性的研究方兴未哎。V.Krasovsky 等31]采用实验与有限元相结合的方式，提出了采用侧向扰动来创建初始缺陷的方法;WaddyT.Haynie等[32]采用实验与有限元相结合的方法计算了采用侧向力创建初始缺陷时结构屈曲荷载的最低限值[42]；J.Michael33]等在NASA 试验的基础上提出了柱壳在受到轴向压力的情况下，在侧向使用探针对该结构施加侧向位移荷载的实验方法，并且用此方法研究了柱壳结构的冲击感度。特别是在2017年，Viroy 等学者[34等对于可乐易拉罐柱壳在轴-侧压作用下的曲屈问题进行了细致的实验研究，试图从中寻找普适的曲屈规律。该文献通过对不同品牌的空易拉罐进行研究，利用曲屈地貌(landscape)来直观的研究屈曲，指出多维复杂的壳体稳定可以简化为低维描述。Virot 等学者.[34]从有限的实验数据，获得的曲屈地貌有着重要的意义。但是文献中的荷载情况只有一种轴-侧压，没有考虑扭转和内压的联合作用。为了进一步验证Virot 等学者.[34从实验总结出来的曲屈规律，我们认为有必要研究其它荷载组合下柱壳的稳定性。

具体讲，在本文中，在Virot等学者工作的基础上[34，我们不是做实验而是试图从数值模拟的角度来研究这个问题。首先使用有限元数值计算验证了Virotetal.34的轴-侧压曲屈结果。完成验证Virot 等学者[34]之后，我们考虑了更多的荷载组合，进一步考察柱壳在其他荷载组合作用下的曲屈行为。通过细致计算，获得了侧压、轴压、扭转和内压等荷载不同组合下柱壳的曲屈地貌。依据我们提出的新描述，对于得到的曲屈地貌，进行了细致的稳定性分析。除了分析参数对于曲屈的影响，还提出了改善提高曲屈能力的思路。

# II．曲屈地貌(LANDSCAPE)的几何示意图

为了形象的表达我们获得曲屈地貌的新信息，本文除了继承Virot etal.[34] 提出的“ridge”，和"valley"之外，还把其"lake"修改成更贴切的"basin"，同时还引进了“cliff”、"sea level"和"hill"等新概念，以便更好的刻画曲屈地貌(见图2)。

![](images/e3f045bcc749d83db480e60b5d491029667da5813aca6d1d49324d0cb3e673b0.jpg)  
图2：曲屈地貌(Buckling landscape)的示意图，其中“ridge(背脊)”、"valley（山谷)"、"lake（湖面）"、"basin（盆地）"、“cliff(断崖)”、"sea level(海平面)"和"hill(丘陵)"

# III．有限元模拟验证了VIROT[34]的试验结果

在这一节，我们的目的是从数值的角度验证Virot等[34的实验，以便核查我们的有限元模型的可行性。为此，我们利用ABAQUS 有限元软件建立了该试件的有限元模型。为了完全还原实验，本文对文献实验中易拉罐进行了尺寸测量，采用测量的几何尺寸来进行有限元建模，具体的几何参数见图3。

![](images/c8e54a838c39bd114db363f3c81517cefb727cc13057428dadf8c715c29b69f2.jpg)  
图3：可乐模型几何尺寸

![](images/6247b16d5523a26eedece83379d0b3e24e163d7f383007967af12eb76de73079.jpg)  
图5：试验与有限元曲线对比，其中exp 表示Virot et al.[34]的实验结果，FE代表我们的计算结果。可乐易拉罐曲屈荷载是exp4=675N

由文献[52-53可知，易拉罐采用3104铝合金，其弹性模量为75000N/mm²，泊松比为0.3，屈服应力为294.3Mpa。在有限元中采用离散刚体模拟试验中的上下夹板与侧向探针。定义易拉罐顶与上夹板、易拉罐底部与下夹板、刚性球与罐体互相接触塑性时，其法向为硬接触，切向采用罚函数法，摩擦系数取0.3。易拉罐采用ABAQUS软件的壳体S4R单元。上述试件的有限元模型如图4所示：

在弹性阶段，实验曲线与有限曲线较为接近。这表明有限元能够较好地模拟试件初始刚度；随着荷载位移的增加，试件变形逐渐加大。当试件承载力到达最低值时，有限元模型的位移要大于实验模型。这是因为有限元中采用的双折线本构模型相比于实际试件材料本构模型有着较大塑性屈服平台，这便导致有限元的塑性开展要大于实验。另外在实验中存在不可避免的误差和随机的初始缺陷，这样就会使得实验中试件承载力退化较快。实验中试件承载力最小时的位移荷载要略低于有限元，但有限元模型的屈曲承载力大约在675N，这与实验相似。

![](images/04d07168ea5fc24976c27743b8c534a1c0f9c0b851c8cff98f1243204dd9d649.jpg)  
图4：可乐有限元模型

总体来说，获得的可乐易拉罐轴-侧压联合作用下屈曲路径地貌（landscape）与Virot等34的使得一致，我们的非线性数值结果支持了[34]的实验结果。下面，我们进一步研究其他几种荷载组合的曲屈地貌。

# IV．可乐易拉罐模型基本参数和几种荷载边界情况

由于在进行有限元模拟时先施加轴向荷载再施加侧向荷载，当施加的轴力为1084N时，试件发生了较大的整体压缩变形，无法继续进行侧向荷载的施加。故只对轴向压为136N,348N,467N,675N,683N,859N的实验试件进行有限元数值模拟。

利用上述建立的有限元模型对实验中6个试件进行非线性数值分析，得到易拉罐在不同轴压力作用下侧向力-位移曲线与试验得到侧向力-位移曲线的对比如图5所示。由图5可以看出：有限元模拟的曲线与实验曲线整体趋势较为接近。

根据Virot等[34]试验发现，易拉罐发生的屈曲变形主要集中在罐体。因此在有限元参数分析时采用简化的分析方式，将易拉罐简化为柱壳结构来进一步进行分析。为了研究不同荷载组合、不同边界条件、不同径高比 $( R / L )$ 、径厚比 $( R / t )$ 、罐体内部充压等对曲屈地貌(landscape)现象的影响。

本文设计4个不同径高比 $( R / L )$ 、3个不同径厚比 $( R / t )$ 、3个不同荷载组合、1个不同边界条件、2 个罐体内部充气的有限元模型。对于易拉罐边界条件本文定义：在加载前试件与上下加载板无约束时的边界条件为自由，试件上下面与加载板自由度完全相同时视为试件固接。在有限元中为了充分模拟试件内部充气，采用等价的方式将罐体内部充气等价成在罐体内部施加压强，压强的数值为一个标准大气压。具体模型的参数如表I所示.

表I：不同试件的几何参数  

<html><body><table><tr><td>名称</td><td>高度 (mm)</td><td>半径) (mm)</td><td>壁厚 (mm)</td><td>径高比 (R/L)</td><td>径厚比 (R/t)</td><td>荷载组合</td><td>边界条件</td><td>罐内是否充气</td></tr><tr><td>Specimen-1</td><td>100</td><td>30</td><td>0.1</td><td>0.3</td><td>300</td><td>轴压-侧压</td><td>自由</td><td>香</td></tr><tr><td>Specimen-2</td><td>110</td><td>30</td><td>0.1</td><td>0.27</td><td>300</td><td>轴压-侧压</td><td>自由</td><td>香</td></tr><tr><td>Specimen-3</td><td>120</td><td>30</td><td>0.1</td><td>0.25</td><td>300</td><td>轴压-侧压</td><td>自由</td><td>香</td></tr><tr><td>Specimen-4</td><td>130</td><td>30</td><td>0.1</td><td>0.23</td><td>300</td><td>轴压-侧压</td><td>自由</td><td>香</td></tr><tr><td>Specimen-5</td><td>90</td><td>20</td><td>0.1</td><td>0.22</td><td>200</td><td>轴压-侧压</td><td>自由</td><td>香</td></tr><tr><td>Specimen-6</td><td>90</td><td>22</td><td>0.1</td><td>0.24</td><td>200</td><td>轴压-侧压</td><td>自由</td><td>香</td></tr><tr><td>Specimen-7</td><td>90</td><td>24</td><td>0.1</td><td>0.27</td><td>220</td><td>轴压-侧压</td><td>自由</td><td>香</td></tr><tr><td>Specimen-8</td><td>90</td><td>20</td><td>0.1</td><td>0.22</td><td>200</td><td>轴压-侧压</td><td>固接</td><td>香</td></tr><tr><td>Specimen-9</td><td>90</td><td>20</td><td>0.1</td><td>0.22</td><td>200</td><td>轴压-侧压-扭转</td><td>固接</td><td>香</td></tr><tr><td>Specimen-10</td><td>90</td><td>20</td><td>0.1</td><td>0.22</td><td>200</td><td>侧压-扭转</td><td>固接</td><td>香</td></tr><tr><td>Specimen-11</td><td>90</td><td>20</td><td>0.1</td><td>0.22</td><td>200</td><td>轴压-扭转</td><td>固接</td><td>香</td></tr><tr><td>Specimen-12</td><td>90</td><td>20</td><td>0.1</td><td>0.22</td><td>200</td><td>轴压-侧压</td><td>固接</td><td>是</td></tr><tr><td>Specimen-13</td><td>90</td><td>20</td><td>0.1</td><td>0.22</td><td>200</td><td>轴压-扭转</td><td>固接</td><td>是</td></tr></table></body></html>

# V.轴-侧压作用下对可乐易拉罐曲屈影响

位移-荷载曲线以及（外力-曲屈荷载-位移）三维地貌：Specimen-1～ Specimen-7均采用与试验中相同的加载方式：先在竖向施加轴向压力，轴向力的范围为1001200N，待试件稳定后施加侧向位移荷载，每步的荷载位移增量为0.16mm。每个试件的侧向位移、侧向力、竖向力、竖向位移分别记为： $D _ { p }$ 、 $F _ { p }$ 、 $F _ { A }$ 、 $D _ { A }$ 。各试件的侧向荷载-位移曲线如下图所示：

![](images/fdb0022336283660fe95525f6c4e2687526d18004881c01dabb5ca11e7550088.jpg)  
图8：Specimen3：曲屈路径的二维曲线和三维曲面地貌

![](images/470bd6f1be257a38e4ee3ea18fbb93cf7fa907ee54fdcb4050194fbcccea894d.jpg)  
图9：Specimen4：曲屈路径的二维曲线和三维曲面地貌

![](images/b16ef3997461a5c2adb36ae825f5be7a27e0e900b6b54b6187d8e5bf2847a258.jpg)  
图6：Specimen1：曲屈路径的二维曲线和三维曲面地貌

![](images/360ae97bdd8dc5b73bd559d7c82b0b9c6582e547b2da710c1e1d27129e4e13e1.jpg)  
图10：Specimen5：曲屈路径的二维曲线和三维曲面地貌

![](images/bacfef0a91c13df3a71e4def9cd38f713b46cf28a01b427f18b5e0a7962a4725.jpg)  
图7：Specimen2：曲屈路径的二维曲线和三维曲面地貌

![](images/e09dcb07a2da74ca58ef491bef7eed38dea9f5eb97e5c03161c10a5bdf644eb6.jpg)  
图11:Specimen6：曲屈路径的二维曲线和三维曲面地貌

![](images/6021d3705a167cbdd905d56562c7ab3d3cf4e5403512fd090e30d61019aeeec3.jpg)  
图12：Specimen7：曲屈路径的二维曲线和三维曲面地貌

由图可以看出7个模型均出现了文献中描述的landscape现象，各试件的“ridge”、“valley”现象差别不大。根据每个试件的力-位移曲线，把试件分为三个阶段：第一阶段为弹性阶段，此阶段侧向承载力随着侧向位移的增加而不断增大；第二阶段为屈曲阶段，试件侧向承载能力随着侧向位移的增加出现先增大后减小再增大的趋势；最后阶段称为“lake”阶段，在这阶段试件的侧向承载能力先增加后下降到零，继续加载会出现两种情况：一是随着位移荷载的逐渐增加，构件承载能力从零开始增加；另一种情况为承载力持续为零，不再增加。由图可以看出，Specimen-1-Specimen-4“lake”阶段的轴向力范围均为“950N1200N”，Specimen-5-Specimen-7“lake”轴向力范围为“1000N1200N”。通过对比发现：随着径高比(R/L)的不断减小，试件侧向承载力为零时的位移不断增大。举例来说：当N=1050N时，径高比(R/L)=0.3,0.27,0.25,0.23 时侧向承载力为零的位移分别为：1.5mm,1.8mm,1.9mm,2.1mm。并且通过三维曲线图也可以看出，试件的“lake”区域随着径高比(R/L)的不断减小而增大。分析Specimen-5-Specimen-7可知：随着径厚比(R/t）的不断增大，试件侧向承载力为零时的位移不断减小。当N=1050N时，径厚比 $\scriptstyle ( \mathrm { { R / t } } ) = 2 0 0 , 2 2 0 , 2 4 0$ ，侧向承载力为零的位移分别为：1.95mm， $1 . 3 5 \mathrm { m m }$ ， $1 . 3 \mathrm { m m }$ 。并且通过三维曲线图也可以看出，红色包围区域为试件的“lake”区域，并且包围区域随着径厚比 $\mathrm { ( R / t ) }$ 的不断增加，红色区域不断减小。

通过上述分析可知径厚比 $\mathrm { ( R / t ) }$ 、径高比(R/L)越大的结构有着较好的稳定性，试件对初始缺陷相对不敏感。

失稳模式讨论：各试件的破坏模式如图13-15所示：不同径高比、径厚比的试件有着相似的破坏模式。当轴向压力较小时，试件侧向受到刚性球挤压,接触点处柱壁发生内凹，试件整体稳定性较好。随着轴向压力的增加，接触点柱壁发生较大变形。当轴向压力达到一定值(950N左右)时，试件在受到刚性球的侧向挤压时，试件发生了局部屈曲，刚性球与柱壁接触位置发生较大内凹变形。并且侧向荷载到达一定值时，侧向荷载位移不再增加但接触点处的变形继续增大，加载点与柱壁发生分离（“lake”现象开始发生）。当柱壁内凹到一定位移时，试件达到新的平衡。继续加载小球与柱壁发生第二次接触（此时“lake”现象结束），试件局部变形继续加大，但并未发生整体屈曲。图15是构件在遭受较大轴向压力时发生的破坏模式。由于较大的轴向力作用，试件在很早便出现了加载球体与柱壁的分离。并且该点处柱体表面的局部屈曲逐渐变大，并且向柱顶、柱脚扩散，试件发生轴向压缩最终导致整个构件发生整体失稳。

![](images/c2807adc65b3d9da461a46395c085f78dee4b05f73a7d4a2c65a30b8ad5df4b9.jpg)  
图13：局部屈曲（左），球体与柱壁分离（右）

1 I

![](images/29af59a83c3606743aaeeed907b39a85561e0b125f704e3d8741a955d908332d.jpg)  
图14：球体与柱壁第二次接触（左）轴力较大时小球与柱壁分离 (右)  
图15：局部屈曲扩散（左）整体压缩屈曲（右)

# VI．轴-侧压-扭转作用下对可乐易拉罐曲屈影响

位移-荷载曲线以及（外力-曲屈荷载-位移）三维地貌：本文在轴-侧压作用下试件的基础上考虑扭转作用，建立了在轴-侧压-扭转作用下有限元模型。为了施加扭转荷载，在有限元中分别将试件两端与上下刚性夹板进行绑定，这就使得试件的边界条件由自由端转变成固结。为了保证单一变量原则，在Specimen-5的基础上改变边界条件，建立Specimen-8来与Specimen9进行对比分析，研究该情况下柱壳结构的landscape现象。Specimen-9几何尺寸与Specimen-8 相同，施加扭转荷载为5000N·mm，记为 $M _ { A }$ 。得到侧向力-位移对比曲线如下图所示：

![](images/49906566dc3e379062b4f74a134c97cc18591ebc7e9dcb005fe85bce8e7b8179.jpg)  
图16：Specimen8：曲屈路径的二维曲线，以及三维曲面地貌

![](images/03892d5e28b7c5589086e175b441991b9188d76d4d0e80091ddd4124821a3cca.jpg)  
图17:Specimen9：曲屈路径的二维曲线，以及三维曲面地貌

由曲线图我们可以看出，在轴压-侧压-扭转荷载作用下，试件也出现了landscape现象。相比未施加扭转的试件曲线，在轴压-侧压-扭转联合作用下的柱壳结构出现了新现象，本文把这种曲线现象叫做“cliff”，“cliff”下方承载力为零的空白区域定义为“sea”，并且本文将“lake”区域重新定义为“basin”。“Cliff”现象出现的原因为：在侧向加载球体加载到一定位移时柱壁发生跳跃，加载点与柱壁发生分离，试件侧向承载力变为零。这一现象形成了曲线中“basin”。当荷载的继续增加小球与柱壁再次接触，试件侧向承载力从零开始增加。但对于轴压-侧压-扭转联合作用下的试件来说，试件到达“basin”位移之后，由于扭转弯矩的存在导致在加载后期试件发生了扭转破坏，小球与柱壁发生了第二次分离，试件的承载力瞬间下降到了零便形成了曲线中的“cliff”现象。对比Specimen-8发现，Specimen9“valley”结束早，“ridge”相对弯曲，其主要原因还是施加了扭转荷载导致试件变形加大，破坏时间提前。并且分析发现，在有限元中施加扭转荷载对试件强度影响不大，但降低了试件的稳定性。并且扭转荷载的增加使得试件进入“basin”时间提前，在施加位移荷载后期试件发生了整体失稳，承载力瞬间下降到零。

对比Specimen-8与Specimen-5可知：当试件两端边界条件由自由变为固接时，试件侧向力有了较大的提升，试件形成“basin”时间推迟、形成“basin”面积小，试件的稳定性和承载能力均有了较大的提升。两端固接，一定程度上削弱了结构对初始缺陷的敏感性。

失稳模式讨论：由于模拟试件较多，选取具有代表性试件来进行对比分析。当N=1200N，试件的破坏模式对比图见图-。由图我们可以看出，Specimen-8的最大应力云图关于轴线对称，最大应力以加载点为中心向四周发散；相比于Specimen-8，Specimen-9最大应力云图关于轴线反对称，整体呈现“N”字形。这表明增加扭转荷载在一定程度上改变了试件的受力状态，进而改变了试件的破坏形态。Specimen-9在N=1200N时发生了小球与柱壁的两次分离，第一次分离形成曲线中“basin”现象，第二次分离形成“cliff”现象。而Specimen-8在加载全程并未发生加载球体与柱壁分离。这表明施加扭转荷载一定程度上削弱了试件的稳定性。在加载后期Specimen-9发生了整体扭转失稳，而Specimen-8只发生局部屈曲，这一现象也证明了扭转荷载的施加对结构的稳定性有不利的影响。

![](images/3d48129ae9174cd1f9ba89fee069a78f8c4e0ea25ff1024c15718f15145e6d39.jpg)  
图18:当 $\begin{array} { r l r } { M _ { A } } & { { } = } & { 1 2 0 0 N } \end{array}$ ·mm时，Specimen-8（左）与Specimen-9（右）的应力分布

![](images/d20057f15c96986ac020c7ec4501bb969b71d8c859d5e9f254a3e0880bd34d62.jpg)  
图19:在加载中期Specimen-8（左）小球与柱壁接 触，Specimen-9（右）发生小球与柱壁发生分离

![](images/1621d2c59e7c6536bc4d79917087a28be1dc9c37967ccf7e0a52000200a26e1e.jpg)  
图20:加载后期Specimen-8发生局部屈曲（左）Specimen-9 （右）出现整体扭转破坏

# VII．侧压-扭转作用下对可乐易拉罐曲屈影响

位移-荷载曲线以及（外力-曲屈荷载-位移）三维地貌：图是Specimen-10的侧向力-位移曲线，由曲线可以看出，当扭转荷载范围为： $1 0 0 0 N \cdot m m \sim 7 5 0 0 N \cdot m m$ 时，试件的承载力随着位移荷载的增加而逐渐增加。当扭转荷载大于7500N·mm时，试件的承载能力呈现先增加后快速下降的趋势。三维曲线图展示了Specimen-10在不同扭转荷载作用下，出现上文提起的“cliff”、“ridge”、“sea”现象。对比Specimen-9，Specimen-10并未出现“lake”现象，“valley”现象也不太明显。这是因为试件在侧向加载时，加载点处柱壁由于刚性小球的作用发生内凹，但由于竖向无荷载作用，柱壁内凹处并不会脱离小球继续变形，反而由于扭转荷载的作用内凹处发生扭转变形，继续加载扭转变形范围继续扩大最终导致试件发生整体扭转失稳。在试件发生整体失稳之前，刚性加载小球一直与柱壁接触，直到试件发生整体失稳时才分离。

![](images/e24aecf8da94b2c30e2543ef77d3d6867335c89e7c3af995128f131a7911f41a.jpg)  
图23：当扭转荷载为7000N $\cdot$ mm时，Specimen-10的应力分布图

![](images/8aabeefcf90656af99e76823746a1157df65749811829436f0023e2669bd629f.jpg)  
图21：Specimen10：曲屈路径的二维曲线，以及三维曲面地貌

![](images/75a2cd62e821f07d686f0e29e06bee405b65dfed0a48017c97d58af915277de9.jpg)  
图24：扭转荷载为 $8 0 0 0 \mathrm { N } \cdot \mathrm { m m }$ （左）、 $9 5 0 0 \mathrm { N } \cdot \mathrm { m m }$ （右）时，Specimen-10的整体扭转破坏

失稳模式讨论：Specimen-10的破坏模式图如下所示：由图可以看出当扭转荷载比较小时，试件只在接触点处发生轻微变形。试件加载点处最大应力关于轴线呈正对称状。随着扭矩荷载的增加，试件柱壁内凹变形逐渐加大，最大应力受扭转荷载的影响逐渐由正对称转化为反对称。当扭转荷载增加到8000N·mm时，试件由加载点处弯曲变形转变为扭转屈曲，并且随着扭转荷载的继续增加，扭转变形加大，最终导致试件发生整体扭转失稳。

# VIII．轴压-扭转作用下对可乐易拉罐曲屈影响

由Specimen-10力-位移曲线、破坏模式图可以总结出：侧压-扭转荷载作用下的试件有着不同的landscape现象。相比于Specimen-9，缺少了轴向压力的试件承载能力有了提高，但扭转荷载的存在改变了试件最终破坏模式，也改变了landscape现象。

位移-荷载曲线以及（外力-曲屈荷载-位移）三维地貌：为了研究在轴压-扭转作用下柱壳结构的屈曲性能，建立Specimen-11。为了方便施加扭转荷载，试件顶端与底端分别于上下夹板固接。首先施加扭转荷载，待试件稳定后在试件轴线方向施加位移荷载，具体的轴向力-位移曲线如下图所示：

![](images/e3714433d94f06cd9d07c567b4c17b850b062afbb7b0854c54321acce43b1732.jpg)  
图22：当扭转荷载为1000N $\cdot$ mm时，Specimen-10的应力分布图

![](images/16cd98bbcc696cae0ff9c1d7dcecc97030afe60f0fa8b45843e75aee01438208.jpg)  
图25：Specimen11：曲屈路径的二维曲线，以及三维曲面地貌

由曲线图可以看出，各试件曲线呈现先增大后减小的趋势，试件最大承载能力基本相同。随着位移荷载的增加，各个试件曲线展现出了不同的变化趋势。当施加扭转荷载为 $3 0 0 0 N \cdot m m$ ,试件轴向承载力出现负值，并且随着扭转荷载的增加，轴向承载力出现负值的时刻不断提前，数值不断增大。发生这种现象主要原因是：当施加扭矩荷载范围为： $1 0 0 0 N \cdot m m \sim 3 0 0 0 N \cdot m m$ ，此时试件轴向承载能力基本为正，扭转荷载并不起主导作用，试件变形多为轴向压缩变形；随着扭转荷载的不断增加，相对于轴向位移荷载，扭转荷载逐渐起主导作用。在加载初期，试件由于扭转荷载的作用柱体出现多个斜45度方向上的褶皱，前后褶皱呈现交叉状；未出现扭转变形时，试件主要依靠柱壁承受竖向荷载；当试件出现扭转褶皱时，试件由以前柱壁承载逐渐变为交叉褶皱承载加上扭转荷载的作用，此时试件轴向承载力出现反向，承载力大小有了一定的提升。根据与此，按照海岸带中定义方式，做出承载力为零时的平面，并将该平面定义为“sea level”。加载初期承载力上升段定义为“hill”，承载力快速下降段也定义成“cliff”。经分析，试件峰值荷载相似，这也表明“hill”高度相同；试件在“海平面”上部的曲线，轴向承载力为正，轴向位移荷载起主导作用；试件在““sea level”下部的曲线，轴向承载力为负，扭转荷载起主导作用。

失稳模式讨论：下图为Specimen-11在不同扭转荷载作用下的破坏模式图，由图可以看出：当扭转荷载小于 $3 0 0 0 N \cdot m m$ 时，试件发生轴向压缩屈曲。这是因为扭转荷载较小，并未影响试件的轴向变形。当扭转荷载大于 $4 0 0 0 N \cdot m m$ 时，试件由轴向压缩屈曲转变为整体扭转屈曲，并且随着扭转荷载的增加试件变形逐渐加大。试件破坏模式的改变，是因为扭转荷载较大，影响了试件最后的破坏模式。可以判断，当试件曲线完全在“sealevel”之上试件多发生轴向压缩屈曲，在“sealevel”之下试件多为整体扭转失稳。

![](images/def6cfb0c668c4462eb0fc44201ede94b42d5d163322aa079f6261b68d2e59ac.jpg)  
图26：当扭转荷载为 $_ { 1 0 0 0 \mathrm { N } } \cdot _ { \mathrm { m m } }$ （左）、 ${ 2 0 0 0 } \mathrm { { N } } \cdot { \mathrm { { m m } } }$ (右）时，Specimen-11的破坏模式图

![](images/4d76cc94545c502a665355c0a3b80f7cf322f0822592f413a0d8f1c4eb82dda9.jpg)  
图27：当扭转荷载为 $\mathrm { 3 0 0 0 N \cdot \ m m }$ （左）、 $4 0 0 0 \mathrm { N } \cdot \mathrm { m m }$ （右）时，Specimen-11的破坏模式图

![](images/5f83eafa301809f62f6e8d5941dd34e1416af5631c60b79f9b927f29f3cca366.jpg)  
图28：当扭转荷载为 $\mathrm { 5 0 0 0 N \cdot m m }$ （）、 $_ { 6 0 0 0 \mathrm { N } } \cdot _ { \mathrm { m m } }$ （右）时，Specimen-11的破坏模式图

# IX．罐体内部充气对可乐易拉罐曲屈影响

位移-荷载曲线以及（外力-曲屈荷载-位移）三维地貌：为了研究易拉罐等柱壳结构内部充气时“landscape”现象，本文在原有模型的基础上设计了Specimen-12、Specimen-13两个模型。下图为该试件的力-位移曲线,由图可以看出:Specimen-12在轴压-侧压-内压作用下的力-荷载位移曲线呈现单调递增趋势；试件并未出现较为明显的landscape现象。将Specimen-12、Specimen-8曲线中最大承载力取出绘制最大承载力-轴向荷载曲线。由该曲线可以看出，两个试件承载力退化趋势相似，但Specimen-12的最大承载力要远远大于Specimen-8。取平均值计算，Specimen-12最大荷载平均值为68.72N，Specimen-8最大荷载平均值为28.25N。并且当轴向荷载为1300N时，Specimen-8已经出现“lake”现象，试件发生了局部屈曲；然而Specimen-12曲线还是保持单调递增的趋势，试件处于弹性阶段。这表明，柱壳结构内部充气可以较大的提升试件的侧向承载能力，提高试件屈曲荷载，降低柱壳结构对初始缺陷的敏感性。

图30为Specimen-13的力-位移曲线图。由图可以看出各试件曲线展现出先增大后减小的趋势，试件最大承载能力相似。由于内部压强荷载的作用，试件曲线并未出现“sea level”现象。取Specimen-13、Specimen-11曲线中的承载力最小值做出对比图。由图31可以看出：Specimen-13的轴向承载能力要远远大于Specimen-11，并且随着扭转荷载的增加Specimen-11 的承载力退化程度要远远大于Specimen-13。当扭转荷载为4000N·mm时，Specimen-11的最小轴向承载能力已经退化到负值，而Specimen-13最小承载力一直为正。通过上述分析可知：为受到轴压-扭转荷载作用的试件施加内部压强，可以较大程度的提升柱壳结构的承载能力，减缓承载力退化。

![](images/d611fd29bfe70d330ecb18c42ed9f7e65b20c4df2115406316716a708a8e0951.jpg)  
图29：Specimen12：曲屈路径的二维曲线，以及三维曲面地貌

![](images/9e1b3501571a3771038a46733bf0e14525dd1c5fef692ce4afc47f61de11348f.jpg)  
图30：Specimen13：曲屈路径的二维曲线，以及三维曲面地貌

# X．结论

![](images/5f2c1d3535d6ab2b1c89f865214507e2bd7e389a1d64a74eea74a5967a855432.jpg)  
图31：最大承载力对比（左），最小承载力对比（右）

失稳模式讨论：Specimen-12、Specimen-13的破坏模式图如下所示。Specimen-12并未发生屈曲破坏。相比于Specimen-8，施加了内部压强提高了柱壳结构的稳定性，增大了试件侧向扰动的抵抗能力。Specimen-13试件在不同扭转荷载作用下发生了局部屈曲，屈曲形式随着扭转荷载的增加逐渐变为局部扭转屈曲,试件整体稳定性好。对比Specimen-11可以看出，在扭转荷载范围为：1000N·mm～ 6000N·mm时，Specimen13并未发生整体扭转失稳。当扭转荷载为6000N·mm时，Specimen-13仅在距上加载板30mm处发生局部屈曲；而Specimen-11发生类似破坏模式的扭转荷载为 $2 0 0 0 N \cdot m m$ 。这表明，柱壳结构内部充气可以提升结构抗扭承载能力，推迟局部失稳的发生，一定程度上提高了柱壳结构的稳定性。

![](images/dbb00606b1f058acaa83a064e9380324a37d1c641cea5d3181f132f5c1c12e87.jpg)  
图32:Specimen-12：左图N $\scriptstyle \mathsf { I } = 1 0 0 \mathrm { N }$ ，右图N $\mathbf { \bar { \rho } } = \mathbf { \rho }$ 1300N

本文采用有限元非线性数值模拟的方法，首先从数值计算的角度验证和支持了Virot等学者[34]的实验以及曲屈地貌的趋势。然后进一步对不同荷载组合的柱壳的曲屈进行了细致的数值模拟研究，获得了柱壳的曲屈地貌(landscape），并在此基础上，细致讨论分析了不同荷载组合、不同边界条件、不同径高比(R/L)、径厚比(R/t）对柱壳结构曲屈地貌(landscape）的影响。从目前的数值分析并利用曲屈地貌解释，可以总结出以下几个结论：

（1）不同径高比、径厚比试件有着相似的屈曲地貌，试件“ridge”、“valley”趋势相差不大，“lake”变化较大。随着径高比、径厚比增大，试件形成“lake”的面积不断减小。这表明较大径高比、径厚比的试件有着较好的稳定性，对初始缺陷敏感度不高。

（2）试件在受到侧压-轴压-扭转时不仅展现出与侧压-轴压相似的现象，也出现了新的屈曲地貌。由于扭转荷载存在，试件力-位移曲线在加载后期出现了承载力骤降的现象。为了更加形象的描述这种力学性能，本文把这种现象定义为“clif”，下方承载力为零的空白处定义为“sea”，并且将“lake”改为“basin”。这些现象出现与定义在以前是没有过的。

（3）相比于侧压-轴压荷载作用下的试件，扭转荷载的存在不仅把试件的破坏模式由整体压缩屈曲转变成扭转屈曲，还降低了试件的稳定性，使得试件对初始缺陷更加敏感。

（4）受到侧压-扭转荷载作用的试件并未出现“basin”现象。这是因为没有竖向轴压力的作用，试件接触点处内凹变形并未得到进一步加强。并且由于扭转荷载的作用试件内凹形状发生改变，试件最终发生整体扭转失稳。

（5）本文对轴向-扭转荷载作用下的试件进行了有限元分析，发现扭转荷载的存在改变柱壳结构的受力机制，试件的轴向力出现了负值。为了更好的描述这一现象，本文将承载力为零的平面定义为“sealevel”，承载力最大时曲线围成的范围定义为“hill”。经分析得，“sea level”上部试件轴向荷载其主导作用，试件多发生轴向压缩变形，下部试件变形主要有扭转荷载控制，试件最终发生整体扭转失稳。

（6）轴压-扭转-内压作用下试件轴向承载力增大，试件局部失稳被推迟，并未发生整体失稳；根据轴压-侧压-内压荷载作用下的屈曲地貌和破坏模式可以看出，由于内部压强的存在，试件未发生屈曲变形，结构侧向承载能力大幅提升。这表明：柱壳结构内部充气提高了试件的侧向承载能力、轴向承载能力、抗扭能力和整体稳定性，降低了试件对初始缺陷的敏感度。

（7）试件边界条件由自由变为固接时，试件的承载能力增大稳定性提高，对初始缺陷敏感度降低。

致谢本文作者之一，孙博华曾于1991-1992有幸获得荷兰代尔夫特大学(TUDelft)的Research Fellowship,在航天工程学院师从结构稳定性权威J.Arbocz教授做ResearchFellow，学习研究结构曲屈和后曲屈理论。近期获悉Arbocz 教授因病仙逝，特以此文致敬Arbocz教授在结构曲屈理论方面给予孙博华的指导和提供的留学机会。

# XI．参考文献

[1] Euler，L.,De curvis elasticis，Leonhard Euler’s Elastic Curves,translated and annotated by W.A. Oldfather,C.A. Ellis,and D.M.Brown，reprinted from Isis,20,(58)，1933, The St.Catherine Press,Bruges,Belgium. [2] Timoshenko,S.,History of Strength of Materials,McGrawHill Book Company, New York/Toronto/London,1953   
[3] von Karman,T.V.and Tsien,H. S.[1939] The buckling of spherical shells by external pressure,J.Aero.Sci.,7,43-50. [4] von Karman,T.V.and Tsien,H. S.[1941] The buckling of thin cylindrical shells under axial compression.J.Aero. Sci., 8,303-312.   
[5] Tsien,H. S.[1942] Theory for the buckling of thin shells,J. Aero. Sci., 9, 373-384. [6] Koiter,W.T.[1945] On the stability of elastic equilibrium, Dissertation,Delft,Holland.(An English translation is available asNASA,Tech.Trans.,F10,833,1967(Koiter,W.T., 1945，“de Stabiliteit van het Elastich Evenwicht,”Ph.D.thesis,Delft University of Technology,Delft,The Netherlands.)   
[7] Tsien,H. S.[1947] Lower buckling load in the non-linear buckling theory for thin shells,Quart.Appl.Math.5,236-7.   
[8] Seide,P.and Weingarten,V.I.,On the Buckling of Circular Cylindrical Shells under Pure Bending,ASME Journal of Applied Mechanics,28,(1),March 1961,112-116.   
[9] Hutchinson，J.W.,Axial Buckling of Pressurized Imperfect Cylindrical Shells,AIAA Journal,3,(8),August 1965,1461- 1466.   
[10] NASA，1965，“Buckling of Thin-Walled Circular Cylinders,”NASA Space Vehicle Design Criteria,National Aeronautics and Space Administration，Washington，DC,Technical Report No.NASA SP-8007.   
[11] NASA,1969,“Buckling of Thin-Walled Doubly Curved Shells,”NASA Space Vehicle Design Criteria,National Aeronautics and Space Administration，Washington,DC,Technical Report No.NASA SP-8032   
[12] Babcock Jr.,C.D.[1967] The influence of the testing machine on the buckling of cylindrical shells under axial compression, Int.J. Solids Struct.3, 809-17.   
[13] J.W. Hutchinson and W.T. Koiter. Postbuckling theory, Applied Mechanics Reviews, pp.1353-1366,1970.   
[14] Singer,J.,Arbocz，J.，and Babcock,C.D.，Buckling of Imperfect Stiffened Cylindrical Shells under Axial Compression, AIAA Journal, 9,(1),1971,68-75.   
[15] Riks,E.,The Application of Newton’s Method to the Problem of Elastic Stability,ASME Journal of Applied Mechanics, 39,1972,1060-1066.   
[16] Thompson,J.M.T.and Hunt,G.W.[1973]A general theory of elastic stability,Wiley, London.   
[17] Arbocz,J.,The Effect of Initial Imperfections on Shell Stability,in: Thin-Shell Structures,Theory, Experiment and Design Y.C.Fung and E.E. Sechler eds.,Prentice Hall, Englewood Cliffs,N.J., 1974, 205-245.   
[18] Brush,D.O.,Almroth,B .O.[1975] Buckling of bars,plates and shells.McGraw-Hill, New York.   
[19] Arbocz,J.and Sechler,E.E.,On the Buckling of Stiffened Imperfect Shells,AIAA Journal,14,(11),1611-1617 (1976).   
[20] Arbocz，J.，Past，Present and Future of Shell Stability Analysis,Zeitschrift fir Flugwissenschaften und Weltraumforschung,5,(6),335-348(1981).   
[21] Arbocz,J.,Potier-Ferry，M.，Singer,J.and Tvergaard,V., Buckling and Post- Buckling,Lecture Notes in Physics No. 288,Springer-Verlag,Berlin,Heidelberg,1987.   
[22] J. Singer,J.Arbocz,T.Weller,Buckling Experiments:Experimental Methods in Buckling of Thin-Walled Structures, John Wiley & Sons,Inc.,New York (1998).   
[23] Bo-Hua Sun,Buckling Problems of Sandwich Shells,Delft University of Technology, pp.1-99., Report LR-690,1992.   
[24] K.Y.Yeh,Bo-Hua Sun and F.P.J.Rimrott,Buckling of impefect sandwich cone under axial compression - equivalentcylinder approach，part 1.Technische Mechanik,Band 14, Heft 3/4: 239-248,1994.   
[25] K.Y.Yeh,Bo-Hua Sun and F.P.J.Rimrott,Buckling of impefect sandwich cone under axial compression - equivalentcylinder approach，part 2.Technische Mechanik,Band 15, Heft 1:1-12,1994.   
[26] Bo-Hua Sun,K.Y. Yeh,and F.P.J. Rimrott,On the buckling of structures,Technische Mechanik,Band 15,Heft 2:129-140, 1995.   
[27] Bo-Hua Sun,Modified Koiter’s buckling theory based on the generalized variational principles,CERECAM Report No. 244,University of Cape Town,1994.   
[28] Timshenko,S.P.and Gere, J.M.,Theory of Elastic Stability, 2nd ed.,Dover Publications,Inc.New York,2009.   
[29] Singer,J.Buckling experiments ：experimental methods in buckling of thin-walled structures[J].Applied Mechanics Reviews,2002,56(1):B5.   
[30] Bushnell, D. Shell buckling, website, http://shellbuckling.com/index.php (2004).   
[31] Krasovsky V,Marchenko V，Schmidt R.Deformation and buckling of axially compressed cylindrical shells with local loads in numerical simulation and experiments[J]. ThinWalled Structures,2011,49(5):576-580.   
[32] Haynie,W.,Hilburger,M.,Bogge,M.,Maspoli,M.,and Kriegesmann,B.ValidationofLower-BoundEstimatesfor Compression-Loaded CylindricalShells, AIAAPaper No.2012-1864.   
[33] Thompson, J.M T .Advances in Shell Buckling: Theory and Experiments[J]. International Journal of Bifurcation Chaos, 2015,25(01):1530001.   
[34] Virot E,Kreilos T,Schneider TM,etal.Stability Landscape of Shell Buckling[J].Phys.Rev.Lett,2017,119.   
[35] Gerasimidis S,Virot E，Hutchinson J W,et al.On EstablishingBucklingKnockdownsforImperfectionSensitive Shell Structures[J]. Journal of Applied Mechanics, 2018,85(9):091010.   
[36]Von Slooten，R.A.and Soong，T.T.，Buckling of a long, axially compressed thin cylindrical shell with random initial imperfections,J.AppliedMechanics,Vol.39,No.4,Dec.1972, p.1066.   
[37] Narasimhan，K.Y.and Hoff,N.J.,Snapping of imperfect thin-walled circular cylindrical shells of finite length.J.Ap plied Mechanics,Vol.38,No.1,Mar.1971,pp.162-171.   
[38] Tennyson,R.C.,Muggeridge,D.B.and Caswell.R.D.New design criteria for predicting buckling of cylindrical shells underaxial compression.Journal of Spacecraft and Rockets,Vol. 8,No.10,Oct,1971,p.1062   
[39]Stein,M.,The effect on the buckling of perfect cylinders of prebuckling deformations and stresses induced by edge support.Collected papers on instability od shell structures.NASA TN D-1510.Dec.1962,p.217   
[40]Almroth，B.O.，Holmes，A.M.C.and Brush，D.O.，An experimental study of the buckling of cylinders under axial compression.Experimental Mech.4,263-270,1964.   
[41] Budiansky,B.,Theory of buckling and post-buckling,Advance in AppliedMech,Vol.14,1974.   
[42]Elishakoff,I.,2014,Resolution of the Twentieth Century ConundruminElastic Stability,World ScientificPublishing,Singapore.   
[43]Mark W.Hilburger,Developing the Next Generation Shell Buckling Design Factors and Technologies [R],American Institute of Aeronautics and Astronautics,2007   
[44]Gerasimidis，S.，Virot，E.，Hutchinson，J.W.and Rubinstein，S.M..On Establishing Buckling Knockdowns for Imperfection- Sensitive Shell Structures,Journal of Applied Mechanics,85,091010-1(2018)   
[45] Yan H.,et al,Sterically controlled mechanochemistry under hydrostatic pressure,554,Nature,505(2018)   
[46] W.Yang,Z.-M.Li,W.Shi,B.-H.Xie,and M.-B.Yang,Review on Auxetic Materials,J.Mater.Sci.39,3269 (2004).   
[47]A.Alderson and K.L.Alderson,Auxetic Materials,PI Mech Eng G-J Aer 221,565 (2007).   
[48]Xiaoyu Zheng,et al.,Ultralight,Ultrastiff Mechanical Metamaterials,Science,VOL 344ISSUE 6190,2014.   
[49]Banerjee et al.,Ultralarge elastic deformation of nanoscale diamond,Science 360,300 -302 (2018)   
[50] Bin Liu,et al.,Topological kinematics of origami metamaterials,Nature Physics,14:811-815(2018)   
[51]周承倜.薄壳弹塑性稳定性理论[M].国防工业出版社，1979.   
[52]徐春杰,张浩,许帅，etal.易拉罐用铝基和铁基材料组织与力学性 能对比研究[J].铸造技术,2018,v.39No.314(05):14-17.   
[53]李魏梓,宋昕宜,杨凯,马新玲,杨刚.易拉罐轴向受压失稳试验研究 及有限元分析[J].制造业自动化,2014,36(15):83-85+101.