# 铁在液态铅铋合金中腐蚀的分子动力学研究

刘 捷甄 琦赵灿军卢文强(中国科学院大学工程科学学院，北京101408)

摘要液态铅铋合金(LBE)是一种性能优异的材料，在加速驱动系统（ADS）中作为散裂靶和冷却剂材料。然而，在ADS 中，贮存 LBE 的容器和结构钢材料在高温下与 LBE 直接接触时会被严重腐蚀。本文研究该腐蚀和金属Cr、Ni减轻该腐蚀的机制。研究发现，铁在 LBE 中被腐蚀的微观机制是由于铁原子与 LBE 原子相互渗透，破坏了铁材料结构；铁中掺入Cr、Ni可以有效减轻铁的腐蚀,其微观机理为金属Cr、Ni加入到铁后阻止了LBE 原子渗入铁材料中破坏其结构。

关键词腐蚀；分子动力学；LBE；扩散系数中图分类号：TK124 文献标识码：A 文章编号: 0253-231X(2017)03-0557-05

# Corrosion Study of Iron in Liquid Lead-Bismuth Eutectic in Accelerator Driven System by Molecular Dynamics Method

LIU JieZHEN QiZHAO Can-JunLU Wen-Qiang (School of Engineering Science,Universityof Chinese Academy of Sciences，Beijing 101408,China)

Abstract The liquid-bismuth eutectic (LBE) is an excellent material as coolant and spallation target material in the accelerator driven system (ADS). However,the molten metal has a severely corrosion for structural stel material and the container storing LBE,especially at high temperatures. This paper studies the mechanism of the corrosion and mitigating the corrosion by using Cr and Ni. It is concluded that the micro-mechanism of the corrosion of the iron in the LBE is due to the mutual penetration between the iron and the LBE atoms destroys the structure of the iron. Meanwhile,after adding the Cr and Ni atoms in the iron,the corrosion of the iron is efectively reduced,which owes to the mixing of the Cr and Ni atoms in the iron prevents the LBE atoms from penetrating into the iron material and destroying its structure.

Key words corrosion;molecular dynamics;LBE;diffusion coefficient

# 0引言

