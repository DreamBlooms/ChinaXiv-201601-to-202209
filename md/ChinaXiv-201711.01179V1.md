# CN 53-1189/P ISSN 1672-7673

# 改进的帧差法在空间运动目标检测中的应用

王恩旺¹，王恩达²(1.中国科学院紫金山天文台，江苏 南京210008；2.楚雄师范学院信息科学与技术学院，云南 楚雄 675000)

摘要：针对空间运动目标检测易受光照、云层等因素的干扰，导致在没有出现运动目标的情况下，错误地判断为检测到运动目标，设计了一种改进的帧差算法，把帧差法和背景减除法相结合，周期性地把当前帧更新为背景帧。先对待检测图像进行二值化处理，有效消除了光照、云层等噪声因素，并且强化了空间目标的图像，然后通过帧差法检测出空间目标。实验表明，该方法有效降低了空间运动目标的误判率，改进的算法不需要把每一帧图像作为背景帧，提高了运行速度，也不需要对背景进行统计建模，简化了背景的建立过程，算法易于实现，操作简单，资金投入少，灵敏度高，具有较高的实用价值。

关键词：帧差法；空间目标；运动目标检测；二值图；背景减除法图分类号：P123 文献标识码：A 文章编号：1672-7673(2016)03-0333-07

光学观测是空间目标观测的重要手段，空间目标的自动检测和跟踪是空间目标检测的关键技术。运动目标检测的正确性直接关系到空间目标的自动识别、定位和编目精度以及望远镜的运行效率，通过自动检测，可以有效提高空间目标检测的效率，对空间目标检测和空间科学研究具有重大意义。帧差法可以用于空间运动目标的检测，是一种简单、易于实现的算法[1]，通过视频序列中前后两帧图像的像素值做差运算来判断是否出现运动物体。首先对第 $k$ 帧及第k-1帧图片进行平滑去噪，再做帧差法处理，用第 $k$ 帧图片减去第k-1帧图片，得到一个值，用这个值和预先设定的阈值 $\mathbf { \chi } _ { t }$ 进行比较，若该值大于t，表示检测到运动目标，若该值小于 $\mathbf { \Phi } _ { t }$ ，表示没有出现运动目标[2]。但帧差法受光照、云层等因素变化的影响，虽然没有出现运动目标，由于光照、云层等因素的变化，导致帧序列中图像像素值发生巨大变化，从而使得帧差值大于 $\mathbf { \chi } _ { t }$ ，这样会误判为出现了空间运动物体。

为了在一定程度上降低光照、云层等噪声因素对算法的影响，提高空间目标检测的精确度，研究结合opencv 技术、帧差法和背景减除法，设计了一种改进的帧差算法，在帧差运算前先把前景帧和背景帧二值化，然后再做帧差运算，降低噪声因素的影响，提高算法的正确性和可靠性，在此基础上，还实现了运动目标检测的自动报警和提示功能。

# 1运动目标检测

运动目标检测通常有3种方法：光流法、背景减除法和帧差法，它们各有优缺点。

光流法的主要任务是计算光流场，即在适应的平滑约束性条件下，根据图像序列的时空梯度估算运动物体场，通过分析运动物体的变化对运动目标和场景进行分割。光流法的优点在于光流不仅携带了物体的运动信息，而且还携带了有关景物三维结构的丰富信息，它能够在不知道场景的任何信息的情况下，检测出运动对象。光流法的缺点是计算方法相当复杂，计算量巨大，不能满足实时的要求[3]。

背景减除法是在检测场景确定后，建立一张场景的图片作为背景图，接下来使用当前所获得的图像和背景图对比，也就是用当前图像和背景图做减法运算，相减后结果接近0，说明当前图像和背景图像几乎一致，也就是没有运动目标进入；相减后结果很大，说明当前图和背景图差异很大，也就是有运动目标进入。背景减除法的优点是算法简单，易于实现，在背景已知的情况下，检测出的运动目标的位置精确，速度快，实时性好。背景减除法的缺点是容易受环境、光线、天气变化等影响，一旦实际背景有变化就会影响检测结果[4]。

帧差法是对相邻两帧的图像进行差分，并设定一个阈值，认为差分结果大于阈值的像素点就是运动目标。帧差法的缺点是对环境噪声较为敏感，阈值的选择相当关键，选择过低不足以抑制图像中的噪声，过高则忽略了图像中有用的变化。帧差法的优点在于算法简单、计算量小、实时性高，在目标检测中比较常用[5-9]。

# 1. 1 图像二值化

