# 三次多项式温度分布液相模型在液滴蒸发中的应用

李玮玉1周致富¹　陈 斌1王国祥1,2 应朝霞

1．西安交通大学动力工程多相流国家重点实验室，西安710049;2．美国 Akron 大学机械工程系，Akron Ohio 44325-3903;3．西安交通大学医学院第二附属医院皮肤科，西安710049)

摘要三次多项式温度分布模型反映了液滴内部基于希尔球涡的实际流动，可以较为准确地预测单个液滴蒸发。鉴于三次多项式温度分布模型在预测单个液滴蒸发的准确高效性，本文以 $\boldsymbol { n }$ -Decane油滴蒸发为例，采用三次多项式模型研究了通过改变初温和初始气流速度来改变初始雷诺数对液滴蒸发的影响，结果表明通过改变气流速度来改变雷诺数的情况，不同雷诺数下液滴蒸发率与内部温度分布存在较大差异；以 $n$ -Decane, $n$ -Heptane和 $\mathbf { \xi } _ { n } .$ -Dodecane三种不同黏度的油滴蒸发为例，对比了液滴黏度对蒸发的影响，发现不同黏度液滴的蒸发率与内部温度分布差异较大，黏度越小，蒸发率越快；在液滴蒸发的初始阶段，内部温度梯度较大。

关键词液滴蒸发；希尔球涡；三次多项式模型；液滴黏度中图分类号：TK124 文献标识码：A 文章编号:0253-231X(2017)05-1012-05

# Application of the ${ \bf 3 ^ { \mathrm { { r d } } } }$ -order Polynomial TeMperature Profile Liquid Model in Predicting Droplet Vaporizing

LI Wei-Yu1 ZHOU Zhi-Fu1 ChehBm1 WANG Guo-Xiang $^ { 1 , 2 }$ （ YING Zhao-Xia $^ 3$

(1.State Key Laboratoryof MultiphaseFlPower Enginering,Xi'an Jiaotong University，Xi'an 710049,China; 2.Department of Mechancal Engineering,University of Akron，Ohio 44325-3903,USA; .Laser Treatment Center,DepartmenermatologyMedical School, Xi'anJiaotong University，Xi'an10049,hina)

AbstractA $3 ^ { \mathrm { r d } }$ -order Polynomial temperature profile liquid model for droplet evaporation was proposed recently, in Which the enhancement of heat transport by internal circulation was correctly reflected due to the introduction of Hil's vortex. Thus it could pfedict droplet temperature and evaporation rate well. Based on this well-built liquid evaporationmodel, this paper investigated the effect of initial parameters including initial droplet temperature and ambient gas velocity on droplet evaporation rate. It was found that the initial gas velocity had a larger efect on droplet evaporation rate and temperature distribution than the initial droplet temperature. Further,several kinds of liquid droplets ( $n$ -Decane, $n$ -Heptane and $n$ -Dodecane） were employed to study liquid viscosity on droplet evaporation. The result indicated that a smallr Viscosity of liquid droplet could lead to a larger droplet evaporation rate and a greater temperaturegradient inside droplet in the transient evaporation period.

Key wordsdroplet evaporation; hill's vortex; $3 ^ { \mathrm { r d } }$ -order polynomial temperature profile model; liquid viscosity

# 0引言

液滴蒸发涉及液滴与周围环境的传热、传质以及动量交换，是影响整个喷雾液滴群喷雾动力学与热特性行为的重要因素，同时在工业应用中也非常重要。例如，液滴蒸发对内燃机燃油的燃烧效率，激光皮肤手术中制冷剂喷雾冷却在皮肤表面的冷却效率以及冷却塔的换热效果等均具有重要影响[1-5]。因此，建立准确并且计算高效的液滴蒸发模型具有重要理论及实际意义，但是既要保证模型的准确性又要保证计算的高效性却往往是一个相互矛盾的问题。最近本课题组提出一种基于液滴内部温度服从三次多项式分布的液相模型，考虑了基于希尔球涡的实际流动对液滴内部传热与蒸发的影响，即当气流流过液滴表面，作用于液滴表面的剪切力会使液滴产生一个内部流动，从而加强了液滴内部的传热[6]。与集总参数模型和二次多项式温度分布模型相比，新的三次多项式模型可以更为准确地反映液滴内部的实际流动情况与温度梯度[7,8]；与导热模型和有效导热模型相比，三次模型预测结果也更为准确，且计算简单，效率更高[7]。三次多项式温度分布模型平衡了针对单个液滴蒸发的液相模型的准确性与高效性，适合被广泛地应用于喷雾CFD 计算中。

