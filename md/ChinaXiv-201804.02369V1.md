# 基于似物目标的快速行人检测算法

刘倩1²，李策1，杨峰1

(1．中国矿业大学(北京）机电与信息工程学院，北京 100083;2.宁夏大学 信息工程学院，银川 750001)

摘要：针对传统滑动窗口行人检测速度慢、无效窗口数量大和识别率低的问题，提出基于似物目标的快速行人检测算法。该算法首先使用改进的二值化赋范梯度算法生成目标候选集，再利用提出的NDOG 特征描述子计算目标特征。通过在INRIA和Caltech-USA两个行人数据库分析实验，证明该算法可有效减少待检测窗口数量,提高特征表示能力，且计算时间显著降低，使用线性支持向量机作为分类器可获得较高的行人检测率。

关键词：似物目标检测；二值化赋范梯度；方向梯度直方图；极限学习机 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2018.01.0115

# Rapid pedestrian detection based on generic object generation

Liu Qian1, ², Li $\mathrm { C e ^ { 1 } }$ , Yang Fengl (1.SchoolofMechanicalElectronic&InformationEngineering,ChinaUniversityofMining&Technology,Beijing10083, China;2. College of Information Engineering Ningxia University,YinChuan 75oo01,China)

Abstract: Detection ofpedestrians on the image usingasliding window moderesults ina huge amountofinvalid windows and inefficiecy.Tocircumventthese problems forpedestriandetection,this paper proposed anapproach,basedongenericobject generation,forrapid detectionof pedestrian.Firstly,the approach generated the genericobject proposals bytheImproved Binarized Normed Gradients，and thencalculated thecharacterof proposals basedonour NDOG feature descriptor. Experimental resultsover the INRIA and Caltech-USA pedestrian datasets show thatour approach reduces the numberof proposals effectivelyandimproves theeficiencyandthedetectionaccracysignificantlyalong withalinearSVMclassifier.

Keywords:generic object proposal generation; BING;HOG; ELM

# 0 引言

在科技水平飞速发展、计算机运算能力不断提高的背景下，如何使计算机更好的满足人们生产生活的实际需要是计算机视觉领域的实现目标。其中，模拟人眼视觉系统，通过对摄像头拍摄的画面进行识别和分析，提取目标对象是该领域工作者的研究热点，而自然场景下的行人识别则是该领域的重要组成部分。

基于梯度直方图（histogramof oriented gradient，HOG）[1的图像描述方法是当前人体模型建模的主要方法之一。该算法通过对图像中每个像素点的梯度幅值和梯度方向做统计的方法来描述窗口中像素点梯度分布情况。与其他常用的特征表示方法相比，HOG可较好的表征目标对象的轮廓线条，提取的特征鲁棒性强，算法简单易懂，代码量少。

为提高HOG特征的表征能力，此后产生了很多基于HOG的改进算法[2-5]，。但这些方法都无法实现快速的行人检测，且都忽略了相邻block之间的空间关系，而这个因素对梯度直方

图检测方法来说是至关重要的。

在搜索策略方面，行人检测系统[67通常先计算滑动窗口（slidingwindow）中的特征再判断该窗口是否包含行人特征。而在实际计算过程中，一副图像对应的滑动窗口数量是巨大的，并且其绝大部分是无效窗口，即不包含目标对象或只包含目标对象的一部分，因此如何减少待检测窗口的数量是提高目标识别效率的关键。似物性目标检测方法[8,9]根据人眼感知对象的原理[10]，可快速定位图像中前景目标，为在行人识别的过程中降低检测窗口数量、提高识别效率提供了有效的解决方法。

在似物目标检测算法中[1-13]，二值化赋范梯度（binarizednormed gradients,BING)检测算法利用二级支持向量机（supportvectormachine，SVM）[4]对待测目标的梯度图像进行检测。算法中对梯度图像和一级支持向量机模板做二值化处理，通过二进制运算快速实现梯度图像和模板的内积计算。与其他似物目标检测算法相比，BING算法仅需要3毫秒即可完成目标检索。因此，使用BING对图像中似物目标快速检测，为降低检测窗□数量，实现快速行人检测提供了可能。但BING算法仍有问题亟待解决，如文献[15]提出无论一级支持向量机的模板如何调整，对其算法检测率的影响均不明显。但作者没有解释造成这一问题的原因，也没有提出相应的办法予以解决。

本文通过对上述问题的认真分析，提出了基于似物目标的快速行人检测算法。首先，利用改进的BING算法快速识别图像中似物目标，然后结合改进的HOG 方法——方向梯度邻域描述子方法（neighborhood descriptor of oriented gradient，NDOG）进行行人检测。使用国际上常用的公开行人数据集测试，并与原算法进行比较。实验表明，本文提出的算法显著降低候选窗□数量，节省计算时间，并达到较高的检测率。

# 1 改进的似物性检测BING算法

# 1.1 BING算法

在2014的IEEE国际计算机视觉与模式识别会议（IEEEConference on Computer Vision and Pattern Recognition，简称CVPR）程明明等人发表的《BinarizedNormedgradients forobjectness estimationat300fps》中提出了BING算法。此算法在具有较高检测率的同时其运算速度远远超过其他同类算法。在BING 算法中，高效运行的关键是利用二进制移位运算和或运算实现测试图像和一级分类模板的内积运算得到第一阶段的似物性评估分值。尽管这一部分实现了快速内积运算，但也是文献[15]对BING 算法提出的问题所在。即无论如何调整其分类模板 $w \in R ^ { 6 4 }$ 中权值，其窗口检测率与原算法的检测率没有明显差异。

本文在对BING分析中发现，该算法在识别过程第一阶段仅包含一个二值线性分类器 $w \in R ^ { 6 4 }$ ，该分类器是基于Liblinear[16]的 squared hinge loss（或简称L2 loss）支持向量回归（support vector regression，SVR）方法计算得出。BING 实际上是利用模板 $w$ 线性拟合其他训练样本。为了量化BING在第一阶段的识别性能，在相同训练样本集下，本文使用同样基于Liblinear的L2lossSVM算法对测试样本进行分类识别。图1显示第一阶段分类器 $w$ 对PASCALVOC2007[17]测试样本的似物目标检测结果。从图中可知，BING 算法的准确率和灵敏度分别是 $7 3 . 6 7 \%$ 和 $100 \%$ ，但特异度只有 $0 . 0 0 0 1 \%$ 。这一实验结果说明所有测试样本均被判断为正样本。由此可以得出结论，BING算法中二值线性分类器 $w \in R ^ { 6 4 }$ 不具备识别样本的能力。

![](images/8eaf0cd1855583c354534aadd2b87498b1c19518e3bf41fb60bb216cd9e1dfd3.jpg)  
图1BING算法第一阶段的似物目标检测性能指标极限学习机[18\~20]（extreme learning machine，ELM）作为求

解单隐层前馈神经网络的算法，其隐藏输入节点权值随机初始化，输出权值根据 Moore-Penrose广义逆[21]方法计算得出。该算法执行过程中不需要调整网络的输入权值以及隐元的偏置，并且产生唯一最优解，因而学习速度快且泛化性能好，其运算速度高于SVM算法。ELM也同SVM算法一样，可以通过优化推导的方法得出与Moore-Penrose广义逆相同的输出权值。更重要的是，ELM算法中输入节点权值也可按照BING算法中的方法实现二值化。这为将BING 算法中的SVM 算法替换为ELM提供了可能。从算法实现原理角度分析，ELM隐层中由多个节点组成，样本需要与所有隐层节点做内积运算，其共同运算的结果即为算法输出值。若将BING算法中模板 $w$ 替换为一组模板 $w _ { 1 } , . . . , w _ { L }$ ，可明显提高对样本的识别能力。图1显示了将BING算法中第一阶段的SVM算替换为ELM方法后各项分类评价指标。图中改进算法的识别率是 $7 4 . 4 3 \%$ ，较原算法相比识别率提高了 $0 . 7 6 \%$ 。虽然灵敏度从指标上观察下降了$2 4 . 5 8 \%$ ，但特异度提高了 $54 . 3 5 \%$ 。特异度的大幅提升说明在BING算法中利用ELM代替SVM的方法可以提升对负样本的识别能力，大幅减少BING算法在第一阶段计算得到的候选窗□的数量。

# 1.2BING 的改进算法

为了更清楚地理解BING 算法的改进方法（improved BING,IBING)，本文首先对BING实现步骤做简要介绍。假设有 $N$ 个训练样本 $( x _ { i } , t _ { i } )$ ，其中 $x _ { i } = [ x _ { i 1 } , x _ { i 2 } , . . . , x _ { i n } ] ^ { T } \in R ^ { n }$ ，（204号 $t _ { i } = [ t _ { i 1 } , t _ { i 2 } , . . . , t _ { i m } ] ^ { T } \in R ^ { m }$ 。在单隐层前馈神经网络中可表示为

$$
H \eta = T
$$

其中： $\eta , \tau$ 和 $H$ 分别表示输出权值、期望输出和隐层输出矩阵。 $H$ 表示为

$$
H ( w _ { 1 } , . . . , w _ { L } , d _ { 1 } , . . . , d _ { L } , x _ { 1 } , . . . , x _ { N } ) = \left[ \begin{array} { c } { { H _ { 1 } } } \\ { { \vdots } } \\ { { H _ { N } } } \end{array} \right]
$$

$$
\begin{array} { r l r } {  { = [ \begin{array} { c c c } { G ( w _ { 1 } \cdot x _ { 1 } + d _ { 1 } ) } & { \cdots } & { G ( w _ { L } \cdot x _ { 1 } + d _ { L } ) } \\ { \vdots } & { \cdots } & { \vdots } \\ { G ( w _ { 1 } \cdot x _ { N } + d _ { 1 } ) } & { \cdots } & { G ( w _ { L } \cdot x _ { N } + d _ { L } ) } \end{array} ] _ { N \times L } } } \end{array}
$$

$\boldsymbol { w } _ { i } = [ w _ { i 1 } , w _ { i 2 } , . . . , w _ { i n } ] ^ { T }$ 和 $d _ { i }$ 分别表示第 $i ( i { = } 1 , \ldots , L )$ 个隐节点的输入权值和偏差， $G ( \bullet )$ 是激活函数。

在随机初始化 $w _ { i }$ 和 $d _ { i }$ 后，根据极小范数最小二乘解方法确定隐层输出矩阵

$$
\hat { \eta } = H ^ { \dagger } \boldsymbol { T } \mathrm { ~ , ~ }
$$

其中： $H ^ { \dag }$ 是矩阵 $H$ 的Moore-Penrose广义逆。由此计算得到ELM算法中输出权值 $\eta$ ，并利用式（1）判断样本类别。

在IBING算法中，将BING算法中SVM算法替换为ELM的关键问题就是如何实现 $w \cdot x$ 二值化。首先根据式（4）（5）对 $w$ 和 $x$ 做二值化处理

$$
w = \sum _ { j = 1 } ^ { N _ { b a s i s } } \beta _ { j } a _ { j } ,
$$

$$
x = \sum _ { j = 1 } ^ { N _ { b a s i s } } \alpha _ { j } b _ { j }
$$

其中： $\boldsymbol { N } _ { b a s i s }$ 是偏差向量的个数， ${ \alpha _ { j } , \beta _ { j } \in R }$ 是系数，$a _ { j } , b _ { j } \in \{ - 1 , 1 \} ^ { N _ { b a s i s } }$ 是偏差向量并且 $a _ { j } ^ { + } , b _ { j } ^ { + } \in \{ 0 , 1 \} ^ { N _ { b a s i s } }$ 满足条件

$$
a _ { j } = a _ { j } ^ { + } - \overline { { a _ { j } ^ { + } } } ,
$$

$$
b _ { j } = b _ { j } ^ { + } - \overline { { b _ { j } ^ { + } } } \circ
$$

则 $w$ 和 $x$ 的内积可表示为

$$
\begin{array} { r } { \langle \boldsymbol { w } , \boldsymbol { x } \rangle = \displaystyle \sum _ { i = 1 } ^ { N _ { b a s i s } } \beta _ { i } \langle a _ { i } , \sum _ { j = 1 } ^ { N _ { b a s i s } } \alpha _ { j } b _ { j } \rangle } \\ { = \displaystyle \sum _ { i = 1 } ^ { N _ { b a s i s } } \beta _ { i } \sum _ { j = 1 } ^ { N _ { b a s i s } } \alpha _ { j } \langle a _ { i } , b _ { j } \rangle } \end{array}
$$

其中:

$$
\begin{array} { r l } & { \langle a _ { i } , b _ { j } \rangle = \langle a _ { i } ^ { + } , b _ { j } \rangle - \langle \overline { { a _ { i } ^ { + } } } , b _ { j } \rangle } \\ & { \qquad = 2 ^ { 2 } \langle b _ { j } ^ { + } , a _ { i } ^ { + } \rangle - 2 ^ { 1 } [ \left| a _ { i } ^ { + } \right| + \left| b _ { j } ^ { + } \right| ] + 2 ^ { 6 } } \end{array}
$$

因此式（8）可表示为

$$
\langle w , x \rangle = \sum _ { i = 1 } ^ { N _ { a } } \beta _ { i } \sum _ { j = 1 } ^ { N _ { a } } \alpha _ { j } S _ { i j }
$$

其中： $S _ { i j } = [ 2 ^ { 2 } \langle b _ { j } ^ { + } , a _ { i } ^ { + } \rangle - 2 ^ { 1 } [ \left| a _ { i } ^ { + } \right| + \left| b _ { j } ^ { + } \right| ] + 2 ^ { 6 } ]$ 可通过二进制移位运算和或运算实现。由此，实现了BING 算法中SVM替换为ELM。

# 2 NDOG 特征描述子

HOG首先对灰度图像整体进行边缘检测，利用边缘算子计算各个像素点的梯度幅值和梯度方向，然后统计各个cel1内相同方向通道的梯度累计直方图，最后由多个cell构成一个block，block内所有cell的梯度直方图串联得到该block的HOG特征直方图。HOG 算法允许相邻block间的存在cell重叠以此提高数据关联性。按照Dalal在文献中提出的算法，在大小为 $6 4 \times$ 128 的滑动检测窗口中设定cell尺寸为 $8 \times 8$ 像素点组成,block由 $2 \times 2$ 块cell组成，block移动步长为8个像素单位构成的HOG描述子对图像中行人检测的漏检率是最低的。但HOG特征长度为3780维，每个cel1平均被统计4次，描述信息里有四分之三的数据是重复的，冗余信息量很大。且该算法没有利用各个cell之间的局部邻域关系。

针对上述问题，结合相邻样本具有线性相关性的特点[22]，提出了方向梯度邻域描述子（NDOG）方法。该算法不需要重叠block，仅将每个block与周围相邻的8个block的邻域关系通过权值向量表示，并将该向量串联到每个block方向直方图向量的尾部。

假设样本由 $m { \times } n$ （ $\scriptstyle \left( = N \right)$ 个 block 组成,block $b ^ { i } \in R ^ { 3 6 } ( i { = } 1 , \ldots ,$ $N )$ 根据HOG算法得出。计算 $b ^ { i }$ 与其相邻的8个block之间的权值系数 $\boldsymbol { W } ^ { i } = [ W _ { 1 } ^ { i } , W _ { 2 } ^ { i } , . . . , W _ { 8 } ^ { i } ]$ ，并保证重构代价误差最小：

$$
\varepsilon \left( W \right) = \sum _ { i = 1 } ^ { N } \left\| b ^ { i } - \sum _ { j = 1 } ^ { 8 } W _ { j } ^ { i } b _ { j } ^ { i } \right\| ^ { 2 }
$$

其中权值 $\boldsymbol { W } _ { j } ^ { i }$ 表示 $b ^ { i }$ 与第 $j$ 个相邻 block的相似度，式（11)满足约束条件 $\sum _ { j = 1 } ^ { 8 } W _ { j } ^ { i } = 1$ 。重构代价误差亦可写成

