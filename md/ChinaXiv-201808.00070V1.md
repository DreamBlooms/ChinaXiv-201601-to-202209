# 一种基于密钥的受控最低有效位修改技术的稳健型量子水印算法\*

李涛la，程振文la，瞿治国 1b,2

(1.南京信息工程大学 a.电子与信息工程学院;b.计算机与软件学院，南京 210044;2.江苏省网络监控工程中心，南京 210044)

摘要：如何更好地保护量子图像的版权，是量子水印技术的一个重要研究课题。基于对数极坐标的量子图像表示，提出了一种新颖的量子水印算法。根据通信双方共享一组密钥的值，发送方选择量子载体图像像素灰度值的高四位中的某一位作为受控位；再根据所选受控位的值，发送方将水印信息嵌入到量子载体图像的最低有效位或次最低有效位上。这种基于密钥的受控最低有效位修改技术，提高了量子水印图像的透明性和稳健性。基于 MATLAB 的实验仿真和性能分析也表明新算法在透明性、稳健性和嵌入容量上有着良好的表现。

关键词：版权保护；量子水印技术；对数极坐标量子图像；最低有效位修改技术；透明性；稳健性；嵌入容量中图分类号：TP309.2 doi: 10.3969/j.issn.1001-3695.2018.05.0317

# Robust quantum watermarking algorithm based on key to implement controlled least significant qubit modification technique

Li Taola, Cheng Zhenwenlat, Qu Zhiguo1b, 2 (1.a.SchoolofElectronic&InformationEngineeing,b.SchoolofComputer&Software,Nanjing UniversityofInformation Science& Technology，Nanjing 210044，China;2.Jiangsu Engineering Centerof Network Monitoring,Nanjing 210044, China)

Abstract: How to beter protect thecopyright of quantum images is an important research subject in quantum watermarking technology. Basedon the representation of quantum log-polar images,this paper proposed a novel quantum watermarking algorithm.According to the valueofthe key shared bythe both communicating parties,the sender selected oneof the high four qubits ofthe pixel gray value ofquantumcarier image as thecontrolled qubit.And the watermarking information was embedded intothe least significant qubit or the peripheralleast significant qubit of quantum carrierimageonthebasis of the valueof theselectedcontrolled qubit.Utilizing the Keyto implement thecontrolled least significant qubit modification technique improved thetransparencyand robustness ofquantumwatermark image.Experimental simulationand performance analysis based on MATLAB showed that the new algorithm has a good performance on transparency,robustness and the embedding capacity.

Key words:copyright protection；quantum watermarking technology；quantum log-polar images；least significant qubit modification technique; transparency; robustness; embedding capacity

# 0 引言

作为一种崭新的计算模型，量子计算可以利用量子力学[1]的特殊性质，如叠加态和纠缠态来存储、处理和传输信息。近些年来，随着量子计算的快速发展和数字图像的广泛应用，为了满足采用量子态来存储数字图像的需求，多种量子图像表示模型被提出，如Qubit Lattice[2]、Entangled Image[3]、Real Ket[4]、

FRQI[5]、NEQR[6]、QUALPI[7]和NCQ[8]等。其中，QUALPI是基于对数极坐标的量子图像表示模型，具有旋转和缩放的不变性特点[9]。QUALPI 量子图像的三种变换，即对称变换、旋转变换和缩放变换，可以灵活快速地进行。

多种量子图像表示模型的提出，使得量子图像在通信网络中有着广阔的应用前景。基于不同量子图像表示模型的特点，量子图像隐写技术 $[ 1 0 ^ { - } 1 2 ]$ 和量子水印技术 $[ 1 3 ^ { \sim } 1 6 ]$ 也相应地被提出。相比于量子图像隐写技术侧重秘密信息在量子图像中的隐蔽性，量子水印技术则在量子图像的版权保护方面起到了至关重要的作用。量子水印技术是将标志信息（即量子水印）嵌入到量子载体（包括文本、图像、视频等）当中，既不影响量子载体的使用价值，也不轻易让非法第三方察觉到量子水印的存在。通过这些隐藏在量子载体中的水印信息，可以达到版权保护的目的。目前，量子水印技术取得的主要研究成果如下所述。

2013年，Zhang等人[13]提出了一种通用的量子水印算法，可以根据提取出的水印找出真正的水印嵌入者，而且任何非版权所有者都无法去除嵌入的水印。同一年，一种基于量子傅里叶变换（QFT）的量子水印算法也被 Zhang 等人[4]提出。该算法将量子水印图像的信息嵌入到量子载体图像的傅里叶系数中，利用傅里叶变换的性质，确保含水印的量子载体图像能够抵抗无法避免的噪声。2016年，运用经典的最低有效位（LSB[17]）修改技术的思想，Sang等人[15]首先给出了量子的最低有效位（LSQb）修改技术的思想，接着提出基于量子彩色图像表示模型（NCQI）的量子水印算法，使得该算法具有易操作和信息隐藏量大等优点。

透明性、稳健性以及嵌入容量是评估量子水印算法性能的三个重要指标。其中稳健性是评估量子水印算法的关键。任何一种量子水印算法的提出，只有经得住非法第三方各种攻击的考验才是安全的，一旦误用弱稳健性的量子水印算法，可能使合法的版权所有者的利益受到损失。若非法第三方试图删除或者破坏图像中存在的水印，则会导致载体图像存在严重失真，这种恶意攻击也使得非法第三方无法获取水印信息。若非法第三方采用扫描与复印、几何变换和噪声污染等攻击，不仅对载体图像造成的影响较小，而且非法第三方还会获取一部分水印信息。这种无意攻击通常是非法第三方采用的攻击手段。上述三种量子水印算法着重分析了扫描与复印和噪声污染这两种攻击对算法的影响，但却忽略了几何变换攻击对含水印的量子载体图像的影响。因此，提出一种能有效抵抗几何变换攻击的稳健型量子水印算法，具有重要的现实意义。

