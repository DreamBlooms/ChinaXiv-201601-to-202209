Wang Dazhao,BaiWeiua,SunYueqang,MengXiangguang,WangDongwei,LiWei.Inversionalgorithmsandprecisioaalyis of ROPP (in Chinese). Chin.J. Space Sci.,2015,35(3):350-355,doi:10.11728/cjss2015.03.350

# ROPP反演软件算法及其精度分析

王大钊1.2 白伟华² 孙越强²  
孟祥广2 王冬伟² 李伟²

1(中国科学院大学北京 100049)

2(中国科学院空间科学与应用研究中心北京 100190)

摘要介绍了ROPP 反演软件中无线电掩星反演的算法与精度分析．采用COSMIC卫星2008年1月1日全天的附加相位数据，反演得到折射率、温度、压强与湿度等参数，并与CDAAC 相应结果进行对比.实验结果表明,在 $3 0 \mathrm { k m }$ 高度以下,折射率、压强和湿度的相对误差在 $2 \%$ 以内，温度误差不超过2K.

关键词无线电掩星,折射率,大气参数,ROPP中图分类号P128.14,V448

# Inversion Algorithms and Precision Analysis of ROPP

WANG Dazhao $^ { 1 , 2 }$ （204 BAI Weihua² SUN Yueqiang $^ 2$

MENG Xiangguang $^ 2$ WANG Dongwei $^ 2$ LI Wei $^ 2$

1(UniversityofChineseAcademyofSciences,Beijing 1o0049)

2(Center for Space Science and Applied Research,Chinese Academy of Sciences,Beijing 100190)

AbstractThe unique combination of global coverage,high precision, high vertical resolution, longterm stability and all-weather viewing of radio occultation will enhance the data sets of numerical weather prediction and improve the precision of Numeric Weather Prediction (NWP). And data assimilation requires preprocessng of the raw radio signals into the bending angles and refractivity. Then the atmospheric parameters such as temperature, pressure and humidity can be retrieved through data variational assmilation. The procedures for processing of radio occultation data, especially several important steps are introduced.And comparative analysis between these results and those from CDAAC shows that below the altitude of $3 0 \mathrm { k m }$ , the relative errors of refractivity, pressure and humidity are within $2 \%$ and the deviation of temperature is below $2 \mathrm { K }$ . The results are also compared with the data from ERA-interim model of ECMWF and similar conclusion is obtained. Key wordsRadio occultation inversion, Refractivity, Atmospheric parameters, ROPP

# 0 引言

美国喷气推进实验室（JetPropulsionLaborato-ry,JPL）在19世纪60年代首次提出将无线电掩星技术应用于地球大气主动探测[1]，由于当时技术和经济条件的限制，计划暂时搁浅.在美国与前苏联分别部署了各自的全球定位系统GPS和GLONASS之后，利用掩星技术探测地球大气剖面成为可能．1993年美国 UCAR (University Corporation for Atmo-spheric Research),UA(UniversityofArizona)与JPL联合制定了GPS/MET计划.其第一颗实验卫星Mi-croLab1于1995年成功发射.通过两年的运行，证明了无线电掩星技术可在地球大气探测与研究中起到重要作用[2-3]．由于GPS/MET计划的成功,NASA在1995年资助了两个国际计划，分别是丹麦Orsted卫星和南非 Sunsat卫星[4]．此后国际上较出名的无线电掩星卫星有SAC-C,CHAMP,GRACE，Metop系列和 COSMIC 等.值得一提的是，2013 年中国成功发射了风云三号卫星，首次兼容GPS和中国北斗导航卫星系统开展无线电掩星探测.

无线电掩星具有全球覆盖、高精度、高垂直分辨率、长期稳定性及全天候观测等优势，每颗LEO卫星每天大约可以获取500条剖面，这为气候研究与数值天气预报提供了大量数据源．目前无线电掩星研究的热点之一是，如何将掩星观测到的数据应用于现行数值天气预报系统．其关键是无线电掩星反演的精度应满足数值天气预报系统的精度要求．目前比较有影响力的GNSS气象学研究机构主要有GFZ的ISDC数据系统中心、JPL的GENESIS数据系统中心及UCAR的CDAAC数据系统中心等.UCAR与中国台湾联合发射的COSMIC任务是目前公认的在无线电掩星探测领域取得较好突破的任务.

