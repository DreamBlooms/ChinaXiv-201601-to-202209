# 技术方法

# 基于密集特征匹配的胸片肺野自动分割

佘广南，陈莹胤,钟丽明,阳维,冯前进南方医科大学生物医学工程学院，广东广州510515摘要：目的X线胸片中肺野的准确分割是胸片图像自动分析的必要步骤。本文采用局部特征的密集匹配和标号融合进行胸片肺野的自动分割。方法对于输入的待分割胸片，基于每个像素点提取密集SIFT描述子和图像块作为局部特征，采用密集匹配直接在整个参考图像特征集合中快速搜索近邻;密集匹配分为受限的随机初始化、近邻场传播和受限的随机搜索三步，并数次迭代后两步。利用匹配得到的近邻场，提取标号图像块并进行加权，权重为匹配的相似度，最后重组为肺野的概率图,经阈值化处理即可得到肺野的分割。结果 在公开的JSRT胸片图像数据集上进行测试,本文方法的Jaccard指标可达 $9 5 . 5 \%$ 。结论利用局部特征的密集匹配和标号融合能取得准确性高且稳定的胸片肺野分割效果，并且优于当前最好的胸片肺野分割方法。

关键词：局部特征；密集匹配；标号融合；肺野分割；胸片

# Automatic segmentation of lung fields in chest radiographs based on dense matching of local features

SHE Guangnan, CHEN Yingyin,ZHONGLiming, YANGWei,FENG Qianjin School of Biomedical Engineering,SouthernMedicalUniversity,Guangzhou 51o515,China

Abstract: Objective Acurate segmentationof lung fields inchest radiographs (CXR)is veryuseful for automatic analysis of CXR. In this work, we propose to use dense matching of local features and label fusion to automaticallysegment the lung fields in CXR. Methods For an input CXR,the dense Scale Invariant Feature Transform (SIFT) descriptors and raw image patcheswere extractedasthelocal features for each pixel.The nearestneighbors of the local features were then quickly searched by dense matching directly from the whole feature dataset of the reference images.The dense matchingincluded thre steps: limitedrandominitialization,propagationofnarestneghborfield,andlimtedandomearch,withiteatioof the lasttwo steps for several times.The label imagepatches for each pixel were extracted according to the nearest neighbor fieldandweightedbythematchngsimlarity.Finall,teweightedlabelpatches wererearrangedastelabelclassprobability image of the input $\operatorname { C X R } ,$ from which thresholds were obtained for segmentation of the lung fields. Results The Jaccard index of the proposed method reached $9 5 . 5 \%$ on the public JSRT dataset. Conclusion A high accuracy and robustness can be obtained by adopting dense matching of local features and label fusion to segment the lung fields in $\operatorname { C X R } ,$ and the result is better than that of current segmentation method.

Key words: local feature; dense matching; label fusion; lung segmentation; chest radiograph

X线胸片是目前临床上广泛使用的医学成像技术，对于肺部疾病的分析与诊断具有重要的临床意义。对胸片中肺野的准确分割是对疾病的分析与诊断的重要前提。目前，随着计算机辅助诊断的普及，已经有很多肺野自动分割算法被提出来了，分割准确度与速度也越来越高，但仍存在一些难点：锁骨和肋骨窗的强边界，容易导致局部极小值;极小的胸膈角难以准确分割等。

目前胸片肺野分割算法主要有基于规则的分割[]像素分类、活动形状模型等。基于规则的肺野分割，通常只得到较为粗糙的肺野轮廓，可用做活动形状模型等的初始解。基于像素分类的分割取决于分类器预测性能，一般难以准确定位肺野边界。形变模型2-3由于具有灵活的形变特性而广泛应用于医学图像分割4,但也存在一些不足：(1)对初始解敏感，易陷入局部极小值点；(2)对算法参数敏感，造成性能不稳定。