针对这方面的需求，Qu等人[16在2017年提出了一种基于QUALPI量子图像的稳健型量子水印算法。该算法将量子水印图像以LSQb修改技术的方式嵌入到量子载体图像中，再利用QUALPI量子图像具有旋转和缩放的不变性特点，使得含水印的量子载体图像能有效抵抗旋转、翻转和缩放等常见的几何变换攻击，具有良好的稳健性。虽然该算法利用LSQb修改技术易操作的优点，但是当非法第三方获取到含水印的量子载体图像，并从中读取出最低比特位平面时，非法第三方仍然有很大几率得知水印信息，使得该算法存在安全性隐患。1984年，Bennett等人[18]提出了第一个量子密钥分发协议，即BB84协议，达到让合法通信者共享一串随机密钥的目的，并且非法第三方不能得到关于密钥的任何信息。因此，本文提出了一种基于密钥的受控最低有效位修改技术的稳健型量子水印算法。即使非法第三方获取到含水印的量子载体图像，由于不知道密钥信息，所以无法得知水印信息，进一步提高了算法的稳健性。

# 1基于对数极坐标的量子图像表示模型

假设对数极坐标数字图像的对数半径 $\rho$ 和角方向 $\theta$ 的采样分辨率分别为 $2 ^ { m }$ 和 $2 ^ { n }$ ，那么基于对数极坐标的量子图像表示模型（QUALPI），该数字图像可以表示为

$$
\left. F \right. = \frac { 1 } { \sqrt { 2 ^ { m + n } } } \sum _ { \rho = 0 } ^ { 2 ^ { m } - 1 } \sum _ { \theta = 0 } ^ { 2 ^ { n } - 1 } \bigl ( \bigl \vert G ( \rho , \theta ) \bigr \rangle \otimes \bigl \vert \rho \bigr \rangle \otimes \bigl \vert \theta \bigr \rangle \bigr )
$$

其中： $G ( \rho , \theta )$ 表示第 $\rho \theta$ 个像素的灰度值。若数字图像的灰度范围是 $2 ^ { q }$ ，则像素的灰度值可以用二进制序列 $g _ { \scriptscriptstyle q - 1 } g _ { \scriptscriptstyle q - 2 } \cdots g _ { \scriptscriptstyle 1 } g _ { \scriptscriptstyle 0 }$ 编码，即

$$
G { \big ( } \rho , \theta { \big ) } = g _ { q - 1 } g _ { q - 2 } \cdots g _ { 1 } g _ { 0 } , G { \big ( } \rho , \theta { \big ) } \in { \Big [ } 0 , 2 ^ { q } - 1 { \Big ] }
$$

相应的，对数半径 $\rho$ 和角方向 $\theta$ 也可编码为

$$
\left. \rho \right. \otimes \left. \theta \right. = \left. \rho _ { { m } - 1 } \rho _ { { m } - 2 } \cdots \rho _ { 0 } \right. \otimes \left. \theta _ { { n } - 1 } \theta _ { { n } - 2 } \cdots \theta _ { 0 } \right.
$$

式（1）表明，整个QUALPI量子图像存储在一个归一化和等概率的量子叠加态中，每个基态表示一个像素。基态由三个量子比特序列的张量积组成，像素的所有信息，包括灰度值、对数半径和角方向，都存储在基态中。

图1是一幅大小为 $2 \times 4$ 、灰度范围为256的QUALPI量子图像的示例。采用QUALPI模型可以表示为

![](images/b0ada6f7d753ae76bfb8c04baef3bc9f10c1dba8125f4af376e318c9d4819072.jpg)  
图1QUALPI量子图像的示例

# 2 量子水印算法

运用基于密钥的受控最低有效位（LSQb）修改技术，本文提出了一种新颖的量子水印算法。新算法由量子水印图像的嵌入过程和提取过程两部分组成。其流程如图2所示。

![](images/71fb785d4c4a8741911147bf222e70fd8904bbd99325204e56e8350ce321cae2.jpg)  
图2新颖的量子水印算法的流程

# 2.1量子水印图像的嵌入过程

量子水印图像的嵌入过程如下所述。

a)假设数字载体图像是一幅大小为 $2 ^ { m } \times 2 ^ { n }$ 的灰度图像，数字水印图像是一幅大小为 $2 ^ { m } \times 2 ^ { n }$ 的二值图像。制备基于QUALPI模型的量子载体图像 $| c \rangle$ 和量子水印图像 $\left| W \right.$ ，其表达式分别如式（5）和（6）所示。

$$
\vert C \rangle = { \frac { 1 } { \sqrt { 2 ^ { m + n } } } } \sum _ { \rho = 0 } ^ { 2 ^ { m } - 1 } \sum _ { \theta = 0 } ^ { 2 ^ { n } - 1 } { \big \vert } c _ { 7 } c _ { 6 } \cdots c _ { 1 } c _ { 0 } { \big \rangle } { \big \vert } \rho \theta { \big \rangle }
$$

$$
\left| W \right. = \frac { 1 } { \sqrt { 2 ^ { m + n } } } \sum _ { \rho = 0 } ^ { 2 ^ { m } - 1 } \sum _ { \theta = 0 } ^ { 2 ^ { n } - 1 } \left| w _ { 0 } \right. \left| \rho \theta \right.
$$

b)发送方和接收方共享一组密钥 $K$

$$
K = k _ { 0 } k _ { 1 } \cdots k _ { 2 t } k _ { 2 t + 1 } \cdots k _ { 2 \left( 2 ^ { m + n } - 1 \right) } k _ { 2 \left( 2 ^ { m + n } - 1 \right) + 1 } , t \in \left[ 0 , 2 ^ { m + n } - 1 \right]
$$

