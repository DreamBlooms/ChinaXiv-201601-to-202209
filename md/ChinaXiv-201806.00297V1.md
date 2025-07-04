# 差分像运动视宁度优化监测法

王子跃1，任德清1,21 (中国科学院国家天文台南京天文光学技术研究所，江苏 南京 210042)2（美国加州州立大学北岭分校，物理与天文学系，美国加州北岭91330-8268）3（中国科学院大学，北京100049）

摘要：大气视宁度是衡量台址大气光学品质的重要指标。差分像运动视宁度监测仪(DifferentialImage Motion Monitor,DIMM）,被广泛应用于国内外天文选址的视宁度测量作业，例如,ES0DIMM被应用于欧洲南方天文台选址。介绍了一种优良的视宁度测量方法—差分像运动视宁度优化监测（I-DIMM,Improved toDifferentialImage Motion Monitor）法。首先对I-DIMM的结构设计和视宁度计算方法进行了详细描述，随后通过设置0.36m和0.12m两种口径望远镜进行视宁度的模拟测量，将I-DIMM测量结果与传统的DIMM测量的结果进行对比,均证明I-DIMM视宁度计算方法比DIMM更为精确，最后对模拟结果进行了分析，证明了I-DIMM相比于DIMM的优势。

关键词：差分像运动视宁度优化监测法；大气视宁度；台址；差分像运动视宁度监测仪中图分类号：P11 文献标识码：A 文章编号：1672-7673(2018)

弗洛伊德参数 $\boldsymbol { { r } } _ { 0 }$ ，即大气光学相干长度，是衡量一个台址大气视宁度的重要参数。运用差分像运动法，通过测量星像相对位置的变化计算 $\varGamma _ { 0 }$ 值，能够有效地消除非大气因素对大气视宁度测量的影响，使得测量结果更加准确可靠。差分像运动视宁度监测仪是以此原理设计研制的。

现如今，在量化天文视宁度领域，最普遍的方法是差分像运动测量法（Differential ImageMotion Monitor,DIMM)，由 Sarazin 和Roddier 两位科学家在1990 年为欧洲南方天文台选址时提出。它由一个35cm口径的望远镜和一块有两个子瞳的掩模组成,最后连接一块CCD。对于经过地球大气的单一目标光源，差分像运动视宁度监测仪测量其在望远镜入瞳面的两个子瞳上的波前到达角的相对方差，求得大气视宁度参数 $\varGamma _ { 0 }$ 。该方法的优点是能有效消除望远镜由于风力载荷造成的追踪星轨误差、仪器抖动等非大气因素的影响，具有足够的时空精度，便于野外选址使用。1980 年以后，很多优良台址和新的选址工作都使用了差分像运动视宁度监测仪，例如：西班牙La Palma 天文台选址，日本 Subaru八米望远镜选址3，国内有云南天文台丽江高美古 2.4米望远镜选址4等。然而，差分像运动视宁度监测仪在测量过程中入瞳掩模的尺寸是固定的，所以一次曝光捕捉的图像上只能得到一组固定子瞳间距的星像相对位移信息。

DIMM方法只能够测量总的大气视宁度，无法对某一层高度的大气视宁度进行测量，而三维大气视宁度测量是设计多层共轭自适应光学系统的前提，针对该问题文[5]于2015.基金项目：

年提出了多子孔径日间视宁度监测仪（Multiple-Aperture Seeing Profiler,MASP）[5]，用来测量日间大气视宁度。它由两个口径 $4 0 \mathrm { c m }$ 的望远镜组成，选取双星作为导星，在 $0 { - } 3 0 \mathrm { k m }$ 范围分多层对大气湍流进行分析，进而得出大气视宁度参数 $\boldsymbol { { r } } _ { 0 }$ 。它可以将大气湍流测量高度提升至 $3 0 \mathrm { k m }$ ，等同于 $1 1 2 \mathrm { c m }$ 大口径望远镜所能测量的高度。多子孔径日间视宁度监测仪具有成本低、可移动性强等优点，尤其适合还不具备大口径望远镜的新台址。但是一般情况下，只需测量总的大气相干长度 $\boldsymbol { { r } } _ { 0 }$ ，无需对多层大气湍流进行量化，另外多子孔径日间视宁度监测仪用到两台望远镜使得架设过程较为复杂，不便于总体大气视宁度的测量工作。

本文提出一种名为差分像运动视宁度优化监测法：I-DIMM（Improved to DifferentialImage Motion Monitor)。该方法在差分像运动视宁度监测仪"的基础上进行改良，不再采用瞳孔掩模制造子瞳的方式，而是改为在望远镜瞳面上选择两个间距 $2 0 \mathrm { c m }$ 的子孔径，通过应用 MASP中计算大气视宁度参数 $\boldsymbol { { r } } _ { 0 }$ 的方法，对两个子孔径采集到的星像像差法处理，使得计算得到的 $\boldsymbol { { r } } _ { 0 }$ 值更为精确。此外，相较于DIMM法，I-DIMM系统通过改变两个子孔径之间的距离，得到不同子孔径间距情况下的 $\boldsymbol { { r } } _ { 0 }$ 结果，尤其在较小子孔径间距（1.6口3.0个子孔径直径距离）时，I-DIMM计算得到的 $\boldsymbol { r _ { 0 } }$ 值比DIMM 法更精确。

# 1I-DIMM系统描述

![](images/222c87b044189f666487f3d1e72a76d46809e181cff95b3f3bc113ba7d479f7d.jpg)  
图1差分像运动视宁度监测仪光学系统示意图Fig.1 DIMM Optical Scheme

