# 一种基于超混沌的图像零水印算法

张海涛，张思博，

(辽宁工程技术大学 软件学院，辽宁 葫芦岛 125105)

摘要：超混沌系统有着密钥空间大、初值敏感的特性，又对其公式进行了改进，具有一定的优越性。针对已有的零水印算法鲁棒性差、安全性低的问题进行了研究，提出了一种基于超混沌的图像零水印算法，首先利用Chen 三维超混沌系统对水印信息进行加密预处理，通过解析各个位平面在分解后对图像的影响，将载体图像中的最低有效位初始化为零；采用块均值二值量化的方法进行特性提取；最后通过对加密水印与Anorld置乱后的特征矩阵进行异或处理得到零水印。仿真攻击实验及与以往零水印算法对比表明，该算法在保持鲁棒性良好的同时，能够抵御噪声攻击、滤波攻击、压缩攻击、剪切攻击等多种攻击。

关键词：超混沌加密；Chen混沌系统；鲁棒性；零水印 中图分类号：TP309.2 doi: 10.3969/j.issn.1001-3695.2018.07.0437

# Research on zero watermaking algorithm for hyper-chaos-based image

Zhang Haitao, Zhang Sibo (Collegeof SoftwareLiaoning Technical University,Huludao 1251o5,China)

Abstract: Hyperchaotic system has certainadvantages becauseof itscharacteristics of sercret key space and sensitivity to initial value.Aimingatthe lowcomputation efficiencyandpoor securityof theexisting Zero watermarking algorithm,this paper proposed a zero watermark algorithm based on hyperchaoticsystem.Firstly thealgorthm realizes theencryption pretreatmentof watermarking information taking advantageof thelarge keyspace and sensitivityof initialvalueofthe Chen hyper-chaos system.Andthen analyzing theinfluenceofeach bit planeon theimage,least significant bitofthe imagecarrier is initialized tozeros toextract thefeature matrixusingofblock meanbinaryquantization method.Finally,Armoldscrambled characteristics matrix and hyper-chaotic encrypted binary watermarking are executed for xor operation to construct a zero watermarking.The simulation atack experiment and comparison with the precious zero watermark algorithm show that the algorithm in this papercanresist noiseattck,filterattck,compresson attack and shear attck while maintainingbetter robustness.

Key Words:hyper-chaos encryption; Chen system; robustness; zero watermarking

# 0 引言

随着互联网和信息多媒体技术的迅速发展，人们的生活变得更加快捷，人们可以通过QQ、微博同其他人进行信息的交流，各种图片、视频在互联网上不断被观看和传递，在这个信息爆炸的时代，科技作为一把双刃剑在带给人们生活便利的同时，也存在着巨大的隐患，一些不法分子通过对互联网上的信息例如图片、视频进行盗窃、窜改、传播来为自己牟取利益，这些行为轻则损害版权使用者的合法利益，重则给社会给国家造成不可挽回的损失，在网络传输中有一系列的不确定因素，例如噪声的干扰、图像失真、丢失传输包等，这些都会造成接受方无法确定收到的数据的真实性以及完整性，所以，数字图像版权的保护问题显得格外重要[1-2]。

1989年，混沌映射产生密码序列的思想被Matthews首次提出[3],混沌动力系统对初始条件非常敏感，不同的初始条件，通过复杂的混沌动力学行为，会产生截然不同的混沌序列。混沌系统有确定的公式，但是初始值细微的变化会导致混沌序列的不同走向，在这种看似确定实为随机的动力学行为下，难以预测的混沌加密序列又给算法增添了一种保障。混沌系统随着维度的增加，其动力学行为会更加复杂，更难以预测，Chen 混沌系统是经典的三维混沌系统，它具有系统结构复杂、产生的序列多、且随机性更强，方便设计加密系统，它多参数、多初值的特点又使整个加密系统多了密钥空间大的优点[4-6]。通过混沌系统所产生的混沌序列对水印加密，会提高水印的鲁棒性、安

全性。

