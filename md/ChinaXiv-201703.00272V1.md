# 基于中阶梯光栅的波长定标方法的研究

毛靖华1,²，王咏梅\*，石恩涛'，张仲谋，江芳1（1.中国科学院国家空间科学中心2.北京100190;2.中国科学院大学 北京 100190)

摘要：光谱定标是仪器遥感数据定量化的前提和基础，针对星载大气微量成分探测仪视场大、波长宽、空间分辨率和光谱分辨率高的特点，建立了基于中阶梯衍射光栅的光谱定标装置。中阶梯光栅因其较少的线密度和较大的闪耀角工作在较高的闪耀级次，光谱范围宽且具有较高的分辨率，可在工作波段内一次性输出多条分布较为均匀的谱线，克服了传统定标方式的缺点，提高了定标精度。本文首先介绍了光谱定标装置的工作原理，接着利用该装置对高光谱大气微量成份探测仪进行光谱定标，通过寻峰和回归分析给出载荷的光谱定标方程，并利用标准汞灯谱线对定标结果进行检验。结果表明：高光谱大气微量成份探测仪的像元和波长近似满足线性分布规律，定标不确定度为$0 . 0 2 5 8 \mathsf { n m }$ ，汞灯特征谱线的定标值和标准值偏差最大不超过0.0435nm，证明了定标结果的准确性。

关键词：波长定标；中阶梯光栅；星载大气微量成分探测仪；光栅衍射方程中图分类号：TG502.33；TH744 文献标识码：A 文章编号：

# Research of spectral calibration based on echelle MAO Jing-hua1²,WANG Yong-mei2\*,SHI En-tao², ZHAGN Zhong-mou²， JIANG Fang

(1.National Space Science Center,Beijing 1Oo19o,China

2.University of Chinese Academy of Sciences,Beijing 1Oo19o,China)

Abstract: Spectral calibration is the premise ofremote sensing data inversion. Considering the characteristic of large field ,wide wavelength range, high spatial and spectral resolution,the Spectral calibration equipment is built. The Spectral calibration equipment is based on echelle.Echelle has large blaze angle work at a higher blazed order, The echelle is charactered by wide spectrum range and high spectral resolution, it can output multiple spectral lines and distribution uniformity in the detection band,overcome the shortcomings of the traditional calibration methods and improve the calibration accuracy. Firstly the theory of the Spectral calibration equipment were given. Then use the equipment, the Spectral calibration equation of the hyperspectral imaging spectrometer were given accurately by peak-searching and regression analysis, finally using the unique characteristics of mercury spectral lines validate the results.The results showed that: Pixel and wavelength of the hyperspectral atmospheric trace elementsapproximation meet the linear distribution， The uncertainty of the wavelength calibration is $0 . 0 2 5 8 \mathrm { n m }$ ，The maximum deviation of calibration values and standard deviation values of the mercury spectral lines is $0 . 0 4 3 5 \mathrm { n m }$ ，proved the accuracy of the calibration results.

# Key words: Spectral calibration; Echelle grating;Hyperspectral imaging spectrometer; Grating equation

# 0引言

为满足我国环境污染监测的迫切需求，研制了风云卫星高光谱大气微量成份探测仪。高光谱大气微量成份探测仪是以差分光学吸收光谱法 DOAS[](Differential Optical Absorption Spectroscopy)为探测原理的成像光谱仪。高光谱大气微量成份探测仪探测光谱范围 $3 7 5 \mathrm { n m } { - } 5 0 0 \mathrm { n m }$ ，总视场 $1 1 2 ^ { \circ }$ ，光谱分辨率约$0 . 4 \mathrm { - } 0 . 6 \mathrm { n m }$ ，通过在卫星上探测大气后向散射辐射，利用DOAS算法解析微量气体成分的分布和变化，实现我国对大气微量成分全球探测。

