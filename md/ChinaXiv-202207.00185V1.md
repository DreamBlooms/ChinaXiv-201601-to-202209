# 加速器中的相运动

朱雄伟中国科学院高能物理研究所

# Abstract

加速器中带电粒子的运动分为横向运动与纵向运动，加速器中的纵向运动即为相运动，给出了一维近似下的相运动方程，相运动的稳定性物理机制和相位条件。给出了一个纵向运动的标准映射，可用于非线性动力学研究。模拟研究了二台S波段电子直线加速器，验证了相运动的基本理论，模拟结果与基本理论一致，吻合的很好。提出了在常规直流高压电子枪的电子直线加速器中，直接将直流高压电子枪更换成光阴极微波电子枪，并使用束团压缩器的实验研究方案，同样可以获得高峰值电流的短电子束团。

Keywords:束流动力学，纵向运动，加速器

# 1 引言

加速器学科是一门运用电磁场加速带电粒子的学科[1,2,3,4]，研究的是带电粒子与电磁场的相互作用。粒子加速器自发明诞生以来，走过了百年的风雨历程，为世界科技的进步作出了贡献。加速器科学的发展伴随着技术的进步，加速器科学与技术的发展使得加速器成为一个多学科的研究平台。基于加速器研究平台的学科有：高能物理、同步辐射光源、自由电子激光、散裂中子源、洁净核能源、稀有同位素等。粒子加速器在科技发展和国民经济发展中都得到了广泛的应用，成为科学技术发展的一个重要的方向。现代加速器集众多的高精尖技术于一体，加速器技术主要涉及带电粒子的产生与传输技术（粒子源技术）、高功率微波的产生与传输技术、磁铁技术、低温技术、电源技术、真空技术、束流测量技术、束流控制技术等。

十九世纪麦克斯韦总结了电磁理论，形成了麦克斯韦方程组，它是电磁场的理论基础。带电粒子（电量为 $q$ )在电磁场 $( E , B )$ 中感受到洛伦兹力 $\boldsymbol { F } = q ( \boldsymbol { E } + \boldsymbol { v } \times \boldsymbol { B } )$ ，因此带电粒子的能量改变为 $\begin{array} { r } { \frac { d W } { d t } = q E \cdot v } \end{array}$ ．从上式来看，带电粒子与电场有能量交换，而与磁场没有直接的能量交换。静电场与时变场（射频电场）都能用来加速带电粒子，这对应于静电加速器与射频加速器。在静电加速器中没有什么相运动。而在射频加速器中由于存在纵向电场方向的改变，所以存在相运动（纵向运动），从而保持带电粒子与射频电场之间的同步，得到稳定的加速。

![](images/405c2caff440107b9d8cb020d0babb5e39348ab87118ad0d400ddaac375ecb9e.jpg)  
图1.电子直线加速器的典型结构示意图

上图给出了电子直线加速器的典型结构示意图，它的主要组成部分有：注入器或预注入器、加速结构、磁铁、低电平系统、高电平系统、束测单元、控制系统、电源、功率源等[5,6,7,8,9]，而束流输送系统(BDS)将电子束团运送到实验站或实验用户。相运动主要存在于注入器或预注入器中，电子束团经过相运动形成占据一定相宽的束团区(bucket)，形成具有宏脉冲、微脉冲结构的电子束团。

# 2 相运动的基本理论

在一维近似下，假定纵向电场分量为 $E _ { z } = E s i n ( \omega t - k z + \Delta \varphi )$ 那么纵向运动方程为

$$
\begin{array} { c c c } { \displaystyle { \frac { d { \gamma } } { d z } = \frac { q E } { m c ^ { 2 } } s i n ( \varphi ) } } \\ { \displaystyle { \frac { d \varphi } { d z } = \frac { \omega } { c } ( \frac { 1 } { \beta } - \frac { 1 } { \beta _ { p } } ) } } \end{array}
$$

