# 一种减少色彩失真的自适应单幅图像去雾算法

唐慧，任杰文，鲍旭东(东南大学 计算机科学与工程学院，南京 210096)

摘要：基于暗通道先验的单幅图像去雾算法是目前最为高效的图像去雾技术，然而当图像中某些场景不完全满足暗通道先验时，去雾处理后的图像中常常出现大量伪影和色彩失真，因此需要根据图像对该方法进行修正。假设图像场景亮度越高，暗通道越不可信；场景饱和度越低，暗通道越不可信。基于该假设重新设计了图像的暗通道置信度，以补偿场景不完全满足暗通道先验时估算过大的暗通道值；另外对图像进行后置增强处理，以提升图像的视觉效果。提出的算法对三类具有代表性的雾天图像进行实验，实验结果显示，与相关算法相比，该算法在缓解色彩失真、去除伪影等方面表现更好。该算法通过设计暗通道置信度克服了图像场景不完全满足暗通道先验时暗通道值估计偏大的问题，显著提升了暗通道先验去雾模型对不同雾天场景的适应能力。

关键词：图像去雾；暗通道置信度；饱和度；亮度 中图分类号：TP391.4 doi:10.19734/j.issn.1001-3695.2018.10.0850

Color preserved self-adaptive single image defogging method

Tang Hui, Ren Jiewen, Bao Xudong (School of Computer Science& Engineering,Southeast University,Nanjing 21oo96,China)

Abstract:The single image hazeremoval algorithm basedondark channel priori iscurrentlythe most efficient image defogging technology.However,when theimage does not fullysatisfythedark channel priori,manyartifactsand color distortion willappear in theprocessed image,sothatthe method should be modified according tothe image situation.This paper proposed the hypothesis thatthe brighter the scene is,the lesscredible thedark channel priori willbe;the lower the scene saturation is,the less credible thedark channelpriori willbe.Basedon this asumption,an image'sdark chanel confidence was designed to limit thedark channel value when thescene does notfull satisfythe dark channel prior. Furthermore,the image was post-enhanced to improve the visual efect.Threetypical fog weather images were selected to verifythe effectiveness ofthe proposed method.The experimentalresultsshow that the proposed algorithmperforms better in preserving color and removing artifacts comparing to some curent related defogging algorithms.A new dark chanel confidence calculation method is designed toovercome the problem thattheestimation of dark channel value willbe too large when theimage scene does not fullsatisfythe dark channelpriori.The proposed method improves the adaptabilityof the dark channel priori defogging model to different foggy scenes.

Key words: image defogging; dark channel confidence; saturation; lightness

# 0 引言

随着处理技术在交通监控，安防设备，医疗成像，地形勘察、智能驾驶，摄影艺术等场合发挥着越来越无可替代的作用。然而在户外采集图像时，常常因恶劣的天气条件导致图像降质，其中雾和霾是最常见的。由于雾霾条件下的降质图像损失了一定程度的对比度和色彩信息，将严重影响相关视觉应用的性能表现，因此有必要对它们进行去雾处理。

传统的图像去雾的研究可以分为两大类，基于图像增强的算法和基于图像复原的算法。近年来由于计算能力的提高，也出现了一些基于深度学习的图像去雾算法I，但是基于深度学习的算法需要大量的测试数据，应用成本较高。对传统方法的研究依然很活跃[4]。基于图像复原的去雾算法研究雾霾条件下图像退化的物理过程，建立成像物理模型，并反映其成像过程，针对性更强，是目前去雾研究的热点[5]。

在雾霾天气条件下，最终到达相机镜头的光包括两部分：在传播过程中由于大气散射作用被不断衰减的场景辐射光，和随着传播路径延长而不断叠加在其上的空气光。因此，为了复原原本的场景辐射，估算精确的场景深度是基于图像复原去雾算法的一个共同之处。然而对于单幅有雾图像，不能唯一确定其场景深度，需要引入合适的先验条件与假设。

