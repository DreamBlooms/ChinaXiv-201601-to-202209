# 基于PST和多尺度高斯滤波的视网膜血管的分割

蔡震震'，唐鹏1，胡建斌1²，金炜东1(1．西南交通大学 电气工程学院，成都 610031;2．爱尔眼科医院，成都 610051)

摘要：视网膜血管分割是眼科计算机辅助诊断和大规模眼科疾病筛查系统的基础。为辅助眼科医生进行眼底疾病的诊断，提出了一种基于相位拉伸变换(PST)和多尺度高斯滤波的视网膜血管分割方法。首先将彩色眼底影像的绿色通道分量图进行增强预处理；然后采用不同尺度的高斯滤波器对预处理增强后的视网膜血管进行降噪处理，再结合PST边缘检测算法初步获得视网膜血管分割图；最后整合初步获得的视网膜血管分割图并进行形态学去噪，获得最终的视网膜血管分割图。通过在视网膜图像库DRIVE上进行实验，其平均准确率为 $93 \%$ ，平均灵敏度达 $7 7 \%$ ，平均特异性为$9 5 \%$ ，实验结果验证了该方法的有效性。

关键词：视网膜血管；相位拉伸变换；多尺度；血管分割中图分类号：TP181 doi:xxxxxx

# Retinal vessel segmentation based on PST and multi-scale Gaussian filter

Cai Zhenzhen1,Tang Pengl,Hu Jianbin1,²,Jin Weidongl (1.SchooloflecticalEngineeing,SouthwestJaotong UnversityChengdu 6o1,China;2.AierEyeHospital,Cengdu 610051, China)

Abstract: Retinal vessel segmentation is thebasis ofophthalmiccomputer-aided diagnosisandlarge-scaleophthalmic disease screeningsystems.Inordertoasistophthalmologistsinthediagnosisoffundus diseases,thispaperpresentedaretinalvessel segmentationmethodbasedonPSTandmulti-scale Gausiafilter.Firstly,itenhancedthegrenchannelofcolorfundusimage; then,itused Gausian filters with diferent scales toreduce thenoiseof retinal vessels with different diameters after preconditioning,andcombinedwiththeGausianfilters,itusedtheedgedetectionalgorithmofthePST(phasestretchtrasform) to obtain preliminaryretinal vascularsgmentationmap;finally,itintegratedtheinitialretinal vesselsegmentationmapsand denoised theresult based on morphologytoobtain th finalretinal vesel segmentationmap.The experiments onDRIVEretinal image database show that the average accuracy is $93 \%$ ,the average sensitivity is $7 7 \%$ ,and the average specificity is $9 5 \%$ . The experimental results verify the effectiveness of the method proposed.

Key words:retinal vessel; PST; multi-scale; segmentation of blood vessels

# 0 引言

眼底视网膜血管网络是人体血液循环系统中唯一可以无创直接观察到的血液微循环，其形态和特征的变化（如血管弯曲度、新生血管等）可以作为很多疾病的诊断依据，如糖尿病性视网膜病变、青光眼等，该类疾病在世界范围内有较高的发病率，且早期大多无临床征兆，早期筛查诊断十分重要[1]。眼底视网膜血管自动分割是眼科计算机辅助诊断和大规模疾病筛查系统的基础[2]，对于实现相关疾病的大规模自动筛查和辅助诊断具有重要意义。