式中 $\gamma$ 为相对论因子， $m$ 为对带电粒子的质量， $\scriptstyle { c }$ 为光速， $\varphi = \omega t - k z + \Delta \varphi$ 为带电粒子在电场中感受到的相位， $\begin{array} { r } { \beta = \frac { v } { c } } \end{array}$ 为带电粒子的速度, $\begin{array} { r } { \beta _ { p } = \frac { v _ { p } } { c } } \end{array}$ 为电场的相速。在慢波加速结构中，电磁场的相速 $\beta _ { p } \leq 1$ ，而电子速度 $\beta < 1$ ．在直线加速器的开始部分， $\beta \ll 1 , \beta < \beta _ { p }$ ，一方面需要加速电子，另一方面需要对非聚束电子束团完成聚束，形成占据一定相宽的稳定的束团。而当电子速度与相速近似相等时，或者说电子速度达到了光速时， $\beta \simeq \beta _ { p } \simeq 1$ ，相运动可近似为冻结了，即不再有相运动。电子直线加速器注入器的基本组成结构如下图

![](images/786fdf3f2dbf440826993748cb17984348e310319265cb1c6e0e539554744ec5.jpg)  
图2.电子直线加速器注入器的典型结构

电子直线加速器主要由电子枪，聚束段，光速段所组成。在聚束段， $\beta < 1$ ，而在光速段， $\beta \simeq 1$ ．相运动在聚束段中完成，在光速段近似没有相运动。聚束段由次谐波聚束器，预聚束器，聚束器所组成。在相空间 $( \gamma , \varphi )$ 中，假定束团中有参考粒子 $( \gamma _ { s } , \varphi _ { s } )$ ，束团中粒子围绕参考粒子运动，设 $\Delta \gamma = \gamma - \gamma _ { s } , \Delta \varphi = \varphi - \varphi _ { s }$ ，可以求得关于 $\Delta \varphi$ 的近似方程

$$
\frac { d ^ { 2 } \Delta \varphi } { d z ^ { 2 } } + \frac { q E \omega c o s ( \varphi _ { s } ) } { m c ^ { 3 } } \frac { 1 } { ( \gamma _ { s } ^ { 2 } - 1 ) ^ { 3 / 2 } } \Delta \varphi = 0 .
$$

上式近似为二阶微分方程，当 $0 < c o s ( \varphi _ { s } ) < 1$ 时，有稳定的振荡解，粒子围绕参考粒子作稳定的振荡运动。在区间 $[ 0 , 2 \pi ]$ 内，如果 $\varphi _ { s }$ 在 $[ 0 , \frac { \pi } { 2 } ]$ ， $[ \frac { 3 \pi } { 2 } , 2 \pi ]$ 内，那么束团能够实现稳定的加速，这就是相运动稳定性的物理机制。

![](images/9d5fe1b43ac4f7315dd03cc48fe135681fbe394c3117048d035646289c6b6bfa.jpg)  
图3.稳定区间图

一般来说，预聚束器，聚束器工作在加速器的射频工作频率上，射频加速器的工作频率取决于功率源的频率，常用的功率源是速调管。而次谐波聚束器工作在工作频率的分频上。电子束团尾部的粒子加速比头部的粒子快，这样尾部的电子能追上头部的电子到达电子束的头部，而头部的电子因为加速慢落后到束团尾部，然后束团尾部的电子又运动到束团头部，束团头部的粒子又运动到束团尾部，围绕参考粒子循环往复的振荡运动。见下图，束团头部在 $z < 0$ 方向。很显然，头部粒子感受的加速电场比尾部粒子所感受的加速电场小。

![](images/5b26f6d4755760474f25b52269c438731f596b0cb67a0827aee79634521e2592.jpg)  
图4.射频场中的束团加速

轴对称射频直线加速器中的 $T M$ 模式普遍的电磁场可表达为

$$
\begin{array} { r } { E _ { z } = E _ { 0 } \displaystyle \sum _ { n = - \infty } ^ { + \infty } b _ { n } c o s ( \omega t - k _ { n } z ) , } \\ { E _ { r } = - \displaystyle \frac { r } { 2 } \frac { \partial E _ { z } } { \partial z } , } \\ { B _ { \theta } = \displaystyle \frac { r } { 2 c ^ { 2 } } \frac { \partial E _ { z } } { \partial t } . } \end{array}
$$

