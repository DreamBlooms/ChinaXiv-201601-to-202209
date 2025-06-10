# 基于直方图移位的AMBTC域无损信息隐藏

张弢la，柳雨农la，邢亚林la，任帅』b，张德刚²(1．长安大学a.电子与控制工程学院;b.信息工程学院，西安 710068;2.云南电网有限责任公司教育培训评价中心,昆明 650033)

摘要：针对秘密信息的安全传输，提出了一种信息隐藏算法，将混沌置乱变换及行程压缩编码同时应用于秘密信息预处理，旨在改善隐藏载体的嵌入容量和鲁棒。该算法将直方图移位技术应用于信息嵌入过程，在绝对矩阵块截断编码（AMBTC）生成的高低平均值序列上隐藏预处理后的秘密信息，实现了载体的无损隐藏并提升了嵌入容量，且嵌入容量高于直接在由AMBTC生成的高低平均值序列上进行隐藏的算法。实验结果表明，在受到某些攻击后仍保证提取出的秘密信息具有较高的可辨识度，归一化系数始终高于0.6，证明了该算法在鲁棒性和隐藏效率方面的优势。因此，提出的信息隐藏方法能达到秘密信息安全传输的目的，同时具有很好的抗攻击性。

关键词：信息隐藏；混沌置乱变换；行程压缩编码；绝对矩阵块截断编码 中图分类号：TP309.2 doi:10.3969/j.issn.1001-3695.2018.01.0006

# Lossless information hiding in AMBTC domain based on histogram shift

