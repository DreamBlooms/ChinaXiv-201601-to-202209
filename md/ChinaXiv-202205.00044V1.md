# 一种具有平衡标签预测能力的在线哈希算法

何硕，谢良(武汉理工大学 理学院，武汉 430070)

摘要：针对传统离线哈希算法训练模型耗时、占用内存大和不易更新模型的问题，以及现实图像集的标签存在大量损失的现象，提出了一种能够平衡标签预测的在线哈希算法(balancedlabelprediction foronline hashing，BLPOH)。BLPOH通过标签预测模块生成预测标签，并融合残缺的真实标签，能够有效缓解因标签损失导致的模型性能下降。观察到标签存在分布不平衡现象，提出标签类别相似性平衡算法并应用于标签预测模块，提升标签预测的准确性。将旧数据的信息加入哈希函数的在线更新过程，提升模型对旧数据的兼容性。通过在两个广泛使用的数据集上进行实验，并和一些当前先进的算法进行对比，结果证实了BLPOH的优越性。

关键词：在线哈希；多标签；标签预测；图像检索 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.02.0088

Online hash algorithm with balanced label prediction ability

He Shuo, Xie Liang† (SchoolofFaculty ofScience,Wuhan University of Technology,Wuhan43oo70,China)

Abstract:Aimingattheproblems thattheraditionaloflinehashingalgorithmis time-consumingtorainthe model,occupies alargeamountofmemoryandisdificult toupdatethe model,andthereisalargelossoflabels inreal imagesets,this paper proposed a balanced label prediction foronline hashing algorithm(BLPOH).BLPOH generated predicted labels through the label prediction module,and fused the incompletereallabels,whichcan efectivelyalleviate theperformancedegradationof the modelcaused by labellossItobserved that there isan imbalance inthe distributionof labels,then proposedalabel category similarity balance algorithm toapplytothe label prediction module to improve the accuracyof label prediction.It addedthe informationofolddatatotheonline update process ofthe hash functionto improvethecompatibilityofthe model to the olddata.Byconducting experiments ontwo widelyused datasetsandcomparing withsome state-of-the-art algorithms, the results demonstrate the superiority of BLPOH.

Keywords:online hashing;multi label; label prediction; image retrieval

# 0 引言

哈希算法由于其高效的检索能力和占用存储低的特点而在图像检索领域一直备受关注。哈希算法把高维的图像特征映射到一个低维的二值空间[1]，得到一连串紧凑的哈希码，这串哈希码保留了图像间的相似性信息[2]。正是由于哈希码的这些特性，使得图像检索任务可以在一个低维空间高效地进行，而哈希码的质量也就成为影响图像检索性能的关键因素。

