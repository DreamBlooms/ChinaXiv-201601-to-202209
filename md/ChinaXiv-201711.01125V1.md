# 大气折射对射电望远镜高精度指向的影响

肖明1,²，王 娜1，刘志勇1(1.中国科学院新疆天文台，新疆 乌鲁木齐830011；2.中国科学院大学，北京100049)

摘要：针对中性大气的物理属性以及大气折射对射电望远镜指向的影响进行了模型分析和计算，以改进型的“三段式”标准指向改正模型为基础，着重研究了由大气折射造成高阶指向误差的改正方案，目的是不断提高射电望远镜的指向精度，尤其针对大口径、高分辨率的射电望远镜。在此模型的基础上，模拟南山观测基地的气候特征，给出合理的计算结果。通过分析和评估这些结果与射电望远镜指向精度的要求，为将来大口径射电望远镜的指向修正提供参考。

关键词：大气折射；射电望远镜；指向误差；指向修正中图分类号： $\mathrm { P } 4 2 2 . 3 \AA ^ { + } . 2$ 文献标识码：A 文章编号：1672-7673(2016)01-0044-08

灵敏度和分辨率是衡量射电望远镜工作性能的两个重要指标，其中，分辨率与射电望远镜的口径成正比，望远镜的口径越大，分辨率越高。望远镜的分辨率与其指向精度的要求是一致的。影响射电望远镜指向精度的因素主要有两大类：第一类是随机因素(时变的)，比如风载荷和温度载荷等。第二类是非随机因素(非时变的)，比如重力载荷和天线结构设计误差等。造成射电望远镜指向误差的因素很复杂，而且一般都是单独考虑由大气折射造成的望远镜指向偏差，即基于改进型的“三段式”指向改正模型，然后通过软件编程拟合到望远镜的伺服控制系统中。改进型的“三段式”标准指向改正模型是指射电望远镜工作在不同俯仰角下，其观测视线方向上对应的大气厚度是不同的，习惯上根据俯仰角的不同划分为3个区域。由于大气折射对射电望远镜指向精度的影响在大尺度上具有非时变的特性，小尺度上又具有时变的特性，因此一般将大气折射的影响因素单独考虑[1]。本文在合理假设新疆天文台周围气候环境的基础上，针对地球大气的折射特性及其对射电望远镜高精度指向修正的影响进行了研究，在实践中不断提高大口径射电望远镜的指向精度。

# 1中性大气物理属性及大气折射的物理机制

地球周围包裹着一层中性大气。习惯上根据不同的物理属性划分为4层：第1层为对流层，在低纬度地区的范围从海平面到海拔高度 $1 5 \sim 2 0 ~ \mathrm { k m }$ ；第2层为同温层，范围从对流层以上至海拔高度63$\sim 7 3 \ \mathrm { k m }$ ；第3层为中间层，上限为海拔高度 $8 0 ~ \mathrm { k m }$ ；第4层为热电离层，范围从中间层上限 $8 0 ~ \mathrm { k m }$ 至海拔高度 $3 2 0 { \sim } 6 0 0 ~ \mathrm { k m }$ 。在射电波段，由于大气折射作用造成射电望远镜指向误差的主要来源是第1层大气，即对流层的影响。

由于中性分子结构中原子之间存在振动作用，这种振动在宏观上产生两种效果：大气吸收和大气折射。假设一束沿 $y$ 轴正向传播的平面电磁波具有如下的数学表达式：

$$
E ( \boldsymbol { y } , \ t ) = E _ { 0 } e ^ { i ( k n y - 2 \pi \nu t ) } .
$$

其中， $n$ 具有复数形式，即 $n = n _ { \mathrm { R } } ^ { \mathrm { \Lambda } } { + } i n _ { \mathrm { I } } ^ { \mathrm { \Lambda } }$ 。大气的吸收作用对应虚部，大气的折射作用对应实部。设大气成分产生的折射频率为 $\boldsymbol { f } _ { \mathrm { r e f } }$ ，折射作用对低于这个频率范围有贡献，而高于这个频率范围没有贡献，其中水汽组分和氧气组分是决定射电波段大气折射率的主要因素[2]：水汽组分的折射频率大致在近红外波段，氧气组分的折射频率大致 $6 0 ~ \mathrm { G H z }$ 。因此水汽组分对低于红外波段频率的范围有贡献，而氧气组分对低于 $6 0 \ : \mathrm { G H z }$ 的频率范围有贡献。因为水汽和氧气组分主要存在于地球大气的对流层，因而大气的折射作用主要集中在此范围。大气的折射效果与射电望远镜在不同俯仰角时视线方向上大气的有效厚度相关，因此，一般采用改进型的“三段式”标准指向修正模型。

# 2大气折射修正

