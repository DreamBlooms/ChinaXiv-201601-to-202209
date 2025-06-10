# 基于MEMS加速度传感器的步数检测算法研究综述

谢光强，黄向龙，李杨，徐峰(广东工业大学 计算机学院，广州 510000)

摘要：随着智能移动终端、智能穿戴设备以及基于惯性传感器的行人定位导航系统的快速发展，针对这些设备和系统中的计步需求，大量有关基于MEMS 加速度传感器的步数检测算法的研究工作已经开展并取得了优秀的成果。针对该领域中现有的技术方法，首先阐述了该领域的发展情况，指出目前该领域的主要研究要点、方法种类以及应用情况；接着，综述了目前该领域的研究现状，从数据预处理方法和步数验证方法这两方面对多种步数检测算法进行了阐述以及优缺点的分析；然后，对该领域的研究要点进行了深入的探讨，分析总结步数检测算法中与研究要点相关的技术方法。最后，讨论并展望了该领域未来的发展方向，以期为后续的研究提供参考。

关键词：步数检测；MEMS；加速度传感器 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.10.0000

# Review of research on step detection algorithm with MEMS-based acceleration sensor

Xie Guangqiang, Huang Xianglong, Li Yang†, Xu Feng (School of Computers Guangdong University of Technology, Guangzhou 51ooo0, China)

Abstract:Withtherapid developmentof inteligent mobile terminal,smart wearable devicesand the pedestrian navigation systembasedoninertialsensors,andforthedemandofstepcountingin thesedevicesandsystems,alargenumberofresearches onstep detection algorithm with MEMS-based acceleration sensor have beencarriedoutand achieved good results.For the existingtechnlogyithefeld,thedevelopmentofthisfieldisfirstlyintroduced,andthemainresearchpoints,methodnd applicationsofthfeldarepoitedout.Ten,teurrntresearchstatusintisfeldiseviewedadthedatapre-preproeing methodsand thevalidation methods ofsteps in diferent step detectionalgorithms are describedand analyzed.And then,the main research pointsare discussed indetail,andthe methods related tothe mainresearch pointsaresummarized.Finally,for providing reference for follow-up researches, the possible developments ofthis field is discussed and prospected.

Key Words:step detection; MEMS;acceleration sensor

# 0 引言

近年来，关于步数检测算法的研究成果层出不穷。传统的步数检测方法利用金属摆或钢珠的惯性来进行[1]。随着MEMS技术的发展，基于MEMS的加速度传感器技术日趋成熟，其物理体积小，轻便易携带，并且对加速度数据测量的准确度和可靠性达到了实际应用的要求，许多智能移动终端例如智能手机、智能手环等都已经嵌入MEMS加速度传感器，并且随着这些设备对于计步功能的需求的提出，基于MEMS加速度传感器的步数检测算法受到越来越广泛的关注。所谓的基于MEMS加速度传感器的步数检测，即通过预定的算法或方法对当前MEMS 加速度传感器在人体行走过程中所采集的数据进行计算识别，从而得出人体行走的步数。因此，步数检测算法的准确性，即用该算法计算出来的步数与实际步数之间的误差，是判断该算法优劣的首要因素。随着该领域研究的不断深入，除了步数检测算法的准确性以外，算法的自适应性、实时性等问题也得以突出，例如使步数检测算法能够自适应加速度传感器在人体的不同位置以及人体的多种行走方式等，其最终目的在于提高多种情况下步数检测算法的准确性，并且在某些应用场景下需要在短时间内产生计步结果。由此可见，目前该领域的研究要点主要集中在准确性、自适应性、实时性等方面。

