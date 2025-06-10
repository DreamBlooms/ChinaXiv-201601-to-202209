# 博斯腾湖有机物污染改善方案研究

胡春明¹，娜仁格日乐²，马金锋'，秦晶'，尤立（1．中国科学院生态环境研究中心,北京100085；2．新疆巴音郭楞蒙古自治州博斯腾湖科学研究所,新疆 库尔勒841000)

摘要：博斯腾湖径流入湖、出湖口过近的水文现状对有机物浓度及其空间分布形成制约。采用MIKE21软件构建水动力水质二维数值模型,分析工程方案对博斯腾湖有机物污染的改善效果。根据模拟结果以及配对样本 $T$ 检验分析：在现状基础上实施扬水站东移或引开都河水 $3 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ 进入黄水沟,均可显著改善博斯腾湖有机物污染，年均化学需氧量(COD)浓度分别降低 $1 3 . 4 \%$ 和 $8 . 9 1 \%$ ;两方案同时实施效果更为显著，年均COD浓度降低$2 0 . 2 \%$ ;通过工程实施改善博斯腾湖有机物污染切实可行。但在流域尺度上,工程方案仅改变了有机物平衡而未改变总量，博斯腾湖有机物污染改善源于污染物转移至下游孔雀河。

关键词：博斯腾湖；有机物污染；MIKE21；COD；水文条件

博斯腾湖是我国最大内陆湖泊，在区域社会经济发展、生态平衡维持、生物多样性保持等方面发挥着重要作用[1-2]。随着矿化度上升、有机物污染、水资源短缺等问题凸显[3],博斯腾湖生态环境问题受到学者关注，包括围绕水质水量[4-5]、水生植物[6-7]、水生生物[8-9]、沉积物[10-11]的基础研究,面向湖泊需水量[12]、生态水位[13]、水资源[14-15]的管理研究以及针对矿化度分布[16]、塔里木河输水[17]等实际问题的工程探讨。

博斯腾湖核心环境问题在于有机物污染，突出表现为大部分湖区水体化学需氧量（COD，chemicaloxygendemand)浓度高于地表水Ⅲ类标准限值，以及空间差异显著[18]。有机物对湖泊自净能力反映较弱[19],浓度降低更多依靠稀释交换作用,而博斯腾湖径流入湖、出湖口位置较近，径流对湖水稀释作用更多体现在西南局部湖区。在现状水文条件下，大部分湖区有机物无法得到稀释，也难以通过水体交换而排出，阻碍博斯腾湖全面水质达标。因此，通过工程优化径流入湖及出湖口，继而促进湖水稀释交换成为改善博斯腾湖有机物污染的潜在方案。

本文采用MIKE21软件构建水动力水质二维数值模型，模拟不同工程方案对于博斯腾湖有机物污染的改善效果，以期为博斯腾湖水环境保护提供理论依据和工程参考。

# 1 研究区域概况

博斯腾湖位于中国天山南麓焉耆盆地东南部低洼处,地理位置介于 $8 6 ^ { \circ } 1 9 ^ { \prime } \sim 8 7 ^ { \circ } 2 8 ^ { \prime } \mathrm { E }$ ， $4 1 ^ { \circ } 4 6 ^ { \prime } \sim$ $4 2 ^ { \circ } 0 8 ^ { \prime } \mathrm { N }$ ，是开都河等水系的尾闾以及孔雀河源头（图1）。博斯腾湖由公路分隔为大小湖区：大湖区在水位 $1 ~ 0 4 7 . ~ 0 0 ~ \mathrm { ~ m ~ }$ 时,面积 $1 \ \mathrm { 0 6 4 . } \ \mathrm { 1 } \ \mathrm { k m } ^ { 2 }$ ，容积$7 3 . 0 3 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 }$ ,平均水深约 $7 . 5 \mathrm { ~ m ~ }$ ,最深处约 $1 6 \mathrm { ~ m ~ }$ ：小湖区为诸多浅小湖泊和芦苇沼泽湿地。

博斯腾湖补给河流历史上有开都河、黄水沟、清水河、曲惠沟、乌拉斯台河，现状仅余开都河东支。湖滨的黄水沟湿地承担着污水深度净化功能，部分污水通过渗漏以及汛期行洪进入大湖区。博斯腾湖唯一出水口是位于大湖区西南角的扬水站，水体由东、西两个泵站提升进入孔雀河。

# 2 MIKE21模型

# 2.1 基本方程

