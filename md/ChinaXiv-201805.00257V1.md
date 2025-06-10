# 一种局部二值模式图像特征点匹配算法

王强1,²，李柏林1，罗建桥1，陈小艳³

(1．西南交通大学 机械工程学院，成都 610031;2．成都工业学院 机械工程学院，成都 611730;3．成都航空职业技术学院航空制造工程系，成都 610100)

摘要：针对图像匹配问题进行了研究，提出了一种改进BRIEF算法的特征点匹配算法。该算法利用随机点与特征点之间的差分大小和差分幅值关系来生成特征点描述算子。针对BRIEF对噪声敏感问题，因为小的像素幅值差分更易受到噪声影响，为了抑制噪声，通过设置小像素差分阈值，差分在阈值内的设置为不确定位，然后通过其邻域均值来决定不确定位的值。特征点匹配使用描述算子之间的汉明距离进行比较来完成。实验与BRIEF和ORB算法进行了比较，证明该算子具有更高的判别性，计算简单且具有很好的噪声抑制性能，运行速度快，匹配准确率更高。

关键词：BRIEF；ORB；特征点匹配算子；局部二值模式中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2017.07.0890

# Local binary pattern image feature point matching algorithm

Wang Qiang1,², Li Bailin1, Luo Jianqiao1, Chen Xiaoyan3 (1.SchoolofMechanicalEngineering,SouthwestJiaotongUniversityChengdu 61o31,China;2.ColegeofMechanical Engineering，Chengdu Technological University，Chengdu 611730,China;3.Dept.ofAviation Manfacturing Engineering, Chengdu Aeronautic Polytechnic,Chengdu 6101oo,China)

Abstract: This paperresearched Image matchingissue and proposed afeature point matchingalgorithmto improve the BRIEF algorithm.The proposed algorithm generatedthe feature pointdescriptionoperatoraccording to thediferencesigns and the diference magnitudesrelation between therandom pointandthe featurepoint.BRIEFwas sensitiveto noise because thesmal diference magnitudeis more susceptible tothenoise.Tosolvethis problem,This paperdeterminedasmallpixeldifference thresholdbythe neighborhood mean value ofthe BRIEF.Comparing the Hamming distance between descriptions realizes the feature points matching.Compared with BRIEF and ORB algorithm,the experiments proved thatthe operator has higher discriminant, simple calculation and good noise suppression performance.And the matching accuracy is higher.

Key Words:BRIEF;ORB; feature point matching operator; local binary pattern

# 0 引言

计算机视觉技术已经广泛应用在目标检测[1]、人脸识别[2\~4]、图像分类[5]、场景识别[]、运动物体跟踪[7]、纹理分类[8\~12]等方面。其中，利用图像特征点进行匹配是计算机视觉技术中比较常用的一种技术。随着智能设备的发展，图像匹配算法的要求主要体现在稳定性、抗噪声以及低内存消耗和高运算速度，因此对特征点匹配算子提出了更高的要求。

