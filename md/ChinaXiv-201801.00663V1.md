# 技术方法

# 基于图割的肺4D-CT图像超分辨率重建

陈 瑾1²，申正文1,²，席卫文1²,张 煜1,2  
南方医科大学'生物医学工程学院,广东省医学图像重点实验室，广东广州510515

摘要：肺4D-CT在当今的肺癌放射治疗中起着重要的作用。本文提出了一种基于全局图割方法的肺4D-CT图像超分辨率重建方法,来提升肺4D-CT图像的质量。该方法首先在最大后验马尔科夫随机场框架下建立一个肺4D-CT各相位高分辨率图像重建的全局能量函数,然后，将该能量函数转化成图的表达方式，最后用图割方法和α- $\cdot \beta$ swap算法优化能量函数来恢复高分辨率图像细节结构。实验结果表明,在恢复图像的细节方面，本文方法要优于传统的线性插值和凸集投影超分辨率重建算法。

关键词:肺4D-CT;超分辨率重建;图割;α-βswap

# Super-resolution reconstruction for 4-dimensional computed tomography of the lung using graph cuts

CHENJinl²,SHENZhengwen1²,XI Weiwenl²,ZHANG $Y u ^ { { 1 , 2 } }$ （204号   
SchoolofodicaleeigGagdonroncialKybotoryfedicalgouedicalesityg   
510515, China

Abstract: Four-dimensionalcomputer tomography (4D-CT)has a great valuein lung cancer radiotherapy for itscapability in providing lung information with respiratory motion. We employed a global graph cuts super-resolution (SR)reconstruction method toreconstruct high-resolution lung 4D-CT images.First,the high-resolution imagesreconstruction energy function was built based on a Maximum a posteriori Markov Random Field (MAP-MRF) formulation.The energy function was then transformed to a graph formulation, which was solved using graph cut algorithm. Allthe evaluation results showed that this approach outperformed the ine interpolation and projection onto convex sets (POCS)approach with an improved structural clarity.

Key words: 4-dimensional computer tomography; super resolution; graph cuts; $\alpha { - } \beta$ swap

肺4D断层扫描(4D-CT)是当今的肺癌放射治疗中必不可少的元素。肺4D-CT图像在肺癌靶向治疗中捕获肺部随呼吸运动的信息，能够指导精确放射治疗。然而，由于存在一些因素，例如人体能承受的放射剂量有限，成像硬件以及时间限制等导致肺4D-CT图像在Z轴方向上的分辨率较低，并且图像常伴有伪影和噪声。而在大多数临床工作中，常需要高分辨率的肺4D-CT图像来引导放射治疗，因此提高肺4D-CT图像的工作十分重要[1]。

