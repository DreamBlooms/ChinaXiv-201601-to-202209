# 恒星大气参数测量

袁海龙，张彦霞，张昊彤，赵永恒中国科学院光学天文重点实验室（国家天文台），北京100012摘要：从恒星的研究意义谈起，介绍了恒星大气参数的基本概念及研究意义；阐述了恒星参数测量方法的分类：直接测量和间接测量。着重评述了间接测量方法，包括测光方法、红外流量方法、巴尔默线轮廓拟合、谱线比例方法、线指数方法、金属线诊断法、光谱模板拟合和机器学习方法等。指出在大型巡天数据中光谱模板拟合与机器学习方法的优势及其广泛应用。对于高分辨率光谱，金属线诊断仍然备受天文学家青睐；红外流量方法的测量结果常用来定标。

关键词：参数测量；恒星；光谱；机器学习中图分类号：P141.5 文献标识码：A 文章编号：1672-7673（2018）04

天文学是一门研究宇宙天体的形成和演化规律的古老学科。恒星是宇宙中研究最为广泛和详细的天体，恒星诞生于星际物质，经过漫长岁月的演化，形成白矮星、中子星或者黑洞，同时对星际物质进行反馈。恒星是星系的重要组成单元，星系又构成了当前可见宇宙的主要部分。以恒星为基础，可以通过运动学、动力学研究星团、星系、星系并合和星系团的物质分布和演化规律，进一步研究整个宇宙演化的过去、现在和未来。因而可以认为，研究恒星是研究整个宇宙的基点。

恒星是由引力聚集在一起发光的气体球，通常主要成份是氢气。大多数情况下，在恒星的内部持续进行着剧烈的核反应，并由此释放大量的能量，从而维持高温高压的环境并产生足以对抗外层大气重力的压力，其生命周期从数百万年到数百亿年以上，使得整个恒星在外表看起来是一个长期持续的发光体。除了太阳之外，恒星距离人类往往太过遥远，难以近距离观测研究，即使是太阳也难以真正近距离研究。因而，天文学家只能通过对恒星发出的光进行观测和分析，从它们的位置、星等和光谱出发，研究每一颗恒星的外部特征（例如：方向、距离和运动速度等）和内在属性（例如：质量、半径、大气成份、内部大气分布、大气湍流、脉动、自转和磁场等等），其中恒星大气参数的测量是开展恒星相关科学研究的基础。

# 1恒星大气参数

恒星大气是指能直接观测到的部分，是恒星内部与星际介质的过度区间。恒星大气覆盖在恒星核心、辐射区和对流区之上，再进一步可以分成若干层，如光球层、色球层、色球日冕过渡层和日冕。光球层是恒星主要的可见部分，是恒星大气的最底层，恒星的辐射主要从这一层发出，穿过外层大气，到达观测者，恒星黑子就发生在光球层。因而可以认为，恒星大气参数主要由光球层决定，其厚度定义为一个光深。通常来说，恒星大气参数包括有效温度 $T _ { \mathrm { e f f } }$ 、表面重力 $\log g$ 、金属丰度[Fe/H]和微观湍流速度，这些参数是恒星大气

参数测量的主要内容。

# 2直接测量

恒星大气参数的直接测量有非常苛刻的要求。例如有效温度 $T _ { \mathrm { e f f } }$ ，定义为与恒星单位面积光度相等的黑体的温度，并由斯特藩一玻尔兹曼定律实现转换。从观测的角度看，即使能忽略或者修正消光的影响，仍然需要地面上测量的恒星的各个波段观测总流量，以及恒星的角直径，即恒星直径与到观测者的距离的比值。能精确直接测量恒星角直径的一般是距离地球非常近的，因此在数量上非常有限。其他的多种方法，例如干涉测量和月掩星等等，测量精度都难以提高。对表面重力的直接测量，则需要精确测量质量和恒星半径。利用掩食双星可以达到较好的精度，单星的测量则非常困难。目前，通过直接测量获得大气参数的恒星已有150多颗星，其中主要代表有太阳和织女星（英文名Vega）。

# 3间接测量

间接测量是目前恒星大气参数测量的主要手段，基本思路是基于一些已知参数的恒星，利用已有的观测资料，建立观测数据与参数的某种映射或关系，从而推断待测恒星的参数具体的间接测量方法多种多样，主要的区别在于这几方面：数据类型、处理方法和优化技术。数据类型分为测光数据和光谱数据。处理方法包括最初的网格定标、从数据构建经验解析函数（线性拟合和非线性拟合）、模板拟合（例如卡方最小）和机器学习等。优化技术则是对算法的各个环节的成功率、精确性和速度等细节的处理方法的优化改善。

