# 削弱模块化永磁电机齿槽转矩的新方法

井立兵1,2 柳　霖}　高起兴} 罗正豪(1.三峡大学电气与新能源学院宜昌 4430022.湖北省微电网工程技术研究中心宜昌 443002)

![](images/a82eb2dbf6aae6e37e033f75dbfa8e2ac2d50dcc0f4f3e1fa6881ef8bb441f90.jpg)

井立兵男 1982年生，博士，研究方向为特种电机设计与优化、电机电磁场分析计算。

摘要：为减小模块化永磁电机的齿槽转矩，结合永磁电机槽口偏移法，提出并讨论了一种新型定子结构，沿圆周方向带有向左和向右的槽开口。由于定子槽开口的机械位移，产生的齿槽转矩分量也移向右侧和左侧。因此，对于一个适当的移动角，齿槽转矩分量的一半和另一半可以移动 $1 8 0 ^ { \circ }$ ，这使得齿槽转矩分量相互抵消，从而削弱了总的合成齿槽转矩。通过将一个电机的总齿槽转矩看作是由两个电机齿槽转矩叠加而成的方法，使得分析方法更加简单易懂，并给出了槽口偏移的表达式。实验仿真表明，该方法能够有效削弱模块化永磁电机的齿槽转矩，并将转矩波动控制在额定转矩的 $2 \%$ 以下。

关键词：模块化永磁电机槽口偏移 齿槽转矩转矩波动有限元分析中图分类号：TM464；V44

# A Novel Method of Weakening the Cogging Torque of Modular Permanent Magnet Motor

![](images/4ebae90c5fc7871b94f7572fedba66c757ede6fe2ee55b5719a23b48d45c2f20.jpg)

Jing Libingl,²Liu Lin'Gao QixinglLuo Zhenghao1 (1.China Three Gorges University Yichang 443002 China 2.Hubei Micro-Grid Engineering Technology Research CenterYichang443002 China)

柳霖男1990年生，硕士研究生，研究方向为永磁电机电磁场的数值分析与优化设计。

Abstract: A new structure of stator combing the slot opening shift of the permanent magnet motor is discussed in the paper in order to reduce the cogging torque of modular permanent magnet motor. The generated cogging torque components are shifted also to the right and to the left due to the mechanical displacement of stator slot opening. Therefore, for an appropriate shifting angle,the cogging torque components for the one-half and the second half can be shifted by $1 8 0 ^ { \circ }$ ， and the cogging torque components can be mutually offset,then the total cogging torque can be reduced.By the method of regarding the total cogging torque of one motor as the addictive cogging torque of two motors,the expression of slot opening shift has been given.The experimental simulation shows that the method can effectively weaken the cogging torque of modular permanent magnet motor, and can keep the torque ripple under the $2 \%$ of the rated torque.

Keywords: Modular permanent magnet motor, slot-opening shift, cogging torque, torque ripple, finite element analysis

# 1 引言

模块化定子结构永磁电机（ModularPermanentMagnetMachines，MPMM）是一种新型拓扑结构的电机，其显著特点是多极数、低速运行、输出转矩较大[1-3]。根据 $n p = 6 0 f$ ，在频率确定的情况下,增加电机的极数可以降低电机的转速，因此采用模块化定子结构的电机可以轻松达到上述要求。由于极数较多、转速较低，电机的输出转矩也较大，从而使电机在没有减速机构的情况下就可以运行在低速大转矩状态。MPMM与传统电机的最大区别在于其定子结构采用模块化，定子上属于各相的绕组分别绕制在连续的定子齿上，使得各相之间不会产生交叉绕组。这样不仅制造方便，而且可以获得较高的绕组分布系数从而获得较高的效率，减少制造时交叉的机率。对于一个给定极数的电机，只需要很少的槽数就可以满足。

