# 基于运动目标特征的关键帧提取算法“

田丽华，张咪，李晨(西安交通大学软件学院，西安 710049)

摘要：针对运动类视频特征不易提取，且其关键帧结果中易产生较多漏检帧的问题，提出了基于运动目标特征的关键帧提取算法。该算法在强调运动目标特征的同时弱化背景特征，从而防止由于运动目标过小而背景占据视频画面主要内容所导致的漏检和冗余现象。首先根据视频帧熵值将颜色变化明显的帧作为部分关键帧，对颜色未发生突变的帧根据运动物体的尺度不变特征变换(SIFT)获得帧内运动目标的特征点。最后分别根据帧熵值及运动物体 SIFT点分布提取视频关键帧。实验结果表明该算法所得关键帧结果集不仅漏检率较低且能够准确地表达原视频内容。

关键词：关键帧提取；混合高斯检测；SIFT特征点；感知哈希 中图分类号：TP391.41 doi: 10.3969/j.issn.1001-3695.2018.06.0363

# Key frame extraction algorithm based on feature of moving target

Tian Lihua, Zhang Mi, Li Chen† (School of Software Engineering,Xi'an Jiaotong University,Xi'an 71oo86,China)

Abstract:Motion featuresare difcult toextractwhicheasilyleads tomissdandredundantframes intheresult.Inorderto solvethis problem,this paperproposesa methodofkey frames extractionbasedon featureofmovingtarget.The methodreduces redundantrate and missedrateoftheresultsetbyemphasizing thefeaturesofthe moving target and weakening thebackground features of the frame.In this method,aframe withaburst entropychange is taken aspartof the keyframe firstly.Then,our method extracts the SIFTpoints of the moving target from the frameof which the entropy value has not suddenly changed. Finaly,itextractskeyframesaccordingtotheentropyandSIFTdistrbutionrespectively.Experimentalresultssowthatthe missrate ofthisalgorithmislow.Atthesame time,keyframeresultscanaccuratelyandcompletelydescribe themaincontent of the video.

Key Words: key frame extraction; gaussian mixed model detection; SIFT; perceptual hashing

# 0 引言

关键帧提取是视频检索的重要步骤，其提取结果质量好坏直接影响视频检索的效率。由于运动类视频中场景切换频繁，故其关键帧结果中存在较多漏检帧。运动类视频的关键帧提取方法多种多样。文献[1,2]提出通过分析光流场实现对运动场的分析从而提取关键帧。Ma等人[3]提出在运动对象状态发生变化处提取关键帧[3]。Li等人[4]提出了一种聚焦物体运动的关键帧提取算法，该方法将匀速运动的物体作为参照物，从而获得视频中运动目标并提取关键帧。针对视频中由于摄像机移动造成的物体运动，Guironnet等人[5]提出通过检测摄像机运动提取关键帧，根据镜头运动方式排列顺序不同，灵活地调整关键帧提取方法[5]。以上方法对运动类视频的关键帧提取能力有限，当视频中存在快速运动的物体时，关键帧结果中易产生漏检帧。