本文的主要目的是通过超分辨率重建技术来提高肺4D-CT图像Z轴的分辨率。超分辨率重建技术常用的方法是结合多幅低分辨率图像提供的不同空间信息来恢复高分辨率图像。例如：迭代反投影算法[2,POCS算法3等，这些算法的结果严重依赖配准结果的精度，并且需要不断地迭代以重建出高分辨率图像。超分辨率重建的另一类方法是基于学习的方法。该方法主要是通过训练图像学习高分辨率图像与低分辨率图像之间的关系,来恢复低分辨率图像的细节信息。例如Yang等4人提出基于稀疏表达的方法来重建高分辨率图像。基于学习的方法可以得到较好的结果，但是依然存在一个弊端就是需要高分辨率数据作为训练集，因此基于学习的方法在肺4D-CT数据上并不适用。目前也有一部分超分辨率重建方法是基于MAP-MRF框架来构建超分辨率重建的模型[5]。例如,Wallach等提出基于最大后验的超分辨率重建方法来提高正电子断层成像质量。基于MAP-MRF方法的优势在于能较灵活地结合多种形式的正则化项来得到好的重建结果，但是传统的估计最大后验的方法求解常需要结合迭代过程，而且多数情况下会导致非凸集优化问题[]

本文主要工作是提出一种基于图割方法的超分辨率重建方法来提高肺4D-CT图像在Z轴方向上的分辨率。本文的方法分为两个步骤。首先，在MAP-MRF框架下构建肺4D-CT图像超分辨率重建的模型，并构建成全局图模式，然后，用图割方法求解能量函数的最优值。为了提高求解速度和精度,我们采用 $\alpha - \beta$ swap方法8进行图割优化。实验结果显示，与经典的线性插值和POCS超分辨率重建算法相比，本文的方法在视觉和定量方面都获得了更优的结果。

# 1方法

1.1 图割

能量函数优化技术在计算机视觉领域已有长时间发展,图割是图像能量函数优化常用方法之一[9]。假设$\scriptstyle { g = ( V , E ) }$ 表示带权图，顶点称为终端，V是顶点的集合， $E$ 是边的集合，图中有两个与其他顶点相连的终端，该图的一个切割就是 $E$ 的一个子集，使得两个终端之间没有通路连接。图割问题就是要寻找这样的一个切割，使得中包含的边的权值最小。本文将超分辨率重建问题转化成图割优化问题。假设给图中所有的像素点都赋有标签，找到像素点最佳的标签匹配值，使图像能量函数值最小，最佳的标签匹配即为重建出高分辨率图像的像素值。

# 1.2图像退化模型

图像退化原理[0]如图1所示。

![](images/9b388089a2bc17a25a0521c13cd6edf2763b38875f40068e087e35885ec1bb4e.jpg)  
图1图像退化模型 Fig.1 Image degradation model.

图像退化模型可以用公式(1)表示为：

$$
g _ { k } = D H _ { K } M _ { k } f + n _ { k } ,
$$

其中 $g _ { k }$ 表示第 $\mathbf { k }$ 幅图像, $f$ 是要重建出的高分辨率图像。 $M _ { k }$ 是 $f$ 相对于 $g _ { \boldsymbol { k } }$ 的几何变换矩阵， $H _ { k }$ 为光学模糊矩阵，是由光学系统本身、成像系统与原始场景的相对运动以及低分辨率传感器的点扩散函数(pointspreadfunction,PSF)形成的；D为降采样矩阵； $n _ { k }$ 则表示系统加性噪声。

超分辨率重建过程是图像退化过程的逆问题，其原理就是利用多帧关于同一场景(不同相位)的有相互位移的低分辨率图像，重建高分辨率清晰的图像。在本文中，我们在MAP-MRF框架下构建图像超分辨率重建能量函数，如公式(2)所示：

$$
E \Big ( f / g \Big ) = \sum _ { k } \Big | \Big | D H _ { k } M _ { k } f - g _ { k } \Big | \Big | ^ { 2 } + \sum _ { p , q \in N } V _ { p , q } ( f _ { p } , f _ { q } )
$$

其中 ${ \bf \Phi } _ { p , q } ^ { \prime } \Bigl ( f _ { p } , f _ { q } \Bigr ) .$ 为平滑项， $\mathbf { N }$ 为邻域， $f _ { p } , f _ { q }$ 为像素点 $p , q$ 的灰度值。

1.3基于图割的肺4D-CT超分辨率重建

1.3.1 全局图构建 2001年Kolmogorov等]提出图割方法用于能量函数优化后，图割方法就常用于求取多维图像能量函数的全局最小值。考虑到4D-CT数据的特点，一个数据包含多相位低分辨率图像，且每相位图像之间有着相互的联系。因此本文提出了一个全局图割方法来优化针对4D-CT数据建立的图像能量函数。首先将4D-CT图像用一个全局图表示，然后在MAP-MRF框架下构建多相位图像能量函数，优化求解像素点最佳的标签匹配值。全局图可以用图2表示。

![](images/3123ce9a1e5349014f8cd57ff4c0f4ae22fff63279fe42e2685e56c01d81b515.jpg)  
图2肺4D-CT图像全局图构建 Fig.2 An example of global graph represents 4D-CT data.

1.3.2能量函数构建图割方法能优化能量函数，前提是函数必须是图的表达形式[1],，所以我们构建包含全部相位的全局图形式的能量函数。公式(3)可以写为：

$$
\begin{array} { c } { { E \Big ( f _ { k } \Big ) = \displaystyle \sum _ { p \in S } \sum _ { k = 0 } ^ { T } ( h ^ { * } f _ { k } \big ( p \big ) - F _ { k } ^ { B } ( p ) ) ^ { 2 } + } } \\ { { \lambda \displaystyle \sum _ { \kappa } ^ { T } = \supset \sum _ { p , \ q \in N } V _ { p , \ q } ( \ f _ { k } \left( p \right) , \ f _ { k } \left( q \right) ) } } \end{array}
$$

