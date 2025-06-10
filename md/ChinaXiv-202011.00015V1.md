# 基于最大熵谱估计的高能电子周期特性研究

万美言‘，鲁同所¹²，廖傯含‘，于白雪‘，高贝贝

1．西藏大学理学院，拉萨850000；2.中国科学院上海应用物理研究所，上海嘉定201800；

摘要：本文利用最大熵谱估计的方法研究了风云二号D星>2.0MeV的高能电子通量的周期特性，该算法以自相关（AR）模型为基础，通过对最大熵谱功率谱的分析，推测出风云二号D星高能电子通量存在13.87d和27.8d的周期。根据FPE、AIC准则确定最佳阶数进而计算AR 模型参数，并将Levinson-Durbin、Burg 算法与最大熵谱估计法进行了比较，发现最大熵谱估计法在周期特性研究上存在优势。这一结果对研究地球同步轨道高能电子空间分布、预报高能电子增强事件和预警深层充电事件至关重要。

关键词：高能电子；最大熵谱；周期特性；功率谱估计中图分类号：P172.4文献标识码：A 文章编号xxxx -xxxx(xxxx)xx- xxxx -xx

高能带电粒子组成的空间辐射环境是影响航天器在轨安全飞行最重要的空间环境之一，主要包含：其一，这些高能带电粒子入射到物质中，在航天材料表面或内部发生充放电反应，导致航天器材料内部因为电磁干扰而发生故障；其二，高能电子会形成电流脉冲，改变元器件内部的电荷分布，造成元器件的逻辑状态混乱而引发故障甚至失效；其三，高能带电粒子的辐射效应会通过电离作用导致航天器的材料、元器件性能变差，直至失效，同时辐射效应也会对人体造成损伤，严重影响航天员的安全。

风云二号是我国研制的第一代地球同步轨道气象卫星，与极地轨道气象卫星相辅相成，构成我国气象卫星应用体系[2]。风云二号D星于2006年12月8日成功发射升空，在高度为35783-35788km 的高轨道上飞行，包含高能质子、电子、He离子等，共有7个能道。FY-2D 定位东经 $8 6 . 5 ^ { \circ }$ 赤道上空，轨道周期为1436.04分钟，轨道倾角为 $1 . 8 4 ^ { \circ }$ ，自旋稳定，转速 $1 0 0 \mathrm { r / m i n }$ 。风云二号D星搭载空间粒子探测器，它是空间环境监测器的一部分。风云二号D星与之前发射的A星共同实现双星观测，发挥 $_ { 1 + 1 }$ 大于2的系统效益，提高卫星观测频次，扩大卫星观测范围，实现立体观测和动态监测3]。对研究高能粒子的周期特性提供更精确、可靠的数据，同时也可为研究太阳活动、地磁活动对空间环境的影响提供很好的参考。

本文主要利用最大熵谱估计研究了近地空间高能电子( ${ \bf \beta } \mathrm { \geqslant } 2 . 0 { \bf M e V }$ 电子通量)的周期性变化特征，同时对比其与Levinson-Durbin和Burg算法的优缺性。本课题研究所采用的数据覆盖时间范围为2006年12月19日至2012年5月21日，时间精度为 $5 \mathrm { m i n }$ ，对数据空缺部分均进行插值处理。

# 1研究方法

lutongsuo@163.com

# 1.1最大熵谱估计

