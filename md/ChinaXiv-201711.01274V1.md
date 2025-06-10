# BLLac天体GeV-TeV能谱分析

钟微，刘文广，郑永刚

(1 云南师范大学物理与电子信息学院，云南 昆明 650500)(2 云南省高校高能天体物理重点实验室，云南 昆明 650500)

摘要：收集了126个BLLac 天体在高能段和甚高能段的观测谱指数，利用数学模型$\Delta \Gamma _ { o b s } = \alpha z + \beta$ 分析其能谱拐折（甚高能与高能观测谱指数之差)。目的是确定河外星系背景光(EBL)吸收是否是导致大红移BLLac天体能谱拐折的主要原因。统计分析结果为 $\alpha \neq 0$ ，$\beta \neq 0$ 。统计结果表明，BLLac 天体能谱拐折不仅起源于河外星系背景光吸收，还与其它物理过程有关。

键词：星系；BLLac天体；辐射机制；非热；统计中图分类号：P157 文献标识码：A 文章编号：1672-7676

BLLac天体的连续辐射主要来自与观测者视线夹角很小的喷流辐射区，能谱分布（SEDs）呈双峰结构，对应两个主要辐射成分[1-2]。一般认为第1个峰（低能峰）是由极端相对论性电子同步辐射产生,第 2 个峰（高能峰）可能由相对论性电子的逆康普顿产生[3]，也可能由相对论性质子同步辐射、光介子对级联过程、介子同步辐射等过程产生[4-5]。这两个主要辐射成分使伽玛射线谱带平滑，然而，在更高的能段，能谱分布图有变陡的趋势[6-7]，这种趋势展示了不同能带间的能谱拐折。

