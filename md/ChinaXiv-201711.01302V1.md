# 一种基于傅里叶变换和图像二值化阈值遍历的干涉条纹角度计算方法

王超燕，陈欣扬，郑立新，李可新，蔡建清，丁媛媛（中国科学院上海天文台，上海200030)

摘要：消除综合孔径望远镜子孔径之间的相对光程差是实现高分辨率干涉成像的前提条件，条纹检测法是一种检测相对光程差的有效办法。因子孔径的空间位置排布使干涉条纹具有一定的方向性，若不能精确获知干涉条纹的角度，则无法沿条纹的法线方向行采样，进而无法根据对比度变化曲线的最大值获得子孔径之间的最小光程差位置。提出了一种基于傅里叶变换和图像二值化阈值遍历的获得干涉条纹角度的方法，首先介绍了算法的基本原理，其次通过对条纹角度为 $4 3 ^ { \circ }$ 的仿真数据进行算法验证得到的角度为 $4 3 . 0 0 7 8 ^ { \circ }$ ，与理论值的误差为 $0 . 0 1 8 \%$ ，证实了方法的可行性。最后对比了未旋转相机和旋转相机两种情况下的条纹对比度变化曲线，可知通过旋转相机使条纹转至相机靶面纵轴方向再进行采样的办法，更有利于精确得到相对光程差的最小位置。

关键词：傅里叶变换；阈值；干涉条纹；条纹角度；光程差中图分类号：TH744.3；TH751 文献标识码：A 文章编号：1672-7673(2017)03-0369-07

对空间目标高分辨率成像一直以来都是天文工作者不断努力的目标，在波长一定的条件下，望远镜的分辨率通常受限于系统的孔径大小，孔径越大分辨率越高[1]，但材料、工艺及成本的因素限制了系统孔径的增大[2-3]。综合孔径成像技术可以通过容易加工的小孔径合成大孔径系统，实现高分辨率成像，但前提条件是消除子孔径间的相对光程差。条纹检测法是检测综合孔径望远镜子孔径之间相对光程差的一种有效方法[4]。通常在利用相移法[5]得到综合孔径两孔径之间的干涉条纹后，需要对连续采集的多组条纹数据行采样，从而得到最小光程差的位置。但因为子孔径的空间排布并不是上下或左右并列排布，因而得到的条纹数据有一定角度。若得到条纹的角度，则可以沿干涉条纹的法线方向采样，获得对比度的变化曲线，从而根据对比度的峰值位置找到子孔径之间的最小相对光程差位置，最终实现综合孔径望远镜的高分辨率成像。

# 1仿真对象

将独立三孔径干涉条纹作为仿真对象，3个子孔径的空间位置呈等边三角形排列，如图1（a)，理论上，透射到光束合成镜入瞳面上的光束相对于透射到整个系统入瞳面上的光束是等比例复制的,但实际上由于剪切误差和放大率误差的原因，两者之间存在瞳映射误差，所以映射到合成镜入瞳面上的3个光斑不是等边三角形分布，其相对位置如图1（b）。

由图1(b)可以得到基线 $B _ { 1 3 }$ 与水平方向的夹角近似为 $- 4 7 ^ { \circ }$ （这里的负号表示与水平 $x$ 轴负方向的夹角；若为正，则是与正方向的夹角)，由于被基线切割，条纹与水平方向的夹角约为 $4 3 ^ { \circ }$ 。当单口径望远镜对无穷远处的点目标成像时，在系统的焦平面上接收到的是点目标的夫琅禾费衍射像，因此子孔径1和子孔径3对无穷远处的点目标成像时，在系统的焦平面上接收到的衍射光强可以分别表示为

$$
I _ { 1 } = \left| \frac { 2 \times J _ { 1 } \bigg ( \displaystyle \frac { \pi x D _ { 1 } } { \lambda f } \bigg ) } { \bigg ( \displaystyle \frac { \pi x D _ { 1 } } { \lambda f } \bigg ) } \right| ^ { 2 } \times \bigg ( \frac { \pi { D _ { 1 } } ^ { 2 } } { 4 \lambda f } \bigg ) ^ { 2 } ,
$$