首先，给出射电望远镜的场强方向图分布的精确计算公式：

$$
f ( \theta , \ \phi ) = 2 \biggl ( \frac { \pi D ^ { 2 } } { 4 } \biggr ) \biggl [ \frac { J _ { 1 } ( u ) } { u } \biggr ] ,
$$

$$
u = \left( \frac { k D } { 2 } \right) \sin \theta \ ,
$$

其中， $f ( \theta , \phi )$ 表示电场场强矢量的方向分布图； $\theta$ 表示射电望远镜场强分布方向图中任一点相对于极轴方向的偏移角； $J _ { 1 }$ 是一阶贝塞尔函数； $D$ 表示望远镜的口径； $k$ 表示电磁波的波数。若只考虑场强方向图的分布属性，可以忽略其中面积常数项和变量 $\phi$ ，因为变量 $\phi$ 与相对于方向图的极轴方向成轴对称关系。因此，（2)式可写为如下形式：

$$
f ( \theta ) = \frac { J _ { 1 } ( u ) } { u } = \frac { - 1 } { T ( 3 ) } \left( \frac { u ^ { 2 } } { 8 } \right) ,
$$

其中， $\boldsymbol { { \cal { T } } } ( \boldsymbol { x } )$ 表示伽玛函数。一般定义射电望远镜的指向精度为：当接收功率降为最大接收功率的$90 \%$ 时对应的偏移角的大小。在此范围内计算射电望远镜指向精度的近似公式为（弧度)：

$$
\Delta \theta = \frac { 1 . 0 2 } { 1 0 } \left( \frac { \lambda } { D } \right) .
$$

假设射电望远镜的观测频率 $3 0 ~ \mathrm { G H z }$ ，对于 $2 5 \mathrm { ~ m ~ }$ 射电望远镜，则指向精度要求 $9 . 5 { \mathrm { ~ a r c s } }$ ，而对于$1 1 0 \mathrm { m }$ 射电望远镜，指向精度要求提高到 $2 . 0 \ \mathrm { a r c s }$ 。

近似假设地球大气层是由相互平行的平面组成，那么大气折射角的计算将变得十分简单：

$$
\Delta z = \left( n _ { 0 } - 1 \right) \mathrm { t a n } z _ { 0 } \ ,
$$

其中， $\Delta z$ 表示折射角（单位：rad）； $z _ { 0 }$ 表示望远镜天顶距； $n _ { 0 }$ 表示地球表面处的大气折射率（单位：ppm）。(6)式是一个近似公式，当望远镜的俯仰角在 $\left[ 9 0 ^ { \circ } , 2 5 ^ { \circ } \right. .$ ]范围内，得到的结果与实际情况吻合很好。但是，当望远镜的俯仰角在 $2 5 ^ { \circ }$ 及以下时，就必须考虑地球大气层的圆弧效应。完整的计算球面大气层折射角的公式[3]：

$$
\Delta z = r _ { 0 } n _ { 0 } \mathrm { s i n } z _ { 0 } \int _ { 1 } ^ { n _ { 0 } } \frac { \mathrm { d } n } { n \sqrt { r ^ { 2 } n ^ { 2 } - r _ { 0 } ^ { 2 } n _ { 0 } ^ { 2 } \mathrm { s i n } ^ { 2 } z _ { 0 } } } ~ ,
$$

其中， $r _ { 0 }$ 表示地心到地球表面的半径距离； $\boldsymbol { r }$ 表示从地心到大气层某一高度处的距离。在计算和应用时，直接求解非线性积分公式不方便，因此，需将此积分公式进行分段简化。当望远镜的俯仰角在$[ 2 5 ^ { \circ } , 1 0 ^ { \circ } ]$ 范围时，（7)式可以简化成：

$$
\Delta z \approx ( n _ { 0 } - 1 ) \left( 1 - \frac { H _ { 0 } } { r _ { 0 } } \right) \mathrm { t a n } z _ { 0 } - ( n _ { 0 } - 1 ) \left[ \frac { H _ { 0 } } { r _ { 0 } } - \frac { ( n _ { 0 } - 1 ) } { 2 } \right] \mathrm { t a n } ^ { 3 } z _ { 0 } + \delta ( \Delta z ) ,
$$

$$
H _ { 0 } = \left( { \frac { 1 } { \rho _ { \mathrm { 0 } } } } \right) \int _ { 0 } ^ { \infty } \rho \mathrm { d } h ,
$$

