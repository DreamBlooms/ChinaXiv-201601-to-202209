# R语言应用于LAMOST光谱分析初探

陈淑鑫1,²，罗阿理³，孙伟民²（1.齐齐哈尔大学机电工程学院，黑龙江 齐齐哈尔161006；2.哈尔滨工程大学理学院纤维集成光学教育部重点实验室，黑龙江 哈尔滨150006；3.中国科学院光学天文重点实验室，北京 100012)

摘要：以可扩展性极强的开源软件R程序语言为工具，发挥在统计学和数据挖掘领域强大的数据分析能力，重点研究R语言用于读写FITS格式文件软件包RFITSIO的主要功能和特点，并对LOMAST采集的FITS文件进行详细介绍，将海量LOMAST巡天光谱DR2数据用RFITSIO读出恒星光谱，并利用R语言的主成分分析工具提取各类型光谱数据的特征量即主成分。从含有大量冗余信息的光谱中提取代表恒星光谱特征的主要成分，通过采用主成分分析方法提取光谱特征，重构后能够有效降低原始光谱数据受噪声的影响，为后续数据挖掘工作提供研究基础。

关键词：R语言；FITSIO；光谱巡天；LAMOST；主成分分析中图分类号：P114.1 文献标识码：A 文章编号：1672-7673(2017)03-0363-06

R 程序语言是集成了多种数据分析和可视化方法的开源软件，已成为信息时代大数据分析的重要工具，并在统计学和数据挖掘领域可扩展性极强，具备强大的数据分析能力，能有效地简化数据分析的过程。为了将R语言的优势应用到天文数据分析中，首先需要了解天文数据的格式。国际通用天文数据格式的标准是普适图像传输系统[1]（Flexible Image Transport System，FITS），该格式由文[1]于1979 年首先提出，用于描述天文学数据定义和数据本身编码的格式方法，已成为天文学领域应用最广泛的数据格式。前人已将FITSIO 软件包应用于FORTRAN语言、C语言、IDL 语言中，编写读取FITS 文件，分析天文数据读取等大量的相关工作。文[2-3]概述了FITS文件的标准数据格式以及3种类型即图像文件、ASCII表文件和二进制表文件等，文[2]对FITS 基本格式及其扩展进行了较详细的分析阐述，文[3]对g、r、i3个波段的FITS 图像文件进行了重新读写，分析了斯隆数字巡天的测光数据，文[4］利用数据库保存和管理FITS 头信息归档入库，提供光谱数据文件的查询检索。近年来，由于R语言在各专业的统计领域广泛应用，已经有美国马里兰大学Andrew Harris 等①用R语言编写了读取FITS 的软件包RFITSIO。

国内外已相继开展了多个天文大规模巡天项目[5]，如 $2 \mathrm { d F }$ 、6dF、RAVE、SDSS、LAMOST和Gaia等，这些大规模光学光谱巡天已获取数以十万、百万甚至千万计的天体光谱[6]。2013年我国自主研发的大天区面积多目标光纤光谱望远镜[7]（Large Sky Area Multi-Object Fiber Spectroscopy Telescope，LAMOST)是目前世界上口径最大、视场范围广、观测目标最多、天体光谱获取率最高的光纤光谱望远镜，获取的FITS格式光谱大数据信息达 ${ 1 0 } ^ { 7 }$ 数量级。LAMOST目前已经对国际公开发布了巡天数据约380万条，其中未能被软件识别的有306 810条。由于大数据导入时包含了大量的冗余信息，所以恒星光谱的全频谱信号充分利用多元统计分析（Multivariable Statistical Analysis)这些数据，本文利用 R语言提供的数据挖掘工具，通过主成分分析方法消除流量特征之间的相关性，从原始光谱数据中提取与物理参数相关的特征，降维数据并剔除噪声。

# LAMOST光谱数据FITS格式

