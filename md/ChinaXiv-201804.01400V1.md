# 模糊C-均值聚类引导的Kinect深度图像修复算法‘

万红1,²，钱锐1,2

(1．郑州大学 电气工程学院，郑州 450001;2.脑科学与脑机接口技术河南省重点实验室，郑州 450001)

摘要：针对 Kinect传感器所采集的深度图像中存在大面积空洞的问题，提出了一种模糊C-均值聚类引导的深度图像修复算法。该算法将同步获取的彩色图像和深度图像作为输入；利用模糊C-均值聚类算法对彩色图像进行聚类，聚类结果作为引导图像；然后对每个深度图像中的大面积空洞区域，利用改进的快速行进算法，从空洞边缘向空洞内部逐层修复空洞区域；最后，利用改进的双边滤波算法去除图像中的散粒噪声。实验表明该算法能有效修复Kinect深度图像中的空洞，修复后的图像在平滑度和边缘强度上优于传统算法。

关键词：深度图像；空洞修复；模糊C-均值算法；聚类；快速行进法 中图分类号：TP391.41 doi:10.3969/j.issn.1001-3695.2017.12.0831

# Kinect depth map inpainting under fuzzy C-mean clustering guidance

Hong Wan1,², Rui Qian1, 2 (1.SchoolofElectricalEngineering,ZhengzhouUniversityZhengzhou450o1,China;2.Henan KeyLaboratoryfBrain Science & Brain-Computer Interface Technology,Zhengzhou University, Zhengzhou 45ooo1, China)

Abstract: Considering the problemthatlarge holes inthe depth mapcapturedbyKinect,analgorithm for inpainting holes in depth map under fuzzy C-means clustering guidance was proposed.Firstly,color image and depth map were simultaneously obtainedasinput.Thenthe proposed methodused fuzzyC-means clustering algorithmforcolorimage,image clusteringresults as a guiding image.For thelarge holes inthedepth map,the proposed method usedtheimproved fast marching algorithmto inpainttheholes fromtheedgetotheinternal layer.Forthediscrete voidpoints,thealgorithm inpainted thembyusing the improved bilateral filtering.Experiments showthat thealgorithmcan effectively inpaint holes in depth mapcaptured by Kinect, andtheestoreddepth mapare superior tothedepth maprestoredbythetraditionalalgorithms insmoothnessandedgestrength. Key words: depth image; hole inpainting; fuzzy-c mean algorithm; clustering; fast marching method

# 0 引言

近年来，深度信息在人机交互[1]，三维场景重建[2]，3D打印[3]等计算机视觉领域有着重要的应用。微软公司的Kinect作为一款廉价的深度传感器能够获取被测场景的深度图像和同步的彩色图像，得到越来越多研究人员的关注。但是由于其自身成像原理的限制，Kinect获取的深度图像存在深度信息缺失区域，包括遮挡造成的黑色空洞区域，图像光学噪声[4]。为了获取高质量的深度图像，改善Kinect的应用效果，需要对其获取的深度图像进行修复。

针对Kinect传感器深度图像修复的问题，相关研究人员提出了几类不同的修复算法。文献[5]基于水平集思想，通过模拟水波在水面的传播过程来确定空洞区域边缘像素的修复顺序，结合快速行进算法(fastmarchingmethod，FMM)来修复图像中的缺损区域，这种方法对单幅图像中小区域空洞和简单结构有较好的修复效果，但是对大面积空洞或纹理复杂的图像，修复效果不理想。文献[6]提出了基于空间域的高斯滤波，用邻域内像素的加权平均值去替代模板中心像素点的值，该方法只考虑到了像素点的空间信息，容易造成图像中物体边缘信息的丢失。而文献[7,8]提出了基于双边滤波(bilateralfilter,BF)的改进算法,同时考虑了像素点的空间信息和值域信息，像素之间的距离和像素差值共同决定了权值的大小，该方法能够很好地保护图像中物体的边缘，但是对于较大面积的空洞区域，该算法可信度较差。文献[9\~11]在双边滤波法的基础上，提出了结合彩色图像信息的联合双边滤波(joint bilateral filtering,JBF)的空洞修复算法，该算法引入了基于彩色图像像素差的权值，虽然能够修复图像中的大部分空洞，但是该算法未考虑物体边缘处深度不连续，易产生过度平滑的效果，且采用单一的滤波参数修复整幅深度图像具有较大的盲目性。文献[12]提出一种基于聚类思想的K-means修复算法，该算法对灰度化后的彩色图像进行聚类，通过聚类图像在深度图像中找出匹配空洞信息的像素点，用该点的深度值作为空洞处的深度值，k-means 聚类算法作为一种硬分类方法，每个样本属于某一类的结果只有0，1两种情况，所以仅以距离最近像素点深度值为空洞填充值的方法出错率较大。文献[13,14]基于多种角度或多帧图像对采集的图像背景进行提取从而达到图像的修复，这类方法的修复效果明显、可信度较高，但对单帧图像无法进行有效的处理。

