# 一种基于复合混沌序列的图像加密方法

张晓博1,²，彭进业1，习敏

(1．西北工业大学 电子信息学院，西安 710072;2.长安大学 信息工程学院，西安 710064;3．西安交通大学 电子与信息工程学院，西安710049)

摘要：针对低维度混沌系统的密钥空间小，加密系统安全性较低的不足。提出一种由 Sine混沌改变均匀分布Logistic混沌排列次序形成复合混沌序列的图像加密方法。首先，产生服从均匀分布的Logistic混沌序列，用 Sine混沌序列重排该序列整数化后的重复部分，以此无重复数值的复合混沌序列进行像素位置置乱；之后，由于仅进行位置置乱不能改变图像的灰度统计直方图特征，用Sine混沌重排整个Logistic混沌序列形成复合混沌序列，以此进行像素扩散完成图像加密。对方法安全性从密钥空间、密钥敏感性、差分分析、统计直方图、相邻像素相关性、信息熵方面进行了测量。实验结果表明该方法密钥空间大、敏感性高，能有效地抵抗穷举分析、差分分析和统计分析。

关键词：图像加密；均匀分布；Logistic 混沌；Sine混沌 中图分类号：TP309.7 doi:10.3969/j.issn.1001-3695.2018.05.0393

# Image encryption algorithm based on complex chaotic sequences

Zhang Xiaobo1,2, Peng Jinye², Xi Min³ (1.SchooloflectronicInformation,NothweterolyechicalUniversityXian,Ca;.holofftion EngineeringChang'an UniversityXi'an7064,China;3.ShoolofElectronics&InformationEnginering,Xi'anJtong University,Xi'an 710049,China)

Abstract:Forthelowdimensional chaoticsystem,thekeyspace issmaland thesecurityoftheencryption system islow.This paper presents animage encryption methodforcomplex chaotic sequences formedby Sine chaoschanginguniformly distributed Logistic chaos order.First,aLogisticchaotic sequence obeyinguniformdistributionis generated.Sinechaotic sequenceis used torearrange therepeated partafter the integerof thesequence,sothatthecompound chaotic sequence withoutrepeating value is used forpixel position disorder.After that,because position scrambling alone cannotchange the histogram features of gray statisticsoftheimage,Sinechaos wasused torearrange the entireLogisticchaossquencetoformcompoundchaotic sequence, so as to complete image encryption by pixel difusion.The method security was measured from key space,keysensitivity diferentialanalysis,statisticalhistogram,adjacentpixelcorrelationand informationentropy.Theexperimentalresultsshow thatthis methodhasalarge keyspaceandhigh sensitivity,andcan effectivelyresist exhaustive analysis,differentialanalysis and statistical analysis.

Key words:Image encryption; uniform distribution; Logistic chaos; sine chaos

# 0 引言

随着互联网技术的日趋成熟与信息技术的发展，越来越多的信息被数字化通过网络传播，这些信息的形式有文字、图像、视频等。图像由于直观、生动的特点被广泛用于信息传播和交换。在日趋复杂的网络环境中保证传输图像的安全性和保密性具有重要意义。对具有数据量大、像素间存在相关性等特点的图像数据，IDEA、AES和DES等主要面向文本加密的方法不

具优势[1,2]。

混沌系统产生的连续信号经离散化后形成混沌序列，具有不可预测性、非周期性等特点，在图像加密领域具有突出优势，基于混沌系统的图像加密成为研究热点[3]。文献[4]提出使用Logistic 映射和二维Henon 映射，通过图像位置置乱和像素灰度值加密两个步骤完成加密。文献[5]使用Logistic 映射分别进行位置置乱和灰度值扩散。文献[6]对每个像素点进行一次位置置乱后紧接着进行一次扩散。这些方法相较于单一的位置置乱，不但改变了像素位置而且改变了像素灰度值分布，增大了破译难度。但上述方法使用的Logistic混沌的统计特性不服从均匀分布，密文的隐藏性有一定不足。

混沌加密的安全性很大程度上依赖于混沌序列的分布性、随机性和复杂性[7]，对基本混沌序列进行改造是有益的。文献[8]针对1维Logistic 映射只有两个可变参数的不足，提出了一种基于3维交织编码Logistic 映射产生混沌序列的方法。文献[9]提出了一种Logistic 映射和双随机相位编码结合的彩色图像加密方法。文献[10]提出由Logistic 映射和蔡氏电路（Chua'scircuit)组成Logistic-Chua复合混沌映射产生混沌序列的方法。文献[11]使用Logistic、Ten 和Sine 等混沌映射两两之间进行异或、取模和反馈操作形成新的复合混沌。文献[12]对Logistic 混沌序列进行均匀化，并在此基础上通过序列元素的位置交换实现一种Logistic随机排列的生成方法（Logisticrandompermutation based on position interchange,LRPRI），该方法对均匀分布的Logistic 序列，首先从以1,2，.，n排列的序列中任选一个位置的数与最后位置n上的数进行位置互换；之后从余下的1,2，.，n-1序列中再随机选择一个数与n-1位置上的数互换，直到结束。该方法通过对均匀分布Logistic序列进行位置交换，进一步增加了Logistic 的无序性，但使用单一混沌序列作为密钥序列的安全性有待提高。

