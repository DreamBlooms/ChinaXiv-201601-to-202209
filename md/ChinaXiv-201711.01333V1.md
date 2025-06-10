# 一米新真空太阳望远镜多波段光谱仪杂散光及空间PSF的测量

韩笑1,²，徐稚¹，李正刚¹，金振宇¹，王 瑞1,2（1.中国科学院云南天文台，云南 昆明650011；2.中国科学院大学，北京 100049)

摘要：杂散光由于光学表面散射和地球大气散射引起，降低了光谱图像的空间分辨率。光学系统都存在杂散光，要获得高分辨的光谱图像需要对杂散光进行抑制。多波段光谱仪的杂散光分为两类：(1)光谱桶内由于光机结构引起的杂射光；(2)混在成像光路中并参与色散的杂散光。第1种杂散光可直接测量，约占光谱能量的 $3 \%$ 左右。第2种杂散光由于受多种因素影响，所以很难精确测量。从日食光谱测量中测得在观测目标周围对目标产生的杂散光的下限约为 $10 \%$ ，并对空间方向的点扩散函数进行测量，为光谱的高分辨重建提供参考。

关键词： $\mathrm { ~ 1 ~ m ~ }$ 太阳望远镜；多波段光谱仪；杂散光；点扩散函数中图分类号：TH744.1 文献标识码：A 文章编号：1672-7673(2017)01-0052-08

抚仙湖 $1 \mathrm { m }$ 新真空太阳望远镜(New Vacuum Solar Telescope，NVST)是国内口径最大的地基真空太阳望远镜，主要用于太阳光球和色球的高分辨率成像观测和太阳光谱观测[1。杂散光对成像观测和光谱观测的影响是一个需要解决的难题，光谱观测中，杂散光的能量占光谱强度的很大一部分，对数据分析结果产生严重影响。观测目标的亮度越小，杂散光对其影响越大，例如黑子观测、日面边缘观测和较深谱线的观测[2]。

地基望远镜杂散光的来源有以下几种：（1)由地球大气中灰尘和粒子的散射引起的杂散光；（2)由于大气折射率的快速变化产生的在总量上不断变化的杂散光；（3)仪器散射产生的杂散光[3]。杂散光从表现形式上可以分为两类：（1)经过光栅参与色散的杂散光，称之为色散杂散光；（2）由光谱桶内光、机表面散射产生的杂散光，称之为仪器杂散光。杂散光的影响通常被量化成扩散函数，大规模和小规模的杂散光可以用解析函数的不同形式表达，例如高斯函数或洛伦兹函数或它们的组合[4]。点扩散函数(Point Spread Function，PSF)可以准确地描述点源在经过光学系统后产生空间上形状的变化，可以用点扩散函数描述仪器轮廓对光谱图像产生的影响。日面边缘外强度的径向变化和遮挡部分视场时遮挡处强度的径向变化可用来测量空间方向上的点扩散函数。

本文根据杂散光的理论推导把多波段光谱仪的杂散光从形式上分为仪器杂散光和色散杂散光，对两部分杂散光分别进行测量。阐述了空间方向上的点扩散函数与杂散光之间的关系，并由日食光谱测量了空间方向上的点扩散函数。

# 1杂散光问题的理论描述

太阳光经过地球大气、望远镜系统最终到达探测器。太阳光的真实强度 $I _ { \mathrm { t u r e } }$ 由于仪器轮廓的作用，最终获得的观测强度 $I _ { \mathrm { o b s } }$ 与 $I _ { \mathrm { t u r e } }$ 关系为

$$
I _ { \mathrm { o b s } } ( t ) = P S F ( t ) \bigotimes I _ { \mathrm { t u r e } } ( t ) ,
$$

其中， $I _ { \mathrm { t u r e } }$ 表示光谱能量的真实强度； $I _ { \mathrm { o b s } }$ 表示 $I _ { \mathrm { t u r e } }$ 经过点扩散函数作用得到的观测强度。当只考虑非时变性的点扩散函数时，对(1)式做傅里叶变换：

