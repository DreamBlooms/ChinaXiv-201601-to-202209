# 脉冲星PSR $\mathrm { J 1 9 0 6 + 0 7 4 6 }$ 射电辐射束的观测特征及其启示

黄文俊」，黄秀健²，温志刚³，王洪光1.3

（1．广州大学物理与电子工程学院，广东广州510006）（2.华中师范大学物理科学与技术学院，湖北 武汉 430079）（3．中国科学院新疆天文台，新疆乌鲁木齐 830011）

摘要：本文利用公开数据研究了PSRJ $1 9 0 6 \substack { + 0 7 4 6 }$ 的主脉冲和中间脉冲的辐射特征。通过对各段时期的平均脉冲轮廓进行高斯拟合，得到了对应的 $10 \%$ 峰值脉冲宽度和峰值流量密度，进而研究了其与碰撞角之间的关系。结果表明主脉冲辐射束的主要可见部分可由一束有确定磁经度角范围的磁流管产生，而中间脉冲则来自于环绕磁轴的磁力线上的辐射。现有的扇形束模型可以较好的解释主脉冲的特征，但难以解释中间脉冲的辐射特征。中间脉冲的特征要求改进扇形束模型，在假设磁轴四周的磁力线均有辐射的情况下，通过合理选择模型参数来模拟观测到的条形辐射束。

关键词：脉冲星；射电辐射；PSRJ1906+0746；辐射束中图文分类号：P162 文献标志码：A

脉冲星辐射束内的强度分布并不均匀，当视线扫过辐射束时，辐射流量起伏变化，形成一定形状的脉冲轮廓。但若想通过看到的轮廓来反推辐射束的结构，却是非常困难的。研究这一难题的途径有两个，一是根据现象进行合理猜测，建立辐射束唯象模型，从样本统计的角度来检验和修正，二是设法直接观测脉冲星射电辐射束的二维结构。

第一个途径，目前最流行的唯象模型是上世纪80年代Rankin提出的核双锥辐射束模型[1]。该模型是对早期的空心辐射锥模型的改进2]，认为辐射束是由较亮的核心以及外围的两个嵌套的亮环组成。该模型被广泛应用于解释脉冲轮廓的多样性、偏振、子脉冲漂移等现象。

另一个模型是上世纪 80 年代 Michel 提出的扇形辐射束模型[3]，近10 年来，扇形束模型得到了较快发展，并演变出不同的版本[46]。尽管具体物理机制有所不同，这些模型都有一个共同点，即假设粒子在脉冲星磁层的磁流管中运动时产生径向延展的辐射束，形状类似扇形的结构。近年来扇形束模型得到了越来越多观测现象的支持。

在这些扇形束模型中，Wang 等人的工作[5]（以下简称WPZ模型）推导出了辐射束的脉冲宽度和光度公式，并指出扇形束模型和锥辐射束模型的重要差别——扇形束模型预言脉冲轮廓宽度与碰撞角（观测者视线和磁轴之间的最小夹角）之间存在正相关关系，而锥辐射束模型则预言相反的关系。该作者收集了64颗脉冲星的脉冲宽度和碰撞角数据，发现观测数据显示二者之间存在正相关，从而为扇形束模型提供了较强的观测支持。

第二个途径仅适用于极少数位于双星系统中的进动脉冲星，如PSRJ1141-6545[7和 PSR$\mathbf { J 1 9 0 6 + 0 7 4 6 } ^ { [ 8 ] }$ 。由于自转轴的进动效应，观测者的视线能够从辐射束的不同部位扫过，从而可以观测到辐射束的二维结构。PSR $\mathrm { J 1 9 0 6 + 0 7 4 6 }$ 的进动周期大约160年，利用从2005到2018跨越14年的观测数据，Desvignes 等人反演出了该星辐射束的部分结构。结果显示主脉冲和中间脉冲的辐射束均为延展的长条形，既无圆形或椭圆形的亮环，也无磁轴附近的亮斑，完全不同于核双锥模型的辐射束图像，反而更像扇形束模型的图像。PSR $\mathrm { J 1 9 0 6 + 0 7 4 6 }$ 作为目前唯一比较可靠的具有辐射束二维结构信息的脉冲星，其偏振轮廓数据已经由 Desvignes等人发布在科学数据共享网站Zenodo①，但其辐射特征尚未在最近的文献中深入研究。

本文旨在利用开放数据挖掘PSR $\mathrm { J 1 9 0 6 + 0 7 4 6 }$ 的辐射特征，重点比对WPZ扇形束模型的两个核心关系——脉冲宽度与碰撞角以及峰值辐射流量与碰撞角的关系。第1部分介绍了数据处理方法，结果在第2部分给出，第3部分就观测对模型的检验和启示进行讨论，第4部分为结论。

# 1．数据处理

该星的轮廓数据下载自Zenodo,包含从2005年到2018年共47个L波段平均脉冲轮廓。其中，2005-2007 年是 Nancay 射电望远镜的观测数据，2008-2009 年以及 2012-2018 年是Arecibo 射电望远镜的观测数据，2009-2012年无观测数据。除Nancay的观测数据（从MJD53572到MJD 54282）外，其他时段的流量数据均能重复文献[9]的结果，因此在分析流量特征时，我们排除了Nancay 的观测数据。测量脉冲宽度并不需要流量定标的轮廓，因此在分析宽度特征时，我们采用了所有的数据。

在文献[9]中，磁倾角是通过进动旋转矢量模型（PrecessionalRVM）拟合线偏振位置角曲线的拐点相位数据而得到的。主脉冲所在磁极的磁倾角被确定为 $\alpha _ { \mathrm { M P } } { = } 9 9 . 4 1 ^ { \circ } { \pm } 0 . 1 7 ^ { \circ }$ ，中间脉冲磁极的磁倾角 $\alpha _ { \mathrm { I P } }$ 为 $\alpha _ { \mathrm { M P } }$ 的补角。然后固定磁倾角，通过转矢量模型（RVM）拟合主脉冲和中间脉冲的线偏振位置角数据来得出历次观测的碰撞角。本文直接采用了文献[9]支撑材料中表S2的碰撞角结果。有一个特殊情况本文做了处理，即从MJD 56963到57553（2014年11月至 2016 年6月)，因主脉冲信噪比低而得不到碰撞角，主脉冲的碰撞角 $\beta _ { \mathrm { M P } }$ 需要通过中间脉冲磁极的碰撞角 $\beta _ { \tt I P }$ 来估算，公式为