鉴于三次多项式温度分布模型在预测液滴蒸发过程中的优越性，本文将采用三次多项式温度分布模型对单个液滴蒸发过程进行研究。以 $n$ -Decane油滴蒸发为例，采用三次多项式模型研究初始条件对液滴蒸发的影响，分析通过改变初温和初始气流速度来改变初始雷诺数对液滴蒸发的影响。由于液滴黏度对其流动具有重要影响，本文以 $n$ -Decane，nHeptane和 $n$ -Dodecane三种不同黏度的油滴蒸发为例，应用新模型对比研究了液滴黏度对蒸发及内部传热的影响。

# 1液滴蒸发液相模型

如果不考虑液滴内部温度梯度，把液滴整体当作为一个温度处理，即集总参数模型，液滴能量平衡方程为： >

$$
h ( T _ { \mathrm { g } } - T _ { \mathrm { s } } ) = \frac { 1 } { 3 } r _ { \mathrm { s } } \rho \big \vert \underline { { c _ { p } } } , \vert \frac { \mathrm { d } \bar { T } } { \mathrm { d } t } - \rho _ { \mathrm { l } } L \dot { r } _ { \mathrm { s } }
$$

式中， $h$ ， $T _ { \mathrm { g } }$ 与 $ { T _ { \mathrm { s } } }$ 分别表示对流换热系数，环境气体温度和液滴表面温度。 $r _ { \mathrm { s } }$ 为液滴半径, $\rho _ { \mathrm { l } }$ ， $c _ { p , 1 }$ ， $L$ 和 $\dot { r } _ { \mathrm { s } }$ 分别代表液体密度，液体比热容，蒸发潜热和液滴半径变化率。

虽然集总参数模型计算效率高，但是不能反映液滴内部的温度分布。而近来由本课题组提出的基于三次多项式温度分布和液滴内部基于希尔球涡的实际流动的液相模型不仅可以考虑液滴内部温度分布[6,9-11]，并且计算简单高效。三次模型的基本思路是用一个三次多项式函数来近似表示液滴内部温度分布，用平均温度来代替集总参数模型当中的液滴整体温度，由平均温度 $\bar { T }$ 表示能量方程为：

$$
{ \frac { \mathrm { d } { \bar { T } } } { \mathrm { d } t } } = { \frac { 3 \dot { r } _ { \mathrm { s } } } { r _ { \mathrm { s } } } } \left( T _ { \mathrm { s } } - { \bar { T } } + { \frac { L } { c _ { p , 1 } } } \right) - { \frac { 3 h } { r _ { \mathrm { s } } \rho _ { 1 } c _ { p , 1 } } } ( T _ { \mathrm { s } } - T _ { \mathrm { g } } )
$$

根据液滴表面能量平衡、液滴中心温度对称、希尔涡滞止条件以及平均温度定义式四项条件，可以求得三次多项式温度分布模型的表面温度 $T _ { \mathrm { s } }$ 与平均温度的关系式可以表示为 (详细推导可参考文献[6]):

$$
T _ { s } = \frac { \bar { T } + 0 . 0 4 3 \lambda _ { \mathrm { g l } } N u T _ { \mathrm { g } } } { 1 + 0 . 0 4 3 \lambda _ { \mathrm { g l } } N u } +
$$

