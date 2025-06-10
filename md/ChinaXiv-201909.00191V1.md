# 基于MATLAB的一维光谱可视化与分析工具的设计与实现

张珊瑚,邱丹，聂嘉潞,李崇晟,王习东，田海俊,刘高潮，郑胜（三峡大学天文与空间科学研究中心湖北 宜昌443002）

摘要：随着LAMOST光谱巡天项目的不断推进，国际上积累的光谱数量已经步入千万量级。因科学研究需求或大量低信噪比光谱的不断产出，在光谱处理过程中，常涉及到大量人工识谱的任务。为方便用户高效便捷地进行人工识谱，本文基于MATLAB 编程技术设计并实现了一套一维光谱可视化与分析工具。该工具包括谱线标识、滤波去噪、红移测量、等值宽度估算等功能。该工具操作简单、直观，在特殊天体搜寻，LAMOST“UNKONWN”光谱的人工处理等方面具有较高的使用价值。

关键字：MATLAB；一维光谱；工具；红移测量；等值宽度估算

Design and Implementation of Visualization and Analysis Tool for 1-D Spectrum Based on MATLAB

Zhang Shanhu,Qiu Dan,Nie Jialu, Li Chongsheng,Wang Xidong,Tian haijun,

Liu Gaochao, Zheng Sheng

(Center for Astronomy and Space Science,Three Gorges University, Yichang,Hubei 443002)

Abstract: With the development of LAMOST spectroscopic Sky Survey project, the accumulated spectra in the world have stepped into tens of millions of magnitudes.Due to the need of scientific research or the continuous output of a large number of low signal-to-noise ratio spectra,a large number of manual spectral identification tasks are often involved in spectral processing. In order to facilitate users to carry out manual spectrum recognition efficiently and conveniently,this paper designs and implements a set of one-dimensional spectral visualization and analysis tools based on MATLAB programming technology. The tool includes spectral line identification, filtering and denoising,redshift measurement, and equivalent width estimation. The tool is simple,intuitive operation.It has high application value in the search of special celestial objects and the artificial processing of LAMOST "UNKONWN" spectra.

# Keywords: MATLAB; 1-D spectra;tools; redshift measurement; equivalent width estimation

# 1引言

随着各个大型光谱巡天项目不断地开展，最近十几年来，天文学领域已收集了丰富的天体光谱，这些光谱为科学研究提供了重要的数据基础。我国自主研发的大天区面积多目标光纤光谱天文望远镜(Large Sky Area Multi-Object Fiber Spectroscopy Telescope，LAMOST)[]自2012年正式巡天到2019年3月，已经获取了1125余万条光谱，其中“UNKNOWN”光谱100余万条。随着巡天观测的深入，“UNKONWN”光谱会越来越多。

这些“UNKONWN”光谱大多数因为信噪比较低，传统的算法无法处理；也可能有极少数奇异的天体，由于谱型太奇怪，传统的算法无法识别，如毛晓燕2提出了基于加权滤波的低信噪比LAMOST光纤光谱信号降噪。由于每条光谱的获取成本较高，且这些光谱本身可能含有丰富的科学价值，不能舍弃它们，因此如何识别挖掘这些“UNKONWN”光谱的科学价值是我们急需解决的问题。一些天文学家可以对这些低信噪比光谱进行分类和参数值估计，但是如此巨量的数据仅靠少数的专家利用有限的时间和精力完成人工处理是不可能的，必须开发自动化的光谱分析软件。“工欲善其事，必先利其器”，只有借助良好的光谱分析软件，天文学家才能便捷地对光谱进行分析和研究，从而提高工作效率和科学产出。