针对Kinect深度图存在大量空洞，而传统算法没能有效利用彩色图像提供的全局信息和邻域关系，不能有效分割物体边缘，易产生过平滑的现象，影响深度图的修复效果的这一问题，本文提出一种模糊C-均值聚类引导的深度图像修复算法。该算法联合彩色图像聚类信息和原始深度图，利用改进的快速行进法和改进的双边滤波算法来修复深度图像中的空洞像素点。

# 1 算法框架

本文提出的算法基本思路是：首先通过Kinect获得对齐的彩色图像和深度图像作为输入，如图1(a)(b)所示，然后对彩色图像进行模糊C-均值聚类得到每个像素点对于各个类的隶属度，生成聚类引导图。针对深度图像中存在的大面积深度缺失区域，基于快速行进算法，对原像素估计公式中的权重项进行改造，加入隶属度因子，对缺失像素进行深度估计；最后，针对依然存在的噪声点，基于传统双边滤波修复算法，加入彩色图像提供的信息，对双边滤波算法进行改进，用该方法去噪，得到最终的修复后的图像。本文提出算法的框架如图2所示。

![](images/2cc5fd6a036c320a2df0b630a83179f42372b27d45ca179d93d870545340619f.jpg)  
图1带有空洞点的深度图

![](images/bb4180f3e98c0d8958474f6092d4dff0e1ab106a91dc745cbed9be34a5c3eba8.jpg)  
图2模糊C-均值聚类引导的深度图像空洞修复框架

# 1.1聚类引导图

本文使用聚类后的彩色图像作为修复深度图像的引导图。彩色图像的每个像素值是由RGB 颜色空间决定的，每一个像素点的值就是一个样本点。聚类能够将获得像素缺失区域的局部信息，以及不同像素点之间的相关性信息。本文使

用的聚类方法是一种模糊聚类算法-FCM算法。模糊聚类就是用模糊数学的方法，把样本之间的模糊关系定量，从而客观准确地进行聚类，使得各个类之间的数据差别应尽可能大，类内之间的数据差别应尽可能小，即最小化类间的相似性，最大化类内的相似性。FCM算法是一种应用最广泛且较成功的模糊聚类方法。它通过优化目标函数得到每个样本点对所有类中心的隶属度，从而决定样本点的类属以达到对样本进行分类的目的。

FCM算法优越于传统硬C均值聚类算法在于隶属度可以连续取值于[0,1]，考虑到了样本属于各个类的"亦此亦彼"性，能够对类与类之间样本有重叠的数据集进行分类，具有良好的收敛性；而且FCM算法复杂度低，易于实现。

FCM算法主要是比较每个样本点与每个类的中心点值，最终给每个像素指派一个值(0-1之间)，说明该像素更接近于哪个类的中心点，模糊规则是该像素的隶属度对所有类的值之和为1。

假定有数据集为 $X$ ，如果把这些数据分为 $\mathbf { \Psi } _ { c }$ 类的话，那么就有 $\boldsymbol { c }$ 个类中心为 $V { = } [ \nu _ { 1 } , . . . , \nu _ { c } ]$ ，样本 $\boldsymbol { \mathscr { X } } _ { j }$ 属于某一类 $i$ 的隶属度为 $u _ { i j }$ ，定义一个FCM目标函数式(1)及其约束条件式(2)如下:

$$
J = \sum _ { i = 1 } ^ { \mathrm { c } } \sum _ { j = 1 } ^ { n } u _ { i j } ^ { m } \left\| x _ { j } - \nu _ { i } \right\| ^ { 2 }
$$

$$
\sum _ { i = 1 } ^ { c } u _ { i j } = 1 , j = 1 , 2 . . . , n
$$

在式(2)的约束条件下，可以求得式(1)中目标函数取极小值时相应的隶属度矩阵和聚类中心。对各变量求偏导，并令偏导数为0，联立求得模糊隶属度和聚类中心为

$$
u _ { i j } = \frac { 1 } { \displaystyle \sum _ { k = 1 } ^ { c } ( \frac { \lVert \boldsymbol { x } _ { j } - \boldsymbol { \nu } _ { i } \rVert } { \lVert \boldsymbol { x } _ { j } - \boldsymbol { \nu } _ { k } \rVert } ) ^ { ( \frac { 2 } { m - 1 } ) } }
$$

$$
\nu _ { i } = \frac { \displaystyle \sum _ { j = 1 } ^ { n } ( x _ { j } u _ { i j } ^ { m } ) } { \displaystyle \sum _ { j = 1 } ^ { n } u _ { i j } ^ { m } } , \forall i , j , i = 1 , 2 , 3 , . . . , c \ a n d \ j = 1 , 2 , 3 , . . . , n
$$

根据FCM的基本原理，总结出该算法的步骤如下：

a)设置目标函数的精度 $\mathbf { \Psi } _ { e }$ ，模糊指数 $m$ （ $\mathbf { \Sigma } _ { m }$ 通常取2)和算法最大迭代次数；

b）初始化隶属度矩阵 $u _ { i j }$ 或聚类中心 $\nu _ { i }$ c）由式(3)(4)更新模糊划分矩阵 $u _ { i j }$ 和聚类中心 $\nu _ { i }$ ：d)若目标函数 $\vert J ( \mathrm { t } ) - J ( t + 1 ) \vert ~ < e$ 则迭代结束；否则，跳转执行c)步；e)根据所得到的隶属度矩阵，取样本隶属度最大值所对应类作为样本聚类的结果，聚类结束。

为了获得在不同聚类数下的聚类有效性，寻找最佳的聚类结果，这里使用Xie-Beni指标[15]来对聚类结果进行评价。其定义为

$$
V _ { _ { X B } } ( U , V , c ) = \frac { \displaystyle { \sum _ { i = 1 } ^ { c } } \sum _ { j = 1 } ^ { n } { u _ { i j } ^ { m } \left\| \nu _ { i } - x _ { j } \right\| ^ { 2 } } } { n \times \operatorname* { m i n } _ { i \ne j } \left\| \nu _ { i } - \nu _ { j } \right\| ^ { 2 } }
$$

由上式可知，类内数据相似性越大，类与类之间的分离度越好， $V _ { X B }$ 的值越小，分类结果越好。当指定聚类数 $\mathbf { \Psi } _ { c }$ 的范围[cmin,Cmax]时，可以由上面的指标找到最佳聚类数。对于不同场景的彩色图，利用Xie-Beni指标能够自动选取最佳的 $\mathbf { \Psi } _ { c }$ 值。

对图像做FCM聚类并由Xie-Beni指标选择最佳的聚类数目，得到各个像素点对应各个聚类中心的隶属度，将隶属度归一化到灰度空间，生成聚类引导图。通过聚类之后的彩色图，其高纹理区域的纹理细节降低，边缘细节更加明显，可见彩色图像的聚类信息能够为空洞像素的估计起到指导作用。

![](images/693e6b23806db2365b2dfae0046b9e85bdbc1a6b4d8c067faa39d4917ce74b30.jpg)  
图3聚类引导图

# 1.2基于改进的FMM算法的空洞修复

对大面积空洞的修复是一个难点，修复出来的图像往往过于平滑，边缘细节丢失。本文基于改进的FMM算法，按照每个待修复像素与空洞边界的距离大小来确定修复顺序，在修复边界上的像素点的同时将待修复区域的边界往空洞内部推进，类似于人工修复图像的原则。

