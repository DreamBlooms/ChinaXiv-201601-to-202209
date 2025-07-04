# 相互逼近技术用于小行星702(Alauda)的高精度位置测量试验

覃永贵1,2，彭青玉1,2,\*(1暨南大学 计算机科学系，广州 510632)(2 暨南大学中法天体测量、动力学与空间科学联合实验室，广州 510632)

摘要：本文把Morgado等人提出的相互逼近（mutualapproximation）技术从天然卫星的天体位置测量拓展到小行星和邻近Gaia星表参考星的相对位置测量，希望获得更高的小行星的位置测量精度。使用中国科学院云南天文台1m光学望远镜在2020年11月11\~12日对小行星702（Alauda）进行了试验观测。在观测资料中，目标小行星共有5次相互逼近事件。参考GaiaDR2(Data Release 2)星表，归算结果显示，在准确度方面，相互逼近方法与经典天体测量（四常数模型）方法具有良好的一致性；在测量精度方面，相互逼近方法在赤经、赤纬两个方向分别为6毫角秒和2毫角秒，相比于经典天体测量（四常数模型）方法在位置测量精度上有6\~10倍的提高。

关键词：相互逼近技术；天体测量；小行星702(Alauda)；CCD图像处理

中图分类号：P129文献标识码：A

# 1引言

目前，大部分小行星的位置测量都是基于地面光学望远镜观测的图像资料，因而提高地面观测的测量精度是一项十分重要的工作。然而，影响小行星测量精度的因素主要有两个。一是即使在短曝光条件下，快速运动的小行星在CCD图像成像上仍存在拖影，从而引起测量精度的损失。为解决此问题，文献[1]提出了合成追踪技术（technique of synthetic tracking）以获取准确的近地小行星位置。随后，Zhai等人利用该技术在近地小行星位置测量的精度上达到了10毫角秒[2]。二是星表提供恒星数据的精度问题。由于星光在进入地球大气层后发生抖动，历史上的星表在恒星的位置或自行上精确度不高，这给观测对象的位置测量带来了不可忽视的误差。随着航空航天技术的进步与发展，人们把探测器发射到空间中，以消除地球大气的影响。欧洲空间局成功地发射了Gaia卫星，在完成阶段性测量任务后发布了Gaia星表，为高精度的天体测量工作奠定了重要基础。Gaia星表由于其恒星参考星数量庞大及精度高的特性[3-4]，在位置归算工作中得到国际同行的广泛认可。

2016年，Morgado等人[5-7]基于两天体相对位置测量存在着精度回报（precision premium）[8]提出了相互逼近的天体测量技术，可以精确地测量两个天然卫星的相对距离，并成功地将该技术应用到木星伽利略卫星的天体测量。2019年，Santos-Filho等人也成功地使用该技术对天王星卫星进行了天体测量[9]。参考JPL（Jet Propulsion Laboratory）历表，他们的测量结果显示，伽利略卫星内部精度达到11.3毫角秒，天王星卫星达到45毫角秒，并且伽利略卫星间测量结果在准确度和精度上均与联合天象技术相媲美。2019年，Lin等人[10基于M35星团进一步研究了精度回报现象，发现相距100角秒以内的两个天体之间的相对位置测量存在着精度回报，并且可以使用Sigmoid函数描述这两个天体之间的精度回报特性。这项工作为CCD图像上的任意两个天体之间的相对位置测量精度提供了定量描述。理论上，无论两个天体是否发生相对运动，都\*基金项目：国家自然基金(11873026，11273014)；国家自然科学天文联合基金重点项目(U1431227).

作者简介：覃永贵，男，硕士研究生.研究方向：图像处理.Email：952659199@qq.com

存在着精度回报现象。

本文把相互逼近技术从两颗天然卫星天体位置观测拓展到小行星和邻近恒星参考星（位置参考Gaia星表）的相对位置测量，并利用该技术以期改善小行星的位置测量精度。本文的结构如下：第2部分基于小行星在较小天空平面上做匀加速直线运动的假设，阐述了小行星和参考星的相互逼近模型。第3部分给出观测资料、归算过程和结果，并与经典天体测量方法进行比较。最后一部分为本文的总结。

# 2相互逼近技术

# 2.1理论模型

如图1所示，假设小行星做匀加速直线运动（加速度为 $a$ ）经过该天空平面（100角秒以内）。在小行星经过的路径附近，存在一颗参考星Ref。在观测时间内，小行星从A点运动到B点，并令小行星在A点的时刻 $t = 0$ （即起始点）。小行星到达C点时与参考星的角距离达到最小值（即冲击参数——impact parameter，用 $d _ { 0 }$ 表示），到达C点的时刻称为中心时刻（central instant，用 $t _ { 0 }$ 表示）。对于观测时间内的任意时刻t，小行星和参考星的角距离为 $d$ （例如图1中的B点）。

![](images/be6ab5e02534334f9f33cda2268836f05234b3aee93e2926dd72c34ff0194307.jpg)  
图1小行星与参考星的相互逼近模型  
Fig.1Model for the mutual approximation of an asteroid and its reference star

显然，角距离的平方 $d ^ { 2 }$ 有：

$$
d ^ { 2 } = d _ { 0 } ^ { 2 } + ( s - s _ { 0 } ) ^ { 2 } = d _ { 0 } ^ { 2 } + ( { \nu } t + a t ^ { 2 } / 2 - s _ { 0 } ) ^ { 2 } = a _ { 0 } + a _ { 1 } t + a _ { 2 } t ^ { 2 } + a _ { 3 } t ^ { 3 } + a _ { 4 } t ^ { 4 }
$$

$\backslash *$ MERGEFORMAT（1)