# 3．1测光方法

相对于光谱观测，测光观测具有很大的优势，包括：能够在较短的时间内获得大天区、甚至全天的数据；可以完备特定星等极限；可以同时获得多个波段的数据；增加观测时间可以进行时变源的长期监控。这些优势是光谱观测难以比拟的。虽然目前国际上的大天区光谱巡天观测越来越多，其观测的光谱有数百万之多，但与实际恒星的数量相差甚远。因此，从测光数据出发对恒星大气参数进行测量，虽然获得的参数没有光谱数据获得的准确但是能获得比光谱观测更多的恒星参数，具有非常大的应用价值。

测光网格定标方法。根据特定的宽波段测光系统，结合理论计算的规律，建立从测光到有效温度和表面重力的映射网格，并用织女星或者其他已知参数的恒星进行标定。文[1]针对测光系统给出一个从测光数据到参数的映射图表，在早期的多波段测光巡天中应用广泛，做到温度 $T _ { \mathrm { e f f } }$ 精度200K，表面重力logg精度 $0 . 2 \mathrm { d e x }$ ，但对金属丰度不敏感，且对表面重力的估计只适合于Am型星。文[2]利用模型计算了理论的色指数。

光谱能量分布(Spectral energy distribution,SED)拟合。除了直接的定标，还有很多利用测光数据的一些优化算法。文[3]介绍了当时最主流的测光参数测量方法，即利用测光数据建立光谱能量分布，然后与理论模型拟合，寻找最佳匹配，估计有效温度、表面重力、金属丰度和微观湍流等等。这种光谱能量分布拟合方法的温度误差在几百开尔文，但其他量不太准，尤其是金属丰度。文[4]利用贝叶斯理论，用赫罗图作为先验分布，从2MASS测光数据和视差，估计依巴谷FGK恒星的温度和消光，温度精度达到 200K，消光精度0.2等。文[5]介绍了VOSA软件，通过银河系演化探测器（Galaxy Evolution Explorer,GALEX）、斯隆数字巡天（Sloan Digia Sky Survey，SDSS）、2 微米全天巡天（2 Micron Al-sky Survey，2MASS）、广域红外巡天探测（Wide-feld Infrared Survey Explorer，WISE）和可见光与红外巡天望远镜（Visible and nfrared SurveyTelescope for Astronomy，VISTA）数据建立光谱能量分布，估计M型星的恒星参数。

色指数温度关系方法。色指数（两个波段的星等差值）与温度存在某种非常强的关系。从测光可以获得色指数，然后利用已知有效温度的目标进行数学回归，即可得到较好的数学模型[6-11]。

3．2红外流量方法

红外流量方法（The InfraRedFluxMethod，IRFM）的原理是恒星在红外波段的表面流量对温度不敏感[12-13]，几乎不依赖理论模型，是最接近有效温度定义的方法。该方法的温度测量精度大概是 $1 \% { \sim } 2 \%$ ，该方法还可以用来测量恒星的角直径。

# 3．3巴尔默线轮廓拟合

巴尔默线与有效温度有较强的耦合，利用线翼进行拟合，能对温度进行较好的估计。但是在温度较高时（8000K以上），温度与表面重力耦合比较强，需要借助其他途径同时测定，参见文[14-15]。

# 3．4谱线比例方法

不同谱线对有效温度、表面重力和金属丰度的相关性不同，有的呈正相关，有的呈负相关，且相关的程度各不相同。文[16]用谱线深度比确定温度，精度达到10K。

# 3．5线指数方法

从光谱中提取与参数相关的线指数，进而建立这些指数与大气参数相关的数学模型。应用最广的是文[17]提出的Lick 指数，另外有Rose 指数[18]、新Lick巴尔默指数[19]和LICK/SDSS指数[2]等等。文[21]用322个等值宽度比例对有效温度进行估计，用100多条FeI线的等值宽度进行金属丰度估计，方法应用于FGK矮星和GK巨星，可达到74K的有效温度精度和0.07dex的金属丰度精度。

# 3．6金属线诊断法

对高分辨率光谱，可以结合电离平衡和激发平衡，同时解出有效温度、表面重力和微观湍流。例如利用FeI谱线得到的丰度与激发电势无关确定有效温度，FeI和FeII谱线得到的丰度一致确定表面重力，而微观湍流速度是根据FeI的丰度与等值宽度无关确定的。其它元素比如TiI和TiII、CrI和CrⅡI等也可以使用。金属线诊断法需要通过辅助手段测量若干金属线的等值宽度，往往需要人机交互，且耗时较长，但其测量结果具有较高的精度，是处理高分辨光谱的主流方法之一。这方面最有代表性的软件是MOOG，它最早由Sneden于1973年基于C语言编写[22]。后来研究人员以它为基础进行了一系列的改进和集成，例如FAMA[23]，GAUFRE[24]，MyGIsFOS[25]和iSpec[26]等。

