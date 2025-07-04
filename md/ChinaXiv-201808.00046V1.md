# 基于矢量相似性的多元滤波方法研究\*

何晓军‘，徐爱功ʰ，李玉b

(辽宁工程技术大学 a.创新实践学院;b.测绘与地理科学学院，辽宁 阜新 123000)

摘要：为了避免彩色图像滤波时排序难题，在探究矢量相似性的基础上，提出一种针对彩色图像的多元滤波方法。首先，在RGB 彩色空间中，利用彩色矢量间距离和角度定义其相似性测度，以刻画与人类视觉感知相一致的彩色相似性；其次，以上述彩色相似性为准则设计并构建一种彩色多元滤波方法，并就其相关参数对滤波性能的影响进行了深入分析和研究；最后，为了验证提出方法的有效性，将其应用于标准彩色影像和彩色遥感影像滤波。实验结果可知，提出的方法不仅有效解决了传统滤波方法的排序难题，而且克服了因滤波使图像模糊，边缘不清等问题；另外，将提出的多元滤波与传统方法进行实验对比，结果表明其不仅能有效滤除多种类型噪声，而且较好地保持了原始图像信息，使图像信息保真清晰，其视觉效果优于传统，客观评价指标也有较大幅度的改善和提升。

关键词：矢量相似性；相似性测度；矢量滤波；多元滤波 中图分类号：TP391. doi:10.3969/j.issn.1001-3695.2018.05.0342

# Research on multivariate filtering method based on vector similarity

He Xiaojuna, Xu Aigongb, Li ${ \mathrm { Y u } } ^ { \mathrm { b } }$ (a.CollegeofInovation&Practice,b.choolofGeomaticsiaoningTechicalUniversityFuxinLiaoning23oChina)

Abstract: Inordertoavoid the problemofsorting incolorimagefltering,this paper definesand proposes a multivariatefiter method forcolor image basedon thestudyof vectorsimilarity.Firstly,inRGBcolor space,the similarity measure between the colorvectors is definedbythedistanceand theangletodescribethecolorvectorsimilarityconsistent with the human visual perception.Secondly,usingthecolor similaritycriterion,thecolor multivariate filteris designed and constructed,and the influenceof therelatedparametersonthefiltering performanceisanalyzedandstudiedindepth.Finaly,inordertoverifythe efectivenessof theproposed method,it isapplied totheactualremotesensing image filtering.Itcan beseen from the experiment that the proposed method notonly efectivelysolves the problemof sorting the traditional filtering methods,but also overcomes the problemsof blurring the imageand unclear edges dueto the filtering.Inaddition,compared with the resultsofothertraditionalmethods,theresultsshowthatitnotonlycanefectivelyfilterallkindsofnoise,butalsomaintains theoriginal image information beter,making the image information clearand fidelity.Thevisual effectofthisfiltering method is superior to the traditional, its objective evaluation index also has greatly improved.

Key words:Vector similarity; Similarity measure;Vector filtering; Multivariate filtering

# 0 引言

