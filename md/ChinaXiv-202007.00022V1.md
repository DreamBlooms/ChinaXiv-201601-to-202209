# 云南大学多通道测光巡天望远镜W巡天曝光时间优化

雷磊，李晋达1，吴金泰1，蒋思艺1，陈丙秋²(1 云南大学物理与天文学院，云南 昆明 650500;2 云南大学中国西南天文研究所，云南 昆明 650500)

摘要：在建的云南大学多通道测光巡天望远镜(Mephisto)预计将在2022年开展W巡天(Mephisto-WSurvey)。Mephisto-W巡天将对北半球可观测天区(约26000平方度)开展多通道多历元测光巡天，为细致描绘银河系结构、深刻理解星系形成和演化理论、精确限制宇宙学模型、深入探究暗物质暗能量本质提供重大契机。本文基于丽江站天文台址监测系统(ASMS)2019全年观测数据，利用机器学习方法模拟了丽江站一年的台址条件模型。简单估算了在不同曝光时间下，Mephisto-W巡天一整年对巡天天区的可观测次数与期望极限星等。考虑到Mephisto-W巡天的科学目标，建议对每个天区单次观测采用曝光2次，每次时长为20秒的曝光模式，在这一曝光模式下，可以实现全年对巡天天区在每组滤波片组合(ugi和vrz)下分别进行约3.8次观测，单次观测r波段极限星等可达22.37等，叠加星等可达23.11等。

关键词：大天区巡天；台址条件；极限星等中图分类号：P141.2 文献标识码：A 文章编号:1007-2276-(2020)X-XXXX-XX

云南大学双一流重点建设项目“多通道测光巡天望远镜”(Multi-channelPhotometric SurveyTelescope，简称Mephisto)目前已在云南天文台丽江观测站开工建设，预计将于2020年底建设完成。Mephisto建成后预计将进行一年的调试与先导巡天。正式巡天将于2022年开始，为期10年。在正式巡天的第一年(2022年)，Mephisto所有观测时间将用于对北半球可观测天区多通道多历元测光巡天(简称为Mephisto-W巡天)。Mephisto-W巡天主要利用ugi和vrz两组滤光片对北半球可观测天区(赤纬δ>-15度，面积约26000平方度)开展多通道测光巡天，巡天面积如图1所示。

![](images/8fb78d92d2f12b5b82cf0db39a4a6f4cec5d2831d77307a3cf11163443185ed4.jpg)  
图1Mephisto-W巡天天区示意图。本图采用赤道坐标系，红线和绿线分别表示银道面和黄道面位置Fig.1TesureyareaofMephsto-Wsureyinquatorialcoodinates.Redandgreelinesmarkthepositionsof teGalacticadElipticplanes,respectively

建成后Mephisto将是国际上首个较大通光口径较大视场的多通道高精度测光巡天光学望远镜。Mephisto主镜1.6米，系统焦比为4.5，可达到3.14平方度的视场。其光学系统设计采用了加改正镜的Ritchey-Chretien (RC)系统，在焦面上放置了由3个立方棱镜组成分色系统和三台CCD相机，总像素超过10亿，像质可以达到好于0.6角秒( $80 \%$ 能量)。通过这一设计，Mephisto可以在三个光学波段对同一天区进行高精度的成像观测，对天体的实时颜色信息进行捕捉，不仅能显著提高巡天效率和颜色定标精度，更重要的是能提供天体的实时颜色信息，为天体分类和后续观测以及分光证认提供依据。Mephisto将在时域天文学和星系宇宙学、银河系考古学与近场宇宙学、恒星物理、太阳系普查等多个研究方向上发挥重要作用。

