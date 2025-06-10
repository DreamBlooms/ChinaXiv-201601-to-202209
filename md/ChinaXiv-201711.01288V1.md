# 基于能量集中度的广角望远镜自动调焦快速清晰度评价算法

苑嘉辉1,²，蔡洪波1，魏建彦1(1.中国科学院国家天文台空间天文与技术重点实验室，北京100012；2.中国科学院大学，北京100049)

摘要：地基广角相机阵由36个广角相机拼接组成，主要观测目标为光学瞬变源，具有超大视场、高时间采样率、实时数据处理的技术特点。实时自动调焦对于系统自动化观测与提高科学产出至关重要。自动调焦的核心目标为提高图像的能量集中度，目前常用评价指标如星像 $5 0 \%$ 能量半径、点扩散函数的半高全宽均存在计算量过大的问题。基于地基广角相机阵调焦过程中星像中心区域能量变化大、星像总流量及分布范围基本不变这一点，提出了通过统计中心区域流量占星像总流量百分比的快速清晰度评价算法，并对两个流量孔径展开详细研究。进一步对算法中流量计算方法进行简化，细化了背景取值、选星标准、选星数目等对算法有影响的参数，最终确立了一套适用于地基广角相机阵系统实时自动调焦的清晰度评价算法。算法结果准确，单图运算时间在0.1s左右，满足系统快速自动调焦的需求。

关键词：图像清晰度；广角望远镜；自动调焦；能量集中度中图分类号：TP311 文献标识码：A 文章编号：1672-7673(2016)04-0472-09

我国兴建中的中法天文卫星地面项目地基广角相机阵（Ground Wide Angle Cameras，GWAC）[1-2],其主要科学目标为光学瞬变源(如伽马暴)的搜寻。地基广角相机阵共有36 台广角望远镜，每台望远镜相机参数为口径 $1 8 ~ \mathrm { c m }$ ，焦距 $2 2 \mathrm { c m }$ ，采用像元大小为 $1 2 \mu \mathrm { m }$ 的 $4 \mathrm { k } \times 4 \mathrm { k }$ CCD，单个视场为150平方度，拼接视场达到约5000平方度。系统时间采样率为 $1 5 \mathrm { ~ s ~ }$ ，并进行实时数据处理。在大视场、高时间采样率方面较同类天文设备有很大提升。

对于地基广角相机阵，探测能力是核心技术指标。探测能力深一个星等，可探测源数目增加3倍左右，可大大增加探测到瞬变源的几率。地基广角相机阵为短焦比系统，景深仅为 $2 8 ~ \mu \mathrm { m }$ 。在观测过程中，受温度等因素的影响，焦点会发生移动[3]，使星像能量弥散，造成系统探测能力降低。为保证36台望远镜同时高效工作，自动调焦必不可缺。而调焦的核心目标即为保持系统工作在星像能量最集中的状态下，提高科学产出。

