# 碳超丰贫金属拐点星的搜寻与丰度分析

张世琳²，李海宁]，赵刚1,2

（1.中国科学院光学天文重点实验室(国家天文台）北京100101;2.中国科学院大学天文与空间科学学院北京100049）

摘要：C超丰贫金属星（CEMP）在老年恒星中的普遍存在使得它成为研究宇宙早期形成和演化的重要对象，具有不同中子俘获元素丰度特征的CEMP有着不同的起源。不同于已经历挖掘过程的巨星，主序拐点星能很好地在其表层大气保留形成初期的物质，从而可以追溯到更早期的恒星形成化学环境。我们通过LAMOST巡天数据选源并利用Subaru/HDS进行后续高分辨率光谱观测了12颗CEMP主序拐点星，其中有10颗星是首次被分析。与已有的CEMP主序拐点星观测样本相比，我们的样本中包含了更高比例的中子俘获元素不超丰CEMP恒星（CEMP-no星），发生在中等程度C超丰区域，为其起源研究提供了重要数据。对其中6颗CEMP-no星测定了Li丰度，尤其是其中3颗极贫金属星样为探讨 $[ \mathrm { F e / H } ] < - 3 . 0$ 的CEMP拐点星Li丰度特征提供了重要的新观测数据。新增样本验证了CEMP-no星在 $\mathrm { [ F e / H ] } \sim - 3 . 0$ 附近为Li-正常星，与前人结论一致；而新增的两颗CEMP-s星表现出了中等Li丰度，介于之前的较大Li丰度范围，我们的研究为CEMP-s和CEMP-nO的分类提供了辅助约束条件。

关键词：元素丰度；C超丰贫金属星；拐点星；Li丰度中图分类号：P141.5 文献标识码：A 文章编号：

# 0引言

大爆炸之后，宇宙仅由H（ $7 5 \%$ ）、He( $2 5 \%$ ）以及微量的Li元素构成。真正意义上的第一代恒星是诞生于几百万年之后，其质量分布在十到几百 $M _ { \odot }$ 错误!未找到引用源。。天文学中，将比H和He重的元素都统称为“金属”。第一代大质量恒星内部发生一系列的核聚变过程之后，迅速演化至发生超新星爆炸，炙热的恒星核产生的金属元素（原子数小于等于Fe元素）被释放到宇宙中，同时快中子俘获过程产生的元素，即重元素，也被释放，使周围气体云增丰，并孕育下一代恒星，这表明恒星中初始金属含量是随着宇宙年龄不断增长的过程。以太阳作为参考，金属丰度Z小于太阳1/10的恒星通常早于太阳形成，这些更老的恒星被称为“贫金属星”，可见贫金属星的搜寻和大样本的建立对于宇宙早期的形成和演化过程的研究有着十分重要的意义。

宇宙早期会产生大量C，恒星中C 的来源可能为以下三种：1）大质量原生星带来的原初物质；2）小质量极贫金属星自身内部演化产生；3）来自于中等质量伴星表面物质转移，伴星在AGB 演化阶段可产生大量的C[1]。

一般情况下,当VMP 星(very metal-poor star; $[ \mathrm { F e / H } ] < - 2 . 0 \rangle$ 的C丰度 $[ \mathrm { C } / \mathrm { F e } ] > 0 . 7$ 时，我们称之为C超丰贫金属星（CEMP)[1]错误!未找到引用源。。过去二十年的研究表明，VMP 中C 增丰的比例约为 $2 0 \%$ ，并且这个比例随着金属丰度的降低而增加。例如：当 $[ \mathrm { F e / H } ] < - 3 . 0$ ，该比例升至 $3 0 \%$ ；当 $\mathrm { [ F e / H ] } < - 4 . 0$ 时，该比例上升至 $7 7 \% ( 2 8 / 3 6 ^ { \mathrm { ~ [ 3 ] ~ } }$ )；在观测到的极少数$[ \mathrm { F e / H } ] < - 5 . 0$ 的超贫金属星中，几乎所有星都呈现出C超丰的特征[5-7]，如图1所示，贫金属巨星 HE 1327-2326 的金属丰度 $[ \mathrm { F e / H } ] { = } { - } 5 . 4$ ，Fe吸收线（ $\mathrm { \lambda } \lambda \mathrm { \sim } 3 9 3 0 \mathrm { \AA }$ ）变得极弱，表征C丰度的CH分子吸收带（ $\lambda { \sim } 3 9 2 8 \mathrm { \AA }$ ）却非常明显。

基于中子俘获元素丰度特征，可以将CEMP 星分为四个子类：CEMP-no（中子俘获元素不超丰），CEMP-s（慢中子俘获元素超丰)，CEMP-r/s（快／慢中子俘获元素均超丰)和CEMP-r（快中子俘获元素超丰）[2]。s-过程元素一般产生于低质量的AGB星（渐近巨星支星）[8]，而r-过程更多的是发生在超新星爆炸核塌缩、中子星并合等事件中错误!未找到引用源。错误!未找到引用源。目前观测样本较多的是CEMP-s和CEMP-no型星，关于前者的起源普遍认为与含AGB子星的双星系统有关，而CEMP-no的起源仍是未解之谜。

![](images/80de7574b21ba27deed180dfbd64d3717f92faca756c100a4fca5b5dcdfad088.jpg)  
图1不同金属丰度的恒星光谱比较，随着金属丰度的降低，Fel吸收线强度变弱，三颗星有着相似的有效温度和表面重力，底部的光谱 HE1327-2326为[Fe/H]值在-5.0以下的恒星，可以看出在Fel吸收线极弱的情况下表征C丰度CH吸收线依然清晰可见 $[ 1 5 ] _ { \circ }$ 左下插图展示了HE1327-2326的Subaru 光谱探测到的 $3 8 6 \mathsf { n m }$ 处最强Fe|线（等值宽度为 $0 . 6 4 \mathsf { p m }$

Figure 1Spectrum of stars with different metalicity. The Fe Ilines are geting weaker with declining metalicity. All three stars have a similar effective temperature and gravity. In HE

1327-2326, we note the absence of the Fe Iline at 393 nm together with the appearance of CH lines.The inset shows the strongest detected Fe Iline (0.64 pm equivalent width) at 386 nm in the Subaru data