Fattal等人[5]通过假设透射率和物体表面着色局部不相关，估算场景反照率以及介质透射率，这种基于物理模型的方法能够获得不错的去雾效果，但当雾气严重时，该假设失效。Tan等人[7]假设局部区域大气光为常数，无雾图像比有雾图像对比度更高，通过最大化局部对比度复原图像，尽管去雾效果令人印象深刻，但此方法可能是物理无效的。何凯明等人[8]首次提出暗通道先验，通过计算有雾图像的暗通道值，近似估算出对应的场景深度以及透射率，对户外图像取得了很好的去雾效果。然而暗通道先验只能大致估算有雾图像中的场景透射率，需要计算复杂度很高的软抠图方法加以优化；并且当某些场景不满足暗通道先验时，常常出现过饱和、伪影、过度曝光、色彩失真等问题。尽管此方法不够完善，但简单高效的暗通道先验得到了广泛认同，大量研究工

作在此基础上展开。

为了降低去雾算法的复杂度，许多研究使用效果近似的结构转换滤波器代替软抠图方法，如关联滤波器[9]、双边滤波器[10]、引导滤波器[1]等。汤红忠等人[5]采用传播滤波替代双边滤波，对基于暗通道的方法进行修正。针对估算全局大气光值可能导致的过度曝光，伪影，色彩不自然等问题，Xu等人[12]提出了亮通道先验更为合理的估算场景局部大气光值；为了解决在某些特殊的场合下，暗通道先验条件可能失效，Li等人[9提出了基于暗通道亮度及局部对比度计算暗通道置信度的方法，来度量图像场景满足暗通道先验的程度，以提升对更多种类场景的去雾效果。然而基于局部对比度的方法不能很好的符合大气散射规律，容易导致去雾图像中出现某些不合理的过度增强。蒋建国等人[13]通过抑制场景中亮度接近大气光值位置的透射率，从而防止伪影和色彩失真，然而由于算法是基于像素抑制的，而透射率是基于局部区域计算的，导致抑制结果在局部区域内亮度差异明显，且当天空及水面亮度变化很大时，算法失效。Wang等人[14]通过分割天空区域从而避免对其计算暗通道，然而当天空与景物边界模糊时，算法效果不佳。

本文在上述暗通道先验去雾相关研究的基础上，受Li等人[9暗通道置信度方法的启发，提出了一种新的置信度计算方法，并且对复原图像场景辐射度不足的情形进行后置增强处理，选取引导滤波器代替软抠图方法，实现了线性时间复杂度，在缓解色彩失真、去除伪影等方面表现更好，显著提升了暗通道先验去雾模型对不同雾天场景的适应能力。

# 1 相关工作

在图像去雾研究中，通常用以下简化大气散射模型描述有雾图像的组成：

$$
\pmb { I } \left( x , y \right) = \pmb { J } \left( x , y \right) t \left( x , y \right) + \pmb { A } \left( 1 - t \left( x , y \right) \right)
$$

其中： $I ( x , y )$ 表示观测图像， $\boldsymbol { J } ( x , y )$ 表示场景辐射度， $t \big ( x , y \big )$ 表示介质透射率， $A$ 表示大气光。对于一幅有 $N$ 个像素的彩色图像，式(1)中有 $4 N + 3$ 个未知量，而仅有 $3 N$ 个已知量，通常需要先引入先验条件或假设估算得到 $A$ 和 $t \big ( x , y \big )$ ，进而再计算得到复原去雾图像 $J ( x , y )$ 。式(1)右侧第一项称为直接衰减项，第二项称为空气光项。直接衰减项描述了场景辐射在传播介质中被不断衰减后的部分，空气光项则描述了由于大气散射作用，大气表现为光源，发出的光叠加在场景辐射光路中的部分。

当大气同质时，透射率 $t \left( x , y \right)$ 表示为

$$
t \left( x , y \right) = e ^ { - \beta d \left( x , y \right) }
$$

其中： $\beta$ 表示大气散射系数， $^ d$ 表示场景深度。该式指出当雾气浓度不变时，透射率仅与场景深度呈指数相关。

# 1.1暗通道先验及去雾流程

所谓暗通道先验，即对于室外光照充足，景物中存在大量阴影的图像，其中普遍存在暗通道一一局部区域像素的最小颜色通道值非常小[8]，记做 $\pmb { J } ^ { d a r k }$ ：

$$
J ^ { { d a r k } } \left( x , y \right) = \operatorname* { m i n } _ { \left( i , j \right) \in \Omega \left( x , y \right) } \left( \operatorname* { m i n } _ { c \in \left\{ r , g , b \right\} } J ^ { c } \left( i , j \right) \right)
$$

其中： $\Omega$ 表示以 $\left( x , y \right)$ 为中心半径为 $R$ 的局部区块， $J ^ { c }$ 表示图像的一个颜色通道。通常情况下，晴朗天气所拍摄图像在去除天空区域后，其暗通道值非常接近于0。

$$
J ^ { d a r k }  0
$$

结合式(3)(4)与(1),可以推导得出局部区块透射率 $\tilde { t } \left( x , y \right)$ 为

$$
\tilde { t } \left( x , y \right) = 1 - \operatorname* { m i n } _ { \left( i , j \right) \in \Omega \left( x , y \right) } \left( \operatorname* { m i n } _ { c \in \left\{ r , g , b \right\} } \frac { I ^ { c } \left( i , j \right) } { A ^ { c } } \right)
$$

由于雾气彻底去除会导致图像失去判断景深的参照，引入参数 $\omega ( 0 < \omega < 1 )$ 修正透射率，为了简化计算，通常将式(5)写做

$$
\tilde { t } \left( x , y \right) = 1 - \omega ^ { * } \frac { I ^ { d a r k } } { \bar { A } }
$$

其中： $\bar { A }$ 表示大气光的均值， $\omega$ 通常取 $0 . 9 5$ 。由于此时得到的透射率图是基于图像局部区域的粗略估计，在强边缘附近不能准确反映出场景深度的变化，常导致复原图像中出现光晕和伪影。为了在透射率图中引入场景结构信息，需要使用软抠图或功能类似的结构转换滤波器如引导滤波器，联合双边滤波器等，对 $\tilde { t } \left( x , y \right)$ 进行优化得到改善的透射率 $t \big ( x , y \big )$ 。

基于暗通道先验，He等人[8改进了传统估算大气光值的方法，先取原图中暗通道值前 $0 . 1 \%$ 的像素，再从其中选取亮度最高的像素值作为全局大气光值 $A$ ，最终得到复原去雾图像为

$$
J ( x , y ) { = } A { + } \frac { I ( x , y ) { - } A } { m a x ( t ( x , y ) , t _ { 0 } ) }
$$

其中： $t _ { 0 }$ 为透射率下限，通常设为0.1，以避免对去雾图像过度增强。

# 1.2暗通道置信度

与大多数先验条件一样，暗通道先验是一种基于统计和观察结果的经验性总结，在某些特殊的场合下先验条件可能会失效。如完全不满足暗通道先验的天空区域，由于其透射率总是接近于0，在去雾图像中常常会表现出严重的伪轮廓与噪声；此外，对于颜色及亮度接近天空区域的景物，如平滑的水面，灰白的水泥路及建筑表面，也不完全满足暗通道，这将导致暗通道值估计偏大，进而导致复原图像过饱和。针对这个问题，Li等人[9]提出了暗通道置信度的概念对暗通道方法进行修正，对于图像中某些不满足暗通道先验的场景，适当降低其对应暗通道置信度，以补偿此时估计过大的暗通道。

Li的方法中暗通道置信度基于以下两个假设来定义：a)局部亮度变化越小，暗通道越不可靠；b)暗通道强度越高，可靠性越低。据此，导出暗通道置信度模型及修正后的透射率为

$$
C ( x , y ) { = } m a x ( C _ { 1 } ( x , y ) , C _ { 2 } ( x , y ) )
$$

$$
t ( x , y ) = 1 - \omega ^ { * } \frac { C ( x , y ) I ^ { d a r k } } { \overline { { A } } }
$$

其中： $C _ { 1 }$ 和 $C _ { 2 }$ 分别表示通过对图像局部对比度与暗通道亮度度量得到的暗通道置信度，取值在区间[0.1]中。当局部区域具有可检测纹理的情况下， $C ( x , y )$ 的值趋近于1，可以完全消除雾霾；当区域平滑时， $\boldsymbol { C } ( \boldsymbol { x } , \boldsymbol { y } )$ 的值随亮度增加而减小，使得修正后的透射率变大，可以防止复原图像因原图场景不完全满足暗通道先验而出现过饱和，或在平滑区域引入伪影。

# 2 本文算法

暗通道先验之所以成立，主要基于三类场景元素，即大量的阴影、艳丽的色彩以及本身为暗色的景物[8]，如图1所示。通过经验和分析可知，满足暗通道先验的场景恰恰是图像中亮度较低、饱和度较高的景物，这也正是户外风景照及城市景观照常常表现出的特征。遗憾的是，由于雾天图像中常常出现大面积亮度较高，且饱和度相对低的景物，如天空、水面、颜色接近灰白的岩石、墙面、水泥路等，完全不满足或不能完全满足暗通道先验，导致基于暗通道先验的去雾方法错误的估计了雾气的厚度，进而对雾天图像进行过度增强，导致复原结果出现不同程度的过饱和乃至严重的伪影。

![](images/88caf15ca2b78da4fc03747c436b7127ac84608891f95ea4a6020a05b0a93876.jpg)  
图1暗通道先验成立要素。  
Fig.1Main factors account for dark channel prior.

本文针对暗通道先验成立的基本要素设计了一种新的计算暗通道置信度的方法，该方法基于两点假设：a)图像场景亮度越高，暗通道越不可信；b)场景饱和度越低，暗通道越不可信。为了得到图像的亮度和饱和度，先将原图转换到HSV颜色空间。由于暗通道置信度本身是为了修饰暗通道而提出的，因此置信度的计算也应该基于局部区块。另外，在修正暗通道的过程中，应尽量减少对原本去雾效果的抑制，本文对HSV颜色空间图像的亮度和饱和度通道分别使用最小值和最大值滤波器，滤波半径与计算暗通道时相同。

