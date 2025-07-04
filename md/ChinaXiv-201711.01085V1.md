# 天文定姿中太阳系内天体视位置计算

连月勇1，张超，詹银虎1，谢宗特(1.信息工程大学，河南 郑州 450001；2.75711部队，广东广州 510000)

摘要：天体视位置是进行天文定姿的必备数据，目前视位置计算的研究多基于地面和海上，天基平台的发展需进一步研究。介绍了星上视位置转换原理，推导各种位置改正公式，基于新天文参考框架建立一种太阳系内天体视位置计算模型，可计算任意时刻天体的地心视位置和站心视位置。与天文年历地心视位置相比，类木行星的赤经差值在 $1 0 ~ \mathrm { { m s } }$ 以内，赤纬差值在220mas以内；与STK仿真的站心视位置相比，赤经差值在0.15s以内，赤纬差值在 $2 ^ { \prime \prime }$ 以内。实验表明，该模型可以正确计算测瞬太阳系内天体的视位置，其精度满足天文定姿的需求。

关键词：视位置计算；天文定姿；天文年历；STK中图分类号：P128.4 文献标识码：A 文章编号：1672-7673(2016)02-0178-06

星敏感器利用天体视位置和星空图像矢量信息进行天文定姿。天文定姿利用恒星、日月以及行星等自然天体作为导航信标，确定航天器在轨道坐标系中的三轴姿态，天文定姿包括初始模式和跟踪模式两种方式[1]。首先，星敏感器对视场内天体成像，经过星图处理和星点提取等技术得到天体的图像矢量信息，对星图上的星点数据进行星图匹配，识别天球坐标系中对应的天体，将这些天体的位置归算到观测历元下测站对应的视位置，天体视位置和天体的图像矢量信息可以确定航天器姿态矩阵，解算航天器三轴姿态信息。因此，天体视位置是天文定姿的必备数据，为提高定姿精度，确保天文定姿的实时性要求，需对恒星以及太阳系内天体的实时视位置计算进行研究。

目前为止，国内外关于天体视位置计算的研究主要应用于地基和海基观测。文[2]基于DE405 历表数据，采用天文矢量处理方法，提出了一种高精度行星视位置计算的数学模型，主要运用于舰船平台。文[3]归纳并建立了常数变易法和坐标摄动法两种计算行星视位置的方法，在船舶天文导航系统中使用。文[4-5]介绍了基于地面观测的新型天文测量系统中行星视位置的计算方法。文[6]通过理论分析得出一种行星视位置长时段更新算法，但未考虑载体运动产生的影响。文「7-8]对恒星视位置的计算做了相关研究，对于太阳系内天体视位置的计算有一定的参考作用。

天文定姿时星敏感器位于高速运动的航天器上，与地基海基的运用情况最大的差别就是测站本身产生的光行差量级较大，不可忽略(实验结果显示影响达角秒量级)。本文研究了新天文参考框架下天文定姿时太阳系内天体视位置计算，并建立了一种实用解算模型。与2011年、2013年、2014 年和2015年的天文年历上天体视位置进行比对，验证地心视位置计算的精确度，利用STK仿真软件模拟卫星的在轨运行，通过得到的位置和速度信息计算天体的序列站心视位置，与STK中的太阳系内天体视位置数据比对分析站心视位置计算的准确度。

# 1太阳系内天体视位置转换

# 1.1 新天文参考框架

新天文参考框架规定了新的坐标系和岁差章动模型，天体视位置计算需做相应的改变。国际天文协会（Intemational Astronomical Union，IAU）1991年引人以广义相对论为基础的国际天球参考系（International Celestial Reference System，ICRS），定义了两套运动学无旋转时空坐标系太阳系质心天球参考系（Barycentric Celestial Reference System，BCRS）和地心天球参考系（Geocentric Celestial ReferenceSystem，GCRS）。2003年开始采用新的运动瞬时参考框架，该框架同动力学参考架没有关系，由新的岁差章动模型确定。IAU2000 岁差章动模型描述了天体中间极（Celestial Intermediate Pole，CIP)在地心天球参考系中的运动[9-10]