其中 $\mathbf { \Psi } _ { t }$ 的值对应于量子载体图像 $| c \rangle$ 第 $j i$ 个像素。

根据密钥 $k _ { 2 t } k _ { 2 t + 1 }$ 的值，发送方将选择量子载体图像 $| c \rangle$ 第（20 $j i$ 个像素灰度值 $\left| { C } _ { 7 } ^ { j i } { C } _ { 6 } ^ { j i } { C } _ { 5 } ^ { j i } { C } _ { 4 } ^ { j i } { C } _ { 3 } ^ { j i } { C } _ { 2 } ^ { j i } { C } _ { 1 } ^ { j i } { C } _ { 0 } ^ { j i } \right.$ 的高四位中的某一位作为控制位，规定：

如果 $k _ { 2 t } k _ { 2 t + 1 } = 0 0$ ，选择 $\left| c _ { 7 } ^ { j i } \right.$ 作为控制位；  
如果 $k _ { 2 t } k _ { 2 t + 1 } = 0 1$ ，选择 $\left. c _ { 6 } ^ { j i } \right.$ 作为控制位；  
如果 $k _ { 2 t } k _ { 2 t + 1 } = 1 0$ ，选择 $\left. c _ { 5 } ^ { j i } \right.$ 作为控制位；  
如果 $k _ { 2 t } k _ { 2 t + 1 } = 1 1$ ，选择 $\left. c _ { 4 } ^ { j i } \right.$ 作为控制位。

再根据所选控制位的值，发送方将量子水印图像 $| W \rangle$ 第 $j i$ 个像素灰度值 $\left| w _ { 0 } ^ { j i } \right.$ 嵌入到最低有效位 $\left. c _ { 0 } ^ { j i } \right.$ 或次最低有效位 $\left| c _ { 1 } ^ { j i } \right.$ 上，即

(a)如果控制位是 $| 0 \rangle$ ，那么将 $\left| w _ { 0 } ^ { j i } \right.$ 嵌入到最低有效位 $\left. c _ { 0 } ^ { j i } \right.$ 上。具体的酉操作为：

如果 $\left| w _ { 0 } ^ { j i } \right.$ 和 $\left| c _ { 0 } ^ { j i } \right.$ 相同，那么不翻转 $\left. c _ { 0 } ^ { j i } \right.$ 的值。定义酉变换U:

$$
U _ { s } ^ { j i } = { \cal I } ^ { \otimes 8 } \otimes \left( \sum _ { \rho = 0 } ^ { 2 ^ { m } - 1 } \sum _ { \theta = 0 } ^ { 2 ^ { n } - 1 } \bigr | \rho \theta \bigr \rangle \bigl \langle \rho \theta \bigr | \right)
$$

其中： $I$ 表示 Pauli 矩阵 $\sigma _ { \iota }$ ：

$$
\begin{array} { r } { I = \sigma _ { { } _ { I } } = \boxed { 1 } \quad { 0 } } \\ { 0 \quad { 1 } . } \end{array}
$$

此时，酉变换 $U _ { s } ^ { j i }$ 作用在量子载体图像 $\left. C \right.$ 上，有

$$
\begin{array} { l } { { U _ { s } ^ { \mu } ( | C  ) = ( I ^ { \otimes \otimes } \bigotimes _ { \rho = 0 } ^ { 2 ^ { m _ { - 1 } } 2 ^ { n _ { - 1 } } } | \rho \theta   \rho \theta | ) } } \\ { { \displaystyle ( \frac { 1 } { \sqrt { 2 ^ { m ^ { + n } } } } \sum _ { \rho = 0 } ^ { 2 ^ { m _ { - 1 } } 2 ^ { n _ { - 1 } } } | c _ { \gamma } c _ { 6 } \cdots c _ { 1 } c _ { 0 }  | \rho \theta  \Bigg ) } } \\ { { \displaystyle = \frac { 1 } { \sqrt { 2 ^ { m ^ { + n } } } \sum _ { \rho = 0 } ^ { 2 ^ { m _ { - 1 } } 2 ^ { n _ { - 1 } } } | c _ { \gamma } c _ { 6 } \cdots c _ { 1 } c _ { 0 }  | \rho \theta  } } } \end{array}
$$

如果 $\left| w _ { 0 } ^ { j i } \right.$ 和 $\left. c _ { 0 } ^ { j i } \right.$ 不相同，那么翻转 $\left. c _ { 0 } ^ { j i } \right.$ 的值。定义酉变换$U _ { _ { D } } ^ { j i }$ ：

$$
U _ { _ { D } } ^ { j i } = I ^ { \otimes 7 } \otimes X \otimes { \left| \left. j i \right. \right.}  j i { \left| + I ^ { \otimes 8 } \otimes \left( \sum _ { \rho = 0 } ^ { 2 ^ { m } - 1 } \sum _ { \theta = 0 , \rho \theta \neq j i } ^ { 2 ^ { n } - 1 } | \rho \theta \rangle \langle \rho \theta | \right) \right.} 
$$

其中： $X$ 表示 Pauli矩阵 $\sigma _ { x }$ □

$$
X = \sigma _ { _ X } = { \left[ \begin{array} { l l } { 0 } & { 1 } \\ { 1 } & { 0 } \end{array} \right] } \quad
$$

此时，酉变换 $U _ { _ { D } } ^ { j i }$ 作用在量子载体图像 $\left. C \right.$ 上，有