定标是高光谱大气微量成份探测仪精确定量化应用的前提和基础，其中一项主要的定标是光谱定标[2]。光谱定标可以确定遥感仪器光谱特性指标，进而为提高仪器本身可靠性提供依据。因此为了保证高光谱大气微量成份探测仪能够高精度反演微量气体含量及变化，发射前需要对仪器进行光谱定标。传统的光谱定标利用标准谱线灯[3-5]或者可调激光器作为光源，谱线灯在遥感仪器工作范围内只能提供有限条且分布不均匀的谱线，对高分辨率光谱仪波长定标精度影响较大；可调激光器一次只能对一个波长的位置进行定标，定标高光谱仪器时需要定标多条谱线，花费时间长且不易操作，受扫描仪器的影响，每次引入的误差不一样，影响波长定标精度。

针对大气微量成分探测仪视场大、探测波段宽空间分辨率和光谱分辨率高的特点，研究了相应的光谱定标方法，研制了一套基于中阶梯衍射光栅的光谱定标实验装置，实现了仪器全视场精确光谱定标，分析了光谱定标不确定度，并利用汞灯谱线对定标结果进行了检验。中阶梯光栅因其较少的线密度和较大的闪耀角工作在较高的闪耀级次，光谱范围宽且具有较高的分辨率，基于中阶梯衍射光栅的光谱定标装置可以在工作波段内一次性输出多条分布较为均匀的高分辨率谱线，克服了传统定标方式的缺点，提高了定标精度，为后续光谱定标提供了经验。本文首先介绍了基于中阶梯光栅衍射的定标装置的工作原理，然后对大气微量成份探测仪进行光谱定标，最后对定标结果进行分析和评估。

# 2定标装置的工作原理

# 2.1定标装置的工作原理及光路图

根据光栅衍射方程：

$$
\sin \alpha + \sin \beta = m \lambda / d
$$

式中α为光线入射角，β为衍射角， $\mathbf { m }$ 为衍射级次，入为中心波长，d为光栅常数。

推导出光栅倒线色散公式：

$$
\frac { d \lambda } { d l } { = } \frac { 1 0 ^ { 6 } \cos \beta } { m n f }
$$

$\mathfrak { n }$ 为光栅刻线密度，dI为出射狭缝宽度，f为出射焦距长度。对公式（2）进行变形可得如下式：

$$
d \lambda = \frac { 1 0 ^ { 6 } \cos { \beta } } { m n f } d l
$$

公式（3）为狭缝宽度对应的光谱增宽，即不同波长对应的光谱分辨率。

为满足大气微量成份探测仪光谱定标需求，要求定标仪器的光谱分辨率为待测仪器光谱分辨率的五分之一到十分之一，光谱定标装置结构图如图 $1 ^ { [ 7 ] }$ 所示：

光栅刻线为79.01grooves/mm,衍射角为 $7 1 . 5 ^ { \circ }$ ，根据公式(2)，当准直镜焦距 $\mathrm { f = 6 1 5 . 8 9 4 m m }$ 时，对$3 7 0 \mathrm { n m } { - } 5 0 5 \mathrm { n m }$ 光谱范围，狭缝函数测量仪的光谱分辨率为 $0 . 0 3 9 4 \mathrm { n m } { - 0 . 0 5 7 8 \mathrm { n m } }$ ，可满足定标要求。

# 2.2定标装置光源的选择

为保证定标装置对 $3 7 5 { - } 5 0 0 \mathrm { n m }$ 光谱范围的全覆盖，定标光源选用日本浜松公司生产的L2479型超静氙灯，该光源具有输出功率高、光能分布稳定等特点，光源主要辐射特性见表1。

表1L2479的主要辐射特性  
Table1Radiationcharacteristic ofL2479   

<html><body><table><tr><td rowspan="2">型号</td><td rowspan="2">功率W</td><td rowspan="2">弧长mm</td><td>光强uW/cm2.nm@50cm</td></tr><tr><td>λ440nm</td></tr><tr><td>L2479</td><td>300</td><td>3.0</td><td>5.06</td></tr></table></body></html>

![](images/c2da6b60d5a3ee5a1c3fff19282251b9436e6e3d11c441b389856adcd9d00cdf.jpg)  
Fig.1 Standard of calibration equipment

![](images/e02c3471f08a3f4fb5b2be1b172f65615969e70d1750ce0635ce6d6d810763e2.jpg)  
图1光谱定标装置结构图  
图2光谱定标装置输出的光谱图  
Fig.2 The spectrum of the calibration equipment

# 2.3定标装置的输出谱线及分辨率

