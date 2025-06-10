# 基于紫外辐射传输模型AURIC-2012的气辉 辐射模拟

王后茂①②\*，王咏梅$\textcircled{1}$ 中国科学院国家空间科学中心，北京100190;$\textcircled{2}$ 中国科学院大学地球科学学院，北京100049\* E-mail: hmwang@ nssc.ac.cn

收稿日期:2015-02-08；接受日期:2015-04-13；网络版发表日期:2015-11-02中国科学院空间科学战略性先导科技专项项目(编号：XDA04060202)资助摘要AURIC是由美国计算物理公司CPI与空军Phillips 实验室联合开发的中高层大气紫外-可见光-近红外气辉辐射传输模型，是目前唯一用来进行中高层大气气辉辐射模拟研究的通用模型.基于MODTRAN模型的理论，AURIC可以进行 $8 0 \mathrm { k m }$ 高度以上的辐射传输模拟并将辐射波段扩展到远紫外波段 $\langle 8 0 \ \mathrm { n m } \rangle$ ．目前，CPI公司只面向全球发布了AURICv1.2软件封装包，其只能进行 2000年以前的单点计算，不适用于批量的中高层大气辐射模拟，更不能用于星上大气成分的批量反演．本文利用Matlab对AURICv1.2地磁参数模块、大气电子密度模块、大气温度及各种中性气体成分密度模块进行了替代，将更新模块与原有的辐射计算模块相结合，将AURICv1.2更新为AURIC-2012模型，其可以批量地进行全球的大气辐射传输模拟，可以与星载测量数据相结合进行中高层大气成分的批量反演，如 $\mathrm { O } / \mathrm { N } _ { 2 }$ 、电子密度等，同时也为模型辐射计算模块的进一步改进和辐射机制的参数更新奠定基础．基于AURIC-2012模型，进行了气辉临边柱辐射强度模拟和体辐射率计算，并将结果分别与GUVI柱辐射强度和 TIDI体辐射率实测值进行了比较，得到两者峰值的模拟平均相对误差都小于 $20 \%$ 最后，利用AURIC-2012对气辉临边柱辐射强度随纬度和高度的分布进行了二维模拟，并基于模拟对昼、夜气辉辐射强度分布特性及影响因素进行了分析.

关键词 AURIC-2012 气辉模拟 柱辐射强度 体辐射率

气辉是中高层大气一种重要的自然发光现象,其主要是由太阳紫外辐射直接或间接激发大气分子或原子而产生的．气辉主要分布在 $8 0 ~ \mathrm { k m }$ 以上高度,覆盖了所有纬度范围，并且昼夜一直存在.按照发生的时间，气辉可以分为昼气辉、夜气辉和曙幕气辉;按照辐射谱线可以分为紫外气辉、可见光气辉和近红外气辉．在各种谱线气辉中，不同的气辉分布高度不同，辐射强度也不同；而同一谱线气辉辐射强度随地理位置和时间也在不断的变化，强度的变化与大气的化学过程和动力学过程存在着密切的关系，这表明气辉是反应这些物理过程和物理参数的媒介，因而被誉为中高层大气的“指纹”．因此，利用模型对气辉辐射的模拟计算，有助于深入了解气辉的辐射特性，并对了解电离层的化学、动力学及热力学等过程提供参考数据．同时，利用模型与气辉的星载测量值相结合，还可以对电离层大气成分进行反演(如 $\mathrm { O } / \mathrm { N } _ { 2 }$ 电子密度等)，为科学研究和军事活动等提供观测数据.

目前，国际上针对中高层大气的气辉辐射模拟一般只基于一种或者两种气辉进行它们的体辐射率或强度的模拟(Solomon和Abreu，1989；Richards和Torre,1988;Richards等,1994;Murtagh和Donal,1989;Murtagh等，1990;Witasse等，1999;Estes,2000；江芳等,2014)，而综合起来进行中高层大气气辉辐射传输模拟的通用模型只有大气紫外辐射模型AURIC(Atmospheric Ultraviolet Radiance Integrated Code).该模型是由美国计算物理公司CPI（ComputationalPhysics,Inc.)和空军Phillips实验室经过十多年的研究于2002年联合发布的，以用于中高层大气辐射传输模拟(Link等，1992；Strickland等，1999；Evans等,2002).1999年,Strickland等第一次利用AURIC模型进行气辉辐射强度、体辐射等的计算模拟，并将模拟结果与火箭、卫星等实测数据进行了对比分析．之后，AURIC模型逐渐的被应用于大气成分的反演等方面.

Bishop等(2003)对AURICv1.0极紫外波段范围进行了进一步扩展，并基于该模型对霍普金斯紫外望远镜(HUT)观测的极紫外数据进行了分析；Stephan等(2004)利用AURIC对赤道地区热层磁暴时紫外辐射情况进行了研究；Strickland等(2004)利用AURIC建立的查找表得到了 $\mathrm { O } / \mathrm { N } _ { 2 }$ 与 $1 3 5 . 6 / \mathrm { L B H _ { S } }$ 的关系，并结合GUVI数据进行全球热层 $\mathrm { O } / \mathrm { N } _ { 2 }$ 的季节变化分析；Bobik等(2013)利用AURIC对 $3 0 0 { \sim } 4 0 0 \ \mathrm { n m }$ 的夜气辉辐射率进行计算，并用于南大西洋异常区的紫外辐射背景研究；Evans等(2013)结合火星大气的气体成分及数据对AURIC模型进行了更改，以用于对火星大气辐射的研究．在国内，近几年学者基于AURIC也进行了一些研究，彭圣峰等(2012)利用AURIC模型对$1 3 5 . 6 ~ \mathrm { n m }$ 和LBH昼气辉进行了模拟研究，并将其用于热层 $\mathrm { O } / \mathrm { N } _ { 2 }$ 计算；张永超等(2014)基于AURIC模型进行了LBH计算方法的改进，引入了观测方位角，并考虑了大视场下太阳天顶角变化对结果的影响！

