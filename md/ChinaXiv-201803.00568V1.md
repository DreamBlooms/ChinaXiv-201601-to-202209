# 基于 $L _ { 0 }$ 范数平滑和图像分割的 CT图像阴影校正技术研究

梁晓坤」张志诚」陈思宇」谢耀钦1

1(中国科学院深圳先进技术研究院 生物医学健康与工程研究所深圳518055)

摘要：锥束CT 的图像阴影问题严重影响了其CT 值精度、低对比度目标的检测能力及剂量计算的准确性，限制了锥束CT 在临床上广泛应用。为了消除图像阴影，文章首先对原始CT 图像进行多阈值的图像分割，把骨骼和软组织分离并赋予标准的CT 值得到模版图像；然后，利用 $L _ { 0 }$ 范数平滑算法对原始CT 图像进行边缘保护平滑，得到去除图像纹理信息的平滑图像，之后两幅图像做差后利用低通滤波即可得到图像阴影分布；最后把估计的阴影分布补偿至原始图像，得到阴影校正图像。实验发现校正后的感兴趣区域的 CT 误差由大于115HU下降至小于 $1 3 \mathrm { H U }$ ，整体图像非均匀度由大于 $9 \%$ 下降至小于 $1 \%$ 。实验结果表明，基于 $L _ { 0 }$ 范数平滑和图像分割的 CT 图像阴影校正方法可以有效地校正CT 图像阴影，具有一定的临床应用价值。

# Shading Correction for CT using $\mathbf { { { L } _ { 0 } } }$ Norm Smoothing and Image Segmentation

LIANG Xiaokun1ZHANG Zhicheng1 CHEN Siyu1XIE Yaoqin1 1(Institute of Biomedical and Health Engineering,Shenzhen Institutes of Advanced Technology, Chinese Academy of Sciences, Shenzhen 518055, China)

Abstract：X-rayshdingartifactsadtoCTumberinaccracymagecontrastlossandspatialnon-uniforityandtheforeare consideredasoneof thefundamentallimitatiosofCBCT.Inordertosolvethis problem,anovelshadingcorrectionmethod was proposed.Specifically，we firstusemulti-treshold segmentation algorithmtosegmenttheoriginalCTimageforconstructinga template image where each structure is filled with the same CT number of a specific tissue type.Then,the $L _ { 0 }$ norm smoothing algorithmis used tosmooth the CBCTimage forconstructing animage without texture.Bysubtracting the templatefromthe image withouttexture,theresidual images fromvarious errorsourcesarelow-passfiltered togeneratetheestimatedshadingartifacts.

Finaly,theestimated shadingartifactsareaddedback totheoriginal imageforshadingcorrection.Compared withtheCTmage without correction,the proposed method reduces the overall CT number error from over $1 1 3 \mathrm { H U }$ to be less than $1 3 \mathrm { H U }$ and decreases the non-uniformity from over $9 \%$ to be less than $1 \%$ .The experimental results demonstrate that the proposed shading correction method using $L _ { 0 }$ norm smoothing and image segmentation can effctively correct the shading artifacts and its feasibility in clinical application is validated.

Key words:CT shading artifacts; computed tomography; $L _ { 0 }$ norm; image segmentation

# 1引言