现阶段，利用混沌对水印加密的算法有很多，兀旦晖,郑恩让等人在针对图像水印鲁棒性的问题上，提出了一种基于混沌映射logistic和Arnold二次加密的图像水印的算法研究[；季诺然,吕晓琪等人针对现行数字水印算法中抗几何攻击能力弱以及嵌入水印信息容量差的问题,提出一种Contourlet变换下QR 码与混沌加密相结合的彩色图像水印算法[8]；曲长波、于智龙等人结合二维混沌系统、SVD和位平面技术共同构造零水印信息，提出了一种基于脊波变换域的鲁棒零水印算法[9；曲长波、吴德阳等人利用Arnold置乱和特征矩阵构造零水印信息，提出了一种基于Curvelet-DSVD和视觉密码相结合的强鲁棒零水印算法[10]。以上几种算法均采取的是利用低维混沌映射去对水印图像进行加密，水印图像的鲁棒性以及安全性都得到了提高，本文将chen经典三位混沌系统进行降维为一维混沌系统，利用其产生的混沌序列对水印图像进行加密，在对各个平面分解之后对于图像影响的解析，找到载体图像的最低有效位，并将其初始化为零，采用块均值量化的方法对其进行特征提取，把特征矩阵进行Armold变换后与加密水印退休那个异或得到零水印，通过一系列的仿真实验可以得到，本文算法的拥有良好的鲁棒性，以及能够抵御噪声攻击、剪切攻击、滤波攻击以及压缩攻击等多种攻击。

# 1 本文算法

# 1.1水印的预处理

由于考虑到一维的混沌映射的动力学行为相比较于高维混沌系统而言较为简单，本文算则利用Chen 经典三维混沌系统对本文图像水印进行加密处理，以往的研究表明，Chen混沌系统是一个非常容易用电路实现的三阶系统，可用于实现更高安全性的加密系统[4-6]。

本身chen混沌系统对于初始值的微小改动是十分敏感的，通过式（2）的降维模型将其降为一维后，其中H，C值的作用是用来放大混沌系统对于初始值的敏感性的，这会使新的一维混沌系统比Chen混沌系统本身对初始值的改动更具敏感性，Chen混沌系统的动力学方程可描述如下：

$$
\left\{ { \begin{array} { l } { d x / d t = a ( y - x ) } \\ { d y / d t = ( c - a ) x - x z + c y } \\ { d z / d t = x y - b z } \end{array} } \right.
$$

将上式混沌系统按照下式降为一维混沌映射：

$$
L _ { k } = f l o o r ( H \sqrt { x _ { k } y _ { k } + y _ { k } z _ { k } + x _ { k } z _ { k } } + C )
$$

$$
\mathbf { k } { = } 0 , 1 , 2 , \ldots { \ldots } , \mathbf { N } { \times } \mathbf { N }
$$

其中:Xk，yk， $\mathbf { z } _ { \mathrm { k } }$ 是chen 混沌系统的三个状态变量在第k时刻的值，H，C为控制参数，混沌系统对于初始值是具有敏感性的，文本想要将chen 混沌系统降为一维，就是想让这个改造后的一维混沌映射的敏感性更强，因此在式（2）中的因子H是用来大幅度地放大这种敏感性，而因子L是用来小幅度地放大这种敏感性。

本算法选择大小为 $\mathbf { N } \times \mathbf { N }$ 的二值水印图像 $W ( i , j )$ ，其中$0 < i \leq N$ ， $0 < j \leq N$ 。初始值为 $\mathbf { X } 0$ 、 $\mathbf { y } _ { 0 }$ 和 $\mathbf { z } _ { 0 }$ ，这三个初始值将作为密钥K1保存起来。以三个初始值为起点，在chen 混沌系统的迭代作用下产生三组混沌序列 $\mathbf { x } ( \mathbf { k } )$ 、y(k)和 $\mathbf { \boldsymbol { z } } ( \mathbf { \boldsymbol { k } } )$ ，其中$k = 1 , 2 . . . N \times N$ 。将三维混沌序列进行降维处理，为保证降维后的序列具有更好的超混沌特性和良好的扩散均匀度[1I]，选取式（2）的参数降维模型。

设所选参数 $N = 2 5 6$ ，经过降维公式(2)处理后的超混沌序列如图1所示。

![](images/cb94d8bb997fedb583073dec537a325e4b1d33af122af2cbb43305c2e44567b6.jpg)  
图1三维超混沌序列经降维后的序列

本文选取的实验对象为二值图像，一组混沌序列无法满足对二维图像加密，所以首先要对L(k)序列进行升维为二维矩阵LL(k)，通过式(3)(4)最终得到加密后的水印图像。

$$
J ( i , j ) = \left\{ \begin{array} { l l } { 1 } & { \ L L ( i , j ) > m l } \\ { 0 } & { \ L L ( i , j ) < = m l } \end{array} \right. \ m l = m e a n ( L L )
$$

$$
C ( i , j ) = W ( i , j ) \oplus J ( i , j )
$$

其中： $\mathrm { m l }$ 为升维后的二维矩阵的均值，当二位矩阵中的点的值大于均值ml时,矩阵 $\mathrm { J ( i , j ) }$ 赋值为1，反之，赋值为0，经过二值量化处理后，得到矩阵 $\mathrm { J ( i , j ) }$ 。由公式(4)将矩阵J(i,j)与而至水印图像进行异或处理后得到加密后的二维水印数组 $\mathbf { C } ( \mathrm { i , j } )$ 。

![](images/9ccdbda123cf3b39493ff7039a22cf608e31353af4b1355e047242175a677426.jpg)  
图2为水印加密预处理框图。  
图2水印加密预处理框图

# 1.2特征矩阵的提取以及零水印的构造

图像特征提取是构造零水印的重要的一环，它决定着算法的鲁棒性的算法的好坏，本文将 $2 5 6 \times 2 5 6$ 的Lena灰度图像按照式(5)进行位平面分解，如图3(a)\~(i)所示。

$$
S _ { \mathrm { k } } ( i , j ) = B _ { k } ( S ( i , j ) ) = \left\{ \begin{array} { l l } { 1 , \mathrm { m o d } ( f l o o r ( S ( i , j ) / 2 ^ { k - 1 } ) , 2 ) = 1 } \\ { ~ ( 0 , \mathrm { m o d } ( f l o o r ( S ( i , j ) / 2 ^ { k - 1 } ) , 2 ) = 0 } \end{array} \right.
$$

![](images/90ad95f574bc7118914cf2aa8cf2f7cf05d4fc38b3fecaeb1fcc330d6158511a.jpg)  
图3Lena图像的位平面分解图  
图5原始载体图像和水印图像

由图3可以看出，Lena灰度图像位平面分解的各个层面中，MSB层的轮廓最为清晰，随后是第六层和第七层，随着平面位的下降，像素逐渐变得不规则，在后面的几幅图像中可以直观地看到像素的分布毫无规律可循，这是因为图像的可视性权重的大小是由位平面的高低决定的，可视性会随着为平面的升高而占比增加，图像所包含的信息量也会随着增加[12]。

通过对图3(a)\~(i)的分析，可以发现LSB作为最低有效位，它包含的信息量非常少，类似一些随机的信号，为了改善原始图像的纹理信息丢失情况，本文算法对LSB进行了初始化为零的操作。如图3(j)为Lena灰度图像LSB层初始化为零之后的图像，通过计算，图3(j)的PSNR的值为51.12dB,明显要大于35dB,故可判断其与原始图像的差异是微小的，提取过程中纹理信息的丢失是较小的，特征矩阵的提取以及零水印的构造的流程图如图4所示。

![](images/0c9cd2050233f0b3d018d275dc570e6941946d38f2932ddeae4e5a1edc8adab0.jpg)  
图4零水印构造流程图

本文算法选取 ${ \bf N } \times { \bf N }$ 的原始图像I作为水印嵌入载体，具体构造零水印的步骤如下：

a)通过对原始载体图像I的最低有效位初始化为零，得到I_LSo。

b)对所得到的图像I_LSo做分块处理，大小为 $\mathbf { m } \times \mathbf { m } .$ 用 $\mathbf { P } _ { \mathrm { k } }$ 标记每个子块，只是单纯的标号。

c)通过式(6)来计算每个子块的均值 $\mathrm { \Delta T _ { k } }$ 。

$$
T _ { \mathrm { k } } = \frac { 1 } { m ^ { 2 } } \sum _ { i = 1 } ^ { m } \sum _ { i = 1 } ^ { m } P _ { k } \left( i , j \right) \quad \quad i , j = 1 , 2 , . . . , m
$$

d)把每一个子块中的像素值与其所处子块做比较，构造一个大小为 ${ \bf N } \times { \bf N }$ 的矩阵 B,其中 $\mathbf { b } _ { \mathbf { k } }$ 为每块中每个像素点的像素值。

e)对矩阵B进行次数为K次的Arnold变换，得到置乱后的矩阵Bs.

f)将步骤e)中得到置乱矩阵 $\mathbf { B } _ { \mathrm { S } }$ 与加密后的水印序列C进行异或操作得到LSI序列，长度为 ${ \bf N } \times { \bf N } _ { \circ }$ （202