在文献[11,12]的基础上，本文提出了一种复合混沌序列生成方法。首先产生一个服从均匀分布的Logistic混沌序列，再依据Sine 混沌序列的数值大小次序来重新排列Logistic序列中元素的排列位置，以形成复合混沌序列。方法通过不同类型的混沌序列来改变混沌序列的排列次序，既保持原有混沌序列的均匀分布特性，又通过重新排序Logistic序列形成复合混沌，增强了密钥序列的无序程度。

本文的加密过程包括位置置乱和像素扩散两步。在位置置乱中，为了避免在将混沌序列值转换为整数时，由于取整的舍入误差引起的重复数值。提出用Sine序列重排部分Logistic序列次序的无重复数值的复合混沌序列生成方法。在像素扩散中，为了进一步增大Logistic序列的无序性，依据Sine序列值大小的排序重排全部Logistic序列的排列次序，生成像素扩散用复合混沌序列。经实验，本文方法能有效地抵抗穷举分析、统计分析和差分分析等攻击类型。

# 1 混沌序列

基于混沌序列的图像加密通常是将混沌序列与原图像信息进行异或、循环移位等运算，使原图像信息变为具有类似随机噪声的性态，达到加密目的。以下是本文用到的混沌序列。

# 1.1基本 Logistic 混沌序列

混沌在动力学系统中指确定性动力学系统因对初值敏感而表现出的不可预测、类似随机性的运动。在图像处理领域常使用Logistic 混沌映射进行图像加密。Logistic 混沌映射是一种动力系统，系统方程为

$$
x _ { i + 1 } = \mu x _ { i } ( 1 - x _ { i } )
$$

其中： $x _ { i } \in V , i = 0 , 1 , 2 , \dotsc$ ，称为状态， $x _ { 0 }$ 是初值， $\mu$ 为混沌系统的李雅普诺夫(Lyapunov)指数，取值区间为(O,4]。当Lyapunov指数 $\mu$ 在区间（3.5699456,4.0]时，Logistic 映射呈混沌状态，其迭代生成的序列值处于一种随机分布的状态，系统状态的值域$x _ { i } \in ( 0 , 1 )$ 。

基本的Logistic 映射所产生的序列是非均匀分布的，直接用于图像加密存在一定安全隐患。

# 1.2服从均匀分布的混沌序列

目前已有一些将混沌序列转换为具有均匀分布统计特性序列的研究[12\~14]，本文采用序列映射的方法进行转换[12]。对于基本Logistic 混沌序列 $x _ { 1 }$ 按式（2）映射转换为服从均匀分布的混沌序列序列 $x _ { 2 }$ ，算式如下：

$$
x _ { 2 } = \frac { 2 } { \pi } \arcsin \sqrt { x _ { 1 } }
$$

转换后，序列 $x _ { 2 }$ 为区间(0.1)上服从均匀分布的随机变量。由μ为3.997， $x _ { 0 }$ 为0.512，迭代30000 次产生Logistic序列的序列值分布直方图如图1（a）所示，根据式（2）转换后服从均匀分布的Logistic 序列统计直方图如图1（b）所示。

![](images/7480129d3d2609cce2aab67ff9b1cf2e80a981c71b2ec9f48f458e07de8a65ef.jpg)  
图1Logistic序列统计直方图

从图1(b)序列值出现频数的统计直方图可以看出，经过映射转换后的Logistic序列在（0,1）区间序列值的出现机率是均等的。

# 1.3Sine 混沌序列

用于构造复合混沌序列的Sine 映射的表达式为

$$
x _ { n + 1 } = { \frac { a } { 4 } } \sin ( \pi x _ { n } ) 0 < a \leq 4
$$

其中：系统参数α的取值范围 $\in ( 0 , 4 ]$ 。由于Sine 函数的值域区间是[-1,1]，在根据其序列值大小进行重排其他序列次序时运算快捷，因此选择由Sine 混沌来改变Logistic 混沌序列的排列次序以构成复合混沌序列。

# 2 图像像素位置置乱

像素位置置乱的目的是从图像空间位置上掩盖明文、密钥和密文之间的关系。方法用无重复数值的复合混沌序列作为置乱密钥序列，改变图像的像素点位置，实现位置置乱。

# 2.1无重复数值置乱密钥序列

