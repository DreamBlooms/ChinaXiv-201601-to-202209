# 基于纳米压痕法的富 $\mathrm { S n }$ 相应力-应变关系的研究

刘志高1，侯 斌²，刘天寒¹，秦红波1（1.桂林电子科技大学 机电工程学院，广西 桂林541004;2.广东省焊接技术研究所，广州510651)

摘要：在电子封装领域中,所用的无铅钎料主要是二元或者三元 Sn基共晶或近共晶合金，其基体相为富 Sn相。为得到富 Sn 相的力学性能及应力-应变关系，由纳米压痕试验测试获得了富 Sn相的弹性模量与硬度，并得到载荷-位移曲线。采用有限元反演分析的方法确定了富 Sn相的特征应力和特征应变，并由量纲函数确定应变强化指数。将特征应力和特征应变强化指数等参数代入幂强化模型中，计算得到富Sn相的屈服强度为 $3 1 . 5 1 \mathrm { M P a }$ ,并最终确定富 $\mathrm { S n }$ 相的应力-应变关系函数表达式。

键词：富Sn相；纳米压痕法；有限元分析；反演分析；应力-应变关系中图分类号：TG425.1 文献标志码：A 文章编号：1673-808X(2021)05-0000-00

# Research on the stress-strain relationship of Sn-rich phase based on nanoindentation

LIU Zhigaol，HOU Bin²，LIU Tianhan1，QIN Hongbol (1.School of Mechatronic Engineering，Guilin University of Electronic Technology，Guilin 541O04，China; 2.Guangdong Welding Institute，Guangzhou 51O651，China)

Abstract:At present，the lead-fre solders used are mainly binaryor ternary Sn-based eutectic or near-eutectic aloys in the ield of electronic packaging，and the matrix phaseis Sn-rich phase. In order toobtainthe mechanical properties and stress;train relation of the Sn-rich phase，the elastic modulus $E$ and the hardness $H$ of the Sn-rich phase were obtained by nanoinlentationtest，andtheload-displacementcurvewasobtained.Then，therepresentativestress and representative strainof he Sn-rich phase are determined by the finite element reverse analysis method，and the strain hardening exponent $n$ was letermined bythe dimensional function.Finaly，the above parameters weresubstituted intothepower-law stressstrain behavior model，the yield strength of Sn-rich phase was calculated to be $3 1 . 5 1 \mathrm { M P a }$ ，and the expression of stress-strain relaion function of Sn-rich phase was finally determined.

Key words:Sn-rich phase；nanoindentation；finite element analysis；reverse analysis；stres-strain relationship

电子封装从广义上讲就是将构成电子产品的各种晶体管、裸芯片、引线、电路、基板和其它封装材料等按照规定或者设计的要求合理密封、布置、固定和连接，实现与外部环境隔离、屏蔽及保护，最终组装成电子产品的整个工艺过程，而狭义的电子封装则是指将半导体晶体管或裸芯片密封、固定并引出接线端子的工艺技术，从而实现对晶体管或裸芯片的保护并增强其环境适应性[1]。在电子封装领域,焊点有机械支撑、电气连接与信号通道的用途。国内外研究者已达成共识：电子封装系统中最薄弱的环节是焊点，焊点的力学失效引起了电子产品和设备的失效。随着电子产品小型化、便携化、多功能化的发展趋势，电子封装密度不断提高，焊点尺寸持续减小。例如，与传统的球栅阵列(BGA，焊球直径 $7 0 0 { \sim } 1 ~ 0 0 0 ~ \mu \mathrm { m } )$ 和微球栅阵列( $\operatorname { \mu - B G A }$ ,焊球直径 $3 0 0 { \sim } 5 0 0 ~ \mu \mathrm { m } ^ { \left[ 2 \right] }$ )微焊点相比，目前典型倒装芯片微焊点直径达到 $1 0 0 \ \mu \mathrm { { m } }$ 以下,2024年将达到 $3 5 \ \mu \mathrm { m } ^ { [ 3 ] }$