20世纪80年代，国际天文联合会正式公布FITS格式作为天文数据的国际标准，世界各地的数据中心和天文学家以此文件为标准，完成了相关研究的保存和数据交换。LAMOST中FITS 文件已发布的文件名格式为 spec-MMMMM-YYYY_spXX-FFF.fits，扩展名.fits，其中，MMMMM代表当地修正的儒略日（MJD，即公元前4713年1月1日起计），YYYY 是计划标识的字符串（PLANID，即计划号）,XX表示光谱仪的数字编号（在1到16之间），并且FFF显示了采集光谱的光纤编号（在1到255之间）。此外，LAMOST还通过设计关键字“LAMOSTJHHMMSS.ss $^ +$ DDMMSS.ss”的形式指定对应一个目标文件，其中HHMMSS.ss 是以时分秒为单位的赤经值，DDMMSS.ss是以度分秒为单位的赤纬值，在 FITS 文件的基本头部单元，可选择符合扩展以及其他可选择的特殊记录，并将头文件分成8组包括强制关键字、文件信息关键词、望远镜参数关键字、观测参数关键字、光谱仪参数关键字、天气条件关键字、数据简化参数关键字和光谱分析结果关键字。

# 2 RFITSIO软件包简介

20 世纪70 年代开发的天文数据文件FITS 格式有别于GIF、JPG 等图像文件[8]，它作为一种标准的数据格式可同时存储图像和数据表格。20世纪90年代初，美国高能物理科学研究中心[9]研发了功能强大、使用简便的FITSIO程序库，在FORTRAN程序和C语言程序中均可直接调用该程序库，并提供简单的途径完成读、写FITS 格式的文件。

研究中R语言包是从相应的ComprehensiveRArchiveNetwork镜像站点下载并将其放人库中，加载FITSIO包后读取，这个包中包含的功能用于读取FITS头文件数据单元(HDUs)的图像和扩展二进制表，以及写入FITS图像文件等功能。其中函数readFITS能自动识别图像（多维数组)和扩展二进制表、返回数据、头文件和扩展信息列表，函数readFITS返回值及参数如表1。利用readFrameFromFITS返回从二进制表头文件数据单元的R语言数据框架，这两个函数主要接收头文件数据单元的文件参数、二进制表位等。

# 3R语言分析光谱数据

R语言具备强大的统计功能，从分析事物、判别分析对象分类到已知类别数量集的表现特征，聚类分析一定尺度的对象相关性，推断该分析对象事物内在可能存在的规律性。常用的方法有回归分析、判别分析、聚类分析以及探索性分

表1readFITS返回值及参数列表  
Table 1Return values from readFITS and arguments list   

<html><body><table><tr><td>向量</td><td>功能</td></tr><tr><td>header</td><td>将 END 语句输入文件头</td></tr><tr><td>hdr</td><td>将头文件的各组解析值赋给关键字</td></tr><tr><td>imDat</td><td>数据数组(图像)</td></tr><tr><td>axDat</td><td>带轴缩放和标签(图像)的数据帧</td></tr><tr><td>col</td><td>每个列的数据(二进制表)</td></tr><tr><td>hdu</td><td>FITS文件头部和数据单元的位置： “1”即为第1个文件头部和数据单元</td></tr><tr><td>colNames</td><td>列名称向量TTYPEnFITS变量</td></tr><tr><td>colUnits</td><td>列单元的向量 TUNITn FITS 变量</td></tr><tr><td>TNULLn</td><td>未定义值的定义向量，FITS变量</td></tr><tr><td>TSCALn</td><td>缩放倍乘的向量，FITS变量</td></tr><tr><td>TZEROn</td><td>零缩放向量，FITS 变量</td></tr><tr><td>TDISPn</td><td>格式信息向量，FITS变量</td></tr></table></body></html>

析。天文学中的统计方法从1996 年以来，如文［10]采用Fortran 程序、C语言程序以及Python 程序,本文实验分析基于R语言程序平台。

# 3.1 数据获取

从 http://dr2.lamost.org/下载 2016年6月LAMOST发布的第2次巡天共享数据 $\mathrm { d } \mathrm { r } 2 . 7 \mathrm { z }$ 共计156 GB,下载后 DR2中恒星数据按CLASS 字段执行分类到恒星74个文件夹，实现FITS 文件的聚类分布及科

学计算，分析输出绘制图表。

# 3.2数据处理环境

实验编程及程序运行在Linux环境下，采用R版本2.9.0程序语言编写，载入FITSIO软件包。实验下载服务器 htps://cran.r-project.org/src/contrib/Archive/FITSio/FITSio_1.2-0.tar.gz，安装命令install.packages（"FITSio"）执行后，选择 CRAN mirror 为“32:China（Beijing）”。