应用于欧洲南方天文台选址的差分像运动视宁度监测仪光学结构如图1，传统 DIMM系统通常在小口径(比如 $1 8 0 \mathrm { m m } ^ { \sim } 3 5 0 \mathrm { m m } )$ 望远镜的入瞳上放置一块有两个子瞳（204号 $( 5 0 \mathrm { m m } ^ { \sim } 1 0 0 \mathrm { m m } )$ 的掩模，并在其中一个子瞳上放置光楔，使到达这个子瞳的波前产生倾斜，从而同一目标星经过两子瞳后产生不重叠的双像，最后用探测器记录下一系列双像的瞬时状态，并统计双像相对位置的方差，即可计算出视宁度。本文用于对比的传统DIMM系统即[在此处键入]

为此结构及原理。具体参数见表1。

表1欧洲南方天文台DIMM参数 Table1 ESODIMMParameters   

<html><body><table><tr><td>ESODIMM技术参数名称</td><td>参数数值或型号</td></tr><tr><td>望远镜口径</td><td>35cm</td></tr><tr><td>子瞳口径D</td><td>4cm</td></tr><tr><td>间距d</td><td>20cm</td></tr><tr><td>d/D</td><td>5</td></tr><tr><td>焦比</td><td>f/15</td></tr><tr><td>探测器</td><td>增强 CCD</td></tr><tr><td>像元角尺寸</td><td>0.87"x0.87"</td></tr></table></body></html>

本文的I-DIMM系统在模拟时采用微透镜阵列将望远镜瞳面分割成多个子孔径，如图2。将有效的哈特曼子孔径的线性阵列进行编号，如图3。

![](images/52aae07e48c2bec219fb7d4485d257fc7d6af803c1f755253847c59c03e75ca6.jpg)  
图2I-DIMM工作流程图Fig.2I-DIMMworkflow diagram

![](images/2088db674d79e3c3d541d52d7d3dc6b3fa106677d9818eb02a71a55225008926.jpg)  
图3I-DIMM 夏克-哈特曼波前传感微透镜阵列Fig.3I-DIMM SHWFS lens let array

如图3的I-DIMM系统中，在直径长度上由9个哈特曼子孔径组成，相当于将望远镜瞳面直径方向上等分为9个子孔径（如图数字1-9)，每个子孔径的直径 $4 \mathsf { c m }$ ，与DIMM中子瞳口径相等（参见表1，欧洲南方天文台DIMM参数表)。在同一行的哈特曼子孔径阵列中，相邻两个数字代表的孔径相距为一个子孔径直径的距离，即1D。以此类推，数字间相差为2的两个子孔径间距为2D，当数字间相差为5时，两个子孔径间距5D，相当于DIMM中两个子瞳相距 $2 0 \mathsf { c m }$ 。这样在结构模型上完成了I-DIMM系统与DIMM系统的一致与统一。对于一个固定的子孔径间距，每一行阵列可以至少提供一种子孔径的组合方式。以Fig.B为例，子孔径1与2的组合间距为1D，而子孔径3与4的组合间距也为1D,以此类推，间距为1D可以找到8种子孔径组合。图4展示了直径不同的夏克-哈特曼子孔径组合的数量与对应的孔径间距之间的关系。

![](images/870a2b2f8ed2fa432ddae5c07be29bb4085dc542c3201e246941829520c4b109.jpg)  
图4夏克-哈特曼子孔径组合数量与孔径间距的关系 Fig.4Numberofsub-aperture pairs versus the sub-aperture distance

# 2I-DIMM计算理论

在传统的 DIMM 法[1]中，在 $L$ 方向（沿着子瞳中心连线方向）差分像位移方差的表达式为

$$
< [ \lambda ( d ) - \mathit { { l } } ( 0 ) ] ^ { 2 } ~ > = 0 . 3 5 8 \lambda ^ { 2 } r _ { 0 } ^ { - \frac { 5 } { 3 } } D ^ { - \frac { 1 } { 3 } } \cdot [ 1 - 0 . 5 4 1 ( \frac { d } { D } ) ^ { - \frac { 1 } { 3 } } ] .
$$

$T$ 方向（垂直于子瞳中心连线方向）差分像位移方差的表达式为

$$
< [ t ( d ) - t ( 0 ) ] ^ { 2 } > = 0 . 3 5 8 \lambda ^ { 2 } { r _ { 0 } } ^ { - \frac { 5 } { 3 } } D ^ { - \frac { 1 } { 3 } } \cdot [ 1 - 0 . 8 1 1 ( \frac { d } { D } ) ^ { - \frac { 1 } { 3 } } ] .
$$

两者方差可以用单个孔径的二维运动总方差 $\sigma ^ { 2 }$ 表示：

$$
\sigma ^ { 2 } = 0 . 3 5 8 ( \frac { \lambda } { r _ { 0 } } ) ^ { \frac { 5 } { 3 } } ( \frac { \lambda } { D } ) ^ { \frac { 1 } { 3 } } .
$$

理论上，假设 $S = d / D$ ，应用(3)式应满足条件： $S \ge 2$ 。式(4)(5)简化为：

$$
\sigma _ { \it l } ^ { 2 } \ = \ { \cal I } _ { \it D I M M } ( S , 0 ) \sigma ^ { 2 }
$$

$$
\boldsymbol { \sigma } _ { t } ^ { 2 } \ : = \ : I _ { p I M M } ( S , \frac { \pi } { 2 } ) \boldsymbol { \sigma } ^ { 2 }
$$

其中

$$
I _ { \mathit { D I M M } } ( S , 0 ) = 1 - 0 . 5 4 1 S ^ { - \frac { 1 } { 3 } }
$$

$$
I _ { \mathit { D I M M } } ( S , \frac { \pi } { 2 } ) = 1 - 0 . 8 1 1 S ^ { - \frac { 1 } { 3 } }
$$

虽然，文[1]给出的上述近似表达已经对文[6]的表达式进行了改进，在 $d > D / 2$ 时能够[在此处键入]