对星像能量集中度直观的评价指标为星像能量分布范围的大小，如常用的星像 $5 0 \%$ 能量半径[4],得到星像能量分布的半径需进行多次孔径测光得到能量增长曲线，再插值得到一定能量对应的半径，计算量过大。地基广角相机阵样机系统[5]采用常用天文软件 IRAF计算的点扩散函数（Point SpreadFunction，PSF)的半高全宽值(FWHM)反应能量集中度，这也是目前天文领域常用的方法[6-8]。在图像处理领域，点扩散函数轮廓也是检验图像质量的重要手段[9」。半高全宽的结果在精度上满足需求，但实际应用中，这种方法受模型选择、拟合方法等因素的影响较大，且涉及到插值、拟合等多种运算，计算量也比较大。IRAF计算单幅图的时间在10s左右，地基广角相机阵 $1 5 \mathrm { ~ s ~ }$ 的数据处理时间分配给清晰度评价的计算时间不超过 $2 \mathrm { ~ s ~ }$ 。显然与地基广角相机阵快速评估图像清晰度的需求不太相符。

本文从自动调焦的根本目标出发，通过研究调焦过程中星像能量变化的规律，发现星像总能量分布的范围随调焦过程的变化较小，离焦对星像带来的影响主要表现为中心的流量向周围扩散。基于此提出以星像中心区域 $\boldsymbol { r }$ 内流量占较大半径 $R$ 内流量的百分比，表征星像的能量集中度，并作为自动调焦系统的清晰度评价标准，半径 $R$ 应包含星像较大百分比流量，其中流量值在调焦过程中相对稳定;$\boldsymbol { r }$ 为固定较小值，是对离焦程度最为敏感的星像中心区域，其中流量随调焦过程变化较大。通过对计算方案中相关参数与方法的多种简化，实现了算法加速。最终结果焦点位置准确，单图运算量在千量级，运算时间小于0.1s，较IRAF计算半高全宽的方法有两个量级的加速，充分满足了地基广角相机阵自动调焦的需求，算法与研究过程可为同类望远镜系统提供参考。

# 1快速算法原理

在对两种传统的能量集中度评价方法进行研究和评估的基础上，本文通过研究星像能量随调焦过程变化的规律，确定了一种快速评价算法。

# 1.1传统能量集中度评价方法

(1)星像能量的分布范围

表征星像能量集中度的直观性指标是星像一定百分比的能量分布半径，常用 $5 0 \%$ 的能量半径。而得到能量半径的过程可以总结为：对星像进行密集的孔径测光得到其总能量及能量增长曲线；计算出 $5 0 \%$ 能量值，对能量增长曲线进行插值计算对应的半径值。

显然，这种方法需进行多次孔径测光和插值运算，运算量很大。对于地基广角相机阵而言，由于大视场的特点，视场中星像数目众多，星像为欠采样状态。调焦时须在视场中均匀选择多颗星进行计算，这种方法对于地基广角相机阵系统而言，不满足快速调焦的需求。

(2)点扩散函数的半高全宽值

点扩散函数是对星像轮廓的描述，其半高全宽值可反映星像轮廓的尖锐程度，也是能量集中程度的一种描述。以常用的高斯模型为例，其点扩散函数如(1)式，而半高全宽如(2)式，半高全宽与决定点扩散函数轮廓的参数 $\sigma$ 直接相关，也直接反映了能量集中度。

$$
\begin{array} { r } { I _ { _ { ( x , \ y ) } } = H \times e ^ { \frac { - ( x - x _ { 0 } ) ^ { 2 } + ( y - y _ { 0 } ) ^ { 2 } } { 2 \sigma ^ { 2 } } } + B , } \end{array}
$$

$$
F W H M = 2 \sqrt { 2 \mathrm { l n } 2 } \sigma \approx 2 . 3 5 5 \sigma ~ .
$$

这种评价方法在多个系统应用，也是目前样机系统采用的方法。但地基广角相机阵广角望远镜系统其星像轮廓在视场不同位置变化较大，与理想点扩散函数轮廓存在一定偏差。如图1，在视场边缘，星像轮廓的“拉伸”现象比较明显。另一方面，地基广角相机阵系统调焦好的图像其半高全宽值在1.6左右，星像处于欠采样状态，数据拟合本身难度较大，且拟合过程中包括插值、非线性拟合等计算，运算量较大。IRAF计算单幅图（200颗星)的时间约为10s，远远不能满足系统需求。

# 1.2基于能量集中度的快速算法

# (1)算法原理

理论上，在相同曝光时间内，望远镜接收到的星像能量相同，  
离焦对系统图像带来的影响是星像轮廓变弥散，即中心强度逐渐  
减弱，更多的能量向周围扩散[10]。本文通过对地基广角相机阵调焦图像进行分析，印证了这一规律。

![](images/c7391e4aa6e9daf5ed89ee9539fa7e6b587d6a822c95a059737ddaf248dbdb2f.jpg)  
图1视场边缘星  
Fig.1Stars on the edge of the image