$$
\widetilde { I } _ { \mathrm { o b s } } = \widetilde { I } _ { \mathrm { t u r e } } \cdot \widetilde { K } \ ,
$$

其中，\~代表傅里叶变换； $K$ 表示点扩散函数的卷积核，根据(2)式可以得出真实光谱能量为

$$
\widetilde { I } _ { \mathrm { t u r e } } = \widetilde { K } ^ { - 1 } \cdot \widetilde { I } _ { \mathrm { o b s } } \ .
$$

$1 \mathrm { m }$ 太阳望远镜多波段光谱仪简图如图 $1 ^ { [ 5 - 6 ] }$ ，为了便于测量，把CCD 靶面中心的光谱强度写成下式[7].

$$
I _ { \mathrm { o b s } } ( \lambda , \ x , \ \gamma ) = I _ { \mathrm { t u r e } } ( \lambda , \ x , \ \gamma ) \ + \alpha _ { 1 } I _ { \mathrm { g l o b a l } } ( \lambda ) \ + \alpha _ { 2 } I _ { \mathrm { l o c a l } } ( \lambda ) \ + c o n s t . ,
$$

其中

$$
c o n s t . = d c + p a r a s i t i c l i g h t = d c + \alpha _ { 3 } \langle I _ { l o c a l } \rangle ,
$$

![](images/fa6167297639d1cd5ba01db9c186aa6ad9b78befc87adea9a646a4af00b500ec.jpg)  
图1 $\mathrm { ~ 1 ~ m ~ }$ 太阳望远镜多波段光谱仪简图Fig.1Schematic diagram of the multi-band spectrometer

$I _ { \mathrm { t u r e } } ( \lambda , x , y )$ 表示在太阳上空间位置为 $( x , y )$ 的点产生的光谱强度，对应狭缝位置在太阳图像上 $x$ 位置的CCD 靶面像素的第 $y$ 行； $I _ { \mathrm { g l o b a l } } ( \lambda )$ 表示 $\boldsymbol { F } _ { 1 }$ 焦点之前的平均光谱强度，因为在观测过程中，整个日面都会对 $I _ { \mathrm { g l o b a l } }$ 产生散射，从而影响其强度，这一项包含的杂散光相当于整个日面对 $I _ { \mathrm { g l o b a l } }$ 的贡献[8],所以假设 $I _ { \mathrm { g l o b a l } }$ 包含的杂散光与观测目标的位置 $( x , y )$ 没有关系，在望远镜视场内都是一致的； $\alpha _ { 1 }$ 表示 $I _ { \mathrm { { g l o b a l } } }$ 中杂散光所占的比例； $I _ { \mathrm { l o c a l } }$ 表示 $\boldsymbol { F } _ { 1 }$ 焦点后的平均光谱强度，此部分的光谱强度来源于 $\boldsymbol { F } _ { 1 }$ 焦点处由孔径光阑限制的视场，而不是来源于全日面。杂散光在 $I _ { \mathrm { { l o c a l } } } ( \lambda )$ 中由两部分组成：一部分由视场内的光谱强度受观测目标周围太阳光的散射光经过 $\boldsymbol { F } _ { 1 }$ 焦点前的光学元件后产生，另一部分由仪器的点扩散函数造成[7]：

$$
\alpha _ { 2 } I _ { \mathrm { l o c a l } } ( \lambda ) = \alpha _ { 4 } \frac { \displaystyle \int _ { \sigma } I ( \lambda ) \mathrm { d } \sigma } { \displaystyle \int _ { \sigma } \mathrm { d } \sigma } + \langle P S F _ { \mathrm { i n s t r } } ( \Delta x , \ \Delta y ) \ \times I ( \lambda , \ \Delta x , \ \Delta y ) \ \rangle _ { _ { ( \Delta x , \ \Delta y ) } } ,
$$