# 2 仿真实验以及安全性分析

在实验部分的所有实验均在MatlabR2010b的实验环境下进行，试验中所选取的原始图像为 $2 5 6 \times 2 5 6$ 的经典lena图像，水印信息采取二值图像版权保护四个字，实验中，在实验中的水印加密阶段，混沌系统初始值以及参数取 $\scriptstyle 1 0 = 0 . 1 2 3$ 、$\mathrm { y 0 = 0 } . 3 2 1$ 、 $z 0 { = } 0 . 2 3 1 , \mathrm { H } { = } 3 0$ 、 $\scriptstyle { \mathrm { C = 1 } . 2 7 }$ ,将以上数据作为密钥K1保存，Arnold置乱二值矩阵的次数为75，将此置乱次数作为密钥K2 进行保存，实验中所使用的原始图像与水印图像如图5所示，其中(a)为原始图像，(b)为水印图像。

版权保护(a)原始载体图像 (b)水印图像

# 2.1算法抵御攻击的性能分析

# 2.1.1压缩攻击和滤波攻击

压缩攻击和滤波攻击是最为常见的攻击方式，压缩图像是为了减少图像在传输的过程中由于数据量过大，会对信道产生过大的压力，从而影响传输的速率；滤波是给图像去噪的操作，主要是为了过滤图像中高频的成分，在这两个过程中都会损失图像的像素。在实验中，压缩攻击选取的是JEPG压缩，其中选取压缩质量因子60、70、80的三种情况，滤波的模板选择了$3 ^ { * } 3$ 和 $5 ^ { * } 5$ 两种对原始载体图像进行测试，采取NC值对前后水印的差距做出客观的评估，滤波攻击测试结果图如图6所示，压缩攻击测试结果图如图7所示，结果如表1所示。