调焦序列图像的生成方案为：以固定步长( $5 \mu \mathrm { m } \dot { }$ )沿光轴单向移动CCD靶面，产生61幅图像，过程中图像由模糊变清晰再变模糊。经IRAF 测定以及肉眼检测后，焦点位置在标号30的这幅图附近。在调焦图像中选取了同一批约200 颗星，对这些星进行半径从1.0到9.0的孔径测光。

统计固定孔径下流量值随调焦过程的变化，结果如图2。图2中 $x$ 轴为沿光轴焦距， $y$ 轴为流量值。可以看出，不同测光半径内流量值随调焦过程变化的幅度差别很大。

![](images/8f1a0aba1328620d2ec02eb88c160a46300fda87644db49c547283f9f43632ee.jpg)  
图2不同半径内流量值随调焦过程变化情况 Fig.2The changing energy during focusing enclosed in different

计算某一孔径下，调焦过程中流量的变化值与过程中均值的比值，以此作为该孔径内流量随调焦变化大小的指标。比例越大，说明该半径内流量随调焦过程变化越剧烈；比例越小，说明该半径内流量随调焦过程变化越小，结果如表1。由表1可以看出，测光半径越小，其中流量随调焦过程变化越大，而较大半径内流量随调焦过程变化很小。

表1不同孔径内流量值随调焦过程变化的大小  
Table 1The relative change of flux within different radiuses   

<html><body><table><tr><td>测光半径/pixel</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td></tr><tr><td>流量相对变化</td><td>1. 33</td><td>1.00</td><td>0.76</td><td>0.58</td><td>0.46</td><td>0.37</td><td>0.30</td><td>0.26</td><td>0.22</td></tr></table></body></html>

由此提出，对调焦敏感的中心区域 $\boldsymbol { r }$ 内流量占星像总流量的比值，直接与星像能量集中程度相关，可作为系统的清晰度评价函数。该算法的关键即为两个测光的半径，代表中心区域的半径 $\boldsymbol { r }$ ，测定星像总流量的半径 $R$ ，其中 $R$ 范围内流量值随调焦过程变化较小， $\boldsymbol { r }$ 为固定值，且代表对调焦敏感的中心较小的区域。

$R$ 值的选取理论上应选取总流量所在的半径。在实际图像上，这一半径会随调焦过程有一定变化，通过孔径测光计算了多颗星平均 $7 0 \% \sim 1 0 0 \%$ 能量所占的半径值，结果如图3与表2。图3中横轴为沿光轴焦距，纵轴为pixel值。

由图3可以看出，星像 $70 \% \sim 1 0 0 \%$ 能量所在的半径，随调焦过程的变化比较平缓，结合图2，可以说明，星像能量分布的总范围随调焦过程变化不大。因中心流量的变化幅度很大，因此对 $R$ 内包含流量的百分比可以存在小幅波动而不影响比值结果的趋势。

因此不同图像中， $R$ 可以取固定值。这样可以省去对每幅图进行孔径测光测定 $R$ 值的过程，将大大简化运算。

![](images/6c65f6300bee4edb204a23b3f7337b251712dee4c78f9c48fba984d8b3c5b68c.jpg)  
图3星像 $7 0 \% \sim 1 0 0 \%$ 能量所占的半径值Fig.3The radius of $70 \% \sim 1 0 0 \%$ energy of stars

表2 $70 \% \sim 1 0 0 \%$ 能量的半径在调焦过程中的均值与方差  
Table 2 The mean and variance of radiuses containing $70 \% - 1 0 0 \%$ energy   

<html><body><table><tr><td></td><td>70%能量</td><td>80%能量</td><td>90%能量</td><td>100%能量</td></tr><tr><td>均值/pixel</td><td>3.527</td><td>4. 446</td><td>5. 937</td><td>9.329</td></tr><tr><td>方差/pixel</td><td>0.925</td><td>0.998</td><td>1. 016</td><td>0.784</td></tr></table></body></html>