值得注意的是，焊点力学行为表征和失效分析的重要依据是材料或者物相力学性能和应力-应变关系。由于万能拉伸机测得的大尺寸试样不能很好地表征微焊点中材料或者物相的微观力学行为4,纳米压痕技术的出现为微焊点力学性能测量提供了手段。纳米压痕技术通过得到的载荷-位移的关系曲线，从而得到微焊点材料及其物相的硬度、弹性模量、蠕变等力学性能，例如：Chromik 等[5通过纳米压痕测试获得了微焊点中 $\mathrm { A g _ { 3 } S n \mathrm { , C u _ { 6 } S n _ { 5 } } }$ 和 $\mathrm { C u _ { 3 } S n }$ 等金属间化合物的硬度及弹性模量等力学性能;孙祥霞等[借助纳米压痕试验方法，研究了Bi和Ni对 $\mathrm { C u / S A C / }$ Cu微焊点体钎料蠕变性能的影响；Xiao等7通过纳米压痕的方法研究了 $\mathrm { S n { - } 3 . 0 A g { - } 0 . 5 C u / C u }$ 接头界面处金属间化合物的硬度、弹性模量和蠕变与应变速率之间的关系；王凤江等8利用纳米压痕技术测量了Sn-Ag-Cu无铅钎料 BGA 焊点的弹性模量。此外，通过纳米压痕技术还可构建金属材料的应力-应变关系函数表达式(力学本构方程),例如:Dao 等[9]提出了特征应力和特征应变的概念，并建立了可以求解金属材料塑性性能的量纲函数；马永等[10]认为可在Da等[9]提出的理论基础上利用纳米压痕技术和有限元反演分析确定弹性模量 $E$ 为 $5 5 { \sim } 6 0 0 ~ \mathrm { G P a }$ 屈服强度 $\sigma _ { \mathrm { y } }$ 为 $0 . 1 { \sim } 1 0 ~ \mathrm { G P a }$ 、应变强化指数 $n$ 为 $0 \sim 0 . 6$ 的金属材料的屈服强度及应变强化指数等塑性性能；秦飞等[11基于马永等[10的反演分析方法，并利用Dao等9建立的量纲函数，确定了电子封装微互联结构TSV-Cu的屈服强度等力学性能参数和弹塑性力学本构方程(应力-应变关系函数表达式)。

在电子工业中，目前开发的无铅钎料（如 $\mathrm { \ S n A g }$ 、SnCu、SnAgCu 和 SnBi等）大多以富Sn 相为基体[12],富 Sn相的应力应变关系很大程度决定了微焊点的力学失效行为。目前，针对无铅钎料合金应力-应变关系的研究较多[13],而钎料合金微观组织中富Sn 相应力-应变关系尚不明确，导致无法进行微观组织力学行为分析。基于上述研究背景和现状，制备了典型无铅钎料SnBi合金中的富Sn相单相固溶体试样，采用纳米压痕技术测试了该富Sn相固溶体试样的载荷-位移曲线，通过马永等[1° 提出的反演分析方法，将有限元模拟结果与纳米压痕试验测试所得结果作对比,并利用Dao 等[9建立的量纲函数,最终得出富 Sn相的应力-应变关系函数表达式。

# 1 试验方法

# 1.1单相固溶体的制备及纳米压痕试验的参数

$\mathrm { { S n } \mathrm { { - } \mathrm { { B i } } } }$ 钎料合金中，富 $\mathrm { S n }$ 相是Bi原子溶解在 $\mathrm { S n }$ 中的单相固溶体，Bi在Sn中的固溶度为1.5$\mathrm { a t \% ^ { \ell } } ^ { [ 1 4 ] }$ 。1)原材料选取纯度为 $9 9 . 9 9 5 \%$ 的 $\mathrm { S n }$ 锭和Bi块，将它们切割成小块状，用高精密天平对其进行称量，金属 $\mathrm { S n }$ 的质量为 $6 0 0 . 0 0 0 \textrm { g }$ ,金属Bi质量为 $1 6 . 0 8 0 ~ \mathrm { g } ; 2 )$ 在坩蜗中加入 $\mathrm { 5 0 ~ g }$ 松香作为抗氧化剂和覆盖剂，将锡炉温度调整到 $2 5 0 ~ \mathrm { { ^ \circ C } }$ ,待松香融化后加入称量好的金属 $\mathrm { S n }$ 和金属Bi;3)等金属完全熔化后，锡炉保持 $2 5 0 \ \mathrm { ~ \textdegree ~ C ~ 1 ~ h ~ }$ 并每隔 $1 0 ~ \mathrm { m i n }$ 用玻璃棒搅拌一次金属，将坩蜗取出并将其中的液态金属倒入钢制模具中，凝固后打开模具，取出富 $\mathrm { S n }$ 相固溶体合金；4)利用线切割的方法将制备的富Sn相固溶体合金切割出一块边长约为 $1 0 \ \mathrm { m m }$ 的正方体试样，剩余的固溶体合金根据GBT/228.1—2010机加工成总长度为 $9 0 ~ \mathrm { m m }$ ，长度方向中间受力处横截面积为 $2 . \ 0 \times 5 . \ 0 \ \ \mathrm { m m } ^ { 2 }$ 的犬骨状试样，用于拉伸试验，将正方体试样放置到树脂与固化剂的质量比为5：4的水晶胶中，待水晶胶凝固后，采用系列砂纸打磨、抛光制备金相试样，以用于后续的纳米压痕试验测试。

纳米压痕试验采用的设备是安捷伦G200纳米压痕仪，该设备位移分辨率为 $0 . 0 1 { \mathrm { n m } }$ ，载荷分辨率为50nN。试验采用Berkovich压头，对富 $\mathrm { S n }$ 相金相试样进行纳米压痕试验测试。纳米压痕试验测试点为5个，压入深度均为 $5 0 0 ~ \mathrm { n m }$ ,加载应变率为 $0 . 0 5 ~ \mathrm { s } ^ { - 1 }$ 。

# 1.2 试验原理

金属材料的塑性性能常采用幂强化模型来描述，对于各向同性材料，弹塑性应力-应变关系为

$$
\begin{array}{c} \sigma = \Biggl \{ \cfrac { E \varepsilon , \sigma \leqslant \sigma _ { \mathrm { y } } , } { \vert \cfrac { E \varepsilon ^ { n } } { R \varepsilon ^ { n } } = \sigma _ { \mathrm { y } } \Bigl ( 1 + \frac { E } { \sigma _ { \mathrm { y } } } \varepsilon _ { \mathrm { p } } \Bigr ) ^ { n } , \sigma > \sigma _ { \mathrm { y } } , }  \end{array}
$$

其中： $E$ 为弹性模量； $R$ 为强度系数; $n$ 为应变强化指数； $\sigma _ { \mathrm { y } }$ 为屈服强度； $\boldsymbol \varepsilon _ { \mathrm { p } }$ 为塑性应变。弹性模量 $E$ 可由纳米压痕测试得到，并记录试验载荷-位移曲线；屈服强度 $\sigma _ { \mathrm { y } }$ 和应变强化指数 $n$ 则需特征应力、特征应变与量纲函数9确定，其中特征应力 $\sigma _ { \mathrm { r } }$ 和特征应变 $\varepsilon _ { \mathrm { { r } } }$ 是应力应变曲线上一个代表点的值，可以由有限元反演方法确定[10]。将这些参数代入幂强化模型中，得出富Sn相的应力-应变关系函数表达式。

# 1.3 有限元仿真

在结构轴对称时，二维轴对称有限元模型与三维轴对称有限元模型具有相同的精度[10]。因此，为了更好地提高运算效率，在ANSYS软件中采用二维轴对称有限元模型对纳米压痕测试的加载阶段进行模拟仿真。在二维有限元模型(见图1)中，单元类型采用PLANE182单元，选取TRAGE169和CON-TA172作为接触单元。Berkovich压头可以等效为顶角为 $1 4 0 . 6 ^ { \circ }$ 的圆锥压头[15],在二维轴对称模型中压头可以等效为顶角（靠近试样的角）为 $7 0 . 3 ^ { \circ }$ 的三角形，被压试样为边长 $4 0 \ \mu \mathrm { m }$ 的正方形。为了在节省运算时间的同时，确保运算的准确性，对模型中左上角 $1 0 \times 1 0 ~ \mu \mathrm { { m } ^ { 2 } }$ 的区域进行局部网格细化，共6400个网格。在富Sn相有限元模型中，单元数和节点数分别为12100和12310。对底边的节点施加 $Y$ 方向的约束，沿对称轴上的节点施加对称约束，加载条件与试验测试情况一致。

![](images/6e58cda399874239e8d73d46991ee720fc3b8ce97734587b6a8c5d71a96ed59c.jpg)  
图1有限元模型

# 2实验结果与分析

# 2.1 纳米压痕试验的结果

对富 $\mathrm { S n }$ 相进行纳米压痕测试，得到5个测试点的弹性模量和硬度的值，弹性模量的平均值为61.10GPa,硬度的平均值为 $0 . 3 7 \ \mathrm { G P a }$ ,试验结果见表1。图2(a)给出了试验测试中加载阶段的5个测试点的载荷位移曲线及其平均载荷位移曲线。根据文献[16」，将平均载荷位移曲线拟合为抛物线函数曲线，如图2(b)所示。

表1富 Sn 相的弹性模量 $E$ 和硬度 $H$   

<html><body><table><tr><td>测试点</td><td>E/GPa</td><td>H/GPa</td></tr><tr><td>1</td><td>59.62</td><td>0.33</td></tr><tr><td>2</td><td>61. 18</td><td>0.37</td></tr><tr><td>3</td><td>61.65</td><td>0.37</td></tr><tr><td>4</td><td>61.10</td><td>0.36</td></tr><tr><td>5</td><td>61.95</td><td>0.44</td></tr><tr><td>平均值</td><td>61.10</td><td>0.37</td></tr></table></body></html>

![](images/80cbced317cf2ee6e00549fa25e0a8f62883d0c2a5490cc3d67d50c6f6eeaa85.jpg)  
图2试验载荷-位移曲线及其平均曲线和拟合曲线

# 2.2应力应变关系函数表达式确定

# 2.2.1特征应力的确定

根据Dao等[9]的理论，当金属材料具有相同特征应力、特征应变和弹性模量时，可以得到相同的加载阶段载荷-位移曲线。因此，在应变强化指数 $n = 0$ 的情况下（ANSYS采用BISO模型，将BISO模型的屈服强度假设为富 $\mathrm { S n }$ 相特征应力的值)，根据文献[17]和式(2)估算特征应力 $\sigma _ { \mathrm { r } }$ 。

$$
\frac { E _ { \mathrm { r } } } { H } = 0 . 2 3 1 \Big ( \frac { E _ { \mathrm { r } } } { \sigma _ { \mathrm { r } } } \Big ) + 4 . 9 1 0 ,
$$

其中： $E _ { \mathrm { r } }$ 为等效弹性模量； $H$ 为硬度。

$$
\frac { 1 } { E _ { \mathrm { r } } } { = } \frac { 1 - \nu ^ { 2 } } { E } { + } \frac { 1 - \nu _ { \mathrm { i } } ^ { 2 } } { E _ { \mathrm { i } } } ,
$$

其中：富 $\mathrm { S n }$ 相试样的泊松比 $\nu$ 为0.33；压头的泊松比 $\nu _ { \mathrm { i } }$ 为0.07；富 $\mathrm { S n }$ 相试样的弹性模量 $E$ 为61.10$\mathrm { G P a }$ ;压头的弹性模量 $E _ { \mathrm { i } }$ 为 $1 \ 1 4 1 \ \mathrm { G P a }$ 。将富 $\mathrm { S n }$ 相和压头的材料参数输入ANSYS中进行反演分析，当最大模拟载荷 $F _ { \mathrm { m a x } } ^ { \mathrm { F E M } }$ 与最大试验载荷 $F _ { \mathrm { { m a x } } } ^ { \mathrm { { E X P } } }$ 的误差大于 $0 . 5 \%$ ，则按式(4)进行迭代。

$$
\sigma _ { r } \left( i + 1 \right) = \sigma _ { r } \left( i \right) \frac { F _ { \mathrm { m a x } } ^ { \mathrm { E X P } } } { F _ { \mathrm { m a x } } ^ { \mathrm { F E M } } } ,
$$

其由：$i \mp 1$ $F _ { e ^ { \mathrm { m a x } } } ^ { \widehat { \mathrm { F E M } } }$ 所。

（204号 $\sigma _ { \mathrm { r } } ( i )$ 为第 $i$ 次迭代的特征应力; $\sigma _ { \mathrm { r } } ( i + 1 )$ 为第次迭代的特征应力。当得到的模拟最大载荷和试验最大载荷 $F _ { \mathrm { \ m a x } } ^ { \mathrm { E X P } }$ 误差小于0.5且模拟载荷-位移曲线与试验载荷-位移曲线一致时，迭代结束，最终确定特征应力 $\sigma _ { \mathrm { r } }$ 取 $8 2 . 8 4 ~ \mathrm { M P a }$ ，如图3

![](images/650cf605d5c0b30e91a7d887a0d6fc7fb5e73e926e8f4e67d5bbcda282c7fd9a.jpg)  
图3当 $n { = } 0$ 时的试验载荷-位移曲线和模拟载荷-位移曲线

# 2.2.2应变强化指数的确定

由纳米压痕试验得到卸载后的残余深度 $\left| h _ { \mathrm { ~ r ~ } } \right|$ 和最大压深 $h _ { \mathrm { ~ m ~ } }$ 值， $h _ { \mathrm { ~ r ~ } }$ 的平均值为 $5 1 8 . 8 2 9 \ 0 \ \mathrm { n m } , h _ { \mathrm { m } }$ 的平均值为 $5 3 4 . 2 2 4 \ 9 \ \mathrm { n m }$ ，如表2所示。根据Dao 等[9]提出的量纲函数，将 $h _ { \mathrm { ~ r ~ } } \mathbf { \nabla } _ { \mathbf { \mathrm { { r } } } } h _ { \mathrm { { m } } }$ 的值代入式（5)，经计算，应变强化指数 $n { = } 0 . 3 0 9 \ 6$ 。

$$
\begin{array} { c } { { \displaystyle \frac { h _ { \mathrm { r } } } { h _ { \mathrm { m } } } = ( 0 . 0 1 0 1 0 0 n ^ { 2 } + 0 . 0 0 1 7 9 6 3 9 n -  } } \\ { { \displaystyle  0 . 0 0 4 0 8 3 7 ) [ \ln ( \frac { \sigma _ { \mathrm { r } } } { E _ { \mathrm { r } } } ) ] ^ { 3 } + ( 0 . 1 4 3 8 6 n ^ { 2 } +  } } \\ { {  \qquad 0 . 0 1 8 1 5 3 n - 0 . 0 8 8 1 9 8 ) [ \ln ( \frac { \sigma _ { \mathrm { r } } } { E _ { \mathrm { r } } } ) ] ^ { 2 } + } } \end{array}
$$

表2残余深度 $h _ { \mathrm { { r } } }$ 和最大压深 $h _ { \mathrm { ~ m ~ } }$   

<html><body><table><tr><td>测试点</td><td>h/nm</td><td>hm/nm</td></tr><tr><td>1</td><td>513.895 0</td><td>535.224 9</td></tr><tr><td>2</td><td>518.981 9</td><td>534.303 8</td></tr><tr><td>3</td><td>519.038 0</td><td>534.554 2</td></tr><tr><td>4</td><td>516.357 9</td><td>530.904 7</td></tr><tr><td>5</td><td>525.874 3</td><td>539.312 6</td></tr><tr><td>平均值</td><td>518.829 0</td><td>534.8600</td></tr></table></body></html>

$^ { \circ } 0 . 0 5 9 ~ 5 0 5 n ^ { 2 } + 0 . 0 3 4 ~ 0 7 4 n - 0 . 6 5 4 ~ 1 7 ) \left\lfloor \ln \left( { \frac { \sigma _ { \mathrm { r } } } { E _ { \mathrm { r } } } } \right) \right\rfloor +$ $( 0 . 5 8 1 8 0 n ^ { 2 } - 0 . 0 8 8 4 6 0 n - 0 . 6 7 2 9 0 ) ,$ (5）

2.2.3特征应变与应力应变关系函数表达式的确定根据文献18」，富 $\mathrm { S n }$ 相的特征应变 $\boldsymbol { \varepsilon } _ { \mathrm { r } }$ 可由式(6)估算得到：

$$
\mathfrak { \varepsilon } _ { \mathrm { r } } = \exp ( - 3 . 9 1 + 1 6 6 . 7 / ( E _ { \mathrm { r } } / \sigma _ { \mathrm { r } } + 1 7 7 . 3 ) )
$$

将得到的特征应力 $\sigma _ { \mathrm { r } }$ 、应变强化指数 $n$ 和估算的特征应变 $\varepsilon _ { \mathrm { { r } } }$ 代入幂强化模型中（即 $n \not = 0$ 时)，可以得出一系列应力-塑性应变点的值，将这些值输入材料属性进行有限元模拟。若最大模拟载荷 $F _ { \mathrm { m a x } } ^ { \mathrm { F E M } }$ 与最大试验载荷 $F _ { \mathrm { \ m a x } } ^ { \mathrm { E X P } }$ 的误差大于 $0 . 5 \%$ ，则按照式（7)进行迭代。