为实现准确、可靠的肺野分割，本文提出了一种基于图像特征密集匹配和标号融合的肺野分割方法。提取待分割胸片图像的局部特征，将像素点的局部特征与肺野已知的参考图像集中的局部特征进行匹配，确定特征在参考图像集中的最近邻，并由此将参考图像中的肺野标号信息通过标号融合迁移至待分割的胸片图像，以实现肺野的自动分割。

# 1 材料和方法

1.1 材料

实验数据采用公开的JSRT胸片图像数据集5，包括154幅肺结节图像和93幅无结节图像，其中每幅胸片均有专家手工勾画的肺野轮廓。JSRT数据集中胸片原始图像大小为 $2 0 4 8 \times 2 0 4 8$ ，像素大小 $0 . 1 7 5 \mathrm { m m }$ ，灰度深度为12比特。为了与文献结果比较和减少运算时间，原始胸片图像降采样为 $2 5 6 \times 2 5 6$ 大小进行实验和性能评价。本文中算法采用Matlab编程实现。

![](images/865a0a01b992ba02acaff263dd7b31c2e9001bec414565068219a9febe0599f0.jpg)  
图1本文方法基本流程 Fig.1 Flow chart of the proposed method.

# 1.2 方法

1.2.1方法的基本流程本文方法分为两部分实现：构建参考图像特征集合和通过密集特征匹配分割肺野。算法基本流程见图1。给定参考图像集合及其对应的分割标号图集合，参考图像特征集合构建过程如下： $\textcircled{1}$ 将所有参考图像进行灰度归一化处理； $\textcircled{2}$ 取所有图像中肺野外接矩形内的区域,将其长宽变换为固定之后叠加平均，形成模板图像T； $\textcircled{3}$ 将所有参考图像与模板图像T进行对齐，对参考图像标号图像作相应的空间变换，提取局部特征描述子并降维，得到参考图像特征集合以及对应的分割标号图像集合。

在构建参考图像特征几何完成后，对一给定的胸片图像I,对其进行分割的基本过程如下： $\textcircled{1}$ 对输入图像I进行灰度归一化处理； $\textcircled{2}$ 将图像I与模板图像T进行对齐； $\textcircled{3}$ 提取图像I的局部描述子并降维； $\textcircled{4}$ 进行K次密集局部特征匹配，得到K个近邻场； $\textcircled{5}$ 利用步骤4得到的近邻场和局部特征的相似性进行标号融合； $\textcircled{6}$ 将标号融合结果进行空间逆变换,使得标号融合结果与原始输入图像在空间上一致； $\textcircled{7}$ 将标号融合结果进行阈值化处理得到肺野分割结果，阈值可设为 $0 . 5 _ { \scriptscriptstyle \odot }$

1.2.2 灰度归一化和空间对齐为减小胸片之间对比度差异对特征匹配造成的影响，对胸片灰度进行归一化处理。设胸片灰度直方图中的最后一个和第一个峰值对应的灰度分别为 $p _ { m a x }$ 和 $p _ { m i n }$ ,归一化处理后的图像灰度为Pi=(pi-Pmin)/(pmax-Pmin),其中pi表示像素i的灰度值。

