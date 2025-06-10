# 弱光条件下的高分辨光谱测量

蓝若明1,23，刘雪峰，姚旭日1，俞文凯4，翟光杰1\*（1.中国科学院 国家空间科学中心，复杂航天系统电子信息技术重点实验室，北京100190；2.中国科学院大学,北京100190；3.山东师范大学 物理与电子科学学院，山东 济南 250014；4.北京理工大学 物理学院，北京100081)

摘要：提出了一种基于数字微镜器件(DMD)和光电倍增管(PMT)的弱光高分辨光谱测量的新方法。首先，利用基于小尺寸狭缝的分光光路将被测光光谱成像到DMD上，然后DMD微镜阵列按列依次翻转将光谱分波段投射到PMT点探测器上，最终实现对光谱的分时扫描测量。进行了与CCD光谱仪的对比实验以及不同弱光条件下的测试实验，并对系统的信噪比（SNR)特性进行了实验测试。实验结果表明，光谱测量系统的谱分辨率高达 $\mathrm { 0 . 2 3 \ n m }$ ，灵敏度可达 $4 . 6 \ \mathrm { p W }$ 以下，系统的信噪比（SNR)特性比较理想。相对于传统的光谱测量方法，本文方法具有成本低、易于实现且性能稳定等优点，在弱光高分辨光谱测量领域具有较大的潜在应用价值。

关键词：光谱测量；弱光；高分辨；扫描方式中图分类号：TH741 文献标识码：A 文章编号：1005-0086(2015)11-2175-05

# High-resolution spectral measurement of low light based on DMD and PMT

LAN Ruo-ming1,23， LIU Xue-feng1 ， YAO Xu-Ri1,²，YU Wen-kai $^ { 1 , 2 }$ ， ZHAI Guang jiel \* (1.Key Laboratoryof Electronicsand Information Technology for Space Systems,National Space Science Center, Chinese Academyof Sciences,Beijing lool9o,China；2.Universityof Chinese Academyof Sciences,Beijing 100190, China；3.School of Physicsand Electronics,Shandong Normal University,Jinan 250ol4,China；4.Schoolof Physics,Beijing Institute of Technology,Beijing lOoo8l,China)

Abstract:In this paper,in order to realize the high-resolution spectral measurement of low light,we propose a new spectral measurement method which is based on a digital micro-mirror device(DMD）and a photoelectric multiplier tube (PMT).Firstly,the spectrum of the measured light is imaged on a DMD by the dispersive optics system based on a smal-size slit.Secondly,by the rotation of the micro-mirrors of the DMD per column,the spectrum is reflected to a PMT according to the different wavelengths.Lastly, the measurement of the spectrum is achieved through the scanning mode. The contrast experiments of our method and a charge-coupled device(CCD) spectrometer are performed,and the experiments for different low light conditions are also performed.At last,the signalto-noise ratio（SNR) experiment of the system is conducted. The results show that the spectral resolution is $0 . 2 3 ~ \mathrm { n m }$ ,the sensitivity of the spectral system is less than $4 . 6 ~ \mathrm { p W }$ ,and the SNR performance is also perfect.Compared with the conventional spectroscopy technique,this spectral measurement method has the merits of low price,easy imple mentation and stable performance.

Key words:spectral measurement；low light；high resolution；scanning mode

# 1引言

微型光谱仪一般基于Czerny-Turner光学结构[1\~3]，多采用电荷耦合元件（CCD)线阵探测器[3,4]，是一种结构简单、成本低和非常适合于可见光波段、强光条件下的光谱测量。在一些特殊的应用领域，例如利用荧光光谱进行文物和艺术品的质量评估、利用光谱法分析类天体性质或者进行大天区多目标观测8以及利用拉曼光谱进行生物化学成分分析[10～12],经常遇到光信号比较微弱的情况。