宇宙中存在弥散河外星系背景光，它是从紫外到远红外波的各向同性的弥散辐射场[8]。BLLac天体喷流辐射区内产生的甚高能（VHE， $E { \ge } 5 0 G e V$ ）伽玛射线光子在星际空间传播过程中与河外星系背景光子相互作用产生正负电子对912]，即 $\gamma _ { { } _ { V H E } } + \gamma _ { { } _ { E B L } }  e ^ { + } + e ^ { - }$ ，使得观测光谱变陡[13-14]。预计当 TeV 光子处于较高红移，具有明显的河外星系背景光吸收特性[12,15-17]。然而，大红移BLLac天体的伽玛射线辐射不能被次级级联[18-20或轴子类型的粒子转换①吸收。基于上述情况，预计BLLac 天体的高能（HE， $1 0 0 M e V \le E < 5 0 G e V$ ）观测光谱和甚高能观测光谱是不同的，将导致GeV谱和TeV谱指数的不同。

为了阐明能谱拐折机制，本文主要研究了BLLac天体GeV-TeV能谱指数。其目的是确定河外星系背景光吸收是否是导致大红移BLLac天体能谱拐折的主要原因。由于观测光谱是光谱被河外星系背景光吸收后得到的，因此对观测光谱进行修正可得到内禀光谱。

# 1样本选择

本文选择Fermi-LAT2FHL目录和TeV目录的源进行分析研究。2FHL目录包括甚高能观测谱指数和内禀谱指数，高能观测谱指数来自 3FGL目录[21]。TeV 目录包括甚高能和高能观测谱指数，但甚高能内禀谱指数来自文[22]。由于 $\mathrm { T e V }$ 目录中的某些源与2FHL目录中的源是相同的，因此对这些源仅计算一次。

耀变体分为BLLac 天体[23]和平谱射电类星体(FSRQs)[24]。与BLLac 天体相比，FSRQs的宽线区(BLR)的吸收和外部康普顿辐射(EC)将影响能谱拐折，因此移除平谱射电类星体。从上述目录中选取126 个观测谱指数 $\left( \Gamma _ { { \scriptscriptstyle V H E } , o b s } \right)$ 和内禀谱指数 $( \Gamma _ { { \nu } { H E } , \mathrm { i n t } } ^ { } )$ ，其中高能段有 120个源。对于这些来源，使用观测高能谱指数（ $\dot { \mathbf { \nabla } } \mathbf { r } _ { H E }$ ）完善数据。根据同步辐射峰值频率，将样本分为 23 个低同步辐射峰值频率BL Lac 天体（IBL， $\nu _ { p e a k } ^ { S } \leq 1 0 ^ { 1 4 } H z \ \rangle$ ，13个中同步辐射峰值频率 BL Lac 天体（IBL， $1 0 ^ { 1 4 } H z \le \nu _ { p e a k } ^ { s } \le 1 0 ^ { 1 5 } H z$ ），90 个高同步辐射峰值频率 BLLac 天体（HBL， $\nu _ { p e a k } ^ { S } \geq 1 0 ^ { 1 5 } H z$ ）°

# 2观测谱和内禀谱的比较

观测谱指数和内禀谱指数的分布如图1。为了估计样本的最大似然均值和离散程度，按照如下方程组[25]：

$$
{ \Gamma } _ { 0 } { = } \Bigg ( \frac { { \Gamma } _ { j } } { { \sigma } _ { 0 } ^ { 2 } + { \sigma } _ { j } ^ { 2 } } \Bigg ) \Bigg ( \sum _ { j = 1 } ^ { N } \frac { 1 } { { \sigma } _ { 0 } ^ { 2 } + { \sigma } _ { j } ^ { 2 } } \Bigg ) ^ { - 1 } ,
$$

$$
\sum _ { j = 1 } ^ { N } \frac { 1 } { \sigma _ { 0 } ^ { 2 } + \sigma _ { j } ^ { 2 } } = \sum _ { j = 1 } ^ { N } \frac { \left( \Gamma _ { j } - \Gamma _ { 0 } \right) } { \left( \sigma _ { 0 } ^ { 2 } + \sigma _ { j } ^ { 2 } \right) ^ { 2 } } \quad .
$$

其中， $\Gamma _ { j }$ 为耀变体的谱指数； $\sigma _ { j }$ 为谱指数的误差； $N$ 为总的耀变体数目； $\Gamma _ { 0 }$ 为均值谱指数； $\sigma _ { 0 }$ 为耀变体的离散程度。解上述方程组得到均值谱指数和离散程度，并将均值谱指数在图1中表示。

通过计算，得到观测谱指数的离散程度 $\sigma _ { 0 , \ o b s } = 1 . 4 3$ 和内禀谱指数的离散程度（20 $\sigma _ { 0 , \mathrm { i n t } } = 1 . 5 5$ 。注意到 $\sigma _ { 0 , \mathrm { \ i n t } } - \sigma _ { 0 , \mathrm { \ o b s } } = 0 . 1 2$ ，意味着观测谱指数和内禀谱指数的置信区间相差不大，不影响内禀谱指数和观测谱指数的研究。因为内禀谱（光谱未被河外星系背景光吸收）是通过观测谱修正得到的，预计内禀谱指数比观测谱指数小。如图1，均值观测谱指数（204 $\Gamma _ { 0 , \ o b s } = 2 . 9 6$ ,均值内禀谱指数 $\Gamma _ { 0 , \mathrm { i n t } } = 2 . 5 5$ 。比较这两个值发现，均值观测谱指数相对较低，暗示着内禀谱是硬谱，而河外星系背景光修正的主要作用是减小均值谱指数。

![](images/03ab324f5b102f27193bcd2a827ed01b09857d0734a41e786a3a18c48fd39bc7.jpg)  
图1观测谱指数与内禀谱指数的分布。观测谱指数分布由灰色直方图表示，内禀谱指数由阴影直方图表示。均值观测谱指 数用灰色垂直虚线绘制，均值内禀谱指数由黑色垂直虚线绘制，它们是通过文[25]的方法获得。 Fig.1.Theobserved intrinsicspectral indicesversus theintrinsicspectralindices.Asshowninthefigure,theobservedpectral indices arerepresentedbythegrayhistogram,the intrinsicspectralindicesarerepresentedbytheshadow histogram.The meanobserved spectralindexisplottdbythegrayverticaldotted lineandthe meanintrinsic spectralidexisplottedbythe black vertical dotted line,they are obtained by the method of the Venters & Pavlidou (2007)[25].

甚高能内禀谱指数随红移的变化如图2。由于内禀谱是河外星系背景光未吸收的光谱，河外星系背景光吸收的影响被移除。从图2可以看出，样本的内禀谱指数没有红移随演化。这些源的中位数（黑色五角星）及其不确定度如图2所示，中位数的不确定度是根据源每个红移区间的分布估计的，并且对各个中位数的不确定性解释。同样，文[22]和文[26]认为耀变体辐射的甚高能伽玛射线与河外星系背景光吸收相互作用产生正负电子对。在这种情况下，伽玛射线光谱预计比1.5软（即， $\Gamma _ { \mathrm { i n t } } \geq 1 . 5$ ），它使内禀谱直接将观测谱与河外星系背景光吸收相联系,因此可以看到一个水平线直线 $\Gamma _ { \mathrm { i n t } } = 1 . 5$ ，当谱指数小于标准值(1.5)，这个谱可能是最硬的谱。样本中大部分的源在 $1 \sigma$ 内，指数在图2中大多超过1.5。

![](images/1c7e5bb11b08582348ee6e364acdacdd85b6667a05fe5872ff9c07af5b0a8c8f.jpg)  
图2甚高能内禀谱指数随红移的演变。图中，实心红点表示LBL天体，绿色空心正方形表示IBL天体，实心蓝色三角形表示 HBL天体。源的误差来自Fermi-LAT望远镜，H.E.S.S望远镜或 MAGIC 望远镜。实心黑色五边形代表每个红移区间内源的中位数（这里分为3个红移区间)，中位数的 $_ { 1 \sigma }$ 不确定度由灰色盒绘制。根据分析，源几乎比1.5软，这个下限用红色水平线绘制。  
Fig.2.Theevolutionofvery high energy intrinsic spectralindicesandredshift.As shownabove,solidreddotsrepresentLBL objects,grensquaresrepresent IBLobjects,andsolid blue triangles representHBLobjects.The erroris derived fromthe Fermi-LAT telescope,H.E.S.S telescope or MAGIC telescope.The solid black pentagonrepresents the medianof sources within each redshift bin (i.e.,we can get three redshift bins), the $_ { 1 \sigma }$ uncertain of the median are ploted by the gray box. According toouranalysis,our sources nearlysofter than1.5,andthis lower limit is ploted byared horizontal line.

