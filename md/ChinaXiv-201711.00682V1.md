编号：2016-0264

# 新型螺旋梅花形孔板换热器热力性能仿真计算

张轩恺，韩东，何纬峰，岳晨，蒲文灏

(南京航空航天大学能源与动力学院江苏省航空动力系统重点实验室，南京210016)摘要：依据涡旋流动强化传热技术，变传统直流道的梅花形支撑孔板为螺旋流道的梅花形支撑孔板，进而设计出一种新型螺旋梅花形孔板换热器，建立了相应的数学模型，并对其传热与流动特性进行了仿真计算。通过与梅花形孔板换热器的对比分析，展示了新型换热器壳程强化换热机理，并进一步探索了螺旋流道的螺旋角对新型换热器的影响。计算结果表明：在研究范围内，新型换热器壳程平均对流换热系数高于传统换热器，但同时壳程压降也相对应增加，在一定雷诺数范围内新型换热器综合性能参数优于传统换热器。当螺旋角为27°、雷诺数小于19672时，其综合性能比传统换热器较佳；探究了不同螺旋角的影响，发现螺旋角越大，新型换热器压降越大，同时换热能力也越强。

关键词：螺旋梅花形支撑孔板；传热；数值模拟；流场；换热器中图分类号：TK172 文献标识码：A

# The simulation on thermal performance of a novel shell-and-tube heat exchanger with screw cinquefoil orifice baffles

ZHANG Xuan-Kai, HAN Dong,HE Wei-Feng, YUE Chen, PU Wen-Hao (College of Energy and Power Engineering,Nanjing University of Aeronautics and Astronautics, Jiangsu Province Key Laboratory of Aerospace Power System, Nanjing 210016,Jiangsu, China)

Abstract: According to the effect of vortex flow on heat transfer enhancement,a novel shell-and-tube heat exchanger with screw cinquefoil orifice baffles (STHX-SCOB) by using screw type cinquefoil orifice baffles on the shell side is proposed.The corresponding mathematical and physical model of the shell side of the heat exchangers was established,and the shell side flow is simulated.By comparing with the shell-and-tube heat exchanger with cinquefoil orifice bafles (STHX-COB),the heat transfer enhancement mechanism in shellside of the novel heat exchanger is shown. Moreover, study on the performance of the heat exchanger with variable helical angle of screw type cinquefoil orifice bales.The simulation results showed that the heat transfer coeffcient of the novel heat exchanger and pressure drop are both higher than that of traditional heat exchanger,and the comprehensive performance of the novel heat exchanger is higher than that of traditional heat exchanger in a certain range of Reynolds number. The comprehensive performance of STHX-SCOB is better than STHX-COB when helical angle is 27 ° and Reynolds number less than 19672. In addition, the study shows the larger number of helical angle of screw type cinquefoil orifice baffles, the higher of the heat transfer coefficient and pressure drop.

Key words: screw cinquefoil orifice bafles; heat transfer; numerical simulation； flow field； heatexchanger

# 0引言

管壳式换热器，因其成本低、简单耐用、能处理大流量流体等优点，在化工领域应用极为普遍[1]。而传统的管壳式换热器存在壳程压降大，流动“死区”，易产生诱导振动等缺点[2]，故探索研究能替代传统换热器的新型换热器具有重要意义。