噪声产生于图像采集、传输和处理的各个环节，直接影响图像质量及其处理结果精度[1。由于产生原因不同，常见的图像噪声包括高斯、椒盐等多种类型。图像滤波则是以图像保真为目标的图像处理技术，其作用在于从被噪声污染的图像中恢复原始图像信息，同时保持图像中目标边缘和细节信息，因此在图像处理中有着十分重要的实际意义。一般而言，图像滤波方法具有很强的针对性，图像和噪声的特性不同，采用的滤波方法亦有所不同。从图像表达形式来看，图像滤波可分为灰度图像滤波和彩色图像滤波两大类。灰度图像滤波以灰度值作为唯一依据，实现较为容易。与灰度图像不同，彩色图像是多元图像，涉及多个颜色通道，而且各通道间存在着强烈的相关性。因此，灰度图像滤波方法不能直接移植于彩色图像，也使彩色图像滤波的实现更复杂、更困难。

对于彩色图像，噪声不仅使其颜色失真、清晰度下降，而且也直接影响图像的处理及应用[2，针对噪声常用的滤波方法有标量和矢量滤波法。标量滤波法是对彩色图像的三个颜色通道分别进行滤波，然后合成各通道滤波结果得到彩色滤波图像。这类方法没有考虑彩色图像中三个颜色分量间的有机联系，可能产生原图像所没有的颜色，进一步造成图像失真，甚至出现局部不协调的色彩，从而破坏了色调和边缘细节信息。矢量滤波法是将彩色像素作为彩色空间矢量来处理，充分考虑各颜色通道分量之间的联系，在消除噪声、保持色调、保护边缘与细节上有较好的鲁棒性。因此，彩色图像的矢量滤波法较标量滤波法更合理、更有效，其中，矢量中值滤波(vectormedian filter,VMF)、矢量方向滤波(vectordirectionfilter,VDF)、矢量方向距离滤波(vector direction distance filter,DDF)等方法受到普遍关注[3-8]，但这些方法在滤波时均采用最大数量平滑，经常会因损坏图像的边缘和细节信息而导致图像失真。除了上述矢量滤波方法外，Lukac等人[提出选择加权的矢量中值滤波；武昆等人[10]将四元数理论引入到彩色图像滤波领域；孙建召等人[11]利用模糊神经网络进行图像噪声滤波等。这些改进的滤波方法使其性能在某些方面得到一定的提升和改善，但由于彩色图像表示形式的特殊性及排序等问题，所以均存在一定的局限性[12:13]。

为了避免彩色图像滤波时排序的难题，本文以彩色空间矢量相似性为准则，设计并构建了一种针对彩色图像的多元滤波方法。该方法不仅消除了因排序带来的滤波问题，而且能较好滤除图像噪声，并保持原始图像细节特征，也不会因产生新的颜色而造成图像失真。与传统的滤波方法比对，其性能得到了较大的改善和提升。

# 1 理论基础

给定彩色图像 $z { = } \{ z _ { i } ( x _ { i } , \ y _ { i } ) , \ ( x _ { i } , \ y _ { i } ) { \in } P , \ i { \in } I \ \}$ 为定义在图像域$P$ 上的彩色影像，其中， $I = \{ 1 , 2 , . . . , n \}$ ， $( x _ { i } , y _ { i } )$ 为像素 $i$ 的平面坐标，i为像素索引， $n$ 为像素个数， $P$ 为图像域, $\pmb { \zeta } i = ( z _ { i R } , z _ { i G } , z _ { i B } )$ 为像素 $i$ 在RGB中所对应的彩色矢量，ZiR、ZiG、ZiB分别表示彩色矢量 $z _ { i }$ 的红、绿、蓝分量。以像素 $i$ 为中心的滤波窗口彩色矢量集合 $W _ { i } = ( z _ { i } , z _ { i ^ { \prime } } ) = \{ z _ { j } , j { \in } J \}$ ，其中， $i { \in } I , i ^ { \prime } { \in } N _ { i } , l$ $N _ { i }$ 为像素 $i$ 的邻域像素集合， $j$ 为滤波窗口中像素索引， $J = \{ 1 , 2 , . . . ,$ $m \}$ ， $\mathbf { \nabla } m$ 为滤波窗口中矢量数目。彩色图像矢量滤波就是按一定的规则和顺序逐个获取滤波窗口并实现滤波输出，这样彩色图像滤波就转化成彩色空间矢量的滤波问题[14-18]。

# 1.1典型矢量滤波

在进行矢量滤波时，将以像素 $i$ 为中心的滤波窗口 $W _ { i }$ 中 $m$ 个彩色矢量，按照一定的规则进行排序并构成一个升序序列：

$$
z _ { ( 1 ) } \leq z _ { ( 2 ) } \leq \ldots \leq z _ { ( j ) } \leq \ldots \leq z _ { ( m ) }
$$

其中， $z _ { ( j ) }$ 表示第 $j$ 矢量的排序统计量，则排序最小矢量 $z _ { ( 1 ) }$ 和最大矢量 $z ( m )$ 就分别是该滤波窗口的最小和最大滤波输出。

实际应用时，矢量排序标准不同，则滤波输出也有所不同，经常可形成VMF、VDF、DDF 等非线性滤波方法[19-24]。

当以矢量间距离作为排序依据时，则窗口中每个矢量 $z _ { j }$ 到所有矢量距离的累加和 $\varDelta _ { j }$ 可表示为

$$
\mathcal { A } _ { j } = \sum _ { k = 1 } ^ { m } d ( z _ { j } , z _ { k } ) \mathrm { j , k } \in \mathbb { J }
$$

由此规则获得排序序列为

$$
\Delta ( 1 ) { \leqslant } \Delta ( 2 ) . . . \leqslant \Delta \left( \mathrm { j } \right) . . . { \leqslant } \Delta ( \mathrm { m } )
$$

则式(3)所对应式(1)序列中的 $z _ { ( 1 ) }$ 是当前滤波窗口中到所有矢量距离累加和最小的矢量，如将其作为滤波输出，即就是矢量中值滤波VMF，这种滤波方法输出为窗口内原有像素，能有效地去除在矢量距离上相差较大的噪声像素。

同理，利用两个矢量间的角度来进行排序时，则每个矢量$z _ { j }$ 到所有矢量角度的累加和 $\boldsymbol { \Theta } _ { j }$ 可表示为

$$
\Theta _ { j } = \sum _ { k = 1 } ^ { m } \theta ( z _ { j } , z _ { k } ) \qquad j , k \in J
$$

其类似的排序序列为

$$
\Theta _ { ( I ) } \le \Theta _ { ( 2 ) } \dots \le \Theta _ { ( j ) } \dots \le \Theta _ { ( m ) }
$$

则式(5)对应式(1)序列中的 $z _ { ( 1 ) }$ 是当前滤波窗口中到所有矢量角度累加和最小的矢量，将其作为滤波输出，即就是所谓的矢量方向滤波VDF，它能有效地去除色调相差较大的噪声像素。

另外，为了更全面考虑矢量相关性的特征，有时会将矢量距离和相对方向同时作为排序依据，则滤波窗口中每个矢量 $z _ { j }$ 到所有矢量的距离与角度累加和的乘积 $B _ { j }$ 表示为

$$
B _ { j } = \sum _ { k = 1 } ^ { m } \theta ( z _ { j } , z _ { k } ) \sum _ { k = 1 } ^ { m } d ( z _ { j } , z _ { k } ) \qquad { \mathrm { j , k \in J } }
$$

以距离和相对方向（角度）作为矢量排序依据时，可得到

$$
B _ { ( 1 ) } { \le } B _ { ( 2 ) } { \ldots } { \le } B _ { ( j ) } { \ldots } { \le } B _ { ( m ) }
$$

这时，式(7)所对应式(1)序列中的 $z _ { ( 1 ) }$ 是当前滤波窗口中到所有矢量距离与角度累加和乘积最小的矢量，这就是距离方向滤波DDF，既能去除矢量距离相差较大的噪声像素，又能消除色调相差较大的噪声像素。

上述滤波方法输出像素均为窗口内原有像素，不会引入新的色彩，但因所有像素均被平等平滑，没有被噪声污染的像素也发生了变化，从而致使彩色图像中的轮廓、边缘、细节等信息在滤波过程中受到损伤和影响，在抑制噪声和保护细节方面存在一定的矛盾和问题，且去噪时均要进行大量矢量排序，运算量随滤波窗口的增大呈几何速度增长，导致难以满足一些实际应用需求。另外，在实际应用时，其实难以找到一种合适、通用的彩色矢量排序规则，所以这些方法在去除噪声、还原图像、保留原图像细节特征等方面均存在一定的局限性。

# 1.2矢量相似性测度

一般而言，彩色图像中未受噪声影响的同质区域像素，具有较高的相似性，而受到噪声影响后其相似性就会降低，本文

正是利用这个特征，引入相似性测度的概念以刻画彩色矢量间的相似性程度，并以此作为彩色图像多元滤波的基础，这也有效避免和解决了彩色矢量排序的难题。

相似性测度是研究和分析目标间关系的一种十分重要的量度方法，在图像处理、信息检索、模式识别、数据挖掘、多元数据分析、图像检索等中都有着十分广泛的应用。

对于任一像素 $i$ 所构成的滤波窗口彩色矢量集合 $W _ { i } = \{ z _ { j } ,$ （204号 $j { \in } J \}$ ，给定彩色矢量对 $z _ { j }$ ， $z _ { k } \in W _ { i }$ ， $j , k \in J$ ，则其矢量相似性测度 可定义为

$$
\mu ( z _ { j } , z _ { k } ) = e ^ { - k _ { 1 } d ( z _ { j } , z _ { k } ) } \cos { \Bigl ( k _ { 2 } \theta ( z _ { j } , z _ { k } ) \Bigr ) }
$$

其中， $k _ { 1 } \in [ 0 , \infty )$ 和 $k _ { 2 } \in [ 0 , 1 ]$ 为控制相似程度的参数， $d ( z _ { j } , \ z _ { k } )$ 和$\theta ( z _ { j } , z _ { k } ) \in [ 0 , \pi / 2 )$ 分别为两彩色矢量间的距离和夹角，可表示为

$$
\begin{array}{c} d ( z _ { j } , z _ { k } ) = \left\{ \left( \sum _ { q = 1 } ^ { 3 } \left| z _ { j q } - z _ { k q } \right| ^ { p } \right) ^ { 1 / p } \qquad 1 \leq p < \infty \qquad \right.  \\ { \left. \operatorname* { m a x } \left[ \mid z _ { j 1 } - z _ { k 1 } \mid , \mid z _ { j 2 } - z _ { k 2 } \mid , \mid z _ { j 3 } - z _ { k 3 } \mid \right] \qquad p = \infty \qquad \right. } \end{array}
$$

$$
\cos \theta ( z _ { j } , z _ { k } ) = \frac { \displaystyle \sum _ { q = 1 } ^ { 3 } z _ { j q } z _ { k q } } { \displaystyle \left( \sum _ { q = 1 } ^ { 3 } \lvert z _ { j q } \rvert ^ { p } \right) ^ { l / p } \left( \displaystyle \sum _ { q = 1 } ^ { 3 } \lvert z _ { k q } \rvert ^ { p } \right) ^ { l / p } }
$$

其中： $p$ 为矢量范式，在这里取 $\scriptstyle p = 2$ ，即 $d ( z _ { j } , \ z _ { k } )$ 为矢量间的欧几里德距离。由式(8)可以看出，定义的矢量相似性测度取值区间为[0,1]。这样，彩色图像中两个像素点颜色在视觉感知上越相近时，其对应到RGB空间的彩色矢量在距离和角度上就越接近，即其距离和夹角越小，相似性测度的值越大，则表示两者具有较高相似性；反之，当两个像素点颜色在视觉感知上差别较大时，其矢量间距离或夹角较大，其相似性测度的值越小，则表示相似程度较低。当然，当是同一颜色时，两个彩色矢量重合（即为同一矢量)，距离及夹角均为0，相似性测度为1，则表征其相似程度最高。彩色图像的实际视觉感知均与矢量相似性相符合。

一般而言，人类对彩色认知存在差异性，相似性会因人的视觉感知而不同；另外，彩色图像的边缘、细节信息等均具有一定的非确定性，使得人们很难精确地区分这些边缘细节像素和噪声，所以式(8)中引入参数 $k _ { 1 }$ 和 $k _ { 2 }$ ，通过改变其值能达到人为调整两个矢量的相似性程度的目的，即对于同样两个矢量，由于参数 $k _ { 1 }$ 、 $k _ { 2 }$ 选择的不同，则具有不同的相似性测度值。如若 $d ( z _ { j } , z _ { k } ) = 1$ 、 $\theta ( z _ { j } , z _ { k } ) = \pi / 4$ ，两个矢量间相似性测度变化，如图1所示，从图中能够清楚地看出，针对同样的两个彩色矢量，当参数 $k _ { 1 }$ 和 $k _ { 2 }$ 取不同值时，由式(8)所得到的模糊相似性测度不同，这与人类视觉感知的模糊性和不确定性相一致。通过实验分析可知，参数 $k _ { 1 }$ 和 $k _ { 2 }$ 的不同组合直接决定了两个矢量的相似性程度，随着 $k _ { 1 }$ 、 $k _ { 2 }$ 的增加，矢量间的相似性测度减小，相似性降低；反之，相似性升高；参数 $k _ { 1 }$ 比 $k _ { 2 }$ 对相似性测度的影响更大，相似性测度对于 $k _ { 1 }$ 的变化更加敏感。上述相似性测度定义能很好的刻画两个矢量间的相似性关系，这也为彩色图像

多元滤波的实现奠定了基础。

![](images/0af4e9bae8bcfe54b1f5eaf7fef427c0fa1c974fcf6d7319db291ca7be03b875.jpg)  
图1当 ${ \bf d } = 1$ $\theta = \pi / 4$ 时k1、k2对相似性测度的影响

当然，式(8)中参数 $k _ { 1 }$ 决定了两个矢量空间距离上的相似性，当参数 $k _ { 1 } = 0$ 时，矢量相似性仅与角度有关；同理，参数$k _ { 2 }$ 决定了两个矢量在角度上的相似程度，当 $k _ { 2 } = 0$ 时，矢量相似性仅与距离有关。

# 2 算法描述

彩色图像 $z$ 的多元滤波就是按照顺序对其每一像素点 $i$ 所对应的滤波窗口 $W _ { i }$ 进行处理，并实现滤波矢量输出 $\mathbf { \Delta } _ { \mathbf { \mathcal { V } } i }$ ，即 $\pmb { \nu } _ { i } =$ $\pmb { \mathscr { E } } ( W _ { i } )$ ，当前像素 $i$ 在窗口中对应的矢量设定为 $z _ { 1 }$ 。具体实现过程如下。

据式(8)-(10)计算矢量间的相似性测度并形成一个 $W _ { i } { \times } W _ { i }$ 相似性关系矩阵 ${ \pmb R } _ { i }$

$$
\pmb { R } _ { i } = [ \mu ( z _ { j } , z _ { k } ) ] \quad j , k \in J , i \in I
$$

由式(11)得到的相似性关系矩阵 $\pmb { R } _ { i }$ 满足以下两个条件：

a）自反性： $\mu ( z _ { j } , z _ { j } ) = 1$ ，j∈J

b）对称性： $\mu ( z _ { j } , z _ { k } ) = \mu ( z _ { k } , z _ { j } ) , \mathrm { ~ \ } j , k \in \boldsymbol { J }$

则对于 $z _ { j } \in W _ { i }$ 的平均相似性测度可表示为

$$
A _ { j } = \frac { 1 } { m } \sum _ { k = 1 } ^ { m } \mu ( z _ { j } , z _ { k } ) \qquad j , k { \in } J
$$

式(12)中平均相似性测度 $A _ { j }$ 表示矢量 $z _ { j }$ 与 $W _ { i }$ 中所有矢量的相似性测度的平均值，由这些平均相似性测度中最大值所对应的矢量构成一个矢量集合 $U _ { i }$ 可表示为

$$
U _ { i } = \{ z _ { t } \in W _ { i } , A _ { t } { = } \operatorname* { m a x } \{ A _ { j } \} \} \qquad j , t \in J , i \in I
$$

由式(13)即可获取 $W _ { i }$ 中所有矢量相似性测度平均值最大的矢量，也就是当前窗口中最“中心”矢量。这样，即可得到一个与最“中心”矢量 $z _ { t }$ 对应的相似性聚类及对应的相似性测度；根据实际滤波要求，如果给定一个阈值 $\alpha ( 0 \leq  { \alpha } \leq 1 )$ ，则由此相似性聚类中矢量相似性测度大于给定阈值 $\scriptstyle a$ 的矢量构成一个割集 $W _ { i a } \subseteq W _ { i }$ ，称为 $\scriptstyle a .$ 割集，即

$$
W _ { i \alpha } = \{ \ z _ { j } , \mu \left( z _ { t } , z _ { j } \right) > \alpha \} \quad j , t \in J
$$

则在当前滤波窗口 $W _ { i }$ 中，基于矢量相似性的多元滤波输出可表示为

$$
\nu _ { i } = \left\{ \begin{array} { l l } { { z _ { 1 } \qquad } } & { { z _ { 1 } \in W _ { i \alpha } } } \\ { { z _ { t } \qquad } } & { { z _ { 1 } \not \in W _ { i \alpha } } } \end{array} \right.
$$

从式(15)可知，当前矢量在 $W _ { i a }$ 中时，其滤波窗口输出 $\mathbf { \Delta } _ { \mathbf { \mathcal { V } } _ { i } }$ 即原为原当前矢量 $z _ { 1 }$ ；当前矢量 $z _ { 1 }$ 不在 $W _ { i \alpha }$ 中时，其输出 $\pmb { \nu } _ { i }$ 为当前滤波窗口中最“中心”矢量 $z _ { t }$ ，而无论是当前矢量还是最“中心”矢量，均为当前滤波窗口中的原图像像素矢量。

这样，对于给定彩色图像 $z = \{ z _ { i } , i \in I \}$ ，通过上述操作f，即形成滤波后彩色图像 $V = \{ \nu _ { i } , i \in I \}$ ，其中， $I = \{ 1 , 2 , . . . , n \}$ 。这种处理不仅能够更好的保留原图像的细节特征，同时也避免因矢量排序带来的滤波问题，算法效率及性能有了较大的改善和提升。

# 3 实验结果与分析

# 3.1多元滤波窗口中相关量的获取

滤波窗口是多元滤波的基本单元和区域，为了进一步分析其中各个量的获取和确定。假设彩色图像 $z$ 中，以某一像素 $i$ 为中心构造一个 $3 { \times } 3$ 像素的滤波窗口 ${ \bf \nabla } _ { { W } _ { i } }$ ，其对应的矢量集 $W _ { i } =$ $\{ z _ { j } , j \in J \}$ ， $J = \{ 1 , 2 , . . . , 9 \}$ ，九个彩色矢量分别为： $z _ { 1 } = ( 3 5 , 4 7$ 49)、 $z _ { 2 } { = } ( 2 3 2 , 2 3 6 , 2 3 6 )$ 、 ${ z 3 = ( 8 5 , 9 7 , 9 9 ) }$ 、z4=(29,34,13)、 $z s { = } ( 1 4 3$

145,147）、 $z _ { 6 } = ( 9 , 2 3 , 4 5 )$ 、z7=(143,137,146)、 $z _ { 8 } = ( 5 6 , 5 9 , 7 0 )$ （204号和 $z \mathrm { { s } = } ( 1 2 , 1 8 , 4 1 )$ ，其中，当前滤波像素i对应的矢量为 $z _ { 1 }$ 。

为了简化实验复杂度，选取参数 $k _ { 1 } = 0 . 0 0 1$ ， $k _ { 2 } = 0 . 2$ ，利用式(8)\~(12)计算矢量间的相似性测度并形成一个 $W _ { i } { \times } W _ { i }$ 相似性关系矩阵 $\pmb { R } _ { i }$ 及平均相似性测度 $A _ { j }$ ，计算结果如表1所示。由表1可以得出，平均相似性测度 $A _ { j }$ 的最大值为0.9124，其所对应的矢量集合为 $U _ { i } = \{ \boldsymbol { z } \mathrm { { s } \} }$ ，即 $z _ { 8 }$ 是当前窗口最“中心”的矢量，此矢量所对应相似性聚类的相似性测度分别为：{0.9683,0.7409,0.9455,0.9553,0.8653,0.9343,0.8698,1.000,0.9326}。当滤波阈值 $\alpha = 0 . 9$ 时，其 $\alpha \cdot$ -割集 $W _ { i \alpha } = \left\{ \begin{array} { r l } { z 1 , z 3 , z 4 , z 6 , z 8 , z 9 } \end{array} \right\}$ ，因当前滤波矢量 $z _ { 1 }$ 在 $\scriptstyle a$ -割集中，所以滤波窗口输出 $\mathbf { \Delta } _ { \mathbf { \nu } _ { \mathbf { \lambda } } \mathbf { \nu } _ { \mathbf { \lambda } } }$ 即为原矢量 $z _ { 1 }$ ，这充分体现了此滤波方法在允许范围内尽量保留原窗口及像素的原有特征；当滤波阈值 $\alpha = 0 . 9 7$ 时，其 $\scriptstyle a .$ -割集 $W _ { i \alpha } = \{ z _ { 8 } \}$ ，此时当前滤波矢量 $z _ { 1 }$ 未包含在 $\scriptstyle a$ -割集中，所以滤波输出 $\mathbf { \Delta } _ { \mathbf { \mathcal { V } } i }$ 即为此滤波窗口中最“中心”的矢量 $z { 8 }$ ，这就说明此方法在允许范围内能发现一个最优矢量作为输出，而其仍为原图像矢量。

表1滤波窗口中矢量相似性测度  

<html><body><table><tr><td>矢量</td><td>71</td><td>2</td><td>73</td><td>Z4</td><td>Z5</td><td>Z6</td><td>77</td><td>Z8</td><td>79</td><td rowspan="2">Aj</td></tr><tr><td>RGB</td><td>(35,47,49)</td><td>(232,236,236)</td><td>(85,97,99)</td><td>(29,34,13)</td><td>(143,145,147)</td><td>(9,23,45)</td><td>(143,137,146)</td><td>(56,59,70)</td><td>(12,18,41)</td></tr><tr><td>71</td><td>1.0000</td><td>0.7180</td><td>0.9169</td><td>0.9845</td><td>0.8386</td><td>0.9618</td><td>0.8426</td><td>0.9683</td><td>0.9599</td><td>0.9101</td></tr><tr><td>72</td><td>0.7180</td><td>1.0000</td><td>0.7832</td><td>0.7076</td><td>0.8561</td><td>0.6920</td><td>0.8515</td><td>0.7409</td><td>0.6903</td><td>0.7822</td></tr><tr><td>73</td><td>0.9169</td><td>0.7832</td><td>1.0000</td><td>0.9035</td><td>0.9145</td><td>0.8839</td><td>0.9187</td><td>0.9455</td><td>0.8816</td><td>0.9053</td></tr><tr><td>74</td><td>0.9845</td><td>0.7076</td><td>0.9035</td><td>1.0000</td><td>0.8265</td><td>0.9748</td><td>0.8307</td><td>0.9553</td><td>0.9748</td><td>0.9064</td></tr><tr><td>75</td><td>0.8386</td><td>0.8561</td><td>0.9145</td><td>0.8265</td><td>1.0000</td><td>0.8080</td><td>0.9920</td><td>0.8653</td><td>0.8061</td><td>0.8786</td></tr><tr><td>76</td><td>0.9618</td><td>0.6920</td><td>0.8839</td><td>0.9748</td><td>0.8080</td><td>1.0000</td><td>0.8121</td><td>0.9343</td><td>0.9927</td><td>0.8955</td></tr><tr><td>77</td><td>0.8426</td><td>0.8515</td><td>0.9187</td><td>0.8307</td><td>0.9920</td><td>0.8121</td><td>1.0000</td><td>0.8698</td><td>0.8104</td><td>0.8809</td></tr><tr><td>78</td><td>0.9683</td><td>0.7409</td><td>0.9455</td><td>0.9553</td><td>0.8653</td><td>0.9343</td><td>0.8698</td><td>1.0000</td><td>0.9326</td><td>0.9124</td></tr><tr><td>9</td><td>0.9599</td><td>0.6903</td><td>0.8816</td><td>0.9748</td><td>0.8061</td><td>0.9927</td><td>0.8104</td><td>0.9326</td><td>1.0000</td><td>0.8943</td></tr></table></body></html>

# 3.2 多元滤波实验

为了直观评价这种多元滤波方法的性能，分别选取$1 5 0 \times 1 5 0$ 像素的经典彩色图像'Pepper'和分辨率为 $1 \mathrm { m } , 1 5 0 { \times } 1 5 0$ 像素的Ikonos 高分辨率遥感影像作为测试图像，如图2(a1)(a2)所示；分别加入强度为0.08的椒盐噪声构成噪声图像，如图2(b1)(b2)所示；式(8)中计算矢量相似性测度时，仍然选取参数$k _ { 1 } = 0 . 0 0 1$ ， $k _ { 2 } = 0 . 2$ ，滤波窗口为 $3 { \times } 3$ 像素的矩形区域，阈值 $\alpha =$ 0.97。经过多元滤波后的输出图像，如图2(c1)(c2)所示，从原图像(图2(a1)(a2))与滤波后图像(图2(c1)(c2))直观对比效果可以看出，此多元滤波方法具有很好的滤波效果，不但能够较好的去除噪声，而且很大程度保留了实际影像的边缘及细节信息，未因滤波造成图像信息模糊，避免失真，为彩色图像的进一步应用奠定了基础。

![](images/4a305d36e4b8717923fdb2066645d36ee3c108fdb95f3829e138fe7a3cff788b.jpg)  
图2图像滤波

# 3.3参数对滤波性能影响的分析与评价

实际评价滤波方法效果及性能主要是通过主观和客观两个方面。主观评价是通过人的主观感觉对图像质量的优劣做出评定，上述实验即通过此方式进行评价，该方式具有很大的主观性，受不同观察者、不同图像类型和环境的影响，使其具有一定的不确定性。因此，在实际图像滤波质量评价中主要以客观评价为主，客观评价就是通过量化指标进行滤波图像的评价。一般而言，图像质量特征不同，客观评价的标准也会有所不同。但在实际应用中，由于很难评估滤波方法消除噪声以及对未受噪声影响像素的保持能力，所以对其性能的评价是一件十分复杂的工作。本文采用应用最为广泛的标准均方差(normalizedmean square error,NMSE)，通过统计两个数字图像之间像素值分布的不同和差异来进行多元滤波方法的性能评价。若 $z _ { i }$ 表示原彩色图像中像素 $i$ 所对应的矢量，而 $\mathbf { \Delta } _ { \mathbf { \nu } _ { \mathbf { \lambda } } \mathbf { \nu } _ { \mathbf { \lambda } } }$ 表示其估计值，即滤波后该像素的具体值，则NMSE可表示为

$$
\mathrm { N M S E } = \frac { \displaystyle \sum _ { q = 1 } ^ { 3 } \lVert \boldsymbol { z } _ { i q } - \boldsymbol { \nu } _ { i q } \rVert ^ { 2 } } { \displaystyle \sum _ { q = 1 } ^ { 3 } \lVert \boldsymbol { z } _ { i q } \rVert ^ { 2 } }
$$

分析参数对滤波性能的影响实验，选取 $1 5 0 \times 1 5 0$ 像素的“Pepper'作为测试图像，如图2(a1)所示，在这里分别用高斯噪声、椒盐噪声及两者结合进行污染干扰，噪声类型及相关参数如表2所示。

表2噪声类型  

<html><body><table><tr><td>模式</td><td>噪声类型</td></tr><tr><td>1</td><td>高斯 (方差0.005)</td></tr><tr><td>2</td><td>高斯 (方差0.005)+ 椒盐 (强度0.02)</td></tr><tr><td>3</td><td>椒盐 (强度0.02)</td></tr><tr><td>4</td><td>椒盐(强度0.02)+高斯 (方差0.005)</td></tr></table></body></html>

原测试图像经过上表噪声进行干扰后的噪声图像，如图3所示，图3(a)\~(d)分别对应表2中四种噪声模式产生的噪声图像。

![](images/3c8f1fdcb0f785a6be501090bf0580fc975ca62b1d69f21618cd60adf099c577.jpg)  
图3噪声图像 (a)模式1(b)模式2(c)模式3(d)模式4

通过前面的算法描述可以看出，因多元滤波方法以矢量相似性为基础，所以式(8)中引入的参数 $k _ { 1 }$ 、 $k _ { 2 }$ 及式(14)中的阈值$\alpha$ 直接影响滤波性能。其中参数 $k _ { 1 }$ 、 $k _ { 2 }$ 决定了两个矢量之间的相似程度，当 $k _ { 1 } = 0$ 时，两个矢量间的相似程度与距离没有关系，仅与相对角度有关，即滤波就是以矢量角度作为依据进行，即变为VDF 滤波；同理，当 $k _ { 2 } { = } 0$ 时，就变为VMF滤波，即两个矢量间的相似性与相对角度没有关系，仅与距离有关，仅以距离作为滤波依据；阈值 $\scriptstyle a$ 决定了滤波窗口输出当前像素点的概率。

首先，评价参数 $k _ { 1 }$ 在不同噪声干扰下对滤波效果及性能的影响。假设 $k _ { 2 } = 0 . 2$ ，阈值 $\alpha = 0 . 5$ ，而 $k _ { 1 }$ 从0变化到10时，多元滤波的性能NMSE评价曲线，如图4(a)-(d)所示。从图4可知，当 $k _ { 1 } = 0 . 0 0 1$ 时，多元滤波方法对于噪声模式1的滤波效果最好，如图4(a)所示；当 $k _ { 1 } = 0 . 0 2$ 时，其对于噪声模式2-4的滤波效果最好，如图4(b)所示。从参数 $k _ { 1 }$ 整体影响的变化趋势看，多元滤波针对噪声模式3（椒盐噪声）的滤波性能尤为显著。

![](images/4440ebc3d141587967c8329deeeb74dbd6565d3aea2f4cf40f99fdc8491b088d.jpg)  
图4参数k1对噪声模式1-4滤波性能的NMSE评价

同理，评价参数 $k _ { 2 }$ 对滤波性能影响时，设定参数 $k _ { 1 } = 0 . 0 0 1$ ，阈值 $a = 0 . 5$ ，参数 $k _ { 2 } \in [ 0 , 1 ]$ ，NMSE变化曲线，如图5所示，从图示变化可以看出，当 $k _ { 2 } = 0 . 2$ 时对所有噪声模式其滤波效果及性能达到最优。

![](images/52427e0afbcef1f40395cbcf504bbe5ebf73fded544e83fcf8d7e2282e0950f3.jpg)  
图5参数 $\mathbf { k } _ { 2 }$ 对噪声模式1-4滤波性能的NMSE评价

![](images/531ce66e303e8047fb1b19cd120c450c25cc843b7363b525707c5d63e937497e.jpg)  
图6阈值α对噪声模式1-4滤波性能的NMSE评价

另外，阈值 $\scriptstyle a$ 是用于调节滤波时保留原像素的概率，当 $k _ { 1 }$ $= 0 . 0 0 1$ ， $k _ { 2 } = 0 . 0 2$ ，阈值 $\alpha$ 在0\~1变化时，NMSE曲线如图6所示。图中变化情况表明，当 $a { < } 0 . 6$ 时，对于所有噪声模式，滤波效果最好。

基于上述实验及分析，可以看出，参数 $k _ { 1 }$ 、 $k _ { 2 }$ 及阈值 $\alpha$ 均直接影响多元滤波的性能，所以在实际中一般要根据具体情况进行确定。

# 3.4性能对比实验

下面将本文多元滤波方法与矢量中值滤波VMF、矢量方向滤波VDF、距离方向滤波DDF等典型滤波方法进行对比实验，进一步研究和分析其性能。根据前面的实验结果分析，本文多元滤波方法参数 $k _ { 1 } = 0 . 0 0 1$ 、 $k _ { 2 } = 0 . 2$ 、 $\alpha = 0 . 5$ ，滤波窗口均为 $3 { \times } 3$ 像素，四种测试噪声图像如图3所示。

针对噪声模式1的VMF、VDF、DDF及本文方法滤波结果分别如图 7(a1)\~(a4)所示；针对噪声模式2、3、4 的滤波结果如图7(b1-b4)\~(d1-d4)所示。从滤波效果对比可以看，本文方法(图7(a4)\~(d4))具有良好的滤波效果及性能，能较好的保留原图像的细节特征，且能使图像边缘光滑。

当然，四种方法的滤波性能及效果有时通过主观视觉很难准确进行评判，在这里，仍然采用上述标准均方差(NMSE)来进行评价和分析，其滤波性能NMSE曲线如图8所示，其中图8(a)为四种滤波方法针对噪声模式1的滤波性能NMSE评价，即对应图7(a1)-(a4)；同理，图8(b)-(d)为针对噪声模式2、3、4的 NMSE 评价曲线，且分别对应图7(b1-b4)-(d1-d4)。从NMSE曲线可以清楚的看出，本文提出的多元滤波方法与传统的VMF、VDF、DDF等方法相比，其客观评价指标有较大的改善和提高，针对上述四种噪声均具有较好的滤波效果及性能。

# 4 结束语

为了解决彩色图像滤波问题，文章在RGB彩色空间，从矢量相似性角度出发，利用距离和角度共同定义相似性测度，以刻画和描述矢量间与人类视觉感知相一致的相似性关系；并以此为基础和准则，构造并提出了一种针对彩色图像的多元滤波方法。该方法不仅能避免滤波时矢量排序的难题，而且具有保留原始像素和去除噪声像素之间的折衷能力，较好保持了图像边缘及细节特性。通过实验可知其具有较好的滤波效果，尤其是当参数 $k _ { 1 } = 0 . 0 0 1$ ， $k _ { 2 } = 0 . 2$ ，阈值 $a { < } 0 . 6$ 时，该方法滤波性能较优。另外，文章还将其与常用滤波方法进行实验对比，通过客观评价指标NMSE的变化曲线表明，该方法能有效的去除多种类型的噪声，能较好地保持原图像信息，其视觉效果及评价指标均优于传统滤波方法，具有一定的推广和实用价值。

![](images/d042d46c4671915417791acc04d4700caa1c7a11bff5a0f966d22ed2105ba56e.jpg)  
图7针对四种类型噪声模式的滤波结果

![](images/49706271a6f39caa10417aa4e7bb61668563d884b843762b4cb2e3300c1e0bf3.jpg)  
图8不同滤波方法针对不同噪声模式的NMSE评价

# 参考文献：

[1]谭志国，欧建平，张军，等．一种层析深度图像去噪算法[J]．光学学 报,2017,37(5): 94-100.(Tan Zhiguo,Ou Jianping,Zhang Jun,et al.A laminar denoising algorithm for depth image [J].Acta Optica Sinica, 2017, 37 (5):94-100.)   
[2]杨昊，陈雷霆，邱航．基于局部特征的正则化滤波算法[J].计算机应 用研究，2017,34(9):2817-2821.(Yang Hao,Chen Leiting,Qiu Hang. Regularization filtering algorithm based on local characteristics[J]. Application Research of Computers,2017,34(9): 2817-2821.)

[3]王瑜，闫沫．采用全局相似性测量的彩色图像分割[J].信号处理，

2016,32 (8):951-959.(Wang Yu,Yan Mo. Color image segmentation by using global similarity measure [J]. Journal of Signal Processing,2O16,32 (8): 951-959.)

[4]冯平兴．一种盲信号处理中的时域自适应滤波算法[J].计算机应用研 究,2018,35 (4):1092-1095.(Feng Pingxing.Adaptive filtering algorithm for blind signal processing [J].Application Research of Computers,2018, 35 (4): 1092-1095.)

[5]肖红光，文俊，陈立福，等．一种新的高分辨率SAR图像道路提取算法 [J]．计算机工程与应用,2016,52(15):198-202,207.(Xiao Hongguang, Wen Jun,Chen Lifu,et al.New road extraction algorithm of high resolution SAR image [J]. Computer Engineering and Applications,2016, 52 (15): 198-202,207.)

[6]马良慧，李东兴，张华强，等．基于小波阈值函数与改进中值滤波融合 的抑制图像混合噪声算法[J].光学技术，2017，43(1)：38-42.(Ma Lianghui,Li Dongxing，Zhang Huaqiang，et al.An algorithm of suppressing image noise based on the integration of wavelet threshold function and improved median filter[J]. Optical Technique,2O17,43 (1): 38-42.)

[7]谢伟，游敏，周玉钦．基于自适应分数阶微分的引导滤波及其应用[J]. 计算机应用研究,2017,34(1):283-286,301.(Xie Wei,You Min,Zhou Yuqin. Guided image filterandapplication basedonadaptive fractional-order differential [J].Application Research of Computers,2017, 34 (01):283-286,301.)

[8]郑丹，马尚昌，赵静．基于空域滤波的图像增强法的探讨[J].微型机 与应用,2017,36(4): 40-42,46.(Zheng Dan,Ma Shangchang,Zhao Jing. Research on image enhancement method based on spatial filtering [J]. Microcomputer& Its Applications,2017,36(4): 40-42,46.)

[9]Lukac R,PlataniotisKN,SmolkaB,et al.Generalized selection weighted vector filters [J].EURASIP Journal on Advances in Signal Processing, 2004,2014(1): 1870-1885

[10]武昆，李桂菊，韩广良，等．四元数引导滤波彩色图像细节增强[J]. 计算机辅助设计与图形学学报，2017,29(3):419-427.(Wu Kun，Li Guiju,Han Guangliang,et al.Color image detail enhancement based on quaternion guided filter [J].Journal of Computer-Aided Design& Computer Graphics,2017,29(3): 419-427.)

[11]孙建召，常青．一种新型的图像噪声滤波算法研究[J].控制工程, 2016,23 (O6): 848-851.(Sun Jianzhao,Chang Qing.Research on image noise filtering algorithm [J].Control Engineering of China,2O16,23 (6): 848-851.)

[12] Melo R O,Costa CFF,Costa MG F.Leak detection of natural gas with base on the components of color spaces RGB and HSI using novelty filter [J].IEEE Latin America Transactions,2014,12(8):1560-1565.

[13] Sghaier MO,Foucher S,Lepage R.River extraction from high-resolution SAR images combining a structural feature set and mathematical morphology [J].IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing,2017,10(3):1025-1038.

[14]Shih H C，Liu E R. Automatic reference color selectionfor adaptive mathematical morphology and application in image segmentation [J].IEEE Trans on Image Processing,2016,25 (10): 4665-4676.   
[15]刘辉，张云生，张印辉，等．均匀空间色差度量的矢量形态学图像处理 [J].中国图象图形学报，2011，16(12):2145-2151.(Liu Hui,Zhang Yunsheng,Zhang Yinhui,et al. Vector morphology image processing based on difference formula in uniform space [J].Journal of Image and Graphics, 2011,16 (12): 2145-2151.)

[16]李淑清，李瑞华，王潇．基于 SAR 图像的海洋溢油分割方法研究[J]. 测绘工程，2017,26 (2):37-41.(Li Shuqing,Li Ruihua,Wang Xiao. Research onsplit methodsof ocean oil spill in SAR image [J]. Engineering ofSurveying andMapping,2017,26(2):37-41.)

[17]方智文，曹治国，肖阳．深度图像的目标潜在区域提取算法[J].信号 处理，2016,32(02):193-202.(Fang Zhiwen,Cao Zhiguo,Xiao Yang. Object proposal algorithm for the depth image [J].Journal of Signal Processing,2016,32(02):193-202.)

[18]汪洋，卢焕章，孙广富．基于空间模糊化表示的图形相似性测度[J]. 系统工程与电子技术,2005,27(2):340-342.(Wang Yang,Lu Huanzhang Sun Guangfu. Similarity measure between shapes based on spatial fuzzy representation [J].Systems Engineering and Electronics,2Oo5,27 (2): 340-342.)

[19]安静．基于数学形态学的图像增强算法及其应用[D].兰州：西北师范 大学,2016.(An Jing.Image enhancement algorithm and the application based on mathematical morphology [D].Lanzhou: Northwest Normal University,2016.)

[20]于海燕，牛庆丽．计算机技术在图像轮廓提取中的有效应用[J].现代电子技术，2016，39 (10):34-36.(Yu Haiyan，Niu Qingli.Effectiveapplication of computer technology in image contour extraction [J].Modern Electronics Technique,2016,39 (10): 34-36.)

[21]郑亚惠．基于超图与数学形态学的灰度形态学新算子[D].西安：西安 电子科技大学,2016.(Zheng Yahui.New grayscale morphology operator based on the hypergraph and the mathematical morphology [D].Xi’an: Xidian University,2016.)

[22]甄勇，刘伟，陈建宏，等．高分辨率SAR图像舰船目标几何结构特征提 取[J].信号处理，2016,32(4):424-429.(Zhen Yong，LiuWei,Chen Jianhong,et al.Geometric structure feature extraction of ship target in high-resolution SAR image [J]. Journal of Signal Processing,2O16,32 (4): 424-429.)

[23]汤红忠，黄辉先，郭雪峰，等．新型彩色图像形态学处理方法[J].计 算机应用,2010,30(8):2101-2104.(Tang Hongzhong,Huang Huixian, Guo Xuefeng,et al. New method of morphological color image processing [J]. Journal of Computer Applications,2010,30 (8): 2101-2104.)

[24]王玉，李玉，赵泉华．基于规则划分和RJMCMC的可变类图像分割[J]. 仪器仪表学报，2015，36(06):1388-1396.(Wang Yu,Li Yu，Zhao Quanhua. Segmentation of the color remote sensing image with unknown number of classes based on the regular tessellation and RJMCMC [J].

Chinese Journal of Scientific Instrument,2015,36 (6):1388-1396.) [25]赵泉华，赵雪梅，李玉．结合HMRF模型的模糊ISODATA高分辨率遥 感图像分割[J].信号处理,2016,32(2):157-166.(Zhao Quanhua,Zhao Xuemei,Li Yu.A fuzzy ISODATA approach combing HMRF model for high resolution remote sensing image segmentation [J]. Journal of Signal Processing,2016,32(2):157-166.)

[26]Xu Zeshui. On similarity measures of interval-valued intuitionist fuzzy sets and their application to pattern recognitions [J].Journal of Southeast University,2007,23 (3): 139-143.

[27]王淑青，姚伟，陈进，等．基于直方图均衡化与形态学处理的边缘检测 [J].计算机应用与软件,2016,33(3):193-196.(Wang Shuqing,Yao Wei, ChenJin,et al.Image edge detection based on hitogram equalisation and morphology processing [J].Computer Applications and Software,2016,33 (3): 193-196. )

[28]余燕飞，郑烃，王嵩，等．基于空间域的图像噪声检测技术[J].计算 机应用,2012,32(6):1552-1556.(Yu Yanfei,Zheng Quan,Wang Song,et al.Image noise detection technology base on spatial domain [J].Journal of Computer Applications,2012,32(6):1552-1556.)