$$
I _ { 3 } = \left| \frac { 2 \times J _ { 1 } \Bigg ( \displaystyle \frac { \pi x D _ { 3 } } { \lambda f } \Bigg ) } { \Bigg ( \displaystyle \frac { \pi x D _ { 3 } } { \lambda f } \Bigg ) } \right| ^ { 2 } \times \Bigg ( \displaystyle \frac { \pi { D _ { 3 } } ^ { 2 } } { 4 \lambda f } \Bigg ) ^ { 2 } .
$$

双孔径干涉实质上是在单孔径衍射的基础上叠加了一个与基线有关的余弦调制项，由此可以得到双孔径干涉条纹的计算公式：

$$
I _ { 1 3 } = \int _ { \stackrel { \lambda _ { 0 } - \Delta \lambda / 2 } { \lambda _ { 0 } - \Delta \lambda / 2 } } \{ I _ { 1 } + I _ { 3 } + 2 \sqrt { I _ { 1 } \times I _ { 3 } } \times \cos [ \frac { 2 \pi } { \lambda } \times ( \frac { x } { f } \times B _ { 1 3 } + \delta ) ] \} \mathrm { d } \lambda ,
$$

其中， $J _ { 1 }$ 为一阶一类贝塞尔函数； $x$ 为焦面位置坐标； $\lambda _ { 0 }$ 为光源中心波长； $\Delta \lambda$ 为光源带宽； $f$ 为合成镜焦距；δ为泊松误差。根据图1(b)可以计算3条基线长度的平均值 $B$ 约为 $1 6 ~ \mathrm { m m }$ ，具体仿真参数如下： $\lambda _ { 0 } = 6 0 0 \mathrm { n m }$ ， $\varDelta \lambda = 1 0 0 \mathrm { n m }$ ， $f = 1 \ 2 6 0 \ \mathrm { m m }$ ，像元尺寸 ${ \mathrm { P i x e l } } = 7 . 4 ~ { \mu \mathrm { m } }$ ，光斑大小 $D = 9 ~ \mathrm { m m }$ ， $\delta = 0$ ，仿真条纹如图2。

![](images/5fad97db09558f20caa502a5bbec7a67c8c6634115df5bba20ac30d7a4fa5252.jpg)  
图1（a）子孔径空间排布图；（b）合成镜入瞳面光束相对位置图Fig.1（a）Layout of sub-apertures；（b）Beam position at the entrance pupil of lens

# 2算法原理及仿真条纹计算

# 2.1Hough变换直线提取法计算条纹角度

Hough 变换直线提取是一种比较经典的算法[6]，采用证据收集的方式，遍历一幅图像上的所有直线的位置，哪条直线上的特征点最多，哪条直线就是期望得到的直线。利用此算法思想计算条纹角度的主要步骤是：先将条纹的灰度图像进行边缘提取，然后检测边缘提取图像的直线段，根据提取的直线得到条纹的斜率，从而得到条纹的角度。对图2的仿真条纹图进行Hough变换直线提取的结果如图3。

由于条纹的边缘并不完全是直线，对于比较细长的条纹，此方法尚可，若条纹比较宽、比较短，此方法的计算结果有很大偏差。此外，算法在边缘检测和直线提取时都需要用到阈值，阈值的选择对计算结果有很大影响。傅里叶变换计算条纹角度的方法不依赖于条纹的长度及宽度，同时只需在二值化时用到阈值，大大简化了算法对阈值的依赖程度。

![](images/dff3a25910b52cbb06fa2e13746809df6fe1ed33a1677bd69ef499c8fe11b9ac.jpg)  
图2仿真条纹图Fig.2Simulation fringe

![](images/62e6af883d061b4085a7899fd38f87dc6f28cbe983617780a56d9a86e7f63162.jpg)  
图3对仿真条纹图的霍夫变换直线提取

# 2.2傅里叶变换计算条纹角度