其中 $f _ { k }$ 为待求解的各相位高分辨率重建图像。 $S$ 为初始高分辨率图像像素集， $. T$ 表示相位数， $p$ 为高分辨率图像上的像素点， $h$ 表示 PSF, $\lambda$ 为平滑项系数。$V _ { p , q } ( f _ { k } ( p ) , f _ { k } ( q ) )$ 表示平滑项,可以保证重建出的每一相位高分辨率图像保持平滑， $N$ 表示邻域。我们设定

$V _ { p , q } \big ( f _ { k } \big ( p \big ) , f _ { k } \big ( q \big ) \big ) = \operatorname* { m i n } { \left( \tau , \big | f _ { k } ( p ) - f _ { k } ( q ) \big | \right) }$ 其中 $\tau$ 为阈值大小。

$\boldsymbol { F } _ { k } ^ { B }$ 表示相位K通过三次样条插值得到的初始高分辨率图像 $f _ { k 0 }$ ，采用Demons配准方法分别向其他相位的低分辨率图像上投影，然后根据投影位置插值重建的高分辨率观察图像[7]。

为了使式(4)可以采用图割的方法优化求解，我们对 $\dot { \iota } ^ { * } f _ { k } ( \boldsymbol { p } )$ 进行简化[12]，卷积 $h ^ { \ast } f _ { k } ( p )$ 可以写成：

$$
h ^ { \ast } f _ { k } ( p ) = w _ { p p } f _ { k } ( p ) + \sum _ { r \in N _ { r } } w _ { p r } f _ { k } ( r )
$$

其中 $\dot { \boldsymbol { r } }$ 是像素p的邻域 $\cdot N ,$ 内的点。这里假设邻域像素点对中心点的影响较小,我们设定 ${ { \bf \dot { \rho } } _ { w _ { p p } } }$ 值为 $1 , w _ { p r }$ 值为0，则简化后全局图能量函数如下：

$$
E { \big ( } f _ { k } { \big ) } =
$$

$$
\sum _ { p \in S } \sum _ { k = 0 } ^ { T } ( f _ { k } \big ( p \big ) - F _ { k } ^ { B } ( p ) ) ^ { 2 } + \lambda \sum _ { k = 0 } ^ { T } \sum _ { p , q \epsilon N } V _ { p , q } ( f _ { k } \big ( p \big ) , f _ { k } \big ( q \big ) )
$$

1.3.3全局图能量函数优化图割方法有两种最小化算法,swap算法和expansion算法[8]。本文中我们选择 $\alpha - \beta$ swap算法来优化能量函数 $( 6 )$ 。 $\alpha - \beta$ swap算法主要是通过计算数据项 $\sum _ { p \in S } \sum _ { k = 0 } ^ { T } ( f _ { k } \big ( p \big ) - F _ { k } ^ { B } ( p ) ) ^ { 2 } | \mathrm { \vec { f } }$ 直,如果数据项满足条件，那么像素点的标签由 $\dot { \alpha }$ 变成 $\beta$ ，反之保持原来的标签，通过这样的策略求解最佳的标签与像素点的匹配，即最优的高分辨率图像。

# 1.4基于全局图割方法的肺4D-CT图像超分辨率重建

本文基于全局图割方法的肺4D-CT图像超分辨率重建步骤如下：

输入：肺4D-CT的低分辨率图像;(1)由肺4D-CT数据获得不同相位的低分辨率图像序列；(2)将不同相位的低分辨率图像均进行插值，得到初始的高分辨率图像；(3)根据图像退化模型建立能量函数式(2)；(4)选取任意一相位图像插值得到的初始高分辨率图像的像素值集作为所有像素点匹配的初始标签集；(5)计算各相位的投影重建高分辨率观察图像 $F _ { K } ^ { B }$ ，构建全局图的能量函数式(6);(6)通过图割方法和a $\cdot \beta$ swap算法优化求解建立的全局图能量函数式(6);输出：肺4D-CT的高分辨率图像。

# 2结果

本文采用DIR实验室提供的一个公共可用的肺