在众多新型管壳式换热器中，孔板换热器因其壳程流体呈纵向流动，具有压力损失低、传热效率高、流动"死区"小、抗振性能好等优点，被广泛地应用在核电等行业[3]。目前国内外关于孔板换热器的研究较少。戴玉龙等［4]人通过 FLUENT 分析了梅花形孔板换热器壳程的单元简化模型，并拟合出了Nu-Re关系式。董其伍等人[5]利用FLUENT对三叶孔板换热器壳程流体流动和传热特性进行了数值模拟研究，分析了壳程流量、孔高、支承板间距等结构参数对换热器的性能影响，并对比不同换热器的综合性能。游永华等[人则通过实验研究三叶孔板换热器，得到了其试验准则关系式，并通过数值分析，表明孔板形成的射流和强烈回流可冲刷管壁，提高流体湍流强度，加速主流混合，同时减小了边界层厚度，有效强化了换热。但通过以往的研究发现，孔板换热器壳程的强化换热区域集中于支撑板附近，在远离支撑板的区域，流体换热能力减弱，换热潜力仍待开发。而针对目前孔板纵流换热器的研究，除了对常见的结构参数，如板间距等研究外，还可以通过改变孔板上的孔形以获得更好的换热性能。

螺旋折流板换热器的壳侧流体在折流板的引导作用下可消除流动死区，降低壳程阻力损失，有效抑制污垢的形成和管束的振动破坏，因而逐步受到换热器行业的重视[7-9]。杜文静等[10]人提出了六分扇形螺旋折流板换热器，通过 ANSYSCFX对其进行数值模拟，并与实验进行了对比，其认为由于螺旋折流板形成的近似螺旋通道，壳侧流体受离心力和向心力共同作用使流体产生旋转流动，新型换热器的综合性能要优于传统弓形板换热器。但由于螺旋折流板与管板间夹角的存在，其加工工序比普通弓形折流板要稍显复杂[7]，因此螺旋折流板换热器成本较高。

为了解决上述问题，本文以梅花型孔板为基础，变传统支撑孔板的直流道为螺旋流道，设计出了一种新型螺旋梅花形孔板换热器，拓宽了孔板纵流换热器的研究范围，为实际生产生活提供了一类新的解决方案。本文通过对梅花形孔板换热器和螺旋梅花形孔板换热器的壳程流场进行数值模拟研究，分析了两者热力性能不同的原因，并进一步探究螺旋角对于新型换热器的热力性能的影响，为螺旋梅花形孔板换热器的结构优化提供了理论依据。

# 1 换热器模型

# 1.1几何模型

螺旋梅花形支撑孔板为整圆形支撑板，每个管孔周围有6个流体通孔作为壳程流体在孔板处的流通通道，流通通道呈螺旋状，使通过螺旋流道的流体流向改变，其结构如图1(a)(b)所示。相比之下，梅花形支撑孔板的流道则为直流流道，其结构如图1(c)(d)所示，两种换热器的具体几何参数详见表1。

![](images/6f6380f95e3610f3dcb48d73688ea314950f11b5e48136b75629c21828cd7429.jpg)

(b）螺旋梅花形支撑孔板   
(a）螺旋梅花形支撑孔板 中心孔截面图   
(a) Graphic model of screw (b) The cross section type cinquefoil orifice drawingin the centerhole baffle. of screw type cinquefoil orifice baffle.

![](images/c1805a54ecd830ea48ace79af0c67283edc76f6b0e580bed6bc3a98bc7b55a55.jpg)

(d)梅花形支撑孔板中心 (c）梅花形支撑孔板 孔截面图 (c) Graphic model of (d) The cross section cinquefoil orifice baffle. drawing in the center hole of cinquefoil orifice baffle.

图1两种支撑孔板对比 Fig.1.Two type of baffles.

表1不同模型的几何参数  
Table1 Common geometry parameters for two models.   

<html><body><table><tr><td>参数</td><td>STHX- COB</td><td>STHX-SCO B</td></tr><tr><td>螺旋角α/ (°)</td><td>/</td><td>27/38/46</td></tr><tr><td>孔板厚度Db/mm</td><td>3</td><td>8</td></tr><tr><td>孔板数量</td><td></td><td>3</td></tr><tr><td>孔板中心间距B /mm</td><td></td><td>166</td></tr><tr><td>壳体内径D/mm</td><td></td><td>95</td></tr><tr><td>换热管有效长度L/mm</td><td></td><td>600</td></tr><tr><td>换热管中心间距 dc/mm</td><td></td><td>30</td></tr><tr><td>换热管数量</td><td></td><td>7</td></tr><tr><td>换热管排布形式</td><td></td><td>三角形排布</td></tr><tr><td>通孔圆心角β/()</td><td></td><td>40</td></tr><tr><td>梅花孔通孔外径d。/mm</td><td></td><td>28</td></tr><tr><td>换热管外径dt /mm</td><td></td><td>20</td></tr></table></body></html>

# 1.2控制方程和边界条件

根据实际的数值方法对控制方程进行了修改。控制方程组为稳态的连续性方程、动量方程、能量方程和状态方程。

选取水作为壳程流体介质，两换热器进口均为速度进口，温度为 $3 6 0 \mathrm { ~ K ~ }$ ；出口为压力出口，表压为 $0 \mathrm { { P a } }$ ，参考压力 $1 0 1 3 2 5 \mathrm { P a }$ ；换热管壁设定为恒温壁面，壁面温度为 $3 0 0 \mathrm { ~ K ~ }$ ；壳体内壁、孔板表面等采用绝热、不可渗透、无滑移边界条件。

# 1.3数值求解方法及模型验证

建立两种换热器的壳程实体模型，如图2所示，并采用软件ANSYSCFX模拟整个壳程流场，采用RNG $k { - } \varepsilon$ 湍流模型[9,1]进行稳态求解，压力速度的耦合方式采用SIMPLE算法，物理参量采用二阶迎风格式进行求解。

![](images/34f4a1942b23c06fe0f2c8caf55084331296590f3a0ab07d8962f44c4476b0ba.jpg)  
图2新型换热器的整体模型 Fig.2.Whole model.

考虑到支撑板处流体流动的复杂，将网格模型分成远离支撑板区域、支撑板的附近区域以及进出口区域三块[1]，如图3所示，采用ANSYSICEM进行分块处理。

为了确保模拟的准确，需要对所有模型进行网格无关性验证 [1,5,12]。以螺旋梅花形孔板换热器为例，在螺旋角为 $\scriptstyle a = 3 8$ °、雷诺数为 $R e { = } 5 8 0 2$ 的工况下，采用4种不同数量的网格模型对其压降 $\varDelta p$ 和换热系数 $h$ 进行了数值计算。如图4所示，综合考虑计算机性能，选择网格量为 $3 . 6 7 \times 1 0 ^ { 6 }$ 。梅花形孔板换热器网格量为 $3 . 0 9 \times 1 0 ^ { 6 }$ 。

为了验证本文的数值模拟的正确性，通过研究Ozden等人的换热器模型，采用本文的数值模拟方法得到的结果与文献[13]Ozden 等人的数据结果进行对比，如图5所示。其中红线为通过本文数值模拟方法得到的数据，黑线为Ozden等人得到的数据，结果显示两个模型的换热系数 $h$ 最大差值不超过 $5 \%$ ， $\varDelta p$ 最大差值不超过 $3 \%$ ，证明本文的数值模拟的正确性可以得到保证。

![](images/aa667456b38d378b01e328058e8121119ef731abff0eeb6ce16db779a9fac62b.jpg)  
图3新型换热器网格模型

![](images/4ead019898df7a578d075297ab28c4ccfc8a0eb7b0eecae496e1e222b4bead7d.jpg)  
Fig.3. Meshes of computational model.   
图4新型换热器网格独立性验证  
Fig.4.STHX-SCOB results of different grid systems.

![](images/814d8998550056ba6d7b3f31eda219f6039c14cdfacb8fa124ee224a1fcd92e0.jpg)  
图5本文模拟结果与文献[13]中的结果对比 Fig.5.The comparison between the result in[13]and the simulation result by this paper method.

# 2结果与讨论

# 2.1强化传热机理分析

图6给出了在相同雷诺数条件下两种换热器的流场流线。相对于图6(a)梅花形孔板换热器的速度流场分布，从图6(b)中可以看到螺旋梅花形孔板换热器的壳程流体处于一种较为强烈的旋转流动状态。新型换热器的壳程流体在梅花孔处，不仅产生了射流效应，而且也可产生连续不断的涡流，强化了流体微团之间的掺混，对流体边界层和污垢层产生很强的冲刷作用，达到强化传热目的。

从图7中也可以看出，传统换热器在壳体附近存在较大的低速区域，而新型换热器的整体流速较均匀，其流动死区范围较小。新型换热器内流体流速较高，破坏了流动边界层的形成。由图8可知，相比之下新型换热器在壁面处的平均换热系数更高，而且较为均匀。所以综上，新型换热器壳程流体换热能力相比于传统换热器得到提高。

![](images/ba82c702317ad035f3960b16dd996e8b4b031b8adb70607e8405277b6b8f777e.jpg)  
图6两种换热器的流场流线对比！ $R e { = } 5 8 0 2$

Fig.6.Flow distributions in different heat exchangers( $R e { = } 5 8 0 2$ ）

![](images/6d93a9ad7820d53a2536e4466cdf62af89649b4378abe468ff881e196bf56aa8.jpg)  
图7两种换热器在不同截面上的速度分布 $( R e { = } 5 8 0 2$ 0Fig.7.Velocity distributions on corresponding cross sectionin different heat exchangers( $R e { = } 5 8 0 2$ ）

![](images/09004492c2e15ac16a761a3381f7b60c32404c49ad3f85d0ec01bfdf2d4589ed.jpg)

# 2.2换热器性能对比

在两种换热器边界条件相等的情况下， $h$ 和$\varDelta p$ 随雷诺数 $R e$ 的变化关系如图9所示。由图9可以看出，在所研究的雷诺数变化范围内，随着 $R e$ 的增加， $h$ 和 $\varDelta p$ 都有大幅度的增加，且随着 $R e$ 的增加， $\varDelta p$ 的增加速率较 $h$ 的增加速率更大。

从图9(a)可以看出，新型换热器 $h$ 高于传统换热器，5个状态点平均高出 $9 . 2 \%$ 。在低 $R e$ 条件下，优势更加明显。

当 $R e = 2 3 2 2$ 时，新型换热器 $h { = } 7 5 4 . 9$ $\mathrm { W } { \cdot } \mathrm { m } ^ { - 2 } { \cdot } \mathrm { K } ^ { - 1 }$ ，而传统换热器 $h { = } 6 1 0 . 9 \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 } { \cdot } \mathrm { K } ^ { - 1 }$ ，两者相差 $23 . 6 \%$ ；随着 $R e$ 的增加，传统换热器内的壳程流体湍流度增大，换热性能得到改善，两者相差逐渐降低。当 $R e { = } 2 3 2 2 0$ 时，两者相差$6 . 9 \%$ 。这证明新型换热器在低雷诺数的条件下的换热性能更优秀。除了 $h$ ，从图9(b)看出，新型换热器 $\varDelta p$ 则高于传统换热器。当 $R e = 2 3 2 2$ 时，新型换热器 $\varDelta p$ 比传统换热器要高 $21 . 4 \%$ ，而随着 $R e$ 增大，两换热器 $\varDelta p$ 的差值也在不断增加，在所研究范围内，新型换热器 $\varDelta p$ 比传统换热器平均要高 $3 6 . 0 \%$ 。综上，新型换热器在低 $R e$ 数范围条件下相比传统换热器适用性更强。

![](images/1b5323f0310de88d9c2bbf0b73a95551464e7e4c4e48648b65f05e8a5278dbdb.jpg)  
(a）换热系数随雷诺数的变化曲线

(a) Heat transfer coefficient versus Reynolds number.

![](images/78faa8c9a643fd720409d23427dad85081c79d486847d9623139320bb99fbb70.jpg)  
图8两种换热器在管壁处的换热系数比较 $( R e { = } 5 8 0 2 )$ Fig.8.Heat transfer coeficient in different heat exchangers $( R e { = } 5 8 0 2 )$   
图9两种换热器的热力性能比较 Fig.9.The comparison performances of two heat exchangers.

在动力工程和石油化工领域中由于受到流体输送推动力或工艺条件的限制，许多工作流体粘性较大或流速较慢，这些流体常在低Re数下流动，故对低 $R e$ 数换热器研究就具有重大意义[16]。

# 2.3螺旋角对新型换热器性能的影响

在螺旋折流板换热器中折流板螺旋角直接影响到换热器性能[7,9]。同理，在螺旋梅花形孔板换热器中，螺旋梅花孔的螺旋角对于换热器性能有重要影响。探究的螺旋角 $\scriptstyle a$ 大小分别为 $2 7 ^ { \mathrm { ~ o ~ } }$ 、38°和 $4 6 ^ { \circ }$ ，三种换热器的边界条件相同。如图10所示，螺旋梅花形支撑孔板 $\scriptstyle a$ 越大，壳程流体流线的螺旋程度越强，换热器换热性能越好。

![](images/875fc0fc9405b9c7f003f5be90f8ac73e38ed2bc08f3cb88b98ebef01cf7679d.jpg)

图11(a)为三种不同 $\scriptstyle a$ 的新型换热器的 $h$ ，可以看出 $\scriptstyle a$ 越大， $h$ 越大。在研究范围内， $\scriptstyle { a = 4 6 ^ { \circ } }$ （204号与 $\scriptstyle \alpha = 3 8 ^ { \textnormal { o } }$ 两换热器的 $h$ 相差 $6 . 2 \%$ ，而 $\scriptstyle \alpha = 3 8 ^ { \mathrm { ~ o ~ } }$ 与$\scriptstyle a = 2 7 ^ { \circ }$ 两换热器的 $h$ 相差 $7 . 1 \%$ 。但换热性能提升同时 $\varDelta p$ 也在增加。由图11(b)， $\scriptstyle { a = 4 6 ^ { \circ } }$ 与 $\scriptstyle { a = 3 8 ^ { \textnormal { o } } }$ 两换热器的 $\varDelta p$ 相差 $36 . 9 \%$ ，而 $\scriptstyle { a = 3 8 }$ 与 $\scriptstyle a = 2 7$ 。两换热器 $\varDelta p$ 相差 $3 1 . 6 \%$ 。

![](images/557bafc8b3159903ebd3a8a5c202ca36dbcbfcc70353c3e0dc19761f2a2496e9.jpg)  
(a)换热系数随雷诺数的变化曲线

(a) Heat transfer coefficient versus Reynolds number.

![](images/0b9446146c9d1d590890d408d66e12ad34dc9700e8f972a40712a17aedbbc5e9.jpg)  
图11螺旋角对换热器的性能影响

![](images/4db4297fd8a3aa183d8b07834cf6f17b7d0b3fe01cbdc25a005c8127495ee7d7.jpg)  
图10螺旋角对流场流线的影响( $R e { = } 5 8 0 2$ 0 Fig.10.Velocity flow distribution with different helicalangle ( $\mathrm { R e } { = } 5 8 0 2$ ）   
Fig.11.The performances with different helical angles.   
图12螺旋角对综合性能的影响  
Fig.12.The effect of $\mathfrak { a }$ on comprehensive performance.

![](images/5daf08b9bd9cbcdcf6ca4062d91dc3a93df2b75ba37c2e1613cee6864f028f62.jpg)  
图13两种换热器的综合性能比较  
Fig.13. The comprehensive performance comparison of two heat exchangers.

为了综合评定两换热器的性能，引入综合性能参数 $C P = N u \cdot f ^ { ^ { - { \frac { 1 } { 3 } } } }$ [14]。如图12所示，可知换热器 $C P$ 随着 $\alpha$ 的减小而增高。因此选取 $\scriptstyle { a = 2 7 ^ { \circ } }$ 时的新型换热器与传统换热器进行对比。如图13所示，可见新型换热器 $C P$ 在一定 $R e$ 数范围内高于传统换热器。当 $\scriptstyle \alpha = 2 7 ^ { \mathrm { ~ o ~ } }$ 、 $R e { < } 1 9 6 7 2$ 时，新型换热器综合性能优于传统换热器，特别当 $R e = 2 3 2 2$ 时， $C P { = } 4 . 3$ ，其与传统换热器相比要高 $5 . 7 \%$ 0

通过研究，本文发现螺旋通道内柱状流的速度梯度影响了边界层的形成，使换热系数大大提高，特别是低 $R e$ 数下换热效果更加突出，而前人的研究[15-17] 也证实了这个结论。

# 3结论

（1）新型换热器的强化换热机理在于：壳程流体处于一种较强的旋转流动状态。在梅花孔处，不仅产生了射流效应，而且也可产生连续不断的涡流，强化了流体微团之间的掺混，对流体边界层和污垢层产生很强的冲刷作用，达到强化传热目的。

（2）在除支撑板外其他结构参数和边界条件相同的情况下，新型换热器的壳程平均对流换热系数和压降均高于传统换热器。但新型换热器的综合性能值在一定雷诺数范围内要优于传统换热器。当螺旋角为27°、雷诺数小于19672时，新型换热器综合性能优于传统换热器。

（3）在除支撑板外其他结构参数和边界条件相同的情况下，螺旋流道的螺旋角越大，壳程流体流线的螺旋程度越强，但能量损失也越大，因此换热器的壳程平均对流换热系数和压降越高。如螺旋角为38°与27°两换热器的换热系数相差 $7 . 1 \%$ ，而压降值相差 $3 1 . 6 \%$ 。故采用该新型换热器时，应针对换热器使用场合对于传热与压降的具体要求进行综合考量。

# 参考文献

[1]王新婷，郑年本，刘鹏，等．波形折流杆换热器的流动 与传热性能分析[J]．工程热物理学报，2016,37(8): 1758-1762. WANG Xinting， ZHENG Nianben，LIU Peng,et al. Analysis of Flow and Heat Transfer Capability in Rod Baffle Heat Exchangers with Ripple Rods [J].Journal of Engineering Thermophysics,2016,37(8): 1758-1762.   
[2] 钱才富，高宏宇，孙海阳．曲面弓形折流板换热器壳 程流体流动与传热[J]．化工学报，2011，62(5): 1233-1238. QIAN Caifu, GAO Hongyu,SUN Haiyang. Shell Side Fluid Flow and Heat Transfer in Curved Bale Heat Exchanger [J]. Journal of Chemical Industryand Engineering(China),2011, 62(5): 1233-1238.   
[3] 王翠华，张平，吴剑华,等．网状孔板纵向流换热器壳 程流体流动及换热的三维数值模拟[J].化工进展, 2011,30(9): 1932-1936. WANG Cuihua, ZHANG Ping,WU Jianhua, et al. Three Dimensional Numerical Simulation for Shell Side Fluid Flow and Heat Transfer Characteristics in Reticulated Orifice Baffle Longitudinal Flow Type Heat Exchangers [J].Chemical Industry and Engineering Progress,2011, 30(9): 1932-1936.   
[4]戴玉龙,李志安，王翠华，等．梅花形孔板支撑换热器 壳程流场的数值分析[J].沈阳化工学院学报，2007, 21(1): 25-28. DAI Yulong ,LI Zhian ,WANG Cuihua, et al. Numerical Analysis of Flow Field in Shell Side of Cinquefoil Orifice Baffle Support Type Heat Exchanger [J]. Journal of Shenyang Institute of Chemical Technology, 2007, 21(1): 25-28.   
[5] 董其伍，白彩鹏，刘敏珊，等．三叶孔板换热器壳程流 动和传热研究[J]．工程热物理学报，2012，49(2): 21-23. DONG Qiwu,BAI Caipeng, LIU Minshan,et al. Research on Flow and Heat Transfer in Shell Side of the Trefoil Baffle Support Type Heat Exchanger [J], Journal ofEngineering Thermophysics,2012,49(2): 21-23.   
[6]游永华.管壳式换热器中单相流体强化传热的数值模 拟和实验研究[D]．武汉：华中科技大学,2013. YOUYonghua.NumericalandExperimental Investigations in Single Phase Thermal Augmentation for Shell-and-Tube Heat Exchangers [D]. Wuhan: Huazhong University of Science and Technology, 2013.   
[7]张少维．螺旋折流板换热器的结构及性能研究[D]．南 京：南京工业大学，2005. ZHANG Shaowei. Study on Structure and Performance of Heat Exchanger with Helical Baffles [D]. Nanjing: Nanjing University of Technology, 2005.   
[8]Nasr M J,Shafeghat A.Fluid Flow Analysis and Extension of Rapid Design Algorithm for Helical Baffle Heat Exchangers [J].Applied Thermal Engineering,2008. 28(11): 1324-1332.   
[9] 王伟晗，陈亚平，吴嘉峰，等．三分螺旋折流板换热器 壳侧流场温度场模拟[J]．工程热物理学报,2012,33(1): 131-134. WANG Weihan,CHEN Yaping，WU Jiafeng，et al. Numerical Simulation of Flow Field and Temperature Field in Shell Side of Trisection Helix Heat Exchangers [J].Journal of Engineering Thermophysics,2012,33(1): 131-134.   
[10] 杜文静，王红福，曹兴，等．新型六分扇形螺旋折流板 换热器壳程传热及流动特性[J]．化工学报,2013,64(9): 3123-3129. DU Wenjing,WANG Hongfu, CAO Xing,et al. Heat Transfer and Fluid Flow on Shell Side of Heat Exchangers with Novel Sextant Sector Helical Baffles [J]. Journal of Chemical Industry and Engineering (China), 2013,64(9):3123-3129.   
[11] Wang S,Wen J. Experimental Investigation on Heat Transfer Enhancement of a Heat Exchanger with Helical Baffles through Blockage of Triangle Leakage Zones [J]. Applied Thermal Engineering,2014,67(1):122-130.   
[12] Wang Q， Chen Q， Chen G， et al. Numerical Investigation onCombinedMultiple Shell Pass Shell-and-Tube Heat Exchanger with Continuous Helical Baffles [J].International Journal of Heat and Mass Transfer,2009,52(5): 1214-1222.   
[13]Ozden E,Tari I. Shell Side CFD Analysis of a Small Shell-and-Tube Heat Exchanger [J]. Energy Conversion and Management, 2010,51(5): 1004-1014.   
[14] Jian W, Huizhu Y, Wang S,et al. Numerical Investigation on Baffle Configuration Improvement of the Heat Exchanger with Helical Baffles [J].Energy Conversion and Management, 2015,89: 438-448.   
[15] Stehlik P, Némcansky J,Kral D,et al. Comparison of Correction Factors for Shell-and-Tube Heat Exchangers with Segmental or Helical Baffles [J].Heat Transfer Engineering,1994,15(1): 55-65.   
[16]李建军．低雷诺数流动换热器的传热和压降特性研究 [D]．上海交通大学,2004. LI Jianjun.Research on Heat Transfer and Pressure Drop in Low Reynolds Number Flow Heat Exchangers [D]. Shanghai: Shanghai Jiao Tong University, 2004.   
[17]李燕．低雷诺数下纵流壳程换热器强化传热研究[D]. 郑州：郑州大学,2006. LI Yan.Heat Transfer Enhancement Research of Heat Exchangers with Longitudinal Flow of Shell Side Fluid underLowReynoldsNumber[D]. Zhengzhou: Zhengzhou University, 2006.