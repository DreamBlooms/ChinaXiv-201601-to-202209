# 改变蜗壳结构对离心风机性能及噪音的影响

雷乐1，谭俊飞²，李景银1(1．西安交通大学能源与动力工程学院，西安710049;2．中冶赛迪工程技术股份有限公司，重庆400013)

摘 要：利用 Ansys Fluent 软件进行数值模拟，通过分别改变蜗壳宽度和蜗舌倾角的方法，详细研究了改变蜗壳结构对离心风机气动性能及声功率级的影响。研究结果显示，在离心风机设计推荐范围内存在最佳蜗壳宽度，使得离心风机的声功率级最低；增加蜗壳宽度，离心风机的全压、效率略有下降，静压升高；固定离心风机蜗壳后盖板蜗舌半径 $R _ { 1 }$ ，增大蜗壳前盖板蜗舌半径$R _ { 2 }$ ，能有效的降低离心风机的声功率级；在降噪效果上，改变蜗舌间隙优于改变蜗舌倾角。

关键词：离心风机；声功率级；倾斜蜗舌；蜗壳宽度；

中文分类号：TH43 文献标识码：A

# Effect of Volute Configuration on Aerodynamic Performance and Noise Level of the Centrifugal Fan

LEI Le’, TAN Jun-fei², LI Jing-yin’

(1.School of Energy and Power Engineering,Xi'an Jiaotong University,Xi'an 710o49, China; 2. Cisdi Engineering Co.,Ltd., Chongqing 400013, Chia)

Abstract: The efect of the variation in volute widths and inclining angles of the volute tongue on the aerodynamic characteristics and sound power levels ofa centrifugal fan was simulated and analyzed by using Ansys Fluent. It is found thatthere is an optimal volute width leading to the lowest sound power level within the recommended range of design parameters.And an increase in the volute width leads to an increase in the static pressure with a slight decrease in the total pressure and effciency. In addition,the sound power level can be reduced by fixing the volute tongue radius $R _ { 1 }$ at the volute rear plate and increasing its radius $R _ { 2 }$ at the volute front plate. Changing the volute tongue clearance has a better noise reduction effect than the variation of the inclining angle.

Key words: centrifugal fan; sound power level; inclined volute tongue; volute width

# 0引言

离心风机广泛应用于国民经济的各个领域，据统计离心风机每年的耗电量在全国年发电总量中所占比例约为 $5 \%$ ，但这些投入运行的风机中，很多效率偏低，噪音偏高。

现有的研究表明[1,2]，由于叶轮出口的尾迹气流与蜗壳存在着强烈的非定常干涉，使得离心风机蜗壳、特别是蜗舌部位成为风机的主要噪声源，所以改变蜗壳结构是非常具有针对性的降噪方法。

诸多学者对此进行了研究，并提出各种改变蜗壳结构的方法来降低离心风机的噪声，如增加蜗壳宽度[3]、采用吸声蜗壳[4]、采用阶梯蜗舌[5]、优化蜗壳出口[]、采用倾斜蜗舌[]、增大叶轮与蜗舌间隙[8]等，其中增加蜗壳宽度和倾斜蜗舌是最常用的方法。

本文以某型应用在动车机组上的离心风机为模型，研究增加蜗壳宽度、采用倾斜蜗舌对离心风机气动性能及声功率级的影响。

# 1离心风机气动性能及声功率级的数

# 值模拟

本文采用AnsysFluent模拟离心风机的气动性能与噪声。首先对离心风机进行建模和网格划分，进行定常计算获得风机气动性能；以定常计算结果为初值进行非定常计算，获取风机的声源信息，待非定常计算收敛后，利用FW-H方程，预测风机噪音。

# 1.1离心风机模型的建立及网格划分

离心风机包含集流器、叶轮和蜗壳三部分，采用ICEMCFD软件进行高质量的六面体结构网格划分。叶轮、集流器、蜗壳的网格数分别约为96万、16万、87万，整机网格数约为199万。