图像特征点匹配算子的唯一性是基于特征点的图像匹配的关键。为了让描述算子更加稳定，通常采用更高的维度和更复杂的描述方式。高维的描述算子可以增加其判别性，但是计算相对复杂，且时间复杂度较高。BRIEF(binaryrobust independentelementaryfeatures)[13]算法对特征点描述给出了一种简单的方法。在此之前，Moravec[14提出了基于特征点的图像匹配方法，Harris 等人[15]提出了Harris角点检测方法应用于图像匹配，但是匹配效果不是很理想。SIFT[6算法采用了一种复杂的描述方式，在特征点 $1 6 \times 1 6$ 邻域内，利用梯度方向直方图进行描述，分别计算特征点邻域每个 $4 \times 4$ 小块8个方向的梯度方向直方图，得到128维向量，虽然算法比较稳定，但是效率较低。利用 PCA[17]或LDA[18]方法能够部分提高速度。SURF[19-21]算法对SIFT 进行了改进，采用Haar小波检测图像在水平和垂直方向的响应得到64维向量对特征点进行描述，在速度上有一定提升。后来有人又提出了BRISK[22]和FREAK[23]算法，在速度上有很大的提升，但是匹配准确率不够。BRIEF算法在邻域内选择随机点对，通过比较点对像素大小得到二进制串作为特征点描述算子，通过异或运算在时间上大大提高，但是单个像素之间比较对噪声敏感。 $\mathrm { O R B } ^ { [ 2 4 ] }$ 算法对BRIEF进行了改进，以随机点为中心，取 $S \times S$ 子窗口像素之和进行比较得到二进制编码，能够部分抑制噪声。ORB和BRIEF算法计算速度快。但是只考虑了特征点邻域内随机点的分布，而没有考虑邻域像素与特征点之间的关系。此外，BRIEF算法容易受到噪声影响。ORB算子通过均值滤波抑制了部分噪声，但是为了解决旋转不变性问题，计算特征点的主方向导致描述算子的相关性增加，从而判别性下降。本文提出利用随机点与特征点之间的关系来描述特征点的属性。此外，图像如果受到噪声影响，小的像素差分幅值影响更加明显，由此，本文根据差分幅值大小设置阈值单独处理这种情况，降低了噪声。

# 1 BRIEF和ORB简介及问题分析

# 1.1 BRIEF算法简介

BRIEF算法用于特征点匹配，采用特征点邻域随机点对进行比较，得到二进制串，通过汉明距离判断两个特征点是否匹配。在特征点邻域内取 $S \times S$ 大小的邻域 $P$ ，定义测试函数 $\boldsymbol { \tau }$

$$
\tau ( p ; x , y ) : = \left\{ { 1 \atop 0 } \right. \overset { i f } { p ( x ) } \geq p ( y )
$$

$p ( x )$ 和 $p ( y )$ 代表点 $x$ 和点 $y$ 位置的像素值。如果取 $n _ { d }$ 维二进制串进行特征点描述,则BRIEF的描述算子可以表示为

$$
f _ { n _ { d } } ( \boldsymbol { p } ) : = \sum _ { 1 \le i \le n _ { d } } 2 ^ { i - 1 } \tau ( \boldsymbol { p } ; \boldsymbol { x } _ { i } , \boldsymbol { y } _ { i } )
$$

其中： $n _ { { \scriptscriptstyle d } } = 1 2 8 , 2 5 6 , 5 1 2$ ，代表二进制串的位数，特征点匹配采用汉明距离进行判断，最小的汉明距离认为是匹配的点对。随机点的选择服从高斯分布，X和 $\mathrm { \Delta Y }$ 服从各向同性高斯分布（204 $( x , y ) \sim G a u s s i a n ( 0 , \frac { 1 } { 2 5 } S ^ { 2 } )$ 。BIREF 算法速度很快，但是对噪声敏感，在得到描述算子之前需要先进行高斯滤波。

# 1.2 ORB算法简介

ORB算法对BRIEF进行了改进，主要是解决BRIEF算法对噪声敏感和旋转不变性问题。其点对选择方式和BRIEF一样。为了解决噪声敏感的问题，采用了图像积分的方法，本质上是对图像进行了均值滤波。为了解决旋转不变性问题，通过计算特征点的主方向，再根据主方向来生成描述算子。但是由于主方向会发生变化，随机点对的相关性会比较大，从而降低描述子的判别性。

# 1.3问题分析

相比较其他基于特征点的匹配算法，BRIEF和ORB具有速度快等优点。但是其缺陷也很明显，首先是噪声敏感问题不能很好地解决；其次特征点描述算子只考虑了邻域内随机点之间的差分大小关系，没有考虑差分幅值的关系，特征点与邻域的差分分布关系表达不够完整，所以得到的描述算子判别性不高。

# 2 提出的方法

# 2.1理论分析

Ojala 等人[25\~26]提出，图像的纹理特征可以通过中心像素与邻域像素的差分关系表示，由此提出了LBP编码算法。如果将中心像素看成是一个特征点，则LBP算法可以认为是关于特征点的描述算子。该描述算子利用了邻域像素和中心像素的差分分布关系。如果描述算子表达的差分关系足够完整，得到的描述算子将具有更高的判别性。邻域像素和中心像素的差分关系可以由差分大小和差分幅值完全描述。差分大小关系可以表达大部分原始信息，LBP或BRIEF只利用了差分大小关系。但是差分幅值也可以表达部分原始信息[8]，显然这部分信息对提高描述算子的判别性也是有用的。设 $N \times N$ 邻域中心像素为 $g _ { c }$ 邻域像素为 $g _ { p } ( 0 , 1 , \cdots , p - 1 )$ ，定义 $g _ { p }$ 与 $g _ { c }$ 的差分 $z _ { p } = g _ { p } - g _ { c }$ ，$z _ { p }$ 可以分解为差分大小和幅值两部分

$$
z _ { p } = b _ { p } * m _ { p }
$$

其中：

$$
b _ { p } = \left\{ { \begin{array} { l l } { 1 } & { \ z _ { p } \geq 0 } \\ { - 1 } & { \ z _ { p } < 0 } \end{array} } \right.
$$

$b _ { p }$ 代表像素差分大小关系, $m _ { p }$ 代表像素差分幅值信息。Maitre[27]已经证明,像素之间的差分服从高斯分布或拉普拉斯分布:

$$
f ( x ) = \exp ( - \vert x \vert / \sigma ) / \sigma
$$

而像素差分大小关系 $b _ { p }$ 服从伯努利分布：

$$
f ( n ) = a ^ { \frac { n + 1 } { 2 } } ( 1 - a ) ^ { \frac { 1 - n } { 2 } } \circ
$$

其中： $a = 0 . 5 ~ , ~ n \in \{ - 1 , 1 \} ~ \circ$ （20

如果分别从 $b _ { p }$ 和 $m _ { p }$ 重建差分信号 $z _ { p }$ ，当只采用幅值信息重建差分信号 $z _ { p }$ ，则

$$
z _ { p m } ^ { ^ { \mathrm { ~ \tiny ~ \cdot ~ } } } = m _ { _ p } ^ { ^ { \mathrm { ~ \tiny ~ * ~ } } b _ { _ p } ^ { ^ { \mathrm { ~ \tiny ~ * ~ } } } }
$$

$b _ { p } ^ { ^ { \phantom { \dagger } } }$ 服从伯努利分布， $z _ { p }$ 服从拉普拉斯分布,所以 $m _ { p }$ 将服从单边拉普拉斯分布:

$$
f ( x ) = \exp ( - x / \sigma ) / \sigma , x > 0 \mathrm { ~ \circ ~ }
$$

如果只使用像素差分大小关系重建原始信号，则

$$
{ z _ { p b } } ^ { \prime } = { m _ { p } } ^ { \prime } * b _ { p }
$$

$m _ { p }$ 表示幅值部分的均值。重建误差分别由 $E _ { b }$ 和 $E _ { { \scriptscriptstyle m } }$ 表示为

$$
\begin{array} { c } { E _ { b } = E [ ( z _ { p } - z _ { p b } ) ^ { 2 } ] } \\ { E _ { m } = E [ ( z _ { p } - z _ { p m } ) ^ { 2 } ] } \end{array}
$$

由此可以得到 $E _ { b } = \sigma ^ { 2 }$ 而 $E _ { { \scriptscriptstyle m } } = 4 \sigma ^ { 2 }$ [8]。可以看出，信号之间的差分幅值信息能够表示原始图像 $20 \%$ 的信息。如果能够利用差分幅值信息，将大大提高BRIEF的判别性。

# 2.2 方法

为了更完整地表达特征点与邻域的差分关系，提高描述算子的判别性，本文采用差分大小和差分幅值联合生成特征点描述算子。同时，根据图像之间的差分服从高斯分布或拉普拉斯分布的特点[27]，在特征点邻域内采用高斯分布生成随机点，利用随机点和特征点之间的关系来生成特征点的二进制描述算子。图1是整个特征点描述算子生成示意图。其中图1(a)表示特征点附近 $3 \times 3$ 邻域；(b)表示邻域像素与中心像素的差分；(c)表示差分信号大小关系，其中“-1”在实际编码时用“0”代替；(d)表示差分幅值大小。

![](images/df29fbe4e00269f542e0258d5e773dd0abcbe7e3395ec2debdbe8de1ab0f99a6.jpg)  
图1差分信号关系和差分幅值大小编码示意

设邻域大小为 $N \times N$ ，为了生成特征点描述算子，首先根据高斯分布，选取以特征点为中心的 $N \times N$ 邻域内 $K$ 个点，设特征点像素值 $f _ { c }$ ，记特征点与邻域内的像素值联合分布为

$$
T = t ( f _ { c } , f _ { 1 } , f _ { 2 } , \cdot \cdot \cdot , f _ { k } )
$$

为了满足灰度不变性，让邻域像素减去中心像素的值，得到式(13)。

$$
T = t ( f _ { 1 } - f _ { c } , f _ { 2 } - f _ { c } , \cdot \cdot \cdot , f _ { k } - f _ { c } )
$$

定义符号函数 $s ( x )$ ：

$$
s ( x ) = \left\{ { \begin{array} { l l } { 1 } & { \ x \geq 0 } \\ { 0 } & { \ x < 0 } \end{array} } \right.
$$

其中： $s ( x ) = s ( f _ { k } - f _ { c } )$ ，如果只考虑差分信号大小关系，则得到式(15)

$$
T _ { s } = t ( s ( f _ { 1 } - f _ { c } ) , s ( f _ { 2 } - f _ { c } ) , \cdots , s ( f _ { k } - f _ { c } ) )
$$

式（15）是邻域像素与特征点差分大小关系的纹理描述算子，具有很高的判别性[25\~26]，但是没有差分幅值信息，导致丢失了部分邻域像素和特征点之间的关联信息。为了保证信息不丢失，再进行差分幅值编码。由于幅值大小不能够直接编码成4 $0 ^ { \prime \prime }$ 或 $" 1 "$ ，所以设置每个邻域像素与特征点差分幅值之和的均值作为阈值，将每个幅值大小与均值进行比较得到" $0$ "或“1”的编码，得到式(16)。

$$
T _ { m } = t ( s ( m _ { 1 } - m _ { m } ) , s ( m _ { 2 } - m _ { m } ) , . . . , s ( m _ { k } - m _ { m } ) )
$$

其中： $m _ { k }$ 表示邻域像素与特征点的幅值大小； $m _ { { \scriptscriptstyle m } }$ 表示幅值的均值； $T _ { { \scriptscriptstyle m } }$ 即幅值的二进制编码结果，将 $T _ { s }$ 和 $T _ { { \scriptscriptstyle m } }$ 联合即得到特征点的二进制描述算子。

# 2.3噪声抑制

由于单个像素进行比较容易受到噪声影响，为了抑制噪声，采用局部邻域均值代替特征点作为阈值，从而消除部分噪声，

设邻域像素均值为fm。

$$
f _ { m } = \frac { 1 } { k + 1 } ( \sum _ { i = 1 } ^ { k } f _ { i } + f _ { c } )
$$

计算特征点邻域像素与均值的差分。

$$
T = t ( f _ { 1 } - f _ { m } , f _ { 2 } - f _ { m } , \cdot \cdot \cdot , f _ { k } - f _ { m } )
$$

采用邻域均值作为阈值进行差分计算，可以抑制部分噪声。文献[2]提出小的像素差分幅值更容易受到噪声影响。为了进一步抑制噪声，设定阈值 $\mathbf { \Phi } _ { t }$ ，将邻域像素与均值的差分幅值在阈值 $\mathbf { \Phi } _ { t }$ 范围内的编码设置为不确定位 $\boldsymbol { x }$ 。由此修改符号函数为

$$
s ^ { \prime } ( x ) = \left\{ { X \atop N } \right. \quad \left| x \right| \leq t
$$

不确定位 $X$ 取 ${ } ^ { \mathfrak { s } } 0 ^ { \mathfrak { s } }$ 或 $^ { \dag } { } ^ { \left. \begin{array} { r l } \end{array} \right. } ^ { \left. \begin{array} { r l } \end{array} \right. }$ ，具体取值由该像素的邻域决定。设点 $f _ { p }$ 为不确定点，取 $f _ { p }$ 点附近 $3 \times 3$ 邻域共9个点 $f _ { p i }$ ，计算平均值 $f _ { p m }$ ，由 $f _ { p }$ 的邻域点共同决定 $f _ { p }$ 的值。

$$
f _ { p m } = \frac { 1 } { 9 } \sum _ { i = 1 } ^ { 9 } f _ { p i }
$$

用 $f _ { p m }$ 代替 $f _ { p }$ ，然后再与 $f _ { m }$ 进行比较得到 $X$ 的值。相当于进行了局部均值滤波。由此消除小像素差异的噪声，得到差分大小关系的二进制编码结果，如式(21)所示。

$$
f _ { k d } ( p ) { : = } \sum _ { 1 \leq i \leq k d } 2 ^ { i - 1 } s ^ { * } ( x )
$$

其中： $k d$ 代表 $N \times N$ 邻域的 $k$ 维点。

同理可以得到差分幅值的二进制编码结果。将两个编码结果进行线性连接得到整个抗噪声的二进制编码。

采用高斯分布选择邻域内随机点与特征点进行比较，并且不仅仅利用差分大小信号，同时利用了差分幅值信号，从而更加准确地描述了特征点的属性。将邻域像素的均值作为阈值进行比较，排除了部分噪声影响，对于小的像素幅值差异引起的噪声，采用不确定位的编码方式，通过计算 $3 { \times } 3$ 邻域均值代替邻域像素的值与均值进行比较，进一步提高了描述算子的抗噪声能力。其算法描述如下：

提出的特征点匹配算子

1．利用高斯函数生成邻域内随机点的位置；  
2．for 循环处理每个特征点；  
2.1.计算特征点 $N \times N$ 邻域的均值 $f _ { m }$ ：  
2.2.设置阈值 $t$ ，比较随机点 $f _ { p }$ 与均值 $f _ { m }$ 的大小if $f _ { p } - f _ { m } > t$ then bitset $\scriptstyle = 1$ （204号  
else if $f _ { p } - f _ { m } < - t$ then bitset $\scriptstyle = \varnothing$   
else if $\left| f _ { p } - f _ { m } \right| \leq t$ then  
计算 $f _ { p }$ 的 $3 \times 3$ 邻域均值 $f _ { p m }$   
if $f _ { p m } - f _ { m } \ge 0$ then bitset $^ { = 1 }$ （204号  
else bitset $\scriptstyle = 0$   
得到关于差分信号大小的二进制编码 $T _ { s }$   
2.3．计算每个随机点与特征点的幅值 $m _ { i }$ ：2.4 设置阈值t，计算幅值的均值 $m _ { { \scriptscriptstyle m } }$ ，比较 $m _ { i }$ 与 $m _ { { \scriptscriptstyle m } }$ 大小，与步骤2.2类似，得到关于幅值的二进制编码 $T _ { { \scriptscriptstyle m } }$ ：  
3.将 $T _ { s }$ 与 $T _ { { \scriptscriptstyle m } }$ 结合，得到特征点的描述算子。

# 3 实验结果

为了验证提出的特征点匹配算法，实验采用标准的图像匹配基准数据集进行测试。实验比较了BRIEF和ORB算法。图2是五个公开可用的测试图像序列。每个图像序列6张图像，分别表示视觉变化(wall)、图像模糊(trees）、光照变化(light)、压缩图像(JPG)和旋转加尺度变换(boat)。小像素差异阈值的选择与噪声的强弱有关，如果噪声比较小，阈值选择通常在2\~5。如果噪声很强，阈值相应增大，这样会增加部分时间开销，如果图像本身的噪声很强，在进行特征点检测阶段会进行降噪声的预处理，所以特征点描述阶段的阈值一般2\~5范围是比较合适的。实验中选择的阈值为 $t = 5$ 。

![](images/b8676fcd8259070128c95e72d2b5b03c6692aed46d380bab24e0e2edeaf92e59.jpg)  
图2测试图像集

图3是选择不同邻域大小的匹配结果示意。以图2(b)图像序列6张图像为例，第一张图像分别与后面五张图像匹配。N表示以特征点为中心的邻域大小。通常邻域选择越大，选择的随机点越多，匹配越准确， $\Nu { = } 1 7$ 以后，邻域增加对匹配率的结果影响不是很大，而且邻域越大计算时间越多，对于匹配要求比较高的情况下通常选择 $\mathrm { N } { = } 1 7$ 的邻域已经足够，如果想进一步提高时间，可以选择更小的邻域，但是有可能导致匹配率下降。

![](images/434af66274cbd3d2b193a1d480ccabfccc9bc2df91113571a6539ddffadd374a.jpg)  
图3不同邻域大小的匹配结果

实验从两个方面进行比较：同一序列图像分别与第一张图像分别进行匹配；对每个序列第二张图像分别添加不同的高斯噪声和椒盐噪声再与第一张图像进行匹配。实验采用最直观的指标衡量匹配结果，即匹配准确率。实验编码采用 $\cot +$ 结合opencv2.4.9 实现。邻域大小 $\mathrm { N } { = } 1 7$ ，小像素差异阈值选择 $t = 5$ ，特征点采用CenSurE特征点。表1\~5显示了原始图像序列第一张图像分别与剩下的五张图像的匹配结果。其中BRIEF和ORB算法选择的是512位的描述算子。从图中可以看出，对于光照、视觉、模糊和压缩变化的图像，本文提出的算法匹配率最高，对于旋转变化和尺度变化的图像，如果旋转和尺度变化不大，本文算法要好于ORB算法，如果增大旋转角度和尺度，本文算法略低于ORB 算法。由于ORB 算法增加了主方向方向的计算，所以旋转不变性较好。但是增加主方向会导致随机点对选择相关性比较大，从而描述算子的判别性有所下降，这一点从表1\~4可以看出。现实中很多图像旋转和尺度变化不会太大，所以本文算法是适用的。

表1Wall图像匹配率 $\%$   

<html><body><table><tr><td>方法</td><td>1|2</td><td>13</td><td>14</td><td>1|5</td><td>16</td></tr><tr><td>ORB</td><td>93.8</td><td>92.5</td><td>90.3</td><td>70.7</td><td>57.6</td></tr><tr><td>BRIEF</td><td>95.1</td><td>93.4</td><td>93.1</td><td>75.8</td><td>60.9</td></tr><tr><td>本文方法</td><td>95.4</td><td>94.8</td><td>94.4</td><td>77.2</td><td>62.6</td></tr></table></body></html>

表2Trees 图像匹配率/%  

<html><body><table><tr><td>方法</td><td>1|2</td><td>13</td><td>14</td><td>1|5</td><td>16</td></tr><tr><td>ORB</td><td>92.2</td><td>90.7</td><td>88.2</td><td>73.4</td><td>57.1</td></tr><tr><td>BRIEF</td><td>95.1</td><td>93.1</td><td>91.5</td><td>75.8</td><td>62.4</td></tr><tr><td>本文方法</td><td>96.7</td><td>94.5</td><td>92.6</td><td>76.3</td><td>64.9</td></tr></table></body></html>

表3Light图像匹配率/%  

<html><body><table><tr><td>方法</td><td>1|2</td><td>13</td><td>14</td><td>1|5</td><td>16</td></tr><tr><td>ORB</td><td>92.1</td><td>90.3</td><td>89.8</td><td>88.7</td><td>85.7</td></tr><tr><td>BRIEF</td><td>94.2</td><td>92.5</td><td>91.4</td><td>91.3</td><td>87.6</td></tr><tr><td>本文方法</td><td>94.5</td><td>92.6</td><td>92.3</td><td>92.5</td><td>88.3</td></tr></table></body></html>

表4JPG 图像匹配率/%  

<html><body><table><tr><td>方法</td><td>1|2</td><td>13</td><td>14</td><td>1|5</td><td>16</td></tr><tr><td>ORB</td><td>92.7</td><td>90.3</td><td>88.2</td><td>73.9</td><td>57.2</td></tr><tr><td>BRIEF</td><td>96.1</td><td>93.3</td><td>91.7</td><td>75.4</td><td>62.9</td></tr><tr><td>本文方法</td><td>98.8</td><td>94.7</td><td>92.5</td><td>76.8</td><td>64.3</td></tr></table></body></html>

表5Boat图像匹配率 $\%$   

<html><body><table><tr><td>方法</td><td>1|2</td><td>13</td><td>14</td><td>1|5</td><td>16</td></tr><tr><td>ORB</td><td>91.6</td><td>90.8</td><td>86.1</td><td>70.3</td><td>55.8</td></tr><tr><td>BRIEF</td><td>94.3</td><td>88.3</td><td>84.9</td><td>65.9</td><td>52.1</td></tr><tr><td>本文方法</td><td>95.2</td><td>89.5</td><td>85.6</td><td>68.5</td><td>53.7</td></tr></table></body></html>

图4是添加了高斯噪声的图像示意，选择trees图像作为示例。高斯噪声是一种最常见的噪声。根据标准偏差 $\sigma$ 的大小，选择了四种 $\sigma$ 值进行实验，分别是 $\sigma ^ { - 0 . 0 5 }$ ，0.10，0.15，0.2。随着 $\sigma$ 值的增大，图像越模糊，匹配的准确率越低。图5是添加椒盐噪声的图像结果，同样选择Trees 图像作为示例。椒盐噪声是另一种比较常见的图像噪声。选择的椒盐噪声的大小分别是 $p = 0 . 0 5 , \ 0 . 1 0 , \ 0 . 1 5 , \ 0 . 2 0 _ { \mathrm { c } }$ ，与高斯噪声类似，当图像噪声增大后，匹配率也相应降低，当噪声很大时，用肉眼已经无法观察图像的细节特征。

![](images/c5726f30a4705f3cd1c54ff5cfbf4560c23766956a341b162666829d8e46f383.jpg)  
图4添加高斯噪声的图像

表6\~10是添加了高斯噪声后的匹配结果。表11\~15是添加了椒盐噪声后的匹配结果。随着噪声的增加，匹配率在下降，但是不管添加哪种噪声，本文算法都要好于BRIEF和ORB算法。BRIEF 算法在计算描述算子之前进行了高斯滤波，所以有较强的噪声抑制能力，其匹配效果要好于ORB 算法。而ORB算法采用局部邻域像素之和进行描述算子计算。本质上是利用均值滤波代替了高斯滤波，通过图像积分提高了算子的计算速度，同时有一定的噪声抑制能够，但是主方向的计算导致随机点对相关性增加从而导致描述算子判别性下降的问题没有很好解决，从而匹配率有所下降。

表6Wall图像添加高斯噪声匹配率 $/ \%$   

<html><body><table><tr><td>方法</td><td>q=0.05</td><td>9=0.10</td><td>q=0.15</td><td>9=0.20</td></tr><tr><td>ORB</td><td>92.1</td><td>85.7</td><td>80.3</td><td>73.6</td></tr><tr><td>BRIEF</td><td>93.5</td><td>91.7</td><td>90.5</td><td>88.3</td></tr><tr><td>本文方法</td><td>94.3</td><td>93.5</td><td>92.8</td><td>89.4</td></tr><tr><td>表7</td><td>Trees 图像高斯噪声g=0.10 匹配率/%</td><td></td><td></td><td></td></tr><tr><td>方法</td><td>q= 0.05</td><td>q=0.10</td><td>q =0.15</td><td>9=0.20</td></tr><tr><td>ORB</td><td>93.4</td><td>86.9</td><td>81.8</td><td>76.5</td></tr><tr><td>BRIEF</td><td>95.3</td><td>90.2</td><td>87.4</td><td>84.8</td></tr><tr><td>本文方法</td><td>95.7</td><td>91.6</td><td>89.3</td><td>87.3</td></tr><tr><td>表8</td><td>Light 图像高斯噪声σ=0.15匹配率/%</td><td></td><td></td><td></td></tr><tr><td>方法</td><td>q=0.05</td><td>g=0.10</td><td>q=0.15</td><td>9 = 0.20</td></tr><tr><td>ORB</td><td>93.5</td><td>90.2</td><td>89.8</td><td>87.3</td></tr><tr><td>BRIEF</td><td>94.3</td><td>91.1</td><td>91.4</td><td>89.9</td></tr><tr><td>本文方法</td><td>95.8</td><td>92.6</td><td>91.6</td><td>90.3</td></tr><tr><td>表9</td><td></td><td></td><td>JPG 图像高斯噪声g=0.20 匹配率/%</td><td></td></tr><tr><td>方法</td><td>9=0.05</td><td>9=0.10</td><td>q=0.15</td><td>9=0.20</td></tr><tr><td>ORB</td><td>95.4</td><td>94.1</td><td>93.7</td><td>91.2</td></tr><tr><td>BRIEF</td><td>96.1</td><td>95.7</td><td>95.2</td><td>94.2</td></tr><tr><td>本文方法</td><td>97.7</td><td>96.4</td><td>95.5</td><td>95.1</td></tr></table></body></html>

表10Boat 图像高斯噪声 $\sigma ^ { - 0 . 2 0 }$ 匹配率 $\%$   

<html><body><table><tr><td>方法</td><td>q =0.05</td><td>q=0.10</td><td>g = 0.15</td><td>g= 0.20</td></tr><tr><td>ORB</td><td>94.5</td><td>91.8</td><td>83.6</td><td>72.4</td></tr><tr><td>BRIEF</td><td>95.3</td><td>93.6</td><td>85.8</td><td>79.7</td></tr><tr><td>本文方法</td><td>96.6</td><td>94.9</td><td>86.1</td><td>81.5</td></tr></table></body></html>

![](images/fcef0b7b167ea3bec08811e17be5fb9fbd7774957b5fcc40f88a81b62e7596b7.jpg)  
图5添加椒盐噪声的图

表11Wall图像匹配率/% $\scriptstyle \mathtt { p } = 0 . 0 5$   

<html><body><table><tr><td colspan="5">长 国家区 HU 方法 p=0.05</td></tr><tr><td>ORB</td><td>92.2</td><td>p=0.10 88.9</td><td>p=0.15 70.7</td><td>p=0.20 53.3</td></tr><tr><td></td><td></td><td>92.7</td><td>85.3</td><td>78.5</td></tr><tr><td>BRIEF</td><td>94.6 95.7</td><td></td><td>87.6</td><td></td></tr><tr><td>本文方法 表12</td><td></td><td>94.3</td><td></td><td>80.1</td></tr><tr><td></td><td></td><td>Trees 图像匹配率/%</td><td>p=0.10</td><td></td></tr><tr><td>方法 ORB</td><td>p=0.05 91.7</td><td>p=0.10 88.5</td><td>p=0.15 70.2</td><td>p=0.20</td></tr><tr><td>BRIEF</td><td>93.7</td><td>92.7</td><td>85.7</td><td>53.5</td></tr><tr><td>本文方法</td><td>95.4</td><td>94.5</td><td></td><td>78.1</td></tr><tr><td></td><td></td><td></td><td>87.2</td><td>80.8</td></tr><tr><td>表13</td><td></td><td>Light 图像匹配率/%</td><td>p=0.15</td><td></td></tr><tr><td>方法 ORB</td><td>p=0.05 90.7</td><td>p=0.10</td><td>p=0.15</td><td>p=0.20</td></tr><tr><td>BRIEF</td><td>92.7</td><td>89.1 90.2</td><td>82.7 85.5</td><td>62.4 74.7</td></tr><tr><td>本文方法</td><td>93.4</td><td>91.6</td><td></td><td></td></tr><tr><td>表14</td><td></td><td></td><td>87.6</td><td>78.7</td></tr><tr><td></td><td></td><td>JPG 图像匹配率/%</td><td>p=0.20</td><td></td></tr><tr><td>方法</td><td>p=0.05</td><td>p=0.10</td><td>p=0.15</td><td>p=0.20</td></tr><tr><td>ORB BRIEF</td><td>92.1</td><td>90.4</td><td>73.6</td><td>61.7</td></tr><tr><td></td><td>95.6</td><td>93.3</td><td>84.5</td><td>80.3</td></tr><tr><td>本文方法</td><td>98.3</td><td>97.7</td><td>84.8</td><td>82.7</td></tr><tr><td>表15</td><td></td><td>Boat 图像匹配率/%</td><td>p=0.20</td><td></td></tr><tr><td>方法</td><td>p=0.05</td><td>p=0.10</td><td>p=0.15</td><td>p=0.20</td></tr><tr><td>ORB</td><td>93.7</td><td>90.3</td><td>83.1</td><td>63.5</td></tr><tr><td>BRIEF</td><td>95.1</td><td>92.9</td><td>85.1</td><td>75.2</td></tr><tr><td>本文方法</td><td>95.8</td><td>94.1</td><td>86.4</td><td>77.7</td></tr></table></body></html>

从实验结果可以看出，不管是原始图像之间的匹配还是添加了噪声的图像进行匹配，改进的方法都能够得到更好的匹配结果。由于改进的方法增加了差分幅值信息，得到的描述算子能够完整的表达邻域像素与特征点之间的联合差分分布关系，其判别性更强。此外，通过设置小像素差异阈值，提高了算法的抗噪声能力。

从描述算子的运行时间来看，由于都是采用的汉明距离进行判断，三种算法进行匹配的时间复杂度接近。时间开销主要在描述算子的生成上面。BRIE 进行高斯滤波操作将花费大量的时间，如果不进行高斯滤波其速度将是最快的，但是缺少滤波操作将大大降低匹配准确率。ORB算法利用图像积分操作代替高斯滤波，时间要小于BRIEF。本文算法在生成描述算子的时候，时间主要消耗在进行小像素差值阈值比较阶段，图像上的小像素差值的数量根据具体的图像有所不同，其时间与需要进行邻域均值计算的像素点的数量有关。但是该方法同样可以利用图像积分快速实现，因此，时间复杂度与ORB接近，唯一不同的是因为利用了差分信号和差分幅值两种关系得到描述算子，本文的描述算子长度要比BRIEF或ORB多一倍，所以整体上时间略多于ORB算法，最后的实验也证明了这一点。设有$n$ 个特征点，在计算描述算子时只有一次循环，计算次数为 $n$ ，因此时间复杂度为 $O ( n )$ 。从整体上比较，在同时采用512 位二进制串进行比较的情况下，本文算法与ORB计算时间接近，比BRIEF要快。表16是三种算法计算描述算子的运行时间比较。算法在单线程Inteli5 $2 . 5 ~ \mathrm { G H z }$ 处理器上实现。特征点数量为875个点。时间采用多次运行的平均结果。

表16运行时间比较  

<html><body><table><tr><td>方法</td><td>ORB</td><td>BRIEF</td><td>本文方法</td></tr><tr><td>时间/ms</td><td>70.9466</td><td>171.545</td><td>83.1741</td></tr></table></body></html>

# 4 结束语

BREIF算法是比较优秀的算法，在保证匹配率的前提下，其运行效率非常高，ORB 算法在BRIEF算法上进行了改进，增加了旋转不变性，但是导致描述算子的相关性增加。从而降低了匹配率，但是增加了旋转不变性。这两个算法都对噪声敏感，所以BRIEF算法在使用前需要进行高斯滤波。ORB算法采用图像积分来实现滤波操作，时间上有了很大提高。但是BRIEF 算法和ORB 算法都只是考虑了特征点邻域之间的分布关系，没有考虑特征点和邻域之间的关系，同时，只考虑了像素差分大小关系，没有考虑像素差分幅值关系。本文从像素差分大小和幅值关系两方面进行考虑得到二进制描述算子，能够更完整的表达邻域之间的联合差分分布关系，得到的描述算子判别性更高。通过邻域均值以及小像素差异之间设置阈值的方式进行噪声抑制，避免了高斯滤波操作。描述算子采用二进制串之间的异或操作计算匹配距离，计算简单，速度快。

# 参考文献：

[1]SatpathyA,Jiang X,Eng HL.LBP-based edge-texture features for object

recognition [J].IEEE Trans on image Processing,2014,23(5):1953-1964.   
[2]Ren J, Jiang X, Yuan J,et al.LBP encoding schemes jointly utilizing the informationofcurrent bitand otherLBPbits[J]. IEESignal Processing Letters,2015,22 (12): 2373-2377.   
[3]Chen D,Cao X, Wen F,etal. Blessing of dimensionality: high-dimensional feature and its efficient compression for face verification [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.2013: 3025-3032.   
[4]Deshmukh A,Sirpotdar P, Sheikh J,et al. High accuracy face recognition system based on SIFT[J]. International Journal of Advanced Research in Computer Engineering& Technology,2015,4(6): 2626-2628.   
[5]Li W, Chen C,Su H,et al. Local binary patterns and extreme learning machine for hyperspectral imagery classification [J]. IEEE Trans on Geoscience and Remote Sensing,2015,53(7): 3681-3693.   
[6]Xiao Y,WuJ, Yuan J,et al. mCENTRIST: a multi-channel feature generation mechanism for scene categorization [J].IEEE Transon Image Processing, 2014,23 (2): 823-836.   
[7]Zhao G,Ahonen T, Matas J,et al. Rotation-invariant image and video description with local binary patern features [J]. IEEE Trans on Image Processing,2012,21 (4): 1465-1477.   
[8] Guo Z,Zhang L, Zhang D,et al. Acompleted modeling of local binary pattern operator for textureclassification[J]. IEEE Trans on Image Processing,2010,19 (6): 1657-1663.   
[9]Song T,Li H,Meng F,et al.Noise-robust texture description using local contrast pattrns via global measures [J].IEEE Signal Process.Letters,2014, 21 (1): 93-96.   
[10] Wang K, Bichot C E, Zhu C,et al. Pixel to patch sampling structure and localneighboring intensityrelationshippatterns for textureclassfication[J]. IEEE Signal Processing Letters,2013,20 (9): 853-856.   
[11]Liao S,Law MWK, Chung AC S,etal. Dominant local binary patterns for texture classification [J]. IEEE Trans on Image Processing,20o9,18 (5): 1107-1118.   
[12] Kwak JT,Xu S,WoodB J,etal.Efficient data mining for localbinary patternin texture image analysis [J].Expert Systemswith Applications 2015,42 (9): 4529-4539.   
[13] Calonder M,Lepetit V,Ozuysal M,et al. BRIEF: computinga local binary descriptor very fast [J].IEEE Transon Pattern Analysisand Machine Intelligence,2012,34(7): 1281-1298.   
[14] Moravec H P.Rover visual obstacle avoidance [C]// Proc of the 7th International Joint Conference on Artificial Intelligence.1981: 785-790.   
[15] Harris C, Stephens M.Acombined corner and edge detector [C]//Proc of the 4th Alvey Vision Conference.1988:147-151.   
[16] Lowe DG. Distinctive image features from scale-invariant keypoints [J]. International Journal of Computer Vision,2004,60 (2): 91-110   
[17] Mikolajczyk K,Schmid C.Aperformance evaluationoflocal descriptors [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,20o5,27(10): 1615-1630.   
[18] Hua G,Brown M,Winder S.Discriminant embedding for local image descriptors [C]// Proc of the 1lth IEEE International Conference on Computer Vision. 2007:1-8.   
[19]BayH,Tuytelaars T,Van Gool L.Surf: speeded up robust features [C]//Proc of International Conference on Computer Vision. Berlin: Springer, 2006: 404-417.   
[20]初守艳，席志红，结合 SURF 的数字稳像技术[J].计算机辅助设计与 图形学学报,2014,26(2):241-247.   
[21]陈小丹，杜宇人，高秀斌，等．一种基于 SURF的图像特征点快速匹配 算法[J].扬州大学学报：自然科学版,2012,15(4):64-67.   
[22] Leutenegger S,Chli M, Siegwart R Y.BRISK:binary robust invariant scalable keypoints [C]// Proc of International Conference on Computer Vision. 2011:2548-2555.   
[23] Alahi A, Ortiz R,Vandergheynst P.Freak: fast retina keypoint [C]/ Proc of IEEE Conference on Computer Vision and Pattern Recognition.2012:510- 517.   
[24]Rublee E,Rabaud V,Konolige K,et al. ORB:an efficient alternative to SIFT orURF[C]//Proc of International Conference on Computer Vision.2011: 2564-2571.   
[25] Ojala T,Pietikainen M,Harwood D.A comparative study of texture measures with classification based on featured distributions [J].Pattern Recognition,1996,29 (1):51-59.   
[26] Ojala T,Pietikainen M,Maenpaa T.Multiresolution gray-scale and rotation invariant texture classification with local binary patterns [J].IEEE Trans on Pattern Analysis and Machine Intelligence,2002,24(7): 971-987.   
[27] Weinberger MJ,RissanenJJ,Arps RB,et al.Applications of universal context modeling to lossless compression of gray-scale images [J].IEEE Trans on Image Processing,1996,5 (4): 575-586.