$$
0 . 0 8 6 \frac { \rho _ { \mathrm { l } } L \dot { r } _ { \mathrm { s } } r _ { \mathrm { s } } } { \lambda _ { \mathrm { l } } \left( 1 + 0 . 0 4 3 \lambda _ { \mathrm { g l } } N u \right) }
$$

式中， $\lambda _ { \mathrm { g l } }$ 为液滴表面混合气体导热系数与液体导热系数之比。式(2)、(3)给出了液滴蒸发过程中基于希尔球涡理论的三次多项式温度分布液相模型的完整表达。

此外，关于决定液滴表面与环境气体间传热传质的Nu和Sh气相模型，本文中选用文献[12]提出的适合于不同蒸发率下N-G-R-M气相模型。

# 2三次模型计算液滴蒸发结果与讨论

# 2.1初始雷诺数对液滴蒸发的影响

鉴余兰次多项式温度分布模型在预测液滴蒸发过程中的优越性，本节采用三次模型研究初始条件对液滴加热蒸发的影响。Wong与Lin的实验结果表明，在雷诺数 $0 \mathrm { \sim } 1 0 0$ 的范围内，雷诺数的改变对液滴蒸发的影响很小，但是只考虑了改变初始温度来改变雷诺数的情况[13]。而实际上雷诺数随液滴初始直径、周围环境气体流速和液滴表面混合气体的热物性的变化而改变，并且液滴内部流动与传热受周围气流速度的影响更大。因此为了进一步研究初始雷诺数对液滴蒸发的影响，本文分别考虑了通过改变初始温度和周围环境气体流速来改变初始雷诺数的情况，并对液滴蒸发率和内部温度分布随时间变化进行了比较。在2.1.1中，固定环境气体流速为1m/sx雷诺数为17，60和 100时所对应的初温分别为315K,307K和 $3 0 1 \mathrm { K }$ 。在2.1.2中，固定液滴初始温度为315K，雷诺数为0，17，60和100 时所对应的环境气体速度分别为 $0 ~ \mathrm { m / s }$ ， $\mathrm { 1 ~ m / s }$ ， $3 . 8 ~ \mathrm { m / s }$ 和$6 . 3 ~ \mathrm { m / s }$ 。在两种情况下，液滴初始直径都为 $2 ~ \mathrm { m m }$ 5周围气体温度为 $1 0 0 0 \mathrm { K }$ 。

# 2.1.1通过改变初始温度改变初始雷诺数

图1为三次模型计算 $n$ -Decane油滴在不同初始温度下液滴直径随时间的变化。当液滴初始温度较高时， $n$ -Decane液滴的蒸发率也较高，但在不同初始雷诺数下计算的液滴蒸发率没有较大的差异。初始温度的增加导致雷诺数 $R e$ 与施密特数 $\mathit { S c }$ 的减小，从而导致舍伍德数 $S h$ 的减小。同时，扩散系数减小。因此，在雷诺数 $R e { \approx } 0 ( 1 0 ) { \sim } 0 ( 1 0 0 )$ 的范围内,液滴蒸发率没有明显的差异，与Wong和Lin之前的结论一致。图2为三次模型计算 $n$ -Decane 油滴在不同时刻不同初始温度下内部温度分布情况。液滴蒸发的初始阶段，在雷诺数 $R e { \approx } 0 ( 1 0 ) { \sim } \mathrm { O } ( 1 0 0 )$ 的范围内，不同雷诺数下计算得到的液滴内部温度分布有一定的差异，但是随着时间增加，差异逐渐减小。

![](images/7579f797702fc1b28a9ca644a3bf35b47b43f9432c560bc60e9d1ecf7b7ed11c.jpg)  
图1 三次模型计算 $\mathbf { \Psi } _ { n }$ -Decane 油滴在不同初始温度下液滴直径随时间的变化Fig.1 Variation of $n$ -Decane droplet diameter versus time atdifferent initial temperature