$$
\begin{array} { c } { \varepsilon \left( W ^ { i } \right) = \left\| b ^ { i } - \displaystyle \sum _ { j = 1 } ^ { 8 } W _ { j } ^ { i } b _ { j } ^ { i } \right\| ^ { 2 } } \\ { = \left\| \displaystyle \sum _ { j = 1 } ^ { 8 } W _ { j } ^ { i } b ^ { i } - \displaystyle \sum _ { j = 1 } ^ { 8 } W _ { j } ^ { i } b _ { j } ^ { i } \right\| ^ { 2 } } \end{array}
$$

定义 $B ^ { i } = [ b ^ { i } , b ^ { i } , . . . , b ^ { i } ] _ { 3 6 \times 8 }$ ， $\boldsymbol { N } ^ { i } = [ b _ { 1 } ^ { i } , b _ { 2 } ^ { i } , . . . , b _ { 8 } ^ { i } ] _ { 3 6 \times 8 }$ ，则

$$
\begin{array} { r l } & { \varepsilon \left( W ^ { i } \right) = \left\| B ^ { i } W ^ { i } - N ^ { i } W ^ { i } \right\| ^ { 2 } } \\ & { \quad \quad \quad = W ^ { i ^ { \prime } } \left( B ^ { i } - N ^ { i } \right) ^ { T } ( B ^ { i } - N ^ { i } ) W ^ { i } } \\ & { \quad \quad = W ^ { i ^ { \prime } } G ^ { i } W ^ { i } } \end{array}
$$