$$
\beta _ { \mathrm { M P } } \approx ( \alpha _ { \mathrm { I P } } + \beta _ { \mathrm { I P } } ) - \alpha _ { \mathrm { M P } } { \it \Delta \phi } \mathrm { ~ \Omega ~ } \mathrm { ~ o ~ }
$$

由于不少观测噪声明显，为了得到轮廓宽度和峰值流量密度，我们采用若干个高斯成分对主脉冲和中间脉冲的平均脉冲轮廓进行了拟合，得到光滑的轮廓后，再测量 $5 0 \%$ 峰值宽度 $W _ { 5 0 }$ 和 $10 \%$ 峰值宽度 $W _ { 1 0 }$ （峰值高度 $50 \%$ 和 $10 \%$ 水平上的宽度）以及峰值流量密度 $f _ { \mathrm { p k } }$ 。有两个例外，一是MJD 57311的主脉冲轮廓因信噪比过低，不利于可靠的测量宽度和流量密度，二是从MJD57553以后主脉冲就观测不到了，所以主脉冲宽度和峰值流量密度最后的有效数据分别为34和25个，中间脉冲对应的有效数据分别为47和38个。

脉冲宽度的误差考虑了两部分的贡献：采样间隔和高斯轮廓测量误差，总误差为二者平方和的算术平方根。所有观测的采样点都是2048，因此采样时间间隔对应的误差为 $0 . 1 8 ^ { \circ }$ 。由于观测都采用了连续消色散的方法，色散引起的误差很小，这里不考虑。轮廓噪声部分辐射流量密度的rms通常在0.1mJy左右,这个值明显低于已发表的L波段平均流量的误差[0],如果采用rms 值作为误差很可能低估了真正的误差，因此本文不处理辐射流量密度的误差。

# 2．结果

# 2.1脉冲宽度与碰撞角的关系

图1给出了主脉冲和中间脉冲的 $W _ { 1 0 }$ 随 $| \beta |$ 变化的结果。如图1（a）所示，主脉冲的脉冲宽度与 $| \beta |$ 呈正相关关系，与WPZ模型的图像定性符合。为了检验是否符合定量关系，我们尝试用WPZ模型的 $W - \beta$ 函数关系来拟合数据。

WPZ 模型区分了辐射束内区和外区，内区大致是从磁轴到 $| \beta | \approx 2 \rho _ { \mathrm { p c } }$ 的地方，即$| \beta | < 2 \rho _ { \mathrm { p c } }$ 的区域， $| \beta | > 2 \rho _ { \mathrm { p c } }$ 为外区。其中极冠区的半张角 $\rho _ { \mathrm { { p c } } }$ 定义为在脉冲星表面极冠区边缘的磁力线切线与磁轴的夹角。假设磁场为静态磁偶极场，则有 $\rho _ { \mathrm { p c } } \approx 1 . 5 R / R _ { \mathrm { e } }$ ，其中 $R$ 为脉冲星半径（设为 $1 0 \mathrm { k m } \dot { }$ ， $R _ { \mathrm { e } }$ 为一根开放磁力线上离脉冲星中心最大的距离， $P$ 为脉冲星自转周期， $c$ 为真空光速。对于PSR $\mathrm { J 1 9 0 6 + 0 7 4 6 }$ ，有 $\scriptstyle P = 0 . 1 4 4 \mathrm { \ s }$ ，利用文献[11]中给出的公式（6)和（7)，在静态磁偶极场情形下可以计算出最外开放磁力线的 $\dot { \rho } _ { \mathrm { { p c } } }$ 最小值约为 $2 . 2 ^ { \circ }$ ，最大值约为 $3 . 3 ^ { \circ ^ { \mathrm { ( 2 ) } } }$ ，平均值约为 $2 . 7 5 ^ { \circ }$ ，因此我们将辐射束内外部分的边界设在 $| \beta | \approx 5 . 5 ^ { \circ }$ ，并在图1中用竖直的虚线表示出来。

WPZ 模型指出内、外区域脉冲轮廓宽度的变化很可能不同。内区不确定性较大，在多个磁流管并存的情况下有可能出现脉冲宽度从磁轴向外递减的情况。外区主要是偶极场磁流管的几何特征起主要作用，导致脉冲宽度W随着 $| \beta |$ 增加而递增，服从如下关系

$$
\begin{array} { r } { \cos \left( \frac { W } { 2 } + C \right) = \frac { \sin \alpha } { \tan ( \alpha + \beta ) ( \cos ^ { 2 } \alpha + \tan ^ { - 2 } \varphi ) ^ { 1 / 2 } } \quad \frac { } { \sin \alpha } } \end{array}
$$

