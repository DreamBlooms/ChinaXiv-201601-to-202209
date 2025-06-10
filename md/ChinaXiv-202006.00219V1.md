# 机架模型下指向误差数据的筛选与分析

胡晓炜1，2，朱庆生1，2

（1、中国科学技术大学，安徽 合肥，2300262、中科院南京天文仪器有限公司，江苏 南

京，210042）

摘要：对地平式望远镜机架模型拟合的指向误差数据展开分析。介绍了指向误差数据的获取方法。采用最小二乘法求解修正系数，结合方位轴位置和高度轴位置拟合出指向修正量。在显著性水平 $\mathtt { q } = 0 . 0 5$ 下进行残差分析，剔除偏离过大的点以提高拟合精度。通过计算均方根误差，相关系数，F检验的 $\mathsf { p }$ 值验证了机架模型有效性。本文说明了增加测试数据后，未经残差检验不一定能提高拟合精度；以及分次获取的误差数据可合并处理。将求解的系数写入配置文件，在指向与跟踪过程中根据光栅编码器的反馈值实时修正。

关键词：残差分析；机架模型；指向修正；指向误差数据获取

中图分类号：P111.21

# Screening and analysis of pointing error data under frame model

Hu Xiao-wei1.2, Zhu Qing-sheng1.2 (1.University of Science and Technology of China,Hefei Anhui,230026;

2.Nanjing Astronomical Instruments Limited Company,Chinese Academy of Sciences,Nanjing Jiangsu,210042)

Abstract: The pointing error data of the frame model which apply to the altazimuth telescope are analyzed.The method of obtaining pointing error data is introduced in this paper. The least square method is used to solve the correction coefficient,and the pointing correction amount is fitted by combining the position of the azimuth axis and the height axis.At the significance level of $\mathfrak { a } = 0 . 0 5$ , the residual analysis is carried out to eliminate those points with excessive deviation to improve the fiting accuracy. The validity of the model is verified by calculating RMS error, correlation coefficient and p value of F test.This article explains that the fitting accuracy can not be improved without residual test after adding test data,and the error data obtained in different times can be combined for processing. Coefficients are writen into the configuration file,and then correct pointing error in real time according to the feedback value of the grating encoder during

the pointing and tracking process.

Key words: residual analysis; frame model; pointing correction; acquisition of pointing error data

# 1引言