$$
V _ { m i n } \left( x , y \right) = \operatorname* { m i n } _ { \left( i , j \right) \in \Omega \left( x , y \right) } I ^ { \nu } \left( i , j \right)
$$

$$
S _ { m a x } \left( x , y \right) = \operatorname* { m a x } _ { \left( i , j \right) \in \Omega \left( x , y \right) } I ^ { s } \left( i , j \right)
$$

其中： $V _ { m i n }$ 和 $S _ { m a x }$ 分别表示经最小、最大值滤波器作用后的亮度和饱和度通道， $I ^ { \nu }$ 和 $I ^ { s }$ 分别表示图像在HSV空间的亮度与饱和度通道。而引导滤波器与功能相近的结构转换滤波器相比，细节保持能力更强，且能够在线性时间内实现[1]。为了在计算得到的 $V _ { m i n }$ 和 $S _ { m a x }$ 中加入其缺少的原图细节和纹理信息并保留其原本强度，本文采用引导滤波器，以原图作为引导图像进行滤波得到 $V _ { m i n } ^ { ' }$ 和 $S _ { m a x } ^ { ' }$ 。根据假设，暗通道置信度随着亮度的增加和饱和度减小而急剧降低，这与sigmoid函数曲线相符。根据以上分析，本文提出分别基于亮度和饱和度估算的新的置信度 $C _ { 1 }$ 和 $C _ { 2 }$ 为