在锥形束CT（Cone-BeamCT，CBCT）扫描中，由于散射信号[和射束硬化效应[2的影响，重建图像中出现低频的CT 图像阴影，这严重影响了图像CT 值的准确性和图像的空间均匀度[3-5]。在无阴影校正的 CBCT 系统中，CT 图像阴影导致重建图像的CT 值误差可超过 $3 5 0 \mathrm { \ H U ^ { [ 4 ] } }$ ，给影像引导治疗的定位精度和影像的诊断带来误差，因而限制了CBCT 在临床中的广泛应用。目前CBCT 主要还是用于初步定位和放疗摆位，在介入和放疗中的进一步应用受到限制，因此CT 图像阴影校正是提升CBCT 图像质量首要解决的重要问题之一。

目前已知的CT 图像阴影校正的方法主要分为两大类：预处理和后处理方法。其中，预处理方法校正 CT 图像阴影主要是通过附加硬件装置，以阻止散射光子到达探测器，这样也就不存在散射信号。预处理进行阴影校正有两个典型方法：一是增加物体与探测器之间的空气隙[7，二是使用抗散射线栅[8]。随着空气隙加宽，扩散开的散射光子的探测率会降低，而源信号则不受影响。但该方法受CBCT 设备本身物理空间的限制，空间距离不能无限增大，而且增大的同时加大了影像的几何模糊，同时还需要增加X 线剂量来弥补距离的增加，在临床实际中并不实用。抗散射线栅使用聚焦于射线源的铅栅网格，能阻挡非聚焦入射角的散射光。该方法也存在对散射光的衰减效率不高的缺陷。目前商用铅栅只能提供约3倍的散透比（Scatter-to-Primary Ratio，SPR）降低率，无法保证高散射环境下的CBCT 图像质量。此外，它还需要增加病人的受照剂量来补偿被衰减掉的源射线强度，临床应用价值不高。

虽然预处理方法能直接阻止散射光子到达探测器，但其局限性比较突出，相比而言，后处理方法更实用。后处理指的是按照原来的方法采集X射线投影后，再通过后处理估计散射分布，通过源投影减去估计出的散射分布，即可对其进行阴影校正。后处理方法包括：解析建模法[9]、蒙特卡罗模拟法[10,]、源调制法[9,12]、测量法、基于先验数据校正法、基于极坐标的校正法和自适应迭代阴影校正法。其中，解析建模法认为散射信号是源信号通过散射核后的响应，计算速度很快，但相应的散射估计精度有限且对复杂物体需要繁琐的调整参数；蒙特卡罗模拟法[10.1]是散射估计的“金标准”，但该方法计算量极大，十分耗时;源调制法[12l是在 X 射线源和物体之间加入高频调制器，根据散射和源信号不同的响应特性，在频域上把它们分离开，但该方法对调制板的制造精度要求高，其临床应用效果受到实际物理因素的限制；测量法是在 X 射线源和受照物之间插入源射线阻挡器(通常是铅条)[13-17]，这样探测器上形成仅包含散射信号的阴影区，但该方法要改变系统的硬件设置，操作难度较大；基于先验数据校正法虽能较好地得到校正图像[18],但该方法需要借助放射治疗中额外的先验病患信息，因此无法作为大体积CT 成像系统阴影校正的通用解决方案；基于极坐标的校正法通过CT 图像阴影在极坐标下的分布特征[19]，估计出CT 图像阴影分布，但该方法需要对图像进行极坐标转化和插值操作，耗时长；自适应迭代阴影校正法无需先验图像信息[20]，但该方法需要对重建图像进行反复正投影操作，计算效率低。

本研究利用 $L _ { 0 }$ 范数平滑和图像分割相结合的方法，提出一种新的CT 图像阴影校正方法。该方法不依赖其他影像数据，完全兼容现代放疗加速器的图像引导系统，不用改变其他硬件和扫描协议，无需进行坐标变换和正投影，不增加扫描时间和扫描剂量。通过 $L _ { 0 }$ 范数平滑分离图像纹理并保护图像细节信息，利用图像分割建立模版图像，估计出CT 图像阴影的分布，最终达到CT 图像阴影校正的目的。

# 2方法

# 2.1CT图像阴影校正方法的流程

图1 显示的是CT 图像阴影校正方法的工作流程图。CT 图像阴影信号属于低频信号，CT 图像的细节信息同样属于低频信号。为了保护图像细节信息以及更精确的估计CT 图像阴影的分布，本研究首先利用 $L _ { 0 }$ 范数平滑，在对图像进行边缘保护的同时把图像纹理从原始图像中去除。解剖学常识指出，人体同种类型的组织的CT 值大小基本一致。根据这一特点，通过图像分割的方法构建模版图像，模版图像可以作为校正的参考图像。参考图像所含结构与无纹理的平滑图像做差的残留图像存在CT 图像阴影和少量的结构误差。因为结构误差属于高频信号，而 CT 图像阴影属于低频信号，因此可通过低通滤波把少量的结构误差去除，从而得到低频的CT 图像阴影分布。下面将对工作流程中的关键步骤进行介绍，包括： $L _ { 0 }$ 范数平滑、模版图像的生成以及低通滤波。

![](images/e44b1b9400daf0cd2dcb26cb1e57516b5bedeed0331ff4e01def519b730c075c.jpg)  
图1图像阴影校正方法的工作流程图  
Fig.1Workflow of the proposed method of CT shading correction

# 2.2 $L _ { 0 }$ 范数平滑

在图像阴影校正过程中，为了保护图像细节，不损失图像空间分辨率，本研究把CT 图像分解为纹理和结构。相对于CT 图像阴影信号而言，图像的纹理属于高频信号。为了更精确地提取散射信号，本研究首先对原始重建图像进行边缘保护的 $L _ { 0 }$ 范数平滑。具有边缘保护的 $L _ { 0 }$ 范数平滑算法过程如下：设 $I$ 为输入的原始CT 重建图像， $s$ 为输出无纹理的平滑图像， ${ \boldsymbol { \nabla } } S _ { p } { = } ( \partial _ { x } \mathbf { S } _ { p } , \partial _ { y } \mathbf { S } _ { p } ) ^ { T }$ 为图像的梯度（ $p$ 为图像的像素索引， $x$ 和 $y$ 分别为图像的横纵两个方向的坐标)。对于一个像素索引 $p$ ，计算其在 $x$ 和 $y$ 两个方向的梯度差之和作为它的梯度值，如公式（1）[21]所示：

$$
C ( S ) { = } { \# } \big \{ p \big | \big | \partial _ { x } \mathbf { S } _ { p } \big | { + } \big | \partial _ { y } \mathbf { S } _ { p } \big | { \neq } 0 \big \}
$$

其中， $C ( S )$ 为 $\big | \hat { o } _ { x } \mathbf { S } _ { p } \big | { + } \big | \hat { o } _ { y } \mathbf { S } _ { p } \big | { \neq } 0$ 像素索引 $p$ 的个数。根据上面的定义，无纹理的平滑图像S可以通过以下目标函数求得[21]，见公式（2)：

$$
\operatorname* { m i n } _ { S } \left\{ \sum _ { p } \left( S _ { p } - I _ { p } \right) ^ { 2 } + \lambda \cdot C \left( S \right) \right\}
$$

其中， $\sum ( S - I ) ^ { 2 }$ 为图像结构相似性约束项。因 $L _ { 0 }$ 范数的不可解性，所以本文将算法分为两个子问题进行分别求解，采用半二次分裂的特殊交替优化策略得到近似的最优解。

# 2.3模版图像的生成

根据解剖常识，同种类型的人体组织在没有伪影的 CBCT 图像中的CT 值应该基本一致[20]。由此，可以利用图像分割的方法，把人体不同的组织分割出来。CT 图像中的结构成分可分为空气、骨头、软组织（如肌肉和脂肪）区域等，对应的组织区域填充相应组织在对应X 射线球管电压下的标准CT 值，生成一幅模版图像，该图像作为阴影校正过程的参考标准。本研究采用多阈值的图像分割算法，分离病人头部的骨骼和软组织并赋予标准的CT 值。

# 2.4低通滤波

上述生成的模板图像与无纹理的平滑图像之差包含图像阴影和少量组织结构误差。阴影伪影主要为低频信号，而组织结构则主要是高频信号，可利用低通滤波器消除组织结构误差。普通的低通滤波可以消除组织结构的误差，但解剖结构的边界轮廓也会被滤除，导致图像对比度的严重丢失。因此，本研究采用Savitzky-Golay 局部低通滤波器[22]在图像域上对残差图像进行滤波，该低通滤波器可以保持轮廓特征，避免了校正后损失图像的对比度分辨率。

# 2.5 实验评估

通过 Varian Trilogy 机载 CBCT 系统采集实验所需投影，在均匀模体上进行 CT 图像阴影校正，再对病人头部重建图像进行CT 图像阴影校正，最后，把扇束CT 和计划CT 扫描图像作为均匀模体和病人头部CT 图像阴影校正效果的金标准与校正后的图像进行对比分析。对于扇束CT，本研究把射线源前放的准直器宽度缩小为 $4 \mathrm { m m }$ ，采集均匀模体，得到一组近似无CT 图像阴影的扇束CT 图像，即可利用扇束 CT 图像与校正后的图像作对比。此外，实验采集的Capthan 504 模体数据用于算法参数设置分析。实验采集的三组数据扫描与图像重建参数如表1所示。图像处理的硬件配置如下：Corei7-6820HK E72002.70 GHz CPU、 $3 2 \mathrm { G }$ 内存的微星笔记本电脑，编程环境采用 Matlab R2016a。

# 表1瓦里安Trilogy机载CBCT系统扫描与图像重建参数

Table 1Imaging and reconstruction parameters of the Varian Trilogy OBI system   

<html><body><table><tr><td>参数</td><td>均匀模体</td><td>Catphan 504</td><td>病人头部</td></tr><tr><td>扫描模式</td><td>full-fan</td><td>full-fan</td><td>full-fan</td></tr><tr><td>X 射线能量（kVp)</td><td>125</td><td>125</td><td>100</td></tr><tr><td>管电流（mA）</td><td>80</td><td>80</td><td>80</td></tr><tr><td>X 射线焦斑尺寸（mm）</td><td>0.4</td><td>0.4</td><td>0.4</td></tr><tr><td>脉冲宽度（ms)</td><td>25</td><td>25</td><td>13</td></tr><tr><td>源至探测器距离 （mm）</td><td>1 501.42</td><td>1 501.42</td><td>1 501.42</td></tr><tr><td>源至等中心距离（mm)</td><td>1000</td><td>1000</td><td>1000</td></tr><tr><td>探测器尺寸</td><td>400*300mm²</td><td>400*300mm²</td><td>400*300mm²</td></tr><tr><td>探测器像素</td><td>1024*768</td><td>1024*768</td><td>1024*768</td></tr><tr><td>旋转角度（°）</td><td>360</td><td>360</td><td>360</td></tr><tr><td>投影数量</td><td>663</td><td>662</td><td>367</td></tr><tr><td>重建体素大小（mm Xmm× mm)</td><td>0.5 × 0.5 × 0.5</td><td>0.5 × 0.5 × 0.5</td><td>0.5 X 0.5 × 0.5</td></tr><tr><td>重建体积大小（体素)</td><td>512×512×512</td><td>512×512×512</td><td>512×512×512</td></tr><tr><td>算法</td><td>FDK</td><td>FDK</td><td>FDK</td></tr></table></body></html>