本文在均匀分布Logistic序列的基础上提出一种无重复数值的复合混沌序列实现方法。方法用Sine类型的混沌序列改变均匀分布Logistic 序列的排列，形成新的复合混沌序列。考虑到若直接用此复合混沌序列进行图像位置置乱，需要将取值范围是（0,1）之间浮点数的Logistic序列与图像像素坐标对应，通常做法是将序列值乘以图像的大小后再取整数。浮点数取整数是根据四舍五入进行取整，会出现相当数量的相同整数。使用具有相同整数的序列去改变明文图像像素位置时，其所对应像素的位置不会被移动，达不到置乱目的。为解决这个问题，提出无重复数值的置乱密钥序列产生方法，即用Sine混沌序列替换整数化后Logistic序列中重复数值，生成加密用的复合混沌序列，步骤如下：

a）对大小为 $\mathbf { M } { \times } \mathbf { N }$ 图像，产生一组长度均为L的Logistic序列 $x _ { 1 }$ ，用式（2）转换为均匀Logistic序列。为保证混沌性，截取从200点之后长度为 $\mathbf { M } { \times } \mathbf { N }$ 的部分，记为序列ml。b）由于 $\mathrm { m } 1$ 取值范围是（0,1）之间的浮点数，为了和被置乱图像的像素位置对应，将m1中的每个元素值乘以（ $\mathbf { \hat { M } } \mathbf { \times N } \mathbf { - } 1 \mathbf { \cdot }$ ，再加1使序列中每个数值改变为 $( 1 ,  { \mathrm { M } } \times  { \mathrm { N } } )$ 之间的浮点数，记为序列 $\mathbf { m } 2$ 。c）用四舍五入的方法将序列 $\mathbf { m } 2$ 中的数值转换为整数，会在序列中产生相当数量的重复数值。将重复出现的数值只保留第一次出现时对应序列位置上的数值，之后再次出现的序列值被置为0，并记录重复出现的数值的总数S，及其在m2中的位置；

d）用Sine 映射产生一组长度为S的混沌序列，序列的值为[-1,1]。e）将Sine 混沌序列的值按照大小进行升序排列，并用一维数组R记录新序列中每个值在原序列中的位置。f）将 $\mathbf { m } 2$ 中没有出现在 $\left[ 1 , \mathbf { M } \times \mathbf { N } \right]$ 之间的数值，依照数组R的次序插入步骤3中被置为0的序列位置上。

通过以上步骤得到长度为 $\mathbf { M } { \times } \mathbf { N }$ ，取值范围为 $[ 1 , \boldsymbol { \mathrm { M } } \times \boldsymbol { \mathrm { N } } ]$ 且值为互不相同整数的序列 $\mathbf { m } 3$ ，以 $\mathbf { m } 3$ 作为位置置乱密钥序列。

以图像大小 $\mathbf { M } { \times } \mathbf { N }$ 为 $2 5 6 \times 2 5 6$ 图像的置乱密钥序列生成进行说明。密钥序列的参数为 $[ \mu , x _ { 1 } ( 0 ) , \alpha , x _ { 2 } ( 0 ) ]$ ,其中 $\mu$ 为Logistic混沌的 Lyapunov 指数， $x _ { 1 } ( 0 )$ 为初值； $a$ 为 Sine 函数系数，$x _ { 2 } ( 0 )$ 为初值，数值取[3.9997,0.512,4.0,0.88]。首先，产生长度为65536 的均匀分布Logistic 序列，每个序列值乘以图像大小$\mathbf { M } { \times } \mathbf { N }$ ，转换为32位无符号整数序列；此时，序列由于取整舍入产生了24400个重复的数值；之后，记录这些重复位置上的数值和在Logistic序列中的位置；最后，生成长度为24400的 Sine混沌序列，依照 Sine 序列值的升序，将上一步1\~65536中没有出现的24400的数重新填入到这些重复位置中，产生一个和图像大小相等，且数值为1至65536的无重复数值的整数序列。序列值的排列次序是由Logistic和Sine 混沌序列共同决定，其序列值如图2所示。

![](images/fa62f61257e97e01bf23d5d1f5ea8309e570c145d726b1d2cc8fff478e6c8aea.jpg)  
图2无重复数值置乱密钥序列

图2中，序列长度和图像的大小一致，均为65536，序列的值为1-65536，且每个值只出现一次。

# 2.2图像像素位置置乱

图像像素位置置乱通过密钥序列打乱原图像的像素位置。本文提出无重复数值的置乱密钥生成后，像素位置置乱的步骤得到简化，只需以下四步：

a）依照2.1节方法用Logistic 混沌和 Sine 混沌序列产生无  
重复数值的整数密钥序列。b）将图像转换为一维序列。c)将一维序列中每个元素按照生成的整数密钥序列中对应  
元素内的值作为移动目标位置依次进行移动。d）转换一维序列为二维，完成图像的像素点位置置乱。

