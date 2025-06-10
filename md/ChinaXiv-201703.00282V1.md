# 星载高光谱成像光谱仪狭缝函数测试方法的研究

毛靖华1²，王咏梅1\*，石恩涛‘，张仲谋'，江芳1（1．中国科学院国家空间科学中心北京1001902．中国科学院大学 北京 100190;)

摘要：为了满足大气微量成分高精度测量需求，要求准确描述星载高光谱大气微量成份探测仪的仪器狭缝函数，针对高光谱大气微量成份探测仪视场大、波段宽、空间分辨率和光谱分辨率高等特点，研制了狭缝函数测量仪。本文首先介绍了狭缝函数测量仪的工作原理，接着利用狭缝函数测量仪可同时实现高分辨率、宽谱段测量的特点，对高光谱大气微量成份探测仪进行全视场的狭缝函数测试，给出仪器狭缝函数特性分布，并对结果进行分析。测试结果表明：高光谱大气微量成份探测仪的狭缝函数特性曲线近似满足高斯分布规律，由于星载大视场成像光谱仪存在光谱弯曲现象，导致边缘视场分辨能力略低于中心视场分辨能力，高光谱大气微量成份探测仪全视场光谱分辨率优于0.6nm。

关键词：狭缝函数；高光谱大气微量成份探测仪；中阶梯衍射光栅中图分类号：TG502.33；TH744 文献标识码：A 文章编号：

# 0引言