研究者们致力于学习一个优秀的哈希函数，得到高质量的哈希码。Gionis 等人[3]提出局部敏感哈希算法(Locality-SensitiveHashing,LSH)。LSH是一种无监督哈希算法，通过将原始数据随机映射到不同的哈希桶中，然后经过符号函数得到哈希码。Weiss 等人[4]提出谱哈希算法(Spectral Hashing,SH)。SH以图像分割的思想解决图像特征的编码问题。Wang等人[5]提出基于半监督学习的图像哈希检索算法(Semi-SupervisedHashing，SSH)。Liu 等人[提出图哈希算法(HashingwithGraphs,AGH)。AGH有很多思想源于SH，不同的是AGH通过数据聚类中心和数据样本点之间的近邻图近似样本点之间的近邻图。Shen等人[7提出基于有监督的哈希算法(Supervised Discrete Hashing,SDH)。SDH通过离散循环下降算法(Cyclic CoordinateDescent,DCC)按位求解哈希码避免松弛化求解引起的次优问题。

然而，以上提出的哈希算法都是通过离线学习[8]的方式一次性从所有数据中学习哈希函数。面对越来越庞大的图像数据集，这些离线哈希算法在学习过程中不仅占用大量的内存空间，而且十分耗时。不仅如此，每当新数据到来，离线哈希算法为了更新模型不得不重新进行训练。面对这样的应用场景，在线哈希算法(OnlineHashing)能够很好地解决这些问题。在线哈希算法流式地读取数据[9]，每次只从一个数据流中训练并更新模型，占用空间小，训练模型快，并且易于更新模型。近年来，研究者们提出了多种在线哈希算法。作为代表的在线哈希算法包括在线核哈希[10](OnlineKernelHashing,OKH)，在线监督哈希[11](Online Supervised Hashing,OSH)，自适应哈希[12](Adaptive Hashing,AdaptHash)，在线草图哈希[13](Sketching Hashing,SketchHash)，具有共同信息的在线哈 希 [14](Online Hashing with Mutual Information,MIHASH)和平衡相似性在线离散哈希[15] (Balanced Similarityfor Online Discrete Hashing,BSODH)，高效更新哈希码的在线哈希[16](Online Hashing with Efficient Updating of Binary Codes,OHWEU)，哈达玛矩阵引导的在线哈希[17](HadamardMatrixOnlineHashing，HMOH）以及通过哈达玛码书学习的监督在线哈希[18](Online Hashing via Hadamard Codebook,HCOH)。

虽然这些在线哈希算法解决了离线哈希算法在巨大数据集上较难训练和更新模型的问题，但是它们仍然存在一些缺点。现实可用的图像数据集总会由于图像标注[19]误差造成图像标签的缺失，然而当前的在线哈希算法都默认用到的数据集的标签是完整的，这造成模型精度的下降。以BSODH为例，只考虑多标签数据的情况下，以两幅图像是否共享至少一个标签来判断它们是否相似[20]，由于图像标签并不完整，导致构造的图像标签相似性矩阵不准确，最终造成模型精度的损失。

本文提出了一种能够平衡标签预测的在线哈希算法(BLPOH)。引入在线哈希算法，避免离线哈希算法在巨大图像数据集上训练耗时，占用内存大和加入新数据需要重新训练的问题。考虑到现实图像标签存在缺失的问题，加入标签预测[2I模块，通过图像相似性和标签类别相似性预测近邻图像的标签，以对抗图像标签缺失引起的性能损失。由于多数标签类别是不相似的，相似的只有少数，所以，标签类别存在不平衡现象。因此，在标签预测模块设计了一个标签类别相似性平衡算法，提升标签预测的准确性。此外，本文巧妙地根据汉明距离[22]的退化形式度量新旧数据之间哈希码和标签的距离，使旧数据的信息参与哈希函数的在线更新。本文在MIRFlickr25k和NUS-WIDE两个数据集上进行广泛的实验，并和一些当前先进的算法进行对比以证明BLPOH的优越性。

本文的主要贡献如下：

a）本文引入在线哈希算法，解决了离线哈希在巨大数据集训练和更新模型难的问题。并通过加入标签预测模块，缓解了现实图像数据标签缺失引起的性能下降问题。

b)本文考虑到标签类别分布不平衡问题，在标签预测模块设计标签类别相似性平衡算法，提升预测的准确性。

c）本文通过汉明距离的退化形式建立新旧数据之间哈希码和标签的相似性对等关系，让旧数据的信息监督哈希函数的在线更新，解决了在线哈希在旧数据上性能下降的问题，提升哈希函数对旧数据的兼容性。

# 1 算法框架

图1展示了BLPOH的整体框架。每当数据流中有新数据到来时，通过找出图像的 $K$ 近似最近邻计算图像相似性矩阵，并把该矩阵应用到标签预测当中。然后，通过预测的标签计算图像标签相似性矩阵，并利用该矩阵与旧数据建立关联，使得旧数据的信息也参与到哈希函数的在线更新过程。最后，通过哈希函数计算出图像数据的哈希码。

![](images/b698bb8736a644a1959f0a5772b843c2ff1e205f666e2781d752bc23fd95a0c6.jpg)  
图1算法框架图  
Fig.1Algorithm framework diagram

# 1.1问题定义

给出一个多标签数据集， $X = [ x _ { 1 } , . . . , x _ { n } ] ^ { T } \in \mathbb { R } ^ { n \times d }$ 表示图像特征集， $L = [ l _ { 1 } , . . . , l _ { n } ] ^ { T } \in \mathbb { N } ^ { n \times u }$ 表示标签集，其中 $\boldsymbol { x } _ { i } \in \mathbb { R } ^ { d }$ 是第 $i$ 个图像实例，它对应的标签是 $l _ { i } \in \mathbb { N } ^ { u }$ ， $n$ 是实例的个数， $\boldsymbol { u }$ 是标签类别数量， $\textit { d }$ 是图像特征的维度。哈希函数把图像特征数据映射为 $B = [ b _ { 1 } , . . . , b _ { n } ] ^ { T } \in \{ - 1 , + 1 \} ^ { n \times k }$ ，其中 $b _ { i }$ 是图像实例 $x _ { i }$ 对应的二进制哈希码向量， $k$ 是哈希码的位数。一般情况下，哈希函数都采用如BSODH的线性哈希映射，为了适合本文的数据处理方式，将哈希函数定义为

$$
B = F ( X ) = \operatorname { s g n } ( X W )
$$

其中， $W$ 是投影矩阵。 $\operatorname { s g n } ( x )$ 是符号函数，当变量 $x { > } 0$ 时返回1，否则返回-1。

将在线哈希算法的数据流表示为 $X _ { s } ^ { \prime }$ 和 $X _ { e } ^ { \prime }$ ，其中$X _ { s } ^ { t } = [ x _ { s 1 } ^ { t } , . . . , x _ { s n _ { t } } ^ { t } ] ^ { T } \in \mathbb { R } ^ { n _ { t } \times d }$ 表示 $\textit { t }$ 时刻到来的新数据，$X _ { e } ^ { t } = [ x _ { e 1 } ^ { t } , . . . , x _ { e m _ { t } } ^ { t } ] ^ { T } \in \mathbb { R } ^ { m _ { t } \times d }$ 表示 $t$ 时刻已经存在的旧数据，以及它们在 $\textit { t }$ 时刻对应的真实标签矩阵 $L _ { s } ^ { t } = [ l _ { s 1 } ^ { t } , . . . , l _ { s n _ { t } } ^ { t } ] ^ { T } \in \mathbb { N } ^ { n _ { t } \times u }$ 和$\boldsymbol { L } _ { e } ^ { t } = [ l _ { e 1 } ^ { t } , . . . , l _ { e m _ { t } } ^ { t } ] ^ { T } \in \mathbb { N } ^ { m _ { t } \times u }$ ， $n _ { t }$ 表示 $t$ 时刻数据流中的数据量， $m _ { t }$ 表示$t$ 时刻已经存在的数据量。对应地，把 $t$ 时刻数据流中的新数据对应的哈希码矩阵表示为 $B _ { s } ^ { t } = \mathrm { s g n } ( X _ { s } ^ { t } W ^ { t } ) = [ b _ { s 1 } ^ { t } , . . . , b _ { s n _ { t } } ^ { t } ] ^ { T } \in \{ - 1 , + 1 \} ^ { n _ { t } \times k }$ 把 $\textit { t }$ 时刻已经存在的旧数据对应的哈希码矩阵表示为$B _ { e } ^ { t } = \operatorname { s g n } ( X _ { e } ^ { t } W ^ { t } ) = [ b _ { e 1 } ^ { t } , . . . , b _ { e m _ { t } } ^ { t } ] ^ { T } \in \{ - 1 , + 1 \} ^ { m _ { t } \times k }$ 。在本文的在线哈希算法中,随着新数据 $X _ { s } ^ { t }$ 的到来，以在线的方式更新 $t$ 时刻的哈希码投影矩阵 $W ^ { t }$ 。把 $t$ 时刻数据流对应的预测标签矩阵表示为$Y _ { s } ^ { t } = [ y _ { s 1 } ^ { t } , . . . , y _ { s n _ { t } } ^ { t } ] ^ { T } \in \{ - 1 , + 1 \} ^ { n _ { t } \times u }$ ，把已经存在的旧数据对应的预测标签矩阵表示为 $Y _ { e } ^ { t } = [ y _ { e 1 } ^ { t } , . . . , y _ { e m _ { t } } ^ { t } ] ^ { T } \in \{ - 1 , + 1 \} ^ { m _ { t } \times u }$ ，-1表示没有该标签，1表示拥有该标签。

表1介绍了本文主要的变量及其定义。

表1关键变量的介绍  
Tab.1Introduction to key variables   

<html><body><table><tr><td>变量</td><td>定义</td></tr><tr><td>X</td><td>t时刻的数据流</td></tr><tr><td>X</td><td>t时刻已经存在的旧数据</td></tr><tr><td>Y</td><td>t时刻数据流X!对应的预测标签矩阵</td></tr><tr><td>Y</td><td>t时刻旧数据X对应的预测标签矩阵</td></tr><tr><td>B</td><td>t时刻数据流X对应的哈希码矩阵</td></tr><tr><td>B</td><td>t时刻旧数据X对应的哈希码矩阵</td></tr><tr><td>W:</td><td>t时刻哈希函数对应的投影矩阵</td></tr><tr><td>V</td><td>t时刻X和Y间的投影矩阵</td></tr></table></body></html>

# 1.2模型框架

# 1.2.1标签预测及标签类别相似性平衡

正如前面提到的，现实可用的图像数据集总会由于标注误差导致数据集的标签存在缺失。考虑到这种情况，本文通过建立标签预测模块来对抗标签缺失引起的模型精度下降问题。受到文献[21]的启发，在假设标签类别相似矩阵 $\mathcal { Q } _ { s }$ 已知的情况下，一个图像实例的标签可以由该图像实例的最近邻近似地表示。类似地，一个图像实例的标签也可以由该标签的最近邻近似地表示。建立如文献[21的标签预测正则化项，得到 $t$ 时刻的关系表达公式：

$$
\operatorname* { m i n } _ { Y _ { s } ^ { \prime } } \Vert Y _ { s } ^ { \prime } - S _ { i } ^ { \prime } Y _ { s } ^ { \prime } Q _ { s } ^ { \prime } \Vert _ { F } ^ { 2 } ~ s . t . ~ Y _ { s } ^ { \prime } \in \{ - 1 , 1 \} ^ { n _ { r } \times u }
$$

其中， $S _ { i } ^ { t }$ 是 $t$ 时刻通过图像的 $K$ 近似最近邻计算得到的图像实例间的相似性矩阵。I·Il表示Frobenius范数。

和文献[21]不同的是，本文创新性的提出标签类别相似性平衡算法。标签类别相似性平衡算法基于标签类别分布不平衡现象：绝大多数标签对是不相似的，少数标签对是相似的。为了解决这个问题，本文将标签类别相似矩阵分为 $\boldsymbol { Q } _ { s 1 }$ 和$Q _ { s 2 }$ 两部分，它们分别表示相似标签对和非相似标签对，对于$\scriptstyle Q _ { s 1 }$ ，给它分配一个较小的权重，而给 $\scriptstyle Q _ { s 2 }$ 分配一个较大的权重，以此让标签类别相似性向标签对不相似的方向偏移。对于没有添加标签类别相似性平衡算法的模型，为了达到和添加该算法的模型同等精度，需要迭代更多的次数，导致在相同迭代次数下预测的标签的准确性和预测的收敛速度都较为低下。将标签类别相似性平衡算法的公式定义如下：

$$
\tilde { Q } _ { i j } ^ { t } = \left\{ \eta _ { s } Q _ { i j } ^ { t } , \ Q _ { i j } ^ { t } > 0 \right.
$$

其中， $\eta _ { s }$ 表示较小的权重， $\eta _ { d }$ 表示较大的权重。

1.2.2映射关系及其损失函数的定义

此外，建立 $\boldsymbol { \cal X }$ 到预测标签 $Y$ 的线性映射关系， $Y$ 以 $X V$ 表示，建立 $t$ 时刻 $X _ { s } ^ { \prime } V ^ { t }$ 和 $Y _ { s } ^ { t }$ 的 $F$ 范数损失：

$$
\operatorname* { m i n } _ { V ^ { \prime } } \| X _ { s } ^ { \prime } V ^ { \prime } - Y _ { s } ^ { \prime } \| _ { F } ^ { 2 }
$$

哈希算法的目的是学习一个哈希函数，根据式(1)，最小化线性哈希函数 $F$ 和 $X _ { s } ^ { t }$ 对应哈希码 $B _ { s } ^ { t }$ 之间的误差，建立公式：

$$
\operatorname* { m i n } _ { W ^ { t } } \| X _ { s } ^ { t } W ^ { t } - B _ { s } ^ { t } \| _ { F } ^ { 2 }
$$

1.2.3旧数据的信息参与哈希函数的在线更新

以汉明距离度量两个维度相同的向量之间的距离。如果两个数据越相似，则它们对应的二进制哈希码之间的汉明距离越小，反之越大。在训练新数据和更新模型的同时，得到的新模型应该同样适用于旧数据。因此，从数据流中训练模型的同时，应该把旧数据的信息考虑在内。考虑到如果数据$x _ { i }$ 和 $x _ { j }$ 是相似的，那么它们就有相似的标签矩阵，而且由哈希函数的特性可知，哈希码保留了数据间的相似性关系，因此能够通过哈希码和标签数据建立新数据和旧数据之间的相似性对等关系。考虑到，当哈希码以-1和1表示时，那么哈希码 $b _ { i }$ 和 $b _ { j }$ 之间的汉明距离 $h$ 就可以表示为

$$
h { = } 1 / 2 ( k { - } < b _ { i } , b _ { j } > )
$$

其中， $< b _ { i } , b _ { j } >$ 表示 $b _ { i }$ 和 $b _ { j }$ 的内积。

同样，对于某个标签类别，以-1和1分别标识数据没有该标签和拥有该标签。最小化两者间的 $F$ 范数损失得：

$$
\begin{array} { c } { \displaystyle \operatorname* { m i n } _ { B _ { s } ^ { t } , B _ { e } ^ { t } } \| B _ { s } ^ { t } B _ { e } ^ { t T } - S _ { l } ^ { t } \| _ { F } ^ { 2 } } \\ { s . t . ~ B _ { s } ^ { t } \in \{ - 1 , 1 \} ^ { n _ { t } \times k } , B _ { e } ^ { t } \in \{ - 1 , 1 \} ^ { m _ { t } \times k } } \end{array}
$$

其中， $S _ { l } ^ { t }$ 是标签相似性矩阵。

为了有效利用存在损失的真实标签信息，在计算标签相似性矩阵 $S _ { l } ^ { t }$ 时，将存留的真实标签信息附加到对应的预测标签上，即将真实的标签矩阵中为1处的值加到对应位置的预测标签矩阵中，充分利用已经存在的真实标签信息，进一步提升模型的精度。因为只需要利用标签存在的信息，所以把$L _ { s } ^ { t }$ 和 $L _ { e } ^ { t }$ 中值为-1的位置替换为0，为1的位置不变，分别用$A _ { s } ^ { t }$ 和 $A _ { e } ^ { t }$ 表示。 $S _ { l } ^ { t }$ 的计算定义如下：

$$
S _ { l } ^ { t } = k ( Y _ { s } ^ { t } + A _ { s } ^ { t } ) ( Y _ { e } ^ { t } + A _ { e } ^ { t } ) ^ { T } { \big / } u
$$

综上，建立BLPOH的模型公式：

$$
\operatorname* { m i n } _ { Q _ { s } ^ { t } , B _ { s } ^ { t } , B _ { e } ^ { t } , W ^ { t } , V ^ { t } , Y _ { s } ^ { t } } \parallel Y _ { s } ^ { t } - S _ { i } ^ { t } Y _ { s } ^ { t } Q _ { s } ^ { t } \parallel _ { F } ^ { 2 } +
$$

$$
\alpha \parallel B _ { s } ^ { t } B _ { e } ^ { t T } - S _ { l } ^ { t } \parallel _ { F } ^ { 2 } + \beta \parallel X _ { s } ^ { t } W ^ { t } - B _ { s } ^ { t } \parallel _ { F } ^ { 2 } +
$$

$$
\varsigma \| X _ { s } ^ { t } V ^ { t } - Y _ { s } ^ { t } \| _ { F } ^ { 2 } + \lambda ( \| W ^ { t } \| _ { F } ^ { 2 } + \| V ^ { t } \| _ { F } ^ { 2 } )
$$

$$
s . t . \ B _ { s } ^ { t } \in \{ - 1 , 1 \} ^ { n _ { t } \times k } , B _ { e } ^ { t } \in \{ - 1 , 1 \} ^ { m _ { t } \times k } , Y _ { s } ^ { t } \in \{ - 1 , 1 \} ^ { n _ { t } \times u }
$$

# 1.3算法优化

由于存在二进制约束问题，所以采用迭代的方式进行求解，在更新一个变量时固定其他变量，把其他变量当作常量处理。

1)更新 $W ^ { t }$ ：固定 $\mathcal { Q } _ { s } ^ { \prime }$ ， $B _ { s } ^ { \prime }$ ， $B _ { e } ^ { \prime }$ ， $V ^ { t }$ 和 $Y _ { s } ^ { t }$ ，然后学习 $W ^ { t }$ 。求解 $W ^ { t }$ 的子问题是：

$$
\operatorname* { m i n } _ { W ^ { \prime } } \beta \lVert X _ { s } ^ { \prime } W ^ { \prime } - B _ { s } ^ { \prime } \rVert _ { F } ^ { 2 } + \lambda ( \lVert W ^ { \prime } \rVert _ { F } ^ { 2 } )
$$

因此，可以得到式(10)的闭式解：

$$
W ^ { t } = \beta ^ { t } ( \beta ^ { t } X _ { s } ^ { t T } X _ { s } ^ { t } + \lambda ^ { t } I ) ^ { - 1 } X _ { s } ^ { t T } B _ { s } ^ { t }
$$

其中， $I$ 是一个 $d { \times } d$ 的单位矩阵。

2)更新 $\smash { \boldsymbol { V } ^ { t } }$ ：和更新 $W ^ { t }$ 一样，固定 $\mathcal { Q } _ { s } ^ { t }$ ， $B _ { s } ^ { t }$ ， $B _ { e } ^ { \prime }$ ， $W ^ { t }$ 和 $Y _ { s } ^ { t }$ ，然后学习 $\boldsymbol { V ^ { t } }$ 。求解的子问题是：

$$
\operatorname* { m i n } _ { V ^ { t } } \varsigma \| X _ { s } ^ { t } V ^ { t } - Y _ { s } ^ { t } \| _ { F } ^ { 2 } + \lambda ( \| V ^ { t } \| _ { F } ^ { 2 } )
$$

因此，可以得到 $\mathbf { \Omega } _ { V ^ { t } }$ 的闭式解：

$$
V ^ { t } = \varsigma ^ { t } ( \varsigma ^ { t } X _ { s } ^ { t T } X _ { s } ^ { t } + \lambda ^ { \prime } I ) ^ { - 1 } X _ { s } ^ { t T } Y _ { s } ^ { t }
$$

3）更新 $B _ { e } ^ { t }$ ：同样固定其他所有变量，更新 $B _ { e } ^ { t }$ 。求解子问题是：

$$
\operatorname* { m i n } _ { B _ { e } ^ { \prime } } \alpha \| B _ { s } ^ { \prime } B _ { e } ^ { \prime T } - S _ { l } ^ { \prime } \| _ { F } ^ { 2 } \quad s . t . \ B _ { e } ^ { \prime } \in \{ - 1 , 1 \} ^ { m _ { e } \times k }
$$

类似文献[23]，式(14)又可以退化为求解：

$$
\operatorname* { m i n } _ { B _ { \epsilon } ^ { \prime } } \big \| B _ { s } ^ { \prime } B _ { e } ^ { \prime T } - S _ { l } ^ { \prime } \big \| _ { 1 } \quad s . t . \ B _ { e } ^ { \prime } \in \{ - 1 , 1 \} ^ { m _ { \epsilon } \times k }
$$

求解式(15)，得

$$
B _ { e } ^ { t } = \mathrm { s g n } ( S _ { l } ^ { t T } B _ { s } ^ { t } ) \in \{ - 1 , 1 \} ^ { m _ { t } \times k }
$$

4)）更新 $B _ { s } ^ { t }$ ：固定其他所有变量，学习 $B _ { s } ^ { t }$ 。求解子问题为

$$
\begin{array} { r l } & { \underset { B _ { s } ^ { t } } { \operatorname* { m i n } } \alpha \| B _ { s } ^ { t } B _ { e } ^ { t T } - S _ { l } ^ { t } \left. _ { F } ^ { 2 } + \beta \right. X _ { s } ^ { t } W ^ { t } - B _ { s } ^ { t } \left. _ { F } ^ { 2 } \right. } \\ & { ~ \left. s . t . ~ B _ { s } ^ { t } \in \{ - 1 , 1 \} ^ { n _ { t } \times k } \right. } \end{array}
$$

展开式(17)为

$$
\begin{array} { r l } & { \underset { \boldsymbol { B } _ { s } ^ { t } } { \operatorname* { m i n } } \alpha (  \boldsymbol { B } _ { e } ^ { t } \boldsymbol { B } _ { s } ^ { t T }  _ { F } ^ { 2 } +  \boldsymbol { S } _ { l } ^ { t }  _ { F } ^ { 2 } - 2 t r ( \boldsymbol { B } _ { s } ^ { t } \boldsymbol { B } _ { e } ^ { t T } \boldsymbol { S } _ { l } ^ { t T } ) ) +  } \\ & {  \beta (  \boldsymbol { B } _ { s } ^ { t }  _ { F } ^ { 2 } +  \boldsymbol { W } ^ { t T } \boldsymbol { X } _ { s } ^ { t T }  _ { F } ^ { 2 } - 2 t r ( \boldsymbol { B } _ { s } ^ { t } \boldsymbol { W } ^ { t T } \boldsymbol { X } _ { s } ^ { t T } ) )   } \\ & {   s . t . \boldsymbol { B } _ { s } ^ { t } \in \{ - 1 , 1 \} ^ { n _ { t } \times k }   } \end{array}
$$

式(18)可以简化为

$$
\begin{array} { r l } { \ } & { \underset { \boldsymbol { B } _ { s } ^ { t } } { \operatorname* { m i n } } \alpha \parallel \boldsymbol { B } _ { e } ^ { t } \boldsymbol { B } _ { s } ^ { t T } \parallel _ { F } ^ { 2 } - 2 t r ( \alpha \boldsymbol { B } _ { s } ^ { t } \boldsymbol { B } _ { e } ^ { t T } \boldsymbol { S } _ { l } ^ { t T } + \beta \boldsymbol { B } _ { s } ^ { t } \boldsymbol { W } ^ { t T } \boldsymbol { X } _ { s } ^ { t T } ) } \\ & { \quad \quad \quad s . t . \ \boldsymbol { B } _ { s } ^ { t } \in \{ - 1 , 1 \} ^ { n _ { t } \times k } } \end{array}
$$

和 BSODH类似，使 $P = \alpha B _ { e } ^ { t T } S _ { l } ^ { t T } + \beta W ^ { t T } X _ { s } ^ { t T }$ ，得到：

$$
\begin{array} { c } { \underset { { B _ { s } ^ { t } } } { \operatorname* { m i n } } \alpha \| \boldsymbol B _ { s } ^ { t } { B _ { e } ^ { t T } } \| _ { F } ^ { 2 } - 2 t r ( B _ { s } ^ { t } P )   } \\ {   \qquad \mathrm { \Omega } _ { t e r m \mathrm { I } }  \qquad } \\ { { s . t . } \ { B _ { s } ^ { t } } \in \{ - 1 , 1 \} ^ { n _ { r } \times k } } \end{array}
$$

其中， $t e r m \mathrm { I } = \tilde { b } _ { s r } ^ { t } \tilde { b } _ { e r } ^ { t } { } ^ { T } + \tilde { B } _ { s } ^ { t } \tilde { B } _ { e } ^ { t T }$ ， $t e r m \Pi = \tilde { b } _ { s r } ^ { t } \tilde { p } _ { r } + \tilde { B } _ { s } ^ { t } \tilde { P }$ ， $\tilde { b } _ { s r } ^ { t }$ ， $\tilde { b } _ { e r } ^ { t }$ ， $\tilde { p } _ { r }$ 分别代表代表 $B _ { s } ^ { \ i } \ , \ B _ { e } ^ { \ i } \ , P$ 的第 $\boldsymbol { r }$ 行， $\tilde { B } _ { s } ^ { t }$ ， $\tilde { B } _ { e } ^ { t }$ ， $\tilde { P }$ 分别代表除了 $\tilde { b } _ { s r } ^ { t }$ ，$\tilde { b } _ { e r } ^ { t }$ ， $\tilde { p } _ { r }$ 余下的行。

式(20)转换为

$$
\begin{array} { c } { \displaystyle \operatorname* { m i n } _ { \tilde { b } _ { s r } ^ { t } } \alpha \| \tilde { b } _ { s r } ^ { t } \tilde { b } _ { e r } ^ { t } + \tilde { B } _ { s } ^ { t } \tilde { B } _ { e } ^ { t T } \| _ { F } ^ { 2 } - 2 t r ( \tilde { b } _ { s r } ^ { t } \tilde { p } _ { r } ) - } \\ { 2 t r ( \tilde { B } _ { s } ^ { t } \tilde { P } ) \ s . t . \ \tilde { b } _ { s r } ^ { t } \in \{ - 1 , 1 \} ^ { 1 \times k } } \end{array}
$$

求解式(21)，得

$$
\tilde { b } _ { s r } ^ { t } = \mathrm { s g n } ( \tilde { p } _ { r } ^ { \ T } - \alpha \tilde { B } _ { s } ^ { t } \tilde { B } _ { e } ^ { t T } \tilde { b } _ { e r } ^ { t } ) \in \{ - 1 , 1 \} ^ { 1 \times k }
$$

通过迭代求解每一行，得到最终的 $B _ { s } ^ { \prime }$ 。

5）更新 $Y _ { s } ^ { t }$ ：固定其他所有变量，学习 $Y _ { s } ^ { t }$ 。求解子问题为

$$
\begin{array} { c } { \displaystyle \operatorname* { m i n } _ { Y _ { s } ^ { t } } \| Y _ { s } ^ { t } - S _ { i } ^ { t } Y _ { s } ^ { \prime } Q _ { s } ^ { t } \| _ { F } ^ { 2 } + \varsigma \| X _ { s } ^ { t } V ^ { t } - Y _ { s } ^ { t } \| _ { F } ^ { 2 } } \\ { s . t . ~ Y _ { s } ^ { t } \in \{ - 1 , 1 \} ^ { n _ { t } \times u } } \end{array}
$$

将式(23)转换为普通的线性方程：

$$
( M ^ { T } M + \varsigma I \_ V ) V e c { ( Y _ { s } ^ { t } ) } = V e c { ( \varsigma X _ { s } ^ { t } V ^ { t } ) }
$$

其中， $M = I _ { - } V - L _ { - } S$ ， $L _ { - } S = Q _ { s } ^ { t T } \otimes S _ { i } ^ { t }$ ， $\otimes$ 是Kronecker 积,$I _ { - } V$ 是一个 $u n _ { t } \times u n _ { t }$ 的单位矩阵。

6)更新 $\mathcal { Q } _ { s } ^ { t }$ ：固定其他所有变量，更新 $\mathcal { Q } _ { s } ^ { t }$ 。过程和求解 $Y _ { s } ^ { t }$ 类似，得

$$
( I _ { - } L \otimes ( ( S _ { i } ^ { t } Y _ { s } ^ { t } ) ^ { T } ( S _ { i } ^ { t } Y _ { s } ^ { t } ) ) ) V e c ( Q _ { s } ^ { t } ) = V e c ( ( S _ { i } ^ { t } Y _ { s } ^ { t } ) ^ { T } Y _ { s } ^ { t } )
$$

其中， $I _ { - } L$ 是一个 $\boldsymbol { u } \boldsymbol { u } \times \boldsymbol { u } \boldsymbol { u }$ 的单位矩阵。

算法1 BLPOH 的描述

输入：数据集 $X$ ，哈希码位数 $k$ ，数据流大小 $n _ { \scriptscriptstyle { t } }$ ，参数 $\alpha ~ , ~ \beta ~ , ~ \varsigma$ ，$\lambda$ ， $\eta _ { s } / \eta _ { d }$ 和图像的最近邻个数 $K$ 。  
输出： $W$ 和 $B$ ，其中 $W = W ^ { t }$ ， $B { = } \operatorname { s g n } ( X W )$ 。  
a）对数据集 $X$ 进行归一化处理，并根据 $n _ { t }$ 从 $X$ 中切分出 $X _ { s } ^ { \prime }$ ，随机

初始化 $W ^ { t }$ 和 $V ^ { t }$ ，初始化 $\mathcal { Q } _ { s } ^ { \prime }$ 为一个单位矩阵，并计算初始的 $B _ { s } ^ { t }$ 和 $Y _ { s } ^ { t }$ 。

b）根据 $K$ 计算 $X _ { s } ^ { t }$ 中数据间的相似性矩阵 $S _ { i } ^ { t }$ 。  
c）根据式(11)和(13)分别更新 $W ^ { t }$ 和 $V ^ { t }$ 。  
d）根据式(16)更新 $B _ { e } ^ { t }$ 。  
e）根据式(22)迭代更新 $B _ { s } ^ { t }$ 。  
f）根据式(24)和(25)分别更新 $Y _ { s } ^ { t }$ 和 $\mathcal { Q } _ { s } ^ { t }$ 。  
g）设置 $X _ { e } ^ { t } = [ X _ { e } ^ { t } ; X _ { s } ^ { t } ]$ ， $B _ { e } ^ { t } = [ B _ { e } ^ { t } ; B _ { s } ^ { t } ]$ ， $Y _ { e } ^ { t } = [ Y _ { e } ^ { t } ; Y _ { s } ^ { t } ]$ ，并从 $X$ 中切分出下一次的 $X _ { s } ^ { t }$ 。  
h）重复步骤 ${ \bf b } ) { \bf - g } )$ 。