在贫金属星中，Li 元素丰度是很重要的课题，因为它是大爆炸中产生的唯一“金属”，贫金属星中观测到的Li丰度，几乎全部来自于大爆炸时期。在恒星演化过程中，当其内部温度高于 $2 . 5 { \times } 1 0 ^ { 6 } \mathrm { K }$ 时，Li元素很容易被核反应瓦解。当恒星演化至红巨星阶段，内部物质通过对流与大气表面物质发生混合，导致恒星表面Li丰度会因稀释作用而降低至少一个量级。因此研究贫金属拐点星Li丰度特征对于原初Li合成过程非常重要。另一方面，文[10」中首次发现贫金属拐点星（其定义为 $T _ { e f f } \geq 5 8 0 0 \ : K$ 且[Fe/H]≤-1.51）大致上都有着同样的Li丰度，其分布情况不会随着有效温度或者金属丰度而变化，这种特征被称为"Li平台”。基于宇宙微波背景辐射与标准大爆炸核合成模型相结合的重子数密度估计错误!未找到引用源。[13],文［14]充分考虑了宇宙参数之后给出Li元素的原初值在A(Li)=2.66－2.73之间。该丰度值比“Li平台”大约高了0.5dex，目前对于该差值并没有合理的解释，这就是非常著名的“Li 丰度之谜"。 因此研究贫金属拐点星Li 丰度特征对于深入理解原初Li 合成过程非常重要。

本文通过CEMP星拐点星高分辨率光谱样本，对其元素丰度特征进行分析与统计，检验和约束CEMP 星的形成和演化理论模型，更好地理解早期天体核合成和化学演化历史。第 2部分简述了不同CEMP子类恒星的丰度特征及其起源；第3部分介绍了CEMP拐点星样本的来源并对样本的元素丰度特征进行了分析；第4部分归纳总结了本文的主要内容。

# 1不同类别CEMP星起源的研究现状

# 1.1CEMP-s恒星起源

当 $[ \mathrm { F e / H } ] > - 3 . 0$ 时，大多数CEMP 星都表现出很强的 ${ \mathrm { s } } - { }$ 过程元素增丰，Aoki 等人(2007)

错误!未找到引用源。的研究表明，星系中至少 $8 0 \%$ 的CEMP 恒星同时呈现出了Ba丰度超丰现象，它们的类太阳元素绝大多数是通过 $\mathrm { s } ^ { - }$ 过程产生的( $\left( 8 9 \% ^ { \left[ 1 6 \right] } \right.$ )，因此这类星被称为CEMP-S型星。C，Ba 以及其它s-过程元素的同时增丰现象可以通过一种理论机制解释：CEMP-s 型星经历了从处于AGB阶段的伴星表面吸积物质的过程。观测数据表明，大多数CEMP-s 型星都表现出了与轨道运行方向一致的视向速度变化[17-19]，意味着它们可能是处于双星或者多星系统中，为双星表面物质转移机制提供证据。同时CEMP-s样本星s-过程元素丰度分布范围很广，表明它们的表面大气可能来自不同质量伴星，为AGB核合成理论提供有用的约束条件。

# 1.2CEMP-no星起源

一般情况下,CEMP-no 星的金属丰度比 CEMP-s 星更低,当金属丰度[Fe/H]<-4.0(ultrametal-pOor，UMP)时，绝大部分CEMP 星都可以被划分为CEMP-no 型星。很多观测证据表明，CEMP-no 型星是宇宙中极早期形成的小质量恒星，因此它们对于追溯产生第一代恒星的分子云化学构成十分重要[19]。

与 CEMP-s 星的高双星率不同的是，CEMP-no 星中的双星比例大约为 $1 7 \pm 9 \%$ [20]错误!未找到引用源。，因此二者有着非常不同的增丰机制。CEMP-no 星一种可能是由大质量高速旋转的 MMP（mega metal-poor）[2-25]前身星演化而来，被称为自旋星（spinstars）；另一种起源可能是其组成物质源于与第一代恒星相关的暗弱超新星，这类超新星在爆发中会经历很强的混合和回落[26-29]。

# 1.3CEMP-r恒星起源

二十世纪五十年代，研究者第一次意识到太阳的重元素丰度须由 r-过程来解释[31][32],当中子密度达到 $n _ { n } > 1 0 ^ { 2 2 } c m ^ { - 3 }$ 时，会发生快中子俘获过程，然后在1-2 秒内，基核被中子轰炸形成极不稳定的富中子同位素，包括铀以后的元素。一旦中子流停止，原子核衰变形成稳定的同位素，包括锕系元素针 $T h _ { 9 0 } ^ { 2 3 2 }$ 和铀 $U _ { 9 2 } ^ { 2 3 8 }$ 。

只有少数的天体物理事件可以产生如此高的中子密度，如超新星核塌缩、磁转动喷射超新星、双中子星并合以及中子星-黑洞并合（参见文［30]及其引用)。验证这些理论一直是核物理的重大挑战，近年来矮星系中的年老恒星天文观测表明中子星并合极有可能是产生r-过程元素的主要天体物理事件错误!未找到引用源。。

# 1.4CEMP-r/s恒星起源

有一部分CEMP 星 $\mathrm { s } -$ 过程元素增丰的同时， $\mathrm { r } ^ { - }$ 过程元素也表现出增丰现象，例如铕 $E u _ { 6 3 } ^ { 1 5 2 }$ （204$9 4 \%$ 来源于 $\mathrm { r } ^ { - }$ 过程［16])。这类星被称为CEMP-r/s型星，与CEMP-s星相比，两类星的轻-s元素（锶 $S r _ { 3 8 } ^ { 8 8 }$ ，钇 $Y _ { 3 9 } ^ { 8 9 }$ 和锆 ${ Z r } _ { 4 0 } ^ { 9 1 }$ )丰度大致相同[33],但CEMP-r/s 星的重-s元素（钡 $B a _ { 5 6 } ^ { 1 3 7 }$ ，澜$L a _ { 5 7 } ^ { 1 3 9 }$ 和铈 $C e _ { 5 8 } ^ { 1 4 0 }$ ）丰度平均水平高于[Eu/Fe]≤1的CEMP-s星。文［34］和文［35］讨论了多种理论机制，其中有很多机制认为CEMP-r/s星中的s-元素全部来自于双星系统中 AGB 主星的污染，与 CEMP-s 星类似。但有一个普遍的认知是，AGB 星内部中子密度并未达到可以激发r-过程的高度，因此CEMP-s 的形成机制并不能解释观测到的CEMP-r/s 星中的丰度特征。这使得CEMP-r/s 型星的起源存在争议，文［34］和［35］等人提出了几种方案：a)形成双星系统的气体云是因前身星的超新星爆发遗留的富r-过程元素气体；b)r-过程核合成在一些低金属丰度的AGB 恒星的环境下能够被激发;c)r-过程元素是三星系统中的第三颗大质量恒星或者双星系统中的主星抛射物质；d)1.5型超新星爆发；e)或者经历吸积过程引发的塌缩变成一颗中子星。

文［36］引入了中等中子俘获过程（i-过程)，该过程在ABG 阶段会因为某些环境而激发，与CEMP-s 类似，发生于双星系统中的星风物质吸积过程，它对应了上述的b）方案，该模型可以重现大部分观测样本的中子俘获元素丰度特征，似乎可以为CEMP-r/s 的起源提供一个合理解释。

# 2基于LAMOST-Subaru 观测样本的 CEMP 拐点星研究

# 2.1CEMP拐点星样本筛选

目前已有的工作中，CEMP 样本星绝大部份都分布在巨星支（注意：贫金属星中巨星比例就很高)。其中一个原因是因为通常用来作为C超丰星选源依据的G-波段CH分子带对温度的敏感度高，随着有效温度的上升，该波段的观测难度也随之增加，导致高温星在样本中的比例减少。巨星至少已经经历了第一次挖掘过程，它们的表面大气已发生混合；而主序拐点星（本文中定义为 $T _ { e f f } \geq 6 0 0 0 \mathrm { K }$ ，log $g \geq 3 . 5$ ）尚未演化至该阶段，极大程度的保留了其吸积而来的原初物质。因此主序拐点星的样本对于我们探讨CEMP 星的形成具有极其重要的意义。