国内外专家设计了诸多一维光谱数据可视化与分析软件。比如，欧洲空间局虚拟天文台研发团队开发了VOSpec[3]，可以对光谱进行查询、分析、拟合光谱能量分布；美国空间望远镜科学研究所开发的 SpecView[4]，可以对光谱进行查询、可视化与分析；德国虚拟天文台团队与捷克共和国科学院的天文研究所共同开发的 SPLAT[5]，可以显示、比较、修改和分析天文光谱数据，并且能查询和下载光谱；法国天体物理学和行星学研究开发的CASSIS[6]，可以查询光谱、估算谱线的柱密度等；中国科学院国家天文台开发的ASERA[7]，可以识别类星体光谱和测量红移；雷国洪等人设计了一套基于数据挖掘的专家识谱平台8，可以对光谱数据进行管理、可视化与分析和科学研究与科学普及等。这些软件确实能挖掘天体光谱的科学价值，然而我们发现VOSpec、SpecView、SPLAT 对LAMOST光谱数据存在不兼容现象；ASERA主要针对类星体的光谱而设计，且不能进行滤波去噪、等值宽度估算等。

为此，本文基于MATLAB设计并实现一套一维光谱的可视化与分析工具，重点完成LAMOST“UNKNOWN”的人工处理，其中包括光谱的人工分类、光谱的红移和等值宽度等特征物理参量的测量、特殊天体搜寻等科学目标。设计的可视化界面力求简单直观，适合普通学生使用，通过发动学生力量，逐渐消化不断产生的“UNKNOWN”光谱数据。

# 2一维光谱可视化与分析工具的总体结构设计

本文将设计一个基于MATLAB开源的一维光谱可视化与分析工具，利用MATLAB设计的图形用户界面（MATLABGUI）实现一维光谱的可视化，并结合相关算法实现对光谱进行平滑去噪、红移测量、等值宽度估算等分析功能。一维光谱可视化与分析工具的总体结构设计如图1所示：

![](images/18c6b6c1f57a1b5e53af67d687b02b86d4bf2211bfd099b00ddecfdbcd950252.jpg)  
图1一维光谱可视化与分析工具总体结构设计图

Fig.1 Overall architecture design of 1-D spectral visualization and analysis tool一维光谱可视化与分析工具分为三个部分，分别为数据导入，数据可视化和数据分析。

（1）数据导入：用户将本地光谱数据导入到一维光谱可视化与分析工具中，光谱文件格式主要分为FITS 格式、CSV格式和ASCII格式。LAMOST，SDSS等大型巡天项目的光谱文件通常为FITS格式。

（2）数据可视化：导入光谱数据后，通过MATLAB程序设计实现光谱数据可视化。光谱数据可视化包括特征谱线标识、多光谱加叠、光谱横纵坐标轴设置、谱线类型设置等。标准谱线文件是在静止坐标系下的特征谱线的波长列表，通过导入标准谱线文件来进行谱线标识。

（3）数据分析：数据分析包括红移或视向速度的测量、滤波降噪处理以及等值宽度的估算等。运用定义法计算红移或视向速度，运用小波平滑去噪算法进行光谱去噪处理，运用定义法测量光谱的等值宽度。

# 3一维光谱可视化与分析工具的具体实现

可视化界面设计分为桌面设置、光谱数据导入设置、数据可视化与分析设置三部分，数据分析功能主要包括光谱去噪处理、光谱红移或视向速度的测量和等值宽度测量。这些功能都将通过Matlab编程技术来实现。

# 3.1桌面设置

# 3.1.1桌面颜色设置

用户可根据个人的喜好选择不同的颜色界面，系统设计了6种颜色可供选择,分别为绿色（Summer Greens）、蓝色（Winter Blues）、橙色（Earthy Copper）、粉色（Subtle Pinks）、灰色（GrayTones）和黑色（DarkBlacks）选项。

# 3.1.2Logo图标设置

在图形用户界面的左上角是系统的Logo展示区，用户可设置自己的Logo 图标

# 3.2数据导入设置

光谱数据导入过程如图2所示：

