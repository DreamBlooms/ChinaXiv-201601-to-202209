# 基于单镜头双相机的运动颗粒三维速度测量

贾敏华周骛金娜蔡小舒

(上海理工大学能源与动力工程学院，上海市动力工程多相流动与传热重点实验室，上海 200093)

摘要本文基于离焦测距原理，提出一种利用单镜头双相机测量运动颗粒三维速度的方法。入射光经分束立方体分别进入两个工业相机，通过调节分束立方体与相机间的垫圈厚度获取同一对象两幅不同模糊度的图片，根据其模糊差实现运动颗粒在三维场中的定位，再结合单帧多曝光方法，获取其三维速度。通过拍摄慢速搅拌水流中颗粒运动并分析处理不同运动情况的颗粒图片得到了运动颗粒的三维速度，经计算与实验考察证明了其可行性。该方法解决了离焦二义性问题与速度方向二义性问题，为三维速度的测量提供了新的方向。

关键词离焦模糊；三维速度；单镜头双相机；单帧多曝光中图分类号：TK313 文献标识码：A 文章编号:0253-231X(2017)08-1692-05

# 3-D Velocity Measurement of Moving Particles Based on Single-Lens Dual-Camera

JIA Min-Hua ZHOU Wu JIN Na CAI Xiao-Shu

ShanghaiKeyLaboratoryofMultiphaseFlowand HeatTransferinPowerEnginering,SchoolofEnergyandPowerEngineering University of Shanghai for Science and Technology， Shanghai 200093, China)

Abstract Based on the principle of depth from defocus,a kind of method for the measurement of three-dimensional (3-D) velocity of moving particle using the single-lens dual-camera was proposed. The incident light was dispersed into two industrial cameras through the beam splitter prism.Two images with different blur degree for the same object were acquired by adjusting the thickness of the washers between the prism and the cameras. The orientation of the moving particle in the three-dimensional field was obtained from the diffrence of blur degree between the images,and then the 3-D velocity of the particles can be calculated combined with the single-frame multi-exposure method.The images recording the movement of particles in the water flow with slow agitation were processed and analyzed which lead to the calculating results of the 3-D velocity field of moving particles. The feasibility of the method proposed was verified through the comparison of the calculating results and the experimental results. The method solves the problems of the ambiguity of both defocus and the direction of velocity,as wellas indicating a new way for the measurement of 3-D velocity. Key wordsdefocus blur; 3-D velocity; single-lens dual-camera; single-frame multi-exposure

# 0引言

多相流在燃烧学、医药学等各个学科领域中有广泛应用，深入了解多相流机理有赖于对多相流中颗粒相的三维定量测量。因此颗粒场的三维测量研究具有重要的科学意义及实用价值，如药物喷雾的测量、循环流化床锅炉气固两相流流动特性的研究。