其中， $v$ 是小行星在时刻 $t = 0$ 时的速度。我们可以使用最小二乘法求解（1）式的系数$( a _ { 0 } \sim a _ { 4 } )$ ，且有关系：

$$
\left\{ \begin{array} { l l } { a _ { 0 } = d _ { 0 } ^ { 2 } + s _ { 0 } ^ { 2 } , } \\ { a _ { 1 } = - 2 s _ { 0 } \nu , } \\ { a _ { 2 } = \nu ^ { 2 } - s _ { 0 } a , } \\ { a _ { 3 } = \nu a , } \\ { a _ { 4 } = a ^ { 2 } / 4 . } \end{array} \right.
$$

\\*MERGEFORMAT (2)

显然，对（1）式求一阶导并令其等于0，中心时刻 $t _ { 0 }$ 就是该方程的根，

$$
a _ { 1 } + 2 a _ { 2 } t _ { 0 } + 3 a _ { 3 } t _ { 0 } ^ { 2 } + 4 a _ { 4 } t _ { 0 } ^ { 3 } = 0
$$

\\*MERGEFORMAT (3)

我们可以迭代求解出方程（3）的根，得到中心时刻 $t _ { 0 }$ 的值。令 $t = t - t _ { 0 }$ ，使得中心时刻 $t _ { 0 } = 0$ 之后重新拟合（1）式，这时（1）式中的参数 $s _ { 0 } , \ t _ { 0 }$ 均为 $0$ ，于是有关系：

$$
\begin{array} { r } { \left\{ { { a _ { 0 } } = { d _ { 0 } ^ { 2 } } , } \right. } \\ { \left. { { a _ { 1 } } = 0 , } \right. } \\ { \left. { { a _ { 2 } } = \nu ^ { 2 } , } \right. } \\ { \left. { { a _ { 3 } } = \nu a , } \right. } \\ { \left. { { a _ { 4 } } = { a ^ { 2 } } / 4 } \right. } \end{array}
$$

\\*MERGEFORMAT (4)

由（4）式可知，当使用中心时刻 $t _ { 0 } = 0$ 的观测数据再次拟合（1）式后，可以通过（4）式直接求解冲击参数 $d _ { 0 }$ 和小行星在中心时刻 $t _ { 0 }$ 的速度 $v$ （即小行星运动到图1中C点位置的速度），

上面的关系式不仅仅适用于观测数据，同样适用于理论数据（即来自GaiaDR2星表中的恒星参考星数据与历表中的小行星数据）。因此，通过分别拟合观测数据和理论数据，我们可以得到观测数据下的中心时刻 $t _ { 0 } ^ { O }$ （单位为秒）、冲击参数 $d _ { 0 } ^ { O }$ （单位为像素）和小行星在中心时刻的速度 $v ^ { O }$ （单位为像素/秒），以及理论数据下的中心时刻 $t _ { 0 } ^ { C }$ （单位为秒）、冲击参数 $d _ { 0 } ^ { C }$ （单位为角秒）和小行星在中心时刻的速度 $v ^ { C }$ （单位为角秒/秒）。如果能精确计算出CCD图像的比例尺（见2.3节），我们便可以确定小行星在中心时刻的位置偏差（O-C，即观测值减去理论值）：冲击参数的偏差，即 $\Delta d = \rho d _ { 0 } ^ { O } - d _ { 0 } ^ { C }$ （单位为角秒），其中 $\rho$ 是比例尺；小行星在运动方向的位置偏差，即 $\Delta s = v ^ { C } \Delta t$ （单位为角秒），其中 $\Delta t = ( t _ { 0 } ^ { O } - t _ { 0 } ^ { C } )$ 。我们求解小行星在中心时刻的速度虽然有两种方式，即来自观测数据的 $\rho v ^ { O }$ 和来自理论数据的 $v ^ { C }$ ，使用任何一种方式求解均不影响观测资料的归算结果（见3.4节）。

# 2.2 △d、 $\Delta s$ 的投影

为了将2.1节提到的小行星在中心时刻的 $\Delta d$ 、 $\Delta s$ 投影到赤经、赤纬方向上，我们建立如图2所示的以参考星Ref为原点的参考系。图2中，Ref表示参考星； $\xi , ~ \eta$ 分别表示天空平面上的赤经、赤纬方向； $v$ 为小行星的运动方向； $\Delta d$ 和 $\Delta s$ 即为2.1节提到的小行星在中心时刻的位置偏差； $\theta$ 是小行星运动方向与赤经方向的夹角（取值区间 $[ 0 ^ { 0 } , 3 6 0 ^ { 0 } ]$ ）。因为 $\Delta d$ 和 $\Delta s$ 一般为不大于0.1角秒的小量，我们可以使用历表精确计算 $\theta$ 。将 $\Delta d$ 和 $\Delta s$ 以向量形式表示，又 $\xi$ ，$\eta$ 可以视作向量（如图2所示），在右手法则下，如果 $( \overrightarrow { \Delta { d } } \times \overrightarrow { \Delta { s } } )$ 和 $( { \vec { \xi } } \times { \vec { \eta } } )$ 的方向相同，可以证明 $( \Delta { d } , \Delta { s } )$ 和 $( \Delta \alpha c o s \delta , \Delta \delta )$ 投影关系为：

$$
{ \left[ \begin{array} { l } { \Delta \alpha \cos \delta } \\ { \Delta \delta } \end{array} \right] } = { \left[ \begin{array} { l l } { + \sin \theta } & { \cos \theta } \\ { - \cos \theta } & { \sin \theta } \end{array} \right] } { \left[ \begin{array} { l } { \Delta d } \\ { \Delta s } \end{array} \right] }
$$

\\* MERGEFORMAT (5)

否则，

$$
{ \left[ \begin{array} { l } { \Delta \alpha \cos \delta } \\ { \Delta \delta } \end{array} \right] } = { \left[ \begin{array} { l l } { - \sin \theta } & { \cos \theta } \\ { + \cos \theta } & { \sin \theta } \end{array} \right] } { \left[ \begin{array} { l } { \Delta d } \\ { \Delta s } \end{array} \right] }
$$

![](images/96a8cdebf72d02f723ab686edd02f1ae38872fa781b48f2ee36dc06dc8af46b5.jpg)  
图2将 $\Delta d$ 和 $\Delta s$ 投影到赤经、赤纬方向上  
Fig.2 The projection of the shifts $\Delta d$ $\Delta s$ to the right ascension and declination

# 2.3 比例尺

我们根据文献[11-13]构造CCD图像的扭曲模型，去除扭曲效应后使用四常数模型精确计算视场的比例尺（精度达到 $1 0 ^ { - 6 }$ 角秒/像素）。此时由比例尺引起 $\rho d _ { 0 } ^ { o }$ 的误差对归算结果的影响甚微（见3.4节）。

# 3数据归算与结果分析

# 3.1观测资料

表11m光学望远镜和CCD参数说明  
Table 1 Specifications of the 1m optical telescope and CCD chip   

<html><body><table><tr><td>Parameter</td><td>Value</td></tr><tr><td>Approximate focal length</td><td>1330 cm</td></tr><tr><td>F-Ratio</td><td>13</td></tr><tr><td>Diameter of primary mirror</td><td>100 cm</td></tr><tr><td>CCD field of view</td><td>7'× 7'</td></tr><tr><td>Size of CCD array</td><td>2048 × 2048 pixel2</td></tr><tr><td>Adopted scale factor</td><td>0.20973 arcsec/pixel</td></tr></table></body></html>

2020年11月11\~12日，使用中国科学院云南天文台 $\mathrm { ~ 1 ~ m ~ }$ 光学望远镜（I滤光片）对小行星702（Alauda）进行了观测，观测所用望远镜的参数说明见表1。这两个晚上一共获得 550帧的CCD图像数据，每天晚上拍摄的CCD 图像数量、曝光时间和相互逼近事件的数量见表2。此外，使用I滤光片进行观测可以有效减少较差色差折射（differential color refraction）效应对天体测量的影响[14]。

表2小行星702（Alauda）的观测资料概要  
Table.2 Observations overview for Asteroid 702 Alauda   

<html><body><table><tr><td>Date</td><td>No.of CCD frames</td><td>Filter</td><td>Exposure(s)</td><td>No. mutual approximation</td></tr><tr><td>2020-11-11</td><td>240</td><td>I</td><td>30</td><td>2</td></tr><tr><td>2020-11-12</td><td>310</td><td>I</td><td>30</td><td>3</td></tr></table></body></html>

# 3.2数据归算

在对参考星的位置测量和归算中，我们参考了欧洲空间局发布的GaiaDR2星表[3-4]，小行星702（Alauda）的理论位置参考了美国国家航空航天局喷气推进实验室发布的JPL历表(https://ssd.jpl.nasa.gov）。在上面的位置归算中，我们均考虑到了站心视位置的计算和大气折射的影响。

小行星与参考星相互逼近的归算步骤如下：第一步对所有的观测资料，使用二维高斯定心算法拟合求解参考星和小行星在CCD图像中的像素位置。第二步，计算小行星和参考星之间像素距离的平方，并用于拟合4次多项式函数（即（1）式）。第三步，对拟合得到的（1）式进行一阶求导，并令其等于0（即方程（3）），迭代求解方程（3）的根，获取中心时刻。第四步，将观测数据的时间整体减去中心时刻，再次使用观测数据拟合（1）式。根据2.1节的（4）式，计算冲击参数和小行星在中心时刻的速度。同理，小行星和参考星的理论数据也进行上述类似的归算过程。于是，我们便能得到小行星在中心时刻的位置偏差，即2.1节的 $\Delta d$ ，Δs。利用 JPL历表，计算小行星的速度方向与赤经方向的夹角θ，根据2.2节的方法，将△d 和$\Delta s$ 投影到赤经、赤纬方向，最后得到小行星的位置测量在赤经、赤纬两个方向的（O-C）。

# 3.3结果与分析

在2020年11月11\~12日拍摄的两个晚上的观测资料，分别存在2颗和3颗参考星与小行星702（Alauda）进行相互逼近，其归算结果见表3。目标小行星702（Alauda）在JPL历表显示其星等约为 $1 2 \mathrm { m a g }$ ，5颗参考星的G星等范围为 $1 3 { \sim } 1 6 \mathrm { m a g }$ ，于是小行星和参考星的星等差不大于5。比较相互逼近测量技术与经典天体测量（四常数模型）方法的归算结果（见表3)可以得出，两者位置测量的平均（O-C）在赤经和赤纬方向有良好的一致性，前者的精度分别为6毫角秒和2毫角秒，相比于后者有6-10倍的提高。此外，虽然使用更高阶模型的经典天体测量方法可以提高测量精度，但是我们在使用相互逼近技术时，并未考虑视场的扭曲和高阶大气折射的模型，因而经典天体测量（四常数模型）方法与相互逼近技术测量方法等价。

图3显示了表3观测资料的归算结果在赤经、赤纬两个方向的（O-C）与参考星星等和冲击参数的关系。从图3可以得出，在赤经、赤纬两个方向的（O-C）与冲击参数没有明显的相关性；在赤经方向的（O-C）与参考星星等没有呈现明显关系，但在赤纬方向的（O-C）与参考星星等之间可能存在二次函数关系。

# 3.4误差分析

在2.1节中求解小行星在中心时刻的速度有两种方式，即来自观测数据的 $\rho v ^ { O }$ 和来自理论数据的 $v ^ { C }$ 。在归算观测资料时，我们发现 ${ \rho } v ^ { O }$ 和 $v ^ { C }$ 的差值是微小量（小于 $1 0 ^ { - 5 }$ 角秒/秒），该差值与 $\Delta t$ （小于15秒）之积小于1毫角秒，所以 $\rho v ^ { O }$ 和 $v ^ { C }$ 的偏差对小行星在运动方向的位置偏差 $\Delta s$ 的影响可忽略不计。其次，由式(4）可知小行星在中心时刻的速度 $v ^ { O } = \sqrt { a _ { 2 } }$ ，于是其误差为 $\delta v ^ { O } = \delta a _ { 2 } / ( 2 v ^ { O } )$ 。在归算观测资料中，利用相互逼近技术计算小行星在中心时刻速度的误差不超过 $4 \times 1 0 ^ { - 6 }$ 角秒/秒。另外，由2.3节可知比例尺的精度达到 $1 0 ^ { - 6 }$ 角秒/像素，由于冲击参数 $d _ { 0 } ^ { O }$ 不大于100角秒，因此由比例尺引起 $\rho d _ { 0 } ^ { o }$ 的误差对归算结果不超过1毫角秒。

在对运动的天体进行高精度的位置测量时，还需要考虑相位角效应（phase effect）等因素对测量结果的影响。根据文献[15]，相位角影响的大小可以使用公式

$$
{ \scriptstyle \left[ - \Delta \alpha \cos \delta \right] = \left[ \sin \mathcal { Q } \atop \cos \mathcal { Q } \right]}   C r \sin ( i / 2 )
$$

描述，其中 $r$ 是目标的视半径， $i$ 是太阳相位角， $Q$ 是日下点在切平面的位置角， $c$ 是光照反射模型，且 $0 \leq C \leq 1$ ，又 $0 \leq | s i n Q | , | c o s Q |$ ，|sin $( i / 2 ) | \leq 1$ ，从JPL历表查询到小行星 702（Alauda）的视半径 $r$ 在观测时间内的变化不超过0.04毫角秒，据此预估相位角效应对位置的测量精度的影响不超过0.04毫角秒，远小于位置的测量精度，因此相位角对本文归算结果的影响甚微。此外，当曝光时间较长时，运动速度较快的小行星受抖动效应影响，造成其在CCD 图像的成像上存在拖尾现象，对小行星的高精度测量带来不可忽视的影响[2]。由于小行星702（Alauda）的运动速度较小（约0.006角秒/秒）且曝光时间较短（30秒），曝光时间与小行星运动速度之积远小于宁静度（约1.5角秒 ${ \sim } 2 . 0$ 角秒），故抖动效应带来的影响可忽略不计。

表3 小行星702（Alauda）的归算结果。第一列是观测日期。第二列给出参与相互逼近的Gaia DR2参考星的唯一标识。第三列是参考星的G星等。第四列为相互逼近的冲击参数（单位为角秒）。第五列以对应于UTC 的儒略日（Julian date）减去2459100形式给出的中心时刻。最后两列分别列出在赤经、赤纬方向上的观测位置偏差（O-C）（单位为角秒）。最后两行分别给出相互逼近测量技术和经典天体测量（四常数模型）方法位置测量的平均（O-C）和标准差（单位为角秒）。

Table3Thereducedresultsofallobservationsofasteroid7Auda.Thefirstcolumistheobservationdate.Column2showstheunique sourcedentifierofGaaDR2starfoeachapproximationevent.Cou3givestheG-bandmeanmagnitudeoftheferencstarTefourth columlists teapproximateimpactparameterinunitsofrcseonsforachaproximationventTefthcouniesthectralistats intheformofthecorspondingUTCJuliandateminus2459.Thelasttwocoluslistthe(-Ciightasesionandclinationin unitsofarcseondsspectivelyTheaveragepositional(O-andstandardeviation(unitsofseconds)futualaproximatiosad classical astrometry of 4-constant plate model are given in the last two lines.   

<html><body><table><tr><td>Date</td><td>ID of Ref-star</td><td>Gmag of Ref-star</td><td>Impact Parameter</td><td>JD- 2459100</td><td>△acos8</td><td>△8</td></tr><tr><td rowspan="2">2020/11/11</td><td>190965103659693952</td><td>13.8</td><td>14.7</td><td>65.371358</td><td>0.077</td><td>-0.004</td></tr><tr><td>190965107955867776</td><td>14.2</td><td>7.8</td><td>65.338580</td><td>0.086</td><td>-0.006</td></tr><tr><td rowspan="3">2020/11/12</td><td>190945316746612608</td><td>15.4</td><td>24.6</td><td>66.359842</td><td>0.088</td><td>-0.008</td></tr><tr><td>190945106293176064</td><td>16.2</td><td>19.2</td><td>66.341169</td><td>0.082</td><td>-0.009</td></tr><tr><td>190945110588179456</td><td>15.3</td><td>33.1</td><td>66.327897</td><td>0.094</td><td>-0.008</td></tr><tr><td colspan="2"></td><td>Mutual Approximation</td><td></td><td></td><td>0.085±0.006</td><td>-0.007±0.002</td></tr><tr><td colspan="4">Classical CCD Astrometry</td><td></td><td>0.087±0.036</td><td>-0.002±0.020</td></tr></table></body></html>

![](images/8c9ab0ed6f17c3191b3a549f8563f64841b58e310780d5a627f80eb1846d456d.jpg)  
图3（O-C）与参考星星等和冲击参数的关系。图a、b分别表示在赤经、赤纬方向上的（O-C）与参考星星等的关系，图c、d分别 表示在赤经、赤纬方向上的（O-C）与冲击参数的关系。 Fig.3Therelationetwe(O-CandmagtudeofreferencestarsorimpactparametersPanelaandbshowteelatioshipetwen(OC) andmagnitudeofreferencestarsinthightascesionnddclinationespectivelyPanelcaddhowtheelationshipbetwn(Oand impact parameters in the right ascension and declination,respectively.

# 4总结

本文把相互逼近技术拓展到了小行星和邻近恒星参考星的相对位置测量。不同于Morgado等人提出的相互逼近模型，本文的相互逼近模型是小行星和Gaia参考星之间相对位置测量的模型。此外，本文根据小行星在较小天空平面上作匀加速直线运动的假设推导出的相互逼近模型，不仅具有良好的物理意义，还能直接求解出小行星在中心时刻的速度和冲击参数，在一定程度上优化了相互逼近模型。在使用中国科学院云南天文台1m光学望远镜观测小行星702（Alauda）的两晚资料中，我们一共捕获了5次小行星与恒星进行相互逼近的事件。参考GaiaDR2 星表的归算结果显示，相互逼近测量技术与经典天体测量（四常数模型）方法相比，在赤经、赤纬两个方向有良好的一致性，相互逼近技术在赤经、赤纬两个方向的位置测量精度分别为6毫角秒和2毫角秒，比经典天体测量（四常数模型）方法提高了 $6 { \sim } 1 0$ 倍。上述结果表明，本文为小行星的位置测量提供了一种高精度的测量方法。

致谢 感谢中国科学院云南天文台 $\mathrm { ~ 1 ~ m ~ }$ 望远镜运行团组给予的帮助和支持,感谢郭碧峰、林孚荣在论文写作中给予了帮助

# The Experiment for the Application of Mutual Approximation Technique to High-precision Positional Measurement of Asteroid 702 (Alauda)

Qin Yonggui1,2, Peng Qingyu1,2,\* (1Department of Computer Science,Jinan University,Guangzhou,510632, China) (2 Sino-FrenchJointLaboratoryforAstrometry,DynamicsandSpaceScience,JinanUniversity,Guangzhou,563,Cina)

Abstract: This paper extends the mutual approximation technique proposed by Morgado et al. from positional measurement of natural satelites to a relative positional measurement of an asteroid and its nearby Gaia reference star, hoping to obtain a higher positional precision of asteroids.lm telescope at Yunnan Observatory of the Chinese Academy of Sciences is used to obtain the observations of the asteroid 702 (Alauda) on November 11 and 12,2020. There are totally 5 approximation events of the asteroid with different reference stars in the observations.With reference to Gaia DR2 (Data Release 2) catalogue,our results show that in terms of accuracy,the mutual approximation technique is in good agreement with the classical CCD astrometry (i.e.,a 4-constant plate model solution). The positional precision of the mutual approximation technique is 6 mill-arcseconds and 2 milli-arcseconds in right ascension and declination respectively，and the positional precision is improved obviously in compared with the classical CCD astrometry by a factor of $6 { \sim } 1 0$

Key words: Mutual Approximation Technique; Astrometry; Asteroid 702(Alauda)； CCD Image Processing

# 参考文献

[1] Shao M.,NematiB.,Zhai,C.etal.,Finding VerySmallNear-EarthAsteroids using Synthetic Tracking.ApJ,2014,782, 1.   
[2] Zhai C,Shao M,Saini NS,etal.,Accurate Ground-based Near-Earth-Asteroid Astrometry using Synthetic Tracking[J]. AJ,2018,156 (2): 65.   
[3] Lindegren L.,Lammers U.,Bastian U.et al., Gaia data release l-astrometry:one bilion positions,two millon proper motions and parallaxes.A&A,2016,595,A4.   
[4] Gaia Collboration,Gaia Early Data Release 3: Summary of the contents and survey properties.A&A (accepted),2020.   
[5] Morgado B,Asafin M,Vieira-Martins R,et al.，Astrometryof mutual approximations between natural satelites. Application to the Galilean moons[J].MNRAS,2016,460 (4): 4086-4097.   
[6] Morgado B,Vieira-Martins R,Assafin M,etal.,APPROX- mutualapproximations between the Galilean moons:the 2016 - 2018 observational campaign[J].MNRAS,2019,482 (4): 5190-5200.   
[7] Morgado B,Vieira-Martins R,Assafin M,etal.,The2014-2015Brazilian mutualphenomena campaign fortheJovian satellites and improved results for the 2009 events[J].P&SS,2019,179:104736.   
[8] Pascu.D.,An appraisal of the USNO program of photographic astrometryof bright planetary satelites[C],G&SSOA, 1994:304-311.   
[9] Santos-Filho S,Assafin M,MorgadoBE,et al.,Mutual approximations between the five main moons of Uranus[J]. MNRAS,2019,490 (3):3464-3475.   
[10] LinFR,PengJH,Zheng ZJ,etal.,Characterizationof theprecisionpremium inastrometry[J].MNRAS,2019,490 (3): 4382-4387.   
[11]Peng QY,Vienne A,ZhangQF,etal.,A ConvenientSolution to Geometric Distortionand Its ApplicationtoPhoebe's Observations[J].AJ,2012,144 (6):170.   
[12]Wang N.,Peng Q.Y.,Peng H.W.,etal.,Precise CCD positionsof Triton in 2014-2016 using the newest Gaia DRl star catalogue.,MNRAS,2017,468,1415-1419.   
[13]Peng HW,Peng QY,Wang N.,Precise CCD positions of Himalia using Gaia DR1 in 2015-2016[J].MNRAS,2017, 467(2): 2266-2273.   
[14]LinF.R.,PengQ.Y.,Zheng Z.J.,Using GaiaDR2 tosolve diferential colourrefractionandcharge transfer effcency issues.MNRAS,2020,498,258-264.   
[15]LindegrenL.,Meridianobservationsofplanets withaphotoelectric multislit micrometer[J].A&A,1977,57:-72.