$$
\begin{array} { l l } { { \displaystyle { V _ { \phi } ^ { * } [ ( C _ { i } ^ { * } ) ] = [ T ^ { \alpha } \otimes X \otimes | | \hat { H } _ { i } ^ { * } \rangle | \hat { H } _ { i } ^ { * } ] - T ^ { \alpha } \otimes \frac { \hat { \Phi } _ { i } ^ { * } } { \rho _ { i } + \alpha \kappa \kappa \kappa \kappa } | \rho \theta | \langle \rho \theta \theta \rangle ] } } } \\  { \displaystyle { [ \frac { 1 } { \sqrt { 2 ^ { \alpha - \kappa } } } \sum _ { \epsilon = \kappa } ^ { \infty } \sum _ { \epsilon = \kappa } ^ { \infty } c _ { \epsilon , \epsilon } \cdot ( c _ { \epsilon , \epsilon } ) ] \rho \theta \Big \} } } \\  { \displaystyle { = \frac { 1 } { \sqrt { 2 ^ { \alpha - \kappa } } } [ T ^ { \alpha } \otimes X \otimes | \hat { H } _ { i } ^ { * } | \hat { H } _ { i } ^ { * } | + { T ^ { \alpha } } \otimes \frac { \hat { \Phi } _ { i } ^ { * } } { c _ { \epsilon } ^ { \alpha - \kappa } c _ { \epsilon , \epsilon , \epsilon , \epsilon , \epsilon , \epsilon } } | \rho \theta \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } \hat { \theta } } } \\   \displaystyle  [ \mathrm { l e } _ { \epsilon } ^ { * } c _ { \epsilon } ^ { * } - c _ { \epsilon } ^ { * } c _ { \epsilon } ^ { * } c _ { \epsilon } ^ { * } c _ { \epsilon } ^ { * } c _ { \epsilon } ^ { * } c _ { \epsilon } ^ { * } \delta _ { \epsilon } ^ { * } \delta _ { \epsilon } ^ { * } \delta _ { \epsilon } ^ { * } c _ { \epsilon , \epsilon , \epsilon , \epsilon , \epsilon } ^ { * } ] \rho \hat  \sigma  \end{array}
$$

其中 $\left| \overline { { c } } _ { 0 } ^ { j i } \right.$ 是 $\left. c _ { 0 } ^ { j i } \right.$ 的相反状态，即

$$
\left| { \overline { { c } } } _ { 0 } \right. \Big \rangle = \left\{ { \begin{array} { l } { { \left| 0 \right. , \left| c _ { 0 } ^ { j i } \right. = \left| 1 \right. } } \\ { { \left| 1 \right. , \left| c _ { 0 } ^ { j i } \right. = \left| 0 \right. } } \end{array} } \right.
$$

![](images/aef709deece1a8cfd21c462b98698e57ac3e4554d5eff68ddc0c7fe5debe7dfa.jpg)  
图3基于密钥的受控LSQb修改技术的量子线路

通过酉变换 $U _ { s } ^ { j i }$ 或者 $U _ { _ { D } } ^ { \ j i }$ ，就可以将 $\left| w _ { 0 } ^ { j i } \right.$ 嵌入到 $\left. c _ { 0 } ^ { j i } \right.$ 上。

（b）如果控制位是 $| 1 \rangle$ ，那么将 $\left| w _ { 0 } ^ { j i } \right.$ 嵌入到次最低有效位$\left| c _ { 1 } ^ { j i } \right.$ 上。定义两种酉变换 $V _ { s } ^ { j i }$ 和 $V _ { _ { D } } ^ { j i }$ ：

$$
V _ { s } ^ { j i } = { I ^ { \otimes 8 } \otimes \left( \sum _ { \rho = 0 } ^ { 2 ^ { m } - 1 } \sum _ { \theta = 0 } ^ { 2 ^ { n } - 1 } \lvert \rho \theta \rangle \langle \rho \theta \rvert \right) }
$$

$$
V _ { _ { D } } ^ { j i } = I ^ { \otimes 6 } \otimes X \otimes I \otimes | j i  \bigr \langle j i | + I ^ { \otimes 8 } \otimes ( \sum _ { \rho = 0 } ^ { 2 ^ { m _ { - 1 } } } \sum _ { \theta = 0 , \rho \theta \neq j i } ^ { 2 ^ { n _ { - 1 } } } | \rho \theta  \bigl \langle \rho \theta | )
$$

如果 $\left| w _ { 0 } ^ { j i } \right.$ 和 $\left| c _ { 1 } ^ { j i } \right.$ 相同，那么酉变换 $V _ { s } ^ { j i }$ 作用在量子载体图像$| c \rangle$ 上，有

$$
\begin{array} { l } { { \displaystyle V _ { s } ^ { \mu } ( | C  ) = ( I ^ { \otimes s } \otimes \sum _ { \rho = 0 } ^ { 2 ^ { m - 1 } 2 ^ { n - 1 } } | \rho \theta   \rho \theta | ) } } \\ { { \displaystyle ( \frac { 1 } { \sqrt { 2 ^ { m + n } } } \sum _ { \rho = 0 } ^ { 2 ^ { m - 1 } 2 ^ { n - 1 } } \sum _ { \theta = 0 } ^ { 1 } c _ { \gamma } c _ { 6 } \cdots c _ { 1 } c _ { 0 } ) | \rho \theta  ) } } \\ { { \displaystyle = \frac { 1 } { \sqrt { 2 ^ { m + n } } } \sum _ { \rho = 0 } ^ { 2 ^ { m - 1 } 2 ^ { n - 1 } } \sum _ { \theta = 0 } ^ { 1 } | c _ { \gamma } c _ { 6 } \cdots c _ { 1 } c _ { 0 }  | \rho \theta  } } \end{array}
$$

如果 $\left| w _ { 0 } ^ { j i } \right.$ 和 $\left| c _ { 1 } ^ { j i } \right.$ 不相同，那么酉变换 $V _ { _ { D } } ^ { j i }$ 作用在量子载体图像 $| c \rangle$ 上，有

