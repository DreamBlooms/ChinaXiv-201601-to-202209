# 关中平原PM2.5浓度周期性变化规律及成因分析

贾册，王亚琼，杨啸（中国人民大学环境学院，北京 100872)

摘要：采用Morlet小波分析法和交叉小波分析法,对关中五市2013年11月15日至2019年3月15日期间的 $\mathrm { P M } _ { 2 . 5 }$ 浓度周期性变化特征及成因进行分析。结果表明：(1)关中五市的 $\mathrm { P M } _ { 2 . 5 }$ 浓度变化具有显著区域性和周期性， $\mathrm { P M } _ { 2 . 5 }$ 浓度在夏季呈现低浓度稳定状态,秋冬季呈现高浓度状态，并呈现出365d左右、36d左右以及14d左右的周期性变化规律。(2)秋冬季，关中五市的 $\mathrm { P M } _ { 2 . 5 }$ 浓度以14d左右的周期性变化为主。 $\mathrm { P M } _ { 2 . 5 }$ 浓度14d左右的周期性变化与风向、风速和气压三项气象因子基本为负相关关系，与湿度呈现落后1/8个相位周期，与气温基本无相关关系。（3）关中五市秋冬季 $\mathrm { P M } _ { 2 . 5 }$ 浓度周期性变化主要是由运城、三门峡、洛阳和关中城市等区域形成的局地静稳气流(该类气流占 $2 1 . 0 8 \%$ ,在该类气流下 $\mathrm { P M } _ { 2 . 5 }$ 不断积累)和从蒙古国、内蒙古等地输入的气流(该类气流占 $2 3 . 8 6 \%$ ,在该类气流下积累的 $\mathrm { P M } _ { 2 . 5 }$ 得到清除)周期性交替所致。

关键词：关中平原； $\mathrm { P M } _ { 2 . 5 }$ 浓度；周期性变化；成因分析

关中平原位于陕西省中部地区，位于渭南、西安、宝鸡、咸阳和铜川五市(也称关中五市),被北山山系、秦岭以及崤山等高海拔山脉环绕，形成了独特的地形气候[1-3]。随着关中五市经济的迅速发展，人为活动源排放污染物不断增加，秋冬季重污染天气频发[4-6]。针对关中平原的 $\mathrm { P M } _ { 2 . 5 }$ 污染问题,多数研究集中在应用WRF等污染扩散模型对成因进行分析[7-8],从季节、月等长时间尺度变换的角度对 $\mathrm { P M } _ { 2 . 5 }$ 变化规律的研究较少。分析 $\mathrm { P M } _ { 2 . 5 }$ 周期性变化趋势，有利于优化 $\mathrm { P M } _ { 2 . 5 }$ 预测方法和更好地治理 $\mathrm { P M } _ { 2 . 5 }$ 污染[9]。小波分析是研究时间序列中周期性现象的有效方法，尤其在识别随时间变化的潜频率方面效果好[10]。自1980年代初以来,小波分析大量应用于信号和图像处理、气象、水文变化、地球物理和经济学等方面[1I-14]。最近几年,李梓铭[15]、王海鹏[16]、周静等采用小波分析方法分别对北京、兰州、太原地区的 $\mathrm { P M } _ { 2 . 5 }$ 长时间的浓度变化趋势进行分析，识别 $\mathrm { P M } _ { 2 . 5 }$ 变化规律。本研究采用趋势分析、小波分析、交叉小波分析等方法，研究关中平原的 $\mathrm { P M } _ { 2 . 5 }$ 发展规律、变化特征、影响因素，将有助于了解关中平原 $\mathrm { P M } _ { 2 . 5 }$ 污染分布特征、变化规律及成因。

# 1研究方法

# 1.1数据来源