我国有许多学者在天文望远镜的指向误差修正方面进行过研究，中科院南京天文仪器公司的朱庆生、陈伟民等人建立了机架模型[1]，经修正后的指向精度优于 $5 ^ { \prime \prime }$ 。中国科学院紫金山天文台的张晓祥、吴连大对静态指向模型的基本参数进行了讨论，通过逐步回归分析，确定了码盘零点差、度盘偏心误差等误差源作为显著回归因子[2。中国科学院国家天文台的李振伟、杨文波等人对比了球谐函数模型和水平式望远镜指向模型，并通过水平式望远镜观测验证了模型的有效性3。在射电望远镜的指向性能改进上，中国科学院新疆天文台的温浩兴等人通过修正轨道高差造成的指向偏差，提高了天线整体指向精度[4]。本文通过软件的方式修正指向误差，对机架模型下误差数据的获取及系数求解做了说明，并通过残差分析的方法筛选指向误差数据，计算均方根误差以验证模型对优化后数据的内符合精度，排除找星错误等误操作对修正结果的影响，提高拟合精度。在此基础上分析加密测量点数对指向修正精度的影响，并说明了分次获取的误差数据，残差检验后可合并处理。使用本文的方法对1米人卫激光测距望远镜和地基激光发射望远镜获取的指向误差数据进行分析，修正精度均得到有效提高。

# 2指向误差影响因素分析

天文望远镜在设计、加工、制造、装配等环节，由于多种因素引入指向误差，导致望远镜主光轴显示到达的位置与目标星实际的位置存在偏差，在卫星跟踪中不能准确指向卫星的预报位置。这些因素主要包含机架的制造与安装误差、轴系倾斜、轴间的不正交、重力变形、镜筒与光学系统的弯沉5、光栅编码器误差、视准轴误差等。指向误差一般用均方根误差（RMSE）表示。

修正指向误差可采用硬件修正和软件修正两种方法。硬件修正指机械和光学系统设计加工、装调过程中，采用轴系校准、视轴校准、光栅编码器测角组件校准等方法减小误差。但望远镜装调结束后就难以通过硬件修正减小误差，且随着运动部件的磨损，硬件修正效果大打折扣，硬件修正效果有限且费用较高。软件修正提取了影响望远镜指向误差的各个因素，利用系统误差重复性的特征，建立数学模型并通过计算机软件修正。

通过对望远镜机械系统的分析，可以估计出不加修正前的误差量，这部分误差为系统误差。就地平式望远镜而言，指向误差中系统误差较大，随机误差较小，由于系统误差与望远镜轴系的角度有关，可建立高度误差△H和方位误差△A的拟合模型。

望远镜在指向与跟踪前需要建立指向误差模型，通过回归分析确定拟合参数。在运行时，计算机实时计算望远镜在当前指向处的系统误差估计值，并对光栅编码器反馈的位置值进行修改，则可消除指向误差中的系统误差，大幅提高望远镜的指向精度和盲测的跟踪精度，美国的SLR2000经模型修正后指向误差可小于 $1 ^ { \prime \prime }$ 。

望远镜指向误差修正包含以下几个步骤：恒星选取、获取误差数据、建立指向误差模型、计算模型参数、验证模型符合度、在望远镜控制程序中导入修正系数并实时修正。

# 3常用指向误差模型

（1）球谐函数模型。采用球谐函数多项式对地基望远镜指向误差进行拟合的误差模型称为球谐函数模型，它可应用于任何机架结构的望远镜，通过对基准面为球面的误差进行拟合，方法简单，可拟合各种误差。对地平式望远镜和赤道式望远镜，能达到较高的内符合精度。但其模型参数较多且没有实际物理意义，参数之间相关性大，模型不稳定[，重新测得数据后，求出的模型参数变化大。

（2）基本参数模型。对望远镜的静态指向误差及基本参数逐步回归分析以确定显著回归因子。由于导致指向误差的因素较多且可能存在相关性，通过逐步回归分析，可将误差源中的不显著因子剔除，确保模型中的参数项必须存在且不可替代。其分析思路是将误差源逐个引入，每引入一个变量，要对模型中的原有变量逐个检验，将不显著的因子删除，重复该步骤，直至添加所有误差源。此时，回归模型中的所有误差源对修正系数都是显著的。因为经过逐步回归分析，故参数项较少且参数之间相关性小，模型较为稳定。但需根据望远镜的机架结构引入其他参数，设计不同的模型并验证残差，过程复杂且可拓展性较差。

（3）机架模型。机架模型也称为转台模型，常用于地平式望远镜，通过对望远镜机架结构分析建立模型。全模型共有24项参数，通过对参数间的相关性回归分析及试验，保留19 项参数，其中方位轴参数有11项，高度轴参数有10项（方位轴南北向倾斜和方位轴东西向倾斜为共同参数），这些参数均有实际的物理意义，表1和表2所示分别为模型方位轴和高度轴各项参数。

表1机架修正模型参数表（方位轴）  
Tab.1 Table of parameters of frame correction model (azimuth axis)  

<html><body><table><tr><td>序号</td><td>误差项描述</td><td>方位函数</td></tr><tr><td>1</td><td>方位编码器零点差</td><td>1</td></tr><tr><td>2</td><td>方位轴南北向倾斜</td><td>-cosAtanH</td></tr><tr><td>3</td><td>方位轴东西向倾斜</td><td>-sinAtanH</td></tr><tr><td>4</td><td>CCD 视场中心与光轴中心偏差</td><td>secH</td></tr><tr><td>5</td><td>方位轴与高度轴非正交</td><td>-tanH</td></tr><tr><td>6</td><td>方位方向椭圆率(sin)</td><td>sinA</td></tr><tr><td>7</td><td>方位方向椭圆率（cos）</td><td>CosA</td></tr></table></body></html>

表2机架修正模型参数表（高度轴）  

<html><body><table><tr><td>序号</td><td>误差项描述</td><td>方位函数</td></tr><tr><td>8</td><td>方位上的双周期(经验项)</td><td>sin2A</td></tr><tr><td>9</td><td>方位上的双周期 (经验项)</td><td>Cos2A</td></tr><tr><td>10</td><td>方位轴的双周期比例（sin)</td><td>sin2AsecH</td></tr><tr><td>11</td><td>方位轴的双周期比例（cos)</td><td>cos2AsecH</td></tr></table></body></html>