ROPP由EUMESAT下属科研机构GRAS开发,其最初目的是用于处理Metop卫星数据，但在实际使用中,通过调整软件配置，可用于处理其他GPS-LEO掩星数据．在掩星数据处理过程中，ROPP可以对无线电掩星数据进行预处理和质量控制，还可将掩星数据同化到NWP(NumericWeatherPredic-tion）或者其他气候模式．ROPP是基于Fortran90的开源代码,在Linux 系统下运行[5]．文献[6]介绍了ROPP各模块之间的关系，以及其中主要模块的算法原理,使用ROPP处理了一组COSMIC数据，并对其结果进行了精度分析．在文献[6]基础上，根据实际需求，本文将ROPP处理软件移植到Windows中并用Matlab 进行编译.通过以上调整，可以实现在Windows下对一天的无线电掩星数据进行批量处理,共计2354次掩星事件.

使用ROPP的预处理模块对2009 年1月1日的COSMIC数据进行处理．将ROPP的反演结果与OCC反演结果对比，可以看到最优弯曲角、折射率和干温在 $4 5 \mathrm { k m }$ 高度以下保持了良好的一致性,平均相对偏差在 $0 . 4 \%$ 以内;而在 $4 5 \mathrm { k m }$ 高度以上误差较大，其原因在于在电离层修正过程中选择了不同的最优拟合MSIS 廓线.同时对于同一天的数据，还对同一位置的ECMWF分析数据进行了处理，得到折射率廓线.

通过对比ROPP反演的折射率和ECMWF的折射率，可以看出在多路径效应发生区域，相对误差可达 $2 \%$ 以上,干温误差更为明显，但是在 $1 0 { \sim } 2 0 \mathrm { k m }$ 高度内，误差较小，不超过1K.本文使用的数据为2008年1月1日的COSMIC数据，采用的ROPP版本为v6.1,主要进行了ROPP反演结果与CDAAC数据的对比，以检验ROPP与CDAAC数据处理流程的异同及其精度.

# 1无线电掩星数据处理流程

从GNSS发射出的信号在穿越电离层和大气层后，被 LEO 接收机接收．由于电离层与大气层的折射与衍射效应，导致GNSS信号出现相位延迟.在 $2 5 \mathrm { k m }$ 高度以上，传统几何光学反演算法根据观测到的相位延迟和卫星（GNSS与LEO）相对位置与速度，可以得到信号的弯曲角.但是在 $2 5 \mathrm { k m }$ 高度以下，由于水气含量较高，出现了多路径效应和超折射，几何光学反演不适用，这时需要进行波动光学反演，从而得到 $2 5 \mathrm { k m }$ 高度以下的弯曲角剖面.由于电离层的影响，在反演大气参数时要进行电离层修正.将L1和L2波段的弯曲角插值到同一碰撞参数层之后，进行线性组合与统计最优化，可得到最优弯曲角，即消除了电离层影响的大气弯曲角.利用Abel逆变换，可以得到折射率剖面.由于折射率受到温度与压强的影响，在没有水气的情况下，即在 $1 5 \mathrm { k m }$ 以上高度时，折射率仅受到干温和干压的影响，结合流体静力学方程，可以得到 $1 5 \mathrm { k m }$ 高度以上的干温和干压但是在 $1 5 \mathrm { k m }$ 高度以下，水气的影响是不能忽视的，仅由两个方程无法得到温度、干压和湿压三个参数这时需要使用大气模式的背景数据,对掩星反演结果进行变分同化.通过积分算子，实现同化表示成分析变量函数的任意观测量．ROPP中可以对弯曲角和折射率进行同化，在此选择对大气折射率进行同化，因为对折射率进行同化所需附加资料仅为点值坐标，观测算子相对简单，容易实现

ROPP包括输入/输出模块(ropp_io)、预处理模块(ropp-pp)、一维和二维前向模块(ropp-fm)、质量控制工具(ropp-qc）和一维变分反演模块(rop-p_ldvar)．在附加模块即工具模块 (ropp-utils）中有ROPP模块的部分或全部实用程序．图1给出了ROPP各模块间的相互关系以及各模块的主要函数.其中主要的是 ropp-pp 模块和 ropp-ldvar 模块ropp-pp 模块的主要输入为LEO 和GPS卫星的位置和速度及附加相位，输出主要是折射率、干大气温度和压强．ropp-ldvar 模块的主要输入包括观测数据和背景数据，输出为湿大气温度、压强和湿度等.

# 1.1 数据处理流程

无线电掩星数据处理流程如图2所示．可以看出，由LEO接收机接收到的附加相位数据，反演得到弯曲角和折射率剖面，然后得到没有水气分量的干温和干压.在得到折射率剖面后，对折射率剖面进行一维变分，进而得到带有水气分量的温度、压强及湿度信息.

# 1.2 主要步骤算法说明

(1）特定任务修正

CHAMPL2数据有很高的仪器噪声，因此L2振幅用L1代替．光线高度在 $8 { \sim } 1 1 \mathrm { k m }$ 以下时，COS-MIC和GRAS采用了开环技术且分别有自己的原始采样模式．该区域内的附加相位测量反演要去除在测量过程中加到每个数据样本中的伪随机数0或 $\pi$ 这个过程可以使用内部衍生的导航数据或参考导航数据的外部来源

# (2)数据截断

数据截断用来剔除信号跟踪误差非常大的数据截止的标准基于测量相位和通过平滑的几何光学计算出来的弯曲角和碰撞参数剖面的大概估计.剔除从振幅低于最大振幅的某一比例(例如0.1）时刻开始的数据．剔除从平滑弯曲角剖面大于特定碰撞高度和直线切线高度达到临界值(例如0.05)时刻开始的数据.

# (3）无线电全息滤波

在进行几何光学反演前，应对无线电掩星数据进行处理，将数据中的噪声降低并去除较差的数据样本.在此ROPP使用了一种基于正则变换（CT2）和无线电全息聚焦合成孔径法的无线电全息法滤波算法．首先将接收到的信号进行CT2处理，将转换空间中的信号除以参考信号，然后与一个傅里叶滤波窗进行卷积，再乘以参考信号从而重构初始信号.该算法很容易实施，而且在数值模拟中得到了验证[7].

![](images/97be368608deb5460481d8a5148c9baca5e47308aadb93d6dfc4eeba9eb68000.jpg)  
图1ROPP 模块及其相互关系  
Fig.1Relationships of the modules of ROPP

![](images/f2b00b7276fe49e5ff6891a6c8685179fe3a004b1ad092d724aef5ce9c4a0f51.jpg)  
图2无线电掩星数据处理流程  
Fig.2Data processing procedures of the radio occultation

# (4)几何光学

在水气含量较少的海拔高度上，没有出现多路径效应时，弯曲角是碰撞参数的单值函数.在折射率的局部球对称假设下，结合GNSS和LEO卫星的相对位置和速度，根据 Snell方程，最终可以得到弯曲角与碰撞参数[8]．传统的几何光学反演在水气含量较低的高度范围内，反演精度较高且算法实现容易

# (5）波动光学

当水气含量变高时，产生多路径效应和超折射此时单信号假设及瞬时频率与观测的对应性均不成立，即观测弯曲角与碰撞参数不是一一对应的.基于波动方程的波动光学反演方法就是为克服上述多路径效应而设计的．主要的波动光学反演算法有衍射法[9、后传播反演、滑动频谱法、全谱反演和正则变换[8].这五种算法中,全谱反演与正则变换的反演结果最好，而全谱反演的计算效率略高于正则变换在此选择了第二类正则变换算法.

# (6）电离层修正与统计最优化

电离层修正残余误差与接收机噪声是无线电掩星的一个主要噪声源,这些噪声会影响 $3 5 { \sim } 4 0 \mathrm { k m }$ 高度范围内的反演精度.ROPP使用的电离层修正与减小噪声的算法包括以下细节：对气候模式进行拟合;

使用 $5 0 \mathrm { k m }$ 以上的无线电掩星信号对信号与噪声的协方差矩阵进行动态估计;根据背景弯曲角、信号与噪声的协方差矩阵，对中性大气和电离层弯曲角进行统计最优化分析[10].

# 2无线电掩星反演实例

本次实验选取了COSMIC卫星2008年1月1日全部共 2354次大气掩星事件．其中下降掩星次数为967，上升掩星次数为1387．探测全程高度为 $0 { \sim } 6 0 \mathrm { k m }$ ，对COSMIC数据采用了开环跟踪处理，CDAAC数据处理成功率为 $7 5 . 8 \%$ 业

从包含附加相位信息的文件中反演出干温、干压.再使用背景数据进行一维变分，得到湿温、湿压与湿度信息．将反演结果与经过CDAAC数据处理得到的温湿压进行对比，即可得到反演结果的平均偏差和标准差，结果如图3所示，

图3中红色曲线表示ROPP反演结果与C-DAAC的平均偏差，其左右两条蓝色曲线分别表示平均偏差减去标准差、平均偏差加上标准差的值.从图3可以看出，在 $0 { \sim } 4 5 \mathrm { k m }$ 高度折射率反演结果较好,折射率相对误差的平均偏差保持在 $1 \%$ 以内

![](images/40f7815b419c1765734631fae9ca620c2cb577d92d2b7faaaf7996cd8bc95993.jpg)  
图3干大气反演结果对比  
Fig.3Comparison of dry atmosphere inversion

而干温误差的平均偏差在 $0 { \sim } 3 5 \mathrm { k m }$ 高度范围内保持在1K之内，干压相对误差则保持在 $1 \%$ 之内.

从文献[6]可以看出，对于单条廓线，ROPP反演结果与CDAAC的结果对比显示，在 $4 0 \mathrm { k m }$ 高度以下,折射率相对误差可以保持在 $1 \%$ 之内，而在 $4 0 \mathrm { k m }$ 以上，其迅速增大，可以达到 $- 3 \%$

在数据处理过程中，主要出现异常的问题在于在对ROPP反演的数据进行一维变分同化时，由于质量控制参数的不一致，导致ROPP与CDAAC对于同一条廓线的质量产生了不同的结果，在观测数据与背景数据进行匹配时出现异常.

随后使用ECMWF业务化预报的模式的数据作为背景数据，对折射率进行一维变分同化，得到了包含有湿度信息的温度、压强和湿度，结果如图4所示，

由图4可以看出，湿大气的反演结果要略差于干大气反演结果.但是在 $3 5 \mathrm { k m }$ 海拔高度内，温度误差可以控制在2K内，而压强与湿度的相对误差均小于 $2 \%$ ．此次实验中还将反演结果与ECMWF再分析模式ERA-interim的数据进行了对比，得到的结果类似.在文献6中，对于多路径效应发生的区域，温度误差较大，可达到2K，而此次实验中，对于多路径效应发生区域，误差得到了明显改善

# 3结语

通过反演统计分析可知，折射率廓线和干大气温度、压强的反演精度在 $0 { \sim } 3 5 \mathrm { k m }$ 内较高，折射率相对误差在 $1 \%$ 之内，压强相对误差在 $2 \%$ 之内，干温误差在1K左右.而在 $3 5 \mathrm { k m }$ 高度以上，反演精度有所降低.湿大气反演结果表明，在 $1 0 \mathrm { k m }$ 以下，温度误差在 $0 . 5 { \sim } 1 . 5 \mathrm { K }$ 以内；在 $1 0 { \sim } 2 5 \mathrm { k m }$ 高度，温度误差不超过1K；在 $2 5 \mathrm { k m }$ 高度以上，温度误差增大;在 $3 5 \mathrm { k m }$ 高度以下，压强相对误差在 $2 \%$ 之内.比湿误差也在 $2 \%$ 之内.

无线电掩星反演在 $3 0 \mathrm { k m }$ 高度以上的主要误差来源是电离层修正不完全和接收机跟踪误差，而 $1 0 \mathrm { k m }$ 高度以下的误差主要是由于大气水气模糊度无法确定．而大气参数(温度、压强和比湿）误差比折射率误差大，其主要原因是在数据同化过程中采用了背景数据,引入背景数据误差.背景数据误差对比湿的影响较小，而对温度和压强的影响较大．比湿在 $1 0 \mathrm { k m }$ 高度以上几乎为0,而在 $1 0 \mathrm { k m }$ 高度以下因水气梯度变化较大，导致误差发生了剧烈波动.主要误差来源包括电离层修正的影响、接收机噪声、水气模糊度和数据同化方法.

由上述实验可以看出，ROPP反演软件的预处理模块对无线电掩星数据的处理结果与CDAAC提供的结果较为接近，而一维别.在一维变分过程中出现误差的可能原因是，所使变分模块结果有了一定差用的背景数据不一致或者同化算子的选择不一致.在此选择的背景数据分层仅为60层，而CDAAC反演出来的数据分层为400层,其垂直分辨率明显优于本文所选择的背景数据.另外，选择弯曲角同化与折射率同化，两者差别也会造成反演结果的不同

![](images/9c6dd0eab26e5bfbd3bbc7f9859edb72676044e54d2edc7b56d1de7b7ed43aee.jpg)  
图4湿大气反演结果对比  
Fig.4Comparison of wet atmosphere inversion

在对ROPP反演软件进行系统移植与部分修改之后，还可以根据掩星事件发生的经纬度和时间分别进行统计分析.可以量化描述赤道地区、温带与极地的反演结果误差并进行对比，也可量化描述同一地区不同地方时的误差．进一步将利用一个月左右的数据，对不同纬度带的反演结果进行分析

# 参考文献

[1] Fischbach F F.A satellite method for pressure and temperature below 24km[J].Bull.Am．Meteor.Soc.,1965, 46:528-532   
[2] Rocken C,Anthes R,Exner M,et al. Analysis and validation of GPS/MET data in the neutral atmosphere [J]. J.Geophys.Res.:Atmos.,1997,102(D25):29849-29866   
[3] Gorbunov M E,Gurvich A,Bengtsson L.Advanced Algorithms of Inversion of GPS/MET Satellite Data and Their Application to Reconstruction of Temperature and Humidity [R].Hamburg,Germany:Max-Planck-Institut fir Meteorologie,1996   
[4] Mostert S,Koekemoer J A. The science and engineering payloads and experiments on SUNSAT[J].Acta Astron., 1997,41(4-10):401-411   
[5] Gars S.The Radio Occultation Processing Package (ROPP）user guide.II: Forward model and 1D-Var modules [EB/OL].[2015-03-15].http://www.romsaf.org/romsaf_ropp-ug_ldvar.pdf   
[6] Tan Xingang,Sun Yueqiang,Bai Weihua,et al. ROPP software in inverting occultation data and accuracy analysis[J]. Sci.Tech. Eng.,2013,13(20):5898-5902.In Chinese (谭鑫刚，孙越强，白伟华，等.ROPP 掩星数据反演软件 及其精度分析[J]．科学技术与工程,2013,13(20):5898-5902)   
[7] Gorbunov M E,Lauritsen K B,Rhodin A,et al. Radio holographic fltering,error estimation,and quality control of radio occultation data[J].J.Geophys.Res.,2006, 111(D10),D10105   
[8] Kuo Y H,Wee T K, Sokolovskiy S,et al. Inversion and error estimation of GPS radio occultation data[J].J.Meteor.Soc.Japan．Ser.II,2004,82(1B):507-531   
[9] Wang X,Lü D R.Comparative analysis of inversion methods of retrieving atmospheric profiles with GPS occultation measurements[J].Chin.J.Geophys.，2007, 50(2):329-338   
10] Gorbunov M E. Ionospheric correction and statistical optimization of radio occultation data[J].Radio Sci.,2002, 37(5):1084,doi:10.1029/2000RS002370