# 3.3绘制数据一维光谱图

R语言是动态语言，在编写代码时常采用两种形式：一种形式如同书写文章，将要完成的功能按模块编写后统一运行；另一种形式则是编写一行语句编译该行。RStudio分为4个工作区域，左上区域为“编写代码”。左下区域也可写代码且运行程序数据输出，即能完成编写一句回车编译解释一句的工作区域。右上区域为“工作区及历史记录”，如图1，使用RStudio直观显示文件的环境变量。右下区域包括的主要功能：“Files”查看当前主页下的文件；“Plots”展示运算结果的图案；“Packages”展示系统已安装的软件包，同时勾选载入内存；“Help”查看帮助文档等功能。

Environment History   
中 日 Import Dataset- List- C   
Global Environment\~ Q   
OM_STAR List of 4 A imDat num [1:3909，1:5] -66.216 71.728 -129.072 -8.909 -0.273 axDat 'data.frame': 2 obs. of 6 variables: S crpix: num [1:2] 1 1 crval: num [1:2] 3.57 1 cdelt: num [1:2] 1 1 len : int [1:2] 3909 5 .\$ ctype: chr [1:2] "LINEAR" \*" \$ cunit:chr [1:2] "" \*" hdr:chr [1:252] "SIMPLE" "T" "BITPIX" "-32" header : chr [1:128] "SIMPLE = T /Primary Header created by MWRFITS v1.11b " "BITPIX = -32 / " "NAXIS..

LAMOST发布的巡天光谱FITS 数据通过cfitsio软件包写成，完全依据国际天文联合会发布的天文数据国际标准格式，从已下载的恒星数据中解压FITS命名“spec-MMMMM-YYYY_spXX-FFF.fits”格式指定目标文件，利用 require（FITSio)载入需要的FITSio软件包，读取光谱数据文件 readFITS（"路径\*.fits"）。利用表1中介绍的readFITS 返回值及参数列表，利用M_STAR $\$ 8$ imDat提取特征向量矩阵，可将其存储成.csv、.txt等格式文件，再读取对应参数信息数据列，并限定最大数据范围值。利用plot（）函数选用type $\mathbf { \tau } = \mathbf { \tau }$ " s"，任意选取LAMOST 巡天数据库中的A1IV 型星光谱数据文件 spec-55938-GAC_070N40_V1_sp04-161.fits，绘制流量光谱图如图2。

![](images/0104b9f31f13f6c1648c53755f4333e8875085b1477717498fa3ecbb6a863867.jpg)  
图1RStudio右上工作区读取M型星数据变量例表图  
Fig.1The M Star data variable list in the right top workspace reads of RStudio   
图2R语言读取并绘制的LAMOST巡天数据A1IV型星流量光谱图 ig.2A spectrum of A1IV type Star in LAMOST survey data read and draw by F

# 4挖掘高维光谱数据

实验采用降维数据的方法处理维数无限增大时，简化线性变换掩盖数据原有的信息，探索适合的投影方向，选取最优贡献率将高维空间的目标特征信息尽可能忠实地投影到低维空间，进而高效地提取高维空间中存在的明显差异或特征。

# 4.1主成分分析方法应用

高维空间向低维空间线性变换的关键取决于缺失数据的特征信息及关联属性。主成分分析是一种多变量数据线性分析方法，能够较好地完成大样本多参数定量的数据分析，具备非监督性，在尽可能少损失信息的前提下，利用降维理念完成正交变换。由于各主成分变量的总方差贡献率的大小不同，在研究过程中，一般挑选前面几个方差最大的主成分（累计方差贡献率在 $8 0 \% \sim 9 0 \%$ )分析问题，从而降低问题的复杂程度，抓住主要成分。R语言在主成分分析中，能高效快捷地对光谱数据进行计算分析。

# 4.2R语言光谱数据主成分分析

为了去除如光子噪声和设备的热噪声等冗余信息的恒星全频谱信号光谱，较好地从原始光谱数据中提取物理参数的相关特征，提高物理参数测量模型的可靠性和运行效率，实验采用R语言中核心stats 包的prcomp 函数对光谱数据的特征量提取完成主成分分析，主成分分析是基于光谱域的特征提取方法，通过提取光谱中每个波段对应的光谱信号描述能力强弱的流量特征值，旋转坐标系后消除特征之间相关性的光谱分辨力，达到数据降维和剔除噪声的目的。天文研究中主成分分析处理需考虑特征和物理参数间的关系，提取不同的物理参数的特征相关性时难于解释其物理意义，仅仅是数学上的线性相关。现就LAMOST大样本、多变量的数据光谱进行主成分分析的应用。