Tab.2 Table of parameters of frame correction model (height axis)   

<html><body><table><tr><td>序号</td><td>误差项描述</td><td>高度函数</td></tr><tr><td>1</td><td>高度编码器零点差</td><td>1</td></tr><tr><td>2</td><td>方位轴南北向倾斜</td><td>sinA</td></tr><tr><td>3</td><td>方位轴东西向倾斜</td><td>-cosA</td></tr><tr><td>4</td><td>镜筒弯沉</td><td>cotH</td></tr><tr><td>5</td><td>高度编码器的阻力（sin）</td><td>sinA</td></tr><tr><td>6</td><td>高度编码器的阻力（cos）</td><td>CosA</td></tr><tr><td>7</td><td>高度轴的阻力（sin)</td><td>HsinA</td></tr><tr><td>8</td><td>高度轴的阻力（cos）</td><td>HcosA</td></tr><tr><td>9</td><td>高度轴的双周期（sin)</td><td>sin2A</td></tr><tr><td>10</td><td>高度轴的双周期（cos）</td><td>Cos2A</td></tr></table></body></html>

机架模型的表达式为：

△A=ai-a2 cos A tan H-a3 sin A tan H+a4 sec $H - a { 5 }$ tan H+a6 sin A +a7 cos A+a& sin 2A+a9cos 2A+ aio sin 2A sec H+ aicos 2Asec H

机架模型是对基本参数模型的扩展，具有更高的精度，符合度优于基本参数模型。由于机架模型加入了更多的参数，增大了参数间的相关性，因此没有基本参数模型稳定[8]。

# 4误差数据获取与机架模型系数求解

望远镜指向模型修正分为零点校正，指向误差测定和模型系数求解三个模块，并将修正系数载入控制程序，在恒星和卫星的指向与跟踪中实时修正。本文基于地基激光发射望远镜，选用机架模型修正指向误差。

（1）测定码盘零点偏差。通过FK5 星表或星图软件让望远镜指向任意一颗恒星（避免指向双星系统，条件允许时选北极星可便于跟踪，避免引入更多误差)，手动将该星调到CCD中心，用码盘测得的方位/高度值减去该星的理论方位/高度值，即为码盘的零点偏差。通过这一步骤，修正码盘零点和坐标系零点之间的偏差。

（2）划分天区，获取数据。在晴夜中，根据拟获取的测试数据组数均匀划分天区，在每个分区内选定一颗亮度适中恒星（太亮容易曝光过度，使获取的误差数据不准确，太暗则可能与周围的恒星混淆)。此时有两种方法获得指向误差数据，方法一：根据该星偏离CCD中心的脱靶量和CCD 像素的空间分辨率，计算望远镜在该空间指向处的指向误差。方法二：手动将目标星调整到相机成像中心，该方法能避免方位轴像素分辨率随高度角变化带来的影响，有效提高测量精度。通过测量星点在CCD上偏移一定像素对应的望远镜转角，可以测定像素分辨率。经试验，在高度角为 $0 ^ { \circ }$ 时，方位像素分辨率见表3：

表3CCD像素分辨率测量表  
Tab.3 CCD pixel resolution measurement table   

<html><body><table><tr><td></td><td>方位</td><td>高度</td></tr><tr><td>角度</td><td>1208.0"</td><td>894.0"</td></tr><tr><td>CCD像素数</td><td>2592</td><td>1944</td></tr><tr><td>像素分辨率</td><td>0.466"</td><td>0.460"</td></tr></table></body></html>

则高度角H处，方位的像素分辨率为 $\left( 0 . 4 6 6 \times \mathrm { c o s H } \right) ^ { \prime \prime }$ 。因此，采用方法二记录误差数据（方位、高度、方位误差、高度误差)。试验共测得66组数据。