$\mathrm { P M } _ { 2 . 5 }$ 数据和风速、风向、气温、气压、湿度等气象数据来自关中五市空气质量国控监测点。研究时段为2013年11月15日至2019年3月15日，气象数据从2014年11月15日至2019年3月15日，覆盖关中五市6个冬防期(11月15日至次年3月15日）。后向轨迹模式(HYSPLIT)聚类分析所用的气象场数据来自美国国家海洋和大气管理局(NOAA)(ftp://arlftp.arlhq.noaa.gov/pub/archives/reanalysis/)。使用R软件WaveletComp包进行Morlet小波分析和交叉小波分析[17]。

# 1.2Morlet小波分析方法

经典的傅立叶变换可以把时间序列变换到频域，但只能单独从时域或频域分析时间序列。小波变换克服了时域和频域不能兼顾的缺点，可以从时域和频域两个角度同时分析时间序列。Morlet小波通过频移保持形状，在时间分辨率基本无损失的情况下，对不同频带的波进行有效分离和级数重构，具有良好的时间聚集性、较高的频率分辨率、包含相位信息等特点[18-19]。本研究选用Morlet小波对关中平原的 $\mathrm { P M } _ { 2 . 5 }$ 的周期性进行分析。Morlet小波的时域、频域表达式为：

$$
\psi _ { 0 } ( t ) = \pi ^ { - 1 / 4 } \mathrm { e } ^ { i \omega _ { 0 } t } \mathrm { e } ^ { - t ^ { 2 } / 2 }
$$

式中： $\mathbf { \Phi } _ { t }$ 为时间; $\omega _ { \scriptscriptstyle 0 }$ 是无量纲频率。当 $\omega _ { \scriptscriptstyle 0 } = 6$ ，小波尺度 $s$ 与傅里叶周期基本相等，尺度项与周期项可以相互替代。

将小波功率谱 $\left| W _ { n } ( s ) \right| ^ { 2 }$ 在某一周期上进行时间平均，可以得到一幅展示时间系列在某一尺度上的波动特征及其随时间变化的小波全谱，小波全谱能够表明时间系列真实功率谱的无偏、一致估计[10.20-21]由于小波全谱可以显示出背景谱，通过小波全谱图，可以清晰辨别时间系列的周期波动特征和强度。

$$
\overline { { \boldsymbol { W } } } ^ { 2 } ( s ) = \frac { 1 } { n } \sum _ { n = 0 } ^ { n - 1 } \bigl | \boldsymbol { W } _ { n } ( s ) \bigr | ^ { 2 }
$$

式中： $n$ 为总时间个数； $W _ { n } ( s )$ 为连续变换小波函数。

# 1.3交叉小波分析

交叉小波分析可以比较两个时间序列 $X _ { t }$ 和 $Y _ { t }$ 的频率，得出两个序列在某些时间段内的共振周期和相位情况。两个时间序列的交叉小波谱图XWT为$\boldsymbol { W } ^ { X Y } = \boldsymbol { W } ^ { X } \boldsymbol { W } ^ { Y ^ { * } }$ ,交叉小波功率为 $|  W ^ { X Y } |$ 。同样,交叉小波功率所反映的周期随时间变化的性质，可以用全谱图进行可视化展示[10.22]。交叉小波幂的置信度可以从两个卡方分布的乘积的平方根得出，其置信

度公式如下：

$$
R _ { \mathbf { \eta } _ { n } } ^ { 2 } ( s ) = \frac { \left| S \big [ W _ { n } ^ { X Y } ( s ) \big ] \right| ^ { 2 } } { S \bigg [ W _ { n } ^ { X } ( s ) \big ] ^ { 2 } \bigg ] \times S \bigg [ \Big | W _ { n } ^ { Y } ( s ) \Big | ^ { 2 } \bigg ] }
$$

交叉小波变换包含有关两个序列的同步性信息，这些信息取决于一个序列的任何周期分量相对于另一个序列相应分量的局部相位差情况。相位差可以转换为间隔 $\left[ - \pi , \pi \right]$ 中的某个角度的差值，相位差的大小可以反映两序列的滞后特性，正负可以反映两序列的主导系列[12]。相位差公式如下：

$$
\varphi _ { x y } = \arctan \left( \frac { I \big [ W _ { n } ^ { X Y } ( s ) \big ] } { R \big [ W _ { n } ^ { X Y } ( s ) \big ] } \right)
$$

# 2结果与讨论

# 2.1关中五市 $\mathbf { P M } _ { 2 . 5 }$ 浓度变化趋势

根据关中五市 $\mathrm { P M } _ { 2 . 5 }$ 浓度从2013年11月15日至2019年3月15日的月尺度浓度变化趋势（图1），$\mathrm { P M } _ { 2 . 5 }$ 浓度存在明显的季节性波动，冬防期为当年浓度变化的波峰期，夏季为浓度波谷期。在 $\mathrm { P M } _ { 2 . 5 }$ 浓度的波动过程中，风速、风向等气象因素对于 $\mathrm { P M } _ { 2 . 5 }$ 的生成、转移和去除有密切的关系[23]。根据图2,关中五市 $\mathrm { P M } _ { 2 . 5 }$ 大于 $8 0 \ \mathrm { m g \cdot m ^ { - 3 } }$ 时,风向分布基本在东北风至北风之间，风速分布在 $0 \sim 4 ~ \mathrm { m \cdot s ^ { - 1 } }$ 之间，当 $\mathrm { P M } _ { 2 . 5 }$ 浓度值超过 $1 1 0 ~ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ 时，基本处于微风静稳天气。由于关中五市 $\mathrm { P M } _ { 2 . 5 }$ 浓度波动存在一致的变化趋势，高浓度 $\mathrm { P M } _ { 2 . 5 }$ 发生时风速、风向等气象条件基本一致，推断关中平原的 $\mathrm { P M } _ { 2 . 5 }$ 浓度变化存在较强区域性。

![](images/baff173bf922bb3bf72d383d4a7dfb0b03c1e3d3a82ea6bba67fda8aba9ec33b.jpg)  
图1关中五市 $\mathrm { P M } _ { 2 . 5 }$ 浓度变化趋势  
Fig.1 Trend of $\mathrm { P M } _ { 2 . 5 }$ concentration in five cities of Guanzhong

![](images/85d1589a0bb6f13af8531780f88abd1a1c36e19428b9436fea5547389319be42.jpg)  
图2关中五市 $\mathrm { P M } _ { 2 . 5 }$ 浓度与风速风向分布  
Fig 2 $\mathrm { P M } _ { 2 . 5 }$ concentration and wind speed and direction in five cities of Guanzhong

# 2.2关中五市 $\mathbf { P M } _ { 2 . 5 }$ 周期变化规律

为分析2013—2019年关中五市 $\mathrm { P M } _ { 2 . 5 }$ 的时间周期特征，分别对关中五市2013—2019年日均 $\mathrm { P M } _ { 2 . 5 }$ 浓度的时间序列作Morlet小波变换，进行小波功率谱图分析(图3)。在小波谱图中，白色阴影包围的蓝色区域为小波边界效应影响锥，其周期性特征存在较高不确定性，白色粗实线所包围的红色区域表示通过显著性水平为 $\scriptstyle a = 0 . 1$ 的噪声检验，其对应的时间段具有显著周期性。

从小波谱图中发现，关中五市 $\mathrm { P M } _ { 2 . 5 }$ 浓度在冬防期间均存在 $4 \sim 3 2 \mathrm { ~ d ~ }$ 的显著周期性变化，与关中平原在冬防期间周期性出现雾霾天气的现象吻合。结合小波功率曲线图可以看出，关中五市 $\mathrm { P M } _ { 2 . 5 }$ 存在两个显著的周期，第一主周期均为365d左右，第二主周期均为14d左右，这两个周期均通过了 $9 0 \%$ 置信度检验。同时，咸阳市、西安市和渭南市36d左右，宝鸡市和铜川市32d左右的周期变化也通过了$9 0 \%$ 的置信度检验。此外，咸阳市、西安市和渭南市存在6d左右的周期变化，宝鸡市和铜川市存在7d左右的周期变化，关中平原的 $\mathrm { P M } _ { 2 . 5 }$ 变化整体存在星期效应。

分析关中平原2013—2019年 $\mathrm { P M } _ { 2 . 5 }$ 长期变化、季节变化以及短期变化特征。以西安市为例，绘制第一主周期365d、第二主周期14d、季节性周期36d和星期效应7d时间尺度下的小波时序图， $\mathrm { P M } _ { 2 . 5 }$ 浓度在夏季保持低浓度稳定状态，春季有小范围波动，秋冬季呈现出强烈的震动性，从36d到7d之间，震荡周期越来越短，频率越来越高，在12月至次年1月期间达到最大振幅。从图4可知，在2016—2017年冬防期间，7d和14d周期下的 $\mathrm { P M } _ { 2 . 5 }$ 浓度波动幅度明显高于其他年份。

# 2.3 $\mathbf { P M } _ { 2 . 5 }$ 浓度周期性变化与气象因素之间的关系

通过以上分析可知，关中五市的 $\mathrm { P M } _ { 2 . 5 }$ 浓度周期变化呈现区域性特征。以西安市为例，分析风向、风速、气压、气温和湿度对 $\mathrm { P M } _ { 2 . 5 }$ 周期性的影响。将西安市 $\mathrm { P M } _ { 2 . 5 }$ 浓度的时间序列分别与各气象因子作交叉Morlet小波变换，进行交叉小波功率谱图分析，进一步分析 $\mathrm { P M } _ { 2 . 5 }$ 浓度周期。在交叉小波谱图中（图5)，白色阴影包含的蓝色区域为小波边界效应影响锥，白色粗实线包围的红色区域表示通过显著性水平为 $\scriptstyle a = 0 . 1$ 检验，箭头表示两序列之间的相位关系，4 $\stackrel { \cdot } {  }$ ”表示 $\mathrm { P M } _ { 2 . 5 }$ 与气象数据之间为同相位,二者为正相关关系，‘ $ \ "$ 表示 $\mathrm { P M } _ { 2 . 5 }$ 与气象数据之间为反相位，二者为负相关关系，“」"和“↑”分别表示 $\mathrm { P M } _ { 2 . 5 }$ 与气象数据相比提前和落后1/4个周期，非线性相关。

