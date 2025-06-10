# 一种新型 Micro-CT系统设计

张志诚1,² 梁晓坤」朱轩玉1,3 李维振1,3 谢耀钦1（中国科学院深圳先进技术研究院生物医学健康与工程研究所深圳 518055)

（中国科学院大学深圳先进技术学院 深圳 518055)

（东北大学沈阳 110819)

摘要传统的CT 设备由于受到系统架构的物理限制，导致最终扫描结果中运动伪影影响很大，本文依据碳纳米管的场致发射原理设计出一套工作在准静态模式下的显微CT。该系统采用35个碳纳米管X射线光源和5个探测器。相对于传统CT，通过外部时序控制减少了机架的机械旋转次数和行程，大大降低了运动伪影的影响。由于重建角度是稀疏的，因此通过采用迭代重建算法模拟仿真验证了该系统的有效性。

关键词显微 CT；系统设计；迭代重建中图分类号 TG156 文献标志码A

# A Novel Design of Micro-CT System

ZHANG Zhicheng1,² LIANG Xiaokun1 ZHU Xuanyu1,³ LI Weizhen1,3 XIE Yaoqin' 1( Institute of Biomedical and Health Engineering, Shenzhen Institutes of Advanced Technology, Chinese Academy of Sciences, Shenzhen 518055, China ) 2( Shenzhen College of Advanced Technology, University of Chinese Academy of Sciences, Shenzhen 518055,China ） 3( Northeastern University, Shenyang 110819, China )

AbstractLimitedtothesystemarchitectureinconventionalCT,Artifacts inducedbyrespiratory motionduringroutinediagnosis severelydegrades the image quality.A novel micro-CTsystemperforming wellina quasi-static way is proposed acording tothe principle of field emission. It employs 35 carbon nanotubes based $\mathbf { x }$ -ray tubes and 5 flat detectors,motion artifacts can be greatly suppressed byreducing thegantryrotation timesandrangeunder thecontrolof theexternal sequential whencompared with conventionalCTsystem.Tovalidate the feasibilityoftheproposedsystem,iterativereconstructionalgorithmisadoptedon simulation due to sparse sampling .

Keywords Micro-CT,system design，iterative reconstruction

# 1引言

显微计算机断层成像设备（Micro-CT）作为一种非侵入式、无损的X射线三维成像设备，它能在有限的扫描视野内得到超高空间分辨率图像[12]，并被广泛应用于小动物成像以促进人类组织工程、疾病机理和药物评估的研究 $^ { [ 3 ] }$ 。小动物的生理运动比人类更加快速 $^ { [ 4 ] }$ ，对于传统的micro-CT,运动伪影对图像质量的影响将会更加突出，因此，如何减少运动伪影对实验结果的影响是micro-CT不可忽视一个重大问题。

传统的micro-CT 普遍采用含有阳极－阴极两级结构的X射线源，阳极为钼、钨等重金属靶材，用于接受高速电子轰击，阴极为直径很小的钨丝，用于发射电子，两者均被密封在高真空度的玻璃、金属或者陶瓷外壳内。当灯丝通入大电流的时候，灯丝表面温度会迅速升高，直至其表面温度超过2000K，灯丝会释放出自由电子，产生游离的电子云，电子云在阳极加速电压的作用下，加速轰击阳极靶材，产生X射线。根据上述“热阴极”电子发射的原理可知：传统的X射线光源无法在高压通断的瞬间启停X射线，这就造成了以“热阴极”电子发射为原理的成像设备如CT、断层合成成像等，在时间分辨率的方面有个天然的物理极限。近几年，随着碳纳米管新型材料的兴起，以碳纳米管为阴极材料的新型X射线源业已被研究人员开发出来。