在图像的定量分析中，采用CT 值误差与整体图像非均匀度评价校正前后图像质量。整体图像非均匀度（Spatial Non-Uniformity，SNU）的计算公式[17]如公式（3）所示。

$$
S N U { = } \frac { \overline { { H U } } _ { \mathrm { m a x } } - \overline { { H U } } _ { \mathrm { m i n } } } { 1 0 0 0 } { \times } 1 0 0 \%
$$

在图像同一组织区域选择 5个半径大小为5 个像素的感兴趣区域（Region of Interest，ROI)。其中，4 个ROI选在重建物体的边缘，1个ROI 选在重建物体的中心。式（3）中 $\overline { { H U } } _ { \mathrm { m a x } }$ 和 $\overline { { H U } } _ { \mathrm { m i n } }$ 分别为5个ROI中平均CT 值的最大值和最小值。

# 3结果

# 3.1 均匀模体

图2 为均匀模体中心层的横断图像，图3为阴影校正前后在图2（c）中白色虚线位置上CT 值的对比图。从图2 和图3可看出，图像阴影明显地被抑制，抑制后的图像效果图2（b）接近于扇束CT 重建的图像。图2（a）中 5个白色虚线圆圈为计算整体图像 SNU的 ROI，校正后图像的整体 SNU 由 $9 \%$ 降至 $0 . 4 \%$ ；图2（c）白色虚线圈ROI的CT值误差从 $7 7 \mathrm { H U }$ 降至 $2 { \mathrm { H U } }$ 。此外，图2中3个图像的ROI（白色虚线圆圈内）的CT平均值分别为：(a)一139HU；（ $_ { \mathrm { 2 } } ) { - } 6 0 \ : \mathrm { H U }$ ；（ $\mathrm { \Phi _ { c } } ) - 6 2 \mathrm { \ : H U }$ 。图3表明校正后的 CT 值强度与扇束CT 值强度基本吻合。