其中 $G _ { j m } ^ { i } = ( b ^ { i } - b _ { j } ^ { i } ) ^ { T } ( b ^ { i } - b _ { m } ^ { i } )$ 是对称半正定阵。根据拉格朗日乘子法在得到

$$
L ( W ^ { i } ) { = } W ^ { i ^ { T } } G ^ { i } W ^ { i } + \lambda ( W ^ { i ^ { T } } \vec { 1 } - 1 )
$$

计算式（14）中 $\boldsymbol { W } ^ { i }$ 的一阶偏导得

$$
\frac { \partial { \cal L } } { \partial W ^ { i } } = 2 G ^ { i } W ^ { i } + \lambda \vec { 1 } = 0
$$

$$
W ^ { i } = - \frac { \lambda } { 2 } ( G ^ { i } ) ^ { - 1 } \vec { 1 } = - \frac { \lambda } { 2 } \left[ \sum _ { m = 1 } ^ { 8 } ( G ^ { i } ) _ { \phantom { - } ~ \vdots } ^ { - 1 } \right] \circ
$$

根据条件 $\sum _ { j = 1 } ^ { 8 } W _ { j } ^ { i } = 1$ 计算得到每个 block 的邻域点权值向量

$$
W _ { j } ^ { i } = { \frac { \sum _ { m = 1 } ^ { 8 } \bigl ( G ^ { i } \bigr ) ^ { - 1 } { } _ { j m } } { \sum _ { p = 1 } ^ { 8 } \sum _ { q = 1 } ^ { 8 } \bigl ( G ^ { i } \bigr ) ^ { - 1 } { } _ { p q } } } \ _ { \rho }
$$