版权保护(a)中值滤波3\*3版权保护(b)中值滤波 $5 ^ { * } 5$

版权 保护   
(a)JPEG压缩质量因子为80 版权 保护   
(b)JPEG压缩质量因子为70 版权 保护   
(c)JPEG压缩质量因子为60

如图6、7所示，随着滤波攻击模板的扩大，原始载体图像质量有所下降，但从水印图像来看并没有受到太大的影响，图片中的字样依旧清晰可见；压缩攻击方面，随着压缩质量因子的减小，原始载体图像和水印图像都收到了轻微的影响，但是这种影响在可以接受的范围内，所以，从实验效果图来看，本文算法对于滤波攻击和压缩攻击有一定程度的抵抗能力。

如表1所示，水印NC的值随着滤波模板的增大而减小，在两种模板中的测试值的值都在0.85之上，在压缩攻击方面，水印NC的值随着压缩因子的增大而增大，三次测试结果的值也在0.87之上，所以说，本文算法在受到一定程度的滤波攻击或者压缩攻击时仍能保持一种良好的鲁棒性。

表1攻击后得到的水印NC 值  

<html><body><table><tr><td>攻击方式</td><td colspan="2">中值滤波</td><td colspan="2">JPEG 压缩</td></tr><tr><td>压缩质量因子与</td><td>3*3模板</td><td>5*5模板</td><td>质量因子60</td><td>质量因子70 质量因子80</td></tr><tr><td>滤波模板选择</td><td></td><td></td><td></td><td></td></tr><tr><td>NC值</td><td>0.8966</td><td>0.8502</td><td>0.8795</td><td>0.8894 0.9008</td></tr></table></body></html>