对地基广角相机阵图像进一步研究发现，由表1可以看出， $70 \% \sim 9 0 \%$ 的能量对应所在半径值均匀分布增加1pixel左右，而 $9 0 \% \sim 1 0 0 \%$ 能量所在半径增加了4pixel。这说明地基广角相机阵星像轮廓其“拖尾”比较长。而 $100 \%$ 能量孔径较大，如图4，使用较大的 $100 \%$ 能量半径计算流量值，很容易受密集星场的影响导致流量计算错误。而 $8 0 \% \sim 9 0 \%$ 能量分布的半径只为 $100 \%$ 能量半径的1/2左右，选取 $8 0 \%$ \~$9 0 \%$ 半径不仅可提高流量计算精度，同时还降低运算量。

综合上述，选取 $R = 5$ ，即包含 $8 0 \% \sim 9 0 \%$ 能量的半径大小作为计算流量值的半径。

$r$ 值为计算中心流量的半径值，选取原则为尽量选取对于调焦过程敏感的中心区域，由表1可以得出， $\boldsymbol { r }$ 越小，其对调焦过程越敏感，

![](images/960cff6da0955388204d2d3a059284666c9d72291304601a955a275d63de5098.jpg)  
图4密集星像分布示意图(红色圆形半径为9，绿色圆形半径为5)Fig.4An example of dense stars

为验证上述结论，根据地基广角相机阵系统调焦好的图像其半高全宽约为1.6左右，模拟产生了$F W H M = 3 . 0 \sim 1 . 5 \sim 3 . 0$ 以0.1为间隔的一系列图像。并对 $r = 1$ ，2，3的结果归一化后进行比较。

图5中 $x$ 轴为模拟图像编号， $y$ 轴为不同 $r$ 取值下归一化的算法结果。可以看出， $\boldsymbol { r }$ 值越小，曲线越锐，且曲线起伏越少，可以说明越接近星像中心的范围对离焦程度越敏感。为提高自动调焦的敏感度，选取 $r = 1$ 。

# (2)算法流程

系统自动调焦的流程如图6（a）。系统设计中，清晰度评价是在对图像找星之后，系统采用快速找星软件包Sextractor生成星表，对每幅图进行清晰度评估后，与系统调焦阈值进行比较以确定是否需要调焦。图6(b)是本文快速算法的流程，具体如下：

(1)确定计算星像流量的半径 $R$ ，并测定在距离星像中心 $R$ 范围内该星的总流量。(2)将距离星像中心距离小于 $\boldsymbol { r }$ 的像素的流量(像素值减去背景值)除以总流量并相加，得到占总流量的百分比。

因单一星像统计具有很大不确定性，选择 $N$ 颗星进行(1）、（2)步操作并叠加，作为最终清晰度评价参数。

![](images/da5ec8d85c62f949e486b4b80048e76a1eff45b9ef3e9ba87a7d3dc097cf1272.jpg)  
图5不同中心流量计算范围 $\boldsymbol { r }$ 在模拟图像上的结果Fig.5The influence of different $r$ on simulate images

![](images/ad4cc2e19a1e81e09012990dffe382fd3e45bda1b69505c1b5462241a6b32b28.jpg)  
图6自动调焦系统.（a）自动调焦判断过程；（b）清晰度评价算法过程 Fig.6The auto-focusing system，the left is the focusingflow，the right is theflow of image definition flow

# (3)小结

调焦过程中，星像能量分布的总体范围随调焦过程变化缓慢，而中心流量随调焦过程变化剧烈。以固定的中心区域内流量占固定较大半径内流量的比例可以代表星像能量集中度，从而对图像清晰度进行快速评估。

该方法无需在调焦过程中不同图像之间选择相同的星，从而降低了对系统跟踪的要求，且只需对星像进行两次孔径测光，计算量较小，便于针对系统进行后续的优化与加速。

# 2算法设计与优化

影响计算的其他因素包括流量的计算方案、背景值的选取、参与计算的星的数目以及星像中心精

度等。在设计这些方法与参数时，从自动调焦的需求出发，对孔径测光不追求流量值的完全准确，只需满足符合星像能量变化的趋势即可，且相比散焦特别严重的图像，更为关注焦点位置附近的图像特点。

# (1)流量计算方案的简化