MIKE21是丹麦水利研究所开发的系列水动力学软件之一,在水环境模拟中得到诸多应用[20-21]博斯腾湖为浅水湖泊，水平尺度远大于垂直尺度，用MIKE21HD模块构建垂向平均的二维水动力模型，控制方程如式（1）式（2）、式（3）；采用MIKE21

![](images/319754651caf01320222bd17174edd7e00fecc70c99ca0ef7f29afee0988bf15.jpg)  
图1博斯腾湖水系图

Transport模块构建水质模型，基本方程如式（4）。

$$
\frac { \partial h } { \partial t } + \frac { \partial h \bar { u } } { \partial x } + \frac { \partial h \bar { v } } { \partial y } = h S _ { f }
$$

$$
\frac { \partial h \bar { u } } { \partial t } + \frac { \partial h \bar { u } ^ { 2 } } { \partial x } + \frac { \partial h \bar { v } \bar { u } } { \partial y } = f \overline { { v } } h - g h \frac { \partial \eta } { \partial x } - \frac { g h ^ { 2 } \partial \rho } { 2 \rho \ \partial x } + \frac { \tau _ { s x } } { \rho } - \frac { \tau _ { b x } } { \rho } +
$$

$$
\frac { \partial } { \partial x } ( h T _ { x x } ) \ : + \frac { \partial } { \partial y } ( h T _ { x y } ) \ : + h u _ { 2 } S _ { f }
$$

$$
\frac { \partial h \bar { v } } { \partial t } + \frac { \partial h \bar { v } ^ { 2 } } { \partial y } + \frac { \partial h \bar { v } \bar { u } } { \partial x } = { \bf \nabla } - f \bar { v } h - g h \frac { \partial \eta } { \partial y } - \frac { g h ^ { 2 } \partial \rho } { 2 \rho { \bf \nabla } \partial x } + \frac { \tau _ { s y } } { \rho } -
$$

$$
\frac { \tau _ { b y } } { \rho } + \frac { \partial } { \partial x } ( h T _ { x y } ) \ : + \frac { \partial } { \partial y } ( h T _ { y y } ) \ : + h v _ { 2 } S _ { f }
$$

式中： $\mathbf { \Psi } _ { t } \mathbf { \Psi } _ { \left. \begin{array} { l } { \left. \begin{array} { r l r l } \end{array} \right. } \end{array} \right. }$ 为时间; $u$ 及 $\mathbf { \sigma } _ { v }$ 为流速； $g$ 为重力加速度； $\eta$ 为水位； $h$ 为水深： $f$ 为科氏力系数； $\rho$ 为密度, $S _ { f }$ 为源项； $\boldsymbol { \tau } _ { s x } \hphantom { \tau } _ { s y } \hphantom { \tau } \cdot \boldsymbol { \tau } _ { b x } \hphantom { \tau } \cdot \boldsymbol { \tau } _ { b y }$ 为 $x , y$ 方向的表面风应力和底部切应力。

$$
\frac { \partial h \overline { { C } } } { \partial t } + \frac { \partial h \bar { u } \overline { { C } } } { \partial x } + \frac { \partial h \bar { v } \overline { { C } } } { \partial y } = h F _ { _ c } - h k _ { _ p } \overline { { C } } + h C _ { _ s } S _ { t }
$$

式中： $\boldsymbol { F } _ { c }$ 为水平扩散项; $\bar { C }$ 为垂向平均浓度； $S _ { \ t { t } }$ 为源汇项； $k _ { p }$ 为线性衰减速率; $C _ { s }$ 为污染物浓度。模型计算范围为博斯腾湖大湖区，采用三角形不规则网格（图2），三角形边长约为 $5 0 \mathrm { ~ m ~ }$ ○

# 2.2 模型验证

从新疆巴音郭楞蒙古自治州环境保护局收集2012—2016 年博斯腾湖17个国家地表水环境质量监测点水质数据、开都河东支水质数据及污染物数据，从塔里木河流域管理局收集开都河2013一2016年东支径流量、扬水站输水量、博斯腾湖水位等月均水文数据。鉴于博斯腾湖湖流受风场影响较大的特征[16],从气象局收集 2013—2016 年降雨、蒸发、风速、风向等月均气象数据作为模型基础输入参数。

![](images/48e2175d2856dca8db5dfdcbbf913f99be27d8616e241ce829fd92d20a6d94cc.jpg)  
Fig.1The water system of Bosten Lake   
图2模型计算网格  
Fig.2The computational grid of MIKE21