$$
\begin{array} { l } { { \displaystyle V _ { s } ^ { \prime } [ \{ c \} ) = \Bigg [ I ^ { \prime \prime } \otimes X \otimes I ^ { \prime } \otimes \{ | \partial _ { t } ^ { \prime } | ^ { \prime } \} + I ^ { \prime \prime } \otimes \frac { c ^ { \prime \prime } + 1 } { \rho ^ { \prime } \omega ^ { \prime } \omega ^ { \prime } } | \rho \theta ^ { \prime } | / \theta ^ { \prime \prime } ] } } \\ { { \displaystyle ( \frac { 1 } { \sqrt { 2 ^ { - \frac { 1 } { 2 ^ { \alpha } } } } } \sum _ { i = 0 } ^ { \infty } \sum _ { \ell , k ^ { \prime } = 1 } ^ { \infty } c _ { \ell , k ^ { \prime } } ) | \rho \theta ^ { \prime } | _ { \ell } ] } } \\ { { \displaystyle - \frac { 1 } { \sqrt { 2 ^ { - \frac { 1 } { \alpha ^ { \prime } } } } } [ I ^ { \prime \prime \prime } \otimes X \otimes I ^ { \prime } \otimes \{ | \partial _ { t } ^ { \prime } | ^ { \prime } \} + I ^ { \prime \prime \prime } \otimes \frac { c ^ { \prime } - 1 } { \rho ^ { \prime } \omega ^ { \prime } \omega ^ { \prime } \omega ^ { \prime } } | \rho \theta ^ { \prime } | / \theta ^ { \prime } ] } } \\ { { \displaystyle ( | c  c _ { \ell } ^ { \prime }  c _ { \ell } ^ { \prime } | _ { \ell } ^ { \prime \prime \prime } ) | \partial _ { t } ^ { \prime } \} + \sum _ { \ell = \frac { 1 } { \sqrt { 2 ^ { - \frac { 1 } { \alpha ^ { \prime } } } } } } ^ { \infty } \sum _ { \ell = \frac { 1 } { \sqrt { 2 ^ { - \frac { 1 } { \alpha ^ { \prime } } } } } } | c _ { \ell } ^ { \prime } - c _ { \ell } ^ { \prime } c _ { \ell } ^ { \prime } | / \theta ^ { \prime } | } } \\   \displaystyle - \frac { 1 } { \sqrt { 2 ^ { - \frac { 1 } { \alpha ^ { \prime } } } } } ( | c _ { \ell } ^ { \prime } c _ { \ell } ^ { \prime } , c _ { \ell } ^ { \prime } c _ { \ell } ^ { \prime } , c _ { \ell } ^ { \prime } | ) | \begin{array} { l }  { \displaystyle \sum _ { j = 1 } ^ { \ell } \sum _ { i = 0 } ^ { \ell - 1 } c _ { \ell } ^ { \prime } | \partial _ { t } ^ { \prime } | ^ { \prime } } \\   \displaystyle \sum _ { \ell = \ell } ^ { \ell } | c _ { \ell } ^ { \prime } , c _ { \ell } ^ { \prime } , c _ { \ell } ^ { \prime } , c _ { \ell }  \end{array} \end{array}
$$

通过酉变换 $V _ { s } ^ { j i }$ 或者 $V _ { _ { D } } ^ { j i }$ ，就可以将 $\left| \boldsymbol { w } _ { 0 } ^ { j i } \right.$ 嵌入到 $\left| c _ { 1 } ^ { j i } \right.$ 上。

这种基于密钥的受控LSQb修改技术的嵌入方法，可由图3设计的量子线路来实现。在图3中，符号“·”“。”和“ $\oplus$ ”分别代表1控制位、0控制位和受控非门，并且常数输入量子比特 $| 0 \rangle$ 是辅助量子比特。为了方便起见，基于密钥的受控LSQb修改技术的量子线路方块图省略了辅助输入和无关输出，如图4所示。

![](images/409b8a2c755083a3835b6e1a98af74c3c7734ac9735b8c20e9d919f92bc160da.jpg)  
图4基于密钥的受控LSQb修改技术的量子线路方块图

![](images/155f788b8f48342d48be3c11e37128772e8e8f9a4dcbb96ed6634ecdb82ac436.jpg)  
图5量子水印图像的嵌入量子线路

c)通过执行 $2 ^ { m + n }$ 次 b)，量子水印图像 $| W \rangle$ 的所有信息就会嵌入到量子载体图像 $\left. C \right.$ 中，得到含水印的量子载体图像 $\left. C W \right.$ ：

$$
{ \big | } C W \big \rangle = { \frac { 1 } { \sqrt { 2 ^ { m + n } } } } \sum _ { \rho = 0 } ^ { 2 ^ { m } - 1 } \sum _ { \theta = 0 } ^ { 2 ^ { n } - 1 } { \bigg | } c _ { 7 } c _ { 6 } \cdots \left( c _ { 1 } \right) ^ { \prime } \left( c _ { _ 0 } \right) ^ { \prime } { \bigg \rangle } { \big | } \rho \theta \big \rangle
$$

为了提高新算法的可执行性，本文设计了一种高效的量子水印图像的嵌入量子线路，如图5所示。这种基于密钥的受控LSQb修改技术的嵌入方法，既保证了含水印的量子载体图像$\left. C W \right.$ 在视觉上与原始的量子载体图像 $| c \rangle$ 没有明显差别，也使得新算法具有良好的稳健型。

至此，量子水印图像的嵌入过程就完成了。

# 2.2量子水印图像的提取过程

量子水印图像的提取过程如下所述。

a)在希尔伯特空间中，含水印的量子载体图像 $\left. C W \right.$ 是一个复杂的向量，需要把该向量分解成灰度值信息和像素位置信息的张量积形式。假设含水印的量子载体图像 $\left. C W \right.$ 对应的矢量是 $\boldsymbol { \mathcal { Q } }$ ，则矢量 $\boldsymbol { Q }$ 可分解成如下形式：