# 2.1.2噪声攻击

![](images/541ce2912ea47a8d4357ff0bbafb6d15689dcf0f2debd78274dd62873f2e532a.jpg)  
图6中值滤波载体图像和提取水印  
  
图7JPEG压缩载体图像和提取水印  
图8噪声攻击后载体图像  
图9噪声攻击后提取水印图像

噪声攻击是一种较为常见的图像攻击方式，图像在传输的过程中都会收到噪声的干扰，高斯噪声和椒盐噪声为两种非常普遍的噪声攻击，本次实验采用高斯噪声与椒盐噪声两种攻击方式和不同的强度对原始载体图像进行测试，如图8、9为高斯噪声和椒盐噪声攻击下的原始图像和提取水印图像。

版权 版权 保护 保护 (a)高斯噪声0.001 (b)高斯噪声0.002 版权 版权 保护 保护 (c)高斯噪声0.003 (d)椒盐噪声0.01 版权 版权 保护 保护 (e)椒盐噪声0.02 (f)椒盐噪声0.03

如图7、8所示，无论是高斯噪声还是椒盐噪声，随着噪声的增大，图片的质量变得越来越差，提取的水印图像的清晰度也逐渐降低，但是水印图像的基本轮廓大致都能看得出，其中的“版权保护”依然可以轻易分辨，所以，本算法能够抵御一定范围的高斯噪声和椒盐噪声。

表2噪声攻击后得到的水印 NC 值  

<html><body><table><tr><td>噪声攻击类型</td><td>攻击强度</td><td>NC值</td></tr><tr><td rowspan="3">高斯噪声</td><td>0.001</td><td>0.8508</td></tr><tr><td>0.002</td><td>0.7645</td></tr><tr><td>0.003</td><td>0.7388</td></tr><tr><td rowspan="3">椒盐噪声</td><td>0.01</td><td>0.9461</td></tr><tr><td>0.02</td><td>0.9157</td></tr><tr><td>0.03</td><td>0.8952</td></tr></table></body></html>

如表2所示，无论是高斯噪还是椒盐噪声，随着噪声强度的增大，NC值不断减小，当高斯噪声的噪声强度为0.003时，虽然NC值与椒盐噪声攻击的NC值差距较大，但是NC值仍能保持在0.73以上，当椒盐噪声的噪声强度为0.03时，NC值仍保持在0.89以上，所以，本文算法能够抵御一定程度的高斯噪声和椒盐噪声的攻击。

# 2.1.3 剪切攻击

剪切攻击是一种常见的攻击方式，与其他攻击方式比较来说更为直观，它是直接对图像进行任意规则的剪切，从而破坏掉图像信息，在这一部分的实验中，一共选取了图片左上角、图片中心、图片右下角三个剪切部位，每个部位分别采取了四种不同程度的剪切面积，图10、11分别为原始载体图像裁剪后的效果图以及水印提取的图像的效果图。

版权版权 版权版权 保护保护保护 (a)左上角剪切1/16 (b)左上角剪切1/8 (c)左上角剪切1/4

版权保护版权保护版权保护(d)左上角剪切1/2(e)中心剪切1/16(f)中心剪切1/8版权保护版权保护版权保护(i)右下角剪切1/16

![](images/469fe1cc9e70cbeb8bea066ce536d67d433877c487aaca0e2ee1a9f568835880.jpg)  
图10剪切攻击后的载体图像  
(g)中心剪切1/4  
(h)中心剪切1/2  
图11剪切攻击后提取的水印图像

