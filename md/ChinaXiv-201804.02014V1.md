# 基于DW特征参数的GNSS-R海面风速反演研究

刘原华1，郭顺利1，牛新亮²

(1．西安邮电大学 通信与信息工程学院，西安 710121;2．中国空间技术研究院西安分院，西安 710000)

摘要：传统上，机载风速反演一般使用相关功率曲线后沿直接匹配方法，该方法需从实测数据中提取状态信息生成理论波形，而从实测数据中提取状态信息是有误差的，导致生成的理论波形存在误差，从而反演效果不好。对此，提出一种新的基于一维时延功率波形特征参数的风速反演方法，该方法根据风速对一维时延功率曲线时延窗的影响，建立以一维时延功率曲线时延窗作为特征参数的风速反演模型。实验结果表明，新方法的精度为 $\mathrm { { 0 . 7 7 \ m / s } }$ ，相比传统方法，精度提高了 $3 3 . 0 4 \%$ ，且模型简单。

关键词：相关功率曲线；风速；一维时延功率波形特征参数；一维时延相关功率；时延窗 中图分类号：TP7 doi:10.3969/j.issn.1001-3695.2017.11.0779

# Research on sea wind speed inversion of GNSS-R based on DW feature parameters

Liu Yuanhua1, Guo Shunli', Niu Xinliang² (1.CollegeofCommunications&Information Engineering,Xi'an UniversityofPosts&Telecommunications,Xi'an710121, China; 2.Xi'an Branch of China Academy of Space Technology,Xi'an 71oooo,China)

Abstract: Traditionall,airboreseasurface windspeediversion generallyuserelevant powercurvedirectly matching method, this methodnedtoextracted stateinformationfromtheactualmeasurementdataforgenerating theoretical waveform,however, thestateinformationextracted fromtheactualmeasurementdataisexisted eror,sothatthereisanerrorinthetheoretical waveform,thus,theinversionresult is notaccurate.Tothis,this paperproposedanewmethodofwind speed inversionbased onone-dimensionaldelay power waveform characteristic parameters,the method wasbasedonthe influenceof wind speedon delay windowofone dimensionaldelay power curve,it establishedthe inversion modelof wind spedbyusingthe time delay windowofone dimensiondelaypowercurveas thecharacteristic parameter.The experimentalresults showthat theacuracyof the new method is $0 . 7 7 \mathrm { m / s }$ .Compared to traditional methods,the accuracy is improved by $3 3 . 0 4 \%$ ,and the model is simple.

Key Words:corelation power curve;wind speed;one-dimensional delay power waveform characteristic parameters；onedimensional delay correlation power; window of time delay

# 0 引言

利用GPS散射信号进行海面高度测量的概念自1993年由Martion-Neria博士提出以来，全球导航卫星系统反射信号（global navigation satellite system-reflection，GNSS-R）技术逐渐发展成一个新的分支[1\~4]。从电磁波的传播理论可知，海面反射信号中必然含有反射面的相关特征信息，其中包括反射信号的波形和极化特性等的变化。因此，可以借助对反射信号的接收处理来实现反射面物理特征的估计并进行下一步反演方面的相关工作[5]。

GNSS-R技术在测量海面风速方面取得了很大的进展，其中，机载方面进行的飞行实验可检验性强，可用来开展反演方法的研究工作[6\~8]。利用相关功率曲线后沿直接匹配的风速反演算法是传统机载风速反演的主要方法，其他风场反演算法是在此基础上发展起来的9]。但是功率曲线后沿直接匹配算法在生成理论模拟波形时，需从实测数据中提取状态信息生成理论波形，而从实测数据中提取状态信息会产生误差，这将导致生成的理论模拟波形存在误差，从而降低了反演精度[9]。

本文提出一种新的基于一维时延功率波形（one-dimensional delaypowerwaveform，DW）特征参数的GNSS-R海面风速反演方法。首先介绍了GNSS-R海面风速反演原理，并在此基础上对传统的相关功率曲线后沿直接匹配方法进行分析；然后建立起以一维时延功率曲线时延窗作为特征参数的海面风速反演模型，从而实现了海面风速高精度的反演。实验结果表明，与传统功率曲线后沿直接匹配的风速反演方法相比，新反演方法的精度提高了 $3 3 . 0 4 \%$ ，且模型简单。