# 3 图像像素扩散

图像像素点置乱通过移动图像中像素点的位置，从视觉上掩盖原图像内容，但像素点的灰度值没有改变，加密后图像和原图像的灰度统计直方图一致，存在安全隐患。有必要通过像素扩散隐藏图像的统计直方图特性，即在不改变像素点位置的情况下，将任一像素点的信息隐藏在其他的密文像素点中。

# 3.1扩散密钥序列生成

扩散密钥序列采用和置乱密钥相似的复合混沌序列产生方法。为了进一步增加密钥序列的无序程度，相对于置乱序列是使用Sine序列改变出现重复数值的Logistic序列中部分位置的排列次序，扩散序列是使用Sine序列改变整个Logistic序列的排列次序，步骤如下：

a）产生长度与图像大小 $\mathbf { M } { \times } \mathbf { N }$ 相同的一维Logistic 均匀混  
沌序列。b)产生长度为 $\mathbf { M } { \times } \mathbf { N }$ 的 Sine 混沌序列，序列的值为[-1,1]。c）将Sine 混沌序列的元素按照升序排列，并用一维数组  
A 记录新序列中每个元素在原Sine序列中的位置。d）用Sine 混沌序列重新排列Logistic序列，即将Logistic  
序列按照一维数组A的值重新排列，得到像素扩散所用的复合

混沌序列S。

# 3.2基于双向循环异或运算的像素扩散

在扩散密钥序列生成后，用双向循环异或运算进行像素扩散，即对图像每一像素进行正向循环和逆向循环共两次异或运算，将明文图像中某一点像素的信息扩散到整个密文像素中[15]

像素扩散的过程：先将大小为 $\mathbf { M } { \times } \mathbf { N }$ 的灰度图像 $I _ { M \times N }$ ，转为成长度为 $\mathbf { M } { \times } \mathbf { N }$ 的一维向量 $P$ ，其值与3.1节产生的长度为$\mathbf { M } { \times } \mathbf { N }$ 的密钥序列S一一对应，再依次进行正向和逆向异或运算两次循环，得到以一维向量表示的密文 $c$ 。其中，正向（即i从1到MN）循环的异或运算如式（4）所示，对应的解密逆运算如式（5）所示。

$$
\begin{array} { c } { { C _ { i } = C _ { i - 1 } \oplus S _ { i } \oplus P _ { i } } } \\ { { P _ { i } = C _ { i - 1 } \oplus C _ { i } \oplus S _ { i } } } \end{array}
$$

如式（4）所示，进行正向循环后， $P _ { 1 }$ 像素点的信息可以扩散到全部密文像素点的信息中，但 $P _ { 2 }$ 像素点的信息只能扩散到$C _ { _ 2 } { \sim } C _ { _ { M N } }$ ，即明文像素点 $P _ { i }$ 的信息只能扩散在 $C _ { i } { \sim } C _ { M N }$ 中，扩散的效果不佳。因此，需要按逆向（即i从MN到1）循环一次，即按照式（6）循环。其对应的解密的逆运算如式（7）所示。

$$
\begin{array} { l } { { C _ { i } = C _ { i + 1 } \oplus S _ { i } \oplus P _ { i } } } \\ { { P _ { i } = C _ { i + 1 } \oplus C _ { i } \oplus S _ { i } } } \end{array}
$$

# 4 加密解密过程

当混沌系统由两个以上混沌序列组成时，其非线性行为更加复杂和难以预测[16]。本文的密钥序列由均匀分布Logistic 混沌和Sine 混沌组成，密钥序列的生成方法如第3节所述，其参数为 $[ \mu , x _ { 1 } ( 0 ) , \alpha , x _ { 2 } ( 0 ) ]$ ,其中 $\mu$ 为Logistic 混沌 Lyapunov 指数,$x _ { 1 } ( 0 )$ 为初值； $a$ 为 Sine 函数系数， $x _ { 2 } ( 0 )$ 为初值，加密与解密过程如下：

# 4.1加密过程

加密过程包括像素位置置乱和灰度值扩散两步。首先，产生均匀分布Logistic 混沌序列并整数化，用Sine 混沌序列改变其部分序列的排列产生无重复数值的混沌序列，以此序列对图像进行像素点位置置乱。之后，用同样的密钥参数产生均匀分布Logistic 混沌序列，用Sine 混沌序列改变整个Logistic序列的排列，以此序列和置乱后图像进行正向和逆向扩散运算，完成像素灰度值扩散，实现图像加密。

# 4.2解密过程

图像的解密过程是加密的逆过程，解密密钥的参数与加密密钥参数 $[ \mu _ { 1 , } x _ { 1 } ( 0 ) , \mu _ { 2 , } x _ { 2 } ( 0 ) ]$ 相同。解密过程是先进行像素灰度值扩散解密，后进行像素点位置置乱解密，完成从密文中恢复图像。