FMM算法是由Telea[1提出的，算法的基本思想如下:如图4所示， $\Omega$ 是图像中的待修复区域， $\delta \Omega$ 是该区域的边界， $p$ 是边界上一点，在 $p$ 周围的已知区域内选择一个邻域 $B _ { \varepsilon } ( p )$ ,故$p$ 点的像素值可以由其邻域内的有效像素来估计。

当 $p$ 的邻域足够小时，可以用以下公式来估计空洞点的深度。像素深度的估计公式如下：

$$
D _ { _ p } = \frac { \sum _ { q \in B _ { \varepsilon } ( p ) } w ( p , q ) [ D _ { q } + \nabla D _ { q } ( p - q ) ] } { \sum _ { q \in B _ { \varepsilon } ( P ) } w ( p , q ) }
$$

其中: $q$ 是 $p$ 点的邻域像素； $w ( p , q )$ 是权值函数，用来衡量已知像素点 $q$ 对估计未知像素点 $p$ 的贡献大小; $D _ { \boldsymbol { q } }$ 表示点 $q$ 的深度；$\nabla D _ { q }$ 代表像素点 $q$ 的梯度，用来衡量 $p$ 点与邻域像素相似程度。

在对空洞区域进行修复时需要不断迭代上面的公式，每次迭代仅修复空洞边缘的像素点，使得空洞区域不断收缩，直到空洞被完全修复为止。上述修复过程按照待修复像素点距离初

始边界的距离大小来决定下一个修复的像素点，距离初始边界最近的点最先得到修复。这里用到FMM算法来求解空洞像素点与边界的距离 $T$ ，定义约束式为

$$
\left| \nabla T \right| = 1
$$

![](images/d8827cccaca992a53d23e19cc2897981c4d9fe76ca45b08c10ee6e2e272b4e6d.jpg)  
图4FMM算法修复示意图

对于边界上的像素点 $T = 0$ 。根据文献[17]提出的方法对上式进行求解，解 $T$ 是待修补区域内的像素点到边界的距离。

$\operatorname* { m a x } ( D ^ { - x } T , - D ^ { x } T ) ^ { 2 } + \operatorname* { m a x } ( D ^ { - y } T , - D ^ { y } T ) ^ { 2 } = 1$ (8)其中： $D ^ { - ^ { \mathrm { x } } } T = T ( i , j ) - T ( i - 1 , j ) , D ^ { \mathrm { x } } T = T ( i + 1 , j ) - T ( i , j ) \ ^ { \mathrm { ~ , ~ } } \ y$ 方向的差分类似。

FMM算法能够确保待修复区域边界上像素点按照其距离初始边界的大小顺序依次处理，利用式(6)进行深度估计。

相比于彩色图像，深度图像提供的信息量较少，因此可以利用彩色图像的颜色相似性对缺失的深度图像像素点进行估计。由于彩色图像对深度图像的填补起着引导作用，本文针对深度图像中的大面积空洞区域，对传统的FMM算法进行了改进。将彩色图像的聚类信息引入到缺失深度点的估计中去，结合聚类引导图对式(6)中的权重项进行改造。根据待修复像素点与邻域内的有效像素的相关性，通过构造权值函数来确定相关性大小，具体改进方法：

结合双边滤波器的设计形式，将权重设计为两个权重因子的乘积。两个权重因子分别为

1)空间邻近度因子

$$
w _ { d } \big ( p , q \big ) = \exp ( - \frac { \| \operatorname { \nabla } p - q \| ^ { 2 } } { 2 { \delta _ { d } } ^ { 2 } } )
$$

2)隶属度因子

$$
w _ { u } \left( p , q \right) = \exp ( - \frac { \| u _ { s p } - u _ { s q } \| ^ { 2 } } { 2 \delta _ { u } ^ { 2 } } ) , q \in B _ { \varepsilon }
$$

$$
s = \arg \operatorname* { m a x } _ { i } ( u _ { i p } ) , i = 1 , 2 , . . . , c
$$

其中: $\| \bullet \| ^ { 2 }$ 表示欧氏距离; $p , q$ 分别表示待修复像素点及其邻域像素点的坐标；空间邻近度因子 $w _ { d } \left( p , q \right)$ 和隶属度因子都服从高斯分布，方差分别为 $\delta _ { d } \setminus \delta _ { u }$ ；在隶属度因子中， $s$ 表示像素点 $p$ 的最大隶属度所对应的类；则 $u _ { s q }$ 表示像素点 $q$ 对于类 $s$ 的隶属度； $\mathbf { \Psi } _ { c }$ 为聚类类别数。

