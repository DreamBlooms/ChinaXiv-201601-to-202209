# 一种基于全天相机云图的云量测量指标

张雨昕1，邱波1，石超君1，李梦慈1，相冠杰1（1.河北工业大学，天津300401）

摘要：全天相机云图是天文界监测云量的重要手段，但没有确定的云量计算指标。因此本文提出了一种新的云量测量量化指标——云分布密度，并基于该指标建立全天相机云图自动分类系统。首先，对云图进行去噪，利用Otsu算法分割云区域；然后对去除背景的云区域图像使用本文提出的云分布密度计算云量；最后使用四种传统的分类器（支持向量机，K最近邻，决策树和随机森林）根据计算数值进行自动分类并评估各分类器的性能。结果表明，本文提出的云分布密度可作为评判全天相机云图云量的数值指标 ;基于云分布密度建立的云图自动分类系统实现了较高的识别准确率，其中随机森林法得到了最好的分类效果—各类云图的识别准确率均达到 $9 5 \%$ 以上。

关键字：云分布密度，全天相机云图，TMT，云量测量

中图分类号：P412.15

# 0引言

全天相机拍摄的云图是目前天文台判别地球大气条件的重要依据，是天文观测工作不可缺少的重要工具，特别是在天文台的选址工作中至关重要，而云量是全天相机云图反映的云的重要信息之一。云量指的是特定类型的云（部分云量）或全部类型的云（总云量）覆盖天空的估计比例，目前对于云量计算的研究大部分是基于云检测来实现的，一类是根据云点与总像元点之间的比值来计算云量。比如国际卫星测云气候学计划（ISCCP）根据像元辐射值与晴空辐射之间的关系，判断像元是云点还是非云点[2。阈值法根据天空与云的红蓝波段比值的不同，利用固定阈值3、全局自适应阈值4、局部阈值对云点进行判断。超高分辨率辐射仪第一阶段云量算法(CLAVR-1)错误!未找到引用源。将像元分为无云、混合和有云三类；中等分辨率成像光谱仪云量算法（MODIS）2将像元分为确定云、可能云、可能晴空、晴空四类。此外还有超高分辨率辐射仪拓展云量算法（CLAVR-X），高分辨率红外测深仪云量算法（HIRS）[方法等。但是它们都是将像元分为有限的几个类别，做一个定性的分析，这无疑是很粗糙的。此外还有基于特征的云检测分类算法的研究如随机森林、支持向量机、贝叶斯分类器[8]、K-means $+ + ^ { [ 9 ] }$ 、神经网络[10]等，主要基于颜色[11-14]或纹理特征[12]进行云区域分割。近年来深度学习也在云检测领域得到了广泛应用，比如一种基于深度残差全卷积网络[14]的云检测方法实现了对遥感影像云层目标像素级别的分割，像素精度达到了 $9 3 . 3 3 \%$ ；还有一种基于带权重的多尺度融合分割网络的遥感云图云检测方法°，其像素精度可达 $9 5 . 3 9 \%$ ：

某改进的全卷积神经网络实现了日间地基云图和夜间地基云图的云区域分割[15]，像素精度达到了 $9 4 . 5 9 \%$ 。另一类就是根据像元辐射量与反射率的比值来计算等效云量，但是其仅仅是对云覆盖面积的一个反应。

因此无论是云量还是等效云量，现阶段云量的研究仅仅关注于云层的覆盖面积而忽略了云的分布密集程度。

目前天文台的云量观测是使用30米口径望远镜（Thirty Meters Telescope,TMT）中用到的人工判读云图法：分别在天顶距 $4 4 . 7 ^ { \circ }$ 和 $6 5 ^ { \circ }$ 处画圆（在图1中用蓝色和绿色标注），将全天云量分为Clear（外圈以内无云）、Covered（外圈以内厚云覆盖超过 $5 0 \%$ ）、Inner（内圈有云）、Outer（内圈无云，外圈到内圈之间有云）四类。

![](images/4e7d9cd86124bf2b6945b2d3243899f0fb812ef6313ab9c5cc714023bf7ced04.jpg)  
图1全天相机云图区域划分 Fig.1. Division of ASI image region.

本质上来说，TMT方法主要是基于ASI图像中云区域的比例来测量云量，对云分布的密集程度考虑不够充分，并且没有直观可靠的定量指标。

针对上述问题，本文提出了一种新的云量测量指标——云分布密度（Cloud DistributionDensityof ASIImages，ASICDD），用于描述围绕云图中心点的全天云量的分布情况。本文的主要创新点有：（1）将云点与云图中心点之间的距离变量引入云量计算中，定义了云分布密度的计算模型；（2）重新定义云面积的计算模型，引入云层厚度变量；（3）提出了一种基于云分布密度和云面积的云图自动分类系统，使用四种传统分类算法（决策树，KNN，SVM 和随机森林）并选取1511张云图数据进行实验分析。结果表明，随机森林（RF）的分类结果是最好的，并且在各种类型中具有很高的识别精度。

本文使用的云图数据来源于中国科学院国家天文台光学天文学重点实验室，大小为$1 4 1 1 \times 1 4 1 1$ 像素。数据集中包含1511张全天相机云图，包括 295张Clear，696 张Covered,277 张 Inner 和 243 张 Outer。

# 1云分布密度的定义

# 1.1云分布密度计算模型

云分布密度的提出主要是为了说明云区域距云图中心的远近对天文观测结果的不同影响，距离中心越近，影响越大，反之则越小。云分布密度就是对这种影响进行量化表示。云分布密度有三个决定要素：面积、厚度和距云图中心点的距离。在归一化处理后的云区域灰度图的基础上，将云区域划分为 $N$ 个单位云区域 $x _ { i }$ $( i { = } 1 , 2 , . . . , N )$ ， $x _ { i }$ 的面积为 $s _ { i }$ ，平均云层厚度为 $w _ { i }$ ，云区域中心点距云图中心点的距离为 $d _ { i }$ ，一张ASI的云分布密度公式可如下表示：

$$
\mathrm { A S I C D D } = \sum _ { i = 1 } ^ { N } s _ { i } w _ { i } f ( d _ { i } )
$$

其中 $f$ 是以 $d _ { i }$ 为自变量的云区域的分布密度函数。由于设备和裁剪的问题，距离参数不是固定的，因此取相对距离 $\boldsymbol d _ { i } ^ { * } = \boldsymbol d _ { i } / R$ ，其中 $R$ 表示ASI有效区域半径。

云分布密度主要探究的是寻找合适的函数来表达云区域距云图中心点距离大小的影响。根据云分布密度的定义，相同面积大小的云区域距离中心点越近对观测影响越大，则定义式（1）中的距离分布函数 $f$ 是随 $d _ { i }$ 递减的函数，在云图中心点分布密度最大。由于本文对全天相机云图的分类是基于TMT的判断标准，则在参数设定上考虑内圈和外圈的影响。经过多次试验和与人工观测的结果对比研究，人为设定云图中心点处分布密度为1,内圈处为0.7，外圈处为0，经MATLAB曲线拟合工具箱线性拟合后 $f$ 如图2所示，公式表达如式（2），其中正弦项是为了修正拟合的二次函数，使其满足递减条件。

$$
f ( d _ { i } ^ { * } ) = - 2 4 . 3 3 \mathrm { s i n } ( d _ { i } ^ { * } - \pi ) + 1 . 2 2 8 ( d _ { i } ^ { * } - 1 0 ) ^ { 2 } - 1 2 1 . 8
$$

在实际运算中，本文以每个像素点为计算单位，可使ASICDD 测量精确到像素级别，则式（1）中 $x _ { i }$ 是云图像素点，面积 $s _ { i }$ 为1，由于云图中天空呈蓝色而云呈白色，且云层越厚云越白，即云层厚度与云点的灰度值呈正比，因此云层厚度 $w _ { i }$ 由灰度值 $V _ { i }$ 表示

$$
w _ { i } = V _ { i } / 2 5 5
$$

其中 $V _ { i }$ 的取值范围为0\~255。综合式（1）（2）（3）可得到基于像素的ASICDD计算模型

$$
\mathrm { A S I C D D } = \sum _ { i = 1 } ^ { N _ { c l o u d } } \frac { V _ { i } f ( d _ { i } / R ) } { 2 5 5 }
$$

其中， $V _ { i }$ 表示云图像素值， $d _ { i }$ 表示该像素点距云图中心点的距离， $N _ { c l o u d }$ 表示云点总数。计算结果进行归一化处理，使云分布密度值映射到O-100 之间。图3表示 Clear、Covered、Inner、Outer 四类云图的云分布密度的分布情况，可以看出各类云图有较明显的分界，说明云分布密度可作为基于云量的云图分类的标准。

![](images/b175fb1f4e927945f941c5a94a1b87b7438f7ef32d0b2878699ee4fe4dbd9e90.jpg)  
图3四类云图的云分布密度分布Fig.3ASICDD of four categories ofASI images.

![](images/a0871e7c9f4db9f3f772a4439aa6cf8db4b269595d3758db96a09c6f97e17705.jpg)  
图2距离分布函数 $f$ 与相对距离di\*的关系 Fig.2The relationship between distance distribution function $f$ and relative distance di\*.   
图4云图自动分类系统流程图

1.2云面积计算模型

目前国际上主要是针对卫星云图根据云检测得到的云像元，将云像元分为不同的种类，统计计算每种像元的概率，从而得到总云量，以此反映云层的覆盖面积。计算的方法主要有ISCCP、CLAVR-1、CLAVR-X、MODIS 等。本文在CLAVR-X的基础上，以云图每个像素点定义云面积的计算模型，所有云像素点的加权面积和与整个云图有效区域的面积比，作为代表云面积（Scloud）的指标。以云层厚度作为云点面积权重，即根据灰度值定义权重参数，灰度值 $V _ { i }$ 的取值范围为0\~255，将其线性划分为255个等级。云面积计算公式如式（5）所示，其中 $S _ { g l o b a l }$ 是云图有效区域面积，以像素为单位，本文中是 $S _ { g l o b a l } { = } 1 4 1 1 { \times } 1 4 1 1$ 像素。

$$
\mathrm { S c l o u d } = { \frac { \displaystyle \sum _ { i = 1 } ^ { N _ { c l o u d } } V _ { i } } { 2 5 5 S _ { g l o b a l } } }
$$

# 2基于云量计算的云图分类系统

国内已有关于云图自动分类的相关研究：文献[17]结合卫星云图的纹理特征和光谱特征采用 SVM算法实现卫星云图的自动分类；文献[18]提出一种针对全天相机云图的云量自动计算方法，并依据TMT判读全天相机云图的方法对云图进行自动分类。但这两种方法没有对全天相机云图的云量特征进行深入描述。本文以云分布密度和云面积来描述云图的云量特征，并结合机器学习算法构建基于云量计算的云图分类系统，图4是自动分类系统的流程框图。云图经去噪、分割出云区域图像后，在此基础上进行云量的数值计算，最后以云分布密度和云面积为特征的分类器对云图进行自动分类。

Cloud   
ASI Cloud region Denoising amount Classification   
images segmentation calculation

2.1 云图去噪

云图的固定噪声[19会影响云检测的准确度，进而影响云量计算和云图分类的结果。本文的系统主要针对严重影响云检测准确度的两种噪声——星光噪声和日、月光噪声进行云图去噪，可见图5(a) (b)。

# 2.2 云图分割

本文采用Otsu算法进行云区域检测，云区域标记为1，天空背景标记为0，得到二值图像，结果如图5(c)所示。在此基础上将二值图像与原图相乘可分割出云区域，然后将分割图进行灰度归一，消除云图之间的明暗差异，最终云图分割结果如图5(d)所示。

![](images/4c37bc290ffa5e00f2e234c2ffd932a01bde6619ab97dbc9f82f839882f187b6.jpg)  
Fig.4 Cloud map automatic classification system flowchart   
图5(a)原图(灰度图）；(b)去噪结果；(c)云区域检测；(d)云图分割 Fig.5 (a) Original image (grayscale image); (b) Denoising image; (c) Cloud area detection; (d) Cloud segmentation.

2.3云量计算

系统在云区域分割的基础上，计算每张云图的ASICDD和 Scloud，作为下一步云图分类的特征。表1显示了数据集

中部分云图的ASICDD和Scloud，图6展示了数据集中云图的两个指标之间的关系，图中离差（deviation）计算公式如式6所示。可以看出，ASICDD 和 Scloud在整体上呈正相关，经统计$7 6 . 4 4 \%$ 的云图数据的离差在0.1以内， $9 3 . 7 8 \%$ 的云图的离差在0.2以内。但在云较少（Scloud $< 0 . 3$ ）的情况下，二者并非严格的正相关，离差较大。出现Scloud较高但ASICDD 较低的情况，这在表1列举出的样例中也有体现。这正是由于云分布密度的计算模型中加入了云点和中心点的距离影响：云面积大但距中心点

表1 部分云图的云分布密度和云面积  
Table 1 ASICDD and Scloud value of some ASI images.   

<html><body><table><tr><td></td><td>ASICDD</td><td>Scloud</td><td></td><td>ASICDD</td><td>Scloud</td></tr><tr><td></td><td>0</td><td>0.0921</td><td></td><td>56.0984</td><td>0.5312</td></tr><tr><td></td><td>2.0625</td><td>0.1543</td><td></td><td>59.5941</td><td>0.4799</td></tr><tr><td></td><td>11.0089</td><td>0.0714</td><td></td><td>64.6411</td><td>0.5876</td></tr><tr><td></td><td>22.1305</td><td>0.2822</td><td></td><td>75.2491</td><td>0.7054</td></tr><tr><td></td><td>30.0241</td><td>0.3628</td><td></td><td>79.3264</td><td>0.7732</td></tr></table></body></html>

远，云多分布在云图边缘，ASICDD值低；反之，云面积小但云距中心点近，云多位于云图中央，则不利于天文观测，ASICDD 值高。ASICDD 和 Scloud 非正相关的情况多出现于 Clear类和Outer类之中，可能会导致这两类之间的误判。

$$
d e \nu i a t i o n = \left| S c l o u d - A S I C D D / 1 0 0 \right|
$$

2.4分类算法

这一部分本文采用了SVM，KNN，决策树和随机森林4种传统算法进行分类测试。数据集中训练集包含1056张 ASI图像，其中有 206张Clear，489 张Covered，199 张 Inner 和

162张Outer。另外455张ASI图像用作测试集，包括89张Clear，207张Covered，78 张Inner和81张Outer。本文基于Python中的Scikit-learn（Sklearn）对ASI图像进行分类，将计算的每张云图的ASICDD和Scloud值作为分类特征，训练集用于训练4个分类器，结合分层洗牌分割交叉验证训练超参数，使用准确率（Accuracy)作为模型评分。另采用文献[17]中的结合纹理特征与SVM的方法作对比，基于灰度共生矩阵（Gray-level Co-occurrenceMatrix，GLCM）提取图像的灰度和纹理特征，结合SVM进行云图分类。

# 3实验结果分析

实验部分是在为了较全面地评价本文提出的基于云分布密度和云面积的云

![](images/042311f3d35adbc3f0d7cf15ebf11cf9494dd094a46eeff112c4795ffd34971a.jpg)  
图6云分布密度和云面积之间的关系Fig.6 The relationship of ASICDD and Scloud.

图自动分类系统的分类效果，本文以分类准确率（Accuracy）、精准率（precision）、召回率（recall）和F1-score作为评判指标，在测试集455张 ASI图像上进行自动分类，并与国家天文台提供的人工分类标签作对比，以人工分类结果为准，评估不同分类算法在各类云图上的分类性能。四个指标的定义如下：

$$
A c c u r a c y = ( T P + T N ) / \big ( T P + F P + T N + F N \big )
$$

$$
p r e c i s i o n = T P / \big ( T P + F P \big )
$$

$$
r e c a l l = T P / { \left( T P + F N \right) }
$$

$$
F 1 - s c o r e = \frac { 2 \times p r e c i s i o n \times r e c a l l } { p r e c i s i o n + r e c a l l }
$$

其中，TP表示实为正并划分为正的样本数，TN表示实为负并划分为负的样本数，FP表示实为负却划分为正的样本数，FN表示实为正却划分为负的样本数。测试集上的预测结果如表2所示。可以看出，本文使用的四种算法在各类云图的识别准确率上均达到了 $90 \%$ 以上，这表明本文提出的云分布密度和云面积可以作为可信的云量指标，在云图自动分类工作中展现了其优良性。总体准确率最高的是随机森林算法，Covered 和Inner达到了 $100 \%$ 准确识别。但Outer 类准确率最高的是文献[17]中的方法，本文提出的方法很容易将Outer 类误判为Clear类。基于GLCM特征提取的方法在Outer类的识别较准确，但对Clear类和Inner类的识别准确度较差，因此总体准确率不如本文提出的方法。

对于误判的云图，进行如图7所示的分析。图7(a)是人工判定标签为Clear，系统自动识别为Clear 的云图；图7(b)是人工判定标签为Outer，系统自动识别为Clear的云图（误判云图）。可以看出，图 7(a)(b)在外圈以内均有云存在；图 7(a)中云较薄，分布较分散；图7(b)中云较厚，分布较为集中。这就导致(a)图的云分布密度和云面积值均大于(b)图，因此导

致系统的误判。

![](images/0258ab23d10e7d3c02c29315e1dd9301eb1b14675683dc7a2aa05dd474145786.jpg)  
图7云图误判分析  
Fig.7Misjudgmentanalysisofcloud images.

表2自动分类准确率对比  
Table 2 Comparison of accuracy of automatic classification results   
Table 3 Using precision,recall,and F1-score to evaluate classification results   

<html><body><table><tr><td colspan="2">Categories of cloud images</td><td>Clear</td><td>Covered</td><td>Inner</td><td>Outer</td><td>Total</td></tr><tr><td rowspan="5">precision</td><td>SVM</td><td>0.9158</td><td>0.9902</td><td>0.9500</td><td>0.9733</td><td>0.9573</td></tr><tr><td>KNN</td><td>0.9355</td><td>0.9904</td><td>1</td><td>0.9737</td><td>0.9749</td></tr><tr><td>Decision Tree</td><td>0.9457</td><td>0.9857</td><td>1</td><td>0.9733</td><td>0.9762</td></tr><tr><td>Random Forest</td><td>0.9667</td><td>0.9952</td><td>1</td><td>0.9747</td><td>0.9841</td></tr><tr><td>GLCM+SVM</td><td>0.9540</td><td>0.9951</td><td>0.9500</td><td>0.9634</td><td>0.9656</td></tr><tr><td rowspan="6">recall</td><td>SVM</td><td>0.9775</td><td>0.9807</td><td>0.9744</td><td>0.9012</td><td>0.9584</td></tr><tr><td>KNN</td><td>0.9775</td><td>1</td><td>0.9872</td><td>0.9136</td><td>0.9696</td></tr><tr><td>Decision Tree</td><td>0.9775</td><td>1</td><td>1</td><td>0.9012</td><td>0.9697</td></tr><tr><td>Random Forest</td><td>0.9775</td><td>1</td><td>1</td><td>0.9506</td><td>0.9820</td></tr><tr><td>GLCM+SVM</td><td>0.9326</td><td>0.9903</td><td>0.9744</td><td>0.9753</td><td>0.9681</td></tr><tr><td>SVM</td><td>0.9457</td><td>0.9854</td><td>0.9620</td><td>0.9359</td><td>0.9573</td></tr><tr><td rowspan="5">F1-score</td><td>KNN</td><td>0.9560</td><td>0.9952</td><td>0.9935</td><td></td><td></td></tr><tr><td>Decision Tree</td><td>0.9613</td><td>0.9928</td><td>1</td><td>0.9427 0.9359</td><td>0.9719 0.9725</td></tr><tr><td>Random Forest</td><td>0.9721</td><td>0.9976</td><td>1</td><td>0.9625</td><td>0.9830</td></tr><tr><td>GLCM+SVM</td><td>0.9432</td><td>0.9927</td><td>0.9620</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>0.9693</td><td>0.9668</td></tr></table></body></html>

实验采用精准率（precision）、召回率（recall）和F1-score 对分类结果进行评判，表3显示了四种分类器的分类结果评分，总体评分取样本的宏平均。可以看出，随机森林分类器的各项总评分为最高值，总精准率达到 $9 8 . 4 1 \%$ ，总召回率达到 $9 8 . 2 \%$ ，总F1-score达到 $9 8 . 3 \%$ 在本文的自动分类系统中的分类性能最好。

表3使用精准率、召回率和F1-score评估分类结果

# 4结论

本文的创新点是提出了一个计算全天相机云图云量的直观可信的数值指标——云分布密度，并基于云量的数值特征建立云图自动分类系统，该系统实现了较高的识别准确率。本文测试了SVM，KNN，决策树和随机森林4种传统算法；其中随机森林的准确率更高，各类云图的识别准确率达 $9 5 \%$ 以上。但是还存在云图误判的情况，需要进一步完善计算模型。此外，云图的光照条件容易影响云层厚度的判断，本文未能完全消除光照的影响。因此在接下来的研究中需要考虑光照的影响，通过去噪消除光照影响，或是建立基于光照模型的云量计算模型。除此之外，还可以结合最新的机器学习算法完善系统，提高系统的识别准确率。

# 参考文献

[1] Dev S，Wen B, Lee Y H，et al. Ground-Based Image Analysis: A Tutorial on Machine-Learning Techniques and Applications[J]. IEEE Geoence & Remote Sensing Magazine, 2016, 4(2):79-93.

[2]Kotarba, Andrzej Z . Evaluation of ISCCP cloud amount with MODIS observations[J]. Atmospheric Research,2015,153:310-317.   
[3] Long C N，Sabburg JM，Calbo J，et al. Retrieving Cloud Characteristics from Ground-Based Daytime Color All-Sky Images[J]. Journal of Atmospheric and Oceanic Technology, 2006,23(5):633-652.   
[4]杨俊，吕伟涛，马颖，等．基于自适应阈值的地基云自动检测方法[J]．应用气象学报， 2009, 20(6):713-721. Yang J,Lv W T,Ma Y,et al. An Automatic Ground-based Cloud Detection Method Basedon Adaptive Threshold[J]. Journal of AppliedMeteorology， 2009, 20(6):713-721.   
[5]Liu S, Zhang L B, Zhang Z, et al. Automatic Cloud Detection for All-Sky Images Using Superpixel Segmentation[J]. Geoscience and Remote Sensing Letters, IEEE,2015.   
[6] Jelenak A，Heidinger A K .Validation of CLAVR-x cloud detection over ocean using AVHRR GAC sea surface temperature[J]. Proceedings of Spie the International Society for Optical Engineering,2005, 5658:292-298..   
[7] Gang，M. A.， Zongyi, F., Fengying， Z.: An error analysis on the simulated data of TOVS HIRS by RTTOV5 model[J]. Journal of Meteorological Research, 2002,16(2):226-241.

[8] Cheng HY,Lin C L . Cloud detection in all-sky images via multi-scale neighborhood features and multiple supervised learning techniques[J]. Atmospheric Measurement Techniques,2017,10(1):1-20.

[9]Blazek M，Pata P . Colour transformations and K-means segmentation for automatic cloud detection[J]. Meteorologische Ztschrift, 2015, 24(5):503-509.

[10] Taravat A，Del Frate F，Cornaro C ，et al. Neural Networks and Support Vector Machine Algorithms for Automatic Cloud Classification of Whole-Sky Ground-Based Images[J]. IEEE Geoence & Remote Sensing Letters,2014， 12(3):666-670.

[11] Dev S,Member, IEEE,etal. CloudSegNet: A Deep Network for Nychthemeron Cloud Image Segmentation[J]. IEEE Geoscience & Remote Sensing Letters，2019, PP(99):1-5.

[12] Ye L, Cao Z, Xiao Y,et al. Supervised Fine-Grained Cloud Detection and Recognition in Whole-Sky Images[J]. IEEE Transactions on Geoence and Remote Sensing,2019, PP(99):1-14.

[13] Dev S，Savoy F M，Lee Y H，et al. High-Dynamic-Range Imaging for Cloud Segmentation[J]. Atmospheric Measurement Techniques, 2018, 11(4).

[14]张家强，李潇雁，李丽圆,等．基于深度残差全卷积网络的Landsat8遥感影像云检测方法[J．激光与光电子学进展,2020,57(10):364-371.

Zhang J Q, Li X Y, Li L Y, et al. L andsat8 remote sensing image based on deep residual fully convolutional network[J]. Laster& Optoelectronics Progress, 2020,57(10):364-371.

[15]郭玥，于希明，王少军,等．遥感图像云检测的多尺度融合分割网络方法[J]．仪器仪表学

报,2019,40(6):31-38.

Guo Y, Yu X M,Wang S J, et al. Cloud detection in remote sensing images with multilevel scale fused network[J]. Chinese Journal of Scientific Instrument, 2019,40(6):31-38.

[16] Shi C J, Zhou Y T, Qiu B, et al. Diurnal and nocturnal cloud segmentation of all-sky imager (ASl) images using enhancement fully convolutional networks[J]. Atmospheric Measurement Techniques,2019,12(9):4713-4724.

[17]贾杰，邵丽群.遥感领域中气象卫星云图自动分类研究[J].无线互联科技，2016(01):120-123.

Jia J，Shao L Q.The research of automatic classification of meteorological satellite imagery in remote sensing field[J].Wireless Internet Technology, 2016(01):120-123.

[18]魏诗雅,邱波,曹子皇,等.一种全天相机云图的自动处理方法[J].天文研究与技术，2019,16(01):85-92.

Wei S Y，Qiu B，Cao Z H，et al. An Automatic Processing Method for All-sky Images[J]. Astronomical Research & Technology, 2019,16(01):85-92.

[19]高振斌,李梦慈,邱波,等.全天相机云图去噪算法的研究[J].天文研究与技术，2020,17(01):76-84.

Gao Z B, Li M C, Qiu B,et al. Research on denoising algorithm for camera image of all-day camera[J]. Astronomical Research & Technology,2019,16(01):85-92.

A cloud cover measurement index based on all-sky imager

# images

Zhang Yuxin1, Qiu Bo', Shi Chaojun1,Li Mengci', Xiang Guanjie (1.HebeiUniversity of Technology，Tianjin，300401)

Abstract: All-sky imager (ASI) images are an important means for the astronomy community to monitor cloud cover at present, but there is no definite cloud cover calculation index.Therefore, this paper proposes a new quantitative index for cloud amount measurement--Cloud Distribution Density of ASI images (ASICDD),and establishes an automatic classification system for ASI images based on this index.Firstly,all the images in the dataset from the Key Laboratory of Optical Astronomy at the National Astronomical Observatories of Chinese Academy of Sciences (CAS) are denoised and the cloud area is segmented from the sky by OTSU algorithm. Secondly, the cloud amount for ASI image with the background remove is calculated by ASICDD proposed in this paper. Finally, we use four traditional classifiers (SVM, KNN,Decision Tree and Random Forest)to classify ASI images automatically according to the calculated value and evaluate the performance of each classifier. The results show that ASICDD can be used as a numerical index for judging the cloud cover of ASI images; the automatic ASI images classfication system based on ASICDD achieves a high recognition accuracy rate. Meanwhile Random Forest has the best classification effect--the recognition accuracy rate of various cloud images has reached more than $9 5 \%$ ：

Keywords: ASICDD; all-sky images; TMT; cloud cover measurement