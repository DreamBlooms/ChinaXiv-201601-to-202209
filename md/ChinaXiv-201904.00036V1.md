# 基于声源阵列的空间麦克风定位方法研究

陈晓辉，孙昊，张恒，翟葆朔(河北工业大学 人工智能与数据科学学院，天津 300130)

摘要：针对当前麦克风位置估计方法出现较少且只对平面的麦克风阵列进行位置估计的问题，提出了一种基于声源阵列的空间麦克风定位方法。该方法将四个声源按照正四面体形式排列，在利用其对称性保证定位全向性的同时，根据时延估计的测距方法计算麦克风与各个声源之间的距离，之后根据几何关系确定麦克风位置坐标，实现在线的基于声源阵列的空间麦克风位置估计。通过进行MATLAB仿真实验，验证了该方法的可行性和有效性。

关键词：声源阵列；时延估计；声达时间差；麦克风定位 中图分类号：TP391.9 doi:10.19734/j.issn.1001-3695.2018.10.0823

Microphone spatial positioning method based on sound source array

Chen Xiaohui, Sun Hao†, Zhang Heng, Zhai Baoshuo (SchoolofArtificial Intelligence,Hebei University ofTechnology,Tianjin3oo130,China)

Abstract: Currently,there are fewer microphone position estimation methods andonly position estimates are made fora planar microphone array.Aiming at this problem,this paper proposed a spatial microphone positioning method based on sound source array.The method arranges four sound sources in the form ofa regular tetrahedron.While using its symmetry to ensuretheomnidirectionalityof thepositioning,the distancebetween the microphoneandeach sound source is calculated according to theranging method of thetime delay estimation.The microphone position coordinates are then determined based on the geometric relationship torealizethe spatialmicrophone position estimationbasedonthe sound source array fr online positioning.In thispaper,MATLAB simulation experimentis carriedout,andtheexperimentalresultsverifies the feasibility and effectiveness of the proposed method.

Key words: sound source aray; time delay estimation; time delay of arrival; microphone positioning

# 0 引言