其中， $H _ { 0 }$ 表示与地面垂直方向上的大气层有效厚度； $\delta ( \Delta z )$ 表示由于不同的射电望远镜观测站所处地理位置海拔高度的不同造成的折射角残差修正值，即(8)式与(7)式的差值； $\rho$ 表示与海拔高度有关的大气密度值。表1给出了标准大气环境条件下，不同海拔高度的大气折射角残差修正参考值。在实际应用中，可以将大气属性分为干燥和潮湿两种情形[4」，分别对应大气层的有效厚度(单位：米)为

$$
\begin{array} { l } { { \left. H _ { 0 } \right| _ { \scriptstyle + \sqrt { 3 \atop | \sqrt [ ] { 3 } } } \approx 8 0 0 0 \left( \frac { T } { 2 7 3 . 1 5 } \right) , } } \\ { { \left. H _ { 0 } \right| _ { \scriptstyle \frac { | \sqrt [ ] { 3 } } { | \sqrt [ ] { 3 } | \sqrt { 6 } } } \approx 2 0 0 0 . } } \end{array}
$$

# 表1标准大气属性下不同海拔高度对应的大气折射角残差修正参考值(单位：角秒)

Table 1 The residual corrections of the refraction to the different altitude under the standard model（Unit：arcs）   

<html><body><table><tr><td rowspan="2">望远镜 俯仰角 /0</td><td colspan="5">天文台观测站的海拔高度/km</td><td rowspan="2">望远镜 俯仰角</td><td colspan="5">天文台观测站的海拔高度/km</td></tr><tr><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>/0</td><td>0</td><td>1</td><td>2</td><td>3 4</td></tr><tr><td>25</td><td>+0.02</td><td>+0.01</td><td>+0.01</td><td>+0.00</td><td>+0.00</td><td>17</td><td>+0.08</td><td>+0.07</td><td>+0.06</td><td>+0.05</td><td>+0.04</td></tr><tr><td>24</td><td>+0.02</td><td>+0.02</td><td>+0.01</td><td>+0.01</td><td>+0.00</td><td>16</td><td>+0.12</td><td>+0.10</td><td>+0.09</td><td>+0.08</td><td>+0.07</td></tr><tr><td>23</td><td>+0.02</td><td>+0.02</td><td>+0.02</td><td>+0.02</td><td>+0.01</td><td>15</td><td>+0.18</td><td>+0. 15</td><td>+0.12</td><td>+0.10</td><td>+0.08</td></tr><tr><td>22</td><td>+0.03</td><td>+0.03</td><td>+0.02</td><td>+0.02</td><td>+0.01</td><td>14</td><td>+0.25</td><td>+0.21</td><td>+0.19</td><td>+0.16</td><td>+0.14</td></tr><tr><td>21</td><td>+0.03</td><td>+0.03</td><td>+0.03</td><td>+0.02</td><td>+0.02</td><td>13</td><td>+0.35</td><td>+0.30</td><td>+0.26</td><td>+0.22</td><td>+0.19</td></tr><tr><td>20</td><td>+0.04</td><td>+0. 04</td><td>+0.04</td><td>+0.03</td><td>+0. 03</td><td>12</td><td>+0.50</td><td>+0.45</td><td>+0.40</td><td>+0.36</td><td>+0.32</td></tr><tr><td>19</td><td>+0.04</td><td>+0. 04</td><td>+0.03</td><td>+0.03</td><td>+0.03</td><td>11</td><td>+0. 74</td><td>+0. 65</td><td>+0.57</td><td>+0.51</td><td>+0.46</td></tr><tr><td>18</td><td>+0.06</td><td>+0.05</td><td>+0.04</td><td>+0.03</td><td>+0.03</td><td>10</td><td>+1. 19</td><td>+1.05</td><td>+0.91</td><td>+0.81</td><td>+0.73</td></tr></table></body></html>

若望远镜工作在接近极限的范围，如 $[  0 ^ { \circ } ,  5 ^ { \circ } ]$ 之间，此时美国绿岸射电望远镜（GreenBankTelescope，GBT)采用此改正方案，使用经验公式，在(8)式的基础上乘以因子 $1 + 0 . 0 0 1 2 \big ( 3 5 . 8 - z _ { 0 } \big )$ 。当射电望远镜工作在此俯仰角范围内时，大气折射的作用效果比较复杂，精确评估其折射角较为困难，参考美国绿岸射电望远镜采用的修正算法，快速算法与精确的迭代算法之间的差值可以控制在$1 . 5 "$ 以内①。

在上述模型中，获得大气折射角必须建立当地的大气折射模型，给出大气折射率的数值。大气折射率与周围的环境属性有关，可参照大气折射率的计算公式[5]：

$$
\left( n _ { 0 } - 1 \right) 1 0 ^ { 6 } = 7 7 . 6 8 9 0 { \frac { p _ { \mathrm { d } } } { T } } + 7 1 . 2 9 5 2 { \frac { e } { T } } + 3 7 5 4 6 3 { \frac { e } { T ^ { 2 } } } ,
$$

