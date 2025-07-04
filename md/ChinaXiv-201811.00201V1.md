# 融合高光谱影像三维空谱特征的子空间聚类算法\*

李文洲a，邓秀勤a，刘富春b(广东工业大学a.应用数学学院;b.计算机学院，广州 510006)

摘要：为提高高光谱遥感影像的聚类精度，将三维空谱特征和子空间聚类算法相结合，提出一种新的稀疏子空间聚类模型，在关注高光谱影像的光谱信息的同时，也关注空间上下文信息。首先提取高光谱影像像素点的三种三维空谱特征，然后通过特征对子空间聚类模型的系数矩阵进行加权，使得像素点可被与它最为相似的像素点稀疏表示，从而获得更好的系数矩阵，最后由系数矩阵通过谱聚类获得更好的聚类结果。算法对四个经典高光谱数据集进行实验，并将实验结果与六种聚类算法进行比较，结果表明，所提出的3DF-SSC算法在四个数据集上获得的聚类精度都比其他算法要高，对于同样是利用三维空谱特征的 M3DF算法，3DF-SSC 算法最高能提高 $8 . 6 2 \%$ 的精度，而与同样是利用空间上下文信息对子空间聚类算法进行改进的L2-SSC 算法和 SS-LRSC 算法相比，最高能提高 $2 5 . 1 8 \%$ 的精度。

关键词：高光谱遥感影像；三维空谱特征；子空间聚类；空间上下文信息 中图分类号：TP751.1 doi: 10.19734/j.issn.1001-3695.2018.07.0482

# Subspace clustering algorithm fused three-dimensional spatial spectral features of hyperspectral images

Li Wenzhoua, Deng Xiuqina†, Liu Fuchunb (a.SchoolofAppliedMathematics,b.SchoolofComputersGuangdong UniversityofTechnologyGuangzhou510o6China)

Abstract: In order to improve the clustering accuracy of hyperspectral images,this paper proposed anew sparse subspace clustering model combined three-dimensional spatial spectral features with subspaceclustering algorithms.While focusing on thespectralinformatioofyperspectralimages,italsopaidatentiontospatialontextiformation.Firstlyxtractingtree kinds of thre-dimensionalspatialspectralfeatures from thepixelsofthe hyperspectral image.Thenthe features weighted the coeffcient matrixofthesubspaceclustering modelsothatthpixel pointscouldsparselyrepresent thepixelpointtowhich they aremostsimilar,terebyobtainingthebettercoeficient matrix.inally,itusedtecoeficientmatrix toobtainbettrlustering resultswith spectral clustering.Thealgorithm experimented on four clasical hyperspectral datasets，and compared the experimental results with six clustering algorithms.Theresults show that the proposed algorithmachieves higher clustering accuracy on the four datasets than the other algorithms.The algorithm can achieve at most $8 . 6 2 \%$ accuracy than the algorithms based 3D spatial spectral features like $\mathrm { M } 3 \mathrm { D F } ^ { 3 }$ algotithm and 3DF-SSC algorithm, and at most $2 5 . 1 8 \%$ than the algorithms which improvethe subspace clustering algorithmbyusing spatial context information likeL2-SSCalgorithmand SS-LRSCalgorithm. Key words: hyperspectral images;thre-dimensional spatial spectralfeatures;subspaeclustering;spatialcontextinformation

# 0 引言

相对于传统的多光谱数据，高光谱遥感影像提供了丰富的光谱信息，拥有数量庞大的细微光谱特征，因此解决了光谱信息不足的问题，提高了地物目标的区分和识别能力[1]。但由于在监督分类中，对高维高光谱遥感影像的大量训练样本进行标记具有一定的困难，因而K-means 聚类[2]和谱聚类(SC)[3]等无监督聚类算法被广泛应用于高光谱遥感影像的聚类中。