近年来利用高光谱成像技术[1-获取探测物体空间信息和光谱信息的方法逐渐成为空间环境探测的主要手段之一，尤 其在气象观测和环境监测领域得到广泛应用。

为满足我国环境污染监测的迫切需求，研制了风云卫星高光谱大气微量成份探测仪。高光谱大气微量成份探测仪是以差分光学吸收光谱法DOAS[7](Differential Optical Absorption Spectroscopy)为探测原理的成像光谱仪。高光谱大气微量成份探测仪探测光谱范围 $3 7 5 \mathrm { n m } { - } 5 0 0 \mathrm { n m }$ ，总视场 $1 1 2 ^ { \circ }$ ，光谱分辨率约 $0 . 4 \mathrm { - } 0 . 6 \mathrm { n m }$ ，通过在卫星上探测大气后向散射辐射，利用DOAS算法解析微量气体成分的分布和变化，实现我国对大气微量成分全球探测。

DOAS算法以比尔定律为基础，根据分子瑞利散射和波长吸收随波长变化的差异，利用光谱差分技术将消光作用分解为慢变部分和快变部分，通过低阶多项式拟合处理消除慢变部分影响，并从快变部分中提取出目标气体的总量信息。星载大气微量成分探测仪的定标是产品高精度定量化的前提和基础，其中一项主要的定标是高光谱仪器狭缝函数的测量[8-9]。差分吸收光谱仪数据反演的精度在很大程度上取决于对仪器狭缝函数描述的精度，因此高精度的狭缝函数测量对星载大气微量成分探测仪起着至关重要的作用。2004年搭载于Aura卫星上的臭氧监测仪OMI（Ozone MonitoringImager）研制专用的基于中阶梯光栅分光原理的衍射装置[10-14]进行仪器狭缝函数测量。中阶梯光栅有较少的线密度和较大的闪耀角，具有高分辨率和色散率的特点，适用于仪器狭缝函数的测量。

为了满足大气微量成分高精度测量需求，要求准确描述星载高光谱大气微量成份探测仪的仪器狭缝函数，针对该有效载荷视场大、波段宽、空间分辨率和光谱分辨率高等特点，研制了狭缝函数测量仪。本文主要介绍所研制的狭缝函数测量仪的工作原理，并对高光谱大气微量成份探测仪进行全视场的狭缝函数特性测量。

# 1狭缝函数测量仪的简介

# 1.1狭缝函数测量仪的工作原理

狭缝函数测量仪的光学示意图如图1所示。这里前光学系统用有效面积为 ${ \bf A } _ { 0 }$ 的单透镜代替。

![](images/8e42dce9380c87887f9a2dbf546a077e8f0b095c6ff30ed4744c65ba24ff4daa.jpg)  
图1狭缝函数测量仪的光学示意图  
Fig.1 Sketch map of the SiltFunction

由图1可得，进入光谱仪狭缝的辐射功率为

$$
P = E _ { 5 0 } ( \frac { 5 0 } { L 1 } ) ^ { 2 } A _ { 0 } \eta A _ { x } / A _ { g i }
$$

其中， $\mathrm { E } _ { 5 0 }$ 为距光源 $5 0 \mathrm { c m }$ 处的辐照度， $\mathfrak { n }$ 为前光学系统的效率， $A _ { x }$ 为入射狭缝面积， $A _ { g i }$ 为光源在狭缝上像的面积，有

$$
A _ { g i } = A _ { g } \cdot ( L _ { 2 } / L _ { 1 } ) ^ { 2 }
$$

将上式代入(3)式，得

$$
P = E _ { 5 0 } \cdot \eta \cdot ( A _ { _ x } / A _ { _ g } ) 5 0 ^ { 2 } F ^ { 2 }
$$

其中，F为光谱仪的F数， $A _ { x }$ 为光源面积。

从（3）式看出，若光源像的宽和高均大于光谱仪入射狭缝的宽和高，则进入光谱仪的能量仅与光源在 $5 0 \mathrm { c m }$ 处的辐照度、前光学系统的效率、入射狭缝和光源面积以及光谱仪的F数有关。

高光谱大气微量成份探测仪光谱分辨率优于

$0 . 6 \mathrm { n m }$ ，为了准确描述仪器狭缝函数，需要狭缝函数测量仪光谱分辨率高达 $0 . 0 6 \mathrm { n m }$ 。根据光栅衍射方程：

$$
\sin \alpha + \sin \beta = m \lambda / d
$$

式中 $\alpha$ 为光线入射角， $\beta$ 为衍射角， $m$ 为衍射级次， $\lambda$ 为中心波长， $d$ 为光栅常数。

由公式（4）得出狭缝宽度对应的光谱增宽：

$$
d \lambda = \frac { 1 0 ^ { 6 } \cos { \beta } } { m n f } d l
$$

$n$ 为光刻线密度， $d l$ 为出射狭缝宽度， $f$ 为出射焦距长度。光栅刻线为79.01grooves/mm，衍射角为$7 1 . 5 ^ { \circ }$ ，根据公式(5)，当准直镜焦距 $\mathrm { f = 6 1 5 . 8 9 4 m m }$ 时，对 $3 7 0 \mathrm { n m } { - } 5 0 5 \mathrm { n m }$ 光谱范围，狭缝函数测量仪的光谱分辨率为 $0 . 0 3 9 4 \mathrm { n m } { - 0 . 0 5 7 8 } \mathrm { n m }$ ，可满足测试要求。狭缝函数测量仪光谱分辨能力如表1所示。

# 表1狭缝函数测量仪光谱分辨能力

Table1 Spectral resolution of the Siilt Function   

<html><body><table><tr><td>m</td><td>λ(nm)</td><td>dλ (nm)</td></tr><tr><td>48</td><td>506.903</td><td>0.0578</td></tr><tr><td>49</td><td>496.558</td><td>0.0566</td></tr><tr><td>50</td><td>486.626</td><td>0.0555</td></tr><tr><td>51</td><td>477. 085</td><td>0.0544</td></tr><tr><td>52</td><td>467.910</td><td>0.0533</td></tr><tr><td>53</td><td>459.082</td><td>0.0523</td></tr><tr><td>54</td><td>450.580</td><td>0.0514</td></tr><tr><td>55</td><td>442.388</td><td>0.0504</td></tr><tr><td>56</td><td>434.488</td><td>0.0495</td></tr><tr><td>57</td><td>426.865</td><td>0.0487</td></tr><tr><td>58</td><td>419.506</td><td>0.0478</td></tr><tr><td>59</td><td>412.395</td><td>0.0470</td></tr><tr><td>60</td><td>405.522</td><td>0.0427</td></tr><tr><td>61</td><td>398.874</td><td>0.0420</td></tr><tr><td>62</td><td>392.441</td><td>0.0413</td></tr><tr><td>63</td><td>386.212</td><td>0.0406</td></tr></table></body></html>

<html><body><table><tr><td>64</td><td>380.177</td><td>0.0400</td></tr><tr><td>65</td><td>374.328</td><td>0.0394</td></tr></table></body></html>

# 1.2狭缝函数测量仪的基本结构

狭缝函数测量仪由稳定光源系统、高光谱分辨率中阶梯光栅光谱仪和后光学系统三部分组成。结构中三部分为独立模块，便于光源散热和出射光束可调。图2为狭缝函数测量仪的结构图。

![](images/3cc228a10f8bd510ec92fe6073b02254065fba8e17cb86f7d67f283b622905d6.jpg)  
图2狭缝函数测量仪的结构图

# 2测试过程与结果

# 2.1测试光源的选取

狭缝函数测量仪光源的选取需由待测的高光谱大气微量成分探测仪的探测信号和探测能力决定。高光谱大气微量成份探测仪在标准信号探测时的SNR为1000。为此光源选用日本浜松公司生产的L2479型超静氙灯，该光源具有输出功率高、光能分布稳定等特点，光源主要辐射特性见表2。

# 表2L2479的主要辐射特性

Table2Radiationcharacteristic ofL2479   

<html><body><table><tr><td>型号</td><td>功率W</td><td>弧长mm</td><td>光强uW/cm2.nm@50cm</td></tr><tr><td></td><td></td><td></td><td>λ440nm</td></tr><tr><td>L2479</td><td>300</td><td>3.0</td><td>5.06</td></tr></table></body></html>

狭缝函数测量仪中单片反射镜反射率为0.87，光栅效率为0.5，光源大小为 $3 \times 1 \mathrm { m m } ^ { 2 }$ ，狭缝大小为 $5 . 2 \times 0 . 5 \mathrm { m m } ^ { 2 }$ 。由公式（2）和公式（3)，当输出光束在 $\Phi 2 0 \mathrm { m m }$ 时，该系统输出辐照度如表3所示。