版权版权版权 保护保护保护 (j)右下角剪切1/8 (k)右下角剪切1/4 (I)右下角剪切1/2

由图11可以看出剪切攻击无论是从左上角、中心还是右下角对图像进行攻击并没有什么太大的差别，但是无论是哪一个部位，随着剪切面积的增大，所提取的水印图像就变得越模糊，尤其是剪切面积从1/4变化到1/2的手，前后两张水印图像模糊程度差异较大，但是剪切面积最大为1/2的时候，所提取的水印图像仍能非常清楚的辨别图片中的字体，所以说，本文算法可以很好的抵御大强度的剪切攻击。除了效果图，还计算了每张提取的水印图像的NC值 如表3所示。

表3剪切攻击后得到的水印NC 值  

<html><body><table><tr><td>剪切位置</td><td>剪切尺寸</td><td>NC值</td></tr><tr><td rowspan="3">左上角</td><td>1/16</td><td>0.9982</td></tr><tr><td>1/8</td><td>0.9916</td></tr><tr><td>1/4</td><td>0.9679</td></tr><tr><td rowspan="5">中心</td><td>1/2</td><td>0.8743</td></tr><tr><td>1/16</td><td>0.9973</td></tr><tr><td>1/8</td><td>0.9911</td></tr><tr><td>1/4</td><td>0.9667</td></tr><tr><td>1/2</td><td>0.8686</td></tr><tr><td rowspan="4">右下角</td><td>1/16</td><td>0.9972</td></tr><tr><td>1/8</td><td>0.9909</td></tr><tr><td>1/4</td><td>0.9909</td></tr><tr><td>1/2</td><td>0.8642</td></tr></table></body></html>

由表3可以看出NC值和效果图的结果一致对应，NC 值随着剪切面积的增大而减小，最低时的NC值在0.86以上，这表明本文算法具有面对一定程度的剪切攻击，能够保持良好的鲁棒性。

# 2.1.4图像篡改攻击

在这一部分，主要测试本文算法对于篡改攻击的抵御效果，主要从内容删除、文本添加和拷贝粘贴三个方面进行，图12\~14分别为内容删除、文本添加、拷贝粘贴的实验效果图。

版权 保护 (a) (b)

版权 保护 (a) (b)

版权 保护 (a) (b)

如图12中，(a)为被内容删除攻击的原始载体图像，(b)是对图(a)的水印提取的效果图；如图13中，(a)为被添加文本攻击的原始载体图像，(b)是对(a)的水印提取的效果图；如图14中，(a)为被拷贝粘贴攻击的原始载体图像，(b)为对(a)的水印提取的效果图。

从上述几幅图象可以看出，本文算法对于内容删除、添加文本、拷贝粘贴攻击均具有良好的鲁棒性，在载体图像收到以上几种攻击之后，提取的水印图像仍然清晰可见，从客观评价的角度来说，表4给出了几种窜改攻击后的图像的PSNR值和NC值。

表4窜改图像PSNR值和提取水印NC值  

<html><body><table><tr><td>攻击类型</td><td>PSNR</td><td>NC</td></tr><tr><td>拷贝粘贴攻击</td><td>26.4652</td><td>0.9911</td></tr><tr><td>文本添加攻击</td><td>24.1951</td><td>0.9864</td></tr><tr><td>内容删除攻击</td><td>26.4821</td><td>0.9833</td></tr></table></body></html>

![](images/63bbc97875d5ed9c035a73cfe18ee4fb231663cdd3a5bb97b288682c663b332b.jpg)  
图12内容删除攻击

由表4可以看出在三种篡改攻击下的水印提取图像的NC值均在0.98之上，故本文算法在面对篡改攻击时具有极好的鲁棒性。

# 2.2水印加密安全性分析

在这一部分主要是对水印加密算法的安全性的测试，本文水印加密算法运用了Chen 混沌系统和Arnold变换对水印图像和特征矩阵进行加密和置乱，在整个加密过程中，共产生两个密钥分别为K1、K2，其中的值均为系统初始化的取值，想要提取水印图像必须依赖两个密钥，在这一部分载体图像选取Lena和Boat两幅二值图像作为载体图像进行测试，如图3.11为密钥不同时的水印提取效果。