Zhang Taola, Liu Yunonglat, Xing Yalinla, Ren Shuai1b, Zhang Degang² (1.a.Schooloflectronic&ControlEngineeing,b.hoolofIformationEngineringChang'anUniversity,Xi’a064, China; 2.Education Training Evaluation Center Yunnan Power Grid Co,Kunming 65oo33, China)

Abstract:Forthesecure transmissionofconfidential information,thisproposedaninformation hidingalgorithm.Usingchaos scrambling transform andrun-length codecompresion simultaneouslyin the secret informationpreprocessing,inorderto improve theembeddingcapacityand robustess ofthestego.Inordertoachieve thelosless hidingandimprove thecapacityit usedthe histogram-shifttechnologyand the AMBTC(Absolute Moment Block Truncating Coding)to hidethepreprocessed secret informationinhighand low meanvalue sequence,andthecapacity waslarger than thatofthe algorithm which is only based on the AMBTC.Theexperimentalresults showthatthe extractedsecret informationcanbehighly identified evenafter someattacks,andthenormalizationcoefficientisalways lager than O.6,which proves theadvantagesofthe proposedalgorithm intermsofrobustnessand hiding eficiency.Therefore,the methodof information hiding inthis paper achieves the goalof secure transmission of secret information and has good anti-aggression.

Key Words: information hiding; chaotic scrambling transform; stroke compresson coding; AMBTC

# 0 引言

信息隐藏的主要方式是修改载体数据进行隐藏，旨在将密文隐藏在普通载体中。近年来高嵌入容量与无损恢复的信息隐藏研究广泛应用于医学图像、遥感图像、军事图像等领域。而无损信息隐藏主要面临在数字媒体中实现较大容量的嵌入，实现较低失真的无损信息隐藏、嵌入率及嵌入算法的安全性、传输过程中出现信息丢失和噪声影响等方面的挑战。目前主要载体为二维图像、三维模型、视频、音频等。在二维图像中实现指纹、人脸等特征的信息隐藏已成为安全通信、电子商务及远程身份认证的最新应用技术。Ker等人[提出多幅二维图像信息隐藏方式，该方式对算法计算复杂度极具考验，相反Qian等人[2]提出的单幅信息隐藏，简化了算法过程。

秘密信息的预处理作为安全隐藏的前提，置乱与压缩为主要处理方式，文献[3,4]将混沌置乱应用于信息隐藏的图像预处理，文献[5,6]提出改进的JPEG图像压缩算法来增加载体的嵌入容量，文献[7]中提出的基于Armold的置乱算法，该算法具有周期性缺点，破译者很容易掌握其规律并且破译。由于一般的预处理算法基于离散余弦变换的编码算法，在量化中易产生数据缺失和方块效应[8]，此类处理算法只保证了载体的视觉质量，但对载体数据特性产生破坏，攻击者可根据直方图异常、JPEG分块效应等异常现象有效击破此类隐藏方法[9-10]。针对上述问题，无损信息隐藏(losslessinformationhiding)能有效地避免破坏原始载体信息，可以完全无损恢复原载体图像，提高信息传输的隐蔽性。Chen 等人提出了由绝对矩阵块截断编码[11,12]（absolute moment block truncatingcoding，AMBTC）生成高低平均值进行处理的信息隐藏算法，只改变了高低平均值的相对位置。

本文在AMBTC无损嵌入算法基础上，对高低平均值数据分别进行直方图移位操作，实现两级无损数据隐藏。首先采用Chebyshev映射的混沌置乱及行程压缩编码对密文进行预处理，加强了嵌入系统安全性并具有较好的去相关性；相对于文献[6]的 JPEG 图像压缩，行程编码的压缩比达到26，对于文献[7],混沌置乱避免了周期性的缺点。随后采用基于直方图移位的AMBTC无损嵌入算法实现信息隐藏，并对隐藏载体进行攻击测试，提取出秘密信息并将归一化系数与文献算法进行对比分析，结果显示本文中算法面临几何攻击和空间滤波攻击具有良好的鲁棒性。因此，本文提出的信息隐藏系统实现秘密信息的安全传输，而且具有较好的抗攻击性。

# 1 信息隐藏系统组成

本文采用某二值指纹图像作为隐秘信息，图1、2为信息隐藏系统的嵌入和检测两过程，隐秘信息与隐藏载体经过隐藏算法形成隐秘载体，视觉上与嵌入之前的载体图像无差别，其次对隐藏载体进行攻击测试，分别提取出隐秘信息和载体图像并与原始图像数据对比，检验其隐藏算法鲁棒性。

![](images/d9d9aefbbc75aedb9b41c72c017228e78134dbfc308075444982b72fb7a9744c.jpg)  
图1秘密信息嵌入系统框图

![](images/c14936f50e5e91a0bb1c193279f59361e546f247a951ffce8dcfe1fcc20b18ce.jpg)  
图2秘密信息提取系统框图

信息隐藏系统基本包括以下元素：定义 $M$ 为原始隐秘信息$\mathbf { \nabla } _ { m }$ 的集合； $X$ 为隐藏载体 $x$ 集合； $W$ 为预处理后的隐秘信息 $w$ 集合； $K$ 为隐藏密钥 $k$ 集合； $G$ 表示利用原始信息 $\mid m$ 、密钥 $k$ 及隐藏载体 $x$ 生成的加密算法：

$$
G \colon M \times X \times K \to W , w = G { \bigl ( } m , x , k { \bigr ) }
$$

$A _ { t }$ 表示对嵌入隐秘信息的载体 $x ^ { w }$ 攻击测试算法:

$$
A _ { t } : X \times K \to X , \hat { x } = A _ { t } \big ( x ^ { w } , K ^ { \prime } \big )
$$

# 2 置乱算法

# 2.1Chebyshev 映射

Chebyshev 映射与Logistic 映射、Henon 映射同属于混沌置乱算法，由Chebyshev提出的以阶数为参数的混沌映射。设 $C [$ 1,1]上的所有实值连续函数构成的向量空间，则$\left\{ \cos ( n \operatorname { a r c c o s } \chi _ { n } ) , n \in [ 0 , \infty ) \right\}$ 是 $C [ - 1 , 1 ]$ 上的一组基。令$T _ { n } ( \chi ) = \cos ( n \operatorname { a r c c o s } \chi _ { n } )$ ，则 $T _ { n } ( \chi )$ 称为 $n$ 阶第一切比雪夫多项式。当迭代次数为 $k$ ，Chebyshev 映射如下：

$$
x _ { n + 1 } = \cos ( k \operatorname { a r c c o s } x _ { n } )
$$

其中: $x _ { n } \in ( - 1 , 1 )$ ，当 $k \geq 2$ 时，映射进入混沌区域。

基于Chebyshev 映射的置乱算法

算法1置乱算法

a)获取混沌随机序列 $X = \left\{ x _ { 1 , } x _ { 2 } \cdots x _ { 8 m \times n } \right\}$ ，经过对(2.1）迭代 $8 m \times n$ 次， $m , \ n$ 为图像宽、高。

b)从随机序列 $X$ 中选取8个数得到一个序列$Y = \left\{ y _ { 1 , } y _ { 2 } \cdots y _ { 8 } \right\} _ { \mathrm { { c } } }$ （20

c)将序列 $Y$ 经过一次置换得 $Y ^ { \prime } = \left\{ y _ { 1 , } ^ { \prime } y _ { 2 } ^ { \prime } \cdots y _ { 8 } ^ { \prime } \right\}$ 售

