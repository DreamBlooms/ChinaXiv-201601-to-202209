# 跨音透平中激波与边界层、尾迹干涉机理研究

卞修涛林敦苏欣荣袁新(清华大学热科学与动力工程教育部重点实验室，北京100084)

摘要高负荷跨音透平导叶中，流动过程十分复杂，DDES 方法在该条件下对流动细节地捕捉具有特殊优势。本文采用自主开发的 DDES 程序，获得可靠而精确的计算结果，研究跨音叶片内部的流动机理。根据不同区域的流动现象，作者分别研究叶片吸力面处，激波和边界层的相互作用；叶片尾流区，激波和尾迹的相互作用。并对这些区域进行熵生成情况分析，为后续跨音透平中的损失减小提供理论基础。

关键词DDES；跨音透平导叶；激波；边界层；尾迹中图分类号：TK472 文献标识码：A 文章编号：0253-231X(2017)05-0965-05

# Study on Interaction Mechanism of Shock Wave and Boundary Layer, Wake ir Transonic Turbine

BIAN Xiu-Tao LIN Dun SU X-Rong YUAN Xin E (Key Laboratory for Thermal Science and Power Engmeering of Ministry of Education,Tsinghua University，Beijing l00084,China)

Abstract In the high load transonic turbingide vanes, the flow is extremely complex and DDES has special advantages in capturing thedetails of fow. In this paper, the DDES program with a well-proved in-house code is usedtobtain reliable and accurate results,and the internal flow mechanism of transonic bladessstudied. According to the fow phenomena in different areas, the author studies the interacti@hof shock wave and boundary layer at the blade suction surface, and the interaction of shock wave and wake at wake region of the blade. And the entropy generation of these areas is analyzedwhich provides the theoretical basis of the loss reduction in transonic turbine. Key wordsDDES; transonic turbine guide vane; shock wave; boundary layer; wake

# 0引言

燃气轮机负荷正朝着越来越高的方向发展，膨胀比逐渐增大，在透平级数不变的条件下，这势必会导致单级负荷的增加，甚至会在通道内出现跨音和超音流动。通道中激波诱导的边界层分离以及叶片尾部的脱落涡等一直是影响效率提高的主要因素；采用数值模拟的方式，可以在降低实验成本的同时，获取更多的流场信息，这对燃机内部流动的物理分析十分重要。