我们的样本来源基于LAMOST 低分辨率光谱巡天的贫金属星搜寻大样本，并于 2014 至2016 年利用 Subaru/HDS 对其中 400 余颗进行了后续高分辨率观测[37]。高分辨率光谱波长覆盖范围为4000－6800A，分辨率为 $\mathrm { R } = 4 5 0 0$ 。利用IRAF内部标准程序进行数据约简，视向速度也经由IRAF中的fxcor 程序获得。

基于 Subaru高分辨率光谱样本星的大气参数初步估计采用了文[37」中的方法。于 2016年 Subaru 望远镜观测并分析首批得到的 300 多颗贫金属星中，选出了90 颗有效温度$T _ { e f f } \geq 6 0 0 0 \mathrm { K }$ ，且光谱在4300A 附近的信噪比S/N≥40的拐点星样本候选体，C丰度的测量方法在 2.1节中有具体描述，最终在这 90 颗候选体中得到了12 颗[C/Fe]≥1.0或[C/Fe]测量下限为0.7的恒星，即CEMP 拐点星。这12颗样本中包含了2颗在文［38］中分析过的CEMP 恒星，样本的基本观测信息列举在表1中。

# 2.2大气参数测量

等值宽度由文［39］的线表通过高斯拟合原子吸收线测定；由于金属丰度很低的某些样本星，例如 J1658+4329,FeI吸收线数量非常有限，无法通过光谱平衡法确定有效温度 $T _ { e f f }$ ，因此我们采用了文[40]中测光法的经验公式，并选择红化改正后的 $( V - K ) _ { 0 }$ 参数计算得到;由于Gaia DR2为所有样本星提供了可靠的视差，因此表面重力log $g$ 通过视差法估算，即文[41］中公式（1）和（2)；恒星质量采用典型的贫金属星质量 $0 . 8 M _ { \odot }$ ，；微观湍流速度是通过调节FeI线等值宽度和Fe丰度测量值之间的平衡得到。所有的测光大气参数列在表2，样本星在赫罗图上的分布如图2所示，作为对比的参考样本是文错误!未找到引用源。中测量和搜集的CEMP 拐点星以及 SAGA 数据库[43-45]中的 CEMP 样本星。

# 2.3元素丰度测定

对于丰度分析，我们采用了一维 Kurucz新不透明分布函数（NEWODF）插值法，文［46]的ATLAS9 LTE 大气模型，以及新版的丰度分析程序 M00G(文［47]，version 2017）。对这12 颗样本星，总共测定了12种元素丰度。大多数元素的丰度都是直接通过原子吸收线的等值宽度进行估计，C 和Li丰度是由光谱综合法测量得到，太阳元素丰度采用文［48］测量结果，样本星元素丰度测量结果见表3。

![](images/f9be4d72362856a97f91a87590ead43551d072a3c1608ab73a6aead2d3dd0bdd.jpg)  
图2样本候选体（圆形）在赫罗图上的分布，以及参考文献中CEMP拐点星（三角形），背景星（叉号）为来自 SAGA数据库的CEMP 样本星。

Figure 2 Surface gravity as a function of effective temperature in the HR diagram. Circles and triangles indicate our program stars and literature sample respectively. Crosses refer to background stars from SAGA database.

我们用理论光谱拟合 4300A附近的G波段CH分子吸收带来估计C丰度，CH-AX分子线表参数来自文［49]，谱线致宽选用高斯拟合。Li丰度通过测量6707.80A附近的共振双线得到，选用了文［50］中的线表，同位素比例设为 $^ 7 L i / ^ { 6 } L i = 3 0$ 。

# 2.4样本星分类

根据文[1]的分类定义，12颗样本星中有6颗可以被归为CEMP-no 星，即使考虑文[38]中分类的修正方案（修正了 $[ \mathrm { C } / \mathrm { F e } ] > 2 . 0$ 的 CEMP 分类法则)，结果依然不受影响，因为所有CEMP-no 样本星都分布在[C/Fe] $< 2 . 0$ 的区域，这些星不仅重中子俘获元素没有表现出增丰，Sr 丰度也是不增丰。

[C/Fe]和[Ba/Fe]随[Fe/H]的分布函数见图3，可见相对于参考样本，我们的样本星中包含的CEMP-no 比例明显更高，尤其是对于C丰度中等增丰的样本星而言。这个结果是意料之中的，因为在以往的工作中，CEMP 拐点星的工作都是基于G-波段CH分子带吸收强度的目测结果，使得挑选出的样本星趋于C丰度更高的恒星。而图中CEMP-no的分布情况表明，当[C/Fe]< 2.0时，CEMP-no 所占的比例开始增加。

# 2.5Li元素研究

贫金属样本星Li丰度研究相关工作表明，大部分拐点星均落在“Li平台”范围内，但也存在一些特殊样本为Li丰度“异常”星。当金属丰度 $\mathrm { [ F e / H ] } < - 4 . 0$ （即UMP）时，所有已知的观测样本的Li丰度（或丰度上限）都低于“Li平台”。例如，目前为止金属丰度最低的C超丰拐点星HE 1327-2326，A(Li)<0.70[51][52]。因此，尽管在金属丰度更低（更年老）的拐点恒星中，理论预言的Li消耗过程应该更弱，但实际观测结果表明，在极贫金属星中存在着其它可以激发Li 消耗的过程[53]。另一方面，一个显著的特点是很高比例的 UMP星都表现出了C超丰现象，并且所有的C超丰星都是CEMP-no星[54]，这意味着我们很有必要研究Li消耗和C超丰之间的关系。

![](images/bb05f56feed91e2c8eee87affee4393d75b06673f9cfdd9a32fbd55ed2cf70f9.jpg)  
图3C丰度([C/Fe])和Ba丰度([Ba/Fe])随金属丰度[Fe/H]的分布，图标同图2，并且在此图中实心图标代表CEMP-no，空心图标代表CEMP-s，空心中带"叉号"的为未能明确分类的样本。  
Figure 3 Abundance ratios of [C/Fe] and [Ba/Fe] as functions of $[ F e / H ]$ . Symbols are the same   
as Figure 2. open symbols are CEMP-s stars,filed symbols are CEMP-no stars and symbols

with a cross are CEMP stars that cannot be classified.

为检验极贫金属星Li 消耗和C超丰之间是否存在必然联系，最好的方法是将$[ \mathrm { F e / H } ] < - 4 . 0$ 的C 超丰星和C正常星进行对比，但实际上目前为止仅观测到一颗UMP 的C不超丰的星(SDSS J102915+172927，[Fe/H]=-4.89；文［55]）。这颗星的 Li 丰度很低（20 $( \mathrm { A ( L i ) } < 1 . 1 )$ ，且C和N均未表现出明显的超丰现象，通过理论光谱拟合，仅能给出C 丰度上限值： $[ \mathrm { C / H } ] < - 3 . 8 1$ ， $[ \mathrm { C } / \mathrm { F e } ] < 0 . 9 3$ ，似乎暗示着贫金属星的Li 消耗过程与C 增丰现象并不存在直接关系。

另一个可行的方法是假设 $\mathrm { [ F e / H ] } \sim - 3 . 0 \$ 与 $\mathrm { [ F e / H ] } < - 4 . 0$ 的 CEMP-no 恒星起源是一致，研究 $\mathrm { [ F e / H ] } \sim - 3 . 0$ 的CEMP-no 恒星中的Li丰度，并与相同金属丰度情况下的C正常星进行比较，以探讨C丰度和Li丰度的关系。但目前该范围内的CEMP-no 星样本很少，文［38]中增加了两个新的样本 $( \mathrm { J 1 3 0 5 ^ { + } 2 8 1 5 }$ 和J1410-0555)，使得总样本数变为4颗，首次作为小样本进行讨论。

