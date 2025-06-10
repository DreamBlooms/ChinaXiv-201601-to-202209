# Astrometrica与MaxImDL在天体测量的应用与技术研究

郭碧峰1,²,彭青玉1,2\*，林孚荣1,2(1 暨南大学计算机科学系 广州 510632)(2 暨南大学中法天体测量、动力学与空间科学联合实验室广州510632)

摘要：为探究Astrometrica和MaxImDL两个软件在天体测量中的应用与处理差异，本文从上述两个软件的总体情况、CCD图像的读写与变换、平场校正处理、参数设置、归算与堆叠等方面进行了详细的比较和技术研究。以中国科学院云南天文台1m光学望远镜拍摄的M35星团的2组观测资料为例，探究了Astrometrica 均值、中值和MaxIm DL均值、中值、标准差(Sigma Clip)、迭代的标准差(SDMask)6种图像堆叠方法的输出结果。本文对上述6种输出结果进行了数据归算，具体参考了Gaia DR2星表，比较了上述6种堆叠方法星像的位置测量精度。本文发现使用 Astrometrica中值堆叠输出的图像在位置精度中存在异常。最后，本文提出了两个软件在天体测量和巡天工作中配合使用的方法。

关键词：天体测量软件技术研究；天体测量；CCD 图像处理；Astrometrica；MaxIm DL

中图分类号：P129 文献标识码：A

# 1引言

信息化与工业化是社会与科技发展的趋势。用于天体测量的处理工具和软件目前与传统制造业的工业化仍存在一定的差距，导致不同的科研工作者在天体测量的处理和研究中使用的工具和软件不相同。一定程度上，这种模式不利于对科学的讨论与探究。CCD 图像处理是天体测量中一个重要的环节，而正确地使用现有的天体测量处理工具和软件可以确保CCD 图像处理结果的准确性和可信度，也有利于推动科学研究的探索和发展。