对于燃机中复杂的湍流流动，LES 能够得到比RANS更精细的模拟结果，而RANS消耗的计算资源远小于LES。为此，1997年 Spalart 等[1] 提出了将RANS 和 LES 混合的 DES(Detached Eddy Sim-ulation）方法，在保证精度的同时，降低对计算资源的需求。2006年，Spalart 等[2]修改交界处混合方法的判定准则，在近壁区延迟LES模拟，被称为延迟脱体涡模拟 DDES(Delayed DES)，修正了 DES97 中应力模化不足的问题，使 DDES 能够和实验更好地吻合。因此，在激波处，边界层分离区，尾迹涡脱落等复杂流动区域采用 DDES 可以在获得精细流场的条件下，减小计算量，适合跨音导叶内部机理研究。

本文使用完全自主开发的多块并行求解器[3],采用多块并行计算以增大计算规模，利用双时间步法以达到透平流动中非定常求解要求；对激波，边界层和尾迹等复杂流动区域，程序采用耗散项自适应函数[4]，提高计算精度，获得较好结果。

# 1研究对象及方法

# 1.1求解域及网格

本文计算几何模型选取的是加拿大国家研究委员会（CNRC）测试使用的高负荷透平进口导叶[5],计算工况为跨音工况，可用于研究激波和边界层以及尾迹的相互作用，为除去上下端壁对流动的干扰，选取导叶中截面几何进行模拟，为进一步简化，选择平面叶栅的流动状况进行讨论，叶型表面设置为绝热壁面。主要数据由表1给出。选取的计算域由图1给出，入口距叶片前缘选取0.72个弦长，出口距叶片尾缘选取1.5个弦长，周向长度选取一个栅距，展向计算区域高度选定 $1 0 ~ \mathrm { m m }$ ，沿展向和周向均设置为周期性条件。

Table 1 The parameters of the blade   

<html><body><table><tr><td>弦长/mm</td><td>轴向弦长/mm</td><td>栅距/mm</td><td>展长/mm</td></tr><tr><td>204</td><td>84.7</td><td>147.8</td><td>112.8</td></tr></table></body></html>

![](images/3625040882dc4291ce7df0b6fd8e4c8912913273c876aad9a48985243df46f0f.jpg)  
图2尾缘网格

# 2结果分析

![](images/5622a7b6e9a64198264970364470caaaf2d7d51be40a07eef6394f26696044e5.jpg)  
图1计算域Fig.1 Computation domain

将叶型几何数据导入NUMECA中，利用Auto-Grid5生成满足要求的计算区域，再导入IGG中进行分块，共计95块。为保证计算的精度，全局选用结构化网格，且在网格数设置时，保证计算过程中可以采用多重网格方法进行加速收敛；加密后，网格总数为 $1 . 4 \times 1 0 ^ { 7 }$ 。叶片尾缘采用圆弧拟合，保证尾缘区域的光滑性，尾缘部分网格如图2所示。在计算中，时间步长选取 $1 0 ^ { - 6 }$ s，每个物理时间步迭代结束的条件为内迭代30步或残差下降4个量级。

# 1.2边界条件

跨音计算工况，出口马赫数选取1.16，其他进出口参数如表2所示：

# 表2进出口参数

表1叶型参数  
Table 2 Inlet and outlet parameters   

<html><body><table><tr><td>进口总温/K</td><td>进口总压/Pa</td><td>膨胀比</td><td>来流攻角/()</td></tr><tr><td>293</td><td>101300</td><td>2.3</td><td>-10</td></tr></table></body></html>

# 2.1计算结果与实验数据对比

不开算3.5个通过周期后，取叶片尾缘监测点压分随时间的变化做傅里叶变换，做功率谱密度分析为图3，峰值处频率为 $2 5 . 9 2 ~ \mathrm { k H z }$ ，满足文献实验给定[6]的涡脱落频率参考范围 $2 4 { \sim } 2 6 . 5 \mathrm { k H z }$ 。

![](images/bc8fba1fa05366e0079a72f5c8b43de5d4bd4e81938e38dd02ec6b5c6aadf7f7.jpg)  
Fig.2 Trailing edge mesh   
图3功率谱密度图 Fig.3 Power spectral density

# 2.2弱激波分析

做出瞬时密度梯度图(DGM，DensityGradientMagnitude)，采用流场中最大密度梯度进行单位化，得图4，其中叶片尾缘，两道主斜激波之前，还存在两道唇部激波，局部放大后如图5中左图所示，唇部激波强度较弱，产生原因为尾缘圆弧直径稍大于尾部厚度。

此外，图4瞬时密度梯度图中，在吸力面前段部分，出现一个密度梯度较高的区域，局部放大后如图5中右图所示，对时均结果做马赫数云图得图4右图，黑线是马赫数为1的等值线，所以图5中，在吸力面前段密度高区为正激波，产生原因为本次计算选用叶型内部流道为渐缩流道，吸力面膨胀较快，当流速达到音速时，后续流道无法为气动提供必要的膨胀条件，所以出现正激波。在叶片压力面处，因为流体膨胀较慢，故相同流道截面位置，并未出现该现象。

![](images/3d56a8ee1fa5f391c057116beb7654ba9a901e805f5e95d1e1337f4f42401baa.jpg)  
图4弱激波

![](images/6fc75bad50d08e41fe06b422d9f9cc5b51f54bd61c5897251fb9680849bb03b1.jpg)  
Fig.4 Weak shock wave   
图5弱激波局部放大图  
Fig.5 Partial enlarged view of weak shock wave

# 2.3激波与边界层干涉机理分析

在激波边界层作用区域，对时均马赫数云图进行局部放大得图6，可以看到斜激波在叶片边界层发生反射，同时诱导边界层分离。做出该区域的形状因子，结果表明，在吸力面处出现边界层分离现象，并产生分离泡，用距壁面的相对位置表征干涉区形状因子的大小，可以看到，干涉区形状因子突然增加，也说明该区域发生了边界层分离。

![](images/6c7d9c1a91fe9e5b462bae3d2b6efa06ebea7118e4c31fe043284241395a2b23.jpg)  
图6边界层分离

图为激波边界层干涉区域的速度脉动，图7(a)为湍动能图，在两道激波处，激波交汇处以及分离泡前端，湍动能较大，速度波动较大。做出马赫数云图，近壁区用黑实线表示马赫数为1的等值线，壁面附近黑色区域为诱导产生的分离泡，用线图简化干涉过程。激波前后速度波动是该处湍动能较大的原因，同时，边界层附近出现马赫反射现象，马赫激波前后，速度由超音降为亚音，速度波动较大。

![](images/e6fa496a8a8c367bda05281fec3830963731846565f79ebaeeb31bc0655e5022.jpg)  
Fig.6 Boundary layer separation   
图7干涉区速度波动  
Fig.7 Velocity fluctuation in interaction area

图8(a)为上述过程的简化图，入射激波在壁面附近形成马赫反射，且因为分离泡的存在，增大了入射激波的入射角度，对近壁区域激波反射特性产生影响。该分析过程也在图8(b)相同工况的实验中得到验证。

分离泡前，湍动能较大，对该位置放大后得图9，左图显示，其位置在分离泡前半部分，右图为该区域涡量图，用流场中最大涡量归一化后的结果，可以看到，分离泡的存在，改变了其前半部分流体的涡量，进而引起该区域较大的速度波动。

![](images/9588d0ab10447c089e2f4656a22ef4d87089c1cb85584e0e842525bd73b90a08.jpg)  
图8干涉分析Fig.8 Analysis of interaction

![](images/bcaeb7cd2063a3c5437f6390e0093e71a10926abf61c710c41375b7f89bead12.jpg)  
图9分离泡处速度波动

关于干涉区损失，采用熵生成率(EGR,EntropyGenerationRatio)分析，公式为：

$$
{ \dot { S } } _ { \mathrm { g e n } } = { \frac { 1 } { T } } \tau _ { i k } { \frac { \partial V _ { i } } { \partial x _ { k } } } + { \frac { \lambda } { T ^ { 2 } } } { \frac { \partial T } { \partial x _ { i } } } { \frac { \partial T } { \partial x _ { i } } }
$$

将总熵生成率分解为黏性和不可逆传热两部分，公式等号右端第一项表示由于黏性带来的影响，右端第二项表示由于传热带来的影响。做出熵分布如图11所示，黏性和传热所引起的损失分别用当地总熵生成率进行单位化，表征黏性和传热在熵生成中所占的比例。

![](images/61ed3977f01c87cc132d823cc10d36cf384db5bc5b1e0fe1ec5bfb4d7120403d.jpg)  
Fig.9 Velocity fluctuation in separatjon bubble area   
图11干涉区损失分布 Fig.11 Loss distribution in interaction area

工

给出涡量公式：

$$
\frac { \mathrm { d } } { \mathrm { d } t } ( \nabla \times \overrightarrow { V } ) = - \nabla \left( \frac { 1 } { \rho } \right) \times \nabla p + \cdot \cdot \cdot
$$

在激波边界层作用区域，涡量值的改变主要为斜压项带来的影响，分析过程见图10。压力云图中，边界层附近，因为马赫激波的存在，压力梯度为流动方向，而密度梯度基本是垂直壁面方向，二者乘不为零。做出斜压项云图，在分离泡前端，上部区域，斜压项数值很大，影响非常明显，所以，分离泡前端斜压项的存在，改变涡量，引起速度波动。

![](images/e823017276fe8c429692a4bcd0a0e9fd88c6ca8870dfa94071245f5ef15fbad9.jpg)  
图10涡量公式分析Fig.10 Analysis of vorticity formula

激波作用之前，未发生分离，近壁区总熵生成率较高，边界层内除黏性底层外，熵生成主要由传热不可逆引起；激波引发分离后，近壁区总熵生成率降低，且主要以黏性为主；此外，入射激波和反射激波作用区域，总熵生成率较高，引起损失较大，且主要以黏性为主。

# 2.4 激波与尾迹干涉机理分析

当激波穿过尾迹时，用密度梯度表征激波强度，得图12，和RANS 结果相比，DDES 结果能够更加清楚地反映出涡结构，更加清晰地展示激波尾迹的作用过程。

斜激波穿过尾迹时，产生反射现象，反射激波强度较弱，很快耗散消失；进一步分析可以得到，尾迹还会改变激波的强度；同时，当激波进入和穿过尾迹时，方向都会发生明显改变。

当尾迹通过激波时，激波前后存在较大的压力、速度脉动，尾迹涡结构发生明显变化。做出 $Q$ 等值面，用马赫数染色，得图13，尾迹涡通过激波时，整体上存在明显的涡破碎现象，使流场趋向均匀化。原始的涡结构，经过第一道激波后，已变为尺度较小的无规则涡系，到第二道激波时，大尺度结构已基本耗散消失。

![](images/9d3f447193afeb4eff020ede702b775f9db93a911c9cdcd0306cae6add1d3942.jpg)  
图12瞬时密度梯度 Fig.12 Instantaneous density gradient

![](images/d90aacbd03e33df9570beafdbd6be12889fd2b2d1494bf51751931f9a446cb69.jpg)  
图13激波对尾迹作用Fig.13 The effect of shock wave on wake

![](images/42476ac31e4fd44cf50e63cd9752dce1a64ec333eb7828ae88d57bea41e4b4ec.jpg)  
图14尾迹区损失分布 Fig.14 Loss distribution in wake area

激波尾迹干涉处的损失分析，做出时均熵生成率结果如图14所示。尾迹方面，尾迹处熵生成率较大，但因为激波的存在，尾迹很快耗散，在激波附近，激波后部区域，因尾迹带来的损失比重已经很小。激波方面，反射激波在反射过程中存在激波强度地衰减，经过尾迹后，相同流向位置时，左侧激波分支强度方面会弱于流道中的右侧分支，后续熵增也较小。所以，涡结构的破碎，利于减小流场损失，激波强度的衰减，利用减小流场损失。

# 3结论

本文采用自主开发的DDES求解器，解析出精细的非定常流场结构，为实现跨音复杂流动现象的机理分析提供必要条件。流道斜激波在叶片吸力面诱导边界层分离，产生马赫反射，使分离泡前斜压项数值较大，改变边界层附近损失分布。尾迹会使激波发生表面的反射和透过时的折射，并改变其强度；激波前后，大尺度的涡结构破碎，很快耗散消失，流场趋向均匀化；激波和尾迹的干涉情况有利于减小流场损失。

# 参考文献

[1] Spalart PR,Jou WH,Strelets M,et al. Comments on the FeasibilityofLES for Wings,and ona Hybrid RANS/LES Approach[J].Advances in DNS/LES,1997,1: 4-8   
[2]Spalart PR,Deck S,Shur ML,et al.A New Version of Detached-eddy Simulation,Resistant to Ambiguous Grid Densities. Theoretical and Computational Fluid Dynamics,2006,20(3): 181-195   
[3]苏欣荣.叶轮机械非定常流动数值算法研究[D].清华大学, 2010 SU Xinrong.Algorithm Developments for Unsteady Turbomachinery Flow Computations [D].Tsinghua University,2010   
[4] Strelets M.Detached Eddy Simulation of Massively Separated Flows [M.American Institute of Aeronautics and Astronautics,2001   
[5] Brooksbank E J.A Numerical Investigation of Time Resolved Flows Around Turbine Blades.[J].University of Leicester,2001   
[6] Currie T C,Carscallen WE.Simulation of Trailing Edge Vortex Shedding ina Transonic Turbine Cascade [J].Journal of Turbomachinery,1998,120(1):10-19   
[7] Gostelow JP,Mahallati A,Andrews S A,et al. Measurement and Computation ofFlowfieldin Transonic Turbine Nozzle Blading with Blunt Trailing Edges [C]//ASME Turbo Expo 2Oo9:Power for Land,Sea,and Air.American Society of Mechanical Engineers,20o9:979-991