在这12 颗金属丰度范围在 $- 3 . 5 < \mathrm { [ F e / H ] } < - 2 . 0$ 的样本星中，我们测定了9颗星的 Li丰度（或上限)，包括6颗CEMP-no 星和2颗CEMP-s 星以及1颗不能明确分类的CEMP 星。更重要的是，我们的样本中包含了3颗金属丰度 $\mathrm { [ F e / H ] } < - 3 . 0$ 的 CEMP-no星$\langle 3 5 2 + 0 5 1 4 \$ ,J1410-0555和 $\mathrm { J 1 6 5 8 + 4 3 2 9 }$ )，为数量有限的该类特殊恒星增加了新的观测样本。在文［38］中，定义Li丰度 $1 . 8 < \mathrm { A ( L i ) } < 2 . 4$ 为 Li-正常恒星，当A(Li）<1.8时，定义为Li-贫恒星。

我们将参考文献中的CEMP 样本（具体来源参照文［38]）和来自 SAGA数据库的C 正常贫金属星Li丰度A(Li)随[Fe/H]的分布展示在图4,我们的样本基本符合文[38]中的结论，即在金属丰度 $- 3 . 5 < \mathrm { [ F e / H ] } < - 2 . 0$ 范围内的所有CEMP-no 星都是Li-正常恒星，但CEMP-S中同时存在Li-正常和Li-贫的恒星。而在 69 颗来自 SAGA 数据库的C 正常星中，仅有两颗星表现出了Li-贫的特征，一颗是 HE 0411-3558 $( T _ { e f f } = 6 3 0 0 , \log g = 3 . 7 , [ \mathrm { F e / H } ] =$ $- 2 . 8 , [ \mathrm { C / F e } ] < 0 . 7 , \mathrm { A ( L i ) } < 1 . 4 4$ ；文[56]),另一颗是 CS 22957-019(Teff = 6070K,log $g =$ 3.75, $[ \mathrm { F e / H } ] = - 2 . 4 3 , [ \mathrm { C / F e } ] = 0 . 3 4 , \mathrm { A } ( \mathrm { L i } ) = 1 . 5 6$ ；文［57]），其余样本也均为Li正常星。因此在 $\mathrm { [ F e / H ] } \sim - 3 . 0$ 与 $[ \mathrm { F e / H } ] < - 4 . 0$ 的CEMP-no 恒星有着相同起源的假设下，可以得出结论，UMP 恒星的低Li丰度并不是C超丰造成的，而更可能是与低金属丰度相关。目前虽然并没有确切的形成机制可以解决极贫金属星的低Li丰度问题，但一个可能的猜测是，在前主序阶段Li元素被消耗之后未能吸积到富Li的星际介质。也有可能是UMP 星大部分形成于快速旋转的不含Li的 Pop III（星族III）星，在这种情况下，金属丰度[Fe/H]～-3.0的CEMP-no 星诞生的气体云中，PopIII星抛射气体已基本被原初气体完全稀释。

CEMP-s 星与CEMP-no 星呈现的Li丰度差异很可能源自于CEMP-s 极高的双星率，导致CEMP-s 星经历大量的质量转移过程，而该过程在CEMP-no星中发生的概率却很低。进一步的，CEMP-no 和CEMP-s 星存在的Li 丰度分布差异性，可以作为 $[ \mathrm { F e / H } ] \geq - 3 . 5$ 的CEMP星

![](images/4c192fc3ccb0b12c8a9f35450b23095f5b77c183d54f0d1a4fcc756207e9d340.jpg)  
图4Li丰度（A（Li))随金属丰度[Fe/H]的分布，图标同图3，黑色小点代表SAGA数据库中得到的C正常贫金属星。

Figure 4 A(Li) as a function of $[ F e / H ]$ .Symbols are the same as Figure 3. Black dots refer to C-normal stars searched from SAGA database.

子类划分的辅助依据，即CEMP-no 星Li丰度都在 $\mathrm { A ( L i ) } = 1 . 8 - 2 . 4$ 范围内，而Li贫的恒星则应是CEMP-s星。但这并不能作为一个严格的分类准则，因为有一部分CEMP-s 星也具有正常的Li 丰度。

# 3总结和展望

本文列举了各类CEMP 主序拐点星的丰度特征及其可能的形成机制，并分析了12颗高分辨率光谱观测的CEMP 拐点星。该样本含有6颗CEMP-no星，增加了此类特殊天体的样本数量。同时通过对9颗样本星测定Li丰度，并结合以往的CEMP 样本，对贫金属星中Li丰度和C丰度关系进行了分析，并讨论了CEMP 星中Li丰度的起源和消耗理论。为了更加明确各类CEMP 星中C元素、中子俘获元素以及Li元素的起源，更大的高分辨率高信噪比观测样本显得尤为重要，尤其是金属丰度[Fe/H]低于-3.0 的极端贫金属星样本。目前该样本中一颗Ba元素丰度极端超丰的CEMP-s星J0119-0121得到了Subaru望远镜近紫外光谱的后续观测，其元素丰度模式的细致研究结果对限制AGB的质量等基本性质具有重要的意义。

# 表1.样本候选体和观测信息

Table 1:Program stars and observations   

<html><body><table><tr><td>Star</td><td>R. A. (J2000)</td><td>Dec (J2000)</td><td>observe yyyy-mm-dd</td><td>date UT</td><td>EXPTIME (s)</td><td>VHelio (km s−1)</td><td>S/N (pixel-1)</td></tr><tr><td>J0119-0121</td><td>01:19:39. 222</td><td>-01:21:50.45</td><td>2015-11-30</td><td>09:38:54. 763</td><td>1800.00</td><td>-92</td><td>39</td></tr><tr><td>J0352+0514</td><td>03:52:10.743</td><td>+05:14:50.83</td><td>2015-11-30</td><td>11:11:20. 186</td><td>900.000</td><td>-46</td><td>67</td></tr><tr><td>J0924+2651</td><td>09:24:48.710</td><td>+26:51:48.20</td><td>2016-05-28</td><td>06:11:27. 722</td><td>600.000</td><td>-163</td><td>95</td></tr><tr><td>J1003-0358</td><td>10:03:57. 555</td><td>-03:58:54.31</td><td>2016-05-29</td><td>07:06:23.195</td><td>600.000</td><td>69</td><td>40</td></tr><tr><td>J1011+3524</td><td>10:11:26.181</td><td>+35:24:12. 27</td><td>2016-05-28</td><td>06:23:59.643</td><td>600.000</td><td>28</td><td>49</td></tr><tr><td>J1044-0358</td><td>10:44:10.697</td><td>-03:58:59.29</td><td>2016-05-29</td><td>07:18:28.426</td><td>600.000</td><td>61</td><td>63</td></tr><tr><td>J1058-0138</td><td>10:58:42. 235</td><td>-01:38:25. 79</td><td>2016-05-29</td><td>07:30:29.457</td><td>600.000</td><td>-22</td><td>61</td></tr><tr><td>J1135+3100</td><td>11:35:18. 096</td><td>+31:00:21.85</td><td>2016-05-24</td><td>07:20:36. 363</td><td>600.000</td><td>-62</td><td>70</td></tr><tr><td>J1305+2815</td><td>13:05:34. 331</td><td>+28:15:06.86</td><td>2014-05-11</td><td>11:20:46. 423</td><td>51300.0</td><td>37</td><td>77</td></tr><tr><td>J1359+2112</td><td>13:59:33. 185</td><td>+21:13:00.03</td><td>2016-05-29</td><td>10:16:56. 772</td><td>600.000</td><td>-19</td><td>42</td></tr><tr><td>J1410-0555</td><td>14:10:02. 795</td><td>-05:55:58.02</td><td>2014-05-10</td><td>11:32:44. 750</td><td>51300.0</td><td>92</td><td>82</td></tr><tr><td>J1658+4329</td><td>16:58:44. 153</td><td>+43:29:02.93</td><td>2014-05-10</td><td>13:55:41. 331</td><td>51300.0</td><td>-120</td><td>60</td></tr></table></body></html>