和文[6]给出的近似值良好匹配[1]，例如，当 $S = 1$ 时，沿着子瞳中心连线方向的差分像运动位移方差近似值偏差率为 $0 . 2 \%$ ，但是在垂直于子瞳中心连线的方向上，差分像运动位移方差却偏差了， $. 1 7 . 3 \%$ 。当 $s { = } 2$ 时，垂直于子瞳中心连线方向的差分像运动位移方差依然偏差较大，有 $- 9 . 0 \%$ 之多。所以，为得到更精确的 ${ \varGamma } _ { 0 }$ 估计，本文将 $S$ 趋近于0 的情况也考虑其中，引用文[5]在MASP 中的近似表达式：

$$
\begin{array} { l } { { \displaystyle \sigma _ { _ I } ^ { 2 } = \sum _ { n = 1 } ^ { N } F _ { _ I } ( d , \theta , h _ { n } ) \sigma ^ { 2 } \ : , } } \\ { { \displaystyle \sigma _ { _ t } ^ { 2 } = \sum _ { n = 1 } ^ { N } F _ { _ t } ( d , \theta , h _ { n } ) \sigma ^ { 2 } \ : . } } \end{array}
$$

其中:

$$
\begin{array} { r l r } & { } & { F _ { \mathit { l } } ( d , \theta , h _ { n } ) = I _ { \mathit { I - D I M M } } ( \displaystyle \frac { \theta h _ { n } - d } { D } , 0 ) / 2 } \\ & { } & { + I _ { \mathit { I - D I M M } } ( \displaystyle \frac { \theta h _ { n } + d } { D } , 0 ) / 2 - I _ { \mathit { I - D I M M } } ( \displaystyle \frac { \theta h _ { n } } { D } , 0 ) , } \end{array}
$$

$$
F _ { t } ( d , \theta , h _ { n } ) = I _ { \scriptscriptstyle { I - D I M M } } ( \frac { \theta h _ { \scriptscriptstyle { n } } - d } { D } , \frac { \pi } { 2 } ) / 2
$$

$$
+ I _ { _ { I - D I M } } ( \frac { \theta h _ { n } + d } { D } , \frac { \pi } { 2 } ) / 2 - I _ { _ { I - D I M M } } ( \frac { \theta h _ { n } } { D } , \frac { \pi } { 2 } ) .
$$

由于本文研究导星数量为一，且仅评估总的 $\boldsymbol { r _ { 0 } }$ 值，故 $\theta = 0$ ， $h _ { { } _ { n } }$ 是望远镜垂直上空大气湍流的叠加。再联合 $S = d / D$ ，式(14)(15)改写为：

$$
F _ { \scriptscriptstyle I } ( d , 0 , h _ { \scriptscriptstyle \pi } ) = I _ { _ { I - D I M } } ( - S , 0 ) / 2 + I _ { _ { I - D I M } } ( S , 0 ) / 2 - I _ { _ { I - D I M } } ( 0 , 0 ) ,
$$

$$
F _ { t } ( d , \frac { \pi } { 2 } , h _ { n } ) = I _ { _ { I - D I M } } ( - S , \frac { \pi } { 2 } ) / 2 + I _ { _ { I - D I M } } ( S , \frac { \pi } { 2 } ) / 2 - I _ { _ { I - D I M } } ( 0 , \frac { \pi } { 2 } ) .
$$

对于方形子孔径，文[7]指出，函数 $I _ { I - D I M } ( i , 0 )$ 和函数 $I _ { I - D I M M } ( i , \frac { \pi } { 2 } )$ 的定义分别为

$$
{ \cal I } _ { _ { I - D I M } } ( i , 0 ) = 2 - \left| 1 - i \right| ^ { 5 / 3 } + 2 \left| i \right| ^ { 5 / 3 } - \left| 1 + i \right| ^ { 5 / 3 } ,
$$

$$
I _ { _ { I - D I M M } } ( i , \frac { \pi } { 2 } ) = 2 + 2 \left| { \cal i } \right| ^ { 5 / 3 } - 2 ( 1 + i ^ { 2 } ) ^ { 5 / 6 } .
$$

引入函数 $\cos ( \it { \Delta } I _ { \it { 1 - D I M M } } / I _ { \it { D I M M } } )$ ：当 $I _ { \ / { I - D I M M } } / I _ { \ / { D I M M } } \ < \ 1$ 时，函数值为 $\phantom { - } 0$ ，即 ${ \cal I } _ { \ / I - D I M M } \ < \ { \cal I } _ { \ / D I M M }$ ，否则为1,即 $I _ { \mathit { I - D I M M } } \ > \ I _ { \mathit { D I M M } }$ 。表2和表3给出了在两个方向上,Fried近似值、 $\boldsymbol { I } _ { D I M M }$ 和 $\boldsymbol { I } _ { \boldsymbol { I } - \boldsymbol { D } \boldsymbol { I } \boldsymbol { M } _ { } }$ （204号3种 $\varGamma _ { 0 }$ 计算方法在不同孔径分离比下的二维运动关系偏差值。

# 表2L方向3种方法在不同孔径分离比下的二维运动关系偏差

Table2 Difference of two-dimensional motion for various aperture-to-separation ratios in longitude by three methods   

<html><body><table><tr><td>S</td><td>Fried</td><td>IDImm (S,0)</td><td>%偏差</td><td>I1-DIMM(S,0)</td><td>%偏差</td><td>Comp()</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