近年来，稀疏子空间聚类(sparse subspace clustering,SSC)算法[4也被应用于高光谱遥感影像的聚类中，并显示出巨大的潜力。SSC算法是一种基于谱聚类的数据聚类框架，它可利用数据的稀疏表示系数构造相似度矩阵，然后利用谱聚类方法得到数据的子空间聚类结果，然而稀疏子空间聚类在聚类过程中却仅利用了光谱信息，没有考虑空间上下文信息，导致其最终的聚类图像会出现大量椒盐噪声[5]。对此，Zhai 等人[提出L2-SSC算法，融入邻域信息对系数进行TV（totalvariation)约束，从而提高聚类精度。为了强化高光谱遥感影像的空间信息，Zhu等人[提出高光谱影像的三维空谱特征提取方法，并基于稀疏决策融合算法提出M3DF算法对高光谱影像进行地物分类。而Xu 等人[8提出的SS-LRSC算法则是利用空间信息对子空间聚类算法求得的系数矩阵进行调制，从而获得了更高的聚类精度。

为了更有效地利用高光谱遥感影像的空间上下文信息，本文提出一种融合高光谱影像三维空谱特征的子空间聚类算法(three dimension spatial feature-sparse subspace clustering,3DF-SSC)，通过提取像素的三维空谱特征求出像素之间的相似度，在子空间聚类的稀疏度量中引入与相似度成反比的权重，迫使相似的像素尽可能参与到数据的自表示当中，提高聚类的准确性。实验结果表明，本文提出的3DF-SSC算法对于四个经典的高光谱数据集都能获得准确可靠的聚类结果。

# 1 稀疏子空间聚类

稀疏子空间聚类是一种基于稀疏表示和谱聚类的子空间聚类方法，基本思想是对给定的一组高维数据，寻找其稀疏表示系数，由此构造相似度矩阵，再利用谱聚类方法，如规范化割[9]得到数据聚类结果。

在高光谱遥感影像(hyperspectral image,HSI) $\pmb { I } \in \pmb { R } ^ { M \times N \times D }$ （204中，首先对像素按波段 $D$ 进行列化，将三维的高光谱影像 $I$ 映射到二维空间 $Y = [ y _ { 1 } , y _ { 2 } , \cdots , y _ { _ { M N } } ] \in R ^ { D \times M N }$ ，然后假设来自 $Y$ 的所有像素都是属于 $\mathbf { \xi } _ { l }$ 个子空间的并 $\textstyle \bigcup _ { i = 1 } ^ { l } S _ { i }$ ,每个子空间对应一个特定的陆地覆盖类型，最后子空间聚类利用像素的稀疏自我表示将每个像素表示为其他像素的线性组合，从而将这些像素聚类为不同的类。具体模型为

$$
\begin{array} { r } { \underset { C , E } { \operatorname* { m i n } } \left\| C \right\| _ { 1 } + \lambda \left\| E \right\| _ { F } ^ { 2 } \quad } \\ { s . t . \quad Y = Y C + E , d i a g ( C ) = 0 } \end{array}
$$

其中： $Y \in { \boldsymbol { R } } ^ { D \times M N }$ 为二维HSI矩阵，M、N、 $D$ 分别为高光谱影像的长、宽和波段数， $C \in R ^ { M N \times M N }$ 为稀疏表示系数矩阵，$E \in R ^ { D \times M N }$ 为误差矩阵， $\lambda > 0$ 为平衡参数。

在MATLAB 中使用 ADMM(alternating direction method ofmultipliers)[10]法求解模型式(1)可得稀疏表示系数矩阵 $C$ ，然后由矩阵 $c$ 通过式(2)构造邻接矩阵 $W \in R ^ { M N \times M N }$ ， $W$ 中的元素表示两个像素之间的相似度[1I][2]。

$$
W = \left| C \right| + \left| C \right| ^ { T }
$$

最后通过Ncut(normalizedcuts)算法[13]由邻接矩阵 $W$ 得到最终的聚类结果。

因为子空间聚类模型对噪声较为敏感，所以文献[14]提出加权稀疏子空间表示模型，引入权重使得数据尽可能由与它最为相似的数据线性表示，首先利用高斯相似度函数对系数进行加权，即式(3)。

$$
G _ { i j } = \exp \left( - { \frac { \left\| y _ { i } - y _ { j } \right\| _ { 2 } ^ { 2 } } { \sigma ^ { 2 } } } \right)
$$

其中 $y _ { i }$ 和 $y _ { j }$ 是两个数据样本，建立加权稀疏表示模型：

$$
\operatorname* { m i n } _ { { \boldsymbol { c } } , { \boldsymbol { E } } } \sum _ { j \neq i } { \frac { 1 } { G _ { i j } } } \Bigl | C _ { i j } \Bigr | + \lambda \bigl \| { \boldsymbol { E } } \bigr \| _ { 2 }
$$

$$
\begin{array} { r } { s . t . \quad Y = Y C + E , d i a g ( C ) = 0 } \end{array}
$$

# 2 高光谱遥感影像的三维空谱特征

高光谱遥感影像包含了关于地表物质的丰富空间、辐射和光谱三重信息，因此近年来也有许多高光谱遥感影像的特征提取方法，但是现有的空谱特征提取方法大多是将不同波段的空间特征机械地组合起来，为了充分利用高光谱遥感影像空谱结构中的上下文信息，文献[15]提出了高光谱遥感影像的三维空谱特征的提取方法，如三维LBP空谱特征、三维空谱开特征和三维空谱闭特征。具体特征提取公式如下：

给定高光谱遥感影像 HSI: $\pmb { I } \in \pmb { R } ^ { M \times N \times D }$ ，像素点 $k$ 的3DLBP空谱特征为

$$
3 D L B P _ { k } = \left\{ \begin{array} { l l } { \displaystyle \sum _ { P = 0 } ^ { P - 1 } s ( I _ { p } - I _ { c } ) } & { i f \ \Gamma ( 3 D L B P _ { P } ) \leq P } \\ { P + 1 } & { \ i f \ \vec { \subset } \vec { \Sigma } } \end{array} \right.
$$

其中：

$$
s ( x ) = { \left\{ \begin{array} { l l } { 1 } & { \left| x \right| \geq \sigma } \\ { 0 } & { \left| x \right| < \sigma } \end{array} \right. }
$$

$$
\Gamma ( 3 D L B P _ { P } ) = \sum _ { i , j = 0 } ^ { P - 1 } \left| s ( I _ { i } - I _ { c } ) - s ( I _ { j } - I _ { c } ) \right|
$$

其中： $I _ { i } ( i = 0 , \cdots , P - 1 )$ 是以像素点 $k$ 为中心的外接球半径为 1的正八面体的第 $i$ 个采样点的像素值， $P$ 为采样点的数量。为了实现灰度不变性，通过八面体邻域的中心点的像素值对采样点执行二值化，从而获取局部空谱结构的三维局部二值模式，如式(5)所示，其中 $I _ { c }$ 为中心点， $\sigma$ 为判断阈值。即若顶点位置的像素值与中心点的像素值的差 $x$ 大于 $\sigma$ ，将其设为1，否则设为0。

像素点 $k$ 的三维空谱开特征为

$$
3 D O P _ { k } = \operatorname* { m a x } ( \operatorname* { m i n } _ { x , y , z } ( I ( x , y , z ) \in Q ( x _ { 0 } , y _ { 0 } , z _ { 0 } ) ) )
$$

像素点 $k$ 的三维空谱闭特征为

$$
3 D C P _ { k } = \operatorname* { m i n } ( \operatorname* { m a x } _ { x , y , z } ( I ( x , y , z ) \in Q ( x _ { 0 } , y _ { 0 } , z _ { 0 } ) ) )
$$

其中： $I ( x _ { 0 } , y _ { 0 } , z _ { 0 } )$ 是位于 $( x _ { 0 } , y _ { 0 } , z _ { 0 } )$ 处的像素值。 $Q ( x _ { 0 } , y _ { 0 } , z _ { 0 } )$ 是高光谱影像HSI中以像素点 $( x _ { 0 } , y _ { 0 } , z _ { 0 } )$ 为中心的立方体集合。

# 3 融合高光谱三维空谱特征的子空间聚类算法

由于基于子空间聚类算法的高光谱遥感影像的地物区分仅利用了影像的光谱信息，因此本文将三维空谱特征与子空间聚类算法进行融合，利用影像的光谱信息的同时，还利用像素的空间上下文信息，使得每个像素都可以被与它最为相似的像素稀疏表示，提高子空间聚类精度。

首先对高光谱遥感影像中的每个像素点 $k$ ,量化以像素点$k$ 为中心的三维局部正八面体领域的空谱结构，通过八面体邻域的中心点的像素值对采样点执行二值化，从而统计每个像素点 $k$ 的八面体邻域内的3DLBP特征： $3 D L P _ { k }$ ，然后对以像素点$k$ 为中心的立方体集合进行膨胀、腐蚀、开启和闭合运算，提取每个像素点 $k$ 的三维空谱开特征和闭特征： $3 D O P _ { k }$ 、 $3 D C P _ { k }$ 。将三种特征分别记做 $X _ { 1 ^ { \setminus } } \ X _ { 2 ^ { \setminus } } \ X _ { 3 }$ ，通过高斯函数计算每两个像素点之间的相似度为：

$$
G _ { i j } = \exp ( - \frac { \big \| ( X _ { 1 } ) _ { p } - ( X _ { 1 } ) _ { q } \big \| _ { 2 } ^ { 2 } + \big \| ( X _ { 2 } ) _ { p } - ( X _ { 2 } ) _ { q } \big \| _ { 2 } ^ { 2 } + \big \| ( X _ { 3 } ) _ { p } - ( X _ { 3 } ) _ { q } \big \| _ { 2 } ^ { 2 } } { \mu ^ { 2 } } )
$$

其中： $\left( X _ { n } \right) _ { p }$ 和 $\left( X _ { n } \right) _ { q }$ 分别为像素 $p$ 和 $\boldsymbol { q }$ 的第 $n$ 个特征，$n = 1 , 2 , 3$ 。

最后用 $1 / G _ { i j }$ 对系数的 $l _ { \mathrm { { l } } }$ 范数进行加权，使得相似度越大的像素点权重越小，相似度越小的像素点权重越大，让像素点尽可能被最相似的像素线性表示，具体模型如下：

$$
\operatorname* { m i n } \sum _ { j \neq i } \frac { 1 } { G _ { j i } } \big | C _ { j i } \big | + \lambda \big | \big | Y C _ { i } - Y _ { i } \big | \big | _ { 2 }
$$

$$
s . t . \quad C _ { i i } = 0 , i = 1 , 2 , \cdots , M N
$$

3DF-SSC 算法步骤如下：输入： $H S I : I \in R ^ { M \times N \times D }$ ，聚类数 $l$ 。a)对高光谱影像 $I$ 进行降维，得 $Y \in { \cal R } ^ { D \times M N }$ ·，b)提取Y中每个像素的三种特征，3DLBP: $X _ { 1 } = [ x _ { 1 1 } , \cdots , x _ { 1 D } ]$ 、  
3DOP: $X _ { _ 2 } = [ x _ { _ { 2 1 } } , \cdots , x _ { _ { 2 D } } ]$ 和 3DCP: $X _ { \scriptscriptstyle 3 } = [ x _ { \scriptscriptstyle 3 1 } , \cdots , x _ { \scriptscriptstyle 3 D } ]$ ·c)由式(10)计算像素之间的相似度;d)求解模型(11),得子空间表示系数矩阵 $c$ ·e)由式(2)计算相似度矩阵 $W$ ，并利用Ncut算法得到聚类结  
果。输出：图像聚类结果。