其中， $\sigma$ 表示 $\boldsymbol { F } _ { 1 }$ 焦点处孔径光阑的面积； $( \Delta x , \Delta y )$ 表示视场内一点 $( x , y )$ 到视场内任意一点的距离;$P S F _ { \mathrm { i n s t r } }$ 表示 $\boldsymbol { F } _ { 1 }$ 焦点后的空间点扩散函数。在 $F _ { _ 2 }$ 焦点处视场约为 $3 ^ { \prime }$ ，空间点扩散函数对视场内一点$( x , y )$ 的贡献来自于 $( \Delta x , \Delta y )$ 小于 $0 . 8 2 ^ { \prime \prime }$ 的范围（见3.1节）。在太阳宁静区，由于没有特殊结构，较大视场和较小视场产生的图像轮廓几乎相同，所以假设(6)式右侧两项可以使用相同的比例项 $\alpha _ { 2 }$ 。$I _ { \mathrm { g l o b a l } }$ 和 $I _ { \mathrm { l o c a l } }$ 因为混在入射光路中，所以都会经过光栅。跟波长没有关系的杂散光来自于光谱桶内部,$d c$ 表示 CCD 的暗电流， $\alpha _ { 3 } \langle I _ { \mathrm { l o c a l } } \rangle$ 表示在光谱桶内仪器散射产生的杂散光，此部分杂散光不经过光栅直接到达CCD，并且与进入光谱桶内部的光量有关。（4)式可以很好地解决系统杂散光问题，由于杂散光对 $I _ { \mathrm { l o c a l } }$ 的贡献非常大，全视场时产生的平均图像轮廓与全日面时的平均图像轮廓相似，所以没有必要从观测光谱中定义 $I _ { \mathrm { g l o b a l } }$ ，用 $I _ { \mathrm { l o c a l } }$ 替代 $I _ { \mathrm { g l o b a l } }$ ，所以(4)式简化为[7]：

$$
I _ { \mathrm { o b s } } ( \lambda , \ x , \ y ) = I _ { \mathrm { t u r e } } ( \lambda , \ x , \ y ) + \alpha I _ { \mathrm { l o c a l } } ( \lambda ) + \beta \langle I _ { \mathrm { l o c a l } } \rangle \ .
$$

从而把光谱仪的杂散光分为两部分：（1）由于大气散射而混在成像光路中参与色散的杂散光，称之

为色散杂散光；(2)偏离主光路的光由谱桶内光机结构的散射而产生的杂散光，称之为仪器杂散光。(7)式右侧第2项表示色散杂散光，第3项表示仪器杂散光。 $\alpha$ 和 $\beta$ 参数的测量将在下一节介绍。

# 2杂散光的测量

目前 $1 \mathrm { m }$ 太阳望远镜多波段光谱仪工作在3个波段，分别为FeI波段、 $\mathbf { H } \alpha$ 波段、CaI波段。在进行杂散光测量之前，先用傅里叶变换光谱仪（Fourier Transform Spectrograph，FTS）标准谱与观测 $\mathrm { H } \alpha$ 谱线进行对比[9]，结果如图2。

在谱线对齐后，将谱线对应的傅里叶变换光谱仪标准谱与一个高斯轮廓进行卷积，当傅里叶变换光谱仪标准谱与一个半宽为 $0 . 0 0 6 5 \mathrm { n m }$ 的高斯轮廓卷积后，与观测谱线的轮廓很好地吻合。从图2中可以看出，在对标准谱进行卷积后，太阳平均谱线轮廓依然比卷积后的标准谱线浅，这部分差异就是由杂散光造成的。

![](images/8db4595edd64f6455c424c30287d6acecca4b7e4de4be3baed278ba0233671a4.jpg)  
图2 Hα 通道的观测光谱(红色)与卷积后的FTS标准谱(绿色)的对照  
Fig.2Comparison between the observed profile of the Hα channel（red line）and the convolved FTS standard profile（green line)

# 2.1仪器杂散光的测量

