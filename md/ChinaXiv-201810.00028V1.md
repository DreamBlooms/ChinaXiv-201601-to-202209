# 基于明文相关的混沌映射与SHA-256算法的数字图像的加密与监测

刘西林，严广乐(上海理工大学 管理学院，上海 200093)

摘要：针对数字图像的传播安全性问题，以及数字图像加密脱离明文，过分依赖混沌系统的问题，提出了基于明文相关的混沌映射与SHA-256算法的数字图像的加密与监测算法。算法通过使用 SHA-256算法计算明文图像的哈希值，作为摘要来监测数字图像的传播；使用前向扩散、关联明文的置乱与后向扩散的方法对数字图像进行加密，Lorenz混沌映射产生相应的密码。结果表明该算法具有较好的抵抗各种攻击的能力，达到了图像传播的安全性与隐蔽性的目的。

关键词：混沌系统；图像加密；SHA-256；哈希值；Lorenz 混沌映射 中图分类号：TP309.7 doi:10.3969/j.issn.1001-3695.2018.07.0411

# Encryption and monitoring of digital images based on plaintext related chaotic map and SHA-256 algorithm

Liu Xilin, Yan Guangle (Business School,University ofShanghai forScience&Technology,Shanghai2Ooo93,China)

Abstract:Forthesecurityproblemofthe spreadofdigital imageandthedigital imageencryption fromplaintextandtoodepend onthecaoticsystems,thispaper proposesadigitalimage encryptionand monitoringalgorithmcombinedwithplaintext-related chaotic mapping and SHA-256.The algorithmuses the SHA-256algorithmtocalculatethe hash value asrecordtomonitorthe spreadofdigital image;Lorenzchaotic mappinggenerates thecorresponding cryptogrambyusingforwarddifusion,associated plaintext scramblingand backward diffusion to encrypt the digital image.Theresultsshow that the algorithmcanresist many attacks and achieve the security and concealment of image propagation.

Key words: chaotic systems; image encryption; SHA-256; hash value; Lorenz chaotic mapping

# 0 引言

随着网络信息技术的迅速发展，在通信系统的传输过程中，数字图像信息极其容易被恶意者拦截，面临着隐私泄露和数据安全等问题。在远程医疗、军事、个人图像、视频会议和生物指标系统等应用中，图像的传输需要确保安全性，但泄露事件却频有发生错误!未找到引用源。因此，数字图像的加密是数字图像安全传输的重要保障。

伴随着人们越来越重视数字图像传输中的安全性问题，近年来学者们提出了一些新的图像加密算法错误!未找到引用源。。其中有基于图像像素点位置置乱与像素值扩散的如文献[2\~4]，都完成了数字图像的加密，但都存在着密钥空间小的问题。文献[5,7,8]都是基于数字图像的频域变换与混沌系统结合，使得将数字图像能完成更好的加密效果，但同时存在加密后密文图像信息熵偏小的问题。而文献[4]将多个方法与混沌系统结合对数字图像进行加密，算法密钥空间很大，但加密解密过程繁琐，存在效率低的问题。此外，以上的部分文献算法还存在置乱与扩散严重依赖混沌系统，脱离明文，从而削弱了算法的可靠性问题。在众多经典的数字图像密码系统中，密钥是产生加密明文图像的密码的唯一依据，即密码仅受密钥控制，与密钥有关，而与明文无关，这种类型的图像密码系统易受选择明文攻击或已知明文攻击错误!未找到引用源。

为此，本文提出了基于明文相关混沌映射与SHA-256算法的数字图像的加密与检测。首先通过对数字图像的灰度图像使用SHA-256算法生成256bit的哈希值作为摘要，来监测密文图像在传播过程中是否被篡改；其次，使用前向扩散与逆向扩散相结合的方法对数字图像的像素值进行扩散，使用明文相关的置乱算法对数字图像的位置进行置乱后形成密文，即密码的生成不止与密钥有关还和明文的信息有关；三维Lorenz混沌映射产生对应的密码。这样传输加密后的图像就实现了数字图像的隐秘传输。实验结果显示该算法不仅能够提高密钥的敏感性、监测传输图像的安全性，还能有效的抵抗明文、暴力等其他攻击。

# 1 SHA-256算法、混沌系统

# 1.1 SHA-256 算法