本文使用方形区域内流量直接叠加计算流量值以简化运算。因中心区域 $r = 1$ ，方形面积与圆形面积相差不大，对中心区域流量影响不大；而外圈 $R$ 的边缘像素内流量已经衰减得较小，因此直接使用方形区域进行计算。

常规的圆形流量统计中，涉及到对于只有一部分在统计范围内的像元流量值的统计。计算亚像元流量值的方法有多种：如IRAF对星像进行二维插值，得到亚像元内的流量值[11]；而 Sextractor 将像素分为 $5 \times 5$ 个亚像元对流量值进行统计[12]。为达到较高的测光精度，这两种孔径测光的方法均对亚像元的部分进行了切分计算，这显然大大增加了运算量。

图7中为 $R = 5$ 时，简化方法计算流量值相较于IRAF和Sextractor计算流量值结果的相对误差值。图7中横轴为沿光轴焦距，纵轴表示流量相对误差值。由图7可以看出，简化的计算方法相比IRAF和Sextractor而言，流量计算相对误差在0.1左右。

在实际自动调焦工作过程中，不会等到像质很差才进行调焦，焦点附近为调焦的重点关注区域。在调焦敏感区域，简便方案误差很小，仅为0.02左右。

# (2)背景值的选取

在流量统计时，背景值一定程度影响流量计算。对于大视场望远镜，背景值的分布受视场、天气等因素的影响较大，存在一定程度的不均匀性。在天文领域测光时，对单星背景值统计有多种方法[13]。其中IRAF对于单星背景值的计算方