（3)求解指向模型系数。利用Matlab 软件对获取的误差数据进行处理，计算修正系数。误差数据包含4项，分别为方位角 $A Z _ { i }$ 、高度角 $E _ { i }$ 、方位偏差 $d e l t a A Z _ { i }$ 、高度偏差deltaHi（方位、高度以弧度表示，偏差数据以角度表示，共测得 $N$ 组数据, $i { = } 1 , 2 , \cdots , N )$ ，将其导入Matlab 中，构造四组一维列向量。代入机架模型的方位函数与高度函数，得到修正系数矩阵 $A$ ，通过最小二乘法求解，可求得修正系数向量 $B _ { \circ }$ 推导过程如下：

令系数矩阵 $A = { \left[ \begin{array} { l } { X } \\ { Y } \end{array} \right] }$ ，误差矩阵 $D E T = \left[ { { d e l t a A Z } \atop { d e l t a H } } \right]$ $X$ 为方位函数矩阵， $\boldsymbol { Y }$ 为高度函数矩阵，根据机架模型中系数的物理意义，有$\mathrm { X = [ 1 ~ 0 \mathrm { \mathrm { \mathrm { - c o s } ( A Z ) . \times t a n ( H ) \mathrm { \cdot { s i n } ( A Z ) . \times t a n ( H ) \mathrm { \ s e c ( H ) \mathrm { \cdot { t a n ( H ) \mathrm { \ s i n } ( A Z ) \mathrm { \cos ( A Z ) \mathrm { 0 } } } } } } } } }$ $\sin ( 2 . \times \mathrm { A Z } ) \cos ( 2 . \times \mathrm { A Z } ) 0 0 0 0 \sin ( 2 . \times \mathrm { A Z } ) . \times \sec ( \mathrm { H } ) \cos ( 2 . \times \mathrm { A Z } ) . \times \sec ( \mathrm { H } ) 0 0 ]$

$$
\begin{array} { r l } & { \mathrm { Y } { = } [ 0 \ 1 \ \sin ( \mathrm { A Z } ) \cdot \cos ( \mathrm { A Z } ) \ 0 \ 0 \ 0 \ \cot ( \mathrm { H } ) \ 0 \ 0 \ \sin ( \mathrm { A Z } ) \cos ( \mathrm { A Z } ) } \\ & { \mathrm { H } . \times \sin ( \mathrm { A Z } ) \ \mathrm { H } . \times \cos ( \mathrm { A Z } ) \ 0 \ 0 \ \sin ( 2 . \times \mathrm { A Z } ) \cos ( 2 . \times \mathrm { A Z } ) ] } \end{array}
$$

采用多项式曲线拟合，拟合曲线方程为19 阶多项式。测试数据共66 组，系数矩阵 $A$ 为 $1 3 2 \times 1 9$ ，误差矩阵DET为 $1 3 2 \times 1$ 。