# 2 实验与分析

# 2.1 数据集

在这篇文章中，本文在两个公开可用的数据集上进行实验。为了更准确地模拟图像标签损失的情况，需要构造确定标签存在损失的数据集。首先，从数据集中筛选出具有特定标签数量以上的数据，建立实验所需的图像数据集和对应的标签集。然后，本文使用卷积神经网络VGG-16对图像数据进行特征提取，提取的特征维度为4096。同时，对图像对应的标签集进行编码，建立标签矩阵，为了模型计算相似度的需要，如果一个图像包含该标签，就把该标签所在位置标识为1，否则为-1。最后，像文献[21]那样考虑不完整标签率，随机丢弃训练数据 $\{ 0 \%$ . $20 \%$ ， $40 \%$ ， $60 \%$ ， $80 \% \}$ 的标签，分别建立这五种状态下的子数据集。

MIRFlicki $2 5 \mathrm { k }$ 数据集包含25000张图像数据和24个标签类别，本文筛选具有3个及3个以上标签数量的数据，总共筛选出17568张图像。在提取完图像特征和建立标签矩阵之后，再以 $\{ 0 \% , 2 0 \% , 4 0 \% , 6 0 \% , 8 0 \% \}$ 的比率随机丢弃标签，模拟数据标签丢失标签的情况。实验中，除了分析数据库的数量对实验结果影响的实验，对于其他的实验，本文从挑选出的17568个图像数据中随机选择12400个作为实验的数据集，其中10000个作为数据库用作训练，剩下的2400个图像数据用作查询集。