由于CCD探测器的灵敏度比较低，动态范围也比较窄，在弱光条件下，CCD光谱仪难以实现高分辨率测量。为了解决这个问题，Bendad等[13」以及WonJun等人[14]提出利用电子倍增CCD(EM-CCD)进行光谱测量。EMCCD具有很高的灵敏度，但因其工作一般需要制冷，所以结构复杂，且价格一般是普通CCD的10倍以上，且仅能用于可见光波段的光谱测量。Bendad等13还提出利用高灵敏的光电倍增管（PMT)阵列进行光谱测量，刘金涛等[15也提出该方法，但由于PMT阵列的规模有限（仅有32个单元），实现的光谱分辨率只有 $8 . 9 \ \mathrm { n m }$ 和 $1 0 . \ 0 \ \mathrm { n m }$ 。Kraft等[16]以及Luo Biao等人[17]，提出利用MEMS驱动的旋转光栅结合高灵敏单点探测器的方法进行光谱的扫描测量，但是该方法对于光栅旋转角度的控制精度要求很高，实际应用中不容易实现。

为了实现弱光条件下的高分辨光谱测量，本文提出了一种基于固定光栅的扫描光谱测量结构，利用数字微镜器件（DMD)[18,19]进行光谱信号扫描，仅使用一个高灵敏度的PMT点探测器进行光信号探测。与线阵探测器方式比较，点探测器的方式使系统成本大大降低；利用DMD进行光谱的空间分辨，打破了PMT阵列对于谱分辨率的限制；采用固定光栅的方式，使该结构易于实现且性能稳定。另外，点探测器的选择具有更多的灵活性，可以很容易的推广到可见光以外的其它波段。

# 2实验装置与理论计算

如图1所示，被测光经过狭缝和准直透镜L1后，投射到光栅上，由光栅分光后的光谱线经过后透镜L2成像到DMD上，DMD可对光谱信号进行空间调制。

实验装置中，DMD的微镜阵列规模是 $1 0 2 4 \times$ 768，微镜尺寸为 $1 3 . 6 8 ~ \mu \mathrm { m } \times 1 3 . 6 8 ~ \mu \mathrm { m }$ ，每个微镜可以单独控制旋转到 $+ 1 2 ^ { \circ }$ 方向或者 $- 1 2 ^ { \circ }$ 方向，两个方向的设计确保了控制的高精度，由于光谱为一维信号，将DMD一列视为一个单元，当一列旋转到 $+ 1 2 ^ { \circ }$ 方向（测量方向）、其它列旋转到一 $1 2 ^ { \circ }$ 方向时，一个波段的光谱信号被反射到收集透镜L3，经过汇聚后投射到PMT上，实现一次测量，通过1024个列（实验中只用了512列)的依次 $+ 1 2 ^ { \circ }$ 旋转，实现对整个谱线的扫描测量；PMT是滨松公司的H10682型光子计数探测器，其探测灵敏度达到光子计数水平，输出信号为光子计数脉冲，在 $6 0 0 ~ \mathrm { n m }$ 波长时的计数灵敏度高达 $2 . 0 \times 1 0 ^ { 5 } \ \mathrm { s } ^ { - 1 } \cdot \mathrm { p } \mathrm { W } ^ { - 1 }$ ，动态范围极宽，暗计数典型值为 $6 0 0 ~ \mathrm { { s } ^ { - 1 } }$ ，具有很强的抗噪能力；实验光源为$6 3 2 . 8 ~ \mathrm { n m }$ 的准单色光，通过卤素灯加滤光片得到；滤光片的中心波长 $\lambda _ { \mathrm { 0 } } = 6 3 2 . 8 \ \mathrm { n m }$ ，半高宽为 $1 \ \mathrm { n m }$ ；衰减片用于模拟弱光条件;狭缝的横向尺寸 $a = 2 5 \ \mu \mathrm { m }$ .准直透镜L1的焦距 $f _ { 1 } = 3 0 \ \mathrm { m m }$ ；后透镜L2的焦距$f _ { 2 } = 1 0 0 \ \mathrm { ~ m m }$ ;光栅采用 THORLABS公司的 GR-1850闪耀光栅，闪耀波长为 $5 0 0 ~ \mathrm { n m }$ ，闪耀角为$2 6 . 7 3 ^ { \circ }$ ，线数为 $1 8 0 0 \ \mathrm { l i n e / m m }$ ，光栅常数 $d = 5 5 5 . \ 6$ $\mathrm { n m }$ ，选择入射角 $i = { 6 0 } ^ { \circ }$ 。

![](images/c3f52f72360d7f1b2732fc5c6c71a5cf5b9d7604a19709c8c8ee85c1c4f2767e.jpg)  
图1基于DMD和PMT的光谱仪 Fig.1Spectrometer based on PMT and DMD

由光栅方程[18]可知， $6 3 2 . 8 ~ \mathrm { n m }$ 波长光的出射角$\theta { = } 1 5 . 8 4 ^ { \circ }$ 因此光谱仪的线分辨率是