# 1 GNSS-R海面风速反演原理

目前，在利用GNSS海面散射信号进行海面风场反演的研究中，Zavortny和Voronovich借助于双基雷达方程，并通过克希霍夫近似的几何光学方法提出了海面散射信号的时延一多普勒二维相关功率模型[9]：

$$
\begin{array} { c } { { \displaystyle {  | Y ( \tau ) | ^ { 2 }  { } = T _ { i } ^ { 2 } \int } \int \int \frac { G ^ { 2 } ( \stackrel {  } { \rho } ) } { 4 \pi { R _ { t } } ^ { 2 } ( \stackrel {  } { \rho } ) { R _ { r } } ^ { 2 } ( \stackrel {  } { \rho } ) } \times \Lambda ^ { 2 } { } [ \tau - \frac { { R _ { t } } + { R _ { r } } } { c } ] } }  \\ { { \times { } | S [ f _ { D } ( \stackrel {  } { \rho } ) - f _ { c } ] | ^ { 2 } \times \delta _ { 0 } ( \stackrel {  } { \rho } ) d ^ { 2 } { \rho } } } \end{array}
$$

这是一个二重积分，积分区域为散射区域 $\rho$ ，主要为上述菲涅耳区域和多普勒区的交集[9]。其中： $\mathbf { \Omega } _ { T _ { i } }$ 为积分时间； $G$ 为天线增益； $R _ { _ t }$ 和 $R _ { , }$ 分别表示GNSS卫星和接收机到散射区域的距离； $\mathbf { \Psi } _ { \Lambda }$ 表示伪码相关函数； $s$ 表示多普勒滤波函数。

在给定的卫星仰角和接收机高度下，随着风速的增加，会直接带动海面粗糙度的增加，准镜面方向的散射信号相关功率减小，从而互相关函数变化曲线就会呈现不同的形状[9]，如图1所示。

![](images/e2899e4dda408f4355186779c9080eb1e86e9bbd5b58352c4e5038a1988c6918.jpg)  
图1不同海况下散射信号的相关功率曲线

因此，可以通过研究海面粗糙度变化对散射信号相关功率的影响来实现海面风速的反演。

# 2 传统的GNSS-R海面风速反演方法

传统海面风速反演是利用相关功率曲线后沿直接匹配方法[9]。该方法首先从实测数据中提取系统状态信息，生成理论波形，并进行归一化处理；然后提取实测数据波形，并进行降噪处理和归一化处理；最后将归一化后的实测波形与根据实测状态信息所计算出来的归一化后的理论波形进行匹配得到风速，如图2所示。

2017年在山东威海先后进行了多次GNSS-R机载飞行实验，这里仅对某一次机载飞行实验下采集的数据进行处理。实验场景如图3所示。

![](images/1c8008132174e9a406256f38d222bc71a7b4430d1955a6229b4808b6324b2c76.jpg)  
图2海面风场反演图

![](images/1ef0555bf78eba89fd1deb0b02d341fa0681b98010a9011d2f31c4e559ec3e1d.jpg)  
图3实验场景图

利用相关功率曲线后沿直接匹配方法反演风速。反演结果如图4所示。其中红色三角形线为实测数据，最下方的黄色星线为风速 $7 . 8 ~ \mathrm { m / s }$ 的理论曲线，中间的蓝色星线为风速 $8 . 8 ~ \mathrm { m / s }$ 的理论曲线，最上方的绿色星线为风速 $9 . 8 \mathrm { m / s }$ 的理论曲线。通过比较可见，实测数据与 $8 . 8 ~ \mathrm { m / s }$ 的理论曲线匹配得较好。

![](images/8a81a3e79645dafbb5b1de9e004a73fde902bcf28ef4ea9de3448cec470cc9cc.jpg)  
图4风速匹配图

最后，通过浮标数据对风速反演的精度进行评估。图5所示即为利用GNSS-R反演得到的风速值与浮标数据的对比结果。图中浮标数据显示的平均风速为 $8 . 8 ~ \mathrm { m / s }$ ；GNSS-R实际反演风速为 $7 . 4 { \sim } 1 1 . 5 ~ \mathrm { m } / \mathrm { s }$ 、平均反演风速为 $8 . 3 ~ \mathrm { m / s }$ ，由此得到其风速反演精度为 $1 . 1 5 ~ \mathrm { m / s }$ 。