从图5可以看出，冬防期间 $\mathrm { P M } _ { 2 . 5 }$ 浓度与风向、风速、气压、湿度在周期 $8 \sim 3 2 { \mathrm { ~ d ~ } }$ 内呈现明显共振，形成了14d左右的第二主震荡周期、7d左右的第三震荡周期、36d左右的震荡周期。 $\mathrm { P M } _ { 2 . 5 }$ 与风向、风速、气压基本为负相关，与湿度呈现落后1/8个相位周期。 $\mathrm { P M } _ { 2 . 5 }$ 浓度与风向、气压、湿度在2016一2017年冬防期间，在7d左右和14d左右的共振程度明显高于其他年份，说明关中平原2016一2017年冬防期间的 $\mathrm { P M } _ { 2 . 5 }$ 浓度较其他年份高，受到气象因素的不利影响。

![](images/c349216ceba7a28253351c9b9bc62f6e20c4f341ed4325b1beef3fb97a947e35.jpg)  
图3关中五市 $\mathrm { P M } _ { 2 . 5 }$ 小波谱图及小波功率曲线分布

![](images/b5883c326d119bd77a7e912ba7eedb8634518e76f97472da2ddd1037dadeeb96.jpg)  
Fig.3 $\mathrm { P M } _ { 2 . 5 }$ Wavelet spectrum and wavelet power curve of five cities in Guanzhong   
图4特定时间尺度的小波时序  
Fig.4Wavelet time series of specific time scale