在实际计算时， $\boldsymbol { G } ^ { i }$ 有可能是奇异矩阵，需要做正则化处理：

$$
G ^ { i } = G ^ { i } + \alpha \cdot I _ { \mathrm { ~ \circ ~ } }
$$

其中 $\alpha$ 是正则化参数， $I$ 是 $8 { \times } 8$ 单位矩阵。

从式（18）可以看出相邻block见的欧几里得距离越近，其相似度越高，对应的权值越大。图2显示了相邻block的相似度和权值的关系。

HOG 算法原理是利用图像中目标和背景间梯度幅值的差异以及梯度方向的连续性建立目标特征。图3（b）显示了图3（a）中行人的HOG特征。从图3（b）中可以看出行人轮廓处的block方向具有连续性和一致性，但在HOG算法中没有量化block间的这一重要信息。

因此，本文提出的NDOG 算法的目标之一就是量化block间的相似性，图3（c）显示了图3（b）中block之间的相似性。为了让读者获得更直观的感受，将权值小于均值的 $\boldsymbol { W } _ { j } ^ { i }$ 设为0。如图所示，行人轮廓处的block相似性高于图像中的其他部分。鉴于block $b ^ { i }$ 与其权值向量 $\boldsymbol { W } _ { j } ^ { i }$ 一一对应，本文提出将权值向量串联到对应block的尾部，为保证对比标准化，需要对特征向量再使用二阶梯度范数做归一化处理，串联后组成的向量即为NDOG特征描述子。