NUS-WIDE数据集包含269648张图像数据和81个标签类别，本文选择出现最多的21个类别作为标签。处理过程和MIRFlickr25k类似，总共筛选出57073张图像数据，并从中随机选择12100个作为实验的数据集，其中10000个作为数据库用作训练，剩下的2100个图像数据用作查询集。

# 2.2基准方法与评估指标

本文以一些前沿的在线哈希算法作为基准方法，包括BSODH，MIHASH，OKH，AdaptHash，SketchHash，HMOH和OHWEU。实验时，BLPOH和对比算法对比使用的数据集和数据集的标签损失率等设定完全一致，对于每个对比算法的参数，专门设定使其得到最好的效果。实验设备的操作系统为Windows10，CPU为R5-3600，内存为32G。当数据集是MIRFlicki ${ \boldsymbol { \cdot } } 2 5 \mathbf { k }$ 时，实验设置参数 $\alpha = \beta = 0 . 8$ ， $\varsigma = 0 . 9$ ， $\lambda = 0 . 6$ 流数据量为200，最近邻 $K = 1 0$ ， $\eta _ { s } = 0 . 4$ ， $\eta _ { d } = 1$ 。当数据集是NUS-WIDE时，实验设置参数 $\alpha = \beta = \varsigma = 0 . 9$ ， $\lambda = 0 . 1$ ，流数据量为200，最近邻 $K = 1 2$ ， $\eta _ { s } = 0 . 2$ ， $\eta _ { d } = 1$ 。本文使用平均精度均值(MeanAveragePrecision,MAP)作为度量的标准来评估这些算法的性能。