![](images/904017b4d15b542845aab5e0053f6bb38b055ef886ee8ad73d5a57f5fcd5f0b3.jpg)  
图2均匀模体重建的横断面图像（显示窗口为：[一150450]HU)  
图3CT 图像阴影校正前后通过图2(c)白色虚线所在位置的CT 值对比图 Fig. 3Comparison of 1D profiles passing through the dotted white line as indicated in figure 2(c)

Fig.2Axial views of the reconstructed uniform acrylic cylindrical phantom (Display window: $[ - 1 5 0 4 5 0 ] \mathrm { H U } )$

=II0 = 11I At-50 MM  
(nH)  
-100 0程MW M 出-150参考扇束CT图像EEEE 未校正的CT图像-200 校正后的CT图像0 50 100 150 200 250 300像素

# 3.2 病人头部

图4 显示的是病人头部的横断图像，图5（a）和（b）分别显示阴影校正前后在图4（c）和（f）中白色虚线位置上CT 值的对比图。从图4 和图5可看出，图像阴影明显地被抑制，抑制后的图像效果图4 第二列接近于配准后的计划CT 重建图像。图4（a）中5个白色虚线圆圈为计算整体图像（图 $4 ( \mathrm { a } ) \sim$

图 4(c)）SNU 的 ROI，校正后图像的整体 SNU 由 $14 \%$ 降至 $1 \%$ ，图4（b）白色虚线圈ROI的CT值误差从 $2 0 0 \mathrm { H U }$ 降至 $1 3 \mathrm { H U }$ 。此外，整体图像中的 3个图像的 CT 值平均值分别为：(a) $- 2 7 \mathrm { H U }$ ； (b)$1 7 3 \mathrm { H U }$ ；(c) $1 6 0 \mathrm { H U }$ 。图 5 显示校正后的CT 值强度接近于配准后的计划CT 值强度。