4D-CT数据集进行方法评估[13]。该数据集由10组肺4D-CT数据组成。每组肺4D-CT包含10个相位，包括极端的吸气和呼气的末端。对于数据1到数据5,图像大小分别为 $2 5 6 \times 2 5 6$ ,层内的体素尺寸范围从 $0 . 9 7 \mathrm { m m } \times$ $0 . 9 7 ~ \mathrm { m m } { \sim } 1 . 1 6 ~ \mathrm { m m } { \times } 1 . 1 6 ~ \mathrm { m m }$ 之间。数据6到数据10,图像的大小为 $5 1 2 { \times } 5 1 2$ ,层内的体素尺寸均为 $0 . 9 7 ~ \mathrm { m m } \times$ $0 . 9 7 { \mathrm { m m } }$ 。对于所有的数据,层间间距均为 $2 . 5 \mathrm { m m } _ { \mathrm { o } }$

# 2.1视觉评价

图3显示了典型的冠状面和矢状面用不同方法重建的结果。第一行和第三行从左到右分别为冠状面和矢状面由线性插值,POCS算法和本文方法重建结果，第一行和第三行中矩形里的内容被放大显示在第二行和第四行。我们可以看出，与线性插值和POCS算法结果相比，本文方法重建出来的结果要更加清晰。

![](images/8d54bd5ff4e3eacc0a9c56e4abac112cb4e6e4cb5a1f79e669e1d1af7d86e4fc.jpg)  
图3分辨率增强的冠状面和矢状面图像重建结果

Fig.3Visual comparison of reconstruction results of coronal and sagittal images.The results given by linear interpolation, POCS method and our proposed method are shown in the first and third rows,respectively.The area of red box are enlarged and shown in the second and fourth rows.

# 2.2量化评价

我们采用平均梯度[14]和边缘宽度[15]作为量化评价指标。

平均梯度能反映图像微小细节反差变化的速率，能表征图像的相对清晰程度。值越大，清晰度就越高，可用公式表示为：

$$
\nabla f = \frac { 1 } { ( M - 1 ) ( N - 1 ) } \sum _ { i = 1 } ^ { M - 1 } \sum _ { j = 1 } ^ { N - 1 } \sqrt { \frac { \nabla _ { i } ^ { 2 } f \big ( i , j \big ) + \nabla _ { j } ^ { 2 } f ( i , j ) } { 2 } }
$$

其中， $f { \big ( } i , j { \big ) } , \nabla f _ { i } ( i , j ) \mathbb { \hat { \mathcal { F } } } \mathbb { H } \nabla f _ { j } ( i , j )$ 分别是像素点灰度以及其在行、列方向上的梯度;M和N分别为图像的行数和列数。我们分别对10组肺4D-CT数据用不同的方法重建出来的高分辨率图像进行平均梯度计算。结果如表1所示。为了使结果对比的更明显，我们还列出了平均梯度的增加百分比。较线性插值和POCS算法，我们的方法重建出来图像的平均梯度明显提高，说明图像更清晰，细节保持更好。

表1重建结果的平均梯度值 Tab.1 Average gradient value of reconstruction results by different algorithms   

<html><body><table><tr><td rowspan="2">Data</td><td rowspan="2">Linear</td><td rowspan="2">POCS</td><td rowspan="2">Our method</td><td colspan="2">Percent increase %</td></tr><tr><td>Our method/Linear</td><td>Our method/POCs</td></tr><tr><td>Data0</td><td>6.86</td><td>7.75</td><td>8.60</td><td>20.23</td><td>9.88</td></tr><tr><td>Data1</td><td>6.76</td><td>7.68</td><td>8.41</td><td>19.61</td><td>8.68</td></tr><tr><td>Data2</td><td>6.68</td><td>7.59</td><td>8.30</td><td>19.52</td><td>8.55</td></tr><tr><td>Data3</td><td>6.78</td><td>7.74</td><td>8.51</td><td>20.32</td><td>9.05</td></tr><tr><td>Data4</td><td>6.72</td><td>7.78</td><td>8.41</td><td>20.09</td><td>7.40</td></tr><tr><td>Data5</td><td>6.73</td><td>7.85</td><td>8.46</td><td>20.44</td><td>7.21</td></tr><tr><td>Data6</td><td>6.72</td><td>7.86</td><td>8.41</td><td>20.09</td><td>6.53</td></tr><tr><td>Data7</td><td>6.59</td><td>7.72</td><td>8.22</td><td>19.83</td><td>6.08</td></tr><tr><td>Data8</td><td>6.57</td><td>7.61</td><td>8.06</td><td>18.48</td><td>5.23</td></tr><tr><td>Data9</td><td>6.67</td><td>7.71</td><td>8.27</td><td>19.34</td><td>6.77</td></tr><tr><td>Mean</td><td>6.81</td><td>7.73</td><td>8.37</td><td>19.79</td><td>7.54</td></tr></table></body></html>