Select a ormultiple fits spectra X← 2018-12-8spec_data 搜索spec_data 0组织 新建文件夹 用 日 ®收藏夹 - 名称 修改日期 类型下线 3c273.fits 2018/12/2516:28 FITS文件夏点面 new.fits 2015/9/2322:09 FITS文件最近访问的位置 new_library.fits 2015/9/23 22:09 FITS文件2345Download: spec-55892-F9202_sp01-143.fits 2012/2/1912:07 FITS文件同库 spec-55920-F5592001_sp09-085.fits 2012/9/1016:43 FITS文件spec-56597-GAC069N36B2_sp08-099... 2017/12/2215:49 FITS文件spec-57416-GAC100N13B1_sp06-046... 2017/12/231:59 FITS文件库 SPLAT1489664908668692061.fits 2018/12/2516:12 FITS文件视频 spSpec-51817-0399-235.fit 2013/5/1010:43 FIT文件图片 spSpec-52201-0692-378.fit 2008/7/37:54 FIT文件文档音乐III文件名（N）： SpectraFitsFiles(.fits,.fit)Load Spectra ... 打开（O） 取消

图2FITS光谱文件导入过程图  
Fig.2 Diagram of importing FITS spectral file

系统仅支持导入一维光谱数据，且主要支持 FITS 文件格式，用户需要将本地FITS 光谱数据上传至系统中。

# 3.3数据可视化设置

# 3.3.1谱线标识

谱线标识能辅助用户识别光谱上主要的特征谱线，在静止坐标系下测得的常见的特征谱线波长如表1所示：