# 3分析光谱拐折

通常，观测的高能谱（HE， $1 0 0 M e V \le E < 5 0 G e V$ ）可以通过 $d N / d E \propto E ^ { - \Gamma _ { H E , o b s } }$ 的幂律谱拟合，观测的甚高能光谱可以通过dNIdEETvE的幂律谱拟合,其中，ΓHE,bs和IvHE.obs分别是高能段和甚高能段的观测谱指数。在这些情况下，假设每个BLLac天体的内禀谱在高能段用 $d N / d E \propto E ^ { - \Gamma _ { H E , \mathrm { i n t } } }$ 拟合，在甚高能段用 $d N / d E \propto E ^ { - \Gamma _ { V H E , \mathrm { i n t } } }$ 拟合，其中 $\Gamma _ { \scriptscriptstyle H E , \mathrm { i n t } } \ , \ \Gamma _ { \scriptscriptstyle V H E , \mathrm { i n t } }$ 分别是在高能和甚高能内禀谱指数。由于甚高能伽玛射线光子被河外星系背景光吸收，预计在测量中有明显的能谱拐折是河外星系背景光吸收导致的[13]。根据上述分析，导出（204 $\Gamma _ { H E , o b s } = \Gamma _ { H E , \mathrm { i n t } }$ 和 $\Gamma _ { { \scriptscriptstyle V H E , o b s } } = \Gamma _ { { \scriptscriptstyle V H E , \mathrm { i n t } } } + \Delta \Gamma _ { { \scriptscriptstyle E B L } } ( E , z )$ 两个关系。由于河外星系背景光吸收随红移线性变化，预计△IEBL(E,z)=αz。

为了验证 $\Delta \Gamma _ { \scriptscriptstyle E B L } ( E , z ) = \alpha z$ 是否成立，首先研究河外星系背景光模型。由于不同的河外星系背景光模型可能导致 $\Delta \Gamma _ { _ { E B L } } ( E , z )$ 的变化。根据文[27-28]得到的所有河外星系背景光模型能谱

$$
\frac { d N } { d E _ { \mathrm { i n t } } } = \frac { d N } { d E _ { o b s } } e ^ { \tau _ { \gamma \gamma } ( E , z ) }
$$

其中， $\tau _ { \gamma \gamma } ( E , z )$ 为光谱的光深。对（3）式做以下研究：

(1)当 $E \le 0 . 1 T e V$ 时，根据电子对产生过程[29-30]可知， $\tau _ { \gamma \gamma } ( E , z ) = 0$ 。在这种情况下，河外星系背景光模型的选择不影响研究。

(2)当 $E { > } 0 . 1 T e V$ 时， $\tau _ {  { \gamma } } ( E , z ) \not = 0$ ，这意味着能谱已被吸收。但是当 $2 0 0 G e V \le E \le 1 0 T e V$ 时，对于不同经验方法得到的3种河外星系背景光模型来说， $\tau _ { \gamma \gamma } ( E , z )$ 相差不大[12，31-32]，这表明EBL模型对研究的影响不大。