# 5 实验与结果

选择Cameraman、Lena、Peppers灰度图像作为测试图像进行加密和解密实验。实验采用Logistic和Sine 混沌的系统参数和初值 $[ \mu _ { 1 , } x _ { 1 } ( 0 ) , \mu _ { 2 , } x _ { 2 } ( 0 ) ]$ 作为密钥，取值为[3.9997,

0.512,4.0,0.88]。使用计算机为i5CPU，软件是MATLAB2014。实验中，加密过程用时平均为0.153s，解密过程用时平均为0.151秒，实验的视觉效果如图3所示。

图3中，（a）列从上到下依次为Cameraman明文图像、灰度直方图与幅度谱，Lena明文图像、灰度直方图与幅度谱，Peppers明文图像、灰度直方图与幅度谱；（b）列从上到下依次为Cameraman 密文图像、灰度直方图与幅度谱，Lena 密文图像、灰度直方图与幅度谱，Peppers 密文图像、灰度直方图与幅度谱；（c）列从上到下依次为解密Cameraman 图像、灰度直方图与幅度谱，解密Lena图像、灰度直方图与幅度谱，解密Peppers图像、灰度直方图与幅度谱。

从图3的明文、密文和解密后图像可以看出，密文图像的灰度统计直方图基本呈均匀分布，且密文图像灰度值的幅度谱也很平坦，即密文图像的像素值在[0,255]的灰度取值范围内出现的概率几乎均等。

# 6 算法安全性分析

# 6.1 密钥空间分析

密钥空间是衡量密码系统安全性的一个重要指标。密钥空间越大，抵御穷举攻击的能力越强。本文以Logistic系统参数μ，初值α和Sine 混沌映射参数 $[ \mu , x _ { 1 } ( 0 ) , \alpha , x _ { 2 } ( 0 ) ]$ 作为密钥。在32bit计算机中，依IEEE754标准规定表示双精度浮点数的长度是64bit，则密钥空间为 $2 ^ { 6 4 } \times 2 ^ { 6 4 } \times 2 ^ { 6 4 } \times 2 ^ { 6 4 } = 2 ^ { 2 5 6 }$ 。从安全的角度，密钥空间 ${ \geq } 2 ^ { 1 0 0 } { \approx } 1 0 ^ { 3 0 }$ 就能满足较高的安全级别，所以本算法的密钥空间对穷举攻击是安全的。

# 6.2 密钥敏感性分析

密钥敏感性是指在加密过程中对密钥进行微小变化（如$\pm 1 0 ^ { - 1 0 }$ ），能产生与原始密文完全不同的加密密文；同理，在解密过程中，对原始解密密钥进行微小变化（如 $\pm 1 0 ^ { - 1 0 }$ ），对同一密文能产生完全不同的解密结果[17][18]。

为了评估分析密钥敏感性，对某个密钥作微小的改变，计算通过加密算法得到的对应密文图像的变化率。常用像素数目变化率NPCR（NumberofPixelsChangeRate）与像素强度变化强度UACI（Unified Average Changing Intensity）测量，其定义分别为

$$
N P C R = \frac { \displaystyle \sum _ { i , j } D i f ( I _ { 1 } , I _ { 2 } ) } { \displaystyle M \times N } { \times 1 0 0 \% }
$$

$$
U A C I = \frac { 1 } { M \times N } \Bigg [ \sum _ { i , j } \frac { \big | I _ { 1 } ( i , j ) - I _ { 2 } ( i , j ) \big | } { 2 5 5 } \Bigg ] \times 1 0 0 \%
$$

其中： $I _ { 1 }$ 是原始密钥加密后的图像， $I _ { \ O _ { 2 } }$ 是密钥有微小改变后的加密图像； $D i f ( I _ { 1 } , I _ { 2 } )$ 表示图像 $I _ { 1 }$ 和 $I _ { \ O _ { 2 } }$ 不同像素的个数，其取值是：若 $I _ { 1 } ( i , j ) \neq I _ { 2 } ( i , j )$ ，则 $D i f ( I _ { 1 } , I _ { 2 } ) = 1$ ，若 $I _ { 1 } ( i , j ) \neq I _ { 2 } ( i , j )$ ，则 $D i f ( I _ { 1 } , I _ { 2 } ) = 0$ ；M、N分别为图像 $I _ { 1 }$ 和 $I _ { \mathrm { 2 } }$ 的长、宽。测试图像Cameraman为8位灰度图像，其理论值为： $\mathrm { N P C R } { = } 9 9 . 6 0 9 4 \%$ ，$\mathrm { U A C I } { = } 3 3 . 4 6 3 5 \%$ 。

![](images/46b6260fdd435ef87724e64b477df9c5d1d564a075c53eca2c6fa8dae1cfed9e.jpg)  
图3加密与解密视觉效果图