利用Andor公司生产的型号为SR-2234的光谱仪对定标装置输出谱线进行测量，得到光谱图如图2，输出谱线的中心波长及分辨率如表3所示：

# 表2定标装置的中心波长及分辨率

Table 2. Central wavelength and spectral resolution of the equipment   

<html><body><table><tr><td>衍射级次</td><td>中心波长（nm)</td><td>光谱分辨率（nm)</td></tr><tr><td>64</td><td>375. 79838</td><td>0.0453213</td></tr><tr><td>63</td><td>381. 74951</td><td>0.0488178</td></tr><tr><td>62</td><td>387.8958</td><td>0.04960035</td></tr><tr><td>61</td><td>394.27375</td><td>0.0492507</td></tr><tr><td>60</td><td>400.8544</td><td>0.0496503</td></tr><tr><td>59</td><td>407. 63776</td><td>0. 0497169</td></tr><tr><td>58</td><td>414. 65417</td><td>0.04956705</td></tr><tr><td>57</td><td>421. 94558</td><td>0.05036625</td></tr><tr><td>56</td><td>429.4562</td><td>0.0538461</td></tr><tr><td>55</td><td>437. 25177</td><td>0.05093235</td></tr><tr><td>54</td><td>445. 35962</td><td>0.05592735</td></tr><tr><td>53</td><td>453. 74517</td><td>0.0532467</td></tr><tr><td>52</td><td>462. 46239</td><td>0.05745915</td></tr><tr><td>51</td><td>471. 54292</td><td>0.0568098</td></tr><tr><td>50</td><td>480.96176</td><td>0.0564435</td></tr><tr><td>49</td><td>490. 78022</td><td>0. 05755905</td></tr><tr><td>48</td><td>500.9942</td><td>0. 05842485</td></tr></table></body></html>

由表2可以看出，中阶梯衍射光栅定标装置可以在 $3 7 5 \mathrm { n m } { - } 5 0 0 \mathrm { n m }$ 同时输出多条高分辨率谱线，利用该特点进行对高光谱分辨率成像光谱仪进行光谱定标，可以保证谱线位置计算精度，实现高精度的光谱定标。

# 3实验的过程及结果

# 3.1实验的过程

星载大气微量成分探测仪的光谱定标任务是确定出每个像元对应的工作波长，从而确定出仪器的探测波段和光谱分辨能力。由于该载荷大视场探测的特点，会出现谱线弯曲的现象，因此，为了更准确的波长定标，需要标定全视场每个像元的工作中心波长，确定出波长随光谱维和空间维的分布矩阵，实验装置如图3所示，由光源、中阶梯衍射光栅定标装置、高精度转台、高光谱大气微量成份探测仪和计算机组成。

![](images/da854b2708e246456543d89cdf431dd376fe65ca3b18d5a3f6e486272f5b447a.jpg)  
图3实验装置示意图

点亮光源，待氙灯稳定 $1 0 \mathrm { { m i n } }$ 后开始测量，通过调整仪器积分时间和增益以保证获得较高的信噪比。记录CCD感光区域光谱数据 $S _ { i m } - S _ { j n }$ 。i、j代表空间维行号，m、n代表光谱维列号。每隔 ${ 1 0 } ^ { \circ }$ 转动转台，记录下光谱数据 $S _ { i _ { m } } - S _ { { \scriptscriptstyle j } _ { n } }$ ，重复该过程，记录下全视场的光谱数据。

# 3.2数据的处理与分析

仪器的光谱定标过程主要包括寻峰和最小二乘法回归。对于每条光谱，首先通过寻峰处理找出特种谱线对应的像元，然后采用最小二乘法将波长和像元进行回归分析，得到仪器的光谱定标方程，最后根据定标方程，可以计算出探测通道的光谱范围。

将星载大气微量成分探测仪的光谱数据扣除暗计数，选取信噪比较高的几条谱线，由于高斯函数可以较好的表征光谱响应，因此采用Gauss拟合的方法寻峰，拟合函数如公式（4）所示：

$$
S ( X ) = A _ { 0 } { \mathrm { e } } ^ { - { \frac { \left( X - x _ { 0 } \right) ^ { 2 } } { \sigma ^ { 2 } } } }
$$

