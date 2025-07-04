# 基于图推模型与智能寻优的野外道路导向技术

华夏1，王新晴1，马昭烨1，王东1,²，邵发明1(1．陆军工程大学，南京 210007;2．南部战区陆军第二工程科研设计所，昆明 650222)

摘要：为实现无人装备在野外环境下，对非结构化道路进行自动、普适和精准的识别与导向，提出了一种基于图推模型与智能寻优的野外场景道路导向算法。首先将图像分割为同质超像素块，对超像素块的多特征进行融合，构造训练集；改进传统拉普拉斯支持向量机算法，结合超像素块位置信息动态选取道路区域超像素种子块，训练超像素块的多类别分类回归器和相邻超像素的一致性回归器；结合两种回归器的回归值构造马尔科夫随机场的能量函数，再利用标准图割算法迭代求取最小化能量函数实现初始道路推理分割；结合道路初分割结果，依据人对道路的直观感知设定约束条件构造目标函数，利用差分免疫克隆进化算法智能寻优提取道路的导向线。在南京珠山采集的数据和 DARPAGrand Challnge 数据库上进行检测，并与经典算法的道路导向效果进行定性和定量比较，结果表明该算法在野外环境下对非结构化道路的导向线提取精度总体达 $91 . 7 9 \%$ 以上，相比于经典算法，检测精准度分别提升 $4 8 . 1 \%$ 和 $3 5 . 5 \%$ ，算法处理效率分别提升 $9 8 . 6 \%$ 和 $9 7 . 8 \%$ ，在检测的实时性与精准度问题上实现了平衡，具有较强的应用前景。

关键词：马尔可夫随机场；拉普拉斯支持向量机；差分免疫克隆进化；非结构化道路；超像素中图分类号：TP387 doi:10.3969/j.issn.1001-3695.2018.04.0332

# Field scene road guidance technology based on graph reasoning model and intelligent optimization

Hua Xia1,Wang Xinqing1, Ma Zhaoyel,Wang Dongl, ², Shao Famingl (1ColegeofieldEngieering,LAAryEngineeing University,Najingo,Chia;2econdInstituteofEein Research &Design,Southern Theatre Command,Kunming 650222,China)

Abstract:Inorder torealizeautomatic,universalandaccurate identificationand guidanceofunstructuredroads forunmanned equipment in the field environment,proposearoad guidancealgorithmfor field scenes based on graph reasoning modeland inteligentoptimization.Firstlysegmenting theimage into homogeneoussuperpixel blocks,and fusing multi-featuresof the superpixeblockstoconstructatrainingset.Improvingthetraditionallaplacesupportvectormachinealgorithm,combiningthe location informationofsuperpixel blocks,dynamicallyselecting superpixel seed blocks inroadareas,andtraining multi-class classifierregressors ofsuperpixel blocks andconsistency regressors ofadjacent superpixels; Combining theregressio values oftwo kinds ofregressors,constructing theenergyfunctionof Markovrandom fieldandthen using the standard graph cuting algorithmto iterativelyobtainthe minimized energy functiontorealize theinitialroadreasoning segmentation.Combining the initialsegmentationresultsofroads,theobjective function isconstructedaccordingtotheconstraints setbypeople's ntuitive perceptionofroads,andusingthedifferential immuneclonal evolutionalgorithmtointeligentlyoptimizeand extractthe guide lines ofroads.Thedatacollected in Zhushan,NanjingandDARPAgrandchallengedatabaseare tested,andcomparing the results qualitativelyand quantitativelywith thoseof classicalalgorithms.Theresults showthatthe extractionaccuracyof the guide line of unstructured roads by this algorithm in the field environment is over $91 . 7 9 \%$ ,compared with classical algorithms, the detection accuracy is increased by $4 8 . 1 \%$ and $3 5 . 5 \%$ respectively, and the processing efficiency of the algorithm is increased by $9 8 . 6 \ \%$ and $9 7 . 8 \ \%$ respectively, which balances the real-time performance and accuracy of detection and has a strong application prospect.

Key words:Markovrandom field;Laplace support vector machine;diferential immuneclone evolution；guidance line;

superpixel

# 0 引言

道路的导向线信息能够较好地标示道路的与走向，引导无人装备的前进[1]。现阶段大部分车载机器视觉系统对于高速公路或其他有道路标志线的结构化道路环境已经较好地完成了导向线提取，然而在一些特殊的如军事、救灾等应用领域中，无人车辆需要在没有车道线和标志牌的非结构化道路上行驶、作业。因此研究野外复杂环境下非结构化道路的导向线提取问题具有重要的现实意义和广阔的应用前景。

现阶段的道路检测的算法主要分为基于特征 $[ 1 ^ { \sim } 3 ]$ 、基于模型[4]、基于机器学习[5,6]三大类。文献[7]提出通过迭代的方式估计消失点与道路边缘来提取导向线。采用了改进的硬投票算法，用二倍角正弦函数对方向一致率(orientation consistencyratio,OCR)加权，采用循环迭代的方式更新消失点和边缘，提高了消失点估计精度和边缘检测精度。文献[8]提出采用纹理方向与消失点结合的方式提取导向线，克服采用单一特征的局限，而且对阴影、水渍及光照具有很强的抗干扰性，大大提高了导向线提取精度。但是对于边缘纹理不清晰或较弱的道路则存在较大检测误差。文献[9]提出了一个统一的端到端可训练性多任务网络（vanishing point guided network,VPGN)，联合处理由消失点引导的车道和道路标记检测和识别，具有较强的鲁棒性在城市道路下有较高的识别精度，但是对于训练集样本依赖过大，且在非结构化道路条件下效果并不理想。

针对以上算法的不足，提出了一种基于改进的MRF推理分割和进化算法寻优的野外复杂道路导向技术。首先，在超像素分割的基础上构建基于颜色、纹理、结构的融合特征，避免了少数特征引起的分类偏差，又涵盖了位置、形状等先验知识，增强了超像素块的区分能力和稳定性。然后，采用无监督的MRF推理技术进行野外复杂环境下的道路初分割，既考虑到超像素快的多特征融合信息，又兼顾了超像素块邻域类标一致性的先验知识，若某些疑似超像素块被道路内超像素块包围，更加倾向于分类成道路类；若是与道路整体区域分离，更加倾向于分类为非道路类，有助于提高算法的抗干扰能力和鲁棒性，更加符合工程实际情况。第三，在道路类聚类中心（超像素种子块）的选取上融合道路模型与车前最小左右转弯半径交叉覆盖范围内，必定为路的先验知识（参考下文）动态选取道路类超像素种子块，不仅提升了算法对野外“车走路变”的普适性，还有效避免了随机选取道路类超像素种子块可能引起的训练偏差和效率降低。第四，将统计学习理论与最优化方法与机器学习结合起来，提高识别算法的精度和运行效率。针对基于拉普拉斯支持向量机(Lap SVM)的半监督分类方法不能有效处理大规模图像分类的问题，提出了通过融合道路模型与先验知识动态预选取道路类超像素种子块样本进行监督训练的SVM分类方法，有效地提高了分类器的分类精度，降低了算法的时间和空间复杂度。最后，借助统计学习理论和最优化方法解决机器学习问题，提出了双直线估计道路边缘的行驶引导线提取技术。其基本思想是双直线反映道路的大致方向，并尽可能大地涵盖道路区域，符合人眼对道路的直观感知，可操作性强，出现的偏差较小。