由于局部特征能更好地保留帧语义，故目前存在较多根据局部特征提取关键帧的算法。其中Hannane 等人[6提出根据帧SIFT分布直方图提取关键帧。Barbieri等人[7提出根据固定大小窗口提取候选帧，再根据候选帧间SIFT特征距离提取关键帧，然而该方法所得候选帧无法准确地描述运动目标的变化过程。

结合运动类视频特点，本文提出了基于运动目标特征的关键帧提取算法。该算法首先根据帧熵值选取颜色发生突变处的帧作为部分关键帧。对熵值未发生突变的帧，根据混合高斯模型获得帧内运动物体并提取其SIFT特征，计算 SIFT分布距离提取关键帧。根据运动物体SIFT分布特征提取关键帧，在强调帧内运动目标变化的同时弱化背景变化带来的影响，因此能够很好地捕获运动物体的变化过程。最后使用感知哈希算法获得帧指纹，计算其汉明距离去除结果中的冗余帧，以进一步提高关键帧对原视频的有效表达。

# 1 理论基础

# 1.1混合高斯模型

混合高斯建模(GMM)适用于对背景复杂的视频进行建模，从而检测出视频中的运动目标[8.9]。根据混合高斯模型检测运动物体，首先计算出帧中像素点在某时间段内样本值的概率密度等信息，接着根据统计差分中常见原则判定各像素点是否为帧背景内容。每读取新的视频帧时，首先根据当前帧更新模型，再遍历待处理帧中的各像素点，判断其是否为背景点。完成帧各像素点的处理后即能够得到该帧背景模型，然后根据背景得到帧前景。混合高斯模型能够很好地对内容复杂的视频进行背景建模。

# 1.2 SIFT特征

SIFT(scale invariant feature transform)特征点是一种稳定的局部特征。选取物体表面具有代表性的点来描述物体，这些点通常称为兴趣点[10]，如较暗区域亮度较高的点，明亮区域中亮度较低的点，物体边缘的特殊点等都可能成为兴趣点。兴趣点不会因为图像缩放或者旋转而产生较大变化，同时对于光线改变以及噪声干扰都具有一定鲁棒性。

# 1.3感知哈希

图像感知哈希技术也称为数字指纹，是对多媒体信息的总结。感知哈希是一类从多媒体表示到哈希值的单向映射，各图像都有其对应的指纹。

感知哈希算法首先去掉图片细节，忽略图像尺寸和比例差异，仅保留结构、阴影等基本信息。接着计算各帧灰度图的离散余弦变换（DCT）系数矩阵，仅保留左上角的 $8 ^ { * } 8$ 矩阵。计算所有像素灰度均值，比较矩阵各像素点与均值大小，大于或等于均值记为"1"，否则记为"0"，最后生成帧指纹。根据帧指纹计算汉明距离，判断帧相似性。

# 2 基于运动目标特征的关键帧提取

为强调视频中运动目标的变化，本文提出根据运动目标特征提取关键帧的算法。该算法首先计算帧熵值，选择颜色突变的帧作为部分关键帧。对颜色未发生突变的帧，根据帧内运动物体的SIFT分布提取关键帧。最后根据感知哈希算法去除结果集中的冗余帧。算法核心步骤流程如图1所示。

计算帧熵值：读入视频帧序列，根据式(1)(2)所示计算帧熵值，将熵值突变处的帧选为部分关键帧。

$$
p ( x _ { i } ) { = } N u m ( x _ { i } ) / m ^ { * } n
$$

$$
H = - \sum _ { i = 0 } ^ { 2 5 5 } p ( x _ { i } ) ^ { * } \log ( p ( x _ { i } ) )
$$

其中： $\mathbf { \sigma } _ { \mathbf { X } _ { i } }$ 代表视频帧像素点i处的灰度值， $\mathbf { m }$ 和 $\mathfrak { n }$ 分别为帧的高和宽。 $\mathrm { { N u m } ( \mathbf { x } _ { i } ) }$ 代表帧内灰度值为 $\mathbf { X } _ { \mathrm { i } }$ 的像素点总数量， $\mathfrak { p } ( \mathbf { x } _ { \mathrm { i } } )$ 为$\mathbf { X } _ { \mathrm { i } }$ 在视频帧中出现的概率。

a)对熵值未发生突变的帧，根据混合高斯模型（GMM）检  
测出帧内运动物体并对其进行腐蚀膨胀处理。b)将帧分成多个扇形区，计算相邻帧 SIFT分布距离（Motion-SIFT）。c)对距离突变的帧，计算运动目标在帧内所占像素百分比  
(Motion-Rate)，判断当前帧是否受到背景运动干扰。d)使用感知哈希算法去除结果集中的冗余帧。

# 2.1混合高斯提取运动目标特征

读入帧序列计算相邻帧熵值比，取熵突变处的帧为部分关键帧。对熵值未突变的帧，进一步计算帧内运动物体的变化程度判断其是否为关键帧，具体处理过程如下：

a)对熵值未发生突变的帧，根据GMM获得视频帧内的前景运动物体，结果如图2(b)所示。

b)为使获得的帧内运动目标轮廓更加清晰，对帧前景内容进行腐蚀膨胀处理。如图2(c)为对图2(b)中的帧进行腐蚀膨胀处理的结果。

c)逐个获得视频中所有熵值未发生突变帧的运动内容，最后得到一组仅包含运动物体的二值化图像。

![](images/de546474f88a2589503e625a6ade27fe966b4c96fb2dc525bf38a68f8529d43e.jpg)  
图1关键帧提取过程