<html><body><table><tr><td>1.0</td><td>0.460</td><td>0.459</td><td>-0.2</td><td>0.413</td><td>-10.0</td><td>0</td></tr><tr><td>1.5</td><td>0.545</td><td>0.527</td><td>-3.2</td><td>0.506</td><td>-4.0</td><td>0</td></tr><tr><td>2.0</td><td>0.593</td><td>0.571</td><td>-3.8</td><td>0.555</td><td>-2.8</td><td>0</td></tr><tr><td>2.5</td><td>0.625</td><td>0.601</td><td>-3.8</td><td>0.588</td><td>-2.2</td><td>0</td></tr><tr><td>3.0</td><td>0.648</td><td>0.625</td><td>-3.6</td><td>0.613</td><td>-1.9</td><td>0</td></tr><tr><td>3.5</td><td>0.665</td><td>0.644</td><td>-3.2</td><td>0.632</td><td>-1.9</td><td>0</td></tr><tr><td>4.0</td><td>0.678</td><td>0.659</td><td>-2.8</td><td>0.649</td><td>-1.5</td><td>0</td></tr><tr><td>4.5</td><td>0.688</td><td>0.672</td><td>-2.3</td><td>0.663</td><td>-1.3</td><td>0</td></tr><tr><td>5.0</td><td>0.696</td><td>0.684</td><td>-1.8</td><td>0.675</td><td>-1.3</td><td>0</td></tr><tr><td>5.5</td><td>0.703</td><td>0.694</td><td>-1.3</td><td>0.685</td><td>-1.3</td><td>0</td></tr><tr><td>6.0</td><td>0.708</td><td>0.702</td><td>-0.8</td><td>0.694</td><td>-1.1</td><td>0</td></tr><tr><td>6.5</td><td>0.712</td><td>0.710</td><td>-0.3</td><td>0.702</td><td>-1.1</td><td>0</td></tr><tr><td>7.0</td><td>0.717</td><td>0.717</td><td>0.0</td><td>0.709</td><td>-1.1</td><td>0</td></tr><tr><td>7.5</td><td>0.721</td><td>0.724</td><td>0.4</td><td>0.716</td><td>-1.1</td><td>0</td></tr><tr><td>8.0</td><td>0.720</td><td>0.730</td><td>1.3</td><td>0.722</td><td>-1.1</td><td>0</td></tr><tr><td>8.5</td><td>0.720</td><td>0.735</td><td>2.1</td><td>0.728</td><td>-1.0</td><td>0</td></tr><tr><td>9.0</td><td>0.719</td><td>0.740</td><td>2.9</td><td>0.733</td><td>-0.9</td><td>0</td></tr><tr><td>9.5</td><td>0.718</td><td>0.745</td><td>3.7</td><td>0.738</td><td>-0.9</td><td>0</td></tr><tr><td>10.0</td><td>0.717</td><td>0.749</td><td>4.5</td><td>0.742</td><td>-0.9</td><td>0</td></tr></table></body></html>

表3「方向3种方法在不同孔径分离比下的二维运动关系偏差Table 3Differences of two-dimensional motion for various aperture-to-separation ratios intransverse by three methods  

<html><body><table><tr><td>S</td><td>Fried</td><td>IDImm(S,π/2)</td><td>%偏差</td><td>I1-DImm(S,π/2)</td><td>%偏差</td><td>Comp()</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>1.0</td><td>0.228</td><td>0.189</td><td>-17.3</td><td>0.218</td><td>15.3</td><td>1</td></tr><tr><td>1.5</td><td>0.320</td><td>0.291</td><td>-9.0</td><td>0.295</td><td>1.4</td><td>1</td></tr><tr><td>2.0</td><td>0.382</td><td>0.356</td><td>-6.8</td><td>0.351</td><td>-1.4</td><td>0</td></tr><tr><td>2.5</td><td>0.425</td><td>0.402</td><td>-5.4</td><td>0.394</td><td>-2.0</td><td>0</td></tr><tr><td>3.0</td><td>0.458</td><td>0.437</td><td>-4.5</td><td>0.427</td><td>-2.3</td><td>0</td></tr><tr><td>3.5</td><td>0.484</td><td>0.466</td><td>-3.8</td><td>0.455</td><td>-2.3</td><td>0</td></tr><tr><td>4.0</td><td>0.504</td><td>0.489</td><td>-3.0</td><td>0.478</td><td>-2.2</td><td>0</td></tr><tr><td>4.5</td><td>0.521</td><td>0.509</td><td>-2.4</td><td>0.497</td><td>-2.4</td><td>0</td></tr><tr><td>5.0</td><td>0.535</td><td>0.525</td><td>-1.8</td><td>0.514</td><td>-2.1</td><td>0</td></tr><tr><td>5.5</td><td>0.546</td><td>0.540</td><td>-1.0</td><td>0.529</td><td>-2.0</td><td>0</td></tr><tr><td>6.0</td><td>0.555</td><td>0.553</td><td>-0.3</td><td>0.542</td><td>-2.0</td><td>0</td></tr><tr><td>6.5</td><td>0.564</td><td>0.565</td><td>0.2</td><td>0.554</td><td>-2.0</td><td>0</td></tr><tr><td>7.0</td><td>0.573</td><td>0.576</td><td>0.5</td><td>0.565</td><td>-2.0</td><td>0</td></tr><tr><td>7.5</td><td>0.579</td><td>0.585</td><td>1.1</td><td>0.575</td><td>-1.7</td><td>0</td></tr><tr><td>8.0</td><td>0.582</td><td>0.594</td><td>2.1</td><td>0.584</td><td>-1.7</td><td>0</td></tr><tr><td>8.5</td><td>0.585</td><td>0.602</td><td>3.0</td><td>0.592</td><td>-1.7</td><td>0</td></tr></table></body></html>

[在此处键入]

<html><body><table><tr><td>9.0</td><td>0.586</td><td>0.610</td><td>4.1</td><td>0.600</td><td>-1.6</td><td>0</td></tr><tr><td>9.5</td><td>0.588</td><td>0.617</td><td>4.9</td><td>0.607</td><td>-1.6</td><td>0</td></tr><tr><td>10.0</td><td>0.588</td><td>0.623</td><td>6.0</td><td>0.614</td><td>-1.4</td><td>0</td></tr></table></body></html>

其中， $\boldsymbol { I } _ { D I M M }$ 的偏差值是与 Fried 给出的近似值比较的结果， $\boldsymbol { I } _ { \boldsymbol { I } - \boldsymbol { D } \boldsymbol { I } \boldsymbol { M } }$ 的偏差值是与 $\boldsymbol { I } _ { D I M M }$ 值比较的结果。