![](images/0340b5577567ef7535f11e0417e33070f1bdc6c67de6622199e33db1494ebecc.jpg)

风速为 $3 . 9 \mathrm { m / s }$ 时，对应的时延一维相关功率波形时延窗的大小变化如图7所示。

![](images/01ee4630b22904f7e7deb2a7c5c570c4d2699b248d5fd18076e882d342f7294f.jpg)  
图5与浮标数据的对比结果

传统机载风速反演使用的相关功率曲线后沿直接匹配方法主要存在以下不足：

根据实测数据所提取的状态信息生成理论波形时，由于从实测数据中提取状态信息会产生误差，这将导致在生成理论波形过程中这些误差会被二次引入，从而使得反演效果不好，降低了反演精度，而且计算量大，反演过程繁琐。

对山东威海多次机载飞行实验数据进行处理。散射信号的归一化时延相关功率曲线如图6所示。

因此，本文研究提出了一种基于DW特征参数的GNSS-R海面风速反演新方法。

# 3.1基于DW特征参数的GNSS-R海面风速反演机理

# 3 一种改进的基于 DW 特征参数的 GNSS-R 海面风速反演方法

![](images/635f9c5e87e6a9f0e8147d8cc3e802a07da34b96246bb8bede3232afc6183d49.jpg)  
图7时延一维相关功率波形时延窗的大小

![](images/eb12a244b77beaf5542f51de98abcb3d92a0688f3d8ca16a922b0751a6bce90f.jpg)  
图6不同风速的散射信号归一化功率

由图6可见，风速的增加，散射信号对应的时延值向右偏移，散射信号时延相关功率向时延更大的方向扩散[10]（图中的τ为对应风速的时延窗的长度）。因此，可以通过研究相应风速和一维时延功率波形特征参数（时延窗长度）的关系，即建立风速与时延窗长度的函数关系来实现海面风速反演。

由图7可见，时延窗的大小在1000ns上下波动，波动范围为 $9 6 0 ~ \mathrm { n s } { \sim } 1 ~ 0 4 0 ~ \mathrm { n s }$ 。

# 3.2时延一维相关功率时延窗长度的提取

提取一维时延功率曲线时延窗长度τ时，为了更好地反映波形拖尾的变化趋势，将截取阈值定义为 $1 / \mathrm { e } ^ { [ 1 1 ] }$ 。

本文研究选取了三组风速进行分析，分别是 $3 . 9 ~ \mathrm { m / s }$ 、4.3m/s、 $8 . 8 \mathrm { m / s }$ 。现提取这三个风速下的一维时延功率波形的时延窗长度。

风速为 $4 . 3 \mathrm { m / s }$ 时，对应的时延一维相关功率波形时延窗的大小变化如图8所示。

由图8可见，时延窗的大小在1040ns上下波动，波动范围为 $1 ~ 0 0 0 ~ \mathrm { n s } { \sim } 1 ~ 0 8 0 ~ \mathrm { n s } .$ 0

风速为 $8 . 8 \mathrm { m / s }$ 时，对应的时延一维相关功率波形时延窗的大小变化如图9所示。

![](images/ea2e157bbece9659041b0af5f87957c554b828a85e23a41ef5e64451023d6fb2.jpg)  
图8时延一维相关功率波形时延窗的大小  
图9时延一维相关功率波形时延窗的大小

由图9可见，时延窗的大小在1160ns上下波动，波动范围为 $1 0 8 0 { \mathrm { n s } } { \sim } 1 2 4 0 { \mathrm { n s } } ,$ 0

结合图7\~9可以看出，随着风速逐渐变大，对应的一维时延相关功率波形时延窗长度明显变大，风速与一维时延功率波形时延窗长度呈现正比例关系。并且风速发生变化时，时延窗长度变化明显易于区分，在精度上也满足反演技术要求。因此，这为利用时延一维相关功率时延窗长度反演海面风场提供了数据依据。

# 3.3反演模型建立和精度分析