帧差法虽然容易实现，但容易受到光照、噪声等因素的干扰，使得在没有运动目标的情况下误判为出现运动目标，若将图像二值化，则能有效削弱噪声干扰，从而提高空间运动目标检测的准确度。

图像二值化就是把彩色图像、灰度图像等转换为只有两种像素值的黑白图像，即为二值图。这样有利于对图像做进一步处理，图像的集合性质只与像素值为0或255的点的位置有关，不再涉及像素的多级值，使处理变得简单，而且数据的处理和压缩量小。为了得到理想的二值图像，一般采用封闭、连通的边界定义不交叠的区域。所有灰度大于或等于阈值的像素被判定为属于特定物体，其灰度值为255,否则这些像素点被排除在物体区域以外，若灰度值为0，表示背景或者例外的物体区域[10-13]。

二值化方法如下：设 $y ( i , j )$ 为原图的像素值，二值化后的像素值为 $x ( i , j )$ ， $\mathbf { \chi } _ { t }$ 为给定的阈值。

$$
x ( i , j ) = \left\{ \begin{array} { c l } { { 2 5 5 } } & { { y ( i , j ) \geqslant t } } \\ { { 0 } } & { { y ( i , j ) < t } } \end{array} \right. .
$$

当原图像中像素点的值大于给定的阈值 $\mathbf { \chi } _ { t }$ 时，把这点的像素值设为255，若原图像中像素点的像素值小于给定的阈值 $\mathbf { \chi } _ { t }$ ，则把这点的像素值设为0。当点的像素值为255时，二值图中该点处的图像显示为白色，当点的像素值为0时，对应的二值图显示为黑色。相应地，在二值图中白色部分主要对应着图像的物体、形状、轮廓等，而黑色部分对应背景。

空间观测图像大部分为黑白图，主要体现为黑色的背景和白色的发光目标，针对这一特点，把观测图像二值化，可有效地增强图像的清晰度，阈值 $\mathbf { \chi } _ { t }$ 的选取比较关键。在不同的场景中，图像的像素值变化比较大，就需要使用不同的阈值，才能更加准确地分割出运动目标，比较理想的方式是采用自适应阈值法来满足不同的场景需求。考虑到空间运动目标的特性，也可以采用固定的阈值，经过试验，在空间运动目标检测中，二值化的阈值可以设置为128。

# 1. 2 算法实现

帧差法与背景减除法类似，事实上它们是同一种运动目标检测算法的两种不同的变体，它们的原理都是通过前景图像与背景图像作差运算，从而检测出运动目标。它们的优点是算法简单，易于实现，这个优点也使得它们具有较大的应用空间和较高的应用价值。

研究结合帧差法和背景减除法做了一点改变，没有把每一帧图像都设置为背景，而是间隔一段时间周期，把当前帧更新为背景帧，这样做的好处是提高了算法的运行速度，而且可以把进入场景后静止的物体快速降级为背景。同时，也没有对背景模型进行统计建模，更新周期到达时直接把当前帧更新为背景，大大简化了背景建模过程，其中背景更新周期选取是一个关键的技术问题，它决定着检测结果是否理想，如果背景更新过快，前后两次检测结果会叠加在一起，得到错误的运动目标轮廓图，背景更新太慢，检测结果会出现大量空洞，把背景更新周期设置为 $0 . 3 \mathrm { ~ s ~ }$ ，可以得到理想的检测结果，以下是实现原理。

设 $q ( i , j )$ 为前景帧中第 $k$ 个像素点的像素值, $b ( i , j )$ 为背景帧中第 $k$ 个像素点的像素值, $o ( i , j )$ 为运动目标第 $k$ 个像素点的像素值，width表示图像宽度，height表示图像高度， $s u m$ 为差的绝对值之和。

$$
o ( i , j ) = \mid q ( i , j ) - b ( i , j ) \mid ,
$$

$$
s u m = \sum _ { i = 1 } ^ { w i d t h } \sum _ { j = 1 } ^ { h e i g h t } o \left( i , j \right) .
$$

(2)式表示把前景图像第 $k$ 个像素点的值与背景图像中第 $k$ 个像素点的值作差，然后取绝对值。 (3)式中sum 表示各对像素点求差后的绝对值之和。

接下来用sum 和给定的阈值 $\mathbf { \chi } _ { t }$ 进行比较，有两种情况：

$$
\begin{array} { c } { { s u m \geqslant t , } } \\ { { s u m < t . } } \end{array}
$$

当sum的值大于或等于 $\mathbf { \chi } _ { t }$ ，表示检测到了运动目标；当sum的值小于 $\mathbf { \chi } _ { t }$ ，表示没有检测到运动目标。sum 值的选取取决于当前的观测场景，sum是图像检测结果中的像素值总和，不同的运动目标检测场景，对应着不同的图像，它们的像素值分布差异较大，检测结果中图像的像素值大小也就各不相同，所以要能准确地判断是否检测到运动目标，就需要选取一个恰当的阈值 $\mathbf { \chi } _ { t }$ 。

如果阈值 $\mathbf { \chi } _ { t }$ 选取过小，噪声或背景的像素值之和大于 $\mathbf { \chi } _ { t }$ ，这时即使没有运动目标出现，也错误地判断为检测到了运动目标；如果阈值 $\mathbf { \chi } _ { t }$ 选取过大，当出现运动目标时，sum仍然小于t，结果一直判断为没有检测到运动目标。观测的背景改变，前景发生较大变化，光照等发生变化，都需要调整阈值t，才能得到正确的判断结果。阈值的选取在不同设备、不同图像通道、不同噪声等情况下是不一样的，只能根据当前情况下的场景选取，所选取的阈值只能根据当前的场景进行多次试验获得。针对空间运动目标检测背景主要是天空，前景多为发光目标，空间运动目标的场景基本固定，所以阈值 $\mathbf { \chi } _ { t }$ 可以选取一个固定的值，空间运动目标多为星体，阈值选取 $\scriptstyle t = 5 0 0 0$ 为宜，当观测场景中出现的运动目标较少时选取一个恰当的阈值 $\mathbf { \chi } _ { t }$ ，如果观测视野中出现了较多运动目标，检测结果中图像的像素值必然大于t，这时能够正确判断已经检测到运动目标。

算法的实现过程描述如下：

（1)从CCD 像机中取得第1帧图像作为背景帧，把该帧图像二值化;（2)从CCD 像机中取得第2帧图像作为前景图像，把该帧图像二值化;(3)依次取出前景图中第 $k$ 个像素点的像素值 $q ( i , j )$ ，背景图中的第 $k$ 个像素点的像素值 $\textit { b }$ （i，j)，把这两个像素值相减后取绝对值，然后计算所有绝对值之和。如果绝对值之和大于阈值 $\mathbf { \chi } _ { t }$ ，则说明前两张图像差别较大，判断为出现了空间运动目标，同时给出报警信息；如果绝对值之和小于阈值（204号 $\mathbf { \Phi } _ { t }$ ，说明前后两张图像无显著变化，可判断为场景中没有出现运动物体；