对于一个光学成像系统，通常用系统的点扩散函数（PointSpreadFunction，PSF)描述点目标在空间域的成像性能；在频率域则用系统的光学传递函数（Optical TransferFunction，OTF）描述[7]。傅里叶变换是将图像从空间域转换到频率域，建立点扩散函数与光学传递函数之间的联系。光学传递函数的模称为调制传递函数（Modulation TransferFunction,MTF)，整个系统的调制传递函数由子调制传递函数组成，子调制传递函数在频率域分布的角度方向由子孔径的排布决定，这意味着如果知道调制传递函数在频率域的位置分布，就能得到子孔径的空间位置排布[9]，从而得到基线方向以及条纹的角度。基于此理论，本文采用基于傅里叶变换求条纹角度的具体算法见图4。

把条纹图像的灰度数据通过傅里叶正变换转换成图像的频率分布，如图5（a)。根据傅里叶变换的性质，原来集中在图片中心的能量通过傅里叶变换后，能量将分布于图片的4个角，所以需要将分布于4个角的零频点通过对角变换移动到频谱中间。这里的对角变换并不是严格意义的关于图片中心的坐标及灰度值对调，而是将图片的分块区域对调，将傅里叶变换的图像以图像中心为原点等分成4份 $\textcircled{1}$ 、$\textcircled{2}$ 、 $\textcircled{3}$ 、 $\textcircled{4}$ ，通过将 $\textcircled{1}$ 和 $\textcircled{3}$ 、 $\textcircled{2}$ 和 $\textcircled{4}$ 进行区域对调，使频谱能量移动到图像中心，如图5（b）。

![](images/b754bf61c92e4806cc1ed154d08310067a58cf4a454f7489ca3834f2c19d328f.jpg)  
Fig.3Hough transform line extraction from simulation fringe   
图4傅里叶变换计算条纹角度算法流程图 Fig.4Flowchart of the algorithm for calculating fringe angle based onFourier transform

将光斑质心连线，由连线斜率计算条纹的角度。通过连通区域质心连线的方法求出3个光斑所在直线的斜率，求解质心的方法是：首先对图5(b)进行二值化，然后求出每个光斑的连通区域，计算每个连通区域的质心，二值化处理时需要选择合适的阈值。图5(c)是傅里叶对角变换图像的二值化图，为求连通区域做准备。图5(d)是二值化图中的3个连通区域，并用十字丝标记每个连通区域的质心位置，这里是以图像左上角的第1个点作为坐标原点。

根据斜率公式可得到两质心之间的斜率 $k _ { 1 }$ ， $k _ { 2 }$ ， $k _ { 3 }$ ，求出质心连线的斜率的平均值 $\stackrel { - } { k } = \frac { 1 } { 3 } ( k _ { 1 } + k _ { 2 } + k _ { 3 } )$ 所以条纹的斜率 $k { = } \frac { - 1 } { \bar { k } }$ 根据得到的斜率计算出条纹角度 $\theta$ 。

![](images/f10f8313a9e1ec76e8d88ada409e8ce77c3b37273966ceea676ffd507dae62d4.jpg)  
图5（a）傅里叶正变换；（b）对角变换；（c）二值化图；（d）边缘轮廓及质心图'ig.5（a）Fourier forward transform；（b）Diagonal transform；（c）Binary image；（d）Contour and centroid n

计算过程中发现阈值有合理范围，既不能过高，也不能太低，通过阈值遍历的方法解决阈值依赖的问题。以8位无符号数据为例，在阈值范围1\~255中计算条纹角度，找到合理的阈值范围，计算结果如图6。对合理阈值范围内的所有角度求平均值average_Ang $\mathrm { l e } = 4 3 . 0 0 7 8 ^ { \circ }$ ，与理论值 $4 3 ^ { \circ }$ 之间的误差 $\sigma = 0 . 0 1 8 \%$ 。

![](images/89ed13c2dead9f7d0443d81d733e42c6aad58ee0e49635179fab84de791f10c5.jpg)  
图6仿真数据和实验数据合理阈值范围图  
Fig.6Maps for reasonable threshold range of simulation data and experimental data

# 3实验干涉条纹算法验证

独立三孔径干涉实验的参数与仿真数据的参数基本一致，但因测量误差和瞳映射误差的原因，子孔径透射到合成镜上的光斑尺寸，以及基线的尺寸与仿真数据存在一定差异，实验采集的条纹如图7（a）。

