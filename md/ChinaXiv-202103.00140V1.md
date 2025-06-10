# W波段宽带正交模耦合器设计

谈超，李斌

（中国科学院上海天文台，上海200030）（中国科学院大学，北京100049）

摘要：W波段接收机系统能有效接收多条射电天文观测重要分子谱线信息，对于天文观测和科学研究有重要意义。W波段正交模耦合器（Ortho-mode Transducer）作为接收机系统实现极化分离的关键器件，其性能对接收机整体性能有重要影响。本文介绍了一款基于Boifot结构的W波段宽带正交模耦合器，并介绍了OMT的工作原理和设计流程。仿真结果表明，在70-116GHz频带内，OMT相对带宽达到 $4 9 . 4 \%$ ，回波损耗优于 $ { \cdot } 1 8 . 7  { \mathrm { d B } }$ ，交叉极化优于-55.8dB，端口隔离度优于-54dB。

关键词：正交模耦合器；宽带；Boifot结构；W波段

# 0引言1

W 波段覆盖了多条重要天文观测分子谱线，其中包括恒星形成区分子云气体含量第二的CO 及其同位素分子谱线，在此波段能有效地研究恒星形成区分子云的气体组成、分布结构及运动演化。因此W波段是研究银河系及河外星系内恒星形成机制的重要观测波段，是开展毫米波多分子谱线观测最为有效的研究途径，对于天文观测和科学研究有重要意义。

在射电天文接收机系统中，天体射电源发出的微弱信号由大口径天线收集，在天线焦点处通过与天线光路匹配的馈源馈入接收系统，经过90 度移相器进行圆极化转换，或者直接经过正交模耦合器将公共端口的二维电磁波正交分解为两路线极化信号，再由后级电路进行放大、滤波、变频和数字化处理[1]。正交模耦合器（Ortho-mode Transducer)，简称 OMT,是接收机前端的关键无源器件，将从公共通道输入的两路正交线极化信号分离到两路单一输出通道，并使两路输出通道匹配且保持较高的隔离度，宽带OMT 在卫星通信、军事雷达、射电天文上有着广阔的应用。

由于金属波导的传播特性，正交模耦合器的工作带宽是整个射电天文望远镜系统工作带宽的瓶颈[2。随着频率增加，OMT的尺寸也相应减小，加工装配误差对OMT 电磁性能恶化的影响愈发严重。因此，在扩展工作带宽提升频率的同时，如何降低加工装配误差对OMT性能恶化的影响，成为现阶段OMT研究的主要内容3]。本文介绍了一种宽带正交模耦合器，该OMT工作在W波段，结构紧凑易于加工，全频带电磁性能优异，能够降低加工装配误差对于OMT电磁性能的不利影响，最后用电磁仿真软件进行设计验证。

# 1OMT模型选择