因此，式(6)的权重项为

$$
w \big ( p , q \big ) = w _ { d } \big ( p , q \big ) w _ { u } \big ( p , q \big )
$$

从式(9)和(10)可以看出，对于待修复区域边缘上的一点 $p$ ，其邻域内的一点 $q$ 离 $p$ 越近对 $p$ 的贡献越大，隶属度越接近 $p$ ，对 $p$ 的贡献越大。所以 $p$ 点的估计值是由邻域内有效像素的空间距离和隶属度差异共同决定的。

改进的FMM算法伪代码实现如下所示：

改进的FMM算法

1：aΩ是带修补区域的边缘， $p$ 是带修补的空洞像素

2：whileΩ非空   
3： $\mathsf { p } ( \mathbf { x } , \mathbf { y } ) \gets$ head(NarrowBand);   
4:for $( m , n )$ in $( x { + } 1 , y )$ ， $( x , y + 1 )$ ， （20 $( x { - } 1 , y )$ ， (x,y-1)   
5: if $f l a g ( m , n )$ 不等于KNOWN   
6: if $f l a g ( m , n )$ 等于INSIDE   
7: flag(m,n) ←BAND   
8: inpaint $( m , n )$   
9: end if   
10: T(m,n)←min(solve(x-1,y,x,y-1),   
11: solve(x-1,y,x,y+1),   
12: solve(x+1,y,x,y-1),   
13: solve(x+1,y,x,y+1))   
14: insert(m,n) in BAND   
15: end if   
16:end for   
17：end while

首先将像素分为三类，用flag标志记录：BAND：其实就是 $\boldsymbol { \mathcal { \alpha } }$ 上的像素；KNOWN:就是 $\boldsymbol { \mathcal { \alpha } }$ 外部不需要修复的像素;INSIDE:就是 $\boldsymbol { \mathcal { \alpha } }$ 内部的等待修复的像素。 $p$ 为边界上 $T$ 值最小的像素点，NarrowBand为定义的数据结构，用来存放边界上的像素点，按照 $T$ 值升序排列。Head 函数用来提取NarrowBand中 $T$ 值最小的像素点。inpaint函数采用式（6）进行填充。算法先处理 NarrowBand 中 $T$ 值最小的像素点，假设为 $p$ 点，将 $p$ 点类型改为 KNOWN,然后依次处理 $p$ 点的四邻域点 $p i$ 。如果$p i$ 类型为INSIDE，若是则重新计算 $T$ ，修复该点，并更新其$T$ 值,修改该点类型为BAND,加入NarrowBand(这里仍按顺序，即始终保持NarrowBand是按升序排列的)。依次进行，每次处理的都是NarrowBand中 $T$ 最小的像素，直到NarrowBand中没有像素。

# 1.3图像去噪

经过改进的FMM算法修复能够深度图中大部分的空洞点，但是依然存在一些散粒噪声，需要使用滤波算法对图像进行去噪。传统的滤波波算法有高斯滤波，均值滤波，方框滤波，这些方法虽然能够平滑图像，但是往往使图像中物体的边缘变得模糊，丢失大量的有用信息。而基于高斯滤波方法提出的双边滤波能在滤波的同时考虑到图像信息中的图像边缘信息，使图像在正常高斯滤波后很模糊的边缘信息得以保持清晰，并且图像边缘更加平滑。此方法对于彩色和灰度图像的滤波均适用，具有很强的实用性。双边滤波公式如下：

$$
D _ { p } ^ { ^ { \prime } } = { \frac { 1 } { w } } \sum _ { i = 1 } ^ { N ^ { \ast } N - 1 } D _ { q i } w _ { r } \left( p , q i \right) w _ { d } \left( p , q i \right)
$$

$$
w = \sum _ { i = 1 } ^ { N ^ { \ast } N } w _ { r } \left( p , q i \right) w _ { d } \left( p , q i \right)
$$