其中， $T$ 表示当地的温度值（单位：K)； $p _ { \mathrm { d } }$ 表示干燥大气环境的压强值（单位： $\mathrm { { h P a } }$ ）； $\boldsymbol { \mathscr { e } }$ 表示大气中水汽部分的压强值（单位： $\mathrm { { h P a } }$ )。由气象仪测出的气象参数是温度、大气压强、大气相对湿度。绝对湿度是指单位体积的潮湿空气中所含的水汽质量，也就是空气中的水汽密度，绝对湿度不容易直接测量，因此使用比较少。一般实际可测的参量是大气的相对湿度，大气相对湿度是指大气中的实际水汽压与同一温度下饱和水汽压的百分比，即相对湿度的大小表示空气接近饱和的程度，而其中的饱和水汽压值利用玛格努斯经验公式求得[6]：

$$
E = E _ { 0 } 1 0 ^ { \left( \frac { a t } { b + t } \right) } ,
$$

其中， $E$ 是指某一温度下饱和水汽压( $\left( \mathrm { { h P a } } \right)$ ； $\mathbf { \chi } _ { t } ^ { }$ 表示摄氏温度值（单位： $\mathrm { { ^ \circ C } }$ ）。标准水平面条件下，常数 $a = 7 . 5$ ， $b = 2 3 7 . 3$ ， $E _ { \mathrm { 0 } } { = } 6 . 1 1 \ \mathrm { h P a }$ 。在平均大气压环境下， $p _ { \mathrm { d } } { = } 1 ~ 0 1 3 ~ \mathrm { h P a }$ ， $T = 2 8 3 \textrm { K }$ ，且令相对湿度为 $8 \% ( e = 1 . 0 \mathrm { { h P a } ) }$ ，改进型的“三段式”改正模型与其它常用的蒙气差模型[7-8]之间的比较见表2。

表2不同改正模型在天顶距 ${ \bf 0 } ^ { \circ } \sim { \bf 8 5 } ^ { \circ }$ 之间的修正对比  
e 2The comparison of different models of the pointing corrections for the zenith distance from $\bullet ^ { \circ }$ to $\mathbf { 8 5 } ^ { \circ }$   

<html><body><table><tr><td>天顶距 /0</td><td>普尔 科沃 模型</td><td>《航海表》 列表 /arcs</td><td>中国天 文年历 列表</td><td>UNSW932 模型 /ares</td><td>三段式 折射 模型</td><td>天顶距 10</td><td>普尔 科沃 模型</td><td>《航海表》 列表 /arcs</td><td>中国天 文年历 列表</td><td>UNSW932 模型 /arcs</td><td>三段式 折射 模型</td></tr><tr><td>0</td><td>/arcs 0.0</td><td>0.0</td><td>/arcs 0.0</td><td>0.0</td><td>/arcs 0.0</td><td>70</td><td>/arcs 158.2</td><td>156.2</td><td>/arcs 157. 5</td><td>156.7</td><td>/arcs 159.7</td></tr><tr><td>10</td><td>10.3</td><td>10.7</td><td>10.3</td><td>10.1</td><td>10.3</td><td>75</td><td>213.4</td><td>213.5</td><td>212. 4</td><td>211.9</td><td>216.9</td></tr><tr><td>20</td><td>21. 7</td><td>20.8</td><td>21. 6</td><td>21.4</td><td>21.2</td><td>80</td><td>317. 2</td><td>319.3</td><td>316.8</td><td>318.3</td><td>327.6</td></tr><tr><td>30</td><td>33.5</td><td>33.4</td><td>33.4</td><td>33.1</td><td>33.6</td><td>81</td><td>349.9</td><td>352.7</td><td>349.9</td><td>352.7</td><td>349.8</td></tr><tr><td>40</td><td>48.7</td><td>48.2</td><td>48.5</td><td>48.1</td><td>48.8</td><td>82</td><td>389. 1</td><td>393.5</td><td>390. 5</td><td>394. 9</td><td>391. 1</td></tr><tr><td>50</td><td>69.1</td><td>68.2</td><td>68.8</td><td>68.2</td><td>69.3</td><td>83</td><td>436.8</td><td>444.0</td><td>441. 1</td><td>447. 8</td><td>450.9</td></tr><tr><td>60</td><td>100. 3</td><td>98.9</td><td>99.8</td><td>99.1</td><td>100. 8</td><td>84</td><td>494. 2</td><td>503.9</td><td>506.2</td><td>515.8</td><td>512.4</td></tr><tr><td>65</td><td>123. 9</td><td>121. 6</td><td>123. 3</td><td>122. 5</td><td>124. 6</td><td>85</td><td>563.5</td><td>590.3</td><td>594. 8</td><td>606. 4</td><td>600.1</td></tr></table></body></html>

总结上面的计算结果，将大气折射角的计算划分为三个范围：俯仰角分别在 ${ [ 9 0 ^ { \circ } }$ ， $2 5 ^ { \circ } ] [ 2 5 ^ { \circ }$ ${ 1 0 } ^ { \circ } ]$ 以及 $[ { 1 0 } ^ { \circ } , { 5 } ^ { \circ } ]$ 之间，即所谓的改进型“三段式”射电望远镜指向改正模型。在 ${ [ 9 0 ^ { \circ } }$ ， $2 5 ^ { \circ }$ ]范围内，(6)式的计算结果与《航海表》比较相差在 $1 . 2 ^ { \prime \prime }$ 以内；在 $[ 2 5 ^ { \circ } , 1 0 ^ { \circ } ]$ 范围内，(8)式的计算结果与《航海表》比较相差在 $3 . 0 ^ { \prime \prime }$ 以内；在 $[ { 1 0 } ^ { \circ } , { 5 } ^ { \circ } ]$ 之间，(8)式乘以因子 $1 + 0 . 0 0 1 2 ( 3 5 . 8 - z _ { 0 } )$ 后的计算结果与《航海表》相比，其偏差值在 $1 2 ^ { \prime \prime }$ 内。图1是天顶距在 $\left[ 0 ^ { \circ } , 8 5 ^ { \circ } \right] ^ { - }$ 范围内，“三段式”指向改正模型与《航海表》之间残差值的变化趋势：随着观测天顶距的增大，其差值呈递增趋势。

![](images/15d81fb12543c483e9254a64d04862099c289ff3ad800e0a434511cd723277c5.jpg)  
图1“三段式”改正模型与《航海表》列表之间的残差值

Fig.1The residual errors between the plane $\&$ spherical model and the exact value listed in the navigation table

针对南山 $2 5 \mathrm { m }$ 射电望远镜台址周围的环境条件，在海拔高度为 $2 1 0 0 \mathrm { m }$ 且气候干燥的环境下，比如$p _ { \mathrm { d } } = 1 ~ 0 1 3 . 2 5 ~ \mathrm { h P a }$ ，相对湿度 $2 0 \% ( e = 1 . 2 2 \mathrm { { h P a } ) }$ ， $T = 2 7 3 \textrm { K }$ 。根据(6)式，其折射角(单位：arcs）为

$$
\Delta z \approx 6 0 . 7 \mathrm { t a n } z _ { \mathrm { 0 } } .
$$

为了突出气候条件不同对大气折射角的影响，假设在海拔高度同样为 $2 ~ 1 0 0 \mathrm { ~ m ~ }$ 但气候潮湿的环境下，比如 $p _ { \mathrm { d } } = 1 ~ 0 1 3 . 2 5 ~ \mathrm { h P a }$ ，相对湿度 $8 0 \% \left( e = 4 . 8 9 \mathrm { { h P a } } \right)$ ， $T = 2 7 3 \textrm { K }$ 。由(6)式知，其折射角为

$$
\Delta z \approx 6 5 . 0 \mathrm { t a n } z _ { 0 } .
$$

比较可知，由于气候环境的变化，对应的大气折射角相差大约 $9 \%$ 。同一台址的气候条件随着时间的推移呈现周期性变化，说明进行气候实时监测和望远镜实时指向改正是必要的。表3列举了不同的环境温度和湿度条件下大气折射角的数值，着重对比了高温和低温条件下的显著差异，同时考虑射电望远镜工作在不同俯仰角下的情形：越低的俯仰角对应越大的大气折射角，其数值相差一个数量级。图2对比了不同大气湿度环境条件下望远镜的指向偏差，其中，令干燥条件下 $p _ { \mathrm { d } } { = } 1 ~ 0 1 3 ~ \mathrm { h P a }$ ，相对湿度为 $20 \%$ ，温度 $T = 2 7 3 \ : \mathrm { K }$ ；潮湿条件下 $p _ { \mathrm { d } } { = } 1 0 1 3 \mathrm { h P a }$ ，相对湿度为 $8 0 \%$ ，温度 $T = 2 7 3 \textrm { K }$ 。通过比较可以看出，潮湿的大气环境造成的射电望远镜指向偏差更加明显。图3对比了不同大气温度环境下望远镜的指向偏差，其中，高温环境对应 $T { = } 3 0 ~ \mathrm { ^ { \circ } C }$ 且相对湿度为 $20 \%$ ，低温环境对应 $T { = } - 3 0 ~ \mathrm { \textcircled { C } }$ 且相对湿度也为 $20 \%$ 。通过比较可以看出，环境温度越低，对望远镜指向偏差的影响越显著。

表3不同的大气温度和湿度造成的望远镜指向偏差(单位：角秒)  
Table 3The pointing errors due to some different atmospheric temperature and humidity（Unit : arcs）   

<html><body><table><tr><td>环境温度 /K</td><td colspan="2">P=1013hPa，相对湿度 20%</td><td colspan="2">P=1013hPa，相对湿度 80%</td><td>望远镜 俯仰角/°</td></tr><tr><td rowspan="3">303</td><td>10.7± 0.001</td><td rowspan="3">e=8.46 hPa</td><td>14.5 ± 0.001</td><td rowspan="3">e= 33.84 hPa</td><td>80</td></tr><tr><td>60.7 ± 0.05</td><td>82.0 ± 0.05</td><td>45</td></tr><tr><td>346.5 ± 0.1</td><td>470.7± 0.1</td><td>10</td></tr><tr><td rowspan="4">273</td><td>10.7 ± 0.001</td><td rowspan="4">e =1. 22 hPa</td><td>11.5 ± 0.001</td><td rowspan="4">e=4.89 hPa</td><td>80</td></tr><tr><td>60.7 ± 0.05</td><td>65.0 ± 0.05</td><td>45</td></tr><tr><td>346.2 ± 0.1</td><td>368.6± 0.1</td><td>10</td></tr><tr><td></td><td></td><td></td></tr><tr><td rowspan="2">243</td><td>11.7 ± 0.001</td><td rowspan="2">e=0.10 hPa</td><td>11.7 ± 0.001</td><td rowspan="2">e=0.40 hPa</td><td>80</td></tr><tr><td>67.0 ± 0.05 374.6 ± 0.1</td><td>67.4 ± 0.05 375.9 ± 0.1</td><td>45 10</td></tr></table></body></html>

![](images/e54702e01dc94db50dbe6637bd5a182e1d5b9a7e60a51df632f8a5eb4167b161.jpg)  
图2针对 $0 \%$ 干燥(相对湿度 $20 \%$ )和潮湿(相对湿度 $8 0 \%$ )环境下的大气折射角Fig.2The index of the refraction fora dry(relative humidity $20 \%$ ）or wet(relative humidity $80 \%$ ）atmosphere under $0 \%$ respectively

# 3指向改正的高阶修正方法

时变的大气因素对望远镜指向精度的影响，一般划分为两大类：第1类，在空间大尺度上随时间变化的大气因素；第2类，在空间小尺度上随时间变化的大气因素。下面分别讨论这两种不同因素的影响。

![](images/69085de8369a67cbcfe1f8b7f9144e8d9227c15ef701869fbbe19aed80714639.jpg)  
图3高温( $3 0 \ \%$ )和低温( $- 3 0 \mathrm { ~ \textdegree C }$ )环境下的大气折射角  
Fig.3The index of therefraction forthe highorlow temperature underthe standard pressureconditions respectively

首先，明确空间大尺度的时变环境。台址周边气候环境的实际情况往往是复杂的，其中，对望远镜指向造成较显著影响的是温度梯度在空间上的分布特性。比如水平方向上温度分布的不对称性，而这种不对称性一般由几种因素共同作用造成：海洋气候的变化；大型湖泊的蒸发降温作用；森林树木的蒸腾作用；早晚日照的不对称性。例如，南山 $2 5 \mathrm { ~ m ~ }$ 射电望远镜坐落在距离乌鲁木齐市以南 $6 0 ~ \mathrm { k m }$ ，海拔高度 $2 1 0 0 \mathrm { m }$ 的天山山脉上。观测站以北是城市居民区，以南是大部分时间覆盖积雪的天山山脉。这样的地理环境造成了温度梯度分布的南北纵向不对称性。理论上，这种由于温度梯度分布不对称造成的望远镜指向偏差可表示为[9]

$$
\delta ( \Delta z ) \approx - 0 . 2 1 \bigg ( \frac { H _ { 0 } } { 1 0 0 0 } - h \bigg ) \bigg ( \frac { \mathrm { d } T } { \mathrm { d } s } \bigg ) \bigg ( \tan ^ { 2 } z _ { 0 } + \frac { 1 } { 2 } \bigg ) ,
$$

其中，( $\mathrm { ‰ }$ 表示水平方向的温度梯度（单位： $\mathrm { { ^ \circ C } / \mathrm { { k m } } } ,$ ； $\boldsymbol { h }$ 表示射电望远镜所处的海拔高度（单位： $\mathrm { k m }$ ），如(10)式所示，分别表示干燥和潮湿条件下的大气层有效厚度。针对南山 $2 5 \mathrm { ~ m ~ }$ 射电望远镜所处的地理环境，假设南北方向温度梯度为 $- 0 . 1 6 ~ \mathrm { { ^ { \circ } C / k m } }$ 。同时，令望远镜的工作俯仰角为 ${ 1 0 } ^ { \circ }$ ，根据(15)式可得

$$
\begin{array} { r l } & { \delta ( \Delta z ) \mid _ { _ { \overrightarrow { \mathrm { i f f s R } } } } \approx 6 . 0 \mathrm { a r c s } , } \\ & { \delta ( \Delta z ) \mid _ { _ { \overrightarrow { \mathrm { F f s R } } } } \approx 0 . 0 6 \mathrm { a r c s } . } \end{array}
$$

比较(5)式的计算结果可知，由于温度梯度分布的不对称造成的望远镜指向偏差，在干燥的大气环境下可以忽略，而在潮湿的大气环境下需要加以考虑。

考虑另一种较为明显的大气波动情形，即空间小尺度上大气环境的不均匀性。其中，大气云层的不均匀性是一种常见现象。大气云层是水汽密度较大的区域，该区域对射电波传播的折射作用明显。所以，当大气云层掠过射电望远镜天线功率方向图的主瓣区域时，造成望远镜的指向偏差。因为大气云层受风等因素的影响，其密度和尺度是变化的，因此针对这种因素造成的望远镜指向偏差应进行实时改正。假设大气云层区域的视向厚度为 $1 0 0 \mathrm { ~ m ~ }$ ，且该区域的折射率梯度的跨度为5，则计算出望远镜视场方向上电磁波传播路径的光程差约为 $0 . 5 ~ \mathrm { m m }$ 。口径为 $D$ 的射电望远镜，由上述光程差导致的望远镜口径边缘相对于口径中心的指向偏差（单位： $\deg$ 为

$$
\Delta \alpha \approx \frac { 0 . 0 0 5 } { D } .
$$

对于 $2 5 \mathrm { ~ m ~ }$ 射电望远镜，指向偏差为 $1 2 . 0 \ \mathrm { a r c s }$ 。若望远镜的口径为 $1 1 0 \mathrm { m }$ ，则指向偏差为 $2 . 7 \ \mathrm { a r c s }$ 。可

以看出，由于大气云层不均匀造成的望远镜指向偏差的量级与望远镜指向精度的要求相当，不能忽略。该效应也已经被世界范围内的其它高分辨率亚毫米波射电望远镜阵探测到[10]。

# 4大气折射对望远镜口径效率的影响

地球大气尤其是对流层的作用，除了造成射电望远镜的指向偏差外，对望远镜的口径效率也会造成影响。即大口径射电望远镜的俯仰角在 ${ 1 0 } ^ { \circ }$ 以下时，望远镜的口径尺度效应不能忽略。所谓望远镜的口径尺度效应是指地球大气相对于口径中心点的折射角与其相对于口径上、下边沿的折射角不相等。这种效应使得射电望远镜在汇聚来自天体源的电磁波时产生散焦现象，降低了望远镜的口径效率。对于 $1 1 0 \mathrm { m }$ 射电望远镜，其口径尺度效应为

$$
\delta ( \Delta z ) = \left( \frac { D \mathrm { c o s } ( 9 0 - z _ { 0 } ) } { H _ { 0 } } \right) ( \Delta z ) .
$$

针对 $1 1 0 \mathrm { m }$ 射电望远镜，如果俯仰角为 $7 ^ { \circ }$ 时，根据(18)式计算得

$$
\delta ( \Delta z ) = \left[ \frac { D { \mathrm { c o s } } 7 ^ { \circ } } { H _ { 0 } } \right] ( \Delta z ) \approx \left( \frac { D } { H _ { 0 } } \right) ( \Delta z ) \approx 7 . 8 ~ \mathrm { a r c s } ~ .
$$

可以看出，大口径射电望远镜在低俯仰角时口径尺度效应的量级与其指向精度相当，所以这种效应也不能忽略。比较不同的口径尺度效应造成的射电望远镜散焦偏差见表4。原则上，这种由于口径尺度效应造成的望远镜散焦偏差可以通过调节主动面节点加以修正。

表4不同射电望远镜口径尺度效应造成的口径边缘散焦偏差(单位：角秒)  
Table 4The edge effects of the aperture for radio telescopes with different scales（Unit: arcs）   

<html><body><table><tr><td rowspan="2"></td><td colspan="8">射电望远镜口径/m</td><td rowspan="2">大气条件</td></tr><tr><td>20</td><td>30</td><td>40</td><td>50</td><td>70</td><td>80</td><td>100</td><td>110</td></tr><tr><td>口径边缘</td><td>5.6</td><td>8.4</td><td>11.2</td><td>14.0</td><td>19. 6</td><td>22.8</td><td>28.4</td><td>31.2</td><td>潮湿</td></tr><tr><td>散焦偏差</td><td>1.4</td><td>2.1</td><td>2.8</td><td>3.5</td><td>4.9</td><td>5.7</td><td>7.1</td><td>7.8</td><td>干燥</td></tr></table></body></html>

# 5结论

改进型的“三段式”指向改正模型是一种高精度算法。一般情况下，可以不考虑地球大气在较短时间内的时变特性。然而对于大口径射电望远镜而言，指向精度的要求更高。某些短周期时变的大气特性，往往会在大口径望远镜以及高频段的亚毫米波射电阵的实测中突显，并对天文观测和指向偏差改正造成不可忽略的影响。同时，针对这些具有时变性质的大气特性，要对天文台附近的气候状况进行实时监测和指向改正，这样对各天文台配套的气候监测设备和系统提出了更高的要求。

本文一方面从理论上给出不同条件下影响射电望远镜指向偏差的量化结果，对于不断提高射电望远镜的指向精度具有重要的实践意义。具体实现根据理论计算结果并通过优化望远镜控制软件中相关的指向参数完成。分析表明，由大气折射造成的望远镜指向偏差对周围环境的湿度敏感，多数地面射电望远镜台址的气候环境不会常年干燥，而且潮湿的环境条件会明显地增加望远镜的指向偏差，因此，需要针对台址周围气候环境的变化情况设计不同的指向修正模型参数，并拟合到射电望远镜的控制软件中。另一方面，导致射电望远镜指向偏差的诸多效应是交叉相关的，采取的处理手段和改善方法也不尽相同：如果某因素造成射电望远镜指向偏差明显，需要对望远镜的指向模型参数进行修正;如果对望远镜的口径效率造成显著影响，则需要采取调整主动面节点的方法以修正望远镜口径面型。

# 参考文献：

[1] 李维华，胡汉明，陈国强，等.毫米波射电天文观测站选址报告［J］.云南天文台台刊，1987(2) : 90-98.Li Weihua，Hu Hanming，Chen Guoqiang，et al.Report of site selection for a milimeter waveradio astronomical station ［J]. Publications of the Yunnan Observatoty，1987(2）: 91-98.  
[2] Thompson A R，Moran J M，Swenson G W. Interferometry and synthesis in radio astronomy[M].2nd ed.New York:Wiley，2001.  
[3] Smart W M,Green R M. Textbook on spherical astronomy [M].6th ed.UK:Cambridge UniversityPress， 1977.  
[4] Cox A N.Allen's astrophysical quantities [M].4th ed.New York: Springer Verlag，2002: 256-260.  
[5] Smith E K，Weintraub S.The constants in the equation for atmospheric refractive index at radiofrequencies[J].Proceedings of the IRE，1953，41（8）：1035-1037.  
[6] Rueger JM. Electronic distance measurement [M]. New York:Springer Verlag，1996.  
[7] 苏超，王安国，谷树文，等.天文定位中的蒙气差修正方法研究［J].导航，2007(4)：37-41.Su Chao，Wang Anguo,Gu Shuwen，et al. Simple method of atmospheric refraction in astronomicalposition [J]. Navigation，2007(4）:37-41.  
[8] 王锋.天文实测蒙气差的研究[J].云南天文台台刊，1997(1)：97-98.Wang Feng.Research on the actual measurement of atmospheric refraction ［J].Publications ofthe Yunnan Observatoty，1997(1） :97-98.  
[9] Saastamoinen J. Introduction to practical computation of astronomical refraction ［J].BulletinGéodesique，1972，106(1) :383-397.  
[10] Baars J W M.The paraboloidal reflector antenna in radio astronomy and communication [M].New York:Springer Verlag，2007.

# Atmospheric Refractions and Radio Telescope Pointing Corrections

Xiao Ming $^ { 1 , 2 }$ ， Wang Na $^ { 1 }$ ， Liu Zhiyong1 (1.Xinjiang Astronomical Observatory，ChineseAcademyof Siences，Urumqi830ol1,China,Email: xiaoming@xao.ac.cn; 2.University of Chinese Academy of Sciences，Beijing 1Ooo49，China)

Abstract:In this article we discuss the efects of the atmospheric refraction，particularly，the method of accurate corrections to the pointing error of radio telescopes.The position of the telescope beam is somewhat diffrent from the beam positionas indicatedbythe encoders，which is due to the structural deformations caused by the wind，gravity，temperature，and the atmospheric distortion.Accurate refractive corrctions which depend on astronomical pointing measurements are required by observations using large aperture radio telescopes，especiallyat higher frequency bands.Thisarticle presents the advanced model for atmospheric refraction corrections and shows the improvements comparedto traditional methods，particularly at low elevations.Inaddition，thereal-time refraction corrections，in which the higher-orderrefraction corections of telescope pointing errors are involved,for example,the effect of the uneven temperature distribution overa wide scale range，or the diferential refraction across a large aperture telescopes，are also analyzed in this article.

Key Words: Atmospheric refraction；Radio Telescope；Pointing error；Pointing correction