为了将特征匹配的搜索范围限制在较小区域内，需将胸片图像与模板进行空间对齐，使得对齐后的胸片中肺野位于大致相同的位置。本文采用仿射变换作为形变模型，通过最大化增强相关系数进行胸片与模板的对齐。1.2.3 图像块匹配图像块匹配是指对图像块在图像中搜索其最相似的图像块(最近邻),图像块与其近邻之间的位移关系由最近邻场表达。PatchMatch是一种高效的图像块匹配算法。由于图像的一致性，相邻的块与它们的最近邻可能具有同样的位移向量，因此PatchMatch算法可以将最近邻场传播到相邻的区域。PatchMatch算法分为三步：随机初始化、近邻场传播、随机搜索。随机初始化指的是对图像A中的每一个图像块都在图像$B$ 中随机地指定一个最近邻,得到初始最近邻场;近邻场传播可以把好的位移关系传到周围的区域，从而逐步优化最近邻场。以像素点 $p _ { ( \mathrm { i } , \mathrm { j } ) }$ 为例，设 $\cdot A _ { \mathrm { ( i , j ) } }$ 是图A中以像素点 $p _ { ( \mathrm { i } , \mathrm { j } ) }$ 为中心取的一个小块，当传播到点 $p _ { ( \mathrm { i } , \mathrm { j } ) }$ 时,设块$B _ { ( m , n ) }$ 是块 $\cdot A _ { \mathrm { ( i , j ) } }$ 的最近邻，且与 $A _ { \mathrm { ( i , j ) } }$ 相邻的块 $A _ { ( \mathrm { i - 1 , j } ) } \ A _ { ( \mathrm { i , j - l } ) }$ 都已经得到了更新的最近邻,分别设为 $B _ { ( s , t ) } \sqrt { B _ { ( x , y ) } }$ ，则 $B _ { ( s + 1 , t ) }$ $B _ { ( x , y + 1 ) }$ 有可能是 $\cdot A _ { \mathrm { ( i , j ) } }$ 的最近邻,分别计算 $\cdot A _ { ( \mathrm { i } , \mathrm { j } ) }$ 与 $B _ { ( m , n ) } \ L { B _ { ( s + 1 , t ) } }$ $B _ { ( x , y + 1 ) }$ 这三个块的欧式距离,其中距离最小的则作为 $\mathbf { A } _ { ( \mathrm { i } , \mathrm { j } ) }$ 传播后的最近邻,这里假设 $B _ { ( s + 1 , ~ t ) }$ 为 $A _ { \mathrm { ( i , j ) } }$ 传播后的最近邻;随机搜索指的是在以块 $B _ { ( s + 1 , t ) }$ 的中心像素点 $p _ { ( s + 1 , \ t ) }$ 为中心的搜索窗内随机选出一个块 $B _ { ( u , v ) }$ ,然后再从中择优选出一个作为 $A _ { \mathit { \Phi } _ { ( \mathrm { i } , \mathit { \Pi } _ { j } ) } }$ 的最近邻，搜索窗的大小依次为$W { = } m \times n \times \left( 1 / 4 \right) ^ { t - 1 } , r$ $m$ 和 $n$ 分别表示图像A的高、宽， $\mathbf { \Phi } _ { t }$ 是随机搜索次数，直到 $\mathrm { \Delta W = 1 }$ ;最后多次迭代近邻场传播和随机搜索的这两步，最近邻场会逐渐收敛。由于随机初始化后，图像A中至少有一个块得到了较好的最近邻的这种可能性很大，所以，经过多次迭代的传播和随机搜索,最后A中绝大部分的块都能找到合理的最近邻。

PatchMatch算法可以高效求解两图像间图像块的近邻场。但当参考图像数量较多时，逐一将输入图像与参考图像进行块匹配是不实际的。为了解决这一问题，Golland提出了优化的块匹配标号融合算法，用于解剖结构的分割。值得注意的是，块匹配算法的复杂度取决于图像A的大小而不是 $B$ ，优化的块匹配算法是从参考图像集中搜索K个近邻，而不是只从与图像A相似的图像 $B$ 中找一个近邻。标号融合的时候，每个近邻的标号的权重取决于匹配对之间的相似度，跟块匹配算法一样,不是只取中心像素点的标号，而是基于中心点取了一个块。另外，随机初始化和随机搜索都被限制于一个固定大小的搜索窗内。由于不用预先检索出相似图像B,这个优化算法效率更高，而且由于有搜索窗的限制，减小了误匹配率，实现了更高的准确率。