式中 $\begin{array} { r } { k _ { n } = k _ { 0 } + n \frac { 2 \pi } { D } } \end{array}$ ， $D$ 是加速结构的周期长度， $k _ { 0 }$ 为加速场基模的波数。那么纵向运动方程可表达为

$$
\begin{array} { r } { \displaystyle \frac { d \gamma } { d z } = \frac { q E _ { 0 } } { m c ^ { 2 } } \sum _ { n = - \infty } ^ { + \infty } b _ { n } c o s ( \Delta \varphi - \frac { 2 \pi n } { D } z ) , } \\ { \displaystyle \frac { d \Delta \varphi } { d z } = k _ { 0 } ( \frac { \gamma } { ( \gamma ^ { 2 } - 1 ) ^ { 1 / 2 } } - 1 ) . } \end{array}
$$

假定 $\gamma _ { n } = \gamma ( n D ) , \Delta \varphi _ { n } = \Delta \varphi ( n D ) , b _ { 0 } = b _ { n } = 1 _ { : }$ ，可的如下的标准映射

$$
\begin{array} { r } { \gamma _ { n + 1 } = \gamma _ { n } + \frac { q E _ { 0 } D } { m c ^ { 2 } } c o s ( \Delta \varphi _ { n } ) , } \\ { \Delta \varphi _ { n + 1 } = \Delta \varphi _ { n } + k _ { 0 } D ( \frac { \gamma _ { n } } { ( \gamma _ { n } ^ { 2 } - 1 ) ^ { 1 / 2 } } - 1 ) . } \end{array}
$$

以上映射为一类非线性标准映射[12,13]，可用于纵向运动的非线性动力学的研究。．

# 3 相运动理论的具体应用

射频电子直线加速器的加速电场是随时间交变的，那么电子也有可能被减速。为了得到有效的加速，必须实现电子和射频电场的同步，以达到共振加速的目的。按照加速方式划分，可以分为行波加速和驻波加速。按照加速结构划分，加速器可分为盘荷波导结构、边耦合驻波结构、轴耦合驻波结构等，加速结构可以是单周期、双周期、三周期等。电子直线加速器的工作频率有L波段 $1 3 0 0 M H z$ 、S波段 $2 8 5 6 M H z$ 、C波段 $5 7 1 2 M H z$ 、X波段 $1 1 . 4 2 4 G H z$ 、W波段 $9 1 . 3 9 2 G H z$ 。在电子直线加速器中，电子很容易达到相对论状态，基本采用光速加速结构。所以我们以二台S波段 $2 8 5 6 M H z$ 电子直线加速器作为研究例子来分析讨论相运动理论的具体应用[14,15,16]。

以一台 $S - B a n d 2 8 5 6 ~ \mathrm { M H z }$ 电子直线加速器为例分析直线加速器中相运动理论的具体应用研究。北京正负电子对撞机(BEPC)的直线加速器能提供正电子、负电子输运到环形加速器中进行正负电子对撞产生 $J / \psi$ 能区的高能粒子。BEPC电子直线加速器在第四节加速结构后有产生正电子的钨靶，如果钨靶放下，第四节加速结构出口的电子束团(能量约为 $2 4 0 M e V$ )将打在钨靶上，从而产生正电子，这些正电子经过冷却、聚束聚焦俘获等处理形成正电子束团，正电子束团再加速到直线加速器出口提供正电子束团。如果钨靶没有放下，第四节加速结构出口的电子束团将一直加速到直线加速器出口提供电子束团。BEPC电子直线加速器采用 $S - B a n d 2 8 5 6 ~ \mathrm { M H z }$ 加速结构，电子枪采用常规直流高压电子枪。如下图

![](images/a549d7389a65e5369c8d143fd1edf7a8196a993ecd033f88552e4f4bfcbe1d30.jpg)  
图5.直线加速器预注入器