![](images/5b781c8eec192bc0c8107c04962abd88369c44c575c19f70bac7331d038d9ac6.jpg)  
图2三次模型计算 $n$ -Decane 油滴在不同初始温度下不同时刻（ $\mathrm { \Delta \ t { = } 0 . 4 \ s }$ 和 $\scriptstyle t = 2 . 4$ s）内部温度分布情况Fig.2 Internal temperature distribution of $n$ with varied initial temperature at different time0 $\scriptstyle \cdot = 0 . 4$ sand $\scriptstyle t = 2 . 4$ s)

# 2.1.2通过改变气流速度改变初始雷诺数

图3为不同气流速度时三次模型计算 $n$ -Decane油滴的直径随时间变化。可以看到，通过改变气流速度来改变初始雷诺数的情况与通过改变初始温度来改变初始雷诺数的情况有较大区别。不同初始雷诺数下液滴蒸发率存在较大差异。初始温度固定，气流速度越大，初始雷诺数越大，液滴蒸发越快。根据希尔球涡理论，流过液滴表面的气体流速越大，作用于液滴表面的剪切力所产生的内部流动得到加强，因而促进了液滴蒸发。当气流速度为零时 $\mathrm { \Gamma } ( v = 0 \mathrm { m / s } )$ ）,即液滴与环境气体相对静止时，液滴蒸发很慢。可以得出，液滴内部流动对液滴加热与蒸发有很大的影响，而液滴内部流动受环境气流速度影响较大。

![](images/ec189c8d1030d037318ce275684de37bb70c7061d9d8b7a2459b7a696d77f548.jpg)  
图 不同气流速度时三次模型计算 $\boldsymbol { n }$ -Decane 油滴的直径随时间变化5.3Variation of $n$ -Decane droplet diameter versus time atdifferent ambient gas velocity