实验中，对图像Cameraman在加密过程的加密密钥做微小变化，使密钥中的混沌系统初值每次增加 $1 0 ^ { - 1 0 }$ （表1中用 $\Delta$ 表示），测定利用微小变化后的密钥加密生成的密文与原始密文之间的NPCR与UACI值，结果如表1所示。

表1加密密钥敏感性测定表  

<html><body><table><tr><td>△μ</td><td>△x(0)</td><td>△a</td><td>△x(0)</td><td>NPCR</td><td>UACI</td></tr><tr><td>1</td><td>-</td><td></td><td></td><td>99.501%</td><td>33.107%</td></tr><tr><td>2</td><td>-</td><td></td><td></td><td>99.572%</td><td>33.116%</td></tr><tr><td></td><td>1</td><td></td><td></td><td>99.207%</td><td>33.075%</td></tr><tr><td></td><td>2</td><td></td><td></td><td>99.396%</td><td>33.125%</td></tr><tr><td>-</td><td></td><td>1</td><td></td><td>99.402%</td><td>33.013%</td></tr><tr><td></td><td>-</td><td>2</td><td>-</td><td>99.510%</td><td>33.035%</td></tr><tr><td></td><td></td><td>-</td><td>1</td><td>99.115%</td><td>33.023%</td></tr><tr><td></td><td></td><td></td><td>2</td><td>99.227%</td><td>33.031%</td></tr></table></body></html>

表1中，测得的NPCR与UACI值与理想值很接近，说明当密钥发生微小变化时，密文图像中 $9 9 \%$ 以上的像素会发生改变，攻击者很难用穷举法进行分析。本文的解密过程与加密密过程是对称的，因此对解密密钥可得出相同的结论，即本文方法的密钥敏感性很强。

# 6.3 差分攻击分析

差分攻击是一种选择明文攻击，攻击者通过对明文进行微小的改变，分析经过相同加密系统后对应密文之间的差别进行攻击。加密系统抵抗差分攻击的能力可通过NPCR和UACI两个指标衡量[10,19]。实验采用Cameraman，Lena 和Peppers 灰度图像，步骤如下：

a)对于明文图像I,使用加密系统得到对应的密文图像Ei。b)从图像I中随机选择一个像素点，改变其灰度值，变化量为1，用同样的密钥和加密系统得到的密文图像记为 $\mathrm { E } _ { 2 }$ 。c)对密文Ei和E2，计算NPCR和UACI。d)重复步骤b）c)共100 次，得到NPCR 和UACI的平均值。表2是实验得到的NPCR和UACI平均值，数值接近理论值，加密算法具有较好的抵抗差分攻击的能力。

表2差分攻击分析的NPCR和UACI平均值表  

<html><body><table><tr><td>指标</td><td>Cameraman</td><td>Lena</td><td>Peppers</td></tr><tr><td>NPCR</td><td>99.59</td><td>99.60</td><td>99.59</td></tr><tr><td>UACI</td><td>33.45</td><td>33.44</td><td>33.45</td></tr></table></body></html>

# 6.4统计分析

对加密算法进行统计分析的目的是测定算法在置乱和扩散性能方面抵御统计攻击的能力，本文通过分析图像的灰度统计直方图、相邻像素相关性和信息熵实现。

# 6.4.1灰度统计直方图

图像的灰度统计直方图通过统计图像中每个灰度级出现的像素次数，表征图像像素的分布特性。加密前后明文图像和密文图像的灰度统计直方图如图3所示。从图中可以看出，密文图像直方图是均匀分布的，攻击者几乎无法从统计直方图中分

析出统计特性。

# 6.4.2相邻像素相关性分析

图像由像素组成，相邻的像素之间由于色彩、明暗的过渡存在一定的关联性。灰度图像可以看成由不同像素的灰度值构成的矩阵，由于相邻像素点之间存在关联性，许多相邻像素的灰度值差值较小。为了提高加密图像的保密性，必须降低密文图像相邻像素之间的相关性[20]。相邻像素相关性系数 $\rho _ { x y }$ 的定义如下[20]:

$$
p _ { x y } = { \frac { \mathrm { c o v } ( x , y ) } { { \sqrt { D ( x ) } } { \sqrt { D ( y ) } } } }
$$

其中： $x$ 和 $y$ 表示图像中两个相邻像素的灰度值大小， $\mathrm { c o v } ( \mathrm { x } , \mathrm { y } )$ 为这两个像素灰度值 $x$ 和 $y$ 的协方差， $\mathrm { D } ( \mathbf { x } )$ 和 $\mathrm { { D ( y ) } }$ 分别为 $x$ 和$y$ 的方差，其计算公式如下：

$$
E ( x ) = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } x _ { i }
$$

