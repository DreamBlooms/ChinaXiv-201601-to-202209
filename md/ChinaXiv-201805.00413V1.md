# 卫星轨道误差对定位精度影响的摄动分析方法

刘成」李芳2\*（1.北京跟踪与通信技术研究所，北京 100094；2.中国科学院国家天文台，北京100012；\*lifang@bao.ac.cn)

摘要：卫星导航系统定位精度受伪距测量误差、大气时延误差、卫星原子钟钟差及卫星轨道误差等多方面因素综合影响。传统通常采用基于精度因子与用户等效伪距误差的方法对定位误差进行评估，但在其精度表征公式推导过程中需对测量方程组系数矩阵 $\pmb { H }$ 及用户等效伪距误差误差分布做若干假设条件，因此它实际上是一个近似评估公式。此外，各类误差源中的卫星轨道误差属于三维误差，需经过坐标转换，并利用经验参数模型才能换算至用户等效伪距误差。为此，提出采用矩阵摄动数学理论研究卫星轨道误差对定位方程组解的影响，利用谱范数条件数对方程组形态进行刻画。仿真结果表明，方法能够直接反映卫星轨道误差对定位精度的影响，无需进行轨道坐标及用户等效伪距误差换算，能够更加直接和准确地评估卫星轨道误差对定位解精度的影响。

关键词：卫星轨道误差；导航定位；用户等效伪距误差；范数；条件数中图分类号：TN961文献标识码:A 文章编号:1672-7673

# 1概述

全球卫星导航系统(GlobalNavigationSatellteSystem,GNSS)定位误差通常由精度因子（Dilutionof Precision，DOP）及用户等效伪距误差（User Equivalent Range Error，UERE）共同刻画，即[1-3]:

对于某一颗给定卫星而言，用户等效伪距误差被视为与该卫星相关联的各个误差源产生的影响的（统计）和，包括伪距测量误差、大气时延误差、卫星原子钟钟差及卫星轨道误差等。

在各全球卫星导航系统建设与发展过程中，上述误差评估方法发挥了重要的作用。它不仅是星座系统设计的重要依据，也是用户进行星座优选及定位精度预测和分析的重要指标根据精度因子参数类型的不同，用户也能够快速地对各不同坐标方向上的未知量以及接收机钟差进行解算精度评估。

然而，出于方便使用的考虑，基于精度因子与用户等效伪距误差的精度表征方法在理论上存在着一些不足。首先，精度因子与用户等效伪距误差的精度表征公式是基于两个假设条件推导得到的：（1）假设观测方程组系数矩阵 ${ \bf \nabla } \cdot { \bf H }$ 无随机分量，这样才能在推导过程中将系数矩阵 ${ \pmb H }$ 移除到期望算子之外；（2）假设所有的UERE均具有相同的均方差，且是互不相关的零均值，这样才能将期望算子简化为。但是，只有当所有观测卫星都成正交分布关系时，观测方程组系数矩阵 ${ \pmb H }$ 才无随机分量，而用户等效伪距误差的构成十分复杂除符合高斯白噪声的随机测量误差外，还有各类大气时延、硬件设备造成的偏差，以及接收端处的多径效应等误差。因此，在实际定位中，这两个假设条件都难以成立。

其次，在各类定位误差源中，伪距测量误差、大气时延误差及卫星原子钟钟差等属于一维矢量，即卫星至用户视线方向上的误差，因而可以轻易地将其换算至用户等效伪距误差中。然而，卫星轨道误差（一般认为是卫星广播星历误差）属于三维方向上的误差量，难以直接换算至用户等效伪距误差。为此，为评估卫星轨道误差对定位精度的影响，一般需将卫星广播星历误差从地心地固坐标系（Earth-Centered EarthFixed，ECEF）转换至该时刻的轨道坐标系（RTN坐标系）下，得到卫星轨道位置在径向（R）、横向（T）和法向（N）上的偏差[48]。在此基础上，认为径向方向轨道误差对用户定位精度的影响最大，再利用相关经验模型与参数计算得到卫星URE值，并纳入用户等效伪距误差中进行综合考量[9-10]。对于我国北斗卫星导航系统（BeidouNavigationSateliteSystem，BDS）等由混合星座构成的全球卫星导航系统而言，还需要对MEO、GEO及IGSO等不同轨道类型的卫星采用不同的经验参数，这增加了精度分析与评估过程的困难和繁琐性。

