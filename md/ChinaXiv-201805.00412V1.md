# 广义延拓法在GPS精密星历内插和外推中的应用

陈强强1,²，陈志平1，李芳²(1.杭州电子科技大学机械工程学院，浙江 杭州 310018;2.中国科学院国家天文台，北京 100012)

摘要：利用精密星历解算卫星坐标是实现GPS高精度差分定位的首要基础，受限于GPS精密星历的采样时间间隔，为了得到任意时刻的卫星坐标，需要对全球定位系统精密星历数据做内插和外推处理。分析卫星位置随时间变化的规律后，采用广义延拓法对卫星的一段轨道构造以时间为坐标的内插和外推模型，在不引入较大位置误差的同时简化了卫星坐标的计算过程，并与拉格朗日插值法进行对比实验。研究结果表明，利用广义延拓法内插时误差小于5cm，且在外推30min内仍然能维持精度，明显优于拉格朗日插值法。

关键词：精密星历；插值；外推；广义延拓；全球卫星定位系统中图分类号：P228.1 文献标识码：A 文章编号：1672-7673 (2018)

国际GNSS 服务中心（International GNSS Service，IGS）提供的精密星历通常用于全球定位系统精密单点定位等数据处理中，但国际GNSS服务中心发布的精密星历采样间隔是15min，而在全球定位系统精密定位中接收机的采样率一般远小于这个值，因此，需要对精密星历进行高精度的插值。另一方面，由于国际GNSS服务中心精密星历仅提供当天00：00：00\~23：45：00时间段的星历数据，若想仅用当天的数据得到23：45：00\~24：00：00时间段的星历数据，还需要进行外推以获得任意时刻的卫星坐标。

要使插值定位结果平滑、稳定，要求插值多项式及其导数连续和平滑，较为常见的插值方法有Chebyshev多项式插值法、Newton多项式插值法和Lagrange 插值法等[1-3]。在目前的数据处理中，Lagrange插值应用较广，文[4]指出Lagrange插值法在本质上与Neville插值法相同；文[5]将Lagrange插值法改进，利用滑动式Lagrange插值法获得全球定位系统精密星历；文[6]对比了Lagrange和Newton插值法的内插效果，对插值结果进行了总结分析。上述研究中，多种插值方法在一定时段内需要进行高低阶组合才能达到最优效果，且外推效果普遍不很理想。由于广义延拓逼近法构造的插值函数在所有同阶插值函数中具有最小平方逼近误差，为此，本文将基于广义延拓原理对全球定位系统精密星历进行插值外推，利用求得的逼近函数解算任意时刻的全球定位系统卫星的精密坐标。

# 1广义延拓内插及外推模型

广义延拓逼近法在分片边界点上满足插值条件，使分片间变化协调，并充分利用分片插值区域的周围结点信息，实现分片区域内部的最佳拟合，有机结合插值法和拟合法的优点，在数据处理时实现了高精度的逼近[7-9]。

首先在整域内进行剖分处理，以便在单元域内寻找逼近函数及基函数，将定义域剖分成个互不重叠的子域：

，

单元域有个结点，对应结点坐标为，结点坐标满足定义域。现将单元域延 拓至，成为延拓域，结点坐标,满足延拓域为，如图1。

![](images/0e2067ba2a8062881674e3801f2c69e973299ce6380ddf316395262dc572d8ab.jpg)  
图1延拓域及相应函数值 Fig.1 Extension domains and their corresponding function values

设延拓域内有个节点（），利用含有较多结点的延拓域构造单元域内逼近函数:

，

其中，为上的一组基函数；为待定系数；为逼近函数项数，且。在求解函数的待定系数时，将的适用范围由单元域扩大至延拓域。则在延拓域建立如（3）式的广义延拓逼近内插模型，为先验信息采样点，为逼近函数与先验值的误差：

广义延拓逼近方法将单元域嵌套在延拓域中，吸收单元域外延拓域中的结点信息构造单元域内的拟合逼近函数，同时约束单元域边界结点，实现相邻单元逼近函数的协调和连续，从而达到单元域内逼近函数的最佳拟合效果。利用广义延拓构造的逼近函数即可对目标变量进行插值处理。

广义延拓插值模型不但可以用作内插模型，也可以作为外推模型用于外延应用的场合。对一组不断增长的数据序列，，已知以前的数据值，根据先验数据的变化规律和趋势，欲求时刻的值，数据外推示意图如图2。

![](images/217216d11d5e8bac1c21b0d9a1d275796aeadf96c6db2ba2b85dba4971ad71ee.jpg)  
图2数据外推示意图Fig.2 Data extrapolation intent

按照广义延拓插值外推的设计理念，令为最新时刻，采用外推算法可得下 一时刻的值。建立广义延拓外推模型：

在上述模型中，由于插值点为最新采样点的值，为了克服这一点数值突变带来的误差，考虑建立改进的广义延拓模型：

即选择最新的个采样点的平均值作为约束，改进模型的解法与原模型的解法基本一致，但数据的平稳性更好，插值拟合曲线更平滑，外推精度更高。

# 2 全球定位系统精密星历的内插和外推方法