$$
\begin{array} { r } { Q = a _ { 0 } \otimes \left( \begin{array} { l } { 1 } \\ { 0 } \\ { 0 } \\ { \vdots } \\ { 0 } \\ { 0 } \\ { 0 } \end{array} \right) + \cdots + a _ { _ { 2 ^ { m + n - 2 } } } \otimes \left( \begin{array} { l } { 0 } \\ { 0 } \\ { 0 } \\ { \vdots } \\ { 1 } \\ { 0 } \end{array} \right) + a _ { _ { 2 ^ { m + n - 1 } } } \otimes \left( \begin{array} { l } { 0 } \\ { 0 } \\ { 0 } \\ { \vdots } \\ { 0 } \\ { 1 } \end{array} \right) } \end{array}
$$

其中：符号“ $\otimes$ ”表示张量积。张量积的第一部分和第二部分分别是含水印的量子载体图像 $\left. C W \right.$ 的灰度值信息和对应像素的位置信息。

b)为了提取水印信息，将灰度值信息 $a _ { 0 }$ 、、 $a _ { { _ 2 ^ { m + n _ { - 2 } } } }$ 和$a _ { { } _ { 2 } m + n _ { - 1 } }$ 转换成相应的二进制码 $b _ { 0 }$ 、、 $b _ { { } _ { 2 ^ { m + n } - 2 } }$ 和b $b _ { { _ 2 ^ { m + n _ { - 1 } } } }$ 2m+n_。 （20 $b _ { _ t }$ 对应于含水印的量子载体图像 $\left. C W \right.$ 第 $j i$ 个像素的灰度值：

$$
b _ { _ t } = \left| C _ { _ 7 } ^ { j i } C _ { _ 6 } ^ { j i } C _ { _ 5 } ^ { j i } C _ { _ 4 } ^ { j i } C _ { _ 3 } ^ { j i } C _ { _ 2 } ^ { j i } \left( C _ { _ 1 } ^ { j i } \right) ^ { \prime } \left( C _ { _ 0 } ^ { j i } \right) ^ { \prime } \right.
$$

c)根据密钥 $k _ { 2 t } k _ { 2 t + 1 }$ 的值，以及通信双方预先制定的规则，接收方从灰度值 $b _ { _ t }$ 的高四位中确定控制位。如果控制位是 $| 0 \rangle$ ，那么灰度值 $b _ { _ t }$ 的最低有效位 $\left| \left( c _ { 0 } ^ { j i } \right) ^ { \prime } \right.$ 为水印信息；反之，次最低有效位 $\left| \left( c _ { 1 } ^ { j i } \right) ^ { \prime } \right.$ 为水印信息。这种基于密钥的受控LSQb 提取技术的提取方法，可由图6设计的量子线路来实现。基于密钥的受控LSQb 提取技术的量子线路方块图，如图7所示，则省略了无关输出。

本文也设计了一种高效的量子水印图像的提取量子线路，如图8所示。在图8中， $2 ^ { m + n }$ 个输入量子比特 $| 0 \rangle$ 对应的输出量子比特，分别是量子水印图像 $| W \rangle$ 每个像素的灰度值信息。

从上述步骤可知，量子水印图像的提取过程其实是嵌入过程的一个逆过程。

# 3 实验仿真结果和相关性能分析

评估量子水印算法性能主要有三个重要指标，分别是透明性、稳健性和嵌入容量。透明性要求嵌入在量子载体中的量子水印是不可知觉的，而且不影响量子载体的正常使用。稳健性是指在经历多种恶意攻击或无意攻击后，量子水印仍能保持部分完整性，并能被准确鉴别。嵌入容量计算嵌入在量子载体中的量子水印的信息量。为了更好地分析本文所提出的量子水印算法在透明性、稳健性和嵌入容量上的性能，本章将给出若干新算法在经典计算机MATLABR2012a环境下得到的实验数据。实验所用的载体灰度图像为Girl、Woman、Lena和Vegetables，水印二值图像为Thumbs-up、Recycling、Ribbon和Butterfly，分别如图9和10所示，其图像大小均为 $2 5 6 \times 2 5 6$ 。

![](images/5fd6cb1fd6e199fcc58419dae4fae6d613ea0a0e0b1ab4af286f24abed3c7baa.jpg)  
图6基于密钥的受控LSQb提取技术的量子线路

![](images/cd3d6308eacac776cfcfdd1bd101bc1b56852e118cf1c8c47d41fecf1682a00e.jpg)  
图7基于密钥的受控LSQb 提取技术的量子线路方块图

![](images/428f974e7a7d050a5fb87731fdfc2689bab5bfd9bde3e7a62ffcbe96ff2f2abc.jpg)  
图8量子水印图像的提取量子线路

![](images/06ae21c966786c58bd8108a6b9848d82c85c9b698f01a8d66c086f4d49b76152.jpg)  
图9实验所用的载体灰度图像

图10实验所用的水印二值图像  
![](images/222d748e75b5ef263a045dba6143b7a0525189de2fb677a0d94454edd7c51c7c.jpg)  
首先，根据量子水印图像的嵌入过程，分析扫描与复印攻

原始的量子载体图像与含水印的量子载体图像之间的保真度，是评估量子水印算法透明性最常用的方法。在经典数字图像处理中，峰值信噪比（PSNR）则是最广泛使用的评鉴画质的测量方法。假设 $I$ 是原始的载体图像， $J$ 是含水印的载体图像，式（22）和（23）分别给出了均方误差（MSE）和PSNR的计算公式。

$$
M S E = \frac { 1 } { m n } \sum _ { \rho = 0 } ^ { 2 ^ { m } - 1 } \sum _ { \theta = 0 } ^ { 2 ^ { n } - 1 } \bigl [ I \bigl ( \rho , \theta \bigr ) - J \bigl ( \rho , \theta \bigr ) \bigr ] ^ { 2 }
$$

