# DA白矮星视向速度测量

赵颖玥1，罗阿理²

1北京市中关村中学，北京100086,2中国科学院光学天文重点实验室（国家天文台），北京100101，

摘要DA白矮星的光谱在光学波段主要由巴尔默线主导。由于谱线比较宽，而且谱线轮廓不对称，传统的线心确定视向速度方法非常困难。本文介绍了一种基于利用白矮星的有效温度和表面重力加速度来选择理论模板通过交叉相关方法来确定DA白矮星的APP速度，再减去白矮星的引力红移就得到了白矮星的视向速度。测试发现对于Teff高于10000K的DA白矮星的低分辨率光谱（ $\boldsymbol { \mathrm { R } } ^ { \sim } 2 0 0 0$ ），在信噪比大于20的情况下，精度在 $\mathrm { 1 0 k m / s }$ 以内。我们测量了 SDSS DR7的DA白矮星观测样本的视向速度，统计发现在 $1 0 0 0 \mathrm { p c }$ 内，视向速度的平均值接近于0。

关键字白矮星；视向速度；模板匹配中图分类号：P141.5

# 1引言

白矮星是银河系绝大部分恒星的最终归宿，银河系中97%的恒星最终都要演化成白矮星。白矮星由于内部停止了核反应，它的演化非常简单，就是不断的冷却。温度越来越低，光度越来越暗，最后变成一颗黑矮星。根据光谱型，白矮星可以分为DA、DB、DC、DO、DZ、DQ等类型[1]，其中 DA 白矮星是最多的，大约占总数的 $7 5 \%$ 。由于白矮星光度低，观测相对困难，特别是获得白矮星的光谱尤其困难。在Sloan 数字巡天2之前，最大的光谱证认的白矮星星表是MaCcook等人[3在1999年发布的，总数仅有2000颗。在他们的星表里仅提供了白矮星的位置，星等，视差，和自行等信息，由于光谱分辨率比较低，没有提供白矮星的大气参数。Sloan 数字巡天使得光谱证认得白矮星的数量增长了10倍以上。2006年，Eisenstein 等人4在 SDSS DR4中证认出 9000 多颗白矮星，Kleinman 等人[5]在 SDSS DR7中证认出了 20000 多颗白矮星，Kepler等人 $^ { [ 6 ] } 2 0 1 5$ 年在 SDSS DR10中也发现了9000 多个新的白矮星。目前光谱识别的白矮星样本已经超过了30000 多个，这对于研究白矮星的统计特性提供了数据基础。

运动学可以帮助我们理解白矮星的星族，因此白矮星的视向速度测量是非常重要的。白矮星的视向速度（或者APP速度）测量相对较少，主要原因是以前的白矮星光谱的信噪比和分辨率较低。最开始的白矮星运动学研究主要依靠白矮星的自行，而简单的把视向速度设置为零[7]。首次比较精确的测量白矮星视向速度的工作是Pauli等人[8][9]，但是白矮星光谱的分辨率比较高。测量低分辨率 DA 白矮星光谱的视向速度是一个非常困难的工作。DA白矮星光谱的特点就是在光学波段主要由比较宽的氢线和连续谱构成，另外由于 stark 效应，使得氢线的轮廓是不对称的[10]，这使得白矮星的视向速度测量误差较大。为了得到低分辨率白矮星光谱的视向速度，本文介绍了一种基于白矮星参数来选取模板光谱通过相关方法来获得DA白矮星的视向速度。由于白矮星除了多普勒效应外，还有引力红移效应，所以我们这个将白矮星的总体效应对应为APP速度。

第二章详细介绍了我们的方法。第三章介绍方法对于模拟数据的应用效果。第四章介绍了用这种方法来计算一些实际观测光谱的应用效果。第五章对这种方法进行了总结。

# 2基于白矮星参数确定模板的交叉相关方法确定DA白矮星的APP速度

# 2.1DA白矮星光谱

DA白矮星光谱非常有特点，也比较好辨认，特别是温度比较高的白矮星。图一上展示了一颗典型的白矮星和一颗主序星的光谱。绿色实线是一颗主序星的光谱，黑色实线是一颗白矮星的光谱。白矮星的四条氢线Hα、Hβ、Hγ、and Hδ在下面用黑色的实线标出。可以看出DA白矮星光谱的特点是线非常少，仅有几条比较强的氢线，而且线特别宽。这两条光谱具有相同的分辨率，但是就同一条氢线相比，主序星的氢线要比白矮星的氢线窄很多。这导致如果仅依靠一条氢线来来测量视向速度，由于宽线的线心不容易确定，误差会相对较大。所以用氢线线心来估计白矮星的APP速度效果并不理想。

![](images/1d02bd24080db7f56546c2dac3a662151716f3d3b46f0462e19c865f82965899.jpg)  
图1上图：绿色实线是一颗主序星光谱，黑色实线是一颗白矮星光谱，其中四条氢线在下方标出。下图：白矮星光谱的四条氢线的放大显示 Figure1Top:Greensolidlinerepresentsthe spectrumofaMain Sequence star whilethe black solidlineis the spectrumof one white dwarf star.Hα、Hβ、Hγ、and ${ \mathrm { ~ H ~ } } \delta$ are marked with short solid lines.Bottom:the zoomed Hα、 $\mathrm { ~ H ~ } \beta$ 、Hγ、and ${ \mathrm { ~ H ~ } } \delta$ lines.

图1下展示了白矮星的四条氢线的放大图。从上到下分别是，Hα、Hβ、Hγ、and ${ \mathrm { ~ H ~ } } \delta$ 。这四条线都表现出轮廓的非对称性，也就是线心两边不一致。这是由于 stack 效应产生的[10]。Hα 相对好一些，Hβ、Hγ、andHδ呈现明显的轮廓不对称。这对利用线心来估计APP速度造成了一定的困难。

# 2.2模板匹配和交叉相关方法计算DA白矮星的APP速度

计算APP速度的方法主要有两种，一种是利用多条谱线的线心来估计，另外一种就是利用模板光谱基于交叉相关来估计[1]。由于白矮星的光谱特点，利用线心方法来估计不能得到准确的速度，所以我们利用基于模板光谱的交叉相关方法来估计视向速度。我们利用白矮星的理论光谱来作为模板光谱。模板光谱是 Koester计算1的。整个模型光谱库的有效温度范围从5000K到80000K,表面重力加速度的范围从7.0到9.5。为了得到准确的APP速度，首先要从模型光谱库中选出最适合的模板光谱。这里说的适合，就是选出的模板光谱要和目标光谱具有较一致的大气参数，即相近的有效温度和表面重力加速度。

模板匹配过程如下：首先对模型光谱和观测光谱进行重新采样，间隔为0.1A，根据DA光谱的特点，在没有谱线的位置选出8个连续谱窗口 (3862,3939,4035,4219,4490,4693,5025,5254)。在这8个窗口计算每一条理论光谱和观测光谱的流量比，然后拟合流量比和波长的5阶多项式函数。随后整条理论光谱和这个多项式相乘并计算相乘多项式后的理论光谱和观测光谱的卡方差。最小卡方差对应的理论光谱作为我们最终选取的模型光谱。

选出模型光谱后，我们用交叉相关方法来估计白矮星的APP速度。流程如下：

首先设定最小速度V_min,最大速度V_max和速度增量V_delt。然后从最小速度开始，目标光谱进行相应的移动后和模板光谱计算相关系数，然后增加一个速度增量继续计算，一直到最大速度，这样就建立了一个相关系数和速度的关系，也就是相关函数。接下来寻找相关函数的最大值，最大值对应的速度就是我们最终计算得到的APP速度。

2.3方法测试

为了测试方法的可靠性，我们生成了一系列的模拟光谱。模拟光谱的生成是在理论光谱的基础上增加噪音，来形成一定信噪比的光谱。然后再假设一定的APP速度，进行相应的移动，作为一个模拟光谱。然后我们利用2.2的方法对这些模拟光谱进行了APP速度的测量，图2展示了对信噪比为20的模拟光谱进行测试的结果。

![](images/fce07cc15b733b7fd932ba7a72052d106a8c3a37e234a11517db56891c98a80f.jpg)  
图1测试样本的误差和温度的关系。  
Figure 1 Relation between the error and the effective temperatur(

图2中，从左上角到右下角展示了APP速度为 $8 0 \mathrm { k m } / s \sim - 8 0 \mathrm { k m } / s$ 的模拟光谱的测试结果。横坐标表示有效温度，纵坐标表示速度的误差。每一幅图表示一条误差随温度变化的曲线。总的来看，误差在低温区相对较大。从5000K到9000K，误差呈现下降趋势。在5000K的时候误差最大。而且总体误差和速度本身有关。速度绝对值越大，误差相对越大。对于有效温度高于10000K的光谱，白矮星的速度的误差小于 $1 0 \mathrm { k m } / s$ 。

# 3 对观测样本进行APP速度测量

我们利用第二章介绍的方法对 SDSS 的DR713I中的DA白矮星样本进行了APP速度测量。这个样本共包含2万多颗白矮星，并且提供了白矮星的有效温度，表面重力加速度，质量等信息。其中信噪比大于 20的DA白矮星大约2000多颗。图3展示了对一颗DA白矮星进行APP速度测量的例子。实线表示相关系数相对于APP速度的函数，虚线指的是最大相关系数对应的速度值。这个速度就是我们计算得到的这颗白矮星的APP速度。

![](images/a2473af6c3db4a624d8f1249822ef1a21df765498e987a0e62ffb6c8ae1bf181.jpg)

![](images/1b93b4ec26474fcaffaacf897d7cf73a279ea7f5a458444a79efd5fd14a2fd76.jpg)  
图3：计算一颗白矮星APP速度的相关函数，横坐标是速度序列，纵坐标是相关系数。虚线指的是最大相关系数对应的速度的值。Figure 3: The correlation function of APP velocity measurement fora DA white dwarf. Dashed line indicatesthe position of max correlation coefficient.  
图4：观测光谱和理论模型光谱拟合的一个例子。黑色实线为观测的光谱，红色需线为相应的匹配最佳理 论的光谱。 Figure4: An example for fitting between the observed spectrum and the theoretical spectrum. Black solid line represents the observed spectrum while the red dotted line is the theoretical spectrum.

3.1白矮星的引力红移计算

在计算APP速度之前，首先我们计算一下白矮星的引力红移。公式如下：

$M$ 表示白矮星的质量， $\boldsymbol { \mathsf { I o g } } \boldsymbol { g }$ 表示白矮星的表面重力加速度， $R$ 表示白矮星的半径，logg鯽表示太阳的表面重力加速度，这里我们取4.44。这个公式来自于万有引力公式的变换。

Vg=0.635（2)$M$ 表示白矮星的质量， $R$ 表示白矮星的半径。 $V g$ 表示白矮星的引力红移。这个公式来自于Silvestri等人[14]的工作

首先根据白矮星的质量来根据公式（1）计算白矮星的半径，然后根据公式(2)来估计白矮星的引力红移。（图5 的上图显示了这个样本的引力红移和视向速度的分布，可以看出引力红移主要分布在 $1 0 \mathrm { - } 8 0 \mathrm { k m / s }$ 。大部分集中在 $3 0 \mathrm { k m / s }$ 附近。这也和白矮星的质量主要分布在0.6太阳质量一致。

![](images/926dae7cbc0d32e97517dfecdea153457c7e92887e4fdb5f194608cbfb94c48a.jpg)  
图5上图：整个观测样本的白矮星的引力红移和视向速度的关系下图：观测样本中白矮星的视向速度和日心距离的关系，绿色虚线表示视向速度为0的线，紫色矩形框表示某一日心距离范围内的视向速度的平均值及其弥散Figure 5 Top:relation betweenthe gravitationalredshiftandtheradial velocity；Bottom:relationbetweentheradialvelocity and the distance.Rectangles represent the average radial velocity with a distance bin.

# 3.2白矮星的视向速度测量

对于这2000个白矮星样本，我们测量了白矮星的APP速度。APP速度和引力红移之差就是白矮星的视向速度。图4展示了确定白矮星模板光谱的例子。红色虚线为相对于观测光谱（黑色实线）符合最好的模板光谱，这个模板光谱用来做相关来计算白矮星的APP速度。图5的下图展示了白矮星的视向速度和日心距离的关系。我们统计了日心距离在1000pc范围内的视向速度的平均值和弥散。共分为了10个区间，间隔为100pc。矩形框表示每一个区间内视向速度的平均值，误差棒用弥散来表示。可以看出，在日心距离在100pc和1000pc之间，视向速度平均值在0附近。这也证实了以前的对白矮星的视向速度假设为0是合理的。

# 4 结论

基于白矮星参数来选取模板进行匹配来测量DA白矮星的视向速度，对于有效温度高于10000K的DA白矮星，能够得到较准确的视向速度，精度在 $1 0 \mathrm { k m } / s$ 以内。通过对2000多颗高信噪比的白矮星的视向速度分析，我们发现视向速度平均值整体趋向于0，这表明以前的研究在计算白矮星的运动学信息中假设白矮星的速度为0是比较合理的。

# 5 致谢

感谢国家天文台的梁熙龙博士的对这个工作的评论和建议。

# 6 参考文献

[1]Sion,E..;GesteinJ.L;strtJ.D;brt,J;pan,H.L;WegrG..prooedierft classification system.ApJ.1983,269:253-257 [2]York,D.Gdelan,Jnderson,Jr.,JE,etal.eanDiitalSyurvey:chicaumaryJ,():57   
1587 [3] McCook,G.P.,&Sion,E.M.A Catalog of Spectroscopically Identified White Dwarfs.ApJS,1999,121(1): 1-130 [4] Eisenstein,D.J,iebert,J,Haris,H.C,etal.CatalogofSpetroscopicallyConimedWitewarfsfromtheloaniita Sky Survey Data Release 4.ApJS,2006,167(1): 40-58 [5] Kleinman, S.J., Kepler, S. O., Koester,D., et al.SDSS DR7 White Dwarf Catalog.ApJS,2013,204(1): 5-18 [6] Kepler,S.O.,Pelisoli,I.,Koester,D.etal.New white dwarf stars intheSloanDigital Sky SurveyDataRelease 10.MNRAS,   
2015,446(4): 4078-4087 [7]Sion,E.M.,Holberg,J.B,Oswalt,T.D,McCook,G.P.,&Wasatonic,R.The White Dwarfs Within20ParsecsoftheSun: Kinematics and Statistics.AJ,2009,138(6):1681-1689 [8]Pauli,E.-M,Napiwotzki,R.,ltmann,M.,Heber,U.,&Odenkirchen,M.3DinematicsofwhitedwarfsfromtheSproject. A&A,2003,400:877-890 [9]Pauli,E.-M.,Napiwotzki,R.,Heber,U.,ltmann,M.,&Odenkirchen,M.3Dinematicsof whitedwarfs fromtheSproject. II. A&A,2006,447(1): 173-184 [10]Halenka,J.OlchawaW.,Madej,J,Grabowski,B.Presure ShiftandGravitationalRedShiftofBalmerLinesin WhiteDwarfs: Rediscussion.ApJ,2015,808(2):131-140 [11]赵景昆，赵刚，陈玉琴。高分辨率恒星光谱处理与元素丰度分析软件平台。天文研究与技术，2007，4(2):153-158 Zhao Jingkun, Zhao Gang, Chen Yuqin. A software platform for high resolution spectral procesing and elemental abundance analysis.Astronomical Research & Technology,2007, 4(2):153-158 [12] Koester, D. White Dwarf spectra and atmosphere models. MmSAI, 2010. arXiv:0812.0482 [13]王凤飞，罗阿理，张健楠，刘超，赵永恒。统计 SDSS-DR7中的CEMP 星并分析其温度和光谱型。天文研究与技术，   
2009,6(3): 167-174 Wang Fengfei,LuoAli,Zhang Jingnan,Liu Chao,Zhao Yongheng.Temperature and spectral type analysis ofCEMPstars in SDSS-DR7.Astronomical Research & Technology.2009,6(3): 167-174 [14]Silvestri,N,Oswalt,T,& Wood,M.Whitedwarfs incommonpropermotiobinarysystems: masdistributionandetics. AJ,2001,121: 503-516

# Radial Velocity Measurement of the DA White Dwarfs

Yingyue Zhao',Ali Luo² lBeijing Zhongguancun highshool,Beijing086 ²KeyLaboratoryofOpticalAstronomyNationalAstronomicalObervatories,hineAcdemyofciences,Bein

AbstractWhite Dwarfs (WDs) are the final stage for the evolution of the majority of low-and medium-mass stars with initial mass $\mathrm { ~ < ~ } 8 ~ \mathrm { M _ { \odot } }$ .Approximately $7 5 \%$ of all observed WDs are DA type.The spectra of DA white dwarf are dominated with Balmer Hydrogen lines. It is very dificult to measure the APP radial velocity of WDs by the line center because of the wide and asymmetry spectral profile.The kinematics of WDs is very important to distinguish populations of WDs. This paper present a method for APP radial velocity measurement using crosscorelation between the observed spectrum and the template spectrum that has the similar parameters with observed spectrum, which has advantage than linecenter method and the template spectra are from theoretical spectra by Koster et al.The final radial velocityis derived bythe diffrenceofAPP radialvelocityand the gravitational redshift.After test with simulated spectrum, the accuracy will be within $1 0 ~ \mathrm { k m / s }$ for DA white dwarfs with $T _ { \mathrm { e f f } }$ higher than $1 0 0 0 0 \mathrm { ~ K ~ }$ and SNR larger than 20. In addition, the radial velocities of observed DA WDs from SDSS DR7are measured with the above method.The average radial velocities of these close DA white dwarfs(distance $\prec$ 1000 pc) are approaching zero .

Keywordwhite dwarf; radial velocity;template match;