基于上述分析，研究能段小于 $1 0 T e V$ ，意味着目前的河外星系背景光模型对研究的结果影响较小。在这种情况下，仔细研究河外星系背景光吸收与红移之间的关系，注意河外星系背景光吸收可以由甚高能观测谱指数和内禀谱指数之差 $\big ( \Gamma _ { { \scriptscriptstyle V H E , o b s } } - \Gamma _ { { \scriptscriptstyle V H E , i n t } } \big )$ ）代替。图3绘制了河外星系背景光吸收随红移的演变。通过线性回归△TEBL(E,z)=(1.83±0.14)z+(0.08±0.02)表示它们之间的关系。注意α=1.83±0.14≠0,$\beta = 0 . 0 8 \pm 0 . 0 2 \approx 0$ ，这明显地展示了河外星系背景光吸收的性质（无耀变体的物理性质）。

![](images/093e0b73d510347542649d3fa97930d38adc49ff4e950678769c4c2af52e9eb4.jpg)  
图3甚高能观测和内禀谱指数之间的差值随红移的变化。根据等式 $\Delta \Gamma _ { _ { E B L } } ( E , z ) = \Gamma _ { _ { V H E , o b s } } - \Gamma _ { _ { V H E , \mathrm { i n t } } }$ ，只有河外星系背景光吸收的影响。这些源的框，符号和颜色绘制与图2相同。  
Fig.3Thediferencebetween theobservedand intrinsic spectralindicesat VHEswithredshift.Acordingtotheequation, （202 $\Delta \Gamma _ { \mathit { \Pi } _ { E B L } } ( E , z ) = \Gamma _ { \mathit { V H E , o b s } } - \Gamma _ { \mathit { V H E , i n t } }$ ,there areonlythe EBL atteuation can affect this relationship.The boxes，symbols and colors of those sources are plotted same as Figure 2.

它们满足 $\Delta \Gamma _ { \scriptscriptstyle E B L } ( E , z ) = \alpha z$ 的相关性，并且在低红移区间河外星系背景光吸收的影响较小。

基于上述分析，甚高能观测谱指数减去高能观测谱指数得到观测谱拐折，即△bs =IvHE.obs-ΓHE.obs 。同样地，甚高能与高能内禀谱指数之间的差导出内禀谱拐折，△im =TvHE.imt-FHE.m。这样可以看到观测谱拐折随红移的演化，也就是说，（204号 $\begin{array} { r } { \Delta \Gamma _ { o b s } = \Gamma _ { V H E , \mathrm { i n t } } - \Gamma _ { H E , \mathrm { i n t } } + \Delta \Gamma _ { E B L } ( E , z ) = \Delta \Gamma _ { E B L } ( E , z ) + \Delta \Gamma _ { \mathrm { i n t } } = \alpha z + \beta , } \end{array}$ 其中，预计 $\Delta \Gamma _ { \mathrm { i n t } } = \beta \ , \ \beta$ 与内禀谱曲率有关。与之相对，整个样本的最佳拟合线为△I。b, =(2.42±0.38)z+(0.62±0.17)，注意 $\alpha = 2 . 4 2 \pm 0 . 3 8 \neq 0$ 和 $\beta = 0 . 6 2 \pm 0 . 1 7 \neq 0$ ，与数学模型相一致。可以得到观测能谱的拐折与河外星系背景光吸收和内禀光谱曲率（其他物理过程）有关。红移越高，观测光谱的拐折越明显，这意味着河外星系背景光吸收对处于低红移的源影响不大。

可以从理论模型的角度确定河外星系背景光吸收是否是导致大红移BLLac天体能谱拐折的主要原因。在研究拐折的起源之前，认识内禀谱曲率十分重要，它可以由峰值频率前后之间的谱指数之差代替[33]。结合伽玛射线辐射的河外星系背景光吸收，这个曲率最终变为数学分析公式 $\Delta \Gamma _ { o b s } = \Gamma _ { v H E , o b s } - \Gamma _ { H E , o b s }$ 相一致。根据上述分析，只需从理论模型的角度得到最终曲率和红移之间关系。选择截断幂律自康普顿辐射（broken power-law SSC）模型[34]和河外背景光模型4模拟BLLac 天体的能谱分布。同样的，文[35-36]通过相同的模型证明了他们的分析。根据上述分析，在图4中可得到一个灰色阴影条带，这个条带包括了河外星系背景光吸收、内禀光谱曲率及其误差。结合样本数据和数学模型，这个条带也证明了河外星系背景光吸收的影响不能被排除。