# 3.1 透明性

$$
P S N R { = } 2 0 { \log } _ { 1 0 } \Biggl ( \frac { M A X _ { \scriptscriptstyle I } } { \sqrt { M S E } } \Biggr )
$$

其中： $I ( \rho , \theta )$ 和 $J ( \rho , \theta )$ 分别表示原始的载体图像 $I$ 和含水印的载体图像 $J$ 在第 $( \rho , \theta )$ 个像素的灰度值； $M A X _ { I }$ 是原始的载体图像 $I$ 的最大灰度值。

水印二值图像 Thumbs-up、Recycling、Ribbon 和 Butterfly,采用基于密钥的受控最低有效位修改技术的方法，分别嵌入到载体灰度图像Girl、Woman、Lena 和Vegetables中，得到含水印的载体图像，如图11所示。在图11中，单靠人眼是无法有效区分原始的载体图像和含水印的载体图像。此外，计算图11中原始的载体图像与对应的含水印的载体图像之间的PSNR值，计算结果如表1所示。在表1中，PSNR值都高于图像质量标准38dB，表明含水印的载体图像失真较小。因此，新算法具有良好的透明性。

# 3.2稳健性

稳健性是评估量子水印算法的关键。嵌入在量子载体中的量子水印，不仅使非法第三方难以探知，也要使当非法第三方对含水印的量子载体进行攻击之后，量子水印受到的影响较小。非法第三方的攻击手段分为恶意攻击和无意攻击。恶意攻击（如数据窜改和有损压缩）有极大的几率删除，甚至破坏嵌入在量子载体中的量子水印，使得通信双方和非法第三方都无法获取量子水印。因而量子水印算法通常会着重分析非法第三方的无意攻击对量子水印的影响。常见的无意攻击有扫描与复印、几何变换和噪声污染等攻击。

为了保证所提出的量子水印算法在稳健性上有良好的表现，本节将从非法第三方的扫描与复印、几何变换和噪声污染这三种攻击来分析新算法的稳健性。

![](images/71cbc2b4c07aef3e4b9d7a6c0b221c39b4a82659873a5d8d2a6ff88bf80c4437.jpg)  
图11透明性的仿真结果

在四组示例中，每组示例的第一幅图是原始的载体图像，第二幅图是水印图像，第三幅图是含水印的载体图像

表1在图11中，原始的载体图像与对应的含水印的载体图像之间的PSNR值  

<html><body><table><tr><td colspan="3"></td></tr><tr><td>水印图像</td><td>载体图像</td><td>PSNR/dB</td></tr><tr><td>Thumbs-up</td><td>Girl</td><td>44.7304</td></tr><tr><td>Recycling</td><td>Woman</td><td>46.1151</td></tr><tr><td>Ribbon</td><td>Lena</td><td>46.1146</td></tr><tr><td>Butterfly</td><td>Vegetables</td><td>46.1284</td></tr></table></body></html>

击对新算法的影响。当非法第三方对含水印的量子载体图像进行扫描与复印之后，非法第三方可以获取该图像像素信息的最低比特位平面和次最低比特位平面。非法第三方试图从这两个位平面中获取水印信息，这是徒然的。因为量子水印图像是以基于密钥的受控最低有效位修改技术的方式嵌入到量子载体图像中，而且通信双方共享的密钥是绝对安全的，所以非法第三方并不知道量子水印图像嵌入到量子载体图像中的具体位置。通信双方共享的密钥提高了新算法的稳健性。

接着，根据对数极坐标的量子图像表示模型（QUALPI)特性，分析几何变换攻击对新算法的影响。QUALPI量子图像具有旋转和缩放的不变性特点，使得QUALPI量子图像的三种变换，即对称变换、旋转变换和缩放变换，可以灵活快速地进行。当非法第三方对含水印的量子载体图像进行几何变换攻击之后，接收方仍然可以通过酉变换恢复出原始的含水印的量子载体图像，并从中提取出量子水印图像。

为了证明上述论点，对图11中四组示例的含水印的载体图像分别进行旋转、水平轴翻转、垂直轴翻转和缩放等几何变换，仿真结果如图12所示。在图12中，受到几何变换攻击后的含水印的载体图像仍可恢复出含水印的载体图像。运用基于密钥的受控最低有效位提取技术的提取方法，从含水印的载体图像中提取出水印图像，仍具有很高的图像质量。采用QUALPI模型表示载体图像和水印图像也提高了新算法的稳健性。

最后，根据经典数字图像处理中另一个常用的误码率（BER），分析噪声污染攻击对新算法的影响。含水印的载体图像在通信网络中传输时，由于信道中存在着噪声，使得输出的图像产生误码，在某种程度上与原始的含水印的载体图像不一样。而单靠人眼是无法分辨出这两张图像的区别，因此，采用误码率来衡量噪声污染在图像传输过程中的影响。BER定义为PSNR的倒数，即

$$
B E R = \big / \mathop { P S N R }
$$

根据表1给出的PSNR值，计算得到BER值，如表2所示。在表2中，新算法的BER值都比较小，表明噪声污染对新算法的影响较小。

通过分析非法第三方的无意攻击，表明新算法具有良好的稳健性。

# 3.3嵌入容量

量子水印算法的嵌入容量可由嵌入率和修改率来衡量。根据嵌入率的定义（嵌入率 $\ c =$ 嵌入水印的比特数/载体图像所有像素的个数），可知新算法的嵌入率为1。此外，根据修改率的定义（修改率 $\overset { \cdot } { = }$ 载体图像单位像素被修改的比特数/嵌入水印的比特数），假定水印二值图像的0值比特和1值比特均匀分布，那么载体图像单位像素的最低有效位或次最低有效位，有 $5 0 \%$ 的概率被修改，可知新算法的修改率为0.5。

