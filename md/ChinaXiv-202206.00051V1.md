# 基于近红外和可见光差分特征的图像融合方法

赵国辉，张鹤

(杭州海康威视数字技术股份有限公司 产品研发中心，杭州 310051)

摘要：暗光环境拍摄的图像通常存在昏暗、噪声、偏色等退化问题。为此，提出一种基于差分特征的可见光与近红外融合方法。首先，观察到近红外与可见光图像成像不一致性，通过两者结构性差异构造差分特征。其次，利用差分特征映射为融合权重进行权重融合。最后，采用偏色校正方法对融合后易产生偏色区域进行亮度复原，使得融合后偏色区域颜色真实自然。提出方法能切实有效地利用近红外信息，输出高质量清晰图像。实验结论表明，该方法在主管感受和客观评价上均优于现有算法。

关键词：图像融合；差分特征；近红外；偏色校正 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.03.0134

Near-infrared and visible images fusion based on differential feature

Zhao Guohui, Zhang He† (Hangzhou HikvisionDigitalTechnologyCo,Ltd,R&D Center,HangZhou310051,China)

Abstract:Images captured indimlightoften suferfromsevere degradations,suchaslowvisibility,intensivenoisesand colordistortion.Totacklethese isues,thispaperproposedanear-infraredfusion methodbasedonimage diferentialfeature. First,itintroducedthedirentialapwhichcapturestheinherentdiscrepancyofstructuresinthetwodierenttypsof images.Then,itconducted feature mappng functions to formanoptimal weight mapand recoverd a visually pleasing result. To reduce the possblecolorcast inthe imagerecovery process,itfuture proposed jointlyrecovering the final image by using the visible image toreduce overbrightnessin the fused image.The proposed algorithmcanalways takefulladvantageof the near-infrared images and generate natural high qualityoutputs.Experimental results demonstrate the proposed method is superior to existing fusion methods in terms of visual quality and quantitative measurements.

Key words:image fusion; differential feature; near-infrared light; color correction

# 0 引言

夜晚环境下光线不足，导致相机设备拍摄的画面存在亮度暗、对比度低、噪声大和色彩失衡等不同程度的退化问题，影响人们的视觉观感和有用信息的自动提取。研究如何复原夜间低照度图像不仅可以改善图像的观赏性，也可以被广泛应用于智能监控、无人驾驶和地形侦探等许多领域，具有十分重要的现实意义和应用价值。针对此问题，一种原始直接的方法是增大可见光补光，但这种措施不可避免带来强光污染，特别是在视频监控领域，强光导致驾驶员眼睛暂时性失明，容易引发道路安全问题。其他图像调试方法如增大光圈，等同于扩大进光量以利于提高图像亮度，但也降低了成像景深；放慢快门，相当于增大曝光时长来提升图像信噪比，但容易导致运动物体模糊，出现鬼影。

虽然现阶段图像低照度研究领域已有不少优秀成果出现但仅依赖单一输入图像，信息匮乏条件下难以甄别随机噪声和真实图像信息，这些基于去噪[1,2]和增强[3-6]方法往往会导致细节纹理丢失且不善于自适应补偿因光照不足引起的对比度损失，效果提升欠佳。因而采用可见光和近红外成对图像的低照度增强算法[7-16]得到了越来越多的关注和研究，这类方法采用两颗图像传感器，通过特殊的光学元器件，其中一颗通过增加近红外补光采集到包含图像亮度信息和物体轮廓的近红外灰度图像，另外一颗采集到包含场景色彩信息的可见光彩色图像。然后通过图像融合算法将两颗采集到的图像信息进行融合，获得同时具有可见光色彩与近红外图像亮度的图像。又因为人眼对近红外波段光具有弱感知性，近红外补光并不会影响到人们正常工作生活，降低对驾驶人员眩光刺激，因此，近红外可见光融合技术在夜间监控场景下具有十分重要的应用价值。

