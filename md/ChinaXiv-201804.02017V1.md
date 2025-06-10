# 消除光晕效应和保持细节信息的图像快速去雾算法

谢伟'，余瑾1，涂志刚²，龙雪玲1，胡欢君1(1．华中师范大学 计算机学院，武汉 430070;2.南洋理工大学 电气电子工程学院，新加坡 639798)

摘要：现有的基于大气散射物理模型的图像去雾算法，在去雾过程中大都无法避免的会产生光晕效应和细节丢失。针对这一问题，提出了一种消除光晕效应和保持细节信息的图像快速去雾算法。首先运用四叉树子矩阵划分的分层遍历方法得到更精确的大气光值，再通过分析大气散耗函数，利用融合梯度信息的改进引导滤波得到精确估计的大气散耗函数，并自适应的获取最小值图像与大气光平均值的阈值，求解出透射图，最后反演复原出无雾图像，并对复原后的图像进行亮度调整。对多组有雾图像进行了实验，本算法能有效地抑制去雾过程中产生的光晕效应，较多地保留了图像的细节信息，且运行时间大约减少了一倍。融合梯度信息的改进引导滤波不但可以较好地保留透射图的细节信息，有效地消除光晕效应，而且具有较好的鲁棒性和时间复杂性。本算法适用于交通等室外场景的去雾。

关键词：光晕效应；细节信息；大气散耗；引导滤波；图像去雾 中图分类号：TP391.41 doi:10.3969/j.issn.1001-3695.2017.11.0776

# Fast algorithm for image defogging by eliminating halo effect and preserving details

Xie Wei1, Yu Jin1, Tu Zhigang²,Long Xueling1, Hu Huanjun1 (1.SchoolofComputing,Central China Normal University,WuHan 43070,China;2.SchoolofElectrical&Electronic Engineering,Nanyang Technological University,Singapore 639798,Singapore)

Abstract: Objective:Theexisting imagedefoggingalgorithmbasedonatmospheric scatering model,thedefogging processare inevitable willhaveahaloefectanddetailsarelost.Tosolvethis problem,thispaperproposesafastdefoggingalgorithmfor eliminatinghaloefectandkeepthedetailinformationoftheimage.Method:Thealgorithmfirstusesfourtreesubspacedivision level the search method to get moreaccurate atmospheric light value,then consumption function through the analysisof atmospheric dispersion,using theimproved gradientinformation fusion filtertoget theaccurate estimationofatmospheric lead consumption dispersion function,and adaptive image and get the minimum average valueofatmospheric optical threshold, calculatedthetransmisionmap,finallyno fog inversionrecovery image,and thebrightnessof therestored image.Result: Experiments onfogimages arecarredout.Thealgorithmcanefectivelysuppressthehaloeffect infogremoval.More details are preservedand the running time is reduced by about twice.Conclusion: Retain detail information transmision improved fusiongradientinformationgudefilternotonlycanbettereliminatethealoeect,efective,andhasbeterrobustnessandtime complexity. This algorithm is suitable for transportation and other outdoor scenes to defog.

Key words: halo effect; details; atmospheric scattering; guided filtering; image defogging

# 0 引言

雾是由许多漂浮在接近地面空气中的微小颗粒组成的气溶胶系统,加上空气中的灰尘等污染物,附着于这些气溶胶上，使采集到的图像严重降质，影响了图像在视频监控、城市交通、遥感成像等设备中的应用。为了减小雾对这些设备的影响，图像去雾技术逐渐受到了国内外图像处理等相关方向研究人员的广泛关注。