1.2.4 特征密集匹配与标号融合 对于胸片图像，由于图像采集条件和病人个体差异，不同胸片肺野灰度和对比度差异较大。直接通过图像块匹配和标号融合，难以得到可靠的分割结果。为了解决这个问题，本文采用原始图像块和密集尺度不变特征转换描述子(SIFT)作为图像的局部特征。原始像素块是一种具有较强区分能力的描述子，但对噪声和形变很敏感，为了平衡描述子的不变性和区分能力，原始图像块的尺寸不能过大。SIFT描述子在计算机视觉有着广泛的应用，具有很好的旋转不变性，通常用于描述局部区域的形状特征，对于图像的形变和对比度能够保证一定的不变性。本文中，原始图像块的大小取 $9 { \times } 9$ ,SIFT描述子的维度是128，局部特征的维数为 $2 0 9$ 。为了减小计算复杂度，采用了主成分分析"对特征向量进行了降维。本文中，局部特征的维数降为40，保持总方差的 $9 5 \%$ ○

特征匹配与块匹配不同，对于输入图像的每一局部特征，直接在所有参考图像的局部特征中搜索其对应的K个近邻。设共有N幅参考图像，参考图像大小为 $\mathrm { m } \times$ n,局部特征的维数为D，则参考图像特征集合可用大小为 $\mathrm { D } { \times } \mathrm { N } { \times } \mathrm { m } { \times } \mathrm { n }$ 的四阶张量表达，参考图像特征集合可通过离线方式提取并保存。特征匹配搜索近邻的步骤与PatchMatch算法相似，分3步进行迭代：受限随机初始化、近邻场传播、受限随机搜索，其中近邻场传播仅在图像平面内进行。

如图2所示，右边的大长方体表示特征向量集，圆点代表该点对应的特征，浅蓝色方框表示固定大小的搜索窗，t表示参考图像序号，范围是1到N。随机初始化时，输入图像特征在参考图像特征集合中随机指定一个近邻。比如图2所示，输入图像相邻点的近邻可以位于不同参考图像中。近邻场传播的方法与PatchMatch算法类似，仅在参考图像的图像平面内进行传播，即近邻场传播时，近邻场对应的参考图像序号保持不变。随机搜索时，对输人图像任一点随机选择参考图像序号，在以当前近邻为中心的搜索窗内随机选取一点，如果随机选取的特征比当前近邻与输人图像特征之间的距离小，则将随机选取的近邻作为更新后的近邻。特征之间距离采用欧式距离。