(1)P03岁差模型

天文学中采用过几种岁差模型，1986年以前一直使用纽康岁差系统，1986年后开始采用IAU1976岁差模型，2000 年后采用IAU2000 岁差模型，2006年的国际天文协会大会决定2009年1月1日之后采用最新的P03 模型。P03 模型的岁差量如(1)式

$$
\psi _ { \mathrm { \scriptscriptstyle ~ A } } = 5 0 3 8 . 4 8 1 5 0 7 ^ { \prime \prime } T - 1 . 0 7 9 0 0 6 ^ { \prime \prime } T ^ { 2 } - 0 . 0 0 1 1 4 6 4 5 ^ { \prime \prime } T ^ { 3 } + 0 . 0 0 0 1 3 2 8 5 1 ^ { \prime \prime } T ^ { 4 } - 9 . 5 1 ^ { \prime \prime } \times 1 0 ^ { - 8 } T ^ { 5 }
$$

$$
\omega _ { \mathrm { { A } } } = 8 4 3 8 1 . 4 0 6 0 0 0 ^ { \prime \prime } - 0 . 0 2 5 7 5 4 ^ { \prime \prime } T + 0 . 0 5 1 2 6 6 3 ^ { \prime \prime } T ^ { 2 } - 0 . 0 0 7 7 2 5 0 3 ^ { \prime \prime } T ^ { 3 }
$$

$$
- \ 4 . 6 7 ^ { \prime \prime } \times 1 0 ^ { - 7 } T ^ { 4 } \ - \ 3 . 3 3 7 ^ { \prime \prime } \times 1 0 ^ { - 7 } T ^ { 5 }
$$

$$
\varepsilon _ { \mathrm { _ A } } = 8 4 3 8 1 . 4 0 6 0 0 0 ^ { \prime \prime } - 4 6 . 8 3 6 7 6 9 ^ { \prime \prime } T - 0 . 0 0 0 1 8 3 1 ^ { \prime \prime } T ^ { 2 } + 0 . 0 0 2 0 0 3 4 0 ^ { \prime \prime } T ^ { 3 }
$$

$$
- 5 . 7 6 ^ { \prime \prime } \times 1 0 ^ { - 7 } T ^ { 4 } - 4 . 3 4 ^ { \prime \prime } \times 1 0 ^ { - 8 } T ^ { 5 }
$$

$$
\begin{array} { r } { \chi _ { \scriptscriptstyle \mathrm { A } } = 1 0 . 5 5 6 4 0 3 ^ { \prime \prime } T - 2 . 3 8 1 4 2 9 ^ { \prime \prime } T ^ { 2 } - 0 . 0 0 1 2 1 1 9 7 ^ { \prime \prime } T ^ { 3 } + 0 . 0 0 0 1 7 0 6 6 3 ^ { \prime \prime } T ^ { 4 } - 5 . 6 0 ^ { \prime \prime } \times 1 0 ^ { - 8 } T ^ { 5 } } \end{array}
$$

式中， $T$ 为距离历元J2000.0的儒略世纪数。

(2)IAU2000章动模型

1984 年章动的计算采用IAU1980 章动理论，2005年正式采用IAU2000 章动模型。其中，IAU2000 章动模型分为2000A和2000B模型，A模型精度最高，优于 $0 . 2 \mathrm { m a s }$ ，它包含了678个日月项和687个行星项，总共1365项，数量上是过去模型的十多倍。为了简化计算，提高解算效率，减少计算时间，对A模型进行了简化，取其中的78项组成模型B，它的精度在1995-2050 年之间可以保持在 $1 \mathrm { m a s }$ 。