$$
{ \frac { \mathrm { d } { \boldsymbol { l } } } { \mathrm { d } \lambda } } = { \frac { 1 } { d \mathrm { c o s } \theta } } \times { \frac { f _ { 2 } } { \mathrm { c o s } \sigma } } = 1 8 9 9 9 1
$$

式中， $\sigma$ 是成像面与高斯面的夹角，即DMD平面与后透镜平面的夹角，实验中 $\sigma$ 为 ${ 1 0 } ^ { \circ }$ 。

根据光学谱分辨率计算公式[21,22]

$$
\delta \lambda = \frac { a } { f _ { 1 } } \times d \mathrm { c o s } i
$$

可以算出，光谱实验装置的光学谱分辨率约为0.23$\mathrm { n m }$ ，基本满足高分辨率光谱测量的要求。

# 3实验结果

# 3.1基于 CCD 的光谱实验

为了进行性能对比，首先通过基于CCD的光谱实验分析了狭缝尺寸对光谱分辨率和光谱测量的影响。实验原理图如图2所示，分光光路与图1实验装置相同。此时，光谱线成像在CCD探测面上。实验中，CCD 探测面宽为1280 pixel。

![](images/5e858645aaefc82e6e5b56bd3f44a52a827956971923bd6e9f3eca3d80210320.jpg)  
图2基于CCD的光谱仪 Fig.2Spectrometer based on CCD

在光源未衰减和衰减到 $1 \%$ 的两种条件下，均采用宽为 $2 0 0 ~ \mu \mathrm { m }$ 和 $2 5 \ \mu \mathrm { m }$ 的狭缝进行对比实验，实验结果如图3所示。从图可以看出，狭缝尺寸为 $2 5 \ \mu \mathrm { m }$ 时，测量结果的谱分辨率提高了，但进入后续光路的光强降低了；当光源衰减到 $1 \%$ 时，且当狭缝尺寸为$2 5 \ \mu \mathrm { m }$ 时，光信号强度已经接近了CCD的灵敏度极限，光谱测量几乎无法完成；光源衰减到 $1 \%$ 且当狭缝尺寸为 $2 0 0 \ \mu \mathrm { m }$ 时，光谱虽然可以测量，但因为CCD的动态范围窄，导致光谱线不再平滑。

![](images/6b1c033f0aad62bca8cfe786e116cb3527679f8a6ddafe89bf246afc73d994fd.jpg)  
图3CCD测量的 $2 0 0 ~ \mu \mathrm { m }$ 和 $2 5 ~ { \mu \mathrm { m } }$ 狭缝对应光谱：(a)光源未衰减； (b)光源衰减到 $1 \%$ Fig.3Spectra of $2 0 0 ~ \mu \mathrm { m }$ and $2 5 ~ { \mu \mathrm { m } }$ slitsusing CCD:(a）Light is not weakened;（b）Light is weakened to $1 \%$ （204号

实验结果表明，因为CCD的探测灵敏度比较低，所以难以实现弱光下的高分辨率光谱测量。

# 3.2基于DMD 和 PMT 的光谱实验

实验中，狭缝尺寸为 $2 5 \ \mu \mathrm { m }$ ，选择PMT探测器的计数周期与CCD的曝光时间相同（ $\mathrm { { 1 0 ~ m s ) } }$ ，光源同样衰减到 $1 \%$ ，测到的光谱线如图4所示。与图3（b)中CCD 测得的谱线进行比较，由于PMT的高灵敏度，在相同光强条件下，可以实现CCD无法完成的弱光光谱探测；因为PMT的动态范围大，所以谱线平滑，此时的测量结果优于CCD测量时 $2 0 0 \ \mu \mathrm { m }$ 狭缝的结果。

![](images/557b6d3ea4a18fd5684ec31c8a4a00d55e91281088c9efb1c6c95a9dc13076cd.jpg)  
图4当光衰减到 $1 \%$ 时，PMT测量的 $2 5 ~ { \mu \mathrm { m } }$ 狭缝对应光谱 Fig.4Spectrum of $2 5 ~ { \mu \mathrm { m } }$ slit using PMT when the light is weakened to $1 \%$

在上述实验基础上，将光源进一步衰减到0.$1 \%$ ，测得的光谱线如图5所示。可以看出，光谱线依然清晰平滑，测量结果的信噪比（SNR）也很高。此时，PMT探测器在 $1 0 ~ \mathrm { m s }$ 内输出的总脉冲数可以通过对图5中的光谱线进行积分得到，即有