d)获取一个索引序列 $D _ { i }$ ， $D _ { i } = \left\{ d _ { 1 } , d _ { 2 } , \cdot \cdot \cdot d _ { 8 } \right\}$ ，其中 $d _ { i }$ 表示$D _ { i }$ 序列中第 $i$ 个数在 $Y _ { i } ^ { \prime }$ 的位置。

算法2 Chebyshev 映射 $N$ 次迭代算法

a)获取二进制序列 $K _ { i } = \left\{ k _ { 1 , } k _ { 2 } \cdots k _ { 8 } \right\}$ ，将秘密信息转换一维序列 $G _ { i } = \left\{ g _ { 1 , } g _ { 2 } \cdots g _ { 8 m \times n } \right\}$ ，将 $g _ { i }$ 转换为 $K _ { i }$ 。

b)利用算法1得到的索引序列 $D _ { i }$ 对 $B _ { i }$ 进行置换，得到序列 $K _ { i } ^ { \prime } = \left\{ k _ { 1 , } ^ { \prime } k _ { 2 } ^ { \prime } \cdots k _ { 8 } ^ { \prime } \right\}$ 。

c)将序列 $K _ { i } ^ { \prime }$ 转换成 $g _ { i } ^ { \prime }$ 。

d)重复步骤 $\boldsymbol { \mathsf { b } } ) \boldsymbol { \mathsf { c } } ) 4 \boldsymbol { m } \times \boldsymbol { n }$ 次。e)得到 $N$ 次迭代序列 $G _ { i } ^ { \prime } = \left\{ g _ { 1 , } ^ { \prime } g _ { 2 } ^ { \prime } \cdots g _ { 8 m \times n } ^ { \prime } \right\}$

# 2.2混沌置乱算法检验

对Chebyshev 映射的混沌置乱算法进行仿真，Matlab2012仿真环境中，选取大小为 $5 1 2 \times 5 1 2$ 的指纹图像。其中图（a）为原始图像，（b）为混沌置乱图像，（c）为反置乱变换后图像，(d）为原始图像直方图，（e）为混沌置乱图像直方图，（f)为反置乱变换后图像直方图：

![](images/21262f35f19b9555633e96698d5b0e0f7b023a3c1bf669f1df82862875f9bb44.jpg)  
图3置乱算法测试结果

在混实验结果中，图（a) $\sim$ （c）体现出混沌置乱算法具有极好的置乱效果，置乱改变了原图像的数据，再经过反置乱变换后，置乱图像恢复原始画面，在直方图（d）～（f）中，对图像数据进行比较，可得到当秘密图像经过置乱与反置乱变换得到的恢复图像，其图像的亮度变暗，图像数据发生改变但不改变图像内容。

# 3 压缩算法理论

本文提出压缩编码来减少隐秘信息在嵌入载体的数据量，由于图像的冗余性和相关性，图像压缩的本质是对图像数据按照一定规则进行变换和组合，来去除冗余信息量。信息量与信息熵组成了该压缩算法的理论。

# 3.1信息量

设一个信息源 $X$ 发出的一个信息元素集合表示为$A = \left\{ a _ { i } \vert i = 1 , 2 , . . . , m \right\}$ ， $X$ 发出的 $a _ { i }$ 出现概率为 $p ( a _ { i } )$ ，则定义元素 $a _ { i }$ 出现的信息量为

$$
I ( a _ { i } ) = - \log _ { 2 } p ( a _ { i } )
$$

# 3.2 信息熵

对信息源 $X$ 各元素自信息量取统计平均，得每个元素平均自信息量 $H ( X )$ ，称为信息源的熵，定义为

$$
H ( X ) = - \sum _ { i = 1 } ^ { m } p ( a _ { i } ) \log _ { 2 } p ( a _ { i } )
$$