![](images/964bc2b316b5d658f37607d5e7f13cc037b433a6356c5a534739578740eeb398.jpg)  
图2帧内运动物体

提取视频中各帧的前景内容，获得仅包含运动物体的二值化图像，其中白色部分表示视频中的运动物体，黑色区域为帧的背景内容。接着提取帧运动内容的SIFT特征，根据相邻帧SIFT 点分布计算帧间距离。

如图3(a)所示为根据混合高斯检测到的视频帧内的运动物体完成腐蚀膨胀处理后的结果。提取并标记出图3(a)的SIFT点结果如图3(b)所示。由图3(b)中特征点分布可得，SIFT点能够有效标记出帧内运动物体的位置。

![](images/da7280e4808fe5faad1a3e4c6c7a009d0768cf7437e315b2ff515296e4fffd16.jpg)  
图3运动物体 SIFT特征

# 2.2Motion-SIFT 距离计算

计算出帧内运动物体的 SIFT特征点(Motion-SIFT)，根据其在各扇形区的分布情况提取关键帧。计算SIFT分布距离首先需获得帧内运动物体的SIFT特征点，然后把各帧划分成多个扇形区域。接着将SIFT特征点转换到极坐标系下，统计各扇形区的SIFT点个数并计算帧间距离提取关键帧。Motion-SIFT距离计算过程如下：

# 1）帧扇形分区

为统计视频中运动物体的SIFT分布情况，本文算法将视频帧分成多个扇形区。由于运动类视频的主要内容可能出现在帧的任何区域，故根据不同的半径和角度将视频帧分成多个扇形区。

$h$ 为待分区视频帧的高， $w$ 为帧宽。直角坐标系下视频帧中心为 $\cup ( x _ { o } , y _ { 0 } )$ ，其横坐标 $\scriptstyle { x _ { o } = w / 2 }$ ，纵坐标 $\scriptstyle x _ { o } = h / 2$ 。以视频帧中心点为圆点，根据不同半径和角度将帧划分成多个扇形区，结果如图4所示。

![](images/c911db1b8c03dbc98d1a895ae849ee1a88ebe0ab400bc48b7ff54627f5cba0fc.jpg)  
图4帧扇形分区

视频帧扇形分区具体步骤如下：

a）首先获得视频帧的高h和宽w，以视频帧中心O为圆心，分别以 ${ \mathrm { r } } _ { 1 } { = } _ { \mathrm { W } } / 6$ ， ${ \mathrm { r } } _ { 2 } { = } _ { \mathrm { W } } / 3$ ， ${ \mathrm { r } } _ { 3 } { = } _ { \mathrm { W } } / 2$ 为半径作圆，视频帧被三个同心圆分为了3个环形区域。b）根据不同角度对SIFT特征点划分：以45度为单位，使用四条过视频帧中心O点的直线，将帧根据不同的角度划分成8个范围。最终根据角度和距离不同，视频帧被分成24个扇形区。

# 2）坐标系变换

根据上述步骤完成帧分区后，计算帧中各区SIFT特征点的分布数量。统计各区特征点个数并将所有特征点从直角坐标系转换为以原视频帧中心O点为极心的极坐标下。 $\mathrm { ( x _ { i } , y _ { i } ) }$ 表示第i个SIFT特征点的直角坐标，该特征点 $( x _ { i } , \mathrm { y _ { i } } )$ 的极坐标表示形式为 $( r _ { \mathrm { i } } , \theta _ { \mathrm { i } } )$ 。

如式(3)所示,首先计算出坐标为 $( x _ { i } , \mathrm { y _ { i } } )$ 的特征点以帧中心为原点的直角坐标系下的坐标值 $( x _ { i } ^ { \prime } , \mathbf { y } _ { \mathrm { { i } } } ^ { \prime } )$ 。