表1常见特征谱线的波长列表（单位： ${ \lambda } / { \mathrm { n m } }$ ）  
Table 1 The wavelength list of some common spectral lines (unit: ${ \mathrm { \lambda } } \lambda { \mathrm { n m } } ,$   

<html><body><table><tr><td>特殊谱线</td><td>O VI</td><td>Ly</td><td>NV</td><td>01</td><td>C I</td><td>SilV</td><td>CIV</td><td>HeII</td><td>OIII</td></tr><tr><td>静止坐标</td><td>1033.8</td><td>1215.7</td><td>1240.8</td><td>1305.5</td><td>1335.3</td><td>1397.6</td><td>1549.5</td><td>1640.4</td><td>1665.8</td></tr><tr><td>特殊谱线</td><td>AlIII</td><td>CIII</td><td>NeIV</td><td>MgII</td><td>Ne V</td><td>NeVI</td><td>OII</td><td>He I</td><td>S II</td></tr><tr><td>静止坐标</td><td>1857.4</td><td>1908.7</td><td>2439.5</td><td>2799.1</td><td>3346.8</td><td>3426.8</td><td>3727.1</td><td>3889</td><td>6718.3</td></tr><tr><td>特殊谱线</td><td>NI</td><td>N II</td><td>Li</td><td>K</td><td>H</td><td>G</td><td>MgI</td><td>NaI</td><td>CaII'</td></tr><tr><td>静止坐标</td><td>6529</td><td>6549.9</td><td>6707.9</td><td>3934.8</td><td>3969.6</td><td>4305.6</td><td>5176.7</td><td>5895.6</td><td>8500.4</td></tr></table></body></html>

点击 Speclines 按钮，系统将根据用户设置的红移值，将特征谱线以虚线的形式显示出来。

# 3.3.2多光谱加叠

点击 Holdon按钮，图形用户界面可以同时导入多条一维光谱，并对这些光谱进行比较分析，点击clear按钮清除可视化界面上的光谱图像。多光谱加叠显示如图3所示：

![](images/e1eb7f4233ec7ccf58257e00ba500c367f00fa1659f87039709a269a7be2d7e6.jpg)  
图3多光谱加叠图  
Fig.3 Diagram of multi-spectrums overlapping

图3中可视化界面显示了两条不同的类星体光谱图像，用红色虚线显示的特征谱线有较强的吸收线，特征谱线MgII发生红移后波长坐标在 $6 5 0 0 { \sim } 6 7 5 0 \mathrm { n m }$ 之间，特征谱线CIII发生红移后波长坐标在 $4 5 0 0 \mathrm { n m }$ 左右。

数据可视化还包括对光谱图像进行网格划分、改变光谱横纵坐标轴的范围、设置谱线类型和设置图形用户界面的标题，用户可以根据自己的需求在可视化界面的编辑框进行设置。

# 4光谱数据分析功能的实现

根据彭广民[10]等人的小波去噪方法，李天超[1]等人的等值宽度算法以及刘蓉[12-13]等人的红移测量和谱线证认方法，本文运用MATLAB编程技术实现了光谱平滑去噪处理、红移测量和等值宽度测量等光谱分析功能。

# 4.1光谱平滑去噪算法

小波去噪方法既能去除图像中的噪音，又可以尽可能地保留图像局部的细节，因此小波

去噪法可以很好的对光谱进行平滑去噪处理。

# 4.1.1光谱平滑去噪法的原理

设 $( x , y )$ 为图像中点的坐标， $f ( x , y )$ 为含有噪声的图像， $e ( x , y )$ 为图像上噪音干扰，$\sigma$ 是噪声方差。图像去噪后可以表示为：

$$
g ( x , y ) = f ( x , y ) - \sigma e ( x , y ) , ( x = 3 7 0 0 , 3 7 0 1 , . . . , 9 0 0 0 ; y = - 1 0 , - 9 , . . . , 1 0 )
$$

小波去噪的主要步骤：

（1）对 $f ( x , y )$ 作小波变换，得到各尺度的小波系数 $w _ { ( j , k ) }$ ；（2）设定各分解层阈值，对小波系数 $w _ { ( j , k ) }$ 进行阈值处理，得到小波估计系数 $\hat { w } _ { ( j , k ) }$ ；（3）重构小波系数，再利用小波估计系数 $\hat { w } _ { ( j , k ) }$ 进行重新构造得到去噪处理后的图像（204号 $\hat { \boldsymbol f } ( x , y )$ 。

# 4.1.2阈值函数选择

阀值的确定和对小波系数的阀值处理是小波去噪的关键，这里选择半软阀值法进行阈值处理:

$$
\hat { w } _ { ( j , k ) } = \left\{ \begin{array} { l l } { \mathrm { s g n } \Big ( w _ { ( j , k ) } \Big ) \Big ( \Big | w _ { ( j , k ) } \Big | - \alpha \lambda \Big ) } & { ( w _ { ( j , k ) } \geq \lambda ) } \\ { 0 } & { ( w _ { ( j , k ) } < \lambda ) } \end{array} \right.
$$

其中， $w _ { ( j , k ) }$ 为处理前的小波系数， $\hat { w } _ { ( j , k ) }$ 为处理后的小波系数， $\lambda$ 为阀值，且 $0 < \alpha < 1$ 。

# 4.1.3光谱平滑去噪结果

本文将光谱平滑程度设置成6个等级，分别为3、5、7、9、11和13（单位：pix），平滑程度为3pix和11pix的光谱图去噪效果如图4所示：

![](images/add5e3f4a90019eca23c3e68c8ecbfb931e354fc4498b6851b3b6d7e7e329d29.jpg)  
图4光谱去噪程度比较图  
Fig. 4 Comparisons of spectral denoising

从上图可以看出，平滑程度为11pix 的光谱图比平滑程度为3pix的光谱图更平滑，视觉

效果更好，但是11pix 可能会损伤部分微小的光谱特征，比如 AII等。因此，用户需要根据自己的需求来选择平滑程度。

# 4.2红移或视向速度测量算法

在物理学和天文学领域，红移现象指物体的电磁辐射由于某种原因使波长被拉伸的现象，具体表现为光谱的谱线朝红端移动了一段距离，即波长变长，频率降低。红移现象目前多用于天体的移动以及规律的预测上，红移值是河外天体最重要的物理参数之一。

# 4.2.1红移测量法的原理

设谱线的静止波长为 $\lambda ^ { \prime }$ ，观测波长为 $\lambda$ ， $z$ 为红移值，则

$$
\lambda = ( 1 + z ) \lambda ^ { \prime }
$$

$$
z = \frac { \lambda } { \lambda ^ { \prime } } - 1
$$

谱线的静止波长 $\lambda ^ { \prime }$ 如表1所示，根据可视化界面的特殊谱线位置确定观测波长λ后，将观测波长输入到编辑框，点击enter键，得到特殊谱线的红移值。

# 4.2.2红移测量结果

本文以三条光谱测量为例，运用一维光谱可视化与分析工具测得光谱的特征谱线 II和 $\mathbf { M g } \mathbf { I I }$ 的红移值如表2所示：

表2光谱特征谱线红移值Table2ofSpectral redshift  

<html><body><table><tr><td>光谱文件名</td><td>C III</td><td>MgII</td></tr><tr><td>spSpec-51817-0399-235.fit</td><td>1.3566</td><td>1.3675</td></tr><tr><td>spSpec-52201-0692-378.fit</td><td>1.3570</td><td>1.3656</td></tr><tr><td>spSpec-55920-F5592001-sp09-085.fits</td><td>1.3587</td><td>1.3636</td></tr></table></body></html>

# 4.3等值宽度测量算法

等值宽度，即与吸收（或发射）谱线轮廓和连续谱之间所包围的面积相当的高度为1的矩形的宽度。

# 4.3.1等值宽度测量法的原理

下面以一观测光谱上CIII谱线为例，概述天体特征谱线等值宽度的测量方法（如图5所示）。

![](images/3ce116c84f610507f5d5de37df1d7cb9b2d7b59559b566d9254d97921b215bff.jpg)  
图5CIII的等值宽度测量示意图  
Fig.5 Chart of equivalent width measurement for CIII

已知特征谱线峰值的取值范围是 $\left[ \left( w l _ { 1 } , f l _ { 1 } \right) , \left( w l _ { n } , f l _ { n } \right) \right]$ ，峰值左边点的取值范围是$\left[ \left( a _ { 1 } , b _ { 1 } \right) , \left( a _ { j } , b _ { j } \right) \right]$ ,峰值右边点的取值范围是 $\left[ { \left( { { c _ { 1 } } , { d _ { 1 } } } \right) , \left( { { c _ { k } } , { d _ { k } } } \right) } \right]$ ,峰值左边点的坐标 $\left( w c 1 , f c 1 \right)$ 为：

$$
w c 1 = \frac { \sum a _ { j } } { j }
$$

$$
f c 1 = \frac { \sum b _ { j } } { j }
$$

峰值右边点的坐标 $\left( w c 2 , f c 2 \right)$ 为：

$$
\begin{array} { c } { { w c 2 = \displaystyle \frac { \sum _ { c _ { k } } } { k } } } \\ { { { } } } \\ { { f c 2 = \displaystyle \frac { \sum _ { d _ { k } } } { k } } } \end{array}
$$

$\left( w l _ { i } , f c _ { i } \right)$ 是坐标 $\left( w c \mathbf { l } , f c \mathbf { l } \right)$ 和坐标 $\left( w c 2 , f c 2 \right)$ 连接线上的一点， $\left( w l _ { i } , f c _ { i } \right)$ 的值为：

$$
f c _ { i } = \frac { \big ( f c 2 - f c 1 \big ) } { \big ( w c 2 - w c 1 \big ) } \big ( w l _ { i } - w c 1 \big ) + f c 1
$$

等值宽度的计算结果为：

$$
e w = \int _ { w l _ { 1 } } ^ { w l _ { n } } \left( 1 - \frac { f c _ { i } } { f l _ { i } } \right) d w l
$$

# 4.3.2等值宽度测量结果

本文以三条光谱测量为例，运用一维光谱可视化与分析工具测得光谱的特征谱线 II和MgII的等值宽度值如表3所示：

表3光谱特征谱线等值宽度  
Table 3of Spectral Equivalent Width   

<html><body><table><tr><td>光谱文件名</td><td>C III MgII</td></tr><tr><td>spSpec-51817-0399-235.fit</td><td>58.592 73.492</td></tr><tr><td>spSpec-52201-0692-378.fit</td><td>53.797 67.268</td></tr><tr><td>spSpec-55920-F5592001-sp09-085.fits</td><td>59.297 35.366</td></tr></table></body></html>

# 5总结与展望

LAMOST、2dF、SDSS等国际上大型巡天项目不断获取大量的光谱数据，这些光谱为天文学研究提供了重要的数据基础。为方便用户深度挖掘这些光谱的科学价值，本文基于Matlab 研发了一套一维光谱可视化与分析工具。该工具具备以下几个方面的优势：

（1）针对一维光谱数据，集成多种可视化与分析算法，方便用户简单快捷地计算出光  
谱的红移或视向速度、等值宽度等重要物理参数。（2）界面简洁，操作步骤简单，用户只需要掌握可视化界面的操作方法，就可以对光  
谱进行分析处理。（3）能像 SPLAT-VO等项目一样，实现一维光谱数据可视化与分析，提高天文学家光

谱处理的效率。

我们会根据需求进一步完善该工具功能，借鉴国际上优秀的光谱可视化软件优势，最终使其成为处理LAMOST、SDSS 等光谱数据的首选工具。

# 参考文献

[1]施建荣.LAMOST望远镜[J].科学通报,2016,61(12):1330-1335.  
[2]毛晓艳,张博,叶中付.基于加权滤波的低信噪比LAMOST光纤光谱信号降噪[J].天文研究与技术,2015,12(4):447-454.  
[3] Osuna P, Barbarisi I, SalgadoJ, et al. VOSpec: a tool for handling virtual observatory compli-ant spectra [C] // Astronomical Society of the Pacific Conference Series. 2Oo5: 198202.  
[4] Busko I. Specview: a Java tool for spectral visualization and model fiting [C]//Proceedings ofthe SPIE.2002: 410-418.  
[5] Skoda P,PerP W,Neves M C, et al. Spectroscopic analysis in the virtual observator environ-ment with SPLAT-VO[J]. Astronomy & Computing,2014,7: 108-120.  
[6] Lebouteiller V,Barry D J, Spoon H W W, et al. CASSIS: the cornellatlas of spitzer / infraredspectrograph sources []. Astrophysical Journal Supplement, 2011，196(1): 849-856.  
[7] Yuan Hailong, Zhang Haotong, Zhang Yanxia, et al. ASERA: a spectrum eye recognitionassistant for quasar spectra[J]. Astronomy & Computing,2O13,3-4: 65-69.  
[8]雷国洪,徐洋,牛晨辉,田海俊,张彦霞,崔辰州,赵永恒.专家识谱平台的设计与实现[J].天文研究与技术,2018,15(02):216-224.  
[9]王文成,李健,王瑞兰,吴小进,孙学岩.基于MatlabGUI的数字图像处理仿真平台设计与开发[J].实验技术与管理,2019,36(02):141-144.  
[10]彭广民,陈婷.基于Matlab 小波去噪的研究方法[J].测绘与空间地理息,2016,39(07):24-26.[11]李天超,邓李才,赵刚.漩涡星系M31和椭圆星系M32CaⅡI三重线的等值宽度[J].光谱学与光谱分析,2000(04):468-470.  
[12]刘蓉,段福庆,刘三阳,吴福朝.基于知识的红移测量和谱线证认方法[J].电子与信息学报，2006(01):76-79.  
[13]屠良平,罗阿理,姜斌,韦鹏,赵永恒,刘蓉.一种新的活动星系光谱红移自动测量方法[J].光谱学与光谱分析,2012,32(10):2858-2862.