$$
\left\{ \begin{array} { l l } { \displaystyle \mathrm { d e t } _ { 1 } = \sum _ { i = 0 } ^ { 1 9 } a i x ^ { i } = a { 1 9 } A _ { 1 } { , } ^ { 1 9 } + a { 1 8 } A _ { 1 , 2 } { } ^ { 1 8 } + \cdots + a { 2 A _ { 1 , 1 8 } } ^ { 2 } + a { 1 A _ { 1 , 1 9 } } } \\ { \displaystyle \mathrm { d e t } _ { 2 } = \sum _ { i = 0 } ^ { 1 9 } a i x ^ { i } = a { 1 9 } A _ { 2 , 1 } { } ^ { 1 9 } + a { 1 8 } A _ { 2 , 2 } { } ^ { 1 8 } + \cdots + a { 2 A _ { 2 , 1 8 } } ^ { 2 } + a { 1 A _ { 2 , 1 9 } } } \\ { \vdots } \\ { \displaystyle \mathrm { d e t } _ { 1 3 2 } = \sum _ { i = 0 } ^ { 1 9 } a i x ^ { i } = a { 1 9 } A _ { 1 3 2 , 1 } { } ^ { 1 9 } + a { 1 8 } A _ { 1 3 2 , 2 } { } ^ { 1 8 } + \cdots + a { 2 A _ { 1 3 2 , 1 8 } } ^ { 2 } + a { 1 A _ { 1 3 2 , 1 9 } } } \end{array} \right.
$$

用矩阵形式可以表示为：

$$
D E T = A B
$$

$B$ 为待求解的修正系数向量 $[ \mathbf { b } _ { 1 9 } , \mathbf { b } _ { 1 8 } , \cdots , \mathbf { b } _ { 1 } ] ^ { \mathrm { T } }$ ，在方程两边左乘 $\boldsymbol { A } ^ { \mathrm { T } }$ ，得到：

$$
A ^ { T } D E T = A ^ { T } A B
$$

在新方程的两边同乘 $A ^ { \mathrm { I } } A$ 的逆矩阵，有

$$
B { = } ( A ^ { T } A ) ^ { - 1 } A ^ { T } D E T
$$

上式右半部分各项均已知，可求解得到修正系数向量 $B _ { \circ }$

在望远镜的基座、重力分布未发生较大变化的情况下，一次误差测定可长期使用。

# 5误差数据分析及模型符合度验证

在指向模型数据处理的过程中，修正系数的拟合精度受单次观测的统计量影响。当出现目标星识别错误，基座振动等情况时，测量的误差值会大幅偏离真实误差值。异常的观测数据在图形上呈现孤立型，偏离由大多数数据组成的分布趋势，需要剔除这些数据以降低对拟合精度的影响。

通过残差分析的方法剔除偏离过大的数据，从而保证实验数据的精确度。在上节的求解模型中将方位误差提取出来，单独求解，由式1可知，方位修正系数共11项。若要求解这11个系数，则最少需要11组方程。试验共获取66 组数据，可构建 66 组方程，相应的就有66 个残差。本文中，第i组数据的残差 $\mathbf { e } _ { \mathrm { i } }$ 为该组的预测值 $\hat { y } _ { i }$ 与观测值 $\bf { y } _ { \mathrm { { i } } }$ 之差，即 $e _ { i } = \hat { y } _ { i } - y _ { i }$ 。代入上节求解模型，有：

$$
e = \left[ \left( X \times B \right) - d e l t a A Z \right] \times 3 6 0 0
$$

上式残差的单位为角秒，取残差 $9 5 \%$ 置信区间，可得方位残差图，以此估计预测的误差与实际误差是否一致，从而验证所建模型的符合度，方位残差图如图1所示：

![](images/93435b9c2736bcf36ab1e00391158077acc7dd351c51cc2863d31b3e7eefd0c3.jpg)  
图1方位残差分析图  
Fig.1 azimuth residual analysis chart

图注：左图为 $9 5 \%$ 置信区间，右图为 $9 9 \%$ 置信区间

图1的横坐标表示测试文件中数据的序号，纵坐标代表残差，即拟合值与实际测量值之间的差值，以角秒表示。可看出，残差随机分布在零点的两侧，若残差的置信区间与零点相交，则说明获取的指向误差数据能够较好地符合模型。反之，若置信区间偏离零点，则该组数据可视为异常数据，需要剔除。以方位残差 $9 5 \%$ 置信区间为例，66组测试数据中有4组异常，需要剔除以提高模型精度。

为了验证指向模型对偏差数据的修正是否具有良好的精确度，本文采用均方误差（MSE)作为评价指标，该指标可评价数据的变化程度，MSE越小，说明模型描述数据越准确。均方误差表达式为：

$$
M S E = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \left( \hat { y } _ { i } - y _ { i } \right) ^ { 2 }
$$

为了在数量级上更直观，可对均方误差开方，即均方根误差（RMSE)，有：

$$
R M S E = { \sqrt { M S E } }
$$

以方位的指向误差为例，分别计算在不同组数下的均方根误差，如表4所示：

# 表4不同数量测试组下计算的均方根误差（方位角）

Tab.4 Root mean square error calculated under different number of test groups (azimuth)   

<html><body><table><tr><td>测试数据组数</td><td>均方根误差(角秒)</td><td>测试数据组数</td><td>均方根误差(角秒)</td></tr><tr><td>12</td><td>737966.61</td><td>25</td><td>25.56</td></tr><tr><td>13</td><td>1044325.26</td><td>30</td><td>29.41</td></tr><tr><td>14</td><td>98457.58</td><td>35</td><td>30.06</td></tr><tr><td>15</td><td>1253.46</td><td>40</td><td>32.45</td></tr><tr><td>16</td><td>406.68</td><td>45</td><td>34.65</td></tr></table></body></html>