2.1全球定位系统精密星历的解算方法

考虑卫星的实际运行轨道会偏离无摄运行轨道，因此全球定位系统的星历参数通常采用一套扩展后的开普勒轨道参数，由16个参数组成，包括6个开普勒根数，9个摄动参数和星历参考时间。

由文献[10]提供的解算算法，可将卫星定位计算过程简要描述如下：(6)其中，，，为每个历元待求的卫星坐标。经过坐标变换和摄动校正，最终得到t时刻该卫星在WGS-84地心地固坐标系中的坐标计算矩阵：(7)其中，为信号发射时刻卫星在轨道平面的位置坐标；为信号发射时刻的升交点赤经；为轨道倾角，均可由星历参数计算求得。

由以上求解过程可知，利用星历参数计算全球定位系统卫星在某一时刻的空间位置必须提供准确的星历数据，每定位一次需要的计算量也挺大。

2.2全球定位系统精密星历的插值可行性分析

图3中的三条曲线分别是某颗卫星的位置在WGS-84地心地固坐标系中的X,Y和Z分量随时间的变化情况，历元间隔为15min，可见卫星的轨道位置呈周期性变化。如图4，卫星位置的各分量在一段短时间内随时间变化平滑，几乎呈线性变化。

![](images/f37ae2e9c51b77ef5b463d8688b33496b16763691ac33a7b7821858f812cb289.jpg)  
图3长时间内卫星的空间位置

![](images/7e7e8c2aeaba03d8d86190ba86efbf9fee523562601f20cec8ae0002f92b4fc4.jpg)  
图4短时间内卫星的空间位置

Fig.3 Space position of satellite over a long period of time Fig.4 Space position of satellite in short time

因此，卫星的一段轨道可以用一个以时间域上的插值多项式表达[11]，如果此逼近函数构造得当，那么这种插值方法不会引入很大的卫星位置误差，可避免2.1节所述的复杂计算方法，使计算量大幅度减少。

2.3基于广义延拓的全球定位系统精密星历内插和外推方法

利用广义延拓插值原理，对卫星位置与速度在WGS-84地心地固坐标系中的X，Y，Z分量分别分段建立广义延拓模型，在到这段时间内，以卫星位置在 $\chi$ 方向上的分量为例，若在区间内取两端点作为先验点进行约束，则广义延拓插值模型为

，

其中，表示在插值区间左端点时刻卫星位置在WGS-84地心地固坐标系中 $\chi$ 方向上的分量；表示在插值区间右端点时刻卫星位置在WGS-84地心地固坐标系中 $\chi$ 方向上的分量；为待求系数；是精密星历更新的时间点。

对上述模型展开求解，即由得到法方程，（9）式中，为拉格朗日乘子，其中

且，，解上述法方程，求得系数后，可得卫星位置在×方向上的分量随时间变化的广义延拓内插函数，将所需时刻时间代入，即可快速求解。

接着，由（5）式构造广义延拓外推模型：

，

其中，变量含义见（8）式，其中表示选用了最新个卫星位置的 $\chi$ 分量，取平均值作为外推模型约束。对此模型的解法如下：

可得系数求解矩阵：

其中：

解得待求系数后，便可得到外推公式：

同理可得卫星位置在其余各分量上的外推公式。

# 3算例分析

现验证广义延拓插值外推模型的推算效果，采用IGS 提供的2017年6月6日（即GPS1952周）采样时间间隔为15min的精密星历数据，选用的卫星为PRN15号。选取前4个采样数据作为先验采样点，以Lagrange插值法作为参照，并与精密星历数据拟合的标准曲线对比。得到两种精密星历插值法的逼近效果如图5。

![](images/a8f8a0e1df4fd71f51c4b5b6de5cbb6a86ac8dd898ec2f9329b887e9aeacbacb.jpg)  
图5两种精密星历插值法的插值外推效果对比

由图5可见，当以1小时的精密星历作为先验点进行拟合逼近函数时，在1.5小时的时段内，Lagrange插值法和广义延拓法构造的逼近函数与精密星历的拟合曲线基本吻合，而在1.5小时以后，广义延拓法的外推效果明显好于Lagrange插值法。为了更直观得观察广义延拓法构造的模型精度，将X、Y、Z各分量的误差整合为位置误差e，，得到位置误差随时间变化如图6。

![](images/17d5c03f3860ef918cd3ee97e86a2b23316216ad31da6e82ce124acc9e7093e4.jpg)  
图6卫星位置随时间变化图  
Fig.6 Chart of satellite position versus time

由图6可知，前4个比对点拟合的曲线为广义延拓内插效果，其插值的卫星位置误差小于5cm，自第5个比对点开始为广义延拓的外推效果，可见广义延拓外推1小时左右的卫星位置误差小于 $1 0 \ \mathsf { c m }$ ，外推2小时的卫星位置误差小于20cm，而在外推2小时以后，卫星位置误差开始迅速变大。

由于IGS提供的精密星历误差精度为5cm，因此，利用广义延拓法对全球定位系统精密星历的内插能够满足精度要求，而在利用广义延拓外推时，在30min内也能维持精度，在较长时间内也不会引入很大的位置误差。