目前关于MPMM的研究主要集中在研究模块化永磁电机的齿槽转矩、反电动势、负载转矩和铁损，并没有提出一种有效的方法来削弱模块化永磁电机的齿槽转矩。因此，为了填补这部分空缺并进一步提高模块化永磁电机的性能，本文提出了一种新的削弱齿槽转矩的方法。与其他方法不同，该方法是通过开槽的齿槽转矩分量相互抵消来减小总的齿槽转矩。

齿槽转矩是在永磁电机绕组不通电时永磁体和铁心之间相互作用产生的转矩，是由永磁体和电枢齿之间相互作用力的切向分量引起的。齿槽转矩的存在会严重影响电机的稳定性能，使得电机产生振动，并发出噪声。因此齿槽转矩的削弱是永磁电机设计的重要问题之一。但是仅仅考虑齿槽转矩远远不够，在削弱齿槽转矩的同时还要考虑电机的转矩波动。本文设计了一种新型定子，能够在削弱齿槽转矩的同时，控制其产生较小的转矩波动。

# 2 理论分析

由于开槽，在永磁磁动势(MMF)谐波与气隙磁导谐波相互作用下产生了齿槽转矩。根据文献[4],可得齿槽转矩的一般表达式为

$$
T _ { \mathrm { c o g } } = \sum _ { n = 1 , 2 , 3 , \cdots } T _ { \mathrm { c } , n } \sin n N _ { \mathrm { c } } \alpha
$$

式中， $T _ { \mathrm { c } , n }$ 为 $n$ 次谐波的齿槽转矩幅值； $N _ { \mathrm { c } }$ 为槽数$\varrho _ { \mathrm { s } }$ 和极数 $2 p$ 的最小公倍数； $\alpha$ 为定子和转子之间的机械角度。同普通电机一样，齿槽转矩的周期取决于 $N _ { \mathrm { c } }$ 。周期数越大，齿槽转矩频率越高，其振幅就越小，因此该方法适用于合适的极槽配合。周期数特别大时，其齿槽转矩的峰值几乎为零，这样的模块化永磁电机本文不予研究。所以，本文以10极12 槽为模型电机。

文献[5]中提到，电机齿槽转矩可以看作是每个磁极作用下齿槽转矩的叠加。因此本文将电机分成两个部分，如图1所示。

![](images/96b6826b0f4450c91fa9e3127160e75b5878b8b86008234a106cabdf0500c514.jpg)  
图1两个次级结构定子铁心  
Fig.1Two sub-structures of stator core

每个部分由6个定子槽组成，两组相加得到完整的定子。因此电机的齿槽转矩可以表示为

$$
T _ { \mathrm { c o g } } = T _ { \mathrm { I } } + T _ { \mathrm { I I } }
$$

由式（1）可知， $T _ { \mathrm { I } }$ 和 $T _ { \mathrm { I I } }$ 可以表示为

$$
T _ { \mathrm { I } } = \sum _ { n = 1 , 2 , 3 , \cdots } ^ { \infty } T _ { N _ { \mathrm { c } , n } ^ { \mathrm { I } } } \sin N _ { \mathrm { c } } ^ { \mathrm { I } } n \theta
$$

$$
T _ { \mathrm { I I } } = \sum _ { n = 1 , 2 , 3 , \cdots } ^ { \infty } T _ { N _ { \mathrm { c } , n } ^ { \mathrm { I I } } } \sin N _ { \mathrm { c } } ^ { \mathrm { I I } } n \theta
$$

式中， $T _ { N _ { \mathrm { c } , n } ^ { \mathrm { I } } }$ 、 $T _ { { _ { N _ { \mathrm { c } , n } } ^ { \mathrm { u } } } }$ 分别为第一部分和第二部分 $n$ 次谐波齿槽转矩的幅值； $\theta$ 为定子和转子之间的机械角度。

# 3 新型定子设计