LBE 是ADS 中一种性能优异的冷却剂和散裂靶的材料[1,2]，这是因为其低熔点(398.25K)，高沸点(1943.15K)[3]，低蒸汽压力和良好的传热性能[4]。这些优异的性能使得 ADS 运行过程更加可靠和安全[5]。此外，LBE不仅与水和氧气成化学惰性，而且每 $1 ~ \mathrm { G e V }$ 的能量能使其产生30 个中子[，与其他材料相比，能够产生更多的中子。基于以上优异性能使得LBE 成为了 ADS 的最佳材料之一。

众所周知，腐蚀会严重影响材料的性能，给ADS的安全性带来隐患。故而，LBE对容器和结构钢的腐蚀问题被视为研究ADS系统问题的焦点之一。特别是在高温下，这种液态材料对铁制容器有极强的腐蚀性[4,6]。虽然有一些实验研究了LBE 的腐蚀间题[6-8],但是关于腐蚀的机理尚未有透彻的理解。就目前来说，腐蚀问题是ADS系统设计与运行的一个至关重要和充满挑战的问题，关乎到整个系统的安全性与可靠性。因此需要从微观的角度理解原子间的扩散过程，从根本上掌握腐蚀产生的原因以保证ADS系统安全可靠稳定的运行。虽然实验结果可靠，但是其花费较高且在ADS系统中进行较为困难。因此通过分子动力学模拟来研究此问题成为一个很好的选择。Artoto、Wang 等人[9,10]也用分子动力学的方法研究了铁在液态铅中的扩散系数。Manulana等人[11]用分子动力学的方法研究了Pb、Bi原子渗透到铁中的深度。本文把腐蚀问题看作为铁自身结构被破坏且铁原子与LBE原子相互扩散的过程。为了揭示铁在LBE中的腐蚀机理和利用在铁中加入金属铬（Cr)、镍(Ni）来减轻该腐蚀，本文通过计算铁及其他元素原子在LBE中的扩散系数，并得到了铁在LBE中腐蚀过程中的微观结构图并进行了深入的分析。

# 1 理论背景

分子动力学模拟是一种用来计算一个经典体系的平衡和传递的方法，在特定的模拟条件下(温度，压力，时间，原子数等)，追踪和计算出原子的轨迹从而得到系统各种性质。在原子系统中，原子之间的相互作用力是基于牛顿运动方程：

$$
M { \frac { \mathrm { d } ^ { 2 } r _ { i } } { \mathrm { d } t ^ { 2 } } } = \sum _ { j = 1 , j \neq i } ^ { N } F _ { i j }
$$

式中， $F _ { i j }$ 表示原子 $i$ 与原子 $j$ 之间的相互作用力， $M$ 是原子 $i$ 的质量, $\boldsymbol { r } _ { i }$ 表示原子 $i$ 的位移， $N$ 表示原子总数， $\mathrm { d } t$ 表示模拟时间步长。

在分子动力学模拟中，原子之间相互作用的势函数的选取尤为重要，在模拟中，原子之间采用Lennard-Jones (LJ) $n - m$ 势函数：

$$
U ( r ) = \kappa \varepsilon \left[ \left( \frac { \sigma } { r } \right) ^ { n } - \left( \frac { \sigma } { r } \right) ^ { m } \right]
$$

公式(2)中 $\sigma$ 和 $\boldsymbol { \varepsilon }$ 是LJ势函数参数，分别表示尺寸参数、势阱深度。

在本文中，我们取 $n = 1 2$ ， $m = 6$ ，则LJ势函数的形式为：

$$
U ( r ) = \kappa \varepsilon \left[ \left( { \frac { \sigma } { r } } \right) ^ { 1 2 } - \left( { \frac { \sigma } { r } } \right) ^ { 6 } \right]
$$

对于同种元素的原子（Fe-Fe、Pb-Pb、 $\mathrm { C r - C r }$ 、Ni-Ni)之间的LJ势参数，我们选取 Zhen 和 Davies[12] 给出的值。铋元素原子(Bi-Bi)之间的LJ势参数源于Lemmon 等人[13]的研究。不同原子之间(Fe-Pb、Fe-Bi、Pb-Bi、Pb- $\mathrm { . c r }$ 、Bi- $\mathrm { . c r }$ 、Pb-Ni、Bi-Ni）的势函数则根据Lorentz-Berthelot混合原则：

$$
\sigma _ { i j } = ( \sigma _ { i i } + \sigma _ { j j } ) / 2
$$

$$
\varepsilon _ { i j } = \sqrt { \varepsilon _ { i i } \cdot \varepsilon _ { j j } }
$$

本文采用的LJ势参数见表1。

一般而言，腐蚀是一个化学反应的过程。然而，Manly[14] 研究发现，高温时铁在液态金属中的腐蚀，腐蚀过程中并未发现电子在原子间的转移，非化学行为占了主要的因素。因此，本文把腐蚀过程看作为一个物理过程，而并非化学过程。本文主要关注的是铁在LBE 中的扩散过程，并应用以下两个公式计算铁在LBE中的扩散系数：

$$
M S D = \langle | \vec { r } ( t ) - \vec { r } ( t = 0 ) | ^ { 2 } \rangle
$$

$$
D = \operatorname* { l i m } _ { t  \infty } \frac { \langle | \vec { r } ( t ) - \vec { r } ( t = 0 ) | ^ { 2 } \rangle } { 6 t }
$$

式(6)、（7)中 $M S D$ 表示均方根位移，“”表示系综平均， $\vec { r } ( t )$ 和 $\vec { r } ( t = 0 )$ 分别表示原子在时间 $\mathbf { \Psi } _ { t }$ 和 $t = 0$ 时刻的位移。

表1LJ参数表  
Table 1 The LJ potential parameters   

<html><body><table><tr><td>元素</td><td>ε/eV</td><td>σ/10-10m</td></tr><tr><td>Fe-Fe</td><td>0.5193</td><td>2.3193</td></tr><tr><td>Pb-Pb</td><td>0.2363</td><td>3.1888</td></tr><tr><td>Bi-Bi</td><td>0.0590</td><td>3.0500</td></tr><tr><td>Cr-Cr</td><td>0.4989</td><td>2.3357</td></tr><tr><td>Ni-Ni</td><td>0.5190</td><td>2.2808</td></tr><tr><td>Fe-Pb</td><td>0.3503</td><td>3.6979</td></tr><tr><td>Fe-Bi</td><td>0.1750</td><td>3.5369</td></tr><tr><td>Pb-Bi</td><td>0.1181</td><td>4.8629</td></tr><tr><td>Fe-Cr</td><td>0.5090</td><td>2.7086</td></tr><tr><td>Fe-Ni</td><td>0.5191</td><td>2.6449</td></tr><tr><td>Pb-Cr</td><td>0.3433</td><td>3.7240</td></tr><tr><td>Pb-Ni</td><td>0.3502</td><td>3.6365</td></tr><tr><td>Bi-Cr</td><td>0.1716</td><td>3.5619</td></tr><tr><td>Bi-Ni</td><td>0.1750</td><td>3.4782</td></tr><tr><td>Cr-Ni</td><td>0.5088</td><td>2.6636</td></tr></table></body></html>