![](images/bc13f06347d047290a0cbb078021eb444874d07b259a75c1c833a785afc51093.jpg)

![](images/de447616512039347ef3adca8b48ef829b95ebd50e1fe759d7331cd1d2a62a35.jpg)  
（a）校正前（中心层面）图像；（b）校正后（中心层面）图像；（c）配准后的参考计划CT（中心层面）图像；（d）校正前（非中心层面）图像；（e）校正后（非中心层面）图像；（f）配准后的参考计划CT（非中心层面）图像图4病人头部横断面CT重建图像(显示窗口为：[一200 500]HU)  
Fig.4Axial views of the reconstructed patient head (Display window:[一2Oo 500] HU)   
图5对比图4两条虚线所在位置的一维轮廓像素值

Fig.5Comparison of 1D profiles passing through the two dotted white lines as indicated in figure 4

# 4讨论

$L _ { 0 }$ 范数平滑的参数选择影响图像纹理去除程度与组织结构边缘保护的效果，纹理去除和边缘保护是一对矛盾。充分的图像纹理去除，有助于校正后图像的细节保留，不破坏图像分辨率。良好的边缘保护，有助于估计图像阴影的准确性，提高校正后图像组织间的对比度。因此，在 $L _ { 0 }$ 范数平滑过程中，平滑强度因子λ的选择应在两者间取得平衡。不同λ选择对图像造成的影响如图6所示。其中，图6（a) ${ \sim } 6$ （c）分别为3个不同 $\lambda$ 下的 $L _ { 0 }$ 范数平滑图像，图6（d) ${ \sim } 6$ （f）为在相应 $\lambda$ 下的校正图像。当λ取得过小时，如图6（a）和6（d)，纹理去除不充分导致估计出的阴影信号中包含图像细节，阴影信号补偿至原始图像得到的校正图像损失图像细节。当 $\lambda$ 取得过大时，如图6（c）和6（f)，因平滑程度过强导致组织结构边缘模糊，估计出的阴影信息中包含结构信息，因此校正后图像组织结构之间对比度降低。当取0.01时，在纹理去除和边缘保护之间取得了平衡，在保护图像细节的同时，不降低组织间对比度。

