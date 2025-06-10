# 鹊桥卫星激光测距成功概率分析

高清鹏1.2，李春晓1.2，李荣旺2.3，李语强2.3

（1.中国科学院大学，北京100049；2.中国科学院云南天文台，云南 昆明650011；

# 3.中国科学院空间目标与碎片观测重点实验室，江苏南京210034）

摘要：本文首先对鹊桥卫星任务轨道进行计算，通过数值方法给出一条有效的近似模拟鹊桥卫星探测任务的目标轨道。计算给出了云南天文台距鹊桥卫星的最大和最小距离，并对最大距离和最小距离激光测距回波光子数进行对比分析，对影响鹊桥卫星激光测距成功率的关键因素进行研究对比分析。计算在最近观测距离时间段鹊桥卫星与月球的最小距离和最小z方向垂直距离，针对鹊桥卫星分析计算给出 2019 年下半年云南天文台鹊桥卫星激光测距观测任务时刻表，根据以往月球激光测距积累的经验，通过对观测任务时刻表的分析计算结合影响测距的因素给出了提高激光回波光子数和测距成功率的改善方法。

关键词：鹊桥卫星激光测距、目标晕轨道、回波光子数

# 一．引言

嫦娥四号中继星（又称鹊桥卫星）于2018年5月28日成功发射在地月系L2点附近用来实现月球背面嫦娥四号软着陆器与地面站的通信和数据传输。鹊桥卫星运行在地月系L2点 halo 轨道，斯坦福大学 Farquhar[1-3]于上世纪70 年代在月球背面探测的研究过程中，发现了地月系L2点附近存在三维halo轨道，该轨道利用飞行器在地月系L2点运行可实现月球背面与地球的通信和数据传输，是月球背面探测中继通信的理想位置。徐明[4对地月系 L2点附近轨道进行分析，结果表明Lissajous 轨道在月球背面探测中继任务过程中会存在月球遮挡问题，对于一颗中继卫星无法满足中继通讯任务。高珊[5-6]、何芸[通过对鹊桥卫星任务轨道分析和激光测距技术研究，对于保障长期运行对地通讯的需求情况下轨道采用 halo轨道，轨道z方向振幅在1.2万—1.5万km的轨道，不会存在月球遮挡问题。

当月球背面处于月夜的时段内，鹊桥卫星中继通信和数据传输任务暂停。鹊桥卫星中继通信任务暂停时段可以调整卫星姿态，使得鹊桥卫星上的中空激光角反射器正对着地球，在地面开展鹊桥卫星激光测距试验。云南天文台利用1.2米光学望远镜在国内首次实现了月球激光测距[8，即将对鹊桥卫星开展激光测距试验，这是人类首次开展地月L2点激光测距试验，对我国今后在开展深空激光测距技术的发展有着重要意义。

# 二．任务目标轨道分析计算

在牛顿力学体系惯性空间中物体受万有引力作用，对于地月系深空探测而言，我们通常采用圆型限制性三体模型，坐标系为地月会合坐标系，对第三体航天飞行器的运动方程进行推导并进行归一化单位后可得到圆形限制性三体问题常用的动力学方程[9]：

$$
\stackrel { \bullet \cdot } { x } - 2 ^ { * } \dot { y } - x = - \frac { ( 1 - \mu ) ( x + \mu ) } { { r _ { 1 } ^ { 3 } } } - \frac { \mu ( x - ( 1 - \mu ) ) } { { r _ { 2 } ^ { 3 } } }
$$

$$
\overbrace { y + 2 } ^ { \bullet } x - y = - { \frac { ( 1 - \mu ) y } { r _ { 1 } ^ { 3 } } } - { \frac { \mu y } { r _ { 2 } ^ { 3 } } }
$$

$$
\stackrel { \bullet \bullet } { z } = - { \frac { ( 1 - \mu ) z } { r _ { 1 } ^ { 3 } } } - { \frac { \mu z } { r _ { 2 } ^ { 3 } } }
$$

其中：

$$
\begin{array} { l } { \displaystyle \mathbf { r } _ { 1 } = \sqrt { \left( x + \mu \right) ^ { 2 } + \mathbf { y } ^ { 2 } + \mathbf { z } ^ { 2 } } } \\ { \displaystyle \mathbf { r } _ { 2 } = \sqrt { \left( x - ( 1 - \mu ) \right) ^ { 2 } + \mathbf { y } ^ { 2 } + \mathbf { z } ^ { 2 } } } \end{array}
$$

$$
\mu = \mathbf { m } _ { 2 } / ( \mathbf { m } _ { 1 } + \mathbf { m } _ { 2 } )
$$

欧拉和拉格朗日分别发现在三体问题中存在三个共线平动点和两个三角平动点，通过计算可得L2平动点位置： $L _ { 2 } = ( 1 . 1 5 5 7 0 1 6 4 , 0 , 0 )$ 。

把地月系L2 点位置带入并令其速度为零可得雅可比常数 $\mathrm { C _ { L 2 } } = 3 . 1 7 2 2 0 0 4 3 1 3 7 8 6 7 \mathrm { \Omega }$ （2对于 L2 点鹊桥卫星，其能量[]满足C<C[2。

在没有得到准确鹊桥卫星轨道参数的情况下，我们有必要通过对鹊桥卫星目标轨道模拟计算出一条比较接近任务的轨道来对其进行鹊桥卫星测距研究分析。在 $\mathrm { t } _ { 0 }$ 时刻，初值估计取一个L2 点附近的初始状态量 $( \mathrm {  ~ x , \mathrm {  ~ y , \mathrm {  ~ z , ~ } } } \mathrm {  ~ \dot { \boldsymbol { x } } , \mathrm {  ~ \dot { \boldsymbol { y } } ~ , ~ } } \bar { \mathrm {  ~ z ~ } } )$ · ，通过数值积分方法计算得到一条满足鹊桥卫星任务目标的轨道，该轨道z方向振幅在 $1 2 0 0 0 \mathrm { k m }$ 附近 $\mathrm { A z }$ 为 $1 1 8 8 3 \mathrm { k m }$ 的halo轨道如图2所示，具体计算方法可参考文献[14]。

![](images/0b69be9c2367a4870d00b76c0f0075c2670e0e0159aeab03d97d1593094be45b.jpg)  
图1地月系L2点附近 $\mathrm { A z }$ 方向振幅为 $1 1 8 8 3 \mathrm { k m }$ 的halo轨道（以一个地月距离为单位）

Fig.1 The halo orbit with an amplitude of $1 1 8 8 3 \mathrm { k m }$ in the Az direction near the L2 point of the Earth-moon system (In terms of an Earth-moon distance)

通过计算我们得到一条轨道周期为14.798125542762529天的halo轨道，轨道的雅可比积分常数 $\mathrm { C = 3 . 1 4 8 0 0 2 7 5 6 0 8 2 3 1 2 3 }$ 。该轨道的 $\mathrm { ~ z ~ }$ 方向最大振幅为 $1 1 8 8 3 \mathrm { k m , x }$ 方向最大振幅为 $1 2 1 3 2 \mathrm { k m } , \mathrm { z }$ 方向最大振幅为 $\mathrm { 3 5 0 5 4 k m }$ 。并且当x,z方向同时达到最大振幅时，轨道y方向坐标趋近于零，而在y方向达到最大振幅时的x,z方向距离振幅中心分别约为 $4 1 4 6 \mathrm { { k m } }$ 和$2 6 7 0 \mathrm { k m }$ 。轨道x方向的振幅中心距离拉格朗日点距离约为 $2 8 0 9 \mathrm { k m }$ 且靠近月球和地球一侧。通过分析该轨道无月球遮挡，对月球探测器和地面测控站能很好的覆盖，可作为一条有效近似模拟中继任务的目标轨道。

# 三．鹊桥卫星激光测距：

在地球公转和自转周期相近的情况下，月球背面始终背离地球，嫦娥四号卫星在月球处于背离太阳的月夜时段时，月球背面温度低至零下 $1 9 0 ^ { \circ } \mathrm { C }$ ，嫦娥四号探测器的电子器件无法在这样的低温条件下正常工作，每农历月有将近14天的时间段内嫦娥四号探测卫星关闭至休眠状态，鹊桥卫星相对地月位置及工作状态示意图如图2所示。在这个休眠时间段内号鹊桥卫星可以调整姿态使带上去的激光角反射器正对地面，云南天文台1.2米望远镜对鹊桥卫星开展激光测距试验。

![](images/7a9923366b9c7ebfb82732dc3006fc9f86c518dec74f3b49f22e8425861a46c1.jpg)  
图2太阳、地球、月球和鹊桥卫星目标轨道相对位置示意图

Fig.2 Schematic diagram of the relative positions of the sun、earth、moon and queqiao satellite orbits

经计算目标轨道距离月球质心的最近距离为 $4 5 7 0 4 \mathrm { k m }$ ，在最近距离时，从地球看月球和鹊桥卫星的Z方向垂直视距离有 $6 7 2 0 \mathrm { k m }$ ，在假定认为满月时月球反射光对鹊桥卫星激光测距无影响的情况下，激光测距的可观测时间段需满足以下条件：1.当月球背面处于月夜情况下，嫦娥四号探测器处于休眠状态，每个月球相位周期内的可观测时间段为上弦月—满月—下弦月，即每农历月9-22日左右。2.在观测站处于白天时，探测器发出的激光被淹没在白天的噪声中，昆明站相对太阳高度角需要在 $0 ^ { \circ }$ 以下，即观测站处于夜晚才能进行观测，本次计算中太阳高度角取为 $- 5 ^ { \circ }$ 。3.由于大气折射、散射、衰减等大气环境因素的影响，根据以往激光测月实际观测中积累的经验，鹊桥卫星的最大高度角需大于 $4 5 ^ { \circ }$ ，并且每晚连续可观测时段需大于2小时以满足激光测距回波光子数的积累。4.观测需在无云晴朗的夜晚，昆明降雨分布情况如图3所示，根据昆明地区的降雨概率分布情况使观测时间避开雨季观测。

![](images/e62b84cfd9a5d12791f423b44e9fdf82f34db63742492cf6ec45c3f0f79740f9.jpg)  
图3昆明全年降雨分布情况  
Fig.3 Distribution of annual rainfall in Kunming

在本次计算中取时间步长为10分钟，综合以上条件计算给出 2019 年下半年云南天文台鹊桥卫星激光测距观测任务时刻表如表1：

表12019年下半年云南天文台鹊桥卫星激光测距观测任务时刻表

Table.1 Timetable of queqiao satellite laser ranging observation task of Yunnan Observatory in the second half of 2019

<html><body><table><tr><td>年份</td><td>阳历日期</td><td>阴历日期</td><td>可观测否</td><td>观测时段</td><td>观测时长</td></tr><tr><td colspan="6">2019 年7.01-10.08（农历5.29-9.10）雨季暂停观测</td></tr><tr><td>2019</td><td>10.9</td><td>9.11</td><td></td><td>20:50-23:30</td><td>160</td></tr><tr><td>2019</td><td>10.10</td><td>9.12</td><td></td><td>21：10-24:00</td><td>170</td></tr><tr><td>2019</td><td>10.11</td><td>9.13</td><td></td><td>00:00—00:30 21:30-24:00</td><td>30+150</td></tr><tr><td>2019</td><td>10.12</td><td>9.14</td><td></td><td>00:00—01:40 21:50—24:00</td><td>100+130</td></tr><tr><td>2019</td><td>10.13</td><td>9.15</td><td>√</td><td>00:00—02:40 22:20—24:00</td><td>160+100</td></tr><tr><td>2019</td><td>10.14</td><td>9.16</td><td>√</td><td>00:00—03:40 22：50—24:00</td><td>220+70</td></tr><tr><td>2019</td><td>10.15</td><td>9.17</td><td>√</td><td>00：00—04:30</td><td>270+40</td></tr><tr><td>2019</td><td>10.16</td><td>9.18</td><td>√</td><td>23：20—24:00 00:00—05:20</td><td>320</td></tr><tr><td>2019</td><td>10.17</td><td>9.19</td><td>√</td><td>00:00-06:20</td><td>380</td></tr><tr><td>2019</td><td>10.18</td><td>9.20</td><td>√</td><td>00:40-06:40</td><td>360</td></tr></table></body></html>

<html><body><table><tr><td>2019</td><td>10.19</td><td>9.21</td><td>√</td><td>01：30-06:40</td><td>310</td></tr><tr><td>10.20</td><td></td><td>9.22</td><td>√</td><td>02:30-06:40</td><td>250</td></tr><tr><td></td><td colspan="5">2019 年10.21-11.05（农历9.23-10.09）不可观测</td></tr><tr><td>2019</td><td>11.6</td><td>10.10</td><td>√</td><td>19:20-22:20</td><td>180</td></tr><tr><td>2019</td><td>11.7</td><td>10.11</td><td>√</td><td>19:30-23:30</td><td>240</td></tr><tr><td>2019</td><td>11.8</td><td>10.12</td><td>√</td><td>20:00-24:00</td><td>240</td></tr><tr><td>2019</td><td>11.9</td><td>10.13</td><td>√</td><td>00：00-00:30</td><td>30+220</td></tr><tr><td></td><td></td><td></td><td></td><td>20:20-24:00</td><td></td></tr><tr><td>2019</td><td>11.10</td><td>10.14</td><td>√</td><td>00:00-01:30</td><td>90+190</td></tr><tr><td></td><td></td><td></td><td></td><td>20:50-24:00</td><td></td></tr><tr><td>2019</td><td>11. 1</td><td>10.15</td><td>√</td><td>00:00-02:20</td><td>140+160</td></tr><tr><td></td><td></td><td></td><td></td><td>21: 20-24:00</td><td></td></tr><tr><td>2019</td><td>11. 12</td><td>10.16</td><td>7</td><td>00：00-03:20</td><td>200+120</td></tr><tr><td></td><td></td><td></td><td></td><td>22:00-24:00</td><td></td></tr><tr><td>2019</td><td>11. 13</td><td>10.17</td><td>√</td><td>00:00-04:10</td><td>250+80</td></tr><tr><td></td><td></td><td></td><td></td><td>22:40-24:00</td><td></td></tr><tr><td>2019</td><td>11. 14</td><td>10.18</td><td>√</td><td>00：00-03：50</td><td>230+20</td></tr><tr><td></td><td></td><td></td><td></td><td>23:40-24:00</td><td></td></tr><tr><td>2019</td><td>11.15</td><td>10.19</td><td>√</td><td>00:00-06:00</td><td>360</td></tr><tr><td>2019</td><td>11.16</td><td>10.20</td><td>√</td><td>00:20-07:00</td><td>400</td></tr><tr><td>2019</td><td>11. 17</td><td>10.21</td><td>√</td><td>01:20-07:00</td><td>340</td></tr><tr><td>2019</td><td>11.18</td><td>10.22</td><td>√</td><td>02:10-07:00</td><td>290</td></tr><tr><td>2019</td><td>11.19</td><td>10.23</td><td>√</td><td>03:10-07:00</td><td>230</td></tr><tr><td colspan="6">2019 年11.20-12.03（农历10.24-11.08）不可观测</td></tr><tr><td>2019</td><td>12.4</td><td>11.09</td><td>√</td><td>18:50-21:10</td><td>140</td></tr><tr><td>2019</td><td>12.5</td><td>11. 10</td><td>√</td><td>18:50-22:20</td><td>210</td></tr><tr><td>2019</td><td></td><td>11. 11</td><td>√</td><td>18:50-23:20</td><td></td></tr><tr><td></td><td>12.6</td><td></td><td></td><td></td><td>250</td></tr><tr><td>2019</td><td>12.7</td><td>11. 12</td><td>√</td><td>18：50-24:00</td><td>310</td></tr><tr><td>2019</td><td>12.8</td><td>11. 13</td><td>√</td><td>00:00-00:10</td><td>10+280</td></tr><tr><td>2019</td><td></td><td></td><td></td><td>19:20-24:00</td><td></td></tr><tr><td></td><td>12.9</td><td>11. 14</td><td>7</td><td>00：00-01:10</td><td>70+240</td></tr><tr><td>2019</td><td></td><td></td><td></td><td>20:00-24:00</td><td></td></tr><tr><td></td><td>12.10</td><td>11. 15</td><td>√</td><td>00:00-02:00</td><td>120+200</td></tr><tr><td></td><td></td><td></td><td></td><td>20:40-24:00</td><td></td></tr><tr><td>2019</td><td>12.11</td><td>11. 16</td><td>√</td><td>00:00-02:50</td><td>170+160</td></tr><tr><td></td><td></td><td></td><td></td><td>21:20-24:00</td><td></td></tr><tr><td>2019</td><td>12.12</td><td>11. 17</td><td>√</td><td>00：00-03：50</td><td>230+110</td></tr><tr><td></td><td></td><td></td><td></td><td>22：10-24:00</td><td></td></tr><tr><td>2019</td><td>12.13</td><td>11. 18</td><td>√</td><td>00:00-04:50</td><td>290+50</td></tr><tr><td></td><td></td><td></td><td></td><td>23:10-24:00</td><td></td></tr><tr><td>2019</td><td>12.14</td><td>11. 19</td><td>√</td><td>00：00-05:50</td><td>350</td></tr><tr><td>2019</td><td>12.15</td><td>11.20</td><td>√</td><td>00:10-06:40</td><td>390</td></tr></table></body></html>

<html><body><table><tr><td>2019</td><td>12.16</td><td>11. 21</td><td>√</td><td>01:10-07:20</td><td>370</td></tr><tr><td>2019</td><td>12.17</td><td>11. 22</td><td>√</td><td>02:10-07:20</td><td>310</td></tr><tr><td>2019</td><td>12.18</td><td>11. 23</td><td>√</td><td>03:10-07:20</td><td>250</td></tr><tr><td colspan="6">2019 年12.19-12.31（农历11.24-12.06）不可观测</td></tr></table></body></html>

由于激光测距回波光子数和距离的四次方成反比，随着测距距离的增加，能探测到的回波光子数衰减，激光测距的距离对测距成功率有着重要影响。通过对Z方向振幅为 $1 1 8 8 3 \mathrm { k m }$ 的地月系L2点halo轨道计算，可以得到在可观测的时间段内航天器目标轨道到云南天文台1.2 米望远镜的最大距离和最小距离分别为 $4 5 3 7 1 2 \mathrm { k m }$ 和 $4 2 3 6 8 1 \mathrm { k m }$ 。

在鹊桥卫星激光测距中，云南天文台1.2米望远镜所使用的观测参数如表2：

表2云南天文台1.2米望远镜所使用的观测参数

Table 2 Observation parameters used by the 1.2-meter telescope at the Yunnan Observatory   

<html><body><table><tr><td>脉冲能量E为3000mJ</td><td>望远镜抖动标准差为0.1"</td></tr><tr><td>大气相干长度ro为10cm</td><td>激光发散角为2"</td></tr><tr><td>鹊桥卫星角反射器面积为0.0227m</td><td>角反射器反射率为0.6</td></tr><tr><td>角反射器发散角为2"</td><td>大气透过率为0.6</td></tr><tr><td>卷云透过率0.1</td><td>望远镜发射系统光学效率0.4</td></tr><tr><td>接收系统光学效率0.2</td><td>探测器量子效率为0.6</td></tr><tr><td>望远镜有效口径1.06m</td><td>激光波长为532nm</td></tr></table></body></html>

探测器接收到的回波光子数N表示[11]为:

$$
N = \bar { \varepsilon } \eta _ { e } T ^ { 2 } { a { T _ { c } } ^ { 2 } } S \rho _ { r e f l e c t i o n } ( \Omega _ { r e f l e c t i o n } R ^ { 2 } ) ^ { - 1 } \pi ( \frac { D } { 2 } ) ^ { 2 } \eta _ { r } \eta _ { q } \frac { \lambda } { h c }
$$

激光测距成功率表示为：

$$
\zeta = 1 - e ^ { - N }
$$

先假定轨道预报参数是精确的情况下，带入参数可得鹊桥卫星距离观测站最近距离为423681km时的测距回波光子数和测距成功率分别为：0.16516058451731563和0.18051588941373053。在距离观测站最远距离为453712km时计算得激光测距回波光子数和测距成功率分别为：0.13726398182287192和0.128259927778114。

再计算轨道预报参数横向偏差为 $2 \mathrm { k m }$ 时，鹊桥卫星距离观测站最近距离为423681km 时的测距回波光子数和测距成功率分别为：0.03921051544940731和0.0384517329270474。在距离观测站最远距离为 $4 5 3 7 1 2 \mathrm { k m }$ 时计算得激光测距回波光子数和测距成功率分别为：0.03313527824586319和0.03259231847743693。

为了更加清晰的分析轨道预报横向标准差对激光测距成功率的影响情况，对鹊桥卫星轨道预报参数横向标准差取 $0 { - } 5 \mathrm { k m }$ 时，分别画出鹊桥卫星与观测站最近距离和最远距离时的测距回波光子数和测距成功率分布图如图4和图5。

![](images/430706827653bbeb5c775bd38eef73e4a726ccf4a991ad3571003ccecd385ee8.jpg)  
图4在鹊桥卫星与昆明观测站距离为 $4 2 3 6 8 1 \mathrm { k m }$ 时激光测距回波光子数和测距成功率随预报横向标准差的变化

Fig.4 The variation of the number of laser ranging echoes and the success rate of ranging with the horizontal standard deviation of the forecast when the distance between the queqiao satellite and the Kunming observatory is 423681 km

![](images/934d8f324029bbe791d0b8cbff79ff36f793fb336bd34056cc9f21c1eeda02a9.jpg)  
图5 在鹊桥卫星与昆明观测站距离为453712km时激光测距回波光子数和测距成功率随预报横向标准差的变化

Fig.5 The variation of the number of laser ranging echoes and the success rate of ranging with the horizontal standard deviation of the forecast when the distance between the queqiao satellite and the Kunming observatory is $4 5 3 7 1 2 \ \mathrm { k m }$ （204号

通过以上对比分析表明：1.在鹊桥卫星激光测距中，鹊桥卫星轨道预报偏差对测距成功率有重要影响，在轨道预报参数精确的情况下测距的成功率最好能达到 $1 8 \%$ 左右，而在其他条件不变的情况下当轨道预报参数横向偏差为 $2 \mathrm { k m }$ 时，鹊桥卫星激光测距成功率就迅速下降到 $3 . 8 \%$ 。

改善途径：根据以往激光测距实际观测过程中积累的经验，预报横向标准差一般可通过两种方法来进行改进，一是通过多种手段联合定轨及实时修正轨道预报参数等方式提高预报轨道参数的精度，二是对望远镜预报模型的指向精度进行改进提高，使望远镜对目标的指向精度更高从而减小由望远镜指向偏差带来的预报指向偏差。

2.在轨道预报精度短期内不能提高的情况下，观测站到鹊桥卫星的距离变化也对鹊桥卫星测距成功率有明显影响，在假定预报精度精确的情况下，在鹊桥卫星与观测站的最近距离处进行激光测距比在最远距离处进行测距其测距成功率可提升 $4 0 . 7 4 \%$ 。

进一步画出鹊桥卫星激光测距回波光子数和测距成功率随测距距离的变化如下图6 所示：

![](images/550a45a74ab3505d4ec18a952b775923a3556ed00a59bdb9b5479f43205b2596.jpg)  
图6假定轨道预报横向偏差为 $1 0 0 \mathrm { m }$ ，鹊桥卫星与昆明观测站距离为423681km 时激光测距回波光子数 和测距成功率随预报偏差的变化（横坐标为测距距离，左边纵坐标为激光回波光子数，右边纵坐标为测距 成功率)

Fig.6 Assume that the lateral deviation of the orbital prediction is $1 0 0 \mathrm { m }$ ，and the laser ranging echo photon and the ranging success rate varies with the forecast deviation when the distance between the queqiao satellite and the Kunming observatory is 423681km (the abscissa is the ranging distance,and the left ordinate is Laser echo photon number，right ordinate is the laser ranging success rate)

通过对图6分析可明显看出激光测距成功率随测距距离增大而降低。

根据月球相位周期，一个农历月的月球周期约为29.53天，而所计算的目标晕轨道周期约为14.8天，目标晕轨道的两个周期与月球的一个相位周期几乎近似相同，因此通过目标轨道一次相位调整就能满足较长时间段内鹊桥卫星激光测距处于较为理想状态。目标轨道相位调整分为两种情况分析：

1．目标轨道距离月球质心的最近距离为 $4 5 7 0 4 \mathrm { k m }$ ，在最近距离时，从地球看月球表面离与鹊桥卫星的Z方向垂直距离有 $6 7 2 0 \mathrm { k m }$ （到月球质心为 $6 7 2 0 + 1 7 3 7 \mathrm { k m }$ ，由于月球扁率的缘故，实际距离比 $6 7 2 0 \mathrm { k m }$ 稍大）。在假定认为满月时月球的反射光对鹊桥卫星激光测距无影响的情况下，根据表1给出的鹊桥卫星激光测距观测任务时刻表，通过调整轨道相位使观测处于最近距离时运行轨道对应表中可观测时长在最长的时间段附近最有利于做鹊桥卫星激光测距观测试验，此时也即为较理想状态下的观测。

2．鉴于之前对月球激光测距的经验，当月球满月时，月球被太阳照射的反射光对月球激光测距影响较大，处于满月状态时比较难进行月球激光测距。假定对鹊桥卫星激光测距时月球的反射光对鹊桥卫星测距还会出现较为明显的影响时，可以通过调整使鹊桥卫星运行轨道的最近距离时间段与观测任务时刻中的上弦月农历日约为11-12日相对应，这样即认为在满月时月球反射光对鹊桥卫星激光测距影响较大时较为理想的最佳观测状态。

由于在测距最近距离时鹊桥卫星与月球质心的最小距离为45704km，并且月球被太阳照射的反射光始终背离鹊桥卫星，在实测之前可优先选择方案一进行试验，之后再根据实测情况来确定是否需要进一步调整。激光测距回波光子数和距离的四次方成反比，在望远镜性能短暂时间内无法得到提升，并且轨道预报的精确度无法得到进一步改善时，在鹊桥卫星任务和燃料允许的情况下可以通过相位调整使鹊桥卫星运行轨道处于地面最佳观测状态，也可提高测距成功率。

四．总结

鹊桥卫星激光测距将是我国首次开展的超过地月距离的激光测距技术，对于通过联合其他手段进行远距离精密轨道确定，其激光测距本身较高的精度特性对开展高精度轨道定轨有重要价值，同时鹊桥卫星激光测距技术对于开展远距离激光通信等关键技术的研究有积极作用，对我国进行深空探测有重要意义。

文章通过分析鹊桥卫星任务轨道，计算出一条比较接近鹊桥卫星任务的轨道，对该轨道进行分析计算影响激光测距回波光子数和测距成功率的关键因素，最后得到以下结论：

1.在望远镜和大气环境暂时不能得到有效改善和提升时，通过改善目标的轨道预报精度可以显著提高鹊桥卫星激光测距的成功率。2.在以上条件即望远镜，大气环境，轨道预报精度都暂时无法得到提升时，鹊桥卫星激光测距的观测距离对测距回波光子数和测距成功率有明显影响，可以通过计算分析和控制鹊桥卫星降低鹊桥卫星和观测站间的距离来提高测距的成功率。3.月球背面的嫦娥四号探测器由于月夜低温不能正常工作的鹊桥卫星激光测距可观测周期在14天左右，鹊桥卫星目标晕轨道的周期也为14天左右，通过轨道相位的一次调整可使观测台站在较长时间内处于最佳观测状态（在目标轨道运行至最近距离段时观测站的可观测任务时长最长）。理想状况下，在距离观测台站最近的时间段内进行观测比在距离观测台站最远时测距成功率可提高 $4 0 . 7 4 \%$ 。

# 五．参考文献

[1].Faquhar R W.Utilization of libration point for human exploration in thesun_earth_moon system and beyond[J].acta Astronautica,55(2004) :687-700.  
[2].Faquhar R W.Qiasi-periodic orbits about the translunar libration point[J」.celestial Mechanics,1973,7:458-473.  
[3].Faquhar R w,uhonen DP.Mission design for a halo orbiter of the earth[J].AIAA/AASAstrondynamics conference,san Siego,august 1977:170-177.  
[4].徐明，徐世杰.地月系L2点lissajous 轨道卫星对地月球的跟踪规律研究[J].宇航学报，2008，29(1) :59-65.  
[5].高珊，周文艳，张磊，等.嫦娥四号中继星任务轨道设计与实践［J].中国科  
学,2019,49(2) :156-165.  
[6].高珊，周文艳．地月拉格朗日L2点中继星轨道分析与设计[J].深空探测学  
报,2017,4(2) :122-129.  
[7].何芸，刘祺，田伟，等．地月第二拉格朗日点卫星激光测距技术研究［J].深空探测学报，2017，4（2）:130-137.  
[8].李语强，伏红林，李荣旺，等.云南天文台月球激光测距研究与实验［J].中国激光，2018,46(1) :188-195.  
[9].李明涛.共线平动点任务节能轨道设计与优化[D].2010:19-123.  
[10].侯锡云.平动点的动力学特征及其应用[D].2008：1-60.  
[11].李春晓，高清鹏,李语强，等.地月系L2点中继星激光测距成功率的估算[J].天文研究与技术，2019，16（1）：44-53.  
[12].Wang sang koon,Martin W.Lo,Jerrold E.Marsden,et al.Dynamical systems,thethree-body problem,and space mission design[M].2006.143-171.  
[13].Richard H.Battin.An introduction to the mathematics and methods of  
astrodynamics,revised Edition[M].1999:365-622.  
[14].孙超，唐玉华，李翔宇，等．地一月L2点中继星月球近旁转移轨道设[J].深空探测学报，2017,4(3):264—269.

# Success probability analysis of the Chang'e-4 lunar queqiao satellite laser ranging Qingpeng Gao1.2,Chunxiao Li1.2,rongwang Li2 3,Yuqiang Li2.3

(1.University of Chinese academy of Sciences,Beijing 1OoO49,China: 2.Yunnnan Observatories,Chinese Academy of Sciences,Kunming 65o011,China 3. Key Laboratory of Space Target and Debris Observation,Chinese Academy of Sciences, Nanjing 210034, China)

Abstract:In this paper, we first calculate the queqiao satellite mission orbit, and give a valid approximate orbit to simulated queqiao satellite detection task by numerical integration method. By calculating the maximum and minimum distances between the queqiao satellite and Yunnan Observatory, the maximum distance and the minimum distance queqiao satellite laser ranging echo photon number are compared and analyzed respectively, which affects the queqiao satellite laser ranging. The key factors of the success rate of queqiao satelite laser ranging are studied and compared. Calculate the minimum distance between the queqiao satellite and the moon and the minimum z-direction vertical viewing distance during the most recent observation distance period. According to the analysis and calculation of the queqiao satelite,the schedule of the task observation of the queqiao satellite laser ranging observation of the Yunnan Observatory in the second half of 2O19 is given. According to the experience of lunar laser ranging accumulation in the past, the improvement method of laser echo photon number and ranging success rate is given by the calculation and analysis,the observation task schedule combined with the factors affecting the ranging.

Key words: Queqiao satellite laser ranging; Mission ofHalo orbit; Effective photon numbers.