![](images/afc066c07df9c9a9dbe43939cd88bca09e82a5b69cb56c83f331c293c2cea368.jpg)  
图13添加文本攻击

![](images/12160709fd791310d6af2e1c1881a701e34741f6e73c325983b2917ca0a7fefb.jpg)  
图14复制粘贴窜改攻击

时版权保护(a)原始载体图像lena(b)原始水印图像版权保护(b)提取的水印图像(K1、K2正确)

(d)仅K1错误(e)仅K2错误(f)原始载体图像Boat版权保护版权保护(g)原始水印图

![](images/f1369450677f7adc4cfbe736481ba9caa16ff5ae48f8097745c9c2f9e9954f97.jpg)

![](images/3b8f09e56220e8f51d67c9f341dd11c6984a8c70e4db3988ed6d609578d4949a.jpg)  
图15不同密钥下提取出的水印图像

(h)提取的水印图像(K1、K2 正确)

由图15可以看出，在密钥K1、K2中的任何一个出现错误时，提取的水印信息类似于随机噪声，不能对水印图像进行成功的提取，所以，在不得到密钥的情况下，是不可能对水印图像进行正确的提取。

# 2.3算法性能比较

在这一部分，测试本文算法与其他算法在鲁棒性上的对比效果，选取噪声攻击、剪切攻击、滤波攻击三种类型的攻击，并且采取不同的强度对算法的鲁棒性进行测试，如表5为测试结果。

表5算法鲁棒性评价(NC值)  

<html><body><table><tr><td>攻击类型</td><td>攻击强度</td><td>文献[13]</td><td>文献[14]</td><td>本文算法</td></tr><tr><td rowspan="3">高斯噪声</td><td>0.001</td><td>0.5022</td><td>0.5024</td><td>0.8058</td></tr><tr><td>0.002</td><td>0.5006</td><td>0.5017</td><td>0.7645</td></tr><tr><td>0.003</td><td>0.4964</td><td>0.4988</td><td>0.7388</td></tr><tr><td rowspan="2">中值滤波</td><td>3*3</td><td>0.6612</td><td>0.6209</td><td>0.8966</td></tr><tr><td>5*5</td><td>0.5927</td><td>0.5660</td><td>0.8502</td></tr><tr><td rowspan="2">剪切攻击</td><td>中心剪切1/16</td><td>0.9778</td><td>0.9967</td><td>0.9973</td></tr><tr><td>中心剪切1/4</td><td>0.9685</td><td>0.9790</td><td>0.9667</td></tr></table></body></html>

从表5可以看出，在抵御高斯噪声和中值滤波攻击的方面的能力,本算法要优于文献[13，14],在剪切攻击的方面，本算法要稍逊于文献[13，14],文献[11]在构造特征矩阵的方法是采用置乱图像的最低有效位，由于LSB 算法对于噪声攻击和几何攻击表现较为脆弱，在被攻击后所提取的水印图像和原始的水印图像存在差异性。文献[14]采用的不是零水印这种无损的嵌入方式，而是一种有损的嵌入方式，通过水印来代替载体图像的最低有效位，这样虽然可以获得一定的鲁棒性，但是会破坏载体图像。本文算法采取零水印这种无损的嵌入方式，不会使原始载体图像发生任何变化，在构造特征阶段采取LSB置零后分块像素值和块均值的大小关系，在受到攻击时，块均值不会有太大的变化，鲁棒性好，因此在与文献[13，14]比较下，本算法具有更好的水印提取效果。

# 3 结束语

本文提出了一种基于超混沌的图像零水印算法，采用零水印技术这种无损的方式，在不改变原始载体图像的情况下，提高了鲁棒性，在水印加密阶段采用Chen 高维混沌系统结合Arnold变换完成，提高了水印的安全性，通过一系列的攻击实验以及和其他算法的比较，可以得出，本文算法能够抵御噪声攻击、滤波攻击、压缩攻击等多种攻击，并且具有良好的水印提取效果。