# 表3狭缝函数测量仪输出的光辐照度

Table 3 Irradiance of the Silt Function   

<html><body><table><tr><td>波长nm</td><td>440</td></tr><tr><td>50cm处灯辐射照度uW/cm2.nm</td><td>5.06</td></tr><tr><td>仪器输出的光谱功率密度uW/nm.cm2</td><td>2.7</td></tr><tr><td>光谱分辨率nm</td><td>0.063</td></tr><tr><td>仪器输出辐射功率密度uW/cm2</td><td>0.17</td></tr><tr><td>SNR</td><td>980</td></tr></table></body></html>

从上表可以看出，若采用300W的L2479氙灯，当输出光束在 $\Phi 2 0 \mathrm { m m }$ 时，狭缝函数测量仪测量SNR与标准信号测量时的SNR相当。

# 2.2仪器狭缝函数的测量

由于星载大气微量成分探测仪探测视场大，不可避免会出现谱线弯曲的现象，且谱线弯曲不能调整到完全对称。为了准确描述该载荷的仪器狭缝函数，需要在全视场范围内对仪器狭缝函数进行测量。实验装置如图3所示，由光源、狭缝函数测量仪、高精度转台、待测的高光谱大气微量成份探测仪和计算机组成。

![](images/47b80cac12481b539fb4af268aca6f6008f09cd519b0fa3a860c1b744ea9ba41.jpg)  
Fig.2Optical structure of the Silt Function   
图3实验装置示意图  
Fig.3 Experiment diagram of the Silt Function

点亮光源，通过调整仪器积分时间和增益以保证获得较高的信噪比。稳定 $1 0 \mathrm { { m i n } }$ 后开始测量，记录CCD感光区域光谱数据 $S _ { i m } - S _ { j n }$ 。i、j代表空间维行号，m、n代表光谱维列号。每隔 $1 0 ^ { \circ }$ 转动高精度转台，记录下光谱数据 $S _ { i m } ^ { } - S _ { j n } ^ { }$ ，重复该过程，记录下全视场的光谱数据。