$$
\left\{ \begin{array} { l } { { \Delta \psi = \displaystyle \sum _ { i = 1 } ^ { 6 7 8 } \left( A _ { i } + A _ { i } ^ { \prime } T \right) \mathrm { s i n } f _ { i } + \left( A _ { i } ^ { \prime \prime } + A _ { i } ^ { \prime \prime \prime } T \right) \mathrm { c o s } f _ { i } } } \\ { { \qquad \mathrm { , } } } \\ { { \Delta \varepsilon = \displaystyle \sum _ { i = 1 } ^ { 6 7 8 } \left( B _ { i } + B _ { i } ^ { \prime } T \right) \mathrm { c o s } f _ { i } + \left( B _ { i } ^ { \prime \prime } + B _ { i } ^ { \prime \prime \prime } T \right) \mathrm { s i n } f _ { i } } } \end{array} \right. ,
$$

式中各参数详细见文[11]。

# 1.2视位置转换

DE/LE历表里包含了太阳系内所有天体的基本信息，天文定姿时太阳系内天体的测瞬站心视位置计算需要充分考虑各种因素的影响。（1)天体的自行（propermotion）：从岁首历元时刻到测瞬时刻时间长度的天体自行，一般投影到星空中自行的影响小于1("/年)；（2)视差(parallax）：两个不同地点看到的物体的视方向之差，视差通常用来换算天体之间的距离，它的量级小于 $1 ^ { \prime \prime }$ (3)光行差(aberration）：由观测者与观测对象之间的相对运动和光速有限引起的位置视觉差异，在地面进行天体的观测时光行差的影响可以达到$2 1 ^ { \prime \prime }$ ，而航天器在轨道上的运行速度对视位置的计算影响更大，是研究航天器上恒星视位置计算与地面观测之间的主要差别；(4)还有光引力偏折、岁差和章动等。图1给出了天文定姿中天体各种位置之间的转换关系。

![](images/b4195adda1d839d47c51c430a32e93c231fc779018e099db6aa8d489679c94d1.jpg)  
图1各种视位置关系  
Fig.1Relationship between various apparent positions

# 2 视位置计算模型

同恒星的视位置计算相比，太阳系内天体的视位置计算最大的区别在于需要考虑由光行差引起的位置影响。因为测站同被观测天体距离近，相对运动速度大，故需要考虑周日视差和周日光行差改正。具体计算步骤如下：

(1)计算观测瞬间的地球时 $T T$ 对应的儒略日 $J$ 和TDB时间

鉴于早期使用的历书时存在不连续和不一致等问题以及原子频标技术的高速发展，1976年起采用力学时以广义相对论作为时间工作的理论基础。目前采用两种力学时，太阳系质心参考系用质心力学时TDB，地心视位置的解算用地球时 $\mathit { T T }$ 。TT是建立在国际原子时TAI的基础上，两者关系如式：

$$
T T = T A I + 3 2 ^ { \circ } . 1 8 4 = U T C + L S + 3 2 ^ { \circ } . 1 8 4 { \mathrm { , } }
$$

$L S$ 为跳秒，可根据IERS上面发布的公报B参数数据确定跳秒的值。

(2)通过DE/LE 历表内插得到 J2000 历元下太阳系内各天体质心的位置矢量 $\pmb { r } _ { p } ( T )$ 和地球在TDB时刻对应的质心天球参考系中的质心位置 $\pmb { r } _ { e }$ 和速度 $\pmb { \nu } _ { e }$ ， $\pmb { \nu } _ { e }$ 是地球绕太阳的公转速度，单位为AU／日。

(3)计算航天器TT时刻在真赤道真春分点坐标体系下相对于地心的位置 $\pmb { r } _ { c }$ 和速度 $\pmb { \nu } _ { c }$ ， $\pmb { r } _ { c }$ 以 $\mathrm { k m }$ 为单位， $\pmb { \nu } _ { c }$ 以 $\mathrm { k m / s }$ 为单位，从而得到航天器在质心天球参考系中的位置 $\boldsymbol { r } _ { o }$ 和速度 $\boldsymbol { \nu } _ { \flat }$ ：

$$
\pmb { r } _ { o } = \pmb { r } _ { e } + \pmb { r } _ { c }
$$

$$
\pmb { \nu } _ { o } = \pmb { \nu } _ { e } + \pmb { \nu } _ { e } .
$$

（4)计算太阳系天体的光行时。光行时的近似值 $\tau$ 为

