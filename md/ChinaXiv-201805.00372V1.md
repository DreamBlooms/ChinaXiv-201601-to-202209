# 基于Curvelet-DSVD和视觉密码的强鲁棒零水印算法

曲长波，吴德阳

(辽宁工程技术大学 软件学院，辽宁 葫芦岛 125105)

摘要：为了更好的表现自然图像的曲线特性，进一步提高数字水印算法的鲁棒性，提出一种基于Curvelet-DSVD 和视觉密码相结合的强鲁棒零水印算法。首先对原始图像进行Amold置乱；其次进行Curvelet 变换得到低频域信息，对低频域信息进行分块并对各个块进行双奇异值分解(DSVD),利用块最大奇异值与整体奇异值均值之间的关系构造特征矩阵，同时利用视觉密码将水印信息生成两个共享份；最后将其中一个共享份进行 Amold 置乱后与特征矩阵进行异或运算生成零水印。实验结果表明，该算法能够有效地抵抗常规攻击，与现有的零水印算法相比，鲁棒性更强，安全性更高。

关键词：Curvelet变换；双奇异值分解；视觉密码；鲁棒性 中图分类号：TP309.2 doi:10.3969/j.issn.1001-3695.2017.10.0936

# Strong robust zero watermarking algorithm based on Curvelet - DSVD and visual cryptography

Qu Changbo, Wu Deyang (College of Software Liaoning Technical University,HuLudao Liaoning l25105,China)

Abstract:Inorder to beterperformthecharacteristicsof naturalimagecurves andfurtherimprove therobustnessof digital watermarking algorithms,this paper proposed arobust zero-watermarking algorithm based on Curvelet-DSVD and visual cryptography.Firstly,performingArnoldscramblingontheoriginalimage,thenobtainingthelowfrequencydomaininformation by Curvelet transform，segmenting the low frequency domain information,andeach block was double singular value decomposition(DSVD),byusing the relationship between the maximum singular value ofthe blockand the mean value of the globalsingularvalue structuring characteristic matrix.At thesametime,this paperused thevisual cryptography to generate two shared copiesofthe watermark information.Finalyoneoftheshares was executetoArnoldscrambleand then xoroperation withthe feature matrix to generate azero-watermark.Experimentalresultsshow that the proposed algorithmcan efectively resistthe conventional attacks and is more robust and more secure than the existing zero-watermarking algorithms.

Key Words: curvelet transform; double singular value decomposition (DsVD); visual cryptography; robustness

# 0 引言

为了解决传统变换域水印算法的透明性与鲁棒性之间的矛盾，温泉等人[1]提出零水印的概念，由于零水印算法不需要将版权信息嵌入到载体图像中，对载体图像的内容完整性起到很好的保护作用，所以近年来零水印在版权保护领域得到广泛的应用[2.3]。

传统的零水印算法大都利用小波变换和奇异值分解构造载体图像的特征信息，然后与水印信息结合生成零水印 $[ 4 ^ { \sim } 6 ]$ 。文献[4]利用离散小波和奇异值分解构造零水印，对于小范围的噪声攻击、滤波攻击和压缩攻击具有较好的稳定性，但对于较大强度的攻击鲁棒性较差。文献[5]提出一种基于不变质心的鲁棒零水印算法，选择不变质心作为稳定的几何参考点，能够有效的抵抗几何攻击的影响，但滤波攻击和噪声攻击对构造的特征矩阵产生一定影响。文献[6]提出一种基于DWT-SVD的图像双零水印算法，利用haar小波对载体图像进行两次变换，选择载体图像的低频域LL2来构造零水印。随着对水印算法的不断研究，近年来出现许多较为新颖的水印算法 $[ 7 ^ { - 9 ] }$ ，文献[7]选取图像感兴趣的区域构造特征矩阵，再将特征矩阵与水印图像进行异或运算生成零水印。算法对于常规攻击具有一定的鲁棒性，但当感兴趣域受到攻击时，水印信息影响较大，具有一定的局限性。文献[8]利用余弦离散小波变换（DCT）具有能量集中优势来构造零水印，但利用图像块均值构造特征矩阵稳定性较差。为提高图像特征的稳定性，曾文权等人[9利用整数小波变换和混沌加密原理提出一种基于整数小波变换的鲁棒零水印算法。实验结果表明算法对于非几何攻击具有较强的鲁棒性，但由于算法未考虑几何攻击对图像的影响，所以在受到剪切攻击和旋转攻击时，提取的水印相似度较低。为了克服几何攻击对载体图像的影响，曲长波等人[10]利用小波变换结合视觉密码提出一种基于视觉密码和边缘检测的零水算法。算法对于小范围的噪声攻击具有较好的鲁棒性，但对于几何攻击表现鲁棒性较差。肖振久等人[1]提出了一种基于增强奇异值分解和细胞神经网络的零水印算法，算法通过均匀化奇异值并结合神经网络算法解决了对角线失真问题，但神经网络的引入，增加了算法的时间复杂度。以上算法虽然使用小波变换能够很好地将图像分为高频域和低频域，但是自然图像中包含有大量的纹理特征，曲线奇异性表现比较突出,小波变换对于点奇异特性表现较好，而对于图像曲线奇异特性表现较差，所以在受到攻击时提取的水印信息往往影响比较大。

针对上述问题，本文提出一种基于Curvelet-DSVD和视觉密码的强鲁棒零水印算法。首先对载体图像进行Arnold置乱；其次对置乱后的载体图像进行Curvelet变换提取出图像曲线特征信息，并对得到的曲线信息的进行分块和DSVD；然后利用块最大奇异值与块整体最大奇异值的均值之间的关系构造特征矩阵，同时对水印图像进行视觉密码加密操作，产生两个秘密图份，将其中一个秘密图份进行Amold置乱，将特征矩阵与置乱后的秘密图份进行异或操作生成零水印；最后将生成的零水印与另一秘密图份保存至版权保护中心。

# 1 基础理论

# 1.1Curvelet变换理论

Curvelet变换是一种多分辨、带通、具有方向性的函数分析方法，是通过一种特殊的滤波过程和多尺度Ridgelet变换来实现的，对于图像曲线边缘的描述，其逼近性能具有近乎最优的非线性逼近误差衰减阶，对曲线特征信息具有很好的表示性能[12]。以笛卡尔坐标系下的 $f [ t _ { 1 } , t _ { 2 } ] ( 0 \leq t _ { 1 } , t _ { 2 } < n )$ 作为输入，Curvelet变换的离散形式为

$$
c ^ { D } ( j , l , k ) : = \sum _ { 0 \le t _ { 1 } , t _ { 2 } < n } f [ t _ { 1 } , t _ { 2 } ] \overline { { \phi _ { j , l , k } ^ { D } [ t _ { 1 } , t _ { 2 } ] } }
$$

其中： $j \in { 0 , 1 , 2 , 3 \cdots n }$ 为尺度参数； $l \in { 0 , 1 , 2 , 3 \cdots n }$ 为方向参数；$k = ( k _ { 1 } , k _ { 2 } ) \in Z ^ { 2 }$ 是一个旋转参数。Canddes 和Donoho 提出了一种基于USFFT(unequally spacefast Fourier trans form)的快速离散Curvelet变换实现方法[12]，步骤如下：

a)对于给定一个笛卡尔坐标下的二维函数进行 2DFFT 变换，得到二维频域信息。