# 4 实验结果与分析

为了评估算法的聚类精度，本文将对四个经典高光谱数据集:Salinas-A、the Pavia Center、Pavia University 和 Indian Pines[16]进行实验测试。Salinas-A高光谱遥感影像由AVIRIS传感器在California的SalinasValley获取，数据集包含224个波段图像，每个波段图像大小为 $8 6 ^ { * } 8 3$ ，分为6类地物；PaviaCenter高光谱遥感影像由ROSIS-03传感器在意大利的帕维亚中心获取，简称PaviaC。数据集包含102个波段图像，每个波段图像大小为 $1 0 9 6 ^ { * } 7 1 5$ ，总共148152个标记样本，分为9类地物。实验采用其中尺寸为 $1 2 0 ^ { * } 1 2 0$ ，包含6类地物的高光谱图像进行测试；PaviaUniversity高光谱遥感影像由ROSIS-3传感器采集于意大利帕维亚大学周边的帕维亚大学，拥有103个波段图像，每个波段图像大小为 $6 1 0 ^ { * } 3 4 0$ ，分为9类地物。实验采用其中尺寸为 $2 0 0 ^ { * } 1 0 0$ ，包含8类地物的高光谱图像进行测试；IndianPines 是AVIRIS传感器于印第安纳洲的农场采集，其中包含220个尺寸为 $1 4 5 ^ { * } 1 4 5$ 的高光谱图像，分为6类地物。

