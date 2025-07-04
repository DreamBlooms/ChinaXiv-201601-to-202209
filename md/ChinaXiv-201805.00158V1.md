# 基于宽光谱条纹对比度的菲索型光干涉望远镜共相检测与控制方法

王蓓1²，陈欣扬¹，□立新¹，李可新¹，颜召军1(1.中国科学院上海天文台，上海200030；2.中国科学院大学，北京100049)

摘要：菲索型光干涉望远镜得到高分辨率成像的关键是需要消除各子镜之间相位平移误差。宽光谱条纹对比度检测法是一种检测相位平移误差的有效办法。基于物理光学基本原理，论证了平移误差与系统点扩展函数的关系，进而仿真了共相远场条纹像，分析了共相检测与控制过程和数据预处理的方法，提出了加权对比度的算法和共相维持的方法，最终得到了共相远场像，并与仿真结果进行了对比。结果表明，实验与仿真的共相远场像能量分布形态以及数值都比较接近，该方法可以实现对子镜之间相位平移误差的检测与控制。

关键字：共相检测；子镜拼接；相位平移误差；条纹对比度中图分类号：TH744,TH751 文献标识码：A 文章编号：1672-7673(2018)02

空间分辨率是评价天文望远镜观测能力的重要技术指标。空间分辨率越高，望远镜对目标细节的分辨能力越强，获取的信息越多山。在波长一定时，望远镜的分辨能力随主镜口径的增大而增加。但以现有的技术水平，存在镜面材料制备、加工检测、支撑结构和造价等多种限制，主镜口径不能一直增大[2]。目前国际上单块光学望远镜主镜最大直径约为 $8 . 4 \mathrm { m }$ ，想要制造更大口径的光学望远镜，可采用天文光干涉技术实现[3]。天文光干涉技术是指将多个小口径光学孔径（子镜或独立口径望远镜）按照一定的空间位置排列，形成多基线阵列，通过入射波的干涉获得天体的信息，其分辨率等效于直径相当于基线长度的一架单口径望远镜。根据基线形式不同，天文光干涉可分为长基线干涉和光学综合孔径两种形式。前者的基线长度远大于子孔径的口径，通过测量任意两个小孔径之间干涉产生的观察源的复可见度，由傅里叶逆变换重构源的强度分布；后者的基线长度与子孔径的口径相当，在空间频率充分覆盖的条件下，可直接获得高分辨率成像。子镜拼接是光学综合孔径望远镜的一种结构形式，具有中心遮挡小、成像终端可安装于独立的光学平台等优点，但同时存在检测与保持子镜间共相性的技术难点。各子镜产生的像场必须具有相同的相位，才能在爱里斑中心互相增强，从而获得高分辨图像[4]。在光学综合孔径望远镜系统中，共相误差对成像的影响十分明显。在实际应用中，要求共相精度至少为波长的1/10。

