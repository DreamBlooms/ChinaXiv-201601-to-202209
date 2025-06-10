# 大口径射电望远镜轮轨滚动接触有限元分析

师洪强1,2，许谦 2.3,4，王娜 2.3,4，王兆军1（1.新疆大学物理科学与技术学院，乌鲁木齐，830046;  
2.中国科学院新疆天文台，乌鲁木齐，830011;  
3.中国科学院射电天文重点实验室，乌鲁木齐，830011;  
4.新疆射电天体物理重点实验室，乌鲁木齐，830011)

摘要：通过显式有限元法建立轮轨滚动接触模型，用于分析110米口径射电望远镜滚轮经过焊缝时的应力变化。建模时不仅考虑了焊缝处材料差异，同时还考虑轨道焊缝处表面不平度和摩擦系数的影响，分析了滚轮经过轨道焊缝时轮轨间作用力的瞬态响应。采用层级细分技术对轮轨模型进行前处理，经过静力学分析结果表明，模型求解精度较高。将该前处理模型用于瞬态分析发现，焊缝处表面不平度对轮轨间作用力影响较大，使轮轨间Mises 应力增加了约 $20 \%$ ，可能会对轨道长期可靠服役带来一定的隐患，因此需要定期对轨道的状态进行检测与维护，保障轨道的长期可靠服役特性。

关键词：射电望远镜；方位轨道；滚动接触；瞬态响应；有限元法中图分类号：P111.44; 文献标识码：A

# 0引言

中小口径精度要求不高的射电望远镜普遍采用拼接轨道技术，拼接轨道在滚轮经过接缝时易出现跳动以及应力集中，从而影响天线指向精度以及轨道使用寿命[1]。目前大口径、高精度射电望远镜轨道逐渐采用整体焊接技术，如美国GBT[2]、上海天马 $6 5 \mathrm { m } ^ { \left[ 3 \right] }$ 射电望远镜等。正在建设的新疆110米口径全向可动射电望远镜(QTT)[4]，方位轨道将采用整体焊接技术，由于采用窄槽坡口焊接技术，因此堆焊层需要用到3种不同的焊接材料[5]。焊接过程中的高温会引起材料内部结构性能变化，造成焊缝位置硬度和强度与母材的差异。由于轮轨接触力分布有大载荷、小集中的特点，天线滚轮在经过焊缝位置时，焊缝与母材的差异可能会引起轮轨接触力的突变。应力突变是引起疲劳磨损的主要原因之一，因此弄清滚轮经过焊缝时的应力变化尤为重要。