由于模型式(11)中存在平衡参数 $\lambda$ ，因此在进行对比实验前分别取λ为0.001、0.005、0.01、0.05、0.1或0.5，对数据集寻找对模型较优的参数。实验结果表明当λ取0.01时模型能得到较高的聚类精度。

将本文提出的 3DF-SSC 算法的实验结果与 K-means[2]、$\mathrm { S C } ^ { [ 3 ] }$ 、 $\mathrm { S S C } ^ { [ 4 ] }$ 、 $M 3 D F ^ { 3 [ 7 ] }$ 、SS-LRSC 算法[8]和 L2-SSC[]算法的实验结果进行对比。七种算法对四个数据集的聚类精度如表1所示，其中PaviaU和SalinasA数据集的聚类结果如图1和图2所示。K-means和SC 算法是经典的无监督聚类算法，从表1以及图1、2可以看出，这两种仅关注光谱信息的算法取得的聚类效果较为一般，对高光谱像素的判别能力较差，存在大量的误分类和椒盐噪声。而由算法的运行结果可看出，在提取高光谱影像的三维空谱特征后，影像的聚类效果得到了显著提高，可见高光谱遥感影像的空间上下文信息有助于对像素点的识别：对于子空间聚类算法，传统的 SSC 算法的运行结果和 $\mathbf { k }$ -means、SC 算法一样较为一般，而L2-SSC 算法和 SS-LRSC 算法添加空间上下文信息后，遥感影像的聚类效果则有了明显的提高，由此可见，获得空间上下文信息的子空间聚类的聚类效果优异。