# 1.2离心风机气动性能及噪音预测

# 1.2.1离心风机气动性能预测

当网格划分完成后，利用AnsysFluent进行数值计算。风机内部气流最大马赫数小于0.3，属于不可压缩流动范畴，因此计算过程中密度不变。定常计算中采用多重参考系(MRF)进行求解。模拟过程中，风机进口边界条件采用Mass-flow-inlet，给定设计工况点的均匀质量流量，出口边界条件设定为Pressure-outlet。湍流模型选用Realizable $\operatorname { k } \mathbf { - } { \mathcal { E } }$ 模型，为了避免壁面过度加密，选用Scalable壁面函数。

# 1.2.2离心风机气动噪声预测

将定常计算得到的结果作为初值，进行非定常计算。非定常计算过程中，采用滑移网格（SlidingMesh）模拟动静干涉。非定常过程中时间步长按照公式（1）计算：

$$
\Delta t = \frac { 6 0 } { n K Z }
$$

式中： $n$ 一转速 $/ \mathrm { r p m }$ ： $K$ 一单流道计算步数，本文取$K { = } 3 0$ ; $Z$ 一叶片数。

使用FW-H方程来预测噪音；忽略四极子源的影响；计算完成后，对计算得到的关于时间的离散声压进行FFT变换，得到监测点上的线性声压级。

# 1.2.3利用声压级合成声功率级

本文是根据国际标准ISO3745采用包络面法，通过在包围离心风机的包络面上布置20个检测点，通过测量检测点上的声压级，通过以下公式来合成声功率级。

$$
{ \cal L } _ { p f } = 1 0 \log \left[ { \frac { 1 } { 2 0 } } { \sum _ { i = 1 } ^ { 2 0 } } { 1 0 } ^ { 0 . 1 L _ { p i } } \right]
$$

$$
L _ { \mathrm { } _ { w } } = L _ { \mathrm { } _ { p f } } + 1 0 \log { \frac { S _ { 1 } } { S _ { 0 } } }
$$

式中： $L _ { p i }$ —表示各个检测点的声压级/dB； $L _ { w }$ 一表示声功率级/dB； $S _ { 1 }$ 一包络面的面积 $/ \mathrm { m } ^ { 2 }$ ; $S _ { 0 }$ 一参考面积$/ \mathrm { m } ^ { 2 }$ 。

# 2蜗壳宽度对离心风机气动性能及声功率级的影响

现有经验已知，增加蜗壳宽度能够有效的降低离心风机的基频噪声，增加宽频噪声[3]。现利用数值模拟的手段，确定最佳的蜗壳宽度，使得风机的声功率级最低。本文从蜗壳后盖板侧增大蜗壳宽度，风机原始蜗壳宽度 $B { = } 1 0 8 ~ \mathrm { m m }$ ，依次增加蜗壳宽度到$1 1 4 \mathrm { m m }$ 、 $1 2 0 \mathrm { m m }$ 、 $1 2 6 \mathrm { m m }$ 、 $1 3 2 \mathrm { m m }$ 。

图1表示在设计流量下，不同蜗壳宽度下风机静压、全压和效率的变化。分析可知，随着蜗壳宽度的增大，风机的静压逐渐增大，全压缓慢减小。当蜗壳宽度为 $1 0 8 ~ \mathrm { { m m } }$ 时，风机的全压值为 $3 8 3 5 . 0 4 \mathrm { P a }$ ，蜗壳宽度增大到 $1 3 2 \mathrm { m m }$ 时，全压值为 $3 7 9 8 . 2 7 \mathrm { P a }$ ，变化很小。风机的全压效率随着蜗壳宽度的增加也缓慢下降；但当蜗壳宽度增大到 $1 2 6 ~ \mathrm { m m }$ 后，效率下降速度开始增大。蜗壳宽度为 $1 0 8 ~ \mathrm { { m m } }$ ，效率为0.819，蜗壳宽度为 $1 2 6 \mathrm { m m }$ ，效率为0.816，几乎没有变化；继续增大蜗壳宽度到 $1 3 2 ~ \mathrm { m m }$ ，效率相比原模型也仅减少了 $0 . 0 9$ 。总的来说，蜗壳宽度从 $1 0 8 \mathrm { m m }$ 增大到126$\mathrm { m m }$ ，全压、效率变化不大。