对于大型射电望远镜轨道而言，传统试验研究成本高昂，因此可采用仿真分析的方法进行研究[]。任懿等人[7]针对大型反射面天线轮轨接触问题，在不同仿真软件中进行对比分析，获得轮轨接触应力，但未涉及瞬态分析。JunejaG[8等人通过三维有限元分析，用移动载荷法模拟轮子滚动，分析GBT斜接缝轨道的力学行为以及耐磨板、基板接触界面的微动磨损，分析结果为轨道重新设计与改造提供参考。移动载荷法不能还原真实的轮轨接触状态，且材料差异带来的影响也很难考虑进去。因此需要采用完整的有限元模型才能更加真实、准确的反映轮轨接触的瞬态响应。

本研究采用有限元法将天线轨道焊缝真实焊接工艺考虑在内，建立QTT轮轨接触模型，使用层级细分技术对模型进行相应处理。在此基础上采用“面-面”赫兹接触算法求解接触耦合，进而通过显式时间积分法，获得轮轨间作用力在不同摩擦系数和轨道面形貌下的瞬态响应。研究结果为天线轨道的疲劳寿命分析和天线维护提供参考。

# 1轮轨接触应力计算

本研究建立的大型射电望远镜轮轨接触模型，由于接触斑的几何尺寸远小于轮轨几何特征尺寸，且不考虑天线滚轮的侧滑和蠕滑现象。因此轮轨间作用力可以使用赫兹接触理论进行计算[9]，通过理论计算与仿真结果进行对比，验证模型的准确性，为瞬态分析奠定基础。

根据Hertz接触理论有关弹性体接触斑的几何尺寸关系，轮轨之间的接触可看作是两个任意曲面弹性体的接触，它的接触斑呈椭圆形，其长轴半径 $a$ ，和短轴半径 $b$ 分别为：

$$
a = m \left\{ \frac { 3 \pi N \left( k _ { 1 } + k _ { 2 } \right) } { 4 { \left( A + B \right) } } \right\} ^ { 1 / 3 } , b = \mathrm { n } \left\{ \frac { 3 \pi N \left( k _ { 1 } + k _ { 2 } \right) } { 4 { \left( A + B \right) } } \right\} ^ { 1 / 3 }
$$

$N$ 是轮轨间的法向力； $\mathbf { \nabla } _ { m }$ 和 $n$ 与椭圆积分相关，一般表示为：

$$
\cos \theta = \frac { B - A } { A + B }
$$

m、 $n$ 、 $\theta$ 的关系可以通过查表获得。 $k _ { 1 }$ 和 $k _ { 2 }$ 为材料参数，其值表示为：

$$
k _ { 1 } = \frac { 1 - \nu _ { 1 } ^ { 2 } } { \pi E _ { 1 } } , k _ { 2 } = \frac { 1 - \nu _ { 2 } ^ { 2 } } { \pi E _ { 2 } }
$$

其中， $E _ { l } , \ E _ { 2 }$ 和 $\nu _ { I } , \nu _ { 2 }$ 分别为滚轮和轨道材料的弹性模量和泊松比。轮轨接触曲面初始间隙函数的常数 $A$ 和 $B$ 可由式（4）确定。

$$
A + B = \frac { 1 } { 2 } \left( \frac { 1 } { R _ { _ { 1 1 } } } + \frac { 1 } { R _ { _ { 1 2 } } } + \frac { 1 } { R _ { _ { 2 1 } } } + \frac { 1 } { R _ { _ { 2 2 } } } \right) , B - A = \frac { 1 } { 2 } \left( \frac { 1 } { R _ { _ { 1 1 } } } - \frac { 1 } { R _ { _ { 1 2 } } } + \frac { 1 } { R _ { _ { 2 1 } } } - \frac { 1 } { R _ { _ { 2 2 } } } \right)
$$

式中 $R _ { I I } , R _ { I 2 } , R _ { 2 I } , R _ { 2 2 }$ 分别为两个接触体的主曲率半径；求得接触斑长、短半轴 $a , \ b$ 之后，则接触斑的内应力分布即可表示为：

$$
P _ { z } \left( x , y \right) = \frac { 3 } { 2 } \frac { N } { \pi a b } \sqrt { 1 - \left( \frac { x } { a } \right) ^ { 2 } - \left( \frac { y } { b } \right) ^ { 2 } }
$$

则由式（5）可知，最大接触压应力 $q _ { 0 }$ 出现在接触斑中心处，其值为：

$$
q _ { 0 } = \frac { 3 N } { 2 \pi a b }
$$

由于接触位置多为压应力，轨道一般不会因此破坏，而如果剪应力超过容许值，会使得轨道内部发生塑性流动，更容易引起钢轨的破坏。最大剪应力发生在轮轨接触面以下的某一

深度，其值约为：

$$
2 \tau \approx 0 . 6 3 q _ { 0 } = 0 . 6 3 m _ { \mathrm { { 0 } } } \sqrt { \frac { P E ^ { 2 } } { R _ { w } ^ { 2 } } }
$$

接触面上的最大剪应力为：

$$
2 \tau _ { 1 } = n _ { 0 } q _ { 0 }
$$

式中 $m _ { \theta }$ ， $n _ { \theta }$ 与两接触体的主曲率半径有关，均可由查表得到 $[ 1 0 ]$ 。通过以上公式即可计算出天线轮轨接触力的大小和分布。

# 2轮轨接触模型构建

# 2.1模型建立

仿真模型基于QTT建立，天线座架共有4组滚轮，每组8个。取一个滚轮和两段轨道组成分析模型，如图1所示。轨道建模时考虑了焊接过渡层、填充层及表面焊接层。滚轮轴采用3维线性有限元应变梁单元表示，并使用多点约束单元将轮轴与天线滚轮进行耦合，不仅可以将整个天线载荷均匀施加在滚轮上，也可以实现滚轮的滚动，有效地简化了模型又不失准确性。

有限元模型的计算准确性高度依赖于网格划分精度，当接触斑区域网格尺寸为接触斑短半轴宽度的1/20时，可以得到精确的轮轨接触解，当网格尺寸为1/10时，可以满足大多数工程问题中的精度要求[I]。采用层级网格细分技术，对焊缝附近区域的轨道及滚轮进行网格细化，最小网格尺寸为 $1 . 1 \ \mathrm { m m }$ 。如图1所示，模型采用8节点6面体单元进行离散，焊缝位置采用共节点方式，以减少接触设置，提高计算效率。为了保证网格质量，所有网格的长宽比小于3.5，最终整个模型网格数量约79万，节点数82万，其中焊缝附近网格数量约占总体网格数量的 $91 \%$

![](images/f74ec86290195a4b5b5b23038caa9a634c93e826af2fb1e51d5a1806642bb577.jpg)  
图1模型及网格  
Fig.1 The model and grid

轨道材料为高质合金钢42CrMo，而焊缝位置表面需要较大硬度以保证其耐磨性和使用寿命，因此焊接坡口需要一层较“软”材料作为过渡，将轨道材料与表面堆焊层进行有效衔接。过渡层厚度约 $4 \mathrm { m m }$ ，由于目前有限元分析无法实现对材料硬度的表征，因此考虑通过采用不同的弹性模量来近似表征不同焊接工艺的熔敷金属硬度。文献[12]通过实验分析指出，越靠近焊缝位置，其材料弹性模量越小，焊缝中心位置弹性模量最小，约为母材的 $90 \%$ 。因此取过渡层及填充层的弹性模量约为轨道的 $90 \%$ ，表面堆焊层约为轨道的 $9 5 \%$ 。具体材料参数设置如表1所示。

表1材料参数Table1 Material parameter  

<html><body><table><tr><td>Parameter information</td><td>Elasticity modulus (GPa)</td><td>Poisson's ratio</td><td>Material density（kg/m³)</td></tr><tr><td>Rail and wheel</td><td>213</td><td></td><td></td></tr><tr><td>Filling weld</td><td>190</td><td>0.3</td><td>7850</td></tr><tr><td>Backing weld</td><td>190</td><td></td><td></td></tr><tr><td>Surface weld</td><td>200</td><td></td><td></td></tr></table></body></html>

# 2.2载荷与工况设置

考虑到天线的重量以及轨道的合理承载，将单轮载荷设为200吨，保证实际工况安全性。载荷均布施加于轮轴上，考虑轨道自重影响其底面设置为全约束，滚轮约束横向自由度以避免横向滑移。

工况一：当滚动速度为 $2 0 \mathrm { m m / s }$ ，摩擦系数分别为0.3、0.4、0.5时，分析当天线滚轮经过焊缝时，轮轨间作用力的瞬态响应。

工况二：当滚动速度为 $2 0 \mathrm { m m / s }$ ，摩擦系数为0.3，分析焊缝表面不平度分别为 $0 . 1 \mathrm { m m }$ ，$0 . 2 \mathrm { m m }$ 、 $0 . 3 ~ \mathrm { m m }$ 时，对轮轨间作用力的影响。

瞬态分析时，设定滚轮与轨道接触起始位置与焊缝轨道交界线之间为稳态过渡区，以保证滚轮进入焊缝区时初始激扰的能量被消耗[13]。通过试算，稳态过渡区取值为 $7 0 \mathrm { m m }$ 。

# 2.3时间步长确定

时间步长与数值分析误差分布有关，合理的时间步长可以保证数值分析稳定性和计算精度。时间步长的选取不能一次定论，应该对比三个相距一定时间间隔步长下的计算结果，若相对偏差较小，即可取中间那个步长的计算结果作为问题的合理解[14]。取三个时间步长分别计算2s内滚轮经过相同位移时，绘制轨道上同一位置的应力时变曲线，如图2所示。从图中可以看出，不同时间步长对分析结果影响较小，因此选取时间步长为0.025s进行瞬态分析。

![](images/c1b2edfc295c883f6c3aefebe54d35da4dfdc791d907b58ca4946c9170abd2a9.jpg)  
图2时间步长对结果的影响

# 3轮轨接触有限元分析

# 3.1静力学分析

![](images/5ba4b746a2cc247d7439189ad03afec2e7df14b059208e5d06a04c6ec863e36a.jpg)  
Fig.2 The effect of time step on the results

基于赫兹接触理论，考虑天线滚轮处于焊缝处的静态工况，设置静摩擦系数为0.5。通过有限元数值分析，静态轮轨接触总变形量为 $0 . 1 4 7 \mathrm { m m }$ ，轨道最大变形量为 $0 . 0 6 9 \mathrm { m m }$ ，轨道受力云图如图3所示。由图3(a)可知，天线滚轮与轨道间的Mises 应力最大值为 $3 6 3 \mathrm { M P a }$ 与理论值 $3 7 1 \mathrm { \ m P a }$ 误差仅为 $2 . 2 \%$ ，最大Mises应力出现在轨道表面下约 $4 \mathrm { m m }$ 处；由图3（b）可以看到轮轨接触斑呈椭圆形，接触斑宽度为 $1 3 \mathrm { m m }$ （理论值 $1 3 . 2 \mathrm { m m }$ )，与赫兹接触理论基本吻合，最大接触压力为 $4 8 6 \mathrm { M P a }$ （理论值 $4 8 9 \mathrm { M P a } \$ )，远小于轮轨材料42CrMo的屈服应力 $9 3 0 \mathrm { M P a }$ ，验证天线静态工况下的安全性；由图3（c）可以看到最大剪应力为117MPa（理论值 $1 1 5 \mathrm { M P a } ,$ )，但远小于轮轨材料的最大剪应力，且剪应力场出现在轨道表面下，可反映真实轮轨接触应力场。静力学分析验证了模型的准确性，可用于瞬态分析。