图4为三次模型计算 $n$ -Decane油滴在不同气流速度下不同时刻内部温度分布情况。在液滴蒸发的初始阶段！ $( t = 0 . 4 ~ \mathrm { s } )$ )，当初始雷诺数为17，60和100的情况下（ $\mathit { \Delta } _ { v } = 1 \mathrm { m } / \mathrm { s }$ ， $3 . 8 ~ \mathrm { m / s }$ ， $6 . 3 ~ \mathrm { m / s ) }$ ， $n$ -Decane液滴内部具有较大的温度梯度。由于外界气流作用于液滴表面的剪切力所产生的内部流动加强了液滴表面向中心的传热，因此气流速度越大，液滴中心的加热越明显，表面温度与中心温度都明显高于他们中间滞业点温度，因此液滴内部的温度梯度越大。随着时间的增加，内部温度梯度减小，气流速度越大，内部温度越早趋于均匀分布。可以看出，在 $\scriptstyle t = 2 . 4$ S时，对于雷诺数为60，1 $1 0 0 ( v = 3 . 8 ~ \mathrm { m / s }$ ， $6 . 3 ~ \mathrm { m / s } \mathrm { \AA }$ 的情况，液滴达到稳态蒸发阶段。而对于雷诺数为 $0 ( v$ $= 0 ~ \mathrm { m / s ) }$ 的情况，液滴整体温度较低，并且在液滴蒸发的整个过程中，内部温度总是趋于均匀分布，这是由于当液滴与环境气体相对静止时，液滴不存在基于希尔球涡的内部流动。

# 2.2液滴黏度对蒸发的影响

基于希尔球涡理论的三次多项式温度分布模型考虑了液滴内部温度分布梯度，反映了液滴内部的实际流动情况，当气流流过液滴表面，作用于液滴表面的剪切力会使液滴产生一个内部流动，从而加强了液滴内部的传热过程。对于不同种类的油滴，黏度的不同会对液滴内部流动情况产生影响，因此本节采用三次多项式模型并选取了黏度不同的三种油滴 ( $\stackrel { \cdot } { n }$ -Heptane， $n$ -Decane和 $n$

Dodecane）来研究液滴黏度对蒸发的影响。其中n-heptane 液滴的黏度为 $7 . 5 6 \times 1 0 ^ { - 4 } \mu \mathrm { P a } { \cdot } \mathrm { s } .$ ，沸点温度为$9 8 . 4 ^ { \circ } \mathrm { C }$ ; $n$ -Decane 液滴的黏度为 $1 . 2 8 \times 1 0 ^ { - 3 }$ （20 $\mu \mathrm { P a } { \cdot } \mathrm { s }$ ，沸点温度为 $1 7 4 ^ { \circ } \mathrm { C }$ ； $n$ -Dodecane液滴的黏度为$4 . 2 2 \times 1 0 ^ { - 2 }$ （ $\mu \mathrm { P a } { \cdot } \mathrm { s }$ ，沸点温度为 $2 1 5 . 9 ^ { \circ } \mathrm { C }$ 。计算中，周围气体温度为 $7 4 1 \mathrm { ~ K ~ }$ ，压强为 $0 . 1 \ \mathrm { M P a }$ ，液滴初始温度为 $3 0 0 ~ \mathrm { K }$ ，液滴初始直径为 $0 . 6 \ \mathrm { m m }$ 。

![](images/6d425d6853d562094d613db484e804f8355d4b938033856de5aaafa4d855ae0c.jpg)  
图4三次模型计算 $\mathbf { \Omega } _ { n }$ -Decane油滴在不同气流速度下不同时刻0 $\mathrm { \Delta _ { \ t = 0 . 4 \ \mathrm { s } } }$ ， $\scriptstyle t = 2 . 4$ s）内部温度分布情况

图5为雷诺数为17时亚次模型计算 $n$ -Heptane,$n$ -Decane和 $n$ -Dodecane油滴的蒸发率，内部温度分布和表面温度随时间变化。与其他两种液滴相比, $n \mathrm { . }$ Dodecane液滴的蒸发率最低，这是由于 $n$ -Dodecane较高的液滴黏度造成的。液滴黏度越大，对内部流动的阻碍就越大，从而减弱了液滴热量传递，导致蒸发率偏小。当雷诺数为17时，在 $t / d _ { 0 } ^ { 2 } = 0 . 1$ 的时刻，可以明显看到三种液滴内部存在温度梯度，并且由于高黏度液滴阻碍内部涡旋流动，所以当液滴黏度越小，液滴内部流动越强，对中心温度的加热促进作用越明显，因此内部温度梯度越大。在 $t / d _ { 0 } ^ { 2 } = 1$ 的时刻，由于 $n$ -Heptane油滴已达到稳态蒸发阶段，内部温度分布趋于均匀。而 $n$ -Decane 油滴和 $n$ -Dodecane油滴内部仍然存在一定的温度梯度。从图5(c）中可知，在液滴蒸发的初始阶段， $n$ -Heptane 油滴由于黏度最小，表面温度上升最快， $n$ -Decane 油滴与 $n$ （2Dodecane 油滴的表面温度上升速率相近， $n$ -Heptane油滴大约 $0 . 2 \mathrm { ~ s ~ }$ 达到稳态温度， $n$ -Decane 油滴大约1.5s达到稳态温度，而 $n$ -Dodecane达到稳态温度所需时间最久，大约 $2 . 5 ~ \mathrm { s } .$ 。三种油滴最后达到的稳态温度的大小关系与它们的沸点温度的大小关系相一致。

![](images/80d0c07277af3b9f30120448f1d0d63915eaa006dec25f127de1691496b0de4f.jpg)  
Fig.4 Internal temperature distribution of $\mathbf { \Omega } _ { n }$ Deane droplet exposed to varied gas velocity at times (tQ.s and $\scriptstyle t = 2 . 4 :$   
图5三次模型计算 $\boldsymbol { n }$ -Heptane, $n$ -Decane和 $\boldsymbol { n }$ -Dodecane 油滴 的蒸发率、内部温度分布和表面温度随时间变化 $R e _ { 0 } { = } 1 7$ 0 Fig.5 Evaporation characteristics of $n$ -Heptane, $^ n$ -Decane and $n$ -Dodecanedroplets ( $R e _ { 0 } { = } 1 7$ 1

# 3结论

本文采用基于希尔球涡理论的三次多项式温度分布液相模型针对喷雾过程中的单个液滴蒸发过程开展理论研究。首先以 $n$ -Decane油滴蒸发为例，分析了分别通过改变液滴初始温度与外界气流速度来改变初始雷诺数对液滴加热与蒸发的影响，结果表明，当通过改变初始温度来改变初始雷诺数时，在不同雷诺数下液滴蒸发率与内部温度分布情况相近;而通过改变气流速度来改变初始雷诺数对液滴蒸发率与温度分布有显著的影响，气流速度的增加引起内部流动的加强，导致液滴蒸发变快，在蒸发的初始阶段内部温度梯度较为明显。接着以 $n$ -Decane，nHeptane和 $n$ -Dodecane三种不同黏度的油滴蒸发为例，对比了不同黏度液滴的蒸发率与温度分布的差异，液滴黏度的增大导致了内部流动和传热的减弱，因此液滴黏度越大，蒸发越慢，在液滴蒸发的初始阶段内部温度分布梯度越不明显。因此，三次多项式温度分布模型在对单个液滴蒸发的计算中体现出了实际的内部流动对液滴蒸发与加热的促进作用。

# 参考文献

[1] Zhou ZF,Chen B,Wang R,et al.Comparative Invs tigation on the Spray Characteristics and Heat Transfer Dynamics of Pulsed Spray Cooling With Volatile Cryogens [J]. Experimental Thermal and FluidSeience, 2017, 82:189-197 N   
[2] Zhifu Z,Weitao W, Bin C,et al. AnExperimental Study on the Spray and Thermal Characteristics of R134a Twophase Flashing Spray [J]. International Journal of Heat and Mass Transfer,2012,55(15):4460-4468   
[3] Zhou Z,Chen B,Wang R,et al.Coupling Effect of Hypobaric Pressure and Spray Distance on Heat Transfer Dynamics of R134a Pulsed Flashing Spray Cooling [J]. Experimental Thermal and Fluid Science,2016,70:96- 104 [4] Zhou Z F,Xu T Y,Chen B.Algorithms for the Estimation of Transient Surface heat Flux During Ultra-fast Surface Cooling [J].International Journal of Heat and Mass Transfer,2016,100:1-10   
[5] Zhou Z, Chen B,Wang Y,et al.An Experimental Study onPulsed Spray CoolingwithRefrigerant R-4O4a inLaser Surgery [J].Applied Thermal Engineering，20l2,39(4): 29-36   
[6] Zhou ZF,Li WY,Chen B,et al.A 3rd-order Polynomial Temperature Profile Model for the Heating and Evaporation of Moving Droplets [J].Applied Thermal Engineering, 2017,110:162-170 [7] Sirignano W A.Fluid Dynamics and Transport of Droplets and Sprays [M].Cambridge:Cambridge University Press, 1999   
[8] Dombrovsky L A,Sazhin S S.A Parabolic Temperature Profile Model for Heating of Droplets [J]. J Heat Trans-T ASME;2003,125 (3): 535-537   
[9]Abramzon B, Sirignano W A. Droplet Vaporization Model for Spray Combustion Calculations [J].Int J Heat Mass Tran,1989,32 (9):1605-1618   
[10] Tong A Y, Sirignano W A.Multicomponent Droplet Vaporization in a High Temperature Gas [J].Combustion and Flame.1986,66(3): 221-35   
[11]Prakash S,Sirignano W A.Liquid Fuel Droplet Heating With Internal Circulation [J].International Journal of Heat and Mass Transfer.1978,21(7):885-95   
[12] Zhifu Z,Guoxiang W,Bin C,et al. Evaluation of Evaporation Models for Single Moving Droplet with a High Evaporation Rate [J]. Powder Technology, 2013,240:95- 102   
[13]Wong S C.Lin A C.Internal Temperature Distributions of Droplets Vaporizing in High-temperature Convective Flows [J]. Journal of Fluid Mechanics,1992, 237: 671-687