![](images/173fb7344fa134b4f8343ee084ff1c685aceff9b0b8dba9bc49d8932a21521ee.jpg)  
图1不同蜗壳宽度下风机的气动性能  
Fig.1Aerodynamiccharacteristicsof fanswithdifferent volute

width

图2表示不同宽度下离心风机的声功率级的变化。分析可知，声功率级随着蜗壳宽度的增加，先减小后增大；在蜗壳宽度为 $1 2 0 ~ \mathrm { m m }$ 时，声功率级取得最小值107.64dB，较初始声功率级降低了1.86dB。离心风机的声功率级先减小后增大是因为离心风机的基频噪声随宽度的增加而减小，而宽频噪声随蜗壳宽度增大而增大。蜗壳宽度稍微增加，基频噪声下降对整个风机声功率级的作用要强于宽频噪声增大的作用，导致整体的声功率级下降，继续增大蜗壳宽度，则刚好相反。

![](images/3ea41f6d16761b51d41dcd7212e1e70823c980baec766337b996b08eae056a47.jpg)  
图2不同蜗壳宽度下风机的声功率级

Fig.2Sound powerlevels of the fanswith different volute width

# 3倾斜蜗舌对离心风机气动性能及声功

# 率级的影响

采用倾斜蜗舌，可以降低离心风机的基频及高次谐波的峰值[7，从而降低离心风机的噪音。本文采用的倾斜蜗舌为蜗壳前盖板侧的蜗舌半径 $R _ { 2 }$ 大于后盖板侧的蜗舌半径 $R _ { 1 }$ 。

固定蜗壳后盖板上蜗舌半径 $R _ { 1 } { = } 2 8 ~ \mathrm { m m }$ ，增大蜗壳前盖板上的蜗舌半径 $R _ { 2 }$ 至结构允许的最大值$R _ { 2 } { = } 6 0 \ \mathrm { m m }$ ，即蜗舌倾角 $\theta$ 为 $1 5 ^ { \circ }$ 。分别计算了平蜗舌和倾斜蜗舌 $\theta$ 为 $1 5 ^ { \circ }$ 时的气动性能和声功率级，计算结果见表1。

# 表1两种蜗舌倾角下气动性能和声功率级对比

Table 1 Aerodynamic characteristics and sound power levels of the fans with different inclining angles   
of the volute tongue   

<html><body><table><tr><td>0/0</td><td>Pst/Pa</td><td>Ptot/Pa</td><td>n</td><td>Lw/dB</td></tr><tr><td>0</td><td>3475.72</td><td>3827.29</td><td>0.817</td><td>107.64</td></tr><tr><td>15</td><td>3396.87</td><td>3751.15</td><td>0.804</td><td>105.56</td></tr></table></body></html>

分析表1可知，当蜗舌倾角 $\theta$ 为 $0 ^ { \circ }$ ，计算得到的全压为 $3 8 2 7 . 2 9 \mathrm { \ P a }$ ，效率为0.817，声功率级为107.64dB；增加蜗舌倾角 $\theta$ 到 $1 5 ^ { \circ }$ ，全压为3751.15Pa，下降了 $7 6 . 1 4 \ \mathrm { P a }$ ，效率相比下降0.013，计算声功率级为 $1 0 5 . 5 6 ~ \mathrm { d B }$ ，相比下降了 $2 . 0 8 \mathrm { d B }$ 。

固定蜗壳后盖板上的蜗舌半径 $R _ { 1 }$ ，增大前盖板的蜗舌半径 $R _ { 2 }$ 可以将风机的声功率级降低 $2 . 0 8 \mathrm { d B }$ 。但这种方法会受到蜗壳出口长度限制，导致蜗舌倾角只能做到 $1 5 ^ { \circ }$ 。为了进一步增大蜗舌倾角 $\theta$ ，只有减小蜗壳后盖板的蜗舌半径 $R _ { 1 }$ ，而保持前盖板蜗舌半径 $R _ { 2 } { = } 6 0 \ \mathrm { m m }$ 不变。表2表示蜗壳前盖板的蜗舌半径 $R _ { 2 } { = } 6 0 \ \mathrm { m m }$ ，不同蜗舌倾角 $\theta$ 对应的后盖板 $R _ { 1 }$ 。

表2不同舌倾角对应的蜗壳前后盖板蜗舌半径 Table 2 Radius of the incling volute tongue at the volute front and rear plates   

<html><body><table><tr><td>01</td><td>R2/mm</td><td>R1/mm</td></tr><tr><td>15</td><td>60</td><td>28</td></tr><tr><td>20</td><td>60</td><td>23.4</td></tr><tr><td>25</td><td>60</td><td>16.1</td></tr></table></body></html>

图3表示不同蜗舌倾角下风机的静压、全压和效率的变化。分析可知，通过固定蜗壳前盖板蜗舌半径 $R _ { 2 }$ ，改变蜗壳后盖板蜗舌半径 $R _ { 1 }$ 的方式增大蜗舌倾角，风机的静压和全压都随着倾角的增大而增大。蜗舌倾角为 $1 5 ^ { \circ }$ ，静压为 $3 3 9 6 . 9 \mathrm { P a }$ ，全压为3751.2Pa；增大蜗舌倾角到 $2 5 ^ { \circ }$ ，静压相对增加了 $1 . 4 \%$ 即约 $5 0 \ \mathrm { P a }$ ，全压增加了约 $0 . 7 \%$ ，即 $2 8 \mathrm { P a }$ 。效率随着蜗舌倾角的增大而略微增大：蜗舌倾角为 $1 5 ^ { \circ }$ ，计算出的离心风机效率为0.804；增大蜗舌倾角到 $2 5 ^ { \circ }$ ，效率仅仅增加了0.007，增幅很小。

![](images/e7f4c4fa70c9eadb95d05eda3f84969eb00cc3a7e5e26888663d08a73b082029.jpg)  
图3不同蜗舌倾角下风机的气动性能  
Fig.3Aerodynamic characteristics of fans with different inclining angle of the volute tongue

图4表示不同蜗舌倾角下风机的声功率级的变化。分析图4可知，通过固定 $R _ { 2 }$ 、减小 $R _ { 1 }$ 的方式倾斜蜗舌，离心风机的声功率级是随着蜗舌倾角 $\theta$ 的增大而增大。蜗舌倾角 $\theta$ 为 $1 5 ^ { \circ }$ ，声功率级为105.56dB，增大蜗舌倾角 $\theta$ 到 $2 5 ^ { \circ }$ ，声功率级增大到106.7dB。固定蜗壳前盖板蜗舌半径 $R _ { 2 }$ ，减小蜗壳后盖板蜗舌半径 $R _ { 1 }$ 来增大蜗舌倾角这种方式，会导致叶轮出口跟蜗舌之间的距离减小，这或许是离心风机整体声功率级增大的原因。由此我们可以推测，增加蜗舌间隙降噪跟增加蜗舌倾斜角度降噪相比，前者更有效果。

![](images/d94012b30151c1f2b5ef41754117154c64008d9d923d7d4ba9a3a73e50c7baf6.jpg)  
图4不同蜗舌倾角下风机的声功率级 Fig.4 Sound power levels of the fans with different inclining angles of the volute tongue

# 4结论

本文采用数值模拟的方法，研究了增加蜗壳宽度、改变倾斜蜗舌角度对离心风机气动性能及声功率级的影响。结果显示：

1.在离心风机蜗壳的推荐宽度范围内，存在最佳宽度，使得离心风机的声功率级最低。2.增加蜗壳宽度，离心风机的全压、效率稍微下降，静压升高。3.固定离心风机蜗壳后盖板蜗舌半径 $R _ { 1 }$ ，增大蜗壳前盖板蜗舌半径 $R _ { 2 }$ ，能有效降低离心风机的声功率级；反之，固定离心风机蜗壳前盖板蜗舌半径 $R _ { 2 }$ 通过减小蜗壳后盖板侧的蜗舌半径 $R _ { 1 }$ 的方法来增大蜗舌倾角，却会增加离心风机的噪音。

4.在降噪效果上，蜗舌间隙优于蜗舌倾角。

# 参考文献

[1]Liu Q,Qi D，Tang H. Computation of Aerodynamic Noise of Centrifugal Fan Using Large Eddy Simulation Approach,Acoustic Analogy,and Vortex Sound Theory[J]. Proceedings of the Institution of Mechanical Engineers,Part C:Journal of Mechanical Engineering Science. 2007, 221(11):1321-1332.   
[2]毛义军，祁大同，徐长棱等．叶片与蜗舌耦合对离心风 机性能和旋转噪声影响的数值研究[J]．应用力学学 报．2006，23(3):368-372. MAO Yijun, Qi Datong, Xu Changleng, et al. Effect of Interaction between Centrifugal Impeller and Volute Tongue on the Performance and BPF Noise[J].Chinese Journal of Applied Mechanics.2006，23(3): 368-372.   
[3] 刘晓良，祁大同，马健峰等．改变蜗壳宽度对离心风机 气动噪声影响的数值计算与试验研究[J]．西安交通大学 学报．2008，42(11):1429-1434. LIU Xiaoliang, QI Datong, MA Jianfeng, et al. Numerical and Experimental Study of the Impact on the Aerodynamic noise of the Centrifugal Fan by Changing the Volute Width [J]. Journal of Xi'an Jiaotong University,2008，42(11): 1429-1434.   
[4]Gu Y,Qi D,Mao Y,et al. Theoretical and Experimental Studiesonthe Noise Control of Centrifugal Fans Combining Absorbing Liner and Inclined Tongue[J]. Proceedings of the Institution of Mechanical Engineers, Part A: Journal of Power and Energy. 201, 225(6): 789-801.   
[5]李栋，顾建明．阶梯蜗舌蜗壳的降噪分析和实验[J]．流 体机械．2004，32(2). LI Dong, GU Jianming. Practice and Analysis to Reduce the Fan Noise with Step-tongue Volute[J].Fluid Machinery. 2004，32(2).   
[6]刘晓良，袁民建，毛义军等．前向离心风机蜗壳出口结 构的数值优化[J].西安交通大学学报.2009,43(5):61-65. LIU Xiaoliang，YUAN Minjian，MAO Yijun, et al. Numerical Optimization of Volute Outlet Structure for Forward-Curved Centrifugal Fan[J]. Journal of Xi'an Jiaotong University. 2009，43(5): 61-65.   
[7]赵婷，赵忖，任刚等．倾斜蜗舌对离心风机降噪影响的 试验研究[J]．流体机械．2012，40(3)：1-7. ZHAO Ting, ZHAO Cun,REN Gang,et al. Experimental Study on the Effect of Inclined Volute Tonue on the Noise Reduction of Centrifugal Fan[J].Fluid Machinery. 2012, 40(3): 1-7   
[8]Datong Q, Yijun M, Xiaoliang L, et al. Experimental Study on the Noise Reduction of an Industrial Forward-curved Blades Centrifugal Fan[J]. Applied Acoustics.20o9,70(8): 1041-1050.   
第一作者：雷乐   
通讯地址：陕西省西安市咸宁西28号西安交通大学1614信箱   
手机号码：15191487157   
电子信箱：leile2014@163.com