# 4结论

采用广义延拓法对全球定位系统精密星历进行卫星位置内插时效果较好，可以将卫星的一段轨道用一个以时间为坐标的模型表达，使得计算卫星位置时在不损失精度的情况下，不再进行复杂冗长的步骤，极大程度减少了计算量。此外，通过实例分析，广义延拓外推法能够保证外推1小时的精度能满足要求，广义延拓内插法可获得全球定位系统任一时刻的精密星历数据。

参考文献

[1］李征航，黄劲松．GPS 测量与数据处理[M].武汉：武汉大学出版社，2005.[2]孙腾科.基于拉格朗日与切比雪夫的精密星历插值研究[J].测绘与空间地理信息，2014，37（2）：33-37.Sun Tengke. The research of GPS precise interpolation methodsbased on Lagrange and Chebyshev[J]. Geomatics & SpatialInformation Technology，2014，37（2）:33-37.  
[3] 汪威，陈明剑，闫建巧，等.北斗三类卫星精密星历内插方法比较分析[J].全球定位系统，2016，41（2）：60-65.Wang Wei， Chen Mingjian， Yan Jianqiao， et al. Three kinds ofcompass satellite precise ephemeris interpolation method analysiscomparative[J].GNSS World of China，2016，41 （2） : 60-65.  
[4]王超，郭际明，周命端，等.高精度GPS数据处理中GAMIT批处理方法与实现[J].测绘信息与工程，2012，37（2）：10-12.Wang Chao， Guo Jiming， Zhou mingduan ， et al． A method ofGAMIT batch processing and its implementation in high precise GPSdata processing[J].Journal of Geomatics，2012，37 （2） : 10-12.  
[5]雷雨，赵丹宁，高玉萍．基于滑动式Lagrange插值方法的GPS 精密星历内插分析[J].测绘工程，2013，22（2）：34-36.Lei Yu， Zhao Danning， Gao Yuping. Analysis of interpolation forGPS precise ephemeris using sleek Lagrangeinterpolation[J].Engineering of Surveying andMapping，2013，22（2）：34-36.  
[6]柳笛，逢淑涛，董绪荣．IGS 精密星历文件的读取及内插方法研究[J].全球定位系统，2011，36（5）： $4 6 { - } 4 8 { + } 6 4$ Liu Di， Pang Shutao，Dong Xurong. Read of precise ephemeris fileand research on methods ofinterpolation[J]. GNSS World ofChina，2011，36（5）： $4 6 { - } 4 8 { + } 6 4$   
[7]施浒立，颜毅华，徐国华，等.工程科学中的广义延拓逼近发[M].北京：科学出版社，2005.  
[8] 魏彦飞，耿建平，施浒立，等．一种新的数据融合方法一广义融合法[J].天文研究与技术，2016,13(3)：318-325Wei Yanfei， Geng Jianping， Shi Huli，et al. A new method of datafusion—the generalized fusion method[J]. Astronomical Research &Technology， 2016，13(3): 318-325.  
[9］耿建平，衣伟，刘成，等．基于广义延拓外推的单频周跳检测与修复方法[J]．天文研究与技术，2015，12(2)：174-182Geng Jianping， Yi Wei ， Liu Cheng， et al. A new method fordetection and correction of single-frequency cycle slips usingdata extrapolation based on the method of generalized extendedinterpolation[J].AstronomicalResearch &Technology， 2015,12(2): 174-182.  
[10] Jiang R B，Liu X Q.Using fourier series to fit the GPS precise ephemeris[C]// 2010International Conference on Computer Application and System Modeling (ICCASM 2010),2010:96-99.  
[11] Liu W P， Hao J M. A new interpolation method based on satellite

physical character in using IGS precise ephemeris[J]. Geodesy and Geodynamics，2014,5(3) : 29-33.

# Application of Generalized Continuation Method in Iterpolation and Extrapolation of GPS Precise Ephemeris

Chen Qiangqiang1², Chen Zhiping', Shi Huli²,Li Fang²   
(1.School of Mechanical Engineering, Hangzhou Dianzi University, Hangzhou 310018, China;   
2.National Astronomical Observatories， Chinese Academy of Science， Beijing

# 100012，China)

Abstract: The use of precise ephemeris to solve satellite coordinates is the primary basis for high precision differential positioning of GPS, in order to obtain satelite coordinates at any time since the GPS precise ephemeris has limit of the sampling interval, it is necessary to interpolate and extrapolate GPS precise ephemeris data. After analyzing the law of satellite position changing with time,the interpolation and extrapolation model which is relat to time is built by generalized extension method,and it is used to describe a section of satellite orbit, the calculation process of satelite coordinate is simplified without introducing larger position error through this method, then compared with the Lagrange interpolation method in experiment. The result shows that the error of interpolate when using generalized extension method is less than 5cm, and maintain the accuracy of extrapolation in 3O minutes, significantly beter than the Lagrange interpolation method.

Key words: Precise ephemeris;interpolation;extrapolation； Generalizedextension; GPS