目前主流研究的[1雾天图像清晰化处理算法，依据是否依赖于大气散射模型，主要分为两大类:基于非物理模型的方法(NMB)和基于物理模型的方法(MB),这种分类方法反映了去雾算法的本质区别。第一类方法属于图像增强的范畴，并不分析天气因素造成图像降质的物理成因,而是根据主观的视觉感受改善图像的质量，增强图像的对比度以及校正图像的颜色.但是，非物理模型的方法可能会造成图像部分边缘细节信息的丢失，导致去雾后的图像失真。在可见光范围内，对于以水汽为主的大气颗粒主要受散射制约[2],第二类方法通过研究大气中的悬浮颗粒对光的散射作用,建立大气散射模型，最后通过反演来恢复无雾清晰图像,这是一类专门针对雾天图像的清晰化图像去雾方法。尤其对复杂场景的有雾图像处理效果良好，复原后的图像颜色真实，并能够较好地保持图像的边缘细节信息。

Tan 等人[3]首先把原有雾图像作白平衡处理,使雾变为纯白色。Tan认为图像中景深突变的情况相对较少，因此用马尔可夫随机场(Markovrandomfield,MRF)对大气光建模，求出大气光值和透射率分布，最终间接复原出无雾清晰图像。这种方法能够较好的恢复有雾图像的边缘细节信息，增强图像的对比度，但是并没有基于物理模型来复原物体反射的光线,从而使得复原后的图像过饱和,在景深突变处产生光晕效应。

He 等人[4通过对户外大量无雾清晰图像统计特征的观察,发现在这类图像的非天空区域中,存在某些至少在一个颜色通道的像素值很低的像素点,这是由图像中景物的阴影、黑色物体和具有鲜艳颜色的物体造成的.He等运用这个先验理论,对图像的大气光值和透射率进行粗略估计，为避免直接用大气散射模型对图像反演去雾产生的块效应，He等人用软抠图算法对透射率细节分布图进行了优化,使去雾效果更加理想。但是,由于暗原色先验去雾算法的参数无法自适应调整,而且该算法使用软抠图算法对透射图细化处理时需要进行大量的运算，算法的时间和空间效率都非常低,无法实时处理大幅图片，因此算法实用性不好。并且，暗原色先验算法无法处理景物颜色与天空颜色接近且没有阴影时的有雾图像区域。随后，He等人[5]发现引导滤波替代软抠图细化透射图,较大地提高了算法效率,但由于引导滤波选取的是有雾图像为引导图,使得该算法去雾不彻底,并且也没有解决在景物颜色与天空颜色接近且没有阴影区域的图像细节丢失和景深突变处的光晕效应问题。

Tarel等人[6用中值滤波替代He等[4算法中的最小值滤波来对大气光值进行估计,极大地简化了处理过程，提高算法的运行效率。但是,去雾后的图像边缘细节丢失,尤其是当局部区域景深存在密集突变时，就会使该区域去雾不彻底和产生光晕效应，并且该算法同样不能自适应的调整阈值参数，从而一定程度上限制了算法在实际领域中的应用。

Zeng等人[7利用暗通道与双边滤波结合的方式对大气光值进行估计，间接求解透射率,然后利用大气散射物理模型推算获取无雾清晰图像。该算法较好地改善了去雾算法的时间复杂度，保持图像边缘细节信息，但是经过去雾处理后的图像仍然存在光晕效应问题。

本文针对图像去雾中存在上述问题，提出了一种消除光晕效应和保持细节信息的图像快速去雾算法。该算法运用四叉树子矩阵划分的分层遍历方法得到更精确地大气光值，通过分析大气散耗函数，把有雾图像的最小值图像进行均值滤波后的图像作为引导图，再利用融合梯度信息的引导滤波得到大气散耗函数，并自适应的获取最小值图像与大气光值平均值的阈值，调整细化透射率。因此，本文算法可以很好地解决图像去雾中存在的细节丢失与景深突变处的光晕效应等问题，同时本文算法具备较好的时间复杂性。

# 1大气散射模型和改进引导滤波

# 1.1大气散射模型

Narasimhan和Nayar[8]在McCartney[9]的衰减模型(attenuation model)和环境光模型(airlightmodel)的基础上，推演出了在雾霾天气条件下的单色大气散射模型，并将其扩展到RGB颜色空间中：

$$
I ( x ) = J ( x ) t ( x ) + ( 1 - t ( x ) ) A
$$

其中： $I ( x )$ 表示有雾条件下观察者接收到的图像, $J ( x )$ 表示无雾条件下观察者应该接收到的图像, $t { \big ( } x { \big ) }$ 表示透射率， $A$ 表示无穷远处的大气光值。

由式（1）知,Narasimhan和Nayar把大气对物体反射的光线的影响分为大气对物体的衰减和环境光叠加两部分。 式(1)中的 $J ( x ) t ( x )$ 为衰减模型,是大气中悬浮的大气粒子的散射作用,致使的一部分物体表面的反射光因为散射而衰减，而未被散射的部分会直接到达成像设备，到达的光强随着传播距离的增大成指数衰减。式(1)中的 ${ \big ( } 1 - t { \big ( } x { \big ) } { \big ) } A$ 为环境光模型,这是由于大气中悬浮的微小颗粒对自然光的散射引起大气表现出光源的特性，环境光的强度随着传播距离增大而逐步增加。

# 1.2融合梯度信息的改进引导滤波

He 等人[5]在2012年提出的引导滤波算法通过定义局部线性模型，较好的实现了图像保边平滑的特性，并且成功克服了双边滤波算法中的梯度反转现象，但是,仍无法很好地解决光晕现象。针对引导滤波存在的问题,Xie 等人[10]在2016 年提出了融合梯度信息的改进引导滤波，在较好地消除反演中产生的光晕问题的同时还提升了引导滤波的保边平滑的滤波特性。

引导滤波把一幅图像分为基础层和细节层两个部分，基础层表征图像的本质部分和边缘信息，细节层包括了图像的纹理细节和噪声信息。基础层 $q$ 被定义为与引导图像 $I$ 相关的线性模型:

$$
q _ { i } = a _ { k } I _ { i } + b _ { k } , \forall i \in \omega _ { k }
$$

其中： $a _ { k }$ 和 $b _ { k }$ 是引导图像在以像素点 $k$ 为中心，半径为 $r$ 的局部窗□ $\omega _ { k }$ 内的线性系数，其代价函数如下：

$$
E = \sum _ { i \in \omega _ { k } } \Biggl ( \big ( a _ { k } I _ { i } + b _ { k } - p _ { i } \big ) ^ { 2 } + \frac { \varepsilon } { \varphi \big ( i \big ) } { a _ { k } } ^ { 2 } \Biggr )
$$

在信息化数字图像视频处理领域，大部分图像的边缘细节信息都能借助于计算图像梯度求得,因此可以对引导图像梯度场取绝对值，具体公式如下：

$$
a M _ { i } = \left[ \frac { \hat { \sigma } I _ { i } } { \hat { \sigma } x } , \frac { \hat { \sigma } I _ { i } } { \hat { \sigma } y } \right] ^ { T } \mathrm { ~ , ~ }
$$

其中： $I$ 表示引导图像， $\left( { x , y } \right)$ 表示像素点 $i$ 的坐标.

为了使梯度信息得到更精确地应用,向权值 $\varphi ( i )$ 中引入纟

束因子 $s ( i )$ 树立一个约束边界,使其能够精准的确定不同区域所需要采取的不同加权． $\varphi ( i )$ 定义为

$$
\varphi ( i ) = \beta + ( a M _ { i } - t ) . \wedge s ( i )
$$

其中：阈值 $t$ 能够自适应地设置阈值, $\left( a M _ { i } - t \right)$ 表示 $i$ 点的边缘信息， $s ( i )$ 表示 $i$ 点的约束因子。

综上，最终的输出图像为

$$
q _ { i } = \frac { 1 } { \left| \omega \right| } \sum _ { k \in \omega _ { i } } a _ { k } I _ { i } + \frac { 1 } { \left| \omega \right| } \sum _ { k \in \omega _ { i } } b _ { k }
$$

其中： $a _ { k } = \frac { \displaystyle \frac { 1 } { \omega } \sum _ { i \in \omega _ { k } } I _ { i } p _ { i } - \mu _ { k } \overline { { p _ { k } } } } { \sigma _ { k } ^ { 2 } + \varepsilon / \varphi ( i ) } , b _ { k } = \overline { { p _ { k } } } - a _ { k } \mu _ { k } .$ （7）

# 2 基于融合梯度信息改进引导滤波的快速去雾算法

针对现有算法存在的细节丢失和光晕效应问题，本文改进算法是基于大气散射模型的去雾算法，通过对大气散耗函数的精确估计，间接求取透射率，并对透射率进行细化处理，进而复原出无雾清晰图像．具体算法流程如图1所示。

![](images/5f9f25f22afb55e3395d928dea54b373907c70995734aaf054c0f92be2c75266.jpg)  
图1算法流程图

# 2.1透射率细化算法改进

# 2.1.1大气光值A修正

因为大量的雾通常会导致图像出现发亮或发白的颜色。由于图像中可能存在颜色比大气光更加明亮的物体，导致一个本来不应该作为大气光参考值的结果被用作大气光的估计。为了更加精确地对大气光进行估计,根据这样一个理论：通常，那些亮度小的灰蒙蒙部分(如天空)中像素的方差总体来说比较小。基于这个认识,Kim 等人[1提出了一个基于四叉树子矩阵分割的分层遍历方法。首先把输入的原图像看做一个大的矩阵,再把这个大矩阵划分成四个大小相等的子矩阵；然后计算出子矩阵内所有像素的均值与这些像素的标准差的差值,再记录下这个差值为每个子矩阵评分．最后，选择具有最高得分的子矩阵,并将其继续划分为更小的四个子矩阵。重复这个过程直到被选中的子矩阵小于某个提前指定的门限值。最后，在这被选定的子矩阵中，记录下使得距离最短的颜色(即离纯白色最近的颜色，归一化后的像素值表示为(1,1,1))作为大气光A的精确估计值:

$$
A ^ { c } = \operatorname* { m i n } _ { c \in \{ R , G , B \} } \left\| I ^ { c } \bigl ( x \bigl ) - \bigl ( 1 , 1 , 1 \bigr ) \right\|
$$

# 2.1.2大气散耗函数的精确估计

由于有雾图像的最小值 $W { \left( x \right) }$ 中包含丰富的景深信息，因此以 $W { \left( x \right) }$ 作均值滤波后的图像为引导图，对 $W { \left( x \right) }$ 作融合梯度信息的改进引导滤波，来保持图像边缘平滑和细节信息的同时避免景深突变处产生光晕效应:

$$
W \big ( x \big ) = \operatorname* { m i n } _ { c \in \{ R , G , B \} } I ^ { c } \big ( x \big )
$$

$$
V ^ { \prime } \big ( x \big ) = t g i f \Bigg ( a \nu e r a g e W \big ( y \big ) , W \big ( x \big ) \Bigg )
$$

$V ^ { \prime } { \left( x \right) }$ 是融合梯度信息引导滤波后获取的大气散耗函数的粗略估计。

由式(1)(9),当图像远景部分的雾较浓时,大气散耗函数的估计值会偏大，导致图像过亮；而当近景部分图像本身像素值较大时，大气散耗函数的估计值就会偏小,使得近景部分颜色暗沉。因此，引入函数 $\sigma ( x )$ 来解决这些问题:

$$
\sigma ( x ) = | V ^ { \prime } ( x ) - W ( x ) |
$$

当 $\sigma ( x )$ 的值较大时，表征图像的近景部分，当 $\sigma ( x )$ 的值较小时，表征图像的远景部分。结合 $\sigma ( x )$ 和大气散射函数的粗略估计值得到大气散射函数的精确估计 $\tilde { V } ( \boldsymbol { x } )$ ：

$$
\tilde { V } ( x ) = V ^ { \prime } ( x ) \biggl ( 1 { - } \frac { \sigma ( x ) } { A } \biggr )
$$

其中：A为大气光值 $A ^ { c }$ 的平均值.这样就能精确地区分出浓雾和近景区域的大气散耗函数.根据大气散耗函数的特性，需要对其进行范围限制，即：

$$
V \big ( x \big ) = \mathrm { m a x } \big ( \mathrm { m i n } \big ( \eta \widetilde { V } \big ( x \big ) , W \big ( x \big ) \big ) , 0 \big )
$$

其中： $\eta$ 是为了保留一定的雾,提高视觉效果,本文设为 $0 . 9 5$ 。

# 2.1.3透射率修正

因为透射率是由景深与大气散射系数一起决定的，所以可以通过大气散耗函数间接求透射率：

$$
t { \big ( } x { \big ) } = 1 - { \frac { V { \big ( } x { \big ) } } { A } }
$$

为避免由于透射率在景深突变与天空明亮区域的不适应，而导致透射率估计偏小出现的光晕现象，本文设定阈值 $K$ ，根据 $K$ 值，将图像的天空区与非天空区进行区别，减弱光晕效应。由于 $\mathrm { W } ( \mathbf { x } )$ 中包含图像的景深信息,因而本文依据 $\mathrm { W } ( \mathbf { x } )$ 和大气光强 $\boldsymbol { A } ^ { c }$ 的平均值A的距离大小来区别该区域是否为明亮区域(如天空)，设定阈值K，则透射率为

$$
t { \big ( } x { \big ) } = { \left\{ \begin{array} { l l } { \qquad t { \big ( } x { \big ) } } & { { \big | } A - W { \big ( } x { \big ) } { \big | } > K } \\ { { \displaystyle { \frac { K } { { \big | } A - W { \big ( } x { \big ) } { \big | } } t { \big ( } x { \big ) } } } } & { { \big | } A - W { \big ( } x { \big ) } { \big | } \leq K } \end{array} \right. }
$$

# 2.2阈值K的自适应获取

Jiang等人[12]通过经验对 $K$ 值进行选取,Sun 等人[13]设置$K = 8 0$ ，再对 $K$ 进行归一化。但是对于不同的图像，由于明亮区域和图像大小的不同，设定的阈值 $K$ 也应该不同，所以本文通过图像的亮度分量图 $L$ ,计算出 $L$ 中明亮区域即像素值大于或等于大气光 $A ^ { c }$ 的最小值像素点个数 $\mathbf { \xi } _ { l }$ 占图像总像素点个数$m$ 的百分比，设定阈值 $K$ ：

$$
L = 0 . 5 0 1 1 ^ { * } R + 0 . 4 7 0 8 ^ { * } G + 0 . 0 2 8 1 ^ { * } B
$$

$$
K = \frac l m
$$

# 2.3 图像复原

根据上述，已知大气光值 $A ^ { c }$ 、透射率 $t ( x )$ ，就可以反演复原出无雾清晰图像 $J ^ { c ^ { ' } } ( x )$ ，即

$$
J ^ { c ^ { ' } } \left( x \right) = \frac { I ^ { c } \left( x \right) - A ^ { c } } { \operatorname* { m a x } \left( t \left( x \right) , t _ { 0 } \right) } + A ^ { c }
$$

为避免 $t { \big ( } x { \big ) }$ 过于小，本文设定 $t _ { 0 }$ 的值为0.1。

由于近似估计，本文去雾算法计算出的透射率会相对偏小，从而使得大部分像素值都小于本文算法求得的透射率，经去雾后，像素值相对于大气光值的差就会被增大，相当于像素值会变得更小，所以导致复原后的图像整体会偏暗。因此需要对复原后的图像 $J ^ { c } \overset { \prime } { ( } \boldsymbol { x } )$ 进行亮度增强,本文采用非线性叠加的方法调整亮度，增强后的图像为 $J ^ { c } \left( x \right)$ ，即

$$
J ^ { c } \left( x \right) = J ^ { c ^ { ' } } \left( x \right) + \left( 1 - J ^ { c ^ { ' } } \left( x \right) \right) \times J ^ { c ^ { ' } } \left( x \right) \times o
$$

$o$ 为增强倍数,本文设为0.2.

# 3 实验结果及分析

实验编程环境为 Matlab8.3 版本，操作系统为Windows7,计算机硬件配置为Intel(RCoreTMi7-6700 CPU $\textcircled { a } 3 . 4 0 \mathrm { G H z }$ 以及16 GB RAM。

# 3.1主观评价

He[5引导滤波窗口大小为20.本文算法中，窗口大小设为33，选取三组有雾图像进行实验，实验图像均来自文献[4]，并从透射图、复原结果图进行对比分析，实验结果如图2\~4所示。

图2（e）是图1（b）的局部细节放大图，可以看出He[4算法未细化的透射图存在明显细节丢失现象；图2（f）显示了对透射图进行引导滤波处理后的结果，图像细节信息比图2（e）丰富；图2（g）显示了本文算法对透射图进行处理后的结果,图像细节信息明显更加优于图2（e）（f），因此复原后的无雾图像细节变得清晰可辨认，如图 $2 ( \mathrm { h } ) { \sim } ( \mathrm { j } )$ 所示。

![](images/1962e85d94b5df07026c1cafd1d9825f6c3923fb8f8c6c09a8bd6f96e5fc10cf.jpg)  
图2本文算法与 $\mathrm { H e } ^ { [ 4 , 5 ] }$ 算法去雾效果对比

图3（e）是图3（b）的局部细节放大图，可以看出He[4]算法未细化的透射图在景深突变边缘与天空区域存在边缘模糊现象；图3（f）显示了对透射图进行引导滤波处理后的结果，图像仍然存在边缘模糊现象；图3（g）显示了本文算法对透射图进行处理后的结果，图像边缘变得更加清晰，使得复原后的无雾图像在天空区域和景深突变处具有更好的视觉效果,如图3（h)～（j）所示。

由图4（e）可以看出He[4算法未细化透射图复原后的图像在景深突变处存在明显的光晕效应；图4（f）显示了对透射图进行引导滤波处理再复原后的结果,图像仍然存在光晕效应；图4（g）显示了本文算法对透射图进行细化处理后再复原的结果，基本改善了景深突变处的光晕现象,使得复原后的无雾图像在天空区域和景深突变处具有更好的视觉效果。

# 3.2客观评价

熵（entropy）是用来表明任何一种能量在空间中的均匀分布程度。图像的信息熵E值越大，则图像中偏离图像直方图高峰灰度区的大小越大,所有灰度值出现的机率趋于相等，图像携带的信息量越大，信息越丰富。

![](images/52eaa8abb18ce1e8f23424b98fd05edf8de4c03ca49d318f45a5727c9d11ffd1.jpg)  
图3本文算法与 $\mathrm { H e } ^ { [ 4 , 5 ] }$ 算法去雾效果对比

PSNR峰值信噪比,是目前图像质量评价中使用最为普遍和标准的一种指标，是基于对应像素点间的误差，即基于误差敏感的图像质量评价，取值越大代表图像质量越好。

因此，本文分别使用信息熵E和峰值信噪比PSNR对实验结果进行质量评价，如表1所示，本文算法参考评价值与He[4未细化透射图以及He[5]引导滤波细化透射图的去雾效果相比明显更好。同时， $\mathrm { H e } ^ { [ 5 ] }$ 引导滤波算法与本文所应用的融合梯度信息的引导滤波算法时间复杂度都为O(n)本文算法保留了He[5]引导滤波算法优良的的时间复杂性,具体参考数据如表1所示，从表中数据可以得出He[5]引导滤波算法耗时大约是本文算法的两倍。

![](images/bb07c9c64e73a832bdb022e0229f43a95f2645e9f45e09bae0f51dfae8cf34e3.jpg)  
图4本文算法与 $\mathrm { H e } [ 4 , 5 ]$ 算法去雾效果对比

表1客观质量评价  

<html><body><table><tr><td>图像名称</td><td>算法</td><td>E</td><td>PSNR</td><td>运行时间/s</td></tr><tr><td rowspan="3">图像1 (600*400)</td><td>未细化</td><td>6.8420</td><td>10.3181</td><td>0.366</td></tr><tr><td>引导滤波</td><td>7.2095</td><td>11.7993</td><td>3.044</td></tr><tr><td>本文算法</td><td>7.5417</td><td>14.4196</td><td>1.112</td></tr><tr><td rowspan="3">图像2 (600*450)</td><td>未细化</td><td>6.6788</td><td>8.4916</td><td>0.411</td></tr><tr><td>引导滤波</td><td>6.7325</td><td>8.7446</td><td>3.480</td></tr><tr><td>本文算法</td><td>7.1264</td><td>10.1152</td><td>1.257</td></tr><tr><td rowspan="2">图像3</td><td>未细化</td><td>7.3120</td><td>9.7011</td><td>0.406</td></tr><tr><td>引导滤波</td><td>7.5266</td><td>10.7403</td><td>3.477</td></tr><tr><td>(450*600)</td><td>本文算法</td><td>7.8345</td><td>18.2064</td><td>1.227</td></tr></table></body></html>

# 4 结束语

针对目前去雾算法中存在的光晕效应与细节丢失等问题，本文所提出的去雾算法，较好的保持了图像细节信息，避免了光晕效应，对去雾后的图像进行了亮度增强，因此，本文算法复原后的无雾图像在视觉效果与客观质量评价指标方面都有着良好的表现．本文算法适用于各类有雾图像的清晰化处理，具有良好的鲁棒性，同时降低了算法的时间复杂度．下一步的研究目标是使本文算法能够运用到目标跟踪、目标识别、视频监控、遥感图像等的实时处理中.

# 参考文献：

[1]禹晶，徐东彬，廖庆敏．图像去雾技术研究进展[J].中国图象图形学 报,2011,16 (9): 1561-1576.   
[2]朱淼良，钱徽．自然景物中大气退化模型的研究[J].计算机辅助设计 与图形学学报,2001,13(9):793-799.   
[3]TanRT.Visibility in bad weather from a single image[C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.2Oo8:1-8.   
[4]He K, Sun J,Tang X. Single image haze removal using dark channel prior [J].IEEE Trans on Pattern Analysis & Machine Intelligence,2011,33(12): 2341.   
[5]He K,Sun J,Tang X.Guided image filtering[J].IEEE Trans on Pattern Analysis & Machine Intelligence,2013,35(6):1397-409.   
[6]Tarel JP, Hautiere N.Fast visibility restoration from a single color or gray level image [C]// Proc of International Conference on Computer Vision. 2010:2201-2208.   
[7]曾接贤，余永龙．双边滤波与暗通道结合的图像保边去雾算法[J]．中 国图象图形学报,2017,22(2):147-153.   
[8]Narasimhan,S G,Nayar S K.Contrast restoration of weather degraded images [J].IEEE Trans on Pattern Analysis& Machine Intelligence,2003, 25 (6): 713-724.   
[9]Cox LJ.Optics of the atmosphere-scattering by molecules and particles [J]. IEEE Journal of Quantum Electronics,1977,24(7): 779-779.

[10]谢伟，周玉钦，游敏．融合梯度信息的改进引导滤波[J]．中国图象图

形学报，2016,21(9):1119-1126.

[11]KimJH,JangWD, SimJY,et al. Optimized contrast enhancement for realtime image and video dehazing [J]. Journal of Visual Communication & Image Representation,2013,24(3):410-425.

[12]蒋建国，侯天峰，齐美彬．改进的基于暗原色先验的图像去雾算法[J].电路与系统学报,2011,16(2):7-12.  
[13]孙小明，孙俊喜，赵立荣，等．暗原色先验单幅图像去雾改进算法[J].中国图象图形学报,2014,19(3):381-385.