在式（5）中，若图像灰度级为 $[ 1 , M ]$ ，通过直方图各灰度级出现的概率为 $p _ { s } ( s _ { i } ) , i = 1 , 2 , . . . , M$ ，得到图像的熵为

$$
H = - \sum _ { i = 1 } ^ { m } p ( s _ { i } ) \log _ { 2 } p _ { s } ( s _ { i } )
$$

通常，以峰值信噪比PSNR作为客观评价指标，表示为

$$
P S N R { = } 1 0 1 \mathrm { g } \frac { ( L - 1 ) ^ { 2 } } { ( e _ { r m s } ) ^ { 2 } }
$$

其中： $L$ 是图像灰度级总数， $e _ { r m s }$ 表示大小为 $M \times N$ 的图像的均方误差，其定义如下：

$$
e _ { r m s } = \sqrt { \frac { 1 } { M N } \sum _ { x = 0 } ^ { M - 1 } \sum _ { y = 0 } ^ { N - 1 } \Bigl [ \hat { f } ( x , y ) - f ( x , y ) \Bigr ] ^ { 2 } }
$$

隐藏信息的数据压缩处理使用一种无损压缩编码，即行程编码（run-lengthcodecompression，RLCC），选取大小为$5 1 2 \times 5 1 2$ 的灰度图作为同样的测试图像，图（a）为密文的原始图像二值图，图（b）为压缩后结果，图（c）为解压后图像；图（d) $\sim$ （f）为原始图、压缩图像、解压后图像数据，测试结果如下：

![](images/cc508dfc3477cfe34277359a6c7cc1306fba6ba439cc52b41982574e8bc1ee32.jpg)  
图4压缩编码算法测试结果

霍夫曼编码算法编码时间为 $1 0 3 t$ ，压缩比为1.7，而RLCC的编码时间为 $1 . 7 t$ （t为单位时间 $s$ ），压缩比为26.2。可见，RLCC 算法复杂度简单且压缩速率优于霍夫曼编码。

# 4 嵌入算法理论

隐藏信息嵌入作为信息隐藏系统的核心，面临着在传输过程中被攻击的挑战，因此对抗攻击性要求较高。在此之前，Lema和 Mitchell 提出了AMBTC 编码嵌入算法，而 Chen 等人[11,12]后来在此基础上引入了直方图移位，但此方法对直方图移位具有依赖性的数据改变而无法恢复。面对以上问题，这里提出了一种基于直方图移位的AMBTC（绝对矩阵块截断编码）高低均值压缩图像隐写嵌入方法，其过程简化为两个步骤：用数据替换二进制位图和根据所嵌数据和原始位图最优化高低均值。

# 4.1数据嵌入

a)AMBTC编码。设一幅大小为 $M \times N$ 的图像 $C$ ，取块大小为 $m \times n$ ，经AMBTC 编码得到高低平均序列， $l _ { i }$ 和 $h _ { i }$ 表示高低序列块元素：

$$
L = \left\{ l _ { i } \big | 1 \leq i \leq ( M \times N ) / ( m \times n ) \right\}
$$

$$
H = \left\{ h _ { i } { \big | } 1 \leq i \leq ( M \times N ) / ( m \times n ) \right\}
$$

以及位平面

$$
B = \left\{ B _ { i } { \big | } 1 \leq i \leq ( M \times N ) / ( m \times n ) \right\}
$$

其中 $B _ { i }$ 大小为 $m \times n$ ，且与 $l _ { i }$ 和 $h _ { i }$ 构成三元组 $( l _ { i } , h _ { i } , B _ { i } )$ 。

![](images/2578ca6e1a05cf8a01266fe4bedc1f60685e07c3a92a15a0abec0268921b10dd.jpg)  
图5直方图移位示意图

![](images/6aa9187b488157e783539d788be28abd87f9c2b2d345cc46dcd65deca5aed1b2.jpg)  
图6数据嵌入示意图

b)高平均序列直方图移位。

（a)计算平均序列进行直方图移位： $H _ { h } ( x ) , x \in [ 0 , 2 5 5 ]$ 。

(b)在 $H _ { h } ( x )$ 中找到最大值点 $x _ { \mathrm { m a x } }$ 和最小值点 $x _ { \operatorname* { m i n } }$ ，假设Xmax<Xmin的情况，如图6所示。若Hh(x)≠0记录所有值等于 $x _ { \operatorname* { m i n } }$ 的像素点位置。