在进行FeI观测时，用边缘较锐的金属挡片遮挡一部分狭缝后进行观测（如图1)，减去暗场后得到图3(a)的光谱图像， $5 3 2 . 4 \ \mathrm { n m }$ 吸收线附近连续谱空间方向上的光强分布如图3(b)。从图3(b)可以看出，在减掉暗场后，阴影区域仍然有剩余强度存在，剩余强度由仪器杂散光引起。

![](images/dfcbd99a01694729d22994802cdf5086f79038f58729979db7bb7fc80cf3a90a.jpg)  
图3FeI通道的观测光谱 Fig.3Observed spectra of FeI channel

仪器杂散光由光谱桶内光、机结构对光的散射引起，此部分杂散光与进入光谱桶内的光量有关，进入光谱桶内的光量越大，仪器杂散光越多。由于谱线线心的剩余能量较小，即使这部分杂散光不大，也会对光谱观测造成影响。把仪器杂散光分为两类进行研究：（1)由于光谱桶的漏光在光谱桶内散射产生的杂散光，称之为漏光杂散光；（2）由于偏离主光路的光线在光谱桶内的散射形成的杂散光，称之为散射杂散光。

漏光杂散光的测量方法为：用不同的方法测量两组暗场，第1组为遮挡CCD镜头测量暗场，第2组为完全遮挡 $F _ { _ 2 }$ 焦点(狭缝)进行测量[10]。第1组暗场是CCD自身的暗电流，第2组既包括CCD 自身暗电流 $I _ { \mathrm { d c } }$ ，又包括漏光杂散光 $I _ { \mathrm { l e a k e d } }$ 。

$$
I _ { f _ { 2 } } = I _ { \mathrm { l e a k e d } } + I _ { \mathrm { d c } } .
$$

由(8)式可知， $I _ { \mathrm { l e a k e d } }$ 的强度等于遮挡 $F _ { _ 2 }$ 焦点时暗场的平均强度 $I _ { f _ { 2 } }$ 减去遮挡CCD镜头时暗场的平均强度 $I _ { d c }$ 。求得3个通道由漏光产生的杂散光约为 $0 . 3 \% \sim 0 . 5 \%$ 。

如果直接到达CCD的成像光线被遮挡，那么CCD上剩余的能量就是光谱桶内自由散射光的能量，这就是测量仪器杂散光的原理。如图4，在$\mathrm { H } \alpha$ 通道成像镜到CCD成像的光路中加挡板进行遮挡，遮挡的位置靠近成像镜，移动挡板位置，如果刚好在CCD上看不见谱线，说明CCD上的剩余强度是由自由散射光引起的[7]。

由于各个通道成像镜的入射光线和出射光线距离很近，在成像镜附近遮挡的同时也会遮挡到入射光线，所以对此方法做了改进：假设仪器杂散光是以一定的角度入射CCD，在CCD前加黑色遮光筒，对于入射角度大的仪器杂散光可以直

![](images/a18756924585cf71c957c2cb302be2b602a7e4326472bd3f25cf32301b8abea1.jpg)  
图4实验原理图  
Fig.4Schematic diagram of the experimental setups

接阻挡，人射角度较小的仪器杂散光由于在遮光桶内的散射和吸收，能量衰减。用正常观测下的平均光谱强度 $I _ { \mathrm { o b s 1 } }$ 减掉加遮光筒后观测的平均光谱强度 $I _ { \mathrm { o b s } 2 }$ ，图像上剩余的强度即为仪器杂散光的强度 $I _ { \beta }$ ：

$$
I _ { \beta } = I _ { \mathrm { { o b s l } } } - I _ { \mathrm { { o b s 2 } } } .
$$

求得在FeI通道 $\beta = 3 . 5 \%$ ， $\mathrm { H } \alpha$ 通道 $\beta = 0 . 5 \%$ ，Ca $\mathbb { I }$ 通道 $\beta = 8 . 8 \%$ 。

本节测量的各部分杂散光总结见表1。可以看出在Ca $\mathbb { I }$ 通道的仪器杂散光量级远高出正常的杂散光量级。