伴随着科学技术日新月异的发展，传感器技术的应用领域逐步扩大，其所面对的工作环境也愈来愈复杂[1]。对麦克风位置进行准确的定位能够帮助分布式麦克风阵列信号处理，而麦克风阵列在语音增强、声源定位[2-4]、声源分离等应用中起着重要作用。针对如何对麦克风阵列信号[5\~7进行处理的问题研究虽已近十年，但大多集中于国外，并且由于刚起步不久，还仍处于探索阶段。然而在国内，对于该问题的研究则是很少。因此最终研究成果不多。同时，准确得到麦克风位置坐标可以帮助解决当前机器人领域众多问题，例如，当机器人处于未知的环境中，对自身位姿未知时，如何进行自定位和环境识别，即同时自定位和地图构建[8]一直都是智能机器人技术研究的热点和难点[9]。然而从机器人听觉系统的角度出发，确定出待定位麦克风的位置坐标，将机器人技术与机器人所处环境中的分布的麦克风位置进行有机结合，可帮助解决机器人同时自定位与构建环境地图的问题，从而实现机器人全自主移动等[10]。因此，确定麦克风阵列中的麦克风位置是一个必须解决的技术难题。

文献[11]中采用三个不同位置的校正声源来校正麦克风阵列中的麦克风位置。其方法是将一个声源先后放置于三个位置，分三次进行信号的采集与计算，最后将三次计算结果融合得到麦克风位置。但该方法的信号采集操作较繁琐，效率较低，只能离线计算，无法实现麦克风位置的在线估计。文献[12]通过选择三个不同频带的声音信号作为三个声源的发声信号，在麦克风位置估计过程中一次性采集并分离出三个声源，实现麦克风位置的在线估计。将基于能量和时延的测距方法结合使用，先后进行距离的粗、精估计；采用三角形质心算法获取阵列中各麦克风的位置，对各种无解情况均有相应的处理，该方法保证了测距具有较小的计算量和较高的精度，同时保证定位结果的持续性和稳定性。但此方法只针对平面的麦克风阵列进行了位置估计，无法实现空间分布麦克风的位置估计。

为解决现有技术存在的上述问题，本文提出了一种精度较高、计算复杂度较小、并能够实现在线定位的基于声源阵列的空间麦克风定位方法。在一定的空间范围内，随机分布一定数量的麦克风；声源分布单元为四个声源按照四元三维阵列，特别是正四面体的方式排列分布；声源分布单元依次产生声音信号，接收到四个声音信号的麦克风定义为待定位麦克风，之后采用时延估计法获取参考麦克风与待定位麦克风接收到声音信号的时间差（声达时间差）信息，最后根据几何关系确定各个待定位麦克风位置。此方法利用正四面体的对称性，保证了定位全向性，同时保证信号被麦克风均匀接收，从而满足定位精度，保证定位精度的持续性和稳定性。

本文利用声达时间差数据，通过MATLAB仿真实验，实现了三维空间中的麦克风的在线定位。

# 1 声源阵列模型

本文将声源分布单元按照四元三维阵列分布，即构建一个三维空间坐标系，将四个声源按照正四面体的形式空间分布。可利用其对称性保证信号被麦克风均匀接收，从而满足定位精度，同时空间分布的麦克风位置表示都将以此坐标系为基准。声源阵列模型如图1所示。

![](images/5525ff770c07afef6644afda69cc4516f053624a9258a295d2b815c129ff7ee2.jpg)  
图1声源阵列模型  
Fig.1The model of sound source array

图中，在以o为原点的三维空间坐标系（x、y、z）中，S1、S2、S3、S4分别为四个声源，C0为参考麦克风，其所处位置距离各个声源小于10米，M1设定为第一个待定位麦克风，即所要进行定位的目标待定位麦克风之一，L1为参考麦克风C0到第一个声源S1的距离，已知且固定不变，同理，参考麦克风C0 到其他声源（S2、S3、S4)的距离分别为L2、L3、L4也已知且固定不变，d11为第一个待定位麦克风M1到第一个声源 S1的距离，它是由S1到达C0与M1的时间差乘以声速计算得到的距离差，然后再根据已知距离L1所求得的，依此类推，可计算出M1到其他声源的距离，这是定出M1空间位置的必要条件。

# 2 时延估计算法

时延估计主要指利用信号处理的理论和方法对不同接收器所接收信号的时间差进行估计，来确定其他相关参量，如新源的距离、方位、速度和移动方向等[13,14]。按照测量环境、条件和信号的特性可将时延估计方法分为如下几类：相位法、双谱法、相关法、自适应滤波器参数模型法等。其中，相关法是最经典的且常用的一种时延估计方法。

# 2.1基本互相关法

声源分布单元依次产生声音信号，参考麦克风与待定位麦克风接收到声音信号。这里假设麦克风接收到的声音信号模型是理想模型，即只考虑环境噪声，这里环境噪声用高斯白噪声近似代替，且假设噪声与噪声之间、噪声与声源之间互不相关。麦克风接收到信号的数学模型如式（1）所示。

$$
x _ { i } \left( t \right) = \alpha _ { i } s \left( t - \tau _ { i } \right) + n _ { i } \left( t \right)
$$

其中：声源信号为 $s ( t )$ ，第i个麦克风接收到的信号为 $x _ { i } \left( t \right) , \alpha _ { i }$ 、$\tau _ { i }$ 、 $n _ { i } \left( t \right)$ 分别表示声源信号到达第i个麦克风的幅度衰减系数、时间延迟和环境噪声。第i和 $\mathrm { ~ j ~ }$ 个麦克风的互相关函数

如式（2）所示。

$$
R _ { x _ { i } x _ { j } } \left( \tau \right) = E \big [ x _ { i } \left( t \right) x _ { j } \left( t - \tau \right) \big ]
$$

将式（1）代入式（2）可得