![](images/8b819540e8734d1f80515de1e1b42a9a918b472ad6e63532ce287e4d00a8a131.jpg)  
图5西安市 $\mathrm { P M } _ { 2 . 5 }$ 浓度与气象因子的交叉小波谱  
Fig.5Cross wavelet spectrum of $\mathrm { P M } _ { 2 . 5 }$ concentration and meteorological factors in Xi'an

# 2.4周期性变化成因分析

在北半球冬半年平流层中，存在显著的 $1 0 \sim 2 0$ d双震荡周期[24]和 $3 0 \sim 6 0 \mathrm { ~ d ~ }$ 的季节震荡周期[25-26]等低频振荡，这些震荡导致了风速、风向、气压等气象要素的变化,在水平方向上由东向西传播[27]。通过后向轨迹聚类分析，可以将具有相似气象因素的气流进行聚类分组，研究相似地理起源的数据所对应的污染物传输情况[11,8]。通过以西安市为起点（图6)，对2013年11月15日至2019年3月15日期间的近地面( $1 0 \mathrm { ~ m ~ }$ )5d时长的后向轨迹气流以季节尺度（春季：3—5月，夏季：6—8月，秋季：9—11月，冬季12一次年2月)进行聚类，发现西安市四季均存在从运城、三门峡、洛阳、渭南等地输送的西风、西北风局地气流，以及从天水、陇南和宝鸡、咸阳等地输送的东风、东北风长距离气流。在冬季，来自运城、三门峡、洛阳等由东向西传播的C4类气流占关中平原冬季气流的 $2 1 . 0 8 \%$ （以西安、咸阳、渭南、宝鸡和铜川为起点，该类气流分别占冬季气流的 $2 2 . 7 \%$ ！$2 3 . 3 \% . 2 2 . 3 \% . 1 7 . 7 \%$ 和 $1 9 . 4 \%$ )。对关中平原冬季聚类后的C1、C2、C3、C4四类后向轨迹气流对应$\mathrm { P M } _ { 2 . 5 }$ 浓度进行分析(图7)，当C4类局地气流出现时，整个关中平原 $\mathrm { P M } _ { 2 . 5 }$ 呈现高浓度水平，结合图2可知，高浓度 $\mathrm { P M } _ { 2 . 5 }$ 出现时关中平原气象条件处于静稳状态，可以推测在此类不利气象条件下，本地排放量较大，超过相应气象条件下的环境容量，使得$\mathrm { P M } _ { 2 . 5 }$ 浓度升高。