# 1 超像素类标MRF推理场景分割

采用无监督超像素MRF推理类标技术进行野外复杂环境下的道路初分割。既考虑到超像素块的多特征融合信息，而且兼顾了超像素块领域类标一致性的先验知识，如某些疑似超像素块被道路内超像素块包围，更加倾向于分类成道路类；反之更加倾向于分类为非道路类。这种方法有助于降低道路区域孤立的树叶、阴影、水迹等干扰因素对分类结果产生的影响，更加符合工程实际情况。

# 1.1超像素块多特征融合

超像素将图像从像素级划分成区域级，将图像划分为同质的区域再进行分类可以提高图像分割的效率。采用SLIC(simplelineariterativecluster）算法进行超像素块分割。SLIC算法与传统超像素分割方法相比处理速度更快，占用内存更小，边缘吻合度更高，可以将图像划分为均匀的小块区域，邻域特征比较容易表达，且保留物体的边缘和轮廓等重要信息。

为了获得区分性较好的视觉特征，通过多种特征融合的方式来描述超像素块。结合野外非结构化道路场景图像特点，本文提取以下四类特征构成视觉特征集。

a）颜色特征。野外道路场景图像的颜色信息非常丰富，一般天空会呈现天蓝色、灰白色或者白色，道路则是褐色或者红褐色。只有垂直物的颜色变化比较大，但是绿色最为常见。Lab色彩模型是由亮度L和有关色彩的a、b三个要素组成，致力于感知均匀性，它的L分量密切匹配人类对亮度感知，对阴影和光照有较强的鲁棒性。所以本文在HSV（色调，饱和度，明度）和Lab这两种颜色空间下提取颜色统计特征。提取超像素在Lab颜色空间下两个颜色通道a、b的均值（mean）、方差（variance）、斜度（skewness），以及在HSV颜色空间下的色度直方图和饱和度直方图[3]。

b)纹理特征。野外非结构化道路场景的纹理信息体现出多、杂、乱的特点，传统统计、几何、模型等方法提取纹理特征不能取得很好的区分效果。局部二进制模式（localbinary patterns,LBP)对图像局部纹理特征具有卓越描绘能力，计算复杂度低，灰度尺度不变性，易于工程实现，纹元字典无须训练学习，可以非常灵活地适应计算机视觉领域。其中MRELBP(medianrobust extendedlocal binarypattern)方法可以捕获微观结构和宏观织构信息，具有计算复杂度低、特征维数较低、对高斯随机噪声、椒盐噪声、随机像素损毁和图像模糊等，具有高鲁棒性[12]。采用 MRELBP 法来提取超像素块的纹理特征，将获得的关联LBP特征谱统计直方图作为特征向量用于分类识别。

c）结构信息。结构信息具有很好的稳定性，不容易受外界环境的干扰，能够有效提高超像素块分类的鲁棒性和抗干扰能力。采用稠密方式提取尺度不变特征变换（scale-invariantfeaturetransform,SIFT）和方向梯度直方图（histogramoforientedgradient,HOG)。即先在超像素内计算每个像素的SIFT、HOG特征向量，再计算超像素块内所有SIFT、HOG向量的几何平均作为其特征向量[3]。

d)位置和形状特征。野外非结构化道路场景中超像素块的坐标和形状能够为超像素块分类提供很强的几何布局线索。

![](images/e70a8bb4acecff60ad5b74c15808c14841118d2a0f00a159f205800aedeaead1.jpg)  
图1SLIC超像素图像分块

由图1中结果可以看出，因为道路区域纹理、颜色等多种特征融合复杂，所以分割形成的超像素块形状并不均匀，与天空、水坑等特征均匀区域的均匀六边形超像素块对比明显。采用基于Hu 不变矩[13]的方法提取形状特征，即归一化的超像素不变矩和离心率值。

依据一定的模型和先验知识，针对非结构化道路识别问题，车辆在行驶过程中，在通道宽度内，当视觉系统安装固定且沿车辆轴向时，恒定视野区域始终为可靠的道路区域[14]。所以超像素块的位置信息同样具有较好的区分度，采用归一化的超像素块中心像素位置的方法提取超像素块位置特征[15]。

# 1.2道路类超像素种子块动态选取

针对非结构化道路识别问题，车辆在行驶过程中，在通道宽度内，当视觉系统安装固定且沿车辆轴向时，恒定视野区域始终为可靠的道路区域。在道路类聚类中心(超像素种子块)的选取上融合了车前最小左右转弯半径交叉覆盖范围内，必定为路的先验知识（参考下文)，既提升了对野外“车走路变”的自适应性，同时又避免了随机选取道路类超像素种子块可能引起的训练偏差和效率降低。图像道路区域示意图如图2所示。

![](images/8113f254913dd1c18518c5bbe4635347047ca85706ac95d2afe59fa50c353ff4.jpg)  
图2图像道路区域示意图

可以确定道路图像中，车前以略大于车宽的尺寸 $D$ 为底边长，高为 $l$ 的等腰三角形区域，为图像中道路类超像素种子块选取最佳区域。依据几何学知识可以求得高 $l$ 如式(1)所示。

$$
l = \sqrt { R ^ { 2 } - \Big ( \mathbf { r } + \mathop { \mathcal { D } } _ { 2 } \Big ) ^ { 2 } }
$$

其中： $D$ 为车宽对应图像中尺寸； $r$ 为汽车最小转弯半径对应

图像中尺寸； $R$ 为汽车最大转弯半径对应图像中尺寸。

# 1.3LapSVM超像素块回归器训练

超像素 $a _ { i }$ 的全部特征向量记为 $f _ { i }$ ，类标集合表示为$l _ { i } \in \left\{ 1 , 2 , 3 \right\}$ ，分别对应道路、垂直障碍和天空三种类别。由$f _ { i }$ 和 $l _ { i }$ 组成多类别回归器 $H _ { \mathfrak { r } }$ 的训练集 $S _ { \mathrm { 1 } }$ 如式（2）所示。