图4为高光谱大气微量成份探测仪位于中心视场时单次测试输出信号。由图4可以看出，狭缝函数测量仪能一次输出多条分布均匀的谱线，这些均匀分布的离散谱线被成像在高光谱大气微量成分探测仪的面阵探测器上。

![](images/758e270d19bcb1a5f1dd714a536bf62b2adc4ce3ca27b10f6b3f731225fad6c0.jpg)  
图4高光谱大气微量成份探测仪单次测量输出谱线 Fig.4Hyperspectral atmospheric trace constituents detectors output lines in a single measurement

根据高光谱大气微量成分探测仪光谱响应范围，可以提取信号较强的多条谱线（14条)，并分别对这些谱线进行拟合，得到仪器狭缝函数。

# 2.3测试结果与分析

对于理想光谱仪，仪器的狭缝函数是梯形或者是三角形,实际中由于受衍射效应、散射效应以及像元响应函数的非矩形等多种因素影响，高光谱遥感仪器每个波段的狭缝函数曲线近似满足Gauss 分布。仪器在中心波长的光谱分辨率一般用狭缝函数的半高宽表示。

图5a)和b)为高光谱仪器在中心视场时，$4 8 1 . 4 \mathrm { n m }$ 、 $4 6 2 . 7 \mathrm { n m }$ 的狭缝函数曲线，c）和d）为在边缘视场时， $4 8 1 . 4 \mathrm { n m }$ ！ $4 6 2 . 7 \mathrm { n m }$ 的狭缝函数曲线。

![](images/60ff06f68d7511b988a56d581ac6c41921f6ad4205997173bafc60d89beb52cf.jpg)  
图5不同视场下 $4 8 1 . 4 \mathrm { n m }$ 、 $4 6 2 . 7 \mathrm { n m }$ 的狭缝函数曲线  
Fig.5The silt function of $4 8 1 . 4 \mathrm { n m }$ 、 $4 6 2 . 7 \mathrm { n m }$ in different fields

图6a)和b)为高光谱仪器在中心视场时， $4 5 3 . 8 \mathrm { n m }$ ，$4 4 5 . 3 \mathrm { n m }$ 的狭缝函数曲线，c）和d)为在边缘视场时，$4 5 3 . 8 \mathrm { n m }$ 、 $4 4 5 . 3 \mathrm { n m }$ 的狭缝函数曲线。

![](images/8a33581b194f066ecd670726527ed6c9c46cd0f432d0336166e7ecd973c77160.jpg)  
图6不同视场下 $4 5 3 . 8 \mathrm { n m }$ 、 $4 4 5 . 3 \mathrm { n m }$ 的狭缝函数曲线  
Fig.5The silt function of $4 5 3 . 8 \mathrm { n m }$ 、 $4 4 5 . 3 \mathrm { n m }$ in different

fields

将高光谱大气微量成份探测仪可见通道输出数据扣除暗电流，利用Savitzky-Golay方法对数据进行平滑降噪处理，归一化后通过拟合可以得到仪器狭缝函数曲线。

曲线拟合函数如公式（6)：

$$
S \left( \lambda \right) = e ^ { - \left( \lambda - \lambda _ { s } \right) ^ { 2 } / \sigma ^ { 2 } } + A _ { 1 } e ^ { - \left( \lambda - \lambda _ { 1 } \right) ^ { 2 } / { \sigma _ { 1 } } ^ { 2 } }
$$

$\lambda _ { s }$ 为峰值对应的中心波长， $\sigma$ 表征仪器狭缝函数的半高宽， $A _ { 1 }$ （2 $\cdot ^ { \sigma _ { 1 } } , \$ $\lambda _ { \mathrm { { _ { l } } } }$ 为仪器狭缝函数的修正系数， $s ( \lambda )$ 为高光谱大气微量成份探测仪输出信号。

由图（5）和图（6）可以看出，拟合曲线能较好的符合函数（6）的分布，边缘视场下的中心波长相较于中心视场下的中心波长存在略微偏移，这是由于大视场成像光谱仪的smile效应造成的，图7为测试的全视场谱线弯曲图，其清楚地显示了全视场下谱线弯曲的程度，弯曲跨度最大为4个像元。因此为了准确描述大视场成像光谱仪的仪器狭缝函数，对高光谱大气微量成份探测仪进行全视场仪器狭缝函数测量是必要的。