$$
\begin{array} { c } { { R _ { x _ { i } x _ { j } } \left( \tau \right) = \alpha _ { i } \alpha _ { j } R _ { s s } \left( \tau - \tau _ { i j } \right) + \alpha _ { i } R _ { s n _ { j } } \left( \tau \right) } } \\ { { + \alpha _ { j } R _ { s n _ { i } } \left( \tau - \tau _ { i j } \right) + R _ { n _ { i } n _ { j } } \left( \tau \right) } } \end{array}
$$

其中： $R _ { s s } \left( \tau \right)$ 是 $\mathbf { s } \left( \mathbf { t } \right)$ 的自相关函数， $R _ { n _ { i } n _ { j } }$ 是 $n _ { i } ( \mathfrak { t } )$ 与 $n _ { j } ( \mathrm { t } )$ 的互相关函数， $R _ { s n _ { j } }$ 和 $R _ { s n _ { i } }$ 是噪声与声源的互相关函数， $\tau _ { i j }$ 是第 $i , j$ 个麦克风接收到声音信号的相对时间延迟。因为噪声与噪声之间、噪声与声源之间互不相关，则式（3）可化简为

$$
R _ { x _ { i } x _ { j } } \left( \tau \right) = \alpha _ { i } \alpha _ { j } R _ { s s } \left( \tau - \tau _ { i j } \right)
$$

根据自相关函数的性质可知当 $\tau - \tau _ { i j } = 0$ 时， $R _ { x _ { i } x _ { j } } ( \tau )$ 达到最大值[15]。则时延估计 $\tau _ { i j }$ 便可由两路麦克风接收信号的互相关函数和其最大值位置所在点计算而得。

# 2.2广义互相关法

广义互相关算法是目前应用最广泛的一种时间估计方法[16]。针对实际环境中噪声与混响大量存在，进而造成互相关函数最大峰值不明显或者峰值出现多个的情况，广义互相关以其抑制噪声与混响的能力相对基本互相关算法在峰值检测难易程度方面性能较好。对式（4）进行傅里叶变换可得

$$
{ { \varphi } _ { { { x } _ { i } } { { x } _ { j } } } } \left( \omega \right) = { { \alpha } _ { i } } { { \alpha } _ { j } } { { \varphi } _ { s s } } \left( \omega \right) e ^ { - j \omega { { \tau } _ { i j } } } + { { \varphi } _ { { { n } _ { i } } { { n } _ { j } } } } \left( \omega \right)
$$

其中： $\varphi _ { s s } \left( \omega \right)$ ， $\varphi _ { x _ { i } x _ { j } } \left( \omega \right)$ ， $\varphi _ { n _ { i } n _ { j } } \left( \omega \right)$ 分别为 $R _ { s s } \left( \tau \right)$ ， $R _ { x _ { i } x _ { j } } \left( \tau \right)$ 与 $R _ { n _ { i } n _ { j } } \left( \tau \right)$ 所对应的功率谱，其中， $R _ { n _ { i } n _ { j } } \left( \tau \right)$ 为 $n _ { i } \left( t \right)$ 和 $n _ { j } \left( t \right)$ 的互相关函数。进而，对式（5）进行加权后做逆变换，则可得到广义互相关函数如式（6）所示。

$$
R _ { i j } \left( \tau \right) = \int _ { - \infty } ^ { \infty } \varphi _ { x _ { i } x _ { j } } \left( \omega \right) \theta _ { i j } \left( \omega \right) e ^ { j \omega \tau } d \omega
$$

其中： $\theta _ { i j } \left( \omega \right)$ 为广义加权函数[17]。加权函数有Roth、SCOT（平滑相干变换）、PATH（相位变换）等。由于它们有着不同的特性，应根据不同应用场景选择不同的加权函数。由于广义互相关以其抑制噪声与混响的能力相对基本互相关算法在峰值检测难易程度方面性能较好，因此本文选取广义互相关时延估计算法。并且PATH加权函数在信噪比不断变化的情况下有着较小的波动性，抗噪声性能也较好[18]，因此其中应用PATH加权函数进行定位仿真分析。