(4)周期到达时，把当前帧更新为背景帧，取得下一帧图像作为前景帧，返回（3）。

# 2结果与分析

以中国科学院紫金山天文台姚安观测站篱笆2 号 $5 0 0 ~ \mathrm { m m }$ 口径的大视场 $( 2 . 1 ^ { \circ } \times 2 . 1 ^ { \circ }$ )望远镜作为实验仪器，采用数据引导捕获的方式对 $5 0 0 \mathrm { m m }$ 口径望远镜拍摄的视频素材做实验。CCD图像尺寸是$1 0 2 4 \times 2 0 2 4$ ，像素值为16位，空间运动目标的大小一般为8像素左右。空间运动目标大，所占的像素值就大，空间运动目标小，所占的像素值就小。

# 2.1光照变化对比实验

首先，检测前待检测图像不进行二值化，结合opencv技术，直接使用帧差算法，进行运动目标检测。实验结果如图1、图2，两图是连续两帧图像，因为图1和图2中都没有运动目标进入，所以它们的背景完全相同，但是图1中的光照较弱一些，图2中的光照相对较强。

从实验结果可以看出，图1和图2表示光照变化检测结果。图1光照较弱，图2光照较强，两帧图像之间光照发生了变化，虽然图1和图2中都没有出现运动目标，但光照变化引起了前后两帧图像的像素值发生变化，造成前后两帧图像差别较大，结果显示为检测到了运动目标。

![](images/97d09bb76dc6aec3431a2eaa0c7cc5717f35c28a8eb1a652ba71353d8b4a302d.jpg)  
图1光照弱 Fig.1Light is weak

![](images/e53af0ccfd53b346b25d41ca242f62292991ffec8240f93f4ed7608548077901.jpg)  
图2光照强 Fig.2Light is strong

接下来，仍然使用图1和图2连续的两帧图像，背景完全相同，没有运动目标进入。采用本文算法，在检测前，对图1和图2的检测图像做二值化处理，再使用改进的帧差算法检测运动目标，实验结果如图3和图4。