$$
\left\{ { \begin{array} { l } { x _ { i } ^ { \prime } = x _ { i } - w / 2 } \\ { y _ { i } ^ { \prime } = y _ { i } - h / 2 } \end{array} } \right.
$$

接着将各特征点转换为以视频帧中心点O $( \mathrm { w } / 2 , \mathrm { h } / 2 )$ 为极心的极坐标系下，分别根据式（4）(5)计算出极坐标系下SIFT点$( x _ { i } , \mathrm { y i } )$ 的对应的极坐标 $( \mathrm { r } _ { \mathrm { i } } , \mathrm { \theta } _ { \mathrm { i } } )$ 。

$$
\theta _ { i } = \arctan \left( \frac { ( { y _ { i } } ^ { \prime } { - y _ { o } } ^ { \prime } ) } { ( { x _ { i } } ^ { \prime } { - x _ { o } } ^ { \prime } ) } \right)
$$

$$
r _ { i } = \sqrt { \left( { x _ { i } } ^ { \prime } - { x _ { o } } ^ { \prime } \right) ^ { 2 } + \left( { y _ { i } } ^ { \prime } - { y _ { o } } ^ { \prime } \right) ^ { 2 } }
$$

重复上述步骤获得所有特征点的极坐标，统计特征点在各扇形区内的分布数量，计算帧间距离提取关键帧。

3）Motion-SIFT分布统计

计算SIFT分布距离，首先需统计各区特征点个数并计入Count[i][j]。其中ij分别代表SIFT特征点半径r范围，和角度0范围。当 $\scriptstyle \mathbf { r } = 0$ 时表示该像素点处于最小圆 $\operatorname { \rho ( r _ { 1 } = w / 6 ) }$ 内，当 $\scriptstyle \mathbf { r } = 2$ 时表示该像素点在最大的圆 $( { \bf r } _ { 3 } \mathrm { = w } / 2 )$ 内或该圆之外，当 $\scriptstyle 0 < 0 < \pi / 4$ 时，与该特征点角度对应的数组j值为0。

获得帧内各扇形区SIFT点个数后，接着根据特征点Si极坐标(r.0)确定其所在区域。由式(6)(7)可计算出特征点(r.0)所属的扇形区第 $( \mathrm { i } , \mathrm { j } )$ 区，将此特征点计入Count[i][i]。

$$
i = \frac { r } { \left( w / 6 \right) }
$$

$$
\begin{array} { r } { j = \left\{ \begin{array} { l l } { \displaystyle \theta } & { \quad \boldsymbol { x } ^ { \prime } > 0 ~ y ^ { \prime } > 0 } \\ { \displaystyle ( \pi / 4 ) } & { \quad \boldsymbol { x } ^ { \prime } > 0 ~ y ^ { \prime } > 0 } \\ { \displaystyle \theta + \pi } & { \quad \boldsymbol { x } ^ { \prime } < 0 } \end{array} \right\} } \\ { \left\{ \begin{array} { l l } { \displaystyle \theta + 2 ^ { * } \pi } & { \quad \boldsymbol { x } ^ { \prime } > 0 ~ y ^ { \prime } < 0 } \\ { \displaystyle ( \pi / 4 ) } & { \quad \boldsymbol { x } ^ { \prime } > 0 ~ y ^ { \prime } < 0 } \end{array} \right\} } \end{array}
$$

逐个判断运动物体SIFT特征点所在区域，得到统计扇形特征点个数的二维数组，该数组描述运动目标的特征点分布情况。

# 4）计算帧间距离

根据运动物体提取Motion-SIFT特征点，从而计算其帧间距离。设视频中的连续两帧分别为fk， $\mathbf { f } _ { \mathbf { k } + 1 }$ ，其对应的Motion-SIFT特征点分布数组分别为Countk[i][i]和Count $\mathbf { k } { + } \mathbf { l }$ [i][i]。如式(8)所示，计算两视频帧特征点分布距离（SiftCountDiff）。

$$
S i f t C o u n t D i f f ( f _ { k } , f _ { k + 1 } ) = \sqrt { \sum _ { i = 0 } ^ { 2 } \sum _ { j = 0 } ^ { 7 } ( ( C o u n t _ { k } [ i , j ] - C o u n t _ { k + 1 } [ i , j ] ) ^ { 2 } ) }
$$

由于运动类视频中可能将背景误检为运动目标，从而造成SiftCountDiff差值骤增。采用平均值作为阈值提取关键帧容易造成运动变化较快处的关键帧漏检。因此本文算法使用相邻帧间特征点分布距离的比值来衡量运动特征的变化程度，其计算过程如式(9)所示。

$$
M o t i o n C h a n g e ( k , k + 1 ) = S i f t C o u n t D i f f ( k + 1 ) / S i f t C o u n t D i f f ( k )
$$

视频中相邻两帧的Motion-SIFT分布距离比值记为MotionChange，根据相邻帧比值衡量帧特征距离，判断是否为关键帧。当MotionChange(fk, $\mathbf { f } _ { \mathbf { k } + 1 } .$ )值发生突变时，进一步判断当前帧 $\mathbf { f } _ { \mathbf { k } + 1 }$ 是否受到背景运动干扰。若未受背景干扰则将该帧选为关键帧加入关键帧集合中；否则依次比较其后两相邻帧的特征点分布距离，直到遍历完所有帧。根据Motion-SIFT距离提取关键帧伪代码如下：

方法：帧熵值及Motion-SIFT分布距离提取关键帧

1:Count[i][i] $ 0$ /number of feature points of each sector   
2: for $\mathrm { n { = } 0 {  } i N u m }$ do // number of frames of video   
3: extractMotion-Object of frame by GMM   
4: extract SIFT points of frame   
5: divide frame into sectors   
6: for （204号 $_ { \textrm { k } = 0  }$ SiftNum do   
7: getting r and 0   
8: calculating i and j,Count[i][i] $^ { + + }$   
9: end for   
10: call formula(4-9) calculate SiftCountDiff   
11: call formula(4-10)calculate MotionChange   
12: if MotionChange>α then   
13: ifMotionRate>β then   
14: goto(2)   
15: else   
16: add this frame into keyframe set   
17: end if   
18: end if   
19: end for

# 2.3Motion-Rate 计算

通过混合高斯检测出的视频中的运动物体，其中白色部分为帧内运动目标，黑色为帧背景内容。计算白色像素点在整个帧中的占比(Motion-Rate)，根据该占比判断运动内容的变化情况。当相邻帧间的Motion-Rate值在局部范围发生较大变化时，则判定为有大量背景信息介入。

判断关键帧提取过程中是否受到运动背景干扰，首先需统计出帧内所有白色像素点的个数记为MotionCount。然后计算当前待判断帧与上一个关键帧中运动目标的像素总数比值(MotionChange)。相邻关键帧间运动目标像素总数比值如式(10)所示。

$$
M o t i o n C h a n g e ( i ) = M o t i o n C o u n t ( i ) / M o t i o n C o u n t ( c u r )
$$

运动类视频中，帧内运动物体的变化占整帧内容百分比较小。故本文根据混合高斯检测出的帧中运动目标在视频帧中所占百分比(Motion-Rate)以及待判断关键帧像素总数的变化幅度来判断是否存在背景干扰。运动目标在帧内所占百分比计算如式(11)所示。

$$
M o t i o n R a t e = M o t i o n C o u n t / A l l p i x e l
$$

根据帧运动目标像素占比以及该帧与其前一帧的变化程度即可判断当前帧是否受到运动背景干扰。当存在背景干扰时继续判断下一候选帧是否为关键帧，未受到背景干扰时则将该帧加入关键帧集合。

最后，使用感知哈希算法去除所得关键帧集合中的冗余帧。计算结果集中相邻帧间的汉明距离，当两帧距离小于n时则认为当前存在一帧冗余。

# 3 实验结果与分析

为检测本文算法的有效性，本文在Windows7操作系统下英特尔Corei3，2GB内存的计算机上进行，选择VisualStudio2010及OpenCV3.0作为开发平台实现并测试该算法。实验中

选取了多个运动视频进行测试，其中包括足球比赛、篮球比赛、运动教学、体操、滑冰以及击剑等类型视频。

# 3.1评价标准

查准率（P）和查全率（R）是对结果集的有效评价标准。其中查全率用于衡量关键帧的漏检情况如式(12)所示。查准率反映提取结果的准确性如式(13)所示。

$$
R = \frac { N _ { c } } { N _ { c } + N _ { m } } { \times } 1 0 0 \% 
$$

$$
P = \frac { N _ { c } } { N _ { c } + N _ { f } } { \times } 1 0 0 \%
$$

其中 ${ \mathrm { \cdot N _ { c } } }$ ， $\mathrm { N } _ { \mathrm { m } }$ ， $\mathrm { N _ { f } }$ 分别表示结果中正确提取的关键帧数量，漏检帧个数和误检个数。由于关键帧提取过程中 $\mathtt { R }$ 值和 $\mathrm { ~ \bf ~ P ~ }$ 值难以兼顾，因此为综合度量结果集的有效性，本文使用两者的调和平均值F评价结果集，其定义如式(14)所示。

$$
F = \frac { 2 \times R \times P } { R + P }
$$

# 3.2实验结果

# 3.2.1关键帧提取视觉结果

实验中本文截取了15个运动类视频片段进行测试，并确定各参数取值，对关键帧提取结果进行分析和总结。实验结果显示当汉明距离n为5时，对相似帧判断最准确；MotionChange比值大于3时，能够判定该帧相对于前一帧发生了突变。

为验证本文算法的有效性，将本文算法与基于SIFT分布直方图的关键帧提取算法（SIFT-HD）[6进行比较，其视觉结果如图5\~7所示。

![](images/9bbf43307d8e5de22522496f053a3a4adbd3bd775b0d4c38f493cdf6e4d94524.jpg)  
(a)基于帧SIFT分布直方图关键帧提取结果

![](images/2e5a4bc11c00cf4b2d435783e224c2d2a2980cabebc66446c82867abca0f1c07.jpg)  
图5花样滑冰视频的关键结果集

图5(a)中检测到4个关键帧，图5(b)中检测到8个关键帧，其中图5(a)和图5(b)都存在1帧冗余。根据原视频，运动员完成了多组动作，包括两次分开和三次次共同完成的动作。图 5(a)仅反映出两次共同完成的托举动作，故图5(b)对视频内容表达更加准确。

如图6所示SIFT-HD算法检测到2个关键帧，本文算法检测到8个关键帧帧。原视频中，右方选手攻击两次防守一次，左方选手攻击一次防守两次。如图6(b)所示，本文结果能完整的表达两运动员攻守情况，而图6(a)无法准确地表达原视频内容。

![](images/ddda324f5edd1a61ae61a338fa820346c054e532516302102fd98685d8d0b697.jpg)  
(a)基于帧SIFT分布直方图关键帧提取结果

![](images/fad40a257bbf51d6c6d7339622b01db71ee230a9e30338046001698778779b89.jpg)  
图6击剑关键帧结果

如图7(a)所示，该关键帧结果仅能描述出运动员三步上篮过程，丢失了该运动员尝试投篮被拦下的动作。图7(b)中则可完整描述整个过程。

![](images/7e4adc67dddbe86582946af1ee18fcd3bcb6044d8f54c51914c9dc705e81ff4c.jpg)  
(a)基于帧SIFT分布直方图关键帧提取结果

![](images/78569d2e2d79f3a938e5cab757414043b78b2da10dcc9d5e68418df0439a5a33.jpg)

由图5\~7可得本文算法相较于文献[6]算法对原视频内容的表达能力更强，对原视频内容的表达更加准确。

# 3.2.2实验结果分析和对比

将本文算法分别与基于帧SIFT分布直方图（SIFT-HD）[6]及基于帧 SIFT特征(KS-SIFT)[7的关键帧提取算法进行对比。计算结果的冗余率，漏检率及其调和值。由于运动视频难以人工标定关键帧，故将本文算法和对比算法的结果互为参考标准判断各自漏检帧。本文算法与SIFT-HD算法[关键帧结果的漏检及冗余帧统计结果如表1所示。

表1本文与 SIFT-HD 算法漏检冗余对比  

<html><body><table><tr><td rowspan="2">视频</td><td rowspan="2">总帧</td><td colspan="2">结果帧总数</td><td colspan="2">漏检帧</td><td colspan="2">冗余</td></tr><tr><td>文献[6]</td><td>本文算法</td><td>文献[6]</td><td>本文算法</td><td>文献[6]</td><td>本文算法</td></tr><tr><td>体操</td><td>155</td><td>8</td><td>9</td><td>3</td><td>1</td><td>2</td><td>1</td></tr><tr><td>篮球1</td><td>149</td><td>14</td><td>12</td><td>0</td><td>0</td><td>2</td><td>0</td></tr><tr><td>篮球2</td><td>115</td><td>4</td><td>8</td><td>3</td><td>0</td><td>1</td><td>1</td></tr><tr><td>篮球3</td><td>165</td><td>7</td><td>13</td><td>4</td><td>0</td><td>1</td><td>3</td></tr><tr><td>足球1</td><td>85</td><td>4</td><td>5</td><td>1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>足球2</td><td>82</td><td>19</td><td>16</td><td>1</td><td>0</td><td>7</td><td>3</td></tr><tr><td>足球3</td><td>240</td><td>5</td><td>5</td><td>1</td><td>0</td><td>1</td><td>0</td></tr><tr><td>足球4</td><td>102</td><td>8</td><td>10</td><td>2</td><td>0</td><td>1</td><td>1</td></tr><tr><td>击剑</td><td>125</td><td>2</td><td>10</td><td>6</td><td>0</td><td>0</td><td>2</td></tr></table></body></html>

由表1可知本文算法和SIFT-HD 算法所得的结果中都存在少量冗余，但本文算法的漏检帧少于文献[6]。SIFT-HD 算法检测到的关键帧都包含在本文算法结果中，然而本文算法获得的关键帧结果中存在部分关键帧SIFT-HD算法未能检测到。故本文算法所得结果对原视频的重现程度更好。

将本文算法与基于帧 SIFT 特征的关键帧提取算法(KS-SIFT)[的关键帧结果进行对比。KS-SIFT算法和本文算法所得结果的漏检帧及冗余帧的统计情况如表2所示。

表2与KS-SIFT 算法漏检冗余对比  

<html><body><table><tr><td rowspan="2">视频</td><td rowspan="2">总帧</td><td colspan="2">结果帧</td><td colspan="2">漏检帧</td><td colspan="2">冗余帧</td></tr><tr><td>文献[7]</td><td>本文算法</td><td>文献[7]</td><td>本文算法</td><td>文献[7]</td><td>本文算法</td></tr><tr><td>体操</td><td>155</td><td>7</td><td>9</td><td>3</td><td>1</td><td>1</td><td>1</td></tr><tr><td>篮球1</td><td>149</td><td>8</td><td>12</td><td>4</td><td>0</td><td>0</td><td>0</td></tr><tr><td>篮球2</td><td>115</td><td>5</td><td>8</td><td>2</td><td>0</td><td>0</td><td>1</td></tr><tr><td>足球1</td><td>85</td><td>4</td><td>5</td><td>1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>足球2</td><td>82</td><td>4</td><td>16</td><td>9</td><td>0</td><td>0</td><td>3</td></tr><tr><td>足球3</td><td>240</td><td>4</td><td>5</td><td>1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>足球4</td><td>102</td><td>6</td><td>10</td><td>3</td><td>0</td><td>0</td><td>1</td></tr><tr><td>击剑</td><td>125</td><td>5</td><td>10</td><td>3</td><td>0</td><td>0</td><td>2</td></tr></table></body></html>

由表2可知本文算法和KS-SIFT算法7所得结果中的冗余帧都很少。本文算法的结果中漏检帧极少，而参考文献算法存在较多漏检帧。因此在冗余帧都较少的情况下，本文算法的查全率更高对视频内容的表达更加完整。

对比本文算法与KS-SIFT算法以及 SIFT-HD 算法，计算三种算法关键帧结果的F值，其统计结果如图8所示。

![](images/2b21711cb3e65c5097c46800188035dbd1eee26a8a4c66e5f934a42e1c70ce4f.jpg)  
图7篮球教学片断关键帧结果  
图8三种算法结果集F值对比

由图8可知本文算法的综合表现更优，相对于其他两种算法，本文算法所得结果的F值更加稳定。其中SIFT-HD算法和KS-SIFT算法的F值总体情况不相上下，都存在个别视频的F值低于 $50 \%$ 。基于帧 SIFT-HD关键帧提取算法[和KS-SIFT算法[提取出的关键帧结果集中都存在较多漏检的关键帧，故其F值略低于本文算法。

综上本文算法提取出的关键帧能完整的表达出原视频的主要内容，而基于帧SIFT分布直方图关键帧提取算法所得关键帧集合对视频中部分内容的表达不够完整，会造成部分视频内容丢失。

本文进一步比较了三种算法的运行效率，实验中对上述 8段运动类视频进行测试，帧大小均为 $4 8 0 ^ { * } 2 7 2$ 。三种算法各自的帧处理平均时间如表3所示。

表3算法处理时间比较  

<html><body><table><tr><td>算法</td><td>帧平均时间/s</td></tr><tr><td>KS-SIFT</td><td>0.018</td></tr><tr><td>SIFT-HD</td><td>0.026</td></tr><tr><td>本文算法</td><td>0.035</td></tr></table></body></html>

由表3可知KS-SIFT算法耗时最少，其原因在于KS-SIFT算法选取固定位置的帧为候选帧，再从候选帧中选取关键帧，能够极大地降低所需处理的数据量。然而此方法虽简单快捷，但不够灵活，候选帧的选取往往存在偏差。SIFT-HD算法是根据帧SIFT分布直方图提取关键帧，较KS-SIFT算法肯定更为耗时，但效果一般好于KS-SIFT 算法。相较于SIFT-HD 算法，本文算法首先根据混合高斯建模获得帧内运动物体，然后提取运动物体的SIFT特征点。该方法减少了所需处理的SIFT特征点个数，但是在高斯混合提取运动目标时需要一定耗时，故其执行时间略高于SIFT-HD算法。虽然本文算法耗时略高，但其所得的关键帧结合对原视频的表达更加准确，且耗时在相同数量级，满足工程要求。

# 4 结束语

针对运动类视频，本文提出了一种基于运动目标特征的关键帧提取算法。该算法强调视频中运动物体的变化，弱化视频中运动背景的改变，从而防止由于背景内容过多或过于复杂而造成运动目标特征不明显导致的关键帧漏检。实验结果表明，即使在运动背景较为复杂运动目标占据帧百分比较小时，该算法依然能够较好地检测出运动目标的变化。基于运动目标特征的关键帧算法所得的关键帧结果，对于原始视频内容还原度高，能够完整准确地表达原视频内容。

# 参考文献：

[1]崔智高，王华，李艾华，等．动态背景下基于光流场分析的运动目标检 测算法[J].物理学报,2017,66(8): 97-104.(Cui Zhigao,Wang Hua,Li Aihua,et al.Moving object detection based on optical flow field analysis in dynamic scenes [J].Acta Physica Sinica,2017,66(8): 97-104.)

[2]Shao Ling,Ji Ling.Motion histogram analysis based key frame extraction for human action//activity representation [C]// Proc of Canadian Conference on Computer and Robot Vision. Washington DC: IEEE Computer Society, 2009:88-92.   
[3]Ma Yanzhuo, Chang Yilin, Yuan Hui.Key-frame extraction based on motion acceleration [J]. Optical Engineering,2008,47(9): 957-966.   
[4]Li Congcong,Wu Yita,Yu S S,et al.Motion-focusing key frame extraction and video summarization for lane surveillance system [C]//Proc of IEEE International Conference on Image Processing.2010: 4329-4332.   
[5]Guironnet M,Pellerin D,Guyader N,et al. Video summarization based on camera motion and a subjective evaluation method [J].Eurasip Journal on Image & Video Processing,2007,2007(1): 060245.   
[6]Hannane R,Elboushaki A,Afdel K,et al.An efficient method for video shot boundary detection and keyframe extraction using SIFT-point distribution histogram [J].International Journal of Multimedia Information Retrieval 2016,5 (2): 89-104.   
[7]Barbieri T,Goularte R.KS-SIFT:a keyframe extraction method based on local features [C]// Proc of IEEE International Symposium on Multimedia. 2015: 13-17.   
[8]黄东军，杨颖华．基于改进混合高斯模型的运动物体检测研究[J].计 算机应用研究,2017,34(6):1862-1866.(Huang Dongjun,Yang Yinghua. Modified Gaussian mixture background model for moving object detection [J].Application Research of Computers,2017,34(6):1862-1866.)   
[9]於正强，潘资，宦若虹．一种结合帧差法和混合高斯的运动检测算法 [J]．计算机应用与软件,2015(4):129-132.(Yu Zhengqiang,Pan Yun, Huan Ruohong.A moving detection method combining frame diffrence and gaussian mixture model[J]. Computer Applications and Software,2015 (4): 129-132. )   
[10]李海洋，文永革，何红洲．一种改进的 SIFT特征点检测方法[J].计算 机应用与软件,2013(9):147-150.(LiHaiyang,Wen Yongge,He Hongzhou.

An improved SIFT feature point detection method [J]. Computer Applications and Software,2013 (9): 147-150.)