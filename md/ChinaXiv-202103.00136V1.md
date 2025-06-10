# CCD图像相对测光中的技术研究与精度回报现象

郭碧峰1²，彭青玉1,2\*，尚一佳¹²，覃永贵²，林孚荣1,2(1 暨南大学计算机科学系 广州 510632)(2 暨南大学中法天体测量、动力学与空间科学联合实验室广州 510632)

摘要：天体随时间的光度变化能够反映其物理性质，高精度测光技术的研究帮助我们更好地分析与探究天体的光变情况，对天体的演化研究有重要意义。本文介绍了相关的测光工具与技术，探索了把 MaxImDL软件与photutils测光库相结合的测光技术及其应用，提出了连续图像中各星像测光数据快速匹配的解决方案。通过分析中国科学院云南天文台 $ { \mathrm { 1 m } }$ 光学望远镜拍摄的M35星团图像，本文发现了相对测光中存在精度回报(precision premium)现象，即相近的两颗星进行相对测光具有更高的测量精度，且该现象的显著程度与大气质量相关。针对于相对测光的精度回报现象，本文提出了高精度相对测光的参考方法。

关键词：相对测光； 测光精度回报；CCD 图像处理； photutils；MaxIm DL中图分类号：P141.2 文献标识码：A

# 1引言