SHA(securehashalgorithm)安全加密标准，是至今国际上使用最为广泛的较为安全的压缩算法之一，由美国NIST和NSA两个组织共同开发的，此算法于1993年5月11日被美国NIST和 NSA 设定为加密标准错误:未找到引用源。。SHA-256 算法就是其中一个，该算法弥补了SHA-1存在安全隐患的问题。可以将数字图像信息转换成256bit的哈希值，数字图像内容有任何微小的变换，哈希值都会发生巨大的变化，经使用SHA-256算法的数字图像，就相当于拥有了“指纹”。

# 1.2Lorenz混沌系统

本文采用的是Lorenz系统映射，其具体的动力学方程如下所示：

$$
\left\{ \begin{array} { l } { x = a ( y - x ) + w } \\ { y = c x - y - x z } \\ { z = x y - b z } \\ { w = - y z + r w } \end{array} \right.
$$

其中 $: a$ ，b，c， $\boldsymbol { \mathbf { \rho } } _ { w }$ ， $\boldsymbol { r }$ 为超混沌系统的参数， $x , y , z$ 为Lorenz 混沌系统产生混沌序列的三个状态变量，当 $\scriptstyle a = 1 0$ ， $\scriptstyle { b = 8 / 3 }$ ， $c { = } 2 8$ -1.52≤r≤-0.06时，式（1）处于混沌状态错误!未找到引用源。

# 2 加密方案设计

方案设计流程图如图1所示。

![](images/cfdf82d39faa6a71860e0c15ba704ec88cac9cc2143e904aa9e07ae60fa9624b.jpg)  
图1方案设计流程图

# 2.1产生图像摘要

将数字图像转换成灰度图像，即三维矩阵转换成二维矩阵(不可逆)。将灰度图像经过SHA-256 算法产生的256bit哈希值作为摘要，成为数字图像的“指纹”，对经典Lena灰度图像使用SHA-256 算法编码产生的256位摘要(哈希值)为：9a9b4963ddaa149de2d7d66b5c952e2fe0036f4a819046998f766be605eb3f18。发送方保存该摘要值等待与接收方解密密文后再经过SHA-256编码的摘要值进行匹配。

# 2.2 图像加密

本文提出的加密算法首先对原始图像的像素值就行正向扩散操作；然后进行明文相关的置乱方法对像素的位置进行置乱操作；最后再进行逆向扩散像素值，形成密文。混沌Lorenz系统的参数和初始值作为密钥。解密过程是加密过程的逆过程。假设明文图像为 $\boldsymbol { p }$ ，大小为 $\mathbf { M } ^ { * } \mathbf { N }$ ，灰度等级为 $L$ ，密钥$K = \{ x _ { 0 } , y _ { 0 } , z _ { 0 } , w _ { 0 } , r _ { 1 } , r _ { 2 } \}$ ，其中 $\{ x _ { 0 } , y _ { 0 } , z _ { 0 } , w _ { 0 } \}$ 为状态初值， $r _ { 1 } , r _ { 2 }$ 为两个8b的随机数。具体加密步骤如下：

a)借助于密钥状态初值，迭代混沌Lorenz系统产生4个伪随机序列 $\{ x _ { i } \} \cdot \{ y _ { i } \} \cdot \{ z _ { i } \} \cdot \{ w _ { i } \}$ ， $\scriptstyle { i = 1 }$ ，2，…，MN。借助于这四个伪随机序列，生成矩阵 $\chi$ 、Y、Z、W、 $\upsilon$ 和 $V _ { \circ }$ 具体公式如下错误！未找到引用源。：