最早的BEPC直线加速器电子枪产生的电子束团电量为 $1 n C$ ，束团长度为1ns．为了提高正电子的产生电流，可提高打靶的电子电流，可更换电子枪将电子束的电量提高到 $1 0 n C$ 。上图中的PB为预聚束器，Buncher 为聚束器，Accelerating structure为SLAC$\mathrm { 3 m }$ 长加速管，工作频率为 $2 8 5 6 ~ \mathrm { M H z }$ 。束团长度为1ns占据三个射频相区(bucket)的电子束团，经过预聚束器、聚束器后将形成三个相区，形成三个束团。为提高正电子产生电流，在预注入器中增加次谐波聚束器，将束团长度为 $1 n s$ 的电子束团聚束到一个相区，形成一个电子束团，提高了打靶的电子束团流强。最早的预注入器由电子枪、单腔 $\pi$ 模予聚束器、四腔 $2 \pi / 3$ 模的聚束器、SLAC $\mathrm { 3 m }$ 长 $2 \pi / 3$ 模加速管A0所组成，用Superfish计算予聚束器、聚束器主要参数如下：

表1、予聚束器主要参数  

<html><body><table><tr><td>工作模式</td><td>T</td></tr><tr><td>工作频率MHz</td><td>2856</td></tr><tr><td>分路阻抗MΩ/m</td><td>7.35</td></tr><tr><td>品质因数</td><td>7315</td></tr></table></body></html>

表2、聚束器主要参数  

<html><body><table><tr><td>工作模式</td><td>2π/3</td></tr><tr><td>工作频率MHz</td><td>2856</td></tr><tr><td>分路阻抗MΩ/m</td><td>53</td></tr><tr><td>品质因数</td><td>11000</td></tr><tr><td>相速</td><td>0.75c</td></tr></table></body></html>

最早的BEPC电子枪可提供 $8 0 K e V , 2 . 5 n s , 5 A$ 的脉冲电子束，为了提高正电子流强，改进后的电子枪将产生1ns, $1 0 n C$ 脉冲电子束团，能量 $1 2 0 - 2 0 0 K e V$ ，我们分别模拟了电子能量120,150.200KeV情形下预注入器的束流动力学。螺旋管线圈纵向聚焦磁场分布如下图

![](images/c836ee202c7ddf7a0bb33fbe63b1fddfe517a12448a9900d21e13c9d2935ec2f.jpg)  
图6.线圈磁场分布图

1ns、10nC脉冲电子束团经过预注入器后形成三个束团，见下图

![](images/bce8d82608e54fd618a3ca4e513a7b056fea5e4341bc91f85298a68dafce486f.jpg)  
图7.A0出口的电子束能谱与相谱

次谐波聚束器（SHB）是实现单束团运行的一项发展技术，它工作在主要工作频率的分频上。如果在BEPC聚束系统中加入次谐波聚束器，则 $1 n s$ 长的电子束团可以压缩到一个束团，且具有较高的电流密度，这样，电子打靶产生的正电子也将具有一个短束长和较高的电流密度，保证了束流品质，从而提高储存环正电子的注入速率。另外由于产生短的正电子束长远小于环接收度（约1ns)，降低了对注入时间晃动的要求，因而有利于正电子的注入。因此，在BEPC聚束系统上开展次谐波聚束器的研究，实现BEPC直线加速器的单束团运行具有重要意义。引入次谐波聚束器（SHB）的一种方案是在现有聚束系统中加入一个次谐波聚束器，保留原有聚束系统，如图二。考虑功率源要求，可取次谐波聚束器工作频率为476MHz，作为简单模拟计算，将其近似为理想间隙，电子经过SHB后能量增益。再次模拟1ns、 $\mathrm { 1 0 n C }$ 的束流动力学，在A0出口处其形成为一个束团，见下图

![](images/fca63b2876142abd552b8439cca8ca9dc934a1d5d3b98edf93e7645b2fb47788.jpg)  
图8.A0出口的电子束能谱与相谱(SHB)

我们采用PARMELA进行束流动力学模拟[10,11]，图七、图八非常形象、清晰的演示了电子直线加速器注入器中的相运动，与相运动的基本理论吻合的很好。

对于采用光阴极电子枪的情形，枪出口的电子束已经达到了相对论情形。如果后面接上光速段的加速结构，那么纵向相运动将近似冻结，也就是说没有相运动了。但如果后面接上的加速结构相速小于1，将仍然存在相运动。这种情况也是可能存在的。如果过去的采用直流高压电子枪、带聚束段的加速器将直流高压电子枪换成光阴极微波电子枪就是这种情况。如下图就是一个例子。