![](images/fb43fe13dedc19d669ffa093de314c4b0551dc32823c7e74d58e4fa9aa993acf.jpg)  
（a）平滑图像（ $\lambda { = } 0 . 0 0 1 \mathrm { ; }$ ；（b）平滑图像（ $\lambda = 0 . 0 1$ )；（c）平滑图像（ $\lambda = 0 . 0 4 \$ )；（d）校正后图像（ $\lambda { = } 0 . 0 0 1$ )；(e）校正后图像（ $\lambda = 0 . 0 1$ )；（f）校正后图像（ $\lambda = 0 . 0 4$ ）  
图6不同平滑强度因子 $\lambda$ 下的平滑和校正图像 （显示窗口为：[一200 500]HU)

Fig. 6Effect of the strength of smoothing $\lambda$ in the smoothing images and corrected images (Display window:[-2Oo 500]

HU)

精确模版图像的生成依赖于图像分割的精度。本文采用基于多阈值Otsu 准则的阈值分割方法，阈值由最大类间准则确定。在分割步骤中，需要假设图像中存在 $n$ 个待区分的类， $n$ 的取值影像图像阴影修正效果。在病人头部的阴影校正中， $n$ 取3能准确分割骨骼、软组织和空气，获得精确的模版图像。当 $n$ 过小时，无法区分灰度值相近的不同组织，导致阴影修正后图像的组织间对比度下降。当 $n$ 过大时，则导致同一组织内阴影校正不全，残留阴影。