$$
P C = \sum _ { i = 1 } ^ { 5 1 2 } P C _ { i } = 9 2 3 4
$$

按PMT在 $6 0 0 ~ \mathrm { n m }$ 波长时的计数灵敏度换算，系统在 $6 3 2 . 8 \ \mathrm { n m }$ 波长时的灵敏度达到 $4 . 6 \mathrm { \ p W }$ 以下。可见，光谱测量方法具有极高的探测灵敏度。

由图4和5还可以看出，单色光的实测半高宽约为17个DMD微镜尺寸，按公式（1)换算成波长为$1 . 2 2 \ \mathrm { n m }$ ，与被测单色光的半高宽基本一致。

实验结果表明，相对于CCD光谱测量方法，基于DMD和PMT的光谱测量方法具有非常强的弱光高分辨光谱测量的能力。

![](images/84584b75daa5e1474759c35e17485e82b0ffcba2732b66f46b431fc20896dcfe.jpg)  
图5当光衰减到 $0 . 1 \%$ 时，PMT测量的 $2 5 ~ { \mu \mathrm { m } }$ 狭缝对应光谱 Fig.5Spectrum of $2 5 ~ { \mu \mathrm { m } }$ slit using PMT when the light is weakened to $0 . 1 \%$

# 3.3 SNR 比实验

定义SNR为谱线峰值与暗噪声（谱线外区域）标准差之比。在光源衰减到 $0 . 1 \%$ 时，依次选择PMT的计数周期为2、5、10、25和 $5 0 ~ \mathrm { m s }$ 进行光谱测量，SNR-计数周期关系曲线如图6所示。

![](images/12919e8d23e0aec643d602c46122856c6e64d10c6a0a8055b321da9158312e19.jpg)  
图6不同计数器周期对应的SNRFig.6SNRs of different count periods

从图6可以看出，随着计数周期的增长，SNR在增加，其关系符合一般规律“SNR随积分时间的增加而增大”。对于衰减到 $0 . 1 \%$ 的弱光（可探测功率<$4 . 6 ~ \mathrm { p W } ) , 2 ~ \mathrm { m s }$ 计数周期的SNR具有约1200的$S N R$ 。

因此，该光谱测量方式的SNR特性是比较理想的。

# 4结论

设计了基于DMD和PMT的光谱测量实验装置，理论计算了装置的谱分辨率高达 $0 . \ 2 3 \ \mathrm { n m }$ ，实验测得装置的灵敏度可达 $4 . 6 \mathrm { \ p W }$ 以下，能够满足弱光条件下高分辨光谱测量的要求。本文的光谱测量方法弥补了高灵敏探测器阵列成本高或空间分辨率低的缺陷，点探测器的设计易于由可见光扩张到红外等波段，固定光栅的设计降低了系统的复杂度易于实现且稳定，因而在弱光高分辨光谱测量领域具有较大的潜在应用价值。

# 参考文献：