其中 $C = \tan ^ { - 1 } ( s \sec \alpha / \tan \varphi )$ ， $\varphi$ 为磁流管边界的磁力线所具有的磁经度角。为了定义 $\varphi$ ，先取垂直于磁轴与自转轴所在平面的平面为参考面，磁力线平面与该平面的二面角为磁经度角。在主脉冲一极，向下看时 $\varphi$ 从自转方向开始沿顺时针方向递增，而在中间脉冲一极则相反，定为从自转方向开始沿逆时针方向递增。这主要是为了使两极具有相同 $\varphi$ 值的磁力线具有完全一样的与磁轴和自转方向的相对关系，便于后面比较两极的辐射束和辐射区域。

![](images/61ce5453b9f4c3a3e6e3fdbdb317907c6e6e5a5afeb8ad17f13539346b3d1b6c.jpg)  
图1主脉冲（a）和中间脉冲（b）的脉冲宽度随 $| \beta |$ 的变化。方框符号代表 $W _ { 1 0 }$ ，三角形符号代表 ${ \mathrm { . } } W _ { 5 0 }$ 。两图中的红色实线分别代表用公式（2）和线性函数得到的最佳加权拟合结果（仅用宽度误差进行加权)，蓝色和黑色方框符号分别代表 $\beta < 0$ 和 $\beta > 0$ 时的宽度数据，竖直黑色虚线则代表辐射束内外部分的近似分界线，有 $| \beta | { = } 5 . 5 ^ { \circ }$ ，其中辐射束内区为粉红色区域。

Fig.1Variation of the main pulse (a) and interpulse (b)widths versus $| \beta |$ .Squares represent $W _ { 1 0 }$ and triangles represents $W _ { 5 0 }$ .The redsolidinesinthefiguresrepresenthebestweighted-fitresultsobtainedbyusingEquation(2)andinearfunction(weightedbywidth error only),respectively. The blue and black squares represent the width data of $\beta < 0$ and $\beta > 0$ ,respectively.The vertical black dotted line represents the approximate separatrix for the inner and outer parts of the emission beam, with $| \beta | { = } 5 . 5 ^ { \circ }$ .The inner part of the emission beam is represented by the pink area.

图1(a)显示主脉冲的 $W _ { 1 0 }$ 随 $| \beta |$ 呈正相关关系，其中 $\beta$ 均为负值，且都落在辐射束外区。图中红色的曲线是利用公式(2)得到的最佳拟合曲线， $\varphi$ 的最佳拟合值为 $1 9 . 5 ^ { \circ } { \pm } 1 . 3 ^ { \circ }$ 。因此，从扇形束模型的观点来看，主脉冲的辐射大致来自于磁经度角范围约为 $3 9 ^ { \circ } \pm 2 ^ { \circ }$ 的磁流管。图中也显示了 $W _ { 5 0 }$ 随 $| \beta |$ 的变化，情况相似。

不过需要指出，公式（2）适用的前提是辐射区关于磁轴一自转轴所在平面对称，而实际情况是主脉冲辐射束偏离磁轴和自转轴平面，朝向了自转方向一侧（见文献[9]图3)，所以上述拟合只是粗糙的估计。为了更好的揭示辐射束边界的磁经度分布范围，我们对每一个主脉冲轮廓的 $10 \%$ 峰值强度水平上左右轮廓边界都计算了磁经度角，公式如下：

$$
\varphi = \left\{ \begin{array} { c c } { { \frac { 3 } { 2 } \pi + \mathrm { s i g n } ( \phi ) \cos ^ { - 1 } \left( { \frac { \cos \zeta - \cos \alpha \cos \rho } { \sin \alpha \sin \rho } } \right) } } & { { \left( \alpha > { \frac { \pi } { 2 } } \right) } } \\ { { \frac { \pi } { 2 } - \mathrm { s i g n } ( \phi ) \cos ^ { - 1 } \left( { \frac { \cos \zeta - \cos \alpha \cos \rho } { \sin \alpha \sin \rho } } \right) } } & { { \left( \alpha < { \frac { \pi } { 2 } } \right) } } \end{array} \right. ~ \circ
$$

式中视线角{为视线与自转轴的夹角，满足 $\zeta = \alpha + \beta$ ， $\rho$ 为相对轮廓参考中心的相位 $\phi$ 上的辐射所具有的辐射张角（即辐射方向到磁轴的角距离)，可通过下式计算

$$
\rho = \cos ^ { - 1 } ( \cos \zeta \cos \alpha + \sin \zeta \sin \alpha \cos \phi ) ~ \circ
$$

这里的 $\phi$ 为主脉冲和中间脉冲轮廓中的相位相对于各自的中心参考相位的差值， $\sin ( \phi )$ 是符号函数，负 $\phi$ 值的辐射比正 $\phi$ 值的辐射更早达到观测者。在旋转矢量模型中，线偏振位置角RVM 曲线拐点的相位被认为是磁轴一自转轴平面所在的相位，因此我们将主脉冲和中间脉冲的 RVM 曲线拐点相位作为各自的中心参考相位（ $\boldsymbol { \phi } _ { \mathrm { c , M P } }$ 和 $\boldsymbol { \phi } _ { \mathrm { c , I P } } )$ ，则相对相位 $\phi _ { M \mathrm { P / I P } } =$ $\phi _ { \mathrm { M P / I P } } - \phi _ { \mathrm { c , M P / I P } }$ 。公式（3）中第一个式子适用于主脉冲，第二个适用于中间脉冲。