(c)移位（图5）：若 ${ x _ { \operatorname* { m a x } } > x _ { \operatorname* { m i n } } }$ ，遍历整个序列 $H$ ，当$h _ { i } \in \left[ x _ { \operatorname* { m a x } } + 1 , x _ { \operatorname* { m i n } } \right)$ 时，进行 $\left( h _ { i } + 1 \right)$ ；若 ${ x _ { \mathrm { m a x } } < x _ { \mathrm { m i n } } }$ ，当$h _ { i } \in ( x _ { \operatorname* { m i n } } , x _ { \operatorname* { m a x } } - 1 ]$ 时，进行 $( h _ { i } + 1 )$ 。

(d)嵌入数据；再次遍历序列 $H$ ，当 $h = x _ { \operatorname* { m a x } }$ 时，若嵌入的数据为"1”，则将 $h _ { i }$ 进行加1；若嵌入数据为 $\cdot _ { 0 } \cdot \cdot ,$ ，则 $h _ { i }$ 不变。

c)如同步骤b)，对低平均序列 $L$ 进行直方图移位。

d)修改高低平均值的相对次序：遍历经过直方图移位后的高低平均值序列 $H ^ { \prime }$ 和 $L ^ { \prime }$ ，当 $h _ { i } ^ { \prime } \neq l _ { i } ^ { \prime }$ 时，如果待嵌入数据为"1”,交换 $l _ { i } ^ { \prime }$ 和 $h _ { i } ^ { \prime }$ 位置。同时，将 $l _ { i } ^ { \prime }$ 和 $h _ { i } ^ { \prime }$ 对应的 $B _ { i }$ 中所有比特位翻转；如果嵌入数据为 $\cdot _ { 0 } \cdot \cdot ,$ ，保持 $( l _ { i } , h _ { i } , B _ { i } )$ 不变。在 $h _ { i } ^ { \prime } = l _ { i } ^ { \prime }$ 时，直接将 $m \times n$ 位的待嵌入数据替换 $B _ { i }$ 。

# 4.2数据提取与图像恢复

数据的提取和图像恢复为数据嵌入的逆过程。

a)统计高低平均值序列的相对次序。遍历隐藏数据高低平均值序列 $H ^ { W }$ 和 $L ^ { \ l ^ { W } }$ ，在 ${ h _ { i } } ^ { W } \neq l ^ { W } { i }$ 时，如果 ${ h _ { i } } ^ { W } < { l ^ { W } } _ { i }$ ，提取数据"1”，并交换 $l _ { i } ^ { \phantom { \dagger } }$ 和 ${ h _ { i } } ^ { W }$ 位置。同时，将 $l _ { i } ^ { \phantom { \dagger } }$ 和 ${ h _ { i } } ^ { W }$ 对应的 $B _ { i }$ 中所有比特位翻转；如果 ${ h _ { i } } ^ { W } > l ^ { W } { i }$ ，提取出数据 $\cdot _ { 0 } \cdot \cdot ,$ ，保持 $( l _ { i } , h _ { i } , B _ { i } )$ （204号不变。在 ${ h _ { i } } ^ { W } = { l _ { i } } ^ { W }$ 时，直接从 $B _ { i }$ 中将 $m \times n$ 位的待嵌入隐藏数据提取出来。

b)对低平均值序列进行直方图逆过程如下：

(a)提取数据。按照步骤a)处理后的低平均值序列 $L ^ { \prime }$ 。若（20 ${ x _ { \operatorname* { m a x } } > x _ { \operatorname* { m i n } } }$ ，则当 $l _ { i } ^ { \prime \prime } { = } x _ { \mathrm { m a x } } + 1$ 时，提取出数据"1”，然后将 $l _ { i } ^ { \prime \prime }$ （20减1；若 $l _ { i } ^ { \prime \prime } { = } x _ { \mathrm { m a x } }$ ，则提取数据 $^ { \mathrm { \scriptsize ~ \mathfrak ~ { \omega } ~ } , \mathfrak { c } }$ 。若 $x _ { \mathrm { m a x } } < x _ { \mathrm { m i n } }$ ，则当（204号 $l _ { i } ^ { \prime \prime } { = } x _ { \mathrm { m a x } } - 1$ 时，提取数据"1”，然后将 $l _ { i } ^ { \prime \prime }$ 减1;若 $l _ { i } ^ { \prime \prime } { = } x _ { \mathrm { m a x } }$ ，则提取出的数据为 $\cdot _ { 0 } \cdot \cdot$ 。