![](images/69e1bfd44abcd5d0baecfa39fbe7b96c6f095cece09b7363241a922ffe30196c.jpg)  
图7简化流量计算方案与IRAF和Sextractor的相对偏差( $R = 5$ ）  
Fig.7The relative error of simple method( $R = 5$ ）

法是将距离星像中心一定半径外的环形区域进行统计和计算["1]。Sextractor 的计算方案将图像分为固定大小的区域，对区域内背景值进行统计后，通过二维三次样条插值计算星像位置的背景值[12]。

本文中因计算流量范围较小，且视场中星的数目很多，通过选取信噪比高于20的非饱和亮星，可以有效降低背景值在流量计算中的影响。因此省略了计算单星背景值，使用固定经验值以简化运算。

# (3)统计星数的选取

由于单颗星统计误差较大，且考虑到地基广角相机阵大视场的特点，本文算法在视场中均匀选取$N$ 颗较亮的星作为算法的参考星。 $N$ 的大小直接决定算法的速度， $N$ 值越大，算法计算量越大，因此在保证算法精度的前提下， $N$ 值越小越好。

在调焦序列图像中分别均匀选择100、200、300颗星，对结果进行归一化后进行比较，结果如图8。图8中 $x$ 轴为沿光轴焦距， $y$ 轴为归一化清晰度评价结果。可以看出， $N = 1 0 0$ 的曲线不够平滑，特别是在调焦敏感区域存在毛刺， $N = 2 0 0$ 、300的曲线足够平滑，满足清晰度评价的要求。

综合考虑速度与精度的因素，对于地基广角相机阵系统，选取 $N = 2 0 0$ 。

# (4)星像中心精度

系统设计中在图像清晰度评价之前使用 Sextractor找星生成星表，Sextractor 计算星像中心具有速度快、精度高的特点。实际上本文算法是对星像中心周围一定范围内流量进行叠加，中心精度的大小一定范围内不影响算法统计区域，因此算法对于星像定心精度不敏感。

本文对算法中使用的星像中心分别用向下取整（图9中int_center)和四舍五入取整（图9中 round_center)的方式进行计算，清晰度评价结果如图9，图9中 $x$ 轴为沿光轴焦距， $y$ 轴为归一化的算法结果。可以看出，两种简化星像中心后的结果，焦点位置与使用 Sextractor 计算的中心结果基本一致，但曲线毛刺较多。这说明星像中心精度对于本文算法有效性影响不大。在本文中结合地基广角相机阵系统设计方案，采用 Sextractor的结果。原则上，结合一定判定策略，本文算法同样可以使用星像流量最大的像素坐标作为星像中心，不影响算法的有效性，其他望远镜系统可作为参考。

![](images/ed46229d9cce60079c5aa33240f3d14634469084c30e70b22b72ebd7503573cc.jpg)  
图8不同星像数目的计算结果Fig.8The result of different $N$

![](images/bfc07257a8fca72a249d96ed47e1600f537d4a7067dd32e581af575fbee0df7d.jpg)  
图9不同星像中心的算法结果Fig.9The result of different center caculation

# 3算法验证

(1)调焦图像结果

本文以地基广角相机阵系统两组不同步长的从离焦到准焦再到离焦的图像进行实验，并与IRAF计算的点扩散函数的半高全宽值进行比较，检验算法对自动调焦的有效性。

图10为 $5 ~ { \mu \mathrm { m } }$ 步长的调焦序列图像的结果，图11为 $1 0 ~ \mu \mathrm { m }$ 步长的调焦序列图像的结果，两图中$x$ 轴为沿光轴焦距， $y$ 轴为归一化的算法结果，其中为方便比较，将IRAF计算的半高全宽值曲线进行了翻转。

![](images/b3ec2c433b66ac16684ce06a7b4d569f8c23de2fa4d0a6c50183b608360f768f.jpg)  
图10 算法在 $5 ~ { \mu \mathrm { m } }$ 间隔序列图像的结果 Fig.10The final result on focusing images with a gap of ${ 5 \mu \mathrm { m } }$

![](images/88c9b6473a84e78907f590862ab93cffe353d9d063f84d62e3db0f70cc1c7641.jpg)  
图11算法在 $1 0 ~ \mu \mathrm { m }$ 间隔序列图像的结果 Fig.11The final result on focusing images with a gap of $1 0 \mu \mathrm { m }$

由图10和图11可以看出，在不同组实验中，本文算法找到的焦点位置与FWHM方法计算出的位置均只相差一幅图，分别对应 $5 ~ { \mu \mathrm { m } }$ 与 $1 0 ~ \mu \mathrm { m }$ 的距离。考虑到地基广角相机阵相机的景深为 $2 8 ~ \mu \mathrm { m }$ ，在 $2 8 \mu \mathrm { m }$ 范围内均可认为是系统的焦点位置，曲线中也可以看出，焦点附近图像清晰度评价结果相差不到 $1 \%$ 。因此，本文算法可以正确找到系统焦点的位置。

# (2)计算时间

本文算法对于地基广角相机阵系统1.1Giga-pixel的图像而言，单图运算量为 $N * R * R = 5 0 0 0$ 次的量级，运算量非常小。算法经Python实现，单图运算时间约为0.1s左右，作为参考，相同的选星，IRAF单幅图运算时间约为 $1 0 \mathrm { { s } }$ 左右。因此本文算法运算量小，速度快，大大满足了系统 $2 \mathrm { s }$ 的时间需求。

# 4结论

望远镜自动调焦的核心目标为提高星像能量集中度，本文提出的快速清晰度评价算法与其目标直接相关。研究过程中，通过对地基广角相机阵系统图像特点的研究，细化了过程中算法和参数，使计算量大大降低。最终结果运算快速、准确，计算焦点位置与系统实际焦点位置一致。调焦曲线单峰、尖锐，满足地基广角相机阵系统自动调焦的需求，可为其他望远镜自动观测系统提供参考。

# 参考文献：

[1] Wei J,Cordier B，Antier S,et al. The deep and transient universe in the SVOM Era：new challenges and opportunities-scientific prospects of the SVOM misson [C]// Proceedings of the Workshop held from 11th to 15th April 2016 at Les Houches School of Physics.2016.   
[2] 马冬，吴潮，田海俊，等.大视场光学瞬变源认证系统的设计与实现［J］．天文研究与技 术，2016，13(2)：190-198. Ma Dong，Wu Chao，Tian Haijun，et al. The design and implementation of a wide-field optical transient identification system [J].Astronomical Research & Technology，2016，13（2）：190- 198.   
[3] 曾德贤，胡炳梁，宋海军.空间碎片天基光学探测系统离焦问题分析［J]．光子学报， 2016，45(1): 147-151. Zeng Dexian，Hu Bingliang，Song Haijun.Analysis of defocus in space based optical debris detection ［J].Acta Photonica Sinica，2016，45(1）：147-151.   
[4] Weber B L，Brady S.Fast auto-focus method and software for CCD-based telescopes [C]// Minor Planet Amateur/Professional Workshop.2001:1O4-113.   
[5] 黄垒，辛立平，韩旭辉，等．广角天文望远镜的自动调焦［J]．光学精密工程，2015，23 (1):174-183. Huang Lei，Xin Liping，Han Xuhui，et al. Auto-focusing of wide-angle astronomical telescope [J].Optics and Precision Engineering，2015，23(1）：174-183.   
[6] Tang Pengyi,Liu Jiajing， Zhang Guangyu， et al. Automatic focusing system of BSST in Antarctic [C]//Proceedings of SPIE.2015：16-21.   
[7] 李彬，赵海斌.近地天体望远镜的PSF分布研究［J].天文学报，2012，53(3)：240-248. Li Bin，Zhao Haibin.Distribution of PSF of near earth object survey telescope ［J].Acta Astronomica Sinica，2012，53(3）:240-248.   
[8] Valdes F. PSFMEASURE/STARFOCUS:new IRAF PSF measuring tasks [C]// Astronomical Data Analysis Software and Systems III：A.S.P. Conference.1994:280-283.   
[9] Hong Hanyu，Li Liangcheng，Zhang Tianxu,et al. Universal deblurrng method for real images using transition region [J]. Optical Engineering，2012，51(4）：7006-7016.   
[10] Mahajan V N. Optical imaging and aberrations: part I. ray geometrical optics [M]. Washington: SPIE Press，1998.   
[11] Valdes F. PSFMEASURE/STARFOCUS:PSF measuring algorithms [C]// Astronomical Data Analysis Software and Systems III:A.S.P. Conference.1994:284-287.   
[12] Bertin E，Arnouts S. SExtractor: Software for source extraction [J]. Astronomy & Astrophysics Supplement，1996，117(2）:393-404.   
[13] 杨光普，邬文强.CCD恒星光度测量方法研究进展［J].天文学进展，2012，30(4)：467- 486. Yang Guangpu，Wu Wentao.Progress in the stellar CCD photometric methods [J]. Progress in Astronomy，2012，30(4) :467-486.

# Fast Image Definition Evaluation Based on Energy Concentration for Auto-Focusing on Wide-Angle Telescope

Yuan Jiahui $^ { 1 , 2 }$ ， Cai Hongbo $^ 2$ ，Wei Jianyan1 (1.Key Laboratory of Space Astronomy and Technology，National Astronomical Observatories, Chinese Academy of Sciences，Beijing 1Ooo12,China,Email：chb@bao.ac.cn; 2.University of Chinese Academy of Sciences，Beijing 1OoO49，China)

Abstract:Ground Wide Angle Cameras（GWAC） consists of 36 wide-angle telescopes to observe optical transients.It has super-large field of view，short cadence exposures and real-time data processing.Autofocusing is crucial to the system for realizing automatic observation and increasing scientific output.Enhancing the star's energy concentration is the main purpose of auto-focusing.The current evaluation methods such as $5 0 \%$ energy's radius and the full width of half maximum of point spread function take too much amount of calculation.Based on the rule that the central part of stars change sharply during focusing while the entire range of stars stay roughly the same，this paper presents a fast image definition evaluation method that calculates theratio between the flux within acertain central part of the star to its total flux,and studies on the choice of the two radiuses for aperture photometry.This paper also simplifies the photometry method，and selects he relative parameters such as background，star selection standard and star amount.A fast and accurate algorithm is archived for GWAC real-time auto-focusing system.The computation time is O.1s per frame，which meets the requirement of GWAC auto-focusing system.

Key Words:Image definition evaluation；Wide-angle telescope；Auto-focusing；Energy concentration