文献[9]采用了RVM模型最佳拟合曲线的拐点确定主脉冲和中间脉冲的中心参考相位，将它们设置为0和 $1 8 0 ^ { \circ }$ ，用以对齐轮廓。Zenodo共享的轮廓数据已经进行了相位对齐，但中心相位并不是0和 $1 8 0 ^ { \circ }$ ，Zenodo 的技术文档也未说明中心参考相位在哪里。我们通过与文献[9]中轮廓的比对，确定出主脉冲和中间脉冲轮廓的中心参考相位分别近似为0.25和0.75（以自转周期为单位)。随后，主脉冲的相位和中间脉冲的相位分别减去上述值，归算出相对相位 $\phi _ { M \mathrm { P } }$ 和 $\phi _ { \mathrm { I P } }$ ，进而计算各边界的磁经度角。

图2（a）给出了主脉冲 $10 \%$ 峰值强度边界的磁经度角随碰撞角的变化。可以看到，主脉冲的左边界和右边界都在各自的平均值附近摆动，二者之差所得的磁经度宽度为△φ$\scriptstyle = 3 3 ^ { \circ } \pm 8 ^ { \circ }$ （见图2（b))，这与之前利用公式（2）拟合得到的结果差别不太大。

为了更加直观的显示辐射束结构，我们将主脉冲的磁经度角范围投影到天球上，在如图3 中用蓝色的线段代表，同时用蓝色箭头表示碰撞角随观测时间的变化方向。可见在主脉冲磁极，辐射束主要位于第四象限。两条红色虚线分别代表左边界和右边界的平均磁经度角。如图所示，主脉冲辐射束能较好的用红色边界线之间的辐射束来描述。

需要特别指出，这里采用每个轮廓 $10 \%$ 峰值强度的轮廓边界来表征辐射束边界，可以理解为对各轮廓独立做强度归一化，然后做相对强度的 $10 \%$ 水平上的等值图，而文献[9]的图3则是用绝对流量来做等值图，二者效果不同。当辐射束内部流量密度差别巨大的时候，绝对流量的等值图不利于完整地显示弱的结构，而采用相对强度等值图则更有优势。对比本文图中纵坐标 $. 1 5 ^ { \circ }$ 以下的部分和文献[9]图3主辐射束的相同部分，可以非常清楚的看到这一点。

相比主脉冲，中间脉冲表现出截然不同的脉冲宽度与碰撞角的相关性，如图1（b）所示。在辐射束内区， $W _ { 1 0 }$ 与 $| \beta |$ 呈现较为明显的反相关关系。因WPZ模型没有给出辐射束内区的宽度和碰撞角关系，我们简单地采用线性拟合，得到最佳拟合结果为 $W _ { 1 0 } = - 1 . 5 ^ { \circ } \pm$ $0 . 4 ^ { \circ } | \beta | + 2 6 . 3 ^ { \circ } \pm 1 . 1 ^ { \circ } ,$ 。需要特别指出的是，中间脉冲的碰撞角从 $1 3 ^ { \circ }$ 左右变化到 $. 6 . 2 ^ { \circ }$ ，在磁轴南北两侧均有一部分区域属于辐射束内区，有趣的是这两部分的 $W _ { 1 0 }$ 与 $| \beta |$ 的关系基本一致（图1（b）中蓝色方框代表负的碰撞角，黑色方框代表正的碰撞角)。辐射束外区 $W _ { 1 0 }$ 的变化不太规则，随着碰撞角增加先下降后增加，这很可能与脉冲轮廓的不规则变化有关。

图2（c）给出了中间脉冲 $10 \%$ 峰值强度辐射束边界的磁经度角随碰撞角的变化。可以看到左右边界均出现持续变化，而不像主脉冲那样在各自平均值附近摆动。图2（d）显示，随着碰撞角由正值变向负值，辐射束磁经度宽度先是逐渐增大，在碰撞角为0，即视线扫过磁轴时，磁经度宽度达到最大值 $1 8 0 ^ { \circ }$ ，随后减小。这表明中间脉冲辐射束并不是固定宽度的磁流管产生的，而是在环绕极轴的磁力线上产生的。这可以直观地从图3中深灰色的辐射束投影区域看出来。就磁经度范围的这一特点而言，中间脉冲辐射束更具有锥辐射束的特点，但是辐射束在纬度方向的延展性是锥辐射束模型无法解释的。

![](images/bff3cf3bde3a5ce16c32c966e3aa8940b2e3dda19f3099c039638724135755a7.jpg)  
图2PSR $\mathrm { J 1 9 0 6 + 0 7 4 6 }$ 脉冲轮廓 $1 0 \%$ 峰值强度辐射束边界的磁经度角（"Azimuth"，即 $\varphi$ ）和辐射束磁经度宽度（ $^ { * } \Delta$ Azimuth",即△φ)。（a）为不同碰撞角时主脉冲（MP）的辐射束左边界（菱形）和右边界（圆点）的 $\varphi$ ，红色和黑色水平线代表平均磁经度角，分别是左边界 $2 8 1 ^ { \circ } .$ 和右边界 $3 1 3 ^ { \circ } .$ 。（b）为主脉冲辐射束的 $\Delta \varphi _ { \circ }$ （c）和（d）分别是中间脉冲（IP）的𝜑和△𝜑，其中（c)图中在 $_ { \cdot \beta = 0 }$ 处右边界 $\cdot \varphi$ 值的跳变是由于随着时间 $\boldsymbol { \beta }$ 从正值变到负值，右边界从第四象限变到第一象限所致，见图4。磁经度角根据脉冲轮廓 $1 0 \%$ 峰值水平的左右边界相位计算得到，其计量方法见正文和图1。因主脉冲近期观测不到或信噪比过低，在2005-2018年的47次观测中，主脉冲共有34个轮廓可用。中间脉冲共有47个轮廓。