<html><body><table><tr><td>测试数据组数</td><td>均方根误差(角秒)</td><td>测试数据组数</td><td>均方根误差(角秒)</td></tr><tr><td>17</td><td>171.53</td><td>50</td><td>43.86</td></tr><tr><td>18</td><td>19.08</td><td>55</td><td>46.60</td></tr><tr><td>19</td><td>19.88</td><td>60</td><td>47.01</td></tr><tr><td>20</td><td>21.78</td><td>66</td><td>46.76</td></tr></table></body></html>

由于拟合方位误差需要确定11个系数，故最少需要11组测试数据。从表4可看出，在一定范围内，增加测试组别能有效提高模型的符合度。当测试组数超过20 组时，拟合数据的准确度反而随测试组数的增加而降低。因此，不经处理的增加测试组数并不能使拟合精度得到优化。添加新的误差数据后须经残差分析，剔除偏离较大的值，才能降低拟合误差。

在已获取指向误差数据的情况下，可通过残差分析，将残差 $9 5 \%$ 置信区间与零点不相交的数据依次剔除，如图2所示。并计算剔除后数据的均方根误差，如表5、表6所示。

方位残差分析图（95%置信区间） 方位残差分析图（95%置信区间）150山址山 1001001 1l5050 4  
/ -50 /r T -50-100 C-150 -100-20010 20 30 40 50 60 10 20 30 40 50 60方位误差组序 方位误差组序a b方位残差分析图（95%置信区间） 方位残差分析图（95%置信区间）8080 60604040 ①2020  
/ 0 用/ TF-20-20-40-40-60 -60-80 -80-100 -1005 101520 253035 40 45 50 55 5 10 15 20 2530 35 40 45 50方位误差组序 方位误差组序C d

图注：图a为66组数据，图b为62组数据，图c为58组数据，图d为54组数据。均取 $9 5 \%$ 置信区间。

表5剔除残差偏离数据后的均方根误差（方位角）  
Tab.5 Root mean square error after eliminating residual deviation data(azimuth)   

<html><body><table><tr><td>测试数据组数</td><td>均方根误差(角秒)</td><td>测试数据组数</td><td>均方根误差(角秒)</td></tr><tr><td>66</td><td>46.76</td><td>58</td><td>26.25</td></tr><tr><td>62</td><td>34.35</td><td>54</td><td>22.42</td></tr></table></body></html>

由式2可知，高度修正系数共有10项，故拟合高度误差至少需要10 组数据。同理，对高度方向做残差分析。

1614 L1210组86215 -10 -5 0 5 10 15 20残差/角秒

注：图为残差分布直方图，横坐标表示残差，纵坐标表示某一残差范围的数据组数，由图可看出，高度残差近似服从正态分布。

![](images/a63bc3d0c83d04aec99100be74b9ca66331bc35e15ba3f0a05168eda4519f0e2.jpg)  
图3高度角残差数据分布  
Fig.3 height residual data distribution   
图4剔除部分偏离较大数据后的残差分析图（高度角）  
Fig.4 residual analysis chart after removing some value with large deviation (height)

图注：图a为66组数据，图b为62组数据，图c为58组数据，图d为54组数据。均取 $9 5 \%$ 置信区间。

# 表6剔除残差偏离数据后的均方根误差（高度角）

Tab.6 Root mean square error after eliminating residual deviation data(height)   

<html><body><table><tr><td>测试数据组数</td><td>均方根误差(角秒)</td><td>测试数据组数</td><td>均方根误差(角秒)</td></tr><tr><td>66</td><td>5. 41</td><td>58</td><td>3.37</td></tr><tr><td>62</td><td>4.29</td><td>54</td><td>2. 77</td></tr></table></body></html>

使用乌鲁木齐的地基激光发射望远镜试验，在 $0 ^ { \circ } \ \sim 3 6 0 ^ { \circ }$ 范围内选择60 颗恒星，测量指向误差数据，删除残差偏离较大的数据点后，计算的两轴均方根误差如表8、表9所示，相应残差分析图如图6、图7所示：

![](images/f7f5898dac554e41a589f08aaa52ff415b974262323b90d78b8ed4c8761c9f72.jpg)  
图5恒星指向数据的A-0-E坐标分布图

