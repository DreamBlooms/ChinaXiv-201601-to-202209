# 500kV高压直流输电线离子流场对绝缘子电位分布特性影响

李静 冯宇宁』 刘骥陶² 许鹏鹃1（1.沈阳工业大学电气工程学院 沈阳 1108702.沈阳新松机器人自动化有限公司 沈阳 110006)

![](images/d0aaa7e7ee1d4a7e09b7e75568bec6fa44d931eaed1ae06eca69ad2c1c74fd45.jpg)

李静女 1977年生，博士，讲师，研究方向为电器及其控制。

摘要：由于特高压直流输电线周围存在空间电荷，直流输电线附近电场分布复杂，对附近的绝缘子闪络存在影响。本文基于上流有限元方法计算模拟了 $5 0 0 \mathrm { k V }$ 单极高压直流线路附近的离子流场，采用迭代收敛控制算法，以保证迭代收敛；研究了空间电荷的存在对 $5 0 0 \mathrm { k V }$ 直流绝缘子沿面参数的影响。

关键词：特高压空间电荷 直流输电绝缘子闪络离子流场中图分类号：TM85

# The Impact of the $\mathbf { 5 0 0 k V }$ Ion Flow Field of High Voltage DC Transmission Lines on Insulator Potential Distribution

Li Jingl Feng Yuning' Liu Jitao² Xu Pengjuan' （1.Shenyang University of Technology School Shenyang 110870 China 2. Shenyang Xinsong Robot Automation Co., Ltd. Shenyang 110006 China）

![](images/92bc7d927223f1ab534ced476854e2b9830c74edd0b89ebda8e1f2b7af958d73.jpg)

Abstract: The space charge around ultra high voltage dc transmission line makes the electric field distribution nearby complicated,and has an effect on the insulator flashover nearby. The ion flow field near the $5 0 0 \mathrm { k V }$ single-electrode high voltage dc line is simulated based on the upper-class finite element method in this paper,and an iterative convergence control algorithm is adopted to ensure iterative convergence.The influence of space charge on the surface electric field parameters of $5 0 0 \mathrm { k V }$ dc insulators is studied.

冯宇宁男1993年生，硕士研究生，研究方向为电器及其控制。

Keywords: Extreme high voltage,space charge,dc power transmission, insulator, flashover, the ion flow field

# 1 引言

高压直流输电技术在远距离、大容量输电方面有较大的优势[1-3]，在我国电网中发挥着重要的作用。然而，高压直流输电的发展却面临较大的技术难题，与交流输电线路相比，高压直流输电线路周围存在的空间电荷导致线路附近电场强度与交流线路有明显区别，对附近的电器设备的电场分布也有较大的影响，由于绝缘子距离输电线十分接近，受影响较明显，且绝缘子表面电场电位数值对电网稳定运行具有十分重要的现实意义。因此，有必要对直流线路附近的离子流场进行研究。

同时，直流输电线路运行时，如果导线表面的电场强度超过大气的击穿场强，导线表面会发生电晕放电[4]，产生空间电荷，线路附近的电荷会在空间产生电场，使直流线路和交流线路具有不同的电场分布。高压直流线路在运行时，会发生电晕放电现象，而且直流输电线路与交流线路在发生电晕现象时，附近的空间电荷分布存在很大区别。由于交流输电线的线路电压随时间作正弦变化，因此当交流线路产生电晕时，在上半周期产生的空间电荷，在下半周期时，由于线路极性发生改变，又被导线吸引，因此，交流输电线附近的空间电荷仅在导线附近做往返运动，在各相输电线线之间和相导线与大地之间的范围内基本不存在空间电荷。而直流输电线路发生电晕时，由于输电线的电压极性恒定，在极导线发生电晕产生的带电离子中，与导线极性相反的离子向导线移动，而与导线极性相同的离子将远离导线，沿所受电场力方向移动，因此，在各相输电线线之间和相导线与大地之间的范围内会存在带电离子。