![](images/1fb42cdbab3a5a8d8cae25a9c364d040b54f30479ad5d2176c1e75acc08e9e76.jpg)  
图3（a）Mises应力云图；（b）接触压力云图；（c）最大剪应力云图

(c）The pattern for maximum shear stress

# 3.2瞬态分析

由于整个轮轨模型网格数量较大，瞬态分析计算量庞大，对计算机性能要求极高。基于模型中轮轨接触特点，采用减缩Z向模型比例以减小模型计算量来进行瞬态分析。分别选取Z向0.5、0.2、0.1的比例模型，其静力学计算结果与完整模型进行对比，结果如图4所示。从图中可以看出，随着Z向模型比例的减小，减缩模型结果与原比例模型结果间的误差逐渐增大，为了兼顾计算精度与计算量，最终选取Z向厚度为0.2的模型进行瞬态分析。

![](images/e7c5ca0c9572035de83e23e96f878cd5d7c94823d659acc02ae077bef96f9091.jpg)  
Fig.3（a）The pattern for Mises stress；（b）The pattern for contact pressure;   
图4Z向不同比例模型计算结果  
Fig.4 Calculation results of different scale models in Z direction

# 3.2.1摩擦系数影响分析

不同摩擦系数会引起滚轮与轨道间作用力的变化。摩擦系数分别取0.3、0.4、0.5与不考虑焊缝处材料影响的分析结果进行对比，其轮轨间作用力的时变曲线如图5所示。轮轨间Mises 应力出现两个快速变化的峰值，其原因是焊缝过渡层与轨道存在变形差，在滚轮接触到过渡层时，在轨道上出现应力集中，因此过渡层承受载荷快速减小。由于过渡层只有 $4 \mathrm { m m }$ 滚轮将迅速转过并抵达高硬度焊接区，应力集中又出现在表面焊接层。滚轮从轨道段进入焊缝过程中过渡层承受载荷最小，可保障焊缝承载区域的焊接成功率。整个仿真中Mises 应力最大变化量约 $2 2 \mathrm { M P a }$ ，该应力的突变在轨道长期服役过程中容易造成焊缝区域的疲劳。

不同摩擦系数对轮轨间作用力影响较小，如摩擦系数为0.3与摩擦系数为0.5之间的Mises应力差约为 $2 . 5 \mathrm { M P a }$ ，因此摩擦系数对轮轨间作用力的影响几乎可以忽略不计。摩擦系数主要影响轮轨之间的摩擦力。从图5（b）可以看出，随着摩擦系数的增大，轮轨间静、动摩擦应力都随之增大，且材料越“软”摩擦应力越大。考虑焊缝影响，滚轮在经过焊缝时，最大摩擦应力增加了 $71 \%$ ，也增加了焊缝位置长期服役过程出现疲劳磨损的可能性。大型轮轨式天线由于滚轮负载大、速度低，一般不会出现滑动摩擦和滚轮“打滑"现象，因此天线的日常维护可以通过涂抹润滑油来降低轮轨间摩擦系数，从而降低摩擦应力。

![](images/6a8251695335feac9136764808af0e2490635af812a287f4e2c0c5aa0b9db3a3.jpg)  
图5不同摩擦系数的影响。（a）Mises应力时变曲线；（b）摩擦应力时变曲线 Fig.5 The influence of different friction factors.（a）The time-varying curve ofMises stress; （b）The time-varying curve of frictional stress

# 3.2.2轨道表面不平度的影响

QTT 建成后整个轨道表面不平度峰峰值优于 $0 . 3 ~ \mathrm { m m }$ ，而轨道在制造及现场焊接装配过程中，不可避免会造成轨道表面的不平度。由于不平度的随机性和复杂性，使用文献[15]的方法，用正弦波曲线简化焊缝处表面不平度。以焊缝中心位置为原点，焊缝宽度为 $6 0 \mathrm { m m }$ 依照图6（a）所示的正弦波曲线改变焊缝位置处的节点坐标以实现有限元模型的修改。

在不同的表面不平度下，轮轨间作用力的时变曲线如图6（b）所示。从图中可以看出，滚轮在进入焊缝时，Mises应力出现快速的减小又增大的现象，是因为通过坐标改变轨道表面不平度时，曲面与平面过渡处相邻两个节点出现了高度差。表面不平度为 $0 . 1 \mathrm { m m }$ 时，该高度差约为 $0 . 0 0 5 \mathrm { m m }$ ，但造成应力的剧烈变化。侧面反映了重载天线轮轨接触时，局部微小缺陷（表面夹杂、气泡等）更容易对天线滚轮及轨道表面造成严重影响。随着轨道表面不平度的增加，Mises应力也随之增大。当轨道表面不平度为 $0 . 3 ~ \mathrm { m m }$ 时，最大Mises应力为$4 4 2 \mathrm { M P a }$ ，相比于平顺轨道其应力增加了约 $20 \%$ 。可以发现焊缝不平度对天线的影响较大，天线运行时，需要时常对天线轨道进行检测和维护，保证天线轨道表面清洁，及时处理磨耗或装配带来的轨道表面不平度，减小对天线轮轨的损伤。

![](images/30eed9667d32d78f87fccbb13132509ae1bc6a24266c146887bdc6c7aede9f3c.jpg)  
图6（a）轨道焊缝不平度；（b）不同轨道表面不平度下的应力时变曲线  
Fig.6（a）Therail welded joint flatness；（b）Time-varying stress curves in diferent track surface flatness

分析可知，摩擦系数对轮轨间作用力影响较小，而焊缝处材料差异和轨道表面不平度更容易引起天线轮轨间作用力变化，该应力的突变伴随着应力集中，对天线轨道的高周疲劳有着不良影响。

# 4结论

本文通过建立的QTT轮轨模型，考虑轨道焊缝位置对轮轨瞬态接触的影响，研究了接触参数和轨道面形貌对轮轨间作用力的影响，主要分析结果为：（1）采用层级细分技术对模型进行前处理，可以大大减小网格数量和计算成本，且模型具有较高求解精度。（2）考虑焊缝材料差异时，静态工况下轮轨接触总变形量为 $0 . 1 4 7 \mathrm { m m }$ ，与瞬态相比接触变形量相差较小，但滚轮经过焊缝时轮轨间Mises 应力发生剧烈变化，对轮轨长期有效服役带来不利影响。（3）不同摩擦系数对轮轨间作用力影响较小，主要影响轮轨间摩擦应力，且在滚轮经过焊缝时摩擦应力增大约 $71 \%$ 。对大载荷天线轮轨间作用力影响较大的是轮轨接触面形貌的改变，由于轮轨间作用力大载荷、小集中的特点，轨道表面微小不平度特征会带来应力较大变化，应保证天线轨道表面清洁，时常检测并及时处理轨道表面不平度。

# Finite Element Analysis of Wheel-on-track Rolling Contact for Large Aperture Radio Telescope

Shi Hongqiang1,2, Xu Qian2,3,4, Wang $\mathrm { N a } ^ { 2 , 3 , 4 }$ , Wang Zhaojunl (1.School of Physics and Technology,Xinjiang University,Urumqi 830046:

2.Xinjiang Astronomical Observatory, Chinese Academy of Sciences,Urumqi 830011;

3.KeyLaboratory of Radio Astronomy,Chinese Academy of Sciences,Urumqi 830011;

4.KeyLaboratory of XinjiangRadio Astrophysics,Urumqi 830011)

Abstract: Based on wheel-on-track roling contact model which established by explicit finite element method, the stress variation about the wheel of 110-meter aperture radio telescope passing through the welding joint is analyzed. When modeling,not only the material difference at the welding joint, but also the influence of the flatness and friction coefficient at the track welding joint were considered. According to the model, when the wheel passing through the welding joint, the transient response of the force between wheel and track is analyzed. The hierarchical subdivision technology is used to preprocess the wheel-on-track model, and the results of static analysis show that the model has high precision. The transient analysis results show that, the Mises stress was increased by about $20 \%$ due to the track flatness,which may bring some hidden danger to the track's long-term reliable service. Therefore，it is necessary to inspection and maintenance the status of the track regularly to ensure the long-term reliable service characteristics of the track.

Key words: Radio telescope; Azimuth track; Roling contact; Transient response; Finite element method

# 参考文献

[1] 温浩兴,许谦,王娜.南山 26 米射电望远镜轨道高差测量及其对指向精度的影响[J].天文研究与技术,2019,16(02):158-166. Wen Haoxing,Xu Qian, Wang Na. Measurement ofNSRT26m antenna track unevennessandinfluence on pointing accuracy[J]. Astronomical Research & Technology,2019,16(02): 158-166.   
[2] Symmes,Arthur,Anderson,etal.Improvingtheservicelifeof the0-meter greenbank telescopeazimuthtrack[J].Procedings of SPIE,2008,7012:701238.   
[3] 付丽,凌权宝，赵融冰，等 $\mathrm { T M } 6 5 \mathrm { m }$ 天线基础和轨道沉降及对天线指向的影响[J].红外与激光工程,2016,45(11):190-196. FuLi,Ling Quanbao,ZhaoRongbing,etal.SettlementsoffoundationandtrackofTM65manditsefectonantennapoiting[J]. Infrared and Laser Engineering,2016,45(11): 190-196.   
[4] 王娜.新疆奇台110米射电望远镜[J].中国科学:物理学 力学 天文学,2014,44(08):783-794. Wang Na.Xinjiang Qitai110mradio telescope[J].SCIENTIASNICAPhysica,Mechanica&Astronomica,2014,44(8):783-794.   
[5] 许红祥.QTT天线轨道施焊工艺及变形控制研究[D].哈尔滨工业大学,2018. Xu Hongxiang.Researchon QTTantenna track welding process and deformation control[D]. Harbin Instituteof Technology, 2018.   
[6] 赵聪,许谦,王娜,等.新疆奇台110米射电望远镜主焦点馈源换馈方案研究[J].天文研究与技术,2017,14(02):172-178. Zhao Cong,XuQian,Wang Na,etal.The prime focusreceiver positionerdesignof Xinjiang QiTai11Omradio telescope[J]. Astronomical Research & Technology,2017,14(02):172-178.   
[7] 任懿,郑元鹏.大型反射面天线轮轨接触问题分析[J].无线电工程,2013,43(07):45-48. RenYi,ZhengYuanpeng.Analysisofwhel-railcontactproblemoflargerelectorantea[J].adioEngneering,,4(0): 45-48.   
[8] Juneja G,KanFWAntebiJ.Updateonslipandwearinmulti-layerazimuthtracksystems[J].ProceedingsofSE,6,6: 627318.   
[9] 马昌红,史生良,吴亚平.轮轨接触应力的有限元分析[J].石家庄铁道学院学报,2006(03):32-35. MaChanghong,Shi Shengliang,Wu Yaping.TheFEManalysisof the whel-railcontactstress[J].Journalof Shijiazhuang Railway Institute.2006(03): 32-35.   
[10]刘伟.轮轨接触斑测试及接触应力分析[D].北京交通大学,2014. Liu Wei.The patch test and stress analysis of wheel/rail contact [D]. Beijing Jiaotong University,2014.   
[11]ZhaoXin,LiZil.Tesoutionoffrictionalwl-railollngontactwithaDransietfiteelementmodel:Vidationan error analysis[J].Wear,2010,271(1): 444-452.   
[12]赵振洋,杜家政,卢立晗.超声波法测定铝合金焊接板的弹性模量[C].//北京力学会第 21届学术年会暨北京振动工程学会第 22 届学术年会论文集.2015:589-590. Zhao Zhenyang,DuJiazheng,LuLihan.Measurementofelastic modulusof aluminum allywelded plate byultrasonicmethod [C].//Proceedingsof the21st Annual Conferenceof BSTAMandthe2nd AnnualConferenceof Beijing Societyof Vibration Engineering.2015: 589-590.   
[13]贾昕昱.基于轮轨瞬态滚动接触模型的钢轨接触疲劳伤损研究[D].中国铁道科学研究院,2020. JiaXinyu.Researchoncontactfatiguedamageofrailbasedonwheel-rail transientrollingcontact model[DJ.ChinaAcademyof Railway Sciences,2020.   
[14]翟婉明.车辆-轨道耦合动力学[M].第二版.北京:中国铁道出版社,2002:122-124. Zhai Wanming.Vehicle-tarck coupling dynamics [M].2ndEd.Beijing: China Railway Publishing House,20o2:12-124.   
[15]于淼.高速铁路轨道-车辆系统高频瞬态仿真及波磨机理研究[D].中国铁道科学研究院,2019. YuMiao.Transient simulation for high-speed track/vehicle systemand studyonrail corugation[D].ChinaAcademyof Railway Sciences,2019.