图5和图6给出了两个方向上3种方法在不同孔径分离比的二维运动关系曲线。

![](images/60ef610b4c11f9a16e915bf7e0af05519adde6d3bd835282286504211d5d5082.jpg)  
图53种方法中 $ { L }$ 方向不同孔径分离比的二维运动关系曲线

Fig.5 Graphs of two-dimensional motion for various aperture-to-separation ratios in longitude by three methods

![](images/1620c108e5f62953042a64032a572bbbc88831fc4b92609ffda55b66934fdb30.jpg)  
图6T方向3种方法中 $T$ 方向不同孔径分离比的二维运动关系曲线  
Fig.6 Graphs of two-dimensional motion for various aperture-to-separation ratios in transverse by three methods

图5和图6直观地显示,改进后的 $\boldsymbol { I } _ { \boldsymbol { I } - \boldsymbol { D } \boldsymbol { I } \boldsymbol { M } \boldsymbol { M } }$ 在 $\iota$ 方向上均小于 $\boldsymbol { I } _ { D I M M }$ 。 $\tau$ 方向上，当 $S < 1 . 6$ （204号时， $\boldsymbol { I } _ { \boldsymbol { I } - \boldsymbol { D } \boldsymbol { I } | \boldsymbol { M } }$ 略大于 $\boldsymbol { I } _ { D I M M }$ ，当 $S \geq 1 . 6$ 时， $\boldsymbol { I } _ { \boldsymbol { I } - \boldsymbol { D } \boldsymbol { I } \boldsymbol { M } \boldsymbol { M } }$ 均小于 $\boldsymbol { I } _ { D I M M }$ 。尽管 $\boldsymbol { I } _ { D I M M }$ 是Roddier[1]针对欧洲南方天文台 DIMM 圆形子孔径的简化公式，而 $\boldsymbol { I } _ { \boldsymbol { I } - \boldsymbol { D } \boldsymbol { I } \boldsymbol { M } \boldsymbol { M } }$ 是针对线性类方孔径的简化公式，但根据表2和表3的量化比较，在 $S \geq 1 . 5$ 时，两种简化表达式相差仅仅在 $2 \%$ 上下，孔径形状的不同不会对计算结果带来明显的误差。

# 3I-DIMM与DIMM对比模拟

# 3.1子孔径间距20cm 时I-DIMM与DIMM对比模拟