![](images/230f6607f8d17d81ca0145981bb6f5e2e9177192fe75868544fff2c792973342.jpg)  
图4观测谱拐折与红移的关系。其误差是甚高能和高能观测谱指数的误差之和，但是图上的框，符号和颜色的绘制与图2 相同。根据我们的数学模型 $\Delta \Gamma _ { o b s } = \alpha z + \beta$ ，我们可以得到一条红色虚线。灰色阴影包含了内禀谱曲率，曲率误差和 EBL吸收。注观测谱拐折在较高的红移中是明显的。  
Fig.4.Therelationshipbetweentheobserved spectrabreakandredshiftforthefullsmple.Theerrors barsare thesumof the errors of the VHEand HEobserved spectral indices,but the boxes,symbolsandcolorsofothers are ploted bysame as figure 2.According to our math model, $\Delta \Gamma _ { o b s } = \alpha z + \beta$ ，we can get a red dotes line.The gray shadow includes the intrinsicspectral curvature,the errorof curvatureandEBLatenuationclearly.Noted thattheobserved spectral break is obvious in the higher redshift.

虽然在 $0 \leq z \leq 2 . 1$ 区间内观测谱拐折的起源得到很好的证实，但是并不知道是否在较小的红移区间也能被证实。研究较小的红移区间内BLLac天体的河外星系背景光吸收变得重要。根据源的分布情况，选择红移小于0.6区间，减少源选择误差。对于 $z \le 0 . 6$ 的子样本如图5，最佳拟合线为 $\Delta \Gamma _ { o b s } = \left( 1 . 0 4 \pm 0 . 0 7 \right) z + \left( 0 . 4 2 \pm 0 . 3 7 \right)$ ，注意， $\alpha { = } 1 . 0 4 { \pm } 0 . 0 7 { \neq } 0$ 和$\beta = 0 . 4 2 \pm 0 . 3 7 \neq 0$ ，它们与上述分析一致。使用相同的方法获得灰色阴影带，发现河外星系背景光吸收和内禀光谱曲率在低红移区间中也发挥重要作用。结合整个样本的分析发现，源位于较高的红移中，观测能谱拐折更加明显。

基于观测能谱拐折的分析，有必要确定 $\Delta \Gamma _ { \mathrm { i n t } }$ 是否等于 $\beta$ 。将研究甚高能内禀谱指数和高能观测谱指数之间的差异（即： $\Gamma _ { { \ / { V H E } , \mathrm { i n t } } } - \Gamma _ { { \ / { H E } , o b s } }$ ，也称为内禀谱拐折）与红移之间的关系表示在图6中。由于 $\Gamma _ { _ { H E , o b s } } { = } \Gamma _ { _ { H E , \mathrm { i n t } } }$ ，并且内禀光谱如图4是没有河外星系背景光吸收的光谱，因此内禀谱拐折移除了河外星系背景光吸收的影响。在图中没看到内禀能谱拐折随红移变化。在这种情况下，利用 SSC 模型拟合得到灰色阴影条带，这个灰色阴影带满足 $\Delta \Gamma _ { \mathrm { i n t } } = \beta$ 。结合这些方法发现， $\alpha = 0$ 而 $\beta \neq 0$ ，表明河外星系背景光吸收不影响内禀能谱拐折，除了其他物理过程（内禀光谱曲率)。

![](images/13340cf8184380380765ed21e53394d5b74007b8dff08f1a89a4a28cdd898915.jpg)  
图5子样本 $z \leq 0 . 6$ 时观测谱拐折与红移之间的关系。这些框，符号和颜色与图2完全相同。 Fig.5.The relationship between the observed spectral break and redshift forthe subsample with $z \le 0 . 6$ .The boxes,symbols and colors of these sources are exactly same as figure 2.

![](images/e6e6817eb4359c8a987a01c3b9668e2905db71512f7f549c1f9eada7703cb2f9.jpg)  
图6甚高能内禀谱指数与高能谱指数之差随红移的演变。河外星系背景光吸收已被内禀谱拐折的特性所排除，只有耀变体物理（内禀谱曲率）才能影响这种关系。灰色阴影条带带与数学模型 $\Delta \Gamma _ { \mathrm { i n t } } = \beta$ 一致。图中的框，符号和颜色与图2相同。