按照2.2节中的算法得到如图6的合理阈值范围，对比上下两图可知实验数据和仿真数据的合理阈值范围的重叠区域是「50，64]，在此范围计算得到的角度的平均值为 $4 4 . 7 9 0 \ : 1 ^ { \circ }$ 。从实验和仿真的结果对比来看，两者的合理阈值范围并不完全一致，这是由于实验采用的光学器件以及整个光学系统会引人像差，以及采集条纹的相机存在噪声，而仿真所用的条纹图是理想的无像差、无噪声图像。

通过步进扫描法得到条纹数据，此时的条纹有一定角度，为了获得子孔径间的相对光程差的最小位置，需要沿条纹的法线方向行采样。在对行采样数据处理时，条纹的对比度作为评价条纹好坏的一个重要指标，其定义是

$$
\gamma = \frac { I _ { { { m a x } } } - I _ { { { m i n } } } } { I _ { { { m a x } } } + I _ { { { m i n } } } } \mathrm { ~ , ~ }
$$

其中， $I _ { \mathit { m a x } }$ 、 $I _ { \mathop { m i n } }$ 分别表示干涉条纹光强的最大值和最小值。为了方便对比结果，这里给出两种条纹,第1种是不经过相机旋转采集得到的条纹，如图7（a），根据计算得到的条纹角度 $4 4 . 7 9 0 1 ^ { \circ }$ ，沿条纹的法线方向 $\cdot - 4 5 . 2 0 9 9 ^ { \circ }$ )行采样，得到对比度的变换曲线如图7(b)，步进扫描的对比度的变化趋势并不明显，也无法从拟合曲线中找到最小光程差的位置。

![](images/a1636361b9b448ae165d02113b4dd51bd6ce838a3acaf4cdc31456ee5f6a2890.jpg)  
图7未旋转相机。（a）实验采集条纹图；（b）沿条纹法向行采样得到的对比度变化曲线 Fig.7Camera not rotate.（a）Fringe from experiment；（b）Thecontrast curve along the normal directionof the fring

另一种是相机旋转一定角度后采集的条纹，根据计算得到的条纹角度 $4 4 . 7 9 0 \ : 1 ^ { \circ }$ ，先将相机逆时针旋转 $4 5 . 2 0 9 9 ^ { \circ }$ ，使条纹竖直（即 $9 0 ^ { \circ }$ ），如图8(a)，然后沿条纹的法线方向 $\left( 0 ^ { \circ } \right) ^ { . }$ )行采样，得到对比度的变换曲线如图8（b）。

由图8(b)可知，条纹从模糊到清晰的变化趋势比较明显，且可以从拟合曲线中找到条纹最清晰的位置，也就是光程差最小时对应的促动器位置。但从图8（a)可以看出，采集的条纹质量不高，在步进扫描的过程中，两光斑在焦面位置会略微分开，导致看上去有两组条纹，这是由于在步进扫描的过程中引入倾斜误差。

通过实验可知，旋转相机后更容易根据条纹对比度的最大值找到最小光程差位置，这是由采集条纹图的相机本身属性决定的。相机采用 $2 0 4 8 \times 2 0 4 8$ 像素点组成的点阵，条纹图是用有限个像素点组成的点阵图。理想情况下，如果条纹水平或竖直，那么条纹像素点最大限度地分布在一条直线上。当条纹呈一定角度时，描述条纹的像素点实际上是直线附近像素点的近似取整。因此在计算未旋转相机之前的条纹对比度时，选择的光强最大值与最小值并不精确，从而导致对比度的计算不准确，这是旋转相机使条纹竖直后可以改善确定条纹对比度位置的物理原因。

![](images/9b5f98bf696f59dd5682a6de72a773441c9c2727561e18d5401cb62271ad35ee.jpg)  
图8相机旋转后。（a）实验采集条纹图；（b）沿条纹法向行采样得到的对比度变化曲线 Fig.8 Camera rotate.（a）Fringe from experiment；（b） Contrast curve along the normal direction of the fring

# 4结论