![](images/5337866c8ebe537ba618ed537f93b511ea570f6007dfba54b9964ddbe0f9497b.jpg)  
图6西安市不同季节下的近地面大气输送通道

![](images/dd2db83034d711c2eb36d25fe8410f7309b10c8b6d0fcd25825fb3dec6dee634.jpg)  
Fig.6Near surface atmospheric transport channels in different seasons in Xi'an   
图7关中五市冬季不同后向轨迹聚类下的 $\mathrm { P M } _ { 2 . 5 }$ 浓度分布  
Fig.7 $\mathrm { P M } _ { 2 . 5 }$ concentration under different backward trajectory clusters in five cities of Guanzhong in winter

当冬季出现途经蒙古国、内蒙、宁夏等地的长距离输送C2类气流时，该气流对关中平原的 $\mathrm { P M } _ { 2 . 5 }$ 进行清除，使得整个关中平原的 $\mathrm { P M } _ { 2 . 5 }$ 浓度在较低水平(图7)，该类气流占关中平原冬季气流的 $2 3 . 8 6 \%$ （以西安、咸阳、渭南、宝鸡和铜川为起点，该类气流分别占冬季气流的 $2 5 . 5 \% . 2 1 . 8 \% . 2 5 . 5 \% . 2 4 . 7 \%$ 和$2 1 . 8 \%$ ),与薛文博和黄光球等[29-30]的研究结论基本吻合。同时从图7可以看出，在冬季各类气象条件下，西安和咸阳两市 $\mathrm { P M } _ { 2 . 5 }$ 本地源叠加区域污染后，$\mathrm { P M } _ { 2 . 5 }$ 浓度均高于关中其他地市，也在一定程度上说明了西安和咸阳两市两地城市 $\mathrm { P M } _ { 2 . 5 }$ 本地源排放强度相对排放量要高于关中其他地市。