$$
D ( x ) = \frac { 1 } { N } { \sum _ { i = 1 } ^ { N } ( x _ { i } - E ( x ) ) ^ { 2 } }
$$

$$
\operatorname { c o v } ( x , y ) = { \frac { 1 } { N } } \sum _ { i = 1 } ^ { N } ( x _ { i } - E ( x ) ) ( y _ { i } - E ( y ) )
$$

由上述定义式可以看出，相邻像素间的相关性越强，相关性系数 $\rho _ { x y }$ 越大。

在Cameraman明文图像和密文图像中分别随机选取 $10 \%$ 数量的像素点，取其在水平、垂直、对角线方向的相邻像素的灰度分布情况如图4所示。

![](images/3950d221b5c6f13197a76df944c2525c4814c0778006b229edc862d6f0db01ec.jpg)  
  
图4Cameraman图像明文、密文在不同方向上的相邻像素分布

图4中,明文在三个方向上相邻像素的灰度值几乎集中分布在一条直线上，说明相邻位置上每个像素对的灰度值差别不大，相关性强；密文在上述方向上的相邻像素对的灰度值平均分布在整个灰度值范围，接近不相关。因此本文算法能破坏图像相邻像素间的相关性，使密文像素的灰度值在图像平面的分布接近随机，攻击者很难用统计攻击法破解。

表3是本文方法图像相邻像素间的平均相关系数的比较。从表2可以看出，密文图像相邻像素的平均相关系数较明文图像前明显减小，接近于0。

表3明文和密文相邻像素间的平均相关系数  

<html><body><table><tr><td colspan="3">Cameraman</td><td colspan="2">Lena</td><td colspan="2">Peppers</td></tr><tr><td></td><td>明文</td><td>密文</td><td>明文</td><td>密文</td><td>明文</td><td>密文</td></tr><tr><td>水平方向</td><td>0.9606</td><td>-0.0011</td><td>0.9774</td><td>0.0012</td><td>0.9650</td><td>-0.0237</td></tr><tr><td>垂直方向</td><td>0.9322</td><td>-0.0050</td><td>0.9543</td><td>-0.0017</td><td>0.9634</td><td>0.0054</td></tr><tr><td>对角方向</td><td>0.9106</td><td>-0.0027</td><td>0.9304</td><td>-0.0028</td><td>0.9276</td><td>-0.0046</td></tr></table></body></html>

# 6.4.3信息熵

信息熵是度量信息不确定度的物理量，计算式如下：

$$
H ( X ) = - { \overset { 2 ^ { L } - 1 } { \sum _ { i = 0 } ^ { 2 ^ { L } } } } P ( X _ { i } ) \log _ { 2 } P ( X _ { i } )
$$

其中： $P ( X _ { i } )$ 是信号 $X _ { i }$ 出现的概率，L是每个信号的比特数，对于图像则表示灰度图像的灰度等级数。信息的不确定性越大，熵值也越大。

实验对Cameraman 图像进行，该图像是 $_ { \mathrm { L = 8 } }$ 的的灰度图像，有256级灰度，信息熵的最大值为8。计算本文方法加密后的Cameraman图像信息熵为7.9895，接近信息熵的最大值，说明加密后的图像信息不确定度很大，能够抵抗熵分析。

# 7 结束语

本文提出一种新的复合混沌序列的产生方法，并通过像素位置置乱和灰度值扩散的双重加密步骤，实现图像加密。方法的主要特点有：

a）依据Sine混沌序列元素的排列次序改变均匀分布Logistic混沌序列的排列次序的方法，运算简洁。b)在位置置乱过程中，用Sine 混沌重排匀分布Logistic序列中部分重复元素的排列次序，生成无重复数值、且与被置乱图像像素位置一一对应的密钥序列，简化了后续置乱步骤。c)在像素值扩散中，用Sine 混沌重排全部均匀分布Logistic序列的排列次序，较部分打乱进一步提高了序列的无序程度，并通过正向、逆向循环异或操作完成像素扩散。本文加密方案的置乱和扩散过程都是在空间域进行，对原图像信息保存完整，经过实验验证，能有效抵抗穷举分析，差分分析和统计分析等类型的攻击。

# 参考文献：

[1]Pareek NK,Patidar V, Sud KK.Image encryption using chaotic logistic map[J].Image and Vision Computing,2006,24(9): 926-934.

[2]Li Chengqing,Tao Xie,QiLiu,Cheng Ge.Cryptanalyzing image encryption using chaotic logistic map[J].Nonlinear Dynamics,2014,78(2): 1545-1551.

[3]Gao Tiegang,Chen Zengqiang.A new image encryption algorithm based on hyper-chaos [J].Physics Letters A,2008,372 (4):394-400.