$$
\varepsilon _ { \mathrm { r } } ( i + 1 ) = \varepsilon _ { \mathrm { r } } ( i ) \frac { F _ { \mathrm { m a x } } ^ { \mathrm { F E M } } } { F _ { \mathrm { m a x } } ^ { \mathrm { E X P } } } ,
$$

其中： $\varepsilon _ { \mathrm { r } } ( i )$ 为第 $\mathbf { \chi } _ { i }$ 次迭代的特征应变； $\varepsilon _ { \mathrm { r } } ( i { + } 1 )$ 为第 $i + 1$ 次迭代的特征应变。当得到的模拟最大载荷 $F _ { \mathrm { m a x } } ^ { \mathrm { F E M } }$ （204号和试验最大载荷 $F _ { \mathrm { m a x } } ^ { \mathrm { E X P } }$ 误差小于 $0 . 5 \%$ 且模拟载荷-位移曲线与试验载荷-位移曲线一致时，迭代结束，最终确定特征应变 $\varepsilon$ 为0.0112，如图4所示。将已经确定的富Sn相的材料参数代入幂强化模型中，最终计算得到富 $\mathrm { S n }$ 相的屈服强度 $\sigma _ { \mathrm { y } }$ 为 $3 1 . 5 1 \ \mathrm { M P a }$ 。