以2013—2015年数据进行模型率定，以2016年数据进行结果验证。模型初始条件为2013年1月1日，时间步长为 $5 ~ \mathrm { m i n }$ ,初始水位为实测水位，初始COD浓度以2012年10月实测浓度代替

模型模拟值与实测值对比如图3所示，采用过程线拟合中常用的均方根误差（RMSE）、纳什效率系数（NSE）两个函数进行验证[22-23]。RMSE计算函数如式（5），表征模拟值与实测值之间的偏差。NSE计算函数如式（6），表征两组数据序列的模拟精度：接近1则表示模拟质量越好、模型可信度越高；接近0则表示模型总体结果可信，但过程模拟误差较大；小于0则表明模拟结果不可信。

![](images/5378ea4ebc1ba57460683fc125b7db06b67551be2f4a0d7a4cf6cb93b81ae679.jpg)  
图3水位及化学需氧量(COD)模拟验证情况 Fig.3Verification of water level and COD

$$
{ \mathrm { R M S E } } = { \sqrt { { \frac { 1 } { N } } { \sum _ { i = 1 } ^ { n } ( \ Q _ { 0 } ^ { i } - Q _ { s } ^ { i } ) ^ { 2 } } } }
$$

$$
\mathrm { N S E } = 1 - \frac { \displaystyle \sum _ { i = 1 } ^ { n } ( Q _ { 0 } ^ { i } - Q _ { s } ^ { i } ) ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { n } ( Q _ { 0 } ^ { i } - \overline { { Q _ { 0 } } } ) ^ { 2 } }
$$

式中： $Q _ { 0 }$ 为实测值; $Q _ { s }$ 为模拟值; $Q _ { 0 }$ 为实测值的平均值。

验证表明，水位模拟结果良好（ $\mathrm { ^ { \prime } R M S E } = 0 . 0 5 6$ $\mathrm { N S E } = 0 . \ 9 7 \$ ),COD模拟结果整体可信（ $\mathrm { R M S E } =$ $1 . 7 7 , \mathrm { N S E } = 0 . 3 6 )$ 。

# 3 结果与讨论

# 3.1 工程方案

针对博斯腾湖径流入湖、出湖口距离较近的状况，结合区域实际情况和工程可行性，设计3类工程方案(表1)：径流入湖优化、径流出湖优化、入湖出

湖同时优化。

径流出湖优化从增强开都河对湖水稀释作用、提高出湖水体污染物总量角度出发，将现状扬水站向东部迁移，根据湖岸特征设计3个迁移位置：1#为南岸最北部；2#为二道海心山附近；3#为三道海心山附近。博斯腾湖南部现状为荒漠区域，扬水站迁移及新建输水设施均具有较高可行性。

径流入湖优化从恢复博斯腾湖自然水文条件出发，将开都河东支部分径流引入黄水沟（多年平均径流量为 $2 . 9 1 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ )，设计引水径流量分别为$1 \times 1 0 ^ { 8 } \cdot 2 \times 1 0 ^ { 8 } \cdot 3 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \cdot \mathrm { \Large ~ a } ^ { - 1 }$ 的3种方案。开都河与黄水沟均位于焉耆盆地,相互距离较近且地势平坦，引水工程具有可行性。此外，引水工程可作为黄水沟汛期洪水入湖通道，从而减少湿地污水入湖量。

入湖出湖同时优化则为上述两类方案中最优方案的组合（方案 $^ { 2 + }$ 方案6）。

# 3.2 模拟结果

各方案2016年模拟结果统计分析如表2。在收集2012—2016 年的博斯腾湖水质数据中，最后一批数据为2016年10月15日，各方案模拟的该日COD浓度场如图4。

# 表1工程方案设计

Tab.1Design of projects   