目前用于颗粒场三维速度测量的技术主要有：数字全息技术（DH）[1]、激光多普勒测速技术(LDV）[2]、粒子图像测速技术（PIV）[3]以及粒子跟踪测速技术(PTV)[4]。后两种技术由于其全场、瞬态、非接触测量等优势，在工业领域得到了广泛的应用。PIV是一种基于杨氏条纹法和自相关法的技术,其可在极短的曝光时间内连续两次或多次通过CCD相机记录流动区域内的示踪粒子。该方法在二维速度的测量上已相对成熟，其三维速度主要通过与全息技术结合，即数字全息粒子测速技术（DHPIV）[5],或者采用两台或多台相机从不同角度记录同一流动区域内示踪粒子的运动情况获取[，完成颗粒三维速度场的重建。PTV技术从原理来说与PIV技术近似，相比于PIV，其示踪粒子浓度较低，避免了PIV技术的平均效应；PTV技术可对单个粒子进行跟踪，具有更高的准确性，便于由二维测速推广到三维测速。在实际应用中每种方法都有其优势和局限，仍需进一步的研究探索。

# 1 实验原理

20 世纪90 年代初迎来了数字图像处理技术[7]的大发展。该技术在采集图像过程中通常要避免产生离焦，但离焦时产生的模糊信息能反映物体的深度信息，进而实现三维位置和速度的重建。因此本文基于离焦测距原理，提出一种利用单镜头双相机测量运动颗粒三维速度的方法。该方法解决了离焦二义性和速度二义性问题，操作简单，且可行性得到验证。

物方远心镜头[8离焦模糊成像如图1所示，在像方焦平面处放置一个直径为 $D$ 的光阑，使物距发生变化时物体的尺寸大小可以保持不变。图中 $P$ 为物点， $D$ 为光阑直径， $P ^ { \prime }$ 为像点。 $P$ 到镜头主平面的距离为物距 $u$ ，光阑到镜头主平面的距离为焦距$f$ ， $P ^ { \prime }$ 到镜头主平面的距离为像距 $\mathbf { \sigma } _ { v }$ 。

$$
u = \frac { f ( s _ { 1 } + \alpha s _ { 2 } ) } { s _ { 1 } - f + \alpha ( s _ { 2 } - f ) } , \quad ( s _ { 2 } < v < s _ { 1 } )
$$

# 1.1离焦测距原理

![](images/90b64882d6cbd34085c038c88b7dc9ef80441296450d1043ee6c0e01bee07072.jpg)  
图1物方远心镜头离焦模糊成像过程 Fig.1 Defocus burring imaging process of object-space telecentric lens

式[9]：

$$
u = \frac { f ( s _ { 1 } - \alpha s _ { 2 } ) } { s _ { 1 } - f - \alpha ( s _ { 2 } - f ) } , \left( \begin{array} { l } { \alpha > 1 , v < s _ { 2 } < s _ { 1 } } \\ { \alpha < 1 , s _ { 2 } < s _ { 1 } < v } \end{array} \right)
$$

若传感器 $\mathrm { I S } _ { 1 }$ 和 $\mathrm { I S } _ { 2 }$ 位于最佳成像面的同侧时选择公式 (2)； $\mathrm { I S } _ { 1 }$ 和 $\mathrm { I S _ { 2 } }$ 位于最佳成像面的异侧时选择公式 (3)。公式中的 $f , s _ { 1 }$ 和 $s _ { 2 }$ 可以通过系统标定得到， $\alpha$ 通过比较图像的离焦模糊度得到。当相机传感器位于最佳成像面时会产生两种临界情况，即$\mathrm { I S } _ { 1 }$ 和 $\mathrm { I S } _ { 2 }$ 分别位于最佳成像面时，由此可以推出：

$$
\delta _ { 1 } = \frac { D \left( s _ { 1 } - s _ { 2 } \right) } { s _ { 2 } - f }
$$

$$
\delta _ { 2 } = { \frac { D \left( s _ { 1 } - s _ { 2 } \right) } { s _ { 1 } - f } }
$$

其中, $\delta _ { 1 }$ 为 $\mathrm { I S _ { 2 } }$ 恰好位于最佳成像面时 $\mathrm { I S } _ { 1 }$ 上所成模糊像的模糊直径； ${ \delta } _ { 2 }$ 为 $\mathrm { I S } _ { 1 }$ 恰好位于最佳成像面时$\mathrm { I S } _ { 2 }$ 上所成模糊像的模糊直径。若 $2 r _ { 1 } < \delta _ { 1 }$ 且 $2 r _ { 2 } { < } \delta _ { 2 }$ 最佳成像面位于双相机传感器之间，即选择式 (3)，若 $2 r _ { 1 } > \delta _ { 1 }$ 或 $2 r _ { 2 } { > } \delta _ { 2 }$ ，最佳成像面位于双相机传感器同侧，即选择式 (2)。

# 1.2单帧多曝光方法

为获得颗粒场三维速度，采用单帧多曝光测量方法，如图2所示。第一个外部触发信号输入，相机开始接收入射光，进行第一次曝光，曝光时间为触发信号的宽度，经过一段时间后，相机根据设置开始进行下一次曝光， $N$ 次曝光后数据集合在一帧图像上，形成单帧多曝光图像。根据实验要求选择合适的曝光次数 $N$ 、曝光时间和间隔时间，若曝光次数过多会造成噪声增加，曝光次数过少则无法准确判断颗粒的运动过程。

根据高斯公式 ${ \frac { 1 } { u } } + { \frac { 1 } { v } } = { \frac { 1 } { f } }$ 成像系统的焦距 $f$ ，确定后，物距 $u$ 和像距 $\mathbf { \sigma } _ { v }$ 呈一一对应关系，只有相机传感器位于像距处时才能得到最清晰的像，此时为最佳成像面。若相机传感器偏离最佳成像面时会产生离焦模糊，如图1所示两个相机传感器分别位于 $\mathrm { I S } _ { 1 }$ 位置和 $\mathrm { I S _ { 2 } }$ 位置时 $\left( s _ { 1 } > s _ { 2 } \right)$ ，此时传感器偏离了最佳成像面，会产生不同程度的离焦模糊，模糊半径分别为 $\left| { { r _ { 1 } } } \right.$ 和 $r _ { 2 }$ ， $\mathbf { \boldsymbol { r } } _ { 1 }$ 和 $r _ { 2 }$ 的比值根据几何关系可以被表示为：

![](images/e60caf98ddd047ace7618f9f358e985a032a941e5984e3c391f6bf8d2020048e.jpg)  
图2单帧多曝光方法  
Fig.2 Single-frame and multiple-exposure method

$$
\alpha \equiv { \frac { r _ { 1 } } { r _ { 2 } } } = { \frac { s _ { 1 } - v } { \pm s _ { 2 } \mp v } }
$$

结合高斯公式可以得到离焦图像的物距计算公

图3为一幅单帧多曝光图像，由图可知，一个颗粒经过四次曝光后在一帧图像上成像，直观反映了颗粒的运动轨迹，总曝光时间已知，只要选择其中两个位置就可以得到颗粒的三维速度和方向。为减少误差，选择位置1和4，通过程序处理得到颗粒在位置1和位置4的三维坐标，根据下面公式可获得颗粒的三维速度：

$$
v _ { x } = { \frac { \Delta x } { m t } } = { \frac { x _ { 4 } - x _ { 1 } } { m t } }
$$

$$
v _ { y } = { \frac { \Delta y } { m t } } = { \frac { y _ { 4 } - y _ { 1 } } { m t } }
$$

$$
v _ { z } = { \frac { \Delta u } { m t } } = { \frac { u _ { 4 } - u _ { 1 } } { m t } }
$$

其中， $m$ 为镜头的放大倍率； $\mathbf { \Psi } _ { t }$ 为从第一次曝光开始到最后一次曝光结束的总时间； $u _ { 1 }$ 和 $u _ { 4 }$ 分别为颗粒处于位置1和位置4时的物距。

![](images/5b5ab1cd43dc4c57fbe3f7baf88d8ab01ad652a4b4894d8096781254756b0b77.jpg)  
图3单帧多曝光图像 Fig.3 The image captured by single-frame and multiple-exposure imaging

# 2单镜头双相机系统

单镜头双相机系统由两个CCD工业相机（帧率16 fbs、分辨率 $1 6 2 8 \times 1 2 3 6$ 、像元大小 $4 . 4 ~ \mu \mathrm { m } \times 4 . 4$ μm)、一个物方远心镜头 $( 1 \times )$ 和一个分束立方体组成，如图4所示。入射光经分束立方体分离为5:5的透射光和反射光，分别进入两个CCD工业相机，通过调节分束立方体与相机之间的垫圈厚度获取了同一对象的两幅不同模糊度图片，而双相机的同步运行则需要使用信号发生器同步触发。

镜头是由多片透镜组成的透镜组，添加分束立方体后可近似看作在原透镜组上添加了新的透镜，原镜头的参数被改变，故镜头与分束立方体的组合可视为一个新镜头。该组合的焦距与其他参数较原镜头可能发生改变，需要通过实验对镜头进行重新标定。实验选取直径为 $1 0 0 0 ~ { \mu \mathrm { m } }$ 的圆点标定板作为拍摄对象，在相机和分光棱镜之间从0开始依次添加垫圈(厚度 $1 \mathrm { m m }$ 、 $2 ~ \mathrm { m m }$ 或 $\mathrm { 5 ~ m m } ^ { \cdot }$ )，用游标卡尺测得分束立方体到相机之间的距离，并移动圆点标定板的位置，找到该像距下对应的最清晰像的工作距离 (标定板到镜头前端面的距离)，此时可得到两个参数，即工作距离 $w$ 与分束立方体到相机之间的距离 $y$ ，由高斯公式得到公式：

$$
{ \frac { 1 } { w + L _ { 1 } } } + { \frac { 1 } { y + L _ { 2 } } } = { \frac { 1 } { f } }
$$

其中， $L _ { 1 }$ 表示从镜头的前端面到其物主平面的距离， $L _ { 2 }$ 表示从镜头的后端面到其像主平面的距离。根据以上公式拟合得到本实验镜头和分束立方体组合的参数如表1所示。

![](images/d2b1d54e40e5fdc89c15f2f0fd1f855998b3957c73456b7bb668ca6ad06adf65.jpg)  
图4单镜头双相机系统示意图 Fig.4 Schematic drawing of single-lens dual-camera system

# 表1镜头参数

Table 1 The parameters of lens   

<html><body><table><tr><td></td><td>f/mm</td><td>L1/mm</td><td>L2/mm</td></tr><tr><td>原镜头</td><td>47.76</td><td>29.14</td><td>78.01</td></tr><tr><td>分束立方体＋镜头</td><td>45.59</td><td>27.67</td><td>121.66</td></tr></table></body></html>

在系统搭建中需选取合适数量和厚度的垫圈，使同一物体在双相机上的成像模糊度不同，便于后续程序处理得到其模糊度之比。系统确定后，移动圆点标定板，分别记录圆点在双相机上成清晰像时的工作距离 $w _ { 1 }$ 和 $w _ { 2 }$ ，再分别加上 $L _ { 1 }$ 的值即为双相机最佳成像面所对应的物距 $u$ ，代入高斯公式可以得到像距 $\mathbf { \nabla } _ { v }$ ，即图1中的 $s _ { 1 }$ 和 $s _ { 2 }$ 。经计算， $s _ { 1 }$ 为$1 2 6 . 4 6 ~ \mathrm { m m }$ ， $s _ { 2 }$ 为 $1 2 2 . 2 6 ~ \mathrm { m m }$ 。

# 3 实验结果

为验证系统的可行性，对水槽中的颗粒场进行拍摄。图5为运动颗粒速度测量实验装置图，其使用粒径大小为 $1 0 0 ~ { \mu \mathrm { m } }$ 、密度为 $\mathrm { 1 . 1 8 ~ g / c m ^ { 3 } }$ 的示踪粒子PMMA(聚甲基丙烯酸甲酯)作为流场内运动颗粒的拍摄对象。实验时使用玻璃棒搅动水槽内的水，使其低速运动，选用卤素灯作为背景光源，采用背光拍摄方式，通过信号发生器实现双相机的同步拍摄及单帧多曝光功能，曝光时间依次为 $1 ~ \mathrm { m s }$ 、 $4 ~ \mathrm { m s }$ 、1ms和 $1 ~ \mathrm { m s }$ ，间隔时间为 $2 0 ~ \mathrm { m s }$ 。

图6为运动颗粒在双相机中成像的几种典型图片及处理结果。在图6(a）中，沿运动方向颗粒在两个相机中成像的模糊度变化不同，在传感器IS1上模糊度逐渐变小，而在传感器IS2上模糊度逐渐变大；图6(b）中运动颗粒的模糊度变化相同，均逐渐变大；图6(c）中运动颗粒的模糊度基本不变。由于第二段曝光时间较长，导致颗粒的遮光时间长，除存在一定长度运动轨迹外，相比其它颗粒图像其灰度值也较大，通过该长轨迹图像位置的判断可以获得颗粒的运动方向。为避免运动模糊带来的复杂计算，应选取颗粒位于短曝光时段的图像进行三维定位处理计算。本文通过对颗粒运动轨迹图像（椭圆形框中）的第一点和第四点分析计算，得到 $x$ 、y、z三个分量的速度、二维合速度和三维合速度，计算结果如表2所示，其中 $\mathbf { \Psi } _ { x }$ 分量以向左运动为正， $y$ 分量以向下运动为正， $z$ 分量以向镜头方向运动为正。

![](images/8f950f9e6b542f751bd1489ad699a53c9c12a56711ab83dc4644243863eacc17.jpg)  
图5运动颗粒速度测量实验装置图Fig.5 Experimental setup for velocity measurement ofmoving particles

![](images/8b9c6b6aac764efd4e70213897b3d907f089c3ac12a6a7311926aa9bfc41f4ae.jpg)

![](images/86948e3203fcdbb4d04e80bd0baed0621b3d4e877b8790602e7b0e41c855c763.jpg)

图6运动颗粒三维速度测量结果  
\`ig.6 Experimental results for velocity measurement of moving particles

表2运动颗粒的三维速度 $\bf ( m m / s )$   
Table 2 3-D velocity of moving particles (mm/s)   

<html><body><table><tr><td></td><td>图像 (a)</td><td>图像 (b) 图像 (c)</td></tr><tr><td>Ux</td><td>18.26 1.18</td><td>34.28</td></tr><tr><td>Uy</td><td>4.60</td><td>20.49 4.20</td></tr><tr><td>Uz</td><td>20.90</td><td>0.00</td></tr><tr><td>Ux,y</td><td>18.83</td><td>20.52 34.54</td></tr><tr><td>Ux,y,z</td><td>28.13</td><td>20.54 34.54</td></tr></table></body></html>

由表2可知，图像(a）中运动颗粒的二维合速度 $v _ { x , y }$ 与其三维合速度 $v _ { x , y , z }$ 相差较大，表明颗粒相对于成像平面有较大的运动，对应了两幅图片运动颗粒图像模糊度变化不同的情况；图像(b)和（c中颗粒的 $v _ { x , y }$ 和 $v _ { x , y , z }$ 基本相同，表明其颗粒在 $z$ 方向上基本没有运动，对应了两幅图片运动颗粒图像模糊度变化一致的情况；图像 (b)和(c)分别对应了颗粒垂直运动和水平运动。实验结果证明了该方法和系统在运动颗粒三维速度测量方面的可行性。

# 4结论

本文基于离焦测距原理和单帧多曝光方法，利用单镜头双相机系统测量运动颗粒的三维速度，并简述了离焦测距公式中各个参数的获取方法，通过拍摄慢速搅拌水流中颗粒的运动，对不同运动情况的颗粒图片进行了处理分析，证明了该方法的可行性与有效性，操作简单、成本低，实现了运动颗粒在无参考条件下的深度定位以及速度重构，为三维流场测量奠定了基础。

# 参考文献

[1]罗鹏，吕晓旭,钟丽云.数字全息技术研究进展及应用[J].激光杂志,2006,27(6):8-10

LUO Peng，LU Xiaoxu,ZHONG Liyun．Development and Applications of Digital Holography [J].Laser Journal,2006,27(6): 8-10 [2] Maru K,Watanabe K.Non-Mechanical Scanning Laser Doppler Velocimetry with Sensitivity to Direction of Transverse Velocity Component Using Optical Serrodyne Frequency Shifting. Optics Communications， 2014,319:   
80-84 [3] Kolehmainen J， Elfvengren J， SaarenrinneP.A Measurement-Integrated Solution for Particle Image Velocimetry and Volume Fraction Measurements in a Fluidized Bed [J].International Journal of Multiphase Flow,   
2013,56:72-80 [4] Ohmi K.SOM-Based Particle Matching Algorithm for 3D Particle Tracking Velocimetry [J].Applied Mathematics and Computation,2008,205:890-898 [5] SHEN Gongxin,WEI Runjie.Digital Holography Particle Image Velocimetry for the Measurement of 3Dt-3c Flows [J].Optics and Lasers in Engineering,2005,43:1039-1055 [6] Amaral R L,Castilho G J,Cremasco M A. Experimental Investigation of 3D Velocity by Tomographic Particle Image Velocimetry (Tomo-PIV) in a Short Riser Section [J]. Procedia Engineering,2012,42:683-689 [7]陈汗青,万艳玲,王国刚.数字图像处理技术研究进展[J].工 业控制计算机，2013,26(1)：72-74 CHEN Hanqing， WAN Yanling， WANG Guogang. Progress of Digital Image Technology Processing Research [J].Industrial Control Computer,2013,26(1):72-74 [8] 潘兵,俞立平,吴大方．使用双远心镜头的高精度二维数字 图像相关测量系统[J].光学学报，2013,33(4)：105-115 PAN Bing,YU Liping,WU Dafang. High-Accuracy TwoDimensional Digital Image Correlation Measurement System Using a Bilateral Telecentric Lens [J].Acta Optica Sinica,2013,33(4): 105-115 [9] ZHOU Wu, JIN Na, JIA Minhua,et al. A 3D Positioning Method for Moving Particles Based on Defocused Imaging Using Single-Lens Dual-Camera System [J]. Chinese Optics Letters,2016,14(03):46-50