图1是Curvelet变换的分解实例，其中图1(a)大小为512$\times 5 1 2$ 的Lena图像，（b）为Curvelet变换分解的图像，(c)为小波变换分解的图像。

![](images/61b8ffce7f73a2c52dae74c52b333af2ed794699acf7ebe2e352d70c0ff22108.jpg)  
图1Curvelet变换和小波变换实例

由图1可以看到，Lena图像经过Curvelet变换后被划分为6个尺度层,第一层为Coarse尺度层，第六层即最外层为Fine尺度层，中间的第二至第五层为Detail尺度层，每层的系数分别被划分为8、8、16、16个小方向，都是由高频系数组成的矩阵。而Lena 图像经过小波变换则被分成4个层，具体如图1(c)所示。分别统计Curvelet变换和小波变换后每层系数的能量，将每层的系数的绝对值的平方和作为能量进行直方图对比，具体如图2所示。

![](images/0cb9ccc5eadddf09c00db5262029c6e74fa25180a2e82a4293cf2941795ca4c7.jpg)  
图2Curvelet变换和小波变换能量直方图对比

其中图2(a)(b)横向表示频域变换后的层数，纵向表示对应的能量。由图2的能量分布图可知，经Curvelet变换后的图像的系数能量主要集中于第一层，其余的各层分布的能量较少，而经过小波变换后的图像的能量分布2、3和4层（主要含有高频信息）的能量较多。

# 1.2双奇异值分解(DSVD)

SVD矩阵分析中常用的数学工具，它可以将一个矩阵分解为三个矩阵的乘积[13]，对于一个大小为 $\mathbf { m } \times \mathbf { n }$ 的矩阵 $I$ ，奇异值分解可表示为

$$
\begin{array} { r } { I = U _ { m \times n } \left[ \begin{array} { c c c c c } { \delta _ { 1 } } & & & & \\ & { \delta _ { 2 } } & & & \\ & & { \ddots } & & \\ & & & { \delta _ { n - 1 } } & \\ & & & & { \delta _ { n } } \end{array} \right] _ { n \times n } V _ { n \times m } ^ { T } } \end{array}
$$

$$
\hat { f } [ n _ { 1 } , n _ { 2 } ] , - n _ { 1 } / 2 , n _ { 2 } / 2
$$

b)对得到的二维频域信息进行重采样，得到相应的采样值。

$$
\hat { f } [ n _ { 1 } , n _ { 2 } - n _ { 1 } , \tan \theta _ { 1 } ] , ( n _ { 1 } , n _ { 2 } ) \in P _ { j }
$$

c）将内插后的 $\hat { \boldsymbol f }$ 与 $\hat { \boldsymbol { \upsilon } }$ 函数相乘得到 $\hat { \ b { f } } [ { \boldsymbol n } _ { 1 } , { \boldsymbol n } _ { 2 } ]$

$$
\hat { \dot { f } } [ n _ { 1 } , n _ { 2 } ] = \hat { \dot { f } } [ n _ { 1 } , n _ { 2 } - n _ { 1 } \tan \theta _ { 1 } ] \bar { U _ { j } } [ n _ { 1 } , n _ { 2 } ]
$$

对 $\bar { f _ { j , l } }$ 进行IFFT逆变换得到离散Curvelet变换的系数集合$\boldsymbol { c } ^ { D } ( j , l , \boldsymbol { k } )$ □

δδ  
其中： $U _ { \mathrm { m } \times n }$ 左奇异矩阵， 为奇异值矩阵；δ𝑛-1δn  
$\delta _ { 1 } \geq \delta _ { 2 } \geq \cdots \geq \delta _ { n - 1 } \geq \delta _ { n } \geq 0$ ； $\boldsymbol { V } _ { n \times m } ^ { T }$ 为右奇异矩阵。图像经过奇异值分  
解会把冗余的信息去掉，用少量的奇异值代表整个图像的信息，  
在图像去噪和图像压缩具有重要的意义，同时经过奇异值分解  
后的图像具有一定抗攻击能力，所以经常用于数字水印领域来

