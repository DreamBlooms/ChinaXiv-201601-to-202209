# 航天继电器多参数贮存寿命加速退化预测方法研究

李文华 沈培根 马思宁（河北工业大学电气工程学院 天津300130)

![](images/3ad6a40c8ffd454be6f939c09d6e9718ae6819ab54aa81556b37e2af8113e5cf.jpg)

李文华男 1973年生，教授，研究方向为电器可靠性及检测技术、新能源发电和并网技术。

摘要：航天继电器在国防、航天工业等重要领域使用范围十分广泛，因此，为了提高航天继电器的可靠性，研究其贮存寿命具有十分重要的意义。目前，基于性能退化数据的大多文献局限于研究单个特征参数的情况，然而许多产品具有多个性能退化特征量。针对航天继电器具有多个性能参数的特点，本文提出了退化距离分析法，并在此基础上引入主元分析法 (PCA)，融合了多个特征参数，给出了参数权重因子求解方法。文中选择了航天继电器的接触电阻 $R _ { \mathrm { j } }$ 、吸合时间 $T _ { \mathrm { x } }$ 和释放电压 $U _ { \mathrm { s } }$ 这三个参数，通过该方法实现了贮存寿命预测，并选取实测数据对该方法进行了验证。

关键词：寿命预测退化距离 多特征参数主元分析中图分类号：V442；TM5

# Study on Multi-Parameters Storage Life Prediction Method for Aerospace Relay in Accelerated Degradation

Li Wenhua Shen Peigen Ma Sining (Hebei University of TechnologyTianjin300130 China)

![](images/19b602785cfd71ed76c09a9d09cbdaf60f3bc073cb23531611374a4f50da5322.jpg)

沈培根男1990年生，硕士研究生，研究方向为电器可靠性及检测技术。

Abstract: Aerospace relay, is widely used in the field of national defense,aerospace industry,and others. Therefore,in order to improve the reliability of the aerospace relay, it is of great significance to study its storage life.At present, researches based on performance degradation data are mostly confined to the single characteristic parameters. However, many products have multiple performance degradation parameters. On account of the multiple performance parameters of aerospace relay, the degradation distance analysis method is proposed in this paper, principal component analysis (PCA) is also introduced into this analysis method to fuse multiple characteristic parameters,and weighting factors of parameters are given. In this paper, the aerospace relay contact resistance $R _ { \mathrm { j } }$ ，pick-up time $T _ { \mathrm { x } } ,$ release voltage $U _ { \mathrm { s } }$ are selected as life prediction parameters, and the relay storage life can be predicted with the help of the above method ，which is also verified to be accurate by other data acquired in the experiment.

Keywords: Life prediction, degradation distance,multiple characteristic parameters, principal component analysis

# 1 引言

航天继电器广泛用于国防、航天工业等重要设备中，需要在低温、高温、高湿及高频振动等恶劣环境下完成系统电信号传递、电路隔离及继电保护等重要功能。在实际的工作情况下，只要有一台继电器出现故障，就可能造成整个系统瘫痪，这就要求继电器能够可靠工作以保证整个系统的长期正常运行。有些继电器的贮存时间远远大于使用时间[1]。在贮存过程中，由于环境条件的不断变化，继电器的性能会出现衰退，这就可能造成当其投入使用时，继电器已经无法正常工作的情况。因此，进行航天继电器贮存寿命预测对保证继电器在诸多特殊环境中满足极高的可靠性、寿命要求和消除故障隐患可能带来的重大的经济损失有着深远的意义[2]。传统的寿命试验方法对继电器进行可靠性评估和寿命预测时，会面临试验成本高、失效数据少等许多问题，从而无法得到有效的结果。继电器产品在服役过程中的失效机理最终能够追溯到产品潜在的性能退化过程，可以认为性能退化最终导致了产品失效（或故障）的产生。因此，基于性能退化数据的分析已经成为一种有效且节约成本的性能评估方法[3]。

# 2 问题描述