齿槽转矩由永磁电机绕组不通电时永磁体和定子铁心之间相互作用产生，因此永磁体和定子是影响齿槽转矩大小的主要原因。国内外已有许多学者对其进行了研究，并取得了一定成果[6-13]，但还存在一些不足之处，如采用斜槽，它能够在一定程度上削弱齿槽转矩，但是不能削弱永磁体端部和定子铁心端部之间产生的齿槽转矩；又如开辅助槽，虽然会减小齿槽转矩，但是生产过程复杂，会增加机械生产成本。因此本文设计研究了一个减少齿槽转矩而不影响电机其他性能和生产过程的简单的解决方案。该方案基于补偿法实现，后面会重点说明。

如图2所示，传统定子齿的槽口完全一致，当永磁体随转子运动时，磁场能量的变化产生了齿槽转矩。偏移型定子齿的槽口较传统定子齿的槽口偏移了 $\beta$ 角度，如图3所示。

工TTTI永磁体转子

ELLII转子

![](images/738d9e29cfd6138d6a2fcd614a9b5cf9b7f5a317548c6f250eca232460dc70d5.jpg)  
图2传统定子结构  
Fig.2 Conventional stator core   
图3偏移型定子结构  
Fig.3 Stator core with shifted slot opening   
图4新型定子结构Fig.4New stator core

与传统电机一样，槽口的偏移不会影响电机齿槽转矩的幅值，仅仅改变其相位角。因此本文考虑是否可以将第一部分与第二部分的槽口偏移适当角度，使得两者产生的齿槽转矩相互抵消，以达到削弱效果。图4为新型定子结构。

图4中，第一部分的槽口向右偏移 $\beta$ 角度，第二部分的槽口向左偏移 $\beta$ 角度。因此偏移后的齿槽转矩可以表示为

$$
T _ { \mathrm { I } } = \sum _ { n = 1 , 2 , 3 , \cdots } ^ { \infty } T _ { N _ { \mathrm { c } , n } ^ { \mathrm { I } } } \sin N _ { \mathrm { c } } ^ { \mathrm { I } } ( \theta - \beta )
$$

$$
T _ { \mathrm { I I } } = \sum _ { n = 1 , 2 , 3 , \cdots } ^ { \infty } T _ { N _ { \mathrm { c } , n } ^ { \mathrm { I I } } } \sin N _ { \mathrm { c } } ^ { \mathrm { I I } } ( \theta + \beta )
$$

由于第一部分和第二部分实际上可以看作是基本相同的两个部分，仅仅是对应永磁体极性的不同。

因此可以认定 $T _ { N _ { \mathrm { c } , n } ^ { \mathrm { I } } } = T _ { N _ { \mathrm { c } , n } ^ { \mathrm { I I } } }$ ， $N _ { \mathrm { c } } ^ { \mathrm { I } } { = } N _ { \mathrm { c } } ^ { \mathrm { I I } }$

因此电机的齿槽转矩可以表示为

$$
\begin{array} { c } { { T _ { \mathrm { c o } } = \displaystyle \frac { 1 } { 2 } \Bigg [ \sum _ { n = 1 , 2 , 3 , \cdots } ^ { \infty } T _ { N _ { \mathrm { c } , n } ^ { 1 } } \sin n N _ { \mathrm { c } } ^ { 1 } ( \theta - \beta ) + } } \\ { { { } } } \\ { { \displaystyle \sum _ { n = 1 , 2 , 3 , \cdots } ^ { \infty } T _ { N _ { \mathrm { c } , n } ^ { 1 } } \sin n N _ { \mathrm { c } } ^ { 1 } ( \theta + \beta ) \Bigg ] } } \\ { { { } } } \\ { { { } = \displaystyle \sum _ { n = 1 , 2 , 3 , \cdots } ^ { \infty } T _ { N _ { \mathrm { c } , n } ^ { 1 } } \sin n N _ { \mathrm { c } } ^ { 1 } \theta \cos n N _ { \mathrm { c } } ^ { 1 } \beta } } \end{array}
$$

根据式 (7)，要使 $n N _ { \mathrm { c } } ^ { \mathrm { I } }$ 次转矩谐波产生的齿槽转矩为零，则