![](images/21e7160dfefd6729a8235b2fae19882086ebd6d1ce6f8996ce77b2d552fc1738.jpg)  
Fig.5 A-O-E coordinate distribution of star pointing data   
图6剔除部分偏离较大数据后的残差分析图（方位角）  
Fig.6 residual analysis chart after removing some value with large deviation (azimuth)

图注：左图为60 组数据，右图为56 组数据。

![](images/cafef6f158bf891dbd6ac005a66584e3af31598174dda83caec18c3767e3ea88.jpg)  
图7剔除部分偏离较大数据后的残差分析图（高度角）  
Fig.7 residual analysis chart after removing some value with large deviation (height)

图注：左图为60组数据，右图为56组数据。

# 表7应用机架模型计算的剔除残差偏离较大数据前后的修正系数对比表

Tab.7 Comparison table of correction coefficient calculated by frame model (before and after removing data with large residual deviation)   

<html><body><table><tr><td rowspan="2">序号</td><td rowspan="2">数据优化前 方位</td><td colspan="2">数据优化后</td></tr><tr><td>高度 方位</td><td>高度</td></tr><tr><td>1</td><td>0.19809 0. 04877</td><td>0.19549</td><td>0.05176</td></tr><tr><td>2</td><td>0.03339 -0. 02918</td><td>0.03242</td><td>-0. 02667</td></tr><tr><td>3</td><td>-0.00849</td><td>0. 00125 -0. 00649</td><td>0. 00380</td></tr><tr><td>4</td><td>-0.13096</td><td>-0. 01822 -0.13219</td><td>-0. 02299</td></tr><tr><td>5</td><td>-0.00400</td><td>-0.02918 -0. 00641</td><td>-0. 02667</td></tr><tr><td>6</td><td>-0.00100</td><td>-0.00125 0.00395</td><td>-0.00380</td></tr><tr><td>7</td><td>-0. 00076</td><td>0. 01993 -0.00280</td><td>0. 01674</td></tr><tr><td>8</td><td>0. 00352</td><td>-0. 00593 0.00628</td><td>-0. 00099</td></tr><tr><td>9</td><td>-0. 00143</td><td>-0. 00241 0. 00022</td><td>-0. 00224</td></tr><tr><td>10</td><td>-0. 00218</td><td>-0. 00457 -0. 00349</td><td>-0. 00332</td></tr><tr><td>11</td><td>0.00007</td><td>-0.00029</td><td></td></tr></table></body></html>

Tab.8 Root mean square error after eliminating residual deviation data(azimuth)

表8剔除残差偏离数据后的均方根误差（方位角）  

<html><body><table><tr><td>测试数据组数</td><td>均方根误差(角秒)</td><td>测试数据组数</td><td>均方根误差(角秒)</td></tr><tr><td>60</td><td>9.46</td><td>56</td><td>7.79</td></tr></table></body></html>

Tab.9 Root mean square error after eliminating residual deviation data(height)

表9剔除残差偏离数据后的均方根误差（高度角）  

<html><body><table><tr><td>测试数据组数</td><td>均方根误差(角秒)</td><td>测试数据组数</td><td>均方根误差(角秒)</td></tr><tr><td>60</td><td>18.47</td><td>56</td><td>11.39</td></tr></table></body></html>

试验获取了1m人卫激光测距望远镜，地基激光发射望远镜等项目的多组指向误差数据，通过计算分析得出结论：剔除残差偏离的测试组能够有效提高指向修正数据的拟合精度。

在外界环境未发生明显变化的前提下，指向误差数据可分次获取（可将分批获取的数据合并，使用残差图分析，若残差集中在 $9 5 \%$ 置信区间内且未出现断层，则可判定外部环境未发生明显变化)，添加新的测试数据时，要保证添加后测试组的均方根误差小于原有测试组的均方根误差，方能提高指向模型对误差数据描述的准确度。

通过多元线性回归检验机架指向修正模型对偏差数据拟合的精确度，如表10所示：

# 表10机架模型检验表

Tab.10 Frame model inspection form   