# 4.3LAMOST光谱数据提取主成分分析实验

在R 语言环境下调用 require（graphics），运行主成分分析时需去掉提取后的字段名，也可以用stats 包中的 prcomp 函数及princomp（）函数进行主成分分析，princomp 函数返回一个 princomp 对象，用 summary（)函数查询每个主成分的重要信息，用loadings 函数查看每个变量对主成分的贡献度。此处以A1IV类不同光谱数据的主成分为例，分析的结果差别较明显，光谱主成分分析结果如图3。

Importance of components:   
Comp.1 Comp.2 Comp.3 Comp.4   
Standard deviation 4.192833e+053.315269e+049.429371e+036.951163e+03   
Proportion of Variance 9.909872e-01 6.195700e-03 5.012083e-04 2.723754e-04   
Cumulative Proportion 9.909872e-01 9.971829e-01 9.976842e-01 9.979565e-01   
Comp.769 Comp.770 Comp.771 Comp.772   
Standard deviation 1.185081e+01 1.166097e+01 1.161865e+01 1.149543e+01   
Proportion of Variance 7.916780e-10 7.665176e-10 7.609638e-10 7.449094e-10   
Cumulative Proportion 9.999999e-01 9.999999e-01 1.000000e+00 1.000000e+00

根据综合评价函数累计贡献率，然后排序择优，图3中 Standard deviation表示主成分的标准差，对相应特征值的开方，即主成分方差平方根；Proportionof Variance 表示方差贡献率如 $\mathrm { { C o m p . 1 } = }$ $9 9 . 0 9 \%$ ；Cumulative Proportion 表示方差累计贡献率，第770个主成分Comp.770 时其和为1。在此例中选取A1IV型恒星前4个主成分，总方差贡献率达到 $9 9 . 7 9 6 \%$ 。用这4个主成分重构图3中A1IV型星光谱数据文件 spec-55938-GAC_070N40_V1_sp04-161.fits，重构后如图4显示的光谱噪声幅度减小，曲线光滑，而主要的光谱特征谱线都未受损失，说明用主成分分析方法进行特征提取是高效的。

![](images/f4d12af05af5235f6e09776f5b68263236816068ed5a1bd890698593fbed73f0.jpg)  
图4R语言重构A1IV型星光谱数据文件“spec-55938-GAC_070N40_V1_sp04-161.fits”的流量光谱图Fig.4Reconstraction of a A1IV type spectrum“spec-55938-GAC_070N40_V1_sp04-161.fits” in LAMOSTby I

# 5结论与展望

目前天文学与云计算在大数据领域的研究应用合作[1]，将逐步提升天文领域更深人地探索宇宙空间，海量数据处理需依靠得力的工具，R语言平台及其强大的统计分析软件包应用在天文学中将充分发挥其性能优势，在海量数据处理挖掘过程中发挥重要的作用。本文用RFITIO对天文数据的读写和主成分分析方法的概念构造光谱的主成分为例，寻找天文光谱数据多变量的“代表”提取到低维空间样本主要特征点，将R语言初步应用于天文数据挖掘中，研究结果表明，结合天文数据的领域知识与R语言具有的大数据分析优势，能够更加高效地获取挖掘天文光谱数据，是下一步天文数据应用的一项有价值的尝试。

# 参考文献：