$$
\tau = \big | r _ { p } ( T ) - r _ { \mathrm { { o } } } \big | / \mathrm { c } .
$$

根据 DE405历表获取 $T { - } \tau$ 时太阳系内天体的质心位置矢量 $r _ { p } ( T - \tau )$ ，则光行时改进值为

$$
\tau ^ { \prime } = \vert r _ { _ { p } } ( T - \tau ) - r _ { _ { o } } \vert / \mathrm { c } .
$$

依此循环迭代，直到光行时满足精度要求。

(5)计算 $T { - } \tau$ 时太阳系内天体相对于 $T$ 时航天器的坐标方向的单位矢量 $P$

$$
P = \frac { { r _ { p } ( { T - \tau } ) \ ^ { - } } { r _ { o } } } { \rho } ,
$$

$$
\rho = \big | r _ { { \scriptscriptstyle p } } ( T - \tau ) - r _ { { \scriptscriptstyle o } } \big | .
$$

(6)进行光线引力弯曲改正、周年光行差改正、岁差和章动改正：

$$
\boldsymbol { P } _ { 1 } = \boldsymbol { P } + \frac { 2 G M } { c ^ { 2 } \left[ \boldsymbol { r } _ { o } { } ^ { 2 } - ( \boldsymbol { r } _ { o } \cdot \boldsymbol { P } ) { } ^ { 2 } \right] } \cdot ( \frac { \boldsymbol { r } _ { o } \cdot \boldsymbol { P } } { r _ { o } } + \frac { \boldsymbol { r } _ { o } - \boldsymbol { r } _ { p } } { \rho } ) \cdot \boldsymbol { P } \times ( \boldsymbol { P } \times \boldsymbol { r } _ { o } ) ,
$$

$$
P _ { \mathrm { \Lambda } } = P _ { \mathrm { \Lambda } } _ { 1 } - \frac { 1 } { c } \big ( 1 - \frac { \boldsymbol { P } \cdot \boldsymbol { V } _ { e } } { c } \big ) \cdot \boldsymbol { P } \times \left( \boldsymbol { P } \times \boldsymbol { V } _ { e } \right) + \frac { 1 } { 2 c ^ { 2 } } \boldsymbol { V } _ { e } \times \left( \boldsymbol { P } \times \boldsymbol { V } _ { e } \right) ,
$$

$$
P _ { _ 3 } = N \cdot P \cdot P _ { _ 2 } .
$$

(7)将位置矢量转换为球面坐标：

$$
\begin{array} { l } { { \alpha _ { 1 } = \tan ^ { - 1 } ( y _ { 3 } / x _ { 3 } ) \ : , } } \\ { { \delta _ { 1 } = \tan ^ { - 1 } ( z _ { 3 } / \sqrt { x _ { 3 } ^ { 2 } + y _ { 3 } ^ { 2 } } ) . } } \end{array}
$$

(8)加入周日视差改正：

$$
\alpha _ { 2 } = \alpha _ { 1 } - P _ { 0 } \mathrm { c o s } \varphi \mathrm { s e c } \delta \mathrm { s i n } t ,
$$

$$
\delta _ { 2 } = \delta _ { 1 } - \mathrm { s i n } \varphi \mathrm { c o s } \delta _ { 1 } + \mathrm { c o s } \varphi \mathrm { s i n } \delta _ { 1 } \mathrm { c o s } t + { \frac { 1 } { 2 } } \big ( \alpha _ { 2 } - \alpha _ { 1 } \big ) \mathrm { s i n } \delta _ { 1 } \mathrm { s i n } t .
$$