<html><body><table><tr><td>测试组数</td><td>R²(R为相关系数)</td><td>F统计量</td><td>F检验的p值</td><td>误差方差</td></tr><tr><td>66（方位角）</td><td>0.99695889</td><td>1803.05339</td><td>2.0198×10-65</td><td>2.0253×10-4</td></tr><tr><td>54（方位角）</td><td>0.99891837</td><td>3971.18443</td><td>2.3422×10-60</td><td>4.8698×10-5</td></tr><tr><td>66 (高度角）</td><td>0.99951715</td><td>17151.7968</td><td>1.0660×10-93</td><td>2.5792 ×10-6</td></tr><tr><td>54（高度角）</td><td>0.99986543</td><td>48827.2601</td><td>8.4612×10-87</td><td>6.9740×10-7</td></tr></table></body></html>

$\boldsymbol { \mathrm { R } } ^ { 2 }$ 为决定系数，其值越大，拟合程度越高。由表10可看出，原始的66 组测试数据拟合优度超过 $9 9 \%$ ，误差拟合精度非常好。通过残差分析筛选数据后，拟合优度又得到了进一步提高。同样的，也可通过F检验的p值验证指向模型的有效性。一般的，当 $\mathrm { p } { < } 0 . 0 0 1$ 时，说明模型有效，由上表可看出，对于所列的测试组，F检验的p值远远小于0.001,说明指向模型能够很好的拟合偏差数据。

# 参考文献：

[1］朱庆生，陈伟民，吴金虎.卫星激光测距望远镜的指向改正[J]．天文研究与技术，2011，8(3):268-271.Zhu Qingsheng，Chen Weimin,Wu Jinhu.TheCorrectionof Pointingofalm SLR Telescope［J].ASTRONOMICAL RESEARCH  
&TECHNOL0GY，2011，8(3):268-271.[2]张晓祥，吴连大．望远镜静态指向模型的基本参数[J]．天文学报，2001,42(2):198-205.ZHANG X X，WUL D.The basic parameters of telescope static point model[J]．Acta Astronomica  
Sinica,2001,42(2):198-205.[3]李振伟，杨文波，张楠．水平式光电望远镜静态指向误差的修正[J]．中国光学，2015，8(2):263-269.LI Zhen-wei,YANG Wen-bo,ZHANG Nan.Staticpointing errorof levelmounting optoelectronic telescope[J].Chinese  
Optics，2015，8(2):263-269.[4]温浩兴，许谦，王娜．南山 26 米射电望远镜轨道高差测量及其对指向精度的影响［J]．天文研究与技术，2019,  
16(2):158-166.Wen Haoxing,XuQian,WangNa.Measurementof NSRT 26m Antenna Track Unevennessand Influence onPoint Accuracy[J].  
ASTRONOMICALRESEARCH& TECHNOLOGY，2019，16(2):158-166.[5]马锦，顾伯忠．地平式望远镜轴系误差对指向精度和跟踪精度的影响[J]．天文研究与技术，2011，8(2):132-138.Ma Jin,Gu Bozhong.Effects of the Shaft Error of an Altazimuth Telescopeon Pointing and Tracking Accuracies  
[J]．ASTRONOMICAL RESEARCH& TECHNOLOGY，2011，8(2):132-138.[6]平一鼎，张晓祥，鲁春林．65cm 水平式望远镜静态指向模型[J]．天文学报，2006,47(2):224-230.Ping Yiding，Zhang Xiaoxiang，Lu Chunlin.Static Pointing Model of 65cm Level Mounting Telescope[J]．Acta

Astronomica Sinica,2006,47(2) :224-230.

[7]喻业钊，韩雷，等．佳木斯66m 射电望远镜指向精度测量及改进[J]．天文研究与技术，2016，13(4)：408-415.Yu Yezhao，Han Lei，et al.A Study on the Measurements and Improvements of Pointing Acuracy of Jiamusi 6mRadio Telescope［J]．ASTRONOMICAL RESEARCH& TECHNOLOGY，2016，13(4):408-415.[8]朱程广，周勇，等．卫星激光测距望远镜指向误差研究[J]．大地测量与地球动力学，2013,33:126-128.Zhu Chengguang，Zhou Yong，etal.Research of Pointing Errorof Satellite Laser Ranging [J].JOURNAL OF GEODESYANDGEODYNAMICS,2013,33:126-128.