本研究提出了一种结合 $L _ { 0 }$ 范数平滑与图像分割相结合的CT 图像阴影校正方法，有效地消除了图像阴影。与类似研究相比，如 Niu 等[18引入诊断CT 数据，把诊断CT 作为参考图像对 CBCT 进行阴影校正，模体感兴趣区域的CT 值误差降至17HU。但该方法对诊断CT 数据的依赖很强，专用于放疗中的影像引导，并且由于诊断CT 与锥束CT 是在治疗的不同阶段扫描得到，所以需要对二者进行图像配准，对配准精度要求高。而在本研究中，模体感兴趣区域的CT 值误差降至4HU，主要原因在于无需配准，避免了配准误差所带来的阴影估计误差。在Fan等[19的研究当中，首先把原始CBCT 图像由笛卡尔坐标系转为极坐标系，之后在极坐标图像上进行滤波，估计出图像阴影，最后把估计的图像阴影转化为笛卡尔坐标补偿至原始CBCT 图像中。在校正后的病人头部图像中，同一组织的图像 SNU 下降至 $3 \%$ ，但是该方法对于组织结构复杂以及带环形的物体效果不好。图8为上述算法和本文提出算法的 Catphan 504 模体处理结果对比图。在极坐标系下处理上述图像会引入新的伪影（如图8（c）红色箭头所指)，导致图像对比度的损失。本算法处理的效果如图8（b）所示，保持了图像的对比度，主要原因在于引入图像分割产生了精确的模版图像，模版图像的同一组织的图像 SNU为0，再利用 $L _ { 0 }$ 范数平滑保留图像细节，较好地保护了图像对比度。

![](images/61196a3f54968128ee8d446bac64735d816bf3fb99b95f2e97d5b09269b6df8c.jpg)  
图8不同阴影校正算法的效果对比图 (显示窗口为：[一30450]HU)  
Fig.8The results of the shading corrected CBCTusing diffrent algorithm (Display window:[一30 450] HU)

本方法利用边缘保护的 $L _ { 0 }$ 范数平滑算法，把图像分解为结构图像和纹理图像，把纹理信息消除后再做后续处理，不损失图像分辨率。精确的图像分割算法成功地将人体组织进行分割，生成精确的参考图像。因此，可作为CBCT 图像阴影校正的通用方法。基于 $L _ { 0 }$ 范数平滑和图像分割的CT 图像阴影校正技术除了图像阴影校正效果明显外，还具有以下优点：（1）通过 $L _ { 0 }$ 范数平滑最大限度地保护了图像的细节信息，图像空间分辨率损失小；（2）本研究无需先验的CT 信息，无需前投影操作，无需极坐标转换，因此计算速度较快；（3）完全兼容现代放疗加速器的图像引导CBCT 系统，不用改变其他硬件和扫描协议。在未来，本方法还需在以下两方面进行改进。第一，精确模版图像的生成依赖图像分割的精度，分割精度更高的算法有助于图像阴影的校正。多阈值图像分割算法成功地分割出了头部骨骼、软组织和空气，但难以分割出脂肪，导致校正后图像的脂肪和其他软组织的图像对比度下降。因此，在之后的工作将进一步提升图像分割的精度以提高组织对比度。第二，本文利用 matlab 平台实现图像阴影校正算法，按表1的参数校正一层 CBCT 图像需 2.1 秒，其中 $L _ { 0 }$ 范数平滑步骤占用1.5 秒。 $L _ { 0 }$ 范数的不可解性导致 $L _ { 0 }$ 范数平滑步骤耗时，半二次分裂的特殊交替优化策略增加了算法的时间复杂度，算法速度仍有待提高。

# 5结论

本研究提出了 $L _ { 0 }$ 范数平滑与图像分割相结合的CT 图像阴影校正方法，该方法有效地改善了CBCT的图像质量。在均匀模体实验中，校正后图像 ROI 的 CT 值误差由 77HU 降至 $2 \mathrm { H U }$ 。整体图像的 SNU由 $9 \%$ 降至 $0 . 4 \%$ 。在病人头部试验中，校正后图像ROI的CT值误差由 $2 0 0 \mathrm { H U }$ 降至 $1 3 \mathrm { H U }$ 。整体图像的非 SNU 由 $14 \%$ 降至 $1 \%$ 。与现有的阴影校正方法不一样，本方法无需先验信息，完全兼容现代放疗加速器的图像引导系统，不用改变其他硬件和扫描协议，不增加扫描时间和扫描剂量，具有一定的临床应用价值。

# 6致谢

本文感谢来自浙江大学附属邵逸夫医院的牛田野研究员和周勤瑄先生对本文的帮助。

# 参考文献

[1]Siewerdsen JH,Daly MJ,Bakhtiar B et al.A simple，direct method for X-ray scater estimation and correction in digital radiography and cone-beam CT[J]. Medical Physics,20O6,33(1): 187-197.   
[2]Hsieh J,Molthen RC,Dawson CA,et al. An iterative approach to the beam hardening correction in cone beam CT [J]. Medical Physics,2000, 27(1): 23-29.   
[3]Virshup G, SuriR,Star-LackJ.TH-E-330A-06: Scatter characterization in cone-beam CT systems with offset flat panel imagers [J]. Medical Physics, 2006, 33(6): 2288-2288.   
[4]Zhu L,Xie Y,Wang J，et al. Scater correction for cone-beam CT in radiation therapy[J]. Medical Physics, 2009,36(6): 2258-2268.   
[5]Tanaka T,Arai Y,Inaba Y, et al. Current role of hybrid CT/angiography system compared with C-arm cone beam CT for interventional oncology [J].The British Journal of Radiology,2014,87(1041): 20140126.   
[6]Niu T, Zhu L. Overview of X-ray scater in cone-beam computed tomography and its correction methods [J]. Current Medical Imaging Reviews, 2010, 6(2): 82-89.   
[7]Neitzel U. Grids or air gaps for scater reduction in digital radiography: a model calculation [J]. Medical Physics,1992,19(2): 475-481.   
[8]Wiegert J,Bertram M,Schaefer D,et al.Performance of standard fluoroscopy anti-scater grids in flat detector based cone beam CT[C] // Proceedings of SPIE 5368,Medical Imaging 2004: Physics of Medical Imaging, 2004: 67-78.   
[9]Sun M,Star-Lack JM. Improved scatter correction using adaptive scater kernel superposition [J]. Physics in Medicine and Biology, 2010, 55(22): 6695-6720.   
[10] ColijnAP,Beekman FJ.Accelerated simulation of cone beam X-ray scater projections [J]. IEEE Transactions on Medical Imaging,2004, 23(5): 584-590.   
[11] Kyriakou Y,RiedelT,KalenderWA.Combining deterministic and Monte Carlo calculationsforfast estimation of scatter intensities in CT[J].Physics in Medicine and Biology,2006,51(18): 4567-4586.   
[12] Gao H,Fahrig R,BennettNR,et al. Scater correction method for X-ray CT using primary modulation: Phantom studies [J]. Medical Physics,2010,37(2): 934-946.   
[13] Maltz JS,Gangadharan B,Vidal M,et al. Focused beam-stop arry for the measurement of scatter in megavoltage portal and cone beam CT imaging [J]. Medical Physics, 2008, 35(6): 2452-2462.   
[14] Liang X,Gong S, Zhou Q, et al. SU-F-J-211: Scater corrction for clinical cone-beam CT system using an optimized stationary beam blocker with a single scan [J]. Medical Physics, 2016, 43(6): 3457.   
[15]梁晓坤，牛田野，周勤煊，等．直线加速器机载锥形束 CT 图像散射的修正方法 [J]．中国医学影像技 术,2016,32(4): 619-622.   
[16] Zhu L, Bennet NR,Fahrig R. Scatter correction method for X-ray CT using primary modulation: theory and preliminary results [J]. IEEE Transactions on Medical Imaging, 2006,25(12): 1573-1587.   
[17] Niu T,Zhu L. Scatter correction for ful-fan volumetric CT using a stationary beam blocker in a single full scan [J]. Medical Physics,2011, 38(11): 6027-6038.   
[18] Niu T, Sun M, Star-Lack J, et al. Shading correction for on-board cone-beam CT in radiation therapy using planning MDCT images [J]. Medical Physics, 2010, 37(10): 5395-5406.   
[19]Fan Q,LuB,Park JC,et al. Image-domain shading corrction for cone-beam CT without prior patient information [J]. Journal of Applied Clinical Medical Physics, 2015,16(6): 65-75.   
[20] Wu P,Sun X,Hu H,etal. Iterative CT shading corection with no prior information [J]. Physics in Medicine and Biol0gy, 2015, 60(21): 8437-8455.   
[21]Xu L, Lu CW, Xu Y, et al. Image smoothing via $L _ { 0 }$ gradient minimization [J]. ACM Transactions on Graphics, 2011, 30(6): 61-64.   
[22] Savitzky A, Golay MJE.Smoothing and diffrentiation of data by simplified least squares procedures [J]. Analytical Chemistry, 1964, 36(8): 1627-1639.