在整个输电线路上，绝缘子是其中应用广泛的装备之一，电网的安全与稳定运行与绝缘子运行状况息息相关。由于直流输电线路存在离子流场问题，绝缘子串的周围存在着空间电荷，使其电压及电场强度分布特性与交流绝缘子发生变化。为了保障高压直流线路绝缘子在线路正常运行，减少闪络事故，在设计时，需要分析绝缘子的沿面参数。由于直流线路存在离子流场问题，这将导致绝缘子串的周围（尤其是高压端）存在着大量的空间电荷，这些空间电荷使绝缘子的沿面电压及电场强度分布特性与交流绝缘子不同。当绝缘子沿面电压分布不均匀的情况严重时，绝缘子处于高场强一端的部件容易发生老化，绝缘能力受到破坏，当局部发生电晕时，绝缘子的绝缘能力受到影响更大，这将严重影响电网安全运行。为使直流输电线路更安全地运行，需要对直流绝缘子沿串电压、电场分布计算方法进行研究。这种研究可以更深入地了解直流线路中绝缘子的性能，有助于更好地针对直流绝缘子的特点进行优化设计，同时，对于进一步研究绝缘子的沿面放电和污闪提供了支持，对于直流线路绝缘子的优化设计和稳定运行具有重要意义，通过这些优化，可以逐步确保直流输电线的安全运行，从而最终解决高压直流输电的技术难题。

本文对描述直流输电线路离子流场的Poisson方程和电流连续性方程进行了求解，提出了改进的迭代方法，基于Kapzov假设，研究了直流输电线的离子流场及风速对其影响，同时使用Matlab软件进行编程，采用有限元法，计算了空间电荷对$5 0 0 \mathrm { k V }$ 绝缘子表面电场和电位分布的影响。

# 2 数学模型

# 2.1离子流场控制方程

特高直流输电线路在工作时，由于发生电晕现象，附近存在大量的带电离子。带电离子的运动形成离子流。考虑风速的影响，由高压直流输电线的具体运行环境及麦克斯韦方程组可以得出离子流场的控制方程如下：

$$
\begin{array} { r l } & { \nabla ^ { 2 } \varphi = - ( \rho _ { + } - \rho _ { - } ) / \varepsilon _ { 0 } } \\ & { \qquad E = - \nabla \varphi } \\ & { J _ { + } = \rho _ { + } ( { \boldsymbol K } , { \boldsymbol E } + { \boldsymbol w } ) } \\ & { J _ { - } = \rho _ { - } ( { \boldsymbol K } . { \boldsymbol E } - { \boldsymbol w } ) } \\ & { \nabla \cdot J _ { + } = - R \rho _ { + } \rho _ { - } / e } \\ & { \nabla \cdot J _ { - } = - R \rho _ { + } \rho _ { - } / e } \\ & { \nabla \cdot J _ { - } = - R \rho _ { + } \rho _ { - } / e } \end{array}
$$

式中， $\varphi$ 为电位； $\rho _ { + \setminus } \rho _ { - }$ 分别为正、负空间电荷密度； $\scriptstyle { \varepsilon _ { 0 } }$ 为空气介电常数； $E$ 为合成电场强度； $J _ { + }$ ， $J _ { - }$ 分别为正、负离子电流密度； $K _ { + }$ 、 $K _ { - }$ 分别为正、负离子迁移率； $w$ 为风速； $R$ 为离子复合系数； $e$ 为电子电量。

# 2.2基本假设

为更加方便地对离子流场进行分析，本章在分析中采用如下假设：

（1）高压直流输电线周围空间充满了两种极性的电荷，由于电离层厚度远远小于导线对地高度和极间距离，因此对其厚度忽略不计。