Fig.2The magnetic longitude('Azimuth', i.e. $\varphi$ ）and the magnetic longitude width of the emision beam ( $^ { \bullet } \Delta$ Azimuth', ie. $\Delta \varphi$ at the $10 \%$ peak intensity level of the pulse profile of PSR J $1 9 0 6 + 0 7 4 6$ . (a) The $\varphi$ of the left boundary (diamonds)and the right boundary (dots)of theemissionbeamoftemainpulse(MP)fordiferentimpactangle.Theredandblackhorzontallinesrepreseteaverage magnetic longitudes,which are $2 8 1 ~ ^ { \circ }$ for the left boundary and $3 1 3 ^ { \circ }$ for the right boundary,respectively.(b) The $\Delta \varphi$ of the main pulse emission beam. (c) and (d) are $\varphi$ and $\Delta \varphi$ of the interpulse (IP),respectively. In panel (c),the jump of $\varphi$ value of the right boundary at $\scriptstyle { \beta = 0 }$ is caused by the change of the right boundary from the fourth quadrant to the first quadrant when $\beta$ changes from a positive value to anegativevalue,sshowninFigure4.Themagneticlongitudeiscalculatedaccording totheleftandrightboundaryphasesatthe $10 \%$ peak intensitylevelof thepulseprofile. textandFigure1forits measuringmethod.Bcausethemain pulse wasnotdetectedorthe signal-to-noiseratioistoolowinrecentoservatiosinthe47bservatiosino-8,34profilesofteainpuseareseful.47 profiles of the interpulse are useful.

![](images/f263e1db192f0f9e4c8aea179249f742b68f4fbe6648ae874406cb511400e5ab.jpg)

图3PSR $\mathrm { J 1 9 0 6 + 0 7 4 6 }$ 主脉冲和中间脉冲辐射束的主要分布范围。图中显示的是天球在两个磁极（绿色十字）附近的区域，蓝色和深灰色曲线线段分别代表主脉冲和中间脉冲轮廓 $10 \%$ 峰值宽度 $W _ { 1 0 }$ 所对应的经度范围。为了便于比较两极的辐射束，已将主脉冲磁极区域的方位做了转换。对于主脉冲而言，从磁极（坐标原点）竖直向上指向自转轴反方向；对于中间脉冲而言，从磁极竖直指向自转轴正方向。在主脉冲和中间脉冲这两极视线的变化方向分别由蓝色和黑色箭头代表，与此相应，主脉冲的碰撞角为负值且持续减小，中间脉冲的碰撞角从正值持续变化到负值（注意图中纵坐标递增方向仅代表主脉冲碰撞角递增方向，中间脉冲的与之相反)。红色虚线代表了主脉冲 $10 \%$ 峰值强度左右边界上平均的磁经度角。

Fig.3The major ranges of the main-pulse and interpulse emission beams of PSR $\phantom { - } 1 9 0 6 + 0 7 4 6$ .The area of the celestial sphere near the two magneticpoles (greencross)isshown.Theblueanddark-graycurvesrepresent the projectionof thelongitudinalranges for $W _ { 1 0 }$ of the mainpulseandtheinterpulse,respectively.Inordertocomparetheemisionbeamsbetweenthetwopoles,therientationofthe mai-pulsepolarregionhasbeenadjusted.Forthemaipulse,thedirectionpointigfromthepole (coordinateorigin)verticallypwads representstheppositedectioofrotationaxis,hilefortheinterpulse,itepresentsthepositivedirectionofterotationais.e directionsof telieofsightatemain-pulsendinterpulsepolesarerepresentedbybluendblackaros,respectively.Accodgly theimpactangleoftemainpulseisegativeanddcreasescontinuouslyandtheimpactangleoftheinterpulsechangescotiously frompositivetonegativevalues(otethattheincrementdirectionoftheordinateonlyrepresentstheincrementdirectionofteipact angleforthemainpulse,hileitisoppositetteinterpulse).Theeddotedlinesrepresenttheaveragemagneticlongitudesontheleft and right boundaries at the $10 \%$ peak intensity level of the main-pulse profile.

# 2.2辐射流量密度与碰撞角的关系

图4显示了峰值流量密度与 $| \beta |$ 的关系。如图4（a）所示，主脉冲辐射束外区峰值流量密度随 $| \beta |$ 的增加而减小，这与WPZ 模型的理论预言定性吻合。在WPZ模型中，辐射强度和 $| \beta |$ 成幂律关系，所以观测者接收到的峰值辐射流量与 $| \beta |$ 也成幂律关系，公式如下

$$
f _ { \mathrm { p k } } \approx A P ^ { q - 4 } \dot { P } _ { - 1 5 } | \beta | ^ { 2 q - 6 } \ ,
$$

其中 $\dot { P } _ { - 1 5 }$ 是以 $1 0 ^ { - 1 5 } \mathrm { s / s }$ 为单位度量的自转周期变化率， $\boldsymbol { q }$ 为描述带电粒子相干辐射功率与辐射高度之间关系的参量。二者的关系取决于具体的辐射机制，以及辐射模型中有关参数随高度的变化。WPZ做了唯象化处理，假设二者的关系服从幂律函数，则幂指数 $q$ 反映了辐射功率随高度衰减（或增加）的快慢程度。采用Bi-square 加权进行非线性回归，用公式（3）能较好地拟合主脉冲观测数据。图4（a）中的红色曲线表示最佳拟合曲线，相应的指数为$q { = } { - } 0 . 8 5 { \pm } 0 . 9 3$ 。

如图4（b）所示，中间脉冲的峰值流量密度与 $| \beta |$ 整体上呈正相关关系。理论上，在辐射束内区，就单个磁流管而言，WPZ模型阐明其辐射强度可随 $| \beta |$ 增加而增强，但是如果存在多个磁流管，情况会比较复杂。因此，WPZ模型是有潜力解释辐射束内区的正相关关系的。但是，辐射束外区的观测数据显示出的正相关关系却和WPZ模型的预言相反，对模型参数的要求在本文下一部分讨论。最后，对辐射束内区我们尝试用幂律函数拟合，所得函数关系为 $f _ { \mathrm { p k } } = 1 0 ^ { 0 . 0 2 \pm 0 . 0 4 } | \beta | ^ { 0 . 1 9 \pm 0 . 0 7 }$ ，图4（b）给出了最佳拟合曲线。

![](images/235e2b3694a606ba42a7af521ca83c1a5fa690e32bf7241206bf1e83aab8e4bd.jpg)  
图4主脉冲（a）和中间脉冲（b）轮廓峰值流量密度与Iβ的关系。两幅图中的红色实线分别为公式（3）和幂律函数的最佳拟合曲线，黑色竖直虚线对应 $| \beta | { = } 5 . 5 ^ { \circ }$ ，代表辐射束内外部分的近似分界线，其中辐射束内区以粉红色区域表示。蓝色和黑色圆圈分别表征 $\beta < 0$ 和 $| \beta > 0$ 时的数据点。

Fig.4Relationship between the peak flux densities of the main-pulse(a)and interpulse (b)profiles and $| \beta |$ . The red solid lines in the twopanelsarethebest-fitcuresbyuingEq.(）andpower-lwfunction,espectively.Theblackverticaldotedlincorsdsto $| \beta | { = } 5 . 5 ^ { \circ }$ ,representing theapproximateseparatrixoftheinnerandouterpartsof theemisionbeam,whereintheinnerpart isrepresented by the pink area.The blue and black circles represent the data points when $\beta < 0$ and $\beta > 0$ ,respectively.

# 3．讨论

# 3.1现有辐射束模型的困难

由于PSR $\mathrm { J 1 9 0 6 + 0 7 4 6 }$ 两极的辐射束都明显不符合核双锥辐射束的图像，因此这里不讨论核双锥模型，而重点讨论扇形束模型。从上述结果可以看到WPZ扇形束模型能够符合一部分观测特征，也有不符合的，分别概括和讨论如下。

（1）WPZ模型可以定量解释的观测事实。

$\textcircled{1}$ 主脉冲的脉冲宽度和 $| \beta |$ 呈正相关关系，结果表明可见部分的辐射束与一个磁经度宽度为 $3 3 ^ { \circ } \pm 8 ^ { \circ }$ 的磁流管产生的扇形束宽度特征吻合。$\textcircled{2}$ 主脉冲的轮廓峰值流量密度与 $| \beta |$ 呈反相关关系，符合WPZ模型的理论关系。

（2）难以用WPZ模型解释的观测特征如下。

$\textcircled{1}$ 中间脉冲宽度随 $| \beta |$ 的变化无法用单一的、有确定磁经度宽度的磁流管所产生的扇形束来描述。由图2（d）所示，随着视线的变化（伴随 $\beta$ 从负值变到正值)，辐射束的磁经度宽度在连续不断地变化，先增加后减小，且在视线扫过磁极处时达到最大值 $1 8 0 ^ { \circ }$ 。这表明辐射来自于磁轴四周的磁力线，而不是一个具有固定宽度的磁流管，这不同于WPZ模型中辐射是来自于具有确定宽度的磁流管的图像（见文献[5]图7)。