采用场致发射的原理制成的冷阴极X射线源，在极小的发射阈值下，就能获得极其稳定的电子发射和更加绵长的使用寿命[6]。2002 年，北卡罗来纳州大学教堂山分校Yue 等小组利用碳纳米管场致发射原理，替换传统热阴极灯丝，研发出脉冲可控式X射线源，在此之后，他们研发出了基于碳纳米管的阵列式 断层合成成像、micro-CT 和环形放疗装置[-0]。基于碳纳米管的X射线源的特点如下1]：(1）基于碳纳米管的X射线源是利用电场产生游离的电子云，因此在工作的过程中，几乎不产生热量，这就解决了传统X射线光源无法小型化的弱点；(2）相同尺寸的碳纳米管的电子发射量与材料的表面电场强度成正比，因此，操作人员可以利用外部脉冲控制材料表面电场强度，从而控制X射线源的启停。

鉴于碳纳米管优异的特性，最近几年许多研究小组都利用碳纳米管X射线光源提出了自己的系统设计方案或制造出相关原型机。西门子Maltz 等[12]提出了一种放疗过程中适时引导的静态框架，该系统采用52 个冷阴极X射线光源。Qian 等通过脉冲控制阵列式碳纳米管X射线源的启停取代传统的单个X射线源的机械旋转，研发出了静态数字化乳腺 断层合成成像，大大提高了系统的时间分辨率，增强了系统的稳定性。清华大学的Li 等[13]在传统CT 的基础上，通过增加碳纳米管X射线源，减少机械转动，理论上获得了更快的扫描速度，在扫描过程中，为了围绕物体扫描 $3 6 0 ^ { \circ }$ ，该系统仍需要旋转数十次，但该系统相比较传统CT 而言，通过加快扫描速度大大地减少了运动伪影对图像质量的影响。

本文提出了一种基于碳纳米管的新型 micro-CT系统设计方案，该系统包含35个碳纳米管

X射线光源和5个平板探测器，且均匀分布在两个同心圆上。当35个碳纳米管X射线光源按照一定的时序激发后，机架将会两次旋转24°，每次旋转稳定后继续激发35个碳纳米管X射线光源，因此总共可获得105个投影。该系统采用迭代重建算法重建出最终结果。

本文结构如下：第二部分介绍场致发射原理和基于碳纳米管的新型micro-CT系统的设计方案，并介绍相应的迭代重建算法；第三部分给出了该系统的计算机仿真结果；第四部分和第五部分分别是讨论和结论。

# 2方法

# 2.1 Micro-CT 系统设计

2.1.1 场致发射

图1为基于场致发射的X射线源的原理图，如图所示，X射线源包含含有碳纳米管新型材料的阴极、聚焦电极、栅极和阳极四级结构。在保证真空度的前提下，给栅极施加一个受控的电压，当电压达到某一阈值时碳纳米管表面会释放出游离的自由电子，然后在阳极的加速电压作用下加速轰击阳极靶材产生X射线。其中通过控制聚焦电极的聚焦电压来调控电子轰击阳极靶材的轰击面积，即X射线源光斑。栅极电压的大小取决于碳纳米管材料的结构和栅极与材料之间的距离。

![](images/a5f0ac3ff55f89eedf4b1a15fd1f2e858aa4012783d0cd71189129b0a86387b8.jpg)  
图1 基于场致发射的X 射线产生原理图  
Fig.1 The schematic diagram of carbon nanotube based X-ray sources

2.1.2系统设计

图2为该新型基于碳纳米管的 micro-CT系统的设计方案，整个系统可以分成均匀分布在两个同心圆上的5个子系统。碳纳米管X射线源所在的圆半径为 $R ( R { \in } \mathbf { R } ^ { + } )$ ，每个子系统包含$n ( n { \in } \mathbf { N } ^ { + } )$ ）个碳纳米管X 射线源和1个平板探测器。其中， $n$ 个X射线源均匀分布在圆上$\alpha ( \alpha { \in } ( 0 , 2 \pi ) )$ 范围内；平板探测器位置如图2 所示，其大小为 $d \times d$ ；探测器与同心圆圆心之间的距离为 $l$ ；扫描视野（FOV）为半径 $r ( r \in { \mathbf { R } } ^ { + } )$ 的球。

![](images/2021b5947094d46b1e1caa185f6c19755abc3dac9c79090c78e607a166dc9b0d.jpg)  
图 2Micro-CT 系统设计图  
Fig.2 The system design of Micro-CT

在此系统设计方案中，机架的尺寸参数需要在综合考虑实际过程中整体机架尺寸的条件下根据以

下两个原则仔细计算：

(1）为了尽量减少机械转动，且扫描过程中能够 $3 6 0 ^ { \circ }$ 覆盖待扫描模体， $\alpha$ （204 必须是72的约数，例如24；

(2）为了避免投影中出现截断现象，平板探测器必须安置在合适的位置。例如：如图2所示，P点是在第三象限内黄色光路和红色光路的交点，这就是水平方向上的平板探测器的左上端点安置极限点。

其中第三象限内黄色光路边缘的直线方程 $l _ { 1 }$ 为：

$$
{ \frac { x - R \mathrm { s i n } { \frac { \alpha } { 2 } } } { R \mathrm { s i n } ( { \frac { \alpha } { 2 } } - 2 \theta ) - R \mathrm { s i n } { \frac { \alpha } { 2 } } } } = = { \frac { y ~ R \mathrm { c o s } { \frac { \alpha } { 2 } } } { R \mathrm { c o s } ( { \frac { \alpha } { 2 } } ~ 2 \theta ) ~ R \mathrm { c o s } { \frac { \alpha } { 2 } } } } ~ s . t ~ \theta ~ \mathrm { a r c c o s } { \frac { r } { R } }
$$

第三象限内红色光路边缘的直线方程 $l _ { 2 }$ 为：

$$
{ \frac { x + R \cdot \mathbf { s i n } ( { \frac { \boldsymbol { \alpha } } { 2 } } \cdot \ { \frac { 4 } { 5 } } \pi ) } { R \cdot \mathbf { s i n } ( { \frac { \boldsymbol { \alpha } } { 2 } } + { \frac { 4 } { 5 } } \pi ) + \mu \mathbf { k i n } ( 2 \theta + { \frac { \boldsymbol { \alpha } } { 2 } } \cdot \ { \frac { 4 } { 5 } } \pi ) } } = { \frac { y \quad R \cdot \mathbf { s o s } ( { \frac { \boldsymbol { \alpha } } { 2 } } \cdot \ { \frac { 4 } { 5 } } \pi ) } { R \cdot \mathbf { s o s } ( 2 \theta \ { \frac { \boldsymbol { \alpha } } { 2 } } \cdot { \frac { 4 } { 5 } } \pi ) \quad R \cdot \mathbf { s o s } ( { \frac { \boldsymbol { \alpha } } { 2 } } \cdot \ { \frac { 4 } { 5 } } \pi ) } } \quad s . t \quad \theta \ \operatorname { a r c c o s } { \frac { r } { R } }
$$

通过 $l _ { 1 }$ 和 $l _ { 2 }$ （20 求出 $P ( X _ { P } , Y _ { P } )$ ，可以得出：

$$
\frac { l { = } | { \cal Y } _ { P } | } { d { = } 2 | { \cal X } _ { P } | }
$$

该系统的扫描视野取决于不同的机架配置参数，在忽略光斑和尽可能充分利用机架空间的前提下，本文根据以上两个原则和三个公式提供了一套假定的系统参数，如表1所示。

# 表1本文所提系统的系统参数

Table1 System parameterof proposed system   

<html><body><table><tr><td>参数</td><td>本文系统</td></tr><tr><td>α</td><td>24°</td></tr><tr><td>n</td><td>7</td></tr><tr><td>r</td><td>32 mm</td></tr><tr><td>d</td><td>226 mm</td></tr><tr><td>1</td><td>284.5 mm</td></tr><tr><td>R</td><td>500 mm</td></tr></table></body></html>

根据场致发射原理，碳纳米管X射线光源能够被外部脉冲有效控制。通过设计35 路时序脉冲控制35个碳纳米管X射线源的启停，此过程称为一次静态扫描。为了 $3 6 0 ^ { \circ }$ 覆盖待扫描物体，该系统需要旋转两次，每次经过 $2 4 ^ { \circ }$ 。系统运行图如图3所示。

![](images/7939fdac843760a330de5192074323c3bbb40458d004702ee549d981029fb9d0.jpg)  
Fig.3 The process of system operation

# 2.2系统的重建模型

传统CT 中由于X射线源和探测器同时随着机架的旋转而旋转，每个角度的X射线锥形束形状是一致的。然而在本文所提出的系统中，X射线锥形束形状随着角度的变化而变化（图4）。为了验证该系统的有效性，本系统采用迭代重建方法。

![](images/cfa09499dc34e13e4c2ccd7f76f567d11b5e963fa55d45a6bab9e343cdb25130.jpg)  
图3系统运行图  
图4 本文系统中五种X射线锥形束

假定该系统中重建模型是一个离散线性系统：

$$
g { = } M f
$$

其中，g 表示测量到的投影数据 $\mathbf { \Omega } _ { \mathcal { M } }$ 为系统矩阵， $f$ 为要重建的图像。重建问题可以看成公式

（4）的逆问题，根据优化理论可知，公式（1）可转换成公式（5）的凸优化问题[4]。

$$
\mathrm { m i n i m i z e } { \left\| \boldsymbol { f } \right\| } _ { T V } \quad s . t \quad { \left\| \boldsymbol { M } f - \boldsymbol { \check { g } } \right\| } \geqslant { \check { \mathcal { Z } } } , \xi \quad 0 , f _ { i } \quad 0
$$

其中 $\| f \| _ { T V }$ 为图像 $f$ 的全变差， $\xi$ 为一个非常小的常数， $f _ { i }$ 为图像 $f$ 中任意一点。

# 3结果

# 3.1碳纳米管X射线源的场发射特性测试

我们根据碳纳米管的场致发射原理搭建了相应的测试平台，并得到了碳纳米管X射线光源相应的场发射特性（图5）。图5为碳纳米管X射线光源的伏安特性曲线，在实验过程中，通过调整栅极电压（ $0 \sim 1 7 0 0 \mathrm { V }$ ）来控制X射线光源的阳极电流。从图5中可知，当栅极电压小于 $9 0 0 \mathrm { V }$ 的时候，电流变化很缓慢，类似于线性变化，当栅极电压大于某一阈值 $( 9 0 0 \mathrm { v } )$ 后，电流会呈指数形式增长。

![](images/c107c8f70ae7435fd949b2dc9cb13d38daa32c47c0bc5a8d83380a58b0f2d024.jpg)  
Fig.4 Five examples about the shape of $\mathrm { \Delta X }$ -ray beam of the proposed system   
图5 碳纳米管 X 射线光源的伏安曲线

Fig.6 Volt-ampere characteristics curve of carbon nanotube based $\mathbf { x }$ -ray source

# 3.2计算机仿真实验

根据本文所提出的系统参数，我们对该系统进行了计算机仿真实验。仿真过程中，3D Shepp-Logan 为待扫描模体，其分辨率为 $2 5 6 \times 2 5 6 \times 2 5 6$ ，体素的实际尺寸为 $2 5 0 \mu \mathrm { m } { \times } 2 5 0 \mu \mathrm { m } { \times } 2 5 0 \mu \mathrm { m }$ 。仿真结果见图6，迭代重建算法能够在若干次迭代下较好处理该系统的特殊数据，重建结果与3D Shepp-Logan 模体相比，最大差值为0.326，均方根误差为0.000401。

![](images/9c77676b986ae8d3890a8f3af8e3ff4b6212bdc38a57917e8ebfd0863e6af3c9.jpg)

图6计算机仿真实验结果：（A1,B1,C1）分别显示的是仿真结果的横断面、矢状面和冠状面; (A2,B2,C2）分别展示了3D Shepp-Logan 模体的横断面、矢状面和冠状面;(A3,B3,C3)分别表示图像在三个断面上的中轴线灰度之间的差异

Fig.6Simulationresultsbyusinga3DShepp-Loganphantom:(A1-A3)Simulationresults intransverse,sagitalandcoronal sectionrespectively;(B1-B3)3DShepp-Loganphantomin transverse,sagitalandcoronal sectionrespectively;(C1-C3)1D profiles for the comparison between the Shepp-Logan phantom and the simulation results along the central line.

# 4讨论

对于传统的商业CT 成像，由于“热阴极”X射线源的响应时间相对较长，再加上整个系统需要机械旋转，最终导致得到的影像受运动伪影的影响很大。本文提出了一种基于碳纳米管的micro-CT 系统设计，依据冷阴极场致发射原理，当碳纳米管表面电场强度达到一定的阈值后，碳纳米管X射线源的栅极电流会随着其表面场强的增大而指数增加。鉴于碳纳米管优异的电子瞬发特性（从碳纳米管材料表面施加电压到电子释放这一过程的延时大约在 $0 \sim 1 0 0 ~ \mu \mathrm { s }$ ，这是整个系统中保护电路所导致的），本文系统中尽可能地选择电子激发，减少机架的机械旋转次数和范围，从而使整体系统处于一种准静态状态。

在完成整个系统的扫描过程后，可以得到105 张投影数据，这对于传统的解析算法是远远不够的，因此本文采用迭代算法去处理该稀疏重建问题。从重建结果（图5）可以看出，无论是从横断面、矢状面还是冠状面，该系统的计算机仿真结果与 3D Shepp-Logan 数字模体的差别不大。

由于本文中的系统还是一个概念，无法通过实验得到其准确的时间分辨率，因此我们通过理论分析，定性地得到其大致的时间分辨率。在该系统扫描过程中，存在两个耗时部分—一机架两次旋转$2 4 ^ { \circ }$ 所需的时间[15]和三批35 个碳纳米管X射线源曝光时间[16]。目前最快的CT 旋转一周所需的时间为 $0 . 2 7 { \ } \mathrm { s } ^ { [ 1 7 ] }$ ，在本文系统中，如果采用类似的技术制造该系统，那么机架旋转两次走过 $4 8 ^ { \circ }$ 所需时间为 $( 4 8 / 3 6 0 ) { \times } 0 . 2 7 ~ \mathrm { s } = 6 ~ \mathrm { m s }$ 。

通过设计时序，使得分布在5个子系统中的5支碳纳米管X射线光源同时曝光，在一次静态扫描中只需7次曝光即可，机架旋转两次后，总共需要曝光21 次。在待扫描体所受剂量恒定的情况下，X射线源的曝光时间与其电流成反比，一般的X射线源的曝光时间大约在 $0 . 1 \sim 0 . 5$ ms(e.g.1ms)[18]，即系统总得扫描时间为： $2 1 { \times } 1 \mathrm { m s } + 3 6 \mathrm { m s } = 5 7 \mathrm { m s }$ 。该理论时间的估计是在忽略碳纳米管X射线源开启时间、碳纳米管X射线源功率足够和机架制造工艺与最先进的CT 制造工艺相当的理想情况下得出的，在实际成像过程中由于受到制造工艺的限制，系统的扫描时间会相应的延长。

本研究提出了一种基于碳纳米管的micro-CT 的系统设计，有效地提高了系统的时间分辨率，减少了待扫描体的生理运动对成像质量的影响。与现有设备 $^ { [ 1 ] }$ 不一样，本方法利用碳纳米管的场发射特性，碳纳米管在其表面电场强度达到一定的程度的时候就能瞬间激发出自由电子，而传统X射线光源需要预热，这一优异特性突破了传统micro-CT 的时间分辨率的极限。与Li 等[13]提出的基于碳纳米管的micro-CT的系统相比，本研究减少了系统的旋转次数和范围，从另一方面提升了系统的扫描速度。

# 5结论

本文提出了一种基于碳纳米管X射线源的新型Micro-CT 系统设计，该系统工作在准静态模式下，三次静态扫描能够实现 $3 6 0 ^ { \circ }$ 覆盖待扫描体，且通过计算机仿真实验验证了该系统的有效性。该系统理论上能够大大提高成像的扫描速度，减少了运动伪影对图像质量的影响。

# 参考文献

[1] Ritman EL. Micro-computed tomography-current status and developments [J]. Annual Review of Biomedical Engineering,2004, 6(1): 185-208.   
[2] Ritman EL. Current status of developments and applications of micro-CT [J]. Annual Review of Biomedical Engineering,2011,13(13): 531-552.   
[3] Mcgonigle P, Ruggeri B. Animal models of human disease: challenges in enabling translation [J]. Biochemical Pharmacology, 2014, 87(1): 162-171.   
[4] 叶乃力．用于活体小鼠模型的微型CT 呼吸门控技术研究[D].武汉：华中科技大学,2012.   
[5] Zink FE. X-ray tubes [J]. Radio Graphics,1997,17(5): 1259-1268.   
[6] Baughman RH, Zakhidov AA, Heer WAD. Carbon nanotubes -the route toward applications [J]. Science,2002,297(5582): 787-792.   
[7] Yue GZ, Qiu Q, Gao B,et al, Generation of continuous and pulsed diagnostic imaging x-ray radiation using acarbon-nanotube-based field-emission cathode [J]. Applied Physics Letters,2002,81(2): 355- 357.   
[8]Cao G,Lee YZ, Peng R, et al. A dynamic micro-CT scanner based on a carbon nanotube field emission x-ray source [J]. Physics in medicine and biology,2009, 54(8): 2323-2340.   
[9]Qian X, Rajaram R, Calderon-Colon X, et al. Design and characterization of a spatially distributed multibeam field emission x-ray source for stationary digital breast tomosynthesis [J]. Medical physics, 2009,36(10): 4389-4399.   
[10] Zhang J, Yang G,Lee YZ,et al. Multiplexing radiography using a carbon nanotube based x-ray source [J]. Applied Physics Letters,2006, 89(6): 1016.   
[11] Heo SH, Kim HJ,Ha JM, et al. A vacum-sealed miniature x-ray tube based on carbon nanotube field emitters [J]. Nanoscale Research Letters, 2012, 7(1): 258.   
[12] Maltz JS,SprengerF,Fuerst J, et al.Fixed gantry tomosynthesis system for radiation therapy image guidance based on a multiple source X-ray tube with carbon nanotube cathodes [J]. Medical Physics, 2009,36(5): 1624-1636.   
[13] Li L, Chen Z, Jin X. The multi-source instant CT for superfast imaging: system concept, reconstruction algorithms and experiments [C] //Nuclear Science Symposium and Medical Imaging Conference (NSS/MIC), 2013: 1-4.   
[14] Sidky EY, Kao CM, Pan X. Accurate image reconstruction from few-views and limited-angle data in divergent-beam CT [J]. Journal of X-Ray Science and Technology, 2009, 14(2): 119-139.   
[15] Petersilka M, Krauss B, Stierstorfer K,et al. Technical principles of dual source CT[J]. European Journal of Radiology, 2008, 68(3): 362-368.   
[16] Cao G,Burk LM,Lee YZ, et al. Prospective-gated cardiac micro-CT imaging offree-breathing mice using carbon nanotube field emission x-ray[J]. Medical Physics, 2010,37(10): 5306-5312.   
[17]Russo V, Garattoni M,Buia F,et al. 128-slice CTangiographyof the aorta without ECG-gating: efficacyof faster gantry rotation time and iterative reconstruction in terms of image quality and radiation dose [J]. European Radiology,2016,26(2): 359-369.   
[18] LiL, Chen Z, Yu H, et al. Experimental measurement of human head motion for high-resolution computed

tomography system design [J]. Optical Engineering, 2010, 49(6): 063201-063201-6.