Mephisto-W巡天将探测到百亿颗恒星、数十亿星系、数百万类星体，获取它们高精度的多波段星等和颜色，以及它们的位置、星等、颜色变化信息，为细致描绘银河系结构、深刻理解星系形成和演化理论、精确限制宇宙学模型、深入探究暗物质暗能量本质提供重大契机。基于Mephisto-W巡天的科学目标，要求Mephisto-W巡天的观测极限星等尽可能深，单次曝光r波段极限星等大于22等，叠加星等大于23等，且观测次数尽可能多，全年大部分天区达到4次观测。本文将基于丽江天文台址监测系统(ASMS)2019全年观测数据，利用机器学习方法模拟丽江站一年的台址条件模型。简单估算在不同曝光时间下，Mephisto-W巡天一整年对巡天天区的可观测次数与期望极限星等，给出Mephisto-W巡天的最佳曝光时间。

# 1丽江观测站全年台址条件的随机森林模型

丽江观测站是中国目前最好的光学天文观测台址之一，已建有2.4米望远镜[1]等多台先进的光学天文望远镜。为了协助丽江2.4米望远镜(LJT)和Mephisto的运行，丽江站在两处高地上各自安装了一组天文台址监测系统(简称ASMS)，丽江2.4米望远镜旁的监测系统为ASMS-A，Mephisto安装址点的监测系统为ASMS-B[2I3]4]。其中ASMS-B从2018年底开始已经投入使用。ASMS系统主要包括四个子系统：气象站、全天信息采集系统、视宁度系统和视频监控系统。这些设备所记录的视宁度数据、云量数据、温度、风速和天光背景数据可以支持对Mephisto巡天的估算和观测环境评价。但由于天气状况与仪器故障等问题，ASMS-B采集的数据的观测时间不连续，丢失了相当长一段时间的数据，ASMS-A与B之间直线距离仅百米，因此本文将基于ASMS-B采集的数据并以ASMS-A数据作为补充建立完整的丽江观测在全年的台址条件模型。