[4] 张雪锋，范九伦．一种改进的基于混沌系统的数字图像加密算法[J]. 计算机应 用研究，2007,24(4):184-186.(Zhang Xuefeng,Fan Jiulun. Extended image encryption algorithm based on chaos system [J]. Application Research of Computers,2007,24 (4): 184-186. )

[5]胡春强，邓绍江，秦明甫，等．基于Logistic 与标准映射的数字图像加 密算法[J].计算机科学,2010,37(12):57-59.(Hu Chunqiang,Deng Shaojiang, Qin Mingfu,elat. Image encryption algorithm based on logistic and standard map [J]. Computer Science,2010,37(12): 57-59.) [6] 舒永录，张玉书，肖迪，等．基于置乱扩散同步实现的图像加密算法 [J].兰州大学学报：自科版,2012,48(2):113-116.(Shu Yonglu, Zhang Yushu,Xiao Di,et al. Image encryption algorithm based on the synchronizationof permutation and diffusion. Journal of Lanzhou University: NaturaSciences,2012,48 (2):-116.) [7]朱从旭，胡玉平，孙克辉．基于超混沌系统和密文交错扩散的图像加密 新算法[J].电子与信息学报,2012,34(7):1735-1743.(Zhu Congxu,Hu Yuping,Sun Kehui.New image encryption algorithm based on hyperchaotic systemand ciphertext diffusion in crisscross pattern [J].Journal of Electronics & Information Technology2012,34(7):1735-1743.) [8]Ye Guodong,Huang Xiaoling.An efficient symmetric image encryption algorithm based on an intertwining logistic map [J]. Neurocomputing,2017,   
251: 45-53. [9]Huang Huiqing, Yang Shouzhi, Colour image encryption based on logistic mapping and double random-phase encoding [J]. Iet Image Processing,2017,   
11 (4): 211-216. [10] Slimane NB,Bouallgue K, Machhout M. Designing a multi-scroll haotic system by operating Logistic map with fractal process [J].Nonlinear Dynamics,2017,88 (3): 1655-1675. [11] Zhou Yicong,Bao Long,Chen C.L.Philip.A new 1D chaotic system for image encryption [J]. Signal Processing,2014,97: 172-182. [12]曹光辉，胡凯，佟维．基于Logistic均匀分布图像置乱方法[J].物理学 报,2011,60(11):133-140.(Cao Guanghui,Hu Kai,Tong Wei.Image scrambling based on Logistic uniform distribution [J].Acta Physica Sinica,   
2011, 60 (11): 133-140.) [13]盛利元，肖燕予，盛喆．将混沌序列变换成均匀伪随机序列的普适算法 [J].物理学报,2008,57(7): 4007-4012.(Sheng Liyuan, Xiao Yanyu,Sheng Zhe.A universal algorithm for transforming chaotic sequences into uniform pseudo-random sequences [J].Acta Physica Sinica,2008,57 (7): 4007-   
4012.) [14]李佩玥，石俊霞，郭嘉亮，等．一种混沌伪随机序列均匀化普适算法的 改进[J].电子学报,2015,43(4):753-759.(LiPeiyue,Shi Junxia,Guo Jialiang,elat. Improvement ofa Universal Algorithm for Uniformization of Chaotic Pseudo-Random Sequences [J].Acta Electronica Sinica,2015,43

# (4):753-759.)

[15]张勇，混沌数字图像加密[M].北京：清华大学出版社，2016:59-60.(Zhang Yong,Chaotic Digital Image Cryptosystem [M],Bei Jing: TsinghuaUniversity Press,2016: 59-60.)

[16]蒋君莉，张雪锋．基于多混沌系统的彩色图像加密方法[J].计算机应 用研究，2014,31(10):3131-3136.(Jiang Junli,Zhang Xuefeng.Color image encryption method based on chaotic systems [J].Application Research ofComputers,2014,31(10): 3131-3136.)

[17]罗玉玲，杜明辉．基于量子Logistic 映射的小波域图像加密算法[J] 华南理工大学学报：自然科学版,2013,41(6):53-62.(Luo Yuling,Du Minghui.Image encryption algorithm based on quantum logistic map in

wavelet domain [J]. Journal of South China University of Technology: Natural Science Edition,2013,41(6):53-62.)   
[18]Behnia S,Akhshani A,Ahadpour S,etal.A fast chaotic encryption scheme based on piecewise nonlinear chaotic maps [J].Physics Letters A,2oo7,366: 391-396.   
[19]Xu Lu,Li Zhi,Li Jian,Hua Wei.A novel bit-level image encryption algorithm based on chaotic maps[J].Optics and Lasers in Engineering,2016, 78 (21): 17-25.   
[20]Mohamad Javad Rostam,Abbas Shahba,Saeid Saryazdi,et al.A novel parallel image encryption with chaotic windows based on logistic map [J]. Computers and Electrical Engineering,2017,62:384-400.