在2002年，Ladetto 等人[2]在所设计的行人导航系统中提出可以利用加速度传感器检测行人步数，结合步长计算出人行走的距离。Jang等人[3]在2007年基于两轴MEMS加速度传感器实现了一种高鲁棒性步数检测算法。在最近几年，步数检测算法的研究发展迅速，国内外许多学者已经在该研究领域作出了贡献，涌现出了许多方法，主要包括步长周期识别法[1]、自相关性分析法 $[ 4 ^ { - 7 } ]$ 、峰值检测法 $[ 8 ^ { \sim } 1 8 ]$ 、模糊逻辑法[19]、零交叉检测法[20.21]、有限状态机法 $[ 2 2 ^ { - 2 4 ] }$ 、零速修正法 $[ 2 5 ^ { - } 2 7 ]$ 以及动态时间规整法[1,8]等。该领域的研究对于智能手机计步应用[28,29]、智能计步器的设计 $[ 3 0 ^ { - 3 2 } ]$ 、运动健康检测应用[33.34]、基于 PDR 的行人定位导航技术[35.36等方面的研究具有强力的推进作用。同时，随着智能手机以及移动智能终端设备的发展，该领域的应用也相应得到发展，已经有许多厂商，如Jawbone[37]和Apple[38]等，针对设备内部的MEMS加速度传感器进行与步数检测相关的应用开发，通过检测分析用户行走的步数，结合一系列健康指标，为用户提供健康性的指导。

# 1 步数检测算法的研究现状

如引言部分所述，步数检测算法是采用合适的算法对加速度传感器在人体行走过程中采集的数据进行计算来识别步数，其处理过程分为两个阶段：数据预处理阶段和步数检测验证阶段。本节将从上述两个阶段来分析步数检测算法的研究现状，并结合各个算法的特点进行优劣分析。

# 1.1数据预处理方法

对MEMS加速度传感器采集的数据进行预处理，还原数据的规律性，是步数检测算法的重要环节。以手机中的加速度传感器为例，在人体行走过程中，人握持手机的方式是随意的，因此，传感器采集的数据可能会呈现不规律的变化，即通常所说的带有噪声的数据。数据预处理的目的在于最大化减少原始数据的噪声，服务于后续步数检测算法对于步数的计算识别。

# 1.1.1合成加速度的计算

目前，普遍采用3轴MEMS加速度传感器来进行人体步行数据的采集，3轴分别为X轴、 $\mathrm { \Delta Y }$ 轴和Z轴，即三维的数据表示方式。可用如下的方程式计算出合成加速度：

$$
A _ { c } \left( t \right) = \sqrt { a _ { x } ^ { 2 } + a _ { y } ^ { 2 } + a _ { z } ^ { 2 } }
$$

其中： $\boldsymbol { a } _ { x }$ ， $\boldsymbol { a } _ { y }$ ， $\boldsymbol { a } _ { z }$ 分别表示X轴、Y轴、Z轴在t时刻的采样大小， $A _ { c }$ (t)合成加速度，其物理意义表示t时刻，该加速度传感器所测物体的瞬时加速度大小。

文献[6，7，9，16\~18，24，30，44]等采用了该方法对加速度数据进行预处理。研究表明，该方法计算简易，所占用的资源量较少。人体携带加速度传感器方式的随意性会导致三轴加速度方向与人的运动方向不一致，通过合成加速度的计算可以部分消除该因素产生的噪声[6]。

Tang等人[1]在研究一种自适应步数检测算法时，在计算合成加速度的基础上，利用重力计算出垂直加速度和水平加速度，研究表明，该方法进一步消除了原始数据中由加速度传感器的携带方式和人体行走习惯所产生的噪声，其计算垂直加速度和水平加速度的方法如下：

$$
g = \sqrt { g _ { x } ^ { 2 } + g _ { y } ^ { 2 } + g _ { z } ^ { 2 } }
$$

$$
a = \sqrt { a _ { x } ^ { 2 } + a _ { y } ^ { 2 } + a _ { z } ^ { 2 } }
$$

$$
a _ { \nu } = \frac { a _ { x } g _ { x } + a _ { y } g _ { y } + a _ { z } g _ { z } } { g }
$$

$$
a _ { \scriptscriptstyle h } = \sqrt { a ^ { 2 } - a _ { \scriptscriptstyle \nu } ^ { 2 } }
$$

式（2）中 $g _ { x }$ ， $g _ { y } , g _ { z }$ 分别表示X轴、Y轴和Z轴方向上的重力， $g$ 表示完整重力；式（3）中 $a _ { x }$ ， $a _ { y } , a _ { z }$ 分别表示X轴、Y 轴和Z轴方向上的加速度， $a$ 表示完整重力；式（4）中 $\boldsymbol { a } _ { \nu }$ 表示计算出的垂直加速度；式（5） $a _ { h }$ 表示计算出的水平加速度。

# 1.1.2坐标旋转的方法

Pan 等人[4在研究基于智能手机上的计步算法时提出以坐标旋转方法为基础的加速度数据预处理方法。该方法的特点在于对三个轴的数据进行分别处理，对于单轴数据的处理效果较好，但是计算代价相对于计算合成加速度较高。

假设三维平面上的一个点 $p ( x _ { p } , y _ { p } , z _ { p } )$ ,三维坐标原点位于该平面上。设该点到坐标原点的距离为 $L$ ，该点到原点的连线与Z轴夹角为 $\alpha _ { y }$ 。现先将该点沿着Y轴旋转 $\beta _ { y }$ 的角度后变成点 $p ^ { \prime } ( x _ { p } ^ { ' } , y _ { p } ^ { ' } , z _ { p } ^ { ' } )$ 。根据三角函数的定义，有以下一些关系：

$$
\left\{ \begin{array} { l l } { \displaystyle s i n ( \alpha _ { y } ) = \frac { x _ { p } } { L } , c o s ( \alpha _ { y } ) = \frac { z _ { p } } { L } } \\ { \displaystyle s i n ( \alpha _ { y } + \beta _ { y } ) = \frac { x _ { p } ^ { ' } } { L } , c o s ( \alpha _ { y } + \beta _ { y } ) = \frac { z _ { p } ^ { ' } } { L } } \end{array} \right.
$$

在式（6）的基础上，根据三角函数和的定律有如下数学关系：

$$
\left\{ \begin{array} { l l } { \displaystyle s i n ( \alpha _ { y } + \beta _ { y } ) = \frac { \dot { x _ { p } } } { L } = \frac { { x _ { p } } } { L } \times c o s ( \beta _ { y } ) + \frac { z _ { p } } { L } \times s i n ( \beta _ { y } ) } \\ { c o s ( \alpha _ { y } + \beta _ { y } ) = \frac { \dot { z _ { p } } } { L } = \frac { z _ { p } } { L } \times c o s ( \beta _ { y } ) - \frac { { x _ { p } } } { L } \times s i n ( \beta _ { y } ) } \end{array} \right.
$$

式(7)结合消除 $L$ 后，可以得出 $p ( x _ { p } , y _ { p } , z _ { p } )$ 与 $p ^ { \prime } ( x _ { p } ^ { ' } , y _ { p } ^ { ' } , z _ { p } ^ { ' } )$ 之间的关系如下：

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { \dot { x _ { p } } = x _ { p } \times c o s ( \beta _ { y } ) + z _ { p } \times s i n ( \beta _ { y } ) } \\ { \dot { y _ { p } } = y } \\ { \dot { z _ { p } } = - x _ { p } \times s i n ( \beta _ { y } ) + z _ { p } \times c o s ( \beta _ { y } ) } \end{array} \right. } \end{array}
$$

此时设点 $p ^ { \prime } ( x _ { p } ^ { ' } , y _ { p } ^ { ' } , z _ { p } ^ { ' } )$ 到原点的连线与Y轴夹角为 $\alpha _ { x }$ ，然后将点 $p ^ { \prime } ( x _ { p } ^ { ' } , y _ { p } ^ { ' } , z _ { p } ^ { ' } )$ 沿着 $\mathrm { ~ X ~ }$ 轴旋转 $\beta _ { x }$ 的角度后变成$p ^ { \prime } ( x _ { p } ^ { \prime } , y _ { p } ^ { \prime } , z _ { p } ^ { \prime } )$ ，同理，根据上述的三角函数关系，可以得出点$p ^ { \prime } ( x _ { p } ^ { ' } , y _ { p } ^ { ' } , z _ { p } ^ { ' } )$ 与 $p ^ { \prime \prime } ( x _ { p } ^ { " } , y _ { p } ^ { " } , z _ { p } ^ { " } )$ 之间的关系如下：

$$
\left\{ \begin{array} { l l } { \dot { x _ { p } ^ { - } } = \dot { x _ { p } } } \\ { \dot { y _ { p } ^ { - } } = \dot { y _ { p } ^ { ' } } \times c o s ( \beta _ { x } ~ ) \ – \dot { z _ { p } } \times s i n ( \beta _ { x } ~ ) } \\ { \ddot { z _ { p } ^ { - } } = \dot { y _ { p } ^ { ' } } \times s i n ( \beta _ { x } ~ ) \ – \dot { z _ { p } ^ { ' } } \times c o s ( \beta _ { x } ~ ) } \end{array} \right.
$$

结合式（8）（9）即可计算出点 $p ( x _ { p } , y _ { p } , z _ { p } )$ 变换成点$p ^ { \prime } ( x _ { p } ^ { " } , y _ { p } ^ { " } , z _ { p } ^ { " } )$ 所旋转的角度 $\beta _ { y }$ 和 $\beta _ { x }$ ，推广到该点所在平面，则$\beta _ { y }$ 和 $\beta _ { x }$ 也为该平面分别绕Y轴和 X轴旋转的角度，近似代替传感器此时相对于水平面的偏差程度，从而计算出此时加速度值的水平分量值，消除传感器平面处在非水平面时产生的噪声。

# 1.1.3滤波算法

在数据的预处理过程中，滤波算法的使用也比较常见。文献[6，12，15，18，24]等采用了卡尔曼滤波算法,文献[16，20,29，43]等则采用了均值法滤波，文献[5，9，40]等采用了巴特沃斯滤波，文献[36]采用了傅里叶变换滤波等等。

Tran 等人[15]以采用离散卡尔曼滤波算法所计算出的结果为基础，根据每一步的加速度数据呈现先增后减的特点提出新的滤波方法，该方法可以识别和标记加速度数据中对步数验证具有重要作用的加速度变化，所提出的滤波方法如下：

11 $\backslash { \mathrm { i . i f } } \left( P _ { i } - P _ { i - 1 } > T \right) t h e n \ Q _ { i } = Q _ { i - 1 } + K$   
2.if $\ \big ( P _ { i - 1 } - P _ { i } > T \big ) t h e n$ （20  
3.if $( Q _ { i - 1 } = 0 ) t h e n Q _ { i } = Q _ { m a x } ,$ (with $Q _ { m a x }$ is the maximunvalue of $\mathrm { ~ Q ~ }$ up to $Q _ { i - 1 } ^ { \phantom { - } }$ ）  
4. $\mathrm { i f } \left( Q _ { i - 1 } > 0 \right) t h e n \ : Q _ { i } = Q _ { i - 1 } - K$   
5. （204号 $\mathrm { i f } \left( Q _ { i - 1 } < 0 \right) t h e n \ : Q _ { i } = 0$   
$6 . \mathrm { i f } ( \left| Q _ { i - 1 } - Q _ { i } \right| < T ) t h e n ~ Q _ { i } = 0$

其中 $T$ 为阈值， $P$ 为经过卡尔曼滤波后的加速度信号， $\boldsymbol { \mathcal { Q } }$ 为采用上述滤波方法后的加速度信号。通过滤波算法，可以有效消除数据波形中的毛刺，使采集的样本数据能够更加平滑或者规律性更加明显，进一步消除数据中的噪声。通常情况下，为了获取良好的加速度数据，会采用计算合成加速度方法和滤波算法相结合的方法。

# 1.2步数检测和验证方法

步数检测研究领域中对步数进行识别的方法主要包括引言部分所述的方法，下面对这些方法进行简单介绍。

# 1.2.1自相关性分析法

自相关性分析法采用的是相关系数的理论基础，其数学形式化描述如下：

$$
\rho \left( m , t \right) = \frac { \sum _ { k = 0 } ^ { k = t - 1 } \left[ \left( a \left( m + k \right) - \mu \left( m , t \right) \right) \times \hphantom { \left( m + k \right) } \right] } { t \times \sigma \left( m , t \right) \times \sigma \left( m + t , t \right) }
$$

其中： $\mu ( m , t )$ 和 $\sigma ( m , t )$ 表示加速度序列$\{ a ( k ) , a ( k + 1 ) , \Lambda ~ , a ( k + t - 1 ) \}$ 的均值和标准差， $\textit { t }$ 为采样周期,$\rho ( m , t )$ 为相关系数，即计算两个周期 $t$ 内的加速度序列的相关系数。

Pan 等人[4的利用自相关性分析法的步数检测算法中，针对加速度传感器的Y轴和Z轴数据，采用了起始点检测的方法，在验证步数时并非以单步为单位进行验证，而是在2步或者4步的加速度序列之间进行相关系数的计算，获得了良好的步数检测结果。Soaz等人[5提出一种步数参数化的方法构建出步行数据模板，最后采用自相关性分析法行模板匹配以排除非真实步行数据产生的计步结果。陈国良等人[基于自相关性分析法在手机上实现了一种计步器功能，作者采用了一种加框计算的方法，在加框范围内以一个梯度进行相关系数的计算，直到计算出不小于预定阈值的相关系数值，才进行有效步的识别。Rai等人[7在实现一种室内定位系中，实现了一种基于自相关性的计步算法，通过给计算出的相关系数设定一个阈值来进行步数验证。

# 1.2.2峰值检测法

Jang 等人[3]提出人体在行走时所采集的水平加速度和垂直加速度可以被建模成具有正弦规律的数据波形，通过检测连续出现的波峰和波谷，可以进行步数识别。假设当前算法窗口大小为 $n$ ，窗口内的加速度序列$A ( n , t ) = \{ a ( k + 1 , t ) , a ( k + 2 , t ) , \Lambda ~ , a ( k + n , t ) \}$ ,则满足条件的加速度峰值 $a _ { p e a k }$ 可以表现为如下的形式：

$$
\begin{array} { c } { { \left\{ a _ { _ { p e a k } } = a \left( k + m , t \right) > a \left( k + i , t \right) \right.}  }  \\ { { \left. m < n a n d i \in \left[ 1 , m \right) \cup \left( m , n \right] \right. } } \end{array}
$$

由于人体在行走时会使加速度传感器产生抖动，导致数据存在噪声，在使用峰值检测法进行步数识别时，一般还会对数据进行滤波处理。

Tang等人提出一种基于自适应性峰值检测法的步数检测方法，该方法考虑多维度的参数，并且采用可调节的最优阈值，提高了峰值检测法的鲁棒性。Susi等人[9]采用了一种自适应峰值阈值的步数检测方法，改善了峰值检测法的自适应性。Yoneyama等人[10]从加速度数据中提取相关系数、加速度数据正负向的偏离程度等信息，基于这些信息提出一种新的峰值检测法来检测行人的步数。Lee等人[1提出一种基于形态学滤波器(morphologicalfilter,MF）的峰值检测法，该方法利用MF改变加速度数据的波形，进而将峰值特征明显化，从而提高峰值检测的准确性。Shin 等人[13]在运动识别的基础上，根据不同的运动方式设定不同的峰值检测法的阈值，提高了峰值检测对不同运动方式的自适应能力。Chon 等人[14提出了一个基于峰值检测法的步数检测算法，该方法在一系列加速度传感器测量值中确定多个局部峰值，利用均值和标准差消除可能的伪峰值并产生候选峰值，每一个候选峰值即表示人体行走了一步。王文杰等人[基于峰值检测算法提出加减分减分机制，该方法可以增强峰值检测法对伪波峰的处理能力。陈国良等人[17根据不同运动状态下具有不同加速度峰值这一特点，基于峰值检测法提出一种自适应多种运动方式的步数检测算法，提高了峰值检测法的自适应性。

# 1.2.3零速修正法

人体在行走过程中，在某一个时刻会出现脚与水平地面垂直的情况，此时人体的运动速度接近于零，利用该特点可以进行步数检测。在文献[25]中，作者通过在鞋子内部固定一个压力传感器来检测人体行走过程中的零速值，其计算零速值方法的数学程式如下：

$$
{ \boldsymbol { \overline { { \mathbf { \Lambda } } } } } \mathbf { \Lambda } _ { \nu } ^ { \otimes } ( \theta , t ) = { \frac { d r { \big ( } \theta , t { \big ) } } { d t } } \cdot { \hat { r } } \approx { \frac { r { \big ( } \theta , t + \Delta t { \big ) } - r { \big ( } \theta , t { \big ) } } { \Delta t } } \cdot { \hat { r } }
$$

$$
{ \mathfrak { P } } _ { c n t r } = \int _ { 0 } ^ { 2 \pi } { \overline { { \nu } } } { \left( \theta , t \right) } d \theta
$$

其中： $\underset { \nu } { \mathbf { u } }$ 为压力传感器等压线上某一点的速度， $\boldsymbol { r }$ 为该点半径，$\hat { r }$ 是等压线中心到该点方向上的单位向量。式（13）中 $\underset { \nu _ { c n t r } } { \mathbf { \omega } }$ 则是最后要计算的等压线中心点的速度值。

Lo 等人[26通过在小腿固定惯性传感器检测人体行走过程中的零速度。谷阳等人[27]提出一种粒子滤波框架下利用建筑物结构先验知识改进零速修正法的轨迹计算，提高了人员自主定位的精确度。

# 1.2.4动态时间规整法

动态时间规整算法是应用相对广泛的用于对比两个时间序列之间相似度的方法，该方法与自相关性分析法的区别在于自相关性分析法属于线性的方法，而该方法属于非线性的[8。假设存在采样的加速度序列 $A { \left( n , t \right) }$ 与 $B \big ( n , t \big )$ ·

$$
A ( n , t ) = \{ a ( 1 , t ) , a ( 2 , t ) , \Lambda ~ , a ( n , t ) \}
$$

$$
B ( n , t ) = \{ b ( 1 , t ) , b ( 2 , t ) , \Lambda \ , b ( n , t ) \}
$$

动态时间规整算法需要计算出 $A { \left( n , t \right) }$ 与 $B { \left( n , t \right) }$ 之间的距离 $d i s t [ A , B ]$ 来确定两个序列的相似度，而该距离一般为欧式距离：

$$
d i s t \big [ A , B \big ] = \sqrt { \sum _ { k = 1 } ^ { k = n } \bigl ( b \bigl ( k , t \bigr ) - a \bigl ( k , t \bigr ) \bigr ) ^ { 2 } }
$$

Tang等人[1提出一种自适应的基于动态时间规整的步数检测算法，在匹配验证时采用动态变化的步行模板，提高了基于动态时间规整法的步数检测算法的自适应性。Brajdic 等人[8基于动态时间规整算法实现了一个步数检测算法用于和其他步数检测算法进行对比。

# 1.2.5零交叉检测法

人体在行走过程中会出现加速度大小为零的情况，该特征可以用来进行步数检测。

Seo 等人[20]基于该方法，利用人体在行走过程中会出现加速度大小为零的特点，构建步数与零加速度值次数之间的线性规律。在实际操作时，通过检测加速度值为零的次数来检测出有效的步数。同时，作者提出的一种改进的零交叉检测技术（AZDC)，该方法如下：

$$
A D Z C R a n g e = \pm c ^ { * } S T D _ { r e s t }
$$

其中： $\mathbf { \Psi } _ { c }$ 为常量， $S T D _ { r e s t }$ 为静止时加速度序列的标准差。由于采样的加速度数据存在噪声，通过设定该界限，只有由该界限外的加速度产生的零交叉情况才会被记为一次有效的零交叉，有效降低了噪声对零交叉检测的影响。

Shin 等人[2I]通过检测合成加速度在人体行走过程中出现零值的次数进行步数检测，实现了一个简单的零交叉计步方法。

# 1.2.6步长周期识别法

Tang 等人[1]基于峰值检测法只关注峰值的单一性限制以及自适应差等的问题，提出步长周期识别算法。该方法在计算两个加速度序列的相似度时，考虑了两个序列之间的垂直加速度的相似度、水平加速度峰值之间的相似度以及传感器方向角的重叠程度。其计算垂直加速度相似度时，方法如下：

$$
\begin{array} { l } { d _ { a _ { v } } = \left( S \left[ x \right] . a _ { v } , T \left[ y \right] . a _ { v } \right) = } \\ { \left\{ \begin{array} { l l } { \alpha \cdot \sqrt { 2 } \cdot \left| S \left[ x \right] . a _ { v } - T \left[ y \right] . a _ { v } \right| , i f } & { S \left[ x \right] . a _ { v } \cdot T \left[ y \right] . a _ { v } < 0 } \\ { \displaystyle \frac { \alpha } { 2 } \cdot \frac { \left| S \left[ x \right] . a _ { v } - T \left[ y \right] . a _ { v } \right| } { \sqrt { m a x } \left\{ \frac { 1 } { 2 } , m i n \left\{ \left| S \left[ x \right] . a _ { v } \right| , \left| T \left[ y \right] . a _ { v } \right| \right\} \right\} } , o t h e r w i s e } \end{array} \right. } \end{array}
$$

其中： $s [ x ]$ 和 $T [ y ]$ 分别为两步的加速度序列采样值， $d _ { a _ { \nu } }$ 则为某时刻 $S \big [ x \big ]$ 和 $T [ y ]$ 中两个加速度值之间的距离。在计算水平加速度序列相似度时，方法如下：

$$
d _ { \operatorname* { m a x } \{ a _ { h } \} } \left( S \right) = 4 \cdot m a x ^ { 2 } \left\{ 0 , 5 - m a x \big \{ S \big [ x \big ] . a _ { h } \big \} \right\}
$$

$$
d _ { \operatorname* { m a x } \{ a _ { h } \} } \left( S , T \right) = \frac { \left| \operatorname* { m a x } \left\{ S \left[ x \right] . a _ { h } \right\} - \operatorname* { m a x } \left\{ T \left[ y \right] . a _ { h } \right\} \right| } { 4 \cdot \sqrt { \operatorname* { m i n } \left\{ \operatorname* { m a x } \left\{ S \left[ x \right] . a _ { h } \right\} , \operatorname* { m a x } \left\{ T \left[ y \right] . a _ { h } \right\} \right\} } }
$$

$$
d _ { \operatorname* { m i n } \{ a _ { h } \} } \left( S \right) = m a x ^ { 2 } \left\{ 0 , \operatorname* { m i n } \left\{ S \left[ x \right] . a _ { h } \right\} - 5 \right\}
$$

$$
d i s t ( S , T ) = d _ { \operatorname* { m a x } \{ a _ { h } \} } \left( S \right) + d _ { \operatorname* { m a x } \{ a _ { h } \} } ( T ) +
$$

$$
d _ { \operatorname* { m a x } \{ a _ { h } \} } ( S , T ) + d _ { \operatorname* { m i n } \{ a _ { h } \} } ( S ) + d _ { \operatorname* { m i n } \{ a _ { h } \} } ( T )
$$

其中： $d i s t ( S , T )$ 即为序列 $s [ x ]$ 和 $T [ y ]$ 的水平加速度的距离。与动态时间规整算法明显的不同的是，在进行距离计算时，不再是简单计算欧式距离。作者通过缩小搜索空间的方式降低了算法的时间复杂度，以保证算法的执行效率。

# 1.2.7有限状态机法

该方法根据每一步加速度数据的大小先达到一个波峰后降至一个波谷的特点，将其划分为多种状态，然后设定一些状态转换条件将这些状态组合成一个有限状态机。通过转换状态条件，对输入的3轴加速度数据进行判断，确定当前加速度所处于的状态来进行步数检测。

Alzantot等人[22]依据加速度的大小特点，将人体行走一步的加速度数据分为六种状态。这些状态从S0到S6分别是：非走动状态、开始走一步状态、波峰状态、波谷状态、两个噪声容纳状态和一步终止状态。每个状态之间通过设定的阈值进行转换，状态间的转换如图1所示，其中阈值的定义如表1所示[22]。

![](images/8a636a4e5ba3820ce10abdac9a4042ee5f7d7d9cd9ad0465250f293d740b1b6c.jpg)  
图1状态转换过程

表1状态机中的阈值  

<html><body><table><tr><td>阈值名</td><td>Thr</td><td>Pos_Peak_Thr</td><td>Neg_Peak_Thr</td><td>Neg_Thr</td></tr><tr><td>值</td><td>0.6</td><td>1.8</td><td>-1</td><td>-0.6</td></tr></table></body></html>

Yim 等人[23]在文献[18]中六种状态的基础上，又添加一个噪声处理的状态，使得该方法对噪声的处理更加良好。王革超等人[24提出的加速度差分有限状态机计步算法，加入了数据预处理的过程，在数据预处理阶段对数据的噪声进行处理，而不需要在状态机中加入噪声屏蔽状态，简化了状态转换过程，提高了步数验证的效率。

# 1.2.8模糊逻辑法

Kammoun 等人[19]提出了基于该方法的步数检测方法。该方法将去除重力的加速度信号分为多个片段，每一个片段即为一个候选步数，并利用模糊分类器来验证候选片段是否为有效步数。其中去除重力的方法如下：

$$
a _ { scriptscriptstyle B P } [ n ] = a _ { \scriptscriptstyle L P } [ n ] - g
$$

其中: $a _ { \scriptscriptstyle L P } \big [ n \big ]$ 表示经过低通滤波后的加速度序列， $a _ { \scriptscriptstyle B P } \left[ n \right]$ 则表示去除重力后的加速度序列。基于筛选出的候选片段，计算出如表2所示的 $f _ { 1 } \sim f _ { 4 }$ 这四个特征[19]。

表2中 $X _ { k }$ 即表示一个加速度序列片段， $t _ { 0 }$ 表示该片段中第一个加速度所对应的采样时间，此时加速度递增趋向于正阈值， $t _ { 1 }$ 表示 $X _ { k }$ 中加速度递减过程中经过零点或等于零的加速度所对应的采样时间， $t _ { 2 }$ 表示 $X _ { k }$ 中最后一个加速度值所对应的采样时间，此时 $X _ { k }$ 中的加速度大小重新趋向于正阈值。$A m p ( k )$ 表示 $X _ { k }$ 中最大加速度与最小加速度的差值，即 $X _ { k }$ 的幅度， $\sigma _ { s t e p } ^ { 2 } \left( k \right)$ 即为 $X _ { k }$ 片段的方差。

表2模糊逻辑法特征列表  

<html><body><table><tr><td colspan="2">特征名</td><td>表达式</td></tr><tr><td>f</td><td>Step Duration</td><td>Tstep(k)=t2(k)-t0(k)</td></tr><tr><td>f</td><td>Duty Cycle</td><td>duty(k)=(t(k)-t(k))/Tstep (k)</td></tr><tr><td>f</td><td>Acc-Amplitude</td><td>Amp(k)= max(Xk)-min(X )</td></tr><tr><td>f4</td><td>Acc-Var</td><td>δstep(k)=(1/nk)∑(x-mean(Xx))²</td></tr></table></body></html>

基于抽取的四个特征，计算特征之间的隶属度，并以向量$d _ { k }$ 表示：

$$
\boldsymbol { d } _ { k } = \left[ D _ { 1 } ( f _ { 1 } ) , . . . , D _ { P } ( f _ { P } ) \right] ^ { T }
$$

其中： $P$ 表示特征总数， $D _ { i }$ 表示隶属函数，作者采用的是以下高斯隶属函数：

$$
D _ { i } \left( x \right) = e ^ { \frac { - \left( x - \mu _ { i } \right) ^ { 2 } } { 2 \sigma _ { i } ^ { 2 } } }
$$

根据 $d _ { k }$ 和四个特征，作者提出以下一些逆模糊化规则进行步数验证：

Rule1:IF （204号 $( T _ { s t e p } \left( k \right) < T _ { m i n } )$ OR $( T _ { s t e p } \left( k \right) > T _ { m a x } )$ （20 $( A m p \big ( k \big ) < \mathfrak { A } _ { m i n } ) \ \Rightarrow \ y _ { k } = - 1$

Rule 2: IF $\left( T _ { m i n } \leq T _ { s t e p } \left( k \right) \leq T _ { m a x } \right) \quad \mathrm { ~ A N D ~ } \quad \operatorname* { m i n } \left( d _ { k } \right) \geq \mathcal { X } \quad \Rightarrow$

$$
y _ { k } = + 1
$$

Rule3:IF $\left( T _ { m i n } \leq T _ { s t e p } \left( k \right) \leq T _ { m a x } \right)$ AND （20 $\operatorname* { m i n } \left( d _ { k } \right) \leq \beta$ → y=-1

Rule 4: IF rule1 AND rule2 AND rule3 THEN $y _ { k } = 0$

Rule5:IF $y _ { k } = + 1 { \bigl ( } \mathbf { r e s p . } y _ { k } = - 1 { \bigr ) }$ AND $y _ { k - i } = 0$ $\mid \Rightarrow$ $y _ { k - i } = + 1 \big ( \mathrm { r e s p . } y _ { k } = - 1 \big )$

上述规则中 $T _ { m i n }$ ， $T _ { m a x }$ ， $A _ { m i n }$ 以及 $\alpha , \beta$ 为预先设定的阈值,$y _ { k } = + 1$ 表示 $d _ { k }$ 向量代表一步， $y _ { k } = - 1$ 表示 $d _ { k }$ 向量不能代表一步， $y _ { k } = 0$ 表示不确定 $d _ { k }$ 是否代表一步。

# 1.3步数检测和验证方法优缺点分析

正如引言部分所述，步数检测算法的应用领域具有多样性，针对不同的应用情况，所需要采集和使用的数据以及数据预处理的方法会有所不同。另外，传感器数据本身具有时序性的特点，即使对同一个人同一种情况也会采集到不同的数据，目前还不存在一个标准化的数据样本可供研究，这是目前步数检测算法研究领域中存在的一个难点，也是笔者目前正在努力研究的一个方向。因此，在没有标准化参考指标的情况下，对于各类步数检测算法的优劣性分析可以从算法的自适应性、各自应用场景下的步数检测的准确性以及计步的实时性等方面进行分析。综合上述对各个方法的阐述和表3中的优缺点分析，可以总结出以下几点内容：

a)基于零交叉检测和峰值检测的步数检测方法实现方式简单，消耗的资源少。但是峰值检测法的检测结果的准确性依赖于窗口大小的选取[。除此以外，合理的阈值设定对峰值检测法也至关重要[10]。零交叉检测法则会因为多检测或少检测零交叉点的情况而使检测结果的准确性不高。

b)基于零速修正法的步数检测方法利用人体行走过程中腿与地面垂直时出现瞬时速度为零这一自然的现象，使得步数检结果在准确性上表现很好，但是由于其对传感器固定位置的依赖性，导致该方法的实用性不强。

c)基于自相关性分析、动态时间规整以及步长周期识别方法利用了同种运动下每个周期的加速度序列呈现相似性这一特征，使得这一类方法准确性较高，并且具有一定的自适应性，但是其所需的计算资源相对较高，其算法的时间复杂度达到了$O \big ( n ^ { 2 } \big )$ 。同时，步长周期的动态变化也是影响该方法检测结果准确性的重要因素[34]。

d)有限状态机法克服了峰值检测法中只关注峰值与阈值关系的缺点，将峰值和谷值设定为一种状态，更加关注加速度数据的变化情况。但是由于其状态转换阈值的固定化以及不考虑周期性特征，导致该方法自适应性较差，一般情况下，该方法对正弦波规律良好的加速度数据具有较好的处理能力[35]。

e)基于模糊逻辑法的步数检测方法由于采用多种特征作为依据，使得该方法的步数检测结果的准确性较高。但是，由于该方法的阈值相对固定，导致其自适应性较差。

# 2 步数检测算法研究要点分析

# 2.1步数检测算法的准确性

准确性是步数检测算法的优劣的首要标准。目前，为了确保步数检测的准确性，对数数据的预处理是一种常用的方法，如前面所述计算合成加速度、使用滤波算法以及其他的处理方

法等。

除了对加速度数据进行预处理以外，除了对加速度数据进行预处理以外，对加速度数据所属的运动状态、步态进行分类分析以及排除异常的步数检测也是提高步数检测算法准确性的有效方法。

表3步数检测和验证方法的优缺点分析  

<html><body><table><tr><td rowspan="2">步数检测和 验证方法</td><td colspan="3">对比指标</td></tr><tr><td>准确性</td><td>自适应性</td><td>实时性</td></tr><tr><td rowspan="2">自相关性分析法</td><td>利用步行数据的周期性相似的规律，具有较准确步</td><td>对于步长周期有一定的自适应性，对于传</td><td>实时性次于峰值检测法，可</td></tr><tr><td>数检测结果，但是容易受到类步行数据的干扰</td><td>感器位置和连续复杂运动的自适应较差</td><td>用于非实时性分析</td></tr><tr><td rowspan="2">峰值检测法</td><td>对于简单步行运动的步数检测结果较准确，所消耗</td><td>对步长周期的变化、传感器位置变化、连</td><td>实时性好，</td></tr><tr><td>的资源相对少，易受到伪波峰和周期的变化影响</td><td>续复杂运动的自适应性较差</td><td>可用于非实时性分析</td></tr><tr><td>零速修正法</td><td>具有相对较高的步数检测准确性</td><td>需要在人体固定部位，例如腿部、脚部等 固定加速度传感器</td><td>实时性好， 可用于非实时性分析</td></tr><tr><td rowspan="2">动态时间规整法</td><td>与自相关性分析法类似，</td><td></td><td>实时性次于峰值检测法，可</td></tr><tr><td>只是计算序列的相似度方法有所不同</td><td>与自相关性分析法类似</td><td>用于非实时性分析</td></tr><tr><td rowspan="2">零交叉检测法</td><td>对于简单步行的检测效果较好，</td><td>对于传感器放置位置、</td><td></td></tr><tr><td>易实现，易受到“伪零交叉点”的干扰</td><td>复杂运动状态的自适应较差</td><td>更适合非实时性分析</td></tr><tr><td rowspan="2">步长周期识别法</td><td>将部分历史数据的特征作为参考，步数检测的准确</td><td>对步长周期自适应型好，对于传感器位置</td><td>实时性相对较差，可用于非</td></tr><tr><td>性较高，但是计算的资源消耗较多</td><td>和连续复杂运动的自适应较差</td><td>实时性分析</td></tr><tr><td rowspan="2">有限状态机法</td><td>对正弦规律的加速度数据的处理效果较好，</td><td>对于步长周期、传感器位置和连续复杂运</td><td>可用于实时性和</td></tr><tr><td>容易受到步行周期的变化的干扰</td><td>动的自适应较差</td><td></td></tr><tr><td rowspan="2">模糊逻辑法</td><td>考虑加速度数据多种特征作，</td><td>对于传感器位置、</td><td>非实时性分析</td></tr><tr><td>对简单步行运动的检测准确</td><td>连续复杂运动的自适应较差</td><td>实时性次于峰值检测法，可 用于非实时性分析</td></tr></table></body></html>

Soaz等人[5]利用K-means聚类方法对正常步态和缓慢步态这两类步态模型进行分类，在此分类基础上，采用模板匹配的方式进行步数检测，匹配时采用的是相关性分析方法，有效提高了基于自相关性分析法的步数检测算法的准确性和可靠性。

Susi 等人[指出当传感器在人体的手中时，加速度数据的特征会随着不同的携带方式而出现变化，在这种情况下进行步数检测将更为复杂，因此设计一种针对复杂运动方式下的步态分析方法，并在此基础上进行步数检测，将会有效提高检测结果的准确性。

Shin 等人[13]在研究基于运动识别的行人导航系统中提出一种采用人工神经网络进行多种运动识别的方法，实验结果表明，该方法能有效识别静止、跑步、行走等6种运动状态。

Delgado-Gonzalo 等人[33]提出一种基于二叉分类树的运动方式识别方法，通过提取加速度数据中信号长度、规律性以及频率稳定性三种特征作为分类的基础特征，在此基础上利用步频的规律性进行步数验证。对于频率规律性不良好的加速度数据则进行时域的分析，从信号的周期、强度、波形等方面进行步数验证。

Wang等人[41]提出一种基于小波变换的实时步态进行分析识别的方法，该方法对采用小波变换处理后的信号进行特征提取，并运用多种机器学习方法进行分类识别，实验证明该利用该方法所设计的步态分类系统实时性较好，分类的准确性较高。

Karantonis等人[42]提出一种基于三轴加速度计的非临床条件下的人体运动检测方法。该方法采用SMA、加速度峰值、SVM以及计算出的人体姿态角度等少量信息实现了人体坐立、站立、躺卧等状态的分类识别。该方法在能耗、功耗、实时性需求的条件限制下，达到了较好的运动状态分类效果。

Das 等人[43]利用安卓手机中的加速度传感器进行人体多种运动方式的检测。该方法采用了线上匹配和线下分类的方式进行运动识别，线上匹配是已知模板和采集样本之间的匹配，线下分类则利用朴素贝叶斯分类器根据提取的频率、加速度均值、最大幅度和最小幅度这四个特征进行分类。实验结果表明，该方法对运动方式的识别准确度较高，但是对加速度传感器器的位置具有较强的依赖性，即自适应性较差。

卢先领等人[44]提出一种基于隐马尔可夫模型的人体跌倒状态的检测方法。该方法利用日常活动产生的加速度数据训练出HMM模型，降低了由于跌倒这一状态的低频性而导致的模型训练过程的复杂性，最终在HMM模型输出结果的基础上利用倾角信息来增强跌倒检测的准确性。实验表明，该方法对于人体跌倒运动的检测结果具有较高的准确性。

李月香等人[45提出一种行走模式分类的方法，该方法从加速度信号的时频特征中提取三个特征，从时域特征中提取两个特征，结合频域中的步频特征实现行走模式的多级分类。实验表明该方法通过少量特征的提取，即可实现上、下楼梯和水平行走这三种行走模式的有效识别。

Yao 等人[46]提出一种基于单类支持向量机的异常步数检测的方法。该方法针对以往步数检测算法和计步设备中存在误将抖动、摇晃等情况检测为有效步数的缺陷，从加速度数据中提取出13个非方向性的特征，以这13个特征作为输入，输出结果用于判断该输入数据是否为异常状态下的数据，实验结果表明该方法能够有效检测出异常状态下的步数检测结果。

从上述研究中发现，数据预处理在一定程度上消除了数据的噪声，通过对运动检测分类、步态分析和除异常步数检测等方法，可以更好地判断当前行人是否处于运动状态以及排除异常检测结果，需要解决的关键性问题是要结合步数检测的应用场景、设备运行资源以及实时性需求等多方面因素来选取和应用相应的运动分类识别方法。以基于自相关性分析法为例，由于其过于关注数据间的相似度，而不关心数据是否由人的正常步行产生，检测的结果很容易受到干扰，因此在检测前对加速度数据进行步行检测或步态分析，可以很大程度上确保步数检测结果的准确性和可靠性。

# 2.2步数检测算法的自适应性

随着步数检测算法研究的深入，近几年步数检测算法的自适应性得到国内外学者的重视。在实际的应用中，人的行走方式和携带传感器的方式是多变的且不可预测的，如何使算法更好地适应这些状况是一个值得研究的重要方面。

Tang等人[提出的一种自适应峰值检测算法，该方法将垂直加速度、水平加速度、传感器的旋转角度、步频和步长等多维度的数据作为步数检测的参数，在每一步被验证后即调整参数的最优阈值，并且将初始化最优阈值作为基本依据来预防步数检测过程中出现不符合实际的阈值的情况。该方法通过多维度参数和可变参数最优值有效提高了基于峰值检测的步数检测算法对多种运动方式的自适应性。

Pan等人[4采用基于坐标旋转的方法对数据进行预处理，通过获取加速度数据的水平分量值得方法，很大程度上消除因人体握持手机方式的随意性而产生的数据噪声，实验证明该数据预处理方法提高了基于自相关性分析的步数检测算法对多种加速度传感器携带方式的自适应性。

Ryu等人[10]设计了一种自适应方步数检测算法，该方法针对以往步数检测算法中采取单一阈值的缺点，设计了一种可变阈值的算法，该方法将加速度数据变化的幅度作为一种因素，可变阈值则根据历史数据的幅度来更新，提高了基于峰值检测的步数检测算法的自适应性。

陈国良等人[17]提出了一种自适应波峰检测的步数检测算法，该方法根据人体在不同运动方式下加速度数据峰值大小范围不同的特点，设定多个固定的峰值阈值。该方法以峰值检测法为基础，提高了峰值检测对人体多种运动方式的自适应性。

从上述的研究中发现，步数检测算法的自适应性问题研究可以从两方面进行，即对数据预处理方法和步数检测和验证方法的改进创新。通过合理的数据预处理，可以初步地有效减少加速度数据因传感器抖动、传感器方向与行走方向不一致、行走方式的多样性等产生的噪声，充分还原加速度数据的规律性，提高算法对这些因素的自适应性。对步数检测验证方法的改进创新，例如设定可变阈值、采用新的数学模型等，通过克服已有方法的低自适应性等缺点，进一步提高步数检测算法在多种环境下的准确性。

# 2.3步数检测算法的实时性

在实际的应用中，步数检测算法的实时性也很重要。人体步行频率范围为 $1 { \sim } 2 . 5 ~ \mathrm { H z }$ ，即步行的周期范围大概在0.4\~1 s[6]。因此，步数检测算法理论上应在1s左右即可产生步数识别的结果。由于算法的复杂度以及硬件资源的限制等原因，使得步数检测算法的实时性要求具有一定挑战性。在一些情况下，为了保证步数检测结果的准确性，也会牺牲一些时间上的代价。

Tang 等人[1指出其设计的步长周期识别算法在步数检测时存在滞后性，原因是在验证当前加速度数据时，会将该数据与之后的几步数据进行相似度比较，只有对比结果满足阈值条件后，才会产生当前加速度数据的步数检测结果。这种情况即以牺牲时间为代价来确保步数检测结果的准确性。

Oshin等人[39]基于智能手机设计了一种节能的实时步数检测算法，该方法对加速度数据不进行滤波和降噪的处理，从而节约了滤波和降噪方法的时空消耗。该方法以低采样频率的方式节省了手机的能耗，通过从加速度数据中提取5个特征以及对特征设定阈值的方式，来进行步数检测。实验表明该方法可以在2s以内产生步数检测的结果。

# 3 结束语

基于MEMS加速度传感器的步数检测算法具有广泛的应用场景。步数检测算法的研究主要包括数据采集处理、步数检测和验证算法的设计这两个阶段，其中以准确性作为算法优劣的首要衡量标准，以自适应性作为增强准确性的保障，在确保算法高准确性的前提下，尽量满足步数检测的实时性要求。未来对该领域的研究方向集中在以下几个方面：

a)步数检测方法的改进和创新。目前已有的许多步数检测算法在准确性、自适应性和实时性等方面还存在很多缺陷，例如采用固定的阈值、依赖传感器的携带方式、不适用于低速行走状态下的步数检测、检测结果存在时延的情况等等。在后续的步数检测方法研究工作中，可以对步数检测算法的自适应性和实时性等方面进行改善，一方面，使算法能够满足自适应传感器的携带方式、行走的姿态，以及动态调整最优值等需求，另一方面，针对实时性的需求，研究对应的数据预处理方法和步数验证方法等。

b)步数检测方法与动作检测方法的结合。对人体一系列正常的活动或运动进行检测分类，例如跑步、行走、上下楼梯、静止站立、跳跃等，在此基础上进行步数检测，可以有效过滤非正常步行所产生的数据，同时可以针对不同的动作检测结果动态调整算法最优值，进一步增强步数检测算法的自适应性，提高检测结果的准确性。

c)基于步数检测算法的多样化应用的开发。例如：a)高精确度的室内定位导航系统的开发，包括对室内的行人进行路径追踪、为行人提供可靠的导航建议等功能；b)健康类应用的开发，包括基于智能手机的健康监测APP、基于智能穿戴设备的计步功能等。与此同时，将海量的计步数据与智能穿戴设备或健康监测APP所采集的部分个人特征数据（例如性别、身高、年龄、职业等）结合并进行统计和分析，可以进一步理解用户的行为习惯、分析用户的健康程度、预测分析新用户的个人特征等，根据分析结果进行相应的应用开发。

# 参考文献：

[1]Tang Z, Guo Y, Chen X. Self-adaptive step counting on smartphones under unrestricted stepping modes [C]// Proc of IEEE Computer Software and Applications Conference.2016: 788-797.   
[2]Ladetto Q,Merminod B.In step with INS[J].Gps World,2002 (3): 259   
[3]Jang HJ,Kim JW,Hwang D H.Robust step detection method for pedestrian navigation systems [J].Electronics Letters,2007,43 (14): 749-751.   
[4]Pan M S,Lin H W.A step counting algorithm for smartphone users: design and implementation [J].IEEE Sensors Journal,2015,15 (4): 2296-2305.   
[5]Soaz C,Diepold K. Step detection and parameterization for gait assessment using a single waist-worn acceler-ometer [J]. IEEE Trans on Biomedical Engineering,2016,63 (5): 933-942.   
[6]陈国良，张言哲，杨洲．一种基于手机传感器自相关分析的计步器实现 方法[J]．中国惯性技术学报,2014,22(6).   
[7]Rai A,Chintalapudi K K,Padmanabhan V N,et al. Zee:zero-effort crowdsourcing for indoor localization [C]// Proc of the 18th Annual International Conference on Mobile Computing and Networking.2012: 293- 304.   
[8]Brajdic A,Harle R.Walk detection and step counting on unconstrained smartphones [C]//Proc of ACM International Joint Conference on Pervasive and Ubiquitous Computing.2013: 225-234.   
[9] Susi M, Renaudin V, Lachapelle G. Motion mode recognition and step detection algorithms for mobile phone users [J].Sensors,2013,13 (2): 1539- 62.   
[10] Yoneyama M, Kurihara Y,Watanabe K,et al. Accelerometry-based gait analysis and its application to Parkinson's disease assessment,part 1: detection of stride event [J]. IEEE Trans on Neural Systems & Rehabilitation Engineering,2014,22 (3):613.   
[11] Lee HK, You J, Cho S P,et al. Computational methods to detect step events for normal and pathological gait evaluation using accelerometer [J]. Electronics Letters,2010,46(17):1185-1187.   
[13] Shin B,Kim C,Kim J,et al.Motion recognition-based 3D pedestrian navigation system using smartphone [J]. IEEE Sensors Journal,2016,16 (18): 6977-6989.   
[14] Chon J, Cha H.LifeMap:a smartphone-based context provider for location based services [J]. IEEE Pervasive Computing,2011,10 (2): 58-67.   
[15] Tran K,Le T,Dinh T.A high-accuracy step counting algorithm for iPhones using accelerometer [C]/ Proc of IEEE International Symposium on Signal Processing and Information Technology.2012: 000213-000217.   
[16]王文杰，李军．基于手机加速度传感器的计步算法设计[J].工业控制 计算机,2016,(01):75-76+79.   
[17]陈国良，李飞，张言哲．一种基于自适应波峰检测的 MEMS 计步算法 [J]．中国惯性技术学报,2015(3):315-321.   
[18]梁久祯，朱向军，陈璟．基于手机加速度传感器的高精低采样计步算法 设计[J].西北大学学报：自然科学版,2015,45(5):738-744.   
[19] Kammoun S,PothinJB,CousinJC.An efficient fuzzy logic step detection algorithm forunconstrainedsmartphones [C]// Proc of International Symposium on Personal, Indoor,and Mobile Radio Communications.2015: 2110-2114.   
[20]SeoJ, ChiangY,Laine TH,etal.Stepcountingonsmartphonesusing advanced zero-crossing and linear regression [C]// Proc of the 9th International Conference on Ubiquitous Information Management and Communication 2015: Article No.106.   
[21] Shin SH,Park CG,KimJW,et al.Adaptive step length estimation algorithm using low-cost MEMS inertial sensors [Cl//Proc ofIEEE Sensors Applications Symposium.Washington DC:IEEE Computer Society,2007: 1-5.   
[22] Alzantot M,Youssef M.UPTIME:ubiquitous pedestrian tracking using mobile phones [C]// Proc of Wireless Communications and NETWORKING Conference. 2012: 3204-3209.   
[23] Yim J.A smartphone indoor positioning method [J]. International Journal of Smart Home,2013,7(5): 9-18.   
[24]王革超，梁久祯，陈璟，等．加速度差分有限状态机计步算法[J].计 算机科学与探索,2016,10(8):1133-1142.   
[25] Bebek O,Suster MA,Rajgopal S,et al. Personal navigation via shoe mounted inertial measurement units [C]//Proc of IEEE//RSJ International Conference on Intelligent Robots and Systems.2010: 1052-1058.   
[26] Lo C C, Chiu C P, Tseng YC, et al. A walking velocity update technique for pedestrian dead-reckoning applications[C]//Procof International Symposium on Personal, Indoor and Mobile Radio Communications.2011: 1249-1253.   
[27]谷阳，宋千，李杨寰，等．基于惯性鞋载传感器的人员自主定位粒子滤 波方法[J].电子与信息学报,2015,37(2):484-488.   
[28] Naqvi MN Z,Kumar A, Chauhan A,et al. Step counting using smartphonebased accelerometer[J]. International Journal on Computer Science &

Engineering,2012,4(5): 6/5-681.   
[29]马松岩．基于iOS平台的计步器应用的设计与实现[J]．软件,2012,33 (12): 66-68.   
[30]Ryu UJ,Ahn K,Kim E,etal.Adaptive step detection algorithm for wireless smart step counter [C]//Proc of International Conference on Information Science and Applications.2013:1-4.   
[31]韩文正，冯迪，李鹏，等．基于加速度传感器LIS3DH的计步器设计[J]. 传感器与微系统,2012,31(11):97-99.   
[32]宋浩然，廖文帅，赵一鸣．基于加速度传感器 ADXL330 的高精度计步 器[J].传感技术学报,2006,19(4):1005-1008.   
[33]Delgado-Gonzalo R,Celka P,Renevey P,et al.Physical activity profiling: Activity-specific step counting and energy expenditure models using 3D wrist acceleration [C]//Proc of the 37th Annual International Conference of Engineering in Medicine and Biology Society.2015: 8091.   
[34] Jr D R B,Wyatt H R,Thompson H,et al.Pedometer-measured physical activity and health behaviors in united states adults [J].Medicine& Science in Sports& Exercise,2010,42(10):1819.   
[35] Ladetto Q. On Foot navigation: continuous step calibration using both complementary recursive prediction and adaptive Kalman filtering [J]. Ion Gps Salt Lake City Utah Usa,2000:1735-1740.   
[36]宋敏，申闫春．室内定位航位推测算法的研究与实现[J].计算机工程, 2013,39 (7): 293-297.   
[37] Jawbone. JAWBONE introduces UP3 [EB/OL]. (2014-11-5)[2017-8-25]. http://content.jawbone.com/static/www/pdf/press-releases/jawboneintroduces-up3. pdf.   
[38] Apple.Apple watch series 3: technical specifications [EB/OL].(2017-09-13) 0 [2017-09-30].https://support.apple.com/kb/SP766?viewlocale=en_US &locale=zh_CN.   
[39] Oshin T O,Poslad S.ERSP:An Energy-Efficient Real-Time Smartphone Pedometer [C]//Proc of IEEE International Conference on Systems,Man, and Cybernetics.2013:2067-2072.   
[40] Jayalath S,Nimsiri A,Murray I.A Gyroscope based Accurate Pedometer Algorithm [C]//Proc of International Conference on Indoor Positioning and Indoor Navigation.2013.   
[41] Wang JH,Ding JJ,Chen Y,et al.Real time accel-erometer-based gait recognition using adaptive windowed wavelet transforms [C]// Circuits and Systems.2012: 591-594.   
[42] Karantonis DM,Narayanan MR,Mathie M,et al. Implementation of a realtime human movement classifier using a triaxial accelerometer for ambulatory monitoring [J].IEEE Trans on Information Technology in Biomedicine,2006,10(1): 156.   
[43] Das S,Green L,et al. Detecting user activities using the accelerometer on Android smartphones [EB/OL].(2010-07-30)[2017-05-20]. https://www. truststc.org/education/reu/10/Papers/DasGreenPerezMurphy_Paper. pdf.   
[44]卢先领，王洪斌，王莹莹，等．一种基于加速度传感器的人体跌倒识别 方法[J].计算机应用研究,2013,30(4):1109-1111.   
[45]李月香，刘燕，袁涛，等．基于加速度信号的走路模式多级分类算法 [J]．电子学报,2009,37(8):1794-1798.   
[46] Yao Z J, Zhang ZP,Xu L Q.An Effective Algorithm to Detect Abnormal Step Counting Based on One-Class SVM[C]//Proc of IEEE International Conference on Computational Science and Engineering.Washington DC: IEEE Computer Society,2014: 964-969.