通过 $3 . 9 \mathrm { m / s }$ 、 $4 . 3 \mathrm { m / s }$ 、 $8 . 8 \mathrm { m / s }$ 这三组风速对应的时延窗长度，结合风速与时延窗长度的正比例变化趋势和新反演方法的反演机理，利用数学建模理论知识，对时延一维相关功率时延窗的大小 $\tau$ 和风速 $\mu$ 数据进行建模，经建模发现幂函数模型最能反映出风速和时延窗长度的正比例变化关系，且误差小，精度优于其他经验模型。对此，本文仅讨论采用幂函数模型进行建模。

$$
u = a * \tau ^ { 2 } + b * \tau + c
$$

其中：a、b、c为待定系数。

现对时延一维相关功率时延窗的大小和风速进行拟合，如图10所示。拟合计算出 $\mathrm { a } { = } 1 . 4 2 { ^ { * } } 1 0 ^ { - 5 }$ ， $\mathsf { b } { = } - 0 . 0 0 4 6 2$ ， $\mathrm { ~ c ~ } { = } 6 . 0 1$ 。

![](images/f63641c0ff896eb20e87b3f9778e469042b9fe476636e48b354578f8771a4032.jpg)  
图10时延一维相关功率波形时延窗的大小和风速拟合图

最后，通过浮标数据对风速反演的精度进行评估。图11所示即为利用GNSS-R反演得到的风速值与浮标数据的对比结果。从图中可以看出，反演风速与浮标风速观测数据具有很好的一致性，由此得到其风速反演精度为 $0 . 7 7 \mathrm { m / s }$ 。

![](images/95588db16e9a40bb17aa8cde38fd8f747a3ee3621e8009bb4e8e35750c735960.jpg)  
图11反演风速与浮标数据的对比结果

# 4 结束语

本文介绍了一种利用DW特征参数进行海面风速反演的新方法，通过对山东威海海域实验数据进行处理和分析，建立了以一维时延功率曲线时延窗作为特征参数的海面风速反演模型，从而实现了海面风速的高精度反演。结果显示，利用DW特征参数进行海面风速反演的新方法能够有效地反映出风速的变化，反演精度为 $0 . 7 7 ~ \mathrm { m / s }$ ，与传统相关功率曲线后沿直接匹配方法相比，精度提高了 $3 3 . 0 4 \%$ 。因此，新反演方法具有精度高、模型简单等优点，大大提高了工作效率，简化了反演流程。

# 参考文献：

[1]Martin-Neira M.A passive reflectometry and interferometry system (PARIS) application to ocean altimetry [J].ESA Journal,1993,17 (4): 331-355.   
[2]边超磊，葛海波，陈瑞姣．基于 PMF-FFT 的高精度伪码捕获算法[J] 电视技术,2016,40(1):62-66.   
[3]李颖，朱雪瑷，曹妍，等.GNSS-R 海洋遥感监测技术综述[J].海洋通 报,2015,34(2):121-129.   
[4]Egido A,Paloscia S,Motte E,et al. Airborne GNSS-R polarimetric measurements for soil moisture and above-ground biomass estimation [J]. IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing,2014,7(5): 1522-1532.   
[5]Fabra F, Cardellach E,Nogues-Correig O,et al. Monitoring sea-ice and dry snow with GNSS reflections [C]// Proc of IEEE International Geoscience and Remote Sensing Symposium.2010: 3837-3840.   
[6]Martin-Neira M,Caparrini M,Font-Rosselló J,etal. The PARIS concept: an experimental demonstration of sea surface altimetry using GPS reflected signals [J]. IEEE Trans on Geoscience and Remote Sensing,2Oo1,39(1): 142-150.   
[7] 黄健，张德海，孟进，闫大帅，等．一种新的基于 FFT 的高动态扩频信 号捕获方法[J]．电视技术,2015,39(9):113-116.   
[8]周兆明，符养，严卫，等．利用GPS反射信号遥感Michael飓风海面风 场研究[J].武汉大学学报：信息科学版,2006,31(11):991-994.   
[9]杨东凯，张其善.GNSS 反射信号处理基础与实践[M].北京：电子工 业出版社,2012.   
[10]周晓中，李紫薇．机载GPS-R 遥感海面风场实验[J]．解放军理工大学 学报：自然科学版,2011,12(1):84-89.   
[11] Valencia E,Camps A,Marchan HJF,et al.Experimental determination of the sea correlation time using GNSS-R coherent data [J]. Geosci Remote Sens Lett,2010,7 (4): 675-679.