Astrometrical1l和MaxImDL[2是两个可用开发于天体测量的公开软件。当然，也有许多科研工作者使用自主研发的处理程序和软件用于天文研究工作，如孙浩民等人开发的射电测量集文件生成软件[和张珊瑚等人开发的一维光谱可视化与分析工具[4]。本文主要对 Astrometrica 和 MaxIm DL 在天体测量中的应用和处理结果进行比较和技术研究。Astrometrica 是由Raab Herbert研发的用于天体测量处理的软件，对于太阳系小行星的巡天、数据归算有较大的帮助与参考价值。Astrometrica主要有CCD 图像的读写与变换、平场校正、太阳系小行星目标检测、数据归算、图像堆叠等功能。Astrometrica的使用也帮助人们在天体测量、巡天等工作中提供了参考并取得了良好的进展。例如，Qiao 等人使用 Astrometrica 软件对拍摄的土星卫星 $^ { [ 5 ] } \mathrm { C C D }$ 图像进行处理与位置测量，得出了较好的准确度。Vaduvescu等人使用该软件进行巡天工作]，发现了280颗近地小行星。MaxImDL是由Diffraction公司研发的主要用于天文望远镜观测、测光和天体测量的一套软件，广泛使用于天文爱好者和科研工作者，例如Gupta等人使用 MaxImDL对OJ287天体的观测资料进行了平场处理和测光的数据处理[7]。

本文的第2部分讨论了Astrometrica与MaxImDL两个软件在天体测量中CCD 图像处理的应用比较与技术研究。第3部分通过实验比较了Astrometrica和MaxImDL两个软件的6种堆叠方法对位置测量精度的影响。第4 部分讨论了Astrometrica 和MaxIm DL两个软件在天体测量和巡天中配合使用的方法。最后一部分进行了总结，并提出了后续的研究方向。

# 2Astrometrica与MaxImDL的应用比较与技术研究

Astrometrica 主要有CCD 图像的读写与变换、平场校正处理、太阳系小行星移动目标检测、数据归算、图像堆叠、生成MPC 报告等功能，对太阳系巡天工作与天体测量有较大的帮助。MaxIm DL主要有控制观测设备、读写CCD图像、测光、图像质量评估、图像堆叠、运行自定义脚本等功能。

虽然 MaxImDL也能进行相应的数据归算，但是该功能需要协同其他软件才能进行使用，所以本文不讨论两个软件在数据归算功能的比较。相比之下，MaxImDL的功能要比Astrometrica的多，毕竟它们的购买费用与研发规模不同。本文主要从上述两个软件用于天体测量工作的功能进行比较与技术研究。具体地，我们从CCD 图像的读写与变换、平场校正处理、Astrometrica 参数的设置与归算、图像堆叠和两个软件的总体评价进行详细论述。

# 2.1CCD图像的读写与变换

在图像的读写过程，Astrometrica可以读取8位、16 位和32位的整型的FITS 图像，但只能存储为16位的整型图像。相比之下，MaxImDL支持更多图像格式的读取与存储，具体可以查阅该产品的用户手册。值得注意的是，上述两个软件目前还不支持64 位浮点型 FITS 图像的读取，但SAOImage $\mathrm { D S 9 ^ { [ 8 ] } }$ 是支持的。如果我们需要用Astrometrica 和MaxImDL进行图像处理，需要尽量避免使用这种类型的图像。Astrometrica、MaxIm DL 和 SAOImage DS9 都可以查看FITS 图像的头文件。但我们在实践中发现，对于存在“千年虫”问题的 FITS 图像，即其中头文件的键值对存在形如“DATE-OBS $\ c =$ MM/DD/YYY”的格式，SAOImageDS9可能出现头文件信息的键值对数量显示不完整的问题。此外，Astrometrica目前只能手动修改观测时间的头文件信息，而 MaxImDL可以编辑大部分的头文件信息，也包括增加与删除键值对。

Astrometrica 和MaxImDL均能对图像进行灰度变换的调整，使图像有更好的视觉效果。在图像的变换功能上，MaxImDL的功能要比Astrometrica强大得多。MaxImDL除了能调整简单的像素灰度变换外，还支持热像素的忽略、大量的滤波器的使用、图像任意角度的旋转、反卷积操作、增加噪声、像素合并、剔除坏像素等功能。当拍摄的CCD图像角度与星图中不匹配时，旋转图像的角度可以较好地帮助我们手动匹配星像。对于天体测量处理过程，我们不建议对图像做除平场校正外的其他图像变换处理，如使用滤波器处理、反卷积操作。我们认为这些操作只能让图像有更好的视觉效果，而对位置测量的结果不会有明显的提高。Astrometrica 在用户手册术语表的校正说明中也提到：“进一步的图像处理（如直方图缩放、使用滤波器或反卷积）可能会扭曲星像的质心与光通量。”

# 2.2平场校正处理

CCD 图像的平场校正处理是测光中重要的一个步骤，有时我们也把该技术应用在天体测量中。Astrometrica 和 MaxImDL均有平场校正处理的功能。Astrometrica 只能使用1幅暗场图像(Dark)和1幅平场(Flat)图像进行校正处理，而 MaxIm DL 则支持多幅暗场、平场和本底(Bias)图像进行校正。此外，MaxImDL可以把不同类型的校正图像分组，每组可以通过均值、中值等方法生成一张“主”("Master")图像以节省校正图像的内存空间和提高校正的运算速度。MaxImDL还可以自定义调整图像的“底座”("Pedestal")像素值以确保图像的像素值为正数。当平场处理后的图像需要作为其他工具的输入图像时，我们一般会结合使用 MaxIm DL 中批量保存与转换功能(Batch Save and Convert),这样能快速地批量输出平场校正后的图像。

# 2.3Astrometrica参数的设置与归算方法

在CCD的参数设置中，有时望远镜焦距和像素大小的设置可能会难以确定，因为这些信息不一定会包含在图像的头文件中。本文给出两种确定上述两个参数的方法。实际上，像素大小与望远镜焦距之比就是图像的比例尺。我们可以这样认为，只要两者之间的比例是正确的，Astrometrica也能正确地进行数据归算和图像堆叠。第一种确定图像比例尺的方式是把图像上传至astrometry.net获得，详细的算法可以参考Lang等人的论文[9]。第二种确定比例尺的方法是把图像中两颗恒星与星图匹配，通过坐标转换关系计算出比例尺。

使用 Astrometrica 得出数据归算的结果对于高精度的天体测量来说是不够的。我们将讨论如何提高 Astrometrica 在数据归算中参考星的精度问题。在软件的设置中，参考星的搜索半径(Search

Radius)、星表极限星等(Upper/ Lower Limit)、检测目标的孔径大小(Aperture Radius)、检测极限(Detection Limit)等参数的调整都会影响参考星的精度。参考星的搜索半径是指图像中搜索的恒星与星表中参考星位置的最大误差，若搜索的恒星与星表中参考星的位置偏差小于设置的参数时，系统会认为这两颗星是同一颗星。星表的极限星等设置会影响星表中用于匹配的参考星，我们认为把该参数调整到星像未饱和的亮星区间范围是较好的。检测目标的孔径大小和检测极限按照用户手册推荐的参考数值范围进行设置对于参考星精度的影响不大。我们实践发现参考星搜索半径参数的调整对参考星精度的影响较大，对此我们给出了中国科学院云南天文台1m光学望远镜连续拍摄的 M35星团的3幅原始的(未做平场校正等处理)CCD 图像进行实验对比。我们把3幅图像分别命名为A、B、C，以B为基准，对相同参考星的二维坐标的残差(即A、C中每颗参考星的坐标与B中相同参考星的坐标之差)进行统计。图1-图2分别显示了参考星搜索半径为lpx 和0.51px图像坐标的残差情况。

从图1中我们可以看到在图像Y方向的残差存在异常点，有若干的参考星在位置上偏离了正常值约0.7个像素。在图2中，我们把参考星的搜索半径设置为 $0 . 5 1 \mathrm { p x }$ 时(0.51px是该软件能设置的最小值)，我们可以看到大部分的异常点消失，参考星的精度有所提高。我们认为参考星的搜索半径参数应设置得尽可能小来提高参考星的测量精度。当然，我们也可以调整测量的极限残差(AstrometricLimit)来选择高精度的参考星进行匹配。但是我们很难确定并设置测量极限残差的最优值，它与底片常数阶数的选择、参考星匹配的数量和观测资料等因素都有较大的关系。我们也探索了参考星位置残差异常点的原因。如图1右下角子图的残差异常点所示，Astrometrica对于同一颗参考星似乎搜索了两次或三次，且每次恒星中心的坐标都不同。我们在Astrometrica 的数据归算过程中的确找到了同一颗星被搜索成两颗或三颗星的现象如图3所示。

在实践中我们发现Astrometrica对于暗弱或圆度较大的星像可能会把同一颗星搜索成两颗或三颗不同的恒星。也就是说，Astrometrica对于搜星是过于敏感的，毕竟我们也用它来做巡天工作。为了尽可能消除这种搜星的过敏感性对参考星精度的影响，我们建议参考星的搜索半径设置到最小，即 $0 . 5 1 \mathrm { p x }$ 。

![](images/ecb7388056a8a3cbbcba4483418e568c063b4cb2afc1622a40dc40e8b54a96e4.jpg)  
图1 参考星搜索半径设置为1px 时A、C 两幅图的参考星在二维坐标的残差分布 Fig.1Residual distributionof reference stars in two-dimensionalcoordinates ofAand Cimages whenthe searchradius of reference stars is set to 1px

![](images/9313391a6665b8ef3bdfb918c4a02b687fc2bdeb9dd4a1879ad34c788c27ba54.jpg)  
图2参考星搜索半径设置为 $0 . 5 1 \mathrm { p x }$ 时A、C两幅图的参考星在二维坐标的残差分布 Fig.2Residual distributionofreference stars intwo-dimensionalcoordinates ofAand Cimages whenthe searchradius of reference stars is set to 0.51px

![](images/803068ba5d0c6fe2c2416c0aca0d227052b807a751da95a615bce6e5a0d44973.jpg)  
图3左、右两幅子图分别是Astrometrica把一颗恒星搜索成两颗、三颗不同的恒星 ig.3 The left and right respectively show that Astrometrica searches a star into two and three diffrent sta

# 2.4 CCD图像堆叠

CCD 图像的堆叠可以提高图像的信噪比，对暗星测光和位置测量工作有较大的帮助。Astrometrica 和 MaxImDL 都有图像堆叠的功能，下面我们将对它们的堆叠机制进行讨论。在Astrometrica中，设置好参数和数据归算都是图像堆叠的前置条件。在堆叠的参数设置中，目标移动的速度与角度的调整一般用于巡天工作。当我们用于恒星位置测量时，上述的两个参数应设置为0。Astrometrica 有数值叠加(Sum)、均值叠加(Average)、中值叠加(Median)三种堆叠方法可以选择。通常，数值叠加方法适用于巡天工作而不适用于位置测量工作，因为数值叠加方法会导致大部分的星像饱和从而影响星像质量。均值与中值均适用于位置测量，关于两者的细节，我们在第3部分将进行详细的对比实验与讨论。我们通过观察 Astrometrica 的运行和查看日志文件不难看出它在图像堆叠中的运作机制。首先，Astrometrica在进行图像堆叠前对两幅图像进行了数据归算。然后，它根据数据归算的结果把需要堆叠的图像进行对齐(图像X轴与Y轴)。不过Astrometrica在图像对齐时只考虑了图像两个坐标方向的简单平移。最后，Astrometrica根据设置的参数与叠加方法进行图像堆叠。

在MaxImDL的堆叠过程中，有图像分类、选择符合质量的图像、图像对齐、调整颜色、选择叠加方法五个步骤进行处理。在图像分类过程中，MaxImDL可以根据我们所选的文件夹以及观测的目标和观测时使用的滤光片进行分类。此外，我们也能在叠加工作进行前进行平场校正、合并像素等操作。在选择符合质量的图像过程中，MaxIm DL 把每幅图像的星像半高全宽(FWHM)、圆度(Roundness)、光强(Itensity)、对比度(Contrast)作为质量评估的标准，关于这些参数的详细说明可参照软件的用户手册。在图像对齐的过程中，相比Astrometrica，MaxImDL的星像自动对齐模式多考虑了图像的旋转与图像的缩放关系，这相当于考虑了4-常数模型。在图像的叠加方法选择中，MaxImDL 除可选数值叠加、均值叠加、中值叠加方法外，比起 Astrometrica 还提供了标准差(Sigma Clip)、迭代的标准差(SDMask)、抖动(Drizzle)三种方法的叠加,关于这些叠加方法的详细说明可参照 MaxImDL 用户手册。对于Astrometrica 和MaxImDL提供的叠加方法的区别，本文的第3部分将进行实验说明与详细的讨论。

# 3Astrometrica与MaxImDL图像堆叠方法的比较实验

在本节中，我们将详细讨论 Astrometrica与 MaxIm DL 提供的叠加方法对位置测量的影响。我们在实验中没有考虑数值叠加(Sum)方法与抖动(Drizzle)方法，因为对图像进行数值叠加会造成大量星像的饱和，而抖动叠加方法主要用于欠采样、抖动观测的图像。我们比较了Astrometrica 提供的均值叠加(Average)、中值叠加(Median)算法和 MaxIm DL 提供的均值叠加(Average)、中值叠加(Median)、标准差叠加(Sigma Clip)、迭代的标准差(SD Mask)叠加方法。均值叠加算法将一组图像对齐后，取每幅图像各位置像素值的平均值，而中值叠加算法则取每幅图像各位置像素值的中值。标准差剔除算法将每幅图像各位置像素值进行标准差剔除(软件的推荐值为3倍标准差)后再取剩余像素值的平均值，而迭代的标准差算法则是一种多次迭代的标准差(软件的推荐值为0.5倍标准差，迭代3次)算法。

我们选取了中国科学院云南天文台1m光学望远镜拍摄的 M35 星团的CCD 图像进行实验，包括了2020年2月7日与2020年3月5日拍摄的2组共50幅使用I滤光片观测的CCD图像，每幅图像的曝光时间为60秒。这2组观测资料的大气宁静度较好，图像抖动程度较小(即基本指向稳定)，大部分图像中星像的半高全宽为4.5-6像素。但观测时接近月望，所以图像的天空背景值相对较高，我们将看到图像堆叠可以有效地提高星像的信噪比。

在处理过程中，第一步，我们利用观测的若干平场和本底图像使用MaxImDL对2组观测资料进行了平场校正处理。第二步，我们使用MaxImDL对平场校正处理后的图像进行质量筛选。其中，2020年2月7日的筛选标准为半高全宽不大于5个像素，圆度不大于0.2；2020年3月5日的筛选标准为半高全宽不大于6个像素，圆度不大于0.2。第三步，我们在每组观测资料中选择了15 幅满足质量要求的图像，每5幅图像为一组，分别使用Astrometrica和MaxImDL选择不同的方法进行图像叠加操作。在MaxIm DL的叠加操作中，其他的参数与设置均使用系统的默认值或推荐值且在实验中保持不变。第四步，我们根据叠加的2组共18幅实验图像(每5幅图像叠加后的图像为1幅实验图像)根据叠加方法的分类进行了数据归算，其中我们参照了Gaia DR2 星表[的位置，具体可参考Lin等人[1的数据归算方法。图4\~图9给出了2月7日观测资料中每种叠加方法恒星随星等在精度方面的分布情况，3月5日观测资料在位置测量中精度方面的分布情况与2月7日是相似的。

从图4-图9中我们可以看到赤纬方向位置精度的弥散程度比赤经方向略大一些。此外，我们注意到使用 Astrometrica 中值叠加方法处理的图像(见图 5)在赤经、赤纬方向的精度分布情况是异常的，即星等亮于14 等的恒星在赤经、赤纬方向的精度比亮度在14 等左右的恒星的精度还要差，这是一种异常的情况。我们认为导致这种异常现象的原因是Astrometrica在进行图像对齐时使用的超定方程组的数据均来自于14等星左右的坐标。

![](images/2447191ca4516e26dc06fc0b10ac192c5917fe42d01ce0268a95e954dcce7784.jpg)  
图4 Astrometrica 均值叠加后恒星O-C(观测值-计算值)的标准差在赤经、赤纬的分布情况，其中红色实线表示亮于14等星标准差的中位数(下同)

Fig.4Thedistributionof stars’standarddeviationofO-C(observed minus computed)inrightascensionanddeclinationafter Astrometrica'saverage stacking,where thered solid linerepresents the medianofthe standard deviation brighter than14

![](images/d440794f7dd8f9ed49fa0c806c9602dc771537ceed52e5fda0a5801dff169c26.jpg)  
图5Astrometrica中值叠加后恒星O-C(观测值-计算值)的标准差在赤经、赤纬的分布情况

Fig.5Thedistributionofstars'standarddeviationofO-C(observed minuscomputed) inrightascensionanddeclinationafter ie distribution of stars’standard deviation of O-C (observed minus computed) in right ascension and declin

![](images/2924edda35adda41c36828281502c4d0e67d25bbe4c45f7899cd3d55b3ad8544.jpg)  
图6MaxImDL均值叠加后恒星O-C(观测值-计算值)的标准差在赤经、赤纬的分布情况

![](images/d46384f8c0367ccb713f1f356dd7fc67875908de51b3c3321409f4c3e5ba7718.jpg)  
图7MaxImDL中值叠加后恒星O-C(观测值-计算值)的标准差在赤经、赤纬的分布情况

Fig.7The distributionof stars’standard deviationofO-C(bserved minus computed) inright ascension anddeclinationafter MaxIm DL's median stacking

![](images/37123f91f4c32cfe9b7943b29e9cc350b83785629dbbc2efc111d3583717ecbf.jpg)  
图8MaxImDL标准差叠加后恒星O-C(观测值-计算值)的标准差在赤经、赤纬的分布情况

![](images/da35974c1e5d5b5773cb6650e6dfdcbacdea7b1747dbd43b72eaa02d3e0e5366.jpg)  
Fig.8Thedistributionof stars’standarddeviationofO-C(bserved minuscomputed) inrightascensionanddeclinationafter   
图9 MaxImDL迭代的标准差叠加后恒星O-C(观测值-计算值)的标准差在赤经、赤纬的分布情况 ig.9The distributionof stars’standard deviationofO-C(observed minus computed)inrightascensionanddeclinationafter MaxIm DL's SD Mask stacking

# 4Astrometrica与 MaxImDL 的配合使用

Astrometrica和MaxImDL的CCD 图像处理功能对天体测量的研究都有较大的帮助，且它们考虑的功能和细节也略有不同。Qiao等人在位置测量的处理中，背景调整、平场校正、数据归算等步骤都是基于 Astrometrica 进行的[5]。在实践中，我们可以结合两个软件的优势进行CCD 图像处理与研究。Astrometrica在平场校正处理中只能使用一幅平场图像和一幅暗场图像，而MaxImDL可以使用多幅图像进行平场校正处理。我们可以先使用MaxImDL进行CCD图像的平场校正处理，再使用Astrometrica 对校正后的图像进行数据归算。Vaduvescu 等人使用 Astrometrica 通过数值和中值叠加CCD 图像的方式进行巡天工作，发现了280 颗近地小行星。从图5中我们可以看出，使用Astrometrica对CCD 图像进行中值叠加后存在位置测量精度异常的情况。MaxImDL在图像的堆叠中也考虑了更多的参数与细节问题。此外，MaxIm DL 在进行图像的中值叠加时不会出现位置测量精度异常的情况。实践中，我们可以先使用MaxImDL进行CCD图像的质量筛选和图像堆叠。然后，我们再使用 Astrometrica 进行巡天工作。综上所述，结合 Astrometrica和 MaxImDL两个软件的使用对天体测量和巡天工作可能有较大的改进。

# 5总结与展望

在本文介绍了Astrometrica 和MaxImDL两个软件在天体测量中的应用，对两个软件从CCD图像的读写与变换、平场校正处理、参数的设置与归算方法、图像堆叠进行了详细的比较和技术研究。此外，我们使用了中国科学院云南天文台1m望远镜拍摄的2组目标为M35星团的观测资料来比较和探究了Astrometrica和MaxImDL两个软件图像堆叠功能对恒星位置测量精度的影响。我们发现，使用 Astrometrica 中值叠加处理后的图像在位置测量的精度上会出现异常。结合两个软件的特点，我们提出了两个软件配合使用的方法。在后续的研究工作中，我们会进一步探究MaxImDL的一些图像处理功能，并应用在我们的天体测量工作中，以提高位置测量的准确度和精度。

# Applications and Technology Research for Astrometrica and MaxIm DL in Astrometry

Guo Bifeng1.2,Peng Qingyu1.2\*,LinFurong1,

(1 College of Information Science and Technology,Jinan University,Guangzhou,51O632, China) (2 Sino-FenchJointLaboratoryforAstrometry,DynamicsndSpacecience,JinanUniversity,Guangzhou,51632,Cina)

Abstract: In order to explore the difference of Astrometrica and MaxIm DL for application and CCD image processing in Astrometry,overall introduction, loading,saving and transforming CCD images,flat calibration， data reduction and stacking of the two suites of software are detailedly compared and technically researched in this paper.Taking the example of two sets of observations of M35 Cluster photographed by the 1m optical telescope of Yunnan Observatory of Chinese Academy of Sciences, this paper explores the output results of the 6 stacking methods including Mean, Median of Astrometrica and Mean, Median, Sigma Clip and SD Mask of MaxIm DL. Referring to Gaia DR2 Catalog,this paper reduces the 6 output results above and compares their precision of the star images.In this paper, we find anomalies in the position accuracy of the output images using Astrometrica's Median stacking. At the end of this paper, we put forward some methods of using the two suites software in combination for astrometry and survey.

Key words: Technical Research for Software Used in Astrometry; Astrometry; CCD Image Processing; Astrometrica; MaxIm DL

# 参考文献

[1] http://www.astrometrica.at/   
[2] http://diffractionlimited.com/   
[3] 孙浩民，邓辉，梅盈,等．基于 Python-casacore 的射电测量集文件生成方法[J]．天文研究与技术，2020,17(2) 210-216.   
[4] 张珊瑚，邱丹，聂嘉潞,等．基于 MATLAB 的一维光谱可视化与分析工具的设计与实现[J].天文研究与技术 2020,17(1): 121-128.   
[5] Qiao R.C.,Xi X.J.,Dourmeau G,et al., CCD astrometric observations of Phoebe in 2005-2008[J].Monthlyof the Royal Astronomical Society, 2011,413(2):1079-1082.   
[6] Vaduvescu O.,Hudin,L.,Mocnik T.,etal.,280 one-opposition near-Earth asteroids recovered bytheEURONEAR with the Isaac Newton Telescope[J].Astronomy & Astrophysics,2011, 609:A105.   
[7] Gupta A.C., Gaur H.,Wiita,P.J.,et al., Characterizing Optical Variabilityof OJ287 in 2016-2017[J].The Astronomical Journal, 2019,157(3):95.   
[8] Joye W.A.,Mandel E., New Features of SAOImage DS9[C].Astronomical Data Analysis Software and Systems XII ASP Conference Series, 2003,295:489-492.   
[9] Lang D., Hogg D.W., Mierle K., etal., Astrometry.net: Blind Astrometric Calibration of Arbitrary Astronomical Images[J]. The Astronomical Journal,2010,139(5):1782-1800.   
[10]Gaia Collaboration,BrownA.G.A.,Vallenari,A.,etal.,GaiaDataRelease 2.Summaryofthecontents andsurvey properties[J]. Astronomy & Astrophysics,2018, 616:A1.   
[11]Lin FR.,PengJ.H.,Zheng Z.J.,etal., Characterization of the precision premium in astrometry[J].Monthly Notices of the Royal Astronomical Society, 2019,490(3):4382-4387.