本文利用随机森林回归方法(Random Forest Repressor)来建立完整的丽江观测站2022年台址模型。随机森林(Random Forests)是机器学习当中重要的一种Bagging算法。它采用集成学习方法进行分类和回归，使用平均数来提高预测准确性和控制过度拟合。在训练阶段，随机森林使用自助采样法(bootstrap sampling)从输入训练数据集中采集多个不同的子训练数据集来依次训练多个不同决策树；在预测阶段，随机森林将内部多个决策树的预测结果取平均得到最终结果[5]。本文使用了Python程序包sklearn[，将ASMS采集的2019年观测数据中随机挑选 $7 5 \%$ 的数据作为训练样本，另外 $2 5 \%$ 作为测试样本。

大气视宁度是大气湍流造成的星象随机扩散现象，使获得的天体图像质量下降。大气视宁度与台址的大气温度、风速和地形等有关，是现代天文选址的最重要指标之一[7]。由于视宁度与昼夜温度、风速有关，而视宁度随时间的变化可以分为两个较为明显的随时间变化关系：一是在一年当中随月份和季节的变化，这部分变化可以用积日值(days of the year)作为自变量；二是在一天之中随气温等因素的变化，这一部分可以用本地太阳平时作为自变量。所以在模型训练时需要将时间序列数据整理成积日值和本地时两部分的形式。而ASMS观测数据中，气象站采集的信息如温度与风速的采集时间与其他系统的时间并不同步。因此本文采用随机森林回归方法，先对温度和风速分别建立以时间(积日值和本地时组成)为特征变量的随机森林回归模型，从而得到在视宁度、云量和背景天光观测时间点上的温度和风速数据。再以积日值、本地时、风速和温度作为四个特征变量，结合视宁度数据，由随机森林回归方法建立一个特征变量与视宁度的关系模型。基于该模型可以预测丽江观测站全年任意时间的视宁度。对测试样本的比较结果(图2左)显示，视宁度模型训练得分为0.89，差值弥散为0.016。

云量是帮助确定望远镜是否开机工作的重要气象数据。在ASMS的观测数据中，云量值由整数0-10来表示，其中云量数值达到10时全天覆盖有云，云量数值为0时天空无云。云量的变化也与温度和风速相关。而云量随时间的变化也可以看作随年月季节的长期变化以及一天内的天气变化两个部分。所以在云量模型训练与视宁度类似，也是积日值、本地时、风速和温度这四个特征变量。对测试样本的比较结果(图2中)显示，云量模型的训练得分为0.967，差值弥散为0.645。

天光背景是天文观测条件的一个重要指标，它限制着望远镜的观测极限星等[8]。天光背景随时间的变化与当日月相(用积日做自变量)以及一天之中的太阳、月亮高度等因素有关(用本地时作为自变量)。所以对天光背景，我们采用了积日值、本地时和云量这三个特征变量。对测试样本的比较结果(图2右)显示，天光背景模型训练得分为0.999，差值弥散为0.103。

![](images/3cf099f5867b331cd785fbfa2931f0dbec1b492db57bd3883755e47fc17eee0f.jpg)  
图2 测试样本的视宁度、云量和背景天光观测值与随机森林模型给出的模拟结果比较。图中红线为y=x线 Fig2Comparsonsbtwntheseing,cloudandskybrightnessvaluesfromthetestsamplesadtosefromtheRandomForestmodelsRed lines are the $\mathbf { y } { = } \mathbf { x }$ curves

由此我们获得了丽江观测站全年视宁度、云量和天光背景的变化模型。图3给出了积日从66.5天到69.5天的视宁度、云量和天光背景的观测数据和模型数据变化图。如图3左66.5天到67.5天数据所示，2019年的ASMS视宁度、云量以及天光背景的观测数据(红色点)有很大一部分是缺失的，我们的随机森林模型给出预测数据(蓝色点)则完整描述了这些量的变化情况。在有观测数据的时段，模型的预测结果与观测数据非常吻合。我们建立的随机森林模型与原观测数据的高度一致，并合理地弥补了观测缺失的数据信息。

![](images/95a6796738cc593460c8d33abe2b925970ac1699fedb6634b51c0dd136169afb.jpg)  
图3 积日为6.5到69.5天之间ASMS观测的(图中红色叉号)以及随机森林模型给出的(图中蓝点)视宁度(左图)、云量(中图)和天光 背景(右图)变化比较图 Fig3Comparisonsbetweenvariationsofseeing(left panel),cloud(middlerpanel)andskybrightness(rightpanel)fromtheAM observations(redcrosses)andthosefromtheRandomForest models (bluedots)duringdaysofthe yearbetween 6.5and 69.5.

基于上述随机森林模型，我们可以估算丽江观测站Mephisto 台址位置全年的视宁度、云量和天光背景的分布情况。模型结果显示，全年Mephisto 台址的可观测时间(视宁度小于2角秒，云量小于等于3，太阳高度角低于-12度)为1867小时。全年可观测时间内，视宁度中值为1.06角秒，小于1角秒的时间占 $3 9 . 4 7 \%$ ；云量值为0的时间占 $6 6 . 4 5 \%$ ；天光背景中值为21.30 等(V波段)，大于20等的观测时长达到了 $6 9 . 7 6 \%$ 。

# 2Mephisto-W巡天的曝光时间优化

# 2.1天区观测次数与极限星等估算

为获取天体精确的自行、三角视差等天测数据，以及从数据中寻找变源、获取天体的实时颜色变化信息，我们需要对观测天区进行多次时域观测，观测次数越多越好。而为了探测到更暗的天体，达到更深的探测体积，我们需要对观测天区进行深度曝光，以达到更深的极限星等。这两个目标对曝光时间的要求是相互矛盾的，更多的观测次数要求曝光时间越短越好，而更深的极限星等则要求更长的曝光时间。此外，在可观测时间内，望远镜除了曝光以外，还需要从一个天区挪到另一个天区，如果曝光时间过短，那么望远镜则花费了更多的时间在天区挪动上。

我们首先估算在不同的曝光时间下，Mephisto-W巡天对整个W天区的观测次数。我们的台址条件模型给出Mephisto台址全年可观测时间为 $t _ { t o t a l } = 1 8 6 7$ 小时。Mephisto-W巡天天区数为$n _ { f i e l d } = 1 3 7 4 2$ 。W巡天目前的观测模式将对每个天区进行两次曝光，两次曝光之间望远镜中心指向进行微小的摆动，以覆盖CCD芯片之间的空隙。平均而言，单个天区的观测时间主要分为四个部分：(1)曝光总时长 $2 t _ { _ { e x p o s u r e } }$ ；(2)两次曝光之间的望远镜摆动以及稳定时间 $t _ { \mathit { d i z z e r } }$ ； (3)望远镜两个天区之间转换的挪动时间以及稳定 $t _ { t r a n s f o r m }$ ；(4)CCD相机曝光后的读出时间。设Mephisto的转动速度能达到2度每秒，转动加速度能达到1度每二次方秒，因此望远镜可以在5秒内赤经和赤纬分别挪动6度，因此我们把望远镜从一个天区到另一个天区的平均挪动时间设为5秒。而两次曝光之间望远镜的摆动非常微小，一般小于0.6度，因此本文中这个时间忽略不计。望远镜挪动后，需要稳定下来，Mephisto的稳定时间是10秒。因此望远镜每次更好观测天区并稳定下来需要的时间是 $t _ { { t r a n s f o r m } } = 1 5$ 秒，两次曝光之间的摆动及稳定时间为 $t _ { \mathit { d i z z e r } } = 1 0$ 秒。Mephisto的CCD相机采用e2v290芯片，读出时间可以控制在10秒内，由于CCD读出可以与望远镜的运动过程同步进行，故不额外占用时间。由此我们可估算曝光总时长分别在： $2 { \times } 1 0$ 秒、 $2 { \times } 1 5$ 秒、 $2 { \times } 2 0$ 秒、$2 { \times } 2 5$ 秒、 $2 { \times } 3 0$ 秒、 $2 { \times } 3 5$ 秒、 $2 { \times } 4 0$ 秒、 $2 { \times } 4 5$ 秒、 $2 { \times } 5 0$ 秒、 $2 { \times } 5 5$ 秒、 $2 { \times } 6 0$ 秒的情况下，全年对每个天区的平均观测次数 $N$ ，如下式，

$$
N = \frac { t _ { t o t a l } } { 2 \cdot n _ { f i e l d } \cdot ( 2 t _ { e x p o s u r e } + t _ { d i z z e r } + t _ { t r a n s f o r m } ) }
$$

曝光时长占比 $\eta$ 是指全年望远镜用来曝光花费的时间在总观测时间当中所占的比重，标志着巡天的时间利用度，由下式计算：

$$
\eta = \frac { 2 t _ { e x p o s u r e } } { 2 t _ { e x p o s u r e } + t _ { d i z z e r } + t _ { t r a n s f o r m } }
$$

一个好的曝光模式应该有较高的曝光时长占比,也即望远镜应该用更多的时间去观测，则应尽量趋近于1。如果它偏小，说明望远镜的很多时间浪费在转到和稳定上。

望远镜观测的噪声来源主要有目标源噪声、天光背景、CCD读出噪声以及暗流噪声。对给定曝光时间，结合望远镜的通光效率、CCD的性能以及丽江观测站的台址信息，我们可以估算巡天的极限星等。本文分别计算了曝光时间为 $2 { \times } 1 0$ 秒、 $2 { \times } 1 5$ 秒、 $2 { \times } 2 0$ 秒、 $2 { \times } 2 5$ 秒、 $2 { \times } 3 0$ 秒、 $2 { \times } 3 5$ 秒、 $2 { \times } 4 0$ 秒、 $2 { \times } 4 5$ 秒、 $2 { \times } 5 0$ 秒、 $2 { \times } 5 5$ 秒、 $2 { \times } 6 0$ 秒情况下，信噪比为5时不同滤光片的极限星等。信噪比SNR计算如下式所示，

$$
S N R = \frac { f l u x } { n o i s e } = \frac { F } { \sqrt { F + B + R + D } }
$$

其中flux为目标源在CCD上产生的电子数,noise为总噪声电子数。 $F$ 为目标源的信号， $B$ 为天光背景噪声， $R$ 为CCD读出噪声， $D$ 为CCD暗流噪声。

结合单次曝光极限星等与全年天区曝光次数，我们可以估算巡天天区的全年叠加星等，叠加信噪比公式如下式，

$$
S N R _ { c o a d d e d } = S N R \cdot \sqrt { N }
$$

本文总观测次数N保留了一位小数，对于小数部分，分配额外的一次观测次数给部分天区，也即该部分天区的观测次数变成（N的整数部分） $+ 1$ ，这部分天区的数量占总天区数量的比例与小数数值相等，而剩余天区观测次数变成N的整数部分。将未额外增加观测次数的天区的叠加星等和拥有一次额外观测次数的天区的叠加星等进行加权平均，从而得到全部天区最终的平均叠加星等。

# 2.2结果与讨论

根据2.1，对上述11组曝光模式，由公式(1)求得不同曝光模式的观测次数，由公式(2)求得不同曝光模式的曝光时长占比。在每一次观测都曝光两次、信噪比阈值SNR=5的情况下，我们通过公式(3)分别估算了11组曝光模式的各个波段的极限星等。最后利用公式(4)计算得到不同波段的全年叠加星等。经过计算，Mephisto-W巡天11组曝光模式下每组滤波片可观测次数、曝光时长占比、六个波段的单次曝光极限星等和全年叠加星等结果如下表1所示。

表1不同曝光方案下Mephisto-W巡天结果  
Tab.1 The results of different exposure modes for Mephisto-W survey   

<html><body><table><tr><td>曝光时长t/s</td><td>巡天天区平均可 观测次数N</td><td>曝光时长 占比n</td><td>uvgriz单次曝光极限星等/mag</td><td>uvgriz全年叠加星等/mag</td></tr><tr><td>2×10</td><td>5.4</td><td>0.44</td><td>20.94,20.97,22.01,21.83,21.50,20.60</td><td>21.90,21.93,22.97,22.78,22.44,21.55</td></tr><tr><td>2x15</td><td>4.5</td><td>0.55</td><td>21.34,21.37,22.37,22.16,21.80,20.92</td><td>22.19,22.21,23.20,22.99,22.62,21.76</td></tr><tr><td>2×20</td><td>3.8</td><td>0.62</td><td>21.63,21.67，22.60,22.37,21.99,21.14</td><td>22.38,22.40,23.34,23.11,22.73,21.88</td></tr><tr><td>2×25</td><td>3.3</td><td>0.67</td><td>21.84,21.86,22.78,22.54,22.14,21.30</td><td>22.51,22.52,23.44,23.19,22.80,21.95</td></tr><tr><td>2x30</td><td>2.9</td><td>0.71</td><td>22.01,22.02,22.92,22.66,22.26,21.42</td><td>22.61,22.62,23.51,23.25,22.84,22.01</td></tr><tr><td>2x35</td><td>2.6</td><td>0.74</td><td>22.15,22.16,23.03,22.77,22.36,21.53</td><td>22.68,22.69,23.55,23.28,22.87,22.05</td></tr><tr><td>2x40</td><td>2.3</td><td>0.76</td><td>22.27,22.28,23.13,22.86,22.44,21.62</td><td>22.74,22.75,23.59,23.32,22.90,22.08</td></tr><tr><td>2x45</td><td>2.1</td><td>0.78</td><td>22.37,22.38,23.21,22.93,22.52,21.69</td><td>22.80,22.80,23.63,23.35,22.93,22.11</td></tr><tr><td>2x50</td><td>2.0</td><td>0.80</td><td>22.47,22.47,23.28,23.00,22.58,21.76</td><td>22.84,22.85,23.66,23.37,22.95,22.13</td></tr><tr><td>2×55</td><td>1.8</td><td>0.82</td><td>22.55,22.55,23.35,23.06,22.64,21.82</td><td>22.87,22.87,23.66,23.38,22.95,22.14</td></tr><tr><td>2x60</td><td>1.7</td><td>0.83</td><td>22.62,22.62,23.41,23.12,22.69,21.88</td><td>22.89,22.89,23.67,23.38,22.95,22.14</td></tr></table></body></html>

如表1所示，在不同的曝光时间下，W巡天2022年平均可观测次数最大可达到5.4次，对应单次曝光时长最短的方案为 $2 { \times } 1 0$ 秒；最少为1.7次，对应 $2 { \times } 6 0$ 秒。当单次曝光时长大于 $2 { \times } 2 5$ 秒时，巡天天区平均可观测次数低于3次。考虑诸如变星证认等科研工作，每年一到两次的观测显然不能满足Mephisto-W巡天的科学目标要求。而对于曝光时间较短的方案，即 $2 { \times } 1 0$ 秒、 $2 { \times } 1 5$ 秒、 $2 { \times } 2 0$ 秒、 $2 { \times } 2 5$ 秒四种方案，其中 $2 { \times } 1 0$ 秒方案不论是单次曝光极限星等还是全年叠加星等，均明显低于另外三种方案，无法满足巡天科学目标的要求。 $2 { \times } 2 5$ 秒方案能达到4次观测的天区仅约有 $30 \%$ 也不是很好的选择。

剩下的两种观测方案中， $2 { \times } 1 5$ 秒和 $2 { \times } 2 0$ 秒的方案对应的全年可观测次数分别为4.5和3.8次，其中 $2 { \times } 2 0$ 秒的观测方案的单次曝光极限星等和全年叠加星等略深。此外， $2 { \times } 1 5$ 秒的曝光时长占比n仅为0.55，也就是说望眼镜将近一半的时间会被花费在转动和稳定上。对于 $2 { \times } 2 0$ 秒的方案，$\eta$ 可达到0.62，相比于 $2 { \times } 1 5$ 秒有较大提升，因此我们认为 $2 { \times } 2 0$ 秒的方案更优。

综上所述， $2 { \times } 2 0$ 秒的曝光时间为Mephisto-W巡天的最佳观测方案。在此曝光模式下，在一整年的时间内Mephisto可分别在两组滤光片平均各观测3.8次， $\boldsymbol { r }$ 波段的单次曝光极限星等达到

22.37等，所有天区中约有 $80 \%$ 的天区可达到4次观测，对应r波段全年叠加星等达到23.15等，剩下约 $2 0 \%$ 的天区全年可观测3次，对应r波段全年叠加星等达到22.99等。

# 3总结

为了寻找Mephisto-W巡天的最佳曝光模式，以尽可能同时达到较深的极限星等和较多的观测次数，我们基于2019年丽江站天文台址监测系统(ASMS)的大气视宁度、云量和天光背景观测数据，用随机森林回归方法建立了Mephisto台址条件模型。基于模型的预测结果，我们估算了在不同曝光模式下，Mephisto-W巡天一整年对巡天天区的平均观测次数，单次曝光极限星等以及全年叠加星等，结果如表1所示。结果显示，符合Mephisto-W巡天科学目标的最佳曝光模式为 $2 { \times } 2 0$ 秒，在这一曝光模式下，Mephisto-W巡天可在一年中对北天26000平方度天区分别在两组滤光片组合下平均观测3.8次。即 $80 \%$ 的观测天区能达到4次观测， $20 \%$ 的天区3次观测。全年叠加星等达22.38等(u波段),22.40等(v波段),23.34等(g波段),23.11等(r波段),22.73等(i波段),21.88等(z波段)。

在利用机器学习方法建立丽江站台址条件模型过程中，由于观测数据的限制，本文只采用了2019年一年的数据。实际上天文观测站的台址条件还存在更长的时间变化趋势，这个在本文中是没有考虑的。未来我们计划收集丽江站过去10年的历史气象数据，研究丽江站台址条件的长时间变化趋势。

# On the exposure time of the Mephisto-W survey

Lei Lei1,Li Jindal,Wu Jintai',Jiang Siyi',Chen Bingqiu (1 School of Physics and Astronomy,Yunnan University，Kunming 65o5oo，China; 2 South-Western Institute For Astronomy Research，Kunming 6505Oo， China)

Abstract: The multi-channel photometric survey telescope (Mephisto) that is under construction, is expected to carry out the Mephisto-W Survey in 2O22.The Mephisto-W survey is a multi-channel and multi-epoch photometric survey that covers the observable northern sky (about 26ooO sq.deg). The survey willprovide an opportunity to describe the detailed structure of the Milky Way,to explore the formation and evolution history of galaxies,to accurately constrain the cosmology model,and to understand the nature of dark matter and dark energy.Based on the data from Astronomical Site Monitoring System (ASMS) in Lijiang Observatory during 2O19, we have constructed models of the variations of values of seeing,cloud and sky brightnessin Lijiang Observatory for a entire year by a machine learning method. Based on the models,we simply estimate the number of epochs and the expected limiting magnitudes of the Mephisto-W survey. To achieve the scientific goals of Mephisto-W survey, it is recommended to take the 2 times 2Os exposure mode.That is for each visit, we observe a given field twice, with each time of 2Os exposure time.In this mode, we are able to observe the survey about 3.8 times for both the ugi and vrz filter combinations. The expected 5 sigma $r$ band depth of the single visit is 22.37 mag and co-added depth in one year 23.11 mag.

Key words: Large-area survey; Site conditions; Limiting magnitude

# 参考文献：

[1]WANGChuan-Jun,BaiJin-Ming,FanYu-Fengetal.Lijiang2.4-meterTelescopeanditsinstruments[J].ResearchinAstroomyand Astrophysics (RAA),[S.l.],v.19,n.10,p.149,sep.2019.ISSN2397-6209.[2]Xin YX,Bai JM,LunBL,et al. Astronomical Site Monitoring System atLijiang Observatory[J]. RAA,inpressarXiv:2004.12128,2020[3]辛玉新，王传军，范玉峰,等．丽江站台址信息监测系统[J].天文学进展,2017,035(003):367-380.[4]辛玉新，范玉峰，伦宝利,等．长期视宁度监测DIMM系统设计方案[J]．天文研究与技术，2012(04):62-69.[5]Breiman,L.Random Forests[J]. Machine Learning 45,5-32(2001).[6]Fabian Pedregosa,Gael Varoquaux,Alexandre Gramfort etal.Scikit-learm: Machine Learning in Python., JMLR[J].12(85):2825-2830,2011.[7]刘子忠,栾蒂,于建明,等．高美古全夜视宁度的变化[J].云南天文台台刊，1999，1：42-50.[8］胡平，李锐，王娜，魏鹏．南山站的光学观测环境监测与分析．天文研究与技术，2017，14(4)：495-501.

收稿日期：2020-XX-XX； 修订日期：2020-XX-XX\*基金项目：国家级大学生创新训练项目201910673001；国家自然科学基金11803029；云南大学科研经费C176220100007.作者简介：雷磊，男，本科生，研究方向：测光巡天、变星、星际介质.Email:Astro_lei@outlook.com通讯作者：陈丙秋，男，副教授，主要从事银河系三维消光、尘埃、星际介质、银河系结构、变星、测光/光谱巡天方面的研究工作．Email: bchen@ynu.edu.cn