<html><body><table><tr><td colspan="2">工程方案</td><td>开都河东支年径流量</td><td>黄水沟年径流量/10m</td><td>扬水站位置</td><td>黄水沟湿地污染物输入</td></tr><tr><td colspan="2">现状</td><td>现状值</td><td>0</td><td>西南角</td><td>模型率定值</td></tr><tr><td rowspan="4">径流出湖优化</td><td>方案1</td><td>现状值</td><td>0</td><td>东南角1#</td><td>模型率定值</td></tr><tr><td>方案2</td><td>现状值</td><td>0</td><td>东南角2#</td><td>模型率定值</td></tr><tr><td>方案3</td><td>现状值</td><td>0</td><td>东南角3#</td><td>模型率定值</td></tr><tr><td>方案4</td><td>现状值减少1×10m</td><td>1</td><td>西南角</td><td>减少至率定值1/5</td></tr><tr><td rowspan="3"></td><td>方案5</td><td>现状值减少2×10m</td><td>2</td><td>西南角</td><td>减少至率定值1/5</td></tr><tr><td>方案6</td><td>现状值减少3×10m</td><td>3</td><td>西南角</td><td>减少至率定值1/5</td></tr><tr><td>方案7</td><td>现状值减少3×10m</td><td>3</td><td>东南角2#</td><td>减少至率定值1/5</td></tr></table></body></html>

表2各方案2016年化学需氧量(COD)浓度模拟结果统计Tab.2Simulation of COD in 2016  

<html><body><table><tr><td rowspan="2">工程方案</td><td colspan="7">COD 浓度/（mg·L-1)</td></tr><tr><td>5月</td><td>6月</td><td>7月</td><td>8月</td><td>9月</td><td>10月</td><td>年均</td></tr><tr><td>现状</td><td>22.26 ± 1.29</td><td>22.16 ±1.78</td><td>21.85 ±1.47</td><td>22.18 ± 1.64</td><td>21.96 ± 1.16</td><td>21.89 ±0.87</td><td>22.05 ±1.19</td></tr><tr><td>方案1</td><td>19.60 ± 1.52</td><td>19.58 ± 1.86</td><td>19.20 ± 1.75</td><td>19.05 ± 2.27</td><td>18.70 ± 1.61</td><td>18.77 ±1.04</td><td>19.15 ± 1.46</td></tr><tr><td>方案2</td><td>19.54 ±1.55</td><td>19.52 ± 1.87</td><td>19.13 ± 1.76</td><td>18.99 ±2.26</td><td>18.67 ±1.61</td><td>18.77 ±1.03</td><td>19.11 ±1.45</td></tr><tr><td>方案3</td><td>19.63 ±1.54</td><td>19.60 ± 1.87</td><td>19.20 ± 1.77</td><td>19.05 ±2.27</td><td>18.72 ±1.61</td><td>18.83 ±1.04</td><td>19.17 ±1.45</td></tr><tr><td>方案4</td><td>20.84 ±1.06</td><td>20.49 ± 1.28</td><td>20.11 ± 1.27</td><td>20.28 ± 1.48</td><td>20.20 ±0.92</td><td>20.00 ±0.92</td><td>20.32 ±0.97</td></tr><tr><td>方案5</td><td>20.73 ± 1.08</td><td>20.37 ±1.30</td><td>19.99 ± 1.35</td><td>20.17 ±1.55</td><td>20.11 ±0.91</td><td>19.91 ±0.91</td><td>20.21 ±1.00</td></tr><tr><td>方案6</td><td>20.60 ±1.10</td><td>20.23 ±1.32</td><td>19.84 ±1.45</td><td>20.04 ±1.63</td><td>20.00 ±0.92</td><td>19.79 ±0.91</td><td>20.09 ±1.05</td></tr><tr><td>方案7</td><td>18.27 ± 1.24</td><td>17.96 ± 1.29</td><td>17.52 ± 1.45</td><td>17.35 ± 1.75</td><td>17.24 ± 1. 13</td><td>17.19 ±0.92</td><td>17.59 ± 1.07</td></tr></table></body></html>

注：数据为"均值 $\pm$ 标准差”。