# 3 麦克风位置估计

在实际环境中，将一定数量的麦克风准确得摆放在同一平面内有一定的难度，因此对同一平面内的麦克风位置估计将会产生一定的误差。而将麦克风在同一空间内随机分布相对容易，即降低了设备组装等的困难程度，并且实现麦克风空间位置估计可帮助解决传感器技术、机器人技术等领域众多问题。

本文所述的麦克风空间位置估计系统包括声源分布单元、参考麦克风、待定位麦克风以及麦克风定位单元。在一定的空间范围内，随机分布一定数量的麦克风；声源分布单元为四个声源按照第一节所述形式排列，并依次发声，共产生四个声音信号；将在空间中分布的所有麦克风中能接收到四个声音信号的麦克风定义为待定位麦克风，即该四个声音信号被待定位麦克风和参考麦克风所接收；参考麦克风与待定位麦克风接收声音信号的时间差（声达时间差）传递给麦克风定位单元；经过上节所述广义互相关时延估计法获取声达时间差之后，麦克风定位单元根据声达时间差以及参考麦克风与待定位麦克风之间的位置关系确定出待定位麦克风的位置。基于声源阵列的空间麦克风定位方法流程图如图2所示。

![](images/48dbd7dee50db887835e858310f069c3f0abeae079c150fd1eae8a82d9004afe.jpg)  
图2基于声源阵列的空间麦克风定位方法流程图

如图2所示，S1、S2、S3、S4分别为产生声音信号的四个声源，产生的声音信号被参考麦克风和待定位麦克风1、待定位麦克风2待定位麦克风 $N$ 所接收，利用经典的时延估计法中的广义互相关函数法来估计四个声源依次产生的声音信号 $s _ { i } \left( t \right) \left( i = 1 , 2 , 3 , 4 \right)$ 到达参考麦克风与待定位麦克风的时间差即声达时间差，即为图中的TDOA1、TDOA2、TDOA3、TDOA4,其中， $\mathbf { \Psi } _ { t }$ 表示各个声源发声对应的时间， $\scriptstyle i = 1 , 2 , 3 , 4$ 表示四个声源，进行“麦克风定位单元”的操作，将TDOA1、TDOA2、TDOA3、TDOA4作为输入信号，输出待定位麦克风在三维空间中的坐标，包括待定位麦克风1坐标、待定位麦克风2坐标…待定位麦克风 $N$ 坐标，由此完成基于声源阵列的空间麦克风定位。麦克风定位单元的工作流程描述如下：

定义 $\Delta T _ { i j } ( \mathrm { { i } } = 1 , 2 . . . . . N ; \mathrm { { j } } = 1 , 2 , 3 , 4 )$ 为参考麦克风与第i个待定位麦克风接收到第 $j$ 个声音信号的时间差；定义声音在空气中传播速度为 $C$ ，将信号到达时间差乘以声速 $C$ ，得到第 $j$ 个声源与参考麦克风的距离和与第 $i$ 个待定位麦克风的距离的差值如式（7）所示。

$$
\Delta L _ { i j } = \Delta T _ { i j } \times C
$$

根据参考麦克风到第 $j$ 个声源的距离 $L _ { j } ( \mathfrak { j } = 1 , 2 , 3 , 4 )$ ，以及第 $j$ 个声源到参考麦克风与第 $i$ 个待定位麦克风的距离差 $\Delta L _ { i j }$ ，获得第 $i$ 个待定位麦克风到第 $j$ 个声源的距离 $d _ { i j }$

$$
d _ { i j } = L _ { j } + \Delta L _ { i j } = L _ { j } + \Delta T _ { i j } \times C
$$

根据几何关系，通过求解分别以四个声源位置为球心，以待定位麦克风到相对应的声源的距离为半径的四个球的交点，来确定第i个麦克风在空间环境中的位置。即