$\textcircled{2}$ 中间脉冲辐射束外区峰值脉冲流量的整体趋势是随 $| \beta |$ 增加而增加，这和WPZ 模型预期的相反。如果仍然沿用WPZ模型的公式（3）解释，则要求 $q { > } 3$ ，即在辐射束外区相干辐射功率随高度增加显著增长，物理上是否可行有待研究。但这种正相关关系非常不可能持续下去，到一定的距离后流量转为衰减看起来更为合理。我们注意到图5（b）中最右侧的两个数据点确实显示峰值辐射流量密度随 $| \beta |$ 增加而降低，这一趋势是否能继续，还有待后续的观测。

$\textcircled{3}$ 中间脉冲的辐射来自磁轴四周，辐射束跨越磁轴延展，这对 WPZ 模型来说是个难题。主脉冲的辐射束是否也具有跨越磁轴的性质尚无数据支持，但从Desvignes 等人发表的辐射束来看，1998年所看到的脉冲是比较宽，离磁轴较近，且位于磁轴的另一侧，与主要的辐射束相对，所以不能排除其辐射束类似中间脉冲辐射束那样跨越磁轴延展的可能。

WPZ 模型的困难主要来自于其现有的假设，认为辐射束是由单个或若干分立的磁流管产生的子辐射束构成的，每一个子辐射束都是延展的扇叶形或长条形，其末端汇聚在磁轴（见文献[5]图5-8)，这样就不能形成像中间脉冲那样连贯的跨越磁轴的条形辐射束。

其他的扇形束模型，如Dyks 等人[4,6和Oswald等人[12]的工作，均未明确给出辐射束的宽度、辐射流量与碰撞角的关系，且通常假设辐射束内边缘离磁轴有一段距离，所以对磁轴附近的辐射也是缺乏考虑的。

# 3.2扇形束模型改进的方向

中间脉冲辐射束的特征要求一种兼具锥模型和扇形束模型特点的唯象模型，需满足以下几个要素。

（1）图2（d）的结果要求辐射能够从各个磁经度角的磁力线上产生，例如极冠区内围绕磁轴的一圈磁力线，或者整个极冠区等。这一点类似于锥辐射束模型常用的假设。

（2）Desvignes 等人的结果表明在相差很大的辐射高度上都可以产生1.4GHz 波段的辐射，这不符合通常认为的不同频率的辐射来自不同高度的假设（radius-to-frequencymapping)。更加合理的假设是相对论性粒子流在沿磁力线外流过程中产生宽频辐射，因而在单个频率上看辐射束可以是足够延展的。