$$
\begin{array} { c } { \displaystyle { \cos n N _ { \mathrm { c } } ^ { \mathrm { I } } \beta = 0 } } \\ { \displaystyle { \Rightarrow \beta = \frac { \pi } { 2 n N _ { \mathrm { c } } ^ { \mathrm { I } } } } } \end{array}
$$

# 4 有限元仿真

电机主要参数见下表。

表电机主要参数Tab.Motor major parameters  

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>永磁体内径/mm</td><td>63</td></tr><tr><td>永磁体外径/mm</td><td>75</td></tr><tr><td>定子内径/mm</td><td>77</td></tr><tr><td>定子外径/mm</td><td>140</td></tr><tr><td>气隙/mm</td><td>1</td></tr><tr><td>铁心轴长/mm</td><td>65</td></tr><tr><td>极对数p</td><td>5</td></tr><tr><td>槽数N</td><td>12</td></tr><tr><td>剩磁B,/T</td><td>1.2</td></tr><tr><td>负载电流Ir/A</td><td>100</td></tr><tr><td>额定转矩T/Nm</td><td>12</td></tr><tr><td>转速n/rpm</td><td>1000</td></tr></table></body></html>

本文给出的模型电机是10极12槽（ $\overset { \cdot } { n } = 1$ ， ${ N _ { \mathrm { c } } ^ { \mathrm { I } } } =$ 60)，根据式 (8)，槽口偏移角度为 $1 . 5 ^ { \circ }$ ，如图5所示。

图6为新型定子电机空载磁场分布图，图7为新型电机和传统电机径向气隙磁通密度的对比。通过对比可以发现，槽口的偏移同样不会影响径向磁通密度的幅值，但是会改变其位置角。图8为径向磁通密度的谐波分析，可以清晰地看到新型定子电机与传统定子电机的基波幅值与传统定子电机的基本一致，但是其谐波幅值要稍低于传统定子电机。其中传统定子电机的径向磁通密度THD值为

![](images/c71c54aec90e9eb0d964e0fb7b93021c786a2bea4afc01e25510a15f3a512294.jpg)  
图5新型定子电机剖面图

![](images/96e86c2f8877fbfbd58a8aa600e1194aff6614c197a6de9470de1a58aa636650.jpg)  
Fig.5Cross section of motor with new stators

![](images/4d3f98fa311d1546f88c44b8d2a16dd07c086a7226125761639770b56b379898.jpg)  
图6空载磁场分布  
图7径向磁通密度波形  
Fig.7Radial flux density waveform

$4 6 . 3 \%$ ，而新型定子电机的径向磁通密度THD值为$4 3 . 2 \%$ 。其气隙磁通密度的正弦性稍有提升。

图9则给出了新型定子电机与传统定子电机的齿槽转矩对比图。传统定子设计中，其电机的齿槽转矩达到 $0 . 5 5 \mathrm { N \cdot m }$ ，这在实际应用中已经很大了。然而在新型定子设计中，齿槽转矩明显减小，并且在特定的优化角度下其值小于 $0 . 1 5 \mathrm { N \cdot m }$ 。此外，图10为最大负载下新型定子电机与传统定子电机的输出转矩图。对于 $I _ { \mathrm { f } } { = } 1 0 0 \mathrm { A }$ ，额定转矩为 $1 2 \mathrm { N } \cdot \mathrm { m }$ ，其新型定子电机相应的转矩波动大约是额定转矩的 $1 . 5 \%$ ，而传统定子电机的转矩波动大约是额定转矩的 $5 . 8 \%$ 。

![](images/40be92ab6064d2409b7f2e680357a84bef64795d73083b5ddc2f7ffbc67b522f.jpg)  
图8径向磁通密度谐波分析

![](images/4e9199cf70727f5c3a0fbcf0a11bfeea14274a137f264086026077e77ef442c8.jpg)  
Fig.8Harmonic analysis of radial flux density   
图9齿槽转矩波形

![](images/ff5cd869d121b0fe30bbfa9673dca444fe10980aa3a1d487da72d8267179ed0b.jpg)  
Fig.6No-load field distribution   
Fig.9The cogging torque waveform   
图10 负载转矩波形  
Fig.10The load torque waveform