$$
w _ { r } \big ( p , q i \big ) = \exp ( - \frac { \| D _ { p } - D _ { q i } \| ^ { 2 } } { 2 { \delta _ { r } } ^ { 2 } } )
$$

$$
w _ { d } \left( p , q i \right) = \exp ( - \frac { \parallel p - q i \parallel ^ { 2 } } { 2 { \delta _ { d } } ^ { 2 } } )
$$

对于深度图中的一点 $\ d _ { p } , \ d _ { D _ { p } }$ 为其深度值， $\vec { D _ { p } } ^ { ^ { \prime } }$ 是滤波处理后像素点的估计值； $N ^ { * } N$ 为待修复像素点的邻域窗口大小;$D _ { q i }$ 是窗口中像素点 $q i$ 的深度值; $\| \bullet \| ^ { 2 }$ 表示欧氏距离；亮度相似度因子 $w _ { r } \big ( p , q i \big )$ 和空间邻近度因子 $w _ { d } \left( p , q i \right)$ 都服从高斯分布，方差分别为 $\delta _ { r }$ 、 $\delta _ { d }$ ； $w$ 为归一化常数。

双边滤波器的加权系数是空间邻近度因子 $w _ { d }$ 和亮度相似度因子 $w _ { r }$ 的乘积。像素点与中心点之间欧氏距离越大，空间邻近度因子越小，两像素亮度值之差越大，亮度相似度因子越小。在图像变化平缓的区域，邻域内像素亮度值接近，此时双边滤波类似于高斯低通滤波器；在图像变化剧烈的区域，滤波器利用边缘点附近亮度值相近的像素点的平均亮度值代替原亮度值。因此，双边滤波器既平滑滤波了图像，又保持了图像的边缘。

为了提高图像的修复精度，平滑深度数据，本文在传统双边滤波方法的基础上，引入彩色图像提供的信息，提出改进的双边滤波算法，用该方法去除图像中的噪声。将原空间邻近度替换为隶属度因子：

$$
w _ { u } \left( p , q i \right) = \exp ( - \frac { \| u _ { p } - u _ { i } \| ^ { 2 } } { 2 { \delta _ { u } } ^ { 2 } } )
$$

改进的双边滤波公式如下：