![](images/7e17178136335b73492d094d351ac899c756ab00043e5495a5f40470f467c150.jpg)  
图9.光阴极注入器

我们模拟研究了一台用作激光电子相互作用的S-band亚皮秒束团的产生装置。该装置由BNL型S-band光阴极电子枪、2856MHz加速结构、螺旋管、聚焦线圈、束团压缩器Chicane所组成。束团压缩技术广泛应用在自由电子激光装置与直线对撞机中，通过束团压缩获得高峰值电流的短束团。压缩通常采用磁压缩技术，压缩由加速段与磁压缩器所构成，在加速段，加速相位不处于峰值加速相位，因而束团经过加速段时会产生依赖于束团位置的相干能散，而能量不同的粒子经过磁压缩器时会产生路程差，从而束团得到压缩。早期低增益自由电子激光振荡器驱动加速器常采用 $\alpha$ 磁铁压缩技术，现在自由电子激光驱动器一般采用由四块二极铁组成的chicane来完成束团压缩。

加速管原与直流电子枪匹配，后电子枪换为光阴极微波电子枪。头十个cell为变相速区。前四个腔相速为 $\beta _ { p } = 0 . 7 7 5$ ，接下来的三个腔相速为 $\beta _ { p } = 0 . 9 4 6$ ，变相速区的最后三个腔相速为 ${ \bf \nabla } \beta _ { p } = 0 . 9 9$ 。变相速区之后由51个光速腔所组成。由于光阴极电子枪与加速管之间不匹配，束团过变相速区时会存在一定的滑相运动。光阴极微波电子枪的主要参数如下表

表3、光阴极微波电子枪的主要参数  

<html><body><table><tr><td>阴极材料 阴极半径 量子效率 阴极表面峰值场强 枪出口电子束能量 电子束电量 能散 微波频率 电子束重复频率 微波脉冲长度 微波峰值功率</td><td>Cu(或Mg) 1.0mm > 10-5at266nm 100MV/m 5MeV 100 －1000pC 0.2%rms 2856MHz 10H z 3μs</td></tr></table></body></html>

加速结构由61个cell所组成，工作在模式，加速管主要参数见下表，

# 表4、加速结构主要参数

<html><body><table><tr><td>工作频率</td><td>2856MHz</td></tr><tr><td>工作模式</td><td>2π/3</td></tr><tr><td>场分布</td><td>等梯度</td></tr><tr><td>长度</td><td>2.09m</td></tr><tr><td>腔数</td><td>61</td></tr><tr><td>品质因子</td><td>11000</td></tr><tr><td>分路阻抗</td><td>57MΩ/m</td></tr><tr><td>衰减常数</td><td>0.57dB</td></tr><tr><td>群速</td><td></td></tr><tr><td>填充时间</td><td>0.02c - 0.03c 0.55μs</td></tr></table></body></html>

束团压缩器有四块相同的二极铁所组成，chicane的主要参数如下

表5.chicane主要参数  

<html><body><table><tr><td>参数 电子束团能量</td><td>数值 15.46</td><td>单位 MeV</td></tr><tr><td>电子束团能散</td><td>8.8</td><td>%</td></tr><tr><td>束团长度压缩比</td><td>10</td><td></td></tr><tr><td>R56</td><td>-13</td><td>mm</td></tr><tr><td>总长</td><td>1.04</td><td>m</td></tr><tr><td>头两块磁铁间长度</td><td></td><td></td></tr><tr><td>中间两块磁铁间长度</td><td>0.194</td><td>m</td></tr><tr><td></td><td>0.19</td><td>m</td></tr><tr><td>二极磁铁长度</td><td>11.6</td><td>cm</td></tr><tr><td>磁铁偏转角</td><td>10</td><td>0</td></tr><tr><td>CSR发射度增长</td><td>40</td><td>%</td></tr></table></body></html>