提高算法的鲁棒性，但是传统奇异值分解的安全性较低且存在一定虚警问题[14]。

针对传统奇异分解存在的问题，提出一种具有安全性更高的双奇异值分解（DSVD）。DSVD不直接对图像进行SVD分解，而且先对图像进行双对角化操作，然后对双对角矩阵进行奇异值分解。DSVD分解过程如下：

a)先对矩阵 $I _ { \boldsymbol { m } \times \boldsymbol { n } }$ 进行双对角化分解，如式(6所示。

$$
\begin{array} { r } { I _ { m \times n } = U _ { _ { I } } \sum _ { I } V _ { I } ^ { T } } \end{array}
$$

其中： $\boldsymbol { U } _ { I }$ 为正交矩阵； $V _ { I } ^ { T }$ 为酉矩阵。

$$
\begin{array} { r } { \sum _ { I } \mathbf { \Psi } = \left[ \begin{array} { l l l l l l } { I _ { 1 1 } } & { I _ { 1 2 } } & & & & \\ & { I _ { 2 2 } } & { I _ { 2 3 } } & & & \\ & & { \ddots } & { \ddots } & & \\ & & & { I _ { n - 1 , n - 1 } } & { I _ { n - 1 , n } } \\ & & & & & { I _ { n , n } } \end{array} \right] } \end{array}
$$

b)然后对得到的双对角矩阵 $\Sigma _ { \scriptscriptstyle I }$ 进行奇异值分解，得到最大奇异值矩阵：

$$
\left\{ \begin{array} { l l } { \sum _ { \imath } = U _ { \Sigma } S V _ { \Sigma } ^ { T } } \\ { S = \mathbf { m a x } ( \sum _ { \imath } ) } \end{array} \right.
$$

# 1.3 视觉密码

视觉密码是两位伟大的数学家Moni Naor和Adi Shamir[15]提出的一种视觉系统解密的新型密码方案，它的核心思想是，将一个秘密图像（secretimage），利用视觉密码加密规则加密，得到两张共享图份，其中第一张共享份可以看做是秘密图像加密后得到的密文（cipher）,第二张共享图份可以看做是解码的秘钥（key）。由于每一个共享份都是像随机噪声一样杂乱无章的，所以密码破译者是无法从一张图份中得到另一张共享份的任何信息的，更加无法破解秘密图像。

本文利用的视觉密码原理将水印信息产生两个密钥，将其中一个密钥进行Armold置乱后与载体图像特征生成零水印，另一个密钥用于后期验证。其加密过程如式（9）～（10）所示。

$$
{ [ \begin{array} { l l } { 1 } & { 1 } \\ { 1 } & { 1 } \end{array} ] } = { [ \begin{array} { l l } { 1 } & { 0 } \\ { 0 } & { 1 } \end{array} ] } { \begin{array} { l l } { { [ \begin{array} { l l } { 0 } & { 1 } \\ { 1 } & { 0 } \end{array} ] } } & { } { \mathrm { k e y l } } \\ { { [ \begin{array} { l l } { 0 } & { 1 } \\ { 1 } & { 0 } \end{array} ] } } & { { [ \begin{array} { l l } { 0 } & { 1 } \\ { 1 } & { 0 } \end{array} ] } } \end{array} ] } \qquad { \mathrm { k e y } } 2 { \mathrm { } }
$$

$$
{ \left[ \begin{array} { l l } { 1 } & { 0 } \\ { 0 } & { 1 } \end{array} \right] } = { \left[ \begin{array} { l l } { { \left[ \begin{array} { l l } { 1 } & { 0 } \\ { 0 } & { 1 } \end{array} \right] } } & { { \left[ \begin{array} { l l } { 0 } & { 1 } \\ { 1 } & { 0 } \end{array} \right] } } & { { \mathrm { k e y l } } } \\ { { \left[ \begin{array} { l l } { 1 } & { 0 } \\ { 0 } & { 1 } \end{array} \right] } } & { { \left[ \begin{array} { l l } { 0 } & { 1 } \\ { 1 } & { 0 } \end{array} \right] } } & { { \mathrm { k e y 2 } } } \end{array} \right] }
$$

其中：两个密钥重叠得到 $\left[ { \begin{array} { l l } { 1 } & { 1 } \\ { 1 } & { 1 } \end{array} } \right]$ 则原始图像的像素为黑色像素，否则为白色像素。图3为视觉密码加密实例，其中图3(a)为水印图像，(b)和(c)分别是通过视觉密码原理生成的两个互不重叠的密钥share1和share2。

版权   
保护   
(a)版权水印 (b)sharel (c)share2

# 2 零水印算法

# 2.1 零水印生成

零水印的生成过程需要构造图像的特征信息，首先对大小为 $5 1 2 \times 5 1 2$ 图像进行Arnold置乱，然后对置乱后的图像进行Curvelet变换、分块和DSVD，最后构造特征矩阵。同时对版权水印进行视觉密码加密生成两个共享份，将其中一个共享份进行Amold置乱，最后将置乱后的共享份与特征矩阵进行异或操作生成零水印，将生成的零水印和另一共享份保存至版权保护中心。零水印具体生成步骤如下所示：

a)对大小为 $5 1 2 \times 5 1 2$ 的载体图像 $I$ 进行 Arnold 置乱，置乱方式如式(11)所示。

$$
\binom { x } { y ^ { * } } = \binom { 1 } { 1 } 2 \binom { x } { y } \bmod { ( N ) }
$$

b)对置乱后的载体图像进行Curvelet变换，得到Curvelet变换的曲线系数矩阵 $c I _ { 2 5 6 \times 2 5 6 }$ 。