边缘宽度是衡量空间分辨率的量化参数。边缘宽度主要反映所选边缘‘锐利'程度，其计算公式(8)如下：

$$
w i d \operatorname { t h } [ e d g e ] = \frac { 4 . 4 } { a }
$$

其中a又双曲线函数y(x)=1+exp(-a(x-c)) 拟合得到。函数中 $y ( x )$ 为像素点灰度， $x$ 为像素点坐标， $c$ 为采集的像素点中心。

我们分别对10组数据进行量化评价，在线性插值，POCS算法和文本方法重建出来的图像上局部选取3个边缘区域A，B，C(图4)。

根据公式(8)，我们对三种方法重建得到高分辨率图像上取3个边缘区域进行边缘宽度计算，结果如下表2所示。很明显我们方法与线性插值和POCS算法相比较，边缘宽度都有了一定的减小，边缘细节有所增强。

# 3结论

高分辨率图像在当今的医疗和科研中起着重要的作用。如可以提高分割精度、改进可视化效果等[16]。图像处理技术可以提高图像的分辨率，例如基本的插值方法可以改变图像大小。但是这些插值方法会使图像产生一些伪影，而且图像中没有增加额外的信息。超分辨率重建技术可以有效地提高图像分辨率。肺4D-CT图像在肺癌的方式在治疗中发挥着重要的作用，它可以提供肺部随呼吸运动的信息，有利用跟踪肿瘤运动。提高肺4D-CT图像的质量，有利于实施更精确的肿瘤放射治疗。

![](images/ab9d1ddde186833e269da27f8fbff2d768989e85c90c87fa0157ddcdd942420f.jpg)  
图43个边缘区域位置Fig.4 Three edge area location.

本文采用了一种基于全局图割方法的超分辨率重建方法来提高肺4D-CT图像的Z轴分辨率。该方法主要特点是以MAP-MRF框架建立一个肺4D-CT多相位高分辨率图像重建的全局能量函数，然后用图割方法和$\alpha - \beta$ swap算法优化能量函数从而重建高分辨率图像。本方法的优势在于不需要迭代求解，同时由于图割方法本身的特性能获得全局最优解。另外，采用的马尔科夫正则化项，有助于保持图像的平滑，降低重建图像的噪声。实验结果证明,本文方法相比与传统的线性插值和POCS算法，该方法无论是在视觉上还是在量化评估都优于以上的两种方法。

表2重建结果的边缘宽度值 Tab.2 Edge width value of reconstruction results by different algorithms   