为此，本文提出采用矩阵摄动数学理论研究和分析卫星轨道误差对定位观测方程组解的影响，并利用基于谱范数的条件数对测量方程组的形态进行刻画（实际上，精度因子的数学本质也即为矩阵范数中的Frobenius 范数）。仿真计算结果表明，基于矩阵摄动理论能够直接反映卫星轨道误差对定位精度的影响，无需进行等效伪距误差转换，从而能够更加直接和准确地研究定位方程组性能及其解的误差，以及卫星轨道误差对定位解精度的影响。

# 2观测方程与误差方程

全球卫星导航系统单点定位解的线性方程组矩阵形式可表示为

其中， $\pmb { H }$ 为方向余弦矩阵：

其中，，和分别为用户估计位置指向第i颗卫星的单位矢量方向余弦。

为近似解与真解之间的改正向量：

为由用户估计位置和钟差估计值计算得到的几何距离与观测伪距之差：

当 $\scriptstyle \mathrm { n = 4 }$ 时，(2)式为正定方程。其解为：

当 $\mathrm { \tt n { > } } 4$ 时，(2)式为超定方程。采用最小二乘法获得其冗余解：

根据文[1-3]中对最小二乘解算值协方差矩阵的推导，可得用户坐标位置误差的协方差为

其中， $E$ 为期望算子；为用户位置误差均方差；为伪距观测误差向量； $n$ 为观测卫星数量。在上述推导过程中，曾假设系统矩阵 ${ \pmb H }$ 无随机分量，因此可被移到期望算子之外。再进一步假设所有的用户等效伪距误差均有相同的方差，且是互不相关的零均值，则(8)式中的期望算子可简化为

其中， $\boldsymbol { \mathit { I } }$ 为 $4 { \times } 4$ 的单位矩阵。于是，(8)式中的两个方程可简化为其中，为用户等效伪距误差换算至用户位置误差时的误差放大因子精度因子，它与用户至卫星的单位矢量所勾勒的立体体积成反比。

根据用户所在坐标参考系的不同，精度因子可以表征不同方向上的位置误差。当用户位于用户等效伪距误差坐标系时，其实际含义为

其对角线元素的平方根分别对应三维方向坐标位置及接收机钟差的误差放大因子精度因子。

由于在精度因子的推导过程中，曾假设系数矩阵 ${ \pmb H }$ 无随机分量，所以(11)式中矩阵的协方差阵也被认为是零值。由此可以发现，精度因子的定义与矩阵范数中的Frobenius 范数（即F-范数，矩阵中各元素平方和的平方根）一致，其数学本质即为矩阵F-范数。这也说明，可以利用矩阵范数摄动理论进一步开展对测量方程组定位误差解的深入研究。

# 3轨道误差摄动分析方法

从以上误差方程推导可知，基于精度因子的分析方法对测量值的误差统计情况及系数矩阵 $\pmb { H }$ 的随机分量情况均做了条件假设（假设测量值误差均符合高斯分布且相互独立、系统矩阵 $\pmb { H }$ 无随机分量）。而在实际情况下，卫星导航定位的过程很难符合上述理想条件。相较之下，基于范数概念的摄动分析理论可对测量方程组的实际形态进行研究，并对卫星轨道误差的影响程度进行更加直接和真实的评估。

当考察卫星轨道误差对定位解的影响时，认为对方程组左端系数矩阵 ${ \pmb H }$ 带来摄动误差并给坐标及钟差未知数向量造成摄动。即有

可以证明，由于矩阵 $\pmb { H }$ 非奇异，而由卫星轨位误差等造成的摄动误差甚小，故矩阵仍然可以保持它的非奇异性[12]。因此，将(12)式减去(2)式可得：

从而，对(12)式左右两端进行范数表达可得：

进一步地有