本文使用专业光学软件YAO（YAO是被广泛公认的用以模拟不同大气及星源条件下点扩散函数成像的软件)。在Linux 环境下运行YAO，设置望远镜口径为36cm，直径方向上设置9个子孔径，每个子孔径直径4cm，设置与传统DIMM相同的望远镜参数[，这样，I-DIMM在硬件上与DIMM完全相同，所以排除了两种方法在计算 $\varGamma _ { 0 }$ 值时因为硬件原因导致的差异与误差，最终结果的差异完全因为计算公式的差异。在硬件上通过设置大气湍流参数，初始化 $\boldsymbol { { r } } _ { 0 }$ 设置值 $0 . 1 \mathrm { { m } \ ( \it { s t d } \mathrm { { \Omega = \ 0 . 1 } } \mathrm { { ) } } }$ ，运行仿真软件得到一系列光源的点扩散函数模拟图像，仿真DIMM中差分像运动图像的曝光捕捉。具体设置参数如表4。

# 表4YA0参数设置

Tab.4 Software YAO setup parameters

# YAO参数设置

<html><body><table><tr><td>望远镜口径</td><td>0.36m</td></tr><tr><td>子孔径口径D</td><td>0.04m</td></tr><tr><td>间距d</td><td>0.04-0.32m</td></tr><tr><td>S=d/D</td><td>1-8</td></tr><tr><td>子孔径像元角尺寸</td><td>0.87"× 0.87"</td></tr><tr><td>工作波长</td><td>500nm</td></tr><tr><td>曝光时间</td><td>10ms</td></tr><tr><td>点扩散函数图像</td><td>2000 幅/组数</td></tr><tr><td>模拟组数</td><td>100</td></tr><tr><td>初始设置总ro值</td><td>0.1m</td></tr></table></body></html>

每次模拟处理 2000幅点扩散函数图像，共模拟100次。利用图像质心算法求得每一个子孔径上图像质心在 $L$ （沿着子瞳中心连线）和 $T$ （垂直于子瞳中心连线）方向的坐标，结合差分像运动算法，求得在两个方向上的大气视宁度参数 $\boldsymbol { { r } } _ { 0 }$ 值，图7和图8分别给出了 $L$ 和 $T$ 两个方向上， $S \ : = \ : 5$ 时，100 次模拟求得的 $\boldsymbol { { r } } _ { 0 }$ 值。

![](images/1804e8bb42ec1993ec52971db6d948579e7e0d6e7aece7f00acad795d1fdc7e1.jpg)  
图7 $s = 5$ 时 $ { L }$ 方向100 次模拟 $\boldsymbol { { r } } _ { 0 }$ 计算值  
Fig.7 $s = 5$ results of $\boldsymbol { { r } } _ { 0 }$ by100 times simulating in Longitude

![](images/380d326d3ea1037e1c58c407625245a2e83f59b318b4e6ca18d4142c47c4d89d.jpg)  
图8 $s = 5$ 时T方向100次模拟 $\boldsymbol { { r } } _ { 0 }$ 计算值

如图7和图8，当子孔径间距 $2 0 \mathsf { c m }$ ，即孔径分离比 $S \ : = \ : 5$ 时，100 次模拟中I-DIMM 测量 $\boldsymbol { r _ { 0 } }$ 值均比DIMM更接近设置值 $0 . 1 \mathsf { m }$ 。 $L$ 方向上，I-DIMM 测量 $\boldsymbol { r _ { 0 } }$ 平均值为 $0 . 1 0 0 8 \mathsf { m }$ ，误差$0 . 8 \%$ ，小于 DIMM 的误差 $1 . 6 \%$ ; $T$ 方向上，I-DIMM 测量 $\boldsymbol { { r } } _ { 0 }$ 为 $0 . 1 0 2 6 \mathsf { m }$ ，误差 $2 . 6 \%$ ，小于DIMM的误差 $4 . 0 \%$ 。图9给出了100 次模拟总 $\varGamma _ { 0 }$ 计算值。

![](images/4e41844724666dcf91545e9d69056b10bf418ad7428933f477de9036b524ed2d.jpg)  
Fig.8 $s = 5$ results of $\boldsymbol { { \cal T } } _ { 0 }$ by 100 times simulating in Tranverse

[在此处键入]

I-DIMM 测量总的 $\boldsymbol { { r } } _ { 0 }$ 平均值为 $0 . 1 0 1 7 \mathrm { m }$ ，误差 $1 . 7 \%$ ，小于DIMM的误差 $2 . 8 \%$ 。所以证明了I-DIMM 得到的 ${ \varGamma } _ { 0 }$ 值比传统DIMM法得到的更加精确。

# 3.2方形子孔径误差模拟

本文3.1节证明了改用I-DIMM计算公式，可以提高 ${ \varGamma } _ { 0 }$ 计算值的计算精度，但是，传统DIMM采用的公式是在1990年提出的，由于当时计算能力有限，再加上主要应用于圆形子孔径，与本文模拟时的方形孔径有差别，必然导致一定的计算偏差。尽管在第3部分论证了与I-DIMM公式误差仅仅在 $2 \%$ 左右，完全可以忽略。但是，为了排除 Sarazin 和Roddier 为欧洲南方天文台DIMM中提出的针对圆形子孔径计算公式带来的误差，进一步验证运用I-DIMM对计算精度的影响，对两种方法中的 $\varGamma _ { 0 }$ 计算均采用I-DIMM的计算公式，不同的是，模拟孔径间距为 $2 0 \mathrm { c m }$ 的传统DIMM计算时只处理孔径1和6的像差分信息，而在模拟I-DIMM时，如图4，I-DIMM系统的微透镜阵列在直径方向上最多可以提供4组孔径间距为 $2 0 \mathrm { c m }$ 的像差分信息，所以为计算 $\boldsymbol { { r } } _ { 0 }$ 值提供了更多组数。以一次模拟 2000 幅点扩散函数图像计算 $\boldsymbol { r _ { 0 } }$ 为例，I-DIMM 相当于处理8000幅点扩散函数图像，是DIMM处理像差分信息量的4倍。图13 给出了对 20 次模拟，每次模拟 2000 幅图像得到总 $\boldsymbol { { r } } _ { 0 }$ 平均值的结果：

# 表5总 $\boldsymbol { r _ { 0 } }$ 平均值

Table 5The average results of total ro   

<html><body><table><tr><td>方法</td><td>I-DIMM</td><td>DIMM</td></tr><tr><td>点扩散函数图像数/次</td><td>2000</td><td>2000</td></tr><tr><td>模拟次数</td><td>20</td><td>20</td></tr><tr><td>计算总r。平均值</td><td>0.1017</td><td>0.1019</td></tr></table></body></html>

如表5，I-DIMM 计算总 $\boldsymbol { \mathscr { r } } _ { 0 }$ 平均值为0.1017，误差为 $1 . 7 \%$ ，比只处理一组信息的DIMM法计算误差 $1 . 9 \%$ 更加精确，所以，在处理相同数量图像时，I-DIMM计算更多的子孔径像偏移信息，计算值也比DIMM更精确。

# 3.3 子孔径间距比 $S \le 3$ 时I-DIMM与DIMM对比模拟

根据文[1]的理论，使用DIMM时要求 $S \geq 2$ ，而实际的望远镜未必一定满足这一条件，比如，美国的 NOAO 和欧洲南方天文台的选址[3，也刚刚达到 $S = 2$ ，再比如，台湾的选址[3]， $S = 1 . 6$ 。实际上，当 $S$ 越小 $\left( S \le 3 \right)$ ，望远镜口径也能随之越小，更便于选址作业。为了评估 $S$ 较小情况下 I-DIMM 测量 $\boldsymbol { r _ { 0 } }$ 值的精确程度，本文详细分析了 $S$ 较小（20 $( S \le 3 )$ 时的情况。图10与图11分别给出了 $S$ 较小时100次模拟 $\boldsymbol { { r } } _ { 0 }$ 计算平均值。

![](images/1984d88475bec05dacc7b3d99412f9352b47897de08e1d49bfa1c8d9655cb1d4.jpg)  
图100.36m望远镜 $ { L }$ 方向 $\boldsymbol { { r } } _ { 0 }$ 计算结果

![](images/14eef0915ef5965aa6807118150dc7232c39ffdf855aef7e06ea1092b505e16c.jpg)  
Fig. 10 Results of $\boldsymbol { { r } } _ { 0 }$ （204 in longitude via $0 . 3 6 \mathrm { m }$ telescope   
图110.36m望远镜 $T$ 方向 $\boldsymbol { { r } } _ { 0 }$ 计算结果  
Fig.11 Results of $\boldsymbol { { r } } _ { 0 }$ in transverse via $0 . 3 6 \mathrm { m }$ telescope

如图10，在 $L$ 方向上，I-DIMM法求得的 $\varGamma _ { 0 }$ 值均小于DIMM法所求值，且距离 $\varGamma _ { 0 }$ 设置值的基准线更近，说明I-DIMM法求得的 $\boldsymbol { { r } } _ { 0 }$ 值更精确。实际数值上，当 $S = 1 , 2 , 3$ 时，

I-DIMM计算 $\boldsymbol { { r } } _ { 0 }$ 值分别为 $0 . 1 1 6 4 \mathrm { m } , 0 . 1 0 3 1 \mathrm { m }$ 和 $0 . 1 0 0 7 \mathrm { m }$ ，误差分别为 $1 6 , 4 \% , 3 . 1 \%$ 和 $0 . 7 \%$ 均小于DIMM计算 $\boldsymbol { { r } } _ { 0 }$ 值误差 $2 4 . 1 \%$ ， $4 . 9 \%$ 和 $1 . 9 \%$ 。在 $T$ 方向上，当 $S = 2 , 3$ 时，I-DIMM法计算 $\boldsymbol { { r } } _ { 0 }$ 值为0.1046m和 $0 . 1 0 1 9 \mathrm { m }$ ，误差 $4 . 6 \%$ 和 $1 . 9 \%$ ,均小于DIMM法误差值 $5 . 6 \%$ 和 $3 . 5 \%$ 且I-DIMM曲线距离 $\varGamma _ { 0 }$ 设置值的基准线更近，证明了I-DIMM法计算 $\varGamma _ { 0 }$ 值在 $T$ 方向同样更为精确。由于 $\varGamma _ { 0 }$ 与 $\boldsymbol { I } _ { ( I - D I M M , D I M M ) }$ 的单调性一致，当 $\boldsymbol { I } _ { \boldsymbol { I } - \boldsymbol { D } \boldsymbol { I } \boldsymbol { M } \boldsymbol { M } }$ 大于 $\boldsymbol { I } _ { D I M M }$ 时，I-DIMM 的 $\varGamma _ { 0 }$ 计算值也大于 DIMM，如图6，当 $S < 1 . 6$ 时， $I _ { \mathit { I - D I M M } } \ > \ I _ { \mathit { D I M M } }$ ，所以当 $S \ = 1$ 时，I-DIMM法计算值大于DIMM 法所求的 $\varGamma _ { 0 }$ 值，偏离基准线也更远。图12 给出的 100次模拟总 $\boldsymbol { { r } } _ { 0 }$ 值的平均值，同样印证了上述结论。

![](images/579526675e13a37cad75859d51c9cdcfb6a748acf1b499d59ecd9e4cafd60747.jpg)  
图 $1 2 \ 0 . 3 6 \mathrm { m }$ 望远镜总 $\boldsymbol { r } _ { 0 }$ 计算结果  
Fig.12 Results of Total $\boldsymbol { { r } } _ { 0 }$ via $0 . 3 6 \mathrm { m }$ telescope

# 40.12m口径望远镜I-DIMM的模拟

在软件YAO上，设置望远镜口径为 $1 2 \mathsf { c m }$ ，子孔径直径 $4 0 m$ ，子孔径间距 $8 0 m$ ，即 $S = 2$ ，初始 $\boldsymbol { { r } } _ { 0 }$ 设置值 $0 . 0 3 m$ ( $s t d = 0 . 0 3$ )，具体参数如表6。

表6YAO 参数设置Table 6 Software YAO setup parameters  

<html><body><table><tr><td>YAO 参数设置</td><td></td></tr><tr><td>望远镜口径</td><td>0.12m</td></tr><tr><td>子孔径口径D</td><td></td></tr></table></body></html>

[在此处键入]

<html><body><table><tr><td>间距d</td><td>0.04m</td></tr><tr><td>S=d/D</td><td>0.08m</td></tr><tr><td>子孔径像元角尺寸</td><td>2</td></tr><tr><td>工作波长</td><td>1.3"× 1.3"</td></tr><tr><td>曝光时间</td><td>500nm</td></tr><tr><td>点扩散函数图像</td><td>10ms</td></tr><tr><td>初始设置总ro值</td><td>2000幅</td></tr><tr><td></td><td>0.03m</td></tr></table></body></html>

运用差分像运动法结合式(20)(21)，图13给出了 $L$ 和 $T$ 两个方向上20 次模拟求得的 $\boldsymbol { r _ { 0 } }$ 计算平均值.

![](images/3fbc795a88a5100ecab6c2744175ed659a92898322a6e5419bd757d97e2efc27.jpg)  
图13 $0 . 1 2 \mathrm { { m } }$ 望远镜 $\boldsymbol { { r } } _ { 0 }$ 计算结果  
Fig.13 Results of $\boldsymbol { { r } } _ { 0 }$ via $0 . 1 2 \mathrm { m }$ telescope

如图13，当 $S = 2$ 时，无论在 $L$ 方向或是 $T$ 方向，本文所用I-DIMM法求得 $\varGamma _ { 0 }$ 值都更接近 $\varGamma _ { 0 }$ 设置值 $0 . 0 3 \mathrm { m }$ 的基准线，说明计算结果更精确。计算值分别为 $0 . 0 3 2 6 \mathrm { m }$ 和 $0 . 0 3 0 3 \mathrm { m }$ 与设置值的误差为 $8 . 6 \%$ 和 $0 . 9 \%$ ，低于DIMM法所得计算值误差 $1 0 . 5 \%$ 和 $1 . 8 \%$ 。I-DIMM计算得总的 $\boldsymbol { r _ { 0 } }$ 值为 $0 . 0 3 1 4 \mathrm { { m } }$ ，误差 $4 . 7 \%$ ，小于DIMM的误差值 $6 . 1 \%$ 。这表明小口径望远镜，子孔径间距分离比 $S$ 尽管很小，但I-DIMM法求得的总 $\varGamma _ { 0 }$ 值比DIMM更精确。

# 5结语

[在此处键入]

本文介绍了差分像运动视宁度优化监测法（I-DIMM)，在小口径望远镜上，选取一定间距的两个子孔径组合即可计算得到大气视宁度参数 $\boldsymbol { r _ { 0 } }$ 值。本文通过和传统DIMM对比，在计算公式方面，不但证明了I-DIMM法应用的计算公式在孔径间距为 $2 0 \mathrm { c m }$ 时计算 $\boldsymbol { r _ { 0 } }$ 值比DIMM的公式更精确，而且还证明了在孔径间距很小的情况下I-DIMM得到的 $\boldsymbol { { r } } _ { 0 }$ 值同样比DIMM更精确，尤其当孔径分离比在1.6口3之间时，无论在沿子孔径中心连线方向还是垂直于子孔径中心连线方向，I-DIMM法计算得到的 $\varGamma _ { 0 }$ 值都比DIMM精确，最大误差在 $5 \%$ 左右。在子孔径组合方面，当星像图像数量相同，孔径间距固定时，I-DIMM 处理一张图像子孔径信息的组合数大于或等于1，大多数情况下比DIMM处理一张图像只能得到一组子孔径星像偏移信息要多，从而进一步提高了 $\boldsymbol { { r } } _ { 0 }$ 计算精度。

本文又通过模拟 $0 . 1 2 \mathrm { { m } }$ 口径望远镜，在孔径分离比为2的视宁度测量情况，进一步验证了I-DIMM 法计算 $\boldsymbol { r _ { 0 } }$ 值比DIMM更精确。这就为使用更小口径望远镜提供了证据。同时，I-DIMM，只需小口径望远镜上的部分孔径组合，即可求得精确的大气视宁度参数 $\boldsymbol { r _ { 0 } }$ ，极大地简化了仪器设备，更利于开放环境下便携的大气视宁度测量和选址作业。

# 参考文献

[1]SARAZIN M, RODDIER F.The Eso Differential Image Motion Monitor [J].Astron Astrophys,1990, 227(1): 294-300.   
[2]VERNIN J, MUNOZTUNON C. Optical Seeing at La-Palma-Observatory .1.General-Guidelines and Preliminary-Results at the Nordic Optical Telescope [J]. Astron Astrophys,1992, 257(2): 811-6. [3]谭徽松，岑学奋，钱铜铃．用 DIMM 测视宁度的几个问题 [J].云南天文台台刊，2002,01): 38-46.   
[4]岑学奋，钱铜铃，王建成,etal．高美古的大气视宁度[J]．云南天文台台刊,2002,04):45-50. [5]REN D Q, ZHAO G, ZHANG X,et al. Multiple-Aperture-Based Solar Seeing Profiler[J]. Publ Astron Soc Pac, 2015,127(955): 870-9.   
[6]FRIED D L. Differential Angle of Arrival - Theory, Evaluation,and Measurement Feasibility [J]. Radio Sci,1975,10(1): 71-6.   
[7]SCHARMER G B, VAN WERKHOVEN TIM.S-DIMM plus height characterization of day-time seeing using solar granulation [J]. Astron Astrophys,2010,513(   
[8]TOKOVININA,KORNILOVV. Accurate seing measurements with MASS and DIMM[J].MonNotR Astron Soc,2007,81(3): 1179-89.   
[9] TOKOVININ A.From diffrential image motion to seeing [J].Publ Astron Soc Pac,2002,114(800):1156-66.   
[10]岑学奋，许骏，钱铜铃．云南天文台 DIMM 的视宁度测量和评估 [J].云南天文台台刊,1996,S1):73-80.Cen Xuefen, Xu Jun, QianTongling.Seing MeasurementandEvaluationwiththeDIMMattheYunnanObservatory，[J].PublicationsofThe Yunnan Obsevatory, 1996,S1): 73-80.   
[11]辛玉新，范玉峰，伦宝利．等．长期视宁度监测 DIMM 系统设计方案[J].天文研究与技术,2012,04):397-404.Xin Yuxin,Fan Yufeng,LunBaolietlAesignofsteforLong-Tereingeasurement[J]stronomicalesearch&chology2 04):397-404.   
[12]陈华林，裴冲，袁祥岩，等．差分图像运动监测仪的数值模拟与对比实验研究[J].光子学报，2014,12):62-7.Chen Hualin, PeiChong,YuanXiangyan,etal.ResearchofNumericalSimulationandComparisonofExperimentfromDiferentialImageMotion Monitor [J].Acta Photonica Sinica,2014,12): 62-7.   
[13]钱铜铃，许骏，岑学奋．两套 DIMM 系统的比对观测及结果分析 [J].云南天文台台刊,1996,04):62-8.Qian Tongling, Xujun, Cen Xuefen.TheComparisonofTwo SetsofThreeAperture DIMMandItsResult Analysis[J].PublicationsofTheYunnanObsevatory

