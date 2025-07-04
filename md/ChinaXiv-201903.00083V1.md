# 基于集总参数热网络法的永磁同步电机温度场分析

![](images/ede0b9725682a530b448bc4836f8cf91f98c702fa5e917e948ea4e1c55074d94.jpg)

兰志勇 魏雪环李虎如 廖克亮陈麟红（湘潭大学信息工程学院 湘潭411105)

兰志勇男 1980年生，博士，主要研究方向为大功率永磁同步电机设计及优化、无刷直流电机设计及优化、精密伺服驱动器的研究与开发等。

摘要：永磁同步电机与其他类型电机相比性能指标尤为突出，被广泛应用于各个领域。随着电机制造业的发展，电机单机容量增加，使电机内部温升过高，影响电机的性能与可靠运行。本文在考虑高速电机永磁体涡流损耗对电机温度场的影响的情况下，用集总参数热网络法（LPTN）对永磁同步电机进行温度场分析，建立38节点的热网络模型，真实反映了电机各部件的温升。最后，通过与有限元法（FEM）分析结果、电机温升试验结果对比，证明该热网络计算模型的正确性。

关键词：永磁同步电机 温度场 集总参数热网络法有限元法中图分类号：TM351

# Thermal Analysis ofPMSM Based on Lumped Parameter Thermal Network Method

Lan ZhiyongWei Xuehuan Li Huru Liao Keliang Chen Linhong (Xiang Tan UniversityXiangtan411105 China)

![](images/6e7377ace10fa16ecc213855d32ce1163b9112a8b1dd352649bb597f62fbe72a.jpg)

魏雪环女 1990年生，硕士研究生，主要研究方向为永磁同步电机及异步电机的温度场分析及优化等。

Abstract: The performance targets of PMSM are prominent, compared to other type motors,PMSM are widely used in various fields.With the development of the motor manufacturing industry, the motor capacity increases,resulting in increasing temperature of inside the motor, the high temperature severely affected performance and reliable operation of motor.In this paper, in consideration of the influence of the permanent magnet eddy current loss of high speed motor on the temperature field, thermal analysis using LPTN in PMSM, the thermal network model of 38 nodes is established. truly reflect the temperature rise of each part of the motor. Finally, the correctness of the model is verified by comparison with the results of finite element method (FEM) and temperature rise test.

Keywords: Permanent magnet synchronous motor, temperature field, lumped parameter thermal network, finite element method

# 1 引言

近年来，由于永磁同步电机具有体积小、容量大且效率高等优势，在各个领域得到了广泛的应用。随着电机功率密度的提高和电机材料的充分利用，电机经常处于电负荷和磁负荷的极限状态，导致电机的损耗变大，引起电机的温升过高。对于永磁电机而言，过高的温度容易使永磁体发生不可逆退磁，影响电机的性能和可靠运行[1]。因此，对电机温度场的分析尤为重要。

目前，常用的电机温升计算方法有有限元法(FEM)、集总参数热网络法（LPTN）和流体力学(CFD)。FEM和CFD都是数值计算方法，可以通过计算机分析得到电机整体温度的分布云图[2-3]。但是，对于当前的计算机设备用这两种方法计算，耗时也很长。LPTN法则通过将电机相似部位以节点的形式划分为几个部分，借助电路的思想，通过热阻及温度计算公式，得到电机内部各节点的温度。由于热阻的计算方法相似，LPTN对于不同的电机模型也能做相应的简化和拓展。相较于FEM和CFD，该方法节省了很多时间，计算时间上具有较大优势。

LPTN在感应电机和同步电机的温度场分析及其优化过程中都有应用，文献[4]用LPTN对电机进行了温度场分析，本文在其基础上添加了6个端盖节点、两个轴承节点和3个转轴节点，使电机的网格结构更加规则，更符合电机传热的实际情况。并在考虑永磁体涡流损耗的基础上用LPTN对电机进行温度场分析与计算。最后，与FEM分析结果及电机温升试验结果对比，验证该方法的有效性。

# 2集总参数热网络法（LPTN）

LPTN是将电机的主要部件按照其各自结构及发热散热情况划分成多个温度单元，并通过热导将各个单元联系起来，使电机内部温度场离散为等效热网络，编写Matlab计算程序，对电机各部分温度进行求解，得到电机的平均温升分布情况。

# 2.1分析过程

用LPTN对电机进行温度场分析计算时，需要对电机的计算模型进行合理的假设，如下：