我们用PARMELA模拟研究该装置。PARMELA是一个多粒子PIC程序，它考虑了空间电荷效应，得到了业界的认可。所用版本的PARMELA程序没有考虑到相干同步辐射效应（CSR），所以其所得到的发射度增长效应较实际小。模拟中我们考虑了边缘场效应。模拟中的激光参数为波长266nm、脉冲长度 $1 0 p s$ 、脉冲能量 $2 0 \mu J$

![](images/c1c1ec9d621d4b686f56dbd18d88019855860c5b4068df18a2ba3c04170c2e69.jpg)  
图10.亚皮秒输出束团

从这个例子可以看出，如果将使用常规直流高压电子枪的电子直线加速器的电子枪更换成光阴极电子枪，而且在随后的加速器上安装束团压缩器chicane,也可以获得高峰值电流的很短的电子束团，满足实验用户的使用要求。

# 4讨论

加速器的种类繁多，一般有电子加速器、质子加速器、重离子加速器。本文所讨论电子直线加速器的相运动基本理论同样适用于质子直线加速器、离子直线加速器，只不过具体的表现形式不大相同。而环形加速器中影响纵向运动的因素除了射频加速曲率效应，还有磁铁的色散效应。并且带电粒子不是单次通过加速，而是反复累积通过加速。所以环形加速器中的束流动力学相对要复杂的多。一般来说，直线加速器主要研究带电粒子在加速结构中的运动，聚焦磁铁很少。环形加速器主要研究带电粒子在磁铁中的运动（二极铁、四极铁、六极铁等），只有一二个或几个加速结构（高频腔），或者说环形加速器基本是磁铁。

# References

[1] T.Wangler, RF linear accelerators,Wiley, New York, 1998.   
[2] P.M.Lapstolle, A.L.Septier, Linear Accelerators, North-Holland, Amsterdam,1970.   
[3] S.Y.Lee, Accelerator Physics.   
[4]M.Reiser, Theory and Design of charged particle beam.   
[5] D.Alesini, Linac, CERN Accelerator School, Introduction to accelerator physics, 2010.   
[6] D.C.Faircloth, Particle Source, CERN Accelerator School, Introduction to accelerator physics, 2010.   
[7] M.Chodorow, et.al.,Stanford High Energy Linear electron Acceleator (Mark II), RSI, 26, 2, 134,1955.   
[8] D.H.Whittum， Introduction to Electrodynamics for microwave Linear accelerators, SLAC-PUB-7802, 1998.   
[9] D.H.Whittum, Introduction to Microwave linacs, SLAC-PUB-026,1998.   
[10] L.Young, PARMELA Manual, 2004.   
[11] J.H.Billen, L.Young, Superfish Manual, 2002.   
[12] Xiongwei Zhu, The effect of high spatial harmonics in RF linac, International journal of infrared and millimeter wave, 25, 4, 667,2004.   
[13] Xiongwei Zhu, The effect of high spatial harmonics on beam dynamic in RF linac, chinaXiv:201801.00003, 2018.   
[14] Xiongwei Zhu, Study on the production of the Subpicosecond electron bunch,arXiv:1301.0703, 2013.   
[15]朱雄伟，超短电子束团的产生研究，chinaXiv.201701.00040,2017.   
[16]朱雄伟，BEPCII直线预注入器束流动力学研究，北京正负电子对撞机运行年 会，2002.

# Phase Motion in Accelerator

Zhu Xiong-Wei Institue of High Energy Physics, Chinese Academy of Sciences

# Abstract

The motion of charged particle can be divided by the longitudinal motion and the transverse motion. The longitudinal motion is the phase motion. Under one dimensional approximation, the longitudinal motion equations are derived, the physical mechanism for the stable phase motion and its related phase condition are given. The one standard map for the longitudinal motion is gotten, this standard map can be used for the nonlinear dynamics study. We simulated two S-Band electron linacs to prove the basic theory of the phase motion. The simulation result agreed the basic theory well. In the common electron linac (with DC electron gun and the bunching section)， We propose to replace the high voltage DC electron gun by the photocathode RF gun directly while preserving the bunching section still to get the high peak current short electron bunch.

Keywords:Beam dynamics, longitudinal motion,accelerator