通过仿真数据可知，阈值不同得到的条纹角度也有微小差异，通过阈值遍历计算平均值的方法，得到的角度与理论角度更加接近。将此算法用到三孔径干涉实验，根据得到的条纹角度，指导相机的旋转角度，使条纹的角度沿竖直方向，便于条纹行采样，更容易、更精确得到对比度最大的位置，即最小光程差位置。

# 参考文献：

[1] 王姗姗，朱秋东，曹根瑞.空间拼接主镜望远镜共相位检测方法［J]．光学学报，2009，29 (9):2435-2440. Wang Shanshan， Zhu Qiudong，Cao Genrui. Cophasing methods of segmented space telescope [J].Acta Optica Sinica，2009，29(9）:2435-2440.   
[2] Wu Quanying，Wu Feng，Qian Lin，et al. Demonstration of the Golay3 multiple-mirror telescope with a spherical primary mirror [J]. Optics & Laser Technology，2012，44(4）: 749-755.   
[3] 高莉莉，刘忠，金振宇.综合孔径干涉望远镜的高分辨率图像重建［J]．天文研究与技术 -国家天文台台刊，2009，6(4)：327-333. Gao Lili，Liu Zhong，Jin Zhenyu. High-resolution reconstruction of images from an interferometry telescope ［J]. Astronomical Research & Technology———Publications of National Astronomical Observatories of China，2009，6(4):327-333.   
[4] Pizarro C，Arasa J,Laguarta F,et al. Design of an interferometric system for the measurement of phasing errors in segmented mirrors [J]. Applied Optics，2002，41(22）: 4562-4570.   
[5] Dong Jingtao，Lu Rongsheng. A five-point stencil based algorithm used for phase shifting lowcoherence interference microscopy [J]. Optics & Lasers in Engineering，2012，50(3）: 502- 511.   
[6] Zhao Yao,Pan Haibin，Du Changping，et al. Principal direction-based Hough transform for line detection ［J].Optical Review，2015，22(2）:224-231.   
[7] 刘丽，江月松.综合孔径成像原理与应用［M].北京：国防工业出版社，2013.   
[8] Lu Mingfeng， Zhang Feng，Tao Ran，et al. Parameter estimation of optical fringes with quadratic phase using the fractional Fourier transform [J]. Optics & Lasers in Engineering,2O15，74：1- 16.   
[9] 白静，姜爱民，戴妍峰.Golay3型光学稀疏孔径系统退化图像的频率信息提取及合成研究 [J]．天文研究与技术，2016，13(3)：351-357. Bai Jing， Jiang Aimin，Dai Yanfeng. Frequency extraction and degraded image synthesis for Golay3 type optical sparse-aperture systems [J]. Astronomical Research & Technology，2016, 13(3) : 351-357.

# A Method for Calculating the Angle of Interference Fringes Based on Fourier Transform and Threshold Traversal of Binary Image

Wang Chaoyan，Chen Xinyang，Zheng Lixin，Li Kexin，Cai Jianqing，Ding Yuanyuan Shanghai AstronomicalObservatory，Chinese Academyof Sciences，Shanghai 2Ooo3o,China,Email：superyan@shao.ac.cl

Abstract：Eliminating the relative Optical Path Diffrence （OPD）between two sub-apertures in synthetic aperture telescope isa precondition for high resolution image.The fringe detection method is efective to decrease the relative OPD.The fringe angle depends on the position distribution of sub-aperture.The precise angle of fringe is an essential prerequisite for taking line sample along the normal direction.And then，on the basis of the maximum contrast value，the position corresponding to the minimum OPD between two subaperture can be obtained.Here，a method for calculating the angle of interference fringes based on Fourier transformand threshold traversal of image binaryzation is proposed.Firstly,the basic principle of the algorithm is introduced.Secondly，with the data for fringe angle of 43 degrees as the simulation data to test this algorithm，the result of 43. OO7 8 degree is obtained. The value of error is $0 . 0 1 8 \%$ compared with theoretical simulation value.In the end，contrast curves from two cases of rotating camera and non-rotating camera are compared.It is more benefit to get the accurate minimum OPD by the method of rotating camera to make the fringe along the longitudinal axis of camera according to the angle of fringe.

Key Words:Fourier Transform； Threshold； Interference fringe；Fringe angle；Optical path diffrence