![](images/7b4e3e77f5704482fce14e274049418f649d4934e5eba384026f370f13818104.jpg)

图12稳健性仿真结果

在四组示例中，每组示例的第一幅图是受到几何变换攻击后的含水印的载体图像，第二幅图是通过酉变换恢复出的含水印的载体图像，第三幅图是提取出的水印图像

表2根据表1的PSNR值，计算得到BER值  

<html><body><table><tr><td>水印图像</td><td>载体图像</td><td>BER</td></tr><tr><td>Thumbs-up</td><td>Girl</td><td>0.0224</td></tr><tr><td>Recycling</td><td>Woman</td><td>0.0217</td></tr><tr><td>Ribbon</td><td>Lena</td><td>0.0217</td></tr><tr><td>Butterfly</td><td>Vegetables</td><td>0.0217</td></tr></table></body></html>

# 4 结束语

运用对数极坐标的量子图像表示模型（QUALPI）具有旋转和缩放的不变性特点，以及基于密钥的受控最低有效位修改技术具有易操作的优点，本文提出了一种新颖的稳健型量子水印算法。相比于以往的量子水印算法，新算法利用QUALPI量子图像的特点，当含水印的量子载体图像受到旋转、翻转和缩放等几何变换攻击时，仍可从图像中提取出所嵌入的量子水印图像，保证了含水印的量子载体图像的稳健性。此外，基于密钥的受控最低有效位修改技术的嵌入方法，使得非法第三方在无法获取密钥信息的情况下，即便对含水印的量子载体图像进行扫描与复印攻击，也无法恢复出量子水印图像，进一步保护了量子图像的版权。

基于MATLAB给出的实验仿真，再结合经典数字图像处理中的峰值信噪比和误码率，对新算法的透明性和稳健性进行分析。仿真结果和实验数据也表明新算法具有良好的透明性和稳健性。根据对新算法的嵌入容量进行分析，新算法的嵌入率为1，这是一个比较可观的嵌入率。

本文另外一个创新之处是设计了基于密钥的受控最低有效位修改技术的量子线路和基于密钥的受控最低有效位提取技术的量子线路，一方面确保新算法在实现过程中严格遵循了量子力学原理，且在当前的物理实验条件下是可行的；另一方面也使得新算法具有很好的实用性。

# 参考文献：

[1]Nielsen M A, Chuang IL. Quantum computation and quantum information [J].Cambridge University Press,2011,21(1):1-59.   
[2]Venegas-Andraca S E, Bose S. Storing,processing and retrieving an image using quantum mechanics [J]. Quantum Information and Computation, 2003,5105 (8):1085-1090.   
[3]Venegas-Andraca S E,Ball JL,Burnet K,et al.Processing images in entangled quantum systems [J].Kluwer Academic Publishers,2010,9(1): 1-11.   
[4]Latorre JI. Image compression and entanglement [J]. Computer Science, 2005.   
[5]Le P Q,Dong Fangyan,Hirota K.A flexible representation of quantum images for polynomial preparation,image compression,and processing operations [J]. Quantum Information Processing,2011,10(1): 63-84.   
[6]Zhang Yi,Lu Kai,Gao Yinghui,et al. NEQR: a novel enhanced quantum representation of digital images [J]. Quantum Information Processing, 2013,12 (8): 2833-2860.   
[7]Zhang Yi, Lu Kai, Gao Yinghui,et al.A novel quantum representation for log-polar images [J].Quantum Information Processing，2013,12(9): 3103-3126.   
[8]Sang Jianzhi,Wang Shen,Li Qiong.A novel quantum representation of color digital images [J]. Quantum Information Processing,2O17,16 (2): 42.   
[9]Araujo H,Dias J M.An introduction to the log-polar mapping [J] Workshop on Cybernetic Vision,1996,69 (3): 139-144.   
[10] Wang Shen,Sang Jianzhi, Song Xianhua,et al.Least significant qubit (LSQb) information hiding algorithm for quantum image [J]. Measurement, 2015,73:352-359.   
[11]李涛，何煌兴，瞿治国．一种基于含水印量子图像的自适应量子隐写算 法[J].计算机应用研究,2018,35(2):503-506.(Li Tao,He Huangxing, Qu Zhiguo.Novel self-adaptive quantum steganography algorithm based on quantum image with watermark [J].Application Research of Computers, 2018,35 (2): 503-506.)   
[12] Heidari S,Farzadnia E.A novel quantum LSB-based steganography method using the Gray code for colored quantum images [J].Quantum Information Processing,2017,16 (10): 242.   
[13] Zhang Weiwei, Gao Fei,Liu Bin,et al. Aquantum watermark protocol [J]. International Journal of Theoretical Physics,2013,52(2): 504-513.   
[14] Zhang Weiwei, Gao Fei,Liu Bin,et al. A watermark strategy for quantum images based on quantum fourier transform [J].Quantum Information Processing,2013,12(2): 793-803.   
[15] Sang Jianzhi,Wang Shen,Li Qiong.Least significant qubit algorithm for quantum images [J]. Quantum Information Processing,2016,15 (11): 1-20.   
[16] Qu Zhiguo,Cheng Zhenwen,Luo Mingxing,et al.A robust quantum watermark algorithm based on quantum log-polar images [J]. International Journal of Theoretical Physics,2017,56 (11): 3460-3476.   
[17] Gupta S,Goyal A,Bhushan B.Information hiding using least significant bit steganography and cryptography [J].International Journal of Modern Education and Computer Science,2012,4(6): 27-34.   
[18] Bennett C H, Brassard G. Quantum cryptography:public key distribution and coin tossingIn [C]// Proc of IEEE International Conference on Computers,Systems and Signal processing. 1984: 175-179.