综上，本研究中富 $\mathrm { S n }$ 相的应力应变关系函数表达式为

$$
\sigma = \left\{ \begin{array} { l } { 6 1 1 0 0 \varepsilon , \sigma \leqslant 3 1 . 5 1 , } \\ { 3 1 . 5 1 ( 1 + 1 9 3 9 . 0 7 \varepsilon _ { \mathrm { p } } ) ^ { 0 . 3 0 9 6 } , \sigma > 3 1 . 5 1 \circ } \end{array} \right.
$$

# 2.3 拉伸试验验证

为了验证采用反演分析方法得到的富 $\mathrm { S n }$ 相应力-应变关系函数表达式的准确性，根据GBT/228.1—2010对长度方向中间受力处横截面积为 $2 . 0 \times$ $5 . 0 ~ \mathrm { m m ^ { 2 } }$ 的富 $\mathrm { S n }$ 相犬骨状试样进行拉伸试验，得到应力-应变曲线，如图(5)所示。拉伸试验测试中所采用的引伸计标距为 $2 5 ~ \mathrm { m m }$ ，将试样发生 $0 . 2 \%$ 塑性变形 $( R _ { \mathrm { p 0 . 2 } } )$ 时的应力 $2 9 . 6 7 \ \mathrm { M P a }$ 作为屈服强度，与反演分析所得的屈服强度 $3 1 . 5 1 \ \mathrm { M P a }$ 相接近，可验证本研究通过反演分析得到的富 $\mathrm { S n }$ 相应力-应变关系函数表达式是正确的。

![](images/cc723071134a350afee2f4825f3fd85dcdb4038d1ae27b0025d907beaf779776.jpg)  
图4 $n \not = 0$ 时的试验载荷-曲线位移和模拟载荷-位移曲线

![](images/25c925535f609463bdc08c7801a18553826195926042381ee419fd0b6b072e9b.jpg)  
图5由拉伸试验得到的富 Sn 相应力-应变曲线

# 3 结束语

1）由纳米压痕试验测得富Sn相的弹性模量 $E$ 和硬度 $H$ 分别为 $6 1 . 1 0 \ \mathrm { G P a }$ 和 $0 . 3 7 \ \mathrm { G P a }$ 。  
2）将纳米压痕试验测试和有限元反演分析相结合，得到了富Sn相的应力-应变关系函数表达式，利用拉伸试验验证了反演分析结果的正确性。  
3）所得富Sn相的力学性能参数及应力应变关系函数表达式对Sn基微焊点微观力学行为研究、力学失效行为分析及可靠性评估具有较为重要的意义。

# 参考文献：

［1］秦红波.无铅微互连焊点力学性能及疲劳与电迁移行为 的尺寸效应研究[D].广州：华南理工大学，2014:3-4.   
[2]TONG H M,LAIY S,WONG CP.Advanced flip chip packaging_Ml.Boston:Springer,2013:23-27.   
[3]HOEFFLINGER B. ITRS:the international technology 4 余红 期十 阳似好点时 低周疲劳行为研究[J].机械工程学报,2014,50（20)： 54-62.   
[5]CHROKMIK R R,VINCI R P,ALLEN S L,et al. Measuring the mechanical properties of $\mathrm { C u _ { 6 } S n _ { 5 } }$ and Cu3Sn intermetallics by nanoindentation [J]. JOM, 2003,55(6):66-69.   
[6］孔祥霞,孙凤莲,杨淼森,等.Bi和 Ni元素对 $\mathrm { C u / S A C / }$ Cu 微焊点体钎料蠕变性能的影响[J].机械工程学报, 2017,53(2) :53-60.   
[7]XIAO Gesheng, YANG Xuexia, YUAN Guozheng,et al. Mechanical properties of intermetallic compounds at the Sn-3.OAg-0.5Cu/Cu joint interface using nanoindentation[J].Materials and Design,2015,88:520-527.   
［8］王凤江,钱乙余,马鑫.纳米压痕法测量 $\mathrm { S n { ^ { - } A g { - } C u } }$ 无铅 钎料 BGA焊点的力学性能参数[J].金属学报，2005， 32(4) :1-4.   
[9]DAO M,CHOLLACOOP N,VAN V K J,et al. Computational modeling of the forward and reverse problems in instrumented sharp indentation[J].Acta Materialia,2001,49(19):3899-3918.   
[10]马永,姚晓红，田林海,等.利用纳米压入的反演分析法 确定金属材料的塑性性能[J].金属学报,2011,47（3)： 321-326.   
[11］秦飞,项敏,武伟.纳米压痕法确定 TSV-Cu 的应力-应 变关系[J].金属学报,2014,50(6):722-726.   
[12]陈旭.Sn-Bi基焊料组织与性能的研究[D].南京;东南 大学,2017:1-4.   
[13]ZHANG Liang,HAN Jiguang,HE Chengwen,et al. Reliability behavior of lead-free solder joints in electronic components [J]. Journal of Materials Science: Materials in Electronics,2012,24(1):172-190.   
[14]KAYA H,BOYUK U,CADIRLI U,et al. Dependency of microstructural parameters and microindentation hardness on the temperature gradient in the In-Bi-Sn ternary alloy with a low melting point[J].Metals &. Materials Internation,2018,14(5):575-582.   
[15]WANG Tonghong，FANG Tehua,LIN Yucheng. Finite-element analysis of the mechanical behavior of Au/ Cu and Cu/Au multilayers on silicon substrate under nanoindentation[J].Applied Physics A,20o8,90（3）: 457-463.   
[16]ZHUKD I,ISAENKOVA MG,PERLOVICH Y A,et al.Finite element simulation of microindentation[J]. Russian Metallurgy （Metally）,2017(5）:390-396.   
[17]ANTUNES J M,FERNANDES J V,MENEZNS L F, et al.A new approach for reverse analyses in depth

sensing indentation using numerical simulation[J].ActaMaterialia,2007,55(1):69-81. [18]LEE JM,LEE CJ,KIM B.Reverse analysis of nano indentation using different representative strains and residual indentation profiles[J].Materials and Design, 2009,30(9):3395-3404.

编辑：张所滨