![](images/d85d75c5d740c86cdd70980ea7b9533906a572e3bb5051ae84bba4a975dba105.jpg)  
图2HOG 算法中block与相邻8个block相似度和权值关系示意图

![](images/fa95e5f32a226d595598a7eae81ecce567cebcefca8e802ddff1e29a4506b2ec.jpg)  
图3行人特征描述示意图  
图6候选窗口数量对比图

# 3 本文算法

本文是在基于似物性目标检测框架的基础上实现快速行人识别。首先使用本文提出的IBING算法得到似物目标候选集，然后计算似物性目标的NDOG特征并利用SVM进行进一步识别，具体算法如图4所示。

![](images/8411a15453dac6f3945578b0c043c7a14ebd1658cb10ee32e5dc5463388e2ebe.jpg)  
图4本文提出的算法流程

# 4 实验过程和结果分析

本文中的实验平台为Intel(Core"i5-4590 CPU $@ 3 . 3 0$ GHz 3.30 GHz，RAM 8.00 GB，64 bit operating system,MATLABR2014b。为验证算法性能，本文使用INRIA和Caltech-USA[23.24]数据库作为实验用样本集。这两个数据库是行人识别邻域中公认的标准数据集，因此使用它们对提出算法进行性能分析和比较具有实际意义。此外，本文使用LIBSVM[14算法实现 SVM过程的训练和分类。

# 4.1候选窗口数量对比

选用INRIA数据库作为实验对象，分别使用滑动窗口、BING算法和IBING算法计算INRIA每个测试图像候选窗口的数量。如图所示，在每个INRIA的测试图像上使用滑动窗口的方法因为不对窗口内图像做任何识别操作，所以候选窗口数量最多，每幅测试图像产生的滑动窗口数量大约在1.2万\~2万个间。BING算法生成的候选窗口数量次之，但每个测试样本的候选窗□数量仍保持在1万个左右。导致这一现象的原因正是BING 算法在第一阶段将所有样本判断为正样本的结果。IBING算法在隐层包含多个匹配模板，故对样本的识别性能较BING算法有明显提升。在INRIA数据库的每个测试样本中得到的候选窗口数量只有0.15万个左右，远远低于前两种方法得到的窗口数量。有效降低了后续行人识别的计算量，节省结算时间。

2.5  
数 Sliding Window  
口标 BINGIBING0.5500 1000 1500 2000 2500 3000 3500 4000 4500 5000测试样本

# 4.2行人特征对比

NDOG是HOG的改进算法，其改进之处是在避免产生特征冗余信息。在文献[1]中，若定义滑动窗口的大小为 $M \times N$ 个像素点组成，block 由 $m \times m$ 个像素点组成，cell 由 $n \times n$ 个像素点构成，Block在滑动窗口中移动步长为 $k$ 个像素单位（ $m$ 能被$k$ 整除)，在一个ce11内的像素点梯度方向分为 $i$ 个梯度方向，则在滑动窗口中HOG描述子的长度$= [ ( M / k - 1 ) \times ( N / k - 1 ) ] \times ( m ^ { 2 } / n ^ { 2 } ) \times i$ 。当 $M = 6 4$ ， $N = 1 2 8$ ，$m = 1 6$ ， $n = 8$ ， $k = 8$ ， $i = 9$ 时，H0G描述子的长度是3780维。NDOG 算法在计算特征描述子时不需要重叠block，只需要计算cel1邻接点权值向量，并将向量（该向量的特征长度为8）添加到该ce11梯度直方图向量的尾部即可。因此，NDOG描述子的长度 $\mathrm { \xi = ( M / n ) \times ( N / n ) \times ( i + 8 ) = ( 6 4 / 8 ) \times ( 1 2 8 / 8 ) \times ( 9 + 8 ) = 2 1 7 6 }$ 与HOG特征相比，NDOG特征向量长度明显缩短，不包含冗余信息，对行人特征的表示能力优于HOG（图3所示）。