产品性能退化可能会引起某一个或几个特征性能参数发生变化，这就需要根据产品功能来考察其中某几个重点特征参数，然后综合考虑这些参数来评价产品工作状态或性能情况。产品的性能特别是一些复杂的系统，往往要几个性能参数综合反映，同样需要综合考虑这些参数来评价产品的性能退化[4]。在产品性能退化数据分析研究中，针对多性能退化参数的文献大多假设多个退化参数的联合概率密度函数服从某种多元分布，例如文献[3]假设检查时刻点的多元性能退化数据服从多元正态分布，文献[5]利用了联合概率密度函数表征产品失效概率密度，或者假设性能参数退化规律符合Wiener、泊松等随机过程并通过预先确定的单特征参数的失效阈值来计算产品的故障时间[6-8]，这就忽略了多性能退化参数相关条件下，失效阈值也可能变化的情况。本文提出了退化距离分析法，解决了多参数和多参数失效阈值的问题。在利用该方法进行分析需要做如下假设：

（1）产品的各个性能参数随时间退化具有不可逆性[9]。

(2）多个性能退化参数相关或者相互独立。(3）当继电器的某个退化参数达到产品给定失效阈值时，就判定产品失效。

# 3 数据预处理

对25台某型号航天继电器在 $1 2 5 \mathrm { { ^ circ C } }$ 恒定应力下进行加速贮存退化试验，采集继电器的接触电阻 $R _ { \mathrm { j } }$ ，吸合时间 $T _ { \mathrm { x } }$ 和释放电压 $U _ { \mathrm { s } }$ 这3个电特征参数，其中选取触点接触电阻 $R _ { \mathrm { j } }$ 的最大值为产品的接触电阻值。产品的规定阈值分别为 $5 0 ~ \mathrm { m } \Omega$ 、 $8 ~ \mathrm { m s }$ 、 $2 . 5 \mathrm { ~ V ~ }$ 。试验中编号17#继电器贮存试验测量得到的特征量数据见表1。

表1特征参数样本数据  
Tab.1 Characteristic parameters of sample data   

<html><body><table><tr><td>周数</td><td>接触电阻Rj/mΩ</td><td>吸合时间Tx/ms</td><td>释放电压U/V</td></tr><tr><td>1</td><td>8.31</td><td>5.09</td><td>4.50</td></tr><tr><td>2</td><td>8.34</td><td>5.68</td><td>4.21</td></tr><tr><td>3</td><td>8.66</td><td>5.82</td><td>4.13</td></tr><tr><td>4</td><td>8.65</td><td>5.74</td><td>4.29</td></tr><tr><td>5</td><td>8.23</td><td>5.76</td><td>4.15</td></tr><tr><td>6</td><td>8.87</td><td>6.33</td><td>4.23</td></tr><tr><td>7</td><td>8.56</td><td>5.81</td><td>4.10</td></tr><tr><td>8</td><td>8.33</td><td>5.86</td><td>4.11</td></tr><tr><td>9</td><td>8.62</td><td>5.82</td><td>4.09</td></tr><tr><td>10</td><td>8.63</td><td>6.78</td><td>4.04</td></tr><tr><td>11</td><td>8.93</td><td>5.97</td><td>4.06</td></tr><tr><td>12</td><td>8.66</td><td>5.92</td><td>4.13</td></tr><tr><td>13</td><td>9.04</td><td>5.70</td><td>4.06</td></tr><tr><td>14</td><td>8.70</td><td>5.85</td><td>4.06</td></tr><tr><td>15</td><td>9.07</td><td>5.90</td><td>4.25</td></tr><tr><td>16</td><td>8.86</td><td>5.71</td><td>4.18</td></tr><tr><td>17</td><td>8.88</td><td>5.86</td><td>4.33</td></tr><tr><td>18</td><td>8.91</td><td>5.96</td><td>4.13</td></tr><tr><td>19</td><td>8.74</td><td>5.85</td><td>4.28</td></tr><tr><td>20</td><td>9.08</td><td>6.02</td><td>4.21</td></tr><tr><td>21</td><td>9.00</td><td>5.91</td><td>4.23</td></tr><tr><td>22</td><td>8.99</td><td>5.91</td><td>4.05</td></tr><tr><td>23</td><td>9.20</td><td>5.82</td><td>3.96</td></tr><tr><td>24</td><td>9.50</td><td>5.95</td><td>3.97</td></tr></table></body></html>

由于测量设备本身存在误差和外界环境等扰动因素，所测的特征变量包含一定的噪声，为减少干扰的影响，降低测量值的随机性，前期有必要对数据进行平稳处理，本文采用移动平滑滤波法分别对3个特征参数进行平滑处理。

# 4参数退化距离分析

在大多数实际问题中，表示产品工作状态的性能参数，其稳定的变化趋势是单调上升或单调下降的。从产品性能开始发生退化到产品最终失效，产品的性能参数初值是朝着失效阈值方向发展的。随着试验时间的延长，每个性能参数值与失效阈值间的距离将越来越接近，当参数值无限接近失效阈值的时候，也就是距离接近为0时，产品最终发生了失效。这种现象也反映了退化过程的不可逆性。用2个性能参数 $X ^ { 1 }$ ， $X ^ { 2 }$ 来说明产品性能退化过程，如图1所示。

![](images/f2a69581b217358cd3fc0fcf9de34be34b2f015493a09817b0ff3cc6ae3f0a6b.jpg)  
图1产品性能退化过程  
Fig.1Product performance degradation process

假设产品有 $L$ 个性能退化参数： $X ^ { 1 }$ ， $X ^ { 2 }$ $X ^ { 3 }$ ， $\cdots X ^ { L }$ 且设第 $j$ 个性能退化参数的失效阈值为$X _ { \mathrm { f } } ^ { j }$ ，则在 $t$ 时刻性能退化参数值与失效阈值间距离为 $\vert X ^ { j } ( t ) - X _ { \mathrm { f } } ^ { j } \vert$ ，记做 $D ( t )$ ，在 $\mathbf { \chi } _ { t }$ 时刻多性能参数与阀值间距离的定义为

$$
D ( t ) = \sum _ { j = 1 } ^ { L } w _ { j } \Big | X ^ { j } ( t ) - X _ { \mathrm { f } } ^ { j } \Big |
$$

式中， $w _ { j } ( j = 1 , 2 , \ \cdots L )$ 为加权因子，根据各个特征参数在实际中的重要程度给出。通过对某时刻的参数值与失效阈值间距离的分析，可以看出距离可以有效地反映产品性能的变化趋势，那么在实际问题中，如何从若干特征参数中筛选较为重要的参数，确定参数之间的加权因子和经数据变化后失效阈值，是进行性能退化分析的关键所在。

# 4.1主元分析融合特征参数

主元分析是一种常用的特征提取方法，已广泛应用于传感器信号的提取、发电量预测和凝汽器故障诊断等领域。采用主元分析法能把多维的特征参数维度降低，能提取出所有特征参数之间的相关性

较强的特征量。其基本思想是通过对原始数据进行线性变换，变换后的数据即主元，具有较低的维数但能最多地反映原始数据信息[10-12]。对于某个数据矩阵 $X _ { n \times m }$ ，每一列 $X _ { i }$ 对应一个特征矢量，每一行为观测样本。对矩阵 $X _ { n \times m }$ 进行主元分析实质上就是对其协方差矩阵进行特征矢量分析。当 $X _ { n \times m }$ 的特征矢量量纲不同或数量级差别较大时，需采用式（2）对其进行数据极差变换，经过变换后，矩阵 $X$ 中的每个元素取值均在 $0 \sim 1$ 之间。

$$
x _ { i j } ^ { R } = \frac { x _ { i j } - \underset { 1 \leqslant k \leqslant n } { \operatorname* { m a x } } x _ { k j } } { \underset { 1 \leqslant k \leqslant n } { \operatorname* { m a x } } x _ { k j } - \underset { 1 \leqslant k \leqslant n } { \operatorname* { m i n } } x _ { k j } }
$$

本文以接触电阻 $R _ { \mathrm { j } }$ 、吸合时间 $T _ { \mathrm { x } }$ 和释放电压$U _ { \mathrm { s } }$ ，这3个特征参数构成数据矩阵 $X _ { 2 4 \times 3 }$ 。对 $X _ { 2 4 \times 3 }$ 进行主元分析，得到各主元 $Y _ { i } ( i = 1 , 2 , 3 )$ 。当各特征参数之间存在一定的相关性时， $X _ { 2 4 \times 3 }$ 的变化主要体现在前几个主元上。经PCA计算得到3个主元的系数矩阵

$$
\left( \begin{array} { c c c } { { 0 . 0 4 4 4 } } & { { 0 . 0 7 5 5 } } & { { 0 . 9 9 9 2 } } \\ { { 0 . 8 7 0 2 } } & { { 0 . 4 8 6 8 } } & { { - 0 . 0 7 5 7 } } \\ { { - 0 . 4 9 0 7 } } & { { 0 . 8 7 0 2 } } & { { - 0 . 0 4 4 1 } } \end{array} \right)
$$

在应用主元分析法进行数据压缩和特征提取时，为了使舍弃的原有数据信息不影响对整体数据的分析，要求主元的累积贡献率必须大于 $8 5 \%$ ，见表2。

# 表2主元贡献率

Tab.2 Principal component contribution   

<html><body><table><tr><td>主元</td><td>特征根</td><td>贡献率(%)</td></tr><tr><td>Y</td><td>1.10 ×10-²</td><td>97.52</td></tr><tr><td>Y</td><td>2.57× 10-4</td><td>2.28</td></tr><tr><td>Y</td><td>2.16× 10-5</td><td>0.20</td></tr></table></body></html>

第一主元和第二主元的累积贡献率已经达到$8 5 \%$ 以上。经过PCA，不但消除了多参数间彼此的冗余信息及干扰信息，而且第一主元和第二主元已经足够强地反映出原始多维特征参数的变化信息。所以，完全可以省略第三主元，只保留第一、第二主元，从而达到降低多参数维度的效果。第一主元的贡献率最大，保持了特性参数之间的绝大部分相关性，反映了特征参数的变化。在忽略其他贡献率较小主元的情况下，第二主元是原始信息和第一主元之间误差信息的一种综合体现，反映了参数变化中不确定性和干扰因素。由系数矩阵，可得到第一主元 $\pmb { Y } _ { 1 }$ 、第二主元 $\boldsymbol { Y } _ { 2 }$ 的表达式

$$
\begin{array} { r } { Y _ { 1 } = 0 . 0 4 4 4 x _ { 1 } + 0 . 8 7 0 2 x _ { 2 } - 0 . 4 9 0 7 x _ { 3 } } \\ { \quad } \\ { Y _ { 2 } = 0 . 0 7 5 5 x _ { 1 } + 0 . 4 8 6 8 x _ { 2 } + 0 . 8 7 0 2 x _ { 3 } } \end{array}
$$

根据式（3）和式（4）可以进一步得到第一主元和第二主元变化的时间序列。

# 4.2主元参数权因子的确定方法

第 $j$ 个主元的贡献率代表的含义是第 $j$ 个主元所包含信息占系统全部信息的百分比，即第 $j$ 个主元的重要程度的百分比。 $\omega _ { j }$ 表示式（1）中，各个参数的重要程度，也就是占有信息量的多少。若选取了 $q$ 个主元，可得

$$
{ \omega } _ { j } = { \lambda } _ { j } \Bigg / \sum _ { k = 1 } ^ { q } { \lambda } _ { k }
$$

式中， $\lambda _ { j }$ 表示为被选取的第 $j$ 个主元的特征值，这里提取了两个主元 $\pmb { Y } _ { 1 }$ 、 $\boldsymbol { \mathsf { 1 } } _ { 2 }$ 。根据式 (5)，可以计算出参数权因子 $\omega _ { 1 }$ ， $\omega _ { 2 }$ 的数值。

# 4.3多参数失效阈值的确定

首先，在分析性能退化的数据时，为了消除各个性能参数之间量纲的不同对原始数据进行了变换。其次，对消除量纲后的数据进行了主成分分析。因此，在给定各个性能参数失效阈值的情况下，不能简单地得到失效阈值，而是需要对失效阈值也做上述相应的变化，才能保证失效阈值的有效性。

在产品性能发生退化的过程中，从长期来看，产品的性能指标值的变化趋势是上升或下降的，而这种变化趋势就是产品的性能退化轨迹，显然产品的各个参数的失效阈值就是退化轨迹上的最大值或最小值。根据极差变换公式和数据所反映的趋势，可以对产品说明给定的失效阈值进行变换。接触电阻 $R _ { \mathrm { j } }$ 、吸合时间 $T _ { \mathrm { x } }$ 和释放电压 $U _ { \mathrm { s } }$ ，3个特征参数规定阈值向量为 $[ 5 0 ~ \mathrm { m } \Omega$ ，8ms,2.5V]，则经过极差变换后阈值向量为[1，1,0]。通过PCA分析，利用式(3）和式（4）把3个特征参数的初始阈值变为两个主元的阈值。得出第一主元阈值 $\pmb { Y } _ { \mathrm { 1 f } } = 0 . 9 1$ ，第二主元阈值 $Y _ { 2 \mathrm { f } } = 0 . 5 6$ 。

# 4.4主元退化距离分析

将得到第一、二主元时间序列 $\mathbf { } Y _ { 1 } ( t )$ 、 ${ \mathbf { } } Y _ { 2 } ( t )$ 各点值和由式（5）得到的权重因子带入式（1）中得到的数值见表3。

对表中各点进行描点，并用最小二乘法进行曲线拟合，如图2所示。

# 表3主元参数退化距离的时间序列

Tab.3The time series of principal parameter degradation distance   

<html><body><table><tr><td>周数</td><td>主元参数距离</td><td>周数</td><td>主元参数距离</td></tr><tr><td>1</td><td>1.373</td><td>13</td><td>1.052</td></tr><tr><td>2</td><td>1.192</td><td>14</td><td>1.073</td></tr><tr><td>3</td><td>1.161</td><td>15</td><td>1.087</td></tr><tr><td>4</td><td>1.076</td><td>16</td><td>1.075</td></tr><tr><td>5</td><td>1.063</td><td>17</td><td>1.086</td></tr><tr><td>6</td><td>1.059</td><td>18</td><td>1.077</td></tr><tr><td>7</td><td>1.045</td><td>19</td><td>1.068</td></tr><tr><td>8</td><td>0.981</td><td>20</td><td>1.051</td></tr><tr><td>9</td><td>0.993</td><td>21</td><td>1.051</td></tr><tr><td>10</td><td>0.988</td><td>22</td><td>0.949</td></tr><tr><td>11</td><td>0.994</td><td>23</td><td>0.881</td></tr><tr><td>12</td><td>0.991</td><td>24</td><td>0.850</td></tr></table></body></html>

![](images/79560374c67dceef462d365cffa5e43231eb19a9c98f2fe4c858265837eaa85b.jpg)  
图2最小二乘法拟合 Fig.2Least square fitting

可以看出离散点均匀的分布在一条直线两侧，根据曲线的趋势利用线性方程对各个离散点进行拟合，得到的拟合函数为

$$
D ( t ) = p _ { 1 } t + p _ { 2 }
$$

式中，函数系数为： ${ \pmb p } _ { 1 } = - 0 . 0 0 8 ~ 8 6 7 ~ 9$ ， $p _ { 2 } = 1 . 1 6 1 ~ 5$ 。

当产品发生失效时，主元参数阈值距离函数$D ( t ) = 0$ 。可以算出 $t = 1 3 0$ ，即在 $1 2 5 \mathrm { ^ \circ C }$ 的应力条件下该产品伪失效寿命为130周。在实际应用中，相同试验条件下一批同型号的继电器寿命差距是不大的，所以本文的思路是把该方法用到该试验条件下其他航天继电器退化数据上进行类比验证，如果在其他继电器上能得到相差不大的寿命值，则说明该方法具有一定适用性和准确性。从试验的25台继电器中随机选择编号为3#、5#、8#、13#这4台继电器，以所测得数据为例对该方法进行类比验证，得到这4台继电器主元参数退化距离的时间序列见表4。

# 表44台主元参数退化距离的时间序列

Tab.4The time series of principal parameter degradation distance   

<html><body><table><tr><td rowspan="2">周数</td><td colspan="4">主元参数距离</td></tr><tr><td>3#</td><td>5#</td><td>8#</td><td>13#</td></tr><tr><td>1</td><td>1.367</td><td>1.451</td><td>1.453</td><td>1.324</td></tr><tr><td>2</td><td>1.212</td><td>1.340</td><td>1.366</td><td>1.240</td></tr><tr><td>3</td><td>1.135</td><td>1.224</td><td>1.336</td><td>1.212</td></tr><tr><td>4</td><td>1.097</td><td>1.157</td><td>1.288</td><td>1.166</td></tr><tr><td>5</td><td>1.094</td><td>1.134</td><td>1.272</td><td>1.151</td></tr><tr><td>6</td><td>1.092</td><td>1.134</td><td>1.259</td><td>1.141</td></tr><tr><td>7</td><td>1.091</td><td>1.139</td><td>1.253</td><td>1.137</td></tr><tr><td>9</td><td>1.075</td><td>1.129</td><td>1.221</td><td>1.109</td></tr><tr><td>10</td><td>1.067</td><td>1.117</td><td>1.214</td><td>1.105</td></tr><tr><td>11</td><td>1.054</td><td>1.105</td><td>1.216</td><td>1.108</td></tr><tr><td>12</td><td>1.046</td><td>1.098</td><td>1.203</td><td>1.098</td></tr><tr><td>13</td><td>1.045</td><td>1.094</td><td>1.221</td><td>1.117</td></tr><tr><td>14</td><td>1.030</td><td>1.092</td><td>1.220</td><td>1.119</td></tr><tr><td>15</td><td>1.024</td><td>1.088</td><td>1.214</td><td>1.115</td></tr><tr><td>16</td><td>1.010</td><td>1.082</td><td>1.198</td><td>1.101</td></tr><tr><td>17</td><td>1.008</td><td>1.074</td><td>1.192</td><td>1.098</td></tr><tr><td>18</td><td>1.006</td><td>1.067</td><td>1.186</td><td>1.094</td></tr><tr><td>19</td><td>0.996</td><td>1.063</td><td>1.176</td><td>1.086</td></tr><tr><td>20</td><td>0.994</td><td>1.063</td><td>1.170</td><td>1.082</td></tr><tr><td>21</td><td>0.991</td><td>1.062</td><td>1.163</td><td>1.077</td></tr><tr><td>22</td><td>0.982</td><td>1.052</td><td>1.149</td><td>1.065</td></tr><tr><td>23</td><td>0.978</td><td>1.030</td><td>1.136</td><td>1.054</td></tr><tr><td>24</td><td>0.988</td><td>1.018</td><td>1.114</td><td>1.035</td></tr></table></body></html>

根据表4所示的4台主元参数退化距离时间序列进行了寿命预测，得到3#、5#、8#、13#继电器伪寿命值分别 $t _ { 1 } = 1 1 7$ 、 $t _ { 2 } = 1 1 4$ ， $t _ { 3 } = 1 4 0$ 、 $t _ { 4 } = 1 5 0$ 。设由表3所求17#继电器的伪寿命值为 $t _ { 5 }$ ，则5台继电器伪寿命均值 $T = ( t _ { 1 } + t _ { 2 } + t _ { 3 } + t _ { 4 } + t _ { 5 } ) / 5 = 1 3 0 . 2$ 伪寿命标准差： $D = { \mathrm { s t d } } ( t ) = 1 5 . 2$ 。由均值和方差可以看出，将 $1 2 5 \mathrm { ^ \circ C }$ 的应力条件下随机抽取的5台继电器数据带入该方法所预测出的寿命值相差不大。这表明该方法用到其他航天继电器退化数据上进行类比验证时，可以得到相差不大的寿命值，说明该方法能够适用于其他继电器数据，并具有一定准确性，能够实现基于多参数航天继电器性能退化的贮存寿命预测。

# 5 结论

（1）加速贮存试验能够在相对短时间内获得关于继电器工作特性退化的关键信息，通过对退化数据的分析，能够完成航空航天继电器的贮存寿命预测。

(2）本文提供了一种分析多性能参数退化数据的新思路，即主元参数退化距离分析法。给出了参数与相应阈值间退化距离的定义，并引入了主元分析法，给出了不同主元参数在退化距离分析中加权因子的确定方法。最后，预测了航天继电器的贮存寿命。

(3）解决了现有方法基于多元联合概率密度函数假设，以及求解过程较复杂等不足。特别是当产品的性能参数增多时，主元参数退化距离分析法能大大减小计算量。

(4）虽然线性拟合的方法能够直接快速地通过主元退化距离预测出产品的贮存寿命，但是拟合的好坏直接依赖距离数据的质量和数量，存在一定的局限性。因此，还有待进一步研究和完善。

# 参考文献

[1] 王召斌，翟国富，黄晓毅．电磁继电器贮存期接触 电阻增长的动力学模型[J]．电工技术学报，2012, 27(5): 206-211. Wang Zhaobin,Zhai Guofu,Huang Xiaoyi.Kinetic model of contact resistance increment of electromagne tic relay in storage[J].Transactions of China Electrotechnical Society,2012,27(5): 206-211.   
[2] 陆俭国，骆燕燕，李文华，等．航天继电器贮存 寿命试验及失效分析[J]．电工技术学报，2009， 24(20): 54-59. Lu Jianguo, Luo Yanyan,Li Wenhua,et al. Storage life test and failure analysis of aerospace relays[J]. Transactions of China Electrotechnical Society, 2009,24(20): 54-59.   
[3] 钟强晖，张志华，梁胜杰．基于多元退化数据的 可靠性分析方法[J]．系统工程理论与实践，2011, 31(3): 544-551. Zhong Qianghui,Zhang Zhihua,Liang Shengjie. Reliability analysis approach based onmultivariate degradation data[J]. Systems Engineering-Theory & Practice,2011,31(3): 544-551.   
[4] 张国龙，蔡金燕，梁玉英，等．基于距离分析 的多性能参数故障预测方法[J]．电光与控制, 2014(2): 32-35. Zhang Guolong, Cai Jinyan, Liang Yuying, et al. A fault prediction approach for multiple performance measures based on distance analysis[J]. Electronics Optics & Control, 2014(2): 32-35.   
[5] 晁代宏，马静，陈淑英．应用多元性能退化量评估 光纤陀螺贮存的可靠性[J]．光学精密工程，2011, 19(1): 35-40. Chao Daihong,Ma Jing, Chen Shuying.Assessment of storage reliability for FOGs by multivariate degradation data[J].Optics and Precision Engineering,2011,19(1): 35-40.   
[6] 毛端海，董金龙，汪立新，等．基于多元性能退 化量光纤陀螺贮存寿命综合评估[J]．计算机测量 与控制，2014，22(2)：446-449. Mao Duanhai, Dong Jinlong,Wang Lixin,et al. Comprehensive assessment of FOG storage life based on multivariate degradation data[J]. Comuputer Measurement & Control, 2014, 22(2): 446-449.   
[7] 王浩伟，徐廷学，周伟．综合退化数据与寿命数 据的某型电连接器寿命预测方法[J]．上海交通大 学学报，2014，48(5)：702-706. Wang Haowei,Xu Tinxue,Zhou Wei.Lifetime prediction method for missile electrical connector synthesizing degradation data and lifetime data[J]. Journal of Shanghai Jiao Tong University, 2014, 48(5): 702-706.   
[8] 王浩伟，徐廷学，赵建忠．融合加速退化和现场 实测退化数据的剩余寿命预测方法[J]．航空学报, 2014，35(12): 3350-3357. Wang Haowei, Xu Tingxue, Zhao Jianzhong. Residual life prediction method fusing accelerated degradation and field degradation data[J].Acta Aeronautica et Astronautica Sinica,2014,35(12): 3350-3357.   
[9] 赵志草，宋保维，赵晓哲．加速退化试验与加速 寿命试验相结合的产品可靠性评估[J]．系统工程 理论与实践，2014(7)：1916-1920. Zhao Zhicao, Song Baowei, Zhao Xiaozhe.Product reliability assessment by combining accelerated degradation test and accelerated life test[J]. Systems Engineering-Theory & Practice,2014(7):1916- 1920.   
[10] 王淑娟，余琼，翟国富．电磁继电器接触失效机理 判别方法[J]．电工技术学报，2010，25(8)：38-44. Wang Shujuan, Yu Qiong, Zhai Guofu. Discrimination method of contact failure mechanisms for electromagnetic apparatus[J].Transactions of China Electrotechnical Society, 2010,25(8): 38-44.   
[11] 聂鹏，谌鑫．基于主元分析和BP神经网络对刀 具VB 值预测[J]．北京航空航天大学学报，2011, 37(3):364-367，373. Nie Peng Chen Xin.Prediction of tool VB value based on PCA and BP neural network[J]. Journal of Beijing University of Aeronautics and Astronautics, 2011, 37(3): 364-367, 373.   
[12]蒋浩，洪丽，张国江．主元分析结合神经网络的 光伏发电量预测[J]．电力系统及其自动化学报, 2013，25(6):102-105. Jiang Hao, Hong Li, Zhang Guojiang. PV generation system forecasting model based on neutral network and principal components analysis[J]. Proceedings of the CSU-EPSA,2013,25(6): 102-105.