![](images/2249efc19818f824ff9f69d1b9bd26cc65a08bfab9642e2a2c240ead0e63984b.jpg)

![](images/437b7ff4c51377ac412643d3ddebe739380341d6a7e6eaf3a02d8a350863e373.jpg)  
图3光照弱 (算法改进后) Fig.3Light is weak   
图4光照强 (算法改进后) Fig.4Light is strong

图3和图4的实验为改进后的光照变化检测结果，在没有出现运动目标的情况下，虽然在原图中光照变化很强，检测结果提示没有发现运动目标，说明检测结果准确。

# 2.2 云层变化对比实验

首先，待检测图像不做二值化处理，结合opencv技术，直接使用改进的帧差算法，进行运动目标检测，实验结果如图5\~8。图5和图6是连续两帧图像，因为图5和图6中都没有运动目标进入，所以它们的背景完全相同，但是图5中的云层相对厚一些，图6中的云层相对较薄。

通过实验结果可以发现：在图5和图6中虽然没有出现运动目标，但由于受到云层变化的影响，却错误地判断为检测到了运动目标。

接下来，仍然使用图5和图6连续的两帧图像，它们的背景完全相同，没有运动目标进入。采用本文算法，在检测前对图5和图6的图像做二值化处理，再使用改进的帧差算法检测运动目标，实验结果如图7和图8。由图7、图8可以看出，算法改进以后，在没有出现运动目标的情况下，虽然云层变化很大，但没有检测到运动目标，达到了预期的效果。

# 2.3运动目标检测实验

从2.1节和2.2节实验可以看出，帧差算法相对容易，但帧差法在空间运动目标检测过程中容易受到光照、云层变化的影响，会得到错误的检测结果，在没有运动目标出现的情况下，也判断为检测到运动目标。研究结果表明：在检测之前，对待检测图像进行二值化处理，能有效地降低光照、云层

等噪声因素的干扰，更准确可靠地检测出空间运动目标。

![](images/e569bbd3a5a62e0d0d5b3040992932f464993a524109b1ec55bbf7899036530d.jpg)  
图5云层较厚Fig.5Thick clouds

![](images/6fb1abc246e30cec062b51b4658feb68c904adb98717a7f5bc7d1bf8f1a63199.jpg)  
图6云层较薄Fig.6Thin clouds

![](images/af7f704a232d7480a6b1eee8bd10f78e344b7a77309d85b04fe01542a9d39e83.jpg)  
图7云层较厚 (算法改进后) Fig.7Thick clouds

![](images/a1a338b070627fa7d1ea87a65f4c152b866f243bcdabc425a4ebea3e2b7fbe77.jpg)  
图8云层较薄(算法改进后)Fig.8Thin clouds

接下来使用本文的算法对空间运动目标进行检测，图9是原视频中连续的3帧图像，在原视频中，有空间运动目标从右下角往左上角方向运动，图10是检测前先对图9做二值化，然后再使用帧差算法对运动目标检测的结果。

实验结果表明，采用改进算法后，有效降低了光照、云层等噪声的影响，使用了恰当的阈值后能够完好地检测出空间运动目标，检测结果更加准确可靠。

![](images/c895ff14fae05b73d85a494adc2241d90bd47f7ae5ffd72d91ad69f7351643fd.jpg)  
图9原视频中的图像Fig.9The original Images

![](images/d0da6dd7c4aba8c4549c06243e79abb75f0ce4ca263bdad5dc086d52e6ff1bbd.jpg)  
图10二值化后的图像  
Fig.10Images after binarization processing

# 3结论

本文提出的方法有效可行，将二值化和新的帧差算法相结合，在一定程度上避免了光照和薄云层对空间运动目标自动检测的干扰，从而减少运动目标的误判，能够精确、灵敏地检测到空间运动目标，而且检测到运动目标时可以自动发出报警提示用户，为空间运动目标的跟踪提供了一种新的思路，为实现空间运动目标自适应跟踪提供了一种新的依据。

研究表明，通过二值化和新的帧差算法相结合，提高了望远镜对光照和云层干扰等方面的处理能力，为适用不同望远镜的自动跟踪、自动搜索、自动捕获提供更加有效可行的方法，特别是对定点捕获的光学望远镜阵和篱笆望远镜阵，在空间运动目标检测时能够发挥其优越性，实验验证效果明显。

# 参考文献：