# 3．7光谱模板拟合

光谱模板拟合是目前非常普遍的方法，并且常常作为参数测量的初始步骤，更精细的例如金属线诊断方法一般以它的结果作为初始值。对整个观测光谱拟合，首先需要预处理（例如连续谱归一和去红移等），然后与理论光谱模板比较，寻找最佳匹配，最佳匹配模板的参数即可作为目标光谱的参数。一般需要建立一个多维的光谱网格，考虑不同的参数包括有效温度、表面重力、金属丰度和微观湍流等等。光谱模板拟合综合使用了全部的光谱信息，获得的结果可靠性较高；测量过程的自动化易于实现，适合应用到海量光谱的参数测量中。该方法需要考虑消光对光谱的红化。在算法的具体应用中，主要考虑优化网格本身的精度，以及提高网格拟合的速度及精度。

网格的精度决定了最终测量的精度，网格越精细，测量越准确，但是耗时也更长。文[3]介绍了同时利用测光和光谱数据测量恒星参数，还简单分析了视向速度实验（Radialvelocity experiment，RAVE）光谱覆盖范围的在参数测量中的不足之处。文[27]介绍了光谱库网格与贝叶斯模型的结合，并应用到红外空间天文台（Infrared Space Observatory）的短波光谱仪数据中。文[28]介绍了RAVE巡天的第2版数据数万条光谱的发布情况，详述了基于理论光谱库的卡方最小模板匹配方法在恒星参数测量中的应用。文[29]介绍了SDSS-SEGUE巡天的恒星参数测量程序SSPP，综合了多种测量方法，包括多种线指数方法和基于理论光谱库的卡方最小光谱拟合方法。ULYSSZwitterT,SiebertA,MunariU,et al.TheRadial Velocity Experiment (RAVE): second data release [J]. AJThe Astronomical Journal,2008,136(1):421-451.使用ELODIE光谱[31]，对每个像素以有效温度、表面重力和金属丰度为变量进行多变量高阶多项式拟合，得到一个基于实测光谱的网格，可以从中获得任意恒星参数下的光谱；同时ULYSS还引入了点扩散函数综合考虑各种谱线致宽效应。GAUFRE-CHI2 Valentini M,Morel T,Miglio A,et al. GAUFRE: a tool for an automated determination ofatmospheric parameters from spectroscopy [C]// EPJWCEuropean Physical Journal Web ofConferences.2013、 MyGIsFOS Sbordone L，Caffau E，Bonifacio P，et al. MyGlsFOS:anautomated code for parameter determination and detailed abundance analysis in cool stars [J].A&AAstronomy& Astrophysics,2014,564:A109 和 iSpec[2软件均以光谱模板拟合作为主要参数测量方法。文[32]介绍了CFI和ULYSS代码在LAMOST[33]的光谱大气参数测量中的应用，并将结果与高分辨光谱参数进行了比较。文[34]介绍了中高分辨率光谱参数测量软件GSSP（Grid Search in Stellar Parameter，GSSP），能够兼容各种模板光谱库，同时专门针对双星光谱参数测量提供了相应的程序。文[35]介绍了使用MILES实测光谱库[36-37]构建的多项式拟合模板网格，然后使用卡方最小方法和下山算法等进行网格匹配，应用于LAMOST光谱的恒星大气参数测量。文[38]应用ROTFIT代码对LAMOST-Kepler恒星进行了参数测量，使用的参考光谱是INDO-US光谱库[39]，在光谱拟合时，将光谱分隔为8个区分别拟合，然后加权求和，选择最合适的模板作为输出参数。文[40]介绍了APOGEE巡天的参数测量程序ASPCAP，主要使用基于理论光谱库的卡方最小方法测量有效温度、表面重力和金属丰度。

对同样的网格，提高拟合的速度和精度也是算法优化的一个方向。例如文[41]研究了局部网格多元线性回归，针对GAIA[42]光谱数据应用MATISSE算法，在完成一个粗糙的整体网格搜索后，将参数投影到特定的向量上进行优化。

# 3．8机器学习方法

机器学习是研究利用计算机的超强计算能力来模拟或实现人类的学习行为，以获取新的知识或技能，其具体算法各种各样，在恒星大气参数测量中，通过已知参数的恒星作为训练样本，根据其观测数据 $X$ 和参数Y（或者回归信息）进行学习，然后估计新的数据对应的参数（或者回归）。相比于其他传统的参数算法，机器学习算法的优点是效率高，不需要预先猜测数学模型，人工干预度低，可以应用到海量的光谱数据处理当中。