$P _ { 0 }$ 为行星的周日地平视差，可根据历表获取； $\varphi$ 为测站天文纬度； $\mathbf { \chi } _ { t }$ 为天体的时角。

(9)加入周日光行差改正：

$$
\begin{array} { l } { { \alpha = \alpha _ { _ 2 } - 0 ^ { \mathrm { s } } . 0 2 1 \mathrm { c o s } \varphi \mathrm { c o s } t \mathrm { s e c } \delta _ { 2 } , } } \\ { { \delta = \delta _ { _ 2 } - 0 ^ { \mathrm { ^ { \prime } } } . 3 2 \mathrm { c o s } \varphi \mathrm { s i n } \delta _ { _ 2 } \mathrm { s i n } t . } } \end{array}
$$

利用VS2010平台对太阳系内天体视位置计算进行了编译，历表采用美国喷气推进实验室提供的DE405 历表数据，岁差章动模型采用最新的IAU2000 岁差章动模型。天体视位置解算程序界面如图2。

在参数输入处输入测瞬历元信息、测站信息和对应的地球定向参数（Earth Orientation Parameter,EOP），选择对应的解算类型。 表1地心视位置计算差值

# 3实例计算和精度分析

# 3.1地心视位置计算

分别采用2011、2013、2014和2015年4个年份的天文年历验证程序的准确性，观测时间取每年的2月3日力学时0时，测站统一设置在地心处。限于篇幅，表1仅列出2014年的比对数据。

从表1可以看出，离航天器越远的行星，计算的精度越高，而太阳、水星、金星和火星等这些在内行星范围内的类地行星其计算精度比较低，且离航天器位置越近精度越低，类地行星的

Table1The difference value of geocentric apparent position   

<html><body><table><tr><td>天体名称</td><td>赤经差值/s</td><td>赤纬差值/"</td></tr><tr><td>Mercury</td><td>-0. 100 4</td><td>-1. 331 2</td></tr><tr><td>Venus</td><td>-0.021 7</td><td>0. 099 0</td></tr><tr><td>Mars</td><td>-0.050 0</td><td>0. 257 8</td></tr><tr><td>Jupiter</td><td>0. 0158</td><td>-0.045 3</td></tr><tr><td> Saturn</td><td>-0. 003 4</td><td>0. 048 9</td></tr><tr><td>Uranus</td><td>-0.012 3</td><td>-0.130 1</td></tr><tr><td>Neptune</td><td>-0.001 7</td><td>-0. 056 3</td></tr><tr><td>Sun</td><td>-0. 193 2</td><td>-0. 7878</td></tr></table></body></html>

赤经误差在0.35s以内，赤纬误差在 $2 ^ { \prime \prime }$ 以内。类木行星的赤经误差在 $1 0 ~ \mathrm { { m s } }$ 以内，赤纬误差在 $2 2 0 ~ \mathrm { { m a s } }$ 以内。图3给出了4年计算结果同天文年历比对的差值，天体序列顺序同表1。

![](images/5e0a8ef7c948239929d4db0a8e12c64752b8a27c11b07888bf0dc12246ade4c2.jpg)  
图2视位置解算界面

![](images/ca17fc8354ad85676b9e7c7db5e020a42596484dc0e7e9f689c6d13c7f2209c7.jpg)  
Fig.2The interface of apparent position calculation   
图3地心视位置解算差值  
Fig.3The difference value of geocentric apparent position

# 3.2站心视位置计算

利用STK卫星轨道仿真软件，创建一颗 $6 0 0 \mathrm { k m }$ 高度的人造卫星，考虑J2摄动确定定轨数据，轨道倾角 $i = \mathrm { 6 0 . 0 7 4 d e g }$ ，升交点赤经 $\Omega { = } 2 9 8 . 0 7 4 ~ \mathrm { d e g }$ ，偏心率设为0，卫星的姿态信息采用经典模式。模拟2015年2月7日到8日两天的轨道数据，时间间隔取 $5 \mathrm { m i n }$ 。通过STK仿真得到577组卫星的位