# 2模拟结果与讨论分析

为了研究铁在 LBE 中的腐蚀以及加入金属$\mathrm { C r }$ 、Ni在该腐蚀过程中的作用，本文研究内容主要分为下面的几个部分。

# 2.1不同温度下铁在LBE 中的扩散系数计算

本文采用的模拟盒子为：中央建立 $1 7 \times 1 7 \times 1 7$ 的晶格常数为 $2 . 8 6 8 2 \times 1 0 ^ { - 1 } ~ \mathrm { n m }$ 的 BCC 结构的铁原子，其个数为10745；铁原子周围为LBE原子，其中铅原子个数为 $2 1 5 6 8 ( \omega ( \mathrm { P b } ) { = } 0 . 4 5 )$ ，铋原子个数为26137( $\omega ( \mathrm { B i } ) { = } 0 . 5 5 \$ ，铁、铅和铋元素的相对原子质量分别为55.845，207.2，208.98；模拟盒子的体积大小为 $1 2 . 2 6 \times 1 2 . 2 6 \times 1 2 . 2 6 ~ \mathrm { n m ^ { 3 } }$ ，其结构如图1所示。对于ADS而言，其工作温度范围为 $7 7 3 \small { \sim } 8 7 3 \mathrm { ~ K ~ }$ ，我们不仅要研究正常工作温度下情况，而且需要考虑极端高温的情况，因此，在计算铁在LBE中扩散系数时，选取温度为：773K,873K,973K，1023K，1073K，1173K，1273K。本文使用LAMMPS软件进行模拟时所采用的参数：NVT系综，时间步长为0.0001ps，弛豫时间为 $1 0 ~ \mathrm { p s }$ ，平衡时间为 $8 0 ~ \mathrm { p s }$ 。模拟完成后，根据公式(6)、(7)计算出铁在LBE中的扩散系数。

![](images/76b72cb55151c9fe2603b773064bed058f30d647bb2b16a6e33d2f6a0dbf4882.jpg)  
图1Fe-LBE系统微观结构图(Fe、Pb、Bi原子颜色分别为淡黄色、红色、蓝色)

利用铁在LBE 中的 MSD(图 2）和式 (6)、（7)计算出了 $\mathrm { 1 0 2 3 ~ K }$ 时铁在 LBE 中的扩散系数为$2 . 2 4 \times 1 0 ^ { - 9 } ~ \mathrm { m ^ { 2 } / s }$ ；该值与Banerje[15]给出的实验值$\mathrm { 2 . 2 7 \pm 0 . 1 1 \times 1 0 ^ { - 9 } ~ m ^ { 2 } / s }$ 十分接近，这说明了本文模拟结果的可靠性。紧接着，本文计算了在不同温度下 $( 7 7 3 \mathrm { K } , 8 7 3 \mathrm { K } , 9 7 3 \mathrm { K } , 1 0 7 3 \mathrm { K } , 1 1 7 3 \mathrm { K } , 1 2 7 3 \mathrm { K } )$ 铁在LBE中的扩散系数，结果如图3所示。到目前为止，仅Banerje得出温度为 $1 0 2 3 \mathrm { K }$ 时铁在LBE 中的扩散系数实验值，因此本文模拟所得到的值可以提供有效的参考数据。

![](images/79cc680c875697b0912dcc28ddaee06d26de69c16872526077997a387e6eb9e8.jpg)  
Fig.1 The simulation box of Fe-LBE system(The colors of Fe,Pb and Bi atoms are yellow,grey and indigo,respectively)   
图2 1023K 时铁在LBE中的 MSD 曲线图Fig.2 The MSD curve of the iron in the LBE at 1023K  
Fig.4 The diffusion coefficient of the iron in the LBE after adding different proportion of $\mathrm { C r }$ in the iron at different temperatures

![](images/8e0fe94c6496f5f7b61bfc5131ee07bcb0972395b81aee0f5d5fc94924785ad6.jpg)  
图3不同温度下铁在LBE 中的扩散系数Fig.3 The diffusion coefficient of the iron in the LBE atdifferent temperatures

# 2.2铁中掺人不同比例 $\mathbf { C r }$ 、Ni

基于上述模拟的准确性，本文研究了在铁中加入不同比例 $\mathrm { C r }$ ，Ni的情况，此时模拟温度，模拟参数都与2.1节相同。本文在铁中掺入金属 $\mathrm { C r }$ ，Ni质量分数如下：

1）当铁中掺入质量分数分别为 $\begin{array} { r l } { \omega ( \mathrm { C r } ) } & { { } = } \end{array}$ $5 \%$ ， $\omega ( \mathrm { C r } ) = 1 0 \%$ ， $\omega ( \mathrm { C r } ) = 1 5 \%$ 的铬时，计算结果如图4所示。

![](images/14437ffbf2dcd70642981e874ca81d4011ad08b92d20946cfbb9f3e7eac95f06.jpg)  
图4不同温度下铁中加入不同比例 $\mathrm { C r }$ 时其在LBE 中的扩散系数

2）当铁中掺入质量分数分别为 $\omega ( \mathrm { N i } ) = 5 \%$ $\omega ( \mathrm { N i } ) = 1 0 \%$ ， $\omega ( \mathrm { N i } ) = 1 5 \%$ 的镍时，计算结果如图5所示。

![](images/ba83e20b1f2d8f7cdf9a11d9a3a1ec0c5ca41476db99759a50fe8b993d024fb8.jpg)  
图5不同温度下铁中加入不同比例 Ni 时其在LBE 中的扩散系数

3）当铁中同时掺入质量分数分别为 $\omega ( \mathrm { C r } ) =$ $5 \%$ 、 $\omega ( \mathrm { N i } ) { = } 5 \%$ ， $\omega ( \mathrm { C r } ) { = } 1 0 \%$ 、 $\omega ( \mathrm { N i } ) { = } 1 0 \%$ ， $\omega ( \mathrm { C r } ) =$ $1 5 \%$ 、 $\omega ( \mathrm { N i } ) { = } 1 5 \%$ 的铬镍时，计算结果如图6所示。

铁在LBE中的扩散系数越大，说明其受到的腐蚀程度越重。图4中，铁的扩散系数随着温度的升高而升高，这说明高温下铁腐蚀程度比低温下要大;在不同温度下，铁中加入不同比例 $\mathrm { C r }$ 元素后，其在LBE中扩散系数都比纯铁的小，这说明 $\mathrm { C r }$ 的加入使得铁的腐蚀程度得到了减轻；随着 $\mathrm { C r }$ 元素比例的增加，扩散系数也逐渐减小，这说明在加入质量分数为 $5 \% \sim 1 5 \%$ 的 $\mathrm { C r }$ 时，随着 $\mathrm { C r }$ 质量增加，铁腐蚀程度逐渐减小，但是 $\mathrm { C r }$ 比例在 $1 0 \%$ 、 $1 5 \%$ 时，对铁的腐蚀程度并不是很明显。如图5所示，铁中加入Ni原子后也与上述规律类似。而图6中，在铁中同时加入不同比例 $\mathrm { C r }$ 、Ni时，该扩散系数的减小速度比单独加入 $\mathrm { C r }$ 、Ni时要快，尤其是在高温区，这说明同时加入 $\mathrm { C r }$ 、Ni能够更好地抑制铁的腐蚀。

![](images/7fbd8a9d86a8e80d79b161e879694abcaef963da2f809929a12f2ab00e0ff368.jpg)  
Fig.5 The diffusion coefficient of the iron in the LBE after adding different proportion of Ni in the iron at different temperatures

图6不同温度下铁中加入不同比例 $\mathrm { C r }$ 、Ni时其在LBE 中的扩散系数

通过分析铁在LBE中的构型图 (图7)，可以发现加入金属 $\mathrm { C r }$ 后，扩散到铁中的LBE 原子比未加入时要少，而且随着加入比例的增加而逐渐减少，这说明加入金属 $\mathrm { C r }$ 能阻止铁原子与LBE 原子相互渗透从而减轻了铁的腐蚀。综上分析，本文得出金属Cr、Ni能有效保护铁的微观机制为：金属 $\mathrm { C r }$ 、Ni加入到铁后阻止了LBE 原子渗入铁材料中破坏其结构。

![](images/3720be6f9348b8ca7d71b6c8045497bdd4264e4ee62627ad4bd0aaf090edb099.jpg)  
Fig.6 The diffusion coefficient of the iron in the LBE after adding different proportion of Ni and $\mathrm { C r }$ in the iron at different temperatures

![](images/3c7f0e3bd1d55013a5ff8060fe6c056c6b160280587bd4db91d040ff7f1dd31b.jpg)  
图71173K时铁在加入不同比例 $\mathrm { C r }$ 时在LBE中的微观结构图 ( $\mathrm { C r }$ 原子为深黄色)Fig.7 The microstructure of the system after adding different proportion of $\mathrm { C r }$ in the iron at $1 1 7 3 \mathrm { ~ K ~ }$ (The color of $\mathrm { C r }$ atom isdeep yellow)

# 3结论

本文采用分子动力学方法研究了铁在LBE中的腐蚀问题，计算得到的铁在LBE中的扩散系数可以提供有效的参考。研究发现，铁在LBE 中被腐蚀的微观机制是由于铁原子与LBE 原子相互渗透，破坏了铁材料结构；然而，铁中掺入 $\mathrm { C r }$ 、Ni可以有效减轻铁的腐蚀，而且随着加入比例的增加腐蚀程度随之减小，其微观机理为金属 $\mathrm { C r }$ 、Ni加入到铁后阻止了LBE原子渗入铁材料中破坏其结构。

# 参考文献

[1]DoE.A Roadmap for Developing Accelerator Transmutation of Waste (ATW） Technology [R].Washington,USA: Department of Energy,1999   
[2]Li Ning，Woloshun K，Tcharnotskaria V,et al. Leadbismuth Eutectic(LBE)Materials Test Loop(MTL)Test Plan [R]. Los Alamos: Los Alamos National Laboratory, 2001   
[3] Weeks J R. Lead,Bismuth,Tin and Their Alloys as Nuclear Coolants [J].Nuclear Engineering and Design,1971, 15:363-372   
[4]Hata K,Hara K,Takahashi M.Experimental Studies on Steel Corrosion in Pb-Bi With Steam Injection [J]. Progress in Nuclear Energy,2005,47(1):596-603   
[5] Celino M,Conversano R,Rosato V.Atomistic Simulation ofLiquid Lead and Lead-Bismuth Eutectic [J]. Journal of Nuclear Materials,2002,301(1):64-69   
[6]Sapundjiev D,Van D S,Bogaerts W.Liquid Metal Corrosion of T91 and A316L Materials in Pb-Bi Eutectic at Temperatures $4 0 0 { - } 6 0 0 ^ { \circ } \mathrm { C }$ [J].Corrosion Science,2006, 48(3): 577-594   
[7]Maitre A，Francois M,Podor R,et al. Approach of the Corrosion Behavior of T91 Steel in Lead or Leadbismuth Liquid Bath [J].Materials Science Forum,2004, 461:1141-1148 [8] Rivai AK, Takahashi M.Corrosion Characteristics of Materials inPb-Bi Under Transient Temperature Conditions [J].Journal of Nuclear Materials,2010,398(1):139-145 [9] Arkundato A,Suud Z,Abdullah M.Corrosion Study of Fe in a Stagnant LiquidPb by Molecular Dynamics Methods [J].AIP Conference Proceedings,2010,1244(1):136-144   
[10] Wang Zhenghui,Chen Huan,Zhang Longyan．Atomistic Simulation of Self-Diffusion and Interfacial Diffusion of Liquid Lead [J]. Journal of Non-Crystalline Solids,2012, 358(21): 2906-2909   
[11] Maulana A,Su'ud Z,Hermawan K D.Simulation Study of Steels Corrosion Phenomenon in Liquid Lead-Bismuth Cooled Reactors Using Molecular Dynamics Methods [J]. Progress in Nuclear Energy,2008,50(2):616-620   
[12] Zhen S,Davies G J.Calculation of the Lennard-Jones nm Potential Energy Parameters for Metals [J].Physica Status Solidi (a),1983,78(2): 595-605   
[13] Lemmon EW,Jacobsen R T.Viscosity and Thermal Conductivity Equations for Nitrogen,Oxygen,Argon,and Air [J].International journal of thermophysics,2004,25(1): 21-69   
[14] Manly W D.Fundamentals of Liquid Metal Corrosion [J]. Corrosion,1956,12(7): 46-52   
[15]Banerjee S.Proceedings of the Fifth International Congress on Metallic Corrosion,Tokyo,Japan,May,1972. [M].Houston: National Association of Corrosion Engineers,1974:21-27