# 表1各部分杂散光的测量

Table1 Measurement results of stray-light   

<html><body><table><tr><td>测量方法</td><td>波段/nm</td><td>百分比/%（(sryliht/bs）</td></tr><tr><td>与 FTS 谱对比</td><td>656. 3</td><td>1</td></tr><tr><td>漏光产生的杂散光</td><td>532.4/656.3/854. 2</td><td>0.4~0.6</td></tr><tr><td>仪器杂散光</td><td>532.4/656.3/ 854. 2</td><td>3.5/0.5/8.8</td></tr><tr><td>遮挡F2焦点</td><td>532.4/656.3/ 854. 2</td><td>2.5/0.5/8.8(尾部)</td></tr><tr><td>日面边缘</td><td>532.4/656.3/854.2</td><td>3.5/2/8.8(尾部)</td></tr></table></body></html>

# 2.2色散杂散光的测量

色散杂散光来源于地球大气对太阳光的散射，由观测目标附近的太阳表面光经由大气散射后对观测目标产生的杂散光。

太阳光由大气散射造成的杂散光量级是从黑子本影中测量得到的，通过对比固有能量很小的黑子本影的平均轮廓与太阳宁静区光谱图像的平均轮廓获得。通过黑子本影轮廓与太阳光谱轮廓的比较可以获得太阳光散射对杂散光贡献的最大比重[0]。

由于黑子能量不为0，为此在2016年3月9日进行了日食光谱观测，由于月球本身不发光，表面的能量为0，所以用日食光谱获得的 $\alpha$ 参数更为准确。把狭缝调整到横跨在日食造成阴影的边缘，用曝光时间为 $7 0 \mathrm { m s }$ ，在日食食甚时采集数据。图像去除暗场后 $\mathrm { H } \alpha$ 通道日食光谱如图5。与黑子本影不同，由于在黑子本影光谱图像中，黑子本影轮廓在光谱图像的中间位置，黑子两侧的太阳光会对其进行散射，而太阳光对日食阴影部分的散射随着阴影部分面积的增加而减少。所以取在明暗交界处附近的日食光谱轮廓（约 $2 5 ^ { \prime \prime }$ 处)与对应的正常拍摄的太阳光谱图像上 $2 5 ^ { \prime \prime }$ 处的光谱图像轮廓的对比测量 $\alpha$ 。

![](images/857bc442245d15cac5b29753cd0aaa68a4d77c97972549cbb898b4022d128ce1.jpg)  
图5日食光谱  
Fig.5Solar eclipse spectrum

根据上述方法，从日食光谱中得到的 $\alpha$ 值为 $1 1 \%$ 。用金属挡片遮挡在狭缝 $2 5 ^ { \prime \prime }$ 处，得到的图像减去暗场，阴影区域剩余的能量约为日面上光谱强度的 $1 \%$ 左右，所以 $\alpha$ 的值约为 $10 \%$ 左右。

# 3空间点扩散函数的测量

# 3.1点扩散函数与杂散光的关系

在光谱观测中，点扩散函数表示仪器轮廓对光谱图像的影响，光信号经过光学系统后，由于点扩散函数的影响会产生变化，杂散光的存在影响点扩散函数轮廓曲线，所以实际测得点扩散函数轮廓曲线受到杂散光的影响。因此测得点扩散函数后，利用反卷积的办法还原光谱图像的真实轮廓，不仅可以提高光谱图像的空间分辨率，还可以消除杂散光对光谱信号的影响。

# 3.2点扩散函数的测量

对点扩散函数有贡献的3方面，由于自适应光学（AdaptiveOptics，AO)系统的实时修正，由大气折射率变化引起的杂散光被基本修正，剩下由于地球大气散射和仪器散射引起的杂散光。点扩散函数从视场内一点向其余点散射光，视场内的每个点相互影响，这样就形成了杂散光[7]。根据(3)式，在求得点扩散函数后可利用反卷积的方法提高空间分辨率，但这种方法带来放大的噪声。