综上分析，可以看出由于关中平原地形特殊，结合气象影响[31和污染物传输及排放，使得关中平原的 $\mathrm { P M } _ { 2 . 5 }$ 浓度在冬季形成了14d左右的双震荡周期以及36d左右的季节震荡周期。同时，叠加本地污染源的排放影响后，形成了7d左右的星期效应[32-33]。

# 3结论

（1）关中平原五个城市 $\mathrm { P M } _ { 2 . 5 }$ 浓度变化规律基本保持一致，具有显著区域性和周期性。夏季保持稳定低浓度状态，秋冬季呈现季节性高浓度状周期性变化。 $\mathrm { P M } _ { 2 . 5 }$ 浓度在夏季呈现低浓度稳定状态，秋冬季呈现高浓度状态。其中，365d左右、36d左右以及14d左右的主震荡周期通过了 $9 0 \%$ 的置信度检验。

(2）秋冬季，关中五市的 $\mathrm { P M } _ { 2 . 5 }$ 浓度以 $1 4 { \mathrm { ~ d ~ } }$ 左右的周期性变化为主。14d左右的 $\mathrm { P M } _ { 2 . 5 }$ 浓度周期性变化主要受风速、风向、气压和湿度四项气象因子进行驱动。结合后向轨迹聚类分析，得出其原因主要是由运城、三门峡、洛阳和关中城市等地形成的局地静稳气流(该类气流占 $2 1 . 0 8 \%$ ,在该类气流下$\mathrm { P M } _ { 2 . 5 }$ 不断积累)和从蒙古国、内蒙古等地输入的气流（该类气流占 $2 3 . 8 6 \%$ ，在该类气流下积累的PM2.5得到清除)周期性交替所致。

(3）秋冬季局地静稳气流之下，污染源排放的污染物超过了对应气象条件下的环境容量，使得$\mathrm { P M } _ { 2 . 5 }$ 浓度升高。不同年份的 $\mathrm { P M } _ { 2 . 5 }$ 浓度波动有差异，在2016—2017年冬防期间， $\mathrm { P M } _ { 2 . 5 }$ 浓度波动幅度明显高于其他年份，受气象因素的影响较大。

# 参考文献(References):

[1]郝志新,耿秀,刘可邦,等.关中平原过去1000年干湿变化特征 [J].科学通报,2017,62(21): 2399-2406.[Hao Zhixin,Geng Xiu, Liu Kebang,et al.Dryness and wetness variations for the past 1000 years in Guanzhong Plain[J]. Chinese Science Bulletin, 2017,62(21): 2399-2406.]   
[2]陈建文,胡琳,王娟敏,等.陕西省大气稳定度分布特征研究[J] 水土保持研究,2013,20(3): 299-304.[Chen Jianwen,Hu Lin, Wang Juanmin,et al.Distribution characteristics of atmospheric stability in Shaanxi Province[J].Research of Soil and Water Conservation,2013,20(3): 299-304.]   
[3]高茂盛,李红梅,王卫东,等.1961—2014年陕西省气候资源变 化趋势及突变分析[J].中国农业大学学报,2017,22(11):121- 132.[Gao Maosheng,Li Hongmei, Wang Weidong,et al. Climate resources trend and abrupt climate change in Shaanxi Province during 1961 to 2O14[J]. Journal of China Agricultural University, 2017,22(11): 121-132.]   
[4]黄鑫,李亚丽,王靖中,等.1980—2016年陕西省冬季霾日数时 空变化及增多成因初探[J].中国环境科学,2019,39(9):3671- 3681.[Huang Xin,Li Yali,Wang Jingzhong,et al. The spatialtemporal variations of haze in Shaanxi Province from 198O to 2016 and the initial exploration of the increase[J].China Environmental Science,2019,39(9): 3671-3681.]   
[5]胡琳,张侠,苏静,等.陕西省霾天气变化特征及气候成因分析 [J].干旱区地理,2019,42(4): 707-714.[Hu Lin,Zhang Xia,Su Jing,et al. Variation characteristics of haze weather and its climatic causes in Shaanxi Province[J].Arid Land Geography,2019,42 (4): 707-714.]   
[6]黄小刚,邵天杰,赵景波,等.汾渭平原 $\mathrm { P M } _ { 2 . }$ 5浓度的影响因素及 空间溢出效应[J].中国环境科学,2019,39(8):3539-3548. [Huang XiaoGang, Shao TianJie, Zhao JingBo,et al. Influence factors and spillover effect of $\mathrm { P M } _ { 2 . 5 }$ concentration on Fenwei Plain[J]. China Environmental Science,2019,39(8): 3539-3548.] [7]韩磊,李蕴琪,赵永华,等.关中地区 $\mathrm { P M } _ { 2 . \cdot }$ 地面浓度分布及来源 [J].生态学杂志,2019,38(8):2500-2507.[Han Lei,Li Yunqi, Zhao Yonghua,et al. Ground concentration distribution and source d $\mathrm { P M } _ { 2 . 5 }$ in Guanzhong Region[J]. Chinese Journal of Ecology,2019,   
38(8): 2500-2507.] [8]孟宁,贝耐芳,李国辉,等.关中地区冬季人为源减排对 $\mathrm { P M } _ { 2 . 5 }$ 浓 度的影响[J].中国环境科学,2017,37(5):1646-1656.[Meng Ning,Bei Naifang,Li Guohui,et al.Response of the wintertime $\mathrm { P M } _ { 2 . 5 }$ level to anthropogenic emission mitigations in the Guanzhong basin[J]. China Environmental Science,2017,37(5):1646-   
1656.] [9]周静,张岳军,相栋,等.太原市 $\mathrm { P M } _ { 2 . 5 }$ 周期性特征及其成因分析 [J].生态环境学报,2018,27(3): 527-532.[Zhou Jing, Zhang Yuejun, Xiang Dong,et al.The periodicity and cause analysis of $\mathrm { P M } _ { 2 , : }$ in Taiyuan[J]. Ecology and Environment Sciences,2018,27(3):   
527-532.] [10] Torrence Christopher, Compo Gilbertp.A practical guide to waveletanalysis[J].Buletinof theAmerican MeteorologicalSociety,   
1998, 79(1): 61-78. [11] Stein A f,Draxler Rr,Rolph Gd,etal.NOAA's HYSPLIT atmospheric transport and dispersion modeling system[J]. Bulletin of the American Meteorological Society,2015,96(12): 2059-2077. [12]Aguiar-Conraria Luis,Joana Soares Maria. Business cycle synchronization and the Euro: A wavelet analysis[J]. Journal of Macroeconomics,2011,33(3): 477-489. [13] 李明,王贵文,柴旭荣,等.基于空间聚类的中国东北气候分区 及其气象干旱时间变化特征[J].自然资源学报,2019,34(8):   
1682-1693.[Li Ming, Wang Guiwen, Chai Xurong,et al. Climate regionalizationand temporal evolution of meteorological drought in Northeast China based on spatial clustering[J]. Journal of Natural Resources,2019,34(8): 1682-1693.] [14] 马爱华,岳大鹏,赵景波,等.近60a来内蒙古极端降水时空变 化及其影响[J].干旱区研究,2020,37(1):74-85.[Ma Aihua, Yue Dapeng, Zhao Jingbo,et al. Spatiotemporal variation and effect of extreme precipitation in Inner Mongolia in recent 6O years [J]. Arid Zone Research,2020,37(1): 74-85.] [15] 李梓铭,孙兆彬,邵勰,等.北京城区 $\mathrm { P M } _ { 2 . 5 }$ 不同时间尺度周期性 研究[J].中国环境科学,2017,37(2): 407-415.[Li Ziming,Sun Zhaobin, Shao Xie,et al. Using morlet wavelet analysis to analyze multiple time scale periodically in $\mathrm { P M } _ { 2 . 5 }$ in Beijing[J]. China Environmental Science,2017,37(2): 407-415.] [16] 王海鹏,张斌,刘祖涵,等.基于小波变换的兰州市近十年空 气污染指数变化[J].环境科学学报,2011,31(5):1070-1076. [Wang Haipeng, Zhang Bin,Liu Zuhan, et al.Wavelet analysis of air pollution index changes in Lanzhou during the last decade[J]. Acta Scientiae Circumstantiae,2011,31(5): 1070-1076.] [17]Roesch Angi, Schmidbauer Harald. WaveletComp 1.1: A guided tour through the R package[J/OL]. https: //CRAN.R-project. org/ package=WaveletComp.2018-03-18.   
[18]Morlet J,Arens G,Fourgeau E,et al. Wave propagation and sampling theory Part I: Complex signal and scattering in multilayered media[J]. Geophysics,1982,47(2): 203-221.   
[19]Morlet J,Arens G,Fourgeau E,et al. Wave propagation and sampling theory: Part II: Sampling theory and complex waves[J].Geophysics,1982,47(2): 222-236.   
[20] Grinsted A,Moore Jc,Jevrejeva S.Application of the cross wavelet transform and wavelet coherence to geophysical time series[J]. Nonlinear Processes in Geophysics,2004,11(5/6): 561-566.   
[21] Torrence Christopher,Webster Peterj. Interdecadal changes in the ENSO-monsoon system[J]. Journal of Climate,1999,12(8): 2679- 2690.   
[22]Veleda Doris,Montagne Raul,Araujo moacyr. Cross-wavelet bias corrected by normalizing scales[J]. Journal of Atmospheric and Oceanic Technology,2012,29(9): 1401-1408.   
[23] 朱蓉,张存杰,梅梅.大气自净能力指数的气候特征与应用研究 [J].中国环境科学,2018,38(10):3601-3610.[Zhu Rong, Zhang Cunjie,Mei Mei. The climate characteristics of atmospheric selfcleaning ability index and its application in China[J].China Environmental Science,2018,38(10): 3601-3610.]   
[24] 杨双艳,武炳义,胡景高,等.大气准双周振荡的研究进展[J].大 气科学学报,2015,38(6): 855-864.[Yang Shuangyan,Wu Bingyi,Hu Jinggao,et al. Research progress of quasi-biweekly oscillation of atmosphere[J]. Transactions of Atmospheric Sciences, 2015,38(6): 855-864.]   
[25] 杨双艳,武炳义,周顺武,等.大气季节内振荡研究进展[J].气象 科技,2012,40(6): 938-948.[Yang Shuangyan,Wu Bingyi, Zhou Shunwu, et al.Progress in researches on atmospheric intraseasonal oscillation[J]. Meteorological Science and Technology,2012, 40 (6): 938-948.]   
[26] 李崇银.大气中的季节内振荡[J].大气科学,1990,15(1):32- 45.[Li Chongyin. Intraseasonal oscillation in the atmosphere[J]. Chinese Journal of Atmospheric Sciences,1990,15(1): 32-45.] [27] 李崇银,程胜,潘静.冬季北半球平流层季节内振荡与对流层季 节内振荡的关系[J].大气科学,2006,30(5):744-752.[Li Chongyin, Cheng Sheng,Pan Jing.The relationship between the intraseasonal oscillations in the northern hemisphere during the boreal winter in the stratosphere and troposphere[J]. Chinese Journal of Atmospheric Sciences,2006,30(5): 744-752.] [28]Stunder Barbarajb.An assessment of the quality of forecast trajectories[J].Journal of Applied Meteorology,1996,35(8): 1319-1331. [29] 薛文博,付飞,王金南,等.中国 $\mathrm { P M } _ { 2 . 5 }$ 跨区域传输特征数值模拟 研究[J].中国环境科学,2014,34(6):1361-1368.[Xue Wenbo, Fu Fei,Wang Jinnan,et al.Numerical study on the characteristics of regional transport of $\mathrm { P M } _ { 2 . 5 }$ in China[J]. China Environmental Science,2014,34(6):1361-1368.] [30] 黄光球,雷哲.西安市大气颗粒物 $\mathrm { P M } _ { 2 . 5 }$ 的输送路径和潜在源分 析[J].云南大学学报(自然科学版),2019,41(6):1191-1200. [Huang Guangqiu, Lei Zhe. Transport pathways and potential sources of $\mathrm { P M } _ { 2 . 5 }$ in Xi'an City[J].Journal of Yunnan University(Natural Sciences Edition),2019,41(6): 1191-1200.] [31]张立凤,余沛龙,黎爱兵,等.地形强迫对大气长波调整的可能 影响[J].大气科学,2014,38(4):804-812.[Zhang Lifeng,Yu Peilong,Li Aibing,et al.Possible impacts of topography on adjustment of atmospheric long-waves[J]. Chinese Journal of Atmospheric Sciences,2014,38(4): 804-812.] [32] 赵卉伊褶,周卫健,牛振川,等.西安市2013—2017年大气 $\mathrm { P M } _ { 2 . 5 }$ 的时空变化特征及影响因素分析[J].地球环境学报,2019,10 (3):248-256.[Zhao Huiyizhe, Zhou Weijian,Niu Zhenchuan,et al.Analysis on the characteristics of temporal and spatial changes of atmospheric $\mathrm { P M } _ { 2 , \ 5 }$ and it's influencing factors in Xi'an from   
2013 to 2017[J]. Journal of Earth Environment,2019,10(3): 248-   
256.] [33] 李建东,铁学熙,曹军骥.城市地区 $\mathrm { P M } _ { 2 . 5 }$ 周末效应的初步研究 [J].地球环境学报,2015,6(4): 224-230.[Li Jiandong,Tie Xuexi, Cao Junji.A preliminary study of $\mathrm { P M } _ { 2 . 5 }$ weekend effect in typical cities[J]. Journal of Earth Environment,2015,6(4): 224-230.]

# Analysis on the periodic variation of $\mathbf { P M } _ { 2 . 5 }$ concentration and its causes in Guanzhong Plain

JIA Ce， WANG Ya-qiong， YANG Xiao (SchoolofEnvironment&Nature Resources,Renmin University ofChina,Beijing 1Oo872,China)

Abstract: To analyze the characteristics and causes of $\mathrm { P M } _ { 2 . 5 }$ concentration changes in five Guanzhong cities from November 15,2013 to March15,2019,Morlet wavelet analysis and cross waveletanalysis were used.The results show that (1) the changes in PM $2 . 5$ concentration in five Guanzhong cities were markedly regional and periodic. The $\mathrm { P M } _ { 2 . 5 }$ concentration was low in summer and high in autumn and winter, with periodic changes every 365 d,36 d,and $1 4 \mathrm { ~ d ~ }$ ,respectively. (2) In autumn and winter, the $\mathrm { P M } _ { 2 . 5 }$ concentration in five Guanzhong cities changes periodically every 14 d. The cyclical change in $\mathrm { P M } _ { 2 . 5 }$ concentration every 14 d was negatively correlated with the three meteorological factors of wind direction,wind speed,and air pressure,and was laggng behind by1/8 phase period with humidity, with no correlation with temperature.(3) The periodic change in PM $2 . 5$ concentration in five Guanzhong cities in autumn and winter was mainly due to the local static airflow formed by Yuncheng,Sanmenxia,Luoyang,and Guanzhong cities (this type of airflow accounts for $2 1 . 0 8 \%$ ，and under this type of airflow, $\mathrm { P M } _ { 2 . 5 }$ continuously accumulates)and theairflow imported from Mongolia,Inner Mongolia,and otherplaces (thistype of airflow accounts for $2 3 . 8 6 \%$ ,and the $\mathrm { P M } _ { 2 . 5 }$ accumulated under this type of airflow is removed) periodically.

Keywords: Guanzhong Plain; $\mathrm { P M } _ { 2 . 5 }$ concentration; periodic change; cause analysis