Fig.6.Thediferencebetweenrelationshipbetwee theintrisic spectral indexat VHEsand spectralindexat HEs evolve with redshift.TheEBLatenuation has been excluded bythe propertyof the intrinsic spectral break,onlythe blazarphysics (intrinsicspectralcurvaturecanaectiselatioship.hegayshdobandhasaonsistentwithmathdel $\Delta \Gamma _ { \mathrm { i n t } } = \beta$ The boxes,symbols and colors of those sources are plotted same as Figure 2.

# 4结论与讨论

本文收集了126个大红移BLLac 天体GeV-TeV 能谱指数，分析伽玛射线辐射的观测光谱和内禀光谱。分析发现：观测谱指数和内谱指数的离散程度只有微小的差异（即，观测光谱 $\sigma _ { 0 , o b s } = 1 . 4 3$ ；内禀光谱 $\sigma _ { 0 , \mathrm { i n t } } = 1 . 5 5$ ；两个分布的置信区间相似)，但均值观测谱指数明显高于均值内禀谱指数（即，观测光谱 $\Gamma _ { 0 , o b s } = 2 . 9 6$ ；内禀光谱 $\Gamma _ { 0 , \mathrm { i n t } } = 2 . 5 5 \ \AA$ ，这意味着内禀光谱是一个硬谱，而且观测光谱被河外星系背景光吸收使均值光谱指数降低。

本文主要讨论观测能谱拐折和红移之间的关系，利用一个数学模型 $\Delta \Gamma _ { o b s } = \alpha z + \beta$ 。对于这个数学模型，有下列3种情况：

(1)当 $\alpha \neq 0$ 而 $\beta = 0$ 时，方程可以用河外星系背景光吸收与红移之间的关系代替，△IEBL(E,z)=ΓvHE.obs-ΓvHE.int，这不是观测能谱的拐折。在这种情况下，发现样本数据与线性回归结果一致，这也表明河外星系背景光吸收对低红移的源影响较小。

(2)当 $\alpha \neq 0$ ， $\beta \neq 0$ 时， $\Delta \Gamma _ { o b s } = \alpha z + \beta$ 是最终方程，这是观测能谱拐折。利用线性回归和 SSC 的模拟、河外星系背景光模型验证发现，样本数据与这些方法得到的结果一致。由于 $\alpha \neq 0$ ，河外星系背景光吸收的影响不能被移除，而 $\beta \neq 0$ 时,内禀曲率的影响也不能被移除。

(3)当 $\alpha = 0$ 而 $\beta \neq 0$ 时，该方程涉及甚高能内禀谱指数与高能观测谱指数的差，即△int =ΓvHE.int-ΓHE.obs。在这种情况下讨论的是内禀谱拐折，而河外星系背景光吸收的特性已移除。从内禀谱拐折的分布和理论模型模拟，得出内禀谱曲率（其它物理过程）可以影响这种关系。

得到统计结果 $\alpha = 2 . 4 2 \pm 0 . 3 8 \neq 0$ ， $\beta = 0 . 6 2 \pm 0 . 1 7 \neq 0$ 。这表明河外星系背景光吸收和其它一些物理过程在观测能谱拐折中起重要作用。同时也验证了河外星系背景光吸收是大红移 BLLac 天体能谱拐折的主要因素之一。

已经验证河外星系背景光吸收是大红移BLLac天体能谱拐折的主要因素之一，但是根据统计结果 $\beta \neq 0$ ，说明能谱拐折还与 $\beta$ 有关，需要对 $\beta$ 进行讨论。对于能谱分布的拟合很多不同的方法，文[14]提出对数抛物线 SSC 模型获得内禀谱曲率，但利用截断幂律 SSC 模型获取。不同的方法得到不同的电子谱，也使内禀谱曲率不同，从其它物理过程影响内禀谱拐折。主要研究能谱拐折，文[11，37]认为观测能谱拐折随红移的演变包括了耀变体的物理性质和河外星系背景光吸收。但文[18]认为光谱拐折可验证次级成分存在的假说。在样本研究中存在部分硬谱，预计宇宙射线质子与河外星系背景光子相互作用产生二次伽玛射线成分，也可以解释为高能伽玛光子在源附近震荡产生轴子类型粒子，在到达观测者前又转化为伽玛光子[19]。

# 参考文献：

