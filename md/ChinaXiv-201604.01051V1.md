GAOGuangda,HUXiaoyan,ZHONGJia,ZOUZiming.Seedpointselectionthroughqualineintegralofmagneticfeldntesity algorithmfrisualatiofgeomagneticfeld(inCinse).Chin.J.SpaceSci166(2):47-52.DO10728/j.. 147

# 地磁场磁力线可视化种子点选取的\*磁场强度线积分等分算法

高广大1.2 胡晓彦1 钟佳¹邹自明1

1(中国科学院国家空间科学中心 北京 100190)2(中国科学院大学北京 100049)

摘要将磁力线按流线进行绘制是地磁场可视化的通用方法．磁力线种子点的选取决定了绘制磁力线的疏密，其疏密程度能否真实反映地磁场强度分布是评价地磁场可视化效果的关键．基于磁经圈均匀角度种子点选取算法绘制的磁力线通常不能客观反映地磁场强度的空间分布，针对这一不足，提出一种等分磁场强度线积分的磁力线种子点选取算法．利用该算法对地磁场IGRF 模型和 T96 模型描述的地磁内外源场进行可视化绘制，对磁力线追踪结果中出现的冗余磁力线进行过滤，统计分析了绘制磁力线的空间分布与地磁场强度空间分布的相关性，结果表明该算法能够较好地实现对地磁场的可视化

关键词地磁场可视化，种子点选取，冗余磁力线过滤，线积分等分算法中图分类号P352

# Seed Point Selection through Equal Line Integral of Magnetic Field Intensity Algorithm for Visualization of Geomagnetic Field

GAO Guangda $^ { 1 , 2 }$ （20 HU Xiaoyan1 ZHONG Jia1 ZOU Ziming $^ { 1 }$

1(National Space Science Center,Chinese Academy of Sciences,Beijing 100190)

2(University of Chinese Academy of Sciences,Beijing 100049)

AbstractDrawing the magnetic lines as streamlines is a general method of visualizing geomagnetic field.A key factor to evaluate the efect of the geomagnetic field visualization is whether the space distribution of geomagnetic field lines is consistent with that of magnetic field intensity,while the distribution of geomagnetic field lines is determined by seed point selection. The traditional algorithms that select seed points with uniform angles on magnetic meridian circles cannot objectively reflect the space distributions of magnetic field intensity. This paper proposes an algorithm of selecting seed points with equal line integral of magnetic feld intensity. The algorithm is applied to draw the geomagnetic field lines with the data from T96 model and IGRF model. The redundant magnetic field lines existing in the result are removed.Statistical analysis and comparison between the space distribution of magnetic feld lines and the geomagnetic feld intensity reveals that this algorithm can effectively visualize the geomagnetic field.

Key wordsGeomagnetic field visualization, Seed point selection,Redundant magnetic line removing,Equal line integral algorithm

# 0 引言

地磁场可视化可以直观展现地磁场的形态结构与强度分布等物理特征,通常认为地磁场是一种典型的矢量场，将地磁场磁力线按流线进行绘制，可以形象描绘磁场结构，其是一种对地磁场进行可视化的通用方法.

有效的地磁场可视化算法应能够表现出地磁场的物理特征.在磁场强度越大的区域，单位面积内的磁通量越大，表现在视觉效果上的磁力线分布应该越密；反之，在磁场强度越小的区域，则磁力线应该越疏．因此，评价地磁场磁力线可视化效果的关键因素是绘制磁力线的疏密与磁场强度空间分布之间的相关性.利用磁力线对地磁场进行可视化时，对选取的每个磁力线种子点进行追踪都将生成一条磁力线，所以种子点的空间分布直接决定了磁力线的空间分布选取出能够真实反映地磁场强度空间分布的种子点，将提高地磁场磁力线可视化的有效性，