目前,视网膜血管分割的方法大致可以分为基于血管跟踪的方法、基于匹配滤波的方法和基于机器学习的方法三类。基于血管跟踪的方法是在血管具有连续结构的基础上，设置好初始种子节点，沿血管方向跟踪，直到满足结束条件为止。Nayebifar等人[3]采用了基于粒子滤波的视网膜血管跟踪方法，从视盘边界选择一些点作为初始种子点进一步跟踪血管。Zhang 等人[4结合贝叶斯理论和多尺度检测的实现视网膜血管的跟踪，该类方法可以得到血管的局部信息，但是在血管跟踪时容易被血管分支或交叉点影响而无法继续跟踪。基于匹配滤波的方法是利用视网膜血管剖面的灰度分布特性，通过计算对图像滤波后的响应值来寻找血管点。Li等人[5提出了多尺度匹配滤波方法，在图像预处理阶段利用多尺度匹配滤波的结果叠加来进行图像增强，最后利用双阈值实现视网膜血管分割。曹新容等人[6首先利用匹配滤波消除噪声影响后再估计眼底影像中的背景像素所占比例，最后利用直方图自动选择阈值完成视网膜血管分割。该类方法的算法复杂度一般较低，血管分割速度较快。基于机器学习的方法是通过提取视网膜血管的一系列特征训练分类模型，对眼底影像中的像素进行逐一识别。Lupascu等人[7提出了一种基于特征的AdaBoost分类器的自动视网膜血管分割方法。Slazar-Gonzalez等人[8]采用矢量流的分割方法来进行视网膜血管分割。朱成璋等人[9首先为彩色眼底影像中的每个像素点提取一个23维的特征向量，然后采用随机森林的方法训练出视网膜血管分类器。该类方法可以实现较好的分割结果，但是分割过程中需要对眼底影像中的像素逐一识别，耗时较长。

目前视网膜血管分割研究的难点主要在于两个方面：一方面，在正常眼底影像中，视网膜血管末端细小血管的分割问题、视网膜血管分割过程中血管断裂问题以及视盘处血管分割的问题；另一方面，在病变的眼底影像中，硬性渗出、新生血管、微动脉瘤等病灶的影响使视网膜血管分割难度增加。

匹配滤波的方法在视网膜血管分割中具有简单快速的优势，现有的匹配滤波的方法多数是在时域中将血管进行增强后实现视网膜血管的分割。针对视网膜血管分割的研究，本文提出了一种结合PST（phase stretchtransform）和多尺度高斯滤波的视网膜血管分割的方法，该方法分割耗时短并且在血管漏分割问题上有一定的提高。

# 1 PST理论

相位拉伸变换(phase stretchtransform,PST)是由加州大学电气工程教授Jalali和光电学院院长兼高级研究员Asghari[lo]领导的小组开发提出来的。该算法受物理学启发模拟了电磁波在具有扭曲色散性质的衍射介质中的传播方式，将图像中具有不同特性的像素点区分开。在频域中变换的相位有助于检测图像中的边缘以及像素灰度值变化较快的位置，图像的边缘信息包含较高的频率特征，PST通过强调更高的频率特征来获取图像中的边缘信息，实现对图像中边缘信息的增强。具体如式（1）所示。

$$
\begin{array} { r } { A [ n , m ] = \angle \big \langle I F F T 2 \{ \tilde { K } [ p , q ] \cdot F F T 2 \{ B [ n , m ] \} \} \big \rangle } \end{array}
$$

其中： $\textrm { m , n }$ 为二维时域变量； $\mathbf { B } [ \mathbf { n } , \mathbf { m } ]$ 为输入图像； $\mathbf { A } [ \mathbf { n } , \mathbf { m } ]$ 是输出图像； $\angle \langle \cdot \rangle$ 是角度算子；FFT2{}和 IFFT2{}分别为傅里叶变换和傅里叶逆变换； $\mathfrak { p . q }$ 为二维频域变量； $\tilde { K } [ p , q ]$ 是非线性频率相关描述，如式(2)所示。

$$
\tilde { K } [ p , q ] = e ^ { j \cdot \varphi [ p , q ] }
$$

$$
\varphi [ p , q ] = \varphi _ { p o l a r } [ r , \theta ] =
$$

其中：

$$
S \cdot \frac { W \cdot r \cdot t a n ^ { - 1 } ( W \cdot r ) - ( 1 / 2 ) \cdot \ln \left( 1 + \left( W \cdot r \right) ^ { 2 } \right) } { W \cdot r _ { m } \cdot t a n ^ { - 1 } \left( W \cdot r _ { m } \right) - \left( 1 / 2 \right) \cdot \ln \left( 1 + \left( W \cdot r _ { m } \right) ^ { 2 } \right) }
$$

$\scriptstyle \mathbf { r } = { \sqrt [ ] { p ^ { 2 } + q ^ { 2 } } }$ 取决于二维频率变量p、q； $\mathbf { r } _ { m }$ 为r的最大值;$\scriptstyle \theta = t a n ^ { - 1 } \left( q / ~ p \right)$ ；S 是强度；W 是弯曲强度。S和W 根据分析的图像进行取值，它们的值决定了核的相位导数。

# 2 本文方法流程

本文方法首先将眼底影像的G通道分量图进行增强处理以提高视网膜血管与背景的对比度，通过分析直接采用PST边缘检测算法对眼底影像处理的不足，本文先将预处理后的眼底影像利用不同尺度的高斯滤波器结合PST边缘检测算法获得初步的视网膜血管分割图，最后将初步获得的视网膜血管分割图进行整合，并利用形态学去噪获得最终的视网膜血管分割图。其流程如图1所示。

![](images/e789bd1a4536a7b5a7b08a7fe954dc0aaa5e834dfc0e6b0cd13f11230e2365d5.jpg)  
图1本文方法流程

# 2.1眼底影像预处理

视网膜眼底影像一般为RGB图像，结合色彩理论以及观察各通道分量图发现，G通道中的视网膜血管相对于其他通道的边缘信息丰富且对比度较强，如图2所示。

为进一步增强视网膜血管与背景的对比度，本文采用限制对比度直方图均衡化（contrast limited adaptive histogramequalization,CLAHE)[1]对G通道分量图进行增强。CLAHE是在局部直方图均衡时，相邻两个区域对应位置上用双线性插值方法得到增强后的图像。该方法不仅能够使眼底图像的全局灰度比较均匀，又能增强不同区域局部灰度之间的差异。预处理后如图1(d)所示，可以看出视网膜血管可以被有效增强。

![](images/fc9d55de2d3755ab408f0f8f8e8ecdc2bd7c5380950221624f75e8b47766dc5f.jpg)  
图2眼底影像各通道分量图及G通道增强图

# 2.2PST结合多尺度高斯滤波器

将预处理后的视网膜眼底影像利用PST边缘检测算法进行处理后的结果及细节如图3所示。其中图3(a)为眼底影像灰度图，(b)为PST处理后的眼底影像，(c)为血管细节图。由图3(b)可以发现，视网膜血管边缘可以有效地增强，并且分辨率较低的视网膜血管末端细小的血管位置同样可以达到较好的增强效果。但是由图3(c)PST血管分割细节图可以发现，较粗视网膜血管中心线位置有较多的干扰，而相对较细的位置则不会有这种干扰，血管边缘不平滑，并且较细血管位置容易出现断裂等问题。出现这种问题主要有两方面的原因：一方面是因为直径较大的视网膜血管在眼底影像拍摄过程中血管自身亮度变化产生的噪声；另一方面是在CLAHE对眼底影像进行增强时在增强血管细节的同时也将噪声放大。

![](images/6eb35360300dc71ed520f0b0a0c102668b16bc768ec9c63d940410c034f041f9.jpg)  
图3PST处理后的眼底影像及血管细节

为解决该问题，本文提出了多尺度高斯滤波器结合PST边缘检测算法的视网膜血管分割方法。在尺度空间中，尺度越大图像就越模糊，各种尺度的图像能够模拟目标由远及近人对目标的感知过程。通过对图像的多尺度描述，能获得对目标感知的最佳尺度。高斯函数作为卷积核是实现尺度变换的唯一线性核，将眼底影像和一定尺度下的高斯滤波器进行卷积，可以获得不同尺度下的眼底影像，即

$$
\mathbf { B } ( \mathbf { x } , \mathbf { y } , \sigma ) = \mathbf { G } ( \mathbf { x } , \mathbf { y } , \sigma ) ^ { * } \mathbf { B } ( \mathbf { x } , \mathbf { y } )
$$

其中： $\mathbf { B } ( \mathbf { x } , \mathbf { y } , \sigma )$ 为输出的不同尺度下的眼底影像； $\mathbf { B } ( \mathbf { x } , \mathbf { y } )$ 为输入的眼底影像； ${ \bf G } ( { \bf x } , { \bf y } , { \sigma } )$ 为高斯滤波器。其表达式为

$$
G ( x , y , \sigma ) = \frac { 1 } { \sqrt { 2 \pi \sigma ^ { 2 } } } \exp \left( - \frac { x ^ { 2 } + y ^ { 2 } } { 2 \sigma ^ { 2 } } \right)
$$

采用高斯滤波对眼底影像进行尺度改变时，若选用的高斯核尺度过大，则较细血管无法与背景区分或者容易造成细小血管的断裂；若选用的高斯核尺度过小，则干扰噪声无法去除。因此本文使用了不同尺度的高斯核，以针对不同直径的视网膜血管实现降噪处理。通过分析视网膜眼底影像发现视网膜血管宽度大概从2到12个像素不等，直接采用PST边缘检测算法处理后直径较大的血管位置的干扰可以达到血管直径的1/3 左右，据此，本文分别使用（3,3）和（5,5）尺度的高斯滤波器对增强后的眼底影像进行降噪处理，然后再采用PST算法进行视网膜血管分割，处理结果如图4(a)(b)所示。图4(a)从上往下一次为CLAHE 增强图、CLAHE $^ +$ (3,3)尺度高斯滤波、CLAHE $\cdot +$ (5,5)尺度高斯滤波；(b)为对应的PST边缘检测结果；(c)为背景去噪后的结果；(d)为对应区域的细节图。由图4(d)的细节图可以看出，(3,3)尺度的高斯滤波器可以平滑血管边缘，使断裂的细小的血管连通起来，消除了一部分血管内的噪声；(5,5)尺度的高斯滤波器消除了较粗血管的全部噪声，但是造成了较细血管的断裂。因此，本文结合两个尺度的高斯滤波器，以获得较好的分割结果。

![](images/476db19dc57691c252679b0720efad84a8f3a23ba5fd87979cab5e1d8aebc8d8.jpg)  
图4多尺度高斯滤波结合PST处理结果

另外，眼底影像中除眼球外的黑色背景通过图3(b)可以发现其灰度值的变化也会产生较多干扰，背景处的灰度值大概集中在0\~15像素。由于眼底影像随拍摄环境的不同，灰度值的分布亦有变化。本文针对该问题，将原眼底影像中低于最大灰度值 $5 \%$ 的像素点的位置在PST处理后的结果中的灰度值设为0。眼底影像中眼球为近似圆形，与黑色背景交界处是清晰明显的轮廓，因此在PST结合多尺度高斯滤波器处理眼底影像时该圆形轮廓边缘被明显增强，造成很大的干扰，而该操作处理不仅可以去除黑色背景的干扰，还可以减弱该干扰轮廓，处理结果如图4(c)所示。

# 2.3 后处理

本文将初步获得的三张视网膜血管分割图，分别利用形态学去噪，去除连通域小于30个像素点的噪声；然后将处理后的结果图进行叠加处理。

黄斑位置处为边缘不清晰的黑色的圆，在边缘检测的过程中该位置容易被增强，并且其处理后的连通域较大，故上一步的去噪处理并不能除去该位置的干扰。针对黄斑位置处的干扰，本文首先对叠加处理后的血管分割图进行形态学膨胀操作，然后筛除连通域的外接矩形近似正方形的区域。其处理过程如图5所示。其中图5(a)为叠加后的视网膜血管分割图；(b)为形态学膨胀操作；(c)为筛除外接矩形近似正方形的位置；(d)为最终的视网膜血管分割图。

图6给出了利用本文方法视网膜血管分割图。其中图6(a)为彩色眼底影像图；(b)为数据集中对应的专家标注图；(c)为本文方法最终的视网膜血管分割结果。图中第三张眼底影像为本文分割方法较差的结果，该眼底影像已经发生病变，并且血管末端对比度较低，由视网膜血管分割结果可以发现本文方法在含有病变的眼底影像中也能获得相对较好的结果。

![](images/3be0f575798affe85bf0bc6ef9a4faccb8212239c39dafda0c3b130f08e1c3bf.jpg)  
图5黄斑位置去噪

![](images/064f3bb3542ede746e184ff7c400cfbd76e82474f8821b34b53f68525e575e03.jpg)  
图6本文视网膜血管分割方法结果

# 3 实验结果与分析

# 3.1评价指标

目前，视网膜血管分割算法的评价指标主要有三个，即准确率（accuracy,AC）、灵敏度（sensitively,SE）和特异性（specificity,SP）。其计算公式分别如式（6）～（8）所示。

$$
\mathrm { A C } = { \frac { \mathrm { T P } + \mathrm { T N } } { \mathrm { T P } + \mathrm { F P } + \mathrm { T N } + \mathrm { F N } } }
$$

$$
\mathrm { S E } = { \frac { \mathrm { T P } } { \mathrm { T P } + \mathrm { F N } } }
$$

$$
\mathrm { S P } { = } \frac { \mathrm { T N } } { \mathrm { F P + T N } }
$$

其中：TP、FP、FN、TN分别为真阳性、假阳性、假阴性、真阴性，在结果统计中均为像素点的个数；SE体现的是眼底影像中血管被正确分割的概率；SP表征的是眼底影像中背景被正

确分割的概率；AC用来评价整张眼底影像中所有像素点被正确分割准确率。

# 3.2结果统计

为了测试本文提出的视网膜血管分割方法的有效性，本文选择了 DRIVE（digital retinal image for vessel extractionintroduction）[12]数据集中眼底影像进行测试。该数据库中共有40幅分辨率为 $5 6 5 ^ { * } 5 8 4$ 的眼底影像，分为20幅测试集和20幅训练集，每幅眼底影像都有对应的专家对视网膜血管的标注图片。该数据集是衡量视网膜血管分割方法性能好坏的最常用的数据集。由于本文中的算法不需要进行模型训练，所以将40 张全部用来测试，以验证本文算法的有效性。

本文以DRIVE 数据集中医生对每幅眼底影像中视网膜血管的标注图为标准，利用本文算法对视网膜血管分割的结果进行统计。表1中给出了本文方法的统计结果以及其他文献方法中的视网膜血管分割统计结果。由表1结果对比发现，机器学习与匹配滤波的方法在视网膜血管分割的整体准确率即AC 相差不大，在特异性指标中即 SP本文的方法略低于其他三个文献中的方法。眼底影像中视网膜血管末端细小血管的分割一直是视网膜血管分割的难点，所以血管分割会造成比较高的漏分割，即敏感性指标SE相对较低，由表1发现本文的SE要高于其他三个文献中的方法，即本文算法的漏分割率较低。本文方法属于视网膜血管分割中的匹配滤波方法，该方法不需要训练视网膜血管的分类模型，分割过程中不需要多次调用分类模型逐个像素的去判断是否为血管像素点，操作简单快速，符合临床计算机辅助诊断快速的要求，并且在SE指标中可以获得较好的结果，可以为视网膜血管分割提供一种新的方向。

表1本文方法与其他文献方法对比  

<html><body><table><tr><td>类型</td><td>文献</td><td>AC/%</td><td>SE/%</td><td>SP/%</td></tr><tr><td>机器学习</td><td>文献[11]</td><td>96.09</td><td>74.47</td><td>98.38</td></tr><tr><td rowspan="3">匹配滤波</td><td>文献[13]</td><td>94.89</td><td>76.57</td><td>98.09</td></tr><tr><td>文献[14]</td><td>95.74</td><td>74.10</td><td>98.94</td></tr><tr><td>本文方法</td><td>95.02</td><td>77.87</td><td>97.01</td></tr></table></body></html>

# 4 结束语

眼底图像的视网膜血管分割是眼科计算机辅助诊断和大规模疾病筛查的基础，也是近年来的研究热点。基于匹配滤波的视网膜血管分割是一种快速高效的方法。本文提出了一种结合PST边缘检测和多尺度高斯滤波的视网膜血管分割方法，首先利用CLAHE对眼底影像的G通道分量图进行增强；然后将多尺度高斯滤波器和PST边缘检测算法结合起来，以针对不同直径的血管实现降噪处理，初步获取视网膜血管分割图；最后将初步获取的视网膜血管分割图进行整合，并利用形态学去噪，最终获得视网膜血管的分割图。在DRIVE 眼底图像数据集上对本文算法进行验证，与其他方法相比结果较好。但是同样面临血管分割难点的问题，即视网膜血管末端细小血管的分割问题。目前，视网膜血管分割在敏感性指标中普遍结果在 $7 5 \%$ 左右，本文方法在该指标中有一定的提升达到了 $7 7 . 8 7 \%$ ，但是视网膜血管分割算法还有很大的提升空间。在后续的工作中，将针对如何进一步降低血管的漏分割率进行研究，为视网膜血管分割方法提供更可靠的借鉴。

# 参考文献：

[1]李祁凤，刘国才，段宣初，等．基于多相 Mumford-Shah 模型最小图分 割的视乳头杯盘分割[J].计算机应用研究,2011,28(8):3151-3154.   
[2]朱承璋，邹北骥，向遥，等.彩色眼底图像视网膜血管分割方法研究进 展[J].计算机辅助设计与图形学学报,2015,27(11):2046-2057.   
[3]Nayebifar B,Moghaddam HA.A novel method for retinal vessel tracking usingparticle filters[J].ComputersinBiology& Medicine,2013,43(5): 541-548.   
[4]Zhang Jia,Li Huiqi,Nie Qing,et al.A retinal vessel boundary tracking method based on Bayesian theory and multi-scale line detection [J]. Computerized Medical Imaging& Graphics,2014,38(6): 517-525.   
[5]Li Q, You J, Zhang D. Vessel segmentation and width estimation in retinal images using multiscale production of matched filter responses [J]. Expert Systems with Applications,2012,39(9):7600-7610.   
[6]曹新容，薛岚燕，林嘉雯，等．基于匹配滤波和自动阈值的眼底血管分 割方法[J].电子测量与仪器学报,2017,31(1):51-57.   
[7]Lupascu C A,Tegolo D, Trucco E. FABC: retinal vessel segmentation using adaboost [J].IEEE Trans on Information Technology in Biomedicine,2010, 14 (5): 1267-1274.   
[8]Salazar-Gonzalez A,Kaba D,Li Y,et al. Segmentation of the blood vessels and optic disk in retinal images [J].IEEE Journal of Biomedical and Health Informatics,2014,18(6):1874-1886.   
[9]朱承璋，崔锦恺，邹北骥，等．基于多特征融合和随机森林的视网膜血 管分割[J].计算机辅助设计与图形学学报,2017,29(4):584-592.   
[10] Asghari MH, Jalali B.Edge detection in digital images using dispersive phase stretch transform [J]. Journal of Biomedical Imaging,2015,2015: 687819.   
[11] Reza A M.Realization of the contrast limited adaptive histogram equalization (CLAHE) for real-time image enhancement [J].Journal of Vlsi Signal Processing Systems for Signal Image & Video Technology,2004,38 (1): 35-44.   
[12] Viergever M,Luijten P.DRIVE:digital retinal images for vessel extraction [EB/OL]. (2010).http://www. isi.uu. nl/Research/Databases/DRIVE/.   
[13]黄文博，王珂，杨燕．彩色视网膜眼底图像血管自动检测方法[J]．光 学精密工程,2017,25(5):1378-1386.   
[14]梁礼明，黄朝林，朱莎，等．基于Hessian 矩阵和水平集的视网膜血管 分割[J].科学技术与工程,2016,16(10):44-49.