c)然后按照式(12)对 $c I _ { 2 5 6 \times 2 5 6 }$ 进行分块，得到块矩阵 $B _ { k }$ 。

$$
\{ { \cal I } { \cal F } \bmod ( i , 4 ) { \Longrightarrow } 0 \& \& { \bmod ( j , 4 ) } { = } 0 \quad { \cal T } h e n
$$

其中： $i , j \in { 1 , 2 , 3 . . . 2 5 6 }$ ； $m \in \{ ( i - 3 ) \colon ( i ) \} , n \in \{ ( j - 3 ) \colon ( j ) \}$ ； $k \in { 1 , 2 , 3 } { \cdot \cdot \cdot 6 4 }$ 。

d)根据式(6)和(8)求得各个块 $B _ { k \times k }$ 的最大奇异值 $S _ { i , j }$ ，并构成最大奇异值矩阵 $S _ { i , j } ^ { \mathrm { m a x } }$ ，然后根据式(13)求得最大奇异值矩阵的均值 $M$ 。

$$
{ \cal M } = \sqrt { \sp \mathrm { \small { ~ m a x ~ } } } { \displaystyle \int _ { k \times k } \nonumber }
$$

e)利用每个块最大奇异值 $S _ { i , j } ^ { \mathrm { m a x } }$ 与整体最大奇异值的均值 $M$ 的关系构造特征矩阵 $T$ 。

$$
T = \left\{ { \begin{array} { l l } { 1 } & { I F \quad S _ { i , j } ^ { \operatorname* { m a x } } > M } \\ { 0 } & { \phantom { { \frac { 1 } { \sqrt { 1 } } } } E L S E } \end{array} } \right.
$$

f)利用视觉密码原理对水印图像 $W$ 进行加密操作，产生两个秘密图份 $w _ { 1 }$ 和 $w _ { 2 }$ ，将其中一秘密图份 $w _ { 1 }$ 进行 Arnold 置乱，得到置乱后的秘密图份 $w _ { 1 1 }$ 。

g)将f)中置乱后的秘密图份 $w _ { 1 1 }$ 与e)中得到的特征矩阵 $T$ 进行异或操作生成零水印 $z$ ，并将生成的零水印 $z$ 和秘密图份 $w _ { 2 }$ 存放于版权保护中心，两个置乱密钥 $K _ { \mathfrak u }$ 和 $K _ { \scriptscriptstyle 2 }$ 由客户保管。

$$
Z = X O R ( w _ { 1 1 } , T )
$$

零水印产生过程如图4所示。

# 2.2版权认证

版权认证过程需要从版权保护中心提取零水印 $z$ 和秘密图份 $w _ { 2 }$ ,版权认证过程的曲线特征信息提取过程与2.1节的步骤a) ${ \sim } \tt { e }$ )一致得到新的特征矩阵 $\boldsymbol { T }$ 。具体步骤如下：

a)从版权保护中心得到零水印 $z$ 与新构造的特征矩阵 $T$ 进行异或操作得到置乱后秘密图份 $w _ { 1 1 } ^ { \cdot }$ 。

$$
w _ { 1 1 } ^ { ' } = X O R ( Z , T ^ { ' } )
$$

b)从客户中得到密钥 $K _ { 2 }$ 将秘密图份 $w _ { 1 1 } ^ { \cdot }$ 进行 Arnold 逆置乱，得到解密后的秘密图份 $w _ { 1 } ^ { ' }$ 。

c)将解密后的秘密图份 $w _ { 1 } ^ { ' }$ 与版权中心的 $w _ { 2 }$ 进行重叠，得到版权水印 $W _ { 1 } ^ { ' }$ □

![](images/8dee45b0e59aa3a2fd84672fad7ade35bf1a9aaa0b1c19caa37da99287364c60.jpg)  
图4零水印生成过程

版权认证过程如图5所示。

![](images/86868534b16585ef7e52debb60304f65118d17c9967cdd5a4947de6e92074d83.jpg)  
图5版权认证过程

# 3 参数说明及鲁棒性攻击实验

# 3.1参数说明

为了验证本文算法的有效性，选择在64位Windows7操作系统和MATLABR2014a平台上进行仿真实验，实验载体图像选择大小为 $5 1 2 \times 5 1 2$ 的 Airplane、Lena、Baboon 、Paper 和Bride 的标准灰度图像，分别对应图6(a) $\sim$ （e）；版权水印图像选择大小为 $6 4 \mathrm { x } 6 4$ 含有"版权水印"四个字的二值水印图像，对应图6(f)；同时利用视觉密码将版权水印图像加密生成两个共享图份，分别对应图6(g)和(h)；为了进一步提高算法的安全性和鲁棒性，将得到的share1进一步置乱，用于增强算法的鲁棒性能，得到的置乱后的share1，对应图6(i)，具体如图6所示。

![](images/534a6f231629e63e955cc23b32073307b218aef4001c9d03174df75af677d36f.jpg)  
图6载体图像与版权水印

本文用归一化相关系数（NC）衡量提取的水印与原始水印相似度。NC是衡量数字水印的相关标准，本文采用如下计算方式[16]:

$$
{ \cal N } C ( w , w ^ { \prime } ) = \frac { \displaystyle \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } w ( i , j ) w ^ { \prime } ( i , j ) } { \sqrt { \displaystyle \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } w ( i , j ) ^ { 2 } } \sqrt { \displaystyle \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } w ^ { \prime } ( i , j ) ^ { 2 } } }
$$