其中 $S ( X )$ 代表大气微量成分探测仪的仪器计数，

X为像元序号， $A _ { 0 }$ 为拟合系数， $x _ { 0 }$ 为谱线中心峰对应像元号， $\sigma$ 为谱线半高宽。图4为大气微量成分探测仪中心视场 $4 6 2 . 4 6 \mathrm { n m }$ 的光谱响应曲线。

![](images/7bc63a7059976a14f4bb5f38c221d6189df1c9ec35ed3489172fa3c7116dc5f5.jpg)  
图4462.46nm光谱响应曲线

通过拟合，确定出峰中心对应像元号为490.959，即该像元号和波长 $4 6 2 . 4 6 \mathrm { n m }$ 对应。利用寻峰处理，可以得出中心波长和像元的对应关系 $\left[ X _ { \scriptscriptstyle i m } , \lambda _ { \scriptscriptstyle i m } \right]$ ，其中i为行号， $\mathrm { m }$ 为列号， $\lambda _ { i m }$ 为中心波长， $X _ { _ { i m } }$ 为中心波长对应的像元号。由于光谱在CCD上近似成线性排列，所以采用最小二乘法对数据组进行线性回归分析，回归方程如公式（5）和公式（6)。

$$
\lambda _ { i m } ( X _ { i m } ) = a X _ { i m } + b ( 5 )
$$

$$
\left\{ \begin{array} { l l } { \displaystyle { a = \frac { \displaystyle \sum _ { m = 1 } ^ { n } \left( X _ { i m } - \overline { { X _ { i } } } \right) \left( \lambda _ { i m } - \overline { { \lambda _ { i } } } \right) } { \displaystyle \sum _ { m = 1 } ^ { n } \left( X _ { i m } - \overline { { X _ { i } } } \right) ^ { 2 } } } } \\ { \displaystyle { b = \overline { { \lambda _ { i } } } - a \overline { { X _ { i } } } } } \end{array} \right.
$$

图5为星载大气微量成分探测仪在中心视场的回归结果：

![](images/3246ef0800e39858b19470baaff311b78d53a2ac733b6428b98fc3f66eb41177.jpg)  
Fig.3Experiment diagram of spectral calibration   
图5星载大气微量成分探测仪在中心视场的回归直线

Fig.5 The line of Hyperspectral imaging spectrometer in center area of FOV图中实心圆点代表中阶梯衍射光栅定标装置的输出波长，直线为定标方程。定标方程如公式（7)，

$$
\lambda _ { _ { i m } } ( X _ { _ { i m } } ) = - 0 . 1 7 1 6 7 X _ { _ { i m } } + 5 4 6 . 7 3 9 7 ( 7 )
$$

回归系数 $R ^ { 2 } = 0 . 9 9 9 9$ ，说明波长和像元近似满足线性关系，图6为回归残差图，

![](images/fa406e099022b6745d1c35b19a9f133dd1b52d940307bb51d2013820d04d11d0.jpg)  
图6回归直线残差图  
Fig.6 Residual plot of the regression line

横坐标代表参与回归的点的序号，纵坐标代表残差。从图中可以看出，参与回归的点置信区间均包括零点，没有奇异点，最大偏差不超过 $0 . 0 4 \mathrm { n m }$ ，再次说明了像元与波长的关系较好的满足回归直线，根据回归方程计算出探测波段为 $3 7 0 \mathrm { m n m } { \cdot } 5 1 0 \mathrm { n m }$ ，满足$3 7 5 \mathrm { n m } { - } 5 0 0 \mathrm { n m }$ 的设计要求。

# 3.3不确定度分析

星载大气微量成分探测仪的波长定标不确定度主要包括定标光源的不稳定性、寻峰误差、回归分析误差。

光谱定标装置的输出光谱不确定度取决于SR-2234单色仪测量不确定度，SR-2234单色仪的测量不确定度为 $0 . 0 1 \mathrm { n m }$ ；谱峰定位的不确定度主要由大气微量成份探测仪的稳定性以及采用算法等引起，不确定度优于0.1个像元;回归分析的不确定度由残差标准差来表征。误差传递公式为：

$$
\sigma = \sqrt { \sigma _ { 1 } ^ { 2 } + \sigma _ { 2 } ^ { 2 } + \sigma _ { 3 } ^ { 2 } } ( 7 )
$$