表1七种算法在四个数据集上的聚类精度  
Table1 Clustering accuracy of seven algorithms on four datasets   

<html><body><table><tr><td></td><td>K-means</td><td>SC</td><td>SSC</td><td>M3DF3</td><td>SS-LRSC</td><td>L2-SSC</td><td>3DF-SSC</td></tr><tr><td>SalinasA</td><td>65.12</td><td>69.27 66.49</td><td></td><td>81.78</td><td>75.76</td><td>75.14</td><td>90.40</td></tr><tr><td>PaviaC</td><td>64.37</td><td>64.98 58.76</td><td></td><td>85.66</td><td>86.67</td><td>82.16</td><td>89.47</td></tr><tr><td>PaviaU</td><td>56.69</td><td>56.68 54.39</td><td></td><td>70.44</td><td>68.99</td><td>63.30</td><td>74.15</td></tr><tr><td>IndianP</td><td>34.69</td><td>34.69 37.23</td><td></td><td>68.22</td><td>46.13</td><td>44.54</td><td>69.72</td></tr></table></body></html>

+H+ Vyy 佳 ? 原图 K-means SC SSC 佳 M3DF3 SS-LRSC L2-SSC 3DF-SSC

![](images/1784115a1d4fb6a4b556f2965ee924c779b0514ea6834d9c6c3a8a06b43b7107.jpg)  
图2七种算法对SalinasA数据集的聚类结果  
Fig.2Clustering maps of seven algorithms with SalinasA dataset

表1以及图1、2的实验结果表明，在融合三维空谱特征后，本文提出的3DF-SSC 算法的聚类效果都比其他算法要好，四个数据集的聚类精度都能达到 $70 \%$ 左右或以上，尤其是SalinasA的聚类精度高达 $9 0 . 4 0 \%$ 。对于同样是利用三维空谱特征的 $M 3 D F ^ { 3 }$ 算法，本文算法获得的聚类精度也能够有所提高，最高能提高 $8 . 6 2 \%$ ；而与同样是利用空间上下文信息对子空间聚类算法进行改进的L2-SSC 算法和 SS-LRSC 算法相比，本文算法的运行结果也更为优异，尤其是IndianP数据集，聚类精度比L2-SSC算法提高了 $2 5 . 1 8 \%$ 。由此可见，本文提出的3DF-SSC 算法能有效对高光谱遥感影像进行聚类。

# 5 结束语

本文提出的结合三维空谱特征和子空间聚类算法的3DF-SSC算法，在关注高光谱影像的光谱信息的同时，也关注空间上下文信息。通过提取高光谱影像像素点的三种三维空谱特征，利用高斯函数由多特征对子空间聚类算法的系数矩阵进行加权，建立了融合三维空谱特征的稀疏子空间聚类模型。模型对四种经典高光谱数据集进行实验，并将实验结果与六种经典聚类算法相比较。实验结果表明，本文提出的3DF-SSC算法在四个数据集上都获得了良好的聚类精度，并且比其他经典算法的实验结果都要更好。