目前，由于很难获得AURICv1.2的源代码，绝大部分研究一般仍基于CPI发布的AURICv1.2软件包进行的．而AURICv1.2只是一个软件封装包，这使得其只能进行单点计算，不能进行批量模拟，且不能用于星载大气成分的批量数据反演．此外，AURICv1.2电子密度计算是基于FAIM模型，而中性气体密度和温度计算基于NRLMSISE-OO和SHARC模型，都是基于2000年及以前的数据库．因此，本文利用国际参考电离层模型IRI-2012电子密度计算模块和DTM-2013大气温度、中性气体密度计算模块对AURICv1.2进行了模块更新，并基于Matlab将其集成为AURIC-2012程序包，可循环进行全球任意时间的气辉辐射模拟，并可用于中高层大气成分的星载反演.

# 1原理与方法

在AURICv1.2中，昼气辉计算模型主要有14个模块，分别为地磁参数GEOPARM、大气模式模块ATMOS、电离层模式模块IONOS、太阳光谱模块SOLAR、倾角柱密度计算模块COLDEN、光电子源模块PESOURCE、光电子通量模块PEFLUX、电子碰撞模块E-IMPACT、化学反应模块DAYCHEM、多元汇合模块MERGEVER、观测视线柱密度计算模块LOSDEN、辐射传输模块RADTRANS、柱辐射率计算模块LOSINT和柱辐射率结果存储模块MERGEINT．夜气辉计算模型则主要有8个模块，分别为地磁参数GEOPARM、大气模式模块ATMOS、电离层模式模块IONOS、夜气辉辐射计算模块NITEGLO、观测视线柱密度计算模块LOSDEN、辐射传输模块RADTRANS、柱辐射率计算模块LOSINT和柱辐射率结果存储模块MERGEINT.这些模块封装在同一个bat执行文件中，每个模块承担一种计算功能，模块之间通过参数或者文件相互连接，因此AURIC可以依次调用不同的计算模块来分别进行昼气辉和夜气辉的模拟计算.

由于AURICv1.2只能进行单点的气辉模拟，不适用于大量数据的仿真模拟及星上大气成分反演，因此，本文对地磁参数GEOPARM模块、电离层IONOS模块及大气ATMOS模块进行了更新替代，改进内容及步骤如图1所示，

![](images/d3794b5f2324056f00309832509858b2747b9fbdddd36b0eb733add485f0f417.jpg)  
图1AURIC-2012改进内容及步骤