重复特征匹配过程K次，对于输入图像可以得到K个近邻场 $( n n f )$ ，记录了输入图像中像素点特征在参考图像特征集合中K个近邻的空间位置和参考图像序号信息。在标号融合过程中，本文采用基于图像块的标号融合方法[1I-13]。设标号图像中像素值为0或者1,其中1表示像素点为肺野。对于输入图像的任一像素点 $( x ,$ $y )$ ，在标号图像中取以其近邻为中心的小块(如 $5 { \times } 5$ 大小的图像块),并以点 $( x , y )$ 的特征 $\nu _ { ( x , y ) }$ 与其近邻的特征V(mf(x,y)的相似度作为标号块的权重,由K近邻加权得到的标号块为

$$
l _ { ( x , y ) } = \sum _ { i = 1 } ^ { K } w _ { i } l _ { i } ( n n f _ { ( i , ( x , y ) ) } ) / \sum _ { i = 1 } ^ { K } w _ { i }
$$

其中 $l _ { i } ( n n f _ { ( i , ( x , y ) ) } )$ 表示以点 $( x , y )$ 在第 $i$ 个近邻场nnfi对应的近邻 $\{ n n f _ { ( i , ( x , y ) ) }$ 为中心取的标号块,权重

$$
w _ { i } = \exp \left( \frac { - S S D \Big ( \nu _ { ( x , y ) } , \nu _ { ( n n f _ { ( i , ( x , y ) ) } ) } \Big ) } { \sigma } \right) , S S D ( \nu 1 , \nu 2 ) =
$$

$\sum _ { d = 1 } ^ { D } ( \nu 1 _ { d } - \nu 2 _ { d } ) ^ { 2 }$ 表示两个D维向量的欧式距离的平方,另外,s的取值要适中，过大则权重都约为1,过小则权重都约为0，实验中可取为待分割图像中所有像素点与其近邻的距离的均值。最后，将加权的标号块进行重排和叠加为输入图像对应的标号图，并进行归一化处理

为了得到与原始输入胸片空间位置对应的分割，还需将标号融合结果用模板匹配的空间变换进行逆变换。标号融合的结果可以看做肺野的概率图，对其进行阈值化或使用图割方法4进行处理即可得到肺野的分割。

![](images/e0e38a31290b0a822b6068c95e1f2ffbdd5f0d0d30e3a5187cafce49f46acd95.jpg)  
图2密集特征匹配示意图 Fig.2 General view of dense matching of local features.Left: Input Image,Right: Features Database of reference images.

# 2实验和结果

2.1 实验

实验中，将JSRT胸片数据集分为大小相同的两个子集，分别用作训练集和测试集。肺野分割性能指标包括Jaccard指标(JI)和平均边界距离(MBD)，Jaccard值越大、MBD值越小则表明分割的性能越好，其中：

$$
J a c c a r d { = } \frac { \left| { G T } \bigcap { S M } \right| } { \left| { G T } \bigcup { S M } \right| }
$$

$$
\frac { 1 } { 2 } \Bigg ( \frac { \displaystyle \sum _ { i } D ( g _ { i } , S M B ) } { \displaystyle N _ { g } } + \frac { \displaystyle \sum _ { j } D ( s _ { j } , G T B ) } { \displaystyle N _ { s } } \Bigg )
$$

这里GT、SM分别表示手动分割的和自动分割的标号图，1为肺野，0为背景，公式(2)计算的是这两个标号图的肺野区域的重叠率，重叠率越高表示分割效果越好；公式(3)计算的是GT、SM中肺野的边界GTB、SMB之间的欧式距离的平均值，当手动分割的肺野区域与自动分割的完全重叠，Jaccard值为1,MBD值为0,重叠率Jaccard越高时，MBD值越小，表示分割效果越好，

![](images/8f38b97be994d74fbe308b9bfce6867dcbdab500cc144ee6ef13c9fe277ed018.jpg)  
图3近邻数不同的标号融合结果 Fig.3Result of label fusion with different numbers of nearest neighbors.

$D ( g _ { i } , S M B ) = \operatorname* { m i n } _ { j } \left\| g _ { i } - s _ { j } \right\|$ 表示GTB上的任意点 $\boldsymbol { g _ { i } }$ 到SMB的最短距离， $N _ { g \setminus } N _ { s }$ 分别表示GTB、SMB上像素点的总个数。

# 2.2结果

响，c-d分别是近邻数K等于1、2、5、7、10时的分割结果。图4显示的是不同近邻数时标号融合后的结果，左中至右近邻数分别是1、5、10。可以看出近邻数增加时，分割得到的肺野轮廓更平滑、分割结果更准确。

![](images/80901f1a14fad00f5265687d5c2f6d8525bb96122757a496b07b210be6d04fc2.jpg)  
图3反映了特征匹配近邻数K对Jaccard指标的影  
图4近邻数K对分割结果的影响 Fig.4Effect of K (number of nearest neighbors) on segmentation results.

图5主要反映了密集匹配过程中迭代次数对分割性能的影响，横轴表示近邻数。图中可见Jaccard值在第二次迭代后明显提高，迭代次数大于3且近邻数大于6时，Jaccard值逐渐趋于稳定。由于迭代次数与近邻数越大，需要的运算时间会增加，平衡效率和分割性能，本文选取的迭代次数为3，近邻数为10。

图6反映的是权重系数s对Jaccard指标的影响。当s很小，比如0.1时，对Jaccard的影响较大，尤其是近邻数较小的时候；当s为所有像素点与其近邻的欧式距离的均值(即图中 $m e a n ( D i s t )$ ,约为9.5),和s等于10或

100时，Jaccard值几乎完全相等；所以，为省去计算s的时间，本文直接选取s为10。

图7是JSRT数据集中部分图像自动分割的结果与手工分割结果的对比。图中红线和绿线分别为手工勾画和本文方法得到的肺野轮廓;第1行是容易分割且效果很好的例子，第2行是较难分割且分割效果不太理想的例子。JI代表Jaccard指标。表1列出了本文方法和其他肺野分割方法在JSRT数据集上的分割性能，本文方法对应的Jaccard指标优于其他方法。表2列出了各算法用相应的编程语言实现时运行时间的比较

![](images/c291b84b93fc883d344691a83227c51ea28c963e45392016578615fd6e26d857.jpg)  
图5密集匹配迭代次数的影响 Fig.5 Effect of iterations of dense matching.

![](images/cd497d76d4249b360971c7625dd2d7058643659d4e9a9477890dac9417ba83e4.jpg)  
图6权重系数s的影响Fig.6 Effect of weight factor.

![](images/62af3978368ab4e063f615e69d5f58d9667c51d8aace296bb338f56cb888d9f5.jpg)  
图7JSRT数据集中的图像分割结果实例演示Fig.7 Instances of segmentation results from JSRT database.  
图8数字胸片自动分割实例 Fig.8 Instances of automatic segmentation in DR.

为了验证本文方法的有效性和推广能力，采用本文方法对两种不同X线DR设备上采集的数字化胸片进行自动分割。图8显示了DR胸片和自动分割肺野的轮廓(红线），可以看出分割结果合理，并且肺野轮廓定位准确。虽然JSRT数据集中的胸片都是通过扫描胶片获取的，但人工分割的结果通过本文方法仍可很好地迁移至DR胸片的分割，说明本文方法具有良好的推广能力。

00 山

# 3讨论

胸片中细小的胸膈角和受锁骨影响的肺肩区域的 准确分割比较困难，并且肋骨窗的强对比度会影响分割

结果的准确性。从实验结果看，本文方法在一定程度较好解决了这些问题。从图8中分割结果较差的图像来看，严重胀气的结肠或周围组织被错分为肺野区域，而

# 表1肺野分割算法性能比较

Tab.1 Comparison of performances of lung field segmentation algorithms   

<html><body><table><tr><td>Algorithms</td><td>Jaccard (%)</td><td>MBD (mm)</td></tr><tr><td>Proposed method with Graph-cut post-processing</td><td>95.5±1.6</td><td>1.39±0.57</td></tr><tr><td>Proposed method with threshold post-processing</td><td>95.4±1.6</td><td>1.41±0.58</td></tr><tr><td>Atlases with Non-rigid Registration[15]</td><td>95.4±1.5</td><td>1.31±0.32</td></tr><tr><td>Human observer[16]</td><td>94.6±1.8</td><td>1.64±0.69</td></tr><tr><td>Joint shape and appearance sparse learning[17]</td><td>94.6±1.9</td><td>1.67±0.76</td></tr><tr><td>ASM tuned[16]</td><td>92.7±3.2</td><td>2.30±1.03</td></tr></table></body></html>

表2肺野分割运行时间的比较 Tab.2 Comparison of execution time on lung fields segmentation   

<html><body><table><tr><td>Algorithms</td><td>Execution time</td><td>Programming language</td></tr><tr><td>Proposed method with Graph-cut post-processing</td><td>12-14 s</td><td>Matlab</td></tr><tr><td>Prophod pethpd witsing</td><td>11-13 s</td><td>Matlab</td></tr><tr><td>Atlases with Non-rigid Registration[15]</td><td>20-25 s</td><td>C++、Matlab</td></tr><tr><td>Human observer[16]</td><td>-</td><td>-</td></tr><tr><td>Joint shape and appearance sparse learning[17]</td><td>35.2 s</td><td>Matlab</td></tr><tr><td>ASM tuned[16]</td><td>1s</td><td>C++</td></tr></table></body></html>

由于大量液体存在而模糊的肺野区域被错分为非肺野，这些问题尚需进一步解决。

# 4结论

本文提出了一种采用图像特征密集匹配和标号融合的胸片肺野分割方法。与一般的两图像间块匹配方法不同，本文采用密集SIFT和原始图像块作为图像的局部特征，直接将输入图像特征与参考图像集合的特征进行匹配，避免了参考图像子集的选择问题，有效利用所有参考图像及其标号的信息。在JSRT胸片图像数据集上，本文方法得到了目前为止最高的分割精度。此外，实验结果还表明本文方法具有很好的推广能力。在进一步的工作中，我们将对特征匹配方法进行推广应用，如用于胸片中结节的自动检测和肋骨的抑制。

1998,5(4): 245-55.   
[2]Cootes TF,Gj E,Taylor CJ.Active appearance models[J].IEEE Trans Pattern Anal Mach Intell,1998,23(6): 681-5.   
[3]Van Ginneken B,Frangi AF,Staal J,et al.Active shape model segmentation with optimal features[J]. IEEE Trans Med Imaging, 2002,21(8): 924-33.   
[4] Xu T, Mandal M,Long R,et al. An edge-region force guided active shape approach for automatic lung field detection in chest radiographs[J]. Comput Med Imaging Graph,2012,36(6): 452-63.   
[5]Shiraishi J, Katsuragawa S, Ikezoe J,etal. Development of adigital image database for chest radiographs with and without a lung nodule:receiver operating characteristic analysis of radiologists' detection of pulmonary nodules[J].AJR Am J Roentgenol, 2000, 174(1): 71-4.   
[6] Evangelidis GD,Psarakis EZ. Parametric image alignment using enhanced correlation coefficient maximization [J].IEEE Trans Pattern Anal Mach Intell,2008,30(10):1858-65.   
[7]Barnes C,Shechtman E,Finkelstein A,et al.PatchMatch:A randomized correspondence algorithm for structural image editing [J].ACM Trans Graph,2009,28(3): 341-52.   
[8]Ta VT, Giraud R,Collns DL,et al. Optimized patchmatch for near real time and accurate label fusion [M].Med Image Comput Compu Assist,2014,17(pt3): 105-12.   
[9]Lowe DG. Object recognition from local scale-invariant features [C]//The Proceedingsof the Seventh IEEE International Conference on. IEEE,1999:1150-7.   
[10]Hervé A,Wiliams LJ.Principal component analysis [J].Wiley Interdiscip Rev Comput Stat,2010,2(4): 433-59.   
[11] Coupé P, Manjon JV,Fonov V,et al.Patch-based segmentation using expert priors: application to hippocampus and ventricle segmentation[J]. Neuroimage,2011,54(2): 940-54.   
[12]Rousseau F,Habas PA,Studholme C.A supervised patch-based approach for human brain labeling[J]. IEEE Trans Med Imaging, 2011,30(10): 1852-62.   
[13] Wu G,Wang Q, Zhang D,et al.A generative probability model of joint label fusion for multi-atlas based brain segmentation[J].Med Image Anal, 2014,18(6): 881-90.   
[14] Vicente S,Kolmogorov V,Rother C.Graph cut based image segmentation with connectivity priors [C]//2008 CVPR IEEE Conference.2008:1-8.   
[15] Candemir S,Jaeger S,Palaniappan K,et al. Lung segmentation in chest radiographs using anatomical atlases with nonrigid registration [J]. IEEE Trans Med Imaging,2014,33(2): 577-90.   
[16]Van Ginneken B,Stegmann MB,Loog M. Segmentation of anatomical structuresin chest radiographsusing supervised methods: a comparative study on a public database[J].Med Image Anal,2006,10(1): 19-40.   
[17] Shao Y,Gao Y,Guo Y,et al. Hierarchical lung field segmentation with joint shape and appearance sparse learning[J]. IEEE Trans Med Imaging,2014,33(9): 1761-80.

# 参考文献：

[1]Armato SG,Giger ML,Macmahon H. Automated lung segmentation in digitized posteroanterior chest radiographs[J].Acad Radiol,

(编辑：孙昌朋)