<html><body><table><tr><td rowspan="2">Data</td><td colspan="3">A</td><td colspan="3">B</td><td colspan="3">C</td></tr><tr><td>Linear</td><td>POCS</td><td>Our method</td><td>Linear</td><td>POCS</td><td>Our method</td><td>Linear</td><td>POCS</td><td>Our method</td></tr><tr><td>1</td><td>4.81</td><td>4.56</td><td>3.66</td><td>9.92</td><td>7.68</td><td>6.38</td><td>5.51</td><td>5.15</td><td>4.47</td></tr><tr><td>2</td><td>4.77</td><td>4.54</td><td>3.54</td><td>10.10</td><td>7.87</td><td>6.61</td><td>7.92</td><td>6.41</td><td>5.73</td></tr><tr><td>3</td><td>4.91</td><td>4.66</td><td>3.65</td><td>12.13</td><td>8.83</td><td>7.21</td><td>4.79</td><td>4.55</td><td>3.48</td></tr><tr><td>4</td><td>5.12</td><td>4.79</td><td>3.78</td><td>9.63</td><td>7.48</td><td>6.32</td><td>6.28</td><td>5.45</td><td>3.99</td></tr><tr><td>5</td><td>4.89</td><td>4.68</td><td>3.65</td><td>9.16</td><td>5.44</td><td>5.44</td><td>5.77</td><td>5.16</td><td>4.26</td></tr><tr><td>6</td><td>5.05</td><td>4.80</td><td>3.41</td><td>9.05</td><td>6.94</td><td>5.49</td><td>5.69</td><td>5.17</td><td>4.29</td></tr><tr><td>7</td><td>4.73</td><td>4.41</td><td>3.51</td><td>9.77</td><td>7.38</td><td>6.37</td><td>5.90</td><td>5.43</td><td>4.57</td></tr><tr><td>8</td><td>4.49</td><td>4.28</td><td>3.08</td><td>7.71</td><td>6.00</td><td>4.65</td><td>8.68</td><td>6.91</td><td>5.99</td></tr><tr><td>9</td><td>5.22</td><td>5.12</td><td>4.28</td><td>8.51</td><td>6.99</td><td>4.32</td><td>5.21</td><td>5.12</td><td>4.52</td></tr><tr><td>10</td><td>5.27</td><td>5.06</td><td>4.16</td><td>10.1</td><td>7.54</td><td>5.30</td><td>4.91</td><td>4.40</td><td>4.16</td></tr><tr><td>Mean</td><td>4.93</td><td>4.69</td><td>3.67</td><td>9.61</td><td>7.22</td><td>5.80</td><td>6.07</td><td>5.37</td><td>4.55</td></tr></table></body></html>

# 参考文献：

[1］张书旭,周凌宏，陈光杰,等.4D-CT重建及其在肺癌放疗中的应用研 究进展[J].中国辐射卫生,2008,17(3):375-7.   
[2]Peleg S,Keren D, Schweitzer L. Improving image resolution using subpixel motion[J].Pattern Recogn Lett,1987,5(3): 223-6.   
[3]Stark H,Oskoui P.High-resolution image recovery from imageplane arrays,using convex projections[J].J Opt Soc Am A,1989,6 (11):1715-26.   
[4]Yang J,Wright J,Huang TS,et al. Image super-resolution via sparse representation [J]. IEEE Trans Image Process，2010,19(11): 2861-73.   
[5]Pickup LC.Machine learning in multi-frame image super-resolution [J].Oxford University,2008.   
[6]Wallach D,Lamare F,Roux C,et al. Incorporation of respiratory motion estimation within a map super-resolution algorithm for image enhancement in 4D pet[C]//ISBI.IEEE Press,20O9: 931-4.   
[7]Mudenagudi U, Singla R,Kalra P,et al. Super resolution using graph-cut[C]//ACCV, Springer-Verlag,2006:385-94.   
[8]Delong A,Osokin A, Isack HN,et al. Fast approximate energy minimization with label costs [J].Int J Comput Vis,2012,96(1): 1-27.   
[9]Birchfield S,Tomasi C.Depth Discontinuities by Pixel-to-Pixel Stereo[C]//Int JComput Vision.1998:1073-80.   
[10] Park SC,Park MK,Kang MG. Super-resolution image Reconstruction: a technical overview[J].IEEE Signal Process Mag,2003,20 (4): 21-36.   
[11]Kolmogorov V, Zabih R.What energy functions can be minimized via graph cuts?[C]// In ICCV,2003.   
[12]Zhang DX,Jodoin PM,Li CH,et al.Novel graph Cuts method for Multi-Frame Super-Resolution[J].IEEE Signal Process Lett,2015, 22(12): 2279-83.   
[13]Castillo R,Castillo E,Guerra R,et al.A framework for evaluation of deformable image registration spatial accuracy using large landmark point sets[J].Phys Med Biol,2009,54(7):1849-70.   
[14]徐美芳,刘晶红.基于边缘保持的航拍图像凸集投影超分辨率重建算 法[J].液晶与显示,2010,25(6):873-8.   
[15]Greenspan H, Oz G,Kiryati N,et al. MRI inter-slice Reconstruction using super-resolution [J].Magn Reson Imaging，20O2,20(5): 437-46.   
[16]Ibragimov B,Prince JL,Murano EZ,et al. Segmentation of tongue muscles from super-resolution magnetic resonance images[J].Med Image Anal,2015,20(1): 198-207.

(编辑：孙昌朋)