（3）在上述两个假设的前提下，如果辐射强度随高度的变化关系不依赖于磁经度角，势必会导致圆形的辐射束结构。但观测到中间脉冲辐射束的形状在纬度方向延展，在经度方向相对压缩，因而就要求辐射强度与高度的关系在不同的磁经度角上有差异，以便能够解释这种长条形的特征。

采取以上假设，通过调节模型参数，理论上有可能构建出具有PSR $\mathrm { J 1 9 0 6 + 0 7 4 6 }$ 辐射束特征的唯象模型，这将对构建更加物理的辐射模型具有借鉴意义。

# 3.3关于磁轴附近辐射的物理机制

如何解释PSR $\mathrm { J 1 9 0 6 + 0 7 4 6 }$ 磁轴附近的辐射是构建辐射模型的重要内容之一。曲率辐射经常被用于解释脉冲星射电辐射[13.14]。在静态磁偶极场模型下，磁轴上的磁力线曲率为零，附近的开放磁力线曲率也非常小，因此无法通过曲率辐射产生有效的射电辐射。但在旋转磁偶极场情况下，磁力线的曲率会增大，是否足以产生观测到的射电辐射频率和流量，需要具体研究。

逆康普顿散射模型[15.16]在这方面可能更有优势。该模型下，极冠加速区放电产生的低频电磁波在向外传播时被次级相对论性粒子散射（逆康普顿散射过程)，产生较高频率的射电波。只要低频波波矢方向和次级粒子运动方向的夹角不为零，散射过程便可发生。当磁轴附近有次级粒子外流时，它们同其他区域产生的低频波散射，满足夹角不为零的条件，便可能

会产生可观测的射电辐射。

无论是曲率辐射模型还是逆康普顿散射模型，都要求从磁轴附近有相对论性次级粒子外流。在内加速区模型框架下[13]，这就要求在磁轴附近的极冠加速区存在多极磁场，以提供足够大的磁力线曲率，使得级联放电过程能够发生。

# 3.4两极辐射束的差异性

一般认为脉冲星两极的磁场结构应该是相同的，在相同磁场结构的区域物理过程也是相同的，因而两极的辐射束结构应该相同。图4将两极的辐射束重叠比较，在相同的象限两极的磁场结构是相同的。然而，主脉冲和中间脉冲辐射束却相差甚大，即便是在视线都扫过的区域，二者的磁经度范围也差别很大，中间脉冲的辐射区域明显要宽得多。需要注意的是，根据文献[9]，1998年时主脉冲的位置在本文图3中位于纵坐标接近 $5 ^ { \circ }$ 的地方，且脉冲轮廓的中心接近横坐标 $0 ^ { \circ }$ ，因此不排除主脉冲的辐射束也跨越磁轴，辐射也来自于环绕磁轴的磁力线的可能性。即便如此，两极的辐射束形状的差异仍然十分显著。这一点在文献[9]中未引起足够的重视，而PSR $\mathrm { J 1 9 0 6 + 0 7 4 6 }$ 作为第一颗能揭示两极辐射差异性的脉冲星，对通常的观点构成了挑战。

两极辐射束在形状方面的差异，既可能是辐射来源的磁力线分布不同，也可能是两极的磁场结构不同。关于第一种可能性，可以利用旋转磁偶极模型的辐射几何，从观测数据中尝试反演两极辐射的来源区域，检查磁力线分布的可能差异及其合理性。关于第二种可能性，文献中有少数工作曾提出两个磁极不平行的理论模型[17,18],其中两极的物理性质可能会有差异，这提供了一种思路。这样的模型中两个极轴的相位会偏离 $1 8 0 ^ { \circ }$ ，且线偏振位置角曲线偏离经典的旋转矢量模型，因此需要建立模型，通过拟合偏振观测数据来探索可能的参数空间，进而判断这种模型的可行性。这两种模型的主要差别之一是线偏振位置角曲线和两个磁极的相位差，因此需要综合两极的数据对全周期的线偏振位置角进行完整地拟合，来尝试是否可以区分二者。如果这两种模型都能在合理的参数空间解释偏振观测特征，则需要进一步考虑解释两极辐射束内强度分布特征差异的可行性，不过这可能高度依赖具体辐射模型。

# 4.结论

本文利用PSR $\mathrm { J 1 9 0 6 + 0 7 4 6 }$ 的开放数据，研究了该星的主脉冲和中间脉冲的辐射特征。结果表明，主脉冲的 $10 \%$ 峰值强度脉冲宽度和 $| \beta |$ 呈正相关关系，脉冲轮廓峰值流量密度与 $| \beta |$ 呈反相关关系，观测数据可以用WPZ扇形束模型的理论关系来合理拟合，因而主脉冲主要可见部分的辐射束可被解释为由一束磁流管产生。对于中间脉冲，从脉冲宽度和 $\beta$ 数据计算得到的磁经度角显示辐射所在磁力线围绕在磁轴四周，因此中间脉冲难以用单一的、有确定磁经度角范围的磁流管所产生的辐射束来描述。另外中间脉冲辐射束外区的峰值流量密度随$| \beta |$ 增加而增加，这和WPZ 模型的预言也不符合。本文认为，PSR $\mathrm { J 1 9 0 6 + 0 7 4 6 }$ 中间脉冲辐射束的特征要求一种兼具锥辐射束模型和扇形束模型特点的唯象模型，要求允许磁轴四周的磁力线上均产生辐射，通过合理选择辐射强度随高度和磁经度角的依赖关系，来模拟出能够连续跨越磁轴的条形辐射束。此外，观测揭示两极的辐射束有显著差异，这对认为两极磁层的物理状态和过程相同的传统观点带来了挑战。