# 2.3实验结果

# 2.3.1MAP对比

表2\~4和图2展示了BLPOH和对比算法在数据集为MIRFlickr25k和NUS-WIDE,并且标签损失率分别为 $\{ 0 , 2 0 \%$ $40 \%$ + $60 \%$ ， $80 \%$ 时不同哈希码位数下的MAP结果对比和变化曲线。

如表2所示，在数据集MIRFlickr25K的不同标签损失率下，BLPOH的MAP始终高于其他所有对比算法。其中，HMOH和OHWEU的整体效果和BLPOH较为接近，AdaptHash 的整体效果相比最差。在NUS-WIDE 数据集下，当标签损失率为0的时候，BLPOH的MAP高于除HMOH外的其他对比算法，当标签损失率继续上升时，BLPOH的MAP超过包括HMOH在内的所有对比算法，证明了BLPOH的优越性能。从和HMOH在数据集NUS-WIDE下的结果中可以看出，当没有标签损失时，HMOH的MAP高于BLPOH，当标签损失率上升到 $20 \%$ 及以后时，BLPOH的MAP超过了HMOH，证明了BLPOH对抗标签损失的有效性。在实际应用中，标签的损失程度可能会非常严重，BLPOH更适用于实际情况。

图2给出了BLPOH和对比算法在数据集MIRFlicki $2 5 \mathrm { k }$ 和NUS-WIDE不同哈希码位数下的MAP随标签损失率上升的变化图。从中可以看出，在不同数据集和不同哈希码位数的情况下，BLPOH的MAP的下降更加平缓，且多数情况下总能保持更高的水平。

# 2.3.2关键参数灵敏度分析

本小节分析标签类别相似性权重参数 $\eta _ { s }$ 和 $\eta _ { d }$ 对实验结果的影响。在实验中，设置 $\eta _ { d } = 1$ ，并通过改变 $\eta _ { s } / \eta _ { d }$ 的大小来分析它们对实验结果的影响。从图3(a)可以看出，在数据集MIRFlickr25k上，当 $\eta _ { s } / \eta _ { d }$ 的值介于(0.3,0.5)时，MAP出现最大值，当 $\eta _ { s } / \eta _ { d }$ 在0.8以后MAP大幅下降，当 $\eta _ { s } / \eta _ { d } = 1$ 时MAP的值最低，此时表示的是没有使用标签类别相似性平衡算法的MAP，最终本文选取 $\eta _ { s } = 0 . 4$ ， $\eta _ { d } = 1$ 作为实际参数值。如图3(b)所示，在数据集NUS-WIDE上， $\eta _ { s } / \eta _ { d } = 0 . 2$ 时MAP最高，当 $\eta _ { s } / \eta _ { d } = 1$ 时MAP最低，最终选取 $\eta _ { s } = 0 . 2$ ， $\eta _ { d } = 1$ 作为实际参数值。从标签类别相似性权重比值在两种数据集上的表现可以看出，没有使用标签类别相似性平衡的MAP总是低于使用标签类别相似性平衡的，这证明了标签类别相似性平衡对BLPOH的有效性。

表2在MIRFlickr25k和NUS-WIDE上且哈希码位数为32时的MAPTab.2The MAPofMIRFlickr25k andNUS-WIDE when the hash bits is 32  

<html><body><table><tr><td rowspan="2">方法</td><td colspan="6">MIRFlickr25k</td><td colspan="4">NUS-WIDE</td></tr><tr><td>0</td><td>20%</td><td>40%</td><td>60%</td><td>80%</td><td>0</td><td>20%</td><td>40%</td><td>60%</td><td>80%</td></tr><tr><td>BSODH</td><td>0.716</td><td>0.714</td><td>0.636</td><td>0.503</td><td>0.260</td><td>0.843</td><td>0.769</td><td>0.662</td><td>0.496</td><td>0.282</td></tr><tr><td>MIHASH</td><td>0.836</td><td>0.736</td><td>0.553</td><td>0.370</td><td>0.207</td><td>0.850</td><td>0.714</td><td>0.534</td><td>0.347</td><td>0.201</td></tr><tr><td>OKH</td><td>0.797</td><td>0.692</td><td>0.532</td><td>0.363</td><td>0.199</td><td>0.855</td><td>0.719</td><td>0.535</td><td>0.357</td><td>0.204</td></tr><tr><td>AdaptHash</td><td>0.783</td><td>0.672</td><td>0.523</td><td>0.352</td><td>0.205</td><td>0.856</td><td>0.719</td><td>0.540</td><td>0.359</td><td>0.203</td></tr><tr><td>SketchHash</td><td>0.803</td><td>0.697</td><td>0.544</td><td>0.373</td><td>0.216</td><td>0.869</td><td>0.736</td><td>0.553</td><td>0.369</td><td>0.211</td></tr><tr><td>HMOH</td><td>0.837</td><td>0.767</td><td>0.653</td><td>0.523</td><td>0.267</td><td>0.883</td><td>0.799</td><td>0.683</td><td>0.530</td><td>0.279</td></tr><tr><td>OHWEU</td><td>0.789</td><td>0.737</td><td>0.647</td><td>0.506</td><td>0.306</td><td>0.869</td><td>0.792</td><td>0.680</td><td>0.520</td><td>0.292</td></tr><tr><td>BLPOH</td><td>0.872</td><td>0.812</td><td>0.714</td><td>0.562</td><td>0.336</td><td>0.881</td><td>0.802</td><td>0.703</td><td>0.532</td><td>0.303</td></tr></table></body></html>

Tab.3TheMAPofMIRFlickr25k and NUS-WIDE when the hash bits is 64   
表4在MIRFlickr25k和NUS-WIDE上在哈希码位数为128时的MAP  

<html><body><table><tr><td rowspan="2">方法</td><td colspan="5">MIRFlickr25k</td><td colspan="5">NUS-WIDE</td></tr><tr><td>0</td><td>20%</td><td>40%</td><td>60%</td><td>80%</td><td>0</td><td>20%</td><td>40%</td><td>60%</td><td>80%</td></tr><tr><td>BSODH</td><td>0.717</td><td>0.725</td><td>0.642</td><td>0.494</td><td>0.261</td><td>0.842</td><td>0.765</td><td>0.651</td><td>0.501</td><td>0.279</td></tr><tr><td>MIHASH</td><td>0.851</td><td>0.734</td><td>0.576</td><td>0.396</td><td>0.229</td><td>0.858</td><td>0.741</td><td>0.559</td><td>0.356</td><td>0.205</td></tr><tr><td>OKH</td><td>0.810</td><td>0.699</td><td>0.552</td><td>0.373</td><td>0.220</td><td>0.856</td><td>0.726</td><td>0.546</td><td>0.362</td><td>0.208</td></tr><tr><td>AdaptHash</td><td>0.769</td><td>0.661</td><td>0.513</td><td>0.357</td><td>0.204</td><td>0.855</td><td>0.720</td><td>0.537</td><td>0.357</td><td>0.203</td></tr><tr><td>SketchHash</td><td>0.809</td><td>0.704</td><td>0.551</td><td>0.379</td><td>0.220</td><td>0.872</td><td>0.740</td><td>0.557</td><td>0.372</td><td>0.213</td></tr><tr><td>HMOH</td><td>0.852</td><td>0.781</td><td>0.667</td><td>0.534</td><td>0.272</td><td>0.885</td><td>0.803</td><td>0.691</td><td>0.532</td><td>0.274</td></tr><tr><td>OHWEU</td><td>0.806</td><td>0.750</td><td>0.663</td><td>0.524</td><td>0.311</td><td>0.873</td><td>0.805</td><td>0.694</td><td>0.531</td><td>0.296</td></tr><tr><td>BLPOH</td><td>0.873</td><td>0.817</td><td>0.720</td><td>0.568</td><td>0.342</td><td>0.882</td><td>0.812</td><td>0.709</td><td>0.534</td><td>0.311</td></tr></table></body></html>

表3在MIRFlickr25k和NUS-WIDE上且哈希码位数为64时的MAP  
Tab.4The MAPofMIRFlickr25k andNUS-WIDE when the hashbits is128   

<html><body><table><tr><td rowspan="2">方法</td><td colspan="5">MIRFlickr25k</td><td colspan="5">NUS-WIDE</td></tr><tr><td>0</td><td>20%</td><td>40%</td><td>60%</td><td>80%</td><td>0</td><td>20%</td><td>40%</td><td>60%</td><td>80%</td></tr><tr><td>BSODH</td><td>0.715</td><td>0.716</td><td>0.637</td><td>0.499</td><td>0.258</td><td>0.847</td><td>0.771</td><td>0.658</td><td>0.502</td><td>0.278</td></tr><tr><td>MIHASH</td><td>0.857</td><td>0.751</td><td>0.593</td><td>0.405</td><td>0.235</td><td>0.854</td><td>0.714</td><td>0.550</td><td>0.366</td><td>0.206</td></tr><tr><td>OKH</td><td>0.820</td><td>0.713</td><td>0.558</td><td>0.384</td><td>0.222</td><td>0.857</td><td>0.725</td><td>0.549</td><td>0.366</td><td>0.210</td></tr><tr><td>AdaptHash</td><td>0.775</td><td>0.684</td><td>0.514</td><td>0.345</td><td>0.201</td><td>0.855</td><td>0.721</td><td>0.539</td><td>0.359</td><td>0.205</td></tr><tr><td>SketchHash</td><td>0.817</td><td>0.713</td><td>0.559</td><td>0.385</td><td>0.224</td><td>0.875</td><td>0.745</td><td>0.562</td><td>0.376</td><td>0.215</td></tr><tr><td>HMOH</td><td>0.854</td><td>0.781</td><td>0.662</td><td>0.536</td><td>0.274</td><td>0.886</td><td>0.811</td><td>0.689</td><td>0.533</td><td>0.278</td></tr><tr><td>OHWEU</td><td>0.822</td><td>0.759</td><td>0.670</td><td>0.537</td><td>0.315</td><td>0.882</td><td>0.812</td><td>0.703</td><td>0.534</td><td>0.308</td></tr><tr><td>BLPOH</td><td>0.876</td><td>0.817</td><td>0.725</td><td>0.573</td><td>0.346</td><td>0.885</td><td>0.817</td><td>0.712</td><td>0.539</td><td>0.316</td></tr></table></body></html>

1. 0 BLPOH 1. 0 BLPOH 1. 0 BLPOH0.9 BSHASH 0.9 BSHASH 0.9 BSHSAdersh OKH 08 Athash 8.7 AatashHMOH HMOH HMOHOHWEU OHWEL OHWEU0.2 0.2 0.20.1 0.1 0.10.0 0.0 0.00 20 40 60 80 0 20 40 60 80 0 20 40 60 80标签损失率(%) 标签损失率(%) 标签损失率(%)(a)MIRFlickr25k32位哈希码的MAP(b)MIRFlickr25k 64 位哈希码的 MAP (c)MIRFlickr25k128 位哈希码的 MAP1.0 1. 0 1. 0BLPOH BLP0H BLPOH0.9 BSODH 0.9 BSODH 0.9 BSODHMIHASH MIHASH MIHASH0 AdaptHash 8 \*AdaptHash 0 AdaptHashSketchHash SketchHash SketchHashOHWEU HMOH OHWHUOHWEU08 00.2 0.2 0.20.1 0.1 0.10.0 0.0 0.00 20 40 60 80 0 20 40 60 80 0 20 40 60 80标签损失率(%) 标签损失率(%) 标签损失率(%)(d)NUS-WIDE32位哈希码的MAP (e)NUS-WIDE64位哈希码的MAP (f)NUS-WIDE128位哈希码的MAP

![](images/f8366bf8da6e58ba265c4c6177c412b1b1d5921226d143b38b934383a4ff5909.jpg)  
图2标签损失率对实验结果的影响  
Fig.2The effect of label loss rate on results   
图3标签类别相似性权重比值对实验结果的影响  
Fig.3The effect of label category similarity weight ratio on results 2.3.3数据库样本数量对实验结果的影响 BLPOH是一种基于在线哈希的改进算法，为了测证

BLPOH作为在线哈希算法的检索性能，本文分析了BLPOH的实验结果随数据库样本增加的变化情况。设置MIRFlickr25k和NUS-WIDE查询集的数量分别为2400和2100，剩下的用作训练。如图4(a)所示，数据集为MIRFlickr25k，当数据库的样本数量为2000时，BLPOH的MAP较其他五种情况最差，当样本数量在4000以后，MAP逐渐增加，当样本数量为10000 时，BLPOH的MAP基本趋于稳定。如图4(b)所示，BLPOH在NUS-WIDE数据集下的MAP从数据库样本数量为2000开始逐渐上升，在样本数量为8000时趋于稳定。

# 2.3.4标签类别相似性平衡算法对实验结果的影响

在算法优化过程中，本文把优化预测标签矩阵 $Y _ { s } ^ { t }$ 和标签类别相似性矩阵 $\mathcal { Q } _ { s } ^ { \prime }$ 转换为求解对应的线性方程组，即式(23)和(24)。在实际编程计算中，本文使用预条件共轭梯度法(PreconditionalConjugate Gradient,PCG)对式(23)和(24)进行求解。

本节通过PCG 的收敛位置来分析标签类别相似性平衡对BLPOH的影响。以NUS-WIDE 数据集下的标签预测和求解标签类别相似性矩阵为例。如图5(a)所示，在每次数据流到来并进行标签预测时，使用标签类别相似性平衡算法总能比未使用标签类别相似性平衡算法收敛的更快，且每次收敛的位置变化较小，表现更稳定。同样地，如图5(b)，在求解标签类别相似性矩阵时，使用标签类别相似性平衡算法相比未使用标签类别相似性平衡算法的表现也相对稳定一些。

![](images/97191c32489039e5f71d6b48f941dc78280d40332e558d374d2dd3589bd8da7e.jpg)  
图4不同样本数量对实验结果的影响  
图5标签类别相似性平衡对不同求解过程收敛位置的影响Fig.5Influence of label categories similarity balance on convergencelocation of different solution processes

200 100180 使用标签类别相似性平衡 90 –使用标签类别相似性平衡160 未使用标签类别相似性平衡 80 未使用标签类别相似性平衡140 70  
120 60  
00 50收 4060 3040 2020 100 01 6 11 16 212631364146 1 6 11 16 212631 364146数据流次序 数据流次序(a)标签预测 (b)求解标签类别相似性矩阵

本文提出了改进的在线哈希算法，流式地读取数据，以在线的方式训练和更新模型，使得算法模型不受制于数据集

# 2.3.5图像实例的检索效果

为了展现BLPOH的实际检索效果，本文和BSODH在数据集MIRFlickr25K中的图像实例检索效果进行对比。

实验时，从MIRFlickr25K数据集中选取一张图像，根据相同条件下训练出的模型返回前5张最相似的图像。结果如图6所示，图像下的文本为该图像的标签。根据BLPOH训练的模型返回了5张人像，而根据BSODH训练的模型返回了4 张人像和一张动物的图像。BLPOH 的检索效果明显优于BSODH。

的大小，并使模型契合当前的数据信息，使模型具有良好的实时性。并且，让旧数据的信息监督哈希函数的在线更新，提升哈希函数对旧数据的兼容性。此外，考虑到现实图像数据标签存在缺失的问题，加入标签预测模块，并且新颖地提出标签类别相似性平衡算法，指导标签的预测，使得预测的标签更加精确，也提升了图像标签相似度的准确性，进一步提升模型精度。此外，本文的标签预测模块不仅能让模型能够很好地对抗标签缺失，并且在标签损失率不断上升时，也能够使模型的性能以较平缓的速度下降，在标签存在缺失的在线图像检索任务中具有良好的应用前景。然而，本文的标签预测模型比较单一，模型的健壮性并不能令人非常满意，所以在今后的工作中考虑加入集成学习的思想提升模型的健壮性。

# 参考文献：

![](images/ffaaffdd425122a1ef3c8b02d672c9bbc624a6a0cad5aa34f7b6cfa4d1857b10.jpg)  
Fig.4The effect of different sample sizes on results   
Fig.6Instance retrieval ofthe algorithm in this paperand bsodh in mir flickr25k   
图6blpoh 和bsodh 在 mir flickr25k 中的实例检索

[1]郭一村，陈华辉．在线哈希算法研究综述[J].计算机应用,2021,41 (04):1106-1112.(Guo Yicun,Chen Huahui. Survey on online hashing algorithm [J]. Journal of Computer Applications,2021,41 (04):1106- 1112.)   
[2]Lin Guosheng,Shen Chunhua,Shi Qinfeng,et al.Fast supervised hashing with decision trees for high-dimensional data [C]// Proc of the 27th IEEE Conference on Computer Vision and Pattern Recognition.Los Alamitos,CA:IEEE Computer Society,2014:1963-1970.   
[3]Gionis A,Indyk P, Motwani R.Similarity search in high dimensions via hashing [C]// Proc of the 25th Very Large Data Base Conference. San Francisco,CA: Morgan Kaufmann Publishers,1999:518-529.   
[4]Weiss Y,Fergus R,Torralba A.Multidimensional spectral hashing [C]// Proc of the l2th European Conference on Computer Vision.Berlin: Springer Verlag,2012: 340-353.   
[5]Wang Jun, Kumar S, Chang SF.Semi-supervised hashing for large-scale search[J]. IEEE Trans on Patern Analysis and Machine Intellgence, 2012,34 (12): 2393-2406.   
[6]Liu Wei, Mu Cun, Kumar S,et al. Discrete graph hashing[C]//Proc of the 27th International Conference on Neural Information Processing Systems. Cambridge,MA: MIT Press,2014: 3419-3427.   
[7]Shen Fumin,Shen Chunhua,Liu Wei,et al. Supervised discrete hashing [C]//Proc of the 28th IEEE Conference on Computer Vision and Pattern Recognition.Los Alamitos,CA: IEEE Computer Society,2015:37-45.   
[8]Bombara G,Belta C.Offline and online learning of signal temporal logic formulae using decision trees [J].ACM Trans on Cyber-Physical Systems, 2021,5 (3): 1-23.   
[9]Lu Xu, Zhu Lei,Cheng Zhiyong,et al.Flexible online multi-modal hashing for large-scale multimedia retrieval [Cl//Proc of the 27th ACM International Conference on Multimedia.New York:Association for Computing Machinery,2019:1129-1137.   
[10] Huang Longkai, Yang Qiang,Zheng Weishi. Online hashing [C]//Proc of the 23rd International Joint Conference on Artificial Intelligence. Menlo Park,CA:AAAI Press,2013:1422-1428.   
[11] CakirF,Bargal SA,Sclaroff S.Online supervised hashing [J]. Computer Vision and Image Understanding,2017,156:162-173.   
[12] Cakir F,Sclaroff S.Adaptive hashing for fast similarity search [C]//Proc of the 15th IEEE International Conference on Computer Vision.NW Washington,DC:IEEE Computer Society,2015:1044-1052.   
[13] Leng Cong,Wu Jiaxiang,Cheng Jian,et al. Online sketching hashing [C]//Proc of the 28th IEEE Conference on Computer Vision and Pattern Recognition. Los Alamitos,CA: IEEE Computer Society,2015:2503- 2511.   
[14] CakirF,He Kun,Adel Bargal S,et al. Mihash: Online hashing with

# 3 结束语

mutual information [C]//Proc of the 16th IEEE International Conference on Computer Vision.NW Washington,DC:IEEE Computer Society, 2017: 437-445.   
[15] Lin Mingbao,Ji Rongrong,Liu Hong,et al.Towards optimal discrete online hashing with balanced similarity[C]// Proc of the 33rd Association for the Advancement of Artificial Intelligence Conference on Artificial Intelligence.Palo Alto,CA:AAAIPress,2019:8722-8729.   
[16]Weng Zhenyu,Zhu Yuesheng. Online hashing with efficient updating of binary codes [C]//Proc of the 34th Association for the Advancement of Artificial Intelligence Conference on Artificial Intelligence.Palo Alto, CA:AAAIPress,2020:12354-12361.   
[17]Lin Mingbao,Ji Rongrong,Liu Hong,et al.Hadamard matrix guided online hashing[J].International Journal of Computer Vision,2O20,128 (8): 2279-2306.   
[18] Lin Mingbao,Ji Rongrong,Liu Hong,et al. Supervised online hashing via hadamard codebook learning $[ \mathrm { C } ] / \hbar$ Proc of the 26th ACM International Conference on Multimedia.New York:Association for Computing Machinery,2018:1635-1643.   
[19]王琳，张素兰，杨海峰．基于CNN和加权贝叶斯的最近邻图像标注 方法[J].计算机技术与发展,2021,31(10):63-69.(Wang Lin,Zhang Sulan,Yang Haifeng.A nearest neighbor image annotation method based on CNN and weighted bayesian [J].Computer Technology and Development,2021,31(10): 63-69.)   
[20] Jiang Qingyuan,Li Wujun.Deep cross-modal hashing[C]// Proc of the 30th IEEE Conference on Computer Vision and Pattern Recognition.Los Alamitos,CA:IEEE Computer Society,2017:3232-3240.   
[21] Dong Haochen,Li Yufeng,Zhou Zhihua.Learning from semi-supervised weak-label data [C]//Proc of the 32nd Association for the Advancement of Artificial Intelligence Conference on Artificial Intelligence.Palo Alto, CA: AAAI Press,2018:2926-2933.   
[22] Norouzi M,Punjani A,Fleet DJ.Fast search in hamming space with multi-index hashing [C]// Proc of the 25th IEEE Conference on Computer Vision and Pattern Recognition.Los Alamitos,CA:IEEE Computer Society,2012:3108-3115.   
[23] Kang Wangcheng,Li Wujun,Zhou Zhihua.Column sampling based discrete supervised hashing [C]//Proc of the 3Oth Association for the Advancement of Artificial Intelligence Conference on Artificial Intelligence.Palo Alto,CA:AAAIPress,2016:1230-1236.