[在此处键入]

1996,04): 62-8.   
[14]WANGLQ,SCHOCK M,CHANAN G,et al.High accuracyDIMM measurements for the TMT site testing program-art.no.   
62671S [J].Ground-based and Airborme Telescopes,Pts 1 and 2,2006,6267(S2671-S.   
[15]BECKERSJM.Aseeing monitor forsolarandother extendedbjectobservations [J].ExpAstron,2Oo1,12(1):1-20.

# Improved to Differential lmage Motion Monitor

Wang Ziyuel,3,Ren Deqing2.3 1(Nanjing Instituteof Astronomical Optics & Technology,Chinese Academyof Sciences,Nanjing 210042，China) 2(Physics &AstronomyDepartment,California StateUniversityNorthridge,Northridge,California9133O-8268,USA

Abstract: The atmospheric seeing is an important index to measure the atmospheric optical quality of the site. The Diferential Image Motion Monitor (DIMM) is widely used for site testing at home and abroad.For example,ESO DIMM was implied in site testing for Europe Southern Observatory. This paper introduced an excellent method of seeing measurement: Improved to Differential Image Motion Monitor (I-DIMM). Firstly, the structure design of I-DIMM and seeing calculation method were described in details. After that, followed by setting the two telescopes, of which one's diameter is $0 . 3 6 \mathrm { m }$ and the other is $0 . 1 2 \mathrm { m }$ ，this paper compared the calculated values of seeing in these two situations. Both results showed that calculating seing by method I-DIMM was more accurate than DIMM. Finally，this paper analyzed both simulation results and introduced the advantages of I-DIMM compared to DIMM.

Keywords: I-DIMM; atmospheric seeing; site; DIMM