# 表2.测光数据和大气参数

Table 2: Photometric Data and Atmospheric Parameters   

<html><body><table><tr><td>Star</td><td>V-K (mag)</td><td>E(B-V) (mag)</td><td>Teff (V-K) (K)</td><td>logg</td><td>[Fe/H]</td><td>(km s-1)</td><td>Class</td></tr><tr><td>J0119-0121</td><td>1. 24</td><td>0.04</td><td>6276</td><td>3.9</td><td>-2.93</td><td>0.25</td><td>CEMP-s</td></tr><tr><td>J0352+0514</td><td>1.38</td><td>0.23</td><td>6028</td><td>3.8</td><td>-3.01</td><td>0.45</td><td>CEMP-no</td></tr><tr><td>J0924+2651</td><td>1.21</td><td>0.02</td><td>6301</td><td>3.8</td><td>-2.56</td><td>1.47</td><td>CEMP-no</td></tr><tr><td>J1003-0358</td><td>1. 24</td><td>0.03</td><td>6233</td><td>3.9</td><td>-2.32</td><td>1.84</td><td>CEMP-s</td></tr><tr><td>J1011+3524</td><td>1. 33</td><td>0.01</td><td>6062</td><td>4.3</td><td>-2.3</td><td>1. 44</td><td>CEMP-s</td></tr><tr><td>J1044-0358</td><td>1.21</td><td>0.04</td><td>6290</td><td>3.8</td><td>-2.2</td><td>1.8</td><td>CEMP-s</td></tr><tr><td>J1058-0138</td><td>1.34</td><td>0.05</td><td>6045</td><td>4. 1</td><td>-2.39</td><td>1.82</td><td>unclassified</td></tr><tr><td>J1135+3100</td><td>1.19</td><td>0.02</td><td>6378</td><td>4</td><td>-2.9</td><td>1.91</td><td>CEMP-no</td></tr><tr><td>J1305+2815</td><td>1.3</td><td>0.01</td><td>6154</td><td>3.7</td><td>-2.93</td><td>1.52</td><td>CEMP-no</td></tr><tr><td>J1359+2112</td><td>1.27</td><td>0.03</td><td>6169</td><td>3.9</td><td>-2.35</td><td>1.57</td><td>unclassified</td></tr><tr><td>J1410-0555</td><td>1. 23</td><td>0.03</td><td>6311</td><td>4</td><td>-3.17</td><td>1. 44</td><td>CEMP-no</td></tr><tr><td>J1658+4329</td><td>1.18</td><td>0.02</td><td>6405</td><td>3.7</td><td>-3.07</td><td>1.82</td><td>CEMP-no</td></tr></table></body></html>

# 3.元素丰度测量结果

Table 3: Chemical Abundances Results   