[1] Paggi A.Flares in Blazars[D]. Roma :Universita degli Studi di Roma, 2009.   
[2] 毛李胜．费米 BL Lac 天体的中红外-伽马波段辐射相关性(英文)[J].天文研究与技术-国 家天文台台刊,2013,10(2):103-109.   
Mao Lisheng. Revisiting the correlation between γ-ray and Mid-Infrared Fluxes of the BL Lac objects detected by the FERMI satellite[J]. Astronomical Research & Technology—Publications of National Astronomical Observatories of China,2013,10(2):103-109.   
[3] Maraschi L, Ghiselini G, Celoti A.A jet model for the gamma-ray emiting blazar 3C 279[J]. The Astrophysical Journal, 1992, 397: L5-L9.   
[4] Dwek E，Krennrich F. Simultaneous constraints on the spectrum of the extragalactic background light and the intrinsic TeV spectra of Markarian 421, Markarian 501,and ${ \mathrm { H } } 1 4 2 6 +$ 428[J]. The Astrophysical Journal, 2005, 618(2): 657-674.   
[5] Sikora M, Begelman M C,Rees M J. Comptonization of diffuse ambient radiation by a relativistic jet: the source of gamma rays from blazars?[J]. The Astrophysical Journal,1994, 421: 153-162.   
[6] Abdo A A，Ackermann M,Ajelo M,et al. Early Fermi Gamma-ray Space Telescope observations of the quasar 3C 454.3[J]. The Astrophysical Journal, 2009, 699(1): 817-823. [7] Abdo A A,Ackermann M, Ajello M, et al. Fermi Gamma-ray Space Telescope observations of the Gamma-ray outburst from 3C454. 3 in November 2010[J]. The Astrophysical Journal Letters, 2011, 733(2): L26-L32.   
[8] Hauser M G, Dwek E. The cosmic infrared background: measurements and implications 1[J]. Annual Review of Astronomy and Astrophysics, 2001, 39(1): 249-307.   
[9] Stecker FW, De Jager O C, Salamon M H. TeV gamma rays from 3C 279-A possible probe of origin and intergalactic infrared radiation fields[J]. The Astrophysical Journal，1992,390: L49-L52.   
[10] Stecker F W, Jager O C D. Absorption of very high energy Gamma-rays by intergalactic infrared radiation: a new determination[J]. Astronomy & Astrophysics, 1998,334(3):L85-L87. [11] Stecker F W, Malkan M A, Scully S T. Intergalactic photon spectra from the far-IR to the UV Lyman limit for $\cdot$ and the optical depth of the universe to high-energy gamma rays[J]. The Astrophysical Journal, 2006, 648: 774-783.   
[12] Franceschini A, Rodighiero G, Vaccari M. Extragalactic optical-infrared background radiation, its time evolution and the cosmic photon-photon opacity[J]. Astronomy & Astrophysics,2008, 487(3): 837-852.   
[13] Ackermann M, Ajello M, Allafort A, et al. The imprint of the extragalactic background light in the gamma-ray spectra of blazars[J]. Science,2012, 338(6111): 1190-1192.   
[14] Sanchez D A,Fegan S, Giebels B. Evidence for a cosmological effect in $\gamma$ -ray spectra of BL Lacertae[J]. Astronomy & Astrophysics,2013, 554: A75-A83.   
[15] Kneiske T M, Bretz T, Mannheim K,et al. Implications of cosmological gamma-ray absorption-I. Modification of gamma-ray spectra[J]. Astronomy & Astrophysics, 2004, 413(3): 807-815.   
[16] Imran A, Krennrich F. Detecting a unique EBL signature with TeV gamma rays[C]// International Cosmic Ray Conference. 2007:981-984.   
[17] Tavecchio F, Mazin D. Intrinsic absorption in 3C 279 at GeV—TeV energies and consequences for estimates of the extragalactic background light[J]. Monthly Notices of the Royal Astronomical Society: Letters, 2009,392(1): L40-L44.   
[18] Essey W, Kusenko A. On weak redshift dependence of gamma-ray spectra of distant blazars[J]. The Astrophysical Journal Letters,2012, 751(1): L11-L14.   
[19]Zheng】 T.Evidence for secondary emission as the origin of hard spectra in TeV blazars[J]. The Astrophysical Journal, 2013,764(2): 113-117.   
[20] Zheng Y G, Yang Y,Kang S J.Bethe-Heitler cascades as a plausible origin of hard spectra in distant TeV blazars[J Astronomy & Astrophysics,2016, 585: A8-A15.   
[21] Acero F, Ackermann M, Ajello M, et al. Fermi large area telescope third source catalog[J]. The Astrophysical Journal Supplement Series, 2015, 218(2): 23-63.   
[22] Gilmore R C, Somerville R S, Primack JR,et al. Semi-analytic modelling of the extragalactic background light and consequences for extragalactic gamma-ray spectra[J]. Monthly Notices of the Royal Astronomical Society,2012, 422(4): 3189-3207.   
[23] 白金明．BL Lac 天体的光变[J]．天文台台刊，2000(1):58-60.   
Bai J. Variability in the BL Lac objects.[J]. Publications of Yunnan Observatory, 20o0(1):58-60 [24] 米立功，崔朗，胡开宇．59 个耀变体的15.3GHz光变周期分析［J]．天文研究与技术, 2015，12(4) :410-416.   
Mi Ligong, Cui Lang，Hu Kaiyu. An analysis of periods of light variations of 59 blazars observed at 15.3GHz[J]. Astronomical Research & Technology, 2015， 12(4):410-416.   
[25] Venters T M, Pavlidou V. The spectral index distribution of EGRET blazars: prospects for GLAST[J]. The Astrophysical Journal, 2007, 666(1): 128-138.   
[26] Aharonian F, Akhperjanian A G, Bazer-Bachi A R,et al. A low level of extragalactic backgroundlightasrevealedbygamma-raysfromblazars.[J].Nature,2006, 440(7087):1018-1021.   
[27] Albert J, Aliu E, Anderhub H, et al. Observation of very high energy $\gamma$ -rays from the AGN 1ES $2 3 4 4 + 5 1 4$ in a low emission state with the MAGIC telescope[J]. The Astrophysical Journal, 2007,662(2): 892-899.   
[28] Raue M, Mazin D. Optical depth for VHE $\gamma$ rays from distant sources from a generic EBL density[J]. International Journal of Modern Physics D, 2008,17(09): 1515-1520.   
[29] Rubtsov G I, Troitsky S V. Breaks in gamma-ray spectra of distant blazars and transparency of the Universe[J]. JETPLetters,2014,100(6):355-359.   
[30] Dzhatdoev T A. On conservative models of "the pair-production anomaly” in blazar spectra at Very High Energies[C]. Journal of Physics: Conference Series. 2015.   
[31] Dominguez A,Primack JR, Rosario D J, et al. Extragalactic background light inferred from AEGIS galaxy-SED-type fractions[J]. Monthly Notices of the Royal Astronomical Society, 2011, 410(4): 2556-2578.   
[32] Finke JD, Razzaque S, Dermer C D. Modeling the extragalactic background light from stars and dust[J]. The Astrophysical Journal, 2010,712(1): 238-249.   
[33] Chen L. Curvature of the spectral energy distributions of blazars[J]. The Astrophysical Journal, 2014, 788(2): 179-194.   
[34] Massaro F. Spectral evolution of the high energy emisson from TeV BL Lac Objects[D]. Roma $\because$ Universita degli Studi di Roma, 2008.   
[35] Albert J, Aliu E, Anderhub H, et al. Discovery of Very High Energy γ-Rays from 1ES $1 0 1 1 +$ 496 at $\mathbf { z } { = } 0 . 2 1$ 2[J]. The Astrophysical Journal Letters, 2007, 667(1): L21-L24.   
[36] Aharonian F, Akhperjanian A G, De Almeida UB, et al. Discovery of VHE gamma-rays from the distant BL Lacertae 1ES 0347-121[J]. Astronomy & Astrophysics, 2007, 473(3): L25-L28. [37] Stecker F W, Scully S T. Derivation of a relation for the steepening of Tev-selected blazar $\gamma$ -rayspectra with energy and redshift[J]. The Astrophysical Journal Lettrs，2O10,709(2): L124-L126.

# GeV-TeV Energy Spectral Analysis of BL Lac objects

Zhong Wei， Liu Wenguang， Zheng Yonggang (1 School of physics and Electronic Information,Yunnan Normal University,Kunming 65o5oo,China) (2the KeyLaboratoryof the High Energy Astrophysicsof Universityof Yunnan Provinceof China,65o50o,China) Abstract: The research compile both the high energy and very high energy observed spectral index of 126 BL Lac objects and employ a math model ( $\Delta \Gamma _ { o b s } = \alpha z + \beta )$ to study the energy spectral break (the difference between very high energy and high energy observed spectral indices). Our goal is to determine whether the extraterrestrial galactic background (EBL) attenuation is an exclusive origin for the energy spectral break of the distant BL Lac objects. The results of statistical analysis show: $\alpha \neq 0$ and $\beta \neq 0$ . It also shows the energy spectral break contributes both to the EBL attenuation and some other physical processes.

Key words: Galaxies $\ ;$ BL Lac objects；Radiation mechanism ;Non-thermal emission; Statistics.