这里，是误差放大率，即解的相对误差为测量数据相对误差的倍。又称为矩阵的条件数，记为

因此，(15)式可记为

由于相对而言一般已经充分小，因此(17)式通常可以近似为这说明当 $\pmb { H }$ 具有扰动时，引起的解的相对误差不超过 $\pmb { H }$ 的相对误差的[11-14]。

从上述分析可以看出，当方程组中的 $\pmb { H }$ 具有扰动误差时，方程组解的误差可以由条件数决定，其作用可视为误差传递的放大因子，起到类似于精度因子的作用。条件数与所取的矩阵范数有关，数学上一般采用谱范数（即2-范数）进行表征：

此时，又称为矩阵的谱条件数[11-12,14]。

条件数同时刻画了方程组的形态，反映了方程组解对误差的敏感程度。当相对较大时，称测量方程组为病态方程；当相对较小时，则可称为良态方程。

# 4仿真实验与分析

为分析和验证基于范数的摄动分析方法的可行性，采用了实测与仿真相结合的方法。首先，利用全球卫星导航系统接收机在某一已知坐标的固定位置测量了一段历元时长的全球定位系统卫星轨道坐标数据，并且为了便于分离和控制误差，仿真生成了对应的全球定位系统伪距数据，其中含有 $1 \sigma { = } 3 \mathrm { m }$ 的伪距误差。其次，为考察卫星轨道误差对定位精度的影响，在卫星位置的 $X$ 、Y、 $Z$ 三维坐标方向上又分别生成和添加了 $1 \sigma { = } 3 \mathrm { m }$ 的轨道坐标均方误差（因此轨道的三维误差为 $1 \sigma { = } 5 . 1 9 6 \mathrm { m }$ ）。通过计算添加轨道误差前后的定位结果，得到由卫星轨道误差造成的实际解算误差，并与基于范数的摄动分析方法估计得到的误差进行对比，结果如图1。

30 实际误差  
25 估计误差  
20 实际误差-估计误差  
1510505  
-5 WMmwwwwAwMmWwwmm  
-10  
-15  
30 0 100 200 300实际误养  
1050  
-5 mwm  
-10300 400 500 600历元（秒）

可以看出，基于矩阵范数摄动分析理论，能够不依赖误差分布假设条件、不通过轨道坐标分解与转换，直接评估和分析卫星轨道误差对全球卫星导航系统定位解的影响。并且，由范数摄动分析方法计算得到的误差上限均恰好位于实际解算误差之上，两者吻合情况良好（之间差异保持在数米以内），说明范数摄动分析方法能够准确、可靠地对全球卫星导航系统定位解算误差情况进行刻画和评估。

# 5总结

基于精度因子与用户等效伪距误差的精度表征方法在星座优选、定位精度预测与分析等方面发挥了重要作用。但是，精度因子与用户等效伪距误差的精度表征公式基于若干假设条件推导得到，因此严格意义上只能作为近似评估手段，在理论上仍欠严谨。同时，将所有定位误差源折算至用户等效伪距误差概念中进行评估，也为卫星轨道误差对用户定位精度影响的评估工作带来了一定的困难，增加了评估过程的繁琐性。

本文提出基于范数数学概念，采用矩阵摄动分析方法对卫星轨道误差影响进行研究，提供了一种新的理论和实用方法，以丰富和弥补传统以来基于精度因子与用户等效伪距误差的精度表征方法。当已知卫星轨道误差先验统计信息时，即可利用方法对卫星轨道误差影响程度进行预测和评估，或在利用事后精密星历计算得到真实卫星轨道误差后，对卫星系统星座性能进行更加准确和便捷的分析。该方法能够避免对测量值误差统计情况及观测方程组系数矩阵随机分量情况的条件假设，无需进行卫星轨道误差的解析与坐标转换，并且不依赖统计意义，能够对单次定位解的误差摄动进行细致描述。因此，能够更加全面和直接地评估与分析卫星轨道误差对用户定位精度的影响。仿真实验与分析表明，基于矩阵范数的摄动分析方法计算过程简洁，评估结果准确可靠，具有理论意义与应用价值。

# 奓兮乂