其中： $w$ 、 $w ^ { ' }$ 分别表示初始水印和提取的水印。

# 3.2虚警率实验

为了验证算法的虚警问题，计算图6的五幅载体图像构造的零水印之间的相似性，不同零水印之间相似度越低，表明虚警率越低，否则相反。具体实验结果如表1所示。

表1虚警实验结果(NC 值)  

<html><body><table><tr><td>偏移参数</td><td>Airplane</td><td>Lena</td><td>Baboon</td><td>Paper</td><td>Bride</td></tr><tr><td>Airplane</td><td>1.0000</td><td>0.5777</td><td>0.4952</td><td>0.4849</td><td>0.5667</td></tr><tr><td>Lena</td><td>0.5777</td><td>1.0000</td><td>0.4852</td><td>0.4480</td><td>0.4385</td></tr><tr><td>Baboon</td><td>0.4952</td><td>0.4852</td><td>1.0000</td><td>0.5337</td><td>0.5184</td></tr><tr><td>Paper</td><td>0.4849</td><td>0.4480</td><td>0.5337</td><td>1.0000</td><td>0.4847</td></tr><tr><td>Bride</td><td>0.5667</td><td>0.4385</td><td>0.5184</td><td>0.4847</td><td>1.0000</td></tr></table></body></html>

由表1可知，五幅不同载体图像之间生成的零水印的相似度都很低，最高相似度为0.5777，最低相似度为0.4385，平均相似度为0.5033，表明本文算法虚警较低。

# 3.3非几何鲁棒攻击实验

常见的非几何鲁棒性攻击主要为噪声攻击、滤波攻击和压

缩攻击等。本文实验主要围绕以上几种非几何攻击进行鲁棒性攻击实验。

# 1）噪声攻击

本文对五幅不同的载体图像进行的不同强度的椒盐噪声攻击检验算法对于不同强度噪声的抵抗能力，并计算提取水印的NC 值。具体实验结果如表2所示。

表2不同强度椒盐噪声攻击实验数据表(NC 值)  

<html><body><table><tr><td>噪声强度</td><td>Airplane</td><td>Lena</td><td>Baboon</td><td>Paper</td><td>Bride</td></tr><tr><td>0.1</td><td>0.9751</td><td>0.9769</td><td>0.95087</td><td>0.9838</td><td>0.9709</td></tr><tr><td>0.2</td><td>0.9531</td><td>0.9612</td><td>0.9463</td><td>0.9549</td><td>0.9518</td></tr><tr><td>0.3</td><td>0.9308</td><td>0.9436</td><td>0.9102</td><td>0.9399</td><td>0.9296</td></tr><tr><td>0.4</td><td>0.9288</td><td>0.9103</td><td>0.9038</td><td>0.9198</td><td>0.9086</td></tr><tr><td>0.5</td><td>0.8846</td><td>0.8938</td><td>0.8601</td><td>0.89335</td><td>0.8865</td></tr></table></body></html>

由表2可以看出，随着噪声强度的增大，从五幅载体图像中提取的水印与原始版权水印的相似度（NC值）都很高，平均值在0.9100以上。对于载体图像Lena对于以上各种强度的椒盐噪声攻击时得到的NC值最高为0.9769，最低为0.8938。而对于载体图像Airplane、Baboon、Paper 和Bride 得到的NC 值的平均值也在0.9123以上。对于以上几种不同强度的椒盐噪声攻击，整体表现出较好的鲁棒性能。

2)JPEG压缩攻击

对五幅载体图像进行不同强度的JPEG压缩攻击，压缩攻击主要去除载体图像的冗余的信息，载体图像在受到压缩攻击后，生成的零水印也因此受到较大的影响。具体实验数据如表3 所示。由表3可知，对于不同的压缩强度攻击，从五幅载体图像中提取的水印与原水印的相似度的平均值为0.9945以上，表明本文算法对不同强度的JPEG压缩攻击表现出较强的鲁棒性能。

表3不同强度JPEG 压缩攻击实验数据表(NC 值)  

<html><body><table><tr><td>压缩因子</td><td>Airplane</td><td>Lena</td><td>Baboon</td><td>Paper</td><td>Bride</td></tr><tr><td>10</td><td>0.9909</td><td>0.9922</td><td>0.9778</td><td>0.9935</td><td>0.9904</td></tr><tr><td>20</td><td>0.9939</td><td>0.9939</td><td>0.9839</td><td>0.9974</td><td>0.9918</td></tr><tr><td>30</td><td>0.9961</td><td>0.9974</td><td>0.9874</td><td>0.9974</td><td>0.9935</td></tr><tr><td>40</td><td>0.9970</td><td>0.9961</td><td>0.9848</td><td>0.9983</td><td>0.9926</td></tr><tr><td>50</td><td>0.9957</td><td>0.9961</td><td>0.9918</td><td>0.9987</td><td>0.9944</td></tr><tr><td>60</td><td>0.9974</td><td>0.9987</td><td>0.9927</td><td>0.9987</td><td>0.9939</td></tr></table></body></html>

3)中值滤波攻击

对五幅载体图像分别进行中值滤波攻击，选择的模板大小分别为 $3 \times 3$ 、 $5 \times 5$ ， $7 \times 7$ 和 $9 \times 9$ 的滤波模板进行仿真实验。具体实验数据如表4所示。由表4可知，五幅载体图像在受到不同的滤波攻击后，得到NC值在 $0 . 9 6 3 \ 7 { \sim } 0 . 9 9 9 \ 1$ ，即使是9$\times 9$ 的滤波模板得到的NC值的平均值也在0.9813以上。所以本文算法对以上四种不同模板大小的中值滤波攻击具有较强的抵抗攻击能力。

表4中值滤波攻击实验数据表(NC 值)  