其中 $\sigma$ 为大气微量成分探测仪总的波长定标不确定度， $\sigma _ { \scriptscriptstyle 1 }$ 为光谱定标装置的输出光谱不确定度， $\sigma _ { 2 }$ 为谱峰定位不确定度， $\sigma _ { 3 }$ 为回归分析不确定度。通过误差传递公式可以分析出大气微量成分探测仪中心视场的波长定标不确定度如表3所示：

# 表3波长定标不确定度分析

Table 3.Uncertainty analysis of spectral calibration

<html><body><table><tr><td>01 （nm）</td><td>（nm） 62</td><td>（nm） 03</td><td>9 （nm）</td></tr><tr><td>0.01</td><td>0.0172</td><td>0.0165</td><td>0.02584</td></tr></table></body></html>

# 3.4定标结果的检验

利用标准汞灯谱线对波长定标结果进行检验，光谱的波长信息由定标方程获取，通过对比汞灯特征谱线的定标值和标准值来验证星载大气微量成分探测仪波长定标的准确性。表4给出了定标波长和标准波长的对比结果：

# 表4定标波长与标准波长的对比

Table 4.The comparison of the calculated value and standard values   

<html><body><table><tr><td>标准波长（nm)</td><td>定标波长（nm)</td><td>偏差绝对值 (nm）</td></tr><tr><td>435.8335</td><td>435.7948</td><td>0.0387</td></tr><tr><td>407.7837</td><td>407. 7749</td><td>0.0087</td></tr><tr><td>404.6565</td><td>404.6130</td><td>0.0435</td></tr></table></body></html>

对比结果表明，峰位偏差绝对值最大不超过$0 . 0 4 3 5 \mathrm { n m }$ ，说明了光谱定标方程的准确性。

# 3结论

本文研究了星载大气微量成分探测仪的光谱定标技术。针对载荷大视场、宽探测波段的特性，确定了大气微量成分探测仪光谱定标方案，选取超静氙灯作为定标光源，构建了基于中阶梯衍射光栅的光谱定标装置，对仪器进行了光谱定标。光谱定标装置在 $3 7 5 \mathrm { n m } { - } 5 0 0 \mathrm { n m }$ 范围内一次性输出多条分布较为均匀的高分辨率谱线，相比传统光谱定标方式，不仅可以提高定标效率，而且还能提高光谱定标精度，通过数据处理后得到光谱定标方程，并通过标准汞灯谱线对定标结果进行检验。结果表明：大气微量成分探测仪的像元与波长的关系较好的符合回归直线，回归系数 $R ^ { 2 } = 0 . 9 9 9 9$ ，探测范围为$3 7 0 \mathrm { n m } { - } 5 1 0 \mathrm { n m }$ ，满足设计要求。通过对定标不确定度的分析，定标不确定度为 $0 . 0 2 5 8 \mathrm { n m }$ ，为后续星载大视场成像光谱仪的光谱定标工作积累了经验。

# 参考文献：

[1] 周斌,刘文清,齐峰,等．差分吸收光谱法测量大气污染中数据处理方法研究.物理学报,2001,9(50):1818\~1823.  
[2] 赵敏杰,司福祺,江宇,等．星载大气痕量气体差分吸收光谱仪的实验室定标［J].光学 精密工程，2013，3(21)：567-573.  
[3] 郑玉权．超光谱成像仪的精细光谱定标[J]．光学 精密工程，2010，18(11)：2347～2354.  
[4] 周海金,刘文清,司福祺,等．星载大气痕量气体差分吸收光谱仪光谱定标技术研究[J].光谱学与光谱分析，2012，11(32) : 2881-2885.  
[5] 李聪，王咏梅.用PtNe 灯对大气紫外成像光谱仪进行光谱定标[J].光谱学与光谱分析，2010,30(12)：3302\~3305.  
[6] 裴舒．成像光谱仪光谱定标.光机电信息,2011,28(11): $4 8 { \sim } 5 1$ ：  
[7] 毛靖华,王咏梅,石恩涛,等．星载高光谱成像光谱仪狭缝函数测试方法的研究[J].光谱学与光谱分析，2017，37(3).