[1] SUN Zhen-hua，YU Zhen-gang，HUANG Mei-zhen，et al. Optimal design of a portable Raman spectrometer and the prediminary applications[J].Journal of Optoelectronics· Laser,2015,26(6)：1132-1136. 孙振华，余镇岗，黄梅珍，等.小型化拉曼光谱仪的优化 设计及应用[J].光电子·激光，2015，26（6)：1132- 1136.   
[2] LIU Jian-peng,TANG Yi, HUANG Gang,et al. Degign method of optical system of improved Czerny-Turner imaging spectrometer[J]．Acta Optica Sinica，2013，32（3）： 0322007. 刘健鹏，唐义，黄刚，等.改进型Czerny-Turner成像光谱 仪光学系统设计方法[J].光学学报，2013，32（3）： 0322007.   
[3] TANG Yi,ZHENG Cheng,JIA Hui-ping,el al.Theoretical and experimental study on anamorphosis correction of Czerny-Turner imaging spectrometers[J].Applied $\mathsf { O p ^ { - } }$ tics,2015,52(9)2507-2513.   
[4] Ocaya R O.A linear CCD spectrometer based on FPGA for light-source characterization[J].Applied Mechanics and Materials,2015,763(6):120-125.   
[5] Hooke R,Pearson A,Hagan J O'.Autonomous portable solarultraviolet spectroradiometer(APSUS)-A new CCD spectrometer system for localized,reaFtime solar ultraviolet $( 2 8 0 - 4 0 0 ~ \mathsf { n m }$ ）radiation measruement[J].Photo chemistry and Photobiology,2014,90(4)903-910.   
[6]Lognoli D,Cecchi G,Mochi l,et al.Fluorescence lidar im aging of the cathedral and baptistery of Parma[J].Applied Physics B,2003,76(4) :457-465.   
[7]Comelli D,D'Andrea C,Valentini G,et al.Fluorescence lifetime imaging and spectroscopy as tools for nondestruc tive analysis of works of art[J]. Applied Optics,2004,43 (10)：2175-2183.   
[8]Telfer R C,Zheng W,Kriss G A,et al.The rest-frame extreme-ultra-violet spectral properties of quasi-stellarobjects[J].Astrophys,2002,565:773-785.   
[9]Cui X Q,Zhao Y H,Chu Y Q,et al. The large sky area multi-object fiber spectroscopic telescope（LAMOST） [J].Res Astron Astrophys,2012,12:1197-1242.   
[10]Efremov E V,Ariese F,Gooijer C.Achievements in resonance Raman spectroscopy:review of a technique with a distinct analytical chemistry polential[J]．Analytica Chemica Acta,2008,606(2):119-134.   
[11］Bell S E J，Sirimulhu N M S．Surface-enhanced Raman spectroscopy（SERS）for sub-micromolar detection of DNA/RNA mononucleolides[J].Journal of the American Chemical Society,2006,128(49):15580-15581.   
[12]PENG Yi-jie,LIU Mu-hua,ZHAO Jin-hui,et al. Detection of oxytetracycline residues in water based on surface-enhanced Raman spectroscopy[J].Journal of Optoelectronics $\cdot$ Laser,2015,26(4):740-745. 彭义杰，刘木华,赵进辉，等.基于表面增强拉曼光谱的 水中土霉素残留量的快速检测[J].光电子·激光， 2015,26(4):740-745.   
[13]Benda A, Kapusta P,Hof M,et al.Fluorescence spectral correlation spectroscopy（FSCS）for probes with highly overlapping emission spectra.Optics Express,2014,22 (3):2973-2988.   
[14] Jun W,Kim M S,Lee K,et al.JunAssessment of bacterial biofilm on stainless steel by hyperspectral fluorescence imaging[J].Sens.& Instrumen.Food Qual,20o9,3：41- 48.   
[15]LIU Jin-tao,ZHANG Kai-lin,LU Yuan,et al. The development of A 3D-LIF spectral system for on-line detection of phytoplankton[J].Acta Laser Biology Sinica，2014,23 (6)542-546. 刘金涛，张凯临，卢渊，等.用于浮游植物探测的三维激 光诱导荧光光谱系统[J].2014，23(6)：542-546.   
[16]Kraft M,Kenda A,Frank A,et al.Single-detector micro-electro-mechanical scanning grating spectrometer[J].Anal Bioanal Chem,2006,386:1259-1266.   
[17]BIAO Luo,WEN Zhi-yu. Design and experiment of spectrometer based on scanning micro-grating integrating with angle sensor[J]. Infrared Physics & Technology,2014, 62:29-33.   
[18]Radwell N,Mitchell K J,Gibson G M,et al. Single-pixel infrared and visible microscope[J].Optica,2014,1（5）： 285-288.   
[19]Wang C,Liu XF,Yu W K,et al.Compressed spectral imaging with a spectrometer[J].Opt.Commun,2015,352: 45-48.   
[20]ZHAO Kai-hua,ZHONG Xi-hua.Optics[M].Beijing: Peking University Press,2013,Volume Two,18-27. 赵凯华，钟锡华.光学[M].北京：北京大学出版社， 2013,下册,18-27.   
[21]LIN Zhong,FAN Shi-fu. Spectral instrument[M].Beijing: China Machine Press,1989,114-118. 林中，范世福.光谱仪器学[M.北京：机械工业出版社， 1989,114-118.   
[22]WU Guo-an.The design of spectral instrument[M].Beijing:Science Press,1978,11:69-123. 吴国安，光谱仪器设计[M].北京：科学出版社，1978， 69-123.

# 作者简介：

翟光杰( $( 1 9 6 4 - )$ ，男，安徽人，博士，研究员，主要从事APD单光子探测技术、极弱光探测技术和静电悬浮技术等方面的研究．