近年来，光干涉望远镜的高精度共相检测问题已经成为研究的热点，为了解决检测共相误差问题，各国科研人员做了大量的研究，并提出了很多有效的检测方法。例如：四棱锥波前检测法、色散条纹检测法、色散条纹哈特曼法、泽尼克相位对比度法以及差分电容位移传感器法[5等共相检测方法。其中条纹检测法是检测子镜之间相对光程差的一种有效方法。本文基于宽光谱条纹对比度法，以一套采用菲索型天文光干涉技术的由7块子镜组成的 $5 0 0 \mathrm { m m }$ 直径子镜拼接实验样机系统为实验对象，采用闭环控制机构和相位校正技术实现共相检测。该检测控制方法有优于1/10波长的检测精度，可为共相误差的检测与控制技术的进一步研究提供有益的参考。

1理论与仿真[Z]

平移误差是由各个子光束沿出瞳面的 $z$ 轴产生的光场差引起。当只考虑平移误差时，假设其中一束子光束的相位被延迟一个常数 $\scriptstyle a$ ，光瞳函数可以表示为在单色光照明的情况下，若子镜间存在平移误差，系统远场像强度为当光源为宽光谱光源时，系统远场像强度分布为各单色光成分远场强度的叠加，其中，为宽光谱光源的中心波长；为光源带宽； $f$ 为合成镜焦距； $a$ 为子镜半径。具体仿真参数如下：，, $f { = } I O O O \mathrm { m m }$ ,像元尺寸为3.45。当两个子镜间平移误差为0时，远场仿真条纹如图1。

![](images/598b145a100f15d293fef51ff938efd7f164f793424cd76686a665117c5a08bc.jpg)  
图1仿真条纹图  
Fig.1 Simulation fringe image

光的干涉现象表现为在干涉场中呈现稳定分布的明暗相间的干涉条纹，干涉条纹对比度可表示干涉条纹的清晰程度。条纹对比度表示为 $C = ( I _ { \mathrm { m a x } } I _ { \mathrm { m i n } } ) /$ $( I _ { \mathrm { m a x } } { + } I _ { \mathrm { m i n } } )$ ，其中， $I _ { \mathrm { m a x } }$ 和 $I _ { \mathrm { m i n } }$ 分别为中央亮条纹的峰值和相邻暗区的波谷值。得到对比度与光程差的关系近似为

其中，为光程差； $k = 2 \pi / \lambda$ 为波数；。说明光源的光谱宽度和光程差直接影响干涉条纹对比度。

当光源的光谱宽度为时，在干涉中范围内的每一种波长的光都产生各自的一组干涉条纹，并且各组条纹除零干涉级外，互相间均有位移，其相对位移量随干涉光束间光程差的增大而增大，所以干涉条纹对比度随着光程差的增大而下降，最后将为0。因此光源的光谱宽度限制了干涉条纹的对比度。但是对于单色光源，光经过不同路径到达干涉场总是相干的。而对于宽光谱光源，只有相位差为0时，才能保证对比度为1，一旦相位差不为0，其可见度下降。所以需要使用宽光谱光源实现共相检测。在选择光源光谱宽度时，需要考虑光的相干长度(和对比度相对于光程差变化的灵敏度。图2为当光谱宽度为 $1 0 0 \mathrm { n m }$ 和$8 0 \mathrm { n m }$ 时对比度与光程差的曲线关系，相干长度分别为 $L _ { 1 }$ 和 $L _ { 2 }$ ，在相干长度范围内，随着光程差的增大，对比度与光程差近似呈抛物线关系。随着带宽的减小，相干长度增大，即测量范围增大，但对比度与光程差的曲线斜率减小，即灵敏度变低。随着带宽的增大，虽然灵敏度变高，但测量范围减小。所以需要根据实验需求确定合适的带宽。

![](images/5c186bcd0b9e56793cbfc501a18c0d807ae6ec18eff958bd40c0fb22b2063464.jpg)  
图2对比度与光程差的关系

2实验验证

# 2.1实验装置

实验使用的样机主镜采用抛物面型，由中心1块环形子镜（基准）和外围6块均布的离轴子镜组成，面型精度均方根优于 $1 / 4 0 \lambda$ ，材料为微晶玻璃。子镜直径 $1 5 0 \mathrm { m m }$ ，环形子镜内径 $6 0 \mathrm { m m }$ ，子镜间距 $1 5 \mathrm { m m }$ ，主镜面填充因子 $\scriptstyle \mathtt { - 0 . 6 8 }$ 。实验样机的每套子镜均具备沿 $X$ 、Y、 $Z$ 轴平移和绕 $X$ 、Y、 $Z$ 轴旋转共6个自由度的调节功能，在每个子镜背面均布置了3个线性微位移促动器，用来推动钢丝改变子镜的法向位移和两维偏摆，以实现平移误差和倾斜误差的校正。7块分离子镜以及子镜调节机构均安装于主镜机架上（见图3）。实验中采用了宽光谱光源，中心波长为 $6 0 0 \mathrm { n m }$ ，带宽为 $1 0 0 \mathrm { n m }$ ，相干长度为36。

![](images/d42a4b7c0249798f9129be681dba7d420472117d7093502cbc2466e80a9eef69.jpg)  
Fig.2 The relationship between contrast and optical path difference   
图3子镜机架结构  
Fig.3 Sub-mirrors rack construction

2.2实验步骤

实验第1阶段需要实现子镜的粗共相，利用干涉仪的波前检测和机械结构的调整，使6块离轴子镜均达到波前误差的最小值，此时子镜之间的平移误差可减小到数十微米。接下来依次对两两子镜进行共相精调，校正平移误差和倾斜误差。倾斜误差可通过检测离焦面像斑的几何偏移量进行闭环校正[4]。对于平移误差的校正，当平移误差较大时，可以先通过光栅色散干涉条纹法判断平移误差偏离的方向，手动调整使误差逐渐减小，直到干涉条纹较为稀疏，肉眼难以判断色散干涉条纹的方向，此时平移误差范围已缩小到5以内[8]。由于实验中平台抖动和实验环境对光栅色散干涉条纹法精确的检测共相影响较大，所以采用宽光谱条纹对比度法实现共相精调。利用步长为 $2 0 \mathrm { n m }$ 的方式改变子镜的轴向位移，采集多组远场条纹数据，以对比度为评价指标，通过拟合对比度测量数据，获得对比度与子镜轴向位置的相关曲线，峰值所对应的位置即为两子镜共相位置的最佳估计，从而实现全部子镜均共相。

# 2.3数据预处理

在获得两两子镜干涉的远场条纹像后，为防止CCD相机噪声等影响，需要先对图像进行均值滤波处理，消除图像中尖锐的部分。由于子镜的空间位置排布使干涉条纹具有一定的方向性，需要先利用傅里叶变换和图像二值化阈值遍历的方法精确计算出条纹倾斜角度，才能沿条纹法线方向进行采样，计算得到准确的条纹对比度9。接下来以图像中最亮点为中心沿条纹法线方向采样，得到该方向的条纹数据，如图4。曲线的主峰即为波峰，主峰与相邻次峰之间的极小值位置即为波谷，之后通过对比度计算公式可得到干涉条纹的对比度值。通过步进扫描方法，得到子镜不同轴向位置对比度的数据，根据对比度与光程差间近似抛物线的关系，利用高斯拟合方法对已获取的离散数据进行处理，得到对比度与子镜轴向位置关系的连续曲线，再对曲线进行三次样条插值，即可得到共相位置的最佳估计值。

![](images/5578d9e4e6534ec30b70722c646b979085c4e1f0870f8776ba0b5e4a273c6ff1.jpg)  
图4条纹采样数据  
Fig.4 Sampled data of fringe

# 2.4加权对比度算法

由于实验中采用经典对比度算法运算时，相邻暗区的波谷值采用的总是峰值某一侧的值，得到的干涉条纹对比度离散数据出现数据分层、不连续的现象（图5(a)）。现提出一种新的对比度算法，根据峰值左右区间波谷值分别计算左右条纹对比度 $C _ { I }$ 和 $C _ { 2 }$ ，建立加权平均对比度指标 $C { = } C _ { I } / C _ { 2 } { ^ * } ( C _ { I } { + } C _ { 2 } ) / 2$ ，得到对比度与共相位置关系的离散数据（图5(b)）。对比左右两图中的离散数据可知，使用加权对比度算法，数据相对连续。再对两组离散数据进行高斯拟合，得到的加权对比度误差的均方根值为0.037417，而经典对比度的均方根值为0.049089。可见使用新的对比度算法更为准确、稳定。

![](images/9a2c12bdbdcd29e89f2b7a1f7d497250f487914bf33ebed19eef4bcb8e4d714b.jpg)  
图5 (a)使用经典对比度算法的拟合曲线图 (b)使用加权对比度算法的拟合曲线图

# 2.5共相维持

由于实验中用到平行光管体积较大，独立安装于另一个光学平台上，平台本身的抖动影响共相位置的保持，再加上周围环境的影响，随着时间的变化，泊松点不能一直保持在原来的位置，共相位置将发生漂移，此时需要及时做出调整。将步进扫描的拟合数据作为查找表，当条纹对比度小于0.75时，通过查表找到对应的泊松的变化值实时调整，直至对比度达到要求为止。图6(a)和图6(b)分别为 $2 5 \mathrm { m i n }$ 内在得到的共相位置处未开启共相维持校正和开启共相维持校正的对比度实时变化数据（采样频率 $8 \mathrm { H z }$ ），图6(a)对比度随时间变化明显减小，说明此时共相位置已经发生了变化。图6(b)25min内对比度数据虽然有波动，但均能被及时校正，并且平均值一直保持在0.8以上。

![](images/9d86184fd31413e82f7e576e18f566618afe888b60d048b600bbe7585b80e297.jpg)  
Fig.5 (a)Fiting curve based on classical contrast method; (b)Fiting curve based on weighted contrast methoc   
图6(a)未共相维持校正  
Fig.6 (a) With co-phasing maintaining; (b) Without co-phasing maintaining

# 3结果分析

经过共相粗调和精调后，远场准直光经过实验样机光学系统后得到的远场像如图7 (b）。其中图7(a)为非共相远场像，图7(c)为仿真图像。对比(b)、(c)两图可知，二者能量分布形态相似，而非共相远场像与实验共相及仿真结果能量分布形态差别较大。参照单口径望远镜以半高全宽 (FWHM)作为星像质量的判据，由仿真远场像计算的半高全宽约为 $2 6 . 2 6 "$ ，由实验远场像测量的半高全宽约为 $2 7 . 7 3 ^ { \prime \prime }$ ，而非共相远场像的半高全宽约为 $1 2 4 . 1 5 ^ { \prime \prime }$ 。可以看出实测共相结果与非共相结果差距较大，并与仿真结果极为接近。

![](images/4cccc6752e9796bf99b938f74913acc4bcf3bba9aac557172b3f13463d291f63.jpg)  
Fig.7 (a) Non-co-phasing far field image; (b) Co-phasing far field experiment image ; (c) Co-phasing simulated image

4结论

本文开展了菲索型光干涉望远镜分离子镜间平移误差共相检测与控制方法的研究，以粗共相与精共相结合的方法，实现了6块分离子镜均共相，完善了宽光谱条纹对比度共相检测方法。结果表明，基于该方法可以实现对子镜间的相位平移误差的直接检测和校正。

# 参考文献

[1]刘丽,江月松.综合镜成像原理与应用[M].北京:国防工业出版社,2013. [2]王珊珊,朱秋冬,曹根瑞.空间拼接主镜望远镜共相位检测方法[J].光学学报, 2009,29(9): 2435-2440. Wang Shanshan, Zhu Qiudong, Cao Genrui. Cophasing methods of segmented space telescope [J]. Acta Optica Sinica,2009,29(9):2435-2440. [3]白静，姜爱民，戴妍峰.Golay3型光学稀疏孔径系统退化图像的频率信息提取及合 成研究[J].天文研究与技术,2016,13(3):351-357. Bai Jing, Jiang Aimin, Dai Yanfeng. Frequency extraction and degraded image synthesis   
for Golay3 type optical sparse-aperture systems[J]. Astronomical Research & Technology, 2016,   
13 (3): 351-357. [4] 陈欣扬,颜召军,郑立新,等.子孔径拼接实验样机研制及共相检测方法研究进展 [J].天文学进展,2016,34:115-120. Chen Xinyang, Yan Zhaojun, Zheng Lixin, et al. Progress on the research of segmented sub-aperture experiment prototype and co-phasing sensing method [J]. Progress in Astronomy, 2016,34: 115-120. [5] Acton D S,Bouchez A. Phasing metrology system for the GMT[C]//Proceedings of the   
SPIE.2012. [6] Pizarro C, Arasa J, Laguarta F, et al. Design of an interferometric system for the measurement of phasing errors in segmented mirrors [J]. Applied Optics, 2002, 41(22): 4562-4570. [7]石顺祥.物理光学与应用光学[M].陕西:西安电子科技大学出版社,2008:

102-103.

[8]王超燕,陈欣扬,郑立新,等.一种基于傅里叶变换和图像二值化阈值遍历的干涉 条纹角度计算方法[J].天文研究与技术,2017,14(3):369-375. Wang Chaoyan, Chen Xinyang, Zheng Lixin,et al. A method for calculating the angle of interference fringes based on fourier transform and threshold traversal of binary image [J]. Astronomical Research & Technology, 2017, 14(3): 369-375   
[9]颜召军,陈欣扬,杨朋千,等.基于光栅色散干涉条纹的菲佐光干涉望远镜共相检 测方法研究[J].物理学报,2015,64(14):417-425. Yan Zhaojun, Chen Xinyang, Yang Pengqian, et al. Co-phasing detecting method based on grating dispersed fringe for Fizeau optical interferometric telescope [J].Acta Physica Ainica, 2015, 64(14): 417-425.

# Co-phasing Detection and Control Method Base on Broadband Spectrum Fringe Contrast for Fizeau Optical Interferometric Telescope

Wang Bei'², Chen Xinyang1, Zheng Lixin1,Li Kexin1, Yan Zhaojunl (1.Shanghai Astronomical Observatory, Chinese Academy of Sciences, Shanghai 2ooo3o,China; 2.University of Chinese Academy of Sciences,Beijing 10o049,China,Email: wb@shao.ac.cn)

Abstract: For Fizeau optical interferometric telescope, eliminating the relative phasing piston errors between sub-mirrors plays an important role in realizing high resolution imaging. The broadband spectrum fringe contrast detection method is effective to detect the relative phasing piston errors.In this paper, we analyze the relationship between piston errors and point spread function of system based on physical principles,and simulate the images of co-phasing far field fringe. Furthermore, we describe the experimental process of co-phasing detection and control, and the data preparation method. Besides we provide an algorithm of weighted contrast and a solution of maintaining co-phasing. Finally, co-phasing far field images are got and compared with simulation image. The experimental results show that power distribution and FWHM values of these two images are pretty close, and detection and control of phasing piston errors can be realized using this method.

Key Words: Co-phasing detection; Segmented sub-mirrors; Phasing piston errors; Fringe contrast