与传统的长波红外热成像[17]不同，近红外利用了景物反射成像，体现了景物的几何形状，与可见光融合的目的是获取干净、通透和清晰的彩色图像。但如何最大化利用近红外的亮度信息同时保证融合图像色彩真实可信以便适合于人的视觉特征或计算机监控等设备的后续识别利用，是非常有挑战性的研究课题。由于近红外与可见光在成像表观上存在着显著差异，直接将近红外的灰度图像代替可见光的亮度通道图像导致色彩偏离问题非常严重。Krishnan 等[7]提出使用近红外的梯度结构信息引导彩色图像进行噪声去除。Shen 等[9]构造一副尺度图显式表示近红外梯度的可信度，通过求解最佳尺度图进而恢复可见光图像。Su等[结合多尺度小波分析将含噪声的可见光图像与近红外图像进行小波分解，权衡可视性与对比性将两者进行融合，以达到重构清晰图像的目的。考虑到近红外对物体的细节感知较为理想，Jee等[10]采用联合双边滤波，以近红外图像作梯度结构信息引导可见光辅助降噪，继而叠加近红外纹理细节。由于可见光与近红外成像存在不同，这种方式会错误的导致可见光图像一些固有的边缘梯度变得模糊。受深度学习理论的启发，一些基于样本学习的图像融合方法[13\~16]应运而生。Li等[13]提出一种包含编码器、融合层和解码器模型的深度学习框架用于可见光与红外图像融合，端到端的网络不需要人为寻找先验信息。唐等[14]采用感受野更大的U-Net网路结构，通过对多尺度上下文信息进行更加有效地编码保证可见光与近红外融合的视觉效果。Mei等[16]分别为降噪、增强和融合设计了独立分工的子网络，输入图像依次经过三个子网络得到增强后的图像。这样子网络的任务相对简单，容易训练收敛。上述基于深度学习的方法取得了令人瞩目的成就，但其缺陷是需要大量训练样本和算力。图像融合质量依赖于训练的标签素材、模型容量、损失函数选取及超参数选择等诸多方面。

目前低照度可见光与近红外融合技术主要停留在学术研究阶段，工业场所应用不多，主要有以下原因：一是物体对可见光与近红外反射存在结构差异，复原后的图像极易因亮度失调产生偏色现象；二是大多数方法是利用近红外图像结构信息协助低照度图像降噪和细节增强，对近红外亮度信息利用有限，恢复图像效果不够理想；三是现有的方法计算复杂度都较大，算力要求高，难以满足高清视频实时处理和嵌入式系统上实现。

观测到近红外图像对于同种颜色亮度表现不一致性，本文提出一种基于差分特征的近红外与可见光图像融合方法，简称为差分融合方法。总体框架如图1所示，首先，可见光亮度与近红外亮度进行图像差分得到差分特征，差分特征物理反映了两种光谱反射差异区域与程度，可以对融合中易产生偏色的区域起到良好的约束作用；其次，基于差分特征与融合之间的相关性，定义特征映射函数，将差分特征映射为对应所需的融合权重项；然后，对可见光与近红外图像进行亮度域加权融合得到融合图像的亮度；鉴于暗光环境下对图像的纹理细节削弱，亦需将近红外的纹理迁移整合进来；最后，整合亮度颜色信息重构出彩色的清晰图像。此外，本文还提出一种基于差分特征的偏色校正方法，在充分利用红外信息兼顾融合结果视觉上明亮通透信噪比高的同时，保证颜色还原的准确和真实。实验结果表明，提出方法简单但切实有效克服图像融合过程中产生的偏色问题，视觉效果得到显著提升，具有非常快的速度可用在一些实时监控任务中。

![](images/2487e58e565a10ceb1b2052567f5061fe4ec60cc942206164ec94977c5040401.jpg)  
Fig.1Overall framework of the algorithm

# 1 算法介绍

# 1.1数据获取

为获取真实低照度可见光图像与近红外图像样本对，本文选用相机型号为HIKiDS-2CD9736-AMS双传感器900万(分辨率 $4 0 9 6 \times 2 1 6 0 )$ 专业相机，该款相机采用分光棱镜将可见光与近红外光分别导入对应传感器成像，其中可见光与近红外图像间仅存在微小的刚性空间变换，利用棋盘格校准获取配准矩阵并自动应用于所有图像样本对。

测试相机架设在道路上，杆高度6米，抓拍距离24米，以捕获过往车辆全貌。搭配频曝环保补光灯(LED 频闪灯和近红外爆闪灯)，其中近红外图像采用近红外爆闪补光，波长为 $7 3 0 { \sim } 1 0 0 0 \mathrm { n m }$ ，可见光图像采用LED频闪灯补光，亮度相对比较微弱，仅为获取环境色彩。道路监控核心目标是为行驶车辆，因此相机快门时间设置为 $2 \mathrm { m s }$ ，避免车辆运动拖尾，增益遵循常规设置为50。由于快门时间短且补光弱，相机传感器感光不足导致可见光图像信噪比非常低，出现大量噪声。为了简化问题，本文事先将输入图像数据经过图像信号处理(ISP)进行降噪，将一副低照度噪声图像转变为低照度模糊图像，这样后续不用考虑图像噪声问题，专注于图像融合课题。

输入可见光图像格式为YCbCr格式，其中Y表示可见光亮度通道，CbCr则表示可见光色度通道。输入近红外图像为单通道，以 $\mathbf { N }$ 表示近红外亮度通道。近红外与可见光亮度域图像融合公式定义如下：

$$
\tilde { \mathbf { Y } } ( x ) = \mathbf { Y } ( x ) ( 1 - a ( x ) ) + \mathbf { N } ( x ) a ( x )
$$

其中， $x$ 为表示像素坐标位置的2D向量，Y为可见光图像的亮度辐射图，N为近红外图像的亮度辐射图， $\tilde { \mathbf { Y } }$ 为期望得到的多光谱融合亮度图。 $a$ 表示近红外图像的融合权重，用于描述输出图像中近红外亮度所占比例，其值介于0到1区间。由于融合权重随着像素的位置而变化，因此其整体图又称之为融合权重图。上式表明，若已知图像场景中的融合权重信息 $\mathbf { \Delta } _ { a }$ ，相应地就可以计算得到期望值。由于融合权重图 $\mathbf { \Delta } _ { a }$ 未知，则基于上述物理模型多光谱融合方法的本质可以看成是估计参数 $\boldsymbol { a }$ 以从Y和N重建到 $\tilde { \Upsilon }$ 的过程。

# 1.2差分特征

近红外光与人眼可见光在光学频谱上非常接近，一般情况下，近红外图像与可见光图像在亮度分布状况视为相同。但对某些物体，特别是彩色物体，两者反射成像方面存在不小差异，甚至出现截然不同的情况。对大量自然成对拍摄的可见光近红外图像进行统计分析，发现两者成像主要存在以下不同：a）近红外图像对于同颜色亮度表现不一致；b）可见光纹理信息可能在近红外图像上消失不见；c）可见光图像与近红外图像存在亮度逆转的情况。举例说明，图2显示了一组交通监控领域夜间抓拍图像，同是红颜色车辆，其对应的近红外图像有的明亮，有的灰暗。图2左上衣服上的条纹在其对应的近红外图上不可见，图2左上黑色安全带变成图2左下的灰白色。这些若不加以区分融合得到的图像势必产生偏色失真、纹理细节丢失问题。

![](images/62b2296595510211bd72667fe51ec3bf210722bb52f2f11104b3284395486b71.jpg)  
图1算法整体框架  
图2近红外成像的不一致性，输入可见光图(上)和对应近红外图(下)Fig.2The discrepancy between RGB(top) and NIR(bottom) images若假设自然图像局部区域对可见光的反射特性与对近红外反射特性相同，其可见光图像局部亮度与近红外图像局部亮度也应当接近。对两幅亮度图像进行低通保边滤波，可选图像中值滤波、双边滤波[18]和引导滤波[19]等，起到平滑局部,消除奇异点的作用，得到两幅图像的亮度特征图Ybase 和 $\mathbf { N } ^ { \mathrm { b a s e } }$ 。以可见光图像亮度图双边滤波为例：

$$
\Upsilon ^ { \mathrm { b a s e } } \left( x \right) = \frac { 1 } { k ( x ) } \sum _ { y \in \Omega } \mathrm { e x p } ( \frac { | y - x | ^ { 2 } } { \sigma _ { s } ^ { 2 } } ) \mathrm { e x p } ( \frac { | \Upsilon ( y ) - \Upsilon ( x ) | ^ { 2 } } { \sigma _ { r } ^ { 2 } } ) \Upsilon ( y )
$$

其中，Ybase 是一个局部平滑后的亮度特征图像， $k ( x )$ 是一个归一化因子：

$$
k ( x ) = \sum _ { y \in \Omega } \exp ( - \frac { \mid y - x \mid ^ { 2 } } { \sigma _ { s } ^ { 2 } } ) \exp ( - \frac { \mid \Upsilon ( y ) - \Upsilon ( x ) \mid ^ { 2 } } { \sigma _ { r } ^ { 2 } } )
$$

左正则项 $\sigma _ { s }$ 定义了基于像素距离的空间域权重，而右正则项 $\sigma _ { r }$ 定义基于颜色强度差的值域权重。这两个函数均是定义在局部区域 $\Omega$ 上的高斯距离函数。根据经验，通常设置 $\sigma _ { s }$ 为20的领域窗口， $\sigma _ { r }$ 设置为所有图像的颜色范围的 $1 \%$ 是一个较好的选择。将可见光亮度特征图像 $\mathrm { Y ^ { \mathrm { b a s c } } }$ 与红外亮度特征图像 $\mathbf { N } ^ { \mathrm { b a s e } }$ 差分得到差分图像，这里使用高亮补光的近红外光亮度特征 $\mathbf { N } ^ { \mathrm { b a s e } }$ 减去可见光亮度特征Ybase：

$$
\scriptstyle \mathrm { d i f f } ( x ) = \mathbf { N } ^ { \mathrm { b a s e } } ( x ) - \mathbf { Y } ^ { \mathrm { b a s e } } ( x )
$$

差分图像物理地反映了自然图像局部区域对可见光和近红外光反射特性差异。如图3所示，差分图(为便于显示取绝对值)越亮的地方，说明近红外与可见光反射特性差异越大。例如司机穿的黑色短袖，对应的近红外图像特别明亮。直接采用这些区域的近红外亮度极易导致图像发灰偏色。差分图越暗的地方，说明近红外与可见光反射特性差异越小。例如驾驶台以及司机系的黑色安全带，对应的近红外图像与可见光成像非常接近。这些区域，融合时使用更多比例的近红外亮度，使得恢复的图像整体更加明亮通透，信噪比高，而且也不易出现偏色问题。

![](images/6e113d8e0b8166bad6b54f27434bce54bf3d05d13ee16c85421d553d628af31e.jpg)  
图3差分特征

# 1.3特征映射

差分特征朴素地反映了不同光谱间成像差异现象，得益于此有利先验信息，可在图像融合时最大化利用近红外信息，同时避免融入不良红外信息导致色彩偏差的问题，取得理想的图像效果。根据对差分特征与融合偏色的关联观察分析，不难得出其与近红外融合权重具有以下推论：

$$
\begin{array} { c l c r } { { \int \mathrm { d i f f } \left( x \right) { \to } 0 \Rightarrow a ( x ) { \to } 1 } } \\ { { \mathrm { d i f f } \left( x \right) { \to } \infty \Rightarrow a ( x ) { \to } 0 } } \end{array}
$$

其中，当差分值趋近于0时，可见光与近红外反射特性接近，融合近红外权重趋近于最大值1。而当差分值趋近无穷大时，可见光与近红外反射特性相反，融合近红外权趋近于最小值0。应当注意到的是，差分值为大于0的正数区域，该部分近红外图像亮度大于可见光图像亮度。由于近红外图像依靠闪光拍摄获取，这种情况占据图像绝大多数。但也存在差分值小于0的负数区域，该部分近红外图像亮度小于可见光图像亮度，一般出现在近红外图像阴影遮挡区域。阴影的存在并不会影响图像真实感，反而增加图像明暗通透感。综上所述，建立一种如图4示意的分段线性特征映射函数：

![](images/edb41f61b65c5649686235bb54be9468402a0c0c6cbbbc95926a4d938dfc79d0.jpg)  
图4差分特征映射 Fig.4Feature mapping

图4表示当差分特征值为负值或正值但比较小时，融合近红外权重最高设定为 $a _ { \mathrm { m a x } }$ ，起到最大化利用近红外信息的作用；当差分特征为正值且大于阈值 $t _ { 0 }$ 时，融合红外权重比例逐渐降低至 $a _ { \mathrm { m i n } }$ ，以降低因近红外光物体反射强烈带来的色偏影响。通过此映射步骤，本文将差分特征图像映射为红外融合权重图，图4中，阈值 $t _ { 0 }$ 和 $t _ { 1 }$ 根据实验经验而来，通常设置为20和120；融合权重上下限 $a _ { \mathrm { m a x } }$ 和 $a _ { \mathrm { m i n } }$ ，用于调节融合红外的程度，一般设置为0.8和0.1。由于差分特征输入数据范围是确定且可枚举的，对于八位深度图，差分值落在负255与正255之间，因此该步骤常预先制作成查找表，以便加速图像处理过程。

# 1.4图像融合

经特征映射获取融合权重图 $a$ 后，通过代入式(1)直接求解，可得到融合图像的亮度辐射图。然而，在弱光环境下拍摄的可见光图像由于感光不足，存在纹理线条模糊、细节梯度退化问题，因此需要提取对应近红外图像的表面纹理细节图层迁移进入融合图像，从而丰富图像细节和提升画面层次感。

$$
\mathbf { Y } _ { \mathrm { F u s i o n } } \left( x \right) { = } \tilde { \mathbf { Y } } ( x ) + \mathbf { D } ( x )
$$

其中， $\tilde { \Upsilon }$ 是将可见光图像Y和近红外图像 $\mathbf { N }$ 两者亮度域进行加权融合的结果，D为迁移叠加的纹理细节图层，即

$$
\mathrm { D } ( x ) = \lambda _ { \mathrm { v I S } } ( \mathrm { Y } ( x ) - \mathrm { Y } ^ { \mathrm { b a s e } } ( x ) ) + \lambda _ { \mathrm { N I R } } ( \mathrm { N } ( x ) - \mathrm { N } ^ { \mathrm { b a s e } } ( x ) a ( x ) )
$$

$\lambda _ { \mathrm { v I S } }$ 和 $\lambda _ { \mathrm { { N I R } } }$ 分别用来控制可见光图像和近红外图像纹理叠加强度，参数值设置越大，清晰度越为显著，但容易导致图像锐化过度，部分像素截断溢出问题，因而一般情况下设置为1.0。对于近红外图像纹理，本文同样乘以融合权重，避免在近红外图像与可见光图像存在梯度逆转时出现伪影等不自适应问题。

对于融合图像的颜色获取，用输入的低照度可见光UV通道乘以相应亮度增益值得到融合后的数值。

$$
\begin{array} { r } { \left\{ \mathrm { U } _ { \mathrm { F u s i o n } } ( x ) = \mathrm { U } ( x ) \mathrm { Y } _ { \mathrm { G a i n } } ( x ) \ , \right. } \\ { \left. \mathrm { V } _ { \mathrm { F u s i o n } } ( x ) = \mathrm { V } ( x ) \mathrm { Y } _ { \mathrm { G a i n } } ( x ) \ . \right. } \end{array}
$$

其中， $\mathrm { Y } _ { \mathrm { G a i n } } \left( x \right) { = } \mathrm { Y } _ { \mathrm { F u s i o n } } \left( x \right) / \mathrm { Y } ( x )$ 为亮度增益值。最后将融合得到的YUV色彩转换为RGB空间即得到彩色融合效果图。如图5所示，经过融合增强后的整体图像变得干净通透，人脸更加清晰。同时，输出融合图像颜色与可见光颜色基本一致，色彩真实可信。

![](images/253ed13013c2f877af480097ae8ebbc5f9d185219682f444963fdd5950fe5c3c.jpg)  
Fig.3Differential feature   
图5可见光图像与融合效果比较  
Fig.5Comparison of the visible image and fusion image

# 1.5偏色校正

低照度可见光图和近红外闪光图相比，其信噪比更低一些。虽然通过图像增强手段，例如LIME方法[3]可将可见光图像变得明亮，但理论上信息量不会增加，且会带来一系列色噪及光晕变大等负面问题，如图6(d)。因此，融合近红外图像亮度越多，越有利于提升信噪比。本文曾尝试过将可见光和近红外图像对通过最大化亮度思想进行权重设计。这种方法能极大提升融合图像明亮度和清晰度，但缺点也十分明显，图像偏色失真情况较为严重，与人眼主观感受不符，如图6(e)，暗红色轿车车身偏粉色而墨绿色草丛偏青色。差分融合方法为避免颜色失真，在一些近红外反光异常区域限制近红外亮度的使用，但无法保证融合图像的高信噪比，因此红外利用率不够充分。若再进一步提高红外使用率则会引入人眼可察觉的偏色问题。特别是人眼对红色特别敏感，能够分辨出不同亮度的红色，如图6(c)，暗红色车身略显偏粉色。此外，夜间图像常因补光不足亦或白平衡问题影响导致颜色暗淡或偏色，这些都需要对图像进行进一步偏色校正处理。

首先，将差分融合后的图像转到RGB色彩空间以便计算颜色特征。对于常见的颜色，如红、绿、蓝，这些颜色在融合后加入过量近红外亮度导致偏色发生。因此，根据融合前后图像亮度变化及每个像素颜色强弱特征，设计如下公式校正偏色：

$$
\mathrm { I } ^ { c } ( x ) = \mathrm { I } ^ { c } ( x ) - \operatorname* { m i n } ( 1 - \mathrm { I } ^ { c } ( x ) , \mathrm { I } ^ { c } ( x ) , \mathrm { k } ( x ) ) \mathrm { s } ( x ) , c \in \{ r , g , b \}
$$

其中， $\mathbf { k } ( x ) = \mathrm { m a x } ( \tilde { \mathbf { Y } } ( x ) - Y ( x ) , 0 )$ 为融合前后亮度增加数值，$\mathsf { s } ( x ) = \mathsf { m a x } \operatorname { I } ^ { c } ( x ) - \mathsf { m i n } \operatorname { I } ^ { c } ( x )$ 代表当前像素颜色强弱数值。使用偏色校正后的融合结果如图6(f)所示。可以看出融合图像充分有效地利用了红外信息，明亮通透，颜色真实，信噪比高。图像整体更接近于红外闪光图像的亮度风格，但具有可见光真实色彩。

![](images/a2f04eaf0cfa4c335c9b933ac96ce29002bc3718a3e0545dcae510fec489effc.jpg)  
图6偏色校正  
Fig.6Color cast correction

# 2 实验效果

为验证提出方法的有效性，本节除选取部分交通场景的实拍图，其他均为公开的近红外与可见光数据对，与目前最为先进的方法在融合效果上比较来验证所提出方法的有效性。对比方法包含三维块匹配(BlockMatching3D，BM3D)降噪算法[1]、变分法[9]、深度学习融合法[14]等具有代表性和影响力的方法。

# 2.1 视觉主观分析

图7是针对夜间交通场景下抓拍的低照度图像与近红外爆闪图像进行融合处理。(a)是低照度可见光图，(b)是闪光近红外图，(c)是BM3D的，(d)是文献[9]的，(e)是文献[14]的，(f)是本文的。交通场景图像抓拍的难点主要在于拍摄主体是车辆，运动速度快，因此抓拍图像比较黑暗，图像噪点很大；另外，夜间光源较为复杂，拍摄时除补光灯外，还受到路灯、车大灯等强光影响，因而可见光图像光晕较大。近红外路存在红外爆闪灯补光，因而整体明暗均衡，清晰度较高且噪点光晕较小。从视觉上看BM3D降噪后与原图风格一致，虽然具有噪点较小优势，但图像清晰度和对比度明显不足。文献[9]处理效果在红外反射异常区域出现模糊不清问题，且基于变分的模型方法主要利用近红外梯度信息，而忽视了近红外亮度，处理后图像仍然显得昏暗，缺少近红外明暗高对比度的特性。文献[14]基于深度学习端到端的处理，无须设计和提取特征，但可以看出车灯光晕及路面照射区域亮度都有错误提升，究其原因可能是低照度可见光与近红外融合的真实数据集非常难以获取，文献[14]选择了长曝光图像作为训练集的标签图像，导致网络功能最终变成可见光降噪和增强，缺乏近红外信息导致视觉可见性没有得到很好的改善。相比之下，差分融合方法恢复的车辆纹理清晰易见且色彩鲜明，道路交通标线等得到凸显，整体视觉效果更接近于近红外爆闪图像，显得更佳。

![](images/74a286edcd975f5d45213b8084915713969502ee714bf2a5d9638c26c4c72ea3.jpg)  
图7交通场景数据car融合增强效果比较

图8是暗室拍摄的低照度图像及用红外灯闪光拍摄的近红外图像。(a)是低照度可见光图，(b)是闪光近红外图，(c)是BM3D的，(d)是文献[9]的，(e)是文献[14]的，(f)是本文的。虽是静态场景但由于环境比较暗，原始可见光噪点比较多，信息完全被噪声湮没而基本丢失。BM3D复原图像虽然能较好抑制噪声，但清晰程度远低于使用近红外融合的结果。文献[9]恢复的明暗反差较差，视觉上不自然协调。文献[14]不能有效地利用近红外信息，某些区域不够清晰，例如图中包装盒上的字迹比较模糊。相比之下，差分融合方法对物体恢复的颜色和清晰程度在视觉上面比较理想，而且包装盒上的字迹在方法结果中也较为清晰的体现。

![](images/9e0be302d1e35f415d986ddea7aa1dec77e445a4d10ca5ed7290a22302d992e3.jpg)  
Fig.7Visual comparison of image fusion on car example   
图8公共数据集teapot融合增强效果比较  
Fig.8Visual comparison of image fusion on teapot example

图9是暗室拍摄的陶瓷古玩等文物照片和对应近红外闪光照片。(a)是低照度可见光图，(b)是闪光近红外图，(c)是BM3D的，(d)是文献[9]的，(e)是文献[14]的，(f)是本文的。原始图像色彩噪点较大，图片比较朦胧。BM3D复原图像虽消除了噪声，但画面较糊，颜色暗淡。文献[9]恢复图像较为清晰，但不能够有效去除噪点。如兵马俑上仍存在一些色彩噪声。文献[14]复原图像虽为清晰，但对比度和通透度略显不足。相比之下，差分融合方法综合了可见光色彩与近红外亮度优点，同时克服各自的不足，取得了较为出色的融合效果，主要体现在：融合图像噪声、色彩准确度、可见光信息保留程度、图像对比度以及近红外信息量等方面。

![](images/57604716abd21113c9dbd38b45b19ca1a9701ef483f1852c7998db1da1a9c620.jpg)  
图9公共数据集bowls 融合增强效果比较Fig.9Visual comparison of image fusion on bowls example

# 2.2客观定量比较

理论上，图像融合领域并没有十分客观的评价指标，主要以主观评价为主，但低照度图像融合本质上可视作图像清晰化增强的过程。由于微光成像会减少图像的边缘变换特征和细节信息，图像恢复的清晰程度可由处理后图像的边缘强度和细节变化反差来衡量。在图像增强领域，较为广泛使用的是Hautiere等[20]提出的可见边梯度法，即利用新增的可见边的数量比(e)，平均梯度比(r)和饱和像素比( $\cdot \sigma ^ { \cdot }$ )来描述输入原始图像和融合后图像的增强效果：

$$
e = \frac { n _ { r } - n _ { 0 } } { n _ { 0 } } , \overline { r } = \frac { \overline { g } _ { r } } { \overline { g } _ { 0 } }
$$

其中： $n _ { 0 }$ 和 $n _ { \mathrm { { i } } }$ 分别表示可见光图像和融合图像中可见边的数目，它是图像局部对比度的反映； $\overline { { g } } _ { 0 }$ 表示原图像的平均梯度，g,表示恢复后图像的平均梯度。另一指标 $\sigma$ 表示恢复图像新增的饱和像素比例，这些饱和像素通常是由算法过度增强所致。考虑到图像噪声对评测指标的影响，可见光图像做了降噪处理。一般情况下， $e$ 和 $\overline { r }$ 的值越大，表明处理后图像恢复的地方纹理细节越多，图像越为清晰。而 $\sigma$ 的值越高，表明融合后图像溢出的像素比例越多，地方细节损失越多。

从表1数据结果可以说明，相比之下，本文对真实交通场景和暗室实验场景低照度增强清晰化具有较明显的优势，融合后恢复的可见边数量和平均梯度比值均较高。文献[9]中算法在近红外与可见光图像反射趋向异同时容易失效，恢复图像区域趋于平滑，细节匮乏，甚至出现效果不如BM3D降噪的情况。图7，文献[9]在路面车灯照射区域清晰度较BM3D效果差，新增可见边 $e$ 值为负数。文献[14]能有效避免了融合出现偏色失真的现象，但该方法所使用的网络模型往往对近红外的信息利用不足，例如图7，车灯光晕不能够得到有效抑制，恢复效果并不清晰理想。本文提出方法则能很好地避免融合偏色失真和光晕伪迹放大现象，且充分汲取了近红外的有用信息，亮度和清晰度均为接近闪光图像效果。例如，本文在所有结果均得出可观的可见边数目，保持最好的 $\mathbf { \Delta } _ { e }$ 和$\overline { r }$ 得分。而 $\sigma$ 较高，究其原因在于本文方法融合更多近红外阴影，而非增强过度所致。

# 2.3运行时间

提出方法在性能速度方面具有明显优势，文献[9]基于变分的方法通过多次迭代来取得融合最优解。文献[14]基于深度学习方法采用了U-Net网络模型，包含数十次卷积操作，计算并不便宜。对于 $\mathbf { M } \times \mathbf { N }$ 的图像，本文算法的时间复杂度为O(MN)，且与任何其他参数无关。显然易知，提出方法比其他方法都要快得多，且当输入图像越来越大时，复杂度也能以线性的速度较慢增长。本文最后在海思嵌入式平台使用

SIMD指令同时执行32个像素的并行计算，在 $4 0 9 6 \times 2 1 6 0$ 高清图像耗时为 $3 1 ~ \mathrm { m s }$ ，可以满足实时视频处理需求。

表1不同方法融合后的可见梯度边和平均梯度比  
Tab.1Values of $e$ androbtained by different approaches   

<html><body><table><tr><td>原图</td><td>方法</td><td>e</td><td></td><td>9</td></tr><tr><td rowspan="4">图7</td><td>BM3D[1]</td><td>0.000</td><td>1.000</td><td>0.08%</td></tr><tr><td>文献[9]</td><td>-0.282</td><td>1.638</td><td>0.08%</td></tr><tr><td>文献[14]</td><td>0.354</td><td>2.550</td><td>0.10%</td></tr><tr><td>差分融合</td><td>0.719</td><td>3.029</td><td>0.43%</td></tr><tr><td rowspan="4">图8</td><td>BM3D[1]</td><td>0.000</td><td>1.000</td><td>0.00%</td></tr><tr><td>文献[9]</td><td>0.357</td><td>1.501</td><td>0.01%</td></tr><tr><td>文献[14]</td><td>0.329</td><td>1.448</td><td>0.05%</td></tr><tr><td>差分融合</td><td>0.775</td><td>1.844</td><td>0.05%</td></tr><tr><td rowspan="4">图9</td><td>BM3D[1]</td><td>0.000</td><td>1.000</td><td>0.00%</td></tr><tr><td>文献[9]</td><td>0.551</td><td>3.127</td><td>0.00%</td></tr><tr><td>文献[14]</td><td>0.643</td><td>2.251</td><td>0.00%</td></tr><tr><td>差分融合</td><td>0.829</td><td>3.218</td><td>0.00%</td></tr></table></body></html>

# 3 结束语

本文介绍了一种基于差分特征的近红外与可见光融合的低照度图像增强方法。观测到近红外与可见光成像差异问题，提出利用差分特征构造生成融合权重，最大化利用近红外亮度信息增强图像信噪比，输出接近于近红外补光亮度风格的图像，但具有可见光真实色彩自然。所提方法非常简单，易于在嵌入式平台优化实现。与最新其他研究方法比较，本文方法不仅效果优势明显，性能也可满足工业的实时处理需求。

基于差分特征的图像融合方法在多源异构图像恢复具有普适通用原则，未来将探索研究其在近红外/可见光图像去雾，闪光/非闪光图像联合降噪等图像恢复领域的应用。

# 参考文献：

[1]Dabov K,Foi A,Katkovnik V,et al. Image denoising by sparse 3-D transform-domain collaborative filtering [J].IEEE Trans on Image Processing,2007,16 (8): 2080-2095.   
[2]Zhang Kai,Zuo Wangmeng,Chen Yunjin,et al.Beyond a gaussian denoiser:Residual learning of deep CNN for image denoising[J]. IEEE Trans on Image Processing,2017,26(7):3142-3155.   
[3]Guo Xiaojie,Li Yu,Ling Haibin.LIME:low-light image enhancement via illumination map estimation [J].IEEE Trans on Image Processing, 2017,26 (2): 982-993.   
[4]Chen Chen,Chen Qifeng,Xu Jia,et al.Learning to see in the dark [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. Piscataway,NJ:IEEE Press,2018:3291-3300.   
[5]王萍，孙振明．多级分解的 Retinex 低照度图像增强算法[J].计算 机应用研究,2020,37(04):1204-1209.(Wang Ping,Sun Zhenming. Multi-level decomposition Retinex low-light image enhancement algorithm [J].Application Research of Computers,2020,37 (04):1204- 1209.)   
[6]刘寿鑫，龙伟，李炎炎，等．基于HSV 色彩空间的低照度图像增强 [J]．计算机工程与设计,2021,42(09):2552-2560.(Liu Shouxin,Long Wei,Li Yanyan,et al.Low-light image enhancement based on HSV color space [J].Computer Engineering and Design,2021,42 (09): 2552-2560.)   
[7]Krishnan D,Fergus R.Dark flash photography [J].ACM Trans on Graphics,2009,28 (3):96.   
[8]Zhuo Shaojie, Zhang Xiaopeng,Miao Xiaoping,et al.Enhancing low light images using near infrared flash images [C]// Proc of IEEE International Conference on Image Processing. Piscataway,NJ:IEEE Press,2010:2537-2540.   
[9]Shen Xiaoyong,Yan Qiong,Xu Li,et al. Multispectral joint image restoration via optimizing a scale map [J].IEEE Trans on Pattern Analysis and Machine Intelligence,2015,37 (12): 2518-2530.   
[10] Jee S,Kang MG.Sensitivity improvement of extremely low light scenes with RGB-NIR multispectral filter array sensor[J].Sensors,2019,19 (5): 1256.   
[11] Su Haonan, Jung C,Yu Long.Multi-spectral fusion and denoising of color and near-infrared images using multi-scale wavelet analysis [J]. Sensors,2021,21(11): 3610.   
[12]Li Zhuo,Hu Haimiao,Zhang Wei,et al.Spectrum characteristics preserved visible and near-infrared image fusion algorithm [J].IEEE Trans on Multimedia,2021,23:306-319.   
[13]Li Hui,Wu Xiaojun.Densefuse:a fusion approach to infrared and visible images [J].IEEE Trans on Image Processing,2019,28 (5):2614-2623.   
[14]唐超影，浦世亮，叶鹏钊，等．基于卷积神经网络的低照度可见光与 近红外图像融合 [J]．光学学报,2020,40(16):31-39.(Tang Chaoying, Pu Shiliang,Ye Pengzhao,et al.Fusion of low-illuminance visible and near-Infrared images based on convolutional neural networks [J].Acta Optica Sinica,2020,40 (33):31-39.)   
[15]Jung C,Zhou Kailong,Feng Jiawei.Fusionnet:multispectral fusion of RGB and NIR images using two stage convolutional neural networks [J]. IEEE Access,2020,8:23912-23919.   
[16] Mei Lin,Jung C.Deep fusion of RGB and NIR paired images using convolutional neural networks [C]// Proc of IEEE International Conference on Pattern Recognition.Piscataway,NJ:IEEE Press,2021: 6802-6803.   
[17]Li Guofa,Lin Yongjie,Qu Xingda.An infrared and visible image fusion method based on multi-scale transformation and norm optimization [J]. Information Fusion,2021.71:109-129.   
[18] Tomasi C,ManduchiR.Bilateral filtering for gray and color images [C]// Proc of IEEE International Conference on Computer Vision.Piscataway, NJ:IEEE Press,1998:839-846.   
[19]He Kaiming,Sun Jian,Tang Xiaoou.Guided image filtering [J].IEEE Trans on Pattern Analysis and Machine Intelligence,2013,35 (6):1397- 1409.   
[20]Hautiere N,Tarel JP,Aubert D,et al.Blind contrast enhancement assessment by gradient ratioing at visible edges [J].Image Analysis and Stereology,2011,27 (2): 87-95.