# 参考文献

[1]RANKIN JM. Toward an empirical theory of pulsar emisson. I Morphological taxonomy[J]. The Astrophysical Journal, 1983, 274: 333-358.

[2]KOMESAROFF M M. Possible Mechanism for the Pulsar Radio Emission[J]. Nature,1970, 225(5233): 612-614.   
[3]MICHEL FC.A Pulsar Emission Model: Observational Tests[J]. The Astrophysical Journal, 1987,322: 822.   
[4] DYKS J,RUDAK B,DEMOREST P. The nature of pulsar radio emission[J]. Monthly Notices of the Royal Astronomical Society, 2010, 401(3): 1781-1795.   
[5]WANG HG,PI F P, ZHENG X P,et al.A Fan Beam Model for Radio Pulsars.I. Observational Evidence[J]. The Astrophysical Journal, 2014, 789(1): 73.   
[6] DYKS J，RUDAK B. The origin of the frequency-dependent behaviour of pulsar radio profiles[J]. Monthly Notices of the Royal Astronomical Society,2015, 446(3): 2505-2522.   
[7] MANCHESTER R N, KRAMER M, STAIRS I H, et al. Observations and Modeling of Relativistic Spin Precession in PSR J1141-6545[J]. The Astrophysical Journal, 2010, 710(2): 1694-1709.   
[8] DESVIGNES G, KRAMER M, COGNARD I, et al. Neutron Stars and Pulsars: Challenges and Opportunities after 8O years. Ed. van Leeuwen J，in IAU Symposium 291[M]. Cambridge: Cambridge Univ.Press,2013:199-202.   
[9] DESVIGNES G, KRAMER M, LEE K, et al. Radio emission from a pulsar's magnetic pole revealed by general relativity[J]. Science,2019,365(6457): 1013-1017.   
[10] LORIMER D R, STAIRS IH,FREIRE P C, et al. Arecibo Pulsar Survey Using ALFA. II. The Young,Highly Relativistic Binary Pulsar $\mathrm { J 1 9 0 6 + 0 7 4 6 [ J ] }$ . The Astrophysical Journal, 2006,640(1): 428-434.   
[11] LEE K J,DU Y J,WANG H G, et al. Low bounds for pulsar $\gamma$ -ray radiation altitudes[J]. Monthly Notices of the Royal Astronomical Society, 2010, 405(3): 2103-2112.   
[12] OSWALD L, KARASTERGIOU A, JOHNSTON S. Understanding the radio beam of PSR （204号 $\mathrm { J 1 } 1 3 6 + 1 5 5 1$ through its single pulses[J]. Monthly Notices of the Royal Astronomical Society, 2019,489(1): 310-324.   
[13] RUDERMAN M A, SUTHERLAND P G. Theory of pulsars - Polar caps， sparks, and coherent microwave radiation[J]. The Astrophysical Journal,1975,196: 51-72.   
[14] WANG P F, WANG C, HAN J L. Curvature radiation in rotating pulsar magnetosphere[J]. Monthly Notices of the Royal Astronomical Society, 2012, 423(3): 2464-2475   
[15] QIAO G. A mechanism for core emisson of pulsars[J]. Vistas in Astronomy,1988, 31(1): 393-397.   
[16] QIAO G J, LIN W P. An inverse Compton scattering (ICS) model of pulsar emission. I. Core and conal emission beams[J]. Astronomy and Astrophysics, 1998, 333: 172-180.   
[17] HARDING A K, MUSLIMOV A G. Pulsar Pair Cascades in Magnetic Fields with Offset Polar Caps[J]. The Astrophysical Journal, 2011, 743(2): 181.   
[18] BURNETT C R, MELATOS A. Stokes tomography of a radio pulsar with an offset magnetic dipole[J]. Monthly Notices of the Royal Astronomical Society,2014, 440(3): 2519-2527.

# Observational properties of radio emission beams of PSR J $1 9 0 6 + 0 7 4 6$ and its implication

Huang Wenjun', Huang Xiujian², Wen Zhigang³, Wang Hongguang1 (1. School of Physics and Electronic Engineering, Guangzhou University, Guangzhou 510006, China, Email: hgwang @ gzhu.edu.cn; 2. College of Physical Science and Technology, Central China Normal University, Wuhan 430079, China; 3. Xingjiang Astronomical Observatory, CAS, Urumqi 830011, China)

Abstract: In this paper, the properties of the main-pulse and interpulse radio emission beams were studied for PSR $\mathrm { J 1 9 0 6 + 0 7 4 6 }$ by using the open data. By fitting the integrated pulse profile of each epoch with Gaussian components,we obtained the corresponding $10 \%$ peak pulse width and the peak flux density,and then analyzed the relationships between them and the impact angle. The results show that the major visible part of the emission beam of the main pulse is generated by a magnetic flux tube with a certain range of magnetic longitude, while the emisson of the interpulse comes from magnetic field lines around the magnetic axis.The properties of the main pulse can be well explained by the existing fan beam models,but the properties of the interpulse are difficult to interpret by the fan beam models,which requires the improvement of the fan beam model. Under the assumption that radio radiation can be generated along the magnetic field lines around the magnetic axis,the observed strip-shaped emission beam can be simulated by reasonable selection of the model parameters.

Key words: Pulsars; Radio emission; PSR J19O6+O746; Emission beam