<html><body><table><tr><td>模板大小</td><td>Airplane</td><td>Lena</td><td>Baboon</td><td>Paper</td><td>Bride</td></tr><tr><td>3×3</td><td>0.9965</td><td>0.9974</td><td>0.9852</td><td>0.9991</td><td>0.9926</td></tr><tr><td>5×5</td><td>0.9917</td><td>0.9948</td><td>0.9769</td><td>0.9970</td><td>0.9865</td></tr><tr><td>7×7</td><td>0.9891</td><td>0.9926</td><td>0.9708</td><td>0.9957</td><td>0.9791</td></tr><tr><td>9×9</td><td>0.9856</td><td>0.9909</td><td>0.9637</td><td>0.9913</td><td>0.9751</td></tr></table></body></html>

# 3.4几何鲁棒攻击实验

几何攻击主要为旋转攻击和行列偏移攻击，几何攻击使得载体图像发生很大的变化，所以对提取的水印影响也较大。

1)旋转攻击

实验对五幅载体图像分别进行小幅度的旋转攻击，旋转角度分别为 $1 ^ { \circ }$ 、 $2 ^ { \circ }$ 和 $3 ^ { \circ }$ 。具体实验数据如表5所示。由表5可以看出，本文算法对于旋转攻击表现出较好的鲁棒性能。

表5旋转攻击实验数据表(NC 值)  

<html><body><table><tr><td>旋转度数</td><td>Airplane</td><td>Lena</td><td>Baboon</td><td>Paper</td><td>Bride</td></tr><tr><td>向左1°</td><td>0.9850</td><td>0.9838</td><td>0.9816</td><td>0.9833</td><td>0.9816</td></tr><tr><td>向右1°</td><td>0.97981</td><td>0.9738</td><td>0.9838</td><td>0.9887</td><td>0.9724</td></tr><tr><td>向左2°</td><td>0.9417</td><td>0.9516</td><td>0.9466</td><td>0.9427</td><td>0.9416</td></tr><tr><td>向右2°</td><td>0.9465</td><td>0.9423</td><td>0.9537</td><td>0.9403</td><td>0.9430</td></tr><tr><td>向左3°</td><td>0.9300</td><td>0.9369</td><td>0.9376</td><td>0.9280</td><td>0.9288</td></tr><tr><td>向右3°</td><td>0.9321</td><td>0.9281</td><td>0.9325</td><td>0.9363</td><td>0.9348</td></tr></table></body></html>

# 2）行列偏移攻击

对五幅载体图像分别进行上、下、左、右四个方向进行不同行列的移动攻击,移动丢失的像素进行置0操作。具体实验数据如表6所示。由表6可知，对五幅载体图像偏移2列时，提取的水印NC值在0.9671以上。而偏移5行时，得到的NC值最低为0.9236，最高为0.9506。由于Curvelet变换具有多尺度、多方向性，所以对于各个方向的攻击时，依然能够很好地提取水印信息，说明本文算法对于抵抗各个方向的行列偏移攻击表现出的鲁棒性较强，

表6行列偏移攻击实验结果(NC值)  

<html><body><table><tr><td rowspan="2">偏移 方向</td><td rowspan="2">偏移 参数</td><td rowspan="2"></td><td rowspan="2">Lena</td><td rowspan="2">Baboon</td><td rowspan="2">Paper</td><td rowspan="2">Bride</td></tr><tr><td>Airplane</td></tr><tr><td>向左</td><td>2列</td><td>0.9673</td><td>0.9756</td><td>0.9707</td><td>0.9698</td><td>0.9638</td></tr><tr><td>偏移</td><td>5列</td><td>0.9326</td><td>0.9496</td><td>0.9239</td><td>0.9243</td><td>0.9416</td></tr><tr><td>向右</td><td>2列</td><td>0.9716</td><td>0.9723</td><td>0.9671</td><td>0.9673</td><td>0.9695</td></tr><tr><td>偏移</td><td>5列</td><td>0.9260</td><td>0.9482</td><td>0.9226</td><td>0.9206</td><td>0.9361</td></tr><tr><td>向上</td><td>2行</td><td>0.9718</td><td>0.9792</td><td>0.9711</td><td>0.9835</td><td>0.9726</td></tr><tr><td>偏移</td><td>5行</td><td>0.9251</td><td>0.9430</td><td>0.9236</td><td>0.9496</td><td>0.9420</td></tr><tr><td>向下</td><td>2行</td><td>0.9846</td><td>0.9809</td><td>0.9712</td><td>0.9738</td><td>0.9752</td></tr><tr><td>偏移</td><td>5行</td><td>0.9331</td><td>0.9506</td><td>0.9341</td><td>0.9459</td><td>0.9413</td></tr></table></body></html>

# 3.5组合攻击

为了进一步验证算法的强鲁棒性能，本文增加组合攻击仿真实验，组合攻击的类型分别为旋转攻击 $^ +$ 噪声攻击、JPEG压缩攻击 $^ { \cdot + }$ 噪声攻击、JPEG 压缩攻击 $^ { \cdot + }$ 中值滤波攻击、行列偏移攻击 $^ { \cdot + }$ 中值滤波攻击和行列偏移攻击 $^ { \cdot + }$ 高斯噪声攻击等。具体实验数据如表7所示。由表7可知，对于JPE压缩 $3 0 \% +$ 中值滤波，载体图像Airplane、Lena、Paper 和Bride 得到的NC 值都在0.9913以上。对于JPEG压缩 $3 0 \% +$ 高斯噪声0.05攻击时，整体得到的NC值的平均为0.9668。总体而言，本文算法对于以上几种组合攻击表现出较强的鲁棒性能。

表7组合攻击实验数据表 (NC值)  