![](images/517040642decdd00bb828efcfd1be2e1d066fe5b9087478b13388bd77ded4586.jpg)  
图7全视场下的谱线弯曲现象  
Fig.7Spectral lines bend in full field of view

由公式（6）可以得出高光谱大气微量成份探测仪在波长 $\lambda _ { s }$ 时的光谱分辨率为：

$$
F W H M = 2 \sqrt { \ln 2 } \bullet \sigma
$$

下表为高光谱大气微量成份探测仪狭缝函数测量结果，参数 $\sigma$ 均在 $9 5 \%$ 的置信水平，拟合结果如如表4。

# 表4高光谱仪器在不同视场下的拟合结果

Table 4Fitting Results of Hyperspectral   

<html><body><table><tr><td colspan="5">equipmentindifferent fields</td></tr><tr><td></td><td>R²</td><td>9</td><td>置信区间</td><td>FWHM</td></tr><tr><td rowspan="3">0° 中心</td><td>481.41</td><td>0.9852</td><td>0.304</td><td>(0.2865,0.3217)</td><td>0.5062</td></tr><tr><td>462.68</td><td>0.9916</td><td>0.254</td><td>(0.2428,0.2653)</td><td>0.4229</td></tr><tr><td>453.83</td><td>0.9801</td><td>0.262</td><td>(0.2433,0.2803)</td><td>0.4346</td></tr><tr><td rowspan="3">56° 边缘</td><td>445.32</td><td>0.9739</td><td>0.277</td><td>(0.2548,0.3002)</td><td>0.4612</td></tr><tr><td>481.44</td><td>0.9886</td><td>0.359</td><td>(0.3423,0.3803)</td><td>0.5977</td></tr><tr><td>462.71</td><td>0.9898</td><td>0.291</td><td>(0.2768,0.3062)</td><td>0.4845</td></tr><tr><td>视场</td><td>453.86</td><td>0.9779</td><td>0.287</td><td>(0.266,0.3083)</td><td>0.4779</td></tr></table></body></html>

由上表可以看出，高光谱大气微量成份探测仪光谱分辨率在 $0 . 4 2 3 \mathrm { n m } { } \mathrm { - } 0 . 5 9 7 \mathrm { n m }$ 之间，满足技术指标要求。由于光谱在视场方向会存在光谱弯曲，因此高光谱大气微量成份探测仪在边缘视场的分辨能力略低于在中心视场的分辨能力。

<html><body><table><tr><td>445.34 0.9741</td><td>0.292</td><td>(0.2682,0.3153)</td><td>0.4862</td></tr></table></body></html>