用金属板遮挡部分视场的方法获得多波段光谱仪空间方向上的点扩散函数，由于 $1 \mathrm { m }$ 太阳望远镜是真空望远镜， $\boldsymbol { F } _ { 1 }$ 焦点位于真空桶内，没有办法遮挡，所以只遮挡 $F _ { 2 }$ 焦点。遮挡 $F _ { 2 }$ 焦点时的光谱图像如图6。

![](images/ae1bb4aa260de4f831d3eeb805743da89e9603ffbb33539c2aa3c3b1ab83aa25.jpg)  
图6金属挡片遮挡狭缝时的谱图像  
Fig.6The spectral image with the slit blocked by the metal plane

在去除仪器杂散光和暗场后，取图5中红线所示的约 $4 ^ { \prime \prime }$ 的区域，分析径向强度的变化，得到图7。构建一个高斯函数和洛伦兹函数组合模拟点扩散函数，用阶梯函数（图7中蓝线)模拟理想情况下的径向强度变化。随后用试错法改动这两个函数的参数和组合比例，直到阶梯函数与点扩散函数卷积后的曲线与遮挡 $F _ { 2 }$ 焦点时观察强度变化曲线吻合。最后使用的卷积核如图7(b)中黑线，可以看出卷积核的中心在25像素，在20像素左右它的值为0，变化较大的区间在20像素到30像素之间， $1 \mathrm { ~ m ~ }$ 太阳望远镜多波段光谱仪的空间分辨率为 $0 . 0 8 2 ^ { \prime \prime } / \mathrm { p i x e l }$ ，说明由点扩散函数对视场内一点 $( x , y )$ 杂散光的贡献来源于 $( x , y )$ 周围的 $0 . 8 2 ^ { \prime \prime }$ 范围内。为了检验所得卷积核是否正确，从二维轴对称的卷积核$K ( x , y )$ 中可以得出一维卷积核[7(10式)，如图7(b)红线。

$$
K ( x ) = { \frac { \mathrm { d } I _ { \mathrm { { o b s } } } } { \mathrm { d } x } } ( x ) \ .
$$

$K ( x )$ 表示观测强度分布相对于阶梯函数的变化。从图7(b)可以看出，用试错法得到的卷积核(黑线)与理论预期(红线)符合得很好。从图7(a)可以看出，在强度变化曲线的尾部，即离遮挡处5 像素之后，剩余能量不足 $1 \%$ ，说明当视场只有一部分被照亮时，点扩散函数是杂散光的主要来源，日面边缘的光谱观测与其相同。

![](images/0f801dfcbe5d6a783016255f0d66166270547ff5dad9715535e871af2d67aa35.jpg)  
图7光谱图像强度的径向变化与卷积核  
Fig.7Brightness distribution in the spatial direction and the kernel of PSF

# 4总结

根据杂散光的理论公式把杂散光分为仪器杂散光和色散杂散光。对于仪器杂散光而言，由于各个通道探测器所处的位置不同，每个波段的杂散光占光谱图像能量的比重也不同，分别为FeⅠ通道$3 . 5 \%$ 、 $\mathrm { H } \alpha$ 通道 $0 . 5 \%$ 、CaI通道 $8 . 8 \%$ 。在CaⅡ的仪器杂散光远高出正常杂散光水平。随后利用日食光谱测量了由地球大气散射引起的色散杂散光，约为光谱能量的 $10 \%$ ，为以后去除此部分杂散光的算法做了铺垫，最后测量了 $1 \mathrm { m }$ 太阳望远镜多波段光谱仪空间方向上的点扩散函数。

# 参考文献：

[1] Liu Z，Xu J.1-meter near-infrared solar telescope [C]// First Asia-Pacific Solar Physics Meeting ASI Conference Series. 2011:9-17.   
[2] Koppen J. Sunspot and stray light observations during the 1971,February 25 partial solar eclipse [J].Solar Physics，1975，42(2):325-332.   
[3] Sanchez Almeida J，Martinez Pillet V.Instrumental polarization in the focal plane of telescopes [J].Astronomy & Astrophysics，1992，260(1-2）: 543-555.   
[4] Benton JA，Deforest C A，Vivekanandan V，et al.Photocrosslinking of gelatin macromers to synthesize porous hydrogels that promote valvular interstitial cell function ［J].Tissue Engineering Part A，2009，15（11）:3221-3231.   
[5] 王瑞，徐稚，刘忠.一米新真空红外太阳望远镜多波段光谱仪光谱弯曲分析［J].天文研究 与技术——国家天文台台刊，2014，11(2)：165-167. Wang Rui，Xu Zhi，Liu Zhong. An analysis of spectrum curvatures for the multi-wavelength spectrometer of the new vaccum solar telescope of the Yunnan Observatories [J].Astronomical Research & Technology———Publications of National Astronomical Observatories of China，2014, 11(2) : 165-167.   
[6] 许方宇，徐稚，徐世春，等.抚仙湖一米新真空太阳望远镜6米近红外光谱仪装调及太阳 1.56 微米光谱的初步观测结果［J].天文研究与技术—国家天文台台刊，2014，11（2)： 168-175. Xu Fangyu，Xu Zhi，Xu Shichun，et al. Installation/Adjustment of a 6m near-infrared spectrograph for the 1m new vacuum solar telescope in the Fuxian-Lake Solar-Observation Station and preliminary observation results of solar spectra around $1 . 5 6 \mu \mathrm { m }$ using the spectrograph[J]. Astronomical Research & Technology———Publications of National Astronomical Observatories of China，2014，11(2):168-175.   
[7] Beck C,Rezaei R,Fabbian D. Stray-light contamination and spatial deconvolution of slit-spectrograph observations [J].Astronomy & Astrophysics，2011，535(11）：1038-1050.   
[8] Mattig W. Observations of stray-light and sunspot intensities during the Mercury transit of 1970 May 9［J].Solar Physics，1971，18(3):434-442.   
[9] Wang Rui，Xu Zhi，Jin Zhenyu，et al.The first observation and data reduction of the Multiwavelength Spectrometer on the New Vacuum Solar Telescope ［J].Research in Astronomy & Astrophysics，2013，13(10) :1240-1254.   
[10] Rezaei R,Schlichenmaier R，Beck C A R,et al. Relation between photospheric magnetic field and chromospheric emission ［J].Astronomy & Astrophysics，2007，466：1131-1144.