# 参考文献：

[1]Seitz J.Digital watermarking for digital media [M].London: Information Science Publishing,2005:1-30.   
[2]Cox I, MillrM,Bloom J,et al.Digital Watermarking and Steganography [M].San Francisco,California:Morgan Kaufmann Publishers,2007: 15-56.   
[3]Matthews R A J. On the derivation of a chaotic encryption algo-rithm [J]. Cryptologia,1989,13(1):29-42.   
[4] Chen Guanrong,Dong Xiaoning.From Chaos to order methodologies, perspectives and applications [J].World Scientific,1998,24(16): 760.   
[5]Ueta T,Chen Guanrong.Bifurcation analysis of Chen's equation [J]. International Journal of Bifurcation and Chaos,2Ooo,10(8):1917-1931.   
[6]Yassen M T.Chaos control of Chen chaotic dynamical system [J].Chaos, Solitons &Fractals,2003,15(2):271-283.   
[7]兀旦晖，郑恩让．基于混沌Logistic 和Arnold二次加密的图像水印算法 研究[J].计算机测量与控制，2017，25(04):193-196.(Wu Danhui, Zheng Enrang.Research of encryption algorithm of image watermarking based on logistic and arnold of chaos [J]，Computer Measurement & Control,2017,25 (04): 193-196.)   
[8] 季诺然，吕晓琪，谷宇，等．基于QR码与混沌加密的Contourlet域彩色 图像盲水印算法 [J]．包装工程,2017,38(15):173-178.(Ji Nuoran,Lyu Xiaoqi,Gu Yu,et al.Blind watermarking algorithm for color image in contourlet domain based on QR code and chaotic encryption [J], Packaging Engineering,2017,38 (15):173-178)   
[9]曲长波，于智龙，李栋栋．基于分块 FRIT-SVD 的鲁棒零水印算法 [J]. 计算机工程与科学,2018,40 (06):1005-1016.(Qu Changbo,Yu Zhilong, Li Dongdong.A robust zero-watermarking algorithm based on the block FRIT-SVD[J]，Computer Engineering and Science，2018，40（06): 1005-1016)   
[10]曲长波，吴德阳．基于Curvelet-DSVD和视觉密码的强鲁棒零水印算法 [J/OL].计算机应用研究，2019,36(3）．[2018-09-13].http://kns.cnki. net/kcms/detail/51.1196.TP.20180209.115.064.html.(Qu Changbo WuDeyang. Strong robust zero-watermarking algorithm based on Curvelet-DSVD and visual cryptography [J]，Application Research of Computers，2019，36(3）．[2018-09-13].htp://kns.cnki. net/kcms/detail/51.1196.TP.20180209.1115.064. html.)   
[11]杨晋霞，鞠杰，邵峰．基于超混沌加密的半脆弱音频水印算法[J].计 算机应用与软件,2014,31(11):295-298.(YangJinxia,JuJie,Shao Feng. Semi-fragile audio watermarking algorithm based on hyper-chaos encryption [J]，Computer Applications and Software，2014,31(11): 295-298. )   
[12]姚雪．一种基于位平面和 HVS 的信息隐藏算法研究 [D].葫芦岛：辽 宁工程技术大学，2014.（Yao Xue.Research on information hiding algorithm based on bit-plane and HVS [D]. Huludao: Liaoning Technical University, 2014)   
[13]吴伟民，丁冉，林志毅，等．基于混沌的医学图像窜改定位零水印算法 [J].计算机应用研究,2014,31(12):3685-3688.(Wu Weimin,Ding Ran, Lin Zhiyi,etal. Chaos-based zero-bit watermarking scheme for medical image tamper location [J]，Application Research of Computers,2014,31 (12): 3685-3688. )   
[14] Sanjay R,Raman B.A chaotic system based fragile watermarking scheme for image tamper detection [J]. International Journal of Electronics and Communications,2011,65 (10): 840-847.