另外，由于狭缝函数测量仪一次能输出多条分立谱线，相比而言，传统谱线灯[15仅有有限的且分布不均匀的特征波长，普通的单色仪一次仅输出一个波长，要完成一个宽谱段的光谱仪光谱定标需要繁杂的过程，在一定程度上影响了宽谱段高分辨率成像光谱仪的光谱定标精度，因此可以利用狭缝函数测量仪同时输出多条高分辨率谱线的特点来进行波长定标，从而提高谱线位置计算精度，实现高精度的光谱定标。

# 3结论

为满足风云卫星高光谱大气微量成份探测反演精度的要求，针对其视场大、波段宽、空间分辨率和光谱分辨率高等特点，研制了狭缝函数测量仪。通过搭建定标装置，测量了高光谱大气微量成份探测仪全视场狭缝函数曲线，并得出了仪器狭缝函数的数学表达式。测试结果表明：高光谱大气微量成份探测仪光谱分辨率在 $0 . 4 2 3 \mathrm { n m } { } \mathrm { - } 0 . 5 9 7 \mathrm { n m }$ 之间，狭缝函数曲线较好的符合高斯分布规律，由于存在光谱弯曲，导致边缘视场分辨能力略低于星下点视场光谱分辨能力。狭缝函数测量仪是基于中阶梯衍射光栅设计，可同时输出多条高分辨率谱线，且分布均匀，不仅可以测量高光谱成像光谱仪的仪器狭缝函数，也可对星载高光谱仪器光谱定标。

# 参考文献：

[1] WANG Yue-ming,LANG Jun-wei,WANG Jian-yu (王跃明，郎均慰，王建宇).Laser &Optoelectronics Progress(激光与光电子学进展),2013,50(1):010008.  
[2] ZHANG Da,ZHENG Yu-quan.（张达，郑玉权).OPTICS& OPTOELECTRONIC TECHNOLOGY(光学与光电技术),2013,11(3): $6 7 { \sim } 7 3$ ：  
[3] XUE Qing-sheng(薛庆生).ACTAOPTICA SINICA （光学学报),2014,8(34):0822005（1） -0822005（6）.  
[4] CHEN Wei, ZHE NG Yu-quan, XUE Qing-sheng(陈伟，郑玉权，薛庆生).ACTA OPTICA SINICA （光学学报），2014,10(43):1022001（1）-1022001（6）.  
[5] CHEN Wei，ZHENG Yu-quan，XUE Qing-sheng（陈伟，郑玉权，薛庆生).ACTA PHOTONICA SINICA（光子学报),2014,10（43)：1022001（1）-1022001（6）.  
[6] XUE Qing-sheng(薛庆生).ACTA OPTICA SINICA (光学学报),2013,3（33） :0322001(1)- 0322001(6).  
[7] ZHOU Bin，LIU Wen-qing，QI Feng，et al（周斌,刘文清,齐峰,等).ACTA PHYSICA SINICA（物理学报),2001,9(50):1818\~1823.  
[8] LI Zhan-feng,WANG Shu-rong,HUANG Yu,et al.(李占峰,王淑荣,黄煜,等).ACTA OPTICA SINICA (光学学报),2013,2(33):0228002（1） -0228002（5）  
[9] ZHENG Yu- quan(郑玉权). Optics and Precision Engineering(光学 精密工程),2010,18(1): 2347～2354.  
[10] Dirksen,Dobber,Voors,et al.Appl Opt,2006,45(17):3972-3981.  
[11] Dirksen R,Dobber ; M, Levelt ,et al. Sensors Systems & Next Generation Satellites VI1, 2004.  
[12] J.de Vries,G.H.J.van den Oord,E.Hilsenrath,M.te Plate,P.Levelt,andR.Dirksen.SPIE,20O1,4880:315-325.  
[13] K.Smorenburg,M.Dobber,E. Schenkeveld,R.Vink,and H.Visser. SPIE,2002,4881:511-520.  
[14] M.R.Dobber,R.J. Dirksen,P.F.Levelt,et al. IEEE,2006,44 (5):1209\~1237.  
[15] LI Cong，WANG Yong-mei（李聪，王咏梅）．Spectroscopy and Spectral Analysis(光谱学与光谱分析），2010,30(12): 3302\~3305.

# A study of the Hyperspectral imaging spectrometer slit function test method

MAO Jing-hua1,2,WANG Yong-mei2\*,SHI En-tao²,ZHAGN Zhong-mou²， JIANG Fang (1.National Space Science Center,Beijing 1Ool90,China

2. University of Chinese Academy of Sciences,Beijing 100190,China)

Abstract: In order to met the needs of high-precision measurements of atmospheric trace constituents,Requires to descript an accurate slit function of the spectrometer. Considering the characteristic of large field ,wide wavelength range,high spatial and spectral resolution,Slit Function measuring device is built.Firstlythe theoryof Slit Function measuring instrument were given. Then based on the instrument,the slit function of Hyperspectral imaging spectrometer were given accurately. The results show that: the slit function of hyperspectral imaging spectrometer fitting Gaussian distribution approximately， Since the large field of the hyperspectral imaging instrument,a phenomenon of smiling was appeared,This result led to the spectral resolution in the edge of he field slightly below that in the center of the field. Overallthe spectral resolution of Hyperspectral imaging spectrometer is better than $0 . 6 \mathrm { n m }$ in the full field.

Key words: Slit Function; Hyperspectral imaging spectrometer ; Echelle grating;