[1]Misra P, Enge P. Global Positioning System - signals,measurements, and performance[M]. Lincoln: Ganga - Jamuna Press, 2001.   
[2] Parkinson B W, Spilker J J,Axelrad P, et al. Global Positioning System: theory and applications[M]. Washington: American Institute of Aeronautics and Astronautics, 1996.   
[3]谢钢.GPS原理与接收机设计[M].北京:电子工业出版社,2009. [4]施闯,赵齐乐,李敏,等.北斗卫星导航系统的精密定轨与定位研究 [J].中国科学:地球科学,2012,42(6):854-861.   
Shi Chuang, Zhao Qile,Li Min, et al. Precise orbit determination of Beidou Satelites with precise positioning[J]. Scientia Sinica: Terrae, 2012, 42(6):854-861.   
[5]刘伟平,郝金明,李建文,等.一种北斗卫星精密定轨方法[J].测绘 科学技术学报,2013,30(3):247-250.   
Liu Weiping,Hao Jinming,Li Jianwen ,et al. A method of precise orbit determination of BeiDou navigation satellite[J]. Journal of Geomatics Science and Technology, 2013, 30(3): 247-250. [6]李征航,丁文武,李昭.GPS广播星历的轨道误差分析[J].大地测量 与地球动力学,2008,28(1):50-54.   
Li Zhenghang,Ding Wenwu,Li Zhao.Error analysis of orbit determined by GPS broadcast ephemeris[J]. Journal of Geodesy and Geodynamics, 2008,28(1): 50-54.   
[7]李济生.人造卫星精密轨道确定[M].北京:解放军出版社,1995. [8]徐小钧,艾国祥,马利华,等.基于不同轨道高度iHCO通信卫星的 CAPS 星座优化研究[J].天文研究与技术一国家天文台台刊,2014,11(4): 350-355.   
Xu Xiaojun, Ai Guoxiang,Ma Lihua, et al. A study of optimization of a CAPS constellation of iHCO communication satellites of different orbit heights[Jj. Astronomical Research & Technology —Publications of National Astronomical Observatories of China,2014,11(4): 350-355.   
[9]高为广，苏牡丹,郭树人，等.北斗系统空间信号精度测试与评估 [C]//第四届中国卫星导航学术年会电子文集.2014.   
[10]罗璠,李建文,黄海,等.BDS广播星历的轨道误差分析[C]//第五 届中国卫星导航学术年会电子文集.2015.   
[11]何旭初,苏煜城,包雪松.计算数学简明教程[M].北京：人民教育

出版社,1980.

[12]数学手册编写组.数学手册[M].北京:高等教育出版,1979]  
[13]施浒立,孙希延,李志刚.转发式卫星导航原理[M].北京:科学出版社,2009.  
[14]王世儒,王金金,冯有前,等.计算方法[M].西安:西安电子科技大学出版社，2004.

# Studyon Perturbation Analysis Method of the Influence of Satellite Orbit Error on Positioning Accuracy

Liu Cheng', Li Fang² (1.Beijing Institute of Tracking and Telecommunication Technology, Beijing 100094; 2.National Astronomical Observatories, Chinese Academy of Sciences, Beijing 100190)

Abstract: GNSS positioning accuracy is affected by pseudo-range measuring error, atmospheric time-delay error, satellite atomic clock error and satellite orbit eror, et al. Traditionally, the DOP and UERE parameters are used to estimate positioning error. However, several assumptions are needed to make in the derivation process of precision representation formula, thus it is actualy an approximate estimate formula. In addition, the satelite orbit error of various error sources belongs to three-dimensional error, which requires coordinate transformation and experience parameter model to switch to UERE. Therefore， the paper proposes using matrix perturbation mathematicaltheory to study the influence of satellite orbit error on positioning accuracy; and describes equation form by conditional number using spectral norm. The simulation result demonstrates that this method can reflect the influence directly without transformation of orbit coordinate and UERE error so that it is more direct and precise to assess the influence of satellite orbit error on positioning accuracy.

Keywords: Satelite Orbit Error; Navigation and Positioning; UERE; Norm; Condition Number