文[43]测试了人工神经网络方法在光谱分类中的应用，使用的是多层后向传播网格（MBPN）。文[44]介绍了使用主成分分析（Principal Component Analysis，PCA）方法对光谱降维，然后使用MBPN神经网络进行光谱参数测量，结果表明光谱数据降维能大幅度减少运行负荷，同时保证计算精度。文[45]比较了从光谱指数测量大气参数的几种机器学习方法，包括距离度量方法（MDM）、K近邻方法和局部加权回归方法（LocalWeightedRegression，LWR），以及这些方法与PCA降维的组合，测试发现LWR 和PCA降维组合方法的效果最佳。文[46]使用最近邻方法（KNearest Neighbour，KNN），比较了使用连续谱归一化光谱、线指数和谱线三种方式的输入测量参数，发现线指数、谱线达到的精度相似，比使用连续谱归一化光谱的精度略高。文[47]在利用光谱线指数进行参数测量时，使用遗传算法进行光谱指数的筛选，结合KNN进行训练和预测，在缩减程序运行时间的同时，预测误差减小了 $3 5 \%$ 以上。文[48]针对Hamburg/ESO巡天，对光谱进行特征提取，包括吸收线、发射线、吸收带、连续谱形状和光谱能量分析二分点等信息，然后结合贝叶斯理论进行特征训练，采用经典统计方法，对FG型恒星进行了光谱分类，对信噪比10以上的光谱测试精度为有效温度 400K，表面重力和金属丰度好于0.68dex。文[49-51]介绍了多种机器学习方法在大型巡天例如GAIA中的应用。文[52]介绍了MBPN人工神经网络在亚矮星分类中的应用。文[53]介绍了人工智能技术在低分辨可见光波段光谱的应用，另外还扩展了几个人工神经网络的模型作为辅助方法。文[3]提到了从测光和光谱数据出发，利用人工智能技术，例如神经网络，实现观测到参数的“高层”定标。文[54]介绍了神经网络方法在2.34米万努巴普望远镜光谱中的应用。文[55]研究了使用非线性回归模型对SDSS/SEGUE的光谱进行训练，结合了PCA降维和波长范围选择（WRS）降维。SDSS的参数测量用到了神经网络算法，并且测试表明其同样可以应用到LAMOST的光谱参数测量中 Lee Y S,Beers T C, Carlin JL,et al.Application of the SEGUE stellar parameter pipeline toLAMOST stellar spectra [J].AJThe Astronomical Journal,2015,150(6): 187。文[57]使用从 SDSS获得的经红化改正过的测光数据，利用KNN技术估计恒星的金属丰度。文[58]使用 PCA方法，对ELODIE[31]和 $\mathrm { S ^ { 4 } N }$ 光谱库进行降维，然后建立温度的线性回归，内部误差为50K，并且与红外流量方法进行了对比。文[59]设计了Cannon代码，它对观测数据用历史已知参数进行标记，用建立学习模型来预测未知的观测数据，通过对APOGEE 数据进行测试，验证误差与APOGEE自身的误差相似[60]。文[61]利用核主成分分析和线性回归方法测量LAMOST光谱的大气参数和绝对星等。文[62]使用深度神经网络方法对SDSS光谱进行恒星参数测量。文[63]使用Cannon用APOGEE参数结合LAMOST光谱，对45

LAMSOT巨星光谱进行了参数测量。文[64]使用Cannon基于APOGEE和K2/EPIC数据进行训练，重新测量了RAVE-on数据的恒星参数。

从恒星大气参数测量方法的演化趋势来看，随着观测数据的数量和类型的增多，使用的信息从局部扩展到全谱，算法的复杂度越来越高，测量精度也越来越准确。这说明，一方面天文数据的获取能力逐步增强；另一方面计算机的数据运算能力大幅度提升并且得到了天文界的认可，越来越多的面向大数据的新技术、新软件和新算法被天文研究人员使用Casey A R, Hawkins K, Hogg D W, et al. The RAVE-on catalog of stellar atmospheric parametersand chemical abundances for Chemo-dynamic studies in the Gaia era [J]. AJThe AstronomicalJournal,2017,840(1):59.涂洋,张彦霞,赵永恒,等.光谱分析软件在天文学研究中的应用 [J].天文研究与技术,2016,13(1):124-132.。当前应用最广的算法是全谱拟合，这需要有大量的光谱数据，同时需要有强大的计算能力，这样才能对海量的数据从高密度、高精度的模板网格中快速准确地找出最佳匹配。机器学习以其独有的方式对数据进行训练和预测，对天文学的研究具有重要意义。而在高分辨率高信噪比光谱的参数测量方面，金属线诊断方法因为能够获得非常高精度的测量结果而仍然备受关注。另外，红外流量方法的测量结果常常被用来作为参考基准。