图1中，改进1为AURICv1.2中GEOPARM模块参数的更新替代，主要包括地磁经纬度、磁倾角、太阳天顶角、当地时间、太阳指数 $\mathrm { F } _ { 1 0 . 7 }$ 及地磁指数Ap这些参数只更新到1999年12月31日，这使得AURIC不适用于目前观测数据的应用．因此本次更新对这些参数进行了重新计算和模块代替．其中，磁倾角是由国际地磁参考模型(Finlay等，2010)计算得到的；太阳天顶角的计算是基于Reda等(2004)提出的太阳位置算法；太阳 $\mathrm { F } _ { 1 0 . 7 }$ 指数和地磁Ap指数的计算则是基于NOAA提供的实 测数据库(ftp://ftp.ngdc.noaa.gov/STP/GEOMAGNETIC_DATA/INDICES/KP_AP).

改进2为大气温度和中性气体密度廓线的计算，AURICv1.2中ATMOS模块的计算是基于2000年以前的数据库进行的，这不适用于目前的气辉模拟和大气成分星上反演．因此本次更新基于DTM-2013模型进行大气温度和中性气体密度的计算，并将其作为AURIC-2012中ATMOS的更新模块.DTM模型是基于卫星实测数据的半经验模型，主要用于大气温度和中性气体密度的模拟计算，其中中性气体主要包括H, He, O, $\mathbf O _ { 2 } \mathfrak { F } \mathbb { I } \mathbf N _ { 2 }$ ．目前，DTM模型先后经历了6个升级版本，其是由Barlier等(1978)利用从卫星电力数据反演的热层大气温度和密度数据首次开发的，之后经过DTM-1994，DTM-2000，DTM-2009，DTM-2012及DTM-2013版本(Berger等，1998；Bruinsma等，2003,2004，2012)．因此，本文利用其最新的版本DTM-2013代替AURICv1.2的ATMOS模块进行温度和中性气体密度的计算，从而实现ATMOS模块的更新.

改进3为电子密度廓线的计算．AURICv1.2中IONOS模块的计算模拟是基于1989年以前的实测电子密度数据库进行的，这不适用于现在的气辉模拟和大气成分星上反演．因此本次更新是利用国际参考电离层IRI-2012代替原IONOS模块进行电子密度的计算，并将其作为AURIC-2012的IONOS模块．IRI模型是在20世纪60年代由空间研究委员会(COSPAR)和国际无线电科学联盟(URSI)共同发起建立的电离层模型，其是基于世界范围内实测数据的经验预报模型．它综合了全球180多个电离层探测站的资料,主要描述了海拔高度 $5 0 { \sim } 1 5 0 0 ~ \mathrm { k m }$ 范围内电离层的电子密度、电子温度、离子成分及离子温度等重要参数(Bilitza和Reinisch,2008;Bilitza等,2014)．因此，本文利用其最新的版本IRI-2012代替AURICv1.2中IONOS模块进行电子密度廓线计算，从而实现IONOS模块的更新.

改进后的AURIC-2012模型主要输入参数有三个，分别是地理纬度、地理经度和世界时(UTC)，而AURIC-2012模型的输出参数主要为各种气辉的柱辐射强度、体辐射率等参数.AURIC-2012模型计算流程如图2所示.

![](images/29bafc0bf5cb32962d1bd5734d5d95ab7b997ee1f9481405af4f1dde1fec809a.jpg)  
图2AURIC-2012计算模拟流程图

# 2模型验证与分析

基于AURIC-2012，本文对GUVI气辉观测进行了仿真模拟，包括130.4， $1 3 5 . 6 \ \mathrm { n m }$ 和LBH波段气辉，并将模拟结果与实测数据进行了比较．以2002年3月20日地理坐标为 $( 3 1 . 7 8 ^ { \circ } \mathrm { N }$ ， $1 3 8 . 4 ^ { \circ } \mathrm { W } ,$ 的GUVI数据为例，对比结果如图3所示．图中，130.4， $1 3 5 . 6 \ \mathrm { n m }$ 和LBH波段气辉辐射强度模拟值与GUVI实测值随高度的变化规律(纵坐标)较为一致，同一位置同一高度处两者的辐射强度值相近，其中3个波段气辉在峰值区域的模拟相对误差分别为 $2 1 . 9 3 \% ( 1 3 0 . 4 \ \mathrm { ~ n m } )$ $2 2 . 5 7 \% ( 1 3 5 . 6 \ \mathrm { n m } )$ 和 $1 1 . 3 2 \% ( \mathrm { L B H } )$ ，平均相对误差为$1 8 . 6 \%$ ，且峰值模拟值与GUVI峰值实测值处于同一高度.

将AURIC-2012计算得到的 $\mathrm { O } _ { 2 } ( 0 { - } 0 )$ 波段气辉体辐射率与TIDI观测数据进行了对比，如图4所示，AURIC-2012体辐射率计算模拟值随高度分布规律与TIDI观测数据相吻合，4次模拟峰值区域(3个采样(a)2005年9月2日;(b)2008年5月17日;(c)2009年5月17日;(d)2010年1月5日点)相对误差分别为 $8 . 5 6 \%$ （图4(a)）， $1 2 . 4 9 \%$ （图4（b）），$2 4 . 6 7 \%$ （图4(c)）和 $1 6 . 0 6 \%$ (图4(d))，平均相对误差为$1 5 . 4 5 \%$ ，且峰值高度模拟值与TIDI实测值非常一致，

![](images/36b03ca9ce12258b214cfcb9787ca6a9589c0ec93eea29ce3c9f837a5d9464fb.jpg)  
图3 $\mathbf { 1 3 0 . 4 n m }$ (a), $\mathbf { 1 3 5 . 6 \ n m ( b ) }$ 和LBH波段(c)气辉辐射强度对比(单位：瑞利)

![](images/fe4daf1f9de1ea0572954dd905f0a3ba183a0a76ca51bde6f885c98e0eb3b3f8.jpg)  
图4体辐射率模拟值与TIDI实测值比较结果

# 3气辉辐射模拟分析

# 3.1气辉随纬度和高度变化模拟

基于AURIC的更新改进，本文利用AURIC-2012进行了随纬度和高度变化的临边柱辐射强度模拟，模拟日期选择多个年份的春分点附近，以 $1 1 6 ^ { \circ } \mathrm { E }$ (跨北京上空)为不变量，纬度覆盖范围为 $1 9 0 ^ { \circ } \mathrm { S } { \sim } 9 0 ^ { \circ } \mathrm { N }$ ，模拟高度为 $8 0 { \sim } 6 0 0 ~ \mathrm { k m }$ ．由于AURIC-2012只进行了5种主要中性气体密度(H,He,O, $\mathbf { O } _ { 2 }$ 和 ${ \bf N } _ { 2 } \dot { { \bf \Phi } }$ 的计算更新，因此本文的气辉模拟分析主要包括氧原子气辉谱线130.4,135.6,557.7,630.0,636.4,777.4和 $8 4 4 . 6 ~ \mathrm { n m }$ 、氮气分子气辉谱线LBH(仅昼气辉)以及氧气分子气辉谱线 $\mathrm { O } _ { 2 } ( 0 { - } 0 )$ (仅夜气辉)，这些气辉也是用于电离层探测和研究最主要的谱线气辉．模拟结果以2013年3月20日为例 $( \mathrm { F _ { 1 0 . 7 } } \mathrm { = } 1 0 6 . 7$ ， $\mathbf { A } \mathbf { p } _ { \scriptscriptstyle \equiv } { = } 1 2$ ， $\mathrm { A p } _ { \mathscr { U } } { = } 9 .$ ，如图 ${ 5 } { \sim } 6$ 所示(图5为昼气辉，图6为夜气辉).

图5为昼气辉柱辐射强度的模拟结果，分别为130.4, 135.6,630.0,636.4, 777.4,844.6, $5 5 7 . 7 ~ \mathrm { n m }$ 以及LBH波段气辉．由图5可知，昼气辉辐射几乎覆盖所有纬度，其中在赤道附近最强，随着纬度的增加气辉辐射强度逐渐减弱.而昼气辉辐射随高度一般先增大后减小，但不同谱线气辉的主要分布高度和变化快慢规律不同．130.4，135.6，630.0，636.4，777.4和$8 4 4 . 6 ~ \mathrm { n m }$ 气辉辐射分布高度相对较高，随高度变化相对缓慢；而 $5 5 7 . 7 \ \mathrm { n m }$ 和LBH气辉的分布高度相对较低，随高度的变化较快．每个谱线昼气辉具体的分布和变化规律如下：

(1) $1 3 0 . 4 ~ \mathrm { n m }$ 昼气辉较强辐射主要分布在 $3 0 0 ~ \mathrm { k m }$ 高度以下，辐射强度最大可达到几万瑞利；当 ${ > } 3 0 0$ km时，随着高度的增加，辐射强度逐渐减小到几千

![](images/10aa8dda5d77f797e7c80430cccb8fd016fcbb8c0ed7208b86a5ad512003eab8.jpg)  
图5昼气辉临边柱辐射强度模拟结果(单位：瑞利)

瑞利 $( < 6 0 0 ~ \mathrm { k m } )$ ：

(2) $1 3 5 . 6 ~ \mathrm { n m }$ 昼气辉辐射也主要分布在 $3 0 0 ~ \mathrm { k m }$ 以下，辐射强度最大为几千瑞利；在 ${ > } 3 0 0 \ \mathrm { k m }$ 时，气辉辐射迅速减小到几百瑞利；而当 ${ > } 5 0 0 \ \mathrm { k m }$ 时，气辉则变得非常微弱，仅为几个瑞利，

(3)630.0和 $6 3 6 . 4 \ \mathrm { n m }$ 气辉的辐射机理一致，两者的强度变化规律完全相同，但由于跃迁能级不同，因此两种气辉的辐射强度不同 $( I _ { 6 3 0 . 0 } / I _ { 6 3 6 . 4 } \approx 3 . 0 9 )$ .其中，$6 3 0 . 0 \ \mathrm { n m }$ 昼气辉辐射主要分布在 $3 0 0 \mathrm { k m }$ 以下，辐射强度达到几万瑞利；当 ${ > } 3 0 0 \ \mathrm { k m }$ 时，随着高度的增加,辐射强度逐渐减小；而当 ${ > } 5 0 0 \ \mathrm { k m }$ 时，气辉则变得非常微弱，仅为几个瑞利.

(4) $7 7 7 . 4 ~ \mathrm { n m }$ 昼气辉辐射主要分布在 $2 5 0 \mathrm { k m }$ 以下，辐射强度为几千瑞利；当 $> 2 5 0 \ \mathrm { k m }$ 时，随着高度的增加气辉辐射强度逐渐减小；而当 ${ > } 4 0 0 \ \mathrm { k m }$ 时，气辉辐射强度只为几个瑞利.

(5) $8 4 4 . 6 \ \mathrm { n m }$ 昼气辉辐射变化规律与 $7 7 7 . 4 ~ \mathrm { n m ^ { - } }$ 1致，但是辐射强度相对较强，这是由于 $8 4 4 . 6 \ \mathrm { n m }$ 昼气辉除了由氧原子与光电子复合产生之外，还来自于氧气分子及氧原子与电子的反应贡献(表1)

(6) $5 5 7 . 7 \ \mathrm { n m }$ 气辉辐射主要分布在 $2 0 0 ~ \mathrm { k m }$ 以下，其辐射强度较大，达到几十万瑞利；当 ${ > } 2 0 0 \ \mathrm { ~ k m }$ 时，气辉辐射强度迅速减小到几千瑞利；而当 ${ > } 4 0 0 \ \mathrm { k m }$ 时，气辉辐射只为几个瑞利.

(7)LBH气辉与 $5 5 7 . 7 \ \mathrm { n m }$ 气辉辐射分布在同一高度，辐射强度为几万瑞利．不同于其他谱线气辉，LBH气辉为远紫外宽谱段气辉，波段覆盖范围为$1 4 0 { \sim } 1 9 0 ~ \mathrm { n m }$

图6为夜气辉临边柱辐射强度的模拟结果，分别为130.4,135.6,630.0,636.4,777.4, 844.6, 557.7 nm以及 $\mathrm { O } _ { 2 } ( 0 { - } 0 )$ 波段气辉．由于AURIC不能进行曙暮气辉中 $9 0 ^ { \circ } <$ 太阳天顶角 ${ < } 1 1 0 ^ { \circ }$ )计算，因此3月20日夜气辉辐射强度计算主要位于纬度 $( 7 0 ^ { \circ } \mathrm { S } { \sim } 7 0 ^ { \circ } \mathrm { N } )$ 范围内.由图5\~6可知，夜气辉的水平变化规律与昼气辉一致，在赤道附近较强，且随着纬度的增加气辉辐射强度迅速减弱．但相对于昼气辉，夜气辉辐射强度较小，纬度分布范围也相对较小，除 $5 5 7 . 7 ~ \mathrm { n m }$ 和 $\mathrm { O } _ { 2 } ( 0 { - } 0 )$ 波段气辉外，其他夜气辉辐射主要分布在中低纬度地区．此外，夜气辉随高度的分布和变化规律与昼气辉也不一样,130.4,135.6,630.0,636.4,777.4和 $8 4 4 . 6 ~ \mathrm { n m }$ 夜气辉的辐射覆盖范围较广，变化相对缓慢，且峰值高度明显较高；而 $5 5 7 . 7 \mathrm { n m }$ 和 $| \mathrm { O } _ { 2 } ( 0 { - } 0 )$ 夜气辉分布的峰值高度相对于昼气辉则变得更低(峰值为 ${ \sim } 9 5 \ \mathrm { k m } \ '$ ，辐射高度范围也更窄，仅为 ${ \sim } 4 0 \mathrm { k m }$ .每个谱线夜气辉具体的分布和变化规律如下：

![](images/1f4375aca41b31acbf638613ffe2258f94cd91dc5b2adc8de44806e1111c3cd7.jpg)  
图6夜气辉临边柱辐射强度模拟结果(单位：瑞利)

(1) $1 3 0 . 4 ~ \mathrm { n m }$ 夜气辉辐射相对于昼气辉要弱很多，最大只有几百瑞利，主要分布在低纬度地区 $5 0 0 ~ \mathrm { k m }$ 高度以下，中高纬度气辉辐射强度只有几个瑞利，

(2) $1 3 5 . 6 ~ \mathrm { { n m } }$ 夜气辉辐射主要分布在低纬度$1 0 0 { \sim } 5 0 0 ~ \mathrm { k m }$ 高度范围内，最大峰值出现在 ${ \sim } 3 0 0 ~ \mathrm { k m }$ 高度，辐射强度为几百瑞利，而当 ${ > } 5 0 0 \ \mathrm { k m }$ 时，气辉则变得非常微弱.

(3）630.0和 $6 3 6 . 4 \ \mathrm { ~ n m }$ 夜气辉辐射 $( I _ { 6 3 0 . 0 } / I _ { 6 3 6 . 4 } \approx$ 3.09)在中低纬度 ${ \sim } 1 0 0 { \sim } 4 0 0 \ \mathrm { k m }$ 高度范围内辐射较强，其中 $6 3 0 . 0 \ \mathrm { n m }$ 气辉辐射达几千瑞利；在高纬地区依然有气辉辐射，为几百瑞利；无论中低纬还是高纬地区，最大峰值一般出现在 ${ \sim } 2 5 0 \ \mathrm { k m }$ 高度，而当 ${ > } 4 0 0$ $\mathrm { k m }$ 时，气辉则变得非常微弱.

(4) 777.4和 $8 4 4 . 6 ~ \mathrm { n m }$ 夜气辉辐射主要分布在中低纬 ${ \sim } 1 5 0 { \sim } 4 5 0 ~ \mathrm { k m }$ 高度范围内，最大峰值出现在$3 0 0 { \sim } 3 5 0 ~ \mathrm { k m }$ 高度，辐射强度为几百瑞利，而在高纬地区气辉则变得非常微弱．图中， $1 3 5 . 6 \ \mathrm { n m }$ 气辉与777.4和 $8 4 4 . 6 \ \mathrm { n m }$ 气辉辐射变化规律一致，这是因为3种夜气辉均主要由光电子与氧原子碰撞及离子中和反应产生，但是跃迁能级、跃迁概率和复合系数不同，所以3种气辉的辐射强度会有一定差异.

(5) $5 5 7 . 7 \ \mathrm { n m }$ 夜气辉辐射覆盖纬度范围较广，其中在中低纬较大，在高纬地区有所减小，但辐射仍然较强，为几千瑞利；但其辐射强度高度范围较窄，位于 $8 0 { \sim } 1 2 0 ~ \mathrm { k m }$ ，强度最大可达几万瑞利；但当 ${ > } 1 2 0$ $\mathrm { k m }$ 时，气辉辐射强度迅速减小并变得非常微弱.

(6) $\mathrm { O } _ { 2 } ( 0 { - } 0 ) \mathrm { A }$ 波段夜气辉辐射分布规律与557.7$\mathbf { n m }$ 气辉类似，但其辐射强度更大，最大达到几十万瑞利. $\mathbf { O } _ { 2 }$ (0-0)A波段气辉受氧气密度的影响较大，而$5 5 7 . 7 \ \mathrm { n m }$ 气辉则主要受氧原子密度的影响(Strickland,1999)，在 ${ \sim } 1 0 0 \ \mathrm { k m }$ 高度处氧气密度远远大于氧原子的密度，同时 $\mathrm { O } _ { 2 } ( 0 { - } 0 ) \mathrm { A }$ 波段气辉的淬灭系数远小于$5 5 7 . 7 \ \mathrm { ~ n m }$ 气辉的淬灭系数(Strickland，1999)．因此， $\mathrm { O } _ { 2 } ( 0 { - } 0 ) \mathrm { A }$ 波段气辉辐射要远强于 $5 5 7 . 7 \ \mathrm { n m }$ 气辉的辐射.

由图5和6可得，气辉辐射强度随纬度和高度分布具有一定的规律:

(1）氧原子、氧气分子及氮气分子气辉辐射在赤道低纬地区明显强于其他地区，随着纬度的增加逐渐减弱，这主要受电子密度纬度分布的影响．大部分气辉辐射来自于自由光电子与其他粒子的碰撞或反应(表1)，而赤道低纬地区电离层存在赤道异常，导致该区域电子密度明显高于其他高纬地区，因此气辉辐射在该区域也明显增强，随着纬度的增加，电子密度的减小，气辉辐射强度也随之减弱.

(2)气辉辐射强度随着高度的增加先增大后减小．气辉一般是由电子和其他至少一种粒子进行相互作用产生的，由于电子密度随高度不断增大( $\scriptstyle \mathtt { \le 5 0 0 }$ km)，而其他大部分粒子随高度一般呈现相反的变化规律(图7)，因此气辉的辐射强度随高度的增加一般先增大后减小，即在某一高度将存在一个辐射最大值，

同时由图5\~6可知，昼气辉与夜气辉的辐射强度分布也存在一些不同的规律：

(1）昼气辉辐射强度远远大于夜气辉，且纬度覆盖范围也相对较大．由于白天大气受太阳较强的直接照射，电子的密度会大大增加(图7(a))，其他粒子也有不同程度的增加(图7(b))，再加上气辉的激发可以通过太阳的光致电离而直接产生，气辉的辐射机制也变得相对复杂多样，因此昼气辉的辐射强度及分布范围也会大大增加.

(2) $5 5 7 . 7 \ \mathrm { n m }$ 夜气辉辐射高度范围变窄，峰值高度相对较低. $5 5 7 . 7 \ \mathrm { n m }$ 夜气辉的辐射主要来自于氧原子的三体复合(需要第三种中性气体粒子的参与，如$\mathrm { O } _ { 2 } \ddag \Pi \mathrm { N } _ { 2 } \rangle$ ，因此其主要发生在 ${ \sim } 1 0 0 \ \mathrm { k m }$ 高度及以下区域．而 $5 5 7 . 7 \ \mathrm { n m }$ 昼气辉还来自于氧原子与电子的碰撞、太阳直接辐射导致的氧气分子电离以及氮气的惰性化过程，这些机制在 $1 0 0 { \sim } 2 0 0 \ \mathrm { k m }$ 高度范围内均有较大的辐射贡献，使 $1 0 0 { \sim } 2 0 0 \ \mathrm { k m }$ 高度成为白天最主要的辐射区域(Upadhayaya等，2006；Culot等，2004;Thirupathaiah等，2012).因此，相对于昼气辉，557.7nm夜气辉辐射峰值高度会变得较低，辐射厚度范围变得较窄.

(3) $1 3 0 . 4 ~ \mathrm { n m }$ 夜气辉辐射在中层-低热层区域辐射强度随着高度的增加变化非常小，这是由氧原子与光电子碰撞及辐射传输综合作用的结果，这个高度范围主要由电子密度(或峰值)的分布高度决定的(Dymond, 2009).

由气辉的辐射机制可知，中高层大气电子密度对气辉的辐射强度具有较大的影响，是气辉辐射分布的最主要影响因素，尤其对于辐射机制相对简单的夜气辉，电子密度的变化将直接影响它们的辐射变化．图8为不同电子密度时135.6和 $6 3 0 . 0 \ \mathrm { n m }$ 气辉体辐射率和临边柱辐射强度随高度的变化．图中，随着电子密度的降低，气辉的体辐射率和辐射强度也随之减小，且减小的幅度均大于电子密度的减小幅度.

表1各种气辉的辐射机制a  

<html><body><table><tr><td>气辉辐射线</td><td>辐射机制</td></tr><tr><td rowspan="6">OI 130.4 nm</td><td>氧原子与光电子碰撞(昼气辉):O+e→O(3S)+e 太阳光子共振散射(昼气辉):O+Hv→O(3S)+hv(130.4 nm)</td></tr><tr><td>氧气分子离解:Oz+e→O+0(3s)+e</td></tr><tr><td></td></tr><tr><td>光致电离(昼气辉):O2+hv→O+O(3S)</td></tr><tr><td>氧离子与电子复合：O++e→O+hv(130.4 nm)</td></tr><tr><td>离子中和反应:O++O→20+hv(130.4 nm) 跃迁:O(3S)→O(3P)+hv(130.4 nm)</td></tr><tr><td rowspan="3">OI 135.6 nm</td><td>氧离子与电子复合：O++e→O+hv(135.6 nm)</td></tr><tr><td>氧离子中和反应：O++O→2O+hv(135.6 nm)</td></tr><tr><td>氧气分子离解：O+e→O+O+e+hv(135.6 nm)</td></tr><tr><td rowspan="6">OI 630.0 nm/636.4 nm</td><td>离解复合:O²+e¹→O(D')+O</td></tr><tr><td>光电子碰撞:e+O→e+O(D')</td></tr><tr><td>光致电离(昼气辉):O+hv→O(P)+O(D')</td></tr><tr><td>离解复合：NO++e¹→O(D')+N</td></tr><tr><td>禁戒跃迁：O(D')→O+hv(630.0 nm)</td></tr><tr><td>氧离子与电子复合：O++e→O+hv(777.4 nm)</td></tr><tr><td rowspan="2"></td><td>离子中和反应：O+ +O-→20+hv(777.4 nm)</td></tr><tr><td>光电子碰撞(昼气辉):O+e→O(3P)+e</td></tr><tr><td rowspan="4">OI 844.6 nm</td><td>离解复合(昼气辉):O+e→O(3P)+O+e</td></tr><tr><td>氧离子与电子复合：O++e→O+hv(844.6 nm)</td></tr><tr><td>离子中和反应：O+ +O" →20+hv(844.6 nm)</td></tr><tr><td>电子跃迁：O(3P)→O(3S)+hv(844.6 nm)</td></tr><tr><td rowspan="6">OI 557.7 nm</td><td>氧原子与电子碰撞：O+e→O(S)+e</td></tr><tr><td>光致电离(昼气辉):O+hv→O+O(St)</td></tr><tr><td>离解复合:O++e→O+O(S)</td></tr><tr><td>氮气惰性化:N(A³∑,)+O→N+O(IS)</td></tr><tr><td>三体复合:O+O+M→O+MM=N,O²O²+O→O(S)+O</td></tr><tr><td>禁戒跃迁：O(Sl)→O(D')+hv(557.7 nm)</td></tr><tr><td rowspan="3">Oz-A (0-0) 762.0 nm</td><td>三体复合:O+O+M→O(b)+MM=N,O,O</td></tr><tr><td>氧原子与臭氧结合(昼气辉):O+O→2O(bl)</td></tr><tr><td>20(bl)-→2O(X³)+hv(762.0 nm)</td></tr><tr><td>N2 LBH</td><td>N2(X'∑)+e→N(a'[L)+e</td></tr></table></body></html>

a）引自 Strickland 等(1999),Ghosh(2002)和Witasse 等(1999)

![](images/f010b1c6cfa36d48562898e3b3ebbee4286c34bc6c83c4e6debf763a017e8896.jpg)  
图7电子(a)和中性气体(b)密度夜间和白天对比

![](images/995586b90690e6cd966e41b1a8fd2bb7ccc71b9842fe3d303df584f0b346d71c.jpg)  
图8气辉临边柱辐射强度和体辐射率随电子密度的变化(a)电子密度廓线;(b)气辉体辐射率廓线;(c)气辉临边柱辐射强度.1代表原始值，1/2代表原始值的0.5倍，1/3约为原始值的

# 3.2气辉辐射随太阳活动和地磁活动的变化

气辉辐射来自于大气中电子与其他粒子的碰撞、气体的离解复合以及光致电离等作用，因此太阳活动和地磁活动对气辉辐射会有较大的影响.AURIC模型采用太阳射电常数 $\mathrm { F } _ { 1 0 . 7 }$ 和地磁Ap指数分别代表太阳和地磁活动的强烈程度．本文选用两种应用最广泛的630.0和 $5 5 7 . 7 \ \mathrm { n m }$ 气辉进行太阳活动和地磁活动的影响分析，图9为它们临边辐射强度随太阳活动和地磁活动的变化.

随着太阳活动的加剧，气辉辐射具有不同程度的增加，这是由于太阳辐射的增强可直接或者间接使大气辐射出更多的气辉．而地磁活动的变化主要体现在对气辉辐射的区域扰动和变化上．当地磁活动增强，大气扰动变得剧烈， $6 3 0 . 0 \ \mathrm { n m }$ 气辉的辐射会随之增强，但其辐射最主要的是受内重力波等的影响会有不同程度的扰动变化，这种变化一般与地磁活动呈正比．而 $5 5 7 . 7 \ \mathrm { n m }$ 气辉辐射和观测的地理位置、时间及当时的粒子密度等有很大关系，变化现象则比较复杂，既存在正相关的情况，也存在负相关的变化(Leonovich等,2011).

此外，基于地基的观测结果，利用模型对地磁异常期间的气辉辐射进行了模拟．图10为2007年1月16日俄国东西伯利亚地区在小型磁暴期间观测到的气辉变化(Leonovich等，2011)与模型的比较结果．图中，实测值为归一化垂直柱辐射强度，而模拟值为峰值切点高度处归一化临边柱辐射强度．由图可得，气辉辐射的模拟结果变化趋势与观测值变化一致.

# 4结论

AURICv1.2只能进行某一地理位置的单点气辉模拟分析，且只能适用于2000年以前的计算，不适用于目前大量数据的气辉模拟及星上大气成分反演.本文利用Matlab对其地磁参数模块GEOPARM、电离层IONOS模块及大气ATMOS模块进行了更新改进，得到AURIC-2012．其中，AEOPARM模块的改进包括地磁经纬度、磁倾角、太阳天顶角、太阳当地时间、太阳指数 $\mathrm { F } _ { 1 0 . 7 }$ 及地磁指数Ap等的计算；电子密度的更新是利用国际参考电离层IRI-2012计算值代替AURICv1.2的IONOS模块计算值；大气温度及中性气体密度廓线的更新则是利用DTM-2013模型的计算值代替AURICv1.2的ATMOS模块计算值．将更新模块与AURIC原有模块相结合，不仅可以进行气辉辐射模拟批量计算，还可以参与星上大气成分的批量反演，如 $\mathrm { O } / \mathrm { N } _ { 2 }$ 和电子密度.

![](images/f82c3d740cd2e46756fab1ea0153563671602d787040eaf1e4956e36a3d43984.jpg)  
图9气辉辐射强度随太阳活动和地磁活动的变化

![](images/4f24c594c878282982fcfbde5d3f90d7215a8bc564289155161d5e70a95ced1d.jpg)  
图102007年1月26日俄国东西伯利亚地区 $( 5 2 ^ { \circ } \mathbf { N } ,$ $\mathbf { 1 0 3 ^ { \circ } E ) }$ 磁暴期间的气辉辐射实测变化与模拟结果变化的比较

将AURIC-2012的临边辐射强度模拟值和体辐射率计算值分别与GUVI柱辐射强度测量值和TIDI体辐射率测量值进行比较，辐射强度峰值模拟平均相对误差为 $1 8 . 6 \%$ ，体辐射率峰值模拟平均相对误差为$1 5 . 4 5 \%$ ．最后，利用AURIC-2012进行多年份春分时的昼气辉和夜气辉临边辐射强度随纬度和高度的二维模拟，并基于模拟结果对昼气辉和夜气辉的辐射强度及分布规律进行了比较分析．由模拟分析可得，春分点附近氧原子、氧气分子及氮气分子气辉辐射主要位于中低纬度地区 ${ < } 5 0 0 ~ \mathrm { k m }$ 高度范围内，随着纬度的增加，辐射逐渐减弱，而随着高度的增加辐射一般先增大后减小．此外，不同谱线气辉的辐射强度差异较大，同一谱线气辉白天和夜间的辐射差异也较大，这些现象是由气辉本身的辐射机制、大气粒子的密度、太阳活动和地磁活动强度等共同作用的结果.

气辉的批量辐射模拟分析，不仅为星载测量提供物理设计理论指导，也为星载大气成分探测提供反演手段．但由于中性气体模型代码的限制，AURIC-2012只对五种主要中性气体成分进行了密度更新，因此在今后的工作中需进一步对其他中性气体成分进行密度更新计算，同时进行AURIC-2012辐射物理计算模块的替代，并在此基础上对某些气辉的辐射机制进行修正和参数更新，以更准确的进行更多气辉谱线的辐射模拟和星上数据反演研究.

# 参考文献

彭圣锋，唐义，王静，等.2012.远紫外光谱遥感反演热层O/N2技术研究．光谱学与光谱分析,32:1296-1300   
张永超，何飞，张效信，等.2014．电离层LBH日辉辐射大视场计算方法．地球物理学报,57:354-363   
江芳，毛田，李小银，等．2014．利用OI $1 3 5 . 6 \ \mathrm { n m }$ 夜气辉辐射探测电离层峰值电子密度及电子总含量的研究.地球物理学报，57: 3679-3687   
BarlierF,Berger C,FalinJ,etal.1978.A thermospheric modelbased onsatelite drag data.Ann Geophys,34: 9-24   
BergerC,BiancaleR,Il,etal998.ImprovementoftempiricalthermospericodelD:D-94omparativeevieoarious temporal variations and prospects in space geodesy applications.J Geodesy,72:161-178   
BilitzaD,ReinischBW.008.nterationalreferenceionosphere2O7:Improvementsandnewparameters.AdvSpaceRes,42:99609   
BilitzaD,AldilDangYtaeiteatioaleereeosreodelfteaalcolbratioace Weather Space Clim,4: 1-12   
BishopJFeldanPD.AalysisofteAstroHopisUtravioletTelescopeEUVUVaysideadirspetralrdiaceeasutJ Geophys Res,108:1243,doi: 10.1029/2001JA000330   
Bobik P,PutisM,BertainaM.2013.UVnghtbackgroundtiationinSouthAtlanticAomaly3rdIteratioalCosmicRayCoferece. ID0874: 123-127   
BruinsmaSL,Tuillalr.Thpicalospeodlwithatasslatiodostrtsr boundary:Accuracy and properties.JAtmos Sol-TerrPhys,65:1053-1070   
BruinsmaSL,TamagnanD,iancaleR,etal.2O04AtmospericdensitisderivedfromCHAMP/STARaccelerometerbservatios.Planet Space Sci,52:297-312   
BruinsmaSL,Snchez-OrtizN,OlmedoE,etal.2O2.EvaluationoftheD-thermosperemodelforbechmarkingpurpos.pace Weather Space Clim,2: 1-14   
CulotF,LathullereC,LilenstenJ,tal2O04.TeO630and57.7daglowmeasuredbyWNDandmodeledbyANCA.An Geophys,22:1947-1960   
DymondKF.2O09RemotesensingofnighimeFregiopeakheightandpeakdensityusingultravioletlinratios.RadioSci4A28   
Evans JS, Strickland D J,Bishop J. 2002.AURIC User's Guide.Version 1.2   
EvansJS,LumpeJD,CoreiraJetal13ExtensionoftheURICadiativetransferodelforarsatmosphericreseachAmerica Geophysical Union,Fall Meeting 2013,abstract #P21A-1686   
EstesRW.2o.ModeligteNLyman-ige-Hopieldandsithaygowicudingadiatieandcollsioalcscadgbetweetinglet states.JGeophys Res,105: 18557-18573   
FinlayCC,usgCaltatioaogeicerced:eevethgeatioost:   
Ghosh S N.2OO2.The Neutral Upper Atmosphere.Dordrecht: Springer Science Business Media   
Leonovich L A, Mikhalev A V, Leonovich V A. 2011. The 557.7 and $6 3 0 . 0 \ \mathrm { n m }$ atomic Oxygen midlatitude airglow variations associated with geomagnetic activity.Atmos Oceanic Optics,24: 396-401   
Link R,SiricklandDJDaniellRE,al992.AURICirglowoules:Phase1develoentadaplicatioSP,Utravioletcology IV,1764: 132-1441   
MurtaghDP,DonalP1989.Aself-consistentmodeloftheostcommonnightglowemissos.Proc.NinthESA/PACSymposumonuropean Rocket and Balloon Programmes and Related Research.167-171   
Murtagh D P,Witt G, Stegman J, et al. 1990.An assessment of proposed O (1S)and $\mathbf { O } _ { 2 }$ nightglow excitation parameters. Planet Space Sci, 38: 45-53   
Richards PG,TorreDG.1988.Ratios of photoelectrontoEUVionizationrates foraeronomic studies.JGeophys Res,93: 0604066   
Richards PG,Torr D G,Reinisch B W,et al.1994. $\mathrm { F } _ { 2 }$ peak electron density at Millstone Hill and Hobart: Comparison of theory and measurement at solar maximum.JGeophys Res,99:150o5-15016   
Reda I,Andreas A. 2Oo4.Solar position algorithm for solar radiation application.Solar Energy,76: 577-589   
Solomon S C,Abreu VJ.1989.The 630 nm day glow.JGeophys Res,94: 6817-6824   
StephanW,DyondKFudzienSA,etalO4.idleravioletremotesesingofthquatoraltmosperedringgoagetic storm. Ann Geophys,22: 3203-3209   
Stricklandsoted)e and selected results.J Quant Spectrosc Ra, 62: 689-742   
StricklandDJeierR,WalterseidR,etlOQuieteasoalaviofttospreeeitfrultraillo.J Geophys Res,109:A01302   
Thirupathaiah P,SunilKrishna MV,Singh V.2012.Efectof solaractivityon thelatitude variationof peak emissionrateof $5 5 7 . 7 ~ \mathrm { n m }$ dayglow emission under equinox conditions.J Atmos Sol-TerrPhys,77: 2O9-218   
UpadhayayaAK,SinghV,TagiS.o.Latitudinalanddiualvarationsofsoeimportatatomicoxygendayglowemissios.IdianJ Radio & Space Physics,35:327-334   
WitasseO,LstaJatuleC999odelingthed57.7mospricalorigCAodt measurements.JGeophys Res,104: 24639-24655