(b)数据恢复。再次按顺序遍历低平均值序列 $L ^ { \prime }$ 。若$x _ { \operatorname* { m a x } } > x _ { \operatorname* { m i n } }$ ，则当 $l _ { i } ^ { \prime \prime } { \in } ( x _ { \operatorname* { m a x } } + 1 , x _ { \operatorname* { m i n } } )$ ，将 $l _ { i } ^ { \prime \prime }$ 减1。若$x _ { \mathrm { m a x } } < x _ { \mathrm { m i n } }$ ，则当 $l _ { i } ^ { \prime \prime } { \in } [ x _ { \operatorname* { m i n } } , x _ { \operatorname* { m a x } } - 1 )$ ，将 $l _ { i } ^ { \prime \prime }$ 减1。若$H _ { l } ( x _ { \mathrm { m i n } } ) \neq 0$ ，然后根据记录相应位置像素置为 $x _ { \mathrm { m i n } }$ 。

c)对低平均值进行直方图移位逆过程。按照步骤b)对高平均值 $H ^ { \prime }$ 进行操作。

# 4.3实验结果

实验中，采用"Lena”、“Bridge”、“Dollar”三幅大小为$5 1 2 \times 5 1 2$ 的256阶灰度图像进行测试，如图7所示。图9为编码所得到的最高、最低平均值序列，图8为ATMBTC编码生成的位平面，在ATMBTC编码后的载体图像中嵌入图4经过预处理的秘密图像，其嵌入信息后结果如图10所示。

![](images/9ce8d3fefc2dd1bf5f24ba45096de513fcce267aafaa442303c6cc32378a6583.jpg)  
图7原始载体图像

![](images/ac89ca286d7ecef31c67605d84a7ae1264a7d0557082e435eb2ca5f572e9000d.jpg)  
图8AMBTC生成的位平面

![](images/55fae689f8160fb71a5f9a86cc46f177b1f221c78512f5d33f54cae65acca517.jpg)  
图9a.b.c为AMBTC生成的低平均值序列;d.e.f为AMBTC生成的高平均值序列

![](images/d8c6f383811b09602d79b15394a9fe8818134732f9ecc254e26320bb0eb0c0e8.jpg)

# 5 鲁棒性实验

信息隐藏算法的抗攻击性实际是对鲁棒性进行检验，对图像进行空间滤波、有损压缩、几何变形等攻击，检验提取出秘密信息的恢复程度，这里用提取出秘密信息与原始信息的归一化相关系数作为评估算法鲁棒性的标准，可表示如下：