<html><body><table><tr><td>攻击类型</td><td>Airplane</td><td>Lena</td><td>Baboon</td><td>Paper</td><td>Bride</td></tr><tr><td>向左旋转2°+椒 盐噪声0.05</td><td>0.9368</td><td>0.9312</td><td>0.9261</td><td>0.9248</td><td>0.9213</td></tr><tr><td>JPEG压缩30%+ 高斯噪声0.05</td><td>0.9685</td><td>0.9756</td><td>0.9611</td><td>0.9709</td><td>0.9582</td></tr><tr><td>JPEG压缩30%+</td><td>0.9935</td><td>0.9970</td><td>0.9822</td><td>0.9956</td><td>0.9913</td></tr><tr><td>中值滤波3x3 向下偏移2 行+</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>中值滤波 5x5</td><td>0.9709</td><td>0.9792</td><td>0.9606</td><td>0.9839</td><td>0.9766</td></tr><tr><td>向右偏移2列+ 高斯噪声0.05</td><td>0.9505</td><td>0.9556</td><td>0.9931</td><td>0.9561</td><td>0.9526</td></tr></table></body></html>

# 3.6对比实验

为了更好地验证本文算法的鲁棒性能，选择大小为 $5 1 2 \times$ 512的Lena图像作为载体图像，水印图像选择大小为 $6 4 \times 6 4$ 含有“版权水印”的二值图像与文献[4,8.9]进行实验对比，具体不同攻击类型与实验结果如表8所示。

# 1)鲁棒性分析

由表8可知，本文算法对于抵抗非几何攻击和几何攻击相比于文献[4,8.9]表现出的鲁棒性能更优秀。对于非几何攻击，当噪声强度为0.2时，文献[4]得到的NC值为0.8040，鲁棒性较差。椒盐噪声攻击如图7所示。由图7可以看出，随着噪声强度越来越大，本文算法的NC值一直比文献[4,8,9]的要高。JPEG压缩攻击如图8所示。从图8可以看出，在不同的JPEG压缩强度下，文献[8,9]与本文算法得到的NC值几乎一致，而对比文献[4]具有较大的提升。由于文献[4,8.9]使用的小波变换具有局部局限性，不具有方向性，在受到非几何攻击时，图像边缘信息常常被削弱。本文算法所使用的Curvelet变换和DSVD有效地增强了算法的鲁棒性，因为Curvelet变换对图像边缘信息起到了增强的效果，相比于小波变换对于图像的边缘信息具有更强的表现能力，所以图像在受到非几何攻击时鲁棒性更强。

对于几何攻击，相比文献[4,8.9]具有较大的提升，尤其在剪切攻击和旋转攻击方面，在剪切攻击方面本文算法比文献[9]提升 $6 \%$ 左右。旋转攻击如图9所示。从图9可以看出，对于不同角度的旋转攻击，本文算法的NC值一直比文献[4,8,9]的要高，平均高出 $5 \%$ 左右，而向左旋转 $3 ^ { \mathrm { o } }$ 时，本文的NC值在0.93左右，文献[4,8.9]的NC值都0.9以下，鲁棒性较差。对于行列偏移攻击，相比文献[4,8,9]提升 $\% 2 . 9 \%$ 。文献[4]使用块最大奇异值构成图像的特征，在像素位置发生变化时，块的最大奇异值也会产生较大的变化。文献[8]使用DCT的均值构造的零水印，在受到剪切操作时，图像块均值影响较大。而文献[9]直接在空域中利用块均值与整体均值的关系构造特征矩阵，在受到几何攻击时，图像的像素或像素的位置发生了变化，直接影响了块均值与整体均值的关系，稳定性较差。本文使用的块最大奇异值与整体最大奇异值构造特征，最大奇异值具有能量集中稳定性能，相比文献[4,8,9]具有稳定性更高。总体而言，本文算法对于常规的鲁棒性攻击要比文献[4,8,9]的更具有优势，鲁棒性更强。

表8本文算法与文献[4,8,9]对比实验数据表(NC 值)  

<html><body><table><tr><td>攻击 类型</td><td>参数</td><td>文献 [4]</td><td>文献[8]</td><td>文献</td><td>本文</td></tr><tr><td>椒盐</td><td>0.05</td><td>0.9140</td><td>0.9738</td><td>[9] 0.9739</td><td>算法 0.9878</td></tr><tr><td>噪声</td><td>0.2</td><td>0.8062</td><td>0.9478</td><td>0.9365</td><td>0.9612</td></tr><tr><td>高斯</td><td>0.05</td><td>0.9454</td><td>0.9585</td><td>0.9949</td><td>0.9843</td></tr><tr><td>噪声</td><td>0.2</td><td>0.8040</td><td>0.9144</td><td>0.9707</td><td>0.9631</td></tr><tr><td>中值</td><td>模板大小 3x3</td><td>0.9819</td><td>0.9766</td><td>0.9971</td><td>0.9974</td></tr><tr><td>滤波 高斯</td><td>模板大小3x3</td><td>0.9832</td><td></td><td></td><td>0.9965</td></tr><tr><td>滤波 JPEG</td><td>压缩因子10</td><td>0.9300</td><td></td><td>0.9895</td><td></td></tr><tr><td>压缩</td><td>压缩因子30</td><td>0.9707</td><td>0.9917 0.9913</td><td>0.9927</td><td>0.9922 0.9935</td></tr><tr><td>剪切</td><td>左上角1/16</td><td>0.9587</td><td>0.9357</td><td>0.8712</td><td>0.9389</td></tr><tr><td>攻击</td><td>右下角1/16</td><td>0.9590</td><td>0.9295</td><td>0.8812</td><td>0.9300</td></tr><tr><td>旋转</td><td>向左旋转3°</td><td>0.8893</td><td>0.8772</td><td>0.8474</td><td>0.9369</td></tr><tr><td>攻击</td><td>向右旋转3°</td><td>0.8818</td><td>0.86677</td><td>0.8662</td><td>0.9281</td></tr><tr><td>行列</td><td>下移2行</td><td>0.9033</td><td>0.9597</td><td>0.9668</td><td>0.9809</td></tr><tr><td>偏移</td><td>右移2列</td><td>0.8803</td><td>0.9516</td><td>0.9597</td><td>0.9723</td></tr><tr><td></td><td>先缩小0.5倍再放 大2倍</td><td>0.9924</td><td>0.9984</td><td>0.9984</td><td>0.9988</td></tr><tr><td>缩放 攻击</td><td>先放大4倍再缩 小0.25倍</td><td>0.9982</td><td>0.9991</td><td>0.9993</td><td>0.9995</td></tr></table></body></html>