<html><body><table><tr><td></td><td></td><td colspan="2">J0119-0121</td><td colspan="2">J0352+0514</td><td colspan="2"></td><td colspan="3">J0924+2651</td><td colspan="3">J1003-0358</td><td colspan="3">J1011+3524</td><td colspan="3">J1044-0358</td></tr><tr><td></td><td></td><td colspan="2">N</td><td>0</td><td colspan="2"></td><td></td><td colspan="2">N</td><td></td><td colspan="2">N</td><td></td><td colspan="2">N</td><td></td><td colspan="2">N</td></tr><tr><td>A(Li)</td><td>LiI</td><td>：</td><td></td><td></td><td>2.01</td><td></td><td></td><td>2.09</td><td></td><td></td><td><1.90</td><td></td><td><1.60</td><td></td><td></td><td>：</td><td></td><td></td></tr><tr><td>[C/Fe]</td><td>CH</td><td>2.26</td><td></td><td></td><td>>0.70</td><td></td><td>>0.70</td><td></td><td></td><td>1. 68</td><td></td><td></td><td>1.51</td><td></td><td></td><td>1.45</td><td></td><td></td></tr><tr><td>[Na/Fe]</td><td>NaI</td><td>1.93</td><td>0.10</td><td></td><td>-0.31</td><td>0.04</td><td>0.17</td><td>3</td><td>0.16</td><td>0.38</td><td>2</td><td>0.12</td><td>0.47</td><td>2</td><td>0.07</td><td>0.61</td><td>2</td><td>0.02</td></tr><tr><td>[Mg/Fe]</td><td>MgI</td><td>0.93</td><td>6 0.14</td><td></td><td>0.36</td><td>0.15</td><td>0.46</td><td>6</td><td>0.16</td><td>0.40</td><td>7</td><td>0.17</td><td>0.49</td><td>4</td><td>0.12</td><td>0.42</td><td>6</td><td>0.09</td></tr><tr><td>[Ca/Fe]</td><td>CaI</td><td>0.29</td><td>7 0.16</td><td></td><td>0.25</td><td>0.15</td><td>0.43</td><td>14</td><td>0.11</td><td>0.50</td><td>18</td><td>0.11</td><td>0.42</td><td>25</td><td>0.11</td><td>0.49</td><td>21</td><td>0.08</td></tr><tr><td>[Sc/Fe]</td><td>Sc II</td><td>0.61</td><td>2 0.03</td><td></td><td>-0.33</td><td>：</td><td>0.08</td><td>6</td><td>0.11</td><td>0.22</td><td>6</td><td>0.14</td><td>0.20</td><td>2</td><td>0.07</td><td>0.21</td><td>6</td><td>0.06</td></tr><tr><td>[Ti/Fe]</td><td>TiII</td><td>0.47</td><td>7 0.13</td><td></td><td>0.35 12</td><td>0.09</td><td></td><td>23</td><td>0.08</td><td>0.41</td><td>21</td><td>0.12</td><td>0.39</td><td>20</td><td>0.12</td><td>0.47</td><td>24</td><td>0.10</td></tr><tr><td>[Cr/Fe]</td><td>CrI</td><td>-0.48</td><td>2 0.17</td><td></td><td>-0.22</td><td>0.10</td><td>-0.14</td><td>5</td><td>0.03</td><td>-0.12</td><td>6</td><td>0.11</td><td>-0.18</td><td>5</td><td>0.12</td><td>-0.10</td><td>5</td><td>0.10</td></tr><tr><td>[Co/Fe]</td><td>CoI</td><td>0.22</td><td>1 ：</td><td></td><td>0.11</td><td>0.26</td><td></td><td>1</td><td>：</td><td>0.00</td><td>1</td><td>：</td><td>0.05</td><td>2</td><td>0.16</td><td>0.24</td><td>1</td><td>：</td></tr><tr><td>[Fe/Fe]</td><td>FeII</td><td>0.00</td><td>5 0.19</td><td></td><td>0.00</td><td>0.08</td><td></td><td>13</td><td>0.12</td><td>0.00</td><td>15</td><td>0.16</td><td>0.00</td><td>13</td><td>0.10</td><td>0.00</td><td>14</td><td>0.12</td></tr><tr><td>[Ni/Fe]</td><td>NiI</td><td>0.04</td><td>1 0.00</td><td>0.20</td><td></td><td>0.18</td><td></td><td>：</td><td>：</td><td>-0.06</td><td>2</td><td>0.15</td><td>-0.05</td><td>4</td><td>0.06</td><td>-0.07</td><td>3</td><td>0.12</td></tr><tr><td>[Sr/Fe]</td><td>Sr II</td><td>1.37</td><td>2 0.18</td><td></td><td>-0.32</td><td>0.11</td><td>0.01</td><td>2</td><td>0.06</td><td>0.66</td><td>2</td><td>0.24</td><td>0.40</td><td>2</td><td>0.04</td><td>0.48</td><td>2</td><td>0.05</td></tr><tr><td>[Ba/Fe]</td><td>Ba II</td><td>2.95</td><td>3 0.18</td><td>-0.99</td><td>1</td><td></td><td>-0.43</td><td>2</td><td>0.12</td><td>1.56</td><td>3</td><td>0.14</td><td>1.39</td><td>4</td><td>0.17</td><td>1.34</td><td>4</td><td>0.17</td></tr><tr><td></td><td></td><td>J1058-0138</td><td></td><td></td><td>J1135+3100</td><td></td><td></td><td>J1305+2815</td><td></td><td>J1359+2112</td><td></td><td></td><td>J1410-0555</td><td></td><td></td><td>J1658+4329</td><td></td><td></td></tr><tr><td></td><td colspan="3"></td><td colspan="3">N</td><td colspan="3">N</td><td colspan="3">N</td><td colspan="3">N</td><td colspan="3">N</td></tr><tr><td>A(Li)</td><td>LiI</td><td>1.45</td><td></td><td></td><td>2.35</td><td></td><td></td><td>2.12</td><td></td><td></td><td></td><td>0</td><td>2.18</td><td></td><td></td><td>2.23</td><td></td><td>0</td></tr><tr><td>[C/Fe]</td><td>CH</td><td>1. 22</td><td></td><td></td><td>>1.00</td><td></td><td>>0.90</td><td></td><td></td><td>1.10</td><td></td><td></td><td>1.87</td><td></td><td></td><td>>1.00</td><td></td><td></td></tr><tr><td>[Na/Fe]</td><td>NaI</td><td>0.56</td><td>：</td><td></td><td>0.38</td><td>0.08</td><td>-0.09</td><td>2</td><td>0.10</td><td>0.24</td><td>2</td><td>0.07</td><td>0.66</td><td>3</td><td>0.12</td><td>-0.16</td><td>2</td><td>0.05</td></tr><tr><td>[Mg/Fe]</td><td>MgI</td><td>0.45</td><td>6 0.11</td><td></td><td>0.48</td><td>4 0.03</td><td>0.52</td><td>3</td><td>0.14</td><td>0.40</td><td>6</td><td>0.12</td><td>0.92</td><td>8</td><td>0.13</td><td>0.42</td><td>3</td><td>0.09</td></tr><tr><td>[Ca/Fe]</td><td>CaI</td><td>0.29</td><td>9 0.12</td><td></td><td>0.51 11</td><td>0.12</td><td>0.46</td><td>14</td><td>0.17</td><td>0.42</td><td>18</td><td>0.09</td><td>0.32</td><td>3</td><td>0.08</td><td>0.49</td><td>7</td><td>0.16</td></tr></table></body></html>

<html><body><table><tr><td>[Sc/Fe]</td><td>Sc II</td><td>-0.08</td><td>4</td><td>0.05</td><td>0.21</td><td>4</td><td>0.12</td><td>0.30</td><td>5</td><td>0.06</td><td>0.12</td><td>7</td><td>0.13</td><td>0.12</td><td>3</td><td>0.15</td><td>0.31</td><td>7</td><td>0.28</td></tr><tr><td>[Ti/Fe]</td><td>TiII</td><td>0.21</td><td>18</td><td>0.14</td><td>0.49</td><td>14</td><td>0.15</td><td>0.50</td><td>24</td><td>0.17</td><td>0.39</td><td>29</td><td>0.13</td><td>0.35</td><td>13</td><td>0.20</td><td>0.49</td><td>15</td><td>0.11</td></tr><tr><td>[Sc/Fe]</td><td>CrI</td><td>-0.10</td><td>6</td><td>0.11</td><td>-0.05</td><td>5</td><td>0.05</td><td>-0.20</td><td>5</td><td>0.08</td><td>-0.09</td><td>8</td><td>0.14</td><td>-0.21</td><td>5</td><td>0.13</td><td>-0.01</td><td>4</td><td>0.09</td></tr><tr><td>[Co/Fe]</td><td>CoI</td><td>0.19</td><td>2</td><td>0.18</td><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td><td>0.08</td><td>1</td><td>：</td><td>0.63</td><td>2</td><td>0.01</td><td>：</td><td>：</td><td>：</td></tr><tr><td>[Fe/Fe]</td><td>FeII</td><td>0.00</td><td>13</td><td>0.15</td><td>0.01</td><td>8</td><td>0.19</td><td>0.00</td><td>8</td><td>0.18</td><td>0.00</td><td>16</td><td>0.11</td><td>0.00</td><td>11</td><td>0.21</td><td>0.00</td><td>5</td><td>0.15</td></tr><tr><td>[Ni/Fe]</td><td>NiI</td><td>0.15</td><td>4</td><td>0.11</td><td>：</td><td>：</td><td>：</td><td>-0.36</td><td>1</td><td>：</td><td>-0.10</td><td>3</td><td>0.11</td><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td></tr><tr><td>[Sr/Fe]</td><td>Sr II</td><td>-0.01</td><td>2</td><td>0.32</td><td>0.05</td><td>2</td><td>0.04</td><td>0.16</td><td>1</td><td>：</td><td>0.36</td><td>2</td><td>0.04</td><td>-0.12</td><td>2</td><td>0.04</td><td>-0.15</td><td>2</td><td>0.05</td></tr><tr><td>[Ba/Fe]</td><td>BaII</td><td>0.69</td><td>3</td><td>0.18</td><td>-0.25</td><td>1</td><td>：</td><td>-0.36</td><td>2</td><td>0.03</td><td>0.96</td><td>4</td><td>0.19</td><td>-0.32</td><td>2</td><td>0.05</td><td>-0.42</td><td>2</td><td>0.15</td></tr></table></body></html>

# Searching for Carbon-enhanced Metal-poor Main-sequence Turnoff Stars and the Abundances Analysis

Zhang Shilin1,2,Li Haining1,Zhao Gang1.2