常用的时变分析方法是傅里叶变换[4，而本文采用最大熵谱法，其原因一是在研究周期特性上傅里叶变化缺乏时间和频率的定位功能，傅里叶变化是一种整体变化，它不能够反应某个时间段的信号发生了怎样的变化，也无法获得某一频率出现的时刻信息；其二傅里叶变化对非平稳信号存在局限性，本文研究的高能电子通量，它的频率是随时间变化的，用傅里叶变换进行分析只能给出高能电子通量频率变化的整体效果而不能完整地反映出某一时刻信号的本质特性。

最大熵谱估计具有高分辨率和短时性的特点，其原理可概述为：利用已有的自相关函数值,以最大熵为前提,利用N 个已知的自相关函数值来外推其他未知的自相关函数值，最后作频域变换,求得连续的功率谱估计，为研究数据的周期特性提供了算法支撑。

具体步骤为[5]：

计算初始值

$$
\mathrm { r } _ { x } ( 0 ) = \frac { 1 } { N } { \sum _ { n = 0 } ^ { N = 1 } } \bigl [ x ( n ) \bigr ] ^ { 2 }
$$

$$
f _ { _ { 0 } } ( n ) = g _ { _ { 0 } } ( n ) = x ( n )
$$

求出预测均方误差 $p _ { m }$ 递推公式

$$
p _ { m } \equiv \left( 1 - \left| k _ { m } ^ { 2 } \right| \right) p _ { m - 1 }
$$

求解 AR 模型的反射系数 $k _ { m }$

$$
k _ { m } = - 2 \frac { \displaystyle \sum _ { n = m } ^ { N - 1 } f _ { m - 1 } g _ { m - 1 } ( n - 1 ) } { \displaystyle \sum _ { n = m } ^ { N - 1 } \Bigl [ \bigl | f _ { m - 1 } ( n - 1 ) \bigr | ^ { 2 } + \bigl | g _ { m - 1 } ( n - 1 ) \bigr | ^ { 2 } \Bigr ] } , m = 1
$$

求前向预测误差和后向预测误差，然后顺次估计出反射系数 $k _ { m }$

$$
f _ { m } ^ { f } ( n ) = f _ { m - 1 } ( n ) + k _ { m } g _ { m - 1 } ( n - 1 )
$$

$$
g _ { m } ( n ) = f _ { m - 1 } ( n - 1 ) + g _ { m - 1 } ( n - 1 )
$$

由Levinsion递推，求出阶次 $m = 2$ 时 AR 模型参数

$$
a _ { m } ( i ) = a _ { m - 1 } ( i ) + k _ { m } a _ { m - 1 } ( m - 1 ) \quad i = 1 , 2 , \cdots , \ m - 1
$$

$$
a _ { \scriptscriptstyle m } ( m ) = k _ { \scriptscriptstyle m }
$$

重复上述过程，直到 $m$ 等于所需AR 模型阶数，求出所有的AR 模型参数，然后预测出时间序列的最大熵，即，

$$
P _ { \scriptscriptstyle M E M } ( e ^ { j } ) = \frac { \sigma ^ { 2 } } { \displaystyle \left. 1 + \sum _ { k = 1 } ^ { m } a _ { k } e ^ { - j k } \right. ^ { 2 } }
$$

式中 $k = 1 , 2 , \cdots { \mathrm { ~ , ~ p ~ } }$ 为 $\mathsf { p }$ 阶线性预测滤波器系数， $\sigma ^ { 2 }$ 为预测滤波器的预测误差功率。

# 1.2Levinson-Durbin 和Burg 算法

Levinson-Durbin、Burg[算法均是线性预测方法，是根据已知的时间信号序列计算功率谱估计值的递推算法。Burg 算法利用前向滤波误差 $f _ { n , t }$ 和后向滤波误差 $b _ { n , t }$ 来求出滤波误差功率为最小的 $\boldsymbol { a } _ { n m }$ ，再根据 Levinson-Durbin 算法计算AR模型参数 $a _ { n i }$ 。要利用AR模型进行功率谱估计，需要用到Yule-Walker方程：

$$
a _ { m } ( i ) = a _ { m - 1 } ( i ) + k _ { m } a _ { m - 1 } ( m - i ) , i = 1 , 2 , . . . , m - 1
$$

M阶AR模型的第 $\mathrm { m } { + } 1$ 个参数G满足：

$$
\boldsymbol { G ^ { 2 } } = \boldsymbol { p } _ { m }
$$

$p _ { { \scriptscriptstyle m } }$ 是预测功率误差，可得递推公式：

$$
p _ { { _ m } } = p _ { { _ m } - 1 } ( 1 - k _ { { _ m } } ^ { \mathrm { ~ 2 ~ } } )
$$

由（8）式进行递推，可求得最终表征随机信号的AR模型的 $\mathsf { p } +$ 参数，最后求得随机信号的功率谱密度:

$$
S _ { _ x } ( e ^ { j \omega } ) = \sigma ^ { 2 } \omega \big | H ( e ^ { j \omega } ) \big | ^ { 2 }
$$

# 1.3AR(自相关)模型阶数的确定

AR模阶数的确定十分重要，在最大熵谱估计和Levinson-Durbin、Burg 算法中都会用到。若选择太小的阶数，得到的功率谱图会太平滑，不能够有效地分辨出时间序列周期分量；若选择太大的阶数，会影响最大熵估计值的稳定性。AR模型的最佳阶数值需要在递推过程中来确定。使用Levinson递推算法，由低阶到高阶的每一组参数及模型的最小预测误差功率 $p _ { \operatorname* { m i n } }$ 是递减的。理论上来说，当 $p$ 值达到期望值，或不再发生任何变化时，即满足最佳适用性，此时的阶数就是应选的最佳参数。以下是两个常用的阶数适用性检验准则[7];

# （一）最终预测误差准则 $( F P E )$

FPE 准则考虑到的是预测值和真实值之间的误差，以误差最小为原则，而使误差最小只对应一个阶数值 $\scriptstyle { \boldsymbol { r } } _ { \circ }$ 由此 FPE $( r )$ 定义为：

$$
F P E ( r ) = p _ { r } \frac { N + ( r + 1 ) } { N - ( r + 1 ) }
$$

式中N为高能电子通量的数据样本数。

# （二）赤池信息准则(AIC)

AIC 准则是建立在熵的概念上，可以判断所估计模型的复杂度和此模型拟合数据的优良性，定义 $A I C ( { \boldsymbol { r } } )$ 为：

$$
A I C ( r ) { = } 2 r { - } 2 \ln \bigl ( L \bigr ) r
$$

阶数 $\mathit { \Pi } _ { T }$ 取值发生变化 $F P E ( r )$ 和 $A I C ( r )$ 的值也将发生变化。在 $r$ 取某值时， $F P E ( r )$ 和 $A I C ( r )$ 的值都为最小值，那么此时所取的 $\boldsymbol { r }$ 就是最佳阶数值。

在实际运算中发现，数据较短时，所得的最佳阶次值偏低，且以上两个准则所得的最佳阶数值基本一致。即：

$$
\operatorname* { l i m } _ { { N  \infty } } \lg F P E ( r ) = A I C ( r )
$$

# 2.高能电子通量周期特性

# 2.1数据选取

本文选择分析能道 $\geqslant 2 . 0 \mathrm { M e V }$ 的高能电子通量，是能量极高的带电粒子。由于初始数据在2009年12月6日-12月30日、2011年2月2日-2月11日、2011年8月22日-8月24日等时间段均存在缺失,为了避免缺失数据对研究周期特性的影响，因此利用函数Fillmissing通过matlab实现对所收集到的数据进行插值处理，如图1所示，是2006年12月19日到2012年5月21日高能电子在能道≥2.0MeV的电子通量变化情况，数据频次为5min,每日24小时，平均每日288个数据，经过插值处理数据后，数据量超过50万。

![](images/1d2f39f02ad412ceabc93dd96e6d60f53149af571020ee7ac970610d4b7df87a.jpg)  
图1高能电子通量在2006年12月19日-2012年5月12日之间的变化情况Figure 1 Changes in high-energy electron flux between December l9,2006 and May 21，2012

# 2.2数据处理

由图1可知由于时间跨度长，数据量庞大且数据十分密集，高低起伏不平，直接用于分析研究，很难直观的给出周期性特征，故做日平均处理，如图2所示选择的数据是2006年12月19日到2012年5月21日之间的日平均数据。由于数据庞大我们只选择研究以“天”为量级的电子通量周期且日平均数据将平滑掉短周期时变特性，故采用日平均数据是合理的。该图显示高能电子的通量是存在一定周期的且周期不唯一，分主周期和次周期，根据图像的分布特点，可以看出在2006年12月19日至2008年12月19日和2009年12月19日至2012年5月21日期间曲线波动较大，而在2008年12月19日至2009年12月19 日这一年时间的通量变化十分微小。为了更好的研究2006-2012年高能电子通量的周期特性，我们采用了最大熵谱估计8]。

![](images/8861461c599d34e6b6ebb3e0d577777a7ecaa420a0bd66b439447a31a84fd5bd.jpg)  
图2高能电子在2006年12月19日-2012年5月21日之间日平均通量图igure 2 The daily average flux of High Energy Electronics between December 19,2006 and May 21，2012

由于 FY-2D卫星的粒子探测器所探测到的高能电子通量数据存在部分缺失，为了便于处理，我们对原始数据进行了插值处理，然后采用归一化方法，以减少插值数据对原始数据的影响以及对整个研究结果的干扰。由图3可知数据分布特点与图2所显示的几乎一致；表明使用插值后的数据研究周期特性较为合理。

![](images/ab09da4f3db3fcce9f90448c6ec87630de894e7fc54e019e2510dac4f80b929a.jpg)  
图3归一化日平均图 Figure 3 Normalized daily average diagram

# 3高能电子通量的周期特性分析

为估计高能电子通量的周期特性[10]，本文选取2006年12月19 日-2012 年5月21日的日平均数据进行分析。分别采用最大熵谱法和Levinson-Durbin、Burg算法进行计算，对比分析两种方法的准确性。

# 3.1AR模型阶数选择与确定

由2.2.1 可知，在AR模型参数的选择时，我们一般采用 FPE 和 AIC 两种准则来判断。选择正确的AR阶数是最大熵谱估计的关键之一，其值的大小能够影响我们判断熵谱图的波峰，继而影响周期的研究结果。

根据FPE、AIC准则的计算公式，基于matlab来实现最佳阶数的选择[11]，如图4所示，图4(左)、图4(右)分别展示的是FPE 准则和AIC准则关于阶数和参数估计的关系;

![](images/2a736a1530f1ef34ecd67a4cffdc12f5b4ce457fc6f1011cea69c62313b1e8a8.jpg)  
Figure 4 FPE guidelines (left） and AIC guidelines (right)

图4(左、右)两图中的横、纵坐标分别为参数估值和所对应的阶数。用时间序列的最小二乘法和FPR、AIC准则对AR模型进行参数估计，再作折线图得到对应的FPE和AIC准则函数关系。由图4（左）、图4（右）两图对比可以看出AR模型阶数为10时，FPE和AIC函数所对应的参数估值均为最小值，分别为1277145.757和33018.72179,根据上面所说的确定标准，运算结果符合上文2.3公式（11）。由此确定该AR模型的最佳阶数为10。所确定的最佳阶数均适用于下面的最大熵谱估计和Levinson-Durbin、Burg算法。

# 3.2高能电子通量周期特性分析

# 3.2.1最大熵谱估计

根据4.1确定的最佳阶数，进行最大熵谱分析[12]。使用日平均数据作出高能电子通量最大熵谱功率谱，如图5所示，阶数为10，高能电子通量周期分主、次周期[13]，根据功率谱概率分布可知，分布图存在有多个峰值，本文选择研究的是最高波峰和次高波峰。最高波峰频率为$0 . 0 6 2 5 \mathrm { d } ^ { - 1 }$ 时，对应为主周期，功率谱最大，值为14.16，对应周期为13.87d，次波峰频率$0 . 1 6 4 1 \mathrm { d } ^ { - 1 }$ 时，对应为次周期，功率谱处于第二大值，值为13.71，对应周期为27.8d。此研究结果与相关文献[14利用小波分析得出的高能电子通量的27d周期和13d周期结果几乎一致，证明了最大熵谱法研究高能电子通量周期具有一定准确性。

![](images/f30ef48da957ebcfebf2656523c948056ad5ef6c8b875b48ea6363ed414fd57a.jpg)  
图4FPE准则（左）和AIC准则（右）  
图5最大熵谱法功率谱  
Figure 5 power spectrum diagram of Maximum entropy spectrum method

尽管方法合理可行，也考虑了诸多因素，但是由于对数据进行了插值处理，经初步分析，计算结果大概存在0.03-0.08d的误差。

此外图中可以明显看出功率谱不止一个波峰，表明周期不唯一，且根据图像波峰变换的趋势也能判断出其不稳定性[5]。

# 3.2.2 Burg算法和levinson算法

上文已经确定了最佳阶数为10，采用日平均处理后的数据进行周期特性分析。首先按照最佳阶数10绘出 Burg、Levinson 算法的功率谱图像，与图5对比，图6的左、右两图像基本一致，再次证明阶数10为最佳阶数。而观察左、右图可知主周期频率为0.011d1，次周期频率是0.128d‘所算出的主、次周期值均与最大熵谱法结果不符。

![](images/1fbff0641e20f5faa579c3a650b755a62bdbab3cc352d05e1facfc786522b956.jpg)  
图6Burg算法（左）、Levinson算法（右）功率谱图Figure 6power spectrum diagram of Burg algorithm (left）and Levinson algorithm (right)

根据上两图对比可知，高能电子通量确实存在周期性，且有多个周期，周期分为主、次周期，分别为 13.87d 和27.8d。与此同时，对比了最大熵谱法和 Burg、Levinson 算法的分析结果，结果显示最大熵谱法的分析结果更接近真实值，更符合实际情况。

相关文献表明[16，17]，电子通量的13天和27天周期与太阳活动密切相关。比如在太阳活动低年，横越赤道的冕洞发展会产生高速太阳风，导致外辐射中电子通量发生变化，随着太阳的自转，延伸型的冕洞每27天旋转一周，从而电子通量变化也具有了27天的周期性。而电子通量的13天周期也是伴随着太阳风速的变化而产生的，在27天周期中主要有3个相期：快速上升、峰值期和下降期，这种对称变化过程，即形成了13天周期，所以一般在电子通量的27天周期中存在13天周期的变化成分。

# 4结论

本文基于风云二号D星所探测到的高能电子的通量，利用最大熵谱法对周期特性进行了研究，得出以下几个结论：

(1）最大熵谱估计表明高能电子通量的主周期为13.87d 和27.8d，而且高能电子通量的周期不唯一，不稳定。  
（2）通过最大熵谱估计和 Levinson-Durbin、Burg 算法关于高能电子周期特性研究的比较，可以判断出最大熵谱估计更适合于高能电子周期的研究[18]，结果更接近于真实情况。  
(3）太阳活动会影响高能电子的周期，随着太阳活动的变化，周期也将发生相应变化。通过分析高能电子通量的周期变化可以侧面预测太阳活动的变化趋势，为日后研究太阳活动提供有价值的参考。

# 参考文献

[1]刘震.风云4A和GOES-13高能电子观测数据在轨交叉定标及数据融合[D].中国科学院大学(中国科学院国家空间科学中心),2019.

LiuZhen.On-orbitcosscalibrationanddatafusionofFengun4AandGOES-13higenergyelectronicobservationdataDUnivesityf Chinese Academy of Sciences (National Space Science Center of Chinese Academy of Sciences),2019.

[2]咸迪.风云二号H星[J].卫星应用,2018(11):78.XianDi.Fengyun-2H satellite[J].Satellite Applications,2O18(11):78.

[3]许玲,何绍改.中国气象卫星发展又上新台阶——从风云二号D星在轨交付运行看中国气象卫星的发展[J].国防科技工业,207(07):30-32. XuLing,Heogiedvelopntofina'seteorogicalsateliessachdlevel-tedvelopntofina'setegical satelites frotheeliveryndperationoftheFengun-2atelie[J].ationalDefenseTchologyIdustry,o):-2.   
[4]党策,姜爱民,董志超,薛建伟.基于傅里叶变换色散条纹法的实验研究[J].天文研究与技术,2019,16(04):470-477. DangCe，JiangAimin，Dong Zhichao，XueJianweiExperimentalresearchbasedonFouriertransformdispersivefringe method[J].Astronomical Research and Technology,2019,16(04):470-477.   
[5]李甦.有限长观测数据的最大熵谱分析与算法[J].云南大学学报(自然科学版),1995(01):93-99. LiSu.MaximumEntropySpectruAnalysisandAlgorithmofLimitedLengthObservationData[J]JoualofYunnanUniversity(atural Science Edition),1995(01):93-99.   
[6]马忠强,陈国通,赵雪.周期图法与Burg 算法的对比研究[J].信息通信,2017(04):1113 MaZhongqiang,ChenGuotong,Zhao Xue.ComparisonstudyofperiodogrammethodandBurgalgorithm[J].Informationand Communication,2017(04):1113   
[7]邹鲲，袁俊泉，龚享铱.MATLAB 6.x 信号处理[M].清华大学出版社,2002. Zou Kun, Yuan Junquan, Gong Xiangyi. MATLAB 6.x signal processing[M].Tsinghua University Press,2002.   
[8]孔令高,王世金,林华安,韦飞.FY-2C卫星太阳X射线探测器性能定标[J].空间科学学报,2006(05):370-376. KongLinggaoWangSijin,LinHuaan,WeiFei.PerformancecalibrationofFY-2CsatelitesolarX-raydetector[J]ActaSpace   
Science,2006(05):370-376.   
[9]GardereretfsalelaioJ]Esacsousihdalocig 1123.   
[10]N.Ahmed, K.R. Rao. Orthogonal transforms for digital signal processing[M]. Springer,1975.   
[11]何璇.基于 Matlab 的AR 模型参数估计[J].信息与电脑(理论版),2019(07):5-6. He Xuan. AR modelparameterestimationbasedonMatlab[J].IformationandComputer(Theoretical Edition),20l9(07):5-6.   
[12]王宏禹.最大熵谱分析[J].通信学报,1982(01):77-86. Wang Hongyu. Maximum entropy spectrum analysis [J].Journal of Communications,1982(O1): 77-86.   
[13]徐海翔,崔正湃,吴林林,王若阳,刘辉.基于最大熵谱估计的风电功率周期特性研究[J].太阳能学报,2018,39(09):2425-2431. Xu Haixiang,Cui ZhengpaiWuLinlin,WangRuoyang,LiuHui.Researchonwindpowercyclecharacterisicsbasedonmaximumetropy spectrum estimation[J].Acta Solar Energy,2018,39(09):2425-2431.   
[14]张晓芳,符养,严卫,李就.地球同步轨道高能电子变化[J].地球物理学进展,2009,24(06):1951-1957. Zhang Xiaofang,FuYang，YanWei,LiJiu.High-energyelectronchangesingeosynchronousorbitJ].ProgressinGeophsics，09, 24(06):1951-1957.   
[15]唐洁.功率谱分析方法在周期分析中的应用[J].陕西理工学院学报(自然科学版),2013,29(05):71-74+78. TangJie.Alcationofpowerspectrumanalysismethodinperodanalysis[J].JouralofShaaniIstituteofTechnology(NaturalSience Edition),2013,29(05): 71 $^ { 7 4 + 7 8 }$   
[16] 田天,焦维新,王永福.不同地磁活动期间地球同步轨道高能电子通量分析[J].航天器环境工程,2008(02):114-119+97. TianTian,JiaoWeixin,WangYongfu.Analysisofhighenergyelectronfluxingeosynchronousorbitduringdiferentgeomagnetic activities[J].Spacecraft Environmental Engineering,2008(O2):114-119+97.   
[17]Desorghrerde,Outeratioisig95[J]dciaeeac9,   
[18]KunikoKderaRogerdriCdeeViledaryompexepetatioofadsigaldlicatiotalyisf ULFwaves[J].Journalof Geophysical Research,1977,82(7).

# Study on the periodic characteristics ofHigh-energy electronsbasedonmaximumentropyspectralestimation

WAN Mei-yan1,LU Tong-suo1.2,LIAO Si-han1,YU Bai-xue1,GAO Bei-bei1 (1.Collgofice,XizangUversityasa8oo,Cina;.aghaiIstituteofAppledyics,esecadfie

Abstract: Based on maximum entropy spectral estimation method, this paper analyzes the periodic characteristics of the high-energy electron flux ${ \geqslant } 2 . 0 \mathrm { M e V }$ which has been observed by FY-2D meteorological satelite.The algorithm is based on the autocorrelation model (AR),a period of 13.87d and 27.8d is deduced by analyzing the power spectrum. According to the FPE and AIC criteria, the parameters of the AR model can be determined. Levinson-Durbin algorithm and Burg algorithm are compared with the maximum entropy spectral estimation method, it is found that maximum entropy spectral estimation has advantages in the study of periodic characteristics.The results are very important for the study of the spatial distribution of high-energy electrons in geosynchronous orbit,to forecast high energy electron flux enhancement events,or early warning of deep charging events.

Keywords:High-energy electrons;Maximum entropyspectral estimation;The periodic characteristics; power spectrum estimation;