COD/(mg·L-1) COD/(mg·L-1)   
5.15 ×108 (a)现状 0.025 0.024 5.15 ×108 (b)方案1 0.024 0.025   
5.145 0.023 5.145 0.023   
ororrrirotrm 5.14 0.022 (u) 5.14 0.022   
5.136 0.021 1 5.136 0.021   
5.13 0.02 Cooorrtrt 5.13 0.02   
5.125 5.125   
5.12 0.019 5.12 0.019   
5.115 0.018 5.115 0.018   
y 5..1 0.017 y 5..1 0.017   
×108 ×108   
9.65 9.66 9.67 9.68 9.699.7 9.719.729.73 9.74 0.015 9.659.66 9.679.68 9.699.79.719.729.739.74 0.015   
X coordinate(m)→ COD/(mg · L-1) X coordinate(m)→ COD/(mg ·L-1)   
(c)方案2 0.025 (d)方案3 0.025   
5.15×108 0.024 5.15×108 0.024   
5.145 0.023 5.145 0.023   
(u) 5.14 0.022 (u) 5.14 0.022   
ooorrrotee 5.136 5.125 0.021 0.019 Coorrreree 5.136 5.125 0.021 0.019   
5.115 0.018 5.115 0.018   
y 5.11 ×108 0.017 y 5.11 ×108 0.017   
5.105 0.016 5.105 0.016   
9.65 9.66 9.67 9.68 9.69 9.7 9.719.72 9.73 9.74 9.659.669.67 9.68 9.699.7 9.719.729.73 9.74   
0.015 0.015   
X coordinate(m)→ COD/(mg·L-1) X coordinate(m)→ COD/(mg·L-1)   
5.15 5×108（e）方案4 0.025 0.024 5.15 x108 (f）方案5 0.025 0.024   
5.145 0.023 5.145 0.023   
(omrrrrrotrm 54535 5.12 0 0.019 eoronrrrrrrrt 5 5.12 0.02 0.019   
5.115 0.018 5.115 0.018   
y ×108 0.017 y 565 0.017   
X coordinate(m)→ 0.015 X coordinate(m)→ 0.015   
COD/(mg·L-1) COD/(mg ·L-1)   
×108（g）方案6 0.025 ×108 (h)方案7 0.025   
5.15 0.024 5.15 0.024   
1 5.145 0.023 5.145 0.023   
(ooorrirtrn 5.14 0.022 (u) 5.14 0.022   
5.136 5.125 0.021 0.02 coooerretee 5.136 5.125 0.021 0.02   
5.12 0.019 5.12 0.019   
5.115 0.018 5.115 0.018   
y 0.017 y 0.017   
X coordinate(m)→ 0.015 X coordinate(m)→ 0.015

径流出湖优化的3种方案结果相差不大，分别可实现博斯腾湖年均COD浓度下降 $1 3 . 2 \%$ 、$1 3 . 4 \%$ 和 $1 3 . 0 \%$ 。径流入湖优化的3种方案分别可降低年均COD浓度 $7 . 8 4 \% . 8 . 3 3 \%$ 和 $8 . 9 1 \%$ ，黄水沟年径流量越大，湖区水质改善效果愈好。而径流入湖出湖同时优化则可实现博斯腾湖年均COD浓度下降 $2 0 . 2 \%$ 。

基于模拟结果的标准差分析，方案1、方案2、方案3模拟结果的标准差较现状略有上升，各监测点COD 浓度的离散程度更大，表明博斯腾湖COD 浓度整体空间差异性增大，其原因在于出湖口优化至东南角，仅改善了南部区域COD浓度，却进一步加大了与北部区域的差异。其他方案模拟结果的标准差总体下降，COD浓度空间差异性减小，关键原因在于径流从黄水沟入湖降低了现状污染最为严重的西北区域COD 浓度。

# 3.3 方案检验

在各方案模拟结果中，方案2是径流出湖优化的最佳方案，方案6是径流入湖优化的最佳方案，而方案7则为两者的组合。采用“配对样本 $T$ 检验”分析方案实施对博斯腾湖水质改善效果，根据检验结果（表3），各配对样本检验结果对应的 $\textstyle P < 0 . 0 5$ ，表明在现状基础上实施方案2或方案6均可显著改善博斯腾湖COD浓度，而最终实施方案7则可实现COD 浓度进一步显著改善。

表3各方案配对样本 $_ { T }$ 检验结果  
Tab.3Results of paired samples $T$ -test   

<html><body><table><tr><td></td><td>现状- 方案2</td><td>现状- 方案6</td><td>方案2- 方案7</td><td>方案6- 方案7</td></tr><tr><td>T统计值</td><td>57.363</td><td>11. 684</td><td>9.112</td><td>56.204</td></tr><tr><td>相伴概率(P)</td><td>0.000</td><td>0.000</td><td>0.000</td><td>0.000</td></tr></table></body></html>

# 3.4讨论

湖泊污染物浓度上升根本原因在于总量不平衡，入湖量高于出湖量带来污染物累积。针对博斯腾湖矿化度问题，有研究提出优化设想：韩龙喜等[16]模拟扬水站不同位置对矿化度空间分布产生影响;吴敬禄等[4]分析了扬水站建设运行使博斯腾湖总盐量基本保持在 $9 . 6 0 \times 1 0 ^ { 5 } \mathrm { ~ t ~ }$ 的平衡点，而扬水站东迁可将平衡点降低在 $8 . 5 0 \times 1 0 ^ { 5 }$ to

湖泊污染治理通常采用污染源系统治理、清水产流机制修复、湖泊水体生境改善、流域管理等措施[24]。随着博斯腾湖流域污染源治理及生态保护工程不断实施,湖泊水质持续改善，年均COD 浓度由2013年 $2 8 . 6 8 ~ \mathrm { m g } \cdot \mathrm { L } ^ { - 1 }$ 降至2016年 $2 1 . 5 0 { \mathrm { ~ m g ~ } } ^ { . }$ （20$\mathrm { ~ L ~ } ^ { - 1 }$ ,COD 浓度也逐渐达到一个平衡点。若要继续改善湖区水质，提高污染源治理及生态保护工程效果，需通过工程手段改变博斯腾湖水文条件、打破有机污染物平衡。

开都河水体COD 浓度普遍在 $1 0 \mathrm { \ m g \cdot L ^ { - 1 } }$ 以内，汇入后在西南区域与湖水混合，再由扬水站排入下游孔雀河，出湖水体携带的有机物总量较少。本研究设定的各工程方案本质均为增加开都河径流停留时间，提高径流与湖水稀释混合程度，打破博斯腾湖有机物现状平衡。博斯腾湖水体的5日生化需氧量（BOD5）浓度低（约 $2 \mathrm { \ m g \ \cdot \ L ^ { - 1 } }$ ）、浮游生物较少[8-9],有机物生物降解较弱,稀释交换作用对有机物浓度影响尤为显著，使各方案取得较好改善效果。但从流域尺度考虑，各方案并未减少有机物总量，仅改变有机物时空分布，博斯腾湖有机物总量降低，则意味着下游孔雀河有机物总量升高，生态环境将受到一定影响。

# 4结论

径流入湖、出湖口位置较近的水文现状对博斯腾湖COD浓度及其空间分布形成制约。通过优化径流入湖、出湖可改变博斯腾湖有机物平衡，在不改变有机物总量的情况下降低湖区COD平衡浓度：将扬水站东移可实现全湖年均COD浓度较现状降低$1 3 . 4 \%$ ,引开都河水 $3 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ 进入黄水沟可降低年均COD 浓度 $8 . 9 1 \%$ ,两者同时实施可降低年均COD浓度 $2 0 . 2 \%$ ；后两种方案还对湖区COD浓度空间差异性也有一定改善作用。

# 参考文献(References）:

[1］陈亚宁,李卫红,陈亚鹏,等.塔里木河下游断流河道输水的生 态响应与生态修复[J].干旱区研究，2006，23（4）：521-530. [Chen Yaning,Li Weihong,Chen Yapeng,et al.Ecological response and ecological regeneration of transfusing stream water along the dried-up watercourse in the lower reaches of the Tarim river, Xinjiang[J].Arid Zone Research,2006,23(4）:521-530.]   
[2］孙玉芳,刘维忠.新疆博斯腾湖湿地生态系统服务功能价值评 估[J].干旱区研究,2008,25（5）：741-744.［Sun Yufang,Liu Weizhong.Evaluation on the service functional values of the wetland ecosystem in the Bosten Lake basin,Xinjiang[J].Arid Zone

Research,2008,25(5):741 -744.]

[3]袁峡,杨佃华.新疆博斯腾湖水环境问题研究[J].干旱区研 究,2008,25（5）:735-740.［Yuan Xia,YangDianhua.Study on the aqueous environment problems of the Bosten Lake,Xinjiang [J].Arid Zone Research,2008,25(5) :735-740.]

[4]王亚俊,李宇安,王彦国,等.20 世纪50 年代以来博斯腾湖水盐变化及趋势[J].干旱区研究,2005,22（3）：355-30.[WangYaJun,Li Yu'an,Wang Yanguo,etal. Study on the change of in-flow and salt content of the Bosten Lake,Xinjiang Since the 1950s[J」.AridZoneResearch，2005，22(3):355-30.]

[5］房传苓，王秀君,王家平.新疆博斯腾湖湖周水体碳和盐离子的空间分布［J].干旱区研究,2013,30（2）：226-230.［FangChuanling,Wang Xiujun,Wang Jiaping.Spatial distributions of or-ganic carbon and dissolved ions in the Bosten Lake,Xinjiang[J].Arid Zone Research,2013,30(2):226-230.]

[6］买尔哈巴·买买提汗,玉素甫江·如素力,安尼瓦尔·阿布都热依木，等.近26a博斯腾湖芦苇湿地的动态监测及其驱动因素［J].干旱区研究，2016，33（4）：797-804.［MaierhabaMaim-aitihan,YusufujiangRusuli,AnniwaerAbudureyimu,etal.Dynamicvariation ofPhragmites australis wetland in the Bosten Lake basin and its driving factors in recent 26 years[J].Arid Zone Re-search,2016,33（4):797-804.]

[7］刘浩峰,刘巍,刘玉燕,等.博斯腾湖湿地Cu、Ni 和Pb 的分布特征及其生态风险[J].干旱区研究，2017，34（2）：390-394.[LiuHaofeng,LiuWei,Liu Yuyan,etal.DistributionofCu,NiandPb and ecological risk in the Bosten Lake wetland[J].AridZone Research,2017,34（2):390-394.]

[8]李红,马燕武,祁峰,等.博斯腾湖浮游植物群落结构特征及其影响因子分析[J].水生生物学报，2014,38（5）：921-928.［LiHong,Ma Yanwu,Qi Feng,etal.Phytoplankton in Bosten Lake：community characteristics and driving factors[J].Acta Hydrobio-logica Sinica,2014,38(5):921-928.]

[9］李红,祁峰,谢春刚,等.博斯腾湖浮游动物群落结构特征与分布的季节性变化[J].中国水产科学，2013，20（4)：832-842.[LiHong,Qi Feng,Xie Chungang,et al.Zooplankton in BostenLake:community characteristics and seasonal changes in distribu-tion[J].Journal of Fishery Sciences of China,2013,20(4）:832-842.]

[10］华攸胜,马龙,吉力力·阿不都外力，等.新疆博斯腾湖近现代 湖泊沉积物粒度分布特征及其环境记录[J].干旱区研究，2019， 36(5）:11O9-1116.[Hua Yousheng,Ma Long,Jilili Abuduwaili,et al.Grain-size distribution and its environmental records of modern lacustrine sediments from the Bosten Lake in Xinjiang[J].Arid ZoneResearch,2019,36(5):1109-1116.]

[11］蒲佳，马龙，吉力力·阿不都外力，等.新疆博斯腾湖表层沉积物粒度空间分布特征［J].干旱区研究，2018，35（2）：477-485.［Pu Jia,Ma Long,Jilili Abuduwaili,et al. Spatial distributionof grain size composition of surface sediment in the BostenLake re-gion,Xinjiang[J].Arid Zone Research,2018,35（2）:477-485.]

[12］董雯,崔保山，海米提·依米提,等.基于不同盐度目标的博斯 腾湖需水量研究［J].干旱区地理，2014，37（5）：901-907. [DongWen,CuiBaoshan,Hemid Yimit,et al.Water demand of the Bosten Lake based on different salinity goals[J].Arid Land Geography,2014,37(5):901-907.]

[13］胡春明,娜仁格日乐，尤立.基于水质管理目标的博斯腾湖生态水位研究[J].生态学报，2019，39（2）：748-755.［HuChun-ming,Narengerile,You Li.Study of ecological water levels of Bo-sten Lake for water quality management[J].Acta Ecologica Sini-ca,2019,39(2) :748-755.]

[14］王文辉,黄粤,刘铁，等.开都-孔雀河流域水资源优化配置 [J].干旱区研究,2018,35（5）：1030-1039.［WangWenhui, Huang Yue,Liu Tie,et al.Optimized redistribution of water resources in the Kaidu-Kongque river basin[J].Arid Zone Research,2018,35（5):1030-1039.]

[15］伊丽努尔·阿力甫江,玉素甫江·如素力.基于SD 模型的博斯腾湖水量平衡系统分析与仿真研究［J].水土保持研究，2015,22(6）:126-133.[Ilnur Ghalip,Yusufujiang Rusuli.Anal-ysis and simulation of the water balance of Bosten Lake based onsystem dynamics model[J].Research of Soil and Water Conserva-tion,2015,22(6):126-133.]

[16］韩龙喜，张防修，张芃，等.博斯腾湖湖流及矿化度分布研究[J].水利学报,2004,35（10）：100－105.[Han Longxi,ZhangFangxiu,Zhang Peng,et al.Flow field and salinity distribution oflargeinland lake[J]. Journal ofHydraulicEngineering,2004,35（10):100-105.]

[17］刘登峰，田富强,林木.基于生态水文耦合模型的塔里木河下 游人工输水优化方案研究[J].水力发电学报，2014,33（4）：51 -59.[Liu Dengfeng,Tian Fuqiang,Lin Mu,et al.Study on optimal scheme of water transfer in the lower Tarim riverbased on ecohydrological evolution model[J].Journal of Hydroelectric Engineering,2014,33（4）:51-59.]

[18］谢贵娟，张建平，汤祥明，等.博斯腾湖水质现状（2010—2011年)及近50年来演变趋势[J].湖泊科学，2011，23（6)：837-846.[Xie Guijuan,Zhang Jianping,Tang Xiangming,etal. Spatiotemporal heterogeneity of water quality（201O-2011）and succes-sion patterns in Lake Bosten during the past 5O years[J]. Journalof Lake Sciences,2011,23(6) :837-846.]

[19］任瑞丽，刘茂松，章杰明，等.过水性湖泊自净能力的动态变化[J].生态学杂志,2007，26（8）：1222-1227.［RenRuili,LiuMaosong,Zhang Jieming,et al.Self-purification ability of a water-carrying lake[J].Chinese Journal of Ecology,2007,26（8）:1222-1227. ]

[20］高晓薇,刘培斌，王国青，等.北运河(北京段)水污染特征时空 变化模拟[J].水利水电技术，2016,47（12)：73-77.［Gao Xiaowei,Liu Peibin,Wang Guoqing,et al.Simulation of temporal and spatial variation of water pollution characteristics of North Grand Canal（Beijing-section）［J].Water Resources and Hydropower Engineering,2016,47(12）:73-77.]

[21」周燕，再玲于，苟翡翠，等.基于数值模拟的湖库型景观水体生 态设计方法研究——以MIKE21模型在大官塘水库规划方案 中的应用为例[J].中国园林,2018(3）：123－128.［Zhou Yan, Ran Linyu,Gou Feicui,et al. Study on lake and reservoir landscape ecological design method based on numerical simulation-taking the application of MIKE21 model in the planning of Daguantang reservoir as the example［J].Chinese Landscape Architecture,2018 (3):123-128.]

[22]Nash IE,Sutcliffe I V.River flow forecasting through conceptual models part I:a discussion of principles[J]. Journal of Hydrology,

1970,10(3) :282-290.

[23]He ZH,ParajkaJ,Tian FQ,et al.Estimating degree-day factors from MODIS for snowmelt runoff modeling[J].Hydrology and Earth System Sciences,2014,18(12） :4773-4789.   
[24］金相灿，胡小贞.湖泊流域清水产流机制修复方法及其修复策 略[J].中国环境科学,2010,30（3）:374-379.［Jin Xiangcan, Hu Xiaozhen.Concept and tactic of clean water runoff generation mechanism restoration in lake watershed[J].China Environmental Science 2010,30(3):374-379.]

# Study on the project of reducing organic pollutants in the Bosten Lake

HU Chun-ming'， Narengerile²， MA Jin-feng'， QING Jin'， YOU Li'(1.Research Center for Eco-Environmental Sciences,Chinese Academy of Sciences,Beijing 1Ooo85,China;2.InstituteofLake Bosten,BayingolinMongolia Autonomous Prefectureof Xinjiang,Korle841,Xinjiang,China)

Abstract：The contiguous river estuary and outfallinfluence the discharge of organic polutants,which limit he concentration and spatial distribution of the organic pollutants inthe Bosten Lake.Various projects should be conducted to optimize the current hydrological conditions.The MIKE21 software was applied to establish a two-dimensional numerical model and analyze the effcts of diferent intervention projects.According tothe simulation results and the paired sample $T$ -test results,the annual chemical oxygen demand concentration in the Bosten Lake could be reduced by $1 3 . 4 \%$ by moving the outfall from the southwest to the southeast, $8 . 9 1 \%$ by diverting $3 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ （204 of the runoff from the Kaidu River to the Huangshuigou River,and $2 0 . 2 \%$ by implementing both these projects.The results denote that it is feasible to reduce the organic pollutants inthe Bosten Lake byoptimizing the hydrological conditions.However,these projects only changed the proportion of the organic polltants inthe Bosten Lake,they did not reduce the quantityof organic polutants in the basin.The organic pollutants were diverted into the Kongque River downstream.

Key words:Bosten Lake；organic pollutants；MIKE21；chemical oxygen demand; hydrological condition