天体的光度测量工作主要研究天体的光度随时间的变化情况，光度变化能够反映出天体的物理性质，对探究天体的演化规律有重要意义。例如，文献[1]从小行星的光变周期中分析出自转周期和形状，文献[2]研究了柯伊伯带天体的光变周期，分析了其反照率等物理属性，文献[3]利用中长周期光变研究类星体的物理属性。然而，人们在天体的高精度光度测量中面临许多挑战。由于地球大气的影响，天体的光度经过地球大气后存在一定的消光和折射效应，对天体的测量精度有着较大的影响。由于相近(天空平面内角距离较小)的恒星之间相对位置变化较小且通过的大气相似，我们通常使用相对测光的方法进行测量。然而，太阳系天体(特别是近地小行星)相对于恒星位置变化较快且经过不同的大气质量，绝对测光(全天测光)则是一种更好的选择。在地面望远镜观测中，人们可以通过该方法准确地求出大气消光、夜间零点等系数，以降低大气的影响。Landolt提供了标准星的详细参数与信息[4，为绝对测光研究奠定了良好的基础。尽管如此，绝对测光的精度不如相对测光。为了消除地球大气对光度测量的影响，随着科技的发展和进步，人们把探测器发送到空间中(例如哈勃空间望远镜和Gaia卫星)，测光精度有了显著的提高。

本文主要研究基于地面观测的光度测量技术和精度回报现象。在地面观测中，为了提高位置和光度的测量精度，通常我们选择目标在子午线附近观测，以减少大气造成的影响。在天体测量中，

Pascu 发现两颗伽利略卫星相互靠近时有较好的位置测量精度[5]，Morgado等人在此基础上开发了相互逼近天体测量技术，Lin 等人基于M35 星团对该现象进行统计分析，把位置测量的精度回报现象进行特征化[7]。在相对测光中，人们主要关注参考星光度的稳定性而较少地关注目标星与参考星在天空平面内的角距离。若相对测光中也存在精度回报现象，即假设目标星存在许多不同相对距离的候选参考星，且这些参考星的光度相近、稳定，则采用相对距离较小的参考星会有较高的测量精度。基于中国科学院云南天文台1m光学望远镜观测的M35星团资料，本文将探究相对测光的精度回报现象。

本文的第2部分介绍了现有的测光工具及其技术，提出了把MaxImDL软件与photutils 库相合的测光技术及其应用。第3部分统计和分析了M35星团在不同高度角中相对测光的精度与相对距离之间的关系，发现了相对测光中存在精度回报现象，提出了高精度相对测光的参考方法。最后一部分进行了全文的总结。

# 2光度测量工具与关键技术

# 2.1光度测量工具

随着信息化与工业化的发展，目前有许多开放的光度测量工具和软件。例如 IRAF 能够较好地处理图像并进行测光，但需要在 Linux 环境下进行配置和操作。Aperture Photometry Tool(APT)是一款孔径测光的教学软件，能够方便地进行孔径测光、求取生长曲线等[8]。SExtractor被广泛运用在深度巡天的目标源提取和测量中。MaxImDL 除了可以方便地进行批量平场处理、图像质量评估、图像堆叠外，也能方便地进行孔径测光[9]。后来，随着计算机技术的发展和 Python 编程语言的兴起，PyRAF(htps://pypi.org/project/pyraf/)和photutils(htps://photutils.readthedocs.io/en/stable/index.html)成为了方便测光的Python 库。

# 2.2MaxImDL与photutils相结合的测光技术

Photutils 是基于Python 语言的测光库，也是 Astropy 的附属软件包，用户可以通过编程方便地调用其目标检测、光度测量等函数。DaoStarFinder和 IRAFStarFinder是该库函数中用于目标检测的两个函数，分别调用了DAOPHOT 和 IRAF 的搜星程序。Photutils 库中提供了孔径测光和点扩散函数测光两种方法。本文主要使用和探究孔径测光方法，即 photutils.aperture库。在该库中，浮点型数值的孔径半径的设置为孔径测光提供了更高的精度，而MaxImDL、APT等测光软件的孔径半径数值只能设置为整数。此外，aperture_photometry 函数中的 exact 方法能够精确地处理孔径测光中包含像素的分数部分，相比划分子像素(subpixel)方法有着更高的测量精度。

然而，使用Photutils 对地面的观测资料进行光度测量的过程中也存在一些问题。在目标检测(搜星)函数中，无论我们使用DaoStarFinder还是IRAFStarFinder方法，像素阈值(threshold 参数)和星像的半高全宽(FWHM参数)就是必选的输入参数。通常，像素阈值我们选择几倍(例如3-5倍)背景像素的标准差作为输入，而做巡天研究工作时需要把该参数设置得更小。要准确地搜索出观测资料中的大部分星像，传入的半高全宽参数需要与每幅图像相近。当然，我们希望每个晚上观测资料的半高全宽是稳定的，这也需要天气与设备的配合。但实际上，在地面观测中，即使用同一台望远镜连续观测的图像，星像的半高全宽也有一定的波动。因此在测光程序批量处理时，若使用一个大致的半高全宽作为目标检测函数的参数输入，则一些图像中大部分的星像不能被检测出来。对于此类情况，我们可以把半高全宽与设定值相差较大的图像进行单独处理或编写自适应调整半高全宽参数的相关算法。由于上述方法操作或实现过程较复杂，本文提出了与MaxImDL软件相结合的方法。MaxIm DL软件(本文使用 5.24版本)在图像堆叠过程中提供了批量图像质量评估的功能，可以方便地导出每幅图像的半高全宽、圆度等信息(如图1左子图所示)。当我们使用 MaxImDL输出每幅图像的半高全宽数据作为目标检测函数参数的输入时，可以较好地解决图像之间星像半高全宽波动较大的搜星问题。

我们在实践中发现，目标检测函数中传入的半高全宽参数取MaxImDL导出的数值再加上0.5有着更好的搜星效果。

在光度测量的过程中，分析和统计出视场中所有星像的光变情况对变星巡天、星像特征分析有着重要意义。如何把各图像的星像进行相互匹配是统计视场中所有星像的光变的关键问题。对于望远镜指向和取向基本稳定的观测资料来说，获取主帧(一般选择质量较好的图像)所有星像的位置和光度信息就能较好地与其他图像匹配(例如设置一定的像素阈值和光度阈值)，从而方便地画出目标的光变曲线。然而，观测时望远镜指向或跟踪不稳定(例如每幅图之间平移 5px)，统计出视场中所有星像的光度变化是不容易的。本文结合MaxIm DL 软件对该问题提出了一种快速的解决方案。首先，使用 MaxIm DL的对齐功能可以方便地导出每幅图相对于第一幅图在像素坐标的偏移量(如图1右子图所示)。然后，在每一幅图探测出来的星像坐标中减去相应的偏移量(XShift 和 YShift)。此时，我们可以消除由于望远镜指向不稳定带来的视场偏移，能够方便地进行各图像中星像的匹配和统计工作。但如果需要对各星像中的更多信息(例如色指数、视差等)进行分析和统计研究，我们需要采用基于星表匹配的方法，但该方法需要花费更长的时间。

FWHM， Roundness,Intensity, Image XShift, YShift, Theta, Image   
5.905, 0.162, 37273.6, 01_flat.fit 0.00， 0.00, 0.00, 01_flat.fit   
7.031, 0.207, 38790.5, 02 flat.fit 3.11, -0.22, 360.00, 02_flat.fit   
5.748, 0.129, 37537.1, 03_flat.fit 8.54, -0.72, 0.00, 03_flat.fit   
5.989, 0.148, 36169.7, 04_flat.fit 11.09, 0.38, 360.00, 04_flat.fit   
6.333, 0.154, 35987.3, 05_flat.fit 17.62, -0.29, 0.00, 05_flat.fit   
6.024, 0.047, 35652.1, 06_flat.fit 24.04, -1.22, 360.00, 06_flat.fit   
6.555, 0.168, 33000.9, 07_flat.fit 30.61, -0.89, 360.00， 07_flat.fit   
6.398, 0.148, 33755.1, 08_flat.fit 38.01, -0.99, 0.00, 08_flat.fit   
6.048, 0.106, 34309.1, 09_flat.fit 43.28, -2.31, 360.00, 09_flat.fit   
6.016, 0.064, 34107.5, 10_flat.fit 49.58, -3.45, 0.00, 10_flat.fit   
6.365, 0.034， 31404.1, 11_flat.fit 55.66, -3.51, 0.00， 11_flat.fit   
6.536, 0.156, 32321.8, 12_flat.fit 62.98, -2.47, 0.00， 12_flat.fit   
6.138, 0.043, 31529.0, 13_flat.fit 80.15, -3.95, 0.00， 13_flat.fit   
6.852, 0.125, 27071.4, 14_flat.fit 96.39, -4.54, 0.00， 14_flat.fit   
7.047, 0.073, 26810.6, 15_flat.fit 102.40, -6.47, 0.00， 15_flat.fit   
6.715, 0.018, 26743.7, 16_flat.fit 109.59, -7.28, 0.00， 16_flat.fit   
7.007, 0.083, 22335.1, 17 flat.fit 113.86, -6.98, 0.00， 17_flat.fit

Fig.1Theleftandtherightpanel showthe qualityevaluation and image alignment fileexportedbyMaxImDLrespectively

结合Photutils 测光库和MaxImDL 软件，本节提出了由于星像半高全宽变化较大时部分图像中目标不能被检测的解决方法。此外，本节也提出了一种快速的本地星像匹配与统计方法，但要求观测过程中CCD 芯片不产生较大角度旋转。

# 3相对测光中的精度回报现象

受大气湍流的影响，CCD芯片中星像的位置与实际位置存在不同的偏差。由于视场内相近的两颗星受大气湍流的影响相似，星像的位置测量中存在精度回报效应，即星像之间角距离较小时相对位置测量有着更高的精度。在相对测光中，我们猜测在同一视场内受不同大气质量的影响，各星像存在不同程度的消光。若相近的两颗星受大气消光的程度相似，则它们也有较高的相对测光精度。在本节中，我们将统计M35星团的相对测光精度与相对距离的关系，探讨测光中的精度回报现象。

# 3.1观测资料选取

找到两颗相互靠近且光度不变的天体是探究该现象存在的最好方法。然而，我们很难找到角距离变化较大且光度不变的天体。对于太阳系小行星来说，虽然它能够与恒星相互靠近，但小行星受自转、相位、卫星等因素的影响也会发生光度的变化，不适合用于探究该现象的存在性问题。若以一般的恒星作为实验的观测资料，由于恒星之间的相对角距离几乎不变，找到测光精度与距离的关系是比较困难的。此外，也有不少恒星的亮度是变化的。在实验中，我们采用星团作为实验的观测资料。星团中大量的恒星让我们方便地统计出距离和测光精度的关系。此外，星团的统计能够反映该现象是普遍存在的，而不是只发生在某个天区或个别天体上。因此，使用星团能够较好地探究相对测光的精度回报现象。然而，星团中也有光度发生变化或受其他天体光度影响较大的恒星，我们在3.2节中详细讨论对于这些恒星的处理。

# 3.2资料处理与数据分析

使用了中国科学院云南天文台1m光学望远镜(详细参数如表1所示)拍摄的 M35 星团图像进行测光精度回报现象的探究。我们在不同的高度角对M35星团进行了观测，观测时望远镜的指向稳定，具体的观测资料情况如表2所示。

Tab.1 Specifications of the Telescope and CCD   

<html><body><table><tr><td>Item</td><td>Parameter</td></tr><tr><td>Focal Length</td><td>1330cm</td></tr><tr><td>Diameter of PrimaryMirror</td><td>101.6cm</td></tr><tr><td>CCDField ofView</td><td>16'×16'</td></tr><tr><td>Size of Pixel</td><td>15 μ ×15 μ</td></tr><tr><td>Size of CCD Array</td><td>4096×4112</td></tr><tr><td>Scale</td><td>~0.234*/px</td></tr></table></body></html>

表2观测资料概要

表1望远镜及CCD详细说明  
Tab.2 Observations Overview   

<html><body><table><tr><td>Date(y-m-d)</td><td>Frames/Filter</td><td>Altitude(° )</td><td>Exptime(s)</td><td>FWHM(px)</td></tr><tr><td>2020-12-08</td><td>16/I</td><td>83-89</td><td>40</td><td>5.5-6.5</td></tr><tr><td>2021-01-15</td><td>21/I</td><td>83-78</td><td>40</td><td>4.1-5.3</td></tr><tr><td>2021-01-15</td><td>20/I</td><td>50-43</td><td>50</td><td>4.6-6.0</td></tr><tr><td>2021-01-15</td><td>17/</td><td>36-31</td><td>50</td><td>5.7-7.0</td></tr></table></body></html>

对于观测资料的预处理，我们先使用MaxImDL软件做平场校正，用其图像的质量评估功能筛选出半高全宽较小(例如小于6px，即小于1.4 角秒)且圆度较好(例如小于0.2)的图像。表1中列出的图像帧数是经过质量评估筛选后的数量。在实际的测光中，我们要慎重使用该方法进行图像质量的筛选，因为该方法可能把关键的光变数据剔除。在本实验中，探究相对测光的精度回报现象的存在需要假定每颗恒星的光度都是不变，也需要尽可能地把光度发生变化的星像剔除，该方法能够有效地减少由于大气的不稳定、焦距等因素造成的影响。

我们使用孔径测光的方法进行实验探究。由于星团中恒星的星像比较密集，使用环形区域来估计各星像的背景值常常会受到附近星像的干扰。因此，本文在每幅图像的各星像中都采用一个固定的天空背景值。具体地，我们先对每幅图像背景像素剔除了3o，然后采用“3-2”公式(3倍中值-2倍均值)[进行天空背景值的估计。接着，我们使用 photutils 测光库中提供的函数进行搜星，结合MaxIm DL软件进行各星像光度的匹配和统计，具体见本文2.2节。因为我们需要假设每颗恒星在每组图像的光度都是不变的，故以相对测光仪器星等在每组图像的标准差进行衡量。由于暗星测光精度较低，我们选择信噪比较高的亮星来统计星像的相对测光精度与相对距离之间的关系。这些亮星分布在视场不同的位置，我们让这些亮星两两进行较差测光，统计每组图像中星像相对测光精度和与参考星相对像素距离之间的关系。这时，若每组图像中一共选择出n颗亮星，每颗被选择的亮星都会作为其他n-1颗星的参考星，一共有n(n-1)组测光精度与距离的关系。

![](images/089b82fabbd1c05f7ed586bfb0ef16aa2da0b1c3a3100b10ba2ba2782eeb8dc9.jpg)

图2左子图展示了2020年12月8日资料测光精度与相对距离之间的关系，统计了仪器星等为11-13的数据。相对像素距离采用公式 $\sqrt { \Delta \mathbf { x } ^ { 2 } + \Delta \mathbf { y } ^ { 2 } }$ ，其中 $\Delta \mathrm { x }$ 、△y为星像中心的像素坐标之差(下同)。右子图是使用“标准差均值剔除”方法(设置阈值为0.0055)后的结果，红色实线是使用幂函数拟合的结果。

Fig.2Theleft panelshowstherelationshipbetween therelative distance and photometric precisionof theobservations on December 8,2O2O,andthedataof instrumental magnituderange11-13arecounted.Therelative pixeldistanceadopts the formula $\sqrt { \Delta \mathbf { x } ^ { 2 } + \Delta \mathbf { y } ^ { 2 } }$ ，where $\Delta \mathbf { x }$ and $\Delta \mathrm { y }$ are the difference of pixel coordinates of star image center (same hereinafter). The right panel is theresultof using "standarddeviation mean elimination"method(threshold setas O.Oo55),andtheredsolid line is fitted by power function.

然而，以信噪比或星等作为标准筛选出来亮星的光度也不一定是稳定的。若某一恒星是变星、双星系统或受附近亮星光度影响较大时，该恒星的测光精度也会比较低，也不适合用于统计和分析相对测光的精度回报现象。因此，我们需要尽可能找出这些测量精度较低的星，并把它们剔除。我们知道，若一颗星的光度在一组图像中发生了较大的变化，它不管与哪颗参考星进行相对测光，都会有较低的精度(标准差数值较大)。本文提出了“标准差均值剔除”的方法来剔除测量精度较低的恒星。第一步，我们先计算出每颗恒星与视场中其他恒星的星等标准差，则每颗星都能找到n-1 组这样的标准差。第二步，求出每颗星对于n-1组标准差的均值。第三步，设定一个阈值(一般设置为星像精度集中的上方附近，如图2左子图所示)，把标准差的均值高于该阈值的星剔除。使用该方法能够有效地剔除精度不高的恒星，方便统计和探究测光精度回报现象的存在。下图展示了2020 年12月8日拍摄的M35 星团图像对于测光相对精度与像素距离之间的关系，其中采用了仪器星等为11-13的恒星。左边子图是剔除之前的结果，右边子图采用“标准差均值剔除”的方法，设置阈值为0.0055剔除后的结果，可以看到能够有效地剔除精度较差的星。

接着，我们使用同样的方法处理了2021年1月15日共3组在不同高度角拍摄的M35 星团资料，以探究大气质量对测光精度回报现象的影响，结果如图3-图5所示。

![](images/cbb90f7ba31242479c165c44010fb8e7a5766abbb37a88fbe290679fa09bd26a.jpg)  
图3左子图展示了2021年1月15日资料(高度角为 $3 6 { \sim } 3 1 ^ { \circ }$ ，仪器星等为 $1 2 - 1 4 \mathrm { m a g } )$ 测光精度与相对距离之间的关 系，其中剔除阈值设置为0.008，右子图是使用幂函数拟合后残差随相对像素距离之间的分布情况。 Fig.3The leftpanelshows therelationship between therelative distance and photometric precisionof the observations on January 15, 2O21 (the altitude is 36\~31 deg and instrumental magnitude is $1 2 - 1 4 \mathrm { m a g } ,$ ,in which the elimination threshold is set to O.OO8.The right panel shows the distribution of the residual fitted by power function.

![](images/8134655914efede661b29a7b365e122a4eefd19446c6524c158405299559a0de.jpg)

图4左子图展示了2021年1月15日资料(高度角为 $5 0 \sim 4 3 ^ { \circ }$ ，仪器星等为 $\left. 1 1 - 1 3 \mathrm { m a g } \right)$ 测光精度与相对距离之间的关系，其中剔除阈值设置为0.006，右子图是使用幂函数拟合后残差随相对像素距离之间的分布情况。Fig.4The leftpanelshows the relationship between the relative distance and photometric precision of the observations onJanuary 15,2021 (the altitude is $5 0 \sim 4 3$ deg and instrumental magnitude is $1 1 - 1 3 \mathrm { m a g }$ ), inwhich the elimination threshold isset to O.OO6.The right panel shows the distribution of the residual fitted by power function.

![](images/3a26ea4c78d6195c0206c72640b8221fbe9e56b343e32db0d233079f92d96670.jpg)  
图5左子图展示了2021年1月15日资料(高度角为 $8 3 { \sim } 7 8 ^ { \circ }$ ，仪器星等为 $1 1 - 1 3 \mathrm { m a g } ,$ 恒星相对像素距离与相对测光精度之间的关系，其中剔除阈值设置为0.005，右子图是使用幂函数拟合后残差随相对像素距离之间的分布情况。Fig.5Te left panel shows therelationship between therelative distanceand photometric precision of the observations onJanuary 15,2021 (the altitude is $8 3 \sim 7 8 \$ deg and instrumental magnitude is $1 1 - 1 3 \mathrm { m a g }$ ), in which the elimination threshold isset to O.Oo5.The right panel shows the distribution of the residual fitted by power function.

从上述结果我们可以发现在同一天的测光精度来看，目标的高度角越大，相对测光的精度越高。在天顶附近时，亮于13等的恒星测光精度可达0.002星等。当目标高度角较小时，相对测光的精度较低，且存在比较明显的测光精度回报现象。从图3中我们可以看到，相对测光的精度随相对像素距离的增加而降低，测光精度从0.003星等降低到0.006星等。

# 3.3精度回报现象讨论

星光经过不同质量的大气会受到不同的消光效应。因为相对角距离较小的两颗星经过大气的质量相似，所以做相对测光时存在精度回报现象。当目标高度角较低时，大气质量较大，相对测光的精度回报现象较为明显。

在地面观测中，通常我们会选择目标在天顶方向附近观测，以减少大气消光的影响。然而，有些目标经过子午线时仍然处于较低的高度角，此时使用相近的参考星进行相对测光会产生较大的收益。当天顶方向的大气质量较大时，可能也会存在较为明显的精度回报现象，使用相近的恒星作为参考星进行相对测光也许是一种较好的补救方法。测光精度回报现象的存在引导着我们应该尽可能寻找附近的孤立亮星作为参考星，当然我们也需要保证参考星的光度是稳定的。

# 4总结与展望

本文介绍了现有的测光工具与技术，提出了把MaxIm DL 软件与Python 语言中 photutils 库函数相结合的测光技术。通过该技术，我们能够方便地处理由于星像半高全宽有较大变化时导致部分图像目标不能被检测的问题，也能够快速地进行星像测光数据的匹配和统计。通过分析中国科学院云南天文台 $ { \mathrm { 1 m } }$ 光学望远镜在不同高度角拍摄的M35星团图像，本文发现了在目标高度角较低时有较为明显的测光精度回报现象。在后续的工作中，我们将结合位置测量和光度测量的精度回报现象，进一步探究天体中光度和位置变化的联系。

# Technology Research and Precision Premium in Relative Photometry Based on CCD Images

Guo Bifeng1,2,Peng Qingyu12\*,Shang Yijia12,，QinYonggui12,LinFurog, (1 Department of Computer Science,Jinan University,Guangzhou,51O632,China)

Sino-French JointLaboratory forAstrometry,Dynamicsand SpaceScience,Jinan University,Guangzhou,510632,Ch

Abstract: The changes ofcelestial bodies’light with time can reflect their physical properties,and precise photometry technology helps us analyze and explore the changes of light beter, which is of great significance to the studyofthe evolution ofcelestial bodies.This paper introduces the related photometry tools and technologies and suggests a method of photometry technology and its application by combining MaxIm DL with photutils. Besides,this paper puts forward a fast-matching solution of each star image's photometric data in continuous frames.By analyzing the images of M35 cluster taken by the 1m optical telescope of Yunnan Observatory, Chinese Academy of Sciences, we find there is a phenomenon of precision premium in relative photometry. Namely,two close stars have better measurement precision in relative photometry,and the significance of this phenomenon is related to the atmosphere mass. According to the phenomenon,this paper proposes some reference methods in high precision relative photometry.

Key Words: Relative Photometry; Precision Premium in Photometry; CCD Image Processing; photutils; MaxIm DL

# 参考文献

[1] DevogeleM.,TangaP.,BendjoyaPetal.,ShapeandspindeterinationofBarbarianasteroids[J].Astronomy&Astrophsics,7 607:A119.   
[2] VerbiscerlA.J.,PorterS.,BenechiS.D.,etal.,PhaseCurvesfromtheKuiperBelt:hotometricPropertiesofistantKuiperBelt Objects Observed by New Horizons[J]. The Astronomical Journal,2019,158(3):1-17.   
[3] 吴月承，张皓晶，余莲，徐小林.平谱射电类星体 3C 454.3 的中长周期光变特性研究[J].天文研究与技术,2020,17(1):1-7. WUYuecheng,ZHANG Haojing,YULian,etal.The MediumandLong PeriodLight Variation Characteristics ofFSRQ3C454.3[J] Astronomical Research and Technology,2020,17(1): 1-7.   
[4] Landolt A.U., UBVRI PHOTOMETRIC STANDARD STARS AROUND THE CELESTIAL EQUATOR: UPDATES AND ADDITIONS[J]. The Astronomical Journal, 2009,137:4186-4269.   
[5] Pascu.D.,Anappraisalofte USNOprogamofpotorapicastrometryofbghtplanetarysatelltes[C],Galaticndolaryste Optical Astrometry,1994:304-311.   
[6] MorgadoB.,Assin.Vieira-Martins,al,Astromtryofutualaproximatiosetwennaturasatelits.Aplctiotte Galilean moons[J],Monthly Notices of the Royal Astronomical Society,2016,460(4):4086-4097.   
[7] LinF.R.,PengJ.HZhengZ.J,etal.,Characterzationof theprecisiopremiuminastrometryJ].onthlyNoticsoftheRoyal Astronomical Society,2019,490(3):4382-4387.   
[8] LaherR.R.,GorjanV,RebullL.M.,al,AperturePhotometryoolJ],ublicationsof teAstronomicalSocietyofteacific 2012,124:737-763.   
[9] 郭碧峰，彭青玉，林孚荣,Astrometrica 与 MaxIm DL 在天体测量的应用与技术研究[J/OL],2020，天文研究与技术， https://doi.org/10.14005/j.cnki.issn1672-7673.20200701.001 GUO Bifeng,PENG Qingyu,LIN Furong, Applications and Technology Research for Astrometrica and MaxIm DL in Astrometry[J/OL],,AstronomicalReseach&Technology,hps:/oiorg/10.005/j.cnkisn67-767.01   
[10]DaCosta G.S.,BasicPhotometryTchniques[C],AstronomicalCCDobservingandreductiontechniques,992(23):90-104.