# Stray-Light and Space PSF Measuring of the Multi-Band Spectrometer of the 1m New Vacuum Solar Telescope

Han Xiao1,²，Xu Zhi’，Li Zhenggang¹，Jin Zhenyu1，Wang Rui1,2 (1.Yunnan Observatories，Chinese Academic of Sciences，Kunming 65oo11, China，Email:fyul@ ynao.ac.cn; 2.University of Chinese Academy of Sciences，Beijing 10o049,China)

Abstract: Stray-light is caused by the scatering of optical surfaces and the Earth's atmosphere；which degrades the spatial resolution of spectral images.Almost every optical system is affected by stray-light.To obtain high-resolution spectral images，we need to eliminate the effct caused by stray-light as much as possible.The stray-light of multi-waveband spectrometer can be divided into two categories:（1）stray-light caused by the scatering of the optical and mechanical structures in the spectral barrel and（2） stray-light mixed inthe imaging optical path and participating in dispersion.The firstcategory can be measured directly, and it accounts for $3 \%$ of spectral energy. It is difficult to measure the second category precisely because it could be affected by many factors.We measured the stray-light around the target from the eclipse spectral observation，and found that the lower limit of the stray-light was about $10 \%$ .In addition，we measured the point spread function（PSF）of the multi-band spectrometer in the space direction.This work would provide reference for future high-resolution spectrum reconstruction.

Key words: 1m New Vacuum Solar Telescope；Multi-band Spectrometer; Stray-light； PSF