置和速度信息，代人天体视位置程序计算站心视位置。计算J2000坐标系下地球、月球和太阳的视位置，得到赤经赤纬差值如图4。

由图4可看出赤经赤纬差值较小，赤经差值在 $0 . 1 5 \mathrm { ~ s ~ }$ 以内，赤纬差值在 $2 ^ { \prime \prime }$ 以内，从侧面验证了站心视位置计算的正确性，STK所提供的视位置也不是最精确模型解算所得，因此该结果不能作为天体视位置计算程序的精度。表2给出了

表2站心视位置计算指标  
Table2The counting indicator of observer-fixed apparent position   

<html><body><table><tr><td>天体</td><td>△α 均值/s</td><td>△α 均方差/s</td><td>△8 均值/"</td><td>△8 均方差/"</td></tr><tr><td>Earth</td><td>-0.001 2</td><td>0.0709</td><td>-0.013 3</td><td>1. 013 4</td></tr><tr><td>Moon</td><td>0.032 5</td><td>0.068 7</td><td>-0.192 6</td><td>1. 023 4</td></tr><tr><td>Sun</td><td>0.0019</td><td>0.069 3</td><td>0.019 9</td><td>1.0577</td></tr></table></body></html>

地球、月球和太阳站心视位置解算的赤经赤纬均值和均方差，可以看出，地球的视位置计算精度最低，因为它距离航天器最近。太阳的赤经差值均值 $1 . 9 \mathrm { m s }$ ，赤纬均值 $1 9 . 9 \mathrm { m a s }$ ，在白天观星困难的情况下，太阳是最为稳定的信息源，高精度太阳视位置计算对天文定姿具有很好的帮助作用。

![](images/e5c99bd1d55f0feda46e24e7b7afcac54074ccdd4bd7fec474477874e2eb3697.jpg)  
图4站心视位置解算差值  
Fig.4The difference value of observer-fixed apparent position

# 4结论

本文研究了天文定姿时太阳系内天体视位置的计算方法，建立一种实用的视位置算法模型，该模型可以计算天体的地心视位置和站心视位置。与2011、2013、2014和2015年的天文年历比较发现，类地行星的赤经误差在0.35s以内，赤纬误差在 $2 ^ { \prime \prime }$ 以内，类木行星的赤经误差在 $1 0 ~ \mathrm { { m s } }$ 以内，赤纬误差在 $2 2 0 \mathrm { { m a s } }$ 以内，验证了地心视位置计算的准确性。利用STK仿真软件模拟在轨卫星两天的轨道数据，计算地球、月球和太阳的站心视位置，与 STK 得到的 J2000坐标系下的视位置对比，赤经差值在0.15s以内，赤纬差值在 $2 ^ { \prime \prime }$ 以内，太阳的赤经差值均值 $1 . 9 \mathrm { m s }$ ，赤纬均值 $1 9 . 9 \mathrm { m a s }$ ，验证了站心视位置计算的正确性。由于在天文单位中，赤经的使用单位是时秒，而赤纬单位是角秒，时秒与角秒之间相差15倍，若进行单位转换之后，可以看出视位置计算的赤经、赤纬误差大小的量级差不多。实验表明，该计算模型可以正确解算测瞬太阳系内天体的视位置，精度满足天文定姿的需求。

# 参考文献：