![](images/830e92a9185abcb44ab2d8f039cbdbaf3ffcb846a528dc08858f4ceb73508394.jpg)  
图7椒盐噪声攻击

![](images/421b6a61d076c97251e6774fff05fdb9b1da787d4d8e57a32eff556b86d4eedd.jpg)  
图8JPEG压缩攻击

![](images/7a9260abe3a7aa85eb553316fa4abc20e35a252653eed73fd9f42d0ab410ccaa.jpg)  
图9旋转攻击

2)安全性分析

在安全性能方面，本文算法相比文献[4,8.9]更安全，文献[4,8,9]只使用传统的加密操作，安全性较低。本文算法在提取特征过程中对载体图像进置乱操作，一是消除图像像素间的相关性，二是加强算法的安全性,攻击者在对载体图像进行特征提取时，在不知道特征提取的密钥情况下是很难提取到一致的特征信息。同时使用视觉密码和Armold置乱方式对水印信息进行加密处理，生成的零水印并不是直接由版权水印构造的，而是利用视觉密码产生的共享图份进行构造，由于共享图份是一张类似噪声点的密钥图份，所以即使获得零水印信息也无法得知其中的版权信息。

# 4 结束语

本文基于Curvelet 变换、DSVD和视觉密码理论提出一种基于Curvelet-DSVD和视觉密码的强鲁棒零水印算法，该算法克服了传统零水印算法不能表征自然图像曲线特征和对于较大强度攻击鲁棒性差的问题。同时，视觉密码实现将版权水印一分为二，实现三方认证方式，Arnold变换对视觉密码的共享份进行置乱，进一步提高了水印的安全性。实验结果表明，该算法对于常规的噪声攻击、滤波攻击、压缩攻击、旋转攻击、行列偏移攻击表现出较强的鲁棒性能，同时算法的安全性较高。

但本文算法对于较大强度的组合攻击时表现的鲁棒性稍差，有待进一步的优化，在下一步的研究中，将进一步提高算法对于复杂环境中的抗攻击能力。

# 今兮义雕：

[1]温泉，孙锁锋，王树勋．零水印的概念与应用[J]．电子学报,2003,31 (2): 214-216.   
[2]吴伟民，丁冉，林志毅，等．基于混沌的医学图像窜改定位零水印算法 [J].计算机应用研究,2014,31(12):3685-3688.   
[3]Rao Y R,Nagabhooshanam E.A novel image zero-watermarking scheme based on DWT-BN-SVD[C]// Proc of International Conference on Information Communication and Embedded Systems.2014: 1-6.   
[4]Rani A,Bhullar A K,Dangwal D,et al.A zero-watermarking scheme using discrete wavelet transform [J].Procedia Computer Science,2015,70:603- 609.   
[5]Liu P,Tan Y. Robust zero-watermarking algorithm based on invariant centroid [C]// Proc of International Conference on Computational and Information Sciences. 2013: 758-761.   
[6]陈伟琦，李倩．基于 DWT-SVD 的图像双零水印算法[J].计算机工程 与科学,2014,36 (10): 1991-1996.   
[7]Zhang L,Cai P, Tian X,et al. A novel zero-watermarking algorithm based on DWT and edge detection [C]//Proc of the 4th International Congress on Image and Signal Processing. 2011: 1016-1020.   
[8]赵杰．基于DCT 均值的图像零水印算法[J]．系统仿真技术,2015,11 (4): 304-306.   
[9] 曾文权，熊祥光．基于整数小波变换的鲁棒零水印算法[J].微电子学 与计算机,2016,33(4):97-101.   
[10]曲长波，李栋栋．基于视觉密码和边缘检测的零水印算法[J].计算机 应用与软件,2016,33(9):328-333.   
[11]肖振久，张晗，陈虹，等．增强奇异值分解和细胞神经网络的零水印 [J].中国图象图形学报,2017,22(3):288-296.   
[12]汪太月，李宏伟，李志明．基于Curvelet变换的数字水印算法[J].数学 的实践与认识,2012,42(17):124-128.   
[13]何冰．基于 SVD和 Radon 变换的抗旋转攻击盲水印算法[J].计算机 工程与应用,2012,48 (20):200-205.   
[14] Srilakshmi P,Himabindu C.Image watermarking with path based selection using DWT & SVD [C]// Proc of International Conference on Computational Intelligence and Computing Research.2016:1-5.   
[15] Naor M,Shamir A. Visual cryptography [C]//Advances in Cryptology Eurocrypt'94.1995:1-12.   
[16]曲长波，杨晓陶，袁铎宁．小波域视觉密码零水印算法[J]．中国图象 图形学报,2014,19(3):365-372.