OMT 的主要性能指标有工作带宽、回波损耗、插入损耗和端口隔离度等。OMT可以按照工作频带范围划分为窄带OMT和宽带OMT。带宽不同，OMT形式也各有不同。有针对低频宽带使用的四脊形的OMT、旋转节OMT，有适用于较高频率的 Boifot4结构 OMT、Turnstile[结构OMT等，这些正交模耦合器形式各异、各有优缺点，模型选择时需要综合考虑工作频率、工作带宽、加工装配复杂度等因素。虽然OMT形式各异，但核心设计思想一致：设计出只传输一个电磁波传播模式的结构迫使另一个模式的电磁波只能从其他路径传输。对于毫米波段宽带OMT 设计而言，由于OMT尺寸更小，加工装配误差带来的性能恶化更加严重，设计过程中更多考虑的是如何在保证一定的电磁性能指标前提下，尽可能的使工作带宽扩大、降低模型加工复杂度。

一些结构不对称的OMT在窄带有良好的性能，但是隔离度会相对较差。由于波导不连续性激励的高次模将会使OMT性能恶化，为了抑制高次模的产生，在宽带OMT设计中，主要采取对称结构形式。根据实际设计需求，初步选择基于Boifot、Turnstile 两款结构的OMT。基于 Turmstile 结构(如文[8]、文[9])的OMT适用于高频率、高带宽，其输入口可以直接与馈源相接不需要额外设计方-圆波导过渡。但考虑到其加工复杂、结构较Boifot结构OMT臃肿且插入损耗较高，而 Boifot 结构(如文[10])OMT结构紧凑、加工复杂度相对较小，插入损耗小，在较宽频带中有良好的电磁特性，最终本文选择基于Boifot结构的双脊波导OMT。其模型如图1所示：

![](images/34db563e68d87a71f861c59b40877e23b29ca782df4b5193bdc59cbbbbafed5b.jpg)  
图1Boifot结构OMT示意图  
Fig.1A schematic diagram of the OMT

# 2OMT设计

由于器件结构复杂，通过分析其工作原理，可以在设计过程中将该模型分为 Boifot 接头、E面转弯、Y型功率合成器三个独立部分进行预设计，每部分结构分别仿真优化，再整体仿真优化，可有效提高设计效率、缩短设计周期。

# 2.1Boifot接头设计

Boifot接头是OMT模型中核心部分，两路正交线极化信号从接头的公共方端口进入并被分离到其它端口，使得每个路径的端口仅含有一个主模。Boifot接头中的阶梯双脊结构对纵向电磁波信号（图1Pol.V）呈容性，能有效聚集纵向电磁波能量，防止纵向电磁波信号传播到阶梯双脊结构两侧，使得纵向电磁波信号传播模式从波导传播变为脊波导传播，后经E 面转弯由WR10标准矩波导输出。而横向电磁波信号（图 $1 \mathrm { P o l . H }$ 信号）经过阶梯双脊结构则在功率分配后分别在阶梯双脊两侧传输，后经Y型功率合成器合为一路由WR10 标准矩波导输出。

阶梯双脊结构对Boifot接头性能有重要影响，除了极化分离，阶梯双脊结构的阶梯过渡实现 $\mathrm { T E } _ { 1 0 }$ 模式（Pol.V）的阻抗匹配，双脊两侧切角实现 $\mathrm { T E } _ { 0 1 }$ 模式(Pol.H)的-3dB 信号到侧臂波导出口的匹配。在本文Boifot 接头设计中，没有采用宽度、高度均改变的阶梯双脊结构，而采用了宽度一致、单侧高度变化的阶梯双脊结构，既满足设计指标，也能有效的降低加工复杂度。经过软件建模仿真优化，Boifot接头模型示意图和回波损耗如图2、图3所示：

![](images/f08f2febede288855bbcd29e63d3a6b9e10b54e82085798f78a56ff0d09a1291.jpg)  
图2Boifot接头模型

![](images/6cbfb34b373af82155afbb3331f0bde32530373e9c70fe4f9e574e0367092329.jpg)  
Fig.2 The model of Boifot junction   
图3回波损耗  
Fig.3 Return loss

# 2.2E面转弯设计

E面转弯能把经Boifot接头分离的 $\mathrm { T E } _ { 1 0 }$ 模式信号匹配输出到WR10标准矩形波导。此结构核心设计是阻抗变换器的设计。

截面尺寸为 ${ \textbf { a } } \times { \textbf { b } }$ ，内填空气的矩波导阻抗计算公式如下[7：

$$
z _ { e } = \frac { b } { a } \times \frac { \sqrt { \frac { \mu } { \varepsilon } } } { \sqrt { 1 - \left( \frac { \lambda } { 2 a } \right) ^ { 2 } } } \# ( 1 )
$$

其中， $\mu$ 表示空气磁导率， $\varepsilon$ 表示空气介电常数， $\lambda$ 表示空气中电磁波波长。

采用切比雪夫阻抗变换可使E 面转弯在宽频带工作，增加阶梯数目可扩展带宽。利用上述公式计算波导阻抗，根据切比雪夫阻抗变换[12计算出各级变换阻抗值，再反推出各级阶梯截面尺寸，阶梯长度均选定为 $\lambda _ { g } / 4$ ，其中 $\lambda _ { g }$ 表示在中心频率下的波导波长。

经过前期计算和软件建模仿真优化，E面转弯模型示意图和回波损耗如图4、图5所示：

![](images/0229a6006256cf0d6e3ee7fce0beed08d7893008376c5606b820c716112788ce.jpg)  
Fig.4 The model of E-plane bend

![](images/533ec6aa0ec0d3523885c3f46fb20897de2a7357cde1b64180565ea16c197192.jpg)  
图4E面转弯  
图5回波损耗  
Fig.5Return loss

# 2.3Y型功率合成器设计

Y 型功率合成器将Boifot接头分离的两路横向电磁波 $\mathrm { T E } _ { 0 1 }$ 信号合成，并变换到WR10标准矩波导输出。其主要由90 度弯波导、阶梯阻抗变换器组成。此部分采用对称结构，能有效抑制由于非对称结构引起的高次模，在宽频带保持良好的驻波和隔离特性。本模型的弯波导采用90度圆弧弯形式，阶梯阻抗变换设计流程与前文E面转弯阶梯阻抗变换的设计流程一致。经过软件建模仿真优化，Y型功率合成器的结构图和回波损耗如下图所示：

![](images/41a37f766e6290b199029399e161babf614bbbf039bad113fb407b01997e93db.jpg)  
图6Y形功率合成器模型

![](images/c5b02cae0162d2fc44f69b2716b698ab742b926e4b3f7ccf92a7ebeaff6dcd46.jpg)  
Fig.6 The model of Y-junction combiner   
图7回波损耗Fig. 7 Return loss

# 3整体仿真分析

完成上述三个模块预设计后，将Boifot接头、E面转弯、Y型功率合成器合成建立完整OMT模型，进行整体仿真优化，最终得到仿真结果如下图所示：

![](images/51d22fdea9f6cff29f552c82445cd6da76a5a5e819314ad86ce5696eb60d737c.jpg)  
图8OMT回波损耗

![](images/269548551bfb0fc7fabf667d3c7fc3333f3e6e0e126a93d5f843306e12d2ede0.jpg)  
Fig.8 The return loss of OMT   
图9OMT端口隔离度、交叉极化  
Fig.9 The isolation and cross-polarization of OMT

由仿真结果可见，该款OMT电磁性能优异，满足设计要求：在70-116GHz频带内回波损耗基本上优于-20dB,端口隔离度、交叉极化优于-55dB。仿真结果在若干频率出现了毛刺，表明波导腔体可能在对应频率产生谐振。

# 4总结

本文介绍了正交模耦合器的原理以及应用背景，并叙述了正交模耦合器的设计流程，设计了一款基于Boifot结构的宽带正交模耦合器,该 OMT体积 $1 9 . 1 \mathrm { m m } \times 1 9 . 1 \mathrm { m m } \times 2 8 \mathrm { m m }$ 结构紧凑易于加工装配，在达到 $4 9 . 4 \%$ 的相对带宽前提下，在 70-116GHz 频带内拥有良好的电磁性能：全频带回波损耗优于-18.7dB，交叉极化优于-55.8dB，端口隔离度优于-54dB，电磁性能满足实际需求。采用了将OMT按功能分成三部分进行预设计，再将三部分结合进行整体仿真优化的方法，有效提高了设计效率，为以后的实际工程应用中提供了理论准备和技术积累。

# 参考文献：

[1]．贾茹，李斌.天马望远镜 Ka 波段宽带圆极化器研制[J].天文研究与技术，2017，14(4): 488-494. Jia Ru,Li Bin.Development of Ka-Band Wideband Circular Polarizer [J].Astronomical Research & Technology,2017,14(4):488-494.   
[2]．陈卯蒸，宁云炜，马军．基于 Tumstile 结构的超宽带正交模耦合器研究[J].无线电工程, 2016，46(10): 54-57. Chen Mao-zheng, Ning Yun-wei, Ma Jun. Study of a Turnstile Ultra Wideband Waveguide Ortho-mode Transducer [J]. Radio Engineering, 2016,46(1O):54-57.   
[3]．王涛，张文静．宽带正交模耦合器的设计 [J].无线电工程,2013，43(3)：40-43. Wang Tao, Zhang Wen-jing，Design on Wide Band Orthomode Transducer [J].Radio Engineering,2013,43(3): 40-43.   
[4]. Bofiot A M,Lier E,Schaug-Pettersen T.Simple and broadband orthomode transducer [J]. IEEE Proceedings,1990,137(6): 396－400.   
[5]. Yoji Aramaki, Naofumi Yoneda, Moriyasu Miyazaki, et al. Ultra-Thin Broadband OMT with Turnstile Junction [J]. IEEE MTT-S Digest, 2003:47-50.   
[6]．王海伦，李斌．K波段宽带圆极化器设计 [J]．天文研究与技术，2015,12(4):455-460. Wang Hai-lun， Li Bin. A design of a K-Band circular polarizer [J]. Astronomical Research & Technology, 2015,12(4) :455-460.   
[7].JUher, J Bornemann, U Rosenberg. Waveguide Components for Antenna Feed Systems: Theory and CAD [M]. Norwood: Artech House, 1993: 371-445.   
[8].Doug Henke, Stephane Claude.Design of a 7O-116 GHz W-Band Turnstile OMT [C] //Proceedings of the 44th European Microwave Conference, 2014.   
[9]. Giampaolo Pisano, Luca Pietranera, Kate Isaak, et al. A Broadband WR1O Turnstile Junction Orthomode Transducer [J]. IEEE Microwave and Wireless Components Letters, 2O07,17(4): 286-288.   
[10].Alvaro Gonzalez, Shin'ichiro Asayama. Double-RidgedWaveguide Orthomode Transducer (OMT) for the 67-116-GHz Band [J]. Infrared Milli Terahz Waves,2018,39: 727-737.   
[11].顾继慧．微波技术[M].北京：科学出版社,2007:153-155. Gu Ji-hui. Microwave Technology [M]. Beijing: Science Press, 2007: 153-155.   
[12].Dvid M Pozar. Microwave Engineering [M]. America: Wiley, 2011: 256-260.

# A Design of W-band Broadband Ortho-mode Transducer

Abstract: The W-band receiver system can effectively receive many important spectral lines for radio astronomy observations，which is of great significance for astronomical observations and scientific research.As a crucial component of the receiver system, the W-band ortho-mode transducer is important to achieve polarization separation and it has a considerable impact on the overall performance of the receiver system. We design a W-band broadband OMT based on the Boifot junction and introduce the working principle and designing process of OMT. The simulation results show that the relative bandwidth of OMT reaches $4 9 . 4 \%$ , the return loss is better than -18.7dB, the cross-polarization is better than $- 5 5 . 8 \mathrm { d B }$ ,and the port isolation is better than -54dB in the 70-116GHz band.

Key words : Ortho-mode Transducer; Broadband; Boifot junction; W-band