[1] 韩聪颖.小型天文卫星高精度姿态确定和控制技术研究［D]．西安：西北工业大学，2004.  
[2] 王安国，贾传荧，孙鹏.航用行星高精度视位置计算研究［J].中国航海，2005(1)：30-34.Wang Anguo，Jia Chuanying，Sun Peng.Research on precise apparent position calculation fornavigation using planeta [J]. Navigation of China，2OO5(1）:30-34.  
[3] 赵玉新，李磊，李刚.行星视位置计算方法及其在舰船天文导航系统中的设计实现［J].哈尔滨工程大学学报，2005，26(3)：335-339.Zhao Yuxin，Li Lei,Li Gang. Computation of apparent place of celestial bodies and design in thecelestial navigation system for ship[J]. Journal of Harbin Engineering University，2005，26(3):335-339.  
[4] 张超.基于电子经纬仪的天文测量系统及应用研究［D].郑州：解放军信息工程大学，2009.  
[5] 詹银虎，张超，华跃升，等.利用行星进行快速天文定向［J].测绘科学技术学报，2011，28(5): 338-341.Zhan Yinhu，Zhang Chao，Hua Yuesheng，et al. Research on fast astro-geodesic orientation byobserving planet [J]. Journal of Geomatics Science and Technology，2011， 28(5）: 338-341.  
[6] 王文武，孙枫，刘承香，等.太阳系天体视位置的长期计算法［J].哈尔滨工程大学学报，2000，21(5):18-23.Wang Wenwu，Sun Feng，Liu Chengxiang，et al. The algorithm continuously used to calculatethe apparent place of celestial body in the solar system [J]. Journal of Harbin EngineeringUniversity，2000，21(5）:18-23.  
[7] 林钦畅，陈玲强.快速计算白塞耳日数和恒星视位置［J].测绘学报，1997，26(3)：268-274.Lin Qinchang，Chen Lingqiang.Fast computation of besselian day number and the apparentposition of the stars [J]. Acta Geodaetica et Cartographica Sinica，1997,26(3）:268-274.  
[8] 王桂如，刘利强．一种恒星视位置的新算法［J]．应用科技，2006，33(2)：36-39.Wang Guiru，Liu Liqiang. A new algorithm of calculating the apparent place of fixed star [J].Applied Science and Technology，2006，33(2）:36-39.  
[9] 中国科学院紫金山天文台.2015年中国天文年历［M].北京：科学出版社，2015.  
[10] 刘佳成，朱紫.2000年以来国际天文学联合会（IAU）关于基本天文学的决议及其应用［J].天文学进展，2012，30(4）：411-437.Liu Jiacheng，Zhu Zi. Explanation and implementation of the IAU200O/2006 resolutions onfundamental astronomy [J].Progress in Astronomy，2012，30(4）：411-437.  
[11]Ron C.The tables of differences between the nutation series IAU2000,IERS 1996 and IAU1980[C]//Proceedings of the IERS Workshop on the Implementation of the New IAU Resolutions.2002：111-113.

# Apparent Position Calculation of Celestial Body in the Solar System Used for the Celestial Attitude Determination

Lian Yueyong¹，Zhang Chao’，Zhan Yinhu'，Xie Zongte²（1.InformatioEgiUesityZgo0ina；.51os，aguoinEmailb@.co）

Abstract:Celestial apparent position is the key data for celestial atitude determination.At present，the study of apparent position calculation mainly focuses on ground and ocean；development in space-based platform should take a further step.A conversion principle of apparent position in the spacecraft andvarious position correction formula is introduced in this thesis；based on the new astronomical reference frame，a model is established to calculate the apparent position of celestial bodies in the solar system，through which instantaneous geocentric virtual position and observer-fixed apparent position can be calculated.Compared with geocentric virtual position of astronomical almanac,the diference valueof Jovian planet'right ascension can be controlled within 10ms and declination difference under 22Omas；Compared with observer-fixed apparent position of satelite tool kit，the diffrencevalueof rightascension can be keptunderO.15sand the declination difference under $2 ^ { \prime \prime }$ .Experiments show that the model can correctly compute instantaneous apparent position of celestial body in the solar system and such precision meets the requirements of celestial atitude determination.

Key words:Apparent position calculation；Celestial atitude determination；Astronomical almanac；System Tool Kit