$$
\stackrel { \cdot } { D _ { p } ^ { \cdot } } = \left\{ \begin{array} { l l } { \frac { 1 } { w } \stackrel { N ^ { * } N - 1 } { \sum } D _ { q i } w _ { r } \big ( p , q i \big ) w _ { u } \big ( p , q i \big ) , D _ { p } = 0 } \\ { D _ { p } , D _ { p } \neq 0 } \end{array} \right.
$$

其中：

$$
w = \sum _ { i = 1 } ^ { N ^ { \ast } N } w _ { r } \left( p , q i \right) w _ { u } \left( p , q i \right)
$$

本文改进的双边滤波算法只针对深度图中的空洞像素点，对其采用式(18)进行像素填充，用其邻域内的有效像素点来估计像素值，不影响非缺失区域的像素点。改进的算法考虑到了彩色图像提供的信息，增加了像素点之间相似度的影响，也就是邻域的像素点如果和中心像素点的相似度较高，那么权值在高斯权值的基础上增加一个相对较大的权值，相反地，如果相似度不高，那么权值在高斯权值的基础上再加上一个小的权值。

因此权值系数不再单纯依赖位置关系，更依赖于相似度关系。  
在修复空洞点的同时也能很好地保留边缘信息。

# 2 实验结果与比较

为了验证本文提出的算法有效性，在Windows8操作系统的PC机上进行实验，硬件配置是2.60GHzInter(R)Core(TM)i5-4210MCPU,8GBRAM。实验平台是VisualStudio2013,基于计算机视觉库Opencv3.0，使用 $\mathrm { C } { + } { + }$ 编程实现。本文利用Middlebury库中提供的数据集进行实验，并将处理结果与JBF算法，FMM算法的处理结果从主观视觉上和客观指标上比较修复质量。

# 2.1对人造空洞的修复结果

实验1对正常图像添加人工深度空洞，验证算法对于仿真空洞的修复效果。在Middlebury 库[17]中提供的Art 数据集上添加人造空洞，分别用JBF算法，FMM算法以及本文提出的算法对空洞区域进行修复，然后比较修复前的图像以及三种方法修复后的图像与原始正常图像之间的差异。为了量化修复结果，这里采用常用的均方误差(MSE)和峰值信噪比（PSNR）来比较。

给出三个算法的修复结果如图5所示，表2给出相应的均方误差和峰值信噪比。

![](images/6f77dc8c145b0c6a16a3ef979a342ec4aed6be50a976c6c4e32cd1f8653c8e03.jpg)  
图5三种算法对人工空洞的修复效果比较

从左到右，(a)为原始彩色图，(b)为添加人工空洞的深度图，(c)为空洞区域局部放大图，(d)为 JBF 算法的修复效果，(e)为FMM算法的修复结果，(f)为本文算法的修复结果

从图5的修复结果可以看出，在深度图的代表性区域，经放大后的物体边缘处，JBF算法和FMM算法虽然能够保留物体的边缘，但是还原出来的边缘轮廓很模糊。而本文提出的算法不仅还原了物体轮廓，而且边缘更加清晰，对于缺失区域的估计更准确。从均方误差和峰值信噪比两个评价指标上看，本文算法的均方误差降低了 $9 9 . 6 1 \%$ ，,峰值信噪比提高了 $9 0 . 0 9 \%$ 。从统计结果和视觉直观效果来看，本文算法的修复效果优于

JBF 算法和FMM算法。

表2添加人工空洞的Art数据集MSE和PSNR评价  

<html><body><table><tr><td rowspan="2">算法</td><td rowspan="2">MSE</td><td rowspan="2">MSE 降低率/%</td><td rowspan="2">PSNR</td><td rowspan="2">PSNR 提高率/%</td></tr><tr><td></td></tr><tr><td>待修复</td><td>138.0630</td><td></td><td>26.7300</td><td></td></tr><tr><td>JBF</td><td>2.2609</td><td>98.37</td><td>44.5881</td><td>66.78</td></tr><tr><td>FMM</td><td>1.7466</td><td>98.74</td><td>45.7090</td><td>70.97</td></tr><tr><td>本文算法</td><td>0.5385</td><td>99.61</td><td>50.8186</td><td>90.09</td></tr></table></body></html>

# 2.2对自然空洞的修复结果

为了验证本文算法对自然生成的空洞的修复效果，实验2选取Middlebury库中提供的Laundry、Moebius和Reindeer数据集，分别用三种算法对原始深度图进行修复，修复效果如图6所示。为了量化修复结果，实验2同样计算了三组图像与原图的均方误差和值信噪比，并给出本文算法相对于JBF算法和FMM算法在均方误差上的降低率和在峰值信噪比上的提高率，结果如表3和4所示。

表3Laundry、Moebius 和Reindeer 数据集MSE 评价  

<html><body><table><tr><td>图像</td><td>JBF</td><td>FMM</td><td>本文算法</td><td>MSE 降低率/%</td></tr><tr><td>Laundry</td><td>49.0468</td><td>56.2673</td><td>38.8339</td><td>20.82/30.98</td></tr><tr><td>Moebius</td><td>47.6537</td><td>46.7530</td><td>33.6487</td><td>29.39/28.03</td></tr><tr><td>Reindeer</td><td>53.6087</td><td>58.0440</td><td>44.8426</td><td>16.35/22.74</td></tr></table></body></html>

表 4Laundry、Moebius 和Reindeer 数据集PSNR评价  

<html><body><table><tr><td rowspan="2">图像</td><td rowspan="2">JBF</td><td rowspan="2">FMM</td><td>本文</td><td>PSNR</td></tr><tr><td>算法</td><td>提高率/%</td></tr><tr><td>Laundry</td><td>31.2247</td><td>30.6282</td><td>32.2387</td><td>3.25/5.26</td></tr><tr><td>Moebius</td><td>31.3498</td><td>31.4327</td><td>32.8611</td><td>4.82/4.54</td></tr><tr><td>Reindeer</td><td>30.8385</td><td>30.4932</td><td>31.6139</td><td>2.51/3.68</td></tr></table></body></html>

从图6的处理结果可以看出在边缘完整性以及边缘强度上，本文提出算法具有明显的优势；在定量评价指标上，从表3和表4可以看出，本文算法相对于JBF 算法和FMM算法，具有更小的均方误差和更大的峰值信噪比,再次证明了该算法的可靠性。

# 3 结束语

本文针对Kinect采集到的深度图存在大面积空洞的问题，提出了一种结合彩色图像聚类信息，利用聚类信息来引导空洞区域填充的修复算法,从缺失像素点的邻域有效区域获得该像素点的有效估计。实验结果表明，由于增加了彩色图像提供的信息，该算法能够有效修复深度中的空洞，相比JBF算法和FMM算法，从视觉上来看，该算法不仅能恢复出物体边缘，而且边缘更加清晰；从定量评价指标上来看，该算法降低了均方误差，并且有更高的峰值信噪比。但该算法还存在不足，由于该算法需要对彩色图像进行FCM聚类，消耗时间较长。

![](images/2990c20e66e7bf1d815a664ea61d31dae2b9026cb87419cda9130a08ecd29f60.jpg)  
图6三种算法对Laundry、Moebius 和Reindeer 深度图的处理结果

# 参考文献：

[1]Sriparna Sa,RimitaL,AmitK,et al.HMM-basedgesture recognition system using kinect sensorfor improvised human-computer interaction [Cl//Proc of International Joint Conference on Neural Networks.2017:2776-2783.   
[2]Atif Ar, Syed A,Azhar S,et al. Underwater 3D scene reconstruction using kinect v2 based on physical models for refraction and time of flight correction [J].IEEE Access,2017,5:15960-15970.   
[3]NadiaF,Dong Haiwei,El SaddikA.From sense to print: towards automatic 3D printing from 3D sensing devices [C]// Systems,Man,and Cybernetics. 2013:4897-4904.   
[4]Fu Jingjing，Miao Dan，Yu Weiren，et al.Kinect-Like Depth Data Compression [J].IEEE Trans on Multimedia,2013,15 (6):1340-1352.   
[5]肖志云，张文霞，姜玉莉．基于快速行进法的快速图像修复算法[J]. 计算机应用,2007,27(s2):60-61.   
[6]Vijayanagar K R,Loghman M,Kim Joohee.Refinement of depthmaps generated by low-cost depth sensors [C]// Proc of International SoC Design Conference.2013:355-358.   
[7]Salgado L.Efficient spatio-temporal hole filling strategy for Kinect depth maps [Cl// Proc of SPIE,The International Society for Optical Engineering, 2012:13.   
[8]Park MK,Ho C J,Yeop JI,et al.An iterative joint bilateral filtering for depth refinement of a 3D model [C]//Proc of SIGGRAPH. 2011: No.19.   
[9]Yang Qingqing,Wang Lianghao,Li Dongxiao,et al.Hierarchicaljoint bilateral filtering for depth post-processing [C]// Proc of International Conference on Image & Graphics.2011:129-134.   
[10] KopfJ,Cohen MF,Lischinski D,et al. Joint bilateral upsampling[J].ACM Trans on Graphics,2007,26 (3):Article No.96.   
[11]Hu Jinhui,HuRuimin,Wang Zhongyuan,etal.Color image guided locality regularized representation for Kinect depth holes filling [C]// Visual Communications and Image Processing. 2014: 1-6.   
[12]王勇，蒋爱民，胥立波．基于K-means的Kinect深度图像空洞修复算法 [J]．微处理机,2015,4:42-44,48.   
[13]赵旭.Kinect深度图像修复技术研究[D].大连：大连理工大学,2013.   
[14]王奎，安平，张兆杨，等.Kinect深度图像快速修复算法[J]．上海大学

学报：自然科学版,2012,18(5):454-458. [15]Xie XL and Beni G.A Validity Measure for Fuzzy Clustering[J].IEEE Trans on Pattern Analysis & Machine Intelligence,1991,13: 841-847. [16] Alexandru T.An Image Inpainting Technique Based on the FastMarching Method [J]. Journal of Graphics Tools,2004,9(1): 23-34. [17] Sethian JA.A fast marching level set method for monotonicallyadvancing fronts[J].Proceedings of the National Academy of Sciences of the United States of America,1996,93 (4): 1591. [18]Middlebury datasets [DB]. http://vision.middlebury.edu/stereo/data/.