# 1000kV紧凑型输电线路选型研究

汪龙龙」　宋金山’　汪迪锋²（1.江苏省电力公司检修分公司南京2100002.江门供电局江门529000）

![](images/d62b508d82b85529ee3eae51fae828e6c652bf8c6bb002658c7d7fdd575f1546.jpg)

汪龙龙男1988年生，硕士研究生，主要研究方向为电力系统运行与控制。

摘要：线路输送自然功率的多少和单位截面积自然功率的大小是影响输电线路经济性的两个重要参考指标。在特高压输电线路的选择中除了要考虑这两个指标之外，还必须考虑到导线表面电场强度、无线电干扰及可听噪声等电磁环境约束。紧凑型输电技术能够有效地增大线路自然功率和单位截面积自然功率，并能够有效改善其周围的电磁环境。本文运用紧凑型输电技术，考虑特高压线路选择的经济性和电磁环境等工程实际约束，建立有多个非线性约束的多目标数学模型，得到常规子导线对称排列的特高压输电线路选型。将所得线路选型与常规的特高压线路选型相比较，得到一种经济性和电磁环境均较好的线路选型。此外，本文运用粒子群算法对上述选型进行子导线非对称排列优化，进一步减小了线路周围的无线电干扰和可听噪声等电磁参数值，获得了各相子导线非对称排列的线路选型，最后利用有限元法对求得的选型进行了仿真验证。

关键词：特高压紧凑型输电技术 电磁环境 线路选型有限元分析法中图分类号：TM89

![](images/50e4161ccd4053f9df12f33db431aa4b8a2ecc57f0131d472ef5337ba7f47824.jpg)

宋金山男 1980年生，本科，主要研究方向为继电保护。

# A Study of Conductors Selection Types in 1oookV Compact Power Transmission Line

Wang Longlong1Song Jinshan'Wang Difeng2 (1.Jiangsu Electric Power Maintenance Branch CompanyNanjing210000 China 2.Jiangmen Power Supply BureauJiangmen5290ooChina ）

Abstract: The amount of natural power of transmission line and the amount of natural power of unit cross-sectional area are two important indicators of measuring the efficiency of transmission line.We are not only considering the natural power of transmission line and the amount of natural power of unit cross-sectional area, but also the conductor surface electric-field strength,radio interference and audible noises, etc in the construction of ultra-high voltage.Compact power transmission technology is an efective method of increasing the natural power of line, natural power of unit cross-sectional area and improving the line electromagnetic environment. In this paper,by using the compact transmission technology, consideration the economy and the electromagnetic environment of ultra-high voltage construction ,establishing a multi-objective nonlinear optimization model with inequality constraints,we get the ultra-high voltage conductors selection type of conductor is symmetrically arranged. By comparing the conductors selection types with the current ultra-high voltage transmission lines,we get a ultra-high voltage conductors selection types with better economic and environmental friendly. Also, particle swarm optimization has been used to above selection type this paper and to reduce the line electromagnetic environment.Finally,simulations have ben done with the finite element analysis method. Keywords: Ultra-high voltage,compact power transmission technology, electromagnetic environment, conductor selection types, the finite element analysis method

# 1 引言