# 4.3行人识别评价指标对比

实验对比了 $_ \mathrm { H O G + S V M }$ ， $\mathrm { I B I N G + H O G + S V M }$ 和本文提出的 $\mathrm { I B I N G + N D O G + S V M }$ 算法在INRIA 和Caltech-USA 两种数据集的识别性能，评价指标本文采用MR-FPPI（MissRate-FalsePositivePerImage）曲线[1]。实验结果如图7所示，IBING $+ { \bf \sigma }$ HOG+SVM的误检数量较原算法有明显降低，但漏检率也略有升高。这是因为IBING算法将正负样本的分界面向正样本方向移动，造成了在提高了负样本的检测能力的同时也将少量正样本划分到负样本集内。但是，使用本文提出的算法识别图像中的行人，MR-FPPI性能要优于原算法和IBING+HOG+SVM算法。这是由于对候选窗口使用NDOG描述子提高了行人特征的表征能力，为SVM提供更加有效的样本以供训练和识别。

为了量化上述对比图的信息，表1显示了原算法和改进算法在INRIA数据库的具体的平均漏检率和识别速度。其中平均漏检率与图7（a）表现一致，较原算法相比提高了 $43 \%$ ，并且

识别速度提高了4倍。

![](images/aabb85003d3fd98a113f7d7ec3d6c8b4116ee2757d9de009f48a612797195fc0.jpg)  
图7实验测试结果对比图