# 4总结

恒星的研究和恒星大气参数的测量对于研究宇宙的形成和演化具有至关重要的意义。因此如何提高恒星参数的测量精度一直以来是很多研究者深入探究的课题。恒星大气参数主要包括有效温度 $T _ { \mathrm { e f f } }$ 、表面重力 $\log g$ 、金属丰度[Fe/H]、自转速度、微观湍流和宏观湍流等等。为此，天文学家提出了各种各样的测量方法。在众多的恒星大气参数测量方法中，除了少数恒星能够进行直接测量，基本上都使用间接方法从多波段测光或光谱中获得，可以大致分为测光方法、红外流量方法、巴尔默线轮廓拟合、谱线比例方法、线指数方法、金属线诊断法、光谱模板拟合和机器学习方法。机器学习方法作为一个纯数学方法，其在天文学上的广泛应用是随着天文大数据时代的到来和计算机运算能力的大幅度提升而逐步推广应用的，并且对前面几种天文学上的方法都能覆盖兼容，其在海量数据处理上应用的效率和精度都得到了广泛的认可。其他方法如金属线诊断和红外流量方法等，凭借其高精确度和高稳定性等特征，在高分辨光谱参数测量领域仍然备受关注。

# 参考文献

[1]Moon TT,Dworetsky M M. Grids for the determination of effective temperature and surface gravity of B,A and F stars using uvby-beta photometry [J]. MNRASMonthly Notices of the Royal Astronomical Society, 1985, 217: 305-315.   
[2] Lester JB, Gray R O, Kurucz R L. Theoreical uvbyβ indices [J]. ApJSThe Astrophysical Journal Supplement Series, 1986, 61: 509-529.   
[3] Gray R O. Parameterization of stars [J]. MmSAIMemorie della Societa Astronomica Italiana, 2006, 77: 1123-1129.   
[4] Bailer-Jones C A L. Bayesian inference of stellar parameters and interstellar extinction using parallaxes and multiband photometry [J]. MNRASMonthly Notices of the Royal Astronomical Society, 2011, 411: 435-452.   
[5] Bayo A, Rodrigo C, Barrado D, et al. Physical parameters of young M-type stars and brown dwarfs with VOSA [C]//ASInEAstronomical Society of India Conference Series. 2014: 93- 101.   
[6] Alonso A, Arrbas S, Martinez-Roger C. The empirical scale of temperatures of the low main sequence (F0V-K5V)[J].A&AAstronomy & Astrophysics,1996, 313: 873-890.   
[7] Houdashelt M L，Bell R A， Sweigart A V. Improved color-temperature relations and bolometric corrections for cool stars [J]. AJThe Astronomical Journal, 200o,119(3): 1448-   
[8] Sekiguchi M， Fukugita M. A study of the B-V color-temperature relation [J]. AJThe Astronomical Journal, 2000,120(2) : 1072-1084.   
[9]VandenBerg Don A， Clem JL. Empirically constrained color-temperature relations. I. $\mathrm { \Delta B V ( R I ) _ { C } }$ [J].AJThe Astronomical Journal, 2003,126(2): 778-802.   
[10] Clem JL, Vandenberg D A, Grundahl F,et al. Empirically constrained color-temperature relations. II. uvby [J].AJThe Astronomical Journal, 2004,127(2): 1227-1256.   
[11] Ramirez Ivan., Meléndez Jerge. The effective temperature scale of FGK stars. II. $T _ { \mathrm { e f f } }$ color: [Fe/H] calibrations [J]. AJThe Astronomical Journal, 2005, 626(1): 465-485.   
[12] Blackwell D E, Shallis M J. Stellar angular diameters from infrared photometry. application to Arcturus and other stars; with efective temperatures [J]. MNRASMonthly Notices of the Royal Astronomical Society, 1977, 180(2): 177-191.   
[13] Blackwell D E, Petford A D, Shalls M J. Use of the infra-red flux method for determining stellar effective temperatures and angular diameters-the stellar temperature scale [J]. A&AAstronomy & Astrophysics,1980, 82(1-2): 249-252.   
[14] Gray D F. The observation and analysis of stellr photospheres [M]. [S.1.]Camb. Astrophys: Ser: Cambridge University Press,1992.   
[15] Heiter U, Kupka F, van't Veer-Menneret C,et al. New grids of ATLAS9 atmospheres I: influence of convection treatments on model structure and on observable quantities [J]. A&AAstronomy & Astrophysics, 2002,392: 619-636.   
[16] Gray D F, JohanSon H L. PRECISE MEASUREMENT OF STELLAR TEMPERATURES USING LINE-DEPTH RATIOSPrecise measurement of stellar temperatures using line-depth ratios [J]. PASPPublications of the Astronomical Society of the Pacific,1991,103: 439-443.   
[17] Worthey Guy, Faber S M, Gonzalez J J, et al. Old stellar populations. 5: absorption feature indices for the complete LICK/IDS sample of stars [J]. ApJSThe Astrophysical Journal Supplement Series, 1994, 94(2): 687-722.   
[18] Rose James A, Bower R G, Caldwell N,et al. Stellar population in early-type galaxies: Further evidence for environmental influences [J]. AJThe Astronomical Journal,1994, 108(6): 2054-2068.   
[19] Jones Lewis A,Worthey Guy. New age indicators for old stellar populations [J]. AJThe Astronomical Journal, 1995, 446: L31-L34.   
[20] Franchini M, Morossi C， Di Marcantonio P, et al. THE LICK/SDSS LIBRARY. I. SYNTHETIC INDEX DEFINITION AND CALIBRATIONThe Lick/SDSS library. I. synthetic index definition and carlibration [J]. AJThe Astronomical Journal, 2010, 719(1): 240-263.   
[21] Teixeira G D C, Sousa S G, Tsantaki M, et al. New $T _ { \mathrm { e f f } }$ and $[ \mathrm { F e / H } ]$ spectroscopic calibration for FGK dwarfs and GK giants [J]. A&AAstronomy & Astrophysics, 2016, 595, A15.   
[22] Sneden Chris, Bean J, Ivans I, et al. MOOG: LTE line analysis and spectrum synthesis [CP]. [S.l.]: Astrophysics Source Code Library, 2012.   
[23] Magrini Laura, Randich S,Friel E, et al. FAMA: an automatic code for stellar parameter and abundance determination [J]. A&AAstronomy & Astrophysics, 2013, 558, A38.   
[24] Valentini M, Morel T, Miglio A, et al. GAUFRE: a tool for an automated determination of atmospheric parameters from spectroscopy [Cl// EPJWEEuropean Physical Journal Web of Conferences. 2013.   
[25] Sbordone L, Caffau E,Bonifacio P, et al. MyGIsFOS:an automated code for parameter determination and detailed abundance analysis in cool stars [J]. A&AAstronomy & Astrophysics,2014, 564: A109.   
[26] Blanco-Cuaresma S, Soubiran C, Heiter U,et al. Determining stellr atmospheric parameters and chemical abundances of FGK stars with iSpec [J]. A&AAstronomy & Astrophysics, 2014, 569: A111.   
[27] Shkedy Z, Decin L,Molenberghs G, et al. Estimating stellar parameters from spectra using a hierarchical Bayesian approach [J]. MNRASMonthly Notices of the Royal Astronomical Society, 2007,377: 120-132.   
[28] Zwitter T, Siebert A, Munari U, et al. The Radial Velocity Experiment (RAVE): second data release [J].AJThe Astronomical Journal, 2008,136(1): 421-451.   
[29] Lee Y S,Beers T C, Sivarani T, et al. The SEGUE stellar parameter pipeline. I. description and compar1son oI inaividual metnoas [JJ. AJIne Astronomical Journal, ZUu8,136()): ZU22- 2049.   
[30] Koleva M, Prugniel P, Bouchard A,et al. ULySS: a full spectrum fitting package [J]. A&AAstronomy & Astrophysics, 2009, 501(3):1269-1279.   
[31] Prugniel P, Soubiran C. A database of high and medium-resolution stellar spectra [J]. A&AAstronomy & Astrophysics, 2001, 369: 1048-1057.   
[32] Wu Yue,Du Bing,Luo Ali, et al. Automatic stellar spectral parameterization pipeline for LAMOST survey [Cl// Proceedings of the International Astronomical Union， IAU Symposium. 2014: 340-342.   
[33] Cui Xiang-QunQ, Zhao YH,Chu Y,et al.TheLargeSky Area Multi-ObjectFiber Spectroscopic Telescope (LAMOST) [J]. RAAResearch in Astronomy and Astrophysics, 2012, 12(9): 1197-1242.   
[34] Tkachenko A. Grid search in stellar parameters: a software for spectrum analysis of single stars and binary systems [J]. A&AAstronomy & Astrophysics, 2015, 581: A129.   
[35] Xiang M,Liu X, Yuan H, et al. The LAMOST stellar parameter pipeline at Peking University - LSP3 [J]. MNRASMonthly Notices of the Royal Astronomical Society, 2015, 448(1): 822- 854.   
[36] Sanchez-Blazquez P, Peletier R F, Jiménez-Vicente J, et al. Medium-resolution Isaac Newton Telescope library of empirical spectra [J]. MNRASMonthly Notices of the Royal Astronomical Society, 2006,371(2): 703-718.   
[37] Cenarro A J, Peletier R F, Sänchez-Blazquez P, et al. Medium-resolution Isaac Newton Telescope library of empirical spectra - II. the stellar atmospheric parameters [J]. MNRASMonthly Notices of the Royal Astronomical Society, 2007, 374(2): 664-690.   
[38] Frasca A, Molenda-Zakowicz J, De Cat P, et al. Activity indicators and stellar parameters of the Kepler targets. an application of the ROTFIT pipeline to LAMOST-Kepler stellar spectra [J].A&AAstronomy & Astrophysics, 2016, 594: A39.   
[39] Valdes F, Gupta R, Rose JA, et al. The indo-US library of coudé feed stellar spectra [J]. ApJSThe Astrophysical Journal Supplement Series, 2004, 152(2): 251-259.   
[40] Garcia Pérez Ana. E,Allende Prieto Carles, Holtzman Jon A, et al. ASPCAP: the APOGEE Stellr Parameter and Chemical Abundances Pipeline [J]. AJThe Astronomical Journal, 2016, 151(6): 144.   
[41] Bijaoui A, Recio-Blanco A,de Laverny P. Parameter estimation from an optimal projection in a local environment [JCl//AIPEAmerican Institute of Physics Conference Series. 2008: 54- 60.   
[42] Collaboration G,Brown A G A, Vallenari A, et al. Gaia data release 1. summary of the astrometric, photometric,and survey properties [J]. A&AAstronomy & Astrophysics, 2016, 595: A2.   
[43] Gulati R K, Gupta R.Automated classification of a large database of stellar spectra [C]// ASPEAstronomical Data Analysis Software and Systems IV, ASP Conference Series. 1995: 253-256.   
[44] Singh H P, Gulati R K, Gupta R. Stellar spectral classification using principal component analysis and artificial neural networks [J]. MNRASMonthly Notices of the Royal Astronomical Society, 1998,295(2): 312-318.   
[45] Fuentes O, Gulati R K. Instance-based machine learning methods for the prediction of stellar atmospheric parameters [Cl// ASPEAstronomical Data Analysis Software and Systems IX, ASP Conference Series. 2000: 611-614.   
[46] Fuentes O, Gulati R K. Prediction of stellar atmospheric parameters from spectra, spectral indices and spectral lines using machine learning [C]//RMxACRevista Mexicana de Astronomia y Astrofisica Conference Series.2001: 209-213.   
[47] Ramirez JF, Fuentes O, Gulati R K, et al. Prediction of stellar atmospheric parameters using instance-based machine learning and genetic algorithms [EJ]. ExAExperimental Astronomy, 2001, 12(3): 163-178.   
[48] Christlieb N, Wisotzki L, GraBhoff G. Statistical methods of automatic spectral classification and their application to the Hamburg/ESO survey [J]. A&AAstronomy & Astrophysics, 2002, 391: 397-406. and results [M]. London $\because$ Narosa Publising House,2002: 83.   
[50] Bailer-Jones C A L, Gupta R, Singh H P.An introduction to artificial neural networks [M]. London $\because$ Narosa Publising House, 2002: 51.   
[51] Bailer-Jones C A L. Determination of stellar parameters with GAIA [J]. Ap&SSAstrophysics and Space Science, 2002, 280(1/2): 21-29.   
[52] Winter C, Jeffery C S, Drilling J S. Automatic classfication of subdwarf spectra using a neural network [J]. Ap&SSAstrophysics and Space Science, 2004, 291(3): 375-378.   
[53] Rodriguez A，Arcaya B,Dafonte C,et al. Automated knowledge-based analysis and classification of stellar spectra using fuzzy reasoning [J]. Expert Systems with Applications, 2004,27:237-244.   
[54] Giridhar S, Muneer S, Goswami A. Automated classification and stellar parameterization [J]. MmSAIMemorie della Societa Astronomica Italiana, 2006,77: 1130-1135.   
[55] Re Fiorentin; P, Bailor-Jones C A L,Lee Y S,et al. Estimation of stellar atmospheric parameters from SDSS/SEGUE spectra [J]. A&AAstronomy & Astrophysics, 2007, 467(3): 1373-1387.   
[56] Lee Y S, Beers T C, Carlin JL,et al. Application of the SEGUE stellar parameter pipeline to LAMOST stellar spectra [J]. AJThe Astronomical Journal, 2015,150(6): 187.   
[57] Kerekes G, Csabai I, Dobos L, et al. Photo-Met: a non-parametric method for estimating stellr metallicity from photometric observations [J]. ANAstronomische Nachrichten, 2013, 334(9): 1012-1015.   
[58] Munoz Bermejo J, Asensio Ramos A, Allende Prieto C.A PCA approach to stellar effective temperatures [J].A&AAstronomy & Astrophysics,2013, 553: A95.   
[59] Ness M., Hogg D.W., Rix H.-W., et al. The CANNON: A Data-Driven Approach to Stellar Label Determination [J]. AJThe Astronomical Journal, 2015, 808(1): 16.   
[60] Mészaros Sz., Holtzman J., Garcia Pérez A.E., et al. Calibrations of Atmospheric Parameters Obtained from the First Year of SDSS-III APOGEE Observations [J]. AJThe Astronomical Journal, 2013,146(5): 133.   
[61] Xiang M., Liu X.-W., Shi J.-R., et al. Estimating stelar atmospheric parameters, absolute magnitudes and elemental abundances from the LAMOST spectra with Kernel-based principal component analysis [J]. MNRASMonthly Notices of the Royal Astronomical Society, 2017, 464(3): 3657-3678.   
[62] Li X.-R., Pan R.-Y., Duan F.-Q: Parameterizing Stellar Spectra Using Deep Neural Networks [J]. A&AAstronomy & Astrophysics, 2017, 17(4): 36.   
[63] Ho AY Q, Ness MK, Hogg D W, et al. Label transfer from APOGEE to LAMOST: precise stellar parameters for 450,000 LAMOST giants [J].AJThe Astronomical Journal, 2017, 836(1): 5.   
[64] Casey A R, Hawkins K, Hogg D W, et al. The RAVE-on catalog of stellar atmospheric parameters and chemical abundances for Chemo-dynamic studies in the Gaia era [J]. AJThe Astronomical Journal, 2017, 840(1): 59.   
[65]钟守波,韩波,张彦霞,等.天文大数据管理工具的设计与实现 [J].天文研究与技术, 2015, 12(4): 510-517. Zhong Shoubohoube., Han Boe., Zhang Yanxiaanxia., et al. Design and implementation of a software tool package for managing massive astronomical data [J]. Astronomical Research & Technology,2015, 12(4): 510-517.   
[66] 涂洋,张彦霞,赵永恒,等.光谱分析软件在天文学研究中的应用[J].天文研究与技术, 2016,13(1): 124-132. Tu Yangang.， Zhang Yanxiaanxia.， Zhao Yonghengongheng., et al. Application of spectral analysis softwares in astronomy[J]. Astronomical Research & Technology, 2016,13(1): 124- 132.   
[67]陈淑鑫,罗阿里,孙伟民.R语言应用于LAMOST光谱分析初探[J].天文研究与技术, 2017, 14(3): 363-368. Chen Shuxinhuxin., Luo Alili., Sun Weimineimin. Application of R language in LAMOST spectral analysis [J]. Astronomical Research & Technology, 2017,14(3): 363-368.

# Survey of Stellar Atmosphere Parameter Estimation

YUAN Hailong, ZHANG Yanxia, ZHANG Haotong, ZHAO Yongheng Key Laboratory of Optical Astronomy, National Astronomical Observatories, Chinese Academy of Sciences,20A Datun Road, Chaoyang District, 100012, Beijing,P.R.China

Abstract: Starting with the significance of the stellar research, the basic conception and importance of stellar atmosphere parameters are introduced.The two major classes of estimation approaches of stellar atmosphere parameters,the direct technique and the indirect technique, are discussed.This paper focuses on the indirect technique, which can be further divided into several methods: the photometric method, the infrared flux method,the Balmer profile method, the spectral line ratio method,the line index method,the metal line diagnostics method,the spectral template fitting method and the machine learning method. While the spectral template fiting method is widely used in current large spectroscopic survey projects, such as SDSS, RAVE and LAMOST, the machine learning method has shown its advantages in many specific situations. Among various machine learning methods and technologies, the most popular ones are principal component analysis (PCA), $\mathbf { k }$ -nearest neighbors (KNN), support vector machine (SVM),and all kinds of artificial neural network (ANN) methods. On the other hand,traditional astrophysical methods still play prominent roles. The metal line diagnostics method is still favored by astronomers when analyzing high resolution spectra.The experimental results from infrared flux method are generallyused ascalibration.

Keywords: parameter estimation; stellar; spectroscope; machine learning