$$
\begin{array}{c} \begin{array} { r l } & { \{ X ( k , l ) = \iint _ { \partial O P } \Big ( ( x _ { ( k - 1 ) ^ { * } N + l } + 5 0 0 \bmod 1 ) ^ { * } 1 0 ^ { 1 3 } \Big ) \mathrm { m o d } 2 ^ { L } } \\ & { \{ Y ( k , l ) = \iint _ { \partial O P } \Big ( ( y _ { ( k - 1 ) ^ { * } N + l } + 5 0 0 \bmod 1 ) ^ { * } 1 0 ^ { 1 3 } \Big ) \mathrm { m o d } 2 ^ { L }  } \\ & {  \begin{array} { r l } { Z ( k , l ) = ( f l o o r ( z _ { ( k - 1 ) ^ { * } N + l } * 1 0 ^ { 1 3 } ) \bmod M ) + 1 } & { ( \mathrm { ~ i ~ } } \\ { W ( k , l ) = ( f l o o r ( ( w _ { ( k - 1 ) ^ { * } N + l } + 5 0 0 \bmod 1 ) * 1 0 ^ { 1 2 } ) \bmod N ) + 1 } & { ( \mathrm { ~ i ~ } } \end{array} } \\ & {  \begin{array} { r l } { U ( k , l ) = ( f l o o r ( ( w _ { ( k - 1 ) ^ { * } N + l } + y _ { ( k - 1 ) ^ { * } N + l } + 5 0 0 \bmod 1 ) ^ { * } 1 0 ^ { 1 2 } ) \bmod N ) + 1 } & { ( \mathrm { ~ i ~ } } \\ { V ( k , l ) = ( f l o o r ( ( x _ { ( k - 1 ) ^ { * } N + l } + y _ { ( k - 1 ) ^ { * } N + l } + 5 0 0 \bmod 1 ) ^ { * } 1 0 ^ { 1 2 } ) \bmod M ) + 1 } & { ( \mathrm { ~ i ~ } } \end{array} ] \} } \\ & {  \{ V ( k , l ) = ( f l o o r ( ( z _ { ( k - 1 ) ^ { * } N + l } + w _ { ( k - 1 ) ^ { * } N + l } + 5 0 0 \bmod 1 ) ^ { * } 1 0 ^ { 1 2 } ) \bmod N ) + 1 \} } \end{array}   \end{array}
$$

b)将明文图像 $\boldsymbol { p }$ 通过正向扩散转换成矩阵 $A$ ，具体公式如下：

$$
\left\{ \begin{array} { l l } { A ( i , j ) = P ( i , j ) + X ( i , j ) + r _ { 1 } \bmod 2 ^ { L } ( i = 1 , j = 1 ) } \\ { A ( i , j ) = P ( i , j ) + A ( i , j - 1 ) + X ( i , j ) \bmod 2 ^ { L } ( i = 1 , j = j + 1 , j \leq N ) } \\ { A ( i , j ) = P ( i , j ) + s u m ( A ( i - 1 , 1 t o N ) ) + X ( i , j ) \bmod 2 ^ { L } ( i = i + 1 , j = 1 , i \leq M ) } \end{array} \right.
$$

其中 $s u m ( t )$ 返回向量t 中所有元素的和。

c)通过明文相关的置乱算法将图像矩阵 $A$ 转换成矩阵 $B$ 具体公式如下所示：

$$
\begin{array} { r } { \left\{ { m = U ( i , j ) + s u m ( A ( Z ( i , j ) , 1 t o N ) { \bmod { M } } ) + 1 } _ { ( 4 ) } \right. } \\ { \left. { n = V ( i , j ) + s u m ( A ( 1 t o M , w ( i , j ) ) { \bmod { N } } ) + 1 } _ { } \right. } \end{array}
$$

其中 $\mathbf { \nabla } _ { m }$ 和 $n$ 分别是矩阵 $B$ 的坐标，在 $m { = } i$ 或 $\boldsymbol { Z } ( i , j )$ ，或者 $\scriptstyle n = j$ 或 $W ( i , j )$ ，或者 $Z ( i , j ) { = } i$ 或者 $W ( i , j ) { = } j$ 情况下， $A ( i , j )$ 位置不变，否则 $A ( i , j )$ 与 $A ( m , n )$ 互换位置, $s u m ( t )$ 返回向量 $\mathrm { ~  ~ \cdot ~ }$ 中所有元素的和。

d)再对矩阵 $B$ 进行逆向扩散得到矩阵 $c _ { \mathrm { { i } } }$ ，具体公式如下：

$$
\left\{ \begin{array} { l l } { C ( i , j ) = B ( i , j ) + Y ( i , j ) + r _ { 2 } \bmod 2 ^ { L } ( i = M , j = N ) } \\ { C ( i , j ) = B ( i , j ) + C ( i , j + 1 ) + Y ( i , j ) \bmod 2 ^ { L } ( i = M , j = j - 1 , j > 1 ) } \\ { C ( i , j ) = B ( i , j ) + s u m ( C ( i + 1 , 1 t o N ) ) + Y ( i , j ) \bmod 2 ^ { L } ( j = N , i = i + 1 , i \geq 1 ) } \end{array} \right.
$$

其中 $s u m ( t )$ 返回向量 $\mathrm { \Omega } _ { \mathrm { t } }$ 中所有元素的和。

经过正向扩散，明文相关的置乱，逆向扩散可以得到密文

图像。

# 3 仿真实验

在MATLAB7.1环境下对本文提出的算法进行仿真实验，得到结果。待加密的Lena图像如图2所示，加密后的Lena图像如图3所示，解密后的Lean灰度图像如图4所示，错误密钥解密后的图像如图5所示，待加密的Cameraman图像如图6所示，加密后的Cameraman图像如图7所示，正确秘钥解密后的Cameraman图像如图8所示，错误秘钥解密后的图像如图9所示。

![](images/43016c51f7f3c2d19ae8a35d48407b1b840ecce200dff3b19a1c19266171be87.jpg)  
图2待加密的Lena 图像

![](images/460420f34aaf1402eb95cf8fe750c978984ff0665614756dd93c733d0d5d917a.jpg)  
图3加密后的密文图像

![](images/5e433112db94e2ba50650f077a34116da9d469d88d558b6c491bda89e253a96c.jpg)  
图4解密后的Lena 图像

![](images/b423e748a0c09d3e695e710765b3e68a8c51401d7255e9cbbe8ad45d6258e2f7.jpg)  
图5错误密钥解密后图像

![](images/79497d16ade3a4428d0f2afbed2651a7284dae7cffdb96435e87bb951698c981.jpg)  
图6待加密的Cameraman图像

![](images/e09e60489b0e04b0cc7201821faa6caf91ccdef37bd46ebf5c3bfdf693731d66.jpg)  
图7加密后的密文图像

![](images/04e4a0420df3de1e406df83dd01e305570073483dc55d4546db39955a541ffe9.jpg)  
图8正确秘钥解密后的图像

![](images/2efcea8678a0b2f74b717c2d1a90994278bf486cf79ddc304a5fccfb07587152.jpg)  
图9错误秘钥解密后的图像

接收方解密Lena后的图像再经过使SHA-256 算法编码产生的摘要（哈希值）为：9a9b4963ddaa149de2d7d66b5c952e2fe0036f4a819046998f766be605eb3f18，若在图像传播过程中图像信息被稍微改动使用SHA-256 算法编码为 ：44b8ca7c15500098ad801b4c96d4237fa54685594a55924cff8e1a296818b313。

接收方解密Cameraman后的图像再经过使SHA-256算法编码产生的摘要（哈希值）为：29c69af72fd1e6f6b1e7603573a2b750e11a30480516af6ea34fl7ef0caf2021，若在图像传播过程中图像信息被稍微改动使用SHA-256 算法编 码 为 ：345f41ccfl5e39e6f2271155fd0cbd465da0a66151f4273a8a71f7816add2e13。

接收方的摘要值与发送方的摘要值进行匹配，发现有差异，说明图像在传播过程中存在被篡改的行为；没有差异，说明图像传输过程中安全。

# 4 安全性分析

# 4.1 直方图分析

数字图像的加密可以将明文转换成噪声从而隐藏信息。直方图可以表现图像像素的分布频率，描述图像的统计相关性。一般情况下，图像像素灰度的直方图越服从均匀分布，越能有效的抵抗统计分析的攻击。以经典图像Lena为例：加密前图像的灰度直方图如图10所示，加密后的灰度直方图如图11所示。从图可以看出加密后的图像灰度直方图更接近于均匀分布，说明加密后能有效地抵抗统计分析的攻击。

![](images/ef27d4fe7dc42de85369b6b4bba87fac65ca11a0a09d799aba3457a57604b0a9.jpg)  
图10加密前灰度直方

![](images/d3d27c8e63bd3c46996db6507dc014b9887399bc6ccc64504fb2951eb6d8c1cd.jpg)  
图11加密后灰度直方图

# 4.2 相关性分析

明文图像相邻像素之间有很强的相关性，而这些相关性内部存在着明文的部分信息，若被不法分子发现利用，很可能会造成图像的泄露错误!未找到引用源。。优良的加密算法能使得图像的像素之间的相关性变弱。本文从待加密的Lena 图像与加密后的密文图像中分别随机挑选了2000 对相邻的像素点，描绘出他们各个方向的相关性图像如图12所示，计算出各个方向的相关系数如表1所示。从图与表可以看出，加密后的图像相邻像素点的相关性明显降低，使图像更加安全。相关系数的计算公式为：

$$
\begin{array} { l } { \displaystyle r _ { \mathrm { s y } } = \frac { \mathrm { c o v } \big ( u , v \big ) } { \sqrt { D ( u ) } \sqrt { D ( v ) } } } \\ { \displaystyle \mathrm { c o v } ( u , v ) = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \big ( \chi _ { i } - E ( u ) \big ) \big ( y _ { i } - E ( \nu ) \big ) } \\ { \displaystyle D ( u ) = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \big ( u _ { i } - E \big ( u \big ) \big ) ^ { 2 } } \\ { \displaystyle E ( u ) = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } u _ { i } } \end{array}
$$

其中 $\mathrm { ~  ~ N ~ }$ 为任取的相邻像素点的对数，他们的灰度值为$( u _ { i } , \nu _ { i } ) , i = 1 , 2 , \cdots N ,$ 向量 $\boldsymbol { u } = \{ u _ { i } \} , \boldsymbol { \nu } = \{ \nu _ { i } \}$ 。

定 100 s0 so [əx!d 3 axid 0 0 Pixel gray value onlocation(x,y) 50 100 150200250 300 Pixel gray value on location(x,y) 50 100 150 200 250 300 (a)明文水平方向 (b）密文水平方向 品 200 s 福 pxid 0 50 100 150 200250 300 [exd 00 50 100150200250 300 Pixel gray value on location(x,y) Pixel gray value on location(x,y) (c)明文垂直方向 (d)密文垂直方向 ↓300 200 150 100 50 0 50 100150200250 300 0 50 100150200250300 Pixel gray value on location(x,y) Pixel gray value on location(x,y) (e)明文的正对角方向 (f)密文的正对角方向 200 8150 nBA 100 50 50 3 [əxd = 0 0 0 50 100150200250 300 0 50 100 150 200250 300 Pixel gray value on location(x,y) Pixel gray value on location(x,y) (g)明文的反对角方向 (h）密文的反对角方向

表1相关系数  

<html><body><table><tr><td>图像</td><td>水平</td><td>垂直</td><td>正对角</td><td>反对角</td></tr><tr><td>明文</td><td>0.9438</td><td>0.9354</td><td>0.8856</td><td>0.8875</td></tr><tr><td>密文</td><td>0.0220</td><td>0.0272</td><td>-0.0244</td><td>0.0308</td></tr></table></body></html>

# 4.3信息熵计算

信息熵反应图像不确定性，一般情况下，算法的加密效果越好，图像的信息熵越大，图像的信息量和随机性也越大。几个文献加密经典Lena图像的信息熵结果如表2所示。信息熵的具体公式如下：

$$
H = - \sum _ { i = 0 } ^ { L } p \left( i \right) \log 2 p ( i )
$$

其中 $L$ 为图像灰度等级数，P(i)表示灰度值 $i$ 出现的概率。

对于 $\scriptstyle L = 2 5 6$ 的灰度图像，信息熵H理论值为8.由表中数据可以发现，虽然文献[1]和文献[3]以及本算法的信息熵都很接近，但本算法加密后的Lena图像的信息熵更接近于8，说明本算法更能有效地抵抗数据攻击错误!未找到引用源。

表2信息熵结果  

<html><body><table><tr><td>图像</td><td>信息熵值</td></tr><tr><td>Lena 明文图像</td><td>7.3804</td></tr><tr><td>本算法的密文图像</td><td>7.9994</td></tr><tr><td>文献[1]的密文图像</td><td>7.9968</td></tr><tr><td>文献[6]的密文图像</td><td>7.9897</td></tr></table></body></html>

# 4.4 密钥空间分析

密钥空间是指所有合法密钥的集合，加密算法越好，则相应的密钥空间越大错误！未规到引用源。本文密钥 $K = \{ x _ { 0 } , y _ { 0 } , z _ { 0 } , w _ { 0 } , r _ { 1 } , r _ { 2 } \}$ 其中， $x _ { 0 } \in \left( - 4 0 , 4 0 \right) \quad , \qquad y _ { 0 } \in \left( - 4 0 , 4 0 \right) \ , \ : \mathrm { z } _ { 0 } \in \left( 1 , 8 1 \right)$ ，$w _ { 0 } \in ( - 2 5 0 , 2 5 0 )$ ，其中 $x _ { 0 } , \ y _ { 0 }$ 和 $z _ { 0 }$ 的步长为 $1 0 ^ { - 1 3 }$ ， $w _ { 0 }$ 的步长为$1 0 ^ { - 1 2 }$ ， $r _ { \mathrm { i } }$ 和 $r _ { 2 }$ 为0\~255的整数，可得密钥空间大约为$1 . 6 7 7 7 ^ { * } 1 0 ^ { 6 4 }$ ,约为 213 比特,而文献[2]的密钥空间只有 $( 1 0 ^ { 1 6 } ) ^ { 2 }$ ，虽然本算法的密钥空间大，但平均加密速度在 $1 4 { \sim } 2 0 \mathrm { ~ s ~ }$ 之间，而文献[2]的平均加密速度在10秒左右，文献[4]的平均加密速度在30秒以上。综合以上分析，在平均加密速度稍快的情况下，本算法的密钥空间更大，更能抵抗暴力攻击。

# 4.5 差分攻击分析

像素改变率(NPCR)和归一化平均改变度(UACI)是衡量图像加密算法抵抗差分攻击能力的重要指标错误!未找到引用源。差分攻击是指对明文稍微改变，再进行加密，比较相应前后密文的差异，若前后密文相差较大，则说明该算法有较强的的抗明文攻击和差分攻击的能力。本算法的重复100次试验的NPCR和UACI的平均值值如表3所示。NPCR和UACI的具体公式如下：

$$
N P C R  ( P _ { 1 } , P _ { 2 } ) = \frac { 1 } { M N } \sum _ { i = 1 } ^ { M } \sum _ { j = 1 } ^ { N } \lvert S i g n ( P _ { 1 } ( i , j ) - P _ { 2 } ( i , j ) ) \rvert * 1 0 0 \%
$$

其中

$$
S i g n ( x ) = \left\{ \begin{array} { l l } { 1 , x > 0 } \\ { 0 , x = 0 } \\ { - 1 , x < 0 } \end{array} \right.
$$

$$
U A C I ( P _ { 1 } , P _ { 2 } ) = \frac { 1 } { M N } { \sum _ { i } ^ { M } \sum _ { j } ^ { N } \frac { \left| { P _ { 1 } ( i , j ) - P _ { 2 } ( i , j ) } \right| } { { 2 5 5 - 0 } } } * 1 0 0 \%
$$

其中:M 和 $\mathrm { ~ N ~ }$ 分别是图像的长度和宽度， $P _ { 1 } ( i , j )$ 和 $P _ { 2 } ( i , j )$ 分别指明文改变前后的密文像素值。

表3NPCR 和UACI的测试结果  
$\%$   

<html><body><table><tr><td>指标</td><td>Lena 密文</td><td>理论值</td></tr><tr><td>NPCR</td><td>99.6085</td><td>99.6094</td></tr><tr><td>UACI</td><td>33.4576</td><td>33.4635</td></tr></table></body></html>

由表3可知本算法加密像素稍微改变的明文，密文相差很大，NPCR和UACI的值很接近它们的理论值，说明该算法有较好的抗明文攻击与差分攻击的能力。

# 5 结束语

本文提出了一种基于明文相关的混沌映射与SHA-256算法的数字图像的加密与监测。首先对待加密图像的灰度图像使用 SHA-256 算法编码产生的哈希值作为摘要来监测密文图像在传输过程中是否被篡改。使用两次不同的扩散方法以及明文相关的置乱算法对数字图像就行加密，Lorenz混沌映射产生对应的密码。实验结果表明，该算法不仅密钥空间大，而且能够有效的抵抗暴力攻击、明文攻击、统计攻击与差分攻击，从而更好的保障了数字图像的安全传输。

# 参考文献：

[1]韩栋，王春华，肖敏．基于混沌映射和二次剩余密码的彩色图像加密方 法[J].计算机应用研究，2018,35(9):2757-2761.(Han Dong,Wang Chunhua,Xiao Min. Color image encryption method based on chaotic map and quadratic residue cryptosystems [J//OL].Application Research of Computers,2018,35(9): 2757-2761.)

[2]李春虎，罗广春，李春豹．基于斜帐蓬混沌映射和 Arnold 变换的图像 加密方案[J/OL].计算机应用研究,2018,35(11).(2017-11-10)[2017- 11-10].http://www. arocmag. com/article/02-2018-11-028.html.(Li Chunhu, Luo Guangchun,Li Chunbao. Image encryption scheme based on skew tent chaotic map and Arnold transformation [J/OL].Application Research of Computers，2018,35(11）．(2017-11-10)[2017-11-10]. http://www.arocmag.com/article/02-2018-11-028.html.)

[3]蒋君莉，张雪锋．基于多混沌系统的彩色图像加密方法[J].计算机应 用研究，2014,31(10):3131-3136.(Jiang Junli,Zhang Xuefeng.Color image encryption method based on chaotic system [J].Application Research of Computers,2014,31(10): 3131-3136.)

[4]孙力，黄正谦，梁立．基于复合混沌映射与连续扩散的图像加密算法 [J]．计算机工程与设计，2017,38(12):3374-3379.(Sun li,Huang Zhengqian,Liang Li.Image encryption algorithm based on composite chaotic maps and continuous diffusion [J]. Computer Engineering and Design,2017,38(12):3374-3379.)

[5]闫兵，柏森，刘博文，等．基于交叉混沌映射的小波域图像加密算法 [J].计算机应用与研究,2018,35(6):1797-1799,1811.(Yan Bing,Bai Sen, Liu Bowen, Yang Yi, Guo Hui.Algorithm of image encryption in wavelet domain based on cross chaotic map [J].Application Research of Computers, 2018,35 (6):1797-1799,1811.)

[6]张勋才，刘奕杉，崔光照．基于DNA 编码和超混沌系统的图像加密算法[J/OL].计算机应用研究，2019,36(4).(2018-02-07)[2018-02-07].http://www.arocmag.com/article/02-2019-04-034.html.(Zhang Xuncai,

Liu Yishan,Cui Guangzhao.Image encryption algorithm based on DNA encoding and hyper-chaotic system [J/OL].Application Research of Computers,2019,36(4). (2018-02-07)[2018-02-07]. htp://www.arocmag. com/article/02-2019-04-034.html.)

[7]柴秀丽，甘志华．基于超混沌系统的位级自适应彩色图像加密新算法 [J]．计算机科学,2016,43(4):133-139.(Chai Xiuli,Gan Zhihua.A novel bit level adaptive color image encryption algorithm based on hyper chaotic system [J].Computer Science,2016,43 (4): 133-139)

[8]赵佳星，张雪锋．基于组合混沌系统的时空彩色图像加密算法[J].计 算机工程与设计,2016,37(9):2354-2360.(Zhao Jiaxing,Zhang Xuefeng. Spatiotemporal color image encryption method based on combined chaotic system [J].Computer Engineering and Design,2016,37(9): 2354-2360.)

[9]张勇．混沌数字图像加密[M].北京．清华大学出版社.2016:105. (Zhang Yong.Chaotic digital image cryptosystem [M].Beijing.tsinghua university press.2016:105.)

[10]何润民，马俊.SHA-256算法的安全性分析[J]．电子设计工程，2014,22 (3):31-33.(He Runmin,Ma Jun.Analysis safety of SHA-256 algorithm[J].Electronic Design Engineering,2014,22 (3): 31-33.)

[11]王宏达．一种基于混沌系统的新型图像加密算法[J]．光学技术,2017, 43 (3):260-266.(Wang Hongda.A novel image encryption algorithm based on chaotic system[J].Optical Technique,2017,43 (3): 260-266.)

[12] Zhu Hegui,Zhao Cheng,Zhang Xiangde.A novel image encryptioncompression scheme using hyper-chaos and Chinese remainder theorem [J]. Signal Processing: Image Communication,2013,28 (6): 670-680.

[13]朱淑芹，李俊青，葛广英．基于一个新的五维离散混沌的快速图像加密 算法[J].计算机科学,2016,s2 (43): 411-416.(Zhu Shuqin,Li Junqing, Ge Guangying.Fast image encryption algorithm based on novel five dimensional discrete chaos.[J]. Computer Science,2016,s2 (43): 411-416.)

[14] Zhang Miao,Tong Xiaojun.A new algorithm of image compression and encryption based on spatiotemporal cross chaotic system [J].Multimed Tools Appl,2014,71: 1-25.