紧凑型输电技术通过对导线的排列方式进行优化，降低线路波阻抗，减小导线表面电场强度，进而达到提高线路输送自然功率，减小线路走廊宽度，改善线路周围电磁环境的目的[1-5]。苏联曾运用紧凑型输电技术对 $3 3 0 \mathrm { k V }$ 和 $5 0 0 \mathrm { k V }$ 线路的导线排列方式进行了优化[，我国也对 $5 0 0 \mathrm { k V }$ 及 $7 5 0 \mathrm { k V }$ 紧凑型输电线路的导线排列进行了相关研究[7-8]，但目前国内外对紧凑型输电技术运用于 $1 ~ 0 0 0 \mathrm { k V }$ 特高压交流输电线路导线选型的研究相对较少。

本文提出了一种 $1 ~ 0 0 0 \mathrm { k V }$ 特高压交流输电线路导线选型的选取方法，该方法以提高输电线路自然功率和单位截面积自然功率为目标，并考虑导线表面电场强度、无线电干扰和可听噪声等工程实际约束，建立多目标不等式约束的非线性优化模型，把输电线路的导线选型问题转化为数学模型。通过求解数学模型得到各方面参数较优的导线选型初始方案，并将导线选型初始方案与目前常用的特高压输电线路相比较，得出在自然功率、单位截面积自然功率及电磁环境等方面均较优的导线选型。

此外，为了进一步对导线表面电场强度进行优化，改善导线周围的电磁环境。本文还对上述较优导线选型的子导线排列方式采用了粒子群优化方法进行非对称优化，经过对比分析得出，优化后的子导线表面电场强度、可听噪声及无线电干扰等电磁环境因素均得到减小，达到了优化导线周围电磁环境的目的。

# 2 导线选型的选取方法

# 2.1初始方案的选择

通过对 $5 0 0 \mathrm { k V }$ ， $7 5 0 \mathrm { k V }$ 交流紧凑型线路及 $1 0 0 0 \mathrm { k V }$ 特高压常规输电线路的调研，结合线路设计经验，得到了几种初始方案的备选方案，见表1。

# 2.2建立导线选取模型

在初始方案的选取过程中，以提高线路自然功率和单位截面自然功率为目标建立了相应的多目标模型。具体模型如下

$$
\mathrm { \ n a x \ } \left\{ \begin{array} { l l } { P _ { \mathrm { n 0 } } = \frac { 6 \pi \varepsilon _ { \mathrm { 0 } } n \nu _ { \mathrm { { B } } } r K _ { \mathrm { u t } } U _ { \mathrm { p } } E _ { \mathrm { p e r } } } { 3 n \pi r ^ { 2 } } } \\ { P _ { \mathrm { n } } = 6 \pi \varepsilon _ { \mathrm { 0 } } n \nu _ { \mathrm { { B } } } r K _ { \mathrm { u t } } U _ { \mathrm { p } } E _ { \mathrm { p e r } } } \end{array} \right.
$$

式中， $P _ { \mathrm { n 0 } }$ ， $P _ { \mathrm { ~ n ~ } }$ 分别为导线单位截面自然功率和总的自然功率； $\scriptstyle { \varepsilon _ { 0 } }$ 为介电常数； $n$ 为导线分裂数； $\nu _ { \mathrm { { B } } }$ 为相位矩阵； $\boldsymbol { r }$ 为导线半径； $K _ { \mathrm { u t } }$ 为导线有效利用系数；$U _ { \mathfrak { p } }$ 为相电压； $E _ { \mathrm { p e r } }$ 为导线表面极限场强；其他参数见文献[6]。

在建立求解模型的同时还要考虑可听噪声、无线电干扰及子导线表面的最大电场强度等工程实际约束，约束条件如式（2）所示

# 表1初始方案的备选方案

Tab.1The possible ones of initial solution   

<html><body><table><tr><td>分裂数</td><td>相排列方式</td><td>子导线半径/mm</td><td>子导线截面积/mm</td><td>分裂间距/mm</td><td>相间距离/m</td></tr><tr><td>8</td><td>等腰倒三角</td><td>14.93</td><td>700</td><td>450</td><td>16</td></tr><tr><td>8</td><td>等边倒三角</td><td>14.93</td><td>700</td><td>450</td><td>16</td></tr><tr><td>10</td><td>等腰倒三角</td><td>13.82</td><td>600</td><td>450</td><td>16</td></tr><tr><td>10</td><td>等边倒三角</td><td>13.82</td><td>600</td><td>450</td><td>15</td></tr><tr><td>12</td><td>等腰倒三角</td><td>13.23</td><td>550</td><td>375</td><td>13</td></tr><tr><td>12</td><td>等边倒三角</td><td>13.23</td><td>550</td><td>400</td><td>13</td></tr><tr><td>14</td><td>等腰倒三角</td><td>12.60</td><td>376</td><td>378</td><td>12.5</td></tr><tr><td>14</td><td>等边倒三角</td><td>12.60</td><td>376</td><td>378</td><td>12.5</td></tr></table></body></html>

s.t. $\begin{array}{c} \begin{array} { r l } & { \{ 1 2 \mathrm { m } \leqslant L \leqslant 1 6 \mathrm { m }  } \\ & { \{ 9 . 7 7 \mathrm { m } \leqslant r \leqslant 1 7 \mathrm { m m }  } \\ & {  1 5 . 0 \leqslant S / d \leqslant 1 8 . 0 } \\ & {  \vphantom { ( 1 . 5 \mathrm { m } \leqslant S / d \&  }  } \\ & {  \vphantom { ( 1 . 5 \mathrm { m } \leqslant S / } \mathrm { d } \mathrm { B } \mathrm { ( A ) } } \\ & {  \vphantom { ( 1 . 5 \mathrm { m } \leqslant S / } \mathrm { d } \mathrm { B } ( \mathrm { \forall } \mathrm { / \mathrm { m } } )   } \\ & {  \vphantom { ( 1 . 5 \mathrm { m } \leqslant 1 } \mathrm { d } \mathrm { \leqslant 0 . 8 8 } E _ { 0 }  } \end{array}   \end{array}$

式中， $L$ 为相间距离； $d$ 为子导线直径； $s$ 为分裂间距，均为导线结构尺寸的约束。 $L _ { \mathrm { A N } }$ 为可听噪声；$E _ { \mathrm { l i n } }$ 为无线电干扰； $E _ { \mathrm { i m a x } }$ 为子导线最大表面场强，均为电磁环境约束。

在备选方案的基础上，本文以Matlab为计算平台对上述几种备选方案进行求解，得到各备选方案的最优解，见表2。

# 表2备选方案的求解结果

Tab.2 The results of models   

<html><body><table><tr><td>分裂数</td><td>相排列方式</td><td>子导线半径/mm</td><td>分裂间距/mm</td><td>相间距/m</td><td>自然功率/MW</td><td>单位截面自然功率/(MW/mm)</td></tr><tr><td>8</td><td>等腰倒三角</td><td>无解</td><td></td><td></td><td></td><td></td></tr><tr><td>8</td><td>等边倒三角</td><td>无解</td><td></td><td></td><td></td><td></td></tr><tr><td>10</td><td>等腰倒三角</td><td>16.43</td><td>401.48</td><td>14.7</td><td>5 613</td><td>0.242</td></tr><tr><td>10</td><td>等边倒三角</td><td>16.08</td><td>408.89</td><td>14.9</td><td>5 628</td><td>0.249</td></tr><tr><td>12</td><td>等腰倒三角</td><td>13.37</td><td>372.32</td><td>13.0</td><td>6107</td><td>0.311</td></tr><tr><td>12</td><td>等边倒三角</td><td>13.33</td><td>376.88</td><td>13.1</td><td>6116</td><td>0.314</td></tr><tr><td>14</td><td>等腰倒三角</td><td>10.94</td><td>333.84</td><td>12.6</td><td>6342</td><td>0.402</td></tr><tr><td>14</td><td>等边倒三角</td><td>10.71</td><td>337.80</td><td>12.8</td><td>6353</td><td>0.407</td></tr></table></body></html>

通过对表2进行分析，可得到如下规律：

(1）增加分裂数，既能够增大线路自然功率，又能够大幅提高单位截面自然功率。(2）在相同分裂数的情况下，等边三角形的排列方式有较高的自然功率和单位面积的自然功率。(3）增大子导线半径，可以增大输电线路自然功率，但导线半径增大的同时会导致线路单位截面积自然功率降低。

经以上分析，结合工程实际，增加分裂数会给工程上的施工、检修等带来较大的不便，因此，导线的分离数不宜太大。模型求解的备选方案为：10分裂，等边倒三角排列，子导线半径 $r = 1 6 . 0 8 \mathrm { m m }$ ，分裂间距 $S = 4 0 8 . 8 9 \mathrm { m m }$ ，相间距离 $L = 1 4 . 9 \mathrm { m }$ ；12分裂，等边倒三角排列，子导线半径 $r = 1 3 . 3 3 \mathrm { m m }$ ，分裂间距 $S = 3 7 6 . 8 8 \mathrm { m m }$ ，相间距离 $L = 1 3 . 1 \mathrm { m }$ 。

结合工程实际，导线选择的初始备选方案为相导线采用 $1 0 \times \mathrm { L G J } { - } 5 0 0 / 3 5$ 的等边倒三角形排列方式，相间距离 $1 4 . 9 \mathrm { m }$ ，分裂间距 $4 0 0 \mathrm { { m m } }$ ，最下相导线平均对地高度 $2 0 \mathrm { m }$ ； $1 2 \times \mathrm { L G J } { - } 4 0 0 / 3 5$ 的等边倒三角形排列方式，相间距离 $1 3 . 1 \mathrm { m }$ ，分裂间距$3 7 5 \mathrm { m m }$ ，最下相导线平均对地高度 $2 0 \mathrm { m }$ 。

# 2.3较优导线选型的选择

本文经过对 $1 ~ 0 0 0 \mathrm { k V }$ 特高压常规输电线路的调研，比较了特高压交流试验示范工程采用的$8 \times \mathrm { L G J } { - } 5 0 0 / 3 5$ 导线，分裂间距 $4 0 0 \mathrm { { m m } }$ ，典型酒杯塔和猫头塔分别采用的ZBSI、ZMP1， $1 ~ 0 0 0 \mathrm { k V }$ 淮南－上海同塔双回线路采用的 ${ 8 \times \mathrm { L G J } } { - 6 3 0 } / { 4 5 }$ ，分裂间距 $4 0 0 \mathrm { m m }$ ，典型杆塔为 $\mathrm { S K } 3 0 1 ^ { \left[ 9 \right] }$ 。将这3种典型杆塔与 $1 0 \times \mathrm { L G J } { - } 5 0 0 / 3 5$ 的单回紧凑型等边倒三角布置及 $1 2 \times \mathrm { L G J } { - } 4 0 0 / 3 5$ 的单回紧凑型等边倒三角布置作为优化初始方案的备选方案。

在模型的求解过程中，以Matlab为计算平台进行计算，得到所选取的各备选方案模型的电磁环境参数，见表3。

通过对表3进行分析，可知：

较之于8分裂导线的常规单回路，特高压单回紧凑型输电线路采用等边倒三角布置的 $1 0 \times 5 0 0$ 排列与 $1 2 \times 4 0 0$ 排列两种方案的磁感应强度及场强大于 $4 \mathrm { k V / m }$ 的区域宽度大大减小，自然功率及单位走廊的输送功率大幅增加。特高压紧凑型采用 $1 0 \times 5 0 0$ 导线排列和采用 $1 2 \times 4 0 0$ 导线排列方案较常规单回路ZBS1杆塔布置自然功率分别增加约$2 9 \%$ 和 $40 \%$ ，单位走廊输送功率分别为后者的3.8倍和4.1倍。

对于 $1 0 \times 5 0 0$ 、 $1 2 \times 4 0 0$ 两种导线方案，这两种导线的走廊宽度和总截面基本相当，表面上看，$1 0 \times 5 0 0$ 方案相间距较大会增加杆塔投资，但由于

表3紧凑型与常规单双回路电磁环境参数比较  
Tab.3EM parameters of compact and conventional single-circuit and double-circuit transmission lines   

<html><body><table><tr><td>参数</td><td>导线结构</td><td>分裂间距 /mm</td><td>下相最低 高度/m</td><td>场强最大值 /(kV · m-1)</td><td>磁感应强度 最大值/uT</td><td>可听噪声 /dB(A)</td><td>无线电干扰 dB(μV · m-1)</td><td>自然功率 /MW</td><td>单位走廊输送 功率/(MW/m)</td><td>场强>4kV/m 的区域宽</td></tr><tr><td>单回ZBS1</td><td>8×500</td><td>400</td><td>23</td><td>9.67</td><td>36.13</td><td>51.67</td><td>50.64</td><td>4369</td><td>41.7</td><td>104.7</td></tr><tr><td>单回 ZMP1</td><td>8×500</td><td>400</td><td>22</td><td>9.60</td><td>32.41</td><td>51.83</td><td>52.36</td><td>4478</td><td>56.8</td><td>78.9</td></tr><tr><td>双回 SK301</td><td>8×630</td><td>400</td><td>22</td><td>9.50</td><td>27.85</td><td>54.26</td><td>52.52</td><td>2×4 643</td><td>116.1</td><td>80.0</td></tr><tr><td>紧凑相间距离 14.9m</td><td>10 × 500</td><td>400</td><td>20</td><td>9.83</td><td>21.16</td><td>54.99</td><td>52.41</td><td>5628</td><td>159.0</td><td>35.4</td></tr><tr><td>紧凑相间距离 13.1m</td><td>12 ×400</td><td>375</td><td>20</td><td>9.84</td><td>19.81</td><td>54.93</td><td>50.70</td><td>6116</td><td>171.3</td><td>35.7</td></tr></table></body></html>

$1 2 \times 4 0 0$ 导线方案分裂数的增加，使得杆塔总的重量增加[10-]。同时12分裂导线的施工及金具的安装较10分裂导线要困难，总的投资费用会较10分裂方案增加。从增加输电线路输送容量、减小线路投资及施工难度的角度综合来看， $1 0 \times 5 0 0$ 导线排列方案更好。

综合工程实际，较优方案选择为：各相导线采用 $1 0 \times \mathrm { L G J } { - } 5 0 0 / 3 5$ ，等边倒三角形排列方式，相间距离为 $1 4 . 9 \mathrm { m }$ ，最下相导线平均对地高度 $2 0 \mathrm { m }$ ，分裂间距400mm[12-13]。

# 3子导线排列方式非对称优化

为了进一步减小子导线表面的电场强度，改善线路周围的电磁坏境，本文采用粒子群优化算法对所得导线选型的子导线排列方式进行优化。

# 3.1 目标函数

本文对子导线进行优化排列的目的是为了使各子导线表面电场强度分布均匀，因此引入反映各子导线表面电场强度不均匀度的函数（3）作为目标函数。

$$
f = \frac { \left| E _ { \mathrm { m a x } } - E _ { \mathrm { m i n } } \right| } { E _ { \mathrm { a v e r } } }
$$

式中， $E _ { \mathrm { m a x } }$ 为相导线的最大表面电场强度； $E _ { \mathrm { m i n } }$ 为相导线的最小表面电场强度； $E _ { \mathrm { a v e r } }$ 为相导线的平均表面电场强度。

$f$ 的值越小，子导线表面电场强度分布就越均匀。由于 $1 ~ 0 0 0 \mathrm { k V }$ 特高压单回紧凑型输电线路和特高压常规线路应具有同样的环境保护要求，因此，$1 ~ 0 0 0 \mathrm { k V }$ 特高压单回紧凑型线路的电磁环境与常规特高压线路相同[1-2.14-17]，故目标函数（3）的约束条件同式（2）。

# 3.2优化方法分析

当子导线远离相导线的几何中心时，其相邻子导线对其本身的屏蔽作用将减弱，进而增大其本身的表面电场强度，降低其相邻子导线的表面电场强度；反之，当子导线靠近相导线几何中心时，其相邻子导线对其本身的屏蔽作用将增强，进而降低其本身的表面电场强度，增大其相邻子导线的表面电场强度。因此，对于输电线路的子导线，当其表面电场强度低于平均值时，可让其相对远离子导线的中心；反之，可以让导线表面电场强度低于场强平均值的输电线路子导线相对靠近相导线的几何中心。

# 3.3优化前后导线表面电场强度分析

由导线选型方案知，该导线选型优化前在空间中各子导线的排列分布如图1所示。

![](images/a229a906aa1db75bdd4c35d9a0954a7202d95a1f2a5bd00153ca869fe1dab2c0.jpg)  
图1子导线均匀排列示意 (单位：m) Fig.1Symmetrical arrangement of sub-conductors

子导线排列方式优化后（优化前后子导线半径、导线对地高度、相导线间距及所用导线型号均不变），得到的优化方案示意如图2所示。

0.666 0.666 0.640 Q36.531.4°0 0.651 0.651031.4 136.5° 0.640 38.3° 0.632 38.3 0.649! 48.4° 0.632 ? 48.4°0.649 ? 37.6° 37.6° 35.2° 35.2° 35.5° 37 53690.652 0.652 23.69, 35.5 0.649 35.8° 0.650 0.650 35.80 0.649 9 1 + D 0.631 0.619 0.619 0.631 0.646 0.649 ① 0.649 Q33.3° 33.3° ? 0.649 33.2 20 33 0.649 ? 36.0° 36.0° 0.64835.8° 35.8 0.648 0.648 40.3° 40.3° D 0.648 0.648

图3给出了子导线前后两种方式下的子导线表面电场强度分布情况对比。

![](images/58be05b5f75e647d317ba288c1ea76f7fa9e580d4f7ddacaff304034866f3ccc.jpg)  
图2子导线优化排列示意（单位：m) Fig.2Optimized arrangement of sub-conductors

由图3可知，优化前子导线表面电场强度分布很不均匀，优化排列后的导线表面电场强度分布基本均匀。优化前子导线表面场强的最大值为$2 4 . 6 7 \mathrm { k V / c m }$ ，最小值为 $2 0 . 6 8 \mathrm { k V / c m }$ ，前者比后者大 $1 9 . 3 1 \%$ ；优化后子导线表面场强的最大值为$2 3 . 7 9 \mathrm { k V / c m }$ ，最小值为 $2 2 . 3 3 \mathrm { k V / c m }$ ，前者只比后者大 $6 . 5 4 \%$ 。

可见，通过改变子导线的排列方式，可大幅度降低导线表面电场强度的不均匀度。

# 3.4优化前后各电气参数的对比

由于优化后的子导线表面电场强度不均匀度得到大幅度减小，子导线表面的最大电场强度得以减

小，因此和子导线表面电场强度相关的无线电干扰、可听噪声水平均有所减小，见表4。

# 表4子导线优化前后的电气参数比较

Tab.4Contrast of electric parameters before and after optimization   

<html><body><table><tr><td>电气参数</td><td>优化排列前</td><td>优化排列后</td></tr><tr><td>导线表面最大场强 Emax/(kV·cm-1)</td><td>24.67</td><td>23.79</td></tr><tr><td>场强不均匀度(%)</td><td>19.31</td><td>6.54</td></tr><tr><td>地面电场/(kV·cm-1)</td><td>8.42</td><td>8.43</td></tr><tr><td>无线电干扰/[dB(uV·m-1)]</td><td>52.41</td><td>51.23</td></tr><tr><td>可听噪声(湿导线）/(dB·A")</td><td>54.99</td><td>53.34</td></tr><tr><td>自然功率/MW</td><td>5628</td><td>5630</td></tr></table></body></html>

# 4基于有限元法的输电线路电场强度仿真

为了验证Matlab仿真结果的正确性，本文通过有限元分析法求得导线表面电场强度，并与Matlab仿真运算结果相互比较。

# 4.1基于Ansys的输电线路模型的建立

本文通过Ansys 建立 $1 ~ 0 0 0 \mathrm { k V }$ 单回紧凑型输电线路的二维模型，对线路进行有限元分析，线路模型的剖分图如图4所示。

![](images/2cfebb9673725f27f7183ad75efca84c37484fccc807141c15498cf923bf8fe8.jpg)  
图3子导线表面电场强度对比 Fig.3Contrast of electric-field intensity of sub-conductor surface   
图4Ansys线路模型剖分图  
Fig.4Subdivision graph of Ansys lines’model

# 4.2有限元仿真结果分析

利用有限元分析法，对最优选型进行详细仿真，求取子导线表面最大电场强度，并将所得结果与Matlab运行结果相互比较。优化排列时，B相电场强度Ansys分析结果图如图5所示。

由Ansys仿真结果可知，子导线表面最大电场强度为 $2 2 . 8 7 \mathrm { k V / c m }$ ，由前述Matlab运行结果知子导线表面最大电场强度为 $2 3 . 7 9 \mathrm { k V / c m }$ 。分析比较上述两结果可知，由Ansys仿真所得结果偏大，两次结果存在 $3 . 8 \%$ 的误差，满足工程上的要求。由此可知，以Matlab 解析法计算的子导线表面最大电场强度是比较准确的。

![](images/551f3b820185708d4e54df5ee71eb589694f23c18cfd6e49446359b683e507a5.jpg)  
图5优化排列时B相导线Ansys仿真图 Fig.5Phase B's EFI analysis of transmission lines configurated in 1O-division equilateral inverted triangle

# 5 结论

通过对特高压交流紧凑型输电线路导线选型及子导线排列方式优化进行研究，得到以下结论：（1）特高压交流紧凑型输电线路导线选型采用$1 0 \times \mathrm { L G J } { - } 5 0 0 / 3 5$ 导线，等边倒三角型布置，分裂间距 $4 0 0 \mathrm { { m m } }$ ，相间距离取 $1 4 . 9 \mathrm { m }$ 具有较高的经济性和工程实际性。(2）优化排列后的导线选型具有较高的研究价值，子导线表面电场强度的不均匀度大幅减小，线路表面的可听噪声、无线电干扰强度均得到大幅度降低，导线周围电磁环境得到改善。

# 参考文献

[1] 易辉，纪建民．交流架空线路新型输电技术[M].北京：中国电力出版社，2006.  
[2] Huang Weigang. Study on conductor configurationof $5 0 0 \mathrm { k V }$ Chang-Fang compact line[J].IEEETransactions on Power Delivery,2003,18(3):1002-1008.  
[3] 万保权，邬雄，张业茂，等．750kV单回紧凑型输电线路的电磁环境[J]．高电压技术，2009,35(3): 597-600.Wan Baoquan,Wu Xiong,Zhang Yemao,et al.Electro-magnetic environment of $7 5 0 \mathrm { k V }$ singlecircuit compact transmission lines[J].High VoltageEngineering,2009,35(3): 597-600.  
[4] 屠强，李新建，邬雄，等． $7 5 0 \mathrm { k V }$ 同塔双回紧凑型输电线路关键技术研究：电磁环境课题研究[R].西安：西北电网公司．武汉：国网武汉高压研究院，2008.  
[5] 亚历山大罗夫TH．超高压送电线路的设计[M].倪宗德，译．北京：水利电力出版社，1987.  
[6] 阿历克山德罗夫．动力系统传输电能新方法[M].北京：水利电力出版社，1992：44-45.  
[7] 高玉明．紧凑型输电线路与分裂导线的优化设计[J]．电力技术，1992，15(6)：51-56.Gao Yuming.The optimization of compacttransmission lines and split conductor[J]. ElectricPower Technology, 1992,15(6): 51-56.  
[8] 郭琳霞，龚有军．750kV紧凑型输电线路导线表面电场强度优化[J]．电力建设，2011，32(6)：1-4.Guo Linxia, Gong Youjun. Optimization of electricfield intensity on conductor surface in $7 5 0 \mathrm { k V }$ compact power transmission line[J]. Electric PowerConstruction, 2011, 32(6): 1- 4.  
[9] 邬雄，万保权，张广洲，等。 $1 0 0 0 ~ \mathrm { k V }$ 特高压交流同塔双回线路电磁环境及导线优化研究[R]．武汉：国网武汉高压研究院，2008.  
[10]张殿生．电力工程高压送电线路设计手册[M]．第2版．北京：中国电力出版社，2003.  
[11]李勇伟，王劲，薛春林．交流特高压试验示范工程晋东南—南阳—荆门 $1 0 0 0 ~ \mathrm { k V }$ 输电线路工程初步设计/导地线选择[R]．北京：中国电力顾问集团公司，2006.  
[12]张业茂，张广洲，万保权，等． $1 0 0 0 ~ \mathrm { k V }$ 交流单回紧凑型输电线路电磁环境研究[J]．高电压技术,2011，37(8): 1888-1894.Zhang Yemao, Zhang Guangzhou, Wan Baoquan.Electromagnetic environment of $1 0 0 0 \mathrm { k V }$ AC single-circuit compact transmission lines[J]. High VoltageEngineering, 2011, 37(8): 1888-1894.  
[13]胡毅，万保权，何慧雯. $1 0 0 0 \mathrm { k V }$ 交流紧凑型输电关键技术研究[J]．高电压技术，2011，37(8)：1825-1831.Hu Yi,Wan Baoquan, He Huiwen. Key technologiesof $1 0 0 0 \mathrm { k V }$ AC compact transmission[J].HighVoltage Engineering,2011, 37(8): 1825-1831.  
[14]Huang Daochun,Ruan Jiangjun. Discussion onelectromagnetic environment of $1 0 0 0 \mathrm { k V }$ ACoverhead transmission lines in china[C]. IEEE PowerEngineering Conference, 2007: 752-757.  
[15]黄俊璞，林 韩，宋福根，等．不同杆塔转角度

数对输电线路电场的影响[J]．电气应用，2016，35(14): 69-72.[16] 中国电力企业联合会．GB50665—20111000kV架空输电线路设计规范[S]．北京：中国计划出版社，2012.

[17] 邬雄，万保权，路遥． $1 0 0 0 \mathrm { k V }$ 交流输电线路电磁环境的研究[J]．高电压技术，2006，32(12)：1-6.Wu Xiong,Wan Baoquan,Lu Yao.Electromagneticenvironment research of $1 0 0 0 \mathrm { k V }$ AC transmissionline[J].High Voltage Engineering,2006,32(12):1- 6.