$$
S _ { 1 } { = } \{ f _ { i } , l _ { i } \}
$$

超像素块的领域信息能够辅助对该超像素的属性进行判别，因此训练了回归器用来估计相邻超像素类别的一致性[10]。一致性回归器采用两个超像素的差值进行训练[16]。超像素对的一致性标签表示为 $k _ { i } \in \left\{ - 1 , 1 \right\}$ ,这里的-1 和1分别表示相邻两个超像素不同和相同的分类结果。一致性回归器 $H _ { 2 }$ 的训练集 $S _ { 2 }$ 如式（3）所示。

$$
S _ { 2 } { = } \big \{ s ( f _ { i } , f _ { i } ^ { ' } ) , k _ { i } \big \}
$$

其中： $s ( f _ { i } , f _ { i } ^ { ' } )$ 表示相邻两个超像素的特征差。

拉普拉斯支持向量机(LapSVM)算法是一种基于流形正则的半监督分类算法，研究如何同时利用少量的有标志样本和大量的未标志样本进行训练和分类[2I]。通过引入样本流形正则项[21]，LapSVM算法的学习模型中将包含样本的固有几何结构信息。LapSVM加入了未标志样本的流形结构信息，并将这一信息以Laplacian 流形正则项的方式加入SVM。学习过程中充分考虑了样本间的局部几何结构，使蕴涵在样本中局部的鉴别信息得以体现，可以得到更加准确的分类结果。

样本集合 $S = \{ x _ { i } , i = 1 , \cdots , n \} , x _ { i }$ 代表第 $i$ 个样本, $n$ 表示样本的个数。集合 $L = \{ x _ { i } , i = 1 , \cdots , m \}$ 表示标志样本， $\mathbf { \nabla } m$ 表示标志样本的个数, $U = \{ x _ { i } , i = 1 , \cdots , u \}$ 表示无标志样本的集合， $u$ 表示未标志样本的个数。用 ${ \bf y } _ { i }$ 表示第i个样本所属类别，$y _ { i } \in \{ - 1 , 1 \}$ 。LapSVM模型定义为

$$
f ^ { ' } = \underset { f \in { \cal { H } } _ { k } } { m i n } \sum _ { i = 1 } ^ { m } m a x { ( 1 - \gamma _ { i } f ( x _ { i } ) , 0 ) + \gamma _ { _ A } \parallel f \parallel ^ { 2 } } _ { _ A } + \gamma _ { _ I } \parallel f \parallel ^ { 2 } _ { _ { I } }
$$

其中： $f = [ f \left( x _ { i } \right)$ ， $x _ { i } \in S ] ^ { T }$ ，在训练数据集合上应为 $\mathfrak { n }$ 维列向量。 $\| \cdot \| _ { \ A } ^ { 2 }$ 是在再生核希尔伯特空间(RKHS)中定义的环境范数(Ambient Norm)， $H _ { k }$ 是与核函数相关的 RKHS。参数 $\gamma _ { _ A }$ （204号是权重来控制 $\| f \| _ { A } ^ { 2 }$ 在 RKHS 中的复杂性； $\| f \| _ { I } ^ { 2 }$ 是流形正则项(intrinsicregularizer)，用来保持样本分布的内在流形结构，参数 $\gamma _ { _ { I } }$ 是低维流形中函数的权重，来控制内在几何结构函数的复杂性。通过计算拉格朗日乘子，得到分类器为

$$
f ^ { ' } = \sum _ { i = 1 } ^ { n } \alpha _ { i } ^ { ' } K ( x _ { i } , x )
$$

其中： $\alpha _ { i } ^ { \prime }$ 是拉格朗日乘子； $K$ 是核矩阵。求解拉格朗日乘子：

$$
\overset { \cdot } { a ^ { \prime } } = ( 2 \gamma _ { \overset { . } { A } } I + 2 \gamma _ { \overset { . } { I } } K L ) ^ { - 1 } J ^ { T } { } _ { \overset { . } { L } } Y \overset { . } { \beta ^ { \prime } }
$$

其中： $I$ 是单位矩阵； $L$ 是 Laplacian 矩阵； $Y \in R ^ { m \times m }$ 是由标志样本 $y _ { i }$ $i = 1 , \dots$ ， $\mathbf { \Sigma } _ { m }$ ，组成的对角矩阵。 $J _ { L } \in R ^ { m \times m }$ 是由标志样本与未标志样本形成的分块矩阵[I0]。 $\beta ^ { \prime }$ 是Lagrange 乘子，即

$$
\beta ^ { \prime } = \operatorname* { m a x } _ { \beta \in \boldsymbol { R } ^ { m } } \sum \beta _ { i } - \frac { 1 } { 2 } \beta ^ { T } Q \beta
$$

$$
Q = Y J _ { _ { L } } K \left( 2 \gamma _ { _ { A } } I + 2 \gamma _ { _ { I } } K L \right) ^ { - 1 } J _ { _ { L } } ^ { T } Y
$$

$$
s . t . \sum _ { i = 1 } ^ { m } \beta _ { i } y _ { i } = 0 ; 0 \leq \beta _ { i } \leq 1 , i = 1 , \cdots , m
$$

从上面的定义可以看出，LapSVM算法中涉及许多矩阵的运算和转换，当无标记样本很多时，需要很大的内存空间和很长的CPU占用时间，甚至引起内存溢出等问题。可以通过原始优化来加速训练过程，将LapSVM的模型式重新定义为

$$
\operatorname* { m i n } _ { \alpha \in \boldsymbol { R } ^ { n } , b \in \boldsymbol { R } } \left( \sum _ { i = 1 } ^ { m } \operatorname* { m a x } \left( 1 - y _ { i } \left( K _ { i } ^ { T } \alpha + b \right) , 0 \right) + \gamma _ { A } \alpha ^ { T } K \alpha \right) ^ { \frac { 1 } { 2 } }
$$

其中： $\boldsymbol { b }$ 为 SVM 定义中的阈值； $y _ { i }$ （204号 $\mathbf { \psi } , i = 1 , . . . , m$ 为标志样本；参数 $\gamma _ { _ A }$ 是权重； $K$ 是核矩阵； $\alpha$ 是拉格朗日乘子。

利用LapSVM算法进行分类，标志样本数量越少，则分类结果误差可能越大。本文通过上文动态选取道路区域标志样本，选取那些在确定道路区域里面或者附近的超像素块样本即可能属于道路区域的超像素块样本加入训练样本集，舍弃了离确定道路区域较远或在图像四角位置的无标记样本，使得参与训练的无标记样本提供更丰富的启发信息。

结合动态道路预选取样本的LapSVM超像素块分类算法，首先对全部无标记样本选取少量含启发信息更为丰富的 $\mathbf { \nabla } m$ 个无标记样本。假设有1个标记样本以及预选取 $\mathbf { \nabla } _ { m }$ 个无标记样本，以 $l + ~ m$ 个样本建立 $k$ 近邻图然后，在此图上构造目标函数 $f$ 来实现分类。

算法基本流程如下：

a）输入标志样本集合 $L = \{ x _ { i } , i = 1 , \cdots , m \}$ 和无标志样本的集合 $U = \{ x _ { i } , i = 1 , \cdots , u \}$ ：

b）从u个无标记样本中预选取含启发信息更为丰富的m个无标记样本；

c）利用高斯核函数，计算核矩Ki=K(xi,xj);

d）计算图 Laplacian 矩阵 $L = D - W$ ,D 是对角矩阵,$D _ { i i } = \sum _ { j = 1 } ^ { l + m } W _ { i j }$ ， $\mathbb { W }$ 是边权矩阵;

e）选取合适的权重γ，γ；f）计算 $a ^ { * } = ( 2 \gamma _ { _ { A } } I + 2 \gamma _ { _ { I } } K L ) ^ { - 1 } J ^ { _ T } { } _ { _ { L } } Y \beta ^ { * }$ g）输出分类函数f'=∑α'K(xi,x)。 $f ^ { ' } = \sum _ { i = 1 } ^ { n } \alpha _ { i } ^ { ' } K ( x _ { i } , x )$

通过对标志样本和无标志样本的超像素块特征向量进行训练学习，可以得到LapSVM分类器，即可用于对野外复杂非结构化道路图像进行道路区域检测与识别。通过训练学习得到多类别回归器 $H _ { 1 }$ 。在测试过程中，对于一个输入特征，多类回归器 $H _ { \mathfrak { r } }$ 的输出是1、2、3。其中隐含层节点数取为3，可以自动地动态选取道路区域超像素种子块作为道路聚类中心。

用一致性回归器 $H _ { 2 }$ 的回归值作为2个超像素块属于相同类别的隶属度。 $H _ { \sb 2 }$ 回归器的输出也是-1与1之间的连续值。

# 1.4超像素类标 MRF 推理分割

马尔可夫随机场（Markovrandomfields）模型相比其他方法的优势是：提供了一种简单方法来对先验知识建模，相比其他基于像素点，或基于局部的方法，它可以考虑到环境知识的影响，如果建立的图模型得当，进而可能获得更加符合人眼视觉的全局最优解[18]。当超像素分类完成之后，采用 MRF 推理的方法得到超像素的类标。对于一幅输入图像，假设 $A = \left\{ a _ { i } \right\}$ 是图像的超像素集合,对应的成对MRF能量函数如式（11）所示。

$$
E ( l ) = \sum _ { a _ { i } \in A } U _ { i } ( l _ { i } ) + \alpha \sum _ { ( a _ { i } , a _ { j } ) \in P } V _ { i j } ( l _ { i } , l _ { j } )
$$

其中： $i$ 和 $j$ 是超像素索引号； $l _ { i }$ 和 $l _ { j }$ 分别是超像素 $i$ 和 $j$ 的候选标签； $\alpha$ 是成对能量项的权值； $U _ { i }$ 和 $V _ { i j }$ 分别代表数据项和平滑项势能函数，由超像素的回归结果计算得到， $U _ { i }$ 表示分配类标 $l _ { i }$ 到像素块 $a _ { i }$ 的代价值，为 $a _ { i }$ 的类别回归值与类标值之间差的绝对值，如式（12）所示。

$$
U _ { i } ( l _ { i } ) = \left| H _ { 1 } ( f _ { i } ) - l _ { i } \right|
$$

超像素对 $\left\{ a _ { i } , a _ { j } \right\}$ 之间的成对势能 $V _ { i j }$ 是惩罚相邻超像素$a _ { i }$ 、 $a _ { j }$ 取不同类标的代价值。采用Potts 模型来表示成对的代价函数，如式（13）（14）所示。

$$
V _ { i , j } = \beta ( l _ { i } , l _ { j } ) T ( l _ { i } , l _ { j } )
$$

$$
T ( l _ { i } , l _ { j } ) = \left\{ { 1 , l _ { i } \neq l _ { j } } \atop { 0 , l _ { i } = l _ { j } } \right.
$$

其中： $\beta$ 是相邻超像素之间的权值，由类别一致性回归器的输出来计算，如式（15）所示。

$$
\beta ( l _ { i } , l _ { j } ) = 1 + H _ { 2 } ( f _ { i } , f _ { j } )
$$

图割算法(graphcuts)是优化离散方程的有力工具，本文参考文献通过最小化图割来最小化MRF能量函数从而完成对图像的场景分割[19,20]。

# 2 智能寻优道路导向线提取

通过道路分割能够获得复杂不规则的道路区域，如何引导车辆下一步的前进方向成为无人驾驶的又一关键问题。对不规则的道路边界基于纹理消失点的导向线估计误差较大，而基于道路模型的导向线估计边界在复杂野外环境下待拟合点选择困难，拟合偏差较大。双直线道路边界能够反映道路的大致方向，并尽可能大地涵盖道路区域，可操作性强，出现的偏差较小。

# 2.1非结构化道路双直线边界与导向线模型

大部分野外非结构化道路并不是直线，但通常曲率很小，假定非结构化道路的左、右两边界都是直线，这样就可以采用直线道路边界来对图像中的道路边界进行约束，如图3所示。这大大降低了运算的复杂度，提高了程序的运行效率。

![](images/bac1dbd01403e9532bc3a1d80c4d52df2959d6633d47fb5bb9a097ba3293e223.jpg)  
图3非结构化道路双直线边界及导向线模型

依据以上两条道路边缘判定准则，本文以图像的左下角顶点为整个坐标系的原点 $^ { \mathrm { ~ \small ~ O ~ } }$ ，直线 $l _ { 1 }$ 函数方程如式（16）作为道路的左边缘。

$$
y _ { 1 } = k _ { 1 } \times x + b _ { 1 }
$$

道路的右边缘取为直线 $l _ { 2 }$ ，函数方程如式（17）所示。

$$
y _ { 2 } = k _ { 2 } \times x + b _ { 2 }
$$

图片的尺寸为 $\mathfrak { m } { * } \mathfrak { n }$ ．由方程组式（18）

$$
\left\{ \begin{array} { l l } { y _ { 3 } = k _ { 1 } \times x _ { 3 } + b _ { 1 } ; } \\ { y _ { 3 } = k _ { 2 } \times x _ { 3 } + b _ { 2 } ; } \\ { 0 = k _ { 1 } \times x _ { 1 } + b _ { 1 } ; } \\ { 0 = k _ { 2 } \times x _ { 2 } + b _ { 1 } ; } \\ { y _ { 1 } = b _ { 1 } ; } \\ { y _ { 2 } = b _ { 2 } ; } \end{array} \right.
$$

可求解得到 $l _ { 1 }$ 与 $\mathrm { ~ x ~ }$ 轴交点 $\operatorname { c } \left( X _ { 1 } , 0 \right)$ ，与y轴交点B$\left( 0 , Y _ { 1 } \right) :$

$$
\left\{ { \begin{array} { l } { \displaystyle X _ { 1 } = \frac { - b _ { 1 } } { k _ { 1 } } } \\ { \displaystyle Y _ { 1 } = b _ { 1 } } \end{array} } \right.
$$

$l _ { 2 }$ 与 $\mathrm { ~ x ~ }$ 轴交点 $\mathsf { D } \big ( X _ { 2 } , 0 \big )$ ，与 $\mathrm { \Delta y }$ 轴交点 $\mathrm { { A } } { \left( \mathrm { 0 } , Y _ { 2 } \right) }$

$$
\left\{ \begin{array} { l l } { \displaystyle X _ { 2 } = \frac { - b _ { 2 } } { k _ { 2 } } } \\ { \displaystyle Y _ { 2 } = b _ { 2 } } \end{array} \right.
$$

$l _ { 1 }$ 与 $l _ { 2 }$ 交点 $\operatorname { E } { \big ( } X _ { 3 } , Y _ { 3 } { \big ) }$ 作为非结构化道路的消失点：

$$
\left\{ \begin{array} { l l } { \displaystyle X _ { 3 } = \frac { b _ { 2 } - b _ { 1 } } { k _ { 1 } - k _ { 2 } } } \\ { \displaystyle Y _ { 3 } = ( \frac { b _ { 2 } - b _ { 1 } } { k _ { 1 } - k _ { 2 } } ) \times k _ { 1 } + b _ { 1 } } \end{array} \right.
$$

依据先验知识假定车辆当前所处位置为 $\mathrm { ~ F ~ }$ 点 $\left( \% , 0 \right)$ ，由E、F点则可以求得道路的导向线 $l _ { 3 }$ ，由点斜公式可以求得 $l _ { 3 }$ 的方程，如式（22）所示。

$$
\left\{ \begin{array} { l l } { \displaystyle k _ { 3 } = \frac { Y _ { 3 } } { X _ { 3 } - \nu _ { / 2 } } = \frac { b _ { 2 } \bullet k _ { 1 } - b _ { 1 } \bullet k _ { 2 } } { b _ { 2 } - b _ { 1 } - \nu _ { / 2 } ^ { n } \bullet ( k _ { 1 } - k _ { 2 } ) } } \\ { \displaystyle b _ { 3 } = - k _ { 3 } \bullet \nu _ { / 2 } = \frac { n ( b _ { 2 } \bullet k _ { 1 } - b _ { 1 } \bullet k _ { 2 } ) } { 2 b _ { 2 } - 2 b _ { 1 } - n \bullet ( k _ { 1 } - k _ { 2 } ) } } \\ { \displaystyle y _ { 3 } = k _ { 3 } \times x + b _ { 3 } } \end{array} \right.
$$

车辆继续前进需调整角度为／，如式（23）所示。

$$
\gamma = \left\{ \begin{array} { l } { \tan \left( k _ { \mathrm { 3 } } \right) - \displaystyle { \pi } \bigg / _ { 2 } \ , k _ { \mathrm { 3 } } < 0 } \\ { \displaystyle { \pi } \bigg / _ { 2 } - \tan \left( k _ { \mathrm { 3 } } \right) \ , k _ { \mathrm { 3 } } > 0 } \end{array} \right.
$$

# 2.2有约束道路边界双直线估计目标函数构造

结合人眼对道路的直观感知和先验知识，通过整体估计的方式来进行道路边界双直线估计。

合理的道路边界双直线应该尽可能完整地包含道路区域，即边界所包含的道路部分占道路总区域的比例要尽可能大。同时，最优的道路边界包含的区域内，道路应该占有尽可能多的比例。由此构造了两个目标子函数：边界包含区域内道路部分所占比例 $\mu _ { \mathrm { 1 } }$ 、边界内道路占道路整体的比例 $\mu _ { 2 }$ 。依据构造的双直线模型可以得到双直线模型道路边界包含的区域面积为$s _ { 1 }$ ：

$$
s _ { \mathrm { 1 } } = ( \frac { b _ { 1 } } { k _ { 1 } } - \frac { b _ { 2 } } { k _ { 2 } } ) \times ( \frac { ( b _ { 2 } - b _ { 1 } ) \times k _ { 1 } } { k _ { 1 } - k _ { 2 } } + \mathrm { b } 1 ) / 2
$$

因为道路区域的面积一般是不规则图形，通过初分割可以获得道路边缘像素点的位置信息，转换到双直线模型坐标系中可以表示为坐标 $( x _ { i } , y _ { i } )$ ，使用牛顿积分求边界内不规则道路区域的面积 $\sigma$ 。

$\sigma = \int d \sigma = \sum _ { i = 1 } ^ { N } d \sigma ~ , ~ \sharp$ 以 $\mu _ { \mathrm { { i } } }$ ：

$$
\mu _ { 1 } = \frac { \sigma } { s _ { 1 } }
$$

初分割出来整体的道路区域面积 $s _ { 2 }$ ：

$$
s _ { 2 } = \sum _ { i = 1 } ^ { N } \Bigl | x _ { i + 1 } - x _ { i } \Bigr | \times y , y = \mathrm { m i n } ( y _ { i } , y _ { i + 1 } )
$$

$$
\mu _ { 2 } = \frac { \sigma } { s _ { 2 } }
$$

本文通过将 $\mu _ { \mathrm { 1 } }$ 和 $\mu _ { 2 }$ 线性加权的形式构造DICCA 算法的目标函数F，如式（28）所示。

$$
F = \frac { 1 } { \lambda _ { 1 } \times \mu _ { 1 } + \lambda _ { 2 } \times \mu _ { 2 } }
$$

其中： $\lambda _ { 1 }$ 、 $\lambda _ { 2 }$ 分别代表约束条件子函数 $\mu _ { \mathrm { 1 } }$ 和 $\mu _ { 2 }$ 对总体最优化目标函数的指标权重。

所求得的最优化目标函数F的极小值对应的道路边界即是最优检测结果。

由非结构化道路的双直线模型结合先验知识，可以得到最优化目标函数的约束边界条件：

a）为提高运行效率，加快收敛速度，假设道路消失点即两边界交点在图像内部：

$$
\left\{ \begin{array} { l l } { \displaystyle \frac { b _ { 2 } - b _ { 1 } } { k _ { 1 } - k _ { 2 } } \in \left( 0 , n \right) } \\ { \displaystyle ( \frac { b _ { 2 } - b _ { 1 } } { k _ { 1 } - k _ { 2 } } ) * k _ { 1 } + b _ { 1 } \in ( 0 , m ) } \end{array} \right.
$$

b）取两边界直线与 $\textbf { x }$ 轴夹角 $\alpha \in \left( 1 0 ^ { \circ } , 1 7 0 ^ { \circ } \right)$ （20$\beta \in \left( 1 0 ^ { \circ } , 1 7 0 ^ { \circ } \right)$ ，取值间隔 $\Delta \theta = 5 ^ { \circ }$ ，则两直线斜率：

$$
\left\{ k _ { 1 } \in ( \tan ( 1 0 ^ { \circ } ) , \tan ( 1 7 0 ^ { \circ } ) ) \right.
$$

# 2.3群智能边界寻优估计

差分免疫克隆算法（differential immune clone clusteringalgorithm,DICCA）主要是基于差分进化及免疫克隆，通过克隆繁殖、差分变异、交叉及克隆选择操作来进化种群，在进化过程中加入局部搜索机制来提高算法的收敛性。DICCA普适性好，不易陷入局部极值，有较好的全局收敛性和鲁棒性,非常适合求解各种数值最优化问题。先合理构造约束条件和目标函数，由约束边界条件和最优化目标函数通过DICCA迭代优化的方式，即可求得最优化道路边界的参数 $k _ { 1 } \cdot \ b _ { 1 } \cdot \ k _ { 2 }$ 、 $b _ { 2 }$ 。DICCA 算法首先需要初始化参数，具体有种群规模为30、交叉概率为0.85、变异概率为0.05、最大迭代次数为100。算法的操作算子有差分变异、差分交叉、克隆增殖、均匀变异、克隆选择[22]五个。

经过克隆选择操作,得到下一代种群。算法的终止条件是：在种群迭代的过程中，当达到算法最大迭代次数，或者连续4代的适应度值都小于最小迭代的精度时，算法停止迭代，输出最终聚类结果，算法终止。整个DICCA算法具体流程如图4所示,全文算法流程如图5所示。

![](images/7f0a650cd0b30becb5421842524618ce23e2c50f2c080f2adcd5cdfc81e54a47.jpg)  
图4DICCA迭代寻优算法流程

![](images/1942f311b531b89c547015a9b33e1350a1f994b28b567abb91c290feed22e718.jpg)  
图5本文算法流程  
图6样本数据

# 3 实验结果与分析

为了验证本文算法对野外复杂场景下非结构化道路边缘检测的有效性和导向线提取的准确性。实验测试了多种典型复杂非结构化道路，并与文献[7]中的算法以及文献[8]和文献[9]中的算法进行识别效果比较，比较算法代码均来源于网络开源资源。对实验结果采用定性和定量的评价方法进行分析。

# 3.1实验设计和数据库

实验以四核Inteli7处理器， $8 . 0 ~ \mathrm { G B }$ 内存PC 机为硬件平台，在Windows7操作系统下以MATLABR2014a作为开发工具。实验所用非结构化道路图像数据取自于DGC（DARPAgrand challenge）场景分割数据库和在南京珠山采集的非结构化道路数据库，以及互联网上经过筛选得到的典型复杂非结构化道路图像，将所有实验图像进行尺寸归一化为 $6 4 0 ^ { * } 4 8 0$ 像素。

# 3.2实验结果评价指标

为了能够对各种算法的道路边缘检测质量进行定量比较，本文采用文献[7]中的衡量标准，精准度 $\tau$ 来评价各算法道路区域分割精度的高低，τ越小检测精度越低，反之检测精度越高。

$$
\tau = \frac { B _ { \mathrm { t } } \cap B _ { o } } { B _ { t } \cup B _ { o } }
$$

其中： $B _ { t }$ 是人工标定的道路区域像素集； $B _ { o }$ 是算法检测出的道路区域像素集； $B _ { t } \cap B _ { o }$ 表示两者交集，即共同部分；$B _ { t } \cup B _ { o }$ 表示两者并集[23]。

同时，为了定量评价各算法的导向线提取精度，本文定义了导向精度 $\tau _ { 2 }$ ，如式（33）所示。

$$
\tau _ { 2 } = 1 0 0 \% - \frac { \left| k _ { 3 } - k _ { 3 } \right| } { \left| k \right| } , k = \operatorname* { m a x } ( \left| k _ { 3 } \right| , \left| k _ { 3 } \right| )
$$

其中： $k _ { 3 }$ 是人工标注的导向线斜率； $k _ { 3 } ^ { ^ { \prime } }$ 是算法提取出的导向线

斜率。为了使导向精度的结果更加符合人们的认知，对 $\tau _ { 2 }$ 进行数值变换转化为 $\tau _ { 3 }$ ，如式（34）所示。

$$
\tau _ { 3 } { = } 5 0 \% + \frac { \tau _ { 2 } } { 2 } \cdot 1 0 0 \%
$$

$\tau _ { 3 }$ 越大，导向线提取精度越高。

# 3.3 实验结果

指标权重的合理性直接影响着多属性评价结果的准确性。为了合理选定最优权值 $\lambda _ { 1 }$ 、 $\lambda _ { 2 }$ ，提高道路边缘检测精度。

为了降低运算复杂度，对 $\lambda _ { \mathrm { 1 } }$ 、 $\lambda _ { 2 }$ 进行数值约束。

$$
\left\{ \begin{array} { l l } { \lambda _ { 1 } \in \left( 0 , 1 \right) ; } \\ { \lambda _ { 2 } \in \left( 0 , 1 \right) ; } \\ { \lambda _ { 1 } + \lambda _ { 2 } = 1 ; } \end{array} \right.
$$

在数据库中随机抽取20幅图像，人工标定道路区域和道路边界直线，则由式容易求得 $\mu _ { \mathrm { { i } } }$ 和 $\mu _ { 2 }$ ，通过对 $\lambda _ { 1 }$ 在区间(0,1)以间隔0.001取值循环迭代， $\lambda _ { 2 } = 1 - \lambda _ { 1 }$ ，使得目标函数F取得极小值，记录下对应的 $\lambda _ { 1 }$ 、 $\lambda _ { 2 }$ 值进行权值样本的构造。

0.8   
0.7   
0.6   
0.5   
0.4   
0.3   
0.2   
0.1   
0.0   
5 6 7 8 9 1011121314151617181920   
Image Number

通过对 $\lambda _ { \mathrm { _ { l } } }$ 求均值的方式，获得了普适性较好的最优权值

$$
\left\{ \begin{array} { l l } { \lambda _ { 1 } = 0 . 6 4 5 } \\ { \lambda _ { 2 } = 0 . 3 5 5 ^ { \circ } } \end{array} \right.
$$

在实验中定性及定量地对比了本文和文献以及文献提出的非结构化道路边缘检测算法的检测性能，检测效果如图7、表$1 { \sim } 3$ 所示。

![](images/229565b1613e9c8016634336fef80a218260527c34732ea3808498aa25974933.jpg)  
图7各算法道路分割与导向结果

图7中第一列为原图和人工标注道路消失点，第二列为文献[8]算法检测效果，第三列为文献[7]算法检测效果图，第四列为文献[9]算法检测效果，第五列为本文算法检测效果。由于文献[7]和文献[8]都是基于像素纹理的消失点检测，依赖于对纹理特征的提取，当路面纹理较弱不清晰如图6中第4、10张图像，或者杂乱如图6中3、5、7、9 图像时检测效果较差；文献[10]在利用非结构化道路训练集进行训练后，对光照、纹理等干扰有较好的鲁棒性，但是对于形状不规则和场景混乱的非结构化道路识别效果较差，如图6中第5、8、9幅图像；本文基于经过初始分割得到的道路区域再进行道路边缘检测可以有效去除无关干扰，提高算法的运行效率，对道路边界检测的效果也明显要优于其他两种算法，能够有效克服强光、阴影、水迹、雨雪、雾天落叶等外部环境对道路边缘检测的干扰，能够有效检测非结构化道路边缘。但是对于某些形状不规则，有弯道的非结构化道路，本文算法的检测仍然存在着较大的局限性，如图6中第4、9、10、5图像。

为了降低随机性和偶然性对分割性能评估的影响，本文从数据库和互联网上选取了总共100张非结构化道路图像，利用各算法分别进行道路边缘检测和导向线提取，然后计算道路区域分割精度 $\boldsymbol { \tau }$ 和导向精度 $\tau _ { 3 }$ ，实验结果如表 $1 { \sim } 3$ 所示。

从表1可以看出，在道路区域分割精度上，本文算法比文献[7，8]分别高出 $2 8 . 1 \%$ 和 $45 . 1 \%$ ，略低于文献[9]的精度；由表

2 可以发现，在道路导向精度上，本文算法比文献[7，8]分别高出 $3 5 . 5 \%$ 和 $4 8 . 1 \%$ ，比文献[10]也要高出 $1 5 . 5 \%$ ；由表2可以发现，在算法实时性上，本文算法比文献[7，8]分别高出 $9 7 . 8 \%$ 和$9 8 . 6 \%$ ，基本能够实现道路的快速处理。

表1各算法道路区域分割精度t  

<html><body><table><tr><td>算法</td><td>τ均值 (100%)</td><td>τ最小值 (100%)</td><td>τ最大值(100%)</td></tr><tr><td>文献7</td><td>61.86081</td><td>47.70483</td><td>96.48042</td></tr><tr><td>文献8</td><td>54.70859</td><td>35.50663</td><td>95.71827</td></tr><tr><td>文献9</td><td>91.76281</td><td>81.50393</td><td>99.96012</td></tr><tr><td>本文算法</td><td>89.89081</td><td>81.90483</td><td>99.68967</td></tr></table></body></html>

表2各算法导向精度 $\texttt { T } _ { 3 }$   

<html><body><table><tr><td>算法</td><td>T均值(100%)</td><td>T最小值 (100%)</td><td>T最大值(100%)</td></tr><tr><td>文献7</td><td>56.26182</td><td>0.51423</td><td>96.32143</td></tr><tr><td>文献8</td><td>43.70859</td><td>0.32643</td><td>85.41937</td></tr><tr><td>文献9</td><td>76.28165</td><td>69.59314</td><td>98.33963</td></tr><tr><td>本文算法</td><td>91.79281</td><td>72.62583</td><td>99.79864</td></tr></table></body></html>

表3各算法单张图像平均处理时间  

<html><body><table><tr><td>算法</td><td>文献7</td><td>文献8</td><td>文献9</td><td>本文算法</td></tr><tr><td>运行时间</td><td></td><td></td><td></td><td></td></tr><tr><td>(S)</td><td>28.32643</td><td>43.70859</td><td>0.0352</td><td>0.61937</td></tr></table></body></html>

# 4 结束语

本文提出的基于图推模型与智能寻优的野外场景自适应道路导向算法。实验结果表明本文算法在野外复杂环境下对非结构化道路的道路区域分割精度总体达到 $89 . 9 \%$ ，导向精度总体达到了 $91 . 8 \%$ ，算法处理效率分别提升 $9 7 . 8 \%$ 和 $9 8 . 6 \%$ ，综合性能明显优于经典算法，在检测的实时性与精准度问题上实现了平衡，具有较高的道路检测精度和较好的实时性，对道路区域的判定和道路轮廓走向的估计更加符合人眼对道路的直观感知，能够实现对野外非结构化道路精准快速检测，具有极强的应用前景。但是采用的双直线道路边界估计模型较为简单对于弯道等形状复杂道路识别效果一般，且算法的实时性仍然有待提高。

# 参考文献：

[1]王晓栋，徐成，刘彦．一种实时鲁棒的非结构化道路检测算法[J].计 算机应用研究,2010,25(12):2763-2765.(Wang Xiaodong,Xu Cheng,Liu Yan.Real-time and robust method for unstructured roads detection [J]. Application Research of Computers,2010,25(7):2763-2759.)   
[2]郝运河，张浩峰，於敏杰，等．基于K-means 特征的复杂环境下道路识 别算法[J].计算机应用研究,2016,39(2):602-606.(Hao Yunhe,Zhang Haofeng,Yu Minjie,et al.Road recognition algorithm under complex environment based on K-means feature [J].Application Research of Computers.2016,39 (2):602-606.)

[3]邓燕子，卢朝阳，李静，等．采用多层图模型推理的道路场景分割算法 [J]．西安交通大学学报：自然科学版,2017,51(12):62-67.(Deng Yanzi, Lu Cnaoyang,LI Jing,et u. Koau scene segmenauon aigoriuun vaseu on multi-layer graph model reasoning[J]. Journal of Xi'an Jiaotong University: Natural Science Edition,2017,51 (12): 62-67.)

[4] 高嵩，张博峰，陈超波，等．一种基于双曲线模型的车道线检测算法 [J]．西安工业大学学报,2013,33(10):841-844.(Gao Song, Zhang Bofeng, Chen Chaobo,et al.A lane detection algorithm based on hyperbolic model [J]. Jourmalof Xi'an UniversityofTechnology,2013,33(10):841-844.)   
[5]王海，蔡英凤，贾允毅，等.基于深度卷积神经网络的场景自适应道路 分割算法 [J].电子与信息学报,2017,39(2):263-269.(Wang Hai,Cai Yingfeng,Jia Yunyi,et al. Scene adaptive road segmentation algorithm based on deep convolution neural network [J]. Journal of Electronics and Information,2017,39 (2): 263-269.)   
[6] 龚建伟，叶春兰，姜岩，等．多层感知器自监督在线学习非结构化道路 识别[J].北京理工大学学报,2014,34(3):261-266.(Gong Jianwei,Ye Chunlan,Jiang Yan,et al.Multilayer perceptron self-supervised online learning unstructured road identification [J]. Journal of Beijing Institute of Technology,2014,34 (3): 261-266. )   
[7] 刘鹏辉，李岁劳，何颖．基于消失点迭代重估的道路边缘检测[J]．电 子信息学报,2014,36(7):1619-1624.(Liu Penghui,Li Jiulao,He Ying. Road edge detection based on iteration re-evaluation of vanishing points [J]. Chinese Journal of Electronic Information,2014,36(7): 1619-1624.)   
[8]Moghadam P, Starzyk JA,Wijesoma W S.Fast vanishing-point detection in unstructured environments [J]. IEEE Trans on Image Processing,2012,21 (1): 425-430.   
[9]LeeS,KimyJ,YoonyJS,etal.VPGNet:vanishingpoint guided network for lane and road marking detection and recognition [J].arXiv preprint arXiv: 1710. 06288v1,2017.   
[10] Kong Hui,Audibert JY,Ponce J. Generalroaddetection fromasingle image [J]. IEEE Trans on Image Processing,2010,19(8): 2211-2220.   
[11] Kong Hui, Sarma SE,Tang Feng. Generalizing Laplacian ofGaussian filters for Vanishing-point detection [J].IEEE Trans on Intelligent Transportation Systems,2013,14 (1): 408-418.   
[12]LiuL,LaoSY,Fieguth PW,etal.Medianrobust extendedlocalbinarypattern for texture classification [J]. IEEE Trans on Image Processing,2016,25 (3): 1368-1381.   
[13]刁彦华，孟子钰，王晓君．基于Hu不变矩的图像形状特征提取研究[J] 网络安全技术与应用,2017(10): 46-47.(Yan Yanhua,Meng Ziyu,Wang Xiaojun. Image feature extraction based on Hu invariant Moments [J]. Network Security Technology and Application,2017 (10): 46-47.)   
[14]孟凡杰，王新晴，吕高旺，等．基于多特征准则改进区域生长的非结构

化道路识别[J].电脑知识与技术,2016,12(35):200-202.(Meng Fanjie,

Wang Xinqing,Lyu Gaowang,et al. Unstructured road recognition based on multi-feature criteria for improved regional growth [J]. Computer Knowledge and Technology,2016,12(35): 200-202.)   
[15] Costea AD,Nedevschi S.Fast trafic scene segmentation using multi-range features from multi-resolution filtered and spatial context channels $[ \mathrm { C } ] / \hbar$ Proc of IEEE Intelligent Vehicles Symposium Proceedings.Piscataway,NJ: IEEE Press,2016: 328-334.   
[16]周慧，张尤赛，龚淼．基于RBF 神经网络的医学图像分类算法研究 [J].电子设计工程,2017,25 (3):113-120.(Zhou Hui,Zhang Yousai, Gong Zheng. Research on medical image classification algorithm based on RBF neural network [J].Electronic Design Engineering,2017,25(3):113-120.)   
[17] Costea A D,Nedevschi S. Semantic channels for fast pedestrian detection [C]//Proc of IEEE Computer Society Conference on Computer Vision and Patern Recognition.PiscatawayNJ: IEEPress,2016: 2360-2368.   
[18]余淼，胡占义．高阶马尔可夫随机场及其在场景理解中的应用[J]．自 动化学报,2015,41（7):1213-1234.(Yu Miao,Hu Zhanyi.High-order Markov random field and its aplication in scene understanding[J.Acta Automatica Sinica,2015,41(7):1213-1234.)   
[19]李凯，冯全，张建华．棉花苗叶片复杂背景图像的联合分割算法[J]. 计算机辅助设计与图形学学报,2017,29(10):1871-1880.(Li Kai,Feng Quan，Zhang Jianhua.Joint segmentation algorithm for complex background images of cotton seedling leaves [J]. Journal of ComputerAided Design & Computer Graphics,2017,29(10):1871-1880.)   
[20]徐胜军，韩九强，赵亮，等．用于图像分割的局部区域能量最小化算法 [J].西安交通大学学报,2011,45(8):7-12.(Xu Shengjun,Han Jiuqiang, Zhao Liang,et al. Local area energy minimization algorithm for image segmentation[J]. Journal ofXi’an Jiaotong University,2011,45(8): 7-12.)   
[21]王晨，樊养余，熊磊．利用 LapSVM的快速显著性检测方法[J].中国 图像图形学报,2017,22(10):1392-1400.(Wang Chen,FanYangyu,Xiong Lei. Rapid saliency detection method using LapSVM[J].Journal ofImage and Graphics,2017,22(10): 1392-1400.)   
[22]马文萍，黄媛媛，李豪，等．基于粗糙集与差分免疫模糊聚类算法的图 像分割[J].软件学报,2014,25(1):2675-2689.(Ma Wenping,Huang Yuanyuan,Li Hao,et al. Image segmentation based on rough set and differential immune fuzzy clustering algorithm [J].Journal of Software, 2014,25 (1): 2675-2689.)   
[23]华夏，王新晴，俞垚魏，等．无人装备野外场景自适应道路识别技术 [J].兵器装备工程学报,2018,39(6):165-170.(Hua Xia,Wang Xinqing, Yu Yaowei,et al.Adaptive road identification technology for unmanned outdoor scenes [J]. Journal of Weapons and Equipment Engineering,2018, 39 (6): 165-170.)