$$
C _ { 1 } \left( x , y \right) = \frac { 1 } { 1 - e x p \Bigg ( \frac { V _ { m i n } ^ { \prime } - \overline { { A } } } { k _ { 1 } } \Bigg ) }
$$

$$
C _ { 2 } \left( x , y \right) = \frac { 1 } { 1 - e x p \left( \displaystyle \frac { - S _ { m a x } ^ { ' } } { k _ { 2 } } \right) }
$$

其中： $\bar { A }$ 表示大气光的均值， $k _ { 1 }$ 和 $k _ { 2 }$ 是sigmoid函数曲线的缩放系数，这里经验性的取 $\frac { \bar { A } } { 8 }$ 与 $0 . 0 5$ 。式(12)中将 $\bar { A }$ 作为阈值，是由于当原图亮度 $I ^ { c }$ 和大气光值 $A ^ { c }$ 的差值很小时，由式(7)可知， $\pmb { I } ^ { c } - \pmb { A } ^ { c }$ 将被除以一个很小的透射率 $t$ ，导致通道间的颜色差异及像素间的亮度差异被数倍的放大，容易造成伪影和色彩失真[13]。而式(13)中将0作为阈值，是考虑到雾天图像本身由于雾气的原因，显著降低了场景的饱和度，为了在抑制暗通道值估计偏大的同时，尽可能地不影响原本的去雾效果，当饱和度为0时，其置信度为0.5。最后，基于假设，饱和度与亮度同时对暗通道置信度有影响，最终置信度由式（14)得出。

$$
C ( x , y ) = s q r t { ( C _ { 1 } ( x , y ) ^ { * } C _ { 2 } ( x , y ) ) }
$$

由于已经引入了暗通道置信度抑制过度增强，所以估算透射率步骤中的修正参数 $\omega$ 及复原图像步骤中的透射率下限$t _ { 0 }$ 不再需要，式(6(7)分别改写为

$$
t ( x , y ) = 1 - \frac { C ( x , y ) { \cal I } ^ { d a r k } } { \overline { { { \cal A } } } }
$$

$$
J ( x , y ) = A + { \frac { \pmb { I } ( x , y ) - A } { t ( x , y ) } }
$$

综上所述，本文算法总结如下：以改进的暗通道置信度度量场景满足暗通道先验的程度，并使用引导滤波器优化暗通道的场景结构信息，以避免暗通道值估计不准确导致复原图像出现严重的色彩失真与伪影。

# 3 实验结果与分析

本文实验开发环境为VS2017，64位 $^ { C + + }$ 编译器及计算机视觉库OpenCV3.1.0。在暗通道及暗通道置信度的计算中，$\Omega$ 取 $1 5 ^ { * } 1 5$ ，引导滤波器窗口半径 $R$ 取 $2 0 \ , \ \varepsilon$ 分别取0.1，10。由于去雾过程中所用的最小值滤波器及引导滤波器能够在线性时间内实现[8,11,15]，去雾算法的时间复杂度仍然是线性的。

本文选取了三幅典型的图像对算法分别进行视觉效果和定量评价，根据图像内容三幅图像分别记为Mountain、Lake和Gugong。为了说明本文算法的有效性，在算法评价中选取了与本文算法较为接近的He 等人方法[8]、Wang 等人方法[14]、Li等人方法[]以及 $\mathrm { \Delta X u }$ 等人[12]方法加入对比。

# 3.1去雾视觉效果分析

根据式(14)计算暗通道置信度的实验结果如图2所示，从图2(b)中可以看到，对于天空和水面区域，其置信度相应较低，抑制了暗通道估计偏大的问题，去雾结果图2(c)是清晰自然的。

Mountain图像(图3(a))属于一类较为常见的雾天场景，其雾气浓重且场景辐射度不足。这种情况下复原图像常常会出现亮度偏低，伪影及块效应。可以看到(b)\~(e)场景均有不同程度的伪影，其中(b)在天空及浓雾部分出现大量伪影；(c)试图将天空区域分割出来单独计算，然而原图中天空边界不明显，在这种情况下难以实现； (d)使用关联滤波器不能准确估计暗通道值，导致复原图像缺少精细的场景结构信息，且文中所提出的后置增强算法不能有效提升图像的可视效果；(e)视觉失真最少，但是在天空区域的边缘仍然出现了伪影。而本文算法基于原图的亮度和饱和度对暗通道值进行修正，并参照Li等人的方法[1对复原图像进行亮度重映射，取得了效果清晰且过渡自然的去雾结果，如图3(f)所示。

Lake图像（图4(a)）为实际采集的校园图像，其主要特征为场景中有大面积的天空及反光的水面区域，完全不满足暗通道先验。由前文讨论可知，这种情况下基于暗通道先验去雾容易造成天空和水面出现大量伪影、色彩失真甚至噪声。从图4中可以看到(b)在天空和水面区域亮度极不均匀，且存在伪影；(c)能够较好地分割并处理天空部分，然而对于水面部分无能为力；(d)通过暗通道亮度和局部对比度估算暗通道置信度，在一定程度上避免了天空和水面的伪影，然而由于置信度估算不够合理，复原结果整体偏暗、亮度变化不自然；(e)在水面也出现了色彩失真和伪影。相对而言，本文结果(f)在实现去雾的同时有效地避免了伪影和颜色失真的问题，整体效果最好。

![](images/9e67694c0c333314de94e0f4e371da1b9ddbd82fe8a6c401f28bc4b2e4e7bcec.jpg)

图2本文方法计算暗通道置信度

Fig.2 Compute dark channel Confidence using our method

![](images/da6b5065d6c83e651c419b8e22301a7e721591a5674ebbd127bdfa77b12b0e3d.jpg)

Fig.3Experimental results of the Mountain image

![](images/53712ca5d9e3d03e8a39916e5825b88ff0c9a56f68e67f230b935ba4ceb030f8.jpg)  
Fig.4Experimental results of the Lake image

Gugong图像(图5(a))主要特征为大面积场景接近白色，缺少表面阴影，不完全满足暗通道先验。这种情况下基于暗通道先验去雾常常导致色彩失真。可以看到图 5(b)\~(d)四种去雾算法结果均有不同程度的色彩失真，原本接近白色的场景呈现出黄色甚至褐色；(d)由于不能精确的估算场景透射率在图像的强边缘（如人物）附近还存在光晕。相对而言(e)和(f)的复原结果较好，同时本文算法(f)比(e)色彩失真略少一点。然而由于暗通道先验本身的不足，本文算法虽然通过合理的估算其置信度，能够较好的避免天空水面的伪影和色彩失真，但为了权衡去雾效果，亦不能完全避免不完全满足暗通道先验场景部分的过饱和。

![](images/290929a411a139459bf4cbc63c6d44b613c3f609ddb50daa4b863f1b7497a84c.jpg)  
图5Gugong 图像实验结果  
Fig.5Experimental results of the Gugong image

# 3.2定量评价

除了视觉效果评价，本文还选取了两种图像质量评价工具分别对上述处理前后的图像进行定量评价。图像质量评价工具选用了Mittal等人提出的无参考图图像质量评价方法（blind/referenceless image spatial quality evaluator,BRISQUE)[17]和全盲图像质量评价方法（natural image quality evaluator,NIQE）[18]。

两种定量处理结果如表1和2所示，两种评价值均为越小越好。其中BRISQUE在图像空间中根据像素相关性计算图像质量。这个指标主要评价图像的“自然”特性，而过度去雾使得原图像出现了一定的失真，从表1中可以看出，几类方法的处理结果均比原图要差，但是相比较其他的方法，本文方法处理结果仍然表现出优势。在提出BRISQUE图像质量评价方法后，Mittal等人随后又提出了另一个质量评价方法NIQE。该方法总结了一个自然图像的统计模型，度量测试图像和这个模型的距离。Gugong图像由于存在大面积的浅色区域，因此反而是色彩失真最为严重的Li方法评价质量最高。从表2可以看出，本文算法处理后的NIQE值是相对较优的。

表1各方法处理前后BRISQUE 值对比  
表2各方法处理后NIQE值对比  

<html><body><table><tr><td colspan="7">Table 1 BRISQUE value before and after processing</td></tr><tr><td>图像</td><td>原图</td><td>He</td><td>Wang</td><td>Li</td><td>Xu</td><td>本文算法</td></tr><tr><td>mountain</td><td>19.9044</td><td>23.2747</td><td>19.9576</td><td>22.8309</td><td>22.3901</td><td>17.4717</td></tr><tr><td>lake</td><td>46.3612</td><td>52.8017</td><td>51.7829</td><td>60.0532</td><td>65.7201</td><td>50.5383</td></tr><tr><td>Gugong</td><td>36.454</td><td>43.0336</td><td>43.9314</td><td>41.4618</td><td>41.5759</td><td>41.0977</td></tr></table></body></html>

Table 2The NIQE values before and after processing   

<html><body><table><tr><td>图像</td><td>原图</td><td>He</td><td>Wang</td><td>Li</td><td>Xu</td><td>本文算法</td></tr><tr><td>mountain</td><td>5.3289</td><td>5.5429</td><td>5.4296</td><td>4.3491</td><td>4.5255</td><td>4.2617</td></tr><tr><td>lake</td><td>4.4926</td><td>4.4827</td><td>4.6737</td><td>4.7223</td><td>4.6117</td><td>4.1949</td></tr><tr><td>Gugong</td><td>2.9026</td><td>2.7512</td><td>2.7129</td><td>2.5699</td><td>2.6963</td><td>2.7273</td></tr></table></body></html>

# 4 结束语

本文在暗通道先验去雾相关研究的基础上，针对暗通道先验去雾模型常常导致复原图像在不完全满足暗通道先验的区域（如天空、水面）出现严重伪影和色彩失真的现象对暗通道去雾算法进行改进。通过分析暗通道先验成立的基本要素，本文基于亮度与饱和度更为合理的估算了雾天场景的暗通道置信度，显著克服了暗通道先验固有的不足；选择引导滤波器作为结构转换工具，实现了算法的线性计算复杂度；另外，针对重度雾霾条件下成像场景辐射度不足的情况，通过后置增强算法有效改善了其暗部细节的可视效果。

实验对比表明，本文算法相比较原始的暗通道去雾算法及相关改进算法，在缓解色彩失真、去除伪影等方面表现更好，显著提升了暗通道先验去雾模型对不同雾天场景的适应能力。

# 参考文献：

[1]徐岩，孙美双．基于多特征融合的卷积神经网络图像去雾算法[J]. 激光与光电子学进展,2018,55(3):031012.(Xu Yan,Sun Mei Shuang. Convolution Neural Network Image Defogging Based on Multi-Feature Fusion [J].Laser& Optoelectronics Progress.2018,55（3)：031012.)   
[2]姬旭丽，王亚刚，车芳.基于深度学习的图像去雾霾研究[J].信息 技术，2018（8）:106-110.(Ji Xuli,Wang Yagang,Che Fang.Image study on the dehaze based on deep learning [J]. Information Technology 2018（8）:106-110.)   
[3]Qin Manjun,Xie Fengying,Li Wei,et al.Dehazing for multispectral remote sensing images based on a convolutional neural network with the residual architecture [J].IEEE Journal of Selected Topics in Applied Earth Observations And Remote Sensing.2018,11(5):1645-1655.   
[4]Liang Yitao,Zhang Wenqiang,Zhao Kuibin,et al.A self-adaption singie image aenaze metnoa basea on clarity-evaiuation-runcuon ol image [C]//Proc of International Conference on Advanced Mechatronic Systems.2018.   
[5] 汤红忠，张小刚，朱玲,等．结合最小颜色通道图与传播滤波的单幅 图像去雾算法研究[J].通信学报.2017,38(1):26-34.(Tang Hong Zhong,Zhang Xiao Gang,Zhu Ling,et al. Study of single image dehazing algorithm based on propagated filtering and minimum color channels [J]. Journal on Communications.2017,38(1): 26-34.）   
[6]Fattal R. Single image dehazing [J].ACM Trans on Graphics,2008, 27(3): 1-9.   
[7]Tan R T. Visibility in bad weather from a single image [C]//Proc of IEEE International Conference on Computer Vision and Pattern Recognition.Washingtonm DC:IEEE Computer Society,2008.   
[8] He Kaiming, Sun Jian,Tang Xiaoou. Single image haze removal using dark channel prior [J].IEEE Trans on Pattern Analysis & Machine Intelligence,2011,33(12): 2341-53.   
[9] Li Bo, Wang Shuhang,Zheng Jin,et al. Single image haze removal using content-adaptive dark channel and post enhancement [J]. IET Computer Vision,2013,8(2):131-140.   
[10] Kopf J, Cohen MF,Lischinski D,et al.Joint bilateral upsampling [J]. ACM Trans on Graph,2007,26(3): 96.   
[11] He Kaiming, Sun Jian,Tang Xiaoou. Guided image filtering [C]//Proc of European Conference on Computer Vision.Berlin: Springer, 2010: 1-14.   
[12] Xu Yueshu,Guo Xiaoqiang,Wang Haiying,et al. Single image haze removal using light and dark channel prior [C]//Proc ofIEEE International Conference on Communications in China.2016.   
[13]蒋建国，侯天峰，齐美彬.改进的基于暗原色先验的图像去雾算法 [J]．电路与系统学报，2011,16(2):7-12.(Jiang Jian Guo,Hou Tian Feng,Qi Mei Bin.Improved algorithm on image haze removal using dark channel prior[J].Journal of Circuitsand Systems,2011,16(2): 7-12.）   
[14] Wang Gangyi,Ren Guanghui, Jiang Lihui,et al. Single image dehazing algorithm based on sky region segmentation [J]. Information Technology Journal,2013,12(6): 1168-1175.   
[15] He Kaiming,Sun Jian. Fast guided filter[J]. Computer Science,2015.   
[16] Li Bo,Wang Shuhang,Geng Yanbing.Image enhancement based on Retinex and lightness decomposition [C]//Proc of IEEE International Conference on Image Processing. 2011: 3417-3420.   
[17] Mittal A，Moorthy AK，Bovik AC. No-reference image quality assessment in the spatial domain [J]. IEEE Trans on Image Processing. 2012,21(12): 4695-4708.   
[18] Mittal A， Soundararajan R，Bovik A C. Making a'completely blind'image quality analyzer [J]. IEEE Signal Processing Letters,2013, 20(3): 209-212.