# 5 结束语

针对模块化永磁电机齿槽转矩的削弱，本文提出并讨论了一种新的定子设计方案，通过槽口的不对称结构来降低齿槽转矩分量，让槽口从其原本的位置左右偏移，致使齿槽转矩波在类似方向发生位移。因此有一个合适的移动角度，能够使总齿槽转矩明显减小。此外，新给出的定子设计同样能够减小转矩波动，并且新的定子设计生产与偏移较其他方法相比更加简单、廉价。

# 参考文献

[1] Li G J, Ren B, Zhu Z Q. Cogging torque mitigation of modular permanent magnet machines[J]. IEEE Transactions on Magnetics, 2016,52(1): 3238-3247.   
[2] 张炳义，贾宇琪，冯桂宏．新型模块组合式定子永 磁电机[J]．电工技术学报，2015，30(12)：243- 252. Zhang Bingyi, Jia Yuqi,Feng Guihong.Novel permanent magnet synchronous machines with modules combination stator[J]. Transactions of China Electrotechnical Society, 2015,30(12): 243-252.   
[3] Islam R,Husain I, Fardoun A,et al.Permanent magnet synchronous motor magnet designs with skewing for torque ripple and cogging torque reduction[J].IEEE Transactions on Industry Applications,2009,45(1): 152-160.   
[4] Zhu Ziqiang, Howe D.Influence of design parameters on cogging torque in permanent magnet machines[J]. IEEE Transactions on Energy Conversion, 2000, 15(4): 407-412.   
[5] 刘婷，欧阳红林，黄守道．基于重复单元削弱永 磁风力发电机齿槽转矩[J]．电工技术学报，2011, 26(12): 43-48. Liu Ting,Ouyang Honglin,Huang Shoudao. Reducing cogging torque in permanent magnet wind power generators based on unit[J].Transactions of China Electrotechnical Society,2011, 26(12): 43-48.   
[6] Zhu Li, Jiang Suzhe,Zhu Ziqiang.Analytical methods for minimizing cogging torque in permanent-magnet machines[J].IEEE Transactions on Magnetics, 2009,45(4): 2023-2030.   
[7] Zhu Ziqiang,Howe D. Influence of design parameters on cogging torque in permanent magnetmachines[J]. IEEE Transactions on Energy Conversion, 2000, 15(4): 407-412.   
[8] Yang Yubo,Wang Xiuhe, Zhang R. The optimization of pole arc coefficient to reduce cogging torque in surface-mounted permanent magnet motors[J]. IEEE Transactions on Magnetics,2006,42(4): 1135-1138.   
[9] Jiang Xinting,Xing Xiuwan,Ling Yin. Theoretical and simulation analysis of influences of stator tooth width on cogging torque of BLDC motors[J]. IEEE Transactions on Magnetics,2009,45(10): 4601- 4604.   
[10] Lateb R,Takorabet N,Meibody T F.Effect of magnet segmentation on the cogging torque in surface-mounted permanent-magnet motors[J]. IEEE Transactions on Magnetics,2006,42(3): 442-445.   
[11] Zhu Ziqiang,Ishak D.Analysis of cogging torque in brushless machines having non-uniformly distributed stator slots and stepped rotor magnets[J]. IEEE Transactions on Magnetics,2005, 41(10): 3910- 3912.   
[12] Zhu Ziqiang, Howe D. Synthesis of cogging-torque waveform from analysis of a single stator slot[J]. IEEE Transactions on Industry Applications, 2006, 42(3): 650-657.   
[13]杨玉波，王秀和，张鑫．磁极偏移削弱永磁电机 齿槽转矩方法[J]．电工技术学报，2006，21(10)： 22-25. Yang Yubo, Wang Xiuhe, Zhang Xin. Cogging torque reduction method of magnet shifting in permanent magnet motors[J]. Transactions of China Electrotechnical Society, 2006,21(10): 22-25.