# 参考文献：

[1]邓贤明，苗放，翟涌光，等．基于形态学的两种高光谱目标探测改进算 法[J].中山大学学报：自然科学版，2017,56(1):151-160.(Deng Xianming,Miao Fang, Zhai Yongguang,et al. Two modified target detection algorithms based on morphology for hyperspectral imagery [J].Acta Scientiarum Naturalum Universitatis Sunyatseni,2017,56(1):151-160.)   
[2]Lloyd S.Least squares quantization in PCM[J]. IEEE Trans on Information Theory,1982,28 (2): 129-137.   
[3]Luxburg U.A tutorial on spectral clustering [J]. Statistics and Computing. 2007,17 (4): 395-416.   
[4]Ehsan E,Ren V. Sparse subspace clustering [C]// IEEE Conference on Computer Vision and Pattern Recognition. Washington DC: IEEE Computer Society,2009:2790-2797.   
[5]王卫卫，李小平，冯象初，等．稀疏子空间聚类综述[J]．自动化学报， 2015,41(3):1373-1383.(WangWeiwei,LiXiaoping,Feng Xiangchu,etal. A Survey on Sparse Subspace Clustering[J].Acta Automatica Sinica,2015, 41 (3): 1373-1383. )   
[6]Zhai Han, Zhang Hongyan, Zhang Liangpei,et al. A new sparse subspace clusteing algorithm for hyperspectral remote sensing imagery [J],IEEE Geoscience and Remote Sensing Letters,2017,14(1): 43 -47.   
[7]Zhu Jiasong,Hu Jie,Jia Sen,et al.Multiple 3D feature fusion framework for hyperspectral image classification [J]. IEEE Trans on Geoscience and Remote Sensing,2018,56 (4): 1873-1884.   
[8]Xu Jinhuan, Huang Nan, Xiao Liang. Spectral-spatial subspace clustering for hyperspectral images via modulated low-rank representation [Cl/ Proc of IEEE International Geoscience and Remote Sensing Symposium. 2017: 3202-3205   
[9]Shi J,Malik J. Normalized cuts and image segmentation [J]. IEEE Trans on PaUern Analys isand Machine Intelligence,20oo,22(8):888-905.   
[10] Manya VA,Jos MB,Figueiredo Mario A T.Anaugmented Lagrangian approach to the constrained optimization formulation of imaging inverse problems [J]. IEEE Trans on Image Processing,2011,20 (3): 681-695.   
[11] Zhang Hongyan,Zhai Han, Zhang Liangpei,et al.Spectral-spatial sparsesubspace clustering for hyperspectral remote sensing images [J]. IEEE Trans on Geoscience Remote Sensing,2016,54 (6): 3672-3684.   
[12] Ehsan E,Ren V. Sparse subspace clustering: Algorithm,theory，and applications[J].IEEE Transon PatternAnalysis Machine Intelligence,2013, 35 (11): 2765-2781.   
[13] Yuri B,Gareth F. Graph cuts and efficient N-D image segmentation [J]. Computer Visual,2006,70 (2): 109-131.   
[14]李涛，王卫卫，翟栋等．图像分割的加权稀疏子空间聚类方法[J]．系 统工程与电子技术,2014,36 (3):580-585.Li Tao,Wang Weiwei, Zhai Dong，et al.Weighted-sparse subspace clustering method for image segmentation [J].Systems Engineeringand Electronics,2014,36 (3):580- 585.   
[15]胡杰．高光谱遥感影像三维空谱特征提取与小样本分类技术研究[D]. 深圳：深圳大学,2017. (Hu Jie.Three dimensional spectral-spatial feature extraction and small sample clasification technology for Hyperspectral remote sensing image [D]. Shenzhen: Shenzhen University,2017.)   
[16] Grupo De Inteligencia Computacional. Hyperspectral remote sensing scenes [EB/OL].(2014-04-07)[2018-05-16]. http://alweb.ehu.es/ccwintco/index. php?title=Hyperspectral_Remote_Sensing_Scenes.