[1] 余启明.基于背景减法和帧差法的运动目标检测算法研究［D].南昌：江西理工大学，2013.  
[2] 马驰，张红云，苗夺谦，等.改进的多阈值动态二值化算法［J].计算机工程，2006，32(6): $2 0 3 - 2 0 5 + 2 0 8$ ：Ma Chi, Zhang Hongyun，Miao Duoqian，et al. Improved multi-threshold and dynamic binarizationalgorithm[J].Computer Engineering，2006，32（6）: $2 0 3 - 2 0 5 + 2 0 8$   
[3] 于春雨.基于光流法火灾烟雾视频图像识别及多信息融合探测算法研究［D].合肥：中国科学技术大学，2010.  
[4] 张小骏，刘志镜，陈昆.一种基于曝光补偿与颜色信息融合的背景减除法［J].电子技术与软件工程，2014(21)：115-118.  
[5] 赵建.基于三帧差法的运动目标检测方法研究［D].西安：西安电子科技大学，2013.  
[6] Lin HH,Chuang JH,Liu TL. Regularized background adaptation:a novel learning rate controlscheme for Gaussian Mixture Modeling [J]. IEEE Transactions on Image Processing，2011，20(3):822-857.  
[7] 刘忠，仇朴章，邱耀辉，等．差分像运动视宁度测量实验［J].云南天文台台刊，1993(4)：22-30.Liu Zhong，Qiu Puzhang，Qiu Yaohui,et al. Experiments of the differential image motion methodfor measuring the seeing ［J]. Publications of Yunnan Observatory，1993(4）: 22-30.  
[8] 郑联慧，金振宇，向永源.绝对差分算法误差对测大气视宁度的影响分析［J].天文研究与技术—国家天文台台刊，2012，9(2)：157-161.Zheng Lianhui, Jin Zhenyu， Xiang Yongyuan. Analysis of effects of erors of the absolute differencealgorithm on day-time seeing measurement [J]. Astronomical Research & Technology-Publications of National Astronomical Observatories of China，2012,9(2）:157-161.  
[9] 周丹，金振宇，卢汝为，等.像运动法测量视宁度参数中曝光时间的重要性及其测定［J].云南天文台台刊，2002(1)：14-20.Zhou Dan，Jin Zhenyu，Lu Ruwei，et al. The importance of the exposure-time and itsmeasurement in the image motion method to measure the seeing parameter ［J]. Publications ofYunnan Observatory，2002(1）：14-20.  
［10］吴锐，黄剑华，唐降龙，等.基于灰度直方图和谱聚类的文本图像二值化方法［J].电子与信息学报，2009，31（10）：2460-2464.Wu Rui，Huang Jianhua，Tang Jianglong，et al. Method of text image binarization processingusing histogram and spectral clustering [J]. Journal of Electronic & Information Technology,2009，31(10):2460-2464.  
[11］孙少林，马志强，汤伟.灰度图像二值化算法研究［J].价值工程，2010(5)：142-143.Sun Shaolin，Ma Zhiqiang，Tang Wei. Research on gray-level image binarization algorithms [J].Value Engineering，2010(5）:142-143.  
[13] 张引.基于空间分布的最大类间方差牌照图像二值化算法［J].浙江大学学报：工学版，2001，35(3) : $2 7 2 - 2 7 5 + 2 8 0$ ：Zhang Yin.License plate binarization algorithm based on analysis of the spatial distribution andmaximum variance between clusters [J]. Journal of Zhejiang University:Engineering Science,2001，35(3) : $2 7 2 - 2 7 5 + 2 8 0$

# Application of an Improved Frame Difference Method in Space Moving Target Detection

Wang Enwang'，Wang Enda² (1.Purple Mountain Observatory，Chinese Academy of Sciences，Nanjing 210o08，China,Email: ewwang@pmo.ac.cn; 2.School of Informationand Science Technology，Chuxiong Normal University，Chuxiong 6750oo,China)

Abstract:Space moving targets are often mistakenly detected even when they do not appear because the detection process iseasily interfered by light，cloudsand other factors.In order to solve this problem，we propose an improved frame diference algorithm，which combines the frame diference method with the background subtraction method and updates the current frame as the background frame periodicaly，namely,it makes the binarization processing to the images to be detected at the first step.This process can ffctively eliminate such noise factors as light and clouds，and intensify the images of space targets，and then help the frame diference algorithm to detect space targets.According to the experiments，this method can efectively decrease the false detection rate of space moving targets. There is no need for the improved algorithm to put each updated frame as a background or make a statistical model of the background，so it improves the operating speed and simplifies the process of establishing the background.This algorithm is easy to implement and simple to operate. With low investment and high sensitivity it has great practical value.

Key words:The frame diference method； Space target；Moving target detection；Binarization； Backgroundsubtraction method