(2）计算时认为导线电晕已经稳定，不考虑其  
中的暂态变化过程。(3）计算时导线附近的电晕保持稳定，起晕场  
强不发生变化，即Kaptzov 假设。(4）离子迁移率 $k$ 和复合系数 $\boldsymbol { r }$ 与其他变量无  
关，作为常数。(5）不考虑空间电荷扩散，尽管空间电荷存在  
扩散现象，但是与其所受电场力相比，基本可以忽  
略。因此忽略电荷扩散不产生过大误差。(6）在加入风速条件时，忽略风速变化过程，  
风速为常量且稳定不变。(7）不考虑杆塔影响和电晕分布的不均匀性，  
使三维问题变为二维问题。在本文的计算中，电晕起始场的大小通过式

（1）计算获得地面合成电场的约束方程为

$$
E _ { \mathrm { c } } = 2 9 . 8 m \delta \Bigg ( 1 { + } \frac { 0 . 3 0 1 } { \sqrt { \delta r } } \Bigg )
$$

式中， $\boldsymbol { r }$ 为导线半径； $m$ 为导线表面粗糙系数； $\delta$ 为空气的相对密度。

# 3模型求解

在求解直流输电线路离子流场时，需要利用用边界条件以求解泊松方程和电流连续性方程式(1）～式 (6)。其中，由于每个节点的空间电荷密度 $\rho _ { + }$ ， $\rho _ { - }$ 和电位 $\varphi$ 均为待求量，本文采用迭代方法进行求解。在计算时，首先根据同轴圆柱的电荷密度求解公式给出各节点的近似电荷密度初值，根据所给的电荷密度和边界条件计算出各节点的电位及场强，之后再由各点的电场强度，求解电流连续性方程，得到所有节点的空间电荷密度，再根据新的空间电荷密度分布求解新的电位及其场强，直到电场强度和所有节点的空间电荷密度的计算结果同时满足给出的收敛条件，则这个计算结果就为所求数值解。程序计算流程如图1所示。

本文导体表面电荷采用方程如下

$$
\rho _ { \mathrm { 0 } } = { \frac { 4 \varepsilon _ { \mathrm { 0 } } U _ { \mathrm { 0 } } E _ { \mathrm { g } } ( U - U _ { \mathrm { 0 } } ) } { r H E _ { \mathrm { c } } U \left( 5 - { \frac { U _ { \mathrm { 0 } } } { 4 } } \right) } }
$$

式中， $E _ { \mathrm { g } }$ 为导线正下方地面附近的标称场强； $\boldsymbol { r }$ 为导线半径； $H$ 为导线高度； $U _ { 0 }$ 为导线的起晕电压。

本文电荷密度迭代公式为

![](images/4d9375d205b43e77be5dd70732e651fced5610eff68d91a0498aa783c762c333.jpg)  
图1程序计算流程  
Fig.1The calculation process of the program

$$
\rho _ { i } ^ { n } = \rho _ { i } ^ { ( n - 1 ) } \Bigg [ 1 + \mu \frac { E _ { \mathrm { m a x } } - E _ { \mathrm { c } } } { E _ { \mathrm { m a x } } + E } \Bigg ]
$$

式中， $\rho _ { i } ^ { n }$ 为节点 $i$ 在第 $n$ 次迭代时的电荷密度； $\boldsymbol { \mu }$   
为修正因子； $E _ { \mathrm { m a x } }$ 为导线表面最大场强值。

本文 $\mu$ 值选择为 $( E _ { \mathrm { m a x } } - E _ { \mathrm { c } } ) / E _ { \mathrm { m a x } }$ ，这样使程序在运行时根据结果能够自行调整表面电荷变速度。在表面误差较大时能快速向收敛发展，同时在接近收敛值时，使修正变化减慢，尽可能提高精度。

在每次迭代进行修正之后，再次进行下一次迭代计算，在满足收敛条件得到数值解后，推出迭代。

# 4 仿真结果分析

# 4.1离子流场作用下空间电荷分布计算

本文利用Matlab软件自编程求解。采用有限元法计算输电线附近空间电荷之后，得到输电线附近空间电荷的分布。

模型的原始参数为：导线半径为 $0 . 0 2 \mathrm { m }$ ，距地 高度为 $2 0 \mathrm { m }$ ；起始电晕场强为 $3 5 \mathrm { k V / m }$ ，起始电晕 电压329kV[6]

本文分别计算了加载沿 $x$ 轴正方向 $2 \mathrm { m / s }$ 、 $4 \mathrm { m / s }$ ，$6 \mathrm { m / s }$ 和 $8 \mathrm { m / s }$ 的风速，计算不同风速影响下输电线附近空间电荷密度，结果如图 $2 \sim$ 图5所示。从图中结果可以发现水平风速从 $0 \mathrm { m / s }$ 逐渐增大到 $4 \mathrm { m / s }$ 时，风速对导线附近空间电荷分布存在较明显的影响，电荷密度的最大值与风速呈正比例关系，随着风速的增加，整个空间电荷密度的最大值也随之增加，整体分布也明显向风的方向偏移。

# 4.2空间电荷对绝缘子沿面电场参数影响

超高压、特高压直流输电系统中，由于电压等

![](images/78cd79d16e74184e0f009d6cbbfee9745f95cc159173f03cc2536deee3748921.jpg)  
图2风速 $2 \mathrm { m / s }$ 时空间电荷密度分布

![](images/7e984c1c5d002a779efbbce2b4f3394257e809ac953bc7ac778d188bf933f975.jpg)  
Fig.2The density distribution of the space charge in $2 \mathrm { m / s }$ s wind speed

级高，很多环境因素都有可能对绝缘子的电气性能造成破坏，导致绝缘子无法正常工作，因此对绝缘子表面电场及电位进行深入的研究与分析是有必要

![](images/c8935cdd0c95ecc484dfb73c5159cc61a10aa407a91d11d66be14ac00bea48ba.jpg)  
图4风速 $6 \mathrm { { m } / \mathrm { { s } } }$ 时空间电荷密度分布

![](images/53559a70e51c5c8b694e66aa473affb77110759143b8f32b63a2b181d5f38179.jpg)  
图3风速 $4 \mathrm { m / s }$ 时空间电荷密度分布  
Fig.4The density distribution of the space charge in $6 \mathrm { { m } / \mathrm { { s } } }$ s   
图5风速 $8 \mathrm { m / s }$ 时空间电荷密度分布  
Fig.5The density distribution of the space charge in $8 \mathrm { m / s }$ S wind speed

的，本章计算了在空间电荷存在的情况下绝缘子的电场与电位分布，并与交流线路运行状态下的绝缘子进行了对比。模型具体参数见下表。

# 表绝缘子主要尺寸和参数

Tab． The main dimension and parameter of the insulator   

<html><body><table><tr><td rowspan="2">额定机械负荷/kN</td><td colspan="2">盘径/mm</td><td rowspan="2">芯棒直径/mm</td><td colspan="2">伞盘数</td><td rowspan="2">泄漏距离/mm</td><td rowspan="2">绝缘长度/mm</td><td rowspan="2">单边金属端长/mm</td></tr><tr><td>大</td><td>小</td><td>大</td><td>小</td></tr><tr><td>160</td><td>144</td><td>110</td><td>24</td><td>54</td><td>54</td><td>12 786</td><td>4240</td><td>190</td></tr></table></body></html>

在无空间电荷情况下电场与电位分布由图6和图7所示。

在存在空间电荷条件下，绝缘子的电场及电位分布云图如图8和图9所示。空间电位由输电线的电位及空间电荷共同作用决定，可以看出由于空间电荷的作用，整个空间的电位有明显提高。

在后处理中，将绝缘子各伞群边缘点的电场值及电位值提取出来，图10为包含空间电荷及不包含空间电荷的电场对比曲线，图11为电位对比曲线图。

![](images/82ab48ab570ee6316a4f102b4a17d74fe8277d5196d2b310580fed80a3a9cca3.jpg)  
Fig.3The density distribution of the space charge in $4 \mathrm { m / s }$ s wind speed   
图6无空间电荷电场分布  
Fig.6The electric field distribution without space charge

![](images/3bd374cfceeb674e0277b2164f997c5249f309e3910c9e2e88e7baf2818ef5c5.jpg)  
图7无空间电荷电位分布

![](images/3081338879f7dfe41a9c6c4a9023c049a2cb761cc4f1fbba39befdbb2107a03c.jpg)  
Fig.7The potential distribution without space charge

![](images/0aa601d2a29dd3874480974f1bb1ba5f2d9338c8ab75530cbcd1bd185f25f81a.jpg)  
图8存在空间电荷电场分布  
图9存在空间电荷电位分布  
Fig.9The potential distribution with space charge

由图10可知，空间电荷的存在使伞群的电位值明显升高。同时，对比两种状态下的伞裙电场强度分布，可以看出考虑空间电荷情况下，高压端的电场强度明显提高，而绝缘子低压端的电场强度有一定的下降。空间电荷的存在对绝缘子表面的电位和电场强度有很大的影响。产生这种现象的原因是导体的电晕层具相同极性的电荷，在空间的电位有空间电荷和，所以在空间上对绝缘子的电动势有一定加强。

![](images/a3ab9a607aa0a526c6b933395c745a0b07b71874caf02344c46401588ce1096e.jpg)  
图10绝缘子沿面电位分布对比

![](images/4d42107da1330726324a4f8d54ff7f12b180ca51e33e50510b2b32fc0152c8f6.jpg)  
Fig.8The electric field distribution with space charge   
Fig.10The contrase of the potential distribution along the surface of the insulator   
图11绝缘子沿面电场分布对比  
Fig.11The contrase of the electric field distribution along the surface of the insulator

# 5 结论

本文仿真分析了 $5 0 0 \mathrm { k V }$ 特高压直流输电时导线周围空间电荷分布对绝缘子沿面电场分布的影响，并得到以下结论：

（1）针对 $\pm 5 0 0 \mathrm { k V }$ 单极线路，分析了风速对导线附近空间电荷分布的影响，风速会使空间电荷密度最大值升高并向风向偏移；给出了空间电荷分布云图。

(2）研究了存在空间电荷情况下线路上悬式绝缘子的沿面电位及场强分布，并进行了分析。绝缘子高压端的电场强度小于静电场的电场强度，绝缘子低压端的电场强度大于静电场的电场强度，大约增加了 $8 \%$ 。

# 参考文献

[1] 汪讽，范竞敏，李敏，等．高精度上流有限元法在特高压直流输电线路离子流场计算中的应用[J].高电压技术，2016(4)：1061-1067.

Wang Feng,Fan Jingmin,Li Min, etal.Applicationof the high precision upstream FEM to calculation ofthe Ionized field of HVDC transmission line.HighVoltage Engineering[J]. 2016(4): 1061-1067.  
[2] 汪讽，李敏，吕建红，等．风速对特高压直流输电线路离子流场分布的影响[J]．高电压技术，2016(9): 2897-2901.WangFeng,LiMin,Lü Jianhong,etal.Effect ofwindspeed on ion flow field under UHVDC transmissionlines[J]. High Voltage Engineering,2016(9): 2897-2901.  
[3] 袁海燕，傅正财．特高压双极直流输电线路离子流计算[C]．全国博士生学术论坛，2008.  
[4] 乔骥，邹军，鄂天龙，等．有屏蔽线时特高压直流输电线路地面电场与离子流场计算与分析[J]．电网技术，2017，41(7)：2386-2392.Qiao Ji, Zou Jun,E Tianlong,et al.Calculation ofground-level electric field and ion flow of HVDCtransmission lines with shield wires[J].PowerSystem Technology,2017,41(7): 2386-2392.  
[5] Hu Q, Shu L, Jiang X,et al. Influence of air pressureand humidity on positive direct current coronadischarge performances of the conductor in a coronacage[J]. International Transactions on ElectricalEnergy Systems,2014,24(5): 723-735.  
[6] 刘振亚，特高压电网[M]．北京：中国经济出版社，2005：1-10，267-289.  
[7] 刘振亚．特高压直流输电线路[M]．北京：中国电力出版社，2009：1-17，114-143.  
[8] 武占成，张希军．气体放电[M]．北京：国防工业出版社，2012.  
[9] 戴熙杰．直流输电基础[M]．北京：水利水电出版社，1990：230-264.