表1算法识别率和检测时间对比  

<html><body><table><tr><td>算法名称</td><td>识别率</td><td>平均检测时间 (秒)</td></tr><tr><td>HOG+SVM</td><td>70.35%</td><td>1.63</td></tr><tr><td>IBING+HOG+SVM</td><td>70.48%</td><td>0.28</td></tr><tr><td>文本算法</td><td>75.34%</td><td>0.46</td></tr></table></body></html>

# 5 结束语

在围绕如何实现快速行人检测这一问题时，本文提出使用似物目标检测算法选取候选目标再判断类别的方法达到快速识别行人的目的。通过对BING算法的改进，有效降低了候选窗□的数量，为实现后续快速行人识别工作提供了基础。本文提出的NDOG方法通过引入邻域权值信息，克服了HOG 算法中信息冗余度高、特征表示不显著等问题。实验结果表明，本文提出的算法可大幅提升行人检测的实时性，并且识别性能有较明显的提高。下一步将研究如何结合视频时间信息，将同一行人的特征描述子建立时间坐标轴的描述信息，扩大本文方法在视频检测领域的应用范围。

# 参考文献：

[1]Dalal N,Triggs B.Histograms of oriented gradients for human detection [C]// Proc of IEEE Computer Society Conference on Computer Vision and Pattern Recognition.2005: 886-893.   
[2]Walk S,MajerN,SchindlerK,etc.New features and insights for pedestrian detection [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.2010:1030-1037.   
[3]Watanabe T, Ito S,Yokoi K.Co-occurrence histograms of oriented gradients for human detection [J]. IPSJ Trans on Computer Vision and Applications, 2010 (2): 39-47.   
[4]Felzenszwalb PF,GirshickRB,McAllesterD.Cascade object detection with deformable part models [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.Piscataway,NJ: IEEE Press,201o: 2241-8.   
[5] 刘琼，陈雯柏．基于视觉选择性注意与 IHOG-LBP 特征组合的行人目 标快速检测[J].计算机应用研究,2016,33(1):281-285.(Liu Qiong, Chen Wenbai. Fast pedestrian detection method based on combinatory features IHOG-LBP and visual selective attention computation [J]. Application Research of Computers,2016,33(1):281-285.

[6]曲永宇，刘清，郭建明，等．基于HOG 和颜色特征的行人检测[J].武 汉理工大学学报，2011,33(4):134-138.(Qu Yongyu,Liu Qing,Guo Jianming,et al. HOG and color based pedestrian detection [J]. Journal of Wuhan Universityof Technology,2011,33 (4):134-138.)

[7] 疏坤，蒋建国，齐美彬，等．基于改进的 HOG 与 Sobel-LBP 融合的快 速行人检测 [J].合肥工业大学学报：自然科学版,2017,40(7):898-903. (Shu Kun, Jiang Jianguo,Qi Meibin,et al.Fast pedestrian detectionbased on combinatory feature of improved HOG and Sobel-LBP[J]. Journal of Hefei University of Technology (Natural Science,2017,40(7): 898-903.)   
[8]AlexeB,DeselaersT,FerrariV.What isan object?[C]//Proc of IEEE Computer Society Conference on Computer Vision and Pattern Recognition. 2010: 73-80.   
[9]Hosang J,Benenson R,DollarP,etc.What makes for effective detection proposals?[J]. IEEE Trans on Pattern Analysis and Machine Intelligence, 2016,38 (4): 814-830.   
[10] Wolfe JM,Horowitz T S What attributes guide the deployment of visual atentionand how do theydoit?[J].NatRevNeurosci,2004,5(6):495-501   
[11] ChengMM,Zhang Z,LinWY,etal. BING: binarized normed gradients for objectness estimationat 300fps[C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition. 2014: 3286-393.   
[12] Zitnick CL, Dollr P.Edge Boxes: locating object proposals from edges [Cl//Proc ofthe 13th European Conference on Computer Vision. 2014: 391- 405.   
[13] Qi Y, Song Y Z, Xiang T, et al. Making better use of edges via perceptual grouping [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. 2015: 1856-1865.   
[14] Chang C C,Lin C J. LIBSVM: a library for support vector machines [J]. ACMTranson Intelligent Systemsand Technology,2011,2(3):articleNo 27.   
[15] Zhao Q,Liu Z,Yin B.Cracking BING and beyond [C]//Proc of British Machine Vision Conference. 2014.   
[16] Fan RE,Chang K W, Hsieh CJ,et al. LIBLINEAR: a library for large linear clasification [J]. Journal of Machine Learning Research,2oo8,9(6):1871- 1874.   
[17]EveringhamM,VanGoolL,WilliamsCKI,etal.The pascalvisual object classes (VOC) challenge [J]. International Journal ofComputer Vision,2010, 88 (2): 303-338.   
[18]Huang G B,Zhu QY, Siew C K.Extreme learning machine: theory and applications [J]. Neurocomputing,2006,70(1): 489-501.   
[19] Huang G B. What are extreme learning machines?Filing the gap between frank rosenblatt’s dream and John von Neumann's puzzle [J].Cognitive Computation,2015,7(3):263-278.   
[20] Huang GB,Wang D H,Lan Y.Extreme learning machines: asurvey[J]. International Journal of Machine Learning and Cybernetics,2011,2 (2): 107-122.   
[21]Banerjee K S.Generalized inverse of matricesand its applications by C. Radhakrishna Rao,Sujit Kumar Mitra[J].Technometrics,1973,15(1):197   
[22]Roweis ST, Saul LK.Nonlinear dimensionality reduction by locally linear embedding [J]. Science,2000,290 (5500):2323-2326.   
[23]Dollar P,Wojek C,Schiele B,etc.Pedestrian detection: a benchmark [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition.

2009:304-311.

[24] Zhang S,Benenson R,Omran M,et al.How far are we from solving pedestrian detection?[C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.2016:1259-1267.