目前对地磁场磁力线可视化的工作一般是在地球磁经圈、磁纬圈、磁赤道面或某个经纬网格区域内选取种子点.但通常的做法是选取空间均匀分布(例如均匀角度)的种子点，缺乏对种子点空间分布的物理约束.例如,Tsyganenkol1在与太阳风方向平行的磁经圈上以均匀角度的方式选取种子点，对高纬度区域地磁场进行了磁力线可视化，并比较了不同物理参数对地磁场形状的影响．根据真实地磁场的物理特征，在该磁经圈上选取种子点能使得磁力线大致分布在一个平面内，有效消除磁力线在视觉投影面的交叉重叠现象.但由于是均匀角度方式选取种子点，绘制磁力线的疏密不能客观反映地磁场强度的空间分布，

$\mathrm { H e ^ { [ 2 ] } }$ 在磁赤道面上距地心距离为 $L$ 个地球半径的磁纬圈上以均匀角度的方式选取种子点进行磁力线绘制，反映出了磁壳的基本轮廓特征，但由于磁壳参数 $L$ 选取的任意性，磁力线之间没有约束关系，同样不能从磁力线疏密程度客观反映磁场强度的空间分布，并且视觉空间中的交叉重叠现象也比较严重2014年Zhong[3]考虑磁力线疏密与磁场强度空间分布的关系，提出了等磁通量法和等磁通密度衰减法，利用磁赤道面上磁力线疏密的约束规则反推球面上磁力线种子点的选取规则，对地磁偶极子场进行可视化．该方法能够通过磁力线疏密客观反映地磁场强度的空间分布，但文献[3只基于偶极子场模型进行了验证，并没有在更真实或更复杂的地磁场模型下进行应用，其适用性有待进一步讨论，

针对在磁经圈上以均匀角度方式选取种子点方法的不足，本文设计了磁场强度线积分等分算法，利用磁经圈上磁场强度分布对种子点分布进行约束将该算法应用于对IGRF模型和T96模型地磁内外源场的可视化绘制，并对磁力线追踪结果中出现的冗余磁力线进行过滤，实现了对该算法的有效性验证

# 1磁场强度线积分等分算法

磁场强度线积分等分算法的中心思想是将特定路径(如磁经圈、磁纬圈）上磁场强度的线积分进行等分.在磁场强度较大区域，相邻两个等分点之间的距离较短，反之则较长，因此利用磁场强度线积分等分点作为种子点能够有效反映地磁场强度分布，

为了避免视觉上的交叉重叠现象，参照文献[1],在与太阳风方向平行的磁经圈上选取种子点．首先求出磁经圈上磁场强度的线积分总量，即

$$
\quad { \boldsymbol { \phi } } = \oint \left| { \boldsymbol { B } } \right| \cdot \mathrm { d } { \boldsymbol { l } } .
$$

其中， $B$ 为磁场强度

假设要在该磁经圈上选取 $N$ 个种子点，则需要求出该磁经圈上磁场强度线积分的 $N$ 等分点的位置.将每个种子点到地心的连线与地磁轴的夹角记为 $\theta$ (取值范围为0到 $2 \pi$ )，记第 $i$ 个种子点对应的夹角为 $\theta _ { i }$ $( i = 0 , 1 , 2 , \cdots , N - 1 )$ ．选取 $\theta _ { 0 } = 0$ 对应的点作为首个种子点，相邻两个种子点之间的磁场强度线积分均为 $\varPhi / N$ ，从 $\theta _ { 0 }$ 到 $\theta _ { i }$ 的磁场强度线积分

$$
\begin{array} { l } { \displaystyle \varPhi _ { i } = \int _ { \theta _ { 0 } } ^ { \theta _ { i } } \lvert B \rvert \mathrm { d } l ( \theta ) = } \\ { \displaystyle \int _ { \theta _ { 0 } } ^ { \theta _ { i } } \lvert B \rvert R \mathrm { d } \theta = i \frac \varPhi { N } , \quad i = 0 , 1 , 2 , \cdot \cdot , N - 1 . } \end{array}
$$

通常根据式(2）便可求出 $\theta _ { i }$ 的值．但在实际计算中，磁场强度数据不是连续的，需要将磁经圈按角度均匀方式离散化为 $M$ 个采样点，采样点到地心的连线与地磁轴的夹角

$$
\alpha _ { k } = k \frac { 2 \pi } { M } , \quad k = 0 , 1 , 2 , \cdot \cdot \cdot , M - 1 .
$$

第0个采样点沿磁经圈一周并回到第0个采样点对应的周角 $\alpha _ { M } = 2 \pi$ ，并记 $\alpha _ { k }$ 对应的采样点处磁场强度为 $\lvert B _ { k } \rvert$ ．简单起见，假设第 $k$ 和第 $k + 1$ 两个相邻采样点之间的磁场强度是均匀的，用 $\lvert B _ { k } \rvert$ 和 $| B _ { k + 1 } |$ 的平均值来表示．当 $k$ 不小于1时,第 $k { - } 1$ 和 $k$ 个采样点之间的磁场强度线积分可表达为

$$
\phi _ { k } ^ { \prime } = \frac { | { \cal B } _ { k } | + | { \cal B } _ { k - 1 } | } { 2 } \cdot \frac { 2 \pi R } { M } , \quad k = 1 , 2 , 3 , \cdots , M .
$$

当 $k = 0$ 时,记 $\varPhi _ { 0 } ^ { \prime } = 0$ .对于第 $i ( i = 0 , 1 , 2 , \cdots , N -$ 1）个种子点，寻找非负整数 $s$ ，使得 $\theta _ { i }$ 处于 $\alpha _ { s }$ 与 $\alpha _ { s + 1 }$ 之间,则 $s$ 应满足

$$
\sum _ { j = 0 } ^ { s } \phi _ { j } ^ { \prime } \leqslant \varPhi _ { i } < \sum _ { j = 0 } ^ { s + 1 } \phi _ { j } ^ { \prime } , \quad s = 0 , 1 , 2 , \cdots , M - 1 .
$$

式(5)中的 $\varPhi _ { i }$ 可以由式(2)得到.由于假设相邻采样点之间的磁场强度是均匀的，找到第 $i$ 个种子点对应的 $s$ 后可通过线性插值得到

$$
\theta _ { i } = \alpha _ { s } + \frac { \displaystyle \varPhi _ { i } - \sum _ { j = 0 } ^ { s } \varPhi _ { j } ^ { \prime } } { \displaystyle \varPhi _ { s + 1 } ^ { \prime } } ( \alpha _ { s + 1 } - \alpha _ { s } ) ,
$$

$$
s = 0 , 1 , 2 , \cdots , M - 1 .
$$

将式 $( 2 ) { \sim } ( 4 )$ 代入式(6)即可求出 $\theta _ { i }$ 的值,进而可求出种子点的空间位置，

对磁场强度线积分等分算法选取的种子点进行磁力线追踪，会产生两种磁力线，即封闭磁力线和开放磁力线．在封闭磁力线中可能会产生磁力线距离过近甚至重叠的现象，这意味着两条磁力线之间的区域磁场强度非常大，甚至趋于无穷，与物理事实不相符，产生磁力线冗余．而开放磁力线则不存在这类问题．这种现象是由封闭磁力线两次穿越选取种子点的磁经圈而引起的.根据磁力线上磁场方向的不同，可将封闭磁力线区域细分为磁力线发出区域和磁力线射入区域，磁力线沿磁场方向从磁力线发出区域出发，进入到磁力线射入区域.磁力线发出区域内由种子点确定的磁力线条数与该区域内磁场强度分布是相匹配的.但是，从磁力线射入区域的种子点追踪出来的磁力线会进入到磁力线发出区域，使得最终存在于磁力线发出区域的磁力线条数大于磁力线发出区域的种子点数.同理，磁力线射入区域也存在与磁力线发出区域类似的现象.

理论上讲，从磁力线发出区域发出的磁力线条数与进入磁力线射入区域的磁力线条数是相等的.对于这两组磁力线，只需要一组便能够反映整个封闭磁力线区域的磁场强度分布．磁场强度线积分等分算法会同时产生这两组磁力线，于是就产生了磁力线冗余现象，需要对冗余的磁力线进行过滤.

# 2 实验绘制

地磁场可以分为内源场和外源场，IGRF模型[4]和 T96 模型[5]是国际上广泛使用的内外源场模型.本文选用IGRF模型和T96作为地磁场数据源.以1997年1月1日 $1 8 { : } 0 5 \mathrm { L T }$ 的数据为例，输入参数为：太阳风质子密度 $N _ { \mathrm { p } } = 4 . 0 8 \mathrm { c m } ^ { - 3 }$ ；太阳风速度 $v _ { x \mathrm { G S E } } = - 4 1 4 . 5 \mathrm { k m } { \cdot } \mathrm { s } ^ { - 1 }$ ， $v _ { y \mathrm { G S E } } = - 3 4 . 5 \mathrm { k m } { \cdot } \mathrm { s } ^ { - 1 }$ $v _ { z \mathrm { G S E } } = - 2 4 . 4 \mathrm { k m } { \cdot } \mathrm { s } ^ { - 1 }$ ；太阳风动压 $P _ { \mathrm { d y n } } = 1 . 3 7 \mathrm { n P a }$ ，行星际磁场强度 $\begin{array} { r c l } { B _ { y \mathrm { G S E } } } & { = } & { - 2 . 0 8 \mathrm { n T } . } \end{array}$ ： $B _ { z \mathrm { G S E } } =$ （204号$0 . 7 1 \mathrm { n T }$ ；磁暴环电流指数[SYM- $H = - 3 \mathrm { n T }$ ：

由太阳风速度三分量可以求得太阳风速度方向，在地磁（MAG）坐标系[7」中，太阳风速度方向在磁赤道面内的投影与MAG坐标系 $\mathbf { \Psi } _ { x }$ 轴夹角即为种子点所在平面的磁经度.取距地心3个地球半径的磁经圈来进行种子点选取，选取60个种子点．为了呈现最佳视觉效果，将种子点空间坐标转换到GSW坐标系中进行磁力线绘制，因为GSW坐标系的 $\ O x z$ 平面与太阳风方向基本平行，基于GSW坐标系的 $\it { O x z }$ 平面进行投影可以有效减少视觉上的交叉重叠现象

确定种子点空间位置后便可进行磁力线绘制.生成磁力线的方法主要有两种，即数值积分法[8]和双流函数法[9-10]．本文使用的是数值积分法，利用GEOPACK（2008）工具包[11］中的五阶龙格库塔法进行磁力线追踪.对于同一个种子点，需要沿与磁场方向的正反两个方向分别追踪，如果一条磁力线追踪出来的点到地心距离小于1个地球半径，或大于100个地球半径，或追踪点超过2000个点，则停止追踪.

对于绘制结果中的冗余磁力线，需要进行过滤处理．可以将磁力线区分为封闭磁力线和开放磁力线．如果追踪出的磁力线两端点到地心距离均小于等于1个地球半径，则标记为封闭磁力线；如果追踪出的磁力线一个端点的地心距离小于1个地球半径，另一个端点的地心距离大于1个地球半径，则标记为开放磁力线.保留所有开放磁力线，过滤掉封闭磁力线区域的冗余磁力线．假设要保留磁力线射入区域的种子点追踪出来的封闭磁力线，只需判断该封闭磁力线的种子点沿磁场正方向追踪出的第一个磁力线序列点是远离地心还是趋向地心.如果是远离地心，说明该种子点位于磁力线发出区域，则应舍去该种子点对应的磁力线；如果是趋向地心，说明该种子点位于磁力线射入区域，则应保留该种子点对应的磁力线.

使用磁场强度线积分等分算法在磁经圈上选取60个种子点并进行冗余磁力线过滤，得到的绘制效果如图1所示.在地球附近,磁力线基本呈现出偶极磁场的结构特征，这体现了地球主磁场的特征．在向日侧，磁力线被压缩，形成磁层顶;在背日侧，磁力线被拉伸而形成磁尾,并且南北两个极尖区结构也很清晰，体现了太阳风与磁层相互作用的效果.结果表明，基于磁场强度线积分等分算法得到的可视化结果描绘出了地磁场的基本形态特征.

![](images/74deb26f36a80509fa462761045d9e905220ddce699779f8b99adc94a246f6fa.jpg)  
图1选取60个种子点并过滤冗余磁力线后的结果 Fig.1Results by selecting 6O seed points and filtering redundant magnetic lines

区间)内穿过的磁力线条数描述磁力线疏密，同时采用该区间中位点 $( 2 . 5 ^ { \circ } , 7 . 5 ^ { \circ } , \cdot \cdot \cdot , 3 7 5 . 5 ^ { \circ } )$ 的磁场强度作为该区间内的平均磁场强度.

图2给出了磁力线疏密与地磁场强度空间分布的关系.从图2可以看出，两极区域磁场强度较大而赤道区域磁场强度较小，相应地两磁极区域磁力线分布比较密集而赤道区域磁力线分布比较稀疏，符合地磁场的基本特征．并且磁力线疏密与磁场强度之间呈现出明显的正相关性，这说明了磁场强度线积分等分算法的有效性，

# 3.2 冗余磁力线过滤

为了从视觉效果上清晰分辨冗余磁力线过滤的效果，此处选取60个种子点的实例进行分析．图3和图4均为采用磁场强度线积分等分算法得到的种子点进行磁力线追踪后的结果．图3给出的是尚未对冗余磁力线进行过滤的情况，图4给出的是对冗余磁力线进行过滤后的结果.

从图3所示的地球周围结果可以看出，磁力线出现了两两成对的现象，而且越靠近地球，这种现象越严重，甚至出现重叠，这就是磁力线冗余现象．图4对冗余磁力线进行了过滤，磁力线由图3中的60条减少为图4中的41条，磁力线冗余现象消失，而随着重叠磁力线的消除，磁力线对地磁场可视化的准确性得到提高，视觉效果更加清晰

# 3效果分析

# 3.1 磁力线疏密与磁场强度空间分布的匹配性

为分析绘制磁力线疏密与磁场强度空间分布的匹配性，针对360个种子点的实例进行统计.采用磁经圈上每 $5 ^ { \circ }$ 区间（ $( 0 ^ { \circ }$ 5°， $5 ^ { \circ }$ ${ \cdot 1 0 ^ { \circ } }$ ，…， $3 5 5 ^ { \circ }$ $3 6 0 ^ { \circ }$

# 4结论

为使地磁场可视化绘制的磁力线能够有效反映地磁场物理特征，提出了一种等分磁场强度线积分的磁力线种子点选取算法．利用地磁场IGRF模型和T96模型进行实验绘制，得到的可视化结果能够

![](images/139551dc969023496b513fa42c7e46b7ff96e25a581c35c7b10e3e819334e063.jpg)  
图2磁力线疏密与地磁场强度空间分布的关系

Fig.2Relation between the density of magnetic lines and the distribution of geomagnetic field intensity 对磁层顶、磁尾、磁隙等结构进行清晰表达，反映出 地磁场的基本特征

![](images/c4dc28248e09a7c6350ee15939d4f07d08049e53bd02550b7a19fd78ab62bb1b.jpg)  
图3选取60个种子点并包含冗余磁力线的结果

![](images/7abe1f51bcdaff2ccd0989655639ac29b2012d86bb8208bed588a2694ee3911e.jpg)  
Fig.3Results derived from 6O seed points including redundant magnetic lines   
图4选取60个种子点并过滤冗余磁力线的结果  
Fig.4Results derived from 6O seed points excepting redundant magnetic lines

对磁场强度线积分等分算法的统计分析表明，该算法可对磁力线的空间分布进行有效控制，绘制得到的磁力线疏密与磁场强度空间分布有较好的相关性此外，算法中的冗余磁力线过滤方法能够有效修正可视化结果中的磁力线冗余现象，使地磁场磁力线可视化的物理准确性得到提高，视觉效果更加清晰

磁场强度线积分等分算法具有一定的有效性，但还有一些不足．本文在选取种子点磁经圈半径 $L$ 时具有一定随意性，选择不同的 $L$ 可能导致可视化最终结果有所不同，而算法目前并没有考虑种子点所在磁经圈的半径问题

该算法的适应性还可以进一步拓展，例如这里仅在一个磁经圈上选取种子点，没有对地磁场整体空间进行可视化，仅表现了地磁场的一个侧面，信息表达的完整性有待深入研究.但是，若考虑同时在多个磁经圈上选取种子点，存在多个磁经圈之间互相约束的问题.如果同时考虑磁经圈和磁纬圈，两者之间如何互相约束,在多个磁经圈选取种子点时导致的视觉空间中的磁力线交叉重叠现象等尚待深入分析

致谢所使用的GEOPACK-2008工具包和 T96 模型函数由NATsyganenko 教授提供.国家科技基础条件平台地球系统科学数据共享网一空间科学数据共享平台提供了数据支持.

# 参考文献

[1] TSYGANENKO NA.A model of the near magnetosphere witha dawn-dusk asymmetry 2.Parameterization and fitting to observations [J].J.Geophys.Res.: Space Phys., 2002,107(A8):SMP10-1-SMP10-17. DOI:10.1029/2001- JA000220   
[2]HE Huan.Study on Key Technologies for Visualization of Space Environment [D].Beijing:University of Chinese Academy of Sciences,2009(贺欢.空间环境可视化关键技术 研究[D].北京：中国科学院研究生院，2009)   
[3] ZHONG Jia, ZOU Ziming. The algorithm of density visualization of magnetic flux lines based on geomagnetic dipole feld[J]. Prog. Geophys.,2014,29(6): 2614-2619   
[4]BAI Chunhua,XU Wenyao,KANG Guofa.Earth's main magnetic field model[J].Prog.Geophys.，2008,23(4): 1045-1057   
[5] XU Wenyao,DU Aimin,BAI Chunhua.Magnetic feld model of the Earth's magnetosphere[J].Prog.Geophys., 2008,23(1): 14-24   
[6] WANLISS JA,SHOWALTERK M.High-resolution global storm index: Dst versus SYM- $H$ [J]. J. Geophys. Res., 2006，111,A02202.DOI:10.1029/2005JA011034   
[7] XU Wenyao. Data organization in geomagnetism and space physics and relevant coordinate systems [J].Prog. Geophys.,2007,21(4): 1043-1060   
[8] LI Qingyang,WANG Nengchao,YI Dayi. Numerical Integration [M].Beijing:Tsinghua University Press,2001(李 庆扬，王能超，易大义．数值分析[M].北京：清华大学出版社, 2001)   
[9] KNIGHT D,MALLINSON G.Visualizing unstructured flow data using dual stream functions [J].IEEE Trans. Visual.Comp．Graph.,1996,2(4):355-363   
10]KENWRIGHTD N,MALLINSONGD.A 3-d streamline tracking algorithm using dual stream functions [C]//Proceedings of the 3rd Conference on Visualization'92. Boston:IEEE Computer Society Press,1992:62-68   
11] TSYGANENKO N A.Effects of the solar wind conditions in the global magnetospheric configurations as deduced from data-based field models[C]//International Conference on Substorms.Paris:European Space Agency,1996: 181