(1）电机的温度分布周向对称，同时认为电机在圆周方向的冷却条件相同。

(2）电机内部两侧的空腔中，各点的空气温度相同，计算时可以用一个点计算。

(3）忽略定子槽部绕组的趋肤效应。  
(4）两个节点间的互导相等，并与温升无关。  
(5）忽略电机的辐射传热过程。  
LPTN的温度场分析过程如图1所示。

![](images/428bc4f620913ac547508e24e71387805f2a0ef051ebd33691f2fddde02eb723.jpg)  
图1LPTN热分析过程

# 2.2热网络模型

LPTN的热网络模型是二维模型，不仅可以考虑轴向热传递，也可以考虑径向热传递。

本文以十二极三相永磁同步发电机为分析实例，其具体参数为：额定功率 $3 2 0 \mathrm { k W }$ ；额定转速$6 ~ 0 0 0 \mathrm { r / m i n }$ ；定子外径 $0 . 4 \mathrm { m }$ ，定子内径 $0 . 2 8 5 \mathrm { m }$ ；转子外径 $0 . 2 8 2 \mathrm { m }$ ，转子内径 $0 . 1 \mathrm { m }$ ，电机模型如图2所示。电机轴向简化模型及各部件间的热阻分布如图3所示。

![](images/a2cd388dc5cd74d065d8929adf469c6d78da2bf2db6faf3e651abd3ad179d9a3.jpg)  
Fig.1Thermal analysis process of LPTN   
图2 电机模型  
Fig.2Motor model

由图3的电机各部件轴向热阻分布关系可知，电机的每个相邻部件都通过热阻有相应的联系。热阻是传导热阻和对流热阻，为

$$
R _ { \mathrm { c o n d u c t i o n } } = { \frac { l } { A \lambda } }
$$

$$
R _ { \mathrm { c o n v e n t i o n } } = { \frac { l } { A _ { \mathrm { { c } } } \lambda } }
$$

式中， $l$ 为两节点间距离； $A$ 为接触面面积； $A _ { \mathrm { c } }$ 为对流截面积。

国

由上述分析，对样机轴向分布进行网格划分，在各区域中心设立节点，使网格剖分保持整齐，保证计算精度，要充分考虑电机的结构、材料和工艺等因素。沿轴向把定转子划分成均等三份，样机的热网络模型节点分布如图4所示。其中，a-e，5个节点为电机机壳表面节点、1-5为机壳节点、6-8为定子轭部节点、9-13为绕组节点、14-16位定子齿部节点、17-19为永磁体节点、20-22为转子节点、23-24为机腔空气节点、25-30为转轴节点（节点30为轴承节点）、31-33为前端盖节点、34-36为后端盖节点、37-38为轴承节点。

![](images/21730b30bc2da31614c01c49abb5faad8df6a0160ccb1ca7cfaa232e9014dc04.jpg)  
图3 电机轴向热阻分布  
Fig.3Distribution of axial thermal resistance   
图4热网络模型节点分布  
Fig.4Node distribution of thermal network model

# 2.3 热源分析

# 2.3.1热源计算

热源与电机温度场的求解密不可分，它与电机的各部分损耗有关。永磁同步电机的损耗，主要包括定子铁耗、绕组铜耗和机械损耗，这些损耗都可根据经验公式进行计算[5-6]。一般情况下，大多数的电机温度场分析忽略了永磁体涡流损耗对温度场分布的影响，如文献[7]虽然对永磁体涡流损耗进行了分析，但并没有分析永磁体涡流损耗对电机温度场的影响。然而，对于对温度较为敏感的永磁体材料而言，永磁体涡流损耗所导致的温升是不能忽略的。

根据二维有限元涡流损耗分析方法，在时域内磁场方程为[8]

$$
\nabla \frac { 1 } { \mu } ( \nabla A _ { Z } ) = J - \sigma \Bigg ( \frac { \partial A _ { Z } } { \partial t } + \nabla E \Bigg ) + \nabla H _ { \mathrm { c } }
$$

式中， $\mu$ 为相对磁导率； $\mathbf { \nabla } A _ { \mathrm { Z } }$ 为磁位矢量； $J$ 为电流密度； $\sigma$ 为材料导电率； $E$ 为电势标量； $H _ { \mathrm { C } }$ 为永磁体矫顽力。

绕组中的电流密度

$$
J = - { \boldsymbol { \sigma } } \left( { \cfrac { \mathrm { d } { \boldsymbol { A } } } { \mathrm { d } t } } - \nabla E \right)
$$

当磁场发生变化时，会在导电材料内部产生感应电流，该电流为涡流。涡流产生的损耗即涡流损耗为

$$
P = \underset { Z } { \int } { \left( \frac { \left| J _ { _ Z } \right| } { \sigma } \right) } \mathrm { d } s
$$

式中， $J _ { Z }$ 为轴方向的电流密度分量。

2.3.2 热源分布

(1）绕组铜耗分布。铜耗分为槽部和端部损耗，其取值与槽部和端部的绕组长度成正比。

槽部损耗的表达式为

$$
P _ { \mathrm { C u s } } = P _ { \mathrm { C u } } { \frac { L } { L _ { \mathrm { Z } } } }
$$

端部损耗的表达式为

$$
P _ { \mathrm { C u e n d } } = P _ { \mathrm { C u } } { \frac { L _ { \mathrm { s } } } { L _ { \mathrm { Z } } } }
$$

式中， $L$ 为定子铁心长； $L _ { z }$ 为绕组半匝长； $L _ { \mathrm { s } }$ 为绕

组端部伸出端。

(2）定子铁耗分布。本文通过AnsoftMaxwell软件对电机齿部和轭部磁密进行分析，如图5所示。根据齿部和轭部的质量比值，可以计算得到样机齿部与轭部的铁耗，见表1。

1000 800   
LU/ 600   
B 400 200 0 0 20 40 60 80 100 120 D/mm (a）轭部磁密 2.0 1.6 Jn 1.2 T B 0.8 0.4 0 0 10 20 30 40 50 60 70 80 90 D/mm (b）齿部磁密

$$
R _ { 3 1 3 7 } = \frac { B _ { \mathrm { c } } } { 2 \lambda _ { \mathrm { c } } S _ { 3 1 3 7 } } + \frac { L _ { \mathrm { d g } } } { 2 \lambda _ { \mathrm { d g } } S _ { 3 1 3 7 } }
$$

式中， $B _ { \mathrm { c } }$ 为轴承厚度； $\lambda _ { \mathrm { c } }$ 为轴承导热系数； $L _ { \mathrm { d g } }$ 为端盖厚度； $\lambda _ { \mathrm { d g } }$ 为端盖导热系数。

(2）节点32的热阻计算。端盖节点32与机腔内空气节点23、端盖节点31、节点33存在热交换，还与电机外部空气存在对流散热。此处只介绍与节点23的热阻。

$$
R _ { 3 2 2 3 } = \frac { L _ { \mathrm { f r } } - L - 2 L _ { \mathrm { d g } } } { 4 \lambda _ { \mathrm { a } } S _ { 3 1 3 7 } } + \frac { L _ { \mathrm { d g } } } { 2 _ { \mathrm { S } 3 2 2 3 } }
$$

式中， $L _ { \mathrm { f r } }$ 为机壳长度。

# 2.4.2轴承散热

以节点37为例，节点37与转轴节点25、机壳节点31存在热交换。

节点37与转轴节点25的热阻为

$$
R _ { 3 7 2 5 } = { \frac { D _ { 4 } } { 2 \lambda _ { \mathrm { s i } } S _ { 3 7 2 5 } } } + { \frac { D _ { \mathrm { c } } - D _ { 4 } } { 2 \lambda _ { \mathrm { c } } S _ { 3 7 2 5 } } }
$$

# 表1定子铁耗分布

Tab.1 Iron loss distribution of stator   

<html><body><table><tr><td>定子轭部损耗/W</td><td>定子齿部损耗/W</td><td>总损耗</td></tr><tr><td>1369</td><td>1 241</td><td>2610</td></tr></table></body></html>

# 2.4热阻计算

用LPTN对电机进行温度场分析计算过程中，最关键的因素在于各个节点间热阻的计算，它直接关系到整个计算结果的准确性。各个节点是否有热阻连接，主要由电机各部位的散热路径决定。电机散热部分主要包括机壳散热、定子散热和转子散热，文献[9]中介绍了简单的对流传热和热传导计算公式。

一般情况的LPTN热模型忽略了电机的端盖节点，假设电机轴承产生的热量为零，即认为其损耗为零。但对于高速电机而言，轴承损耗较大，忽略轴承损耗将会增大电机温度场计算的误差。因此，在以往LPTN热模型的基础上，添加6个端盖节点和2个轴承节点，更能反映电机传热的实际情况。

# 2.4.1端盖散热

（1）节点31的热阻计算。节点31与端盖节点32、轴承节点37和机外空气进行热传导。与节点32、节点37为简单的热传导。

# 2.5热平衡方程

根据上述分析，通过电机内部各节点间的热传递关系，可以得到电机所有节点的热平衡方程组，其矩阵形式为

$$
G T = W
$$

式中， $G$ 为38阶热导矩阵； $T$ 为 $3 8 \times 1$ 温度列矩阵； $\mathbf { \mathcal { W } }$ 为 $3 8 \times 1$ 损耗列矩阵。

# 2.6 LPTN计算程序

在得到电机各节点间的热平衡方程后，需用Matlab编写LPTN计算程序，主要包括原始数据输入、热阻计算、温度矩阵计算和数据输出，从而得到各节点温度。对于不同的电机模型，可以快速地修改部分程序语言，得到电机的温升分布，体现了LPTN的简易性和拓展性。

# 3样机温升计算结果对比

文献[10]用FEM对样机温度场进行计算，并分析了永磁体涡流损耗对电机温度场分布的影响。可得到FEM和LPTN对样机温度场分析的结果，见表2。

由表2可明显看出，在永磁体温度的计算上，两种方法的计算结果误差最大，主要在于气隙处理方法的不同。FEM将气隙等效为导热系数一定的固

# 表2计算结果

# 表3结果对比

Tab.2 Calculation result   

<html><body><table><tr><td>平均温升</td><td>LPTN</td><td>FEM</td><td>误差(%)</td></tr><tr><td>定子轭/℃</td><td>86.924</td><td>85.126</td><td>2.1</td></tr><tr><td>定子齿/℃</td><td>89.289</td><td>87.617</td><td>1.9</td></tr><tr><td>绕组/℃</td><td>90.653</td><td>89.051</td><td>1.8</td></tr><tr><td>永磁体/℃</td><td>50.147</td><td>48.208</td><td>4.0</td></tr><tr><td>转子轭/℃</td><td>48.273</td><td>46.836</td><td>3.1</td></tr><tr><td>轴承/℃</td><td>59.409</td><td>58.213</td><td>2.1</td></tr><tr><td>端盖/℃</td><td>43.302</td><td>42.564</td><td>1.7</td></tr><tr><td>机壳/℃</td><td>39.612</td><td>38.781</td><td>2.1</td></tr></table></body></html>

体材料，并通过等效计算公式计算气隙的等效导热系数；而LPTN则通过经验计算公式计算出流－固间的对流热阻，然后进行温升计算。因此，由于对气隙处理方式的不同导致永磁体的散热情况不同，也直接影响了转子轭部的温度分布情况。但在误差允许的范围内，有限元法和集总参数热网络法的计算结果一致。

# 4 样机温升试验

$3 2 0 \mathrm { k W }$ 样机测试实物如图6所示。为了验证FEM法和LPTN法计算结果的正确性，需对样机进行温升测试。将5个热敏电阻预先埋入5个定子槽内，对样机的绕组温升进行测试，用红外线温度传感器对样机机壳进行测温，可以得到机壳的平均温升。

Tab.3 Comparison results   

<html><body><table><tr><td>平均温升</td><td>LPTN</td><td>FEM</td><td>测试结果</td></tr><tr><td>绕组/℃</td><td>90.7</td><td>89.1</td><td>91.5</td></tr><tr><td>机壳/℃</td><td>39.6</td><td>38.8</td><td>40.2</td></tr></table></body></html>

![](images/c3f9f1789484009e18bb241f0146f5a4804fab6b10d84104e6f0937653961769.jpg)  
图6样机测试实物图Fig.6Prototype test

由表3中的定子绕组和机壳平均温升可知，在一定的误差允许范围内，用FEM和LPTN对电机进行温度场分析都是合理的。

# 5 结论

本文用LPTN对电机进行了温度场分析，并与FEM温度场分析结果进行了对比，FEM可以得到电机的整体分布云图，LPTN可以得到电机各部件的平均温升，二者结果一致。通过与电机温升试验结果对比可知，FEM和LPTN对电机进行温度场分析都是合理的，都可在工程计算中应用。与FEM相比，LPTN节省了很多时间，对于不同的电机模型也能做相应的简化和拓展，在计算时间和灵活应用上具有较大优势，为下一步基于电机过热点的优化设计做好了准备。

# 参考文献

[1] 魏永田，孟大伟，温嘉斌．电机内热交换[M]．北 京：机械工业出版社，1998.   
[2] Boglietti A,Cavagnino A, Staton D,et al. Evolution and modern approaches for thermal analysis of electrical machines[J].IEEE Transactions on Industrial Electronics,2009,56(3): 871-882.   
[3] Jungreuthmayer C,Bauml T,Winter O,et al.A detailed heat and fluid flow analysis of an internal permanent magnet synchronous machine by means of computational fluid dynamics[J].IEEE Transactions on Industrial Electronics,2012, 59(12): 4568-4578.   
[4] Tong W,Wu S,An Z,et al. Thermal analysis of direct-drive permanent magnet wind generator using both lumped parameter network and finite element method[C]. IEEE Asia-Pacific Power and Energy Engineering Conference,2010: 1-4.   
[5] 王继强．高速永磁电机的机械和电磁特性研究[D]. 沈阳：沈阳工业大学，2006.   
[6] Aglen O.Loss calculation and thermal analysis of a high speed generate[C]. IEEE International Electric Machines & Drives Conference,2003: 1117-1125.