$$
{ \cal N } C = \frac { \underset { i } { \sum } w _ { i } \hat { w } _ { i } } { \sqrt { \underset { i } { \sum } w _ { i } ^ { 2 } } \sqrt { \underset { i } { \sum } \hat { w } _ { i } ^ { 2 } } } { \{ \underset { i } { \geq } T , \ } { \overleftrightarrow { { \mathcal { M } } } { \mathbb { \hat { Z } } } \{ { \underline { { \hat { \mathbb { Z } } } } } \{ { \underline { { \hat { \mathbb { Z } } } } } \} { { \underline { { \hat { \mathbb { Z } } } } } \{ { \underline { { \hat { \mathbb { Z } } } } } \{ { \underline { { \hat { \mathbb { Z } } } } } \{ { \underline { { \hat { \mathbb { Z } } } } } \{ { \underline { { \hat { \mathbb { Z } } } } } \} { { \underline { { \hat { \mathbb { Z } } } } }  { { \hat { \mathbb { Z } } } } \{ { \underline { { \hat { Z } } } } \{ { \hat { \mathbb { Z } } } } \} { { \underline { { \hat { Z } } } }  } { { \underline { { \hat { \mathbb { Z } } } } } } \} } }         
$$

其中： $T$ 为预先设定的阈值，经实验，设 $T$ 定值为0.6。

![](images/2f3a3887f13f66b101d852d90f8ba65f046c3cdd90a2cd4134c0dd0d99e4d29f.jpg)  
图11空间滤波攻击实验

表1算法性能比较  

<html><body><table><tr><td>图像</td><td>Lena</td><td>Bridge</td><td>Dollar</td></tr><tr><td>AMBTC算法PSNR（dB）</td><td>32.140</td><td>28.685</td><td>30.021</td></tr><tr><td>本文提出的算法PSNR（dB)</td><td>32.131</td><td>28.653</td><td>30.014</td></tr><tr><td>Chen 等人算法PSNR（dB）</td><td>32.140</td><td>28.685</td><td>30.021</td></tr><tr><td>本文算法恢复图像PSNR（dB)</td><td>32.131</td><td>28.653</td><td>30.014</td></tr><tr><td>本文算法嵌入容量（Bits）</td><td>16762</td><td>17567</td><td>16878</td></tr><tr><td>Chen 等人算法嵌入容量（Bits）</td><td>16414</td><td>17194</td><td>16544</td></tr></table></body></html>

在表1的实验结果中，可看出本文中直方图移位技术较Chen 等人提出算法在嵌入容量有所提升，而Chen等人算法相比AMBTC编码嵌入算法在性能上较优，且出现在“Lena""Bridge"载体图像的嵌入容量高于16384（ $1 2 8 \times 1 2 8$ ），主要由于这两幅图像中存在一些高低平均值相等的块。恢复后的载体图像与嵌入信息前的载体图像的PSNR都为32.131，表明秘密信息在未受攻击情况下，提取之后载体图像恢复完整，从而达到无损信息隐藏目的。

从空间滤波攻击的检测实验结果得出，经过预处理秘密信息，在受到空间滤波攻击后的NC值仍大于0.6，可看出本文提出的隐藏算法可以有效地抵抗空间滤波攻击和高斯噪声攻击，而且面临高斯滤波攻击时归一化系数最大为1，即对高斯滤波的攻击该算法具有完全抵抗的性能，且对于中值、均值滤波攻击时有很好的鲁棒性，但对与高斯噪声的攻击时鲁棒性相对较弱，因此接下的工作可以针对本文算法噪声攻击时提高鲁棒性。

![](images/5df8f3f897eb6da2c67b2f8945fa917bcb9077c1e360a1d210cfe411d84396c6.jpg)  
图10a为预处理后的秘密图像，b.c.d为含密载体  
图12剪切攻击算法性能比较曲线

![](images/825d1b38932b4e39517bc8101edceecb6853e66b402ec12840dcf1d35569a5c8.jpg)  
图13图像平移攻击算法性能对比曲线

![](images/69ba363f0f97897df2982676d02b64c1ce0db8fadabb630bc448bca4420f658b.jpg)  
图14图像旋转攻击算法性能对比曲线

![](images/27d3f522c75c68a39c64882673340839c8eadf53d58b59d6d84ce1b7b70ca6ca.jpg)  
图15图像缩放攻击算法性能对比曲线

从图12曲线看出，在隐藏载体受到剪切攻击后提取秘密信息，将本文提出算法与文献进行比较，随着剪切度增加到 $60 \%$ 时，本文中算法的NC值始终大于阈值0.6，表现出较强的抗剪切攻击，文献[6，7]算法小于0.6；图13中对于平移攻击测试，当受到平移面积大于400 时，其NC值较差于文献[6]，而且鲁棒性的整体稳定性不及文献[6、7]的算法；图14中受到旋转攻击测试时NC值高于0.65且有一定的规律性，而且抗旋转性能优于文献[6,7]；图15中的缩放攻击算法鲁棒性比较时，本文算法NC大于0.7，且在缩放倍数为1时达到最大0.886，当缩放倍数大于2时，NC值理想且保持稳定。实验表明，本文中隐藏算法在图像剪切、旋转以及缩放攻击时表现出较强的鲁棒性；当载体图像大面积受到平移攻击时，其鲁棒性较弱。但本文算法的整体抗攻击性能及其鲁棒性较好。

# 6 结束语

本文采用对秘密图像进行混沌置乱及行程编码的预处理，具有加密隐藏信息并减小嵌入数据的效果，采用基于直方图移位的AMBTC无损信息隐藏算法嵌入秘密信息，达到一定的视觉冗余，实验中本文算法嵌入容量为16762，高于Chen等人算法的嵌入容量16414，并实现无损信息隐藏。经过算法鲁棒性测试，并与文献[6，7]算法进行比较。实验结果表明，当载体图像受到局部攻击时，隐藏信息可以检测，本文算法性能相对于文献[6，7]具有明显优势，但在大面积被攻击时鲁棒性较差。结果显示，本文提出的信息隐藏方案不仅实现秘密指纹图像的安传输，而且在面临几何攻击与滤波攻击时具有较好的鲁棒性，完整提取出传输的秘密信息。

参考文献：   
[1]Ker A,Pevny T.Anew paradigm for steganalysis via clustering[C]/ Proc of SPIE,Media Watermarking, Security,and Forensics II.2011: 7880.   
[2]Qian Z, Zhou H, Zhang W, Zhang X. Robust steganography using texture synthesis [C]// Proc of the 12th International Conference on Intelligent Information Hiding and Multimedia Signal Processing.2016.   
[3] 刘娟妮，周诠，李小军，方海．多光谱图像变换域统计量移位鲁棒无损 信息隐藏[J].电讯技术,2015,55(11):1187-1193.(Liu Juanni,Zhou Quan,Li Xiaojun,Fang Hai. Statistical shiftsof multispectral image transforms with robust lossless information hiding [J]. Telecommunication Engineering,2015,55 (11): 1187-1193.)   
[4] 张怡，王慧琴．基于混沌置乱的小波域数字水印算法研究[J].电脑知 识与技术,2011,7(10): 2400-2402.(Zhang Yi, Wang Huiqin.Research on digital watermarking algorithm based on chaos scrambling in wavelet domain[J]. Computer Knowledge and Technology,2011,7(10): 2400- 2402.)   
[5］赵慧民，范九伦．一种在 JPEG2000 中隐藏指纹图像的方法研究[J]. 电路与系统学报,2010,15(2):27-32.(Zhao Huimin,Fan Jiulun.Study on the method ofhiding fingerprint image in JPEG2ooo [J]. Journal of Circuits and Systems,2010,15 (2): 27-32.)   
[6]房宜汕．一种基于 JPEG2000 特性的信息隐藏技术的研究[J].嘉应学 院学报,2013,31(2):24-29.(Fang Yiqi. Research on information hiding technology based on JPEG2o0o characteristics[J]. Journal of Jiaying University,2013,31(02): 24-29.)   
[7]张海涛，姚雪，陈虹宇，等．基于分层 Amold 变换的置乱算法 [J].计 算机应用,2013,33(8):2240-2243.(Zhang Haitao, Yao Xue,Chen Hongyu, Zhang Hao.Scrambling algorithm based on hierarchical Arnold transform [J].Journal of Computer Applications,2013,33 (8): 2240-2243.)   
[8] Tang Meng S,Chen X, et al. An adaptive image steganography using AMBTC compression and interpolation technique [J]. Optik: International Journal for Light and Electron Optics,2016,127(1): 471-477.   
[9] 黄蕊蕊，闫肃，解成俊，等．基于 JPEG_LS 的图像无损信息隐藏方法 [J].北华大学学报：自然科学版,2015,16(2):276-280.(Huang Ruirui, Yan Su,Xie Chengjun,Xu Xiaolong. Image lossess information hiding methodbased on JPEG_LS[J].Journal of Beihua University:Natural Science,2015,16(2): 276-280.)   
[10] Prameelamma M, Sridhar V, Nagendra G,et al.AMBTC-compressed images for lossless steganography [J]. International Journal of Advanced

Research in Computer Science & Electronics Engineering,2O12,1(6).

[11] Chen J,Hong W,Chen T S,et al.Steganography for BTC compressed images using no distortion technique [J]. Imaging Science Journal the,2010, 58 (4): 177-185.

[12] An oblivious fragile watermarking scheme for images utilizing edge transitions in BTC bitmaps [J]. Science China: Information Sciences,2012,

55(11):2570-2581.

[13]张新鹏，钱振兴，李晟．信息隐藏研究展望[J].应用科学学报，2016(5):475-489.(Zhang Xinpeng,Qian Zhenxing,Li Wei. Prospects ofinformation hiding research [J].Journal ofApplied Sciences,2016 (5): 475-489.)