$$
\left\{ \begin{array} { l l } { ( x - x _ { 1 } ) ^ { 2 } + ( y - y _ { 1 } ) ^ { 2 } + ( z - z _ { 1 } ) ^ { 2 } = { d _ { i 1 } } ^ { 2 } } \\ { ( x - x _ { 2 } ) ^ { 2 } + ( y - y _ { 2 } ) ^ { 2 } + ( z - z _ { 2 } ) ^ { 2 } = { d _ { i 2 } } ^ { 2 } } \\ { ( x - x _ { 3 } ) ^ { 2 } + ( y - y _ { 3 } ) ^ { 2 } + ( z - z _ { 3 } ) ^ { 2 } = { d _ { i 3 } } ^ { 2 } } \\ { ( x - x _ { 4 } ) ^ { 2 } + ( y - y _ { 4 } ) ^ { 2 } + ( z - z _ { 4 } ) ^ { 2 } = { d _ { i 4 } } ^ { 2 } } \end{array} \right.
$$

由于四个声源位置在空间中以正四面体形式分布，因而由声源两两构成的向量线性无关，从而保证上述方程只有一个解，该解即为四个球的交点，此交点坐标即为第 $i$ 个待定位麦克风在空间中的位置坐标。图3为其几何模型解释：S1、S2、S3、S4分别为四个声源，以第一个待定位麦克风M1为例，d11、d12、d13、d14分别为M1到四个声源的距离。以声源位置为球心，相对应的待定位麦克风到声源的距离为半径作球，由于声源在空间中以正四面体形式分布，因而由声源两两构成的向量线性无关，从而该四个球在空间中只有一个交点，此交点即为待定位麦克风M1的坐标，如图黑色三角形所示。

![](images/8369eb35d183754ebd6d213b1284e0eb78d9484e7cefd662c070460fbcddf82a.jpg)  
图3四个球相交于一点示意图

![](images/b09c697c8b18c8c46e6c7952e793dd23a28d4b10584527eadb626e2db7b90bc8.jpg)  
Fig.2Flow chart of spatial microphone positioning method based on sound source array   
Fig.3Schematic diagram of four balls intersecting at one point图4为四个球相交于一点在三维空间中较为直观的表示，以其中一个待定位麦克风为例。图中红色圆点即为某一个待定位麦克风的位置。  
图4四个球相交于一点立体示意图  
Fig.4Stereoscopic diagram of four balls intersecting at one point

# 4 实验与分析

为了验证方法的可行性和有效性，基于上述广义互相关时延估计法获取的声达时间差数据，本文在MATLAB仿真环境下进行了仿真实验，进行了如下仿真测试。设定一个长、宽、高分别为 $6 0 \mathrm { ~ m ~ }$ 、 $6 0 \mathrm { ~ m ~ }$ 、 $2 0 \mathrm { ~ m ~ }$ 的空间区域，如图5中坐标轴所示，在该空间区域内，图中四个空心圆〇示为四个声源的坐标，位置分别为 $( 6 , 0 , 0 ) \mathrm { ~ m ~ }$ 、 $( - 3 , 3 \sqrt { 3 } , 0 ) \mathrm { ~ m ~ }$ 、 $( - 3 , - 3 { \sqrt { 3 } } , 0 ) \mathrm { m }$ 与 $( 0 , 0 , 6 \sqrt { 2 } ) \mathrm { m }$ ；参考麦克风 $\bigstar$ 坐标为 $( 0 , 0 , 0 ) \mathrm { ~ m ~ }$ ，即选择坐标原点为参考麦克风 $\bigstar$ 的位置，图中空间区域中有200个随机分布的麦克风 $+$ ，经验证，其中有两个接收到四个声音信号的麦克风，即有两个待定位麦克风 $\bullet$ ，因其是200个随机分布的麦克风 $+$ 中的两个，所以在图中显示两个待定位麦克风·的图形“·”肯定是与200个代表随机分布的麦克风十中的两个“ $+$ ”图形重叠，重叠后的图形在该图5中有显示。根据本文方法对这200个随机分布的麦克风中的两个待定位麦克风的位置进行了估计，估计的结果如该图5中的“口”所示，“□"所在的位置就是本文方法对麦克风估计的位置，换句话说，“·"所在的位置是需要对其进行定位的也就是待定位麦克风的实际位置。由基于声源阵列的空间麦克风定位方法将这两个待定位麦克风位置估计出来，声源位置、参考麦克风、随机分布的麦克风、待定位麦克风以及待定位麦克风位置估计的分布如图5所示。

+ 随机分布的麦克风★ 参考麦克风+ · 待定位麦克风10 + + + + + + + □0 待定位麦克风位置估计+ +++ + + 书+ ++ + + ++ +  
米0 5 + ++ +++ 双x +++ ++ +++\* ++ 中 国 + xx + + ++++ ++ +  
高 -5 + ++ x×x + + ++ #+ ++ + ++ + + +# ×x + \$+ +\*+ + ++ + + ++ +-10 艹 ++ + + ++20 +10 ++ +++ ++ 20 300 0 10-10 -10-20 -20宽(米) -30 -30 长(米)

空间麦克风定位结果如表1所示。

表1空间麦克风定位结果分析  
Table 1Analysis of spatial microphone positioning results   

<html><body><table><tr><td>序号</td><td>麦克风坐标真值/m</td><td></td><td>信噪比/dB麦克风坐标测量值/m</td><td>误差/m</td></tr><tr><td>1</td><td>(2.316,-0.744,5.675)</td><td>10</td><td>(2,307,-0.741,5.666)</td><td>0.012</td></tr><tr><td>2</td><td>(1.313,-2.844,-0.205)</td><td>10</td><td>(1.320,-2.851,-0.221)</td><td>0.010</td></tr></table></body></html>

从表1可以看出，考虑在一定的信号信噪比下，麦克风在三维空间坐标系下的位置坐标都能够很好地被估计出来，且定位误差较小。

# 5 结束语

本文针对麦克风位置估计问题，提出了一种基于声源阵列的空间麦克风定位方法。该方法采取四个声源按照正四面体形式排列的方式作为声源分布单元，根据广义互相关时延估计方法获得声音信号到达参考麦克风与待定位麦克风的时间差，利用声达时间差由一定的运算关系的得出待定位麦克风与各个声源之间的距离，之后根据几何关系，通过求解分别以四个声源位置为球心，以待定位麦克风到相对应的声源的距离为半径的四个球的交点，来确定该麦克风在空间环境中的位置。由于四个声源为对称性分布，因而保证了定位全向性，同时保证信号被麦克风均匀接收，从而满足定位精度，保证定位精度的持续性和稳定性。此方法精度较高、计算复杂度较小、并能够实现在线定位的基于声源阵列的空间麦克风位置估计。对麦克风进行空间层面的定位是一种新颖且极具潜力的新技术，如何将该技术应用到声音以及机器人等领域是一个值得深入研究的问题。

# 参考文献：

[1]孙昊．基于声达时间差的移动机器人声源目标定位方法研究[D].天津：河北工业大学，2012.(Sun Hao.Study on sound sourcelocalization for mobile robot based on time delay of arrival [D].Tianjin:Hebei Universityof Technology,2012.）  
[2]陈国良，徐扬，黄晓琴．基于正四棱锥结构的机器人声源定位系统

研究[J].计算机应用研究，2019,36(5）.（Chen Guoliang，Xu Yang, Huang Xiaoqin.Sound source localization system for robot based on rectangular pyramid structure [J]. Application Research of Computer, 2019,36 (5) .)

[3] Yook D,Lee T, Cho Y. Fast sound source localization using two-level search space clustering [J]. IEEE Trans on Cyberm,2017,46(1): 20-26.   
[4]Li X,Liu H. Sound source localization for hri using FOC-based time dierence feature and spatial grid matching [J].IEEE Transon Cybernetics,2013,43(4): 1199-1212.   
[5]Benesty J,Chen J,Huang Y,et al. On microphone-array beamforming from a MIMO acoustic signal processing perspective [J]. IEEE Trans on Audio Speech & Language Processing,2007,15(3): 1053-1065.   
[6] Silva B D,An B,Steenhaut K,et al. Design considerations when accelerating an FPGA-based digital microphone array for sound-source localization [J]. Journal of Sensors,2017(4): 1-20.   
[7] 张雷岳，张兴敢，刘超．麦克风阵列声源定位中时延估计的改进[J] 南京大学学报：自然科学版，2015，51(1):25-30.(Zhang Leiyue, Zhang Xinggan,Liu Chao.The improvement of time delay estimation in the microphone array sound localization system [J]. Journal of Nanjing University: Natural Sciences,2015,51(1):25-30.)   
[8] 柯文德，蔡则苏，李家兰．机器人同时定位与地图构建技术研究[J] 计算机应用研究,2010,27(4):1216-1219.(Ke Wende,Cai Zesu,Li Jialan.Research of simulation localization and mapping in robot [J]. Application Research of Computers,2010,27 (4): 1216-1219.)   
[9]罗元，苏琴，张毅，等．基于优化 RBPF 的同时定位与地图构建[J]. 华中科技大学学报:自然科学版，2016,44(5):30-34.(Luo Yuan,Su Qin, Zhang Yi，et al. Simultaneous localization and mapping implementation based on optimized RBPF [J]. Journal of Huazhong University of Science and Technology:Natural Science Edition,2016, 44(5): 30-34. )   
[10] Evers C, Naylor PA. Acoustic SLAM [J]. IEEE/ACM Trans on Audio Speech & Language Processing,2018,PP(99): 1-1.   
[11]肖华．麦克风阵列的校正方法研究[D]．成都：电子科技大学,2008. (Xiao Hua. Research on correction method of microphone array [D]. Chengdu:University of Electronic Science and Technology of China, 2008.）   
[12]王舒文．分布式麦克风阵列定位方法研究[D]．大连:大连理工大学, 2013.(Wang Shuwen.Studyon distributed microphone array localization method[D].Dalian:Dalian Uuniversityof Technology, 2013)   
[13]行鸿彦，唐娟．时延估计方法的分析 [J]．声学技术，2008，27(1): 110-114. (Hang Hongyan, Tang Juan.Analysis and survey of algorithms for time-delay estimation [J]. Technical Acoustics，2008，27(1): 110-114.）   
[14] Chen Z,Li Z,Wang S,et al.A microphone position calibration method based on combination of acoustic energy decay model and TDOA for distributed microphone arry[J]. Applied Acoustics,2015,95:13-19.   
[15]行鸿彦，赵守国，邸继征，等．广义相关时延估计算法的自适应实现 形式[J].西安石油大学学报:自然科学版,2001,16(6):47-50.(Hang Hongyan, Zhao Shouguo,Di Jizheng, et al. Adaptive realizing form of generalized correlation algorithm for time delay estimation [J]. Journal of Xi’an Petroleum Institute: Natural Science Edition, 20o1,16(6): 47-50.）   
[16]茅惠达，张玲华.声源定位中广义互相关时延估计算法的研究[J]. 计算机工程与应用，2016，52(22):138-142.(Mao Huida，Zhang Linghua.Research on generalized cross correlation algorithm for time

delayestimation insoundsourcelocalization[J].Computer Engineering and Applications,2016,52(22): 138-142.) [17]张莉．基于传声器阵列的声源定位方法研究[D].成都：电子科技大 学，2007.(Zhang Li.Research on sound source localization method based on microphone array [D]. Chengdu:University of Electronic Science and Technology of China,2007.)

[18]孙洋，徐慨，杨海亮．基于广义互相关时延估计算法的性能分析[J]. 计算机与数字工程，2013，41(1):33-34.(Sun Yang，Xu Kai,Yang Hailiang. Performance analysis of time-delay estimation based on generalized cross-correlation algorithm [J].Computer and Digital Engineering,2013,41(1): 33-34.)