(1.KeyLaboratoryofOpticalstronomy,ationalAstronomicalObservatories,ineseAcademyofiences,eig10,

Email: slzhang@nao.cas.cn;2.Schoolof Astronomyand Space Science,Universityof Chinese Academyof Sciences,Beijing

Abstract: Decades of studies on metal-poor stars reveal that there are large fraction of metal-poor stars showing enhancement in carbon. Carbon-enhanced metal-poor (CEMP) stars are believed to be the trace of the first nucleosynthesis process and the chemical composition of the interstellar medium at the early stage of the universe.Different abundance patterns of neutron-capture elements reflect different origins of CEMP stars. Main-sequence turnoff stars are believed to preserve primordial material in its surface atmosphere since its birth date and place,as they have not suffered from dilution, whereas giants should have already gone through at least the first dredge-up. We report high-resolution abundances analysis of 12 CEMP turnoff stars which are selected from LAMOST survey and follow-up observed with Subaru/HDS. Among them, ten are analyzed for the first time. Compared with previous works, our sample includes larger fractions of CEMP-no (indicating carbon enrichment, but no enhancement in neutron-capture elements） stars, proving important new data for moderately C-enriched metal-poor turnoff stars. Especially, this sample provides Li abundance measurements for six CEMP-no stars including three extremely metal-poor ones whose current sample is stillimited.The new sample confirmed that, when it comes to regions around $[ F e / H ] \sim - 3 . 0$ ,CEMP-no stars show normal lithium

abundances while CEMP-s stars are usually depleted in lithium.

Key words: Chemical abundances; Carbon-enhanced metal-poor; Turnoff;

Lithium

参考文献：   
[1]BrommV,CoppiPS,LarsonRB.TheFormationof heFirstStars.I.ThePrimordialStar-formingCloud[J].TheAstrophysic Jourmal,2002,564(1):-51.   
[2]Beers TC,ChristliebN.The Discoveryand Analysis of VeryMetal-Poor Stars intheGalaxy[J].Anual Reviewof Astronomy and Astrophysics,2005,43(1):531-580.   
[3]AokiW,Bers TC,ChristliebN,etal.Carbon Enhanced Metal-Poor Stars.I.Chemical Compositions of 26Stars[J]. Astrophysical Journal,2006,655:124-125.   
[4]SestitoF,LongeardN,MartinNF,etal.Tracingtheformationofthe MilkyWaythroughultra metal-poorstars[J].Monthly Notices of the Royal Astronomical Society,2018,484: 2166-2180   
[5]LeeDM,JohnstonKV,TumlinsonJ,SenB,SmonJD.AMass-dependentYieldOriginofNeutron-captureElementAbundance Distributions in Ultra-faint Dwarfs [J].Astrophysical Journal,2013,774:103-116   
[6]Placco VM,Frebel A,Beers TC,et al. CARBON-ENHANCED METAL-POOR STAR FREQUENCIES IN THE GALAXY: CORRECTIONS FOR THE EFFECT OF EVOLUTIONARY STATUS ON CARBON ABUNDANCES[J]. The Astrophysical Jourmal,2014,797(1):21.   
[7]NorisJ,Frebel A.Near-feldcosmology with extremelymetal-poorstars[J].Annual Reviewof Astronomy &Astrohics, 1914, 53(53).   
[8]Placco VM,Frebel A,Beers TC,et al. CARBON-ENHANCED METAL-POOR STAR FREQUENCIES IN THE GALAXY: CORRECTIONS FOR THE EFFECT OF EVOLUTIONARY STATUS ON CARBON ABUNDANCES[J]. The Astrophysical Joumal,2014,797(1):21.   
[9]Sneden C,Cowan JJ,GalinoR.Neutron-Capture Elements in the Early Galaxy[J]. Annual Reviewof Astronomyand Astrophysics,2008,46(1):241-288.   
[10]JiAP,FrebelA,ChitiA,etal.R-processenichmentfromasingleeventinnancientdwarf galaxy[J].Nature,6,531, 610-613.   
[11]SpiteF,SpiteM,SpiteF,etal.Abundanceoflithiuminunevolvedhalostarsandolddisk stars-Interpretationand consequences[J].Astronomy & Astrophysics,1982,115(115):357-366.   
[12]Coc A,Vangioni-Flam,Elisabeth,DescouvemontP,etal. Updated Big Bang NucleosynthesisCompared with\r,Wilkinson MicrowaveAnisotropyProber,ObservationsandtheAbundanceofLightElements[J].TheAstrophysical Journal,2004, 600(2):544-552.   
[13]Spergel,D.N.,Bean,R.,Doreé,O.etal.Thre-Year Wilkinson Microwave Anisotropy Probe (WMAP)Observations: Implications for Cosmology[J].The Astrophysical Journal Supplement Series,20o7,170:377-408   
[14]Coc,A.,Uzan,J.-P,&Vangioni,.StandardbigbngnucleosynthesisandprimordialCNOabundancesafterPanck[J].Joua of Cosmology and Astroparticle Physics,2014,10,50   
[15]rebelA,Aoki W,ChristliebN,etal.Nucleosytheticsignatursofthefirststars[J].Nature,2O05,434(735):871-873.   
[16]BisterzoS,GalnoR,StraieroO,etal.Thes-procesinlow-metallitystars-II Interpretatioofhig-roution spectroscopicobservationswithasymptoticgiantbranchmodels[J].Monthlyoticesof theRoyalAstronomical Society01, 418(1):284-319.   
[17]LucatellS,BeersT,ChristliebNetal.TheFrequencyofCarbon-EhancedMetal-PoorStarsintheGalaxyfromteHERES

sample[J].Astrophysical Journal,2012,652(1):L37.

[18]Starkenburg E,Oman KA,NavaroJF,et al.The oldest and most metalpoor stars in the APOSTLELocal Group simulations[J]. Monthly Notices of the Royal Astronomical Society,2016, 465.

[19]HansenTT,AndersenJ,NordstromB,BeersTC,PlacoVM,etal.TheroleofbiariesintheenrichmentoftheearlyGalactic halo. III Carbon-enhanced metal-poor stars -- CEMP-s stars,Astronomy& Astrophysics,2016,588:A3   
[20]Hasen,C.J.,Nrdstr,B.,Hansen,T.T.,etal.Abundancesofabo-eancedmetaloorstarssonstrintsoteir formation,Astronomy & Astrophysics,2016,588:A37   
[21]Hansen TT,Andersen J,B.Nordstrom,et al.The role of binaries in the enrichmentof theearly Galactic halo.I. r-process-enhanced metal-poor stars[J]. Astronomy & Astrophysics,2016,586(2).   
[22]Meynet G,EkstromS,MaederA.Theearlystargenerations: ThedominanteffectofrotationontheCNOyields[J].Astronomy and Astrophysics,2005,447(2).   
[23]HirschiR.Verylow-metallcity massve stars:Pre-SNevolution modelsand primarynitrogen production[J].Astronomyand Astrophysics,2007,461(2):571-583.   
[24]FrischknechtU,HirschiR,ielemanFK.Non-stadard s-processinlowmetallcitymassverotatingstars[J].Astroomy and Astrophysics,2012,538,L2   
[25]Maeder,A.,&Meynet,G.Thefirststars: aclassificationofCEMP-nostars,AstronomyandAstrophysics,215,80,A32   
[26]Umeda H,NomotK.First-generation black-hole-formingsupemovaeandthe metalabundance pateofaveryiro-oor star[J]. Nature,2003,422(6934):871-873.   
[27]Tominaga N,Umeda H,Nomoto,Ken'ichi. Supernova Nucleosynthesis in Population III13-50\r,Mr, $\odot \mathrm { { u } }$ , Stars and Abundance Patterns of Extremely Metal-poor Stars[J].The Astrophysical Journal,2Oo7,660(1):516-540.   
[28]NomotoK,KobayashiC,TominagaN.NucleosythesisinStarsandtheChemicalEnrichmentofGalaxies[J].AualReview of Astronomy and Astrophysics,2013,51(1):457-509.   
[29]Tominaga N,IwamotoN,NomotoK.AbundanceProfiling ofExtremelyMetal-Poor StarsandSupernova Propetiesnthe EarlyUniverse[J].Astrophysical Journal,2013,785(2):383-390.   
[30]ThielemanFK,EichlerM,PanovIV,etal.NeutronStarMergersandNucleosynthesisofHeavyElements[J].Anual Review of Nuclear and Particle Science,2017,67(1):annurev-nucl-101916-123246.   
[31]BurbidgeEM,Burbidge GR,Fowler WA,HoyleF.Synthesis of the Elements in Stars,Reviews of Modern Physics,1957, 29:547-650   
[32]Cameron,WAG.Nuclear Astrophysics[J]. Annual Review of Nuclear Science,1958,8(1):99-326.   
[33]Abate C,Pols OR,Izard RG, Karakas AI.Carbon-enhanced metal-poor stars: a windowon AGB nucleosynthesis and biary evolution[J],Astronomy and Astrophysics,2015,581:A22   
[34]JonsellK,Barklem PS,Gustafson B,etal.The Hamburg/ESOR-processEnhanced Starsurvey (HERES)II.HE0338-3945 and the formation of the $\mathrm { r + s }$ stars[J]. 2006. 451:651   
[35]Lugaro M,CampbellSW,De Mink SE.The Mystery of CEMPs $_ { \mathrm { + r } }$ Stars and the Dual Core-Flash Neutron Superburst[J]. Publications of the Astronomical Society of Australia,20o9,26(03):322-326.   
[36]AbateC,StanclifeRJ,LiuZW.How plausibleare he proposedformationscenarios ofCEMP-r/s stars?[J]. Astronomy& Astrophysics,2016,587,A50   
[37]Li HN, Zhao G,Christlieb N,et al.SPECTROSCOPIC ANALYSIS OF METAL-POOR STARS FROM LAMOST: EARLY RESULTS[J]. The Astrophysical Journal,2015,798(2):110.   
[38]MatsunoT,Aoki W,SudaT,etal.Lithiumin CEMP-no stars: Anewconstrainton the lithiumdepletionmechanisminthe

early universe\*[J].Publications of the Astronomical Society of Japan,2O17,69(2).

[39]Aoki,W.,Beers,T.C.,LeeY.S.,etal.High-resolution SpectroscopyofExtremelyMetal-porStars fromS/SEGUE.I. Atmospheric Parameters and Chemical Compositions [J]. The Astrophysical Journal,2013,145:1-34

[40]AlonsoA,Aribas S,Martinezroger C.The empiricalscaleof temperatures of the low main sequence(FOV-K5V).[J]. Astronomy & Astrophysics,1996,313(3):873-890.   
[41]FuhrmannK,feierM,FrankC,etalheurface gravitiesofcooldarfstarsrevisited[J].GlobalChangeiology997, 12(11):2209-2219.   
[42]Aoki W,Bers T,Sivarani T,etal.Carbon-Enhanced Metal-Poor Stars.II. Main-Sequence Turnoff Starsfromthe SDSS SEGUE Sample1[J]. The Astrophysical Jourmal,2008, 678(2):1351-1371.   
[43]SudaT,Yamada S,KatsutaY,etal.The StelarAbundancesforGalacticArchaeology(SAG)DatabaseII-Implicatiosfor MixingandNucleosynthesis inExtremelyMetal-PoorStarsandChemicalEnrichmentof theGalaxy[J].MonthlyNoticesofthe Royal Astronomical Society,2011,412: 843-874   
[44]SudaTKatsutaY,Yamada S,etal.Stelarbundancesforthe GalacticArcheology (SAGA)Database--Compilationofthe Characteristicsof KnownExtremely Metal-Poor Stars[J].Publicationsof the Astronomical Societyof Japan，2008, 60(5):1159-1171.   
[45]Yamada,Suda,Takuma,etal.The StellarundancesforGalacticArchaeology (SAGA)Database-II;Analysisofect historiesforelementsandtwo modesof starformationduringtheearlyevolutionofthe MilkyWay[J].MonthlyNoticesof the Royal Astronomical Society,2013, 436(2):1362-1380.   
[46]THE MOST METAL-POOR STARS.II CHEMICAL ABUNDANCES OF 190 METAL-POOR STARS INCLUDING 10 NEW STARSWITH [Fe/H]<-3.5,[J]. The Astrophysical Journal,2013,762(1):26.   
[47]Sneden C.The nitrogenabundanceofthe very metal-oorstarHD122563.[J].AstrophysicalJoural,1973,184:839-849.   
[48]Asplund M,Grevesse N,Sauval AJ,et al. The chemical compositionof the Sun[J]. Astrophysics & Space Science,2009, 328(1-2):179-183.   
[49]Masseron,T.Plez,B,VanEck,S.,etal.Cinstelaratmosperes:aextenielinelis[J].AstronondAstropsic,01, 571:47-75.   
[50]KirbyEN,Guhathakurta P,Zhang AJ,et al.LITHIUM-RICH GIANTS IN GLOBULAR CLUSTERS[J].The Astrophysical Journal,2016,819(2):135.   
[51]AokiW,FrebelA,ChristiebN,etal.HE1327-2326,anUnevolved Starwith[Fe/H]<-5.0.I.AComprehensive Abundance Analysis[J]. The Astrophysical Journal,20O6,639:897-917.   
[52]Frebel,A.Colet,R.,Erikson,K.,Christlieb,N.,&Aoki,W.HE1327-2326,anUnevolvedStarwith[Fe/H]<-5..I.New 3D-1DCorretedAbundances fromaVeryLarge Telescope UVESSpectrum[J].TheAstrophysicalJoural,008,68488-602.   
[53]Mel'ndez,JCasagrade,Lamrz,Isplund,,&usterW.J.ObservatioalevidenceorbokenLiielate and mass-dependent Li depletion[J].Astronomy and Astrophysics,201o,515,L3   
[54]Norris,John E.; Yong,David; Besell,M.S,et al.The Most Metal-poor Stars.IV.The Two Populations with $[ \mathrm { F e / H } ] \mathrel { \sim } - 3 . 0 [ \mathrm { J } ]$ The Astrophysical Journal, 2013,762:28-46.   
[55]CaffauE,BonifacioP,P.Franois,etal.Aprimordial starintheheartoftheLion[J].Astronomy&Astrophysics,2012, 542(6):275-291.   
[56]Hansen,T.,Hansen,C.J.,Christlieb,N.etal.AnElementalAssyofVery,Extremely,ndUltra-metal-poor Stars[J].e Astrophysical Journal,2015 807:173-189   
[57]RoedererIU,Preston G W,Thompson IB,et al. A SEARCHFOR STARS OF VERY LOW METAL ABUNDANCE.VI.