[1] Wells D C,Greisen E W,Harten R H.FITS:a Flexible Image Transport System [J].Astronomy&Astrophysics Supplement，1981，44：363-370.  
[2] 柯大荣，赵永恒．一种图象传输系统及其FITS 数据基本格式［J].现代图书情报技术，1994(2) : 25-26.Ke Darong，Zhao Yongheng.An image transport system and its FITS basic format [J]. NewTechnology of Library and Information Service，1994(2）:25-26.  
[3] 李化南，肖泉宝，邵正义.FITSIO软件包的简介及应用举例［J]．中国科学院上海天文台年刊，2005(1)：119-124.Li Huanan，Xiao Quanbao，Shao Zhengyi. The introduction to fitsio and its applied example [J].Annals of Shanghai Observatory Academia Sinica，2005(1） :119-124.  
[4] 崔辰州，李文，于策，等.FITS 数据文件的检索和访问［J].天文研究与技术——国家天文台台刊，2008，5(2)：116-123.Cui Chenzhou，Li Wen，Yu Ce，et al. Search and location of FITS data files ［J].AstronomicalResearch & Technology———Publications of National Astronomical Observatories of China,2008,5(2):116-123.  
[5] 钟守波，韩波，张彦霞，等．天文大数据管理工具的设计与实现［J]．天文研究与技术，2015，12(4): 511-515.Zhong Shoubo，Han Bo，Zhang Yanxia，et al.Design and implementation of a software toolpackage for managing massive astronomical data ［J].Astronomical Research & Technology,2015，12(4) : 511-515.  
[6] 赵永恒.大规模天文光谱巡天［J].中国科学：物理学 力学 天文学，2014，44(10)：1041-1048.Zhao Yongheng. Large-scale astronomical spectroscopic surveys [J]. Scientia Sinica: Physica,Mechancia & Astronomica，2014，44（10）：1041-1048.  
[7] Luo Ali，Zhao Yongheng，Zhao Gang，et al. The first data release（DR1）of the LAMOSTregular survey [J]. Research in Astronomy and Astrohysics，2015，15(8）:1095-1124.  
[8] 涂洋，张彦霞，赵永恒，等.光谱分析软件在天文学研究中的应用［J]．天文研究与技术，2016，13(1):124-132.Tu Yang，Zhang Yanxia， Zhao Yongheng，et al. Application of spectral analysis softwares inastronomy[J].Astronomical Research & Technology，2016，13(1）：124-132.  
[9] Pence W. CFITSIO，v2.O:a new ful-featured data interface [C]// David M Mehringer,Raymond L Plante，Douglas A Roberts.Astronomical Data Analysis Software and Systems VIII,ASP Conference Series，1999，172:487-489.  
[10] Babu G J.Feigelson E D.Astrostatistics，Chapman and Hall［C].（1996）[2016-11-28].https://www.crcpress.com/Astrostatistics/Babu-Feigelson/p/book/9780412983917.  
[11] 崔辰州，于策，肖健，等.大数据时代的天文学研究［J].科学通报，2015，60(Z1)：445-449.Cui Chenzhou，Yu Ce，Xiao Jian，et al.Astronomy research in big-data era ［J].ChineseScience Bulletin，2015，60(Z1） : 445-449.

# Application of R language in LAMOST Spectral Analysis

Chen Shuxin $^ { 1 , 2 }$ ，Luo Ali $^ 3$ ，Sun Weimin² (1. College of Mechanical and Electrical Engineering of Qiqihar University，Qiqihar 161Oo6,China;   
2.KeyLabofIn-fiberIntegratedOptics,MinistryEducationofChina,HarbinEngineringUniversity,Harbin15o6,China,   
Email：sunweimin@hrbeu.edu.cn；3.KeyLaboratoryofOpticalAstronomy，ChineseAcademyofSciences，Beijing0ol，China)

Abstract: The data mining research of large-scale survey is focused on handling，processing and extracting information from masive astronomical data. In this paper，we try to apply the extensible R programming language in LAMOST spectral analysis，and make full use of its capability of integrated data analysis and visualization methods.We mainly study the functions and characteristics of the RFITSIO package for reading and writing FITS format files in R.We then group the LAMOST DR2 data according to the released clasification result，and the PCA package in R is applied in each group to extract spectral features from the large amount of noisy spectra. The result shows that，the spectral features are well kept through PCA reconstruction.By extractingthe FLUX eigenvalues of the spectral signal description capabilityof each band in the spectrum，the PCA is used to extract the characteristic value of LAMOST.Rotating coordinate system to eliminate thecorrelation between the characteristics of thespectral resolution of the data，to reduce the dimensionalityof dataand remove the effct of noise.This dimensional reduction based feature extraction method can be a very effcient pre-processing approach for the follow-up data mining in LAMOST dataset.

Key words: R language； Flexible Image Transport System Input Output； Spectroscopic Survey； Large SkyArea Multi-Object Fiber Spectroscopy Telescope；Principal Component Analysis